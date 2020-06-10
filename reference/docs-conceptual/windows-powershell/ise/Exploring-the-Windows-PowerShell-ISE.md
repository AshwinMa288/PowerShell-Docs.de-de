---
ms.date: 01/02/2020
keywords: powershell,cmdlet
title: Kennenlernen der Windows PowerShell ISE
ms.openlocfilehash: 03728a8c83962894b27738609a5b1bec841fdb13
ms.sourcegitcommit: 2aec310ad0c0b048400cb56f6fa64c1e554c812a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/23/2020
ms.locfileid: "83809826"
---
# <a name="exploring-the-windows-powershell-ise"></a><span data-ttu-id="87a22-103">Kennenlernen der Windows PowerShell ISE</span><span class="sxs-lookup"><span data-stu-id="87a22-103">Exploring the Windows PowerShell ISE</span></span>

<span data-ttu-id="87a22-104">Sie können Windows PowerShell® Integrated Scripting Environment (ISE) verwenden, um Befehle und Skripts zu erstellen, auszuführen und zu debuggen.</span><span class="sxs-lookup"><span data-stu-id="87a22-104">You can use the Windows PowerShell® Integrated Scripting Environment (ISE) to create, run, and debug commands and scripts.</span></span> <span data-ttu-id="87a22-105">Windows PowerShell ISE besteht aus der Menüleiste, den Windows PowerShell-Registerkarten, der Symbolleiste, den Skriptregisterkarten, dem Skriptbereich, dem Konsolenbereich, der Statusleiste, dem Schieberegler für die Textgröße und der kontextbezogenen Hilfe.</span><span class="sxs-lookup"><span data-stu-id="87a22-105">The Windows PowerShell ISE consists of the menu bar, Windows PowerShell tabs, the toolbar, script tabs, a Script Pane, a Console Pane, a status bar, a text-size slider and context-sensitive Help.</span></span>

> [!NOTE]
> <span data-ttu-id="87a22-106">Ab Windows PowerShell ISE 3.0 wurden der Befehls- und der Ausgabebereich in Form des zentralen Konsolenbereichs zusammengeführt.</span><span class="sxs-lookup"><span data-stu-id="87a22-106">Beginning with Windows PowerShell ISE 3.0 the Command and Output Panes were combined into a single Console Pane.</span></span>

## <a name="menu-bar"></a><span data-ttu-id="87a22-107">Menüleiste</span><span class="sxs-lookup"><span data-stu-id="87a22-107">Menu Bar</span></span>

<span data-ttu-id="87a22-108">Die Menüleiste enthält die Menüs **Datei**, **Bearbeiten**, **Ansicht**, **Tools**, **Debuggen**, **Add-Ons** und **Hilfe**.</span><span class="sxs-lookup"><span data-stu-id="87a22-108">The menu bar contains the **File**, **Edit**, **View**, **Tools**, **Debug**, **Add-ons**, and **Help** menus.</span></span> <span data-ttu-id="87a22-109">Über die Schaltflächen in den Menüs können Sie Aufgaben erledigen, die im Zusammenhang mit dem Schreiben und Ausführen von Skripts und Ausführen von Befehlen in der Windows PowerShell ISE stehen.</span><span class="sxs-lookup"><span data-stu-id="87a22-109">The buttons on the menus allow you to perform tasks related to writing and running scripts and running commands in the Windows PowerShell ISE.</span></span> <span data-ttu-id="87a22-110">Darüber hinaus kann ein [Add-On-Tool](object-model/The-ISEAddOnTool-Object.md) auf der Menüleiste platziert werden, indem Skripts ausgeführt werden, die die [ISE-Objektmodellhierarchie](object-model/The-ISE-Object-Model-Hierarchy.md) verwenden.</span><span class="sxs-lookup"><span data-stu-id="87a22-110">Additionally, an [add-on tool](object-model/The-ISEAddOnTool-Object.md) may be placed on the menu bar by running scripts that use the [The ISE Object Model Hierarchy](object-model/The-ISE-Object-Model-Hierarchy.md).</span></span>

> [!NOTE]
> <span data-ttu-id="87a22-111">In Windows PowerShell ISE 2.0 gab es die Menüs **Tools** und **Add-Ons** nicht.</span><span class="sxs-lookup"><span data-stu-id="87a22-111">In Windows PowerShell ISE 2.0, The **Tools** and **Add-ons** menus were not present.</span></span>

