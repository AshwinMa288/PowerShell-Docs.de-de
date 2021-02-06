---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 08/10/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/format-wide?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Format-Wide
ms.openlocfilehash: ba61c2d24d85256c55a7409fc368de4407aad5a9
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99596145"
---
# <span data-ttu-id="b5571-102">Format-Wide</span><span class="sxs-lookup"><span data-stu-id="b5571-102">Format-Wide</span></span>

## <span data-ttu-id="b5571-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="b5571-103">SYNOPSIS</span></span>
<span data-ttu-id="b5571-104">Formatiert Objekte als eine große Tabelle, in der nur eine Eigenschaft pro Objekt angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="b5571-104">Formats objects as a wide table that displays only one property of each object.</span></span>

## <span data-ttu-id="b5571-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="b5571-105">SYNTAX</span></span>

```
Format-Wide [[-Property] <Object>] [-AutoSize] [-Column <int>] [-GroupBy <Object>] [-View <string>]
  [-ShowError] [-DisplayError] [-Force] [-Expand <string>] [-InputObject <psobject>]
  [<CommonParameters>]
```

## <span data-ttu-id="b5571-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="b5571-106">DESCRIPTION</span></span>

<span data-ttu-id="b5571-107">Das- `Format-Wide` Cmdlet formatiert Objekte als eine breite Tabelle, in der nur eine Eigenschaft jedes Objekts angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="b5571-107">The `Format-Wide` cmdlet formats objects as a wide table that displays only one property of each object.</span></span> <span data-ttu-id="b5571-108">Sie können den **Property** -Parameter verwenden, um zu bestimmen, welche Eigenschaft angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="b5571-108">You can use the **Property** parameter to determine which property is displayed.</span></span>

## <span data-ttu-id="b5571-109">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="b5571-109">EXAMPLES</span></span>

### <span data-ttu-id="b5571-110">Beispiel 1: Formatieren von Namen von Dateien im aktuellen Verzeichnis</span><span class="sxs-lookup"><span data-stu-id="b5571-110">Example 1: Format names of files in the current directory</span></span>

<span data-ttu-id="b5571-111">Dieser Befehl zeigt die Namen der Dateien im aktuellen Verzeichnis in drei Spalten auf dem Bildschirm an.</span><span class="sxs-lookup"><span data-stu-id="b5571-111">This command displays the names of files in the current directory in three columns across the screen.</span></span>

```powershell
Get-ChildItem | Format-Wide -Column 3
```

<span data-ttu-id="b5571-112">Das Cmdlet „Get-ChildItem“ ruft die Objekte ab, die jede Datei im Verzeichnis darstellen.</span><span class="sxs-lookup"><span data-stu-id="b5571-112">The Get-ChildItem cmdlet gets objects representing each file in the directory.</span></span> <span data-ttu-id="b5571-113">Der Pipeline Operator (|) übergibt die Datei Objekte über die Pipeline an `Format-Wide` , wodurch Sie für die Ausgabe formatiert werden.</span><span class="sxs-lookup"><span data-stu-id="b5571-113">The pipeline operator (|) passes the file objects through the pipeline to `Format-Wide`, which formats them for output.</span></span> <span data-ttu-id="b5571-114">Der **Column** -Parameter gibt die Anzahl der Spalten an.</span><span class="sxs-lookup"><span data-stu-id="b5571-114">The **Column** parameter specifies the number of columns.</span></span>

### <span data-ttu-id="b5571-115">Beispiel 2: Formatieren von Namen von Registrierungs Schlüsseln</span><span class="sxs-lookup"><span data-stu-id="b5571-115">Example 2: Format names of registry keys</span></span>

<span data-ttu-id="b5571-116">Dieser Befehl zeigt die Namen der Registrierungsschlüssel im Schlüssel „HKEY_CURRENT_USER\Software\Microsoft“ an.</span><span class="sxs-lookup"><span data-stu-id="b5571-116">This command displays the names of registry keys in the HKEY_CURRENT_USER\Software\Microsoft key.</span></span>

```powershell
Get-ChildItem HKCU:\software\microsoft | Format-Wide -Property pschildname -AutoSize
```

