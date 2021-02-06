---
description: Kombinieren von Befehlen in Pipelines in PowerShell
Locale: en-US
ms.date: 09/27/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_pipelines?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Pipelines
ms.openlocfilehash: e4ae85fbbfe5232048a90e1fe4f62db3e95e5f1b
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99599645"
---
# <a name="about-pipelines"></a><span data-ttu-id="917b7-103">Informationen zu Pipelines</span><span class="sxs-lookup"><span data-stu-id="917b7-103">About Pipelines</span></span>

## <a name="short-description"></a><span data-ttu-id="917b7-104">Kurze Beschreibung</span><span class="sxs-lookup"><span data-stu-id="917b7-104">Short description</span></span>

<span data-ttu-id="917b7-105">Kombinieren von Befehlen in Pipelines in PowerShell</span><span class="sxs-lookup"><span data-stu-id="917b7-105">Combining commands into pipelines in the PowerShell</span></span>

## <a name="long-description"></a><span data-ttu-id="917b7-106">Lange Beschreibung</span><span class="sxs-lookup"><span data-stu-id="917b7-106">Long description</span></span>

<span data-ttu-id="917b7-107">Eine Pipeline ist eine Reihe von Befehlen, die durch Pipeline Operatoren ( `|` ) (ASCII 124) verbunden sind.</span><span class="sxs-lookup"><span data-stu-id="917b7-107">A pipeline is a series of commands connected by pipeline operators (`|`) (ASCII 124).</span></span> <span data-ttu-id="917b7-108">Jeder Pipeline Operator sendet die Ergebnisse des vorangehenden Befehls an den nächsten Befehl.</span><span class="sxs-lookup"><span data-stu-id="917b7-108">Each pipeline operator sends the results of the preceding command to the next command.</span></span>

<span data-ttu-id="917b7-109">Die Ausgabe des ersten Befehls kann als Eingabe für den zweiten Befehl zur Verarbeitung gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="917b7-109">The output of the first command can be sent for processing as input to the second command.</span></span> <span data-ttu-id="917b7-110">Und diese Ausgabe kann an einen anderen Befehl gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="917b7-110">And that output can be sent to yet another command.</span></span> <span data-ttu-id="917b7-111">Das Ergebnis ist eine komplexe Befehlskette oder _Pipeline_ , die aus einer Reihe einfacher Befehle besteht.</span><span class="sxs-lookup"><span data-stu-id="917b7-111">The result is a complex command chain or _pipeline_ that is composed of a series of simple commands.</span></span>

<span data-ttu-id="917b7-112">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="917b7-112">For example,</span></span>

```powershell
Command-1 | Command-2 | Command-3
```

<span data-ttu-id="917b7-113">In diesem Beispiel werden die-Objekte, die `Command-1` ausgibt, an gesendet `Command-2` .</span><span class="sxs-lookup"><span data-stu-id="917b7-113">In this example, the objects that `Command-1` emits are sent to `Command-2`.</span></span>
<span data-ttu-id="917b7-114">`Command-2` verarbeitet die-Objekte und sendet Sie an `Command-3` .</span><span class="sxs-lookup"><span data-stu-id="917b7-114">`Command-2` processes the objects and sends them to `Command-3`.</span></span> <span data-ttu-id="917b7-115">`Command-3` verarbeitet die Objekte und sendet Sie über die Pipeline.</span><span class="sxs-lookup"><span data-stu-id="917b7-115">`Command-3` processes the objects and send them down the pipeline.</span></span> <span data-ttu-id="917b7-116">Da in der Pipeline keine weiteren Befehle vorhanden sind, werden die Ergebnisse in der Konsole angezeigt.</span><span class="sxs-lookup"><span data-stu-id="917b7-116">Because there are no more commands in the pipeline, the results are displayed at the console.</span></span>

<span data-ttu-id="917b7-117">In einer Pipeline werden die Befehle in der Reihenfolge von links nach rechts verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="917b7-117">In a pipeline, the commands are processed in order from left to right.</span></span> <span data-ttu-id="917b7-118">Die Verarbeitung wird als einzelner Vorgang behandelt, und die Ausgabe wird angezeigt, wenn Sie generiert wird.</span><span class="sxs-lookup"><span data-stu-id="917b7-118">The processing is handled as a single operation and output is displayed as it's generated.</span></span>

<span data-ttu-id="917b7-119">Hier ist ein einfaches Beispiel.</span><span class="sxs-lookup"><span data-stu-id="917b7-119">Here is a simple example.</span></span> <span data-ttu-id="917b7-120">Der folgende Befehl ruft den Notepad-Prozess ab und beendet ihn.</span><span class="sxs-lookup"><span data-stu-id="917b7-120">The following command gets the Notepad process and then stops it.</span></span>

<span data-ttu-id="917b7-121">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="917b7-121">For example,</span></span>

```powershell
Get-Process notepad | Stop-Process
```

<span data-ttu-id="917b7-122">Der erste Befehl verwendet das `Get-Process` Cmdlet, um ein Objekt zu erhalten, das den Notepad-Prozess darstellt.</span><span class="sxs-lookup"><span data-stu-id="917b7-122">The first command uses the `Get-Process` cmdlet to get an object representing the Notepad process.</span></span> <span data-ttu-id="917b7-123">Er verwendet einen Pipeline Operator ( `|` ), um das Process-Objekt an das `Stop-Process` Cmdlet zu senden, das den Notepad-Prozess beendet.</span><span class="sxs-lookup"><span data-stu-id="917b7-123">It uses a pipeline operator (`|`) to send the process object to the `Stop-Process` cmdlet, which stops the Notepad process.</span></span> <span data-ttu-id="917b7-124">Beachten Sie, dass der `Stop-Process` Befehl keinen **namens** -oder **ID** -Parameter besitzt, um den Prozess anzugeben, da der angegebene Prozess über die Pipeline übermittelt wird.</span><span class="sxs-lookup"><span data-stu-id="917b7-124">Notice that the `Stop-Process` command doesn't have a **Name** or **ID** parameter to specify the process, because the specified process is submitted through the pipeline.</span></span>

