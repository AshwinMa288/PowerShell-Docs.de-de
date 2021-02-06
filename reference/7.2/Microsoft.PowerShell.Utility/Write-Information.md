---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 10/14/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/write-information?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Write-Information
ms.openlocfilehash: f15902c1c6c298dd02db3edf061d56e1446ecb1f
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99600692"
---
# <span data-ttu-id="20bac-102">Write-Information</span><span class="sxs-lookup"><span data-stu-id="20bac-102">Write-Information</span></span>

## <span data-ttu-id="20bac-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="20bac-103">SYNOPSIS</span></span>

<span data-ttu-id="20bac-104">Gibt an, wie PowerShell Daten in einem Informationsdaten Strom für einen Befehl verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="20bac-104">Specifies how PowerShell handles information stream data for a command.</span></span>

## <span data-ttu-id="20bac-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="20bac-105">SYNTAX</span></span>

```
Write-Information [-MessageData] <Object> [[-Tags] <String[]>] [<CommonParameters>]
```

## <span data-ttu-id="20bac-106">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="20bac-106">DESCRIPTION</span></span>

<span data-ttu-id="20bac-107">Das- `Write-Information` Cmdlet gibt an, wie PowerShell Daten in einem Informationsdaten Strom für einen Befehl verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="20bac-107">The `Write-Information` cmdlet specifies how PowerShell handles information stream data for a command.</span></span>

<span data-ttu-id="20bac-108">Windows PowerShell 5,0 führt einen neuen, strukturierten Informationsdaten Strom ein.</span><span class="sxs-lookup"><span data-stu-id="20bac-108">Windows PowerShell 5.0 introduces a new, structured information stream.</span></span> <span data-ttu-id="20bac-109">Mit diesem Stream können Sie strukturierte Daten zwischen einem Skript und seinen Aufrufern oder der Host Anwendung übertragen.</span><span class="sxs-lookup"><span data-stu-id="20bac-109">You can use this stream to transmit structured data between a script and its callers or the host application.</span></span>
<span data-ttu-id="20bac-110">`Write-Information` ermöglicht es Ihnen, dem Stream eine Informations Meldung hinzuzufügen und anzugeben, wie PowerShell Daten in einem Informationsdaten Strom für einen Befehl verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="20bac-110">`Write-Information` lets you add an informational message to the stream, and specify how PowerShell handles information stream data for a command.</span></span> <span data-ttu-id="20bac-111">Informationsdaten Ströme funktionieren auch für `PowerShell.Streams` , Aufträge und geplante Aufgaben.</span><span class="sxs-lookup"><span data-stu-id="20bac-111">Information streams also work for `PowerShell.Streams`, jobs, and scheduled tasks.</span></span>

> [!NOTE]
> <span data-ttu-id="20bac-112">Der Informationsdaten Strom folgt nicht der Standard Konvention, dass seine Nachrichten mit "[Stream Name]:" vorangestellt werden.</span><span class="sxs-lookup"><span data-stu-id="20bac-112">The information stream does not follow the standard convention of prefixing its messages with "[Stream Name]:".</span></span> <span data-ttu-id="20bac-113">Dies wurde aus Gründen der Kürze und visuellen Sauberkeit bestimmt.</span><span class="sxs-lookup"><span data-stu-id="20bac-113">This was intended for brevity and visual cleanliness.</span></span>

