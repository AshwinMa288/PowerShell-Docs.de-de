---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 04/10/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/start-sleep?view=powershell-7&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Start-Sleep
ms.openlocfilehash: 535cad057db406eaa48259288e34da6da4ed1cbb
ms.sourcegitcommit: de63e9481cf8024883060aae61fb02c59c2de662
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2020
ms.locfileid: "93210148"
---
# <span data-ttu-id="32cd1-103">Start-Sleep</span><span class="sxs-lookup"><span data-stu-id="32cd1-103">Start-Sleep</span></span>

## <span data-ttu-id="32cd1-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="32cd1-104">SYNOPSIS</span></span>
<span data-ttu-id="32cd1-105">Hält die Aktivität in einem Skript oder einer Sitzung für den angegebenen Zeitraum an.</span><span class="sxs-lookup"><span data-stu-id="32cd1-105">Suspends the activity in a script or session for the specified period of time.</span></span>

## <span data-ttu-id="32cd1-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="32cd1-106">SYNTAX</span></span>

### <span data-ttu-id="32cd1-107">Sekunden (Standard)</span><span class="sxs-lookup"><span data-stu-id="32cd1-107">Seconds (Default)</span></span>

```
Start-Sleep [-Seconds] <Double> [<CommonParameters>]
```

### <span data-ttu-id="32cd1-108">Millisekunden</span><span class="sxs-lookup"><span data-stu-id="32cd1-108">Milliseconds</span></span>

```
Start-Sleep -Milliseconds <Int32> [<CommonParameters>]
```

## <span data-ttu-id="32cd1-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="32cd1-109">DESCRIPTION</span></span>

<span data-ttu-id="32cd1-110">Das- `Start-Sleep` Cmdlet hält die Aktivität in einem Skript oder einer Sitzung für den angegebenen Zeitraum an.</span><span class="sxs-lookup"><span data-stu-id="32cd1-110">The `Start-Sleep` cmdlet suspends the activity in a script or session for the specified period of time.</span></span> <span data-ttu-id="32cd1-111">Sie können es für viele Aufgaben verwenden, z. B. Warten auf den Abschluss eines Vorgangs oder Anhalten, bevor ein Vorgang wiederholt wird.</span><span class="sxs-lookup"><span data-stu-id="32cd1-111">You can use it for many tasks, such as waiting for an operation to complete or pausing before repeating an operation.</span></span>

## <span data-ttu-id="32cd1-112">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="32cd1-112">EXAMPLES</span></span>

### <span data-ttu-id="32cd1-113">Beispiel 1: alle Befehle für 15 Sekunden in den Standbymodus</span><span class="sxs-lookup"><span data-stu-id="32cd1-113">Example 1: Sleep all commands for 15 seconds</span></span>

```powershell
Start-Sleep -s 15
```

### <span data-ttu-id="32cd1-114">Beispiel 2: Standbymodus für alle Befehle für 1,5 Sekunden</span><span class="sxs-lookup"><span data-stu-id="32cd1-114">Example 2: Sleep all commands for 1.5 seconds</span></span>

<span data-ttu-id="32cd1-115">In diesem Beispiel werden alle Befehle in der Sitzung für eine und eine halbe Sekunde in den Standbymodus versetzt.</span><span class="sxs-lookup"><span data-stu-id="32cd1-115">This example makes all the commands in the session sleep for one and one-half of a seconds.</span></span>

```powershell
Start-Sleep -Seconds 1.5
```

## <span data-ttu-id="32cd1-116">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="32cd1-116">PARAMETERS</span></span>

### <span data-ttu-id="32cd1-117">-Millisekunden</span><span class="sxs-lookup"><span data-stu-id="32cd1-117">-Milliseconds</span></span>

<span data-ttu-id="32cd1-118">Gibt an, wie lange die Ressource in Millisekunden im Ruhezustand ist.</span><span class="sxs-lookup"><span data-stu-id="32cd1-118">Specifies how long the resource sleeps in milliseconds.</span></span> <span data-ttu-id="32cd1-119">Der-Parameter kann als **m** abgekürzt werden.</span><span class="sxs-lookup"><span data-stu-id="32cd1-119">The parameter can be abbreviated as **m** .</span></span>

