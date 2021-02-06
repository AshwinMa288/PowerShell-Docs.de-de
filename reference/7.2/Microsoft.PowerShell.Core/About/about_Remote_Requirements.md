---
description: Beschreibt die Systemanforderungen und Konfigurations Anforderungen für das Ausführen von Remote Befehlen in PowerShell.
Locale: en-US
ms.date: 01/03/2018
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_remote_requirements?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Remote_Requirements
ms.openlocfilehash: 4a994ded51195e5932af7bb4af0b2e6fb3a67857
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99596960"
---
# <a name="about-remote-requirements"></a><span data-ttu-id="b410f-103">Informationen zu Remote Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b410f-103">About Remote Requirements</span></span>

## <a name="short-description"></a><span data-ttu-id="b410f-104">KURZE BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="b410f-104">SHORT DESCRIPTION</span></span>
<span data-ttu-id="b410f-105">Beschreibt die Systemanforderungen und Konfigurations Anforderungen für das Ausführen von Remote Befehlen in PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b410f-105">Describes the system requirements and configuration requirements for running remote commands in PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="b410f-106">LANGE BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="b410f-106">LONG DESCRIPTION</span></span>

<span data-ttu-id="b410f-107">In diesem Thema werden die Systemanforderungen, Benutzer Anforderungen und Ressourcenanforderungen für das Einrichten von Remote Verbindungen und das Ausführen von Remote Befehlen in PowerShell beschrieben.</span><span class="sxs-lookup"><span data-stu-id="b410f-107">This topic describes the system requirements, user requirements, and resource requirements for establishing remote connections and running remote commands in PowerShell.</span></span> <span data-ttu-id="b410f-108">Außerdem finden Sie Anweisungen zum Konfigurieren von Remote Vorgängen.</span><span class="sxs-lookup"><span data-stu-id="b410f-108">It also provides instructions for configuring remote operations.</span></span>

<span data-ttu-id="b410f-109">Hinweis: viele Cmdlets (einschließlich der Cmdlets "Get-Service", "Get-Process", "Get-WmiObject", "Get-EventLog" und "Get-WinEvent") rufen Objekte von Remote Computern ab, indem Sie Microsoft .NET Framework-Methoden zum Abrufen der Objekte verwenden.</span><span class="sxs-lookup"><span data-stu-id="b410f-109">Note: Many cmdlets (including the Get-Service, Get-Process, Get-WMIObject, Get-EventLog, and Get-WinEvent cmdlets) get objects from remote computers by using Microsoft .NET Framework methods to retrieve the objects.</span></span> <span data-ttu-id="b410f-110">Die PowerShell-Remoting-Infrastruktur wird nicht verwendet.</span><span class="sxs-lookup"><span data-stu-id="b410f-110">They do not use the PowerShell remoting infrastructure.</span></span> <span data-ttu-id="b410f-111">Die Anforderungen in diesem Dokument gelten nicht für diese Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="b410f-111">The requirements in this document do not apply to these cmdlets.</span></span>

<span data-ttu-id="b410f-112">Informationen zu den Cmdlets, die über einen Computername-Parameter verfügen, aber keine PowerShell-Remoting verwenden, finden Sie in der Beschreibung des Computername-Parameters der Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="b410f-112">To find the cmdlets that have a ComputerName parameter but do not use PowerShell remoting, read the description of the ComputerName parameter of the cmdlets.</span></span>

## <a name="system-requirements"></a><span data-ttu-id="b410f-113">System Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b410f-113">SYSTEM REQUIREMENTS</span></span>

<span data-ttu-id="b410f-114">Zum Ausführen von Remote Sitzungen in Windows PowerShell 3,0 müssen die lokalen Computer und Remote Computer über Folgendes verfügen:</span><span class="sxs-lookup"><span data-stu-id="b410f-114">To run remote sessions on Windows PowerShell 3.0, the local and remote computers must have the following:</span></span>

- <span data-ttu-id="b410f-115">Windows PowerShell 3,0 oder höher</span><span class="sxs-lookup"><span data-stu-id="b410f-115">Windows PowerShell 3.0 or later</span></span>
- <span data-ttu-id="b410f-116">Das Microsoft .NET Framework 4 oder höher</span><span class="sxs-lookup"><span data-stu-id="b410f-116">The Microsoft .NET Framework 4 or later</span></span>
- <span data-ttu-id="b410f-117">Windows-Remoteverwaltung 3,0</span><span class="sxs-lookup"><span data-stu-id="b410f-117">Windows Remote Management 3.0</span></span>

