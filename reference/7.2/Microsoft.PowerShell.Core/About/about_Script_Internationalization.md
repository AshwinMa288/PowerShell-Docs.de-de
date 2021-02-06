---
description: Beschreibt die Skript Internationalisierungs Features, mit denen Skripts das Anzeigen von Nachrichten und Anweisungen an Benutzer in der Benutzeroberfläche (UI) erleichtern.
Locale: en-US
ms.date: 03/20/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.core/about/about_script_internationalization?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: about_Script_Internationalization
ms.openlocfilehash: 283ea6788e76b481c912fc5672350efd2e8bafaa
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99605379"
---
# <a name="about-script-internationalization"></a><span data-ttu-id="cb8f5-103">Informationen zur Skript Internationalisierung</span><span class="sxs-lookup"><span data-stu-id="cb8f5-103">About Script Internationalization</span></span>

## <a name="short-description"></a><span data-ttu-id="cb8f5-104">Kurze Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cb8f5-104">Short Description</span></span>
<span data-ttu-id="cb8f5-105">Beschreibt die Skript Internationalisierungs Features, mit denen Skripts das Anzeigen von Nachrichten und Anweisungen an Benutzer in der Benutzeroberfläche (UI) erleichtern.</span><span class="sxs-lookup"><span data-stu-id="cb8f5-105">Describes the script internationalization features that make it easy for scripts to display messages and instructions to users in their user interface (UI) language.</span></span>

## <a name="long-description"></a><span data-ttu-id="cb8f5-106">Lange Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cb8f5-106">Long Description</span></span>

<span data-ttu-id="cb8f5-107">Mit den Funktionen zur Internationalisierung von PowerShell-Skripts können Sie Benutzer weltweit besser bedienen, indem Sie Hilfe und Benutzer Meldungen in der Sprache des Benutzers anzeigen.</span><span class="sxs-lookup"><span data-stu-id="cb8f5-107">The PowerShell script internationalization features allow you to better serve users throughout the world by displaying help and user messages in the user's language.</span></span>

<span data-ttu-id="cb8f5-108">Die Skript Internationalisierungs Funktionen Fragen die Benutzeroberflächen Kultur des Betriebssystems während der Ausführung ab, importieren die entsprechenden übersetzten Text Zeichenfolgen und zeigen Sie dem Benutzer an.</span><span class="sxs-lookup"><span data-stu-id="cb8f5-108">The script internationalization features query the UI culture of the operating system during execution, import the appropriate translated text strings, and display them to the user.</span></span> <span data-ttu-id="cb8f5-109">Mit dem Daten Abschnitt können Sie Text Zeichenfolgen getrennt von Code speichern, damit Sie leicht identifiziert und extrahiert werden können.</span><span class="sxs-lookup"><span data-stu-id="cb8f5-109">The Data section lets you store text strings separate from code so they are easily identified and extracted.</span></span> <span data-ttu-id="cb8f5-110">Ein neues Cmdlet, `ConvertFrom-StringData` , konvertiert Text Zeichenfolgen in Wörterbuch ähnliche Hash Tabellen, um die Übersetzung zu vereinfachen.</span><span class="sxs-lookup"><span data-stu-id="cb8f5-110">A new cmdlet, `ConvertFrom-StringData`, converts text strings into dictionary-like hash tables to facilitate translation.</span></span>

<span data-ttu-id="cb8f5-111">Zur Unterstützung von International Help Text umfasst PowerShell die folgenden Features:</span><span class="sxs-lookup"><span data-stu-id="cb8f5-111">To support international Help text, PowerShell includes the following features:</span></span>

- <span data-ttu-id="cb8f5-112">Ein Daten Abschnitt, der Text Zeichenfolgen aus Code Anweisungen trennt.</span><span class="sxs-lookup"><span data-stu-id="cb8f5-112">A Data section that separates text strings from code instructions.</span></span> <span data-ttu-id="cb8f5-113">Weitere Informationen zum Abschnitt "Data" finden Sie unter [about_Data_Sections](about_Data_Sections.md).</span><span class="sxs-lookup"><span data-stu-id="cb8f5-113">For more information about the Data section, see [about_Data_Sections](about_Data_Sections.md).</span></span>

