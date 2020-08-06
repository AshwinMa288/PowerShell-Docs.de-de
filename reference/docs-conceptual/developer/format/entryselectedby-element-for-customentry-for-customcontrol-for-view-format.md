---
title: Entryselectedby-Element für customentry für CustomControl für Ansicht (Format) | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: 4d4900cefb0d499397fc9dff7e037ce0a541f72f
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87783686"
---
# <a name="entryselectedby-element-for-customentry-for-customcontrol-for-view-format"></a><span data-ttu-id="79b9f-102">Element „EntrySelectedBy“ für CustomEntry für CustomControl für View (Format)</span><span class="sxs-lookup"><span data-stu-id="79b9f-102">EntrySelectedBy Element for CustomEntry for CustomControl for View (Format)</span></span>

<span data-ttu-id="79b9f-103">Definiert die .NET-Typen, die diesen benutzerdefinierten Eintrag verwenden, oder die Bedingung, die für die Verwendung dieses Eintrags vorhanden sein muss.</span><span class="sxs-lookup"><span data-stu-id="79b9f-103">Defines the .NET types that use this custom entry or the condition that must exist for this entry to be used.</span></span>

<span data-ttu-id="79b9f-104">Configuration-Element (Format) viewdefinitions-Element (Format) View-Element (Format) CustomControl-Element (Format) customentries-Element für CustomControl für View (Format) customentry-Element für customentries für View (Format) entryselectedby-Element für customentry for View (Format)</span><span class="sxs-lookup"><span data-stu-id="79b9f-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) CustomControl Element (Format) CustomEntries Element for CustomControl for View (Format) CustomEntry Element for CustomEntries for View (Format) EntrySelectedBy Element for CustomEntry for View (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="79b9f-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="79b9f-105">Syntax</span></span>

