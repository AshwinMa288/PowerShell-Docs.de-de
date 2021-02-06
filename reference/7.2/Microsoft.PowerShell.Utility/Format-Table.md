---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 08/10/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/format-table?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Format-Table
ms.openlocfilehash: 2db0a8abe8fbd87b077e40655a06a1db45482ebc
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99603699"
---
# <span data-ttu-id="1f449-102">Format-Table</span><span class="sxs-lookup"><span data-stu-id="1f449-102">Format-Table</span></span>

## <span data-ttu-id="1f449-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="1f449-103">SYNOPSIS</span></span>
<span data-ttu-id="1f449-104">Formatiert die Ausgabe als Tabelle.</span><span class="sxs-lookup"><span data-stu-id="1f449-104">Formats the output as a table.</span></span>

## <span data-ttu-id="1f449-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="1f449-105">SYNTAX</span></span>

### <span data-ttu-id="1f449-106">Alle</span><span class="sxs-lookup"><span data-stu-id="1f449-106">All</span></span>

```
Format-Table [-AutoSize] [-RepeatHeader] [-HideTableHeaders] [-Wrap] [[-Property] <Object[]>]
 [-GroupBy <Object>] [-View <String>] [-ShowError] [-DisplayError] [-Force] [-Expand <String>]
 [-InputObject <PSObject>] [<CommonParameters>]
```

## <span data-ttu-id="1f449-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="1f449-107">DESCRIPTION</span></span>

<span data-ttu-id="1f449-108">Das- `Format-Table` Cmdlet formatiert die Ausgabe eines Befehls als Tabelle mit den ausgewählten Eigenschaften des Objekts in jeder Spalte.</span><span class="sxs-lookup"><span data-stu-id="1f449-108">The `Format-Table` cmdlet formats the output of a command as a table with the selected properties of the object in each column.</span></span> <span data-ttu-id="1f449-109">Der-Objekttyp bestimmt das Standardlayout und die Standardeigenschaften, die in den einzelnen Spalten angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="1f449-109">The object type determines the default layout and properties that are displayed in each column.</span></span> <span data-ttu-id="1f449-110">Sie können den **Property** -Parameter verwenden, um die Eigenschaften auszuwählen, die Sie anzeigen möchten.</span><span class="sxs-lookup"><span data-stu-id="1f449-110">You can use the **Property** parameter to select the properties that you want to display.</span></span>

<span data-ttu-id="1f449-111">PowerShell verwendet Standardformatierer, um zu definieren, wie Objekttypen angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="1f449-111">PowerShell uses default formatters to define how object types are displayed.</span></span> <span data-ttu-id="1f449-112">Sie können `.ps1xml` Dateien verwenden, um benutzerdefinierte Ansichten zu erstellen, die eine Ausgabe Tabelle mit angegebenen Eigenschaften anzeigen.</span><span class="sxs-lookup"><span data-stu-id="1f449-112">You can use `.ps1xml` files to create custom views that display an output table with specified properties.</span></span> <span data-ttu-id="1f449-113">Nachdem eine benutzerdefinierte Ansicht erstellt wurde, verwenden Sie den **View** -Parameter, um die Tabelle mit Ihrer benutzerdefinierten Ansicht anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="1f449-113">After a custom view is created, use the **View** parameter to display the table with your custom view.</span></span> <span data-ttu-id="1f449-114">Weitere Informationen zu Ansichten finden Sie unter [about_Format.ps1XML](../Microsoft.PowerShell.Core/About/about_Format.ps1xml.md).</span><span class="sxs-lookup"><span data-stu-id="1f449-114">For more information about views, see [about_Format.ps1xml](../Microsoft.PowerShell.Core/About/about_Format.ps1xml.md).</span></span>

<span data-ttu-id="1f449-115">Sie können eine Hash Tabelle verwenden, um einem Objekt berechnete Eigenschaften hinzuzufügen, bevor Sie Sie anzeigen und die Spaltenüberschriften in der Tabelle angeben.</span><span class="sxs-lookup"><span data-stu-id="1f449-115">You can use a hash table to add calculated properties to an object before displaying it and to specify the column headings in the table.</span></span> <span data-ttu-id="1f449-116">Um eine berechnete Eigenschaft hinzuzufügen, verwenden Sie die **Eigenschaft** oder den **GroupBy** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="1f449-116">To add a calculated property, use the **Property** or **GroupBy** parameter.</span></span> <span data-ttu-id="1f449-117">Weitere Informationen zu Hashtabellen finden Sie unter [about_Hash_Tables](../Microsoft.PowerShell.Core/About/about_Hash_Tables.md) (Informationen zu Hashtabellen).</span><span class="sxs-lookup"><span data-stu-id="1f449-117">For more information about hash tables, see [about_Hash_Tables](../Microsoft.PowerShell.Core/About/about_Hash_Tables.md).</span></span>

## <span data-ttu-id="1f449-118">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="1f449-118">EXAMPLES</span></span>

### <span data-ttu-id="1f449-119">Beispiel 1: Formatieren eines PowerShell-Hosts</span><span class="sxs-lookup"><span data-stu-id="1f449-119">Example 1: Format PowerShell host</span></span>

<span data-ttu-id="1f449-120">In diesem Beispiel werden Informationen zum Host Programm für PowerShell in einer Tabelle angezeigt.</span><span class="sxs-lookup"><span data-stu-id="1f449-120">This example displays information about the host program for PowerShell in a table.</span></span>

```powershell
Get-Host | Format-Table -AutoSize
```

<span data-ttu-id="1f449-121">Mit dem- `Get-Host` Cmdlet werden **System. Management. Automation. Internal. Host. internalhost** -Objekte abgerufen, die den Host darstellen.</span><span class="sxs-lookup"><span data-stu-id="1f449-121">The `Get-Host` cmdlet gets **System.Management.Automation.Internal.Host.InternalHost** objects that represent the host.</span></span> <span data-ttu-id="1f449-122">Die Objekte werden an die Pipeline gesendet `Format-Table` und in einer Tabelle angezeigt.</span><span class="sxs-lookup"><span data-stu-id="1f449-122">The objects are sent down the pipeline to `Format-Table` and displayed in a table.</span></span> <span data-ttu-id="1f449-123">Der **AutoSize** -Parameter passt die Spaltenbreite an, um das Abschneiden zu minimieren.</span><span class="sxs-lookup"><span data-stu-id="1f449-123">The **AutoSize** parameter adjusts the column widths to minimize truncation.</span></span>

