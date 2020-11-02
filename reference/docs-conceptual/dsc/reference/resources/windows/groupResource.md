---
ms.date: 07/16/2020
ms.topic: reference
title: DSC-Ressource „Group“
description: DSC-Ressource „Group“
ms.openlocfilehash: 8e2d1139c9573d7e310fec2410b14df04b79e1b2
ms.sourcegitcommit: 196c7f8cd24560cac70c88acc89909f17a86aea9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2020
ms.locfileid: "93142445"
---
# <a name="dsc-group-resource"></a><span data-ttu-id="894f3-103">DSC-Ressource „Group“</span><span class="sxs-lookup"><span data-stu-id="894f3-103">DSC Group Resource</span></span>

> <span data-ttu-id="894f3-104">Gilt für: Windows PowerShell 4.0, Windows PowerShell 5.x</span><span class="sxs-lookup"><span data-stu-id="894f3-104">Applies To: Windows PowerShell 4.0, Windows PowerShell 5.x</span></span>

<span data-ttu-id="894f3-105">Die Ressource **Group** in Windows PowerShell DSC bietet einen Mechanismus zum Verwalten lokaler Gruppen auf dem Zielknoten.</span><span class="sxs-lookup"><span data-stu-id="894f3-105">The **Group** resource in Windows PowerShell Desired State Configuration (DSC) provides a mechanism to manage local groups on the target node.</span></span>

[!INCLUDE [Updated DSC Resources](../../../../../includes/dsc-resources.md)]

## <a name="syntax"></a><span data-ttu-id="894f3-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="894f3-106">Syntax</span></span>

```Syntax
Group [string] #ResourceName
{
    GroupName = [string]
    [ Credential = [PSCredential] ]
    [ Description = [string[]] ]
    [ Members = [string[]] ]
    [ MembersToExclude = [string[]] ]
    [ MembersToInclude = [string[]] ]
    [ DependsOn = [string[]] ]
    [ Ensure = [string] { Absent | Present }  ]
    [ PsDscRunAsCredential = [PSCredential] ]
}
```

## <a name="properties"></a><span data-ttu-id="894f3-107">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="894f3-107">Properties</span></span>

