---
title: Viewdefinitions-Element (Format) | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: a108c4f8b03e3dec3905181b390aee2c82ab0028
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87772483"
---
# <a name="viewdefinitions-element-format"></a><span data-ttu-id="6899b-102">Element „ViewDefinitions“ (Format)</span><span class="sxs-lookup"><span data-stu-id="6899b-102">ViewDefinitions Element (Format)</span></span>

<span data-ttu-id="6899b-103">Definiert die Sichten, die zum Anzeigen von .NET-Objekten verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="6899b-103">Defines the views used to display .NET objects.</span></span> <span data-ttu-id="6899b-104">Diese Sichten können die Eigenschaften und Skript Werte eines Objekts in einem Tabellenformat, einem Listenformat, einem breiten Format und einem benutzerdefinierten Steuerelement Format anzeigen.</span><span class="sxs-lookup"><span data-stu-id="6899b-104">These views can display the properties and script values of an object  in a table format, list format, wide format, and custom control format.</span></span>

<span data-ttu-id="6899b-105">Configuration-Element (Format) viewdefinitions (Format XML)-Element</span><span class="sxs-lookup"><span data-stu-id="6899b-105">Configuration Element (Format) ViewDefinitions (Format XML) Element</span></span>

## <a name="syntax"></a><span data-ttu-id="6899b-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="6899b-106">Syntax</span></span>

```xml

<ViewDefinitions>
  <View>...</View>
</ViewDefinitions>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="6899b-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="6899b-107">Attributes and Elements</span></span>

<span data-ttu-id="6899b-108">In den folgenden Abschnitten werden die Attribute, die untergeordneten Elemente und das übergeordnete Element des- `ViewDefinitions` Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="6899b-108">The following sections describe the attributes, child elements, and parent element of the `ViewDefinitions` element.</span></span> <span data-ttu-id="6899b-109">Es gibt keine Beschränkung für die Anzahl der Sichten, die in einer Formatierungs Datei definiert werden können, und Sie können in beliebiger Reihenfolge hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="6899b-109">There is no limit to the number of views that can be defined in a formatting file, and they can be added in any order.</span></span>

### <a name="attributes"></a><span data-ttu-id="6899b-110">Attribute</span><span class="sxs-lookup"><span data-stu-id="6899b-110">Attributes</span></span>

<span data-ttu-id="6899b-111">Keine</span><span class="sxs-lookup"><span data-stu-id="6899b-111">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="6899b-112">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="6899b-112">Child Elements</span></span>

|<span data-ttu-id="6899b-113">Element</span><span class="sxs-lookup"><span data-stu-id="6899b-113">Element</span></span>|<span data-ttu-id="6899b-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6899b-114">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="6899b-115">Element „View“ (Format)</span><span class="sxs-lookup"><span data-stu-id="6899b-115">View Element (Format)</span></span>](./view-element-format.md)|<span data-ttu-id="6899b-116">Definiert eine Ansicht, die verwendet wird, um ein oder mehrere .NET-Objekte anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="6899b-116">Defines a view that is used to display one or more .NET objects.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="6899b-117">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="6899b-117">Parent Elements</span></span>

|<span data-ttu-id="6899b-118">Element</span><span class="sxs-lookup"><span data-stu-id="6899b-118">Element</span></span>|<span data-ttu-id="6899b-119">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6899b-119">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="6899b-120">Element „Configuration“ (Format)</span><span class="sxs-lookup"><span data-stu-id="6899b-120">Configuration Element (Format)</span></span>](./configuration-element-format.md)|<span data-ttu-id="6899b-121">Stellt das Element der obersten Ebene einer Formatierungs Datei dar.</span><span class="sxs-lookup"><span data-stu-id="6899b-121">Represents the top-level element of a formatting file.</span></span>|

## <a name="remarks"></a><span data-ttu-id="6899b-122">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="6899b-122">Remarks</span></span>

<span data-ttu-id="6899b-123">Weitere Informationen zu den Komponenten der verschiedenen Sicht Typen finden Sie in den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="6899b-123">For more information about the components of the different types of views, see the following topics:</span></span>

- [<span data-ttu-id="6899b-124">Erstellen einer Tabellenansicht</span><span class="sxs-lookup"><span data-stu-id="6899b-124">Creating a Table View</span></span>](./creating-a-table-view.md)

- [<span data-ttu-id="6899b-125">Erstellen einer Listenansicht</span><span class="sxs-lookup"><span data-stu-id="6899b-125">Creating a List View</span></span>](./creating-a-list-view.md)

- [<span data-ttu-id="6899b-126">Erstellen einer breiten Ansicht</span><span class="sxs-lookup"><span data-stu-id="6899b-126">Creating a Wide View</span></span>](./creating-a-wide-view.md)

- [<span data-ttu-id="6899b-127">Benutzerdefinierte Steuerelemente</span><span class="sxs-lookup"><span data-stu-id="6899b-127">Custom Controls</span></span>](./creating-custom-controls.md)

## <a name="example"></a><span data-ttu-id="6899b-128">Beispiel</span><span class="sxs-lookup"><span data-stu-id="6899b-128">Example</span></span>

<span data-ttu-id="6899b-129">Dieses Beispiel zeigt ein `ViewDefinitions` -Element, das die übergeordneten Elemente für eine Tabellenansicht und eine Listenansicht enthält.</span><span class="sxs-lookup"><span data-stu-id="6899b-129">This example shows a `ViewDefinitions` element that contains the parent elements for a table view and a list view.</span></span>

```xml
<Configuration>
  <ViewDefinitions>
    <View>
      <TableControl>...</TableControl>
    </View>
    <View>
      <ListControl>...</ListControl>
    </View>
  </ViewDefinitions>
</Configuration>
```

## <a name="see-also"></a><span data-ttu-id="6899b-130">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6899b-130">See Also</span></span>

[<span data-ttu-id="6899b-131">Element „Configuration“ (Format)</span><span class="sxs-lookup"><span data-stu-id="6899b-131">Configuration Element (Format)</span></span>](./configuration-element-format.md)

[<span data-ttu-id="6899b-132">Element „View“ (Format)</span><span class="sxs-lookup"><span data-stu-id="6899b-132">View Element (Format)</span></span>](./view-element-format.md)

[<span data-ttu-id="6899b-133">Erstellen einer Tabellenansicht</span><span class="sxs-lookup"><span data-stu-id="6899b-133">Creating a Table View</span></span>](./creating-a-table-view.md)

[<span data-ttu-id="6899b-134">Erstellen einer Listenansicht</span><span class="sxs-lookup"><span data-stu-id="6899b-134">Creating a List View</span></span>](./creating-a-list-view.md)

[<span data-ttu-id="6899b-135">Erstellen einer breiten Ansicht</span><span class="sxs-lookup"><span data-stu-id="6899b-135">Creating a Wide View</span></span>](./creating-a-wide-view.md)

[<span data-ttu-id="6899b-136">Benutzerdefinierte Steuerelemente</span><span class="sxs-lookup"><span data-stu-id="6899b-136">Custom Controls</span></span>](./creating-custom-controls.md)

[<span data-ttu-id="6899b-137">Schreiben einer PowerShell-Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="6899b-137">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
