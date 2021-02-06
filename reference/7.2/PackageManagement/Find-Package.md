---
external help file: Microsoft.PowerShell.PackageManagement.dll-Help.xml
Locale: en-US
Module Name: PackageManagement
ms.date: 04/03/2019
online version: https://docs.microsoft.com/powershell/module/packagemanagement/find-package?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Find-Package
ms.openlocfilehash: c45ff8443818580dcc57cd1a945822007ae259a8
ms.sourcegitcommit: 22c93550c87af30c4895fcb9e9dd65e30d60ada0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/19/2020
ms.locfileid: "99602331"
---
# <span data-ttu-id="0bd1e-102">Find-Package</span><span class="sxs-lookup"><span data-stu-id="0bd1e-102">Find-Package</span></span>

## <span data-ttu-id="0bd1e-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="0bd1e-103">SYNOPSIS</span></span>
<span data-ttu-id="0bd1e-104">Findet Softwarepakete in verfügbaren Paketquellen.</span><span class="sxs-lookup"><span data-stu-id="0bd1e-104">Finds software packages in available package sources.</span></span>

## <span data-ttu-id="0bd1e-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="0bd1e-105">SYNTAX</span></span>

### <span data-ttu-id="0bd1e-106">NuGet</span><span class="sxs-lookup"><span data-stu-id="0bd1e-106">NuGet</span></span>

```
Find-Package [-IncludeDependencies] [-AllVersions] [-Source <String[]>] [-Credential <PSCredential>]
 [-Proxy <Uri>] [-ProxyCredential <PSCredential>] [[-Name] <String[]>] [-RequiredVersion <String>]
 [-MinimumVersion <String>] [-MaximumVersion <String>] [-Force] [-ForceBootstrap]
 [-ProviderName <String[]>] [-ConfigFile <String>] [-SkipValidate] [-Headers <String[]>]
 [-FilterOnTag <String[]>] [-Contains <String>] [-AllowPrereleaseVersions] [<CommonParameters>]
```

### <span data-ttu-id="0bd1e-107">PowerShellGet</span><span class="sxs-lookup"><span data-stu-id="0bd1e-107">PowerShellGet</span></span>

```
Find-Package [-IncludeDependencies] [-AllVersions] [-Source <String[]>] [-Credential <PSCredential>]
 [-Proxy <Uri>] [-ProxyCredential <PSCredential>] [[-Name] <String[]>] [-RequiredVersion <String>]
 [-MinimumVersion <String>] [-MaximumVersion <String>] [-Force] [-ForceBootstrap]
 [-ProviderName <String[]>] [-AllowPrereleaseVersions] [-PackageManagementProvider <String>]
 [-PublishLocation <String>] [-ScriptSourceLocation <String>] [-ScriptPublishLocation <String>]
 [-Type <String>] [-Filter <String>] [-Tag <String[]>] [-Includes <String[]>]
 [-DscResource <String[]>] [-RoleCapability <String[]>] [-Command <String[]>] [-AcceptLicense]
 [<CommonParameters>]
```

## <span data-ttu-id="0bd1e-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="0bd1e-108">DESCRIPTION</span></span>

<span data-ttu-id="0bd1e-109">`Find-Package` findet Softwarepakete, die in Paketquellen verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="0bd1e-109">`Find-Package` finds software packages that are available in package sources.</span></span> <span data-ttu-id="0bd1e-110">`Get-PackageProvider` und `Get-PackageSource` zeigen Sie Details zu ihren Anbietern an.</span><span class="sxs-lookup"><span data-stu-id="0bd1e-110">`Get-PackageProvider` and `Get-PackageSource` display details about your providers.</span></span>

## <span data-ttu-id="0bd1e-111">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="0bd1e-111">EXAMPLES</span></span>

### <span data-ttu-id="0bd1e-112">Beispiel 1: Suchen aller verfügbaren Pakete von einem Paketanbieter</span><span class="sxs-lookup"><span data-stu-id="0bd1e-112">Example 1: Find all available packages from a package provider</span></span>

<span data-ttu-id="0bd1e-113">Mit diesem Befehl werden alle verfügbaren PowerShell-Modul Pakete in einem registrierten Katalog gefunden.</span><span class="sxs-lookup"><span data-stu-id="0bd1e-113">This command finds all available PowerShell module packages in a registered gallery.</span></span> <span data-ttu-id="0bd1e-114">Verwenden `Get-PackageProvider` Sie, um den Anbieter Namen zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="0bd1e-114">Use `Get-PackageProvider` to get the provider name.</span></span>

```
Find-Package -ProviderName NuGet
```

