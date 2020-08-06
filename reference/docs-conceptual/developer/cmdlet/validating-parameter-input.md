---
title: Validieren von Parameter Eingaben | Microsoft-Dokumentation
ms.date: 09/13/2016
helpviewer_keywords:
- parameters, validation rules
- validation, examples
- validation
ms.openlocfilehash: e12c715cfa24edfff958b12be1f3517b2f545256
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87783992"
---
# <a name="validating-parameter-input"></a><span data-ttu-id="d4346-102">Überprüfen von Parametereingaben</span><span class="sxs-lookup"><span data-stu-id="d4346-102">Validating Parameter Input</span></span>

<span data-ttu-id="d4346-103">PowerShell kann die Argumente, die an Cmdlet-Parameter übergeben werden, auf verschiedene Weise überprüfen.</span><span class="sxs-lookup"><span data-stu-id="d4346-103">PowerShell can validate the arguments passed to cmdlet parameters in several ways.</span></span>
<span data-ttu-id="d4346-104">PowerShell kann die Länge, den Bereich und das Muster der Zeichen des Arguments überprüfen.</span><span class="sxs-lookup"><span data-stu-id="d4346-104">PowerShell can validate the length, the range, and the pattern of the characters of the argument.</span></span>
<span data-ttu-id="d4346-105">Sie kann die Anzahl der verfügbaren Argumente (die Anzahl) überprüfen.</span><span class="sxs-lookup"><span data-stu-id="d4346-105">It can validate the number of arguments available (the count).</span></span>
<span data-ttu-id="d4346-106">Diese Validierungsregeln werden durch Validierungs Attribute definiert, die mit dem Parameter-Attribut in öffentlichen Eigenschaften der Cmdlet-Klasse deklariert werden.</span><span class="sxs-lookup"><span data-stu-id="d4346-106">These validation rules are defined by validation attributes that are declared with the Parameter attribute on public properties of the cmdlet class.</span></span>

<span data-ttu-id="d4346-107">Zum Validieren eines Parameter Arguments verwendet die PowerShell-Laufzeit die Informationen, die von den Validierungs Attributen bereitgestellt werden, um den Wert des-Parameters vor dem Ausführen des Cmdlets zu bestätigen.</span><span class="sxs-lookup"><span data-stu-id="d4346-107">To validate a parameter argument, the PowerShell runtime uses the information provided by the validation attributes to confirm the value of the parameter before the cmdlet is run.</span></span>
<span data-ttu-id="d4346-108">Wenn die Parameter Eingabe nicht gültig ist, erhält der Benutzer eine Fehlermeldung.</span><span class="sxs-lookup"><span data-stu-id="d4346-108">If the parameter input is not valid, the user receives an error message.</span></span>
<span data-ttu-id="d4346-109">Jeder Validierungs Parameter definiert eine Validierungs Regel, die von PowerShell erzwungen wird.</span><span class="sxs-lookup"><span data-stu-id="d4346-109">Each validation parameter defines a validation rule that is enforced by PowerShell.</span></span>

<span data-ttu-id="d4346-110">PowerShell erzwingt die Validierungsregeln basierend auf den folgenden Attributen.</span><span class="sxs-lookup"><span data-stu-id="d4346-110">PowerShell enforces the validation rules based on the following attributes.</span></span>

### <a name="validatecount"></a><span data-ttu-id="d4346-111">Validatecount</span><span class="sxs-lookup"><span data-stu-id="d4346-111">ValidateCount</span></span>

<span data-ttu-id="d4346-112">Gibt die minimale und maximale Anzahl von Argumenten an, die ein Parameter annehmen kann.</span><span class="sxs-lookup"><span data-stu-id="d4346-112">Specifies the minimum and maximum number of arguments that a parameter can accept.</span></span>
<span data-ttu-id="d4346-113">Weitere Informationen finden Sie unter [validatecount-Attribut Deklaration](./validatecount-attribute-declaration.md).</span><span class="sxs-lookup"><span data-stu-id="d4346-113">For more information, see [ValidateCount Attribute Declaration](./validatecount-attribute-declaration.md).</span></span>

### <a name="validatelength"></a><span data-ttu-id="d4346-114">ValidateLength</span><span class="sxs-lookup"><span data-stu-id="d4346-114">ValidateLength</span></span>

<span data-ttu-id="d4346-115">Gibt die minimale und maximale Anzahl von Zeichen im Parameter Argument an.</span><span class="sxs-lookup"><span data-stu-id="d4346-115">Specifies the minimum and maximum number of characters in the parameter argument.</span></span>
<span data-ttu-id="d4346-116">Weitere Informationen finden Sie unter [validateLength-Attribut Deklaration](./validatelength-attribute-declaration.md).</span><span class="sxs-lookup"><span data-stu-id="d4346-116">For more information, see [ValidateLength Attribute Declaration](./validatelength-attribute-declaration.md).</span></span>

### <a name="validatepattern"></a><span data-ttu-id="d4346-117">ValidatePattern</span><span class="sxs-lookup"><span data-stu-id="d4346-117">ValidatePattern</span></span>

<span data-ttu-id="d4346-118">Gibt einen regulären Ausdruck an, der das Parameter Argument überprüft.</span><span class="sxs-lookup"><span data-stu-id="d4346-118">Specifies a regular expression that validates the parameter argument.</span></span>
<span data-ttu-id="d4346-119">Weitere Informationen finden Sie unter [validatepattern-Attribut Deklaration](./validatepattern-attribute-declaration.md).</span><span class="sxs-lookup"><span data-stu-id="d4346-119">For more information, see [ValidatePattern Attribute Declaration](./validatepattern-attribute-declaration.md).</span></span>

### <a name="validaterange"></a><span data-ttu-id="d4346-120">Validaterange</span><span class="sxs-lookup"><span data-stu-id="d4346-120">ValidateRange</span></span>

<span data-ttu-id="d4346-121">Gibt den minimalen und maximalen Wert des Parameter Arguments an.</span><span class="sxs-lookup"><span data-stu-id="d4346-121">Specifies the minimum and maximum values of the parameter argument.</span></span>
<span data-ttu-id="d4346-122">Weitere Informationen finden Sie unter [validaterange-Attribut Deklaration](./validaterange-attribute-declaration.md).</span><span class="sxs-lookup"><span data-stu-id="d4346-122">For more information, see [ValidateRange Attribute Declaration](./validaterange-attribute-declaration.md).</span></span>

### <a name="validateset"></a><span data-ttu-id="d4346-123">ValidateSet</span><span class="sxs-lookup"><span data-stu-id="d4346-123">ValidateSet</span></span>

<span data-ttu-id="d4346-124">Gibt die gültigen Werte für das Parameter Argument an.</span><span class="sxs-lookup"><span data-stu-id="d4346-124">Specifies the valid values for the parameter argument.</span></span>
<span data-ttu-id="d4346-125">Weitere Informationen finden Sie unter [validateset-Attribut Deklaration](./validateset-attribute-declaration.md).</span><span class="sxs-lookup"><span data-stu-id="d4346-125">For more information, see [ValidateSet Attribute Declaration](./validateset-attribute-declaration.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="d4346-126">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d4346-126">See Also</span></span>

[<span data-ttu-id="d4346-127">Überprüfen einer Parametereingabe</span><span class="sxs-lookup"><span data-stu-id="d4346-127">How to Validate Parameter Input</span></span>](./how-to-validate-parameter-input.md)

[<span data-ttu-id="d4346-128">Schreiben eines Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="d4346-128">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
