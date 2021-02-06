---
description: Beschreibt das Arbeiten mit Befehlsparametern in PowerShell.
Locale: en-US
ms.date: 02/12/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_parameters?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Parameters
ms.openlocfilehash: c9d7ab62c13a7cafcf93103f9a70f6575d5dd7b8
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99602966"
---
# <a name="about-parameters"></a><span data-ttu-id="c53dc-103">Informationen zu Parametern</span><span class="sxs-lookup"><span data-stu-id="c53dc-103">About Parameters</span></span>

## <a name="short-description"></a><span data-ttu-id="c53dc-104">Kurze Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c53dc-104">Short description</span></span>
<span data-ttu-id="c53dc-105">Beschreibt das Arbeiten mit Befehlsparametern in PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c53dc-105">Describes how to work with command parameters in PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="c53dc-106">Lange Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c53dc-106">Long description</span></span>

<span data-ttu-id="c53dc-107">Die meisten PowerShell-Befehle, z. b. Cmdlets, Funktionen und Skripts, basieren auf Parametern, damit Benutzeroptionen auswählen oder Eingaben bereitstellen können.</span><span class="sxs-lookup"><span data-stu-id="c53dc-107">Most PowerShell commands, such as cmdlets, functions, and scripts, rely on parameters to allow users to select options or provide input.</span></span> <span data-ttu-id="c53dc-108">Die Parameter folgen dem Befehlsnamen und weisen die folgende Form auf:</span><span class="sxs-lookup"><span data-stu-id="c53dc-108">The parameters follow the command name and have the following form:</span></span>

```
-<parameter_name> <parameter_value>
-<parameter_name>:<parameter_value>
```

<span data-ttu-id="c53dc-109">Dem Namen des Parameters wird ein Bindestrich (-) vorangestellt, der PowerShell signalisiert, dass das Wort nach dem Bindestrich ein Parameter Name ist.</span><span class="sxs-lookup"><span data-stu-id="c53dc-109">The name of the parameter is preceded by a hyphen (-), which signals to PowerShell that the word following the hyphen is a parameter name.</span></span> <span data-ttu-id="c53dc-110">Der Parameter Name und der Wert können durch ein Leerzeichen oder einen Doppelpunkt getrennt werden.</span><span class="sxs-lookup"><span data-stu-id="c53dc-110">The parameter name and value can be separated by a space or a colon character.</span></span> <span data-ttu-id="c53dc-111">Einige Parameter erfordern keinen Parameterwert oder akzeptieren ihn nicht.</span><span class="sxs-lookup"><span data-stu-id="c53dc-111">Some parameters do not require or accept a parameter value.</span></span> <span data-ttu-id="c53dc-112">Für andere Parameter ist ein Wert erforderlich, aber der Parameter Name ist im Befehl nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="c53dc-112">Other parameters require a value, but do not require the parameter name in the command.</span></span>

<span data-ttu-id="c53dc-113">Der Parametertyp und die Anforderungen für diese Parameter variieren.</span><span class="sxs-lookup"><span data-stu-id="c53dc-113">The type of parameters and the requirements for those parameters vary.</span></span> <span data-ttu-id="c53dc-114">Um Informationen zu den Parametern eines Befehls zu finden, verwenden Sie das- `Get-Help` Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="c53dc-114">To find information about the parameters of a command, use the `Get-Help` cmdlet.</span></span> <span data-ttu-id="c53dc-115">Wenn Sie z. b. Informationen zu den Parametern des `Get-ChildItem` Cmdlets suchen möchten, geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="c53dc-115">For example, to find information about the parameters of the `Get-ChildItem` cmdlet, type:</span></span>

```powershell
Get-Help Get-ChildItem
```

<span data-ttu-id="c53dc-116">Wenn Sie Informationen zu den Parametern eines Skripts suchen möchten, verwenden Sie den vollständigen Pfad zur Skriptdatei.</span><span class="sxs-lookup"><span data-stu-id="c53dc-116">To find information about the parameters of a script, use the full path to the script file.</span></span> <span data-ttu-id="c53dc-117">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="c53dc-117">For example:</span></span>

```powershell
Get-Help $home\Documents\Scripts\Get-Function.ps1
```

<span data-ttu-id="c53dc-118">`Get-Help`Mit dem-Cmdlet werden verschiedene Details zum Befehl zurückgegeben, einschließlich einer Beschreibung, der Befehlssyntax, Informationen zu den Parametern und Beispielen, die zeigen, wie die Parameter in einem Befehl verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="c53dc-118">The `Get-Help` cmdlet returns various details about the command, including a description, the command syntax, information about the parameters, and examples showing how to use the parameters in a command.</span></span>