<span data-ttu-id="917b7-125">Dieses Pipeline Beispiel ruft die Textdateien im aktuellen Verzeichnis ab, wählt nur die Dateien aus, die mehr als 10.000 Bytes lang sind, sortiert sie nach Länge und zeigt den Namen und die Länge jeder Datei in einer Tabelle an.</span><span class="sxs-lookup"><span data-stu-id="917b7-125">This pipeline example gets the text files in the current directory, selects only the files that are more than 10,000 bytes long, sorts them by length, and displays the name and length of each file in a table.</span></span>

```powershell
Get-ChildItem -Path *.txt |
  Where-Object {$_.length -gt 10000} |
    Sort-Object -Property length |
      Format-Table -Property name, length
```

<span data-ttu-id="917b7-126">Diese Pipeline besteht aus vier Befehlen in der angegebenen Reihenfolge.</span><span class="sxs-lookup"><span data-stu-id="917b7-126">This pipeline consists of four commands in the specified order.</span></span> <span data-ttu-id="917b7-127">Die folgende Abbildung zeigt die Ausgabe der einzelnen Befehle, wenn Sie an den nächsten Befehl in der Pipeline weitergeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="917b7-127">The following illustration shows the output from each command as it's passed to the next command in the pipeline.</span></span>

```
Get-ChildItem -Path *.txt
| (FileInfo objects for *.txt)
V
Where-Object {$_.length -gt 10000}
| (FileInfo objects for *.txt)
| (      Length > 10000      )
V
Sort-Object -Property Length
| (FileInfo objects for *.txt)
| (      Length > 10000      )
| (     Sorted by length     )
V
Format-Table -Property name, length
| (FileInfo objects for *.txt)
| (      Length > 10000      )
| (     Sorted by length     )
| (   Formatted in a table   )
V

Name                       Length
----                       ------
tmp1.txt                    82920
tmp2.txt                   114000
tmp3.txt                   114000
```

## <a name="using-pipelines"></a><span data-ttu-id="917b7-128">Verwenden von Pipelines</span><span class="sxs-lookup"><span data-stu-id="917b7-128">Using pipelines</span></span>

<span data-ttu-id="917b7-129">Die meisten PowerShell-Cmdlets sind für die Unterstützung von Pipelines konzipiert.</span><span class="sxs-lookup"><span data-stu-id="917b7-129">Most PowerShell cmdlets are designed to support pipelines.</span></span> <span data-ttu-id="917b7-130">In den meisten Fällen können Sie die Ergebnisse eines **Get** -Cmdlets über die _Pipeline_ an ein anderes Cmdlet desselben Substantivs übergeben.</span><span class="sxs-lookup"><span data-stu-id="917b7-130">In most cases, you can _pipe_ the results of a **Get** cmdlet to another cmdlet of the same noun.</span></span>
<span data-ttu-id="917b7-131">Beispielsweise können Sie die Ausgabe des- `Get-Service` Cmdlets an das- `Start-Service` Cmdlet oder das- `Stop-Service` Cmdlet weiterreichen.</span><span class="sxs-lookup"><span data-stu-id="917b7-131">For example, you can pipe the output of the `Get-Service` cmdlet to the `Start-Service` or `Stop-Service` cmdlets.</span></span>

<span data-ttu-id="917b7-132">Diese Beispiel Pipeline startet den WMI-Dienst auf dem Computer:</span><span class="sxs-lookup"><span data-stu-id="917b7-132">This example pipeline starts the WMI service on the computer:</span></span>

```powershell
Get-Service wmi | Start-Service
```

<span data-ttu-id="917b7-133">Ein weiteres Beispiel: Sie können die Ausgabe von `Get-Item` oder `Get-ChildItem` innerhalb des PowerShell-Registrierungs Anbieters an das- `New-ItemProperty` Cmdlet weiterreichen.</span><span class="sxs-lookup"><span data-stu-id="917b7-133">For another example, you can pipe the output of `Get-Item` or `Get-ChildItem` within the PowerShell registry provider to the `New-ItemProperty` cmdlet.</span></span> <span data-ttu-id="917b7-134">In diesem Beispiel wird dem Registrierungsschlüssel **MyCompany** ein neuer Registrierungs Eintrag, **noofemployees**, mit dem Wert **8124** hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="917b7-134">This example adds a new registry entry, **NoOfEmployees**, with a value of **8124**, to the **MyCompany** registry key.</span></span>

```powershell
Get-Item -Path HKLM:\Software\MyCompany |
  New-ItemProperty -Name NoOfEmployees -Value 8124
```

<span data-ttu-id="917b7-135">Viele der hilfsprogrammcmdlets, z. b. `Get-Member` , `Where-Object` , `Sort-Object` , `Group-Object` und, `Measure-Object` werden nahezu exklusiv in Pipelines verwendet.</span><span class="sxs-lookup"><span data-stu-id="917b7-135">Many of the utility cmdlets, such as `Get-Member`, `Where-Object`, `Sort-Object`, `Group-Object`, and `Measure-Object` are used almost exclusively in pipelines.</span></span> <span data-ttu-id="917b7-136">Sie können einen beliebigen Objekttyp an diese Cmdlets übergeben.</span><span class="sxs-lookup"><span data-stu-id="917b7-136">You can pipe any object type to these cmdlets.</span></span> <span data-ttu-id="917b7-137">Dieses Beispiel zeigt, wie alle Prozesse auf dem Computer nach der Anzahl der geöffneten Handles in jedem Prozess sortiert werden.</span><span class="sxs-lookup"><span data-stu-id="917b7-137">This example shows how to sort all the processes on the computer by the number of open handles in each process.</span></span>

```powershell
Get-Process | Sort-Object -Property handles
```

