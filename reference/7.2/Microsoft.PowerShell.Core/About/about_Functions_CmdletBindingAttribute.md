---
description: Beschreibt das Attribut, mit dem eine Funktion wie ein kompiliertes Cmdlet funktioniert.
Locale: en-US
ms.date: 06/11/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_functions_cmdletbindingattribute?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Functions_CmdletBindingAttribute
ms.openlocfilehash: f1463bafc462ae2a266f5b1f6f4d71e3422f5831
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99602958"
---
# <a name="about-functions-cmdletbindingattribute"></a><span data-ttu-id="64b17-103">Informationen zu Funktionen cmdletbindingattribute</span><span class="sxs-lookup"><span data-stu-id="64b17-103">About Functions CmdletBindingAttribute</span></span>

## <a name="short-description"></a><span data-ttu-id="64b17-104">Kurze Beschreibung</span><span class="sxs-lookup"><span data-stu-id="64b17-104">Short description</span></span>
<span data-ttu-id="64b17-105">Beschreibt das Attribut, mit dem eine Funktion wie ein kompiliertes Cmdlet funktioniert.</span><span class="sxs-lookup"><span data-stu-id="64b17-105">Describes the attribute that makes a function work like a compiled cmdlet.</span></span>

## <a name="long-description"></a><span data-ttu-id="64b17-106">Lange Beschreibung</span><span class="sxs-lookup"><span data-stu-id="64b17-106">Long description</span></span>

<span data-ttu-id="64b17-107">Das- `CmdletBinding` Attribut ist ein Attribut von Funktionen, das Sie wie in c# geschriebene kompilierte Cmdlets funktionsfähig macht.</span><span class="sxs-lookup"><span data-stu-id="64b17-107">The `CmdletBinding` attribute is an attribute of functions that makes them operate like compiled cmdlets written in C#.</span></span> <span data-ttu-id="64b17-108">Sie ermöglicht den Zugriff auf die Features von Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="64b17-108">It provides access to the features of cmdlets.</span></span>

<span data-ttu-id="64b17-109">PowerShell bindet die Parameter von Funktionen, die über das- `CmdletBinding` Attribut verfügen, auf dieselbe Weise, wie die Parameter der kompilierten Cmdlets gebunden werden.</span><span class="sxs-lookup"><span data-stu-id="64b17-109">PowerShell binds the parameters of functions that have the `CmdletBinding` attribute in the same way that it binds the parameters of compiled cmdlets.</span></span> <span data-ttu-id="64b17-110">Die `$PSCmdlet` Automatische Variable ist für Funktionen mit dem- `CmdletBinding` Attribut verfügbar, aber die `$Args` Variable ist nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="64b17-110">The `$PSCmdlet` automatic variable is available to functions with the `CmdletBinding` attribute, but the `$Args` variable is not available.</span></span>

<span data-ttu-id="64b17-111">In Funktionen, die über das- `CmdletBinding` Attribut verfügen, führen unbekannte Parameter und Positions Argumente, die keine übereinstimmenden Positions Parameter aufweisen, zu einem Fehler bei der Parameter Bindung.</span><span class="sxs-lookup"><span data-stu-id="64b17-111">In functions that have the `CmdletBinding` attribute, unknown parameters and positional arguments that have no matching positional parameters cause parameter binding to fail.</span></span>

> [!NOTE]
> <span data-ttu-id="64b17-112">Kompilierte Cmdlets verwenden das erforderliche- `Cmdlet` Attribut, das dem `CmdletBinding` in diesem Thema beschriebenen-Attribut ähnelt.</span><span class="sxs-lookup"><span data-stu-id="64b17-112">Compiled cmdlets use the required `Cmdlet` attribute, which is similar to the `CmdletBinding` attribute that is described in this topic.</span></span>

## <a name="syntax"></a><span data-ttu-id="64b17-113">Syntax</span><span class="sxs-lookup"><span data-stu-id="64b17-113">Syntax</span></span>

<span data-ttu-id="64b17-114">Das folgende Beispiel zeigt das Format einer Funktion, die alle optionalen Argumente des `CmdletBinding` Attributs angibt.</span><span class="sxs-lookup"><span data-stu-id="64b17-114">The following example shows the format of a function that specifies all the optional arguments of the `CmdletBinding` attribute.</span></span> <span data-ttu-id="64b17-115">Das folgende Beispiel zeigt eine kurze Beschreibung der einzelnen Argumente.</span><span class="sxs-lookup"><span data-stu-id="64b17-115">A brief description of each argument follows this example.</span></span>

