---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 10/29/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/show-command?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Show-Command
ms.openlocfilehash: 87bdd5a9610267b8fce9e391431d24872a77e2de
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99604850"
---
# <span data-ttu-id="6ddb6-102">Show-Command</span><span class="sxs-lookup"><span data-stu-id="6ddb6-102">Show-Command</span></span>

## <span data-ttu-id="6ddb6-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="6ddb6-103">SYNOPSIS</span></span>
<span data-ttu-id="6ddb6-104">Zeigt PowerShell-Befehls Informationen in einem grafischen Fenster an.</span><span class="sxs-lookup"><span data-stu-id="6ddb6-104">Displays PowerShell command information in a graphical window.</span></span>

## <span data-ttu-id="6ddb6-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="6ddb6-105">SYNTAX</span></span>

```
Show-Command [[-Name] <String>] [-Height <Double>] [-Width <Double>] [-NoCommonParameter]
 [-ErrorPopup] [-PassThru] [<CommonParameters>]
```

## <span data-ttu-id="6ddb6-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="6ddb6-106">DESCRIPTION</span></span>

<span data-ttu-id="6ddb6-107">Mit dem- `Show-Command` Cmdlet können Sie einen PowerShell-Befehl in einem Befehlsfenster erstellen.</span><span class="sxs-lookup"><span data-stu-id="6ddb6-107">The `Show-Command` cmdlet lets you create a PowerShell command in a command window.</span></span> <span data-ttu-id="6ddb6-108">Mithilfe der Funktionen des Befehlsfensters können Sie den Befehl ausführen oder den Befehl an Sie zurückgeben lassen.</span><span class="sxs-lookup"><span data-stu-id="6ddb6-108">You can use the features of the command window to run the command or have it return the command to you.</span></span>

<span data-ttu-id="6ddb6-109">`Show-Command` ist ein sehr nützliches Schulungs-und Lerntool.</span><span class="sxs-lookup"><span data-stu-id="6ddb6-109">`Show-Command` is a very useful teaching and learning tool.</span></span> <span data-ttu-id="6ddb6-110">`Show-Command` funktioniert an allen Befehls Typen, einschließlich Cmdlets, Funktionen, Workflows und CIM-Befehlen.</span><span class="sxs-lookup"><span data-stu-id="6ddb6-110">`Show-Command` works on all command types, including cmdlets, functions, workflows and CIM commands.</span></span>

<span data-ttu-id="6ddb6-111">Ohne Parameter `Show-Command` zeigt ein Befehlsfenster an, in dem alle verfügbaren Befehle in allen installierten Modulen aufgelistet sind.</span><span class="sxs-lookup"><span data-stu-id="6ddb6-111">Without parameters, `Show-Command` displays a command window that lists all available commands in all installed modules.</span></span> <span data-ttu-id="6ddb6-112">Um die Befehle in einem Modul zu suchen, wählen Sie das Modul aus der Dropdownliste „Module“ aus.</span><span class="sxs-lookup"><span data-stu-id="6ddb6-112">To find the commands in a module, select the module from the Modules drop-down list.</span></span> <span data-ttu-id="6ddb6-113">Klicken Sie zum Auswählen eines Befehls auf den Befehlsnamen.</span><span class="sxs-lookup"><span data-stu-id="6ddb6-113">To select a command, click the command name.</span></span>

<span data-ttu-id="6ddb6-114">Um das Befehlsfenster zu verwenden, wählen Sie einen Befehl aus, indem Sie entweder den Namen verwenden oder indem Sie in der Liste **Befehle** auf den Befehlsnamen klicken.</span><span class="sxs-lookup"><span data-stu-id="6ddb6-114">To use the command window, select a command, either by using the Name or by clicking the command name in the **Commands** list.</span></span> <span data-ttu-id="6ddb6-115">Jeder Parametersatz wird auf einer separaten Registerkarte angezeigt. Sternchen geben die erforderlichen Parameter an.</span><span class="sxs-lookup"><span data-stu-id="6ddb6-115">Each parameter set is displayed on a separate tab. Asterisks indicate the mandatory parameters.</span></span> <span data-ttu-id="6ddb6-116">Um Werte für einen Parameter einzugeben, geben Sie den Wert in das Textfeld ein, oder wählen Sie den Wert aus der Dropdownliste aus.</span><span class="sxs-lookup"><span data-stu-id="6ddb6-116">To enter values for a parameter, type the value in the text box or select the value from the drop-down box.</span></span> <span data-ttu-id="6ddb6-117">Um einen Switch-Parameter hinzuzufügen, aktivieren Sie das Parameter-Kontrollkästchen.</span><span class="sxs-lookup"><span data-stu-id="6ddb6-117">To add a switch parameter, click to select the parameter check box.</span></span>

