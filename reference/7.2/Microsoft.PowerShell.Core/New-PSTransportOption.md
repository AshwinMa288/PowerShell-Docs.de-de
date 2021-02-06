---
external help file: System.Management.Automation.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/new-pstransportoption?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-PSTransportOption
ms.openlocfilehash: fa19ee7d1856eee91a6b1d6a8352017457031202
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99603125"
---
# <span data-ttu-id="f8ff4-102">New-PSTransportOption</span><span class="sxs-lookup"><span data-stu-id="f8ff4-102">New-PSTransportOption</span></span>

## <span data-ttu-id="f8ff4-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="f8ff4-103">SYNOPSIS</span></span>
<span data-ttu-id="f8ff4-104">Erstellt ein Objekt, das erweiterte Optionen für eine Sitzungskonfiguration enthält.</span><span class="sxs-lookup"><span data-stu-id="f8ff4-104">Creates an object that contains advanced options for a session configuration.</span></span>

## <span data-ttu-id="f8ff4-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="f8ff4-105">SYNTAX</span></span>

```
New-PSTransportOption [-MaxIdleTimeoutSec <Int32>] [-ProcessIdleTimeoutSec <Int32>] [-MaxSessions <Int32>]
 [-MaxConcurrentCommandsPerSession <Int32>] [-MaxSessionsPerUser <Int32>] [-MaxMemoryPerSessionMB <Int32>]
 [-MaxProcessesPerSession <Int32>] [-MaxConcurrentUsers <Int32>] [-IdleTimeoutSec <Int32>]
 [-OutputBufferingMode <OutputBufferingMode>] [<CommonParameters>]
```

## <span data-ttu-id="f8ff4-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="f8ff4-106">DESCRIPTION</span></span>

<span data-ttu-id="f8ff4-107">Das **New-PSTransportOption**-Cmdlet erstellt ein Objekt, das Transportoptionen für Sitzungskonfigurationen enthält.</span><span class="sxs-lookup"><span data-stu-id="f8ff4-107">The **New-PSTransportOption** cmdlet creates an object that contains transport options for session configurations.</span></span>
<span data-ttu-id="f8ff4-108">Sie können das Objekt als Wert des *Transportoption* -Parameters von Cmdlets verwenden, die eine Sitzungs Konfiguration erstellen oder ändern, z. b. die Cmdlets Register-PSSessionConfiguration und Set-PSSessionConfiguration.</span><span class="sxs-lookup"><span data-stu-id="f8ff4-108">You can use the object as the value of the *TransportOption* parameter of cmdlets that create or change a session configuration, such as the Register-PSSessionConfiguration and Set-PSSessionConfiguration cmdlets.</span></span>

<span data-ttu-id="f8ff4-109">Sie können auch die Einstellungen für Transportoptionen ändern, indem Sie die Werte der Sitzungskonfigurationseigenschaften im Laufwerk „WSMan:“ bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="f8ff4-109">You can also change the transport option settings by editing the values of the session configuration properties in the WSMan: drive.</span></span>
<span data-ttu-id="f8ff4-110">Weitere Informationen finden Sie unter WSMAN Provider.</span><span class="sxs-lookup"><span data-stu-id="f8ff4-110">For more information, see WSMan Provider.</span></span>

<span data-ttu-id="f8ff4-111">Die Sitzungs Konfigurationsoptionen stellen die Sitzungs Werte dar, die auf Serverseite festgelegt sind, oder das Ende einer Remote Verbindung.</span><span class="sxs-lookup"><span data-stu-id="f8ff4-111">The session configuration options represent the session values set on the server-side, or receiving end of a remote connection.</span></span>
<span data-ttu-id="f8ff4-112">Das Client seitige oder sende Ende der Verbindung kann die Sitzungs Optionswerte festlegen, wenn die Sitzung erstellt wird, oder wenn der Client die Verbindung mit der Sitzung trennt oder wiederherstellt.</span><span class="sxs-lookup"><span data-stu-id="f8ff4-112">The client-side, or sending end of the connection, can set session option values when the session is created, or when the client disconnects from or reconnects to the session.</span></span>
<span data-ttu-id="f8ff4-113">Sofern nicht anders angegeben, haben die clientseitigen Werte bei einem Wertekonflikt Vorrang.</span><span class="sxs-lookup"><span data-stu-id="f8ff4-113">Unless stated otherwise, when the setting values conflict, the client-side values take precedence.</span></span>
<span data-ttu-id="f8ff4-114">Allerdings dürfen die clientseitigen Werte die maximalen, in der Sitzungskonfiguration festgelegten Werte und Kontingente nicht überschreiten.</span><span class="sxs-lookup"><span data-stu-id="f8ff4-114">However, the client-side values cannot violate maximum values and quotas set in the session configuration.</span></span>

