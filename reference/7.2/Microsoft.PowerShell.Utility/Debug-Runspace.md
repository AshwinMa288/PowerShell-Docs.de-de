---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/debug-runspace?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Debug-Runspace
ms.openlocfilehash: 3f01b7624ffcbca472b09bdb83a7440f3526db43
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99600495"
---
# <span data-ttu-id="cea34-102">Debug-Runspace</span><span class="sxs-lookup"><span data-stu-id="cea34-102">Debug-Runspace</span></span>

## <span data-ttu-id="cea34-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="cea34-103">SYNOPSIS</span></span>
<span data-ttu-id="cea34-104">Startet eine interaktive Debugsitzung mit einem Runspace.</span><span class="sxs-lookup"><span data-stu-id="cea34-104">Starts an interactive debugging session with a runspace.</span></span>

## <span data-ttu-id="cea34-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="cea34-105">SYNTAX</span></span>

### <span data-ttu-id="cea34-106">Runspaceparameterset (Standard)</span><span class="sxs-lookup"><span data-stu-id="cea34-106">RunspaceParameterSet (Default)</span></span>

```
Debug-Runspace [-Runspace] <Runspace> [-BreakAll] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="cea34-107">Nameparameterset</span><span class="sxs-lookup"><span data-stu-id="cea34-107">NameParameterSet</span></span>

```
Debug-Runspace [-Name] <String> [-BreakAll] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="cea34-108">Idparameterset</span><span class="sxs-lookup"><span data-stu-id="cea34-108">IdParameterSet</span></span>

```
Debug-Runspace [-Id] <Int32> [-BreakAll] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="cea34-109">Instanceidparameterset</span><span class="sxs-lookup"><span data-stu-id="cea34-109">InstanceIdParameterSet</span></span>

```
Debug-Runspace [-InstanceId] <Guid> [-BreakAll] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="cea34-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="cea34-110">DESCRIPTION</span></span>

<span data-ttu-id="cea34-111">Mit dem- `Debug-Runspace` Cmdlet wird eine interaktive Debugsitzung mit einem lokalen oder aktiven Remote-Runspace gestartet.</span><span class="sxs-lookup"><span data-stu-id="cea34-111">The `Debug-Runspace` cmdlet starts an interactive debugging session with a local or remote active runspace.</span></span> <span data-ttu-id="cea34-112">Sie finden einen Runspace, den Sie debuggen möchten, indem Sie zuerst ausführen, `Get-Process` um Prozesse zu suchen, die mit PowerShell verknüpft sind, dann `Enter-PSHostProcess` mit der im **ID** -Parameter angegebenen Prozess-ID, die an den Prozess angehängt werden soll, und dann `Get-Runspace` Runspaces im PowerShell-Host Prozess auflisten.</span><span class="sxs-lookup"><span data-stu-id="cea34-112">You can find a runspace that you want to debug by first running `Get-Process` to find processes associated with PowerShell, then `Enter-PSHostProcess` with the process ID specified in the **Id** parameter to attach to the process, and then `Get-Runspace` to list runspaces within the PowerShell host process.</span></span>

<span data-ttu-id="cea34-113">Wenn Sie einen Runspace zum Debuggen ausgewählt haben und der Runspace aktuell einen Befehl oder ein Skript ausgeführt oder das Skript an einem Haltepunkt angehalten wurde, öffnet PowerShell eine Remotedebugsitzung für den Runspace.</span><span class="sxs-lookup"><span data-stu-id="cea34-113">After you have selected a runspace to debug, if the runspace is currently running a command or script, or if the script has stopped at a breakpoint, PowerShell opens a remote debugger session for the runspace.</span></span> <span data-ttu-id="cea34-114">Sie können das Runspace-Skript genauso Debuggen, wie Remote Sitzungs Skripts debuggt werden.</span><span class="sxs-lookup"><span data-stu-id="cea34-114">You can debug the runspace script in the same way remote session scripts are debugged.</span></span>

<span data-ttu-id="cea34-115">Sie können nur an einen PowerShell-Host Prozess angefügt werden, wenn Sie ein Administrator auf dem Computer sind, auf dem der Prozess ausgeführt wird, oder wenn Sie das Skript ausführen, das Sie debuggen möchten.</span><span class="sxs-lookup"><span data-stu-id="cea34-115">You can only attach to a PowerShell host process if you are an administrator on the computer that is running the process, or you are running the script that you want to debug.</span></span> <span data-ttu-id="cea34-116">Außerdem ist es nicht möglich, den Host Prozess einzugeben, von dem die aktuelle PowerShell-Sitzung ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="cea34-116">Also, you cannot enter the host process that is running the current PowerShell session.</span></span> <span data-ttu-id="cea34-117">Sie können nur einen Host Prozess eingeben, der eine andere PowerShell-Sitzung ausgeführt hat.</span><span class="sxs-lookup"><span data-stu-id="cea34-117">You can only enter a host process that is running a different PowerShell session.</span></span>

