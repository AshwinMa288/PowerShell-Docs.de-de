---
description: Beschreibt das Erstellen und Verwenden von Funktionen in PowerShell.
Locale: en-US
ms.date: 02/27/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_functions?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Functions
ms.openlocfilehash: d51c4d0bbf728bb23b4a5452d5192a262b722758
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99600503"
---
# <a name="about-functions"></a><span data-ttu-id="7eeba-103">Informationen zu Functions</span><span class="sxs-lookup"><span data-stu-id="7eeba-103">About Functions</span></span>

## <a name="short-description"></a><span data-ttu-id="7eeba-104">Kurze Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7eeba-104">Short description</span></span>

<span data-ttu-id="7eeba-105">Beschreibt das Erstellen und Verwenden von Funktionen in PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7eeba-105">Describes how to create and use functions in PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="7eeba-106">Lange Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7eeba-106">Long description</span></span>

<span data-ttu-id="7eeba-107">Eine Funktion ist eine Liste von PowerShell-Anweisungen, die einen Namen haben, den Sie zuweisen.</span><span class="sxs-lookup"><span data-stu-id="7eeba-107">A function is a list of PowerShell statements that has a name that you assign.</span></span> <span data-ttu-id="7eeba-108">Wenn Sie eine Funktion ausführen, geben Sie den Namen der Funktion ein.</span><span class="sxs-lookup"><span data-stu-id="7eeba-108">When you run a function, you type the function name.</span></span> <span data-ttu-id="7eeba-109">Die Anweisungen in der Liste werden so ausgeführt, als würden Sie Sie an der Eingabeaufforderung eingegeben haben.</span><span class="sxs-lookup"><span data-stu-id="7eeba-109">The statements in the list run as if you had typed them at the command prompt.</span></span>

<span data-ttu-id="7eeba-110">Funktionen können so einfach wie die folgenden sein:</span><span class="sxs-lookup"><span data-stu-id="7eeba-110">Functions can be as simple as:</span></span>

```powershell
function Get-PowerShellProcess { Get-Process PowerShell }
```

<span data-ttu-id="7eeba-111">Eine Funktion kann auch so komplex sein wie ein Cmdlet oder ein Anwendungsprogramm.</span><span class="sxs-lookup"><span data-stu-id="7eeba-111">A function can also be as complex as a cmdlet or an application program.</span></span>

<span data-ttu-id="7eeba-112">Ebenso wie Cmdlets können Funktionen über Parameter verfügen.</span><span class="sxs-lookup"><span data-stu-id="7eeba-112">Like cmdlets, functions can have parameters.</span></span> <span data-ttu-id="7eeba-113">Die Parameter können benannte, Positions-, Switch-oder dynamische Parameter sein.</span><span class="sxs-lookup"><span data-stu-id="7eeba-113">The parameters can be named, positional, switch, or dynamic parameters.</span></span> <span data-ttu-id="7eeba-114">Funktionsparameter können in der Befehlszeile oder in der Pipeline gelesen werden.</span><span class="sxs-lookup"><span data-stu-id="7eeba-114">Function parameters can be read from the command line or from the pipeline.</span></span>

<span data-ttu-id="7eeba-115">Funktionen können Werte zurückgeben, die angezeigt, Variablen zugewiesen oder an andere Funktionen oder Cmdlets übergeben werden können.</span><span class="sxs-lookup"><span data-stu-id="7eeba-115">Functions can return values that can be displayed, assigned to variables, or passed to other functions or cmdlets.</span></span> <span data-ttu-id="7eeba-116">Sie können auch einen Rückgabewert mit dem- `return` Schlüsselwort angeben.</span><span class="sxs-lookup"><span data-stu-id="7eeba-116">You can also specify a return value using the `return` keyword.</span></span> <span data-ttu-id="7eeba-117">Das- `return` Schlüsselwort wirkt sich nicht auf andere Ausgaben aus, die von der Funktion zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="7eeba-117">The `return` keyword does not affect or suppress other output returned from your function.</span></span> <span data-ttu-id="7eeba-118">Das- `return` Schlüsselwort beendet jedoch die-Funktion in dieser Zeile.</span><span class="sxs-lookup"><span data-stu-id="7eeba-118">However, the `return` keyword exits the function at that line.</span></span> <span data-ttu-id="7eeba-119">Weitere Informationen finden Sie unter [about_Return](about_Return.md).</span><span class="sxs-lookup"><span data-stu-id="7eeba-119">For more information, see [about_Return](about_Return.md).</span></span>

<span data-ttu-id="7eeba-120">Die Anweisungs Liste der Funktion kann unterschiedliche Typen von Anweisungs Listen mit den Schlüsselwörtern `Begin` , `Process` und enthalten `End` .</span><span class="sxs-lookup"><span data-stu-id="7eeba-120">The function's statement list can contain different types of statement lists with the keywords `Begin`, `Process`, and `End`.</span></span> <span data-ttu-id="7eeba-121">In dieser Anweisung werden Eingaben aus der Pipeline anders behandelt.</span><span class="sxs-lookup"><span data-stu-id="7eeba-121">These statement lists handle input from the pipeline differently.</span></span>

<span data-ttu-id="7eeba-122">Ein Filter ist eine besondere Art von Funktion, die das `Filter` Schlüsselwort verwendet.</span><span class="sxs-lookup"><span data-stu-id="7eeba-122">A filter is a special kind of function that uses the `Filter` keyword.</span></span>

<span data-ttu-id="7eeba-123">Funktionen können auch wie Cmdlets fungieren.</span><span class="sxs-lookup"><span data-stu-id="7eeba-123">Functions can also act like cmdlets.</span></span> <span data-ttu-id="7eeba-124">Sie können eine Funktion erstellen, die genau wie ein Cmdlet funktioniert, ohne die Programmierung zu verwenden `C#` .</span><span class="sxs-lookup"><span data-stu-id="7eeba-124">You can create a function that works just like a cmdlet without using `C#` programming.</span></span> <span data-ttu-id="7eeba-125">Weitere Informationen finden Sie unter [about_Functions_Advanced](about_Functions_Advanced.md).</span><span class="sxs-lookup"><span data-stu-id="7eeba-125">For more information, see [about_Functions_Advanced](about_Functions_Advanced.md).</span></span>

## <a name="syntax"></a><span data-ttu-id="7eeba-126">Syntax</span><span class="sxs-lookup"><span data-stu-id="7eeba-126">Syntax</span></span>

<span data-ttu-id="7eeba-127">Im folgenden finden Sie die Syntax für eine Funktion:</span><span class="sxs-lookup"><span data-stu-id="7eeba-127">The following is the syntax for a function:</span></span>

```
function [<scope:>]<name> [([type]$parameter1[,[type]$parameter2])]
{
  param([type]$parameter1 [,[type]$parameter2])
  dynamicparam {<statement list>}
  begin {<statement list>}
  process {<statement list>}
  end {<statement list>}
}
```

<span data-ttu-id="7eeba-128">Eine Funktion umfasst die folgenden Elemente:</span><span class="sxs-lookup"><span data-stu-id="7eeba-128">A function includes the following items:</span></span>