```Output
Name               Version   Source     Summary
----               -------   ------     -------
NUnit              3.11.0    MyNuGet    NUnit is a unit-testing framework for all .NET langua...
Newtonsoft.Json    12.0.1    MyNuGet    Json.NET is a popular high-performance JSON framework...
EntityFramework    6.2.0     MyNuGet    Entity Framework is Microsoft's recommended data acce...
MySql.Data         8.0.15    MyNuGet    MySql.Data.MySqlClient .Net Core Class Library
bootstrap          4.3.1     MyNuGet    Bootstrap framework in CSS. Includes fonts and JavaSc...
NuGet.Core         2.14.0    MyNuGet    NuGet.Core is the core framework assembly for NuGet...
```

<span data-ttu-id="0bd1e-115">`Find-Package` verwendet den **Provider** -Parameter, um den **nuget**-Anbieter anzugeben.</span><span class="sxs-lookup"><span data-stu-id="0bd1e-115">`Find-Package` uses the **Provider** parameter to specify the provider **NuGet**.</span></span>

### <span data-ttu-id="0bd1e-116">Beispiel 2: Suchen eines Pakets aus einer Paketquelle</span><span class="sxs-lookup"><span data-stu-id="0bd1e-116">Example 2: Find a package from a package source</span></span>

<span data-ttu-id="0bd1e-117">Dieser Befehl sucht die neueste Version eines Pakets aus einer angegebenen Paketquelle.</span><span class="sxs-lookup"><span data-stu-id="0bd1e-117">This command finds the newest version of a package from a specified package source.</span></span> <span data-ttu-id="0bd1e-118">Wenn keine Paketquelle bereitgestellt wird, `Find-Package` durchsucht die einzelnen installierten Paketanbieter und die zugehörigen Paketquellen.</span><span class="sxs-lookup"><span data-stu-id="0bd1e-118">If a package source isn't provided, `Find-Package` searches each installed package provider and its package sources.</span></span> <span data-ttu-id="0bd1e-119">Verwenden `Get-PackageSource` Sie, um den Quellnamen zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="0bd1e-119">Use `Get-PackageSource` to get the source name.</span></span>

```
Find-Package -Name NuGet.Core -Source MyNuGet
```

```Output
Name         Version   Source    Summary
----         -------   ------    -------
NuGet.Core   2.14.0    MyNuGet   NuGet.Core is the core framework assembly for NuGet...
```

<span data-ttu-id="0bd1e-120">`Find-Package` verwendet den **Name** -Parameter, um den Paketnamen " **nuget. Core**" anzugeben.</span><span class="sxs-lookup"><span data-stu-id="0bd1e-120">`Find-Package` uses the **Name** parameter to specify the package name **NuGet.Core**.</span></span> <span data-ttu-id="0bd1e-121">Der **Source** -Parameter gibt an, dass in **mynuget** nach dem Paket gesucht werden soll.</span><span class="sxs-lookup"><span data-stu-id="0bd1e-121">The **Source** parameter specifies to search for the package in **MyNuGet**.</span></span>

### <span data-ttu-id="0bd1e-122">Beispiel 3: Suchen aller Versionen eines Pakets</span><span class="sxs-lookup"><span data-stu-id="0bd1e-122">Example 3: Find all versions of a package</span></span>

<span data-ttu-id="0bd1e-123">Mit diesem Befehl werden alle verfügbaren Paketversionen von einem angegebenen Anbieter ermittelt.</span><span class="sxs-lookup"><span data-stu-id="0bd1e-123">This command finds all available package versions from a specified provider.</span></span>

```
Find-Package -Name NuGet.Core -Source MyNuGet -AllVersions
```

```Output
Name          Version          Source       Summary
----          -------          ------       -------
NuGet.Core    2.14.0           MyNuGet      NuGet.Core is the core framework assembly for NuGet...
NuGet.Core    2.14.0-rtm-832   MyNuGet      NuGet.Core is the core framework assembly for NuGet...
NuGet.Core    2.13.0           MyNuGet      NuGet.Core is the core framework assembly for NuGet...
...
NuGet.Core    1.1.229.159      MyNuGet      NuGet.Core is the core framework assembly for NuGet...
Nuget.Core    1.0.1120.104     MyNuGet      NuGet.Core is the core framework assembly for NuGet...
```

