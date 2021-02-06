---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 11/02/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/convertfrom-markdown?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: ConvertFrom-Markdown
ms.openlocfilehash: c694e73e69c1e51ecf88f445684923ef5f19113f
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99601915"
---
# <span data-ttu-id="3ba7f-102">ConvertFrom-Markdown</span><span class="sxs-lookup"><span data-stu-id="3ba7f-102">ConvertFrom-Markdown</span></span>

## <span data-ttu-id="3ba7f-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="3ba7f-103">SYNOPSIS</span></span>
<span data-ttu-id="3ba7f-104">Konvertiert den Inhalt einer Zeichenfolge oder einer Datei in ein **markdowninfo** -Objekt.</span><span class="sxs-lookup"><span data-stu-id="3ba7f-104">Convert the contents of a string or a file to a **MarkdownInfo** object.</span></span>

## <span data-ttu-id="3ba7f-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="3ba7f-105">SYNTAX</span></span>

### <span data-ttu-id="3ba7f-106">Pathparamset (Standard)</span><span class="sxs-lookup"><span data-stu-id="3ba7f-106">PathParamSet (Default)</span></span>

```
ConvertFrom-Markdown [-Path] <String[]> [-AsVT100EncodedString] [<CommonParameters>]
```

### <span data-ttu-id="3ba7f-107">Literalparamset</span><span class="sxs-lookup"><span data-stu-id="3ba7f-107">LiteralParamSet</span></span>

```
ConvertFrom-Markdown -LiteralPath <String[]> [-AsVT100EncodedString] [<CommonParameters>]
```

### <span data-ttu-id="3ba7f-108">Inputobjparamset</span><span class="sxs-lookup"><span data-stu-id="3ba7f-108">InputObjParamSet</span></span>

```
ConvertFrom-Markdown -InputObject <PSObject> [-AsVT100EncodedString] [<CommonParameters>]
```

## <span data-ttu-id="3ba7f-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="3ba7f-109">DESCRIPTION</span></span>

<span data-ttu-id="3ba7f-110">Dieses Cmdlet konvertiert den angegebenen Inhalt in eine **markdowninfo**.</span><span class="sxs-lookup"><span data-stu-id="3ba7f-110">This cmdlet converts the specified content into a **MarkdownInfo**.</span></span> <span data-ttu-id="3ba7f-111">Wenn ein Dateipfad für den **path** -Parameter angegeben wird, wird der Inhalt der Datei konvertiert.</span><span class="sxs-lookup"><span data-stu-id="3ba7f-111">When a file path is specified for the **Path** parameter, the contents on the file are converted.</span></span> <span data-ttu-id="3ba7f-112">Das Ausgabe Objekt verfügt über drei Eigenschaften:</span><span class="sxs-lookup"><span data-stu-id="3ba7f-112">The output object has three properties:</span></span>

- <span data-ttu-id="3ba7f-113">Die **Token** -Eigenschaft verfügt über die abstrakte Syntax Struktur (AST) des konvertierten Objekts.</span><span class="sxs-lookup"><span data-stu-id="3ba7f-113">The **Token** property has the abstract syntax tree (AST) of the the converted object</span></span>
- <span data-ttu-id="3ba7f-114">Die **HTML** -Eigenschaft hat die HTML-Konvertierung der angegebenen Eingabe.</span><span class="sxs-lookup"><span data-stu-id="3ba7f-114">The **Html** property has the HTML conversion of the specified input</span></span>
- <span data-ttu-id="3ba7f-115">Die **VT100EncodedString** -Eigenschaft hat die konvertierte Zeichenfolge mit ANSI (VT100)-Escapesequenzen, wenn der **AsVT100EncodedString** -Parameter angegeben wurde</span><span class="sxs-lookup"><span data-stu-id="3ba7f-115">The **VT100EncodedString** property has the converted string with ANSI (VT100) escape sequences if the **AsVT100EncodedString** parameter was specified</span></span>

<span data-ttu-id="3ba7f-116">Dieses Cmdlet wurde in PowerShell 6,1 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="3ba7f-116">This cmdlet was introduced in PowerShell 6.1.</span></span>

## <span data-ttu-id="3ba7f-117">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="3ba7f-117">EXAMPLES</span></span>

### <span data-ttu-id="3ba7f-118">Beispiel 1: Konvertieren einer Datei mit markdown-Inhalt in HTML</span><span class="sxs-lookup"><span data-stu-id="3ba7f-118">Example 1: Convert a file containing Markdown content to HTML</span></span>

