---
ms.date: 06/12/2017
ms.topic: conceptual
keywords: wmf,powershell,setup
title: Versionshinweise zu WMF 5.x
ms.openlocfilehash: 8bdc423234cf0b104b72b1bee1de35e50783d8a4
ms.sourcegitcommit: 01b81317029b28dd9b61d167045fd31f1ec7bc06
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/17/2019
ms.locfileid: "65855765"
---
# <a name="windows-management-framework-wmf-5x-release-notes"></a><span data-ttu-id="783a0-103">Windows Management Framework (WMF) 5.x – Anmerkungen zu dieser Version</span><span class="sxs-lookup"><span data-stu-id="783a0-103">Windows Management Framework (WMF) 5.x Release Notes</span></span>

## <a name="wmf-50-changes"></a><span data-ttu-id="783a0-104">WMF 5.0-Änderungen</span><span class="sxs-lookup"><span data-stu-id="783a0-104">WMF 5.0 Changes</span></span>

- <span data-ttu-id="783a0-105">Mit PowerShell 5.0 wird ein neuer strukturierter **Information**sdatenstrom hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="783a0-105">PowerShell 5.0 adds a new structured **Information** stream</span></span>
- <span data-ttu-id="783a0-106">Verbesserungen an DSC umfassen vier neue DSC-Ressourcen:</span><span class="sxs-lookup"><span data-stu-id="783a0-106">Improvements to DSC including four new DSC resources:</span></span>
  - <span data-ttu-id="783a0-107">WindowsFeatureSet</span><span class="sxs-lookup"><span data-stu-id="783a0-107">WindowsFeatureSet</span></span>
  - <span data-ttu-id="783a0-108">WindowsOptionalFeatureSet</span><span class="sxs-lookup"><span data-stu-id="783a0-108">WindowsOptionalFeatureSet</span></span>
  - <span data-ttu-id="783a0-109">ServiceSet</span><span class="sxs-lookup"><span data-stu-id="783a0-109">ServiceSet</span></span>
  - <span data-ttu-id="783a0-110">ProcessSet</span><span class="sxs-lookup"><span data-stu-id="783a0-110">ProcessSet</span></span>
- <span data-ttu-id="783a0-111">Just Enough Administration hinzugefügt, um mithilfe von PowerShell-Remoting eine rollenbasierte Verwaltung zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="783a0-111">Added Just Enough Administration to enable role-based administration through PowerShell remoting</span></span>
- <span data-ttu-id="783a0-112">PowerShell 5.0 erweitert die Sprache, um benutzerdefinierte Klassen und Enumerationen einzuschließen.</span><span class="sxs-lookup"><span data-stu-id="783a0-112">PowerShell 5.0 extends the language to include user-defined classes and enumerations</span></span>
- <span data-ttu-id="783a0-113">Verbesserte Debuggingfunktionen in PowerShell ISE und hinzugefügtes Remotedebuggen</span><span class="sxs-lookup"><span data-stu-id="783a0-113">Improved debugging features in PowerShell ISE and added remote debugging</span></span>
- <span data-ttu-id="783a0-114">Module PowerShellGet und PackageManagement hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="783a0-114">Added the PowerShellGet and PackageManagement modules</span></span>
- <span data-ttu-id="783a0-115">Erweiterte PowerShell-Skriptprotokollierung und -transkripte</span><span class="sxs-lookup"><span data-stu-id="783a0-115">Enhanced PowerShell script logging and transcripts</span></span>
- <span data-ttu-id="783a0-116">CMS-Cmdlets (Cryptographic Message Syntax, Syntax verschlüsselter Nachrichten) hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="783a0-116">Add Cryptographic Message Syntax cmdlets</span></span>
- <span data-ttu-id="783a0-117">WMF 5.0 umfasst das NetworkSwitchManager-Modul für Windows.</span><span class="sxs-lookup"><span data-stu-id="783a0-117">WMF 5.0 includes the NetworkSwitchManager module for Windows</span></span>
- <span data-ttu-id="783a0-118">Microsoft.PowerShell.ODataUtils-Modul hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="783a0-118">Added the Microsoft.PowerShell.ODataUtils module</span></span>
- <span data-ttu-id="783a0-119">Unterstützung für Protokollierung des Softwarebestands (Software Inventory Logging, SIL) hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="783a0-119">Added support for Software Inventory Logging (SIL)</span></span>
- <span data-ttu-id="783a0-120">Mehrere neue oder aktualisiere Cmdlets als Reaktion auf Benutzeranforderungen und Probleme</span><span class="sxs-lookup"><span data-stu-id="783a0-120">Sever new or update cmdlets in response to user requests and issues</span></span>

