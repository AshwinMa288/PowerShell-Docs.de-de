---
ms.date: 06/12/2017
keywords: wmf,powershell,setup
title: Deinstallieren von WMF 5.0
ms.openlocfilehash: fa76bacb4b62025d0d2350b9a0e072068ca83ab1
ms.sourcegitcommit: c4906f4c9fa4ef1a16dcd6dd00ff960d19446d71
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/01/2020
ms.locfileid: "89236304"
---
# <a name="uninstallation-instructions"></a><span data-ttu-id="6d81c-103">Deinstallationsanweisungen</span><span class="sxs-lookup"><span data-stu-id="6d81c-103">Uninstallation Instructions</span></span>

## <a name="using-command-prompt"></a><span data-ttu-id="6d81c-104">Verwenden der Eingabeaufforderung</span><span class="sxs-lookup"><span data-stu-id="6d81c-104">Using Command Prompt</span></span>

1. <span data-ttu-id="6d81c-105">Öffnen Sie die **Eingabeaufforderung**.</span><span class="sxs-lookup"><span data-stu-id="6d81c-105">Open **Command Prompt.**</span></span>
2. <span data-ttu-id="6d81c-106">Führen Sie das [eigenständige Windows Update-Startprogramm](https://support.microsoft.com/kb/934307) wie unten dargestellt aus:</span><span class="sxs-lookup"><span data-stu-id="6d81c-106">Run the [Windows Update Standalone Launcher](https://support.microsoft.com/kb/934307) as shown below:</span></span>

<span data-ttu-id="6d81c-107">Unter Windows Server 2012 R2 und Windows 8.1:</span><span class="sxs-lookup"><span data-stu-id="6d81c-107">On Windows Server 2012 R2 and Windows 8.1:</span></span>

```powershell
wusa /uninstall /kb:3134758
```

<span data-ttu-id="6d81c-108">Unter Windows Server 2012:</span><span class="sxs-lookup"><span data-stu-id="6d81c-108">On Windows Server 2012:</span></span>

```powershell
wusa /uninstall /kb:3134759
```

<span data-ttu-id="6d81c-109">Unter Windows Server 2008 R2 SP1 und Windows 7 SP1:</span><span class="sxs-lookup"><span data-stu-id="6d81c-109">On Windows Server 2008 R2 SP1 and Windows 7 SP1:</span></span>

```powershell
wusa /uninstall /kb:3134760
```

## <a name="using-control-panel"></a><span data-ttu-id="6d81c-110">Über die Systemsteuerung</span><span class="sxs-lookup"><span data-stu-id="6d81c-110">Using Control Panel</span></span>

1. <span data-ttu-id="6d81c-111">Öffnen Sie die **Systemsteuerung**.</span><span class="sxs-lookup"><span data-stu-id="6d81c-111">Open **Control Panel.**</span></span>
2. <span data-ttu-id="6d81c-112">Öffnen Sie **Programme** und dann **Programm deinstallieren**.</span><span class="sxs-lookup"><span data-stu-id="6d81c-112">Open **Programs**, then open **Uninstall a program.**</span></span>
3. <span data-ttu-id="6d81c-113">Klicken Sie auf **Installierte Updates anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="6d81c-113">Click **View installed updates.**</span></span>
4. <span data-ttu-id="6d81c-114">Wählen Sie in der Liste der installierten Updates **Windows Management Framework 5.0** aus.</span><span class="sxs-lookup"><span data-stu-id="6d81c-114">Select **Windows Management Framework 5.0** from the list of installed updates.</span></span> <span data-ttu-id="6d81c-115">Dies entspricht *KB3134758*, *KB3134759* oder *KB3134760*.</span><span class="sxs-lookup"><span data-stu-id="6d81c-115">This corresponds to *KB3134758*, *KB3134759*, or *KB3134760*.</span></span> <span data-ttu-id="6d81c-116">Klicken Sie auf **Deinstallieren**.</span><span class="sxs-lookup"><span data-stu-id="6d81c-116">Click **Uninstall.**</span></span>
