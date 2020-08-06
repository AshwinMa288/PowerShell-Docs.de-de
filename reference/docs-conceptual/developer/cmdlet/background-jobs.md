---
title: Hintergrund Aufträge | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: 2a1297b8dfe087474564078cca2a5a0526ed0f36
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87774846"
---
# <a name="background-jobs"></a><span data-ttu-id="f2854-102">Hintergrundaufträge</span><span class="sxs-lookup"><span data-stu-id="f2854-102">Background Jobs</span></span>

<span data-ttu-id="f2854-103">Cmdlets können Ihre Aktion intern oder als Windows PowerShell-*Hintergrund Auftrag*ausführen.</span><span class="sxs-lookup"><span data-stu-id="f2854-103">Cmdlets can perform their action internally or as a Windows PowerShell*background job*.</span></span> <span data-ttu-id="f2854-104">Wenn ein Cmdlet als Hintergrund Auftrag ausgeführt wird, wird die Arbeit asynchron in einem eigenen Thread ausgeführt, getrennt vom Pipeline Thread, der vom Cmdlet verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="f2854-104">When a cmdlet runs as a background job, the work is done asynchronously in its own thread separate from the pipeline thread that the cmdlet is using.</span></span> <span data-ttu-id="f2854-105">Aus Sicht des Benutzers, wenn ein Cmdlet als Hintergrund Auftrag ausgeführt wird, wird die Eingabeaufforderung sofort zurückgegeben, auch wenn die Ausführung des Auftrags längere Zeit in Anspruch nimmt und der Benutzer ohne Unterbrechung fortfahren kann, während der Auftrag ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="f2854-105">From the user perspective, when a cmdlet runs as a background job, the command prompt returns immediately even if the job takes an extended amount of time to complete, and the user can continue without interruption while the job runs.</span></span>

## <a name="background-jobs-child-jobs-and-the-job-repository"></a><span data-ttu-id="f2854-106">Hintergrund Aufträge, untergeordnete Aufträge und das auftragsrepository</span><span class="sxs-lookup"><span data-stu-id="f2854-106">Background Jobs, Child Jobs, and the Job Repository</span></span>

<span data-ttu-id="f2854-107">Das Auftrags Objekt, das von den Cmdlets zurückgegeben wird, die Hintergrund Aufträge unterstützen, definiert den Auftrag.</span><span class="sxs-lookup"><span data-stu-id="f2854-107">The job object that is returned by the cmdlets that support background jobs defines the job.</span></span> <span data-ttu-id="f2854-108">(Das [Start-Job-](/powershell/module/Microsoft.PowerShell.Core/Start-Job) Cmdlet gibt auch ein Auftrags Objekt zurück.) Der Name des Auftrags, ein Bezeichner, der verwendet wird, um den Auftrag, die Zustandsinformationen und die untergeordneten Aufträge anzugeben, sind in dieser Definition enthalten.</span><span class="sxs-lookup"><span data-stu-id="f2854-108">(The [Start-Job](/powershell/module/Microsoft.PowerShell.Core/Start-Job) cmdlet also returns a job object.) The name of the job, an identifier that is used to specify the job, the state information, and the child jobs are included in this definition.</span></span> <span data-ttu-id="f2854-109">Der Auftrag führt keine der Arbeit aus.</span><span class="sxs-lookup"><span data-stu-id="f2854-109">The job does not perform any of the work.</span></span> <span data-ttu-id="f2854-110">Jeder Hintergrund Auftrag hat mindestens einen untergeordneten Auftrag, da der untergeordnete Auftrag die tatsächliche Arbeit ausführt.</span><span class="sxs-lookup"><span data-stu-id="f2854-110">Each background job has at least one child job because the child job performs the actual work.</span></span> <span data-ttu-id="f2854-111">Wenn Sie ein Cmdlet ausführen, sodass die Arbeit als Hintergrund Auftrag ausgeführt wird, muss das Cmdlet den Auftrag und die untergeordneten Aufträge einem gemeinsamen Repository hinzufügen, das als *auftragsrepository*bezeichnet wird.</span><span class="sxs-lookup"><span data-stu-id="f2854-111">When you run a cmdlet so that the work is performed as a background job, the cmdlet must add the job and the child jobs to a common repository, referred to as the *job repository*.</span></span>

