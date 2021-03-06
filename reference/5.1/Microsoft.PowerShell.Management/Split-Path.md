---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/split-path?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Split-Path
ms.openlocfilehash: 5d92acbe080b0d232047f1184c9a369b8837845c
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93214399"
---
# Split-Path

## ZUSAMMENFASSUNG
Gibt den angegebenen Teil eines Pfads zurück.

## SYNTAX

### Parametriset (Standard)

```
Split-Path [-Path] <String[]> [-Parent] [-Resolve] [-Credential <PSCredential>] [-UseTransaction]
 [<CommonParameters>]
```

### Noqualifierset

```
Split-Path [-Path] <String[]> [-NoQualifier] [-Resolve] [-Credential <PSCredential>] [-UseTransaction]
 [<CommonParameters>]
```

### Blätter Satz

```
Split-Path [-Path] <String[]> [-Leaf] [-Resolve] [-Credential <PSCredential>] [-UseTransaction]
 [<CommonParameters>]
```

### Qualifierset

```
Split-Path [-Path] <String[]> [-Qualifier] [-Resolve] [-Credential <PSCredential>] [-UseTransaction]
 [<CommonParameters>]
```

### Isabsoluteset

```
Split-Path [-Path] <String[]> [-Resolve] [-IsAbsolute] [-Credential <PSCredential>] [-UseTransaction]
 [<CommonParameters>]
```

### Literalpathset

```
Split-Path -LiteralPath <String[]> [-Resolve] [-Credential <PSCredential>] [-UseTransaction]
 [<CommonParameters>]
```

## DESCRIPTION

Das **Split-Path-** Cmdlet gibt nur den angegebenen Teil eines Pfads zurück, z. b. den übergeordneten Ordner, einen Unterordner oder einen Dateinamen.
Außerdem können Elemente abgerufen werden, auf die von dem geteilten Pfad verwiesen wird, und es kann angegeben werden, ob es sich um einen relativen oder absoluten Pfad handelt.

Sie können mit diesem Cmdlet nur einen ausgewählten Teil eines Pfads abrufen oder senden.

## BEISPIELE

### Beispiel 1: Holen Sie sich den Qualifizierer eines Pfads.

```
PS C:\> Split-Path -Path "HKCU:\Software\Microsoft" -Qualifier
HKCU:
```

Mit diesem Befehl wird nur der Qualifizierer des Pfads zurückgegeben.
Der Qualifizierer ist das Laufwerk.

### Beispiel 2: Anzeigen von Dateinamen

```
PS C:\> Split-Path -Path "C:\Test\Logs\*.log" -Leaf -Resolve
Pass1.log
Pass2.log
...
```

Mit diesem Befehl werden die Dateien angezeigt, auf die vom geteilten Pfad verwiesen wird.
Da dieser Pfad auf das letzte Element aufgeteilt ist, das auch als Blatt bezeichnet wird, zeigt der Befehl nur die Dateinamen an.

Der *Resolve* -Parameter weist **Split-Path** an, die Elemente anzuzeigen, auf die der geteilte Pfad verweist, anstatt den geteilten Pfad anzuzeigen.

Wie alle **Split-Path-** Befehle gibt dieser Befehl Zeichen folgen zurück.
Es werden keine **FileInfo** -Objekte zurückgegeben, die die Dateien darstellen.

### Beispiel 3: Get the parent Container

```
PS C:\> Split-Path -Path "C:\WINDOWS\system32\WindowsPowerShell\V1.0\about_*.txt"
C:\WINDOWS\system32\WindowsPowerShell\V1.0
```

Mit diesem Befehl werden nur die übergeordneten Container des Pfads zurückgegeben.
Da keine Parameter zum Angeben der Teilung enthalten sind, verwendet **Split-Path** den Standard *Wert für Split* Location, der übergeordnet ist.

### Beispiel 4: bestimmt, ob ein Pfad absolut ist

```
PS C:\> Split-Path -Path ".\My Pictures\*.jpg" -IsAbsolute
False
```