<span data-ttu-id="f8ff4-115">Ohne Parameter generiert **New-pstransportoption** ein Transport Options Objekt, das NULL-Werte für alle Optionen enthält.</span><span class="sxs-lookup"><span data-stu-id="f8ff4-115">Without parameters, **New-PSTransportOption** generates a transport option object that has null values for all of the options.</span></span>
<span data-ttu-id="f8ff4-116">Wenn Sie einen Parameter auslassen, verfügt das Objekt über einen NULL-Wert für die Eigenschaft, die vom Parameter dargestellt wird.</span><span class="sxs-lookup"><span data-stu-id="f8ff4-116">If you omit a parameter, the object has a null value for the property that the parameter represents.</span></span>
<span data-ttu-id="f8ff4-117">Ein NULL-Wert hat keine Auswirkung auf die Sitzungs Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="f8ff4-117">A null value does not affect the session configuration.</span></span>

<span data-ttu-id="f8ff4-118">Weitere Informationen zu Sitzungs Optionen finden Sie unter New-pssessionoption.</span><span class="sxs-lookup"><span data-stu-id="f8ff4-118">For more information about session options, see New-PSSessionOption.</span></span>
<span data-ttu-id="f8ff4-119">Weitere Informationen zu Sitzungs Konfigurationen finden Sie unter [about_Session_Configurations](About/about_Session_Configurations.md).</span><span class="sxs-lookup"><span data-stu-id="f8ff4-119">For more information about session configurations, see [about_Session_Configurations](About/about_Session_Configurations.md).</span></span>

<span data-ttu-id="f8ff4-120">Dieses Cmdlet wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="f8ff4-120">This cmdlet was introduced in Windows PowerShell 3.0.</span></span>

## <span data-ttu-id="f8ff4-121">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="f8ff4-121">EXAMPLES</span></span>

### <span data-ttu-id="f8ff4-122">Beispiel 1: Generieren einer Standard Transport Option</span><span class="sxs-lookup"><span data-stu-id="f8ff4-122">Example 1: Generate a default transport option</span></span>

```powershell
New-PSTransportOption
```

```Output
ProcessIdleTimeoutSec           :
MaxIdleTimeoutSec               :
MaxSessions                     :
MaxConcurrentCommandsPerSession :
MaxSessionsPerUser              :
MaxMemoryPerSessionMB           :
MaxProcessesPerSession          :
MaxConcurrentUsers              :
IdleTimeoutSec                  :
OutputBufferingMode             :
```

<span data-ttu-id="f8ff4-123">Dieser Befehl führt **New-pstransportoption** ohne Parameter aus.</span><span class="sxs-lookup"><span data-stu-id="f8ff4-123">This command runs the **New-PSTransportOption** without parameters.</span></span>
<span data-ttu-id="f8ff4-124">Die Ausgabe zeigt, dass das Cmdlet ein Transport Options Objekt generiert, das NULL-Werte für alle Eigenschaften hat.</span><span class="sxs-lookup"><span data-stu-id="f8ff4-124">The output shows that the cmdlet generates a transport option object that has null values for all properties.</span></span>

### <span data-ttu-id="f8ff4-125">Beispiel 2: Get-Sitzungs Konfigurationsoptionen</span><span class="sxs-lookup"><span data-stu-id="f8ff4-125">Example 2: Get session configuration options</span></span>

<span data-ttu-id="f8ff4-126">In diesem Beispiel wird gezeigt, wie ein Transport Options Objekt zum Festlegen von Sitzungs Konfigurationsoptionen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="f8ff4-126">This example shows how to use a transport options object to set session configuration options.</span></span>

```powershell
$t = New-PSTransportOption -MaxSessions 40
Register-PSSessionConfiguration -Name ITTasks -TransportOption $t
Get-PSSessionConfiguration -Name ITTasks | Format-List -Property *
```

```Output
Architecture                  : 64
Filename                      : %windir%\system32\pwrshplugin.dll
ResourceUri                   : http://schemas.microsoft.com/powershell/ITTasks
MaxConcurrentCommandsPerShell : 1000
UseSharedProcess              : false
ProcessIdleTimeoutSec         : 0
xmlns                         : http://schemas.microsoft.com/wbem/wsman/1/config/PluginConfiguration
MaxConcurrentUsers            : 5
lang                          : en-US
SupportsOptions               : true
ExactMatch                    : true
RunAsUser                     :
IdleTimeoutms                 : 7200000
PSVersion                     : 3.0
OutputBufferingMode           : Block
AutoRestart                   : false
MaxShells                     : 40
MaxMemoryPerShellMB           : 1024
MaxIdleTimeoutms              : 43200000
SDKVersion                    : 2
Name                          : ITTasks
XmlRenderingType              : text
Capability                    : {Shell}
RunAsPassword                 :
MaxProcessesPerShell          : 15
Enabled                       : True
MaxShellsPerUser              : 25
Permission                    :
```