<span data-ttu-id="c53dc-119">Sie können auch den Parameter Parameter des `Get-Help` Cmdlets verwenden, um Informationen zu einem bestimmten Parameter zu suchen.</span><span class="sxs-lookup"><span data-stu-id="c53dc-119">You can also use the Parameter parameter of the `Get-Help` cmdlet to find information about a particular parameter.</span></span> <span data-ttu-id="c53dc-120">Oder Sie können den **Parameter** Parameter mit dem Platzhalter Zeichen ( `*` ) verwenden, um Informationen zu allen Parametern des Befehls zu suchen.</span><span class="sxs-lookup"><span data-stu-id="c53dc-120">Or, you can use the **Parameter** parameter with the wildcard character ( `*` ) value to find information about all parameters of the command.</span></span> <span data-ttu-id="c53dc-121">Beispielsweise werden mit dem folgenden Befehl Informationen zu allen Parametern des `Get-Member` Cmdlets abgerufen:</span><span class="sxs-lookup"><span data-stu-id="c53dc-121">For example, the following command gets information about all parameters of the `Get-Member` cmdlet:</span></span>

```powershell
Get-Help Get-Member -Parameter *
```

### <a name="default-parameter-values"></a><span data-ttu-id="c53dc-122">Standardwerte für Parameter</span><span class="sxs-lookup"><span data-stu-id="c53dc-122">Default parameter values</span></span>

<span data-ttu-id="c53dc-123">Optionale Parameter verfügen über einen Standardwert. Dies ist der Wert, der verwendet wird, oder angenommen, wenn der-Parameter nicht im Befehl angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="c53dc-123">Optional parameters have a default value, which is the value that is used or assumed when the parameter is not specified in the command.</span></span>

<span data-ttu-id="c53dc-124">Der Standardwert des **Computername** -Parameters von vielen Cmdlets ist beispielsweise der Name des lokalen Computers.</span><span class="sxs-lookup"><span data-stu-id="c53dc-124">For example, the default value of the **ComputerName** parameter of many cmdlets is the name of the local computer.</span></span> <span data-ttu-id="c53dc-125">Daher wird der Name des lokalen Computers im Befehl verwendet, es sei denn, der **Computername** -Parameter ist angegeben.</span><span class="sxs-lookup"><span data-stu-id="c53dc-125">As a result, the local computer name is used in the command unless the **ComputerName** parameter is specified.</span></span>

<span data-ttu-id="c53dc-126">Die Standardparameter Werte finden Sie im Hilfethema für das Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="c53dc-126">To find the default parameter value, see help topic for the cmdlet.</span></span> <span data-ttu-id="c53dc-127">Die Beschreibung des Parameters sollte den Standardwert enthalten.</span><span class="sxs-lookup"><span data-stu-id="c53dc-127">The parameter description should include the default value.</span></span>

<span data-ttu-id="c53dc-128">Sie können auch einen benutzerdefinierten Standardwert für jeden Parameter eines Cmdlets oder einer erweiterten Funktion festlegen.</span><span class="sxs-lookup"><span data-stu-id="c53dc-128">You can also set a custom default value for any parameter of a cmdlet or advanced function.</span></span> <span data-ttu-id="c53dc-129">Weitere Informationen zum Festlegen von benutzerdefinierten Standardwerten finden Sie unter [about_Parameters_Default_Values](about_Parameters_Default_Values.md).</span><span class="sxs-lookup"><span data-stu-id="c53dc-129">For information about setting custom default values, see [about_Parameters_Default_Values](about_Parameters_Default_Values.md).</span></span>

### <a name="parameter-attribute-table"></a><span data-ttu-id="c53dc-130">Parameter Attribut Tabelle</span><span class="sxs-lookup"><span data-stu-id="c53dc-130">Parameter attribute table</span></span>

<span data-ttu-id="c53dc-131">Wenn Sie den **Full**-, **Parameter**-oder **Online-** Parameter des `Get-Help` Cmdlets verwenden, wird `Get-Help` eine Parameter Attribut Tabelle mit detaillierten Informationen zum Parameter angezeigt.</span><span class="sxs-lookup"><span data-stu-id="c53dc-131">When you use the **Full**, **Parameter**, or **Online** parameters of the `Get-Help` cmdlet, `Get-Help` displays a parameter attribute table with detailed information about the parameter.</span></span>