Mit diesem Befehl wird bestimmt, ob der Pfad relativ oder absolut ist.
In diesem Fall wird $false zurückgegeben, da der Pfad relativ zum aktuellen Ordner ist, der durch einen Punkt (.) dargestellt wird.

### Beispiel 5: Ändern des Speicher Orts in einen angegebenen Pfad

```
PS C:\> Set-Location (Split-Path -Path $profile)
PS C:\Documents and Settings\User01\My Documents\WindowsPowerShell>
```

Mit diesem Befehl wird der Speicherort in den Ordner geändert, der das PowerShell-Profil enthält.

Der-Befehl in Klammern verwendet **Split-Path** , um nur das übergeordnete Element des Pfads zurückzugeben, der in der integrierten $profile Variablen gespeichert ist.
Der *Parent* -Parameter ist der standardmäßige Split Location-Parameter.
Aus diesem Grund können Sie Sie im Befehl weglassen.
Die Klammern leiten PowerShell an, den Befehl zuerst auszuführen.
Dies ist eine hilfreiche Möglichkeit, um zu einem Ordner zu wechseln, der über einen langen Pfadnamen verfügt.

### Beispiel 6: Aufteilen eines Pfads mithilfe der Pipeline

```
PS C:\> 'C:\Documents and Settings\User01\My Documents\My Pictures' | Split-Path
C:\Documents and Settings\User01\My Documents
```

Dieser Befehl verwendet einen Pipeline Operator (|), um einen Pfad an **Split-Path** zu senden.
Der Pfad ist in Anführungszeichen eingeschlossen, um anzugeben, dass es sich um ein einzelnes Token handelt.

## PARAMETERS

### -Credential

> [!NOTE]
> Dieser Parameter wird von Anbietern, die mit PowerShell installiert wurden, nicht unterstützt.
> Verwenden Sie zum Annehmen der Identität eines anderen Benutzers oder zum herauf Stufen ihrer Anmelde Informationen bei der Ausführung dieses Cmdlets "Start [-Command](../Microsoft.PowerShell.Core/Invoke-Command.md)".

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -IsAbsolute

Gibt an, dass dieses Cmdlet $true zurückgibt, wenn der Pfad absolut ist, und $false, wenn er relativ ist.
Ein absoluter Pfad weist eine Länge größer als 0 (null) auf und verwendet keinen Punkt (.), um den aktuellen Pfad anzugeben.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: IsAbsoluteSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Blatt

Gibt an, dass dieses Cmdlet nur das letzte Element bzw. den letzten Container im Pfad zurückgibt.
Beispielsweise wird im Pfad `C:\Test\Logs\Pass1.log` nur Pass1. log zurückgegeben.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: LeafSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Literalpath

Gibt die zu teilenden Pfade an.
Im Gegensatz zu *Path* wird der Wert von *LiteralPath* genau so verwendet, wie er eingegeben wurde.
Es werden keine Zeichen als Platzhalter interpretiert.
Wenn der Pfad Escapezeichen enthält, müssen Sie ihn in einfache Anführungszeichen einschließen.
Einfache Anführungszeichen veranlassen PowerShell, Zeichen nicht als Escapesequenzen zu interpretieren.

