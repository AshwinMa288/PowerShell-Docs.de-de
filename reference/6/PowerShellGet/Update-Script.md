---
external help file: PSModule-help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PowerShellGet
ms.date: 07/09/2019
online version: https://docs.microsoft.com/powershell/module/powershellget/update-script?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Update-Script
ms.openlocfilehash: e57a291abcc50a6bc912a36a6258583a7751a819
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93216503"
---
# <span data-ttu-id="d6270-103">Update-Script</span><span class="sxs-lookup"><span data-stu-id="d6270-103">Update-Script</span></span>

## <span data-ttu-id="d6270-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="d6270-104">SYNOPSIS</span></span>
<span data-ttu-id="d6270-105">Aktualisiert ein Skript.</span><span class="sxs-lookup"><span data-stu-id="d6270-105">Updates a script.</span></span>

## <span data-ttu-id="d6270-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="d6270-106">SYNTAX</span></span>

### <span data-ttu-id="d6270-107">Alle</span><span class="sxs-lookup"><span data-stu-id="d6270-107">All</span></span>

```
Update-Script [[-Name] <String[]>] [-RequiredVersion <String>] [-MaximumVersion <String>]
 [-Proxy <Uri>] [-ProxyCredential <PSCredential>] [-Credential <PSCredential>] [-Force]
 [-AllowPrerelease] [-AcceptLicense] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="d6270-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="d6270-108">DESCRIPTION</span></span>

<span data-ttu-id="d6270-109">Mit dem- `Update-Script` Cmdlet wird ein Skript aktualisiert, das auf dem lokalen Computer installiert ist.</span><span class="sxs-lookup"><span data-stu-id="d6270-109">The `Update-Script` cmdlet updates a script that is installed on the local computer.</span></span> <span data-ttu-id="d6270-110">Das aktualisierte Skript wird aus demselben Repository wie die installierte Version heruntergeladen.</span><span class="sxs-lookup"><span data-stu-id="d6270-110">The updated script is downloaded from the same repository as the installed version.</span></span>

## <span data-ttu-id="d6270-111">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="d6270-111">EXAMPLES</span></span>

### <span data-ttu-id="d6270-112">Beispiel 1: Aktualisieren des angegebenen Skripts</span><span class="sxs-lookup"><span data-stu-id="d6270-112">Example 1: Update the specified script</span></span>

<span data-ttu-id="d6270-113">In diesem Beispiel wird ein installiertes Skript aktualisiert und die aktualisierte Version angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d6270-113">This example updates an installed script and displays the updated version.</span></span>

```powershell
Update-Script -Name UpdateManagement-Template -RequiredVersion 1.1
Get-InstalledScript -Name UpdateManagement-Template
```

```Output
Version   Name                       Repository   Description
-------   ----                       ----------   -----------
1.1       UpdateManagement-Template  PSGallery    This is a template script for Update Management...
```

<span data-ttu-id="d6270-114">`Update-Script` verwendet den **Name** -Parameter, um das zu Aktualisier gende Skript anzugeben.</span><span class="sxs-lookup"><span data-stu-id="d6270-114">`Update-Script` uses the **Name** parameter to specify the script to update.</span></span> <span data-ttu-id="d6270-115">Der Requirements **dversion** -Parameter gibt die Skript Version an.</span><span class="sxs-lookup"><span data-stu-id="d6270-115">The **RequiredVersion** parameter specifies the script version.</span></span> <span data-ttu-id="d6270-116">`Get-InstalledScript` zeigt die aktualisierte Version des Skripts an.</span><span class="sxs-lookup"><span data-stu-id="d6270-116">`Get-InstalledScript` displays the updated version of the script.</span></span>

## <span data-ttu-id="d6270-117">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="d6270-117">PARAMETERS</span></span>

### <span data-ttu-id="d6270-118">-AcceptLicense</span><span class="sxs-lookup"><span data-stu-id="d6270-118">-AcceptLicense</span></span>

<span data-ttu-id="d6270-119">Akzeptieren Sie den Lizenzvertrag während der Installation automatisch, wenn dies für das Paket erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="d6270-119">Automatically accept the license agreement during installation if the package requires it.</span></span>

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

### <span data-ttu-id="d6270-120">-Allowprerelease</span><span class="sxs-lookup"><span data-stu-id="d6270-120">-AllowPrerelease</span></span>

<span data-ttu-id="d6270-121">Ermöglicht das Aktualisieren eines Skripts mit dem neueren Skript, das als Vorabversion markiert ist.</span><span class="sxs-lookup"><span data-stu-id="d6270-121">Allows you to update a script with the newer script marked as a prerelease.</span></span>

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

### <span data-ttu-id="d6270-122">-Confirm</span><span class="sxs-lookup"><span data-stu-id="d6270-122">-Confirm</span></span>

<span data-ttu-id="d6270-123">Sie werden zur Bestätigung aufgefordert, bevor Sie ausgeführt werden `Update-Script` .</span><span class="sxs-lookup"><span data-stu-id="d6270-123">Prompts you for confirmation before running `Update-Script`.</span></span>

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

### <span data-ttu-id="d6270-124">-Credential</span><span class="sxs-lookup"><span data-stu-id="d6270-124">-Credential</span></span>

<span data-ttu-id="d6270-125">Gibt ein Benutzerkonto an, das über die Berechtigung zum Aktualisieren eines Skripts verfügt.</span><span class="sxs-lookup"><span data-stu-id="d6270-125">Specifies a user account that has permission to update a script.</span></span>

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

### <span data-ttu-id="d6270-126">-Force</span><span class="sxs-lookup"><span data-stu-id="d6270-126">-Force</span></span>

<span data-ttu-id="d6270-127">Erzwingt das `Update-Script` Ausführen von, ohne dass eine Benutzer Bestätigung angefordert wird.</span><span class="sxs-lookup"><span data-stu-id="d6270-127">Forces `Update-Script` to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="d6270-128">-MaximumVersion</span><span class="sxs-lookup"><span data-stu-id="d6270-128">-MaximumVersion</span></span>

<span data-ttu-id="d6270-129">Gibt die maximale oder neueste Version des zu aktualisierenden Skripts an.</span><span class="sxs-lookup"><span data-stu-id="d6270-129">Specifies the maximum, or newest, version of the script to update.</span></span> <span data-ttu-id="d6270-130">Die Parameter **MaximumVersion** und Requirements **dversion** können nicht im selben Befehl verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="d6270-130">The **MaximumVersion** and **RequiredVersion** parameters can't be used in the same command.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="d6270-131">-Name</span><span class="sxs-lookup"><span data-stu-id="d6270-131">-Name</span></span>

<span data-ttu-id="d6270-132">Gibt einen Skriptnamen oder ein Array von zu aktualisierenden Skriptnamen an.</span><span class="sxs-lookup"><span data-stu-id="d6270-132">Specifies one script name or an array of script names to update.</span></span>

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

### <span data-ttu-id="d6270-133">-PassThru</span><span class="sxs-lookup"><span data-stu-id="d6270-133">-PassThru</span></span>

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

### <span data-ttu-id="d6270-134">-Proxy</span><span class="sxs-lookup"><span data-stu-id="d6270-134">-Proxy</span></span>

<span data-ttu-id="d6270-135">Gibt einen Proxy Server für die Anforderung an, anstatt eine direkte Verbindung mit einer Internet Ressource herzustellen.</span><span class="sxs-lookup"><span data-stu-id="d6270-135">Specifies a proxy server for the request rather than connecting directly to an internet resource.</span></span>

```yaml
Type: System.Uri
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="d6270-136">-Proxy Credential</span><span class="sxs-lookup"><span data-stu-id="d6270-136">-ProxyCredential</span></span>

