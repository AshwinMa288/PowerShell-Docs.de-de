---
description: Beschreibt, wie eine Verweistyp Variable erstellt und verwendet wird. Sie können Verweistyp Variablen verwenden, um es einer Funktion zu gestatten, den Wert einer Variablen zu ändern, die an Sie übermittelt wird.
Locale: en-US
ms.date: 08/24/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_ref?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Ref
ms.openlocfilehash: 5b966816c8ac1ef91e03c78378f57fa20b5697de
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99601304"
---
# <a name="about-ref"></a><span data-ttu-id="89111-104">Informationen zu Ref</span><span class="sxs-lookup"><span data-stu-id="89111-104">About Ref</span></span>

## <a name="short-description"></a><span data-ttu-id="89111-105">Kurze Beschreibung</span><span class="sxs-lookup"><span data-stu-id="89111-105">Short description</span></span>
<span data-ttu-id="89111-106">Beschreibt, wie eine Verweistyp Variable erstellt und verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="89111-106">Describes how to create and use a reference type variable.</span></span> <span data-ttu-id="89111-107">Sie können Verweistyp Variablen verwenden, um es einer Funktion zu gestatten, den Wert einer Variablen zu ändern, die an Sie übermittelt wird.</span><span class="sxs-lookup"><span data-stu-id="89111-107">You can use reference type variables to permit a function to change the value of a variable that is passed to it.</span></span>

## <a name="long-description"></a><span data-ttu-id="89111-108">Lange Beschreibung</span><span class="sxs-lookup"><span data-stu-id="89111-108">Long description</span></span>

<span data-ttu-id="89111-109">Sie können Variablen als *Verweis* oder als *Wert* an Funktionen übergeben.</span><span class="sxs-lookup"><span data-stu-id="89111-109">You can pass variables to functions *by reference* or *by value*.</span></span>

<span data-ttu-id="89111-110">Wenn Sie eine Variable als *Wert* übergeben, übergeben Sie eine Kopie der Daten.</span><span class="sxs-lookup"><span data-stu-id="89111-110">When you pass a variable *by value*, you are passing a copy of the data.</span></span>

<span data-ttu-id="89111-111">Im folgenden Beispiel ändert die-Funktion den Wert der an Sie übergebenen-Variablen.</span><span class="sxs-lookup"><span data-stu-id="89111-111">In the following example, the function changes the value of the variable passed to it.</span></span> <span data-ttu-id="89111-112">In PowerShell sind ganze Zahlen Werttypen, sodass Sie als Wert übermittelt werden.</span><span class="sxs-lookup"><span data-stu-id="89111-112">In PowerShell, integers are value types so they are passed by value.</span></span>
<span data-ttu-id="89111-113">Daher bleibt der Wert von `$var` außerhalb des Gültigkeits Bereichs der Funktion unverändert.</span><span class="sxs-lookup"><span data-stu-id="89111-113">Therefore, the value of `$var` is unchanged outside the scope of the function.</span></span>

```powershell
Function Test($data)
{
    $data = 3
}

$var = 10
Test -data $var
$var
```

```output
10
```

<span data-ttu-id="89111-114">Im folgenden Beispiel wird eine Variable, die eine enthält, `Hashtable` an eine Funktion übermittelt.</span><span class="sxs-lookup"><span data-stu-id="89111-114">In the following example, a variable containing a `Hashtable` is passed to a function.</span></span> <span data-ttu-id="89111-115">`Hashtable` ist ein Objekttyp, der standardmäßig als *Verweis* an die Funktion übermittelt wird.</span><span class="sxs-lookup"><span data-stu-id="89111-115">`Hashtable` is an object type so by default it is passed to the function *by reference*.</span></span>

<span data-ttu-id="89111-116">Wenn eine Variable als *Verweis* übergeben wird, kann die Funktion die Daten ändern, und diese Änderung bleibt nach der Ausführung der Funktion erhalten.</span><span class="sxs-lookup"><span data-stu-id="89111-116">When passing a variable *by reference*, the function can change the data and that change persists after the function executes.</span></span>

```powershell
Function Test($data)
{
    $data.Test = "New Text"
}

$var = @{}
Test -data $var
$var
```

```output
Name                           Value
----                           -----
Test                           New Text
```

<span data-ttu-id="89111-117">Die-Funktion fügt ein neues Schlüssel-Wert-Paar hinzu, das außerhalb des Gültigkeits Bereichs der Funktion beibehalten wird.</span><span class="sxs-lookup"><span data-stu-id="89111-117">The function adds a new key-value pair that persists outside of the function's scope.</span></span>

### <a name="writing-functions-to-accept-reference-parameters"></a><span data-ttu-id="89111-118">Schreiben von Funktionen zum Akzeptieren von Verweis Parametern</span><span class="sxs-lookup"><span data-stu-id="89111-118">Writing functions to accept reference parameters</span></span>

<span data-ttu-id="89111-119">Sie können ihre Funktionen so codieren, dass ein Parameter als Verweis übernommen wird, unabhängig vom Typ der übergebenen Daten.</span><span class="sxs-lookup"><span data-stu-id="89111-119">You can code your functions to take a parameter as a reference, regardless of the type of data passed.</span></span> <span data-ttu-id="89111-120">Dies erfordert, dass Sie den Parametertyp als `System.Management.Automation.PSReference` , oder angeben `[ref]` .</span><span class="sxs-lookup"><span data-stu-id="89111-120">This requires that you specify the parameters type as `System.Management.Automation.PSReference`, or `[ref]`.</span></span>

