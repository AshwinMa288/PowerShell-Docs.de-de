---
title: Firstlinehanging-Element für Frame für CustomControl für Ansicht (Format) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c6ac3d86-0529-4b93-9bc7-ee94fcef9618
caps.latest.revision: 8
ms.openlocfilehash: ea43e025f5f653ff000e1d7591b535e73da5c9e5
ms.sourcegitcommit: 52a67bcd9d7bf3e8600ea4302d1fa8970ff9c998
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/15/2019
ms.locfileid: "72363159"
---
# <a name="firstlinehanging-element-for-frame-for-customcontrol-for-view-format"></a>Element „FirstLineHanging“ für Frame für CustomControl für View (Format)

Gibt an, wie viele Zeichen die erste Zeile der Daten nach links verschoben wird. Dieses Element wird beim Definieren einer benutzerdefinierten Steuerelement Ansicht verwendet.

Configuration-Element (Format) viewdefinitions-Element (Format) View-Element (Format) CustomControl-Element (Format) customentries-Element für CustomControl für View (Format) customentry-Element für customentries für View (Format) customItem-Element für Customentry für customcontrolview (Format) Frame-Element für customItem für CustomControl für View (Format) firstlinehanging-Element für Frame für CustomControl für Ansicht (Format)

## <a name="syntax"></a>Syntax

```xml
<FirstLineHanging>NumberOfCharactersToShift</FirstLineHanging>
```

## <a name="attributes-and-elements"></a>Attribute und Elemente

In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und das übergeordnete Element des `FirstLineHanging`-Elements beschrieben.

### <a name="attributes"></a>Attributes

Keine.

### <a name="child-elements"></a>Untergeordnete Elemente

Keine.

### <a name="parent-elements"></a>Übergeordnete Elemente

|Element|Description|
|-------------|-----------------|
|[Frame-Element für customItem für CustomControl für Ansicht (Format)](./frame-element-for-customitem-for-customcontrol-for-view-format.md)|Definiert, wie die Daten angezeigt werden, z. b. das Verschieben der Daten nach links oder rechts.|

## <a name="text-value"></a>Textwert

Geben Sie die Anzahl der Zeichen an, die Sie in die erste Zeile der Daten verschieben möchten.

## <a name="remarks"></a>Hinweise

Wenn dieses Element angegeben ist, können Sie das [firstlineingedent](./firstlineindent-element-for-frame-for-customcontrol-for-view-format.md) -Element nicht angeben.

## <a name="see-also"></a>Weitere Informationen

[FirstLineIndent-Element für Frame für CustomControl für Ansicht (Format)](./firstlineindent-element-for-frame-for-customcontrol-for-view-format.md)

[Frame-Element für customItem für CustomControl für Ansicht (Format)](./frame-element-for-customitem-for-customcontrol-for-view-format.md)

[Schreiben einer PowerShell-Formatierungs Datei](./writing-a-powershell-formatting-file.md)