<span data-ttu-id="b410f-118">Zum Ausführen von Remote Sitzungen in Windows PowerShell 2,0 müssen die lokalen Computer und Remote Computer über Folgendes verfügen:</span><span class="sxs-lookup"><span data-stu-id="b410f-118">To run remote sessions on Windows PowerShell 2.0, the local and remote computers must have the following:</span></span>

- <span data-ttu-id="b410f-119">Windows PowerShell 2,0 oder höher</span><span class="sxs-lookup"><span data-stu-id="b410f-119">Windows PowerShell 2.0 or later</span></span>
- <span data-ttu-id="b410f-120">Das Microsoft .NET Framework 2,0 oder höher</span><span class="sxs-lookup"><span data-stu-id="b410f-120">The Microsoft .NET Framework 2.0 or later</span></span>
- <span data-ttu-id="b410f-121">Windows-Remoteverwaltung 2,0</span><span class="sxs-lookup"><span data-stu-id="b410f-121">Windows Remote Management 2.0</span></span>

<span data-ttu-id="b410f-122">Sie können Remote Sitzungen zwischen Computern erstellen, auf denen Windows PowerShell 2,0 und Windows PowerShell 3,0 ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="b410f-122">You can create remote sessions between computers running Windows PowerShell 2.0 and Windows PowerShell 3.0.</span></span> <span data-ttu-id="b410f-123">Features, die nur in Windows PowerShell 3,0 ausgeführt werden, z. b. die Möglichkeit, eine Verbindung mit Sitzungen herzustellen und diese wiederherzustellen, sind jedoch nur verfügbar, wenn auf beiden Computern Windows PowerShell 3,0 ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="b410f-123">However, features that run only on Windows PowerShell 3.0, such as the ability to disconnect and reconnect to sessions, are available only when both computers are running Windows PowerShell 3.0.</span></span>

<span data-ttu-id="b410f-124">Um die Versionsnummer einer installierten PowerShell-Version zu ermitteln, verwenden Sie die $PSVersionTable automatische Variable.</span><span class="sxs-lookup"><span data-stu-id="b410f-124">To find the version number of an installed version of PowerShell, use the $PSVersionTable automatic variable.</span></span>

<span data-ttu-id="b410f-125">Windows-Remoteverwaltung (WinRM) 3,0 und Microsoft .NET Framework 4 sind in Windows 8, Windows Server 2012 und neueren Versionen des Windows-Betriebssystems enthalten.</span><span class="sxs-lookup"><span data-stu-id="b410f-125">Windows Remote Management (WinRM) 3.0 and Microsoft .NET Framework 4 are included in Windows 8, Windows Server 2012, and newer releases of the Windows operating system.</span></span> <span data-ttu-id="b410f-126">WinRM 3,0 ist in Windows Management Framework 3,0 für ältere Betriebssysteme enthalten.</span><span class="sxs-lookup"><span data-stu-id="b410f-126">WinRM 3.0 is included in Windows Management Framework 3.0 for older operating systems.</span></span> <span data-ttu-id="b410f-127">Wenn der Computer nicht über die erforderliche Version von WinRM oder Microsoft .NET Framework verfügt, tritt bei der Installation ein Fehler auf.</span><span class="sxs-lookup"><span data-stu-id="b410f-127">If the computer does not have the required version of WinRM or the Microsoft .NET Framework, the installation fails.</span></span>

## <a name="user-permissions"></a><span data-ttu-id="b410f-128">BENUTZERBERECHTIGUNGEN</span><span class="sxs-lookup"><span data-stu-id="b410f-128">USER PERMISSIONS</span></span>

<span data-ttu-id="b410f-129">Zum Erstellen von Remote Sitzungen und zum Ausführen von Remote Befehlen muss der aktuelle Benutzer standardmäßig Mitglied der Gruppe "Administratoren" auf dem Remote Computer sein oder die Anmelde Informationen eines Administrators angeben.</span><span class="sxs-lookup"><span data-stu-id="b410f-129">To create remote sessions and run remote commands, by default, the current user must be a member of the Administrators group on the remote computer or provide the credentials of an administrator.</span></span> <span data-ttu-id="b410f-130">Andernfalls führt der Befehl zu einem Fehler.</span><span class="sxs-lookup"><span data-stu-id="b410f-130">Otherwise, the command fails.</span></span>

