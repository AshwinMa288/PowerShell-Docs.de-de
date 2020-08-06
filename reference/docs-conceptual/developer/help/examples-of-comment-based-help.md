---
title: Beispiele für die kommentarbasierte Hilfe
ms.date: 09/12/2016
ms.openlocfilehash: fe5d054c84952367a4e7c2d5d9e32551a4e5c3a8
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87772296"
---
# <a name="examples-of-comment-based-help"></a>Beispiele für die kommentarbasierte Hilfe

Dieses Thema enthält ein Beispiel für die Verwendung der Kommentar basierten Hilfe für Skripts und Funktionen.

## <a name="example-1-comment-based-help-for-a-function"></a>Beispiel 1: Kommentar basierte Hilfe für eine Funktion

 Die folgende Beispiel Funktion enthält eine Kommentar basierte Hilfe.

```powershell
function Add-Extension
{
    param ([string]$Name,[string]$Extension = "txt")
    $name = $name + "." + $extension
    $name

    <#
        .SYNOPSIS
        Adds a file name extension to a supplied name.

        .DESCRIPTION
        Adds a file name extension to a supplied name.
        Takes any strings for the file name or extension.

        .PARAMETER Name
        Specifies the file name.

        .PARAMETER Extension
        Specifies the extension. "Txt" is the default.

        .INPUTS
        None. You cannot pipe objects to Add-Extension.

        .OUTPUTS
        System.String. Add-Extension returns a string with the extension or file name.

        .EXAMPLE
        C:\PS> extension -name "File"
        File.txt

        .EXAMPLE
        C:\PS> extension -name "File" -extension "doc"
        File.doc

        .EXAMPLE
        C:\PS> extension "File" "doc"
        File.doc

        .LINK
        Online version: http://www.fabrikam.com/extension.html

        .LINK
        Set-Item
    #>
}
```

Die folgende Ausgabe zeigt die Ergebnisse eines `Get-Help` Befehls, der die Hilfe für die `Add-Extension` Funktion anzeigt.

```powershell
C:\PS> get-help add-extension -full
```

```Output
        NAME
            Add-Extension

        SYNOPSIS
            Adds a file name extension to a supplied name.

        SYNTAX
            Add-Extension [[-Name] <String>] [[-Extension] <String>] [<CommonParameters>]

        DESCRIPTION
            Adds a file name extension to a supplied name. Takes any strings for the file name or extension.

        PARAMETERS
           -Name
               Specifies the file name.

               Required?                    false
               Position?                    0
               Default value
               Accept pipeline input?       false
               Accept wildcard characters?

           -Extension
               Specifies the extension. "Txt" is the default.

               Required?                    false
               Position?                    1
               Default value
               Accept pipeline input?       false
               Accept wildcard characters?

            <CommonParameters>
               This cmdlet supports the common parameters: -Verbose, -Debug,
               -ErrorAction, -ErrorVariable, -WarningAction, -WarningVariable,
               -OutBuffer and -OutVariable. For more information, type
               "get-help about_commonparameters".

        INPUTS
            None. You cannot pipe objects to Add-Extension.

        OUTPUTS
            System.String. Add-Extension returns a string with the extension or file name.

            -------------------------- EXAMPLE 1 --------------------------

            C:\PS> extension -name "File"
            File.txt

            -------------------------- EXAMPLE 2 --------------------------

            C:\PS> extension -name "File" -extension "doc"
            File.doc

            -------------------------- EXAMPLE 3 --------------------------

            C:\PS> extension "File" "doc"
            File.doc

        RELATED LINKS
            Online version: http://www.fabrikam.com/extension.html
            Set-Item
```

## <a name="example-2-comment-based-help-for-a-script"></a>Beispiel 2: Kommentar basierte Hilfe für ein Skript

Die folgende Beispiel Funktion enthält eine Kommentar basierte Hilfe.

Beachten Sie die leeren Zeilen zwischen dem schließenden **#>** und der- `Param` Anweisung. In einem Skript, das keine `Param` -Anweisung enthält, müssen mindestens zwei Leerzeilen zwischen dem letzten Kommentar im Hilfethema und der ersten Funktionsdeklaration vorhanden sein. Ohne diese leeren Zeilen wird das `Get-Help` Hilfethema anstelle des Skripts mit der Funktion verknüpft.

```powershell
<#
  .SYNOPSIS
  Performs monthly data updates.

  .DESCRIPTION
  The Update-Month.ps1 script updates the registry with new data generated
  during the past month and generates a report.

  .PARAMETER InputPath
  Specifies the path to the CSV-based input file.

  .PARAMETER OutputPath
  Specifies the name and path for the CSV-based output file. By default,
  MonthlyUpdates.ps1 generates a name from the date and time it runs, and
  saves the output in the local directory.

  .INPUTS
  None. You cannot pipe objects to Update-Month.ps1.

  .OUTPUTS
  None. Update-Month.ps1 does not generate any output.

  .EXAMPLE
  C:\PS> .\Update-Month.ps1

  .EXAMPLE
  C:\PS> .\Update-Month.ps1 -inputpath C:\Data\January.csv

  .EXAMPLE
  C:\PS> .\Update-Month.ps1 -inputpath C:\Data\January.csv -outputPath C:\Reports\2009\January.csv
#>

param ([string]$InputPath, [string]$OutPutPath)

function Get-Data { }
```

Der folgende Befehl ruft die Skript Hilfe ab. Da sich das Skript nicht in einem Verzeichnis befindet, das in der PATH-Umgebungsvariablen aufgelistet ist, `Get-Help` muss der Befehl, mit dem die Skript Hilfe abgerufen wird, den Skript Pfad angeben.

