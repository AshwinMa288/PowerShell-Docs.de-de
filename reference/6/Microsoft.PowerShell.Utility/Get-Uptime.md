---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Module Name: Microsoft.PowerShell.Utility
ms.date: 06/27/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/get-uptime?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-Uptime
ms.openlocfilehash: 999ef16ef3065c26dc1d51e49c5ba5793af7db4a
ms.sourcegitcommit: 9b28fb9a3d72655bb63f62af18b3a5af6a05cd3f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2020
ms.locfileid: "93216591"
---
# <span data-ttu-id="84aeb-102">Get-Uptime</span><span class="sxs-lookup"><span data-stu-id="84aeb-102">Get-Uptime</span></span>

## <span data-ttu-id="84aeb-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="84aeb-103">SYNOPSIS</span></span>
<span data-ttu-id="84aeb-104">Zeitspanne **seit dem letzten** Start starten.</span><span class="sxs-lookup"><span data-stu-id="84aeb-104">Get the **TimeSpan** since last boot.</span></span>

## <span data-ttu-id="84aeb-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="84aeb-105">SYNTAX</span></span>

### <span data-ttu-id="84aeb-106">TimeSpan (Standard)</span><span class="sxs-lookup"><span data-stu-id="84aeb-106">Timespan (Default)</span></span>

```
Get-Uptime [<CommonParameters>]
```

### <span data-ttu-id="84aeb-107">Zumal</span><span class="sxs-lookup"><span data-stu-id="84aeb-107">Since</span></span>

```
Get-Uptime [-Since] [<CommonParameters>]
```

## <span data-ttu-id="84aeb-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="84aeb-108">DESCRIPTION</span></span>

<span data-ttu-id="84aeb-109">Dieses Cmdlet gibt die Zeit zurück, die seit dem letzten Start des Betriebssystems verstrichen ist.</span><span class="sxs-lookup"><span data-stu-id="84aeb-109">This cmdlet returns the time elapsed since the last boot of the operating system.</span></span>

<span data-ttu-id="84aeb-110">Das `Get-Uptime` Cmdlet wurde in PowerShell 6,0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="84aeb-110">The `Get-Uptime` cmdlet was introduced in PowerShell 6.0.</span></span>

## <span data-ttu-id="84aeb-111">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="84aeb-111">EXAMPLES</span></span>

### <span data-ttu-id="84aeb-112">Beispiel 1: Anzeigen der Zeit seit dem letzten Start</span><span class="sxs-lookup"><span data-stu-id="84aeb-112">Example 1 - Show time since last boot</span></span>

```powershell
Get-Uptime
```

```Output
Days              : 9
Hours             : 0
Minutes           : 9
Seconds           : 45
Milliseconds      : 0
Ticks             : 7781850000000
TotalDays         : 9.00677083333333
TotalHours        : 216.1625
TotalMinutes      : 12969.75
TotalSeconds      : 778185
TotalMilliseconds : 778185000
```

### <span data-ttu-id="84aeb-113">Beispiel 2: Anzeigen der Uhrzeit des letzten Starts</span><span class="sxs-lookup"><span data-stu-id="84aeb-113">Example 2 - Show the time of the last boot</span></span>

```powershell
Get-Uptime -Since
```

```Output
Tuesday, June 18, 2019 2:34:56 PM
```

## <span data-ttu-id="84aeb-114">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="84aeb-114">PARAMETERS</span></span>

### <span data-ttu-id="84aeb-115">-Seit</span><span class="sxs-lookup"><span data-stu-id="84aeb-115">-Since</span></span>

<span data-ttu-id="84aeb-116">Bewirkt, dass das Cmdlet ein **DateTime** -Objekt zurückgibt, das den Zeitpunkt darstellt, zu dem das Betriebssystem zuletzt gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="84aeb-116">Cause the cmdlet to return a **DateTime** object representing the last time that the operating system was booted.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: Since
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="84aeb-117">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="84aeb-117">CommonParameters</span></span>

<span data-ttu-id="84aeb-118">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="84aeb-118">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="84aeb-119">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="84aeb-119">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="84aeb-120">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="84aeb-120">INPUTS</span></span>

### <span data-ttu-id="84aeb-121">Keine</span><span class="sxs-lookup"><span data-stu-id="84aeb-121">None</span></span>

## <span data-ttu-id="84aeb-122">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="84aeb-122">OUTPUTS</span></span>

### <span data-ttu-id="84aeb-123">System.TimeSpan</span><span class="sxs-lookup"><span data-stu-id="84aeb-123">System.TimeSpan</span></span>

<span data-ttu-id="84aeb-124">Dies ist der Standard Rückgabetyp, wenn keine Parameter verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="84aeb-124">This is the default return type when no parameters are used.</span></span>

### <span data-ttu-id="84aeb-125">System.DateTime</span><span class="sxs-lookup"><span data-stu-id="84aeb-125">System.DateTime</span></span>

<span data-ttu-id="84aeb-126">Dieser Typ wird zurückgegeben, wenn der **seit** -Parameter verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="84aeb-126">This type is returned when using the **Since** parameter.</span></span>

> [!NOTE]
> <span data-ttu-id="84aeb-127">Wenn Windows fast Startup aktiviert ist, aktualisiert Windows den in **LastBootUpTime** gespeicherten Wert nicht.</span><span class="sxs-lookup"><span data-stu-id="84aeb-127">If Windows fast startup is enabled, Windows does not update the value stored in **LastBootUpTime** .</span></span> <span data-ttu-id="84aeb-128">Um den schnellen Start zu deaktivieren, führen Sie den folgenden Befehl aus: `Powercfg -h off` .</span><span class="sxs-lookup"><span data-stu-id="84aeb-128">To disable fast startup, run the following command: `Powercfg -h off`.</span></span>
>
> <span data-ttu-id="84aeb-129">Weitere Informationen zum schnellen Start von Windows finden Sie unter unter [scheiden des schnellen Starts von Wake-from-](/windows-hardware/drivers/kernel/distinguishing-fast-startup-from-wake-from-hibernation)Ruhe Zustands.</span><span class="sxs-lookup"><span data-stu-id="84aeb-129">For more information about Windows fast startup, see [Distinguishing Fast Startup from Wake-from-Hibernation](/windows-hardware/drivers/kernel/distinguishing-fast-startup-from-wake-from-hibernation).</span></span>

## <span data-ttu-id="84aeb-130">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="84aeb-130">NOTES</span></span>

<span data-ttu-id="84aeb-131">Unter Windows ist der zurückgegebene Wert mit der **LastBootUpTime** -Eigenschaft der **Win32_OperatingSystem** -Klasse in WMI identisch.</span><span class="sxs-lookup"><span data-stu-id="84aeb-131">On Windows, the value returned is the same as the **LastBootUpTime** property of the **Win32_OperatingSystem** class in WMI.</span></span>

## <span data-ttu-id="84aeb-132">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="84aeb-132">RELATED LINKS</span></span>

[<span data-ttu-id="84aeb-133">Win32_OperatingSystem</span><span class="sxs-lookup"><span data-stu-id="84aeb-133">Win32_OperatingSystem</span></span>](/windows/win32/cimwin32prov/win32-operatingsystem#properties)