<span data-ttu-id="0bd1e-124">`Find-Package` verwendet den **Name** -Parameter, um das **nuget. Core**-Paket anzugeben.</span><span class="sxs-lookup"><span data-stu-id="0bd1e-124">`Find-Package` uses the **Name** parameter to specify the package **NuGet.Core**.</span></span> <span data-ttu-id="0bd1e-125">Der **providerName** -Parameter gibt an, dass in **mynuget** nach dem Paket gesucht werden soll.</span><span class="sxs-lookup"><span data-stu-id="0bd1e-125">The **ProviderName** parameter specifies to search for the package in **MyNuGet**.</span></span> <span data-ttu-id="0bd1e-126">**Allversions** gibt an, dass alle verfügbaren Versionen zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="0bd1e-126">**AllVersions** specifies that all available versions are returned.</span></span>

### <span data-ttu-id="0bd1e-127">Beispiel 4: Suchen eines Pakets mit einem bestimmten Namen und einer bestimmten Version</span><span class="sxs-lookup"><span data-stu-id="0bd1e-127">Example 4: Find a package with a specific name and version</span></span>

<span data-ttu-id="0bd1e-128">Dieser Befehl sucht eine bestimmte Paketversion von einem angegebenen Anbieter.</span><span class="sxs-lookup"><span data-stu-id="0bd1e-128">This command finds a specific package version from a specified provider.</span></span>

```
Find-Package -Name NuGet.Core -ProviderName NuGet -RequiredVersion 2.9.0
```

```Output
Name          Version          Source       Summary
----          -------          ------       -------
NuGet.Core    2.9.0            MyNuGet      NuGet.Core is the core framework assembly for NuGet...
```

<span data-ttu-id="0bd1e-129">`Find-Package` verwendet den **Name** -Parameter, um den Paketnamen " **nuget. Core**" anzugeben.</span><span class="sxs-lookup"><span data-stu-id="0bd1e-129">`Find-Package` uses the **Name** parameter to specify the package name **NuGet.Core**.</span></span> <span data-ttu-id="0bd1e-130">Der **providerName** -Parameter gibt an, dass in **nuget** nach dem Paket gesucht werden soll.</span><span class="sxs-lookup"><span data-stu-id="0bd1e-130">The **ProviderName** parameter specifies to search for the package in **NuGet**.</span></span> <span data-ttu-id="0bd1e-131">Requirements **dversion** gibt an, dass nur Version **2.9.0** zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="0bd1e-131">**RequiredVersion** specifies that only version **2.9.0** is returned.</span></span>

### <span data-ttu-id="0bd1e-132">Beispiel 5: Suchen nach Paketen innerhalb eines Bereichs von Versionen</span><span class="sxs-lookup"><span data-stu-id="0bd1e-132">Example 5: Find packages within a range of versions</span></span>

<span data-ttu-id="0bd1e-133">Dieser Befehl sucht einen Bereich von Versionen für ein angegebenes Paket.</span><span class="sxs-lookup"><span data-stu-id="0bd1e-133">This command finds a range of versions for a specified package.</span></span>

```
Find-Package -Name NuGet.Core -ProviderName NuGet -MinimumVersion 2.7.0 -MaximumVersion 2.9.0 -AllVersions
```

```Output
Name          Version          Source       Summary
----          -------          ------       -------
NuGet.Core    2.9.0            MyNuGet      NuGet.Core is the core framework assembly for NuGet...
NuGet.Core    2.8.6            MyNuGet      NuGet.Core is the core framework assembly for NuGet...
NuGet.Core    2.8.0            MyNuGet      NuGet.Core is the core framework assembly for NuGet...
NuGet.Core    2.7.0            MyNuGet      NuGet.Core is the core framework assembly for NuGet...
```

<span data-ttu-id="0bd1e-134">`Find-Package` verwendet den **Name** -Parameter, um den Paketnamen " **nuget. Core**" anzugeben.</span><span class="sxs-lookup"><span data-stu-id="0bd1e-134">`Find-Package` uses the **Name** parameter to specify the package name **NuGet.Core**.</span></span> <span data-ttu-id="0bd1e-135">Der **providerName** -Parameter gibt an, dass in **nuget** nach dem Paket gesucht werden soll.</span><span class="sxs-lookup"><span data-stu-id="0bd1e-135">The **ProviderName** parameter specifies to search for the package in **NuGet**.</span></span> <span data-ttu-id="0bd1e-136">**MinimumVersion** gibt die niedrigste Version an **2.7.0** an.</span><span class="sxs-lookup"><span data-stu-id="0bd1e-136">**MinimumVersion** specifies the lowest version **2.7.0**.</span></span> <span data-ttu-id="0bd1e-137">**MaximumVersion** gibt die höchste Version an **2.9.0** an.</span><span class="sxs-lookup"><span data-stu-id="0bd1e-137">**MaximumVersion** specifies the highest version **2.9.0**.</span></span>
<span data-ttu-id="0bd1e-138">**Allversions** gibt an, dass der Bereich gemäß dem minimal-und Maximalwert zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="0bd1e-138">**AllVersions** determines the range is returned as specified by the minimum and maximum.</span></span>

