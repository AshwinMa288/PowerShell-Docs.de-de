---
title: Neuerungen in PowerShell 7.0
description: In PowerShell 7.0 veröffentlichte neue Features und Änderungen
ms.date: 03/04/2020
ms.openlocfilehash: 3a5a1aaa0bd9dd1e0df7d6f5e6021678ed21dce4
ms.sourcegitcommit: 39c2a697228276d5dae39e540995fa479c2b5f39
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/05/2020
ms.locfileid: "93355271"
---
# <a name="whats-new-in-powershell-70"></a><span data-ttu-id="56a08-103">Neuerungen in PowerShell 7.0</span><span class="sxs-lookup"><span data-stu-id="56a08-103">What's New in PowerShell 7.0</span></span>

<span data-ttu-id="56a08-104">PowerShell 7.0 ist eine plattformübergreifende Open-Source-Edition (Windows, macOS und Linux) von PowerShell, die für die Verwaltung heterogener Umgebungen und Hybrid Clouds entwickelt wurde.</span><span class="sxs-lookup"><span data-stu-id="56a08-104">PowerShell 7.0 is an open-source, cross-platform (Windows, macOS, and Linux) edition of PowerShell, built to manage heterogeneous environments and hybrid cloud.</span></span>

<span data-ttu-id="56a08-105">In diesem Release haben wir eine Reihe neuer Features eingeführt, einschließlich:</span><span class="sxs-lookup"><span data-stu-id="56a08-105">In this release, we're introducing a number of new features, including:</span></span>

- <span data-ttu-id="56a08-106">Parallelisierung von Pipelines mit `ForEach-Object -Parallel`</span><span class="sxs-lookup"><span data-stu-id="56a08-106">Pipeline parallelization with `ForEach-Object -Parallel`</span></span>
- <span data-ttu-id="56a08-107">Neue Operatoren:</span><span class="sxs-lookup"><span data-stu-id="56a08-107">New operators:</span></span>
  - <span data-ttu-id="56a08-108">Ternärer Operator: `a ? b : c`</span><span class="sxs-lookup"><span data-stu-id="56a08-108">Ternary operator: `a ? b : c`</span></span>
  - <span data-ttu-id="56a08-109">Pipeline-Kettenoperatoren: `||` und `&&`</span><span class="sxs-lookup"><span data-stu-id="56a08-109">Pipeline chain operators: `||` and `&&`</span></span>
  - <span data-ttu-id="56a08-110">Bedingte NULL-Operatoren: `??` und `??=`</span><span class="sxs-lookup"><span data-stu-id="56a08-110">Null conditional operators: `??` and `??=`</span></span>
- <span data-ttu-id="56a08-111">Eine vereinfachte und dynamische Fehleransicht und das Cmdlet `Get-Error` für eine einfachere Untersuchung von Fehlern</span><span class="sxs-lookup"><span data-stu-id="56a08-111">A simplified and dynamic error view and `Get-Error` cmdlet for easier investigation of errors</span></span>
- <span data-ttu-id="56a08-112">Eine Kompatibilitätsebene, die es Benutzern ermöglicht, Module in eine implizite Windows PowerShell-Sitzung zu importieren</span><span class="sxs-lookup"><span data-stu-id="56a08-112">A compatibility layer that enables users to import modules in an implicit Windows PowerShell session</span></span>
- <span data-ttu-id="56a08-113">Automatische Benachrichtigung zu neuen Versionen</span><span class="sxs-lookup"><span data-stu-id="56a08-113">Automatic new version notifications</span></span>
- <span data-ttu-id="56a08-114">Die Möglichkeit zum direkten Aufrufen von DSC-Ressourcen in PowerShell 7 (experimentell)</span><span class="sxs-lookup"><span data-stu-id="56a08-114">The ability to invoke DSC resources directly from PowerShell 7 (experimental)</span></span>