```powershell
C:\PS> get-help c:\ps-test\update-month.ps1 -full
```

```Output
            NAME
                C:\ps-test\Update-Month.ps1

            SYNOPSIS
                Performs monthly data updates.

            SYNTAX
                C:\ps-test\Update-Month.ps1 [-InputPath] <String> [[-OutputPath]
                <String>] [<CommonParameters>]

            DESCRIPTION
                The Update-Month.ps1 script updates the registry with new data
                generated during the past month and generates a report.

            PARAMETERS
               -InputPath
                   Specifies the path to the CSV-based input file.

                   Required?                    true
                   Position?                    0
                   Default value
                   Accept pipeline input?       false
                   Accept wildcard characters?

               -OutputPath
                   Specifies the name and path for the CSV-based output file. By
                   default, MonthlyUpdates.ps1 generates a name from the date
                   and time it runs, and saves the output in the local directory.

                   Required?                    false
                   Position?                    1
                   Default value
                   Accept pipeline input?       false
                   Accept wildcard characters?

               <CommonParameters>
                   This cmdlet supports the common parameters: -Verbose, -Debug,
                   -ErrorAction, -ErrorVariable, -WarningAction, -WarningVariable,
                   -OutBuffer and -OutVariable. For more information, type,
                   "get-help about_commonparameters".

            INPUTS
                   None. You cannot pipe objects to Update-Month.ps1.

            OUTPUTS
                   None. Update-Month.ps1 does not generate any output.

            -------------------------- EXAMPLE 1 --------------------------

            C:\PS> .\Update-Month.ps1

            -------------------------- EXAMPLE 2 --------------------------

            C:\PS> .\Update-Month.ps1 -inputpath C:\Data\January.csv

            -------------------------- EXAMPLE 3 --------------------------

            C:\PS> .\Update-Month.ps1 -inputpath C:\Data\January.csv -outputPath
            C:\Reports\2009\January.csv

            RELATED LINKS
```

## <a name="example-3-parameter-descriptions-in-a-param-statement"></a>Beispiel 3: Parameter Beschreibungen in einer Param-Anweisung

Dieses Beispiel zeigt, wie Parameter Beschreibungen in die- `Param` Anweisung einer Funktion oder eines Skripts eingefügt werden. Dieses Format ist besonders nützlich, wenn die Parameter Beschreibungen kurz sind.

```powershell
function Add-Extension
{
    param
    (
        [string]
        # Specifies the file name.
        $name,

        [string]
        # Specifies the file name extension. "Txt" is the default.
        $extension = "txt"
    )
    $name = $name + "." + $extension
    $name

    <#
        .SYNOPSIS
        Adds a file name extension to a supplied name.
...
    #>
```

Die Ergebnisse sind identisch mit den Ergebnissen für Beispiel 1. `Get-Help`interpretiert die Parameter Beschreibungen so, als hätten Sie das- `.Parameter` Schlüsselwort begleitet.

## <a name="example-4--redirecting-to-an-xml-file"></a>Beispiel 4: Umleiten an eine XML-Datei

Sie können XML-basierte Hilfe Themen für Funktionen und Skripts schreiben. Obwohl die Kommentar basierte Hilfe einfacher implementiert werden kann, ist die XML-basierte Hilfe erforderlich, wenn Sie die Hilfe Inhalte genauer steuern möchten oder wenn Sie Hilfe Themen in mehrere Sprachen übersetzen möchten. Das folgende Beispiel zeigt die ersten Zeilen des `Update-Month.ps1` Skripts. Das Skript verwendet das- `.ExternalHelp` Schlüsselwort, um den Pfad zu einem XML-basierten Hilfethema für das Skript anzugeben.

```powershell
#  .ExternalHelp C:\MyScripts\Update-Month-Help.xml

    param ([string]$InputPath, [string]$OutPutPath)

    function Get-Data { }
```

Das folgende Beispiel zeigt die Verwendung des- `.ExternalHelp` Schlüssel Worts in einer-Funktion.

```powershell
function Add-Extension
{
    param ([string] $name, [string]$extension = "txt")
    $name = $name + "." + $extension
    $name

    # .ExternalHelp C:\ps-test\Add-Extension.xml
}
```

## <a name="example-5--redirecting-to-a-different-help-topic"></a>Beispiel 5: Umleiten an ein anderes Hilfethema

Der folgende Code ist ein Auszug aus dem Anfang der integrierten `Help` Funktion in PowerShell, der jeweils einen Bildschirm mit Hilfe Text anzeigt. Da im Hilfethema für das Cmdlet "Get-Help" die Hilfe Funktion beschrieben wird, verwendet die Hilfe Funktion die `.ForwardHelpTargetName` `.ForwardHelpCategory` Schlüsselwörter und, um den Benutzer zum Hilfethema Get-Help Cmdlet umzuleiten.

```powershell
function help
{

    <#
      .FORWARDHELPTARGETNAME Get-Help
      .FORWARDHELPCATEGORY Cmdlet
    #>
    [CmdletBinding(DefaultParameterSetName='AllUsersView')]
    param(
            [Parameter(Position=0, ValueFromPipelineByPropertyName=$true)]
            [System.String]
            ${Name},
    ...
```

Der folgende Befehl verwendet diese Funktion. Wenn ein Benutzer einen `Get-Help` Befehl für die Funktion eingibt `Help` , `Get-Help` zeigt das Hilfethema für das `Get-Help` Cmdlet an.

```powershell
C:\PS> get-help help
```

```Output
            NAME
                Get-Help

            SYNOPSIS
                Displays information about Windows PowerShell cmdlets and concepts.
            ...
```
