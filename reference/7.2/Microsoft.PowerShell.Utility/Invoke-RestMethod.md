---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Locale: en-US
Module Name: Microsoft.PowerShell.Utility
ms.date: 09/03/2020
online version: https://docs.microsoft.com/powershell/module/microsoft.powershell.utility/invoke-restmethod?view=powershell-7.2&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Invoke-RestMethod
ms.openlocfilehash: 91cd2dda912d6e79177e8a961012a1604d9460ee
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99596356"
---
# <span data-ttu-id="5de27-102">Invoke-RestMethod</span><span class="sxs-lookup"><span data-stu-id="5de27-102">Invoke-RestMethod</span></span>

## <span data-ttu-id="5de27-103">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="5de27-103">SYNOPSIS</span></span>
<span data-ttu-id="5de27-104">Sendet eine HTTP- oder HTTPS-Anforderung an einen RESTful-Webdienst.</span><span class="sxs-lookup"><span data-stu-id="5de27-104">Sends an HTTP or HTTPS request to a RESTful web service.</span></span>

## <span data-ttu-id="5de27-105">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="5de27-105">SYNTAX</span></span>

### <span data-ttu-id="5de27-106">Standardmethod (Standard)</span><span class="sxs-lookup"><span data-stu-id="5de27-106">StandardMethod (Default)</span></span>

```
Invoke-RestMethod [-Method <WebRequestMethod>] [-FollowRelLink] [-MaximumFollowRelLink <Int32>]
 [-ResponseHeadersVariable <String>] [-StatusCodeVariable <String>] [-UseBasicParsing] [-Uri] <Uri>
 [-WebSession <WebRequestSession>] [-SessionVariable <String>] [-AllowUnencryptedAuthentication]
 [-Authentication <WebAuthenticationType>] [-Credential <PSCredential>] [-UseDefaultCredentials]
 [-CertificateThumbprint <String>] [-Certificate <X509Certificate>] [-SkipCertificateCheck]
 [-SslProtocol <WebSslProtocol>] [-Token <SecureString>] [-UserAgent <String>] [-DisableKeepAlive]
 [-TimeoutSec <Int32>] [-Headers <IDictionary>] [-MaximumRedirection <Int32>]
 [-MaximumRetryCount <Int32>] [-RetryIntervalSec <Int32>] [-Proxy <Uri>]
 [-ProxyCredential <PSCredential>] [-ProxyUseDefaultCredentials] [-Body <Object>]
 [-Form <IDictionary>] [-ContentType <String>] [-TransferEncoding <String>] [-InFile <String>]
 [-OutFile <String>] [-PassThru] [-Resume] [-SkipHttpErrorCheck] [-PreserveAuthorizationOnRedirect]
 [-SkipHeaderValidation] [<CommonParameters>]
```

### <span data-ttu-id="5de27-107">Standardmethodnoproxy</span><span class="sxs-lookup"><span data-stu-id="5de27-107">StandardMethodNoProxy</span></span>

```
Invoke-RestMethod [-Method <WebRequestMethod>] [-FollowRelLink] [-MaximumFollowRelLink <Int32>]
 [-ResponseHeadersVariable <String>] [-StatusCodeVariable <String>] [-UseBasicParsing] [-Uri] <Uri>
 [-WebSession <WebRequestSession>] [-SessionVariable <String>] [-AllowUnencryptedAuthentication]
 [-Authentication <WebAuthenticationType>] [-Credential <PSCredential>] [-UseDefaultCredentials]
 [-CertificateThumbprint <String>] [-Certificate <X509Certificate>] [-SkipCertificateCheck]
 [-SslProtocol <WebSslProtocol>] [-Token <SecureString>] [-UserAgent <String>] [-DisableKeepAlive]
 [-TimeoutSec <Int32>] [-Headers <IDictionary>] [-MaximumRedirection <Int32>]
 [-MaximumRetryCount <Int32>] [-RetryIntervalSec <Int32>] -NoProxy [-Body <Object>]
 [-Form <IDictionary>] [-ContentType <String>] [-TransferEncoding <String>] [-InFile <String>]
 [-OutFile <String>] [-PassThru] [-Resume] [-SkipHttpErrorCheck] [-PreserveAuthorizationOnRedirect]
 [-SkipHeaderValidation] [<CommonParameters>]
```

### <span data-ttu-id="5de27-108">Custommethodnoproxy</span><span class="sxs-lookup"><span data-stu-id="5de27-108">CustomMethodNoProxy</span></span>

```
Invoke-RestMethod -CustomMethod <String> [-FollowRelLink] [-MaximumFollowRelLink <Int32>]
 [-ResponseHeadersVariable <String>] [-StatusCodeVariable <String>] [-UseBasicParsing] [-Uri] <Uri>
 [-WebSession <WebRequestSession>] [-SessionVariable <String>] [-AllowUnencryptedAuthentication]
 [-Authentication <WebAuthenticationType>] [-Credential <PSCredential>] [-UseDefaultCredentials]
 [-CertificateThumbprint <String>] [-Certificate <X509Certificate>] [-SkipCertificateCheck]
 [-SslProtocol <WebSslProtocol>] [-Token <SecureString>] [-UserAgent <String>] [-DisableKeepAlive]
 [-TimeoutSec <Int32>] [-Headers <IDictionary>] [-MaximumRedirection <Int32>]
 [-MaximumRetryCount <Int32>] [-RetryIntervalSec <Int32>] -NoProxy [-Body <Object>]
 [-Form <IDictionary>] [-ContentType <String>] [-TransferEncoding <String>] [-InFile <String>]
 [-OutFile <String>] [-PassThru] [-Resume] [-SkipHttpErrorCheck] [-PreserveAuthorizationOnRedirect]
 [-SkipHeaderValidation] [<CommonParameters>]
```

### <span data-ttu-id="5de27-109">Custommethod</span><span class="sxs-lookup"><span data-stu-id="5de27-109">CustomMethod</span></span>

```
Invoke-RestMethod -CustomMethod <String> [-FollowRelLink] [-MaximumFollowRelLink <Int32>]
 [-ResponseHeadersVariable <String>] [-StatusCodeVariable <String>] [-UseBasicParsing] [-Uri] <Uri>
 [-WebSession <WebRequestSession>] [-SessionVariable <String>] [-AllowUnencryptedAuthentication]
 [-Authentication <WebAuthenticationType>] [-Credential <PSCredential>] [-UseDefaultCredentials]
 [-CertificateThumbprint <String>] [-Certificate <X509Certificate>] [-SkipCertificateCheck]
 [-SslProtocol <WebSslProtocol>] [-Token <SecureString>] [-UserAgent <String>] [-DisableKeepAlive]
 [-TimeoutSec <Int32>] [-Headers <IDictionary>] [-MaximumRedirection <Int32>]
 [-MaximumRetryCount <Int32>] [-RetryIntervalSec <Int32>] [-Proxy <Uri>]
 [-ProxyCredential <PSCredential>] [-ProxyUseDefaultCredentials] [-Body <Object>]
 [-Form <IDictionary>] [-ContentType <String>] [-TransferEncoding <String>] [-InFile <String>]
 [-OutFile <String>] [-PassThru] [-Resume] [-SkipHttpErrorCheck] [-PreserveAuthorizationOnRedirect]
 [-SkipHeaderValidation] [<CommonParameters>]
```

## <span data-ttu-id="5de27-110">BESCHREIBUNG</span><span class="sxs-lookup"><span data-stu-id="5de27-110">Description</span></span>

<span data-ttu-id="5de27-111">Das `Invoke-RestMethod` -Cmdlet sendet HTTP-und HTTPS-Anforderungen an Rest (Representational State Transfer)-Webdienste, die Umfang strukturierte Daten zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="5de27-111">The `Invoke-RestMethod` cmdlet sends HTTP and HTTPS requests to Representational State Transfer (REST) web services that return richly structured data.</span></span>

<span data-ttu-id="5de27-112">PowerShell formatiert die Antwort auf der Grundlage des-Datentyps.</span><span class="sxs-lookup"><span data-stu-id="5de27-112">PowerShell formats the response based to the data type.</span></span> <span data-ttu-id="5de27-113">Bei einem RSS-oder Atom-Feed gibt PowerShell die Element-oder Eingabe-XML-Knoten zurück.</span><span class="sxs-lookup"><span data-stu-id="5de27-113">For an RSS or ATOM feed, PowerShell returns the Item or Entry XML nodes.</span></span> <span data-ttu-id="5de27-114">Bei JavaScript Object Notation (JSON) oder XML konvertiert oder deserialisiert PowerShell den Inhalt in Objekte.</span><span class="sxs-lookup"><span data-stu-id="5de27-114">For JavaScript Object Notation (JSON) or XML, PowerShell converts, or deserializes, the content into objects.</span></span>

<span data-ttu-id="5de27-115">Dieses Cmdlet wird in Windows PowerShell 3.0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="5de27-115">This cmdlet is introduced in Windows PowerShell 3.0.</span></span>