<span data-ttu-id="6ddb6-118">Sobald Sie bereit sind, können Sie auf **Copy** klicken, um den Befehl, den Sie erstellt haben, in die Zwischenablage zu kopieren, oder klicken Sie auf **Run**, um den Befehl auszuführen.</span><span class="sxs-lookup"><span data-stu-id="6ddb6-118">When you're ready, you can click **Copy** to copy the command that you've created to the clipboard or click **Run** to run the command.</span></span> <span data-ttu-id="6ddb6-119">Sie können auch den **passthru** -Parameter verwenden, um den Befehl an das Host Programm zurückzugeben, z. b. die PowerShell-Konsole.</span><span class="sxs-lookup"><span data-stu-id="6ddb6-119">You can also use the **PassThru** parameter to return the command to the host program, such as the PowerShell console.</span></span> <span data-ttu-id="6ddb6-120">Um die Befehls Auswahl abzubrechen und zur Ansicht zurückzukehren, in der alle Befehle angezeigt werden, drücken Sie STRG, und klicken Sie auf den ausgewählten Befehl.</span><span class="sxs-lookup"><span data-stu-id="6ddb6-120">To cancel the command selection and return to the view that displays all commands, press Ctrl and click the selected command.</span></span>

<span data-ttu-id="6ddb6-121">In der PowerShell Integrated Scripting Environment (ISE) `Show-Command` wird standardmäßig eine Variation des Fensters angezeigt.</span><span class="sxs-lookup"><span data-stu-id="6ddb6-121">In the PowerShell Integrated Scripting Environment (ISE), a variation of the `Show-Command` window is displayed by default.</span></span> <span data-ttu-id="6ddb6-122">Weitere Informationen zur Verwendung dieses Befehls Fensters finden Sie in den Hilfe Themen zur PowerShell ISE.</span><span class="sxs-lookup"><span data-stu-id="6ddb6-122">For information about using this command window, see the PowerShell ISE Help topics.</span></span>

<span data-ttu-id="6ddb6-123">Dieses Cmdlet wurde in PowerShell 7 erneut eingeführt.</span><span class="sxs-lookup"><span data-stu-id="6ddb6-123">This cmdlet was reintroduced in PowerShell 7.</span></span>

<span data-ttu-id="6ddb6-124">Da dieses Cmdlet eine Benutzeroberfläche erfordert, funktioniert es nicht unter Windows Server Core oder Windows Nano Server.</span><span class="sxs-lookup"><span data-stu-id="6ddb6-124">Because this cmdlet requires a user interface, it does not work on Windows Server Core or Windows Nano Server.</span></span> <span data-ttu-id="6ddb6-125">Dieses Cmdlet ist nur auf Windows-Systemen verfügbar, die den Windows-Desktop unterstützen.</span><span class="sxs-lookup"><span data-stu-id="6ddb6-125">This cmdlet is only available on Windows systems that support the Windows Desktop.</span></span>

## <span data-ttu-id="6ddb6-126">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="6ddb6-126">EXAMPLES</span></span>

### <span data-ttu-id="6ddb6-127">Beispiel 1: Öffnen des Befehls Fensters</span><span class="sxs-lookup"><span data-stu-id="6ddb6-127">Example 1: Open the Commands window</span></span>