<span data-ttu-id="b5571-117">Das Cmdlet „Get-ChildItem“ ruft die Objekte ab, die die Schlüssel darstellen.</span><span class="sxs-lookup"><span data-stu-id="b5571-117">The Get-ChildItem cmdlet gets objects representing the keys.</span></span> <span data-ttu-id="b5571-118">Der Pfad wird als "HKCU:" angegeben, eines der Laufwerke, die vom PowerShell-Registrierungs Anbieter verfügbar gemacht werden, gefolgt vom Schlüssel Pfad.</span><span class="sxs-lookup"><span data-stu-id="b5571-118">The path is specified as HKCU:, one of the drives exposed by the PowerShell Registry provider, followed by the key path.</span></span> <span data-ttu-id="b5571-119">Der Pipeline Operator (|) übergibt die Registrierungsschlüssel Objekte über die Pipeline an `Format-Wide` , wodurch Sie für die Ausgabe formatiert werden.</span><span class="sxs-lookup"><span data-stu-id="b5571-119">The pipeline operator (|) passes the registry key objects through the pipeline to `Format-Wide`, which formats them for output.</span></span> <span data-ttu-id="b5571-120">Der **Property** -Parameter gibt den Namen der Eigenschaft an, und der **AutoSize** -Parameter passt die Spalten zur besseren Lesbarkeit an.</span><span class="sxs-lookup"><span data-stu-id="b5571-120">The **Property** parameter specifies the name of the property, and the **AutoSize** parameter adjusts the columns for readability.</span></span>

### <span data-ttu-id="b5571-121">Beispiel 3: Problembehandlung bei Format Fehlern</span><span class="sxs-lookup"><span data-stu-id="b5571-121">Example 3: Troubleshooting format errors</span></span>

<span data-ttu-id="b5571-122">Die folgenden Beispiele zeigen die Ergebnisse des Hinzufügens der **displayerror** -oder **ShowError** -Parameter mit einem Ausdruck.</span><span class="sxs-lookup"><span data-stu-id="b5571-122">The following examples show of the results of adding the **DisplayError** or **ShowError** parameters with an expression.</span></span>

```powershell
PS /> Get-Date | Format-Wide { $_ / $null } -DisplayError


#ERR

PS /> Get-Date | Format-Wide { $_ / $null } -ShowError


Failed to evaluate expression " $_ / $null ".
+ CategoryInfo          : InvalidArgument: (12/21/2018 8:18:01 AM:PSObject) [], RuntimeException
+ FullyQualifiedErrorId : PSPropertyExpressionError
```

## <span data-ttu-id="b5571-123">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="b5571-123">PARAMETERS</span></span>

### <span data-ttu-id="b5571-124">-AutoSize</span><span class="sxs-lookup"><span data-stu-id="b5571-124">-AutoSize</span></span>

<span data-ttu-id="b5571-125">Passt die Spaltengröße und die Anzahl der Spalten basierend auf der Breite der Daten an.</span><span class="sxs-lookup"><span data-stu-id="b5571-125">Adjusts the column size and number of columns based on the width of the data.</span></span> <span data-ttu-id="b5571-126">Standardmäßig werden die Spaltengröße und die Anzahl von der Ansicht bestimmt.</span><span class="sxs-lookup"><span data-stu-id="b5571-126">By default, the column size and number are determined by the view.</span></span> <span data-ttu-id="b5571-127">Der **AutoSize** -Parameter und der **Column** -Parameter können nicht im selben Befehl verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="b5571-127">You cannot use the **AutoSize** and **Column** parameters in the same command.</span></span>

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

### <span data-ttu-id="b5571-128">-Spalte</span><span class="sxs-lookup"><span data-stu-id="b5571-128">-Column</span></span>

<span data-ttu-id="b5571-129">Gibt die Anzahl der Spalten in der Anzeige an.</span><span class="sxs-lookup"><span data-stu-id="b5571-129">Specifies the number of columns in the display.</span></span> <span data-ttu-id="b5571-130">Der **AutoSize** -Parameter und der **Column** -Parameter können nicht im selben Befehl verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="b5571-130">You cannot use the **AutoSize** and **Column** parameters in the same command.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b5571-131">-Display Error</span><span class="sxs-lookup"><span data-stu-id="b5571-131">-DisplayError</span></span>