```powershell
ConvertFrom-Markdown -Path .\README.md
```

<span data-ttu-id="3ba7f-119">Das **markdowninfo** -Objekt wird zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="3ba7f-119">The **MarkdownInfo** object is returned.</span></span> <span data-ttu-id="3ba7f-120">Die **Tokens** -Eigenschaft verfügt über die Ast des konvertierten Inhalts der `README.md` Datei.</span><span class="sxs-lookup"><span data-stu-id="3ba7f-120">The **Tokens** property has the AST of the converted content of the `README.md` file.</span></span> <span data-ttu-id="3ba7f-121">Die **HTML** -Eigenschaft verfügt über den HTML-konvertierten Inhalt der `README.md` Datei.</span><span class="sxs-lookup"><span data-stu-id="3ba7f-121">The **Html** property has the HTML converted content of the `README.md` file.</span></span>

### <span data-ttu-id="3ba7f-122">Beispiel 2: Konvertieren einer Datei, die markdown-Inhalte enthält, in eine VT100-codierte Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="3ba7f-122">Example 2: Convert a file containing Markdown content to a VT100-encoded string</span></span>

```powershell
ConvertFrom-Markdown -Path .\README.md -AsVT100EncodedString
```

<span data-ttu-id="3ba7f-123">Das **markdowninfo** -Objekt wird zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="3ba7f-123">The **MarkdownInfo** object is returned.</span></span> <span data-ttu-id="3ba7f-124">Die **Tokens** -Eigenschaft verfügt über die Ast des konvertierten Inhalts der `README.md` Datei.</span><span class="sxs-lookup"><span data-stu-id="3ba7f-124">The **Tokens** property has the AST of the converted content of the `README.md` file.</span></span> <span data-ttu-id="3ba7f-125">Die **VT100EncodedString** -Eigenschaft weist den VT100-codierten Zeichen folgen konvertierten Inhalt der `README.md` Datei auf.</span><span class="sxs-lookup"><span data-stu-id="3ba7f-125">The **VT100EncodedString** property has the VT100-encoded string converted content of the `README.md` file.</span></span>

### <span data-ttu-id="3ba7f-126">Beispiel 3: Konvertieren eines Eingabe Objekts mit markdown-Inhalt in eine VT100-codierte Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="3ba7f-126">Example 3: Convert input object containing Markdown content to a VT100-encoded string</span></span>

```powershell
Get-Item .\README.md | ConvertFrom-Markdown -AsVT100EncodedString
```

<span data-ttu-id="3ba7f-127">Das **markdowninfo** -Objekt wird zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="3ba7f-127">The **MarkdownInfo** object is returned.</span></span> <span data-ttu-id="3ba7f-128">Das **FileInfo** -Objekt von `Get-Item` wird in eine VT100-codierte Zeichenfolge konvertiert.</span><span class="sxs-lookup"><span data-stu-id="3ba7f-128">The **FileInfo** object from `Get-Item` is converted to a VT100-encoded string.</span></span> <span data-ttu-id="3ba7f-129">Die **Tokens** -Eigenschaft verfügt über die Ast des konvertierten Inhalts der `README.md` Datei.</span><span class="sxs-lookup"><span data-stu-id="3ba7f-129">The **Tokens** property has the AST of the converted content of the `README.md` file.</span></span> <span data-ttu-id="3ba7f-130">Die **VT100EncodedString** -Eigenschaft weist den VT100-codierten Zeichen folgen konvertierten Inhalt der `README.md` Datei auf.</span><span class="sxs-lookup"><span data-stu-id="3ba7f-130">The **VT100EncodedString** property has the VT100-encoded string converted content of the `README.md` file.</span></span>

### <span data-ttu-id="3ba7f-131">Beispiel 4: Konvertieren einer Zeichenfolge mit markdown-Inhalt in eine VT100-codierte Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="3ba7f-131">Example 4: Convert a string containing Markdown content to a VT100-encoded string</span></span>

```powershell
"**Bold text**" | ConvertFrom-Markdown -AsVT100EncodedString
```

<span data-ttu-id="3ba7f-132">Das **markdowninfo** -Objekt wird zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="3ba7f-132">The **MarkdownInfo** object is returned.</span></span> <span data-ttu-id="3ba7f-133">Die angegebene Zeichenfolge `**Bold text**` wird in eine VT100-codierte Zeichenfolge konvertiert und ist in der **VT100EncodedString** -Eigenschaft verfügbar.</span><span class="sxs-lookup"><span data-stu-id="3ba7f-133">The specified string `**Bold text**` is converted to a VT100-encoded string and available in **VT100EncodedString** property.</span></span>