<span data-ttu-id="917b7-138">Sie können Objekte über die Pipeline an die Formatierungs-, Export-und Ausgabe-Cmdlets übergeben, z `Format-List` `Format-Table` . b.,, `Export-Clixml` , `Export-CSV` und `Out-File` .</span><span class="sxs-lookup"><span data-stu-id="917b7-138">You can pipe objects to the formatting, export, and output cmdlets, such as `Format-List`, `Format-Table`, `Export-Clixml`, `Export-CSV`, and `Out-File`.</span></span>

<span data-ttu-id="917b7-139">Dieses Beispiel zeigt, wie das `Format-List` Cmdlet verwendet wird, um eine Liste von Eigenschaften für ein Prozess Objekt anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="917b7-139">This example shows how to use the `Format-List` cmdlet to display a list of properties for a process object.</span></span>

```powershell
Get-Process winlogon | Format-List -Property *
```

<span data-ttu-id="917b7-140">In der Praxis werden Sie feststellen, dass die Kombination einfacher Befehle in Pipelines Zeit und Eingabe spart und die Skripterstellung effizienter macht.</span><span class="sxs-lookup"><span data-stu-id="917b7-140">With a bit of practice, you'll find that combining simple commands into pipelines saves time and typing, and makes your scripting more efficient.</span></span>

## <a name="how-pipelines-work"></a><span data-ttu-id="917b7-141">Funktionsweise von Pipelines</span><span class="sxs-lookup"><span data-stu-id="917b7-141">How pipelines work</span></span>

<span data-ttu-id="917b7-142">In diesem Abschnitt wird erläutert, wie Eingabe Objekte an Cmdlet-Parameter gebunden und während der Pipeline Ausführung verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="917b7-142">This section explains how input objects are bound to cmdlet parameters and processed during pipeline execution.</span></span>

### <a name="accepts-pipeline-input"></a><span data-ttu-id="917b7-143">Akzeptiert Pipeline Eingaben</span><span class="sxs-lookup"><span data-stu-id="917b7-143">Accepts pipeline input</span></span>

<span data-ttu-id="917b7-144">Um Pipelining zu unterstützen, muss das empfangende Cmdlet über einen Parameter verfügen, der Pipeline Eingaben akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="917b7-144">To support pipelining, the receiving cmdlet must have a parameter that accepts pipeline input.</span></span> <span data-ttu-id="917b7-145">Verwenden Sie den- `Get-Help` Befehl mit den Optionen **Full** oder **Parameter** , um zu bestimmen, welche Parameter eines Cmdlets Pipeline Eingaben akzeptieren.</span><span class="sxs-lookup"><span data-stu-id="917b7-145">Use the `Get-Help` command with the **Full** or **Parameter** options to determine which parameters of a cmdlet accept pipeline input.</span></span>

<span data-ttu-id="917b7-146">Geben Sie z. b. Folgendes ein, um zu bestimmen, welcher der Parameter des `Start-Service` Cmdlets Pipeline Eingaben akzeptiert:</span><span class="sxs-lookup"><span data-stu-id="917b7-146">For example, to determine which of the parameters of the `Start-Service` cmdlet accepts pipeline input, type:</span></span>

```powershell
Get-Help Start-Service -Full
```

<span data-ttu-id="917b7-147">oder</span><span class="sxs-lookup"><span data-stu-id="917b7-147">or</span></span>

```powershell
Get-Help Start-Service -Parameter *
```

<span data-ttu-id="917b7-148">Die Hilfe für das `Start-Service` Cmdlet zeigt, dass nur der **Inputobject** -Parameter und der **Name** -Parameter Pipeline Eingaben akzeptieren.</span><span class="sxs-lookup"><span data-stu-id="917b7-148">The help for the `Start-Service` cmdlet shows that only the **InputObject** and **Name** parameters accept pipeline input.</span></span>

```Output
-InputObject <ServiceController[]>
Specifies ServiceController objects representing the services to be started.
Enter a variable that contains the objects, or type a command or expression
that gets the objects.

Required?                    true
Position?                    0
Default value                None
Accept pipeline input?       True (ByValue)
Accept wildcard characters?  false

-Name <String[]>
Specifies the service names for the service to be started.

The parameter name is optional. You can use Name or its alias, ServiceName,
or you can omit the parameter name.

Required?                    true
Position?                    0
Default value                None
Accept pipeline input?       True (ByPropertyName, ByValue)
Accept wildcard characters?  false
```

<span data-ttu-id="917b7-149">Wenn Sie Objekte über die Pipeline an senden `Start-Service` , versucht PowerShell, die Objekte den **Inputobject** -und **Name** -Parametern zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="917b7-149">When you send objects through the pipeline to `Start-Service`, PowerShell attempts to associate the objects with the **InputObject** and **Name** parameters.</span></span>

### <a name="methods-of-accepting-pipeline-input"></a><span data-ttu-id="917b7-150">Methoden zum Akzeptieren von Pipeline Eingaben</span><span class="sxs-lookup"><span data-stu-id="917b7-150">Methods of accepting pipeline input</span></span>

<span data-ttu-id="917b7-151">Cmdlets-Parameter können eine Pipeline Eingabe auf zwei verschiedene Arten akzeptieren:</span><span class="sxs-lookup"><span data-stu-id="917b7-151">Cmdlets parameters can accept pipeline input in one of two different ways:</span></span>

- <span data-ttu-id="917b7-152">**Byvalue**: der Parameter akzeptiert Werte, die dem erwarteten .NET-Typ entsprechen oder in diesen Typ konvertiert werden können.</span><span class="sxs-lookup"><span data-stu-id="917b7-152">**ByValue**: The parameter accepts values that match the expected .NET type or that can be converted to that type.</span></span>

  <span data-ttu-id="917b7-153">Der **Name** -Parameter von akzeptiert beispielsweise `Start-Service` Pipeline Eingaben nach Wert.</span><span class="sxs-lookup"><span data-stu-id="917b7-153">For example, the **Name** parameter of `Start-Service` accepts pipeline input by value.</span></span> <span data-ttu-id="917b7-154">Sie kann Zeichen folgen Objekte oder-Objekte akzeptieren, die in Zeichen folgen konvertiert werden können.</span><span class="sxs-lookup"><span data-stu-id="917b7-154">It can accept string objects or objects that can be converted to strings.</span></span>

