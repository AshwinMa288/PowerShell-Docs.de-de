---
ms.date: 06/05/2017
keywords: powershell,cmdlet
title: Arbeiten mit Registrierungseinträge
ms.openlocfilehash: 7f8ee87cebb8b220570bcb969445071a72a68526
ms.sourcegitcommit: d3f78120bdc9096c72aa0dfdbdd91efaf254c738
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 08/04/2020
ms.locfileid: "87758481"
---
# <a name="working-with-registry-entries"></a><span data-ttu-id="909b3-103">Arbeiten mit Registrierungseinträge</span><span class="sxs-lookup"><span data-stu-id="909b3-103">Working with Registry Entries</span></span>

<span data-ttu-id="909b3-104">Da Registrierungseinträge Eigenschaften von Schlüsseln sind und daher nicht direkt gesucht werden können, muss für die Arbeit mit diesen ein etwas anderer Ansatz gewählt werden.</span><span class="sxs-lookup"><span data-stu-id="909b3-104">Because registry entries are properties of keys and, as such, cannot be directly browsed, we need to take a slightly different approach when working with them.</span></span>

## <a name="listing-registry-entries"></a><span data-ttu-id="909b3-105">Auflisten von Registrierungseinträgen</span><span class="sxs-lookup"><span data-stu-id="909b3-105">Listing Registry Entries</span></span>

<span data-ttu-id="909b3-106">Es gibt viele verschiedene Möglichkeiten zum Untersuchen von Registrierungseinträgen.</span><span class="sxs-lookup"><span data-stu-id="909b3-106">There are many different ways to examine registry entries.</span></span> <span data-ttu-id="909b3-107">Am einfachsten ist es, die Eigenschaftennamen mit einem Schlüssel zu verknüpfen.</span><span class="sxs-lookup"><span data-stu-id="909b3-107">The simplest way is to get the property names associated with a key.</span></span> <span data-ttu-id="909b3-108">Wenn Sie beispielsweise die Namen der Einträge im Registrierungsschlüssel `HKEY_LOCAL_MACHINE\Software\Microsoft\Windows\CurrentVersion` anzeigen möchten, verwenden Sie `Get-Item`.</span><span class="sxs-lookup"><span data-stu-id="909b3-108">For example, to see the names of the entries in the registry key `HKEY_LOCAL_MACHINE\Software\Microsoft\Windows\CurrentVersion`, use `Get-Item`.</span></span> <span data-ttu-id="909b3-109">Registrierungsschlüssel verfügen über eine Eigenschaft mit dem generischen Namen „Property“, die eine Liste der Registrierungseinträge im Schlüssel ist.</span><span class="sxs-lookup"><span data-stu-id="909b3-109">Registry keys have a property with the generic name of "Property" that is a list of registry entries in the key.</span></span>
<span data-ttu-id="909b3-110">Der folgende Befehl wählt die Eigenschaft „Property“ aus und erweitert die Elemente so, dass sie in einer Liste angezeigt werden:</span><span class="sxs-lookup"><span data-stu-id="909b3-110">The following command selects the Property property and expands the items so that they are displayed in a list:</span></span>

```powershell
Get-Item -Path Registry::HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion |
  Select-Object -ExpandProperty Property
```

```Output
DevicePath
MediaPathUnexpanded
ProgramFilesDir
CommonFilesDir
ProductId
```

<span data-ttu-id="909b3-111">Wenn Sie die Registrierungseinträge in einer besser lesbaren Form anzeigen möchten, verwenden Sie `Get-ItemProperty`:</span><span class="sxs-lookup"><span data-stu-id="909b3-111">To view the registry entries in a more readable form, use `Get-ItemProperty`:</span></span>

```powershell
Get-ItemProperty -Path Registry::HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion
```

```Output
PSPath              : Microsoft.PowerShell.Core\Registry::HKEY_LOCAL_MACHINE\SO
                      FTWARE\Microsoft\Windows\CurrentVersion
PSParentPath        : Microsoft.PowerShell.Core\Registry::HKEY_LOCAL_MACHINE\SO
                      FTWARE\Microsoft\Windows
PSChildName         : CurrentVersion
PSDrive             : HKLM
PSProvider          : Microsoft.PowerShell.Core\Registry
DevicePath          : C:\WINDOWS\inf
MediaPathUnexpanded : C:\WINDOWS\Media
ProgramFilesDir     : C:\Program Files
CommonFilesDir      : C:\Program Files\Common Files
ProductId           : 76487-338-1167776-22465
WallPaperDir        : C:\WINDOWS\Web\Wallpaper
MediaPath           : C:\WINDOWS\Media
ProgramFilesPath    : C:\Program Files
PF_AccessoriesName  : Accessories
(default)           :
```

