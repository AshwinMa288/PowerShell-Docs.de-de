---
description: Sowohl ganzzahlige als auch echte numerische Literale können über Typ-und Multiplikator-Suffixe verfügen.
Locale: en-US
ms.date: 04/12/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_numeric_literals?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Informationen zu numerischen Literalen
ms.openlocfilehash: 0e4081c7601928ce9b74010ea3c86762902ca97a
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99599191"
---
# <a name="about-numeric-literals"></a><span data-ttu-id="98e52-103">Informationen zu numerischen Literalen</span><span class="sxs-lookup"><span data-stu-id="98e52-103">About numeric literals</span></span>

<span data-ttu-id="98e52-104">Es gibt zwei Arten numerischer Literale: Integer und Real.</span><span class="sxs-lookup"><span data-stu-id="98e52-104">There are two kinds of numeric literals: integer and real.</span></span> <span data-ttu-id="98e52-105">Beide können über Typ-und Multiplikator-Suffixe verfügen.</span><span class="sxs-lookup"><span data-stu-id="98e52-105">Both can have type and multiplier suffixes.</span></span>

## <a name="integer-literals"></a><span data-ttu-id="98e52-106">Ganzzahlenliteral</span><span class="sxs-lookup"><span data-stu-id="98e52-106">Integer literals</span></span>

<span data-ttu-id="98e52-107">Ganzzahlige Literale können in Dezimal-, Hexadezimal-oder Binär Notation geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="98e52-107">Integer literals can be written in decimal, hexadecimal, or binary notation.</span></span>
<span data-ttu-id="98e52-108">Hexadezimal literalen wird das Präfix vorangestellt `0x` , und binäre Literale werden als Präfix vorangestellt `0b` , um Sie von Dezimalzahlen zu unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="98e52-108">Hexadecimal literals are prefixed with `0x` and binary literals are prefixed with `0b` to distinguish them from decimal numbers.</span></span>

<span data-ttu-id="98e52-109">Ganzzahlige Literale können ein Typsuffix und ein Multiplikator-Suffix aufweisen.</span><span class="sxs-lookup"><span data-stu-id="98e52-109">Integer literals can have a type suffix and a multiplier suffix.</span></span>

| <span data-ttu-id="98e52-110">Suffix</span><span class="sxs-lookup"><span data-stu-id="98e52-110">Suffix</span></span> |            <span data-ttu-id="98e52-111">Bedeutung</span><span class="sxs-lookup"><span data-stu-id="98e52-111">Meaning</span></span>             |          <span data-ttu-id="98e52-112">Hinweis</span><span class="sxs-lookup"><span data-stu-id="98e52-112">Note</span></span>           |
| ------ | ------------------------------ | ----------------------- |
| <span data-ttu-id="98e52-113">j</span><span class="sxs-lookup"><span data-stu-id="98e52-113">y</span></span>      | <span data-ttu-id="98e52-114">Byte-Datentyp mit Vorzeichen</span><span class="sxs-lookup"><span data-stu-id="98e52-114">signed byte data type</span></span>          | <span data-ttu-id="98e52-115">In PowerShell 6,2 hinzugefügt</span><span class="sxs-lookup"><span data-stu-id="98e52-115">Added in PowerShell 6.2</span></span> |
| <span data-ttu-id="98e52-116">uy</span><span class="sxs-lookup"><span data-stu-id="98e52-116">uy</span></span>     | <span data-ttu-id="98e52-117">Datentyp ohne Vorzeichen</span><span class="sxs-lookup"><span data-stu-id="98e52-117">unsigned byte data type</span></span>        | <span data-ttu-id="98e52-118">In PowerShell 6,2 hinzugefügt</span><span class="sxs-lookup"><span data-stu-id="98e52-118">Added in PowerShell 6.2</span></span> |
| <span data-ttu-id="98e52-119">s</span><span class="sxs-lookup"><span data-stu-id="98e52-119">s</span></span>      | <span data-ttu-id="98e52-120">short-Datentyp</span><span class="sxs-lookup"><span data-stu-id="98e52-120">short data type</span></span>                | <span data-ttu-id="98e52-121">In PowerShell 6,2 hinzugefügt</span><span class="sxs-lookup"><span data-stu-id="98e52-121">Added in PowerShell 6.2</span></span> |
| <span data-ttu-id="98e52-122">USA</span><span class="sxs-lookup"><span data-stu-id="98e52-122">us</span></span>     | <span data-ttu-id="98e52-123">Short-Datentyp ohne Vorzeichen</span><span class="sxs-lookup"><span data-stu-id="98e52-123">unsigned short data type</span></span>       | <span data-ttu-id="98e52-124">In PowerShell 6,2 hinzugefügt</span><span class="sxs-lookup"><span data-stu-id="98e52-124">Added in PowerShell 6.2</span></span> |
| <span data-ttu-id="98e52-125">l</span><span class="sxs-lookup"><span data-stu-id="98e52-125">l</span></span>      | <span data-ttu-id="98e52-126">Long-Datentyp</span><span class="sxs-lookup"><span data-stu-id="98e52-126">long data type</span></span>                 |                         |
| <span data-ttu-id="98e52-127">u</span><span class="sxs-lookup"><span data-stu-id="98e52-127">u</span></span>      | <span data-ttu-id="98e52-128">Ganzzahl ohne Vorzeichen int-oder Long-Datentyp</span><span class="sxs-lookup"><span data-stu-id="98e52-128">unsigned int or long data type</span></span> | <span data-ttu-id="98e52-129">In PowerShell 6,2 hinzugefügt</span><span class="sxs-lookup"><span data-stu-id="98e52-129">Added in PowerShell 6.2</span></span> |
| <span data-ttu-id="98e52-130">nützlichen</span><span class="sxs-lookup"><span data-stu-id="98e52-130">ul</span></span>     | <span data-ttu-id="98e52-131">Long-Datentyp ohne Vorzeichen</span><span class="sxs-lookup"><span data-stu-id="98e52-131">unsigned long data type</span></span>        | <span data-ttu-id="98e52-132">In PowerShell 6,2 hinzugefügt</span><span class="sxs-lookup"><span data-stu-id="98e52-132">Added in PowerShell 6.2</span></span> |
| <span data-ttu-id="98e52-133">n</span><span class="sxs-lookup"><span data-stu-id="98e52-133">n</span></span>      | <span data-ttu-id="98e52-134">BigInteger-Datentyp</span><span class="sxs-lookup"><span data-stu-id="98e52-134">BigInteger data type</span></span>           | <span data-ttu-id="98e52-135">In PowerShell 7,0 hinzugefügt</span><span class="sxs-lookup"><span data-stu-id="98e52-135">Added in PowerShell 7.0</span></span> |
| <span data-ttu-id="98e52-136">kb</span><span class="sxs-lookup"><span data-stu-id="98e52-136">kb</span></span>     | <span data-ttu-id="98e52-137">KB-Multiplikator</span><span class="sxs-lookup"><span data-stu-id="98e52-137">kilobyte multiplier</span></span>            |                         |
| <span data-ttu-id="98e52-138">mb</span><span class="sxs-lookup"><span data-stu-id="98e52-138">mb</span></span>     | <span data-ttu-id="98e52-139">Megabyte-Multiplikator</span><span class="sxs-lookup"><span data-stu-id="98e52-139">megabyte multiplier</span></span>            |                         |
| <span data-ttu-id="98e52-140">GB</span><span class="sxs-lookup"><span data-stu-id="98e52-140">gb</span></span>     | <span data-ttu-id="98e52-141">Gigabyte-Multiplikator</span><span class="sxs-lookup"><span data-stu-id="98e52-141">gigabyte multiplier</span></span>            |                         |
| <span data-ttu-id="98e52-142">t</span><span class="sxs-lookup"><span data-stu-id="98e52-142">tb</span></span>     | <span data-ttu-id="98e52-143">Terabyte-Multiplikator</span><span class="sxs-lookup"><span data-stu-id="98e52-143">terabyte multiplier</span></span>            |                         |
| <span data-ttu-id="98e52-144">PB</span><span class="sxs-lookup"><span data-stu-id="98e52-144">pb</span></span>     | <span data-ttu-id="98e52-145">Peer tabyte-Multiplikator</span><span class="sxs-lookup"><span data-stu-id="98e52-145">petabyte multiplier</span></span>            |                         |