- <span data-ttu-id="7eeba-129">Ein- `Function` Schlüsselwort</span><span class="sxs-lookup"><span data-stu-id="7eeba-129">A `Function` keyword</span></span>
- <span data-ttu-id="7eeba-130">Ein Bereich (optional)</span><span class="sxs-lookup"><span data-stu-id="7eeba-130">A scope (optional)</span></span>
- <span data-ttu-id="7eeba-131">Ein Name, den Sie auswählen</span><span class="sxs-lookup"><span data-stu-id="7eeba-131">A name that you select</span></span>
- <span data-ttu-id="7eeba-132">Beliebig viele benannte Parameter (optional)</span><span class="sxs-lookup"><span data-stu-id="7eeba-132">Any number of named parameters (optional)</span></span>
- <span data-ttu-id="7eeba-133">Mindestens ein in geschweiften Klammern eingeschlossener PowerShell-Befehl `{}`</span><span class="sxs-lookup"><span data-stu-id="7eeba-133">One or more PowerShell commands enclosed in braces `{}`</span></span>

<span data-ttu-id="7eeba-134">Weitere Informationen zum `Dynamicparam` -Schlüsselwort und zu dynamischen Parametern in-Funktionen finden Sie unter [about_Functions_Advanced_Parameters](about_Functions_Advanced_Parameters.md).</span><span class="sxs-lookup"><span data-stu-id="7eeba-134">For more information about the `Dynamicparam` keyword and dynamic parameters in functions, see [about_Functions_Advanced_Parameters](about_Functions_Advanced_Parameters.md).</span></span>

## <a name="simple-functions"></a><span data-ttu-id="7eeba-135">Einfache Funktionen</span><span class="sxs-lookup"><span data-stu-id="7eeba-135">Simple Functions</span></span>

<span data-ttu-id="7eeba-136">Funktionen müssen nicht kompliziert sein, um nützlich zu sein.</span><span class="sxs-lookup"><span data-stu-id="7eeba-136">Functions do not have to be complicated to be useful.</span></span> <span data-ttu-id="7eeba-137">Die einfachsten Funktionen haben das folgende Format:</span><span class="sxs-lookup"><span data-stu-id="7eeba-137">The simplest functions have the following format:</span></span>

```
function <function-name> {statements}
```

<span data-ttu-id="7eeba-138">Die folgende Funktion startet beispielsweise PowerShell mit der Option als Administrator ausführen.</span><span class="sxs-lookup"><span data-stu-id="7eeba-138">For example, the following function starts PowerShell with the Run as Administrator option.</span></span>

```powershell
function Start-PSAdmin {Start-Process PowerShell -Verb RunAs}
```

<span data-ttu-id="7eeba-139">Geben Sie Folgendes ein, um die-Funktion zu verwenden: `Start-PSAdmin`</span><span class="sxs-lookup"><span data-stu-id="7eeba-139">To use the function, type: `Start-PSAdmin`</span></span>

<span data-ttu-id="7eeba-140">Um der Funktion Anweisungen hinzuzufügen, geben Sie jede Anweisung in einer separaten Zeile ein, oder verwenden Sie ein Semikolon, `;` um die Anweisungen zu trennen.</span><span class="sxs-lookup"><span data-stu-id="7eeba-140">To add statements to the function, type each statement on a separate line, or use a semi-colon `;` to separate the statements.</span></span>

<span data-ttu-id="7eeba-141">Die folgende Funktion findet z. b `.jpg` . alle Dateien in den Verzeichnissen des aktuellen Benutzers, die nach dem Startdatum geändert wurden.</span><span class="sxs-lookup"><span data-stu-id="7eeba-141">For example, the following function finds all `.jpg` files in the current user's directories that were changed after the start date.</span></span>

```powershell
function Get-NewPix
{
  $start = Get-Date -Month 1 -Day 1 -Year 2010
  $allpix = Get-ChildItem -Path $env:UserProfile\*.jpg -Recurse
  $allpix | Where-Object {$_.LastWriteTime -gt $Start}
}
```

<span data-ttu-id="7eeba-142">Sie können eine Toolbox mit nützlichen kleinen Funktionen erstellen.</span><span class="sxs-lookup"><span data-stu-id="7eeba-142">You can create a toolbox of useful small functions.</span></span> <span data-ttu-id="7eeba-143">Fügen Sie diese Funktionen zum PowerShell-Profil hinzu, wie in [about_Profiles](about_Profiles.md) und weiter unten in diesem Thema beschrieben.</span><span class="sxs-lookup"><span data-stu-id="7eeba-143">Add these functions to your PowerShell profile, as described in [about_Profiles](about_Profiles.md) and later in this topic.</span></span>

## <a name="function-names"></a><span data-ttu-id="7eeba-144">Funktionsnamen</span><span class="sxs-lookup"><span data-stu-id="7eeba-144">Function Names</span></span>

<span data-ttu-id="7eeba-145">Sie können einer Funktion einen beliebigen Namen zuweisen, aber Funktionen, die Sie für andere freigeben, sollten den Benennungs Regeln folgen, die für alle PowerShell-Befehle eingerichtet wurden.</span><span class="sxs-lookup"><span data-stu-id="7eeba-145">You can assign any name to a function, but functions that you share with others should follow the naming rules that have been established for all PowerShell commands.</span></span>

<span data-ttu-id="7eeba-146">Funktionsnamen sollten aus einem Verb-Substantiv-paar bestehen, in dem das Verb die von der Funktion ausgeführten Aktion identifiziert, und das Substantiv identifiziert das Element, auf dem das Cmdlet die Aktion ausführt.</span><span class="sxs-lookup"><span data-stu-id="7eeba-146">Functions names should consist of a verb-noun pair in which the verb identifies the action that the function performs and the noun identifies the item on which the cmdlet performs its action.</span></span>

<span data-ttu-id="7eeba-147">Functions sollten die Standard Verben verwenden, die für alle PowerShell-Befehle genehmigt wurden.</span><span class="sxs-lookup"><span data-stu-id="7eeba-147">Functions should use the standard verbs that have been approved for all PowerShell commands.</span></span> <span data-ttu-id="7eeba-148">Diese Verben helfen uns, die Befehlsnamen für die Benutzer einfach, konsistent und leicht verständlich zu halten.</span><span class="sxs-lookup"><span data-stu-id="7eeba-148">These verbs help us to keep our command names simple, consistent, and easy for users to understand.</span></span>

<span data-ttu-id="7eeba-149">Weitere Informationen zu den standardmäßigen PowerShell-Verben finden Sie unter [genehmigte Verben](/powershell/scripting/developer/cmdlet/approved-verbs-for-windows-powershell-commands) in der Microsoft-Dokumentation.</span><span class="sxs-lookup"><span data-stu-id="7eeba-149">For more information about the standard PowerShell verbs, see [Approved Verbs](/powershell/scripting/developer/cmdlet/approved-verbs-for-windows-powershell-commands) in the Microsoft Docs.</span></span>

## <a name="functions-with-parameters"></a><span data-ttu-id="7eeba-150">Funktionen mit Parametern</span><span class="sxs-lookup"><span data-stu-id="7eeba-150">Functions with Parameters</span></span>

