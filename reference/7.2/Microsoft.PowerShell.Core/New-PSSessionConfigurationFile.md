---
external help file: System.Management.Automation.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Core
ms.date: 06/24/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/new-pssessionconfigurationfile?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: New-PSSessionConfigurationFile
ms.openlocfilehash: a41c52bf163aa0a73b54e75b5192389a14da82bb
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99599433"
---
# <span data-ttu-id="4dd66-102">New-PSSessionConfigurationFile</span><span class="sxs-lookup"><span data-stu-id="4dd66-102">New-PSSessionConfigurationFile</span></span>

## <span data-ttu-id="4dd66-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="4dd66-103">SYNOPSIS</span></span>
<span data-ttu-id="4dd66-104">Erstellt eine Datei, die eine Sitzungskonfiguration definiert.</span><span class="sxs-lookup"><span data-stu-id="4dd66-104">Creates a file that defines a session configuration.</span></span>

## <span data-ttu-id="4dd66-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="4dd66-105">SYNTAX</span></span>

```
New-PSSessionConfigurationFile [-Path] <String> [-SchemaVersion <Version>] [-Guid <Guid>]
 [-Author <String>] [-Description <String>] [-CompanyName <String>] [-Copyright <String>]
 [-SessionType <SessionType>] [-TranscriptDirectory <String>] [-RunAsVirtualAccount]
 [-RunAsVirtualAccountGroups <String[]>] [-MountUserDrive] [-UserDriveMaximumSize <Int64>]
 [-GroupManagedServiceAccount <String>] [-ScriptsToProcess <String[]>]
 [-RoleDefinitions <IDictionary>] [-RequiredGroups <IDictionary>] [-LanguageMode <PSLanguageMode>]
 [-ExecutionPolicy <ExecutionPolicy>] [-PowerShellVersion <Version>] [-ModulesToImport <Object[]>]
 [-VisibleAliases <String[]>] [-VisibleCmdlets <Object[]>] [-VisibleFunctions <Object[]>]
 [-VisibleExternalCommands <String[]>] [-VisibleProviders <String[]>]
 [-AliasDefinitions <IDictionary[]>] [-FunctionDefinitions <IDictionary[]>]
 [-VariableDefinitions <Object>] [-EnvironmentVariables <IDictionary>] [-TypesToProcess <String[]>]
 [-FormatsToProcess <String[]>] [-AssembliesToLoad <String[]>] [-Full] [<CommonParameters>]
```

## <span data-ttu-id="4dd66-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="4dd66-106">DESCRIPTION</span></span>

<span data-ttu-id="4dd66-107">Mit dem `New-PSSessionConfigurationFile` -Cmdlet wird eine Datei mit Einstellungen erstellt, mit denen eine Sitzungs Konfiguration und die Umgebung der Sitzungen definiert werden, die mit der Sitzungs Konfiguration erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="4dd66-107">The `New-PSSessionConfigurationFile` cmdlet creates a file of settings that define a session configuration and the environment of sessions that are created by using the session configuration.</span></span>
<span data-ttu-id="4dd66-108">Wenn Sie die Datei in einer Sitzungs Konfiguration verwenden möchten, verwenden Sie den **path** -Parameter der `Register-PSSessionConfiguration` `Set-PSSessionConfiguration` Cmdlets oder.</span><span class="sxs-lookup"><span data-stu-id="4dd66-108">To use the file in a session configuration, use the **Path** parameter of the `Register-PSSessionConfiguration` or `Set-PSSessionConfiguration` cmdlets.</span></span>

<span data-ttu-id="4dd66-109">Die Sitzungs Konfigurationsdatei, die `New-PSSessionConfigurationFile` erstellt, ist eine lesbare Textdatei, die eine Hash Tabelle mit den Eigenschaften und Werten der Sitzungs Konfiguration enthält.</span><span class="sxs-lookup"><span data-stu-id="4dd66-109">The session configuration file that `New-PSSessionConfigurationFile` creates is a human-readable text file that contains a hash table of the session configuration properties and values.</span></span> <span data-ttu-id="4dd66-110">Die Datei hat eine Datei `.pssc` Namen Erweiterung.</span><span class="sxs-lookup"><span data-stu-id="4dd66-110">The file has a `.pssc` filename extension.</span></span>

<span data-ttu-id="4dd66-111">Alle Parameter von `New-PSSessionConfigurationFile` sind optional, mit Ausnahme des **path** -Parameters.</span><span class="sxs-lookup"><span data-stu-id="4dd66-111">All parameters of `New-PSSessionConfigurationFile` are optional, except for the **Path** parameter.</span></span>
<span data-ttu-id="4dd66-112">Wenn Sie einen Parameter weglassen, wird der entsprechende Schlüssel in der Sitzungskonfigurationsdatei auskommentiert, es sei denn, er wurde in der Parameterbeschreibung angegeben.</span><span class="sxs-lookup"><span data-stu-id="4dd66-112">If you omit a parameter, the corresponding key in the session configuration file is commented-out, except where noted in the parameter description.</span></span>

<span data-ttu-id="4dd66-113">Eine Sitzungs Konfiguration, auch als Endpunkt bezeichnet, ist eine Sammlung von Einstellungen auf dem lokalen Computer, die die Umgebung für PowerShell-Sitzungen (**pssessions**) definieren, die eine Verbindung mit dem Computer herstellen.</span><span class="sxs-lookup"><span data-stu-id="4dd66-113">A session configuration, also known as an endpoint, is a collection of settings on the local computer that define the environment for PowerShell sessions (**PSSessions**) that connect to the computer.</span></span> <span data-ttu-id="4dd66-114">Alle **pssessions** verwenden eine Sitzungs Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="4dd66-114">All **PSSessions** use a session configuration.</span></span> <span data-ttu-id="4dd66-115">Verwenden Sie zum Angeben einer bestimmten Sitzungs Konfiguration den **ConfigurationName** -Parameter von Cmdlets, die eine Sitzung erstellen, z `New-PSSession` . b. das Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="4dd66-115">To specify a particular session configuration, use the **ConfigurationName** parameter of cmdlets that create a session, such as the `New-PSSession` cmdlet.</span></span>

<span data-ttu-id="4dd66-116">Eine session configuration file erleichtert die Definition einer Sitzungskonfiguration ohne komplexe Skripts oder Codeassemblys.</span><span class="sxs-lookup"><span data-stu-id="4dd66-116">A session configuration file makes it easy to define a session configuration without complex scripts or code assemblies.</span></span> <span data-ttu-id="4dd66-117">Die Einstellungen in der Datei werden mit dem optionalen Startskript und allen Assemblys in der Sitzungs Konfiguration verwendet.</span><span class="sxs-lookup"><span data-stu-id="4dd66-117">The settings in the file are used with the optional startup script and any assemblies in the session configuration.</span></span>

<span data-ttu-id="4dd66-118">Weitere Informationen zu Sitzungs Konfigurationen und Sitzungs Konfigurationsdateien finden Sie unter [about_Session_Configurations](About/about_Session_Configurations.md) und [about_Session_Configuration_Files](About/about_Session_Configuration_Files.md).</span><span class="sxs-lookup"><span data-stu-id="4dd66-118">For more information about session configurations and session configuration files, see [about_Session_Configurations](About/about_Session_Configurations.md) and [about_Session_Configuration_Files](About/about_Session_Configuration_Files.md).</span></span>

<span data-ttu-id="4dd66-119">Dieses Cmdlet wurde in PowerShell 3,0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="4dd66-119">This cmdlet was introduced in PowerShell 3.0.</span></span>

## <span data-ttu-id="4dd66-120">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="4dd66-120">EXAMPLES</span></span>

### <span data-ttu-id="4dd66-121">Beispiel 1: Erstellen und Verwenden einer nolanguage-Sitzung</span><span class="sxs-lookup"><span data-stu-id="4dd66-121">Example 1: Creating and using a NoLanguage session</span></span>

<span data-ttu-id="4dd66-122">In diesem Beispiel wird gezeigt, wie Sie die Verwendung einer Sitzungs basierten Sitzung und die Auswirkungen von erstellen können.</span><span class="sxs-lookup"><span data-stu-id="4dd66-122">This example show how to create and the effects of using a no-language session.</span></span>

<span data-ttu-id="4dd66-123">Dazu müssen folgende Schritte ausgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="4dd66-123">The steps include:</span></span>

1. <span data-ttu-id="4dd66-124">Erstellen Sie eine neue Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="4dd66-124">Create a new configuration file.</span></span>
1. <span data-ttu-id="4dd66-125">Registrieren Sie die Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="4dd66-125">Register the configuration.</span></span>
1. <span data-ttu-id="4dd66-126">Erstellen Sie eine neue Sitzung, in der die-Konfiguration verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="4dd66-126">Create a new session that uses the configuration.</span></span>
1. <span data-ttu-id="4dd66-127">Führt Befehle in dieser neuen Sitzung aus.</span><span class="sxs-lookup"><span data-stu-id="4dd66-127">Run commands in that new session.</span></span>

<span data-ttu-id="4dd66-128">Um die Befehle in diesem Beispiel auszuführen, starten Sie PowerShell mit der Option als Administrator ausführen.</span><span class="sxs-lookup"><span data-stu-id="4dd66-128">To run the commands in this example, start PowerShell by using the Run as administrator option.</span></span> <span data-ttu-id="4dd66-129">Diese Option ist erforderlich, um das `Register-PSSessionConfiguration` Cmdlet auszuführen.</span><span class="sxs-lookup"><span data-stu-id="4dd66-129">This option is required to run the `Register-PSSessionConfiguration` cmdlet.</span></span>

```powershell
New-PSSessionConfigurationFile -Path .\NoLanguage.pssc -LanguageMode NoLanguage
Register-PSSessionConfiguration -Path .\NoLanguage.pssc -Name NoLanguage -Force
$NoLanguageSession = New-PSSession -ComputerName Srv01 -ConfigurationName NoLanguage
Invoke-Command -Session $NoLanguageSession -ScriptBlock {
  if ((Get-Date) -lt '1January2099') {'Before'} else {'After'}
}
```

```Output
The syntax is not supported by this runspace. This might be because it is in no-language mode.
    + CategoryInfo          : ParserError: (if ((Get-Date) ...') {'Before'}  :String) [], ParseException
    + FullyQualifiedErrorId : ScriptsNotAllowed
    + PSComputerName        : localhost
```

<span data-ttu-id="4dd66-130">In diesem Beispiel schlägt der `Invoke-Command` fehl, da **languagemode** auf **nolanguage** festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="4dd66-130">In this example, the `Invoke-Command` fails because the **LanguageMode** is set to **NoLanguage**.</span></span>

### <span data-ttu-id="4dd66-131">Beispiel 2: Erstellen und Verwenden einer restrictedlanguage-Sitzung</span><span class="sxs-lookup"><span data-stu-id="4dd66-131">Example 2: Creating and using a RestrictedLanguage session</span></span>

<span data-ttu-id="4dd66-132">In diesem Beispiel wird gezeigt, wie Sie die Verwendung einer Sitzungs basierten Sitzung und die Auswirkungen von erstellen können.</span><span class="sxs-lookup"><span data-stu-id="4dd66-132">This example show how to create and the effects of using a no-language session.</span></span>