<span data-ttu-id="20bac-114">Der `$InformationPreference` Wert der Einstellungs Variablen bestimmt, ob die Nachricht, die Sie für bereitstellen, zu `Write-Information` dem erwarteten Zeitpunkt im Vorgang eines Skripts angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="20bac-114">The `$InformationPreference` preference variable value determines whether the message you provide to `Write-Information` is displayed at the expected point in a script's operation.</span></span> <span data-ttu-id="20bac-115">Da der Standardwert dieser Variablen Standard `SilentlyContinue` mäßig nicht angezeigt wird, werden keine Informationsmeldungen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="20bac-115">Because the default value of this variable is `SilentlyContinue`, by default, informational messages are not shown.</span></span> <span data-ttu-id="20bac-116">Wenn Sie den Wert von nicht ändern möchten `$InformationPreference` , können Sie seinen Wert überschreiben, indem Sie dem `InformationAction` Befehl den allgemeinen Parameter hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="20bac-116">If you don't want to change the value of `$InformationPreference`, you can override its value by adding the `InformationAction` common parameter to your command.</span></span> <span data-ttu-id="20bac-117">Weitere Informationen finden Sie unter [about_Preference_Variables](../Microsoft.PowerShell.Core/About/about_Preference_Variables.md) und [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span><span class="sxs-lookup"><span data-stu-id="20bac-117">For more information, see [about_Preference_Variables](../Microsoft.PowerShell.Core/About/about_Preference_Variables.md) and [about_CommonParameters](../Microsoft.PowerShell.Core/About/about_CommonParameters.md).</span></span>

> [!NOTE]
> <span data-ttu-id="20bac-118">Ab Windows PowerShell 5,0 `Write-Host` ist ein Wrapper dafür, mit `Write-Information` `Write-Host` dem Sie die Ausgabe an den Informationsdaten Strom ausgeben können.</span><span class="sxs-lookup"><span data-stu-id="20bac-118">Starting in Windows PowerShell 5.0, `Write-Host` is a wrapper for `Write-Information` This allows you to use `Write-Host` to emit output to the information stream.</span></span> <span data-ttu-id="20bac-119">Dies ermöglicht die **Erfassung** oder **Unterdrückung** von Daten, die mithilfe von geschrieben wurden, während die abwärts `Write-Host` Kompatibilität beibehalten wird.</span><span class="sxs-lookup"><span data-stu-id="20bac-119">This enables the **capture** or **suppression** of data written using `Write-Host` while preserving backwards compatibility.</span></span> <span data-ttu-id="20bac-120">Weitere Informationen finden Sie unter [Write-Host](Write-Host.md) .</span><span class="sxs-lookup"><span data-stu-id="20bac-120">For more information see [Write-Host](Write-Host.md)</span></span>

<span data-ttu-id="20bac-121">`Write-Information` ist auch eine unterstützte Workflow Aktivität in PowerShell 5. x.</span><span class="sxs-lookup"><span data-stu-id="20bac-121">`Write-Information` is also a supported workflow activity in PowerShell 5.x.</span></span>

## <span data-ttu-id="20bac-122">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="20bac-122">EXAMPLES</span></span>

### <span data-ttu-id="20bac-123">Beispiel 1: Schreiben von Informationen für get-results</span><span class="sxs-lookup"><span data-stu-id="20bac-123">Example 1: Write information for Get- results</span></span>

<span data-ttu-id="20bac-124">In diesem Beispiel wird eine Informations Meldung mit dem Namen "hat ihre Features!" angezeigt, nachdem der Befehl ausgeführt wurde, `Get-WindowsFeature` um alle Features zu finden, deren namens Wert mit "p" beginnt.</span><span class="sxs-lookup"><span data-stu-id="20bac-124">In this example, you show an informational message, "Got your features!", after running the `Get-WindowsFeature` command to find all features that have a Name value that starts with 'p'.</span></span>
<span data-ttu-id="20bac-125">Da die- `$InformationPreference` Variable weiterhin auf den Standardwert festgelegt ist, `SilentlyContinue` fügen Sie den `InformationAction` -Parameter hinzu, um den Wert zu überschreiben `$InformationPreference` , und zeigen Sie die Meldung an.</span><span class="sxs-lookup"><span data-stu-id="20bac-125">Because the `$InformationPreference` variable is still set to its default, `SilentlyContinue`, you add the `InformationAction` parameter to override the `$InformationPreference` value, and show the message.</span></span> <span data-ttu-id="20bac-126">Der `InformationAction` Wert lautet "Continue", was bedeutet, dass die Meldung angezeigt wird, das Skript oder der Befehl jedoch fortgesetzt wird, wenn er noch nicht abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="20bac-126">The `InformationAction` value is Continue, which means that your message is shown, but the script or command continues, if it is not yet finished.</span></span>

```powershell
Get-WindowsFeature -Name p*
Write-Information -MessageData "Got your features!" -InformationAction Continue
```

```Output
Display Name                                            Name                       Install State
------------                                            ----                       -------------
[ ] Print and Document Services                         Print-Services                 Available
    [ ] Print Server                                    Print-Server                   Available
    [ ] Distributed Scan Server                         Print-Scan-Server              Available
    [ ] Internet Printing                               Print-Internet                 Available
    [ ] LPD Service                                     Print-LPD-Service              Available
[ ] Peer Name Resolution Protocol                       PNRP                           Available
[X] Windows PowerShell                                  PowerShellRoot                 Installed
    [X] Windows PowerShell 5.0                          PowerShell                     Installed
    [ ] Windows PowerShell 2.0 Engine                   PowerShell-V2                    Removed
    [X] Windows PowerShell ISE                          PowerShell-ISE                 Installed
Got your features!
```

### <span data-ttu-id="20bac-127">Beispiel 2: Schreiben von Informationen und Markieren dieser Informationen</span><span class="sxs-lookup"><span data-stu-id="20bac-127">Example 2: Write information and tag it</span></span>

<span data-ttu-id="20bac-128">In diesem Beispiel verwenden Sie, `Write-Information` um Benutzer darüber zu informieren, dass Sie einen weiteren Befehl ausführen müssen, nachdem Sie den aktuellen Befehl ausgeführt haben.</span><span class="sxs-lookup"><span data-stu-id="20bac-128">In this example, you use `Write-Information` to let users know they'll need to run another command after they're done running the current command.</span></span> <span data-ttu-id="20bac-129">Im Beispiel werden der Informations Meldung die taganweisungen hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="20bac-129">The example adds the tag Instructions to the informational message.</span></span> <span data-ttu-id="20bac-130">Wenn Sie nach dem Ausführen dieses Befehls den Informationsdaten Strom nach Nachrichten mit markierten Anweisungen durchsuchen, wird die hier angegebene Meldung in den Ergebnissen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="20bac-130">After running this command, if you search the information stream for messages tagged Instructions, the message specified here would be among the results.</span></span>

```powershell
$message = "To filter your results for PowerShell, pipe your results to the Where-Object cmdlet."
Get-WindowsFeature -Name p*
Write-Information -MessageData $message -Tags "Instructions" -InformationAction Continue
```

```Output
Display Name                                            Name                       Install State
------------                                            ----                       -------------
[ ] Print and Document Services                         Print-Services                 Available
    [ ] Print Server                                    Print-Server                   Available
    [ ] Distributed Scan Server                         Print-Scan-Server              Available
    [ ] Internet Printing                               Print-Internet                 Available
    [ ] LPD Service                                     Print-LPD-Service              Available
[ ] Peer Name Resolution Protocol                       PNRP                           Available
[X] Windows PowerShell                                  PowerShellRoot                 Installed
    [X] Windows PowerShell 5.0                          PowerShell                     Installed
    [ ] Windows PowerShell 2.0 Engine                   PowerShell-V2                    Removed
    [X] Windows PowerShell ISE                          PowerShell-ISE                 Installed
To filter your results for PowerShell, pipe your results to the Where-Object cmdlet.
```

### <span data-ttu-id="20bac-131">Beispiel 3: Schreiben von Informationen in eine Datei</span><span class="sxs-lookup"><span data-stu-id="20bac-131">Example 3: Write information to a file</span></span>

<span data-ttu-id="20bac-132">In diesem Beispiel leiten Sie den Informationsdaten Strom in der Funktion `Info.txt` mithilfe des Codes an einen um `6>` .</span><span class="sxs-lookup"><span data-stu-id="20bac-132">In this example, you redirect the information stream in the function to a `Info.txt` using the code `6>`.</span></span> <span data-ttu-id="20bac-133">Wenn Sie die `Info.txt` Datei öffnen, wird der Text "hier los" angezeigt.</span><span class="sxs-lookup"><span data-stu-id="20bac-133">When you open the `Info.txt` file, you see the text, "Here you go."</span></span>

```powershell
function Test-Info
{
    Get-Process P*
    Write-Information "Here you go"
}
Test-Info 6> Info.txt
```

### <span data-ttu-id="20bac-134">Beispiel 4: übergeben von Informationen zum Schreiben von Objekten</span><span class="sxs-lookup"><span data-stu-id="20bac-134">Example 4: Pass object to write information</span></span>

<span data-ttu-id="20bac-135">In diesem Beispiel können Sie verwenden, `Write-Information` um die ersten 10 höchsten CPU-Auslastungs Prozesse aus der `Get-Process` Objekt Ausgabe zu schreiben, die mehrere Pipelines durchläuft.</span><span class="sxs-lookup"><span data-stu-id="20bac-135">In this example, you can use `Write-Information` to write the top 10 highest CPU utilization processes from the `Get-Process` object output that has passes through multiple pipelines.</span></span>

```powershell
Get-Process | Sort-Object CPU -Descending |
    Select-Object Id, ProcessName, CPU -First 10 |
        Write-Information -InformationAction Continue
```

```Output
@{Id=12692; ProcessName=chrome; CPU=39431.296875}
@{Id=21292; ProcessName=OUTLOOK; CPU=23991.875}
@{Id=10548; ProcessName=CefSharp.BrowserSubprocess; CPU=20546.203125}
@{Id=312848; ProcessName=Taskmgr; CPU=13173.1875}
@{Id=10848; ProcessName=SnapClient; CPU=7014.265625}
@{Id=9760; ProcessName=Receiver; CPU=6792.359375}
@{Id=12040; ProcessName=Teams; CPU=5605.578125}
@{Id=498388; ProcessName=chrome; CPU=3062.453125}
@{Id=6900; ProcessName=chrome; CPU=2546.9375}
@{Id=9044; ProcessName=explorer; CPU=2358.765625}
```

## <span data-ttu-id="20bac-136">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="20bac-136">PARAMETERS</span></span>

### <span data-ttu-id="20bac-137">-MessageData</span><span class="sxs-lookup"><span data-stu-id="20bac-137">-MessageData</span></span>

<span data-ttu-id="20bac-138">Gibt eine Informations Meldung an, die Benutzern angezeigt werden soll, wenn Sie ein Skript oder einen Befehl ausführen.</span><span class="sxs-lookup"><span data-stu-id="20bac-138">Specifies an informational message that you want to display to users as they run a script or command.</span></span> <span data-ttu-id="20bac-139">Schließen Sie die Informations Meldung in Anführungszeichen ein, um optimale Ergebnisse zu erzielen.</span><span class="sxs-lookup"><span data-stu-id="20bac-139">For best results, enclose the informational message in quotation marks.</span></span>

```yaml
Type: System.Object
Parameter Sets: (All)
Aliases: Msg, Message

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="20bac-140">-Tags</span><span class="sxs-lookup"><span data-stu-id="20bac-140">-Tags</span></span>

<span data-ttu-id="20bac-141">Gibt eine einfache Zeichenfolge an, mit der Sie Nachrichten, die Sie dem Informationsdaten Strom hinzugefügt haben, Sortieren und Filtern können `Write-Information` .</span><span class="sxs-lookup"><span data-stu-id="20bac-141">Specifies a simple string that you can use to sort and filter messages that you have added to the information stream with `Write-Information`.</span></span> <span data-ttu-id="20bac-142">Dieser Parameter funktioniert ähnlich wie der **Tags** -Parameter in `New-ModuleManifest` .</span><span class="sxs-lookup"><span data-stu-id="20bac-142">This parameter works similarly to the **Tags** parameter in `New-ModuleManifest`.</span></span>

```yaml
Type: System.String[]
Parameter Sets: (All)
Aliases:

Required: False
Position: 1
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="20bac-143">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="20bac-143">CommonParameters</span></span>

<span data-ttu-id="20bac-144">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="20bac-144">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="20bac-145">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="20bac-145">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="20bac-146">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="20bac-146">INPUTS</span></span>

### <span data-ttu-id="20bac-147">System.Object</span><span class="sxs-lookup"><span data-stu-id="20bac-147">System.Object</span></span>

<span data-ttu-id="20bac-148">`Write-Information` akzeptiert weitergeleitete Objekte, die an den Informationsdaten Strom übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="20bac-148">`Write-Information` accepts piped objects to pass to the information stream.</span></span>

## <span data-ttu-id="20bac-149">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="20bac-149">OUTPUTS</span></span>

### <span data-ttu-id="20bac-150">System. Management. Automation. informationrecord</span><span class="sxs-lookup"><span data-stu-id="20bac-150">System.Management.Automation.InformationRecord</span></span>

## <span data-ttu-id="20bac-151">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="20bac-151">NOTES</span></span>

## <span data-ttu-id="20bac-152">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="20bac-152">RELATED LINKS</span></span>

[<span data-ttu-id="20bac-153">about_Output_Streams</span><span class="sxs-lookup"><span data-stu-id="20bac-153">about_Output_Streams</span></span>](../Microsoft.PowerShell.Core/About/about_Output_Streams.md)

[<span data-ttu-id="20bac-154">about_Redirection</span><span class="sxs-lookup"><span data-stu-id="20bac-154">about_Redirection</span></span>](../Microsoft.PowerShell.Core/About/about_Redirection.md)

[<span data-ttu-id="20bac-155">about_CommonParameters</span><span class="sxs-lookup"><span data-stu-id="20bac-155">about_CommonParameters</span></span>](../Microsoft.PowerShell.Core/About/about_CommonParameters.md)

[<span data-ttu-id="20bac-156">about_Preference_Variables</span><span class="sxs-lookup"><span data-stu-id="20bac-156">about_Preference_Variables</span></span>](../Microsoft.PowerShell.Core/About/about_Preference_Variables.md)

[<span data-ttu-id="20bac-157">about_Redirection</span><span class="sxs-lookup"><span data-stu-id="20bac-157">about_Redirection</span></span>](../Microsoft.PowerShell.Core/About/about_Redirection.md)

[<span data-ttu-id="20bac-158">Write-Debug</span><span class="sxs-lookup"><span data-stu-id="20bac-158">Write-Debug</span></span>](Write-Debug.md)

[<span data-ttu-id="20bac-159">Write-Host</span><span class="sxs-lookup"><span data-stu-id="20bac-159">Write-Host</span></span>](Write-Host.md)

[<span data-ttu-id="20bac-160">Write-Information</span><span class="sxs-lookup"><span data-stu-id="20bac-160">Write-Information</span></span>](Write-Information.md)

[<span data-ttu-id="20bac-161">Write-Progress</span><span class="sxs-lookup"><span data-stu-id="20bac-161">Write-Progress</span></span>](Write-Progress.md)

[<span data-ttu-id="20bac-162">Write-Verbose</span><span class="sxs-lookup"><span data-stu-id="20bac-162">Write-Verbose</span></span>](Write-Verbose.md)

[<span data-ttu-id="20bac-163">Write-Warning</span><span class="sxs-lookup"><span data-stu-id="20bac-163">Write-Warning</span></span>](Write-Warning.md)

[<span data-ttu-id="20bac-164">Write-Output</span><span class="sxs-lookup"><span data-stu-id="20bac-164">Write-Output</span></span>](Write-Output.md)