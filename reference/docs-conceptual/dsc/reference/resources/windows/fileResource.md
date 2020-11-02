---
ms.date: 07/16/2020
ms.topic: reference
title: DSC-Ressource „File“
description: DSC-Ressource „File“
ms.openlocfilehash: b62b9b80beb1f433715b32b41445dd0a8bb19d84
ms.sourcegitcommit: 196c7f8cd24560cac70c88acc89909f17a86aea9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2020
ms.locfileid: "93142938"
---
# <a name="dsc-file-resource"></a><span data-ttu-id="a6bcd-103">DSC-Ressource „File“</span><span class="sxs-lookup"><span data-stu-id="a6bcd-103">DSC File Resource</span></span>

> <span data-ttu-id="a6bcd-104">Gilt für: Windows PowerShell 4.0, Windows PowerShell 5.x</span><span class="sxs-lookup"><span data-stu-id="a6bcd-104">Applies To: Windows PowerShell 4.0, Windows PowerShell 5.x</span></span>

<span data-ttu-id="a6bcd-105">Die Ressource **File** in Windows PowerShell DSC bietet einen Mechanismus zum Verwalten von Dateien und Verzeichnissen auf einem Zielknoten.</span><span class="sxs-lookup"><span data-stu-id="a6bcd-105">The **File** resource in Windows PowerShell Desired State Configuration (DSC) provides a mechanism to manage files and folders on the target node.</span></span> <span data-ttu-id="a6bcd-106">Der Zielknoten muss auf **DestinationPath** und **SourcePath** zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="a6bcd-106">**DestinationPath** and **SourcePath** must both be accessible by the target Node.</span></span>

[!INCLUDE [Updated DSC Resources](../../../../../includes/dsc-resources.md)]

## <a name="syntax"></a><span data-ttu-id="a6bcd-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="a6bcd-107">Syntax</span></span>

```Syntax
File [string] #ResourceName
{
    DestinationPath = [string]
    [ Attributes = [string[]] { Archive | Hidden | ReadOnly | System }]
    [ Checksum = [string] { CreatedDate | ModifiedDate | SHA-1 | SHA-256 | SHA-512 } ]
    [ Contents = [string] ]
    [ Credential = [PSCredential] ]
    [ Force = [bool] ]
    [ Recurse = [bool] ]
    [ SourcePath = [string] ]
    [ Type = [string] { Directory | File } ]
    [ MatchSource = [bool] ]
    [ DependsOn = [string[]] ]
    [ Ensure = [string] { Absent | Present } ]
    [ PsDscRunAsCredential = [PSCredential] ]
}
```

## <a name="properties"></a><span data-ttu-id="a6bcd-108">Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="a6bcd-108">Properties</span></span>