<span data-ttu-id="b5571-132">Zeigt Fehler in der Befehlszeile an.</span><span class="sxs-lookup"><span data-stu-id="b5571-132">Displays errors at the command line.</span></span> <span data-ttu-id="b5571-133">Dieser Parameter wird nur selten verwendet, kann jedoch als Hilfe beim Debuggen verwendet werden, wenn Sie Ausdrücke in einem Befehl formatieren `Format-Wide` und die Ausdrücke nicht zu funktionieren scheinen.</span><span class="sxs-lookup"><span data-stu-id="b5571-133">This parameter is rarely used, but can be used as a debugging aid when you are formatting expressions in a `Format-Wide` command, and the expressions do not appear to be working.</span></span>

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

### <span data-ttu-id="b5571-134">-Erweitern</span><span class="sxs-lookup"><span data-stu-id="b5571-134">-Expand</span></span>

<span data-ttu-id="b5571-135">Formatiert das Auflistungsobjekt und die Objekte in der Auflistung.</span><span class="sxs-lookup"><span data-stu-id="b5571-135">Formats the collection object, as well as the objects in the collection.</span></span> <span data-ttu-id="b5571-136">Dieser Parameter dient zum Formatieren der Objekte, die die ICollection (System.Collections)-Schnittstelle unterstützen.</span><span class="sxs-lookup"><span data-stu-id="b5571-136">This parameter is designed to format objects that support the ICollection (System.Collections) interface.</span></span> <span data-ttu-id="b5571-137">Der Standardwert ist " **enumonly**".</span><span class="sxs-lookup"><span data-stu-id="b5571-137">The default value is **EnumOnly**.</span></span>

<span data-ttu-id="b5571-138">Gültige Werte sind:</span><span class="sxs-lookup"><span data-stu-id="b5571-138">Valid values are:</span></span>

- <span data-ttu-id="b5571-139">Enumonly: zeigt die Eigenschaften der Objekte in der Auflistung an.</span><span class="sxs-lookup"><span data-stu-id="b5571-139">EnumOnly: Displays the properties of the objects in the collection.</span></span>
- <span data-ttu-id="b5571-140">Coreonly: zeigt die Eigenschaften des Auflistungs Objekts an.</span><span class="sxs-lookup"><span data-stu-id="b5571-140">CoreOnly: Displays the properties of the collection object.</span></span>
- <span data-ttu-id="b5571-141">Beides: zeigt die Eigenschaften des Auflistungs Objekts und die Eigenschaften von Objekten in der Auflistung an.</span><span class="sxs-lookup"><span data-stu-id="b5571-141">Both: Displays the properties of the collection object and the properties of objects in the collection.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: CoreOnly, EnumOnly, Both

Required: False
Position: Named
Default value: EnumOnly
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b5571-142">-Force</span><span class="sxs-lookup"><span data-stu-id="b5571-142">-Force</span></span>

<span data-ttu-id="b5571-143">Gibt an, dass dieses Cmdlet Einschränkungen außer Kraft setzt, die die erfolgreiche Ausführung des Befehls verhindern, sodass die Änderungen nicht die Sicherheit beeinträchtigen.</span><span class="sxs-lookup"><span data-stu-id="b5571-143">Indicates that this cmdlet overrides restrictions that prevent the command from succeeding, just so the changes do not compromise security.</span></span> <span data-ttu-id="b5571-144">Beispielsweise überschreibt **Force** das Schreibschutzattribut oder erstellt Verzeichnisse zum Vervollständigen eines Dateipfads. Es wird jedoch nicht etwa versucht, Dateiberechtigungen zu ändern.</span><span class="sxs-lookup"><span data-stu-id="b5571-144">For example, **Force** will override the read-only attribute or create directories to complete a file path, but it will not attempt to change file permissions.</span></span>

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

### <span data-ttu-id="b5571-145">-GroupBy</span><span class="sxs-lookup"><span data-stu-id="b5571-145">-GroupBy</span></span>