<span data-ttu-id="98e52-146">Der Typ eines ganzzahligen Literals wird durch seinen Wert, das Typsuffix und das numerische Multiplikator-Suffix bestimmt.</span><span class="sxs-lookup"><span data-stu-id="98e52-146">The type of an integer literal is determined by its value, the type suffix, and the numeric multiplier suffix.</span></span>

<span data-ttu-id="98e52-147">Für ein Ganzzahlliteral ohne Typsuffix:</span><span class="sxs-lookup"><span data-stu-id="98e52-147">For an integer literal with no type suffix:</span></span>

- <span data-ttu-id="98e52-148">Wenn der Wert durch den Typ dargestellt werden kann `[int]` , ist dies der Typ.</span><span class="sxs-lookup"><span data-stu-id="98e52-148">If the value can be represented by type `[int]`, that is its type.</span></span>
- <span data-ttu-id="98e52-149">Andernfalls, wenn der Wert durch den Typ dargestellt werden kann `[long]` , ist dies der Typ.</span><span class="sxs-lookup"><span data-stu-id="98e52-149">Otherwise, if the value can be represented by type `[long]`, that is its type.</span></span>
- <span data-ttu-id="98e52-150">Andernfalls, wenn der Wert durch den Typ dargestellt werden kann `[decimal]` , ist dies der Typ.</span><span class="sxs-lookup"><span data-stu-id="98e52-150">Otherwise, if the value can be represented by type `[decimal]`, that is its type.</span></span>
- <span data-ttu-id="98e52-151">Andernfalls wird Sie durch den-Typ dargestellt `[double]` .</span><span class="sxs-lookup"><span data-stu-id="98e52-151">Otherwise, it is represented by type `[double]`.</span></span>

<span data-ttu-id="98e52-152">Für ein Ganzzahlliteral mit einem Typsuffix:</span><span class="sxs-lookup"><span data-stu-id="98e52-152">For an integer literal with a type suffix:</span></span>

- <span data-ttu-id="98e52-153">Wenn das Typsuffix ist `u` und der Wert durch den Typ dargestellt werden kann, `[uint]` ist sein Typ `[uint]` .</span><span class="sxs-lookup"><span data-stu-id="98e52-153">If the type suffix is `u` and the value can be represented by type `[uint]` then its type is `[uint]`.</span></span>
- <span data-ttu-id="98e52-154">Wenn das Typsuffix ist `u` und der Wert durch den Typ dargestellt werden kann, `[ulong]` ist sein Typ `[ulong]` .</span><span class="sxs-lookup"><span data-stu-id="98e52-154">If the type suffix is `u` and the value can be represented by type `[ulong]` then its type is `[ulong]`.</span></span>
- <span data-ttu-id="98e52-155">Wenn der Wert durch den angegebenen Typ dargestellt werden kann, ist dieser Typ.</span><span class="sxs-lookup"><span data-stu-id="98e52-155">If its value can be represented by type specified then that is its type.</span></span>
- <span data-ttu-id="98e52-156">Andernfalls ist dieses Literale falsch formatiert.</span><span class="sxs-lookup"><span data-stu-id="98e52-156">Otherwise, that literal is malformed.</span></span>

## <a name="real-literals"></a><span data-ttu-id="98e52-157">Real-Literale</span><span class="sxs-lookup"><span data-stu-id="98e52-157">Real literals</span></span>

<span data-ttu-id="98e52-158">Echte Literale können nur in Dezimal Schreibweise geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="98e52-158">Real literals can only be written in decimal notation.</span></span> <span data-ttu-id="98e52-159">Diese Notation kann nach einem Dezimaltrennzeichen und wissenschaftlicher Schreibweise nach Komma Werten mit einem exponentiellen Teil enthalten.</span><span class="sxs-lookup"><span data-stu-id="98e52-159">This notation can include fractional values following a decimal point and scientific notation using an exponential part.</span></span>

<span data-ttu-id="98e52-160">Der exponentielle Teil enthält ein "e", gefolgt von einem optionalen Vorzeichen (+/-) und einer Zahl, die den Exponenten darstellt.</span><span class="sxs-lookup"><span data-stu-id="98e52-160">The exponential part includes an 'e' followed by an optional sign (+/-) and a number representing the exponent.</span></span> <span data-ttu-id="98e52-161">Beispielsweise ist der Literalwert mit `1e2` dem numerischen Wert 100.</span><span class="sxs-lookup"><span data-stu-id="98e52-161">For example, the literal value `1e2` equals the numeric value 100.</span></span>

<span data-ttu-id="98e52-162">Echte Literale können ein Typsuffix und ein Multiplikator-Suffix aufweisen.</span><span class="sxs-lookup"><span data-stu-id="98e52-162">Real literals can have a type suffix and a multiplier suffix.</span></span>

| <span data-ttu-id="98e52-163">Suffix</span><span class="sxs-lookup"><span data-stu-id="98e52-163">Suffix</span></span> |       <span data-ttu-id="98e52-164">Bedeutung</span><span class="sxs-lookup"><span data-stu-id="98e52-164">Meaning</span></span>       |
| ------ | ------------------- |
| <span data-ttu-id="98e52-165">T</span><span class="sxs-lookup"><span data-stu-id="98e52-165">d</span></span>      | <span data-ttu-id="98e52-166">decimal-Datentyp</span><span class="sxs-lookup"><span data-stu-id="98e52-166">decimal data type</span></span>   |
| <span data-ttu-id="98e52-167">kb</span><span class="sxs-lookup"><span data-stu-id="98e52-167">kb</span></span>     | <span data-ttu-id="98e52-168">KB-Multiplikator</span><span class="sxs-lookup"><span data-stu-id="98e52-168">kilobyte multiplier</span></span> |
| <span data-ttu-id="98e52-169">mb</span><span class="sxs-lookup"><span data-stu-id="98e52-169">mb</span></span>     | <span data-ttu-id="98e52-170">Megabyte-Multiplikator</span><span class="sxs-lookup"><span data-stu-id="98e52-170">megabyte multiplier</span></span> |
| <span data-ttu-id="98e52-171">GB</span><span class="sxs-lookup"><span data-stu-id="98e52-171">gb</span></span>     | <span data-ttu-id="98e52-172">Gigabyte-Multiplikator</span><span class="sxs-lookup"><span data-stu-id="98e52-172">gigabyte multiplier</span></span> |
| <span data-ttu-id="98e52-173">t</span><span class="sxs-lookup"><span data-stu-id="98e52-173">tb</span></span>     | <span data-ttu-id="98e52-174">Terabyte-Multiplikator</span><span class="sxs-lookup"><span data-stu-id="98e52-174">terabyte multiplier</span></span> |
| <span data-ttu-id="98e52-175">PB</span><span class="sxs-lookup"><span data-stu-id="98e52-175">pb</span></span>     | <span data-ttu-id="98e52-176">Peer tabyte-Multiplikator</span><span class="sxs-lookup"><span data-stu-id="98e52-176">petabyte multiplier</span></span> |