<span data-ttu-id="f8ff4-127">Der erste Befehl verwendet das **New-PSTransportOption**-Cmdlet, um ein Transportoptionsobjekt zu erstellen, das in der $t-Variablen gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="f8ff4-127">The first command uses the **New-PSTransportOption** cmdlet to create a transport options object, which it saves in the $t variable.</span></span> <span data-ttu-id="f8ff4-128">Der Befehl verwendet den *MaxSessions*-Parameter, um die maximale Anzahl von Sitzungen auf 40 zu erhöhen.</span><span class="sxs-lookup"><span data-stu-id="f8ff4-128">The command uses the *MaxSessions* parameter to increase the maximum number of sessions to 40.</span></span>

<span data-ttu-id="f8ff4-129">Der zweite Befehl verwendet das **Register-PSSessionConfiguration**-Cmdlet, um die ITTasks-Sitzungskonfiguration zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="f8ff4-129">The second command uses the **Register-PSSessionConfiguration** cmdlet create the ITTasks session configuration.</span></span> <span data-ttu-id="f8ff4-130">Der Befehl verwendet den  *TransportOption*-Parameter, um das Transportoptionsobjekt in der $t-Variablen anzugeben.</span><span class="sxs-lookup"><span data-stu-id="f8ff4-130">The command uses the *TransportOption* parameter to specify the transport options object in the $t variable.</span></span>

<span data-ttu-id="f8ff4-131">Der dritte Befehl verwendet das Cmdlet "Get-PSSessionConfiguration", um die ittasks-Sitzungs Konfigurationen zu erhalten, und das Format-List-Cmdlet, um alle Eigenschaften des Sitzungs Konfigurations Objekts in einer Liste anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="f8ff4-131">The third command uses the Get-PSSessionConfiguration cmdlet to get the ITTasks session configurations and the Format-List cmdlet to display all of the properties of the session configuration object in a list.</span></span> <span data-ttu-id="f8ff4-132">Die Ausgabe zeigt, dass der Wert der **MaxShells**-Eigenschaft der Sitzungskonfiguration 40 ist.</span><span class="sxs-lookup"><span data-stu-id="f8ff4-132">The output shows that the value of the **MaxShells** property of the session configuration is 40.</span></span>

### <span data-ttu-id="f8ff4-133">Beispiel 3: Festlegen einer Transport Option</span><span class="sxs-lookup"><span data-stu-id="f8ff4-133">Example 3: Setting a transport option</span></span>

<span data-ttu-id="f8ff4-134">Dieser Befehl zeigt, wie sich die Einstellung einer Transportoption in einer Sitzungskonfiguration auf Sitzungen auswirkt, die die Sitzungskonfiguration verwenden.</span><span class="sxs-lookup"><span data-stu-id="f8ff4-134">This command shows the effect of setting a transport option in a session configuration on the sessions that use the session configuration.</span></span>

```powershell
$t = New-PSTransportOption -IdleTimeoutSec 3600
Set-PSSessionConfiguration -Name ITTasks -TransportOption $t
$s = New-PSSession -Name MyITTasks -ConfigurationName ITTasks
$s | Format-List -Property *
```

```Output
State                  : Opened
IdleTimeout            : 3600000
OutputBufferingMode    : Block
ComputerName           : localhost
ConfigurationName      : ITTasks
InstanceId             : 4110c3f5-68ea-40fa-9bbf-04a433dbb02d
Id                     : 1
Name                   : MyITTasks
Availability           : Available
ApplicationPrivateData : {PSVersionTable}
Runspace               : System.Management.Automation.RemoteRunspace
```

<span data-ttu-id="f8ff4-135">Der erste Befehl verwendet das **New-PSTransportOption**-Cmdlet, um ein Transportoptionsobjekt zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="f8ff4-135">The first command uses the **New-PSTransportOption** cmdlet to create a transport option object.</span></span> <span data-ttu-id="f8ff4-136">Der Befehl verwendet den *IdleTimeoutSec*-Parameter zum Festlegen des **IdleTimeoutSec**-Eigenschaftswerts des Objekts auf eine Stunde (3.600 Sekunden).</span><span class="sxs-lookup"><span data-stu-id="f8ff4-136">The command uses the *IdleTimeoutSec* parameter to set the **IdleTimeoutSec** property value of the object to one hour (3600 seconds).</span></span> <span data-ttu-id="f8ff4-137">Der Befehl speichert das Transportoptionsobjekt in der $t-Variablen.</span><span class="sxs-lookup"><span data-stu-id="f8ff4-137">The command saves the transport objects object in the $t variable.</span></span>

