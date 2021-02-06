---
external help file: System.Management.Automation.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/save-help?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Save-Help
ms.openlocfilehash: 6996decc6b2f8b99ab9c04d96c487c37f2609c9e
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99597363"
---
# <span data-ttu-id="426b9-102">Save-Help</span><span class="sxs-lookup"><span data-stu-id="426b9-102">Save-Help</span></span>

## <span data-ttu-id="426b9-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="426b9-103">SYNOPSIS</span></span>
<span data-ttu-id="426b9-104">Lädt die neuesten Hilfedateien herunter und speichert sie in einem Dateisystemverzeichnis.</span><span class="sxs-lookup"><span data-stu-id="426b9-104">Downloads and saves the newest help files to a file system directory.</span></span>

## <span data-ttu-id="426b9-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="426b9-105">SYNTAX</span></span>

### <span data-ttu-id="426b9-106">Pfad (Standard)</span><span class="sxs-lookup"><span data-stu-id="426b9-106">Path (Default)</span></span>

```
Save-Help [-DestinationPath] <String[]> [[-Module] <PSModuleInfo[]>]
 [-FullyQualifiedModule <ModuleSpecification[]>] [[-UICulture] <CultureInfo[]>]
 [-Credential <PSCredential>] [-UseDefaultCredentials] [-Force] [-Scope <UpdateHelpScope>]
 [<CommonParameters>]
```

### <span data-ttu-id="426b9-107">LiteralPath</span><span class="sxs-lookup"><span data-stu-id="426b9-107">LiteralPath</span></span>

```
Save-Help -LiteralPath <String[]> [[-Module] <PSModuleInfo[]>]
 [-FullyQualifiedModule <ModuleSpecification[]>] [[-UICulture] <CultureInfo[]>]
 [-Credential <PSCredential>] [-UseDefaultCredentials] [-Force] [-Scope <UpdateHelpScope>]
 [<CommonParameters>]
```

## <span data-ttu-id="426b9-108">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="426b9-108">DESCRIPTION</span></span>

<span data-ttu-id="426b9-109">Das `Save-Help` Cmdlet lädt die neuesten Hilfedateien für PowerShell-Module herunter und speichert Sie in einem von Ihnen angegebenen Verzeichnis.</span><span class="sxs-lookup"><span data-stu-id="426b9-109">The `Save-Help` cmdlet downloads the newest help files for PowerShell modules and saves them to a directory that you specify.</span></span> <span data-ttu-id="426b9-110">Mit dieser Funktion können Sie die Hilfedateien auf Computern aktualisieren, die keinen Internetzugriff haben, und sie vereinfacht die Aktualisierung der Hilfedateien auf mehreren Computern.</span><span class="sxs-lookup"><span data-stu-id="426b9-110">This feature lets you update the help files on computers that do not have access to the Internet, and makes it easier to update the help files on multiple computers.</span></span>

<span data-ttu-id="426b9-111">In Windows PowerShell 3,0 `Save-Help` funktioniert nur für Module, die auf dem lokalen Computer installiert sind.</span><span class="sxs-lookup"><span data-stu-id="426b9-111">In Windows PowerShell 3.0, `Save-Help` worked only for modules that are installed on the local computer.</span></span> <span data-ttu-id="426b9-112">Obwohl es möglich war, ein Modul von einem Remote Computer zu importieren oder einen Verweis auf ein **psmoduleinfo** -Objekt von einem Remote Computer mithilfe von PowerShell-Remoting abzurufen, wurde die **helpinfouri** -Eigenschaft nicht beibehalten und `Save-Help` funktionierte nicht für die Remote Modul-Hilfe.</span><span class="sxs-lookup"><span data-stu-id="426b9-112">Although it was possible to import a module from a remote computer, or obtain a reference to a **PSModuleInfo** object from a remote computer by using PowerShell remoting, the **HelpInfoUri** property was not preserved, and `Save-Help` would not work for remote module Help.</span></span>

<span data-ttu-id="426b9-113">In Windows PowerShell 4,0 wird die **helpinfouri** -Eigenschaft über PowerShell-Remoting beibehalten, `Save-Help` sodass für Module verwendet werden kann, die auf Remote Computern installiert sind.</span><span class="sxs-lookup"><span data-stu-id="426b9-113">In Windows PowerShell 4.0, the **HelpInfoUri** property is preserved over PowerShell remoting, which enables `Save-Help` to work for modules that are installed on remote computers.</span></span> <span data-ttu-id="426b9-114">Es ist auch möglich, ein **psmoduleinfo** -Objekt auf einem Datenträger oder Wechselmedium zu speichern, indem `Export-Clixml` auf einem Computer ausgeführt wird, der nicht über Internet Zugriff verfügt, das Objekt auf einem Computer mit Internet Zugriff zu importieren und dann `Save-Help` auf dem **psmoduleinfo** -Objekt auszuführen.</span><span class="sxs-lookup"><span data-stu-id="426b9-114">It is also possible to save a **PSModuleInfo** object to disk or removable media by running `Export-Clixml` on a computer that does not have Internet access, import the object on a computer that does have Internet access, and then run `Save-Help` on the **PSModuleInfo** object.</span></span> <span data-ttu-id="426b9-115">Die gespeicherte Hilfe kann mithilfe von Wechselmedien (z. b. einem USB-Laufwerk) auf den Remote Computer übertragen werden.</span><span class="sxs-lookup"><span data-stu-id="426b9-115">The saved help can be transported to the remote computer by using removable storage media, such as a USB drive.</span></span> <span data-ttu-id="426b9-116">Die Hilfe kann durch Ausführen von auf dem Remote Computer installiert werden `Update-Help` .</span><span class="sxs-lookup"><span data-stu-id="426b9-116">The help can be installed on the remote computer by running `Update-Help`.</span></span> <span data-ttu-id="426b9-117">Dieser Prozess kann zum Installieren der Hilfe auf Computern verwendet werden, die überhaupt keinen Zugriff auf das Netzwerk haben.</span><span class="sxs-lookup"><span data-stu-id="426b9-117">This process can be used to install help on computers that do not have any kind of network access.</span></span>

