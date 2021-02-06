---
external help file: PSModule-help.xml
Locale: en-US
Module Name: PowerShellGet
ms.date: 03/27/2020
online version: https://docs.microsoft.com/powershell/module/powershellget/publish-script?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Publish-Script
ms.openlocfilehash: 344a789c9daced51b549d562b7fd74677fe403dc
ms.sourcegitcommit: 22c93550c87af30c4895fcb9e9dd65e30d60ada0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/19/2020
ms.locfileid: "99599426"
---
# <span data-ttu-id="da5ec-102">Publish-Script</span><span class="sxs-lookup"><span data-stu-id="da5ec-102">Publish-Script</span></span>

## <span data-ttu-id="da5ec-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="da5ec-103">SYNOPSIS</span></span>
<span data-ttu-id="da5ec-104">Veröffentlicht ein Skript.</span><span class="sxs-lookup"><span data-stu-id="da5ec-104">Publishes a script.</span></span>

## <span data-ttu-id="da5ec-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="da5ec-105">SYNTAX</span></span>

### <span data-ttu-id="da5ec-106">Pathparameterset (Standard)</span><span class="sxs-lookup"><span data-stu-id="da5ec-106">PathParameterSet (Default)</span></span>

```
Publish-Script -Path <String> [-NuGetApiKey <String>] [-Repository <String>]
 [-Credential <PSCredential>] [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="da5ec-107">Literalpathparameterset</span><span class="sxs-lookup"><span data-stu-id="da5ec-107">LiteralPathParameterSet</span></span>

```
Publish-Script -LiteralPath <String> [-NuGetApiKey <String>] [-Repository <String>]
 [-Credential <PSCredential>] [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="da5ec-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="da5ec-108">DESCRIPTION</span></span>

<span data-ttu-id="da5ec-109">`Publish-Script`Mit dem-Cmdlet wird das angegebene Skript im Onlinekatalog veröffentlicht.</span><span class="sxs-lookup"><span data-stu-id="da5ec-109">The `Publish-Script` cmdlet publishes the specified script to the online gallery.</span></span>

## <span data-ttu-id="da5ec-110">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="da5ec-110">EXAMPLES</span></span>

### <span data-ttu-id="da5ec-111">Beispiel 1: Erstellen einer Skriptdatei, Hinzufügen von Inhalt zu dieser und veröffentlichen</span><span class="sxs-lookup"><span data-stu-id="da5ec-111">Example 1: Create a script file, add content to it, and publish it</span></span>

<span data-ttu-id="da5ec-112">Das- `New-ScriptFileInfo` Cmdlet erstellt eine Skriptdatei mit dem Namen `Demo-Script.ps1` .</span><span class="sxs-lookup"><span data-stu-id="da5ec-112">The `New-ScriptFileInfo` cmdlet creates a script file named `Demo-Script.ps1`.</span></span> <span data-ttu-id="da5ec-113">`Get-Content` zeigt den Inhalt von an `Demo-Script.ps1` .</span><span class="sxs-lookup"><span data-stu-id="da5ec-113">`Get-Content` displays the content of `Demo-Script.ps1`.</span></span> <span data-ttu-id="da5ec-114">`Add-Content`Mit dem-Cmdlet werden eine Funktion und ein Workflow zu hinzugefügt `Demo-Script.ps1` .</span><span class="sxs-lookup"><span data-stu-id="da5ec-114">The `Add-Content` cmdlet adds a function and a workflow to `Demo-Script.ps1`.</span></span>

```powershell
$newScriptInfo = @{
  Path = 'D:\ScriptSharingDemo\Demo-Script.ps1'
  Version = '1.0'
  Author = 'author@contoso.com'
  Description = "my test script file description goes here"
}
New-ScriptFileInfo @newScriptInfo
Get-Content -Path $newScriptInfo.Path
```

```Output
<#PSScriptInfo

.VERSION 1.0

.AUTHOR pattif@microsoft.com

.COMPANYNAME

.COPYRIGHT

.TAGS

.LICENSEURI

.PROJECTURI

.ICONURI

.EXTERNALMODULEDEPENDENCIES

.REQUIREDSCRIPTS

.EXTERNALSCRIPTDEPENDENCIES

.RELEASENOTES
#>

<#
.DESCRIPTION
 my test script file description goes here
#>
Param()
```

```powershell
Add-Content -Path D:\ScriptSharingDemo\Demo-Script.ps1 -Value @"

Function Demo-ScriptFunction { 'Demo-ScriptFunction' }

Workflow Demo-ScriptWorkflow { 'Demo-ScriptWorkflow' }

Demo-ScriptFunction
Demo-ScriptWorkflow
"@
Test-ScriptFileInfo -Path D:\ScriptSharingDemo\Demo-Script.ps1
```

```Output
Version    Name                 Author                   Description
-------    ----                 ------                   -----------
1.0        Demo-Script          author@contoso.com       my test script file description goes here
```

```powershell
Publish-Script -Path D:\ScriptSharingDemo\Demo-Script.ps1 -Repository LocalRepo1
Find-Script -Repository LocalRepo1 -Name "Demo-Script"
```

```Output
Version    Name                 Type       Repository    Description
-------    ----                 ----       ----------    -----------
1.0        Demo-Script          Script     LocalRepo1    my test script file description goes here
```

<span data-ttu-id="da5ec-115">Das- `Test-ScriptFileInfo` Cmdlet überprüft `Demo-Script.ps1` .</span><span class="sxs-lookup"><span data-stu-id="da5ec-115">The `Test-ScriptFileInfo` cmdlet validates `Demo-Script.ps1`.</span></span> <span data-ttu-id="da5ec-116">Das- `Publish-Script` Cmdlet veröffentlicht das Skript im **LocalRepo1** -Repository.</span><span class="sxs-lookup"><span data-stu-id="da5ec-116">The `Publish-Script` cmdlet publishes the script to the **LocalRepo1** repository.</span></span> <span data-ttu-id="da5ec-117">Die letzte Collection</span><span class="sxs-lookup"><span data-stu-id="da5ec-117">Finally.</span></span> <span data-ttu-id="da5ec-118">`Find-Script` wird verwendet, um `Demo-Script.ps1` im **LocalRepo1** -Repository nach zu suchen.</span><span class="sxs-lookup"><span data-stu-id="da5ec-118">`Find-Script` is used to search for `Demo-Script.ps1` in the **LocalRepo1** repository.</span></span>

## <span data-ttu-id="da5ec-119">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="da5ec-119">PARAMETERS</span></span>

### <span data-ttu-id="da5ec-120">-Confirm</span><span class="sxs-lookup"><span data-stu-id="da5ec-120">-Confirm</span></span>

<span data-ttu-id="da5ec-121">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="da5ec-121">Prompts you for confirmation before running the cmdlet.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="da5ec-122">-Credential</span><span class="sxs-lookup"><span data-stu-id="da5ec-122">-Credential</span></span>

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

### <span data-ttu-id="da5ec-123">-Force</span><span class="sxs-lookup"><span data-stu-id="da5ec-123">-Force</span></span>

<span data-ttu-id="da5ec-124">Erzwingt die Ausführung des Befehls ohne Aufforderung zur Bestätigung durch den Benutzer.</span><span class="sxs-lookup"><span data-stu-id="da5ec-124">Forces the command to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="da5ec-125">-Literalpath</span><span class="sxs-lookup"><span data-stu-id="da5ec-125">-LiteralPath</span></span>

<span data-ttu-id="da5ec-126">Gibt einen Pfad zu einem oder mehreren Speicherorten an.</span><span class="sxs-lookup"><span data-stu-id="da5ec-126">Specifies a path to one or more locations.</span></span> <span data-ttu-id="da5ec-127">Im Gegensatz zum **path** -Parameter wird der Wert des **literalpath** -Parameters genau so verwendet, wie er eingegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="da5ec-127">Unlike the **Path** parameter, the value of the **LiteralPath** parameter is used exactly as entered.</span></span> <span data-ttu-id="da5ec-128">Es werden keine Zeichen als Platzhalter interpretiert.</span><span class="sxs-lookup"><span data-stu-id="da5ec-128">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="da5ec-129">Wenn der Pfad Escapezeichen enthält, schließen Sie Sie in einfache Anführungszeichen ein.</span><span class="sxs-lookup"><span data-stu-id="da5ec-129">If the path includes escape characters, enclose them in single quotation marks.</span></span> <span data-ttu-id="da5ec-130">Einfache Anführungszeichen veranlassen Windows PowerShell, Zeichen nicht als Escapesequenzen zu interpretieren.</span><span class="sxs-lookup"><span data-stu-id="da5ec-130">Single quotation marks tell Windows PowerShell not to interpret any characters as escape sequences.</span></span>

```yaml
Type: System.String
Parameter Sets: LiteralPathParameterSet
Aliases: PSPath

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="da5ec-131">-Nugetapikey</span><span class="sxs-lookup"><span data-stu-id="da5ec-131">-NuGetApiKey</span></span>

<span data-ttu-id="da5ec-132">Gibt den API-Schlüssel an, den Sie zum Veröffentlichen eines Skripts im Onlinekatalog verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="da5ec-132">Specifies the API key that you want to use to publish a script to the online gallery.</span></span> <span data-ttu-id="da5ec-133">Der API-Schlüssel ist Teil Ihres Profils im Onlinekatalog.</span><span class="sxs-lookup"><span data-stu-id="da5ec-133">The API key is part of your profile in the online gallery.</span></span> <span data-ttu-id="da5ec-134">Weitere Informationen finden Sie unter [Verwalten von API-Schlüsseln](/powershell/scripting/gallery/how-to/managing-profile/creating-apikeys).</span><span class="sxs-lookup"><span data-stu-id="da5ec-134">For more information see [Managing API keys](/powershell/scripting/gallery/how-to/managing-profile/creating-apikeys).</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="da5ec-135">-Path</span><span class="sxs-lookup"><span data-stu-id="da5ec-135">-Path</span></span>

<span data-ttu-id="da5ec-136">Gibt einen Pfad zu einem oder mehreren Speicherorten an.</span><span class="sxs-lookup"><span data-stu-id="da5ec-136">Specifies a path to one or more locations.</span></span> <span data-ttu-id="da5ec-137">Platzhalter sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="da5ec-137">Wildcards are permitted.</span></span> <span data-ttu-id="da5ec-138">Der Standardspeicherort ist das aktuelle Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="da5ec-138">The default location is the current directory.</span></span>

```yaml
Type: System.String
Parameter Sets: PathParameterSet
Aliases:

Required: True
Position: Named
Default value: <Current location>
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="da5ec-139">-Repository</span><span class="sxs-lookup"><span data-stu-id="da5ec-139">-Repository</span></span>

<span data-ttu-id="da5ec-140">Gibt den anzeigen Amen eines Repository an, das durch Ausführen von registriert wurde `Register-PSRepository` .</span><span class="sxs-lookup"><span data-stu-id="da5ec-140">Specifies the friendly name of a repository that has been registered by running `Register-PSRepository`.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="da5ec-141">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="da5ec-141">-WhatIf</span></span>

<span data-ttu-id="da5ec-142">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="da5ec-142">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="da5ec-143">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="da5ec-143">The cmdlet is not run.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="da5ec-144">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="da5ec-144">CommonParameters</span></span>

<span data-ttu-id="da5ec-145">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="da5ec-145">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="da5ec-146">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="da5ec-146">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="da5ec-147">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="da5ec-147">INPUTS</span></span>

### <span data-ttu-id="da5ec-148">System.String</span><span class="sxs-lookup"><span data-stu-id="da5ec-148">System.String</span></span>

### <span data-ttu-id="da5ec-149">System. Management. Automation. PSCredential</span><span class="sxs-lookup"><span data-stu-id="da5ec-149">System.Management.Automation.PSCredential</span></span>

## <span data-ttu-id="da5ec-150">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="da5ec-150">OUTPUTS</span></span>

### <span data-ttu-id="da5ec-151">System.Object</span><span class="sxs-lookup"><span data-stu-id="da5ec-151">System.Object</span></span>

## <span data-ttu-id="da5ec-152">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="da5ec-152">NOTES</span></span>

> [!IMPORTANT]
> <span data-ttu-id="da5ec-153">Ab April 2020 unterstützt der PowerShell-Katalog die TLS-Versionen (Transport Layer Security) 1.0 und 1.1 nicht mehr.</span><span class="sxs-lookup"><span data-stu-id="da5ec-153">As of April 2020, the PowerShell Gallery no longer supports Transport Layer Security (TLS) versions 1.0 and 1.1.</span></span> <span data-ttu-id="da5ec-154">Wenn Sie nicht TLS 1.2 oder höher verwenden, erhalten Sie beim Versuch des Zugriffs auf den PowerShell-Katalog eine Fehlermeldung.</span><span class="sxs-lookup"><span data-stu-id="da5ec-154">If you are not using TLS 1.2 or higher, you will receive an error when trying to access the PowerShell Gallery.</span></span> <span data-ttu-id="da5ec-155">Mit dem folgenden Befehl können Sie sicherstellen, dass Sie TLS 1.2 verwenden:</span><span class="sxs-lookup"><span data-stu-id="da5ec-155">Use the following command to ensure you are using TLS 1.2:</span></span>
>
> `[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12`
>
> <span data-ttu-id="da5ec-156">Weitere Informationen finden Sie im PowerShell-Blog in der [Ankündigung](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/).</span><span class="sxs-lookup"><span data-stu-id="da5ec-156">For more information, see the [announcement](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) in the PowerShell blog.</span></span>

## <span data-ttu-id="da5ec-157">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="da5ec-157">RELATED LINKS</span></span>

[<span data-ttu-id="da5ec-158">Find-Script</span><span class="sxs-lookup"><span data-stu-id="da5ec-158">Find-Script</span></span>](Find-Script.md)

[<span data-ttu-id="da5ec-159">Install-Script</span><span class="sxs-lookup"><span data-stu-id="da5ec-159">Install-Script</span></span>](Install-Script.md)

[<span data-ttu-id="da5ec-160">Publish-Script</span><span class="sxs-lookup"><span data-stu-id="da5ec-160">Publish-Script</span></span>](Publish-Script.md)

[<span data-ttu-id="da5ec-161">Save-Script</span><span class="sxs-lookup"><span data-stu-id="da5ec-161">Save-Script</span></span>](Save-Script.md)

[<span data-ttu-id="da5ec-162">Update-Script</span><span class="sxs-lookup"><span data-stu-id="da5ec-162">Update-Script</span></span>](Update-Script.md)