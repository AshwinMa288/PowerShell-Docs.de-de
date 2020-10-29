---
ms.date: 05/14/2020
keywords: powershell,cmdlet
title: Ausführen des zweiten Hops in PowerShell-Remoting
description: In diesem Artikel werden die verschiedenen Methoden zum Konfigurieren der Authentifizierung des zweiten Hops für PowerShell-Remoting behandelt, einschließlich der Auswirkungen auf die Sicherheit und Empfehlungen.
ms.openlocfilehash: 905b27b4e6c612249c945a741bbe0d2ba9ae28aa
ms.sourcegitcommit: 9080316e3ca4f11d83067b41351531672b667b7a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2020
ms.locfileid: "92501370"
---
# <a name="making-the-second-hop-in-powershell-remoting"></a>Ausführen des zweiten Hops in PowerShell-Remoting

Das sogenannte „zweite Hop-Problem“ bezieht sich auf folgende Situation:

1. Sie sind bei _ServerA_ angemeldet.
2. Sie starten von _ServerA_ aus eine PowerShell-Remotesitzung, um eine Verbindung mit _ServerB_ herzustellen.
3. Ein auf _ServerB_ über Ihre PowerShell-Remotesitzung ausgeführter Befehl versucht, auf eine Ressource auf _ServerC_ zuzugreifen.
4. Der Zugriff auf die Ressource auf _ServerC_ wird verweigert, da die Anmeldeinformationen, die Sie zum Erstellen der PowerShell-Remotesitzung verwendet haben, nicht von _ServerB_ an _ServerC_ übergeben werden.

Es gibt verschiedene Möglichkeiten, um dieses Problem zu lösen. In der folgenden Tabelle werden die Methoden in der Reihenfolge ihrer Präferenz aufgelistet.

|                      Konfiguration                       |                                  Hinweis                                  |
| -------------------------------------------------------- | ---------------------------------------------------------------------- |
| CredSSP                                                  | Ausgeglichene Benutzerfreundlichkeit und Sicherheit                                      |
| Ressourcenbasierte eingeschränkte Kerberos-Delegierung           | Höhere Sicherheit mit einfacherer Konfiguration                             |
| Eingeschränkte Kerberos-Delegierung                          | Hohe Sicherheit, erfordert jedoch einen Domänenadministrator                         |
| Kerberos-Delegierung (uneingeschränkt)                      | Nicht empfohlen                                                        |
| Just Enough Administration (JEA)                         | Kann die beste Sicherheit bieten, erfordert jedoch eine ausführlichere Konfiguration |
| PSSessionConfiguration mithilfe von RunAs                       | Einfachere Konfiguration, erfordert jedoch Verwaltung von Anmeldeinformationen                |
| Übergeben von Anmeldeinformationen innerhalb eines `Invoke-Command`-Skriptblocks | Am einfachsten zu verwenden, jedoch müssen Anmeldeinformationen bereitgestellt werden                       |

## <a name="credssp"></a>CredSSP

Sie können den [Credential Security Support Provider (CredSSP)][credssp] für die Authentifizierung verwenden.
CredSSP speichert Anmeldeinformationen auf dem Remoteserver  _ServerB_ . Der Server wird dadurch der Gefahr von Angriffen zum Diebstahl der Anmeldeinformationen ausgesetzt. Wenn der Remotecomputer kompromittiert ist, hat der Angreifer Zugriff auf die Anmeldeinformationen des Benutzers. CredSSP ist standardmäßig sowohl auf Client- als auch auf Servercomputern deaktiviert. Sie sollten CredSSP nur in absolut vertrauenswürdigen Umgebungen aktivieren. Beispielsweise wenn ein Domänenadministrator eine Verbindung mit einem Domänencontroller herstellt, weil der Domänencontroller hochgradig vertrauenswürdig ist.

Weitere Informationen zu Sicherheitsaspekten bei der Verwendung von CredSSP für PowerShell-Remoting finden Sie unter [Versehentliche Sabotage: Vorsicht vor CredSSP][beware].

Weitere Informationen zu Angriffen zum Diebstahl von Anmeldeinformationen finden Sie unter [Abschwächen von Pass-the-Hash-Angriffen (PtH) und anderen Techniken zum Diebstahl von Anmeldeinformationen][pth].

Ein Beispiel zum Aktivieren und Verwenden von CredSSP für PowerShell-Remoting finden Sie unter [Enable PowerShell "Second-Hop" Functionality with CredSSP][credssp-psblog] (Aktivieren der PowerShell-Funktion für zweiten Hop mit CredSSP).