<span data-ttu-id="c53dc-132">Diese Informationen umfassen die Details, die Sie kennen müssen, um den-Parameter zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="c53dc-132">This information includes the details you need to know to use the parameter.</span></span>
<span data-ttu-id="c53dc-133">Das Hilfethema für das `Get-ChildItem` Cmdlet enthält z. b. die folgenden Details zum Pfad Parameter:</span><span class="sxs-lookup"><span data-stu-id="c53dc-133">For example, the help topic for the `Get-ChildItem` cmdlet includes the following details about its Path parameter:</span></span>

```
-path <string[]>
    Specifies a path of one or more locations. Wildcard characters are
    permitted. The default location is the current directory (.).

Required?                    false
Position?                    0
Default value                Current directory
Accept pipeline input?       true (ByValue, ByPropertyName)
Accept wildcard characters?  true
```

<span data-ttu-id="c53dc-134">Zu den Parameterinformationen gehören die Parameter Syntax, eine Beschreibung des Parameters und die Parameter Attribute.</span><span class="sxs-lookup"><span data-stu-id="c53dc-134">The parameter information includes the parameter syntax, a description of the parameter, and the parameter attributes.</span></span> <span data-ttu-id="c53dc-135">In den folgenden Abschnitten werden die Parameter Attribute beschrieben.</span><span class="sxs-lookup"><span data-stu-id="c53dc-135">The following sections describe the parameter attributes.</span></span>

#### <a name="parameter-required"></a><span data-ttu-id="c53dc-136">Parameter erforderlich</span><span class="sxs-lookup"><span data-stu-id="c53dc-136">Parameter Required</span></span>

<span data-ttu-id="c53dc-137">Diese Einstellung gibt an, ob der Parameter obligatorisch ist, d. h. ob alle Befehle, die dieses Cmdlet verwenden, diesen Parameter enthalten müssen.</span><span class="sxs-lookup"><span data-stu-id="c53dc-137">This setting indicates whether the parameter is mandatory, that is, whether all commands that use this cmdlet must include this parameter.</span></span> <span data-ttu-id="c53dc-138">Wenn der Wert **true** lautet und der-Parameter im Befehl fehlt, werden Sie von PowerShell aufgefordert, einen Wert für den-Parameter einzugeben.</span><span class="sxs-lookup"><span data-stu-id="c53dc-138">When the value is **True** and the parameter is missing from the command, PowerShell prompts you for a value for the parameter.</span></span>

#### <a name="parameter-position"></a><span data-ttu-id="c53dc-139">Parameter Position</span><span class="sxs-lookup"><span data-stu-id="c53dc-139">Parameter Position</span></span>

<span data-ttu-id="c53dc-140">Wenn die `Position` Einstellung auf eine positive ganze Zahl festgelegt ist, ist der Parameter Name nicht erforderlich.</span><span class="sxs-lookup"><span data-stu-id="c53dc-140">If the `Position` setting is set to a positive integer, the parameter name is not required.</span></span> <span data-ttu-id="c53dc-141">Dieser Parametertyp wird als Positions Parameter bezeichnet, und die Zahl gibt die Position an, an der der Parameter in Relation zu anderen Positions Parametern angezeigt werden muss.</span><span class="sxs-lookup"><span data-stu-id="c53dc-141">This type of parameter is referred to as a positional parameter, and the number indicates the position in which the parameter must appear in relation to other positional parameters.</span></span> <span data-ttu-id="c53dc-142">Ein benannter Parameter kann an einer beliebigen Position nach dem Namen des Cmdlets aufgelistet werden.</span><span class="sxs-lookup"><span data-stu-id="c53dc-142">A named parameter can be listed in any position after the cmdlet name.</span></span> <span data-ttu-id="c53dc-143">Wenn Sie den Parameternamen für einen positionellen Parameter einschließen, kann der Parameter an einer beliebigen Position nach dem Cmdlet-Namen aufgelistet werden.</span><span class="sxs-lookup"><span data-stu-id="c53dc-143">If you include the parameter name for a positional parameter, the parameter can be listed in any position after the cmdlet name.</span></span>