<span data-ttu-id="b410f-131">Die erforderlichen Berechtigungen zum Erstellen von Sitzungen und Ausführen von Befehlen auf einem Remote Computer (oder in einer Remote Sitzung auf dem lokalen Computer) werden von der Sitzungs Konfiguration (auch als "Endpunkt" bezeichnet) auf dem Remote Computer eingerichtet, mit dem die Sitzung eine Verbindung herstellt.</span><span class="sxs-lookup"><span data-stu-id="b410f-131">The permissions required to create sessions and run commands on a remote computer (or in a remote session on the local computer) are established by the session configuration (also known as an "endpoint") on the remote computer to which the session connects.</span></span> <span data-ttu-id="b410f-132">Insbesondere die Sicherheits Beschreibung der Sitzungs Konfiguration bestimmt, wer Zugriff auf die Sitzungs Konfiguration hat und wer Sie zum Herstellen der Verbindung verwenden kann.</span><span class="sxs-lookup"><span data-stu-id="b410f-132">Specifically, the security descriptor on the session configuration determines who has access to the session configuration and who can use it to connect.</span></span>

<span data-ttu-id="b410f-133">Die Sicherheits Deskriptoren in den Standard Sitzungs Konfigurationen Microsoft. PowerShell, Microsoft. PowerShell32 und Microsoft. PowerShell. Workflow erlauben nur den Zugriff auf Mitglieder der Gruppe "Administratoren".</span><span class="sxs-lookup"><span data-stu-id="b410f-133">The security descriptors on the default session configurations, Microsoft.PowerShell, Microsoft.PowerShell32, and Microsoft.PowerShell.Workflow, allow access only to members of the Administrators group.</span></span>

<span data-ttu-id="b410f-134">Wenn der aktuelle Benutzer nicht über die Berechtigung zum Verwenden der Sitzungs Konfiguration verfügt, tritt beim Ausführen des Befehls zum Ausführen eines Befehls (bei dem eine temporäre Sitzung verwendet wird) oder beim Erstellen einer persistenten Sitzung auf dem Remote Computer ein Fehler auf.</span><span class="sxs-lookup"><span data-stu-id="b410f-134">If the current user doesn't have permission to use the session configuration, the command to run a command (which uses a temporary session) or create a persistent session on the remote computer fails.</span></span> <span data-ttu-id="b410f-135">Der Benutzer kann den ConfigurationName-Parameter von Cmdlets verwenden, die Sitzungen erstellen, um eine andere Sitzungs Konfiguration auszuwählen, sofern eine vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="b410f-135">The user can use the ConfigurationName parameter of cmdlets that create sessions to select a different session configuration, if one is available.</span></span>

<span data-ttu-id="b410f-136">Mitglieder der Gruppe "Administratoren" auf einem Computer können ermitteln, wer über die Berechtigung zum Herstellen einer Remote Verbindung mit dem Computer verfügt, indem Sie die Sicherheits Deskriptoren der Standard Sitzungs Konfigurationen ändern und neue Sitzungs Konfigurationen mit unterschiedlichen Sicherheits Beschreibungen erstellen.</span><span class="sxs-lookup"><span data-stu-id="b410f-136">Members of the Administrators group on a computer can determine who has permission to connect to the computer remotely by changing the security descriptors on the default session configurations and by creating new session configurations with different security descriptors.</span></span>

<span data-ttu-id="b410f-137">Weitere Informationen zu Sitzungs Konfigurationen finden Sie unter [about_Session_Configurations](about_Session_Configurations.md).</span><span class="sxs-lookup"><span data-stu-id="b410f-137">For more information about session configurations, see [about_Session_Configurations](about_Session_Configurations.md).</span></span>

## <a name="windows-network-locations"></a><span data-ttu-id="b410f-138">Windows-Netzwerk Orte</span><span class="sxs-lookup"><span data-stu-id="b410f-138">WINDOWS NETWORK LOCATIONS</span></span>

<span data-ttu-id="b410f-139">Ab Windows PowerShell 3,0 kann das Cmdlet "Enable-PSRemoting" Remoting auf Client-und Serverversionen von Windows in privaten, Domänen-und öffentlichen Netzwerken aktivieren.</span><span class="sxs-lookup"><span data-stu-id="b410f-139">Beginning in Windows PowerShell 3.0, the Enable-PSRemoting cmdlet can enable remoting on client and server versions of Windows on private, domain, and public networks.</span></span>

<span data-ttu-id="b410f-140">Unter Serverversionen von Windows mit privaten Netzwerken und Domänen Netzwerken erstellt das Enable-PSRemoting-Cmdlet Firewallregeln, die uneingeschränkten Remote Zugriff zulassen.</span><span class="sxs-lookup"><span data-stu-id="b410f-140">On server versions of Windows with private and domain networks, the Enable-PSRemoting cmdlet creates firewall rules that allow unrestricted remote access.</span></span> <span data-ttu-id="b410f-141">Außerdem wird eine Firewallregel für öffentliche Netzwerke erstellt, die den Remote Zugriff nur von Computern im selben lokalen Subnetz zulässt.</span><span class="sxs-lookup"><span data-stu-id="b410f-141">It also creates a firewall rule for public networks that allows remote access only from computers in the same local subnet.</span></span> <span data-ttu-id="b410f-142">Diese Firewallregel für das lokale Subnetz ist standardmäßig auf Serverversionen von Windows in öffentlichen Netzwerken aktiviert, Enable-PSRemoting aber die Regel erneut anwendet, falls Sie geändert oder gelöscht wurde.</span><span class="sxs-lookup"><span data-stu-id="b410f-142">This local subnet firewall rule is enabled by default on server versions of Windows on public networks, but Enable-PSRemoting reapplies the rule in case it was changed or deleted.</span></span>

