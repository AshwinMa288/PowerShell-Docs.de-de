---
ms.date: 06/12/2017
contributor: JKeithB
keywords: gallery,powershell,cmdlet,psgallery
title: Verwalten von Elementbesitzern
ms.openlocfilehash: 10d2a433253162847028e157b5bac47b23406469
ms.sourcegitcommit: 54534635eedacf531d8d6344019dc16a50b8b441
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/17/2018
---
# <a name="managing-item-owners"></a><span data-ttu-id="a4114-103">Verwalten von Elementbesitzern</span><span class="sxs-lookup"><span data-stu-id="a4114-103">Managing item owners</span></span>

<span data-ttu-id="a4114-104">Der Besitz eines Elements im PowerShell-Katalog wird von der Person definiert, die das Element im Katalog veröffentlicht hat.</span><span class="sxs-lookup"><span data-stu-id="a4114-104">Ownership of an item in the PowerShell Gallery is defined by who published the item to the gallery.</span></span>
<span data-ttu-id="a4114-105">Mitunter müssen diese Metadaten über die anfängliche Veröffentlichung des Elements hinaus verwaltet werden, was bedeutet, dass die Besitzermetadaten veränderlich sein müssen, das Element hingegen nicht.</span><span class="sxs-lookup"><span data-stu-id="a4114-105">Sometimes this metadata needs to be managed beyond the initial item publishing, which means the owner metadata needs to be mutable while the item itself is not.</span></span>

<span data-ttu-id="a4114-106">Alle Elementbesitzer sind Peers.</span><span class="sxs-lookup"><span data-stu-id="a4114-106">All item owners are peers.</span></span>
<span data-ttu-id="a4114-107">Das bedeutet, dass alle Elementbesitzer eine neue Version eines Elements veröffentlichen können.</span><span class="sxs-lookup"><span data-stu-id="a4114-107">This means any item owner can publish a new version of an item.</span></span> <span data-ttu-id="a4114-108">Es bedeutet aber auch, dass jeder Elementbesitzer jeden anderen Elementbesitzer entfernen kann.</span><span class="sxs-lookup"><span data-stu-id="a4114-108">It also means that any item owner can remove any other item owner.</span></span>
<span data-ttu-id="a4114-109">Kein Besitzer verfügt über mehr Berechtigungen als andere Besitzer.</span><span class="sxs-lookup"><span data-stu-id="a4114-109">No owner has more authority than other owners.</span></span>

## <a name="setting-an-items-initial-owner"></a><span data-ttu-id="a4114-110">Festlegen des anfänglichen Besitzers eines Elements</span><span class="sxs-lookup"><span data-stu-id="a4114-110">Setting an Item's Initial Owner</span></span>

<span data-ttu-id="a4114-111">Beim Veröffentlichen eines neues Elements im PowerShell-Katalog wird der anfängliche Besitzer von dem Benutzer definiert, der das Element veröffentlicht.</span><span class="sxs-lookup"><span data-stu-id="a4114-111">When a new item is published to PowerShell Gallery, the initial owner is defined by the user that published the item.</span></span> <span data-ttu-id="a4114-112">Dies richtet sich danach, wessen API-Schlüssel im Cmdlet „Publish-Modul“ verwendet wurde.</span><span class="sxs-lookup"><span data-stu-id="a4114-112">This is determined by whose API key was used in the Publish-Module cmdlet.</span></span>

## <a name="adding-owners"></a><span data-ttu-id="a4114-113">Hinzufügen von Besitzern</span><span class="sxs-lookup"><span data-stu-id="a4114-113">Adding Owners</span></span>

<span data-ttu-id="a4114-114">Sobald ein Element im PowerShell-Katalog veröffentlicht wurde, können ganz einfach zusätzliche Benutzer als Besitzer eines Elements eingeladen werden.</span><span class="sxs-lookup"><span data-stu-id="a4114-114">Once an item has been published to the PowerShell Gallery, it's easy to invite additional users to become owners of an item.</span></span>