<span data-ttu-id="b5571-146">Formatiert die Ausgabe basierend auf einer freigegebenen Eigenschaft bzw. einem freigegebenen Wert in Gruppen.</span><span class="sxs-lookup"><span data-stu-id="b5571-146">Formats the output in groups based on a shared property or value.</span></span> <span data-ttu-id="b5571-147">Geben Sie einen Ausdruck oder eine Eigenschaft der Ausgabe ein.</span><span class="sxs-lookup"><span data-stu-id="b5571-147">Enter an expression or a property of the output.</span></span>

<span data-ttu-id="b5571-148">Der Wert des **GroupBy** -Parameters kann eine neue berechnete Eigenschaft sein.</span><span class="sxs-lookup"><span data-stu-id="b5571-148">The value of the **GroupBy** parameter can be a new calculated property.</span></span> <span data-ttu-id="b5571-149">Die berechnete Eigenschaft kann ein Skriptblock oder eine Hash Tabelle sein.</span><span class="sxs-lookup"><span data-stu-id="b5571-149">The calculated property can be a script block or a hash table.</span></span> <span data-ttu-id="b5571-150">Gültige Schlüssel-Wert-Paare sind:</span><span class="sxs-lookup"><span data-stu-id="b5571-150">Valid key-value pairs are:</span></span>

- <span data-ttu-id="b5571-151">Name (oder Bezeichnung)- `<string>`</span><span class="sxs-lookup"><span data-stu-id="b5571-151">Name (or Label) - `<string>`</span></span>
- <span data-ttu-id="b5571-152">Ausdruck `<string>` oder `<script block>`</span><span class="sxs-lookup"><span data-stu-id="b5571-152">Expression - `<string>` or `<script block>`</span></span>
- <span data-ttu-id="b5571-153">FormatString `<string>`</span><span class="sxs-lookup"><span data-stu-id="b5571-153">FormatString - `<string>`</span></span>

<span data-ttu-id="b5571-154">Weitere Informationen finden Sie unter [about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md).</span><span class="sxs-lookup"><span data-stu-id="b5571-154">For more information, see [about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md).</span></span>

```yaml
Type: System.Object
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b5571-155">-InputObject</span><span class="sxs-lookup"><span data-stu-id="b5571-155">-InputObject</span></span>

<span data-ttu-id="b5571-156">Gibt die zu formatierenden Objekte an.</span><span class="sxs-lookup"><span data-stu-id="b5571-156">Specifies the objects to format.</span></span> <span data-ttu-id="b5571-157">Geben Sie eine Variable ein, die die Objekte enthält, oder geben Sie einen Befehl oder einen Ausdruck ein, mit dem die Objekte abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="b5571-157">Enter a variable that contains the objects, or type a command or expression that gets the objects.</span></span>

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="b5571-158">-Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="b5571-158">-Property</span></span>

<span data-ttu-id="b5571-159">Gibt die in der Anzeige angezeigten Objekteigenschaften und die Reihenfolge an, in der sie angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="b5571-159">Specifies the object properties that appear in the display and the order in which they appear.</span></span>
<span data-ttu-id="b5571-160">Platzhalter sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="b5571-160">Wildcards are permitted.</span></span>

<span data-ttu-id="b5571-161">Wenn Sie diesen Parameter weglassen, hängen die in der Anzeige dargestellten Eigenschaften von dem angezeigten Objekt ab.</span><span class="sxs-lookup"><span data-stu-id="b5571-161">If you omit this parameter, the properties that appear in the display depend on the object being displayed.</span></span> <span data-ttu-id="b5571-162">Der Parameter Name "Property" ist optional.</span><span class="sxs-lookup"><span data-stu-id="b5571-162">The parameter name "Property" is optional.</span></span> <span data-ttu-id="b5571-163">Sie können die Parameter " **Property** " und " **View** " nicht im selben Befehl verwenden.</span><span class="sxs-lookup"><span data-stu-id="b5571-163">You cannot use the **Property** and **View** parameters in the same command.</span></span>

<span data-ttu-id="b5571-164">Der Wert des **Property** -Parameters kann eine neue berechnete Eigenschaft sein.</span><span class="sxs-lookup"><span data-stu-id="b5571-164">The value of the **Property** parameter can be a new calculated property.</span></span> <span data-ttu-id="b5571-165">Die berechnete Eigenschaft kann ein Skriptblock oder eine Hash Tabelle sein.</span><span class="sxs-lookup"><span data-stu-id="b5571-165">The calculated property can be a script block or a hash table.</span></span> <span data-ttu-id="b5571-166">Gültige Schlüssel-Wert-Paare sind:</span><span class="sxs-lookup"><span data-stu-id="b5571-166">Valid key-value pairs are:</span></span>

- <span data-ttu-id="b5571-167">Ausdruck `<string>` oder `<script block>`</span><span class="sxs-lookup"><span data-stu-id="b5571-167">Expression - `<string>` or `<script block>`</span></span>
- <span data-ttu-id="b5571-168">FormatString `<string>`</span><span class="sxs-lookup"><span data-stu-id="b5571-168">FormatString - `<string>`</span></span>

<span data-ttu-id="b5571-169">Weitere Informationen finden Sie unter [about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md).</span><span class="sxs-lookup"><span data-stu-id="b5571-169">For more information, see [about_Calculated_Properties](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md).</span></span>

```yaml
Type: System.Object
Parameter Sets: (All)
Aliases:

