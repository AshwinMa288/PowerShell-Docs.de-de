---
description: Beschreibt die Problembehandlung bei Remote Vorgängen in PowerShell.
Locale: en-US
ms.date: 10/27/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_troubleshooting?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Remote_Troubleshooting
ms.openlocfilehash: cedf38f3982f4036aae59a2019ab72b556e50cfd
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99597174"
---
# <a name="about-remote-troubleshooting"></a><span data-ttu-id="d1d82-103">Informationen zur Remote Problembehandlung</span><span class="sxs-lookup"><span data-stu-id="d1d82-103">About Remote Troubleshooting</span></span>

## <a name="short-description"></a><span data-ttu-id="d1d82-104">Kurze Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d1d82-104">Short description</span></span>
<span data-ttu-id="d1d82-105">Beschreibt die Problembehandlung bei Remote Vorgängen in PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d1d82-105">Describes how to troubleshoot remote operations in PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="d1d82-106">Lange Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d1d82-106">Long description</span></span>

<span data-ttu-id="d1d82-107">In diesem Abschnitt werden einige der Probleme beschrieben, die auftreten können, wenn Sie die Remoting-Features von PowerShell verwenden, die auf WS-Management Technologie basieren, und Lösungen für diese Probleme vorschlägt.</span><span class="sxs-lookup"><span data-stu-id="d1d82-107">This section describes some of the problems that you might encounter when using the remoting features of PowerShell that are based on WS-Management technology and it suggests solutions to these problems.</span></span>

<span data-ttu-id="d1d82-108">Vor der Verwendung von PowerShell-Remoting finden Sie unter [about_Remote](about_remote.md) und [about_Remote_Requirements](about_Remote_Requirements.md) Anleitungen zur Konfiguration und grundlegenden Verwendung.</span><span class="sxs-lookup"><span data-stu-id="d1d82-108">Before using PowerShell remoting, see [about_Remote](about_remote.md) and [about_Remote_Requirements](about_Remote_Requirements.md) for guidance on configuration and basic use.</span></span> <span data-ttu-id="d1d82-109">Außerdem verfügen die Hilfe Themen für die einzelnen Remoting-Cmdlets, insbesondere die Parameter Beschreibungen, über nützliche Informationen, die Ihnen helfen sollen, Probleme zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="d1d82-109">Also, the Help topics for each of the remoting cmdlets, particularly the parameter descriptions, have useful information that is designed to help you avoid problems.</span></span>

> [!NOTE]
> <span data-ttu-id="d1d82-110">Starten Sie PowerShell mit der Option **als Administrator ausführen** , um Einstellungen für den lokalen Computer im WSMAN:-Laufwerk anzuzeigen oder zu ändern, einschließlich Änderungen an den Sitzungs Konfigurationen, vertrauenswürdigen Hosts, Ports oder Listenern.</span><span class="sxs-lookup"><span data-stu-id="d1d82-110">To view or change settings for the local computer in the WSMan: drive, including changes to the session configurations, trusted hosts, ports, or listeners, start PowerShell with the **Run as administrator** option.</span></span>

## <a name="troubleshooting-permission-and-authentication-issues"></a><span data-ttu-id="d1d82-111">Problembehandlung bei Berechtigungen und Authentifizierungs Problemen</span><span class="sxs-lookup"><span data-stu-id="d1d82-111">Troubleshooting permission and authentication issues</span></span>

<span data-ttu-id="d1d82-112">In diesem Abschnitt werden remotingprobleme im Zusammenhang mit Benutzer-und Computer Berechtigungen und Remote Anforderungen behandelt.</span><span class="sxs-lookup"><span data-stu-id="d1d82-112">This section discusses remoting problems that are related to user and computer permissions and remoting requirements.</span></span>

### <a name="how-to-run-as-administrator"></a><span data-ttu-id="d1d82-113">Vorgehensweise beim Ausführen als Administrator</span><span class="sxs-lookup"><span data-stu-id="d1d82-113">How to run as administrator</span></span>

```
ERROR: Access is denied. You need to run this cmdlet from an elevated
process.
```

<span data-ttu-id="d1d82-114">Starten Sie Windows PowerShell mit der Option **als Administrator ausführen** , um eine Remote Sitzung auf dem lokalen Computer zu starten oder Einstellungen für den lokalen Computer im WSMAN:-Laufwerk anzuzeigen oder zu ändern, einschließlich Änderungen an den Sitzungs Konfigurationen, vertrauenswürdigen Hosts, Ports oder Listenern.</span><span class="sxs-lookup"><span data-stu-id="d1d82-114">To start a remote session on the local computer, or to view or change settings for the local computer in the WSMan: drive, including changes to the session configurations, trusted hosts, ports, or listeners, start Windows PowerShell with the **Run as administrator** option.</span></span>

<span data-ttu-id="d1d82-115">So starten Sie Windows PowerShell mit der Option **als Administrator ausführen** :</span><span class="sxs-lookup"><span data-stu-id="d1d82-115">To start Windows PowerShell with the **Run as administrator** option:</span></span>

- <span data-ttu-id="d1d82-116">Klicken Sie mit der rechten Maustaste auf ein Windows PowerShell-Symbol (oder Windows PowerShell ISE), und klicken Sie dann auf **als Administrator ausführen**.</span><span class="sxs-lookup"><span data-stu-id="d1d82-116">Right-click a Windows PowerShell (or Windows PowerShell ISE) icon and then click **Run as administrator**.</span></span>

  <span data-ttu-id="d1d82-117">Zum Starten von Windows PowerShell mit der Option **als Administrator ausführen** in Windows 7 und Windows Server 2008 R2.</span><span class="sxs-lookup"><span data-stu-id="d1d82-117">To start Windows PowerShell with the **Run as administrator** option in Windows 7 and Windows Server 2008 R2.</span></span>

- <span data-ttu-id="d1d82-118">Klicken Sie in der Windows-Taskleiste mit der rechten Maustaste auf das Windows PowerShell-Symbol, und klicken Sie dann auf **als Administrator ausführen**.</span><span class="sxs-lookup"><span data-stu-id="d1d82-118">In the Windows taskbar, right-click the Windows PowerShell icon, and then click **Run as administrator**.</span></span>

  <span data-ttu-id="d1d82-119">In Windows Server 2008 R2 wird das Windows PowerShell-Symbol standardmäßig an die Taskleiste angeheftet.</span><span class="sxs-lookup"><span data-stu-id="d1d82-119">In Windows Server 2008 R2, the Windows PowerShell icon is pinned to the taskbar by default.</span></span>

### <a name="how-to-enable-remoting"></a><span data-ttu-id="d1d82-120">Aktivieren von Remoting</span><span class="sxs-lookup"><span data-stu-id="d1d82-120">How to enable remoting</span></span>

```
ERROR:  ACCESS IS DENIED

or

ERROR: The connection to the remote host was refused. Verify that the
WS-Management service is running on the remote host and configured to
listen for requests on the correct port and HTTP URL.
```

<span data-ttu-id="d1d82-121">Es ist keine Konfiguration erforderlich, um es einem Computer zu ermöglichen, Remote Befehle zu senden.</span><span class="sxs-lookup"><span data-stu-id="d1d82-121">No configuration is required to enable a computer to send remote commands.</span></span>
<span data-ttu-id="d1d82-122">Zum Empfangen von Remote Befehlen muss jedoch PowerShell-Remoting auf dem Computer aktiviert sein.</span><span class="sxs-lookup"><span data-stu-id="d1d82-122">However, to receive remote commands, PowerShell remoting must be enabled on the computer.</span></span> <span data-ttu-id="d1d82-123">Aktivieren von umfasst das Starten des WinRM-Dienst, das Festlegen des Starttyps für den WinRM-Dienst auf automatisch, das Erstellen von Listenern für http-und HTTPS-Verbindungen und das Erstellen von</span><span class="sxs-lookup"><span data-stu-id="d1d82-123">Enabling includes starting the WinRM service, setting the startup type for the WinRM service to Automatic, creating listeners for HTTP and HTTPS connections, and creating default session configurations.</span></span>

<span data-ttu-id="d1d82-124">Windows PowerShell-Remoting ist unter Windows Server 2012 und neueren Versionen von Windows Server standardmäßig aktiviert.</span><span class="sxs-lookup"><span data-stu-id="d1d82-124">Windows PowerShell remoting is enabled on Windows Server 2012 and newer releases of Windows Server by default.</span></span> <span data-ttu-id="d1d82-125">Führen Sie auf allen anderen Systemen das- `Enable-PSRemoting` Cmdlet aus, um Remoting zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="d1d82-125">On all other systems, run the `Enable-PSRemoting` cmdlet to enable remoting.</span></span> <span data-ttu-id="d1d82-126">Sie können das `Enable-PSRemoting` Cmdlet auch zum erneuten Aktivieren von Remoting unter Windows Server 2012 und neueren Versionen von Windows Server ausführen, wenn Remoting deaktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="d1d82-126">You can also run the `Enable-PSRemoting` cmdlet to re-enable remoting on Windows Server 2012 and newer releases of Windows Server if remoting is disabled.</span></span>

<span data-ttu-id="d1d82-127">Verwenden Sie das-Cmdlet, um einen Computer für den Empfang von Remote Befehlen zu konfigurieren `Enable-PSRemoting` .</span><span class="sxs-lookup"><span data-stu-id="d1d82-127">To configure a computer to receive remote commands, use the `Enable-PSRemoting` cmdlet.</span></span> <span data-ttu-id="d1d82-128">Der folgende Befehl aktiviert alle erforderlichen Remote Einstellungen, aktiviert die Sitzungs Konfigurationen und startet den WinRM-Dienst neu, damit die Änderungen wirksam werden.</span><span class="sxs-lookup"><span data-stu-id="d1d82-128">The following command enables all required remote settings, enables the session configurations, and restarts the WinRM service to make the changes effective.</span></span>

`Enable-PSRemoting`

<span data-ttu-id="d1d82-129">Um alle Eingabe Aufforderungen zu unterdrücken, geben Sie ein</span><span class="sxs-lookup"><span data-stu-id="d1d82-129">To suppress all user prompts, type:</span></span>

`Enable-PSRemoting -Force`

<span data-ttu-id="d1d82-130">Weitere Informationen finden Sie unter [enable-psremoting](xref:Microsoft.PowerShell.Core.Enable-PSRemoting).</span><span class="sxs-lookup"><span data-stu-id="d1d82-130">For more information, see [Enable-PSRemoting](xref:Microsoft.PowerShell.Core.Enable-PSRemoting).</span></span>

### <a name="how-to-enable-remoting-in-an-enterprise"></a><span data-ttu-id="d1d82-131">Aktivieren von Remoting in einem Unternehmen</span><span class="sxs-lookup"><span data-stu-id="d1d82-131">How to enable remoting in an enterprise</span></span>

```
ERROR:  ACCESS IS DENIED

or

ERROR: The connection to the remote host was refused. Verify that the
WS-Management service is running on the remote host and configured to listen
for requests on the correct port and HTTP URL.
```