<span data-ttu-id="6ddb6-128">In diesem Beispiel wird die Standardansicht des `Show-Command` Fensters angezeigt.</span><span class="sxs-lookup"><span data-stu-id="6ddb6-128">This example displays the default view of the `Show-Command` window.</span></span> <span data-ttu-id="6ddb6-129">Das Fenster " **Befehle** " zeigt eine Liste aller Befehle in allen Modulen an, die auf dem Computer installiert sind.</span><span class="sxs-lookup"><span data-stu-id="6ddb6-129">The **Commands** window displays a list of all commands in all modules that are installed on the computer.</span></span>

```powershell
Show-Command
```

### <span data-ttu-id="6ddb6-130">Beispiel 2: Öffnen eines Cmdlets im Fenster "Befehle"</span><span class="sxs-lookup"><span data-stu-id="6ddb6-130">Example 2: Open a cmdlet in the Commands window</span></span>

<span data-ttu-id="6ddb6-131">In diesem Beispiel wird das- `Invoke-Command` Cmdlet im **Befehls** Fenster angezeigt.</span><span class="sxs-lookup"><span data-stu-id="6ddb6-131">This example display the `Invoke-Command` cmdlet in the **Command** window.</span></span> <span data-ttu-id="6ddb6-132">Mit dieser Anzeige können Sie Befehle ausführen `Invoke-Command` .</span><span class="sxs-lookup"><span data-stu-id="6ddb6-132">You can use this display to run `Invoke-Command` commands.</span></span>

```powershell
Show-Command -Name "Invoke-Command"
```

### <span data-ttu-id="6ddb6-133">Beispiel 3: Öffnen eines Cmdlets mit angegebenen Parametern</span><span class="sxs-lookup"><span data-stu-id="6ddb6-133">Example 3: Open a cmdlet with specified parameters</span></span>

<span data-ttu-id="6ddb6-134">Mit diesem Befehl wird ein `Show-Command` Fenster für das `Connect-PSSession` Cmdlet geöffnet.</span><span class="sxs-lookup"><span data-stu-id="6ddb6-134">This command opens a `Show-Command` window for the`Connect-PSSession`cmdlet.</span></span>

```powershell
Show-Command -Name "Connect-PSSession" -Height 700 -Width 1000 -ErrorPopup
```

<span data-ttu-id="6ddb6-135">Mit den Parametern **height** und **Width** wird die Dimension des Befehls Fensters angegeben.</span><span class="sxs-lookup"><span data-stu-id="6ddb6-135">The **Height** and **Width** parameters specify the dimension of the command window.</span></span> <span data-ttu-id="6ddb6-136">Der **errorpopup** -Parameter zeigt das Fehler Befehlsfenster an.</span><span class="sxs-lookup"><span data-stu-id="6ddb6-136">The **ErrorPopup** parameter displays the error command window.</span></span>

<span data-ttu-id="6ddb6-137">Wenn Sie auf **Ausführen** klicken, wird der `Connect-PSSession` Befehl genauso ausgeführt, als würden Sie den `Connect-PSSession` Befehl an der Befehlszeile eingeben.</span><span class="sxs-lookup"><span data-stu-id="6ddb6-137">When you click **Run**, the `Connect-PSSession` command runs, just as would if you typed the `Connect-PSSession` command at the command line.</span></span>

### <span data-ttu-id="6ddb6-138">Beispiel 4: Angeben neuer Standardparameter Werte für ein Cmdlet</span><span class="sxs-lookup"><span data-stu-id="6ddb6-138">Example 4: Specify new default parameter values for a cmdlet</span></span>

<span data-ttu-id="6ddb6-139">In diesem Beispiel wird die `$PSDefaultParameterValues` Automatische Variable verwendet, um neue Standardwerte für die Parameter " **height**", " **Width**" und " **errorpopup** " des `Show-Command` Cmdlets festzulegen.</span><span class="sxs-lookup"><span data-stu-id="6ddb6-139">This example uses the `$PSDefaultParameterValues` automatic variable to set new default values for the **Height**, **Width**, and **ErrorPopup** parameters of the `Show-Command` cmdlet.</span></span>

```powershell
$PSDefaultParameterValues = @{
    "Show-Command:Height" = 700
    "Show-Command:Width" = 1000
    "Show-Command:ErrorPopup" = $True
}
```

