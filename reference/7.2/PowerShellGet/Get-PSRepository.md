---
external help file: PSModule-help.xml
Locale: en-US
Module Name: PowerShellGet
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/powershellget/get-psrepository?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-PSRepository
ms.openlocfilehash: 66f840d99b107da22b6771e6327ab68d33a1b368
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99601727"
---
# Get-PSRepository

## ZUSAMMENFASSUNG
Ruft PowerShell-Repository ab.

## SYNTAX

```
Get-PSRepository [[-Name] <String[]>] [<CommonParameters>]
```

## DESCRIPTION

Mit dem Cmdlet " **Get-psrepository** " werden PowerShell-moduldepots abgerufen, die für den aktuellen Benutzer registriert sind.

## BEISPIELE

### Beispiel 1: alle modultrepositorys

```
PS C:\> Get-PSRepository
Name                                     SourceLocation                                     OneGetProvider       InstallationPolicy
----                                     --------------                                     --------------       ------------------
PSGallery                                http://go.micro...                                 NuGet                Untrusted
myNuGetSource                            https://myget.c...                                 NuGet                Trusted
```

Mit diesem Befehl werden alle moduldepots abgerufen, die für den aktuellen Benutzer registriert sind.

### Beispiel 2: Get Module Repository by Name

```
PS C:\> Get-PSRepository -Name "*NuGet*"
```

Dieser Befehl ruft alle modultrepositorys ab, deren Namen nuget enthalten.

### Beispiel 3: erhalten eines modulrepository und Formatieren der Ausgabe

```
PS C:\> Get-PSRepository -Name "Local01" | Format-List * -Force
Name                      : local01
SourceLocation            : http://manikb-dev:8765/api/v2/
Trusted                   : True
Registered                : True
InstallationPolicy        : Trusted
PackageManagementProvider : NuGet
PublishLocation           : http://pattif-dev:8765/api/v2/package/
ScriptSourceLocation      : http://pattif-dev:8765/api/v2/artifacts/psscript
ScriptPublishLocation     : http://pattif-dev:8765/api/v2/package/
ProviderOptions           : {}
```

Dieser Befehl ruft das Repository mit dem Namen Local01 ab und verwendet den Pipeline-Operator, um dieses Objekt an das Format-List-Cmdlet zu übergeben.

## PARAMETERS

### -Name

Gibt die Namen der zu erzurufenden Depots an.

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
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

[Register-PSRepository](Register-PSRepository.md)

[Set-PSRepository](Set-PSRepository.md)

[Unregister-PSRepository](Unregister-PSRepository.md)