```xml
<EntrySelectedBy>
  <TypeName>Nameof.NetType</TypeName>
  <SelectionSetName>NameofSelectionSet</SelectionSetName>
  <SelectionCondition>...</SelectionCondition>
</EntrySelectedBy>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="79b9f-106">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="79b9f-106">Attributes and Elements</span></span>

<span data-ttu-id="79b9f-107">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und das übergeordnete Element des- `EntrySelectedBy` Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="79b9f-107">The following sections describe attributes, child elements, and the parent element of the `EntrySelectedBy` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="79b9f-108">Attribute</span><span class="sxs-lookup"><span data-stu-id="79b9f-108">Attributes</span></span>

<span data-ttu-id="79b9f-109">Keine</span><span class="sxs-lookup"><span data-stu-id="79b9f-109">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="79b9f-110">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="79b9f-110">Child Elements</span></span>

|<span data-ttu-id="79b9f-111">Element</span><span class="sxs-lookup"><span data-stu-id="79b9f-111">Element</span></span>|<span data-ttu-id="79b9f-112">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="79b9f-112">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="79b9f-113">Selectioncondition-Element für entryselectedby für customentry (Format)</span><span class="sxs-lookup"><span data-stu-id="79b9f-113">SelectionCondition Element for EntrySelectedBy for CustomEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-customcontrol-format.md)|<span data-ttu-id="79b9f-114">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="79b9f-114">Optional element.</span></span><br /><br /> <span data-ttu-id="79b9f-115">Definiert die Bedingung, die vorhanden sein muss, damit diese Definition verwendet werden muss.</span><span class="sxs-lookup"><span data-stu-id="79b9f-115">Defines the condition that must exist for this definition to be used.</span></span>|
|[<span data-ttu-id="79b9f-116">Selectionsetname-Element für entryselectedby für customentry (Format)</span><span class="sxs-lookup"><span data-stu-id="79b9f-116">SelectionSetName Element for EntrySelectedBy for CustomEntry (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-customcontrol-for-view-format.md)|<span data-ttu-id="79b9f-117">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="79b9f-117">Optional element.</span></span><br /><br /> <span data-ttu-id="79b9f-118">Gibt einen Satz von .NET-Typen an, die diese Definition der Steuerelement Ansicht verwenden.</span><span class="sxs-lookup"><span data-stu-id="79b9f-118">Specifies a set of .NET types that use this definition of the control view.</span></span>|
|[<span data-ttu-id="79b9f-119">Typname-Element für entryselectedby für customentry (Format)</span><span class="sxs-lookup"><span data-stu-id="79b9f-119">TypeName Element for EntrySelectedBy for CustomEntry (Format)</span></span>](./typename-element-for-selectioncondition-for-customcontrol-for-view-format.md)|<span data-ttu-id="79b9f-120">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="79b9f-120">Optional element.</span></span><br /><br /> <span data-ttu-id="79b9f-121">Gibt einen .NET-Typ an, der diese Definition der Steuerelement Ansicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="79b9f-121">Specifies a .NET type that uses this definition of the control view.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="79b9f-122">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="79b9f-122">Parent Elements</span></span>

|<span data-ttu-id="79b9f-123">Element</span><span class="sxs-lookup"><span data-stu-id="79b9f-123">Element</span></span>|<span data-ttu-id="79b9f-124">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="79b9f-124">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="79b9f-125">Customentry-Element für customentries für View (Format)</span><span class="sxs-lookup"><span data-stu-id="79b9f-125">CustomEntry Element for CustomEntries for View (Format)</span></span>](./customentry-element-for-customentries-for-customcontrol-for-view-format.md)|<span data-ttu-id="79b9f-126">Definiert die Steuerelemente, die von bestimmten .NET-Objekten verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="79b9f-126">Defines the controls used by specific .NET objects.</span></span>|

## <a name="remarks"></a><span data-ttu-id="79b9f-127">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="79b9f-127">Remarks</span></span>

<span data-ttu-id="79b9f-128">Sie müssen mindestens einen Typ, einen Auswahl Satz oder eine Auswahlbedingung für einen Eintrag angeben.</span><span class="sxs-lookup"><span data-stu-id="79b9f-128">You must specify at least one type, selection set, or selection condition for an entry.</span></span> <span data-ttu-id="79b9f-129">Es gibt keine maximale Beschränkung für die Anzahl der untergeordneten Elemente, die Sie verwenden können.</span><span class="sxs-lookup"><span data-stu-id="79b9f-129">There is no maximum limit to the number of child elements that you can use.</span></span>

<span data-ttu-id="79b9f-130">Auswahl Bedingungen werden verwendet, um eine Bedingung zu definieren, die für den zu verwendenden Eintrag vorhanden sein muss, z. b. Wenn ein Objekt eine bestimmte Eigenschaft hat oder wenn ein bestimmter Eigenschafts Wert oder ein Skript als ausgewertet wird `true` .</span><span class="sxs-lookup"><span data-stu-id="79b9f-130">Selection conditions are used to define a condition that must exist for the entry to be used, such as when an object has a specific property or when a specific property value or script evaluates to `true`.</span></span> <span data-ttu-id="79b9f-131">Weitere Informationen zu Auswahl Bedingungen finden Sie unter [Definieren von Bedingungen für die Verwendung eines Ansichts Eintrags oder eines Elements](./defining-conditions-for-displaying-data.md).</span><span class="sxs-lookup"><span data-stu-id="79b9f-131">For more information about selection conditions, see [Defining Conditions for when a View Entry or Item is Used](./defining-conditions-for-displaying-data.md).</span></span>

<span data-ttu-id="79b9f-132">Weitere Informationen zu den Komponenten einer benutzerdefinierten Steuerelement Ansicht finden Sie unter [benutzerdefinierte Steuerelement Ansicht](./creating-custom-controls.md).</span><span class="sxs-lookup"><span data-stu-id="79b9f-132">For more information about the components of a custom control view, see [Custom Control View](./creating-custom-controls.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="79b9f-133">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="79b9f-133">See Also</span></span>

[<span data-ttu-id="79b9f-134">Selectioncondition-Element für entryselectedby für customentry (Format)</span><span class="sxs-lookup"><span data-stu-id="79b9f-134">SelectionCondition Element for EntrySelectedBy for CustomEntry (Format)</span></span>](./selectioncondition-element-for-entryselectedby-for-customcontrol-format.md)

[<span data-ttu-id="79b9f-135">Selectionsetname-Element für entryselectedby für customentry (Format)</span><span class="sxs-lookup"><span data-stu-id="79b9f-135">SelectionSetName Element for EntrySelectedBy for CustomEntry (Format)</span></span>](./selectionsetname-element-for-entryselectedby-for-customcontrol-for-view-format.md)

[<span data-ttu-id="79b9f-136">Typname-Element für entryselectedby für customentry (Format)</span><span class="sxs-lookup"><span data-stu-id="79b9f-136">TypeName Element for EntrySelectedBy for CustomEntry (Format)</span></span>](./typename-element-for-selectioncondition-for-customcontrol-for-view-format.md)

[<span data-ttu-id="79b9f-137">Customentry-Element für customentries für View (Format)</span><span class="sxs-lookup"><span data-stu-id="79b9f-137">CustomEntry Element for CustomEntries for View (Format)</span></span>](./customentry-element-for-customentries-for-customcontrol-for-view-format.md)

[<span data-ttu-id="79b9f-138">Benutzerdefinierte Steuerelement Ansicht</span><span class="sxs-lookup"><span data-stu-id="79b9f-138">Custom Control View</span></span>](./creating-custom-controls.md)

[<span data-ttu-id="79b9f-139">Schreiben einer PowerShell-Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="79b9f-139">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
