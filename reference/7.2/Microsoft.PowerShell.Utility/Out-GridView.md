---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 10/28/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/out-gridview?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Out-GridView
ms.openlocfilehash: 19a53b5b14d2dfdb513fbbda4c55ba0df37ab1c0
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99603932"
---
# <span data-ttu-id="73ed2-102">Out-GridView</span><span class="sxs-lookup"><span data-stu-id="73ed2-102">Out-GridView</span></span>

## <span data-ttu-id="73ed2-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="73ed2-103">SYNOPSIS</span></span>
<span data-ttu-id="73ed2-104">Sendet die Ausgabe an eine interaktive Tabelle in einem separaten Fenster.</span><span class="sxs-lookup"><span data-stu-id="73ed2-104">Sends output to an interactive table in a separate window.</span></span>

## <span data-ttu-id="73ed2-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="73ed2-105">SYNTAX</span></span>

### <span data-ttu-id="73ed2-106">Passthru (Standard)</span><span class="sxs-lookup"><span data-stu-id="73ed2-106">PassThru (Default)</span></span>

```
Out-GridView [-InputObject <PSObject>] [-Title <String>] [-PassThru] [<CommonParameters>]
```

### <span data-ttu-id="73ed2-107">Warten</span><span class="sxs-lookup"><span data-stu-id="73ed2-107">Wait</span></span>

```
Out-GridView [-InputObject <PSObject>] [-Title <String>] [-Wait] [<CommonParameters>]
```

### <span data-ttu-id="73ed2-108">OutputMode</span><span class="sxs-lookup"><span data-stu-id="73ed2-108">OutputMode</span></span>

```
Out-GridView [-InputObject <PSObject>] [-Title <String>] [-OutputMode <OutputModeOption>]
 [<CommonParameters>]
```

## <span data-ttu-id="73ed2-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="73ed2-109">DESCRIPTION</span></span>

<span data-ttu-id="73ed2-110">Das- `Out-GridView` Cmdlet sendet die Ausgabe von einem Befehl an ein Raster Ansichts Fenster, in dem die Ausgabe in einer interaktiven Tabelle angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="73ed2-110">The `Out-GridView` cmdlet sends the output from a command to a grid view window where the output is displayed in an interactive table.</span></span>

<span data-ttu-id="73ed2-111">Da dieses Cmdlet eine Benutzeroberfläche erfordert, funktioniert es nicht unter Windows Server Core oder Windows Nano Server.</span><span class="sxs-lookup"><span data-stu-id="73ed2-111">Because this cmdlet requires a user interface, it does not work on Windows Server Core or Windows Nano Server.</span></span>

<span data-ttu-id="73ed2-112">Sie können die folgenden Funktionen der Tabelle verwenden, um Ihre Daten zu überprüfen:</span><span class="sxs-lookup"><span data-stu-id="73ed2-112">You can use the following features of the table to examine your data:</span></span>

- <span data-ttu-id="73ed2-113">Ausblenden, anzeigen und Neuanordnen von Spalten</span><span class="sxs-lookup"><span data-stu-id="73ed2-113">Hide, Show, and Reorder Columns</span></span>
- <span data-ttu-id="73ed2-114">Zeilen sortieren</span><span class="sxs-lookup"><span data-stu-id="73ed2-114">Sort rows</span></span>
- <span data-ttu-id="73ed2-115">Schnelles Filtern</span><span class="sxs-lookup"><span data-stu-id="73ed2-115">Quick Filter</span></span>
- <span data-ttu-id="73ed2-116">Kriterien-Filter hinzufügen</span><span class="sxs-lookup"><span data-stu-id="73ed2-116">Add Criteria Filter</span></span>
- <span data-ttu-id="73ed2-117">Kopieren und Einfügen</span><span class="sxs-lookup"><span data-stu-id="73ed2-117">Copy and paste</span></span>