<span data-ttu-id="426b9-118">Um die gespeicherten Hilfedateien zu installieren, führen Sie das- `Update-Help` Cmdlet aus.</span><span class="sxs-lookup"><span data-stu-id="426b9-118">To install saved help files, run the `Update-Help` cmdlet.</span></span> <span data-ttu-id="426b9-119">Fügen Sie seinen **SourcePath** -Parameter hinzu, um den Ordner anzugeben, in dem Sie die Hilfedateien gespeichert haben.</span><span class="sxs-lookup"><span data-stu-id="426b9-119">Add its **SourcePath** parameter to specify the folder in which you saved the Help files.</span></span>

<span data-ttu-id="426b9-120">Ohne Parameter wird von einem `Save-Help` Befehl die neueste Hilfe für alle Module in der Sitzung und für Module, die auf dem Computer installiert sind, an einem in der **psmodulepath** -Umgebungsvariablen aufgeführten Speicherort heruntergeladen.</span><span class="sxs-lookup"><span data-stu-id="426b9-120">Without parameters, a `Save-Help` command downloads the newest help for all modules in the session and for modules that are installed on the computer in a location listed in the **PSModulePath** environment variable.</span></span> <span data-ttu-id="426b9-121">Diese Aktion überspringt Module, die eine aktualisierbare Hilfe ohne Warnung nicht unterstützen.</span><span class="sxs-lookup"><span data-stu-id="426b9-121">This action skips modules that do not support Updatable Help without warning.</span></span>

<span data-ttu-id="426b9-122">Das- `Save-Help` Cmdlet überprüft die Version der Hilfedateien im Zielordner.</span><span class="sxs-lookup"><span data-stu-id="426b9-122">The `Save-Help` cmdlet checks the version of any help files in the destination folder.</span></span> <span data-ttu-id="426b9-123">Wenn neuere Hilfedateien verfügbar sind, lädt dieses Cmdlet die neuesten Hilfedateien aus dem Internet herunter und speichert Sie anschließend im Ordner.</span><span class="sxs-lookup"><span data-stu-id="426b9-123">If newer help files are available, this cmdlet downloads the newest help files from the Internet, and then saves them in the folder.</span></span> <span data-ttu-id="426b9-124">Das- `Save-Help` Cmdlet funktioniert genauso wie das- `Update-Help` Cmdlet, mit dem Unterschied, dass es die heruntergeladenen CAB-Dateien (CAB-Dateien) speichert, anstatt die Hilfedateien aus den CAB-Dateien zu extrahieren und auf dem Computer zu installieren.</span><span class="sxs-lookup"><span data-stu-id="426b9-124">The `Save-Help` cmdlet works just like the `Update-Help` cmdlet, except that it saves the downloaded cabinet (.cab) files, instead of extracting the help files from the cabinet files and installing them on the computer.</span></span>

<span data-ttu-id="426b9-125">Die gespeicherte Hilfe für jedes Modul besteht aus einer Hilfe Informationsdatei (helpinfo XML) und einer CAB-Datei für die Hilfedateien jeder Benutzeroberflächen Kultur.</span><span class="sxs-lookup"><span data-stu-id="426b9-125">The saved help for each module consists of one help information (HelpInfo XML) file and one cabinet (.cab) file for the help files each UI culture.</span></span> <span data-ttu-id="426b9-126">Sie müssen die Hilfedateien nicht aus der CAB-Datei extrahieren.</span><span class="sxs-lookup"><span data-stu-id="426b9-126">You do not have to extract the help files from the cabinet file.</span></span> <span data-ttu-id="426b9-127">Das `Update-Help` Cmdlet extrahiert die Hilfedateien, überprüft den XML-Code auf Sicherheit und installiert dann die Hilfedateien und die Hilfe Informationsdatei in einem sprachspezifischen Unterordner des Modul Ordners.</span><span class="sxs-lookup"><span data-stu-id="426b9-127">The `Update-Help` cmdlet extracts the help files, validates the XML for safety, and then installs the help files and the help information file in a language-specific subfolder of the module folder.</span></span>

<span data-ttu-id="426b9-128">Um die Hilfedateien für Module im PowerShell-Installationsordner () zu speichern `$pshome\Modules` , starten Sie PowerShell mit der Option als Administrator ausführen.</span><span class="sxs-lookup"><span data-stu-id="426b9-128">To save the help files for modules in the PowerShell installation folder (`$pshome\Modules`), start PowerShell by using the Run as administrator option.</span></span> <span data-ttu-id="426b9-129">Sie müssen ein Mitglied der Gruppe „Administratoren“ auf dem Computer sein, um die Hilfedateien für diese Module herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="426b9-129">You must be a member of the Administrators group on the computer to download the help files for these modules.</span></span>

<span data-ttu-id="426b9-130">Dieses Cmdlet wurde in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="426b9-130">This cmdlet was introduced in Windows PowerShell 3.0.</span></span>

## <span data-ttu-id="426b9-131">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="426b9-131">EXAMPLES</span></span>

### <span data-ttu-id="426b9-132">Beispiel 1: Speichern der Hilfe für das dhcpserver-Modul</span><span class="sxs-lookup"><span data-stu-id="426b9-132">Example 1: Save the help for the DhcpServer module</span></span>

```powershell
# Option 1: Run Invoke-Command to get the PSModuleInfo object for the remote DHCP Server module,
# save the PSModuleInfo object in the variable $m, and then run Save-Help.

$m = Invoke-Command -ComputerName RemoteServer -ScriptBlock { Get-Module -Name DhcpServer -ListAvailable }
Save-Help -Module $m -DestinationPath "C:\SavedHelp"


# Option 2: Open a PSSession--targeted at the remote computer that is running the DhcpServer
# module--to get the PSModuleInfo object for the remote module, and then run Save-Help.

$s = New-PSSession -ComputerName "RemoteServer"
$m = Get-Module -PSSession $s -Name "DhcpServer" -ListAvailable
Save-Help -Module $m -DestinationPath "C:\SavedHelp"


# Option 3: Open a CIM session--targeted at the remote computer that is running the DhcpServer
# module--to get the PSModuleInfo object for the remote module, and then run Save-Help.

$c = New-CimSession -ComputerName "RemoteServer"
$m = Get-Module -CimSession $c -Name "DhcpServer" -ListAvailable
Save-Help -Module $m -DestinationPath "C:\SavedHelp"
```

