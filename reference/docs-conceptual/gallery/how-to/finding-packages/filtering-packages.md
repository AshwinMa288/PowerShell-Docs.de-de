---
ms.date: 06/12/2017
title: Filtern von Suchergebnissen
description: In diesem Artikel wird die Benutzeroberfläche beschrieben, die zum Filtern von Inhalten im PowerShell-Katalog verwendet wird.
ms.openlocfilehash: cc375f3ddb35c95ed134776500bd326bc3db6b1a
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92661400"
---
# <a name="filtering-search-results"></a><span data-ttu-id="879d1-103">Filtern von Suchergebnissen</span><span class="sxs-lookup"><span data-stu-id="879d1-103">Filtering search results</span></span>

<span data-ttu-id="879d1-104">Die Registerkarte [Pakete](https://www.powershellgallery.com/packages) zeigt alle verfügbaren Pakete im PowerShell-Katalog an.</span><span class="sxs-lookup"><span data-stu-id="879d1-104">The [Packages tab](https://www.powershellgallery.com/packages) displays all available packages in the PowerShell Gallery.</span></span>

<span data-ttu-id="879d1-105">Es gibt verschiedene Möglichkeiten, die Pakete zu filtern, zu sortieren und zu durchsuchen.</span><span class="sxs-lookup"><span data-stu-id="879d1-105">There are several ways to filter, sort, and search the packages.</span></span> <span data-ttu-id="879d1-106">Um weitere Details zu einem bestimmten Paket anzuzeigen, klicken Sie auf das Paket.</span><span class="sxs-lookup"><span data-stu-id="879d1-106">To see more details about a particular package, click the package.</span></span>

## <a name="filter-by"></a><span data-ttu-id="879d1-107">Filtern nach</span><span class="sxs-lookup"><span data-stu-id="879d1-107">Filter By</span></span>

<span data-ttu-id="879d1-108">Mit der Dropdownliste „Filtern nach“ können Benutzer die Ergebnisse nach folgenden Kriterien filtern:</span><span class="sxs-lookup"><span data-stu-id="879d1-108">The drop-down under "Filter By" allows users to filter the results by:</span></span>

- <span data-ttu-id="879d1-109">Vorabversion einbeziehen</span><span class="sxs-lookup"><span data-stu-id="879d1-109">Include Prerelease</span></span>
- <span data-ttu-id="879d1-110">Nur stabile</span><span class="sxs-lookup"><span data-stu-id="879d1-110">Stable Only</span></span>

<span data-ttu-id="879d1-111">Informationen zu „Vorabversion“ und „stabil“ finden Sie im PowerShell-Teamblog unter [Prerelease Versioning Added to PowerShellGet and PowerShell Gallery](https://blogs.msdn.microsoft.com/powershell/2017/12/05/prerelease-versioning-added-to-powershellget-and-powershell-gallery/) (Versionsverwaltung von Vorabversionen zu PowerShellGet und dem PowerShell-Katalog hinzugefügt).</span><span class="sxs-lookup"><span data-stu-id="879d1-111">For information about "Prerelease" and "Stable", see [Prerelease Versioning Added to PowerShellGet and PowerShell Gallery](https://blogs.msdn.microsoft.com/powershell/2017/12/05/prerelease-versioning-added-to-powershellget-and-powershell-gallery/) in the PowerShell Team Blog.</span></span>

<span data-ttu-id="879d1-112">Mithilfe der Kontrollkästchen unter der Dropdownliste können Benutzer die Ergebnisse nach folgenden Kriterien filtern:</span><span class="sxs-lookup"><span data-stu-id="879d1-112">The checkboxes under the drop-down allow users to filter the results by:</span></span>

- <span data-ttu-id="879d1-113">Pakettypen</span><span class="sxs-lookup"><span data-stu-id="879d1-113">Package Types</span></span>
  - <span data-ttu-id="879d1-114">Modul</span><span class="sxs-lookup"><span data-stu-id="879d1-114">Module</span></span>
  - <span data-ttu-id="879d1-115">Skript</span><span class="sxs-lookup"><span data-stu-id="879d1-115">Script</span></span>
- <span data-ttu-id="879d1-116">Kategorien</span><span class="sxs-lookup"><span data-stu-id="879d1-116">Categories</span></span>
  - <span data-ttu-id="879d1-117">Cmdlet</span><span class="sxs-lookup"><span data-stu-id="879d1-117">Cmdlet</span></span>
  - <span data-ttu-id="879d1-118">DSC-Ressource</span><span class="sxs-lookup"><span data-stu-id="879d1-118">DSC Resource</span></span>
  - <span data-ttu-id="879d1-119">Funktion</span><span class="sxs-lookup"><span data-stu-id="879d1-119">Function</span></span>
  - <span data-ttu-id="879d1-120">Rollenfunktion</span><span class="sxs-lookup"><span data-stu-id="879d1-120">Role Capability</span></span>
  - <span data-ttu-id="879d1-121">Workflow</span><span class="sxs-lookup"><span data-stu-id="879d1-121">Workflow</span></span>

<span data-ttu-id="879d1-122">Um im PowerShell-Katalog nur Module anzuzeigen, aktivieren Sie unter „Pakettypen“ die Option „Modul“.</span><span class="sxs-lookup"><span data-stu-id="879d1-122">To see only modules in the PowerShell Gallery, check Module in the Package Types.</span></span> <span data-ttu-id="879d1-123">Um im PowerShell-Katalog nur Skripts anzuzeigen, aktivieren Sie unter „Pakettypen“ die Option „Skript“.</span><span class="sxs-lookup"><span data-stu-id="879d1-123">Similarly, to see only scripts in the PowerShell Gallery, check Script in the Package Types.</span></span>

> [!NOTE]
> <span data-ttu-id="879d1-124">Filter sind inklusiv.</span><span class="sxs-lookup"><span data-stu-id="879d1-124">Filters are inclusive.</span></span> <span data-ttu-id="879d1-125">Beispiel: Ein Paket, das sowohl Cmdlets als auch Funktionen erhält, wird angezeigt, wenn entweder „Cmdlet“ oder „Funktion“ (oder beides) aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="879d1-125">Example: A package containing both cmdlets and functions will appear if either Cmdlet or Function (or both) are checked.</span></span> <span data-ttu-id="879d1-126">Wenn keine der Optionen ausgewählt ist, wird das Paket nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="879d1-126">If neither are selected, the package will not appear.</span></span> <span data-ttu-id="879d1-127">Ähnliches gilt, wenn Kategorien ausgewählt werden: Es werden nur Pakete angezeigt, die zu einer dieser Kategorien gehören.</span><span class="sxs-lookup"><span data-stu-id="879d1-127">Similarly, if all categories are selected, only packages containing one of those categories will appear.</span></span> <span data-ttu-id="879d1-128">**Pakete, die zu keiner dieser Kategorie gehören, werden nicht angezeigt.**</span><span class="sxs-lookup"><span data-stu-id="879d1-128">**Packages that do not belong to any of those categories will not appear.**</span></span>

## <a name="sort-by"></a><span data-ttu-id="879d1-129">Sortieren nach</span><span class="sxs-lookup"><span data-stu-id="879d1-129">Sort By</span></span>

<span data-ttu-id="879d1-130">Mithilfe der Dropdownliste „Sortieren nach“ können Benutzer die Ergebnisse nach folgenden Kriterien filtern:</span><span class="sxs-lookup"><span data-stu-id="879d1-130">The Sort By drop-down allows users to sort the results by:</span></span>

- <span data-ttu-id="879d1-131">Beliebtheit: Die Beliebtheit wird durch die Anzahl der Downloads bestimmt.</span><span class="sxs-lookup"><span data-stu-id="879d1-131">Popularity - Popularity is determined by Download Count</span></span>
- <span data-ttu-id="879d1-132">A-Z: Alphabetisch nach Paketname.</span><span class="sxs-lookup"><span data-stu-id="879d1-132">A-Z - Alphabetically by package name</span></span>
- <span data-ttu-id="879d1-133">Aktuell: Pakete werden in der Reihenfolge der Veröffentlichungsdaten angezeigt.</span><span class="sxs-lookup"><span data-stu-id="879d1-133">Recent - Packages appear in order of publish date</span></span>

## <a name="search-box"></a><span data-ttu-id="879d1-134">Suchfeld</span><span class="sxs-lookup"><span data-stu-id="879d1-134">Search Box</span></span>

<span data-ttu-id="879d1-135">Mit dem Suchfeld können Benutzer Pakete nach Schlüsselwort suchen.</span><span class="sxs-lookup"><span data-stu-id="879d1-135">The Search Box allows users to search the packages on keywords.</span></span>
<span data-ttu-id="879d1-136">Weitere Informationen finden Sie unter [Syntax für die Katalogsuche](search-syntax.md).</span><span class="sxs-lookup"><span data-stu-id="879d1-136">For more information, see [Gallery Search Syntax](search-syntax.md).</span></span>
