---
ms.date: 06/12/2017
keywords: dsc,powershell,configuration,setup
title: 'Desired State Configuration (DSC): Übersicht für Entscheidungsträger'
ms.openlocfilehash: ce554d4bb994d4b1816d9d9c24599e4ef0e1c593
ms.sourcegitcommit: 00ff76d7d9414fe585c04740b739b9cf14d711e1
ms.translationtype: MTE95
ms.contentlocale: de-DE
ms.lasthandoff: 12/14/2018
ms.locfileid: "53401349"
---
# <a name="desired-state-configuration-overview-for-decision-makers"></a><span data-ttu-id="4c61a-103">Desired State Configuration (DSC): Übersicht für Entscheidungsträger</span><span class="sxs-lookup"><span data-stu-id="4c61a-103">Desired State Configuration Overview for Decision Makers</span></span>

<span data-ttu-id="4c61a-104">In diesem Dokument werden die Unternehmensvorteile der Verwendung von Windows PowerShell Desired State Configuration (DSC) beschrieben.</span><span class="sxs-lookup"><span data-stu-id="4c61a-104">This document describes the business benefits of using Windows PowerShell Desired State Configuration (DSC).</span></span> <span data-ttu-id="4c61a-105">Es handelt sich nicht um ein technisches Handbuch.</span><span class="sxs-lookup"><span data-stu-id="4c61a-105">It is not a technical guide.</span></span>

## <a name="what-is-desired-state-configuration"></a><span data-ttu-id="4c61a-106">Was ist „Desired State Configuration“?</span><span class="sxs-lookup"><span data-stu-id="4c61a-106">What Is Desired State Configuration?</span></span>

<span data-ttu-id="4c61a-107">PowerShell Desired State Configuration ist eine in Windows integrierte Konfigurationsverwaltungsplattform, die auf offenen Standards basiert.</span><span class="sxs-lookup"><span data-stu-id="4c61a-107">PowerShell Desired State Configuration is a configuration management platform built into Windows that is based on open standards.</span></span> <span data-ttu-id="4c61a-108">DSC ist flexibel genug, in jeder Phase des Bereitstellungslebenszyklus (Entwicklung, Test, Präproduktion, Produktion) sowie bei horizontaler Skalierung zuverlässig und konsistent zu funktionieren.</span><span class="sxs-lookup"><span data-stu-id="4c61a-108">DSC is flexible enough to function reliably and consistently in each stage of the deployment lifecycle (development, test, pre-production, production), as well as during scale-out.</span></span>

<span data-ttu-id="4c61a-109">Eine Hauptfunktion von DSC sind [Konfigurationen](../configurations/configurations.md).</span><span class="sxs-lookup"><span data-stu-id="4c61a-109">DSC centers around [configurations](../configurations/configurations.md).</span></span>
<span data-ttu-id="4c61a-110">Eine Konfiguration ist ein einfach zu lesendes Dokument, das eine aus Computern („Knoten“) bestehende Umgebung mit bestimmten Merkmalen beschreibt.</span><span class="sxs-lookup"><span data-stu-id="4c61a-110">A configuration is an easy-to-read document that describes an environment made up of computers ("nodes") with specific characteristics.</span></span>
<span data-ttu-id="4c61a-111">Diese Merkmale können so einfach wie das Sicherstellen, dass ein bestimmtes Windows-Feature aktiviert ist, oder so komplex wie das Bereitstellen von SharePoint sein.</span><span class="sxs-lookup"><span data-stu-id="4c61a-111">These characteristics can be as simple as ensuring a specific Windows feature is enabled or as complex as deploying SharePoint.</span></span>

<span data-ttu-id="4c61a-112">DSC verfügt auch über eine integrierte Überwachung und Berichterstellung.</span><span class="sxs-lookup"><span data-stu-id="4c61a-112">DSC also has monitoring and reporting built in.</span></span>
<span data-ttu-id="4c61a-113">Wenn ein System nicht mehr kompatibel ist, kann DSC eine Warnung auslösen und agieren, um das System zu korrigieren.</span><span class="sxs-lookup"><span data-stu-id="4c61a-113">If a system is no longer compliant, DSC can raise an alert and act to correct the system.</span></span>