## <a name="windows-powershell-tabs"></a><span data-ttu-id="87a22-112">Windows PowerShell-Registerkarten</span><span class="sxs-lookup"><span data-stu-id="87a22-112">Windows PowerShell Tabs</span></span>

<span data-ttu-id="87a22-113">Eine Windows PowerShell-Registerkarte ist die Umgebung, in der ein Windows PowerShell-Skript ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="87a22-113">A Windows PowerShell tab is the environment in which a Windows PowerShell script runs.</span></span> <span data-ttu-id="87a22-114">Sie können neue Windows PowerShell-Registerkarten in der Windows PowerShell ISE öffnen, um auf dem lokalen Computer oder auf Remotecomputern getrennte Umgebungen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="87a22-114">You can open new Windows PowerShell tabs in the Windows PowerShell ISE to create separate environments on your local computer or on remote computers.</span></span> <span data-ttu-id="87a22-115">Gleichzeitig können maximal acht PowerShell-Registerkarten geöffnet sein.</span><span class="sxs-lookup"><span data-stu-id="87a22-115">You may have a maximum of eight PowerShell tabs simultaneously open.</span></span>

## <a name="toolbar"></a><span data-ttu-id="87a22-116">Symbolleiste</span><span class="sxs-lookup"><span data-stu-id="87a22-116">Toolbar</span></span>

<span data-ttu-id="87a22-117">Die folgenden Schaltflächen befinden sich auf der Symbolleiste.</span><span class="sxs-lookup"><span data-stu-id="87a22-117">The following buttons are located on the toolbar.</span></span>