<span data-ttu-id="6ddb6-140">Wenn Sie nun einen `Show-Command` Befehl ausführen, werden die neuen Standardwerte automatisch angewendet.</span><span class="sxs-lookup"><span data-stu-id="6ddb6-140">Now when you run a `Show-Command` command, the new defaults are applied automatically.</span></span> <span data-ttu-id="6ddb6-141">Um diese Standardwerte in jeder PowerShell-Sitzung zu verwenden, fügen Sie die `$PSDefaultParameterValues` Variable Ihrem PowerShell-Profil hinzu.</span><span class="sxs-lookup"><span data-stu-id="6ddb6-141">To use these default values in every PowerShell session, add the `$PSDefaultParameterValues` variable to your PowerShell profile.</span></span> <span data-ttu-id="6ddb6-142">Weitere Informationen finden Sie unter [about_Profiles](../Microsoft.PowerShell.Core/About/about_Profiles.md) und [about_Parameters_Default_Values](../Microsoft.PowerShell.Core/About/about_Parameters_Default_Values.md).</span><span class="sxs-lookup"><span data-stu-id="6ddb6-142">For more information, see [about_Profiles](../Microsoft.PowerShell.Core/About/about_Profiles.md) and [about_Parameters_Default_Values](../Microsoft.PowerShell.Core/About/about_Parameters_Default_Values.md).</span></span>

### <span data-ttu-id="6ddb6-143">Beispiel 5: Senden der Ausgabe an eine Rasteransicht</span><span class="sxs-lookup"><span data-stu-id="6ddb6-143">Example 5: Send output to a grid view</span></span>

<span data-ttu-id="6ddb6-144">Dieser Befehl zeigt, wie die `Show-Command` `Out-GridView` Cmdlets und verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="6ddb6-144">This command shows how to use the `Show-Command` and `Out-GridView` cmdlets together.</span></span>

```powershell
Show-Command Get-ChildItem | Out-GridView
```

<span data-ttu-id="6ddb6-145">Der Befehl verwendet das `Show-Command` Cmdlet zum Öffnen eines Befehls Fensters für das `Get-ChildItem` Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="6ddb6-145">The command uses the `Show-Command` cmdlet to open a command window for the`Get-ChildItem`cmdlet.</span></span>
<span data-ttu-id="6ddb6-146">Wenn Sie auf die Schaltfläche Ausführen klicken, wird der Befehl **ausgeführt** , `Get-ChildItem` und die Ausgabe wird generiert.</span><span class="sxs-lookup"><span data-stu-id="6ddb6-146">When you click the **Run** button, the `Get-ChildItem` command runs and generates output.</span></span> <span data-ttu-id="6ddb6-147">Der Pipeline Operator (|) sendet die Ausgabe des `Get-ChildItem` Befehls an das `Out-GridView` Cmdlet, das die `Get-ChildItem` Ausgabe in einem interaktiven Fenster anzeigt.</span><span class="sxs-lookup"><span data-stu-id="6ddb6-147">The pipeline operator ( | ) sends the output of the `Get-ChildItem` command to the `Out-GridView` cmdlet, which displays the `Get-ChildItem` output in an interactive window.</span></span>

### <span data-ttu-id="6ddb6-148">Beispiel 6: Anzeigen eines Befehls, den Sie im Fenster "Befehle" erstellen</span><span class="sxs-lookup"><span data-stu-id="6ddb6-148">Example 6: Display a command that you create in the Commands window</span></span>

<span data-ttu-id="6ddb6-149">Dieses Beispiel zeigt den Befehl, den Sie im- `Show-Command` Fenster erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="6ddb6-149">This example shows the command that you created in the `Show-Command` window.</span></span> <span data-ttu-id="6ddb6-150">Der Befehl verwendet den **passthru** -Parameter, der die `Show-Command` Ergebnisse in einer Zeichenfolge zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="6ddb6-150">The command uses the **PassThru** parameter, which returns the `Show-Command` results in a string.</span></span>

```powershell
Show-Command -PassThru
```

```Output
Get-EventLog -LogName "Windows PowerShell" -Newest 5
```

