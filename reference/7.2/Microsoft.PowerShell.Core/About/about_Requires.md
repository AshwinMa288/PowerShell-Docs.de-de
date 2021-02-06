---
description: Verhindert, dass ein Skript ohne die erforderlichen Elemente ausgeführt wird.
Locale: en-US
ms.date: 12/14/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_requires?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Requires
ms.openlocfilehash: d340de615923437bb3e29c1984ef8849fe03a40e
ms.sourcegitcommit: 9a86cac80402d8193147058d4ba50e07b26059dd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/15/2020
ms.locfileid: "99599197"
---
# <a name="about-requires"></a><span data-ttu-id="c391f-103">Informationen zu voraus</span><span class="sxs-lookup"><span data-stu-id="c391f-103">About Requires</span></span>

## <a name="short-description"></a><span data-ttu-id="c391f-104">Kurze Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c391f-104">Short description</span></span>
<span data-ttu-id="c391f-105">Verhindert, dass ein Skript ohne die erforderlichen Elemente ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="c391f-105">Prevents a script from running without the required elements.</span></span>

## <a name="long-description"></a><span data-ttu-id="c391f-106">Lange Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c391f-106">Long description</span></span>

<span data-ttu-id="c391f-107">Mit der `#Requires` -Anweisung wird verhindert, dass ein Skript ausgeführt wird, es sei denn, die PowerShell-Version, die Module (und die Version) oder die Snap-Ins (und die-Version) und die Editions Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="c391f-107">The `#Requires` statement prevents a script from running unless the PowerShell version, modules (and version), or snap-ins (and version), and edition prerequisites are met.</span></span> <span data-ttu-id="c391f-108">Wenn die Voraussetzungen nicht erfüllt sind, führt PowerShell das Skript nicht aus.</span><span class="sxs-lookup"><span data-stu-id="c391f-108">If the prerequisites aren't met, PowerShell doesn't run the script.</span></span>

### <a name="syntax"></a><span data-ttu-id="c391f-109">Syntax</span><span class="sxs-lookup"><span data-stu-id="c391f-109">Syntax</span></span>

```
#Requires -Version <N>[.<n>]
#Requires -PSSnapin <PSSnapin-Name> [-Version <N>[.<n>]]
#Requires -Modules { <Module-Name> | <Hashtable> }
#Requires -PSEdition <PSEdition-Name>
#Requires -ShellId <ShellId> -PSSnapin <PSSnapin-Name> [-Version <N>[.<n>]]
#Requires -RunAsAdministrator
```

<span data-ttu-id="c391f-110">Weitere Informationen zur Syntax finden Sie unter [scriptrequirequirements](/dotnet/api/system.management.automation.language.scriptrequirements).</span><span class="sxs-lookup"><span data-stu-id="c391f-110">For more information about the syntax, see [ScriptRequirements](/dotnet/api/system.management.automation.language.scriptrequirements).</span></span>

### <a name="rules-for-use"></a><span data-ttu-id="c391f-111">Verwendungs Regeln</span><span class="sxs-lookup"><span data-stu-id="c391f-111">Rules for use</span></span>

<span data-ttu-id="c391f-112">Ein Skript kann mehr als eine `#Requires` Anweisung enthalten.</span><span class="sxs-lookup"><span data-stu-id="c391f-112">A script can include more than one `#Requires` statement.</span></span> <span data-ttu-id="c391f-113">Die- `#Requires` Anweisungen können in einer beliebigen Zeile in einem Skript angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="c391f-113">The `#Requires` statements can appear on any line in a script.</span></span>