|             <span data-ttu-id="87a22-118">Taste</span><span class="sxs-lookup"><span data-stu-id="87a22-118">Button</span></span>             |                                                                                     <span data-ttu-id="87a22-119">Funktion</span><span class="sxs-lookup"><span data-stu-id="87a22-119">Function</span></span>                                                                                     |
| ------------------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| <span data-ttu-id="87a22-120">**Neu**</span><span class="sxs-lookup"><span data-stu-id="87a22-120">**New**</span></span>                        | <span data-ttu-id="87a22-121">Öffnet ein neues Skript.</span><span class="sxs-lookup"><span data-stu-id="87a22-121">Opens a new script.</span></span>                                                                                                                                                              |
| <span data-ttu-id="87a22-122">**Öffnen**</span><span class="sxs-lookup"><span data-stu-id="87a22-122">**Open**</span></span>                       | <span data-ttu-id="87a22-123">Öffnet ein vorhandenes Skript oder eine Datei.</span><span class="sxs-lookup"><span data-stu-id="87a22-123">Opens an existing script or file.</span></span>                                                                                                                                                |
| <span data-ttu-id="87a22-124">**Speichern**</span><span class="sxs-lookup"><span data-stu-id="87a22-124">**Save**</span></span>                       | <span data-ttu-id="87a22-125">Speichert ein Skript oder eine Datei.</span><span class="sxs-lookup"><span data-stu-id="87a22-125">Saves a script or file.</span></span>                                                                                                                                                          |
| <span data-ttu-id="87a22-126">**Ausschneiden**</span><span class="sxs-lookup"><span data-stu-id="87a22-126">**Cut**</span></span>                        | <span data-ttu-id="87a22-127">Schneidet den ausgewählten Text aus und kopiert ihn in die Zwischenablage.</span><span class="sxs-lookup"><span data-stu-id="87a22-127">Cuts the selected text and copies it to the clipboard.</span></span>                                                                                                                           |
| <span data-ttu-id="87a22-128">**Copy**</span><span class="sxs-lookup"><span data-stu-id="87a22-128">**Copy**</span></span>                       | <span data-ttu-id="87a22-129">Kopiert den ausgewählten Text in die Zwischenablage.</span><span class="sxs-lookup"><span data-stu-id="87a22-129">Copies the selected text to the clipboard.</span></span>                                                                                                                                       |
| <span data-ttu-id="87a22-130">**Einfügen**</span><span class="sxs-lookup"><span data-stu-id="87a22-130">**Paste**</span></span>                      | <span data-ttu-id="87a22-131">Fügt den Inhalt der Zwischenablage an der Cursorposition ein.</span><span class="sxs-lookup"><span data-stu-id="87a22-131">Pastes the contents of the clipboard at the cursor location.</span></span>                                                                                                                     |
| <span data-ttu-id="87a22-132">**Ausgabebereich löschen**</span><span class="sxs-lookup"><span data-stu-id="87a22-132">**Clear Output Pane**</span></span>          | <span data-ttu-id="87a22-133">Löscht den gesamten Inhalt aus dem Ausgabebereich.</span><span class="sxs-lookup"><span data-stu-id="87a22-133">Clears all content in the Output Pane.</span></span>                                                                                                                                           |
| <span data-ttu-id="87a22-134">**Rückgängig**</span><span class="sxs-lookup"><span data-stu-id="87a22-134">**Undo**</span></span>                       | <span data-ttu-id="87a22-135">Macht die Aktion rückgängig, die zuvor erfolgt ist.</span><span class="sxs-lookup"><span data-stu-id="87a22-135">Reverses the action that was just performed.</span></span>                                                                                                                                     |
| <span data-ttu-id="87a22-136">**Wiederholen**</span><span class="sxs-lookup"><span data-stu-id="87a22-136">**Redo**</span></span>                       | <span data-ttu-id="87a22-137">Führt die Aktion aus, die zuvor rückgängig gemacht wurde.</span><span class="sxs-lookup"><span data-stu-id="87a22-137">Performs the action that was just undone.</span></span>                                                                                                                                        |
| <span data-ttu-id="87a22-138">**Skript ausführen**</span><span class="sxs-lookup"><span data-stu-id="87a22-138">**Run Script**</span></span>                 | <span data-ttu-id="87a22-139">Führt ein Skript aus.</span><span class="sxs-lookup"><span data-stu-id="87a22-139">Runs a script.</span></span>                                                                                                                                                                   |
| <span data-ttu-id="87a22-140">**Auswahl ausführen**</span><span class="sxs-lookup"><span data-stu-id="87a22-140">**Run Selection**</span></span>              | <span data-ttu-id="87a22-141">Führt einen ausgewählten Teil eines Skripts aus.</span><span class="sxs-lookup"><span data-stu-id="87a22-141">Runs a selected portion of a script.</span></span>                                                                                                                                             |
| <span data-ttu-id="87a22-142">**Vorgang beenden**</span><span class="sxs-lookup"><span data-stu-id="87a22-142">**Stop Execution**</span></span>             | <span data-ttu-id="87a22-143">Beendet ein Skript, das ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="87a22-143">Stops a script that is running.</span></span>                                                                                                                                                  |
| <span data-ttu-id="87a22-144">**Neue Registerkarte „Remote-PowerShell“**</span><span class="sxs-lookup"><span data-stu-id="87a22-144">**New Remote PowerShell Tab**</span></span>  | <span data-ttu-id="87a22-145">Erstellt eine neue PowerShell-Registerkarte, die eine Sitzung auf einem Remotecomputer herstellt.</span><span class="sxs-lookup"><span data-stu-id="87a22-145">Creates a new PowerShell Tab that establishes a session on a remote computer.</span></span> <span data-ttu-id="87a22-146">Ein Dialogfeld wird angezeigt und fordert Sie zur Eingabe von Details auf, die zum Herstellen der Remoteverbindung erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="87a22-146">A dialog box appears and prompts you to enter details required to establish the remote connection.</span></span> |
| <span data-ttu-id="87a22-147">**„PowerShell.exe“ starten**</span><span class="sxs-lookup"><span data-stu-id="87a22-147">**Start PowerShell.exe**</span></span>       | <span data-ttu-id="87a22-148">Öffnet eine PowerShell-Konsole.</span><span class="sxs-lookup"><span data-stu-id="87a22-148">Opens a PowerShell Console.</span></span>                                                                                                                                                      |
| <span data-ttu-id="87a22-149">**Skriptbereich oben anzeigen**</span><span class="sxs-lookup"><span data-stu-id="87a22-149">**Show Script Pane Top**</span></span>       | <span data-ttu-id="87a22-150">Verschiebt den Skriptbereich in der Anzeige nach oben.</span><span class="sxs-lookup"><span data-stu-id="87a22-150">Moves the Script Pane to the top in the display.</span></span>                                                                                                                                 |
| <span data-ttu-id="87a22-151">**Skriptbereich rechts anzeigen**</span><span class="sxs-lookup"><span data-stu-id="87a22-151">**Show Script Pane Right**</span></span>     | <span data-ttu-id="87a22-152">Verschiebt den Skriptbereich in der Anzeige nach rechts.</span><span class="sxs-lookup"><span data-stu-id="87a22-152">Moves the Script Pane to the right in the display.</span></span>                                                                                                                               |
| <span data-ttu-id="87a22-153">**Skriptbereich maximiert anzeigen**</span><span class="sxs-lookup"><span data-stu-id="87a22-153">**Show Script Pane Maximized**</span></span> | <span data-ttu-id="87a22-154">Maximiert den Skriptbereich.</span><span class="sxs-lookup"><span data-stu-id="87a22-154">Maximizes the Script Pane.</span></span>                                                                                                                                                       |

