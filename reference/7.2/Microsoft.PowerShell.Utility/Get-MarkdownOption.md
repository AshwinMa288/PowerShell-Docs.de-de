---
external help file: Microsoft.PowerShell.Commands.Utility.dll-Help.xml
Module Name: Microsoft.PowerShell.Utility
ms.date: 01/30/2020
online version: https://docs.microsoft.com/powershell/module/Microsoft.PowerShell.Utility/Get-MarkdownOption?view=powershell-7.x.0&WT.mc_id=ps-gethelp
schema: 2.0.0
ms.openlocfilehash: 775b11db79b9ca8290864b757e5cd1a0615f89e4
ms.sourcegitcommit: 95d41698c7a2450eeb70ef2fb6507fe7e6eff3b6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "99596963"
---
# Get-MarkdownOption

## ZUSAMMENFASSUNG
Gibt die aktuellen Farben und Stile zurück, die zum Rendern von markdown-Inhalten in der Konsole verwendet werden.

## SYNTAX

```
Get-MarkdownOption [<CommonParameters>]
```

## DESCRIPTION

Gibt die aktuellen Farben und Stile zurück, die zum Rendern von markdown-Inhalten in der Konsole verwendet werden. Die Zeichen folgen, die in der Ausgabe dieses Cmdlets angezeigt werden, enthalten die ANSI-Escapecodes, die verwendet werden, um die Farbe und den Stil des Renderings zu ändern.

Weitere Informationen zu markdown finden Sie auf der [commonmark](https://commonmark.org/) -Website.

## BEISPIELE

### Beispiel 1: erhalten der aktuellen Farben und des Stils

```powershell
Get-MarkdownOption
```

```Output
Header1         : [7m
Header2         : [4;93m
Header3         : [4;94m
Header4         : [4;95m
Header5         : [4;96m
Header6         : [4;97m
Code            : [48;2;155;155;155;38;2;30;30;30m
Link            : [4;38;5;117m
Image           : [33m
EmphasisBold    : [1m
EmphasisItalics : [36m
```

> [!NOTE]
> Die in der Ausgabe angezeigten Zeichen folgen Werte sind die Zeichen **, die auf** das Escapezeichen ( `[char]0x1B` ) für die ANSI-Escapesequenz folgen. Weitere Informationen zu ANSI-Escapecodes finden Sie unter [ANSI_escape_code](https://en.wikipedia.org/wiki/ANSI_escape_code).

## PARAMETERS

### CommonParameters

Dieses Cmdlet unterstützt diese gängigen Parameter: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction und -WarningVariable. Weitere Informationen findest du unter [about_CommonParameters](https://go.microsoft.com/fwlink/?LinkID=113216).

## EINGABEN

### Keine

## AUSGABEN

### Microsoft. PowerShell. markdownrendering. psmarkdownoptioninfo

## HINWEISE

## VERWANDTE LINKS

[Set-MarkdownOption](Set-MarkdownOption.md)

[ConvertFrom-Markdown](ConvertFrom-Markdown.md)

[Show-Markdown](Show-Markdown.md)

[ANSI_escape_code](https://en.wikipedia.org/wiki/ANSI_escape_code)

[CommonMark](https://commonmark.org/)

