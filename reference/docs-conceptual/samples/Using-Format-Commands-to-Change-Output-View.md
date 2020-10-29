---
ms.date: 11/22/2019
keywords: powershell,cmdlet
title: Verwenden von „Format“-Befehlen zum Ändern der Ausgabeanzeige
description: PowerShell verfügt über ein erweiterbares Formatierungssystem, das Ihnen die Darstellung von Ausgaben in Listen, Tabellen oder benutzerdefinierten Layouts ermöglicht.
ms.openlocfilehash: ebb285a19c7fe1bc80608385f9e2842469e95817
ms.sourcegitcommit: 9080316e3ca4f11d83067b41351531672b667b7a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2020
ms.locfileid: "92500945"
---
# <a name="using-format-commands-to-change-output-view"></a><span data-ttu-id="b2afe-104">Verwenden von „Format“-Befehlen zum Ändern der Ausgabeanzeige</span><span class="sxs-lookup"><span data-stu-id="b2afe-104">Using Format Commands to Change Output View</span></span>

<span data-ttu-id="b2afe-105">PowerShell umfasst eine Reihe von Cmdlets, mit denen Sie steuern können, wie Eigenschaften für bestimmte Objekte angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="b2afe-105">PowerShell has a set of cmdlets that allow you to control how properties are displayed for particular objects.</span></span> <span data-ttu-id="b2afe-106">Der Name jedes dieser Cmdlets beginnt mit dem Verb `Format`.</span><span class="sxs-lookup"><span data-stu-id="b2afe-106">The names of all the cmdlets begin with the verb `Format`.</span></span> <span data-ttu-id="b2afe-107">Mit diesen können Sie auswählen, welche Eigenschaften angezeigt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="b2afe-107">They let you select which properties you want to show.</span></span>

```powershell
Get-Command -Verb Format -Module Microsoft.PowerShell.Utility
```

```Output
CommandType     Name               Version    Source
-----------     ----               -------    ------
Cmdlet          Format-Custom      6.1.0.0    Microsoft.PowerShell.Utility
Cmdlet          Format-Hex         6.1.0.0    Microsoft.PowerShell.Utility
Cmdlet          Format-List        6.1.0.0    Microsoft.PowerShell.Utility
Cmdlet          Format-Table       6.1.0.0    Microsoft.PowerShell.Utility
Cmdlet          Format-Wide        6.1.0.0    Microsoft.PowerShell.Utility
```

<span data-ttu-id="b2afe-108">In diesem Artikel werden die Cmdlets `Format-Wide`, `Format-List` und `Format-Table` näher erläutert.</span><span class="sxs-lookup"><span data-stu-id="b2afe-108">This article describes the `Format-Wide`, `Format-List`, and `Format-Table` cmdlets.</span></span>

<span data-ttu-id="b2afe-109">Jeder Objekttyp in PowerShell besitzt Standardeigenschaften, die verwendet werden, wenn Sie nicht festlegen, welche Eigenschaften angezeigt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="b2afe-109">Each object type in PowerShell has default properties that are used when you don't specify which properties to display.</span></span> <span data-ttu-id="b2afe-110">Für jedes Cmdlet wird außerdem derselbe **Property-Parameter** verwendet, um anzugeben, welche Eigenschaften angezeigt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="b2afe-110">Each cmdlet also uses the same **Property** parameter to specify which properties you want to display.</span></span> <span data-ttu-id="b2afe-111">Weil `Format-Wide` nur eine einzelne Eigenschaft anzeigt, übernimmt deren **Property-Parameter** nur einen einzelnen Wert, wogegen die Property-Parameter von `Format-List` und `Format-Table` eine Liste von Eigenschaftsnamen akzeptieren.</span><span class="sxs-lookup"><span data-stu-id="b2afe-111">Because `Format-Wide` only shows a single property, its **Property** parameter only takes a single value, but the property parameters of `Format-List` and `Format-Table` accept a list of property names.</span></span>

<span data-ttu-id="b2afe-112">In diesem Beispiel gibt die Standardausgabe des Cmdlets `Get-Process` an, dass zwei Instanzen von Internet Explorer ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="b2afe-112">In this example, the default output of `Get-Process` cmdlet shows that we have two instances of Internet Explorer running.</span></span>