<span data-ttu-id="b410f-143">Unter Client Versionen von Windows mit privaten Netzwerken und Domänen Netzwerken erstellt das Cmdlet "Enable-PSRemoting" standardmäßig Firewallregeln, die uneingeschränkten Remote Zugriff zulassen.</span><span class="sxs-lookup"><span data-stu-id="b410f-143">On client versions of Windows with private and domain networks, by default, the Enable-PSRemoting cmdlet creates firewall rules that allow unrestricted remote access.</span></span>

<span data-ttu-id="b410f-144">Um Remoting für Client Versionen von Windows mit öffentlichen Netzwerken zu aktivieren, verwenden Sie den skipnetworkprofilecheck-Parameter des Cmdlets "Enable-PSRemoting".</span><span class="sxs-lookup"><span data-stu-id="b410f-144">To enable remoting on client versions of Windows with public networks, use the SkipNetworkProfileCheck parameter of the Enable-PSRemoting cmdlet.</span></span> <span data-ttu-id="b410f-145">Es wird eine Firewallregel erstellt, die den Remote Zugriff nur von Computern im selben lokalen Subnetz zulässt.</span><span class="sxs-lookup"><span data-stu-id="b410f-145">It creates a firewall rule that allows remote access only from computers in the same local subnet.</span></span>

<span data-ttu-id="b410f-146">Um die Einschränkung des lokalen Subnetzes in öffentlichen Netzwerken zu entfernen und den Remote Zugriff von allen Standorten auf Client-und Serverversionen von Windows zuzulassen, verwenden Sie das Cmdlet "Set-NetFirewallRule" im Netsecurity-Modul.</span><span class="sxs-lookup"><span data-stu-id="b410f-146">To remove the local subnet restriction on public networks and allow remote access from all locations on client and server versions of Windows, use the Set-NetFirewallRule cmdlet in the NetSecurity module.</span></span> <span data-ttu-id="b410f-147">Führen Sie den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="b410f-147">Run the following command:</span></span>

```powershell
Set-NetFirewallRule -Name "WINRM-HTTP-In-TCP-PUBLIC" -RemoteAddress Any
```

<span data-ttu-id="b410f-148">In Windows PowerShell 2,0 erstellt Enable-PSRemoting unter Serverversionen von Windows Firewallregeln, die den Remote Zugriff auf alle Netzwerke erlauben.</span><span class="sxs-lookup"><span data-stu-id="b410f-148">In Windows PowerShell 2.0, on server versions of Windows, Enable-PSRemoting creates firewall rules that permit remote access on all networks.</span></span>

<span data-ttu-id="b410f-149">In Windows PowerShell 2,0 erstellt Enable-PSRemoting unter Client Versionen von Windows Firewallregeln nur in privaten und Domänen Netzwerken.</span><span class="sxs-lookup"><span data-stu-id="b410f-149">In Windows PowerShell 2.0, on client versions of Windows, Enable-PSRemoting creates firewall rules only on private and domain networks.</span></span> <span data-ttu-id="b410f-150">Wenn der Netzwerk Speicherort öffentlich ist, schlägt Enable-PSRemoting fehl.</span><span class="sxs-lookup"><span data-stu-id="b410f-150">If the network location is public, Enable-PSRemoting fails.</span></span>

## <a name="run-as-administrator"></a><span data-ttu-id="b410f-151">als Administrator ausführen</span><span class="sxs-lookup"><span data-stu-id="b410f-151">RUN AS ADMINISTRATOR</span></span>

<span data-ttu-id="b410f-152">Administrator Rechte sind für die folgenden remotingvorgänge erforderlich:</span><span class="sxs-lookup"><span data-stu-id="b410f-152">Administrator privileges are required for the following remoting operations:</span></span>

- <span data-ttu-id="b410f-153">Herstellen einer Remote Verbindung mit dem lokalen Computer.</span><span class="sxs-lookup"><span data-stu-id="b410f-153">Establishing a remote connection to the local computer.</span></span> <span data-ttu-id="b410f-154">Dies wird häufig als "Loopback Szenario" bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="b410f-154">This is commonly known as a "loopback" scenario.</span></span>