### <span data-ttu-id="1f449-124">Beispiel 2: Formatieren von Prozessen nach BasePriority</span><span class="sxs-lookup"><span data-stu-id="1f449-124">Example 2: Format processes by BasePriority</span></span>

<span data-ttu-id="1f449-125">In diesem Beispiel werden Prozesse in Gruppen angezeigt, die dieselbe **BasePriority** -Eigenschaft aufweisen.</span><span class="sxs-lookup"><span data-stu-id="1f449-125">In this example, processes are displayed in groups that have the same **BasePriority** property.</span></span>

```powershell
Get-Process | Sort-Object -Property BasePriority | Format-Table -GroupBy BasePriority -Wrap
```

<span data-ttu-id="1f449-126">Das `Get-Process` -Cmdlet ruft Objekte ab, die jeden Prozess auf dem Computer darstellen, und sendet Sie an die Pipeline `Sort-Object` .</span><span class="sxs-lookup"><span data-stu-id="1f449-126">The `Get-Process` cmdlet gets objects that represent each process on the computer and sends them down the pipeline to `Sort-Object`.</span></span> <span data-ttu-id="1f449-127">Die Objekte werden in der Reihenfolge ihrer **BasePriority** -Eigenschaft sortiert.</span><span class="sxs-lookup"><span data-stu-id="1f449-127">The objects are sorted in the order of their **BasePriority** property.</span></span>

<span data-ttu-id="1f449-128">Die sortierten Objekte werden über die Pipeline an gesendet `Format-Table` .</span><span class="sxs-lookup"><span data-stu-id="1f449-128">The sorted objects are sent down the pipeline to `Format-Table`.</span></span> <span data-ttu-id="1f449-129">Der **GroupBy** -Parameter ordnet die Prozessdaten basierend auf dem Wert Ihrer **BasePriority** -Eigenschaft in Gruppen an.</span><span class="sxs-lookup"><span data-stu-id="1f449-129">The **GroupBy** parameter arranges the process data into groups based on their **BasePriority** property's value.</span></span> <span data-ttu-id="1f449-130">Mit dem **Wrap** -Parameter wird sichergestellt, dass keine Daten abgeschnitten werden.</span><span class="sxs-lookup"><span data-stu-id="1f449-130">The **Wrap** parameter ensures that data isn't truncated.</span></span>

### <span data-ttu-id="1f449-131">Beispiel 3: Formatieren von Prozessen nach Startdatum</span><span class="sxs-lookup"><span data-stu-id="1f449-131">Example 3: Format processes by start date</span></span>

<span data-ttu-id="1f449-132">Dieses Beispiel zeigt Informationen zu den Prozessen, die auf dem Computer ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="1f449-132">This example displays information about the processes running on the computer.</span></span> <span data-ttu-id="1f449-133">Die Objekte werden sortiert und `Format-Table` verwenden eine Ansicht, um die Objekte nach Ihrem Startdatum zu gruppieren.</span><span class="sxs-lookup"><span data-stu-id="1f449-133">The objects are sorted and `Format-Table` uses a view to group the objects by their start date.</span></span>

```powershell
Get-Process | Sort-Object StartTime | Format-Table -View StartTime
```

<span data-ttu-id="1f449-134">`Get-Process` Ruft die **System. Diagnostics. Process** -Objekte ab, die die Prozesse darstellen, die auf dem Computer ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="1f449-134">`Get-Process` gets the **System.Diagnostics.Process** objects that represent the processes running on the computer.</span></span> <span data-ttu-id="1f449-135">Die Objekte werden über die Pipeline an gesendet `Sort-Object` und basierend auf der **StartTime** -Eigenschaft sortiert.</span><span class="sxs-lookup"><span data-stu-id="1f449-135">The objects are sent down the pipeline to `Sort-Object`, and are sorted based on the **StartTime** property.</span></span>

<span data-ttu-id="1f449-136">Die sortierten Objekte werden über die Pipeline an gesendet `Format-Table` .</span><span class="sxs-lookup"><span data-stu-id="1f449-136">The sorted objects are sent down the pipeline to `Format-Table`.</span></span> <span data-ttu-id="1f449-137">Der **View** -Parameter gibt die **StartTime** -Ansicht an, die in der PowerShell- `DotNetTypes.format.ps1xml` Datei für **System. Diagnostics. Process** -Objekte definiert ist.</span><span class="sxs-lookup"><span data-stu-id="1f449-137">The **View** parameter specifies the **StartTime** view that's defined in the PowerShell `DotNetTypes.format.ps1xml` file for **System.Diagnostics.Process** objects.</span></span> <span data-ttu-id="1f449-138">Die **StartTime** -Sicht konvertiert die Startzeit der einzelnen Prozesse in ein kurzes Datum und gruppiert dann die Prozesse nach dem Startdatum.</span><span class="sxs-lookup"><span data-stu-id="1f449-138">The **StartTime** view converts each processes start time to a short date and then groups the processes by the start date.</span></span>

<span data-ttu-id="1f449-139">Die `DotNetTypes.format.ps1xml` Datei enthält eine **Prioritäts** Ansicht für Prozesse.</span><span class="sxs-lookup"><span data-stu-id="1f449-139">The `DotNetTypes.format.ps1xml` file contains a **Priority** view for processes.</span></span> <span data-ttu-id="1f449-140">Sie können eigene `format.ps1xml` Dateien mit benutzerdefinierten Ansichten erstellen.</span><span class="sxs-lookup"><span data-stu-id="1f449-140">You can create your own `format.ps1xml` files with customized views.</span></span>