- <span data-ttu-id="cb8f5-114">Neue automatische Variablen, `$PSCulture` und `$PSUICulture` .</span><span class="sxs-lookup"><span data-stu-id="cb8f5-114">New automatic variables, `$PSCulture` and `$PSUICulture`.</span></span> <span data-ttu-id="cb8f5-115">`$PSCulture` speichert den Namen der auf dem System verwendeten Benutzeroberflächen Sprache für Elemente wie Datum, Uhrzeit und Währung.</span><span class="sxs-lookup"><span data-stu-id="cb8f5-115">`$PSCulture` stores the name of the UI language used on the system for elements such as the date, time, and currency.</span></span> <span data-ttu-id="cb8f5-116">Die- `$PSUICulture` Variable speichert den Namen der auf dem System verwendeten UI-Sprache für Benutzeroberflächen Elemente wie Menüs und Text Zeichenfolgen.</span><span class="sxs-lookup"><span data-stu-id="cb8f5-116">The `$PSUICulture` variable stores the name of the UI language used on the system for user interface elements such as menus and text strings.</span></span>

- <span data-ttu-id="cb8f5-117">Ein Cmdlet, `ConvertFrom-StringData` , das Text Zeichenfolgen in Wörterbuch ähnliche Hash Tabellen konvertiert, um die Übersetzung zu vereinfachen.</span><span class="sxs-lookup"><span data-stu-id="cb8f5-117">A cmdlet, `ConvertFrom-StringData`, that converts text strings into dictionary-like hash tables to facilitate translation.</span></span> <span data-ttu-id="cb8f5-118">Weitere Informationen finden Sie unter [ConvertFrom-StringData](xref:Microsoft.PowerShell.Utility.ConvertFrom-StringData).</span><span class="sxs-lookup"><span data-stu-id="cb8f5-118">For more information, see [ConvertFrom-StringData](xref:Microsoft.PowerShell.Utility.ConvertFrom-StringData).</span></span>

- <span data-ttu-id="cb8f5-119">Ein neuer Dateityp, `.psd1` , der übersetzte Text Zeichenfolgen speichert.</span><span class="sxs-lookup"><span data-stu-id="cb8f5-119">A new file type, `.psd1`, that stores translated text strings.</span></span> <span data-ttu-id="cb8f5-120">Die `.psd1` Dateien werden in sprachspezifischen Unterverzeichnissen des Skript Verzeichnisses gespeichert.</span><span class="sxs-lookup"><span data-stu-id="cb8f5-120">The `.psd1` files are stored in language-specific subdirectories of the script directory.</span></span>

- <span data-ttu-id="cb8f5-121">Ein Cmdlet, `Import-LocalizedData` , das übersetzte Text Zeichenfolgen für eine angegebene Sprache zur Laufzeit in ein Skript importiert.</span><span class="sxs-lookup"><span data-stu-id="cb8f5-121">A cmdlet, `Import-LocalizedData`, that imports translated text strings for a specified language into a script at runtime.</span></span> <span data-ttu-id="cb8f5-122">Dieses Cmdlet erkennt und importiert Zeichen folgen in jeder von Windows unterstützten Sprache.</span><span class="sxs-lookup"><span data-stu-id="cb8f5-122">This cmdlet recognizes and imports strings in any Windows-supported language.</span></span> <span data-ttu-id="cb8f5-123">Weitere Informationen finden Sie unter [Import-localizeddata](xref:Microsoft.PowerShell.Utility.Import-LocalizedData).</span><span class="sxs-lookup"><span data-stu-id="cb8f5-123">For more information see [Import-LocalizedData](xref:Microsoft.PowerShell.Utility.Import-LocalizedData).</span></span>

### <a name="the-data-section-storing-default-strings"></a><span data-ttu-id="cb8f5-124">Der Abschnitt "Data": Speichern von Standard Zeichenfolgen</span><span class="sxs-lookup"><span data-stu-id="cb8f5-124">The Data Section: Storing Default Strings</span></span>