<span data-ttu-id="d1d82-132">Verwenden Sie das-Cmdlet, um einen einzelnen Computer zum Empfangen von PowerShell-Remote Befehlen und zum Akzeptieren von Verbindungen zu aktivieren `Enable-PSRemoting` .</span><span class="sxs-lookup"><span data-stu-id="d1d82-132">To enable a single computer to receive remote PowerShell commands and accept connections, use the `Enable-PSRemoting` cmdlet.</span></span>

<span data-ttu-id="d1d82-133">Zum Aktivieren von Remoting für mehrere Computer in einem Unternehmen können Sie die folgenden skalierten Optionen verwenden.</span><span class="sxs-lookup"><span data-stu-id="d1d82-133">To enable remoting for multiple computers in an enterprise, you can use the following scaled options.</span></span>

- <span data-ttu-id="d1d82-134">Aktivieren Sie die Gruppenrichtlinie **Automatische Konfiguration von** Listenern zulassen, um Listener für Remoting zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="d1d82-134">To configure listeners for remoting, enable the **Allow automatic configuration of listeners** group policy.</span></span>

- <span data-ttu-id="d1d82-135">Verwenden Sie das-Cmdlet, um den Starttyp der Windows-Remoteverwaltung (WinRM) auf mehreren Computern auf "automatisch" festzulegen `Set-Service` .</span><span class="sxs-lookup"><span data-stu-id="d1d82-135">To set the startup type of the Windows Remote Management (WinRM) to Automatic on multiple computers, use the `Set-Service` cmdlet.</span></span>

- <span data-ttu-id="d1d82-136">Um eine Firewallausnahme zu aktivieren, verwenden Sie die Gruppenrichtlinie **Windows-Firewall: lokale Port Ausnahmen zulassen** .</span><span class="sxs-lookup"><span data-stu-id="d1d82-136">To enable a firewall exception, use the **Windows Firewall: Allow Local Port Exceptions** group policy.</span></span>

### <a name="how-to-enable-listeners-by-using-a-group-policy"></a><span data-ttu-id="d1d82-137">Aktivieren von Listenern mithilfe einer Gruppenrichtlinie</span><span class="sxs-lookup"><span data-stu-id="d1d82-137">How to enable listeners by using a group policy</span></span>

```
ERROR:  ACCESS IS DENIED

or

ERROR: The connection to the remote host was refused. Verify that the
WS-Management service is running on the remote host and configured to listen
for requests on the correct port and HTTP URL.
```

<span data-ttu-id="d1d82-138">Um die Listener für alle Computer in einer Domäne zu konfigurieren, aktivieren Sie die Richtlinie **Automatische Konfiguration von** Listenern zulassen im folgenden Gruppenrichtlinie Pfad:</span><span class="sxs-lookup"><span data-stu-id="d1d82-138">To configure the listeners for all computers in a domain, enable the **Allow automatic configuration of listeners** policy in the following Group Policy path:</span></span>

```
Computer Configuration\Administrative Templates\Windows Components
    \Windows Remote Management (WinRM)\WinRM service
```

<span data-ttu-id="d1d82-139">Aktivieren Sie die Richtlinie, und geben Sie die IPv4-und IPv6-Filter</span><span class="sxs-lookup"><span data-stu-id="d1d82-139">Enable the policy and specify the IPv4 and IPv6 filters.</span></span> <span data-ttu-id="d1d82-140">Platzhalter ( `*` ) sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="d1d82-140">Wildcards (`*`) are permitted.</span></span>

### <a name="how-to-enable-remoting-on-public-networks"></a><span data-ttu-id="d1d82-141">Aktivieren von Remoting in öffentlichen Netzwerken</span><span class="sxs-lookup"><span data-stu-id="d1d82-141">How to enable remoting on public networks</span></span>

```
ERROR:  Unable to check the status of the firewall
```

<span data-ttu-id="d1d82-142">`Enable-PSRemoting`Mit dem-Cmdlet wird dieser Fehler zurückgegeben, wenn das lokale Netzwerk öffentlich ist und der **skipnetworkprofilecheck** -Parameter nicht im Befehl verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="d1d82-142">The `Enable-PSRemoting` cmdlet returns this error when the local network is public and the **SkipNetworkProfileCheck** parameter is not used in the command.</span></span>

<span data-ttu-id="d1d82-143">Unter Serverversionen von Windows ist `Enable-PSRemoting` bei allen Netzwerkadressen Typen erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="d1d82-143">On server versions of Windows, `Enable-PSRemoting` succeeds on all network location types.</span></span> <span data-ttu-id="d1d82-144">Es werden Firewallregeln erstellt, die den Remote Zugriff auf private und Domänen Netzwerke ("Home" und "Work") ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="d1d82-144">It creates firewall rules that allow remote access to private and domain ("Home" and "Work") networks.</span></span> <span data-ttu-id="d1d82-145">Für öffentliche Netzwerke werden Firewallregeln erstellt, die den Remote Zugriff über das gleiche lokale Subnetz ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="d1d82-145">For public networks, it creates firewall rules that allows remote access from the same local subnet.</span></span>

<span data-ttu-id="d1d82-146">Unter Client Versionen von Windows ist `Enable-PSRemoting` für private Netzwerke und Domänen Netzwerke erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="d1d82-146">On client versions of Windows, `Enable-PSRemoting` succeeds on private and domain networks.</span></span> <span data-ttu-id="d1d82-147">Standardmäßig schlägt Sie in öffentlichen Netzwerken fehl, aber wenn Sie den **skipnetworkprofilecheck** -Parameter verwenden, ist erfolgreich, und es wird `Enable-PSRemoting` eine Firewallregel erstellt, die Datenverkehr aus dem gleichen lokalen Subnetz zulässt.</span><span class="sxs-lookup"><span data-stu-id="d1d82-147">By default, it fails on public networks, but if you use the **SkipNetworkProfileCheck** parameter, `Enable-PSRemoting` succeeds and creates a firewall rule that allows traffic from the same local subnet.</span></span>

<span data-ttu-id="d1d82-148">Führen Sie den folgenden Befehl aus, um die Einschränkung des lokalen Subnetzes in öffentlichen Netzwerken zu entfernen und den Remote Zugriff von einem beliebigen Speicherort zuzulassen:</span><span class="sxs-lookup"><span data-stu-id="d1d82-148">To remove the local subnet restriction on public networks and allow remote access from any location, run the following command:</span></span>

```powershell
Set-NetFirewallRule -Name "WINRM-HTTP-In-TCP-PUBLIC" -RemoteAddress Any
```

<span data-ttu-id="d1d82-149">Das- `Set-NetFirewallRule` Cmdlet wird vom Netsecurity-Modul exportiert.</span><span class="sxs-lookup"><span data-stu-id="d1d82-149">The `Set-NetFirewallRule` cmdlet is exported by the NetSecurity module.</span></span>

> [!NOTE]
> <span data-ttu-id="d1d82-150">In Windows PowerShell 2,0 erstellt auf Computern, auf denen Serverversionen von Windows ausgeführt werden, `Enable-PSRemoting` Firewallregeln, die den Remote Zugriff auf private, Domänen-und öffentliche Netzwerke ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="d1d82-150">In Windows PowerShell 2.0, on computers running server versions of Windows, `Enable-PSRemoting` creates firewall rules that allow remote access on private, domain and public networks.</span></span> <span data-ttu-id="d1d82-151">Auf Computern, auf denen Client Versionen von Windows ausgeführt werden, `Enable-PSRemoting` erstellt Firewallregeln, die den Remote Zugriff nur in privaten und Domänen Netzwerken zulassen.</span><span class="sxs-lookup"><span data-stu-id="d1d82-151">On computers running client versions of Windows, `Enable-PSRemoting` creates firewall rules that allow remote access only on private and domain networks.</span></span>

### <a name="how-to-enable-a-firewall-exception-by-using-a-group-policy"></a><span data-ttu-id="d1d82-152">Aktivieren einer Firewallausnahme mithilfe einer Gruppenrichtlinie</span><span class="sxs-lookup"><span data-stu-id="d1d82-152">How to enable a firewall exception by using a group policy</span></span>

```
ERROR:  ACCESS IS DENIED

or

ERROR: The connection to the remote host was refused. Verify that the
WS-Management service is running on the remote host and configured to listen
for requests on the correct port and HTTP URL.
```

<span data-ttu-id="d1d82-153">Aktivieren Sie zum Aktivieren einer Firewallausnahme für auf allen Computern in einer Domäne die Richtlinie " **Windows-Firewall: Ausnahmen für lokale Ports zulassen** " im folgenden Gruppenrichtlinie Pfad:</span><span class="sxs-lookup"><span data-stu-id="d1d82-153">To enable a firewall exception for in all computers in a domain, enable the **Windows Firewall: Allow local port exceptions** policy in the following Group Policy path:</span></span>

```
Computer Configuration\Administrative Templates\Network
    \Network Connections\Windows Firewall\Domain Profile
```

<span data-ttu-id="d1d82-154">Diese Richtlinie ermöglicht Mitgliedern der Gruppe "Administratoren" auf dem Computer die Verwendung der **Windows-Firewall** in der **Systemsteuerung** , um eine Firewallausnahme für den Windows-Remoteverwaltung-Dienst zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="d1d82-154">This policy allows members of the Administrators group on the computer to use **Windows Firewall** in **Control Panel** to create a firewall exception for the Windows Remote Management service.</span></span>

<span data-ttu-id="d1d82-155">Wenn die Richtlinien Konfiguration falsch ist, erhalten Sie möglicherweise die folgende Fehlermeldung:</span><span class="sxs-lookup"><span data-stu-id="d1d82-155">If the policy configuration is incorrect you may receive the following error:</span></span>

```
The client cannot connect to the destination specified in the request. Verify
that the service on the destination is running and is accepting requests.
```

<span data-ttu-id="d1d82-156">Ein Konfigurationsfehler in der Richtlinie führt zu einem leeren Wert für die **listeningon** -Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="d1d82-156">A configuration error in the policy results in an empty value for the **ListeningOn** property.</span></span> <span data-ttu-id="d1d82-157">Verwenden Sie den folgenden Befehl, um den Wert zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="d1d82-157">Use the following command to check the value.</span></span>

```powershell
PS> Get-WSManInstance winrm/config/listener -Enumerate

cfg                   : http://schemas.microsoft.com/wbem/wsman/1/config/listener
xsi                   : http://www.w3.org/2001/XMLSchema-instance
Source                : GPO
lang                  : en-US
Address               : *
Transport             : HTTP
Port                  : 5985
Hostname              :
Enabled               : true
URLPrefix             : wsman
CertificateThumbprint :
ListeningOn           : {}
```

### <a name="how-to-set-the-startup-type-of-the-winrm-service"></a><span data-ttu-id="d1d82-158">Festlegen des Starttyps für den WinRM-Dienst</span><span class="sxs-lookup"><span data-stu-id="d1d82-158">How to set the startup type of the WinRM service</span></span>

```
ERROR:  ACCESS IS DENIED
```