|<span data-ttu-id="a6bcd-109">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="a6bcd-109">Property</span></span> |<span data-ttu-id="a6bcd-110">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="a6bcd-110">Description</span></span> |
|---|---|
|<span data-ttu-id="a6bcd-111">DestinationPath</span><span class="sxs-lookup"><span data-stu-id="a6bcd-111">DestinationPath</span></span> |<span data-ttu-id="a6bcd-112">Der Speicherort auf dem Zielknoten, den Sie sicherstellen möchten, ist **Present** oder **Absent** mit **Ensure** .</span><span class="sxs-lookup"><span data-stu-id="a6bcd-112">The location, on the target node, you want to ensure is **Present** or **Absent** with **Ensure** .</span></span> |
|<span data-ttu-id="a6bcd-113">Attributes</span><span class="sxs-lookup"><span data-stu-id="a6bcd-113">Attributes</span></span> |<span data-ttu-id="a6bcd-114">Der gewünschte Status der Attribute der Zieldatei oder des Zielverzeichnisses.</span><span class="sxs-lookup"><span data-stu-id="a6bcd-114">The desired state of the attributes for the targeted file or directory.</span></span> <span data-ttu-id="a6bcd-115">Gültige Werte sind _Archive_ , _Hidden_ , _ReadOnly_ und _System_ .</span><span class="sxs-lookup"><span data-stu-id="a6bcd-115">Valid values are _Archive_ , _Hidden_ , _ReadOnly_ , and _System_ .</span></span> |
|<span data-ttu-id="a6bcd-116">Checksum</span><span class="sxs-lookup"><span data-stu-id="a6bcd-116">Checksum</span></span> |<span data-ttu-id="a6bcd-117">Der zu verwendende Prüfsummentyp, wenn bestimmt wird, ob zwei Dateien identisch sind.</span><span class="sxs-lookup"><span data-stu-id="a6bcd-117">The checksum type to use when determining whether two files are the same.</span></span> <span data-ttu-id="a6bcd-118">Gültige Werte: **SHA-1** , **SHA-256** , **SHA-512** , **createdDate** , **modifiedDate** .</span><span class="sxs-lookup"><span data-stu-id="a6bcd-118">Valid values include: **SHA-1** , **SHA-256** , **SHA-512** , **createdDate** , **modifiedDate** .</span></span> |
|<span data-ttu-id="a6bcd-119">Contents</span><span class="sxs-lookup"><span data-stu-id="a6bcd-119">Contents</span></span> |<span data-ttu-id="a6bcd-120">Nur bei Verwendung mit **Type** **File** gültig.</span><span class="sxs-lookup"><span data-stu-id="a6bcd-120">Only valid when used with **Type** **File** .</span></span> <span data-ttu-id="a6bcd-121">Gibt den Inhalt an, von dem sichergestellt werden soll ( **Ensure** ), ob er in der Zieldatei vorhanden ( **Present** ) oder nicht vorhanden ( **Absent** ) ist.</span><span class="sxs-lookup"><span data-stu-id="a6bcd-121">Indicates the contents to **Ensure** are **Present** or **Absent** from the targeted file.</span></span> |
|<span data-ttu-id="a6bcd-122">Anmeldeinformationen</span><span class="sxs-lookup"><span data-stu-id="a6bcd-122">Credential</span></span> |<span data-ttu-id="a6bcd-123">Die Anmeldeinformationen, die für den Zugriff auf Ressourcen wie z.B. Quelldateien erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="a6bcd-123">The credentials that are required to access resources, such as source files.</span></span> |
|<span data-ttu-id="a6bcd-124">Force</span><span class="sxs-lookup"><span data-stu-id="a6bcd-124">Force</span></span> |<span data-ttu-id="a6bcd-125">Setzt bestimmte Zugriffsoperationen außer Kraft, die zu einem Fehler führen würden (z.B. das Überschreiben einer Datei oder Löschen eines Verzeichnisses, das nicht leer ist).</span><span class="sxs-lookup"><span data-stu-id="a6bcd-125">Overrides access operations that would result in an error (such as overwriting a file or deleting a directory that is not empty).</span></span> <span data-ttu-id="a6bcd-126">Der Standardwert ist `$false`.</span><span class="sxs-lookup"><span data-stu-id="a6bcd-126">Default value is `$false`.</span></span> |
|<span data-ttu-id="a6bcd-127">Recurse</span><span class="sxs-lookup"><span data-stu-id="a6bcd-127">Recurse</span></span> |<span data-ttu-id="a6bcd-128">Nur bei Verwendung mit **Type** **Directory** gültig.</span><span class="sxs-lookup"><span data-stu-id="a6bcd-128">Only valid when used with **Type** **Directory** .</span></span> <span data-ttu-id="a6bcd-129">Führt den Statusvorgang rekursiv für den gesamten Verzeichnisinhalt, alle Unterverzeichnisse und den gesamten Unterverzeichnisinhalt aus.</span><span class="sxs-lookup"><span data-stu-id="a6bcd-129">Performs the state operation recursively to all directory content, subdirectories, and subdirectory content.</span></span> <span data-ttu-id="a6bcd-130">Der Standardwert ist `$false`.</span><span class="sxs-lookup"><span data-stu-id="a6bcd-130">Default value is `$false`.</span></span> |
|<span data-ttu-id="a6bcd-131">SourcePath</span><span class="sxs-lookup"><span data-stu-id="a6bcd-131">SourcePath</span></span> |<span data-ttu-id="a6bcd-132">Der Pfad, aus dem die Datei- oder Ordnerressource kopiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="a6bcd-132">The path from which to copy the file or folder resource.</span></span> |
|<span data-ttu-id="a6bcd-133">type</span><span class="sxs-lookup"><span data-stu-id="a6bcd-133">Type</span></span> |<span data-ttu-id="a6bcd-134">Der Typ der zu konfigurierenden Ressource.</span><span class="sxs-lookup"><span data-stu-id="a6bcd-134">The type of resource being configured.</span></span> <span data-ttu-id="a6bcd-135">Gültige Werte sind **Directory** und **File** .</span><span class="sxs-lookup"><span data-stu-id="a6bcd-135">Valid values are **Directory** and **File** .</span></span> <span data-ttu-id="a6bcd-136">Der Standardwert ist **File** .</span><span class="sxs-lookup"><span data-stu-id="a6bcd-136">Default value is **File** .</span></span> |
|<span data-ttu-id="a6bcd-137">MatchSource</span><span class="sxs-lookup"><span data-stu-id="a6bcd-137">MatchSource</span></span> |<span data-ttu-id="a6bcd-138">Bestimmt, ob die Ressource überwachen sollte, ob dem Quellverzeichnis nach der ersten Kopie neue Dateien hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="a6bcd-138">Determines if the resource should monitor for new files added to the source directory after the initial copy.</span></span> <span data-ttu-id="a6bcd-139">Der Wert `$true` gibt an, dass nach Erstellen der ersten Kopie alle neuen Quelldateien in das Ziel kopiert werden sollten.</span><span class="sxs-lookup"><span data-stu-id="a6bcd-139">A value of `$true` indicates that, after the initial copy, any new source files should be copied to the destination.</span></span> <span data-ttu-id="a6bcd-140">Bei Festlegung auf `$false` speichert die Ressource den Inhalt des Quellverzeichnisses zwischen und ignoriert alle Dateien, die nach der ersten Kopie hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="a6bcd-140">If set to `$false`, the resource caches the contents of the source directory and ignores any files added after the initial copy.</span></span> <span data-ttu-id="a6bcd-141">Der Standardwert ist `$false`.</span><span class="sxs-lookup"><span data-stu-id="a6bcd-141">Default value is `$false`.</span></span> |

