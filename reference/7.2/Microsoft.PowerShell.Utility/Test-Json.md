---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 09/19/2019
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/test-json?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Test-Json
ms.openlocfilehash: a29eab449e567f78d1e54a6716ca91d87aa08405
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99600302"
---
# <span data-ttu-id="6e2de-102">Test-Json</span><span class="sxs-lookup"><span data-stu-id="6e2de-102">Test-Json</span></span>

## <span data-ttu-id="6e2de-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="6e2de-103">SYNOPSIS</span></span>
<span data-ttu-id="6e2de-104">Testet, ob eine Zeichenfolge ein gültiges JSON-Dokument ist.</span><span class="sxs-lookup"><span data-stu-id="6e2de-104">Tests whether a string is a valid JSON document</span></span>

## <span data-ttu-id="6e2de-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="6e2de-105">SYNTAX</span></span>

### <span data-ttu-id="6e2de-106">__AllParameterSets (Standard)</span><span class="sxs-lookup"><span data-stu-id="6e2de-106">__AllParameterSets (Default)</span></span>
```
Test-Json [-Json] <String> [<CommonParameters>]
```

### <span data-ttu-id="6e2de-107">Schemastring</span><span class="sxs-lookup"><span data-stu-id="6e2de-107">SchemaString</span></span>
```
Test-Json [-Json] <String> [[-Schema] <String>] [<CommonParameters>]
```

### <span data-ttu-id="6e2de-108">Schema file</span><span class="sxs-lookup"><span data-stu-id="6e2de-108">SchemaFile</span></span>
```
Test-Json [-Json] <String> [-SchemaFile <String>] [<CommonParameters>]
```

## <span data-ttu-id="6e2de-109">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="6e2de-109">DESCRIPTION</span></span>

<span data-ttu-id="6e2de-110">Das `Test-Json` -Cmdlet testet, ob eine Zeichenfolge ein gültiges JavaScript Object Notation (JSON)-Dokument ist, und kann optional das JSON-Dokument anhand eines bereitgestellten Schemas überprüfen.</span><span class="sxs-lookup"><span data-stu-id="6e2de-110">The `Test-Json` cmdlet tests whether a string is a valid JavaScript Object Notation (JSON) document and can optionally verify that JSON document against a provided schema.</span></span>

<span data-ttu-id="6e2de-111">Die überprüfte Zeichenfolge kann dann mit dem `ConvertFrom-Json` Cmdlet verwendet werden, um eine JSON-formatierte Zeichenfolge in ein JSON-Objekt zu konvertieren, das problemlos in PowerShell verwaltet oder an ein anderes Programm oder einen Webdienst gesendet wird, die auf die JSON-Eingabe zugreifen</span><span class="sxs-lookup"><span data-stu-id="6e2de-111">The verified string can then be used with the `ConvertFrom-Json` cmdlet convert a JSON-formatted string to a JSON object, which is easily managed in PowerShell or sent to another program or web service that access JSON input.</span></span>

<span data-ttu-id="6e2de-112">Viele Websites verwenden JSON statt XML, um Daten für die Kommunikation zwischen Servern und webbasierten Apps zu serialisieren.</span><span class="sxs-lookup"><span data-stu-id="6e2de-112">Many web sites use JSON instead of XML to serialize data for communication between servers and web-based apps.</span></span>

<span data-ttu-id="6e2de-113">Dieses Cmdlet wurde in PowerShell 6,1 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="6e2de-113">This cmdlet was introduced in PowerShell 6.1</span></span>

## <span data-ttu-id="6e2de-114">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="6e2de-114">EXAMPLES</span></span>

### <span data-ttu-id="6e2de-115">Beispiel 1: testen, ob ein Objekt gültiges JSON ist</span><span class="sxs-lookup"><span data-stu-id="6e2de-115">Example 1: Test if an object is valid JSON</span></span>

<span data-ttu-id="6e2de-116">In diesem Beispiel wird getestet, ob die Eingabe Zeichenfolge ein gültiges JSON-Dokument ist.</span><span class="sxs-lookup"><span data-stu-id="6e2de-116">This example tests whether the input string is a valid JSON document.</span></span>