<span data-ttu-id="d1d82-159">PowerShell-Remoting ist abhängig vom Windows-Remoteverwaltung (WinRM)-Dienst.</span><span class="sxs-lookup"><span data-stu-id="d1d82-159">PowerShell remoting depends upon the Windows Remote Management (WinRM) service.</span></span>
<span data-ttu-id="d1d82-160">Der Dienst muss ausgeführt werden, um Remote Befehle zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="d1d82-160">The service must be running to support remote commands.</span></span>

<span data-ttu-id="d1d82-161">Unter Serverversionen von Windows ist der Starttyp des Windows-Remoteverwaltung (WinRM)-Dienstanbieter automatisch.</span><span class="sxs-lookup"><span data-stu-id="d1d82-161">On server versions of Windows, the startup type of the Windows Remote Management (WinRM) service is Automatic.</span></span>

<span data-ttu-id="d1d82-162">Unter Client Versionen von Windows ist der WinRM-Dienst jedoch standardmäßig deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="d1d82-162">However, on client versions of Windows, the WinRM service is disabled by default.</span></span>

<span data-ttu-id="d1d82-163">Verwenden Sie das-Cmdlet, um den Starttyp eines Dienstanbieter auf einem Remote Computer festzulegen `Set-Service` .</span><span class="sxs-lookup"><span data-stu-id="d1d82-163">To set the startup type of a service on a remote computer, use the `Set-Service` cmdlet.</span></span>

<span data-ttu-id="d1d82-164">Wenn Sie den Befehl auf mehreren Computern ausführen möchten, können Sie eine Textdatei oder eine CSV-Datei mit den Computernamen erstellen.</span><span class="sxs-lookup"><span data-stu-id="d1d82-164">To run the command on multiple computers, you can create a text file or CSV file of the computer names.</span></span>

<span data-ttu-id="d1d82-165">Mit den folgenden Befehlen wird z. b. eine Liste mit Computernamen aus der `Servers.txt` Datei und dann der Starttyp des WinRM-Dienstanbieter auf allen Computern auf **automatisch** festgelegt.</span><span class="sxs-lookup"><span data-stu-id="d1d82-165">For example, the following commands get a list of computer names from the `Servers.txt` file and then sets the startup type of the WinRM service on all of the computers to **Automatic**.</span></span>

```powershell
$servers = Get-Content servers.txt
Set-Service WinRM -ComputerName $servers -startuptype Automatic
```

<span data-ttu-id="d1d82-166">Verwenden Sie das `Get-WMIObject` Cmdlet mit dem **Win32_Service** Objekt, um die Ergebnisse anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="d1d82-166">To see the results use the `Get-WMIObject` cmdlet with the **Win32_Service** object.</span></span> <span data-ttu-id="d1d82-167">Weitere Informationen finden Sie unter [Set-Service](xref:Microsoft.PowerShell.Management.Set-Service).</span><span class="sxs-lookup"><span data-stu-id="d1d82-167">For more information, see [Set-Service](xref:Microsoft.PowerShell.Management.Set-Service).</span></span>

### <a name="how-to-recreate-the-default-session-configurations"></a><span data-ttu-id="d1d82-168">So erstellen Sie die Standard Sitzungs Konfigurationen neu</span><span class="sxs-lookup"><span data-stu-id="d1d82-168">How to recreate the default session configurations</span></span>

```
ERROR:  ACCESS IS DENIED
```

<span data-ttu-id="d1d82-169">Um eine Verbindung mit dem lokalen Computer herzustellen und Befehle Remote auszuführen, muss der lokale Computer Sitzungs Konfigurationen für Remote Befehle enthalten.</span><span class="sxs-lookup"><span data-stu-id="d1d82-169">To connect to the local computer and run commands remotely, the local computer must include session configurations for remote commands.</span></span>

<span data-ttu-id="d1d82-170">Wenn Sie verwenden `Enable-PSRemoting` , werden Standard Sitzungs Konfigurationen auf dem lokalen Computer erstellt.</span><span class="sxs-lookup"><span data-stu-id="d1d82-170">When you use `Enable-PSRemoting`, it creates default session configurations on the local computer.</span></span> <span data-ttu-id="d1d82-171">Remote Benutzer verwenden diese Sitzungs Konfigurationen, wenn ein Remote Befehl nicht den **ConfigurationName** -Parameter enthält.</span><span class="sxs-lookup"><span data-stu-id="d1d82-171">Remote users use these session configurations whenever a remote command does not include the **ConfigurationName** parameter.</span></span>

<span data-ttu-id="d1d82-172">Wenn die Registrierung der Standardkonfigurationen auf einem Computer aufgehoben oder gelöscht wird, verwenden `Enable-PSRemoting` Sie das Cmdlet, um Sie neu zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="d1d82-172">If the default configurations on a computer are unregistered or deleted, use the `Enable-PSRemoting` cmdlet to recreate them.</span></span> <span data-ttu-id="d1d82-173">Dieses Cmdlet kann wiederholt verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="d1d82-173">You can use this cmdlet repeatedly.</span></span> <span data-ttu-id="d1d82-174">Wenn bereits eine Funktion konfiguriert ist, werden keine Fehler generiert.</span><span class="sxs-lookup"><span data-stu-id="d1d82-174">It does not generate errors if a feature is already configured.</span></span>

<span data-ttu-id="d1d82-175">Wenn Sie die Standard Sitzungs Konfigurationen ändern und die ursprünglichen Standard Sitzungs Konfigurationen wiederherstellen möchten, verwenden Sie das `Unregister-PSSessionConfiguration` Cmdlet, um die geänderten Sitzungs Konfigurationen zu löschen, und verwenden Sie dann das `Enable-PSRemoting` Cmdlet, um Sie wiederherzustellen.</span><span class="sxs-lookup"><span data-stu-id="d1d82-175">If you change the default session configurations and want to restore the original default session configurations, use the `Unregister-PSSessionConfiguration` cmdlet to delete the changed session configurations and then use the `Enable-PSRemoting` cmdlet to restore them.</span></span>
<span data-ttu-id="d1d82-176">`Enable-PSRemoting` vorhandene Sitzungs Konfigurationen werden von nicht geändert.</span><span class="sxs-lookup"><span data-stu-id="d1d82-176">`Enable-PSRemoting` does not change existing session configurations.</span></span>

> [!NOTE]
> <span data-ttu-id="d1d82-177">Wenn `Enable-PSRemoting` die Standard Sitzungs Konfiguration von wieder hergestellt wird, werden keine expliziten Sicherheits Deskriptoren für die Konfigurationen erstellt.</span><span class="sxs-lookup"><span data-stu-id="d1d82-177">When `Enable-PSRemoting` restores the default session configuration, it does not create explicit security descriptors for the configurations.</span></span> <span data-ttu-id="d1d82-178">Stattdessen erben die Konfigurationen die Sicherheits Beschreibung von rootddl, die standardmäßig sicher ist.</span><span class="sxs-lookup"><span data-stu-id="d1d82-178">Instead, the configurations inherit the security descriptor of the RootSDDL, which is secure by default.</span></span>

<span data-ttu-id="d1d82-179">Geben Sie Folgendes ein, um die Sicherheits Beschreibung für roozddl anzuzeigen:</span><span class="sxs-lookup"><span data-stu-id="d1d82-179">To see the RootSDDL security descriptor, type:</span></span>

```powershell
Get-Item wsman:\localhost\Service\RootSDDL
```

<span data-ttu-id="d1d82-180">Verwenden Sie das `Set-Item` Cmdlet im WSMAN:-Laufwerk, um die rootsddl zu ändern.</span><span class="sxs-lookup"><span data-stu-id="d1d82-180">To change the RootSDDL, use the `Set-Item` cmdlet in the WSMan: drive.</span></span> <span data-ttu-id="d1d82-181">Verwenden Sie das `Set-PSSessionConfiguration` Cmdlet mit den Parametern **securitydescriptorsddl** oder **showsecuritydescriptorui** , um die Sicherheits Beschreibung einer Sitzungs Konfiguration zu ändern.</span><span class="sxs-lookup"><span data-stu-id="d1d82-181">To change the security descriptor of a session configuration, use the `Set-PSSessionConfiguration` cmdlet with the **SecurityDescriptorSDDL** or **ShowSecurityDescriptorUI** parameters.</span></span>

<span data-ttu-id="d1d82-182">Weitere Informationen zum WSMAN:-Laufwerk finden Sie im Hilfethema für den WSMAN-Anbieter ("Get-Help WSMAN").</span><span class="sxs-lookup"><span data-stu-id="d1d82-182">For more information about the WSMan: drive, see the Help topic for the WSMan provider ("Get-Help wsman").</span></span>

### <a name="how-to-provide-administrator-credentials"></a><span data-ttu-id="d1d82-183">Angeben von Administrator Anmelde Informationen</span><span class="sxs-lookup"><span data-stu-id="d1d82-183">How to provide administrator credentials</span></span>

```
ERROR:  ACCESS IS DENIED
```

<span data-ttu-id="d1d82-184">Zum Erstellen einer PSSession oder zum Ausführen von Befehlen auf einem Remote Computer muss der aktuelle Benutzer standardmäßig Mitglied der Gruppe "Administratoren" auf dem Remote Computer sein.</span><span class="sxs-lookup"><span data-stu-id="d1d82-184">To create a PSSession or run commands on a remote computer, by default, the current user must be a member of the Administrators group on the remote computer.</span></span> <span data-ttu-id="d1d82-185">Anmelde Informationen werden manchmal auch dann benötigt, wenn der aktuelle Benutzer an einem Konto angemeldet ist, das Mitglied der Gruppe "Administratoren" ist.</span><span class="sxs-lookup"><span data-stu-id="d1d82-185">Credentials are sometimes required even when the current user is logged on to an account that is a member of the Administrators group.</span></span>

<span data-ttu-id="d1d82-186">Wenn der aktuelle Benutzer ein Mitglied der Gruppe "Administratoren" auf dem Remote Computer ist oder die Anmelde Informationen eines Mitglieds der Gruppe "Administratoren" angeben kann, verwenden Sie den **Credential** -Parameter der `New-PSSession` `Enter-PSSession` `Invoke-Command` Cmdlets, oder, um eine Remote Verbindung herzustellen.</span><span class="sxs-lookup"><span data-stu-id="d1d82-186">If the current user is a member of the Administrators group on the remote computer, or can provide the credentials of a member of the Administrators group, use the **Credential** parameter of the `New-PSSession`, `Enter-PSSession` or `Invoke-Command` cmdlets to connect remotely.</span></span>

<span data-ttu-id="d1d82-187">Der folgende Befehl stellt z. b. die Anmelde Informationen eines Administrators bereit.</span><span class="sxs-lookup"><span data-stu-id="d1d82-187">For example, the following command provides the credentials of an Administrator.</span></span>

```powershell
Invoke-Command -ComputerName Server01 -Credential Domain01\Admin01
```

