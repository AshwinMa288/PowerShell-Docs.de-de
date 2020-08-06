---
title: Windows PowerShell-Sitzungs Status | Microsoft-Dokumentation
ms.date: 09/13/2016
helpviewer_keywords:
- Cmdlets [PowerShell], session state
- session state [PowerShell]
ms.openlocfilehash: 7436e3ebd0e099ead81f9fea01a0a2994b982213
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87783941"
---
# <a name="windows-powershell-session-state"></a><span data-ttu-id="7849a-102">Windows PowerShell-Sitzungszustand</span><span class="sxs-lookup"><span data-stu-id="7849a-102">Windows PowerShell Session State</span></span>

<span data-ttu-id="7849a-103">Der Sitzungs Status bezieht sich auf die aktuelle Konfiguration einer Windows PowerShell-Sitzung oder eines Windows PowerShell-Moduls.</span><span class="sxs-lookup"><span data-stu-id="7849a-103">Session state refers to the current configuration of a Windows PowerShell session or module.</span></span> <span data-ttu-id="7849a-104">Eine Windows PowerShell-Sitzung ist die Betriebsumgebung, die interaktiv vom Befehlszeilen Benutzer oder Programm gesteuert von einer Host Anwendung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="7849a-104">A Windows PowerShell session is the operational environment that is used interactively by the command-line user or programmatically by a host application.</span></span> <span data-ttu-id="7849a-105">Der Sitzungszustand für eine Sitzung wird als globaler Sitzungszustand bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="7849a-105">The session state for a session is referred to as the global session state.</span></span>

<span data-ttu-id="7849a-106">Aus Sicht des Entwicklers bezieht sich eine Windows PowerShell-Sitzung auf die Zeit zwischen dem Öffnen eines Windows PowerShell-Runspace durch eine Host Anwendung und dem Schließen des Runspace.</span><span class="sxs-lookup"><span data-stu-id="7849a-106">From a developer perspective, a Windows PowerShell session refers to the time between when a host application opens a Windows PowerShell runspace and when it closes the runspace.</span></span> <span data-ttu-id="7849a-107">Anders betrachtet, ist die Sitzung die Lebensdauer einer Instanz der Windows PowerShell-Engine, die aufgerufen wird, während der Runspace vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="7849a-107">Looked at another way, the session is the lifetime of an instance of the Windows PowerShell engine that is invoked while the runspace exists.</span></span>

## <a name="module-session-state"></a><span data-ttu-id="7849a-108">Modul Sitzungs Status</span><span class="sxs-lookup"><span data-stu-id="7849a-108">Module Session State</span></span>

<span data-ttu-id="7849a-109">Modul Sitzungs Zustände werden immer dann erstellt, wenn das Modul oder eines seiner in die Sitzung importierten Module importiert wird.</span><span class="sxs-lookup"><span data-stu-id="7849a-109">Module session states are created whenever the module or one of its nested modules is imported into the session.</span></span> <span data-ttu-id="7849a-110">Wenn ein Modul ein Element, z. b. ein Cmdlet, eine Funktion oder ein Skript, exportiert, wird dem globalen Sitzungs Status der Sitzung ein Verweis auf dieses Element hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="7849a-110">When a module exports an element such as a cmdlet, function, or script, a reference to that element is added to the global session state of the session.</span></span> <span data-ttu-id="7849a-111">Wenn das Element ausgeführt wird, wird es jedoch innerhalb des Sitzungs Status des Moduls ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="7849a-111">However, when the element is run, it is executed within the session state of the module.</span></span>

## <a name="session-state-data"></a><span data-ttu-id="7849a-112">Sitzungszustandsdaten</span><span class="sxs-lookup"><span data-stu-id="7849a-112">Session-State Data</span></span>

<span data-ttu-id="7849a-113">Sitzungszustandsdaten können öffentlich oder privat sein.</span><span class="sxs-lookup"><span data-stu-id="7849a-113">Session state data can be public or private.</span></span> <span data-ttu-id="7849a-114">Öffentliche Daten sind für Aufrufe außerhalb des Sitzungs Zustands verfügbar, während private Daten nur für Anrufe innerhalb des Sitzungs Zustands verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="7849a-114">Public data is available to calls from outside the session state while private data is available only to calls from within the session state.</span></span> <span data-ttu-id="7849a-115">Ein Modul kann z. b. über eine private Funktion verfügen, die nur vom Modul oder nur intern von einem öffentlichen, exportierten Element aufgerufen werden kann.</span><span class="sxs-lookup"><span data-stu-id="7849a-115">For example, a module can have a private function that can be called only by the module or only internally by a public element that has been exported.</span></span> <span data-ttu-id="7849a-116">Dies ist vergleichbar mit den privaten und öffentlichen Membern eines .NET Framework Typs.</span><span class="sxs-lookup"><span data-stu-id="7849a-116">This is similar to the private and public members of a .NET Framework type.</span></span>