```powershell
"{'name': 'Ashley', 'age': 25}" | Test-Json
```

```Output
True
```

### <span data-ttu-id="6e2de-117">Beispiel 2: Testen eines Objekts mit einem bereitgestellten Schema</span><span class="sxs-lookup"><span data-stu-id="6e2de-117">Example 2: Test an object against a provided schema</span></span>

<span data-ttu-id="6e2de-118">In diesem Beispiel wird eine Zeichenfolge mit einem JSON-Schema angenommen und mit einer Eingabe Zeichenfolge verglichen.</span><span class="sxs-lookup"><span data-stu-id="6e2de-118">This example takes a string containing a JSON schema and compares it to an input string.</span></span>

```powershell
$schema = @'
{
  "definitions": {},
  "$schema": "http://json-schema.org/draft-07/schema#",
  "$id": "http://example.com/root.json",
  "type": "object",
  "title": "The Root Schema",
  "required": [
    "name",
    "age"
  ],
  "properties": {
    "name": {
      "$id": "#/properties/name",
      "type": "string",
      "title": "The Name Schema",
      "default": "",
      "examples": [
        "Ashley"
      ],
      "pattern": "^(.*)$"
    },
    "age": {
      "$id": "#/properties/age",
      "type": "integer",
      "title": "The Age Schema",
      "default": 0,
      "examples": [
        25
      ]
    }
  }
}
'@
"{'name': 'Ashley', 'age': '25'}" | Test-Json -Schema $schema
```

```Output
Test-Json : IntegerExpected: #/age
At line:1 char:37
+ "{'name': 'Ashley', 'age': '25'}" | Test-Json -Schema $schema
+                                     ~~~~~~~~~~~~~~~~~~~~~~~~~
+ CategoryInfo          : InvalidData: (:) [Test-Json], Exception
+ FullyQualifiedErrorId : InvalidJsonAgainstSchema,Microsoft.PowerShell.Commands.TestJsonCommand
False
```

<span data-ttu-id="6e2de-119">In diesem Beispiel erhalten wir eine Fehlermeldung, da das Schema eine ganze Zahl für das **Alter** erwartet, die JSON-Eingabe, die wir getestet haben, stattdessen einen Zeichen folgen Wert verwendet.</span><span class="sxs-lookup"><span data-stu-id="6e2de-119">In this example, we get an error because the schema expects an integer for **age** but the JSON input we tested uses a string value instead.</span></span>

