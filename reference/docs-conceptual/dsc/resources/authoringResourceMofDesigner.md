---
ms.date: 07/08/2020
keywords: DSC,PowerShell,Konfiguration,Setup,Einrichtung
title: Verwenden des Ressourcen-Designers
description: Der Ressourcen-Designer ist ein Gruppe von Cmdlets, die vom Modul xDscResourceDesigner verfügbar gemacht werden und das Erstellen von Windows PowerShell DSC-Ressourcen erleichtern.
ms.openlocfilehash: efe36d045ac3fba3823cb1f812bb5761d238fdf1
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92656493"
---
# <a name="using-the-resource-designer-tool"></a>Verwenden des Ressourcen-Designers

> Gilt für: Windows PowerShell 4.0, Windows PowerShell 5.0

Der Ressourcen-Designer ist ein Satz von Cmdlets, die vom Modul **xDscResourceDesigner** verfügbar gemacht werden und das Erstellen von Windows PowerShell DSC-Ressourcen erleichtern. Die Cmdlets in dieser Ressource helfen beim Erstellen des MOF-Schemas, des Skriptmoduls und der Verzeichnisstruktur für die neue Ressource. Weitere Informationen zu DSC-Ressourcen finden Sie unter [Erstellen von benutzerdefinierten Windows PowerShell DSC-Ressourcen](authoringResource.md). In diesem Artikel wird eine DSC-Ressource zur Verwaltung von Active Directory-Benutzern erstellt. Verwenden Sie das Cmdlet [Install-Module](/powershell/module/PowershellGet/Install-Module) zum Installieren des Moduls **xDscResourceDesigner**.

## <a name="creating-resource-properties"></a>Erstellen von Ressourceneigenschaften

Zunächst werden Eigenschaften festgelegt, die die Ressource verfügbar machen soll. In diesem Beispiel wird ein Active Directory-Benutzer mit den folgenden Eigenschaften definiert.

Parameternamen und Beschreibungen

- **UserName** : Schlüsseleigenschaft, die einen Benutzer eindeutig identifiziert.
- **Ensure** : Gibt an, ob das Benutzerkonto vorhanden („Present“) oder nicht vorhanden („Absent“) sein soll. Für diesen Parameter gibt es nur zwei mögliche Werte.
- **DomainCredential** : Das Domänenkennwort für den Benutzer.
- **Password** : Das gewünschte Kennwort für den Benutzer, um einer Konfiguration zu erlauben, das Benutzerkennwort bei Bedarf zu ändern.

Zum Erstellen der Eigenschaften verwenden wir das Cmdlet `New-xDscResourceProperty`. Mit den folgenden PowerShell-Befehlen werden die oben beschriebenen Eigenschaften erstellt.

```powershell
$UserName = New-xDscResourceProperty –Name UserName -Type String -Attribute Key
$Ensure = New-xDscResourceProperty –Name Ensure -Type String -Attribute Write –ValidateSet "Present", "Absent"
$DomainCredential = New-xDscResourceProperty –Name DomainCredential -Type PSCredential -Attribute Write
$Password = New-xDscResourceProperty –Name Password -Type PSCredential -Attribute Write
```

## <a name="create-the-resource"></a>Erstellen der Ressource

Nachdem die Ressourceneigenschaften nun erstellt wurden, kann das Cmdlet `New-xDscResource` aufgerufen werden, um die Ressource zu erstellen. Vom Cmdlet `New-xDscResource` wird die Liste der Eigenschaften als Parameter verwendet. Es verwendet auch der Pfad, unter dem das Modul erstellt werden soll, den Namen der neuen Ressource und den Namen des Moduls, in dem sie enthalten ist. Der folgende PowerShell-Befehl erstellt die Ressource:

```powershell
New-xDscResource –Name Demo_ADUser –Property $UserName, $Ensure, $DomainCredential, $Password –Path 'C:\Program Files\WindowsPowerShell\Modules' –ModuleName Demo_DSCModule
```

Das Cmdlet `New-xDscResource` erstellt das MOF-Schema, ein Gerüstressourcenskript, die erforderliche Verzeichnisstruktur für die neue Ressource und ein Manifest für das Modul, das die neue Ressource verfügbar macht.

Die MOF-Schemadatei befindet sich in `C:\Program Files\WindowsPowerShell\Modules\Demo_DSCModule\DSCResources\Demo_ADUser\Demo_ADUser.schema.mof`. Ihre Inhalte sind wie folgt.