<span data-ttu-id="4dd66-133">Dazu müssen folgende Schritte ausgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="4dd66-133">The steps include:</span></span>

1. <span data-ttu-id="4dd66-134">Erstellen Sie eine neue Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="4dd66-134">Create a new configuration file.</span></span>
1. <span data-ttu-id="4dd66-135">Registrieren Sie die Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="4dd66-135">Register the configuration.</span></span>
1. <span data-ttu-id="4dd66-136">Erstellen Sie eine neue Sitzung, in der die-Konfiguration verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="4dd66-136">Create a new session that uses the configuration.</span></span>
1. <span data-ttu-id="4dd66-137">Führt Befehle in dieser neuen Sitzung aus.</span><span class="sxs-lookup"><span data-stu-id="4dd66-137">Run commands in that new session.</span></span>

<span data-ttu-id="4dd66-138">Um die Befehle in diesem Beispiel auszuführen, starten Sie PowerShell mit der Option als Administrator ausführen.</span><span class="sxs-lookup"><span data-stu-id="4dd66-138">To run the commands in this example, start PowerShell by using the Run as administrator option.</span></span> <span data-ttu-id="4dd66-139">Diese Option ist erforderlich, um das `Register-PSSessionConfiguration` Cmdlet auszuführen.</span><span class="sxs-lookup"><span data-stu-id="4dd66-139">This option is required to run the `Register-PSSessionConfiguration` cmdlet.</span></span>

```powershell
New-PSSessionConfigurationFile -Path .\NoLanguage.pssc -LanguageMode RestrictedLanguage
Register-PSSessionConfiguration -Path .\NoLanguage.pssc -Name RestrictedLanguage -Force
$RestrictedSession = New-PSSession -ComputerName Srv01 -ConfigurationName RestrictedLanguage
Invoke-Command -Session $RestrictedSession -ScriptBlock {
  if ((Get-Date) -lt '1January2099') {'Before'} else {'After'}
}
```

```Output
Before
```

<span data-ttu-id="4dd66-140">In diesem Beispiel `Invoke-Command` ist erfolgreich, da **languagemode** auf **restrictedlanguage** festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="4dd66-140">In this example, the `Invoke-Command` succeeds because the **LanguageMode** is set to **RestrictedLanguage**.</span></span>

### <span data-ttu-id="4dd66-141">Beispiel 3: Ändern einer Sitzungs Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="4dd66-141">Example 3: Changing a Session Configuration File</span></span>

<span data-ttu-id="4dd66-142">Dieses Beispiel zeigt, wie Sie die Sitzungs Konfigurationsdatei ändern können, die in einer vorhandenen Sitzung namens "ittasks" verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="4dd66-142">This example shows how to change the session configuration file that is used in an existing session named "ITTasks".</span></span> <span data-ttu-id="4dd66-143">Bisher verfügten diese Sitzungen nur über die Kernmodule und über ein internes **ittasks** -Modul.</span><span class="sxs-lookup"><span data-stu-id="4dd66-143">Previously, these sessions had only the core modules and an internal **ITTasks** module.</span></span> <span data-ttu-id="4dd66-144">Der Administrator möchte das **psscheduledjob** -Modul zu Sitzungen hinzufügen, die mit der ittasks-Sitzungs Konfiguration erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="4dd66-144">The administrator wants to add the **PSScheduledJob** module to sessions created by using the ITTasks session configuration.</span></span>

```powershell
New-PSSessionConfigurationFile -Path .\New-ITTasks.pssc -ModulesToImport Microsoft*, ITTasks, PSScheduledJob
Set-PSSessionConfiguration -Name ITTasks -Path .\New-ITTasks.pssc
```

<span data-ttu-id="4dd66-145">Mit dem- `New-PSSessionConfigurationFile` Cmdlet können Sie eine Sitzungs Konfigurationsdatei erstellen, mit der die erforderlichen Module importiert werden.</span><span class="sxs-lookup"><span data-stu-id="4dd66-145">The `New-PSSessionConfigurationFile` cmdlet to create a session configuration file that imports the required modules.</span></span> <span data-ttu-id="4dd66-146">Mit dem- `Set-PSSessionConfiguration` Cmdlet wird die aktuelle Konfigurationsdatei durch die neue ersetzt.</span><span class="sxs-lookup"><span data-stu-id="4dd66-146">The `Set-PSSessionConfiguration` cmdlet replaces the current configuration file with the new one.</span></span> <span data-ttu-id="4dd66-147">Diese neue Konfiguration wirkt sich nur auf neue Sitzungen aus, die nach der Änderung erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="4dd66-147">This new configuration only affects new sessions created after the change.</span></span>
<span data-ttu-id="4dd66-148">Vorhandene ittasks-Sitzungen sind nicht betroffen.</span><span class="sxs-lookup"><span data-stu-id="4dd66-148">Existing "ITTasks" sessions are not affected.</span></span>

### <span data-ttu-id="4dd66-149">Beispiel 4: Bearbeiten einer Sitzungs Konfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="4dd66-149">Example 4: Editing a Session Configuration File</span></span>

<span data-ttu-id="4dd66-150">In diesem Beispiel wird veranschaulicht, wie Sie eine Sitzungskonfiguration durch Bearbeiten der aktiven Sitzungskonfigurationskopie der Konfigurationsdatei ändern können.</span><span class="sxs-lookup"><span data-stu-id="4dd66-150">This example shows how to change a session configuration by editing the active session configuration copy of the configuration file.</span></span> <span data-ttu-id="4dd66-151">Um die Sitzungs Konfigurationskopie der Konfigurationsdatei zu ändern, müssen Sie über Vollzugriff auf die Datei verfügen.</span><span class="sxs-lookup"><span data-stu-id="4dd66-151">To modify the session configuration copy of the configuration file, you must have full control access to the file.</span></span> <span data-ttu-id="4dd66-152">Dies erfordert möglicherweise das Ändern der Berechtigungen für die Datei.</span><span class="sxs-lookup"><span data-stu-id="4dd66-152">This may require you to change the permissions on the file.</span></span>

<span data-ttu-id="4dd66-153">In diesem Szenario möchten wir einen neuen Alias für das `Select-String` Cmdlet hinzufügen, indem wir die aktive Konfigurationsdatei bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="4dd66-153">In this scenario, we want to add a new alias for the `Select-String` cmdlet by editing the active configuration file.</span></span>

<span data-ttu-id="4dd66-154">Der folgende Beispielcode führt die folgenden Schritte aus, um diese Änderung vorzunehmen:</span><span class="sxs-lookup"><span data-stu-id="4dd66-154">The example code below performs the following steps to make this change:</span></span>

1. <span data-ttu-id="4dd66-155">Den Pfad der Konfigurationsdatei für die ITconfig-Sitzung erhalten.</span><span class="sxs-lookup"><span data-stu-id="4dd66-155">Get the configuration file path for the ITConfig session.</span></span>
1. <span data-ttu-id="4dd66-156">Der Benutzer bearbeitet die Konfigurationsdatei mit **Notepad.exe** , um den **aliasdefinitions** -Wert wie folgt zu ändern: `AliasDefinitions = @(@{Name='slst';Value='Select-String'})` .</span><span class="sxs-lookup"><span data-stu-id="4dd66-156">The user edits the configuration file using **Notepad.exe** to change the **AliasDefinitions** value as follows: `AliasDefinitions = @(@{Name='slst';Value='Select-String'})`.</span></span>
1. <span data-ttu-id="4dd66-157">Testen Sie die aktualisierte Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="4dd66-157">Test the updated configuration file.</span></span>

```powershell
$ITConfig = Get-PSSessionConfiguration -Name ITConfig
notepad.exe $ITConfig.ConfigFilePath
Test-PSSessionConfigurationFile -Path $ITConfig.ConfigFilePath
```

```Output
True
```

<span data-ttu-id="4dd66-158">Verwenden Sie den **verbose** -Parameter mit `Test-PSSessionConfigurationFile` , um alle erkannten Fehler anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="4dd66-158">Use the **Verbose** parameter with `Test-PSSessionConfigurationFile` to display any errors that are detected.</span></span> <span data-ttu-id="4dd66-159">Das-Cmdlet gibt zurück, `$True` Wenn keine Fehler in der Datei erkannt werden.</span><span class="sxs-lookup"><span data-stu-id="4dd66-159">The cmdlet returns `$True` if no errors are detected in the file.</span></span>

### <span data-ttu-id="4dd66-160">Beispiel 5: Erstellen einer Beispielkonfigurationsdatei</span><span class="sxs-lookup"><span data-stu-id="4dd66-160">Example 5: Create a sample configuration file</span></span>

<span data-ttu-id="4dd66-161">Dieses Beispiel zeigt einen `New-PSSessionConfigurationFile` Befehl, der alle Cmdlet-Parameter verwendet.</span><span class="sxs-lookup"><span data-stu-id="4dd66-161">This example shows a `New-PSSessionConfigurationFile` command that uses all the cmdlet parameters.</span></span>
<span data-ttu-id="4dd66-162">Er wurde angegeben, um das richtige Eingabeformat für jeden Parameter zu zeigen.</span><span class="sxs-lookup"><span data-stu-id="4dd66-162">It is included to show the correct input format for each parameter.</span></span>

<span data-ttu-id="4dd66-163">Die resultierende SampleFile.pssc wird in der Ausgabe angezeigt.</span><span class="sxs-lookup"><span data-stu-id="4dd66-163">The resulting SampleFile.pssc is displayed in the output.</span></span>

```powershell
$configSettings = @{
    Path = '.\SampleFile.pssc'
    SchemaVersion = '1.0.0.0'
    Author = 'User01'
    Copyright = '(c) Fabrikam Corporation. All rights reserved.'
    CompanyName = 'Fabrikam Corporation'
    Description = 'This is a sample file.'
    ExecutionPolicy = 'AllSigned'
    PowerShellVersion = '3.0'
    LanguageMode = 'FullLanguage'
    SessionType = 'Default'
    EnvironmentVariables = @{TESTSHARE='\\Test2\Test'}
    ModulesToImport = @{ModuleName='PSScheduledJob'; ModuleVersion='1.0.0.0'; GUID='50cdb55f-5ab7-489f-9e94-4ec21ff51e59'},'PSDiagnostics'
    AssembliesToLoad = 'System.Web.Services','FSharp.Compiler.CodeDom.dll'
    TypesToProcess = 'Types1.ps1xml','Types2.ps1xml'
    FormatsToProcess = 'CustomFormats.ps1xml'
    ScriptsToProcess = 'Get-Inputs.ps1'
    AliasDefinitions = @{Name='hlp';Value='Get-Help';Description='Gets help.';Options='AllScope'},
        @{Name='Update';Value='Update-Help';Description='Updates help';Options='ReadOnly'}
    FunctionDefinitions = @{Name='Get-Function';ScriptBlock={Get-Command -CommandType Function};Options='ReadOnly'}
    VariableDefinitions = @{Name='WarningPreference';Value='SilentlyContinue'}
    VisibleAliases = 'c*','g*','i*','s*'
    VisibleCmdlets = 'Get*'
    VisibleFunctions = 'Get*'
    VisibleProviders = 'FileSystem','Function','Variable'
    RunAsVirtualAccount = $true
    RunAsVirtualAccountGroups = 'Backup Operators'
}
New-PSSessionConfigurationFile @configSettings
Get-Content SampleFile.pssc
```