<span data-ttu-id="d1d82-188">Weitere Informationen zum **Credential** -Parameter finden Sie unter [New-PSSession](xref:Microsoft.PowerShell.Core.New-PSSession), [Enter-PSSession](xref:Microsoft.PowerShell.Core.Enter-PSSession) oder [aufrufen-Command](xref:Microsoft.PowerShell.Core.Invoke-Command).</span><span class="sxs-lookup"><span data-stu-id="d1d82-188">For more information about the **Credential** parameter, see [New-PSSession](xref:Microsoft.PowerShell.Core.New-PSSession), [Enter-PSSession](xref:Microsoft.PowerShell.Core.Enter-PSSession) or [Invoke-Command](xref:Microsoft.PowerShell.Core.Invoke-Command).</span></span>

### <a name="how-to-enable-remoting-for-non-administrative-users"></a><span data-ttu-id="d1d82-189">Aktivieren von Remoting für Benutzer, die keine Administratoren sind</span><span class="sxs-lookup"><span data-stu-id="d1d82-189">How to enable remoting for non-administrative users</span></span>

```
ERROR:  ACCESS IS DENIED
```

<span data-ttu-id="d1d82-190">Um eine PSSession einzurichten oder einen Befehl auf einem Remote Computer auszuführen, muss der Benutzer über die Berechtigung zum Verwenden der Sitzungs Konfigurationen auf dem Remote Computer verfügen.</span><span class="sxs-lookup"><span data-stu-id="d1d82-190">To establish a PSSession or run a command on a remote computer, the user must have permission to use the session configurations on the remote computer.</span></span>

<span data-ttu-id="d1d82-191">Standardmäßig haben nur Mitglieder der Gruppe "Administratoren" auf einem Computer die Berechtigung, die Standard Sitzungs Konfigurationen zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="d1d82-191">By default, only members of the Administrators group on a computer have permission to use the default session configurations.</span></span> <span data-ttu-id="d1d82-192">Daher können nur Mitglieder der Gruppe "Administratoren" eine Remote Verbindung mit dem Computer herstellen.</span><span class="sxs-lookup"><span data-stu-id="d1d82-192">Therefore, only members of the Administrators group can connect to the computer remotely.</span></span>

<span data-ttu-id="d1d82-193">Um anderen Benutzern das Herstellen einer Verbindung mit dem lokalen Computer zu gestatten, erteilen Sie dem Benutzerberechtigungen zum Ausführen der Standard Sitzungs Konfigurationen auf dem lokalen Computer.</span><span class="sxs-lookup"><span data-stu-id="d1d82-193">To allow other users to connect to the local computer, give the user Execute permissions to the default session configurations on the local computer.</span></span>

<span data-ttu-id="d1d82-194">Mit dem folgenden Befehl wird ein Eigenschaften Blatt geöffnet, mit dem Sie die Sicherheits Beschreibung der standardmäßigen Microsoft. PowerShell-Sitzungs Konfiguration auf dem lokalen Computer ändern können.</span><span class="sxs-lookup"><span data-stu-id="d1d82-194">The following command opens a property sheet that lets you change the security descriptor of the default Microsoft.PowerShell session configuration on the local computer.</span></span>

```powershell
Set-PSSessionConfiguration Microsoft.PowerShell -ShowSecurityDescriptorUI
```

<span data-ttu-id="d1d82-195">Weitere Informationen finden Sie unter [about_Session_Configurations](about_Session_Configurations.md).</span><span class="sxs-lookup"><span data-stu-id="d1d82-195">For more information, see [about_Session_Configurations](about_Session_Configurations.md).</span></span>

### <a name="how-to-enable-remoting-for-administrators-in-other-domains"></a><span data-ttu-id="d1d82-196">Aktivieren von Remoting für Administratoren in anderen Domänen</span><span class="sxs-lookup"><span data-stu-id="d1d82-196">How to enable remoting for administrators in other domains</span></span>

```
ERROR:  ACCESS IS DENIED
```

<span data-ttu-id="d1d82-197">Wenn ein Benutzer in einer anderen Domäne Mitglied der Gruppe "Administratoren" auf dem lokalen Computer ist, kann der Benutzer nicht Remote mit Administrator Rechten eine Verbindung mit dem lokalen Computer herstellen.</span><span class="sxs-lookup"><span data-stu-id="d1d82-197">When a user in another domain is a member of the Administrators group on the local computer, the user cannot connect to the local computer remotely with Administrator privileges.</span></span> <span data-ttu-id="d1d82-198">Standardmäßig werden Remote Verbindungen aus anderen Domänen nur mit Standard Token für Benutzerberechtigungen ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="d1d82-198">By default, remote connections from other domains run with only standard user privilege tokens.</span></span>

<span data-ttu-id="d1d82-199">Sie können jedoch den Registrierungs Eintrag **LocalAccountTokenFilterPolicy** verwenden, um das Standardverhalten zu ändern und Remote Benutzern, die Mitglieder der Gruppe "Administratoren" sind, das Ausführen von Administrator Rechten zu gestatten.</span><span class="sxs-lookup"><span data-stu-id="d1d82-199">However, you can use the **LocalAccountTokenFilterPolicy** registry entry to change the default behavior and allow remote users who are members of the Administrators group to run with Administrator privileges.</span></span>

> [!CAUTION]
> <span data-ttu-id="d1d82-200">Mit dem Eintrag **LocalAccountTokenFilterPolicy** werden die Remote Einschränkungen der Benutzerkontensteuerung (User Account Control, UAC) für alle Benutzer aller betroffenen Computer deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="d1d82-200">The **LocalAccountTokenFilterPolicy** entry disables user account control (UAC) remote restrictions for all users of all affected computers.</span></span> <span data-ttu-id="d1d82-201">Berücksichtigen Sie die Auswirkungen dieser Einstellung sorgfältig, bevor Sie die Richtlinie ändern.</span><span class="sxs-lookup"><span data-stu-id="d1d82-201">Consider the implications of this setting carefully before changing the policy.</span></span>

<span data-ttu-id="d1d82-202">Verwenden Sie den folgenden Befehl, um die Richtlinie zu ändern: Legen Sie den Wert des Registrierungs Eintrags **localaccountbukenfilterpolicy** auf 1 fest.</span><span class="sxs-lookup"><span data-stu-id="d1d82-202">To change the policy, use the following command to set the value of the **LocalAccountTokenFilterPolicy** registry entry to 1.</span></span>

```powershell
New-ItemProperty -Name LocalAccountTokenFilterPolicy `
  -Path HKLM:\SOFTWARE\Microsoft\Windows\CurrentVersion\Policies\System `
  -PropertyType DWord -Value 1
```

### <a name="how-to-use-an-ip-address-in-a-remote-command"></a><span data-ttu-id="d1d82-203">Verwenden einer IP-Adresse in einem Remote Befehl</span><span class="sxs-lookup"><span data-stu-id="d1d82-203">How to use an ip address in a remote command</span></span>

```
ERROR: The WinRM client cannot process the request. If the authentication
scheme is different from Kerberos, or if the client computer is not joined to a
domain, then HTTPS transport must be used or the destination machine must be
added to the TrustedHosts configuration setting.
```

<span data-ttu-id="d1d82-204">Der **Computername** -Parameter der `New-PSSession` `Enter-PSSession` `Invoke-Command` Cmdlets, und akzeptiert eine IP-Adresse als gültigen Wert.</span><span class="sxs-lookup"><span data-stu-id="d1d82-204">The **ComputerName** parameter of the `New-PSSession`, `Enter-PSSession` and `Invoke-Command` cmdlets accepts an IP address as a valid value.</span></span> <span data-ttu-id="d1d82-205">Da die Kerberos-Authentifizierung IP-Adressen jedoch nicht unterstützt, wird standardmäßig die NTLM-Authentifizierung verwendet, wenn Sie eine IP-Adresse angeben.</span><span class="sxs-lookup"><span data-stu-id="d1d82-205">However, because Kerberos authentication does not support IP addresses, NTLM authentication is used by default whenever you specify an IP address.</span></span>

<span data-ttu-id="d1d82-206">Wenn Sie die NTLM-Authentifizierung verwenden, ist das folgende Verfahren für Remoting erforderlich.</span><span class="sxs-lookup"><span data-stu-id="d1d82-206">When using NTLM authentication, the following procedure is required for remoting.</span></span>

1. <span data-ttu-id="d1d82-207">Konfigurieren Sie den Computer für den HTTPS-Transport, oder fügen Sie die IP-Adressen der Remote Computer der Liste "Treuhänder Hosts" auf dem lokalen Computer hinzu.</span><span class="sxs-lookup"><span data-stu-id="d1d82-207">Configure the computer for HTTPS transport or add the IP addresses of the remote computers to the TrustedHosts list on the local computer.</span></span>

1. <span data-ttu-id="d1d82-208">Verwenden Sie den **Credential** -Parameter in allen Remote Befehlen.</span><span class="sxs-lookup"><span data-stu-id="d1d82-208">Use the **Credential** parameter in all remote commands.</span></span>

   <span data-ttu-id="d1d82-209">Dies ist auch dann erforderlich, wenn Sie die Anmelde Informationen des aktuellen Benutzers übermitteln.</span><span class="sxs-lookup"><span data-stu-id="d1d82-209">This is required even when you are submitting the credentials of the current user.</span></span>

### <a name="how-to-connect-remotely-from-a-workgroup-based-computer"></a><span data-ttu-id="d1d82-210">Herstellen einer Remote Verbindung von einem Arbeitsgruppen basierten Computer aus</span><span class="sxs-lookup"><span data-stu-id="d1d82-210">How to connect remotely from a workgroup-based computer</span></span>

```
ERROR: The WinRM client cannot process the request. If the authentication
scheme is different from Kerberos, or if the client computer is not joined to a
domain, then HTTPS transport must be used or the destination machine must be
added to the TrustedHosts configuration setting.
```

<span data-ttu-id="d1d82-211">Wenn sich der lokale Computer nicht in einer Domäne befindet, ist das folgende Verfahren für Remoting erforderlich.</span><span class="sxs-lookup"><span data-stu-id="d1d82-211">When the local computer is not in a domain, the following procedure is required for remoting.</span></span>

1. <span data-ttu-id="d1d82-212">Konfigurieren Sie den Computer für den HTTPS-Transport, oder fügen Sie die Namen der Remote Computer der Liste "Treuhänder Hosts" auf dem lokalen Computer hinzu.</span><span class="sxs-lookup"><span data-stu-id="d1d82-212">Configure the computer for HTTPS transport or add the names of the remote computers to the TrustedHosts list on the local computer.</span></span>

1. <span data-ttu-id="d1d82-213">Vergewissern Sie sich, dass auf dem Arbeitsgruppen basierten Computer ein Kennwort festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="d1d82-213">Verify that a password is set on the workgroup-based computer.</span></span> <span data-ttu-id="d1d82-214">Wenn kein Kennwort festgelegt ist oder der Kenn Wort Wert leer ist, können Sie keine Remote Befehle ausführen.</span><span class="sxs-lookup"><span data-stu-id="d1d82-214">If a password is not set or the password value is empty, you cannot run remote commands.</span></span>

   <span data-ttu-id="d1d82-215">Verwenden Sie die Benutzerkonten in der Systemsteuerung, um das Kennwort für Ihr Benutzerkonto festzulegen.</span><span class="sxs-lookup"><span data-stu-id="d1d82-215">To set password for your user account, use User Accounts in Control Panel.</span></span>