## <a name="benefits-of-using-desired-state-configuration"></a><span data-ttu-id="4c61a-114">Vorteile der Verwendung von DSC</span><span class="sxs-lookup"><span data-stu-id="4c61a-114">Benefits of Using Desired State Configuration</span></span>

<span data-ttu-id="4c61a-115">Konfigurationen sind leicht zu lesen, zu speichern und zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="4c61a-115">Configurations are designed to be easily read, stored, and updated.</span></span>
<span data-ttu-id="4c61a-116">Konfigurationen definieren den Zustand, den Zielgeräte haben sollen, anstatt Anweisungen zu schreiben, wie diese in den jeweiligen Zustand versetzt werden können.</span><span class="sxs-lookup"><span data-stu-id="4c61a-116">Configurations declare the state target devices should be in, instead of writing instructions for how to put them in that state.</span></span>
<span data-ttu-id="4c61a-117">Dadurch ist der Aufwand wesentlich geringer, eine Konfiguration über DSC zu erlernen, zu übernehmen, zu implementieren und beizubehalten.</span><span class="sxs-lookup"><span data-stu-id="4c61a-117">This makes it much less costly to learn, adopt, implement, and maintain configuration through DSC.</span></span>

<span data-ttu-id="4c61a-118">Das Erstellen von Konfigurationen bedeutet, dass komplexe Bereitstellungsschritte als kompakte Lösung an einem zentralen Ort erfasst werden.</span><span class="sxs-lookup"><span data-stu-id="4c61a-118">Creating configurations means that complex deployment steps are captured as a "single source of truth" in a single location.</span></span>
<span data-ttu-id="4c61a-119">Dadurch wird die wiederholte Bereitstellung bestimmter Computergruppen wesentlich weniger fehleranfällig.</span><span class="sxs-lookup"><span data-stu-id="4c61a-119">This makes repeated deployments of a specific set of machines much less error-prone.</span></span>
<span data-ttu-id="4c61a-120">Auf der anderen Seite werden Bereitstellungen schneller und zuverlässiger, sodass sich komplexe Bereitstellungen schneller realisieren lassen.</span><span class="sxs-lookup"><span data-stu-id="4c61a-120">In turn, making deployments faster and more reliable which enables a quick turnaround on complex deployments.</span></span>