### <span data-ttu-id="0bd1e-139">Beispiel 6: Suchen eines Pakets aus einem Dateisystem</span><span class="sxs-lookup"><span data-stu-id="0bd1e-139">Example 6: Find a package from a file system</span></span>

<span data-ttu-id="0bd1e-140">Dieser Befehl sucht Pakete mit der Dateierweiterung `.nupkg` , die auf dem lokalen Computer gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="0bd1e-140">This command finds packages with the file extension `.nupkg` that are stored on the local computer.</span></span>
<span data-ttu-id="0bd1e-141">Bei den Dateien handelt es sich um Pakete, die aus einem Katalog wie **nuget** heruntergeladen werden.</span><span class="sxs-lookup"><span data-stu-id="0bd1e-141">The files are packages downloaded from a gallery such as the **NuGet**.</span></span>

```
PS> Find-Package -Source C:\LocalPkg
```

```Output
Name                 Version    Source           Summary
----                 -------    ------           -------
Microsoft.Web.Xdt    3.0.0      C:\LocalPkg\     Microsoft Xml Document Transformation (XDT)...
NuGet.Core           2.14.0     C:\LocalPkg\     NuGet.Core is the core framework assembly...
```

## <span data-ttu-id="0bd1e-142">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="0bd1e-142">PARAMETERS</span></span>

### <span data-ttu-id="0bd1e-143">-AcceptLicense</span><span class="sxs-lookup"><span data-stu-id="0bd1e-143">-AcceptLicense</span></span>

<span data-ttu-id="0bd1e-144">Akzeptiert automatisch einen Lizenzvertrag, wenn dies für das Paket erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="0bd1e-144">Automatically accepts a license agreement if the package requires it.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: PowerShellGet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0bd1e-145">-Allowprereleaseversions</span><span class="sxs-lookup"><span data-stu-id="0bd1e-145">-AllowPrereleaseVersions</span></span>

<span data-ttu-id="0bd1e-146">Schließt Pakete ein, die in den Ergebnissen als Vorabversion gekennzeichnet sind.</span><span class="sxs-lookup"><span data-stu-id="0bd1e-146">Includes packages marked as a prerelease in the results.</span></span>

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

### <span data-ttu-id="0bd1e-147">-Allversions</span><span class="sxs-lookup"><span data-stu-id="0bd1e-147">-AllVersions</span></span>

<span data-ttu-id="0bd1e-148">Gibt an, dass `Find-Package` alle verfügbaren Versionen des Pakets zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="0bd1e-148">Indicates that `Find-Package` returns all available versions of the package.</span></span> <span data-ttu-id="0bd1e-149">Standardmäßig wird `Find-Package` nur die neueste verfügbare Version zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="0bd1e-149">By default, `Find-Package` only returns the newest available version.</span></span>

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

### <span data-ttu-id="0bd1e-150">-Command</span><span class="sxs-lookup"><span data-stu-id="0bd1e-150">-Command</span></span>

<span data-ttu-id="0bd1e-151">Gibt ein Array von Befehlen an, die von gesucht werden `Find-Package` .</span><span class="sxs-lookup"><span data-stu-id="0bd1e-151">Specifies an array of commands searched by `Find-Package`.</span></span>

```yaml
Type: System.String[]
Parameter Sets: PowerShellGet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0bd1e-152">-Configfile</span><span class="sxs-lookup"><span data-stu-id="0bd1e-152">-ConfigFile</span></span>

<span data-ttu-id="0bd1e-153">Gibt eine Konfigurationsdatei an.</span><span class="sxs-lookup"><span data-stu-id="0bd1e-153">Specifies a configuration file.</span></span>

```yaml
Type: System.String
Parameter Sets: NuGet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0bd1e-154">-Enthält</span><span class="sxs-lookup"><span data-stu-id="0bd1e-154">-Contains</span></span>

<span data-ttu-id="0bd1e-155">`Find-Package` Ruft Objekte ab, wenn ein beliebiges Element in den Eigenschafts Werten des Objekts eine genaue Entsprechung für den angegebenen Wert ist.</span><span class="sxs-lookup"><span data-stu-id="0bd1e-155">`Find-Package` gets objects if any item in the object's property values are an exact match for the specified value.</span></span>

