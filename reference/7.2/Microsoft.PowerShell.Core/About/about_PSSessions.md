---
description: Beschreibt PowerShell-Sitzungen (pssessions) und erläutert, wie eine permanente Verbindung mit einem Remote Computer hergestellt wird.
Locale: en-US
ms.date: 01/03/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_pssessions?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_PSSessions
ms.openlocfilehash: edc7109f3f79376ac1d348d3c3cd65e3a8d3e69c
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99597364"
---
# <a name="about-pssessions"></a><span data-ttu-id="a154e-103">Informationen zu pssessions</span><span class="sxs-lookup"><span data-stu-id="a154e-103">About PSSessions</span></span>

## <a name="short-description"></a><span data-ttu-id="a154e-104">Kurze Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a154e-104">Short Description</span></span>
<span data-ttu-id="a154e-105">Beschreibt PowerShell-Sitzungen (pssessions) und erläutert, wie eine permanente Verbindung mit einem Remote Computer hergestellt wird.</span><span class="sxs-lookup"><span data-stu-id="a154e-105">Describes PowerShell sessions (PSSessions) and explains how to establish a persistent connection to a remote computer.</span></span>

## <a name="long-description"></a><span data-ttu-id="a154e-106">Lange Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a154e-106">Long Description</span></span>

<span data-ttu-id="a154e-107">Zum Ausführen von PowerShell-Befehlen auf einem Remote Computer können Sie den **Computername** -Parameter eines Cmdlets verwenden, oder Sie können eine PowerShell-Sitzung (PSSession) erstellen und Befehle in der PSSession ausführen.</span><span class="sxs-lookup"><span data-stu-id="a154e-107">To run PowerShell commands on a remote computer, you can use the **ComputerName** parameter of a cmdlet, or you can create a PowerShell session (PSSession) and run commands in the PSSession.</span></span>

<span data-ttu-id="a154e-108">Wenn Sie eine PSSession erstellen, stellt PowerShell eine permanente Verbindung mit dem Remote Computer her.</span><span class="sxs-lookup"><span data-stu-id="a154e-108">When you create a PSSession, PowerShell establishes a persistent connection to the remote computer.</span></span> <span data-ttu-id="a154e-109">Verwenden Sie eine PSSession, um eine Reihe verwandter Befehle auf einem Remote Computer auszuführen.</span><span class="sxs-lookup"><span data-stu-id="a154e-109">Use a PSSession to run a series of related commands on a remote computer.</span></span> <span data-ttu-id="a154e-110">Befehle, die in derselben PSSession ausgeführt werden, können Daten gemeinsam nutzen, wie z. b. die Werte von Variablen, Aliasen und Funktionen.</span><span class="sxs-lookup"><span data-stu-id="a154e-110">Commands that run in the same PSSession can share data, such as the values of variables, aliases, and functions.</span></span>

<span data-ttu-id="a154e-111">Sie können auch eine PSSession auf dem lokalen Computer erstellen und darin Befehle ausführen.</span><span class="sxs-lookup"><span data-stu-id="a154e-111">You can also create a PSSession on the local computer and run commands in it.</span></span>
<span data-ttu-id="a154e-112">Eine lokale PSSession verwendet die PowerShell-Remoting-Infrastruktur, um die PSSession zu erstellen und zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="a154e-112">A local PSSession uses the PowerShell remoting infrastructure to create and maintain the PSSession.</span></span>

<span data-ttu-id="a154e-113">Ab Windows PowerShell 3,0 sind pssessions unabhängig von den Sitzungen, in denen Sie erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="a154e-113">Beginning in Windows PowerShell 3.0, PSSessions are independent of the sessions in which they are created.</span></span> <span data-ttu-id="a154e-114">Aktive pssessions werden auf dem Remote Computer (oder dem Computer am Remote Ende oder "serverseitig" der Verbindung) verwaltet.</span><span class="sxs-lookup"><span data-stu-id="a154e-114">Active PSSessions are maintained on the remote computer (or the computer at the remote end or "server-side" of the connection).</span></span> <span data-ttu-id="a154e-115">Demzufolge können Sie die Verbindung mit der PSSession trennen und zu einem späteren Zeitpunkt vom gleichen Computer oder von einem anderen Computer aus eine Verbindung mit der PSSession herstellen.</span><span class="sxs-lookup"><span data-stu-id="a154e-115">As a result, you can disconnect from the PSSession and reconnect to it at a later time from the same computer or from a different computer.</span></span>

