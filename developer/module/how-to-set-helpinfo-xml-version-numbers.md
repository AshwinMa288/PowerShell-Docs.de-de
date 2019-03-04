---
title: Festlegen der HelpInfo-XML-Versionsnummern | Microsoft-Dokumentation
ms.custom: ''
ms.date: 09/12/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 93a00463-af58-41c8-b088-450909fa1d05
caps.latest.revision: 6
ms.openlocfilehash: 4929a5b1c9f73bb12b6df975e03fc529db3565ef
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/03/2019
ms.locfileid: "56863316"
---
# <a name="how-to-set-helpinfo-xml-version-numbers"></a>Festlegen von XML-Versionsnummern für HelpInfo

In diesem Thema wird erläutert, wie Sie festlegen, und erhöhen die Versionsnummern in einer aktualisierbaren Hilfe-Informationen-Datei, die häufig als "HelpInfo XML-Datei." bezeichnet.

## <a name="how-to-set-helpinfo-xml-version-numbers"></a>Festlegen von XML-Versionsnummern für HelpInfo

Die Versionsnummern in einer HelpInfo XML-Datei sind entscheidend für die Verwendung der aktualisierbaren Hilfe. Die [Update-Help](/powershell/module/Microsoft.PowerShell.Core/Update-Help) und [Save-Help](/powershell/module/Microsoft.PowerShell.Core/Update-Help) Cmdlets Herunterladen neuer Hilfedateien nur, wenn die Versionsnummer für eine UI-Kultur in der remote HelpInfo-XML-Datendatei größer als die Versionsnummer für die jeweilige UI-Kultur in ist die lokale HelpInfo XML, oder es ist keine lokale HelpInfo XML-Datei.
Die Versionsnummern in einer HelpInfo XML-Datei sind entscheidend für die Verwendung der aktualisierbaren Hilfe. Die [Update-Help](/powershell/module/Microsoft.PowerShell.Core/Update-Help) und [Save-Help](/powershell/module/Microsoft.PowerShell.Core/Update-Help) Cmdlets Herunterladen neuer Hilfedateien nur, wenn die Versionsnummer für eine UI-Kultur in der remote HelpInfo-XML-Datendatei größer als die Versionsnummer für die jeweilige UI-Kultur in ist die lokale HelpInfo XML, oder es ist keine lokale HelpInfo XML-Datei.

Die HelpInfo XML-Datei verwendet, die 4-Teil Versionsnummer, die in definiert ist die **System.Version** Klasse von Microsoft .NET Framework. Das Format ist `N1.N2.N3.N4`. Modulautoren können eine beliebige Version Nummerierungsschema, die zulässig ist die **System.Version** Klasse. Aktualisierbare Hilfe erfordert nur, dass die Versionsnummer für eine Erhöhung des UI-Kultur, wenn eine neue Version der CAB-Datei für diese Benutzeroberflächenkultur an den Speicherort hochgeladen wird, die angegeben wird die **HelpContentURI** Element in der HelpInfo XML-Datei.

Das folgende Beispiel zeigt die Elemente der HelpInfo XML-Datei für Deutsch (de-DE) Benutzeroberfläche Kultur, wenn die Version 2.15.0.10 ist.

```xml

<UICulture>
  <UICultureName>de-DE</UICultureName>
  <UICultureVersion>2.15.0.10</UICultureVersion>
</UICulture>
```

Die Versionsnummer für eine Benutzeroberflächenkultur gibt die Version der CAB-Datei für die jeweilige UI-Kultur wieder. Die Versionsnummer, die auf die gesamte CAB-Datei angewendet wird. Sie können nicht unterschiedliche Versionsnummern für verschiedene Dateien in die CAB-Datei festlegen. Die Versionsnummer für jede Benutzeroberflächenkultur unabhängig ausgewertet, und es muss keine Beziehung zu den Versionsnummern für andere UI-Kulturen, die das Modul unterstützt.