1. <span data-ttu-id="a4114-115">[Melden Sie sich beim PowerShell-Katalog mit dem Konto an](https://powershellgallery.com/users/account/LogOn), das der aktuelle Besitzer eines Elements ist.</span><span class="sxs-lookup"><span data-stu-id="a4114-115">[Log on](https://powershellgallery.com/users/account/LogOn) to the PowerShell Gallery with the account that is the current owner of an item.</span></span>
2. <span data-ttu-id="a4114-116">Navigieren Sie zu einer Elementseite, indem Sie die Registerkarte „Elemente“ verwenden, suchen oder auf Ihren Benutzernamen und dann auf [**Meine Elemente verwalten**](https://www.powershellgallery.com/account/Packages) klicken.</span><span class="sxs-lookup"><span data-stu-id="a4114-116">Navigate to an item page using the 'Items' tab, searching, or clicking your username and then [**Manage My Items**](https://www.powershellgallery.com/account/Packages).</span></span>
3. <span data-ttu-id="a4114-117">Wenn Sie als Besitzer eines Elements angemeldet sind, finden Sie auf der linken Seite einen Link „Besitzer verwalten“, auf den Sie klicken können.</span><span class="sxs-lookup"><span data-stu-id="a4114-117">When logged on as an item's owner, there is a 'Manage Owners' link on the left side to click.</span></span>
4. <span data-ttu-id="a4114-118">Geben Sie den Benutzernamen der Person ein, die Sie als Besitzer hinzufügen möchten, und klicken Sie auf „Hinzufügen“.</span><span class="sxs-lookup"><span data-stu-id="a4114-118">Enter the username of the person to add as an owner and click 'Add'.</span></span>
5. <span data-ttu-id="a4114-119">Eine E-Mail wird an den neuen Mitbesitzer gesendet, um ihn als Besitzer eines Elements einzuladen.</span><span class="sxs-lookup"><span data-stu-id="a4114-119">An email is then sent to the new co-owner, as an invitation to become an owner of an item.</span></span>
6. <span data-ttu-id="a4114-120">Sobald der Benutzer auf den Link klickt, ist er ein vollständiger Mitbesitzer mit Vollzugriff auf ein Element, einschließlich der Möglichkeit, andere Benutzer als Besitzer zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="a4114-120">Once that user clicks the link, they are a full co-owner with full control over an item, including the ability to remove other users as owners.</span></span>

<span data-ttu-id="a4114-121">**HINWEIS**: Der neue Besitzer wird *erst dann* als Besitzer eines Elements aufgeführt, wenn er den Besitz bestätigt.</span><span class="sxs-lookup"><span data-stu-id="a4114-121">**NOTE**: Until the new owner confirms ownership, they *will not* be listed as an owner of an item.</span></span>
<span data-ttu-id="a4114-122">Beim Anzeigen der Seite **Besitzer verwalten** sehen Sie bei den aktuellen Besitzern einen Eintrag „Genehmigung steht aus“.</span><span class="sxs-lookup"><span data-stu-id="a4114-122">When viewing the **Manage Owners** page, you will see a "pending approval" entry in the current owners.</span></span>
<span data-ttu-id="a4114-123">Diese Einladung kann ebenso entfernt werden wie andere Besitzer entfernt werden können.</span><span class="sxs-lookup"><span data-stu-id="a4114-123">That invitation can be removed; just as other owners can be removed.</span></span>
<span data-ttu-id="a4114-124">Dieser Einladungsprozess verhindert, dass Benutzer fälschlicherweise andere Benutzer als Besitzer ihrer Elemente hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="a4114-124">This process of invitations prevents users from falsely adding other users as owners of their items.</span></span>

<span data-ttu-id="a4114-125">Beachten Sie, dass die Metadaten „Autoren“ in reinem Freiformtext vorliegen. Nur „Besitzer“ werden gesteuert.</span><span class="sxs-lookup"><span data-stu-id="a4114-125">Note that the "Authors" metadata is purely freeform text; only "Owners" are controlled.</span></span>


## <a name="removing-owners"></a><span data-ttu-id="a4114-126">Entfernen von Besitzern</span><span class="sxs-lookup"><span data-stu-id="a4114-126">Removing Owners</span></span>

<span data-ttu-id="a4114-127">Wenn ein Element mehrere Besitzer aufweist und einer entfernt werden muss, ist der Prozess einfach:</span><span class="sxs-lookup"><span data-stu-id="a4114-127">When an item has multiple owners and one needs to be removed, the process is simple:</span></span>

1. <span data-ttu-id="a4114-128">[Melden Sie sich beim PowerShell-Katalog mit dem Konto an](https://powershellgallery.com/users/account/LogOn), das der aktuelle Besitzer eines Elements ist.</span><span class="sxs-lookup"><span data-stu-id="a4114-128">[Log on](https://powershellgallery.com/users/account/LogOn) to PowerShell Gallery with the account that is the current owner of an item;</span></span>
2. <span data-ttu-id="a4114-129">Navigieren Sie zu einer Elementseite, indem Sie die Registerkarte „Elemente“ verwenden, suchen oder auf Ihren Benutzernamen und dann auf [**Meine Elemente verwalten**](https://www.powershellgallery.com/account/Packages) klicken.</span><span class="sxs-lookup"><span data-stu-id="a4114-129">Navigate to an item page using the Items tab, searching, or clicking your username and then [**Manage My Items**](https://www.powershellgallery.com/account/Packages).</span></span>
3. <span data-ttu-id="a4114-130">Wenn Sie als Besitzer eines Elements angemeldet sind, finden Sie auf der linken Seite einen Link „Besitzer verwalten“, auf den Sie klicken können.</span><span class="sxs-lookup"><span data-stu-id="a4114-130">When logged on as an item's owner, there is a 'Manage Owners' link on the left side to click;</span></span>
4. <span data-ttu-id="a4114-131">Klicken Sie neben dem Besitzer, der entfernt werden soll, auf den Link „Entfernen“.</span><span class="sxs-lookup"><span data-stu-id="a4114-131">Click the 'remove' link next to the owner to be removed.</span></span>



## <a name="transferring-item-ownership"></a><span data-ttu-id="a4114-132">Übertragen des Besitzes für ein Element</span><span class="sxs-lookup"><span data-stu-id="a4114-132">Transferring Item Ownership</span></span>

<span data-ttu-id="a4114-133">Gelegentlich erhalten wir Supportanfragen, um den Besitz eines Elements von einem Benutzer auf einen anderen zu übertragen, allerdings können Sie das fast immer selbst durchführen.</span><span class="sxs-lookup"><span data-stu-id="a4114-133">We sometimes get support requests to transfer item ownership from one user to another, but you can almost always accomplish this yourself.</span></span>
<span data-ttu-id="a4114-134">Das Übertragen des Besitzes von einem Benutzer auf einen anderen ist einfach eine Kombination aus den beiden oben genannten Funktionen.</span><span class="sxs-lookup"><span data-stu-id="a4114-134">Transferring ownership from one user to another is simply a combination of the two features above.</span></span>

1. <span data-ttu-id="a4114-135">Der aktuelle Besitzer lädt den neuen Benutzer als Mitbesitzer ein, und der neue Benutzer akzeptiert die Einladung.</span><span class="sxs-lookup"><span data-stu-id="a4114-135">The current owner invites the new user to become a co-owner and the new user accepts the invite;</span></span>
2. <span data-ttu-id="a4114-136">Der neue Benutzer entfernt den alten Benutzer aus der Liste der Besitzer.</span><span class="sxs-lookup"><span data-stu-id="a4114-136">The new user removes the old user from the list of owners.</span></span>

<span data-ttu-id="a4114-137">Diese Anfrage ist über mehrere Formulare eingegangen, der Prozess funktioniert aber immer gleich.</span><span class="sxs-lookup"><span data-stu-id="a4114-137">This request has come in under a couple forms but the process works the same.</span></span>

- <span data-ttu-id="a4114-138">Der Besitz eines Elements ändert sich von einem Entwickler zu einem anderen.</span><span class="sxs-lookup"><span data-stu-id="a4114-138">The item ownership is changing from one developer to another</span></span>
- <span data-ttu-id="a4114-139">Das Element wurde versehentlich über das falsche Konto veröffentlicht.</span><span class="sxs-lookup"><span data-stu-id="a4114-139">The item was accidentally published using the wrong account</span></span>


## <a name="orphaned-items"></a><span data-ttu-id="a4114-140">Verwaiste Elemente</span><span class="sxs-lookup"><span data-stu-id="a4114-140">Orphaned Items</span></span>

<span data-ttu-id="a4114-141">Ein letztes Szenario ist aufgetreten, wenn auch nicht häufig.</span><span class="sxs-lookup"><span data-stu-id="a4114-141">One last scenario has occurred, but not many times.</span></span>
<span data-ttu-id="a4114-142">Elemente waren verwaist und das einzige Elementbesitzerkonto kann nicht zum Hinzufügen neuer Besitzer verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="a4114-142">Items have become orphans and the only item owner account cannot be used to add new owners.</span></span>
<span data-ttu-id="a4114-143">Im Folgenden sind einige Beispiele für dieses Szenario aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="a4114-143">Here are some examples of this scenario:</span></span>

- <span data-ttu-id="a4114-144">Dem Konto des Besitzers ist eine E-Mail-Adresse zugeordnet, die nicht mehr existiert, und der Benutzer hat das Kennwort vergessen.</span><span class="sxs-lookup"><span data-stu-id="a4114-144">The owner's account is associated with an email address that no longer exists and the user has forgotten their password</span></span>
- <span data-ttu-id="a4114-145">Der registrierte Besitzer hat das Unternehmen verlassen, in dem das Element erzeugt wird, und kann nicht erreicht werden, um den Besitz des Elements zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="a4114-145">The registered owner has left the company that produces the item and cannot be reached to update the item ownership</span></span>
- <span data-ttu-id="a4114-146">Aufgrund eines Fehlers, der nur wenige Elemente betrifft, befindet sich das Element ohne Besitzer im Katalog.</span><span class="sxs-lookup"><span data-stu-id="a4114-146">Due to a bug that has only affected a handful of items, the item is somehow ownerless on the gallery</span></span>

<span data-ttu-id="a4114-147">Die PowerShell-Katalogadministratoren können für jedes Element auf den Link „Besitzer verwalten“ zugreifen.</span><span class="sxs-lookup"><span data-stu-id="a4114-147">The PowerShell Gallery Administrators can access the 'Manage Owners' link for any item.</span></span>
<span data-ttu-id="a4114-148">Wenn Sie der rechtmäßige Besitzer eines Elements sind und den aktuellen Besitzer des Elements nicht erreichen können, um Besitzberechtigungen zu erlangen, wenden Sie sich über den Link „Missbrauch melden“ im Katalog an die PowerShell-Katalogadministratoren.</span><span class="sxs-lookup"><span data-stu-id="a4114-148">If you are the rightful owner of a item and cannot reach the current owner to gain ownership permissions, then use the 'Report Abuse' link on the gallery to reach the PowerShell Gallery Administrators.</span></span>
<span data-ttu-id="a4114-149">Wir befolgen dann einen Prozess, um Ihren Besitz des Elements zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="a4114-149">We will then follow a process to verify your ownership of the item.</span></span>
<span data-ttu-id="a4114-150">Wenn wir feststellen, dass Sie der Besitzer des Elements sein sollten, verwenden wir selbst den Link „Besitzer verwalten“ für das Element und senden Ihnen die Einladung als Besitzer.</span><span class="sxs-lookup"><span data-stu-id="a4114-150">If we determine you should be an owner of the item, we will use the 'Manage Owners' link for the item ourselves and send you the invite to become an owner.</span></span>
<span data-ttu-id="a4114-151">Dies erfolgt jedoch erst, nachdem wir Sie als Besitzer bestätigt haben, und der Vorgang variiert je nach den Umständen.</span><span class="sxs-lookup"><span data-stu-id="a4114-151">We will only do this after verifying that you should be an owner and the process for this varies by circumstances.</span></span>
<span data-ttu-id="a4114-152">Oft verwenden wir die Projekt-URL des Elements, um eine Möglichkeit zum Kontaktieren des Projektbesitzers zu finden. Gelegentlich wenden wir uns jedoch auch über Twitter, E-Mail oder andere Methoden an den Besitzer.</span><span class="sxs-lookup"><span data-stu-id="a4114-152">Often times, we will use the item's Project URL to find a way to contact the project owner, but we may also use Twitter, Email, or other means for contacting the project owner.</span></span>