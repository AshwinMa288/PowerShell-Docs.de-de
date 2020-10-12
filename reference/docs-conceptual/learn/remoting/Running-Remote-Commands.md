---
ms.date: 08/21/2020
keywords: powershell,cmdlet
title: Ausführen von Remotebefehlen
ms.openlocfilehash: f12d08b03757b24d1de50402b301faff193f27be
ms.sourcegitcommit: 9d95532afe81c235c8094eae28ab84b2f77f8c48
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/07/2020
ms.locfileid: "91814734"
---
# <a name="running-remote-commands"></a><span data-ttu-id="e7c91-103">Ausführen von Remotebefehlen</span><span class="sxs-lookup"><span data-stu-id="e7c91-103">Running Remote Commands</span></span>

<span data-ttu-id="e7c91-104">Mit einem einzigen PowerShell-Befehl können Sie Befehle auf einem oder Hunderten von Computern ausführen.</span><span class="sxs-lookup"><span data-stu-id="e7c91-104">You can run commands on one or hundreds of computers with a single PowerShell command.</span></span> <span data-ttu-id="e7c91-105">Windows PowerShell unterstützt das Remotecomputing mithilfe verschiedener Technologien, unter anderem WMI, RPC und WS-Management.</span><span class="sxs-lookup"><span data-stu-id="e7c91-105">Windows PowerShell supports remote computing by using various technologies, including WMI, RPC, and WS-Management.</span></span>

<span data-ttu-id="e7c91-106">PowerShell Core unterstützt WMI, WS-Management und SSH-Remoting.</span><span class="sxs-lookup"><span data-stu-id="e7c91-106">PowerShell Core supports WMI, WS-Management, and SSH remoting.</span></span> <span data-ttu-id="e7c91-107">In PowerShell 6 wird RPC nicht mehr unterstützt.</span><span class="sxs-lookup"><span data-stu-id="e7c91-107">In PowerShell 6, RPC is no longer supported.</span></span> <span data-ttu-id="e7c91-108">Ab PowerShell 7 wird RPC nur in Windows unterstützt.</span><span class="sxs-lookup"><span data-stu-id="e7c91-108">In PowerShell 7 and above, RPC is supported only in Windows.</span></span>

<span data-ttu-id="e7c91-109">Weitere Informationen zu Remoting in PowerShell Core finden Sie in den folgenden Artikeln:</span><span class="sxs-lookup"><span data-stu-id="e7c91-109">For more information about remoting in PowerShell Core, see the following articles:</span></span>

- <span data-ttu-id="e7c91-110">[SSH-Remoting in PowerShell Core][ssh-remoting]</span><span class="sxs-lookup"><span data-stu-id="e7c91-110">[SSH Remoting in PowerShell Core][ssh-remoting]</span></span>
- <span data-ttu-id="e7c91-111">[WSMan-Remoting in PowerShell Core][wsman-remoting]</span><span class="sxs-lookup"><span data-stu-id="e7c91-111">[WSMan Remoting in PowerShell Core][wsman-remoting]</span></span>

## <a name="windows-powershell-remoting-without-configuration"></a><span data-ttu-id="e7c91-112">Windows PowerShell-Remoting ohne Konfiguration</span><span class="sxs-lookup"><span data-stu-id="e7c91-112">Windows PowerShell Remoting Without Configuration</span></span>

<span data-ttu-id="e7c91-113">Viele Windows PowerShell-Cmdlets verfügen über einen „ComputerName“-Parameter, mit dessen Hilfe Sie Daten auf einem oder mehreren Remotecomputern sammeln und Einstellungsänderungen vornehmen können.</span><span class="sxs-lookup"><span data-stu-id="e7c91-113">Many Windows PowerShell cmdlets have the ComputerName parameter that enables you to collect data and change settings on one or more remote computers.</span></span> <span data-ttu-id="e7c91-114">Diese Cmdlets verwenden unterschiedliche Kommunikationsprotokolle und funktionieren auf allen Windows-Betriebssystemen ohne besondere Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="e7c91-114">These cmdlets use varying communication protocols and work on all Windows operating systems without any special configuration.</span></span>

<span data-ttu-id="e7c91-115">Zu diesem Cmdlets zählen:</span><span class="sxs-lookup"><span data-stu-id="e7c91-115">These cmdlets include:</span></span>