<span data-ttu-id="f2854-112">Weitere Informationen zur Verarbeitung von Hintergrund Aufträgen in der Befehlszeile finden Sie in den folgenden Bereichen:</span><span class="sxs-lookup"><span data-stu-id="f2854-112">For more information about how background jobs are handled at the command line, see the following:</span></span>

- [<span data-ttu-id="f2854-113">about_Jobs</span><span class="sxs-lookup"><span data-stu-id="f2854-113">about_Jobs</span></span>](/powershell/module/microsoft.powershell.core/about/about_jobs)

- [<span data-ttu-id="f2854-114">about_Job_Details</span><span class="sxs-lookup"><span data-stu-id="f2854-114">about_Job_Details</span></span>](/powershell/module/microsoft.powershell.core/about/about_job_details)

- [<span data-ttu-id="f2854-115">about_Remote_Jobs</span><span class="sxs-lookup"><span data-stu-id="f2854-115">about_Remote_Jobs</span></span>](/powershell/module/microsoft.powershell.core/about/about_remote_jobs)

## <a name="writing-a-cmdlet-that-runs-as-a-background-job"></a><span data-ttu-id="f2854-116">Schreiben eines Cmdlets, das als Hintergrund Auftrag ausgeführt wird</span><span class="sxs-lookup"><span data-stu-id="f2854-116">Writing a Cmdlet That Runs as a Background Job</span></span>

<span data-ttu-id="f2854-117">Zum Schreiben eines Cmdlets, das als Hintergrund Auftrag ausgeführt werden kann, müssen Sie die folgenden Aufgaben ausführen:</span><span class="sxs-lookup"><span data-stu-id="f2854-117">To write a cmdlet that can be run as a background job, you must complete the following tasks:</span></span>

- <span data-ttu-id="f2854-118">Definieren `asJob` Sie einen Switch-Parameter, sodass der Benutzer entscheiden kann, ob das Cmdlet als Hintergrund Auftrag ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="f2854-118">Define an `asJob` switch parameter so that the user can decide whether to run the cmdlet as a background job.</span></span>

- <span data-ttu-id="f2854-119">Erstellen Sie ein Objekt, das von der [System. Management. Automation. Job](/dotnet/api/System.Management.Automation.Job) -Klasse abgeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="f2854-119">Create an object that derives from the [System.Management.Automation.Job](/dotnet/api/System.Management.Automation.Job) class.</span></span> <span data-ttu-id="f2854-120">Bei diesem Objekt kann es sich um ein benutzerdefiniertes Auftrags Objekt oder ein von Windows PowerShell bereitgestelltes Auftrags Objekt handeln, z. b. ein [System. Management. Automation. psiebziger Job](/dotnet/api/System.Management.Automation.PSEventJob) -Objekt.</span><span class="sxs-lookup"><span data-stu-id="f2854-120">This object can be a custom job object or a job object provided by Windows PowerShell, such as a [System.Management.Automation.Pseventjob](/dotnet/api/System.Management.Automation.PSEventJob) object.</span></span>

- <span data-ttu-id="f2854-121">Fügen Sie in einer Daten Satz Verarbeitungsmethode eine- `if` Anweisung hinzu, die erkennt, ob das Cmdlet als Hintergrund Auftrag ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="f2854-121">In a record processing method, add an `if` statement that detects whether the cmdlet should run as a background job.</span></span>

