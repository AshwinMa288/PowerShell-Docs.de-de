---
ms.date: 09/13/2016
ms.topic: reference
title: Element „Name“ für SelectionSet (Format)
description: Element „Name“ für SelectionSet (Format)
ms.openlocfilehash: 98c13be6ea352055231fbdb3a60f0eb508f661b8
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92666456"
---
# <a name="name-element-for-selectionset-format"></a>Element „Name“ für SelectionSet (Format)

Gibt den Namen an, mit dem auf den Auswahl Satz verwiesen wird.

Configuration-Element (Format) selectionsets-Element (Format) SelectionSet-Element (Format) Name-Element von SelectionSet (Format)

## <a name="syntax"></a>Syntax

```xml
<Name>Name of selection set</Name>
```

## <a name="attributes-and-elements"></a>Attribute und Elemente

In den folgenden Abschnitten werden die Attribute, die untergeordneten Elemente und das übergeordnete Element des- `Name` Elements beschrieben.

### <a name="attributes"></a>Attribute

Keine

### <a name="child-elements"></a>Untergeordnete Elemente

Keine

### <a name="parent-elements"></a>Übergeordnete Elemente

|Element|Beschreibung|
|-------------|-----------------|
|[Element „SelectionSet“ (Format)](./selectionset-element-format.md)|Definiert einen einzelnen Satz von .NET-Objekten, auf die durch den Namen des Satzes verwiesen werden kann.|

## <a name="text-value"></a>Textwert

Geben Sie den Namen an, der auf den Auswahl Satz verweist. Es gibt keine Einschränkungen, welche Zeichen verwendet werden können.

## <a name="remarks"></a>Bemerkungen

Der hier angegebene Name wird im- `SelectionSetName` Element verwendet. Der Auswahl Satz, der von einer Ansicht verwendet werden kann, durch eine Definition einer Ansicht (Ansichten können mehrere Definitionen aufweisen) oder durch Angeben einer Auswahlbedingung. Weitere Informationen zu Auswahl Sätzen finden Sie unter [Definieren von Objekt Sätzen](./defining-selection-sets.md).

## <a name="example"></a>Beispiel

Dieses Beispiel zeigt ein- `SelectionSet` Element, das vier .NET-Typen definiert. Der Name des Auswahl Satzes lautet "filesystemtypes".

```xml
<SelectionSets>
  <SelectionSet>
    <Name>FileSystemTypes</Name>
    <Types>
     <TypeName>System.IO.DirectoryInfo</TypeName>
     <TypeName>System.IO.FileInfo</TypeName>
     <TypeName>Deserialized.System.IO.DirectoryInfo</TypeName>
     <TypeName>Deserialized.System.IO.FileInfo</TypeName>
    </Types>
  </SelectionSet>
</SelectionSets>
```

## <a name="see-also"></a>Weitere Informationen

[Definieren von Auswahlgruppen](./defining-selection-sets.md)

[Element „SelectionSet“ (Format)](./selectionset-element-format.md)

[Schreiben einer PowerShell-Formatierungsdatei](./writing-a-powershell-formatting-file.md)