<span data-ttu-id="7eeba-151">Sie können Parameter mit Funktionen verwenden, einschließlich benannter Parameter, Positions Parameter, Schalter Parameter und dynamischer Parameter.</span><span class="sxs-lookup"><span data-stu-id="7eeba-151">You can use parameters with functions, including named parameters, positional parameters, switch parameters, and dynamic parameters.</span></span> <span data-ttu-id="7eeba-152">Weitere Informationen zu dynamischen Parametern in Funktionen finden Sie unter [about_Functions_Advanced_Parameters](about_Functions_Advanced_Parameters.md).</span><span class="sxs-lookup"><span data-stu-id="7eeba-152">For more information about dynamic parameters in functions, see [about_Functions_Advanced_Parameters](about_Functions_Advanced_Parameters.md).</span></span>

### <a name="named-parameters"></a><span data-ttu-id="7eeba-153">benannten Parametern</span><span class="sxs-lookup"><span data-stu-id="7eeba-153">Named Parameters</span></span>

<span data-ttu-id="7eeba-154">Sie können beliebig viele benannte Parameter definieren.</span><span class="sxs-lookup"><span data-stu-id="7eeba-154">You can define any number of named parameters.</span></span> <span data-ttu-id="7eeba-155">Sie können einen Standardwert für benannte Parameter einschließen, wie weiter unten in diesem Thema beschrieben.</span><span class="sxs-lookup"><span data-stu-id="7eeba-155">You can include a default value for named parameters, as described later in this topic.</span></span>

<span data-ttu-id="7eeba-156">Sie können Parameter innerhalb der geschweiften Klammern mithilfe des `Param` Schlüssel Worts definieren, wie in der folgenden Beispiel Syntax gezeigt:</span><span class="sxs-lookup"><span data-stu-id="7eeba-156">You can define parameters inside the braces using the `Param` keyword, as shown in the following sample syntax:</span></span>

```
function <name> {
  param ([type]$parameter1[,[type]$parameter2])
  <statement list>
}
```

<span data-ttu-id="7eeba-157">Sie können Parameter auch außerhalb der geschweiften Klammern ohne das- `Param` Schlüsselwort definieren, wie in der folgenden Beispiel Syntax gezeigt:</span><span class="sxs-lookup"><span data-stu-id="7eeba-157">You can also define parameters outside the braces without the `Param` keyword, as shown in the following sample syntax:</span></span>

```powershell
function <name> [([type]$parameter1[,[type]$parameter2])] {
  <statement list>
}
```

<span data-ttu-id="7eeba-158">Im folgenden finden Sie ein Beispiel für diese alternative Syntax.</span><span class="sxs-lookup"><span data-stu-id="7eeba-158">Below is an example of this alternative syntax.</span></span>

```powershell
Function Add-Numbers($one, $two) {
    $one + $two
}
```

<span data-ttu-id="7eeba-159">Während die erste Methode bevorzugt wird, gibt es keinen Unterschied zwischen diesen beiden Methoden.</span><span class="sxs-lookup"><span data-stu-id="7eeba-159">While the first method is preferred, there is no difference between these two methods.</span></span>

<span data-ttu-id="7eeba-160">Wenn Sie die Funktion ausführen, wird der Wert, den Sie für einen Parameter angeben, einer Variablen zugewiesen, die den Parameternamen enthält.</span><span class="sxs-lookup"><span data-stu-id="7eeba-160">When you run the function, the value you supply for a parameter is assigned to a variable that contains the parameter name.</span></span> <span data-ttu-id="7eeba-161">Der Wert dieser Variablen kann in der-Funktion verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="7eeba-161">The value of that variable can be used in the function.</span></span>

<span data-ttu-id="7eeba-162">Das folgende Beispiel ist eine Funktion mit dem Namen `Get-SmallFiles` .</span><span class="sxs-lookup"><span data-stu-id="7eeba-162">The following example is a function called `Get-SmallFiles`.</span></span> <span data-ttu-id="7eeba-163">Diese Funktion verfügt über einen- `$Size` Parameter.</span><span class="sxs-lookup"><span data-stu-id="7eeba-163">This function has a `$Size` parameter.</span></span> <span data-ttu-id="7eeba-164">Die-Funktion zeigt alle Dateien an, die kleiner als der Wert des `$Size` -Parameters sind, und schließt Verzeichnisse aus:</span><span class="sxs-lookup"><span data-stu-id="7eeba-164">The function displays all the files that are smaller than the value of the `$Size` parameter, and it excludes directories:</span></span>

```powershell
function Get-SmallFiles {
  Param($Size)
  Get-ChildItem $HOME | Where-Object {
    $_.Length -lt $Size -and !$_.PSIsContainer
  }
}
```

<span data-ttu-id="7eeba-165">In der-Funktion können Sie die- `$Size` Variable verwenden, bei der es sich um den für den-Parameter definierten Namen handelt.</span><span class="sxs-lookup"><span data-stu-id="7eeba-165">In the function, you can use the `$Size` variable, which is the name defined for the parameter.</span></span>

<span data-ttu-id="7eeba-166">Wenn Sie diese Funktion verwenden möchten, geben Sie den folgenden Befehl ein:</span><span class="sxs-lookup"><span data-stu-id="7eeba-166">To use this function, type the following command:</span></span>

```powershell
Get-SmallFiles -Size 50
```

<span data-ttu-id="7eeba-167">Sie können auch einen Wert für einen benannten Parameter ohne den Parameternamen eingeben.</span><span class="sxs-lookup"><span data-stu-id="7eeba-167">You can also enter a value for a named parameter without the parameter name.</span></span>
<span data-ttu-id="7eeba-168">Der folgende Befehl gibt z. b. das gleiche Ergebnis wie ein Befehl, der den **size** -Parameter benennt:</span><span class="sxs-lookup"><span data-stu-id="7eeba-168">For example, the following command gives the same result as a command that names the **Size** parameter:</span></span>

```powershell
Get-SmallFiles 50
```

<span data-ttu-id="7eeba-169">Um einen Standardwert für einen Parameter zu definieren, geben Sie ein Gleichheitszeichen und den Wert nach dem Parameternamen ein, wie in der folgenden Variation des `Get-SmallFiles` Beispiels gezeigt:</span><span class="sxs-lookup"><span data-stu-id="7eeba-169">To define a default value for a parameter, type an equal sign and the value after the parameter name, as shown in the following variation of the `Get-SmallFiles` example:</span></span>

```powershell
function Get-SmallFiles ($Size = 100) {
  Get-ChildItem $HOME | Where-Object {
    $_.Length -lt $Size -and !$_.PSIsContainer
  }
}
```

<span data-ttu-id="7eeba-170">Wenn Sie `Get-SmallFiles` ohne einen Wert eingeben, wird von der-Funktion 100 zugewiesen `$size` .</span><span class="sxs-lookup"><span data-stu-id="7eeba-170">If you type `Get-SmallFiles` without a value, the function assigns 100 to `$size`.</span></span> <span data-ttu-id="7eeba-171">Wenn Sie einen Wert angeben, verwendet die Funktion diesen Wert.</span><span class="sxs-lookup"><span data-stu-id="7eeba-171">If you provide a value, the function uses that value.</span></span>