## <span data-ttu-id="cea34-118">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="cea34-118">EXAMPLES</span></span>

### <span data-ttu-id="cea34-119">Beispiel 1: Debuggen eines Remoterunspace</span><span class="sxs-lookup"><span data-stu-id="cea34-119">Example 1: Debug a remote runspace</span></span>

```
PS C:\> Get-Process -ComputerName "WS10TestServer" -Name "*powershell*"

Handles      WS(K)   VM(M)      CPU(s)    Id  ProcessName
-------      -----   -----      ------    --  -----------
    377      69912     63     2.09      2420  powershell
    399     123396    829     4.48      1152  powershell_ise

PS C:\> Enter-PSSession -ComputerName "WS10TestServer"
[WS10TestServer]:PS C:\> Enter-PSHostProcess -Id 1152
[WS10TestServer:][Process:1152]: PS C:\Users\Test\Documents> Get-Runspace

Id Name            ComputerName    Type          State         Availability
-- ----            ------------    ----          -----         ------------
 1 Runspace1       WS10TestServer  Remote        Opened        Available
 2 RemoteHost      WS10TestServer  Remote        Opened        Busy

PS C:\> [WS10TestServer][Process:1152]: PS C:\Users\Test\Documents> Debug-Runspace -Id 2

Hit Line breakpoint on 'C:\TestWFVar1.ps1:83'
At C:\TestWFVar1.ps1:83 char:1
+ $scriptVar = "Script Variable"
+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
[Process:1152]: [RSDBG: 2]: PS C:\> >
```

<span data-ttu-id="cea34-120">In diesem Beispiel Debuggen Sie einen Runspace, der auf einem Remote Computer geöffnet ist, WS10TestServer.</span><span class="sxs-lookup"><span data-stu-id="cea34-120">In this example, you debug a runspace that is open on a remote computer, WS10TestServer.</span></span> <span data-ttu-id="cea34-121">In der ersten Zeile des Befehls führen Sie `Get-Process` auf dem Remote Computer aus und Filtern nach Windows PowerShell-Host Prozessen.</span><span class="sxs-lookup"><span data-stu-id="cea34-121">In the first line of the command, you run `Get-Process` on the remote computer, and filter for Windows PowerShell host processes.</span></span> <span data-ttu-id="cea34-122">In diesem Beispiel möchten Sie die Prozess-ID 1152, den Windows PowerShell ISE Host Prozess Debuggen.</span><span class="sxs-lookup"><span data-stu-id="cea34-122">In this example, you want to debug process ID 1152, the Windows PowerShell ISE host process.</span></span>

<span data-ttu-id="cea34-123">Im zweiten Befehl führen Sie aus, `Enter-PSSession` um eine Remote Sitzung auf WS10TestServer zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="cea34-123">In the second command, you run `Enter-PSSession` to open a remote session on WS10TestServer.</span></span> <span data-ttu-id="cea34-124">Im dritten Befehl fügen Sie an den Windows PowerShell ISE Host Prozess an, der auf dem Remote Server ausgeführt wird, indem Sie Ausführen `Enter-PSHostProcess` und die ID des Host Prozesses angeben, den Sie im ersten Befehl abgerufen haben, 1152.</span><span class="sxs-lookup"><span data-stu-id="cea34-124">In the third command, you attach to the Windows PowerShell ISE host process running on the remote server by running `Enter-PSHostProcess`, and specifying the ID of the host process that you obtained in the first command, 1152.</span></span>

<span data-ttu-id="cea34-125">Im vierten Befehl Listen Sie verfügbare Runspaces für Prozess-ID 1152 auf, indem Sie Ausführen `Get-Runspace` .</span><span class="sxs-lookup"><span data-stu-id="cea34-125">In the fourth command, you list available runspaces for process ID 1152 by running `Get-Runspace`.</span></span>
<span data-ttu-id="cea34-126">Notieren Sie sich die ID des ausgelasteten Runspace. Es wird ein Skript ausgeführt, das Sie debuggen möchten.</span><span class="sxs-lookup"><span data-stu-id="cea34-126">You note the ID number of the Busy runspace; it is running a script that you want to debug.</span></span>