<span data-ttu-id="c391f-114">Durch das Platzieren einer `#Requires` Anweisung innerhalb einer Funktion wird der Gültigkeitsbereich nicht eingeschränkt.</span><span class="sxs-lookup"><span data-stu-id="c391f-114">Placing a `#Requires` statement inside a function does NOT limit its scope.</span></span> <span data-ttu-id="c391f-115">Alle `#Requires` -Anweisungen werden immer global angewendet und müssen erfüllt werden, bevor das Skript ausgeführt werden kann.</span><span class="sxs-lookup"><span data-stu-id="c391f-115">All `#Requires` statements are always applied globally, and must be met, before the script can execute.</span></span>

> [!WARNING]
> <span data-ttu-id="c391f-116">Obwohl eine- `#Requires` Anweisung in einer Zeile in einem Skript angezeigt werden kann, wirkt sich die Position in einem Skript nicht auf die Abfolge der Anwendung aus.</span><span class="sxs-lookup"><span data-stu-id="c391f-116">Even though a `#Requires` statement can appear on any line in a script, its position in a script does not affect the sequence of its application.</span></span> <span data-ttu-id="c391f-117">Der globale Status, den die- `#Requires` Anweisung darstellt, muss vor der Skriptausführung erfüllt werden.</span><span class="sxs-lookup"><span data-stu-id="c391f-117">The global state the `#Requires` statement presents must be met before script execution.</span></span>

<span data-ttu-id="c391f-118">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="c391f-118">Example:</span></span>

```powershell
Get-Module AzureRM.Netcore | Remove-Module
#Requires -Modules AzureRM.Netcore
```

<span data-ttu-id="c391f-119">Möglicherweise denken Sie daran, dass der obige Code nicht ausgeführt werden sollte, da das erforderliche Modul vor der Anweisung entfernt wurde `#Requires` .</span><span class="sxs-lookup"><span data-stu-id="c391f-119">You might think that the above code shouldn't run because the required module was removed before the `#Requires` statement.</span></span> <span data-ttu-id="c391f-120">Der Zustand muss jedoch `#Requires` erfüllt sein, damit das Skript überhaupt ausgeführt werden kann.</span><span class="sxs-lookup"><span data-stu-id="c391f-120">However, the `#Requires` state had to be met before the script could even execute.</span></span> <span data-ttu-id="c391f-121">Anschließend hat die erste Zeile des Skripts den erforderlichen Zustand ungültig.</span><span class="sxs-lookup"><span data-stu-id="c391f-121">Then the first line of the script invalidated the required state.</span></span>

### <a name="parameters"></a><span data-ttu-id="c391f-122">Parameter</span><span class="sxs-lookup"><span data-stu-id="c391f-122">Parameters</span></span>

#### <a name="-assembly-assembly-path--net-assembly-specification"></a><span data-ttu-id="c391f-123">-Assembly \<Assembly path> |\<.NET assembly specification></span><span class="sxs-lookup"><span data-stu-id="c391f-123">-Assembly \<Assembly path> | \<.NET assembly specification></span></span>

> [!IMPORTANT]
> <span data-ttu-id="c391f-124">Die `-Assembly` Syntax ist veraltet.</span><span class="sxs-lookup"><span data-stu-id="c391f-124">The `-Assembly` syntax is deprecated.</span></span> <span data-ttu-id="c391f-125">Sie dient nicht zur Funktion.</span><span class="sxs-lookup"><span data-stu-id="c391f-125">It serves no function.</span></span> <span data-ttu-id="c391f-126">Die Syntax wurde in PowerShell 5,1 hinzugefügt, aber der unterstützende Code wurde nie implementiert.</span><span class="sxs-lookup"><span data-stu-id="c391f-126">The syntax was added in PowerShell 5.1 but the supporting code was never implemented.</span></span> <span data-ttu-id="c391f-127">Die Syntax wird aus Gründen der Abwärtskompatibilität weiterhin akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="c391f-127">The syntax is still accepted for backward compatibility.</span></span>