<span data-ttu-id="f8ff4-138">Der zweite Befehl verwendet das Cmdlet "Set-PSSessionConfiguration", um die Transport Optionen der ittasks-Sitzungs Konfiguration zu ändern.</span><span class="sxs-lookup"><span data-stu-id="f8ff4-138">The second command uses the Set-PSSessionConfiguration cmdlet to change the transport options of the ITTasks session configuration.</span></span> <span data-ttu-id="f8ff4-139">Der Befehl verwendet den  *TransportOption*-Parameter, um das Transportoptionsobjekt in der $t-Variablen anzugeben.</span><span class="sxs-lookup"><span data-stu-id="f8ff4-139">The command uses the *TransportOption* parameter to specify the transport options object in the $t variable.</span></span>

<span data-ttu-id="f8ff4-140">Der dritte Befehl verwendet das Cmdlet "New-PSSession", um die myittasks-Sitzung auf dem lokalen Computer zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="f8ff4-140">The third command uses the New-PSSession cmdlet to create the MyITTasks session on the local computer.</span></span> <span data-ttu-id="f8ff4-141">Der Befehl verwendet die **ConfigurationName**-Eigenschaft, um die ITTasks-Sitzungskonfiguration anzugeben.</span><span class="sxs-lookup"><span data-stu-id="f8ff4-141">The command uses the **ConfigurationName** property to specify the ITTasks session configuration.</span></span> <span data-ttu-id="f8ff4-142">Der Befehl speichert die Sitzung in der $s Variable. Beachten Sie, dass der Befehl den *sessionoption* -Parameter von **New-PSSession** nicht verwendet, um eine benutzerdefinierte Leerlaufzeit Überschreitung für die Sitzung festzulegen.</span><span class="sxs-lookup"><span data-stu-id="f8ff4-142">The command saves the session in the $s variable.Notice that the command does not use the *SessionOption* parameter of **New-PSSession** to set a custom idle time-out for the session.</span></span> <span data-ttu-id="f8ff4-143">Wenn dies der Fall ist, hat der in der Sitzungs Option festgelegte Leerlauf Timeout Wert Vorrang vor dem in der Sitzungs Konfiguration festgelegten Leerlauf Timeout.</span><span class="sxs-lookup"><span data-stu-id="f8ff4-143">If it did, the idle time-out value set in the session option would take precedence over the idle time-out set in the session configuration.</span></span>

<span data-ttu-id="f8ff4-144">Der vierte Befehl verwendet das Cmdlet "Format-List", um alle Eigenschaften der Sitzung in der $s Variablen in einer Liste anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="f8ff4-144">The fourth command uses the Format-List cmdlet to display all properties of the session in the $s variable in a list.</span></span> <span data-ttu-id="f8ff4-145">Die Ausgabe zeigt, dass die Sitzung eine Leerlaufzeit von einer Stunde (360.000 Millisekunden) aufweist.</span><span class="sxs-lookup"><span data-stu-id="f8ff4-145">The output shows that the session has an idle time-out of one hour (360,000 milliseconds).</span></span>

## <span data-ttu-id="f8ff4-146">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="f8ff4-146">PARAMETERS</span></span>

### <span data-ttu-id="f8ff4-147">-Idletimeoutsec</span><span class="sxs-lookup"><span data-stu-id="f8ff4-147">-IdleTimeoutSec</span></span>

<span data-ttu-id="f8ff4-148">Bestimmt, wie lange die einzelnen Sitzungen geöffnet bleiben, wenn der Remote Computer keine Kommunikation vom lokalen Computer empfängt.</span><span class="sxs-lookup"><span data-stu-id="f8ff4-148">Determines how long each session stays open if the remote computer does not receive any communication from the local computer.</span></span>
<span data-ttu-id="f8ff4-149">Dies schließt das Taktsignal ein.</span><span class="sxs-lookup"><span data-stu-id="f8ff4-149">This includes the heartbeat signal.</span></span>
<span data-ttu-id="f8ff4-150">Wenn das Intervall abläuft, wird die Sitzung geschlossen.</span><span class="sxs-lookup"><span data-stu-id="f8ff4-150">When the interval expires, the session closes.</span></span>

<span data-ttu-id="f8ff4-151">Der Wert für das Leerlauf Timeout ist von großer Wichtigkeit, wenn der Benutzer die Verbindung zu einer Sitzung trennen und wiederherstellen möchte.</span><span class="sxs-lookup"><span data-stu-id="f8ff4-151">The idle time-out value is of significant importance when the user intends to disconnect and reconnect to a session.</span></span>
<span data-ttu-id="f8ff4-152">Der Benutzer kann die Verbindung nur wiederherstellen, wenn für die Sitzung keine Zeitüberschreitung eingetreten ist.</span><span class="sxs-lookup"><span data-stu-id="f8ff4-152">The user can reconnect only if the session has not timed out.</span></span>

