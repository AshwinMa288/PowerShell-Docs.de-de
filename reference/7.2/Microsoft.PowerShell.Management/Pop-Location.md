---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 02/04/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/pop-location?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Pop-Location
ms.openlocfilehash: 8a44849f27de80ece486b573f1adccafab51972a
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99602115"
---
# <span data-ttu-id="0f115-102">Pop-Location</span><span class="sxs-lookup"><span data-stu-id="0f115-102">Pop-Location</span></span>

## <span data-ttu-id="0f115-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="0f115-103">SYNOPSIS</span></span>
<span data-ttu-id="0f115-104">Ändert den aktuellen Speicherort in den Speicherort, der zuletzt auf den Stapel verschoben wurde.</span><span class="sxs-lookup"><span data-stu-id="0f115-104">Changes the current location to the location most recently pushed onto the stack.</span></span>

## <span data-ttu-id="0f115-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="0f115-105">SYNTAX</span></span>

```
Pop-Location [-PassThru] [-StackName <String>] [<CommonParameters>]
```

## <span data-ttu-id="0f115-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="0f115-106">DESCRIPTION</span></span>

<span data-ttu-id="0f115-107">Mit dem- `Pop-Location` Cmdlet wird der aktuelle Speicherort in den Speicherort geändert, der zuletzt mit dem-Cmdlet auf den Stapel verschoben wurde `Push-Location` .</span><span class="sxs-lookup"><span data-stu-id="0f115-107">The `Pop-Location` cmdlet changes the current location to the location most recently pushed onto the stack by using the `Push-Location` cmdlet.</span></span> <span data-ttu-id="0f115-108">Sie können einen Speicherort vom Standard Stapel oder von einem Stapel erstellen, den Sie mit einem `Push-Location` Befehl erstellen.</span><span class="sxs-lookup"><span data-stu-id="0f115-108">You can pop a location from the default stack or from a stack that you create by using a `Push-Location` command.</span></span>

## <span data-ttu-id="0f115-109">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="0f115-109">EXAMPLES</span></span>

### <span data-ttu-id="0f115-110">Beispiel 1: Ändern des aktuellen Speicher Orts</span><span class="sxs-lookup"><span data-stu-id="0f115-110">Example 1: Change to most recent location</span></span>

```
PS C:\> Pop-Location
```

<span data-ttu-id="0f115-111">Mit diesem Befehl wird der Speicherort in den Speicherort geändert, der dem aktuellen Stapel zuletzt hinzugefügt wurde.</span><span class="sxs-lookup"><span data-stu-id="0f115-111">This command changes your location to the location most recently added to the current stack.</span></span>

### <span data-ttu-id="0f115-112">Beispiel 2: Ändern des aktuellen Speicher Orts in einem benannten Stapel</span><span class="sxs-lookup"><span data-stu-id="0f115-112">Example 2: Change to most recent location in a named stack</span></span>

```
PS C:\> Pop-Location -StackName "Stack2"
```

<span data-ttu-id="0f115-113">Mit diesem Befehl wird der Speicherort in den Speicherort geändert, der dem Speicherstapel %%amp;quot;Stack2%%amp;quot; zuletzt hinzugefügt wurde.</span><span class="sxs-lookup"><span data-stu-id="0f115-113">This command changes your location to the location most recently added to the Stack2 location stack.</span></span>