<span data-ttu-id="c391f-128">Gibt den Pfad zur DLL-Datei der Assembly oder einen .NET-Assemblynamen an.</span><span class="sxs-lookup"><span data-stu-id="c391f-128">Specifies the path to the assembly DLL file or a .NET assembly name.</span></span> <span data-ttu-id="c391f-129">Der **Assembly** -Parameter wurde in PowerShell 5,0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="c391f-129">The **Assembly** parameter was introduced in PowerShell 5.0.</span></span> <span data-ttu-id="c391f-130">Weitere Informationen zu .NET-Assemblys [](/dotnet/standard/assembly/names)finden Sie unter Assemblynamen.</span><span class="sxs-lookup"><span data-stu-id="c391f-130">For more information about .NET assemblies, see [Assembly names](/dotnet/standard/assembly/names).</span></span>

<span data-ttu-id="c391f-131">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="c391f-131">For example:</span></span>

```
#Requires -Assembly path\to\foo.dll
```

```
#Requires -Assembly "System.Management.Automation, Version=3.0.0.0,
  Culture=neutral, PublicKeyToken=31bf3856ad364e35"
```

#### <a name="-version-nn"></a><span data-ttu-id="c391f-132">-Version \<N\> [. \<n\> ]</span><span class="sxs-lookup"><span data-stu-id="c391f-132">-Version \<N\>[.\<n\>]</span></span>

<span data-ttu-id="c391f-133">Gibt die mindestens erforderliche Version von PowerShell an, die für das Skript erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="c391f-133">Specifies the minimum version of PowerShell that the script requires.</span></span> <span data-ttu-id="c391f-134">Geben Sie eine Hauptversionsnummer und optional eine neben Versionsnummer ein.</span><span class="sxs-lookup"><span data-stu-id="c391f-134">Enter a major version number and optional minor version number.</span></span>

<span data-ttu-id="c391f-135">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="c391f-135">For example:</span></span>

```powershell
#Requires -Version 6.0
```

#### <a name="-pssnapin-pssnapin-name--version-nn"></a><span data-ttu-id="c391f-136">-PSSnapIn \<PSSnapin-Name\> [-Version \<N\> [. \<n\> ]]</span><span class="sxs-lookup"><span data-stu-id="c391f-136">-PSSnapin \<PSSnapin-Name\> [-Version \<N\>[.\<n\>]]</span></span>

<span data-ttu-id="c391f-137">Gibt ein PowerShell-Snap-in an, das für das Skript erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="c391f-137">Specifies a PowerShell snap-in that the script requires.</span></span> <span data-ttu-id="c391f-138">Geben Sie den Snap-in-Namen und eine optionale Versionsnummer ein.</span><span class="sxs-lookup"><span data-stu-id="c391f-138">Enter the snap-in name and an optional version number.</span></span>

<span data-ttu-id="c391f-139">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="c391f-139">For example:</span></span>

```powershell
#Requires -PSSnapin DiskSnapin -Version 1.2
```

#### <a name="-modules-module-name--hashtable"></a><span data-ttu-id="c391f-140">-Module \<Module-Name\> |\<Hashtable\></span><span class="sxs-lookup"><span data-stu-id="c391f-140">-Modules \<Module-Name\> | \<Hashtable\></span></span>

<span data-ttu-id="c391f-141">Gibt die PowerShell-Module an, die das Skript erfordert.</span><span class="sxs-lookup"><span data-stu-id="c391f-141">Specifies PowerShell modules that the script requires.</span></span> <span data-ttu-id="c391f-142">Geben Sie den Modulnamen und eine optionale Versionsnummer ein.</span><span class="sxs-lookup"><span data-stu-id="c391f-142">Enter the module name and an optional version number.</span></span>

<span data-ttu-id="c391f-143">Wenn die erforderlichen Module nicht in der aktuellen Sitzung sind, importiert PowerShell Sie.</span><span class="sxs-lookup"><span data-stu-id="c391f-143">If the required modules aren't in the current session, PowerShell imports them.</span></span>
<span data-ttu-id="c391f-144">Wenn die Module nicht importiert werden können, löst PowerShell einen Fehler mit Abbruch aus.</span><span class="sxs-lookup"><span data-stu-id="c391f-144">If the modules can't be imported, PowerShell throws a terminating error.</span></span>