<span data-ttu-id="f8ff4-153">Der *idletimeoutsec* -Parameter entspricht der **idletimeoutms** -Eigenschaft einer Sitzungs Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="f8ff4-153">The *IdleTimeoutSec* parameter corresponds to the **IdleTimeoutMs** property of a session configuration.</span></span>

<span data-ttu-id="f8ff4-154">Geben Sie einen Wert in Sekunden ein.</span><span class="sxs-lookup"><span data-stu-id="f8ff4-154">Enter a value in seconds.</span></span>
<span data-ttu-id="f8ff4-155">Der Standardwert beträgt 7.200 Sekunden (2 Stunden).</span><span class="sxs-lookup"><span data-stu-id="f8ff4-155">The default value is 7200 (2 hours).</span></span>
<span data-ttu-id="f8ff4-156">Der minimale Wert beträgt 60 Sekunden (1 Minute).</span><span class="sxs-lookup"><span data-stu-id="f8ff4-156">The minimum value is 60 (1 minute).</span></span>
<span data-ttu-id="f8ff4-157">Der Höchstwert ist der Wert der **IdleTimeout** -Eigenschaft von shellobjekten in der WSMAN-Konfiguration ( `WSMan:\\\<ComputerName\>\Shell\IdleTimeout` ).</span><span class="sxs-lookup"><span data-stu-id="f8ff4-157">The maximum is the value of the **IdleTimeout** property of Shell objects in the WSMan configuration (`WSMan:\\\<ComputerName\>\Shell\IdleTimeout`).</span></span>
<span data-ttu-id="f8ff4-158">Der Standardwert beträgt 7.200.000 Millisekunden (2 Stunden).</span><span class="sxs-lookup"><span data-stu-id="f8ff4-158">The default value is 7200000 milliseconds (2 hours).</span></span>

<span data-ttu-id="f8ff4-159">Wenn ein Leerlauf Timeout Wert in den Sitzungs Optionen und in der Sitzungs Konfiguration festgelegt ist, hat der in den Sitzungs Optionen festgelegte Wert Vorrang, aber er darf den Wert der **maxidletimeoutms** -Eigenschaft der Sitzungs Konfiguration nicht überschreiten.</span><span class="sxs-lookup"><span data-stu-id="f8ff4-159">If an idle time-out value is set in the session options and in the session configuration, value set in the session options takes precedence, but it cannot exceed the value of the **MaxIdleTimeoutMs** property of the session configuration.</span></span>
<span data-ttu-id="f8ff4-160">Um den Wert der **MaxIdleTimeoutMs**-Eigenschaft festzulegen, verwenden Sie den *MaxIdleTimeoutSec*-Parameter.</span><span class="sxs-lookup"><span data-stu-id="f8ff4-160">To set the value of the **MaxIdleTimeoutMs** property, use the *MaxIdleTimeoutSec* parameter.</span></span>

```yaml
Type: System.Nullable`1[System.Int32]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="f8ff4-161">-Maxconcurrentcommandspersession</span><span class="sxs-lookup"><span data-stu-id="f8ff4-161">-MaxConcurrentCommandsPerSession</span></span>

<span data-ttu-id="f8ff4-162">Beschränkt die Anzahl der Befehle, die in jeder Sitzung gleichzeitig ausgeführt werden können, auf den angegebenen Wert.</span><span class="sxs-lookup"><span data-stu-id="f8ff4-162">Limits the number of commands that can run at the same time in each session to the specified value.</span></span>
<span data-ttu-id="f8ff4-163">Der Standardwert lautet „1000“.</span><span class="sxs-lookup"><span data-stu-id="f8ff4-163">The default value is 1000.</span></span>

<span data-ttu-id="f8ff4-164">Der *maxconcurrentcommandspersession* -Parameter entspricht der **maxconcurrentcommandspershell** -Eigenschaft einer Sitzungs Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="f8ff4-164">The *MaxConcurrentCommandsPerSession* parameter corresponds to the **MaxConcurrentCommandsPerShell** property of a session configuration.</span></span>

```yaml
Type: System.Nullable`1[System.Int32]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="f8ff4-165">-Maxconcurrentusers</span><span class="sxs-lookup"><span data-stu-id="f8ff4-165">-MaxConcurrentUsers</span></span>