- <span data-ttu-id="b410f-155">Verwalten von Sitzungs Konfigurationen auf dem lokalen Computer.</span><span class="sxs-lookup"><span data-stu-id="b410f-155">Managing session configurations on the local computer.</span></span>

- <span data-ttu-id="b410f-156">Anzeigen und ändern WS-Management Einstellungen auf dem lokalen Computer.</span><span class="sxs-lookup"><span data-stu-id="b410f-156">Viewing and changing WS-Management settings on the local computer.</span></span> <span data-ttu-id="b410f-157">Dies sind die Einstellungen im Knoten "localhost" des WSMAN:-Laufwerks.</span><span class="sxs-lookup"><span data-stu-id="b410f-157">These are the settings in the LocalHost node of the WSMAN: drive.</span></span>

<span data-ttu-id="b410f-158">Zum Ausführen dieser Aufgaben müssen Sie PowerShell mit der Option "als Administrator ausführen" starten, auch wenn Sie Mitglied der Gruppe "Administratoren" auf dem lokalen Computer sind.</span><span class="sxs-lookup"><span data-stu-id="b410f-158">To perform these tasks, you must start PowerShell with the "Run as administrator" option even if you are a member of the Administrators group on the local computer.</span></span>

<span data-ttu-id="b410f-159">In Windows 7 und Windows Server 2008 R2, um Windows PowerShell mit der Option "als Administrator ausführen" zu starten:</span><span class="sxs-lookup"><span data-stu-id="b410f-159">In Windows 7 and in Windows Server 2008 R2, to start Windows PowerShell with the "Run as administrator" option:</span></span>

1. <span data-ttu-id="b410f-160">Klicken Sie auf Start, klicken Sie auf alle Programme, klicken Sie auf Zubehör, und klicken Sie dann auf den Ordner Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b410f-160">Click Start, click All Programs, click Accessories, and then click the Windows PowerShell folder.</span></span>
2. <span data-ttu-id="b410f-161">Klicken Sie mit der rechten Maustaste auf Windows PowerShell, und klicken Sie dann auf "als Administrator ausführen".</span><span class="sxs-lookup"><span data-stu-id="b410f-161">Right-click Windows PowerShell, and then click "Run as administrator".</span></span>

<span data-ttu-id="b410f-162">So starten Sie Windows PowerShell mit der Option "als Administrator ausführen":</span><span class="sxs-lookup"><span data-stu-id="b410f-162">To start Windows PowerShell with the "Run as administrator" option:</span></span>

1. <span data-ttu-id="b410f-163">Klicken Sie auf Start, klicken Sie auf alle Programme, und klicken Sie dann auf den Ordner Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b410f-163">Click Start, click All Programs, and then click the Windows PowerShell folder.</span></span>
2. <span data-ttu-id="b410f-164">Klicken Sie mit der rechten Maustaste auf Windows PowerShell, und klicken Sie dann auf "als Administrator ausführen".</span><span class="sxs-lookup"><span data-stu-id="b410f-164">Right-click Windows PowerShell, and then click "Run as administrator".</span></span>

<span data-ttu-id="b410f-165">Die Option "als Administrator ausführen" steht auch in anderen Windows-Explorer-Einträgen für Windows PowerShell, einschließlich Verknüpfungen, zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="b410f-165">The "Run as administrator" option is also available in other Windows Explorer entries for Windows PowerShell, including shortcuts.</span></span> <span data-ttu-id="b410f-166">Klicken Sie einfach mit der rechten Maustaste auf das Element, und klicken Sie dann auf "als Administrator ausführen".</span><span class="sxs-lookup"><span data-stu-id="b410f-166">Just right-click the item, and then click "Run as administrator".</span></span>

<span data-ttu-id="b410f-167">Wenn Sie Windows PowerShell von einem anderen Programm, z. b. Cmd.exe, starten, verwenden Sie die Option "als Administrator ausführen", um das Programm zu starten.</span><span class="sxs-lookup"><span data-stu-id="b410f-167">When you start Windows PowerShell from another program such as Cmd.exe, use the "Run as administrator" option to start the program.</span></span>

## <a name="how-to-configure-your-computer-for-remoting"></a><span data-ttu-id="b410f-168">Konfigurieren des Computers für Remoting</span><span class="sxs-lookup"><span data-stu-id="b410f-168">HOW TO CONFIGURE YOUR COMPUTER FOR REMOTING</span></span>