- [<span data-ttu-id="e7c91-116">Restart-Computer</span><span class="sxs-lookup"><span data-stu-id="e7c91-116">Restart-Computer</span></span>](/powershell/module/microsoft.powershell.management/restart-computer)
- [<span data-ttu-id="e7c91-117">Test-Connection</span><span class="sxs-lookup"><span data-stu-id="e7c91-117">Test-Connection</span></span>](/powershell/module/microsoft.powershell.management/test-connection)
- [<span data-ttu-id="e7c91-118">Clear-EventLog</span><span class="sxs-lookup"><span data-stu-id="e7c91-118">Clear-EventLog</span></span>](/powershell/module/microsoft.powershell.management/clear-eventlog)
- [<span data-ttu-id="e7c91-119">Get-EventLog</span><span class="sxs-lookup"><span data-stu-id="e7c91-119">Get-EventLog</span></span>](/powershell/module/microsoft.powershell.management/get-eventlog)
- [<span data-ttu-id="e7c91-120">Get-HotFix</span><span class="sxs-lookup"><span data-stu-id="e7c91-120">Get-HotFix</span></span>](/powershell/module/microsoft.powershell.management/get-hotfix)
- [<span data-ttu-id="e7c91-121">Get-Process</span><span class="sxs-lookup"><span data-stu-id="e7c91-121">Get-Process</span></span>](/powershell/module/microsoft.powershell.management/get-process)
- [<span data-ttu-id="e7c91-122">Get-Service</span><span class="sxs-lookup"><span data-stu-id="e7c91-122">Get-Service</span></span>](/powershell/module/microsoft.powershell.management/get-service)
- [<span data-ttu-id="e7c91-123">Set-Service</span><span class="sxs-lookup"><span data-stu-id="e7c91-123">Set-Service</span></span>](/powershell/module/microsoft.powershell.management/set-service)
- [<span data-ttu-id="e7c91-124">Get-WinEvent</span><span class="sxs-lookup"><span data-stu-id="e7c91-124">Get-WinEvent</span></span>](/powershell/module/microsoft.powershell.diagnostics/get-winevent)
- [<span data-ttu-id="e7c91-125">Get-WmiObject</span><span class="sxs-lookup"><span data-stu-id="e7c91-125">Get-WmiObject</span></span>](/powershell/module/microsoft.powershell.management/get-wmiobject)

<span data-ttu-id="e7c91-126">In der Regel weisen Cmdlets, die Remoting ohne besondere Konfiguration unterstützen, den „ComputerName“-Parameter und nicht den „Session“-Parameter auf.</span><span class="sxs-lookup"><span data-stu-id="e7c91-126">Typically, cmdlets that support remoting without special configuration have the ComputerName parameter and don't have the Session parameter.</span></span> <span data-ttu-id="e7c91-127">Um diese Cmdlets in Ihrer Sitzung zu finden, geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="e7c91-127">To find these cmdlets in your session, type:</span></span>

```powershell
Get-Command | where { $_.parameters.keys -contains "ComputerName" -and $_.parameters.keys -notcontains "Session"}
```

## <a name="windows-powershell-remoting"></a><span data-ttu-id="e7c91-128">Windows PowerShell-Remoting</span><span class="sxs-lookup"><span data-stu-id="e7c91-128">Windows PowerShell Remoting</span></span>

<span data-ttu-id="e7c91-129">Über das WS-Management-Protokoll können Sie mit Windows PowerShell-Remoting jeden Windows PowerShell-Befehl auf einem oder mehreren Remotecomputern ausführen.</span><span class="sxs-lookup"><span data-stu-id="e7c91-129">Using the WS-Management protocol, Windows PowerShell remoting lets you run any Windows PowerShell command on one or more remote computers.</span></span> <span data-ttu-id="e7c91-130">Sie können dauerhafte Verbindungen herstellen, interaktive Sitzungen starten und Skripts auf Remotecomputern ausführen.</span><span class="sxs-lookup"><span data-stu-id="e7c91-130">You can establish persistent connections, start interactive sessions, and run scripts on remote computers.</span></span>

<span data-ttu-id="e7c91-131">Um Windows PowerShell-Remoting zu verwenden, muss der Remotecomputer für die Remoteverwaltung konfiguriert sein.</span><span class="sxs-lookup"><span data-stu-id="e7c91-131">To use Windows PowerShell remoting, the remote computer must be configured for remote management.</span></span>
<span data-ttu-id="e7c91-132">Weitere Informationen und Anweisungen hierzu finden Sie unter [Informationen zu Remoteanforderungen](/powershell/module/microsoft.powershell.core/about/about_remote_requirements).</span><span class="sxs-lookup"><span data-stu-id="e7c91-132">For more information, including instructions, see [About Remote Requirements](/powershell/module/microsoft.powershell.core/about/about_remote_requirements).</span></span>

