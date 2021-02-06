---
external help file: PSDiagnostics-help.xml
Locale: en-US
Module Name: PSDiagnostics
ms.date: 11/27/2018
online version: https://docs.microsoft.com/powershell/module/psdiagnostics/enable-pstrace?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Enable-PSTrace
ms.openlocfilehash: 231c2e3d2e28463be35ff1c9d5dab5a5d958f430
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99602104"
---
# <span data-ttu-id="c3c0b-102">Enable-PSTrace</span><span class="sxs-lookup"><span data-stu-id="c3c0b-102">Enable-PSTrace</span></span>

## <span data-ttu-id="c3c0b-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="c3c0b-103">SYNOPSIS</span></span>
<span data-ttu-id="c3c0b-104">Aktiviert die Protokolle von Microsoft-Windows-PowerShell-Ereignis Anbietern.</span><span class="sxs-lookup"><span data-stu-id="c3c0b-104">Enables the Microsoft-Windows-PowerShell event provider logs.</span></span>

## <span data-ttu-id="c3c0b-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="c3c0b-105">SYNTAX</span></span>

```
Enable-PSTrace [-Force] [-AnalyticOnly] [<CommonParameters>]
```

## <span data-ttu-id="c3c0b-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="c3c0b-106">DESCRIPTION</span></span>

<span data-ttu-id="c3c0b-107">Dieses Cmdlet aktiviert die Betriebs-und Analyse Ereignisprotokolle des Microsoft-Windows-PowerShell-Ereignis Anbieters.</span><span class="sxs-lookup"><span data-stu-id="c3c0b-107">This cmdlet enables the Operational and Analytic event logs of the Microsoft-Windows-PowerShell event provider.</span></span>

<span data-ttu-id="c3c0b-108">Sie müssen dieses Cmdlet aus einer PowerShell-Sitzung mit erhöhten Rechten ausführen.</span><span class="sxs-lookup"><span data-stu-id="c3c0b-108">You must run this cmdlet from an elevated PowerShell session.</span></span>

## <span data-ttu-id="c3c0b-109">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="c3c0b-109">EXAMPLES</span></span>

### <span data-ttu-id="c3c0b-110">Beispiel 1: Aktivieren des analytischen Ereignis Protokolls für PowerShell</span><span class="sxs-lookup"><span data-stu-id="c3c0b-110">Example 1: Enable the Analytic event log for PowerShell</span></span>

<span data-ttu-id="c3c0b-111">Im folgenden Beispiel wird nur das Analyse Ereignisprotokoll des Microsoft-Windows-PowerShell-Anbieters aktiviert.</span><span class="sxs-lookup"><span data-stu-id="c3c0b-111">The following example enables only the Analytic event log of the Microsoft-Windows-PowerShell provider.</span></span>

```powershell
Enable-PSTrace -AnalyticOnly
```

## <span data-ttu-id="c3c0b-112">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="c3c0b-112">PARAMETERS</span></span>

### <span data-ttu-id="c3c0b-113">-Analytily</span><span class="sxs-lookup"><span data-stu-id="c3c0b-113">-AnalyticOnly</span></span>

<span data-ttu-id="c3c0b-114">Wenn dieser Parameter verwendet wird, aktiviert das Cmdlet das Analyse Ereignisprotokoll des Microsoft-Windows-PowerShell-Anbieters.</span><span class="sxs-lookup"><span data-stu-id="c3c0b-114">When this parameter is used, the cmdlet enables the Analytic event log of the Microsoft-Windows-PowerShell provider.</span></span> <span data-ttu-id="c3c0b-115">Das Betriebs Ereignisprotokoll wird nicht geändert.</span><span class="sxs-lookup"><span data-stu-id="c3c0b-115">The Operational event log is not changed.</span></span>

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

### <span data-ttu-id="c3c0b-116">-Force</span><span class="sxs-lookup"><span data-stu-id="c3c0b-116">-Force</span></span>

<span data-ttu-id="c3c0b-117">Wird verwendet, um die Änderung ohne Eingabeaufforderung zu erzwingen.</span><span class="sxs-lookup"><span data-stu-id="c3c0b-117">Used to force the change without prompting.</span></span>

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

### <span data-ttu-id="c3c0b-118">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="c3c0b-118">CommonParameters</span></span>
<span data-ttu-id="c3c0b-119">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="c3c0b-119">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="c3c0b-120">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="c3c0b-120">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="c3c0b-121">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="c3c0b-121">INPUTS</span></span>

### <span data-ttu-id="c3c0b-122">Keine</span><span class="sxs-lookup"><span data-stu-id="c3c0b-122">None</span></span>

## <span data-ttu-id="c3c0b-123">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="c3c0b-123">OUTPUTS</span></span>

### <span data-ttu-id="c3c0b-124">Keine</span><span class="sxs-lookup"><span data-stu-id="c3c0b-124">None</span></span>

## <span data-ttu-id="c3c0b-125">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="c3c0b-125">NOTES</span></span>

<span data-ttu-id="c3c0b-126">Dieses Cmdlet verwendet die `Get-LogProperties` `Set-LogProperties` Cmdlets und.</span><span class="sxs-lookup"><span data-stu-id="c3c0b-126">This cmdlet uses the `Get-LogProperties` and `Set-LogProperties` cmdlets.</span></span>

<span data-ttu-id="c3c0b-127">Sie müssen dieses Cmdlet aus einer PowerShell-Sitzung mit erhöhten Rechten ausführen.</span><span class="sxs-lookup"><span data-stu-id="c3c0b-127">You must run this cmdlet from an elevated PowerShell session.</span></span>

## <span data-ttu-id="c3c0b-128">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="c3c0b-128">RELATED LINKS</span></span>

[<span data-ttu-id="c3c0b-129">Get-LogProperties</span><span class="sxs-lookup"><span data-stu-id="c3c0b-129">Get-LogProperties</span></span>](Get-LogProperties.md)

[<span data-ttu-id="c3c0b-130">Set-LogProperties</span><span class="sxs-lookup"><span data-stu-id="c3c0b-130">Set-LogProperties</span></span>](Set-LogProperties.md)

[<span data-ttu-id="c3c0b-131">Disable-PSTrace</span><span class="sxs-lookup"><span data-stu-id="c3c0b-131">Disable-PSTrace</span></span>](Disable-PSTrace.md)