<span data-ttu-id="c53dc-144">Das `Get-ChildItem` Cmdlet hat z. b. Pfad-und Ausschluss Parameter.</span><span class="sxs-lookup"><span data-stu-id="c53dc-144">For example, the `Get-ChildItem` cmdlet has Path and Exclude parameters.</span></span> <span data-ttu-id="c53dc-145">Die `Position` Einstellung für **path** ist **0**, was bedeutet, dass es sich um einen Positions Parameter handelt.</span><span class="sxs-lookup"><span data-stu-id="c53dc-145">The `Position` setting for **Path** is **0**, which means that it is a positional parameter.</span></span> <span data-ttu-id="c53dc-146">Die `Position` Einstellung für **Exclude** hat den **Namen**.</span><span class="sxs-lookup"><span data-stu-id="c53dc-146">The `Position` setting for **Exclude** is **named**.</span></span>

<span data-ttu-id="c53dc-147">Dies bedeutet, dass für **path** nicht der Parameter Name erforderlich ist, aber der Parameterwert muss der erste oder einzige unbenannte Parameterwert im Befehl sein.</span><span class="sxs-lookup"><span data-stu-id="c53dc-147">This means that **Path** does not require the parameter name, but its parameter value must be the first or only unnamed parameter value in the command.</span></span>
<span data-ttu-id="c53dc-148">Da der Exclude-Parameter jedoch ein benannter Parameter ist, können Sie ihn an einer beliebigen Position im Befehl platzieren.</span><span class="sxs-lookup"><span data-stu-id="c53dc-148">However, because the Exclude parameter is a named parameter, you can place it in any position in the command.</span></span>

<span data-ttu-id="c53dc-149">Aufgrund der `Position` Einstellungen für diese beiden Parameter können Sie einen der folgenden Befehle verwenden:</span><span class="sxs-lookup"><span data-stu-id="c53dc-149">As a result of the `Position` settings for these two parameters, you can use any of the following commands:</span></span>

```powershell
Get-ChildItem -Path c:\techdocs -Exclude *.ppt
Get-ChildItem c:\techdocs -Exclude *.ppt
Get-ChildItem -Exclude *.ppt -Path c:\techdocs
Get-ChildItem -Exclude *.ppt c:\techdocs
```

<span data-ttu-id="c53dc-150">Wenn Sie einen anderen Positions Parameter einschließen möchten, ohne den Parameternamen einzuschließen, muss dieser Parameter in der von der-Einstellung angegebenen Reihenfolge platziert werden `Position` .</span><span class="sxs-lookup"><span data-stu-id="c53dc-150">If you were to include another positional parameter without including the parameter name, that parameter must be placed in the order specified by the `Position` setting.</span></span>

#### <a name="parameter-type"></a><span data-ttu-id="c53dc-151">Parametertyp</span><span class="sxs-lookup"><span data-stu-id="c53dc-151">Parameter Type</span></span>