<span data-ttu-id="7eeba-172">Optional können Sie eine kurze Hilfe Zeichenfolge bereitstellen, die den Standardwert des Parameters beschreibt, indem Sie das **psdefaultvalue** -Attribut zur Beschreibung des Parameters hinzufügen und die **Help** -Eigenschaft von **psdefaultvalue** angeben.</span><span class="sxs-lookup"><span data-stu-id="7eeba-172">Optionally, you can provide a brief help string that describes the default value of your parameter, by adding the **PSDefaultValue** attribute to the description of your parameter, and specifying the **Help** property of **PSDefaultValue**.</span></span> <span data-ttu-id="7eeba-173">Fügen Sie zum Bereitstellen einer Hilfe Zeichenfolge, die den Standardwert (100) des **size** -Parameters in der `Get-SmallFiles` Funktion beschreibt, das **psdefaultvalue** -Attribut hinzu, wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="7eeba-173">To provide a help string that describes the default value (100) of the **Size** parameter in the `Get-SmallFiles` function, add the **PSDefaultValue** attribute as shown in the following example.</span></span>

```powershell
function Get-SmallFiles {
  param (
      [PSDefaultValue(Help = '100')]
      $Size = 100
  )
}
```

<span data-ttu-id="7eeba-174">Weitere Informationen zur **psdefaultvalue** -Attribut Klasse finden Sie unter [psdefaultvalue-Attribut](/dotnet/api/system.management.automation.psdefaultvalueattribute)Elemente.</span><span class="sxs-lookup"><span data-stu-id="7eeba-174">For more information about the **PSDefaultValue** attribute class, see [PSDefaultValue Attribute Members](/dotnet/api/system.management.automation.psdefaultvalueattribute).</span></span>

### <a name="positional-parameters"></a><span data-ttu-id="7eeba-175">Positions Parameter</span><span class="sxs-lookup"><span data-stu-id="7eeba-175">Positional Parameters</span></span>

<span data-ttu-id="7eeba-176">Ein Positions Parameter ist ein Parameter ohne Parameternamen.</span><span class="sxs-lookup"><span data-stu-id="7eeba-176">A positional parameter is a parameter without a parameter name.</span></span> <span data-ttu-id="7eeba-177">PowerShell verwendet die Reihenfolge der Parameterwerte, um jeden Parameterwert einem Parameter in der Funktion zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="7eeba-177">PowerShell uses the parameter value order to associate each parameter value with a parameter in the function.</span></span>

<span data-ttu-id="7eeba-178">Wenn Sie Positions Parameter verwenden, geben Sie einen oder mehrere Werte nach dem Funktionsnamen ein.</span><span class="sxs-lookup"><span data-stu-id="7eeba-178">When you use positional parameters, type one or more values after the function name.</span></span> <span data-ttu-id="7eeba-179">Positions Parameterwerte werden der `$args` Array Variablen zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="7eeba-179">Positional parameter values are assigned to the `$args` array variable.</span></span>
<span data-ttu-id="7eeba-180">Der Wert, der auf den Funktionsnamen folgt, wird der ersten Position im `$args` Array zugewiesen `$args[0]` .</span><span class="sxs-lookup"><span data-stu-id="7eeba-180">The value that follows the function name is assigned to the first position in the `$args` array, `$args[0]`.</span></span>

<span data-ttu-id="7eeba-181">Die folgende `Get-Extension` Funktion fügt die `.txt` Dateinamenerweiterung einem Dateinamen hinzu, den Sie angeben:</span><span class="sxs-lookup"><span data-stu-id="7eeba-181">The following `Get-Extension` function adds the `.txt` file name extension to a file name that you supply:</span></span>

```powershell
function Get-Extension {
  $name = $args[0] + ".txt"
  $name
}
```

```powershell
Get-Extension myTextFile
```

```Output
myTextFile.txt
```

### <a name="switch-parameters"></a><span data-ttu-id="7eeba-182">Parameter wechseln</span><span class="sxs-lookup"><span data-stu-id="7eeba-182">Switch Parameters</span></span>

<span data-ttu-id="7eeba-183">Bei einem Switch handelt es sich um einen Parameter, der keinen Wert erfordert.</span><span class="sxs-lookup"><span data-stu-id="7eeba-183">A switch is a parameter that does not require a value.</span></span> <span data-ttu-id="7eeba-184">Stattdessen geben Sie den Funktionsnamen gefolgt vom Namen des Switch-Parameters ein.</span><span class="sxs-lookup"><span data-stu-id="7eeba-184">Instead, you type the function name followed by the name of the switch parameter.</span></span>

<span data-ttu-id="7eeba-185">Um einen Switch-Parameter zu definieren, geben Sie den Typ `[switch]` vor dem Parameternamen an, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="7eeba-185">To define a switch parameter, specify the type `[switch]` before the parameter name, as shown in the following example:</span></span>

```powershell
function Switch-Item {
  param ([switch]$on)
  if ($on) { "Switch on" }
  else { "Switch off" }
}
```

<span data-ttu-id="7eeba-186">Wenn Sie den `On` Switch-Parameter nach dem Funktionsnamen eingeben, zeigt die Funktion "Switch on" an.</span><span class="sxs-lookup"><span data-stu-id="7eeba-186">When you type the `On` switch parameter after the function name, the function displays "Switch on".</span></span> <span data-ttu-id="7eeba-187">Ohne den Switch-Parameter wird "Switch Off" angezeigt.</span><span class="sxs-lookup"><span data-stu-id="7eeba-187">Without the switch parameter, it displays "Switch off".</span></span>

```powershell
Switch-Item -on
```

```Output
Switch on
```

```powershell
Switch-Item
```

```Output
Switch off
```

<span data-ttu-id="7eeba-188">Sie können einen **booleschen** Wert auch einem Switch zuweisen, wenn Sie die Funktion ausführen, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="7eeba-188">You can also assign a **Boolean** value to a switch when you run the function, as shown in the following example:</span></span>

```powershell
Switch-Item -on:$true
```

```Output
Switch on
```

```powershell
Switch-Item -on:$false
```

```Output
Switch off
```

## <a name="using-splatting-to-represent-command-parameters"></a><span data-ttu-id="7eeba-189">Verwenden von splatting zur Darstellung von Befehlsparametern</span><span class="sxs-lookup"><span data-stu-id="7eeba-189">Using Splatting to Represent Command Parameters</span></span>

<span data-ttu-id="7eeba-190">Mithilfe von Verteilung können Sie die Parameter eines Befehls darstellen.</span><span class="sxs-lookup"><span data-stu-id="7eeba-190">You can use splatting to represent the parameters of a command.</span></span> <span data-ttu-id="7eeba-191">Diese Funktion wird in Windows PowerShell 3,0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="7eeba-191">This feature is introduced in Windows PowerShell 3.0.</span></span>

<span data-ttu-id="7eeba-192">Verwenden Sie diese Technik in Funktionen, die Befehle in der Sitzung aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="7eeba-192">Use this technique in functions that call commands in the session.</span></span> <span data-ttu-id="7eeba-193">Sie müssen die Befehlsparameter nicht deklarieren oder aufzählen oder die Funktion ändern, wenn sich die Befehlsparameter ändern.</span><span class="sxs-lookup"><span data-stu-id="7eeba-193">You do not need to declare or enumerate the command parameters, or change the function when command parameters change.</span></span>