<span data-ttu-id="cb8f5-125">Verwenden Sie einen Daten Abschnitt im Skript, um die Text Zeichenfolgen in der Standardsprache zu speichern.</span><span class="sxs-lookup"><span data-stu-id="cb8f5-125">Use a Data section in the script to store the text strings in the default language.</span></span> <span data-ttu-id="cb8f5-126">Ordnen Sie die Zeichen folgen in Schlüssel-Wert-Paaren in einer here-Zeichenfolge an.</span><span class="sxs-lookup"><span data-stu-id="cb8f5-126">Arrange the strings in key/value pairs in a here-string.</span></span> <span data-ttu-id="cb8f5-127">Jedes Schlüssel-Wert-Paar muss sich in einer separaten Zeile befinden.</span><span class="sxs-lookup"><span data-stu-id="cb8f5-127">Each key/value pair must be on a separate line.</span></span> <span data-ttu-id="cb8f5-128">Wenn Sie Kommentare einschließen, müssen sich die Kommentare in separaten Zeilen befinden.</span><span class="sxs-lookup"><span data-stu-id="cb8f5-128">If you include comments, the comments must be on separate lines.</span></span>

<span data-ttu-id="cb8f5-129">Das `ConvertFrom-StringData` -Cmdlet konvertiert die Schlüssel-Wert-Paare in der here-Zeichenfolge in eine Wörterbuch ähnliche Hash Tabelle, die im Wert der Daten Abschnitts Variablen gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="cb8f5-129">The `ConvertFrom-StringData` cmdlet converts the key/value pairs in the here-string into a dictionary-like hash table that is stored in the value of the Data section variable.</span></span>

<span data-ttu-id="cb8f5-130">Im folgenden Beispiel enthält der Daten Abschnitt des `World.ps1` Skripts den English-United States (en-US) Satz von Eingabe Aufforderungs Meldungen für ein Skript.</span><span class="sxs-lookup"><span data-stu-id="cb8f5-130">In the following example, the Data section of the `World.ps1` script includes the English-United States (en-US) set of prompt messages for a script.</span></span> <span data-ttu-id="cb8f5-131">Das `ConvertFrom-StringData` Cmdlet konvertiert die Zeichen folgen in eine Hash Tabelle und speichert Sie in der `$msgtable` Variablen.</span><span class="sxs-lookup"><span data-stu-id="cb8f5-131">The `ConvertFrom-StringData` cmdlet converts the strings into a hash table and stores them in the `$msgtable` variable.</span></span>

```powershell
$msgTable = Data {
    #culture="en-US"
    ConvertFrom-StringData @'
    helloWorld = Hello, World.
    errorMsg1 = You cannot leave the user name field blank.
    promptMsg = Please enter your user name.
'@
}
```

<span data-ttu-id="cb8f5-132">Weitere Informationen zu here-Zeichen folgen finden Sie unter [about_Quoting_Rules](about_Quoting_Rules.md).</span><span class="sxs-lookup"><span data-stu-id="cb8f5-132">For more information about here-strings, see [about_Quoting_Rules](about_Quoting_Rules.md).</span></span>

### <a name="psd1-files-storing-translated-strings"></a><span data-ttu-id="cb8f5-133">PSD1 Files: übersetzte Zeichen folgen speichern</span><span class="sxs-lookup"><span data-stu-id="cb8f5-133">PSD1 Files: Storing Translated Strings</span></span>

<span data-ttu-id="cb8f5-134">Speichern Sie die Skript Nachrichten für jede Benutzeroberflächen Sprache in separaten Textdateien mit demselben Namen wie das Skript und die `.psd1` Dateinamenerweiterung.</span><span class="sxs-lookup"><span data-stu-id="cb8f5-134">Save the script messages for each UI language in separate text files with the same name as the script and the `.psd1` file name extension.</span></span> <span data-ttu-id="cb8f5-135">Speichern Sie die Dateien in den Unterverzeichnissen des Skript Verzeichnisses mit den Namen der Kulturen im folgenden Format:</span><span class="sxs-lookup"><span data-stu-id="cb8f5-135">Store the files in subdirectories of the script directory with names of cultures in the following format:</span></span>

`<language>-<region>`

<span data-ttu-id="cb8f5-136">Beispiele: de-de, AR-SA und zh-Hans</span><span class="sxs-lookup"><span data-stu-id="cb8f5-136">Examples: de-DE, ar-SA, and zh-Hans</span></span>

<span data-ttu-id="cb8f5-137">Wenn das Skript beispielsweise `World.ps1` im Verzeichnis gespeichert wird `C:\Scripts` , erstellen Sie eine Datei Verzeichnisstruktur, die der folgenden ähnelt:</span><span class="sxs-lookup"><span data-stu-id="cb8f5-137">For example, if the `World.ps1` script is stored in the `C:\Scripts` directory, you would create a file directory structure that resembles the following:</span></span>