```yaml
Type: System.String
Parameter Sets: NuGet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0bd1e-156">-Credential</span><span class="sxs-lookup"><span data-stu-id="0bd1e-156">-Credential</span></span>

<span data-ttu-id="0bd1e-157">Gibt ein Benutzerkonto an, das über die Berechtigung zum Suchen nach Paketen verfügt.</span><span class="sxs-lookup"><span data-stu-id="0bd1e-157">Specifies a user account that has permission to search for packages.</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0bd1e-158">-Dscresource</span><span class="sxs-lookup"><span data-stu-id="0bd1e-158">-DscResource</span></span>

<span data-ttu-id="0bd1e-159">Gibt ein Array von DSC-Ressourcen (DSC) an, die von diesem Cmdlet durchsucht werden.</span><span class="sxs-lookup"><span data-stu-id="0bd1e-159">Specifies an array of Desired State Configuration (DSC) resources that this cmdlet searches.</span></span>

```yaml
Type: System.String[]
Parameter Sets: PowerShellGet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0bd1e-160">-Filter</span><span class="sxs-lookup"><span data-stu-id="0bd1e-160">-Filter</span></span>

<span data-ttu-id="0bd1e-161">Gibt die Begriffe an, nach denen in den Eigenschaften **Name** und **Description** gesucht werden soll.</span><span class="sxs-lookup"><span data-stu-id="0bd1e-161">Specifies terms to search for within the **Name** and **Description** properties.</span></span>

```yaml
Type: System.String
Parameter Sets: PowerShellGet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0bd1e-162">-Filterontag</span><span class="sxs-lookup"><span data-stu-id="0bd1e-162">-FilterOnTag</span></span>

<span data-ttu-id="0bd1e-163">Gibt das Tag an, das die Ergebnisse filtert.</span><span class="sxs-lookup"><span data-stu-id="0bd1e-163">Specifies the tag that filters the results.</span></span> <span data-ttu-id="0bd1e-164">Ergebnisse, die das angegebene Tag nicht enthalten, werden ausgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="0bd1e-164">Results that don't contain the specified tag are excluded.</span></span>

```yaml
Type: System.String[]
Parameter Sets: NuGet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0bd1e-165">-Force</span><span class="sxs-lookup"><span data-stu-id="0bd1e-165">-Force</span></span>

<span data-ttu-id="0bd1e-166">Erzwingt die Ausführung des Befehls ohne Aufforderung zur Bestätigung durch den Benutzer.</span><span class="sxs-lookup"><span data-stu-id="0bd1e-166">Forces the command to run without asking for user confirmation.</span></span>

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

### <span data-ttu-id="0bd1e-167">-Forcebootstrap</span><span class="sxs-lookup"><span data-stu-id="0bd1e-167">-ForceBootstrap</span></span>

<span data-ttu-id="0bd1e-168">Gibt an, dass `Find-Package` **packagemanagement** zwingt, den Paketanbieter automatisch zu installieren.</span><span class="sxs-lookup"><span data-stu-id="0bd1e-168">Indicates that `Find-Package` forces **PackageManagement** to automatically install the package provider.</span></span>

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

### <span data-ttu-id="0bd1e-169">-Header</span><span class="sxs-lookup"><span data-stu-id="0bd1e-169">-Headers</span></span>

<span data-ttu-id="0bd1e-170">Gibt die Header für das Paket an.</span><span class="sxs-lookup"><span data-stu-id="0bd1e-170">Specifies the headers for the package.</span></span>

```yaml
Type: System.String[]
Parameter Sets: NuGet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0bd1e-171">-Includababhängigkeiten</span><span class="sxs-lookup"><span data-stu-id="0bd1e-171">-IncludeDependencies</span></span>

<span data-ttu-id="0bd1e-172">Gibt an, dass dieses Cmdlet Paketabhängigkeiten in den Ergebnissen enthält.</span><span class="sxs-lookup"><span data-stu-id="0bd1e-172">Indicates that this cmdlet includes package dependencies in the results.</span></span>

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

### <span data-ttu-id="0bd1e-173">-Includes</span><span class="sxs-lookup"><span data-stu-id="0bd1e-173">-Includes</span></span>

<span data-ttu-id="0bd1e-174">Gibt an, ob `Find-Package` alle Pakete innerhalb einer Kategorie finden soll.</span><span class="sxs-lookup"><span data-stu-id="0bd1e-174">Specifies whether `Find-Package` should find all packages within a category.</span></span>

<span data-ttu-id="0bd1e-175">Die zulässigen Werte lauten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="0bd1e-175">The accepted values are as follows:</span></span>

- <span data-ttu-id="0bd1e-176">Cmdlet</span><span class="sxs-lookup"><span data-stu-id="0bd1e-176">Cmdlet</span></span>
- <span data-ttu-id="0bd1e-177">DscResource</span><span class="sxs-lookup"><span data-stu-id="0bd1e-177">DscResource</span></span>
- <span data-ttu-id="0bd1e-178">Funktion</span><span class="sxs-lookup"><span data-stu-id="0bd1e-178">Function</span></span>
- <span data-ttu-id="0bd1e-179">RoleCapability</span><span class="sxs-lookup"><span data-stu-id="0bd1e-179">RoleCapability</span></span>
- <span data-ttu-id="0bd1e-180">Workflow</span><span class="sxs-lookup"><span data-stu-id="0bd1e-180">Workflow</span></span>

```yaml
Type: System.String[]
Parameter Sets: PowerShellGet
Aliases:
Accepted values: Cmdlet, DscResource, Function, RoleCapability, Workflow

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0bd1e-181">-MaximumVersion</span><span class="sxs-lookup"><span data-stu-id="0bd1e-181">-MaximumVersion</span></span>

