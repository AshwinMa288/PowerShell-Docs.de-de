---
ms.date: 06/05/2017
keywords: powershell,cmdlet
title: Verwalten von Windows PowerShell-Laufwerken
description: Ein PowerShell-Laufwerk ist ein Speicherort für Daten, auf den Sie wie auf ein Dateisystemlaufwerk in PowerShell zugreifen können. PowerShell enthält standardmäßig Anbieter, die das Dateisystem, die Registrierung, Zertifikatspeicher und andere unterstützen.
ms.openlocfilehash: e4e5347c3f3458f25cea31c8e5a499474985220a
ms.sourcegitcommit: 9080316e3ca4f11d83067b41351531672b667b7a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2020
ms.locfileid: "92500333"
---
# <a name="managing-windows-powershell-drives"></a><span data-ttu-id="15bd2-105">Verwalten von Windows PowerShell-Laufwerken</span><span class="sxs-lookup"><span data-stu-id="15bd2-105">Managing Windows PowerShell Drives</span></span>

<span data-ttu-id="15bd2-106">Ein *Windows PowerShell-Laufwerk* ist ein Speicherort für Daten, auf den Sie wie auf ein Dateisystemlaufwerk in Windows PowerShell zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="15bd2-106">A *Windows PowerShell drive* is a data store location that you can access like a file system drive in Windows PowerShell.</span></span> <span data-ttu-id="15bd2-107">Die Windows PowerShell-Anbieter erstellen einige Laufwerke für Sie, z. B. die Dateisystemlaufwerke (einschließlich C: und D:), die Registrierungslaufwerke (HKCU: und HKLM:) und das Zertifikatlaufwerk (Cert:). Sie können auch eigene Windows PowerShell-Laufwerke erstellen.</span><span class="sxs-lookup"><span data-stu-id="15bd2-107">The Windows PowerShell providers create some drives for you, such as the file system drives (including C: and D:), the registry drives (HKCU: and HKLM:), and the certificate drive (Cert:), and you can create your own Windows PowerShell drives.</span></span> <span data-ttu-id="15bd2-108">Diese Laufwerke sind sehr nützlich, aber nur in Windows PowerShell verfügbar.</span><span class="sxs-lookup"><span data-stu-id="15bd2-108">These drives are very useful, but they are available only within Windows PowerShell.</span></span> <span data-ttu-id="15bd2-109">Sie können darauf nicht mit anderen Windows-Tools, z. B. Datei-Explorer oder „Cmd.exe“, zugreifen.</span><span class="sxs-lookup"><span data-stu-id="15bd2-109">You cannot access them by using other Windows tools, such as File Explorer or Cmd.exe.</span></span>

<span data-ttu-id="15bd2-110">Windows PowerShell verwendet das Nomen **PSDrive** für Befehle, die mit Windows PowerShell-Laufwerken arbeiten.</span><span class="sxs-lookup"><span data-stu-id="15bd2-110">Windows PowerShell uses the noun, **PSDrive** , for commands that work with Windows PowerShell drives.</span></span> <span data-ttu-id="15bd2-111">Verwenden Sie zum Anzeigen einer Liste der Windows PowerShell-Laufwerke in Ihrer Windows PowerShell-Sitzung das Cmdlet **Get-PSDrive** .</span><span class="sxs-lookup"><span data-stu-id="15bd2-111">For a list of the Windows PowerShell drives in your Windows PowerShell session, use the **Get-PSDrive** cmdlet.</span></span>

```
PS> Get-PSDrive

Name       Provider      Root                                   CurrentLocation
----       --------      ----                                   ---------------
A          FileSystem    A:\
Alias      Alias
C          FileSystem    C:\                                 ...And Settings\me
cert       Certificate   \
D          FileSystem    D:\
Env        Environment
Function   Function
HKCU       Registry      HKEY_CURRENT_USER
HKLM       Registry      HKEY_LOCAL_MACHINE
Variable   Variable
```

<span data-ttu-id="15bd2-112">Die anzeigten Laufwerke hängen von den in Ihrem System vorhandenen Laufwerken ab. Die Liste sieht jedoch ähnlich wie die oben dargestellte Ausgabe des Befehls **Get-PSDrive** aus.</span><span class="sxs-lookup"><span data-stu-id="15bd2-112">Although the drives in the display vary with the drives on your system, the listing will look similar to the output of the **Get-PSDrive** command shown above.</span></span>