<span data-ttu-id="909b3-112">Die Windows PowerShell-bezogenen Eigenschaften für den Schüssel verfügen alle über das Präfix „PS“, z.B. **PSPath**, **PSParentPath**, **PSChildName** und **PSProvider**.</span><span class="sxs-lookup"><span data-stu-id="909b3-112">The Windows PowerShell-related properties for the key are all prefixed with "PS", such as **PSPath**, **PSParentPath**, **PSChildName**, and **PSProvider**.</span></span>

<span data-ttu-id="909b3-113">Sie können die Notation `*.*` zum Verweisen auf den aktuellen Speicherort verwenden.</span><span class="sxs-lookup"><span data-stu-id="909b3-113">You can use the `*.*` notation for referring to the current location.</span></span> <span data-ttu-id="909b3-114">Sie können `Set-Location` verwenden, um zuerst in den Registrierungscontainer **CurrentVersion** zu wechseln:</span><span class="sxs-lookup"><span data-stu-id="909b3-114">You can use `Set-Location` to change to the **CurrentVersion** registry container first:</span></span>

```powershell
Set-Location -Path Registry::HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion
```

<span data-ttu-id="909b3-115">Alternativ dazu können Sie das integrierte HKLM PSDrive mit `Set-Location` verwenden:</span><span class="sxs-lookup"><span data-stu-id="909b3-115">Alternatively, you can use the built-in HKLM PSDrive with `Set-Location`:</span></span>

```powershell
Set-Location -Path hklm:\SOFTWARE\Microsoft\Windows\CurrentVersion
```

<span data-ttu-id="909b3-116">Anschließend können Sie die Notation `*.*` für den aktuellen Speicherort verwenden, um die Eigenschaften aufzulisten, ohne einen vollständigen Pfad anzugeben:</span><span class="sxs-lookup"><span data-stu-id="909b3-116">You can then use the `*.*` notation for the current location to list the properties without specifying a full path:</span></span>

```powershell
Get-ItemProperty -Path .
```

```Output
...
DevicePath          : C:\WINDOWS\inf
MediaPathUnexpanded : C:\WINDOWS\Media
ProgramFilesDir     : C:\Program Files
...
```

<span data-ttu-id="909b3-117">Die Pfaderweiterung funktioniert genauso wie innerhalb des Dateisystems. Sie können daher von diesem Speicherort die Auflistung **ItemProperty** für `HKLM:\SOFTWARE\Microsoft\Windows\Help` abrufen, indem Sie `Get-ItemProperty -Path ..\Help` verwenden.</span><span class="sxs-lookup"><span data-stu-id="909b3-117">Path expansion works the same as it does within the file system, so from this location you can get the **ItemProperty** listing for `HKLM:\SOFTWARE\Microsoft\Windows\Help` by using `Get-ItemProperty -Path ..\Help`.</span></span>

## <a name="getting-a-single-registry-entry"></a><span data-ttu-id="909b3-118">Abrufen eines einzelnen Registrierungseintrags</span><span class="sxs-lookup"><span data-stu-id="909b3-118">Getting a Single Registry Entry</span></span>

<span data-ttu-id="909b3-119">Wenn Sie einen bestimmten Eintrag in einem Registrierungsschlüssel abrufen möchten, stehen verschiedene Möglichkeiten zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="909b3-119">If you want to retrieve a specific entry in a registry key, you can use one of several possible approaches.</span></span> <span data-ttu-id="909b3-120">In diesem Beispiel wird der Wert von **DevicePath** in `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion` gesucht.</span><span class="sxs-lookup"><span data-stu-id="909b3-120">This example finds the value of **DevicePath** in `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion`.</span></span>

<span data-ttu-id="909b3-121">Verwenden Sie mit `Get-ItemProperty` den Parameter **Path**, um den Namen des Schlüssels anzugeben, und den Parameter **Name**, um den Namen des Eintrags **DevicePath** anzugeben.</span><span class="sxs-lookup"><span data-stu-id="909b3-121">Using `Get-ItemProperty`, use the **Path** parameter to specify the name of the key, and the **Name** parameter to specify the name of the **DevicePath** entry.</span></span>