<span data-ttu-id="d6270-137">Gibt ein Benutzerkonto an, das über die Berechtigung zum Verwenden des Proxy Servers verfügt, der durch den **Proxy** Parameter angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="d6270-137">Specifies a user account that has permission to use the proxy server specified by the **Proxy** parameter.</span></span>

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

### <span data-ttu-id="d6270-138">-Requirements dversion</span><span class="sxs-lookup"><span data-stu-id="d6270-138">-RequiredVersion</span></span>

<span data-ttu-id="d6270-139">Gibt die genaue Versionsnummer des zu aktualisierenden Skripts an.</span><span class="sxs-lookup"><span data-stu-id="d6270-139">Specifies the exact version number of the script to update.</span></span> <span data-ttu-id="d6270-140">Die Parameter **MinimumVersion** und Requirements **dversion** können nicht im selben Befehl verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="d6270-140">The **MinimumVersion** and **RequiredVersion** parameters can't be used in the same command.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="d6270-141">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="d6270-141">-WhatIf</span></span>

<span data-ttu-id="d6270-142">Zeigt, was geschieht, wenn ausgeführt wird `Update-Script` .</span><span class="sxs-lookup"><span data-stu-id="d6270-142">Shows what would happen if `Update-Script` runs.</span></span> <span data-ttu-id="d6270-143">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="d6270-143">The cmdlet isn't run.</span></span>

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

### <span data-ttu-id="d6270-144">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="d6270-144">CommonParameters</span></span>

<span data-ttu-id="d6270-145">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="d6270-145">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="d6270-146">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="d6270-146">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="d6270-147">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="d6270-147">INPUTS</span></span>

### <span data-ttu-id="d6270-148">System.String[]</span><span class="sxs-lookup"><span data-stu-id="d6270-148">System.String[]</span></span>

### <span data-ttu-id="d6270-149">System.String</span><span class="sxs-lookup"><span data-stu-id="d6270-149">System.String</span></span>

### <span data-ttu-id="d6270-150">System.Uri</span><span class="sxs-lookup"><span data-stu-id="d6270-150">System.Uri</span></span>

### <span data-ttu-id="d6270-151">System. Management. Automation. PSCredential</span><span class="sxs-lookup"><span data-stu-id="d6270-151">System.Management.Automation.PSCredential</span></span>

## <span data-ttu-id="d6270-152">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="d6270-152">OUTPUTS</span></span>

### <span data-ttu-id="d6270-153">System.Object</span><span class="sxs-lookup"><span data-stu-id="d6270-153">System.Object</span></span>

## <span data-ttu-id="d6270-154">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="d6270-154">NOTES</span></span>

## <span data-ttu-id="d6270-155">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="d6270-155">RELATED LINKS</span></span>

[<span data-ttu-id="d6270-156">Find-Script</span><span class="sxs-lookup"><span data-stu-id="d6270-156">Find-Script</span></span>](Find-Script.md)

[<span data-ttu-id="d6270-157">Install-Script</span><span class="sxs-lookup"><span data-stu-id="d6270-157">Install-Script</span></span>](Install-Script.md)

[<span data-ttu-id="d6270-158">Publish-Script</span><span class="sxs-lookup"><span data-stu-id="d6270-158">Publish-Script</span></span>](Publish-Script.md)

[<span data-ttu-id="d6270-159">Save-Script</span><span class="sxs-lookup"><span data-stu-id="d6270-159">Save-Script</span></span>](Save-Script.md)

[<span data-ttu-id="d6270-160">Uninstall-Script</span><span class="sxs-lookup"><span data-stu-id="d6270-160">Uninstall-Script</span></span>](Uninstall-Script.md)