<span data-ttu-id="e7c91-133">Nachdem Sie Windows PowerShell-Remoting konfiguriert haben, stehen Ihnen viele Remotingstrategien zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="e7c91-133">Once you have configured Windows PowerShell remoting, many remoting strategies are available to you.</span></span>
<span data-ttu-id="e7c91-134">In diesem Artikel werden nur einige davon aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="e7c91-134">This article lists just a few of them.</span></span> <span data-ttu-id="e7c91-135">Weitere Informationen finden Sie unter [Informationen zu Remote](/powershell/module/microsoft.powershell.core/about/about_remote).</span><span class="sxs-lookup"><span data-stu-id="e7c91-135">For more information, see [About Remote](/powershell/module/microsoft.powershell.core/about/about_remote).</span></span>

### <a name="start-an-interactive-session"></a><span data-ttu-id="e7c91-136">Starten einer interaktiven Sitzung</span><span class="sxs-lookup"><span data-stu-id="e7c91-136">Start an Interactive Session</span></span>

<span data-ttu-id="e7c91-137">Um eine interaktive Sitzung mit einem einzelnen Remotecomputer zu starten, verwenden Sie das Cmdlet [Enter-PSSession](/powershell/module/microsoft.powershell.core/enter-pssession).</span><span class="sxs-lookup"><span data-stu-id="e7c91-137">To start an interactive session with a single remote computer, use the [Enter-PSSession](/powershell/module/microsoft.powershell.core/enter-pssession) cmdlet.</span></span> <span data-ttu-id="e7c91-138">Um beispielsweise eine interaktive Sitzung mit dem Remotecomputer „Server01“ zu starten, geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="e7c91-138">For example, to start an interactive session with the Server01 remote computer, type:</span></span>

```powershell
Enter-PSSession Server01
```

<span data-ttu-id="e7c91-139">Die Eingabeaufforderung ändert sich, und es wird der Name des Remotecomputers angezeigt.</span><span class="sxs-lookup"><span data-stu-id="e7c91-139">The command prompt changes to display the name of the remote computer.</span></span> <span data-ttu-id="e7c91-140">Alle Befehle, die Sie an der Eingabeaufforderung eingeben, werden auf dem Remotecomputer ausgeführt, und die Ergebnisse werden auf dem lokalen Computer angezeigt.</span><span class="sxs-lookup"><span data-stu-id="e7c91-140">Any commands that you type at the prompt run on the remote computer and the results are displayed on the local computer.</span></span>

<span data-ttu-id="e7c91-141">Um die interaktive Sitzung zu beenden, geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="e7c91-141">To end the interactive session, type:</span></span>

```powershell
Exit-PSSession
```

<span data-ttu-id="e7c91-142">Weitere Informationen über die Cmdlets „Enter-PSSession“ und „Exit-PSSession“ finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="e7c91-142">For more information about the Enter-PSSession and Exit-PSSession cmdlets, see:</span></span>

- [<span data-ttu-id="e7c91-143">Enter-PSSession</span><span class="sxs-lookup"><span data-stu-id="e7c91-143">Enter-PSSession</span></span>](/powershell/module/microsoft.powershell.core/enter-pssession)
- [<span data-ttu-id="e7c91-144">Exit-PSSession</span><span class="sxs-lookup"><span data-stu-id="e7c91-144">Exit-PSSession</span></span>](/powershell/module/microsoft.powershell.core/exit-pssession)

### <a name="run-a-remote-command"></a><span data-ttu-id="e7c91-145">Ausführen eines Remotebefehls</span><span class="sxs-lookup"><span data-stu-id="e7c91-145">Run a Remote Command</span></span>