```
C:\Scripts
C:\Scripts\World.ps1
C:\Scripts\de-DE\World.psd1
C:\Scripts\ar-SA\World.psd1
C:\Scripts\zh-CN\World.psd1
...
```

<span data-ttu-id="cb8f5-138">Die `World.psd1` Datei im Unterverzeichnis "de-de" des Skript Verzeichnisses kann folgende Anweisung enthalten:</span><span class="sxs-lookup"><span data-stu-id="cb8f5-138">The `World.psd1` file in the de-DE subdirectory of the script directory might include the following statement:</span></span>

```powershell
ConvertFrom-StringData -StringData @'
helloWorld = Hallo, Welt.
errorMsg1 = Das Feld Benutzername darf nicht leer sein.
promptMsg = Geben Sie Ihren Benutzernamen ein.
'@
```

<span data-ttu-id="cb8f5-139">Ebenso kann die `World.psd1` Datei im Unterverzeichnis "ar-SA" des Skript Verzeichnisses folgende Anweisung enthalten:</span><span class="sxs-lookup"><span data-stu-id="cb8f5-139">Similarly, the `World.psd1` file in the ar-SA subdirectory of the script directory might includes the following statement:</span></span>

```powershell
ConvertFrom-StringData -StringData @'
helloWorld = مرحبًا أيها العالَم
errorMsg1 = لا يمكنك ترك حقل اسم المستخدم فارغًا
promptMsg = يرجى إدخال اسم المستخدم الخاص بك
'@
```

### <a name="import-localizeddata-dynamic-retrieval-of-translated-strings"></a><span data-ttu-id="cb8f5-140">Import-localizeddata: Dynamisches Abrufen von übersetzten Zeichen folgen</span><span class="sxs-lookup"><span data-stu-id="cb8f5-140">Import-LocalizedData: Dynamic Retrieval of Translated Strings</span></span>

<span data-ttu-id="cb8f5-141">Verwenden Sie das-Cmdlet, um die Zeichen folgen in der Benutzeroberflächen Sprache des aktuellen Benutzers abzurufen `Import-LocalizedData` .</span><span class="sxs-lookup"><span data-stu-id="cb8f5-141">To retrieve the strings in the UI language of the current user, use the `Import-LocalizedData` cmdlet.</span></span>

<span data-ttu-id="cb8f5-142">`Import-LocalizedData` sucht den Wert der `$PSUICulture` automatischen Variablen und importiert den Inhalt der `<script-name>.psd1` Dateien im Unterverzeichnis, das mit dem Wert übereinstimmt `$PSUICulture` .</span><span class="sxs-lookup"><span data-stu-id="cb8f5-142">`Import-LocalizedData` finds the value of the `$PSUICulture` automatic variable and imports the content of the `<script-name>.psd1` files in the subdirectory that matches the `$PSUICulture` value.</span></span> <span data-ttu-id="cb8f5-143">Anschließend wird der importierte Inhalt in der Variablen gespeichert, die durch den Wert des **bindingvariable** -Parameters angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="cb8f5-143">Then, it saves the imported content in the variable specified by the value of the **BindingVariable** parameter.</span></span>

```powershell
Import-LocalizedData -BindingVariable msgTable
```

<span data-ttu-id="cb8f5-144">Wenn der Befehl z. b. `Import-LocalizedData` im `C:\Scripts\World.ps1` Skript angezeigt wird und der Wert von `$PSUICulture` "ar-SA" ist, sucht `Import-LocalizedData` die folgende Datei:</span><span class="sxs-lookup"><span data-stu-id="cb8f5-144">For example, if the `Import-LocalizedData` command appears in the `C:\Scripts\World.ps1` script and the value of `$PSUICulture` is "ar-SA", `Import-LocalizedData` finds the following file:</span></span>

`C:\Scripts\ar-SA\World.psd1`

<span data-ttu-id="cb8f5-145">Anschließend werden die arabischen Text Zeichenfolgen aus der Datei in die-Variable importiert, wobei alle Standard Zeichenfolgen `$msgTable` ersetzt werden, die möglicherweise im Data-Abschnitt des `World.ps1` Skripts definiert werden.</span><span class="sxs-lookup"><span data-stu-id="cb8f5-145">Then, it imports the Arabic text strings from the file into the `$msgTable` variable, replacing any default strings that might be defined in the Data section of the `World.ps1` script.</span></span>