Required: False
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="b5571-170">-ShowError</span><span class="sxs-lookup"><span data-stu-id="b5571-170">-ShowError</span></span>

<span data-ttu-id="b5571-171">Sendet Fehler über die Pipeline.</span><span class="sxs-lookup"><span data-stu-id="b5571-171">Sends errors through the pipeline.</span></span> <span data-ttu-id="b5571-172">Dieser Parameter wird nur selten verwendet, kann jedoch als Hilfe beim Debuggen verwendet werden, wenn Sie Ausdrücke in einem Befehl formatieren `Format-Wide` und die Ausdrücke nicht zu funktionieren scheinen.</span><span class="sxs-lookup"><span data-stu-id="b5571-172">This parameter is rarely used, but can be used as a debugging aid when you are formatting expressions in a `Format-Wide` command, and the expressions do not appear to be working.</span></span>

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

### <span data-ttu-id="b5571-173">-Ansicht</span><span class="sxs-lookup"><span data-stu-id="b5571-173">-View</span></span>

<span data-ttu-id="b5571-174">Gibt den Namen eines alternativen Tabellen Formats oder einer anderen Sicht an.</span><span class="sxs-lookup"><span data-stu-id="b5571-174">Specifies the name of an alternate table format or view.</span></span> <span data-ttu-id="b5571-175">Sie können die Parameter " **Property** " und " **View** " nicht im selben Befehl verwenden.</span><span class="sxs-lookup"><span data-stu-id="b5571-175">You cannot use the **Property** and **View** parameters in the same command.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="b5571-176">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="b5571-176">CommonParameters</span></span>

<span data-ttu-id="b5571-177">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="b5571-177">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="b5571-178">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="b5571-178">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="b5571-179">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="b5571-179">INPUTS</span></span>

### <span data-ttu-id="b5571-180">System. Management. Automation. psobject</span><span class="sxs-lookup"><span data-stu-id="b5571-180">System.Management.Automation.PSObject</span></span>

<span data-ttu-id="b5571-181">Sie können jedes beliebige Objekt an die Pipeline übergeben `Format-Wide` .</span><span class="sxs-lookup"><span data-stu-id="b5571-181">You can pipe any object to `Format-Wide`.</span></span>

## <span data-ttu-id="b5571-182">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="b5571-182">OUTPUTS</span></span>

### <span data-ttu-id="b5571-183">Microsoft. PowerShell. Commands. Internal. Format</span><span class="sxs-lookup"><span data-stu-id="b5571-183">Microsoft.PowerShell.Commands.Internal.Format</span></span>

<span data-ttu-id="b5571-184">`Format-Wide` gibt Format Objekte zurück, die die Tabelle darstellen.</span><span class="sxs-lookup"><span data-stu-id="b5571-184">`Format-Wide` returns format objects that represent the table.</span></span>