```powershell
Get-ItemProperty -Path HKLM:\Software\Microsoft\Windows\CurrentVersion -Name DevicePath
```

```Output
PSPath       : Microsoft.PowerShell.Core\Registry::HKEY_LOCAL_MACHINE\Software\
               Microsoft\Windows\CurrentVersion
PSParentPath : Microsoft.PowerShell.Core\Registry::HKEY_LOCAL_MACHINE\Software\
               Microsoft\Windows
PSChildName  : CurrentVersion
PSDrive      : HKLM
PSProvider   : Microsoft.PowerShell.Core\Registry
DevicePath   : C:\WINDOWS\inf
```

<span data-ttu-id="909b3-122">Dieser Befehl gibt die standardmäßigen Windows PowerShell-Eigenschaften sowie die Eigenschaft **DevicePath** aus.</span><span class="sxs-lookup"><span data-stu-id="909b3-122">This command returns the standard Windows PowerShell properties as well as the **DevicePath** property.</span></span>

> [!NOTE]
> <span data-ttu-id="909b3-123">Obwohl `Get-ItemProperty` die Parameter **Filter**, **Include** und **Exclude** aufweist, können sie nicht zum Filtern nach dem Namen der Eigenschaft verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="909b3-123">Although `Get-ItemProperty` has **Filter**, **Include**, and **Exclude** parameters, they cannot be used to filter by property name.</span></span> <span data-ttu-id="909b3-124">Diese Parameter verweisen auf Registrierungsschlüssel (Elementpfade) und nicht auf Registrierungseinträge (Elementeigenschaften).</span><span class="sxs-lookup"><span data-stu-id="909b3-124">These parameters refer to registry keys, which are item paths and not registry entries, which are item properties.</span></span>

<span data-ttu-id="909b3-125">Eine weitere Option ist die Verwendung des Befehlszeilentools „Reg.exe“.</span><span class="sxs-lookup"><span data-stu-id="909b3-125">Another option is to use the Reg.exe command line tool.</span></span> <span data-ttu-id="909b3-126">Um Hilfe zu „reg.exe“ zu erhalten, geben Sie an einer Eingabeaufforderung `reg.exe /?` ein.</span><span class="sxs-lookup"><span data-stu-id="909b3-126">For help with reg.exe, type `reg.exe /?` at a command prompt.</span></span> <span data-ttu-id="909b3-127">Mithilfe von „reg.exe“ finden Sie den Eintrag „DevicePath“, wie im folgenden Befehl gezeigt:</span><span class="sxs-lookup"><span data-stu-id="909b3-127">To find the DevicePath entry, use reg.exe as shown in the following command:</span></span>

```powershell
reg query HKLM\SOFTWARE\Microsoft\Windows\CurrentVersion /v DevicePath
```

```Output
! REG.EXE VERSION 3.0

HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion
    DevicePath  REG_EXPAND_SZ   %SystemRoot%\inf
```

<span data-ttu-id="909b3-128">(Sie können das COM-Objekt **WshShell** auch zum Suchen bestimmter Registrierungseinträge verwenden, obwohl diese Methode mit großen Binärdaten oder mit Registrierungseintragsnamen, die Zeichen wie „\\“ enthalten, nicht funktioniert.)</span><span class="sxs-lookup"><span data-stu-id="909b3-128">You can also use the **WshShell** COM object as well to find some registry entries, although this method does not work with large binary data or with registry entry names that include characters such as "\\").</span></span> <span data-ttu-id="909b3-129">Fügen Sie den Namen der Eigenschaft mit einem \\-Trennzeichen zum Elementpfad hinzu:</span><span class="sxs-lookup"><span data-stu-id="909b3-129">Append the property name to the item path with a \\ separator:</span></span>

```powershell
(New-Object -ComObject WScript.Shell).RegRead("HKLM\SOFTWARE\Microsoft\Windows\CurrentVersion\DevicePath")
```

```Output
%SystemRoot%\inf
```

## <a name="setting-a-single-registry-entry"></a><span data-ttu-id="909b3-130">Festlegen eines einzelnen Registrierungseintrags</span><span class="sxs-lookup"><span data-stu-id="909b3-130">Setting a Single Registry Entry</span></span>