<span data-ttu-id="e7c91-146">Zum Ausführen eines Befehls auf einem oder mehreren Computern verwenden Sie das Cmdlet [Invoke-Command](/powershell/module/microsoft.powershell.core/invoke-command).</span><span class="sxs-lookup"><span data-stu-id="e7c91-146">To run a command on one or more computers, use the [Invoke-Command](/powershell/module/microsoft.powershell.core/invoke-command) cmdlet.</span></span> <span data-ttu-id="e7c91-147">Um beispielsweise einen [Get-UICulture](/powershell/module/microsoft.powershell.utility/get-uiculture)-Befehl auf den Remotecomputern „Server01“ und „Server02“ auszuführen, geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="e7c91-147">For example, to run a [Get-UICulture](/powershell/module/microsoft.powershell.utility/get-uiculture) command on the Server01 and Server02 remote computers, type:</span></span>

```powershell
Invoke-Command -ComputerName Server01, Server02 -ScriptBlock {Get-UICulture}
```

<span data-ttu-id="e7c91-148">Die Ausgabe wird an den Computer zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="e7c91-148">The output is returned to your computer.</span></span>

```output
LCID    Name     DisplayName               PSComputerName
----    ----     -----------               --------------
1033    en-US    English (United States)   server01.corp.fabrikam.com
1033    en-US    English (United States)   server02.corp.fabrikam.com
```

### <a name="run-a-script"></a><span data-ttu-id="e7c91-149">Ausführen eines Skripts</span><span class="sxs-lookup"><span data-stu-id="e7c91-149">Run a Script</span></span>

<span data-ttu-id="e7c91-150">Zum Ausführen eines Skripts auf einem oder mehreren Remotecomputern verwenden Sie den Parameter „FilePath“ des Cmdlets `Invoke-Command`.</span><span class="sxs-lookup"><span data-stu-id="e7c91-150">To run a script on one or many remote computers, use the FilePath parameter of the `Invoke-Command` cmdlet.</span></span> <span data-ttu-id="e7c91-151">Das Skript muss sich auf dem lokalen Computer befinden oder für diesen verfügbar sein.</span><span class="sxs-lookup"><span data-stu-id="e7c91-151">The script must be on or accessible to your local computer.</span></span> <span data-ttu-id="e7c91-152">Die Ergebnisse werden an den lokalen Computer zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="e7c91-152">The results are returned to your local computer.</span></span>

<span data-ttu-id="e7c91-153">Der folgende Befehl führt beispielsweise das Skript „DiskCollect.ps1“ auf den Remotecomputern „Server01“ und „Server02“ aus.</span><span class="sxs-lookup"><span data-stu-id="e7c91-153">For example, the following command runs the DiskCollect.ps1 script on the remote computers, Server01 and Server02.</span></span>

```powershell
Invoke-Command -ComputerName Server01, Server02 -FilePath c:\Scripts\DiskCollect.ps1
```

### <a name="establish-a-persistent-connection"></a><span data-ttu-id="e7c91-154">Herstellen einer dauerhaften Verbindung</span><span class="sxs-lookup"><span data-stu-id="e7c91-154">Establish a Persistent Connection</span></span>

<span data-ttu-id="e7c91-155">Verwenden Sie das Cmdlet `New-PSSession`, um eine permanente Sitzung auf einem Remotecomputer zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="e7c91-155">Use the `New-PSSession` cmdlet to create a persistent session on a remote computer.</span></span> <span data-ttu-id="e7c91-156">Das folgende Beispiel erstellt Remotesitzungen auf „Server01“ und „Server02.</span><span class="sxs-lookup"><span data-stu-id="e7c91-156">The following example creates remote sessions on Server01 and Server02.</span></span> <span data-ttu-id="e7c91-157">Die Sitzungsobjekte werden in der Variablen `$s` gespeichert.</span><span class="sxs-lookup"><span data-stu-id="e7c91-157">The session objects are stored in the `$s` variable.</span></span>

```powershell
$s = New-PSSession -ComputerName Server01, Server02
```

<span data-ttu-id="e7c91-158">Nachdem die Sitzungen nun hergestellt sind, können Sie jeden beliebigen Befehl in diesen ausführen.</span><span class="sxs-lookup"><span data-stu-id="e7c91-158">Now that the sessions are established, you can run any command in them.</span></span> <span data-ttu-id="e7c91-159">Und da die Sitzungen permanent sind, können Sie Daten von einem Befehl sammeln und in einem anderen Befehl verwenden.</span><span class="sxs-lookup"><span data-stu-id="e7c91-159">And because the sessions are persistent, you can collect data from one command and use it in another command.</span></span>