<span data-ttu-id="7eeba-194">Die folgende Beispiel Funktion Ruft das `Get-Command` Cmdlet auf.</span><span class="sxs-lookup"><span data-stu-id="7eeba-194">The following sample function calls the `Get-Command` cmdlet.</span></span> <span data-ttu-id="7eeba-195">Der Befehl verwendet `@Args` , um die Parameter von darzustellen `Get-Command` .</span><span class="sxs-lookup"><span data-stu-id="7eeba-195">The command uses `@Args` to represent the parameters of `Get-Command`.</span></span>

```powershell
function Get-MyCommand { Get-Command @Args }
```

<span data-ttu-id="7eeba-196">Sie können alle Parameter von verwenden, `Get-Command` Wenn Sie die-Funktion aufzurufen `Get-MyCommand` .</span><span class="sxs-lookup"><span data-stu-id="7eeba-196">You can use all of the parameters of `Get-Command` when you call the `Get-MyCommand` function.</span></span> <span data-ttu-id="7eeba-197">Die Parameter und Parameterwerte werden mithilfe von an den Befehl übergeben `@Args` .</span><span class="sxs-lookup"><span data-stu-id="7eeba-197">The parameters and parameter values are passed to the command using `@Args`.</span></span>

```powershell
Get-MyCommand -Name Get-ChildItem
```

```Output
CommandType     Name                ModuleName
-----------     ----                ----------
Cmdlet          Get-ChildItem       Microsoft.PowerShell.Management
```

<span data-ttu-id="7eeba-198">Die `@Args` Funktion verwendet den `$Args` automatischen Parameter, der nicht deklarierte Cmdlet-Parameter und Werte von verbleibenden Argumenten darstellt.</span><span class="sxs-lookup"><span data-stu-id="7eeba-198">The `@Args` feature uses the `$Args` automatic parameter, which represents undeclared cmdlet parameters and values from remaining arguments.</span></span>

<span data-ttu-id="7eeba-199">Weitere Informationen zum splatting finden Sie unter [about_Splatting](about_Splatting.md).</span><span class="sxs-lookup"><span data-stu-id="7eeba-199">For more information about splatting, see [about_Splatting](about_Splatting.md).</span></span>

## <a name="piping-objects-to-functions"></a><span data-ttu-id="7eeba-200">Übergeben von Objekten an Funktionen</span><span class="sxs-lookup"><span data-stu-id="7eeba-200">Piping Objects to Functions</span></span>

<span data-ttu-id="7eeba-201">Jede Funktion kann Eingaben aus der Pipeline annehmen.</span><span class="sxs-lookup"><span data-stu-id="7eeba-201">Any function can take input from the pipeline.</span></span> <span data-ttu-id="7eeba-202">Sie können steuern, wie eine Funktion Eingaben aus der Pipeline mit `Begin` den `Process` Schlüsselwörtern, und verarbeitet `End` .</span><span class="sxs-lookup"><span data-stu-id="7eeba-202">You can control how a function processes input from the pipeline using `Begin`, `Process`, and `End` keywords.</span></span> <span data-ttu-id="7eeba-203">Die folgende Beispiel Syntax zeigt die drei Schlüsselwörter:</span><span class="sxs-lookup"><span data-stu-id="7eeba-203">The following sample syntax shows the three keywords:</span></span>

```
function <name> {
  begin {<statement list>}
  process {<statement list>}
  end {<statement list>}
}
```

<span data-ttu-id="7eeba-204">Die `Begin` Anweisungs Liste wird nur einmal am Anfang der Funktion ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="7eeba-204">The `Begin` statement list runs one time only, at the beginning of the function.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7eeba-205">Wenn Ihre Funktion einen- `Begin` `Process` oder- `End` Block definiert, muss sich der gesamte Code innerhalb dieser Blöcke befinden.</span><span class="sxs-lookup"><span data-stu-id="7eeba-205">If your function defines a `Begin`, `Process` or `End` block, all of your code must reside inside those blocks.</span></span> <span data-ttu-id="7eeba-206">Wenn *ein* Block definiert ist, wird kein Code außerhalb der Blöcke erkannt.</span><span class="sxs-lookup"><span data-stu-id="7eeba-206">No code will be recognized outside the blocks if *any* of the blocks are defined.</span></span>

<span data-ttu-id="7eeba-207">Die `Process` Anweisungs Liste wird einmal für jedes Objekt in der Pipeline ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="7eeba-207">The `Process` statement list runs one time for each object in the pipeline.</span></span>
<span data-ttu-id="7eeba-208">Während der- `Process` Block ausgeführt wird, wird jedes Pipeline Objekt der `$_` automatischen Variablen zugewiesen, einem Pipeline Objekt gleichzeitig.</span><span class="sxs-lookup"><span data-stu-id="7eeba-208">While the `Process` block is running, each pipeline object is assigned to the `$_` automatic variable, one pipeline object at a time.</span></span>

<span data-ttu-id="7eeba-209">Nachdem die Funktion alle Objekte in der Pipeline empfangen hat, wird die `End` Anweisungs Liste einmal ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="7eeba-209">After the function receives all the objects in the pipeline, the `End` statement list runs one time.</span></span> <span data-ttu-id="7eeba-210">Wenn kein- `Begin` ,-oder-Schlüsselwort verwendet wird `Process` `End` , werden alle-Anweisungen wie eine `End` Anweisungs Liste behandelt.</span><span class="sxs-lookup"><span data-stu-id="7eeba-210">If no `Begin`, `Process`, or `End` keywords are used, all the statements are treated like an `End` statement list.</span></span>

<span data-ttu-id="7eeba-211">Die folgende Funktion verwendet das- `Process` Schlüsselwort.</span><span class="sxs-lookup"><span data-stu-id="7eeba-211">The following function uses the `Process` keyword.</span></span> <span data-ttu-id="7eeba-212">Die-Funktion zeigt Beispiele aus der Pipeline an:</span><span class="sxs-lookup"><span data-stu-id="7eeba-212">The function displays examples from the pipeline:</span></span>

```powershell
function Get-Pipeline
{
  process {"The value is: $_"}
}
```

<span data-ttu-id="7eeba-213">Um diese Funktion zu veranschaulichen, geben Sie eine durch Kommas getrennte Liste von Zahlen ein, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="7eeba-213">To demonstrate this function, enter an list of numbers separated by commas, as shown in the following example:</span></span>

```powershell
1,2,4 | Get-Pipeline
```

```Output
The value is: 1
The value is: 2
The value is: 4
```

<span data-ttu-id="7eeba-214">Wenn Sie eine Funktion in einer Pipeline verwenden, werden die an die Funktion weitergeleiteten Objekte der `$input` automatischen Variablen zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="7eeba-214">When you use a function in a pipeline, the objects piped to the function are assigned to the `$input` automatic variable.</span></span> <span data-ttu-id="7eeba-215">Die-Funktion führt-Anweisungen mit dem- `Begin` Schlüsselwort aus, bevor Objekte aus der Pipeline stammen.</span><span class="sxs-lookup"><span data-stu-id="7eeba-215">The function runs statements with the `Begin` keyword before any objects come from the pipeline.</span></span> <span data-ttu-id="7eeba-216">Die Funktion führt-Anweisungen mit dem- `End` Schlüsselwort aus, nachdem alle-Objekte von der Pipeline empfangen wurden.</span><span class="sxs-lookup"><span data-stu-id="7eeba-216">The function runs statements with the `End` keyword after all the objects have been received from the pipeline.</span></span>

