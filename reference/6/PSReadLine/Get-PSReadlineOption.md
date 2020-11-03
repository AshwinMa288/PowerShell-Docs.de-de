---
external help file: Microsoft.PowerShell.PSReadLine2.dll-Help.xml
keywords: powershell,cmdlet
Locale: en-US
Module Name: PSReadLine
ms.date: 06/30/2020
online version: https://docs.microsoft.com/powershell/module/psreadline/get-psreadlineoption?view=powershell-6&WT.mc_id=ps-gethelp
schema: 2.0.0
title: Get-PSReadLineOption
ms.openlocfilehash: 624978c94c9ed24c07c6dad384236c852b8a7fde
ms.sourcegitcommit: 105c69ecedfe5180d8c12e8015d667c5f1a71579
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/02/2020
ms.locfileid: "93209661"
---
# <span data-ttu-id="a65f6-103">Get-PSReadLineOption</span><span class="sxs-lookup"><span data-stu-id="a65f6-103">Get-PSReadLineOption</span></span>

## <span data-ttu-id="a65f6-104">ZUSAMMENFASSUNG</span><span class="sxs-lookup"><span data-stu-id="a65f6-104">SYNOPSIS</span></span>
<span data-ttu-id="a65f6-105">Ruft Werte für die Optionen ab, die konfiguriert werden können.</span><span class="sxs-lookup"><span data-stu-id="a65f6-105">Gets values for the options that can be configured.</span></span>

## <span data-ttu-id="a65f6-106">SYNTAX</span><span class="sxs-lookup"><span data-stu-id="a65f6-106">SYNTAX</span></span>

```
Get-PSReadLineOption [<CommonParameters>]
```

## <span data-ttu-id="a65f6-107">DESCRIPTION</span><span class="sxs-lookup"><span data-stu-id="a65f6-107">DESCRIPTION</span></span>

<span data-ttu-id="a65f6-108">Das- `Get-PSReadLineOption` Cmdlet gibt den aktuellen Status der Einstellungen zurück, die mit dem `Set-PSReadLineOption` Cmdlet konfiguriert werden können.</span><span class="sxs-lookup"><span data-stu-id="a65f6-108">The `Get-PSReadLineOption` cmdlet returns the current state of the settings that can be configured by using the `Set-PSReadLineOption` cmdlet.</span></span> <span data-ttu-id="a65f6-109">Sie können das zurückgegebene-Objekt verwenden, um die **psread Line** -Optionen zu ändern.</span><span class="sxs-lookup"><span data-stu-id="a65f6-109">You can use the returned object to change **PSReadLine** options.</span></span> <span data-ttu-id="a65f6-110">Dies bietet eine etwas einfachere Möglichkeit zum Festlegen von Syntax Farboptionen für mehrere Arten von Token.</span><span class="sxs-lookup"><span data-stu-id="a65f6-110">This provides a slightly simpler way to set syntax coloring options for multiple kinds of tokens.</span></span>

## <span data-ttu-id="a65f6-111">BEISPIELE</span><span class="sxs-lookup"><span data-stu-id="a65f6-111">EXAMPLES</span></span>

### <span data-ttu-id="a65f6-112">Beispiel 1: erhalten von Optionen und deren Werten</span><span class="sxs-lookup"><span data-stu-id="a65f6-112">Example 1: Get options and their values</span></span>

```powershell
Get-PSReadLineOption
```