<span data-ttu-id="6ddb6-151">Wenn Sie z. b. das `Show-Command` Fenster verwenden, um einen Befehl zu erstellen, mit `Get-EventLog` dem die fünf neuesten Ereignisse im Windows PowerShell-Ereignisprotokoll abgerufen werden, und dann auf **OK** klicken, gibt der Befehl die oben gezeigte Ausgabe zurück.</span><span class="sxs-lookup"><span data-stu-id="6ddb6-151">For example, if you use the `Show-Command` window to create a `Get-EventLog` command that gets the five newest events in the Windows PowerShell event log, and then click **OK**, the command returns the output shown above.</span></span> <span data-ttu-id="6ddb6-152">Das Anzeigen der Befehls Zeichenfolge hilft Ihnen beim Erlernen von PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6ddb6-152">Viewing the command string helps you learn PowerShell.</span></span>

### <span data-ttu-id="6ddb6-153">Beispiel 7: Speichern eines Befehls in einer Variablen</span><span class="sxs-lookup"><span data-stu-id="6ddb6-153">Example 7: Save a command to a variable</span></span>

<span data-ttu-id="6ddb6-154">In diesem Beispiel wird gezeigt, wie Sie die Befehls Zeichenfolge ausführen können, die Sie erhalten, wenn Sie den **passthru** -Parameter des `Show-Command` Cmdlets verwenden.</span><span class="sxs-lookup"><span data-stu-id="6ddb6-154">This example shows how to run the command string that you get when you use the **PassThru** parameter of the `Show-Command` cmdlet.</span></span> <span data-ttu-id="6ddb6-155">Mit dieser Strategie können Sie den Befehl anzeigen und ihn verwenden.</span><span class="sxs-lookup"><span data-stu-id="6ddb6-155">This strategy lets you see the command and use it.</span></span>

```powershell
$C = Show-Command -PassThru
$C
Invoke-Expression $C
```

```Output
Get-EventLog -LogName "PowerShell" -Newest 5

Index Time          EntryType   Source                 InstanceID Message
----- ----          ---------   ------                 ---------- -------
11520 Dec 16 16:37  Information Windows PowerShell            400 Engine state is changed from None to Available...
11519 Dec 16 16:37  Information Windows PowerShell            600 Provider "Variable" is Started. ...
11518 Dec 16 16:37  Information Windows PowerShell            600 Provider "Registry" is Started. ...
11517 Dec 16 16:37  Information Windows PowerShell            600 Provider "Function" is Started. ...
11516 Dec 16 16:37  Information Windows PowerShell            600 Provider "FileSystem" is Started. ...
```

<span data-ttu-id="6ddb6-156">Der erste Befehl verwendet den **passthru** -Parameter des `Show-Command` Cmdlets und speichert die Ergebnisse des Befehls in der `$C` Variablen.</span><span class="sxs-lookup"><span data-stu-id="6ddb6-156">The first command uses the **PassThru** parameter of the `Show-Command` cmdlet and saves the results of the command in the `$C` variable.</span></span> <span data-ttu-id="6ddb6-157">In diesem Fall verwenden wir das `Show-Command` Fenster, um einen Befehl zu erstellen `Get-EventLog` , mit dem die fünf neuesten Ereignisse im Windows PowerShell-Ereignisprotokoll abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="6ddb6-157">In this case, we use the `Show-Command` window to create a `Get-EventLog` command that gets the five newest events in the Windows PowerShell event log.</span></span> <span data-ttu-id="6ddb6-158">Wenn Sie auf **OK** klicken, wird `Show-Command` die Befehls Zeichenfolge zurückgegeben, die in der Variablen gespeichert wird `$C` .</span><span class="sxs-lookup"><span data-stu-id="6ddb6-158">When you click **OK**, `Show-Command` returns the command string, which is saved in the `$C` variable.</span></span>

### <span data-ttu-id="6ddb6-159">Beispiel 8: Speichern der Ausgabe eines Befehls in einer Variablen</span><span class="sxs-lookup"><span data-stu-id="6ddb6-159">Example 8: Save the output of a command to a variable</span></span>