## <a name="wmf-51-changes"></a><span data-ttu-id="783a0-121">WMF 5.1 Änderungen</span><span class="sxs-lookup"><span data-stu-id="783a0-121">WMF 5.1 Changes</span></span>

<span data-ttu-id="783a0-122">WMF 5.1 umfasst PowerShell, WMI und WinRM sowie SIL-Komponenten (Softwareinventurprotokollierung), die mit Windows Server 2016 veröffentlicht wurden.</span><span class="sxs-lookup"><span data-stu-id="783a0-122">WMF 5.1 includes the PowerShell, WMI, WinRM, and Software Inventory Logging (SIL) components that were released with Windows Server 2016.</span></span> <span data-ttu-id="783a0-123">WMF 5.1 kann auf Windows 7, Windows 8.1, Windows Server 2008 R2, 2012 und 2012 R2 installiert werden und bietet gegenüber WMF 5.0 eine Reihe von Vorteilen. Dazu zählen u. a.:</span><span class="sxs-lookup"><span data-stu-id="783a0-123">WMF 5.1 can be installed on Windows 7, Windows 8.1, Windows Server 2008 R2, 2012, and 2012 R2, and provides several improvements over WMF 5.0 including:</span></span>

- <span data-ttu-id="783a0-124">Neue Cmdlets</span><span class="sxs-lookup"><span data-stu-id="783a0-124">New cmdlets</span></span>
- <span data-ttu-id="783a0-125">PowerShellGet-Verbesserungen wie z. B. die Durchsetzung von signierten Modulen und die Installation von JEA-Modulen</span><span class="sxs-lookup"><span data-stu-id="783a0-125">PowerShellGet improvements include enforcing signed modules, and installing JEA modules</span></span>
- <span data-ttu-id="783a0-126">Bei PackageManagement wurde Unterstützung für Container, CBS-Setup, EXE-basiertes Setup und CAB-Pakete hinzugefügt</span><span class="sxs-lookup"><span data-stu-id="783a0-126">PackageManagement added support for Containers, CBS Setup, EXE-based setup, CAB packages</span></span>
- <span data-ttu-id="783a0-127">Debuggingverbesserungen für DSC und PowerShell-Klassen</span><span class="sxs-lookup"><span data-stu-id="783a0-127">Debugging improvements for DSC and PowerShell classes</span></span>
- <span data-ttu-id="783a0-128">Sicherheitsverbesserungen wie u. a. die Durchsetzung von katalogsignierten Modulen vom Pullserver und bei Verwendung von PowerShellGet-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="783a0-128">Security enhancements including enforcement of catalog-signed modules coming from the Pull Server and when using PowerShellGet cmdlets</span></span>
- <span data-ttu-id="783a0-129">Antworten auf verschiedene Benutzeranfragen und zu Problemen</span><span class="sxs-lookup"><span data-stu-id="783a0-129">Responses to a number of user requests and issues</span></span>

## <a name="powershell-editions"></a><span data-ttu-id="783a0-130">PowerShell-Editionen</span><span class="sxs-lookup"><span data-stu-id="783a0-130">PowerShell Editions</span></span>

<span data-ttu-id="783a0-131">Ab Version 5.1 steht PowerShell in verschiedenen Editionen zur Verfügung, die unterschiedliche Featuregruppen und Plattformkompatibilität bieten.</span><span class="sxs-lookup"><span data-stu-id="783a0-131">Starting with version 5.1, PowerShell is available in different editions that denote varying feature sets and platform compatibility.</span></span>