## <a name="script-tab"></a><span data-ttu-id="87a22-155">Skriptregisterkarte</span><span class="sxs-lookup"><span data-stu-id="87a22-155">Script Tab</span></span>

<span data-ttu-id="87a22-156">Zeigt den Namen des Skripts an, das Sie bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="87a22-156">Displays the name of the script you are editing.</span></span> <span data-ttu-id="87a22-157">Sie können auf eine Skriptregisterkarte klicken, um das Skript auszuwählen, das Sie bearbeiten möchten.</span><span class="sxs-lookup"><span data-stu-id="87a22-157">You can click a script tab to select the script you want to edit.</span></span>

<span data-ttu-id="87a22-158">Wenn Sie auf die Skriptregisterkarte zeigen, wird der vollqualifizierte Pfad der Skriptdatei als QuickInfo angezeigt.</span><span class="sxs-lookup"><span data-stu-id="87a22-158">When you point to the script tab, the fully qualified path to the script file appears in a tooltip.</span></span>

## <a name="script-pane"></a><span data-ttu-id="87a22-159">Skriptbereich</span><span class="sxs-lookup"><span data-stu-id="87a22-159">Script Pane</span></span>

<span data-ttu-id="87a22-160">Ermöglicht das Erstellen und Ausführen von Skripts.</span><span class="sxs-lookup"><span data-stu-id="87a22-160">Allows you to create and run scripts.</span></span> <span data-ttu-id="87a22-161">Sie können im Skriptbereich vorhandene Skripts öffnen, bearbeiten und ausführen.</span><span class="sxs-lookup"><span data-stu-id="87a22-161">You can open, edit and run existing scripts in the Script Pane.</span></span>

## <a name="output-pane"></a><span data-ttu-id="87a22-162">Ausgabebereich</span><span class="sxs-lookup"><span data-stu-id="87a22-162">Output Pane</span></span>

<span data-ttu-id="87a22-163">Zeigt die Ergebnisse der Befehle und Skripts an, die ausgeführt wurden.</span><span class="sxs-lookup"><span data-stu-id="87a22-163">Displays the results of the commands and scripts you have run.</span></span> <span data-ttu-id="87a22-164">Sie können den Inhalt des Ausgabebereich auch kopieren und löschen.</span><span class="sxs-lookup"><span data-stu-id="87a22-164">You can also copy and clear the contents in the Output Pane.</span></span>

## <a name="command-pane"></a><span data-ttu-id="87a22-165">Befehlsbereich</span><span class="sxs-lookup"><span data-stu-id="87a22-165">Command Pane</span></span>

<span data-ttu-id="87a22-166">Ermöglicht das Schreiben von Befehlen.</span><span class="sxs-lookup"><span data-stu-id="87a22-166">Allows you to write commands.</span></span> <span data-ttu-id="87a22-167">Sie können im Befehlsbereich einen Befehl mit einer oder mehreren Zeilen ausführen.</span><span class="sxs-lookup"><span data-stu-id="87a22-167">You can run a one line command or a multiline command in the Command Pane.</span></span> <span data-ttu-id="87a22-168">Drücken Sie <kbd>UMSCHALT</kbd>+<kbd>EINGABETASTE</kbd>, um jede Zeile eines mehrzeiligen Befehls einzugeben. Drücken Sie nach der letzten Zeile die <kbd>EINGABETASTE</kbd>, um den mehrzeiligen Befehl auszuführen.</span><span class="sxs-lookup"><span data-stu-id="87a22-168">Press <kbd>SHIFT</kbd>+<kbd>ENTER</kbd> to enter each line of a multiline command, and press <kbd>ENTER</kbd> after the last line to execute the multiline command.</span></span> <span data-ttu-id="87a22-169">Die oben im Befehlsbereich angezeigte Aufforderung zeigt den Pfad zum aktuellen Arbeitsverzeichnis.</span><span class="sxs-lookup"><span data-stu-id="87a22-169">The prompt displayed on top of the Command Pane shows the path to the current working directory.</span></span>