## <span data-ttu-id="3ba7f-134">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="3ba7f-134">PARAMETERS</span></span>

### <span data-ttu-id="3ba7f-135">-AsVT100EncodedString</span><span class="sxs-lookup"><span data-stu-id="3ba7f-135">-AsVT100EncodedString</span></span>

<span data-ttu-id="3ba7f-136">Gibt an, ob die Ausgabe als Zeichenfolge mit VT100-Escapecodes codiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="3ba7f-136">Specifies if the output should be encoded as a string with VT100 escape codes.</span></span>

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

### <span data-ttu-id="3ba7f-137">-InputObject</span><span class="sxs-lookup"><span data-stu-id="3ba7f-137">-InputObject</span></span>

<span data-ttu-id="3ba7f-138">Gibt das zu konvertierende Objekt an.</span><span class="sxs-lookup"><span data-stu-id="3ba7f-138">Specifies the object to be converted.</span></span> <span data-ttu-id="3ba7f-139">Wenn ein Objekt vom Typ " **System. String** " angegeben wird, wird die Zeichenfolge konvertiert.</span><span class="sxs-lookup"><span data-stu-id="3ba7f-139">When an object of type **System.String** is specified, the string is converted.</span></span> <span data-ttu-id="3ba7f-140">Wenn ein Objekt vom Typ **System. IO. FileInfo** angegeben wird, wird der Inhalt der durch das-Objekt angegebenen Datei konvertiert.</span><span class="sxs-lookup"><span data-stu-id="3ba7f-140">When an object of type **System.IO.FileInfo** is specified, the contents of the file specified by the object are converted.</span></span> <span data-ttu-id="3ba7f-141">Objekte eines beliebigen anderen Typs führen zu einem Fehler.</span><span class="sxs-lookup"><span data-stu-id="3ba7f-141">Objects of any other type result in an error.</span></span>

```yaml
Type: System.Management.Automation.PSObject
Parameter Sets: InputObjParamSet
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="3ba7f-142">-Literalpath</span><span class="sxs-lookup"><span data-stu-id="3ba7f-142">-LiteralPath</span></span>

<span data-ttu-id="3ba7f-143">Gibt einen Pfad zu der Datei an, die konvertiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="3ba7f-143">Specifies a path to the file to be converted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: LiteralParamSet
Aliases: PSPath, LP

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="3ba7f-144">-Path</span><span class="sxs-lookup"><span data-stu-id="3ba7f-144">-Path</span></span>

<span data-ttu-id="3ba7f-145">Gibt einen Pfad zu der Datei an, die konvertiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="3ba7f-145">Specifies a path to the file to be converted.</span></span>

```yaml
Type: System.String[]
Parameter Sets: PathParamSet
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="3ba7f-146">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="3ba7f-146">CommonParameters</span></span>

<span data-ttu-id="3ba7f-147">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="3ba7f-147">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="3ba7f-148">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="3ba7f-148">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="3ba7f-149">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="3ba7f-149">INPUTS</span></span>

### <span data-ttu-id="3ba7f-150">System. Management. Automation. psobject</span><span class="sxs-lookup"><span data-stu-id="3ba7f-150">System.Management.Automation.PSObject</span></span>

## <span data-ttu-id="3ba7f-151">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="3ba7f-151">OUTPUTS</span></span>

### <span data-ttu-id="3ba7f-152">Microsoft. PowerShell. markdownrendering. markdowninfo</span><span class="sxs-lookup"><span data-stu-id="3ba7f-152">Microsoft.PowerShell.MarkdownRender.MarkdownInfo</span></span>

## <span data-ttu-id="3ba7f-153">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="3ba7f-153">NOTES</span></span>

## <span data-ttu-id="3ba7f-154">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="3ba7f-154">RELATED LINKS</span></span>

[<span data-ttu-id="3ba7f-155">Markdownparser</span><span class="sxs-lookup"><span data-stu-id="3ba7f-155">Markdown Parser</span></span>](https://github.com/lunet-io/markdig)

[<span data-ttu-id="3ba7f-156">ANSI-Escapecode</span><span class="sxs-lookup"><span data-stu-id="3ba7f-156">ANSI escape code</span></span>](https://wikipedia.org/wiki/ANSI_escape_code)