<span data-ttu-id="98e52-177">Es gibt zwei Arten von echtem Literalen: Double und Decimal.</span><span class="sxs-lookup"><span data-stu-id="98e52-177">There are two kinds of real literal: double and decimal.</span></span> <span data-ttu-id="98e52-178">Diese werden durch das Fehlen oder vorhanden sein des Suffixes Decimal angegeben.</span><span class="sxs-lookup"><span data-stu-id="98e52-178">These are indicated by the absence or presence, respectively, of decimal-type suffix.</span></span> <span data-ttu-id="98e52-179">PowerShell unterstützt keine Literale Darstellung eines `[float]` Werts.</span><span class="sxs-lookup"><span data-stu-id="98e52-179">PowerShell does not support a literal representation of a `[float]` value.</span></span> <span data-ttu-id="98e52-180">Ein Double Real-Literale weist den Typ auf `[double]` .</span><span class="sxs-lookup"><span data-stu-id="98e52-180">A double real literal has type `[double]`.</span></span> <span data-ttu-id="98e52-181">Ein tatsächliches Dezimaltrennzeichen weist den Typ auf `[decimal]` .</span><span class="sxs-lookup"><span data-stu-id="98e52-181">A decimal real literal has type `[decimal]`.</span></span>
<span data-ttu-id="98e52-182">Nachfolgende Nullen im Bruchteil eines Dezimal-Real-Literals sind signifikant.</span><span class="sxs-lookup"><span data-stu-id="98e52-182">Trailing zeros in the fraction part of a decimal real literal are significant.</span></span>

<span data-ttu-id="98e52-183">Wenn der Wert der Ziffern von Exponent-Part in einem `[double]` echten literalen kleiner als der unterstützte Mindestwert ist, ist der Wert dieses `[double]` echten Literals 0.</span><span class="sxs-lookup"><span data-stu-id="98e52-183">If the value of exponent-part's digits in a `[double]` real literal is less than the minimum supported, the value of that `[double]` real literal is 0.</span></span> <span data-ttu-id="98e52-184">Wenn der Wert der Ziffern von Exponent-Part in einem `[decimal]` echten literalen kleiner als der unterstützte Mindestwert ist, ist dieses Literalformat falsch formatiert.</span><span class="sxs-lookup"><span data-stu-id="98e52-184">If the value of exponent-part's digits in a `[decimal]` real literal is less than the minimum supported, that literal is malformed.</span></span> <span data-ttu-id="98e52-185">Wenn der Wert der Ziffern Exponent-Part in einem `[double]` oder einem `[decimal]` realen Literalwert größer als der maximal unterstützte Wert ist, ist dieses Literalformat falsch formatiert.</span><span class="sxs-lookup"><span data-stu-id="98e52-185">If the value of exponent-part's digits in a `[double]` or `[decimal]` real literal is greater than the maximum supported, that literal is malformed.</span></span>

> [!NOTE]
> <span data-ttu-id="98e52-186">Die Syntax ermöglicht einem Double Real-literalen das Suffix long-Type.</span><span class="sxs-lookup"><span data-stu-id="98e52-186">The syntax permits a double real literal to have a long-type suffix.</span></span>
> <span data-ttu-id="98e52-187">PowerShell behandelt diesen Fall als Ganzzahlliteral, dessen Wert durch den Typ dargestellt wird `[long]` .</span><span class="sxs-lookup"><span data-stu-id="98e52-187">PowerShell treats this case as an integer literal whose value is represented by type `[long]`.</span></span> <span data-ttu-id="98e52-188">Diese Funktion wurde aus Gründen der Abwärtskompatibilität mit früheren Versionen von PowerShell beibehalten.</span><span class="sxs-lookup"><span data-stu-id="98e52-188">This feature has been retained for backwards compatibility with earlier versions of PowerShell.</span></span> <span data-ttu-id="98e52-189">Programmierer werden jedoch davon abgeraten, ganzzahlige Literale dieses Formulars zu verwenden, da Sie den tatsächlichen Wert des Literale leicht verdecken können.</span><span class="sxs-lookup"><span data-stu-id="98e52-189">However, programmers are discouraged from using integer literals of this form as they can easily obscure the literal's actual value.</span></span> <span data-ttu-id="98e52-190">Hat z. b. den `1.2L` Wert 1, den `1.2345e1L` Wert 12 und `1.2345e-5L` den Wert 0, von denen keiner sofort ersichtlich ist.</span><span class="sxs-lookup"><span data-stu-id="98e52-190">For example, `1.2L` has value 1, `1.2345e1L` has value 12, and `1.2345e-5L` has value 0, none of which are immediately obvious.</span></span>

## <a name="numeric-multipliers"></a><span data-ttu-id="98e52-191">Numerische Multiplikatoren</span><span class="sxs-lookup"><span data-stu-id="98e52-191">Numeric multipliers</span></span>

<span data-ttu-id="98e52-192">Aus praktischen Gründen können ganzzahlige und echte Literale einen numerischen Multiplikator enthalten, der einen der häufig verwendeten Kräfte von 2 angibt.</span><span class="sxs-lookup"><span data-stu-id="98e52-192">For convenience, integer and real literals can contain a numeric multiplier, which indicates one of a set of commonly used powers of 2.</span></span> <span data-ttu-id="98e52-193">Der numerische Multiplikator kann in einer beliebigen Kombination aus Groß-oder Kleinbuchstaben geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="98e52-193">The numeric multiplier can be written in any combination of upper or lowercase letters.</span></span>

<span data-ttu-id="98e52-194">Die Multiplikator-Suffixe können in Kombination mit beliebigen typsuffixen verwendet werden, müssen jedoch nach dem Typsuffix vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="98e52-194">The multiplier suffixes can be used in combination with any type suffixes, but must be present after the type suffix.</span></span> <span data-ttu-id="98e52-195">Beispielsweise ist das Literale falsch formatiert `100gbL` , aber das Literale `100Lgb` ist gültig.</span><span class="sxs-lookup"><span data-stu-id="98e52-195">For example, the literal `100gbL` is malformed, but the literal `100Lgb` is valid.</span></span>

<span data-ttu-id="98e52-196">Wenn ein Multiplikator einen Wert erstellt, der die möglichen Werte für den numerischen Typ überschreitet, den das Suffix angibt, ist das Literale falsch formatiert.</span><span class="sxs-lookup"><span data-stu-id="98e52-196">If a multiplier creates a value that exceeds the possible values for the numeric type that the suffix specifies, the literal is malformed.</span></span> <span data-ttu-id="98e52-197">Beispielsweise ist das Literale falsch formatiert `1usgb` , da der Wert größer ist als der Wert, der `1gb` für den `[ushort]` durch das Suffix angegebenen Typ zulässig ist `us` .</span><span class="sxs-lookup"><span data-stu-id="98e52-197">For example, the literal `1usgb` is malformed, because the value `1gb` is larger than what is permitted for the `[ushort]` type specified by the `us` suffix.</span></span>

### <a name="multiplier-examples"></a><span data-ttu-id="98e52-198">Multiplikator-Beispiele</span><span class="sxs-lookup"><span data-stu-id="98e52-198">Multiplier examples</span></span>