<span data-ttu-id="909b3-131">Wenn Sie einen bestimmten Eintrag in einem Registrierungsschlüssel ändern möchten, stehen Ihnen verschiedene Möglichkeiten zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="909b3-131">If you want to change a specific entry in a registry key, you can use one of several possible approaches.</span></span> <span data-ttu-id="909b3-132">In diesem Beispiel wird der Eintrag **Path** unter `HKEY_CURRENT_USER\Environment` geändert.</span><span class="sxs-lookup"><span data-stu-id="909b3-132">This example modifies the **Path** entry under `HKEY_CURRENT_USER\Environment`.</span></span> <span data-ttu-id="909b3-133">Der Eintrag **Path** gibt an, wo ausführbare Dateien zu finden sind.</span><span class="sxs-lookup"><span data-stu-id="909b3-133">The **Path** entry specifies where to find executable files.</span></span>

1. <span data-ttu-id="909b3-134">Rufen Sie den aktuellen Wert des Eintrags **Path** mit `Get-ItemProperty` ab.</span><span class="sxs-lookup"><span data-stu-id="909b3-134">Retrieve the current value of the **Path** entry using `Get-ItemProperty`.</span></span>
2. <span data-ttu-id="909b3-135">Fügen Sie den neuen Wert hinzu, und trennen Sie ihn mit `;`.</span><span class="sxs-lookup"><span data-stu-id="909b3-135">Add the new value, separating it with a `;`.</span></span>
3. <span data-ttu-id="909b3-136">Verwenden Sie `Set-ItemProperty` mit dem angegebenen Schlüssel, Eintragsnamen und Wert, um den Registrierungseintrag zu ändern.</span><span class="sxs-lookup"><span data-stu-id="909b3-136">Use `Set-ItemProperty` with the specified key, entry name, and value to modify the registry entry.</span></span>

```powershell
$value = Get-ItemProperty -Path HKCU:\Environment -Name Path
$newpath = $value.Path += ";C:\src\bin\"
Set-ItemProperty -Path HKCU:\Environment -Name Path -Value $newpath
```

> [!NOTE]
> <span data-ttu-id="909b3-137">Obwohl `Set-ItemProperty` die Parameter **Filter**, **Include** und **Exclude** aufweist, können sie nicht zum Filtern nach dem Namen der Eigenschaft verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="909b3-137">Although `Set-ItemProperty` has **Filter**, **Include**, and **Exclude** parameters, they cannot be used to filter by property name.</span></span> <span data-ttu-id="909b3-138">Diese Parameter verweisen auf Registrierungsschlüssel (das sind Elementpfade und keine Registrierungseinträge), die Elementeigenschaften sind.</span><span class="sxs-lookup"><span data-stu-id="909b3-138">These parameters refer to registry keys—which are item paths—and not registry entries—which are item properties.</span></span>

<span data-ttu-id="909b3-139">Eine weitere Option ist die Verwendung des Befehlszeilentools „Reg.exe“.</span><span class="sxs-lookup"><span data-stu-id="909b3-139">Another option is to use the Reg.exe command line tool.</span></span> <span data-ttu-id="909b3-140">Um Hilfe zu „reg.exe“ zu erhalten, geben Sie **reg.exe /?** an einer Eingabeaufforderung ein.</span><span class="sxs-lookup"><span data-stu-id="909b3-140">For help with reg.exe, type **reg.exe /?**</span></span>
<span data-ttu-id="909b3-141">an einer Eingabeaufforderung.</span><span class="sxs-lookup"><span data-stu-id="909b3-141">at a command prompt.</span></span>

<span data-ttu-id="909b3-142">Im folgenden Beispiel wird der Eintrag **Path** geändert, indem der im vorstehenden Beispiel hinzugefügte Pfad entfernt wird.</span><span class="sxs-lookup"><span data-stu-id="909b3-142">The following example changes the **Path** entry by removing the path added in the example above.</span></span>
<span data-ttu-id="909b3-143">`reg query` wird weiterhin zum Abrufen des aktuellen Werts verwendet, um zu vermeiden, dass die aus `Get-ItemProperty` zurückgegebene Zeichenfolge analysiert werden muss.</span><span class="sxs-lookup"><span data-stu-id="909b3-143">`Get-ItemProperty` is still used to retrieve the current value to avoid having to parse the string returned from `reg query`.</span></span> <span data-ttu-id="909b3-144">Mit den Methoden **SubString** und **LastIndexOf** wird der letzte Pfad abgerufen, der dem Eintrag **Path** hinzugefügt wurde.</span><span class="sxs-lookup"><span data-stu-id="909b3-144">The **SubString** and **LastIndexOf** methods are used to retrieve the last path added to the **Path** entry.</span></span>