<span data-ttu-id="426b9-133">Dieses Beispiel zeigt drei verschiedene Möglichkeiten, `Save-Help` um die Hilfe für das **DHCPServer** -Modul von einem Client Computer mit Internet Verbindung zu speichern, ohne das **DHCPServer** -Modul oder die DHCP-Server Rolle auf dem lokalen Computer zu installieren.</span><span class="sxs-lookup"><span data-stu-id="426b9-133">This example shows three different ways to use `Save-Help` to save the help for the **DhcpServer** module from an Internet-connected client computer, without installing the **DhcpServer** module or the DHCP Server role on the local computer.</span></span>

### <span data-ttu-id="426b9-134">Beispiel 2: Installieren der Hilfe für das dhcpserver-Modul</span><span class="sxs-lookup"><span data-stu-id="426b9-134">Example 2: Install help for the DhcpServer module</span></span>

```powershell
# First, run Export-CliXml to export the PSModuleInfo object to a shared folder or to removable media.

$m = Get-Module -Name "DhcpServer" -ListAvailable
Export-CliXml -Path "E:\UsbFlashDrive\DhcpModule.xml" -InputObject $m

# Next, transport the removable media to a computer that has Internet access, and then import the
# PSModuleInfo object with Import-CliXml. Run Save-Help to save the Help for the imported DhcpServer
# module PSModuleInfo object.

$deserialized_m = Import-CliXml "E:\UsbFlashDrive\DhcpModule.xml"
Save-Help -Module $deserialized_m -DestinationPath "E:\UsbFlashDrive\SavedHelp"

# Finally, transport the removable media back to the computer that does not have network access, and
# then install the help by running Update-Help.

Update-Help -Module DhcpServer -SourcePath "E:\UsbFlashDrive\SavedHelp"
```

<span data-ttu-id="426b9-135">In diesem Beispiel wird gezeigt, wie die Hilfe, die Sie in Beispiel 1 für das **DHCPServer** -Modul gespeichert haben, auf einem Computer installiert wird, der nicht über Internet Zugriff verfügt.</span><span class="sxs-lookup"><span data-stu-id="426b9-135">This example shows how to install help that you saved in Example 1 for the **DhcpServer** module on a computer that does not have Internet access.</span></span>

### <span data-ttu-id="426b9-136">Beispiel 3: Speichern der Hilfe für alle Module</span><span class="sxs-lookup"><span data-stu-id="426b9-136">Example 3: Save help for all modules</span></span>

```powershell
Save-Help -DestinationPath "\\Server01\FileShare01"
```

<span data-ttu-id="426b9-137">Mit diesem Befehl werden die neuesten Hilfedateien für alle Module in der Benutzeroberflächenkultur für Windows auf den lokalen Computer heruntergeladen.</span><span class="sxs-lookup"><span data-stu-id="426b9-137">This command downloads the newest help files for all modules in the UI culture set for Windows on the local computer.</span></span> <span data-ttu-id="426b9-138">Die Hilfedateien werden im Ordner gespeichert `\\Server01\Fileshare01` .</span><span class="sxs-lookup"><span data-stu-id="426b9-138">It saves the help files in the `\\Server01\Fileshare01` folder.</span></span>

### <span data-ttu-id="426b9-139">Beispiel 4: Speichern der Hilfe für ein Modul auf dem Computer</span><span class="sxs-lookup"><span data-stu-id="426b9-139">Example 4: Save help for a module on the computer</span></span>

```powershell
Save-Help -Module ServerManager -DestinationPath "\\Server01\FileShare01" -Credential Domain01/Admin01
```

<span data-ttu-id="426b9-140">Dieser Befehl lädt die neuesten Hilfedateien für das **Server Manager** -Modul herunter und speichert Sie anschließend im `\\Server01\Fileshare01` Ordner.</span><span class="sxs-lookup"><span data-stu-id="426b9-140">This command downloads the newest help files for the **ServerManager** module, and then saves them in the `\\Server01\Fileshare01` folder.</span></span>

<span data-ttu-id="426b9-141">Wenn ein Modul auf dem Computer installiert ist, können Sie den Namen des Moduls als Wert des **Module**-Parameters eingeben, auch wenn das Modul nicht in die aktuelle Sitzung importiert wird.</span><span class="sxs-lookup"><span data-stu-id="426b9-141">When a module is installed on the computer, you can type the module name as the value of the **Module** parameter, even if the module is not imported into the current session.</span></span>

<span data-ttu-id="426b9-142">Der Befehl verwendet den **Credential**-Parameter, um die Anmeldeinformationen eines Benutzers anzugeben, der über die Berechtigung zum Schreiben in der Dateifreigabe verfügt.</span><span class="sxs-lookup"><span data-stu-id="426b9-142">The command uses the **Credential** parameter to supply the credentials of a user who has permission to write to the file share.</span></span>

### <span data-ttu-id="426b9-143">Beispiel 5: Speichern der Hilfe für ein Modul auf einem anderen Computer</span><span class="sxs-lookup"><span data-stu-id="426b9-143">Example 5: Save help for a module on a different computer</span></span>

```powershell
Invoke-Command -ComputerName Server02 {Get-Module -Name CustomSQL -ListAvailable} | Save-Help -DestinationPath \\Server01\FileShare01 -Credential Domain01\Admin01
```

<span data-ttu-id="426b9-144">Mit diesen Befehlen werden die neuesten Hilfedateien für das **customsql** -Modul heruntergeladen und im `\\Server01\Fileshare01` Ordner gespeichert.</span><span class="sxs-lookup"><span data-stu-id="426b9-144">These commands download the newest help files for the **CustomSQL** module and save them in the `\\Server01\Fileshare01` folder.</span></span>

<span data-ttu-id="426b9-145">Da das **customsql** -Modul nicht auf dem Computer installiert ist, enthält die Sequenz einen `Invoke-Command` Befehl, mit dem das Modul Objekt für das customsql-Modul vom Server02-Computer abgerufen und dann das Modul Objekt an das `Save-Help` Cmdlet weitergeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="426b9-145">Because the **CustomSQL** module is not installed on the computer, the sequence includes an `Invoke-Command` command that gets the module object for the CustomSQL module from the Server02 computer and then pipes the module object to the `Save-Help` cmdlet.</span></span>

