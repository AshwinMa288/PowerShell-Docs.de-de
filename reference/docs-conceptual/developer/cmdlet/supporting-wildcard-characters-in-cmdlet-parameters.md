---
ms.date: 08/26/2019
ms.topic: reference
title: Unterstützung für Platzhalter in Cmdlet-Parametern
description: Unterstützung für Platzhalter in Cmdlet-Parametern
ms.openlocfilehash: 06693c62cd2613050bdeb9d6b12ad6e9597a9894
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92646383"
---
# <a name="supporting-wildcard-characters-in-cmdlet-parameters"></a><span data-ttu-id="b3ede-103">Unterstützung für Platzhalter in Cmdlet-Parametern</span><span class="sxs-lookup"><span data-stu-id="b3ede-103">Supporting Wildcard Characters in Cmdlet Parameters</span></span>

<span data-ttu-id="b3ede-104">Häufig müssen Sie ein Cmdlet so entwerfen, dass es für eine Gruppe von Ressourcen und nicht für eine einzelne Ressource ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="b3ede-104">Often, you will have to design a cmdlet to run against a group of resources rather than against a single resource.</span></span> <span data-ttu-id="b3ede-105">Beispielsweise muss ein Cmdlet möglicherweise alle Dateien in einem Datenspeicher mit dem gleichen Namen oder der gleichen Erweiterung suchen.</span><span class="sxs-lookup"><span data-stu-id="b3ede-105">For example, a cmdlet might need to locate all the files in a data store that have the same name or extension.</span></span> <span data-ttu-id="b3ede-106">Beim Entwerfen eines Cmdlets, das für eine Gruppe von Ressourcen ausgeführt werden soll, müssen Sie Unterstützung für Platzhalter Zeichen bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="b3ede-106">You must provide support for wildcard characters when you design a cmdlet that will be run against a group of resources.</span></span>

> [!NOTE]
> <span data-ttu-id="b3ede-107">Die Verwendung von Platzhalter Zeichen wird manchmal als " *glob"* bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="b3ede-107">Using wildcard characters is sometimes referred to as *globbing*.</span></span>

## <a name="windows-powershell-cmdlets-that-use-wildcards"></a><span data-ttu-id="b3ede-108">Windows PowerShell-Cmdlets, die Platzhalter verwenden</span><span class="sxs-lookup"><span data-stu-id="b3ede-108">Windows PowerShell Cmdlets That Use Wildcards</span></span>

 <span data-ttu-id="b3ede-109">Viele Windows PowerShell-Cmdlets unterstützen Platzhalter Zeichen für Ihre Parameterwerte.</span><span class="sxs-lookup"><span data-stu-id="b3ede-109">Many Windows PowerShell cmdlets support wildcard characters for their parameter values.</span></span> <span data-ttu-id="b3ede-110">Beispielsweise unterstützt fast jedes Cmdlet mit dem-Parameter oder dem-Parameter Platzhalter `Name` `Path` Zeichen für diese Parameter.</span><span class="sxs-lookup"><span data-stu-id="b3ede-110">For example, almost every cmdlet that has a `Name` or `Path` parameter supports wildcard characters for these parameters.</span></span> <span data-ttu-id="b3ede-111">(Obwohl die meisten Cmdlets, die über einen Parameter verfügen, `Path` auch über einen `LiteralPath` Parameter verfügen, der keine Platzhalter Zeichen unterstützt.) Der folgende Befehl zeigt, wie ein Platzhalter Zeichen verwendet wird, um alle Cmdlets in der aktuellen Sitzung zurückzugeben, deren Name das Get-Verb enthält.</span><span class="sxs-lookup"><span data-stu-id="b3ede-111">(Although most cmdlets that have a `Path` parameter also have a `LiteralPath` parameter that does not support wildcard characters.) The following command shows how a wildcard character is used to return all the cmdlets in the current session whose name contains the Get verb.</span></span>

 `Get-Command get-*`