<span data-ttu-id="6ddb6-160">In diesem Beispiel wird der **errorpopup** -Parameter verwendet, um die Ausgabe eines Befehls in einer Variablen zu speichern.</span><span class="sxs-lookup"><span data-stu-id="6ddb6-160">This example uses the **ErrorPopup** parameter to save the output of a command in a variable.</span></span>

```powershell
$P = Show-Command Get-Process -ErrorPopup
$P
```

```Output
Handles  NPM(K)    PM(K)      WS(K) VM(M)   CPU(s)     Id ProcessName
-------  ------    -----      ----- -----   ------     -- -----------
    473      33    94096     112532   709     2.06   4492 powershell
```

<span data-ttu-id="6ddb6-161">Zusätzlich zum Anzeigen von Fehlern in einem Fenster gibt **ErrorPopup** die Ausgabe des Befehls an den aktuellen Befehl zurück, anstatt einen neuen Befehl zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="6ddb6-161">In addition to displaying errors in a window, **ErrorPopup** returns command output to the current command, instead of creating a new command.</span></span> <span data-ttu-id="6ddb6-162">Wenn Sie diesen Befehl ausführen, wird das `Show-Command` Fenster geöffnet.</span><span class="sxs-lookup"><span data-stu-id="6ddb6-162">When you run this command, the `Show-Command` window opens.</span></span> <span data-ttu-id="6ddb6-163">Mithilfe der Funktionen des Fensters können Sie Parameterwerte festlegen.</span><span class="sxs-lookup"><span data-stu-id="6ddb6-163">You can use the window features to set parameter values.</span></span> <span data-ttu-id="6ddb6-164">Um den Befehl auszuführen, klicken Sie im-Fenster auf die Schaltfläche **Ausführen** `Show-Command` .</span><span class="sxs-lookup"><span data-stu-id="6ddb6-164">To run the command, click the **Run** button in the `Show-Command` window.</span></span>

## <span data-ttu-id="6ddb6-165">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="6ddb6-165">PARAMETERS</span></span>

### <span data-ttu-id="6ddb6-166">-Errorpopup</span><span class="sxs-lookup"><span data-stu-id="6ddb6-166">-ErrorPopup</span></span>

<span data-ttu-id="6ddb6-167">Gibt an, dass das Cmdlet neben der Anzeige in der Befehlszeile auch Fehler in einem Popup Fenster anzeigt.</span><span class="sxs-lookup"><span data-stu-id="6ddb6-167">Indicates that the cmdlet displays errors in a pop-up window, in addition to displaying them at the command line.</span></span> <span data-ttu-id="6ddb6-168">Wenn ein in einem `Show-Command` Fenster ausgelaufter Befehl einen Fehler generiert, wird der Fehler standardmäßig nur in der Befehlszeile angezeigt.</span><span class="sxs-lookup"><span data-stu-id="6ddb6-168">By default, when a command that is run in a `Show-Command` window generates an error, the error is displayed only at the command line.</span></span>

<span data-ttu-id="6ddb6-169">Wenn Sie den Befehl ausführen (mit der Schaltfläche " **Ausführen** " im `Show-Command` Fenster), gibt der **errorpopup** -Parameter die Befehls Ergebnisse an den aktuellen Befehl zurück, anstatt den Befehl auszuführen und seine Ausgabe an einen neuen Befehl zurückzugeben.</span><span class="sxs-lookup"><span data-stu-id="6ddb6-169">Also, when you run the command (by using the **Run** button in the `Show-Command` window), the **ErrorPopup** parameter returns the command results to the current command, instead of running the command and returning its output to a new command.</span></span> <span data-ttu-id="6ddb6-170">Mit dieser Funktion können Sie die Ergebnisse des Befehls in einer Variablen speichern.</span><span class="sxs-lookup"><span data-stu-id="6ddb6-170">You can use this feature to save the command results in a variable.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="6ddb6-171">-Höhe</span><span class="sxs-lookup"><span data-stu-id="6ddb6-171">-Height</span></span>