<span data-ttu-id="b410f-169">Computer, auf denen alle unterstützten Versionen von Windows ausgeführt werden, können Remote-Befehle in PowerShell ohne Konfiguration einrichten und ausführen.</span><span class="sxs-lookup"><span data-stu-id="b410f-169">Computers running all supported versions of Windows can establish remote connections to and run remote commands in PowerShell without any configuration.</span></span> <span data-ttu-id="b410f-170">Um jedoch Verbindungen zu empfangen und Benutzern zu ermöglichen, lokale und Remote Benutzer verwaltete PowerShell-Sitzungen ("pssessions") zu erstellen und Befehle auf dem lokalen Computer auszuführen, müssen Sie PowerShell-Remoting auf dem Computer aktivieren.</span><span class="sxs-lookup"><span data-stu-id="b410f-170">However, to receive connections, and allow users to create local and remote user-managed PowerShell sessions ("PSSessions") and run commands on the local computer, you must enable PowerShell remoting on the computer.</span></span>

<span data-ttu-id="b410f-171">Windows Server 2012 und neuere Versionen von Windows Server sind standardmäßig für PowerShell-Remoting aktiviert.</span><span class="sxs-lookup"><span data-stu-id="b410f-171">Windows Server 2012 and newer releases of Windows Server are enabled for PowerShell remoting by default.</span></span> <span data-ttu-id="b410f-172">Wenn die Einstellungen geändert werden, können Sie die Standardeinstellungen wiederherstellen, indem Sie das Cmdlet "Enable-PSRemoting" ausführen.</span><span class="sxs-lookup"><span data-stu-id="b410f-172">If the settings are changed, you can restore the default settings by running the Enable-PSRemoting cmdlet.</span></span>

<span data-ttu-id="b410f-173">Bei allen anderen unterstützten Versionen von Windows müssen Sie das Enable-PSRemoting-Cmdlet ausführen, um PowerShell-Remoting zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="b410f-173">On all other supported versions of Windows, you need to run the Enable-PSRemoting cmdlet to enable PowerShell remoting.</span></span>

<span data-ttu-id="b410f-174">Die Remoting-Features von PowerShell werden vom WinRM-Dienst unterstützt, bei dem es sich um die Microsoft-Implementierung des WS-Management-Protokolls (Web Services for Management) handelt.</span><span class="sxs-lookup"><span data-stu-id="b410f-174">The remoting features of PowerShell are supported by the WinRM service, which is the Microsoft implementation of the Web Services for Management (WS-Management) protocol.</span></span> <span data-ttu-id="b410f-175">Wenn Sie PowerShell-Remoting aktivieren, ändern Sie die Standardkonfiguration WS-Management und fügen die Systemkonfiguration hinzu, mit der Benutzer eine Verbindung mit der WS-Verwaltung herstellen können.</span><span class="sxs-lookup"><span data-stu-id="b410f-175">When you enable PowerShell remoting, you change the default configuration of WS-Management and add system configuration that allow users to connect to WS-Management.</span></span>

<span data-ttu-id="b410f-176">So konfigurieren Sie PowerShell zum Empfangen von Remote Befehlen:</span><span class="sxs-lookup"><span data-stu-id="b410f-176">To configure PowerShell to receive remote commands:</span></span>

1. <span data-ttu-id="b410f-177">Starten Sie PowerShell mit der Option "als Administrator ausführen".</span><span class="sxs-lookup"><span data-stu-id="b410f-177">Start PowerShell with the "Run as administrator" option.</span></span>
2. <span data-ttu-id="b410f-178">Geben Sie an der Eingabeaufforderung Folgendes ein: `Enable-PSRemoting`</span><span class="sxs-lookup"><span data-stu-id="b410f-178">At the command prompt, type: `Enable-PSRemoting`</span></span>

<span data-ttu-id="b410f-179">Um zu überprüfen, ob Remoting ordnungsgemäß konfiguriert ist, führen Sie einen Test Befehl wie den folgenden Befehl aus, der eine Remote Sitzung auf dem lokalen Computer erstellt.</span><span class="sxs-lookup"><span data-stu-id="b410f-179">To verify that remoting is configured correctly, run a test command such as the following command, which creates a remote session on the local computer.</span></span>

```powershell
New-PSSession
```

<span data-ttu-id="b410f-180">Wenn Remoting ordnungsgemäß konfiguriert ist, erstellt der Befehl eine Sitzung auf dem lokalen Computer und gibt ein Objekt zurück, das die Sitzung darstellt.</span><span class="sxs-lookup"><span data-stu-id="b410f-180">If remoting is configured correctly, the command will create a session on the local computer and return an object that represents the session.</span></span> <span data-ttu-id="b410f-181">Die Ausgabe sollte der folgenden Beispielausgabe ähneln:</span><span class="sxs-lookup"><span data-stu-id="b410f-181">The output should resemble the following sample output:</span></span>