```powershell
{
    [CmdletBinding(ConfirmImpact=<String>,
    DefaultParameterSetName=<String>,
    HelpURI=<URI>,
    SupportsPaging=<Boolean>,
    SupportsShouldProcess=<Boolean>,
    PositionalBinding=<Boolean>)]

    Param ($Parameter1)
    Begin{}
    Process{}
    End{}
}
```

## <a name="confirmimpact"></a><span data-ttu-id="64b17-116">ConfirmImpact</span><span class="sxs-lookup"><span data-stu-id="64b17-116">ConfirmImpact</span></span>

<span data-ttu-id="64b17-117">Das **confirmimpact** -Argument gibt an, **wann die Aktion** der Funktion durch einen-aufrufungstyp bestätigt werden soll.</span><span class="sxs-lookup"><span data-stu-id="64b17-117">The **ConfirmImpact** argument specifies when the action of the function should be confirmed by a call to the **ShouldProcess** method.</span></span> <span data-ttu-id="64b17-118">**Der Aufrufe der Methode "** zugsmethode" zeigt nur dann eine Bestätigungsaufforderung an, wenn das " **confirmimpact** "-Argument größer oder gleich dem Wert der "Preference"- `$ConfirmPreference` Variablen ist.</span><span class="sxs-lookup"><span data-stu-id="64b17-118">The call to the **ShouldProcess** method displays a confirmation prompt only when the **ConfirmImpact** argument is equal to or greater than the value of the `$ConfirmPreference` preference variable.</span></span> <span data-ttu-id="64b17-119">(Der Standardwert des Arguments ist " **Medium**".) Geben Sie dieses Argument nur an, wenn das **supportsrechtdprocess** -Argument ebenfalls angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="64b17-119">(The default value of the argument is **Medium**.) Specify this argument only when the **SupportsShouldProcess** argument is also specified.</span></span>

<span data-ttu-id="64b17-120">Weitere Informationen zu Bestätigungs Anforderungen finden Sie unter [Anfordern einer Bestätigung](/powershell/scripting/developer/cmdlet/requesting-confirmation).</span><span class="sxs-lookup"><span data-stu-id="64b17-120">For more information about confirmation requests, see [Requesting Confirmation](/powershell/scripting/developer/cmdlet/requesting-confirmation).</span></span>

## <a name="defaultparametersetname"></a><span data-ttu-id="64b17-121">DefaultParameterSetName</span><span class="sxs-lookup"><span data-stu-id="64b17-121">DefaultParameterSetName</span></span>

<span data-ttu-id="64b17-122">Das **defaultparametersetname** -Argument gibt den Namen des Parameter Satzes an, den PowerShell verwenden soll, wenn er nicht ermitteln kann, welcher Parameter verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="64b17-122">The **DefaultParameterSetName** argument specifies the name of the parameter set that PowerShell will attempt to use when it cannot determine which parameter set to use.</span></span> <span data-ttu-id="64b17-123">Sie können dieses Problem vermeiden, indem Sie den Unique-Parameter jedes Parameters für einen obligatorischen Parameter festlegen.</span><span class="sxs-lookup"><span data-stu-id="64b17-123">You can avoid this issue by making the unique parameter of each parameter set a mandatory parameter.</span></span>

## <a name="helpuri"></a><span data-ttu-id="64b17-124">HelpURI</span><span class="sxs-lookup"><span data-stu-id="64b17-124">HelpURI</span></span>

<span data-ttu-id="64b17-125">Das **HelpUri** -Argument gibt die Internetadresse der Online Version des Hilfe Themas an, das die Funktion beschreibt.</span><span class="sxs-lookup"><span data-stu-id="64b17-125">The **HelpURI** argument specifies the internet address of the online version of the help topic that describes the function.</span></span> <span data-ttu-id="64b17-126">Der Wert des **HelpUri** -Arguments muss mit "http" oder "https" beginnen.</span><span class="sxs-lookup"><span data-stu-id="64b17-126">The value of the **HelpURI** argument must begin with "http" or "https".</span></span>

<span data-ttu-id="64b17-127">Der **HelpUri** -Argument Wert wird für den Wert der **HelpUri** -Eigenschaft des **CommandInfo** -Objekts verwendet, das `Get-Command` für die Funktion zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="64b17-127">The **HelpURI** argument value is used for the value of the **HelpURI** property of the **CommandInfo** object that `Get-Command` returns for the function.</span></span>