**Vorteile**

- Die Lösung eignet sich für alle Server mit Windows Server 2008 oder höher.

**Nachteile**

- birgt Sicherheitsrisiken
- erfordert die Konfiguration von Client- und Serverrollen
- Funktioniert nicht mit der Gruppe „geschützte Benutzer“. Weitere Informationen finden Sie unter [Sicherheitsgruppe „Geschützte Benutzer“][protected-users].

## <a name="kerberos-constrained-delegation"></a>Eingeschränkte Kerberos-Delegierung

Sie können eingeschränkte Legacydelegierung (nicht ressourcenbasiert) verwenden, um den zweiten Hop auszuführen. Konfigurieren Sie die eingeschränkte Kerberos-Delegierung mit der Option „Beliebiges Authentifizierungsprotokoll verwenden“, um den Protokollübergang zu ermöglichen.

**Vorteile**

- erfordert keine besondere Codierung
- kein Speichern von Anmeldeinformationen

**Nachteile**

- keine Unterstützung für den zweiten Hop für WinRM
- Erfordert Domänenadministratorzugriff für die Konfiguration
- muss auf dem Active Directory-Objekt des Remoteservers konfiguriert werden ( _ServerB_ )
- auf einen Server begrenzt; kann Domänen oder Gesamtstrukturen nicht überschreiten
- erfordert Rechte zum Aktualisieren von Objekten und Dienstprinzipalnamen (SPN)
- _ServerB_ kann ein Kerberos-Ticket für _ServerC_ im Auftrag des Benutzers abrufen, ohne dass ein Benutzereingriff erforderlich ist.

> [!NOTE]
> Active Directory-Konten mit dem Eigenschaftensatz **Konto ist vertraulich und kann nicht delegiert werden** können nicht delegiert werden. Weitere Informationen finden Sie unter [Security Focus: Analysing 'Account is sensitive and cannot be delegated' for Privileged Accounts][blog] (Sicherheit im Fokus: Analyse von „Konto ist vertraulich und kann nicht delegiert werden“ für privilegierte Konten) und [Kerberos-Authentifizierungstools und -Einstellungen][ktools].

## <a name="resource-based-kerberos-constrained-delegation"></a>Ressourcenbasierte eingeschränkte Kerberos-Delegierung

Mithilfe von ressourcenbasierter eingeschränkter Kerberos-Delegierung (in Windows Server 2012 eingeführt) können Sie die Delegierung der Anmeldeinformationen für das Serverobjekt konfigurieren, in dem sich Ressourcen befinden. Im zuvor beschriebenen zweiten Hop-Szenario konfigurieren Sie _ServerC_ und geben an, von wo aus Anmeldeinformationen akzeptiert werden.

**Vorteile**

- kein Speichern von Anmeldeinformationen
- Konfiguriert mithilfe von PowerShell-Cmdlets Keine besondere Codierung erforderlich
- Erfordert keinen Domänenadministratorzugriff für die Konfiguration
- domänen- und gesamtstrukturübergreifende Funktionsweise

**Nachteile**

- erfordert Windows Server 2012 oder höher
- keine Unterstützung für den zweiten Hop für WinRM
- erfordert Rechte zum Aktualisieren von Objekten und Dienstprinzipalnamen (SPN)

> [!NOTE]
> Active Directory-Konten mit dem Eigenschaftensatz **Konto ist vertraulich und kann nicht delegiert werden** können nicht delegiert werden. Weitere Informationen finden Sie unter [Security Focus: Analysing 'Account is sensitive and cannot be delegated' for Privileged Accounts][blog] (Sicherheit im Fokus: Analyse von „Konto ist vertraulich und kann nicht delegiert werden“ für privilegierte Konten) und [Kerberos-Authentifizierungstools und -Einstellungen][ktools].

### <a name="example"></a>Beispiel

Sehen wir uns ein PowerShell-Beispiel an, bei dem _ServerC_ für eine ressourcenbasierte eingeschränkte Delegierung konfiguriert wird, um delegierte Anmeldeinformationen von einem _ServerB_ zu ermöglichen. In diesem Beispiel wird davon ausgegangen, dass alle Server Windows Server 2012 oder höher ausführen und dass für jede Domäne jedes eingesetzten Servers mindestens ein Windows Server 2012-Domänencontroller vorhanden ist.

