---
description: Beschreibt die Verwendung von Objekteigenschaften in PowerShell.
Locale: en-US
ms.date: 12/01/2017
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_properties?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Properties
ms.openlocfilehash: c5cc7abdd580a0fa57134f9c79616d1d8290a7e1
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99595526"
---
# <a name="about-properties"></a><span data-ttu-id="09f10-103">Informationen zu Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="09f10-103">About Properties</span></span>

## <a name="short-description"></a><span data-ttu-id="09f10-104">Kurze Beschreibung</span><span class="sxs-lookup"><span data-stu-id="09f10-104">Short description</span></span>
<span data-ttu-id="09f10-105">Beschreibt die Verwendung von Objekteigenschaften in PowerShell.</span><span class="sxs-lookup"><span data-stu-id="09f10-105">Describes how to use object properties in PowerShell.</span></span>

## <a name="long-description"></a><span data-ttu-id="09f10-106">Lange Beschreibung</span><span class="sxs-lookup"><span data-stu-id="09f10-106">Long description</span></span>

<span data-ttu-id="09f10-107">PowerShell verwendet strukturierte Sammlungen von Informationen, die als Objekte bezeichnet werden, um die Elemente in Daten speichern oder den Status des Computers darzustellen.</span><span class="sxs-lookup"><span data-stu-id="09f10-107">PowerShell uses structured collections of information called objects to represent the items in data stores or the state of the computer.</span></span> <span data-ttu-id="09f10-108">In der Regel arbeiten Sie mit einem Objekt, das Teil des Microsoft .NET Frameworks ist, aber Sie können auch benutzerdefinierte Objekte in PowerShell erstellen.</span><span class="sxs-lookup"><span data-stu-id="09f10-108">Typically, you work with object that are part of the Microsoft .NET Framework, but you can also create custom objects in PowerShell.</span></span>

<span data-ttu-id="09f10-109">Die Zuordnung zwischen einem Element und seinem Objekt ist sehr nah.</span><span class="sxs-lookup"><span data-stu-id="09f10-109">The association between an item and its object is very close.</span></span> <span data-ttu-id="09f10-110">Wenn Sie ein Objekt ändern, ändern Sie in der Regel das Element, das es darstellt.</span><span class="sxs-lookup"><span data-stu-id="09f10-110">When you change an object, you usually change the item that it represents.</span></span> <span data-ttu-id="09f10-111">Wenn Sie z. b. eine Datei in PowerShell erhalten, erhalten Sie nicht die tatsächliche Datei.</span><span class="sxs-lookup"><span data-stu-id="09f10-111">For example, when you get a file in PowerShell, you do not get the actual file.</span></span> <span data-ttu-id="09f10-112">Stattdessen erhalten Sie ein FileInfo-Objekt, das die Datei darstellt.</span><span class="sxs-lookup"><span data-stu-id="09f10-112">Instead, you get a FileInfo object that represents the file.</span></span> <span data-ttu-id="09f10-113">Wenn Sie das FileInfo-Objekt ändern, wird die Datei ebenfalls geändert.</span><span class="sxs-lookup"><span data-stu-id="09f10-113">When you change the FileInfo object, the file changes too.</span></span>

<span data-ttu-id="09f10-114">Die meisten Objekte verfügen über Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="09f10-114">Most objects have properties.</span></span> <span data-ttu-id="09f10-115">Eigenschaften sind die Daten, die einem Objekt zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="09f10-115">Properties are the data that is associated with an object.</span></span> <span data-ttu-id="09f10-116">Verschiedene Objekttypen haben unterschiedliche Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="09f10-116">Different types of object have different properties.</span></span> <span data-ttu-id="09f10-117">Beispielsweise verfügt ein FileInfo-Objekt, das eine Datei darstellt, über eine **isleonly** -Eigenschaft, die $true enthält, wenn die Datei das schreibgeschützte Attribut hat, und $false, wenn dies nicht der Fall ist.</span><span class="sxs-lookup"><span data-stu-id="09f10-117">For example, a FileInfo object, which represents a file, has an **IsReadOnly** property that contains $True if the file the read-only attribute and $False if it does not.</span></span>
<span data-ttu-id="09f10-118">Ein DirectoryInfo-Objekt, das ein Dateisystem Verzeichnis darstellt, verfügt über eine Parent-Eigenschaft, die den Pfad zum übergeordneten Verzeichnis enthält.</span><span class="sxs-lookup"><span data-stu-id="09f10-118">A DirectoryInfo object, which represents a file system directory, has a Parent property that contains the path to the parent directory.</span></span>