<span data-ttu-id="f8ff4-166">Beschränkt die Anzahl der Benutzer, die in jeder Sitzung Befehle gleichzeitig ausführen können, auf den angegebenen Wert.</span><span class="sxs-lookup"><span data-stu-id="f8ff4-166">Limits the number of users who can run commands at the same time in each session to the specified value.</span></span>
<span data-ttu-id="f8ff4-167">Der Standardwert ist 5.</span><span class="sxs-lookup"><span data-stu-id="f8ff4-167">The default value is 5.</span></span>

```yaml
Type: System.Nullable`1[System.Int32]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="f8ff4-168">-Maxidletimeoutsec</span><span class="sxs-lookup"><span data-stu-id="f8ff4-168">-MaxIdleTimeoutSec</span></span>

<span data-ttu-id="f8ff4-169">Schränkt die Leerlaufzeit Überschreitung für jede Sitzung auf den angegebenen Wert ein.</span><span class="sxs-lookup"><span data-stu-id="f8ff4-169">Limits the idle time-out set for each session to the specified value.</span></span>
<span data-ttu-id="f8ff4-170">Der Standardwert ist \[ int \] :: MaxValue (~ 25 Tage).</span><span class="sxs-lookup"><span data-stu-id="f8ff4-170">The default value is \[Int\]::MaxValue (~25 days).</span></span>

<span data-ttu-id="f8ff4-171">Der Wert für das Leerlauf Timeout ist von großer Wichtigkeit, wenn der Benutzer die Verbindung zu einer Sitzung trennen und wiederherstellen möchte.</span><span class="sxs-lookup"><span data-stu-id="f8ff4-171">The idle time-out value is of significant importance when the user intends to disconnect and reconnect to a session.</span></span>
<span data-ttu-id="f8ff4-172">Der Benutzer kann die Verbindung nur wiederherstellen, wenn für die Sitzung keine Zeitüberschreitung eingetreten ist.</span><span class="sxs-lookup"><span data-stu-id="f8ff4-172">The user can reconnect only if the session has not timed out.</span></span>

<span data-ttu-id="f8ff4-173">Der *maxidletimeoutsec* -Parameter entspricht der **maxidletimeoutms** -Eigenschaft einer Sitzungs Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="f8ff4-173">The *MaxIdleTimeoutSec* parameter corresponds to the **MaxIdleTimeoutMs** property of a session configuration.</span></span>

```yaml
Type: System.Nullable`1[System.Int32]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="f8ff4-174">-Maxmemorypersessionmb</span><span class="sxs-lookup"><span data-stu-id="f8ff4-174">-MaxMemoryPerSessionMB</span></span>

<span data-ttu-id="f8ff4-175">Beschränkt die Arbeitsspeichernutzung pro Sitzung auf den angegebenen Wert.</span><span class="sxs-lookup"><span data-stu-id="f8ff4-175">Limits the memory used by each session to the specified value.</span></span>
<span data-ttu-id="f8ff4-176">Geben Sie einen Wert in Megabytes ein.</span><span class="sxs-lookup"><span data-stu-id="f8ff4-176">Enter a value in megabytes.</span></span>
<span data-ttu-id="f8ff4-177">Der Standardwert ist 1.024 MB (1 GB).</span><span class="sxs-lookup"><span data-stu-id="f8ff4-177">The default value is 1024 megabytes (1 GB).</span></span>

<span data-ttu-id="f8ff4-178">Der *maxmemorypersessionmb* -Parameter entspricht der **maxmemorypershellmb** -Eigenschaft einer Sitzungs Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="f8ff4-178">The *MaxMemoryPerSessionMB* parameter corresponds to the **MaxMemoryPerShellMB** property of a session configuration.</span></span>

```yaml
Type: System.Nullable`1[System.Int32]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="f8ff4-179">-Maxprocessespersession</span><span class="sxs-lookup"><span data-stu-id="f8ff4-179">-MaxProcessesPerSession</span></span>

<span data-ttu-id="f8ff4-180">Beschränkt die Anzahl der Prozesse, die pro Sitzung ausgeführt werden, auf den angegebenen Wert.</span><span class="sxs-lookup"><span data-stu-id="f8ff4-180">Limits the number of processes running in each session to the specified value.</span></span>
<span data-ttu-id="f8ff4-181">Der Standardwert ist 15.</span><span class="sxs-lookup"><span data-stu-id="f8ff4-181">The default value is 15.</span></span>

<span data-ttu-id="f8ff4-182">Der *maxprocessespersession* -Parameter entspricht der **maxprocessespershell** -Eigenschaft einer Sitzungs Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="f8ff4-182">The *MaxProcessesPerSession* parameter corresponds to the **MaxProcessesPerShell** property of a session configuration.</span></span>