```
PS> 1kb
1024

PS> 1.30Dmb
1363148.80

PS> 0x10Gb
17179869184

PS> 1.4e23tb
1.5393162788864E+35

PS> 0x12Lpb
20266198323167232
```

## <a name="numeric-type-accelerators"></a><span data-ttu-id="98e52-199">Numerische typacceleratoren</span><span class="sxs-lookup"><span data-stu-id="98e52-199">Numeric type accelerators</span></span>

<span data-ttu-id="98e52-200">PowerShell unterstützt die folgenden typacceleratoren:</span><span class="sxs-lookup"><span data-stu-id="98e52-200">PowerShell supports the following type accelerators:</span></span>

| <span data-ttu-id="98e52-201">Accelerator</span><span class="sxs-lookup"><span data-stu-id="98e52-201">Accelerator</span></span> |         <span data-ttu-id="98e52-202">Hinweis</span><span class="sxs-lookup"><span data-stu-id="98e52-202">Note</span></span>         |           <span data-ttu-id="98e52-203">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="98e52-203">Description</span></span>            |
| ----------- | -------------------- | -------------------------------- |
| `[byte]`    |                      | <span data-ttu-id="98e52-204">Byte (ohne Vorzeichen)</span><span class="sxs-lookup"><span data-stu-id="98e52-204">Byte (unsigned)</span></span>                  |
| `[sbyte]`   |                      | <span data-ttu-id="98e52-205">Byte (signiert)</span><span class="sxs-lookup"><span data-stu-id="98e52-205">Byte (signed)</span></span>                    |
| `[Int16]`   |                      | <span data-ttu-id="98e52-206">16-Bit-Ganzzahl</span><span class="sxs-lookup"><span data-stu-id="98e52-206">16-bit integer</span></span>                   |
| `[short]`   | <span data-ttu-id="98e52-207">Alias für `[int16]`</span><span class="sxs-lookup"><span data-stu-id="98e52-207">alias for `[int16]`</span></span>  | <span data-ttu-id="98e52-208">16-Bit-Ganzzahl</span><span class="sxs-lookup"><span data-stu-id="98e52-208">16-bit integer</span></span>                   |
| `[UInt16]`  |                      | <span data-ttu-id="98e52-209">16-Bit-Ganzzahl (ohne Vorzeichen)</span><span class="sxs-lookup"><span data-stu-id="98e52-209">16-bit integer (unsigned)</span></span>        |
| `[ushort]`  | <span data-ttu-id="98e52-210">Alias für `[uint16]`</span><span class="sxs-lookup"><span data-stu-id="98e52-210">alias for `[uint16]`</span></span> | <span data-ttu-id="98e52-211">16-Bit-Ganzzahl (ohne Vorzeichen)</span><span class="sxs-lookup"><span data-stu-id="98e52-211">16-bit integer (unsigned)</span></span>        |
| `[Int32]`   |                      | <span data-ttu-id="98e52-212">32-bit integer</span><span class="sxs-lookup"><span data-stu-id="98e52-212">32-bit integer</span></span>                   |
| `[int]`     | <span data-ttu-id="98e52-213">Alias für `[int32]`</span><span class="sxs-lookup"><span data-stu-id="98e52-213">alias for `[int32]`</span></span>  | <span data-ttu-id="98e52-214">32-bit integer</span><span class="sxs-lookup"><span data-stu-id="98e52-214">32-bit integer</span></span>                   |
| `[UInt32]`  |                      | <span data-ttu-id="98e52-215">32-Bit-Ganzzahl (ohne Vorzeichen)</span><span class="sxs-lookup"><span data-stu-id="98e52-215">32-bit integer (unsigned)</span></span>        |
| `[uint]`    | <span data-ttu-id="98e52-216">Alias für `[uint32]`</span><span class="sxs-lookup"><span data-stu-id="98e52-216">alias for `[uint32]`</span></span> | <span data-ttu-id="98e52-217">32-Bit-Ganzzahl (ohne Vorzeichen)</span><span class="sxs-lookup"><span data-stu-id="98e52-217">32-bit integer (unsigned)</span></span>        |
| `[Int64]`   |                      | <span data-ttu-id="98e52-218">64-Bit-Integer</span><span class="sxs-lookup"><span data-stu-id="98e52-218">64-bit integer</span></span>                   |
| `[long]`    | <span data-ttu-id="98e52-219">Alias für `[int64]`</span><span class="sxs-lookup"><span data-stu-id="98e52-219">alias for `[int64]`</span></span>  | <span data-ttu-id="98e52-220">64-Bit-Integer</span><span class="sxs-lookup"><span data-stu-id="98e52-220">64-bit integer</span></span>                   |
| `[UInt64]`  |                      | <span data-ttu-id="98e52-221">64-Bit-Ganzzahl (ohne Vorzeichen)</span><span class="sxs-lookup"><span data-stu-id="98e52-221">64-bit integer (unsigned)</span></span>        |
| `[ulong]`   | <span data-ttu-id="98e52-222">Alias für `[uint64]`</span><span class="sxs-lookup"><span data-stu-id="98e52-222">alias for `[uint64]`</span></span> | <span data-ttu-id="98e52-223">64-Bit-Ganzzahl (ohne Vorzeichen)</span><span class="sxs-lookup"><span data-stu-id="98e52-223">64-bit integer (unsigned)</span></span>        |
| `[bigint]`  |                      | <span data-ttu-id="98e52-224">Siehe [BigInteger-Struktur][bigint]</span><span class="sxs-lookup"><span data-stu-id="98e52-224">See [BigInteger Struct][bigint]</span></span>  |
| `[single]`  |                      | <span data-ttu-id="98e52-225">Gleit Komma mit einfacher Genauigkeit</span><span class="sxs-lookup"><span data-stu-id="98e52-225">Single precision floating point</span></span>  |
| `[float]`   | <span data-ttu-id="98e52-226">Alias für `[single]`</span><span class="sxs-lookup"><span data-stu-id="98e52-226">alias for `[single]`</span></span> | <span data-ttu-id="98e52-227">Gleit Komma mit einfacher Genauigkeit</span><span class="sxs-lookup"><span data-stu-id="98e52-227">Single precision floating point</span></span>  |
| `[double]`  |                      | <span data-ttu-id="98e52-228">Gleit Komma Wert mit doppelter Genauigkeit</span><span class="sxs-lookup"><span data-stu-id="98e52-228">Double precision floating point</span></span>  |
| `[decimal]` |                      | <span data-ttu-id="98e52-229">128-Bit-Gleit Komma Zahl</span><span class="sxs-lookup"><span data-stu-id="98e52-229">128-bit floating point</span></span>           |

> [!NOTE]
> <span data-ttu-id="98e52-230">Die folgenden typacceleratoren wurden in PowerShell 6,2 hinzugefügt: `[short]` , `[ushort]` , `[uint]` , `[ulong]` .</span><span class="sxs-lookup"><span data-stu-id="98e52-230">The following type accelerators were added in PowerShell 6.2: `[short]`, `[ushort]`, `[uint]`, `[ulong]`.</span></span>

## <a name="examples"></a><span data-ttu-id="98e52-231">Beispiele</span><span class="sxs-lookup"><span data-stu-id="98e52-231">Examples</span></span>

<span data-ttu-id="98e52-232">Die folgende Tabelle enthält einige Beispiele für numerische Literale und listet deren Typ und Wert auf:</span><span class="sxs-lookup"><span data-stu-id="98e52-232">The following table contains several examples of numeric literals and lists their type and value:</span></span>