- <span data-ttu-id="783a0-132">**Desktop-Edition:** Diese Edition basiert auf .NET Framework und bietet Kompatibilität mit Skripts und Modulen für Versionen von PowerShell, die unter Vollversionen von Windows wie Server Core und Windows Desktop ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="783a0-132">**Desktop Edition:** Built on .NET Framework and provides compatibility with scripts and modules targeting versions of PowerShell running on full footprint editions of Windows such as Server Core and Windows Desktop.</span></span>
- <span data-ttu-id="783a0-133">**Core-Edition:** Diese Edition basiert auf .NET Core und bietet Kompatibilität mit Skripts und Modulen für Versionen von PowerShell, die unter funktionsreduzierten Versionen von Windows wie Nano Server und Windows IoT ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="783a0-133">**Core Edition:** Built on .NET Core and provides compatibility with scripts and modules targeting versions of PowerShell running on reduced footprint editions of Windows such as Nano Server and Windows IoT.</span></span>

### <a name="learn-more-about-using-powershell-editions"></a><span data-ttu-id="783a0-134">Weitere Informationen zur Verwendung von PowerShell-Editionen</span><span class="sxs-lookup"><span data-stu-id="783a0-134">Learn more about using PowerShell Editions</span></span>

- [<span data-ttu-id="783a0-135">Determine running edition of PowerShell using $PSVersionTable (Bestimmen der ausgeführten Edition von PowerShell mit $PSVersionTable)</span><span class="sxs-lookup"><span data-stu-id="783a0-135">Determine running edition of PowerShell using $PSVersionTable</span></span>](/powershell/module/microsoft.powershell.core/about/about_automatic_variables)
- [<span data-ttu-id="783a0-136">Filter Get-Module results by CompatiblePSEditions using PSEdition parameter (Filtern von Get-Module-Ergebnissen nach CompatiblePSEditions mithilfe des PSEdition-Parameters)</span><span class="sxs-lookup"><span data-stu-id="783a0-136">Filter Get-Module results by CompatiblePSEditions using PSEdition parameter</span></span>](/powershell/module/microsoft.powershell.core/get-module)
- [<span data-ttu-id="783a0-137">Verhindern der Ausführung von Skripts außer bei Ausführung in einer kompatiblen Edition von PowerShell</span><span class="sxs-lookup"><span data-stu-id="783a0-137">Prevent script execution unless run on a compatible edition of PowerShell</span></span>](/powershell/gallery/concepts/script-psedition-support)
- [<span data-ttu-id="783a0-138">Deklarieren der Kompatibilität eines Moduls mit bestimmten Versionen von PowerShell</span><span class="sxs-lookup"><span data-stu-id="783a0-138">Declare a module's compatibility to specific PowerShell versions</span></span>](/powershell/gallery/concepts/module-psedition-support)

## <a name="module-analysis-cache"></a><span data-ttu-id="783a0-139">Die Datei „ModuleAnalysisCache“</span><span class="sxs-lookup"><span data-stu-id="783a0-139">Module Analysis Cache</span></span>

<span data-ttu-id="783a0-140">Ab Version 5.1 bietet PowerShell Kontrolle über die Datei, die zum Zwischenspeichern von Daten zu einem Modul verwendet wird, z. B. der Befehle, die es exportiert.</span><span class="sxs-lookup"><span data-stu-id="783a0-140">Starting with WMF 5.1, PowerShell provides control over the file that is used to cache data about a module, such as the commands it exports.</span></span>

<span data-ttu-id="783a0-141">Standardmäßig wird dieser Cache in der Datei `${env:LOCALAPPDATA}\Microsoft\Windows\PowerShell\ModuleAnalysisCache` gespeichert.</span><span class="sxs-lookup"><span data-stu-id="783a0-141">By default, this cache is stored in the file `${env:LOCALAPPDATA}\Microsoft\Windows\PowerShell\ModuleAnalysisCache`.</span></span> <span data-ttu-id="783a0-142">Der Cache wird in der Regel beim Start der Suche nach einem Befehl gelesen und einige Zeit nach dem Import des Moduls in einem Hintergrundthread geschrieben.</span><span class="sxs-lookup"><span data-stu-id="783a0-142">The cache is typically read at startup while searching for a command and is written on a background thread sometime after a module is imported.</span></span>

<span data-ttu-id="783a0-143">Um den Standardspeicherort des Caches zu ändern, legen Sie die Umgebungsvariable `$env:PSModuleAnalysisCachePath` vor dem Starten von PowerShell fest.</span><span class="sxs-lookup"><span data-stu-id="783a0-143">To change the default location of the cache, set the `$env:PSModuleAnalysisCachePath` environment variable before starting PowerShell.</span></span> <span data-ttu-id="783a0-144">Änderungen an dieser Umgebungsvariablen betreffen nur untergeordnete Prozesse.</span><span class="sxs-lookup"><span data-stu-id="783a0-144">Changes to this environment variable will only affect children processes.</span></span> <span data-ttu-id="783a0-145">Der Wert muss einen vollständigen Pfad (samt Dateiname) definieren, in dem PowerShell die Berechtigung zum Erstellen und Schreiben von Dateien hat.</span><span class="sxs-lookup"><span data-stu-id="783a0-145">The value should name a full path (including filename) that PowerShell has permission to create and write files.</span></span> <span data-ttu-id="783a0-146">Zum Deaktivieren des Dateicaches kann dieser Wert auf einen ungültigen Speicherort festgelegt werden. Beispiel:</span><span class="sxs-lookup"><span data-stu-id="783a0-146">To disable the file cache, set this value to an invalid location, for example:</span></span>

```powershell
$env:PSModuleAnalysisCachePath = 'nul'
```

<span data-ttu-id="783a0-147">Hiermit wird der Pfad auf ein ungültiges Gerät festgelegt.</span><span class="sxs-lookup"><span data-stu-id="783a0-147">This sets the path to an invalid device.</span></span> <span data-ttu-id="783a0-148">Wenn PowerShell nicht in den Pfad schreiben kann, wird keine Fehlermeldung zurückgegeben. Mithilfe eines Ablaufverfolgungstools können Sie jedoch einen Fehlerbericht anzeigen:</span><span class="sxs-lookup"><span data-stu-id="783a0-148">If PowerShell can't write to the path, no error is returned, but you can see error reporting by using a tracer:</span></span>

```powershell
Trace-Command -PSHost -Name Modules -Expression { Import-Module Microsoft.PowerShell.Management -Force }
```

<span data-ttu-id="783a0-149">Bei der Ausgabe aus dem Cache sucht PowerShell nach Modulen, die nicht mehr vorhanden sind, um einen unnötig großen Cache zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="783a0-149">When writing out the cache, PowerShell will check for modules that no longer exist to avoid an unnecessarily large cache.</span></span> <span data-ttu-id="783a0-150">Mitunter sind diese Überprüfungen nicht wünschenswert, weshalb Sie sie deaktivieren können, indem Sie Folgendes festlegen:</span><span class="sxs-lookup"><span data-stu-id="783a0-150">Sometimes these checks are not desirable, in which case you can turn them off by setting:</span></span>

```powershell
$env:PSDisableModuleAnalysisCacheCleanup = 1
```

<span data-ttu-id="783a0-151">Das Festlegen dieser Umgebungsvariablen wird im aktuellen Prozess sofort wirksam.</span><span class="sxs-lookup"><span data-stu-id="783a0-151">Setting this environment variable will take effect immediately in the current process.</span></span>

## <a name="specifying-module-version"></a><span data-ttu-id="783a0-152">Angeben der Modulversion</span><span class="sxs-lookup"><span data-stu-id="783a0-152">Specifying module version</span></span>

<span data-ttu-id="783a0-153">In WMF 5.1 verhält sich `using module` genauso wie andere modulbezogene Konstruktionen in PowerShell.</span><span class="sxs-lookup"><span data-stu-id="783a0-153">In WMF 5.1, `using module` behaves the same way as other module-related constructions in PowerShell.</span></span>
<span data-ttu-id="783a0-154">Zuvor gab es keine Möglichkeit, eine bestimmte Modulversion anzugeben. Wenn mehrere Versionen vorhanden waren, führte dies zu einem Fehler.</span><span class="sxs-lookup"><span data-stu-id="783a0-154">Previously, you had no way to specify a particular module version; if there were multiple versions present, this resulted in an error.</span></span>

<span data-ttu-id="783a0-155">In WMF 5.1:</span><span class="sxs-lookup"><span data-stu-id="783a0-155">In WMF 5.1:</span></span>

- <span data-ttu-id="783a0-156">Sie können den [Konstruktor „ModuleSpecification“ (Hashtabelle)](/dotnet/api/microsoft.powershell.commands.modulespecification.-ctor?view=powershellsdk-1.1.0#Microsoft_PowerShell_Commands_ModuleSpecification__ctor_System_Collections_Hashtable_) verwenden.</span><span class="sxs-lookup"><span data-stu-id="783a0-156">You can use [ModuleSpecification Constructor (Hashtable)](/dotnet/api/microsoft.powershell.commands.modulespecification.-ctor?view=powershellsdk-1.1.0#Microsoft_PowerShell_Commands_ModuleSpecification__ctor_System_Collections_Hashtable_).</span></span>
  <span data-ttu-id="783a0-157">Diese Hashtabelle hat das gleiche Format wie `Get-Module -FullyQualifiedName`.</span><span class="sxs-lookup"><span data-stu-id="783a0-157">This hash table has the same format as `Get-Module -FullyQualifiedName`.</span></span>

  <span data-ttu-id="783a0-158">**Beispiel:** `using module @{ModuleName = 'PSReadLine'; RequiredVersion = '1.1'}`</span><span class="sxs-lookup"><span data-stu-id="783a0-158">**Example:** `using module @{ModuleName = 'PSReadLine'; RequiredVersion = '1.1'}`</span></span>

- <span data-ttu-id="783a0-159">Wenn mehrere Versionen des Moduls vorhanden sind, verwendet PowerShell **dieselbe Auflösungslogik** wie `Import-Module` und gibt keinen Fehler zurück, was dem Verhalten von `Import-Module` und `Import-DscResource` entspricht.</span><span class="sxs-lookup"><span data-stu-id="783a0-159">If there are multiple versions of the module, PowerShell uses the **same resolution logic** as `Import-Module` and doesn't return an error--the same behavior as `Import-Module` and `Import-DscResource`.</span></span>

## <a name="improvements-to-pester"></a><span data-ttu-id="783a0-160">Verbesserungen an Pester</span><span class="sxs-lookup"><span data-stu-id="783a0-160">Improvements to Pester</span></span>

<span data-ttu-id="783a0-161">In WMF 5.1 wurde die Version von Pester, die im Lieferumfang von PowerShell enthalten ist, von 3.3.5 auf 3.4.0 aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="783a0-161">In WMF 5.1, the version of Pester that ships with PowerShell has been updated from 3.3.5 to 3.4.0.</span></span>
<span data-ttu-id="783a0-162">Dieses Update ermöglicht ein besseres Verhalten für Pester auf Nano Server.</span><span class="sxs-lookup"><span data-stu-id="783a0-162">This update enables better behavior for Pester on Nano Server.</span></span>

<span data-ttu-id="783a0-163">Sie können die Änderungen in Pest überprüfen, indem Sie das [ChangeLog](https://github.com/pester/Pester/blob/master/CHANGELOG.md) im GitHub-Repository durchgehen.</span><span class="sxs-lookup"><span data-stu-id="783a0-163">You can review the changes in Pest by inspecting the [ChangeLog](https://github.com/pester/Pester/blob/master/CHANGELOG.md) in the GitHub repository.</span></span>