```powershell
Get-Process -Name iexplore
```

<span data-ttu-id="b2afe-113">Das Standardformat für **Prozessobjekte** zeigt die folgenden Eigenschaften an:</span><span class="sxs-lookup"><span data-stu-id="b2afe-113">The default format for **Process** objects displays the properties shown here:</span></span>

```Output
 NPM(K)    PM(M)      WS(M)     CPU(s)      Id  SI ProcessName
 ------    -----      -----     ------      --  -- -----------
     32    25.52      10.25      13.11   12808   1 iexplore
     52    11.46      26.46       3.55   21748   1 iexplore
```

## <a name="using-format-wide-for-single-item-output"></a><span data-ttu-id="b2afe-114">Verwenden von „Format-Wide“ für die Ausgabe eines einzelnen Elements</span><span class="sxs-lookup"><span data-stu-id="b2afe-114">Using Format-Wide for Single-Item Output</span></span>

<span data-ttu-id="b2afe-115">Das Cmdlet `Format-Wide` zeigt standardmäßig nur die Standardeigenschaft eines Objekts an.</span><span class="sxs-lookup"><span data-stu-id="b2afe-115">The `Format-Wide` cmdlet, by default, displays only the default property of an object.</span></span> <span data-ttu-id="b2afe-116">Die Informationen, die zu dem jeweiligen Objekt gehören, werden in einer einzelnen Spalte angezeigt:</span><span class="sxs-lookup"><span data-stu-id="b2afe-116">The information associated with each object is displayed in a single column:</span></span>

```powershell
Get-Command -Verb Format | Format-Wide
```

```Output
Format-Custom          Format-Hex
Format-List            Format-Table
Format-Wide
```

<span data-ttu-id="b2afe-117">Sie können auch eine nicht standardmäßige Eigenschaft angeben:</span><span class="sxs-lookup"><span data-stu-id="b2afe-117">You can also specify a non-default property:</span></span>

```powershell
Get-Command -Verb Format | Format-Wide -Property Noun
```

```Output
Custom                 Hex
List                   Table
Wide
```

### <a name="controlling-format-wide-display-with-column"></a><span data-ttu-id="b2afe-118">Steuern der „Format-Wide“-Anzeige mit Spalte</span><span class="sxs-lookup"><span data-stu-id="b2afe-118">Controlling Format-Wide Display with Column</span></span>

<span data-ttu-id="b2afe-119">Mit dem Cmdlet `Format-Wide` können Sie immer nur jeweils eine Eigenschaft anzeigen.</span><span class="sxs-lookup"><span data-stu-id="b2afe-119">With the `Format-Wide` cmdlet, you can only display a single property at a time.</span></span> <span data-ttu-id="b2afe-120">Dadurch ist es zum Anzeigen großer Listen in mehreren Spalten nützlich.</span><span class="sxs-lookup"><span data-stu-id="b2afe-120">This makes it useful for displaying large lists in multiple columns.</span></span>

```powershell
Get-Command -Verb Format | Format-Wide -Property Noun -Column 3
```

```Output
Custom                 Hex                  List
Table                  Wide

```

## <a name="using-format-list-for-a-list-view"></a><span data-ttu-id="b2afe-121">Verwenden von „Format-List“ für eine Listenansicht</span><span class="sxs-lookup"><span data-stu-id="b2afe-121">Using Format-List for a List View</span></span>

<span data-ttu-id="b2afe-122">Das Cmdlet `Format-List` zeigt ein Objekt in Form einer Auflistung an, wobei jede Eigenschaft in einer eigenen Zeile beschriftet und angezeigt wird:</span><span class="sxs-lookup"><span data-stu-id="b2afe-122">The `Format-List` cmdlet displays an object in the form of a listing, with each property labeled and displayed on a separate line:</span></span>

```powershell
Get-Process -Name iexplore | Format-List
```

```Output
Id      : 12808
Handles : 578
CPU     : 13.140625
SI      : 1
Name    : iexplore

Id      : 21748
Handles : 641
CPU     : 3.59375
SI      : 1
Name    : iexplore
```

