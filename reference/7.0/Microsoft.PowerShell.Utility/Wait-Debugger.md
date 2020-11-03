---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 03/30/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/wait-debugger?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Wait-Debugger
ms.openlocfilehash: f1488f65cf5ce48efe9d6459952653ff6570aa25
ms.sourcegitcommit: 2e497178126b2b33a169ff04c31e251e0b59e89b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/02/2020
ms.locfileid: "93209351"
---
# <span data-ttu-id="133fe-103">Wait-Debugger</span><span class="sxs-lookup"><span data-stu-id="133fe-103">Wait-Debugger</span></span>

## <span data-ttu-id="133fe-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="133fe-104">SYNOPSIS</span></span>
<span data-ttu-id="133fe-105">Beendet ein Skript im Debugger, bevor die nächste Anweisung im Skript ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="133fe-105">Stops a script in the debugger before running the next statement in the script.</span></span>

## <span data-ttu-id="133fe-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="133fe-106">SYNTAX</span></span>

```
Wait-Debugger [<CommonParameters>]
```

## <span data-ttu-id="133fe-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="133fe-107">DESCRIPTION</span></span>

<span data-ttu-id="133fe-108">Beendet die PowerShell-Skript Ausführungs-Engine an dem Punkt unmittelbar nach dem `Wait-Debugger` -Cmdlet und wartet, bis ein Debugger angefügt wird.</span><span class="sxs-lookup"><span data-stu-id="133fe-108">Stops the PowerShell script execution engine at the point immediately after the `Wait-Debugger` cmdlet and waits for a debugger to be attached.</span></span> <span data-ttu-id="133fe-109">Dies ähnelt `Enable-RunspaceDebug -BreakAll` der Verwendung von in einer DSC-Ressource, unterbricht aber an einem bestimmten Punkt im Skript.</span><span class="sxs-lookup"><span data-stu-id="133fe-109">This is similar to using `Enable-RunspaceDebug -BreakAll` in a DSC resource but breaks at a specific point in the script.</span></span>

> [!CAUTION]
> <span data-ttu-id="133fe-110">Stellen Sie sicher, dass Sie die Zeilen entfernen, `Wait-Debugger` nachdem Sie abgeschlossen sind.</span><span class="sxs-lookup"><span data-stu-id="133fe-110">Make sure you remove the `Wait-Debugger` lines after you are done.</span></span> <span data-ttu-id="133fe-111">Ein Skript, das ausgeführt wird, wird anscheinend nicht reagiert, wenn es an einem angehalten wird `Wait-Debugger` .</span><span class="sxs-lookup"><span data-stu-id="133fe-111">A running script appears to be hung when it is stopped at a `Wait-Debugger`.</span></span>

## <span data-ttu-id="133fe-112">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="133fe-112">EXAMPLES</span></span>

### <span data-ttu-id="133fe-113">Beispiel 1: Einfügen von Haltepunkten zum Debuggen</span><span class="sxs-lookup"><span data-stu-id="133fe-113">Example 1: Insert breakpoint for debugging</span></span>

```
[DscResource()]
class FileResource
{
    [DscProperty(Key)]
    [string] $Path

    [DscProperty(Mandatory)]
    [Ensure] $Ensure

    [DscProperty(Mandatory)]
    [string] $SourcePath

    [DscProperty(NotConfigurable)]
    [Nullable[datetime]] $CreationTime


    [void] Set()
    {
        $fileExists = $this.TestFilePath($this.Path)
        if ($this.ensure -eq [Ensure]::Present)
        {
            if (! $fileExists)
            {
               $this.CopyFile()
            }
        }
        else
        {
            if ($fileExists)
            {
                Write-Verbose -Message "Deleting the file $($this.Path)"
                Remove-Item -LiteralPath $this.Path -Force
            }
        }
    }

    [bool] Test()
    {
        $present = Test-Path -LiteralPath $this.Path

        if ($this.Ensure -eq [Ensure]::Present)
        {
            return $present
        }
        else
        {
            return (! $present)
        }
    }

    [FileResource] Get()
    {
        $present = Test-Path -Path $this.Path

        if ($present)
        {
            $file = Get-ChildItem -LiteralPath $this.Path
            $this.CreationTime = $file.CreationTime
            $this.Ensure = [Ensure]::Present
        }
        else
        {
            $this.CreationTime = $null
            $this.Ensure = [Ensure]::Absent
        }

        return $this
    }

    [void] CopyFile()
    {
        # Testing only - Remove before deployment!
        Wait-Debugger

        if (! (Test-Path -LiteralPath $this.SourcePath))
        {
            throw "SourcePath $($this.SourcePath) is not found."
        }

        if (Test-Path -LiteralPath $this.Path -PathType Container)
        {
            throw "Path $($this.Path) is a directory path"
        }

        Write-Verbose "Copying $($this.SourcePath) to $($this.Path)"

        Copy-Item -LiteralPath $this.SourcePath -Destination $this.Path -Force
    }
}
```

## <span data-ttu-id="133fe-114">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="133fe-114">PARAMETERS</span></span>

### <span data-ttu-id="133fe-115">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="133fe-115">CommonParameters</span></span>

<span data-ttu-id="133fe-116">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="133fe-116">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="133fe-117">Weitere Informationen findest du unter [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="133fe-117">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="133fe-118">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="133fe-118">INPUTS</span></span>

### <span data-ttu-id="133fe-119">Keine</span><span class="sxs-lookup"><span data-stu-id="133fe-119">None</span></span>

## <span data-ttu-id="133fe-120">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="133fe-120">OUTPUTS</span></span>

### <span data-ttu-id="133fe-121">Keine</span><span class="sxs-lookup"><span data-stu-id="133fe-121">None</span></span>

## <span data-ttu-id="133fe-122">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="133fe-122">NOTES</span></span>

## <span data-ttu-id="133fe-123">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="133fe-123">RELATED LINKS</span></span>

[<span data-ttu-id="133fe-124">Enable-DscDebug</span><span class="sxs-lookup"><span data-stu-id="133fe-124">Enable-DscDebug</span></span>](/powershell/module/PSDesiredStateConfiguration/Enable-DscDebug)