|   <span data-ttu-id="98e52-233">Zahl</span><span class="sxs-lookup"><span data-stu-id="98e52-233">Number</span></span>    |    <span data-ttu-id="98e52-234">type</span><span class="sxs-lookup"><span data-stu-id="98e52-234">Type</span></span>    |    <span data-ttu-id="98e52-235">Wert</span><span class="sxs-lookup"><span data-stu-id="98e52-235">Value</span></span>     |
| ----------: | ---------- | -----------: |
|         <span data-ttu-id="98e52-236">100</span><span class="sxs-lookup"><span data-stu-id="98e52-236">100</span></span> | <span data-ttu-id="98e52-237">Int32</span><span class="sxs-lookup"><span data-stu-id="98e52-237">Int32</span></span>      |          <span data-ttu-id="98e52-238">100</span><span class="sxs-lookup"><span data-stu-id="98e52-238">100</span></span> |
|        <span data-ttu-id="98e52-239">100 u</span><span class="sxs-lookup"><span data-stu-id="98e52-239">100u</span></span> | <span data-ttu-id="98e52-240">UInt32</span><span class="sxs-lookup"><span data-stu-id="98e52-240">UInt32</span></span>     |          <span data-ttu-id="98e52-241">100</span><span class="sxs-lookup"><span data-stu-id="98e52-241">100</span></span> |
|        <span data-ttu-id="98e52-242">100 d</span><span class="sxs-lookup"><span data-stu-id="98e52-242">100D</span></span> | <span data-ttu-id="98e52-243">Decimal</span><span class="sxs-lookup"><span data-stu-id="98e52-243">Decimal</span></span>    |          <span data-ttu-id="98e52-244">100</span><span class="sxs-lookup"><span data-stu-id="98e52-244">100</span></span> |
|        <span data-ttu-id="98e52-245">100 l</span><span class="sxs-lookup"><span data-stu-id="98e52-245">100l</span></span> | <span data-ttu-id="98e52-246">Int64</span><span class="sxs-lookup"><span data-stu-id="98e52-246">Int64</span></span>      |          <span data-ttu-id="98e52-247">100</span><span class="sxs-lookup"><span data-stu-id="98e52-247">100</span></span> |
|       <span data-ttu-id="98e52-248">100 UL</span><span class="sxs-lookup"><span data-stu-id="98e52-248">100uL</span></span> | <span data-ttu-id="98e52-249">UInt64</span><span class="sxs-lookup"><span data-stu-id="98e52-249">UInt64</span></span>     |          <span data-ttu-id="98e52-250">100</span><span class="sxs-lookup"><span data-stu-id="98e52-250">100</span></span> |
|       <span data-ttu-id="98e52-251">100 US-</span><span class="sxs-lookup"><span data-stu-id="98e52-251">100us</span></span> | <span data-ttu-id="98e52-252">UInt16</span><span class="sxs-lookup"><span data-stu-id="98e52-252">UInt16</span></span>     |          <span data-ttu-id="98e52-253">100</span><span class="sxs-lookup"><span data-stu-id="98e52-253">100</span></span> |
|       <span data-ttu-id="98e52-254">100 uy</span><span class="sxs-lookup"><span data-stu-id="98e52-254">100uy</span></span> | <span data-ttu-id="98e52-255">Byte</span><span class="sxs-lookup"><span data-stu-id="98e52-255">Byte</span></span>       |          <span data-ttu-id="98e52-256">100</span><span class="sxs-lookup"><span data-stu-id="98e52-256">100</span></span> |
|        <span data-ttu-id="98e52-257">100 y</span><span class="sxs-lookup"><span data-stu-id="98e52-257">100y</span></span> | <span data-ttu-id="98e52-258">SByte</span><span class="sxs-lookup"><span data-stu-id="98e52-258">SByte</span></span>      |          <span data-ttu-id="98e52-259">100</span><span class="sxs-lookup"><span data-stu-id="98e52-259">100</span></span> |
|         <span data-ttu-id="98e52-260">1E2</span><span class="sxs-lookup"><span data-stu-id="98e52-260">1e2</span></span> | <span data-ttu-id="98e52-261">Double</span><span class="sxs-lookup"><span data-stu-id="98e52-261">Double</span></span>     |          <span data-ttu-id="98e52-262">100</span><span class="sxs-lookup"><span data-stu-id="98e52-262">100</span></span> |
|        <span data-ttu-id="98e52-263">1. E2</span><span class="sxs-lookup"><span data-stu-id="98e52-263">1.e2</span></span> | <span data-ttu-id="98e52-264">Double</span><span class="sxs-lookup"><span data-stu-id="98e52-264">Double</span></span>     |          <span data-ttu-id="98e52-265">100</span><span class="sxs-lookup"><span data-stu-id="98e52-265">100</span></span> |
|       <span data-ttu-id="98e52-266">0x1e2</span><span class="sxs-lookup"><span data-stu-id="98e52-266">0x1e2</span></span> | <span data-ttu-id="98e52-267">Int32</span><span class="sxs-lookup"><span data-stu-id="98e52-267">Int32</span></span>      |          <span data-ttu-id="98e52-268">482</span><span class="sxs-lookup"><span data-stu-id="98e52-268">482</span></span> |
|      <span data-ttu-id="98e52-269">0x1e2l</span><span class="sxs-lookup"><span data-stu-id="98e52-269">0x1e2L</span></span> | <span data-ttu-id="98e52-270">Int64</span><span class="sxs-lookup"><span data-stu-id="98e52-270">Int64</span></span>      |          <span data-ttu-id="98e52-271">482</span><span class="sxs-lookup"><span data-stu-id="98e52-271">482</span></span> |
|      <span data-ttu-id="98e52-272">0x1e2d</span><span class="sxs-lookup"><span data-stu-id="98e52-272">0x1e2D</span></span> | <span data-ttu-id="98e52-273">Int32</span><span class="sxs-lookup"><span data-stu-id="98e52-273">Int32</span></span>      |         <span data-ttu-id="98e52-274">7725</span><span class="sxs-lookup"><span data-stu-id="98e52-274">7725</span></span> |
|        <span data-ttu-id="98e52-275">482d</span><span class="sxs-lookup"><span data-stu-id="98e52-275">482D</span></span> | <span data-ttu-id="98e52-276">Decimal</span><span class="sxs-lookup"><span data-stu-id="98e52-276">Decimal</span></span>    |          <span data-ttu-id="98e52-277">482</span><span class="sxs-lookup"><span data-stu-id="98e52-277">482</span></span> |
|       <span data-ttu-id="98e52-278">482gb</span><span class="sxs-lookup"><span data-stu-id="98e52-278">482gb</span></span> | <span data-ttu-id="98e52-279">Int64</span><span class="sxs-lookup"><span data-stu-id="98e52-279">Int64</span></span>      | <span data-ttu-id="98e52-280">517543559168</span><span class="sxs-lookup"><span data-stu-id="98e52-280">517543559168</span></span> |
|      <span data-ttu-id="98e52-281">482ngb</span><span class="sxs-lookup"><span data-stu-id="98e52-281">482ngb</span></span> | <span data-ttu-id="98e52-282">BigInteger</span><span class="sxs-lookup"><span data-stu-id="98e52-282">BigInteger</span></span> | <span data-ttu-id="98e52-283">517543559168</span><span class="sxs-lookup"><span data-stu-id="98e52-283">517543559168</span></span> |
|    <span data-ttu-id="98e52-284">0x1e2lgb</span><span class="sxs-lookup"><span data-stu-id="98e52-284">0x1e2lgb</span></span> | <span data-ttu-id="98e52-285">Int64</span><span class="sxs-lookup"><span data-stu-id="98e52-285">Int64</span></span>      | <span data-ttu-id="98e52-286">517543559168</span><span class="sxs-lookup"><span data-stu-id="98e52-286">517543559168</span></span> |
|   <span data-ttu-id="98e52-287">0b1011011</span><span class="sxs-lookup"><span data-stu-id="98e52-287">0b1011011</span></span> | <span data-ttu-id="98e52-288">Int32</span><span class="sxs-lookup"><span data-stu-id="98e52-288">Int32</span></span>      |           <span data-ttu-id="98e52-289">91</span><span class="sxs-lookup"><span data-stu-id="98e52-289">91</span></span> |
|     <span data-ttu-id="98e52-290">0xffffs</span><span class="sxs-lookup"><span data-stu-id="98e52-290">0xFFFFs</span></span> | <span data-ttu-id="98e52-291">Int16</span><span class="sxs-lookup"><span data-stu-id="98e52-291">Int16</span></span>      |           <span data-ttu-id="98e52-292">-1</span><span class="sxs-lookup"><span data-stu-id="98e52-292">-1</span></span> |
|  <span data-ttu-id="98e52-293">0xFFFFFFFF</span><span class="sxs-lookup"><span data-stu-id="98e52-293">0xFFFFFFFF</span></span> | <span data-ttu-id="98e52-294">Int32</span><span class="sxs-lookup"><span data-stu-id="98e52-294">Int32</span></span>      |           <span data-ttu-id="98e52-295">-1</span><span class="sxs-lookup"><span data-stu-id="98e52-295">-1</span></span> |
| <span data-ttu-id="98e52-296">-0xFFFFFFFF</span><span class="sxs-lookup"><span data-stu-id="98e52-296">-0xFFFFFFFF</span></span> | <span data-ttu-id="98e52-297">Int32</span><span class="sxs-lookup"><span data-stu-id="98e52-297">Int32</span></span>      |            <span data-ttu-id="98e52-298">1</span><span class="sxs-lookup"><span data-stu-id="98e52-298">1</span></span> |
| <span data-ttu-id="98e52-299">0xffffffffu</span><span class="sxs-lookup"><span data-stu-id="98e52-299">0xFFFFFFFFu</span></span> | <span data-ttu-id="98e52-300">UInt32</span><span class="sxs-lookup"><span data-stu-id="98e52-300">UInt32</span></span>     |   <span data-ttu-id="98e52-301">4294967295</span><span class="sxs-lookup"><span data-stu-id="98e52-301">4294967295</span></span> |

