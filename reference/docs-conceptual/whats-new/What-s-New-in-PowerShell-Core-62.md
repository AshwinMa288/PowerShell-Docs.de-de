---
title: Neuerungen in PowerShell Core 6.2
description: Neue Funktionen und Änderungen in PowerShell Core 6.2
ms.date: 03/28/2019
ms.openlocfilehash: 6a0da8a410e602ae3963e0bc7bace745317d7d4b
ms.sourcegitcommit: e7445ba8203da304286c591ff513900ad1c244a4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62058096"
---
# <a name="whats-new-in-powershell-core-62"></a><span data-ttu-id="8b7d2-103">Neuerungen in PowerShell Core 6.2</span><span class="sxs-lookup"><span data-stu-id="8b7d2-103">What's New in PowerShell Core 6.2</span></span>

<span data-ttu-id="8b7d2-104">Das Release PowerShell Core 6.2 konzentriert sich auf Leistungsverbesserungen, Fehlerbehebungen und kleinere Cmdlet- und Sprachverbesserungen, die die Qualität verbessern.</span><span class="sxs-lookup"><span data-stu-id="8b7d2-104">The PowerShell Core 6.2 release focused on performance improvements, bug fixes, and smaller cmdlet and language enhancements that improve the quality.</span></span> <span data-ttu-id="8b7d2-105">Eine vollständige Liste der Verbesserungen finden Sie in unseren detaillierten [Änderungsprotokollen](https://github.com/PowerShell/PowerShell/releases) auf GitHub.</span><span class="sxs-lookup"><span data-stu-id="8b7d2-105">To see a full list of improvements, check out our detailed [changelogs](https://github.com/PowerShell/PowerShell/releases) on GitHub.</span></span>

## <a name="experimental-features"></a><span data-ttu-id="8b7d2-106">Experimentelle Features</span><span class="sxs-lookup"><span data-stu-id="8b7d2-106">Experimental Features</span></span>

<span data-ttu-id="8b7d2-107">Wir haben bereits früher die Unterstützung [Experimentelle Features][] aktiviert.</span><span class="sxs-lookup"><span data-stu-id="8b7d2-107">Previously, we enabled support for [Experimental Features][].</span></span> <span data-ttu-id="8b7d2-108">Release 6.2 enthält vier experimentelle Features, die Sie ausprobieren können. Bitte geben Sie uns Feedback, damit wir Verbesserungen vornehmen und entscheiden können, ob das Feature allgemein verfügbar gemacht werden sollte.</span><span class="sxs-lookup"><span data-stu-id="8b7d2-108">In the 6.2 release, we have four experimental features to try out. Please provide feedback so we can make improvements and to decide whether the feature is worth promoting to mainstream status.</span></span>

<span data-ttu-id="8b7d2-109">Verwenden Sie `Get-ExperimentalFeature`, um eine Liste der verfügbaren experimentellen Features abzurufen.</span><span class="sxs-lookup"><span data-stu-id="8b7d2-109">Use `Get-ExperimentalFeature` to get a list of available experimental features.</span></span> <span data-ttu-id="8b7d2-110">Sie können diese Features mit `Enable-ExperimentalFeature` und `Disable-ExperimentalFeature` aktivieren oder deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="8b7d2-110">You can enable or disable these features with `Enable-ExperimentalFeature` and `Disable-ExperimentalFeature`.</span></span>

### <a name="command-not-found-suggestions"></a><span data-ttu-id="8b7d2-111">„Befehl nicht gefunden“-Vorschläge</span><span class="sxs-lookup"><span data-stu-id="8b7d2-111">Command Not Found Suggestions</span></span>

<span data-ttu-id="8b7d2-112">Dieses Feature sucht anhand von Fuzzyübereinstimmungen nach Vorschlägen für Befehle oder Cmdlets, bei denen Sie sich möglicherweise verschrieben haben.</span><span class="sxs-lookup"><span data-stu-id="8b7d2-112">This feature uses fuzzy matching to find suggestions for commands or cmdlets you may have mistyped.</span></span>

```powershell
Enable-ExperimentalFeature -Name PSCommandNotFoundSuggestion
```

#### <a name="example"></a><span data-ttu-id="8b7d2-113">Beispiel</span><span class="sxs-lookup"><span data-stu-id="8b7d2-113">Example</span></span>

<span data-ttu-id="8b7d2-114">In diesem Beispiel bestehen Fuzzyübereinstimmungen des falsch geschriebenen Cmdlet-Namens mit mehreren Vorschlägen, vom wahrscheinlichsten bis zum am wenigsten wahrscheinlichen.</span><span class="sxs-lookup"><span data-stu-id="8b7d2-114">In this example, the misspelled cmdlet name is fuzzy matched to several suggestions from most likely to least likely.</span></span>

```powershell
Get-Commnd
```

```Output
Get-Commnd : The term 'Get-Commnd' is not recognized as the name of a cmdlet, function, script file, or operable program.
Check the spelling of the name, or if a path was included, verify that the path is correct and try again.
At line:1 char:1
+ Get-Commnd
+ ~~~~~~~~~~
+ CategoryInfo          : ObjectNotFound: (Get-Commnd:String) [], CommandNotFoundException
+ FullyQualifiedErrorId : CommandNotFoundException


Suggestion [4,General]: The most similar commands are: Get-Command, Get-Content, Get-Job, Get-Module, Get-Event, Get-Host, Get-Member, Get-Item, Set-Content.
```

### <a name="implicit-remoting-batching"></a><span data-ttu-id="8b7d2-115">Implizite Remoting-Batchverarbeitung</span><span class="sxs-lookup"><span data-stu-id="8b7d2-115">Implicit Remoting Batching</span></span>

<span data-ttu-id="8b7d2-116">Bei Verwendung von [implizitem Remoting](https://devblogs.microsoft.com/scripting/remoting-the-implicit-way/) in einer Pipeline behandelt PowerShell die Befehle in der Pipeline unabhängig voneinander.</span><span class="sxs-lookup"><span data-stu-id="8b7d2-116">When using [implicit remoting](https://devblogs.microsoft.com/scripting/remoting-the-implicit-way/) in a pipeline, PowerShell treats each command in the pipeline independently.</span></span> <span data-ttu-id="8b7d2-117">Objekte werden während der Ausführung der Pipeline wiederholt zwischen dem Client und dem Remotesystem serialisiert und `de-serialized`.</span><span class="sxs-lookup"><span data-stu-id="8b7d2-117">Objects are repeatedly serialized and `de-serialized` between the client and remote system over the execution of the pipeline.</span></span>

<span data-ttu-id="8b7d2-118">Mit diesem Feature analysiert PowerShell die Pipeline, um festzustellen, ob der Befehl sicher ausgeführt werden kann und auf dem Zielsystem vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="8b7d2-118">With this feature, PowerShell analyzes the pipeline to determine if the command is safe to run and it exists on the target system.</span></span> <span data-ttu-id="8b7d2-119">Wenn „true“, führt PowerShell die gesamte Pipeline remote aus und serialisiert und `de-serializes` nur die Ergebnisse zurück an den Client.</span><span class="sxs-lookup"><span data-stu-id="8b7d2-119">When true, PowerShell executes the entire pipeline remotely and only serializes and `de-serializes` the results back to the client.</span></span>

```powershell
Enable-ExperimentalFeature -Name PSImplicitRemotingBatching
```

<span data-ttu-id="8b7d2-120">Ein Test von `Get-Process | Sort-Object` in der realen Welt über Localhost wird von 10 bis 15 Sekunden auf 20 bis 30 **Millisekunden** reduziert.</span><span class="sxs-lookup"><span data-stu-id="8b7d2-120">A real-world test of `Get-Process | Sort-Object` over localhost decreases from 10-15 seconds to 20-30 **milliseconds**.</span></span> <span data-ttu-id="8b7d2-121">Dieses Feature muss nur auf dem Client aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="8b7d2-121">The feature only needs to be enabled on the client.</span></span> <span data-ttu-id="8b7d2-122">Auf dem Server sind keine Änderungen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="8b7d2-122">No changes are required on the server.</span></span>

### <a name="temp-drive"></a><span data-ttu-id="8b7d2-123">Temporäres Laufwerk</span><span class="sxs-lookup"><span data-stu-id="8b7d2-123">Temp Drive</span></span>

```powershell
Enable-ExperimentalFeature -Name PSTempDrive
```

<span data-ttu-id="8b7d2-124">Wenn Sie PowerShell Core auf verschiedenen Betriebssystemen verwenden, werden Sie feststellen, dass die Umgebungsvariable für die Suche nach dem temporären Verzeichnis unter Windows, macOS und Linux unterschiedlich ist!</span><span class="sxs-lookup"><span data-stu-id="8b7d2-124">If you're using PowerShell Core on different operating systems, you'll discover that the environment variable for finding the temporary directory is different on Windows, macOS, and Linux!</span></span> <span data-ttu-id="8b7d2-125">Mit diesem Feature erhalten Sie ein [PSDrive][] namens `Temp:`, dass automatisch dem temporären Ordner für das von Ihnen verwendete Betriebssystem zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="8b7d2-125">With this feature, you get a [PSDrive][] called `Temp:` that is automatically mapped to the temporary folder for the operating system you are using.</span></span>

#### <a name="example"></a><span data-ttu-id="8b7d2-126">Beispiel</span><span class="sxs-lookup"><span data-stu-id="8b7d2-126">Example</span></span>

```powershell
PS> "Hello World!" > Temp:/hello.txt
PS> `Get-Content` Temp:/hello.txt
Hello World!
```

<span data-ttu-id="8b7d2-127">Beachten Sie, dass native Dateibefehle (z.B. `ls` unter Linux) nicht für PSDrives geeignet sind und dieses `Temp:`-Laufwerk nicht erkennen.</span><span class="sxs-lookup"><span data-stu-id="8b7d2-127">Be aware that native file commands (like `ls` on Linux) are not aware of PSDrives and won't see this `Temp:` drive.</span></span>

### <a name="abbreviation-expansion"></a><span data-ttu-id="8b7d2-128">Erweiterung der Abkürzung</span><span class="sxs-lookup"><span data-stu-id="8b7d2-128">Abbreviation Expansion</span></span>

<span data-ttu-id="8b7d2-129">Von PowerShell-Cmdlets wird erwartet, dass sie beschreibende Namen haben.</span><span class="sxs-lookup"><span data-stu-id="8b7d2-129">PowerShell cmdlets are expected to have descriptive nouns.</span></span> <span data-ttu-id="8b7d2-130">Dies führt zu langen, schwieriger einzugebenden Namen.</span><span class="sxs-lookup"><span data-stu-id="8b7d2-130">This results in long names that are more difficult to type.</span></span> <span data-ttu-id="8b7d2-131">Mit diesem Feature genügt es, wenn Sie nur die Großbuchstaben des Cmdlets eingeben und anhand der Vervollständigung mit der TAB-Taste eine Übereinstimmung suchen.</span><span class="sxs-lookup"><span data-stu-id="8b7d2-131">This feature allows you to just type the uppercase characters of the cmdlet and use tab-completion to find a match.</span></span>

```powershell
Enable-ExperimentalFeature -Name PSUseAbbreviationExpansion
```

#### <a name="example"></a><span data-ttu-id="8b7d2-132">Beispiel</span><span class="sxs-lookup"><span data-stu-id="8b7d2-132">Example</span></span>

```powershell
PS> i-arsavsf
```

<span data-ttu-id="8b7d2-133">Wenn Sie das [Az](https://www.powershellgallery.com/packages/Az)-Modul von Azure PowerShell installiert haben und die TAB-Taste drücken, wird die automatische Vervollständigung ausgeführt:</span><span class="sxs-lookup"><span data-stu-id="8b7d2-133">If you hit tab, and have the Azure PowerShell [Az](https://www.powershellgallery.com/packages/Az) module installed, it will autocomplete to:</span></span>

```Output
PS> Import-AzRecoveryServicesAsrVaultSettingsFile
```

> [!NOTE]
> <span data-ttu-id="8b7d2-134">Dieses Feature ist für die interaktive Verwendung vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="8b7d2-134">This feature is intended to be used interactively.</span></span> <span data-ttu-id="8b7d2-135">Abgekürzte Formen der Cmdlets können nicht ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="8b7d2-135">Abbreviated forms of cmdlets can't be executed.</span></span>
> <span data-ttu-id="8b7d2-136">Dieses Feature ist kein Ersatz für Aliase.</span><span class="sxs-lookup"><span data-stu-id="8b7d2-136">This feature is not a replacement for aliases.</span></span>

## <a name="breaking-changes"></a><span data-ttu-id="8b7d2-137">Wichtige Änderungen</span><span class="sxs-lookup"><span data-stu-id="8b7d2-137">Breaking Changes</span></span>

- <span data-ttu-id="8b7d2-138">`-NoEnumerate`-Verhalten in `Write-Output` ist konsistent mit Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8b7d2-138">Fix `-NoEnumerate` behavior in `Write-Output` to be consistent with Windows PowerShell.</span></span> <span data-ttu-id="8b7d2-139">(#9069)</span><span class="sxs-lookup"><span data-stu-id="8b7d2-139">(#9069)</span></span>
- <span data-ttu-id="8b7d2-140">Das Ergebnis von `Join-String -InputObject 1,2,3` ist jetzt gleich dem Ergebnis von `1,2,3 | Join-String` (#8611) – vielen Dank an @sethvs!</span><span class="sxs-lookup"><span data-stu-id="8b7d2-140">Make `Join-String -InputObject 1,2,3` result equal to `1,2,3 | Join-String` result (#8611) (Thanks @sethvs!)</span></span>
- <span data-ttu-id="8b7d2-141">Hinzufügen von `-Stable` zu `Sort-Object` und zugehörige Tests (#7862) – vielen Dank an @KirkMunro!</span><span class="sxs-lookup"><span data-stu-id="8b7d2-141">Add `-Stable` to `Sort-Object` and related tests (#7862) (Thanks @KirkMunro!)</span></span>
- <span data-ttu-id="8b7d2-142">Verbesserung des `Start-Sleep`-Cmdlets, sodass es Bruchteile von Sekunden akzeptiert (#8537) – vielen Dank an @Prototyyppi!</span><span class="sxs-lookup"><span data-stu-id="8b7d2-142">Improve `Start-Sleep` cmdlet to accept fractional seconds (#8537) (Thanks @Prototyyppi!)</span></span>
- <span data-ttu-id="8b7d2-143">Ändern der Hashtabelle, sodass OrdinalIgnoreCase verwendet wird, damit die Tabelle in allen Kulturen `case-insensitive` ist (#8566)</span><span class="sxs-lookup"><span data-stu-id="8b7d2-143">Change hashtable to use OrdinalIgnoreCase to be `case-insensitive` in all Cultures (#8566)</span></span>
- <span data-ttu-id="8b7d2-144">**LiteralPath** in `Import-Csv` wird an `Get-ChildItem`-Ausgabe gebunden (#8277) – vielen Dank an @iSazonov!</span><span class="sxs-lookup"><span data-stu-id="8b7d2-144">Fix **LiteralPath** in `Import-Csv` to bind to `Get-ChildItem` output (#8277) (Thanks @iSazonov!)</span></span>
- <span data-ttu-id="8b7d2-145">Eine Spalte ohne Namen wird nicht mehr übersprungen, wenn in `Import-Csv` doppelte Anführungszeichen als Trennzeichen verwendet werden (#7899) – vielen Dank an @Topping!</span><span class="sxs-lookup"><span data-stu-id="8b7d2-145">No longer skips a column without name if double quote delimiter is used in `Import-Csv` (#7899) (Thanks @Topping!)</span></span>
- <span data-ttu-id="8b7d2-146">`Get-ExperimentalFeature` hat nicht mehr die Option `-ListAvailable` (#8318)</span><span class="sxs-lookup"><span data-stu-id="8b7d2-146">`Get-ExperimentalFeature` no longer has `-ListAvailable` switch (#8318)</span></span>
- <span data-ttu-id="8b7d2-147">Beim Debuggen von Parametern wird `$DebugPreference` jetzt auf **Continue** statt auf **Inquire** gesetzt (#8195) – vielen Dank an @KirkMunro!</span><span class="sxs-lookup"><span data-stu-id="8b7d2-147">Debug parameter now sets `$DebugPreference` to **Continue** instead of **Inquire** (#8195) (Thanks @KirkMunro!)</span></span>
- <span data-ttu-id="8b7d2-148">Beachtung von `-OutputFormat` bei Angabe in nicht interaktivem, umgeleitetem, codiertem Befehl, der mit PowerShell verwendet wird (#8115)</span><span class="sxs-lookup"><span data-stu-id="8b7d2-148">Honor `-OutputFormat` if specified in non-interactive, redirected, encoded command used with pwsh (#8115)</span></span>
- <span data-ttu-id="8b7d2-149">Assembly wird vor dem Versuch, aus dem GAC geladen zu werden, aus dem Modulbasispfad geladen (#8073)</span><span class="sxs-lookup"><span data-stu-id="8b7d2-149">Load assembly from module base path before trying to load from the GAC (#8073)</span></span>
- <span data-ttu-id="8b7d2-150">Entfernen der Tilde aus Linux-Vorschaupaketen (#8244)</span><span class="sxs-lookup"><span data-stu-id="8b7d2-150">Remove tilde from Linux preview packages (#8244)</span></span>
- <span data-ttu-id="8b7d2-151">Verschieben der Verarbeitung von `-WorkingDirectory` vor der Verarbeitung von Profilen (#8079)</span><span class="sxs-lookup"><span data-stu-id="8b7d2-151">Move processing of `-WorkingDirectory` before processing of profiles (#8079)</span></span>
- <span data-ttu-id="8b7d2-152">Kein Hinzufügen der `PATHEXT`-Umgebungsvariablen unter Unix (#7697) – vielen Dank an @iSazonov!</span><span class="sxs-lookup"><span data-stu-id="8b7d2-152">Do not add `PATHEXT` environment variable on Unix (#7697) (Thanks @iSazonov!)</span></span>

## <a name="known-issues"></a><span data-ttu-id="8b7d2-153">Bekannte Probleme</span><span class="sxs-lookup"><span data-stu-id="8b7d2-153">Known Issues</span></span>

- <span data-ttu-id="8b7d2-154">Beim Remoting tritt auf Windows IOT-ARM-Plattformen beim Laden von Modulen ein Problem auf.</span><span class="sxs-lookup"><span data-stu-id="8b7d2-154">Remoting on Windows IOT ARM platforms has an issue loading modules.</span></span> <span data-ttu-id="8b7d2-155">Siehe (#8053)</span><span class="sxs-lookup"><span data-stu-id="8b7d2-155">See (#8053)</span></span>

## <a name="general-updates-and-fixes"></a><span data-ttu-id="8b7d2-156">Allgemeine Updates und Fixes</span><span class="sxs-lookup"><span data-stu-id="8b7d2-156">General Updates and Fixes</span></span>

- <span data-ttu-id="8b7d2-157">Vervollständigung mit der TAB-Taste ohne Berücksichtigung der Groß-/Kleinschreibung für Dateien und Ordner im Groß-/Kleinschreibung berücksichtigenden Dateisystem (#8128)</span><span class="sxs-lookup"><span data-stu-id="8b7d2-157">Enable case-insensitive tab completion for files and folders on case-sensitive filesystem (#8128)</span></span>
- <span data-ttu-id="8b7d2-158">Öffentlich machen von PSVersionInfo.PSVersion und PSVersionInfo.PSEdition (#8054) – vielen Dank an @KirkMunro!</span><span class="sxs-lookup"><span data-stu-id="8b7d2-158">Make PSVersionInfo.PSVersion and PSVersionInfo.PSEdition public (#8054) (Thanks @KirkMunro!)</span></span>
- <span data-ttu-id="8b7d2-159">Hinzufügen des Typrückschlusses für `$_` / `$PSItem` in `catch{ }`-Blöcken (#8020) – vielen Dank an @vexx32!</span><span class="sxs-lookup"><span data-stu-id="8b7d2-159">Add Type Inference for `$_` / `$PSItem` in `catch{ }` blocks (#8020) (Thanks @vexx32!)</span></span>
- <span data-ttu-id="8b7d2-160">Behoben: Typrückschluss bei Aufruf der statischen Methode (#8018) – vielen Dank an @SeeminglyScience!</span><span class="sxs-lookup"><span data-stu-id="8b7d2-160">Fix static method invocation type inference (#8018) (Thanks @SeeminglyScience!)</span></span>
- <span data-ttu-id="8b7d2-161">Erstellen von abgeleiteten Typen für `Select-Object`, `Group-Object`, **PSObject** und **Hashtabelle** (#7231) – vielen Dank an @powercode!</span><span class="sxs-lookup"><span data-stu-id="8b7d2-161">Create inferred types for `Select-Object`, `Group-Object`, **PSObject** and **Hashtable** (#7231) (Thanks @powercode!)</span></span>
- <span data-ttu-id="8b7d2-162">Unterstützung des Methodenaufrufs mit `ByRef-like`-Typparametern (#7721)</span><span class="sxs-lookup"><span data-stu-id="8b7d2-162">Support calling method with `ByRef-like` type parameters (#7721)</span></span>
- <span data-ttu-id="8b7d2-163">Behandeln des Falls, dass der Windows PowerShell-Modulpfad bereits im PSModulePath der Umgebung enthalten ist (#7727)</span><span class="sxs-lookup"><span data-stu-id="8b7d2-163">Handle the case where the Windows PowerShell module path is already in the environment's PSModulePath (#7727)</span></span>
- <span data-ttu-id="8b7d2-164">Aktivieren von `SecureString`-Cmdlets für Nicht-Windows durch Speichern von Nur-Text (#9199)</span><span class="sxs-lookup"><span data-stu-id="8b7d2-164">Enable `SecureString` cmdlets for non-Windows by storing the plain text (#9199)</span></span>
- <span data-ttu-id="8b7d2-165">Verbesserte Fehlermeldung in Nicht-Windows beim Importieren von „clixml“ mit securestring (#7997)</span><span class="sxs-lookup"><span data-stu-id="8b7d2-165">Improve error message on non-Windows when importing clixml with securestring (#7997)</span></span>
- <span data-ttu-id="8b7d2-166">Hinzufügen des ReplyTo-Parameters zu `Send-MailMessage` (#8727) – vielen Dank an @replicaJunction!</span><span class="sxs-lookup"><span data-stu-id="8b7d2-166">Adding parameter ReplyTo to `Send-MailMessage` (#8727) (Thanks @replicaJunction!)</span></span>
- <span data-ttu-id="8b7d2-167">Hinzufügen der „Veraltet“-Nachricht zu `Send-MailMessage` (#9178)</span><span class="sxs-lookup"><span data-stu-id="8b7d2-167">Add Obsolete message to `Send-MailMessage` (#9178)</span></span>
- <span data-ttu-id="8b7d2-168">`Restart-Computer` funktioniert auf `localhost`, wenn WinRM nicht vorhanden ist (#9160)</span><span class="sxs-lookup"><span data-stu-id="8b7d2-168">Fix `Restart-Computer` to work on `localhost` when WinRM is not present (#9160)</span></span>
- <span data-ttu-id="8b7d2-169">Veranlassen, dass `Start-Job` einen Fehler mit Abbruch auslöst, wenn PowerShell gehostet wird (#9128)</span><span class="sxs-lookup"><span data-stu-id="8b7d2-169">Make `Start-Job` throw terminating error when PowerShell is being hosted (#9128)</span></span>
- <span data-ttu-id="8b7d2-170">Hinzufügen von Beschleunigern und Suffixen des C#-Formatvorlagentyps für ushort, uint, ulong und kurze Literale (#7813) – vielen Dank an @vexx32!</span><span class="sxs-lookup"><span data-stu-id="8b7d2-170">Add C# style type accelerators and suffixes for ushort, uint, ulong, and short literals (#7813) (Thanks @vexx32!)</span></span>
- <span data-ttu-id="8b7d2-171">Hinzufügen neuer Suffixe für numerische Literale – siehe [about_Numeric_Literals][] (#7901) – vielen Dank an @vexx32!</span><span class="sxs-lookup"><span data-stu-id="8b7d2-171">Added new suffixes for numeric literals - see [about_Numeric_Literals][] (#7901) (Thanks @vexx32!)</span></span>
- <span data-ttu-id="8b7d2-172">Ordnungsgemäßes Melden des Schweregrads, wenn SupportsShouldProcess nicht auf „true“ festgelegt ist (#8209) – vielen Dank an @vexx32!</span><span class="sxs-lookup"><span data-stu-id="8b7d2-172">Correctly Report impact level when SupportsShouldProcess is not set to 'true' (#8209) (Thanks @vexx32!)</span></span>
- <span data-ttu-id="8b7d2-173">Beheben von Problemen mit der Zeichensatzanforderung in Web-Cmdlets (#8742) – vielen Dank an @markekraus!</span><span class="sxs-lookup"><span data-stu-id="8b7d2-173">Fix Request Charset Issues in Web Cmdlets (#8742) (Thanks @markekraus!)</span></span>
- <span data-ttu-id="8b7d2-174">Beheben des erwarteten `100-continue`-Problems mit Web-Cmdlets (#8679) – vielen Dank an @markekraus!</span><span class="sxs-lookup"><span data-stu-id="8b7d2-174">Fix Expect `100-continue` issue with Web Cmdlets (#8679) (Thanks @markekraus!)</span></span>
- <span data-ttu-id="8b7d2-175">Beheben des Dateiblockierungsproblems mit Web-Cmdlets (#7676) – vielen Dank an @Claustn!</span><span class="sxs-lookup"><span data-stu-id="8b7d2-175">Fix file blocking issue with web cmdlets (#7676) (Thanks @Claustn!)</span></span>
- <span data-ttu-id="8b7d2-176">Beheben des Codeseitenanalyse-Problems in `Invoke-RestMethod` (#8694) – vielen Dank an @markekraus!</span><span class="sxs-lookup"><span data-stu-id="8b7d2-176">Fix code page parsing issue in `Invoke-RestMethod` (#8694) (Thanks @markekraus!)</span></span>
- <span data-ttu-id="8b7d2-177">Umgestalten von `ConvertTo-Json`, um JsonObject.ConvertToJson als öffentliche API verfügbar zu machen (#8682)</span><span class="sxs-lookup"><span data-stu-id="8b7d2-177">Refactor `ConvertTo-Json` to expose JsonObject.ConvertToJson as a public API (#8682)</span></span>
- <span data-ttu-id="8b7d2-178">Hinzufügen von konfigurierbarer maximaler Tiefe in `ConvertFrom-Json` mit „-Depth“ (#8199) – vielen Dank an @louistio!</span><span class="sxs-lookup"><span data-stu-id="8b7d2-178">Add configurable maximum depth in `ConvertFrom-Json` with -Depth (#8199) (Thanks @louistio!)</span></span>
- <span data-ttu-id="8b7d2-179">Hinzufügen des EscapeHandling-Parameters in `ConvertTo-Json`-Cmdlet (#7775) – vielen Dank an @iSazonov!</span><span class="sxs-lookup"><span data-stu-id="8b7d2-179">Add EscapeHandling parameter in `ConvertTo-Json` cmdlet (#7775) (Thanks @iSazonov!)</span></span>
- <span data-ttu-id="8b7d2-180">Hinzufügen von `-CustomPipeName` zu PowerShell und `Enter-PSHostProcess` (#8889)</span><span class="sxs-lookup"><span data-stu-id="8b7d2-180">Add `-CustomPipeName` to pwsh and `Enter-PSHostProcess` (#8889)</span></span>
- <span data-ttu-id="8b7d2-181">Relative symbolische Verknüpfungen können mit `New-Item` unter Windows erstellt werden (#8783)</span><span class="sxs-lookup"><span data-stu-id="8b7d2-181">Enable creating relative symbolic links on Windows with `New-Item` (#8783)</span></span>
- <span data-ttu-id="8b7d2-182">Zulassen, das Windows-Benutzer im Entwicklermodus ohne Rechteerweiterung symbolische Verknüpfungen erstellen (#8534)</span><span class="sxs-lookup"><span data-stu-id="8b7d2-182">Allow Windows users in developer mode to create symlinks without elevation (#8534)</span></span>
- <span data-ttu-id="8b7d2-183">`Write-Information` akzeptiert `$null` (#8774)</span><span class="sxs-lookup"><span data-stu-id="8b7d2-183">Enable `Write-Information` to accept `$null` (#8774)</span></span>
- <span data-ttu-id="8b7d2-184">Korrigieren von `Get-Help` für erweiterte Funktionen mit MAML-Hilfeinhalt (#8353)</span><span class="sxs-lookup"><span data-stu-id="8b7d2-184">Fix `Get-Help` for advanced functions with MAML help content (#8353)</span></span>
- <span data-ttu-id="8b7d2-185">Beheben des `Get-Help`-PSTypeName-Problems mit „-Parameter“, wenn nur ein Parameter deklariert wird (#8754) – vielen Dank an @pougetat!</span><span class="sxs-lookup"><span data-stu-id="8b7d2-185">Fix `Get-Help` PSTypeName issue with -Parameter when only one parameter is declared (#8754) (Thanks @pougetat!)</span></span>
- <span data-ttu-id="8b7d2-186">Korrektur der Tokenberechnung für `Get-Help` ausgeführt auf ScriptBlock für Kommentarhilfe.</span><span class="sxs-lookup"><span data-stu-id="8b7d2-186">Token calculation fix for `Get-Help` executed on ScriptBlock for comment help.</span></span> <span data-ttu-id="8b7d2-187">(#8238) – vielen Dank an @hubuk!</span><span class="sxs-lookup"><span data-stu-id="8b7d2-187">(#8238) (Thanks @hubuk!)</span></span>
- <span data-ttu-id="8b7d2-188">Änderung des `Get-Help` Cmdlet-Parameters „-Parameter“, sodass er Zeichenfolgenarrays akzeptiert (#8454) – vielen Dank an @sethvs!</span><span class="sxs-lookup"><span data-stu-id="8b7d2-188">Change `Get-Help` cmdlet -Parameter parameter so it accepts string arrays (#8454) (Thanks @sethvs!)</span></span>
- <span data-ttu-id="8b7d2-189">Korrektur bei PAGER für den Fall, dass der Pfad Leerzeichen enthält (#8571) – vielen Dank an @pougetat!</span><span class="sxs-lookup"><span data-stu-id="8b7d2-189">Resolve PAGER if its path contains spaces (#8571) (Thanks @pougetat!)</span></span>
- <span data-ttu-id="8b7d2-190">Hinzufügen einer Eingabeaufforderung bei Verwendung von `less` in der Funktion „help“", um Benutzer anzuweisen, wie sie beenden sollen (#7998)</span><span class="sxs-lookup"><span data-stu-id="8b7d2-190">Add prompt to the use of `less` in the function 'help' to instruct user how to quit (#7998)</span></span>
- <span data-ttu-id="8b7d2-191">Hinzufügen von Unterstützung für Enumerations- und Char-Datentyp in `Format-Hex`-Cmdlet (#8191) – vielen Dank an @iSazonov!</span><span class="sxs-lookup"><span data-stu-id="8b7d2-191">Add support enum and char types in `Format-Hex` cmdlet (#8191) (Thanks @iSazonov!)</span></span>
- <span data-ttu-id="8b7d2-192">Entfernen von ShouldProcess aus `Format-Hex` (#8178)</span><span class="sxs-lookup"><span data-stu-id="8b7d2-192">Remove ShouldProcess from `Format-Hex` (#8178)</span></span>
- <span data-ttu-id="8b7d2-193">Hinzufügen der neuen Parameter „Offset“ und „Count“ zu `Format-Hex` und Umgestalten des Cmdlets (#7877) – vielen Dank an @iSazonov!</span><span class="sxs-lookup"><span data-stu-id="8b7d2-193">Add new Offset and Count parameters to `Format-Hex` and refactor the cmdlet (#7877) (Thanks @iSazonov!)</span></span>
- <span data-ttu-id="8b7d2-194">Zulassen von „name“ als Aliasschlüssel für „label“ in `ConvertTo-Html`, Zulassen des Eintrags „width“ als Ganzzahl (#8426) – vielen Dank an @mklement0!</span><span class="sxs-lookup"><span data-stu-id="8b7d2-194">Allow 'name' as an alias key for 'label' in `ConvertTo-Html`, allow the 'width' entry to be an integer (#8426) (Thanks @mklement0!)</span></span>
- <span data-ttu-id="8b7d2-195">ScriptBlock-basierte berechnete Eigenschaften funktionieren wieder in `ConvertTo-Html` (#8427) – vielen Dank an @mklement0!</span><span class="sxs-lookup"><span data-stu-id="8b7d2-195">Make scriptblock based calculated properties work again in `ConvertTo-Html` (#8427) (Thanks @mklement0!)</span></span>
- <span data-ttu-id="8b7d2-196">Hinzufügen des Cmdlets `Join-String` zum Erstellen von Text aus der Pipelineeingabe (#7660) – vielen Dank an @powercode!</span><span class="sxs-lookup"><span data-stu-id="8b7d2-196">Add cmdlet `Join-String` for creating text from pipeline input (#7660) (Thanks @powercode!)</span></span>
- <span data-ttu-id="8b7d2-197">Korrektur der FormatString-Parameterlogik des `Join-String`-Cmdlets (#8449) – vielen Dank an @sethvs!</span><span class="sxs-lookup"><span data-stu-id="8b7d2-197">Fix `Join-String` cmdlet FormatString parameter logic (#8449) (Thanks @sethvs!)</span></span>
- <span data-ttu-id="8b7d2-198">Änderung von `Clear-Host` zurück zur Verwendung von `$RAWUI` und Bereitmachen zur Arbeit mit Remoting (#8609)</span><span class="sxs-lookup"><span data-stu-id="8b7d2-198">Change `Clear-Host` back to using `$RAWUI` and clear to work over remoting (#8609)</span></span>
- <span data-ttu-id="8b7d2-199">Änderung von `Clear-Host` in einfach aufgerufenes `[console]::clear` und Entfernen des clear-Alias aus Unix (#8603)</span><span class="sxs-lookup"><span data-stu-id="8b7d2-199">Change `Clear-Host` to simply called `[console]::clear` and remove clear alias from Unix (#8603)</span></span>
- <span data-ttu-id="8b7d2-200">LiteralPath in `Import-Csv` wird an `Get-ChildItem`-Ausgabe gebunden (#8277) – vielen Dank an @iSazonov!</span><span class="sxs-lookup"><span data-stu-id="8b7d2-200">Fix LiteralPath in `Import-Csv` to bind to `Get-ChildItem` output (#8277) (Thanks @iSazonov!)</span></span>
- <span data-ttu-id="8b7d2-201">Hilfefunktion sollte Pager nicht für AliasHelpInfo verwenden (#8552)</span><span class="sxs-lookup"><span data-stu-id="8b7d2-201">help function shouldn't use pager for AliasHelpInfo (#8552)</span></span>
- <span data-ttu-id="8b7d2-202">Hinzufügen von `-UseMinimalHeader` zu `Start-Transcript`, um Aufzeichnungsheader zu minimieren (#8402) – vielen Dank an @lukexjeremy!</span><span class="sxs-lookup"><span data-stu-id="8b7d2-202">Add `-UseMinimalHeader` to `Start-Transcript` to minimize transcript header (#8402) (Thanks @lukexjeremy!)</span></span>
- <span data-ttu-id="8b7d2-203">Hinzufügen der Cmdlets `Enable-ExperimentalFeature` und `Disable-ExperimentalFeature` (#8318)</span><span class="sxs-lookup"><span data-stu-id="8b7d2-203">Add `Enable-ExperimentalFeature` and `Disable-ExperimentalFeature` cmdlets (#8318)</span></span>
- <span data-ttu-id="8b7d2-204">Verfügbar machen aller Cmdlets aus **PSDiagnostics**, wenn „logman.exe“ verfügbar ist (#8366)</span><span class="sxs-lookup"><span data-stu-id="8b7d2-204">Expose all cmdlets from **PSDiagnostics** if logman.exe is available (#8366)</span></span>
- <span data-ttu-id="8b7d2-205">Entfernen des **Persist**-Parameters aus `New-PSDrive` auf der `non-Windows`-Plattform (#8291) – vielen Dank an @lukexjeremy!</span><span class="sxs-lookup"><span data-stu-id="8b7d2-205">Remove **Persist** parameter from `New-PSDrive` on `non-Windows` platform (#8291) (Thanks @lukexjeremy!)</span></span>
- <span data-ttu-id="8b7d2-206">Hinzufügen von Unterstützung für `cd +` (#7206) – vielen Dank an @bergmeister!</span><span class="sxs-lookup"><span data-stu-id="8b7d2-206">Add support for `cd +` (#7206) (Thanks @bergmeister!)</span></span>
- <span data-ttu-id="8b7d2-207">`Set-Location -LiteralPath` funktioniert mit Ordnern, die mit „-“ und „+“ benannt sind (#8089)</span><span class="sxs-lookup"><span data-stu-id="8b7d2-207">Enable `Set-Location -LiteralPath` to work with folders named - and + (#8089)</span></span>
- <span data-ttu-id="8b7d2-208">`Test-Path` gibt `$false` zurück, wenn ein leerer oder `$null`-Pfadwert übergeben wird (#8080) – vielen Dank an @vexx32!</span><span class="sxs-lookup"><span data-stu-id="8b7d2-208">`Test-Path` returns `$false` when given an empty or `$null` path value (#8080) (Thanks @vexx32!)</span></span>
- <span data-ttu-id="8b7d2-209">Dynamische Parameter können auch dann zurückgegeben werden, wenn der Pfad mit keinem Anbieter übereinstimmt (#7957)</span><span class="sxs-lookup"><span data-stu-id="8b7d2-209">Allow dynamic parameter to be returned even if path does not match any provider (#7957)</span></span>
- <span data-ttu-id="8b7d2-210">Unterstützung von `Get-PSHostProcessInfo` und `Enter-PSHostProcess` auf Unix-Plattformen (#8232)</span><span class="sxs-lookup"><span data-stu-id="8b7d2-210">Support `Get-PSHostProcessInfo` and `Enter-PSHostProcess` on Unix platforms (#8232)</span></span>
- <span data-ttu-id="8b7d2-211">Reduzieren der Zuordnungen im `Get-Content`-Cmdlet (#8103) – vielen Dank an @iSazonov!</span><span class="sxs-lookup"><span data-stu-id="8b7d2-211">Reduce allocations in `Get-Content` cmdlet (#8103) (Thanks @iSazonov!)</span></span>
- <span data-ttu-id="8b7d2-212">`Add-Content` kann den Lesezugriff beim Schreiben von Inhalt mit anderen Tools gemeinsam nutzen (#8091)</span><span class="sxs-lookup"><span data-stu-id="8b7d2-212">Enable `Add-Content` to share read access with other tools while writing content (#8091)</span></span>
- <span data-ttu-id="8b7d2-213">Von `Get/Add-Content` bei Anwendung auf einen Container ausgelöste Fehlermeldungen wurden verbessert (#7823) – vielen Dank an @kvprasoon!</span><span class="sxs-lookup"><span data-stu-id="8b7d2-213">`Get/Add-Content` throws improved error when targeting a container (#7823) (Thanks @kvprasoon!)</span></span>
- <span data-ttu-id="8b7d2-214">Dem `Get-Culture`-Cmdlet wurden die Parameter `-Name`, `-NoUserOverrides` und `-ListAvailable` hinzugefügt. (#7702) – Vielen Dank an @iSazonov!</span><span class="sxs-lookup"><span data-stu-id="8b7d2-214">Add `-Name`, `-NoUserOverrides` and `-ListAvailable` parameters to `Get-Culture` cmdlet (#7702) (Thanks @iSazonov!)</span></span>
- <span data-ttu-id="8b7d2-215">Hinzufügen eines vereinheitlichten Attribut für die Vervollständigung des **Encoding**-Parameters.</span><span class="sxs-lookup"><span data-stu-id="8b7d2-215">Add unified attribute for completion for **Encoding** parameter.</span></span> <span data-ttu-id="8b7d2-216">(#7732) – Vielen Dank an @ThreeFive-O!</span><span class="sxs-lookup"><span data-stu-id="8b7d2-216">(#7732) (Thanks @ThreeFive-O!)</span></span>
- <span data-ttu-id="8b7d2-217">Zulassen von numerischen IDs und Namen registrierter Codepages in **Encoding**-Parametern (#7636) – vielen Dank an @iSazonov!</span><span class="sxs-lookup"><span data-stu-id="8b7d2-217">Allow numeric Ids and name of registered code pages in **Encoding** parameters (#7636) (Thanks @iSazonov!)</span></span>
- <span data-ttu-id="8b7d2-218">Korrektur von `Rename-Item -Path` mit Platzhalterzeichen (#7398) – vielen Dank an @kwkam!</span><span class="sxs-lookup"><span data-stu-id="8b7d2-218">Fix `Rename-Item -Path` with wildcard char (#7398) (Thanks @kwkam!)</span></span>
- <span data-ttu-id="8b7d2-219">Wenn bei Verwendung von `Start-Transcript` eine Datei vorhanden ist, Datei leeren statt löschen (#8131) – vielen Dank an @paalbra!</span><span class="sxs-lookup"><span data-stu-id="8b7d2-219">When using `Start-Transcript` and file exists, empty file rather than deleting (#8131) (Thanks @paalbra!)</span></span>
- <span data-ttu-id="8b7d2-220">`Add-Type` öffnet Quelldateien explizit mit **FileAccess.Read** und **FileShare.Read** (#7915) – vielen Dank an @IISResetMe!</span><span class="sxs-lookup"><span data-stu-id="8b7d2-220">Make `Add-Type` open source files with **FileAccess.Read** and **FileShare.Read** explicitly (#7915) (Thanks @IISResetMe!)</span></span>
- <span data-ttu-id="8b7d2-221">Korrektur von `Enter-PSSession -ContainerId` für aktuelle Windows-Version (#7883)</span><span class="sxs-lookup"><span data-stu-id="8b7d2-221">Fix `Enter-PSSession -ContainerId` for the latest Windows (#7883)</span></span>
- <span data-ttu-id="8b7d2-222">Sicherstellen, dass **NestedModules**-Eigenschaft durch `Test-ModuleManifest` aufgefüllt wird (#7859)</span><span class="sxs-lookup"><span data-stu-id="8b7d2-222">Ensure **NestedModules** property gets populated by `Test-ModuleManifest` (#7859)</span></span>
- <span data-ttu-id="8b7d2-223">Hinzufügen des `%F`-Falls zu `Get-Date` -UFormat (#7630) – vielen Dank an @britishben!</span><span class="sxs-lookup"><span data-stu-id="8b7d2-223">Add `%F` case to `Get-Date` -UFormat (#7630) (Thanks @britishben!)</span></span>
- <span data-ttu-id="8b7d2-224">Korrektur von `Set-Service -Status Stopped` zum Beenden von Diensten mit Abhängigkeiten (#5525) – vielen Dank an @zhenggu!</span><span class="sxs-lookup"><span data-stu-id="8b7d2-224">Fix `Set-Service -Status Stopped` to stop services with dependencies (#5525) (Thanks @zhenggu!)</span></span>

<!-- Link references -->
[about_Numeric_Literals]: /powershell/module/Microsoft.PowerShell.Core/About/about_numeric_literals
[Experimentelle Features]: /powershell/module/Microsoft.PowerShell.Core/About/about_Experimental_Features
[Experimental Features]: /powershell/module/Microsoft.PowerShell.Core/About/about_Experimental_Features
[PSDrive]: /powershell/module/microsoft.powershell.management/new-psdrive