---
external help file: PSModule-help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PowerShellGet
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/powershellget/unregister-psrepository?view=powershell-5.1&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Unregister-PSRepository
ms.openlocfilehash: 0d98d7bbb26d5a50542f0e125e912ea6333714c1
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93215180"
---
# Unregister-PSRepository

## ZUSAMMENFASSUNG
Hebt die Registrierung eines Repositorys auf

## SYNTAX

```
Unregister-PSRepository [-Name] <String[]> [<CommonParameters>]
```

## DESCRIPTION

Mit dem- `Unregister-PSRepository` Cmdlet wird die Registrierung eines Repository für den aktuellen Benutzer aufgehoben.

## BEISPIELE

### Beispiel 1: Aufheben der Registrierung eines Repository

In diesem Beispiel wird die Registrierung des Repository mynugetsource aufgehoben.

```powershell
Unregister-PSRepository -Name "myNuGetSource"
```

### Beispiel 2: Aufheben der Registrierung aller Depots

In diesem Beispiel `Get-PSRepository` werden alle registrierten Depots mithilfe des Pipeline-Operators an übergeben, um die `Unregister-PSRepository` Registrierung aufzuheben.

```powershell
Get-PSRepository | Unregister-PSRepository
```

## PARAMETERS

### -Name

Gibt ein Array von Namen der zu entfernenden Depots an.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### CommonParameters

Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## EINGABEN

### System.String[]

## AUSGABEN

### System.Object

## HINWEISE

## VERWANDTE LINKS

[Get-PSRepository](Get-PSRepository.md)

[Register-PSRepository](Register-PSRepository.md)

[Set-PSRepository](Set-PSRepository.md)