- <span data-ttu-id="917b7-155">**Bypropertyname**: der-Parameter akzeptiert nur Eingaben, wenn das Eingabe Objekt eine Eigenschaft mit dem gleichen Namen wie der-Parameter aufweist.</span><span class="sxs-lookup"><span data-stu-id="917b7-155">**ByPropertyName**: The parameter accepts input only when the input object has a property of the same name as the parameter.</span></span>

  <span data-ttu-id="917b7-156">Der Name-Parameter von kann z `Start-Service` . b.-Objekte akzeptieren, die über eine **Name** -Eigenschaft verfügen.</span><span class="sxs-lookup"><span data-stu-id="917b7-156">For example, the Name parameter of `Start-Service` can accept objects that have a **Name** property.</span></span> <span data-ttu-id="917b7-157">Um die Eigenschaften eines Objekts aufzulisten, übergeben Sie es an `Get-Member` .</span><span class="sxs-lookup"><span data-stu-id="917b7-157">To list the properties of an object, pipe it to `Get-Member`.</span></span>

<span data-ttu-id="917b7-158">Einige Parameter können Objekte sowohl nach Wert als auch nach Eigenschaftsname akzeptieren, sodass Sie die Eingabe von der Pipeline vereinfachen.</span><span class="sxs-lookup"><span data-stu-id="917b7-158">Some parameters can accept objects by both value or property name, making it easier to take input from the pipeline.</span></span>

### <a name="parameter-binding"></a><span data-ttu-id="917b7-159">Parameterbindung</span><span class="sxs-lookup"><span data-stu-id="917b7-159">Parameter binding</span></span>

<span data-ttu-id="917b7-160">Wenn Sie Objekte von einem Befehl an einen anderen Befehl übergeben, versucht PowerShell, die weitergeleiteten Objekte einem Parameter des empfangenden Cmdlets zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="917b7-160">When you pipe objects from one command to another command, PowerShell attempts to associate the piped objects with a parameter of the receiving cmdlet.</span></span>

<span data-ttu-id="917b7-161">Die Parameter bindungskomponente von PowerShell ordnet die Eingabe Objekte den Cmdlet-Parametern gemäß den folgenden Kriterien zu:</span><span class="sxs-lookup"><span data-stu-id="917b7-161">PowerShell's parameter binding component associates the input objects with cmdlet parameters according to the following criteria:</span></span>

- <span data-ttu-id="917b7-162">Der-Parameter muss Eingaben aus einer Pipeline akzeptieren.</span><span class="sxs-lookup"><span data-stu-id="917b7-162">The parameter must accept input from a pipeline.</span></span>
- <span data-ttu-id="917b7-163">Der-Parameter muss den Typ des gesendeten Objekts oder einen Typ akzeptieren, der in den erwarteten Typ konvertiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="917b7-163">The parameter must accept the type of object being sent or a type that can be converted to the expected type.</span></span>
- <span data-ttu-id="917b7-164">Der-Parameter wurde im Befehl nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="917b7-164">The parameter wasn't used in the command.</span></span>

<span data-ttu-id="917b7-165">Beispielsweise hat das `Start-Service` Cmdlet viele Parameter, aber nur zwei von Ihnen, **Name** und **Inputobject** akzeptieren Pipeline Eingaben.</span><span class="sxs-lookup"><span data-stu-id="917b7-165">For example, the `Start-Service` cmdlet has many parameters, but only two of them, **Name** and **InputObject** accept pipeline input.</span></span> <span data-ttu-id="917b7-166">Der **Name** -Parameter nimmt Zeichen folgen an, und der **Inputobject** -Parameter übernimmt Dienst Objekte.</span><span class="sxs-lookup"><span data-stu-id="917b7-166">The **Name** parameter takes strings and the **InputObject** parameter takes service objects.</span></span> <span data-ttu-id="917b7-167">Daher können Sie Zeichen folgen, Dienst Objekte und Objekte mit Eigenschaften übergeben, die in Zeichen folgen-oder Dienst Objekte konvertiert werden können.</span><span class="sxs-lookup"><span data-stu-id="917b7-167">Therefore, you can pipe strings, service objects, and objects with properties that can be converted to string or service objects.</span></span>

<span data-ttu-id="917b7-168">PowerShell verwaltet die Parameter Bindung so effizient wie möglich.</span><span class="sxs-lookup"><span data-stu-id="917b7-168">PowerShell manages parameter binding as efficiently as possible.</span></span> <span data-ttu-id="917b7-169">Sie können nicht vorschlagen oder erzwingen, dass PowerShell an einen bestimmten Parameter gebunden wird.</span><span class="sxs-lookup"><span data-stu-id="917b7-169">You can't suggest or force the PowerShell to bind to a specific parameter.</span></span> <span data-ttu-id="917b7-170">Der Befehl schlägt fehl, wenn die weitergeleiteten Objekte von PowerShell nicht gebunden werden können.</span><span class="sxs-lookup"><span data-stu-id="917b7-170">The command fails if PowerShell can't bind the piped objects.</span></span>

