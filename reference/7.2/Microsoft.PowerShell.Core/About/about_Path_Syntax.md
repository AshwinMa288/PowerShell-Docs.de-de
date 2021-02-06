---
description: Beschreibt die Namen Formate für vollständige und relative Pfadnamen in PowerShell.
Locale: en-US
ms.date: 06/09/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_path_syntax?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Path_Syntax
ms.openlocfilehash: 9a95865d67dc15bf79762987622b702b14faf6c6
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99600725"
---
# <a name="about-path-syntax"></a><span data-ttu-id="c708b-103">Informationen zur Pfad Syntax</span><span class="sxs-lookup"><span data-stu-id="c708b-103">About Path Syntax</span></span>

## <a name="short-description"></a><span data-ttu-id="c708b-104">KURZE BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="c708b-104">SHORT DESCRIPTION</span></span>
<span data-ttu-id="c708b-105">Beschreibt die Namen Formate für vollständige und relative Pfadnamen in PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c708b-105">Describes the full and relative path name formats in  PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="c708b-106">LANGE BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="c708b-106">LONG DESCRIPTION</span></span>

<span data-ttu-id="c708b-107">Alle Elemente in einem Datenspeicher, auf die über einen PowerShell-Anbieter zugegriffen werden kann, können durch ihre Pfadnamen eindeutig identifiziert werden.</span><span class="sxs-lookup"><span data-stu-id="c708b-107">All items in a data store accessible through a PowerShell provider can be uniquely identified by their path names.</span></span> <span data-ttu-id="c708b-108">Ein Pfadname ist eine Kombination aus Elementname, Container und unter Containern, in der sich das Element befindet, und dem PowerShell-Laufwerk, auf das die Container zugreifen.</span><span class="sxs-lookup"><span data-stu-id="c708b-108">A path name is a combination of the item name, the container and subcontainers in which the item is located, and the PowerShell drive through which the containers are accessed.</span></span>

<span data-ttu-id="c708b-109">In PowerShell sind Pfadnamen in einen von zwei Typen unterteilt: voll qualifiziert und relativ.</span><span class="sxs-lookup"><span data-stu-id="c708b-109">In PowerShell, path names are divided into one of two types: fully qualified and relative.</span></span> <span data-ttu-id="c708b-110">Ein voll qualifizierter Pfadname besteht aus allen Elementen, die einen Pfad bilden.</span><span class="sxs-lookup"><span data-stu-id="c708b-110">A fully qualified path name consists of all elements that make up a path.</span></span> <span data-ttu-id="c708b-111">Die folgende Syntax zeigt die Elemente in einem voll qualifizierten Pfadnamen:</span><span class="sxs-lookup"><span data-stu-id="c708b-111">The following syntax shows the elements in a fully qualified path name:</span></span>

```powershell
[<provider>::]<drive>:[\<container>[\<subcontainer>...]]\<item>
```

<span data-ttu-id="c708b-112">Der \<provider\> Platzhalter bezieht sich auf den PowerShell-Anbieter, über den Sie auf den Datenspeicher zugreifen.</span><span class="sxs-lookup"><span data-stu-id="c708b-112">The \<provider\> placeholder refers to the PowerShell provider through which you access the data store.</span></span> <span data-ttu-id="c708b-113">Beispielsweise können Sie mit dem File System-Anbieter auf die Dateien und Verzeichnisse auf dem Computer zugreifen.</span><span class="sxs-lookup"><span data-stu-id="c708b-113">For example, the FileSystem provider allows you to access the files and directories on your computer.</span></span> <span data-ttu-id="c708b-114">Dieses Element der Syntax ist optional und wird nie benötigt, da die Laufwerks Namen in allen Anbietern eindeutig sind.</span><span class="sxs-lookup"><span data-stu-id="c708b-114">This element of the syntax is optional and is never needed because the drive names are unique across all providers.</span></span>