<span data-ttu-id="15bd2-113">Dateisystemlaufwerke sind eine Teilmenge der Windows PowerShell-Laufwerke.</span><span class="sxs-lookup"><span data-stu-id="15bd2-113">File system drives are a subset of the Windows PowerShell drives.</span></span> <span data-ttu-id="15bd2-114">Sie können die Dateisystemlaufwerke am Eintrag „FileSystem“ in der Spalte „Provider“ erkennen.</span><span class="sxs-lookup"><span data-stu-id="15bd2-114">You can identify the file system drives by the FileSystem entry in the Provider column.</span></span> <span data-ttu-id="15bd2-115">(Die Dateisystemlaufwerke in Windows PowerShell werden vom Windows PowerShell-Anbieter „FileSystem“ unterstützt.)</span><span class="sxs-lookup"><span data-stu-id="15bd2-115">(The file system drives in Windows PowerShell are supported by the Windows PowerShell FileSystem provider.)</span></span>

<span data-ttu-id="15bd2-116">Um die Syntax des Cmdlets **Get-PSDrive** anzuzeigen, geben Sie den Befehl **Get-Command** mit dem Parameter **Syntax** ein:</span><span class="sxs-lookup"><span data-stu-id="15bd2-116">To see the syntax of the **Get-PSDrive** cmdlet, type a **Get-Command** command with the **Syntax** parameter:</span></span>

```
PS> Get-Command -Name Get-PSDrive -Syntax

Get-PSDrive [[-Name] <String[]>] [-Scope <String>] [-PSProvider <String[]>] [-V
erbose] [-Debug] [-ErrorAction <ActionPreference>] [-ErrorVariable <String>] [-
OutVariable <String>] [-OutBuffer <Int32>]
```

<span data-ttu-id="15bd2-117">Mit dem Parameter **PSProvider** können Sie nur die Windows PowerShell-Laufwerke anzeigen lassen, die von einem bestimmten Anbieter unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="15bd2-117">The **PSProvider** parameter lets you display only the Windows PowerShell drives that are supported by a particular provider.</span></span> <span data-ttu-id="15bd2-118">Um beispielsweise nur die Windows PowerShell-Laufwerke anzuzeigen, die vom Windows PowerShell-Anbieter „FileSystem“ unterstützt werden, geben Sie den Befehl **Get-PSDrive** mit dem Parameter **PSProvider** und dem Wert **FileSystem** ein:</span><span class="sxs-lookup"><span data-stu-id="15bd2-118">For example, to display only the Windows PowerShell drives that are supported by the Windows PowerShell FileSystem provider, type a **Get-PSDrive** command with the **PSProvider** parameter and the **FileSystem** value:</span></span>

```
PS> Get-PSDrive -PSProvider FileSystem

Name       Provider      Root                                   CurrentLocation
----       --------      ----                                   ---------------
A          FileSystem    A:\
C          FileSystem    C:\                           ...nd Settings\PowerUser
D          FileSystem    D:\
```

<span data-ttu-id="15bd2-119">Um die Windows PowerShell-Laufwerke anzuzeigen, die Registrierungsstrukturen darstellen, verwenden Sie den Parameter **PSProvider** , damit nur die Windows PowerShell-Laufwerke angezeigt werden, die vom Windows PowerShell-Anbieter „Registry“ unterstützt werden:</span><span class="sxs-lookup"><span data-stu-id="15bd2-119">To view the Windows PowerShell drives that represent registry hives, use the **PSProvider** parameter to display only the Windows PowerShell drives that are supported by the Windows PowerShell Registry provider:</span></span>

```
PS> Get-PSDrive -PSProvider Registry

Name       Provider      Root                                   CurrentLocation
----       --------      ----                                   ---------------
HKCU       Registry      HKEY_CURRENT_USER
HKLM       Registry      HKEY_LOCAL_MACHINE
```

<span data-ttu-id="15bd2-120">Sie können auch die standardmäßigen „Location“-Cmdlets mit den Windows PowerShell-Laufwerken verwenden:</span><span class="sxs-lookup"><span data-stu-id="15bd2-120">You can also use the standard Location cmdlets with the Windows PowerShell drives:</span></span>