<span data-ttu-id="426b9-146">Wenn ein Modul nicht auf dem Computer installiert ist, `Save-Help` benötigt das Modul Objekt, das Informationen über den Speicherort der neuesten Hilfedateien enthält.</span><span class="sxs-lookup"><span data-stu-id="426b9-146">When a module is not installed on the computer, `Save-Help` needs the module object, which includes information about the location of the newest help files.</span></span>

### <span data-ttu-id="426b9-147">Beispiel 6: Speichern der Hilfe für ein Modul in mehreren Sprachen</span><span class="sxs-lookup"><span data-stu-id="426b9-147">Example 6: Save help for a module in multiple languages</span></span>

```powershell
Save-Help -Module Microsoft.PowerShell* -UICulture de-DE, en-US, fr-FR, ja-JP -DestinationPath "D:\Help"
```

<span data-ttu-id="426b9-148">Dieser Befehl speichert die Hilfe für die PowerShell-Kernmodule in vier verschiedenen Benutzeroberflächen Kulturen.</span><span class="sxs-lookup"><span data-stu-id="426b9-148">This command saves help for the PowerShell Core modules in four different UI cultures.</span></span> <span data-ttu-id="426b9-149">Die Sprachpakete für diese Gebiets Schemas müssen nicht auf dem Computer installiert werden.</span><span class="sxs-lookup"><span data-stu-id="426b9-149">The language packs for these locales do not have to be installed on the computer.</span></span>

<span data-ttu-id="426b9-150">`Save-Help` können Hilfedateien für Module in verschiedenen Benutzeroberflächen Kulturen nur herunterladen, wenn der Modul Besitzer die übersetzten Dateien im Internet verfügbar macht.</span><span class="sxs-lookup"><span data-stu-id="426b9-150">`Save-Help` can download help files for modules in different UI cultures only when the module owner makes the translated files available on the Internet.</span></span>

### <span data-ttu-id="426b9-151">Beispiel 7: Speichern Sie die Hilfe mehr als einmal täglich.</span><span class="sxs-lookup"><span data-stu-id="426b9-151">Example 7: Save help more than one time each day</span></span>

```powershell
Save-Help -Force -DestinationPath "\\Server3\AdminShare\Help"
```

<span data-ttu-id="426b9-152">Dieser Befehl speichert die Hilfe für alle Module, die auf dem Computer installiert sind.</span><span class="sxs-lookup"><span data-stu-id="426b9-152">This command saves help for all modules that are installed on the computer.</span></span> <span data-ttu-id="426b9-153">Der Befehl gibt den **Force** -Parameter an, um die Regel zu überschreiben, die verhindert, dass das `Save-Help` Cmdlet die Hilfe mehr als einmal in jedem 24-Stunden-Zeitraum herunterlädt.</span><span class="sxs-lookup"><span data-stu-id="426b9-153">The command specifies the **Force** parameter to override the rule that prevents the `Save-Help` cmdlet from downloading help more than once in each 24-hour period.</span></span>

<span data-ttu-id="426b9-154">Der **Force** -Parameter überschreibt auch die 1 GB-Einschränkung und umgeht die Versions Überprüfung.</span><span class="sxs-lookup"><span data-stu-id="426b9-154">The **Force** parameter also overrides the 1 GB restriction and circumvents version checking.</span></span>
<span data-ttu-id="426b9-155">Daher können Sie Dateien auch dann herunterladen, wenn die Version nicht höher als die Version im Zielordner ist.</span><span class="sxs-lookup"><span data-stu-id="426b9-155">Therefore, you can download files even if the version is not later than the version in the destination folder.</span></span>

<span data-ttu-id="426b9-156">Der Befehl verwendet das `Save-Help` Cmdlet zum herunterladen und Speichern der Hilfedateien in den angegebenen Ordner.</span><span class="sxs-lookup"><span data-stu-id="426b9-156">The command uses the `Save-Help` cmdlet to download and save the help files to the specified folder.</span></span>
<span data-ttu-id="426b9-157">Der **Force** -Parameter ist erforderlich, wenn Sie einen Befehl mehrmals täglich ausführen müssen `Save-Help` .</span><span class="sxs-lookup"><span data-stu-id="426b9-157">The **Force** parameter is required when you have to run a `Save-Help` command more than one time each day.</span></span>

## <span data-ttu-id="426b9-158">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="426b9-158">PARAMETERS</span></span>

### <span data-ttu-id="426b9-159">-Credential</span><span class="sxs-lookup"><span data-stu-id="426b9-159">-Credential</span></span>

<span data-ttu-id="426b9-160">Gibt Benutzer Anmelde Informationen an.</span><span class="sxs-lookup"><span data-stu-id="426b9-160">Specifies a user credential.</span></span> <span data-ttu-id="426b9-161">Dieses Cmdlet führt den Befehl mithilfe der Anmelde Informationen eines Benutzers aus, der über die Berechtigung zum Zugreifen auf den Dateisystem Speicherort verfügt, der durch den **DestinationPath** -Parameter angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="426b9-161">This cmdlet runs the command by using credentials of a user who has permission to access the file system location specified by the **DestinationPath** parameter.</span></span> <span data-ttu-id="426b9-162">Dieser Parameter ist nur gültig, wenn der **DestinationPath** -Parameter oder der **literalpath** -Parameter im Befehl verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="426b9-162">This parameter is valid only when the **DestinationPath** or **LiteralPath** parameter is used in the command.</span></span>

<span data-ttu-id="426b9-163">Mit diesem Parameter können Sie `Save-Help` Befehle ausführen, die den **DestinationPath** -Parameter auf Remote Computern verwenden.</span><span class="sxs-lookup"><span data-stu-id="426b9-163">This parameter enables you to run `Save-Help` commands that use the **DestinationPath** parameter on remote computers.</span></span> <span data-ttu-id="426b9-164">Durch die Angabe expliziter Anmelde Informationen können Sie den Befehl auf einem Remote Computer ausführen und auf eine Dateifreigabe auf einem dritten Computer zugreifen, ohne dass ein Zugriffs Verweigerungs Fehler aufgetreten ist oder die Verwendung der-Authentifizierung zum Delegieren von Anmelde Informationen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="426b9-164">By providing explicit credentials, you can run the command on a remote computer and access a file share on a third computer without encountering an access denied error or using CredSSP authentication to delegate credentials.</span></span>