<span data-ttu-id="64b17-128">Wenn jedoch Hilfedateien auf dem Computer installiert sind und der Wert des ersten Links im Abschnitt **relatedLinks** der Hilfedatei ein URI ist oder der Wert der ersten `.Link` Anweisung in der Kommentar basierten Hilfe ein URI ist, wird der URI in der Hilfedatei als Wert der **HelpUri** -Eigenschaft der Funktion verwendet.</span><span class="sxs-lookup"><span data-stu-id="64b17-128">However, when help files are installed on the computer and the value of the first link in the **RelatedLinks** section of the help file is a URI, or the value of the first `.Link` directive in comment-based help is a URI, the URI in the help file is used as the value of the **HelpUri** property of the function.</span></span>

<span data-ttu-id="64b17-129">Das `Get-Help` -Cmdlet verwendet den Wert der **HelpUri** -Eigenschaft, um die Online Version des Hilfe Themas der Funktion zu finden, wenn der **Online-** Parameter von `Get-Help` in einem Befehl angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="64b17-129">The `Get-Help` cmdlet uses the value of the **HelpURI** property to locate the online version of the function help topic when the **Online** parameter of `Get-Help` is specified in a command.</span></span>

## <a name="supportspaging"></a><span data-ttu-id="64b17-130">Supportspaging</span><span class="sxs-lookup"><span data-stu-id="64b17-130">SupportsPaging</span></span>

<span data-ttu-id="64b17-131">Das **supportspaging** -Argument fügt der Funktion die Parameter " **First**", " **Skip**" und " **IncludeTotalCount** " hinzu.</span><span class="sxs-lookup"><span data-stu-id="64b17-131">The **SupportsPaging** argument adds the **First**, **Skip**, and **IncludeTotalCount** parameters to the function.</span></span> <span data-ttu-id="64b17-132">Diese Parameter ermöglichen es Benutzern, die Ausgabe eines sehr großen Resultsets auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="64b17-132">These parameters allow users to select output from a very large result set.</span></span> <span data-ttu-id="64b17-133">Dieses Argument wurde für Cmdlets und Funktionen entwickelt, die Daten aus großen Daten speichern zurückgeben, die die Datenauswahl unterstützen, z. b. eine SQL-Datenbank.</span><span class="sxs-lookup"><span data-stu-id="64b17-133">This argument is designed for cmdlets and functions that return data from large data stores that support data selection, such as an SQL database.</span></span>

<span data-ttu-id="64b17-134">Dieses Argument wurde in Windows PowerShell 3,0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="64b17-134">This argument was introduced in Windows PowerShell 3.0.</span></span>

- <span data-ttu-id="64b17-135">**First**: Ruft nur die ersten ' n '-Objekte ab.</span><span class="sxs-lookup"><span data-stu-id="64b17-135">**First**: Gets only the first 'n' objects.</span></span>
- <span data-ttu-id="64b17-136">**Skip**: ignoriert die ersten ' n '-Objekte und ruft dann die übrigen Objekte ab.</span><span class="sxs-lookup"><span data-stu-id="64b17-136">**Skip**:  Ignores the first 'n' objects and then gets the remaining objects.</span></span>
- <span data-ttu-id="64b17-137">**Incluabtotalcount**: gibt die Anzahl der-Objekte im DataSet (eine ganze Zahl) an, gefolgt von den-Objekten.</span><span class="sxs-lookup"><span data-stu-id="64b17-137">**IncludeTotalCount**: Reports the number of objects in the data set (an integer) followed by the objects.</span></span> <span data-ttu-id="64b17-138">Wenn das Cmdlet die Gesamtanzahl nicht ermitteln kann, wird "unbekannte Gesamtanzahl" zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="64b17-138">If the cmdlet cannot determine the total count, it returns "Unknown total count".</span></span>

<span data-ttu-id="64b17-139">PowerShell enthält **newtotalcount**, eine Hilfsmethode, die den zurück zugebende Gesamtzahl Wert abruft und eine Schätzung der Genauigkeit des Gesamtanzahl Werts enthält.</span><span class="sxs-lookup"><span data-stu-id="64b17-139">PowerShell includes **NewTotalCount**, a helper method that gets the total count value to return and includes an estimate of the accuracy of the total count value.</span></span>