- <span data-ttu-id="f2854-122">Implementieren Sie für benutzerdefinierte Auftrags Objekte die Job-Klasse.</span><span class="sxs-lookup"><span data-stu-id="f2854-122">For custom job objects, implement the job class.</span></span>

- <span data-ttu-id="f2854-123">Gibt die entsprechenden Objekte zurück, je nachdem, ob das Cmdlet als Hintergrund Auftrag ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="f2854-123">Return the appropriate objects, depending on whether the cmdlet is run as a background job.</span></span>

<span data-ttu-id="f2854-124">Ein Codebeispiel finden [Sie unter How to Support Jobs](./how-to-support-jobs.md).</span><span class="sxs-lookup"><span data-stu-id="f2854-124">For a code example, see [How to Support Jobs](./how-to-support-jobs.md).</span></span>

## <a name="background-job-related-apis"></a><span data-ttu-id="f2854-125">Im Hintergrund für Aufträge relevante APIs</span><span class="sxs-lookup"><span data-stu-id="f2854-125">Background Job-Related APIs</span></span>

<span data-ttu-id="f2854-126">Die folgenden APIs werden von Windows PowerShell zur Verwaltung von Hintergrund Aufträgen bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="f2854-126">The following APIs are provided by Windows PowerShell to manage background jobs.</span></span>

<span data-ttu-id="f2854-127">[System. Management. Automation. Job](/dotnet/api/System.Management.Automation.Job) leitet benutzerdefinierte Auftrags Objekte ab.</span><span class="sxs-lookup"><span data-stu-id="f2854-127">[System.Management.Automation.Job](/dotnet/api/System.Management.Automation.Job) Derives custom job objects.</span></span> <span data-ttu-id="f2854-128">Dies ist eine abstrakte Klasse.</span><span class="sxs-lookup"><span data-stu-id="f2854-128">This is an abstract class.</span></span>

<span data-ttu-id="f2854-129">[System. Management. Automation. jobrepository](/dotnet/api/System.Management.Automation.JobRepository) verwaltet und stellt Informationen über die aktuellen aktiven Hintergrund Aufträge bereit.</span><span class="sxs-lookup"><span data-stu-id="f2854-129">[System.Management.Automation.Jobrepository](/dotnet/api/System.Management.Automation.JobRepository) Manages and provides information about the current active background jobs.</span></span>

<span data-ttu-id="f2854-130">[System. Management. Automation. jobstate](/dotnet/api/System.Management.Automation.JobState) definiert den Status des Hintergrund Auftrags.</span><span class="sxs-lookup"><span data-stu-id="f2854-130">[System.Management.Automation.Jobstate](/dotnet/api/System.Management.Automation.JobState) Defines the state of the background job.</span></span> <span data-ttu-id="f2854-131">Zu den Zuständen zählen Started, Running und beendet.</span><span class="sxs-lookup"><span data-stu-id="f2854-131">States include Started, Running, and Stopped.</span></span>

<span data-ttu-id="f2854-132">[System. Management. Automation. jobstateinfo](/dotnet/api/System.Management.Automation.JobStateInfo) stellt Informationen über den Status eines Hintergrund Auftrags bereit und, wenn die letzte Zustandsänderung durch einen Fehler verursacht wurde, den Grund für den aktuellen Status des Auftrags.</span><span class="sxs-lookup"><span data-stu-id="f2854-132">[System.Management.Automation.Jobstateinfo](/dotnet/api/System.Management.Automation.JobStateInfo) Provides information about the state of a background job and, if the last state change was caused by an error, the reason the job entered its current state.</span></span>

<span data-ttu-id="f2854-133">[System. Management. Automation. jobstateeventargs](/dotnet/api/System.Management.Automation.JobStateEventArgs) stellt die Argumente für ein Ereignis bereit, das ausgelöst wird, wenn sich der Zustand eines Hintergrund Auftrags ändert.</span><span class="sxs-lookup"><span data-stu-id="f2854-133">[System.Management.Automation.Jobstateeventargs](/dotnet/api/System.Management.Automation.JobStateEventArgs) Provides the arguments for an event that is raised when a background job changes state.</span></span>