<span data-ttu-id="c53dc-152">Diese Einstellung gibt den Microsoft .net Frameworktyp des Parameter Werts an.</span><span class="sxs-lookup"><span data-stu-id="c53dc-152">This setting specifies the Microsoft .NET Framework type of the parameter value.</span></span> <span data-ttu-id="c53dc-153">Wenn der Typ z. b. **Int32** ist, muss der Parameterwert eine ganze Zahl sein.</span><span class="sxs-lookup"><span data-stu-id="c53dc-153">For example, if the type is **Int32**, the parameter value must be an integer.</span></span> <span data-ttu-id="c53dc-154">Wenn der Typ "String" ist, muss der Parameterwert eine Zeichenfolge sein.</span><span class="sxs-lookup"><span data-stu-id="c53dc-154">If the type is string, the parameter value must be a character string.</span></span> <span data-ttu-id="c53dc-155">Wenn die Zeichenfolge Leerzeichen enthält, muss der Wert in Anführungszeichen eingeschlossen werden, oder dem Escapezeichen muss das Escapezeichen (') vorangestellt werden.</span><span class="sxs-lookup"><span data-stu-id="c53dc-155">If the string contains spaces, the value must be enclosed in quotation marks, or the spaces must be preceded by the escape character ( \` ).</span></span>

#### <a name="default-value"></a><span data-ttu-id="c53dc-156">Standardwert</span><span class="sxs-lookup"><span data-stu-id="c53dc-156">Default Value</span></span>

<span data-ttu-id="c53dc-157">Diese Einstellung gibt den Wert an, den der Parameter annimmt, wenn kein anderer Wert angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="c53dc-157">This setting specifies the value that the parameter will assume if no other value is provided.</span></span> <span data-ttu-id="c53dc-158">Beispielsweise ist der Standardwert des path-Parameters oft das aktuelle Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="c53dc-158">For example, the default value of the Path parameter is often the current directory.</span></span> <span data-ttu-id="c53dc-159">Erforderliche Parameter haben niemals einen Standardwert.</span><span class="sxs-lookup"><span data-stu-id="c53dc-159">Required parameters never have a default value.</span></span>
<span data-ttu-id="c53dc-160">Bei vielen optionalen Parametern gibt es keinen Standardwert, da der-Parameter keine Auswirkung hat, wenn er nicht verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="c53dc-160">For many optional parameters, there is no default because the parameter has no effect if it is not used.</span></span>

#### <a name="accepts-multiple-values"></a><span data-ttu-id="c53dc-161">Akzeptiert mehrere Werte</span><span class="sxs-lookup"><span data-stu-id="c53dc-161">Accepts Multiple Values</span></span>

<span data-ttu-id="c53dc-162">Diese Einstellung gibt an, ob ein Parameter mehrere Parameterwerte akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="c53dc-162">This setting indicates whether a parameter accepts multiple parameter values.</span></span>
<span data-ttu-id="c53dc-163">Wenn ein Parameter mehrere Werte akzeptiert, können Sie eine durch Trennzeichen getrennte Liste als Wert des Parameters im Befehl eingeben oder eine durch Trennzeichen getrennte Liste (ein Array) in einer Variablen speichern und die Variable dann als Parameterwert angeben.</span><span class="sxs-lookup"><span data-stu-id="c53dc-163">When a parameter accepts multiple values, you can type a comma-separated list as the value of the parameter in the command, or save a comma-separated list (an array) in a variable, and then specify the variable as the parameter value.</span></span>

<span data-ttu-id="c53dc-164">Der Service Name-Parameter des `Get-Service` Cmdlets nimmt z. b. mehrere Werte an.</span><span class="sxs-lookup"><span data-stu-id="c53dc-164">For example, the ServiceName parameter of the `Get-Service` cmdlet accepts multiple values.</span></span> <span data-ttu-id="c53dc-165">Die folgenden Befehle sind beide gültig:</span><span class="sxs-lookup"><span data-stu-id="c53dc-165">The following commands are both valid:</span></span>

```powershell
Get-Service -servicename winrm, netlogon
```

```powershell
$s = "winrm", "netlogon"
Get-Service -servicename $s
```

#### <a name="accepts-pipeline-input"></a><span data-ttu-id="c53dc-166">Akzeptiert Pipeline Eingaben</span><span class="sxs-lookup"><span data-stu-id="c53dc-166">Accepts Pipeline Input</span></span>

<span data-ttu-id="c53dc-167">Diese Einstellung gibt an, ob Sie den Pipeline Operator ( `|` ) verwenden können, um einen Wert an den Parameter zu senden.</span><span class="sxs-lookup"><span data-stu-id="c53dc-167">This setting indicates whether you can use the pipeline operator ( `|` ) to send a value to the parameter.</span></span>

```
Value                    Description
-----                    -----------
False                    Indicates that you cannot pipe a value to the
                         parameter.

True (by Value)          Indicates that you can pipe any value to the
                         parameter, just so the value has the .NET
                         Framework type specified for the parameter or the
                         value can be converted to the specified .NET
                         Framework type.
```

<span data-ttu-id="c53dc-168">Wenn ein Parameter "true (nach Wert)" ist, versucht PowerShell, alle weitergeleiteten Werte mit diesem Parameter zu verknüpfen, bevor versucht wird, den Befehl mit anderen Methoden zu interpretieren.</span><span class="sxs-lookup"><span data-stu-id="c53dc-168">When a parameter is "True (by Value)", PowerShell tries to associate any piped values with that parameter before it tries other methods to interpret the command.</span></span>

```
True (by Property Name)  Indicates that you can pipe a value to the
                         parameter, but the .NET Framework type of the
                         parameter must include a property with the same
                         name as the parameter.
```

<span data-ttu-id="c53dc-169">Beispielsweise können Sie einen Wert nur an einen **Name** -Parameter übergeben, wenn der Wert eine Eigenschaft namens **Name** aufweist.</span><span class="sxs-lookup"><span data-stu-id="c53dc-169">For example, you can pipe a value to a **Name** parameter only when the value has a property called **Name**.</span></span>

> [!NOTE]
> <span data-ttu-id="c53dc-170">Ein typisierter Parameter, der Pipeline Eingaben ( `by Value` ) oder () akzeptiert, `by PropertyName` ermöglicht die Verwendung von **verzögerten Bindungs** Skript Blöcken für den Parameter.</span><span class="sxs-lookup"><span data-stu-id="c53dc-170">A typed parameter that accepts pipeline input (`by Value`) or (`by PropertyName`) enables use of **delay-bind** script blocks on the parameter.</span></span>
>
> <span data-ttu-id="c53dc-171">Der **Verzögerungs Bindungs** Skriptblock wird automatisch während der **ParameterBinding** ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="c53dc-171">The **delay-bind** script block is run automatically during **ParameterBinding**.</span></span> <span data-ttu-id="c53dc-172">Das Ergebnis wird an den-Parameter gebunden.</span><span class="sxs-lookup"><span data-stu-id="c53dc-172">The result is bound to the parameter.</span></span> <span data-ttu-id="c53dc-173">Die verzögerte Bindung funktioniert **nicht** für Parameter `ScriptBlock` , die als Typ oder definiert `System.Object` sind, und der Skriptblock wird durchlaufen, **ohne** aufgerufen zu werden.</span><span class="sxs-lookup"><span data-stu-id="c53dc-173">Delay binding does **not** work for parameters defined as type `ScriptBlock` or `System.Object`, the script block is passed through **without** being invoked.</span></span>
>
> <span data-ttu-id="c53dc-174">Informationen zu **verzögerten Bindungs** Skript Blöcken finden Sie hier [about_Script_Blocks. MD](about_Script_Blocks.md)</span><span class="sxs-lookup"><span data-stu-id="c53dc-174">You can read about **delay-bind** script blocks here [about_Script_Blocks.md](about_Script_Blocks.md)</span></span>

#### <a name="accepts-wildcard-characters"></a><span data-ttu-id="c53dc-175">Akzeptiert Platzhalter Zeichen</span><span class="sxs-lookup"><span data-stu-id="c53dc-175">Accepts Wildcard Characters</span></span>

<span data-ttu-id="c53dc-176">Diese Einstellung gibt an, ob der Wert des Parameters Platzhalter Zeichen enthalten kann, sodass der Parameterwert mit mehr als einem vorhandenen Element im Zielcontainer abgeglichen werden kann.</span><span class="sxs-lookup"><span data-stu-id="c53dc-176">This setting indicates whether the parameter's value can contain wildcard characters so that the parameter value can be matched to more than one existing item in the target container.</span></span>

#### <a name="common-parameters"></a><span data-ttu-id="c53dc-177">Allgemeine Parameter</span><span class="sxs-lookup"><span data-stu-id="c53dc-177">Common Parameters</span></span>

<span data-ttu-id="c53dc-178">Allgemeine Parameter sind Parameter, die Sie mit jedem Cmdlet verwenden können.</span><span class="sxs-lookup"><span data-stu-id="c53dc-178">Common parameters are parameters that you can use with any cmdlet.</span></span> <span data-ttu-id="c53dc-179">Weitere Informationen zu allgemeinen Parametern finden Sie unter [about_CommonParameters](about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="c53dc-179">For more information about common parameters, see [about_CommonParameters](about_CommonParameters.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="c53dc-180">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="c53dc-180">See also</span></span>

[<span data-ttu-id="c53dc-181">about_Command_syntax</span><span class="sxs-lookup"><span data-stu-id="c53dc-181">about_Command_syntax</span></span>](about_Command_syntax.md)

[<span data-ttu-id="c53dc-182">about_Comment_Based_Help</span><span class="sxs-lookup"><span data-stu-id="c53dc-182">about_Comment_Based_Help</span></span>](about_Comment_Based_Help.md)

[<span data-ttu-id="c53dc-183">about_Functions_Advanced</span><span class="sxs-lookup"><span data-stu-id="c53dc-183">about_Functions_Advanced</span></span>](about_Functions_Advanced.md)

[<span data-ttu-id="c53dc-184">about_Parameters_Default_Values</span><span class="sxs-lookup"><span data-stu-id="c53dc-184">about_Parameters_Default_Values</span></span>](about_Parameters_Default_Values.md)

[<span data-ttu-id="c53dc-185">about_Pipelines</span><span class="sxs-lookup"><span data-stu-id="c53dc-185">about_Pipelines</span></span>](about_Pipelines.md)

[<span data-ttu-id="c53dc-186">about_Wildcards</span><span class="sxs-lookup"><span data-stu-id="c53dc-186">about_Wildcards</span></span>](about_Wildcards.md)