<span data-ttu-id="b2afe-123">Sie können Sie beliebig viele Eigenschaften angeben:</span><span class="sxs-lookup"><span data-stu-id="b2afe-123">You can specify as many properties as you want:</span></span>

```powershell
Get-Process -Name iexplore | Format-List -Property ProcessName,FileVersion,StartTime,Id
```

```Output
ProcessName : iexplore
FileVersion : 11.00.18362.1 (WinBuild.160101.0800)
StartTime   : 10/22/2019 11:23:58 AM
Id          : 12808

ProcessName : iexplore
FileVersion : 11.00.18362.1 (WinBuild.160101.0800)
StartTime   : 10/22/2019 11:23:57 AM
Id          : 21748
```

### <a name="getting-detailed-information-by-using-format-list-with-wildcards"></a><span data-ttu-id="b2afe-124">Abrufen von ausführliche Informationen durch Verwenden von „Format-List“ mit Platzhaltern</span><span class="sxs-lookup"><span data-stu-id="b2afe-124">Getting Detailed Information by Using Format-List with Wildcards</span></span>

<span data-ttu-id="b2afe-125">Das Cmdlet `Format-List` ermöglicht es, einen Platzhalter als Wert für den **Property-Parameter** zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="b2afe-125">The `Format-List` cmdlet lets you use a wildcard as the value of its **Property** parameter.</span></span> <span data-ttu-id="b2afe-126">Dies ermöglicht es Ihnen, ausführliche Informationen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="b2afe-126">This lets you display detailed information.</span></span> <span data-ttu-id="b2afe-127">Häufig enthalten Objekte mehr Informationen als Sie benötigen. Dies ist der Grund, warum PowerShell nicht standardmäßig alle Eigenschaftswerte anzeigt.</span><span class="sxs-lookup"><span data-stu-id="b2afe-127">Often, objects include more information than you need, which is why PowerShell doesn't show all property values by default.</span></span> <span data-ttu-id="b2afe-128">Verwenden Sie den Befehl `Format-List -Property *`, um alle Eigenschaften eines Objekts anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="b2afe-128">To show all of properties of an object, use the `Format-List -Property *` command.</span></span> <span data-ttu-id="b2afe-129">Der folgende Befehl generiert mehr als 60 Zeilen an Ausgabe für einen einzelnen Prozess:</span><span class="sxs-lookup"><span data-stu-id="b2afe-129">The following command generates over 60 lines of output for a single process:</span></span>

```powershell
Get-Process -Name iexplore | Format-List -Property *
```

<span data-ttu-id="b2afe-130">Obwohl der Befehl `Format-List` nützlich ist, um Details anzuzeigen, ist eine einfachere Tabellenansicht oft nützlicher, wenn Sie einen Überblick über eine Ausgabe wünschen, die viele Elemente enthält.</span><span class="sxs-lookup"><span data-stu-id="b2afe-130">Although the `Format-List` command is useful for showing detail, if you want an overview of output that includes many items, a simpler tabular view is often more useful.</span></span>

## <a name="using-format-table-for-tabular-output"></a><span data-ttu-id="b2afe-131">Verwenden von „Format-Table“ für tabellarische Ausgabe</span><span class="sxs-lookup"><span data-stu-id="b2afe-131">Using Format-Table for Tabular Output</span></span>

<span data-ttu-id="b2afe-132">Falls Sie die Ausgabe des Befehls `Get-Process` mit dem Cmdlet `Format-Table` ohne angegebene Eigenschaftennamen formatieren, erhalten Sie genau dieselbe Ausgabe wie ohne das Cmdlet `Format`.</span><span class="sxs-lookup"><span data-stu-id="b2afe-132">If you use the `Format-Table` cmdlet with no property names specified to format the output of the `Get-Process` command, you get exactly the same output as you do without a `Format` cmdlet.</span></span> <span data-ttu-id="b2afe-133">Standardmäßig zeigt PowerShell **Prozessobjekte** im Tabellenformat an.</span><span class="sxs-lookup"><span data-stu-id="b2afe-133">By default, PowerShell displays **Process** objects in a tabular format.</span></span>