<span data-ttu-id="73ed2-118">Vollständige Anweisungen finden Sie im Abschnitt " [Hinweise](#notes) " in diesem Artikel.</span><span class="sxs-lookup"><span data-stu-id="73ed2-118">For full instructions, see the [Notes](#notes) section of this article.</span></span>

> [!NOTE]
> <span data-ttu-id="73ed2-119">Dieses Cmdlet wurde in PowerShell 7 erneut eingeführt.</span><span class="sxs-lookup"><span data-stu-id="73ed2-119">This cmdlet was reintroduced in PowerShell 7.</span></span> <span data-ttu-id="73ed2-120">Dieses Cmdlet ist nur auf Windows-Systemen verfügbar, die den Windows-Desktop unterstützen.</span><span class="sxs-lookup"><span data-stu-id="73ed2-120">This cmdlet is only available on Windows systems that support the Windows Desktop.</span></span> <span data-ttu-id="73ed2-121">Eine plattformübergreifende Version dieses Cmdlets finden Sie unter dem [graphicaltools](https://www.powershellgallery.com/packages/Microsoft.PowerShell.GraphicalTools) -Modul in der PowerShell-Katalog.</span><span class="sxs-lookup"><span data-stu-id="73ed2-121">For a cross-platform version of this cmdlet, see the [GraphicalTools](https://www.powershellgallery.com/packages/Microsoft.PowerShell.GraphicalTools) module in the PowerShell Gallery.</span></span>

## <span data-ttu-id="73ed2-122">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="73ed2-122">EXAMPLES</span></span>

### <span data-ttu-id="73ed2-123">Beispiel 1: Ausgabeprozesse in einer Rasteransicht</span><span class="sxs-lookup"><span data-stu-id="73ed2-123">Example 1: Output processes to a grid view</span></span>

<span data-ttu-id="73ed2-124">Dieses Beispiel ruft die Prozesse ab, die auf dem lokalen Computer ausgeführt werden, und sendet diese an ein Raster Ansichts Fenster.</span><span class="sxs-lookup"><span data-stu-id="73ed2-124">This example gets the processes running on the local computer and sends them to a grid view window.</span></span>

```powershell
Get-Process | Out-GridView
```

### <span data-ttu-id="73ed2-125">Beispiel 2: Verwenden einer Variablen, um Prozesse an eine Rasteransicht auszugeben</span><span class="sxs-lookup"><span data-stu-id="73ed2-125">Example 2: Use a variable to output processes to a grid view</span></span>

<span data-ttu-id="73ed2-126">In diesem Beispiel werden auch die Prozesse abgerufen, die auf dem lokalen Computer ausgeführt werden und an ein Raster Ansichts Fenster gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="73ed2-126">This example also gets the processes running on the local computer and sends them to a grid view window.</span></span>

```powershell
$P = Get-Process
$P | Out-GridView
```

<span data-ttu-id="73ed2-127">Die Ausgabe des `Get-Process` Cmdlets wird in der Variablen gespeichert `$P` .</span><span class="sxs-lookup"><span data-stu-id="73ed2-127">The output of the `Get-Process` cmdlet is saved in the `$P` variable.</span></span> <span data-ttu-id="73ed2-128">Anschließend `$P` wird an weitergeleitet `Out-GridView` .</span><span class="sxs-lookup"><span data-stu-id="73ed2-128">Then, `$P` is piped to `Out-GridView`.</span></span>

### <span data-ttu-id="73ed2-129">Beispiel 3: Anzeigen ausgewählter Eigenschaften in einer Rasteransicht</span><span class="sxs-lookup"><span data-stu-id="73ed2-129">Example 3: Display a selected properties in a grid view</span></span>

<span data-ttu-id="73ed2-130">In diesem Beispiel werden die ausgewählten Eigenschaften der ausgelaufenden Prozesse in einer Rasteransicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="73ed2-130">This example displays selected properties of the running processes in a grid view.</span></span>

```powershell
Get-Process | Select-Object -Property Name, WorkingSet, PeakWorkingSet |
  Sort-Object -Property WorkingSet -Descending | Out-GridView
```

<span data-ttu-id="73ed2-131">Die Ausgabe von `Get-Process` wird an weitergeleitet, `Select-Object` um die Eigenschaften **Name**, **Workingset** und **Peer Share Workingset** auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="73ed2-131">The output of `Get-Process` is piped to `Select-Object` to select the **Name**, **WorkingSet**, and **PeakWorkingSet** properties.</span></span> <span data-ttu-id="73ed2-132">Ein weiterer Pipeline Operator sendet die gefilterten Objekte an das `Sort-Object` Cmdlet, um Sie in absteigender Reihenfolge nach dem Wert der **Workingset** -Eigenschaft zu sortieren.</span><span class="sxs-lookup"><span data-stu-id="73ed2-132">Another pipeline operator sends the filtered objects to the `Sort-Object` cmdlet to sort them in descending order by the value of the **WorkingSet** property.</span></span>
<span data-ttu-id="73ed2-133">Anschließend werden die sortierten Ergebnisse an weitergeleitet `Out-GridView` .</span><span class="sxs-lookup"><span data-stu-id="73ed2-133">Then, the sorted results are piped to `Out-GridView`.</span></span> <span data-ttu-id="73ed2-134">Sie können nun die Funktionen der Rasteransicht verwenden, um die Daten zu durchsuchen, zu sortieren und zu filtern.</span><span class="sxs-lookup"><span data-stu-id="73ed2-134">You can now use the features of the grid view to search, sort, and filter the data.</span></span>

### <span data-ttu-id="73ed2-135">Beispiel 4: Speichern der Ausgabe in einer Variablen und anschließende Ausgabe einer Rasteransicht</span><span class="sxs-lookup"><span data-stu-id="73ed2-135">Example 4: Save output to a variable, and then output a grid view</span></span>

<span data-ttu-id="73ed2-136">In diesem Beispiel wird die Ausgabe des Cmdlets in einer Variablen gespeichert und dann an gesendet `Out-GridView` .</span><span class="sxs-lookup"><span data-stu-id="73ed2-136">This example saves cmdlet output in a variable then sends it to `Out-GridView`.</span></span>

```powershell
($A = Get-ChildItem -Path $PSHOME -Recurse) | Out-GridView
```

<span data-ttu-id="73ed2-137">`Get-ChildItem` Ruft alle Dateien im PowerShell-Installationsverzeichnis und seinen Unterverzeichnissen mithilfe der `$PSHOME` automatischen Variablen ab.</span><span class="sxs-lookup"><span data-stu-id="73ed2-137">`Get-ChildItem` gets all the files in the PowerShell installation directory and its subdirectories using the the `$PSHOME` automatic variable.</span></span> <span data-ttu-id="73ed2-138">Die Klammern im Befehl bestimmen die Reihenfolge der Vorgänge.</span><span class="sxs-lookup"><span data-stu-id="73ed2-138">The parentheses in the command establish the order of operations.</span></span> <span data-ttu-id="73ed2-139">Folglich wird die Ausgabe des `Get-ChildItem` Befehls in der Variablen gespeichert, `$A` bevor Sie an gesendet wird `Out-GridView` .</span><span class="sxs-lookup"><span data-stu-id="73ed2-139">As a result, the output from the `Get-ChildItem` command is saved in the `$A` variable before it is sent to `Out-GridView`.</span></span>

### <span data-ttu-id="73ed2-140">Beispiel 5: Ausgabeprozesse für einen angegebenen Computer in einer Rasteransicht</span><span class="sxs-lookup"><span data-stu-id="73ed2-140">Example 5: Output processes for a specified computer to a grid view</span></span>

<span data-ttu-id="73ed2-141">In diesem Beispiel werden die Prozesse angezeigt, die auf dem Server01-Computer in einem Raster Ansichts Fenster ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="73ed2-141">This example displays the processes that are running on the Server01 computer in a grid view window.</span></span>

```powershell
Get-Process -ComputerName "Server01" | ogv -Title "Processes - Server01"
```

<span data-ttu-id="73ed2-142">Der Prüfer verwendet `ogv` , d. h. den Alias für das `Out-GridView` Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="73ed2-142">The examle uses `ogv`, which is the alias for the `Out-GridView` cmdlet.</span></span> <span data-ttu-id="73ed2-143">Der **Title** -Parameter gibt den Fenstertitel an.</span><span class="sxs-lookup"><span data-stu-id="73ed2-143">The **Title** parameter specifies the window title.</span></span>

### <span data-ttu-id="73ed2-144">Beispiel 6: Ausgeben von Daten von Remote Computern an eine Rasteransicht</span><span class="sxs-lookup"><span data-stu-id="73ed2-144">Example 6: Output data from remote computers to a grid view</span></span>

<span data-ttu-id="73ed2-145">Dieses Beispiel zeigt, wie Daten, die von Remote Computern gesammelt werden, an gesendet werden `Out-GridView` .</span><span class="sxs-lookup"><span data-stu-id="73ed2-145">This example shows how to send data collected from remote computers to `Out-GridView`.</span></span>

```powershell
Invoke-Command -ComputerName S1, S2, S3 -ScriptBlock {Get-Culture} | Out-GridView
```

<span data-ttu-id="73ed2-146">`Invoke-Command` wird `Get-Culture` auf drei Remote Computern ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="73ed2-146">`Invoke-Command` runs `Get-Culture` on three remote computers.</span></span> <span data-ttu-id="73ed2-147">Die resultierenden Daten werden an weitergeleitet `Out-GridView` .</span><span class="sxs-lookup"><span data-stu-id="73ed2-147">The resulting data is piped to `Out-GridView`.</span></span> <span data-ttu-id="73ed2-148">Beachten Sie, dass der Skriptblock, der auf dem Remote Computer ausgeführt wird, den Befehl nicht enthält `Out-GridView` .</span><span class="sxs-lookup"><span data-stu-id="73ed2-148">Notice that the script block that runs on the remote computer does not include the `Out-GridView` command.</span></span> <span data-ttu-id="73ed2-149">Wenn dies der Fall war, würde der Befehl bei dem Versuch fehlschlagen, ein Rasteransichtsfenster auf jedem Remotecomputer zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="73ed2-149">If it did, the command would fail when it tried to open a grid view window on each of the remote computers.</span></span>

### <span data-ttu-id="73ed2-150">Beispiel 7: übergeben von mehreren Elementen durch `Out-GridView`</span><span class="sxs-lookup"><span data-stu-id="73ed2-150">Example 7: Pass multiple items through `Out-GridView`</span></span>

<span data-ttu-id="73ed2-151">In diesem Beispiel können Sie mehrere Prozesse aus dem- `Out-GridView` Fenster auswählen.</span><span class="sxs-lookup"><span data-stu-id="73ed2-151">This example lets you select multiple processes from the `Out-GridView` window.</span></span> <span data-ttu-id="73ed2-152">Die Prozesse, die Sie auswählen, werden an den Befehl übermittelt `Export-Csv` und in die `ProcessLog.csv` Datei geschrieben.</span><span class="sxs-lookup"><span data-stu-id="73ed2-152">The processes that you select are passed to the `Export-Csv` command and written to the `ProcessLog.csv` file.</span></span>

```powershell
Get-Process | Out-GridView -PassThru | Export-Csv -Path .\ProcessLog.csv
```

<span data-ttu-id="73ed2-153">Der **passthru** -Parameter von `Out-GridView` ermöglicht das Senden mehrerer Elemente in der Pipeline.</span><span class="sxs-lookup"><span data-stu-id="73ed2-153">The **PassThru** parameter of `Out-GridView` lets you send multiple items down the pipeline.</span></span> <span data-ttu-id="73ed2-154">Der **PassThru**-Parameter entspricht der Verwendung des **Multiple**-Werts im **OutputMode**-Parameter.</span><span class="sxs-lookup"><span data-stu-id="73ed2-154">The **PassThru** parameter is equivalent to using the **Multiple** value of the **OutputMode** parameter.</span></span>

### <span data-ttu-id="73ed2-155">Beispiel 8: Erstellen einer Windows-Verknüpfung zu `Out-GridView`</span><span class="sxs-lookup"><span data-stu-id="73ed2-155">Example 8: Create a Windows shortcut to `Out-GridView`</span></span>

<span data-ttu-id="73ed2-156">In diesem Beispiel wird gezeigt, wie der **Wait** -Parameter von verwendet wird, `Out-GridView` um eine Windows-Verknüpfung mit dem-Fenster zu erstellen `Out-GridView` .</span><span class="sxs-lookup"><span data-stu-id="73ed2-156">This example shows how to use the **Wait** parameter of `Out-GridView` to create a Windows shortcut to the `Out-GridView` window.</span></span>

```powershell
pwsh -Command "Get-Service | Out-GridView -Wait"
```

<span data-ttu-id="73ed2-157">Diese Befehlszeile kann in einer Windows-Verknüpfung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="73ed2-157">This command line can be used in a Windows shortcut.</span></span> <span data-ttu-id="73ed2-158">Ohne den **Wait** -Parameter würde PowerShell beendet werden, sobald das `Out-GridView` Fenster geöffnet ist, wodurch das `Out-GridView` Fenster fast sofort geschlossen wird.</span><span class="sxs-lookup"><span data-stu-id="73ed2-158">Without the **Wait** parameter, PowerShell would exit as soon as the `Out-GridView` window opened, which would close the `Out-GridView` window almost immediately.</span></span>

## <span data-ttu-id="73ed2-159">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="73ed2-159">PARAMETERS</span></span>

### <span data-ttu-id="73ed2-160">-InputObject</span><span class="sxs-lookup"><span data-stu-id="73ed2-160">-InputObject</span></span>

<span data-ttu-id="73ed2-161">Gibt das Objekt an, das das Cmdlet als Eingabe akzeptiert `Out-GridView` .</span><span class="sxs-lookup"><span data-stu-id="73ed2-161">Specifies object that the cmdlet accepts as input for `Out-GridView`.</span></span>

<span data-ttu-id="73ed2-162">Wenn Sie den **Inputobject** -Parameter verwenden, um eine Auflistung von Objekten an zu senden `Out-GridView` , `Out-GridView` behandelt die Auflistung als ein Auflistungs Objekt und zeigt eine Zeile an, die die Auflistung darstellt.</span><span class="sxs-lookup"><span data-stu-id="73ed2-162">When you use the **InputObject** parameter to send a collection of objects to `Out-GridView`, `Out-GridView` treats the collection as one collection object, and it displays one row that represents the collection.</span></span> <span data-ttu-id="73ed2-163">Um jedes Objekt in der Auflistung anzuzeigen, verwenden Sie einen Pipeline Operator ( `|` ), um Objekte an zu senden `Out-GridView` .</span><span class="sxs-lookup"><span data-stu-id="73ed2-163">To display the each object in the collection, use a pipeline operator (`|`) to send objects to `Out-GridView`.</span></span>

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="73ed2-164">-Outputmode</span><span class="sxs-lookup"><span data-stu-id="73ed2-164">-OutputMode</span></span>

<span data-ttu-id="73ed2-165">Gibt die Elemente an, die das interaktive Fenster die Pipeline als Eingabe an andere Befehle sendet.</span><span class="sxs-lookup"><span data-stu-id="73ed2-165">Specifies the items that the interactive window sends down the pipeline as input to other commands.</span></span>
<span data-ttu-id="73ed2-166">Standardmäßig wird von diesem Cmdlet keine Ausgabe generiert.</span><span class="sxs-lookup"><span data-stu-id="73ed2-166">By default, this cmdlet does not generate any output.</span></span> <span data-ttu-id="73ed2-167">Um Elemente aus dem interaktiven Fenster über die Pipeline zu senden, klicken Sie auf die Elemente und dann auf „OK“.</span><span class="sxs-lookup"><span data-stu-id="73ed2-167">To send items from the interactive window down the pipeline, click to select the items and then click OK.</span></span>

<span data-ttu-id="73ed2-168">Die Werte für diesen Parameter bestimmen, wie viele Elemente Sie über die Pipeline senden können.</span><span class="sxs-lookup"><span data-stu-id="73ed2-168">The values of this parameter determine how many items you can send down the pipeline.</span></span>

- <span data-ttu-id="73ed2-169">Keine</span><span class="sxs-lookup"><span data-stu-id="73ed2-169">None.</span></span>  <span data-ttu-id="73ed2-170">Keine Elemente.</span><span class="sxs-lookup"><span data-stu-id="73ed2-170">No items.</span></span> <span data-ttu-id="73ed2-171">Dies ist der Standardwert.</span><span class="sxs-lookup"><span data-stu-id="73ed2-171">This is the default value.</span></span>
- <span data-ttu-id="73ed2-172">Einfach.</span><span class="sxs-lookup"><span data-stu-id="73ed2-172">Single.</span></span> <span data-ttu-id="73ed2-173">Ein Element oder null Elemente.</span><span class="sxs-lookup"><span data-stu-id="73ed2-173">Zero items or one item.</span></span> <span data-ttu-id="73ed2-174">Verwenden Sie diesen Wert, wenn der nächste Befehl nur jeweils ein Eingabeobjekt akzeptieren kann.</span><span class="sxs-lookup"><span data-stu-id="73ed2-174">Use this value when the next command can take only one input object.</span></span>
- <span data-ttu-id="73ed2-175">Mehr.</span><span class="sxs-lookup"><span data-stu-id="73ed2-175">Multiple.</span></span> <span data-ttu-id="73ed2-176">Null, eines oder viele Elemente.</span><span class="sxs-lookup"><span data-stu-id="73ed2-176">Zero, one, or many items.</span></span> <span data-ttu-id="73ed2-177">Verwenden Sie diesen Wert, wenn der nächste Befehl mehrere Eingabeobjekte akzeptieren kann.</span><span class="sxs-lookup"><span data-stu-id="73ed2-177">Use this value when the next command can take multiple input objects.</span></span> <span data-ttu-id="73ed2-178">Dieser Wert entspricht dem **Passthru**-Parameter.</span><span class="sxs-lookup"><span data-stu-id="73ed2-178">This value is equivalent to the **Passthru** parameter.</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.OutputModeOption
Parameter Sets: OutputMode
Aliases:
Accepted values: None, Single, Multiple

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="73ed2-179">-PassThru</span><span class="sxs-lookup"><span data-stu-id="73ed2-179">-PassThru</span></span>

<span data-ttu-id="73ed2-180">Gibt an, dass das Cmdlet Elemente aus dem interaktiven Fenster über die Pipeline als Eingabe an andere Befehle sendet.</span><span class="sxs-lookup"><span data-stu-id="73ed2-180">Indicates that the cmdlet sends items from the interactive window down the pipeline as input to other commands.</span></span> <span data-ttu-id="73ed2-181">Standardmäßig wird von diesem Cmdlet keine Ausgabe generiert.</span><span class="sxs-lookup"><span data-stu-id="73ed2-181">By default, this cmdlet does not generate any output.</span></span> <span data-ttu-id="73ed2-182">Dieser Parameter entspricht der Verwendung des **Multiple**-Werts im **OutputMode**-Parameter.</span><span class="sxs-lookup"><span data-stu-id="73ed2-182">This parameter is equivalent to using the **Multiple** value of the **OutputMode** parameter.</span></span>

<span data-ttu-id="73ed2-183">Um Elemente aus dem interaktiven Fenster über die Pipeline zu senden, klicken Sie auf die Elemente und dann auf „OK“.</span><span class="sxs-lookup"><span data-stu-id="73ed2-183">To send items from the interactive window down the pipeline, click to select the items and then click OK.</span></span> <span data-ttu-id="73ed2-184">Das Klicken bei gedrückter UMSCHALTTASTE und STRG-TASTE wird unterstützt.</span><span class="sxs-lookup"><span data-stu-id="73ed2-184">Shift-click and Ctrl-click are supported.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: PassThru
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="73ed2-185">-Title</span><span class="sxs-lookup"><span data-stu-id="73ed2-185">-Title</span></span>

<span data-ttu-id="73ed2-186">Gibt den Text an, der in der Titelleiste des `Out-GridView` Fensters angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="73ed2-186">Specifies the text that appears in the title bar of the `Out-GridView` window.</span></span> <span data-ttu-id="73ed2-187">Standardmäßig wird in der Titelleiste der Befehl angezeigt, der aufruft `Out-GridView` .</span><span class="sxs-lookup"><span data-stu-id="73ed2-187">By default, the title bar displays the command that invokes `Out-GridView`.</span></span>

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

### <span data-ttu-id="73ed2-188">-Wait</span><span class="sxs-lookup"><span data-stu-id="73ed2-188">-Wait</span></span>

<span data-ttu-id="73ed2-189">Gibt an, dass das Cmdlet die Eingabeaufforderung unterdrückt und verhindert, dass Windows PowerShell `Out-GridView` geschlossen wird, bis das Fenster geschlossen wird.</span><span class="sxs-lookup"><span data-stu-id="73ed2-189">Indicates that the cmdlet suppresses the command prompt and prevents Windows PowerShell from closing until the `Out-GridView` window is closed.</span></span> <span data-ttu-id="73ed2-190">Standardmäßig wird die Eingabeaufforderung zurückgegeben, wenn das `Out-GridView` Fenster geöffnet wird.</span><span class="sxs-lookup"><span data-stu-id="73ed2-190">By default, the command prompt returns when the `Out-GridView` window opens.</span></span>

<span data-ttu-id="73ed2-191">Mit dieser Funktion können Sie die `Out-GridView` Cmdlets in Windows-Tastenkombinationen verwenden.</span><span class="sxs-lookup"><span data-stu-id="73ed2-191">This feature lets you use the `Out-GridView` cmdlets in Windows shortcuts.</span></span> <span data-ttu-id="73ed2-192">Wenn `Out-GridView` in einer Verknüpfung ohne den **Wait** -Parameter verwendet wird, wird das `Out-GridView` Fenster nur vorübergehend angezeigt, bevor PowerShell geschlossen wird.</span><span class="sxs-lookup"><span data-stu-id="73ed2-192">When `Out-GridView` is used in a shortcut without the **Wait** parameter, the `Out-GridView` window appears only momentarily before PowerShell closes.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Wait
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="73ed2-193">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="73ed2-193">CommonParameters</span></span>

<span data-ttu-id="73ed2-194">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="73ed2-194">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="73ed2-195">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="73ed2-195">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="73ed2-196">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="73ed2-196">INPUTS</span></span>

### <span data-ttu-id="73ed2-197">System. Management. Automation. psobject</span><span class="sxs-lookup"><span data-stu-id="73ed2-197">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="73ed2-198">Sie können jedes beliebige Objekt an dieses Cmdlet senden.</span><span class="sxs-lookup"><span data-stu-id="73ed2-198">You can send any object to this cmdlet.</span></span>

## <span data-ttu-id="73ed2-199">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="73ed2-199">OUTPUTS</span></span>

### <span data-ttu-id="73ed2-200">Keine</span><span class="sxs-lookup"><span data-stu-id="73ed2-200">None</span></span>

<span data-ttu-id="73ed2-201">Normalerweise gibt keine- `Out-GridView` Objekte zurück.</span><span class="sxs-lookup"><span data-stu-id="73ed2-201">Normally, `Out-GridView` does not return any objects.</span></span> <span data-ttu-id="73ed2-202">Wenn Sie den **passthru** -Parameter verwenden, werden die Objekte, die die ausgewählten Zeilen darstellen, an die Pipeline zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="73ed2-202">When using the **PassThru** parameter, the objects representing the selected rows are returned to the pipeline.</span></span>

## <span data-ttu-id="73ed2-203">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="73ed2-203">NOTES</span></span>

<span data-ttu-id="73ed2-204">Dieses Cmdlet ist nur auf Windows-Plattformen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="73ed2-204">This cmdlet is only available on Windows platforms.</span></span>

<span data-ttu-id="73ed2-205">Sie können keinen Remotebefehl verwenden, um ein Rasteransichtsfenster auf einem anderen Computer zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="73ed2-205">You cannot use a remote command to open a grid view window on another computer.</span></span>

<span data-ttu-id="73ed2-206">Die Befehlsausgabe, die Sie an senden, `Out-GridView` kann nicht mit den- `Format` Cmdlets formatiert werden, z `Format-Table` . b.-oder- `Format-Wide` Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="73ed2-206">The command output that you send to `Out-GridView` cannot be formatted using the `Format` cmdlets, such as `Format-Table` or `Format-Wide` cmdlets.</span></span> <span data-ttu-id="73ed2-207">Verwenden Sie das-Cmdlet, um Eigenschaften auszuwählen `Select-Object` .</span><span class="sxs-lookup"><span data-stu-id="73ed2-207">To select properties, use the `Select-Object` cmdlet.</span></span>

<span data-ttu-id="73ed2-208">Die deserialisierte Ausgabe von Remotebefehlen ist möglicherweise im Rasteransichtsfenster nicht ordnungsgemäß formatiert.</span><span class="sxs-lookup"><span data-stu-id="73ed2-208">Deserialized output from remote commands might not be formatted correctly in the grid view window.</span></span>

<span data-ttu-id="73ed2-209">**Tastenkombinationen für**`Out-GridView`</span><span class="sxs-lookup"><span data-stu-id="73ed2-209">**Keyboard Shortcuts for** `Out-GridView`</span></span>

|              <span data-ttu-id="73ed2-210">Taste</span><span class="sxs-lookup"><span data-stu-id="73ed2-210">Use this key:</span></span>              |                                   <span data-ttu-id="73ed2-211">Aktion</span><span class="sxs-lookup"><span data-stu-id="73ed2-211">To perform this action:</span></span>                                    |
| --------------------------------------- | -------------------------------------------------------------------------------------------- |
| <span data-ttu-id="73ed2-212"><kbd>TABULATORTASTE</kbd></span><span class="sxs-lookup"><span data-stu-id="73ed2-212"><kbd>Tab</kbd></span></span>                          | <span data-ttu-id="73ed2-213">Verschiebt den Cursor aus dem Feld " **Filter** " in das Menü " **Kriterien hinzufügen** " in die Tabelle und wieder zurück.</span><span class="sxs-lookup"><span data-stu-id="73ed2-213">Moves the cursor from the **Filter** box to the **Add criteria** menu to the table and back.</span></span> |
| <span data-ttu-id="73ed2-214"><kbd>Oben</kbd></span><span class="sxs-lookup"><span data-stu-id="73ed2-214"><kbd>UpArrow</kbd></span></span>                      | <span data-ttu-id="73ed2-215">Verschieben Sie eine Zeile nach oben.</span><span class="sxs-lookup"><span data-stu-id="73ed2-215">Move up one row.</span></span> <span data-ttu-id="73ed2-216">Wechselt zu Spaltenüberschriften aus der ersten Daten Zeile.</span><span class="sxs-lookup"><span data-stu-id="73ed2-216">Moves to column headers from first row of data.</span></span>                             |
| <span data-ttu-id="73ed2-217"><kbd>Nach unten</kbd></span><span class="sxs-lookup"><span data-stu-id="73ed2-217"><kbd>DownArrow</kbd></span></span>                    | <span data-ttu-id="73ed2-218">Eine Zeile nach unten verschieben.</span><span class="sxs-lookup"><span data-stu-id="73ed2-218">Move down one row.</span></span>                                                                           |
| <span data-ttu-id="73ed2-219"><kbd>Links</kbd></span><span class="sxs-lookup"><span data-stu-id="73ed2-219"><kbd>LeftArrow</kbd></span></span>                    | <span data-ttu-id="73ed2-220">Verschieben Sie in der Spalten Kopfzeile eine Spalte nach links.</span><span class="sxs-lookup"><span data-stu-id="73ed2-220">In column header row, move left one column.</span></span>                                                  |
| <span data-ttu-id="73ed2-221"><kbd>RightArrow</kbd></span><span class="sxs-lookup"><span data-stu-id="73ed2-221"><kbd>RightArrow</kbd></span></span>                   | <span data-ttu-id="73ed2-222">Verschieben Sie in Spalten Kopfzeile eine Spalte nach rechts.</span><span class="sxs-lookup"><span data-stu-id="73ed2-222">In column header row, move right one column.</span></span>                                                 |
| <span data-ttu-id="73ed2-223"><kbd>Contextmenukey</kbd></span><span class="sxs-lookup"><span data-stu-id="73ed2-223"><kbd>ContextMenuKey</kbd></span></span>               | <span data-ttu-id="73ed2-224">In der Spalten Kopfzeile wird die Option Spalten auswählen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="73ed2-224">In column header row, displays the Select Columns option.</span></span>                                    |
| <span data-ttu-id="73ed2-225"><kbd>Eingabe</kbd> oder <kbd>LEERTASTE</kbd></span><span class="sxs-lookup"><span data-stu-id="73ed2-225"><kbd>Enter</kbd> or <kbd>Spacebar</kbd></span></span> | <span data-ttu-id="73ed2-226">Sortieren Sie in der Spalten Kopfzeile die Spaltendaten (A-Z, z-A umschalten).</span><span class="sxs-lookup"><span data-stu-id="73ed2-226">In column header row, sort column data (toggle A-Z, Z-A).</span></span>                                    |

<span data-ttu-id="73ed2-227">**Verwenden der Funktionen des Raster Ansichts Fensters**</span><span class="sxs-lookup"><span data-stu-id="73ed2-227">**How to Use the Grid View Window Features**</span></span>

<span data-ttu-id="73ed2-228">**So blenden Sie eine Spalte aus oder ein:**</span><span class="sxs-lookup"><span data-stu-id="73ed2-228">**To hide or show a column:**</span></span>

1. <span data-ttu-id="73ed2-229">Klicken Sie mit der rechten Maustaste auf eine beliebige Spaltenüberschrift, **und klicken Sie**</span><span class="sxs-lookup"><span data-stu-id="73ed2-229">Right-click any column header and click **Select Columns**.</span></span>
2. <span data-ttu-id="73ed2-230">Verwenden Sie im Dialogfeld **Spalten auswählen** die Pfeiltasten, um die Spalten zwischen den ausgewählten Spalten in die Felder Verfügbare Spalten zu verschieben.</span><span class="sxs-lookup"><span data-stu-id="73ed2-230">In the **Select Columns** dialog box, use the arrow keys to move the columns between the Selected columns to the Available columns boxes.</span></span> <span data-ttu-id="73ed2-231">Im Raster Ansichts Fenster werden nur Spalten im Feld **Spalten auswählen** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="73ed2-231">Only columns in the **Select Columns** box appear in the grid view window.</span></span>

<span data-ttu-id="73ed2-232">**So sortieren Sie Spalten neu:**</span><span class="sxs-lookup"><span data-stu-id="73ed2-232">**To reorder columns:**</span></span>

<span data-ttu-id="73ed2-233">Sie können Spalten per Drag & amp; Drop an die gewünschte Position verschieben.</span><span class="sxs-lookup"><span data-stu-id="73ed2-233">You can drag and drop columns into the desired location.</span></span> <span data-ttu-id="73ed2-234">Oder führen Sie die folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="73ed2-234">Or use the following steps:</span></span>

1. <span data-ttu-id="73ed2-235">Klicken Sie mit der rechten Maustaste auf eine beliebige Spaltenüberschrift, **und klicken Sie**</span><span class="sxs-lookup"><span data-stu-id="73ed2-235">Right-click any column header and click **Select Columns**.</span></span>
2. <span data-ttu-id="73ed2-236">Verwenden Sie im Dialogfeld **Spalten auswählen** die Schaltflächen nach **oben** und nach **unten** , um die Spalten neu zu sortieren.</span><span class="sxs-lookup"><span data-stu-id="73ed2-236">In the **Select Columns** dialog box, use the **Move up** and **Move down** buttons to reorder the columns.</span></span> <span data-ttu-id="73ed2-237">Spalten am oberen Rand der Liste werden links neben den Spalten am Ende der Liste im Rasteransichtsfenster angezeigt.</span><span class="sxs-lookup"><span data-stu-id="73ed2-237">Columns at the top of the list appear to the left of columns at the bottom of the list in the grid view window.</span></span>

<span data-ttu-id="73ed2-238">**Sortieren von Tabellendaten**</span><span class="sxs-lookup"><span data-stu-id="73ed2-238">**How to Sort Table Data**</span></span>

- <span data-ttu-id="73ed2-239">Um die Daten zu sortieren, klicken Sie auf eine Spaltenüberschrift.</span><span class="sxs-lookup"><span data-stu-id="73ed2-239">To sort the data, click a column header.</span></span>
- <span data-ttu-id="73ed2-240">Um die Sortierreihenfolge zu ändern, klicken Sie erneut auf die Spaltenüberschrift.</span><span class="sxs-lookup"><span data-stu-id="73ed2-240">To change the sort order, click the column header again.</span></span> <span data-ttu-id="73ed2-241">Bei jedem Klicken auf die gleiche Überschrift, wird die Sortierreihenfolge zwischen aufsteigender in absteigender Reihenfolge umgeschaltet.</span><span class="sxs-lookup"><span data-stu-id="73ed2-241">Each time you click the same header, the sort order toggles between ascending to descending order.</span></span> <span data-ttu-id="73ed2-242">Die aktuelle Reihenfolge wird durch ein Dreieck in der Spaltenüberschrift angezeigt.</span><span class="sxs-lookup"><span data-stu-id="73ed2-242">The current order is indicated by a triangle in the column header.</span></span>

<span data-ttu-id="73ed2-243">**Auswählen von Tabellendaten**</span><span class="sxs-lookup"><span data-stu-id="73ed2-243">**How to Select Table Data**</span></span>

- <span data-ttu-id="73ed2-244">Um eine Zeile auszuwählen, wählen Sie die Zeile aus, oder verwenden Sie den Pfeil nach oben oder nach unten, um zur Zeile zu navigieren.</span><span class="sxs-lookup"><span data-stu-id="73ed2-244">To select a row, select the row or use the up or down arrow to navigate to the row.</span></span>
- <span data-ttu-id="73ed2-245">Drücken Sie <kbd>STRG</kbd>A, um alle Zeilen (außer der Kopfzeile) auszuwählen + <kbd></kbd>.</span><span class="sxs-lookup"><span data-stu-id="73ed2-245">To select all rows (except for the header row), press <kbd>CTRL</kbd>+<kbd>A</kbd>.</span></span>
- <span data-ttu-id="73ed2-246">Wenn Sie aufeinander folgende Zeilen auswählen möchten, halten Sie die <kbd>UMSCHALT</kbd> Taste gedrückt, während Sie auf die Zeilen klicken oder die Pfeiltasten verwenden.</span><span class="sxs-lookup"><span data-stu-id="73ed2-246">To select consecutive rows, press and hold the <kbd>SHIFT</kbd> key while clicking the rows or using the arrow keys.</span></span>
- <span data-ttu-id="73ed2-247">Zum auswählen nicht aufeinander folgender Zeilen drücken Sie die <kbd>STRG</kbd> -Taste, und klicken Sie auf diese Option, um der Auswahl eine Zeile hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="73ed2-247">To select nonconsecutive rows, press the <kbd>CTRL</kbd> key and click to add a row to the selection.</span></span>
- <span data-ttu-id="73ed2-248">Sie können keine Spalten auswählen, und Sie können nicht die gesamte Spaltenüberschriftszeile auswählen.</span><span class="sxs-lookup"><span data-stu-id="73ed2-248">You cannot select columns, and you cannot select the entire column header row.</span></span>

<span data-ttu-id="73ed2-249">**Kopieren von Zeilen**</span><span class="sxs-lookup"><span data-stu-id="73ed2-249">**How to Copy Rows**</span></span>

- <span data-ttu-id="73ed2-250">Wenn Sie eine oder mehrere Zeilen aus der Tabelle kopieren möchten, wählen Sie die Zeilen aus, und drücken Sie dann STRG + C.</span><span class="sxs-lookup"><span data-stu-id="73ed2-250">To copy one or more rows from the table, select the rows and then press CTRL+C.</span></span>

  <span data-ttu-id="73ed2-251">Sie können die Daten in ein anderes Text- oder Tabellenkalkulationsprogramm einfügen.</span><span class="sxs-lookup"><span data-stu-id="73ed2-251">You can paste the data into any text or spreadsheet program.</span></span> <span data-ttu-id="73ed2-252">Sie können keine Spalten oder Teile von Zeilen kopieren, und Sie können nicht die Spaltenüberschriftszeile kopieren.</span><span class="sxs-lookup"><span data-stu-id="73ed2-252">You cannot copy columns or parts of rows and you cannot copy the column header row.</span></span>

<span data-ttu-id="73ed2-253">**Suchen in der Tabelle (schnell Filter)**</span><span class="sxs-lookup"><span data-stu-id="73ed2-253">**How to Search in the Table (Quick Filter)**</span></span>

<span data-ttu-id="73ed2-254">Verwenden Sie das Feld Filter, um nach Daten in der Tabelle zu suchen.</span><span class="sxs-lookup"><span data-stu-id="73ed2-254">Use the Filter box to search for data in the table.</span></span> <span data-ttu-id="73ed2-255">Wenn Sie den Suchtext in das Feld eingeben, werden nur Elemente, die den eingegebenen Text enthalten, in der Tabelle angezeigt.</span><span class="sxs-lookup"><span data-stu-id="73ed2-255">When you type in the box, only items that include the typed text appear in the table.</span></span>

- <span data-ttu-id="73ed2-256">Suchen Sie nach Text.</span><span class="sxs-lookup"><span data-stu-id="73ed2-256">Search for text.</span></span> <span data-ttu-id="73ed2-257">Um in der Tabelle nach Text zu suchen, geben Sie im Filter Feld den Text ein, der gesucht werden soll.</span><span class="sxs-lookup"><span data-stu-id="73ed2-257">To search for text in the table, in the Filter box, type the text to find.</span></span>
- <span data-ttu-id="73ed2-258">Suchen Sie nach mehreren Wörtern.</span><span class="sxs-lookup"><span data-stu-id="73ed2-258">Search for multiple words.</span></span> <span data-ttu-id="73ed2-259">Um in der Tabelle nach mehreren Wörtern zu suchen, geben Sie die Wörter durch Leerzeichen voneinander getrennt ein.</span><span class="sxs-lookup"><span data-stu-id="73ed2-259">To search for multiple words in the table, type the words separated by spaces.</span></span> <span data-ttu-id="73ed2-260">`Out-GridView` zeigt Zeilen an, die alle Wörter (logisches und) enthalten.</span><span class="sxs-lookup"><span data-stu-id="73ed2-260">`Out-GridView` displays rows that include all the words (logical AND).</span></span>
- <span data-ttu-id="73ed2-261">Suchen Sie nach literalen Ausdrücken.</span><span class="sxs-lookup"><span data-stu-id="73ed2-261">Search for literal phrases.</span></span> <span data-ttu-id="73ed2-262">Um Ausdrücke zu suchen, die Leerzeichen oder Sonderzeichen enthalten, schließen Sie den Ausdruck in Anführungszeichen ein.</span><span class="sxs-lookup"><span data-stu-id="73ed2-262">To search for phrases that include spaces or special characters, enclose the phrase in quotation marks.</span></span> <span data-ttu-id="73ed2-263">`Out-GridView` zeigt Zeilen an, die eine genaue Entsprechung für den Ausdruck enthalten.</span><span class="sxs-lookup"><span data-stu-id="73ed2-263">`Out-GridView` displays rows that include an exact match for the phrase.</span></span>
- <span data-ttu-id="73ed2-264">In Spalten suchen.</span><span class="sxs-lookup"><span data-stu-id="73ed2-264">Search in columns.</span></span> <span data-ttu-id="73ed2-265">Um in mindestens einer Spalte nach Text zu suchen, verwenden Sie das folgende Format:</span><span class="sxs-lookup"><span data-stu-id="73ed2-265">To search for text in one or more columns, use the following format:</span></span>

  `<column>:<text> [<column>:<text>] ...`

  <span data-ttu-id="73ed2-266">Wenn Sie z. b. "NET" in der Spalte " **Display Name** " suchen möchten, geben Sie im Feld **Filter** Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="73ed2-266">For example, to find "Net" in the **DisplayName** column, in the **Filter** box, type:</span></span>

  `displayname:net`

  <span data-ttu-id="73ed2-267">Wenn Sie in den Spalten **Display Name** und **Name** nach Zeilen mit "NET" suchen möchten, geben Sie im Feld **Filter** Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="73ed2-267">To find rows with "Net" in the **DisplayName** and **Name** columns, in the **Filter** box, type:</span></span>

  `displayname:net name:net`

- <span data-ttu-id="73ed2-268">Deaktivieren Sie die Suche.</span><span class="sxs-lookup"><span data-stu-id="73ed2-268">Turn off search.</span></span> <span data-ttu-id="73ed2-269">Um die gesamte Tabelle erneut anzuzeigen, klicken Sie auf die rote X-Schaltfläche in der oberen rechten Ecke des **Filter** Felds, oder löschen Sie den Text aus dem **Filter** Feld.</span><span class="sxs-lookup"><span data-stu-id="73ed2-269">To display the entire table again, click the red X button in the top right corner of the **Filter** box or delete the text from the **Filter** box.</span></span>

<span data-ttu-id="73ed2-270">**Verwenden von Kriterien zum Filtern der Tabelle**</span><span class="sxs-lookup"><span data-stu-id="73ed2-270">**Use Criteria to Filter the Table**</span></span>

<span data-ttu-id="73ed2-271">Sie können Regeln oder Kriterien verwenden, um zu bestimmen, welche Elemente in der Tabelle angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="73ed2-271">You can use rules or criteria to determine which items are displayed in the table.</span></span> <span data-ttu-id="73ed2-272">Elemente werden nur angezeigt, wenn Sie alle von Ihnen festgelegten Kriterien erfüllen.</span><span class="sxs-lookup"><span data-stu-id="73ed2-272">Items appear only when they satisfy all the criteria that you establish.</span></span> <span data-ttu-id="73ed2-273">Die verfügbaren Kriterien werden durch die Eigenschaften der Objekte, die im Rasteransichtsfenster angezeigt werden, und die .NET Framework-Typen der Eigenschaften bestimmt.</span><span class="sxs-lookup"><span data-stu-id="73ed2-273">The available criteria are determined by the properties of the objects displayed in the grid view window and the .NET Framework types of those properties.</span></span>

<span data-ttu-id="73ed2-274">Jedes Kriterium weist das folgende Format auf:</span><span class="sxs-lookup"><span data-stu-id="73ed2-274">Each criterion has the following format:</span></span>

`<column> <operator> <value>`

<span data-ttu-id="73ed2-275">Kriterien für die verschiedenen Eigenschaften sind durch **und** verbunden.</span><span class="sxs-lookup"><span data-stu-id="73ed2-275">Criteria for different properties are connected by **AND**.</span></span> <span data-ttu-id="73ed2-276">Kriterien für die gleiche Eigenschaft sind durch **oder** verbunden.</span><span class="sxs-lookup"><span data-stu-id="73ed2-276">Criteria for the same property are connected by **OR**.</span></span> <span data-ttu-id="73ed2-277">Sie können die logischen Verbindungen nicht ändern.</span><span class="sxs-lookup"><span data-stu-id="73ed2-277">You cannot change the logical connectors.</span></span>

<span data-ttu-id="73ed2-278">Die Kriterien wirken sich nur auf die Anzeige aus.</span><span class="sxs-lookup"><span data-stu-id="73ed2-278">The criteria only affects the display.</span></span> <span data-ttu-id="73ed2-279">Es werden keine Elemente aus der Tabelle gelöscht.</span><span class="sxs-lookup"><span data-stu-id="73ed2-279">It does not delete items from the table.</span></span>

<span data-ttu-id="73ed2-280">**Hinzufügen von Kriterien**</span><span class="sxs-lookup"><span data-stu-id="73ed2-280">**How to Add Criteria**</span></span>

1. <span data-ttu-id="73ed2-281">Um die Menü Schaltfläche **Kriterien hinzufügen** anzuzeigen, klicken Sie in der oberen rechten Ecke des Fensters auf den Erweiterungs Pfeil.</span><span class="sxs-lookup"><span data-stu-id="73ed2-281">To display the **Add criteria** menu button, in the upper right corner of the window, click the Expand arrow.</span></span>
2. <span data-ttu-id="73ed2-282">Klicken Sie auf die Menü Schaltfläche **Kriterien hinzufügen** .</span><span class="sxs-lookup"><span data-stu-id="73ed2-282">Click the **Add Criteria** menu button.</span></span>
3. <span data-ttu-id="73ed2-283">Klicken Sie, um Spalten (Eigenschaften) auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="73ed2-283">Click to select columns (properties).</span></span> <span data-ttu-id="73ed2-284">Sie können mindestens eine Eigenschaft auswählen.</span><span class="sxs-lookup"><span data-stu-id="73ed2-284">You can select one or many properties.</span></span>
4. <span data-ttu-id="73ed2-285">Wenn Sie die Eigenschaften ausgewählt haben, klicken Sie auf die Schaltfläche **Hinzufügen** .</span><span class="sxs-lookup"><span data-stu-id="73ed2-285">When you are finished selecting properties, click the **Add** button.</span></span>
5. <span data-ttu-id="73ed2-286">Klicken Sie auf **Abbrechen**, um die Ergänzungen abzubrechen.</span><span class="sxs-lookup"><span data-stu-id="73ed2-286">To cancel the additions, click **Cancel**.</span></span>
6. <span data-ttu-id="73ed2-287">Um weitere Kriterien hinzuzufügen, klicken Sie erneut auf die Schaltfläche **Kriterien hinzufügen** .</span><span class="sxs-lookup"><span data-stu-id="73ed2-287">To add more criteria, click the **Add Criteria** button again.</span></span>

<span data-ttu-id="73ed2-288">**Bearbeiten eines Kriteriums**</span><span class="sxs-lookup"><span data-stu-id="73ed2-288">**How to Edit a Criterion**</span></span>

- <span data-ttu-id="73ed2-289">Um einen Operator zu ändern, klicken Sie auf den Wert blauer Operator, und wählen Sie dann in der Dropdown Liste einen anderen Operator aus.</span><span class="sxs-lookup"><span data-stu-id="73ed2-289">To change an operator, click the blue operator value, and then select a different operator from the drop-down list.</span></span>
- <span data-ttu-id="73ed2-290">Geben Sie einen Wert in das Feld Wert ein, um einen Wert einzugeben oder zu ändern.</span><span class="sxs-lookup"><span data-stu-id="73ed2-290">To enter or change a value, type a value in the value box.</span></span> <span data-ttu-id="73ed2-291">Wenn Sie einen ungültigen Wert eingeben, wird ein kreisförmiges X-Symbol angezeigt.</span><span class="sxs-lookup"><span data-stu-id="73ed2-291">If you enter a value that is not valid, a circular X icon appears.</span></span> <span data-ttu-id="73ed2-292">Ändern Sie den Wert, um dies zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="73ed2-292">To remove it, change the value.</span></span>
- <span data-ttu-id="73ed2-293">Fügen Sie zum Erstellen einer- **oder** -Anweisung ein Kriterium mit derselben Eigenschaft hinzu.</span><span class="sxs-lookup"><span data-stu-id="73ed2-293">To create an **OR** statement, add a criteria with the same property.</span></span>

<span data-ttu-id="73ed2-294">**Löschen von Kriterien**</span><span class="sxs-lookup"><span data-stu-id="73ed2-294">**How to Delete Criteria**</span></span>

- <span data-ttu-id="73ed2-295">Um die ausgewählten Kriterien zu löschen, klicken Sie neben jedem Kriterium auf das rote X.</span><span class="sxs-lookup"><span data-stu-id="73ed2-295">To delete selected criteria, click the red X beside each criterion.</span></span>
- <span data-ttu-id="73ed2-296">Wenn Sie alle Kriterien löschen möchten, klicken Sie auf die Schaltfläche **alle** löschen.</span><span class="sxs-lookup"><span data-stu-id="73ed2-296">To delete all criteria, click the **Clear All** button.</span></span>

## <span data-ttu-id="73ed2-297">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="73ed2-297">RELATED LINKS</span></span>

[<span data-ttu-id="73ed2-298">Out-File</span><span class="sxs-lookup"><span data-stu-id="73ed2-298">Out-File</span></span>](Out-File.md)

[<span data-ttu-id="73ed2-299">Out-Printer</span><span class="sxs-lookup"><span data-stu-id="73ed2-299">Out-Printer</span></span>](Out-Printer.md)

[<span data-ttu-id="73ed2-300">Out-String</span><span class="sxs-lookup"><span data-stu-id="73ed2-300">Out-String</span></span>](Out-String.md)