1. <span data-ttu-id="d1d82-216">Verwenden Sie den **Credential** -Parameter in allen Remote Befehlen.</span><span class="sxs-lookup"><span data-stu-id="d1d82-216">Use the **Credential** parameter in all remote commands.</span></span>

   <span data-ttu-id="d1d82-217">Dies ist auch dann erforderlich, wenn Sie die Anmelde Informationen des aktuellen Benutzers übermitteln.</span><span class="sxs-lookup"><span data-stu-id="d1d82-217">This is required even when you are submitting the credentials of the current user.</span></span>

### <a name="how-to-add-a-computer-to-the-trusted-hosts-list"></a><span data-ttu-id="d1d82-218">Hinzufügen eines Computers zur Liste der vertrauenswürdigen Hosts</span><span class="sxs-lookup"><span data-stu-id="d1d82-218">How to add a computer to the trusted hosts list</span></span>

<span data-ttu-id="d1d82-219">Das Element "Treuhänder Hosts" kann eine durch Trennzeichen getrennte Liste von Computernamen, IP-Adressen und voll qualifizierten Domänen Namen enthalten.</span><span class="sxs-lookup"><span data-stu-id="d1d82-219">The TrustedHosts item can contain a comma-separated list of computer names, IP addresses, and fully-qualified domain names.</span></span> <span data-ttu-id="d1d82-220">Platzhalter sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="d1d82-220">Wildcards are permitted.</span></span>

<span data-ttu-id="d1d82-221">Verwenden Sie das WSMAN:-Laufwerk, um die Liste der vertrauenswürdigen Hosts anzuzeigen oder zu ändern.</span><span class="sxs-lookup"><span data-stu-id="d1d82-221">To view or change the trusted host list, use the WSMan: drive.</span></span> <span data-ttu-id="d1d82-222">Das Element "Treuhänder Host" befindet sich im- `WSMan:\localhost\Client` Knoten.</span><span class="sxs-lookup"><span data-stu-id="d1d82-222">The TrustedHost item is in the `WSMan:\localhost\Client` node.</span></span>

<span data-ttu-id="d1d82-223">Nur Mitglieder der Gruppe "Administratoren" auf dem Computer verfügen über die Berechtigung, die Liste der vertrauenswürdigen Hosts auf dem Computer zu ändern.</span><span class="sxs-lookup"><span data-stu-id="d1d82-223">Only members of the Administrators group on the computer have permission to change the list of trusted hosts on the computer.</span></span>

<span data-ttu-id="d1d82-224">Vorsicht: der Wert, den Sie für das Element "Treuhänder Hosts" festlegen, wirkt sich auf alle Benutzer des Computers aus.</span><span class="sxs-lookup"><span data-stu-id="d1d82-224">Caution: The value that you set for the TrustedHosts item affects all users of the computer.</span></span>

<span data-ttu-id="d1d82-225">Verwenden Sie den folgenden Befehl, um die Liste der vertrauenswürdigen Hosts anzuzeigen:</span><span class="sxs-lookup"><span data-stu-id="d1d82-225">To view the list of trusted hosts, use the following command:</span></span>

```powershell
Get-Item wsman:\localhost\Client\TrustedHosts
```

<span data-ttu-id="d1d82-226">Sie können auch das `Set-Location` Cmdlet (Alias = CD) verwenden, um durch das WSMAN:-Laufwerk an den Speicherort zu navigieren.</span><span class="sxs-lookup"><span data-stu-id="d1d82-226">You can also use the `Set-Location` cmdlet (alias = cd) to navigate though the WSMan: drive to the location.</span></span> <span data-ttu-id="d1d82-227">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="d1d82-227">For example:</span></span>

```powershell
cd WSMan:\localhost\Client; dir
```

<span data-ttu-id="d1d82-228">Wenn Sie alle Computer der Liste vertrauenswürdiger Hosts hinzufügen möchten, verwenden Sie den folgenden Befehl, der den Wert \* (alle) in Computername platziert.</span><span class="sxs-lookup"><span data-stu-id="d1d82-228">To add all computers to the list of trusted hosts, use the following command, which places a value of \* (all) in the ComputerName</span></span>

```powershell
Set-Item wsman:localhost\client\trustedhosts -Value *
```

<span data-ttu-id="d1d82-229">Sie können auch ein Platzhalter Zeichen ( `*` ) verwenden, um alle Computer in einer bestimmten Domäne der Liste der vertrauenswürdigen Hosts hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="d1d82-229">You can also use a wildcard character (`*`) to add all computers in a particular domain to the list of trusted hosts.</span></span> <span data-ttu-id="d1d82-230">Mit dem folgenden Befehl werden beispielsweise alle Computer in der Domäne "Fabrikam" der Liste der vertrauenswürdigen Hosts hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="d1d82-230">For example, the following command adds all of the computers in the Fabrikam domain to the list of trusted hosts.</span></span>

```powershell
Set-Item wsman:localhost\client\trustedhosts *.fabrikam.com
```

<span data-ttu-id="d1d82-231">Um die Namen bestimmter Computer der Liste vertrauenswürdiger Hosts hinzuzufügen, verwenden Sie das folgende Befehls Format:</span><span class="sxs-lookup"><span data-stu-id="d1d82-231">To add the names of particular computers to the list of trusted hosts, use the following command format:</span></span>

```powershell
Set-Item wsman:\localhost\Client\TrustedHosts -Value <ComputerName>
```

<span data-ttu-id="d1d82-232">Jeder Wert `<ComputerName>` muss das folgende Format aufweisen:</span><span class="sxs-lookup"><span data-stu-id="d1d82-232">where each value `<ComputerName>` must have the following format:</span></span>

```
<Computer>.<Domain>.<Company>.<top-level-domain>
```

<span data-ttu-id="d1d82-233">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="d1d82-233">For example:</span></span>

```powershell
$server = 'Server01.Domain01.Fabrikam.com'
Set-Item wsman:\localhost\Client\TrustedHosts -Value $server
```

<span data-ttu-id="d1d82-234">Wenn Sie einen Computernamen zu einer vorhandenen Liste vertrauenswürdiger Hosts hinzufügen möchten, speichern Sie zuerst den aktuellen Wert in einer Variablen, und legen Sie dann den Wert auf eine durch Trennzeichen getrennte Liste fest, die die aktuellen und die neuen Werte enthält.</span><span class="sxs-lookup"><span data-stu-id="d1d82-234">To add a computer name to an existing list of trusted hosts, first save the current value in a variable, and then set the value to a comma-separated list that includes the current and new values.</span></span>

<span data-ttu-id="d1d82-235">Verwenden Sie z. b. den folgenden Befehl, um den Computer "Server01" einer vorhandenen Liste vertrauenswürdiger Hosts hinzuzufügen:</span><span class="sxs-lookup"><span data-stu-id="d1d82-235">For example, to add the Server01 computer to an existing list of trusted hosts, use the following command</span></span>

```powershell
$curValue = (Get-Item wsman:\localhost\Client\TrustedHosts).value

Set-Item wsman:\localhost\Client\TrustedHosts -Value `
  "$curValue, Server01.Domain01.Fabrikam.com"