> [!WARNING]
> <span data-ttu-id="a6bcd-142">Wenn Sie keinen Wert für **Credential** oder **PSRunAsCredential** angeben, greift die Ressource mithilfe des Computerkontos des Zielknotens auf den **SourcePath** zu.</span><span class="sxs-lookup"><span data-stu-id="a6bcd-142">If you do not specify a value for **Credential** or **PSRunAsCredential** , the resource will use the computer account of the target node to access the **SourcePath** .</span></span> <span data-ttu-id="a6bcd-143">Wenn der **SourcePath** eine UNC-Freigabe ist, könnte dies zu einem „Zugriff verweigert“-Fehler führen.</span><span class="sxs-lookup"><span data-stu-id="a6bcd-143">When the **SourcePath** is a UNC share, this could result in an "Access Denied" error.</span></span> <span data-ttu-id="a6bcd-144">Vergewissern Sie sich, dass Ihre Berechtigungen entsprechend festgelegt sind, oder verwenden Sie die **Credential** bzw. **PSRunAsCredential** , um das Konto anzugeben, das verwendet werden sollte.</span><span class="sxs-lookup"><span data-stu-id="a6bcd-144">Please ensure your permissions are set accordingly, or use the **Credential** or **PSRunAsCredential** properties to specify the account that should be used.</span></span>

## <a name="common-properties"></a><span data-ttu-id="a6bcd-145">Allgemeine Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="a6bcd-145">Common properties</span></span>

|<span data-ttu-id="a6bcd-146">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="a6bcd-146">Property</span></span> |<span data-ttu-id="a6bcd-147">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="a6bcd-147">Description</span></span> |
|---|---|
|<span data-ttu-id="a6bcd-148">DependsOn</span><span class="sxs-lookup"><span data-stu-id="a6bcd-148">DependsOn</span></span> |<span data-ttu-id="a6bcd-149">Gibt an, dass die Konfiguration einer anderen Ressource ausgeführt werden muss, bevor diese Ressource konfiguriert wird.</span><span class="sxs-lookup"><span data-stu-id="a6bcd-149">Indicates that the configuration of another resource must run before this resource is configured.</span></span> <span data-ttu-id="a6bcd-150">Wenn beispielsweise die ID des Skriptblocks mit der Ressourcenkonfiguration, den Sie zuerst ausführen möchten, „ResourceName“ und dessen Typ „ResourceType“ ist, lautet die Syntax für das Verwenden dieser Eigenschaft `DependsOn = "[ResourceType]ResourceName"`.</span><span class="sxs-lookup"><span data-stu-id="a6bcd-150">For example, if the ID of the resource configuration script block that you want to run first is ResourceName and its type is ResourceType, the syntax for using this property is `DependsOn = "[ResourceType]ResourceName"`.</span></span> |
|<span data-ttu-id="a6bcd-151">Ensure</span><span class="sxs-lookup"><span data-stu-id="a6bcd-151">Ensure</span></span> |<span data-ttu-id="a6bcd-152">Legt fest, ob die Datei und Inhalte ( **Contents** ) am Ziel ( **Destination** ) vorhanden sein sollen oder nicht.</span><span class="sxs-lookup"><span data-stu-id="a6bcd-152">Determines whether the file and **Contents** at the **Destination** should exist or not.</span></span> <span data-ttu-id="a6bcd-153">Legen Sie diese Eigenschaft auf **Present** fest, um sicherzustellen, dass die Datei vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="a6bcd-153">Set this property to **Present** to ensure the file exists.</span></span> <span data-ttu-id="a6bcd-154">Legen Sie sie auf **Absent** fest, um sicherzustellen, dass der Inhalt nicht vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="a6bcd-154">Set it to **Absent** to ensure they do not exist.</span></span> <span data-ttu-id="a6bcd-155">Der Standardwert ist **Present** .</span><span class="sxs-lookup"><span data-stu-id="a6bcd-155">The default value is **Present** .</span></span> |
|<span data-ttu-id="a6bcd-156">PsDscRunAsCredential</span><span class="sxs-lookup"><span data-stu-id="a6bcd-156">PsDscRunAsCredential</span></span> |<span data-ttu-id="a6bcd-157">Legt die Anmeldeinformationen für die Ausführung der gesamten Ressource fest.</span><span class="sxs-lookup"><span data-stu-id="a6bcd-157">Sets the credential for running the entire resource as.</span></span> |