## <a name="supported-wildcard-characters"></a><span data-ttu-id="b3ede-112">Unterstützte Platzhalter Zeichen</span><span class="sxs-lookup"><span data-stu-id="b3ede-112">Supported Wildcard Characters</span></span>

<span data-ttu-id="b3ede-113">Windows PowerShell unterstützt die folgenden Platzhalter Zeichen.</span><span class="sxs-lookup"><span data-stu-id="b3ede-113">Windows PowerShell supports the following wildcard characters.</span></span>

| <span data-ttu-id="b3ede-114">Platzhalter</span><span class="sxs-lookup"><span data-stu-id="b3ede-114">Wildcard</span></span> |                             <span data-ttu-id="b3ede-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="b3ede-115">Description</span></span>                             |  <span data-ttu-id="b3ede-116">Beispiel</span><span class="sxs-lookup"><span data-stu-id="b3ede-116">Example</span></span>   |     <span data-ttu-id="b3ede-117">Treffer</span><span class="sxs-lookup"><span data-stu-id="b3ede-117">Matches</span></span>      | <span data-ttu-id="b3ede-118">Stimmt nicht überein mit</span><span class="sxs-lookup"><span data-stu-id="b3ede-118">Does not match</span></span> |
| -------- | ------------------------------------------------------------------- | ---------- | ---------------- | -------------- |
| *        | <span data-ttu-id="b3ede-119">Entspricht 0 (null) oder mehr Zeichen, beginnend an der angegebenen Position.</span><span class="sxs-lookup"><span data-stu-id="b3ede-119">Matches zero or more characters, starting at the specified position</span></span> | `a*`       | <span data-ttu-id="b3ede-120">A, AG, Apple</span><span class="sxs-lookup"><span data-stu-id="b3ede-120">A, ag, Apple</span></span>     |                |
| <span data-ttu-id="b3ede-121">?</span><span class="sxs-lookup"><span data-stu-id="b3ede-121">?</span></span>        | <span data-ttu-id="b3ede-122">Entspricht einem beliebigen Zeichen an der angegebenen Position.</span><span class="sxs-lookup"><span data-stu-id="b3ede-122">Matches any character at the specified position</span></span>                     | `?n`       | <span data-ttu-id="b3ede-123">Ein, in, ein</span><span class="sxs-lookup"><span data-stu-id="b3ede-123">An, in, on</span></span>       | <span data-ttu-id="b3ede-124">an</span><span class="sxs-lookup"><span data-stu-id="b3ede-124">ran</span></span>            |
| <span data-ttu-id="b3ede-125">[ ]</span><span class="sxs-lookup"><span data-stu-id="b3ede-125">[ ]</span></span>      | <span data-ttu-id="b3ede-126">Entspricht einem Zeichenbereich.</span><span class="sxs-lookup"><span data-stu-id="b3ede-126">Matches a range of characters</span></span>                                       | `[a-l]ook` | <span data-ttu-id="b3ede-127">Buch, Kochen, ansehen</span><span class="sxs-lookup"><span data-stu-id="b3ede-127">book, cook, look</span></span> | <span data-ttu-id="b3ede-128">Nook, hat</span><span class="sxs-lookup"><span data-stu-id="b3ede-128">nook, took</span></span>     |
| <span data-ttu-id="b3ede-129">[ ]</span><span class="sxs-lookup"><span data-stu-id="b3ede-129">[ ]</span></span>      | <span data-ttu-id="b3ede-130">Entspricht den angegebenen Zeichen</span><span class="sxs-lookup"><span data-stu-id="b3ede-130">Matches the specified characters</span></span>                                    | `[bn]ook`  | <span data-ttu-id="b3ede-131">Buch, Nook</span><span class="sxs-lookup"><span data-stu-id="b3ede-131">book, nook</span></span>       | <span data-ttu-id="b3ede-132">Kochen, sehen</span><span class="sxs-lookup"><span data-stu-id="b3ede-132">cook, look</span></span>     |