<span data-ttu-id="c391f-145">Geben Sie für jedes Modul den Modulnamen ( \<String\> ) oder eine Hash Tabelle ein.</span><span class="sxs-lookup"><span data-stu-id="c391f-145">For each module, type the module name (\<String\>) or a hash table.</span></span> <span data-ttu-id="c391f-146">Der Wert kann eine Kombination aus Zeichen folgen und Hash Tabellen sein.</span><span class="sxs-lookup"><span data-stu-id="c391f-146">The value can be a combination of strings and hash tables.</span></span> <span data-ttu-id="c391f-147">Die Hash Tabelle verfügt über die folgenden Schlüssel.</span><span class="sxs-lookup"><span data-stu-id="c391f-147">The hash table has the following keys.</span></span>

- <span data-ttu-id="c391f-148">`ModuleName` - **Erforderlich** Gibt den Namen des Moduls an.</span><span class="sxs-lookup"><span data-stu-id="c391f-148">`ModuleName` - **Required** Specifies the module name.</span></span>
- <span data-ttu-id="c391f-149">`GUID` - **Optional** Gibt die GUID des Moduls an.</span><span class="sxs-lookup"><span data-stu-id="c391f-149">`GUID` - **Optional** Specifies the GUID of the module.</span></span>
- <span data-ttu-id="c391f-150">Es ist auch **erforderlich** , einen der drei folgenden Schlüssel anzugeben.</span><span class="sxs-lookup"><span data-stu-id="c391f-150">It's also **Required** to specify one of the three below keys.</span></span> <span data-ttu-id="c391f-151">Diese Schlüssel können nicht gleichzeitig verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="c391f-151">These keys can't be used together.</span></span>
  - <span data-ttu-id="c391f-152">`ModuleVersion` : Gibt eine zulässige Mindestversion des Moduls an.</span><span class="sxs-lookup"><span data-stu-id="c391f-152">`ModuleVersion` - Specifies a minimum acceptable version of the module.</span></span>
  - <span data-ttu-id="c391f-153">`RequiredVersion` : Gibt eine exakte, erforderliche Version des Moduls an.</span><span class="sxs-lookup"><span data-stu-id="c391f-153">`RequiredVersion` - Specifies an exact, required version of the module.</span></span>
  - <span data-ttu-id="c391f-154">`MaximumVersion` : Gibt die maximal zulässige Version des Moduls an.</span><span class="sxs-lookup"><span data-stu-id="c391f-154">`MaximumVersion` - Specifies the maximum acceptable version of the module.</span></span>

> [!NOTE]
> <span data-ttu-id="c391f-155">`RequiredVersion` wurde in Windows PowerShell 5,0 hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="c391f-155">`RequiredVersion` was added in Windows PowerShell 5.0.</span></span>
> <span data-ttu-id="c391f-156">`MaximumVersion` wurde in Windows PowerShell 5,1 hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="c391f-156">`MaximumVersion` was added in Windows PowerShell 5.1.</span></span>

<span data-ttu-id="c391f-157">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="c391f-157">For example:</span></span>

<span data-ttu-id="c391f-158">Erfordert, dass `AzureRM.Netcore` (Version `0.12.0` oder höher) installiert ist.</span><span class="sxs-lookup"><span data-stu-id="c391f-158">Require that `AzureRM.Netcore` (version `0.12.0` or greater) is installed.</span></span>

```powershell
#Requires -Modules @{ ModuleName="AzureRM.Netcore"; ModuleVersion="0.12.0" }
```