> [!NOTE]
> <span data-ttu-id="a6bcd-158">Die allgemeine Eigenschaft **PsDscRunAsCredential** wurde in WMF 5.0 hinzugefügt, um das Ausführen einer beliebigen DSC-Ressource in Verbindung mit anderen Anmeldeinformationen zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="a6bcd-158">The **PsDscRunAsCredential** common property was added in WMF 5.0 to allow running any DSC resource in the context of other credentials.</span></span> <span data-ttu-id="a6bcd-159">Weitere Informationen finden Sie unter [Use Credentials with DSC Resources](../../../configurations/runasuser.md) (Verwenden von Anmeldeinformationen mit DSC-Ressourcen).</span><span class="sxs-lookup"><span data-stu-id="a6bcd-159">For more information, see [Use Credentials with DSC Resources](../../../configurations/runasuser.md).</span></span>

### <a name="additional-information"></a><span data-ttu-id="a6bcd-160">Zusätzliche Informationen</span><span class="sxs-lookup"><span data-stu-id="a6bcd-160">Additional information</span></span>

- <span data-ttu-id="a6bcd-161">Wenn Sie nur einen Zielpfad ( **DestinationPath** ) angeben, stellt die Ressource sicher, ob der Pfad vorhanden ( **Present** ) oder nicht vorhanden ist ( **Absent** ).</span><span class="sxs-lookup"><span data-stu-id="a6bcd-161">When you only specify a **DestinationPath** , the resource ensures that the path exists if **Present** or does not exist if **Absent** .</span></span>
- <span data-ttu-id="a6bcd-162">Wenn Sie einen Quellpfad **SourcePath** und einen Zielpfad ( **DestinationPath** ) mit dem **Type** -Wert **Directory** angeben, kopiert die Ressource das Quellverzeichnis in den Zielpfad.</span><span class="sxs-lookup"><span data-stu-id="a6bcd-162">When you specify a **SourcePath** and a **DestinationPath** with a **Type** value of **Directory** , the resource copies source directory to the destination path.</span></span> <span data-ttu-id="a6bcd-163">Die Eigenschaften **Recurse** , **Force** und **MatchSource** ändern den Typ des ausgeführten Kopiervorgangs, während **Credential** bestimmt, welches Konto für den Zugriff auf das Quellverzeichnis verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="a6bcd-163">The properties **Recurse** , **Force** , and **MatchSource** change the type of copy operation performed, while **Credential** determines which account to use to access the source directory.</span></span>
- <span data-ttu-id="a6bcd-164">Wenn Sie die Eigenschaft **Recurse** beim Kopieren eines Verzeichnisses nicht auf `$true` festlegen, wird keinerlei Inhalt des vorhandenen Verzeichnisses kopiert.</span><span class="sxs-lookup"><span data-stu-id="a6bcd-164">If you do not set the **Recurse** property to `$true` when copying a directory, none of the contents of the existing directory will be copied.</span></span> <span data-ttu-id="a6bcd-165">Es wird nur das angegebene Verzeichnis kopiert.</span><span class="sxs-lookup"><span data-stu-id="a6bcd-165">Only the directory specified will be copied.</span></span>
- <span data-ttu-id="a6bcd-166">Wenn Sie den Wert von **ReadOnly** für die Eigenschaft **Attributes** neben einem Zielpfad ( **DestinationPath** ) angegeben haben, stellen Sie sicher ( **Ensure), dass** **Present** den angegebenen Pfad erstellt, während mit **Contents** die Inhalte der Datei festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="a6bcd-166">If you specified a value of **ReadOnly** for the **Attributes** property alongside a **DestinationPath** , **Ensure** **Present** would create the path specified, while **Contents** would set the contents of the file.</span></span> <span data-ttu-id="a6bcd-167">Die Einstellung mit **Ensure** **Absent** würde die **Attributes** -Eigenschaft vollständig ignorieren und jede Datei im angegebenen Pfad entfernen.</span><span class="sxs-lookup"><span data-stu-id="a6bcd-167">An **Ensure** **Absent** setting would ignore the **Attributes** property entirely, and remove any file at the specified path.</span></span>