<span data-ttu-id="64b17-140">Die folgende Beispiel Funktion zeigt, wie Sie eine Unterstützung für die Paging-Parameter einer erweiterten Funktion hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="64b17-140">The following sample function shows how to add support for the paging parameters to an advanced function.</span></span>

```powershell
function Get-Numbers {
    [CmdletBinding(SupportsPaging = $true)]
    param()

    $FirstNumber = [Math]::Min($PSCmdlet.PagingParameters.Skip, 100)
    $LastNumber = [Math]::Min($PSCmdlet.PagingParameters.First +
      $FirstNumber - 1, 100)

    if ($PSCmdlet.PagingParameters.IncludeTotalCount) {
        $TotalCountAccuracy = 1.0
        $TotalCount = $PSCmdlet.PagingParameters.NewTotalCount(100,
          $TotalCountAccuracy)
        Write-Output $TotalCount
    }
    $FirstNumber .. $LastNumber | Write-Output
}
```

## <a name="supportsshouldprocess"></a><span data-ttu-id="64b17-141">SupportsShouldProcess</span><span class="sxs-lookup"><span data-stu-id="64b17-141">SupportsShouldProcess</span></span>

<span data-ttu-id="64b17-142">Das **supportsschulter dprocess** -Argument fügt der Funktion die Parameter **Confirm** und **WhatIf** hinzu.</span><span class="sxs-lookup"><span data-stu-id="64b17-142">The **SupportsShouldProcess** argument adds **Confirm** and **WhatIf** parameters to the function.</span></span> <span data-ttu-id="64b17-143">Der **Confirm** -Parameter fordert den Benutzer auf, bevor er den Befehl für jedes Objekt in der Pipeline ausführt.</span><span class="sxs-lookup"><span data-stu-id="64b17-143">The **Confirm** parameter prompts the user before it runs the command on each object in the pipeline.</span></span> <span data-ttu-id="64b17-144">Der Parameter **WhatIf** listet die Änderungen auf, die der Befehl durchführen würde, anstatt den Befehl zu ausführen.</span><span class="sxs-lookup"><span data-stu-id="64b17-144">The **WhatIf** parameter lists the changes that the command would make, instead of running the command.</span></span>

## <a name="positionalbinding"></a><span data-ttu-id="64b17-145">PositionalBinding</span><span class="sxs-lookup"><span data-stu-id="64b17-145">PositionalBinding</span></span>

<span data-ttu-id="64b17-146">Das **positionalbinding** -Argument bestimmt, ob Parameter in der Funktion standardmäßig Positionswerte sind.</span><span class="sxs-lookup"><span data-stu-id="64b17-146">The **PositionalBinding** argument determines whether parameters in the function are positional by default.</span></span> <span data-ttu-id="64b17-147">Der Standardwert ist `$True`.</span><span class="sxs-lookup"><span data-stu-id="64b17-147">The default value is `$True`.</span></span> <span data-ttu-id="64b17-148">Sie können das **positionalbinding** -Argument mit einem Wert von verwenden `$False` , um die Positions Bindung zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="64b17-148">You can use the **PositionalBinding** argument with a value of `$False` to disable positional binding.</span></span>

<span data-ttu-id="64b17-149">Das **positionalbinding** -Argument wird in Windows PowerShell 3,0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="64b17-149">The **PositionalBinding** argument is introduced in Windows PowerShell 3.0.</span></span>

<span data-ttu-id="64b17-150">Wenn Parameter Positionswerte sind, ist der Parameter Name optional.</span><span class="sxs-lookup"><span data-stu-id="64b17-150">When parameters are positional, the parameter name is optional.</span></span>
<span data-ttu-id="64b17-151">PowerShell ordnet unbenannte Parameterwerte den Funktionsparametern entsprechend der Reihenfolge oder Position der unbenannten Parameterwerte im Funktionsbefehl zu.</span><span class="sxs-lookup"><span data-stu-id="64b17-151">PowerShell associates unnamed parameter values with the function parameters according to the order or position of the unnamed parameter values in the function command.</span></span>

<span data-ttu-id="64b17-152">Wenn Parameter nicht Positions fähig sind (Sie sind "named"), ist der Parameter Name (oder eine Abkürzung oder ein Alias des Namens) im Befehl erforderlich.</span><span class="sxs-lookup"><span data-stu-id="64b17-152">When parameters are not positional (they are "named"), the parameter name (or an abbreviation or alias of the name) is required in the command.</span></span>

