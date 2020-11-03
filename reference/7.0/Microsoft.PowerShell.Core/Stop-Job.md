---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/stop-job?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Stop-Job
ms.openlocfilehash: 1f00d08ec97d20c3d353c22e8f7abfee7c88621a
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2020
ms.locfileid: "93209844"
---
# <span data-ttu-id="50757-103">Stop-Job</span><span class="sxs-lookup"><span data-stu-id="50757-103">Stop-Job</span></span>

## <span data-ttu-id="50757-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="50757-104">SYNOPSIS</span></span>
<span data-ttu-id="50757-105">Beendet einen PowerShell-Hintergrund Auftrag.</span><span class="sxs-lookup"><span data-stu-id="50757-105">Stops a PowerShell background job.</span></span>

## <span data-ttu-id="50757-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="50757-106">SYNTAX</span></span>

### <span data-ttu-id="50757-107">Sessionidparameterset (Standard)</span><span class="sxs-lookup"><span data-stu-id="50757-107">SessionIdParameterSet (Default)</span></span>

```
Stop-Job [-PassThru] [-Id] <Int32[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="50757-108">Jobparameterset</span><span class="sxs-lookup"><span data-stu-id="50757-108">JobParameterSet</span></span>

```
Stop-Job [-Job] <Job[]> [-PassThru] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="50757-109">Nameparameterset</span><span class="sxs-lookup"><span data-stu-id="50757-109">NameParameterSet</span></span>