<span data-ttu-id="e7c91-160">Beispielsweise führt der folgende Befehl einen „Get-HotFix“-Befehl in den Sitzungen in der Variablen „$s“ aus und speichert die Ergebnisse dann in der Variablen „$h“.</span><span class="sxs-lookup"><span data-stu-id="e7c91-160">For example, the following command runs a Get-HotFix command in the sessions in the $s variable and it saves the results in the $h variable.</span></span> <span data-ttu-id="e7c91-161">Die Variable „$h“ wird in jeder der Sitzungen in „$s“ erstellt, ist jedoch in der lokalen Sitzung nicht vorhanden.</span><span class="sxs-lookup"><span data-stu-id="e7c91-161">The $h variable is created in each of the sessions in $s, but it doesn't exist in the local session.</span></span>

```powershell
Invoke-Command -Session $s {$h = Get-HotFix}
```

<span data-ttu-id="e7c91-162">Nun können Sie die Daten in der Variablen `$h` in der gleichen Sitzung mit anderen Befehlen verwenden.</span><span class="sxs-lookup"><span data-stu-id="e7c91-162">Now you can use the data in the `$h` variable with other commands in the same session.</span></span> <span data-ttu-id="e7c91-163">Die Ergebnisse werden auf dem lokalen Computer angezeigt.</span><span class="sxs-lookup"><span data-stu-id="e7c91-163">The results are displayed on the local computer.</span></span> <span data-ttu-id="e7c91-164">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="e7c91-164">For example:</span></span>

```powershell
Invoke-Command -Session $s {$h | where {$_.InstalledBy -ne "NTAUTHORITY\SYSTEM"}}
```

### <a name="advanced-remoting"></a><span data-ttu-id="e7c91-165">Erweitertes Remoting</span><span class="sxs-lookup"><span data-stu-id="e7c91-165">Advanced Remoting</span></span>

<span data-ttu-id="e7c91-166">Dies sind nur die grundlegenden Möglichkeiten, die die Remoteverwaltung von Windows PowerShell bietet.</span><span class="sxs-lookup"><span data-stu-id="e7c91-166">Windows PowerShell remote management just begins here.</span></span> <span data-ttu-id="e7c91-167">Mithilfe von Cmdlets, die mit Windows PowerShell installiert werden, können Sie Remotesitzungen sowohl von lokaler Seite als auch von Remoteseite aus einrichten und konfigurieren, angepasste und eingeschränkte Sitzungen erstellen, Benutzern über eine Remotesitzung den Import von Befehlen ermöglichen, die tatsächlich implizit in der Remotesitzung ausgeführt werden, die Sicherheit einer Remotesitzung konfigurieren und vieles mehr.</span><span class="sxs-lookup"><span data-stu-id="e7c91-167">By using the cmdlets installed with Windows PowerShell, you can establish and configure remote sessions both from the local and remote ends, create customized and restricted sessions, allow users to import commands from a remote session that actually run implicitly on the remote session, configure the security of a remote session, and much more.</span></span>

<span data-ttu-id="e7c91-168">Windows PowerShell umfasst einen WSMan-Anbieter.</span><span class="sxs-lookup"><span data-stu-id="e7c91-168">Windows PowerShell includes a WSMan provider.</span></span> <span data-ttu-id="e7c91-169">Der Anbieter erstellt ein `WSMAN:`-Laufwerk, dass es Ihnen ermöglicht, durch eine Hierarchie von Konfigurationseinstellungen auf dem lokalen Computer und den Remotecomputern zu navigieren.</span><span class="sxs-lookup"><span data-stu-id="e7c91-169">The provider creates a `WSMAN:` drive that lets you navigate through a hierarchy of configuration settings on the local computer and remote computers.</span></span>

