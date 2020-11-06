---
ms.date: 06/12/2017
keywords: DSC,PowerShell,Konfiguration,Setup,Einrichtung
title: Optionen für Anmeldeinformationen in den Konfigurationsdaten
description: DSC ermöglicht Ihnen, Anmeldeinformationen zur Verfügung zu stellen, sodass Konfigurationseinstellungen im Kontext eines bestimmten Benutzerkontos und nicht des lokalen Systemkontos angewendet werden können.
ms.openlocfilehash: 41478dc042ca59fb70aa033de81b589a4a8c09c7
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92658644"
---
# <a name="credentials-options-in-configuration-data"></a><span data-ttu-id="63554-104">Optionen für Anmeldeinformationen in den Konfigurationsdaten</span><span class="sxs-lookup"><span data-stu-id="63554-104">Credentials Options in Configuration Data</span></span>

> <span data-ttu-id="63554-105">Gilt für: Windows PowerShell 5.0</span><span class="sxs-lookup"><span data-stu-id="63554-105">Applies To: Windows PowerShell 5.0</span></span>

## <a name="plain-text-passwords-and-domain-users"></a><span data-ttu-id="63554-106">Nur-Text-Kennwörter und Domänenbenutzer</span><span class="sxs-lookup"><span data-stu-id="63554-106">Plain Text Passwords and Domain Users</span></span>

<span data-ttu-id="63554-107">DSC-Konfigurationen mit unverschlüsselten Anmeldeinformationen generieren eine Fehlermeldung zu Nur-Text-Kennwörtern.</span><span class="sxs-lookup"><span data-stu-id="63554-107">DSC configurations containing a credential without encryption will generate an error message about plain text passwords.</span></span> <span data-ttu-id="63554-108">DSC generiert außerdem bei Verwendung von Domänenanmeldeinformationen eine Warnung.</span><span class="sxs-lookup"><span data-stu-id="63554-108">Also, DSC will generate a warning when using domain credentials.</span></span> <span data-ttu-id="63554-109">Um diese Fehler- und Warnmeldungen zu unterdrücken, verwenden Sie die DSC-Konfigurationsdaten-Schlüsselwörter.</span><span class="sxs-lookup"><span data-stu-id="63554-109">To suppress these error and warning messages use the DSC configuration data keywords:</span></span>

- <span data-ttu-id="63554-110">**PsDscAllowPlainTextPassword**</span><span class="sxs-lookup"><span data-stu-id="63554-110">**PsDscAllowPlainTextPassword**</span></span>
- <span data-ttu-id="63554-111">**PsDscAllowDomainUser**</span><span class="sxs-lookup"><span data-stu-id="63554-111">**PsDscAllowDomainUser**</span></span>