```
PS> Set-Location HKLM:\SOFTWARE
PS> Push-Location .\Microsoft
PS> Get-Location

Path
----
HKLM:\SOFTWARE\Microsoft
```

## <a name="adding-new-windows-powershell-drives-new-psdrive"></a><span data-ttu-id="15bd2-121">Hinzufügen neuer Windows PowerShell-Laufwerke (New-PSDrive)</span><span class="sxs-lookup"><span data-stu-id="15bd2-121">Adding New Windows PowerShell Drives (New-PSDrive)</span></span>

<span data-ttu-id="15bd2-122">Mit dem Befehl **New-PSDrive** können Sie eigene Windows PowerShell-Laufwerke hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="15bd2-122">You can add your own Windows PowerShell drives by using the **New-PSDrive** command.</span></span> <span data-ttu-id="15bd2-123">Um die Syntax des Befehls **New-PSDrive** abzurufen, geben Sie den Befehl **Get-Command** mit dem Parameter **Syntax** ein:</span><span class="sxs-lookup"><span data-stu-id="15bd2-123">To get the syntax for the **New-PSDrive** command, enter the **Get-Command** command with the **Syntax** parameter:</span></span>

```
PS> Get-Command -Name New-PSDrive -Syntax

New-PSDrive [-Name] <String> [-PSProvider] <String> [-Root] <String> [-Descript
ion <String>] [-Scope <String>] [-Credential <PSCredential>] [-Verbose] [-Debug
] [-ErrorAction <ActionPreference>] [-ErrorVariable <String>] [-OutVariable <St
ring>] [-OutBuffer <Int32>] [-WhatIf] [-Confirm]
```

<span data-ttu-id="15bd2-124">Um ein neues Windows PowerShell-Laufwerk zu erstellen, müssen Sie drei Parameter angeben:</span><span class="sxs-lookup"><span data-stu-id="15bd2-124">To create a new Windows PowerShell drive, you must supply three parameters:</span></span>

- <span data-ttu-id="15bd2-125">Einen Namen für das Laufwerk (Sie können einen beliebigen gültigen Windows PowerShell-Namen verwenden)</span><span class="sxs-lookup"><span data-stu-id="15bd2-125">A name for the drive (you can use any valid Windows PowerShell name)</span></span>

- <span data-ttu-id="15bd2-126">PSProvider (verwenden Sie „FileSystem“ für Dateisystemspeicherorte und „Registry“ für Registrierungsspeicherorte)</span><span class="sxs-lookup"><span data-stu-id="15bd2-126">The PSProvider (use "FileSystem" for file system locations and "Registry" for registry locations)</span></span>

- <span data-ttu-id="15bd2-127">Das Stammelement, d.h. den Pfad zum Stamm des neuen Laufwerks</span><span class="sxs-lookup"><span data-stu-id="15bd2-127">The root, that is, the path to the root of the new drive</span></span>

<span data-ttu-id="15bd2-128">Sie können beispielsweise ein Laufwerk namens „Office“ erstellen, das dem Ordner zugeordnet ist, der die Microsoft Office-Anwendungen auf Ihrem Computer enthält, z.B. **C:\\Programme\\Microsoft Office\\OFFICE11** .</span><span class="sxs-lookup"><span data-stu-id="15bd2-128">For example, you can create a drive named "Office" that is mapped to the folder that contains the Microsoft Office applications on your computer, such as **C:\\Program Files\\Microsoft Office\\OFFICE11** .</span></span> <span data-ttu-id="15bd2-129">Geben Sie zum Erstellen des Laufwerks den folgenden Befehl ein:</span><span class="sxs-lookup"><span data-stu-id="15bd2-129">To create the drive, type the following command:</span></span>

```
PS> New-PSDrive -Name Office -PSProvider FileSystem -Root "C:\Program Files\Microsoft Office\OFFICE11"

Name       Provider      Root                                   CurrentLocation
----       --------      ----                                   ---------------
Office     FileSystem    C:\Program Files\Microsoft Offic...
```

