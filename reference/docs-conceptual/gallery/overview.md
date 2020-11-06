---
ms.date: 06/12/2017
title: Der PowerShell-Katalog | MSDN
description: Der PowerShell-Katalog ist das zentrale Repository für PowerShell-Module, Skripts und DSC-Ressourcen.
ms.openlocfilehash: 1aa3d351e71211259cac4e6d6f0ebd68c0df6ff1
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92662117"
---
# <a name="the-powershell-gallery"></a><span data-ttu-id="b597d-103">Der PowerShell-Katalog | MSDN</span><span class="sxs-lookup"><span data-stu-id="b597d-103">The PowerShell Gallery</span></span>

<span data-ttu-id="b597d-104">Der PowerShell-Katalog ist das zentrale Repository für PowerShell-Inhalte.</span><span class="sxs-lookup"><span data-stu-id="b597d-104">The PowerShell Gallery is the central repository for PowerShell content.</span></span> <span data-ttu-id="b597d-105">Sie finden darin nützliche PowerShell-Module, die PowerShell-Befehle und Desired State Configuration-Ressourcen (DSC) enthalten.</span><span class="sxs-lookup"><span data-stu-id="b597d-105">In it, you can find useful PowerShell modules containing PowerShell commands and Desired State Configuration (DSC) resources.</span></span>
<span data-ttu-id="b597d-106">Sie finden dort auch PowerShell-Skripts, von denen einige PowerShell-Workflows enthalten, eine Reihe von Aufgaben umreißen und Sequenzierungen für diese Aufgaben bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="b597d-106">You can also find PowerShell scripts, some of which may contain PowerShell workflows, and which outline a set of tasks and provide sequencing for those tasks.</span></span> <span data-ttu-id="b597d-107">Einige dieser Pakete wurden von Microsoft erstellt, andere stammen aus der PowerShell-Community.</span><span class="sxs-lookup"><span data-stu-id="b597d-107">Some of these packages are authored by Microsoft, and others are authored by the PowerShell community.</span></span>

## <a name="powershellget-overview"></a><span data-ttu-id="b597d-108">Übersicht über PowerShellGet</span><span class="sxs-lookup"><span data-stu-id="b597d-108">PowerShellGet Overview</span></span>

