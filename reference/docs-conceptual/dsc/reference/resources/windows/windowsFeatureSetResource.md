---
ms.date: 07/16/2020
keywords: DSC,PowerShell,Konfiguration,Setup,Einrichtung
title: DSC-Ressource „WindowsFeatureSet“
ms.openlocfilehash: 856c56e0b35a26add729ef77db9dca71fdc0a4d0
ms.sourcegitcommit: 41e1acbd9ce0f49a23c6eb99facd2c280d836836
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/18/2020
ms.locfileid: "86463855"
---
# <a name="dsc-windowsfeatureset-resource"></a><span data-ttu-id="8c551-103">DSC-Ressource „WindowsFeatureSet“</span><span class="sxs-lookup"><span data-stu-id="8c551-103">DSC WindowsFeatureSet Resource</span></span>

> <span data-ttu-id="8c551-104">Gilt für: Windows PowerShell 5.x</span><span class="sxs-lookup"><span data-stu-id="8c551-104">Applies To: Windows PowerShell 5.x</span></span>

<span data-ttu-id="8c551-105">Die Ressource **WindowsFeatureSet** in Windows PowerShell DSC (Desired State Configuration) bietet einen Mechanismus, um sicherzustellen, dass Rollen und Features einem Zielknoten hinzugefügt oder von diesem entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="8c551-105">The **WindowsFeatureSet** resource in Windows PowerShell Desired State Configuration (DSC) provides a mechanism to ensure that roles and features are added or removed on a target node.</span></span> <span data-ttu-id="8c551-106">Diese Ressource ist eine [zusammengesetzte Ressource](../../../resources/authoringResourceComposite.md), die die Ressource [WindowsFeature](windowsfeatureResource.md) für jedes Feature aufruft, das in der **Name**-Eigenschaft angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="8c551-106">This resource is a [composite resource](../../../resources/authoringResourceComposite.md) that calls the [WindowsFeature resource](windowsfeatureResource.md) for each feature specified in the **Name** property.</span></span>

<span data-ttu-id="8c551-107">Verwenden Sie diese Ressource, wenn Sie verschiedene Windows-Features mit demselben Status konfigurieren möchten.</span><span class="sxs-lookup"><span data-stu-id="8c551-107">Use this resource when you want to configure a number of Windows Features to the same state.</span></span>

## <a name="syntax"></a><span data-ttu-id="8c551-108">Syntax</span><span class="sxs-lookup"><span data-stu-id="8c551-108">Syntax</span></span>

```Syntax
WindowsFeatureSet [string] #ResourceName
{
    Name = [string[]]
    [ Source = [string] ]
    [ IncludeAllSubFeature = [Boolean] ]
    [ Credential = [PSCredential] ]
    [ LogPath = [string] ]
    [ DependsOn = [string[]] ]
    [ Ensure = [string] { Absent | Present }  ]
    [ PsDscRunAsCredential = [PSCredential] ]
}
```

## <a name="properties"></a><span data-ttu-id="8c551-109">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="8c551-109">Properties</span></span>

|  <span data-ttu-id="8c551-110">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="8c551-110">Property</span></span>  |  <span data-ttu-id="8c551-111">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="8c551-111">Description</span></span>   |
|---|---|
|<span data-ttu-id="8c551-112">Name</span><span class="sxs-lookup"><span data-stu-id="8c551-112">Name</span></span> |<span data-ttu-id="8c551-113">Die Namen der Rollen oder Features an, die hinzugefügt oder entfernt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="8c551-113">The names of the roles or features that you want to ensure are added or removed.</span></span> <span data-ttu-id="8c551-114">Dies ist identisch mit der **Name**-Eigenschaft des Cmdlets [Get-WindowsFeature](/powershell/module/servermanager/get-windowsfeature?view=winserver2012r2-ps) und nicht mit dem Anzeigenamen der Rollen oder Features.</span><span class="sxs-lookup"><span data-stu-id="8c551-114">This is the same as the **Name** property of the [Get-WindowsFeature](/powershell/module/servermanager/get-windowsfeature?view=winserver2012r2-ps) cmdlet, and not the display name of the roles or features.</span></span> |
|<span data-ttu-id="8c551-115">`Source`</span><span class="sxs-lookup"><span data-stu-id="8c551-115">Source</span></span> |<span data-ttu-id="8c551-116">Gibt bei Bedarf den Speicherort der Quelldatei an, die für die Installation verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="8c551-116">Indicates the location of the source file to use for installation, if necessary.</span></span> |
|<span data-ttu-id="8c551-117">IncludeAllSubFeature</span><span class="sxs-lookup"><span data-stu-id="8c551-117">IncludeAllSubFeature</span></span> |<span data-ttu-id="8c551-118">Legen Sie diese Eigenschaft auf `$true` fest, um alle erforderlichen Teilfeatures in die Features einzubeziehen, die Sie mit der **Name**-Eigenschaft angeben.</span><span class="sxs-lookup"><span data-stu-id="8c551-118">Set this property to `$true` to include all required subfeatures with of the features you specify with the **Name** property.</span></span> |
|<span data-ttu-id="8c551-119">Anmeldeinformationen</span><span class="sxs-lookup"><span data-stu-id="8c551-119">Credential</span></span> |<span data-ttu-id="8c551-120">Die Anmeldeinformationen zum Hinzufügen oder Entfernen der Rollen oder Features.</span><span class="sxs-lookup"><span data-stu-id="8c551-120">The credentials to use to add or remove the roles or features.</span></span> |
|<span data-ttu-id="8c551-121">LogPath</span><span class="sxs-lookup"><span data-stu-id="8c551-121">LogPath</span></span> |<span data-ttu-id="8c551-122">Der Pfad zu einer Protokolldatei, in der der Ressourcenanbieter den Vorgang protokollieren soll.</span><span class="sxs-lookup"><span data-stu-id="8c551-122">The path to a log file where you want the resource provider to log the operation.</span></span> |