```yaml
Type: System.String[]
Parameter Sets: LiteralPathSet
Aliases: PSPath

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Noqualifizierer

Gibt an, dass dieses Cmdlet den Pfad ohne den Qualifizierer zurückgibt.
Für den Dateisystem- bzw. Registrierungsanbieter ist der Qualifizierer das Laufwerk des Anbieterpfads, beispielsweise %%amp;quot;C:%%amp;quot; oder %%amp;quot;HKCU:%%amp;quot;.
Beispielsweise wird im Pfad `C:\Test\Logs\Pass1.log` nur "\test\logs\pass1.log" zurückgegeben.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: NoQualifierSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Übergeordnetes Element

Gibt an, dass dieses Cmdlet nur die übergeordneten Container des Elements oder des Containers zurückgibt, der durch den Pfad angegeben wird.
Beispielsweise gibt es im Pfad den Wert `C:\Test\Logs\Pass1.log` c:\test\logs.
Der *Parent* -Parameter ist der standardmäßige Split Location-Parameter.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: ParentSet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Path

Gibt die zu teilenden Pfade an.
Platzhalterzeichen sind zulässig.
Wenn der Pfad Leerzeichen enthält, müssen Sie ihn in Anführungszeichen einschließen.
Sie können einen Pfad auch über die Pipeline an dieses Cmdlet übergeben.

```yaml
Type: System.String[]
Parameter Sets: ParentSet, NoQualifierSet, LeafSet, QualifierSet, IsAbsoluteSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### -Qualifizierer

Gibt an, dass dieses Cmdlet nur den Qualifizierer des angegebenen Pfads zurückgibt.
Für den Dateisystem- bzw. Registrierungsanbieter ist der Qualifizierer das Laufwerk des Anbieterpfads, beispielsweise %%amp;quot;C:%%amp;quot; oder %%amp;quot;HKCU:%%amp;quot;.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: QualifierSet
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Auflösen

Gibt an, dass dieses Cmdlet die Elemente anzeigt, auf die vom resultierenden geteilten Pfad verwiesen wird, anstatt die Pfad Elemente anzuzeigen.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -UseTransaction

Schließt den Befehl in die aktive Transaktion ein.
Dieser Parameter ist nur gültig, wenn gerade eine Transaktion ausgeführt wird.
Weitere Informationen finden Sie unter %%amp;quot;about_Transactions%%amp;quot;.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: usetx

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## EINGABEN

### System.String

Sie können eine Zeichenfolge weiterreichen, die einen Pfad zu diesem Cmdlet enthält.

## AUSGABEN

### System. String, System. Boolean

**Split-Path** gibt Text Zeichenfolgen zurück.
Wenn Sie den *Resolve* -Parameter angeben, gibt **Split-Path** eine Zeichenfolge zurück, die den Speicherort der Elemente beschreibt. Sie gibt keine Objekte zurück, die die Elemente darstellen, wie z. b. ein **FileInfo** -oder **RegistryKey** -Objekt.

Wenn Sie den *IsAbsolute* -Parameter angeben, gibt **Split-Path** einen **booleschen** Wert zurück.

## HINWEISE

* Die Split Location-Parameter ( *Qualifizierer* , über *geordnetes* Element, *Blatt* und *noqualifizierer* ) sind exklusiv. In einem Befehl kann immer nur ein Parameter angegeben werden.

  Die Cmdlets, die das **Pfad** -Substantiv enthalten (die **path** -Cmdlets), funktionieren mit Pfadnamen und geben die Namen in einem präzisen Format zurück, das von allen PowerShell-Anbietern interpretiert werden kann.
Diese können in Programmen und Skripts verwendet werden, in denen ein Pfadname vollständig oder teilweise in einem bestimmten Format angezeigt werden soll.
Verwenden Sie diese in der Weise, in der Sie **dirname** , **normpath** , **realpath** , **Join** oder andere Pfad Manipulatoren verwenden.

  Sie können die **Pfad** -Cmdlets mit verschiedenen Anbietern verwenden.
Hierzu gehören das Dateisystem, die Registrierung und die Zertifikat Anbieter.

  **Split-Path** ist für die Arbeit mit den Daten konzipiert, die von beliebigen Anbietern verfügbar gemacht werden.
Um die in Ihrer Sitzung verfügbaren Anbieter aufzulisten, geben Sie ein `Get-PSProvider` .
Weitere Informationen finden Sie unter %%amp;quot;about_Providers%%amp;quot;.

## VERWANDTE LINKS

[Convert-Path](Convert-Path.md)

[Join-Path](Join-Path.md)

[Resolve-Path](Resolve-Path.md)

[Test-Path](Test-Path.md)
