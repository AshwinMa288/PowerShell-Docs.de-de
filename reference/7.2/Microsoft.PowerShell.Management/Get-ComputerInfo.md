---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/get-computerinfo?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-ComputerInfo
ms.openlocfilehash: abc820bd6f8f5c8cd8c6301aacee268c82161d7e
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99601128"
---
# Get-ComputerInfo

## ZUSAMMENFASSUNG
Ruft ein konsolidiertes Objekt der System-und Betriebssystem Eigenschaften ab.

## SYNTAX

```
Get-ComputerInfo [[-Property] <String[]>] [<CommonParameters>]
```

## DESCRIPTION

`Get-ComputerInfo`Mit dem-Cmdlet wird ein konsolidiertes Objekt der System-und Betriebssystem Eigenschaften abgerufen.
Dieses Cmdlet wurde in Windows PowerShell 5,1 eingeführt.

## BEISPIELE

### Beispiel 1: alle Computer Eigenschaften

```powershell
Get-ComputerInfo
```

Mit diesem Befehl werden alle System-und Betriebssystem Eigenschaften vom Computer abgerufen.

### Beispiel 2: alle Computerbetriebssystem-Eigenschaften

```powershell
Get-ComputerInfo -Property "os*"
```

Mit diesem Befehl werden alle Betriebssystem Eigenschaften vom Computer abgerufen.

## PARAMETERS

### -Eigenschaft

Gibt die Computer Eigenschaften, die dieses Cmdlet anzeigt, als Zeichen folgen Array an.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### CommonParameters

Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).

## EINGABEN

### System.String[]

## AUSGABEN

### Microsoft. PowerShell. Management. ComputerInfo

## HINWEISE

Dieses Cmdlet ist nur auf Windows-Plattformen verfügbar.

## VERWANDTE LINKS