<span data-ttu-id="7eeba-217">Das folgende Beispiel zeigt die `$input` Automatische Variable mit `Begin` den `End` Schlüsselwörtern und.</span><span class="sxs-lookup"><span data-stu-id="7eeba-217">The following example shows the `$input` automatic variable with `Begin` and `End` keywords.</span></span>

```powershell
function Get-PipelineBeginEnd
{
  begin {"Begin: The input is $input"}
  end {"End:   The input is $input" }
}
```

<span data-ttu-id="7eeba-218">Wenn diese Funktion mithilfe der Pipeline ausgeführt wird, werden die folgenden Ergebnisse angezeigt:</span><span class="sxs-lookup"><span data-stu-id="7eeba-218">If this function is run by using the pipeline, it displays the following results:</span></span>

```powershell
1,2,4 | Get-PipelineBeginEnd
```

```Output
Begin: The input is
End:   The input is 1 2 4
```

<span data-ttu-id="7eeba-219">Wenn die- `Begin` Anweisung ausgeführt wird, verfügt die-Funktion nicht über die Eingabe aus der Pipeline.</span><span class="sxs-lookup"><span data-stu-id="7eeba-219">When the `Begin` statement runs, the function does not have the input from the pipeline.</span></span> <span data-ttu-id="7eeba-220">Die-Anweisung wird ausgeführt, `End` nachdem die-Funktion die-Werte aufweist.</span><span class="sxs-lookup"><span data-stu-id="7eeba-220">The `End` statement runs after the function has the values.</span></span>

<span data-ttu-id="7eeba-221">Wenn die Funktion über ein `Process` Schlüsselwort verfügt, wird jedes Objekt in `$input` aus entfernt `$input` und zugewiesen `$_` .</span><span class="sxs-lookup"><span data-stu-id="7eeba-221">If the function has a `Process` keyword, each object in `$input` is removed from `$input` and assigned to `$_`.</span></span> <span data-ttu-id="7eeba-222">Das folgende Beispiel enthält eine `Process` Anweisungs Liste:</span><span class="sxs-lookup"><span data-stu-id="7eeba-222">The following example has a `Process` statement list:</span></span>

```powershell
function Get-PipelineInput
{
  process {"Processing:  $_ " }
  end {"End:   The input is: $input" }
}
```

<span data-ttu-id="7eeba-223">In diesem Beispiel wird jedes Objekt, das an die Funktion weitergeleitet wird, an die `Process` Anweisungs Liste gesendet.</span><span class="sxs-lookup"><span data-stu-id="7eeba-223">In this example, each object that is piped to the function is sent to the `Process` statement list.</span></span> <span data-ttu-id="7eeba-224">Die- `Process` Anweisungen werden für jedes Objekt ausgeführt, ein Objekt gleichzeitig.</span><span class="sxs-lookup"><span data-stu-id="7eeba-224">The `Process` statements run on each object, one object at a time.</span></span> <span data-ttu-id="7eeba-225">Die `$input` Automatische Variable ist leer, wenn die Funktion das `End` Schlüsselwort erreicht.</span><span class="sxs-lookup"><span data-stu-id="7eeba-225">The `$input` automatic variable is empty when the function reaches the `End` keyword.</span></span>

```powershell
1,2,4 | Get-PipelineInput
```

```Output
Processing:  1
Processing:  2
Processing:  4
End:   The input is:
```

