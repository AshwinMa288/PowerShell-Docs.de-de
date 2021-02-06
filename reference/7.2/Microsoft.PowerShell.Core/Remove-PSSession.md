---
external help file: System.Management.Automation.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/remove-pssession?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Remove-PSSession
ms.openlocfilehash: cd0e2b62464a4c34278d42b833a669c6c28e377f
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99596561"
---
# <span data-ttu-id="17f2d-102">Remove-PSSession</span><span class="sxs-lookup"><span data-stu-id="17f2d-102">Remove-PSSession</span></span>

## <span data-ttu-id="17f2d-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="17f2d-103">SYNOPSIS</span></span>
<span data-ttu-id="17f2d-104">Schließt mindestens eine PowerShell-Sitzung (pssessions).</span><span class="sxs-lookup"><span data-stu-id="17f2d-104">Closes one or more PowerShell sessions (PSSessions).</span></span>

## <span data-ttu-id="17f2d-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="17f2d-105">SYNTAX</span></span>

### <span data-ttu-id="17f2d-106">ID (Standard)</span><span class="sxs-lookup"><span data-stu-id="17f2d-106">Id (Default)</span></span>

```
Remove-PSSession [-Id] <Int32[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="17f2d-107">Sitzung</span><span class="sxs-lookup"><span data-stu-id="17f2d-107">Session</span></span>

```
Remove-PSSession [-Session] <PSSession[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="17f2d-108">ContainerId</span><span class="sxs-lookup"><span data-stu-id="17f2d-108">ContainerId</span></span>

```
Remove-PSSession -ContainerId <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="17f2d-109">VMId</span><span class="sxs-lookup"><span data-stu-id="17f2d-109">VMId</span></span>

```
Remove-PSSession -VMId <Guid[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="17f2d-110">VMName</span><span class="sxs-lookup"><span data-stu-id="17f2d-110">VMName</span></span>

```
Remove-PSSession -VMName <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="17f2d-111">InstanceId</span><span class="sxs-lookup"><span data-stu-id="17f2d-111">InstanceId</span></span>

```
Remove-PSSession -InstanceId <Guid[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="17f2d-112">Name</span><span class="sxs-lookup"><span data-stu-id="17f2d-112">Name</span></span>

```
Remove-PSSession -Name <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### <span data-ttu-id="17f2d-113">Computername</span><span class="sxs-lookup"><span data-stu-id="17f2d-113">ComputerName</span></span>

```
Remove-PSSession [-ComputerName] <String[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## <span data-ttu-id="17f2d-114">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="17f2d-114">DESCRIPTION</span></span>

<span data-ttu-id="17f2d-115">Das **Remove-PSSession-** Cmdlet schließt PowerShell-Sitzungen (**pssessions**) in der aktuellen Sitzung.</span><span class="sxs-lookup"><span data-stu-id="17f2d-115">The **Remove-PSSession** cmdlet closes PowerShell sessions (**PSSessions**) in the current session.</span></span>
<span data-ttu-id="17f2d-116">Es beendet alle Befehle, die in den **pssessions** ausgeführt werden, beendet die **PSSession** und gibt die Ressourcen frei, die von der **PSSession** verwendet wurden.</span><span class="sxs-lookup"><span data-stu-id="17f2d-116">It stops any commands that are running in the **PSSessions**, ends the **PSSession**, and releases the resources that the **PSSession** was using.</span></span>
<span data-ttu-id="17f2d-117">Wenn die **PSSession** mit einem Remote Computer verbunden ist, schließt dieses Cmdlet auch die Verbindung zwischen dem lokalen Computer und dem Remote Computer.</span><span class="sxs-lookup"><span data-stu-id="17f2d-117">If the **PSSession** is connected to a remote computer, this cmdlet also closes the connection between the local and remote computers.</span></span>

<span data-ttu-id="17f2d-118">Um eine **PSSession** zu entfernen, geben Sie *Name*, *Computer Name*, *ID* oder *InstanceId* der Sitzung ein.</span><span class="sxs-lookup"><span data-stu-id="17f2d-118">To remove a **PSSession**, enter the *Name*, *ComputerName*, *ID*, or *InstanceID* of the session.</span></span>

<span data-ttu-id="17f2d-119">Wenn Sie die *PSSession* in einer Variablen gespeichert haben, bleibt das Sitzungs Objekt in der Variablen, der Status der *PSSession* ist jedoch geschlossen.</span><span class="sxs-lookup"><span data-stu-id="17f2d-119">If you have saved the *PSSession* in a variable, the session object remains in the variable, but the state of the *PSSession* is Closed.</span></span>

## <span data-ttu-id="17f2d-120">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="17f2d-120">EXAMPLES</span></span>

### <span data-ttu-id="17f2d-121">Beispiel 1: Entfernen von Sitzungen mithilfe von IDs</span><span class="sxs-lookup"><span data-stu-id="17f2d-121">Example 1: Remove sessions by using IDs</span></span>

```powershell
Remove-PSSession -Id 1, 2
```

<span data-ttu-id="17f2d-122">Mit diesem Befehl werden die **pssessions** mit den IDs 1 und 2 entfernt.</span><span class="sxs-lookup"><span data-stu-id="17f2d-122">This command removes the **PSSessions** that have IDs 1 and 2.</span></span>

### <span data-ttu-id="17f2d-123">Beispiel 2: Entfernen aller Sitzungen in der aktuellen Sitzung</span><span class="sxs-lookup"><span data-stu-id="17f2d-123">Example 2: Remove all the sessions in the current session</span></span>

```powershell
Get-PSSession | Remove-PSSession
Remove-PSSession -Session (Get-PSSession)
$s = Get-PSSession
Remove-PSSession -Session $s
```

<span data-ttu-id="17f2d-124">Diese Befehle entfernen alle **pssessions** in der aktuellen Sitzung.</span><span class="sxs-lookup"><span data-stu-id="17f2d-124">These commands remove all of the **PSSessions** in the current session.</span></span>
<span data-ttu-id="17f2d-125">Obwohl die drei Befehlsformate anders aussehen, haben sie die gleiche Wirkung.</span><span class="sxs-lookup"><span data-stu-id="17f2d-125">Although the three command formats look different, they have the same effect.</span></span>

### <span data-ttu-id="17f2d-126">Beispiel 3: Schließen von Sitzungen mithilfe von Namen</span><span class="sxs-lookup"><span data-stu-id="17f2d-126">Example 3: Close sessions by using names</span></span>

```powershell
$r = Get-PSSession -ComputerName Serv*
$r | Remove-PSSession
```

<span data-ttu-id="17f2d-127">Diese Befehle schließen die **pssessions** , die mit Computern verbunden sind, deren Namen mit "Serv" beginnen.</span><span class="sxs-lookup"><span data-stu-id="17f2d-127">These commands close the **PSSessions** that are connected to computers that have names that begin with Serv.</span></span>

### <span data-ttu-id="17f2d-128">Beispiel 4: Schließen von Sitzungen, die mit einem Port verbunden sind</span><span class="sxs-lookup"><span data-stu-id="17f2d-128">Example 4: Close sessions connected to a port</span></span>

```powershell
Get-PSSession | where {$_.port -eq 90} | Remove-PSSession
```

<span data-ttu-id="17f2d-129">Dieser Befehl schließt die **pssessions** , die mit Port 90 verbunden sind.</span><span class="sxs-lookup"><span data-stu-id="17f2d-129">This command closes the **PSSessions** that are connected to port 90.</span></span>
<span data-ttu-id="17f2d-130">Sie können dieses Befehls Format verwenden, um **pssessions** nach anderen Eigenschaften als *Computer Name*, *Name*, *InstanceId* und *ID* zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="17f2d-130">You can use this command format to identify **PSSessions** by properties other than *ComputerName*, *Name*, *InstanceID*, and *ID*.</span></span>

### <span data-ttu-id="17f2d-131">Beispiel 5: Schließen einer Sitzung basierend auf der Instanz-ID</span><span class="sxs-lookup"><span data-stu-id="17f2d-131">Example 5: Close a session based on instance ID</span></span>

```powershell
Get-PSSession | Format-Table ComputerName, InstanceID  -AutoSize
```

```Output
ComputerName InstanceId
------------ ----------------
Server01     875d231b-2788-4f36-9f67-2e50d63bb82a
localhost    c065ffa0-02c4-406e-84a3-dacb0d677868
Server02     4699cdbc-61d5-4e0d-b916-84f82ebede1f
Server03     4e5a3245-4c63-43e4-88d0-a7798bfc2414
TX-TEST-01   fc4e9dfa-f246-452d-9fa3-1adbdd64ae85 PS C:\> Remove-PSSession -InstanceID fc4e9dfa-f246-452d-9fa3-1adbdd64ae85
```

<span data-ttu-id="17f2d-132">Diese Befehle zeigen, wie eine **PSSession** auf Grundlage Ihrer Instanz-ID oder **remoterunspaceid** geschlossen wird.</span><span class="sxs-lookup"><span data-stu-id="17f2d-132">These commands show how to close a **PSSession** based on its instance ID, or **RemoteRunspaceID**.</span></span>

<span data-ttu-id="17f2d-133">Der erste Befehl verwendet das **Get-PSSession** -Cmdlet, um die **pssessions** in der aktuellen Sitzung abzurufen.</span><span class="sxs-lookup"><span data-stu-id="17f2d-133">The first command uses the **Get-PSSession** cmdlet to get the **PSSessions** in the current session.</span></span>
<span data-ttu-id="17f2d-134">Er verwendet einen Pipeline Operator (|), um die **pssessions** an das Format-Table-Cmdlet zu senden, das die **Computername** -und **InstanceId-** Eigenschaften in einer Tabelle formatiert.</span><span class="sxs-lookup"><span data-stu-id="17f2d-134">It uses a pipeline operator (|) to send the **PSSessions** to the Format-Table cmdlet, which formats their **ComputerName** and **InstanceID** properties in a table.</span></span>
<span data-ttu-id="17f2d-135">Der *AutoSize* -Parameter komprimiert die Spalten für die Anzeige.</span><span class="sxs-lookup"><span data-stu-id="17f2d-135">The *AutoSize* parameter compresses the columns for display.</span></span>

<span data-ttu-id="17f2d-136">In der resultierenden Anzeige können Sie die zu schließende **PSSession** identifizieren und die *InstanceId* dieser **PSSession** kopieren und in den zweiten Befehl einfügen.</span><span class="sxs-lookup"><span data-stu-id="17f2d-136">From the resulting display, you can identify the **PSSession** to be closed, and copy and paste the *InstanceID* of that **PSSession** into the second command.</span></span>

<span data-ttu-id="17f2d-137">Der zweite Befehl verwendet das **Remove-PSSession-** Cmdlet, um die *PSSession* mit der angegebenen Instanz-ID zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="17f2d-137">The second command uses the **Remove-PSSession** cmdlet to remove the *PSSession* with the specified instance ID.</span></span>

### <span data-ttu-id="17f2d-138">Beispiel 6: Erstellen einer Funktion, die alle Sitzungen in der aktuellen Sitzung löscht</span><span class="sxs-lookup"><span data-stu-id="17f2d-138">Example 6: Create a function that deletes all sessions in the current session</span></span>

```powershell
Function EndPSS { Get-PSSession | Remove-PSSession }
```

<span data-ttu-id="17f2d-139">Diese Funktion löscht alle **pssessions** in der aktuellen Sitzung.</span><span class="sxs-lookup"><span data-stu-id="17f2d-139">This function deletes all of the **PSSessions** in the current session.</span></span>
<span data-ttu-id="17f2d-140">Nachdem Sie diese Funktion dem PowerShell-Profil hinzugefügt haben, geben Sie ein, um alle Sitzungen zu löschen `EndPSS` .</span><span class="sxs-lookup"><span data-stu-id="17f2d-140">After you add this function to your PowerShell profile, to delete all sessions, type `EndPSS`.</span></span>

## <span data-ttu-id="17f2d-141">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="17f2d-141">PARAMETERS</span></span>

### <span data-ttu-id="17f2d-142">-ComputerName</span><span class="sxs-lookup"><span data-stu-id="17f2d-142">-ComputerName</span></span>

<span data-ttu-id="17f2d-143">Gibt ein Array von Namen von Computern an.</span><span class="sxs-lookup"><span data-stu-id="17f2d-143">Specifies an array of names of computers.</span></span>
<span data-ttu-id="17f2d-144">Dieses Cmdlet schließt die **pssessions** , die mit den angegebenen Computern verbunden sind.</span><span class="sxs-lookup"><span data-stu-id="17f2d-144">This cmdlet closes the **PSSessions** that are connected to the specified computers.</span></span>
<span data-ttu-id="17f2d-145">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="17f2d-145">Wildcard characters are permitted.</span></span>

<span data-ttu-id="17f2d-146">Geben Sie den NetBIOS-Namen, eine IP-Adresse oder den vollqualifizierten Domänennamen mindestens eines Computers ein.</span><span class="sxs-lookup"><span data-stu-id="17f2d-146">Type the NetBIOS name, an IP address, or a fully qualified domain name of one or more remote computers.</span></span>
<span data-ttu-id="17f2d-147">Um den lokalen Computer anzugeben, geben Sie den Computernamen, "localhost" oder einen Punkt (.) ein.</span><span class="sxs-lookup"><span data-stu-id="17f2d-147">To specify the local computer, type the computer name, localhost, or a dot (.).</span></span>

```yaml
Type: System.String[]
Parameter Sets: ComputerName
Aliases: Cn

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="17f2d-148">-Containerid</span><span class="sxs-lookup"><span data-stu-id="17f2d-148">-ContainerId</span></span>

<span data-ttu-id="17f2d-149">Gibt ein Array von IDs von Containern an.</span><span class="sxs-lookup"><span data-stu-id="17f2d-149">Specifies an array of IDs of containers.</span></span> <span data-ttu-id="17f2d-150">Mit diesem Cmdlet werden Sitzungen für jeden der angegebenen Container entfernt.</span><span class="sxs-lookup"><span data-stu-id="17f2d-150">This cmdlet removes sessions for each of the specified containers.</span></span> <span data-ttu-id="17f2d-151">Verwenden Sie den `docker ps` Befehl, um eine Liste der Container-IDs abzurufen.</span><span class="sxs-lookup"><span data-stu-id="17f2d-151">Use the `docker ps` command to get a list of container IDs.</span></span> <span data-ttu-id="17f2d-152">Weitere Informationen finden Sie in der Hilfe zum [docker PS](https://docs.docker.com/engine/reference/commandline/ps/) -Befehl.</span><span class="sxs-lookup"><span data-stu-id="17f2d-152">For more information, see the help for the [docker ps](https://docs.docker.com/engine/reference/commandline/ps/) command.</span></span>

```yaml
Type: System.String[]
Parameter Sets: ContainerId
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="17f2d-153">-Id</span><span class="sxs-lookup"><span data-stu-id="17f2d-153">-Id</span></span>

<span data-ttu-id="17f2d-154">Gibt ein Array von IDs von Sitzungen an.</span><span class="sxs-lookup"><span data-stu-id="17f2d-154">Specifies an array of IDs of sessions.</span></span>
<span data-ttu-id="17f2d-155">Dieses Cmdlet schließt die *pssessions* mit den angegebenen IDs.</span><span class="sxs-lookup"><span data-stu-id="17f2d-155">This cmdlet closes the *PSSessions* with the specified IDs.</span></span>
<span data-ttu-id="17f2d-156">Geben Sie eine oder mehrere IDs ein, die durch Kommas getrennt sind, oder verwenden Sie den Bereichs Operator (..), um einen Bereich von IDs anzugeben.</span><span class="sxs-lookup"><span data-stu-id="17f2d-156">Type one or more IDs, separated by commas, or use the range operator (..) to specify a range of IDs.</span></span>

<span data-ttu-id="17f2d-157">Eine ID ist eine Ganzzahl, die die **PSSession** in der aktuellen Sitzung eindeutig identifiziert.</span><span class="sxs-lookup"><span data-stu-id="17f2d-157">An ID is an integer that uniquely identifies the **PSSession** in the current session.</span></span>
<span data-ttu-id="17f2d-158">Es ist einfacher zu merken und einzugeben als die *InstanceId*, aber Sie ist nur in der aktuellen Sitzung eindeutig.</span><span class="sxs-lookup"><span data-stu-id="17f2d-158">It is easier to remember and type than the *InstanceId*, but it is unique only in the current session.</span></span>
<span data-ttu-id="17f2d-159">Um die ID einer **PSSession** zu ermitteln, führen Sie das Get-PSSession-Cmdlet ohne Parameter aus.</span><span class="sxs-lookup"><span data-stu-id="17f2d-159">To find the ID of a **PSSession**, run the Get-PSSession cmdlet without parameters.</span></span>

```yaml
Type: System.Int32[]
Parameter Sets: Id
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="17f2d-160">-InstanceId</span><span class="sxs-lookup"><span data-stu-id="17f2d-160">-InstanceId</span></span>

<span data-ttu-id="17f2d-161">Gibt ein Array von Instanz-IDs an.</span><span class="sxs-lookup"><span data-stu-id="17f2d-161">Specifies an array of instance IDs.</span></span>
<span data-ttu-id="17f2d-162">Dieses Cmdlet schließt die **pssessions** mit den angegebenen Instanz-IDs.</span><span class="sxs-lookup"><span data-stu-id="17f2d-162">This cmdlet closes the **PSSessions** that have the specified instance IDs.</span></span>

<span data-ttu-id="17f2d-163">Die Instanz-ID ist eine GUID, die eine **PSSession** in der aktuellen Sitzung eindeutig identifiziert.</span><span class="sxs-lookup"><span data-stu-id="17f2d-163">The instance ID is a GUID that uniquely identifies a **PSSession** in the current session.</span></span>
<span data-ttu-id="17f2d-164">Die Instanz-ID ist eindeutig, auch wenn mehrere Sitzungen auf einem einzelnen Computer ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="17f2d-164">The instance ID is unique, even when you have multiple sessions running on a single computer.</span></span>

<span data-ttu-id="17f2d-165">Die Instanz-ID wird in der **InstanceId-** Eigenschaft des Objekts gespeichert, das eine **PSSession** darstellt.</span><span class="sxs-lookup"><span data-stu-id="17f2d-165">The instance ID is stored in the **InstanceID** property of the object that represents a **PSSession**.</span></span>
<span data-ttu-id="17f2d-166">Um die **InstanceId** der **pssessions** in der aktuellen Sitzung zu suchen, geben Sie ein `Get-PSSession | Format-Table Name, ComputerName, InstanceId` .</span><span class="sxs-lookup"><span data-stu-id="17f2d-166">To find the **InstanceID** of the **PSSessions** in the current session, type `Get-PSSession | Format-Table Name, ComputerName, InstanceId`.</span></span>

```yaml
Type: System.Guid[]
Parameter Sets: InstanceId
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="17f2d-167">-Name</span><span class="sxs-lookup"><span data-stu-id="17f2d-167">-Name</span></span>

<span data-ttu-id="17f2d-168">Gibt ein Array von anzeigen Amen von Sitzungen an.</span><span class="sxs-lookup"><span data-stu-id="17f2d-168">Specifies an array of friendly names of sessions.</span></span>
<span data-ttu-id="17f2d-169">Dieses Cmdlet schließt die **pssessions** mit den angegebenen anzeigen Amen.</span><span class="sxs-lookup"><span data-stu-id="17f2d-169">This cmdlet closes the **PSSessions** that have the specified friendly names.</span></span>
<span data-ttu-id="17f2d-170">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="17f2d-170">Wildcard characters are permitted.</span></span>

<span data-ttu-id="17f2d-171">Da der Anzeige Name einer **PSSession** möglicherweise nicht eindeutig ist, sollten Sie bei Verwendung des *Name* -Parameters auch den *WhatIf* -Parameter oder den *Confirm* -Parameter im **Remove-PSSession-** Befehl verwenden.</span><span class="sxs-lookup"><span data-stu-id="17f2d-171">Because the friendly name of a **PSSession** might not be unique, when you use the *Name* parameter, consider also using the *WhatIf* or *Confirm* parameter in the **Remove-PSSession** command.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Name
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: True
```

### <span data-ttu-id="17f2d-172">-Sitzung</span><span class="sxs-lookup"><span data-stu-id="17f2d-172">-Session</span></span>

<span data-ttu-id="17f2d-173">Gibt die Sitzungs Objekte der zu schließenden **pssessions** an.</span><span class="sxs-lookup"><span data-stu-id="17f2d-173">Specifies the session objects of the **PSSessions** to close.</span></span>
<span data-ttu-id="17f2d-174">Geben Sie eine Variable ein, die die **pssessions** oder einen Befehl enthält, der die **pssessions** erstellt oder abruft, z. b. einen New-PSSession-oder **Get-PSSession** -Befehl.</span><span class="sxs-lookup"><span data-stu-id="17f2d-174">Enter a variable that contains the **PSSessions** or a command that creates or gets the **PSSessions**, such as a New-PSSession or **Get-PSSession** command.</span></span>
<span data-ttu-id="17f2d-175">Sie können ein oder mehrere Sitzungs Objekte auch über die Pipeline an **Remove-PSSession** übergeben.</span><span class="sxs-lookup"><span data-stu-id="17f2d-175">You can also pipe one or more session objects to **Remove-PSSession**.</span></span>

```yaml
Type: System.Management.Automation.Runspaces.PSSession[]
Parameter Sets: Session
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="17f2d-176">-VMID</span><span class="sxs-lookup"><span data-stu-id="17f2d-176">-VMId</span></span>

<span data-ttu-id="17f2d-177">Gibt ein Array mit der ID der virtuellen Computer an.</span><span class="sxs-lookup"><span data-stu-id="17f2d-177">Specifies an array of ID of virtual machines.</span></span>
<span data-ttu-id="17f2d-178">Dieses Cmdlet startet eine interaktive Sitzung mit jedem der angegebenen virtuellen Computer.</span><span class="sxs-lookup"><span data-stu-id="17f2d-178">This cmdlet starts an interactive session with each of the specified virtual machines.</span></span>
<span data-ttu-id="17f2d-179">Verwenden Sie den folgenden Befehl, um die verfügbaren virtuellen Computer anzuzeigen:</span><span class="sxs-lookup"><span data-stu-id="17f2d-179">To see the virtual machines that are available to you, use the following command:</span></span>

`Get-VM | Select-Object -Property Name, ID`

```yaml
Type: System.Guid[]
Parameter Sets: VMId
Aliases: VMGuid

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="17f2d-180">-VMName</span><span class="sxs-lookup"><span data-stu-id="17f2d-180">-VMName</span></span>

<span data-ttu-id="17f2d-181">Gibt ein Array von Namen von virtuellen Computern an.</span><span class="sxs-lookup"><span data-stu-id="17f2d-181">Specifies an array of names of virtual machines.</span></span>
<span data-ttu-id="17f2d-182">Dieses Cmdlet startet eine interaktive Sitzung mit jedem der angegebenen virtuellen Computer.</span><span class="sxs-lookup"><span data-stu-id="17f2d-182">This cmdlet starts an interactive session with each of the specified virtual machines.</span></span>
<span data-ttu-id="17f2d-183">Verwenden Sie das Cmdlet **Get-VM** , um die für Sie verfügbaren virtuellen Computer anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="17f2d-183">To see the virtual machines that are available to you, use the **Get-VM** cmdlet.</span></span>

```yaml
Type: System.String[]
Parameter Sets: VMName
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="17f2d-184">-Confirm</span><span class="sxs-lookup"><span data-stu-id="17f2d-184">-Confirm</span></span>

<span data-ttu-id="17f2d-185">Hiermit werden Sie vor der Ausführung des Cmdlets zur Bestätigung aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="17f2d-185">Prompts you for confirmation before running the cmdlet.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="17f2d-186">-WhatIf</span><span class="sxs-lookup"><span data-stu-id="17f2d-186">-WhatIf</span></span>

<span data-ttu-id="17f2d-187">Zeigt, was geschieht, wenn das Cmdlet ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="17f2d-187">Shows what would happen if the cmdlet runs.</span></span>
<span data-ttu-id="17f2d-188">Das Cmdlet wird nicht ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="17f2d-188">The cmdlet is not run.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="17f2d-189">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="17f2d-189">CommonParameters</span></span>

<span data-ttu-id="17f2d-190">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="17f2d-190">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="17f2d-191">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="17f2d-191">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="17f2d-192">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="17f2d-192">INPUTS</span></span>

### <span data-ttu-id="17f2d-193">System. Management. Automation. Runspaces. PSSession</span><span class="sxs-lookup"><span data-stu-id="17f2d-193">System.Management.Automation.Runspaces.PSSession</span></span>

<span data-ttu-id="17f2d-194">Sie können ein Sitzungs Objekt über die Pipeline an dieses Cmdlet übergeben.</span><span class="sxs-lookup"><span data-stu-id="17f2d-194">You can pipe a session object to this cmdlet.</span></span>

## <span data-ttu-id="17f2d-195">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="17f2d-195">OUTPUTS</span></span>

### <span data-ttu-id="17f2d-196">Keine</span><span class="sxs-lookup"><span data-stu-id="17f2d-196">None</span></span>

<span data-ttu-id="17f2d-197">Dieses Cmdlet gibt keine Objekte zurück.</span><span class="sxs-lookup"><span data-stu-id="17f2d-197">This cmdlet does not return any objects.</span></span>

## <span data-ttu-id="17f2d-198">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="17f2d-198">NOTES</span></span>

* <span data-ttu-id="17f2d-199">Der *ID* -Parameter ist obligatorisch.</span><span class="sxs-lookup"><span data-stu-id="17f2d-199">The *Id* parameter is mandatory.</span></span> <span data-ttu-id="17f2d-200">Um alle **pssessions** in der aktuellen Sitzung zu löschen, geben Sie ein `Get-PSSession | Remove-PSSession` .</span><span class="sxs-lookup"><span data-stu-id="17f2d-200">To delete all the **PSSessions** in the current session, type `Get-PSSession | Remove-PSSession`.</span></span>
* <span data-ttu-id="17f2d-201">Eine **PSSession** verwendet eine permanente Verbindung mit einem Remote Computer.</span><span class="sxs-lookup"><span data-stu-id="17f2d-201">A **PSSession** uses a persistent connection to a remote computer.</span></span> <span data-ttu-id="17f2d-202">Erstellen Sie eine **PSSession** , um eine Reihe von Befehlen auszuführen, die Daten gemeinsam nutzen.</span><span class="sxs-lookup"><span data-stu-id="17f2d-202">Create a **PSSession** to run a series of commands that share data.</span></span> <span data-ttu-id="17f2d-203">Geben Sie Folgendes ein, um weitere Informationen zu erhalten: `Get-Help about_PSSessions`.</span><span class="sxs-lookup"><span data-stu-id="17f2d-203">For more information, type `Get-Help about_PSSessions`.</span></span>
* <span data-ttu-id="17f2d-204">**Pssessions** sind spezifisch für die aktuelle Sitzung.</span><span class="sxs-lookup"><span data-stu-id="17f2d-204">**PSSessions** are specific to the current session.</span></span> <span data-ttu-id="17f2d-205">Wenn Sie eine Sitzung beenden, werden die **pssessions** , die Sie in dieser Sitzung erstellt haben, zwangsweise geschlossen.</span><span class="sxs-lookup"><span data-stu-id="17f2d-205">When you end a session, the **PSSessions** that you created in that session are forcibly closed.</span></span>

## <span data-ttu-id="17f2d-206">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="17f2d-206">RELATED LINKS</span></span>

[<span data-ttu-id="17f2d-207">Connect-PSSession</span><span class="sxs-lookup"><span data-stu-id="17f2d-207">Connect-PSSession</span></span>](Connect-PSSession.md)

[<span data-ttu-id="17f2d-208">Disconnect-PSSession</span><span class="sxs-lookup"><span data-stu-id="17f2d-208">Disconnect-PSSession</span></span>](Disconnect-PSSession.md)

[<span data-ttu-id="17f2d-209">Enter-PSSession</span><span class="sxs-lookup"><span data-stu-id="17f2d-209">Enter-PSSession</span></span>](Enter-PSSession.md)

[<span data-ttu-id="17f2d-210">Exit-PSSession</span><span class="sxs-lookup"><span data-stu-id="17f2d-210">Exit-PSSession</span></span>](Exit-PSSession.md)

[<span data-ttu-id="17f2d-211">Get-PSSession</span><span class="sxs-lookup"><span data-stu-id="17f2d-211">Get-PSSession</span></span>](Get-PSSession.md)

[<span data-ttu-id="17f2d-212">Invoke-Command</span><span class="sxs-lookup"><span data-stu-id="17f2d-212">Invoke-Command</span></span>](Invoke-Command.md)

[<span data-ttu-id="17f2d-213">New-PSSession</span><span class="sxs-lookup"><span data-stu-id="17f2d-213">New-PSSession</span></span>](New-PSSession.md)

[<span data-ttu-id="17f2d-214">Receive-PSSession</span><span class="sxs-lookup"><span data-stu-id="17f2d-214">Receive-PSSession</span></span>](Receive-PSSession.md)

[<span data-ttu-id="17f2d-215">about_PSSessions</span><span class="sxs-lookup"><span data-stu-id="17f2d-215">about_PSSessions</span></span>](About/about_PSSessions.md)

[<span data-ttu-id="17f2d-216">about_Remote</span><span class="sxs-lookup"><span data-stu-id="17f2d-216">about_Remote</span></span>](About/about_Remote.md)