<span data-ttu-id="c708b-115">Der \<drive\> Platzhalter bezieht sich auf das PowerShell-Laufwerk, das von einem bestimmten PowerShell-Anbieter unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="c708b-115">The \<drive\> placeholder refers to the PowerShell drive that is supported by a particular PowerShell provider.</span></span> <span data-ttu-id="c708b-116">Im Fall des File System-Anbieters werden die PowerShell-Laufwerke den Windows-Laufwerken zugeordnet, die auf Ihrem System konfiguriert sind.</span><span class="sxs-lookup"><span data-stu-id="c708b-116">In the case of the FileSystem provider, the PowerShell drives map to the Windows drives that are configured on your system.</span></span> <span data-ttu-id="c708b-117">Wenn Ihr System beispielsweise ein Laufwerk A: und Laufwerk C: enthält, erstellt der File System-Anbieter die gleichen Laufwerke in PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c708b-117">For example, if your system includes an A: drive and a C: drive, the FileSystem provider creates the same drives in PowerShell.</span></span>

<span data-ttu-id="c708b-118">Nachdem Sie das Laufwerk angegeben haben, müssen Sie alle Container und unter Container angeben, in denen das Element enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="c708b-118">After you have specified the drive, you must specify any containers and subcontainers that contain the item.</span></span> <span data-ttu-id="c708b-119">Die Container müssen in der hierarchischen Reihenfolge angegeben werden, in der Sie im Datenspeicher vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="c708b-119">The containers must be specified in the hierarchical order in which they exist in the data store.</span></span> <span data-ttu-id="c708b-120">Anders ausgedrückt: Sie müssen mit dem übergeordneten Container, dem untergeordneten Container in diesem übergeordneten Container usw. beginnen.</span><span class="sxs-lookup"><span data-stu-id="c708b-120">In other words, you must start with the parent container, then the child container in that parent container, and so on.</span></span> <span data-ttu-id="c708b-121">Außerdem muss jedem Container ein umgekehrter Schrägstrich vorangestellt werden.</span><span class="sxs-lookup"><span data-stu-id="c708b-121">In addition, each container must be preceded by a backslash.</span></span> <span data-ttu-id="c708b-122">(Beachten Sie, dass Sie mithilfe von PowerShell Schrägstriche für die Kompatibilität mit anderen powershells verwenden können.)</span><span class="sxs-lookup"><span data-stu-id="c708b-122">(Note that PowerShell allows you to use forward slashes for compatibility with other PowerShells.)</span></span>

<span data-ttu-id="c708b-123">Nachdem der Container und die Subcontainer angegeben wurden, müssen Sie den Elementnamen angeben, dem ein umgekehrter Schrägstrich vorangestellt ist.</span><span class="sxs-lookup"><span data-stu-id="c708b-123">After the container and subcontainers have been specified, you must provide the item name, preceded by a backslash.</span></span> <span data-ttu-id="c708b-124">Der voll qualifizierte Pfadname für die Shell.dll-Datei im Verzeichnis "C: \\ Windows System32" lautet beispielsweise \\ wie folgt:</span><span class="sxs-lookup"><span data-stu-id="c708b-124">For example, the fully qualified path name for the Shell.dll file in the C:\\Windows\\System32 directory is as follows:</span></span>

```powershell
C:\Windows\System32\Shell.dll
```

<span data-ttu-id="c708b-125">In diesem Fall ist das Laufwerk, über das auf die Container zugegriffen wird, Laufwerk C:, der Container der obersten Ebene ist Windows, der unter Container ist System32 (befindet sich im Windows-Container), und das Element wird Shell.dll.</span><span class="sxs-lookup"><span data-stu-id="c708b-125">In this case, the drive through which the containers are accessed is the C: drive, the top-level container is Windows, the subcontainer is System32 (located within the Windows container), and the item is Shell.dll.</span></span>

<span data-ttu-id="c708b-126">In einigen Situationen müssen Sie keinen voll qualifizierten Pfadnamen angeben und können stattdessen einen relativen Pfadnamen verwenden.</span><span class="sxs-lookup"><span data-stu-id="c708b-126">In some situations, you do not need to specify a fully qualified path name and can instead use a relative path name.</span></span> <span data-ttu-id="c708b-127">Ein relativer Pfadname basiert auf dem aktuellen Arbeits Speicherort.</span><span class="sxs-lookup"><span data-stu-id="c708b-127">A relative path name is based on the current working location.</span></span> <span data-ttu-id="c708b-128">Mit PowerShell können Sie ein Element auf der Grundlage seiner Position relativ zum aktuellen Arbeits Speicherort identifizieren.</span><span class="sxs-lookup"><span data-stu-id="c708b-128">PowerShell allows you to identify an item based on its location relative to the current working location.</span></span> <span data-ttu-id="c708b-129">Sie können mit Sonderzeichen relative Pfadnamen angeben.</span><span class="sxs-lookup"><span data-stu-id="c708b-129">You can specify relative path names by using special characters.</span></span> <span data-ttu-id="c708b-130">In der folgenden Tabelle werden die einzelnen Zeichen beschrieben und Beispiele für relative Pfadnamen und voll qualifizierte Pfadnamen bereitstellt.</span><span class="sxs-lookup"><span data-stu-id="c708b-130">The following table describes each of these characters and provides examples of relative path names and fully qualified path names.</span></span> <span data-ttu-id="c708b-131">Die Beispiele in der Tabelle basieren auf dem aktuellen Arbeitsverzeichnis, das auf "c:\Windows" festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="c708b-131">The examples in the table are based on the current working directory being set to C:\Windows.</span></span>