```Output
EditMode                               : Windows
AddToHistoryHandler                    :
HistoryNoDuplicates                    : True
HistorySavePath                        : C:\Users\username\AppData\Roaming\Microsoft\Windows\
                                         PowerShell\PSReadLine\ConsoleHost_history.txt
HistorySaveStyle                       : SaveIncrementally
HistorySearchCaseSensitive             : False
HistorySearchCursorMovesToEnd          : False
MaximumHistoryCount                    : 4096
ContinuationPrompt                     : >>
ExtraPromptLineCount                   : 0
PromptText                             : {> }
BellStyle                              : Audible
DingDuration                           : 50
DingTone                               : 1221
CommandsToValidateScriptBlockArguments : {ForEach-Object, %, Invoke-Command, icm...}
CommandValidationHandler               :
CompletionQueryItems                   : 100
MaximumKillRingCount                   : 10
ShowToolTips                           : True
ViModeIndicator                        : None
WordDelimiters                         : ;:,.[]{}()/\|^&*-=+'"---
AnsiEscapeTimeout                      : 100
CommandColor                           : "`e[93m"
CommentColor                           : "`e[32m"
ContinuationPromptColor                : "`e[97m"
DefaultTokenColor                      : "`e[97m"
EmphasisColor                          : "`e[96m"
ErrorColor                             : "`e[91m"
KeywordColor                           : "`e[92m"
MemberColor                            : "`e[97m"
NumberColor                            : "`e[97m"
OperatorColor                          : "`e[90m"
ParameterColor                         : "`e[90m"
SelectionColor                         : "`e[30;107m"
StringColor                            : "`e[36m"
TypeColor                              : "`e[37m"
VariableColor                          : "`e[92m"
```

<span data-ttu-id="a65f6-113">Mit diesem Befehl wird die Liste der verfügbaren psread Line-Optionen und ihre aktuellen Werte zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="a65f6-113">This command returns the list of available PSReadLine options and their current values.</span></span>

## <span data-ttu-id="a65f6-114">PARAMETERS</span><span class="sxs-lookup"><span data-stu-id="a65f6-114">PARAMETERS</span></span>

### <span data-ttu-id="a65f6-115">CommonParameters</span><span class="sxs-lookup"><span data-stu-id="a65f6-115">CommonParameters</span></span>

<span data-ttu-id="a65f6-116">Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable.</span><span class="sxs-lookup"><span data-stu-id="a65f6-116">This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable.</span></span> <span data-ttu-id="a65f6-117">Weitere Informationen findest du unter [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).</span><span class="sxs-lookup"><span data-stu-id="a65f6-117">For more information, see [about_CommonParameters](http://go.microsoft.com/fwlink/?LinkID=113216).</span></span>

## <span data-ttu-id="a65f6-118">EINGABEN</span><span class="sxs-lookup"><span data-stu-id="a65f6-118">INPUTS</span></span>

### <span data-ttu-id="a65f6-119">Keine</span><span class="sxs-lookup"><span data-stu-id="a65f6-119">None</span></span>

<span data-ttu-id="a65f6-120">Objekte können nicht an dieses Cmdlet weitergereicht werden.</span><span class="sxs-lookup"><span data-stu-id="a65f6-120">You cannot pipe objects to this cmdlet.</span></span>

## <span data-ttu-id="a65f6-121">AUSGABEN</span><span class="sxs-lookup"><span data-stu-id="a65f6-121">OUTPUTS</span></span>

### <span data-ttu-id="a65f6-122">Microsoft. PowerShell. psconsolereadlineoptions</span><span class="sxs-lookup"><span data-stu-id="a65f6-122">Microsoft.PowerShell.PSConsoleReadLineOptions</span></span>

<span data-ttu-id="a65f6-123">Eine Instanz der aktuellen Optionen.</span><span class="sxs-lookup"><span data-stu-id="a65f6-123">An instance of the current options.</span></span> <span data-ttu-id="a65f6-124">Wenn Sie die Eigenschaftswerte dieses Objekts ändern, werden die Einstellungen in psleline direkt aktualisiert, ohne dass aufgerufen wird `Set-PSReadLineOption` .</span><span class="sxs-lookup"><span data-stu-id="a65f6-124">Changing the property values of this object updates the settings in PSReadLine directly without invoking `Set-PSReadLineOption`.</span></span>

## <span data-ttu-id="a65f6-125">HINWEISE</span><span class="sxs-lookup"><span data-stu-id="a65f6-125">NOTES</span></span>

## <span data-ttu-id="a65f6-126">VERWANDTE LINKS</span><span class="sxs-lookup"><span data-stu-id="a65f6-126">RELATED LINKS</span></span>

[<span data-ttu-id="a65f6-127">Remove-psread linekeyhandler</span><span class="sxs-lookup"><span data-stu-id="a65f6-127">Remove-PSReadLineKeyHandler</span></span>](Remove-PSReadLineKeyHandler.md)

[<span data-ttu-id="a65f6-128">Get-psread linekeyhandler</span><span class="sxs-lookup"><span data-stu-id="a65f6-128">Get-PSReadLineKeyHandler</span></span>](Get-PSReadLineKeyHandler.md)

[<span data-ttu-id="a65f6-129">Set-psread lineoption</span><span class="sxs-lookup"><span data-stu-id="a65f6-129">Set-PSReadLineOption</span></span>](Set-PSReadLineOption.md)

[<span data-ttu-id="a65f6-130">Set-psread linekeyhandler</span><span class="sxs-lookup"><span data-stu-id="a65f6-130">Set-PSReadLineKeyHandler</span></span>](Set-PSReadLineKeyHandler.md)