<span data-ttu-id="c391f-159">Erfordert, dass `AzureRM.Netcore` (**nur** Version `0.12.0` ) installiert ist.</span><span class="sxs-lookup"><span data-stu-id="c391f-159">Require that `AzureRM.Netcore` (**only** version `0.12.0`) is installed.</span></span>

```powershell
#Requires -Modules @{ ModuleName="AzureRM.Netcore"; RequiredVersion="0.12.0" }
```

<span data-ttu-id="c391f-160">Erfordert, dass `AzureRM.Netcore` (Version `0.12.0` oder weniger) installiert ist.</span><span class="sxs-lookup"><span data-stu-id="c391f-160">Requires that `AzureRM.Netcore` (version `0.12.0` or lesser) is installed.</span></span>

```powershell
#Requires -Modules @{ ModuleName="AzureRM.Netcore"; MaximumVersion="0.12.0" }
```

<span data-ttu-id="c391f-161">Erfordert, dass eine beliebige Version von `AzureRM.Netcore` und `PowerShellGet` installiert ist.</span><span class="sxs-lookup"><span data-stu-id="c391f-161">Require that any version of `AzureRM.Netcore` and `PowerShellGet` is installed.</span></span>

```powershell
#Requires -Modules AzureRM.Netcore, PowerShellGet
```

<span data-ttu-id="c391f-162">Wenn Sie den `RequiredVersion` Schlüssel verwenden, stellen Sie sicher, dass die Versions Zeichenfolge exakt der benötigten Versions Zeichenfolge entspricht</span><span class="sxs-lookup"><span data-stu-id="c391f-162">When using the `RequiredVersion` key, ensure your version string exactly matches the version string you require.</span></span>

```powershell
Get-Module AzureRM.Netcore -ListAvailable
```

```Output
    Directory: /home/azureuser/.local/share/powershell/Modules

ModuleType Version Name            PSEdition ExportedCommands
---------- ------- ----            --------- ----------------
Script     0.12.0  AzureRM.Netcore Core
```

<span data-ttu-id="c391f-163">Das folgende Beispiel schlägt fehl, da **0,12** nicht exakt mit **0.12.0** übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="c391f-163">The following example fails because **0.12** doesn't exactly match **0.12.0**.</span></span>

```powershell
#Requires -Modules @{ ModuleName="AzureRM.Netcore"; RequiredVersion="0.12" }
```

#### <a name="-psedition-psedition-name"></a><span data-ttu-id="c391f-164">-P\* dition \<PSEdition-Name\></span><span class="sxs-lookup"><span data-stu-id="c391f-164">-PSEdition \<PSEdition-Name\></span></span>

<span data-ttu-id="c391f-165">Gibt eine PowerShell-Edition an, die für das Skript erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="c391f-165">Specifies a PowerShell edition that the script requires.</span></span> <span data-ttu-id="c391f-166">Gültige Werte sind **Core** für PowerShell Core und **Desktop** für Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c391f-166">Valid values are **Core** for PowerShell Core and **Desktop** for Windows PowerShell.</span></span>

<span data-ttu-id="c391f-167">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="c391f-167">For example:</span></span>

```powershell
#Requires -PSEdition Core
```

#### <a name="-shellid"></a><span data-ttu-id="c391f-168">-Shellid</span><span class="sxs-lookup"><span data-stu-id="c391f-168">-ShellId</span></span>

<span data-ttu-id="c391f-169">Gibt die Shell an, die für das Skript erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="c391f-169">Specifies the shell that the script requires.</span></span> <span data-ttu-id="c391f-170">Geben Sie die Shell-ID ein.</span><span class="sxs-lookup"><span data-stu-id="c391f-170">Enter the shell ID.</span></span> <span data-ttu-id="c391f-171">Wenn Sie den **shellid-** Parameter verwenden, müssen Sie auch den **PSSnapIn** -Parameter einschließen.</span><span class="sxs-lookup"><span data-stu-id="c391f-171">If you use the **ShellId** parameter, you must also include the **PSSnapin** parameter.</span></span>
<span data-ttu-id="c391f-172">Sie können die aktuelle **shellid** ermitteln, indem Sie die `$ShellId` Automatische Variable Abfragen.</span><span class="sxs-lookup"><span data-stu-id="c391f-172">You can find the current **ShellId** by querying the `$ShellId` automatic variable.</span></span>