### <a name="working-with-binary-or-hexadecimal-numbers"></a><span data-ttu-id="98e52-302">Arbeiten mit binären oder hexadezimalen Zahlen</span><span class="sxs-lookup"><span data-stu-id="98e52-302">Working with binary or hexadecimal numbers</span></span>

<span data-ttu-id="98e52-303">Übermäßig große binäre oder hexadezimale Literale können als zurückgeben `[bigint]` , anstatt die Analyse fehlschlagen zu müssen, und zwar nur dann, wenn das `n` Suffix angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="98e52-303">Overly large binary or hexadecimal literals can return as `[bigint]` rather than failing the parse, if and only if the `n` suffix is specified.</span></span> <span data-ttu-id="98e52-304">Signier Bits werden jedoch weiterhin oberhalb von `[decimal]` Bereichen berücksichtigt:</span><span class="sxs-lookup"><span data-stu-id="98e52-304">Sign bits are still respected above even `[decimal]` ranges, however:</span></span>

- <span data-ttu-id="98e52-305">Wenn eine binäre Zeichenfolge ein Vielfaches von 8 Bits ist, wird das höchste Bit als Signier Bit behandelt.</span><span class="sxs-lookup"><span data-stu-id="98e52-305">If a binary string is some multiple of 8 bits long, the highest bit is treated as the sign bit.</span></span>
- <span data-ttu-id="98e52-306">Wenn eine hexadezimale Zeichenfolge, die eine Länge von 8 hat, die erste Ziffer 8 oder höher hat, wird die Zahl als negativ behandelt.</span><span class="sxs-lookup"><span data-stu-id="98e52-306">If a hex string, which has a length that is a multiple of 8, has the first digit with 8 or higher, the numeral is treated as negative.</span></span>

<span data-ttu-id="98e52-307">Das Angeben eines nicht signierten Suffixes für binäre und hexadezimale Literale ignoriert Signier Bits.</span><span class="sxs-lookup"><span data-stu-id="98e52-307">Specifying an unsigned suffix on binary and hex literals ignores sign bits.</span></span> <span data-ttu-id="98e52-308">`0xFFFFFFFF`Gibt z. b `-1` . zurück, `0xFFFFFFFFu` gibt jedoch den `[uint]::MaxValue` von 4294967295 zurück.</span><span class="sxs-lookup"><span data-stu-id="98e52-308">For example, `0xFFFFFFFF` returns `-1`, but `0xFFFFFFFFu` returns the `[uint]::MaxValue` of 4294967295.</span></span>

<span data-ttu-id="98e52-309">In PowerShell 7,1 gibt die Verwendung eines typsuffixes für ein hexadezimal Literale nun einen signierten Wert dieses Typs zurück.</span><span class="sxs-lookup"><span data-stu-id="98e52-309">In PowerShell 7.1, using a type suffix on a hex literal now returns a signed value of that type.</span></span> <span data-ttu-id="98e52-310">Beispielsweise gibt der Ausdruck in PowerShell 7,0 `0xFFFFs` einen Fehler zurück, da der positive Wert für einen-Typ zu groß ist `[int16]` .</span><span class="sxs-lookup"><span data-stu-id="98e52-310">For example, in PowerShell 7.0 the expression `0xFFFFs` returns an error because the positive value is too large for an `[int16]` type.</span></span>
<span data-ttu-id="98e52-311">PowerShell 7,1 interpretiert dies als `-1` ein- `[int16]` Typ.</span><span class="sxs-lookup"><span data-stu-id="98e52-311">PowerShell 7.1 interprets this as `-1` that is an `[int16]` type.</span></span>

<span data-ttu-id="98e52-312">Wenn Sie das Literale mit einem Präfix versehen, `0` wird dies umgangen und als nicht signiert behandelt.</span><span class="sxs-lookup"><span data-stu-id="98e52-312">Prefixing the literal with a `0` will bypass this and be treated as unsigned.</span></span>
<span data-ttu-id="98e52-313">Beispiel: `0b011111111`.</span><span class="sxs-lookup"><span data-stu-id="98e52-313">For example: `0b011111111`.</span></span> <span data-ttu-id="98e52-314">Dies kann bei der Arbeit mit Literalen im Bereich notwendig sein `[bigint]` , da die `u` -und- `n` Suffixe nicht kombiniert werden können.</span><span class="sxs-lookup"><span data-stu-id="98e52-314">This can be necessary when working with literals in the `[bigint]` range, as the `u` and `n` suffixes cannot be combined.</span></span>

<span data-ttu-id="98e52-315">Sie können binäre und hexadezimale Literale auch mit dem- `-` Präfix negieren.</span><span class="sxs-lookup"><span data-stu-id="98e52-315">You can also negate binary and hex literals using the `-` prefix.</span></span> <span data-ttu-id="98e52-316">Dies kann zu einer positiven Zahl führen, da Signier Bits zulässig sind.</span><span class="sxs-lookup"><span data-stu-id="98e52-316">This can result in a positive number since sign bits are permitted.</span></span>