Bevor Sie die eingeschränkte Delegierung konfigurieren können, müssen Sie das `RSAT-AD-PowerShell`-Feature hinzufügen, um das Active Directory-PowerShell-Modul zu installieren und anschließend dieses Modul in die Sitzung zu importieren:

```powershell
Add-WindowsFeature RSAT-AD-PowerShell
Import-Module ActiveDirectory
Get-Command -ParameterName PrincipalsAllowedToDelegateToAccount
```

Mehrere verfügbare Cmdlets haben jetzt einen **PrincipalsAllowedToDelegateToAccount** -Parameter:

```Output
CommandType Name                 ModuleName
----------- ----                 ----------
Cmdlet      New-ADComputer       ActiveDirectory
Cmdlet      New-ADServiceAccount ActiveDirectory
Cmdlet      New-ADUser           ActiveDirectory
Cmdlet      Set-ADComputer       ActiveDirectory
Cmdlet      Set-ADServiceAccount ActiveDirectory
Cmdlet      Set-ADUser           ActiveDirectory
```

Der Parameter **PrincipalsAllowedToDelegateToAccount** legt das Active Directory-Objektattribut **MsDS-AllowedToActOnBehalfOfOtherIdentity** fest, das eine Zugriffssteuerungsliste (access control list, ACL) enthält. Diese gibt an, welche Konten die Berechtigung zum Delegieren von Anmeldeinformationen für das zugehörige Konto haben (in unserem Beispiel das Computerkonto für _ServerA_ ).

Richten Sie nun die Variablen ein, die wir verwenden, um die Server darzustellen:

```powershell
# Set up variables for reuse
$ServerA = $env:COMPUTERNAME
$ServerB = Get-ADComputer -Identity ServerB
$ServerC = Get-ADComputer -Identity ServerC
```

WinRM (und somit die PowerShell-Remoting) wird standardmäßig als Computerkonto ausgeführt. Dies sehen Sie anhand der **StartName** -Eigenschaft des `winrm`-Diensts:

```powershell
Get-CimInstance Win32_Service -Filter 'Name="winrm"' | Select-Object StartName
```

```Output
StartName
---------
NT AUTHORITY\NetworkService
```

Damit _ServerC_ die Delegierung aus einer PowerShell-Remoting-Sitzung auf _ServerB_ zulässt, vergeben wir Zugriffsrechte, indem wir den Parameter **PrincipalsAllowedToDelegateToAccount** von _ServerC_ auf das Computerobjekt von _ServerB_ festlegen:

```powershell
# Grant resource-based Kerberos constrained delegation
Set-ADComputer -Identity $ServerC -PrincipalsAllowedToDelegateToAccount $ServerB

# Check the value of the attribute directly
$x = Get-ADComputer -Identity $ServerC -Properties msDS-AllowedToActOnBehalfOfOtherIdentity
$x.'msDS-AllowedToActOnBehalfOfOtherIdentity'.Access

# Check the value of the attribute indirectly
Get-ADComputer -Identity $ServerC -Properties PrincipalsAllowedToDelegateToAccount
```

Das Kerberos-[Schlüsselverteilungscenter (KDC)](/windows/win32/secauthn/key-distribution-center) speichert verweigerte Zugriffsversuche (negativer Cache) über einen Zeitraum von 15 Minuten. Wenn _ServerB_ zuvor versucht hat, auf _ServerC_ zuzugreifen, müssen Sie zum Löschen des Caches auf _ServerB_ folgenden Befehl aufrufen:

```powershell
Invoke-Command -ComputerName $ServerB.Name -Credential $cred -ScriptBlock {
    klist purge -li 0x3e7
}
```

Sie können den Computer auch neu starten oder mindestens 15 Minuten warten, bevor Sie den Cache löschen.

Nach dem Löschen des Cache können Sie erfolgreich Code vom _ServerA_ über _ServerB_ auf _ServerC_ ausführen:

```powershell
# Capture a credential
$cred = Get-Credential Contoso\Alice

# Test kerberos double hop
Invoke-Command -ComputerName $ServerB.Name -Credential $cred -ScriptBlock {
    Test-Path \\$($using:ServerC.Name)\C$
    Get-Process lsass -ComputerName $($using:ServerC.Name)
    Get-EventLog -LogName System -Newest 3 -ComputerName $($using:ServerC.Name)
}
```