## <span data-ttu-id="b5571-185">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="b5571-185">NOTES</span></span>

<span data-ttu-id="b5571-186">Sie können auch auf den `Format-Wide` integrierten Alias verweisen `fw` .</span><span class="sxs-lookup"><span data-stu-id="b5571-186">You can also refer to `Format-Wide` by its built-in alias, `fw`.</span></span> <span data-ttu-id="b5571-187">Weitere Informationen finden Sie unter [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).</span><span class="sxs-lookup"><span data-stu-id="b5571-187">For more information, see [about_Aliases](../Microsoft.PowerShell.Core/About/about_Aliases.md).</span></span>

<span data-ttu-id="b5571-188">Beim **GroupBy** -Parameter wird davon ausgegangen, dass die Objekte sortiert sind.</span><span class="sxs-lookup"><span data-stu-id="b5571-188">The **GroupBy** parameter assumes that the objects are sorted.</span></span> <span data-ttu-id="b5571-189">Verwenden Sie `Sort-Object` `Format-Custom` , um die-Objekte mithilfe von zu gruppieren.</span><span class="sxs-lookup"><span data-stu-id="b5571-189">Use `Sort-Object` before using `Format-Custom` to group the objects.</span></span>

<span data-ttu-id="b5571-190">Mit dem **View** -Parameter können Sie ein alternatives Format für die Tabelle angeben.</span><span class="sxs-lookup"><span data-stu-id="b5571-190">The **View** parameter lets you specify an alternate format for the table.</span></span> <span data-ttu-id="b5571-191">Sie können die in den `*.format.PS1XML` Dateien im PowerShell-Verzeichnis definierten Ansichten verwenden oder Ihre eigenen Ansichten in neuen PS1XML-Dateien erstellen und Sie mit dem `Update-FormatData` Cmdlet in PowerShell einschließen.</span><span class="sxs-lookup"><span data-stu-id="b5571-191">You can use the views defined in the `*.format.PS1XML` files in the PowerShell directory or you can create your own views in new PS1XML files and use the `Update-FormatData` cmdlet to include them in PowerShell.</span></span>

<span data-ttu-id="b5571-192">Die Alternative Ansicht für den **View** -Parameter muss das Tabellenformat verwenden. Wenn dies nicht der Fall ist, schlägt der Befehl fehl.</span><span class="sxs-lookup"><span data-stu-id="b5571-192">The alternate view for the **View** parameter must use table format; if it does not, the command fails.</span></span> <span data-ttu-id="b5571-193">Wenn die Alternative Ansicht eine Liste ist, verwenden Sie `Format-List` .</span><span class="sxs-lookup"><span data-stu-id="b5571-193">If the alternate view is a list, use `Format-List`.</span></span> <span data-ttu-id="b5571-194">Wenn die alternative Ansicht weder eine Liste noch eine Tabelle ist, verwenden Sie Format-Custom.</span><span class="sxs-lookup"><span data-stu-id="b5571-194">If the alternate view is neither a list nor a table, use Format-Custom.</span></span>

## <span data-ttu-id="b5571-195">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="b5571-195">RELATED LINKS</span></span>

[<span data-ttu-id="b5571-196">about_Calculated_Properties</span><span class="sxs-lookup"><span data-stu-id="b5571-196">about_Calculated_Properties</span></span>](../Microsoft.PowerShell.Core/About/about_Calculated_Properties.md)

[<span data-ttu-id="b5571-197">Format-Custom</span><span class="sxs-lookup"><span data-stu-id="b5571-197">Format-Custom</span></span>](Format-Custom.md)

[<span data-ttu-id="b5571-198">Format-Hex</span><span class="sxs-lookup"><span data-stu-id="b5571-198">Format-Hex</span></span>](Format-Hex.md)

[<span data-ttu-id="b5571-199">Format-List</span><span class="sxs-lookup"><span data-stu-id="b5571-199">Format-List</span></span>](Format-List.md)

[<span data-ttu-id="b5571-200">Format-Table</span><span class="sxs-lookup"><span data-stu-id="b5571-200">Format-Table</span></span>](Format-Table.md)