```powershell
Get-Service -Name win* | Format-Table
```

```Output
Status   Name               DisplayName
------   ----               -----------
Running  WinDefend          Windows Defender Antivirus Service
Running  WinHttpAutoProx... WinHTTP Web Proxy Auto-Discovery Se...
Running  Winmgmt            Windows Management Instrumentation
Running  WinRM              Windows Remote Management (WS-Manag...
```

### <a name="improving-format-table-output-autosize"></a><span data-ttu-id="b2afe-134">Verbessern der „Format-Table“-Ausgabe (AutoSize)</span><span class="sxs-lookup"><span data-stu-id="b2afe-134">Improving Format-Table Output (AutoSize)</span></span>

<span data-ttu-id="b2afe-135">Eine Tabellenansicht ist zwar zum Anzeigen großer Informationsmengen nützlich, kann aber zu Interpretationsschwierigkeiten führen, wenn die Anzeige zu schmal für die Daten ist.</span><span class="sxs-lookup"><span data-stu-id="b2afe-135">Although a tabular view is useful for displaying lots of information, it may be difficult to interpret if the display is too narrow for the data.</span></span> <span data-ttu-id="b2afe-136">Im vorherigen Beispiel ist die Ausgabe abgeschnitten.</span><span class="sxs-lookup"><span data-stu-id="b2afe-136">In the previous example, the output is truncated.</span></span> <span data-ttu-id="b2afe-137">Falls Sie den **AutoSize-Parameter** angeben, wenn Sie den Befehl `Format-Table` ausführen, berechnet PowerShell die Spaltenbreiten anhand der tatsächlich angezeigten Daten.</span><span class="sxs-lookup"><span data-stu-id="b2afe-137">If you specify the **AutoSize** parameter when you run the `Format-Table` command, PowerShell calculates column widths based on the actual data displayed.</span></span> <span data-ttu-id="b2afe-138">Dadurch werden die Spalten lesbar.</span><span class="sxs-lookup"><span data-stu-id="b2afe-138">This makes the columns readable.</span></span>

```powershell
Get-Service -Name win* | Format-Table -AutoSize
```

```Output
Status  Name                DisplayName
------  ----                -----------
Running WinDefend           Windows Defender Antivirus Service
Running WinHttpAutoProxySvc WinHTTP Web Proxy Auto-Discovery Service
Running Winmgmt             Windows Management Instrumentation
Running WinRM               Windows Remote Management (WS-Management)
```

<span data-ttu-id="b2afe-139">Im Cmdlet `Format-Table` werden möglicherweise weiterhin Daten abgeschnitten, aber nur am Ende des Bildschirms.</span><span class="sxs-lookup"><span data-stu-id="b2afe-139">The `Format-Table` cmdlet might still truncate data, but it only truncates at the end of the screen.</span></span> <span data-ttu-id="b2afe-140">Jede Eigenschaft außer der letzten angezeigten Eigenschaft erhält so viel Breite, wie erforderlich ist, damit ihr längstes Datenelement richtig angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="b2afe-140">Properties, other than the last one displayed, are given as much size as they need for their longest data element to display correctly.</span></span>

```powershell
Get-Service -Name win* | Format-Table -Property Name,Status,StartType,DisplayName,DependentServices -AutoSize
```

```Output
Name                 Status StartType DisplayName                               DependentServi
                                                                                ces
----                 ------ --------- -----------                               --------------
WinDefend           Running Automatic Windows Defender Antivirus Service        {}
WinHttpAutoProxySvc Running    Manual WinHTTP Web Proxy Auto-Discovery Service  {NcaSvc, iphl…
Winmgmt             Running Automatic Windows Management Instrumentation        {vmms, TPHKLO…
WinRM               Running Automatic Windows Remote Management (WS-Management) {}
```