<span data-ttu-id="98e52-317">Signier Bits werden für BigInteger-suffixt-Ziffern akzeptiert:</span><span class="sxs-lookup"><span data-stu-id="98e52-317">Sign bits are accepted for BigInteger-suffixed numerals:</span></span>

- <span data-ttu-id="98e52-318">BigInteger-suffixt-suffixt behandelt das hohe Bit eines beliebigen Literals mit einem Längen Vielfaches von 8 Zeichen als Signier Bit.</span><span class="sxs-lookup"><span data-stu-id="98e52-318">BigInteger-suffixed hex treats the high bit of any literal with a length multiple of 8 characters as the sign bit.</span></span> <span data-ttu-id="98e52-319">Die Länge enthält weder das `0x` Präfix noch beliebige Suffixe.</span><span class="sxs-lookup"><span data-stu-id="98e52-319">The length does not include the `0x` prefix or any suffixes.</span></span>
- <span data-ttu-id="98e52-320">Die BigInteger-suffixt-Binärdatei akzeptiert Signier Bits bei 96-und 128-Zeichen und bei jeweils 8 Zeichen nach.</span><span class="sxs-lookup"><span data-stu-id="98e52-320">BigInteger-suffixed binary accepts sign bits at 96 and 128 characters, and at every 8 characters after.</span></span>

### <a name="commands-that-look-like-numeric-literals"></a><span data-ttu-id="98e52-321">Befehle, die wie numerische Literale aussehen</span><span class="sxs-lookup"><span data-stu-id="98e52-321">Commands that look like numeric literals</span></span>

<span data-ttu-id="98e52-322">Jeder Befehl, der wie ein gültiges numerisches Literalformat aussieht, muss mit dem-Operator () ausgeführt werden `&` , andernfalls wird es als Zahl interpretiert.</span><span class="sxs-lookup"><span data-stu-id="98e52-322">Any command that looks like a valid numeric literal must be executed using the call operator (`&`), otherwise it is interpreted as a number.</span></span> <span data-ttu-id="98e52-323">Falsch formatierte Literale mit gültiger Syntax wie `1usgb` führen zu folgendem Fehler:</span><span class="sxs-lookup"><span data-stu-id="98e52-323">Malformed literals with valid syntax like `1usgb` will result in the following error:</span></span>

```
PS> 1usgb
At line:1 char:6
+ 1usgb
+      ~
The numeric constant 1usgb is not valid.
+ CategoryInfo          : ParserError: (:) [], ParentContainsErrorRecordException
+ FullyQualifiedErrorId : BadNumericConstant
```

<span data-ttu-id="98e52-324">Falsch formatierte Literale mit ungültiger Syntax wie werden jedoch `1gbus` als standardmäßige Bare-Zeichenfolge interpretiert und können als gültiger Befehls Name in Kontexten interpretiert werden, in denen Befehle aufgerufen werden können.</span><span class="sxs-lookup"><span data-stu-id="98e52-324">However, malformed literals with invalid syntax like `1gbus` will be interpreted as a standard bare string, and can be interpreted as a valid command name in contexts where commands may be called.</span></span>

### <a name="access-properties-and-methods-of-numeric-objects"></a><span data-ttu-id="98e52-325">Zugreifen auf Eigenschaften und Methoden numerischer Objekte</span><span class="sxs-lookup"><span data-stu-id="98e52-325">Access properties and methods of numeric objects</span></span>

<span data-ttu-id="98e52-326">Wenn Sie auf ein Member eines numerischen Literals zugreifen müssen, gibt es Fälle, in denen Sie das Literale in Klammern einschließen müssen.</span><span class="sxs-lookup"><span data-stu-id="98e52-326">To access a member of a numeric literal, there are cases when you need to enclose the literal in parentheses.</span></span>

- <span data-ttu-id="98e52-327">Das Literale weist keinen Dezimaltrennzeichen auf.</span><span class="sxs-lookup"><span data-stu-id="98e52-327">The literal does not have a decimal point</span></span>
- <span data-ttu-id="98e52-328">Das Literale weist keine Ziffern nach dem Dezimaltrennzeichen auf.</span><span class="sxs-lookup"><span data-stu-id="98e52-328">The literal does not have any digits following the decimal point</span></span>
- <span data-ttu-id="98e52-329">Das Literale weist kein Suffix auf.</span><span class="sxs-lookup"><span data-stu-id="98e52-329">The literal does not have a suffix</span></span>

<span data-ttu-id="98e52-330">Im folgenden Beispiel tritt beispielsweise ein Fehler auf:</span><span class="sxs-lookup"><span data-stu-id="98e52-330">For example, the following example fails:</span></span>

```
PS> 2.GetType().Name
At line:1 char:11
+ 2.GetType().Name
+           ~
An expression was expected after '('.
+ CategoryInfo          : ParserError: (:) [], ParentContainsErrorRecordException
+ FullyQualifiedErrorId : ExpectedExpression
```

<span data-ttu-id="98e52-331">Die folgenden Beispiele funktionieren:</span><span class="sxs-lookup"><span data-stu-id="98e52-331">The following examples work:</span></span>

```
PS> 2uL.GetType().Name
UInt64
PS> 1.234.GetType().Name
Double
PS> (2).GetType().Name
Int32
```

<span data-ttu-id="98e52-332">Die ersten beiden Beispiele funktionieren, ohne dass der Literalwert in Klammern eingeschlossen wird, da der PowerShell-Parser ermitteln kann, wo das numerische Literale endet und die **GetType** -Methode gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="98e52-332">The first two examples work without enclosing the literal value in parentheses because the PowerShell parser can determine where the numeric literal ends and the **GetType** method starts.</span></span>

## <a name="how-powershell-parses-numeric-literals"></a><span data-ttu-id="98e52-333">So analysiert PowerShell numerische Literale</span><span class="sxs-lookup"><span data-stu-id="98e52-333">How PowerShell parses numeric literals</span></span>

<span data-ttu-id="98e52-334">PowerShell v 7.0 änderte die Art und Weise, wie numerische Literale analysiert werden, um die neuen Funktionen zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="98e52-334">PowerShell v7.0 changed the way numeric literals are parsed to enable the new features.</span></span>

### <a name="parsing-real-numeric-literals"></a><span data-ttu-id="98e52-335">Realisieren von echten numerischen Literalen</span><span class="sxs-lookup"><span data-stu-id="98e52-335">Parsing real numeric literals</span></span>

<span data-ttu-id="98e52-336">Wenn das Literale einen Dezimaltrennzeichen oder eine e-Notation enthält, wird die Literalzeichenfolge mit einer reellen Zahl analysiert.</span><span class="sxs-lookup"><span data-stu-id="98e52-336">If the literal contains a decimal point or the e-notation, the literal string is parsed a real number.</span></span>

- <span data-ttu-id="98e52-337">, Wenn das Decimal-Suffix direkt in vorhanden ist `[decimal]` .</span><span class="sxs-lookup"><span data-stu-id="98e52-337">If the decimal-suffix is present then directly into `[decimal]`.</span></span>
- <span data-ttu-id="98e52-338">Andernfalls analysieren `[Double]` Sie As und wenden einen Multiplikator auf den Wert an.</span><span class="sxs-lookup"><span data-stu-id="98e52-338">Else, parse as `[Double]` and apply multiplier to the value.</span></span> <span data-ttu-id="98e52-339">Überprüfen Sie dann die typsuffixe, und versuchen Sie, Sie in den entsprechenden Typ umzuwandeln.</span><span class="sxs-lookup"><span data-stu-id="98e52-339">Then check the type suffixes and attempt to cast into appropriate type.</span></span>
- <span data-ttu-id="98e52-340">Wenn die Zeichenfolge kein Typsuffix aufweist, analysieren Sie als `[Double]` .</span><span class="sxs-lookup"><span data-stu-id="98e52-340">If the string has no type suffix, then parse as `[Double]`.</span></span>

