---
title: ExpressionBinding-Element für customItem für Steuerelemente für die Konfiguration (Format) | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: 1ad83fa9d915822eaefb490658f8a219defdddf2
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87773911"
---
# <a name="expressionbinding-element-for-customitem-for-controls-for-configuration-format"></a><span data-ttu-id="ab05d-102">Element „ExpressionBinding“ für CustomItem für Controls für Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="ab05d-102">ExpressionBinding Element for CustomItem for Controls for Configuration (Format)</span></span>

<span data-ttu-id="ab05d-103">Definiert die Daten, die vom-Steuerelement angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="ab05d-103">Defines the data that is displayed by the control.</span></span> <span data-ttu-id="ab05d-104">Dieses Element wird verwendet, wenn ein gemeinsames Steuerelement definiert wird, das von allen Sichten in der Formatierungs Datei verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="ab05d-104">This element is used when defining a common control that can be used by all the views in the formatting file.</span></span>

<span data-ttu-id="ab05d-105">Konfigurationselement (Format) steuert Element des Konfigurations Elements (Format) Steuerelement für Steuerelemente für Konfiguration (Format) CustomControl-Element für Steuerelement für Configuration (Format) customentries-Element für CustomControl for Configuration (Format) customentry-Element für CustomControl für Steuerelemente für Configuration (Format) customItem-Element für customentry für Steuerelemente für das Configuration ExpressionBinding-Element für customItem für Steuerelemente für die Konfiguration (Format)</span><span class="sxs-lookup"><span data-stu-id="ab05d-105">Configuration Element (Format) Controls Element of Configuration (Format) Control Element for Controls for Configuration (Format) CustomControl Element for Control for Configuration (Format) CustomEntries Element for CustomControl for Configuration (Format) CustomEntry Element for CustomControl for Controls for Configuration (Format) CustomItem Element for CustomEntry for Controls for Configuration ExpressionBinding Element for CustomItem for Controls for Configuration (Format)</span></span>

## <a name="syntax"></a><span data-ttu-id="ab05d-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="ab05d-106">Syntax</span></span>

```xml
<ExpressionBinding>
  <CustomControl>...</CustomControl>
  <CustomControlName>NameofCommonCustomControl</CustomControlName>
  <EnumerateCollection/>
  <ItemSelectionCondition>...</ItemSelectionCondition>
  <PropertyName>Nameof.NetTypeProperty</PropertyName>
  <ScriptBlock>ScriptToEvaluate></ScriptBlock>
</ExpressionBinding>
```

## <a name="attributes-and-elements"></a><span data-ttu-id="ab05d-107">Attribute und Elemente</span><span class="sxs-lookup"><span data-stu-id="ab05d-107">Attributes and Elements</span></span>

<span data-ttu-id="ab05d-108">In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und das übergeordnete Element des- `ExpressionBinding` Elements beschrieben.</span><span class="sxs-lookup"><span data-stu-id="ab05d-108">The following sections describe attributes, child elements, and the parent element of the `ExpressionBinding` element.</span></span>

### <a name="attributes"></a><span data-ttu-id="ab05d-109">Attribute</span><span class="sxs-lookup"><span data-stu-id="ab05d-109">Attributes</span></span>

<span data-ttu-id="ab05d-110">Keine</span><span class="sxs-lookup"><span data-stu-id="ab05d-110">None.</span></span>

### <a name="child-elements"></a><span data-ttu-id="ab05d-111">Untergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="ab05d-111">Child Elements</span></span>