<span data-ttu-id="6ddb6-172">Gibt die Höhe des `Show-Command` Fensters in Pixel an.</span><span class="sxs-lookup"><span data-stu-id="6ddb6-172">Specifies the height of the `Show-Command` window in pixels.</span></span> <span data-ttu-id="6ddb6-173">Geben Sie einen Wert zwischen 300 und der Anzahl der Pixel in der Bildschirmauflösung ein.</span><span class="sxs-lookup"><span data-stu-id="6ddb6-173">Enter a value between 300 and the number of pixels in the screen resolution.</span></span> <span data-ttu-id="6ddb6-174">Wenn der Wert zu groß ist, um das Befehlsfenster auf dem Bildschirm anzuzeigen, `Show-Command` generiert einen Fehler.</span><span class="sxs-lookup"><span data-stu-id="6ddb6-174">If the value is too large to display the command window on the screen, `Show-Command` generates an error.</span></span> <span data-ttu-id="6ddb6-175">Die Standardhöhe ist 600 Pixel.</span><span class="sxs-lookup"><span data-stu-id="6ddb6-175">The default height is 600 pixels.</span></span> <span data-ttu-id="6ddb6-176">Für einen `Show-Command` Befehl, der den **Name** -Parameter enthält, beträgt die Standardhöhe 300 Pixel.</span><span class="sxs-lookup"><span data-stu-id="6ddb6-176">For a `Show-Command` command that includes the **Name** parameter, the default height is 300 pixels.</span></span>

```yaml
Type: System.Double
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="6ddb6-177">-Name</span><span class="sxs-lookup"><span data-stu-id="6ddb6-177">-Name</span></span>

<span data-ttu-id="6ddb6-178">Zeigt ein Befehlsfenster für den angegebenen Befehl an.</span><span class="sxs-lookup"><span data-stu-id="6ddb6-178">Displays a command window for the specified command.</span></span> <span data-ttu-id="6ddb6-179">Geben Sie den Namen eines Befehls ein, z. b. den Namen eines Cmdlets, einer Funktion oder eines CIM-Befehls.</span><span class="sxs-lookup"><span data-stu-id="6ddb6-179">Enter the name of one command, such as the name of a cmdlet, function, or CIM command.</span></span> <span data-ttu-id="6ddb6-180">Wenn Sie diesen Parameter weglassen, wird `Show-Command` ein Befehlsfenster angezeigt, in dem alle PowerShell-Befehle in allen auf dem Computer installierten Modulen aufgelistet sind.</span><span class="sxs-lookup"><span data-stu-id="6ddb6-180">If you omit this parameter, `Show-Command` displays a command window that lists all of the PowerShell commands in all modules installed on the computer.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: CommandName

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="6ddb6-181">-Nocommonparameter</span><span class="sxs-lookup"><span data-stu-id="6ddb6-181">-NoCommonParameter</span></span>

<span data-ttu-id="6ddb6-182">Gibt an, dass dieses Cmdlet den Abschnitt Allgemeine Parameter der Befehls Anzeige auslässt.</span><span class="sxs-lookup"><span data-stu-id="6ddb6-182">Indicates that this cmdlet omits the Common Parameters section of the command display.</span></span> <span data-ttu-id="6ddb6-183">Standardmäßig werden die allgemeinen Parameter in einem erweiterbaren Abschnitt unten im Befehlsfenster angezeigt.</span><span class="sxs-lookup"><span data-stu-id="6ddb6-183">By default, the Common Parameters appear in an expandable section at the bottom of the command window.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="6ddb6-184">-PassThru</span><span class="sxs-lookup"><span data-stu-id="6ddb6-184">-PassThru</span></span>

<span data-ttu-id="6ddb6-185">Gibt ein Objekt zurück, das das Element darstellt, mit dem Sie arbeiten.</span><span class="sxs-lookup"><span data-stu-id="6ddb6-185">Returns an object representing the item with which you are working.</span></span> <span data-ttu-id="6ddb6-186">Standardmäßig wird von diesem Cmdlet keine Ausgabe generiert.</span><span class="sxs-lookup"><span data-stu-id="6ddb6-186">By default, this cmdlet does not generate any output.</span></span> <span data-ttu-id="6ddb6-187">Um die Befehls Zeichenfolge auszuführen, kopieren Sie Sie in die Eingabeaufforderung, oder speichern Sie Sie in einer Variablen, und verwenden Sie das `Invoke-Expression` Cmdlet, um die Zeichenfolge in der Variablen auszuführen.</span><span class="sxs-lookup"><span data-stu-id="6ddb6-187">To run the command string, copy and paste it at the command prompt or save it in a variable and use the `Invoke-Expression` cmdlet to run the string in the variable.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="6ddb6-188">-Breite</span><span class="sxs-lookup"><span data-stu-id="6ddb6-188">-Width</span></span>

<span data-ttu-id="6ddb6-189">Gibt die Breite des `Show-Command` Fensters in Pixel an.</span><span class="sxs-lookup"><span data-stu-id="6ddb6-189">Specifies the width of the `Show-Command` window in pixels.</span></span> <span data-ttu-id="6ddb6-190">Geben Sie einen Wert zwischen 300 und der Anzahl der Pixel in der Bildschirmauflösung ein.</span><span class="sxs-lookup"><span data-stu-id="6ddb6-190">Enter a value between 300 and the number of pixels in the screen resolution.</span></span> <span data-ttu-id="6ddb6-191">Wenn der Wert zu groß ist, um das Befehlsfenster auf dem Bildschirm anzuzeigen, `Show-Command` generiert einen Fehler.</span><span class="sxs-lookup"><span data-stu-id="6ddb6-191">If the value is too large to display the command window on the screen, `Show-Command` generates an error.</span></span> <span data-ttu-id="6ddb6-192">Die Standardbreite ist 300 Pixel.</span><span class="sxs-lookup"><span data-stu-id="6ddb6-192">The default width is 300 pixels.</span></span>

```yaml
Type: System.Double
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="6ddb6-193">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="6ddb6-193">CommonParameters</span></span>

