---
title: ListItem-Element für ListItems für ListControl (Format) | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: e72a887e8bd1f93bacb663e3079eeaec34bdfa51
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87785675"
---
# <a name="listitem-element-for-listitems-for-listcontrol-format"></a><span data-ttu-id="f61dc-102">Element „ListItem“ für ListItems für ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="f61dc-102">ListItem Element for ListItems for ListControl (Format)</span></span>

<span data-ttu-id="f61dc-103">Definiert die Eigenschaft oder das Skript, dessen Wert in einer Zeile der Listenansicht angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="f61dc-103">Defines the property or script whose value is displayed in a row of the list view.</span></span>

<span data-ttu-id="f61dc-104">Configuration-Element (Format) viewdefinitions-Element (Format) Ansichts Element (Format) ListControl-Element (Format) ListEntries-Element für ListControl (Format) ListEntry-Element für ListControl (Format) ListItems-Element für ListControl (Format) ListItem für ListControl-Element (Format)</span><span class="sxs-lookup"><span data-stu-id="f61dc-104">Configuration Element (Format) ViewDefinitions Element (Format) View Element (Format) ListControl Element (Format) ListEntries Element for ListControl (Format) ListEntry Element for ListControl (Format) ListItems Element for ListControl (Format) ListItem for ListControl Element (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="f61dc-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="f61dc-105">Syntax</span></span>

```xml
<ListItem>
  <PropertyName>PropertyToDisplay</PropertyName>
  <ScriptBlock>ScriptToExecute</ScriptBlock>
  <Label>LabelToDisplay</Label>
  <FormatString>FormatPattern</FormatString>
  <ItemSelectionCondition>...</ItemSelectionCondition>
</ListItem>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="f61dc-106">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="f61dc-106">Attributes and Elements</span></span>

<span data-ttu-id="f61dc-107">In den folgenden Abschnitten werden die Attribute, die untergeordneten Elemente und das übergeordnete Element des- `ListItem` Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="f61dc-107">The following sections describe the attributes, child elements, and parent element of the `ListItem` element.</span></span> <span data-ttu-id="f61dc-108">Es kann nur eine Eigenschaft oder ein Skript angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="f61dc-108">Only one property or script can be specified.</span></span>

### <a name="attributes"></a><span data-ttu-id="f61dc-109">Attribute</span><span class="sxs-lookup"><span data-stu-id="f61dc-109">Attributes</span></span>

<span data-ttu-id="f61dc-110">Keine</span><span class="sxs-lookup"><span data-stu-id="f61dc-110">None</span></span>

### <a name="child-elements"></a><span data-ttu-id="f61dc-111">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="f61dc-111">Child Elements</span></span>

|<span data-ttu-id="f61dc-112">Element</span><span class="sxs-lookup"><span data-stu-id="f61dc-112">Element</span></span>|<span data-ttu-id="f61dc-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f61dc-113">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="f61dc-114">FormatString-Element für ListItem für ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="f61dc-114">FormatString Element for ListItem for ListControl (Format)</span></span>](./formatstring-element-for-listitem-for-listcontrol-format.md)|<span data-ttu-id="f61dc-115">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="f61dc-115">Optional element.</span></span><br /><br /> <span data-ttu-id="f61dc-116">Gibt eine Format Zeichenfolge an, die definiert, wie der Eigenschafts-oder Skript Wert angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="f61dc-116">Specifies a format string that defines how the property or script value is displayed.</span></span>|
|[<span data-ttu-id="f61dc-117">Element „ItemSelectionCondition“ für ListItem für ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="f61dc-117">ItemSelectionCondition Element for ListItem for ListControl (Format)</span></span>](./itemselectioncondition-element-for-listitem-for-listcontrol-format.md)|<span data-ttu-id="f61dc-118">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="f61dc-118">Optional element.</span></span><br /><br /> <span data-ttu-id="f61dc-119">Definiert die Bedingung, die vorhanden sein muss, damit dieses Listenelement verwendet werden muss.</span><span class="sxs-lookup"><span data-stu-id="f61dc-119">Defines the condition that must exist for this list item to be used.</span></span>|
|[<span data-ttu-id="f61dc-120">Element „Label“ für ListItem für ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="f61dc-120">Label Element for ListItem for ListControl (Format)</span></span>](./label-element-for-listitem-for-listcontrol-format.md)|<span data-ttu-id="f61dc-121">Optionales Element</span><span class="sxs-lookup"><span data-stu-id="f61dc-121">Optional element</span></span><br /><br /> <span data-ttu-id="f61dc-122">Gibt die Bezeichnung an, die auf der linken Seite des Eigenschafts-oder Skript Werts in der Zeile angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="f61dc-122">Specifies the label that is displayed to the left of the property or script value in the row.</span></span>|
|[<span data-ttu-id="f61dc-123">Element „PropertyName“ für ListItem für ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="f61dc-123">PropertyName Element for ListItem for ListControl (Format)</span></span>](./propertyname-element-for-listitem-for-listcontrol-format.md)|<span data-ttu-id="f61dc-124">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="f61dc-124">Optional element.</span></span><br /><br /> <span data-ttu-id="f61dc-125">Gibt die .net-Eigenschaft an, deren Wert in der Zeile angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="f61dc-125">Specifies the .NET property whose value is displayed in the row.</span></span>|
|[<span data-ttu-id="f61dc-126">Element „ScriptBlock“ für ListItem für ListControl (Format)</span><span class="sxs-lookup"><span data-stu-id="f61dc-126">ScriptBlock Element for ListItem for ListControl (Format)</span></span>](./scriptblock-element-for-listitem-for-listcontrol-format.md)|<span data-ttu-id="f61dc-127">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="f61dc-127">Optional element.</span></span><br /><br /> <span data-ttu-id="f61dc-128">Gibt das Skript an, dessen Wert in der Zeile angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="f61dc-128">Specifies the script whose value is displayed in the row.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="f61dc-129">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="f61dc-129">Parent Elements</span></span>

|<span data-ttu-id="f61dc-130">Element</span><span class="sxs-lookup"><span data-stu-id="f61dc-130">Element</span></span>|<span data-ttu-id="f61dc-131">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f61dc-131">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="f61dc-132">ListItems-Element für Listen Steuer Element (Format)</span><span class="sxs-lookup"><span data-stu-id="f61dc-132">ListItems Element for List Control (Format)</span></span>](./listitems-element-for-listentry-for-listcontrol-format.md)|<span data-ttu-id="f61dc-133">Definiert die Eigenschaften und Skripts, deren Werte in der Listenansicht angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="f61dc-133">Defines the properties and scripts whose values are displayed in the list view.</span></span>|

## <a name="remarks"></a><span data-ttu-id="f61dc-134">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="f61dc-134">Remarks</span></span>

<span data-ttu-id="f61dc-135">Weitere Informationen zu den Komponenten einer Listenansicht finden Sie unter [Erstellen einer Listenansicht](./creating-a-list-view.md).</span><span class="sxs-lookup"><span data-stu-id="f61dc-135">For more information about the components of a list view, see [Creating a List View](./creating-a-list-view.md).</span></span>

## <a name="example"></a><span data-ttu-id="f61dc-136">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f61dc-136">Example</span></span>

<span data-ttu-id="f61dc-137">Dieses Beispiel zeigt die XML-Elemente, die drei Zeilen der Listenansicht definieren.</span><span class="sxs-lookup"><span data-stu-id="f61dc-137">This example shows the XML elements that define three rows of the list view.</span></span> <span data-ttu-id="f61dc-138">Die ersten beiden Zeilen zeigen den Wert einer .net-Eigenschaft an, und die letzte Zeile zeigt einen Wert an, der von einem Skript generiert wurde.</span><span class="sxs-lookup"><span data-stu-id="f61dc-138">The first two rows display the value of a .NET property, and the last row displays a value generated by a script.</span></span>

```xml
<ListEntry>
    <ListItems>
      <ListItem>
        <Label>Property1: </Label>
        <PropertyName>DotNetProperty1</PropertyName>
      </ListItem>
      <ListItem>
        <PropertyName>DotNetProperty2</PropertyName>
      </ListItem>
      <ListItem>
        <ScriptBlock>$_.ProcessName + ":" $_.Id</ScriptBlock>
      </ListItem>
    </ListItems>
</ListEntry>

```

## <a name="see-also"></a><span data-ttu-id="f61dc-139">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="f61dc-139">See Also</span></span>

[<span data-ttu-id="f61dc-140">ListItems-Element (Format)</span><span class="sxs-lookup"><span data-stu-id="f61dc-140">ListItems Element (Format)</span></span>](./listitems-element-for-listentry-for-listcontrol-format.md)

[<span data-ttu-id="f61dc-141">FormatString-Element für ListItem (Format)</span><span class="sxs-lookup"><span data-stu-id="f61dc-141">FormatString Element for ListItem (Format)</span></span>](./formatstring-element-for-listitem-for-listcontrol-format.md)

[<span data-ttu-id="f61dc-142">Label-Element für ListItem (Format)</span><span class="sxs-lookup"><span data-stu-id="f61dc-142">Label Element for ListItem (Format)</span></span>](./label-element-for-listitem-for-listcontrol-format.md)

[<span data-ttu-id="f61dc-143">PropertyName-Element für ListItem (Format)</span><span class="sxs-lookup"><span data-stu-id="f61dc-143">PropertyName Element for ListItem (Format)</span></span>](./propertyname-element-for-listitem-for-listcontrol-format.md)

[<span data-ttu-id="f61dc-144">ScriptBlock-Element für ListItem (Format)</span><span class="sxs-lookup"><span data-stu-id="f61dc-144">ScriptBlock Element for ListItem (Format)</span></span>](./scriptblock-element-for-listitem-for-listcontrol-format.md)

[<span data-ttu-id="f61dc-145">Erstellen einer Listenansicht</span><span class="sxs-lookup"><span data-stu-id="f61dc-145">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="f61dc-146">Schreiben einer Windows PowerShell-Formatierungs-und-Typen Datei</span><span class="sxs-lookup"><span data-stu-id="f61dc-146">Writing a Windows PowerShell Formatting and Types File</span></span>](./writing-a-powershell-formatting-file.md)