<span data-ttu-id="b597d-109">Das PowerShellGet-Modul enthält Cmdlets zum Ermitteln, Installieren, Aktualisieren und Veröffentlichen von PowerShell-Paketen mit Artefakten wie Modulen, DSC-Ressourcen, Rollenfunktionen und Skripts über den [PowerShell-Katalog](https://www.PowerShellGallery.com) und andere private Repositorys.</span><span class="sxs-lookup"><span data-stu-id="b597d-109">The PowerShellGet module contains cmdlets for discovering, installing, updating and publishing PowerShell packages which contain artifacts such as Modules, DSC Resources, Role Capabilities and Scripts from the [PowerShell Gallery](https://www.PowerShellGallery.com) and other private repositories.</span></span>

## <a name="getting-started-with-the-gallery"></a><span data-ttu-id="b597d-110">Erste Schritte mit dem Katalog</span><span class="sxs-lookup"><span data-stu-id="b597d-110">Getting Started with the Gallery</span></span>

<span data-ttu-id="b597d-111">Zur Installation von Paketen aus dem Katalog wird die neueste Version des PowerShellGet-Moduls benötigt.</span><span class="sxs-lookup"><span data-stu-id="b597d-111">Installing packages from the Gallery requires the latest version of the PowerShellGet module.</span></span> <span data-ttu-id="b597d-112">Eine vollständige Anleitung finden Sie unter [Installieren von PowerShellGet](installing-psget.md).</span><span class="sxs-lookup"><span data-stu-id="b597d-112">See [Installing PowerShellGet](installing-psget.md) for complete instructions.</span></span>

<span data-ttu-id="b597d-113">Sehen Sie sich die Seite [Erste Schritte](getting-started.md) an, um weitere Informationen zur Verwendung von PowerShellGet-Befehlen mit dem Katalog zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="b597d-113">Check out the [Getting Started](getting-started.md) page for more information on how to use PowerShellGet commands with the Gallery.</span></span> <span data-ttu-id="b597d-114">Sie können auch *Update-Help -Module PowerShellGet* ausführen, um die lokale Hilfe für diese Befehle zu installieren.</span><span class="sxs-lookup"><span data-stu-id="b597d-114">You can also run *Update-Help -Module PowerShellGet* to install local help for these commands.</span></span>

## <a name="supported-operating-systems"></a><span data-ttu-id="b597d-115">Unterstützte Betriebssysteme</span><span class="sxs-lookup"><span data-stu-id="b597d-115">Supported Operating Systems</span></span>

<span data-ttu-id="b597d-116">Für das **PowerShellGet** -Modul ist **PowerShell 3.0 oder neuer** erforderlich.</span><span class="sxs-lookup"><span data-stu-id="b597d-116">The **PowerShellGet** module requires **PowerShell 3.0 or newer**.</span></span>

<span data-ttu-id="b597d-117">Für **PowerShellGet** ist .NET Framework 4.5 oder höher erforderlich.</span><span class="sxs-lookup"><span data-stu-id="b597d-117">**PowerShellGet** requires .NET Framework 4.5 or above.</span></span> <span data-ttu-id="b597d-118">Von [hier](https://msdn.microsoft.com/library/5a4x27ek.aspx) können Sie .NET Framework 4.5 oder höher installieren.</span><span class="sxs-lookup"><span data-stu-id="b597d-118">You can install .NET Framework 4.5 or above from [here](https://msdn.microsoft.com/library/5a4x27ek.aspx).</span></span>

<span data-ttu-id="b597d-119">Da **PowerShell Core** plattformübergreifend ist – was bedeutet, dass es unter Windows, Linux und macOS funktioniert –, ist auch **PowerShellGet** auf diesen Systemen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="b597d-119">Since **PowerShell Core** is cross-platform and that means it works on Windows, Linux and MacOS, that also makes **PowerShellGet** available on those systems.</span></span> <span data-ttu-id="b597d-120">Eine vollständige Liste der von **PowerShell Core** unterstützten Systeme finden Sie unter [Installieren von PowerShell](/powershell/scripting/install/installing-powershell).</span><span class="sxs-lookup"><span data-stu-id="b597d-120">For a full list of systems supported by **PowerShell Core** see [Installing PowerShell](/powershell/scripting/install/installing-powershell).</span></span>

<span data-ttu-id="b597d-121">Viele Module, die im Katalog aufgeführt sind, unterstützen andere Betriebssysteme und haben zusätzliche Anforderungen.</span><span class="sxs-lookup"><span data-stu-id="b597d-121">Many modules hosted in the gallery will support different OSes and have additional requirements.</span></span>
<span data-ttu-id="b597d-122">Weitere Informationen finden Sie in der Dokumentation der jeweiligen Module.</span><span class="sxs-lookup"><span data-stu-id="b597d-122">Please refer to the documentation for the modules for more information.</span></span>

## <a name="got-a-question-have-feedback"></a><span data-ttu-id="b597d-123">Sie haben eine Frage?</span><span class="sxs-lookup"><span data-stu-id="b597d-123">Got a question?</span></span> <span data-ttu-id="b597d-124">Feedback?</span><span class="sxs-lookup"><span data-stu-id="b597d-124">Have feedback?</span></span>

<span data-ttu-id="b597d-125">Weitere Informationen zum PowerShell-Katalog und zu PowerShellGet finden Sie auf der Seite [Erste Schritte](getting-started.md).</span><span class="sxs-lookup"><span data-stu-id="b597d-125">More information about the PowerShell Gallery and PowerShellGet can be found in the [Getting Started](getting-started.md) page.</span></span> <span data-ttu-id="b597d-126">Stellen Sie Feedback bereit, und melden Sie Probleme über [UserVoice](http://windowsserver.uservoice.com/forums/301869-powershell).</span><span class="sxs-lookup"><span data-stu-id="b597d-126">Please provide feedback and report issues using [UserVoice](http://windowsserver.uservoice.com/forums/301869-powershell).</span></span>