```yaml
Type: System.Int32
Parameter Sets: Milliseconds
Aliases: ms

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="32cd1-120">-Sekunden</span><span class="sxs-lookup"><span data-stu-id="32cd1-120">-Seconds</span></span>

<span data-ttu-id="32cd1-121">Gibt an, wie lange die Ressource in Sekunden im Ruhezustand ist.</span><span class="sxs-lookup"><span data-stu-id="32cd1-121">Specifies how long the resource sleeps in seconds.</span></span> <span data-ttu-id="32cd1-122">Sie können den Parameternamen weglassen, oder Sie können ihn als **s** abkürzen.</span><span class="sxs-lookup"><span data-stu-id="32cd1-122">You can omit the parameter name or you can abbreviate it as **s** .</span></span> <span data-ttu-id="32cd1-123">Beginnend mit der PowerShell-6.2.0 akzeptiert dieser Parameter nun Bruchzahlen.</span><span class="sxs-lookup"><span data-stu-id="32cd1-123">Beginning in PowerShell 6.2.0, this parameter now accepts fractional values.</span></span>

```yaml
Type: System.Double
Parameter Sets: Seconds
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="32cd1-124">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="32cd1-124">CommonParameters</span></span>

<span data-ttu-id="32cd1-125">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="32cd1-125">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="32cd1-126">Weitere Informationen findest du unter [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="32cd1-126">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="32cd1-127">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="32cd1-127">INPUTS</span></span>

### <span data-ttu-id="32cd1-128">System.Int32</span><span class="sxs-lookup"><span data-stu-id="32cd1-128">System.Int32</span></span>

<span data-ttu-id="32cd1-129">Sie können die Anzahl der Sekunden an die Pipeline übergeben `Start-Sleep` .</span><span class="sxs-lookup"><span data-stu-id="32cd1-129">You can pipe the number of seconds to `Start-Sleep`.</span></span>

## <span data-ttu-id="32cd1-130">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="32cd1-130">OUTPUTS</span></span>

### <span data-ttu-id="32cd1-131">Keine</span><span class="sxs-lookup"><span data-stu-id="32cd1-131">None</span></span>

<span data-ttu-id="32cd1-132">Dieses Cmdlet gibt keine Ausgabe zurück.</span><span class="sxs-lookup"><span data-stu-id="32cd1-132">This cmdlet does not return any output.</span></span>

## <span data-ttu-id="32cd1-133">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="32cd1-133">NOTES</span></span>

- <span data-ttu-id="32cd1-134">Sie können auch auf den `Start-Sleep` integrierten Alias verweisen `sleep` .</span><span class="sxs-lookup"><span data-stu-id="32cd1-134">You can also refer to `Start-Sleep` by its built-in alias, `sleep`.</span></span> <span data-ttu-id="32cd1-135">Weitere Informationen finden Sie unter [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).</span><span class="sxs-lookup"><span data-stu-id="32cd1-135">For more information, see [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).</span></span>
- <span data-ttu-id="32cd1-136">`Ctrl+C` bricht von ab `Start-Sleep` .</span><span class="sxs-lookup"><span data-stu-id="32cd1-136">`Ctrl+C` breaks out of `Start-Sleep`.</span></span>
  - <span data-ttu-id="32cd1-137">`Ctrl+C` bricht nicht aus `[Threading.Thread]::Sleep` .</span><span class="sxs-lookup"><span data-stu-id="32cd1-137">`Ctrl+C` does not break out of `[Threading.Thread]::Sleep`.</span></span> <span data-ttu-id="32cd1-138">Weitere Informationen finden Sie unter [Thread. Sleep-Methode](/dotnet/api/system.threading.thread.sleep).</span><span class="sxs-lookup"><span data-stu-id="32cd1-138">For more information, see [Thread.Sleep Method](/dotnet/api/system.threading.thread.sleep).</span></span>

## <span data-ttu-id="32cd1-139">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="32cd1-139">RELATED LINKS</span></span>