|<span data-ttu-id="c708b-132">Symbol</span><span class="sxs-lookup"><span data-stu-id="c708b-132">Symbol</span></span>|<span data-ttu-id="c708b-133">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="c708b-133">Description</span></span>               |<span data-ttu-id="c708b-134">Relativer Pfad</span><span class="sxs-lookup"><span data-stu-id="c708b-134">Relative path</span></span>    |<span data-ttu-id="c708b-135">Vollständiger Pfad</span><span class="sxs-lookup"><span data-stu-id="c708b-135">Full path</span></span>          |
|------|--------------------------|-----------------|-------------------|
|<span data-ttu-id="c708b-136">.</span><span class="sxs-lookup"><span data-stu-id="c708b-136">.</span></span>     |<span data-ttu-id="c708b-137">Aktueller Speicherort</span><span class="sxs-lookup"><span data-stu-id="c708b-137">Current location</span></span>          |<span data-ttu-id="c708b-138">.\\ Anlage</span><span class="sxs-lookup"><span data-stu-id="c708b-138">.\\System</span></span>        |<span data-ttu-id="c708b-139">c: \\ Windows- \\ System</span><span class="sxs-lookup"><span data-stu-id="c708b-139">c:\\Windows\\System</span></span>|
|<span data-ttu-id="c708b-140">..</span><span class="sxs-lookup"><span data-stu-id="c708b-140">..</span></span>    |<span data-ttu-id="c708b-141">Übergeordnetes Element des aktuellen Speicher Orts</span><span class="sxs-lookup"><span data-stu-id="c708b-141">Parent of current location</span></span>|<span data-ttu-id="c708b-142">..\\ Programmdateien</span><span class="sxs-lookup"><span data-stu-id="c708b-142">..\\Program Files</span></span>|<span data-ttu-id="c708b-143">c: \\ Programmdateien</span><span class="sxs-lookup"><span data-stu-id="c708b-143">c:\\Program Files</span></span>  |
|\     |<span data-ttu-id="c708b-144">Laufwerks Stamm der aktuellen</span><span class="sxs-lookup"><span data-stu-id="c708b-144">Drive root of current</span></span>     |<span data-ttu-id="c708b-145">\\Programmdateien</span><span class="sxs-lookup"><span data-stu-id="c708b-145">\\Program Files</span></span>  |<span data-ttu-id="c708b-146">c: \\ Programmdateien</span><span class="sxs-lookup"><span data-stu-id="c708b-146">c:\\Program Files</span></span>  |
|      |<span data-ttu-id="c708b-147">location</span><span class="sxs-lookup"><span data-stu-id="c708b-147">location</span></span>                  |                 |                   |
|<span data-ttu-id="c708b-148">gar</span><span class="sxs-lookup"><span data-stu-id="c708b-148">[none]</span></span>|<span data-ttu-id="c708b-149">Keine Sonderzeichen</span><span class="sxs-lookup"><span data-stu-id="c708b-149">No special characters</span></span>     |<span data-ttu-id="c708b-150">System</span><span class="sxs-lookup"><span data-stu-id="c708b-150">System</span></span>           |<span data-ttu-id="c708b-151">c: \\ Windows- \\ System</span><span class="sxs-lookup"><span data-stu-id="c708b-151">c:\\Windows\\System</span></span>|