<span data-ttu-id="5de27-116">Ab PowerShell 7,0 `Invoke-RestMethod` unterstützt die durch Umgebungsvariablen definierte Proxykonfiguration.</span><span class="sxs-lookup"><span data-stu-id="5de27-116">Beginning in PowerShell 7.0, `Invoke-RestMethod` supports proxy configuration defined by environment variables.</span></span> <span data-ttu-id="5de27-117">Weitere Informationen finden Sie in diesem Artikel im Abschnitt mit [hinweisen](#notes) .</span><span class="sxs-lookup"><span data-stu-id="5de27-117">See the [Notes](#notes) section of this article.</span></span>

## <span data-ttu-id="5de27-118">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="5de27-118">EXAMPLES</span></span>

### <span data-ttu-id="5de27-119">Beispiel 1: Holen Sie sich den PowerShell-RSS-Feed</span><span class="sxs-lookup"><span data-stu-id="5de27-119">Example 1: Get the PowerShell RSS feed</span></span>

<span data-ttu-id="5de27-120">In diesem Beispiel wird das `Invoke-RestMethod` Cmdlet verwendet, um Informationen aus dem PowerShell-Blog-RSS-Feed zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="5de27-120">This example uses the `Invoke-RestMethod` cmdlet to get information from the PowerShell Blog RSS feed.</span></span> <span data-ttu-id="5de27-121">Der Befehl verwendet das `Format-Table` Cmdlet, um die Werte der **Titel** -und **pubDate** -Eigenschaften jedes Blogs in einer Tabelle anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="5de27-121">The command uses the `Format-Table` cmdlet to display the values of the **Title** and **pubDate** properties of each blog in a table.</span></span>

```powershell
Invoke-RestMethod -Uri https://blogs.msdn.microsoft.com/powershell/feed/ |
  Format-Table -Property Title, pubDate
```

```Output
Title                                                                pubDate
-----                                                                -------
Join the PowerShell 10th Anniversary Celebration!                    Tue, 08 Nov 2016 23:00:04 +0000
DSC Resource Kit November 2016 Release                               Thu, 03 Nov 2016 00:19:07 +0000
PSScriptAnalyzer Community Call - Oct 18, 2016                       Thu, 13 Oct 2016 17:52:35 +0000
New Home for In-Box DSC Resources                                    Sat, 08 Oct 2016 07:13:10 +0000
New Social Features on Gallery                                       Fri, 30 Sep 2016 23:04:34 +0000
PowerShellGet and PackageManagement in PowerShell Gallery and GitHub Thu, 29 Sep 2016 22:21:42 +0000
PowerShell Security at DerbyCon                                      Wed, 28 Sep 2016 01:13:19 +0000
DSC Resource Kit September Release                                   Thu, 22 Sep 2016 00:25:37 +0000
PowerShell DSC and implicit remoting broken in KB3176934             Tue, 23 Aug 2016 15:07:50 +0000
PowerShell on Linux and Open Source!                                 Thu, 18 Aug 2016 15:32:02 +0000
```

### <span data-ttu-id="5de27-122">Beispiel 2: Ausführen einer POST-Anforderung</span><span class="sxs-lookup"><span data-stu-id="5de27-122">Example 2: Run a POST request</span></span>

<span data-ttu-id="5de27-123">In diesem Beispiel führt ein Benutzer aus, `Invoke-RestMethod` um eine Post-Anforderung auf einer Intranetwebsite in der Organisation des Benutzers durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="5de27-123">In this example, a user runs `Invoke-RestMethod` to do a POST request on an intranet website in the user's organization.</span></span>

```powershell
$Cred = Get-Credential
$Url = "https://server.contoso.com:8089/services/search/jobs/export"
$Body = @{
    search = "search index=_internal | reverse | table index,host,source,sourcetype,_raw"
    output_mode = "csv"
    earliest_time = "-2d@d"
    latest_time = "-1d@d"
}
Invoke-RestMethod -Method 'Post' -Uri $url -Credential $Cred -Body $body -OutFile output.csv
```

<span data-ttu-id="5de27-124">Die Anmelde Informationen werden in aufgefordert und dann in gespeichert `$Cred` , und die URL, auf die zugegriffen wird, wird in definiert `$Url` .</span><span class="sxs-lookup"><span data-stu-id="5de27-124">The credentials are prompted for and then stored in `$Cred` and the URL that will be access is defined in `$Url`.</span></span>

<span data-ttu-id="5de27-125">Die `$Body` -Variable beschreibt die Suchkriterien, gibt CSV als Ausgabemodus an und gibt einen Zeitraum für zurückgegebene Daten an, der vor zwei Tagen beginnt und vor einem Tag endet.</span><span class="sxs-lookup"><span data-stu-id="5de27-125">The `$Body` variable describes the search criteria, specifies CSV as the output mode, and specifies a time period for returned data that starts two days ago and ends one day ago.</span></span> <span data-ttu-id="5de27-126">Die Body-Variable gibt Werte für Parameter an, die für die jeweilige Rest-API gelten, mit der `Invoke-RestMethod` kommuniziert.</span><span class="sxs-lookup"><span data-stu-id="5de27-126">The body variable specifies values for parameters that apply to the particular REST API with which `Invoke-RestMethod` is communicating.</span></span>

<span data-ttu-id="5de27-127">Der `Invoke-RestMethod` Befehl wird mit allen Variablen ausgeführt, wobei ein Pfad und ein Dateiname für die resultierende CSV-Ausgabedatei angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="5de27-127">The `Invoke-RestMethod` command is run with all variables in place, specifying a path and file name for the resulting CSV output file.</span></span>

### <span data-ttu-id="5de27-128">Beispiel 3: Folgen von Beziehungslinks</span><span class="sxs-lookup"><span data-stu-id="5de27-128">Example 3: Follow relation links</span></span>

<span data-ttu-id="5de27-129">Einige Rest-APIs unterstützen die Paginierung über Beziehungs Links pro [RFC5988](https://tools.ietf.org/html/rfc5988#page-6).</span><span class="sxs-lookup"><span data-stu-id="5de27-129">Some REST APIs support pagination via Relation Links per [RFC5988](https://tools.ietf.org/html/rfc5988#page-6).</span></span> <span data-ttu-id="5de27-130">Anstatt den Header zu übermitteln, um die URL für die nächste Seite zu erhalten, können Sie das Cmdlet hierfür verwenden.</span><span class="sxs-lookup"><span data-stu-id="5de27-130">Instead of parsing the header to get the URL for the next page, you can have the cmdlet do this for you.</span></span> <span data-ttu-id="5de27-131">In diesem Beispiel werden die ersten beiden Seiten von Problemen aus dem PowerShell-GitHub-Repository zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="5de27-131">This example returns the first two pages of issues from the PowerShell GitHub repository.</span></span>

```powershell
$url = 'https://api.github.com/repos/powershell/powershell/issues'
Invoke-RestMethod $url -FollowRelLink -MaximumFollowRelLink 2
```

### <span data-ttu-id="5de27-132">Beispiel 4: vereinfachte Multipart/Form-Übermittlung von Daten</span><span class="sxs-lookup"><span data-stu-id="5de27-132">Example 4: Simplified Multipart/Form-Data Submission</span></span>

<span data-ttu-id="5de27-133">Einige APIs erfordern `multipart/form-data` Übermittlungen zum Hochladen von Dateien und gemischtem Inhalt.</span><span class="sxs-lookup"><span data-stu-id="5de27-133">Some APIs require `multipart/form-data` submissions to upload files and mixed content.</span></span> <span data-ttu-id="5de27-134">In diesem Beispiel wird veranschaulicht, wie das Profil eines Benutzers aktualisiert wird.</span><span class="sxs-lookup"><span data-stu-id="5de27-134">This example demonstrates how to update a user's profile.</span></span>

```powershell
$Uri = 'https://api.contoso.com/v2/profile'
$Form = @{
    firstName  = 'John'
    lastName   = 'Doe'
    email      = 'john.doe@contoso.com'
    avatar     = Get-Item -Path 'c:\Pictures\jdoe.png'
    birthday   = '1980-10-15'
    hobbies    = 'Hiking','Fishing','Jogging'
}
$Result = Invoke-RestMethod -Uri $Uri -Method Post -Form $Form
```

<span data-ttu-id="5de27-135">Das Profil Formular erfordert die folgenden Felder: `firstName` , `lastName` , `email` , `avatar` , `birthday` und `hobbies` .</span><span class="sxs-lookup"><span data-stu-id="5de27-135">The profile form requires these fields: `firstName`, `lastName`, `email`, `avatar`, `birthday`, and `hobbies`.</span></span> <span data-ttu-id="5de27-136">Die API erwartet ein Bild, damit das Benutzerprofil im Feld bereitgestellt wird `avatar` .</span><span class="sxs-lookup"><span data-stu-id="5de27-136">The API is expecting an image for the user profile pic to be supplied in the `avatar` field.</span></span> <span data-ttu-id="5de27-137">Die API akzeptiert auch mehrere `hobbies` Einträge, die in derselben Form übermittelt werden.</span><span class="sxs-lookup"><span data-stu-id="5de27-137">The API will also accept multiple `hobbies` entries to be submitted in the same form.</span></span>

<span data-ttu-id="5de27-138">Beim Erstellen der `$Form` Hash Tabelle werden die Schlüsselnamen als Formular Feldnamen verwendet.</span><span class="sxs-lookup"><span data-stu-id="5de27-138">When creating the `$Form` HashTable, the key names are used as form field names.</span></span> <span data-ttu-id="5de27-139">Standardmäßig werden die Werte der Hash Tabelle in Zeichen folgen konvertiert.</span><span class="sxs-lookup"><span data-stu-id="5de27-139">By default, the values of the HashTable will be converted to strings.</span></span> <span data-ttu-id="5de27-140">Wenn ein `System.IO.FileInfo` Wert vorhanden ist, wird der Inhalt der Datei übermittelt.</span><span class="sxs-lookup"><span data-stu-id="5de27-140">If a `System.IO.FileInfo` value is present, the file contents will be submitted.</span></span> <span data-ttu-id="5de27-141">Wenn eine Auflistung, z. b. Arrays oder Listen, vorhanden ist, wird das Formularfeld mehrmals übermittelt.</span><span class="sxs-lookup"><span data-stu-id="5de27-141">If a collection such as arrays or lists are present, the form field will be submitted multiple times.</span></span>

<span data-ttu-id="5de27-142">Wenn Sie `Get-Item` für den `avatar` Schlüssel verwenden, `FileInfo` wird das-Objekt als-Wert festgelegt.</span><span class="sxs-lookup"><span data-stu-id="5de27-142">By using `Get-Item` on the `avatar` key, the `FileInfo` object will be set as the value.</span></span> <span data-ttu-id="5de27-143">Das Ergebnis ist, dass die Bilddaten für über `jdoe.png` mittelt werden.</span><span class="sxs-lookup"><span data-stu-id="5de27-143">The result is that the image data for `jdoe.png` will be submitted.</span></span>

<span data-ttu-id="5de27-144">Wenn eine Liste für den Schlüssel bereitgestellt wird `hobbies` , ist das `hobbies` Feld in den Einsendungen einmal für jedes Listenelement enthalten.</span><span class="sxs-lookup"><span data-stu-id="5de27-144">By supplying a list to the `hobbies` key, the `hobbies` field will be present in the submissions once for each list item.</span></span>

### <span data-ttu-id="5de27-145">Beispiel 5: übergeben mehrerer Header</span><span class="sxs-lookup"><span data-stu-id="5de27-145">Example 5: Pass multiple headers</span></span>

<span data-ttu-id="5de27-146">APIs erfordern häufig übergebenen Header für die Authentifizierung oder Validierung.</span><span class="sxs-lookup"><span data-stu-id="5de27-146">APIs often require passed headers for authentication or validation.</span></span> <span data-ttu-id="5de27-147">In diesem Beispiel wird veranschaulicht, wie mehrere Header von einem `hash-table` an eine Rest-API übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="5de27-147">This example demonstrates, how to pass multiple headers from a `hash-table` to a REST API.</span></span>

```powershell
$headers = @{
    'userId' = 'UserIDValue'
    'token' = 'TokenValue'
}
Invoke-RestMethod -Uri $uri -Method Post -Headers $headers -Body $body
```

## <span data-ttu-id="5de27-148">Parameter</span><span class="sxs-lookup"><span data-stu-id="5de27-148">Parameters</span></span>

### <span data-ttu-id="5de27-149">-"-Zugewunverschlüsseltedauthentication"</span><span class="sxs-lookup"><span data-stu-id="5de27-149">-AllowUnencryptedAuthentication</span></span>

<span data-ttu-id="5de27-150">Ermöglicht das Senden von Anmelde Informationen und Geheimnissen über unverschlüsselte Verbindungen.</span><span class="sxs-lookup"><span data-stu-id="5de27-150">Allows sending of credentials and secrets over unencrypted connections.</span></span> <span data-ttu-id="5de27-151">Standardmäßig führt die Angabe von Anmelde **Informationen oder einer** beliebigen **Authentifizierungs** Option mit einem **URI** , der nicht mit beginnt, `https://` zu einem Fehler, und die Anforderung wird abgebrochen, um zu verhindern, dass Geheimnisse versehentlich im Klartext über unverschlüsselte Verbindungen kommuniziert werden.</span><span class="sxs-lookup"><span data-stu-id="5de27-151">By default, supplying **Credential** or any **Authentication** option with a **Uri** that does not begin with `https://` will result in an error and the request will abort to prevent unintentionally communicating secrets in plain text over unencrypted connections.</span></span> <span data-ttu-id="5de27-152">Um dieses Verhalten auf eigene Gefahr zu überschreiben, geben Sie den Parameter " **zugswunverschlüsseltedauthentication** " an.</span><span class="sxs-lookup"><span data-stu-id="5de27-152">To override this behavior at your own risk, supply the **AllowUnencryptedAuthentication** parameter.</span></span>

> [!WARNING]
> <span data-ttu-id="5de27-153">Die Verwendung dieses Parameters ist nicht sicher und wird nicht empfohlen.</span><span class="sxs-lookup"><span data-stu-id="5de27-153">Using this parameter is not secure and is not recommended.</span></span> <span data-ttu-id="5de27-154">Sie wird nur aus Gründen der Kompatibilität mit Legacy Systemen bereitgestellt, die keine verschlüsselten Verbindungen bereitstellen können.</span><span class="sxs-lookup"><span data-stu-id="5de27-154">It is provided only for compatibility with legacy systems that cannot provide encrypted connections.</span></span> <span data-ttu-id="5de27-155">Verwenden Sie auf eigene Gefahr.</span><span class="sxs-lookup"><span data-stu-id="5de27-155">Use at your own risk.</span></span>

<span data-ttu-id="5de27-156">Diese Funktion wurde in PowerShell 6.0.0 hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="5de27-156">This feature was added in PowerShell 6.0.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5de27-157">-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="5de27-157">-Authentication</span></span>

<span data-ttu-id="5de27-158">Gibt den für die Anforderung zu verwendenden expliziten Authentifizierungstyp an.</span><span class="sxs-lookup"><span data-stu-id="5de27-158">Specifies the explicit authentication type to use for the request.</span></span> <span data-ttu-id="5de27-159">Der Standardwert ist **None** (Kein).</span><span class="sxs-lookup"><span data-stu-id="5de27-159">The default is **None**.</span></span>
<span data-ttu-id="5de27-160">Die **Authentifizierung** kann nicht mit **usedefault-Anmelde** Informationen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="5de27-160">**Authentication** can't be used with **UseDefaultCredentials**.</span></span>

<span data-ttu-id="5de27-161">Verfügbare Authentifizierungs Optionen:</span><span class="sxs-lookup"><span data-stu-id="5de27-161">Available Authentication Options:</span></span>

- <span data-ttu-id="5de27-162">**None**: Dies ist die Standardoption, wenn keine **Authentifizierung** bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="5de27-162">**None**: This is the default option when **Authentication** is not supplied.</span></span> <span data-ttu-id="5de27-163">Es wird keine explizite Authentifizierung verwendet.</span><span class="sxs-lookup"><span data-stu-id="5de27-163">No explicit authentication will be used.</span></span>
- <span data-ttu-id="5de27-164">**Basic**: erfordert **Credential**.</span><span class="sxs-lookup"><span data-stu-id="5de27-164">**Basic**: Requires **Credential**.</span></span> <span data-ttu-id="5de27-165">Die Anmelde Informationen werden verwendet, um einen RFC 7617-Standard Authentifizierungs `Authorization: Basic` Header im Format von zu senden `base64(user:password)` .</span><span class="sxs-lookup"><span data-stu-id="5de27-165">The credentials will be used to send an RFC 7617 Basic Authentication `Authorization: Basic` header in the format of `base64(user:password)`.</span></span>
- <span data-ttu-id="5de27-166">Bearername **: erfordert** **Token**.</span><span class="sxs-lookup"><span data-stu-id="5de27-166">**Bearer**: Requires **Token**.</span></span> <span data-ttu-id="5de27-167">Sendet und RFC 6750- `Authorization: Bearer` Header mit dem angegebenen Token.</span><span class="sxs-lookup"><span data-stu-id="5de27-167">Will send and RFC 6750 `Authorization: Bearer` header with the supplied token.</span></span> <span data-ttu-id="5de27-168">Dies ist ein Alias für **OAuth.**</span><span class="sxs-lookup"><span data-stu-id="5de27-168">This is an alias for **OAuth**</span></span>
- <span data-ttu-id="5de27-169">**OAuth**: erfordert **Token**.</span><span class="sxs-lookup"><span data-stu-id="5de27-169">**OAuth**: Requires **Token**.</span></span> <span data-ttu-id="5de27-170">Sendet einen RFC 6750- `Authorization: Bearer` Header mit dem angegebenen Token.</span><span class="sxs-lookup"><span data-stu-id="5de27-170">Will send an RFC 6750 `Authorization: Bearer` header with the supplied token.</span></span> <span data-ttu-id="5de27-171">Dies ist ein **Alias für** Bearer.</span><span class="sxs-lookup"><span data-stu-id="5de27-171">This is an alias for **Bearer**</span></span>

<span data-ttu-id="5de27-172">Durch die Bereitstellung der **Authentifizierung** werden alle `Authorization` Header überschrieben, die an **Header gesendet** oder in **websession** eingeschlossen werden</span><span class="sxs-lookup"><span data-stu-id="5de27-172">Supplying **Authentication** will override any `Authorization` headers supplied to **Headers** or included in **WebSession**.</span></span>

<span data-ttu-id="5de27-173">Diese Funktion wurde in PowerShell 6.0.0 hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="5de27-173">This feature was added in PowerShell 6.0.0.</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.WebAuthenticationType
Parameter Sets: (All)
Aliases:
Accepted values: None, Basic, Bearer, OAuth

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5de27-174">-Text</span><span class="sxs-lookup"><span data-stu-id="5de27-174">-Body</span></span>

<span data-ttu-id="5de27-175">Gibt den Anforderungstext an.</span><span class="sxs-lookup"><span data-stu-id="5de27-175">Specifies the body of the request.</span></span> <span data-ttu-id="5de27-176">Der Text entspricht dem Inhalt der Anforderung, der auf die Header folgt.</span><span class="sxs-lookup"><span data-stu-id="5de27-176">The body is the content of the request that follows the headers.</span></span>
<span data-ttu-id="5de27-177">Sie können einen Textwert auch über die Pipeline an senden `Invoke-RestMethod` .</span><span class="sxs-lookup"><span data-stu-id="5de27-177">You can also pipe a body value to `Invoke-RestMethod`.</span></span>

<span data-ttu-id="5de27-178">Der **Body**-Parameter kann verwendet werden, um eine Liste von Abfrageparametern oder den Inhalt der Antwort anzugeben.</span><span class="sxs-lookup"><span data-stu-id="5de27-178">The **Body** parameter can be used to specify a list of query parameters or specify the content of the response.</span></span>

<span data-ttu-id="5de27-179">Wenn die Eingabe eine GET-Anforderung und der Text `IDictionary` (in der Regel eine Hash Tabelle) ist, wird der Text dem Uniform Resource Identifier (URI) als Abfrage Parameter hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="5de27-179">When the input is a GET request, and the body is an `IDictionary` (typically, a hash table), the body is added to the Uniform Resource Identifier (URI) as query parameters.</span></span> <span data-ttu-id="5de27-180">Für andere Anforderungstypen (z. B. POST) wird der Text als Wert des Anforderungstexts im Format „Standardname=Wertformat“ festgelegt.</span><span class="sxs-lookup"><span data-stu-id="5de27-180">For other request types (such as POST), the body is set as the value of the request body in the standard name=value format.</span></span>

<span data-ttu-id="5de27-181">Wenn der Text ein Formular oder die Ausgabe eines anderen `Invoke-WebRequest` Aufrufes ist, legt PowerShell den Anforderungs Inhalt auf die Formularfelder fest.</span><span class="sxs-lookup"><span data-stu-id="5de27-181">When the body is a form, or it's the output of another `Invoke-WebRequest` call, PowerShell sets the request content to the form fields.</span></span>

<span data-ttu-id="5de27-182">Der **Body** -Parameter kann auch ein **System .net. http. multipartformdatacontent** -Objekt akzeptieren.</span><span class="sxs-lookup"><span data-stu-id="5de27-182">The **Body** parameter may also accept a **System.Net.Http.MultipartFormDataContent** object.</span></span> <span data-ttu-id="5de27-183">Dies erleichtert `multipart/form-data` Anforderungen.</span><span class="sxs-lookup"><span data-stu-id="5de27-183">This will facilitate `multipart/form-data` requests.</span></span> <span data-ttu-id="5de27-184">Wenn für **Body** ein **multipartformdatacontent** -Objekt bereitgestellt wird, werden alle Inhalts bezogenen Header, die für den **ContentType**-, **Header**-oder **websession** -Parameter bereitgestellt werden, von den Inhalts Headern des-Objekts überschrieben `MultipartFormDataContent` .</span><span class="sxs-lookup"><span data-stu-id="5de27-184">When a **MultipartFormDataContent** object is supplied for **Body**, any content related headers supplied to the **ContentType**, **Headers**, or **WebSession** parameters will be overridden by the content headers of the `MultipartFormDataContent` object.</span></span> <span data-ttu-id="5de27-185">Diese Funktion wurde in PowerShell 6.0.0 hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="5de27-185">This feature was added in PowerShell 6.0.0.</span></span>

```yaml
Type: System.Object
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### <span data-ttu-id="5de27-186">-Zertifikat</span><span class="sxs-lookup"><span data-stu-id="5de27-186">-Certificate</span></span>

<span data-ttu-id="5de27-187">Gibt das Clientzertifikat an, das für eine sichere Webanforderung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="5de27-187">Specifies the client certificate that is used for a secure web request.</span></span> <span data-ttu-id="5de27-188">Geben Sie eine Variable ein, die ein Zertifikat, einen Befehl oder einen Ausdruck enthält, durch die das Zertifikat abgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="5de27-188">Enter a variable that contains a certificate or a command or expression that gets the certificate.</span></span>

<span data-ttu-id="5de27-189">Um ein Zertifikat zu suchen, verwenden Sie `Get-PfxCertificate` oder das- `Get-ChildItem` Cmdlet im Zertifikat `Cert:` Laufwerk ().</span><span class="sxs-lookup"><span data-stu-id="5de27-189">To find a certificate, use `Get-PfxCertificate` or use the `Get-ChildItem` cmdlet in the Certificate (`Cert:`) drive.</span></span> <span data-ttu-id="5de27-190">Wenn das Zertifikat ungültig ist oder nicht über ausreichende Berechtigungen verfügt, schlägt der Befehl fehl.</span><span class="sxs-lookup"><span data-stu-id="5de27-190">If the certificate isn't valid or doesn't have sufficient authority, the command fails.</span></span>

```yaml
Type: System.Security.Cryptography.X509Certificates.X509Certificate
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5de27-191">-Certifiupethumschlag-Print</span><span class="sxs-lookup"><span data-stu-id="5de27-191">-CertificateThumbprint</span></span>

<span data-ttu-id="5de27-192">Gibt das digitale Zertifikat für öffentliche Schlüssel (X509) eines Benutzerkontos an, das über die Berechtigung zum Senden der Anforderung verfügt.</span><span class="sxs-lookup"><span data-stu-id="5de27-192">Specifies the digital public key certificate (X509) of a user account that has permission to send the request.</span></span> <span data-ttu-id="5de27-193">Geben Sie den Zertifikatfingerabdruck des Zertifikats ein.</span><span class="sxs-lookup"><span data-stu-id="5de27-193">Enter the certificate thumbprint of the certificate.</span></span>

<span data-ttu-id="5de27-194">Zertifikate werden bei der clientzertifikatbasierten Authentifizierung verwendet.</span><span class="sxs-lookup"><span data-stu-id="5de27-194">Certificates are used in client certificate-based authentication.</span></span> <span data-ttu-id="5de27-195">Sie können nur lokalen Benutzerkonten zugeordnet werden und funktionieren nicht mit Domänenkonten.</span><span class="sxs-lookup"><span data-stu-id="5de27-195">They can be mapped only to local user accounts; they do not work with domain accounts.</span></span>

<span data-ttu-id="5de27-196">Um einen Zertifikat Fingerabdruck abzurufen, verwenden Sie den- `Get-Item` Befehl oder den- `Get-ChildItem` Befehl im PowerShell- `Cert:` Laufwerk.</span><span class="sxs-lookup"><span data-stu-id="5de27-196">To get a certificate thumbprint, use the `Get-Item` or `Get-ChildItem` command in the PowerShell `Cert:` drive.</span></span>

> [!NOTE]
> <span data-ttu-id="5de27-197">Diese Funktion wird zurzeit nur auf Windows-Betriebssystemplattformen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="5de27-197">This feature is currently only supported on Windows OS platforms.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5de27-198">-ContentType</span><span class="sxs-lookup"><span data-stu-id="5de27-198">-ContentType</span></span>

<span data-ttu-id="5de27-199">Gibt den Inhaltstyp der Webanforderung an.</span><span class="sxs-lookup"><span data-stu-id="5de27-199">Specifies the content type of the web request.</span></span>

<span data-ttu-id="5de27-200">Wenn dieser Parameter ausgelassen wird und die Anforderungs Methode Post ist, `Invoke-RestMethod` legt den Inhaltstyp auf fest `application/x-www-form-urlencoded` .</span><span class="sxs-lookup"><span data-stu-id="5de27-200">If this parameter is omitted and the request method is POST, `Invoke-RestMethod` sets the content type to `application/x-www-form-urlencoded`.</span></span> <span data-ttu-id="5de27-201">Andernfalls wird der Inhaltstyp nicht im-Befehl angegeben.</span><span class="sxs-lookup"><span data-stu-id="5de27-201">Otherwise, the content type isn't specified in the call.</span></span>

<span data-ttu-id="5de27-202">" **ContentType** " wird überschrieben, wenn ein- `MultipartFormDataContent` Objekt für den **Textkörper** bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="5de27-202">**ContentType** will be overridden when a `MultipartFormDataContent` object is supplied for **Body**.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5de27-203">-Credential</span><span class="sxs-lookup"><span data-stu-id="5de27-203">-Credential</span></span>

<span data-ttu-id="5de27-204">Gibt ein Benutzerkonto an, das über die Berechtigung zum Senden der Anforderung verfügt.</span><span class="sxs-lookup"><span data-stu-id="5de27-204">Specifies a user account that has permission to send the request.</span></span> <span data-ttu-id="5de27-205">Der Standardwert ist der aktuelle Benutzer.</span><span class="sxs-lookup"><span data-stu-id="5de27-205">The default is the current user.</span></span>

<span data-ttu-id="5de27-206">Geben Sie einen Benutzernamen ein, z. b. **USER01** oder **Domain01\User01**, oder geben Sie ein **PSCredential** -Objekt ein, das vom `Get-Credential` Cmdlet generiert wurde.</span><span class="sxs-lookup"><span data-stu-id="5de27-206">Type a user name, such as **User01** or **Domain01\User01**, or enter a **PSCredential** object generated by the `Get-Credential` cmdlet.</span></span>

<span data-ttu-id="5de27-207">Anmelde **Informationen können allein** oder in Verbindung mit bestimmten **Authentifizierungs** Parameter Optionen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="5de27-207">**Credential** can be used alone or in conjunction with certain **Authentication** parameter options.</span></span> <span data-ttu-id="5de27-208">Bei Verwendung allein werden Anmelde Informationen nur für den Remote Server bereitgestellt, wenn vom Remote Server eine Anforderung zur Authentifizierungsanforderung gesendet wird.</span><span class="sxs-lookup"><span data-stu-id="5de27-208">When used alone, it will only supply credentials to the remote server if the remote server sends an authentication challenge request.</span></span> <span data-ttu-id="5de27-209">Bei Verwendung mit **Authentifizierungs** Optionen werden die Anmelde Informationen explizit gesendet.</span><span class="sxs-lookup"><span data-stu-id="5de27-209">When used with **Authentication** options, the credentials will be explicitly sent.</span></span>

<span data-ttu-id="5de27-210">Anmelde Informationen werden in einem [PSCredential](/dotnet/api/system.management.automation.pscredential) -Objekt gespeichert, und das Kennwort wird als [SecureString](/dotnet/api/system.security.securestring)gespeichert.</span><span class="sxs-lookup"><span data-stu-id="5de27-210">Credentials are stored in a [PSCredential](/dotnet/api/system.management.automation.pscredential) object and the password is stored as a [SecureString](/dotnet/api/system.security.securestring).</span></span>

> [!NOTE]
> <span data-ttu-id="5de27-211">Weitere Informationen zum Schutz von **SecureString** -Daten finden Sie unter [wie sicher ist SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span><span class="sxs-lookup"><span data-stu-id="5de27-211">For more information about **SecureString** data protection, see [How secure is SecureString?](/dotnet/api/system.security.securestring#how-secure-is-securestring).</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: Current user
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5de27-212">-Custommethod</span><span class="sxs-lookup"><span data-stu-id="5de27-212">-CustomMethod</span></span>

<span data-ttu-id="5de27-213">Gibt die für die Webanforderung verwendete benutzerdefinierte Methode an.</span><span class="sxs-lookup"><span data-stu-id="5de27-213">Specifies custom method used for the web request.</span></span> <span data-ttu-id="5de27-214">Diese Option kann mit der Anforderungs Methode verwendet werden, die für den Endpunkt erforderlich ist, ist für die **Methode** nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="5de27-214">This can be used with the Request Method required by the endpoint is not an available option on the **Method**.</span></span> <span data-ttu-id="5de27-215">Die **Methode** und die **custommethod** können nicht gleichzeitig verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="5de27-215">**Method** and **CustomMethod** cannot be used together.</span></span>

<span data-ttu-id="5de27-216">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="5de27-216">Example:</span></span>

`Invoke-RestMethod -uri 'https://api.contoso.com/widget/' -CustomMethod 'TEST'`

<span data-ttu-id="5de27-217">Dadurch wird eine `TEST` http-Anforderung an die API durchführt.</span><span class="sxs-lookup"><span data-stu-id="5de27-217">This makes a `TEST` HTTP request to the API.</span></span>

<span data-ttu-id="5de27-218">Diese Funktion wurde in PowerShell 6.0.0 hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="5de27-218">This feature was added in PowerShell 6.0.0.</span></span>

```yaml
Type: System.String
Parameter Sets: CustomMethodNoProxy, CustomMethod
Aliases: CM

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5de27-219">-Disablekeepalive</span><span class="sxs-lookup"><span data-stu-id="5de27-219">-DisableKeepAlive</span></span>

<span data-ttu-id="5de27-220">Gibt an, dass mit dem Cmdlet der **KeepAlive** -Wert im HTTP-Header auf false festgelegt wird.</span><span class="sxs-lookup"><span data-stu-id="5de27-220">Indicates that the cmdlet sets the **KeepAlive** value in the HTTP header to False.</span></span> <span data-ttu-id="5de27-221">Der Standardwert von **KeepAlive** ist „True“.</span><span class="sxs-lookup"><span data-stu-id="5de27-221">By default, **KeepAlive** is True.</span></span> <span data-ttu-id="5de27-222">**KeepAlive** richtet eine persistente Verbindung mit dem Server ein, um nachfolgende Anforderungen zu erleichtern.</span><span class="sxs-lookup"><span data-stu-id="5de27-222">**KeepAlive** establishes a persistent connection to the server to facilitate subsequent requests.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5de27-223">-Followrellink</span><span class="sxs-lookup"><span data-stu-id="5de27-223">-FollowRelLink</span></span>

<span data-ttu-id="5de27-224">Gibt an, dass das Cmdlet Beziehungslinks befolgen soll.</span><span class="sxs-lookup"><span data-stu-id="5de27-224">Indicates the cmdlet should follow relation links.</span></span>

<span data-ttu-id="5de27-225">Einige Rest-APIs unterstützen die Paginierung über Beziehungs Links pro [RFC5988](https://tools.ietf.org/html/rfc5988#page-6).</span><span class="sxs-lookup"><span data-stu-id="5de27-225">Some REST APIs support pagination via Relation Links per [RFC5988](https://tools.ietf.org/html/rfc5988#page-6).</span></span> <span data-ttu-id="5de27-226">Anstatt den Header zu übermitteln, um die URL für die nächste Seite zu erhalten, können Sie das Cmdlet hierfür verwenden.</span><span class="sxs-lookup"><span data-stu-id="5de27-226">Instead of parsing the header to get the URL for the next page, you can have the cmdlet do this for you.</span></span> <span data-ttu-id="5de27-227">Um festzulegen, wie oft Beziehungslinks befolgt werden sollen, verwenden Sie den Parameter **maximumfollowrellink** .</span><span class="sxs-lookup"><span data-stu-id="5de27-227">To set how many times to follow relation links, use the **MaximumFollowRelLink** parameter.</span></span>

<span data-ttu-id="5de27-228">Wenn Sie diesen Schalter verwenden, gibt das Cmdlet eine Auflistung von Ergebnisseiten zurück.</span><span class="sxs-lookup"><span data-stu-id="5de27-228">When using this switch, the cmdlet returns a collection of pages of results.</span></span> <span data-ttu-id="5de27-229">Jede Ergebnisseite kann mehrere Ergebnis Elemente enthalten.</span><span class="sxs-lookup"><span data-stu-id="5de27-229">Each page of results may contain multiple result items.</span></span>

<span data-ttu-id="5de27-230">Diese Funktion wurde in PowerShell 6.0.0 hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="5de27-230">This feature was added in PowerShell 6.0.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases: FL

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5de27-231">-Formular</span><span class="sxs-lookup"><span data-stu-id="5de27-231">-Form</span></span>

<span data-ttu-id="5de27-232">Konvertiert ein Wörterbuch in eine `multipart/form-data` Übermittlung.</span><span class="sxs-lookup"><span data-stu-id="5de27-232">Converts a dictionary to a `multipart/form-data` submission.</span></span> <span data-ttu-id="5de27-233">Das **Formular** darf nicht mit dem **Textkörper** verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="5de27-233">**Form** may not be used with **Body**.</span></span>
<span data-ttu-id="5de27-234">, Wenn **ContentType** ignoriert wird.</span><span class="sxs-lookup"><span data-stu-id="5de27-234">If **ContentType** will be ignored.</span></span>

<span data-ttu-id="5de27-235">Die Schlüssel des Wörterbuchs werden als Formular Feldnamen verwendet.</span><span class="sxs-lookup"><span data-stu-id="5de27-235">The keys of the dictionary will be used as the form field names.</span></span> <span data-ttu-id="5de27-236">Standardmäßig werden Formular Werte in Zeichen folgen Werte konvertiert.</span><span class="sxs-lookup"><span data-stu-id="5de27-236">By default, form values will be converted to string values.</span></span>

<span data-ttu-id="5de27-237">Wenn der Wert ein **System. IO. FileInfo** -Objekt ist, wird der Inhalt der Binärdatei übermittelt.</span><span class="sxs-lookup"><span data-stu-id="5de27-237">If the value is a **System.IO.FileInfo** object, then the binary file contents will be submitted.</span></span>
<span data-ttu-id="5de27-238">Der Name der Datei wird als übermittelt `filename` .</span><span class="sxs-lookup"><span data-stu-id="5de27-238">The name of the file will be submitted as the `filename`.</span></span> <span data-ttu-id="5de27-239">Der MIME wird als festgelegt `application/octet-stream` .</span><span class="sxs-lookup"><span data-stu-id="5de27-239">The MIME will be set as `application/octet-stream`.</span></span> <span data-ttu-id="5de27-240">`Get-Item` kann verwendet werden, um die Bereitstellung des **System. IO. FileInfo** -Objekts zu vereinfachen.</span><span class="sxs-lookup"><span data-stu-id="5de27-240">`Get-Item` can be used to simplify supplying the **System.IO.FileInfo** object.</span></span>

```powershell
$Form = @{
    resume = Get-Item 'c:\Users\jdoe\Documents\John Doe.pdf'
}
```

<span data-ttu-id="5de27-241">Wenn es sich bei dem Wert um einen Sammlungstyp handelt, z. b. ein Array oder eine Liste, wird das Feld für mehrmals übermittelt.</span><span class="sxs-lookup"><span data-stu-id="5de27-241">If the value is a collection type, such as an Array or List, the for field will be submitted multiple times.</span></span> <span data-ttu-id="5de27-242">Die Werte der Liste werden standardmäßig als Zeichen folgen behandelt.</span><span class="sxs-lookup"><span data-stu-id="5de27-242">The values of the list will be treated as strings by default.</span></span> <span data-ttu-id="5de27-243">Wenn der Wert ein **System. IO. FileInfo** -Objekt ist, wird der Inhalt der Binärdatei übermittelt.</span><span class="sxs-lookup"><span data-stu-id="5de27-243">If the value is a **System.IO.FileInfo** object, then the binary file contents will be submitted.</span></span> <span data-ttu-id="5de27-244">Unterstützte Auflistungen werden nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="5de27-244">Nested collections aren't supported.</span></span>

```powershell
$Form = @{
    tags     = 'Vacation', 'Italy', '2017'
    pictures = Get-ChildItem 'c:\Users\jdoe\Pictures\2017-Italy\'
}
```

<span data-ttu-id="5de27-245">Im obigen Beispiel `tags` wird das Feld dreimal in der Form bereitgestellt, einmal für jede von `Vacation` , `Italy` und `2017` .</span><span class="sxs-lookup"><span data-stu-id="5de27-245">In the above example, the `tags` field will be supplied three times in the form, once for each of `Vacation`, `Italy`, and `2017`.</span></span> <span data-ttu-id="5de27-246">Das `pictures` Feld wird auch einmal für jede Datei im Ordner übermittelt `2017-Italy` .</span><span class="sxs-lookup"><span data-stu-id="5de27-246">The `pictures` field will also be submitted once for each file in the `2017-Italy` folder.</span></span> <span data-ttu-id="5de27-247">Der binäre Inhalt der Dateien in diesem Ordner wird als-Werte übermittelt.</span><span class="sxs-lookup"><span data-stu-id="5de27-247">The binary contents of the files in that folder will be submitted as the values.</span></span>

<span data-ttu-id="5de27-248">Diese Funktion wurde in PowerShell 6.1.0 hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="5de27-248">This feature was added in PowerShell 6.1.0.</span></span>

```yaml
Type: System.Collections.IDictionary
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5de27-249">-Header</span><span class="sxs-lookup"><span data-stu-id="5de27-249">-Headers</span></span>

<span data-ttu-id="5de27-250">Gibt die Header der Webanforderung an.</span><span class="sxs-lookup"><span data-stu-id="5de27-250">Specifies the headers of the web request.</span></span> <span data-ttu-id="5de27-251">Geben Sie eine Hashtabelle oder ein Wörterbuch ein.</span><span class="sxs-lookup"><span data-stu-id="5de27-251">Enter a hash table or dictionary.</span></span>

<span data-ttu-id="5de27-252">Verwenden Sie zum Festlegen der UserAgent-Header den **UserAgent**-Parameter.</span><span class="sxs-lookup"><span data-stu-id="5de27-252">To set UserAgent headers, use the **UserAgent** parameter.</span></span> <span data-ttu-id="5de27-253">Sie können diesen Parameter nicht verwenden, um- `User-Agent` oder-Cookie-Header anzugeben.</span><span class="sxs-lookup"><span data-stu-id="5de27-253">You cannot use this parameter to specify `User-Agent` or cookie headers.</span></span>

<span data-ttu-id="5de27-254">Inhalts bezogene Header, z. b., werden `Content-Type` überschrieben, wenn ein- `MultipartFormDataContent` Objekt für den **Textkörper** bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="5de27-254">Content related headers, such as `Content-Type` will be overridden when a `MultipartFormDataContent` object is supplied for **Body**.</span></span>

```yaml
Type: System.Collections.IDictionary
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5de27-255">-Eingabedatei</span><span class="sxs-lookup"><span data-stu-id="5de27-255">-InFile</span></span>

<span data-ttu-id="5de27-256">Ruft den Inhalt der Webanforderung aus einer Datei ab.</span><span class="sxs-lookup"><span data-stu-id="5de27-256">Gets the content of the web request from a file.</span></span>

<span data-ttu-id="5de27-257">Geben Sie einen Pfad- und Dateinamen ein.</span><span class="sxs-lookup"><span data-stu-id="5de27-257">Enter a path and file name.</span></span> <span data-ttu-id="5de27-258">Wenn Sie den Pfad weglassen, wird der aktuelle Speicherort als Standard verwendet.</span><span class="sxs-lookup"><span data-stu-id="5de27-258">If you omit the path, the default is the current location.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5de27-259">-Maximumfollowrellink</span><span class="sxs-lookup"><span data-stu-id="5de27-259">-MaximumFollowRelLink</span></span>

<span data-ttu-id="5de27-260">Gibt an, wie oft Beziehungslinks befolgt werden sollen, wenn " **followrellink** " verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="5de27-260">Specifies how many times to follow relation links if **FollowRelLink** is used.</span></span> <span data-ttu-id="5de27-261">Ein kleinerer Wert ist möglicherweise erforderlich, wenn die Rest-API aufgrund von zu vielen Anforderungen drosselt wird.</span><span class="sxs-lookup"><span data-stu-id="5de27-261">A smaller value may be needed if the REST api throttles due to too many requests.</span></span> <span data-ttu-id="5de27-262">Der Standardwert ist `[Int32]::MaxValue`.</span><span class="sxs-lookup"><span data-stu-id="5de27-262">The default value is `[Int32]::MaxValue`.</span></span> <span data-ttu-id="5de27-263">Der Wert 0 (null) verhindert die folgenden Beziehungslinks.</span><span class="sxs-lookup"><span data-stu-id="5de27-263">A value of 0 (zero) prevents following relation links.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases: ML

Required: False
Position: Named
Default value: Int32.MaxValue
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5de27-264">-Maximumredirect</span><span class="sxs-lookup"><span data-stu-id="5de27-264">-MaximumRedirection</span></span>

<span data-ttu-id="5de27-265">Gibt an, wie oft PowerShell eine Verbindung an eine Alternative Uniform Resource Identifier (URI) umleitet, bevor die Verbindung fehlschlägt.</span><span class="sxs-lookup"><span data-stu-id="5de27-265">Specifies how many times PowerShell redirects a connection to an alternate Uniform Resource Identifier (URI) before the connection fails.</span></span> <span data-ttu-id="5de27-266">Der Standardwert ist 5.</span><span class="sxs-lookup"><span data-stu-id="5de27-266">The default value is 5.</span></span> <span data-ttu-id="5de27-267">Der Wert 0 (null) unterbindet sämtliche Umleitungen.</span><span class="sxs-lookup"><span data-stu-id="5de27-267">A value of 0 (zero) prevents all redirection.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5de27-268">-Maximumretrycount</span><span class="sxs-lookup"><span data-stu-id="5de27-268">-MaximumRetryCount</span></span>

<span data-ttu-id="5de27-269">Gibt an, wie oft PowerShell versucht, eine Verbindung wiederherzustellen, wenn ein Fehlercode zwischen 400 und 599, inklusiv oder 304 empfangen wird.</span><span class="sxs-lookup"><span data-stu-id="5de27-269">Specifies how many times PowerShell retries a connection when a failure code between 400 and 599, inclusive or 304 is received.</span></span> <span data-ttu-id="5de27-270">Siehe auch den Parameter **retryintervalsec** zum Angeben der Anzahl von Wiederholungen.</span><span class="sxs-lookup"><span data-stu-id="5de27-270">Also see **RetryIntervalSec** parameter for specifying number of retries.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5de27-271">-Methode</span><span class="sxs-lookup"><span data-stu-id="5de27-271">-Method</span></span>

<span data-ttu-id="5de27-272">Gibt die für die Webanforderung verwendete Methode an.</span><span class="sxs-lookup"><span data-stu-id="5de27-272">Specifies the method used for the web request.</span></span> <span data-ttu-id="5de27-273">Zulässige Werte für diesen Parameter:</span><span class="sxs-lookup"><span data-stu-id="5de27-273">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="5de27-274">Standard</span><span class="sxs-lookup"><span data-stu-id="5de27-274">Default</span></span>
- <span data-ttu-id="5de27-275">Löschen</span><span class="sxs-lookup"><span data-stu-id="5de27-275">Delete</span></span>
- <span data-ttu-id="5de27-276">Herunterladen</span><span class="sxs-lookup"><span data-stu-id="5de27-276">Get</span></span>
- <span data-ttu-id="5de27-277">Head</span><span class="sxs-lookup"><span data-stu-id="5de27-277">Head</span></span>
- <span data-ttu-id="5de27-278">Zusammenführen</span><span class="sxs-lookup"><span data-stu-id="5de27-278">Merge</span></span>
- <span data-ttu-id="5de27-279">Optionen</span><span class="sxs-lookup"><span data-stu-id="5de27-279">Options</span></span>
- <span data-ttu-id="5de27-280">Patch</span><span class="sxs-lookup"><span data-stu-id="5de27-280">Patch</span></span>
- <span data-ttu-id="5de27-281">Posten</span><span class="sxs-lookup"><span data-stu-id="5de27-281">Post</span></span>
- <span data-ttu-id="5de27-282">Put</span><span class="sxs-lookup"><span data-stu-id="5de27-282">Put</span></span>
- <span data-ttu-id="5de27-283">Trace</span><span class="sxs-lookup"><span data-stu-id="5de27-283">Trace</span></span>

<span data-ttu-id="5de27-284">Der **custommethod** -Parameter kann für Anforderungs Methoden verwendet werden, die oben nicht aufgeführt sind.</span><span class="sxs-lookup"><span data-stu-id="5de27-284">The **CustomMethod** parameter can be used for Request Methods not listed above.</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.WebRequestMethod
Parameter Sets: StandardMethod, StandardMethodNoProxy
Aliases:
Accepted values: Default, Get, Head, Post, Put, Delete, Trace, Options, Merge, Patch

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5de27-285">-NoProxy</span><span class="sxs-lookup"><span data-stu-id="5de27-285">-NoProxy</span></span>

<span data-ttu-id="5de27-286">Gibt an, dass das Cmdlet keinen Proxy verwendet, um das Ziel zu erreichen.</span><span class="sxs-lookup"><span data-stu-id="5de27-286">Indicates that the cmdlet will not use a proxy to reach the destination.</span></span>

<span data-ttu-id="5de27-287">Wenn Sie den in Internet Explorer konfigurierten Proxy oder einen in der Umgebung angegebenen Proxy umgehen müssen, verwenden Sie diesen Switch.</span><span class="sxs-lookup"><span data-stu-id="5de27-287">When you need to bypass the proxy configured in Internet Explorer, or a proxy specified in the environment, use this switch.</span></span>

<span data-ttu-id="5de27-288">Dieser Parameter wurde in PowerShell 6,0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="5de27-288">This parameter was introduced in PowerShell 6.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: StandardMethodNoProxy, CustomMethodNoProxy
Aliases:

Required: True
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5de27-289">-Outfile</span><span class="sxs-lookup"><span data-stu-id="5de27-289">-OutFile</span></span>

<span data-ttu-id="5de27-290">Speichert den Antworttext in der angegebenen Ausgabedatei.</span><span class="sxs-lookup"><span data-stu-id="5de27-290">Saves the response body in the specified output file.</span></span> <span data-ttu-id="5de27-291">Geben Sie einen Pfad- und Dateinamen ein.</span><span class="sxs-lookup"><span data-stu-id="5de27-291">Enter a path and file name.</span></span> <span data-ttu-id="5de27-292">Wenn Sie den Pfad weglassen, wird der aktuelle Speicherort als Standard verwendet.</span><span class="sxs-lookup"><span data-stu-id="5de27-292">If you omit the path, the default is the current location.</span></span> <span data-ttu-id="5de27-293">Der Name wird als literalpfad behandelt.</span><span class="sxs-lookup"><span data-stu-id="5de27-293">The name is treated as a literal path.</span></span> <span data-ttu-id="5de27-294">Namen, die eckige Klammern () enthalten, `[]` müssen in einfache Anführungszeichen () eingeschlossen werden `'` .</span><span class="sxs-lookup"><span data-stu-id="5de27-294">Names that contain brackets (`[]`) must be enclosed in single quotes (`'`).</span></span>

<span data-ttu-id="5de27-295">Standardmäßig `Invoke-RestMethod` gibt die Ergebnisse an die Pipeline zurück.</span><span class="sxs-lookup"><span data-stu-id="5de27-295">By default, `Invoke-RestMethod` returns the results to the pipeline.</span></span> <span data-ttu-id="5de27-296">Verwenden Sie den **Passthru**-Parameter, um Ergebnisse an eine Datei und an die Pipeline zu senden.</span><span class="sxs-lookup"><span data-stu-id="5de27-296">To send the results to a file and to the pipeline, use the **Passthru** parameter.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5de27-297">-PassThru</span><span class="sxs-lookup"><span data-stu-id="5de27-297">-PassThru</span></span>

<span data-ttu-id="5de27-298">Gibt die Ergebnisse zurück und schreibt sie in eine Datei.</span><span class="sxs-lookup"><span data-stu-id="5de27-298">Returns the results, in addition to writing them to a file.</span></span> <span data-ttu-id="5de27-299">Dieser Parameter ist nur gültig, wenn der **OutFile**-Parameter ebenfalls im Befehl verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="5de27-299">This parameter is valid only when the **OutFile** parameter is also used in the command.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: No output
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5de27-300">-Preserveauthorizationonredirect</span><span class="sxs-lookup"><span data-stu-id="5de27-300">-PreserveAuthorizationOnRedirect</span></span>

<span data-ttu-id="5de27-301">Gibt an, dass das Cmdlet den `Authorization` Header, falls vorhanden, über Umleitungen beibehalten soll.</span><span class="sxs-lookup"><span data-stu-id="5de27-301">Indicates the cmdlet should preserve the `Authorization` header, when present, across redirections.</span></span>

<span data-ttu-id="5de27-302">Standardmäßig entfernt das Cmdlet den `Authorization` Header vor der Umleitung.</span><span class="sxs-lookup"><span data-stu-id="5de27-302">By default, the cmdlet strips the `Authorization` header before redirecting.</span></span> <span data-ttu-id="5de27-303">Durch die Angabe dieses Parameters wird diese Logik in Fällen deaktiviert, in denen der Header an den Umleitungs Speicherort gesendet werden muss.</span><span class="sxs-lookup"><span data-stu-id="5de27-303">Specifying this parameter disables this logic for cases where the header needs to be sent to the redirection location.</span></span>

<span data-ttu-id="5de27-304">Diese Funktion wurde in PowerShell 6.0.0 hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="5de27-304">This feature was added in PowerShell 6.0.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5de27-305">-Proxy</span><span class="sxs-lookup"><span data-stu-id="5de27-305">-Proxy</span></span>

<span data-ttu-id="5de27-306">Verwendet einen Proxy Server für die Anforderung, anstatt eine direkte Verbindung mit der Internet Ressource herzustellen.</span><span class="sxs-lookup"><span data-stu-id="5de27-306">Uses a proxy server for the request, rather than connecting directly to the internet resource.</span></span> <span data-ttu-id="5de27-307">Geben Sie den Uniform Resource Identifier (URI) eines Netzwerk Proxy Servers ein.</span><span class="sxs-lookup"><span data-stu-id="5de27-307">Enter the Uniform Resource Identifier (URI) of a network proxy server.</span></span>

<span data-ttu-id="5de27-308">Diese Funktion wurde in PowerShell 6.0.0 hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="5de27-308">This feature was added in PowerShell 6.0.0.</span></span>

```yaml
Type: System.Uri
Parameter Sets: StandardMethod, CustomMethod
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5de27-309">-Proxy Credential</span><span class="sxs-lookup"><span data-stu-id="5de27-309">-ProxyCredential</span></span>

<span data-ttu-id="5de27-310">Gibt ein Benutzerkonto an, das über die Berechtigung zur Verwendung des Proxyservers verfügt, der durch den **Proxy**-Parameter angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="5de27-310">Specifies a user account that has permission to use the proxy server that is specified by the **Proxy** parameter.</span></span> <span data-ttu-id="5de27-311">Der Standardwert ist der aktuelle Benutzer.</span><span class="sxs-lookup"><span data-stu-id="5de27-311">The default is the current user.</span></span>

<span data-ttu-id="5de27-312">Geben Sie einen Benutzernamen ein, z. b. **USER01** oder **Domain01\User01**, **User@Domain.Com** , oder geben Sie ein- `PSCredential` Objekt ein, z. b. das vom `Get-Credential` Cmdlet generierte.</span><span class="sxs-lookup"><span data-stu-id="5de27-312">Type a user name, such as **User01** or **Domain01\User01**, **User@Domain.Com**, or enter a `PSCredential` object, such as one generated by the `Get-Credential` cmdlet.</span></span>

<span data-ttu-id="5de27-313">Dieser Parameter ist nur gültig, wenn der **Proxy** Parameter auch im Befehl verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="5de27-313">This parameter is valid only when the **Proxy** parameter is also used in the command.</span></span> <span data-ttu-id="5de27-314">Die Parameter " **proxycredential** " und " **proxyusedefaultcredential** " können nicht im selben Befehl verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="5de27-314">You can't use the **ProxyCredential** and **ProxyUseDefaultCredentials** parameters in the same command.</span></span>

```yaml
Type: System.Management.Automation.PSCredential
Parameter Sets: StandardMethod, CustomMethod
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5de27-315">-Proxyusedefault-Anmelde Informationen</span><span class="sxs-lookup"><span data-stu-id="5de27-315">-ProxyUseDefaultCredentials</span></span>

<span data-ttu-id="5de27-316">Gibt an, dass das Cmdlet die Anmelde Informationen des aktuellen Benutzers verwendet, um auf den Proxy Server zuzugreifen, der durch den **Proxy** Parameter angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="5de27-316">Indicates that the cmdlet uses the credentials of the current user to access the proxy server that is specified by the **Proxy** parameter.</span></span>

<span data-ttu-id="5de27-317">Dieser Parameter ist nur gültig, wenn der **Proxy** Parameter auch im Befehl verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="5de27-317">This parameter is valid only when the **Proxy** parameter is also used in the command.</span></span> <span data-ttu-id="5de27-318">Die Parameter " **proxycredential** " und " **proxyusedefaultcredential** " können nicht im selben Befehl verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="5de27-318">You can't use the **ProxyCredential** and **ProxyUseDefaultCredentials** parameters in the same command.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: StandardMethod, CustomMethod
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5de27-319">-Response Header Variable</span><span class="sxs-lookup"><span data-stu-id="5de27-319">-ResponseHeadersVariable</span></span>

<span data-ttu-id="5de27-320">Erstellt ein Antwortheader-Wörterbuch und speichert es im Wert der angegebenen Variablen.</span><span class="sxs-lookup"><span data-stu-id="5de27-320">Creates a Response Headers Dictionary and saves it in the value of the specified variable.</span></span> <span data-ttu-id="5de27-321">Die Schlüssel des Wörterbuchs enthalten die Feldnamen des Antwort Headers, der vom Webserver zurückgegeben wird, und die Werte sind die jeweiligen Feldwerte.</span><span class="sxs-lookup"><span data-stu-id="5de27-321">The keys of the dictionary will contain the field names of the Response Header returned by the web server and the values will be the respective field values.</span></span>

<span data-ttu-id="5de27-322">Diese Funktion wurde in PowerShell 6.0.0 hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="5de27-322">This feature was added in PowerShell 6.0.0.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: RHV

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5de27-323">-Fortsetzen</span><span class="sxs-lookup"><span data-stu-id="5de27-323">-Resume</span></span>

<span data-ttu-id="5de27-324">Führt einen bewährten Versuch aus, den Download einer partiellen Datei fortzusetzen.</span><span class="sxs-lookup"><span data-stu-id="5de27-324">Performs a best effort attempt to resume downloading a partial file.</span></span> <span data-ttu-id="5de27-325">Der **Resume** -Parameter erfordert den **outfile** -Parameter.</span><span class="sxs-lookup"><span data-stu-id="5de27-325">The **Resume** parameter requires the **OutFile** parameter.</span></span>

<span data-ttu-id="5de27-326">**Resume** funktioniert nur mit der Größe der lokalen Datei und der Remote Datei und führt keine andere Überprüfung durch, dass die lokale Datei und die Remote Datei identisch sind.</span><span class="sxs-lookup"><span data-stu-id="5de27-326">**Resume** only operates on the size of the local file and remote file and performs no other validation that the local file and the remote file are the same.</span></span>

<span data-ttu-id="5de27-327">Wenn die lokale Dateigröße kleiner ist als die Remote Dateigröße, versucht das Cmdlet, das Herunterladen der Datei fortzusetzen und die verbleibenden Bytes an das Ende der Datei anzuhängen.</span><span class="sxs-lookup"><span data-stu-id="5de27-327">If the local file size is smaller than the remote file size, then the cmdlet will attempt to resume downloading the file and append the remaining bytes to the end of the file.</span></span>

<span data-ttu-id="5de27-328">Wenn die lokale Dateigröße mit der Remote Dateigröße identisch ist, wird keine Aktion durchgeführt, und das Cmdlet geht davon aus, dass der Download bereits abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="5de27-328">If the local file size is the same as the remote file size, then no action is taken and the cmdlet assumes the download already completed.</span></span>

<span data-ttu-id="5de27-329">Wenn die Größe der lokalen Datei größer ist als die Remote Dateigröße, wird die lokale Datei überschrieben, und die gesamte Remote Datei wird vollständig erneut heruntergeladen.</span><span class="sxs-lookup"><span data-stu-id="5de27-329">If the local file size is larger than the remote file size, then the local file will be overwritten and the entire remote file will be completely re-downloaded.</span></span> <span data-ttu-id="5de27-330">Dieses Verhalten ist mit der Verwendung von **outfile** ohne **fort** Setzung identisch.</span><span class="sxs-lookup"><span data-stu-id="5de27-330">This behavior is the same as using **OutFile** without **Resume**.</span></span>

<span data-ttu-id="5de27-331">Wenn der Remote Server das Herunterladen von Downloads nicht unterstützt, wird die lokale Datei überschrieben, und die gesamte Remote Datei wird vollständig erneut heruntergeladen.</span><span class="sxs-lookup"><span data-stu-id="5de27-331">If the remote server does not support download resuming, then the local file will be overwritten and the entire remote file will be completely re-downloaded.</span></span> <span data-ttu-id="5de27-332">Dieses Verhalten ist mit der Verwendung von **outfile** ohne **fort** Setzung identisch.</span><span class="sxs-lookup"><span data-stu-id="5de27-332">This behavior is the same as using **OutFile** without **Resume**.</span></span>

<span data-ttu-id="5de27-333">Wenn die lokale Datei nicht vorhanden ist, wird die lokale Datei erstellt, und die gesamte Remote Datei wird vollständig heruntergeladen.</span><span class="sxs-lookup"><span data-stu-id="5de27-333">If the local file doesn't exist, then the local file will be created and the entire remote file will be completely downloaded.</span></span> <span data-ttu-id="5de27-334">Dieses Verhalten ist mit der Verwendung von **outfile** ohne **fort** Setzung identisch.</span><span class="sxs-lookup"><span data-stu-id="5de27-334">This behavior is the same as using **OutFile** without **Resume**.</span></span>

<span data-ttu-id="5de27-335">Diese Funktion wurde in PowerShell 6.1.0 hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="5de27-335">This feature was added in PowerShell 6.1.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5de27-336">-Retryintervalsec</span><span class="sxs-lookup"><span data-stu-id="5de27-336">-RetryIntervalSec</span></span>

<span data-ttu-id="5de27-337">Gibt das Intervall zwischen den Wiederholungs versuchen für die Verbindung an, wenn ein Fehlercode zwischen 400 und 599, inklusiv oder 304 empfangen wird.</span><span class="sxs-lookup"><span data-stu-id="5de27-337">Specifies the interval between retries for the connection when a failure code between 400 and 599, inclusive or 304 is received.</span></span> <span data-ttu-id="5de27-338">Siehe auch " **maximumretrycount** "-Parameter zum Angeben der Anzahl von Wiederholungs versuchen.</span><span class="sxs-lookup"><span data-stu-id="5de27-338">Also see **MaximumRetryCount** parameter for specifying number of retries.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5de27-339">-Sessionvariable</span><span class="sxs-lookup"><span data-stu-id="5de27-339">-SessionVariable</span></span>

<span data-ttu-id="5de27-340">Gibt eine Variable an, für die dieses Cmdlet eine Webanforderungs Sitzung erstellt und im Wert speichert.</span><span class="sxs-lookup"><span data-stu-id="5de27-340">Specifies a variable for which this cmdlet creates a web request session and saves it in the value.</span></span>
<span data-ttu-id="5de27-341">Geben Sie einen Variablennamen ohne das Dollarzeichen `$` Symbol () ein.</span><span class="sxs-lookup"><span data-stu-id="5de27-341">Enter a variable name without the dollar sign (`$`) symbol.</span></span>

<span data-ttu-id="5de27-342">Wenn Sie eine Sitzungs Variable angeben, `Invoke-RestMethod` erstellt ein Webanforderungs-Sitzungs Objekt und weist es einer Variablen mit dem angegebenen Namen in der PowerShell-Sitzung zu.</span><span class="sxs-lookup"><span data-stu-id="5de27-342">When you specify a session variable, `Invoke-RestMethod` creates a web request session object and assigns it to a variable with the specified name in your PowerShell session.</span></span> <span data-ttu-id="5de27-343">Sie können die Variable in der Sitzung verwenden, sobald der Befehl abgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="5de27-343">You can use the variable in your session as soon as the command completes.</span></span>

<span data-ttu-id="5de27-344">Im Gegensatz zu einer Remote Sitzung ist die Webanforderungs Sitzung keine persistente Verbindung.</span><span class="sxs-lookup"><span data-stu-id="5de27-344">Unlike a remote session, the web request session isn't a persistent connection.</span></span> <span data-ttu-id="5de27-345">Dabei handelt es sich um ein Objekt, das Informationen über die Verbindung und die Anforderung enthält, einschließlich Cookies, Anmelde Informationen, des maximalen Umleitungs Werts und der Zeichenfolge des Benutzer-Agents.</span><span class="sxs-lookup"><span data-stu-id="5de27-345">It's an object that contains information about the connection and the request, including cookies, credentials, the maximum redirection value, and the user agent string.</span></span> <span data-ttu-id="5de27-346">Sie können das Objekt verwenden, um den Zustand und die Daten übergreifend für Webanforderungen zu nutzen.</span><span class="sxs-lookup"><span data-stu-id="5de27-346">You can use it to share state and data among web requests.</span></span>

<span data-ttu-id="5de27-347">Um die Webanforderungssitzung in nachfolgenden Webanforderungen zu verwenden, geben Sie die Sitzungsvariable im Wert des **WebSession**-Parameters an.</span><span class="sxs-lookup"><span data-stu-id="5de27-347">To use the web request session in subsequent web requests, specify the session variable in the value of the **WebSession** parameter.</span></span> <span data-ttu-id="5de27-348">PowerShell verwendet die Daten im Sitzungs Objekt der Webanforderung, wenn die neue Verbindung hergestellt wird.</span><span class="sxs-lookup"><span data-stu-id="5de27-348">PowerShell uses the data in the web request session object when establishing the new connection.</span></span> <span data-ttu-id="5de27-349">Um einen Wert in der Webanforderungssitzung zu überschreiben, verwenden Sie einen Cmdletparameter wie **UserAgent** oder **Credential**.</span><span class="sxs-lookup"><span data-stu-id="5de27-349">To override a value in the web request session, use a cmdlet parameter, such as **UserAgent** or **Credential**.</span></span> <span data-ttu-id="5de27-350">Parameterwerte haben Vorrang vor Werten in der Webanforderungssitzung.</span><span class="sxs-lookup"><span data-stu-id="5de27-350">Parameter values take precedence over values in the web request session.</span></span>

<span data-ttu-id="5de27-351">Der **sessionvariable** -Parameter und der **websession** -Parameter können nicht im selben Befehl verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="5de27-351">You can't use the **SessionVariable** and **WebSession** parameters in the same command.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases: SV

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5de27-352">-SkipCertificateCheck</span><span class="sxs-lookup"><span data-stu-id="5de27-352">-SkipCertificateCheck</span></span>

<span data-ttu-id="5de27-353">Überspringt Überprüfungen der Zertifikat Überprüfung, die alle Überprüfungen enthalten, wie z. b. Ablauf, Sperrung, vertrauenswürdige Stamm Zertifizierungsstelle usw.</span><span class="sxs-lookup"><span data-stu-id="5de27-353">Skips certificate validation checks that include all validations such as expiration, revocation, trusted root authority, etc.</span></span>

> [!WARNING]
> <span data-ttu-id="5de27-354">Die Verwendung dieses Parameters ist nicht sicher und wird nicht empfohlen.</span><span class="sxs-lookup"><span data-stu-id="5de27-354">Using this parameter is not secure and is not recommended.</span></span> <span data-ttu-id="5de27-355">Dieser Switch sollte nur für bekannte Hosts verwendet werden, die ein selbst signiertes Zertifikat zu Testzwecken verwenden.</span><span class="sxs-lookup"><span data-stu-id="5de27-355">This switch is only intended to be used against known hosts using a self-signed certificate for testing purposes.</span></span> <span data-ttu-id="5de27-356">Verwenden Sie auf eigene Gefahr.</span><span class="sxs-lookup"><span data-stu-id="5de27-356">Use at your own risk.</span></span>

<span data-ttu-id="5de27-357">Diese Funktion wurde in PowerShell 6.0.0 hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="5de27-357">This feature was added in PowerShell 6.0.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5de27-358">-Skipheadervalidation</span><span class="sxs-lookup"><span data-stu-id="5de27-358">-SkipHeaderValidation</span></span>

<span data-ttu-id="5de27-359">Gibt an, dass das Cmdlet der Anforderung Header ohne Validierung hinzufügen soll.</span><span class="sxs-lookup"><span data-stu-id="5de27-359">Indicates the cmdlet should add headers to the request without validation.</span></span>

<span data-ttu-id="5de27-360">Dieser Switch sollte für Standorte verwendet werden, für die Header Werte erforderlich sind, die nicht den Standards entsprechen.</span><span class="sxs-lookup"><span data-stu-id="5de27-360">This switch should be used for sites that require header values that do not conform to standards.</span></span>
<span data-ttu-id="5de27-361">Wenn Sie diesen Schalter angeben, wird die Validierung deaktiviert, damit der Wert nicht aktiviert werden kann.</span><span class="sxs-lookup"><span data-stu-id="5de27-361">Specifying this switch disables validation to allow the value to be passed unchecked.</span></span> <span data-ttu-id="5de27-362">Wenn angegeben, werden alle Header ohne Validierung hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="5de27-362">When specified, all headers are added without validation.</span></span>

<span data-ttu-id="5de27-363">Dadurch wird die Überprüfung für Werte deaktiviert, die an die Parameter **ContentType**, **Headers** und **userAgent** übermittelt werden.</span><span class="sxs-lookup"><span data-stu-id="5de27-363">This will disable validation for values passed to the **ContentType**, **Headers**, and **UserAgent** parameters.</span></span>

<span data-ttu-id="5de27-364">Diese Funktion wurde in PowerShell 6.0.0 hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="5de27-364">This feature was added in PowerShell 6.0.0.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5de27-365">-Skiphttperrorcheck</span><span class="sxs-lookup"><span data-stu-id="5de27-365">-SkipHttpErrorCheck</span></span>

<span data-ttu-id="5de27-366">Dieser Parameter bewirkt, dass das Cmdlet http-Fehlerstatus ignoriert und die Verarbeitung von Antworten fortsetzt.</span><span class="sxs-lookup"><span data-stu-id="5de27-366">This parameter causes the cmdlet to ignore HTTP error statuses and continue to process responses.</span></span>
<span data-ttu-id="5de27-367">Die Fehler Antworten werden genau so in die Pipeline geschrieben, als ob Sie erfolgreich waren.</span><span class="sxs-lookup"><span data-stu-id="5de27-367">The error responses are written to the pipeline just as if they were successful.</span></span>

<span data-ttu-id="5de27-368">Dieser Parameter wurde in PowerShell 7 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="5de27-368">This parameter was introduced in PowerShell 7.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: False
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5de27-369">-SslProtocol</span><span class="sxs-lookup"><span data-stu-id="5de27-369">-SslProtocol</span></span>

<span data-ttu-id="5de27-370">Legt die SSL/TLS-Protokolle fest, die für die Webanforderung zulässig sind.</span><span class="sxs-lookup"><span data-stu-id="5de27-370">Sets the SSL/TLS protocols that are permissible for the web request.</span></span> <span data-ttu-id="5de27-371">Standardmäßig sind alle vom System unterstützten SSL/TLS-Protokolle zulässig.</span><span class="sxs-lookup"><span data-stu-id="5de27-371">By default all, SSL/TLS protocols supported by the system are allowed.</span></span> <span data-ttu-id="5de27-372">**SslProtocol** ermöglicht die Beschränkung auf bestimmte Protokolle zu Konformitäts Zwecken.</span><span class="sxs-lookup"><span data-stu-id="5de27-372">**SslProtocol** allows for limiting to specific protocols for compliance purposes.</span></span>

<span data-ttu-id="5de27-373">**SslProtocol** verwendet die Flag-Aufzählung `WebSslProtocol` .</span><span class="sxs-lookup"><span data-stu-id="5de27-373">**SslProtocol** uses the `WebSslProtocol` Flag Enum.</span></span> <span data-ttu-id="5de27-374">Es ist möglich, mehr als ein Protokoll mithilfe der Flag-Notation anzugeben oder mehrere `WebSslProtocol` Optionen mit zu kombinieren `-bor` . das Bereitstellen mehrerer Protokolle wird jedoch nicht auf allen Plattformen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="5de27-374">It is possible to supply more than one protocol using flag notation or combining multiple `WebSslProtocol` options with `-bor`, however supplying multiple protocols is not supported on all platforms.</span></span>

> [!NOTE]
> <span data-ttu-id="5de27-375">Auf nicht-Windows-Plattformen ist es möglicherweise nicht möglich, `Tls` oder `Tls12` als Option anzugeben.</span><span class="sxs-lookup"><span data-stu-id="5de27-375">On non-Windows platforms it may not be possible to supply `Tls` or `Tls12` as an option.</span></span> <span data-ttu-id="5de27-376">Die Unterstützung für `Tls13` ist nicht auf allen Betriebssystemen verfügbar und muss pro Betriebssystem überprüft werden.</span><span class="sxs-lookup"><span data-stu-id="5de27-376">Support for `Tls13` is not available on all operating systems and will need to be verified on a per operating system basis.</span></span>

<span data-ttu-id="5de27-377">Diese Funktion wurde in PowerShell 6.0.0 hinzugefügt, und die Unterstützung für `Tls13` wurde in PowerShell 7,1 hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="5de27-377">This feature was added in PowerShell 6.0.0 and support for `Tls13` was added in PowerShell 7.1.</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.WebSslProtocol
Parameter Sets: (All)
Aliases:
Accepted values: Default, Tls, Tls11, Tls12, Tls13

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5de27-378">-Statuscode Variable</span><span class="sxs-lookup"><span data-stu-id="5de27-378">-StatusCodeVariable</span></span>

<span data-ttu-id="5de27-379">Dieser Parameter gibt eine Variable an, der der ganzzahlige Wert des Statuscodes zugewiesen wird.</span><span class="sxs-lookup"><span data-stu-id="5de27-379">This parameter specifies a variable that's assigned a status code's integer value.</span></span> <span data-ttu-id="5de27-380">Der-Parameter kann Erfolgsmeldungen oder Fehlermeldungen identifizieren, wenn er mit dem **skiphttperrorcheck** -Parameter verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="5de27-380">The parameter can identify success messages or failure messages when used with the **SkipHttpErrorCheck** parameter.</span></span>

<span data-ttu-id="5de27-381">Geben Sie den Variablennamen des Parameters als Zeichenfolge ein, z `-StatusCodeVariable "scv"` . b..</span><span class="sxs-lookup"><span data-stu-id="5de27-381">Input the parameter's variable name as a string such as `-StatusCodeVariable "scv"`.</span></span>

<span data-ttu-id="5de27-382">Dieser Parameter wurde in PowerShell 7 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="5de27-382">This parameter was introduced in PowerShell 7.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5de27-383">-Timeoutsec</span><span class="sxs-lookup"><span data-stu-id="5de27-383">-TimeoutSec</span></span>

<span data-ttu-id="5de27-384">Gibt an, wie lange die Anforderung ausstehend sein kann, bevor eine Zeitüberschreitung auftritt. Geben Sie einen Wert in Sekunden ein.</span><span class="sxs-lookup"><span data-stu-id="5de27-384">Specifies how long the request can be pending before it times out. Enter a value in seconds.</span></span> <span data-ttu-id="5de27-385">Der Standardwert 0 (null) steht für einen unbegrenzten Zeitüberschreitungswert.</span><span class="sxs-lookup"><span data-stu-id="5de27-385">The default value, 0, specifies an indefinite time-out.</span></span>

<span data-ttu-id="5de27-386">Eine Domain Name System (DNS)-Abfrage kann bis zu 15 Sekunden dauern, bis eine Rückgabe oder ein Timeout auftritt. Wenn Ihre Anforderung einen Hostnamen enthält, der aufgelöst werden muss, und Sie **timeoutsec** auf einen Wert größer als 0 (null), aber weniger als 15 Sekunden festlegen, kann es 15 Sekunden oder länger dauern, bis eine WebException ausgelöst wird und für Ihre Anforderung ein Timeout eintritt.</span><span class="sxs-lookup"><span data-stu-id="5de27-386">A Domain Name System (DNS) query can take up to 15 seconds to return or time out. If your request contains a host name that requires resolution, and you set **TimeoutSec** to a value greater than zero, but less than 15 seconds, it can take 15 seconds or more before a WebException is thrown, and your request times out.</span></span>

```yaml
Type: System.Int32
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5de27-387">-Token</span><span class="sxs-lookup"><span data-stu-id="5de27-387">-Token</span></span>

<span data-ttu-id="5de27-388">Das OAuth-oder bearertoken, das in die Anforderung aufgenommen werden soll.</span><span class="sxs-lookup"><span data-stu-id="5de27-388">The OAuth or Bearer token to include in the request.</span></span> <span data-ttu-id="5de27-389">**Token** ist für bestimmte **Authentifizierungs** Optionen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="5de27-389">**Token** is required by certain **Authentication** options.</span></span> <span data-ttu-id="5de27-390">Sie kann nicht unabhängig verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="5de27-390">It can't be used independently.</span></span>

<span data-ttu-id="5de27-391">**Token** nimmt einen an `SecureString` , der das Token enthält.</span><span class="sxs-lookup"><span data-stu-id="5de27-391">**Token** takes a `SecureString` that contains the token.</span></span> <span data-ttu-id="5de27-392">Um das Token bereitzustellen, verwenden Sie manuell Folgendes:</span><span class="sxs-lookup"><span data-stu-id="5de27-392">To supply the token, manually use the following:</span></span>

`Invoke-RestMethod -Uri $uri -Authentication OAuth -Token (Read-Host -AsSecureString)`

<span data-ttu-id="5de27-393">Dieser Parameter wurde in PowerShell 6,0 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="5de27-393">This parameter was introduced in PowerShell 6.0.</span></span>

```yaml
Type: System.Security.SecureString
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5de27-394">-TransferEncoding</span><span class="sxs-lookup"><span data-stu-id="5de27-394">-TransferEncoding</span></span>

<span data-ttu-id="5de27-395">Gibt einen Wert für den HTTP-Antwortheader transfer-encoding an.</span><span class="sxs-lookup"><span data-stu-id="5de27-395">Specifies a value for the transfer-encoding HTTP response header.</span></span> <span data-ttu-id="5de27-396">Zulässige Werte für diesen Parameter:</span><span class="sxs-lookup"><span data-stu-id="5de27-396">The acceptable values for this parameter are:</span></span>

- <span data-ttu-id="5de27-397">Aufgeteilte</span><span class="sxs-lookup"><span data-stu-id="5de27-397">Chunked</span></span>
- <span data-ttu-id="5de27-398">Komprimieren</span><span class="sxs-lookup"><span data-stu-id="5de27-398">Compress</span></span>
- <span data-ttu-id="5de27-399">Deflate</span><span class="sxs-lookup"><span data-stu-id="5de27-399">Deflate</span></span>
- <span data-ttu-id="5de27-400">GZip</span><span class="sxs-lookup"><span data-stu-id="5de27-400">GZip</span></span>
- <span data-ttu-id="5de27-401">Identity</span><span class="sxs-lookup"><span data-stu-id="5de27-401">Identity</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:
Accepted values: chunked, compress, deflate, gzip, identity

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5de27-402">-URI</span><span class="sxs-lookup"><span data-stu-id="5de27-402">-Uri</span></span>

<span data-ttu-id="5de27-403">Gibt den Uniform Resource Identifier (URI) der Internet Ressource an, an die die Webanforderung gesendet wird.</span><span class="sxs-lookup"><span data-stu-id="5de27-403">Specifies the Uniform Resource Identifier (URI) of the internet resource to which the web request is sent.</span></span> <span data-ttu-id="5de27-404">Dieser Parameter unterstützt HTTP-, HTTPS-, FTP- und FILE-Werte.</span><span class="sxs-lookup"><span data-stu-id="5de27-404">This parameter supports HTTP, HTTPS, FTP, and FILE values.</span></span>

<span data-ttu-id="5de27-405">Dieser Parameter ist erforderlich.</span><span class="sxs-lookup"><span data-stu-id="5de27-405">This parameter is required.</span></span> <span data-ttu-id="5de27-406">Der Parameter Name (**URI**) ist optional.</span><span class="sxs-lookup"><span data-stu-id="5de27-406">The parameter name (**Uri**) is optional.</span></span>

```yaml
Type: System.Uri
Parameter Sets: (All)
Aliases:

Required: True
Position: 0
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5de27-407">-Usebasicparamesing</span><span class="sxs-lookup"><span data-stu-id="5de27-407">-UseBasicParsing</span></span>

<span data-ttu-id="5de27-408">Dieser Parameter ist veraltet.</span><span class="sxs-lookup"><span data-stu-id="5de27-408">This parameter has been deprecated.</span></span> <span data-ttu-id="5de27-409">Ab PowerShell 6.0.0 verwenden alle Webanforderungen nur die grundlegende-Verarbeitung.</span><span class="sxs-lookup"><span data-stu-id="5de27-409">Beginning with PowerShell 6.0.0, all Web requests use basic parsing only.</span></span> <span data-ttu-id="5de27-410">Dieser Parameter ist nur aus Gründen der Abwärtskompatibilität enthalten, und jeder Verwendungszweck hat keine Auswirkung auf den Vorgang des Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="5de27-410">This parameter is included for backwards compatibility only and any use of it will have no effect on the operation of the cmdlet.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5de27-411">-Usedefault-Anmelde Informationen</span><span class="sxs-lookup"><span data-stu-id="5de27-411">-UseDefaultCredentials</span></span>

<span data-ttu-id="5de27-412">Gibt an, dass das Cmdlet die Anmelde Informationen des aktuellen Benutzers verwendet, um die Webanforderung zu senden.</span><span class="sxs-lookup"><span data-stu-id="5de27-412">Indicates that the cmdlet uses the credentials of the current user to send the web request.</span></span> <span data-ttu-id="5de27-413">Dies kann nicht mit **Authentifizierung** **oder Anmelde** Informationen verwendet werden und wird möglicherweise nicht auf allen Plattformen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="5de27-413">This can't be used with **Authentication** or **Credential** and may not be supported on all platforms.</span></span>

```yaml
Type: System.Management.Automation.SwitchParameter
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5de27-414">-UserAgent</span><span class="sxs-lookup"><span data-stu-id="5de27-414">-UserAgent</span></span>

<span data-ttu-id="5de27-415">Gibt eine Benutzer-Agent-Zeichenfolge für die Webanforderung an.</span><span class="sxs-lookup"><span data-stu-id="5de27-415">Specifies a user agent string for the web request.</span></span>

<span data-ttu-id="5de27-416">Der Standard-Benutzer-Agent ähnelt `Mozilla/5.0 (Windows NT 10.0; Microsoft Windows 10.0.15063; en-US) PowerShell/6.0.0` mit geringfügigen Abweichungen für die einzelnen Betriebssysteme und Plattformen.</span><span class="sxs-lookup"><span data-stu-id="5de27-416">The default user agent is similar to `Mozilla/5.0 (Windows NT 10.0; Microsoft Windows 10.0.15063; en-US) PowerShell/6.0.0` with slight variations for each operating system and platform.</span></span>

<span data-ttu-id="5de27-417">Um eine Website mit der standardmäßigen Benutzer-Agent-Zeichenfolge zu testen, die von den meisten Internetbrowsern verwendet wird, verwenden Sie die Eigenschaften der Klasse [psuseragent](/dotnet/api/microsoft.powershell.commands.psuseragent) , z. b. Chrome, Firefox, Internet Explorer, Opera und Safari.</span><span class="sxs-lookup"><span data-stu-id="5de27-417">To test a website with the standard user agent string that is used by most internet browsers, use the properties of the [PSUserAgent](/dotnet/api/microsoft.powershell.commands.psuseragent) class, such as Chrome, FireFox, InternetExplorer, Opera, and Safari.</span></span>

```yaml
Type: System.String
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5de27-418">-Websession</span><span class="sxs-lookup"><span data-stu-id="5de27-418">-WebSession</span></span>

<span data-ttu-id="5de27-419">Gibt eine Webanforderungssitzung an.</span><span class="sxs-lookup"><span data-stu-id="5de27-419">Specifies a web request session.</span></span> <span data-ttu-id="5de27-420">Geben Sie den Variablennamen einschließlich des Dollar Zeichens ( `$` ) ein.</span><span class="sxs-lookup"><span data-stu-id="5de27-420">Enter the variable name, including the dollar sign (`$`).</span></span>

<span data-ttu-id="5de27-421">Um einen Wert in der Webanforderungssitzung zu überschreiben, verwenden Sie einen Cmdletparameter wie **UserAgent** oder **Credential**.</span><span class="sxs-lookup"><span data-stu-id="5de27-421">To override a value in the web request session, use a cmdlet parameter, such as **UserAgent** or **Credential**.</span></span> <span data-ttu-id="5de27-422">Parameterwerte haben Vorrang vor Werten in der Webanforderungssitzung.</span><span class="sxs-lookup"><span data-stu-id="5de27-422">Parameter values take precedence over values in the web request session.</span></span> <span data-ttu-id="5de27-423">Inhalts bezogene Header, wie z `Content-Type` . b., werden auch überschrieben, wenn ein **multipartformdatacontent** -Objekt für den **Text** angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="5de27-423">Content related headers, such as `Content-Type`, will be also be overridden when a **MultipartFormDataContent** object is supplied for **Body**.</span></span>

<span data-ttu-id="5de27-424">Im Gegensatz zu einer Remote Sitzung ist die Webanforderungs Sitzung keine persistente Verbindung.</span><span class="sxs-lookup"><span data-stu-id="5de27-424">Unlike a remote session, the web request session isn't a persistent connection.</span></span> <span data-ttu-id="5de27-425">Dabei handelt es sich um ein Objekt, das Informationen über die Verbindung und die Anforderung enthält, einschließlich Cookies, Anmelde Informationen, des maximalen Umleitungs Werts und der Zeichenfolge des Benutzer-Agents.</span><span class="sxs-lookup"><span data-stu-id="5de27-425">It's an object that contains information about the connection and the request, including cookies, credentials, the maximum redirection value, and the user agent string.</span></span> <span data-ttu-id="5de27-426">Sie können das Objekt verwenden, um den Zustand und die Daten übergreifend für Webanforderungen zu nutzen.</span><span class="sxs-lookup"><span data-stu-id="5de27-426">You can use it to share state and data among web requests.</span></span>

<span data-ttu-id="5de27-427">Um eine Webanforderungs Sitzung zu erstellen, geben Sie einen Variablennamen ohne Dollarzeichen in den Wert des **sessionvariable** -Parameters eines `Invoke-RestMethod` Befehls ein.</span><span class="sxs-lookup"><span data-stu-id="5de27-427">To create a web request session, enter a variable name, without a dollar sign, in the value of the **SessionVariable** parameter of an `Invoke-RestMethod` command.</span></span> <span data-ttu-id="5de27-428">`Invoke-RestMethod` erstellt die Sitzung und speichert Sie in der Variablen.</span><span class="sxs-lookup"><span data-stu-id="5de27-428">`Invoke-RestMethod` creates the session and saves it in the variable.</span></span> <span data-ttu-id="5de27-429">In allen nachfolgenden Befehlen verwenden Sie die Variable als Wert für den **WebSession**-Parameter.</span><span class="sxs-lookup"><span data-stu-id="5de27-429">In subsequent commands, use the variable as the value of the **WebSession** parameter.</span></span>

<span data-ttu-id="5de27-430">Der **sessionvariable** -Parameter und der **websession** -Parameter können nicht im selben Befehl verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="5de27-430">You can't use the **SessionVariable** and **WebSession** parameters in the same command.</span></span>

```yaml
Type: Microsoft.PowerShell.Commands.WebRequestSession
Parameter Sets: (All)
Aliases:

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### <span data-ttu-id="5de27-431">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="5de27-431">CommonParameters</span></span>

<span data-ttu-id="5de27-432">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="5de27-432">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="5de27-433">Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="5de27-433">For more information, see [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="5de27-434">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="5de27-434">INPUTS</span></span>

### <span data-ttu-id="5de27-435">System.Object</span><span class="sxs-lookup"><span data-stu-id="5de27-435">System.Object</span></span>

<span data-ttu-id="5de27-436">Sie können den Text einer Webanforderung an übergeben `Invoke-RestMethod` .</span><span class="sxs-lookup"><span data-stu-id="5de27-436">You can pipe the body of a web request to `Invoke-RestMethod`.</span></span>

## <span data-ttu-id="5de27-437">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="5de27-437">OUTPUTS</span></span>

### <span data-ttu-id="5de27-438">System. Int64, System. String, System.Xml.XmlDokument</span><span class="sxs-lookup"><span data-stu-id="5de27-438">System.Int64, System.String, System.Xml.XmlDocument</span></span>

<span data-ttu-id="5de27-439">Die Ausgabe des Cmdlets hängt vom Format des abgerufenen Inhalts ab.</span><span class="sxs-lookup"><span data-stu-id="5de27-439">The output of the cmdlet depends upon the format of the content that is retrieved.</span></span>

### <span data-ttu-id="5de27-440">PSObject</span><span class="sxs-lookup"><span data-stu-id="5de27-440">PSObject</span></span>

<span data-ttu-id="5de27-441">Wenn die Anforderung JSON-Zeichen folgen zurückgibt, `Invoke-RestMethod` gibt ein **psobject** zurück, das die Zeichen folgen darstellt.</span><span class="sxs-lookup"><span data-stu-id="5de27-441">If the request returns JSON strings, `Invoke-RestMethod` returns a **PSObject** that represents the strings.</span></span>

## <span data-ttu-id="5de27-442">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="5de27-442">NOTES</span></span>

<span data-ttu-id="5de27-443">Einige Features sind möglicherweise nicht auf allen Plattformen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="5de27-443">Some features may not be available on all platforms.</span></span>

<span data-ttu-id="5de27-444">Aufgrund von Änderungen in .net Core 3,1 verwenden PowerShell 7,0 und höher die [HttpClient. defaultProxy](/dotnet/api/system.net.http.httpclient.defaultproxy?view=netcore-3.1) -Eigenschaft, um die Proxykonfiguration zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="5de27-444">Because of changes in .NET Core 3.1, PowerShell 7.0 and higher use the [HttpClient.DefaultProxy](/dotnet/api/system.net.http.httpclient.defaultproxy?view=netcore-3.1) Property to determine the proxy configuration.</span></span>

<span data-ttu-id="5de27-445">Der Wert dieser Eigenschaft ist abhängig von Ihrer Plattform von unterschiedlichen Regeln:</span><span class="sxs-lookup"><span data-stu-id="5de27-445">The value of this property is different rules depending on your platform:</span></span>

- <span data-ttu-id="5de27-446">**Für Windows**: liest die Proxykonfiguration aus den Umgebungsvariablen oder, wenn diese nicht definiert sind, aus den Proxy Einstellungen des Benutzers.</span><span class="sxs-lookup"><span data-stu-id="5de27-446">**For Windows**: Reads proxy configuration from environment variables or, if those are not defined, from the user's proxy settings.</span></span>
- <span data-ttu-id="5de27-447">**Für macOS**: liest die Proxykonfiguration aus den Umgebungsvariablen oder, wenn diese nicht definiert sind, aus den Proxy Einstellungen des Systems.</span><span class="sxs-lookup"><span data-stu-id="5de27-447">**For macOS**: Reads proxy configuration from environment variables or, if those are not defined, from the system's proxy settings.</span></span>
- <span data-ttu-id="5de27-448">**Für Linux**: liest die Proxykonfiguration aus Umgebungsvariablen, oder wenn diese nicht definiert sind, initialisiert diese Eigenschaft eine nicht konfigurierte Instanz, die alle Adressen umgeht.</span><span class="sxs-lookup"><span data-stu-id="5de27-448">**For Linux**: Reads proxy configuration from environment variables or, in case those are not defined, this property initializes a non-configured instance that bypasses all addresses.</span></span>

<span data-ttu-id="5de27-449">Die Umgebungsvariablen, die für die `DefaultProxy` Initialisierung auf Windows-und UNIX-basierten Plattformen verwendet werden, sind:</span><span class="sxs-lookup"><span data-stu-id="5de27-449">The environment variables used for `DefaultProxy` initialization on Windows and Unix-based platforms are:</span></span>

- <span data-ttu-id="5de27-450">` HTTP_PROXY`: der Hostname oder die IP-Adresse des Proxy Servers, der für HTTP-Anforderungen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="5de27-450">` HTTP_PROXY`: the hostname or IP address of the proxy server used on HTTP requests.</span></span>
- <span data-ttu-id="5de27-451">`HTTPS_PROXY`: der Hostname oder die IP-Adresse des Proxy Servers, der für HTTPS-Anforderungen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="5de27-451">`HTTPS_PROXY`: the hostname or IP address of the proxy server used on HTTPS requests.</span></span>
- <span data-ttu-id="5de27-452">`ALL_PROXY`: der Hostname oder die IP-Adresse des Proxy Servers, der für http-und HTTPS-Anforderungen verwendet wird, falls `HTTP_PROXY` oder `HTTPS_PROXY` nicht definiert sind.</span><span class="sxs-lookup"><span data-stu-id="5de27-452">`ALL_PROXY`: the hostname or IP address of the proxy server used on HTTP and HTTPS requests in case `HTTP_PROXY` or `HTTPS_PROXY` are not defined.</span></span>
- <span data-ttu-id="5de27-453">`NO_PROXY`: eine durch Trennzeichen getrennte Liste von Hostnamen, die von der Proxy Datei ausgeschlossen werden sollen.</span><span class="sxs-lookup"><span data-stu-id="5de27-453">`NO_PROXY`: a comma-separated list of hostnames that should be excluded from proxying.</span></span>

## <span data-ttu-id="5de27-454">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="5de27-454">RELATED LINKS</span></span>

[<span data-ttu-id="5de27-455">ConvertTo-Json</span><span class="sxs-lookup"><span data-stu-id="5de27-455">ConvertTo-Json</span></span>](ConvertTo-Json.md)

[<span data-ttu-id="5de27-456">ConvertFrom-Json</span><span class="sxs-lookup"><span data-stu-id="5de27-456">ConvertFrom-Json</span></span>](ConvertFrom-Json.md)

[<span data-ttu-id="5de27-457">Invoke-WebRequest</span><span class="sxs-lookup"><span data-stu-id="5de27-457">Invoke-WebRequest</span></span>](Invoke-WebRequest.md)