|<span data-ttu-id="894f3-108">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="894f3-108">Property</span></span> |<span data-ttu-id="894f3-109">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="894f3-109">Description</span></span> |
|---|---|
|<span data-ttu-id="894f3-110">GroupName</span><span class="sxs-lookup"><span data-stu-id="894f3-110">GroupName</span></span> |<span data-ttu-id="894f3-111">Der Name der Gruppe, für die Sie einen bestimmten Zustand sicherstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="894f3-111">The name of the group for which you want to ensure a specific state.</span></span> |
|<span data-ttu-id="894f3-112">Anmeldeinformationen</span><span class="sxs-lookup"><span data-stu-id="894f3-112">Credential</span></span> |<span data-ttu-id="894f3-113">Die Anmeldeinformationen für den Zugriff auf Remoteressourcen.</span><span class="sxs-lookup"><span data-stu-id="894f3-113">The credentials required to access remote resources.</span></span> <span data-ttu-id="894f3-114">Dieses Konto muss die entsprechenden Active Directory-Berechtigungen aufweisen, um alle nicht lokalen Konten zur Gruppe hinzuzufügen. Andernfalls tritt ein Fehler auf, wenn die Konfiguration auf dem Zielknoten ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="894f3-114">This account must have the appropriate Active Directory permissions to add all non-local accounts to the group; otherwise, an error occurs when the configuration is executed on the target node.</span></span>
|<span data-ttu-id="894f3-115">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="894f3-115">Description</span></span> |<span data-ttu-id="894f3-116">Die Beschreibung der Gruppe.</span><span class="sxs-lookup"><span data-stu-id="894f3-116">The description of the group.</span></span> |
|<span data-ttu-id="894f3-117">Members</span><span class="sxs-lookup"><span data-stu-id="894f3-117">Members</span></span> |<span data-ttu-id="894f3-118">Verwenden Sie diese Eigenschaft, um die aktuelle Gruppenmitgliedschaft durch die angegebenen Member zu ersetzen.</span><span class="sxs-lookup"><span data-stu-id="894f3-118">Use this property to replace the current group membership with the specified members.</span></span> <span data-ttu-id="894f3-119">Der Wert dieser Eigenschaft ist ein Zeichenfolgenarray im Format `Domain\UserName`.</span><span class="sxs-lookup"><span data-stu-id="894f3-119">The value of this property is an array of strings of the form `Domain\UserName`.</span></span> <span data-ttu-id="894f3-120">Wenn Sie diese Eigenschaft in einer Konfiguration festlegen, verwenden Sie weder die Eigenschaft **MembersToExclude** noch die Eigenschaft **MembersToInclude** .</span><span class="sxs-lookup"><span data-stu-id="894f3-120">If you set this property in a configuration, do not use either the **MembersToExclude** or **MembersToInclude** property.</span></span> <span data-ttu-id="894f3-121">Andernfalls kommt es zu einem Fehler.</span><span class="sxs-lookup"><span data-stu-id="894f3-121">Doing so generates an error.</span></span> |
|<span data-ttu-id="894f3-122">MembersToExclude</span><span class="sxs-lookup"><span data-stu-id="894f3-122">MembersToExclude</span></span> |<span data-ttu-id="894f3-123">Verwenden Sie diese Eigenschaft, um Member aus der vorhandenen Gruppenmitgliedschaft zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="894f3-123">Use this property to remove members from the existing membership of the group.</span></span> <span data-ttu-id="894f3-124">Der Wert dieser Eigenschaft ist ein Zeichenfolgenarray im Format `Domain\UserName`.</span><span class="sxs-lookup"><span data-stu-id="894f3-124">The value of this property is an array of strings of the form `Domain\UserName`.</span></span> <span data-ttu-id="894f3-125">Wenn Sie diese Eigenschaft in einer Konfiguration festgelegt haben, verwenden Sie die Eigenschaft **Members** nicht.</span><span class="sxs-lookup"><span data-stu-id="894f3-125">If you set this property in a configuration, do not use the **Members** property.</span></span> <span data-ttu-id="894f3-126">Andernfalls kommt es zu einem Fehler.</span><span class="sxs-lookup"><span data-stu-id="894f3-126">Doing so generates an error.</span></span> |
|<span data-ttu-id="894f3-127">MembersToInclude</span><span class="sxs-lookup"><span data-stu-id="894f3-127">MembersToInclude</span></span> |<span data-ttu-id="894f3-128">Verwenden Sie diese Eigenschaft, um Member zur vorhandenen Gruppenmitgliedschaft hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="894f3-128">Use this property to add members to the existing membership of the group.</span></span> <span data-ttu-id="894f3-129">Der Wert dieser Eigenschaft ist ein Zeichenfolgenarray im Format `Domain\UserName`.</span><span class="sxs-lookup"><span data-stu-id="894f3-129">The value of this property is an array of strings of the form `Domain\UserName`.</span></span> <span data-ttu-id="894f3-130">Wenn Sie diese Eigenschaft in einer Konfiguration festgelegt haben, verwenden Sie die Eigenschaft **Members** nicht.</span><span class="sxs-lookup"><span data-stu-id="894f3-130">If you set this property in a configuration, do not use the **Members** property.</span></span> <span data-ttu-id="894f3-131">Andernfalls wird ein Fehler generiert.</span><span class="sxs-lookup"><span data-stu-id="894f3-131">Doing so will generate an error.</span></span> |

## <a name="common-properties"></a><span data-ttu-id="894f3-132">Allgemeine Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="894f3-132">Common properties</span></span>