### <a name="object-properties"></a><span data-ttu-id="09f10-119">Objekteigenschaften</span><span class="sxs-lookup"><span data-stu-id="09f10-119">Object properties</span></span>

<span data-ttu-id="09f10-120">Verwenden Sie das-Cmdlet, um die Eigenschaften eines-Objekts zu erhalten `Get-Member` .</span><span class="sxs-lookup"><span data-stu-id="09f10-120">To get the properties of an object, use the `Get-Member` cmdlet.</span></span> <span data-ttu-id="09f10-121">Um z. b. die Eigenschaften eines **FileInfo** -Objekts zu erhalten, verwenden Sie das `Get-ChildItem` Cmdlet, um das FileInfo-Objekt zu erhalten, das eine Datei darstellt.</span><span class="sxs-lookup"><span data-stu-id="09f10-121">For example, to get the properties of a **FileInfo** object, use the `Get-ChildItem` cmdlet to get the FileInfo object that represents a file.</span></span> <span data-ttu-id="09f10-122">Verwenden Sie dann einen Pipeline Operator (&#124;), um das **FileInfo** -Objekt an zu senden `Get-Member` .</span><span class="sxs-lookup"><span data-stu-id="09f10-122">Then, use a pipeline operator (&#124;) to send the **FileInfo** object to `Get-Member`.</span></span> <span data-ttu-id="09f10-123">Mit dem folgenden Befehl wird die PowerShell.exe Datei abgerufen und an gesendet `Get-Member` .</span><span class="sxs-lookup"><span data-stu-id="09f10-123">The following command gets the PowerShell.exe file and sends it to `Get-Member`.</span></span>
<span data-ttu-id="09f10-124">Die \$ Automatische PSHome-Variable enthält den Pfad des PowerShell-Installationsverzeichnisses.</span><span class="sxs-lookup"><span data-stu-id="09f10-124">The \$Pshome automatic variable contains the path of the PowerShell installation directory.</span></span>

```powershell
Get-ChildItem $pshome\PowerShell.exe | Get-Member
```

<span data-ttu-id="09f10-125">Die Ausgabe des Befehls listet die Member des **FileInfo** -Objekts auf.</span><span class="sxs-lookup"><span data-stu-id="09f10-125">The output of the command lists the members of the **FileInfo** object.</span></span>
<span data-ttu-id="09f10-126">Member enthalten Eigenschaften und Methoden.</span><span class="sxs-lookup"><span data-stu-id="09f10-126">Members include both properties and methods.</span></span> <span data-ttu-id="09f10-127">Wenn Sie in PowerShell arbeiten, haben Sie Zugriff auf alle Member der Objekte.</span><span class="sxs-lookup"><span data-stu-id="09f10-127">When you work in PowerShell, you have access to all the members of the objects.</span></span>

<span data-ttu-id="09f10-128">Um nur die Eigenschaften eines-Objekts und nicht die-Methoden zu erhalten, verwenden Sie den Membership Type-Parameter des `Get-Member` Cmdlets mit dem Wert "Property", wie im folgenden Beispiel gezeigt.</span><span class="sxs-lookup"><span data-stu-id="09f10-128">To get only the properties of an object and not the methods, use the MemberType parameter of the `Get-Member` cmdlet with a value of "property", as shown in the following example.</span></span>

```powershell
Get-ChildItem $pshome\PowerShell.exe | Get-Member -MemberType property
```

```Output
TypeName: System.IO.FileInfo

Name              MemberType Definition
----              ---------- ----------
Attributes        Property   System.IO.FileAttributes Attributes {get;set;}
CreationTime      Property   System.DateTime CreationTime {get;set;}
CreationTimeUtc   Property   System.DateTime CreationTimeUtc {get;set;}
Directory         Property   System.IO.DirectoryInfo Directory {get;}
DirectoryName     Property   System.String DirectoryName {get;}
Exists            Property   System.Boolean Exists {get;}
Extension         Property   System.String Extension {get;}
FullName          Property   System.String FullName {get;}
IsReadOnly        Property   System.Boolean IsReadOnly {get;set;}
LastAccessTime    Property   System.DateTime LastAccessTime {get;set;}
LastAccessTimeUtc Property   System.DateTime LastAccessTimeUtc {get;set;}
LastWriteTime     Property   System.DateTime LastWriteTime {get;set;}
LastWriteTimeUtc  Property   System.DateTime LastWriteTimeUtc {get;set;}
Length            Property   System.Int64 Length {get;}
Name              Property   System.String Name {get;}
```

<span data-ttu-id="09f10-129">Nachdem Sie die Eigenschaften gefunden haben, können Sie Sie in ihren PowerShell-Befehlen verwenden.</span><span class="sxs-lookup"><span data-stu-id="09f10-129">After you find the properties, you can use them in your PowerShell commands.</span></span>

## <a name="property-values"></a><span data-ttu-id="09f10-130">Eigenschaftswerte</span><span class="sxs-lookup"><span data-stu-id="09f10-130">Property values</span></span>

<span data-ttu-id="09f10-131">Obwohl jedes Objekt eines bestimmten Typs über die gleichen Eigenschaften verfügt, beschreiben die Werte dieser Eigenschaften das jeweilige Objekt.</span><span class="sxs-lookup"><span data-stu-id="09f10-131">Although every object of a specific type has the same properties, the values of those properties describe the particular object.</span></span> <span data-ttu-id="09f10-132">Beispielsweise verfügt jedes FileInfo-Objekt über eine Eigenschaft "kreationtime", aber der Wert dieser Eigenschaft ist für jede Datei anders.</span><span class="sxs-lookup"><span data-stu-id="09f10-132">For example, every FileInfo object has a CreationTime property, but the value of that property differs for each file.</span></span>

<span data-ttu-id="09f10-133">Die gängigste Methode, um die Werte der Eigenschaften eines Objekts zu erhalten, ist die Verwendung der Punkt Methode.</span><span class="sxs-lookup"><span data-stu-id="09f10-133">The most common way to get the values of the properties of an object is to use the dot method.</span></span> <span data-ttu-id="09f10-134">Geben Sie einen Verweis auf das Objekt ein, z. b. eine Variable, die das Objekt enthält, oder einen Befehl, mit dem das Objekt abgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="09f10-134">Type a reference to the object, such as a variable that contains the object, or a command that gets the object.</span></span> <span data-ttu-id="09f10-135">Geben Sie dann einen Punkt (.) gefolgt vom Eigenschaftsnamen ein.</span><span class="sxs-lookup"><span data-stu-id="09f10-135">Then, type a dot (.) followed by the property name.</span></span>

<span data-ttu-id="09f10-136">Der folgende Befehl zeigt z. b. den Wert der Eigenschaft "kreationtime" der PowerShell.exe Datei an.</span><span class="sxs-lookup"><span data-stu-id="09f10-136">For example, the following command displays the value of the CreationTime property of the PowerShell.exe file.</span></span> <span data-ttu-id="09f10-137">Der `Get-ChildItem` Befehl gibt ein FileInfo-Objekt zurück, das die PowerShell.exe Datei darstellt.</span><span class="sxs-lookup"><span data-stu-id="09f10-137">The `Get-ChildItem` command returns a FileInfo object that represents the PowerShell.exe file.</span></span> <span data-ttu-id="09f10-138">Der Befehl wird in Klammern eingeschlossen, um sicherzustellen, dass er ausgeführt wird, bevor auf Eigenschaften zugegriffen wird.</span><span class="sxs-lookup"><span data-stu-id="09f10-138">The command is enclosed in parentheses to make sure that it is executed before any properties are accessed.</span></span> <span data-ttu-id="09f10-139">Auf den `Get-ChildItem` Befehl folgt ein Punkt und der Name der Eigenschaft "kreationtime" wie folgt:</span><span class="sxs-lookup"><span data-stu-id="09f10-139">The `Get-ChildItem` command is followed by a dot and the name of the CreationTime property, as follows:</span></span>

```powershell
(Get-ChildItem $pshome\PowerShell.exe).creationtime
```

```output
Tuesday, March 18, 2008 12:07:52 AM
```

<span data-ttu-id="09f10-140">Sie können auch ein Objekt in einer Variablen speichern und dann seine Eigenschaften mit der Punkt-Methode erhalten, wie im folgenden Beispiel gezeigt:</span><span class="sxs-lookup"><span data-stu-id="09f10-140">You can also save an object in a variable and then get its properties by using the dot method, as shown in the following example:</span></span>

```powershell
$a = Get-ChildItem $pshome\PowerShell.exe
$a.CreationTime
```

```output
Tuesday, March 18, 2008 12:07:52 AM
```

<span data-ttu-id="09f10-141">Sie können auch die `Select-Object` -und- `Format-List` Cmdlets verwenden, um die Eigenschaftswerte eines Objekts anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="09f10-141">You can also use the `Select-Object` and `Format-List` cmdlets to display the property values of an object.</span></span> <span data-ttu-id="09f10-142">`Select-Object` und `Format-List` verfügen jeweils über einen **Property** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="09f10-142">`Select-Object` and `Format-List` each have a **Property** parameter.</span></span> <span data-ttu-id="09f10-143">Sie können den **Property** -Parameter verwenden, um eine oder mehrere Eigenschaften und deren Werte anzugeben.</span><span class="sxs-lookup"><span data-stu-id="09f10-143">You can use the **Property** parameter to specify one or more properties and their values.</span></span> <span data-ttu-id="09f10-144">Oder Sie können das Platzhalter Zeichen ( \* ) verwenden, um alle Eigenschaften darzustellen.</span><span class="sxs-lookup"><span data-stu-id="09f10-144">Or, you can use the wildcard character (\*) to represent all the properties.</span></span>

<span data-ttu-id="09f10-145">Der folgende Befehl zeigt z. b. die Werte aller Eigenschaften der PowerShell.exe Datei an.</span><span class="sxs-lookup"><span data-stu-id="09f10-145">For example, the following command displays the values of all the properties of the PowerShell.exe file.</span></span>

```powershell
Get-ChildItem $pshome\PowerShell.exe | Format-List -Property *
```

```output
PSPath            : Microsoft.PowerShell.Core\FileSystem::C:\Windows\System3
                    2\WindowsPowerShell\v1.0\PowerShell.exe
PSParentPath      : Microsoft.PowerShell.Core\FileSystem::C:\Windows\System3
                    2\WindowsPowerShell\v1.0
PSChildName       : PowerShell.exe
PSDrive           : C
PSProvider        : Microsoft.PowerShell.Core\FileSystem
PSIsContainer     : False
Mode              : -a----
VersionInfo       : File:             C:\Windows\System32\WindowsPowerShell\
                    v1.0\PowerShell.exe
                    InternalName:     POWERSHELL
                    OriginalFilename: PowerShell.EXE.MUI
                    FileVersion:      10.0.16299.15 (WinBuild.160101.0800)
                    FileDescription:  Windows PowerShell
                    Product:          Microsoft Windows Operating System
                    ProductVersion:   10.0.16299.15
                    Debug:            False
                    Patched:          False
                    PreRelease:       False
                    PrivateBuild:     False
                    SpecialBuild:     False
                    Language:         English (United States)

BaseName          : PowerShell
Target            : {C:\Windows\WinSxS\amd64_microsoft-windows-powershell-ex
                    e_31bf3856ad364e35_10.0.16299.15_none_8c022aa6735716ae\p
                    owershell.exe}
LinkType          : HardLink
Name              : PowerShell.exe
Length            : 449024
DirectoryName     : C:\Windows\System32\WindowsPowerShell\v1.0
Directory         : C:\Windows\System32\WindowsPowerShell\v1.0
IsReadOnly        : False
Exists            : True
FullName          : C:\Windows\System32\WindowsPowerShell\v1.0\PowerShell.ex
Extension         : .exe
CreationTime      : 9/29/2017 6:43:19 AM
CreationTimeUtc   : 9/29/2017 1:43:19 PM
LastAccessTime    : 9/29/2017 6:43:19 AM
LastAccessTimeUtc : 9/29/2017 1:43:19 PM
LastWriteTime     : 9/29/2017 6:43:19 AM
LastWriteTimeUtc  : 9/29/2017 1:43:19 PM
Attributes        : Archive
```

### <a name="static-properties"></a><span data-ttu-id="09f10-146">Statische Eigenschaften</span><span class="sxs-lookup"><span data-stu-id="09f10-146">Static properties</span></span>

<span data-ttu-id="09f10-147">Sie können die statischen Eigenschaften von .NET-Klassen in PowerShell verwenden.</span><span class="sxs-lookup"><span data-stu-id="09f10-147">You can use the static properties of .NET classes in PowerShell.</span></span> <span data-ttu-id="09f10-148">Statische Eigenschaften sind Eigenschaften der-Klasse, im Gegensatz zu Standardeigenschaften, bei denen es sich um Eigenschaften eines Objekts handelt.</span><span class="sxs-lookup"><span data-stu-id="09f10-148">Static properties are properties of class, unlike standard properties, which are properties of an object.</span></span>

<span data-ttu-id="09f10-149">Verwenden Sie den static-Parameter des Get-Member-Cmdlets, um die statischen Eigenschaften einer Klasse zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="09f10-149">To get the static properties of an class, use the Static parameter of the Get-Member cmdlet.</span></span>

<span data-ttu-id="09f10-150">Beispielsweise ruft der folgende Befehl die statischen Eigenschaften der- `System.DateTime` Klasse ab.</span><span class="sxs-lookup"><span data-stu-id="09f10-150">For example, the following command gets the static properties of the `System.DateTime` class.</span></span>

```powershell
Get-Date | Get-Member -MemberType Property -Static
```

```Output
TypeName: System.DateTime

Name     MemberType Definition
----     ---------- ----------
MaxValue Property   static datetime MaxValue {get;}
MinValue Property   static datetime MinValue {get;}
Now      Property   datetime Now {get;}
Today    Property   datetime Today {get;}
UtcNow   Property   datetime UtcNow {get;}
```

<span data-ttu-id="09f10-151">Verwenden Sie die folgende Syntax, um den Wert einer statischen Eigenschaft zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="09f10-151">To get the value of a static property, use the following syntax.</span></span>

```
[<ClassName>]::<Property>
```

<span data-ttu-id="09f10-152">Mit dem folgenden Befehl wird z. b. der Wert der statischen Eigenschaft UtcNow der- `System.DateTime` Klasse abgerufen.</span><span class="sxs-lookup"><span data-stu-id="09f10-152">For example, the following command gets the value of the UtcNow static property of the `System.DateTime` class.</span></span>

```powershell
[System.DateTime]::UtcNow
```

### <a name="properties-of-scalar-objects-and-collections"></a><span data-ttu-id="09f10-153">Eigenschaften von skalaren Objekten und Auflistungen</span><span class="sxs-lookup"><span data-stu-id="09f10-153">Properties of scalar objects and collections</span></span>

<span data-ttu-id="09f10-154">Die Eigenschaften eines Objekts ("Skalar") eines bestimmten Typs unterscheiden sich häufig von den Eigenschaften einer Auflistung von Objekten desselben Typs.</span><span class="sxs-lookup"><span data-stu-id="09f10-154">The properties of one ("scalar") object of a particular type are often different from the properties of a collection of objects of the same type.</span></span>
<span data-ttu-id="09f10-155">Beispielsweise verfügt jeder Dienst über die **Display Name** -Eigenschaft, aber eine Auflistung von Diensten verfügt nicht über eine **Display Name** -Eigenschaft.</span><span class="sxs-lookup"><span data-stu-id="09f10-155">For example, every service has as **DisplayName** property, but a collection of services does not have a **DisplayName** property.</span></span>

<span data-ttu-id="09f10-156">Mit dem folgenden Befehl wird der Wert der **Display Name** -Eigenschaft des Dienst "AudioSrv" abgerufen.</span><span class="sxs-lookup"><span data-stu-id="09f10-156">The following command gets the value of the **DisplayName** property of the 'Audiosrv' service.</span></span>

```powershell
(Get-Service Audiosrv).DisplayName
```

```output
Windows Audio
```

<span data-ttu-id="09f10-157">Ab PowerShell 3,0 versucht PowerShell, Skript Fehler zu verhindern, die sich aus den unterschiedlichen Eigenschaften von skalaren Objekten und Auflistungen ergeben.</span><span class="sxs-lookup"><span data-stu-id="09f10-157">Beginning in PowerShell 3.0, PowerShell tries to prevent scripting errors that result from the differing properties of scalar objects and collections.</span></span> <span data-ttu-id="09f10-158">Derselbe Befehl gibt den Wert der **DisplayName** -Eigenschaft für jeden Dienst zurück, der `Get-Service` zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="09f10-158">The same command returns the value of the **DisplayName** property of every service that `Get-Service` returns.</span></span>

```powershell
(Get-Service).DisplayName
```

```output
Application Experience
Application Layer Gateway Service
Windows All-User Install Agent
Application Identity
Application Information
...
```

<span data-ttu-id="09f10-159">Wenn Sie eine Sammlung übermitteln, aber eine Eigenschaft anfordern, die nur für einzelne (skalare) Objekte vorhanden ist, gibt PowerShell den Wert dieser Eigenschaft für jedes Objekt in der Auflistung zurück.</span><span class="sxs-lookup"><span data-stu-id="09f10-159">When you submit a collection, but request a property that exists only on single ("scalar") objects, PowerShell returns the value of that property for every object in the collection.</span></span>

<span data-ttu-id="09f10-160">Alle Auflistungen haben eine **count** -Eigenschaft, die zurückgibt, wie viele Objekte in der Auflistung enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="09f10-160">All collections have a **Count** property that returns how many objects are in the collection.</span></span>

```powershell
(Get-Service).Count
```

```output
176
```

<span data-ttu-id="09f10-161">Ab PowerShell 3,0 gibt PowerShell den korrekten Wert zurück, wenn Sie die count-oder length-Eigenschaft von 0 (null) Objekten oder einem Objekt anfordern.</span><span class="sxs-lookup"><span data-stu-id="09f10-161">Beginning in PowerShell 3.0, if you request the Count or Length property of zero objects or one object, PowerShell returns the correct value.</span></span>

```powershell
(Get-Service Audiosrv).Count
```

```output
1
```

<span data-ttu-id="09f10-162">Wenn eine Eigenschaft für die einzelnen Objekte und für die Auflistung vorhanden ist, wird nur die-Eigenschaft der Auflistung zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="09f10-162">If a property exists on the individual objects and on the collection, only the collection's property is returned.</span></span>

 ```powershell
 $collection = @(
 [pscustomobject]@{length = "foo"}
 [pscustomobject]@{length = "bar"}
 )
 # PowerShell returns the collection's Length.
 $collection.length
 ```

 ```output
 2
 ```

<span data-ttu-id="09f10-163">Diese Funktion funktioniert auch mit Methoden von skalaren Objekten und Auflistungen.</span><span class="sxs-lookup"><span data-stu-id="09f10-163">This feature also works on methods of scalar objects and collections.</span></span> <span data-ttu-id="09f10-164">Weitere Informationen finden Sie unter [about_Methods](about_methods.md).</span><span class="sxs-lookup"><span data-stu-id="09f10-164">For more information, see [about_Methods](about_methods.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="09f10-165">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="09f10-165">See also</span></span>

[<span data-ttu-id="09f10-166">about_Methods</span><span class="sxs-lookup"><span data-stu-id="09f10-166">about_Methods</span></span>](about_Methods.md)

[<span data-ttu-id="09f10-167">about_Objects</span><span class="sxs-lookup"><span data-stu-id="09f10-167">about_Objects</span></span>](about_Objects.md)

[<span data-ttu-id="09f10-168">Get-Member</span><span class="sxs-lookup"><span data-stu-id="09f10-168">Get-Member</span></span>](xref:Microsoft.PowerShell.Utility.Get-Member)

[<span data-ttu-id="09f10-169">Select-Object</span><span class="sxs-lookup"><span data-stu-id="09f10-169">Select-Object</span></span>](xref:Microsoft.PowerShell.Utility.Select-Object)

[<span data-ttu-id="09f10-170">Format-List</span><span class="sxs-lookup"><span data-stu-id="09f10-170">Format-List</span></span>](xref:Microsoft.PowerShell.Utility.Format-List)