<span data-ttu-id="b2afe-141">Der Befehl `Format-Table` geht davon aus, dass Eigenschaften nach Wichtigkeit aufgelistet werden.</span><span class="sxs-lookup"><span data-stu-id="b2afe-141">The `Format-Table` command assumes that properties are listed in order of importance.</span></span> <span data-ttu-id="b2afe-142">Daher wird im Befehl versucht, die Eigenschaften, die dem Anfang am nächsten sind, vollständig anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="b2afe-142">So it attempts to fully display the properties nearest the beginning.</span></span> <span data-ttu-id="b2afe-143">Wenn der Befehl `Format-Table` nicht alle Eigenschaften anzeigen kann, entfernt er einige Spalten aus der Anzeige.</span><span class="sxs-lookup"><span data-stu-id="b2afe-143">If the `Format-Table` command can't display all the properties, it removes some columns from the display.</span></span> <span data-ttu-id="b2afe-144">Dieses Verhalten wird im vorherigen Beispiel mit der **DependentServices-Eigenschaft** veranschaulicht.</span><span class="sxs-lookup"><span data-stu-id="b2afe-144">You can see this behavior in the **DependentServices** property previous example.</span></span>

### <a name="wrapping-format-table-output-in-columns-wrap"></a><span data-ttu-id="b2afe-145">Umbrechen von „Format-Table“-Ausgabe in Spalten (Wrap)</span><span class="sxs-lookup"><span data-stu-id="b2afe-145">Wrapping Format-Table Output in Columns (Wrap)</span></span>

<span data-ttu-id="b2afe-146">Sie können erzwingen, dass zu lange `Format-Table`-Daten innerhalb ihrer Anzeigespalte umbrochen werden, indem Sie den **Wrap-Parameter** verwenden.</span><span class="sxs-lookup"><span data-stu-id="b2afe-146">You can force lengthy `Format-Table` data to wrap within its display column by using the **Wrap** parameter.</span></span> <span data-ttu-id="b2afe-147">Das Verwenden des **Wrap-Parameters** führt möglicherweise nicht zum von Ihnen erwarteten Ergebnis, weil die Standardeinstellungen verwendet werden, wenn Sie nicht auch **AutoSize** angeben:</span><span class="sxs-lookup"><span data-stu-id="b2afe-147">Using the **Wrap** parameter may not do what you expect, since it uses default settings if you don't also specify **AutoSize** :</span></span>

```powershell
Get-Service -Name win* | Format-Table -Property Name,Status,StartType,DisplayName,DependentServices -Wrap
```

```Output
Name                 Status StartType DisplayName                               DependentServi
                                                                                ces
----                 ------ --------- -----------                               --------------
WinDefend           Running Automatic Windows Defender Antivirus Service        {}
WinHttpAutoProxySvc Running    Manual WinHTTP Web Proxy Auto-Discovery Service  {NcaSvc,
                                                                                iphlpsvc}
Winmgmt             Running Automatic Windows Management Instrumentation        {vmms,
                                                                                TPHKLOAD,
                                                                                SUService,
                                                                                smstsmgr…}
WinRM               Running Automatic Windows Remote Management (WS-Management) {}
```

<span data-ttu-id="b2afe-148">Die Verwendung des **Wrap-Parameters** an sich verlangsamt die Verarbeitung kaum.</span><span class="sxs-lookup"><span data-stu-id="b2afe-148">Using the **Wrap** parameter by itself doesn't slow down processing very much.</span></span> <span data-ttu-id="b2afe-149">Wenn Sie **AutoSize** für das Formatieren einer rekursiven Dateiliste einer großen Verzeichnisstruktur verwenden, kann dieser Vorgang viel Zeit und Arbeitsspeicher in Anspruch nehmen, bevor die ersten Ausgabeelemente angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="b2afe-149">However, using **AutoSize** to format a recursive file listing of a large directory structure can take a long time and use lots of memory before displaying the first output items.</span></span>

<span data-ttu-id="b2afe-150">Wenn die Systemauslastung keine Rolle spielt, funktioniert **AutoSize** gut mit dem **Wrap-Parameter** .</span><span class="sxs-lookup"><span data-stu-id="b2afe-150">If you aren't concerned about system load, then **AutoSize** works well with the **Wrap** parameter.</span></span>
<span data-ttu-id="b2afe-151">Die ursprünglichen Spalten verwenden weiterhin so viel Breite wie erforderlich, um Elemente in einer Zeile anzuzeigen, aber die letzte Spalte wird ggf. umschlossen.</span><span class="sxs-lookup"><span data-stu-id="b2afe-151">The initial columns still use as much width as needed to display items on one line, but the final column is wrapped, if necessary.</span></span>

