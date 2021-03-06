---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 12/08/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/convertto-csv?view=powershell-7.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: ConvertTo-Csv
ms.openlocfilehash: 7ad8dc837bd843c2df48587ad809d9f65a4cf8a7
ms.sourcegitcommit: 560a9f3c3148acab4655e91e8b07745ab74d5d26
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/09/2020
ms.locfileid: "96913218"
---
# ConvertTo-Csv

## ZUSAMMENFASSUNG
Konvertiert .NET-Objekte in eine Reihe von CSV-Zeichen folgen (Zeichen getrennte Werte).

## SYNTAX

### Trennzeichen (Standard)

```
ConvertTo-Csv [-InputObject] <PSObject> [[-Delimiter] <Char>] [-IncludeTypeInformation]
 [-NoTypeInformation] [-QuoteFields <String[]>] [-UseQuotes <QuoteKind>] [<CommonParameters>]
```

### UseCulture

```
ConvertTo-Csv [-InputObject] <PSObject> [-UseCulture] [-IncludeTypeInformation] [-NoTypeInformation]
 [-QuoteFields <String[]>] [-UseQuotes <QuoteKind>] [<CommonParameters>]
```

## DESCRIPTION

Das- `ConvertTo-CSV` Cmdlet gibt eine Reihe von CSV-Zeichen folgen zurück, die die von Ihnen gesendeten Objekte darstellen. Sie können dann mit dem `ConvertFrom-Csv` Cmdlet Objekte aus den CSV-Zeichen folgen neu erstellen. Die aus CSV konvertierten Objekte sind Zeichen folgen Werte der ursprünglichen Objekte, die Eigenschaftswerte und keine Methoden enthalten.

Sie können das `Export-Csv` Cmdlet verwenden, um Objekte in CSV-Zeichen folgen zu konvertieren. `Export-CSV` ähnelt `ConvertTo-CSV` , mit der Ausnahme, dass die CSV-Zeichen folgen in einer Datei gespeichert werden.

Das- `ConvertTo-CSV` Cmdlet verfügt über Parameter, um ein anderes Trennzeichen als ein Komma anzugeben, oder die aktuelle Kultur als Trennzeichen zu verwenden.

## BEISPIELE

### Beispiel 1: Konvertieren eines Objekts in ein CSV

In diesem Beispiel wird ein **Prozess** Objekt in eine CSV-Zeichenfolge konvertiert.

```powershell
Get-Process -Name pwsh | ConvertTo-Csv -NoTypeInformation
```

```Output
"Name","SI","Handles","VM","WS","PM","NPM","Path","Parent","Company","CPU","FileVersion", ...
"pwsh","8","950","2204001161216","100925440","59686912","67104", ...
```

Das `Get-Process` -Cmdlet ruft das **Process** -Objekt ab und verwendet den **Name** -Parameter, um den PowerShell-Prozess anzugeben. Das Prozess Objekt wird in der Pipeline an das `ConvertTo-CSV` Cmdlet gesendet. Das- `ConvertTo-CSV` Cmdlet konvertiert das Objekt in CSV-Zeichen folgen. Der **notypeinformation** -Parameter entfernt den **#Type** -Informations Header aus der CSV-Ausgabe und ist in PowerShell 6 nicht erforderlich.

### Beispiel 2: Konvertieren eines DateTime-Objekts in eine CSV-Datei

In diesem Beispiel wird ein **DateTime** -Objekt in eine CSV-Zeichenfolge konvertiert.

```powershell
$Date = Get-Date
ConvertTo-Csv -InputObject $Date -Delimiter ';' -NoTypeInformation
```

```Output
"DisplayHint";"DateTime";"Date";"Day";"DayOfWeek";"DayOfYear";"Hour";"Kind";"Millisecond";"Minute";"Month";"Second";"Ticks";"TimeOfDay";"Year"
"DateTime";"Friday, January 4, 2019 14:40:51";"1/4/2019 00:00:00";"4";"Friday";"4";"14";"Local";"711";"40";"1";"51";"636822096517114991";"14:40:51.7114991";"2019"
```

`Get-Date`Mit dem-Cmdlet wird das **DateTime** -Objekt abgerufen und in der `$Date` Variablen gespeichert. Mit dem- `ConvertTo-Csv` Cmdlet wird das **DateTime** -Objekt in Zeichen folgen konvertiert. Der **Inputobject** -Parameter verwendet das **DateTime** -Objekt, das in der Variablen gespeichert ist `$Date` . Mit dem **Delimiter** -Parameter wird ein Semikolon zum Trennen der Zeichen folgen Werte angegeben. Der **notypeinformation** -Parameter entfernt den **#Type** -Informations Header aus der CSV-Ausgabe und ist in PowerShell 6 nicht erforderlich.