|<span data-ttu-id="894f3-133">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="894f3-133">Property</span></span> |<span data-ttu-id="894f3-134">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="894f3-134">Description</span></span> |
|---|---|
|<span data-ttu-id="894f3-135">DependsOn</span><span class="sxs-lookup"><span data-stu-id="894f3-135">DependsOn</span></span> |<span data-ttu-id="894f3-136">Gibt an, dass die Konfiguration einer anderen Ressource ausgeführt werden muss, bevor diese Ressource konfiguriert wird.</span><span class="sxs-lookup"><span data-stu-id="894f3-136">Indicates that the configuration of another resource must run before this resource is configured.</span></span> <span data-ttu-id="894f3-137">Wenn beispielsweise die ID des Skriptblocks mit der Ressourcenkonfiguration, den Sie zuerst ausführen möchten, „ResourceName“ und dessen Typ „ResourceType“ ist, lautet die Syntax für das Verwenden dieser Eigenschaft `DependsOn = "[ResourceType]ResourceName"`.</span><span class="sxs-lookup"><span data-stu-id="894f3-137">For example, if the ID of the resource configuration script block that you want to run first is ResourceName and its type is ResourceType, the syntax for using this property is `DependsOn = "[ResourceType]ResourceName"`.</span></span> |
|<span data-ttu-id="894f3-138">Ensure</span><span class="sxs-lookup"><span data-stu-id="894f3-138">Ensure</span></span> |<span data-ttu-id="894f3-139">Gibt an, ob die Gruppe vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="894f3-139">Indicates if the group exists.</span></span> <span data-ttu-id="894f3-140">Legen Sie diese Eigenschaft auf **Absent** fest, um sicherzustellen, dass die Gruppe nicht vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="894f3-140">Set this property to **Absent** to ensure that the group does not exist.</span></span> <span data-ttu-id="894f3-141">Das Festlegen auf **Present** stellt sicher, dass die Gruppe vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="894f3-141">Setting it to **Present** ensures that the group exists.</span></span> <span data-ttu-id="894f3-142">Der Standardwert ist **Present** .</span><span class="sxs-lookup"><span data-stu-id="894f3-142">The default value is **Present** .</span></span> |
|<span data-ttu-id="894f3-143">PsDscRunAsCredential</span><span class="sxs-lookup"><span data-stu-id="894f3-143">PsDscRunAsCredential</span></span> |<span data-ttu-id="894f3-144">Legt die Anmeldeinformationen für die Ausführung der gesamten Ressource fest.</span><span class="sxs-lookup"><span data-stu-id="894f3-144">Sets the credential for running the entire resource as.</span></span> |

> [!NOTE]
> <span data-ttu-id="894f3-145">Die allgemeine Eigenschaft **PsDscRunAsCredential** wurde in WMF 5.0 hinzugefügt, um das Ausführen einer beliebigen DSC-Ressource in Verbindung mit anderen Anmeldeinformationen zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="894f3-145">The **PsDscRunAsCredential** common property was added in WMF 5.0 to allow running any DSC resource in the context of other credentials.</span></span> <span data-ttu-id="894f3-146">Weitere Informationen finden Sie unter [Use Credentials with DSC Resources](../../../configurations/runasuser.md) (Verwenden von Anmeldeinformationen mit DSC-Ressourcen).</span><span class="sxs-lookup"><span data-stu-id="894f3-146">For more information, see [Use Credentials with DSC Resources](../../../configurations/runasuser.md).</span></span>

## <a name="example-1-ensure-group-is-not-present"></a><span data-ttu-id="894f3-147">Beispiel 1: Sicherstellen, dass Gruppe nicht vorhanden ist</span><span class="sxs-lookup"><span data-stu-id="894f3-147">Example 1: Ensure group is not present</span></span>

