---
external help file: Microsoft.PowerShell.Commands.Management.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Management
ms.date: 05/14/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.management/move-itemproperty?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Move-ItemProperty
ms.openlocfilehash: 92a14e4bd165efd4721e3802cade827744c9c056
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99601725"
---
# <span data-ttu-id="d61ec-102">Move-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="d61ec-102">Move-ItemProperty</span></span>

## <span data-ttu-id="d61ec-103">Übersicht</span><span class="sxs-lookup"><span data-stu-id="d61ec-103">Synopsis</span></span>
<span data-ttu-id="d61ec-104">Verschiebt eine Eigenschaft von einem Speicherort an einen anderen Speicherort.</span><span class="sxs-lookup"><span data-stu-id="d61ec-104">Moves a property from one location to another.</span></span>

## <span data-ttu-id="d61ec-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="d61ec-105">SYNTAX</span></span>

### <span data-ttu-id="d61ec-106">Pfad (Standard)</span><span class="sxs-lookup"><span data-stu-id="d61ec-106">Path (Default)</span></span>

```
Move-ItemProperty [-Path] <String[]> [-Name] <String[]> [-Destination] <String> [-PassThru] [-Force]
 [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>] [-Credential <PSCredential>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="d61ec-107">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="d61ec-107">LiteralPath</span></span>

```
Move-ItemProperty -LiteralPath <String[]> [-Name] <String[]> [-Destination] <String> [-PassThru] [-Force]
 [-Filter <String>] [-Include <String[]>] [-Exclude <String[]>] [-Credential <PSCredential>]
 [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="d61ec-108">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="d61ec-108">Description</span></span>

<span data-ttu-id="d61ec-109">Mit dem- `Move-ItemProperty` Cmdlet wird eine Eigenschaft eines Elements von einem Element zu einem anderen Element verschoben.</span><span class="sxs-lookup"><span data-stu-id="d61ec-109">The `Move-ItemProperty` cmdlet moves a property of an item from one item to another item.</span></span>
<span data-ttu-id="d61ec-110">Beispielsweise kann ein Registrierungs Eintrag von einem Registrierungsschlüssel in einen anderen Registrierungsschlüssel verschoben werden.</span><span class="sxs-lookup"><span data-stu-id="d61ec-110">For instance, it can move a registry entry from one registry key to another registry key.</span></span>
<span data-ttu-id="d61ec-111">Beim Verschieben einer Elementeigenschaft wird diese am neuen Speicherort hinzugefügt und an ihrem ursprünglichen Speicherort gelöscht.</span><span class="sxs-lookup"><span data-stu-id="d61ec-111">When you move an item property, it is added to the new location and deleted from its original location.</span></span>

## <span data-ttu-id="d61ec-112">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="d61ec-112">EXAMPLES</span></span>

### <span data-ttu-id="d61ec-113">Beispiel 1: Verschieben eines Registrierungs Werts und seiner Daten in einen anderen Schlüssel</span><span class="sxs-lookup"><span data-stu-id="d61ec-113">Example 1: Move a registry value and its data to another key</span></span>

<span data-ttu-id="d61ec-114">Dieser Befehl verschiebt den Versions Registrierungs Wert und seine Daten aus dem Unterschlüssel "MyApp" in den newapp-Unterschlüssel des `HKLM\Software\MyCompany` Registrierungsschlüssels.</span><span class="sxs-lookup"><span data-stu-id="d61ec-114">This command moves the Version registry value, and its data, from the "MyApp" subkey to the NewApp subkey of the `HKLM\Software\MyCompany` registry key.</span></span>

```powershell
Move-ItemProperty "HKLM:\Software\MyCompany\MyApp" -Name "Version" -Destination "HKLM:\Software\MyCompany\NewApp"
```

## <span data-ttu-id="d61ec-115">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="d61ec-115">PARAMETERS</span></span>

### <span data-ttu-id="d61ec-116">-Credential</span><span class="sxs-lookup"><span data-stu-id="d61ec-116">-Credential</span></span>

> [!NOTE]
> <span data-ttu-id="d61ec-117">Dieser Parameter wird von Anbietern, die mit PowerShell installiert wurden, nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="d61ec-117">This parameter is not supported by any providers installed with PowerShell.</span></span>
> <span data-ttu-id="d61ec-118">Verwenden Sie zum Annehmen der Identität eines anderen Benutzers oder zum herauf Stufen ihrer Anmelde Informationen bei der Ausführung dieses Cmdlets "Start [-Command](../Microsoft.PowerShell.Core/Invoke-Command.md)".</span><span class="sxs-lookup"><span data-stu-id="d61ec-118">To impersonate another user, or elevate your credentials when running this cmdlet, use [Invoke-Command](../Microsoft.PowerShell.Core/Invoke-Command.md).</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Current user
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="d61ec-119">-Destination</span><span class="sxs-lookup"><span data-stu-id="d61ec-119">-Destination</span></span>

<span data-ttu-id="d61ec-120">Gibt den Pfad zum Zielspeicherort an.</span><span class="sxs-lookup"><span data-stu-id="d61ec-120">Specifies the path to the destination location.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="d61ec-121">-Ausschließen</span><span class="sxs-lookup"><span data-stu-id="d61ec-121">-Exclude</span></span>

<span data-ttu-id="d61ec-122">Gibt als Zeichen folgen Array ein Element oder Elemente an, die von diesem Cmdlet im Vorgang ausgeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="d61ec-122">Specifies, as a string array, an item or items that this cmdlet excludes in the operation.</span></span> <span data-ttu-id="d61ec-123">Der Wert dieses Parameters qualifiziert den **Path**-Parameter.</span><span class="sxs-lookup"><span data-stu-id="d61ec-123">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="d61ec-124">Geben Sie ein Pfad Element oder-Muster ein, z `*.txt` . b..</span><span class="sxs-lookup"><span data-stu-id="d61ec-124">Enter a path element or pattern, such as `*.txt`.</span></span> <span data-ttu-id="d61ec-125">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="d61ec-125">Wildcard characters are permitted.</span></span> <span data-ttu-id="d61ec-126">Der **Exclude** -Parameter ist nur wirksam, wenn der-Befehl den Inhalt eines Elements enthält, z `C:\Windows\*` . b., wobei das Platzhalter Zeichen den Inhalt des `C:\Windows` Verzeichnisses angibt.</span><span class="sxs-lookup"><span data-stu-id="d61ec-126">The **Exclude** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="d61ec-127">-Filter</span><span class="sxs-lookup"><span data-stu-id="d61ec-127">-Filter</span></span>

<span data-ttu-id="d61ec-128">Gibt einen Filter zum Qualifizieren des **path** -Parameters an.</span><span class="sxs-lookup"><span data-stu-id="d61ec-128">Specifies a filter to qualify the **Path** parameter.</span></span> <span data-ttu-id="d61ec-129">Der [File System](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) -Anbieter ist der einzige installierte PowerShell-Anbieter, der die Verwendung von Filtern unterstützt.</span><span class="sxs-lookup"><span data-stu-id="d61ec-129">The [FileSystem](../Microsoft.PowerShell.Core/About/about_FileSystem_Provider.md) provider is the only installed PowerShell provider that supports the use of filters.</span></span> <span data-ttu-id="d61ec-130">Die Syntax für die Filter Sprache des **Dateisystems** finden Sie in [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).</span><span class="sxs-lookup"><span data-stu-id="d61ec-130">You can find the syntax for the **FileSystem** filter language in [about_Wildcards](../Microsoft.PowerShell.Core/About/about_Wildcards.md).</span></span>
<span data-ttu-id="d61ec-131">Filter sind effizienter als andere Parameter, da Sie vom Anbieter angewendet werden, wenn das Cmdlet die Objekte abruft, statt dass PowerShell die Objekte nach dem Abrufen filtert.</span><span class="sxs-lookup"><span data-stu-id="d61ec-131">Filters are more efficient than other parameters, because the provider applies them when the cmdlet gets the objects rather than having PowerShell filter the objects after they are retrieved.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="d61ec-132">-Force</span><span class="sxs-lookup"><span data-stu-id="d61ec-132">-Force</span></span>

<span data-ttu-id="d61ec-133">Erzwingt die Ausführung des Befehls ohne Aufforderung zur Bestätigung durch den Benutzer.</span><span class="sxs-lookup"><span data-stu-id="d61ec-133">Forces the command to run without asking for user confirmation.</span></span>
<span data-ttu-id="d61ec-134">Die Implementierung unterscheidet sich bei den einzelnen Anbietern.</span><span class="sxs-lookup"><span data-stu-id="d61ec-134">Implementation varies from provider to provider.</span></span>
<span data-ttu-id="d61ec-135">Weitere Informationen finden Sie unter [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="d61ec-135">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d61ec-136">-Include</span><span class="sxs-lookup"><span data-stu-id="d61ec-136">-Include</span></span>

<span data-ttu-id="d61ec-137">Gibt als Zeichen folgen Array ein Element oder Elemente an, die dieses Cmdlet in den Vorgang einschließt.</span><span class="sxs-lookup"><span data-stu-id="d61ec-137">Specifies, as a string array, an item or items that this cmdlet includes in the operation.</span></span> <span data-ttu-id="d61ec-138">Der Wert dieses Parameters qualifiziert den **Path**-Parameter.</span><span class="sxs-lookup"><span data-stu-id="d61ec-138">The value of this parameter qualifies the **Path** parameter.</span></span> <span data-ttu-id="d61ec-139">Geben Sie ein Pfad Element oder-Muster ein, z `"*.txt"` . b..</span><span class="sxs-lookup"><span data-stu-id="d61ec-139">Enter a path element or pattern, such as `"*.txt"`.</span></span> <span data-ttu-id="d61ec-140">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="d61ec-140">Wildcard characters are permitted.</span></span> <span data-ttu-id="d61ec-141">Der **include** -Parameter ist nur wirksam, wenn der-Befehl den Inhalt eines Elements enthält, z `C:\Windows\*` . b., wobei das Platzhalter Zeichen den Inhalt des `C:\Windows` Verzeichnisses angibt.</span><span class="sxs-lookup"><span data-stu-id="d61ec-141">The **Include** parameter is effective only when the command includes the contents of an item, such as `C:\Windows\*`, where the wildcard character specifies the contents of the `C:\Windows` directory.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="d61ec-142">-Literalpath</span><span class="sxs-lookup"><span data-stu-id="d61ec-142">-LiteralPath</span></span>

<span data-ttu-id="d61ec-143">Gibt einen Pfad zu einem oder mehreren Speicherorten an.</span><span class="sxs-lookup"><span data-stu-id="d61ec-143">Specifies a path to one or more locations.</span></span> <span data-ttu-id="d61ec-144">Der Wert von **literalpath** wird genau so verwendet, wie er eingegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="d61ec-144">The value of **LiteralPath** is used exactly as it is typed.</span></span> <span data-ttu-id="d61ec-145">Es werden keine Zeichen als Platzhalter interpretiert.</span><span class="sxs-lookup"><span data-stu-id="d61ec-145">No characters are interpreted as wildcards.</span></span> <span data-ttu-id="d61ec-146">Wenn der Pfad Escapezeichen enthält, müssen Sie ihn in einfache Anführungszeichen einschließen.</span><span class="sxs-lookup"><span data-stu-id="d61ec-146">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="d61ec-147">Einfache Anführungszeichen veranlassen PowerShell, Zeichen nicht als Escapesequenzen zu interpretieren.</span><span class="sxs-lookup"><span data-stu-id="d61ec-147">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

<span data-ttu-id="d61ec-148">Weitere Informationen finden Sie unter [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span><span class="sxs-lookup"><span data-stu-id="d61ec-148">For more information, see [about_Quoting_Rules](../Microsoft.Powershell.Core/About/about_Quoting_Rules.md).</span></span>

```yaml
Type: System.String[]
Parameter Sets: LiteralPath
Aliases: PSPath, LP

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="d61ec-149">-Name</span><span class="sxs-lookup"><span data-stu-id="d61ec-149">-Name</span></span>

<span data-ttu-id="d61ec-150">Gibt den Namen der zu verschiebenden Eigenschaft an.</span><span class="sxs-lookup"><span data-stu-id="d61ec-150">Specifies the name of the property to be moved.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases: PSProperty

Required: True
Position: 2
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="d61ec-151">-PassThru</span><span class="sxs-lookup"><span data-stu-id="d61ec-151">-PassThru</span></span>

<span data-ttu-id="d61ec-152">Gibt ein Objekt zurück, das das Element darstellt, mit dem Sie arbeiten.</span><span class="sxs-lookup"><span data-stu-id="d61ec-152">Returns an object representing the item with which you are working.</span></span>
<span data-ttu-id="d61ec-153">Standardmäßig wird von diesem Cmdlet keine Ausgabe generiert.</span><span class="sxs-lookup"><span data-stu-id="d61ec-153">By default, this cmdlet does not generate any output.</span></span>

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

### <span data-ttu-id="d61ec-154">-Path</span><span class="sxs-lookup"><span data-stu-id="d61ec-154">-Path</span></span>

<span data-ttu-id="d61ec-155">Gibt den Pfad zum aktuellen Speicherort der Eigenschaft an.</span><span class="sxs-lookup"><span data-stu-id="d61ec-155">Specifies the path to the current location of the property.</span></span>
<span data-ttu-id="d61ec-156">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="d61ec-156">Wildcard characters are permitted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Path
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### <span data-ttu-id="d61ec-157">-Confirm</span><span class="sxs-lookup"><span data-stu-id="d61ec-157">-Confirm</span></span>

<span data-ttu-id="d61ec-158">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="d61ec-158">Prompts you for confirmation before running the cmdlet.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d61ec-159">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="d61ec-159">-WhatIf</span></span>

<span data-ttu-id="d61ec-160">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="d61ec-160">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="d61ec-161">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="d61ec-161">The cmdlet is not run.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="d61ec-162">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="d61ec-162">CommonParameters</span></span>

<span data-ttu-id="d61ec-163">Dieses Cmdlet unterstützt die allgemeinen Parameter: `-Debug` , `-ErrorAction` , `-ErrorVariable` , `-InformationAction` , `-InformationVariable` , `-OutVariable` , `-OutBuffer` , `-PipelineVariable` , `-Verbose` , `-WarningAction` und `-WarningVariable` .</span><span class="sxs-lookup"><span data-stu-id="d61ec-163">This cmdlet supports the common parameters: `-Debug`, `-ErrorAction`, `-ErrorVariable`, `-InformationAction`, `-InformationVariable`, `-OutVariable`, `-OutBuffer`, `-PipelineVariable`, `-Verbose`, `-WarningAction`, and `-WarningVariable`.</span></span> <span data-ttu-id="d61ec-164">Weitere Informationen findest du unter [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="d61ec-164">For more information, see [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

## <span data-ttu-id="d61ec-165">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="d61ec-165">INPUTS</span></span>

### <span data-ttu-id="d61ec-166">System.String</span><span class="sxs-lookup"><span data-stu-id="d61ec-166">System.String</span></span>

<span data-ttu-id="d61ec-167">Sie können eine Zeichenfolge weiterreichen, die einen Pfad zu diesem Cmdlet enthält.</span><span class="sxs-lookup"><span data-stu-id="d61ec-167">You can pipe a string that contains a path to this cmdlet.</span></span>

## <span data-ttu-id="d61ec-168">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="d61ec-168">OUTPUTS</span></span>

### <span data-ttu-id="d61ec-169">None oder System. Management. Automation. pscustomobject</span><span class="sxs-lookup"><span data-stu-id="d61ec-169">None or System.Management.Automation.PSCustomObject</span></span>

<span data-ttu-id="d61ec-170">Wenn Sie den **passthru** -Parameter verwenden, generiert dieses Cmdlet ein **pscustomobject-Objekt** , das die verschoderte Element Eigenschaft darstellt.</span><span class="sxs-lookup"><span data-stu-id="d61ec-170">When you use the **PassThru** parameter, this cmdlet generates a **PSCustomObject** representing the moved item property.</span></span> <span data-ttu-id="d61ec-171">Andernfalls wird von diesem Cmdlet keine Ausgabe generiert.</span><span class="sxs-lookup"><span data-stu-id="d61ec-171">Otherwise, this cmdlet does not generate any output.</span></span>

## <span data-ttu-id="d61ec-172">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="d61ec-172">NOTES</span></span>

<span data-ttu-id="d61ec-173">Dieses Cmdlet ist für die Arbeit mit den Daten konzipiert, die von beliebigen Anbietern verfügbar gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="d61ec-173">This cmdlet is designed to work with the data exposed by any provider.</span></span> <span data-ttu-id="d61ec-174">Um die in Ihrer Sitzung verfügbaren Anbieter aufzulisten, geben Sie ein `Get-PSProvider` .</span><span class="sxs-lookup"><span data-stu-id="d61ec-174">To list the providers available in your session, type `Get-PSProvider`.</span></span> <span data-ttu-id="d61ec-175">Weitere Informationen finden Sie unter [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span><span class="sxs-lookup"><span data-stu-id="d61ec-175">For more information, see [about_Providers](../Microsoft.PowerShell.Core/About/about_Providers.md).</span></span>

## <span data-ttu-id="d61ec-176">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="d61ec-176">RELATED LINKS</span></span>

[<span data-ttu-id="d61ec-177">Clear-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="d61ec-177">Clear-ItemProperty</span></span>](Clear-ItemProperty.md)

[<span data-ttu-id="d61ec-178">Copy-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="d61ec-178">Copy-ItemProperty</span></span>](Copy-ItemProperty.md)

[<span data-ttu-id="d61ec-179">Get-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="d61ec-179">Get-ItemProperty</span></span>](Get-ItemProperty.md)

[<span data-ttu-id="d61ec-180">New-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="d61ec-180">New-ItemProperty</span></span>](New-ItemProperty.md)

[<span data-ttu-id="d61ec-181">Remove-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="d61ec-181">Remove-ItemProperty</span></span>](Remove-ItemProperty.md)

[<span data-ttu-id="d61ec-182">Rename-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="d61ec-182">Rename-ItemProperty</span></span>](Rename-ItemProperty.md)

[<span data-ttu-id="d61ec-183">Set-ItemProperty</span><span class="sxs-lookup"><span data-stu-id="d61ec-183">Set-ItemProperty</span></span>](Set-ItemProperty.md)

[<span data-ttu-id="d61ec-184">about_Providers</span><span class="sxs-lookup"><span data-stu-id="d61ec-184">about_Providers</span></span>](../Microsoft.PowerShell.Core/About/about_Providers.md)