<span data-ttu-id="0bd1e-182">Gibt die maximale Paketversion an, die Sie suchen möchten.</span><span class="sxs-lookup"><span data-stu-id="0bd1e-182">Specifies the maximum package version that you want to find.</span></span>

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

### <span data-ttu-id="0bd1e-183">-MinimumVersion</span><span class="sxs-lookup"><span data-stu-id="0bd1e-183">-MinimumVersion</span></span>

<span data-ttu-id="0bd1e-184">Gibt die minimale Paketversion an, die Sie suchen möchten.</span><span class="sxs-lookup"><span data-stu-id="0bd1e-184">Specifies the minimum package version that you want to find.</span></span> <span data-ttu-id="0bd1e-185">Wenn eine höhere Version verfügbar ist, wird diese Version zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="0bd1e-185">If a higher version is available, that version is returned.</span></span>

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

### <span data-ttu-id="0bd1e-186">-Name</span><span class="sxs-lookup"><span data-stu-id="0bd1e-186">-Name</span></span>

<span data-ttu-id="0bd1e-187">Gibt einen oder mehrere Paketnamen oder Paketnamen mit Platzhalter Zeichen an.</span><span class="sxs-lookup"><span data-stu-id="0bd1e-187">Specifies one or more package names, or package names with wildcard characters.</span></span> <span data-ttu-id="0bd1e-188">Trennen Sie mehrere Paketnamen durch Kommas.</span><span class="sxs-lookup"><span data-stu-id="0bd1e-188">Separate multiple package names with commas.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="0bd1e-189">-Packagemanagementprovider</span><span class="sxs-lookup"><span data-stu-id="0bd1e-189">-PackageManagementProvider</span></span>

<span data-ttu-id="0bd1e-190">Gibt den Namen eines Paket Verwaltungs Anbieters an.</span><span class="sxs-lookup"><span data-stu-id="0bd1e-190">Specifies the name of a package management provider.</span></span>

```yaml
Type: System.String
Parameter Sets: PowerShellGet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0bd1e-191">-ProviderName</span><span class="sxs-lookup"><span data-stu-id="0bd1e-191">-ProviderName</span></span>

<span data-ttu-id="0bd1e-192">Gibt einen oder mehrere Paketanbieter Namen an.</span><span class="sxs-lookup"><span data-stu-id="0bd1e-192">Specifies one or more package provider names.</span></span> <span data-ttu-id="0bd1e-193">Trennen Sie mehrere Paketanbieter Namen durch Kommas.</span><span class="sxs-lookup"><span data-stu-id="0bd1e-193">Separate multiple package provider names with commas.</span></span>
<span data-ttu-id="0bd1e-194">Verwenden `Get-PackageProvider` Sie, um eine Liste der verfügbaren Paketanbieter zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="0bd1e-194">Use `Get-PackageProvider` to get a list of available package providers.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: Provider
Accepted values: Bootstrap, NuGet, PowerShellGet

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="0bd1e-195">-Proxy</span><span class="sxs-lookup"><span data-stu-id="0bd1e-195">-Proxy</span></span>

<span data-ttu-id="0bd1e-196">Gibt einen Proxy Server für die Anforderung an, anstatt eine direkte Verbindung mit der Internet Ressource herzustellen.</span><span class="sxs-lookup"><span data-stu-id="0bd1e-196">Specifies a proxy server for the request, rather than a direct connection to the internet resource.</span></span>

```yaml
Type: System.Uri
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0bd1e-197">-Proxy Credential</span><span class="sxs-lookup"><span data-stu-id="0bd1e-197">-ProxyCredential</span></span>