<span data-ttu-id="6e2de-120">Weitere Informationen finden Sie unter [JSON-Schema](https://json-schema.org/).</span><span class="sxs-lookup"><span data-stu-id="6e2de-120">For more information, see [JSON Schema](https://json-schema.org/).</span></span>

### <span data-ttu-id="6e2de-121">Beispiel 3: Testen eines Objekts anhand eines Schemas aus einer Datei</span><span class="sxs-lookup"><span data-stu-id="6e2de-121">Example 3: Test an object against a schema from file</span></span>

<span data-ttu-id="6e2de-122">Das JSON-Schema kann mithilfe des Schlüssel Worts auf Definitionen verweisen `$ref` .</span><span class="sxs-lookup"><span data-stu-id="6e2de-122">JSON schema can reference definitions using `$ref` keyword.</span></span> <span data-ttu-id="6e2de-123">Der `$ref` kann in einen URI aufgelöst werden, der auf eine andere Datei verweist.</span><span class="sxs-lookup"><span data-stu-id="6e2de-123">The `$ref` can resolve to a URI that references another file.</span></span> <span data-ttu-id="6e2de-124">Der `SchemaFile` -Parameter akzeptiert den literalpfad zur JSON-Schema Datei und ermöglicht die Validierung von JSON-Dateien anhand solcher Schemas.</span><span class="sxs-lookup"><span data-stu-id="6e2de-124">The `SchemaFile` parameter accepts literal path to the JSON schema file and allows JSON files to be validated against such schemas.</span></span>

<span data-ttu-id="6e2de-125">In diesem Beispiel haben wir `schema.json` die Datei, auf die verweist `definitions.json` .</span><span class="sxs-lookup"><span data-stu-id="6e2de-125">In this example we have `schema.json` file which references `definitions.json`.</span></span>

```powershell
PS> Get-Content schema.json

{
  "description":"A person",
  "type":"object",
  "properties":{
    "name":{
      "$ref":"definitions.json#/definitions/name"
    },
    "hobbies":{
      "$ref":"definitions.json#/definitions/hobbies"
    }
  }
}

PS> Get-Content definitions.json

{
  "definitions":{
    "name":{
      "type":"string"
    },
    "hobbies":{
      "type":"array",
      "items":{
        "type":"string"
      }
    }
  }
}

'{"name": "James", "hobbies": [".NET", "Blogging"]}' | Test-Json -SchemaFile 'schema.json'
```

```Output
True
```

<span data-ttu-id="6e2de-126">Weitere Informationen finden Sie unter [strukturieren eines komplexen Schemas](https://json-schema.org/understanding-json-schema/structuring.html).</span><span class="sxs-lookup"><span data-stu-id="6e2de-126">For more information, see [Structuring a complex schema](https://json-schema.org/understanding-json-schema/structuring.html).</span></span>

## <span data-ttu-id="6e2de-127">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="6e2de-127">PARAMETERS</span></span>

### <span data-ttu-id="6e2de-128">-JSON</span><span class="sxs-lookup"><span data-stu-id="6e2de-128">-Json</span></span>

<span data-ttu-id="6e2de-129">Gibt die JSON-Zeichenfolge an, deren Gültigkeit überprüft werden soll.</span><span class="sxs-lookup"><span data-stu-id="6e2de-129">Specifies the JSON string to test for validity.</span></span> <span data-ttu-id="6e2de-130">Geben Sie eine Variable ein, die die Zeichenfolge enthält, oder geben Sie einen Befehl oder Ausdruck ein, der die Zeichenfolge abruft.</span><span class="sxs-lookup"><span data-stu-id="6e2de-130">Enter a variable that contains the string, or type a command or expression that gets the string.</span></span> <span data-ttu-id="6e2de-131">Sie können eine Zeichenfolge auch über die Pipeline an senden `Test-Json` .</span><span class="sxs-lookup"><span data-stu-id="6e2de-131">You can also pipe a string to `Test-Json`.</span></span>

<span data-ttu-id="6e2de-132">Der **JSON** -Parameter ist erforderlich.</span><span class="sxs-lookup"><span data-stu-id="6e2de-132">The **Json** parameter is required.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="6e2de-133">-Schema</span><span class="sxs-lookup"><span data-stu-id="6e2de-133">-Schema</span></span>

<span data-ttu-id="6e2de-134">Gibt ein Schema an, mit dem die JSON-Eingabe überprüft werden soll.</span><span class="sxs-lookup"><span data-stu-id="6e2de-134">Specifies a Schema to validate the JSON input against.</span></span> <span data-ttu-id="6e2de-135">Wenn übergeben `Test-Json` wird, wird überprüft, ob die JSON-Eingabe der durch den **Schema** -Parameter angegebenen Spezifikation entspricht und nur dann zurückgegeben wird, `$True` Wenn die Eingabe dem bereitgestellten Schema entspricht.</span><span class="sxs-lookup"><span data-stu-id="6e2de-135">If passed `Test-Json` will validate that the Json input conforms to the spec specified by the **Schema** parameter and return `$True` only if the input conforms to the provided Schema.</span></span>

<span data-ttu-id="6e2de-136">Weitere Informationen finden Sie unter [JSON-Schema](https://json-schema.org/).</span><span class="sxs-lookup"><span data-stu-id="6e2de-136">For more information, see [JSON Schema](https://json-schema.org/).</span></span>

```yaml
Type: System.String
Parameter Sets: SchemaString
Aliases:

Required: False
Position: 2
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="6e2de-137">-SchemaFile</span><span class="sxs-lookup"><span data-stu-id="6e2de-137">-SchemaFile</span></span>

<span data-ttu-id="6e2de-138">Gibt eine Schema Datei an, die zum Überprüfen der JSON-Eingabe verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="6e2de-138">Specifies a schema file used to validate the JSON input.</span></span> <span data-ttu-id="6e2de-139">Bei Verwendung von wird `Test-Json` nur dann zurückgegeben, `$True` Wenn die JSON-Eingabe dem Schema entspricht, das in der durch den **SchemaFile** -Parameter angegebenen Datei definiert ist.</span><span class="sxs-lookup"><span data-stu-id="6e2de-139">When used, the `Test-Json` returns `$True` only if the JSON input conforms to the Schema defined in the file specified by the **SchemaFile** parameter.</span></span>

<span data-ttu-id="6e2de-140">Weitere Informationen finden Sie unter [JSON-Schema](https://json-schema.org/).</span><span class="sxs-lookup"><span data-stu-id="6e2de-140">For more information, see [JSON Schema](https://json-schema.org/).</span></span>

```yaml
Type: System.String
Parameter Sets: SchemaFile
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="6e2de-141">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="6e2de-141">CommonParameters</span></span>

<span data-ttu-id="6e2de-142">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="6e2de-142">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="6e2de-143">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="6e2de-143">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="6e2de-144">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="6e2de-144">INPUTS</span></span>

### <span data-ttu-id="6e2de-145">System.String</span><span class="sxs-lookup"><span data-stu-id="6e2de-145">System.String</span></span>

<span data-ttu-id="6e2de-146">Sie können eine JSON-Zeichenfolge an übergeben `Test-Json` .</span><span class="sxs-lookup"><span data-stu-id="6e2de-146">You can pipe a JSON string to `Test-Json`.</span></span>

## <span data-ttu-id="6e2de-147">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="6e2de-147">OUTPUTS</span></span>

### <span data-ttu-id="6e2de-148">Boolesch</span><span class="sxs-lookup"><span data-stu-id="6e2de-148">Boolean</span></span>

## <span data-ttu-id="6e2de-149">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="6e2de-149">NOTES</span></span>

<span data-ttu-id="6e2de-150">Das- `Test-Json` Cmdlet wird mithilfe der [njsonschema-Klasse](https://github.com/RSuter/NJsonSchema)implementiert.</span><span class="sxs-lookup"><span data-stu-id="6e2de-150">The `Test-Json` cmdlet is implemented by using the [NJsonSchema Class](https://github.com/RSuter/NJsonSchema).</span></span>

## <span data-ttu-id="6e2de-151">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="6e2de-151">RELATED LINKS</span></span>

<span data-ttu-id="6e2de-152">[Eine Einführung in JavaScript Object Notation (JSON) in JavaScript und .net](/previous-versions/dotnet/articles/bb299886(v=msdn.10))</span><span class="sxs-lookup"><span data-stu-id="6e2de-152">[An Introduction to JavaScript Object Notation (JSON) in JavaScript and .NET](/previous-versions/dotnet/articles/bb299886(v=msdn.10))</span></span>

[<span data-ttu-id="6e2de-153">Weitere JSON-Schema Details</span><span class="sxs-lookup"><span data-stu-id="6e2de-153">Additional JSON Schema Details</span></span>](https://json-schema.org/)

[<span data-ttu-id="6e2de-154">ConvertTo-Json</span><span class="sxs-lookup"><span data-stu-id="6e2de-154">ConvertTo-Json</span></span>](ConvertTo-Json.md)

[<span data-ttu-id="6e2de-155">Invoke-WebRequest</span><span class="sxs-lookup"><span data-stu-id="6e2de-155">Invoke-WebRequest</span></span>](Invoke-WebRequest.md)

[<span data-ttu-id="6e2de-156">Invoke-RestMethod</span><span class="sxs-lookup"><span data-stu-id="6e2de-156">Invoke-RestMethod</span></span>](Invoke-RestMethod.md)