<span data-ttu-id="56a08-115">Eine vollständige Liste der Features und Korrekturen finden Sie in den [Änderungsprotokollen](https://github.com/PowerShell/PowerShell/blob/master/CHANGELOG/7.0.md).</span><span class="sxs-lookup"><span data-stu-id="56a08-115">To see a full list of features and fixes, see the [changelogs](https://github.com/PowerShell/PowerShell/blob/master/CHANGELOG/7.0.md).</span></span>

## <a name="where-can-i-install-powershell"></a><span data-ttu-id="56a08-116">Wo kann ich PowerShell installieren?</span><span class="sxs-lookup"><span data-stu-id="56a08-116">Where can I install PowerShell?</span></span>

<span data-ttu-id="56a08-117">PowerShell 7 unterstützt derzeit die folgenden x64-Betriebssysteme:</span><span class="sxs-lookup"><span data-stu-id="56a08-117">PowerShell 7 currently supports the following operating systems on x64, including:</span></span>

- <span data-ttu-id="56a08-118">Windows 8.1 und 10</span><span class="sxs-lookup"><span data-stu-id="56a08-118">Windows 8.1, and 10</span></span>
- <span data-ttu-id="56a08-119">Windows Server 2012, 2012 R2, 2016, und 2019</span><span class="sxs-lookup"><span data-stu-id="56a08-119">Windows Server 2012, 2012 R2, 2016, and 2019</span></span>
- <span data-ttu-id="56a08-120">macOS ab 10.13</span><span class="sxs-lookup"><span data-stu-id="56a08-120">macOS 10.13+</span></span>
- <span data-ttu-id="56a08-121">Red Hat Enterprise Linux (RHEL)/CentOS 7</span><span class="sxs-lookup"><span data-stu-id="56a08-121">Red Hat Enterprise Linux (RHEL) / CentOS 7</span></span>
- <span data-ttu-id="56a08-122">Fedora ab 30</span><span class="sxs-lookup"><span data-stu-id="56a08-122">Fedora 30+</span></span>
- <span data-ttu-id="56a08-123">Debian 9</span><span class="sxs-lookup"><span data-stu-id="56a08-123">Debian 9</span></span>
- <span data-ttu-id="56a08-124">Ubuntu LTS ab 16.04</span><span class="sxs-lookup"><span data-stu-id="56a08-124">Ubuntu LTS 16.04+</span></span>
- <span data-ttu-id="56a08-125">Alpine Linux ab 3.8</span><span class="sxs-lookup"><span data-stu-id="56a08-125">Alpine Linux 3.8+</span></span>

<span data-ttu-id="56a08-126">Zusätzlich unterstützt PowerShell 7.0 die ARM32- und ARM64-Varianten von Debian, Ubuntu und ARM64 Alpine Linux.</span><span class="sxs-lookup"><span data-stu-id="56a08-126">Additionally, PowerShell 7.0 supports ARM32 and ARM64 flavors of Debian, Ubuntu, and ARM64 Alpine Linux.</span></span>

<span data-ttu-id="56a08-127">Prüfen Sie die Installationsanweisungen für Ihr bevorzugtes Betriebssystem: [Windows](/powershell/scripting/install/installing-powershell-core-on-windows), [macOS](/powershell/scripting/install/installing-powershell-core-on-macos) oder [Linux](/powershell/scripting/install/installing-powershell-core-on-linux).</span><span class="sxs-lookup"><span data-stu-id="56a08-127">Check the installation instructions for your preferred operating system [Windows](/powershell/scripting/install/installing-powershell-core-on-windows), [macOS](/powershell/scripting/install/installing-powershell-core-on-macos), or [Linux](/powershell/scripting/install/installing-powershell-core-on-linux).</span></span>

<span data-ttu-id="56a08-128">Wenngleich nicht offiziell unterstützt, hat die Community auch Pakete für [Arch](https://aur.archlinux.org/packages/powershell/) und Kali Linux bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="56a08-128">While not officially supported, the community has also provided packages for [Arch](https://aur.archlinux.org/packages/powershell/) and Kali Linux.</span></span>

> [!NOTE]
> <span data-ttu-id="56a08-129">Debian 10 und CentOS 8 unterstützen zurzeit nicht WinRM-Remoting.</span><span class="sxs-lookup"><span data-stu-id="56a08-129">Debian 10 and CentOS 8 currently do not support WinRM remoting.</span></span> <span data-ttu-id="56a08-130">Einzelheiten zum Einrichten von SSH-basiertem Remoting finden Sie unter [PowerShell-Remoting über SSH](/powershell/scripting/learn/remoting/ssh-remoting-in-powershell-core).</span><span class="sxs-lookup"><span data-stu-id="56a08-130">For details on setting up SSH-based remoting, see [PowerShell Remoting over SSH](/powershell/scripting/learn/remoting/ssh-remoting-in-powershell-core).</span></span>

<span data-ttu-id="56a08-131">Weitere aktuelle Informationen zu unterstützten Betriebssystemen und zum Supportlebenszyklus finden Sie unter [PowerShell-Supportlebenszyklus](/powershell/scripting/powershell-support-lifecycle).</span><span class="sxs-lookup"><span data-stu-id="56a08-131">For more up-to-date information about supported operating systems and support lifecycle, see the [PowerShell Support Lifecycle](/powershell/scripting/powershell-support-lifecycle).</span></span>

## <a name="running-powershell-7"></a><span data-ttu-id="56a08-132">Ausführen von PowerShell 7</span><span class="sxs-lookup"><span data-stu-id="56a08-132">Running PowerShell 7</span></span>

<span data-ttu-id="56a08-133">PowerShell 7 wird in ein Verzeichnis getrennt von Windows PowerShell installiert.</span><span class="sxs-lookup"><span data-stu-id="56a08-133">PowerShell 7 installs to a directory seperately from Windows PowerShell.</span></span>
<span data-ttu-id="56a08-134">Dadurch wird ermöglicht, PowerShell 7 parallel mit Windows PowerShell 5.1 zu nutzen.</span><span class="sxs-lookup"><span data-stu-id="56a08-134">This enables you to run PowerShell 7 side-by-side with Windows PowerShell 5.1.</span></span> <span data-ttu-id="56a08-135">Für PowerShell Core 6.x ist PowerShell 7 ein direktes Upgrade, durch das PowerShell Core 6.x entfernt wird.</span><span class="sxs-lookup"><span data-stu-id="56a08-135">For PowerShell Core 6.x, PowerShell 7 is an in-place upgrade that removes PowerShell Core 6.x.</span></span>

- <span data-ttu-id="56a08-136">PowerShell 7 wird in `%programfiles%\PowerShell\7` installiert.</span><span class="sxs-lookup"><span data-stu-id="56a08-136">PowerShell 7 is installed to `%programfiles%\PowerShell\7`</span></span>
- <span data-ttu-id="56a08-137">Der Ordner `%programfiles%\PowerShell\7` wird `$env:PATH` hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="56a08-137">The `%programfiles%\PowerShell\7` folder is added to `$env:PATH`</span></span>

<span data-ttu-id="56a08-138">Das Installationsprogramm von PowerShell 7 aktualisiert frühere Versionen von PowerShell Core 6.x:</span><span class="sxs-lookup"><span data-stu-id="56a08-138">The PowerShell 7 installer package upgrades previous versions of PowerShell Core 6.x:</span></span>

- <span data-ttu-id="56a08-139">PowerShell Core 6. x unter Windows: `%programfiles%\PowerShell\6` wird durch `%programfiles%\PowerShell\7` ersetzt.</span><span class="sxs-lookup"><span data-stu-id="56a08-139">PowerShell Core 6.x on Windows: `%programfiles%\PowerShell\6` is replaced by `%programfiles%\PowerShell\7`</span></span>
- <span data-ttu-id="56a08-140">Linux: `/opt/microsoft/powershell/6` wird durch `/opt/microsoft/powershell/7` ersetzt.</span><span class="sxs-lookup"><span data-stu-id="56a08-140">Linux: `/opt/microsoft/powershell/6` is replaced by `/opt/microsoft/powershell/7`</span></span>
- <span data-ttu-id="56a08-141">macOS: `/usr/local/microsoft/powershell/6` wird durch `/usr/local/microsoft/powershell/7` ersetzt.</span><span class="sxs-lookup"><span data-stu-id="56a08-141">macOS: `/usr/local/microsoft/powershell/6` is replaced by `/usr/local/microsoft/powershell/7`</span></span>

> [!NOTE]
> <span data-ttu-id="56a08-142">In Windows PowerShell heißt die ausführbare Datei zum Starten von PowerShell `powershell.exe`.</span><span class="sxs-lookup"><span data-stu-id="56a08-142">In Windows PowerShell, the executable to launch PowerShell is named `powershell.exe`.</span></span> <span data-ttu-id="56a08-143">Ab Version 6 wurde der Name der ausführbaren Datei so geändert, dass die parallele Ausführung unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="56a08-143">In version 6 and above, the executable name is changed to support side-by-side execution.</span></span> <span data-ttu-id="56a08-144">Der neue Name der ausführbaren Datei zum Starten von PowerShell 7 ist `pwsh.exe`.</span><span class="sxs-lookup"><span data-stu-id="56a08-144">The new executable name to launch PowerShell 7 is `pwsh.exe`.</span></span> <span data-ttu-id="56a08-145">Vorschaubuilds bleiben als `pwsh-preview` anstelle von `pwsh` im Verzeichnis „7-preview“ erhalten.</span><span class="sxs-lookup"><span data-stu-id="56a08-145">Preview builds remain in-place as `pwsh-preview` instead of `pwsh` under the 7-preview directory.</span></span>

## <a name="improved-backwards-compatibility-with-windows-powershell"></a><span data-ttu-id="56a08-146">Verbesserte Abwärtskompatibilität mit Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="56a08-146">Improved backwards compatibility with Windows PowerShell</span></span>

<span data-ttu-id="56a08-147">PowerShell 7.0 markiert einen Wechsel zu .NET Core 3.1, wodurch eine wesentlich bessere Abwärtskompatibilität mit vorhandenen Windows PowerShell-Modulen ermöglicht wird.</span><span class="sxs-lookup"><span data-stu-id="56a08-147">PowerShell 7.0 marks a move a to .NET Core 3.1, enabling significantly more backwards compatibility with existing Windows PowerShell modules.</span></span> <span data-ttu-id="56a08-148">Dazu gehören viele Module unter Windows, die GUI-Funktionalität benötigen, wie `Out-GridView` und `Show-Command`, sowie viele Rollenverwaltungsmodule, die Teil von Windows sind.</span><span class="sxs-lookup"><span data-stu-id="56a08-148">This includes many modules on Windows that require GUI functionality like `Out-GridView` and `Show-Command`, as well as many role management modules that ship as part of Windows.</span></span>

<span data-ttu-id="56a08-149">Für Windows wurde `Import-Module` der neue Schalterparameter **UseWindowsPowerShell** hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="56a08-149">For Windows, a new switch parameter **UseWindowsPowerShell** is added to `Import-Module`.</span></span> <span data-ttu-id="56a08-150">Dieser Schalter erstellt in PowerShell 7 ein Proxymodul, das einen lokalen Windows PowerShell-Prozess verwendet, um alle in diesem Modul enthaltenen Cmdlets implizit auszuführen.</span><span class="sxs-lookup"><span data-stu-id="56a08-150">This switch creates a proxy module in PowerShell 7 that uses a local Windows PowerShell process to implicitly run any cmdlets contained in that module.</span></span> <span data-ttu-id="56a08-151">Weitere Informationen finden Sie unter [Import-Module](/powershell/module/microsoft.powershell.core/import-module?view=powershell-7&preserve-view=true).</span><span class="sxs-lookup"><span data-stu-id="56a08-151">For more information on [Import-Module](/powershell/module/microsoft.powershell.core/import-module?view=powershell-7&preserve-view=true).</span></span>

<span data-ttu-id="56a08-152">Weitere Informationen dazu, welche Microsoft-Module mit PowerShell 7.0 funktionieren, finden Sie in der [Tabelle zur Modulkompatibilität](https://aka.ms/PSModuleCompat).</span><span class="sxs-lookup"><span data-stu-id="56a08-152">For more information on which Microsoft modules work with PowerShell 7.0, see the [Module Compatibility Table](https://aka.ms/PSModuleCompat).</span></span>

## <a name="parallel-execution-added-to-foreach-object"></a><span data-ttu-id="56a08-153">Parallele Ausführung zu ForEach-Object hinzugefügt</span><span class="sxs-lookup"><span data-stu-id="56a08-153">Parallel execution added to ForEach-Object</span></span>

<span data-ttu-id="56a08-154">Das Cmdlet `ForEach-Object`, das Elemente in einer Sammlung iteriert, zeichnet sich nun dank des neuen Parameters **Parallel** durch integrierte Parallelität aus.</span><span class="sxs-lookup"><span data-stu-id="56a08-154">The `ForEach-Object` cmdlet, which iterates items in a collection, now has built-in parallelism with the new **Parallel** parameter.</span></span>

<span data-ttu-id="56a08-155">Standardmäßig verwenden parallele Skriptblöcke das aktuelle Arbeitsverzeichnis des Aufrufers, der die parallelen Aufgaben gestartet hat.</span><span class="sxs-lookup"><span data-stu-id="56a08-155">By default, parallel script blocks use the current working directory of the caller that started the parallel tasks.</span></span>

<span data-ttu-id="56a08-156">In diesem Beispiel werden 50.000 Protokolleinträge aus 5 Systemprotokollen auf einem lokalen Windows-Computer abgerufen:</span><span class="sxs-lookup"><span data-stu-id="56a08-156">This example retrieves 50,000 log entries from 5 system logs on a local Windows machine:</span></span>

```powershell
$logNames = 'Security','Application','System','Windows PowerShell','Microsoft-Windows-Store/Operational'

$logEntries = $logNames | ForEach-Object -Parallel {
    Get-WinEvent -LogName $_ -MaxEvents 10000
} -ThrottleLimit 5

$logEntries.Count

50000
```

<span data-ttu-id="56a08-157">Der Parameter **Parallel** gibt den Skriptblock an, der für jeden Eingabeprotokollnamen parallel ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="56a08-157">The **Parallel** parameter specifies the script block that is run in parallel for each input log name.</span></span>

<span data-ttu-id="56a08-158">Der neue Parameter **ThrottleLimit** begrenzt die Anzahl der zu einer bestimmten Zeit parallel ausgeführten Skriptblöcke.</span><span class="sxs-lookup"><span data-stu-id="56a08-158">The new **ThrottleLimit** parameter limits the number of script blocks running in parallel at a given time.</span></span> <span data-ttu-id="56a08-159">Der Standardwert ist 5.</span><span class="sxs-lookup"><span data-stu-id="56a08-159">The default is 5.</span></span>

<span data-ttu-id="56a08-160">Verwenden Sie die Variable `$_`, um das aktuelle Eingabeobjekt im Skriptblock darzustellen.</span><span class="sxs-lookup"><span data-stu-id="56a08-160">Use the `$_` variable to represent the current input object in the script block.</span></span> <span data-ttu-id="56a08-161">Verwenden Sie den Bereich `$using:`, um Variablenverweise an den ausgeführten Skriptblock zu übergeben.</span><span class="sxs-lookup"><span data-stu-id="56a08-161">Use the `$using:` scope to pass variable references to the running script block.</span></span>

<span data-ttu-id="56a08-162">Weitere Informationen finden Sie unter [ForEach-Object](/powershell/module/microsoft.powershell.core/foreach-object?view=powershell-7&preserve-view=true).</span><span class="sxs-lookup"><span data-stu-id="56a08-162">For more information about [ForEach-Object](/powershell/module/microsoft.powershell.core/foreach-object?view=powershell-7&preserve-view=true).</span></span>

## <a name="ternary-operator"></a><span data-ttu-id="56a08-163">Ternärer Operator</span><span class="sxs-lookup"><span data-stu-id="56a08-163">Ternary operator</span></span>

<span data-ttu-id="56a08-164">PowerShell 7.0 führt einen ternären Operator ein, der sich wie eine vereinfachte `if-else`-Anweisung verhält.</span><span class="sxs-lookup"><span data-stu-id="56a08-164">PowerShell 7.0 introduces a ternary operator which behaves like a simplified `if-else` statement.</span></span>
<span data-ttu-id="56a08-165">Der ternäre Operator von PowerShell ist eng an die Syntax des ternären Operators in C# angelehnt:</span><span class="sxs-lookup"><span data-stu-id="56a08-165">PowerShell's ternary operator is closely modeled from the C# ternary operator syntax:</span></span>

```
<condition> ? <if-true> : <if-false>
```

<span data-ttu-id="56a08-166">Der Bedingungsausdruck wird stets ausgewertet und sein Ergebnis in einen **booleschen Wert** konvertiert, um zu bestimmen, welcher Zweig als Nächstes ausgewertet wird:</span><span class="sxs-lookup"><span data-stu-id="56a08-166">The condition-expression is always evaluated and its result converted to a **Boolean** to determine which branch is evaluated next:</span></span>

- <span data-ttu-id="56a08-167">Der Ausdruck `<if-true>` wird ausgeführt, wenn der Ausdruck `<condition>` TRUE ist.</span><span class="sxs-lookup"><span data-stu-id="56a08-167">The `<if-true>` expression is executed if the `<condition>` expression is true</span></span>
- <span data-ttu-id="56a08-168">Der Ausdruck `<if-false>` wird ausgeführt, wenn der Ausdruck `<condition>` FALSE ist.</span><span class="sxs-lookup"><span data-stu-id="56a08-168">The `<if-false>` expression is executed if the `<condition>` expression is false</span></span>

<span data-ttu-id="56a08-169">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="56a08-169">For example:</span></span>

```powershell
$message = (Test-Path $path) ? "Path exists" : "Path not found"
```

<span data-ttu-id="56a08-170">Wenn in diesem Beispiel der Pfad vorhanden ist, wird **Pfad vorhanden** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="56a08-170">In this example, if the path exists, then **Path exists** is displayed.</span></span> <span data-ttu-id="56a08-171">Wenn der Pfad nicht vorhanden ist, wird **Pfad nicht gefunden** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="56a08-171">If the path does not exist, then **Path not found** is displayed.</span></span>

<span data-ttu-id="56a08-172">Weitere Informationen finden Sie unter [Informationen zu „If“](/powershell/module/microsoft.powershell.core/about/about_if).</span><span class="sxs-lookup"><span data-stu-id="56a08-172">For more information [About If](/powershell/module/microsoft.powershell.core/about/about_if).</span></span>

## <a name="pipeline-chain-operators"></a><span data-ttu-id="56a08-173">Pipeline-Kettenoperatoren</span><span class="sxs-lookup"><span data-stu-id="56a08-173">Pipeline chain operators</span></span>

<span data-ttu-id="56a08-174">PowerShell 7 implementiert die Operatoren `&&` und `||`, um Pipelines bedingt zu verketten.</span><span class="sxs-lookup"><span data-stu-id="56a08-174">PowerShell 7 implements the `&&` and `||` operators to conditionally chain pipelines.</span></span> <span data-ttu-id="56a08-175">Diese Operatoren werden in PowerShell als „Pipeline-Kettenoperatoren“ bezeichnet und ähneln AND- und OR-Listen in Shells wie **Bash** und **Zsh** sowie bedingten Verarbeitungssymbolen in der Windows-Befehlsshell ( **cmd.exe** ).</span><span class="sxs-lookup"><span data-stu-id="56a08-175">These operators are known in PowerShell as "pipeline chain operators", and are similar to AND and OR lists in shells like **Bash** and **Zsh** , as well as conditional processing symbols in the Windows Command Shell ( **cmd.exe** ).</span></span>

<span data-ttu-id="56a08-176">Der Operator `&&` führt die rechte Pipeline aus, wenn die linke Pipeline erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="56a08-176">The `&&` operator executes the right-hand pipeline, if the left-hand pipeline succeeded.</span></span> <span data-ttu-id="56a08-177">Dagegen führt der Operator `||` die rechte Pipeline aus, wenn die linke Pipeline fehlgeschlagen ist.</span><span class="sxs-lookup"><span data-stu-id="56a08-177">Conversely, the `||` operator executes the right-hand pipeline if the left-hand pipeline failed.</span></span>

> [!NOTE]
> <span data-ttu-id="56a08-178">Diese Operatoren verwenden die Variablen `$?` und `$LASTEXITCODE`, um zu bestimmen, ob eine Pipeline fehlgeschlagen ist.</span><span class="sxs-lookup"><span data-stu-id="56a08-178">These operators use the `$?` and `$LASTEXITCODE` variables to determine if a pipeline failed.</span></span> <span data-ttu-id="56a08-179">Dadurch können Sie sie mit nativen Befehlen und nicht bloß mit Cmdlets oder Funktionen verwenden.</span><span class="sxs-lookup"><span data-stu-id="56a08-179">This allows you to use them with native commands and not just with cmdlets or functions.</span></span>

<span data-ttu-id="56a08-180">Hier ist der erste Befehl erfolgreich, und der zweite Befehl wird ausgeführt:</span><span class="sxs-lookup"><span data-stu-id="56a08-180">Here, the first command succeeds and the second command is executed:</span></span>

```powershell
Write-Output 'First' && Write-Output 'Second'
```

```Output
First
Second
```

<span data-ttu-id="56a08-181">Hier schlägt der erste Befehl fehl, der zweite wird nicht ausgeführt:</span><span class="sxs-lookup"><span data-stu-id="56a08-181">Here, the first command fails, the second is not executed:</span></span>

```powershell
Write-Error 'Bad' && Write-Output 'Second'
```

```Output
Write-Error: Bad
```

<span data-ttu-id="56a08-182">Hier ist der erste Befehl erfolgreich, der zweite Befehl wird nicht ausgeführt:</span><span class="sxs-lookup"><span data-stu-id="56a08-182">Here, the first command succeeds, the second command is not executed:</span></span>

```powershell
Write-Output 'First' || Write-Output 'Second'
```

```Output
First
```

<span data-ttu-id="56a08-183">Hier schlägt der erste Befehl fehl, sodass der zweite Befehl ausgeführt wird:</span><span class="sxs-lookup"><span data-stu-id="56a08-183">Here, the first command fails, so the second command is executed:</span></span>

```powershell
Write-Error 'Bad' || Write-Output 'Second'
```

```Output
Write-Error 'Bad'
Second
```

<span data-ttu-id="56a08-184">Weitere Informationen zu finden Sie unter [Informationen zu Pipeline-Kettenoperatoren](/powershell/module/microsoft.powershell.core/about/about_pipeline_chain_operators?view=powershell-7&preserve-view=true).</span><span class="sxs-lookup"><span data-stu-id="56a08-184">For more information [About Pipeline Chain Operators](/powershell/module/microsoft.powershell.core/about/about_pipeline_chain_operators?view=powershell-7&preserve-view=true).</span></span>

## <a name="null-coalescing-assignment-and-conditional-operators"></a><span data-ttu-id="56a08-185">NULL-Sammeloperator, Zuweisung und bedingte Operatoren</span><span class="sxs-lookup"><span data-stu-id="56a08-185">Null-coalescing, assignment, and conditional operators</span></span>

<span data-ttu-id="56a08-186">PowerShell 7 bietet den NULL-Sammeloperator `??`, die Zuweisung mit NULL-Bedingung `??=` sowie die Zugriffsoperatoren `?.` und `?[]` für Member mit NULL-Bedingung.</span><span class="sxs-lookup"><span data-stu-id="56a08-186">PowerShell 7 includes Null coalescing operator `??`, Null conditional assignment `??=`, and Null conditional member access operators `?.` and `?[]`.</span></span>

### <a name="null-coalescing-operator-"></a><span data-ttu-id="56a08-187">NULL-Sammeloperator ??</span><span class="sxs-lookup"><span data-stu-id="56a08-187">Null-coalescing Operator ??</span></span>

<span data-ttu-id="56a08-188">Der NULL-Sammeloperator `??` gibt den Wert seines linken Operanden zurück, wenn er nicht NULL ist.</span><span class="sxs-lookup"><span data-stu-id="56a08-188">The null-coalescing operator `??` returns the value of its left-hand operand if it isn't null.</span></span>
<span data-ttu-id="56a08-189">Andernfalls wertet er den rechten Operanden aus und gibt sein Ergebnis zurück.</span><span class="sxs-lookup"><span data-stu-id="56a08-189">Otherwise, it evaluates the right-hand operand and returns its result.</span></span> <span data-ttu-id="56a08-190">Der Operator `??` wertet seinen rechten Operanden nicht aus, wenn der linke Operand mit ungleich NULL auswertet wird.</span><span class="sxs-lookup"><span data-stu-id="56a08-190">The `??` operator doesn't evaluate its right-hand operand if the left-hand operand evaluates to non-null.</span></span>

```powershell
$x = $null
$x ?? 100
100
```

<span data-ttu-id="56a08-191">Im folgenden Beispiel wird der rechte Operand nicht ausgewertet:</span><span class="sxs-lookup"><span data-stu-id="56a08-191">In the following example, the right-hand operand won't be evaluated:</span></span>

```powershell
[string] $todaysDate = '1/10/2020'
$todaysDate ?? (Get-Date).ToShortDateString()
1/10/2020
```

### <a name="null-conditional-assignment-operator-"></a><span data-ttu-id="56a08-192">Zuweisungsoperator mit NULL-Bedingung ??=</span><span class="sxs-lookup"><span data-stu-id="56a08-192">Null conditional assignment operator ??=</span></span>

<span data-ttu-id="56a08-193">Der Zuweisungsoperator mit NULL-Bedingung `??=` weist den Wert seines rechten Operanden dem linken Operanden nur zu, wenn der linke Operand mit NULL ausgewertet wird.</span><span class="sxs-lookup"><span data-stu-id="56a08-193">The null conditional assignment operator `??=` assigns the value of its right-hand operand to its left-hand operand only if the left-hand operand evaluates to null.</span></span> <span data-ttu-id="56a08-194">Der Operator `??=` wertet seinen rechten Operanden nicht aus, wenn der linke Operand mit ungleich NULL auswertet wird.</span><span class="sxs-lookup"><span data-stu-id="56a08-194">The `??=` operator doesn't evaluate its right-hand operand if the left-hand operand evaluates to non-null.</span></span>

```powershell
$x = $null
$x ??= 100
$x
100
```

<span data-ttu-id="56a08-195">Im folgenden Beispiel wird der rechte Operand nicht ausgewertet:</span><span class="sxs-lookup"><span data-stu-id="56a08-195">In the following example, the right-hand operand is not evaluated:</span></span>

```powershell
[string] $todaysDate = '1/10/2020'
$todaysDate ??= (Get-Date).ToShortDateString()
1/10/2020
```

### <a name="null-conditional-member-access-operators--and--experimental"></a><span data-ttu-id="56a08-196">Zugriffsoperatoren für Member mit NULL-Bedingung ?.</span><span class="sxs-lookup"><span data-stu-id="56a08-196">Null conditional member access operators ?.</span></span> <span data-ttu-id="56a08-197">und ?[] (experimentell)</span><span class="sxs-lookup"><span data-stu-id="56a08-197">and ?[] (Experimental)</span></span>

> [!NOTE]
> <span data-ttu-id="56a08-198">Dies ist ein experimentelles Feature mit dem Namen **PSNullConditionalOperators**.</span><span class="sxs-lookup"><span data-stu-id="56a08-198">This is an experimental feature named **PSNullConditionalOperators**.</span></span> <span data-ttu-id="56a08-199">Weitere Informationen finden Sie unter [Verwenden von experimentellen Features](/powershell/scripting/learn/experimental-features).</span><span class="sxs-lookup"><span data-stu-id="56a08-199">For more information, see [Using Experimental Features](/powershell/scripting/learn/experimental-features).</span></span>

<span data-ttu-id="56a08-200">Ein bedingter NULL-Operator erlaubt den Memberzugriff (`?.`) oder Elementzugriff (`?[]`) auf seinen Operanden nur dann, wenn dieser Operand mit ungleich NULL ausgewertet wird. Andernfalls gibt er NULL zurück.</span><span class="sxs-lookup"><span data-stu-id="56a08-200">A null conditional operator permits member access, `?.`, or element access, `?[]`, to its operand only if that operand evaluates to non-null; otherwise, it returns null.</span></span>

> [!NOTE]
> <span data-ttu-id="56a08-201">Da PowerShell erlaubt, dass `?` Teil des Variablennamens ist, ist für die Verwendung dieser Operatoren die formale Angabe des Variablennamens erforderlich.</span><span class="sxs-lookup"><span data-stu-id="56a08-201">Since PowerShell allows `?` to be part of the variable name, formal specification of the variable name is required for using these operators.</span></span> <span data-ttu-id="56a08-202">Daher ist es nötig, `{}` um die Variablennamen herum zu platzieren, wie z. B. `${a}` oder wenn `?` Teil des Variablennamens `${a?}` ist.</span><span class="sxs-lookup"><span data-stu-id="56a08-202">So it is required to use `{}` around the variable names like `${a}` or when `?` is part of the variable name `${a?}`.</span></span>

<span data-ttu-id="56a08-203">Im folgenden Beispiel wird der Wert der Membereigenschaft **Status** zurückgegeben:</span><span class="sxs-lookup"><span data-stu-id="56a08-203">In the following example, the value of the member property **Status** is returned:</span></span>

```powershell
$Service = Get-Service -Name 'bits'
${Service}?.status
Stopped
```

<span data-ttu-id="56a08-204">Das folgende Beispiel gibt NULL zurück, ohne dass versucht wird, auf den Membernamen **Status** zuzugreifen:</span><span class="sxs-lookup"><span data-stu-id="56a08-204">The following example returns null, without trying to access the member name **Status** :</span></span>

```powershell
$service = $Null
${Service}?.status
```

<span data-ttu-id="56a08-205">Analog wird bei Verwendung von `?[]` der Wert des Elements zurückgegeben:</span><span class="sxs-lookup"><span data-stu-id="56a08-205">Similarly, using `?[]`, the value of the element is returned:</span></span>

```powershell
$a = 1..10
${a}?[0]
1
```

<span data-ttu-id="56a08-206">Wenn der Operand NULL ist, wird nicht auf das Element zugegriffen und NULL zurückgegeben:</span><span class="sxs-lookup"><span data-stu-id="56a08-206">And when the operand is null, the element isn't accessed and null is returned:</span></span>

```powershell
$a = $null
${a}?[0]
```

<span data-ttu-id="56a08-207">Weitere Informationen finden Sie unter [Informationen zu Operatoren](/powershell/module/microsoft.powershell.core/about/about_operators?view=powershell-7&preserve-view=true).</span><span class="sxs-lookup"><span data-stu-id="56a08-207">For more information [About_Operators](/powershell/module/microsoft.powershell.core/about/about_operators?view=powershell-7&preserve-view=true).</span></span>

## <a name="new-view-conciseview-and-cmdlet-get-error"></a><span data-ttu-id="56a08-208">Neue Ansicht ConciseView und neues Cmdlet Get-Error</span><span class="sxs-lookup"><span data-stu-id="56a08-208">New view ConciseView and cmdlet Get-Error</span></span>

<span data-ttu-id="56a08-209">In PowerShell 7.0 wurde die Anzeige von Fehlermeldungen verbessert, um die Lesbarkeit von Interaktions- und Skriptfehlern mithilfe einer neuen Standardansicht namens **ConciseView** zu optimieren.</span><span class="sxs-lookup"><span data-stu-id="56a08-209">PowerShell 7.0 enhances the display of error messages to improve the readability of interactive and script errors with a new default view **ConciseView**.</span></span> <span data-ttu-id="56a08-210">Die Ansichten sind vom Benutzer über die Einstellungsvariable `$ErrorView` auswählbar.</span><span class="sxs-lookup"><span data-stu-id="56a08-210">The views are user-selectable through the preference variable `$ErrorView`.</span></span>

<span data-ttu-id="56a08-211">Wenn bei **ConciseView** ein Fehler nicht von einem Skript- oder Parserfehler herrührt, handelt es sich um eine einzeilige Fehlermeldung:</span><span class="sxs-lookup"><span data-stu-id="56a08-211">With **ConciseView** , if an error is not from a script or parser error, then it's a single line error message:</span></span>

```powershell
Get-Childitem -Path c:\NotReal
```

```Output
Get-ChildItem: Cannot find path 'C:\NotReal' because it does not exist
```

<span data-ttu-id="56a08-212">Wenn der Fehler während der Skriptausführung auftritt oder ein Analysefehler ist, gibt PowerShell eine mehrzeilige Fehlermeldung zurück. Diese enthält den Fehler, einen Zeiger und eine Fehlermeldung, die angibt, wo der Fehler in dieser Zeile vorliegt.</span><span class="sxs-lookup"><span data-stu-id="56a08-212">If the error occurs during script execution or is a parsing error, PowerShell returns a multiline error message that contains the error, a pointer and error message showing where the error is in that line.</span></span> <span data-ttu-id="56a08-213">Wenn das Terminal keine farbigen Escapesequenzen nach ANSI (VT100) unterstützt, werden keine Farben angezeigt.</span><span class="sxs-lookup"><span data-stu-id="56a08-213">If the terminal doesn't support ANSI color escape sequences (VT100), then colors are not displayed.</span></span>

![Fehleranzeige in einem Skript](./media/What-s-New-in-PowerShell-70/myscript-error.png)

<span data-ttu-id="56a08-215">Die Standardansicht in PowerShell 7 ist **ConciseView**.</span><span class="sxs-lookup"><span data-stu-id="56a08-215">The default view in PowerShell 7 is **ConciseView**.</span></span> <span data-ttu-id="56a08-216">Die vorherige Standardansicht war **NormalView** , die durch Festlegen der Einstellungsvariablen `$ErrorView` ausgewählt werden kann.</span><span class="sxs-lookup"><span data-stu-id="56a08-216">The previous default view was **NormalView** and you can select thisby setting the preference variable `$ErrorView`.</span></span>

```powershell
$ErrorView = 'NormalView' # Sets the error view to NormalView
$ErrorView = 'ConciseView' # Sets the error view to ConciseView
```

> [!NOTE]
> <span data-ttu-id="56a08-217">Die neue Eigenschaft **ErrorAccentColor** wird zu `$Host.PrivateData` hinzugefügt, um die Änderung der Akzentfarbe der Fehlermeldung zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="56a08-217">A new property **ErrorAccentColor** is added to `$Host.PrivateData` to support changing the accent color of the error message.</span></span>

<span data-ttu-id="56a08-218">Das neue Cmdlet `Get-Error` bietet auf Wunsch eine vollständige Detailansicht des vollqualifizierten Fehlers.</span><span class="sxs-lookup"><span data-stu-id="56a08-218">A new cmdlet `Get-Error` provides a complete detailed view of the fully qualified error when desired.</span></span>
<span data-ttu-id="56a08-219">Standardmäßig zeigt das Cmdlet die vollständigen Details, einschließlich innerer Ausnahmen, des zuletzt aufgetretenen Fehlers an.</span><span class="sxs-lookup"><span data-stu-id="56a08-219">By default the cmdlet displays the full details, including inner exceptions, of the last error that occurred.</span></span>

![Anzeige aus Get-Error](./media/What-s-New-in-PowerShell-70/myscript-geterror.png)

<span data-ttu-id="56a08-221">Das Cmdlet `Get-Error` unterstützt die Eingabe aus der Pipeline unter Verwendung der integrierten Variablen `$Error`.</span><span class="sxs-lookup"><span data-stu-id="56a08-221">The `Get-Error` cmdlet supports input from the pipeline using the built-in variable `$Error`.</span></span>
<span data-ttu-id="56a08-222">`Get-Error` zeigt alle weitergeleiteten Fehler an.</span><span class="sxs-lookup"><span data-stu-id="56a08-222">`Get-Error` displays all piped errors.</span></span>

```powershell
$Error | Get-Error
```

<span data-ttu-id="56a08-223">Das Cmdlet `Get-Error` unterstützt den Parameter **Newest** , mit dem Sie angeben können, wie viele Fehler aus der aktuellen Sitzung angezeigt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="56a08-223">The `Get-Error` cmdlet supports the **Newest** parameter, allowing you to specify how many errors from the current session you wish displayed.</span></span>

```powershell
Get-Error -Newest 3 # Displays the lst three errors that occurred in the session
```

<span data-ttu-id="56a08-224">Weitere Informationen finden Sie unter [Get-Error](/powershell/module/microsoft.powershell.utility/get-error?view=powershell-7&preserve-view=true).</span><span class="sxs-lookup"><span data-stu-id="56a08-224">For more information about [Get-Error](/powershell/module/microsoft.powershell.utility/get-error?view=powershell-7&preserve-view=true).</span></span>

## <a name="new-version-notification"></a><span data-ttu-id="56a08-225">Benachrichtigung zu neuen Versionen</span><span class="sxs-lookup"><span data-stu-id="56a08-225">New version notification</span></span>

<span data-ttu-id="56a08-226">PowerShell 7 verwendet Updatebenachrichtigungen, um Benutzer über das Vorhandensein von Updates für PowerShell zu informieren.</span><span class="sxs-lookup"><span data-stu-id="56a08-226">PowerShell 7 uses update notifications to alert users to the existence of updates to PowerShell.</span></span>
<span data-ttu-id="56a08-227">Einmal pro Tag fragt PowerShell einen Onlinedienst ab, um zu prüfen, ob eine neuere Version verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="56a08-227">Once per day, PowerShell queries an online service to determine if a newer version is available.</span></span>

> [!NOTE]
> <span data-ttu-id="56a08-228">Die Prüfung auf Updates erfolgt während der ersten Sitzung innerhalb eines bestimmten 24-stündigen Zeitraums.</span><span class="sxs-lookup"><span data-stu-id="56a08-228">The update check happens during the first session in a given 24-hour period.</span></span> <span data-ttu-id="56a08-229">Aus Leistungsgründen beginnt die Prüfung auf Updates 3 Sekunden nach Beginn der Sitzung.</span><span class="sxs-lookup"><span data-stu-id="56a08-229">For performance reasons, the update check starts 3 seconds after the session begins.</span></span> <span data-ttu-id="56a08-230">Die Benachrichtigung wird nur zu Beginn nachfolgender Sitzungen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="56a08-230">The notification is shown only on the start of subsequent sessions.</span></span>

<span data-ttu-id="56a08-231">Standardmäßig abonniert PowerShell je nach Version/Branch einen von zwei verschiedenen Benachrichtigungskanälen.</span><span class="sxs-lookup"><span data-stu-id="56a08-231">By default, PowerShell subscribes to one of two different notification channels depending on its version/branch.</span></span> <span data-ttu-id="56a08-232">Unterstützte, allgemein verfügbare (GA-) Versionen von PowerShell geben nur für aktualisierte GA-Releases Benachrichtigungen zurück.</span><span class="sxs-lookup"><span data-stu-id="56a08-232">Supported, Generally Available (GA) versions of PowerShell only return notifications for updated GA releases.</span></span> <span data-ttu-id="56a08-233">Vorschau- und Release Candidate-Releases (RC) benachrichtigen über Updates für Vorschau-, RC- und GA-Releases.</span><span class="sxs-lookup"><span data-stu-id="56a08-233">Preview and Release Candidate (RC) releases notify of updates to preview, RC, and GA releases.</span></span>

<span data-ttu-id="56a08-234">Das Verhalten der Updatebenachrichtigung kann mithilfe der Umgebungsvariablen `$Env:POWERSHELL_UPDATECHECK` geändert werden.</span><span class="sxs-lookup"><span data-stu-id="56a08-234">The update notification behavior can be changed using the `$Env:POWERSHELL_UPDATECHECK` environment variable.</span></span> <span data-ttu-id="56a08-235">Die folgenden Werte werden unterstützt:</span><span class="sxs-lookup"><span data-stu-id="56a08-235">The following values are supported:</span></span>

- <span data-ttu-id="56a08-236">**Default** entspricht der Nichtangabe von `$Env:POWERSHELL_UPDATECHECK`.</span><span class="sxs-lookup"><span data-stu-id="56a08-236">**Default** is the same as not defining `$Env:POWERSHELL_UPDATECHECK`</span></span>
  - <span data-ttu-id="56a08-237">GA-Releases benachrichtigen zu Updates von GA-Releases.</span><span class="sxs-lookup"><span data-stu-id="56a08-237">GA releases notify of updates to GA releases</span></span>
  - <span data-ttu-id="56a08-238">Vorschau-/RC-Releases benachrichtigen zu Updates von GA- und Vorschau-Releases.</span><span class="sxs-lookup"><span data-stu-id="56a08-238">Preview/RC releases notify of updates to GA and preview releases</span></span>
- <span data-ttu-id="56a08-239">**Off** deaktiviert das Feature zur Updatebenachrichtigung.</span><span class="sxs-lookup"><span data-stu-id="56a08-239">**Off** turns off the update notification feature</span></span>
- <span data-ttu-id="56a08-240">**LTS** benachrichtigt nur zu Updates für LTS GA-Releases (Long-Term-Servicing).</span><span class="sxs-lookup"><span data-stu-id="56a08-240">**LTS** only notifies of updates to long-term-servicing (LTS) GA releases</span></span>

> [!NOTE]
> <span data-ttu-id="56a08-241">Die Umgebungsvariable `$Env:POWERSHELL_UPDATECHECK` ist erst vorhanden, nachdem sie zum ersten Mal festgelegt wurde.</span><span class="sxs-lookup"><span data-stu-id="56a08-241">The environment variable `$Env:POWERSHELL_UPDATECHECK` does not exist until it is set for the first time.</span></span>

<span data-ttu-id="56a08-242">So legen Sie die Versionsbenachrichtigung nur für `LTS`-Releases fest</span><span class="sxs-lookup"><span data-stu-id="56a08-242">To set the version notification for `LTS` releases only:</span></span>

```powershell
$Env:POWERSHELL_UPDATECHECK = 'LTS'
```

<span data-ttu-id="56a08-243">So legen Sie die Versionsbenachrichtigung auf das `Default`-Verhalten fest</span><span class="sxs-lookup"><span data-stu-id="56a08-243">To set the version notification to the `Default` behavior:</span></span>

```powershell
$Env:POWERSHELL_UPDATECHECK = 'Default'
```

<span data-ttu-id="56a08-244">Weitere Informationen finden Sie unter [Informationen zu Updatebenachrichtigungen](/powershell/module/microsoft.powershell.core/about/about_update_notifications).</span><span class="sxs-lookup"><span data-stu-id="56a08-244">For more information [About Update Notifications](/powershell/module/microsoft.powershell.core/about/about_update_notifications).</span></span>

## <a name="new-dsc-resource-support-with-invoke-dscresource-experimental"></a><span data-ttu-id="56a08-245">Unterstützung für neue DSC-Ressourcen mit Invoke-DSCResource (experimentell)</span><span class="sxs-lookup"><span data-stu-id="56a08-245">New DSC Resource support with Invoke-DSCResource (Experimental)</span></span>

> [!NOTE]
> <span data-ttu-id="56a08-246">Dies ist ein experimentelles Feature mit dem Namen **PSDesiredStateConfiguration.InvokeDscResource**.</span><span class="sxs-lookup"><span data-stu-id="56a08-246">This is an experimental feature named **PSDesiredStateConfiguration.InvokeDscResource**.</span></span> <span data-ttu-id="56a08-247">Weitere Informationen finden Sie unter [Verwenden von experimentellen Features](/powershell/scripting/learn/experimental-features).</span><span class="sxs-lookup"><span data-stu-id="56a08-247">For more information, see [Using Experimental Features](/powershell/scripting/learn/experimental-features).</span></span>

<span data-ttu-id="56a08-248">Mit dem Cmdlet `Invoke-DscResource` wird eine Methode einer angegebenen PowerShell DSC-Ressource (Desired State Configuration) ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="56a08-248">The `Invoke-DscResource` cmdlet runs a method of a specified PowerShell Desired State Configuration (DSC) resource.</span></span>

<span data-ttu-id="56a08-249">Dieses Cmdlet ruft eine DSC-Ressource direkt auf, ohne ein Konfigurationsdokument zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="56a08-249">This cmdlet invokes a DSC resource directly, without creating a configuration document.</span></span> <span data-ttu-id="56a08-250">Mit diesem Cmdlet können Konfigurationsverwaltungsprodukte Windows oder Linux mithilfe von DSC-Ressourcen verwalten.</span><span class="sxs-lookup"><span data-stu-id="56a08-250">Using this cmdlet, configuration management products can manage Windows or Linux by using DSC resources.</span></span> <span data-ttu-id="56a08-251">Dieses Cmdlet ermöglicht auch das Debuggen von Ressourcen, wenn die DSC-Engine mit aktiviertem Debuggen ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="56a08-251">This cmdlet also enables debugging of resources when the DSC engine is running with debugging enabled.</span></span>

<span data-ttu-id="56a08-252">Mit diesem Befehl wird die **Set** -Methode einer Ressource mit dem Namen **WindowsProcess** aufgerufen und die zum Starten des angegebenen Windows-Prozesses erforderlichen Eigenschaften **Path** und **Arguments** bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="56a08-252">This command invokes the **Set** method of a resource named **WindowsProcess** and provides the mandatory **Path** and **Arguments** properties to start the specified Windows process.</span></span>

```powershell
Invoke-DscResource -Name WindowsProcess -Method Set -ModuleName PSDesiredStateConfiguration -Property @{
  Path = 'C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe'
  Arguments = ''
}
```

<span data-ttu-id="56a08-253">Weitere Informationen finden Sie unter [Invoke-DSCResource](/powershell/module/psdesiredstateconfiguration/invoke-dscresource?view=powershell-7&preserve-view=true).</span><span class="sxs-lookup"><span data-stu-id="56a08-253">For more information about [Invoke-DSCResource](/powershell/module/psdesiredstateconfiguration/invoke-dscresource?view=powershell-7&preserve-view=true).</span></span>

## <a name="breaking-changes-and-improvements"></a><span data-ttu-id="56a08-254">Breaking Changes und Verbesserungen</span><span class="sxs-lookup"><span data-stu-id="56a08-254">Breaking Changes and Improvements</span></span>

### <a name="breaking-changes"></a><span data-ttu-id="56a08-255">Aktuelle Änderungen</span><span class="sxs-lookup"><span data-stu-id="56a08-255">Breaking Changes</span></span>

- <span data-ttu-id="56a08-256">Bewirken, dass Updatebenachrichtigungen LTS und Standardkanäle unterstützen (#11132)</span><span class="sxs-lookup"><span data-stu-id="56a08-256">Make update notification support LTS and default channels (#11132)</span></span>
- <span data-ttu-id="56a08-257">Aktualisierung von Test-Connection, damit das Cmdlet mehr wie in Windows PowerShell funktioniert (#10697) (vielen Dank an @vexx32!)</span><span class="sxs-lookup"><span data-stu-id="56a08-257">Update Test-Connection to work more like the one in Windows PowerShell (#10697) (Thanks @vexx32!)</span></span>
- <span data-ttu-id="56a08-258">Beibehaltung von $?</span><span class="sxs-lookup"><span data-stu-id="56a08-258">Preserve $?</span></span> <span data-ttu-id="56a08-259">für ParenExpression, SubExpression und ArrayExpression (#11040)</span><span class="sxs-lookup"><span data-stu-id="56a08-259">for ParenExpression, SubExpression and ArrayExpression (#11040)</span></span>
- <span data-ttu-id="56a08-260">Festlegung des Arbeitsverzeichnisses auf das aktuelle Verzeichnis in Start-Job (#10920) (vielen Dank an @iSazonov!)</span><span class="sxs-lookup"><span data-stu-id="56a08-260">Set working directory to current directory in Start-Job (#10920) (Thanks @iSazonov!)</span></span>
- <span data-ttu-id="56a08-261">Veranlassen, dass $PSCulture Veränderungen der Kultur innerhalb der Sitzung konsistent widerspiegelt (#10138) (vielen Dank an @iSazonov!)</span><span class="sxs-lookup"><span data-stu-id="56a08-261">Make $PSCulture consistently reflect in-session culture changes (#10138) (Thanks @iSazonov!)</span></span>

### <a name="engine-updates-and-fixes"></a><span data-ttu-id="56a08-262">Engineupdates und Fixes</span><span class="sxs-lookup"><span data-stu-id="56a08-262">Engine Updates and Fixes</span></span>

- <span data-ttu-id="56a08-263">Verbesserungen bei Haltepunkt-APIs für Remoteszenarien (#11312)</span><span class="sxs-lookup"><span data-stu-id="56a08-263">Improvements in breakpoint APIs for remote scenarios (#11312)</span></span>
- <span data-ttu-id="56a08-264">Korrektur des Entweichens von PowerShell-Klassendefinition in einen anderen Runspace (#11273)</span><span class="sxs-lookup"><span data-stu-id="56a08-264">Fix PowerShell class definition leaking into another Runspace (#11273)</span></span>
- <span data-ttu-id="56a08-265">Korrektur einer Regression in der Formatierung, die durch die in 7.0.0-Preview1 hinzugefügte Primitive FirstOrDefault verursacht wurde (#11258)</span><span class="sxs-lookup"><span data-stu-id="56a08-265">Fix a regression in formatting caused by the FirstOrDefault primitive added in 7.0.0-Preview1 (#11258)</span></span>
- <span data-ttu-id="56a08-266">Zusätzliche in PS7-Telemetrie nachzuverfolgende Microsoft-Module (#10751)</span><span class="sxs-lookup"><span data-stu-id="56a08-266">Additional Microsoft Modules to track in PS7 Telemetry (#10751)</span></span>
- <span data-ttu-id="56a08-267">Festlegung genehmigter Features als nicht experimentell (#11303)</span><span class="sxs-lookup"><span data-stu-id="56a08-267">Make approved features non-experimental (#11303)</span></span>
- <span data-ttu-id="56a08-268">Aktualisierung von ConciseView für die Verwendung von TargetObject, falls zutreffend (#11075)</span><span class="sxs-lookup"><span data-stu-id="56a08-268">Update ConciseView to use TargetObject if applicable (#11075)</span></span>
- <span data-ttu-id="56a08-269">Korrektur von NullReferenceException in öffentlichen CompletionCompleters-Methoden (#11274)</span><span class="sxs-lookup"><span data-stu-id="56a08-269">Fix NullReferenceException in CompletionCompleters public methods (#11274)</span></span>
- <span data-ttu-id="56a08-270">Korrektur der Überprüfung des Status des Apartment-Threads auf Nicht-Windows-Plattformen (#11301)</span><span class="sxs-lookup"><span data-stu-id="56a08-270">Fix apartment thread state check on non-Windows platforms (#11301)</span></span>
- <span data-ttu-id="56a08-271">Aktualisierung der Einstellung PSModulePath dergestalt, dass Prozess- und Computerumgebungsvariablen verkettet werden (#11276)</span><span class="sxs-lookup"><span data-stu-id="56a08-271">Update setting PSModulePath to concatenate the process and machine environment variables (#11276)</span></span>
- <span data-ttu-id="56a08-272">Aktualisierung von .NET Core auf 3.1.0 (#11260)</span><span class="sxs-lookup"><span data-stu-id="56a08-272">Bump .NET Core to 3.1.0 (#11260)</span></span>
- <span data-ttu-id="56a08-273">Korrektur der Erkennung von $PSHOME vor $env:PATH (#11141)</span><span class="sxs-lookup"><span data-stu-id="56a08-273">Fix detection of $PSHOME in front of $env:PATH (#11141)</span></span>
- <span data-ttu-id="56a08-274">Zulassen, dass pwsh $env:PSModulePath erbt, und ermöglichen, dass powershell.exe ordnungsgemäß gestartet wird (#11057)</span><span class="sxs-lookup"><span data-stu-id="56a08-274">Allow pwsh to inherit $env:PSModulePath and enable powershell.exe to start correctly (#11057)</span></span>
- <span data-ttu-id="56a08-275">Umstieg auf .NET Core 3.1 Preview 1 (#10798)</span><span class="sxs-lookup"><span data-stu-id="56a08-275">Move to .NET Core 3.1 preview 1 (#10798)</span></span>
- <span data-ttu-id="56a08-276">Umgestaltung von Tagprüfungen nach erneuter Analyse in Dateisystemanbieter (#10431) (vielen Dank an @iSazonov!)</span><span class="sxs-lookup"><span data-stu-id="56a08-276">Refactor reparse tag checks in file system provider (#10431) (Thanks @iSazonov!)</span></span>
- <span data-ttu-id="56a08-277">Ersetzung von Wagenrücklauf- und Zeilenvorschubzeichen (CR und LF) durch das Zeichen 0x23CE in Skriptprotokollierung (#10616)</span><span class="sxs-lookup"><span data-stu-id="56a08-277">Replace CR and new line with a 0x23CE character in script logging (#10616)</span></span>
- <span data-ttu-id="56a08-278">Korrektur eines Ressourcenlecks durch Aufheben der Registrierung des Ereignisbehandlers in AppDomain.CurrentDomain.ProcessExit (#10626)</span><span class="sxs-lookup"><span data-stu-id="56a08-278">Fix a resource leak by unregistering the event handler from AppDomain.CurrentDomain.ProcessExit (#10626)</span></span>
- <span data-ttu-id="56a08-279">Hinzufügung von Unterstützung für ActionPreference.break, um den Debugger anzuhalten, wenn Debug-, Fehler-, Informations-, Status-, ausführliche oder Warnmeldungen generiert werden (#8205) (vielen Dank an @KirkMunro!)</span><span class="sxs-lookup"><span data-stu-id="56a08-279">Add support to ActionPreference.Break to break into debugger when Debug, Error, Information, Progress, Verbose or Warning messages are generated (#8205) (Thanks @KirkMunro!)</span></span>
- <span data-ttu-id="56a08-280">Aktivierung des Starts von Systemsteuerungs-Add-Ins in PowerShell Core ohne Angabe der CPL-Erweiterung.</span><span class="sxs-lookup"><span data-stu-id="56a08-280">Enable starting control panel add-ins within PowerShell Core without specifying .CPL extension.</span></span> <span data-ttu-id="56a08-281">(#9828)</span><span class="sxs-lookup"><span data-stu-id="56a08-281">(#9828)</span></span>
- <span data-ttu-id="56a08-282">Unterstützung negativer Zahlen im Operator -split (#8960) (vielen Dank an @ece-jacob-scott!)</span><span class="sxs-lookup"><span data-stu-id="56a08-282">Support negative numbers in -split operator (#8960) (Thanks @ece-jacob-scott!)</span></span>

### <a name="general-cmdlet-updates-and-fixes"></a><span data-ttu-id="56a08-283">Allgemeine Cmdletupdates und Korrekturen</span><span class="sxs-lookup"><span data-stu-id="56a08-283">General Cmdlet Updates and Fixes</span></span>

- <span data-ttu-id="56a08-284">Korrektur für Problem in Raspbian beim Festlegen des Datums von Dateiänderungen im experimentellen Feature UnixStat (#11313)</span><span class="sxs-lookup"><span data-stu-id="56a08-284">Fix for issue on Raspbian for setting date of file changes in UnixStat Experimental Feature (#11313)</span></span>
- <span data-ttu-id="56a08-285">Hinzufügung von -AsPlainText zu ConvertFrom-SecureString (#11142)</span><span class="sxs-lookup"><span data-stu-id="56a08-285">Add -AsPlainText to ConvertFrom-SecureString (#11142)</span></span>
- <span data-ttu-id="56a08-286">Prüfung der WindowsPS-Version für WinCompat hinzugefügt (#11148)</span><span class="sxs-lookup"><span data-stu-id="56a08-286">Added WindowsPS version check for WinCompat (#11148)</span></span>
- <span data-ttu-id="56a08-287">Korrektur der Fehlerberichterstellung in einigen WinCompat-Szenarien (#11259)</span><span class="sxs-lookup"><span data-stu-id="56a08-287">Fix error-reporting in some WinCompat scenarios (#11259)</span></span>
- <span data-ttu-id="56a08-288">Hinzufügung von nativem binären Konfliktlöser (#11032) (vielen Dank an@iSazonov!)</span><span class="sxs-lookup"><span data-stu-id="56a08-288">Add native binary resolver (#11032) (Thanks @iSazonov!)</span></span>
- <span data-ttu-id="56a08-289">Aktualisierung der Berechnung der Zeichenbreite unter vollständiger Berücksichtigung von CJK-Zeichen (#11262)</span><span class="sxs-lookup"><span data-stu-id="56a08-289">Update calculation of char width to respect CJK chars correctly (#11262)</span></span>
- <span data-ttu-id="56a08-290">Hinzufügung von Unblock-File für macOS (#11137)</span><span class="sxs-lookup"><span data-stu-id="56a08-290">Add Unblock-File for macOS (#11137)</span></span>
- <span data-ttu-id="56a08-291">Korrektur von Regression in Get-PSCallStack (#11210) (vielen Dank an @iSazonov!)</span><span class="sxs-lookup"><span data-stu-id="56a08-291">Fix regression in Get-PSCallStack (#11210) (Thanks @iSazonov!)</span></span>
- <span data-ttu-id="56a08-292">Entfernung des automatischen Ladens des Moduls ScheduledJob bei Verwendung von Job-Cmdlets (#11194)</span><span class="sxs-lookup"><span data-stu-id="56a08-292">Remove autoloading of the ScheduledJob module when using Job cmdlets (#11194)</span></span>
- <span data-ttu-id="56a08-293">Hinzufügung von OutputType zum Cmdlet Get-Error und Beibehaltung ursprünglicher Typnamen (#10856)</span><span class="sxs-lookup"><span data-stu-id="56a08-293">Add OutputType to Get-Error cmdlet and preserve original typenames (#10856)</span></span>
- <span data-ttu-id="56a08-294">Korrektur des NULL-Verweises in der Eigenschaft SupportsVirtualTerminal (#11105)</span><span class="sxs-lookup"><span data-stu-id="56a08-294">Fix null reference in SupportsVirtualTerminal property (#11105)</span></span>
- <span data-ttu-id="56a08-295">Hinzufügung der Grenzwertprüfung in Get-WinEvent (#10648) (vielen Dank an @iSazonov!)</span><span class="sxs-lookup"><span data-stu-id="56a08-295">Add limit check in Get-WinEvent (#10648) (Thanks @iSazonov!)</span></span>
- <span data-ttu-id="56a08-296">Korrektur der Befehlslaufzeit dahingehend, dass StopUpstreamCommandsException in -ErrorVariable nicht aufgefüllt wird (#10840)</span><span class="sxs-lookup"><span data-stu-id="56a08-296">Fix command runtime so StopUpstreamCommandsException doesn't get populated in -ErrorVariable (#10840)</span></span>
- <span data-ttu-id="56a08-297">Festlegung der Ausgabecodierung auf [Console]::OutputEncoding für native Befehle (#10824)</span><span class="sxs-lookup"><span data-stu-id="56a08-297">Set the output encoding to [Console]::OutputEncoding for native commands (#10824)</span></span>
- <span data-ttu-id="56a08-298">Unterstützung mehrzeiliger Codeblöcke in Beispielen (#10776) (vielen Dank an @Greg-Smulko!)</span><span class="sxs-lookup"><span data-stu-id="56a08-298">Support multi-line code blocks in examples (#10776) (Thanks @Greg-Smulko!)</span></span>
- <span data-ttu-id="56a08-299">Hinzufügung des Culture-Parameters zum Cmdlet Select-String (#10943) (vielen Dank an @iSazonov!)</span><span class="sxs-lookup"><span data-stu-id="56a08-299">Add Culture parameter to Select-String cmdlet (#10943) (Thanks @iSazonov!)</span></span>
- <span data-ttu-id="56a08-300">Korrektur des Arbeitsverzeichnispfads von Start-Job mit nachgestelltem Rückwärtsschrägstrich (#11041)</span><span class="sxs-lookup"><span data-stu-id="56a08-300">Fix Start-Job working directory path with trailing backslash (#11041)</span></span>
- <span data-ttu-id="56a08-301">ConvertFrom-Json: Standardmäßiges Aufheben des Umbruchs in Sammlungen (#10861) (vielen Dank an @danstur!)</span><span class="sxs-lookup"><span data-stu-id="56a08-301">ConvertFrom-Json: Unwrap collections by default (#10861) (Thanks @danstur!)</span></span>
- <span data-ttu-id="56a08-302">Unterscheidung von Groß-/Kleinschreibung für das Cmdlet Group-Object mit den Schaltern -CaseSensitive und -AsHashtable (#11030) (vielen Dank an @vexx32!)</span><span class="sxs-lookup"><span data-stu-id="56a08-302">Use case-sensitive Hashtable for Group-Object cmdlet with -CaseSensitive and -AsHashtable switches (#11030) (Thanks @vexx32!)</span></span>
- <span data-ttu-id="56a08-303">Behandlung der Ausnahme, wenn die Aufzählung von Dateien beim Neuerstellen des Pfads fehlschlägt, um die richtige Schreibweise zu erhalten (#11014)</span><span class="sxs-lookup"><span data-stu-id="56a08-303">Handle exception if enumerating files fails when rebuilding path to have correct casing (#11014)</span></span>
- <span data-ttu-id="56a08-304">Korrektur von ConciseView zur Anzeige von Activity statt myCommand (#11007)</span><span class="sxs-lookup"><span data-stu-id="56a08-304">Fix ConciseView to show Activity instead of myCommand (#11007)</span></span>
- <span data-ttu-id="56a08-305">Zulassen, dass Web-Cmdlets HTTP-Fehlerstatus ignorieren (#10466) (vielen Dank an @vdamewood!)</span><span class="sxs-lookup"><span data-stu-id="56a08-305">Allow web cmdlets to ignore HTTP error statuses (#10466) (Thanks @vdamewood!)</span></span>
- <span data-ttu-id="56a08-306">Korrektur der Weiterleitung von mehr als einer CommandInfo an Get-Command (#10929)</span><span class="sxs-lookup"><span data-stu-id="56a08-306">Fix piping of more than one CommandInfo to Get-Command (#10929)</span></span>
- <span data-ttu-id="56a08-307">Wiederhinzufügung des Cmdlets Get-Counter für Windows (#10933)</span><span class="sxs-lookup"><span data-stu-id="56a08-307">Add back Get-Counter cmdlet for Windows (#10933)</span></span>
- <span data-ttu-id="56a08-308">Veranlassen, dass ConvertTo-Json [AutomationNull]::Value und [NullString]::Value als $null behandelt (#10957)</span><span class="sxs-lookup"><span data-stu-id="56a08-308">Make ConvertTo-Json treat [AutomationNull]::Value and [NullString]::Value as $null (#10957)</span></span>
- <span data-ttu-id="56a08-309">Entfernung von Klammern aus der IPv6-Adresse für SSH-Remoting (#10968)</span><span class="sxs-lookup"><span data-stu-id="56a08-309">Remove brackets from ipv6 address for SSH remoting (#10968)</span></span>
- <span data-ttu-id="56a08-310">Kein Absturz mehr, wenn der an pwsh gesendete Befehl nur aus Leerzeichen besteht (#10977)</span><span class="sxs-lookup"><span data-stu-id="56a08-310">Fix crash if command sent to pwsh is just whitespace (#10977)</span></span>
- <span data-ttu-id="56a08-311">Plattformübergreifende Cmdlets Get-Clipboard und Set-Clipboard hinzugefügt (#10340)</span><span class="sxs-lookup"><span data-stu-id="56a08-311">Added cross-platform Get-Clipboard and Set-Clipboard (#10340)</span></span>
- <span data-ttu-id="56a08-312">Korrektur der Festlegung des Ursprungspfads eines Dateisystemobjekts dahingehend, dass es keinen zusätzlichen nachstehenden Schrägstrich aufweist (#10959)</span><span class="sxs-lookup"><span data-stu-id="56a08-312">Fix setting original path of filesystem object to not have extra trailing slash (#10959)</span></span>
- <span data-ttu-id="56a08-313">Unterstützung von $null für ConvertTo-Json (#10947)</span><span class="sxs-lookup"><span data-stu-id="56a08-313">Support $null for ConvertTo-Json (#10947)</span></span>
- <span data-ttu-id="56a08-314">Wiederhinzufügung des Befehls Out-Printer für Windows (#10906)</span><span class="sxs-lookup"><span data-stu-id="56a08-314">Add back Out-Printer command on Windows (#10906)</span></span>
- <span data-ttu-id="56a08-315">Korrektur von -WorkingDirectory für Start-Job mit Leerzeichen (#10951)</span><span class="sxs-lookup"><span data-stu-id="56a08-315">Fix Start-Job -WorkingDirectory with whitespace (#10951)</span></span>
- <span data-ttu-id="56a08-316">Rückgabe des Standardwerts, wenn für eine Einstellung in PSConfiguration.cs der Wert NULL abgerufen wird (#10963) (vielen Dank an @iSazonov!)</span><span class="sxs-lookup"><span data-stu-id="56a08-316">Return default value when getting null for a setting in PSConfiguration.cs (#10963) (Thanks @iSazonov!)</span></span>
- <span data-ttu-id="56a08-317">Behandlung von E/A-Ausnahme als nicht beendend (#10950)</span><span class="sxs-lookup"><span data-stu-id="56a08-317">Handle IO exception as non-terminating (#10950)</span></span>
- <span data-ttu-id="56a08-318">Hinzufügung der Assembly GraphicalHost zur Aktivierung von Out-GridView, Show-Command und Get-Help -ShowWindow (#10899)</span><span class="sxs-lookup"><span data-stu-id="56a08-318">Add GraphicalHost assembly to enable Out-GridView, Show-Command, and Get-Help -ShowWindow (#10899)</span></span>
- <span data-ttu-id="56a08-319">Verwenden von ComputerName über Pipeline in Get-HotFix (#10852) (vielen Dank an @kvprasoon!)</span><span class="sxs-lookup"><span data-stu-id="56a08-319">Take ComputerName via pipeline in Get-HotFix (#10852) (Thanks @kvprasoon!)</span></span>
- <span data-ttu-id="56a08-320">Korrektur der Vervollständigung per TAB-TASTE für Parameter dergestalt, dass allgemeine Parameter als verfügbar angezeigt werden (#10850)</span><span class="sxs-lookup"><span data-stu-id="56a08-320">Fix tab completion for parameters so that it shows common parameters as available (#10850)</span></span>
- <span data-ttu-id="56a08-321">Korrektur von GetCorrectCasedPath(), um vor dem Aufruf von First() zunächst zu prüfen, ob Systemdateieinträge zurückgegeben werden (#10930)</span><span class="sxs-lookup"><span data-stu-id="56a08-321">Fix GetCorrectCasedPath() to first check if any system file entries is returned before calling First() (#10930)</span></span>
- <span data-ttu-id="56a08-322">Festlegung des Arbeitsverzeichnisses auf das aktuelle Verzeichnis in Start-Job (#10920) (vielen Dank an @iSazonov!)</span><span class="sxs-lookup"><span data-stu-id="56a08-322">Set working directory to current directory in Start-Job (#10920) (Thanks @iSazonov!)</span></span>
- <span data-ttu-id="56a08-323">Ändern von TabExpansion2 dahingehend, dass -CursorColumn nicht erforderlich ist und als $InputScript.Length behandelt wird (#10849)</span><span class="sxs-lookup"><span data-stu-id="56a08-323">Change TabExpansion2 to not require -CursorColumn and treat as $InputScript.Length (#10849)</span></span>
- <span data-ttu-id="56a08-324">Behandeln des Falls, bei dem Host möglicherweise keine Zeilen oder Spalten des Bildschirms zurückgibt (#10938)</span><span class="sxs-lookup"><span data-stu-id="56a08-324">Handle case where Host may not return Rows or Columns of screen (#10938)</span></span>
- <span data-ttu-id="56a08-325">Korrektur der Verwendung von Akzentfarben für Hosts, die diese nicht unterstützen (#10937)</span><span class="sxs-lookup"><span data-stu-id="56a08-325">Fix use of accent colors for hosts that don't support them (#10937)</span></span>
- <span data-ttu-id="56a08-326">Wiederhinzufügung des Befehls Update-List (#10922)</span><span class="sxs-lookup"><span data-stu-id="56a08-326">Add back Update-List command (#10922)</span></span>
- <span data-ttu-id="56a08-327">Aktualisierung von FWLink Id für Clear-RecycleBin (#10925)</span><span class="sxs-lookup"><span data-stu-id="56a08-327">Update FWLink Id for Clear-RecycleBin (#10925)</span></span>
- <span data-ttu-id="56a08-328">Überspringen der Datei während der Vervollständigung per TAB-TASTE, wenn Dateiattribute nicht gelesen werden können (#10910)</span><span class="sxs-lookup"><span data-stu-id="56a08-328">During tab completion, skip file if can't read file attributes (#10910)</span></span>
- <span data-ttu-id="56a08-329">Wiederhinzufügung von Clear-RecycleBin für Windows (#10909)</span><span class="sxs-lookup"><span data-stu-id="56a08-329">Add back Clear-RecycleBin for Windows (#10909)</span></span>
- <span data-ttu-id="56a08-330">Hinzufügung von `$env:__SuppressAnsiEscapeSequences` zum Steuern, ob bei der Ausgabe eine VT-Escapesequenz verwendet werden soll (#10814)</span><span class="sxs-lookup"><span data-stu-id="56a08-330">Add `$env:__SuppressAnsiEscapeSequences` to control whether to have VT escape sequence in output (#10814)</span></span>
- <span data-ttu-id="56a08-331">Hinzufügung des Parameters -NoEmphasize zur farbigen Darstellung der Ausgabe von Select-String (#8963) (vielen Dank an @derek-xia!)</span><span class="sxs-lookup"><span data-stu-id="56a08-331">Add -NoEmphasize parameter to colorize Select-String output (#8963) (Thanks @derek-xia!)</span></span>
- <span data-ttu-id="56a08-332">Wiederhinzufügung des Cmdlets Get-HotFix (#10740)</span><span class="sxs-lookup"><span data-stu-id="56a08-332">Add back Get-HotFix cmdlet (#10740)</span></span>
- <span data-ttu-id="56a08-333">Ermöglichung des Verwendens von Add-Type in Anwendungen, die PowerShell hosten (#10587)</span><span class="sxs-lookup"><span data-stu-id="56a08-333">Make Add-Type usable in applications that host PowerShell (#10587)</span></span>
- <span data-ttu-id="56a08-334">Verwendung einer effektiveren Auswertungsreihenfolge in LanguagePrimitives.IsNullLike() (#10781) (vielen Dank an @vexx32!)</span><span class="sxs-lookup"><span data-stu-id="56a08-334">Use more effective evaluation order in LanguagePrimitives.IsNullLike() (#10781) (Thanks @vexx32!)</span></span>
- <span data-ttu-id="56a08-335">Verbesserung der Handhabung gemischter Sammlungen von weitergeleiteten Eingaben und weitergeleiteten Datenströmen in Format-Hex (#8674) (vielen Dank an @vexx32!)</span><span class="sxs-lookup"><span data-stu-id="56a08-335">Improve handling of mixed-collection piped input and piped streams of input in Format-Hex (#8674) (Thanks @vexx32!)</span></span>
- <span data-ttu-id="56a08-336">Verwendung der Typkonvertierung in Hashtabellen für SSHConnection, wenn der Wert nicht dem erwarteten Typ entspricht (#10720) (vielen Dank an @SeeminglyScience!)</span><span class="sxs-lookup"><span data-stu-id="56a08-336">Use type conversion in SSHConnection hashtables when value doesn't match expected type (#10720) (Thanks @SeeminglyScience!)</span></span>
- <span data-ttu-id="56a08-337">Korrektur des Verhaltens von Get-Content -ReadCount 0, wenn -TotalCount festgelegt ist (#10749) (vielen Dank an @eugenesmlv!)</span><span class="sxs-lookup"><span data-stu-id="56a08-337">Fix Get-Content -ReadCount 0 behavior when -TotalCount is set (#10749) (Thanks @eugenesmlv!)</span></span>
- <span data-ttu-id="56a08-338">Umformulierung der Fehlermeldung des Typs „Zugriff verweigert“ in Get-WinEvent (#10639) (vielen Dank an @iSazonov!)</span><span class="sxs-lookup"><span data-stu-id="56a08-338">Reword access denied error message in Get-WinEvent (#10639) (Thanks @iSazonov!)</span></span>
- <span data-ttu-id="56a08-339">Aktivierung der Vervollständigung per TAB-TASTE zur Variablenzuweisung bei Einschränkung von Enumeration oder Typ (#10646)</span><span class="sxs-lookup"><span data-stu-id="56a08-339">Enable tab completion for variable assignment that is enum or type constrained (#10646)</span></span>
- <span data-ttu-id="56a08-340">Entfernung der nicht verwendeten Remotingeigenschaft SourceLength, die Formatierungsprobleme verursacht (#10765)</span><span class="sxs-lookup"><span data-stu-id="56a08-340">Remove unused SourceLength remoting property causing formatting issues (#10765)</span></span>
- <span data-ttu-id="56a08-341">Hinzufügung des Parameters -Delimiter zu ConvertFrom-StringData (#10665) (vielen Dank an @steviecoaster!)</span><span class="sxs-lookup"><span data-stu-id="56a08-341">Add -Delimiter parameter to ConvertFrom-StringData (#10665) (Thanks @steviecoaster!)</span></span>
- <span data-ttu-id="56a08-342">Hinzufügung von Positionsparameter für ScriptBlock bei Verwendung von Invoke-Command mit SSH (#10721) (vielen Dank an @machgo!)</span><span class="sxs-lookup"><span data-stu-id="56a08-342">Add positional parameter for ScriptBlock when using Invoke-Command with SSH (#10721) (Thanks @machgo!)</span></span>
- <span data-ttu-id="56a08-343">Anzeige von Zeilenkontextinformationen bei mehreren Zeilen, aber keinen Skriptnamen für ConciseView (#10746)</span><span class="sxs-lookup"><span data-stu-id="56a08-343">Show line context information if multiple lines but no script name for ConciseView (#10746)</span></span>
- <span data-ttu-id="56a08-344">Hinzufügung von Unterstützung für Pfade des Typs \\wsl$\ zu Dateisystemanbieter (#10674)</span><span class="sxs-lookup"><span data-stu-id="56a08-344">Add support for \\wsl$\ paths to file system provider (#10674)</span></span>
- <span data-ttu-id="56a08-345">Hinzufügung des fehlenden Tokentexts für TokenKind.QuestionMark im Parser (#10706)</span><span class="sxs-lookup"><span data-stu-id="56a08-345">Add the missing token text for TokenKind.QuestionMark in parser (#10706)</span></span>
- <span data-ttu-id="56a08-346">Festlegung des aktuellen Arbeitsverzeichnisses jedes ausgeführten Skripts des Typs ForEach-Object -Parallel auf einen Ort, der mit dem aufrufenden Skript identisch ist.</span><span class="sxs-lookup"><span data-stu-id="56a08-346">Set current working directory of each ForEach-Object -Parallel running script to the same location as the calling script.</span></span> <span data-ttu-id="56a08-347">(#10672)</span><span class="sxs-lookup"><span data-stu-id="56a08-347">(#10672)</span></span>
- <span data-ttu-id="56a08-348">Ersetzung von api-ms-win-core-file-l1-2-2.dll durch Kernell32.dll für die APIs FindFirstStreamW und FindNextStreamW (#10680) (vielen Dank an @iSazonov!)</span><span class="sxs-lookup"><span data-stu-id="56a08-348">Replace api-ms-win-core-file-l1-2-2.dll with Kernell32.dll for FindFirstStreamW and FindNextStreamW APIs (#10680) (Thanks @iSazonov!)</span></span>
- <span data-ttu-id="56a08-349">Optimierung des Hilfeformatierungsskripts, um toleranter gegenüber StrictMode zu sein (#10563)</span><span class="sxs-lookup"><span data-stu-id="56a08-349">Tweak help formatting script to be more StrictMode tolerant (#10563)</span></span>
- <span data-ttu-id="56a08-350">Hinzufügen des Parameters -SecurityDescriptorSDDL zu New-Service (#10483) (vielen Dank an @kvprasoon!)</span><span class="sxs-lookup"><span data-stu-id="56a08-350">Add -SecurityDescriptorSDDL parameter to New-Service (#10483) (Thanks @kvprasoon!)</span></span>
- <span data-ttu-id="56a08-351">Entfernung von Informationsausgaben, Konsolidierung der Nutzung von Ping in Test-Connection (#10478) (vielen Dank an @vexx32!)</span><span class="sxs-lookup"><span data-stu-id="56a08-351">Remove informational output, consolidate ping usage in Test-Connection (#10478) (Thanks @vexx32!)</span></span>
- <span data-ttu-id="56a08-352">Lesen spezieller Analysepunkte, ohne auf sie zuzugreifen (#10662) (vielen Dank an @iSazonov!)</span><span class="sxs-lookup"><span data-stu-id="56a08-352">Read special reparse points without accessing them (#10662) (Thanks @iSazonov!)</span></span>
- <span data-ttu-id="56a08-353">Direkte Clear-Host-Ausgabe an Terminal (#10681) (vielen Dank an @iSazonov!)</span><span class="sxs-lookup"><span data-stu-id="56a08-353">Direct Clear-Host output to terminal (#10681) (Thanks @iSazonov!)</span></span>
- <span data-ttu-id="56a08-354">Wiederhinzufügung eines Zeilenvorschubzeichens für Gruppierung mit Format-Table und -Property (#10653)</span><span class="sxs-lookup"><span data-stu-id="56a08-354">Add back newline for grouping with Format-Table and -Property (#10653)</span></span>
- <span data-ttu-id="56a08-355">Entfernung von [ValidateNotNullOrEmpty] aus -InputObject für Get-Random, um eine leere Zeichenfolge zuzulassen (#10644)</span><span class="sxs-lookup"><span data-stu-id="56a08-355">Remove [ValidateNotNullOrEmpty] from -InputObject on Get-Random to allow empty string (#10644)</span></span>
- <span data-ttu-id="56a08-356">Keine Unterscheidung von Groß-/Kleinschreibung für Entfernungsalgorithmus in Zeichenfolgen des Vorschlagsystems (#10549) (vielen Dank an@iSazonov!)</span><span class="sxs-lookup"><span data-stu-id="56a08-356">Make suggestion system string distance algorithm case-insensitive (#10549) (Thanks @iSazonov!)</span></span>
- <span data-ttu-id="56a08-357">Korrektur von NULL-Verweisausnahme in Eingabeverarbeitung für ForEach-Object -Parallel (#10577)</span><span class="sxs-lookup"><span data-stu-id="56a08-357">Fix null reference exception in ForEach-Object -Parallel input processing (#10577)</span></span>
- <span data-ttu-id="56a08-358">Hinzufügung von PowerShell Core-Gruppenrichtliniendefinitionen (#10468)</span><span class="sxs-lookup"><span data-stu-id="56a08-358">Add PowerShell Core group policy definitions (#10468)</span></span>
- <span data-ttu-id="56a08-359">Aktualisierung des Konsolenhosts zur Unterstützung von XTPUSHSGR/XTPOPSGR VT-Steuersequenzen, die in Zusammensetzbarkeitsszenarien verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="56a08-359">Update console host to support XTPUSHSGR/XTPOPSGR VT control sequences that are used in composability scenarios.</span></span> <span data-ttu-id="56a08-360">(#10208)</span><span class="sxs-lookup"><span data-stu-id="56a08-360">(#10208)</span></span>
- <span data-ttu-id="56a08-361">Hinzufügung des Parameters WorkingDirectory zu Start-Job (#10324) (vielen Dank an @davinci26!)</span><span class="sxs-lookup"><span data-stu-id="56a08-361">Add WorkingDirectory parameter to Start-Job (#10324) (Thanks @davinci26!)</span></span>
- <span data-ttu-id="56a08-362">Entfernung des Ereignishandlers, der dazu geführt hat, dass Änderungen an Haltepunkten fälschlicherweise in den Runspacedebugger des Hosts repliziert wurden (#10503) (vielen Dank an @KirkMunro!)</span><span class="sxs-lookup"><span data-stu-id="56a08-362">Remove the event handler that was causing breakpoint changes to be erroneously replicated to the host runspace debugger (#10503) (Thanks @KirkMunro!)</span></span>
- <span data-ttu-id="56a08-363">Austausch von api-ms-win-core-job-12-1-0.dll durch Kernell32.dll in Microsoft.PowerShell.Commands.NativeMethods P/Invoke-API (#10417) (vielen Dank an @iSazonov!)</span><span class="sxs-lookup"><span data-stu-id="56a08-363">Replace api-ms-win-core-job-12-1-0.dll with Kernell32.dll in Microsoft.PowerShell.Commands.NativeMethods P/Invoke API(#10417) (Thanks @iSazonov!)</span></span>
- <span data-ttu-id="56a08-364">Korrektur der falschen Ausgabe für New-Service bei der Variablenzuweisung und -OutVariable (#10444) (vielen Dank an @kvprasoon!)</span><span class="sxs-lookup"><span data-stu-id="56a08-364">Fix wrong output for New-Service in variable assignment and -OutVariable (#10444) (Thanks @kvprasoon!)</span></span>
- <span data-ttu-id="56a08-365">Korrektur globaler Toolprobleme bei Exitcode, Befehlszeilenparameter und Pfad mit Leerzeichen (#10461)</span><span class="sxs-lookup"><span data-stu-id="56a08-365">Fix global tool issues around exit code, command line parameters and path with spaces (#10461)</span></span>
- <span data-ttu-id="56a08-366">Korrektur der Rekursion in OneDrive: Ändern Sie FindFirstFileEx() so, dass der SafeFindHandle-Typ verwendet wird (#10405)</span><span class="sxs-lookup"><span data-stu-id="56a08-366">Fix recursion into OneDrive - change FindFirstFileEx() to use SafeFindHandle type (#10405)</span></span>
- <span data-ttu-id="56a08-367">Überspringen des automatischen Ladens von PSReadLine unter Windows, wenn die NVDA-Sprachausgabe aktiv ist (#10385)</span><span class="sxs-lookup"><span data-stu-id="56a08-367">Skip auto-loading PSReadLine on Windows if the NVDA screen reader is active (#10385)</span></span>
- <span data-ttu-id="56a08-368">Erhöhung der built-with-PowerShell-Modulversionen auf 7.0.0.0 (#10356)</span><span class="sxs-lookup"><span data-stu-id="56a08-368">Increase built-with-PowerShell module versions to 7.0.0.0 (#10356)</span></span>
- <span data-ttu-id="56a08-369">Hinzufügen des Auslösens eines Fehlers in Add-Type, wenn ein Typ mit dem gleichen Namen bereits existiert (#9609) (vielen Dank an @iSazonov!)</span><span class="sxs-lookup"><span data-stu-id="56a08-369">Add throwing an error in Add-Type if a type with the same name already exists (#9609) (Thanks @iSazonov!)</span></span>

### <a name="performance"></a><span data-ttu-id="56a08-370">Leistung</span><span class="sxs-lookup"><span data-stu-id="56a08-370">Performance</span></span>

- <span data-ttu-id="56a08-371">Vermeidung der Verwendung des Abschlusses in Parser.SaveError (#11006)</span><span class="sxs-lookup"><span data-stu-id="56a08-371">Avoid using closure in Parser.SaveError (#11006)</span></span>
- <span data-ttu-id="56a08-372">Verbesserung des Zwischenspeicherns beim Erstellen neuer RegEx-Instanzen (#10657) (vielen Dank an @iSazonov!)</span><span class="sxs-lookup"><span data-stu-id="56a08-372">Improve the caching when creating new Regex instances (#10657) (Thanks @iSazonov!)</span></span>
- <span data-ttu-id="56a08-373">Verbesserte Verarbeitung der in PowerShell integrierten Typdaten aus types.ps1xml, typesV3.ps1xml und GetEvent.types.ps1xml (#10898)</span><span class="sxs-lookup"><span data-stu-id="56a08-373">Improve processing of the PowerShell built-in type data from types.ps1xml, typesV3.ps1xml and GetEvent.types.ps1xml (#10898)</span></span>
- <span data-ttu-id="56a08-374">Aktualisierung von PSConfiguration.ReadValueFromFile, um es schneller und speichereffizienter zu machen (#10839)</span><span class="sxs-lookup"><span data-stu-id="56a08-374">Update PSConfiguration.ReadValueFromFile to make it faster and more memory efficient (#10839)</span></span>
- <span data-ttu-id="56a08-375">Hinzufügung kleinerer Leistungsverbesserungen für die Initialisierung von Runspaces (#10569) (Thanks @iSazonov!)</span><span class="sxs-lookup"><span data-stu-id="56a08-375">Add minor performance improvements for runspace initialization (#10569) (Thanks @iSazonov!)</span></span>
- <span data-ttu-id="56a08-376">Beschleunigung von ForEach-Object in häufig verwendeten Szenarien (#10454) und Behebung des Leistungsproblems mit ForEach-Object -Parallel in vielen Runspaces (#10455)</span><span class="sxs-lookup"><span data-stu-id="56a08-376">Make ForEach-Object faster for its commonly used scenarios (#10454) and fix ForEach-Object -Parallel performance problem with many runspaces (#10455)</span></span>

### <a name="code-cleanup"></a><span data-ttu-id="56a08-377">Codebereinigung</span><span class="sxs-lookup"><span data-stu-id="56a08-377">Code Cleanup</span></span>

- <span data-ttu-id="56a08-378">Änderung von Kommentaren und Elementtexten gemäß Microsoft-Standards (#11304)</span><span class="sxs-lookup"><span data-stu-id="56a08-378">Change comment and element text to meet Microsoft standards (#11304)</span></span>
- <span data-ttu-id="56a08-379">Bereinigung von Stilproblemen in Compiler.cs (#10368) (vielen Dank an @iSazonov!)</span><span class="sxs-lookup"><span data-stu-id="56a08-379">Cleanup style issues in Compiler.cs (#10368) (Thanks @iSazonov!)</span></span>
- <span data-ttu-id="56a08-380">Entfernung des nicht verwendeten Typkonverters für CommaDelimitedStringCollection (#11000) (vielen Dank an @iSazonov!)</span><span class="sxs-lookup"><span data-stu-id="56a08-380">Remove the unused type converter for CommaDelimitedStringCollection (#11000) (Thanks @iSazonov!)</span></span>
- <span data-ttu-id="56a08-381">Bereinigung des Stils in InitialSessionState.cs (#10865) (Thanks @iSazonov!)</span><span class="sxs-lookup"><span data-stu-id="56a08-381">Cleanup style in InitialSessionState.cs (#10865) (Thanks @iSazonov!)</span></span>
- <span data-ttu-id="56a08-382">Codebereinigung für PSSession-Klasse (#11001)</span><span class="sxs-lookup"><span data-stu-id="56a08-382">Code clean up for PSSession class (#11001)</span></span>
- <span data-ttu-id="56a08-383">Entfernung des nicht funktionierenden Features „Update-Help in Get-Help ausführen, wenn Get-Help zum ersten Mal ausgeführt wird“ (#10974)</span><span class="sxs-lookup"><span data-stu-id="56a08-383">Remove the not-working 'run Update-Help from Get-Help when Get-Help runs for the first time' feature (#10974)</span></span>
- <span data-ttu-id="56a08-384">Behebung von Stilproblemen (#10998) (vielen Dank an @iSazonov!)</span><span class="sxs-lookup"><span data-stu-id="56a08-384">Fix style issues (#10998) (Thanks @iSazonov!)</span></span>
- <span data-ttu-id="56a08-385">Bereinigung: Verwenden Sie den integrierten Typalias. (#10882) (vielen Dank an @iSazonov!)</span><span class="sxs-lookup"><span data-stu-id="56a08-385">Cleanup: use the built-in type alias (#10882) (Thanks @iSazonov!)</span></span>
- <span data-ttu-id="56a08-386">Entfernung des nicht verwendeten Einstellungsschlüssels ConsolePrompting und Vermeidung der unnötigen Zeichenfolgenerstellung beim Abfragen der Einstellung ExecutionPolicy (#10985)</span><span class="sxs-lookup"><span data-stu-id="56a08-386">Remove the unused setting key ConsolePrompting and avoid unnecessary string creation when querying ExecutionPolicy setting (#10985)</span></span>
- <span data-ttu-id="56a08-387">Deaktivieren der Updatebenachrichtigungsprüfung für tägliche Builds (#10903) (vielen Dank an @bergmeister!)</span><span class="sxs-lookup"><span data-stu-id="56a08-387">Disable update notification check for daily builds (#10903) (Thanks @bergmeister!)</span></span>
- <span data-ttu-id="56a08-388">Reaktivierung der in #10338 verloren gegangenen Debug-API (#10808)</span><span class="sxs-lookup"><span data-stu-id="56a08-388">Reinstate debugging API lost in #10338 (#10808)</span></span>
- <span data-ttu-id="56a08-389">Entfernung des WorkflowJobSourceAdapter-Verweises, der nicht mehr verwendet wird (#10326) (vielen Dank an @KirkMunro!)</span><span class="sxs-lookup"><span data-stu-id="56a08-389">Remove WorkflowJobSourceAdapter reference that is no longer used (#10326) (Thanks @KirkMunro!)</span></span>
- <span data-ttu-id="56a08-390">Bereinigung von COM-Schnittstellen im Sprunglistencode durch Korrektur von PreserveSig-Attributen (#9899) (vielen Dank an @weltkante!)</span><span class="sxs-lookup"><span data-stu-id="56a08-390">Cleanup COM interfaces in jump list code by fixing PreserveSig attributes (#9899) (Thanks @weltkante!)</span></span>
- <span data-ttu-id="56a08-391">Hinzufügung eines Kommentars, der beschreibt, warum -ia nicht der Alias für den allgemeinen Parameter -InformationAction ist (#10703) (vielen Dank an @KirkMunro!)</span><span class="sxs-lookup"><span data-stu-id="56a08-391">Add a comment describing why -ia is not the alias for -InformationAction common parameter (#10703) (Thanks @KirkMunro!)</span></span>
- <span data-ttu-id="56a08-392">Umbenennung von InvokeCommandCmdlet.cs in InvokeExpressionCommand.cs (#10659) (vielen Dank an @kilasuit!)</span><span class="sxs-lookup"><span data-stu-id="56a08-392">Rename InvokeCommandCmdlet.cs to InvokeExpressionCommand.cs (#10659) (Thanks @kilasuit!)</span></span>
- <span data-ttu-id="56a08-393">Hinzufügung geringfügiger Codebereinigungen im Zusammenhang mit Updatebenachrichtigungen (#10698)</span><span class="sxs-lookup"><span data-stu-id="56a08-393">Add minor code cleanups related to update notifications (#10698)</span></span>
- <span data-ttu-id="56a08-394">Entfernung veralteter Workflowlogik aus den Skripts für das Remotesetup (#10320) (vielen Dank an @KirkMunro!)</span><span class="sxs-lookup"><span data-stu-id="56a08-394">Remove deprecated workflow logic from the remoting setup scripts (#10320) (Thanks @KirkMunro!)</span></span>
- <span data-ttu-id="56a08-395">Aktualisierung des Hilfeformats in die Verwendung der richtigen Schreibweise (#10678) (vielen Dank an @tnieto88!)</span><span class="sxs-lookup"><span data-stu-id="56a08-395">Update help format to use proper case (#10678) (Thanks @tnieto88!)</span></span>
- <span data-ttu-id="56a08-396">Bereinigung von CodeFactor-Stilproblemen bei Commits im letzten Monat (#10591) (vielen Dank an @iSazonov!)</span><span class="sxs-lookup"><span data-stu-id="56a08-396">Clean up CodeFactor style issues coming in commits for the last month (#10591) (Thanks @iSazonov!)</span></span>
- <span data-ttu-id="56a08-397">Korrektur eines Tippfehlers in der Beschreibung des experimentellen Features PSTernaryOperator (#10586) (vielen Dank an @bergmeister!)</span><span class="sxs-lookup"><span data-stu-id="56a08-397">Fix typo in description of PSTernaryOperator experimental feature (#10586) (Thanks @bergmeister!)</span></span>
- <span data-ttu-id="56a08-398">Konvertierung des Enumerationswerts ActionPreference.suspend in einen nicht unterstützten, reservierten Zustand und Aufhebung der Einschränkung für die Verwendung von ActionPreference.Ignore in Einstellungsvariablen (#10317) (vielen Dank an @KirkMunro!)</span><span class="sxs-lookup"><span data-stu-id="56a08-398">Convert ActionPreference.Suspend enumeration value into a non-supported, reserved state, and remove restriction on using ActionPreference.Ignore in preference variables (#10317) (Thanks @KirkMunro!)</span></span>
- <span data-ttu-id="56a08-399">Austausch von ArrayList durch List\<T>, um besser lesbaren und zuverlässigeren Code zu erhalten, ohne Funktionalität zu ändern (#10333) (vielen Dank an @iSazonov!)</span><span class="sxs-lookup"><span data-stu-id="56a08-399">Replace ArrayList with List\<T> to get more readable and reliable code without changing functionality (#10333) (Thanks @iSazonov!)</span></span>
- <span data-ttu-id="56a08-400">Korrekturen am Codestil für TestConnectionCommand (#10439) (vielen Dank an @vexx32!)</span><span class="sxs-lookup"><span data-stu-id="56a08-400">Make code style fixes to TestConnectionCommand (#10439) (Thanks @vexx32!)</span></span>
- <span data-ttu-id="56a08-401">Bereinigung von AutomationEngine und Entfernung des zusätzlichen Aufrufs der SetSessionStateDrive-Methode (#10416) (vielen Dank an @iSazonov!)</span><span class="sxs-lookup"><span data-stu-id="56a08-401">Cleanup AutomationEngine and remove extra SetSessionStateDrive method call (#10416) (Thanks @iSazonov!)</span></span>
- <span data-ttu-id="56a08-402">Umbenennung der Standardeinstellung ParameterSetName zurück in Delimiter für ConvertTo-Csv und ConvertFrom-Csv (#10425)</span><span class="sxs-lookup"><span data-stu-id="56a08-402">Rename default ParameterSetName back to Delimiter for ConvertTo-Csv and ConvertFrom-Csv (#10425)</span></span>

### <a name="tools"></a><span data-ttu-id="56a08-403">Tools</span><span class="sxs-lookup"><span data-stu-id="56a08-403">Tools</span></span>

- <span data-ttu-id="56a08-404">Hinzufügung einer Standardeinstellung für die SDKToUse-Eigenschaft für Builds in VS (#11085)</span><span class="sxs-lookup"><span data-stu-id="56a08-404">Add default setting for the SDKToUse property so that it builds in VS (#11085)</span></span>
- <span data-ttu-id="56a08-405">Install-Powershell.ps1: Hinzufügung eines Parameters, um die MSI-Installation zu verwenden (#10921) (vielen Dank an @MJECloud!)</span><span class="sxs-lookup"><span data-stu-id="56a08-405">Install-Powershell.ps1: Add parameter to use MSI installation (#10921) (Thanks @MJECloud!)</span></span>
- <span data-ttu-id="56a08-406">Hinzufügung einfacher Beispiele für install-powershell.ps1 (#10914) (vielen Dank an @kilasuit!)</span><span class="sxs-lookup"><span data-stu-id="56a08-406">Add basic examples for install-powershell.ps1 (#10914) (Thanks @kilasuit!)</span></span>
- <span data-ttu-id="56a08-407">Veranlassen, dass Install-PowerShellRemoting.ps1 eine leere Zeichenfolge im PowerShellHome-Parameter behandelt (#10526) (vielen Dank an @Orca88!)</span><span class="sxs-lookup"><span data-stu-id="56a08-407">Make Install-PowerShellRemoting.ps1 handle empty string in PowerShellHome parameter (#10526) (Thanks @Orca88!)</span></span>
- <span data-ttu-id="56a08-408">Wechsel von /etc/lsb-release zu /etc/os-release in install-powershell.sh (#10773) (vielen Dank an @Himura2la!)</span><span class="sxs-lookup"><span data-stu-id="56a08-408">Switch from /etc/lsb-release to /etc/os-release in install-powershell.sh (#10773) (Thanks @Himura2la!)</span></span>
- <span data-ttu-id="56a08-409">Überprüfung von pwsh.exe und pwsh in täglicher Version unter Windows (#10738) (vielen Dank an @centreboard!)</span><span class="sxs-lookup"><span data-stu-id="56a08-409">Check pwsh.exe and pwsh in daily version on Windows (#10738) (Thanks @centreboard!)</span></span>
- <span data-ttu-id="56a08-410">Entfernen von unnötigem Tippen aus installpsh-osx.sh (#10752)</span><span class="sxs-lookup"><span data-stu-id="56a08-410">Remove unneeded tap in installpsh-osx.sh (#10752)</span></span>
- <span data-ttu-id="56a08-411">Aktualisierung von install-powershell.ps1 zur Überprüfung auf bereits installierte tägliche Builds (#10489)</span><span class="sxs-lookup"><span data-stu-id="56a08-411">Update install-powershell.ps1 to check for already installed daily build (#10489)</span></span>

### <a name="tests"></a><span data-ttu-id="56a08-412">Tests</span><span class="sxs-lookup"><span data-stu-id="56a08-412">Tests</span></span>

- <span data-ttu-id="56a08-413">Unzuverlässigen DSC-Test ausstehend gestalten (#11131)</span><span class="sxs-lookup"><span data-stu-id="56a08-413">Make unreliable DSC test pending (#11131)</span></span>
- <span data-ttu-id="56a08-414">Korrektur des Tests von Zeichenfolgendaten für die ordnungsgemäße Validierung von Schlüsseln von Hashtabellen (#10810)</span><span class="sxs-lookup"><span data-stu-id="56a08-414">Fix stringdata test to correctly validate keys of hashtables (#10810)</span></span>
- <span data-ttu-id="56a08-415">Entladung von Testmodulen (#11061) (vielen Dank an @iSazonov!)</span><span class="sxs-lookup"><span data-stu-id="56a08-415">Unload test modules (#11061) (Thanks @iSazonov!)</span></span>
- <span data-ttu-id="56a08-416">Verlängerung der Zeit zwischen Wiederholungen der Test-URL (#11015)</span><span class="sxs-lookup"><span data-stu-id="56a08-416">Increase time between retries of testing URL (#11015)</span></span>
- <span data-ttu-id="56a08-417">Aktualisieren vom Tests, um Testaktionen genau zu beschreiben.</span><span class="sxs-lookup"><span data-stu-id="56a08-417">Update tests to accurately describe test actions.</span></span> <span data-ttu-id="56a08-418">(#10928) (vielen Dank an @romero126!)</span><span class="sxs-lookup"><span data-stu-id="56a08-418">(#10928) (Thanks @romero126!)</span></span>
- <span data-ttu-id="56a08-419">Temporäres Überspringen des unzuverlässigen Tests TestAppDomainProcessExitEvenHandlerNotLeaking (#10827)</span><span class="sxs-lookup"><span data-stu-id="56a08-419">Temporary skip the flaky test TestAppDomainProcessExitEvenHandlerNotLeaking (#10827)</span></span>
- <span data-ttu-id="56a08-420">Stabilisierung des Ereignishandlertests auf Lecks (#10790)</span><span class="sxs-lookup"><span data-stu-id="56a08-420">Make the event handler leaking test stable (#10790)</span></span>
- <span data-ttu-id="56a08-421">Synchronisieren der Großbeschreibung in CI YAML (#10767) (vielen Dank an @RDIL!)</span><span class="sxs-lookup"><span data-stu-id="56a08-421">Sync capitalization in CI YAML (#10767) (Thanks @RDIL!)</span></span>
- <span data-ttu-id="56a08-422">Hinzufügung eines Tests für die Korrektur des Ereignishandlerlecks (#10768)</span><span class="sxs-lookup"><span data-stu-id="56a08-422">Add test for the event handler leaking fix (#10768)</span></span>
- <span data-ttu-id="56a08-423">Hinzufügung eines Tests von Get-ChildItem (#10507) (vielen Dank an @iSazonov!)</span><span class="sxs-lookup"><span data-stu-id="56a08-423">Add Get-ChildItem test (#10507) (Thanks @iSazonov!)</span></span>
- <span data-ttu-id="56a08-424">Ersetzung mehrdeutiger Sprache für Tests von Schalter zu Parameter für Genauigkeit (#10666) (vielen Dank an @romero126!)</span><span class="sxs-lookup"><span data-stu-id="56a08-424">Replace ambiguous language for tests from switch to parameter for accuracy (#10666) (Thanks @romero126!)</span></span>
- <span data-ttu-id="56a08-425">Hinzufügung einer experimentellen Prüfung zu Tests von ForEach-Object -Parallel (#10354) (vielen Dank an @KirkMunro!)</span><span class="sxs-lookup"><span data-stu-id="56a08-425">Add experimental check to ForEach-Object -Parallel tests (#10354) (Thanks @KirkMunro!)</span></span>
- <span data-ttu-id="56a08-426">Aktualisierung von Tests für Alpine-Validierung (#10428)</span><span class="sxs-lookup"><span data-stu-id="56a08-426">Update tests for Alpine validation (#10428)</span></span>

### <a name="build-and-package-improvements"></a><span data-ttu-id="56a08-427">Verbesserungen von Build- und Packvorgängen</span><span class="sxs-lookup"><span data-stu-id="56a08-427">Build and Package Improvements</span></span>

- <span data-ttu-id="56a08-428">Korrektur der Signierung von NuGet-Paketen für den Coordinated Package-Build (#11316)</span><span class="sxs-lookup"><span data-stu-id="56a08-428">Fix Nuget package signing for Coordinated Package build (#11316)</span></span>
- <span data-ttu-id="56a08-429">Aktualisierung von Abhängigkeiten in PowerShell-Katalog und NuGet (#11323)</span><span class="sxs-lookup"><span data-stu-id="56a08-429">Update dependencies from PowerShell Gallery and NuGet (#11323)</span></span>
- <span data-ttu-id="56a08-430">Aktualisierung von Microsoft.ApplicationInsights von 2.11.0 auf 2.12.0 (#11305)</span><span class="sxs-lookup"><span data-stu-id="56a08-430">Bump Microsoft.ApplicationInsights from 2.11.0 to 2.12.0 (#11305)</span></span>
- <span data-ttu-id="56a08-431">Aktualisierung vonMicrosoft.CodeAnalysis.CSharp von 3.3.1 auf 3.4.0 (#11265)</span><span class="sxs-lookup"><span data-stu-id="56a08-431">Bump Microsoft.CodeAnalysis.CSharp from 3.3.1 to 3.4.0 (#11265)</span></span>
- <span data-ttu-id="56a08-432">Aktualisierung von Paketen für Debian 10 und 11 (#11236)</span><span class="sxs-lookup"><span data-stu-id="56a08-432">Updates packages for Debian 10 and 11 (#11236)</span></span>
- <span data-ttu-id="56a08-433">Ausschließliches Aktivieren experimenteller Funktionen vor RC (#11162)</span><span class="sxs-lookup"><span data-stu-id="56a08-433">Only enable experimental features prior to RC (#11162)</span></span>
- <span data-ttu-id="56a08-434">Aktualisierung der Mindestversion von macOS (#11163)</span><span class="sxs-lookup"><span data-stu-id="56a08-434">Update macOS minimum version (#11163)</span></span>
- <span data-ttu-id="56a08-435">Aktualisierung von NJsonSchema von 10.0.27 auf 10.0.28 (#11170)</span><span class="sxs-lookup"><span data-stu-id="56a08-435">Bump NJsonSchema from 10.0.27 to 10.0.28 (#11170)</span></span>
- <span data-ttu-id="56a08-436">Aktualisierung von Links in README.md und metadata.json für Preview.5 (#10854)</span><span class="sxs-lookup"><span data-stu-id="56a08-436">Updating links in README.md and metadata.json for Preview.5 (#10854)</span></span>
- <span data-ttu-id="56a08-437">Auswählen der Dateien für Konformitätstests, die im Besitz von PowerShell sind (#10837)</span><span class="sxs-lookup"><span data-stu-id="56a08-437">Select the files for compliance tests which are owned by PowerShell (#10837)</span></span>
- <span data-ttu-id="56a08-438">Ermöglichung des Erstellens eines win7x86-msix-Pakets.</span><span class="sxs-lookup"><span data-stu-id="56a08-438">Allow win7x86 msix package to build.</span></span> <span data-ttu-id="56a08-439">(10515 intern)</span><span class="sxs-lookup"><span data-stu-id="56a08-439">(Internal 10515)</span></span>
- <span data-ttu-id="56a08-440">Zulassen, dass semantische Versionen an die Funktion NormalizeVersion übergeben werden (#11087)</span><span class="sxs-lookup"><span data-stu-id="56a08-440">Allow semantic versions to be passed to NormalizeVersion function (#11087)</span></span>
- <span data-ttu-id="56a08-441">Aktualisierung von .NET Core-Framework auf 3.1-preview.3 (#11079)</span><span class="sxs-lookup"><span data-stu-id="56a08-441">Bump .NET core framework to 3.1-preview.3 (#11079)</span></span>
- <span data-ttu-id="56a08-442">Aktualisierung von PSReadLine von 2.0.0-beta5 auf 2.0.0-beta6 in /src/Modules (#11078)</span><span class="sxs-lookup"><span data-stu-id="56a08-442">Bump PSReadLine from 2.0.0-beta5 to 2.0.0-beta6 in /src/Modules (#11078)</span></span>
- <span data-ttu-id="56a08-443">Aktualisierung von Newtonsoft.Json von 12.0.2 auf 12.0.3 (#11037) (#11038)</span><span class="sxs-lookup"><span data-stu-id="56a08-443">Bump Newtonsoft.Json from 12.0.2 to 12.0.3 (#11037) (#11038)</span></span>
- <span data-ttu-id="56a08-444">Hinzufügung von Debian 10-, 11-und CentOS 8-Paketen (#11028)</span><span class="sxs-lookup"><span data-stu-id="56a08-444">Add Debian 10, 11 and CentOS 8 packages (#11028)</span></span>
- <span data-ttu-id="56a08-445">Hochladen von JSON-Datei mit Build-Info mit dem Feld ReleaseDate (#10986)</span><span class="sxs-lookup"><span data-stu-id="56a08-445">Upload Build-Info Json file with the ReleaseDate field (#10986)</span></span>
- <span data-ttu-id="56a08-446">Aktualisierung von .NET Core-Framework auf 3.1-preview.2 (#10993)</span><span class="sxs-lookup"><span data-stu-id="56a08-446">Bump .NET core framework to 3.1-preview.2 (#10993)</span></span>
- <span data-ttu-id="56a08-447">Aktivierung des Builds des x86-MSIX-Pakets (#10934)</span><span class="sxs-lookup"><span data-stu-id="56a08-447">Enable build of x86 MSIX package (#10934)</span></span>
- <span data-ttu-id="56a08-448">Aktualisierung der URL des .SDK-Installationsskripts in build.psm1 (#10927)</span><span class="sxs-lookup"><span data-stu-id="56a08-448">Update the dotnet SDK install script URL in build.psm1 (#10927)</span></span>
- <span data-ttu-id="56a08-449">Aktualisierung von Markdig.Signed von 0.17.1 auf 0.18.0 (#10887)</span><span class="sxs-lookup"><span data-stu-id="56a08-449">Bump Markdig.Signed from 0.17.1 to 0.18.0 (#10887)</span></span>
- <span data-ttu-id="56a08-450">Aktualisierung von ThreadJob von 2.0.1 auf 2.0.2 (#10886)</span><span class="sxs-lookup"><span data-stu-id="56a08-450">Bump ThreadJob from 2.0.1 to 2.0.2 (#10886)</span></span>
- <span data-ttu-id="56a08-451">Aktualisierung von AppX Manifest und des Packaging-Moduls entsprechend den Microsoft Store-Anforderungen (#10878)</span><span class="sxs-lookup"><span data-stu-id="56a08-451">Update AppX Manifest and Packaging module to conform to MS Store requirements (#10878)</span></span>
- <span data-ttu-id="56a08-452">Aktualisierung des Paketverweises für das PowerShell SDK in preview.5 (10295 intern)</span><span class="sxs-lookup"><span data-stu-id="56a08-452">Update package reference for PowerShell SDK to preview.5 (Internal 10295)</span></span>
- <span data-ttu-id="56a08-453">Aktualisierung von ThirdPartyNotices.txt (#10834)</span><span class="sxs-lookup"><span data-stu-id="56a08-453">Update ThirdPartyNotices.txt (#10834)</span></span>
- <span data-ttu-id="56a08-454">Aktualisierung von Microsoft.PowerShell.Native auf 7.0.0-preview.3 (#10826)</span><span class="sxs-lookup"><span data-stu-id="56a08-454">Bump Microsoft.PowerShell.Native to 7.0.0-preview.3 (#10826)</span></span>
- <span data-ttu-id="56a08-455">Aktualisierung von Microsoft.ApplicationInsights von 2.10.0 auf 2.11.0 (#10608)</span><span class="sxs-lookup"><span data-stu-id="56a08-455">Bump Microsoft.ApplicationInsights from 2.10.0 to 2.11.0 (#10608)</span></span>
- <span data-ttu-id="56a08-456">Aktualisierung von NJsonSchema von 10.0.24 auf 10.0.27 (#10756)</span><span class="sxs-lookup"><span data-stu-id="56a08-456">Bump NJsonSchema from 10.0.24 to 10.0.27 (#10756)</span></span>
- <span data-ttu-id="56a08-457">Hinzufügung der Unterstützung von MacPorts zum Buildsystem (#10736) (vielen Dank an @Lucius-Q-User!)</span><span class="sxs-lookup"><span data-stu-id="56a08-457">Add MacPorts support to the build system (#10736) (Thanks @Lucius-Q-User!)</span></span>
- <span data-ttu-id="56a08-458">Aktualisierung von PackageManagement von 1.4.4 auf 1.4.5 (#10728)</span><span class="sxs-lookup"><span data-stu-id="56a08-458">Bump PackageManagement from 1.4.4 to 1.4.5 (#10728)</span></span>
- <span data-ttu-id="56a08-459">Aktualisierung von NJsonSchema von 10.0.23 auf 10.0.24 (#10635)</span><span class="sxs-lookup"><span data-stu-id="56a08-459">Bump NJsonSchema from 10.0.23 to 10.0.24 (#10635)</span></span>
- <span data-ttu-id="56a08-460">Hinzufügung einer Umgebungsvariablen zur Unterscheidung von Client-/Servertelemetrie in MSI (#10612)</span><span class="sxs-lookup"><span data-stu-id="56a08-460">Add environment variable to differentiate client/server telemetry in MSI (#10612)</span></span>
- <span data-ttu-id="56a08-461">Aktualisierung von PSDesiredStateConfiguration von 2.0.3 auf 2.0.4 (#10603)</span><span class="sxs-lookup"><span data-stu-id="56a08-461">Bump PSDesiredStateConfiguration from 2.0.3 to 2.0.4 (#10603)</span></span>
- <span data-ttu-id="56a08-462">Aktualisierung vonMicrosoft.CodeAnalysis.CSharp von 3.2.1 auf 3.3.1 (#10607)</span><span class="sxs-lookup"><span data-stu-id="56a08-462">Bump Microsoft.CodeAnalysis.CSharp from 3.2.1 to 3.3.1 (#10607)</span></span>
- <span data-ttu-id="56a08-463">Aktualisierung von .Net Core 3.0 RTM (#10604) (vielen Dank an @bergmeister!)</span><span class="sxs-lookup"><span data-stu-id="56a08-463">Update to .Net Core 3.0 RTM (#10604) (Thanks @bergmeister!)</span></span>
- <span data-ttu-id="56a08-464">Aktualisierung der Erstellung von MSIX-Paketen entsprechend den Microsoft Store-Anforderungen (#10588)</span><span class="sxs-lookup"><span data-stu-id="56a08-464">Update MSIX packaging so the version to Windows Store requirements (#10588)</span></span>
- <span data-ttu-id="56a08-465">Aktualisierung der PowerShellGet-Version von 2.2 auf 2.2.1 (#10382)</span><span class="sxs-lookup"><span data-stu-id="56a08-465">Bump PowerShellGet version from 2.2 to 2.2.1 (#10382)</span></span>
- <span data-ttu-id="56a08-466">Aktualisierung der PackageManagement-Version von 1.4.3 auf 1.4.4 (#10383)</span><span class="sxs-lookup"><span data-stu-id="56a08-466">Bump PackageManagement version from 1.4.3 to 1.4.4 (#10383)</span></span>
- <span data-ttu-id="56a08-467">Aktualisierung von README.md und metadata.json für 7.0.0-preview.4 (10011 intern)</span><span class="sxs-lookup"><span data-stu-id="56a08-467">Update README.md and metadata.json for 7.0.0-preview.4 (Internal 10011)</span></span>
- <span data-ttu-id="56a08-468">Aktualisierung der .Net Core 3.0-Version von Preview 9 auf RC1 (#10552) (vielen Dank an @bergmeister!)</span><span class="sxs-lookup"><span data-stu-id="56a08-468">Upgrade .Net Core 3.0 version from Preview 9 to RC1 (#10552) (Thanks @bergmeister!)</span></span>
- <span data-ttu-id="56a08-469">Korrektur der Listengenerierung für ExperimentalFeature (intern 9996)</span><span class="sxs-lookup"><span data-stu-id="56a08-469">Fix ExperimentalFeature list generation (Internal 9996)</span></span>
- <span data-ttu-id="56a08-470">Aktualisierung der PSReadLine-Version von 2.0.0-beta4 auf 2.0.0-beta5 (#10536)</span><span class="sxs-lookup"><span data-stu-id="56a08-470">Bump PSReadLine version from 2.0.0-beta4 to 2.0.0-beta5 (#10536)</span></span>
- <span data-ttu-id="56a08-471">Korrektur des Releasebuildskripts zum Festlegen des Releasetags</span><span class="sxs-lookup"><span data-stu-id="56a08-471">Fix release build script to set release tag</span></span>
- <span data-ttu-id="56a08-472">Aktualisierung von Microsoft.PowerShell.Native auf 7.0.0-preview.2 (#10519)</span><span class="sxs-lookup"><span data-stu-id="56a08-472">Update version of Microsoft.PowerShell.Native to 7.0.0-preview.2 (#10519)</span></span>
- <span data-ttu-id="56a08-473">Aktualisierung auf Netcoreapp3.0 preview9 (#10484) (vielen Dank an @bergmeister!)</span><span class="sxs-lookup"><span data-stu-id="56a08-473">Upgrade to Netcoreapp3.0 preview9 (#10484) (Thanks @bergmeister!)</span></span>
- <span data-ttu-id="56a08-474">Sicherstellung, dass der täglich koordinierte Build weiß, dass es sich um einen täglichen Build handelt (#10464)</span><span class="sxs-lookup"><span data-stu-id="56a08-474">Make sure the daily coordinated build, knows it is a daily build (#10464)</span></span>
- <span data-ttu-id="56a08-475">Aktualisierung des kombinierten Paketbuilds dahingehend, dass die täglichen Builds freigegeben werden (#10449)</span><span class="sxs-lookup"><span data-stu-id="56a08-475">Update the combined package build to release the daily builds (#10449)</span></span>
- <span data-ttu-id="56a08-476">Entfernung des Verweises auf appveyor (#10445) (vielen Dank an @RDIL!)</span><span class="sxs-lookup"><span data-stu-id="56a08-476">Remove appveyor reference (#10445) (Thanks @RDIL!)</span></span>
- <span data-ttu-id="56a08-477">Aktualisierung von NJsonSchema von 10.0.22 auf 10.0.23 (#10421)</span><span class="sxs-lookup"><span data-stu-id="56a08-477">Bump NJsonSchema version from 10.0.22 to 10.0.23 (#10421)</span></span>
- <span data-ttu-id="56a08-478">Entfernung der Löschung des Buildordners linux-x64, da einige Abhängigkeiten für Alpine ihn benötigen (#10407)</span><span class="sxs-lookup"><span data-stu-id="56a08-478">Remove the deletion of linux-x64 build folder because some dependencies for Alpine need it (#10407)</span></span>

### <a name="documentation-and-help-content"></a><span data-ttu-id="56a08-479">Dokumentation und Inhalt der Hilfe</span><span class="sxs-lookup"><span data-stu-id="56a08-479">Documentation and Help Content</span></span>

- <span data-ttu-id="56a08-480">Umgestaltung von Änderungsprotokollen in ein Protokoll pro Release (#11165)</span><span class="sxs-lookup"><span data-stu-id="56a08-480">Refactor change logs into one log per release (#11165)</span></span>
- <span data-ttu-id="56a08-481">Korrektur von FWLinks für Onlinehilfedokumente für PowerShell 7 (#11071)</span><span class="sxs-lookup"><span data-stu-id="56a08-481">Fix FWLinks for PowerShell 7 online help documents (#11071)</span></span>
- <span data-ttu-id="56a08-482">Aktualisierung von CONTRIBUTING.MD (#11096) (vielen Dank an @mklement0!)</span><span class="sxs-lookup"><span data-stu-id="56a08-482">Update CONTRIBUTING.md (#11096) (Thanks @mklement0!)</span></span>
- <span data-ttu-id="56a08-483">Korrektur von Links zu Installationsdokumenten in README.MD (#11083)</span><span class="sxs-lookup"><span data-stu-id="56a08-483">Fix installation doc links in README.md (#11083)</span></span>
- <span data-ttu-id="56a08-484">Hinzufügung von Beispielen zum Skript install-powershell.ps1 (#11024) (vielen Dank an @kilasuit!)</span><span class="sxs-lookup"><span data-stu-id="56a08-484">Adds examples to install-powershell.ps1 script (#11024) (Thanks @kilasuit!)</span></span>
- <span data-ttu-id="56a08-485">Korrektur für Hervorhebung von Select-String und Import-DscResource in CHANGELOG.md (#10890)</span><span class="sxs-lookup"><span data-stu-id="56a08-485">Fix to Select-String emphasis and Import-DscResource in CHANGELOG.md (#10890)</span></span>
- <span data-ttu-id="56a08-486">Entfernung des veralteten Links aus powershell-beginners-guide.md (#10926)</span><span class="sxs-lookup"><span data-stu-id="56a08-486">Remove the stale link from powershell-beginners-guide.md (#10926)</span></span>
- <span data-ttu-id="56a08-487">Merge stabiler Branches und Wartung von Änderungsprotokollen (#10527)</span><span class="sxs-lookup"><span data-stu-id="56a08-487">Merge stable and servicing change logs (#10527)</span></span>
- <span data-ttu-id="56a08-488">Aktualisierung der verwendeten .NET-Version in Builddokumenten (#10775) (vielen Dank an @Greg-Smulko!)</span><span class="sxs-lookup"><span data-stu-id="56a08-488">Update used .NET version in build docs (#10775) (Thanks @Greg-Smulko!)</span></span>
- <span data-ttu-id="56a08-489">Austausch von Links aus MSDN zu docs.microsoft.com in powershell-beginners-guide.md (#10778) (vielen Dank an @iSazonov!)</span><span class="sxs-lookup"><span data-stu-id="56a08-489">Replace links from MSDN to docs.microsoft.com in powershell-beginners-guide.md (#10778) (Thanks @iSazonov!)</span></span>
- <span data-ttu-id="56a08-490">Korrektur eines fehlerhaften Links zur DSC-Übersicht (#10702)</span><span class="sxs-lookup"><span data-stu-id="56a08-490">Fix broken DSC overview link (#10702)</span></span>
- <span data-ttu-id="56a08-491">Aktualisierung von Support_Question.md mit einem Link zu Stack Overflow als weitere Communityressource (#10638) (vielen Dank an @mklement0!)</span><span class="sxs-lookup"><span data-stu-id="56a08-491">Update Support_Question.md to link to Stack Overflow as another community resource (#10638) (Thanks @mklement0!)</span></span>
- <span data-ttu-id="56a08-492">Hinzufügung der Prozessorarchitektur zur Verteilungsanforderungsvorlage (#10661)</span><span class="sxs-lookup"><span data-stu-id="56a08-492">Add processor architecture to distribution request template (#10661)</span></span>
- <span data-ttu-id="56a08-493">Hinzufügung eines neuen PowerShell MoL-Buchs zu Dokumenten zum Erlernen von PowerShell (#10602)</span><span class="sxs-lookup"><span data-stu-id="56a08-493">Add new PowerShell MoL book to learning PowerShell docs (#10602)</span></span>
- <span data-ttu-id="56a08-494">Aktualisierung von README.md und Metadaten für v6.1.6 and v6.2.3 (#10523)</span><span class="sxs-lookup"><span data-stu-id="56a08-494">Update README.md and metadata for v6.1.6 and v6.2.3 releases (#10523)</span></span>
- <span data-ttu-id="56a08-495">Korrektur eines Tippfehlers in README.md (#10465) (vielen Dank an @vedhasp!)</span><span class="sxs-lookup"><span data-stu-id="56a08-495">Fix a typo in README.md (#10465) (Thanks @vedhasp!)</span></span>
- <span data-ttu-id="56a08-496">Hinzufügung eines Verweises auf das Modul PSKoans zur Dokumentation für Lernressourcen (#10369) (vielen Dank an @vexx32!)</span><span class="sxs-lookup"><span data-stu-id="56a08-496">Add a reference to PSKoans module to Learning Resources documentation (#10369) (Thanks @vexx32!)</span></span>
- <span data-ttu-id="56a08-497">Aktualisierung von README.md und metadata.json für 7.0.0-preview.3 (#10393)</span><span class="sxs-lookup"><span data-stu-id="56a08-497">Update README.md and metadata.json for 7.0.0-preview.3 (#10393)</span></span>