|<span data-ttu-id="ab05d-112">Element</span><span class="sxs-lookup"><span data-stu-id="ab05d-112">Element</span></span>|<span data-ttu-id="ab05d-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ab05d-113">Description</span></span>|
|-------------|-----------------|
|`CustomControl Element`|<span data-ttu-id="ab05d-114">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="ab05d-114">Optional element.</span></span><br /><br /> <span data-ttu-id="ab05d-115">Definiert ein Steuerelement, das von diesem Steuerelement verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="ab05d-115">Defines a control that is used by this control.</span></span>|
|[<span data-ttu-id="ab05d-116">Element „CustomControlName“ für ExpressionBinding für Controls für Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="ab05d-116">CustomControlName Element for ExpressionBinding for Controls for Configuration (Format)</span></span>](./customcontrolname-element-for-expressionbinding-for-controls-for-configuration-format.md)|<span data-ttu-id="ab05d-117">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="ab05d-117">Optional element.</span></span><br /><br /> <span data-ttu-id="ab05d-118">Gibt den Namen eines allgemeinen Steuer Elements oder eines Ansichts Steuer Elements an.</span><span class="sxs-lookup"><span data-stu-id="ab05d-118">Specifies the name of a common control or a view control.</span></span>|
|[<span data-ttu-id="ab05d-119">Element „EnumerateCollection“ für ExpressionBinding für Controls für Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="ab05d-119">EnumerateCollection Element for ExpressionBinding for Controls for Configuration (Format)</span></span>](./enumeratecollection-element-for-expressionbinding-for-controls-for-configuration-format.md)|<span data-ttu-id="ab05d-120">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="ab05d-120">Optional element.</span></span><br /><br /> <span data-ttu-id="ab05d-121">Gibt an, dass die Elemente der Auflistungen vom-Steuerelement angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="ab05d-121">Specified that the elements of collections are displayed by the control.</span></span>|
|[<span data-ttu-id="ab05d-122">Element „ItemSelectionCondition“ für ExpressionBinding für Controls für Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="ab05d-122">ItemSelectionCondition Element for ExpressionBinding for Controls for Configuration (Format)</span></span>](./itemselectioncondition-element-for-expressionbinding-for-controls-for-configuration-format.md)|<span data-ttu-id="ab05d-123">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="ab05d-123">Optional element.</span></span><br /><br /> <span data-ttu-id="ab05d-124">Definiert die Bedingung, die vorhanden sein muss, damit dieses allgemeine Steuerelement verwendet werden muss.</span><span class="sxs-lookup"><span data-stu-id="ab05d-124">Defines the condition that must exist for this common control to be used.</span></span>|
|[<span data-ttu-id="ab05d-125">Element „PropertyName“ für ExpressionBinding für Controls für Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="ab05d-125">PropertyName Element for ExpressionBinding for Controls for Configuration (Format)</span></span>](./propertyname-element-for-expressionbinding-for-controls-for-configuration-format.md)|<span data-ttu-id="ab05d-126">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="ab05d-126">Optional element.</span></span><br /><br /> <span data-ttu-id="ab05d-127">Gibt die .net-Eigenschaft an, deren Wert durch das allgemeine Steuerelement angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="ab05d-127">Specifies the .NET property whose value is displayed by the common control.</span></span>|
|[<span data-ttu-id="ab05d-128">Element „ScriptBlock“ für ExpressionBinding für Controls für Configuration (Format)</span><span class="sxs-lookup"><span data-stu-id="ab05d-128">ScriptBlock Element for ExpressionBinding for Controls for Configuration (Format)</span></span>](./scriptblock-element-for-expressionbinding-for-controls-for-configuration-format.md)|<span data-ttu-id="ab05d-129">Optionales Element.</span><span class="sxs-lookup"><span data-stu-id="ab05d-129">Optional element.</span></span><br /><br /> <span data-ttu-id="ab05d-130">Gibt das Skript an, dessen Wert durch das allgemeine Steuerelement angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="ab05d-130">Specifies the script whose value is displayed by the common control.</span></span>|

### <a name="parent-elements"></a><span data-ttu-id="ab05d-131">Übergeordnete Elemente</span><span class="sxs-lookup"><span data-stu-id="ab05d-131">Parent Elements</span></span>

|<span data-ttu-id="ab05d-132">Element</span><span class="sxs-lookup"><span data-stu-id="ab05d-132">Element</span></span>|<span data-ttu-id="ab05d-133">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ab05d-133">Description</span></span>|
|-------------|-----------------|
|[<span data-ttu-id="ab05d-134">CustomItem-Element für customentry für Steuerelemente für die Konfiguration</span><span class="sxs-lookup"><span data-stu-id="ab05d-134">CustomItem Element for CustomEntry for Controls for Configuration</span></span>](./customitem-element-for-customentry-for-controls-for-configuration-format.md)|<span data-ttu-id="ab05d-135">Definiert, welche Daten von der benutzerdefinierten Steuerelement Ansicht und der Anzeige angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="ab05d-135">Defines what data is displayed by the custom control view and how it is displayed.</span></span>|

## <a name="remarks"></a><span data-ttu-id="ab05d-136">Bemerkungen</span><span class="sxs-lookup"><span data-stu-id="ab05d-136">Remarks</span></span>

## <a name="see-also"></a><span data-ttu-id="ab05d-137">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="ab05d-137">See Also</span></span>

[<span data-ttu-id="ab05d-138">CustomItem-Element für customentry für Steuerelemente für die Konfiguration</span><span class="sxs-lookup"><span data-stu-id="ab05d-138">CustomItem Element for CustomEntry for Controls for Configuration</span></span>](./customitem-element-for-customentry-for-controls-for-configuration-format.md)

[<span data-ttu-id="ab05d-139">Schreiben einer PowerShell-Formatierungsdatei</span><span class="sxs-lookup"><span data-stu-id="ab05d-139">Writing a PowerShell Formatting File</span></span>](./writing-a-powershell-formatting-file.md)