```
[ClassVersion("1.0.0.0"), FriendlyName("Demo_ADUser")]
class Demo_ADUser : OMI_BaseResource
{
  [Key] string UserName;
  [Write, ValueMap{"Present","Absent"}, Values{"Present","Absent"}] string Ensure;
  [Write, EmbeddedInstance("MSFT_Credential")] String DomainCredential;
  [Write, EmbeddedInstance("MSFT_Credential")] String Password;
};
```

Das Ressourcenskript befindet sich in `C:\Program Files\WindowsPowerShell\Modules\Demo_DSCModule\DSCResources\Demo_ADUser\Demo_ADUser.psm1`.
Es umfasst nicht die eigentliche Logik zum Implementieren der Ressource. Diese müssen Sie selbst hinzufügen. Der Inhalt des Skelettskripts sieht wie folgt aus:

```powershell
function Get-TargetResource
{
  [CmdletBinding()]
  [OutputType([System.Collections.Hashtable])]
  param
  (
    [parameter(Mandatory = $true)]
    [System.String]
    $UserName
  )

  #Write-Verbose "Use this cmdlet to deliver information about command processing."

  #Write-Debug "Use this cmdlet to write debug information while troubleshooting."

  <#
  $returnValue = @{
  UserName = [System.String]
  Ensure = [System.String]
  DomainAdminCredential = [System.Management.Automation.PSCredential]
  Password = [System.Management.Automation.PSCredential]
  }

  $returnValue
  #>
}

function Set-TargetResource
{
  [CmdletBinding()]
  param
  (
    [parameter(Mandatory = $true)]
    [System.String]
    $UserName,

    [ValidateSet("Present","Absent")]
    [System.String]
    $Ensure,

    [System.Management.Automation.PSCredential]
    $DomainAdminCredential,

    [System.Management.Automation.PSCredential]
    $Password
  )

  #Write-Verbose "Use this cmdlet to deliver information about command processing."

  #Write-Debug "Use this cmdlet to write debug information while troubleshooting."

  #Include this line if the resource requires a system reboot.
  #$global:DSCMachineStatus = 1
}

function Test-TargetResource
{
  [CmdletBinding()]
  [OutputType([System.Boolean])]
  param
  (
    [parameter(Mandatory = $true)]
    [System.String]
    $UserName,

    [ValidateSet("Present","Absent")]
    [System.String]
    $Ensure,

    [System.Management.Automation.PSCredential]
    $DomainAdminCredential,

    [System.Management.Automation.PSCredential]
    $Password
  )

  #Write-Verbose "Use this cmdlet to deliver information about command processing."

  #Write-Debug "Use this cmdlet to write debug information while troubleshooting."

  <#
  $result = [System.Boolean]

  $result
  #>
}

Export-ModuleMember -Function *-TargetResource
```

## <a name="updating-the-resource"></a>Aktualisieren der Ressource

Wenn Sie die Parameterliste der Ressource erweitern oder ändern müssen, können Sie das Cmdlet `Update-xDscResource` aufrufen. Das Cmdlet aktualisiert die Ressource mit einer neuen Parameterliste. Wenn Sie bereits Logik zu Ihrem Ressourcenskript hinzugefügt haben, bleibt diese davon unberührt.

Angenommen, Sie möchten den Zeitpunkt der letzten Anmeldung des Benutzers zur Ressource hinzufügen. Anstatt die Ressource vollständig neu zu schreiben, können Sie `New-xDscResourceProperty` aufrufen, um die Eigenschaft neu zu erstellen, und diese neue Eigenschaft dann mit `Update-xDscResource` zur Eigenschaftenliste hinzufügen.

```powershell
$lastLogon = New-xDscResourceProperty –Name LastLogon –Type Hashtable –Attribute Write –Description "For mapping users to their last log on time"
Update-xDscResource –Name 'Demo_ADUser' –Property $UserName, $Ensure, $DomainCredential, $Password, $lastLogon -Force
```

## <a name="testing-a-resource-schema"></a>Testen eines Ressourcenschemas

Der Ressourcen-Designer stellt ein weiteres Cmdlet zur Verfügung, mit dem Sie die Gültigkeit eines MOF-Schemas testen können, das Sie manuell geschrieben haben. Rufen Sie das Cmdlet `Test-xDscSchema` auf, und übergeben Sie dabei den Pfad eines MOF-Ressourcenschemas als Parameter. Das Cmdlet gibt alle Fehler im Schema aus.

### <a name="see-also"></a>Weitere Informationen

#### <a name="concepts"></a>Konzepte

[Erstellen von benutzerdefinierten Windows PowerShell DSC-Ressourcen](authoringResource.md)

#### <a name="other-resources"></a>Weitere Ressourcen

[xDscResourceDesigner-Modul](https://www.powershellgallery.com/packages/xDscResourceDesigner/1.12.0.0)