<span data-ttu-id="7849a-117">Sitzungszustandsdaten werden von der aktuellen Instanz der Ausführungs-Engine innerhalb des Kontexts der aktuellen Windows PowerShell-Sitzung gespeichert.</span><span class="sxs-lookup"><span data-stu-id="7849a-117">Session-state data is stored by the current instance of the execution engine within the context of the current Windows PowerShell session.</span></span> <span data-ttu-id="7849a-118">Sitzungszustandsdaten bestehen aus den folgenden Elementen:</span><span class="sxs-lookup"><span data-stu-id="7849a-118">Session-state data consists of the following items:</span></span>

- <span data-ttu-id="7849a-119">Pfadinformationen</span><span class="sxs-lookup"><span data-stu-id="7849a-119">Path information</span></span>

- <span data-ttu-id="7849a-120">Laufwerks Informationen</span><span class="sxs-lookup"><span data-stu-id="7849a-120">Drive information</span></span>

- <span data-ttu-id="7849a-121">Informationen zum Windows PowerShell-Anbieter</span><span class="sxs-lookup"><span data-stu-id="7849a-121">Windows PowerShell provider information</span></span>

- <span data-ttu-id="7849a-122">Informationen zu den importierten Modulen und verweisen auf die Modul Elemente (z. b. Cmdlets, Funktionen und Skripts), die vom Modul exportiert werden.</span><span class="sxs-lookup"><span data-stu-id="7849a-122">Information about the imported modules and references to the module elements (such as cmdlets, functions, and scripts) that are exported by the module.</span></span> <span data-ttu-id="7849a-123">Diese Informationen und diese Verweise gelten nur für den globalen Sitzungs Status.</span><span class="sxs-lookup"><span data-stu-id="7849a-123">This information and these references are for the global session state only.</span></span>

- <span data-ttu-id="7849a-124">Informationen zu Sitzungs Zustandsvariablen</span><span class="sxs-lookup"><span data-stu-id="7849a-124">Session-state variable information</span></span>

## <a name="accessing-session-state-data-within-cmdlets"></a><span data-ttu-id="7849a-125">Zugreifen auf Sitzungszustandsdaten innerhalb von Cmdlets</span><span class="sxs-lookup"><span data-stu-id="7849a-125">Accessing Session-State Data Within Cmdlets</span></span>

<span data-ttu-id="7849a-126">Cmdlets können auf Sitzungszustandsdaten entweder indirekt über die [System. Management. Automation. PSCmdlet. SessionState \*](/dotnet/api/System.Management.Automation.PSCmdlet.SessionState) -Eigenschaft der Cmdlet-Klasse oder direkt über die [System. Management. Automation. SessionState](/dotnet/api/System.Management.Automation.SessionState) -Klasse zugreifen.</span><span class="sxs-lookup"><span data-stu-id="7849a-126">Cmdlets can access session-state data either indirectly through the [System.Management.Automation.PSCmdlet.Sessionstate\*](/dotnet/api/System.Management.Automation.PSCmdlet.SessionState) property of the cmdlet class or directly through the [System.Management.Automation.Sessionstate](/dotnet/api/System.Management.Automation.SessionState) class.</span></span> <span data-ttu-id="7849a-127">Die [System. Management. Automation. SessionState](/dotnet/api/System.Management.Automation.SessionState) -Klasse stellt Eigenschaften bereit, die verwendet werden können, um unterschiedliche Typen von Sitzungszustandsdaten zu untersuchen.</span><span class="sxs-lookup"><span data-stu-id="7849a-127">The [System.Management.Automation.Sessionstate](/dotnet/api/System.Management.Automation.SessionState) class provides properties that can be used to investigate different types of session-state data.</span></span>

## <a name="see-also"></a><span data-ttu-id="7849a-128">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="7849a-128">See Also</span></span>

[<span data-ttu-id="7849a-129">System. Management. Automation. PSCmdlet. SessionState</span><span class="sxs-lookup"><span data-stu-id="7849a-129">System.Management.Automation.PSCmdlet.Sessionstate</span></span>](/dotnet/api/System.Management.Automation.PSCmdlet.SessionState)

[<span data-ttu-id="7849a-130">System. Management. Automation. SessionState? Displayproperty = FullName</span><span class="sxs-lookup"><span data-stu-id="7849a-130">System.Management.Automation.Sessionstate?Displayproperty=Fullname</span></span>](/dotnet/api/System.Management.Automation.SessionState)

[<span data-ttu-id="7849a-131">Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="7849a-131">Windows PowerShell Cmdlets</span></span>](./cmdlet-overview.md)

[<span data-ttu-id="7849a-132">Schreiben eines Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="7849a-132">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)

[<span data-ttu-id="7849a-133">Windows PowerShell Shell SDK</span><span class="sxs-lookup"><span data-stu-id="7849a-133">Windows PowerShell Shell SDK</span></span>](../windows-powershell-reference.md)