<span data-ttu-id="cea34-127">Im letzten Befehl haben Sie mit dem Debuggen eines geöffneten Runspace begonnen, von dem ein Skript ausgeführt wird, TestWFVar1.ps1, indem ausgeführt `Debug-Runspace` wird und der Runspace mit der ID 2 identifiziert wird, indem der **ID** -Parameter hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="cea34-127">In the last command, you start debugging an opened runspace that is running a script, TestWFVar1.ps1, by running `Debug-Runspace`, and identifying the runspace by its ID, 2, by adding the **Id** parameter.</span></span> <span data-ttu-id="cea34-128">Da es im Skript einen Haltepunkt gibt, wird der Debugger geöffnet.</span><span class="sxs-lookup"><span data-stu-id="cea34-128">Because there's a breakpoint in the script, the debugger opens.</span></span>

## <span data-ttu-id="cea34-129">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="cea34-129">PARAMETERS</span></span>

### <span data-ttu-id="cea34-130">-Id</span><span class="sxs-lookup"><span data-stu-id="cea34-130">-Id</span></span>

<span data-ttu-id="cea34-131">Gibt die ID-Nummer eines Runspace an.</span><span class="sxs-lookup"><span data-stu-id="cea34-131">Specifies the ID number of a runspace.</span></span> <span data-ttu-id="cea34-132">Sie können ausführen `Get-Runspace` , um Runspace-IDs anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="cea34-132">You can run `Get-Runspace` to show runspace IDs.</span></span>

```yaml
Type: System.Int32
Parameter Sets: IdParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="cea34-133">-InstanceId</span><span class="sxs-lookup"><span data-stu-id="cea34-133">-InstanceId</span></span>

<span data-ttu-id="cea34-134">Gibt einen Runspace durch die Instanz-ID an, eine GUID, die Sie anzeigen können, indem Sie Ausführen `Get-Runspace` .</span><span class="sxs-lookup"><span data-stu-id="cea34-134">Specifies a runspace by its instance ID, a GUID that you can show by running `Get-Runspace`.</span></span>

```yaml
Type: System.Guid
Parameter Sets: InstanceIdParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="cea34-135">-Name</span><span class="sxs-lookup"><span data-stu-id="cea34-135">-Name</span></span>

<span data-ttu-id="cea34-136">Gibt einen Runspace anhand seines Namens an.</span><span class="sxs-lookup"><span data-stu-id="cea34-136">Specifies a runspace by its name.</span></span> <span data-ttu-id="cea34-137">Sie können ausführen `Get-Runspace` , um die Namen der Runspaces anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="cea34-137">You can run `Get-Runspace` to show the names of runspaces.</span></span>

```yaml
Type: System.String
Parameter Sets: NameParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="cea34-138">-Runspace</span><span class="sxs-lookup"><span data-stu-id="cea34-138">-Runspace</span></span>

<span data-ttu-id="cea34-139">Gibt ein Runspace-Objekt an.</span><span class="sxs-lookup"><span data-stu-id="cea34-139">Specifies a runspace object.</span></span> <span data-ttu-id="cea34-140">Die einfachste Möglichkeit, einen Wert für diesen Parameter anzugeben, besteht darin, eine Variable anzugeben, die die Ergebnisse eines gefilterten `Get-Runspace` Befehls enthält.</span><span class="sxs-lookup"><span data-stu-id="cea34-140">The simplest way to provide a value for this parameter is to specify a variable that contains the results of a filtered `Get-Runspace` command.</span></span>

```yaml
Type: System.Management.Automation.Runspaces.Runspace
Parameter Sets: RunspaceParameterSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="cea34-141">-Confirm</span><span class="sxs-lookup"><span data-stu-id="cea34-141">-Confirm</span></span>

<span data-ttu-id="cea34-142">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="cea34-142">Prompts you for confirmation before running the cmdlet.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: True
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="cea34-143">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="cea34-143">-WhatIf</span></span>

<span data-ttu-id="cea34-144">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="cea34-144">Shows what would happen if the cmdlet runs.</span></span> <span data-ttu-id="cea34-145">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="cea34-145">The cmdlet is not run.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: True
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="cea34-146">-Breakall</span><span class="sxs-lookup"><span data-stu-id="cea34-146">-BreakAll</span></span>

<span data-ttu-id="cea34-147">{{Breakall-Beschreibung ausfüllen}}</span><span class="sxs-lookup"><span data-stu-id="cea34-147">{{ Fill BreakAll Description }}</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="cea34-148">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="cea34-148">CommonParameters</span></span>