## <a name="status-bar"></a><span data-ttu-id="87a22-170">Statusleiste</span><span class="sxs-lookup"><span data-stu-id="87a22-170">Status Bar</span></span>

<span data-ttu-id="87a22-171">Ermöglicht festzustellen, ob Ihre Befehle und Skripts vollständig ausgeführt wurden.</span><span class="sxs-lookup"><span data-stu-id="87a22-171">Allows you to see whether the commands and scripts that you run are complete.</span></span> <span data-ttu-id="87a22-172">Die Statusleiste befindet sich ganz unten in der Anzeige.</span><span class="sxs-lookup"><span data-stu-id="87a22-172">The status bar is at the very bottom of the display.</span></span> <span data-ttu-id="87a22-173">Ausgewählte Teile von Fehlermeldungen werden auf der Statusleiste angezeigt.</span><span class="sxs-lookup"><span data-stu-id="87a22-173">Selected portions of error messages are displayed on the status bar.</span></span>

## <a name="text-size-slider"></a><span data-ttu-id="87a22-174">Schieberegler für die Textgröße</span><span class="sxs-lookup"><span data-stu-id="87a22-174">Text-Size Slider</span></span>

<span data-ttu-id="87a22-175">Erhöht oder verringert die Größe des Texts auf dem Bildschirm.</span><span class="sxs-lookup"><span data-stu-id="87a22-175">Increases or decreases the size of the text on the screen.</span></span>

## <a name="help"></a><span data-ttu-id="87a22-176">Hilfe</span><span class="sxs-lookup"><span data-stu-id="87a22-176">Help</span></span>

<span data-ttu-id="87a22-177">Hilfe für Windows PowerShell ISE ist im Web in der TechNet-Bibliothek verfügbar.</span><span class="sxs-lookup"><span data-stu-id="87a22-177">Help for Windows PowerShell ISE is available on the Web in the TechNet Library.</span></span> <span data-ttu-id="87a22-178">Sie können die Hilfe öffnen, indem Sie im Menü **Hilfe** auf **Hilfe zu Windows PowerShell ISE** klicken oder die Taste <kbd>F1</kbd> drücken, wobei sich der Cursor allerdings nicht über einem Cmdlet-Namen im Skript- oder Konsolenbereich befinden darf.</span><span class="sxs-lookup"><span data-stu-id="87a22-178">You can open the Help by clicking **Windows PowerShell ISE Help** on the **Help** menu or by pressing the <kbd>F1</kbd> key anywhere except when the cursor is on a cmdlet name in either the Script Pane or the Console Pane.</span></span>
<span data-ttu-id="87a22-179">Im Menü **Hilfe** können Sie auch das Cmdlet `Update-Help` ausführen und das Befehlsfenster anzeigen. Dieses unterstützt Sie beim Erstellen von Befehlen, indem alle Parameter für ein Cmdlet angezeigt werden und Sie die Parameter in einem benutzerfreundlichen Formular ausfüllen können.</span><span class="sxs-lookup"><span data-stu-id="87a22-179">From the **Help** menu you can also run the `Update-Help` cmdlet, and display the Command Window which assists you in constructing commands by showing you all of the parameters for a cmdlet and enabling you to fill in the parameters in an easy-to-use form.</span></span>

## <a name="see-also"></a><span data-ttu-id="87a22-180">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="87a22-180">See Also</span></span>

- [<span data-ttu-id="87a22-181">Einführung in die Windows PowerShell ISE</span><span class="sxs-lookup"><span data-stu-id="87a22-181">Introducing the Windows PowerShell ISE</span></span>](Introducing-the-Windows-PowerShell-ISE.md)