In diesem Beispiel wird die `$using`-Variable verwendet, um die `$ServerC`-Variable für _ServerB_ sichtbar zu machen.
Weitere Informationen zur `$using`-Variable finden Sie unter [About Remote Variables (Informationen zu Remote-Variablen)](/powershell/module/Microsoft.PowerShell.Core/About/about_Remote_Variables).

Damit mehrere Server Anmeldeinformationen an _ServerC_ delegieren können, müssen Sie den Wert des Parameters **PrincipalsAllowedToDelegateToAccount** auf _ServerC_ auf ein Array festlegen:

```powershell
# Set up variables for each server
$ServerB1 = Get-ADComputer -Identity ServerB1
$ServerB2 = Get-ADComputer -Identity ServerB2
$ServerB3 = Get-ADComputer -Identity ServerB3
$ServerC  = Get-ADComputer -Identity ServerC

# Grant resource-based Kerberos constrained delegation
Set-ADComputer -Identity $ServerC `
    -PrincipalsAllowedToDelegateToAccount @($ServerB1,$ServerB2,$ServerB3)
```

Wenn Sie den zweiten Hop zwischen Domänen vornehmen möchten, müssen Sie den vollqualifizierten Domänennamen (FQDN) des Domänencontrollers jener Domäne hinzufügen, zu der _ServerB_ gehört:

```powershell
# For ServerC in Contoso domain and ServerB in other domain
$ServerB = Get-ADComputer -Identity ServerB -Server dc1.alpineskihouse.com
$ServerC = Get-ADComputer -Identity ServerC
Set-ADComputer -Identity $ServerC -PrincipalsAllowedToDelegateToAccount $ServerB
```

Um die Delegierung von Anmeldeinformationen an ServerC zu löschen, müssen Sie den Wert des Parameters **PrincipalsAllowedToDelegateToAccount** auf _ServerC_ auf `$null` festlegen:

```powershell
Set-ADComputer -Identity $ServerC -PrincipalsAllowedToDelegateToAccount $null
```

### <a name="information-on-resource-based-kerberos-constrained-delegation"></a>Informationen zu ressourcenbasierter eingeschränkter Kerberos-Delegierung

- [Neues bei der Kerberos-Authentifizierung][whats-new]
- [How Windows Server 2012 Eases the Pain of Kerberos Constrained Delegation, Part 1 (Wie Windows Server 2012 bei den Problemen mit der eingeschränkten Kerberos-Delegierung Abhilfe schafft, Teil 1)][kcd2012-1]
- [How Windows Server 2012 Eases the Pain of Kerberos Constrained Delegation, Part 2 (Wie Windows Server 2012 bei den Problemen mit der eingeschränkten Kerberos-Delegierung Abhilfe schafft, Teil 2)][kcd2012-2]
- [Understanding Kerberos Constrained Delegation for Azure Active Directory Application Proxy Deployments with Integrated Windows Authentication (Grundlegendes zur eingeschränkten Kerberos-Delegierung für Azure Active Directory Application Proxy-Bereitstellungen mit integrierter Windows-Authentifizierung)][kcdpaper]
- [[MS-ADA2] Active Directory-Schemaattribute M2.210 msDS-AllowedToActOnBehalfOfOtherIdentity-Attribut][MS-ADA2]
- [[MS-SFU] Kerberos-Protokollerweiterungen: Protokoll 1.3.2 S4U2proxy für Service-for-User und eingeschränkte Delegierung][MS-SFU]
- [Remote Administration Without Constrained Delegation Using PrincipalsAllowedToDelegateToAccount (Remoteverwaltung ohne eingeschränkte Delegierung mit PrincipalsAllowedToDelegateToAccount)][remote-admin]

## <a name="kerberos-delegation-unconstrained"></a>Kerberos-Delegierung (uneingeschränkt)

Sie können auch die uneingeschränkte Kerberos-Delegierung verwenden, um den zweiten Hop ausführen. Wie in allen Kerberos-Szenarios werden Anmeldeinformationen nicht gespeichert. Diese Methode unterstützt nicht den zweiten Hop für WinRM.

> [!WARNING]
> Diese Methode bietet keine Kontrolle darüber, wo die delegierten Anmeldeinformationen verwendet werden. Sie ist weniger sicher als CredSSP. Diese Methode sollte nur für Testszenarios verwendet werden.

## <a name="just-enough-administration-jea"></a>Just Enough Administration (JEA)

Mit JEA können Sie einschränken, welche Befehle ein Administrator während einer PowerShell-Sitzung ausführen darf. Das Toolkit kann verwendet werden, um das zweite Hop-Problem zu lösen.

Informationen zu JEA finden Sie unter [Just Enough Administration](/powershell/scripting/learn/remoting/jea/overview).

**Vorteile**

- keine Kennwortverwaltungsaufgaben bei Verwendung eines virtuellen Kontos

**Nachteile**

- erfordert WMF 5.0 oder höher
- erfordert die Konfiguration auf jedem Zwischenserver ( _ServerB_ ).

## <a name="pssessionconfiguration-using-runas"></a>PSSessionConfiguration mithilfe von RunAs

Sie können eine Sitzungskonfiguration auf _ServerB_ erstellen und ihren **RunAsCredential** -Parameter festlegen.

Weitere Informationen zur Verwendung von **PSSessionConfiguration** und **RunAs** , um das zweite Hop-Problem zu lösen, finden Sie unter [Eine weitere Lösung für Multi-Hop-PowerShell-Remoting][pssessionconfig].

**Vorteile**

- funktioniert mit jedem Server mit WMF 3.0 oder höher

**Nachteile**

- erfordert die Konfiguration von **PSSessionConfiguration** und **RunAs** auf jedem Zwischenserver ( _ServerB_ )
- erfordert Kennwortverwaltungsaufgaben bei Verwendung eines Domänen- **RunAs** -Kontos

## <a name="pass-credentials-inside-an-invoke-command-script-block"></a>Übergeben von Anmeldeinformationen innerhalb eines Invoke-Command-Skriptblocks

Anmeldeinformationen können innerhalb des **ScriptBlock** -Parameters für einen Aufruf des [Invoke-Command](/powershell/module/microsoft.powershell.core/invoke-command)-Cmdlet übergeben werden.

**Vorteile**

- erfordert keine spezielle Serverkonfiguration
- funktioniert auf jedem Server mit WMF 2.0 oder höher

**Nachteile**

- erfordert eine umständliche Codetechnik
- Wenn WMF 2.0 ausgeführt wird, wird eine andere Syntax zum Übergeben von Argumenten an eine Remotesitzung benötigt.

### <a name="example"></a>Beispiel

Das folgende Beispiel zeigt, wie Anmeldeinformationen in einem **Invoke-Command** -Skriptblock übergeben werden:

```powershell
# This works without delegation, passing fresh creds
# Note $Using:Cred in nested request
$cred = Get-Credential Contoso\Administrator
Invoke-Command -ComputerName ServerB -Credential $cred -ScriptBlock {
    hostname
    Invoke-Command -ComputerName ServerC -Credential $Using:cred -ScriptBlock {hostname}
}
```

## <a name="see-also"></a>Weitere Informationen

[Sicherheitsaspekte von PowerShell-Remoting](WinRMSecurity.md)

<!-- link references -->
[blog]: /archive/blogs/poshchap/security-focus-analysing-account-is-sensitive-and-cannot-be-delegated-for-privileged-accounts
[ktools]: /previous-versions/windows/it-pro/windows-server-2003/cc738673(v=ws.10)
[credssp]: /windows/win32/secauthn/credential-security-support-provider
[beware]: https://www.powershellmagazine.com/2014/03/06/accidental-sabotage-beware-of-credssp
[pth]: https://www.microsoft.com/download/details.aspx?id=36036
[credssp-psblog]: https://devblogs.microsoft.com/scripting/enable-powershell-second-hop-functionality-with-credssp/
[whats-new]: /previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh831747(v=ws.11)
[kcd2012-1]: https://www.itprotoday.com/windows-server/how-windows-server-2012-eases-pain-kerberos-constrained-delegation-part-1
[kcd2012-2]: https://www.itprotoday.com/windows-server/how-windows-server-2012-eases-pain-kerberos-constrained-delegation-part-2
[kcdpaper]: https://aka.ms/kcdpaper
[MS-ADA2]: /openspecs/windows_protocols/ms-ada2/cea4ac11-a4b2-4f2d-84cc-aebb4a4ad405
[MS-SFU]: /openspecs/windows_protocols/ms-sfu/bde93b0e-f3c9-4ddf-9f44-e1453be7af5a
[remote-admin]: /archive/blogs/taylorb/remote-administration-without-constrained-delegation-using-principalsallowedtodelegatetoaccount
[pssessionconfig]: /archive/blogs/sergey_babkins_blog/another-solution-to-multi-hop-powershell-remoting
[protected-users]: /windows-server/security/credentials-protection-and-management/protected-users-security-group