<span data-ttu-id="c708b-152">Wenn Sie einen Pfadnamen in einem Befehl verwenden, geben Sie diesen Namen auf die gleiche Weise ein, unabhängig davon, ob Sie einen voll qualifizierten Pfadnamen oder einen relativen Pfadnamen verwenden.</span><span class="sxs-lookup"><span data-stu-id="c708b-152">When using a path name in a command, you enter that name in the same way whether you use a fully qualified path name or a relative one.</span></span> <span data-ttu-id="c708b-153">Nehmen Sie beispielsweise an, dass das aktuelle Arbeitsverzeichnis c:\Windows.</span><span class="sxs-lookup"><span data-stu-id="c708b-153">For example, suppose that your current working directory is C:\Windows.</span></span> <span data-ttu-id="c708b-154">Mit dem folgenden Get-ChildItem Befehl werden alle Elemente im Verzeichnis "c:\techdocs" abgerufen:</span><span class="sxs-lookup"><span data-stu-id="c708b-154">The following Get-ChildItem command retrieves all items in the C:\Techdocs directory:</span></span>

```powershell
Get-ChildItem \techdocs
```

<span data-ttu-id="c708b-155">Der umgekehrte Schrägstrich gibt an, dass der Laufwerks Stamm des aktuellen Arbeitsspeicher Orts verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="c708b-155">The backslash indicates that the drive root of the current working location should be used.</span></span> <span data-ttu-id="c708b-156">Da das Arbeitsverzeichnis "c: \\ Windows" ist, ist der Laufwerks Stamm das Laufwerk "c:".</span><span class="sxs-lookup"><span data-stu-id="c708b-156">Because the working directory is C:\\Windows, the drive root is the C: drive.</span></span> <span data-ttu-id="c708b-157">Da sich das techdocs-Verzeichnis außerhalb des Stamms befindet, müssen Sie nur den umgekehrten Schrägstrich angeben.</span><span class="sxs-lookup"><span data-stu-id="c708b-157">Because the techdocs directory is located off the root, you need to specify only the backslash.</span></span>

<span data-ttu-id="c708b-158">Sie können dieselben Ergebnisse erzielen, indem Sie den folgenden Befehl verwenden:</span><span class="sxs-lookup"><span data-stu-id="c708b-158">You can achieve the same results by using the following command:</span></span>

```powershell
Get-ChildItem c:\techdocs
```

<span data-ttu-id="c708b-159">Unabhängig davon, ob Sie einen voll qualifizierten Pfadnamen oder einen relativen Pfadnamen verwenden, ist ein Pfadname nicht nur wichtig, da er ein Element sucht, sondern auch, weil das Element eindeutig identifiziert wird, auch wenn dieses Element denselben Namen wie ein anderes Element in einem anderen Container hat.</span><span class="sxs-lookup"><span data-stu-id="c708b-159">Regardless of whether you use a fully qualified path name or a relative path name, a path name is important not only because it locates an item but also because it uniquely identifies the item even if that item shares the same name as another item in a different container.</span></span>

<span data-ttu-id="c708b-160">Nehmen Sie beispielsweise an, dass Sie über zwei Dateien mit dem Namen Results.txt verfügen.</span><span class="sxs-lookup"><span data-stu-id="c708b-160">For instance, suppose that you have two files that are each named Results.txt.</span></span>
<span data-ttu-id="c708b-161">Die erste Datei befindet sich in einem Verzeichnis mit dem Namen "c: \\ techdocs \\ Jan", und die zweite Datei befindet sich in einem Verzeichnis mit dem Namen "c: \\ techdocs \\ Feb". Der Pfadname für die erste Datei (c: \\ techdocs \\ Jan \\Results.txt) und der Pfadname für die zweite Datei (c: \\ techdocs \\ Feb \\Results.txt) ermöglichen es Ihnen, die beiden Dateien eindeutig zu unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="c708b-161">The first file is in a directory named C:\\Techdocs\\Jan, and the second file is in a directory named C:\\Techdocs\\Feb. The path name for the first file (C:\\Techdocs\\Jan\\Results.txt) and the path name for the second file (C:\\Techdocs\\Feb\\Results.txt) allow you to clearly distinguish between the two files.</span></span>

## <a name="see-also"></a><span data-ttu-id="c708b-162">SIEHE AUCH</span><span class="sxs-lookup"><span data-stu-id="c708b-162">SEE ALSO</span></span>

[<span data-ttu-id="c708b-163">about_Locations</span><span class="sxs-lookup"><span data-stu-id="c708b-163">about_Locations</span></span>](about_Locations.md)