<span data-ttu-id="0bd1e-198">Gibt ein Benutzerkonto an, das über die Berechtigung zur Verwendung des Proxyservers verfügt, der durch den **Proxy**-Parameter angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="0bd1e-198">Specifies a user account that has permission to use the proxy server that is specified by the **Proxy** parameter.</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0bd1e-199">-Publishlocation</span><span class="sxs-lookup"><span data-stu-id="0bd1e-199">-PublishLocation</span></span>

<span data-ttu-id="0bd1e-200">Gibt einen Speicherort für die Veröffentlichung des Pakets an.</span><span class="sxs-lookup"><span data-stu-id="0bd1e-200">Specifies a location for publishing the package.</span></span>

```yaml
Type: System.String
Parameter Sets: PowerShellGet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0bd1e-201">-Requirements dversion</span><span class="sxs-lookup"><span data-stu-id="0bd1e-201">-RequiredVersion</span></span>

<span data-ttu-id="0bd1e-202">Gibt eine genaue Paketversion an, die Sie suchen möchten.</span><span class="sxs-lookup"><span data-stu-id="0bd1e-202">Specifies an exact package version that you want to find.</span></span>

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

### <span data-ttu-id="0bd1e-203">-Rolecapability</span><span class="sxs-lookup"><span data-stu-id="0bd1e-203">-RoleCapability</span></span>

<span data-ttu-id="0bd1e-204">Gibt ein Array von Rollen Funktionen an.</span><span class="sxs-lookup"><span data-stu-id="0bd1e-204">Specifies an array of role capabilities.</span></span>

```yaml
Type: System.String[]
Parameter Sets: PowerShellGet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0bd1e-205">-Scriptpublishlocation</span><span class="sxs-lookup"><span data-stu-id="0bd1e-205">-ScriptPublishLocation</span></span>

<span data-ttu-id="0bd1e-206">Gibt einen Speicherort für die Skript Veröffentlichung für das Paket an.</span><span class="sxs-lookup"><span data-stu-id="0bd1e-206">Specifies a script publishing location for the package.</span></span>

```yaml
Type: System.String
Parameter Sets: PowerShellGet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0bd1e-207">-Scriptsourcelokation</span><span class="sxs-lookup"><span data-stu-id="0bd1e-207">-ScriptSourceLocation</span></span>

<span data-ttu-id="0bd1e-208">Gibt einen Skript Quell Speicherort an.</span><span class="sxs-lookup"><span data-stu-id="0bd1e-208">Specifies a script source location.</span></span>

```yaml
Type: System.String
Parameter Sets: PowerShellGet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0bd1e-209">-Skipvalidate</span><span class="sxs-lookup"><span data-stu-id="0bd1e-209">-SkipValidate</span></span>

<span data-ttu-id="0bd1e-210">Der Schalter, der die Überprüfung der Paket Anmelde Informationen überspringt.</span><span class="sxs-lookup"><span data-stu-id="0bd1e-210">Switch that skips package credential validation.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: NuGet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0bd1e-211">-Source</span><span class="sxs-lookup"><span data-stu-id="0bd1e-211">-Source</span></span>

<span data-ttu-id="0bd1e-212">Gibt mindestens eine Paketquelle an.</span><span class="sxs-lookup"><span data-stu-id="0bd1e-212">Specifies one or more package sources.</span></span> <span data-ttu-id="0bd1e-213">Verwenden `Get-PackageSource` Sie, um eine Liste der verfügbaren Paketquellen zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="0bd1e-213">Use `Get-PackageSource` to get a list of available package sources.</span></span> <span data-ttu-id="0bd1e-214">Ein Dateisystem Verzeichnis kann als Quelle für Download Pakete verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="0bd1e-214">A file system directory can be used as a source for download packages.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="0bd1e-215">-Tag</span><span class="sxs-lookup"><span data-stu-id="0bd1e-215">-Tag</span></span>

<span data-ttu-id="0bd1e-216">Gibt eine oder mehrere Zeichen folgen an, die in den Paket Metadaten gesucht werden sollen.</span><span class="sxs-lookup"><span data-stu-id="0bd1e-216">Specifies one or more strings to search for in the package metadata.</span></span>

```yaml
Type: System.String[]
Parameter Sets: PowerShellGet
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0bd1e-217">-Type</span><span class="sxs-lookup"><span data-stu-id="0bd1e-217">-Type</span></span>

<span data-ttu-id="0bd1e-218">Gibt an, ob nach Paketen mit einem Modul, einem Skript oder einer der beiden Optionen gesucht werden soll.</span><span class="sxs-lookup"><span data-stu-id="0bd1e-218">Specifies whether to search for packages with a module, a script, or either.</span></span>

```yaml
Type: System.String
Parameter Sets: PowerShellGet
Aliases:
Accepted values: Module, Script, All

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="0bd1e-219">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="0bd1e-219">CommonParameters</span></span>