<span data-ttu-id="cb8f5-146">Wenn das Skript die `$msgTable` Variable zum Anzeigen von Benutzer Nachrichten verwendet, werden die Nachrichten daher auf Arabisch angezeigt.</span><span class="sxs-lookup"><span data-stu-id="cb8f5-146">As a result, when the script uses the `$msgTable` variable to display user messages, the messages are displayed in Arabic.</span></span>

<span data-ttu-id="cb8f5-147">Das folgende Skript zeigt z. b. die Meldung "Bitte geben Sie Ihren Benutzernamen ein" in Arabisch an:</span><span class="sxs-lookup"><span data-stu-id="cb8f5-147">For example, the following script displays the "Please enter your user name" message in Arabic:</span></span>

```powershell
if (!($username)) { $msgTable.promptMsg }
```

<span data-ttu-id="cb8f5-148">Wenn keine `Import-LocalizedData` Datei finden kann, die `.psd1` mit dem Wert von übereinstimmt `$PSUIculture` , wird der Wert von `$msgTable` nicht ersetzt, und der-Befehl `$msgTable.promptMsg` zeigt die Fall Back-Zeichen folgen (en-US) an.</span><span class="sxs-lookup"><span data-stu-id="cb8f5-148">If `Import-LocalizedData` cannot find a `.psd1` file that matches the value of `$PSUIculture`, the value of `$msgTable` is not replaced, and the call to `$msgTable.promptMsg` displays the fallback en-US strings.</span></span>

## <a name="examples"></a><span data-ttu-id="cb8f5-149">Beispiele</span><span class="sxs-lookup"><span data-stu-id="cb8f5-149">Examples</span></span>

<span data-ttu-id="cb8f5-150">Dieses Beispiel zeigt, wie die Skript Internationalisierungs Funktionen in einem Skript verwendet werden, um Benutzern in der Sprache, die auf dem Computer festgelegt ist, einen Wochentag anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="cb8f5-150">This example shows how the script internationalization features are used in a script to display a day of the week to users in the language that is set on the computer.</span></span>

<span data-ttu-id="cb8f5-151">Im folgenden finden Sie eine komplette Liste der Sample1.ps1 Skriptdatei.</span><span class="sxs-lookup"><span data-stu-id="cb8f5-151">The following is a complete listing of the Sample1.ps1 script file.</span></span>

<span data-ttu-id="cb8f5-152">Das Skript beginnt mit einem Daten Abschnitt namens Day ($Day), der einen `ConvertFrom-StringData` Befehl enthält.</span><span class="sxs-lookup"><span data-stu-id="cb8f5-152">The script begins with a Data section named Day ($Day) that contains a `ConvertFrom-StringData` command.</span></span> <span data-ttu-id="cb8f5-153">Der an gesendete Ausdruck `ConvertFrom-StringData` ist eine here-Zeichenfolge, die die Namen der Tags in der Standard Kultur der Benutzeroberfläche, en-US, in Schlüssel/Wert-Paaren enthält.</span><span class="sxs-lookup"><span data-stu-id="cb8f5-153">The expression submitted to `ConvertFrom-StringData` is a here-string that contains the day names in the default UI culture, en-US, in key/value pairs.</span></span> <span data-ttu-id="cb8f5-154">Mit dem- `ConvertFrom-StringData` Cmdlet werden die Schlüssel-Wert-Paare in der here-Zeichenfolge in eine Hash Tabelle konvertiert und dann im Wert der `$Day` Variablen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="cb8f5-154">The `ConvertFrom-StringData` cmdlet converts the key/value pairs in the here-string into a hash table and then saves it in the value of the `$Day` variable.</span></span>

<span data-ttu-id="cb8f5-155">Der `Import-LocalizedData` Befehl importiert den Inhalt der `.psd1` Datei in das Verzeichnis, das mit dem Wert der `$PSUICulture` automatischen Variablen übereinstimmt, und speichert ihn dann in der `$Day` Variablen und ersetzt die Werte von, die `$Day` im Daten Abschnitt definiert sind.</span><span class="sxs-lookup"><span data-stu-id="cb8f5-155">The `Import-LocalizedData` command imports the contents of the `.psd1` file in the directory that matches the value of the `$PSUICulture` automatic variable and then saves it in the `$Day` variable, replacing the values of `$Day` that are defined in the Data section.</span></span>