```output
Id Name        ComputerName    State    ConfigurationName
-- ----        ------------    -----    -----
1  Session1    localhost       Opened   Microsoft.PowerShell
```

<span data-ttu-id="b410f-182">Wenn der Befehl fehlschlägt, finden Sie unter Weitere Informationen unter [about_Remote_Troubleshooting](about_Remote_Troubleshooting.md).</span><span class="sxs-lookup"><span data-stu-id="b410f-182">If the command fails, for assistance, see [about_Remote_Troubleshooting](about_Remote_Troubleshooting.md).</span></span>

## <a name="understand-policies"></a><span data-ttu-id="b410f-183">verstehen von Richtlinien</span><span class="sxs-lookup"><span data-stu-id="b410f-183">UNDERSTAND POLICIES</span></span>

<span data-ttu-id="b410f-184">Wenn Sie Remote arbeiten, verwenden Sie zwei Instanzen von PowerShell, eine auf dem lokalen Computer und eine auf dem Remote Computer.</span><span class="sxs-lookup"><span data-stu-id="b410f-184">When you work remotely, you use two instances of PowerShell, one on the local computer and one on the remote computer.</span></span> <span data-ttu-id="b410f-185">Dies hat zur Folge, dass Ihre Arbeit von den Windows-Richtlinien und den PowerShell-Richtlinien auf den lokalen Computern und Remote Computern betroffen ist.</span><span class="sxs-lookup"><span data-stu-id="b410f-185">As a result, your work is affected by the Windows policies and the PowerShell policies on the local and remote computers.</span></span>

<span data-ttu-id="b410f-186">Im Allgemeinen sind die Richtlinien auf dem lokalen Computer wirksam, bevor Sie eine Verbindung herstellen und während Sie die Verbindung herstellen.</span><span class="sxs-lookup"><span data-stu-id="b410f-186">In general, before you connect and as you are establishing the connection, the policies on the local computer are in effect.</span></span> <span data-ttu-id="b410f-187">Wenn Sie die Verbindung verwenden, sind die Richtlinien auf dem Remote Computer wirksam.</span><span class="sxs-lookup"><span data-stu-id="b410f-187">When you are using the connection, the policies on the remote computer are in effect.</span></span>

## <a name="basic-authentication-limitations-on-linux-and-macos"></a><span data-ttu-id="b410f-188">Grundlegende Authentifizierungs Einschränkungen für Linux und macOS</span><span class="sxs-lookup"><span data-stu-id="b410f-188">Basic Authentication Limitations on Linux and macOS</span></span>

<span data-ttu-id="b410f-189">Beim Herstellen einer Verbindung von einem Linux-oder macOS-System zu Windows wird die Standard Authentifizierung über HTTP nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="b410f-189">When connecting from a Linux or macOS system to Windows, Basic Authentication over HTTP is not supported.</span></span> <span data-ttu-id="b410f-190">Die Standard Authentifizierung kann über HTTPS verwendet werden, indem ein Zertifikat auf dem Zielserver installiert wird.</span><span class="sxs-lookup"><span data-stu-id="b410f-190">Basic Authentication can be used over HTTPS by installing a certificate on the target server.</span></span> <span data-ttu-id="b410f-191">Das Zertifikat muss über einen CN-Namen verfügen, der mit dem Hostnamen übereinstimmt, nicht abgelaufen oder gesperrt ist.</span><span class="sxs-lookup"><span data-stu-id="b410f-191">The certificate must have a CN name that matches the hostname, is not expired or revoked.</span></span> <span data-ttu-id="b410f-192">Ein selbst signiertes Zertifikat kann zu Testzwecken verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="b410f-192">A self-signed certificate may be used for testing purposes.</span></span>