<span data-ttu-id="b3ede-133">Wenn Sie Cmdlets entwerfen, die Platzhalter Zeichen unterstützen, lassen Sie Kombinationen von Platzhalter Zeichen zu.</span><span class="sxs-lookup"><span data-stu-id="b3ede-133">When you design cmdlets that support wildcard characters, allow for combinations of wildcard characters.</span></span> <span data-ttu-id="b3ede-134">Der folgende Befehl verwendet z. b. das `Get-ChildItem` Cmdlet zum Abrufen aller txt-Dateien, die sich im Ordner c:\techdocs befinden und mit den Buchstaben "a" bis "l" beginnen.</span><span class="sxs-lookup"><span data-stu-id="b3ede-134">For example, the following command uses the `Get-ChildItem` cmdlet to retrieve all the .txt files that are in the c:\Techdocs folder and that begin with the letters "a" through "l."</span></span>

`Get-ChildItem c:\techdocs\[a-l]\*.txt`

<span data-ttu-id="b3ede-135">Der vorherige Befehl verwendet den Bereichs `[a-l]` Platzhalter, um anzugeben, dass der Dateiname mit den Zeichen "a" bis "l" beginnen soll, und verwendet das `*` Platzhalter Zeichen als Platzhalter für alle Zeichen zwischen dem ersten Buchstaben des Datei namens und der Erweiterung " **. txt** ".</span><span class="sxs-lookup"><span data-stu-id="b3ede-135">The previous command uses the range wildcard `[a-l]` to specify that the file name should begin with the characters "a" through "l" and uses the `*` wildcard character as a placeholder for any characters between the first letter of the filename and the **.txt** extension.</span></span>

<span data-ttu-id="b3ede-136">Im folgenden Beispiel wird ein Bereichs Halter Muster verwendet, das den Buchstaben "d" ausschließt, aber alle anderen Buchstaben von "a" bis "f" umfasst.</span><span class="sxs-lookup"><span data-stu-id="b3ede-136">The following example uses a range wildcard pattern that excludes the letter "d" but includes all the other letters from "a" through "f."</span></span>

`Get-ChildItem c:\techdocs\[a-cef]\*.txt`

## <a name="handling-literal-characters-in-wildcard-patterns"></a><span data-ttu-id="b3ede-137">Verarbeiten von Literalzeichen in Platzhalter Mustern</span><span class="sxs-lookup"><span data-stu-id="b3ede-137">Handling Literal Characters in Wildcard Patterns</span></span>

<span data-ttu-id="b3ede-138">Wenn das von Ihnen angegebene Platzhalter Muster Literalzeichen enthält, die nicht als Platzhalter Zeichen interpretiert werden sollen, verwenden Sie das Graviszeichen-Zeichen ( `` ` `` ) als Escapezeichen.</span><span class="sxs-lookup"><span data-stu-id="b3ede-138">If the wildcard pattern you specify contains literal characters that should not be interpretted as wildcard characters, use the backtick character (`` ` ``) as an escape character.</span></span> <span data-ttu-id="b3ede-139">Wenn Sie die Literalzeichen int der PowerShell-API angeben, verwenden Sie einen einzigen Backtick.</span><span class="sxs-lookup"><span data-stu-id="b3ede-139">When you specify literal characters int the PowerShell API, use a single backtick.</span></span> <span data-ttu-id="b3ede-140">Wenn Sie an der PowerShell-Eingabeaufforderung Literalzeichen angeben, verwenden Sie zwei Backticks.</span><span class="sxs-lookup"><span data-stu-id="b3ede-140">When you specify literal characters at the PowerShell command prompt, use two backticks.</span></span>