## <a name="common-properties"></a><span data-ttu-id="8c551-123">Allgemeine Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="8c551-123">Common properties</span></span>

|<span data-ttu-id="8c551-124">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="8c551-124">Property</span></span> |<span data-ttu-id="8c551-125">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="8c551-125">Description</span></span> |
|---|---|
|<span data-ttu-id="8c551-126">DependsOn</span><span class="sxs-lookup"><span data-stu-id="8c551-126">DependsOn</span></span> |<span data-ttu-id="8c551-127">Gibt an, dass die Konfiguration einer anderen Ressource ausgeführt werden muss, bevor diese Ressource konfiguriert wird.</span><span class="sxs-lookup"><span data-stu-id="8c551-127">Indicates that the configuration of another resource must run before this resource is configured.</span></span> <span data-ttu-id="8c551-128">Wenn beispielsweise die ID des Skriptblocks mit der Ressourcenkonfiguration, den Sie zuerst ausführen möchten, „ResourceName“ und dessen Typ „ResourceType“ ist, lautet die Syntax für das Verwenden dieser Eigenschaft `DependsOn = "[ResourceType]ResourceName"`.</span><span class="sxs-lookup"><span data-stu-id="8c551-128">For example, if the ID of the resource configuration script block that you want to run first is ResourceName and its type is ResourceType, the syntax for using this property is `DependsOn = "[ResourceType]ResourceName"`.</span></span> |
|<span data-ttu-id="8c551-129">Ensure</span><span class="sxs-lookup"><span data-stu-id="8c551-129">Ensure</span></span> |<span data-ttu-id="8c551-130">Gibt an, ob die Rollen oder Features hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="8c551-130">Indicates whether the roles or features are added.</span></span> <span data-ttu-id="8c551-131">Um sicherzustellen, dass die Rollen oder Features hinzugefügt werden, legen Sie diese Eigenschaft auf **Present** fest.</span><span class="sxs-lookup"><span data-stu-id="8c551-131">To ensure that the roles or features are added, set this property to **Present**.</span></span> <span data-ttu-id="8c551-132">Um sicherzustellen, dass die Rollen oder Features entfernt werden, legen Sie diese Eigenschaft auf **Absent** fest.</span><span class="sxs-lookup"><span data-stu-id="8c551-132">To ensure that the roles or features are removed, set the property to **Absent**.</span></span> <span data-ttu-id="8c551-133">Der Standardwert ist **Present**.</span><span class="sxs-lookup"><span data-stu-id="8c551-133">The default value is **Present**.</span></span> |
|<span data-ttu-id="8c551-134">PsDscRunAsCredential</span><span class="sxs-lookup"><span data-stu-id="8c551-134">PsDscRunAsCredential</span></span> |<span data-ttu-id="8c551-135">Legt die Anmeldeinformationen für die Ausführung der gesamten Ressource fest.</span><span class="sxs-lookup"><span data-stu-id="8c551-135">Sets the credential for running the entire resource as.</span></span> |

> [!NOTE]
> <span data-ttu-id="8c551-136">Die allgemeine Eigenschaft **PsDscRunAsCredential** wurde in WMF 5.0 hinzugefügt, um das Ausführen einer beliebigen DSC-Ressource in Verbindung mit anderen Anmeldeinformationen zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="8c551-136">The **PsDscRunAsCredential** common property was added in WMF 5.0 to allow running any DSC resource in the context of other credentials.</span></span> <span data-ttu-id="8c551-137">Weitere Informationen finden Sie unter [Use Credentials with DSC Resources](../../../configurations/runasuser.md) (Verwenden von Anmeldeinformationen mit DSC-Ressourcen).</span><span class="sxs-lookup"><span data-stu-id="8c551-137">For more information, see [Use Credentials with DSC Resources](../../../configurations/runasuser.md).</span></span>

## <a name="example"></a><span data-ttu-id="8c551-138">Beispiel</span><span class="sxs-lookup"><span data-stu-id="8c551-138">Example</span></span>

<span data-ttu-id="8c551-139">Mit der folgenden Konfiguration wird sichergestellt, dass die Features **Webserver** (IIS) und **SMTP-Server** sowie alle Teilfeatures installiert werden.</span><span class="sxs-lookup"><span data-stu-id="8c551-139">The following configuration ensures that the **Web-Server** (IIS) and **SMTP Server** features, and all subfeatures of each, are installed.</span></span>

```powershell
configuration FeatureSetTest
{
    Import-DscResource -ModuleName PSDesiredStateConfiguration
    Node localhost
    {

        WindowsFeatureSet WindowsFeatureSetExample
        {
            Name                    = @("SMTP-Server", "Web-Server")
            Ensure                  = 'Present'
            IncludeAllSubFeature    = $true
        }
    }
}
```
