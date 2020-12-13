---
ms.date: 09/13/2016
ms.topic: reference
title: Element „TableColumnHeader“ (Format)
description: Element „TableColumnHeader“ (Format)
ms.openlocfilehash: 30368512875b7c5c4cf3c686f3d09540dea1bd26
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92651528"
---
# <a name="tablecolumnheader-element-format"></a>Element „TableColumnHeader“ (Format)

Definiert die Bezeichnung, die Breite der Spalte und die Ausrichtung der Bezeichnung für eine Spalte der Tabelle.

Configuration-Element (Format) viewdefinitions-Element (Format) View-Element (Format) tablecontrol-Element (Format) tableHeaders-Element für tablecontrol (Format) tablecolumnheader-Element für tableHeaders für tablecontrol (Format)

## <a name="syntax"></a>Syntax

```xml
<TableColumnHeader>
  <Label>DisplayedLabel</Label>
  <Width>NumberOfCharacters</Width>
  <Alignment>Left, Right, or Centered</Alignment>
</TableColumnHeader>
```

## <a name="attributes-and-elements"></a>Attribute und Elemente

In den folgenden Abschnitten werden Attribute, untergeordnete Elemente und das übergeordnete Element des- `TableColumnHeader` Elements beschrieben.

### <a name="attributes"></a>Attribute

Keine

### <a name="child-elements"></a>Untergeordnete Elemente

|Element|Beschreibung|
|-------------|-----------------|
|[Label-Element für tablecolumnheader für tablecontrol (Format)](./label-element-for-tablecolumnheader-for-tablecontrol-format.md)|Optionales Element.<br /><br /> Definiert die Bezeichnung, die am oberen Rand der Spalte angezeigt wird. Wenn keine Bezeichnung angegeben ist, wird der Name der Eigenschaft verwendet, deren Wert in den Zeilen angezeigt wird.|
|[Element „Width“ für TableColumnHeader für TableControl (Format)](./width-element-for-tablecolumnheader-for-tablecontrol-format.md)|Erforderliches Element.<br /><br /> Gibt die Breite (in Zeichen) der Spalte an.|
|[Element „Alignment“ für TableColumnHeader für TableControl (Format)](./alignment-element-for-tablecolumnheader-for-tablecontrol-format.md)|Optionales Element.<br /><br /> Gibt an, wie die Bezeichnung der Spalte angezeigt wird. Wenn keine Ausrichtung angegeben wird, wird die Bezeichnung linksbündig ausgerichtet.|

### <a name="parent-elements"></a>Übergeordnete Elemente

|Element|Beschreibung|
|-------------|-----------------|
|[Element „TableHeaders“ (Format)](./tableheaders-element-format.md)|Definiert die Spalten einer Tabellen Sicht.|

## <a name="remarks"></a>Bemerkungen

Geben Sie einen Header für jede Spalte der Tabelle an. Die Spalten werden in der Reihenfolge angezeigt, in der die `TableColumnHeader` Elemente definiert sind.

Eine Tabelle muss die gleiche Anzahl von `TableColumnHeader` Elementen wie- `TableRowEntry` Elemente aufweisen. Der Spaltenheader definiert, wie der Text oben in der Tabelle angezeigt wird. Die Zeilen Einträge definieren, welche Daten in den Zeilen der Tabelle angezeigt werden.

Weitere Informationen zu den Komponenten einer Tabellenansicht finden Sie unter [Tabellen Sicht](./creating-a-table-view.md).

## <a name="example"></a>Beispiel

Das folgende Beispiel zeigt zwei- `TableColumnHeader` Elemente. Das erste Element definiert eine Spalte, deren Bezeichnung "Column 1" ist, eine Breite von 16 Zeichen hat und deren Bezeichnung linksbündig ausgerichtet ist. Das zweite Element definiert eine Spalte, deren Bezeichnung "Column 2" ist, eine Breite von 10 Zeichen aufweist und deren Bezeichnung in der Spalte zentriert ist.

```xml
<TableHeaders>
  <TableColumnHeader>
    <Label>Column 1</Label)
    <Width>16</Width>
    <Alignment>Left</Alignment>
  </TableColumnHeader>
    <TableColumnHeader>
    <Label>Column 2</Label)
    <Width>10</Width>
    <Alignment>Centered</Alignment>
  </TableColumnHeader>
</TableHeaders>
```

## <a name="see-also"></a>Weitere Informationen

[Element „Alignment“ für TableColumnHeader für TableControl (Format)](./alignment-element-for-tablecolumnheader-for-tablecontrol-format.md)

[Erstellen einer Tabellenansicht](./creating-a-table-view.md)

[Element „Label“ für TableColumnHeader für TableControl (Format)](./label-element-for-tablecolumnheader-for-tablecontrol-format.md)

[TableHeaders-Element für tablecontrol (Format)](./tableheaders-element-format.md)

[Breite für tablecolumnheader für tablecontrol-Element (Format)](./width-element-for-tablecolumnheader-for-tablecontrol-format.md)

[Schreiben einer PowerShell-Formatierungsdatei](./writing-a-powershell-formatting-file.md)