### Beispiel 3: Konvertieren des PowerShell-Ereignis Protokolls in eine CSV-Datei

In diesem Beispiel wird das Windows-Ereignisprotokoll für PowerShell in eine Reihe von CSV-Zeichen folgen konvertiert.

```powershell
(Get-Culture).TextInfo.ListSeparator
Get-WinEvent -LogName 'PowerShellCore/Operational' | ConvertTo-Csv -UseCulture -NoTypeInformation
```

```Output
,
"Message","Id","Version","Qualifiers","Level","Task","Opcode","Keywords","RecordId", ...
"Error Message = System error""4100","1",,"3","106","19","0","31716","PowerShellCore", ...
```

Das `Get-Culture` Cmdlet verwendet die genten Eigenschaften **TextInfo** und **ListSeparator** und zeigt das Standard Listen Trennzeichen der aktuellen Kultur an. `Get-WinEvent`Mit dem-Cmdlet werden die Ereignisprotokoll Objekte abgerufen, und der **logName** -Parameter wird verwendet, um den Namen der Protokolldatei anzugeben. Die Ereignisprotokoll Objekte werden über die Pipeline an das `ConvertTo-Csv` Cmdlet gesendet. Mit dem- `ConvertTo-Csv` Cmdlet werden die Ereignisprotokoll Objekte in eine Reihe von CSV-Zeichen folgen konvertiert. Der **useculture** -Parameter verwendet das Standard Listen Trennzeichen der aktuellen Kultur als Trennzeichen. Der **notypeinformation** -Parameter entfernt den **#Type** -Informations Header aus der CSV-Ausgabe und ist in PowerShell 6 nicht erforderlich.

### Beispiel 4: Konvertieren in CSV mit Anführungszeichen um zwei Spalten

In diesem Beispiel wird ein **DateTime** -Objekt in eine CSV-Zeichenfolge konvertiert.

```powershell
Get-Date | ConvertTo-Csv -QuoteFields "DateTime","Date"
```

```Output
DisplayHint,"DateTime","Date",Day,DayOfWeek,DayOfYear,Hour,Kind,Millisecond,Minute,Month,Second,Ticks,TimeOfDay,Year
DateTime,"Thursday, August 22, 2019 11:27:34 AM","8/22/2019 12:00:00 AM",22,Thursday,234,11,Local,569,27,8,34,637020700545699784,11:27:34.5699784,2019
```

### Beispiel 4: Konvertieren in CSV nur bei Bedarf mit Anführungszeichen

In diesem Beispiel wird ein **DateTime** -Objekt in eine CSV-Zeichenfolge konvertiert.

```powershell
Get-Date | ConvertTo-Csv -UseQuotes AsNeeded
```

```Output
DisplayHint,DateTime,Date,Day,DayOfWeek,DayOfYear,Hour,Kind,Millisecond,Minute,Month,Second,Ticks,TimeOfDay,Year
DateTime,"Thursday, August 22, 2019 11:31:00 AM",8/22/2019 12:00:00 AM,22,Thursday,234,11,Local,713,31,8,0,637020702607132640,11:31:00.7132640,2019
```

## PARAMETERS

### -Delimiter

Gibt das Trennzeichen zum Trennen der Eigenschaftswerte in CSV-Zeichen folgen an. Der Standardwert ist ein Komma ( `,` ). Geben Sie ein Zeichen ein, z. b. einen Doppelpunkt ( `:` ). Um ein Semikolon ( `;` ) anzugeben, schließen Sie es in einfache Anführungszeichen ein.

```yaml
Type: System.Char
Parameter Sets: Delimiter
Aliases:

Required: False
Position: 1
Default value: comma (,)
Accept pipeline input: False
Accept wildcard characters: False
```

### -Includecotypeinformation

Wenn dieser Parameter verwendet wird, enthält die erste Zeile der Ausgabe **#Type** , gefolgt vom voll qualifizierten Namen des Objekt Typs. #Type z. b. **System. Diagnostics. Process**.

Dieser Parameter wurde in PowerShell 6,0 eingeführt.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: ITI