## <a name="windows-powershell-job-cmdlets"></a><span data-ttu-id="f2854-134">Windows PowerShell-Auftrags-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="f2854-134">Windows PowerShell Job Cmdlets</span></span>

<span data-ttu-id="f2854-135">Die folgenden Cmdlets werden von Windows PowerShell zur Verwaltung von Hintergrund Aufträgen bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="f2854-135">The following cmdlets are provided by Windows PowerShell to manage background jobs.</span></span>

[<span data-ttu-id="f2854-136">Get-Job</span><span class="sxs-lookup"><span data-stu-id="f2854-136">Get-Job</span></span>](/powershell/module/Microsoft.PowerShell.Core/Get-Job)

<span data-ttu-id="f2854-137">Ruft Windows PowerShell-Hintergrundaufträge ab, die in der aktuellen Sitzung ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="f2854-137">Gets Windows PowerShell background jobs that are running in the current session.</span></span>

[<span data-ttu-id="f2854-138">Receive-Job</span><span class="sxs-lookup"><span data-stu-id="f2854-138">Receive-Job</span></span>](/powershell/module/Microsoft.PowerShell.Core/Receive-Job)

<span data-ttu-id="f2854-139">Ruft die Ergebnisse der Windows PowerShell-Hintergrundaufträge in der aktuellen Sitzung ab.</span><span class="sxs-lookup"><span data-stu-id="f2854-139">Gets the results of the Windows PowerShell background jobs in the current session.</span></span>

[<span data-ttu-id="f2854-140">Remove-Job</span><span class="sxs-lookup"><span data-stu-id="f2854-140">Remove-Job</span></span>](/powershell/module/Microsoft.PowerShell.Core/Remove-Job)

<span data-ttu-id="f2854-141">Löscht einen Windows PowerShell-Hintergrundauftrag.</span><span class="sxs-lookup"><span data-stu-id="f2854-141">Deletes a Windows PowerShell background job.</span></span>

[<span data-ttu-id="f2854-142">Start-Job</span><span class="sxs-lookup"><span data-stu-id="f2854-142">Start-Job</span></span>](/powershell/module/Microsoft.PowerShell.Core/Start-Job)

<span data-ttu-id="f2854-143">Startet einen Windows PowerShell-Hintergrundauftrag.</span><span class="sxs-lookup"><span data-stu-id="f2854-143">Starts a Windows PowerShell background job.</span></span>

[<span data-ttu-id="f2854-144">Stop-Job</span><span class="sxs-lookup"><span data-stu-id="f2854-144">Stop-Job</span></span>](/powershell/module/Microsoft.PowerShell.Core/Stop-Job)

<span data-ttu-id="f2854-145">Beendet einen Windows PowerShell-Hintergrundauftrag.</span><span class="sxs-lookup"><span data-stu-id="f2854-145">Stops a Windows PowerShell background job.</span></span>

[<span data-ttu-id="f2854-146">Wait-Job</span><span class="sxs-lookup"><span data-stu-id="f2854-146">Wait-Job</span></span>](/powershell/module/Microsoft.PowerShell.Core/Wait-Job)

<span data-ttu-id="f2854-147">Unterdrückt die Eingabeaufforderung, bis ein oder alle der in der Sitzung ausgeführten Windows PowerShell-Hintergrundaufträge abgeschlossen sind.</span><span class="sxs-lookup"><span data-stu-id="f2854-147">Suppresses the command prompt until one or all of the Windows PowerShell background jobs running in the session are complete.</span></span>

## <a name="see-also"></a><span data-ttu-id="f2854-148">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f2854-148">See Also</span></span>

[<span data-ttu-id="f2854-149">Schreiben eines Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="f2854-149">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
