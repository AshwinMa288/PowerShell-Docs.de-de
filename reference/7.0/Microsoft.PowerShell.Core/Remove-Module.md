---
external help file: System.Management.Automation.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/remove-module?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-Module
ms.openlocfilehash: b8577db1d44f0e7bd4571a080133fecaa282770b
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2020
ms.locfileid: "93210391"
---
# <span data-ttu-id="d4d83-103">Remove-Module</span><span class="sxs-lookup"><span data-stu-id="d4d83-103">Remove-Module</span></span>

## <span data-ttu-id="d4d83-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="d4d83-104">SYNOPSIS</span></span>
<span data-ttu-id="d4d83-105">Entfernt Module aus der aktuellen Sitzung.</span><span class="sxs-lookup"><span data-stu-id="d4d83-105">Removes modules from the current session.</span></span>

## <span data-ttu-id="d4d83-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="d4d83-106">SYNTAX</span></span>

### <span data-ttu-id="d4d83-107">name</span><span class="sxs-lookup"><span data-stu-id="d4d83-107">name</span></span>

```
Remove-Module [-Name] <String[]> [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="d4d83-108">FullyQualifiedName</span><span class="sxs-lookup"><span data-stu-id="d4d83-108">FullyQualifiedName</span></span>

```
Remove-Module [-FullyQualifiedName] <ModuleSpecification[]> [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="d4d83-109">ModuleInfo</span><span class="sxs-lookup"><span data-stu-id="d4d83-109">ModuleInfo</span></span>

```
Remove-Module [-ModuleInfo] <PSModuleInfo[]> [-Force] [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="d4d83-110">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="d4d83-110">DESCRIPTION</span></span>

<span data-ttu-id="d4d83-111">Das **Remove-Module** -Cmdlet entfernt die Elemente eines Moduls, wie z. B. Cmdlets und Funktionen, aus der aktuellen Sitzung.</span><span class="sxs-lookup"><span data-stu-id="d4d83-111">The **Remove-Module** cmdlet removes the members of a module, such as cmdlets and functions, from the current session.</span></span>

<span data-ttu-id="d4d83-112">Wenn das Modul eine Assembly (.dll) enthält, werden alle Elemente entfernt, die von der Assembly implementiert werden, die Assembly wird jedoch nicht entladen.</span><span class="sxs-lookup"><span data-stu-id="d4d83-112">If the module includes an assembly (.dll), all members that are implemented by the assembly are removed, but the assembly is not unloaded.</span></span>

<span data-ttu-id="d4d83-113">Mit diesem Cmdlet wird das Modul nicht deinstalliert oder vom Computer gelöscht.</span><span class="sxs-lookup"><span data-stu-id="d4d83-113">This cmdlet does not uninstall the module or delete it from the computer.</span></span>
<span data-ttu-id="d4d83-114">Er wirkt sich nur auf die aktuelle PowerShell-Sitzung aus.</span><span class="sxs-lookup"><span data-stu-id="d4d83-114">It affects only the current PowerShell session.</span></span>

## <span data-ttu-id="d4d83-115">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="d4d83-115">EXAMPLES</span></span>

### <span data-ttu-id="d4d83-116">Beispiel 1: Entfernen eines Moduls</span><span class="sxs-lookup"><span data-stu-id="d4d83-116">Example 1: Remove a module</span></span>

```powershell
Remove-Module -Name "BitsTransfer"
```

<span data-ttu-id="d4d83-117">Mit diesem Befehl wird das BitsTransfer-Modul aus der aktuellen Sitzung entfernt.</span><span class="sxs-lookup"><span data-stu-id="d4d83-117">This command removes the BitsTransfer module from the current session.</span></span>

### <span data-ttu-id="d4d83-118">Beispiel 2: Entfernen aller Module</span><span class="sxs-lookup"><span data-stu-id="d4d83-118">Example 2: Remove all modules</span></span>

```powershell
Get-Module | Remove-Module
```

<span data-ttu-id="d4d83-119">Dieser Befehl entfernt alle Module aus der aktuellen Sitzung.</span><span class="sxs-lookup"><span data-stu-id="d4d83-119">This command removes all modules from the current session.</span></span>

### <span data-ttu-id="d4d83-120">Beispiel 3: Entfernen von Modulen mithilfe der Pipeline</span><span class="sxs-lookup"><span data-stu-id="d4d83-120">Example 3: Remove modules by using the pipeline</span></span>

```powershell
"FileTransfer", "PSDiagnostics" | Remove-Module -Verbose
```

```Output
VERBOSE: Performing operation "Remove-Module" on Target "filetransfer (Path: 'C:\Windows\system32\WindowsPowerShell\v1.0\Modules\filetransfer\filetransfer.psd1')".
VERBOSE: Performing operation "Remove-Module" on Target "Microsoft.BackgroundIntelligentTransfer.Management (Path: 'C:\Windows\assembly\GAC_MSIL\Microsoft.BackgroundIntelligentTransfer.Management\1.0.0.0__31bf3856ad364e35\Microsoft.BackgroundIntelligentTransfe
r.Management.dll')".
VERBOSE: Performing operation "Remove-Module" on Target "psdiagnostics (Path: 'C:\Windows\system32\WindowsPowerShell\v1.0\Modules\psdiagnostics\psdiagnostics.psd1')".
VERBOSE: Removing imported function 'Start-Trace'.
VERBOSE: Removing imported function 'Stop-Trace'.
VERBOSE: Removing imported function 'Enable-WSManTrace'.
VERBOSE: Removing imported function 'Disable-WSManTrace'.
VERBOSE: Removing imported function 'Enable-PSWSManCombinedTrace'.
VERBOSE: Removing imported function 'Disable-PSWSManCombinedTrace'.
VERBOSE: Removing imported function 'Set-LogProperties'.
VERBOSE: Removing imported function 'Get-LogProperties'.
VERBOSE: Removing imported function 'Enable-PSTrace'.
VERBOSE: Removing imported function 'Disable-PSTrace'.
VERBOSE: Performing operation "Remove-Module" on Target "PSDiagnostics (Path: 'C:\Windows\system32\WindowsPowerShell\v1.0\Modules\psdiagnostics\PSDiagnostics.psm1')".
```

<span data-ttu-id="d4d83-121">Dieser Befehl entfernt die BitsTransfer- und PSDiagnostics-Module aus der aktuellen Sitzung.</span><span class="sxs-lookup"><span data-stu-id="d4d83-121">This command removes the BitsTransfer and PSDiagnostics modules from the current session.</span></span>

<span data-ttu-id="d4d83-122">Der Befehl verwendet einen Pipelineoperator (|), um die Modulnamen an **Remove-Module** zu senden.</span><span class="sxs-lookup"><span data-stu-id="d4d83-122">The command uses a pipeline operator (|) to send the module names to **Remove-Module** .</span></span>
<span data-ttu-id="d4d83-123">Er verwendet den allgemeinen *Verbose* -Parameter, um detaillierte Informationen über die zu entfernenden Elemente abzurufen.</span><span class="sxs-lookup"><span data-stu-id="d4d83-123">It uses the *Verbose* common parameter to get detailed information about the members that are removed.</span></span>

<span data-ttu-id="d4d83-124">In den ausführlichen Meldungen werden die Elemente angezeigt *, die entfernt* werden.</span><span class="sxs-lookup"><span data-stu-id="d4d83-124">The *Verbose* messages show the items that are removed.</span></span>
<span data-ttu-id="d4d83-125">Die Meldungen unterscheiden sich voneinander, da das BitsTransfer-Modul eine Assembly enthält, die die Cmdlets implementiert, sowie ein geschachteltes Modul mit seiner eigenen Assembly.</span><span class="sxs-lookup"><span data-stu-id="d4d83-125">The messages differ because the BitsTransfer module includes an assembly that implements its cmdlets and a nested module with its own assembly.</span></span>
<span data-ttu-id="d4d83-126">Das PSDiagnostics-Modul umfasst eine Modulskriptdatei (.psm1), die Funktionen exportiert.</span><span class="sxs-lookup"><span data-stu-id="d4d83-126">The PSDiagnostics module includes a module script file (.psm1) that exports functions.</span></span>

### <span data-ttu-id="d4d83-127">Beispiel 4: Entfernen eines Moduls mithilfe von ModuleInfo</span><span class="sxs-lookup"><span data-stu-id="d4d83-127">Example 4: Remove a module by using ModuleInfo</span></span>

```powershell
$a = Get-Module BitsTransfer
Remove-Module -ModuleInfo $a
```

<span data-ttu-id="d4d83-128">Dieser Befehl verwendet den *ModuleInfo* -Parameter, um das bitstransfer-Modul zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="d4d83-128">This command uses the *ModuleInfo* parameter to remove the BitsTransfer module.</span></span>

## <span data-ttu-id="d4d83-129">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="d4d83-129">PARAMETERS</span></span>

### <span data-ttu-id="d4d83-130">-Force</span><span class="sxs-lookup"><span data-stu-id="d4d83-130">-Force</span></span>

<span data-ttu-id="d4d83-131">Gibt an, dass mit diesem Cmdlet schreibgeschützte Module entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="d4d83-131">Indicates that this cmdlet removes read-only modules.</span></span>
<span data-ttu-id="d4d83-132">In der Standardeinstellung entfernt **Remove-Module** nur Module mit Lese-/ Schreibzugriff.</span><span class="sxs-lookup"><span data-stu-id="d4d83-132">By default, **Remove-Module** removes only read-write modules.</span></span>

<span data-ttu-id="d4d83-133">Die Werte **ReadOnly** und **ReadWrite** sind in der **AccessMode** -Eigenschaft eines Moduls gespeichert.</span><span class="sxs-lookup"><span data-stu-id="d4d83-133">The **ReadOnly** and **ReadWrite** values are stored in **AccessMode** property of a module.</span></span>

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

### <span data-ttu-id="d4d83-134">-FullyQualifiedName</span><span class="sxs-lookup"><span data-stu-id="d4d83-134">-FullyQualifiedName</span></span>

<span data-ttu-id="d4d83-135">Gibt die voll qualifizierten Namen von Modulen an, die entfernt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="d4d83-135">Specifies the fully qualified names of modules to remove.</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.ModuleSpecification[]
Parameter Sets: FullyQualifiedName
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="d4d83-136">-ModuleInfo</span><span class="sxs-lookup"><span data-stu-id="d4d83-136">-ModuleInfo</span></span>

<span data-ttu-id="d4d83-137">Gibt die zu entfernenden Modulobjekte an.</span><span class="sxs-lookup"><span data-stu-id="d4d83-137">Specifies the module objects to remove.</span></span>
<span data-ttu-id="d4d83-138">Geben Sie eine Variable ein, die ein Modul Objekt ( **psmoduleinfo** ) enthält, oder einen Befehl, mit dem ein Modul Objekt abgerufen wird, z. b. ein Get-Module Befehl.</span><span class="sxs-lookup"><span data-stu-id="d4d83-138">Enter a variable that contains a module object ( **PSModuleInfo** ) or a command that gets a module object, such as a Get-Module command.</span></span>
<span data-ttu-id="d4d83-139">Sie können auch Modulobjekte an **Remove-Module** übergeben.</span><span class="sxs-lookup"><span data-stu-id="d4d83-139">You can also pipe module objects to **Remove-Module** .</span></span>

```yaml
Type: System.Management.Automation.PSModuleInfo[]
Parameter Sets: ModuleInfo
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="d4d83-140">-Name</span><span class="sxs-lookup"><span data-stu-id="d4d83-140">-Name</span></span>

<span data-ttu-id="d4d83-141">Gibt die Namen der zu entfernenden Module an.</span><span class="sxs-lookup"><span data-stu-id="d4d83-141">Specifies the names of modules to remove.</span></span>
<span data-ttu-id="d4d83-142">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="d4d83-142">Wildcard characters are permitted.</span></span>
<span data-ttu-id="d4d83-143">Sie können auch Namenszeichenfolgen an **Remove-Module** übergeben.</span><span class="sxs-lookup"><span data-stu-id="d4d83-143">You can also pipe name strings to **Remove-Module** .</span></span>

```yaml
Type: System.String[]
Parameter Sets: name
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: True
```

### <span data-ttu-id="d4d83-144">-Confirm</span><span class="sxs-lookup"><span data-stu-id="d4d83-144">-Confirm</span></span>

<span data-ttu-id="d4d83-145">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="d4d83-145">Prompts you for confirmation before running the cmdlet.</span></span>

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

### <span data-ttu-id="d4d83-146">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="d4d83-146">-WhatIf</span></span>

<span data-ttu-id="d4d83-147">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="d4d83-147">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="d4d83-148">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="d4d83-148">The cmdlet is not run.</span></span>

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

### <span data-ttu-id="d4d83-149">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="d4d83-149">CommonParameters</span></span>

<span data-ttu-id="d4d83-150">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="d4d83-150">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="d4d83-151">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="d4d83-151">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="d4d83-152">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="d4d83-152">INPUTS</span></span>

### <span data-ttu-id="d4d83-153">System. String, System. Management. Automation. psmoduleinfo</span><span class="sxs-lookup"><span data-stu-id="d4d83-153">System.String, System.Management.Automation.PSModuleInfo</span></span>

<span data-ttu-id="d4d83-154">Sie können Modulnamen und Modul Objekte über die Pipeline an **Remove-Module** übergeben.</span><span class="sxs-lookup"><span data-stu-id="d4d83-154">You can pipe module names and module objects to **Remove-Module** .</span></span>

## <span data-ttu-id="d4d83-155">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="d4d83-155">OUTPUTS</span></span>

### <span data-ttu-id="d4d83-156">Keine</span><span class="sxs-lookup"><span data-stu-id="d4d83-156">None</span></span>

<span data-ttu-id="d4d83-157">Dieses Cmdlet generiert keine Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="d4d83-157">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="d4d83-158">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="d4d83-158">NOTES</span></span>

<span data-ttu-id="d4d83-159">Beim Entfernen eines Moduls ist ein Ereignis für das Modul vorhanden, das ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="d4d83-159">When removing a module, there is an event on the module that will execute.</span></span>
<span data-ttu-id="d4d83-160">Dieses Ereignis ermöglicht einem Modul, auf das Entfernen zu reagieren und einige Bereinigungs Vorgänge auszuführen, z. b. das Freigeben von Ressourcen.</span><span class="sxs-lookup"><span data-stu-id="d4d83-160">This event allows a module to react to being removed and perform some cleanup such as freeing up resources.</span></span> <span data-ttu-id="d4d83-161">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="d4d83-161">Example:</span></span>

<span data-ttu-id="d4d83-162">$OnRemoveScript = {</span><span class="sxs-lookup"><span data-stu-id="d4d83-162">$OnRemoveScript = {</span></span>

  <span data-ttu-id="d4d83-163">\# Bereinigung ausführen</span><span class="sxs-lookup"><span data-stu-id="d4d83-163">\# perform cleanup</span></span>

  <span data-ttu-id="d4d83-164">$cachedSessions | Remove-PSSession</span><span class="sxs-lookup"><span data-stu-id="d4d83-164">$cachedSessions | Remove-PSSession</span></span>

<span data-ttu-id="d4d83-165">}</span><span class="sxs-lookup"><span data-stu-id="d4d83-165">}</span></span>

<span data-ttu-id="d4d83-166">$ExecutionContext. SessionState. Module. OnRemove + = $OnRemoveScript</span><span class="sxs-lookup"><span data-stu-id="d4d83-166">$ExecutionContext.SessionState.Module.OnRemove += $OnRemoveScript</span></span>

<span data-ttu-id="d4d83-167">Um vollständige Konsistenz zu gewährleisten, kann es auch hilfreich sein, auf den Abschluss des PowerShell-Prozesses zu reagieren:</span><span class="sxs-lookup"><span data-stu-id="d4d83-167">For full consistency, it might be also useful to react to the closing of the PowerShell process:</span></span>

<span data-ttu-id="d4d83-168">Register-EngineEvent-SourceIdentifier ([System. Management. Automation. psengineevent]:: Exit)-Action $OnRemoveScript</span><span class="sxs-lookup"><span data-stu-id="d4d83-168">Register-EngineEvent -SourceIdentifier ([System.Management.Automation.PsEngineEvent]::Exiting) -Action $OnRemoveScript</span></span>

## <span data-ttu-id="d4d83-169">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="d4d83-169">RELATED LINKS</span></span>

[<span data-ttu-id="d4d83-170">Get-Module</span><span class="sxs-lookup"><span data-stu-id="d4d83-170">Get-Module</span></span>](Get-Module.md)

[<span data-ttu-id="d4d83-171">Import-Module</span><span class="sxs-lookup"><span data-stu-id="d4d83-171">Import-Module</span></span>](Import-Module.md)