<span data-ttu-id="e7c91-170">Weitere Informationen zum WSMan-Anbieter finden Sie unter [WS-Management-Anbieter](https://technet.microsoft.com/library/dd819476.aspx) und [Informationen zu WS-Management-Cmdlets](/powershell/module/microsoft.wsman.management/about/about_ws-management_cmdlets). Geben Sie alternativ in der Windows PowerShell-Konsole `Get-Help wsman` ein.</span><span class="sxs-lookup"><span data-stu-id="e7c91-170">For more information about the WSMan provider, see [WSMan Provider](https://technet.microsoft.com/library/dd819476.aspx) and [About WS-Management Cmdlets](/powershell/module/microsoft.wsman.management/about/about_ws-management_cmdlets), or in the Windows PowerShell console, type `Get-Help wsman`.</span></span>

<span data-ttu-id="e7c91-171">Weitere Informationen finden Sie in folgenden Quellen:</span><span class="sxs-lookup"><span data-stu-id="e7c91-171">For more information, see:</span></span>

- [<span data-ttu-id="e7c91-172">Häufig gestellte Fragen zu Remote</span><span class="sxs-lookup"><span data-stu-id="e7c91-172">About Remote FAQ</span></span>](https://technet.microsoft.com/library/dd315359.aspx)
- [<span data-ttu-id="e7c91-173">Register-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="e7c91-173">Register-PSSessionConfiguration</span></span>](https://go.microsoft.com/fwlink/?LinkId=821508)
- [<span data-ttu-id="e7c91-174">Import-PSSession</span><span class="sxs-lookup"><span data-stu-id="e7c91-174">Import-PSSession</span></span>](https://go.microsoft.com/fwlink/?LinkId=821821)

<span data-ttu-id="e7c91-175">Hilfe zu Remotingfehlern finden Sie unter [about_Remote_Troubleshooting](https://technet.microsoft.com/library/dd347642.aspx).</span><span class="sxs-lookup"><span data-stu-id="e7c91-175">For help with remoting errors, see [about_Remote_Troubleshooting](https://technet.microsoft.com/library/dd347642.aspx).</span></span>

## <a name="see-also"></a><span data-ttu-id="e7c91-176">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e7c91-176">See Also</span></span>

- [<span data-ttu-id="e7c91-177">about_Remote</span><span class="sxs-lookup"><span data-stu-id="e7c91-177">about_Remote</span></span>](https://technet.microsoft.com/library/9b4a5c87-9162-4adf-bdfe-fbc80b9b8970)
- [<span data-ttu-id="e7c91-178">about_Remote_FAQ</span><span class="sxs-lookup"><span data-stu-id="e7c91-178">about_Remote_FAQ</span></span>](https://technet.microsoft.com/library/e23702fd-9415-4a98-9975-390a4d3adc42)
- [<span data-ttu-id="e7c91-179">about_Remote_Requirements</span><span class="sxs-lookup"><span data-stu-id="e7c91-179">about_Remote_Requirements</span></span>](https://technet.microsoft.com/library/da213949-134c-4741-b307-81f4492ba1bd)
- [<span data-ttu-id="e7c91-180">about_Remote_Troubleshooting</span><span class="sxs-lookup"><span data-stu-id="e7c91-180">about_Remote_Troubleshooting</span></span>](https://technet.microsoft.com/library/2f890148-8578-49ed-85ea-79a489dd6317)
- [<span data-ttu-id="e7c91-181">about_PSSessions</span><span class="sxs-lookup"><span data-stu-id="e7c91-181">about_PSSessions</span></span>](https://technet.microsoft.com/library/7a9b4e0e-fa1b-47b0-92f6-6e2995d70acb)
- [<span data-ttu-id="e7c91-182">about_WS-Management_Cmdlets</span><span class="sxs-lookup"><span data-stu-id="e7c91-182">about_WS-Management_Cmdlets</span></span>](https://technet.microsoft.com/library/6ed3370a-ea10-45a5-9493-696aeace27ed)
- [<span data-ttu-id="e7c91-183">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="e7c91-183">Invoke-Command</span></span>](/powershell/module/microsoft.powershell.core/invoke-command)
- [<span data-ttu-id="e7c91-184">Import-PSSession</span><span class="sxs-lookup"><span data-stu-id="e7c91-184">Import-PSSession</span></span>](https://go.microsoft.com/fwlink/?LinkId=821821)
- [<span data-ttu-id="e7c91-185">New-PSSession</span><span class="sxs-lookup"><span data-stu-id="e7c91-185">New-PSSession</span></span>](https://go.microsoft.com/fwlink/?LinkId=821498)
- [<span data-ttu-id="e7c91-186">Register-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="e7c91-186">Register-PSSessionConfiguration</span></span>](https://go.microsoft.com/fwlink/?LinkId=821508)
- [<span data-ttu-id="e7c91-187">WSMan-Anbieter</span><span class="sxs-lookup"><span data-stu-id="e7c91-187">WSMan Provider</span></span>](https://technet.microsoft.com/library/66fe1241-e08f-49ca-832f-a84c33ca8735)

[wsman-remoting]: WSMan-Remoting-in-PowerShell-Core.md
[ssh-remoting]: SSH-Remoting-in-PowerShell-Core.md