### <span data-ttu-id="1f449-141">Beispiel 4: Verwenden einer benutzerdefinierten Ansicht für die Tabellenausgabe</span><span class="sxs-lookup"><span data-stu-id="1f449-141">Example 4: Use a custom view for table output</span></span>

<span data-ttu-id="1f449-142">In diesem Beispiel zeigt eine benutzerdefinierte Ansicht den Inhalt eines Verzeichnisses an.</span><span class="sxs-lookup"><span data-stu-id="1f449-142">In this example, a custom view displays a directory's contents.</span></span> <span data-ttu-id="1f449-143">Die benutzerdefinierte Ansicht fügt der Tabellenausgabe für **System. IO. directeryinfo** -und **System. IO. FileInfo** -Objekte, die von erstellt werden, die Spalte " **Spalte** " hinzu `Get-ChildItem` .</span><span class="sxs-lookup"><span data-stu-id="1f449-143">The custom view adds the **CreationTime** column to the table output for **System.IO.DirectoryInfo** and **System.IO.FileInfo** objects created by `Get-ChildItem`.</span></span>

<span data-ttu-id="1f449-144">Die benutzerdefinierte Ansicht in diesem Beispiel wurde aus der Ansicht erstellt, die im PowerShell-Quellcode definiert wurde.</span><span class="sxs-lookup"><span data-stu-id="1f449-144">The custom view in this example was created from the view defined in PowerShell source code.</span></span> <span data-ttu-id="1f449-145">Weitere Informationen zu Ansichten und zum Code, der zum Erstellen der Ansicht dieses Beispiels verwendet wird, finden Sie unter [about_Format.ps1XML](../Microsoft.PowerShell.Core/About/about_Format.ps1xml.md#sample-xml-for-a-format-table-custom-view).</span><span class="sxs-lookup"><span data-stu-id="1f449-145">For more information about views and the code used to create this example's view, see [about_Format.ps1xml](../Microsoft.PowerShell.Core/About/about_Format.ps1xml.md#sample-xml-for-a-format-table-custom-view).</span></span>

```powershell
Get-ChildItem  -Path C:\Test | Format-Table -View mygciview
```

```Output
    Directory: C:\Test

Mode                LastWriteTime              CreationTime         Length Name
----                -------------              ------------         ------ ----
d-----        11/4/2019     15:54       9/24/2019     15:54                Archives
d-----        8/27/2019     14:22       8/27/2019     14:22                Drawings
d-----       10/23/2019     09:38       2/25/2019     09:38                Files
-a----        11/7/2019     11:07       11/7/2019     11:07          11345 Alias.txt
-a----        2/27/2019     15:15       2/27/2019     15:15            258 alias_out.txt
-a----        2/27/2019     15:16       2/27/2019     15:16            258 alias_out2.txt
```

<span data-ttu-id="1f449-146">`Get-ChildItem` Ruft den Inhalt des aktuellen Verzeichnisses ab `C:\Test` .</span><span class="sxs-lookup"><span data-stu-id="1f449-146">`Get-ChildItem` gets the contents of the current directory, `C:\Test`.</span></span> <span data-ttu-id="1f449-147">Die Objekte " **System. IO. Director yinfo** " und " **System. IO. FileInfo** " werden über die Pipeline gesendet.</span><span class="sxs-lookup"><span data-stu-id="1f449-147">The **System.IO.DirectoryInfo** and **System.IO.FileInfo** objects are sent down the pipeline.</span></span>
<span data-ttu-id="1f449-148">`Format-Table` verwendet den **View** -Parameter, um die benutzerdefinierte Ansicht **mygciview** anzugeben, die die Spalte " **kreationtime** " enthält.</span><span class="sxs-lookup"><span data-stu-id="1f449-148">`Format-Table` uses the **View** parameter to specify the custom view **mygciview** that includes the **CreationTime** column.</span></span>

<span data-ttu-id="1f449-149">Die Standard `Format-Table` Ausgabe für `Get-ChildItem` enthält nicht die Spalte "up **time** ".</span><span class="sxs-lookup"><span data-stu-id="1f449-149">The default `Format-Table` output for `Get-ChildItem` doesn't include the **CreationTime** column.</span></span>

### <span data-ttu-id="1f449-150">Beispiel 5: Verwenden von Eigenschaften für die Tabellenausgabe</span><span class="sxs-lookup"><span data-stu-id="1f449-150">Example 5: Use properties for table output</span></span>

<span data-ttu-id="1f449-151">In diesem Beispiel wird der **Property** -Parameter verwendet, um alle Computerdienste in einer Tabelle mit zwei Spalten anzuzeigen, in der die Eigenschaften **Name** und **DependentServices** angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="1f449-151">This example uses the **Property** parameter to display all the computer's services in a two-column table that shows the properties **Name** and **DependentServices**.</span></span>

```powershell
Get-Service | Format-Table -Property Name, DependentServices
```

<span data-ttu-id="1f449-152">`Get-Service` Ruft alle Dienste auf dem Computer ab und sendet die **System. ServiceProcess. ServiceController** -Objekte über die Pipeline.</span><span class="sxs-lookup"><span data-stu-id="1f449-152">`Get-Service` gets all the services on the computer and sends the **System.ServiceProcess.ServiceController** objects down the pipeline.</span></span> <span data-ttu-id="1f449-153">`Format-Table` verwendet den **Property** -Parameter, um anzugeben, dass die Eigenschaften **Name** und **DependentServices** in der Tabelle angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="1f449-153">`Format-Table` uses the **Property** parameter to specify that the **Name** and **DependentServices** properties are displayed in the table.</span></span>

<span data-ttu-id="1f449-154">**Name** und **DependentServices** sind zwei der Eigenschaften des Objekt Typs.</span><span class="sxs-lookup"><span data-stu-id="1f449-154">**Name** and **DependentServices** are two of the object type's properties.</span></span> <span data-ttu-id="1f449-155">Um alle Eigenschaften anzuzeigen: `Get-Service | Get-Member -MemberType Properties` .</span><span class="sxs-lookup"><span data-stu-id="1f449-155">To view all the properties: `Get-Service | Get-Member -MemberType Properties`.</span></span>

### <span data-ttu-id="1f449-156">Beispiel 6: Formatieren eines Prozesses und Berechnen der Lauf Zeit</span><span class="sxs-lookup"><span data-stu-id="1f449-156">Example 6: Format a process and calculate its running time</span></span>

<span data-ttu-id="1f449-157">In diesem Beispiel wird eine Tabelle mit dem Prozessnamen und der Gesamtlaufzeit für die **Editor** -Prozesse des lokalen Computers angezeigt.</span><span class="sxs-lookup"><span data-stu-id="1f449-157">This example displays a table with the process name and total running time for the local computer's **notepad** processes.</span></span> <span data-ttu-id="1f449-158">Die Gesamtausführungszeit wird durch Subtrahieren der Startzeit der einzelnen Prozesses von der aktuellen Zeit berechnet.</span><span class="sxs-lookup"><span data-stu-id="1f449-158">The total running time is calculated by subtracting the start time of each process from the current time.</span></span>

```powershell
Get-Process notepad |
  Format-Table ProcessName, @{Label="TotalRunningTime"; Expression={(Get-Date) - $_.StartTime}}
```

```Output
ProcessName TotalRunningTime
----------- ----------------
notepad     03:20:00.2751767
notepad     00:00:16.7710520
```

<span data-ttu-id="1f449-159">`Get-Process` Ruft alle **Editor** -Prozesse des lokalen Computers ab und sendet die Objekte in der Pipeline.</span><span class="sxs-lookup"><span data-stu-id="1f449-159">`Get-Process` gets all the local computer's **notepad** processes and sends the objects down the pipeline.</span></span> <span data-ttu-id="1f449-160">`Format-Table` zeigt eine Tabelle mit zwei Spalten an: **ProcessName**, eine `Get-Process` Eigenschaft und **totalrunningtime**, eine berechnete Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="1f449-160">`Format-Table` displays a table with two columns: **ProcessName**, a `Get-Process` property, and **TotalRunningTime**, a calculated property.</span></span>

<span data-ttu-id="1f449-161">Die **totalrunningtime** -Eigenschaft wird durch eine Hash Tabelle mit zwei Schlüsseln, **Bezeichnung** und **Ausdruck**, angegeben.</span><span class="sxs-lookup"><span data-stu-id="1f449-161">The **TotalRunningTime** property is specified by a hash table with two keys, **Label** and **Expression**.</span></span> <span data-ttu-id="1f449-162">Die **Bezeichnung Key gibt den Namen** der Eigenschaft an.</span><span class="sxs-lookup"><span data-stu-id="1f449-162">The **Label** key specifies the property name.</span></span> <span data-ttu-id="1f449-163">Der **Ausdrucks** Schlüssel gibt die Berechnung an.</span><span class="sxs-lookup"><span data-stu-id="1f449-163">The **Expression** key specifies the calculation.</span></span> <span data-ttu-id="1f449-164">Der Ausdruck ruft die **StartTime** -Eigenschaft jedes Prozess Objekts ab und subtrahiert Sie vom Ergebnis eines- `Get-Date` Befehls, der das aktuelle Datum und die Uhrzeit abruft.</span><span class="sxs-lookup"><span data-stu-id="1f449-164">The expression gets the **StartTime** property of each process object and subtracts it from the result of a `Get-Date` command, which gets the current date and time.</span></span>

### <span data-ttu-id="1f449-165">Beispiel 7: Formatieren von Notepad-Prozessen</span><span class="sxs-lookup"><span data-stu-id="1f449-165">Example 7: Format Notepad processes</span></span>

<span data-ttu-id="1f449-166">In diesem Beispiel wird verwendet `Get-CimInstance` , um die Lauf Zeit für alle **Editor** -Prozesse auf dem lokalen Computer zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="1f449-166">This example uses `Get-CimInstance` to get the running time for all **notepad** processes on the local computer.</span></span> <span data-ttu-id="1f449-167">Sie können `Get-CimInstance` mit dem **Computername** -Parameter verwenden, um Informationen von Remote Computern zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="1f449-167">You can use `Get-CimInstance` with the **ComputerName** parameter to get information from remote computers.</span></span>

```powershell
$Processes = Get-CimInstance -Class win32_process -Filter "name='notepad.exe'"
$Processes | Format-Table ProcessName, @{ Label = "Total Running Time"; Expression={(Get-Date) - $_.CreationDate}}
```

```Output
ProcessName Total Running Time
----------- ------------------
notepad.exe 03:39:39.6260693
notepad.exe 00:19:56.1376922
```

<span data-ttu-id="1f449-168">`Get-CimInstance` Ruft Instanzen der WMI- **Win32_Process** Klasse ab, die alle Prozesse des lokalen Computers mit dem Namen **notepad.exe** beschreibt.</span><span class="sxs-lookup"><span data-stu-id="1f449-168">`Get-CimInstance` gets instances of the WMI **Win32_Process** class that describes all the local computer's processes named **notepad.exe**.</span></span> <span data-ttu-id="1f449-169">Die Prozess Objekte werden in der `$Processes` Variablen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="1f449-169">The process objects are stored in the `$Processes` variable.</span></span>

<span data-ttu-id="1f449-170">Die Prozess Objekte in der `$Processes` Variablen werden über die Pipeline an gesendet `Format-Table` , wodurch die **ProcessName** -Eigenschaft und eine neue berechnete Eigenschaft, **Gesamtlaufzeit**, angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="1f449-170">The process objects in the `$Processes` variable are sent down the pipeline to `Format-Table`, which displays the **ProcessName** property and a new calculated property, **Total Running Time**.</span></span>

<span data-ttu-id="1f449-171">Der Befehl weist den Namen der neuen berechneten Eigenschaft ( **gesamte Lauf Zeit**) dem Bezeichnungs **Schlüssel zu** .</span><span class="sxs-lookup"><span data-stu-id="1f449-171">The command assigns the name of the new calculated property, **Total Running Time**, to the **Label** key.</span></span> <span data-ttu-id="1f449-172">Der Skriptblock des **Ausdrucks** Schlüssels berechnet, wie lange der Prozess ausgeführt wurde, indem er das Erstellungsdatum des Prozesses vom aktuellen Datum subtrahieren konnte.</span><span class="sxs-lookup"><span data-stu-id="1f449-172">The **Expression** key's script block calculates how long the process has been running by subtracting the processes creation date from the current date.</span></span> <span data-ttu-id="1f449-173">Das- `Get-Date` Cmdlet ruft das aktuelle Datum ab.</span><span class="sxs-lookup"><span data-stu-id="1f449-173">The `Get-Date` cmdlet gets the current date.</span></span> <span data-ttu-id="1f449-174">Das Erstellungsdatum wird vom aktuellen Datum subtrahiert.</span><span class="sxs-lookup"><span data-stu-id="1f449-174">The creation date is subtracted from the current date.</span></span> <span data-ttu-id="1f449-175">Das Ergebnis ist der Wert der **gesamten Laufzeit**.</span><span class="sxs-lookup"><span data-stu-id="1f449-175">The result is the value of **Total Running Time**.</span></span>

### <span data-ttu-id="1f449-176">Beispiel 8: Problembehandlung bei Format Fehlern</span><span class="sxs-lookup"><span data-stu-id="1f449-176">Example 8: Troubleshooting format errors</span></span>

<span data-ttu-id="1f449-177">Die folgenden Beispiele zeigen die Ergebnisse des Hinzufügens der **displayerror** -oder **ShowError** -Parameter mit einem Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="1f449-177">The following examples show the results of adding the **DisplayError** or **ShowError** parameters with an expression.</span></span>

```powershell
Get-Date | Format-Table DayOfWeek,{ $_ / $null } -DisplayError
```

```Output
DayOfWeek  $_ / $null
--------- ------------
Wednesday #ERR
```

```powershell
Get-Date | Format-Table DayOfWeek,{ $_ / $null } -ShowError
```

```Output
DayOfWeek  $_ / $null
--------- ------------
Wednesday

InvalidArgument: Failed to evaluate expression " $_ / $null ".
```

## <span data-ttu-id="1f449-178">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="1f449-178">PARAMETERS</span></span>

### <span data-ttu-id="1f449-179">-AutoSize</span><span class="sxs-lookup"><span data-stu-id="1f449-179">-AutoSize</span></span>

<span data-ttu-id="1f449-180">Gibt an, dass das Cmdlet die Spaltengröße und die Anzahl der Spalten basierend auf der Breite der Daten anpasst.</span><span class="sxs-lookup"><span data-stu-id="1f449-180">Indicates that the cmdlet adjusts the column size and number of columns based on the width of the data.</span></span> <span data-ttu-id="1f449-181">Standardmäßig werden die Spaltengröße und die Anzahl von der Ansicht bestimmt.</span><span class="sxs-lookup"><span data-stu-id="1f449-181">By default, the column size and number are determined by the view.</span></span>

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

### <span data-ttu-id="1f449-182">-Display Error</span><span class="sxs-lookup"><span data-stu-id="1f449-182">-DisplayError</span></span>

<span data-ttu-id="1f449-183">Gibt an, dass das Cmdlet Fehler in der Befehlszeile anzeigt.</span><span class="sxs-lookup"><span data-stu-id="1f449-183">Indicates that the cmdlet displays errors on the command line.</span></span> <span data-ttu-id="1f449-184">Dieser Parameter kann als Hilfe beim Debuggen verwendet werden, wenn Sie Ausdrücke in einem Befehl formatieren `Format-Table` und Probleme beheben müssen.</span><span class="sxs-lookup"><span data-stu-id="1f449-184">This parameter can be used as a debugging aid when you're formatting expressions in a `Format-Table` command and need to troubleshoot the expressions.</span></span>

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

### <span data-ttu-id="1f449-185">-Erweitern</span><span class="sxs-lookup"><span data-stu-id="1f449-185">-Expand</span></span>

<span data-ttu-id="1f449-186">Gibt das Format des Auflistungs Objekts und die Objekte in der Auflistung an.</span><span class="sxs-lookup"><span data-stu-id="1f449-186">Specifies the format of the collection object and the objects in the collection.</span></span> <span data-ttu-id="1f449-187">Dieser Parameter dient zum Formatieren von Objekten, die die [ICollection](/dotnet/api/system.collections.icollection) ([System. Collections](/dotnet/api/system.collections))-Schnittstelle unterstützen.</span><span class="sxs-lookup"><span data-stu-id="1f449-187">This parameter is designed to format objects that support the [ICollection](/dotnet/api/system.collections.icollection) ([System.Collections](/dotnet/api/system.collections)) interface.</span></span> <span data-ttu-id="1f449-188">Der Standardwert ist " **enumonly**".</span><span class="sxs-lookup"><span data-stu-id="1f449-188">The default value is **EnumOnly**.</span></span>
<span data-ttu-id="1f449-189">Die zulässigen Werte für diesen Parameter lauten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="1f449-189">The acceptable values for this parameter are as follows:</span></span>

- <span data-ttu-id="1f449-190">**Enumonly**: zeigt die Eigenschaften der Objekte in der Auflistung an.</span><span class="sxs-lookup"><span data-stu-id="1f449-190">**EnumOnly**: Displays the properties of the objects in the collection.</span></span>
- <span data-ttu-id="1f449-191">**Coreonly**: zeigt die Eigenschaften des Auflistungs Objekts an.</span><span class="sxs-lookup"><span data-stu-id="1f449-191">**CoreOnly**: Displays the properties of the collection object.</span></span>
- <span data-ttu-id="1f449-192">**Beides**: zeigt die Eigenschaften des Auflistungs Objekts und die Eigenschaften von Objekten in der Auflistung an.</span><span class="sxs-lookup"><span data-stu-id="1f449-192">**Both**: Displays the properties of the collection object and the properties of objects in the collection.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: CoreOnly, EnumOnly, Both

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="1f449-193">-Force</span><span class="sxs-lookup"><span data-stu-id="1f449-193">-Force</span></span>

<span data-ttu-id="1f449-194">Gibt an, dass das Cmdlet das Cmdlet anweist, alle Fehlerinformationen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="1f449-194">Indicates that the cmdlet directs the cmdlet to display all the error information.</span></span> <span data-ttu-id="1f449-195">Verwenden Sie mit dem **Display Error** -Parameter oder **ShowError** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="1f449-195">Use with the **DisplayError** or **ShowError** parameter.</span></span> <span data-ttu-id="1f449-196">Wenn ein Fehlerobjekt in die Fehler- oder Anzeigedatenströme geschrieben wird, werden standardmäßig nur einige der Fehlerinformationen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="1f449-196">By default, when an error object is written to the error or display streams, only some of the error information is displayed.</span></span>

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

### <span data-ttu-id="1f449-197">-GroupBy</span><span class="sxs-lookup"><span data-stu-id="1f449-197">-GroupBy</span></span>

<span data-ttu-id="1f449-198">Gibt die sortierte Ausgabe basierend auf einem Eigenschafts Wert in separaten Tabellen an.</span><span class="sxs-lookup"><span data-stu-id="1f449-198">Specifies sorted output in separate tables based on a property value.</span></span> <span data-ttu-id="1f449-199">Sie können z. b. **GroupBy** verwenden, um Dienste basierend auf Ihrem Status in separaten Tabellen aufzulisten.</span><span class="sxs-lookup"><span data-stu-id="1f449-199">For example, you can use **GroupBy** to list services in separate tables based on their status.</span></span>

<span data-ttu-id="1f449-200">Geben Sie einen Ausdruck oder eine Eigenschaft ein.</span><span class="sxs-lookup"><span data-stu-id="1f449-200">Enter an expression or a property.</span></span> <span data-ttu-id="1f449-201">Der **GroupBy** -Parameter erwartet, dass die Objekte sortiert werden.</span><span class="sxs-lookup"><span data-stu-id="1f449-201">The **GroupBy** parameter expects that the objects are sorted.</span></span>
<span data-ttu-id="1f449-202">Verwenden Sie das- `Sort-Object` Cmdlet `Format-Table` , bevor Sie zum Gruppieren der Objekte verwenden.</span><span class="sxs-lookup"><span data-stu-id="1f449-202">Use the `Sort-Object` cmdlet before using `Format-Table` to group the objects.</span></span>

<span data-ttu-id="1f449-203">Der Wert des **GroupBy** -Parameters kann eine neue berechnete Eigenschaft sein.</span><span class="sxs-lookup"><span data-stu-id="1f449-203">The value of the **GroupBy** parameter can be a new calculated property.</span></span> <span data-ttu-id="1f449-204">Die berechnete Eigenschaft kann ein Skriptblock oder eine Hash Tabelle sein.</span><span class="sxs-lookup"><span data-stu-id="1f449-204">The calculated property can be a script block or a hash table.</span></span> <span data-ttu-id="1f449-205">Gültige Schlüssel-Wert-Paare sind:</span><span class="sxs-lookup"><span data-stu-id="1f449-205">Valid key-value pairs are:</span></span>

- <span data-ttu-id="1f449-206">Name (oder Bezeichnung)- `<string>`</span><span class="sxs-lookup"><span data-stu-id="1f449-206">Name (or Label) - `<string>`</span></span>
- <span data-ttu-id="1f449-207">Ausdruck `<string>` oder `<script block>`</span><span class="sxs-lookup"><span data-stu-id="1f449-207">Expression - `<string>` or `<script block>`</span></span>
- <span data-ttu-id="1f449-208">FormatString `<string>`</span><span class="sxs-lookup"><span data-stu-id="1f449-208">FormatString - `<string>`</span></span>

<span data-ttu-id="1f449-209">Weitere Informationen finden Sie unter [about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md).</span><span class="sxs-lookup"><span data-stu-id="1f449-209">For more information, see [about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md).</span></span>

```yaml
Type: System.Object
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="1f449-210">-Hidetableheaders</span><span class="sxs-lookup"><span data-stu-id="1f449-210">-HideTableHeaders</span></span>

<span data-ttu-id="1f449-211">Lässt die Spaltenüberschriften in der Tabelle aus.</span><span class="sxs-lookup"><span data-stu-id="1f449-211">Omits the column headings from the table.</span></span>

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

### <span data-ttu-id="1f449-212">-InputObject</span><span class="sxs-lookup"><span data-stu-id="1f449-212">-InputObject</span></span>

<span data-ttu-id="1f449-213">Gibt die zu formatierenden Objekte an.</span><span class="sxs-lookup"><span data-stu-id="1f449-213">Specifies the objects to format.</span></span> <span data-ttu-id="1f449-214">Geben Sie eine Variable ein, die die Objekte enthält, oder geben Sie einen Befehl oder einen Ausdruck ein, mit dem die Objekte abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="1f449-214">Enter a variable that contains the objects, or type a command or expression that gets the objects.</span></span>

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

### <span data-ttu-id="1f449-215">-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="1f449-215">-Property</span></span>

<span data-ttu-id="1f449-216">Gibt die in der Anzeige angezeigten Objekteigenschaften und die Reihenfolge an, in der sie angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="1f449-216">Specifies the object properties that appear in the display and the order in which they appear.</span></span> <span data-ttu-id="1f449-217">Geben Sie einen oder mehrere Eigenschaftsnamen ein, die durch Kommas getrennt sind, oder verwenden Sie eine Hash Tabelle, um eine berechnete Eigenschaft anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="1f449-217">Type one or more property names, separated by commas, or use a hash table to display a calculated property.</span></span> <span data-ttu-id="1f449-218">Platzhalter sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="1f449-218">Wildcards are permitted.</span></span>

<span data-ttu-id="1f449-219">Wenn Sie diesen Parameter weglassen, hängen die Eigenschaften, die in der Anzeige angezeigt werden, von den Eigenschaften des ersten Objekts ab.</span><span class="sxs-lookup"><span data-stu-id="1f449-219">If you omit this parameter, the properties that appear in the display depend on the first object's properties.</span></span> <span data-ttu-id="1f449-220">Wenn das erste Objekt beispielsweise **PropertyA** und **propertyb** aufweist, die nachfolgenden Objekte jedoch **PropertyA**, **propertyb** und **propertyc** aufweisen, werden nur die **PropertyA** -und **propertyb** -Header angezeigt.</span><span class="sxs-lookup"><span data-stu-id="1f449-220">For example, if the first object has **PropertyA** and **PropertyB** but subsequent objects have **PropertyA**, **PropertyB**, and **PropertyC**, then only the **PropertyA** and **PropertyB** headers will display.</span></span>

<span data-ttu-id="1f449-221">Der **Property** -Parameter ist optional.</span><span class="sxs-lookup"><span data-stu-id="1f449-221">The **Property** parameter is optional.</span></span> <span data-ttu-id="1f449-222">Sie können die Parameter " **Property** " und " **View** " nicht im selben Befehl verwenden.</span><span class="sxs-lookup"><span data-stu-id="1f449-222">You can't use the **Property** and **View** parameters in the same command.</span></span>

<span data-ttu-id="1f449-223">Der Wert des **Property** -Parameters kann eine neue berechnete Eigenschaft sein.</span><span class="sxs-lookup"><span data-stu-id="1f449-223">The value of the **Property** parameter can be a new calculated property.</span></span> <span data-ttu-id="1f449-224">Die berechnete Eigenschaft kann ein Skriptblock oder eine Hash Tabelle sein.</span><span class="sxs-lookup"><span data-stu-id="1f449-224">The calculated property can be a script block or a hash table.</span></span> <span data-ttu-id="1f449-225">Gültige Schlüssel-Wert-Paare sind:</span><span class="sxs-lookup"><span data-stu-id="1f449-225">Valid key-value pairs are:</span></span>

- <span data-ttu-id="1f449-226">Name (oder Bezeichnung) `<string>`</span><span class="sxs-lookup"><span data-stu-id="1f449-226">Name (or Label) `<string>`</span></span>
- <span data-ttu-id="1f449-227">Ausdruck `<string>` oder `<script block>`</span><span class="sxs-lookup"><span data-stu-id="1f449-227">Expression - `<string>` or `<script block>`</span></span>
- <span data-ttu-id="1f449-228">FormatString `<string>`</span><span class="sxs-lookup"><span data-stu-id="1f449-228">FormatString - `<string>`</span></span>
- <span data-ttu-id="1f449-229">Width- `<int32>` -muss größer sein als `0`</span><span class="sxs-lookup"><span data-stu-id="1f449-229">Width - `<int32>` - must be greater than `0`</span></span>
- <span data-ttu-id="1f449-230">Der Ausrichtungs Wert kann `Left` , `Center` oder sein. `Right`</span><span class="sxs-lookup"><span data-stu-id="1f449-230">Alignment - value can be `Left`, `Center`, or `Right`</span></span>

<span data-ttu-id="1f449-231">Weitere Informationen finden Sie unter [about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md).</span><span class="sxs-lookup"><span data-stu-id="1f449-231">For more information, see [about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md).</span></span>

```yaml
Type: System.Object[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="1f449-232">-Repeatheiader</span><span class="sxs-lookup"><span data-stu-id="1f449-232">-RepeatHeader</span></span>

<span data-ttu-id="1f449-233">Wiederholt, wenn der Header einer Tabelle nach jedem Vollbild angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="1f449-233">Repeats displaying the header of a table after every screen full.</span></span> <span data-ttu-id="1f449-234">Der wiederholte Header ist nützlich, wenn die Ausgabe an einen Pager wie oder weitergeleitet wird, z `less` `more` . b. oder mit einer Bildschirm Sprachausgabe.</span><span class="sxs-lookup"><span data-stu-id="1f449-234">The repeated header is useful when the output is piped to a pager such as `less` or `more` or paging with a screen reader.</span></span>

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

### <span data-ttu-id="1f449-235">-ShowError</span><span class="sxs-lookup"><span data-stu-id="1f449-235">-ShowError</span></span>

<span data-ttu-id="1f449-236">Dieser Parameter sendet Fehler über die Pipeline.</span><span class="sxs-lookup"><span data-stu-id="1f449-236">This parameter sends errors through the pipeline.</span></span> <span data-ttu-id="1f449-237">Dieser Parameter kann als Hilfe beim Debuggen verwendet werden, wenn Sie Ausdrücke in einem Befehl formatieren `Format-Table` und Probleme beheben müssen.</span><span class="sxs-lookup"><span data-stu-id="1f449-237">This parameter can be used as a debugging aid when you're formatting expressions in a `Format-Table` command and need to troubleshoot the expressions.</span></span>

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

### <span data-ttu-id="1f449-238">-Ansicht</span><span class="sxs-lookup"><span data-stu-id="1f449-238">-View</span></span>

<span data-ttu-id="1f449-239">Ab PowerShell 6 werden die Standardansichten im PowerShell-Quellcode definiert `C#` .</span><span class="sxs-lookup"><span data-stu-id="1f449-239">Beginning in PowerShell 6, the default views are defined in PowerShell `C#` source code.</span></span> <span data-ttu-id="1f449-240">Die `*.format.ps1xml` Dateien aus PowerShell 5,1 und früheren Versionen sind in PowerShell 6 und höheren Versionen nicht vorhanden.</span><span class="sxs-lookup"><span data-stu-id="1f449-240">The `*.format.ps1xml` files from PowerShell 5.1 and earlier versions don't exist in PowerShell 6 and later versions.</span></span>

<span data-ttu-id="1f449-241">Mit dem **View** -Parameter können Sie ein alternatives Format oder eine benutzerdefinierte Ansicht für die Tabelle angeben.</span><span class="sxs-lookup"><span data-stu-id="1f449-241">The **View** parameter lets you specify an alternate format or custom view for the table.</span></span> <span data-ttu-id="1f449-242">Sie können die PowerShell-Standard Sichten verwenden oder benutzerdefinierte Ansichten erstellen.</span><span class="sxs-lookup"><span data-stu-id="1f449-242">You can use the default PowerShell views or create custom views.</span></span> <span data-ttu-id="1f449-243">Weitere Informationen zum Erstellen einer benutzerdefinierten Ansicht finden Sie unter [about_Format.ps1XML](../Microsoft.PowerShell.Core/About/about_Format.ps1xml.md).</span><span class="sxs-lookup"><span data-stu-id="1f449-243">For more information about how to create a custom view, see [about_Format.ps1xml](../Microsoft.PowerShell.Core/About/about_Format.ps1xml.md).</span></span>

<span data-ttu-id="1f449-244">Die Alternative und die benutzerdefinierten Ansichten für den **View** -Parameter müssen das Tabellenformat verwenden, andernfalls `Format-Table` schlägt fehl.</span><span class="sxs-lookup"><span data-stu-id="1f449-244">The alternate and custom views for the **View** parameter must use the table format, otherwise, `Format-Table` fails.</span></span> <span data-ttu-id="1f449-245">Wenn die Alternative Ansicht eine Liste ist, verwenden Sie das- `Format-List` Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="1f449-245">If the alternate view is a list, use the `Format-List` cmdlet.</span></span> <span data-ttu-id="1f449-246">Wenn die Alternative Ansicht weder eine Liste noch eine Tabelle ist, verwenden Sie das- `Format-Custom` Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="1f449-246">If the alternate view isn't a list or a table, use the `Format-Custom` cmdlet.</span></span>

<span data-ttu-id="1f449-247">Sie können die Parameter " **Property** " und " **View** " nicht im selben Befehl verwenden.</span><span class="sxs-lookup"><span data-stu-id="1f449-247">You can't use the **Property** and **View** parameters in the same command.</span></span>

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

### <span data-ttu-id="1f449-248">-Wrap</span><span class="sxs-lookup"><span data-stu-id="1f449-248">-Wrap</span></span>

<span data-ttu-id="1f449-249">Zeigt Text an, der die Spaltenbreite in der nächsten Zeile überschreitet.</span><span class="sxs-lookup"><span data-stu-id="1f449-249">Displays text that exceeds the column width on the next line.</span></span> <span data-ttu-id="1f449-250">Standardmäßig wird Text, der die Spaltenbreite überschreitet, abgeschnitten.</span><span class="sxs-lookup"><span data-stu-id="1f449-250">By default, text that exceeds the column width is truncated.</span></span>

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

### <span data-ttu-id="1f449-251">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="1f449-251">CommonParameters</span></span>

<span data-ttu-id="1f449-252">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="1f449-252">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="1f449-253">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="1f449-253">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="1f449-254">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="1f449-254">INPUTS</span></span>

### <span data-ttu-id="1f449-255">System. Management. Automation. psobject</span><span class="sxs-lookup"><span data-stu-id="1f449-255">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="1f449-256">Sie können jedes beliebige Objekt über die Pipeline an senden `Format-Table` .</span><span class="sxs-lookup"><span data-stu-id="1f449-256">You can send any object down the pipeline to `Format-Table`.</span></span>

## <span data-ttu-id="1f449-257">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="1f449-257">OUTPUTS</span></span>

### <span data-ttu-id="1f449-258">Microsoft. PowerShell. Commands. Internal. Format</span><span class="sxs-lookup"><span data-stu-id="1f449-258">Microsoft.PowerShell.Commands.Internal.Format</span></span>

<span data-ttu-id="1f449-259">`Format-Table` gibt Format Objekte zurück, die die Tabelle darstellen.</span><span class="sxs-lookup"><span data-stu-id="1f449-259">`Format-Table` returns format objects that represent the table.</span></span>

## <span data-ttu-id="1f449-260">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="1f449-260">NOTES</span></span>

## <span data-ttu-id="1f449-261">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="1f449-261">RELATED LINKS</span></span>

[<span data-ttu-id="1f449-262">about_Calculated_Properties</span><span class="sxs-lookup"><span data-stu-id="1f449-262">about_Calculated_Properties</span></span>](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md)

[<span data-ttu-id="1f449-263">about_Format.ps1xml</span><span class="sxs-lookup"><span data-stu-id="1f449-263">about_Format.ps1xml</span></span>](../Microsoft.PowerShell.Core/About/about_Format.ps1xml.md)

[<span data-ttu-id="1f449-264">about_Hash_Tables</span><span class="sxs-lookup"><span data-stu-id="1f449-264">about_Hash_Tables</span></span>](../Microsoft.PowerShell.Core/About/about_Hash_Tables.md)

[<span data-ttu-id="1f449-265">Export-FormatData</span><span class="sxs-lookup"><span data-stu-id="1f449-265">Export-FormatData</span></span>](Export-FormatData.md)

[<span data-ttu-id="1f449-266">Format-Custom</span><span class="sxs-lookup"><span data-stu-id="1f449-266">Format-Custom</span></span>](Format-Custom.md)

[<span data-ttu-id="1f449-267">Format-Hex</span><span class="sxs-lookup"><span data-stu-id="1f449-267">Format-Hex</span></span>](Format-Hex.md)

[<span data-ttu-id="1f449-268">Format-List</span><span class="sxs-lookup"><span data-stu-id="1f449-268">Format-List</span></span>](Format-List.md)

[<span data-ttu-id="1f449-269">Format-Wide</span><span class="sxs-lookup"><span data-stu-id="1f449-269">Format-Wide</span></span>](Format-Wide.md)

[<span data-ttu-id="1f449-270">Get-FormatData</span><span class="sxs-lookup"><span data-stu-id="1f449-270">Get-FormatData</span></span>](Get-FormatData.md)

[<span data-ttu-id="1f449-271">Get-Member</span><span class="sxs-lookup"><span data-stu-id="1f449-271">Get-Member</span></span>](Get-Member.md)

[<span data-ttu-id="1f449-272">Get-CimInstance</span><span class="sxs-lookup"><span data-stu-id="1f449-272">Get-CimInstance</span></span>](../CimCmdlets/Get-CimInstance.md)

[<span data-ttu-id="1f449-273">Update-FormatData</span><span class="sxs-lookup"><span data-stu-id="1f449-273">Update-FormatData</span></span>](Update-FormatData.md)