```

<span data-ttu-id="d1d82-236">Verwenden Sie das folgende Befehls Format, um die IP-Adressen bestimmter Computer der Liste der vertrauenswürdigen Hosts hinzuzufügen:</span><span class="sxs-lookup"><span data-stu-id="d1d82-236">To add the IP addresses of particular computers to the list of trusted hosts, use the following command format:</span></span>

```powershell
Set-Item wsman:\localhost\Client\TrustedHosts -Value <IP Address>
```

<span data-ttu-id="d1d82-237">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="d1d82-237">For example:</span></span>

```powershell
Set-Item wsman:\localhost\Client\TrustedHosts -Value 172.16.0.0
```

<span data-ttu-id="d1d82-238">Zum Hinzufügen eines Computers zur Liste "Treuhänder Hosts" eines Remote Computers verwenden Sie das `Connect-WSMan` Cmdlet zum Hinzufügen eines Knotens für den Remote Computer zum WSMAN:-Laufwerk auf dem lokalen Computer.</span><span class="sxs-lookup"><span data-stu-id="d1d82-238">To add a computer to the TrustedHosts list of a remote computer, use the `Connect-WSMan` cmdlet to add a node for the remote computer to the WSMan: drive on the local computer.</span></span> <span data-ttu-id="d1d82-239">Verwenden Sie dann einen `Set-Item` Befehl, um den Computer hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="d1d82-239">Then use a `Set-Item` command to add the computer.</span></span>

<span data-ttu-id="d1d82-240">Weitere Informationen zum `Connect-WSMan` Cmdlet finden Sie unter [Connect-WSMAN](xref:Microsoft.WSMan.Management.Connect-WSMan).</span><span class="sxs-lookup"><span data-stu-id="d1d82-240">For more information about the `Connect-WSMan` cmdlet, see [Connect-WSMan](xref:Microsoft.WSMan.Management.Connect-WSMan).</span></span>

## <a name="troubleshooting-computer-configuration-issues"></a><span data-ttu-id="d1d82-241">Problembehandlung bei Computer Konfigurationsproblemen</span><span class="sxs-lookup"><span data-stu-id="d1d82-241">Troubleshooting computer configuration issues</span></span>

<span data-ttu-id="d1d82-242">In diesem Abschnitt werden remotingprobleme erläutert, die sich auf bestimmte Konfigurationen eines Computers, einer Domäne oder eines Unternehmens beziehen.</span><span class="sxs-lookup"><span data-stu-id="d1d82-242">This section discusses remoting problems that are related to particular configurations of a computer, domain, or enterprise.</span></span>

### <a name="how-to-configure-remoting-on-alternate-ports"></a><span data-ttu-id="d1d82-243">Konfigurieren von Remoting für alternative Ports</span><span class="sxs-lookup"><span data-stu-id="d1d82-243">How to configure remoting on alternate ports</span></span>

```
ERROR: The connection to the specified remote host was refused. Verify that the
WS-Management service is running on the remote host and configured to listen
for requests on the correct port and HTTP URL.
```

<span data-ttu-id="d1d82-244">PowerShell-Remoting verwendet standardmäßig Port 80 für den HTTP-Transport.</span><span class="sxs-lookup"><span data-stu-id="d1d82-244">PowerShell remoting uses port 80 for HTTP transport by default.</span></span> <span data-ttu-id="d1d82-245">Der Standardport wird verwendet, wenn der Benutzer die **ConnectionUri** -oder **Port** -Parameter nicht in einem Remote Befehl angibt.</span><span class="sxs-lookup"><span data-stu-id="d1d82-245">The default port is used whenever the user does not specify the **ConnectionURI** or **Port** parameters in a remote command.</span></span>

<span data-ttu-id="d1d82-246">Um den Standardport zu ändern, der von PowerShell verwendet wird, verwenden Sie das- `Set-Item` Cmdlet im WSMAN:-Laufwerk, um den Portwert im Listener-Blattknoten zu ändern.</span><span class="sxs-lookup"><span data-stu-id="d1d82-246">To change the default port that PowerShell uses, use `Set-Item` cmdlet in the WSMan: drive to change the Port value in the listener leaf node.</span></span>

<span data-ttu-id="d1d82-247">Der folgende Befehl ändert z. b. den Standardport in 8080.</span><span class="sxs-lookup"><span data-stu-id="d1d82-247">For example, the following command changes the default port to 8080.</span></span>

```powershell
Set-Item wsman:\localhost\listener\listener*\port -Value 8080
```

### <a name="how-to-configure-remoting-with-a-proxy-server"></a><span data-ttu-id="d1d82-248">Konfigurieren von Remoting mit einem Proxy Server</span><span class="sxs-lookup"><span data-stu-id="d1d82-248">How to configure remoting with a proxy server</span></span>

```
ERROR: The client cannot connect to the destination specified in the request.
Verify that the service on the destination is running and is accepting
requests.
```

<span data-ttu-id="d1d82-249">Da PowerShell-Remoting das HTTP-Protokoll verwendet, wird es von http-Proxy Einstellungen beeinflusst.</span><span class="sxs-lookup"><span data-stu-id="d1d82-249">Because PowerShell remoting uses the HTTP protocol, it is affected by HTTP proxy settings.</span></span> <span data-ttu-id="d1d82-250">In Unternehmen, die über Proxy Server verfügen, können Benutzer nicht direkt auf einen PowerShell-Remote Computer zugreifen.</span><span class="sxs-lookup"><span data-stu-id="d1d82-250">In enterprises that have proxy servers, users cannot access a PowerShell remote computer directly.</span></span>

<span data-ttu-id="d1d82-251">Um dieses Problem zu beheben, verwenden Sie die Optionen für die Proxy Einstellung in Ihrem Remote Befehl.</span><span class="sxs-lookup"><span data-stu-id="d1d82-251">To resolve this problem, use proxy setting options in your remote command.</span></span> <span data-ttu-id="d1d82-252">Die folgenden Einstellungen sind verfügbar:</span><span class="sxs-lookup"><span data-stu-id="d1d82-252">The following settings are available:</span></span>

- <span data-ttu-id="d1d82-253">Proxy Access Type</span><span class="sxs-lookup"><span data-stu-id="d1d82-253">ProxyAccessType</span></span>
- <span data-ttu-id="d1d82-254">Proxy Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="d1d82-254">ProxyAuthentication</span></span>
- <span data-ttu-id="d1d82-255">ProxyCredential</span><span class="sxs-lookup"><span data-stu-id="d1d82-255">ProxyCredential</span></span>

<span data-ttu-id="d1d82-256">Um diese Optionen für einen bestimmten Befehl festzulegen, verwenden Sie das folgende Verfahren:</span><span class="sxs-lookup"><span data-stu-id="d1d82-256">To set these options for a particular command, use the following procedure:</span></span>

1. <span data-ttu-id="d1d82-257">Verwenden Sie die Parameter **proxyaccesstype**, **Proxyauthentication** und **proxycredential** des `New-PSSessionOption` Cmdlets, um ein Sitzungs Options Objekt mit den Proxy Einstellungen für Ihr Unternehmen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="d1d82-257">Use the **ProxyAccessType**, **ProxyAuthentication**, and **ProxyCredential** parameters of the `New-PSSessionOption` cmdlet to create a session option object with the proxy settings for your enterprise.</span></span> <span data-ttu-id="d1d82-258">Speichern Sie das Options Objekt ist eine Variable.</span><span class="sxs-lookup"><span data-stu-id="d1d82-258">Save the option object is a variable.</span></span>

1. <span data-ttu-id="d1d82-259">Verwenden Sie die Variable, die das Options Objekt enthält, als Wert des **sessionoption** -Parameters eines- `New-PSSession` ,-oder- `Enter-PSSession` `Invoke-Command` Befehls.</span><span class="sxs-lookup"><span data-stu-id="d1d82-259">Use the variable that contains the option object as the value of the **SessionOption** parameter of a `New-PSSession`, `Enter-PSSession`, or `Invoke-Command` command.</span></span>

<span data-ttu-id="d1d82-260">Der folgende Befehl erstellt z. b. ein Sitzungs Options Objekt mit Proxy Sitzungs Optionen und verwendet dann das-Objekt, um eine Remote Sitzung zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="d1d82-260">For example, the following command creates a session option object with proxy session options and then uses the object to create a remote session.</span></span>

```powershell
$SessionOption = New-PSSessionOption -ProxyAccessType IEConfig `
-ProxyAuthentication Negotiate -ProxyCredential Domain01\User01

New-PSSession -ConnectionURI https://www.fabrikam.com
```

<span data-ttu-id="d1d82-261">Weitere Informationen zum `New-PSSessionOption` Cmdlet finden Sie unter [New-pssessionoption](xref:Microsoft.PowerShell.Core.New-PSSessionOption).</span><span class="sxs-lookup"><span data-stu-id="d1d82-261">For more information about the `New-PSSessionOption` cmdlet, see [New-PSSessionOption](xref:Microsoft.PowerShell.Core.New-PSSessionOption).</span></span>

<span data-ttu-id="d1d82-262">Um diese Optionen für alle Remote Befehle in der aktuellen Sitzung festzulegen, verwenden Sie das Options Objekt, das `New-PSSessionOption` im Wert der `$PSSessionOption` Preference-Variablen erstellt.</span><span class="sxs-lookup"><span data-stu-id="d1d82-262">To set these options for all remote commands in the current session, use the option object that `New-PSSessionOption` creates in the value of the `$PSSessionOption` preference variable.</span></span> <span data-ttu-id="d1d82-263">Weitere Informationen finden Sie unter [about_Preference_Variables](about_Preference_Variables.md).</span><span class="sxs-lookup"><span data-stu-id="d1d82-263">For more information, see [about_Preference_Variables](about_Preference_Variables.md).</span></span>

<span data-ttu-id="d1d82-264">Um diese Optionen für alle Remote Befehle für alle PowerShell-Sitzungen auf dem lokalen Computer festzulegen, fügen Sie `$PSSessionOption` Ihrem PowerShell-Profil die Preference-Variable hinzu.</span><span class="sxs-lookup"><span data-stu-id="d1d82-264">To set these options for all remote commands all PowerShell sessions on the local computer, add the `$PSSessionOption` preference variable to your PowerShell profile.</span></span> <span data-ttu-id="d1d82-265">Weitere Informationen zu PowerShell-Profilen finden Sie unter [about_Profiles](about_Profiles.md).</span><span class="sxs-lookup"><span data-stu-id="d1d82-265">For more information about PowerShell profiles, see [about_Profiles](about_Profiles.md).</span></span>

### <a name="how-to-detect-a-32-bit-session-on-a-64-bit-computer"></a><span data-ttu-id="d1d82-266">Erkennen einer 32-Bit-Sitzung auf einem 64-Bit-Computer</span><span class="sxs-lookup"><span data-stu-id="d1d82-266">How to detect a 32-bit session on a 64-bit computer</span></span>

```
ERROR: The term "<tool-Name>" is not recognized as the name of a cmdlet,
function, script file, or operable program. Check the spelling of the name, or
if a path was included, verify that the path is correct and try again.
```

<span data-ttu-id="d1d82-267">Wenn auf dem Remote Computer eine 64-Bit-Version von Windows ausgeführt wird und der Remote Befehl eine 32-Bit-Sitzungs Konfiguration verwendet, wie z. b. Microsoft. PowerShell32, wird von Windows-Remoteverwaltung (WinRM) ein WOW64-Prozess geladen, und Windows leitet automatisch alle Verweise auf das `$env:Windir\System32` Verzeichnis in das `$env:Windir\SysWOW64` Verzeichnis um.</span><span class="sxs-lookup"><span data-stu-id="d1d82-267">If the remote computer is running a 64-bit version of Windows, and the remote command is using a 32-bit session configuration, such as Microsoft.PowerShell32, Windows Remote Management (WinRM) loads a WOW64 process and Windows automatically redirects all references to the `$env:Windir\System32` directory to the `$env:Windir\SysWOW64` directory.</span></span>

<span data-ttu-id="d1d82-268">Wenn Sie versuchen, Tools im Verzeichnis "System32" zu verwenden, die keine Entsprechungen im Verzeichnis "syswow64" aufweisen, z `Defrag.exe` . b., können die Tools nicht im Verzeichnis gefunden werden.</span><span class="sxs-lookup"><span data-stu-id="d1d82-268">As a result, if you try to use tools in the System32 directory that do not have counterparts in the SysWow64 directory, such as `Defrag.exe`, the tools cannot be found in the directory.</span></span>

<span data-ttu-id="d1d82-269">Um die Prozessorarchitektur zu ermitteln, die in der Sitzung verwendet wird, verwenden Sie den Wert der **PROCESSOR_ARCHITECTURE** -Umgebungsvariablen.</span><span class="sxs-lookup"><span data-stu-id="d1d82-269">To find the processor architecture that is being used in the session, use the value of the **PROCESSOR_ARCHITECTURE** environment variable.</span></span> <span data-ttu-id="d1d82-270">Der folgende Befehl sucht die Prozessorarchitektur der Sitzung in der `$s` Variablen.</span><span class="sxs-lookup"><span data-stu-id="d1d82-270">The following command finds the processor architecture of the session in the `$s` variable.</span></span>

```powershell
$s = New-PSSession -ComputerName Server01 -ConfigurationName CustomShell
Invoke-Command -Session $s {$env:PROCESSOR_ARCHITECTURE}
```

```Output
x86
```

<span data-ttu-id="d1d82-271">Weitere Informationen zu Sitzungs Konfigurationen finden Sie unter [about_Session_Configurations](about_Session_Configurations.md).</span><span class="sxs-lookup"><span data-stu-id="d1d82-271">For more information about session configurations, see [about_Session_Configurations](about_Session_Configurations.md).</span></span>

## <a name="troubleshooting-policy-and-preference-issues"></a><span data-ttu-id="d1d82-272">Problembehandlung und bevorzugte Probleme</span><span class="sxs-lookup"><span data-stu-id="d1d82-272">Troubleshooting policy and preference issues</span></span>

<span data-ttu-id="d1d82-273">In diesem Abschnitt werden remotingprobleme im Zusammenhang mit Richtlinien und Einstellungen erläutert, die auf den lokalen Computern und Remote Computern festgelegt sind.</span><span class="sxs-lookup"><span data-stu-id="d1d82-273">This section discusses remoting problems that are related to policies and preferences set on the local and remote computers.</span></span>

### <a name="how-to-change-the-execution-policy-for-import-pssession-and-import-module"></a><span data-ttu-id="d1d82-274">Vorgehensweise beim Ändern der Ausführungs Richtlinie für Import-PSSession und Import-Module</span><span class="sxs-lookup"><span data-stu-id="d1d82-274">How to change the execution policy for Import-PSSession and Import-Module</span></span>