<span data-ttu-id="cea34-149">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="cea34-149">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="cea34-150">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="cea34-150">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="cea34-151">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="cea34-151">INPUTS</span></span>

### <span data-ttu-id="cea34-152">System. Management. Automation. Runspaces. Runspace</span><span class="sxs-lookup"><span data-stu-id="cea34-152">System.Management.Automation.Runspaces.Runspace</span></span>

<span data-ttu-id="cea34-153">Sie können die Ergebnisse eines Befehls über die Pipeline `Get-Runspace` an **Debug-Runspace übergeben.**</span><span class="sxs-lookup"><span data-stu-id="cea34-153">You can pipe the results of a `Get-Runspace` command to **Debug-Runspace.**</span></span>

## <span data-ttu-id="cea34-154">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="cea34-154">OUTPUTS</span></span>

## <span data-ttu-id="cea34-155">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="cea34-155">NOTES</span></span>

<span data-ttu-id="cea34-156">`Debug-Runspace` funktioniert für Runspaces, die sich im geöffneten Zustand befinden.</span><span class="sxs-lookup"><span data-stu-id="cea34-156">`Debug-Runspace` works on runspaces that are in the Opened state.</span></span> <span data-ttu-id="cea34-157">Wenn sich der Zustand eines Runspace von geöffnet in einen anderen Status ändert, wird der Runspace automatisch aus der Liste wird ausgeführt entfernt.</span><span class="sxs-lookup"><span data-stu-id="cea34-157">If a runspace state changes from Opened to another state, that runspace is automatically removed from the running list.</span></span> <span data-ttu-id="cea34-158">Der Liste wird nur dann ein Runspace hinzugefügt, wenn die folgenden Kriterien erfüllt sind.</span><span class="sxs-lookup"><span data-stu-id="cea34-158">A runspace is added to the running list only if it meets the following criteria.</span></span>

- <span data-ttu-id="cea34-159">Wenn Sie von "aufrufen-Command;" stammt. Das heißt, Sie verfügt über eine `Invoke-Command` GUID-ID.</span><span class="sxs-lookup"><span data-stu-id="cea34-159">If it is coming from Invoke-Command; that is, it has an `Invoke-Command` GUID ID.</span></span>
- <span data-ttu-id="cea34-160">Wenn Sie von stammt, d `Debug-Runspace` . h., Sie verfügt über eine `Debug-Runspace` GUID-ID.</span><span class="sxs-lookup"><span data-stu-id="cea34-160">If it is coming from `Debug-Runspace`; that is, it has a `Debug-Runspace` GUID ID.</span></span>
- <span data-ttu-id="cea34-161">Wenn Sie von einem PowerShell-Workflow stammt, und die zugehörige Workflow Auftrags-ID mit der aktuellen aktiven Debugger-Workflow Auftrags-ID übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="cea34-161">If it is coming from a PowerShell workflow, and its workflow job ID is the same as the current active debugger workflow job ID.</span></span>

## <span data-ttu-id="cea34-162">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="cea34-162">RELATED LINKS</span></span>

[<span data-ttu-id="cea34-163">about_Debuggers</span><span class="sxs-lookup"><span data-stu-id="cea34-163">about_Debuggers</span></span>](../Microsoft.PowerShell.Core/About/about_Debuggers.md)

[<span data-ttu-id="cea34-164">Debug-Job</span><span class="sxs-lookup"><span data-stu-id="cea34-164">Debug-Job</span></span>](../Microsoft.PowerShell.Core/Debug-Job.md)

[<span data-ttu-id="cea34-165">Get-Runspace</span><span class="sxs-lookup"><span data-stu-id="cea34-165">Get-Runspace</span></span>](Get-Runspace.md)

[<span data-ttu-id="cea34-166">Get-Process</span><span class="sxs-lookup"><span data-stu-id="cea34-166">Get-Process</span></span>](../Microsoft.PowerShell.Management/Get-Process.md)

[<span data-ttu-id="cea34-167">Enter-PSHostProcess</span><span class="sxs-lookup"><span data-stu-id="cea34-167">Enter-PSHostProcess</span></span>](../Microsoft.PowerShell.Core/Enter-PSHostProcess.md)

[<span data-ttu-id="cea34-168">Enter-PSSession</span><span class="sxs-lookup"><span data-stu-id="cea34-168">Enter-PSSession</span></span>](../Microsoft.PowerShell.Core/Enter-PSSession.md)