> [!NOTE]
> <span data-ttu-id="15bd2-130">Bei Pfaden wird im Allgemeinen Groß-/Kleinschreibung nicht beachtet.</span><span class="sxs-lookup"><span data-stu-id="15bd2-130">In general, paths are not case-sensitive.</span></span>

<span data-ttu-id="15bd2-131">Sie verweisen auf das neue Windows PowerShell-Laufwerk wie auf alle Windows PowerShell-Laufwerke – über den Namen gefolgt von einem Doppelpunkt ( **:** ).</span><span class="sxs-lookup"><span data-stu-id="15bd2-131">You refer to the new Windows PowerShell drive as you do all Windows PowerShell drives -- by its name followed by a colon ( **:** ).</span></span>

<span data-ttu-id="15bd2-132">Ein Windows PowerShell-Laufwerk kann viele Aufgaben einfacher machen.</span><span class="sxs-lookup"><span data-stu-id="15bd2-132">A Windows PowerShell drive can make many tasks much simpler.</span></span> <span data-ttu-id="15bd2-133">Beispielsweise haben einige der wichtigsten Schlüssel in der Windows-Registrierung äußerst lange Pfade, die den Zugriff darauf mühsam machen und schwer zu merken sind.</span><span class="sxs-lookup"><span data-stu-id="15bd2-133">For example, some of the most important keys in the Windows registry have extremely long paths, making them cumbersome to access and difficult to remember.</span></span> <span data-ttu-id="15bd2-134">Wichtige Konfigurationsinformationen befinden sich unter **HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion** .</span><span class="sxs-lookup"><span data-stu-id="15bd2-134">Critical configuration information resides under **HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion** .</span></span> <span data-ttu-id="15bd2-135">Zum Anzeigen und Ändern von Elementen im Registrierungsschlüssel „CurrentVersion“ können Sie ein Windows PowerShell-Laufwerk mit dem Stamm in diesem Schlüssel erstellen, indem Sie Folgendes eingeben:</span><span class="sxs-lookup"><span data-stu-id="15bd2-135">To view and change items in the CurrentVersion registry key, you can create a Windows PowerShell drive that is rooted in that key by typing:</span></span>

```
PS> New-PSDrive -Name cvkey -PSProvider Registry -Root HKLM\Software\Microsoft\Windows\CurrentVersion

Name       Provider      Root                                   CurrentLocation
----       --------      ----                                   ---------------
cvkey      Registry      HKLM\Software\Microsoft\Windows\...
```

<span data-ttu-id="15bd2-136">Sie können dann zum Laufwerk **cvkey:** auf dieselbe Weise wechseln, wie Sie zu jedem anderen Laufwerk wechseln:</span><span class="sxs-lookup"><span data-stu-id="15bd2-136">You can then change location to the **cvkey:** drive as you would any other drive:</span></span>

```
PS> cd cvkey:
```

<span data-ttu-id="15bd2-137">oder:</span><span class="sxs-lookup"><span data-stu-id="15bd2-137">or:</span></span>

```
PS> Set-Location cvkey: -PassThru

Path
----
cvkey:\
```

<span data-ttu-id="15bd2-138">Das Cmdlet „New-PsDrive“ fügt das neue Laufwerk nur für die aktuelle Windows PowerShell-Sitzung hinzu.</span><span class="sxs-lookup"><span data-stu-id="15bd2-138">The New-PsDrive cmdlet adds the new drive only to the current Windows PowerShell session.</span></span> <span data-ttu-id="15bd2-139">Wenn Sie das Windows PowerShell-Fenster schließen, geht das neue Laufwerk verloren.</span><span class="sxs-lookup"><span data-stu-id="15bd2-139">If you close the Windows PowerShell window, the new drive is lost.</span></span> <span data-ttu-id="15bd2-140">Wenn Sie ein Windows PowerShell-Laufwerk speichern möchten, verwenden Sie das Cmdlet „Export-Console“, um die aktuelle Windows PowerShell-Sitzung zu exportieren, und verwenden Sie dann den „PowerShell.exe“-Parameter **PSConsoleFile** , um sie zu importieren.</span><span class="sxs-lookup"><span data-stu-id="15bd2-140">To save a Windows PowerShell drive, use the Export-Console cmdlet to export the current Windows PowerShell session, and then use the PowerShell.exe **PSConsoleFile** parameter to import it.</span></span> <span data-ttu-id="15bd2-141">Sie können auch das neue Laufwerk Ihrem Windows PowerShell-Profil hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="15bd2-141">Or, add the new drive to your Windows PowerShell profile.</span></span>