<span data-ttu-id="0f115-114">Weitere Informationen zu Speicherort Stapeln finden Sie in den [hinweisen](#notes).</span><span class="sxs-lookup"><span data-stu-id="0f115-114">For more information about location stacks, see the [Notes](#notes).</span></span>

### <span data-ttu-id="0f115-115">Beispiel 3: wechseln Zwischenstand Orten für verschiedene Anbieter</span><span class="sxs-lookup"><span data-stu-id="0f115-115">Example 3: Move between locations for different providers</span></span>

```
PS C:\> pushd HKLM:\Software\Microsoft\PowerShell
PS HKLM:\Software\Microsoft\PowerShell> pushd Cert:\LocalMachine\TrustedPublisher
PS cert:\LocalMachine\TrustedPublisher> popd
PS HKLM:\Software\Microsoft\PowerShell> popd
PS C:\>
```

<span data-ttu-id="0f115-116">Diese Befehle verwenden die `Push-Location` `Pop-Location` Cmdlets und, um Zwischenstand Orten zu wechseln, die von verschiedenen PowerShell-Anbietern unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="0f115-116">These commands use the `Push-Location` and `Pop-Location` cmdlets to move between locations supported by different PowerShell providers.</span></span> <span data-ttu-id="0f115-117">Die Befehle verwenden den `pushd` Alias für `Push-Location` und den `popd` Alias für `Pop-Location` .</span><span class="sxs-lookup"><span data-stu-id="0f115-117">The commands use the `pushd` alias for `Push-Location` and the `popd` alias for `Pop-Location`.</span></span>

<span data-ttu-id="0f115-118">Mit dem ersten Befehl wird der aktuelle Dateisystem Speicherort auf den Stapel verschoben und zum HKLM-Laufwerk gewechselt, das vom PowerShell-Registrierungs Anbieter unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="0f115-118">The first command pushes the current file system location onto the stack and moves to the HKLM drive supported by the PowerShell Registry provider.</span></span>

<span data-ttu-id="0f115-119">Mit dem zweiten Befehl wird der Registrierungs Speicherort auf den Stapel verschoben und zu einem Speicherort gewechselt, der vom PowerShell-Zertifikat Anbieter unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="0f115-119">The second command pushes the registry location onto the stack and moves to a location supported by the PowerShell certificate provider.</span></span>

<span data-ttu-id="0f115-120">Mit den letzten beiden Befehlen werden diese Speicherorte vom Stapel abgerufen.</span><span class="sxs-lookup"><span data-stu-id="0f115-120">The last two commands pop those locations off the stack.</span></span> <span data-ttu-id="0f115-121">Der erste `popd` Befehl kehrt zum Registrierungs Laufwerk zurück, und der zweite Befehl kehrt zum Dateisystem Laufwerk zurück.</span><span class="sxs-lookup"><span data-stu-id="0f115-121">The first `popd` command returns to the Registry drive, and the second command returns to the file system drive.</span></span>

## <span data-ttu-id="0f115-122">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="0f115-122">PARAMETERS</span></span>

### <span data-ttu-id="0f115-123">-PassThru</span><span class="sxs-lookup"><span data-stu-id="0f115-123">-PassThru</span></span>

<span data-ttu-id="0f115-124">Übergibt ein Objekt, das den Speicherort darstellt, an die Pipeline.</span><span class="sxs-lookup"><span data-stu-id="0f115-124">Passes an object that represents the location to the pipeline.</span></span> <span data-ttu-id="0f115-125">Standardmäßig wird von diesem Cmdlet keine Ausgabe generiert.</span><span class="sxs-lookup"><span data-stu-id="0f115-125">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="0f115-126">-Stackname</span><span class="sxs-lookup"><span data-stu-id="0f115-126">-StackName</span></span>

<span data-ttu-id="0f115-127">Gibt den Speicherstapel an, von dem der Speicherort abgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="0f115-127">Specifies the location stack from which the location is popped.</span></span> <span data-ttu-id="0f115-128">Geben Sie einen Speicherstapelnamen ein.</span><span class="sxs-lookup"><span data-stu-id="0f115-128">Enter a location stack name.</span></span>

<span data-ttu-id="0f115-129">Ohne diesen Parameter wird `Pop-Location` ein Speicherort vom aktuellen Speicher Stapel angezeigt.</span><span class="sxs-lookup"><span data-stu-id="0f115-129">Without this parameter, `Pop-Location` pops a location from the current location stack.</span></span> <span data-ttu-id="0f115-130">Standardmäßig ist der aktuelle Speicher Stapel der unbenannte Standard Speicherort Stapel, den PowerShell erstellt.</span><span class="sxs-lookup"><span data-stu-id="0f115-130">By default, the current location stack is the unnamed default location stack that PowerShell creates.</span></span> <span data-ttu-id="0f115-131">Verwenden Sie den **stackname** -Parameter des Cmdlets, um einen Speicherort Stapel zum aktuellen Speicherort Stapel zu machen `Set-Location` .</span><span class="sxs-lookup"><span data-stu-id="0f115-131">To make a location stack the current location stack, use the **StackName** parameter of the `Set-Location` cmdlet.</span></span> <span data-ttu-id="0f115-132">Weitere Informationen zu Speicherort Stapeln finden Sie in den [hinweisen](#notes).</span><span class="sxs-lookup"><span data-stu-id="0f115-132">For more information about location stacks, see the [Notes](#notes).</span></span>

<span data-ttu-id="0f115-133">`Pop-Location` ein Speicherort kann nicht aus dem unbenannten Standard Stapel entfernt werden, es sei denn, er ist der aktuelle Speicher Stapel</span><span class="sxs-lookup"><span data-stu-id="0f115-133">`Pop-Location` cannot pop a location from the unnamed default stack unless it is the current location stack.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="0f115-134">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="0f115-134">CommonParameters</span></span>

<span data-ttu-id="0f115-135">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="0f115-135">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="0f115-136">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="0f115-136">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="0f115-137">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="0f115-137">INPUTS</span></span>

### <span data-ttu-id="0f115-138">Keine</span><span class="sxs-lookup"><span data-stu-id="0f115-138">None</span></span>

<span data-ttu-id="0f115-139">Eingaben können nicht an dieses Cmdlet weitergereicht werden.</span><span class="sxs-lookup"><span data-stu-id="0f115-139">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="0f115-140">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="0f115-140">OUTPUTS</span></span>

### <span data-ttu-id="0f115-141">Keine, System. Management. Automation. PathInfo</span><span class="sxs-lookup"><span data-stu-id="0f115-141">None, System.Management.Automation.PathInfo</span></span>

<span data-ttu-id="0f115-142">Dieses Cmdlet generiert ein **System. Management. Automation. PathInfo** -Objekt, das den Speicherort darstellt, wenn Sie den **passthru** -Parameter angeben.</span><span class="sxs-lookup"><span data-stu-id="0f115-142">This cmdlet generates a **System.Management.Automation.PathInfo** object that represents the location, if you specify the **PassThru** parameter.</span></span> <span data-ttu-id="0f115-143">Andernfalls wird von diesem Cmdlet keine Ausgabe generiert.</span><span class="sxs-lookup"><span data-stu-id="0f115-143">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="0f115-144">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="0f115-144">NOTES</span></span>

<span data-ttu-id="0f115-145">PowerShell unterstützt mehrere Runspaces pro Prozess.</span><span class="sxs-lookup"><span data-stu-id="0f115-145">PowerShell supports multiple runspaces per process.</span></span> <span data-ttu-id="0f115-146">Jeder Runspace verfügt über ein eigenes _Aktuelles Verzeichnis_.</span><span class="sxs-lookup"><span data-stu-id="0f115-146">Each runspace has its own _current directory_.</span></span>
<span data-ttu-id="0f115-147">Dies ist nicht identisch mit `[System.Environment]::CurrentDirectory` .</span><span class="sxs-lookup"><span data-stu-id="0f115-147">This is not the same as `[System.Environment]::CurrentDirectory`.</span></span> <span data-ttu-id="0f115-148">Dieses Verhalten kann ein Problem sein, wenn Sie .NET-APIs aufrufen oder native Anwendungen ausführen, ohne explizite Verzeichnispfade bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="0f115-148">This behavior can be an issue when calling .NET APIs or running native applications without providing explicit directory paths.</span></span>

<span data-ttu-id="0f115-149">Auch wenn die Location-Cmdlets das aktuelle Prozess weite Verzeichnis festgelegt haben, können Sie nicht davon abhängen, weil es von einem anderen Runspace möglicherweise jederzeit geändert wird.</span><span class="sxs-lookup"><span data-stu-id="0f115-149">Even if the location cmdlets did set the process-wide current directory, you can't depend on it because another runspace might change it at any time.</span></span> <span data-ttu-id="0f115-150">Verwenden Sie die Location-Cmdlets zum Ausführen von Pfad basierten Vorgängen mit dem aktuellen Arbeitsverzeichnis, das für den aktuellen Runspace spezifisch ist.</span><span class="sxs-lookup"><span data-stu-id="0f115-150">You should use the location cmdlets to perform path-based operations using the current working directory specific to the current runspace.</span></span>

<span data-ttu-id="0f115-151">Bei einem Stapel handelt es sich um eine Last-in-First-out-Liste, in der nur auf das zuletzt hinzugefügte Element zugegriffen werden kann.</span><span class="sxs-lookup"><span data-stu-id="0f115-151">A stack is a last-in, first-out list in which only the most recently added item can be accessed.</span></span> <span data-ttu-id="0f115-152">Sie fügen einem Stapel Elemente in der Reihenfolge hinzu, in der Sie sie verwenden. Anschließend rufen Sie sie zur Verwendung in der umgekehrten Reihenfolge auf.</span><span class="sxs-lookup"><span data-stu-id="0f115-152">You add items to a stack in the order that you use them, and then retrieve them for use in the reverse order.</span></span> <span data-ttu-id="0f115-153">Mit PowerShell können Sie Anbieter Speicherorte in Speicherort Stapeln speichern.</span><span class="sxs-lookup"><span data-stu-id="0f115-153">PowerShell lets you store provider locations in location stacks.</span></span>

<span data-ttu-id="0f115-154">Von PowerShell wird ein unbenannter Standard Speicher Stapel erstellt, und Sie können mehrere benannte Speicher Stapel erstellen.</span><span class="sxs-lookup"><span data-stu-id="0f115-154">PowerShell creates an unnamed default location stack and you can create multiple named location stacks.</span></span> <span data-ttu-id="0f115-155">Wenn Sie keinen Stapelnamen angeben, verwendet PowerShell den aktuellen Speicher Stapel.</span><span class="sxs-lookup"><span data-stu-id="0f115-155">If you do not specify a stack name, PowerShell uses the current location stack.</span></span> <span data-ttu-id="0f115-156">Standardmäßig ist der unbenannte Standard Speicherort der aktuelle Speicher Stapel. Sie können das `Set-Location` Cmdlet jedoch verwenden, um den aktuellen Speicher Stapel zu ändern.</span><span class="sxs-lookup"><span data-stu-id="0f115-156">By default, the unnamed default location is the current location stack, but you can use the `Set-Location` cmdlet to change the current location stack.</span></span>

<span data-ttu-id="0f115-157">Verwenden Sie zum Verwalten von Speicherort Stapeln die PowerShell- `*-Location` Cmdlets wie folgt:</span><span class="sxs-lookup"><span data-stu-id="0f115-157">To manage location stacks, use the PowerShell `*-Location` cmdlets, as follows:</span></span>

- <span data-ttu-id="0f115-158">Verwenden Sie das-Cmdlet, um einen Speicherort zu einem Speicherort Stapel hinzuzufügen `Push-Location` .</span><span class="sxs-lookup"><span data-stu-id="0f115-158">To add a location to a location stack, use the `Push-Location` cmdlet.</span></span>

- <span data-ttu-id="0f115-159">Verwenden Sie das-Cmdlet, um einen Speicherort aus einem Speicherort Stapel zu erhalten `Pop-Location` .</span><span class="sxs-lookup"><span data-stu-id="0f115-159">To get a location from a location stack, use the `Pop-Location` cmdlet.</span></span>

- <span data-ttu-id="0f115-160">Um die Speicherorte im aktuellen Speicher Stapel anzuzeigen, verwenden Sie den **Stack** -Parameter des `Get-Location` Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="0f115-160">To display the locations in the current location stack, use the **Stack** parameter of the `Get-Location` cmdlet.</span></span>

- <span data-ttu-id="0f115-161">Um die Speicherorte in einem benannten Positions Stapel anzuzeigen, verwenden Sie den **stackname** -Parameter des `Get-Location` Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="0f115-161">To display the locations in a named location stack, use the **StackName** parameter of the `Get-Location` cmdlet.</span></span>

- <span data-ttu-id="0f115-162">Um einen neuen Speicherort Stapel zu erstellen, verwenden Sie den **stackname** -Parameter des `Push-Location` Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="0f115-162">To create a new location stack, use the **StackName** parameter of the `Push-Location` cmdlet.</span></span> <span data-ttu-id="0f115-163">Wenn Sie einen Stapel angeben, der nicht vorhanden ist, wird `Push-Location` der Stapel von erstellt.</span><span class="sxs-lookup"><span data-stu-id="0f115-163">If you specify a stack that does not exist, `Push-Location` creates the stack.</span></span>

- <span data-ttu-id="0f115-164">Verwenden Sie den **stackname** -Parameter des Cmdlets, um einen Speicherort Stapel zum aktuellen Speicherort Stapel zu machen `Set-Location` .</span><span class="sxs-lookup"><span data-stu-id="0f115-164">To make a location stack the current location stack, use the **StackName** parameter of the `Set-Location` cmdlet.</span></span>

<span data-ttu-id="0f115-165">Auf den unbenannten Standardspeicherstapel kann nur vollständig zugegriffen werden, wenn es sich dabei um den aktuellen Speicherstapel handelt.</span><span class="sxs-lookup"><span data-stu-id="0f115-165">The unnamed default location stack is fully accessible only when it is the current location stack.</span></span>
<span data-ttu-id="0f115-166">Wenn Sie einen benannten Speicherort Stapel zum aktuellen Speicher Stapel machen, können Sie die `Push-Location` Cmdlets oder nicht mehr verwenden, `Pop-Location` um Elemente zum Standard Stapel hinzuzufügen oder daraus zu machen. Sie können auch das `Get-Location` Cmdlet verwenden, um die Speicherorte im unbenannten Stapel anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="0f115-166">If you make a named location stack the current location stack, you can no longer use the `Push-Location` or `Pop-Location` cmdlets to add or get items from the default stack or use the `Get-Location` cmdlet to display the locations in the unnamed stack.</span></span> <span data-ttu-id="0f115-167">Um den unbenannten Stapel zum aktuellen Stapel zu machen, verwenden Sie den **stackname** -Parameter des `Set-Location` Cmdlets mit dem Wert `$Null` oder einer leeren Zeichenfolge ( `""` ).</span><span class="sxs-lookup"><span data-stu-id="0f115-167">To make the unnamed stack the current stack, use the **StackName** parameter of the `Set-Location` cmdlet with a value of `$Null` or an empty string (`""`).</span></span>

<span data-ttu-id="0f115-168">Sie können auch auf den `Pop-Location` integrierten Alias verweisen `popd` .</span><span class="sxs-lookup"><span data-stu-id="0f115-168">You can also refer to `Pop-Location` by its built-in alias, `popd`.</span></span> <span data-ttu-id="0f115-169">Weitere Informationen finden Sie unter [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).</span><span class="sxs-lookup"><span data-stu-id="0f115-169">For more information, see [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).</span></span>

<span data-ttu-id="0f115-170">`Pop-Location` ist für die Arbeit mit den Daten konzipiert, die von beliebigen Anbietern verfügbar gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="0f115-170">`Pop-Location` is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="0f115-171">Um die in Ihrer Sitzung verfügbaren Anbieter aufzulisten, geben Sie ein `Get-PSProvider` .</span><span class="sxs-lookup"><span data-stu-id="0f115-171">To list the providers available in your session, type `Get-PSProvider`.</span></span> <span data-ttu-id="0f115-172">Weitere Informationen finden Sie unter [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="0f115-172">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="0f115-173">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="0f115-173">RELATED LINKS</span></span>

[<span data-ttu-id="0f115-174">Get-Location</span><span class="sxs-lookup"><span data-stu-id="0f115-174">Get-Location</span></span>](Get-Location.md)

[<span data-ttu-id="0f115-175">Push-Location</span><span class="sxs-lookup"><span data-stu-id="0f115-175">Push-Location</span></span>](Push-Location.md)

[<span data-ttu-id="0f115-176">Set-Location</span><span class="sxs-lookup"><span data-stu-id="0f115-176">Set-Location</span></span>](Set-Location.md)

[<span data-ttu-id="0f115-177">about_Aliases</span><span class="sxs-lookup"><span data-stu-id="0f115-177">about_Aliases</span></span>](../Microsoft.PowerShell.Core/About/about_Aliases.md)

[<span data-ttu-id="0f115-178">about_Providers</span><span class="sxs-lookup"><span data-stu-id="0f115-178">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)