<span data-ttu-id="b410f-193">Weitere Informationen finden [Sie unter Gewusst wie: Konfigurieren von WinRM für HTTPS](https://support.microsoft.com/help/2019527/how-to-configure-winrm-for-https) .</span><span class="sxs-lookup"><span data-stu-id="b410f-193">See [How To: Configure WINRM for HTTPS](https://support.microsoft.com/help/2019527/how-to-configure-winrm-for-https) for additional details.</span></span>

<span data-ttu-id="b410f-194">Mit dem folgenden Befehl, der an einer Eingabeaufforderung mit erhöhten Rechten ausgeführt wird, wird der HTTPS-Listener unter Windows mit dem installierten Zertifikat konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="b410f-194">The following command, run from an elevated command prompt, will configure the HTTPS listener on Windows with the installed certificate.</span></span>

```powershell
$hostinfo = '@{Hostname="<DNS_NAME>"; CertificateThumbprint="<THUMBPRINT>"}'
winrm create winrm/config/Listener?Address=*+Transport=HTTPS $hostinfo
```

<span data-ttu-id="b410f-195">Wählen Sie auf der Linux-oder macOS-Seite die Option Standard für Authentifizierung und-US.</span><span class="sxs-lookup"><span data-stu-id="b410f-195">On the Linux or macOS side, select Basic for authentication and -UseSSl.</span></span>

> <span data-ttu-id="b410f-196">Hinweis: die Standard Authentifizierung kann nicht mit Domänen Konten verwendet werden. ein lokales Konto ist erforderlich, und das Konto muss in der Gruppe "Administratoren" sein.</span><span class="sxs-lookup"><span data-stu-id="b410f-196">NOTE: Basic authentication cannot be used with domain accounts; a local account is required and the account must be in the Administrators group.</span></span>

```powershell
# The specified local user must have administrator rights on the target machine.
# Specify the unqualified username.
$cred = Get-Credential username
$session = New-PSSession -Computer <hostname> -Credential $cred `
  -Authentication Basic -UseSSL
```

<span data-ttu-id="b410f-197">Eine Alternative zur Standard Authentifizierung über HTTPS ist Aushandlung.</span><span class="sxs-lookup"><span data-stu-id="b410f-197">An alternative to Basic Authentication over HTTPS is Negotiate.</span></span> <span data-ttu-id="b410f-198">Dies führt zur NTLM-Authentifizierung zwischen Client und Server, und die Nutzlast wird über HTTP verschlüsselt.</span><span class="sxs-lookup"><span data-stu-id="b410f-198">This results in NTLM authentication between the client and server and payload is encrypted over HTTP.</span></span>

<span data-ttu-id="b410f-199">Im folgenden wird die Verwendung von Aushandeln mit New-PSSession veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="b410f-199">The following illustrates using Negotiate with New-PSSession:</span></span>

```powershell
# The specified user must have administrator rights on the target machine.
$cred = Get-Credential username@hostname
$session = New-PSSession -Computer <hostname> -Credential $cred `
  -Authentication Negotiate
```

> [!NOTE]
> <span data-ttu-id="b410f-200">Windows Server erfordert eine zusätzliche Registrierungs Einstellung, damit Administratoren, die nicht über den integrierten Administrator verfügen, eine Verbindung über NTLM herstellen können.</span><span class="sxs-lookup"><span data-stu-id="b410f-200">Windows Server requires an additional registry setting to enable administrators, other than the built in administrator, to connect using NTLM.</span></span>
> <span data-ttu-id="b410f-201">Weitere Informationen finden Sie in der Registrierungs Einstellung LocalAccountTokenFilterPolicy unter Aushandlungs Authentifizierung bei [Authentifizierung für Remote Verbindungen](/windows/win32/winrm/authentication-for-remote-connections)</span><span class="sxs-lookup"><span data-stu-id="b410f-201">Refer to the LocalAccountTokenFilterPolicy registry setting under Negotiate Authentication in [Authentication for Remote Connections](/windows/win32/winrm/authentication-for-remote-connections)</span></span>

## <a name="see-also"></a><span data-ttu-id="b410f-202">SIEHE AUCH</span><span class="sxs-lookup"><span data-stu-id="b410f-202">SEE ALSO</span></span>

[<span data-ttu-id="b410f-203">about_Remote</span><span class="sxs-lookup"><span data-stu-id="b410f-203">about_Remote</span></span>](about_Remote.md)

[<span data-ttu-id="b410f-204">about_Remote_Variables</span><span class="sxs-lookup"><span data-stu-id="b410f-204">about_Remote_Variables</span></span>](about_Remote_Variables.md)

[<span data-ttu-id="b410f-205">about_PSSessions</span><span class="sxs-lookup"><span data-stu-id="b410f-205">about_PSSessions</span></span>](about_PSSessions.md)

[<span data-ttu-id="b410f-206">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="b410f-206">Invoke-Command</span></span>](xref:Microsoft.PowerShell.Core.Invoke-Command)

[<span data-ttu-id="b410f-207">Enter-PSSession</span><span class="sxs-lookup"><span data-stu-id="b410f-207">Enter-PSSession</span></span>](xref:Microsoft.PowerShell.Core.Enter-PSSession)

[<span data-ttu-id="b410f-208">New-PSSession</span><span class="sxs-lookup"><span data-stu-id="b410f-208">New-PSSession</span></span>](xref:Microsoft.PowerShell.Core.New-PSSession)