```powershell
$value = Get-ItemProperty -Path HKCU:\Environment -Name Path
$newpath = $value.Path.SubString(0, $value.Path.LastIndexOf(';'))
reg add HKCU\Environment /v Path /d $newpath /f
```

```Output
The operation completed successfully.
```

## <a name="creating-new-registry-entries"></a><span data-ttu-id="909b3-145">Erstellen neuer Registrierungseinträge</span><span class="sxs-lookup"><span data-stu-id="909b3-145">Creating New Registry Entries</span></span>

<span data-ttu-id="909b3-146">Verwenden Sie `New-ItemProperty` mit dem Pfad zum Schüssel, dem Eintragsnamen und dem Wert des Eintrags, um einen neuen Eintrag namens „PowerShellPath“ zum Schlüssel **CurrentVersion** hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="909b3-146">To add a new entry named "PowerShellPath" to the **CurrentVersion** key, use `New-ItemProperty` with the path to the key, the entry name, and the value of the entry.</span></span> <span data-ttu-id="909b3-147">In diesem Beispiel wird der Wert der Windows PowerShell-Variablen `$PSHome` verwendet, in der der Pfad zum Installationsverzeichnis für Windows PowerShell gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="909b3-147">For this example, we will take the value of the Windows PowerShell variable `$PSHome`, which stores the path to the installation directory for Windows PowerShell.</span></span>

<span data-ttu-id="909b3-148">Sie können dem Schlüssel mit Hilfe des folgenden Befehls den neuen Eintrag hinzufügen, und der Befehl gibt auch Informationen zu dem neuen Eintrag zurück:</span><span class="sxs-lookup"><span data-stu-id="909b3-148">You can add the new entry to the key by using the following command, and the command also returns information about the new entry:</span></span>

```powershell
New-ItemProperty -Path HKLM:\SOFTWARE\Microsoft\Windows\CurrentVersion -Name PowerShellPath -PropertyType String -Value $PSHome
```

```Output
PSPath         : Microsoft.PowerShell.Core\Registry::HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows\CurrentVersion
PSParentPath   : Microsoft.PowerShell.Core\Registry::HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows
PSChildName    : CurrentVersion
PSDrive        : HKLM
PSProvider     : Microsoft.PowerShell.Core\Registry
PowerShellPath : C:\Program Files\Windows PowerShell\v1.0
```

<span data-ttu-id="909b3-149">**PropertyType** muss der Namen eines **Microsoft.Win32.RegistryValueKind**-Aufzählungselements aus der folgenden Tabelle sein:</span><span class="sxs-lookup"><span data-stu-id="909b3-149">The **PropertyType** must be the name of a **Microsoft.Win32.RegistryValueKind** enumeration member from the following table:</span></span>

|<span data-ttu-id="909b3-150">PropertyType-Wert</span><span class="sxs-lookup"><span data-stu-id="909b3-150">PropertyType Value</span></span>|<span data-ttu-id="909b3-151">Bedeutung</span><span class="sxs-lookup"><span data-stu-id="909b3-151">Meaning</span></span>|
|----------------------|-----------|
|<span data-ttu-id="909b3-152">Binary</span><span class="sxs-lookup"><span data-stu-id="909b3-152">Binary</span></span>|<span data-ttu-id="909b3-153">Binärdaten</span><span class="sxs-lookup"><span data-stu-id="909b3-153">Binary data</span></span>|
|<span data-ttu-id="909b3-154">DWord</span><span class="sxs-lookup"><span data-stu-id="909b3-154">DWord</span></span>|<span data-ttu-id="909b3-155">Eine Zahl, die eine gültige UInt32 ist</span><span class="sxs-lookup"><span data-stu-id="909b3-155">A number that is a valid UInt32</span></span>|
|<span data-ttu-id="909b3-156">ExpandString</span><span class="sxs-lookup"><span data-stu-id="909b3-156">ExpandString</span></span>|<span data-ttu-id="909b3-157">Eine Zeichenfolge, die Umgebungsvariablen enthalten kann, die dynamisch erweitert werden</span><span class="sxs-lookup"><span data-stu-id="909b3-157">A string that can contain environment variables that are dynamically expanded</span></span>|
|<span data-ttu-id="909b3-158">MultiString</span><span class="sxs-lookup"><span data-stu-id="909b3-158">MultiString</span></span>|<span data-ttu-id="909b3-159">Eine mehrzeilige Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="909b3-159">A multiline string</span></span>|
|<span data-ttu-id="909b3-160">String</span><span class="sxs-lookup"><span data-stu-id="909b3-160">String</span></span>|<span data-ttu-id="909b3-161">Ein beliebiger Zeichenfolgenwert</span><span class="sxs-lookup"><span data-stu-id="909b3-161">Any string value</span></span>|
|<span data-ttu-id="909b3-162">QWord</span><span class="sxs-lookup"><span data-stu-id="909b3-162">QWord</span></span>|<span data-ttu-id="909b3-163">8 Byte Binärdaten</span><span class="sxs-lookup"><span data-stu-id="909b3-163">8 bytes of binary data</span></span>|