<span data-ttu-id="0bd1e-220">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="0bd1e-220">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="0bd1e-221">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="0bd1e-221">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="0bd1e-222">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="0bd1e-222">INPUTS</span></span>

### <span data-ttu-id="0bd1e-223">Keine</span><span class="sxs-lookup"><span data-stu-id="0bd1e-223">None</span></span>

<span data-ttu-id="0bd1e-224">`Find-Package` akzeptiert keine Eingaben aus der Pipeline.</span><span class="sxs-lookup"><span data-stu-id="0bd1e-224">`Find-Package` doesn't accept input from the pipeline.</span></span>

## <span data-ttu-id="0bd1e-225">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="0bd1e-225">OUTPUTS</span></span>

### <span data-ttu-id="0bd1e-226">Softwareidentify []</span><span class="sxs-lookup"><span data-stu-id="0bd1e-226">SoftwareIdentify[]</span></span>

<span data-ttu-id="0bd1e-227">`Find-Package` Gibt ein **softwareidentity** -Objekt aus.</span><span class="sxs-lookup"><span data-stu-id="0bd1e-227">`Find-Package` outputs a **SoftwareIdentity** object.</span></span>

## <span data-ttu-id="0bd1e-228">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="0bd1e-228">NOTES</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0bd1e-229">Ab April 2020 unterstützt der PowerShell-Katalog die TLS-Versionen (Transport Layer Security) 1.0 und 1.1 nicht mehr.</span><span class="sxs-lookup"><span data-stu-id="0bd1e-229">As of April 2020, the PowerShell Gallery no longer supports Transport Layer Security (TLS) versions 1.0 and 1.1.</span></span> <span data-ttu-id="0bd1e-230">Wenn Sie nicht TLS 1.2 oder höher verwenden, erhalten Sie beim Versuch des Zugriffs auf den PowerShell-Katalog eine Fehlermeldung.</span><span class="sxs-lookup"><span data-stu-id="0bd1e-230">If you are not using TLS 1.2 or higher, you will receive an error when trying to access the PowerShell Gallery.</span></span> <span data-ttu-id="0bd1e-231">Mit dem folgenden Befehl können Sie sicherstellen, dass Sie TLS 1.2 verwenden:</span><span class="sxs-lookup"><span data-stu-id="0bd1e-231">Use the following command to ensure you are using TLS 1.2:</span></span>
>
> `[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12`
>
> <span data-ttu-id="0bd1e-232">Weitere Informationen finden Sie im PowerShell-Blog in der [Ankündigung](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/).</span><span class="sxs-lookup"><span data-stu-id="0bd1e-232">For more information, see the [announcement](https://devblogs.microsoft.com/powershell/powershell-gallery-tls-support/) in the PowerShell blog.</span></span>

## <span data-ttu-id="0bd1e-233">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="0bd1e-233">RELATED LINKS</span></span>

[<span data-ttu-id="0bd1e-234">about_PackageManagement</span><span class="sxs-lookup"><span data-stu-id="0bd1e-234">about_PackageManagement</span></span>](../Microsoft.PowerShell.Core/About/about_PackageManagement.md)

[<span data-ttu-id="0bd1e-235">Get-Package</span><span class="sxs-lookup"><span data-stu-id="0bd1e-235">Get-Package</span></span>](Get-Package.md)

[<span data-ttu-id="0bd1e-236">Get-PackageProvider</span><span class="sxs-lookup"><span data-stu-id="0bd1e-236">Get-PackageProvider</span></span>](Get-PackageProvider.md)

[<span data-ttu-id="0bd1e-237">Get-PackageSource</span><span class="sxs-lookup"><span data-stu-id="0bd1e-237">Get-PackageSource</span></span>](Get-PackageSource.md)

[<span data-ttu-id="0bd1e-238">Install-Package</span><span class="sxs-lookup"><span data-stu-id="0bd1e-238">Install-Package</span></span>](Install-Package.md)

[<span data-ttu-id="0bd1e-239">Save-Package</span><span class="sxs-lookup"><span data-stu-id="0bd1e-239">Save-Package</span></span>](Save-Package.md)

[<span data-ttu-id="0bd1e-240">Uninstall-Package</span><span class="sxs-lookup"><span data-stu-id="0bd1e-240">Uninstall-Package</span></span>](Uninstall-Package.md)