<span data-ttu-id="7eeba-226">Weitere Informationen finden Sie unter [Verwenden von Enumeratoren](about_Automatic_Variables.md#using-enumerators) .</span><span class="sxs-lookup"><span data-stu-id="7eeba-226">For more information, see [Using Enumerators](about_Automatic_Variables.md#using-enumerators)</span></span>

## <a name="filters"></a><span data-ttu-id="7eeba-227">Filter</span><span class="sxs-lookup"><span data-stu-id="7eeba-227">Filters</span></span>

<span data-ttu-id="7eeba-228">Ein Filter ist ein Funktionstyp, der für jedes Objekt in der Pipeline ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="7eeba-228">A filter is a type of function that runs on each object in the pipeline.</span></span> <span data-ttu-id="7eeba-229">Ein Filter ähnelt einer Funktion mit allen zugehörigen Anweisungen in einem- `Process` Block.</span><span class="sxs-lookup"><span data-stu-id="7eeba-229">A filter resembles a function with all its statements in a `Process` block.</span></span>

<span data-ttu-id="7eeba-230">Die Syntax eines Filters lautet wie folgt:</span><span class="sxs-lookup"><span data-stu-id="7eeba-230">The syntax of a filter is as follows:</span></span>

```
filter [<scope:>]<name> {<statement list>}
```

<span data-ttu-id="7eeba-231">Der folgende Filter nimmt Protokolleinträge aus der Pipeline und zeigt dann entweder den gesamten Eintrag oder nur den Nachrichten Teil des Eintrags an:</span><span class="sxs-lookup"><span data-stu-id="7eeba-231">The following filter takes log entries from the pipeline and then displays either the whole entry or only the message portion of the entry:</span></span>

```powershell
filter Get-ErrorLog ([switch]$message)
{
  if ($message) { Out-Host -InputObject $_.Message }
  else { $_ }
}
```

## <a name="function-scope"></a><span data-ttu-id="7eeba-232">Funktionsbereich</span><span class="sxs-lookup"><span data-stu-id="7eeba-232">Function Scope</span></span>

<span data-ttu-id="7eeba-233">Eine Funktion ist in dem Bereich vorhanden, in dem Sie erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="7eeba-233">A function exists in the scope in which it was created.</span></span>

<span data-ttu-id="7eeba-234">Wenn eine Funktion Teil eines Skripts ist, steht die Funktion den Anweisungen innerhalb dieses Skripts zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="7eeba-234">If a function is part of a script, the function is available to statements within that script.</span></span> <span data-ttu-id="7eeba-235">Standardmäßig ist eine Funktion in einem Skript an der Eingabeaufforderung nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="7eeba-235">By default, a function in a script is not available at the command prompt.</span></span>

<span data-ttu-id="7eeba-236">Sie können den Gültigkeitsbereich einer Funktion angeben.</span><span class="sxs-lookup"><span data-stu-id="7eeba-236">You can specify the scope of a function.</span></span> <span data-ttu-id="7eeba-237">Beispielsweise wird die-Funktion dem globalen Gültigkeitsbereich im folgenden Beispiel hinzugefügt:</span><span class="sxs-lookup"><span data-stu-id="7eeba-237">For example, the function is added to the global scope in the following example:</span></span>

```powershell
function global:Get-DependentSvs {
  Get-Service | Where-Object {$_.DependentServices}
}
```

<span data-ttu-id="7eeba-238">Wenn sich eine Funktion im globalen Gültigkeitsbereich befindet, können Sie die-Funktion in Skripts, in Funktionen und in der Befehlszeile verwenden.</span><span class="sxs-lookup"><span data-stu-id="7eeba-238">When a function is in the global scope, you can use the function in scripts, in functions, and at the command line.</span></span>

<span data-ttu-id="7eeba-239">Funktionen erstellen in der Regel einen Bereich.</span><span class="sxs-lookup"><span data-stu-id="7eeba-239">Functions normally create a scope.</span></span> <span data-ttu-id="7eeba-240">Die Elemente, die in einer Funktion erstellt werden, z. b. Variablen, sind nur im Funktionsbereich vorhanden.</span><span class="sxs-lookup"><span data-stu-id="7eeba-240">The items created in a function, such as variables, exist only in the function scope.</span></span>

<span data-ttu-id="7eeba-241">Weitere Informationen zum Gültigkeitsbereich von PowerShell finden Sie unter [about_Scopes](about_Scopes.md).</span><span class="sxs-lookup"><span data-stu-id="7eeba-241">For more information about scope in PowerShell, see [about_Scopes](about_Scopes.md).</span></span>

## <a name="finding-and-managing-functions-using-the-function-drive"></a><span data-ttu-id="7eeba-242">Suchen und Verwalten von Funktionen mit dem Function:-Laufwerk</span><span class="sxs-lookup"><span data-stu-id="7eeba-242">Finding and Managing Functions Using the Function: Drive</span></span>

<span data-ttu-id="7eeba-243">Alle Funktionen und Filter in PowerShell werden automatisch auf dem Laufwerk gespeichert `Function:` .</span><span class="sxs-lookup"><span data-stu-id="7eeba-243">All the functions and filters in PowerShell are automatically stored in the `Function:` drive.</span></span> <span data-ttu-id="7eeba-244">Dieses Laufwerk wird vom PowerShell- **Funktions** Anbieter verfügbar gemacht.</span><span class="sxs-lookup"><span data-stu-id="7eeba-244">This drive is exposed by the PowerShell **Function** provider.</span></span>

<span data-ttu-id="7eeba-245">Wenn Sie auf das `Function:` Laufwerk verweisen, geben Sie einen Doppelpunkt nach der **Funktion** ein, genauso wie beim Verweisen auf das- `C` oder- `D` Laufwerk eines Computers.</span><span class="sxs-lookup"><span data-stu-id="7eeba-245">When referring to the `Function:` drive, type a colon after **Function**, just as you would do when referencing the `C` or `D` drive of a computer.</span></span>

<span data-ttu-id="7eeba-246">Der folgende Befehl zeigt alle Funktionen in der aktuellen PowerShell-Sitzung an:</span><span class="sxs-lookup"><span data-stu-id="7eeba-246">The following command displays all the functions in the current session of PowerShell:</span></span>

```powershell
Get-ChildItem function:
```

<span data-ttu-id="7eeba-247">Die Befehle in der Funktion werden als Skriptblock in der Definition-Eigenschaft der Funktion gespeichert.</span><span class="sxs-lookup"><span data-stu-id="7eeba-247">The commands in the function are stored as a script block in the definition property of the function.</span></span> <span data-ttu-id="7eeba-248">Wenn Sie z. b. die Befehle in der Hilfe Funktion von PowerShell anzeigen möchten, geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="7eeba-248">For example, to display the commands in the Help function that comes with PowerShell, type:</span></span>

```powershell
(Get-ChildItem function:help).Definition
```

<span data-ttu-id="7eeba-249">Sie können auch die folgende Syntax verwenden.</span><span class="sxs-lookup"><span data-stu-id="7eeba-249">You can also use the following syntax.</span></span>

```powershell
$function:help
```

<span data-ttu-id="7eeba-250">Weitere Informationen zum `Function:` Laufwerk finden Sie im Hilfethema für den **Funktions** Anbieter.</span><span class="sxs-lookup"><span data-stu-id="7eeba-250">For more information about the `Function:` drive, see the help topic for the **Function** provider.</span></span> <span data-ttu-id="7eeba-251">Geben Sie `Get-Help Function`ein.</span><span class="sxs-lookup"><span data-stu-id="7eeba-251">Type `Get-Help Function`.</span></span>

## <a name="reusing-functions-in-new-sessions"></a><span data-ttu-id="7eeba-252">Wieder verwenden von Funktionen in neuen Sitzungen</span><span class="sxs-lookup"><span data-stu-id="7eeba-252">Reusing Functions in New Sessions</span></span>

<span data-ttu-id="7eeba-253">Wenn Sie an der PowerShell-Eingabeaufforderung eine Funktion eingeben, wird die Funktion Teil der aktuellen Sitzung.</span><span class="sxs-lookup"><span data-stu-id="7eeba-253">When you type a function at the PowerShell command prompt, the function becomes part of the current session.</span></span> <span data-ttu-id="7eeba-254">Sie ist bis zum Ende der Sitzung verfügbar.</span><span class="sxs-lookup"><span data-stu-id="7eeba-254">It is available until the session ends.</span></span>

<span data-ttu-id="7eeba-255">Wenn Sie Ihre Funktion in allen PowerShell-Sitzungen verwenden möchten, fügen Sie die Funktion Ihrem PowerShell-Profil hinzu.</span><span class="sxs-lookup"><span data-stu-id="7eeba-255">To use your function in all PowerShell sessions, add the function to your PowerShell profile.</span></span> <span data-ttu-id="7eeba-256">Weitere Informationen zu Profilen finden Sie unter [about_Profiles](about_Profiles.md).</span><span class="sxs-lookup"><span data-stu-id="7eeba-256">For more information about profiles, see [about_Profiles](about_Profiles.md).</span></span>

<span data-ttu-id="7eeba-257">Sie können Ihre Funktion auch in einer PowerShell-Skriptdatei speichern.</span><span class="sxs-lookup"><span data-stu-id="7eeba-257">You can also save your function in a PowerShell script file.</span></span> <span data-ttu-id="7eeba-258">Geben Sie Ihre Funktion in eine Textdatei ein, und speichern Sie die Datei mit der `.ps1` Dateinamenerweiterung.</span><span class="sxs-lookup"><span data-stu-id="7eeba-258">Type your function in a text file, and then save the file with the `.ps1` file name extension.</span></span>

## <a name="writing-help-for-functions"></a><span data-ttu-id="7eeba-259">Schreiben von Hilfe für Funktionen</span><span class="sxs-lookup"><span data-stu-id="7eeba-259">Writing Help for Functions</span></span>

<span data-ttu-id="7eeba-260">Das- `Get-Help` Cmdlet ruft Hilfe für Funktionen sowie für Cmdlets, Anbieter und Skripts ab.</span><span class="sxs-lookup"><span data-stu-id="7eeba-260">The `Get-Help` cmdlet gets help for functions, as well as for cmdlets, providers, and scripts.</span></span> <span data-ttu-id="7eeba-261">Um Hilfe zu einer Funktion zu erhalten, geben Sie `Get-Help` gefolgt vom Funktionsnamen ein.</span><span class="sxs-lookup"><span data-stu-id="7eeba-261">To get help for a function, type `Get-Help` followed by the function name.</span></span>

<span data-ttu-id="7eeba-262">Wenn Sie beispielsweise Hilfe für die Funktion benötigen, geben Sie Folgendes ein `Get-MyDisks` :</span><span class="sxs-lookup"><span data-stu-id="7eeba-262">For example, to get help for the `Get-MyDisks` function, type:</span></span>

```powershell
Get-Help Get-MyDisks
```

<span data-ttu-id="7eeba-263">Sie können die Hilfe für eine Funktion mit einer der beiden folgenden Methoden schreiben:</span><span class="sxs-lookup"><span data-stu-id="7eeba-263">You can write help for a function by using either of the two following methods:</span></span>

- <span data-ttu-id="7eeba-264">Comment-Based Hilfe zu Funktionen</span><span class="sxs-lookup"><span data-stu-id="7eeba-264">Comment-Based Help for Functions</span></span>

  <span data-ttu-id="7eeba-265">Erstellen Sie ein Hilfethema mithilfe von speziellen Schlüsselwörtern in den Kommentaren.</span><span class="sxs-lookup"><span data-stu-id="7eeba-265">Create a help topic by using special keywords in the comments.</span></span> <span data-ttu-id="7eeba-266">Um eine Kommentar basierte Hilfe für eine Funktion zu erstellen, müssen die Kommentare am Anfang oder Ende des Funktions Texts oder in den Zeilen platziert werden, die dem Function-Schlüsselwort vorangestellt sind.</span><span class="sxs-lookup"><span data-stu-id="7eeba-266">To create comment-based help for a function, the comments must be placed at the beginning or end of the function body or on the lines preceding the function keyword.</span></span> <span data-ttu-id="7eeba-267">Weitere Informationen zur Kommentar basierten Hilfe finden Sie unter [about_Comment_Based_Help](about_Comment_Based_Help.md).</span><span class="sxs-lookup"><span data-stu-id="7eeba-267">For more information about comment-based help, see [about_Comment_Based_Help](about_Comment_Based_Help.md).</span></span>

- <span data-ttu-id="7eeba-268">XML-Based Hilfe zu Funktionen</span><span class="sxs-lookup"><span data-stu-id="7eeba-268">XML-Based Help for Functions</span></span>

  <span data-ttu-id="7eeba-269">Erstellen Sie ein XML-basiertes Hilfethema, z. b. den Typ, der in der Regel für Cmdlets erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="7eeba-269">Create an XML-based help topic, such as the type that is typically created for cmdlets.</span></span> <span data-ttu-id="7eeba-270">Die XML-basierte Hilfe ist erforderlich, wenn Sie Hilfe Themen in mehreren Sprachen lokalisieren.</span><span class="sxs-lookup"><span data-stu-id="7eeba-270">XML-based help is required if you are localizing help topics into multiple languages.</span></span>

  <span data-ttu-id="7eeba-271">Um die Funktion dem XML-basierten Hilfethema zuzuordnen, verwenden Sie das `.ExternalHelp` Kommentar basierte Hilfe Schlüsselwort.</span><span class="sxs-lookup"><span data-stu-id="7eeba-271">To associate the function with the XML-based help topic, use the `.ExternalHelp` comment-based help keyword.</span></span> <span data-ttu-id="7eeba-272">Ohne dieses Schlüsselwort `Get-Help` kann das Funktions Hilfethema nicht finden, und Aufrufe von `Get-Help` für die Funktion geben nur automatisch generierte Hilfe zurück.</span><span class="sxs-lookup"><span data-stu-id="7eeba-272">Without this keyword, `Get-Help` cannot find the function help topic and calls to `Get-Help` for the function return only auto-generated help.</span></span>

  <span data-ttu-id="7eeba-273">Weitere Informationen zum- `ExternalHelp` Schlüsselwort finden Sie unter [about_Comment_Based_Help](about_Comment_Based_Help.md).</span><span class="sxs-lookup"><span data-stu-id="7eeba-273">For more information about the `ExternalHelp` keyword, see [about_Comment_Based_Help](about_Comment_Based_Help.md).</span></span> <span data-ttu-id="7eeba-274">Weitere Informationen zur XML-basierten Hilfe finden Sie unter [How to Write Cmdlet Help](/powershell/scripting/developer/help/writing-help-for-windows-powershell-cmdlets).</span><span class="sxs-lookup"><span data-stu-id="7eeba-274">For more information about XML-based help, see [How to Write Cmdlet Help](/powershell/scripting/developer/help/writing-help-for-windows-powershell-cmdlets).</span></span>

## <a name="see-also"></a><span data-ttu-id="7eeba-275">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7eeba-275">See also</span></span>

[<span data-ttu-id="7eeba-276">about_Automatic_Variables</span><span class="sxs-lookup"><span data-stu-id="7eeba-276">about_Automatic_Variables</span></span>](about_Automatic_Variables.md)

[<span data-ttu-id="7eeba-277">about_Comment_Based_Help</span><span class="sxs-lookup"><span data-stu-id="7eeba-277">about_Comment_Based_Help</span></span>](about_Comment_Based_Help.md)

[<span data-ttu-id="7eeba-278">about_Functions_Advanced</span><span class="sxs-lookup"><span data-stu-id="7eeba-278">about_Functions_Advanced</span></span>](about_Functions_Advanced.md)

[<span data-ttu-id="7eeba-279">about_Functions_Advanced_Methods</span><span class="sxs-lookup"><span data-stu-id="7eeba-279">about_Functions_Advanced_Methods</span></span>](about_Functions_Advanced_Methods.md)

[<span data-ttu-id="7eeba-280">about_Functions_Advanced_Parameters</span><span class="sxs-lookup"><span data-stu-id="7eeba-280">about_Functions_Advanced_Parameters</span></span>](about_Functions_Advanced_Parameters.md)

[<span data-ttu-id="7eeba-281">about_Functions_CmdletBindingAttribute</span><span class="sxs-lookup"><span data-stu-id="7eeba-281">about_Functions_CmdletBindingAttribute</span></span>](about_Functions_CmdletBindingAttribute.md)

[<span data-ttu-id="7eeba-282">about_Functions_OutputTypeAttribute</span><span class="sxs-lookup"><span data-stu-id="7eeba-282">about_Functions_OutputTypeAttribute</span></span>](about_Functions_OutputTypeAttribute.md)

[<span data-ttu-id="7eeba-283">about_Parameters</span><span class="sxs-lookup"><span data-stu-id="7eeba-283">about_Parameters</span></span>](about_Parameters.md)

[<span data-ttu-id="7eeba-284">about_Profiles</span><span class="sxs-lookup"><span data-stu-id="7eeba-284">about_Profiles</span></span>](about_Profiles.md)

[<span data-ttu-id="7eeba-285">about_Scopes</span><span class="sxs-lookup"><span data-stu-id="7eeba-285">about_Scopes</span></span>](about_Scopes.md)

[<span data-ttu-id="7eeba-286">about_Script_Blocks</span><span class="sxs-lookup"><span data-stu-id="7eeba-286">about_Script_Blocks</span></span>](about_Script_Blocks.md)

[<span data-ttu-id="7eeba-287">about_Function_provider</span><span class="sxs-lookup"><span data-stu-id="7eeba-287">about_Function_provider</span></span>](about_Function_provider.md)