```
ERROR: Import-Module: File <filename> cannot be loaded because the
execution of scripts is disabled on this system.
```

<span data-ttu-id="d1d82-275">`Import-PSSession`Mit den `Export-PSSession` Cmdlets und werden Module erstellt, die nicht signierte Skriptdateien und Formatierungs Dateien enthalten.</span><span class="sxs-lookup"><span data-stu-id="d1d82-275">The `Import-PSSession` and `Export-PSSession` cmdlets create modules that contains unsigned script files and formatting files.</span></span>

<span data-ttu-id="d1d82-276">Zum Importieren der Module, die von diesen Cmdlets erstellt werden, entweder mithilfe von `Import-PSSession` oder `Import-Module` , kann die Ausführungs Richtlinie in der aktuellen Sitzung nicht eingeschränkt oder AllSigned werden.</span><span class="sxs-lookup"><span data-stu-id="d1d82-276">To import the modules that are created by these cmdlets, either by using `Import-PSSession` or `Import-Module`, the execution policy in the current session cannot be Restricted or AllSigned.</span></span> <span data-ttu-id="d1d82-277">Weitere Informationen zu PowerShell-Ausführungsrichtlinien finden Sie unter [about_Execution_Policies](about_Execution_Policies.md).</span><span class="sxs-lookup"><span data-stu-id="d1d82-277">For information about PowerShell execution policies, see [about_Execution_Policies](about_Execution_Policies.md).</span></span>

<span data-ttu-id="d1d82-278">Um die Module zu importieren, ohne die Ausführungs Richtlinie für den lokalen Computer zu ändern, der in der Registrierung festgelegt ist, verwenden Sie den **Scope** -Parameter von, `Set-ExecutionPolicy` um eine weniger restriktive Ausführungs Richtlinie für einen einzelnen Prozess festzulegen.</span><span class="sxs-lookup"><span data-stu-id="d1d82-278">To import the modules without changing the execution policy for the local computer that is set in the registry, use the **Scope** parameter of `Set-ExecutionPolicy` to set a less restrictive execution policy for a single process.</span></span>

<span data-ttu-id="d1d82-279">Mit dem folgenden Befehl wird z. b. ein Prozess mit der `RemoteSigned` Ausführungs Richtlinie gestartet.</span><span class="sxs-lookup"><span data-stu-id="d1d82-279">For example, the following command starts a process with the `RemoteSigned` execution policy.</span></span> <span data-ttu-id="d1d82-280">Die Änderung der Ausführungs Richtlinie wirkt sich nur auf den aktuellen Prozess aus und ändert nicht die Registrierungs Einstellung für die PowerShell- **ExecutionPolicy** .</span><span class="sxs-lookup"><span data-stu-id="d1d82-280">The execution policy change affects only the current process and does not change the PowerShell **ExecutionPolicy** registry setting.</span></span>

```powershell
Set-ExecutionPolicy -Scope process -ExecutionPolicy RemoteSigned
```

<span data-ttu-id="d1d82-281">Sie können auch den **ExecutionPolicy** -Parameter von verwenden `PowerShell.exe` , um eine einzelne Sitzung mit einer weniger restriktiven Ausführungs Richtlinie zu starten.</span><span class="sxs-lookup"><span data-stu-id="d1d82-281">You can also use the **ExecutionPolicy** parameter of `PowerShell.exe` to start a single session with a less restrictive execution policy.</span></span>

```powershell
PowerShell.exe -ExecutionPolicy RemoteSigned
```

<span data-ttu-id="d1d82-282">Weitere Informationen zu Ausführungsrichtlinien finden Sie unter [about_Execution_Policies](about_Execution_Policies.md).</span><span class="sxs-lookup"><span data-stu-id="d1d82-282">For more information about execution policies, see [about_Execution_Policies](about_Execution_Policies.md).</span></span> <span data-ttu-id="d1d82-283">Geben Sie Folgendes ein, um weitere Informationen zu erhalten: `PowerShell.exe -?`.</span><span class="sxs-lookup"><span data-stu-id="d1d82-283">For more information, type `PowerShell.exe -?`.</span></span>

### <a name="how-to-set-and-change-quotas"></a><span data-ttu-id="d1d82-284">Festlegen und Ändern von Kontingenten</span><span class="sxs-lookup"><span data-stu-id="d1d82-284">How to set and change quotas</span></span>

```
ERROR: The total data received from the remote client exceeded allowed
maximum.
```

<span data-ttu-id="d1d82-285">Mithilfe von Kontingenten können Sie den lokalen Computer und den Remote Computer vor übermäßig hoher Ressourcenverwendung (versehentlich und bösartig) schützen.</span><span class="sxs-lookup"><span data-stu-id="d1d82-285">You can use quotas to protect the local computer and the remote computer from excessive resource use, both accidental and malicious.</span></span>

<span data-ttu-id="d1d82-286">Die folgenden Kontingente sind in der grundlegenden Konfiguration verfügbar.</span><span class="sxs-lookup"><span data-stu-id="d1d82-286">The following quotas are available in the basic configuration.</span></span>

- <span data-ttu-id="d1d82-287">Der WSMAN-Anbieter (WSMAN:) bietet mehrere Kontingent Einstellungen, wie z. b. die Einstellungen **maxenvelopesizekb** und **maxproviderrequests** im `WSMan:<ComputerName>` Knoten und die Einstellungen **maxconcurrentoperations**, **maxconcurrentoperationsperuser** und **MaxConnections** im `WSMan:<ComputerName>\Service` Knoten.</span><span class="sxs-lookup"><span data-stu-id="d1d82-287">The WSMan provider (WSMan:) provides several quota settings, such as the **MaxEnvelopeSizeKB** and **MaxProviderRequests** settings in the `WSMan:<ComputerName>` node and the **MaxConcurrentOperations**, **MaxConcurrentOperationsPerUser**, and **MaxConnections** settings in the `WSMan:<ComputerName>\Service` node.</span></span>

- <span data-ttu-id="d1d82-288">Sie können den lokalen Computer mit den Parametern **maximumreceiveddatasizepercommand** und **maximumreceivedobjectsize** des `New-PSSessionOption` Cmdlets und der Preference- `$PSSessionOption` Variablen schützen.</span><span class="sxs-lookup"><span data-stu-id="d1d82-288">You can protect the local computer by using the **MaximumReceivedDataSizePerCommand** and **MaximumReceivedObjectSize** parameters of the `New-PSSessionOption` cmdlet and the `$PSSessionOption` preference variable.</span></span>

- <span data-ttu-id="d1d82-289">Sie können den Remote Computer schützen, indem Sie den Sitzungs Konfigurationen Einschränkungen hinzufügen, z. b. mit den Parametern **maximumreceiveddatasizepercommandmb** und **maximumreceivedobjectsizemb** des `Register-PSSessionConfiguration` Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="d1d82-289">You can protect the remote computer by adding restrictions to the session configurations, such as by using the **MaximumReceivedDataSizePerCommandMB** and **MaximumReceivedObjectSizeMB** parameters of the `Register-PSSessionConfiguration` cmdlet.</span></span>

<span data-ttu-id="d1d82-290">Wenn Kontingente mit einem Befehl in Konflikt stehen, generiert PowerShell einen Fehler.</span><span class="sxs-lookup"><span data-stu-id="d1d82-290">When quotas conflict with a command, PowerShell generates an error.</span></span>

<span data-ttu-id="d1d82-291">Um den Fehler zu beheben, ändern Sie den Remote Befehl so, dass er dem Kontingent entspricht.</span><span class="sxs-lookup"><span data-stu-id="d1d82-291">To resolve the error, change the remote command to comply with the quota.</span></span> <span data-ttu-id="d1d82-292">Sie können auch die Quelle des Kontingents ermitteln und dann das Kontingent erhöhen, um den Abschluss des Befehls zuzulassen.</span><span class="sxs-lookup"><span data-stu-id="d1d82-292">Or, determine the source of the quota, and then increase the quota to allow the command to complete.</span></span>

<span data-ttu-id="d1d82-293">Der folgende Befehl erhöht z. b. das Objektgrößen Kontingent in der Microsoft. PowerShell-Sitzungs Konfiguration auf dem Remote Computer von 10 MB (Standardwert) auf 11 MB.</span><span class="sxs-lookup"><span data-stu-id="d1d82-293">For example, the following command increases the object size quota in the Microsoft.PowerShell session configuration on the remote computer from 10 MB (the default value) to 11 MB.</span></span>

```powershell
Set-PSSessionConfiguration -Name microsoft.PowerShell `
  -MaximumReceivedObjectSizeMB 11 -Force