```
Stop-Job [-PassThru] [-Name] <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="50757-110">Instanceidparameterset</span><span class="sxs-lookup"><span data-stu-id="50757-110">InstanceIdParameterSet</span></span>

```
Stop-Job [-PassThru] [-InstanceId] <Guid[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="50757-111">Stateparameterset</span><span class="sxs-lookup"><span data-stu-id="50757-111">StateParameterSet</span></span>

```
Stop-Job [-PassThru] [-State] <JobState> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="50757-112">Filterparameterset</span><span class="sxs-lookup"><span data-stu-id="50757-112">FilterParameterSet</span></span>

```
Stop-Job [-PassThru] [-Filter] <Hashtable> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="50757-113">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="50757-113">DESCRIPTION</span></span>

<span data-ttu-id="50757-114">Das Cmdlet " **Stopp-Job** " beendet PowerShell-Hintergrund Aufträge, die gerade ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="50757-114">The **Stop-Job** cmdlet stops PowerShell background jobs that are in progress.</span></span>
<span data-ttu-id="50757-115">Mit diesem Cmdlet können Sie alle Aufträge oder ausgewählte Aufträge auf der Grundlage ihres Namens, der ID, der Instanz-ID oder des Zustands abbrechen oder indem Sie ein Auftrags Objekt an " **beendet-Job** " übergeben.</span><span class="sxs-lookup"><span data-stu-id="50757-115">You can use this cmdlet to stop all jobs or stop selected jobs based on their name, ID, instance ID, or state, or by passing a job object to **Stop-Job** .</span></span>

<span data-ttu-id="50757-116">Sie können " **stopjob** " verwenden, um Hintergrund Aufträge zu verhindern, z. b. solche, die mit dem Cmdlet "Start-Job" oder dem *AsJob* -Parameter eines beliebigen Cmdlets gestartet wurden.</span><span class="sxs-lookup"><span data-stu-id="50757-116">You can use **Stop-Job** to stop background jobs, such as those that were started by using the Start-Job cmdlet or the *AsJob* parameter of any cmdlet.</span></span>
<span data-ttu-id="50757-117">Wenn Sie einen Hintergrund Auftrag beenden, schließt PowerShell alle Aufgaben ab, die in der Auftrags Warteschlange ausstehend sind, und beendet dann den Auftrag.</span><span class="sxs-lookup"><span data-stu-id="50757-117">When you stop a background job, PowerShell completes all tasks that are pending in that job queue and then ends the job.</span></span>
<span data-ttu-id="50757-118">Keine neuen Vorgänge werden in die Warteschlange hinzugefügt, nachdem dieser Befehl gesendet wird.</span><span class="sxs-lookup"><span data-stu-id="50757-118">No new tasks are added to the queue after this command is submitted.</span></span>

<span data-ttu-id="50757-119">Mit diesem Cmdlet werden die Hintergrundaufträge nicht gelöscht.</span><span class="sxs-lookup"><span data-stu-id="50757-119">This cmdlet does not delete background jobs.</span></span>
<span data-ttu-id="50757-120">Zum Löschen eines Auftrags verwenden Sie das Cmdlet "Remove-Job".</span><span class="sxs-lookup"><span data-stu-id="50757-120">To delete a job, use the Remove-Job cmdlet.</span></span>

<span data-ttu-id="50757-121">Ab Windows PowerShell 3,0 stoppt " **Stopp-Job** " auch benutzerdefinierte Auftrags Typen, z. b. Workflow Aufträge und Instanzen von geplanten Aufträgen.</span><span class="sxs-lookup"><span data-stu-id="50757-121">Starting in Windows PowerShell 3.0, **Stop-Job** also stops custom job types, such as workflow jobs and instances of scheduled jobs.</span></span>
<span data-ttu-id="50757-122">Um " **beendet-Job** " zum Abbrechen eines Auftrags mit einem benutzerdefinierten Auftragstyp zu aktivieren, müssen Sie das Modul, das den benutzerdefinierten Auftragstyp unterstützt, in die Sitzung importieren, bevor Sie einen Befehl zum **Abbrechen eines Auftrags** ausführen, indem Sie entweder das Cmdlet "Import-Module" verwenden oder ein Cmdlet im Modul verwenden.</span><span class="sxs-lookup"><span data-stu-id="50757-122">To enable **Stop-Job** to stop a job with custom job type, import the module that supports the custom job type into the session before you run a **Stop-Job** command, either by using the Import-Module cmdlet or by using or getting a cmdlet in the module.</span></span>
<span data-ttu-id="50757-123">Informationen zu einem bestimmten benutzerdefinierten Auftragstyp finden Sie in der Dokumentation der Funktion „Benutzerdefinierte Auftragstypen“.</span><span class="sxs-lookup"><span data-stu-id="50757-123">For information about a particular custom job type, see the documentation of the custom job type feature.</span></span>

## <span data-ttu-id="50757-124">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="50757-124">EXAMPLES</span></span>

### <span data-ttu-id="50757-125">Beispiel 1: Abbrechen eines Auftrags auf einem Remote Computer mit Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="50757-125">Example 1: Stop a job on a remote computer by using Invoke-Command</span></span>

```powershell
$s = New-PSSession -ComputerName Server01 -Credential Domain01\Admin02
$j = Invoke-Command -Session $s -ScriptBlock {Start-Job -ScriptBlock {Get-EventLog System}}
Invoke-Command -Session $s -ScriptBlock { Stop-job -Job $Using:j }
```

<span data-ttu-id="50757-126">Dieses Beispiel zeigt, wie Sie das **Stop-Job** -Cmdlet verwenden, um einen Auftrag zu beenden, der auf einem Remotecomputer ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="50757-126">This example shows how to use the **Stop-Job** cmdlet to stop a job that is running on a remote computer.</span></span>

<span data-ttu-id="50757-127">Da der Auftrag mithilfe des Invoke-Command-Cmdlets gestartet wurde, um einen **Start-Job-** Befehl Remote auszuführen, wird das Auftrags Objekt auf dem Remote Computer gespeichert.</span><span class="sxs-lookup"><span data-stu-id="50757-127">Because the job was started by using the Invoke-Command cmdlet to run a **Start-Job** command remotely, the job object is stored on the remote computer.</span></span>
<span data-ttu-id="50757-128">Sie müssen einen anderen Befehl zum **aufrufen** eines Auftrags verwenden, um einen Befehl zum **Abbrechen** von Aufträgen Remote auszuführen.</span><span class="sxs-lookup"><span data-stu-id="50757-128">You must use another **Invoke-Command** command to run a **Stop-Job** command remotely.</span></span>
<span data-ttu-id="50757-129">Weitere Informationen zu Remotehintergrundaufträgen finden Sie unter „about_Remote_Jobs“.</span><span class="sxs-lookup"><span data-stu-id="50757-129">For more information about remote background jobs, see about_Remote_Jobs.</span></span>

<span data-ttu-id="50757-130">Der erste Befehl erstellt eine PowerShell-Sitzung ( **PSSession** ) auf dem Server01-Computer und speichert dann das Sitzungs Objekt in der $s Variable.</span><span class="sxs-lookup"><span data-stu-id="50757-130">The first command creates a PowerShell session ( **PSSession** ) on the Server01 computer, and then stores the session object in the $s variable.</span></span>
<span data-ttu-id="50757-131">Der Befehl verwendet die Anmeldeinformationen eines Domänenadministrators.</span><span class="sxs-lookup"><span data-stu-id="50757-131">The command uses the credentials of a domain administrator.</span></span>

<span data-ttu-id="50757-132">Der zweite Befehl verwendet das **Invoke-Command** -Cmdlet zum Ausführen eines **Start-Job** -Befehls in der Sitzung.</span><span class="sxs-lookup"><span data-stu-id="50757-132">The second command uses the **Invoke-Command** cmdlet to run a **Start-Job** command in the session.</span></span>
<span data-ttu-id="50757-133">Der Befehl im Auftrag ruft alle Ereignisse im Systemereignisprotokoll ab.</span><span class="sxs-lookup"><span data-stu-id="50757-133">The command in the job gets all of the events in the System event log.</span></span>
<span data-ttu-id="50757-134">Das resultierende Auftragsobjekt wird in der $j-Variablen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="50757-134">The resulting job object is stored in the $j variable.</span></span>

<span data-ttu-id="50757-135">Mit dem dritten Befehl wird der Auftrag beendet.</span><span class="sxs-lookup"><span data-stu-id="50757-135">The third command stops the job.</span></span>
<span data-ttu-id="50757-136">Er verwendet das Cmdlet " **Aufruf-Command** ", um einen Befehl zum **Abbrechen eines Auftrags** in der **PSSession** auf Server01 auszuführen.</span><span class="sxs-lookup"><span data-stu-id="50757-136">It uses the **Invoke-Command** cmdlet to run a **Stop-Job** command in the **PSSession** on Server01.</span></span>
<span data-ttu-id="50757-137">Da die Auftragsobjekte in $j, einer Variablen auf dem lokalen Computer, gespeichert werden, verwendet der Befehl den „Using“-Bereichsbezeichner, um $j als lokale Variable zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="50757-137">Because the job objects are stored in $j, which is a variable on the local computer, the command uses the Using scope modifier to identify $j as a local variable.</span></span>
<span data-ttu-id="50757-138">Weitere Informationen zum using-bereichsmodifizierer finden Sie unter [about_Remote_Variables](about/about_Remote_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="50757-138">For more information about the Using scope modifier, see [about_Remote_Variables](about/about_Remote_Variables.md).</span></span>

<span data-ttu-id="50757-139">Wenn der Befehl abgeschlossen ist, wird der Auftrag beendet und die **PSSession** in $s zur Verwendung verfügbar.</span><span class="sxs-lookup"><span data-stu-id="50757-139">When the command finishes, the job is stopped and the **PSSession** in $s is available for use.</span></span>

### <span data-ttu-id="50757-140">Beispiel 2: Abbrechen eines Hintergrund Auftrags</span><span class="sxs-lookup"><span data-stu-id="50757-140">Example 2: Stop a background job</span></span>

```powershell
Stop-Job -Name "Job1"
```

<span data-ttu-id="50757-141">Dieser Befehl beendet den Hintergrundauftrag Job1.</span><span class="sxs-lookup"><span data-stu-id="50757-141">This command stops the Job1 background job.</span></span>

### <span data-ttu-id="50757-142">Beispiel 3: mehrere Hintergrund Aufträge werden beendet.</span><span class="sxs-lookup"><span data-stu-id="50757-142">Example 3: Stop several background jobs</span></span>

```powershell
Stop-Job -Id 1, 3, 4
```

<span data-ttu-id="50757-143">Mit diesem Befehl werden drei Aufträge beendet.</span><span class="sxs-lookup"><span data-stu-id="50757-143">This command stops three jobs.</span></span>
<span data-ttu-id="50757-144">Sie werden anhand der ID identifiziert.</span><span class="sxs-lookup"><span data-stu-id="50757-144">It identifies them by their IDs.</span></span>

### <span data-ttu-id="50757-145">Beispiel 4: alle Hintergrund Aufträge werden beendet</span><span class="sxs-lookup"><span data-stu-id="50757-145">Example 4: Stop all background jobs</span></span>

```powershell
Get-Job | Stop-Job
```

<span data-ttu-id="50757-146">Mit diesem Befehl werden alle Hintergrundaufträge im in der aktuellen Sitzung beendet.</span><span class="sxs-lookup"><span data-stu-id="50757-146">This command stops all of the background jobs in the current session.</span></span>

### <span data-ttu-id="50757-147">Beispiel 5: Abbrechen aller blockierten Hintergrund Aufträge</span><span class="sxs-lookup"><span data-stu-id="50757-147">Example 5: Stop all blocked background jobs</span></span>

```powershell
Stop-Job -State Blocked
```

<span data-ttu-id="50757-148">Dieser Befehl beendet alle Aufträge, die blockiert sind.</span><span class="sxs-lookup"><span data-stu-id="50757-148">This command stops all the jobs that are blocked.</span></span>

### <span data-ttu-id="50757-149">Beispiel 6: Beenden eines Auftrags mit einer Instanz-ID</span><span class="sxs-lookup"><span data-stu-id="50757-149">Example 6: Stop a job by using an instance ID</span></span>

```powershell
Get-Job | Format-Table ID, Name, Command, @{Label="State";Expression={$_.JobStateInfo.State}},
InstanceID -Auto
```

```Output
Id Name Command                 State  InstanceId
-- ---- -------                 -----  ----------
1 Job1 start-service schedule Running 05abb67a-2932-4bd5-b331-c0254b8d9146
3 Job3 start-service schedule Running c03cbd45-19f3-4558-ba94-ebe41b68ad03
5 Job5 get-service s*         Blocked e3bbfed1-9c53-401a-a2c3-a8db34336adf
```

```powershell
Stop-Job -InstanceId e3bbfed1-9c53-401a-a2c3-a8db34336adf
```

<span data-ttu-id="50757-150">Diese Befehle veranschaulichen die Beendigung eines Auftrags basierend auf der Instanz-ID.</span><span class="sxs-lookup"><span data-stu-id="50757-150">These commands show how to stop a job based on its instance ID.</span></span>

<span data-ttu-id="50757-151">Der erste Befehl verwendet das Cmdlet "Get-Job", um die Aufträge in der aktuellen Sitzung zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="50757-151">The first command uses the Get-Job cmdlet to get the jobs in the current session.</span></span>
<span data-ttu-id="50757-152">Der Befehl verwendet einen Pipeline Operator (|), um die Aufträge an einen Format-Table Befehl zu senden, der eine Tabelle mit den angegebenen Eigenschaften jedes Auftrags anzeigt.</span><span class="sxs-lookup"><span data-stu-id="50757-152">The command uses a pipeline operator (|) to send the jobs to a Format-Table command, which displays a table of the specified properties of each job.</span></span>
<span data-ttu-id="50757-153">Die Tabelle enthält die Instanz-ID für jeden Auftrag.</span><span class="sxs-lookup"><span data-stu-id="50757-153">The table includes the Instance ID of each job.</span></span>
<span data-ttu-id="50757-154">Er verwendet eine berechnete Eigenschaft, um den Auftragsstatus anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="50757-154">It uses a calculated property to display the job state.</span></span>

<span data-ttu-id="50757-155">Der zweite Befehl verwendet einen Befehl zum **Abbrechen eines Auftrags** , der über den *InstanceId-* Parameter verfügt, um einen ausgewählten Auftrag zu unterbinden.</span><span class="sxs-lookup"><span data-stu-id="50757-155">The second command uses a **Stop-Job** command that has the *InstanceID* parameter to stop a selected job.</span></span>

### <span data-ttu-id="50757-156">Beispiel 7: Abbrechen eines Auftrags auf einem Remote Computer</span><span class="sxs-lookup"><span data-stu-id="50757-156">Example 7: Stop a job on a remote computer</span></span>

```powershell
$j = Invoke-Command -ComputerName Server01 -ScriptBlock {Get-EventLog System} -AsJob
$j | Stop-Job -PassThru
```

```Output
Id    Name    State      HasMoreData     Location         Command
--    ----    ----       -----------     --------         -------
5     Job5    Stopped    True            user01-tablet    get-eventlog system
```

<span data-ttu-id="50757-157">Dieses Beispiel zeigt, wie Sie das **Stop-Job** -Cmdlet verwenden, um einen Auftrag zu beenden, der auf einem Remotecomputer ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="50757-157">This example shows how to use the **Stop-Job** cmdlet to stop a job that is running on a remote computer.</span></span>

<span data-ttu-id="50757-158">Da der Auftrag mithilfe des *AsJob* -Parameters des Cmdlets " **Aufruf-Command** " gestartet wurde, befindet sich das Auftrags Objekt auf dem lokalen Computer, obwohl der Auftrag auf dem Remote Computer ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="50757-158">Because the job was started by using the *AsJob* parameter of the **Invoke-Command** cmdlet, the job object is located on the local computer, even though the job runs on the remote computer.</span></span>
<span data-ttu-id="50757-159">Daher können Sie einen lokalen Befehl zum **Abbrechen eines Auftrags** verwenden, um den Auftrag zu unterbinden.</span><span class="sxs-lookup"><span data-stu-id="50757-159">Therefore, you can use a local **Stop-Job** command to stop the job.</span></span>

<span data-ttu-id="50757-160">Der erste Befehl verwendet das **Invoke-Command** -Cmdlet, um einen Hintergrundauftrag auf dem Computer Server01 zu starten.</span><span class="sxs-lookup"><span data-stu-id="50757-160">The first command uses the **Invoke-Command** cmdlet to start a background job on the Server01 computer.</span></span>
<span data-ttu-id="50757-161">Der Befehl verwendet den *AsJob* -Parameter, um den Remotebefehl als Hintergrundauftrag auszuführen.</span><span class="sxs-lookup"><span data-stu-id="50757-161">The command uses the *AsJob* parameter to run the remote command as a background job.</span></span>

<span data-ttu-id="50757-162">Dieser Befehl gibt ein Auftrags Objekt zurück, bei dem es sich um das gleiche Auftrags Objekt handelt, das vom **Start-Job-** Cmdlet zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="50757-162">This command returns a job object, which is the same job object that the **Start-Job** cmdlet returns.</span></span>
<span data-ttu-id="50757-163">Der Befehl speichert das Auftragsobjekt in der $j-Variablen.</span><span class="sxs-lookup"><span data-stu-id="50757-163">The command saves the job object in the $j variable.</span></span>

<span data-ttu-id="50757-164">Der zweite zweite Befehl verwendet einen Pipelineoperator, um den Auftrag in der $j-Variablen an „Stop-Job“ zu senden.</span><span class="sxs-lookup"><span data-stu-id="50757-164">The second command uses a pipeline operator to send the job in the $j variable to Stop-Job.</span></span>
<span data-ttu-id="50757-165">Der Befehl verwendet den *PassThru* -Parameter, um **Stop-Job** anzuweisen, ein Auftragsobjekt zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="50757-165">The command uses the *PassThru* parameter to direct **Stop-Job** to return a job object.</span></span>
<span data-ttu-id="50757-166">Die Auftrags Objekt Anzeige bestätigt, dass der Status des Auftrags beendet wurde.</span><span class="sxs-lookup"><span data-stu-id="50757-166">The job object display confirms that the state of the job is Stopped.</span></span>

<span data-ttu-id="50757-167">Weitere Informationen zu Remotehintergrundaufträgen finden Sie unter „about_Remote_Jobs“.</span><span class="sxs-lookup"><span data-stu-id="50757-167">For more information about remote background jobs, see about_Remote_Jobs.</span></span>

## <span data-ttu-id="50757-168">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="50757-168">PARAMETERS</span></span>

### <span data-ttu-id="50757-169">-Filter</span><span class="sxs-lookup"><span data-stu-id="50757-169">-Filter</span></span>

<span data-ttu-id="50757-170">Gibt eine Hash Tabelle mit Bedingungen an.</span><span class="sxs-lookup"><span data-stu-id="50757-170">Specifies a hash table of conditions.</span></span>
<span data-ttu-id="50757-171">Dieses Cmdlet beendet Aufträge, die alle Bedingungen erfüllen.</span><span class="sxs-lookup"><span data-stu-id="50757-171">This cmdlet stops jobs that satisfy all of the conditions.</span></span>
<span data-ttu-id="50757-172">Geben Sie eine Hashtabelle ein, in der die Schlüssel Auftragseigenschaften und die Werte Werte der Auftragseigenschaften sind.</span><span class="sxs-lookup"><span data-stu-id="50757-172">Enter a hash table where the keys are job properties and the values are job property values.</span></span>

<span data-ttu-id="50757-173">Dieser Parameter funktioniert nur mit benutzerdefinierten Auftragstypen, z. B. Workflowaufträgen und geplanten Aufträgen.</span><span class="sxs-lookup"><span data-stu-id="50757-173">This parameter works only on custom job types, such as workflow jobs and scheduled jobs.</span></span>
<span data-ttu-id="50757-174">Es funktioniert nicht bei standardmäßigen Hintergrund Aufträgen, wie z. b. bei der Verwendung des Cmdlets **Start-Job** .</span><span class="sxs-lookup"><span data-stu-id="50757-174">It does not work on standard background jobs, such as those created by using the **Start-Job** cmdlet.</span></span>
<span data-ttu-id="50757-175">Weitere Informationen zur Unterstützung für diesen Parameter finden Sie unter dem Hilfethema für den Auftragstyp.</span><span class="sxs-lookup"><span data-stu-id="50757-175">For information about support for this parameter, see the help topic for the job type.</span></span>

<span data-ttu-id="50757-176">Dieser Parameter wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="50757-176">This parameter was introduced in Windows PowerShell 3.0.</span></span>

```yaml
Type: System.Collections.Hashtable
Parameter Sets: FilterParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="50757-177">-Id</span><span class="sxs-lookup"><span data-stu-id="50757-177">-Id</span></span>

<span data-ttu-id="50757-178">Gibt die IDs von Aufträgen an, die von diesem Cmdlet beendet werden.</span><span class="sxs-lookup"><span data-stu-id="50757-178">Specifies the IDs of jobs that this cmdlet stops.</span></span>
<span data-ttu-id="50757-179">Der Standardwert ist alle Aufträge in der aktuellen Sitzung.</span><span class="sxs-lookup"><span data-stu-id="50757-179">The default is all jobs in the current session.</span></span>

<span data-ttu-id="50757-180">Die ID ist eine Ganzzahl, die den Auftrag in der aktuellen Sitzung eindeutig identifiziert.</span><span class="sxs-lookup"><span data-stu-id="50757-180">The ID is an integer that uniquely identifies the job in the current session.</span></span>
<span data-ttu-id="50757-181">Es ist leichter zu merken und einzugeben als die Instanz-ID, Sie ist jedoch nur in der aktuellen Sitzung eindeutig.</span><span class="sxs-lookup"><span data-stu-id="50757-181">It is easier to remember and type than the instance ID, but it is unique only in the current session.</span></span>
<span data-ttu-id="50757-182">Sie können eine oder mehrere IDs (durch Kommas getrennt) eingeben.</span><span class="sxs-lookup"><span data-stu-id="50757-182">You can type one or more IDs, separated by commas.</span></span>
<span data-ttu-id="50757-183">Um die ID eines Auftrags zu ermitteln, geben Sie ein `Get-Job` .</span><span class="sxs-lookup"><span data-stu-id="50757-183">To find the ID of a job, type `Get-Job`.</span></span>

```yaml
Type: System.Int32[]
Parameter Sets: SessionIdParameterSet
Aliases:

Required: True
Position: 0
Default value: All jobs
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="50757-184">-InstanceId</span><span class="sxs-lookup"><span data-stu-id="50757-184">-InstanceId</span></span>

<span data-ttu-id="50757-185">Gibt die Instanz-IDs von Aufträgen an, die von diesem Cmdlet angehalten werden.</span><span class="sxs-lookup"><span data-stu-id="50757-185">Specifies the instance IDs of jobs that this cmdlet stops.</span></span>
<span data-ttu-id="50757-186">Standardmäßig werden alle Aufträge fortgesetzt.</span><span class="sxs-lookup"><span data-stu-id="50757-186">The default is all jobs.</span></span>

<span data-ttu-id="50757-187">Eine Instanz-ID ist eine GUID, die den Auftrag auf dem Computer eindeutig identifiziert.</span><span class="sxs-lookup"><span data-stu-id="50757-187">An instance ID is a GUID that uniquely identifies the job on the computer.</span></span>
<span data-ttu-id="50757-188">Um die Instanz-ID eines Auftrags zu ermitteln, verwenden Sie „Get-Job“.</span><span class="sxs-lookup"><span data-stu-id="50757-188">To find the instance ID of a job, use Get-Job.</span></span>

```yaml
Type: System.Guid[]
Parameter Sets: InstanceIdParameterSet
Aliases:

Required: True
Position: 0
Default value: All jobs
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="50757-189">-Auftrag</span><span class="sxs-lookup"><span data-stu-id="50757-189">-Job</span></span>

<span data-ttu-id="50757-190">Gibt die Aufträge an, die von diesem Cmdlet beendet werden.</span><span class="sxs-lookup"><span data-stu-id="50757-190">Specifies the jobs that this cmdlet stops.</span></span>
<span data-ttu-id="50757-191">Geben Sie eine Variable ein, die entweder die Aufträge oder einen Befehl enthält, durch den die Aufträge abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="50757-191">Enter a variable that contains the jobs or a command that gets the jobs.</span></span>
<span data-ttu-id="50757-192">Sie können auch einen Pipeline Operator verwenden, um Aufträge an das Cmdlet "Set **-Job** " zu übermitteln.</span><span class="sxs-lookup"><span data-stu-id="50757-192">You can also use a pipeline operator to submit jobs to the **Stop-Job** cmdlet.</span></span>
<span data-ttu-id="50757-193">Standardmäßig löscht " **beendet-Job** " alle Aufträge, die in der aktuellen Sitzung gestartet wurden.</span><span class="sxs-lookup"><span data-stu-id="50757-193">By default, **Stop-Job** deletes all jobs that were started in the current session.</span></span>

```yaml
Type: System.Management.Automation.Job[]
Parameter Sets: JobParameterSet
Aliases:

Required: True
Position: 0
Default value: All jobs
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="50757-194">-Name</span><span class="sxs-lookup"><span data-stu-id="50757-194">-Name</span></span>

<span data-ttu-id="50757-195">Gibt die anzeigen Amen von Aufträgen an, die von diesem Cmdlet beendet werden.</span><span class="sxs-lookup"><span data-stu-id="50757-195">Specifies friendly names of jobs that this cmdlet stops.</span></span>
<span data-ttu-id="50757-196">Geben Sie die Auftragsnamen in eine kommagetrennte Liste ein, oder verwenden Sie Platzhalterzeichen (\*), um ein Auftragsnamensmuster einzugeben.</span><span class="sxs-lookup"><span data-stu-id="50757-196">Enter the job names in a comma-separated list or use wildcard characters (\*) to enter a job name pattern.</span></span>
<span data-ttu-id="50757-197">Standardmäßig beendet " **Stopp-Job** " alle Aufträge, die in der aktuellen Sitzung erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="50757-197">By default, **Stop-Job** stops all jobs created in the current session.</span></span>

<span data-ttu-id="50757-198">Da der Anzeige Name nicht unbedingt eindeutig ist, verwenden Sie die Parameter " *WhatIf* " und " *Confirm* ", wenn Sie Aufträge nach Namen beenden.</span><span class="sxs-lookup"><span data-stu-id="50757-198">Because the friendly name is not guaranteed to be unique, use the *WhatIf* and *Confirm* parameters when stopping jobs by name.</span></span>

```yaml
Type: System.String[]
Parameter Sets: NameParameterSet
Aliases:

Required: True
Position: 0
Default value: All jobs
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="50757-199">-PassThru</span><span class="sxs-lookup"><span data-stu-id="50757-199">-PassThru</span></span>

<span data-ttu-id="50757-200">Gibt ein Objekt zurück, das das Element darstellt, mit dem Sie arbeiten.</span><span class="sxs-lookup"><span data-stu-id="50757-200">Returns an object representing the item with which you are working.</span></span>
<span data-ttu-id="50757-201">Standardmäßig wird von diesem Cmdlet keine Ausgabe generiert.</span><span class="sxs-lookup"><span data-stu-id="50757-201">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="50757-202">-State</span><span class="sxs-lookup"><span data-stu-id="50757-202">-State</span></span>

<span data-ttu-id="50757-203">Gibt einen Auftragsstatus an.</span><span class="sxs-lookup"><span data-stu-id="50757-203">Specifies a job state.</span></span>
<span data-ttu-id="50757-204">Dieses Cmdlet beendet nur Aufträge im angegebenen Zustand.</span><span class="sxs-lookup"><span data-stu-id="50757-204">This cmdlet stops only jobs in the specified state.</span></span>
<span data-ttu-id="50757-205">Zulässige Werte für diesen Parameter:</span><span class="sxs-lookup"><span data-stu-id="50757-205">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="50757-206">NotStarted</span><span class="sxs-lookup"><span data-stu-id="50757-206">NotStarted</span></span>
- <span data-ttu-id="50757-207">Wird ausgeführt</span><span class="sxs-lookup"><span data-stu-id="50757-207">Running</span></span>
- <span data-ttu-id="50757-208">Abgeschlossen</span><span class="sxs-lookup"><span data-stu-id="50757-208">Completed</span></span>
- <span data-ttu-id="50757-209">Fehler</span><span class="sxs-lookup"><span data-stu-id="50757-209">Failed</span></span>
- <span data-ttu-id="50757-210">Beendet</span><span class="sxs-lookup"><span data-stu-id="50757-210">Stopped</span></span>
- <span data-ttu-id="50757-211">Blockiert</span><span class="sxs-lookup"><span data-stu-id="50757-211">Blocked</span></span>
- <span data-ttu-id="50757-212">Ausgesetzt</span><span class="sxs-lookup"><span data-stu-id="50757-212">Suspended</span></span>
- <span data-ttu-id="50757-213">Getrennt</span><span class="sxs-lookup"><span data-stu-id="50757-213">Disconnected</span></span>
- <span data-ttu-id="50757-214">Wird angehalten</span><span class="sxs-lookup"><span data-stu-id="50757-214">Suspending</span></span>
- <span data-ttu-id="50757-215">Wird beendet</span><span class="sxs-lookup"><span data-stu-id="50757-215">Stopping</span></span>

<span data-ttu-id="50757-216">Weitere Informationen zu Auftrags Zuständen finden Sie unter [jobstate-Enumeration](https://msdn.microsoft.com/library/system.management.automation.jobstate) in der MSDN Library.</span><span class="sxs-lookup"><span data-stu-id="50757-216">For more information about job states, see [JobState Enumeration](https://msdn.microsoft.com/library/system.management.automation.jobstate) in the MSDN library.</span></span>

```yaml
Type: System.Management.Automation.JobState
Parameter Sets: StateParameterSet
Aliases:
Accepted values: NotStarted, Running, Completed, Failed, Stopped, Blocked, Suspended, Disconnected, Suspending, Stopping, AtBreakpoint

Required: True
Position: 0
Default value: All jobs
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="50757-217">-Confirm</span><span class="sxs-lookup"><span data-stu-id="50757-217">-Confirm</span></span>

<span data-ttu-id="50757-218">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="50757-218">Prompts you for confirmation before running the cmdlet.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="50757-219">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="50757-219">-WhatIf</span></span>

<span data-ttu-id="50757-220">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="50757-220">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="50757-221">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="50757-221">The cmdlet is not run.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="50757-222">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="50757-222">CommonParameters</span></span>

<span data-ttu-id="50757-223">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="50757-223">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="50757-224">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="50757-224">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="50757-225">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="50757-225">INPUTS</span></span>

### <span data-ttu-id="50757-226">System. Management. Automation. remotingjob</span><span class="sxs-lookup"><span data-stu-id="50757-226">System.Management.Automation.RemotingJob</span></span>

<span data-ttu-id="50757-227">Sie können ein Auftrags Objekt an dieses Cmdlet weiterreichen.</span><span class="sxs-lookup"><span data-stu-id="50757-227">You can pipe a job object to this cmdlet.</span></span>

## <span data-ttu-id="50757-228">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="50757-228">OUTPUTS</span></span>

### <span data-ttu-id="50757-229">None, System. Management. Automation. psremotingjob</span><span class="sxs-lookup"><span data-stu-id="50757-229">None, System.Management.Automation.PSRemotingJob</span></span>

<span data-ttu-id="50757-230">Dieses Cmdlet gibt ein Auftrags Objekt zurück, wenn Sie den *passthru* -Parameter angeben.</span><span class="sxs-lookup"><span data-stu-id="50757-230">This cmdlet returns a job object, if you specify the *PassThru* parameter.</span></span>
<span data-ttu-id="50757-231">Andernfalls wird von diesem Cmdlet keine Ausgabe generiert.</span><span class="sxs-lookup"><span data-stu-id="50757-231">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="50757-232">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="50757-232">NOTES</span></span>

## <span data-ttu-id="50757-233">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="50757-233">RELATED LINKS</span></span>

[<span data-ttu-id="50757-234">Get-Job</span><span class="sxs-lookup"><span data-stu-id="50757-234">Get-Job</span></span>](Get-Job.md)

[<span data-ttu-id="50757-235">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="50757-235">Invoke-Command</span></span>](Invoke-Command.md)

[<span data-ttu-id="50757-236">Receive-Job</span><span class="sxs-lookup"><span data-stu-id="50757-236">Receive-Job</span></span>](Receive-Job.md)

[<span data-ttu-id="50757-237">Remove-Job</span><span class="sxs-lookup"><span data-stu-id="50757-237">Remove-Job</span></span>](Remove-Job.md)

[<span data-ttu-id="50757-238">Start-Job</span><span class="sxs-lookup"><span data-stu-id="50757-238">Start-Job</span></span>](Start-Job.md)

[<span data-ttu-id="50757-239">Wait-Job</span><span class="sxs-lookup"><span data-stu-id="50757-239">Wait-Job</span></span>](Wait-Job.md)

[<span data-ttu-id="50757-240">about_Job_Details</span><span class="sxs-lookup"><span data-stu-id="50757-240">about_Job_Details</span></span>](About/about_Job_Details.md)

[<span data-ttu-id="50757-241">about_Remote_Jobs</span><span class="sxs-lookup"><span data-stu-id="50757-241">about_Remote_Jobs</span></span>](About/about_Remote_Jobs.md)

[<span data-ttu-id="50757-242">about_Remote_Variables</span><span class="sxs-lookup"><span data-stu-id="50757-242">about_Remote_Variables</span></span>](About/about_Remote_Variables.md)

[<span data-ttu-id="50757-243">about_Jobs</span><span class="sxs-lookup"><span data-stu-id="50757-243">about_Jobs</span></span>](About/about_Jobs.md)

[<span data-ttu-id="50757-244">about_Scopes</span><span class="sxs-lookup"><span data-stu-id="50757-244">about_Scopes</span></span>](About/about_scopes.md)