<span data-ttu-id="cb8f5-156">Mit den verbleibenden Befehlen werden die Zeichen folgen in ein Array geladen und angezeigt.</span><span class="sxs-lookup"><span data-stu-id="cb8f5-156">The remaining commands load the strings into an array and display them.</span></span>

```powershell
$Day = Data {
#culture="en-US"
ConvertFrom-StringData -StringData @'
    messageDate = Today is
    d0 = Sunday
    d1 = Monday
    d2 = Tuesday
    d3 = Wednesday
    d4 = Thursday
    d5 = Friday
    d6 = Saturday
'@
}

Import-LocalizedData -BindingVariable Day

#Build an array of weekdays.
$a = $Day.d0, $Day.d1, $Day.d2, $Day.d3, $Day.d4, $Day.d5, $Day.d6

# Get the day of the week as a number (Monday = 1).
# Index into $a to get the name of the day.
# Use string formatting to build a sentence.

"{0} {1}" -f $Day.messageDate, $a[(Get-Date -UFormat %u)] | Out-Host
```

<span data-ttu-id="cb8f5-157">Die `.psd1` Dateien, von denen das Skript unterstützt wird, werden in Unterverzeichnissen des Skript Verzeichnisses gespeichert, dessen Namen den `$PSUICulture` Werten entsprechen.</span><span class="sxs-lookup"><span data-stu-id="cb8f5-157">The `.psd1` files that support the script are saved in subdirectories of the script directory with names that match the `$PSUICulture` values.</span></span>

<span data-ttu-id="cb8f5-158">Im folgenden finden Sie eine komplette Liste von `.\de-DE\sample1.psd1` :</span><span class="sxs-lookup"><span data-stu-id="cb8f5-158">The following is a complete listing of `.\de-DE\sample1.psd1`:</span></span>

```powershell
# culture="de-DE"
ConvertFrom-StringData @'
    messageDate = Heute ist
    d0 = Sonntag
    d1 = Montag
    d2 = Dienstag
    d3 = Mittwoch
    d4 = Donnerstag
    d5 = Freitag
    d6 = Samstag
'@
```

<span data-ttu-id="cb8f5-159">Wenn Sie Sample.ps1 auf einem System ausführen, auf dem der Wert von `$PSUICulture` de-de ist, lautet die Ausgabe des Skripts folglich wie folgt:</span><span class="sxs-lookup"><span data-stu-id="cb8f5-159">As a result, when you run Sample.ps1 on a system on which the value of `$PSUICulture` is de-DE, the output of the script is:</span></span>

```Output
Heute ist Freitag
```

## <a name="see-also"></a><span data-ttu-id="cb8f5-160">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="cb8f5-160">See also</span></span>

- [<span data-ttu-id="cb8f5-161">about_Data_Sections</span><span class="sxs-lookup"><span data-stu-id="cb8f5-161">about_Data_Sections</span></span>](about_Data_Sections.md)
- [<span data-ttu-id="cb8f5-162">about_Automatic_Variables</span><span class="sxs-lookup"><span data-stu-id="cb8f5-162">about_Automatic_Variables</span></span>](about_Automatic_Variables.md)
- [<span data-ttu-id="cb8f5-163">about_Hash_Tables</span><span class="sxs-lookup"><span data-stu-id="cb8f5-163">about_Hash_Tables</span></span>](about_Hash_Tables.md)
- [<span data-ttu-id="cb8f5-164">about_Quoting_Rules</span><span class="sxs-lookup"><span data-stu-id="cb8f5-164">about_Quoting_Rules</span></span>](about_Quoting_Rules.md)
- [<span data-ttu-id="cb8f5-165">ConvertFrom-StringData</span><span class="sxs-lookup"><span data-stu-id="cb8f5-165">ConvertFrom-StringData</span></span>](xref:Microsoft.PowerShell.Utility.ConvertFrom-StringData)
- [<span data-ttu-id="cb8f5-166">Import-LocalizedData</span><span class="sxs-lookup"><span data-stu-id="cb8f5-166">Import-LocalizedData</span></span>](xref:Microsoft.PowerShell.Utility.Import-LocalizedData)