## <a name="example"></a><span data-ttu-id="a6bcd-168">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a6bcd-168">Example</span></span>

<span data-ttu-id="a6bcd-169">Im folgenden Beispiel werden ein Verzeichnis und seine Unterverzeichnisse unter Verwendung der Ressource „File“ von einem Pullserver auf einen Zielknoten kopiert.</span><span class="sxs-lookup"><span data-stu-id="a6bcd-169">The following example copies a directory and its subdirectories from a pull server to a target node using the File Resource.</span></span> <span data-ttu-id="a6bcd-170">Wenn der Vorgang erfolgreich ist, schreibt die Ressource „Log“ eine Bestätigungsmeldung in das Ereignisprotokoll.</span><span class="sxs-lookup"><span data-stu-id="a6bcd-170">If the operation succeeds, the Log resource writes a confirmation message to the event log.</span></span>

<span data-ttu-id="a6bcd-171">Das Quellverzeichnis ist ein auf dem Pullserver freigegebener UNC-Pfad (`\\PullServer\DemoSource`).</span><span class="sxs-lookup"><span data-stu-id="a6bcd-171">The source directory is a UNC path (`\\PullServer\DemoSource`) shared from the Pull Server.</span></span> <span data-ttu-id="a6bcd-172">Die **Recurse** -Eigenschaft gewährleistet, dass auch alle Unterverzeichnisse kopiert werden.</span><span class="sxs-lookup"><span data-stu-id="a6bcd-172">The **Recurse** property ensures that all subdirectories are copied as well.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a6bcd-173">Der LCM auf dem Zielknoten wird standardmäßig im Kontext des lokalen Systemkontos ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="a6bcd-173">The LCM on the target Node executes in the context of the local system account by default.</span></span> <span data-ttu-id="a6bcd-174">Um Zugriff auf den **SourcePath** zu gewähren, erteilen Sie dem Computerkonto des Zielknotens entsprechende Berechtigungen.</span><span class="sxs-lookup"><span data-stu-id="a6bcd-174">To grant access to the **SourcePath** , give the target Node's computer account appropriate permissions.</span></span> <span data-ttu-id="a6bcd-175">**Credential** und **PSDSCRunAsCredential** ändern beide den Kontext, den der LCM für den Zugriff auf den **SourcePath** verwendet.</span><span class="sxs-lookup"><span data-stu-id="a6bcd-175">The **Credential** and **PSDSCRunAsCredential** both change the context the LCM uses to access the **SourcePath** .</span></span> <span data-ttu-id="a6bcd-176">Sie müssen weiterhin Zugriff auf das Konto gewähren, das für den Zugriff auf den **SourcePath** verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="a6bcd-176">You still need to grant access to the account that will be used to access the **SourcePath** .</span></span>

```powershell
Configuration FileResourceDemo
{
    Node "localhost"
    {
        File DirectoryCopy
        {
            Ensure = "Present" # Ensure the directory is Present on the target node.
            Type = "Directory" # The default is File.
            Recurse = $true # Recursively copy all subdirectories.
            SourcePath = "\\PullServer\DemoSource"
            DestinationPath = "C:\Users\Public\Documents\DSCDemo\DemoDestination"
        }

        Log AfterDirectoryCopy
        {
            # The message below gets written to the Microsoft-Windows-Desired State Configuration/Analytic log
            Message = "Finished running the file resource with ID DirectoryCopy"
            DependsOn = "[File]DirectoryCopy" # Depends on successful execution of the File resource.
        }
    }
}
```

<span data-ttu-id="a6bcd-177">Weitere Informationen zur Verwendung von **Credentials** in DSC finden Sie unter [Verwenden von Anmeldeinformationen mit DSC-Ressourcen](../../../configurations/runAsUser.md) oder [Optionen für Anmeldeinformationen in den Konfigurationsdaten](../../../configurations/configDataCredentials.md).</span><span class="sxs-lookup"><span data-stu-id="a6bcd-177">For more on using **Credentials** in DSC see [Run As User](../../../configurations/runAsUser.md) or [Config Data Credentials](../../../configurations/configDataCredentials.md).</span></span>