> [!NOTE]
> <span data-ttu-id="b2afe-152">Einige Spalten werden möglicherweise nicht angezeigt, wenn Sie zuerst die breiteste Spalte angeben.</span><span class="sxs-lookup"><span data-stu-id="b2afe-152">Some columns may not be displayed when you specify the widest columns first.</span></span> <span data-ttu-id="b2afe-153">Geben Sie für optimale Ergebnisse zuerst die kleinsten Datenelemente an.</span><span class="sxs-lookup"><span data-stu-id="b2afe-153">For best results, specify the smallest data elements first.</span></span>

<span data-ttu-id="b2afe-154">Im folgenden Beispiel werden die breitesten Eigenschaften zuerst angegeben.</span><span class="sxs-lookup"><span data-stu-id="b2afe-154">In the following example, we specify the widest properties first.</span></span>

```powershell
Get-Process -Name iexplore | Format-Table -Wrap -AutoSize -Property FileVersion,Path,Name,Id
```

<span data-ttu-id="b2afe-155">Selbst mit Umschließung wird die letzte **Id** -Spalte ausgelassen:</span><span class="sxs-lookup"><span data-stu-id="b2afe-155">Even with wrapping, the final **Id** column is omitted:</span></span>

```Output
FileVersion                          Path                                                  Nam
                                                                                           e
-----------                          ----                                                  ---
11.00.18362.1 (WinBuild.160101.0800) C:\Program Files (x86)\Internet Explorer\IEXPLORE.EXE iex
                                                                                           plo
                                                                                           re
11.00.18362.1 (WinBuild.160101.0800) C:\Program Files\Internet Explorer\iexplore.exe       iex
                                                                                           plo
                                                                                           re
```

### <a name="organizing-table-output--groupby"></a><span data-ttu-id="b2afe-156">Ordnen von Tabellenausgabe (-GroupBy)</span><span class="sxs-lookup"><span data-stu-id="b2afe-156">Organizing Table Output (-GroupBy)</span></span>

<span data-ttu-id="b2afe-157">Eine weiterer nützlicher Parameter für das Steuern von tabellarischer Ausgabe ist **GroupBy** .</span><span class="sxs-lookup"><span data-stu-id="b2afe-157">Another useful parameter for tabular output control is **GroupBy** .</span></span> <span data-ttu-id="b2afe-158">Es kann insbesondere schwierig sein, längere tabellarische Auflistungen zu vergleichen.</span><span class="sxs-lookup"><span data-stu-id="b2afe-158">Longer tabular listings in particular may be hard to compare.</span></span> <span data-ttu-id="b2afe-159">Mit dem **GroupBy** Parameter wird die Ausgabe anhand eines Eigenschaftswerts gruppiert.</span><span class="sxs-lookup"><span data-stu-id="b2afe-159">The **GroupBy** parameter groups output based on a property value.</span></span> <span data-ttu-id="b2afe-160">Beispielsweise können Dienste zur einfacheren Überprüfung nach **StartType** gruppiert werden. Dadurch wird der **StartType** -Wert aus der Eigenschaftenliste entfernt:</span><span class="sxs-lookup"><span data-stu-id="b2afe-160">For example, we can group services by **StartType** for easier inspection, omitting the **StartType** value from the property listing:</span></span>

```powershell
Get-Service -Name win* | Sort-Object StartType | Format-Table -GroupBy StartType
```

```Output
   StartType: Automatic
Status   Name               DisplayName
------   ----               -----------
Running  WinDefend          Windows Defender Antivirus Service
Running  Winmgmt            Windows Management Instrumentation
Running  WinRM              Windows Remote Management (WS-Managem…

   StartType: Manual
Status   Name               DisplayName
------   ----               -----------
Running  WinHttpAutoProxyS… WinHTTP Web Proxy Auto-Discovery Serv…
```