Required: False
Position: Named
Default value: #TYPE <Object>
Accept pipeline input: False
Accept wildcard characters: False
```

### -InputObject

Gibt die Objekte an, die in CSV-Zeichen folgen konvertiert werden. Geben Sie eine Variable ein, die die Objekte enthält, oder geben Sie einen Befehl oder einen Ausdruck ein, durch den die Objekte abgerufen werden. Sie können Objekte auch über die Pipeline an übergeben `ConvertTo-CSV` .

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### -Notypeinformation

Entfernt den **#Type** Informations Header aus der Ausgabe. Dieser Parameter wurde in PowerShell 6,0 zum Standard und ist aus Gründen der Abwärtskompatibilität eingeschlossen.

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: NTI

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Useculture

Verwendet das Listen Trennzeichen für die aktuelle Kultur als Element Trennzeichen. Um das Listen Trennzeichen für eine Kultur zu suchen, verwenden Sie den folgenden Befehl: `(Get-Culture).TextInfo.ListSeparator` .

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: UseCulture
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Quotefields

Gibt die Namen der Spalten an, die in Anführungszeichen eingeschlossen werden sollen. Wenn dieser Parameter verwendet wird, werden nur die angegebenen Spalten in Anführungszeichen eingeschlossen. Dieser Parameter wurde in PowerShell 7,0 hinzugefügt.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: QF

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Usequotes

Gibt an, wann Anführungszeichen in den CSV-Dateien verwendet werden. Mögliche Werte:

- Niemals etwas angeben
- Alles immer angeben (Standardverhalten)
- Asbedarf-nur Anführungszeichen Felder, die ein Trennzeichen enthalten

Dieser Parameter wurde in PowerShell 7,0 hinzugefügt.

```yaml
Type: Microsoft.PowerShell.Commands.BaseCsvWritingCommand+QuoteKind
Parameter Sets: (All)
Aliases: UQ

Required: False
Position: Named
Default value: Always
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters

Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## EINGABEN

### System. Management. Automation. psobject

Sie können jedes beliebige Objekt über die Pipeline übergeben, das über einen Extended Type System (ETS)-Adapter verfügt `ConvertTo-CSV` .

## AUSGABEN

### System.String

Die CSV-Ausgabe wird als Auflistung von Zeichenfolgen zurückgegeben.

## HINWEISE

Im CSV-Format wird jedes Objekt durch eine durch Trennzeichen getrennte Liste seiner Eigenschaftswerte dargestellt. Die Eigenschaftswerte werden mithilfe der Methode "$ **String ()** " des Objekts in Zeichen folgen konvertiert. Die Zeichen folgen werden durch den Namen des Eigenschafts Werts dargestellt. `ConvertTo-CSV` exportiert nicht die Methoden des Objekts.

Die CSV-Zeichen folgen werden wie folgt ausgegeben:

- Wenn **includetypeinformation** verwendet wird, besteht die erste Zeichenfolge aus **#Type** gefolgt vom voll qualifizierten Namen des Objekt Typs. #Type z. b. **System. Diagnostics. Process**.
- Wenn **include TypeInformation** nicht verwendet wird, enthält die erste Zeichenfolge die Spaltenüberschriften. Die Header enthalten die Eigenschaftsnamen des ersten Objekts als durch Trennzeichen getrennte Liste.
- Die übrigen Zeichen folgen enthalten durch Trennzeichen getrennte Listen der Eigenschaftswerte jedes Objekts.

Ab PowerShell 6,0 ist das Standardverhalten von `ConvertTo-CSV` , wenn die **#Type** Informationen in das CSV nicht eingeschlossen werden und **notypeinformation** impliziert ist. **Includetypeinformation** kann verwendet werden, um die **#Type** Informationen einzuschließen und das Standardverhalten von `ConvertTo-CSV` vor PowerShell 6,0 zu emulieren.

Wenn Sie mehrere Objekte an senden `ConvertTo-CSV` , `ConvertTo-CSV` ordnet die Zeichen folgen auf der Grundlage der Eigenschaften des ersten von Ihnen gesendeten Objekts zu. Wenn die übrigen Objekte nicht über eine der angegebenen Eigenschaften verfügen, ist der Eigenschafts Wert dieses Objekts NULL, was durch zwei aufeinander folgende Kommas dargestellt wird. Wenn die übrigen Objekte zusätzliche Eigenschaften aufweisen, werden diese Eigenschaftswerte ignoriert.

## VERWANDTE LINKS

[ConvertFrom-Csv](ConvertFrom-Csv.md)

[Export-CSV](Export-Csv.md)

[Import-Csv](Import-Csv.md)