<span data-ttu-id="89111-121">Wenn Sie Verweise verwenden, müssen Sie die- `Value` Eigenschaft des- `System.Management.Automation.PSReference` Typs verwenden, um auf Ihre Daten zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="89111-121">When using references, you must use the `Value` property of the `System.Management.Automation.PSReference` type to access your data.</span></span>

```powershell
Function Test([ref]$data)
{
    $data.Value = 3
}
```

<span data-ttu-id="89111-122">Um eine Variable an einen Parameter zu übergeben, der einen Verweis erwartet, müssen Sie die Variable als Verweis umwandeln.</span><span class="sxs-lookup"><span data-stu-id="89111-122">To pass a variable to a parameter that expects a reference, you must type cast your variable as a reference.</span></span>

> [!NOTE]
> <span data-ttu-id="89111-123">Beide Klammern und Klammern sind erforderlich.</span><span class="sxs-lookup"><span data-stu-id="89111-123">The brackets and parenthesis are BOTH required.</span></span>

```powershell
$var = 10
Test -data ([ref]$var)
$var
```

```output
3
```

### <a name="passing-references-to-net-methods"></a><span data-ttu-id="89111-124">Übergeben von verweisen an .NET-Methoden</span><span class="sxs-lookup"><span data-stu-id="89111-124">Passing references to .NET methods</span></span>

<span data-ttu-id="89111-125">Einige .NET-Methoden erfordern möglicherweise, dass Sie eine Variable als Verweis übergeben.</span><span class="sxs-lookup"><span data-stu-id="89111-125">Some .NET methods may require you to pass a variable as a reference.</span></span> <span data-ttu-id="89111-126">Wenn die Definition der Methode die Schlüsselwörter `in` , `out` oder `ref` für einen Parameter verwendet, wird ein Verweis erwartet.</span><span class="sxs-lookup"><span data-stu-id="89111-126">When the method's definition uses the keywords `in`, `out`, or `ref` on a parameter, it expects a reference.</span></span>

```powershell
[int] | Get-Member -Static -Name TryParse
```

```output
Name     MemberType Definition
----     ---------- ----------
TryParse Method     static bool TryParse(string s, [ref] int result)
```

<span data-ttu-id="89111-127">Die- `TryParse` Methode versucht, eine Zeichenfolge als ganze Zahl zu analysieren.</span><span class="sxs-lookup"><span data-stu-id="89111-127">The `TryParse` method attempts to parse a string as an integer.</span></span> <span data-ttu-id="89111-128">Wenn die Methode erfolgreich ist, gibt Sie zurück `$true` , und das Ergebnis wird in der Variablen gespeichert, die Sie als **Verweis über** mittelt haben.</span><span class="sxs-lookup"><span data-stu-id="89111-128">If the method succeeds, it returns `$true`, and the result is stored in the variable you passed **by reference**.</span></span>

```
PS> $number = 0
PS> [int]::TryParse("15", ([ref]$number))
True
PS> $number
15
```

### <a name="references-and-scopes"></a><span data-ttu-id="89111-129">Verweise und Bereiche</span><span class="sxs-lookup"><span data-stu-id="89111-129">References and scopes</span></span>

<span data-ttu-id="89111-130">Verweise ermöglichen, dass der Wert einer Variablen im übergeordneten Bereich innerhalb eines untergeordneten Bereichs geändert wird.</span><span class="sxs-lookup"><span data-stu-id="89111-130">References allow the value of a variable in the parent scope to be changed within a child scope.</span></span>

```powershell
# Create a value type variable.
$i = 0
# Create a reference type variable.
$iRef = [ref]0
# Invoke a scriptblock to attempt to change both values.
&{$i++;$iRef.Value++}
# Output the results.
"`$i = $i;`$iRef = $($iRef.Value)"
```

```output
$i = 0;$iRef = 1
```

<span data-ttu-id="89111-131">Nur die Variable des Verweis Typs wurde geändert.</span><span class="sxs-lookup"><span data-stu-id="89111-131">Only the reference type's variable was changed.</span></span>

## <a name="see-also"></a><span data-ttu-id="89111-132">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="89111-132">See also</span></span>

[<span data-ttu-id="89111-133">about_Variables</span><span class="sxs-lookup"><span data-stu-id="89111-133">about_Variables</span></span>](about_Variables.md)

[<span data-ttu-id="89111-134">about_Environment_Variables</span><span class="sxs-lookup"><span data-stu-id="89111-134">about_Environment_Variables</span></span>](about_Environment_Variables.md)

[<span data-ttu-id="89111-135">about_Functions</span><span class="sxs-lookup"><span data-stu-id="89111-135">about_Functions</span></span>](about_Functions.md)

[<span data-ttu-id="89111-136">about_Script_Blocks</span><span class="sxs-lookup"><span data-stu-id="89111-136">about_Script_Blocks</span></span>](about_Script_Blocks.md)

[<span data-ttu-id="89111-137">about_Scopes</span><span class="sxs-lookup"><span data-stu-id="89111-137">about_Scopes</span></span>](about_scopes.md)