```Output
@{

# Version number of the schema used for this document
SchemaVersion = '1.0.0.0'

# ID used to uniquely identify this document
GUID = '1caeff7f-27ca-4360-97cf-37846f594235'

# Author of this document
Author = 'User01'

# Description of the functionality provided by these settings
Description = 'This is a sample file.'

# Company associated with this document
CompanyName = 'Fabrikam Corporation'

# Copyright statement for this document
Copyright = '(c) Fabrikam Corporation. All rights reserved.'

# Session type defaults to apply for this session configuration. Can be 'RestrictedRemoteServer' (recommended), 'Empty', or 'Default'
SessionType = 'Default'

# Directory to place session transcripts for this session configuration
# TranscriptDirectory = 'C:\Transcripts\'

# Whether to run this session configuration as the machine's (virtual) administrator account
RunAsVirtualAccount = $true

# Groups associated with machine's (virtual) administrator account
RunAsVirtualAccountGroups = 'Backup Operators'

# Scripts to run when applied to a session
ScriptsToProcess = 'Get-Inputs.ps1'

# User roles (security groups), and the role capabilities that should be applied to them when applied to a session
# RoleDefinitions = @{ 'CONTOSO\SqlAdmins' = @{ RoleCapabilities = 'SqlAdministration' }; 'CONTOSO\SqlManaged' = @{ RoleCapabilityFiles = 'C:\RoleCapability\SqlManaged.psrc' }; 'CONTOSO\ServerMonitors' = @{ VisibleCmdlets = 'Get-Process' } }

# Language mode to apply when applied to a session. Can be 'NoLanguage' (recommended), 'RestrictedLanguage', 'ConstrainedLanguage', or 'FullLanguage'
LanguageMode = 'FullLanguage'

# Execution policy to apply when applied to a session
ExecutionPolicy = 'AllSigned'

# Version of the PowerShell engine to use when applied to a session
PowerShellVersion = '3.0'

# Modules to import when applied to a session
ModulesToImport = @{
    'GUID' = '50cdb55f-5ab7-489f-9e94-4ec21ff51e59'
    'ModuleName' = 'PSScheduledJob'
    'ModuleVersion' = '1.0.0.0' }, 'PSDiagnostics'

# Aliases to make visible when applied to a session
VisibleAliases = 'c*', 'g*', 'i*', 's*'

# Cmdlets to make visible when applied to a session
VisibleCmdlets = 'Get*'

# Functions to make visible when applied to a session
VisibleFunctions = 'Get*'

# Providers to make visible when applied to a session
VisibleProviders = 'FileSystem', 'Function', 'Variable'

# Aliases to be defined when applied to a session
AliasDefinitions = @{
    'Description' = 'Gets help.'
    'Name' = 'hlp'
    'Options' = 'AllScope'
    'Value' = 'Get-Help' }, @{
    'Description' = 'Updates help'
    'Name' = 'Update'
    'Options' = 'ReadOnly'
    'Value' = 'Update-Help' }

# Functions to define when applied to a session
FunctionDefinitions = @{
    'Name' = 'Get-Function'
    'Options' = 'ReadOnly'
    'ScriptBlock' = {Get-Command -CommandType Function} }

# Variables to define when applied to a session
VariableDefinitions = @{
    'Name' = 'WarningPreference'
    'Value' = 'SilentlyContinue' }

# Environment variables to define when applied to a session
EnvironmentVariables = @{
    'TESTSHARE' = '\\Test2\Test' }

# Type files (.ps1xml) to load when applied to a session
TypesToProcess = 'Types1.ps1xml', 'Types2.ps1xml'

# Format files (.ps1xml) to load when applied to a session
FormatsToProcess = 'CustomFormats.ps1xml'

# Assemblies to load when applied to a session
AssembliesToLoad = 'System.Web.Services', 'FSharp.Compiler.CodeDom.dll'

}
```

## <span data-ttu-id="4dd66-164">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="4dd66-164">PARAMETERS</span></span>

### <span data-ttu-id="4dd66-165">-Aliasdefinitionen</span><span class="sxs-lookup"><span data-stu-id="4dd66-165">-AliasDefinitions</span></span>

<span data-ttu-id="4dd66-166">Fügt die angegebenen Aliase zu Sitzungen hinzu, die die Sitzungskonfiguration verwenden.</span><span class="sxs-lookup"><span data-stu-id="4dd66-166">Adds the specified aliases to sessions that use the session configuration.</span></span> <span data-ttu-id="4dd66-167">Geben Sie eine Hashtabelle mit den folgenden Schlüsseln ein:</span><span class="sxs-lookup"><span data-stu-id="4dd66-167">Enter a hash table with the following keys:</span></span>

- <span data-ttu-id="4dd66-168">Name: Name des Alias.</span><span class="sxs-lookup"><span data-stu-id="4dd66-168">Name - Name of the alias.</span></span> <span data-ttu-id="4dd66-169">Dieser Schlüssel ist erforderlich.</span><span class="sxs-lookup"><span data-stu-id="4dd66-169">This key is required.</span></span>
- <span data-ttu-id="4dd66-170">Value: der Befehl, den der Alias darstellt.</span><span class="sxs-lookup"><span data-stu-id="4dd66-170">Value - The command that the alias represents.</span></span> <span data-ttu-id="4dd66-171">Dieser Schlüssel ist erforderlich.</span><span class="sxs-lookup"><span data-stu-id="4dd66-171">This key is required.</span></span>
- <span data-ttu-id="4dd66-172">Description: eine Text Zeichenfolge, die den Alias beschreibt.</span><span class="sxs-lookup"><span data-stu-id="4dd66-172">Description - A text string that describes the alias.</span></span> <span data-ttu-id="4dd66-173">Dieser Schlüssel ist optional.</span><span class="sxs-lookup"><span data-stu-id="4dd66-173">This key is optional.</span></span>
- <span data-ttu-id="4dd66-174">Optionen: Alias Optionen.</span><span class="sxs-lookup"><span data-stu-id="4dd66-174">Options - Alias options.</span></span> <span data-ttu-id="4dd66-175">Dieser Schlüssel ist optional.</span><span class="sxs-lookup"><span data-stu-id="4dd66-175">This key is optional.</span></span> <span data-ttu-id="4dd66-176">Der Standardwert ist " **None**".</span><span class="sxs-lookup"><span data-stu-id="4dd66-176">The default value is **None**.</span></span> <span data-ttu-id="4dd66-177">Die zulässigen Werte für diesen Parameter lauten: None, Read Only, Constant, private oder allscope.</span><span class="sxs-lookup"><span data-stu-id="4dd66-177">The acceptable values for this parameter are: None, ReadOnly, Constant, Private, or AllScope.</span></span>

<span data-ttu-id="4dd66-178">Beispiel: `@{Name='hlp';Value='Get-Help';Description='Gets help';Options='ReadOnly'}`</span><span class="sxs-lookup"><span data-stu-id="4dd66-178">For example: `@{Name='hlp';Value='Get-Help';Description='Gets help';Options='ReadOnly'}`</span></span>

```yaml
Type: System.Collections.IDictionary[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="4dd66-179">-Assemliestoload</span><span class="sxs-lookup"><span data-stu-id="4dd66-179">-AssembliesToLoad</span></span>

<span data-ttu-id="4dd66-180">Gibt die Assemblys an, die in die Sitzungen geladen werden sollen und die die Sitzungskonfiguration verwenden.</span><span class="sxs-lookup"><span data-stu-id="4dd66-180">Specifies the assemblies to load into the sessions that use the session configuration.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="4dd66-181">-Autor</span><span class="sxs-lookup"><span data-stu-id="4dd66-181">-Author</span></span>

<span data-ttu-id="4dd66-182">Gibt den Autor der Sitzungs Konfiguration oder der Konfigurationsdatei an.</span><span class="sxs-lookup"><span data-stu-id="4dd66-182">Specifies the author of the session configuration or the configuration file.</span></span> <span data-ttu-id="4dd66-183">Der Standardwert ist der aktuelle Benutzer.</span><span class="sxs-lookup"><span data-stu-id="4dd66-183">The default is the current user.</span></span> <span data-ttu-id="4dd66-184">Der Wert dieses Parameters wird in der Sitzungskonfigurationsdatei angezeigt, aber es handelt sich nicht um eine Eigenschaft des Sitzungskonfigurationsobjekts.</span><span class="sxs-lookup"><span data-stu-id="4dd66-184">The value of this parameter is visible in the session configuration file, but it is not a property of the session configuration object.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="4dd66-185">-CompanyName</span><span class="sxs-lookup"><span data-stu-id="4dd66-185">-CompanyName</span></span>

<span data-ttu-id="4dd66-186">Gibt das Unternehmen an, das die Sitzungs Konfiguration oder die Konfigurationsdatei erstellt hat.</span><span class="sxs-lookup"><span data-stu-id="4dd66-186">Specifies the company that created the session configuration or the configuration file.</span></span> <span data-ttu-id="4dd66-187">Der Standardwert ist **Unknown** (Unbekannt).</span><span class="sxs-lookup"><span data-stu-id="4dd66-187">The default value is **Unknown**.</span></span> <span data-ttu-id="4dd66-188">Der Wert dieses Parameters wird in der Sitzungskonfigurationsdatei angezeigt, aber es handelt sich nicht um eine Eigenschaft des Sitzungskonfigurationsobjekts.</span><span class="sxs-lookup"><span data-stu-id="4dd66-188">The value of this parameter is visible in the session configuration file, but it is not a property of the session configuration object.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Unknown
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="4dd66-189">-Copyright</span><span class="sxs-lookup"><span data-stu-id="4dd66-189">-Copyright</span></span>

<span data-ttu-id="4dd66-190">Gibt ein Copyright der Sitzungs Konfigurationsdatei an.</span><span class="sxs-lookup"><span data-stu-id="4dd66-190">Specifies a copyright the session configuration file.</span></span> <span data-ttu-id="4dd66-191">Der Wert dieses Parameters wird in der Sitzungskonfigurationsdatei angezeigt, aber es handelt sich nicht um eine Eigenschaft des Sitzungskonfigurationsobjekts.</span><span class="sxs-lookup"><span data-stu-id="4dd66-191">The value of this parameter is visible in the session configuration file, but it is not a property of the session configuration object.</span></span>

<span data-ttu-id="4dd66-192">Wenn Sie diesen Parameter weglassen, `New-PSSessionConfigurationFile` generiert eine Copyright Anweisung mit dem Wert des **Author** -Parameters.</span><span class="sxs-lookup"><span data-stu-id="4dd66-192">If you omit this parameter, `New-PSSessionConfigurationFile` generates a copyright statement by using the value of the **Author** parameter.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="4dd66-193">-Description</span><span class="sxs-lookup"><span data-stu-id="4dd66-193">-Description</span></span>

<span data-ttu-id="4dd66-194">Gibt eine Beschreibung der Sitzungs Konfiguration oder der Sitzungs Konfigurationsdatei an.</span><span class="sxs-lookup"><span data-stu-id="4dd66-194">Specifies a description of the session configuration or the session configuration file.</span></span> <span data-ttu-id="4dd66-195">Der Wert dieses Parameters wird in der Sitzungskonfigurationsdatei angezeigt, aber es handelt sich nicht um eine Eigenschaft des Sitzungskonfigurationsobjekts.</span><span class="sxs-lookup"><span data-stu-id="4dd66-195">The value of this parameter is visible in the session configuration file, but it is not a property of the session configuration object.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="4dd66-196">-Umgebungsvariablen</span><span class="sxs-lookup"><span data-stu-id="4dd66-196">-EnvironmentVariables</span></span>

<span data-ttu-id="4dd66-197">Fügt der Sitzung Umgebungsvariablen hinzu.</span><span class="sxs-lookup"><span data-stu-id="4dd66-197">Adds environment variables to the session.</span></span> <span data-ttu-id="4dd66-198">Geben Sie eine Hashtabelle ein, in der die Schlüssel die Namen der Umgebungsvariablen und die Werte die Werte der Umgebungsvariablen sind.</span><span class="sxs-lookup"><span data-stu-id="4dd66-198">Enter a hash table in which the keys are the environment variable names and the values are the environment variable values.</span></span>

<span data-ttu-id="4dd66-199">Beispiel: `EnvironmentVariables=@{TestShare='\\Server01\TestShare'}`</span><span class="sxs-lookup"><span data-stu-id="4dd66-199">For example: `EnvironmentVariables=@{TestShare='\\Server01\TestShare'}`</span></span>

```yaml
Type: System.Collections.IDictionary
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="4dd66-200">-ExecutionPolicy</span><span class="sxs-lookup"><span data-stu-id="4dd66-200">-ExecutionPolicy</span></span>

