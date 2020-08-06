---
title: ScriptBlock-Element für selectioncondition für entryselectedby für widecontrol (Format) | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: c8f2223d4a1217786a930eb82390c24b81d2f72e
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87787613"
---
# <a name="scriptblock-element-for-selectioncondition-for-entryselectedby-for-widecontrol-format"></a><span data-ttu-id="9d2ee-102">Element „ScriptBlock“ für SelectionCondition für EntrySelectedBy für WideControl (Format)</span><span class="sxs-lookup"><span data-stu-id="9d2ee-102">ScriptBlock Element for SelectionCondition for EntrySelectedBy for WideControl (Format)</span></span>

<span data-ttu-id="9d2ee-103">Gibt das Skript an, das die Bedingung auslöst.</span><span class="sxs-lookup"><span data-stu-id="9d2ee-103">Specifies the script that triggers the condition.</span></span> <span data-ttu-id="9d2ee-104">Wenn dieses Skript als ausgewertet wird `true` , wird die Bedingung erfüllt, und die Breite Eingabe Definition wird verwendet.</span><span class="sxs-lookup"><span data-stu-id="9d2ee-104">When this script is evaluated to `true`, the condition is met, and the wide entry definition is used.</span></span>

<span data-ttu-id="9d2ee-105">Configuration-Element (Format) viewdefinitions-Element (Format) Ansichts Element (Format) widecontrol-Element (Format) wideentries-Element (Format) wideentry-Element (Format) entryselectedby-Element für wideentry (Format) selectioncondition-Element für entryselectedby für wideentry (Format) ScriptBlock-Element für selectioncondition für entryselectedby für wideentry (Format)</span><span class="sxs-lookup"><span data-stu-id="9d2ee-105">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) WideControl Element (Format) WideEntries Element (Format) WideEntry Element (Format) EntrySelectedBy Element for WideEntry (Format) SelectionCondition Element for EntrySelectedBy for WideEntry (Format) ScriptBlock Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="9d2ee-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="9d2ee-106">Syntax</span></span>

```xml
<ScriptBlock>ScriptToEvaluate</ScriptBlock>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="9d2ee-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="9d2ee-107">Attributes and Elements</span></span>

<span data-ttu-id="9d2ee-108">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und das übergeordnete Element des- `ScriptBlock` Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="9d2ee-108">The following sections describe attributes, child elements, and the parent element of the `ScriptBlock` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="9d2ee-109">Attribute</span><span class="sxs-lookup"><span data-stu-id="9d2ee-109">Attributes</span></span>

<span data-ttu-id="9d2ee-110">Keine</span><span class="sxs-lookup"><span data-stu-id="9d2ee-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="9d2ee-111">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="9d2ee-111">Child Elements</span></span>

<span data-ttu-id="9d2ee-112">Keine</span><span class="sxs-lookup"><span data-stu-id="9d2ee-112">None.</span></span>

### <a name="parent-elements"></a><span data-ttu-id="9d2ee-113">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="9d2ee-113">Parent Elements</span></span>

|<span data-ttu-id="9d2ee-114">Element</span><span class="sxs-lookup"><span data-stu-id="9d2ee-114">Element</span></span>|<span data-ttu-id="9d2ee-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9d2ee-115">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="9d2ee-116">Selectioncondition-Element für entryselectedby für wideentry (Format)</span><span class="sxs-lookup"><span data-stu-id="9d2ee-116">SelectionCondition Element for EntrySelectedBy for WideEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md)|<span data-ttu-id="9d2ee-117">Definiert die Bedingung, die vorhanden sein muss, damit diese Definition verwendet werden muss.</span><span class="sxs-lookup"><span data-stu-id="9d2ee-117">Defines the condition that must exist for this definition to be used.</span></span>|

## <a name="text-value"></a><span data-ttu-id="9d2ee-118">Textwert</span><span class="sxs-lookup"><span data-stu-id="9d2ee-118">Text Value</span></span>

<span data-ttu-id="9d2ee-119">Geben Sie das auszuwertende Skript an.</span><span class="sxs-lookup"><span data-stu-id="9d2ee-119">Specify the script that is evaluated.</span></span>

## <a name="remarks"></a><span data-ttu-id="9d2ee-120">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="9d2ee-120">Remarks</span></span>

<span data-ttu-id="9d2ee-121">Die Auswahlbedingung muss mindestens ein Skript oder einen Eigenschaftsnamen angeben, der ausgewertet werden soll, kann jedoch nicht beides angeben.</span><span class="sxs-lookup"><span data-stu-id="9d2ee-121">The selection condition must specify at least one script or property name to evaluate, but cannot specify both.</span></span> <span data-ttu-id="9d2ee-122">Weitere Informationen zum Verwenden von Auswahl Bedingungen finden Sie unter [Definieren von Bedingungen für die Anzeige von Daten](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="9d2ee-122">For more information about how to use selection conditions, see [Defining Conditions for when Data is Displayed](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="9d2ee-123">Weitere Informationen zu anderen Komponenten einer breiten Ansicht finden Sie unter [Wide View](./creating-a-wide-view.md).</span><span class="sxs-lookup"><span data-stu-id="9d2ee-123">For more information about other components of a wide view, see [Wide View](./creating-a-wide-view.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="9d2ee-124">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="9d2ee-124">See Also</span></span>

[<span data-ttu-id="9d2ee-125">Erstellen einer breiten Ansicht</span><span class="sxs-lookup"><span data-stu-id="9d2ee-125">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="9d2ee-126">Definieren von Bedingungen für die Anzeige von Daten</span><span class="sxs-lookup"><span data-stu-id="9d2ee-126">Defining Conditions for When Data Is Displayed</span></span>](./defining-conditions-for-displaying-data.md)

[<span data-ttu-id="9d2ee-127">Element „PropertyName“ für SelectionCondition für EntrySelectedBy für WideEntry (Format)</span><span class="sxs-lookup"><span data-stu-id="9d2ee-127">PropertyName Element for SelectionCondition for EntrySelectedBy for WideEntry (Format)</span></span>](./propertyname-element-for-selectioncondition-for-entryselectedby-for-wideentry-format.md)

[<span data-ttu-id="9d2ee-128">Selectioncondition-Element für entryselectedby für wideentry (Format)</span><span class="sxs-lookup"><span data-stu-id="9d2ee-128">SelectionCondition Element for EntrySelectedBy for WideEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-widecontrol-format.md)

[<span data-ttu-id="9d2ee-129">Schreiben einer PowerShell-Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="9d2ee-129">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