<span data-ttu-id="426b9-165">Geben Sie einen Benutzernamen ein, z. b. **USER01** oder **Domain01\User01**, oder geben Sie ein **PSCredential** -Objekt ein, das vom `Get-Credential` Cmdlet generiert wurde.</span><span class="sxs-lookup"><span data-stu-id="426b9-165">Type a user name, such as **User01** or **Domain01\User01**, or enter a **PSCredential** object generated by the `Get-Credential` cmdlet.</span></span> <span data-ttu-id="426b9-166">Wenn Sie einen Benutzernamen eingeben, werden Sie zur Eingabe des Kennworts aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="426b9-166">If you type a user name, you're prompted to enter the password.</span></span>

<span data-ttu-id="426b9-167">Anmelde Informationen werden in einem [PSCredential](/dotnet/api/system.management.automation.pscredential) -Objekt gespeichert, und das Kennwort wird als [SecureString](/dotnet/api/system.security.securestring)gespeichert.</span><span class="sxs-lookup"><span data-stu-id="426b9-167">Credentials are stored in a [PSCredential](/dotnet/api/system.management.automation.pscredential) object and the password is stored as a [SecureString](/dotnet/api/system.security.securestring).</span></span>

> [!NOTE]
> <span data-ttu-id="426b9-168">Weitere Informationen zum Schutz von **SecureString** -Daten finden Sie unter [wie sicher ist SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span><span class="sxs-lookup"><span data-stu-id="426b9-168">For more information about **SecureString** data protection, see [How secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="426b9-169">-DestinationPath</span><span class="sxs-lookup"><span data-stu-id="426b9-169">-DestinationPath</span></span>

<span data-ttu-id="426b9-170">Gibt den Pfad des Ordners an, in dem die Hilfedateien gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="426b9-170">Specifies the path of the folder in which the help files are saved.</span></span> <span data-ttu-id="426b9-171">Geben Sie keinen Dateinamen und keine Dateierweiterung an.</span><span class="sxs-lookup"><span data-stu-id="426b9-171">Do not specify a file name or file name extension.</span></span>

```yaml
Type: System.String[]
Parameter Sets: Path
Aliases: Path

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="426b9-172">-Force</span><span class="sxs-lookup"><span data-stu-id="426b9-172">-Force</span></span>

<span data-ttu-id="426b9-173">Gibt an, dass dieses Cmdlet nicht die einmal pro Tag-Einschränkung befolgt, die Versions Überprüfung überspringt und Dateien herunterlädt, die den Grenzwert von 1 GB überschreiten.</span><span class="sxs-lookup"><span data-stu-id="426b9-173">Indicates that this cmdlet does not follow the once-per-day limitation, skips version checking, and downloads files that exceed the 1 GB limit.</span></span>

<span data-ttu-id="426b9-174">Ohne diesen Parameter ist nur ein `Save-Help` Befehl für jedes Modul innerhalb von 24 Stunden zulässig, Downloads sind auf 1 GB unkomprimierter Inhalte pro Modul beschränkt, und Hilfedateien für ein Modul werden nur installiert, wenn Sie neuer sind als die Dateien auf dem Computer.</span><span class="sxs-lookup"><span data-stu-id="426b9-174">Without this parameter, only one `Save-Help` command for each module is permitted in each 24-hour period, downloads are limited to 1 GB of uncompressed content per module, and help files for a module are installed only when they are newer than the files on the computer.</span></span>

<span data-ttu-id="426b9-175">Der Grenzwert von einmal täglich schützt die Server, die die Hilfedateien hosten, und ermöglicht es Ihnen, `Save-Help` Ihrem PowerShell-Profil einen Befehl hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="426b9-175">The once-per-day limit protects the servers that host the help files, and makes it practical for you to add a `Save-Help` command to your PowerShell profile.</span></span>

<span data-ttu-id="426b9-176">Um die Hilfe für ein Modul in mehreren Benutzeroberflächen Kulturen ohne den **Force** -Parameter zu speichern, schließen Sie alle Benutzeroberflächen Kulturen in denselben Befehl ein, z. b.: `Save-Help -Module PSScheduledJobs -UICulture en-US, fr-FR, pt-BR`</span><span class="sxs-lookup"><span data-stu-id="426b9-176">To save help for a module in multiple UI cultures without the **Force** parameter, include all UI cultures in the same command, such as: `Save-Help -Module PSScheduledJobs -UICulture en-US, fr-FR, pt-BR`</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="426b9-177">-Fullyqualifiedmodule</span><span class="sxs-lookup"><span data-stu-id="426b9-177">-FullyQualifiedModule</span></span>

<span data-ttu-id="426b9-178">Gibt Module an, deren Namen in Form von **modulespecification** -Objekten angegeben sind.</span><span class="sxs-lookup"><span data-stu-id="426b9-178">Specifies modules with names that are specified in the form of **ModuleSpecification** objects.</span></span> <span data-ttu-id="426b9-179">Weitere Informationen finden Sie im Abschnitt "Hinweise" des [modulespecification-Konstruktors (Hash Tabelle)](/dotnet/api/microsoft.powershell.commands.modulespecification.-ctor#Microsoft_PowerShell_Commands_ModuleSpecification__ctor_System_Collections_Hashtable_).</span><span class="sxs-lookup"><span data-stu-id="426b9-179">See the Remarks section of [ModuleSpecification Constructor (Hashtable)](/dotnet/api/microsoft.powershell.commands.modulespecification.-ctor#Microsoft_PowerShell_Commands_ModuleSpecification__ctor_System_Collections_Hashtable_).</span></span>

<span data-ttu-id="426b9-180">Der **fullyqualifiedmodule** -Parameter akzeptiert z. b. einen Modulnamen, der in einem der folgenden Formate angegeben ist:</span><span class="sxs-lookup"><span data-stu-id="426b9-180">For example, the **FullyQualifiedModule** parameter accepts a module name that is specified in either of these formats:</span></span>

- `@{ModuleName = "modulename"; ModuleVersion = "version_number"}`
- `@{ModuleName = "modulename"; ModuleVersion = "version_number"; Guid = "GUID"}`

<span data-ttu-id="426b9-181">**ModuleName** und **ModuleVersion** sind erforderlich, aber **Guid** ist optional.</span><span class="sxs-lookup"><span data-stu-id="426b9-181">**ModuleName** and **ModuleVersion** are required, but **Guid** is optional.</span></span> <span data-ttu-id="426b9-182">Sie können den **fullyqualifiedmodule** -Parameter nicht im selben Befehl wie einen **Modul** Parameter angeben.</span><span class="sxs-lookup"><span data-stu-id="426b9-182">You cannot specify the **FullyQualifiedModule** parameter in the same command as a **Module** parameter.</span></span> <span data-ttu-id="426b9-183">die beiden Parameter schließen sich gegenseitig aus.</span><span class="sxs-lookup"><span data-stu-id="426b9-183">the two parameters are mutually exclusive.</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.ModuleSpecification[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="426b9-184">-Literalpath</span><span class="sxs-lookup"><span data-stu-id="426b9-184">-LiteralPath</span></span>

<span data-ttu-id="426b9-185">Gibt den Pfad des Ziel Ordners an.</span><span class="sxs-lookup"><span data-stu-id="426b9-185">Specifies a path of the destination folder.</span></span> <span data-ttu-id="426b9-186">Im Gegensatz zum Wert des **DestinationPath** -Parameters wird der Wert des **literalpath** -Parameters genau so verwendet, wie er eingegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="426b9-186">Unlike the value of the **DestinationPath** parameter, the value of the **LiteralPath** parameter is used exactly as it is typed.</span></span> <span data-ttu-id="426b9-187">Es werden keine Zeichen als Platzhalter interpretiert.</span><span class="sxs-lookup"><span data-stu-id="426b9-187">No characters are interpreted as wildcard characters.</span></span> <span data-ttu-id="426b9-188">Wenn der Pfad Escapezeichen enthält, müssen Sie ihn in einfache Anführungszeichen einschließen.</span><span class="sxs-lookup"><span data-stu-id="426b9-188">If the path includes escape characters, enclose it in single quotation marks.</span></span> <span data-ttu-id="426b9-189">Einfache Anführungszeichen veranlassen PowerShell, Zeichen nicht als Escapesequenzen zu interpretieren.</span><span class="sxs-lookup"><span data-stu-id="426b9-189">Single quotation marks tell PowerShell not to interpret any characters as escape sequences.</span></span>

```yaml
Type: System.String[]
Parameter Sets: LiteralPath
Aliases: PSPath, LP

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="426b9-190">-Modul</span><span class="sxs-lookup"><span data-stu-id="426b9-190">-Module</span></span>

<span data-ttu-id="426b9-191">Gibt Module an, für die dieses Cmdlet die Hilfe herunterlädt.</span><span class="sxs-lookup"><span data-stu-id="426b9-191">Specifies modules for which this cmdlet downloads help.</span></span> <span data-ttu-id="426b9-192">Geben Sie mindestens einen Modulnamen oder ein Namensmuster in eine durch Trennzeichen getrennte Liste oder in eine Datei ein, die in jeder Zeile über einen Modulnamen verfügt.</span><span class="sxs-lookup"><span data-stu-id="426b9-192">Enter one or more module names or name patters in a comma-separated list or in a file that has one module name on each line.</span></span> <span data-ttu-id="426b9-193">Platzhalterzeichen sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="426b9-193">Wildcard characters are permitted.</span></span> <span data-ttu-id="426b9-194">Sie können Modul Objekte auch über die Pipeline aus dem `Get-Module` Cmdlet an übergeben `Save-Help` .</span><span class="sxs-lookup"><span data-stu-id="426b9-194">You can also pipe module objects from the `Get-Module` cmdlet to `Save-Help`.</span></span>

<span data-ttu-id="426b9-195">Standardmäßig `Save-Help` lädt die Hilfe für alle Module herunter, die die aktualisierbare Hilfe unterstützen und auf dem lokalen Computer an einem in der **psmodulepath** -Umgebungsvariablen aufgeführten Speicherort installiert sind.</span><span class="sxs-lookup"><span data-stu-id="426b9-195">By default, `Save-Help` downloads help for all modules that support Updatable Help and are installed on the local computer in a location listed in the **PSModulePath** environment variable.</span></span>

<span data-ttu-id="426b9-196">Um die Hilfe für Module zu speichern, die nicht auf dem Computer installiert sind, führen Sie einen `Get-Module` Befehl auf einem Remote Computer aus.</span><span class="sxs-lookup"><span data-stu-id="426b9-196">To save help for modules that are not installed on the computer, run a `Get-Module` command on a remote computer.</span></span> <span data-ttu-id="426b9-197">Übergeben Sie dann die resultierenden Modul Objekte an das `Save-Help` Cmdlet, oder übermitteln Sie die Modul Objekte als Wert der **Module** -oder **Inputobject** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="426b9-197">Then pipe the resulting module objects to the `Save-Help` cmdlet or submit the module objects as the value of the **Module** or **InputObject** parameters.</span></span>

<span data-ttu-id="426b9-198">Wenn das angegebene Modul auf dem Computer installiert ist, können Sie den Modulnamen oder ein Modulobjekt eingeben.</span><span class="sxs-lookup"><span data-stu-id="426b9-198">If the module that you specify is installed on the computer, you can enter the module name or a module object.</span></span> <span data-ttu-id="426b9-199">Wenn das Modul nicht auf dem Computer installiert ist, müssen Sie ein Modul Objekt eingeben, z. b. ein vom `Get-Module` Cmdlet zurück gegebenes.</span><span class="sxs-lookup"><span data-stu-id="426b9-199">If the module is not installed on the computer, you must enter a module object, such as one returned by the `Get-Module` cmdlet.</span></span>

<span data-ttu-id="426b9-200">Der **Modul** Parameter des `Save-Help` Cmdlets akzeptiert nicht den vollständigen Pfad einer Modul Datei oder Modul Manifest-Datei.</span><span class="sxs-lookup"><span data-stu-id="426b9-200">The **Module** parameter of the `Save-Help` cmdlet does not accept the full path of a module file or module manifest file.</span></span> <span data-ttu-id="426b9-201">Um die Hilfe für ein Modul zu speichern, das sich nicht an einem **psmodulepath** -Speicherort befindet, importieren Sie das Modul in die aktuelle Sitzung, bevor Sie den `Save-Help` Befehl ausführen.</span><span class="sxs-lookup"><span data-stu-id="426b9-201">To save help for a module that is not in a **PSModulePath** location, import the module into the current session before you run the `Save-Help` command.</span></span>

<span data-ttu-id="426b9-202">Der Wert "\*" (alle) versucht, die Hilfe für alle Module zu aktualisieren, die auf dem Computer installiert sind.</span><span class="sxs-lookup"><span data-stu-id="426b9-202">A value of "\*" (all) attempts to update help for all modules that are installed on the computer.</span></span>
<span data-ttu-id="426b9-203">Dies schließt Module ein, die die aktualisierbare Hilfe nicht unterstützen.</span><span class="sxs-lookup"><span data-stu-id="426b9-203">This includes modules that do not support Updatable Help.</span></span> <span data-ttu-id="426b9-204">Dieser Wert generiert möglicherweise Fehler, wenn der Befehl Module erkennt, die die aktualisierbare Hilfe nicht unterstützen.</span><span class="sxs-lookup"><span data-stu-id="426b9-204">This value might generate errors when the command encounters modules that do not support Updatable Help.</span></span>

```yaml
Type: System.Management.Automation.PSModuleInfo[]
Parameter Sets: (All)
Aliases: Name

Required: False
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName, ByValue)
Accept wildcard characters: True
```

### <span data-ttu-id="426b9-205">-UICulture</span><span class="sxs-lookup"><span data-stu-id="426b9-205">-UICulture</span></span>

<span data-ttu-id="426b9-206">Gibt Werte für die Benutzeroberflächen Kultur an, für die dieses Cmdlet aktualisierte Hilfedateien abruft.</span><span class="sxs-lookup"><span data-stu-id="426b9-206">Specifies UI culture values for which this cmdlet gets updated help files.</span></span> <span data-ttu-id="426b9-207">Geben Sie mindestens einen Sprachcode ein, z `es-ES` . b. eine Variable, die Kultur Objekte enthält, oder einen Befehl, der Kultur Objekte abruft, z. b. einen- `Get-Culture` oder- `Get-UICulture` Befehl.</span><span class="sxs-lookup"><span data-stu-id="426b9-207">Enter one or more language codes, such as `es-ES`, a variable that contains culture objects, or a command that gets culture objects, such as a `Get-Culture` or `Get-UICulture` command.</span></span>

<span data-ttu-id="426b9-208">Platzhalterzeichen sind nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="426b9-208">Wildcard characters are not permitted.</span></span> <span data-ttu-id="426b9-209">Geben Sie keinen partiellen Sprachcode, z. b. "de", an.</span><span class="sxs-lookup"><span data-stu-id="426b9-209">Do not specify a partial language code, such as "de".</span></span>

<span data-ttu-id="426b9-210">Standardmäßig ruft `Save-Help` Hilfedateien in der Benutzeroberflächen Kultur ab, die für Windows oder die zugehörige Fall backkultur festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="426b9-210">By default, `Save-Help` gets help files in the UI culture set for Windows or its fallback culture.</span></span>
<span data-ttu-id="426b9-211">Wenn Sie den **UICulture** -Parameter angeben, `Save-Help` sucht nur nach Hilfe für die angegebene Benutzeroberflächen Kultur, nicht in einer Fall backkultur.</span><span class="sxs-lookup"><span data-stu-id="426b9-211">If you specify the **UICulture** parameter, `Save-Help` looks for help only for the specified UI culture, not in any fallback culture.</span></span>

```yaml
Type: System.Globalization.CultureInfo[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 2
Default value: Current UI culture
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="426b9-212">-Usedefault-Anmelde Informationen</span><span class="sxs-lookup"><span data-stu-id="426b9-212">-UseDefaultCredentials</span></span>

<span data-ttu-id="426b9-213">Gibt an, dass dieses Cmdlet den Befehl, einschließlich des Webdownloads, mit den Anmelde Informationen des aktuellen Benutzers ausführt.</span><span class="sxs-lookup"><span data-stu-id="426b9-213">Indicates that this cmdlet runs the command, including the web download, with the credentials of the current user.</span></span> <span data-ttu-id="426b9-214">Standardmäßig wird der Befehl ohne explizite Anmeldeinformationen ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="426b9-214">By default, the command runs without explicit credentials.</span></span>

<span data-ttu-id="426b9-215">Dieser Parameter gilt nur, wenn der Webdownload eine NTLM-, Negotiate- oder Kerberos-basierte Authentifizierung verwendet.</span><span class="sxs-lookup"><span data-stu-id="426b9-215">This parameter is effective only when the web download uses NTLM, negotiate, or Kerberos-based authentication.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="426b9-216">-Bereich</span><span class="sxs-lookup"><span data-stu-id="426b9-216">-Scope</span></span>

<span data-ttu-id="426b9-217">Dieser Parameter führt in diesem Cmdlet keine Aktion aus.</span><span class="sxs-lookup"><span data-stu-id="426b9-217">This paramater does nothing in this cmdlet.</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.UpdateHelpScope
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### <span data-ttu-id="426b9-218">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="426b9-218">CommonParameters</span></span>

<span data-ttu-id="426b9-219">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="426b9-219">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="426b9-220">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="426b9-220">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="426b9-221">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="426b9-221">INPUTS</span></span>

### <span data-ttu-id="426b9-222">System. Management. Automation. psmoduleinfo</span><span class="sxs-lookup"><span data-stu-id="426b9-222">System.Management.Automation.PSModuleInfo</span></span>

<span data-ttu-id="426b9-223">Sie können ein Modul Objekt vom `Get-Module` Cmdlet an den **Module** -Parameter von übergeben `Save-Help` .</span><span class="sxs-lookup"><span data-stu-id="426b9-223">You can pipe a module object from the `Get-Module` cmdlet to the **Module** parameter of `Save-Help`.</span></span>

## <span data-ttu-id="426b9-224">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="426b9-224">OUTPUTS</span></span>

### <span data-ttu-id="426b9-225">Keine</span><span class="sxs-lookup"><span data-stu-id="426b9-225">None</span></span>

<span data-ttu-id="426b9-226">Dieses Cmdlet generiert keine Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="426b9-226">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="426b9-227">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="426b9-227">NOTES</span></span>

- <span data-ttu-id="426b9-228">Um die Hilfe für Module im Ordner "$PSHome \modules" zu speichern, starten Sie PowerShell mithilfe der Option als Administrator ausführen.</span><span class="sxs-lookup"><span data-stu-id="426b9-228">To save help for modules in the $pshome\Modules folder, start PowerShell by using the Run as administrator option.</span></span> <span data-ttu-id="426b9-229">Nur Mitglieder der Gruppe "Administratoren" auf dem Computer können die Hilfe für Module im Ordner "$PSHome \modules" herunterladen.</span><span class="sxs-lookup"><span data-stu-id="426b9-229">Only members of the Administrators group on the computer can download help for modules in the $pshome\Modules folder.</span></span>
- <span data-ttu-id="426b9-230">Die gespeicherte Hilfe für jedes Modul besteht aus einer Hilfe Informationsdatei (helpinfo XML) und einer CAB-Datei für die Hilfedateien jeder Benutzeroberflächen Kultur.</span><span class="sxs-lookup"><span data-stu-id="426b9-230">The saved help for each module consists of one help information (HelpInfo XML) file and one cabinet (.cab) file for the help files each UI culture.</span></span> <span data-ttu-id="426b9-231">Sie müssen die Hilfedateien nicht aus der CAB-Datei extrahieren.</span><span class="sxs-lookup"><span data-stu-id="426b9-231">You do not have to extract the help files from the cabinet file.</span></span> <span data-ttu-id="426b9-232">Das- `Update-Help` Cmdlet extrahiert die Hilfedateien, überprüft den XML-Code und installiert dann die Hilfedateien und die Hilfe Informationsdatei in einem sprachspezifischen Unterordner des Modul Ordners.</span><span class="sxs-lookup"><span data-stu-id="426b9-232">The `Update-Help` cmdlet extracts the help files, validates the XML, and then installs the help files and the help information file in a language-specific subfolder of the module folder.</span></span>
- <span data-ttu-id="426b9-233">Mit dem- `Save-Help` Cmdlet können Sie die Hilfe für Module speichern, die nicht auf dem Computer installiert sind.</span><span class="sxs-lookup"><span data-stu-id="426b9-233">The `Save-Help` cmdlet can save help for modules that are not installed on the computer.</span></span> <span data-ttu-id="426b9-234">Da jedoch Hilfedateien im Modul Ordner installiert sind, `Update-Help` kann das Cmdlet die aktualisierte Hilfedatei nur für Module installieren, die auf dem Computer installiert sind.</span><span class="sxs-lookup"><span data-stu-id="426b9-234">However, because help files are installed in the module folder, the `Update-Help` cmdlet can install updated help file only for modules that are installed on the computer.</span></span>
- <span data-ttu-id="426b9-235">Wenn `Save-Help` aktualisierte Hilfedateien für ein Modul nicht finden oder aktualisierte Hilfedateien nicht in der angegebenen Sprache finden kann, wird das unbeaufsichtigte fortgesetzt, ohne dass eine Fehlermeldung angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="426b9-235">If `Save-Help` cannot find updated help files for a module, or cannot find updated help files in the specified language, it continues silently without displaying an error message.</span></span> <span data-ttu-id="426b9-236">Um anzuzeigen, welche Dateien durch den Befehl gespeichert wurden, geben Sie den **verbose** -Parameter an.</span><span class="sxs-lookup"><span data-stu-id="426b9-236">To see which files were saved by the command, specify the **Verbose** parameter.</span></span>
- <span data-ttu-id="426b9-237">Module sind die kleinste Einheit der aktualisierbaren Hilfe.</span><span class="sxs-lookup"><span data-stu-id="426b9-237">Modules are the smallest unit of updatable help.</span></span> <span data-ttu-id="426b9-238">Sie können die Hilfe nicht für ein bestimmtes Cmdlet speichern, sondern nur für alle Cmdlets im Modul.</span><span class="sxs-lookup"><span data-stu-id="426b9-238">You cannot save help for a particular cmdlet, only for all cmdlets in module.</span></span> <span data-ttu-id="426b9-239">Um das Modul zu suchen, das ein bestimmtes Cmdlet enthält, verwenden Sie die **ModuleName** -Eigenschaft mit dem- `Get-Command` Cmdlet, z. b. `(Get-Command \<cmdlet-name\>).ModuleName`</span><span class="sxs-lookup"><span data-stu-id="426b9-239">To find the module that contains a particular cmdlet, use the **ModuleName** property together with the `Get-Command` cmdlet, for example, `(Get-Command \<cmdlet-name\>).ModuleName`</span></span>
- <span data-ttu-id="426b9-240">`Save-Help` unterstützt alle Module und die PowerShell-Kern-Snap-Ins. Es werden keine anderen Snap-Ins unterstützt.</span><span class="sxs-lookup"><span data-stu-id="426b9-240">`Save-Help` supports all modules and the PowerShell Core snap-ins. It does not support any other snap-ins.</span></span>
- <span data-ttu-id="426b9-241">Die `Update-Help` -und- `Save-Help` Cmdlets verwenden die folgenden Ports, um Hilfedateien herunterzuladen: Port 80 für http und Port 443 für HTTPS.</span><span class="sxs-lookup"><span data-stu-id="426b9-241">The `Update-Help` and `Save-Help` cmdlets use the following ports to download help files: Port 80 for HTTP and port 443 for HTTPS.</span></span>
- <span data-ttu-id="426b9-242">Die `Update-Help` `Save-Help` Cmdlets und werden auf Windows Preinstallation Environment (Windows PE) nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="426b9-242">The `Update-Help` and `Save-Help` cmdlets are not supported on Windows Preinstallation Environment (Windows PE).</span></span>

## <span data-ttu-id="426b9-243">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="426b9-243">RELATED LINKS</span></span>

[<span data-ttu-id="426b9-244">Get-Help</span><span class="sxs-lookup"><span data-stu-id="426b9-244">Get-Help</span></span>](Get-Help.md)

[<span data-ttu-id="426b9-245">Get-Module</span><span class="sxs-lookup"><span data-stu-id="426b9-245">Get-Module</span></span>](Get-Module.md)

[<span data-ttu-id="426b9-246">Update-Help</span><span class="sxs-lookup"><span data-stu-id="426b9-246">Update-Help</span></span>](Update-Help.md)