### <a name="paring-integer-numeric-literals"></a><span data-ttu-id="98e52-341">Numerische ganzzahlige numerische Literale werden verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="98e52-341">Paring integer numeric literals</span></span>

<span data-ttu-id="98e52-342">Ganzzahlige typliterale werden mithilfe der folgenden Schritte analysiert:</span><span class="sxs-lookup"><span data-stu-id="98e52-342">Integer type literals are parsed using the following steps:</span></span>

1. <span data-ttu-id="98e52-343">Festlegen des Basis-Formats</span><span class="sxs-lookup"><span data-stu-id="98e52-343">Determine the radix format</span></span>
   - <span data-ttu-id="98e52-344">Analysieren Sie bei binären Formaten in `[BigInteger]` .</span><span class="sxs-lookup"><span data-stu-id="98e52-344">For binary formats, parse into `[BigInteger]`.</span></span>
   - <span data-ttu-id="98e52-345">Analysieren Sie bei hexadezimalen Formaten die `[BigInteger]` Verwendung spezieller Einschränkungen, um ursprüngliches Verhalten beizubehalten, wenn der Wert im `[int]` Bereich oder liegt `[long]` .</span><span class="sxs-lookup"><span data-stu-id="98e52-345">For hexidecimal formats, parse into `[BigInteger]` using special casies to retain original behaviours when the value is in the `[int]` or `[long]` range.</span></span>
   - <span data-ttu-id="98e52-346">Wenn weder Binary noch Hex, wird normal als ausgewertet `[BigInteger]` .</span><span class="sxs-lookup"><span data-stu-id="98e52-346">If neither binary nor hex, parse normally as a `[BigInteger]`.</span></span>
2. <span data-ttu-id="98e52-347">Wenden Sie den Multiplikatorwert an, bevor Sie Umwandlungen versuchen, um sicherzustellen, dass typbegrenzungen ohne Überlauf ordnungsgemäß geprüft werden.</span><span class="sxs-lookup"><span data-stu-id="98e52-347">Apply the multiplier value before attempting any casts to ensure type bounds can be appropriately checked without overflows.</span></span>
3. <span data-ttu-id="98e52-348">Überprüfen Sie die typsuffixe.</span><span class="sxs-lookup"><span data-stu-id="98e52-348">Check type suffixes.</span></span>
   - <span data-ttu-id="98e52-349">Überprüfen Sie die typbegrenzungen, und versuchen Sie, diesen Typ zu analysieren.</span><span class="sxs-lookup"><span data-stu-id="98e52-349">Check type bounds and attempt to parse into that type.</span></span>
   - <span data-ttu-id="98e52-350">Wenn kein Suffix verwendet wird, wird der Wert in der folgenden Reihenfolge durch Begrenzungen überprüft, was zum ersten erfolgreichen Test führt, der den Typ der Zahl bestimmt.</span><span class="sxs-lookup"><span data-stu-id="98e52-350">If no suffix is used, then the value is bounds-checked in the following order, resulting in the first successful test determining the type of the number.</span></span>
     - `[int]`
     - `[long]`
     - <span data-ttu-id="98e52-351">`[decimal]` (nur Basis-10-Literale)</span><span class="sxs-lookup"><span data-stu-id="98e52-351">`[decimal]` (base-10 literals only)</span></span>
     - <span data-ttu-id="98e52-352">`[double]` (nur Basis-10-Literale)</span><span class="sxs-lookup"><span data-stu-id="98e52-352">`[double]` (base-10 literals only)</span></span>
   - <span data-ttu-id="98e52-353">Wenn der Wert außerhalb des Bereichs für hexadezimale `[long]` und binäre Zahlen liegt, schlägt die Analyse fehl.</span><span class="sxs-lookup"><span data-stu-id="98e52-353">If the value is outside the `[long]` range for hex and binary numbers, the parse fails.</span></span>
   - <span data-ttu-id="98e52-354">Wenn der Wert außerhalb des `[double]` Bereichs für die Basis 10-Zahl liegt, schlägt die Analyse fehl.</span><span class="sxs-lookup"><span data-stu-id="98e52-354">If the value is outside the `[double]` range for base 10 number, the parse fails.</span></span>
   - <span data-ttu-id="98e52-355">Höhere Werte müssen explizit mit dem-Suffix geschrieben werden `n` , um das Literale als zu analysieren `BigInteger` .</span><span class="sxs-lookup"><span data-stu-id="98e52-355">Higher values must be explicitly written using the `n` suffix to parse the literal as a `BigInteger`.</span></span>

### <a name="parsing-large-value-literals"></a><span data-ttu-id="98e52-356">Auswerten von großen Wert literalen</span><span class="sxs-lookup"><span data-stu-id="98e52-356">Parsing large value literals</span></span>

<span data-ttu-id="98e52-357">Zuvor wurden höhere ganzzahlige Werte als Double analysiert, bevor Sie in einen anderen Typ umgewandelt werden.</span><span class="sxs-lookup"><span data-stu-id="98e52-357">Previously, higher integer values were parsed as double before being cast to any other type.</span></span> <span data-ttu-id="98e52-358">Dies führt zu einem Genauigkeits Verlust in den höheren Bereichen.</span><span class="sxs-lookup"><span data-stu-id="98e52-358">This results in a loss of precision in the higher ranges.</span></span> <span data-ttu-id="98e52-359">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="98e52-359">For example:</span></span>

```
PS> [bigint]111111111111111111111111111111111111111111111111111111
111111111111111100905595216014112456735339620444667904
```

<span data-ttu-id="98e52-360">Um dieses Problem zu vermeiden, müssen Sie Werte als Zeichen folgen schreiben und diese dann konvertieren:</span><span class="sxs-lookup"><span data-stu-id="98e52-360">To avoid this problem you had to write values as strings and then convert them:</span></span>

```
PS> [bigint]'111111111111111111111111111111111111111111111111111111'
111111111111111111111111111111111111111111111111111111
```

<span data-ttu-id="98e52-361">In PowerShell 7,0 müssen Sie das- `N` Suffix verwenden.</span><span class="sxs-lookup"><span data-stu-id="98e52-361">In PowerShell 7.0 you must use the `N` suffix.</span></span>

```
PS> 111111111111111111111111111111111111111111111111111111n
111111111111111111111111111111111111111111111111111111
```

<span data-ttu-id="98e52-362">Außerdem sollten Werte zwischen `[ulong]::MaxValue` und `[decimal]::MaxValue` mit dem Decimal-Suffix angegeben werden `D` , um die Genauigkeit beizubehalten.</span><span class="sxs-lookup"><span data-stu-id="98e52-362">Also values between `[ulong]::MaxValue` and `[decimal]::MaxValue` should be denoted using the decimal-suffix `D` to maintain accuracy.</span></span> <span data-ttu-id="98e52-363">Ohne das-Suffix werden diese Werte `[Double]` mit dem echt Analysemodus analysiert.</span><span class="sxs-lookup"><span data-stu-id="98e52-363">Without the suffix, these values are parsed as `[Double]` using the real-parsing mode.</span></span>

<!-- reference links -->
[bigint]: /dotnet/api/system.numerics.biginteger