<span data-ttu-id="894f3-148">Im folgenden Beispiel wird veranschaulicht, wie sichergestellt wird, dass eine Gruppe namens „TestGroup“ nicht vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="894f3-148">The following example shows how to ensure that a group called "TestGroup" is absent.</span></span>

```powershell
Group GroupExample
{
    # This removes TestGroup, if present
    # To create a new group, set Ensure to "Present"
    Ensure = "Absent"
    GroupName = "TestGroup"
}
```

## <a name="example-2-add-domain-user-to-local-group"></a><span data-ttu-id="894f3-149">Beispiel 2: Hinzufügen eines Domänenbenutzers zur lokalen Gruppe</span><span class="sxs-lookup"><span data-stu-id="894f3-149">Example 2: Add domain user to local group</span></span>

<span data-ttu-id="894f3-150">Im folgenden Beispiel wird veranschaulicht, wie Sie einen Active Directory-Benutzer zur Gruppe der lokalen Administratoren als Teil eines Testbuilds für mehrere Computer hinzufügen, bei dem Sie bereits die PSCredential-Klasse für das lokale Administratorkonto verwenden.</span><span class="sxs-lookup"><span data-stu-id="894f3-150">The following example shows how to add an Active Directory User to the local administrators group as part of a Multi-Machine Lab build where you are already using a PSCredential for the Local Administrator account.</span></span> <span data-ttu-id="894f3-151">Da diese Informationen auch für das Domänenadministratorkonto (nach der Domänenhöherstufung) verwendet werden, müssen diese vorhandenen PSCredential-Informationen dann in domänenkompatible Anmeldeinformationen konvertiert werden.</span><span class="sxs-lookup"><span data-stu-id="894f3-151">As this is also used for the Domain Admin Account (after Domain promotion), we then need to convert this existing PSCredential to a Domain Friendly credential.</span></span> <span data-ttu-id="894f3-152">Dann kann der Gruppe „Lokale Administratoren“ auf dem Mitgliedsserver ein Domänenbenutzer hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="894f3-152">Then we can add a Domain User to the Local Administrators Group on the Member server.</span></span>

```powershell
@{
    AllNodes = @(
        @{
            NodeName = '*';
            DomainName = 'SubTest.contoso.com';
         }
        @{
            NodeName = 'Box2';
            AdminAccount = 'Admin-Dave_Alexanderson'
        }
    )
}

$domain = $node.DomainName.split('.')[0]
$DCredential = New-Object -TypeName System.Management.Automation.PSCredential -ArgumentList ("$domain\$($credential.Username)", $Credential.Password)

Group AddADUserToLocalAdminGroup {
    GroupName='Administrators'
    Ensure= 'Present'
    MembersToInclude= "$domain\$($Node.AdminAccount)"
    Credential = $dCredential
    PsDscRunAsCredential = $DCredential
}
```

## <a name="example-3"></a><span data-ttu-id="894f3-153">Beispiel 3</span><span class="sxs-lookup"><span data-stu-id="894f3-153">Example 3</span></span>

<span data-ttu-id="894f3-154">Das folgende Beispiel zeigt, wie sichergestellt wird, dass die lokale Gruppe „TigerTeamAdmins“ auf dem Server „TigerTeamSource.Contoso.Com“ ein bestimmtes Domänenkonto, „Contoso\JerryG“, nicht enthält.</span><span class="sxs-lookup"><span data-stu-id="894f3-154">The following example shows how to ensure a local group, TigerTeamAdmins, on the server TigerTeamSource.Contoso.Com does not contain a particular domain account, Contoso\JerryG.</span></span>

```powershell
Configuration SecureTigerTeamSource {
    Import-DscResource -ModuleName 'PSDesiredStateConfiguration'

    Node TigerTeamSource.Contoso.Com {
        Group TigerTeamAdmins {
            GroupName        = 'TigerTeamAdmins'
            Ensure           = 'Present'
            MembersToExclude = "Contoso\JerryG"
        }
    }
}
```