<span data-ttu-id="c391f-173">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="c391f-173">For example:</span></span>

```powershell
#Requires -ShellId MyLocalShell -PSSnapin Microsoft.PowerShell.Core
```

> [!NOTE]
> <span data-ttu-id="c391f-174">Dieser Parameter ist für die Verwendung in Mini Shells vorgesehen, die veraltet sind.</span><span class="sxs-lookup"><span data-stu-id="c391f-174">This parameter is intended for use in mini-shells, which have been deprecated.</span></span>

#### <a name="-runasadministrator"></a><span data-ttu-id="c391f-175">-Runasadministrator</span><span class="sxs-lookup"><span data-stu-id="c391f-175">-RunAsAdministrator</span></span>

<span data-ttu-id="c391f-176">Wenn dieser Switch-Parameter der-Anweisung hinzugefügt wird `#Requires` , gibt er an, dass die PowerShell-Sitzung, in der das Skript ausgeführt wird, mit erhöhten Benutzerrechten gestartet werden muss.</span><span class="sxs-lookup"><span data-stu-id="c391f-176">When this switch parameter is added to your `#Requires` statement, it specifies that the PowerShell session in which you're running the script must be started with elevated user rights.</span></span> <span data-ttu-id="c391f-177">Der Parameter **runasadministrator** wird bei einem nicht-Windows-Betriebssystem ignoriert.</span><span class="sxs-lookup"><span data-stu-id="c391f-177">The **RunAsAdministrator** parameter is ignored on a non-Windows operating system.</span></span> <span data-ttu-id="c391f-178">Der **runasadministrator** -Parameter wurde in PowerShell 4,0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="c391f-178">The **RunAsAdministrator** parameter was introduced in PowerShell 4.0.</span></span>

<span data-ttu-id="c391f-179">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="c391f-179">For example:</span></span>

```powershell
#Requires -RunAsAdministrator
```

### <a name="examples"></a><span data-ttu-id="c391f-180">Beispiele</span><span class="sxs-lookup"><span data-stu-id="c391f-180">Examples</span></span>

<span data-ttu-id="c391f-181">Das folgende Skript verfügt über zwei- `#Requires` Anweisungen.</span><span class="sxs-lookup"><span data-stu-id="c391f-181">The following script has two `#Requires` statements.</span></span> <span data-ttu-id="c391f-182">Wenn die in beiden Anweisungen angegebenen Anforderungen nicht erfüllt sind, wird das Skript nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="c391f-182">If the requirements specified in both statements aren't met, the script doesn't run.</span></span> <span data-ttu-id="c391f-183">Jede `#Requires` Anweisung muss das erste Element in einer Zeile sein:</span><span class="sxs-lookup"><span data-stu-id="c391f-183">Each `#Requires` statement must be the first item on a line:</span></span>

```powershell
#Requires -Modules AzureRM.Netcore
#Requires -Version 6.0
Param
(
    [parameter(Mandatory=$true)]
    [String[]]
    $Path
)
...
```

## <a name="see-also"></a><span data-ttu-id="c391f-184">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c391f-184">See also</span></span>

[<span data-ttu-id="c391f-185">about_Automatic_Variables</span><span class="sxs-lookup"><span data-stu-id="c391f-185">about_Automatic_Variables</span></span>](about_Automatic_Variables.md)

[<span data-ttu-id="c391f-186">about_Language_Keywords</span><span class="sxs-lookup"><span data-stu-id="c391f-186">about_Language_Keywords</span></span>](about_Language_Keywords.md)