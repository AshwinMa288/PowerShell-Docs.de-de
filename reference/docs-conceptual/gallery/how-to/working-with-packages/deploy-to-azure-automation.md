---
ms.date: 06/12/2017
title: Bereitstellen in Azure Automation
description: In diesem Artikel wird beschrieben, wie Sie den PowerShell-Katalog zum Bereitstellen eines Pakets für Azure Automation verwenden.
ms.openlocfilehash: e9de079ee6cc950c8a268423b9eabd515959b718
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92662374"
---
# <a name="deploy-to-azure-automation"></a><span data-ttu-id="5ce33-103">Bereitstellen in Azure Automation</span><span class="sxs-lookup"><span data-stu-id="5ce33-103">Deploy to Azure Automation</span></span>

<span data-ttu-id="5ce33-104">Mit der Schaltfläche „In Azure Automation bereitstellen“ auf der Seite mit den Paketdetails können Sie ein Paket aus dem PowerShell-Katalog in Azure Automation bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="5ce33-104">The Deploy to Azure Automation button on the package details page will deploy the package from the PowerShell Gallery to Azure Automation.</span></span>

![Schaltfläche zum Bereitstellen in Azure Automation](media/deploy-to-azure-automation/DeployToAzureAutomationButton.png)

<span data-ttu-id="5ce33-106">Wenn Sie auf diese Schaltfläche klicken, werden Sie zum Azure-Verwaltungsportal umgeleitet, wo Sie sich mit den Anmeldeinformationen Ihres Azure-Kontos anmelden.</span><span class="sxs-lookup"><span data-stu-id="5ce33-106">When clicked, it will redirect you to the Azure Management Portal, where you sign in using your Azure account credentials.</span></span> <span data-ttu-id="5ce33-107">Wenn das Paket Abhängigkeiten enthält, werden diese ebenfalls in Azure Automation bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="5ce33-107">If the package includes dependencies, all the dependencies will be deployed to Azure Automation as well.</span></span>

> [!WARNING]
> <span data-ttu-id="5ce33-108">Wenn das gleiche Paket und die gleiche Version bereits in Ihrem Automation-Konto vorhanden sind, überschreibt das erneute Bereitstellen aus dem PowerShell-Katalog das Paket in Ihrem Automation-Konto.</span><span class="sxs-lookup"><span data-stu-id="5ce33-108">If the same package and version already exist in your Automation account, deploying it again from the PowerShell Gallery will overwrite the package in your Automation account.</span></span>

<span data-ttu-id="5ce33-109">Wenn Sie ein Modul bereitstellen, wird es im Abschnitt „Module“ von Azure Automation angezeigt.</span><span class="sxs-lookup"><span data-stu-id="5ce33-109">If you deploy a module, it will appear in the Modules section of Azure Automation.</span></span> <span data-ttu-id="5ce33-110">Wenn Sie ein Skript bereitstellen, wird es im Abschnitt „Runbooks“ von Azure Automation angezeigt.</span><span class="sxs-lookup"><span data-stu-id="5ce33-110">If you deploy a script, it will appear in the Runbooks section of Azure Automation.</span></span>

<span data-ttu-id="5ce33-111">Sie können die Schaltfläche „In Azure Automation bereitstellen“ deaktivieren, indem Sie den Paketmetadaten das Tag „AzureAutomationNotSupported“ hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="5ce33-111">The Deploy to Azure Automation button can be disabled by adding the AzureAutomationNotSupported tag to the package metadata.</span></span>

## <a name="require-license-acceptance-on-deploy-to-azure-automation"></a><span data-ttu-id="5ce33-112">Erforderliche Zustimmung zur Lizenz für die Bereitstellung in Azure Automation</span><span class="sxs-lookup"><span data-stu-id="5ce33-112">Require License Acceptance on Deploy to Azure Automation</span></span>

<span data-ttu-id="5ce33-113">Wenn für das Modul, das in Azure Automation bereitgestellt wird, die Zustimmung zur Lizenz erforderlich ist, wird auf der Portaloberfläche ein Haftungsausschluss mit folgender Meldung angezeigt: „Für dieses Modul muss der Lizenz zugestimmt werden.</span><span class="sxs-lookup"><span data-stu-id="5ce33-113">If the module being deployed to Azure Automation requires license acceptance, portal UI will show a disclaimer saying 'This module requires license acceptance.</span></span> <span data-ttu-id="5ce33-114">Indem Sie auf ‚OK‘ klicken, akzeptieren Sie die Lizenzbedingungen.“</span><span class="sxs-lookup"><span data-stu-id="5ce33-114">By clicking OK, you are accepting license terms.'</span></span>

![Für die Bereitstellung in Azure Automation ist die Zustimmung zur Lizenz erforderlich.](media/deploy-to-azure-automation/DeployToAzureAutomationRequireLicenseAcceptanceDisclaimer.png)

## <a name="more-details"></a><span data-ttu-id="5ce33-116">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="5ce33-116">More details</span></span>

- [<span data-ttu-id="5ce33-117">Erforderliche Zustimmung zur Lizenz in PowerShellGet</span><span class="sxs-lookup"><span data-stu-id="5ce33-117">Require License Acceptance in PowerShellGet</span></span>](../../concepts/module-license-acceptance.md)
- [<span data-ttu-id="5ce33-118">Erforderliche Zustimmung zur Lizenz im PowerShell-Katalog</span><span class="sxs-lookup"><span data-stu-id="5ce33-118">Require License Acceptance in PowerShell Gallery</span></span>](packages-that-require-license-acceptance.md)
- [<span data-ttu-id="5ce33-119">Azure Automation-Website</span><span class="sxs-lookup"><span data-stu-id="5ce33-119">Azure Automation website</span></span>](https://azure.microsoft.com/services/automation/)