<span data-ttu-id="a154e-116">In diesem Thema wird erläutert, wie Sie pssessions erstellen, verwenden, erhalten und löschen.</span><span class="sxs-lookup"><span data-stu-id="a154e-116">This topic explains how to create, use, get, and delete PSSessions.</span></span> <span data-ttu-id="a154e-117">Weitere Informationen finden Sie unter [about_PSSession_Details](about_PSSession_Details.md).</span><span class="sxs-lookup"><span data-stu-id="a154e-117">For more advanced information, see [about_PSSession_Details](about_PSSession_Details.md).</span></span>

<span data-ttu-id="a154e-118">Hinweis: pssessions verwenden die PowerShell-Remoting-Infrastruktur.</span><span class="sxs-lookup"><span data-stu-id="a154e-118">Note: PSSessions use the PowerShell remoting infrastructure.</span></span> <span data-ttu-id="a154e-119">Um pssessions verwenden zu können, müssen die lokalen Computer und Remote Computer für Remoting konfiguriert sein.</span><span class="sxs-lookup"><span data-stu-id="a154e-119">To use PSSessions, the local and remote computers must be configured for remoting.</span></span>
<span data-ttu-id="a154e-120">Weitere Informationen finden Sie unter [about_Remote_Requirements](about_Remote_Requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a154e-120">For more information, see [about_Remote_Requirements](about_Remote_Requirements.md).</span></span>

<span data-ttu-id="a154e-121">In Windows Vista und höheren Versionen von Windows müssen Sie PowerShell mit der Option "als Administrator ausführen" starten, um eine PSSession auf einem lokalen Computer zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="a154e-121">In Windows Vista and later versions of Windows, to create a PSSession on a local computer, you must start PowerShell with the "Run as administrator" option.</span></span>

## <a name="what-is-a-session"></a><span data-ttu-id="a154e-122">Was ist eine Sitzung?</span><span class="sxs-lookup"><span data-stu-id="a154e-122">What Is a Session?</span></span>

<span data-ttu-id="a154e-123">Eine Sitzung ist eine Umgebung, in der PowerShell ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="a154e-123">A session is an environment in which PowerShell runs.</span></span>

<span data-ttu-id="a154e-124">Jedes Mal, wenn Sie PowerShell starten, wird eine Sitzung für Sie erstellt, und Sie können Befehle in der Sitzung ausführen.</span><span class="sxs-lookup"><span data-stu-id="a154e-124">Each time you start PowerShell, a session is created for you, and you can run commands in the session.</span></span> <span data-ttu-id="a154e-125">Sie können Ihrer Sitzung auch Elemente hinzufügen, z. b. Module und Snap-Ins, und Sie können Elemente wie Variablen, Funktionen und Aliase erstellen.</span><span class="sxs-lookup"><span data-stu-id="a154e-125">You can also add items to your session, such as modules and snap-ins, and you can create items, such as variables, functions, and aliases.</span></span> <span data-ttu-id="a154e-126">Diese Elemente sind nur in der Sitzung vorhanden und werden gelöscht, wenn die Sitzung beendet wird.</span><span class="sxs-lookup"><span data-stu-id="a154e-126">These items exist only in the session and are deleted when the session ends.</span></span>

<span data-ttu-id="a154e-127">Sie können auch Benutzer verwaltete Sitzungen erstellen, die auf dem lokalen Computer oder auf einem Remote Computer als "PowerShell-Sitzungen" oder "pssessions" bezeichnet werden.</span><span class="sxs-lookup"><span data-stu-id="a154e-127">You can also create user-managed sessions, known as " PowerShell sessions" or "PSSessions," on the local computer or on a remote computer.</span></span> <span data-ttu-id="a154e-128">Ebenso wie die Standard Sitzung können Sie Befehle in einer PSSession ausführen und Elemente hinzufügen und erstellen.</span><span class="sxs-lookup"><span data-stu-id="a154e-128">Like the default session, you can run commands in a PSSession and add and create items.</span></span> <span data-ttu-id="a154e-129">Anders als bei der Sitzung, die automatisch gestartet wird, können Sie jedoch die von Ihnen erstellten pssessions steuern.</span><span class="sxs-lookup"><span data-stu-id="a154e-129">However, unlike the session that starts automatically, you can control the PSSessions that you create.</span></span> <span data-ttu-id="a154e-130">Sie können Sie erhalten, erstellen, konfigurieren und entfernen, die Verbindung trennen und Wiederherstellen und mehrere Befehle in derselben PSSession ausführen.</span><span class="sxs-lookup"><span data-stu-id="a154e-130">You can get, create, configure, and remove them, disconnect and reconnect to them, and run multiple commands in the same PSSession.</span></span> <span data-ttu-id="a154e-131">Die PSSession bleibt verfügbar, bis Sie Sie löschen oder ein Timeout auftritt.</span><span class="sxs-lookup"><span data-stu-id="a154e-131">The PSSession remains available until you delete it or it times out.</span></span>

<span data-ttu-id="a154e-132">In der Regel erstellen Sie eine PSSession, um eine Reihe verwandter Befehle auf einem Remote Computer auszuführen.</span><span class="sxs-lookup"><span data-stu-id="a154e-132">Typically, you create a PSSession to run a series of related commands on a remote computer.</span></span> <span data-ttu-id="a154e-133">Wenn Sie eine PSSession auf einem Remote Computer erstellen, stellt PowerShell eine permanente Verbindung mit dem Remote Computer her, um die Sitzung zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="a154e-133">When you create a PSSession on a remote computer, PowerShell establishes a persistent connection to the remote computer to support the session.</span></span>

<span data-ttu-id="a154e-134">Wenn Sie den **Computername** -Parameter des `Invoke-Command` `Enter-PSSession` Cmdlets oder verwenden, um einen Remote Befehl auszuführen oder eine interaktive Sitzung zu starten, erstellt PowerShell eine temporäre Sitzung auf dem Remote Computer und schließt die Sitzung, sobald der Befehl abgeschlossen ist oder sobald die interaktive Sitzung beendet ist.</span><span class="sxs-lookup"><span data-stu-id="a154e-134">If you use the **ComputerName** parameter of the `Invoke-Command` or `Enter-PSSession` cmdlet to run a remote command or to start an interactive session, PowerShell creates a temporary session on the remote computer and closes the session as soon as the command is complete or as soon as the interactive session ends.</span></span> <span data-ttu-id="a154e-135">Diese temporären Sitzungen können nicht gesteuert werden, und Sie können nicht für mehr als einen einzelnen Befehl oder eine einzelne interaktive Sitzung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="a154e-135">You cannot control these temporary sessions, and you cannot use them for more than a single command or a single interactive session.</span></span>

<span data-ttu-id="a154e-136">In PowerShell ist die "aktuelle Sitzung" die Sitzung, in der Sie arbeiten.</span><span class="sxs-lookup"><span data-stu-id="a154e-136">In PowerShell, the "current session" is the session that you are working in.</span></span> <span data-ttu-id="a154e-137">Die "aktuelle Sitzung" kann auf eine beliebige Sitzung verweisen, einschließlich einer temporären Sitzung oder einer PSSession.</span><span class="sxs-lookup"><span data-stu-id="a154e-137">The "current session" can refer to any session, including a temporary session or a PSSession.</span></span>

## <a name="why-use-a-pssession"></a><span data-ttu-id="a154e-138">Gründe für die Verwendung einer PSSession</span><span class="sxs-lookup"><span data-stu-id="a154e-138">Why Use a PSSession?</span></span>

<span data-ttu-id="a154e-139">Verwenden Sie eine PSSession, wenn eine permanente Verbindung mit einem Remote Computer erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="a154e-139">Use a PSSession when you need a persistent connection to a remote computer.</span></span>
<span data-ttu-id="a154e-140">Mit einer PSSession können Sie eine Reihe von Befehlen ausführen, die Daten gemeinsam nutzen, wie z. b. den Wert von Variablen, den Inhalt einer Funktion oder die Definition eines Alias.</span><span class="sxs-lookup"><span data-stu-id="a154e-140">With a PSSession, you can run a series of commands that share data, such as the value of variables, the contents of a function, or the definition of an alias.</span></span>

<span data-ttu-id="a154e-141">Sie können Remote Befehle ausführen, ohne eine PSSession zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="a154e-141">You can run remote commands without creating a PSSession.</span></span> <span data-ttu-id="a154e-142">Verwenden Sie den **Computername** -Parameter von Remote fähigen Cmdlets, um einen einzelnen Befehl oder eine Reihe von nicht verknüpften Befehlen auf einem oder mehreren Computern auszuführen.</span><span class="sxs-lookup"><span data-stu-id="a154e-142">Use the **ComputerName** parameter of remote-enabled cmdlets to run a single command or a series of unrelated commands on one or many computers.</span></span>

<span data-ttu-id="a154e-143">Wenn Sie den **Computername** -Parameter von `Invoke-Command` oder verwenden `Enter-PSSession` , stellt PowerShell eine temporäre Verbindung mit dem Remote Computer her und schließt dann die Verbindung, sobald der Befehl abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="a154e-143">When you use the **ComputerName** parameter of `Invoke-Command` or `Enter-PSSession`, PowerShell establishes a temporary connection to the remote computer and then closes the connection as soon as the command is complete.</span></span> <span data-ttu-id="a154e-144">Alle Datenelemente, die Sie erstellen, gehen verloren, wenn die Verbindung geschlossen wird.</span><span class="sxs-lookup"><span data-stu-id="a154e-144">Any data elements that you create are lost when the connection is closed.</span></span>

<span data-ttu-id="a154e-145">Andere Cmdlets, die über einen **Computername** -Parameter verfügen, z `Get-Eventlog` . b `Get-WmiObject` . und, verwenden unterschiedliche Remoting-Technologien, um Daten zu erfassen.</span><span class="sxs-lookup"><span data-stu-id="a154e-145">Other cmdlets that have a **ComputerName** parameter, such as `Get-Eventlog` and `Get-WmiObject`, use different remoting technologies to gather data.</span></span> <span data-ttu-id="a154e-146">Keine erstellt eine permanente Verbindung wie eine PSSession.</span><span class="sxs-lookup"><span data-stu-id="a154e-146">None create a persistent connection like a PSSession.</span></span>

## <a name="how-to-create-a-pssession"></a><span data-ttu-id="a154e-147">Erstellen einer PSSession</span><span class="sxs-lookup"><span data-stu-id="a154e-147">How to Create a PSSession</span></span>

<span data-ttu-id="a154e-148">Verwenden Sie das-Cmdlet, um eine PSSession zu erstellen `New-PSSession` .</span><span class="sxs-lookup"><span data-stu-id="a154e-148">To create a PSSession, use the `New-PSSession` cmdlet.</span></span> <span data-ttu-id="a154e-149">Verwenden Sie den **Computername** -Parameter des Cmdlets, um die PSSession auf einem Remote Computer zu erstellen `New-PSSession` .</span><span class="sxs-lookup"><span data-stu-id="a154e-149">To create the PSSession on a remote computer, use the **ComputerName** parameter of the `New-PSSession` cmdlet.</span></span>

<span data-ttu-id="a154e-150">Der folgende Befehl erstellt z. b. eine neue PSSession auf dem Server01-Computer.</span><span class="sxs-lookup"><span data-stu-id="a154e-150">For example, the following command creates a new PSSession on the Server01 computer.</span></span>

```powershell
New-PSSession -ComputerName Server01
```

<span data-ttu-id="a154e-151">Wenn Sie den Befehl übermitteln, `New-PSSession` erstellt die PSSession und gibt ein Objekt zurück, das die PSSession darstellt.</span><span class="sxs-lookup"><span data-stu-id="a154e-151">When you submit the command, `New-PSSession` creates the PSSession and returns an object that represents the PSSession.</span></span> <span data-ttu-id="a154e-152">Sie können das Objekt in einer Variablen speichern, wenn Sie die PSSession erstellen, oder Sie können einen `Get-PSSession` Befehl verwenden, um die PSSession zu einem späteren Zeitpunkt abzurufen.</span><span class="sxs-lookup"><span data-stu-id="a154e-152">You can save the object in a variable when you create the PSSession, or you can use a `Get-PSSession` command to get the PSSession at a later time.</span></span>

<span data-ttu-id="a154e-153">Der folgende Befehl erstellt z. b. eine neue PSSession auf dem Server01-Computer und speichert das resultierende Objekt in der $PS Variable.</span><span class="sxs-lookup"><span data-stu-id="a154e-153">For example, the following command creates a new PSSession on the Server01 computer and saves the resulting object in the $ps variable.</span></span>

```powershell
$ps = New-PSSession -ComputerName Server01
```

## <a name="how-to-create-pssessions-on-multiple-computers"></a><span data-ttu-id="a154e-154">Erstellen von pssessions auf mehreren Computern</span><span class="sxs-lookup"><span data-stu-id="a154e-154">How to Create PSSessions on Multiple Computers</span></span>

<span data-ttu-id="a154e-155">Um pssessions auf mehreren Computern zu erstellen, verwenden Sie den **Computername** -Parameter des `New-PSSession` Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="a154e-155">To create PSSessions on multiple computers, use the **ComputerName** parameter of the `New-PSSession` cmdlet.</span></span> <span data-ttu-id="a154e-156">Geben Sie die Namen der Remote Computer in einer durch Trennzeichen getrennten Liste ein.</span><span class="sxs-lookup"><span data-stu-id="a154e-156">Type the names of the remote computers in a comma-separated list.</span></span>

<span data-ttu-id="a154e-157">Geben Sie z. b. Folgendes ein, um pssessions auf den Computern Server01, Server02 und Server03 zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="a154e-157">For example, to create PSSessions on the Server01, Server02, and Server03 computers, type:</span></span>

```powershell
New-PSSession -ComputerName Server01, Server02, Server03
```

<span data-ttu-id="a154e-158">`New-PSSession` erstellt eine PSSession auf jedem der Remote Computer.</span><span class="sxs-lookup"><span data-stu-id="a154e-158">`New-PSSession` creates one PSSession on each of the remote computers.</span></span>

## <a name="how-to-get-pssessions"></a><span data-ttu-id="a154e-159">Vorgehensweise beim erhalten von pssessions</span><span class="sxs-lookup"><span data-stu-id="a154e-159">How to Get PSSessions</span></span>

<span data-ttu-id="a154e-160">Verwenden Sie das `Get-PSSession` Cmdlet ohne den **Computername** -Parameter, um die in der aktuellen Sitzung erstellten pssessions zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="a154e-160">To get the PSSessions that were created in your current session, use the `Get-PSSession` cmdlet without the **ComputerName** parameter.</span></span> <span data-ttu-id="a154e-161">`Get-PSSession` Gibt den gleichen Objekttyp zurück, der `New-PSSession` zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="a154e-161">`Get-PSSession` returns the same type of object that `New-PSSession` returns.</span></span>

<span data-ttu-id="a154e-162">Der folgende Befehl ruft alle pssessions ab, die in der aktuellen Sitzung erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="a154e-162">The following command gets all the PSSessions that were created in the current session.</span></span>

```powershell
Get-PSSession
```

<span data-ttu-id="a154e-163">Die Standard Anzeige der pssessions zeigt Ihre ID und einen Standard anzeigen Amen an.</span><span class="sxs-lookup"><span data-stu-id="a154e-163">The default display of the PSSessions shows their ID and a default display name.</span></span> <span data-ttu-id="a154e-164">Sie können einen alternativen anzeigen Amen zuweisen, wenn Sie die Sitzung erstellen.</span><span class="sxs-lookup"><span data-stu-id="a154e-164">You can assign an alternate display name when you create the session.</span></span>

```output
Id   Name       ComputerName    State    ConfigurationName
---  ----       ------------    -----    ---------------------
1    Session1   Server01        Opened   Microsoft.PowerShell
2    Session2   Server02        Opened   Microsoft.PowerShell
3    Session3   Server03        Opened   Microsoft.PowerShell
```

<span data-ttu-id="a154e-165">Sie können auch die pssessions in einer Variablen speichern.</span><span class="sxs-lookup"><span data-stu-id="a154e-165">You can also save the PSSessions in a variable.</span></span> <span data-ttu-id="a154e-166">Der folgende Befehl ruft die pssessions ab und speichert Sie in der \$ ps123-Variablen.</span><span class="sxs-lookup"><span data-stu-id="a154e-166">The following command gets the PSSessions and saves them in the \$ps123 variable.</span></span>

```powershell
$ps123 = Get-PSSession
```

<span data-ttu-id="a154e-167">Wenn Sie die PSSession-Cmdlets verwenden, können Sie auf eine PSSession anhand ihrer ID, Ihres Namens oder anhand der Instanz-ID (GUID) verweisen.</span><span class="sxs-lookup"><span data-stu-id="a154e-167">When using the PSSession cmdlets, you can refer to a PSSession by its ID, by its name, or by its instance ID (a GUID).</span></span> <span data-ttu-id="a154e-168">Der folgende Befehl ruft eine PSSession anhand ihrer ID ab und speichert Sie in der \$ PS01-Variablen.</span><span class="sxs-lookup"><span data-stu-id="a154e-168">The following command gets a PSSession by its ID and saves it in the \$ps01 variable.</span></span>

```powershell
$ps01 = Get-PSSession -Id 1
```

<span data-ttu-id="a154e-169">Ab Windows PowerShell 3,0 werden pssessions auf dem Remote Computer verwaltet.</span><span class="sxs-lookup"><span data-stu-id="a154e-169">Beginning in Windows PowerShell 3.0, PSSessions are maintained on the remote computer.</span></span> <span data-ttu-id="a154e-170">Verwenden Sie den **Computername** -Parameter des Cmdlets, um pssessions, die Sie auf bestimmten Remote Computern erstellt haben, zu erhalten `Get-PSSession` .</span><span class="sxs-lookup"><span data-stu-id="a154e-170">To get PSSessions that you created on particular remote computers, use the **ComputerName** parameter of the `Get-PSSession` cmdlet.</span></span> <span data-ttu-id="a154e-171">Mit dem folgenden Befehl werden die auf dem Remote Computer Server01 erstellten pssessions abgerufen.</span><span class="sxs-lookup"><span data-stu-id="a154e-171">The following command gets the PSSessions that you created on the Server01 remote computer.</span></span> <span data-ttu-id="a154e-172">Dies schließt pssessions ein, die in der aktuellen Sitzung und in anderen Sitzungen auf dem lokalen Computer oder auf anderen Computern erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="a154e-172">This includes PSSessions created in the current session and in other sessions on the local computer or other computers.</span></span>

```powershell
Get-PSSession -ComputerName Server01
```

<span data-ttu-id="a154e-173">In Windows PowerShell 2,0 ruft `Get-PSSession` nur die pssessions ab, die in der aktuellen Sitzung erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="a154e-173">In Windows PowerShell 2.0, `Get-PSSession` gets only the PSSessions that were created in the current session.</span></span> <span data-ttu-id="a154e-174">Er ruft keine pssessions ab, die in anderen Sitzungen oder auf anderen Computern erstellt wurden, auch wenn die Sitzungen mit verbunden sind und Befehle auf dem lokalen Computer ausführen.</span><span class="sxs-lookup"><span data-stu-id="a154e-174">It does not get PSSessions that were created in other sessions or on other computers, even if the sessions are connected to and are running commands on the local computer.</span></span>

## <a name="how-to-run-commands-in-a-pssession"></a><span data-ttu-id="a154e-175">Ausführen von Befehlen in einer PSSession</span><span class="sxs-lookup"><span data-stu-id="a154e-175">How to Run Commands in a PSSession</span></span>

<span data-ttu-id="a154e-176">Verwenden Sie das-Cmdlet, um einen Befehl in einer oder mehreren pssessions auszuführen `Invoke-Command` .</span><span class="sxs-lookup"><span data-stu-id="a154e-176">To run a command in one or more PSSessions, use the `Invoke-Command` cmdlet.</span></span>
<span data-ttu-id="a154e-177">Verwenden Sie den Session-Parameter, um die pssessions anzugeben, und den **ScriptBlock** -Parameter, um den Befehl anzugeben.</span><span class="sxs-lookup"><span data-stu-id="a154e-177">Use the Session parameter to specify the PSSessions and the **ScriptBlock** parameter to specify the command.</span></span>

<span data-ttu-id="a154e-178">Wenn Sie z. b. einen `Get-ChildItem` Befehl ("dir") in jeder der drei pssessions ausführen möchten, die in der Variablen "$PS 123" gespeichert sind, geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="a154e-178">For example, to run a `Get-ChildItem` ("dir") command in each of the three PSSessions saved in the $ps123 variable, type:</span></span>

```powershell
Invoke-Command -Session $ps123 -ScriptBlock { Get-ChildItem }
```

## <a name="how-to-delete-pssessions"></a><span data-ttu-id="a154e-179">Löschen von pssessions</span><span class="sxs-lookup"><span data-stu-id="a154e-179">How to Delete PSSessions</span></span>

<span data-ttu-id="a154e-180">Wenn Sie mit der PSSession fertig sind, verwenden Sie das `Remove-PSSession` Cmdlet, um die PSSession zu löschen und die Ressourcen freizugeben, die Sie verwendet haben.</span><span class="sxs-lookup"><span data-stu-id="a154e-180">When you are finished with the PSSession, use the `Remove-PSSession` cmdlet to delete the PSSession and to release the resources that it was using.</span></span>

```powershell
Remove-PSSession -Session $ps
```

<span data-ttu-id="a154e-181">oder</span><span class="sxs-lookup"><span data-stu-id="a154e-181">or</span></span>

```powershell
Remove-PSSession -Id 1
```

<span data-ttu-id="a154e-182">Um eine PSSession von einem Remote Computer zu entfernen, verwenden Sie den **Computername** -Parameter des `Remove-PSSession` Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="a154e-182">To remove a PSSession from a remote computer, use the **ComputerName** parameter of the `Remove-PSSession` cmdlet.</span></span>

```powershell
Remove-PSSession -ComputerName Server01 -Id 1
```

<span data-ttu-id="a154e-183">Wenn Sie die PSSession nicht löschen, bleibt die PSSession zur Verwendung verfügbar, bis ein Timeout eintritt.</span><span class="sxs-lookup"><span data-stu-id="a154e-183">If you do not delete the PSSession, the PSSession remains available for use until it times out.</span></span>

<span data-ttu-id="a154e-184">Sie können auch den **IdleTimeout** -Parameter des `New-PSSessionOption` Cmdlets verwenden, um eine Ablaufzeit für eine Leerlauf-PSSession festzulegen.</span><span class="sxs-lookup"><span data-stu-id="a154e-184">You can also use the **IdleTimeout** parameter of the `New-PSSessionOption` cmdlet to set an expiration time for an idle PSSession.</span></span> <span data-ttu-id="a154e-185">Weitere Informationen finden Sie unter [New-pssessionoption](xref:Microsoft.PowerShell.Core.New-PSSessionOption).</span><span class="sxs-lookup"><span data-stu-id="a154e-185">For more information, see [New-PSSessionOption](xref:Microsoft.PowerShell.Core.New-PSSessionOption).</span></span>

## <a name="the-pssession-cmdlets"></a><span data-ttu-id="a154e-186">Die PSSession-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="a154e-186">The PSSession Cmdlets</span></span>

<span data-ttu-id="a154e-187">Eine Liste der PSSession-Cmdlets erhalten Sie, wenn Sie Folgendes eingeben:</span><span class="sxs-lookup"><span data-stu-id="a154e-187">For a list of PSSession cmdlets, type:</span></span>

```powershell
Get-Help *-PSSession
```

- <span data-ttu-id="a154e-188">Connect-PSSession: verbindet eine PSSession mit der aktuellen Sitzung.</span><span class="sxs-lookup"><span data-stu-id="a154e-188">Connect-PSSession: Connects a PSSession to the current session</span></span>
- <span data-ttu-id="a154e-189">Disconnect-PSSession: trennt eine PSSession von der aktuellen Sitzung.</span><span class="sxs-lookup"><span data-stu-id="a154e-189">Disconnect-PSSession: Disconnects a PSSession from the current session</span></span>
- <span data-ttu-id="a154e-190">Enter-PSSession: startet eine interaktive Sitzung.</span><span class="sxs-lookup"><span data-stu-id="a154e-190">Enter-PSSession: Starts an interactive session</span></span>
- <span data-ttu-id="a154e-191">Exit-PSSession: beendet eine interaktive Sitzung.</span><span class="sxs-lookup"><span data-stu-id="a154e-191">Exit-PSSession: Ends an interactive session</span></span>
- <span data-ttu-id="a154e-192">Get-PSSession: Ruft die pssessions in der aktuellen Sitzung ab.</span><span class="sxs-lookup"><span data-stu-id="a154e-192">Get-PSSession: Gets the PSSessions in the current session</span></span>
- <span data-ttu-id="a154e-193">New-PSSession: erstellt eine neue PSSession auf einem lokalen Computer oder einem Remote Computer.</span><span class="sxs-lookup"><span data-stu-id="a154e-193">New-PSSession: Creates a new PSSession on a local or remote computer</span></span>
- <span data-ttu-id="a154e-194">Receive-PSSession: Ruft die Ergebnisse von Befehlen ab, die in einer getrennten Sitzung ausgeführt wurden.</span><span class="sxs-lookup"><span data-stu-id="a154e-194">Receive-PSSession: Gets the results of commands that ran in a disconnected session</span></span>
- <span data-ttu-id="a154e-195">Remove-PSSession: Löscht die pssessions in der aktuellen Sitzung.</span><span class="sxs-lookup"><span data-stu-id="a154e-195">Remove-PSSession: Deletes the PSSessions in the current session</span></span>

## <a name="for-more-information"></a><span data-ttu-id="a154e-196">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a154e-196">For More Information</span></span>

<span data-ttu-id="a154e-197">Weitere Informationen zu pssessions finden Sie unter [about_PSSession_Details](about_PSSession_Details.md).</span><span class="sxs-lookup"><span data-stu-id="a154e-197">For more information about PSSessions, see [about_PSSession_Details](about_PSSession_Details.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="a154e-198">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="a154e-198">See Also</span></span>

[<span data-ttu-id="a154e-199">about_Remote</span><span class="sxs-lookup"><span data-stu-id="a154e-199">about_Remote</span></span>](about_Remote.md)

[<span data-ttu-id="a154e-200">about_Remote_Disconnected_Sessions</span><span class="sxs-lookup"><span data-stu-id="a154e-200">about_Remote_Disconnected_Sessions</span></span>](about_Remote_Disconnected_Sessions.md)

[<span data-ttu-id="a154e-201">about_Remote_Requirements</span><span class="sxs-lookup"><span data-stu-id="a154e-201">about_Remote_Requirements</span></span>](about_Remote_Requirements.md)

[<span data-ttu-id="a154e-202">Connect-PSSession</span><span class="sxs-lookup"><span data-stu-id="a154e-202">Connect-PSSession</span></span>](xref:Microsoft.PowerShell.Core.Connect-PSSession)

[<span data-ttu-id="a154e-203">Disconnect-PSSession</span><span class="sxs-lookup"><span data-stu-id="a154e-203">Disconnect-PSSession</span></span>](xref:Microsoft.PowerShell.Core.Disconnect-PSSession)

[<span data-ttu-id="a154e-204">Enter-PSSession</span><span class="sxs-lookup"><span data-stu-id="a154e-204">Enter-PSSession</span></span>](xref:Microsoft.PowerShell.Core.Enter-PSSession)

[<span data-ttu-id="a154e-205">Exit-PSSession</span><span class="sxs-lookup"><span data-stu-id="a154e-205">Exit-PSSession</span></span>](xref:Microsoft.PowerShell.Core.Exit-PSSession)

[<span data-ttu-id="a154e-206">Get-PSSession</span><span class="sxs-lookup"><span data-stu-id="a154e-206">Get-PSSession</span></span>](xref:Microsoft.PowerShell.Core.Get-PSSession)

[<span data-ttu-id="a154e-207">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="a154e-207">Invoke-Command</span></span>](xref:Microsoft.PowerShell.Core.Invoke-Command)

[<span data-ttu-id="a154e-208">New-PSSession</span><span class="sxs-lookup"><span data-stu-id="a154e-208">New-PSSession</span></span>](xref:Microsoft.PowerShell.Core.New-PSSession)

[<span data-ttu-id="a154e-209">Remove-PSSession</span><span class="sxs-lookup"><span data-stu-id="a154e-209">Remove-PSSession</span></span>](xref:Microsoft.PowerShell.Core.Remove-PSSession)