<span data-ttu-id="64b17-153">Wenn **positionalbinding** ist `$True` , sind Funktionsparameter standardmäßig Positions fähig.</span><span class="sxs-lookup"><span data-stu-id="64b17-153">When **PositionalBinding** is `$True`, function parameters are positional by default.</span></span> <span data-ttu-id="64b17-154">PowerShell weist den Parametern die Positionsnummer in der Reihenfolge zu, in der Sie in der Funktion deklariert werden.</span><span class="sxs-lookup"><span data-stu-id="64b17-154">PowerShell assigns position number to the parameters in the order in which they are declared in the function.</span></span>

<span data-ttu-id="64b17-155">Wenn **positionalbinding** ist `$False` , sind Funktionsparameter standardmäßig nicht Positions fähig.</span><span class="sxs-lookup"><span data-stu-id="64b17-155">When **PositionalBinding** is `$False`, function parameters are not positional by default.</span></span> <span data-ttu-id="64b17-156">Wenn das **Positions** Argument des **Parameter** Attributs nicht für den Parameter deklariert ist, muss der Parameter Name (oder ein Alias oder eine Abkürzung) eingeschlossen werden, wenn der Parameter in einer Funktion verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="64b17-156">Unless the **Position** argument of the **Parameter** attribute is declared on the parameter, the parameter name (or an alias or abbreviation) must be included when the parameter is used in a function.</span></span>

<span data-ttu-id="64b17-157">Das **Positions** Argument des **Parameter** Attributs hat Vorrang vor dem Standardwert **positionalbinding** .</span><span class="sxs-lookup"><span data-stu-id="64b17-157">The **Position** argument of the **Parameter** attribute takes precedence over the **PositionalBinding** default value.</span></span> <span data-ttu-id="64b17-158">Sie können das **Positions** Argument verwenden, um einen Positionswert für einen Parameter anzugeben.</span><span class="sxs-lookup"><span data-stu-id="64b17-158">You can use the **Position** argument to specify a position value for a parameter.</span></span> <span data-ttu-id="64b17-159">Weitere Informationen zum **Positions** Argument finden Sie unter [about_Functions_Advanced_Parameters](about_Functions_Advanced_Parameters.md).</span><span class="sxs-lookup"><span data-stu-id="64b17-159">For more information about the **Position** argument, see [about_Functions_Advanced_Parameters](about_Functions_Advanced_Parameters.md).</span></span>

## <a name="notes"></a><span data-ttu-id="64b17-160">Notizen</span><span class="sxs-lookup"><span data-stu-id="64b17-160">Notes</span></span>

<span data-ttu-id="64b17-161">Das **supportstransactions** -Argument wird in erweiterten Funktionen nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="64b17-161">The **SupportsTransactions** argument is not supported in advanced functions.</span></span>

## <a name="keywords"></a><span data-ttu-id="64b17-162">Keywords</span><span class="sxs-lookup"><span data-stu-id="64b17-162">Keywords</span></span>

<span data-ttu-id="64b17-163">about_Functions_CmdletBinding_Attribute</span><span class="sxs-lookup"><span data-stu-id="64b17-163">about_Functions_CmdletBinding_Attribute</span></span>

## <a name="see-also"></a><span data-ttu-id="64b17-164">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="64b17-164">See also</span></span>

[<span data-ttu-id="64b17-165">about_Functions</span><span class="sxs-lookup"><span data-stu-id="64b17-165">about_Functions</span></span>](about_Functions.md)

[<span data-ttu-id="64b17-166">about_Functions_Advanced</span><span class="sxs-lookup"><span data-stu-id="64b17-166">about_Functions_Advanced</span></span>](about_Functions_Advanced.md)

[<span data-ttu-id="64b17-167">about_Functions_Advanced_Methods</span><span class="sxs-lookup"><span data-stu-id="64b17-167">about_Functions_Advanced_Methods</span></span>](about_Functions_Advanced_Methods.md)

[<span data-ttu-id="64b17-168">about_Functions_Advanced_Parameters</span><span class="sxs-lookup"><span data-stu-id="64b17-168">about_Functions_Advanced_Parameters</span></span>](about_Functions_Advanced_Parameters.md)

[<span data-ttu-id="64b17-169">about_Functions_OutputTypeAttribute</span><span class="sxs-lookup"><span data-stu-id="64b17-169">about_Functions_OutputTypeAttribute</span></span>](about_Functions_OutputTypeAttribute.md)