```yaml
Type: System.Nullable`1[System.Int32]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="f8ff4-183">-MaxSessions</span><span class="sxs-lookup"><span data-stu-id="f8ff4-183">-MaxSessions</span></span>

<span data-ttu-id="f8ff4-184">Beschränkt die Anzahl der Sitzungen, die die Sitzungskonfiguration verwenden.</span><span class="sxs-lookup"><span data-stu-id="f8ff4-184">Limits the number of sessions that use the session configuration.</span></span>
<span data-ttu-id="f8ff4-185">Der Standardwert ist 25.</span><span class="sxs-lookup"><span data-stu-id="f8ff4-185">The default value is 25.</span></span>

<span data-ttu-id="f8ff4-186">Der *MaxSessions*-Parameter entspricht der **MaxShells**-Eigenschaft einer Sitzungskonfiguration.</span><span class="sxs-lookup"><span data-stu-id="f8ff4-186">The *MaxSessions* parameter corresponds to the **MaxShells** property of a session configuration.</span></span>

```yaml
Type: System.Nullable`1[System.Int32]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="f8ff4-187">-Maxsessionsperuser</span><span class="sxs-lookup"><span data-stu-id="f8ff4-187">-MaxSessionsPerUser</span></span>

<span data-ttu-id="f8ff4-188">Beschränkt die Anzahl der Sitzungen, die die Sitzungskonfiguration verwenden und unter den Anmeldeinformationen eines bestimmten Benutzers ausgeführt werden, auf den angegebenen Wert.</span><span class="sxs-lookup"><span data-stu-id="f8ff4-188">Limits the number of sessions that use the session configuration and run with the credentials of a given user to the specified value.</span></span>
<span data-ttu-id="f8ff4-189">Der Standardwert ist 25.</span><span class="sxs-lookup"><span data-stu-id="f8ff4-189">The default value is 25.</span></span>

<span data-ttu-id="f8ff4-190">Wenn Sie diesen Wert angeben, sollten Sie Bedenken, dass viele Benutzer möglicherweise die Anmelde Informationen eines "Ausführen als"-Benutzers verwenden.</span><span class="sxs-lookup"><span data-stu-id="f8ff4-190">When you specify this value, consider that many users might be using the credentials of a run as user.</span></span>

<span data-ttu-id="f8ff4-191">Der *maxsessionsperuser* -Parameter entspricht der **maxshellsperuser** -Eigenschaft einer Sitzungs Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="f8ff4-191">The *MaxSessionsPerUser* parameter corresponds to the **MaxShellsPerUser** property of a session configuration.</span></span>

```yaml
Type: System.Nullable`1[System.Int32]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="f8ff4-192">-Outputbufferingmode</span><span class="sxs-lookup"><span data-stu-id="f8ff4-192">-OutputBufferingMode</span></span>

<span data-ttu-id="f8ff4-193">Bestimmt, wie die Befehlsausgabe in getrennten Sitzungen verwaltet wird, wenn sich der Ausgabepuffer füllt.</span><span class="sxs-lookup"><span data-stu-id="f8ff4-193">Determines how command output is managed in disconnected sessions when the output buffer becomes full.</span></span>
<span data-ttu-id="f8ff4-194">Zulässige Werte für diesen Parameter:</span><span class="sxs-lookup"><span data-stu-id="f8ff4-194">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="f8ff4-195">Blockierung.</span><span class="sxs-lookup"><span data-stu-id="f8ff4-195">Block.</span></span>
<span data-ttu-id="f8ff4-196">Wenn der Ausgabepuffer voll ist, wird die Ausführung unterbrochen, bis der Puffer leer ist.</span><span class="sxs-lookup"><span data-stu-id="f8ff4-196">When the output buffer is full, execution is suspended until the buffer is clear.</span></span>
- <span data-ttu-id="f8ff4-197">Ablage.</span><span class="sxs-lookup"><span data-stu-id="f8ff4-197">Drop.</span></span>
<span data-ttu-id="f8ff4-198">Wenn der Ausgabepuffer voll ist, wird die Ausführung fortgesetzt.</span><span class="sxs-lookup"><span data-stu-id="f8ff4-198">When the output buffer is full, execution continues.</span></span>
<span data-ttu-id="f8ff4-199">Sobald neue Ausgabedaten gespeichert werden, wird die älteste Ausgabe verworfen.</span><span class="sxs-lookup"><span data-stu-id="f8ff4-199">As new output is saved, the oldest output is discarded.</span></span>
- <span data-ttu-id="f8ff4-200">Keine</span><span class="sxs-lookup"><span data-stu-id="f8ff4-200">None.</span></span>
<span data-ttu-id="f8ff4-201">Es wurde kein Ausgabepufferungsmodus angegeben.</span><span class="sxs-lookup"><span data-stu-id="f8ff4-201">No output buffering mode is specified.</span></span>