```

<span data-ttu-id="d1d82-294">Weitere Informationen zum- `New-PSSessionOption` Cmdlet finden Sie unter `New-PSSessionOption` .</span><span class="sxs-lookup"><span data-stu-id="d1d82-294">For more information about the `New-PSSessionOption` cmdlet, see `New-PSSessionOption`.</span></span>

<span data-ttu-id="d1d82-295">Weitere Informationen zu den WS-Management Kontingenten finden Sie unter [about_WSMan_Provider](../../Microsoft.WsMan.Management/About/about_WSMan_Provider.md).</span><span class="sxs-lookup"><span data-stu-id="d1d82-295">For more information about the WS-Management quotas, see [about_WSMan_Provider](../../Microsoft.WsMan.Management/About/about_WSMan_Provider.md).</span></span>

### <a name="how-to-resolve-timeout-errors"></a><span data-ttu-id="d1d82-296">Auflösen von Timeout Fehlern</span><span class="sxs-lookup"><span data-stu-id="d1d82-296">How to resolve timeout errors</span></span>

```
ERROR: The WS-Management service cannot complete the operation within
the time specified in OperationTimeout.
```

<span data-ttu-id="d1d82-297">Sie können Timeouts verwenden, um den lokalen Computer und den Remote Computer vor übermäßig hoher Ressourcenverwendung zu schützen, sowohl versehentlich als auch bösartig.</span><span class="sxs-lookup"><span data-stu-id="d1d82-297">You can use timeouts to protect the local computer and the remote computer from excessive resource use, both accidental and malicious.</span></span> <span data-ttu-id="d1d82-298">Wenn Timeouts auf dem lokalen Computer und auf dem Remote Computer festgelegt sind, verwendet PowerShell die kürzesten Timeout Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="d1d82-298">When timeouts are set on both the local and remote computer, PowerShell uses the shortest timeout settings.</span></span>

<span data-ttu-id="d1d82-299">Die folgenden Timeouts sind in der grundlegenden Konfiguration verfügbar.</span><span class="sxs-lookup"><span data-stu-id="d1d82-299">The following timeouts are available in the basic configuration.</span></span>

- <span data-ttu-id="d1d82-300">Der WSMAN-Anbieter (WSMAN:) bietet mehrere Client seitige und Dienst seitige Timeout Einstellungen, wie z. b. die Einstellung **maxtimeoutms** im `WSMan:<ComputerName>` Knoten und die Einstellungen **enumerationtimeoutms** und **maxpacketretrievaltimeseconds** im `WSMan:<ComputerName>\Service` Knoten.</span><span class="sxs-lookup"><span data-stu-id="d1d82-300">The WSMan provider (WSMan:) provides several client-side and service-side timeout settings, such as the **MaxTimeoutms** setting in the `WSMan:<ComputerName>` node and the **EnumerationTimeoutms** and **MaxPacketRetrievalTimeSeconds** settings in the `WSMan:<ComputerName>\Service` node.</span></span>

- <span data-ttu-id="d1d82-301">Sie können den lokalen Computer mit den Parametern **canceltimeout**, **IdleTimeout**, **OpenTimeout** und **OperationTimeout** des `New-PSSessionOption` Cmdlets und der `$PSSessionOption` Preference-Variablen schützen.</span><span class="sxs-lookup"><span data-stu-id="d1d82-301">You can protect the local computer by using the **CancelTimeout**, **IdleTimeout**, **OpenTimeout**, and **OperationTimeout** parameters of the `New-PSSessionOption` cmdlet and the `$PSSessionOption` preference variable.</span></span>

- <span data-ttu-id="d1d82-302">Sie können den Remote Computer auch schützen, indem Sie Timeout Werte Programm gesteuert in der Sitzungs Konfiguration für die Sitzung festlegen.</span><span class="sxs-lookup"><span data-stu-id="d1d82-302">You can also protect the remote computer by setting timeout values programmatically in the session configuration for the session.</span></span>

<span data-ttu-id="d1d82-303">Wenn ein Timeout Wert keinen Vorgang zulässt, beendet PowerShell den Vorgang und generiert einen Fehler.</span><span class="sxs-lookup"><span data-stu-id="d1d82-303">When a timeout value does not permit a operation to complete, PowerShell terminates the operation and generates an error.</span></span>

<span data-ttu-id="d1d82-304">Um den Fehler zu beheben, ändern Sie den Befehl innerhalb des Timeout Intervalls in "Fertigstellen", oder ermitteln Sie die Quelle des Timeout Limits, und erhöhen Sie das Timeout Intervall, um den Abschluss des Befehls zuzulassen.</span><span class="sxs-lookup"><span data-stu-id="d1d82-304">To resolve the error, change the command to complete within the timeout interval or determine the source of the timeout limit and increase the timeout interval to allow the command to complete.</span></span>

<span data-ttu-id="d1d82-305">Beispielsweise verwenden die folgenden Befehle das- `New-PSSessionOption` Cmdlet, um ein Sitzungs Options Objekt mit einem **OperationTimeout** -Wert von 4 Minuten (in MS) zu erstellen, und verwenden dann das Sitzungs Options Objekt, um eine Remote Sitzung zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="d1d82-305">For example, the following commands use the `New-PSSessionOption` cmdlet to create a session option object with an **OperationTimeout** value of 4 minutes (in MS) and then use the session option object to create a remote session.</span></span>

```powershell
$pso = New-PSSessionoption -OperationTimeout 240000

New-PSSession -ComputerName Server01 -sessionOption $pso
```

<span data-ttu-id="d1d82-306">Weitere Informationen zu den WS-Management Timeouts finden Sie im Hilfethema für den WSMAN-Anbieter (Type `Get-Help WSMan` ).</span><span class="sxs-lookup"><span data-stu-id="d1d82-306">For more information about the WS-Management timeouts, see the Help topic for the WSMan provider (type `Get-Help WSMan`).</span></span>

<span data-ttu-id="d1d82-307">Weitere Informationen zum `New-PSSessionOption` Cmdlet finden Sie unter [New-pssessionoption](xref:Microsoft.PowerShell.Core.New-PSSessionOption).</span><span class="sxs-lookup"><span data-stu-id="d1d82-307">For more information about the `New-PSSessionOption` cmdlet, see [New-PSSessionOption](xref:Microsoft.PowerShell.Core.New-PSSessionOption).</span></span>

## <a name="troubleshooting-unresponsive-behavior"></a><span data-ttu-id="d1d82-308">Behandeln von nicht reagierenden Verhalten</span><span class="sxs-lookup"><span data-stu-id="d1d82-308">Troubleshooting unresponsive behavior</span></span>

<span data-ttu-id="d1d82-309">In diesem Abschnitt werden Remoting-Probleme erläutert, die verhindern, dass ein Befehl abgeschlossen wird, und die Rückgabe der PowerShell-Eingabeaufforderung verhindern oder verzögern.</span><span class="sxs-lookup"><span data-stu-id="d1d82-309">This section discusses remoting problems that prevent a command from completing and prevent or delay the return of the PowerShell prompt.</span></span>

### <a name="how-to-interrupt-a-command"></a><span data-ttu-id="d1d82-310">Vorgehensweise beim Unterbrechen eines Befehls</span><span class="sxs-lookup"><span data-stu-id="d1d82-310">How to interrupt a command</span></span>

<span data-ttu-id="d1d82-311">Einige systemeigene Windows-Programme, z. b. Programme mit einer Benutzeroberfläche, Konsolen Anwendungen, die Eingabeaufforderung anfordern, und Konsolen Anwendungen, die die Win32-Konsolen-API verwenden, funktionieren im PowerShell-Remote Host nicht ordnungsgemäß.</span><span class="sxs-lookup"><span data-stu-id="d1d82-311">Some native Windows programs, such as programs with a user interface, console applications that prompt for input, and console applications that use the Win32 console API, do not work correctly in the PowerShell remote host.</span></span>

<span data-ttu-id="d1d82-312">Wenn Sie diese Programme verwenden, wird möglicherweise ein unerwartetes Verhalten angezeigt, wie z. b. keine Ausgabe, partielle Ausgabe oder Remote Befehl, der nicht vollständig ist.</span><span class="sxs-lookup"><span data-stu-id="d1d82-312">When you use these programs, you might see unexpected behavior, such as no output, partial output, or a remote command that does not complete.</span></span>

<span data-ttu-id="d1d82-313">Um ein nicht reagierendes Programm zu beenden, geben Sie <kbd>STRG</kbd> + <kbd>C</kbd>ein.</span><span class="sxs-lookup"><span data-stu-id="d1d82-313">To end an unresponsive program, type <kbd>CTRL</kbd>+<kbd>C</kbd>.</span></span> <span data-ttu-id="d1d82-314">Wenn Sie eventuell gemeldete Fehler anzeigen möchten, geben Sie `$error` den lokalen Host und die Remote Sitzung ein.</span><span class="sxs-lookup"><span data-stu-id="d1d82-314">To view any errors that might have been reported, type `$error` in the local host and the remote session.</span></span>

## <a name="how-to-recover-from-an-operation-failure"></a><span data-ttu-id="d1d82-315">Vorgehensweise beim Wiederherstellen nach einem Vorgangs Fehler</span><span class="sxs-lookup"><span data-stu-id="d1d82-315">How to recover from an operation failure</span></span>

```
ERROR: The I/O operation has been aborted because of either a thread exit
or an  application request.
```

<span data-ttu-id="d1d82-316">Dieser Fehler wird zurückgegeben, wenn ein Vorgang beendet wird, bevor er abgeschlossen wird.</span><span class="sxs-lookup"><span data-stu-id="d1d82-316">This error is returned when an operation is terminated before it completes.</span></span>
<span data-ttu-id="d1d82-317">Dies tritt normalerweise auf, wenn der WinRM-Dienst beendet oder neu gestartet wird, während andere WinRM-Vorgänge ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="d1d82-317">Typically, it occurs when the WinRM service stops or restarts while other WinRM operations are in progress.</span></span>

<span data-ttu-id="d1d82-318">Um dieses Problem zu beheben, überprüfen Sie, ob der WinRM-Dienst ausgeführt wird, und wiederholen Sie den Befehl.</span><span class="sxs-lookup"><span data-stu-id="d1d82-318">To resolve this issue, verify that the WinRM service is running and try the command again.</span></span>

1. <span data-ttu-id="d1d82-319">Starten Sie PowerShell mit der Option **als Administrator ausführen** .</span><span class="sxs-lookup"><span data-stu-id="d1d82-319">Start PowerShell with the **Run as administrator** option.</span></span>
1. <span data-ttu-id="d1d82-320">Führen Sie den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="d1d82-320">Run the following command:</span></span>

   `Start-Service WinRM`

1. <span data-ttu-id="d1d82-321">Führen Sie den Befehl erneut aus, der den Fehler generiert hat.</span><span class="sxs-lookup"><span data-stu-id="d1d82-321">Re-run the command that generated the error.</span></span>

## <a name="linux-and-macos-limitations"></a><span data-ttu-id="d1d82-322">Einschränkungen für Linux und macOS</span><span class="sxs-lookup"><span data-stu-id="d1d82-322">Linux and macOS limitations</span></span>

### <a name="authentication"></a><span data-ttu-id="d1d82-323">Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="d1d82-323">Authentication</span></span>

<span data-ttu-id="d1d82-324">Nur die Standard Authentifizierung funktioniert unter macOS und der Versuch, andere Authentifizierungs Schemas zu verwenden, kann dazu führen, dass der Prozess abstürzt.</span><span class="sxs-lookup"><span data-stu-id="d1d82-324">Only basic authentication works on macOS and attempting to use other authentication schemes may result in the process crashing.</span></span>

<span data-ttu-id="d1d82-325">Weitere Informationen finden Sie in den Anweisungen zur [Omi-Authentifizierung](https://github.com/PowerShell/psl-omi-provider#connecting-from-linux-to-windows) .</span><span class="sxs-lookup"><span data-stu-id="d1d82-325">Please see the [OMI authentication](https://github.com/PowerShell/psl-omi-provider#connecting-from-linux-to-windows) instructions.</span></span>

## <a name="see-also"></a><span data-ttu-id="d1d82-326">SIEHE AUCH</span><span class="sxs-lookup"><span data-stu-id="d1d82-326">SEE ALSO</span></span>

[<span data-ttu-id="d1d82-327">Import-PSSession</span><span class="sxs-lookup"><span data-stu-id="d1d82-327">Import-PSSession</span></span>](xref:Microsoft.PowerShell.Utility.Import-PSSession)

[<span data-ttu-id="d1d82-328">Export-PSSession</span><span class="sxs-lookup"><span data-stu-id="d1d82-328">Export-PSSession</span></span>](xref:Microsoft.PowerShell.Utility.Export-PSSession)

[<span data-ttu-id="d1d82-329">Import-Module</span><span class="sxs-lookup"><span data-stu-id="d1d82-329">Import-Module</span></span>](xref:Microsoft.PowerShell.Core.Import-Module)

[<span data-ttu-id="d1d82-330">about_Remote</span><span class="sxs-lookup"><span data-stu-id="d1d82-330">about_Remote</span></span>](about_Remote.md)

[<span data-ttu-id="d1d82-331">about_Remote_Requirements</span><span class="sxs-lookup"><span data-stu-id="d1d82-331">about_Remote_Requirements</span></span>](about_Remote_Requirements.md)

[<span data-ttu-id="d1d82-332">about_Remote_Variables</span><span class="sxs-lookup"><span data-stu-id="d1d82-332">about_Remote_Variables</span></span>](about_Remote_Variables.md)