<span data-ttu-id="4c61a-121">Konfigurationen können auch über den [PowerShell-Katalog](https://powershellgallery.com) freigegeben werden. Möglicherweise sind für die Arbeiten, die erledigt werden müssen, bereits gängige Szenarios und bewährte Methoden vorhanden.</span><span class="sxs-lookup"><span data-stu-id="4c61a-121">Configurations are also shareable via the [PowerShell Gallery](https://powershellgallery.com) meaning common scenarios and best practices might already exist for the work that needs to be done.</span></span>


## <a name="desired-state-configuration-and-devops"></a><span data-ttu-id="4c61a-122">DSC und DevOps</span><span class="sxs-lookup"><span data-stu-id="4c61a-122">Desired State Configuration and DevOps</span></span>

<span data-ttu-id="4c61a-123">DSC wurde mit [DevOps](http://blogs.technet.com/b/ashleymcglone/archive/2015/11/20/devops-for-n00bs-ie-windows-people.aspx) im Hinterkopf entwickelt. Dieser Ansatz vereint Benutzer, Prozesse und Tools, sodass eine schnelle Bereitstellung und Iteration möglich ist, um sowohl internen als auch externen Endbenutzern einen Mehrwert zu bieten.</span><span class="sxs-lookup"><span data-stu-id="4c61a-123">DSC was designed with [DevOps](http://blogs.technet.com/b/ashleymcglone/archive/2015/11/20/devops-for-n00bs-ie-windows-people.aspx) in mind, a combination of people, processes, and tools that allow for rapid deployment and iteration focused on delivering value to end users whether internal or external.</span></span>
<span data-ttu-id="4c61a-124">Wenn eine Umgebung mittels einer einzelnen Konfiguration definiert wird, können Entwickler ihre Anforderungen in einer Konfiguration codieren und diese Konfiguration in die Quellcodeverwaltung einchecken. Das Betriebsteam kann anschließend Code bereitstellen, ohne fehleranfällige manuelle Prozesse durchlaufen zu müssen.</span><span class="sxs-lookup"><span data-stu-id="4c61a-124">Having a single configuration define an environment means that developers can encode their requirements into a configuration, check that configuration into source control, and operation teams can easily deploy code without having to go through error-prone manual processes.</span></span>

<span data-ttu-id="4c61a-125">Konfigurationen sind auch [datengesteuert](../configurations/configData.md), was es dem Betriebsteam erleichtert, Umgebungen ohne Eingriffe von Entwicklern zu erkennen und zu ändern.</span><span class="sxs-lookup"><span data-stu-id="4c61a-125">Configurations are also [data-driven](../configurations/configData.md), which makes it easier for ops to identify and change environments without developer intervention.</span></span>

## <a name="desired-state-configuration-on-premises-and-off-premises"></a><span data-ttu-id="4c61a-126">Desired State Configuration, lokale und externe</span><span class="sxs-lookup"><span data-stu-id="4c61a-126">Desired State Configuration On-Premises and Off-Premises</span></span>
<span data-ttu-id="4c61a-127">DSC kann zum Verwalten lokaler und externer Bereitstellungen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="4c61a-127">DSC can be used to manage both on-premise and off-premise deployments.</span></span>
<span data-ttu-id="4c61a-128">Für lokale Lösungen bietet DSC einen [Pullserver](../pull-server/pullServer.md) zum Zentralisieren der Verwaltung von Computern und Melden ihres Status.</span><span class="sxs-lookup"><span data-stu-id="4c61a-128">For on-premise solutions, DSC has a [pull server](../pull-server/pullServer.md) that can be used to centralize management of machines and report on their status.</span></span>
<span data-ttu-id="4c61a-129">Für Cloudlösungen lässt sich DSC da verwenden, wo Windows verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="4c61a-129">For cloud solutions, DSC is usable wherever Windows is usable.</span></span>
<span data-ttu-id="4c61a-130">Es gibt auch spezielle Angebote in Azure, die auf DSC basieren, wie z.B. [Azure Automation](https://azure.microsoft.com/en-us/documentation/services/automation/) zum Zentralisieren der Berichterstattung für DSC.</span><span class="sxs-lookup"><span data-stu-id="4c61a-130">There are also specific offerings from Azure built on Desired State Configuration, such as [Azure Automation](https://azure.microsoft.com/en-us/documentation/services/automation/), which centralizes reporting of DSC.</span></span>

## <a name="dsc-and-compatibility"></a><span data-ttu-id="4c61a-131">DSC und Kompatibilität</span><span class="sxs-lookup"><span data-stu-id="4c61a-131">DSC and Compatibility</span></span>

<span data-ttu-id="4c61a-132">DSC wurde zwar in Windows Server 2012 R2 eingeführt, ist aber auch für ältere Betriebssysteme über das WMF-Paket (WMF) verfügbar.</span><span class="sxs-lookup"><span data-stu-id="4c61a-132">Although DSC was introduced in Windows Server 2012 R2, it is available for down-level operating systems via the Windows Management Framework (WMF) package.</span></span>
<span data-ttu-id="4c61a-133">Weitere Informationen zum WMF finden Sie auf der [PowerShell-Startseite](/powershell/).</span><span class="sxs-lookup"><span data-stu-id="4c61a-133">More information about the WMF can be found on the [PowerShell homepage](/powershell/).</span></span>

<span data-ttu-id="4c61a-134">DSC kann auch zum Verwalten von Linux verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="4c61a-134">DSC can also be used to manage Linux.</span></span> <span data-ttu-id="4c61a-135">Weitere Informationen finden Sie unter [Erste Schritte mit DSC für Linux](../getting-started/lnxGettingStarted.md).</span><span class="sxs-lookup"><span data-stu-id="4c61a-135">For more information, see [Getting Started with DSC for Linux](../getting-started/lnxGettingStarted.md).</span></span>