<span data-ttu-id="917b7-171">Weitere Informationen zur Problembehandlung bei Bindungs Fehlern finden Sie unter unter [Suchen von Pipeline Fehlern](#investigating-pipeline-errors) weiter unten in diesem Artikel.</span><span class="sxs-lookup"><span data-stu-id="917b7-171">For more information about troubleshooting binding errors, see [Investigating Pipeline Errors](#investigating-pipeline-errors) later in this article.</span></span>

### <a name="one-at-a-time-processing"></a><span data-ttu-id="917b7-172">Uni-at-a-Time-Verarbeitung</span><span class="sxs-lookup"><span data-stu-id="917b7-172">One-at-a-time processing</span></span>

<span data-ttu-id="917b7-173">Das Weiterleiten von Objekten an einen Befehl ähnelt dem Verwenden eines Parameters des Befehls, um die Objekte zu übermitteln.</span><span class="sxs-lookup"><span data-stu-id="917b7-173">Piping objects to a command is much like using a parameter of the command to submit the objects.</span></span> <span data-ttu-id="917b7-174">Sehen wir uns ein Beispiel für eine Pipeline an.</span><span class="sxs-lookup"><span data-stu-id="917b7-174">Let's look at a pipeline example.</span></span> <span data-ttu-id="917b7-175">In diesem Beispiel verwenden wir eine Pipeline, um eine Tabelle mit Dienst Objekten anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="917b7-175">In this example, we use a pipeline to display a table of service objects.</span></span>

```powershell
Get-Service | Format-Table -Property Name, DependentServices
```

<span data-ttu-id="917b7-176">Funktionell ist dies die Verwendung des **Inputobject** -Parameters von `Format-Table` zum übermitteln der Objekt Auflistung.</span><span class="sxs-lookup"><span data-stu-id="917b7-176">Functionally, this is like using the **InputObject** parameter of `Format-Table` to submit the object collection.</span></span>

<span data-ttu-id="917b7-177">Beispielsweise können wir die Auflistung der Dienste in einer Variablen speichern, die mithilfe des **Inputobject** -Parameters übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="917b7-177">For example, we can save the collection of services to a variable that is passed using the **InputObject** parameter.</span></span>

```powershell
$services = Get-Service
Format-Table -InputObject $services -Property Name, DependentServices
```

<span data-ttu-id="917b7-178">Oder Sie können den Befehl in den **Inputobject-Parameter einbetten** .</span><span class="sxs-lookup"><span data-stu-id="917b7-178">Or we can embed the command in the **InputObject** parameter.</span></span>

```powershell
Format-Table -InputObject (Get-Service) -Property Name, DependentServices
```

<span data-ttu-id="917b7-179">Es gibt jedoch einen wichtigen Unterschied.</span><span class="sxs-lookup"><span data-stu-id="917b7-179">However, there's an important difference.</span></span> <span data-ttu-id="917b7-180">Wenn Sie mehrere Objekte an einen Befehl übergeben, sendet PowerShell die Objekte nacheinander an den Befehl.</span><span class="sxs-lookup"><span data-stu-id="917b7-180">When you pipe multiple objects to a command, PowerShell sends the objects to the command one at a time.</span></span> <span data-ttu-id="917b7-181">Wenn Sie einen Command-Parameter verwenden, werden die-Objekte als einzelnes Array Objekt gesendet.</span><span class="sxs-lookup"><span data-stu-id="917b7-181">When you use a command parameter, the objects are sent as a single array object.</span></span> <span data-ttu-id="917b7-182">Dieser geringfügige Unterschied hat bedeutende Konsequenzen.</span><span class="sxs-lookup"><span data-stu-id="917b7-182">This minor difference has significant consequences.</span></span>

<span data-ttu-id="917b7-183">Beim Ausführen einer Pipeline listet PowerShell automatisch jeden Typ auf, der die- `IEnumerable` Schnittstelle implementiert, und sendet die Elemente nacheinander über die Pipeline.</span><span class="sxs-lookup"><span data-stu-id="917b7-183">When executing a pipeline, PowerShell automatically enumerates any type that implements the `IEnumerable` interface and sends the members through the pipeline one at a time.</span></span> <span data-ttu-id="917b7-184">Die Ausnahme ist `[hashtable]` , was einen aufzurufenden- `GetEnumerator()` Methode erfordert.</span><span class="sxs-lookup"><span data-stu-id="917b7-184">The exception is `[hashtable]`, which requires a call to the `GetEnumerator()` method.</span></span>

<span data-ttu-id="917b7-185">In den folgenden Beispielen werden ein Array und eine Hash Tabelle an das `Measure-Object` Cmdlet weitergeleitet, um die Anzahl der Objekte zu zählen, die von der Pipeline empfangen werden.</span><span class="sxs-lookup"><span data-stu-id="917b7-185">In the following examples, an array and a hashtable are piped to the `Measure-Object` cmdlet to count the number of objects received from the pipeline.</span></span> <span data-ttu-id="917b7-186">Das Array verfügt über mehrere Member, und die Hash Tabelle verfügt über mehrere Schlüssel-Wert-Paare.</span><span class="sxs-lookup"><span data-stu-id="917b7-186">The array has multiple members, and the hashtable has multiple key-value pairs.</span></span> <span data-ttu-id="917b7-187">Nur das Array wird nacheinander aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="917b7-187">Only the array is enumerated one at a time.</span></span>

```powershell
@(1,2,3) | Measure-Object
```

```Output
Count    : 3
Average  :
Sum      :
Maximum  :
Minimum  :
Property :
```

```powershell
@{"One"=1;"Two"=2} | Measure-Object
```

```Output
Count    : 1
Average  :
Sum      :
Maximum  :
Minimum  :
Property :
```

<span data-ttu-id="917b7-188">Wenn Sie mehrere Prozess Objekte aus dem `Get-Process` Cmdlet an das `Get-Member` Cmdlet weiterreichen, sendet PowerShell jedes Prozess Objekt einzeln an `Get-Member` .</span><span class="sxs-lookup"><span data-stu-id="917b7-188">Similarly, if you pipe multiple process objects from the `Get-Process` cmdlet to the `Get-Member` cmdlet, PowerShell sends each process object, one at a time, to `Get-Member`.</span></span> <span data-ttu-id="917b7-189">`Get-Member` zeigt die .NET-Klasse (Typ) der Prozess Objekte und ihre Eigenschaften und Methoden an.</span><span class="sxs-lookup"><span data-stu-id="917b7-189">`Get-Member` displays the .NET class (type) of the process objects, and their properties and methods.</span></span>

```powershell
Get-Process | Get-Member
```

```Output
TypeName: System.Diagnostics.Process

Name      MemberType     Definition
----      ----------     ----------
Handles   AliasProperty  Handles = Handlecount
Name      AliasProperty  Name = ProcessName
NPM       AliasProperty  NPM = NonpagedSystemMemorySize
...
```

> [!NOTE]
> <span data-ttu-id="917b7-190">`Get-Member` entfernt Duplikate, sodass nur ein Objekttyp angezeigt wird, wenn die Objekte alle denselben Typ haben.</span><span class="sxs-lookup"><span data-stu-id="917b7-190">`Get-Member` eliminates duplicates, so if the objects are all of the same type, it only displays one object type.</span></span>

<span data-ttu-id="917b7-191">Wenn Sie jedoch den **Inputobject** -Parameter von verwenden `Get-Member` , `Get-Member` empfängt ein Array von **System. Diagnostics. Process** -Objekten als einzelne Einheit.</span><span class="sxs-lookup"><span data-stu-id="917b7-191">However, if you use the **InputObject** parameter of `Get-Member`, then `Get-Member` receives an array of **System.Diagnostics.Process** objects as a single unit.</span></span> <span data-ttu-id="917b7-192">Es zeigt die Eigenschaften eines Arrays von-Objekten an.</span><span class="sxs-lookup"><span data-stu-id="917b7-192">It displays the properties of an array of objects.</span></span> <span data-ttu-id="917b7-193">(Beachten Sie das Array Symbol ( `[]` ) nach dem **System. Object** -Typnamen.)</span><span class="sxs-lookup"><span data-stu-id="917b7-193">(Note the array symbol (`[]`) after the **System.Object** type name.)</span></span>

<span data-ttu-id="917b7-194">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="917b7-194">For example,</span></span>

```powershell
Get-Member -InputObject (Get-Process)
```

```Output
TypeName: System.Object[]

Name               MemberType    Definition
----               ----------    ----------
Count              AliasProperty Count = Length
Address            Method        System.Object& Address(Int32 )
Clone              Method        System.Object Clone()
...
```

<span data-ttu-id="917b7-195">Das Ergebnis ist möglicherweise nicht das, was Sie beabsichtigt haben.</span><span class="sxs-lookup"><span data-stu-id="917b7-195">This result might not be what you intended.</span></span> <span data-ttu-id="917b7-196">Aber nachdem Sie es verstanden haben, können Sie es verwenden.</span><span class="sxs-lookup"><span data-stu-id="917b7-196">But after you understand it, you can use it.</span></span> <span data-ttu-id="917b7-197">Beispielsweise verfügen alle Array Objekte über eine **count** -Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="917b7-197">For example, all array objects have a **Count** property.</span></span> <span data-ttu-id="917b7-198">Damit können Sie die Anzahl der Prozesse zählen, die auf dem Computer ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="917b7-198">You can use that to count the number of processes running on the computer.</span></span>

<span data-ttu-id="917b7-199">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="917b7-199">For example,</span></span>

```powershell
(Get-Process).count
```

<span data-ttu-id="917b7-200">Beachten Sie, dass Objekte, die über die Pipeline gesendet werden, nacheinander zugestellt werden.</span><span class="sxs-lookup"><span data-stu-id="917b7-200">It's important to remember that objects sent down the pipeline are delivered one at a time.</span></span>

## <a name="investigating-pipeline-errors"></a><span data-ttu-id="917b7-201">Untersuchen von Pipeline Fehlern</span><span class="sxs-lookup"><span data-stu-id="917b7-201">Investigating pipeline errors</span></span>

<span data-ttu-id="917b7-202">Wenn PowerShell die weitergeleiteten Objekte keinem Parameter des empfangenden Cmdlets zuordnen kann, schlägt der Befehl fehl.</span><span class="sxs-lookup"><span data-stu-id="917b7-202">When PowerShell can't associate the piped objects with a parameter of the receiving cmdlet, the command fails.</span></span>

<span data-ttu-id="917b7-203">Im folgenden Beispiel wird versucht, einen Registrierungs Eintrag aus einem Registrierungsschlüssel in einen anderen zu verschieben.</span><span class="sxs-lookup"><span data-stu-id="917b7-203">In the following example, we try to move a registry entry from one registry key to another.</span></span> <span data-ttu-id="917b7-204">Mit dem- `Get-Item` Cmdlet wird der Zielpfad abgerufen, der dann an das `Move-ItemProperty` Cmdlet weitergeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="917b7-204">The `Get-Item` cmdlet gets the destination path, which is then piped to the `Move-ItemProperty` cmdlet.</span></span> <span data-ttu-id="917b7-205">Der `Move-ItemProperty` Befehl gibt den aktuellen Pfad und Namen des Registrierungs Eintrags an, der verschoben werden soll.</span><span class="sxs-lookup"><span data-stu-id="917b7-205">The `Move-ItemProperty` command specifies the current path and name of the registry entry to be moved.</span></span>

```powershell
Get-Item -Path HKLM:\Software\MyCompany\sales |
Move-ItemProperty -Path HKLM:\Software\MyCompany\design -Name product
```

<span data-ttu-id="917b7-206">Der Befehl schlägt fehl, und PowerShell zeigt die folgende Fehlermeldung an:</span><span class="sxs-lookup"><span data-stu-id="917b7-206">The command fails and PowerShell displays the following error message:</span></span>

```Output
Move-ItemProperty : The input object can't be bound to any parameters for
the command either because the command doesn't take pipeline input or the
input and its properties do not match any of the parameters that take
pipeline input.
At line:1 char:23
+ $a | Move-ItemProperty <<<<  -Path HKLM:\Software\MyCompany\design -Name p
```

<span data-ttu-id="917b7-207">Um dies zu untersuchen, verwenden Sie das- `Trace-Command` Cmdlet, um die Parameter bindungskomponente von PowerShell zu verfolgen.</span><span class="sxs-lookup"><span data-stu-id="917b7-207">To investigate, use the `Trace-Command` cmdlet to trace the parameter binding component of PowerShell.</span></span> <span data-ttu-id="917b7-208">Im folgenden Beispiel wird die Parameter Bindung nachverfolgt, während die Pipeline ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="917b7-208">The following example traces parameter binding while the pipeline is executing.</span></span> <span data-ttu-id="917b7-209">Der **pshost** -Parameter zeigt die Ablauf Verfolgungs Ergebnisse in der-Konsole an, und der **FilePath** -Parameter sendet die Ablauf Verfolgungs Ergebnisse zur `debug.txt` späteren Referenz an die Datei.</span><span class="sxs-lookup"><span data-stu-id="917b7-209">The **PSHost** parameter displays the trace results in the console and the **FilePath** parameter send the trace results to the `debug.txt` file for later reference.</span></span>

```powershell
Trace-Command -Name ParameterBinding -PSHost -FilePath debug.txt -Expression {
  Get-Item -Path HKLM:\Software\MyCompany\sales |
    Move-ItemProperty -Path HKLM:\Software\MyCompany\design -Name product
}
```

<span data-ttu-id="917b7-210">Die Ergebnisse der Ablauf Verfolgung sind langwierig, aber Sie zeigen die Werte an, die an das `Get-Item` Cmdlet gebunden werden, und dann die benannten Werte, die an das `Move-ItemProperty` Cmdlet gebunden werden.</span><span class="sxs-lookup"><span data-stu-id="917b7-210">The results of the trace are lengthy, but they show the values being bound to the `Get-Item` cmdlet and then the named values being bound to the `Move-ItemProperty` cmdlet.</span></span>

```Output
...
BIND NAMED cmd line args [`Move-ItemProperty`]
BIND arg [HKLM:\Software\MyCompany\design] to parameter [Path]
...
BIND arg [product] to parameter [Name]
...
BIND POSITIONAL cmd line args [`Move-ItemProperty`]
...
```

<span data-ttu-id="917b7-211">Schließlich wird angezeigt, dass der Versuch, den Pfad an den **Ziel** Parameter von zu binden, `Move-ItemProperty` fehlgeschlagen ist.</span><span class="sxs-lookup"><span data-stu-id="917b7-211">Finally, it shows that the attempt to bind the path to the **Destination** parameter of `Move-ItemProperty` failed.</span></span>

```Output
...
BIND PIPELINE object to parameters: [`Move-ItemProperty`]
PIPELINE object TYPE = [Microsoft.Win32.RegistryKey]
RESTORING pipeline parameter's original values
Parameter [Destination] PIPELINE INPUT ValueFromPipelineByPropertyName NO
COERCION
Parameter [Credential] PIPELINE INPUT ValueFromPipelineByPropertyName NO
COERCION
...
```

<span data-ttu-id="917b7-212">Verwenden Sie das- `Get-Help` Cmdlet, um die Attribute des **Destination** -Parameters anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="917b7-212">Use the `Get-Help` cmdlet to view the attributes of the **Destination** parameter.</span></span>

```Output
Get-Help Move-ItemProperty -Parameter Destination

-Destination <String>
    Specifies the path to the destination location.

    Required?                    true
    Position?                    1
    Default value                None
    Accept pipeline input?       True (ByPropertyName)
    Accept wildcard characters?  false
```

<span data-ttu-id="917b7-213">Die Ergebnisse zeigen an, dass das **Ziel** nur Pipeline Eingaben "by Property Name" annimmt.</span><span class="sxs-lookup"><span data-stu-id="917b7-213">The results show that **Destination** takes pipeline input only "by property name".</span></span> <span data-ttu-id="917b7-214">Daher muss das weitergeleitete Objekt über eine Eigenschaft mit dem Namen " **Destination**" verfügen.</span><span class="sxs-lookup"><span data-stu-id="917b7-214">Therefore, the piped object must have a property named **Destination**.</span></span>

<span data-ttu-id="917b7-215">Verwenden `Get-Member` Sie, um die Eigenschaften des Objekts anzuzeigen, das aus stammt `Get-Item` .</span><span class="sxs-lookup"><span data-stu-id="917b7-215">Use `Get-Member` to see the properties of the object coming from `Get-Item`.</span></span>

```powershell
Get-Item -Path HKLM:\Software\MyCompany\sales | Get-Member
```

<span data-ttu-id="917b7-216">Die Ausgabe zeigt, dass es sich bei dem Element um ein **Microsoft. Win32. RegistryKey** -Objekt handelt, das nicht über eine **Ziel** Eigenschaft verfügt.</span><span class="sxs-lookup"><span data-stu-id="917b7-216">The output shows that the item is a **Microsoft.Win32.RegistryKey** object that doesn't have a **Destination** property.</span></span> <span data-ttu-id="917b7-217">Dies erläutert, warum der Befehl fehlgeschlagen ist.</span><span class="sxs-lookup"><span data-stu-id="917b7-217">That explains why the command failed.</span></span>

<span data-ttu-id="917b7-218">Der **path** -Parameter akzeptiert Pipeline Eingaben nach Namen oder Wert.</span><span class="sxs-lookup"><span data-stu-id="917b7-218">The **Path** parameter accepts pipeline input by name or by value.</span></span>

```Output
Get-Help Move-ItemProperty -Parameter Path

-Path <String[]>
    Specifies the path to the current location of the property. Wildcard
    characters are permitted.

    Required?                    true
    Position?                    0
    Default value                None
    Accept pipeline input?       True (ByPropertyName, ByValue)
    Accept wildcard characters?  true
```

<span data-ttu-id="917b7-219">Zum Beheben des Befehls müssen wir das Ziel im `Move-ItemProperty` Cmdlet angeben und verwenden `Get-Item` , um den **Pfad** des Elements zu erhalten, das verschoben werden soll.</span><span class="sxs-lookup"><span data-stu-id="917b7-219">To fix the command, we must specify the destination in the `Move-ItemProperty` cmdlet and use `Get-Item` to get the **Path** of the item we want to move.</span></span>

<span data-ttu-id="917b7-220">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="917b7-220">For example,</span></span>

```powershell
Get-Item -Path HKLM:\Software\MyCompany\design |
Move-ItemProperty -Destination HKLM:\Software\MyCompany\sales -Name product
```

## <a name="intrinsic-line-continuation"></a><span data-ttu-id="917b7-221">Intrinsische Zeilen Fortsetzung</span><span class="sxs-lookup"><span data-stu-id="917b7-221">Intrinsic line continuation</span></span>

<span data-ttu-id="917b7-222">Wie bereits erwähnt, besteht eine Pipeline aus einer Reihe von Befehlen, die durch Pipeline Operatoren ( `|` ) verbunden sind, die in der Regel in einer einzelnen Zeile geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="917b7-222">As already discussed, a pipeline is a series of commands connected by pipeline operators (`|`), usually written on a single line.</span></span> <span data-ttu-id="917b7-223">Zur besseren Lesbarkeit ermöglicht Ihnen PowerShell jedoch, die Pipeline über mehrere Zeilen hinweg aufzuteilen.</span><span class="sxs-lookup"><span data-stu-id="917b7-223">However, for readability, PowerShell allows you to split the pipeline across multiple lines.</span></span>
<span data-ttu-id="917b7-224">Wenn ein Pipeoperator das letzte Token in der Zeile ist, fügt der PowerShell-Parser den Befehl nächste Zeile zum aktuellen Befehl ein, um die Erstellung der Pipeline fortzusetzen.</span><span class="sxs-lookup"><span data-stu-id="917b7-224">When a pipe operator is the last token on the line, the PowerShell parser joins the next line to current command to continue the construction of the pipeline.</span></span>

<span data-ttu-id="917b7-225">Beispielsweise die folgende einzeilige Pipeline:</span><span class="sxs-lookup"><span data-stu-id="917b7-225">For example, the following single-line pipeline:</span></span>

```powershell
Command-1 | Command-2 | Command-3
```

<span data-ttu-id="917b7-226">kann wie folgt geschrieben werden:</span><span class="sxs-lookup"><span data-stu-id="917b7-226">can be written as:</span></span>

```powershell
Command-1 |
  Command-2 |
    Command-3
```

<span data-ttu-id="917b7-227">Die führenden Leerzeichen in den nachfolgenden Zeilen sind nicht von Bedeutung.</span><span class="sxs-lookup"><span data-stu-id="917b7-227">The leading spaces on the subsequent lines are not significant.</span></span> <span data-ttu-id="917b7-228">Der Einzug verbessert die Lesbarkeit.</span><span class="sxs-lookup"><span data-stu-id="917b7-228">The indentation enhances readability.</span></span>

<span data-ttu-id="917b7-229">PowerShell 7 fügt Unterstützung für die Fortsetzung von Pipelines mit dem Pipeline Zeichen am Anfang einer Zeile hinzu.</span><span class="sxs-lookup"><span data-stu-id="917b7-229">PowerShell 7 adds support for continuation of pipelines with the pipeline character at the beginning of a line.</span></span> <span data-ttu-id="917b7-230">In den folgenden Beispielen wird gezeigt, wie Sie diese neue Funktion verwenden können.</span><span class="sxs-lookup"><span data-stu-id="917b7-230">The following examples show how you could use this new functionality.</span></span>

```powershell
# Wrapping with a pipe at the beginning of a line (no backtick required)
Get-Process | Where-Object CPU | Where-Object Path
    | Get-Item | Where-Object FullName -match "AppData"
    | Sort-Object FullName -Unique

# Wrapping with a pipe on a line by itself
Get-Process | Where-Object CPU | Where-Object Path
    |
    Get-Item | Where-Object FullName -match "AppData"
    |
    Sort-Object FullName -Unique
```

> [!IMPORTANT]
> <span data-ttu-id="917b7-231">Wenn Sie in der Shell interaktiv arbeiten, fügen Sie Code nur am Anfang einer Zeile mit Pipelines ein, wenn <kbd></kbd>Sie + zum Einfügen Strg<kbd>V</kbd> verwenden.</span><span class="sxs-lookup"><span data-stu-id="917b7-231">When working interactively in the shell, pasting code with pipelines at the beginning of a line only when using <kbd>Ctrl</kbd>+<kbd>V</kbd> to paste.</span></span>
> <span data-ttu-id="917b7-232">Klicken Sie mit der rechten Maustaste auf Einfügevorgänge, um die Zeilen einzeln einzufügen.</span><span class="sxs-lookup"><span data-stu-id="917b7-232">Right-click paste operations insert the lines one at a time.</span></span> <span data-ttu-id="917b7-233">Da die Zeile nicht mit einem Pipeline Zeichen endet, betrachtet PowerShell die Eingabe als abgeschlossen und führt diese Zeile wie eingegeben aus.</span><span class="sxs-lookup"><span data-stu-id="917b7-233">Since the line does not end with a pipeline character, PowerShell considers the input to be complete and executes that line as entered.</span></span>

## <a name="see-also"></a><span data-ttu-id="917b7-234">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="917b7-234">See Also</span></span>

[<span data-ttu-id="917b7-235">about_PSReadLine</span><span class="sxs-lookup"><span data-stu-id="917b7-235">about_PSReadLine</span></span>](../../PSReadLine/About/about_PSReadLine.md)

[<span data-ttu-id="917b7-236">about_Objects</span><span class="sxs-lookup"><span data-stu-id="917b7-236">about_Objects</span></span>](about_objects.md)

[<span data-ttu-id="917b7-237">about_Parameters</span><span class="sxs-lookup"><span data-stu-id="917b7-237">about_Parameters</span></span>](about_parameters.md)

[<span data-ttu-id="917b7-238">about_Command_Syntax</span><span class="sxs-lookup"><span data-stu-id="917b7-238">about_Command_Syntax</span></span>](about_command_syntax.md)

[<span data-ttu-id="917b7-239">about_ForEach</span><span class="sxs-lookup"><span data-stu-id="917b7-239">about_ForEach</span></span>](about_foreach.md)