<span data-ttu-id="4dd66-201">Bestimmt die Ausführungsrichtlinie von Sitzungen, die die Sitzungskonfiguration verwenden.</span><span class="sxs-lookup"><span data-stu-id="4dd66-201">Specifies the execution policy of sessions that use the session configuration.</span></span> <span data-ttu-id="4dd66-202">Wenn Sie diesen Parameter weglassen, ist der Wert des **ExecutionPolicy** -Schlüssels in der Sitzungs Konfigurationsdatei **eingeschränkt**.</span><span class="sxs-lookup"><span data-stu-id="4dd66-202">If you omit this parameter, the value of the **ExecutionPolicy** key in the session configuration file is **Restricted**.</span></span> <span data-ttu-id="4dd66-203">Informationen zu Ausführungsrichtlinien in PowerShell finden Sie unter [about_Execution_Policies](about/about_Execution_Policies.md).</span><span class="sxs-lookup"><span data-stu-id="4dd66-203">For information about execution policies in PowerShell, see [about_Execution_Policies](about/about_Execution_Policies.md).</span></span>

```yaml
Type: Microsoft.PowerShell.ExecutionPolicy
Parameter Sets: (All)
Aliases:
Accepted values: Unrestricted, RemoteSigned, AllSigned, Restricted, Default, Bypass, Undefined

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="4dd66-204">-Formatstoprocess</span><span class="sxs-lookup"><span data-stu-id="4dd66-204">-FormatsToProcess</span></span>

<span data-ttu-id="4dd66-205">Gibt die Formatierungsdateien (.ps1xml) an, die in Sitzungen ausgeführt werden, die die Sitzungskonfiguration verwenden.</span><span class="sxs-lookup"><span data-stu-id="4dd66-205">Specifies the formatting files (.ps1xml) that run in sessions that use the session configuration.</span></span>
<span data-ttu-id="4dd66-206">Der Wert dieses Parameters muss ein vollständiger oder absoluter Pfad der Formatierungs Dateien sein.</span><span class="sxs-lookup"><span data-stu-id="4dd66-206">The value of this parameter must be a full or absolute path of the formatting files.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="4dd66-207">-Full</span><span class="sxs-lookup"><span data-stu-id="4dd66-207">-Full</span></span>

<span data-ttu-id="4dd66-208">Gibt an, dass dieser Vorgang alle möglichen Konfigurations Eigenschaften in der Sitzungs Konfigurationsdatei enthält.</span><span class="sxs-lookup"><span data-stu-id="4dd66-208">Indicates that this operation includes all possible configuration properties in the session configuration file.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="4dd66-209">-Functiondefinitions</span><span class="sxs-lookup"><span data-stu-id="4dd66-209">-FunctionDefinitions</span></span>

<span data-ttu-id="4dd66-210">Fügt Sitzungen, die die Sitzungskonfiguration verwenden, die angegebenen Funktionen hinzu.</span><span class="sxs-lookup"><span data-stu-id="4dd66-210">Adds the specified functions to sessions that use the session configuration.</span></span> <span data-ttu-id="4dd66-211">Geben Sie eine Hashtabelle mit den folgenden Schlüsseln ein:</span><span class="sxs-lookup"><span data-stu-id="4dd66-211">Enter a hash table with the following keys:</span></span>

- <span data-ttu-id="4dd66-212">Name: der Name der Funktion.</span><span class="sxs-lookup"><span data-stu-id="4dd66-212">Name - Name of the function.</span></span> <span data-ttu-id="4dd66-213">Dieser Schlüssel ist erforderlich.</span><span class="sxs-lookup"><span data-stu-id="4dd66-213">This key is required.</span></span>
- <span data-ttu-id="4dd66-214">ScriptBlock-Funktions Text.</span><span class="sxs-lookup"><span data-stu-id="4dd66-214">ScriptBlock - Function body.</span></span> <span data-ttu-id="4dd66-215">Geben Sie einen Skriptblock ein.</span><span class="sxs-lookup"><span data-stu-id="4dd66-215">Enter a script block.</span></span> <span data-ttu-id="4dd66-216">Dieser Schlüssel ist erforderlich.</span><span class="sxs-lookup"><span data-stu-id="4dd66-216">This key is required.</span></span>
- <span data-ttu-id="4dd66-217">Optionen: Funktions Optionen.</span><span class="sxs-lookup"><span data-stu-id="4dd66-217">Options - Function options.</span></span> <span data-ttu-id="4dd66-218">Dieser Schlüssel ist optional.</span><span class="sxs-lookup"><span data-stu-id="4dd66-218">This key is optional.</span></span> <span data-ttu-id="4dd66-219">Der Standardwert ist " **None**".</span><span class="sxs-lookup"><span data-stu-id="4dd66-219">The default value is **None**.</span></span> <span data-ttu-id="4dd66-220">Die zulässigen Werte für diesen Parameter lauten: None, Read Only, Constant, private oder allscope.</span><span class="sxs-lookup"><span data-stu-id="4dd66-220">The acceptable values for this parameter are: None, ReadOnly, Constant, Private, or AllScope.</span></span>

<span data-ttu-id="4dd66-221">Beispiel: `@{Name='Get-PowerShellProcess';ScriptBlock={Get-Process PowerShell};Options='AllScope'}`</span><span class="sxs-lookup"><span data-stu-id="4dd66-221">For example: `@{Name='Get-PowerShellProcess';ScriptBlock={Get-Process PowerShell};Options='AllScope'}`</span></span>

```yaml
Type: System.Collections.IDictionary[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="4dd66-222">-Groupmanagedserviceaccount</span><span class="sxs-lookup"><span data-stu-id="4dd66-222">-GroupManagedServiceAccount</span></span>

<span data-ttu-id="4dd66-223">Konfiguriert Sitzungen, die diese Sitzungs Konfiguration verwenden, um im Kontext des angegebenen Gruppen verwalteten Dienst Kontos ausgeführt zu werden.</span><span class="sxs-lookup"><span data-stu-id="4dd66-223">Configures sessions using this session configuration to run under the context of the specified Group Managed Service Account.</span></span> <span data-ttu-id="4dd66-224">Der Computer, auf dem diese Sitzungs Konfiguration registriert ist, muss über die Berechtigung zum Anfordern des GMSA-Kennworts verfügen, damit Sitzungen erfolgreich erstellt werden können.</span><span class="sxs-lookup"><span data-stu-id="4dd66-224">The machine where this session configuration is registered must have permission to request the gMSA password in order for sessions to be created successfully.</span></span> <span data-ttu-id="4dd66-225">Dieses Feld kann nicht mit dem Parameter " **runasvirtualaccount** " verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="4dd66-225">This field cannot be used with the **RunAsVirtualAccount** parameter.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="4dd66-226">-GUID</span><span class="sxs-lookup"><span data-stu-id="4dd66-226">-Guid</span></span>

<span data-ttu-id="4dd66-227">Gibt einen eindeutigen Bezeichner für die Sitzungskonfigurationsdatei an.</span><span class="sxs-lookup"><span data-stu-id="4dd66-227">Specifies a unique identifier for the session configuration file.</span></span> <span data-ttu-id="4dd66-228">Wenn Sie diesen Parameter weglassen, `New-PSSessionConfigurationFile` generiert eine GUID für die Datei.</span><span class="sxs-lookup"><span data-stu-id="4dd66-228">If you omit this parameter, `New-PSSessionConfigurationFile` generates a GUID for the file.</span></span> <span data-ttu-id="4dd66-229">Geben Sie ein, um eine neue GUID in PowerShell zu erstellen `New-Guid` .</span><span class="sxs-lookup"><span data-stu-id="4dd66-229">To create a new GUID in PowerShell, type `New-Guid`.</span></span>

```yaml
Type: System.Guid
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="4dd66-230">-Languagemode</span><span class="sxs-lookup"><span data-stu-id="4dd66-230">-LanguageMode</span></span>

<span data-ttu-id="4dd66-231">Bestimmt, welche Elemente der PowerShell-Sprache in Sitzungen zulässig sind, die diese Sitzungs Konfiguration verwenden.</span><span class="sxs-lookup"><span data-stu-id="4dd66-231">Determines which elements of the PowerShell language are permitted in sessions that use this session configuration.</span></span> <span data-ttu-id="4dd66-232">Sie können diesen Parameter verwenden, um die Befehle einzuschränken, die bestimmte Benutzer auf dem Computer ausführen können.</span><span class="sxs-lookup"><span data-stu-id="4dd66-232">You can use this parameter to restrict the commands that particular users can run on the computer.</span></span>

<span data-ttu-id="4dd66-233">Zulässige Werte für diesen Parameter:</span><span class="sxs-lookup"><span data-stu-id="4dd66-233">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="4dd66-234">Fulllanguage: alle Sprachelemente sind zulässig.</span><span class="sxs-lookup"><span data-stu-id="4dd66-234">FullLanguage - All language elements are permitted.</span></span>
- <span data-ttu-id="4dd66-235">"Einschräninedlanguage": Befehle, die auszuwertende Skripts enthalten, sind nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="4dd66-235">ConstrainedLanguage - Commands that contain scripts to be evaluated are not allowed.</span></span> <span data-ttu-id="4dd66-236">Der ConstrainedLanguage-Modus schränkt den Benutzerzugriff auf Microsoft .NET Framework-Typen, -Objekte oder -Methoden ein.</span><span class="sxs-lookup"><span data-stu-id="4dd66-236">The ConstrainedLanguage mode restricts user access to Microsoft .NET Framework types, objects, or methods.</span></span>
- <span data-ttu-id="4dd66-237">Nolanguage: Benutzer können Cmdlets und Funktionen ausführen, dürfen jedoch keine Sprachelemente verwenden, wie z. b. Skriptblöcke, Variablen oder Operatoren.</span><span class="sxs-lookup"><span data-stu-id="4dd66-237">NoLanguage - Users may run cmdlets and functions, but are not permitted to use any language elements, such as script blocks, variables, or operators.</span></span>
- <span data-ttu-id="4dd66-238">Restrictedlanguage: Benutzer können Cmdlets und Funktionen ausführen, dürfen jedoch keine Skriptblöcke oder Variablen verwenden, mit Ausnahme der folgenden zulässigen Variablen: `$PSCulture` , `$PSUICulture` , `$True` , `$False` und `$Null` .</span><span class="sxs-lookup"><span data-stu-id="4dd66-238">RestrictedLanguage - Users may run cmdlets and functions, but are not permitted to use script blocks or variables except for the following permitted variables: `$PSCulture`, `$PSUICulture`, `$True`, `$False`, and `$Null`.</span></span> <span data-ttu-id="4dd66-239">Benutzer dürfen nur die grundlegenden Vergleichs Operatoren ( `-eq` , `-gt` ,) verwenden `-lt` .</span><span class="sxs-lookup"><span data-stu-id="4dd66-239">Users may use only the basic comparison operators (`-eq`, `-gt`, `-lt`).</span></span> <span data-ttu-id="4dd66-240">Zuweisungsanweisungen, Eigenschaftsverweise und Methodenaufrufe sind nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="4dd66-240">Assignment statements, property references, and method calls are not permitted.</span></span>

<span data-ttu-id="4dd66-241">Der Standardwert des **LanguageMode**-Parameters hängt vom Wert des **SessionType**-Parameters ab.</span><span class="sxs-lookup"><span data-stu-id="4dd66-241">The default value of the **LanguageMode** parameter depends on the value of the **SessionType** parameter.</span></span>

- <span data-ttu-id="4dd66-242">Empty-nolanguage</span><span class="sxs-lookup"><span data-stu-id="4dd66-242">Empty - NoLanguage</span></span>
- <span data-ttu-id="4dd66-243">Restrictedremuteserver-nolanguage</span><span class="sxs-lookup"><span data-stu-id="4dd66-243">RestrictedRemoteServer - NoLanguage</span></span>
- <span data-ttu-id="4dd66-244">Standard-fulllanguage</span><span class="sxs-lookup"><span data-stu-id="4dd66-244">Default - FullLanguage</span></span>

```yaml
Type: System.Management.Automation.PSLanguageMode
Parameter Sets: (All)
Aliases:
Accepted values: FullLanguage, RestrictedLanguage, NoLanguage, ConstrainedLanguage

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="4dd66-245">-Modulestoimport</span><span class="sxs-lookup"><span data-stu-id="4dd66-245">-ModulesToImport</span></span>

<span data-ttu-id="4dd66-246">Gibt die Module und Snap-ins an, die automatisch in Sitzungen importiert werden, die die Sitzungskonfiguration verwenden.</span><span class="sxs-lookup"><span data-stu-id="4dd66-246">Specifies the modules and snap-ins that are automatically imported into sessions that use the session configuration.</span></span>

<span data-ttu-id="4dd66-247">Standardmäßig wird nur das **Microsoft. PowerShell. Core** -Snap-in in Remote Sitzungen importiert, aber wenn die Cmdlets nicht ausgeschlossen sind, können Benutzer die `Import-Module` -und `Add-PSSnapin` -Cmdlets verwenden, um der Sitzung Module und Snap-Ins hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="4dd66-247">By default, only the **Microsoft.PowerShell.Core** snap-in is imported into remote sessions, but unless the cmdlets are excluded, users can use the `Import-Module` and `Add-PSSnapin` cmdlets to add modules and snap-ins to the session.</span></span>

<span data-ttu-id="4dd66-248">Jedes Modul oder Snap-In im Wert dieses Parameters kann durch eine Zeichenfolge oder als Hashtabelle dargestellt werden.</span><span class="sxs-lookup"><span data-stu-id="4dd66-248">Each module or snap-in in the value of this parameter can be represented by a string or as a hash table.</span></span> <span data-ttu-id="4dd66-249">Eine Modul Zeichenfolge besteht nur aus dem Namen des Moduls oder Snap-Ins.</span><span class="sxs-lookup"><span data-stu-id="4dd66-249">A module string consists only of the name of the module or snap-in.</span></span> <span data-ttu-id="4dd66-250">Eine Modul Hash Tabelle kann die Schlüssel " **ModuleName**", " **moduleversion**" und " **GUID** " enthalten.</span><span class="sxs-lookup"><span data-stu-id="4dd66-250">A module hash table can include **ModuleName**, **ModuleVersion**, and **GUID** keys.</span></span> <span data-ttu-id="4dd66-251">Nur der **ModuleName**-Schlüssel ist erforderlich.</span><span class="sxs-lookup"><span data-stu-id="4dd66-251">Only the **ModuleName** key is required.</span></span>

<span data-ttu-id="4dd66-252">Beispielsweise besteht der folgende Wert aus einer Zeichenfolge und einer Hashtabelle.</span><span class="sxs-lookup"><span data-stu-id="4dd66-252">For example, the following value consists of a string and a hash table.</span></span> <span data-ttu-id="4dd66-253">Jede Kombination aus Zeichenfolgen und Hashtabellen, in beliebiger Reihenfolge, ist gültig.</span><span class="sxs-lookup"><span data-stu-id="4dd66-253">Any combination of strings and hash tables, in any order, is valid.</span></span>

`'TroubleshootingPack', @{ModuleName='PSDiagnostics'; ModuleVersion='1.0.0.0';GUID='c61d6278-02a3-4618-ae37-a524d40a7f44'}`

<span data-ttu-id="4dd66-254">Der Wert des **modulestoimport** -Parameters des `Register-PSSessionConfiguration` Cmdlets hat Vorrang vor dem Wert des **modulestoimport** -Schlüssels in der Sitzungs Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="4dd66-254">The value of the **ModulesToImport** parameter of the `Register-PSSessionConfiguration` cmdlet takes precedence over the value of the **ModulesToImport** key in the session configuration file.</span></span>

```yaml
Type: System.Object[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="4dd66-255">-Mountuserdrive</span><span class="sxs-lookup"><span data-stu-id="4dd66-255">-MountUserDrive</span></span>

<span data-ttu-id="4dd66-256">Konfiguriert Sitzungen, die diese Sitzungs Konfiguration verwenden, um das `User:` PSDrive verfügbar zu machen.</span><span class="sxs-lookup"><span data-stu-id="4dd66-256">Configures sessions that use this session configuration to expose the `User:` PSDrive.</span></span> <span data-ttu-id="4dd66-257">Benutzer Laufwerke sind für jeden Benutzer, der eine Verbindung herstellt, eindeutig und ermöglichen Benutzern das Kopieren von Daten in und von PowerShell-Endpunkten, auch wenn der Datei System Anbieter nicht verfügbar gemacht wird.</span><span class="sxs-lookup"><span data-stu-id="4dd66-257">User drives are unique for each connecting user and allow users to copy data to and from PowerShell endpoints even if the File System provider is not exposed.</span></span> <span data-ttu-id="4dd66-258">Benutzer Laufwerk Stämme werden unter erstellt `$env:LOCALAPPDATA\Microsoft\Windows\PowerShell\DriveRoots\` .</span><span class="sxs-lookup"><span data-stu-id="4dd66-258">User drive roots are created under `$env:LOCALAPPDATA\Microsoft\Windows\PowerShell\DriveRoots\`.</span></span> <span data-ttu-id="4dd66-259">Für jeden Benutzer, der eine Verbindung zum Endpunkt herstellt, wird ein Ordner mit dem Namen `$env:USERDOMAIN_$env:USERNAME` erstellt.</span><span class="sxs-lookup"><span data-stu-id="4dd66-259">For each user connecting to the endpoint, a folder is created with the name `$env:USERDOMAIN_$env:USERNAME`.</span></span>

<span data-ttu-id="4dd66-260">Der Inhalt des Benutzer Laufwerks wird über Benutzersitzungen hinweg beibehalten und nicht automatisch entfernt.</span><span class="sxs-lookup"><span data-stu-id="4dd66-260">Contents in the user drive persist across user sessions and are not automatically removed.</span></span> <span data-ttu-id="4dd66-261">Standardmäßig können Benutzer nur bis zu 50 MB Daten auf dem Benutzer Laufwerk speichern.</span><span class="sxs-lookup"><span data-stu-id="4dd66-261">By default, users can only store up to 50MB of data in the user drive.</span></span> <span data-ttu-id="4dd66-262">Dies kann mit dem **userdrivemaximumsize** -Parameter angepasst werden.</span><span class="sxs-lookup"><span data-stu-id="4dd66-262">This can be customized with the **UserDriveMaximumSize** parameter.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="4dd66-263">-Path</span><span class="sxs-lookup"><span data-stu-id="4dd66-263">-Path</span></span>

<span data-ttu-id="4dd66-264">Gibt den Pfad und den Dateinamen der Sitzungs Konfigurationsdatei an.</span><span class="sxs-lookup"><span data-stu-id="4dd66-264">Specifies the path and filename of the session configuration file.</span></span> <span data-ttu-id="4dd66-265">Die Datei muss eine `.pssc` Dateinamenerweiterung aufweisen.</span><span class="sxs-lookup"><span data-stu-id="4dd66-265">The file must have a `.pssc` file name extension.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="4dd66-266">-PowerShellVersion</span><span class="sxs-lookup"><span data-stu-id="4dd66-266">-PowerShellVersion</span></span>

<span data-ttu-id="4dd66-267">Gibt die Version der PowerShell-Engine in Sitzungen an, die die Sitzungs Konfiguration verwenden.</span><span class="sxs-lookup"><span data-stu-id="4dd66-267">Specifies the version of the PowerShell engine in sessions that use the session configuration.</span></span> <span data-ttu-id="4dd66-268">Die zulässigen Werte für diesen Parameter sind: 2,0 und 3,0.</span><span class="sxs-lookup"><span data-stu-id="4dd66-268">The acceptable values for this parameter are: 2.0 and 3.0.</span></span> <span data-ttu-id="4dd66-269">Wenn Sie diesen Parameter weglassen, wird der **PowerShellVersion** -Schlüssel auskommentiert, und die neueste Version von PowerShell wird in der Sitzung ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="4dd66-269">If you omit this parameter, the **PowerShellVersion** key is commented-out and newest version of PowerShell runs in the session.</span></span>

<span data-ttu-id="4dd66-270">Der Wert des **psversion** -Parameters des `Register-PSSessionConfiguration` Cmdlets hat Vorrang vor dem Wert des **PowerShellVersion** -Schlüssels in der Sitzungs Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="4dd66-270">The value of the **PSVersion** parameter of the `Register-PSSessionConfiguration` cmdlet takes precedence over the value of the **PowerShellVersion** key in the session configuration file.</span></span>

```yaml
Type: System.Version
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="4dd66-271">-Requirements dgroups</span><span class="sxs-lookup"><span data-stu-id="4dd66-271">-RequiredGroups</span></span>

<span data-ttu-id="4dd66-272">Gibt bedingte Zugriffsregeln für Benutzer an, die eine Verbindung mit Sitzungen herstellen, die diese Sitzungs Konfiguration verwenden.</span><span class="sxs-lookup"><span data-stu-id="4dd66-272">Specifies conditional access rules for users connecting to sessions that use this session configuration.</span></span>

<span data-ttu-id="4dd66-273">Geben Sie eine Hash Tabelle ein, um die Liste der Regeln mithilfe von nur 1 Schlüssel pro Hash Tabelle, ' and ' oder ' or ', zu verfassen, und legen Sie den Wert auf ein Array von Sicherheitsgruppen Namen oder zusätzlichen Hash Tabellen fest.</span><span class="sxs-lookup"><span data-stu-id="4dd66-273">Enter a hashtable to compose your list of rules using only 1 key per hashtable, 'And' or 'Or', and set the value to an array of security group names or additional hashtables.</span></span>

<span data-ttu-id="4dd66-274">Beispiel für das Herstellen einer Verbindung von Benutzern mit Mitgliedern einer einzelnen Gruppe: `@{ And = 'MyRequiredGroup' }`</span><span class="sxs-lookup"><span data-stu-id="4dd66-274">Example requiring connecting users to be members of a single group: `@{ And = 'MyRequiredGroup' }`</span></span>

<span data-ttu-id="4dd66-275">Beispiel für den Zugriff auf den Endpunkt durch Benutzer, die der Gruppe a oder beiden Gruppen B und C angehören müssen: `@{ Or = 'GroupA', @{ And = 'GroupB', 'GroupC' } }`</span><span class="sxs-lookup"><span data-stu-id="4dd66-275">Example requiring users to belong to group A, or both groups B and C, to access the endpoint: `@{ Or = 'GroupA', @{ And = 'GroupB', 'GroupC' } }`</span></span>

```yaml
Type: System.Collections.IDictionary
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="4dd66-276">-Roledefinitions</span><span class="sxs-lookup"><span data-stu-id="4dd66-276">-RoleDefinitions</span></span>

<span data-ttu-id="4dd66-277">Gibt die Zuordnung zwischen Sicherheitsgruppen (oder Benutzern) und Rollen Funktionen an.</span><span class="sxs-lookup"><span data-stu-id="4dd66-277">Specifies the mapping between security groups (or users) and role capabilities.</span></span> <span data-ttu-id="4dd66-278">Benutzer erhalten Zugriff auf alle Rollen Funktionen, die für ihre Gruppenmitgliedschaft zum Zeitpunkt der Erstellung der Sitzung gelten.</span><span class="sxs-lookup"><span data-stu-id="4dd66-278">Users will be granted access to all role capabilities which apply to their group membership at the time the session is created.</span></span>

<span data-ttu-id="4dd66-279">Geben Sie eine Hash Tabelle ein, in der die Schlüssel der Name der Sicherheitsgruppe sind, und die Werte sind Hash Tabellen, die eine Liste der Rollen Funktionen enthalten, die der Sicherheitsgruppe zur Verfügung gestellt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="4dd66-279">Enter a hash table in which the keys are the name of the security group and the values are hash tables that contain a list of role capabilities that should be made available to the security group.</span></span>

<span data-ttu-id="4dd66-280">Beispiel: `@{'Contoso\Level 2 Helpdesk Users' = @{ RoleCapabilities = 'Maintenance', 'ADHelpDesk' }}`</span><span class="sxs-lookup"><span data-stu-id="4dd66-280">For example: `@{'Contoso\Level 2 Helpdesk Users' = @{ RoleCapabilities = 'Maintenance', 'ADHelpDesk' }}`</span></span>

```yaml
Type: System.Collections.IDictionary
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="4dd66-281">-Runasvirtualaccount</span><span class="sxs-lookup"><span data-stu-id="4dd66-281">-RunAsVirtualAccount</span></span>

<span data-ttu-id="4dd66-282">Konfiguriert Sitzungen, die diese Sitzungs Konfiguration verwenden, damit Sie als (virtuelles) Administrator Konto des Computers ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="4dd66-282">Configures sessions using this session configuration to be run as the computer's (virtual) administrator account.</span></span> <span data-ttu-id="4dd66-283">Dieses Feld kann nicht mit dem **groupmanagedserviceaccount** -Parameter verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="4dd66-283">This field cannot be used with the **GroupManagedServiceAccount** parameter.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="4dd66-284">-Runasvirtualaccountgroups</span><span class="sxs-lookup"><span data-stu-id="4dd66-284">-RunAsVirtualAccountGroups</span></span>

<span data-ttu-id="4dd66-285">Gibt die Sicherheitsgruppen an, die dem virtuellen Konto zugeordnet werden sollen, wenn eine Sitzung, die die Sitzungs Konfiguration verwendet, als virtuelles Konto ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="4dd66-285">Specifies the security groups to be associated with the virtual account when a session that uses the session configuration is run as a virtual account.</span></span> <span data-ttu-id="4dd66-286">Wenn die Angabe weggelassen wird, gehört das virtuelle Konto Domänen Administratoren auf Domänen Controllern und Administratoren auf allen anderen Computern an.</span><span class="sxs-lookup"><span data-stu-id="4dd66-286">If omitted, the virtual account belongs to Domain Admins on domain controllers and Administrators on all other computers.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="4dd66-287">-Schemaversion</span><span class="sxs-lookup"><span data-stu-id="4dd66-287">-SchemaVersion</span></span>

<span data-ttu-id="4dd66-288">Gibt die Version des Sitzungskonfigurationsdateischemas an.</span><span class="sxs-lookup"><span data-stu-id="4dd66-288">Specifies the version of the session configuration file schema.</span></span> <span data-ttu-id="4dd66-289">Der Standardwert ist „1.0.0.0“.</span><span class="sxs-lookup"><span data-stu-id="4dd66-289">The default value is "1.0.0.0".</span></span>

```yaml
Type: System.Version
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="4dd66-290">-Scriptstoprocess</span><span class="sxs-lookup"><span data-stu-id="4dd66-290">-ScriptsToProcess</span></span>

<span data-ttu-id="4dd66-291">Fügt den Sitzungen, die die Sitzungskonfiguration verwenden, die angegebenen Skripts hinzu.</span><span class="sxs-lookup"><span data-stu-id="4dd66-291">Adds the specified scripts to sessions that use the session configuration.</span></span> <span data-ttu-id="4dd66-292">Geben Sie den Pfad und die Dateinamen der Skripts ein.</span><span class="sxs-lookup"><span data-stu-id="4dd66-292">Enter the path and file names of the scripts.</span></span> <span data-ttu-id="4dd66-293">Der Wert dieses Parameters muss ein vollständiger oder absoluter Pfad von Skript Dateinamen sein.</span><span class="sxs-lookup"><span data-stu-id="4dd66-293">The value of this parameter must be a full or absolute path of script file names.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="4dd66-294">-SessionType</span><span class="sxs-lookup"><span data-stu-id="4dd66-294">-SessionType</span></span>

<span data-ttu-id="4dd66-295">Gibt den Typ der Sitzung an, die mit der Sitzungskonfiguration erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="4dd66-295">Specifies the type of session that is created by using the session configuration.</span></span> <span data-ttu-id="4dd66-296">Der Standardwert ist Default.</span><span class="sxs-lookup"><span data-stu-id="4dd66-296">The default value is Default.</span></span> <span data-ttu-id="4dd66-297">Zulässige Werte für diesen Parameter:</span><span class="sxs-lookup"><span data-stu-id="4dd66-297">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="4dd66-298">Leer: der Sitzung werden standardmäßig keine Module hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="4dd66-298">Empty - No modules are added to session by default.</span></span> <span data-ttu-id="4dd66-299">Verwenden Sie die Parameter dieses Cmdlets, um der Sitzung Module, Funktionen, Skripts und andere Funktionen hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="4dd66-299">Use the parameters of this cmdlet to add modules, functions, scripts, and other features to the session.</span></span> <span data-ttu-id="4dd66-300">Mit dieser Option können Sie benutzerdefinierte Sitzungen erstellen, indem Sie ausgewählte Befehle hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="4dd66-300">This option is designed for you to create custom sessions by adding selected commands.</span></span> <span data-ttu-id="4dd66-301">Wenn Sie einer leeren Sitzung keine Befehle hinzufügen, ist die Sitzung auf Ausdrücke beschränkt und kann womöglich nicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="4dd66-301">If you do not add commands to an empty session, the session is limited to expressions and might not be usable.</span></span>
- <span data-ttu-id="4dd66-302">Standard: Fügt der Sitzung das Microsoft. PowerShell. Core-Modul hinzu.</span><span class="sxs-lookup"><span data-stu-id="4dd66-302">Default - Adds the Microsoft.PowerShell.Core module to the session.</span></span> <span data-ttu-id="4dd66-303">Dieses Modul enthält das `Import-Module` Cmdlet, mit dem Benutzer andere Module importieren können, sofern Sie dieses Cmdlet nicht explizit verbieten.</span><span class="sxs-lookup"><span data-stu-id="4dd66-303">This module includes the `Import-Module` cmdlet that users can use to import other modules unless you explicitly prohibit this cmdlet.</span></span>
- <span data-ttu-id="4dd66-304">RestrictedRemoteServer.</span><span class="sxs-lookup"><span data-stu-id="4dd66-304">RestrictedRemoteServer.</span></span> <span data-ttu-id="4dd66-305">Schließt nur die folgenden Proxy Funktionen ein: `Exit-PSSession` , `Get-Command` , `Get-FormatData` , `Get-Help` , `Measure-Object` , `Out-Default` und `Select-Object` .</span><span class="sxs-lookup"><span data-stu-id="4dd66-305">Includes only the following proxy functions: `Exit-PSSession`, `Get-Command`, `Get-FormatData`, `Get-Help`, `Measure-Object`, `Out-Default`, and `Select-Object`.</span></span>
  <span data-ttu-id="4dd66-306">Verwenden Sie die Parameter dieses Cmdlets, um der Sitzung Module, Funktionen, Skripts und andere Funktionen hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="4dd66-306">Use the parameters of this cmdlet to add modules, functions, scripts, and other features to the session.</span></span>

```yaml
Type: System.Management.Automation.Remoting.SessionType
Parameter Sets: (All)
Aliases:
Accepted values: Empty, RestrictedRemoteServer, Default

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="4dd66-307">-Transcriptdirectory</span><span class="sxs-lookup"><span data-stu-id="4dd66-307">-TranscriptDirectory</span></span>

<span data-ttu-id="4dd66-308">Gibt das Verzeichnis an, in dem Sitzungsprotokolle für Sitzungen mit dieser Sitzungs Konfiguration platziert werden.</span><span class="sxs-lookup"><span data-stu-id="4dd66-308">Specifies the directory to place session transcripts for sessions using this session configuration.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="4dd66-309">-Typestoprocess</span><span class="sxs-lookup"><span data-stu-id="4dd66-309">-TypesToProcess</span></span>

<span data-ttu-id="4dd66-310">Fügt den `.ps1xml` Sitzungen, die die Sitzungs Konfiguration verwenden, die angegebenen Typdateien hinzu.</span><span class="sxs-lookup"><span data-stu-id="4dd66-310">Adds the specified `.ps1xml` type files to sessions that use the session configuration.</span></span> <span data-ttu-id="4dd66-311">Geben Sie die typdateinamen ein.</span><span class="sxs-lookup"><span data-stu-id="4dd66-311">Enter the type filenames.</span></span> <span data-ttu-id="4dd66-312">Der Wert dieses Parameters muss ein vollständiger oder absoluter Pfad zu den typdateinamen sein.</span><span class="sxs-lookup"><span data-stu-id="4dd66-312">The value of this parameter must be a full or absolute path to type filenames.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="4dd66-313">-Userdrivemaximumsize</span><span class="sxs-lookup"><span data-stu-id="4dd66-313">-UserDriveMaximumSize</span></span>

<span data-ttu-id="4dd66-314">Gibt die maximale Größe für Benutzer Laufwerke an, die in Sitzungen verfügbar gemacht werden, die diese Sitzungs Konfiguration verwenden.</span><span class="sxs-lookup"><span data-stu-id="4dd66-314">Specifies the maximum size for user drives exposed in sessions that use this session configuration.</span></span>
<span data-ttu-id="4dd66-315">Wenn der Wert weggelassen wird, beträgt die Standardgröße der einzelnen `User:` Laufwerk Stamm 50 MB.</span><span class="sxs-lookup"><span data-stu-id="4dd66-315">When omitted, the default size of each `User:` drive root is 50MB.</span></span>

<span data-ttu-id="4dd66-316">Dieser Parameter sollte mit **mountuserdrive** verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="4dd66-316">This parameter should be used with **MountUserDrive**.</span></span>

```yaml
Type: System.Int64
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="4dd66-317">-Variabledefinitionen</span><span class="sxs-lookup"><span data-stu-id="4dd66-317">-VariableDefinitions</span></span>

<span data-ttu-id="4dd66-318">Fügt den Sitzungen, die die Sitzungskonfiguration verwenden, die angegebenen Variablen hinzu.</span><span class="sxs-lookup"><span data-stu-id="4dd66-318">Adds the specified variables to sessions that use the session configuration.</span></span> <span data-ttu-id="4dd66-319">Geben Sie eine Hashtabelle mit den folgenden Schlüsseln ein:</span><span class="sxs-lookup"><span data-stu-id="4dd66-319">Enter a hash table with the following keys:</span></span>

- <span data-ttu-id="4dd66-320">Name: der Name der Variablen.</span><span class="sxs-lookup"><span data-stu-id="4dd66-320">Name - Name of the variable.</span></span> <span data-ttu-id="4dd66-321">Dieser Schlüssel ist erforderlich.</span><span class="sxs-lookup"><span data-stu-id="4dd66-321">This key is required.</span></span>
- <span data-ttu-id="4dd66-322">Wert-Variablen Wert.</span><span class="sxs-lookup"><span data-stu-id="4dd66-322">Value - Variable value.</span></span> <span data-ttu-id="4dd66-323">Dieser Schlüssel ist erforderlich.</span><span class="sxs-lookup"><span data-stu-id="4dd66-323">This key is required.</span></span>
- <span data-ttu-id="4dd66-324">Optionen: Variablen Optionen.</span><span class="sxs-lookup"><span data-stu-id="4dd66-324">Options - Variable options.</span></span> <span data-ttu-id="4dd66-325">Dieser Schlüssel ist optional.</span><span class="sxs-lookup"><span data-stu-id="4dd66-325">This key is optional.</span></span> <span data-ttu-id="4dd66-326">Der Standardwert ist " **None**".</span><span class="sxs-lookup"><span data-stu-id="4dd66-326">The default value is **None**.</span></span> <span data-ttu-id="4dd66-327">Die zulässigen Werte für diesen Parameter lauten: None, Read Only, Constant, private oder allscope.</span><span class="sxs-lookup"><span data-stu-id="4dd66-327">The acceptable values for this parameter are: None, ReadOnly, Constant, Private, or AllScope.</span></span>

<span data-ttu-id="4dd66-328">Beispiel: `@{Name='WarningPreference';Value='SilentlyContinue';Options='AllScope'}`</span><span class="sxs-lookup"><span data-stu-id="4dd66-328">For example: `@{Name='WarningPreference';Value='SilentlyContinue';Options='AllScope'}`</span></span>

```yaml
Type: System.Object
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="4dd66-329">-Visiblealiases</span><span class="sxs-lookup"><span data-stu-id="4dd66-329">-VisibleAliases</span></span>

<span data-ttu-id="4dd66-330">Beschränkt die Aliase in der Sitzung auf jene, die im Wert dieses Parameters angegeben wurden, sowie auf alle Aliase, die Sie im **AliasDefinition**-Parameter definieren.</span><span class="sxs-lookup"><span data-stu-id="4dd66-330">Limits the aliases in the session to those specified in the value of this parameter, plus any aliases that you define in the **AliasDefinition** parameter.</span></span> <span data-ttu-id="4dd66-331">Platzhalterzeichen werden unterstützt.</span><span class="sxs-lookup"><span data-stu-id="4dd66-331">Wildcard characters are supported.</span></span> <span data-ttu-id="4dd66-332">Standardmäßig sind alle Aliase, die von der PowerShell-Engine definiert werden, und alle Aliase, die von Modulen exportiert werden, in der Sitzung sichtbar.</span><span class="sxs-lookup"><span data-stu-id="4dd66-332">By default, all aliases that are defined by the PowerShell engine and all aliases that modules export are visible in the session.</span></span>

<span data-ttu-id="4dd66-333">Beispiel: `VisibleAliases='gcm', 'gp'`</span><span class="sxs-lookup"><span data-stu-id="4dd66-333">For example: `VisibleAliases='gcm', 'gp'`</span></span>

<span data-ttu-id="4dd66-334">Wenn ein beliebiger **sichtbarer** Parameter in der Sitzungs Konfigurationsdatei enthalten ist, entfernt PowerShell das `Import-Module` Cmdlet und den zugehörigen ipmo-Alias aus der Sitzung.</span><span class="sxs-lookup"><span data-stu-id="4dd66-334">When any **Visible** parameter is included in the session configuration file, PowerShell removes the `Import-Module` cmdlet and its ipmo alias from the session.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="4dd66-335">-Visiblecmdlets</span><span class="sxs-lookup"><span data-stu-id="4dd66-335">-VisibleCmdlets</span></span>

<span data-ttu-id="4dd66-336">Beschränkt die Cmdlets in der Sitzung auf jene, die im Wert dieses Parameters angegeben wurden.</span><span class="sxs-lookup"><span data-stu-id="4dd66-336">Limits the cmdlets in the session to those specified in the value of this parameter.</span></span> <span data-ttu-id="4dd66-337">Platzhalter Zeichen und qualifizierte Modulnamen werden unterstützt.</span><span class="sxs-lookup"><span data-stu-id="4dd66-337">Wildcard characters and Module Qualified Names are supported.</span></span>

<span data-ttu-id="4dd66-338">Standardmäßig sind alle Cmdlets, die von Modulen in der Sitzung exportiert werden, in der Sitzung sichtbar.</span><span class="sxs-lookup"><span data-stu-id="4dd66-338">By default, all cmdlets that modules in the session export are visible in the session.</span></span> <span data-ttu-id="4dd66-339">Verwenden Sie die **SessionType**- und **ModulesToImport**-Parameter, um zu bestimmen, welche Module und Snap-Ins in die Sitzung importiert werden.</span><span class="sxs-lookup"><span data-stu-id="4dd66-339">Use the **SessionType** and **ModulesToImport** parameters to determine which modules and snap-ins are imported into the session.</span></span> <span data-ttu-id="4dd66-340">Wenn das Cmdlet in **modulestoimport** nicht verfügbar ist, versucht das entsprechende Modul, das Cmdlet zu veröffentlichen.</span><span class="sxs-lookup"><span data-stu-id="4dd66-340">If no modules in **ModulesToImport** expose the cmdlet, the appropriate module will attempt to be autoloaded.</span></span>

<span data-ttu-id="4dd66-341">Wenn ein beliebiger **sichtbarer** Parameter in der Sitzungs Konfigurationsdatei enthalten ist, entfernt PowerShell das `Import-Module` Cmdlet und den zugehörigen ipmo-Alias aus der Sitzung.</span><span class="sxs-lookup"><span data-stu-id="4dd66-341">When any **Visible** parameter is included in the session configuration file, PowerShell removes the `Import-Module` cmdlet and its ipmo alias from the session.</span></span>

```yaml
Type: System.Object[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="4dd66-342">-Visibleexternalcommands</span><span class="sxs-lookup"><span data-stu-id="4dd66-342">-VisibleExternalCommands</span></span>

<span data-ttu-id="4dd66-343">Schränkt die externen Binärdateien, Skripts und Befehle, die in der Sitzung ausgeführt werden können, auf die Werte ein, die im Wert dieses Parameters angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="4dd66-343">Limits the external binaries, scripts, and commands that can be executed in the session to those specified in the value of this parameter.</span></span> <span data-ttu-id="4dd66-344">Platzhalterzeichen werden unterstützt.</span><span class="sxs-lookup"><span data-stu-id="4dd66-344">Wildcard characters are supported.</span></span>

<span data-ttu-id="4dd66-345">Standardmäßig sind keine externen Befehle in der Sitzung sichtbar.</span><span class="sxs-lookup"><span data-stu-id="4dd66-345">By default, no external commands are visible in the session.</span></span>

<span data-ttu-id="4dd66-346">Wenn ein beliebiger **sichtbarer** Parameter in der Sitzungs Konfigurationsdatei enthalten ist, entfernt PowerShell das `Import-Module` Cmdlet und den zugehörigen ipmo-Alias aus der Sitzung.</span><span class="sxs-lookup"><span data-stu-id="4dd66-346">When any **Visible** parameter is included in the session configuration file, PowerShell, removes the `Import-Module` cmdlet and its ipmo alias from the session.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="4dd66-347">-Visiblefunctions</span><span class="sxs-lookup"><span data-stu-id="4dd66-347">-VisibleFunctions</span></span>

<span data-ttu-id="4dd66-348">Beschränkt die Funktionen in der Sitzung auf jene, die im Wert dieses Parameters angegeben wurden, sowie auf alle Funktionen, die Sie im **FunctionDefinition**-Parameter definieren.</span><span class="sxs-lookup"><span data-stu-id="4dd66-348">Limits the functions in the session to those specified in the value of this parameter, plus any functions that you define in the **FunctionDefinition** parameter.</span></span> <span data-ttu-id="4dd66-349">Platzhalterzeichen werden unterstützt.</span><span class="sxs-lookup"><span data-stu-id="4dd66-349">Wildcard characters are supported.</span></span>

<span data-ttu-id="4dd66-350">Standardmäßig sind alle Funktionen, die von Modulen in der Sitzung exportiert werden, in der Sitzung sichtbar.</span><span class="sxs-lookup"><span data-stu-id="4dd66-350">By default, all functions that modules in the session export are visible in the session.</span></span> <span data-ttu-id="4dd66-351">Verwenden Sie die **SessionType**- und **ModulesToImport**-Parameter, um zu bestimmen, welche Module und Snap-Ins in die Sitzung importiert werden.</span><span class="sxs-lookup"><span data-stu-id="4dd66-351">Use the **SessionType** and **ModulesToImport** parameters to determine which modules and snap-ins are imported into the session.</span></span>

<span data-ttu-id="4dd66-352">Wenn ein beliebiger **sichtbarer** Parameter in der Sitzungs Konfigurationsdatei enthalten ist, entfernt PowerShell das `Import-Module` Cmdlet und den zugehörigen ipmo-Alias aus der Sitzung.</span><span class="sxs-lookup"><span data-stu-id="4dd66-352">When any **Visible** parameter is included in the session configuration file, PowerShell removes the `Import-Module` cmdlet and its ipmo alias from the session.</span></span>

```yaml
Type: System.Object[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="4dd66-353">-Visibleproviders</span><span class="sxs-lookup"><span data-stu-id="4dd66-353">-VisibleProviders</span></span>

<span data-ttu-id="4dd66-354">Schränkt die PowerShell-Anbieter in der Sitzung auf die Werte ein, die im Wert dieses Parameters angegeben sind.</span><span class="sxs-lookup"><span data-stu-id="4dd66-354">Limits the PowerShell providers in the session to those specified in the value of this parameter.</span></span>
<span data-ttu-id="4dd66-355">Platzhalterzeichen werden unterstützt.</span><span class="sxs-lookup"><span data-stu-id="4dd66-355">Wildcard characters are supported.</span></span>

<span data-ttu-id="4dd66-356">Standardmäßig sind alle Anbieter, die von Modulen in der Sitzung exportiert werden, in der Sitzung sichtbar.</span><span class="sxs-lookup"><span data-stu-id="4dd66-356">By default, all providers that modules in the session export are visible in the session.</span></span> <span data-ttu-id="4dd66-357">Verwenden Sie die Parameter **SessionType** und **modulestoimport** , um zu bestimmen, welche Module in die Sitzung importiert werden.</span><span class="sxs-lookup"><span data-stu-id="4dd66-357">Use the **SessionType** and **ModulesToImport** parameters to determine which modules are imported into the session.</span></span>

<span data-ttu-id="4dd66-358">Wenn ein beliebiger **sichtbarer** Parameter in der Sitzungs Konfigurationsdatei enthalten ist, entfernt PowerShell das `Import-Module` Cmdlet und den zugehörigen `ipmo` Alias aus der Sitzung.</span><span class="sxs-lookup"><span data-stu-id="4dd66-358">When any **Visible** parameter is included in the session configuration file, PowerShell removes the `Import-Module` cmdlet and its `ipmo` alias from the session.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: True
```

### <span data-ttu-id="4dd66-359">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="4dd66-359">CommonParameters</span></span>

<span data-ttu-id="4dd66-360">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="4dd66-360">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="4dd66-361">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="4dd66-361">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="4dd66-362">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="4dd66-362">INPUTS</span></span>

### <span data-ttu-id="4dd66-363">Keine</span><span class="sxs-lookup"><span data-stu-id="4dd66-363">None</span></span>

<span data-ttu-id="4dd66-364">Sie können keine Objekte über die Pipeline an dieses Cmdlet übergeben.</span><span class="sxs-lookup"><span data-stu-id="4dd66-364">You cannot pipe any objects to this cmdlet.</span></span>

## <span data-ttu-id="4dd66-365">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="4dd66-365">OUTPUTS</span></span>

### <span data-ttu-id="4dd66-366">Keine</span><span class="sxs-lookup"><span data-stu-id="4dd66-366">None</span></span>

<span data-ttu-id="4dd66-367">Dieses Cmdlet generiert keine Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="4dd66-367">This cmdlet does not generate any output.</span></span>

## <span data-ttu-id="4dd66-368">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="4dd66-368">NOTES</span></span>

<span data-ttu-id="4dd66-369">Dieses Cmdlet ist nur auf Windows-Plattformen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="4dd66-369">This cmdlet is only available on Windows platforms.</span></span>

- <span data-ttu-id="4dd66-370">Parameter, wie z. **b. visiblecmdlets** und **visibleproviders**, importieren keine Elemente in die Sitzung.</span><span class="sxs-lookup"><span data-stu-id="4dd66-370">Parameters, such as **VisibleCmdlets** and **VisibleProviders**, do not import items into the session.</span></span> <span data-ttu-id="4dd66-371">Stattdessen treffen sie ihre Auswahl unter den Elementen, die in die Sitzung importiert wurden.</span><span class="sxs-lookup"><span data-stu-id="4dd66-371">Instead, they select from among the items imported into the session.</span></span> <span data-ttu-id="4dd66-372">Wenn z. b. der Wert des **visibleproviders** -Parameters der Zertifikat Anbieter ist, der **modulestoimport** -Parameter jedoch nicht das **Microsoft. PowerShell. Security** -Modul angibt, das den Zertifikat Anbieter enthält, ist der Zertifikat Anbieter in der Sitzung nicht sichtbar.</span><span class="sxs-lookup"><span data-stu-id="4dd66-372">For example, if the value of the **VisibleProviders** parameter is the Certificate provider, but the **ModulesToImport** parameter does not specify the **Microsoft.PowerShell.Security** module that contains the Certificate provider, the Certificate provider is not visible in the session.</span></span>
- <span data-ttu-id="4dd66-373">`New-PSSessionConfigurationFile` erstellt eine Sitzungs Konfigurationsdatei mit der Dateinamenerweiterung. PSSC in dem Pfad, den Sie im **path** -Parameter angeben.</span><span class="sxs-lookup"><span data-stu-id="4dd66-373">`New-PSSessionConfigurationFile` creates a session configuration file that has a .pssc file name extension in the path that you specify in the **Path** parameter.</span></span> <span data-ttu-id="4dd66-374">Wenn Sie die Sitzungs Konfigurationsdatei verwenden, um eine Sitzungs Konfiguration zu erstellen, `Register-PSSessionConfiguration` kopiert das Cmdlet die Konfigurationsdatei und speichert eine aktive Kopie der Datei im Unterverzeichnis **sessionconfig** des `$PSHOME` Verzeichnisses.</span><span class="sxs-lookup"><span data-stu-id="4dd66-374">When you use the session configuration file to create a session configuration, the `Register-PSSessionConfiguration` cmdlet copies the configuration file and saves an active copy of the file in the **SessionConfig** subdirectory of the `$PSHOME` directory.</span></span>

  <span data-ttu-id="4dd66-375">Die **configfilepath** -Eigenschaft der Sitzungs Konfiguration enthält den voll qualifizierten Pfad der aktiven Sitzungs Konfigurationsdatei.</span><span class="sxs-lookup"><span data-stu-id="4dd66-375">The **ConfigFilePath** property of the session configuration contains the fully qualified path of the active session configuration file.</span></span> <span data-ttu-id="4dd66-376">Sie können die aktive Konfigurationsdatei im Verzeichnis jederzeit `$PSHOME` mithilfe eines beliebigen Text-Editors ändern.</span><span class="sxs-lookup"><span data-stu-id="4dd66-376">You can modify the active configuration file in the `$PSHOME` directory at any time using any text editor.</span></span> <span data-ttu-id="4dd66-377">Die Änderungen, die Sie vornehmen, betreffen alle neuen Sitzungen, die diese Sitzungskonfiguration verwenden, aber nicht bereits vorhandene Sitzungen.</span><span class="sxs-lookup"><span data-stu-id="4dd66-377">The changes that you make affect all new sessions that use the session configuration, but not existing sessions.</span></span>

  <span data-ttu-id="4dd66-378">Vor der Verwendung einer bearbeiteten Sitzungs Konfigurationsdatei können `Test-PSSessionConfigurationFile` Sie mit dem Cmdlet überprüfen, ob die Einträge in der Konfigurationsdatei gültig sind.</span><span class="sxs-lookup"><span data-stu-id="4dd66-378">Before using an edited session configuration file, use the `Test-PSSessionConfigurationFile` cmdlet to verify that the configuration file entries are valid.</span></span>

## <span data-ttu-id="4dd66-379">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="4dd66-379">RELATED LINKS</span></span>

[<span data-ttu-id="4dd66-380">Disable-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="4dd66-380">Disable-PSSessionConfiguration</span></span>](Disable-PSSessionConfiguration.md)

[<span data-ttu-id="4dd66-381">Enable-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="4dd66-381">Enable-PSSessionConfiguration</span></span>](Enable-PSSessionConfiguration.md)

[<span data-ttu-id="4dd66-382">Get-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="4dd66-382">Get-PSSessionConfiguration</span></span>](Get-PSSessionConfiguration.md)

[<span data-ttu-id="4dd66-383">Register-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="4dd66-383">Register-PSSessionConfiguration</span></span>](Register-PSSessionConfiguration.md)

[<span data-ttu-id="4dd66-384">Set-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="4dd66-384">Set-PSSessionConfiguration</span></span>](Set-PSSessionConfiguration.md)

[<span data-ttu-id="4dd66-385">Test-PSSessionConfigurationFile</span><span class="sxs-lookup"><span data-stu-id="4dd66-385">Test-PSSessionConfigurationFile</span></span>](Test-PSSessionConfigurationFile.md)

[<span data-ttu-id="4dd66-386">Unregister-PSSessionConfiguration</span><span class="sxs-lookup"><span data-stu-id="4dd66-386">Unregister-PSSessionConfiguration</span></span>](Unregister-PSSessionConfiguration.md)

[<span data-ttu-id="4dd66-387">WSMan-Anbieter</span><span class="sxs-lookup"><span data-stu-id="4dd66-387">WSMan Provider</span></span>](../Microsoft.WsMan.Management/About/about_WSMan_Provider.md)

[<span data-ttu-id="4dd66-388">about_Session_Configurations</span><span class="sxs-lookup"><span data-stu-id="4dd66-388">about_Session_Configurations</span></span>](About/about_Session_Configurations.md)

[<span data-ttu-id="4dd66-389">about_Session_Configuration_Files</span><span class="sxs-lookup"><span data-stu-id="4dd66-389">about_Session_Configuration_Files</span></span>](About/about_Session_Configuration_Files.md)