> [!NOTE]
> <span data-ttu-id="909b3-164">Sie können einen Registrierungseintrag zu mehreren Speicherorten hinzufügen, indem Sie ein Array von Werten für den Parameter **Path** angeben:</span><span class="sxs-lookup"><span data-stu-id="909b3-164">You can add a registry entry to multiple locations by specifying an array of values for the **Path** parameter:</span></span>

```powershell
New-ItemProperty -Name PowerShellPath -PropertyType String -Value $PSHome `
  -Path HKLM:\SOFTWARE\Microsoft\Windows\CurrentVersion, HKCU:\SOFTWARE\Microsoft\Windows\CurrentVersion
```

<span data-ttu-id="909b3-165">Sie können auch einen bereits vorhandenen Registrierungseintragswert überschreiben, indem Sie den Parameter **Force** an einen beliebigen `New-ItemProperty`-Befehl anfügen.</span><span class="sxs-lookup"><span data-stu-id="909b3-165">You can also overwrite a pre-existing registry entry value by adding the **Force** parameter to any `New-ItemProperty` command.</span></span>

## <a name="renaming-registry-entries"></a><span data-ttu-id="909b3-166">Umbenennen von Registrierungseinträgen</span><span class="sxs-lookup"><span data-stu-id="909b3-166">Renaming Registry Entries</span></span>

<span data-ttu-id="909b3-167">Verwenden Sie `Rename-ItemProperty`, um den Eintrag **PowerShellPath** in „PSHome“ umzubenennen:</span><span class="sxs-lookup"><span data-stu-id="909b3-167">To rename the **PowerShellPath** entry to "PSHome," use `Rename-ItemProperty`:</span></span>

```powershell
Rename-ItemProperty -Path HKLM:\SOFTWARE\Microsoft\Windows\CurrentVersion -Name PowerShellPath -NewName PSHome
```

<span data-ttu-id="909b3-168">Um den umbenannten Wert anzuzeigen, fügen Sie dem Befehl den Parameter **PassThru** hinzu.</span><span class="sxs-lookup"><span data-stu-id="909b3-168">To display the renamed value, add the **PassThru** parameter to the command.</span></span>

```powershell
Rename-ItemProperty -Path HKLM:\SOFTWARE\Microsoft\Windows\CurrentVersion -Name PowerShellPath -NewName PSHome -passthru
```

## <a name="deleting-registry-entries"></a><span data-ttu-id="909b3-169">Löschen von Registrierungseinträgen</span><span class="sxs-lookup"><span data-stu-id="909b3-169">Deleting Registry Entries</span></span>

<span data-ttu-id="909b3-170">Verwenden Sie `Remove-ItemProperty`, um die Registrierungseinträge „PSHome“ und „PowerShellPath“ zu löschen:</span><span class="sxs-lookup"><span data-stu-id="909b3-170">To delete both the PSHome and PowerShellPath registry entries, use `Remove-ItemProperty`:</span></span>

```powershell
Remove-ItemProperty -Path HKLM:\SOFTWARE\Microsoft\Windows\CurrentVersion -Name PSHome
Remove-ItemProperty -Path HKCU:\SOFTWARE\Microsoft\Windows\CurrentVersion -Name PowerShellPath
```
