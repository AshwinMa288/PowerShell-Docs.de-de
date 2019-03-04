---
title: FirstLineIndent-Element für Frame für CustomControl für Ansicht (Format) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: bb4e1564-3fd3-4be3-b93e-ac90480e05c0
caps.latest.revision: 6
ms.openlocfilehash: 9ec6caedcb7cf20d4aab2216cd8a9707269d9452
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/03/2019
ms.locfileid: "56854956"
---
# <a name="firstlineindent-element-for-frame-for-customcontrol-for-view-format"></a>Element „FirstLineIndent“ für Frame für CustomControl für View (Format)

Gibt an, wie viele Zeichen, die die erste Zeile der Daten nach rechts verschoben wurde. Dieses Element wird verwendet, bei der Definition einer benutzerdefinierten anzuzeigen.

-Element (Format) ViewDefinitions-Element (Format) anzeigen (Format)-Element CustomControl-Element (Format) CustomEntries Konfigurationselement für CustomControl für Ansicht (Format) CustomEntry-Element für CustomEntries für Ansicht (Format) CustomItem-Element für CustomEntry für Frame-Element für CustomItem für CustomControl für Ansichtselement (Format) FirstLineIndent CutomControlView (Format)

## <a name="syntax"></a>Syntax

```xml
<FirstLineIndent>NumberOfCharactersToShift</FirstLineIndent>
```

## <a name="attributes-and-elements"></a>Attribute und Elemente

Den folgenden Abschnitten werden Attribute, untergeordnete Elemente und übergeordnete Element des Elements der `FirstLineIndent` Element.

### <a name="attributes"></a>Attributes

Keine.

### <a name="child-elements"></a>Untergeordnete Elemente

Keine.

### <a name="parent-elements"></a>Übergeordnete Elemente

|Element|Beschreibung|
|-------------|-----------------|
|[Frame-Element für CustomItem für CustomControl für Ansicht (Format)](./frame-element-for-customitem-for-customcontrol-for-view-format.md)|Definiert, wie die Daten angezeigt werden, z. B. das Verschieben von Daten nach links oder rechts.|

## <a name="text-value"></a>Textwert

Geben Sie die Anzahl der Zeichen, die die erste Zeile der Daten verschoben werden sollen.

## <a name="remarks"></a>Hinweise

Wenn dieses Element angegeben ist, Sie können nicht angeben, die [FirstLineHanging](./firstlinehanging-element-for-frame-for-customcontrol-for-view-format.md) Element.

## <a name="see-also"></a>Weitere Informationen

[FirstLineHanging-Element für Frame für CustomControl für Ansicht (Format)](./firstlinehanging-element-for-frame-for-customcontrol-for-view-format.md)

[Frame-Element für CustomItem für CustomControl für Ansicht (Format)](./frame-element-for-customitem-for-customcontrol-for-view-format.md)

[Schreiben Sie eine Formatierungsdatei PowerShell](./writing-a-powershell-formatting-file.md)