<span data-ttu-id="b3ede-141">Das folgende Muster enthält z. b. zwei eckige Klammern, die wörtlich genommen werden müssen.</span><span class="sxs-lookup"><span data-stu-id="b3ede-141">For example, the following pattern contains two brackets that must be taken literally.</span></span>

<span data-ttu-id="b3ede-142">Wenn Sie in der PowerShell-API verwendet wird, verwenden Sie:</span><span class="sxs-lookup"><span data-stu-id="b3ede-142">When used in the PowerShell API use:</span></span>

- <span data-ttu-id="b3ede-143">"John Smith \` [\* ']"</span><span class="sxs-lookup"><span data-stu-id="b3ede-143">"John Smith \`[\*\`]"</span></span>

<span data-ttu-id="b3ede-144">Wenn Sie von der PowerShell-Eingabeaufforderung verwendet wird:</span><span class="sxs-lookup"><span data-stu-id="b3ede-144">When used from the PowerShell command prompt:</span></span>

- <span data-ttu-id="b3ede-145">"John Smith \` \` [\* \` ']"</span><span class="sxs-lookup"><span data-stu-id="b3ede-145">"John Smith \`\`[\*\`\`]"</span></span>

<span data-ttu-id="b3ede-146">Dieses Muster entspricht "John Smith [Marketing]" oder "John Smith [Development]".</span><span class="sxs-lookup"><span data-stu-id="b3ede-146">This pattern matches "John Smith [Marketing]" or "John Smith [Development]".</span></span> <span data-ttu-id="b3ede-147">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="b3ede-147">For example:</span></span>

```
PS> "John Smith [Marketing]" -like "John Smith ``[*``]"
True

PS> "John Smith [Development]" -like "John Smith ``[*``]"
True
```

## <a name="cmdlet-output-and-wildcard-characters"></a><span data-ttu-id="b3ede-148">Cmdlet-Ausgabe und Platzhalter Zeichen</span><span class="sxs-lookup"><span data-stu-id="b3ede-148">Cmdlet Output and Wildcard Characters</span></span>

<span data-ttu-id="b3ede-149">Wenn Cmdlet-Parameter Platzhalter Zeichen unterstützen, generiert der Vorgang normalerweise eine Array Ausgabe.</span><span class="sxs-lookup"><span data-stu-id="b3ede-149">When cmdlet parameters support wildcard characters, the operation usually generates an array output.</span></span>
<span data-ttu-id="b3ede-150">Gelegentlich ist es nicht sinnvoll, eine Array Ausgabe zu unterstützen, da der Benutzer möglicherweise nur ein einzelnes Element verwendet.</span><span class="sxs-lookup"><span data-stu-id="b3ede-150">Occasionally, it makes no sense to support an array output because the user might use only a single item.</span></span> <span data-ttu-id="b3ede-151">Beispielsweise `Set-Location` unterstützt das Cmdlet die Array Ausgabe nicht, da der Benutzer nur einen einzigen Speicherort festlegt.</span><span class="sxs-lookup"><span data-stu-id="b3ede-151">For example, the `Set-Location` cmdlet does not support array output because the user sets only a single location.</span></span> <span data-ttu-id="b3ede-152">In diesem Fall unterstützt das Cmdlet weiterhin Platzhalter Zeichen, aber es erzwingt die Auflösung an einem einzelnen Speicherort.</span><span class="sxs-lookup"><span data-stu-id="b3ede-152">In this instance, the cmdlet still supports wildcard characters, but it forces resolution to a single location.</span></span>

## <a name="see-also"></a><span data-ttu-id="b3ede-153">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b3ede-153">See Also</span></span>

[<span data-ttu-id="b3ede-154">Schreiben eines Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="b3ede-154">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)

[<span data-ttu-id="b3ede-155">Wildcardpattern-Klasse</span><span class="sxs-lookup"><span data-stu-id="b3ede-155">WildcardPattern Class</span></span>](/dotnet/api/system.management.automation.wildcardpattern)