> [!NOTE]
> <span data-ttu-id="63554-112">Das Speichern/Übertragen von unverschlüsselten Nur-Text-Kennwörtern ist in der Regel nicht sicher.</span><span class="sxs-lookup"><span data-stu-id="63554-112">Storing/transmitting plaintext passwords unencrypted is generally not secure.</span></span> <span data-ttu-id="63554-113">Das Sichern von Anmeldeinformationen mithilfe der weiter unten in diesem Thema behandelten Verfahren wird empfohlen.</span><span class="sxs-lookup"><span data-stu-id="63554-113">Securing credentials by using the techniques covered later in this topic is recommended.</span></span> <span data-ttu-id="63554-114">Der Azure Automation DSC-Dienst erlaubt Ihnen, Ihre Anmeldeinformationen zentral zu verwalten, um sie in Konfigurationen zu kompilieren und sicher zu speichern.</span><span class="sxs-lookup"><span data-stu-id="63554-114">The Azure Automation DSC service allows you to centrally manage credentials to be compiled in configurations and stored securely.</span></span> <span data-ttu-id="63554-115">Informationen finden Sie unter: [Compiling DSC Configurations / Credential Assets (Kompilieren von DSC-Konfigurationen/Anmeldeinformationsassets)](/azure/automation/automation-dsc-compile#credential-assets)</span><span class="sxs-lookup"><span data-stu-id="63554-115">For information, see: [Compiling DSC Configurations / Credential Assets](/azure/automation/automation-dsc-compile#credential-assets)</span></span>

## <a name="handling-credentials-in-dsc"></a><span data-ttu-id="63554-116">Behandeln von Anmeldeinformationen in DSC</span><span class="sxs-lookup"><span data-stu-id="63554-116">Handling Credentials in DSC</span></span>

<span data-ttu-id="63554-117">DSC-Konfigurationsressourcen werden standardmäßig als `Local System` ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="63554-117">DSC configuration resources run as `Local System` by default.</span></span> <span data-ttu-id="63554-118">Einige Ressourcen benötigen jedoch Anmeldeinformationen, z. B. wenn die `Package`-Ressource Software unter einem bestimmten Benutzerkonto installieren muss.</span><span class="sxs-lookup"><span data-stu-id="63554-118">However, some resources need a credential, for example when the `Package` resource needs to install software under a specific user account.</span></span>

<span data-ttu-id="63554-119">Frühere Ressourcen verwendeten in diesem Fall einen hartcodierten `Credential`-Eigenschaftennamen.</span><span class="sxs-lookup"><span data-stu-id="63554-119">Earlier resources used a hard-coded `Credential` property name to handle this.</span></span> <span data-ttu-id="63554-120">In WMF 5.0 wurde eine automatische `PsDscRunAsCredential`-Eigenschaft für alle Ressourcen hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="63554-120">WMF 5.0 added an automatic `PsDscRunAsCredential` property for all resources.</span></span> <span data-ttu-id="63554-121">Weitere Informationen zur Verwendung von `PsDscRunAsCredential`, finden Sie unter [Ausführen von DSC mit Benutzeranmeldeinformationen](runAsUser.md).</span><span class="sxs-lookup"><span data-stu-id="63554-121">For information about using `PsDscRunAsCredential`, see [Running DSC with user credentials](runAsUser.md).</span></span> <span data-ttu-id="63554-122">Neuere und benutzerdefinierte Ressourcen können diese automatische Eigenschaft verwenden, anstatt eine eigene Eigenschaften für Anmeldeinformationen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="63554-122">Newer resources and custom resources can use this automatic property instead of creating their own property for credentials.</span></span>

> [!NOTE]
> <span data-ttu-id="63554-123">Das Design einiger Ressourcen wurde so angelegt, dass sie aus einem bestimmten Grund mehrere Sätze von Anmeldeinformationen verwenden und über eigene Eigenschaften für Anmeldeinformationen verfügen.</span><span class="sxs-lookup"><span data-stu-id="63554-123">The design of some resources are to use multiple credentials for a specific reason, and they will have their own credential properties.</span></span>

<span data-ttu-id="63554-124">Um die verfügbaren Eigenschaften für Anmeldeinformationen für eine Ressource zu finden, verwenden Sie entweder `Get-DscResource -Name ResourceName -Syntax` oder Intellisense in der ISE (`CTRL+SPACE`).</span><span class="sxs-lookup"><span data-stu-id="63554-124">To find the available credential properties on a resource use either `Get-DscResource -Name ResourceName -Syntax` or the Intellisense in the ISE (`CTRL+SPACE`).</span></span>

```powershell
Get-DscResource -Name Group -Syntax
```

```Output
Group [String] #ResourceName
{
    GroupName = [string]
    [Credential = [PSCredential]]
    [DependsOn = [string[]]]
    [Description = [string]]
    [Ensure = [string]{ Absent | Present }]
    [Members = [string[]]]
    [MembersToExclude = [string[]]]
    [MembersToInclude = [string[]]]
    [PsDscRunAsCredential = [PSCredential]]
}
```

<span data-ttu-id="63554-125">In diesem Beispiel wird eine [Group](../resources/resources.md)-Ressource aus dem integrierten DSC-Ressourcenmodul `PSDesiredStateConfiguration` verwendet.</span><span class="sxs-lookup"><span data-stu-id="63554-125">This example uses a [Group](../resources/resources.md) resource from the `PSDesiredStateConfiguration` built-in DSC resource module.</span></span> <span data-ttu-id="63554-126">Damit können lokale Gruppen erstellt oder Member hinzugefügt bzw. entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="63554-126">It can create local groups and add or remove members.</span></span> <span data-ttu-id="63554-127">Es wird sowohl die Eigenschaft `Credential` als auch die automatische Eigenschaft `PsDscRunAsCredential` akzeptiert.</span><span class="sxs-lookup"><span data-stu-id="63554-127">It accepts both the `Credential` property and the automatic `PsDscRunAsCredential` property.</span></span> <span data-ttu-id="63554-128">Allerdings verwendet die Ressource nur die Eigenschaft `Credential`.</span><span class="sxs-lookup"><span data-stu-id="63554-128">However, the resource only uses the `Credential` property.</span></span>

<span data-ttu-id="63554-129">Weitere Informationen über die Eigenschaft `PsDscRunAsCredential` finden Sie unter [Ausführen von DSC mit Benutzeranmeldeinformationen](runAsUser.md).</span><span class="sxs-lookup"><span data-stu-id="63554-129">For more information about the `PsDscRunAsCredential` property, see [Running DSC with user credentials](runAsUser.md).</span></span>

## <a name="example-the-group-resource-credential-property"></a><span data-ttu-id="63554-130">Beispiel: Die Eigenschaft „Credential“ der Ressource „Group“</span><span class="sxs-lookup"><span data-stu-id="63554-130">Example: The Group resource Credential property</span></span>

<span data-ttu-id="63554-131">Der DSC-Dienst wird unter `Local System` ausgeführt, sodass er bereits über Berechtigungen zum Ändern lokaler Benutzer und Gruppen verfügt.</span><span class="sxs-lookup"><span data-stu-id="63554-131">DSC runs under `Local System`, so it already has permissions to change local users and groups.</span></span> <span data-ttu-id="63554-132">Wenn es sich bei dem hinzugefügten Member um ein lokales Konto handelt, sind keine Anmeldeinformationen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="63554-132">If the member added is a local account, then no credential is necessary.</span></span> <span data-ttu-id="63554-133">Wenn die Ressource `Group` ein Domänenkonto zur lokalen Gruppe hinzufügt, sind Anmeldeinformationen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="63554-133">If the `Group` resource adds a domain account to the local group, then a credential is necessary.</span></span>

<span data-ttu-id="63554-134">Anonyme Abfragen an Active Directory sind nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="63554-134">Anonymous queries to Active Directory are not allowed.</span></span> <span data-ttu-id="63554-135">Die Eigenschaft `Credential` der Ressource `Group`ist das zum Abfragen von Active Directory verwendete Domänenkonto.</span><span class="sxs-lookup"><span data-stu-id="63554-135">The `Credential` property of the `Group` resource is the domain account used to query Active Directory.</span></span> <span data-ttu-id="63554-136">In den meisten Fällen könnte es sich dabei um ein allgemeines Benutzerkonto handeln, da Benutzer standardmäßig über *Lesezugriff* auf die meisten Objekte in Active Directory verfügen.</span><span class="sxs-lookup"><span data-stu-id="63554-136">For most purposes this could be a generic user account, because by default users can *read* most of the objects in Active Directory.</span></span>

## <a name="example-configuration"></a><span data-ttu-id="63554-137">Beispielkonfiguration</span><span class="sxs-lookup"><span data-stu-id="63554-137">Example Configuration</span></span>

<span data-ttu-id="63554-138">Der folgende Beispielcode verwendet DSC zum Auffüllen einer lokalen Gruppen mit einem Domänenbenutzer:</span><span class="sxs-lookup"><span data-stu-id="63554-138">The following example code uses DSC to populate a local group with a domain user:</span></span>

```powershell
Configuration DomainCredentialExample
{
    param
    (
        [PSCredential] $DomainCredential
    )
    Import-DscResource -ModuleName PSDesiredStateConfiguration

    node localhost
    {
        Group DomainUserToLocalGroup
        {
            GroupName        = 'ApplicationAdmins'
            MembersToInclude = 'contoso\alice'
            Credential       = $DomainCredential
        }
    }
}

$cred = Get-Credential -UserName contoso\genericuser -Message "Password please"
DomainCredentialExample -DomainCredential $cred
```

<span data-ttu-id="63554-139">Dieser Code generiert eine Fehler- und eine Warnmeldung:</span><span class="sxs-lookup"><span data-stu-id="63554-139">This code generates both an error and warning message:</span></span>

```
ConvertTo-MOFInstance : System.InvalidOperationException error processing property 'Credential' OF
TYPE 'Group': Converting and storing encrypted passwords as plain text is not recommended.
For more information on securing credentials in MOF file, please refer to MSDN blog:
https://go.microsoft.com/fwlink/?LinkId=393729

At line:11 char:9
+   Group
At line:341 char:16
+     $aliasId = ConvertTo-MOFInstance $keywordName $canonicalizedValue
+                ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : InvalidOperation: (:) [Write-Error], InvalidOperationException
    + FullyQualifiedErrorId : FailToProcessProperty,ConvertTo-MOFInstance
WARNING: It is not recommended to use domain credential for node 'localhost'. In order to suppress
the warning, you can add a property named 'PSDscAllowDomainUser' with a value of $true to your DSC
configuration data for node 'localhost'.

Compilation errors occurred while processing configuration
'DomainCredentialExample'. Please review the errors reported in error stream and modify your
configuration code appropriately.
At C:\WINDOWS\system32\WindowsPowerShell\v1.0\Modules\PSDesiredStateConfiguration\PSDesiredStateConfiguration.psm1:3917 char:5
+     throw $ErrorRecord
+     ~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : InvalidOperation: (DomainCredentialExample:String) [], InvalidOperationException
    + FullyQualifiedErrorId : FailToProcessConfiguration
```

<span data-ttu-id="63554-140">In diesem Beispiel gibt es zwei Probleme:</span><span class="sxs-lookup"><span data-stu-id="63554-140">This example has two issues:</span></span>

1. <span data-ttu-id="63554-141">Ein Fehler zeigt an, dass Nur-Text-Kennwörter nicht empfohlen werden.</span><span class="sxs-lookup"><span data-stu-id="63554-141">An error explains that plain text passwords are not recommended</span></span>
2. <span data-ttu-id="63554-142">Eine Warnung rät davon ab, Domänenanmeldeinformationen zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="63554-142">A warning advises against using a domain credential</span></span>

<span data-ttu-id="63554-143">Die Flags **PSDSCAllowPlainTextPassword** und **PSDSCAllowDomainUser** unterdrücken den Fehler und die Warnung, die den Benutzer über das damit verbundene Risiko informieren.</span><span class="sxs-lookup"><span data-stu-id="63554-143">The flags **PSDSCAllowPlainTextPassword** and **PSDSCAllowDomainUser** suppress the error and warning informing the user of the risk involved.</span></span>

## <a name="psdscallowplaintextpassword"></a><span data-ttu-id="63554-144">PSDSCAllowPlainTextPassword</span><span class="sxs-lookup"><span data-stu-id="63554-144">PSDSCAllowPlainTextPassword</span></span>

<span data-ttu-id="63554-145">Die erste Fehlermeldung enthält eine URL zur Dokumentation.</span><span class="sxs-lookup"><span data-stu-id="63554-145">The first error message has a URL with documentation.</span></span> <span data-ttu-id="63554-146">Unter diesem Link wird erläutert, wie Kennwörtern mit einer [ConfigurationData](./configData.md)-Struktur und einem Zertifikat verschlüsselt werden.</span><span class="sxs-lookup"><span data-stu-id="63554-146">This link explains how to encrypt passwords using a [ConfigurationData](./configData.md) structure and a certificate.</span></span> <span data-ttu-id="63554-147">Weitere Informationen zu Zertifikaten und DSC [erhalten Sie in diesen Beitrag](https://aka.ms/certs4dsc).</span><span class="sxs-lookup"><span data-stu-id="63554-147">For more information on certificates and DSC [read this post](https://aka.ms/certs4dsc).</span></span>

<span data-ttu-id="63554-148">Um ein Nur-Text-Kennwort zu erzwingen, muss im Konfigurationsdatenabschnitt der Ressource das Schlüsselwort `PsDscAllowPlainTextPassword` wie folgt enthalten sein:</span><span class="sxs-lookup"><span data-stu-id="63554-148">To force a plain text password, the resource requires the `PsDscAllowPlainTextPassword` keyword in the configuration data section as follows:</span></span>

```powershell
$password = "ThisIsAPlaintextPassword" | ConvertTo-SecureString -asPlainText -Force
$username = "contoso\Administrator"
[PSCredential] $credential = New-Object System.Management.Automation.PSCredential($username,$password)

Configuration DomainCredentialExample
{
    Import-DscResource -ModuleName PSDesiredStateConfiguration

    node localhost
    {
        Group DomainUserToLocalGroup
        {
            GroupName        = 'ApplicationAdmins'
            MembersToInclude = 'contoso\alice'
            Credential       = $credential
        }
    }
}

$cd = @{
    AllNodes = @(
        @{
            NodeName = 'localhost'
            PSDscAllowPlainTextPassword = $true
        }
    )
}

DomainCredentialExample -ConfigurationData $cd
```

### <a name="localhostmof"></a><span data-ttu-id="63554-149">localhost.mof</span><span class="sxs-lookup"><span data-stu-id="63554-149">localhost.mof</span></span>

<span data-ttu-id="63554-150">Das Flag **PSDSCAllowPlainTextPassword** verlangt, dass der Benutzer das Risiko erkennt, Nur-Text-Kennwörter in einer MOF-Datei zu speichern.</span><span class="sxs-lookup"><span data-stu-id="63554-150">The **PSDSCAllowPlainTextPassword** flag requires that the user acknowledge the risk of storing plain text passwords in a MOF file.</span></span> <span data-ttu-id="63554-151">In der generierten MOF-Datei liegen die Kennwörter dennoch als Nur-Text vor, obwohl ein **PSCredential** -Objekt, das eine **SecureString** -Angabe enthält, verwendet wurde.</span><span class="sxs-lookup"><span data-stu-id="63554-151">In the generated MOF file, even though a **PSCredential** object containing a **SecureString** was used, the passwords still appear as plain text.</span></span> <span data-ttu-id="63554-152">Dies ist das einzige Mal, dass die Anmeldeinformationen offengelegt werden.</span><span class="sxs-lookup"><span data-stu-id="63554-152">This is the only time the credentials are exposed.</span></span> <span data-ttu-id="63554-153">Wenn Sie Zugriff auf diese MOF-Datei erhalten, haben Sie Zugriff auf das Administratorkonto.</span><span class="sxs-lookup"><span data-stu-id="63554-153">Gaining access to this MOF file gives anyone access to the Administrator account.</span></span>

```
/*
@TargetNode='localhost'
@GeneratedBy=Administrator
@GenerationDate=01/31/2019 06:43:13
@GenerationHost=Server01
*/

instance of MSFT_Credential as $MSFT_Credential1ref
{
Password = "ThisIsAPlaintextPassword";
 UserName = "Administrator";

};

instance of MSFT_GroupResource as $MSFT_GroupResource1ref
{
ResourceID = "[Group]DomainUserToLocalGroup";
 MembersToInclude = {
    "contoso\\alice"
};
 Credential = $MSFT_Credential1ref;
 SourceInfo = "::11::9::Group";
 GroupName = "ApplicationAdmins";
 ModuleName = "PSDesiredStateConfiguration";

ModuleVersion = "1.0";

 ConfigurationName = "DomainCredentialExample";

};
```

### <a name="credentials-in-transit-and-at-rest"></a><span data-ttu-id="63554-154">Anmeldeinformationen im Übergang und im Ruhezustand</span><span class="sxs-lookup"><span data-stu-id="63554-154">Credentials in transit and at rest</span></span>

- <span data-ttu-id="63554-155">Das Flag **PSDscAllowPlainTextPassword** ermöglicht die Zusammenstellung von MOF-Dateien, die Kennwörter als Nur-Text enthalten.</span><span class="sxs-lookup"><span data-stu-id="63554-155">The **PSDscAllowPlainTextPassword** flag allows the compilation of MOF files that contain passwords in clear text.</span></span> <span data-ttu-id="63554-156">Treffen Sie Vorsichtsmaßnahmen beim Speichern von MOF-Dateien mit Nur-Text-Kennwörtern.</span><span class="sxs-lookup"><span data-stu-id="63554-156">Take precautions when storing MOF files containing clear text passwords.</span></span>
- <span data-ttu-id="63554-157">Wenn die MOF-Datei an einen Knoten im **Push** modus übermittelt wird, verschlüsselt WinRM die Kommunikation zum Schutz des Nur-Text-Kennworts, es sei denn, Sie überschreiben die Standardeinstellung mit dem **AllowUnencrypted** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="63554-157">When the MOF file is delivered to a Node in **Push** mode, WinRM encrypts the communication to protect the clear text password unless you override the default with the **AllowUnencrypted** parameter.</span></span>
  - <span data-ttu-id="63554-158">Die Verschlüsselung der MOF-Datei mit einem Zertifikat schützt die MOF-Datei im Ruhezustand, bevor sie auf einen Knoten angewendet wurde.</span><span class="sxs-lookup"><span data-stu-id="63554-158">Encrypting the MOF with a certificate protects the MOF file at rest before it has been applied to a node.</span></span>
- <span data-ttu-id="63554-159">Im **Pull** modus können Sie den Windows-Pullserver so konfigurieren, dass er HTTPS verwendet, um den Datenverkehr mit dem in Internet Information Server angegebenen Protokoll zu verschlüsseln.</span><span class="sxs-lookup"><span data-stu-id="63554-159">In **Pull** mode, you can configure Windows pull server to use HTTPS to encrypt traffic using the protocol specified in Internet Information Server.</span></span> <span data-ttu-id="63554-160">Weitere Informationen finden Sie in den Artikeln [Einrichten eines DSC-Pullclients](../pull-server/pullclient.md) und [Sichern von MOF-Dateien mit Zertifikaten](../pull-server/secureMOF.md).</span><span class="sxs-lookup"><span data-stu-id="63554-160">For more information, see the articles [Setting up a DSC pull client](../pull-server/pullclient.md) and [Securing MOF files with Certificates](../pull-server/secureMOF.md).</span></span>
  - <span data-ttu-id="63554-161">In der [Azure Automation State Configuration](/azure/automation/automation-dsc-overview) ist Pulldatenverkehr immer verschlüsselt.</span><span class="sxs-lookup"><span data-stu-id="63554-161">In the [Azure Automation State Configuration](/azure/automation/automation-dsc-overview) service, Pull traffic is always encrypted.</span></span>
- <span data-ttu-id="63554-162">Auf dem Knoten werden MOF-Dateien im Ruhezustand ab PowerShell 5.0 verschlüsselt.</span><span class="sxs-lookup"><span data-stu-id="63554-162">On the Node, MOF files are encrypted at rest Beginning in PowerShell 5.0.</span></span>
  - <span data-ttu-id="63554-163">In PowerShell 4.0 sind MOF-Dateien im Ruhezustand unverschlüsselt, es sei denn, sie werden mit einem Zertifikat verschlüsselt, wenn sie auf den Knoten gepusht oder von ihm gepullt werden.</span><span class="sxs-lookup"><span data-stu-id="63554-163">In PowerShell 4.0 MOF files are unencrypted at rest unless they are encrypted with a certificate when they pushed or pulled to the Node.</span></span>

<span data-ttu-id="63554-164">**Microsoft empfiehlt, Nur-Text-Kennwörter aufgrund des hohen Sicherheitsrisikos zu vermeiden.**</span><span class="sxs-lookup"><span data-stu-id="63554-164">**Microsoft advises to avoid plain text passwords due to the significant security risk.**</span></span>

## <a name="domain-credentials"></a><span data-ttu-id="63554-165">Anmeldeinformationen für die Domäne</span><span class="sxs-lookup"><span data-stu-id="63554-165">Domain Credentials</span></span>

<span data-ttu-id="63554-166">Wenn Sie das Beispielkonfigurationsskript erneut ausführen (mit oder ohne Verschlüsselung), wird weiterhin die Warnung generiert, dass die Verwendung von Anmeldeinformationen eines Domänenkontos nicht empfohlen wird.</span><span class="sxs-lookup"><span data-stu-id="63554-166">Running the example configuration script again (with or without encryption), still generates the warning that using a domain account for a credential is not recommended.</span></span> <span data-ttu-id="63554-167">Durch Verwendung eines lokalen Kontos wird verhindert, dass Domänenanmeldeinformationen, die auf anderen Servern verwendet werden könnten, offengelegt werden.</span><span class="sxs-lookup"><span data-stu-id="63554-167">Using a local account eliminates potential exposure of domain credentials that could be used on other servers.</span></span>

<span data-ttu-id="63554-168">**Bei Verwendung von Anmeldeinformationen mit DSC-Ressourcen ziehen Sie, wenn möglich, ein lokales Konto einem Domänenkonto vor.**</span><span class="sxs-lookup"><span data-stu-id="63554-168">**When using credentials with DSC resources, prefer a local account over a domain account when possible.**</span></span>

<span data-ttu-id="63554-169">Enthält die `Username`-Eigenschaft der Anmeldeinformationen die Zeichen „\\“ oder „\@“, behandelt DSC das Konto als Domänenkonto.</span><span class="sxs-lookup"><span data-stu-id="63554-169">If there is a '\\' or '\@' in the `Username` property of the credential, then DSC will treat it as a domain account.</span></span> <span data-ttu-id="63554-170">Ausnahmen machen „Localhost“, „127.0.0.1“ und „:: 1“ im Domänenteil des Benutzernamens.</span><span class="sxs-lookup"><span data-stu-id="63554-170">There is an exception for "localhost", "127.0.0.1", and "::1" in the domain portion of the user name.</span></span>

## <a name="psdscallowdomainuser"></a><span data-ttu-id="63554-171">PSDscAllowDomainUser</span><span class="sxs-lookup"><span data-stu-id="63554-171">PSDscAllowDomainUser</span></span>

<span data-ttu-id="63554-172">Im oben stehenden Beispiel zur DSC-Ressourcen `Group` ist zum Abfragen einer Active Directory-Domäne ein Domänenkonto *erforderlich*.</span><span class="sxs-lookup"><span data-stu-id="63554-172">In the DSC `Group` resource example above, querying an Active Directory domain *requires* a domain account.</span></span> <span data-ttu-id="63554-173">Fügen Sie in diesem Fall die Eigenschaft `PSDscAllowDomainUser` wie folgt zum Block `ConfigurationData` hinzu:</span><span class="sxs-lookup"><span data-stu-id="63554-173">In this case add the `PSDscAllowDomainUser` property to the `ConfigurationData` block as follows:</span></span>

```powershell
$password = "ThisIsAPlaintextPassword" | ConvertTo-SecureString -asPlainText -Force
$username = "contoso\Administrator"
[PSCredential] $credential = New-Object System.Management.Automation.PSCredential($username,$password)

Configuration DomainCredentialExample
{
    Import-DscResource -ModuleName PSDesiredStateConfiguration

    node localhost
    {
        Group DomainUserToLocalGroup
        {
            GroupName        = 'ApplicationAdmins'
            MembersToInclude = 'contoso\alice'
            Credential       = $credential
        }
    }
}

$cd = @{
    AllNodes = @(
        @{
            NodeName = 'localhost'
            PSDscAllowDomainUser = $true
            PSDscAllowPlainTextPassword = $true
        }
    )
}

DomainCredentialExample -ConfigurationData $cd
```

<span data-ttu-id="63554-174">Nun generiert das Konfigurationsskript die MOF-Datei ohne Fehler oder Warnungen.</span><span class="sxs-lookup"><span data-stu-id="63554-174">Now the configuration script will generate the MOF file with no errors or warnings.</span></span>