<span data-ttu-id="f8ff4-202">Der Standardwert der **outputbufferingmode** -Eigenschaft von Sessions ist Block.</span><span class="sxs-lookup"><span data-stu-id="f8ff4-202">The default value of the **OutputBufferingMode** property of sessions is Block.</span></span>

```yaml
Type: System.Nullable`1[System.Management.Automation.Runspaces.OutputBufferingMode]
Parameter Sets: (All)
Aliases:
Accepted values: None, Drop, Block

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="f8ff4-203">-Processidletimeoutsec</span><span class="sxs-lookup"><span data-stu-id="f8ff4-203">-ProcessIdleTimeoutSec</span></span>

<span data-ttu-id="f8ff4-204">Schränkt den Timeout Wert für jeden Host Prozess auf den angegebenen Wert ein.</span><span class="sxs-lookup"><span data-stu-id="f8ff4-204">Limits the time-out for each host process to the specified value.</span></span>
<span data-ttu-id="f8ff4-205">Der Standardwert 0 (null) bedeutet, dass kein Timeout Wert für den Prozess vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="f8ff4-205">The default value, 0, means that there is no time-out value for the process.</span></span>

<span data-ttu-id="f8ff4-206">Andere Sitzungs Konfigurationen verfügen über prozessspezifische Timeout Werte.</span><span class="sxs-lookup"><span data-stu-id="f8ff4-206">Other session configurations have per-process time-out values.</span></span>
<span data-ttu-id="f8ff4-207">Die **Microsoft. PowerShell. Workflow** -Sitzungs Konfiguration verfügt z. b. über einen prozessspezifischen Timeout Wert von 28800 Sekunden (8 Stunden).</span><span class="sxs-lookup"><span data-stu-id="f8ff4-207">For example, the **Microsoft.PowerShell.Workflow** session configuration has a per-process time-out value of 28800 seconds (8 hours).</span></span>

```yaml
Type: System.Nullable`1[System.Int32]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="f8ff4-208">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="f8ff4-208">CommonParameters</span></span>

<span data-ttu-id="f8ff4-209">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="f8ff4-209">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="f8ff4-210">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="f8ff4-210">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="f8ff4-211">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="f8ff4-211">INPUTS</span></span>

### <span data-ttu-id="f8ff4-212">Keine</span><span class="sxs-lookup"><span data-stu-id="f8ff4-212">None</span></span>

<span data-ttu-id="f8ff4-213">Eingaben können nicht an dieses Cmdlet weitergereicht werden.</span><span class="sxs-lookup"><span data-stu-id="f8ff4-213">You cannot pipe input to this cmdlet.</span></span>

## <span data-ttu-id="f8ff4-214">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="f8ff4-214">OUTPUTS</span></span>

### <span data-ttu-id="f8ff4-215">Microsoft. PowerShell. Commands. wsmanconfigurationoption</span><span class="sxs-lookup"><span data-stu-id="f8ff4-215">Microsoft.PowerShell.Commands.WSManConfigurationOption</span></span>

## <span data-ttu-id="f8ff4-216">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="f8ff4-216">NOTES</span></span>

- <span data-ttu-id="f8ff4-217">Die Eigenschaften eines Sitzungskonfigurationsobjekts weichen hinsichtlich der für die Sitzungskonfiguration festgelegten Optionen sowie der Werte dieser Optionen ab.</span><span class="sxs-lookup"><span data-stu-id="f8ff4-217">The properties of a session configuration object vary with the options set for the session configuration and the values of those options.</span></span> <span data-ttu-id="f8ff4-218">Sitzungskonfigurationen, die eine Sitzungskonfigurationsdatei verwenden, haben außerdem zusätzliche Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="f8ff4-218">Also, session configurations that use a session configuration file have additional properties.</span></span>

## <span data-ttu-id="f8ff4-219">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="f8ff4-219">RELATED LINKS</span></span>

[<span data-ttu-id="f8ff4-220">New-PSSession</span><span class="sxs-lookup"><span data-stu-id="f8ff4-220">New-PSSession</span></span>](New-PSSession.md)

[<span data-ttu-id="f8ff4-221">New-PSSessionOption</span><span class="sxs-lookup"><span data-stu-id="f8ff4-221">New-PSSessionOption</span></span>](New-PSSessionOption.md)

[<span data-ttu-id="f8ff4-222">Register-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="f8ff4-222">Register-PSSessionConfiguration</span></span>](Register-PSSessionConfiguration.md)

[<span data-ttu-id="f8ff4-223">Set-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="f8ff4-223">Set-PSSessionConfiguration</span></span>](Set-PSSessionConfiguration.md)