<span data-ttu-id="6ddb6-194">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="6ddb6-194">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="6ddb6-195">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="6ddb6-195">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="6ddb6-196">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="6ddb6-196">INPUTS</span></span>

### <span data-ttu-id="6ddb6-197">Keine</span><span class="sxs-lookup"><span data-stu-id="6ddb6-197">None</span></span>

<span data-ttu-id="6ddb6-198">Eingaben können nicht an übergeben werden `Show-Command` .</span><span class="sxs-lookup"><span data-stu-id="6ddb6-198">You cannot pipe input to `Show-Command`.</span></span>

## <span data-ttu-id="6ddb6-199">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="6ddb6-199">OUTPUTS</span></span>

### <span data-ttu-id="6ddb6-200">None, System. String, System. Object</span><span class="sxs-lookup"><span data-stu-id="6ddb6-200">None, System.String, System.Object</span></span>

<span data-ttu-id="6ddb6-201">Wenn Sie den **passthru** -Parameter verwenden, `Show-Command` gibt eine Befehls Zeichenfolge zurück.</span><span class="sxs-lookup"><span data-stu-id="6ddb6-201">When you use the **PassThru** parameter, `Show-Command` returns a command string.</span></span> <span data-ttu-id="6ddb6-202">Wenn Sie den **errorpopup** -Parameter verwenden, wird `Show-Command` die Befehlsausgabe (beliebiges Objekt) zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="6ddb6-202">When you use the **ErrorPopup** parameter, `Show-Command` returns the command output (any object).</span></span> <span data-ttu-id="6ddb6-203">Andernfalls `Show-Command` generiert keine Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="6ddb6-203">Otherwise, `Show-Command` does not generate any output.</span></span>

## <span data-ttu-id="6ddb6-204">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="6ddb6-204">NOTES</span></span>

<span data-ttu-id="6ddb6-205">Dieses Cmdlet ist nur auf Windows-Plattformen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="6ddb6-205">This cmdlet is only available on Windows platforms.</span></span>

<span data-ttu-id="6ddb6-206">`Show-Command` funktioniert nicht in Remote Sitzungen.</span><span class="sxs-lookup"><span data-stu-id="6ddb6-206">`Show-Command` does not work in remote sessions.</span></span>

## <span data-ttu-id="6ddb6-207">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="6ddb6-207">RELATED LINKS</span></span>