## <a name="deleting-windows-powershell-drives-remove-psdrive"></a><span data-ttu-id="15bd2-142">Löschen von Windows PowerShell-Laufwerken (Remove-PSDrive)</span><span class="sxs-lookup"><span data-stu-id="15bd2-142">Deleting Windows PowerShell Drives (Remove-PSDrive)</span></span>

<span data-ttu-id="15bd2-143">Über das Cmdlet **Remove-PSDrive** können Sie Laufwerke aus Windows PowerShell löschen.</span><span class="sxs-lookup"><span data-stu-id="15bd2-143">You can delete drives from Windows PowerShell by using the **Remove-PSDrive** cmdlet.</span></span> <span data-ttu-id="15bd2-144">Das Cmdlet **Remove-PSDrive** ist einfach zu verwenden. Um ein bestimmtes Windows PowerShell-Laufwerk zu löschen, geben Sie lediglich den Namen des Windows PowerShell-Laufwerk ein.</span><span class="sxs-lookup"><span data-stu-id="15bd2-144">The **Remove-PSDrive** cmdlet is easy to use; to delete a specific Windows PowerShell drive, you just supply the Windows PowerShell drive name.</span></span>

<span data-ttu-id="15bd2-145">Wenn Sie beispielsweise das Windows PowerShell-Laufwerk **Office:** hinzugefügt haben, wie im Thema **New-PSDrive** gezeigt, können Sie es löschen, indem Sie Folgendes eingeben:</span><span class="sxs-lookup"><span data-stu-id="15bd2-145">For example, if you added the **Office:** Windows PowerShell drive, as shown in the **New-PSDrive** topic, you can delete it by typing:</span></span>

```powershell
Remove-PSDrive -Name Office
```

<span data-ttu-id="15bd2-146">Zum Löschen des Windows PowerShell-Laufwerks **cvkey:** , das ebenfalls im Thema **New-PSDrive** gezeigt wird, verwenden Sie den folgenden Befehl:</span><span class="sxs-lookup"><span data-stu-id="15bd2-146">To delete the **cvkey:** Windows PowerShell drive, also shown in the **New-PSDrive** topic, use the following command:</span></span>

```powershell
Remove-PSDrive -Name cvkey
```

<span data-ttu-id="15bd2-147">Das Löschen eines Windows PowerShell-Laufwerk ist einfach. Sie können es jedoch nur löschen, wenn Sie sich nicht auf dem Laufwerk befinden. Beispiel:</span><span class="sxs-lookup"><span data-stu-id="15bd2-147">It's easy to delete a Windows PowerShell drive, but you can't delete it while you are in the drive.</span></span> <span data-ttu-id="15bd2-148">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="15bd2-148">For example:</span></span>

```
PS> cd office:
PS Office:\> remove-psdrive -name office
Remove-PSDrive : Cannot remove drive 'Office' because it is in use.
At line:1 char:15
+ remove-psdrive  <<<< -name office
```

## <a name="adding-and-removing-drives-outside-windows-powershell"></a><span data-ttu-id="15bd2-149">Hinzufügen und Entfernen von Laufwerken außerhalb von Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="15bd2-149">Adding and Removing Drives Outside Windows PowerShell</span></span>

<span data-ttu-id="15bd2-150">Windows PowerShell erkennt Dateisystemlaufwerke, die in Windows hinzugefügt oder gelöscht werden, einschließlich Netzlaufwerken, die zugeordnet sind, USB-Laufwerken, die angeschlossen sind, und Laufwerken, die über den Befehl **net use** oder die Methoden **WScript.NetworkMapNetworkDrive** und **RemoveNetworkDrive** von einem WSH-Skript (Windows Script Host) gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="15bd2-150">Windows PowerShell detects file system drives that are added or removed in Windows, including network drives that are mapped, USB drives that are attached, and drives that are deleted by using either the **net use** command or the **WScript.NetworkMapNetworkDrive** and **RemoveNetworkDrive** methods from a Windows Script Host (WSH) script.</span></span>
