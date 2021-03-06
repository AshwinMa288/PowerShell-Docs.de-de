---
ms.date: 09/13/2016
ms.topic: reference
title: Erweitern von Ausgabeobjekten
description: Erweitern von Ausgabeobjekten
ms.openlocfilehash: 9fea476e3032002bd206609313581cc6373dfddc
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92652903"
---
# <a name="extending-output-objects"></a>Erweitern von Ausgabeobjekten

Sie können die .NET Framework Objekte, die von Cmdlets, Funktionen und Skripts zurückgegeben werden, mithilfe von Typen Dateien (. ps1xml) erweitern. Typen Dateien sind XML-basierte Dateien, mit denen Sie vorhandenen Objekten Eigenschaften und Methoden hinzufügen können. Windows PowerShell stellt z. b. die Types.ps1XML-Datei bereit, die mehreren vorhandenen .NET Framework Objekten Elemente hinzufügt. Die Types.ps1-XML-Datei befindet sich im Windows PowerShell-Installationsverzeichnis ( `$pshome` ). Sie können Ihre eigene Typen Datei erstellen, um diese Objekte weiter zu erweitern oder andere Objekte zu erweitern. Wenn Sie ein Objekt mithilfe einer Typen Datei erweitern, wird jede Instanz des Objekts mit den neuen Elementen erweitert.

## <a name="extending-the-systemarray-object"></a>Erweitern des System. Array-Objekts

Im folgenden Beispiel wird gezeigt, wie das [System. Array](/dotnet/api/System.Array) -Objekt in der Types.ps1-XML-Datei von Windows PowerShell erweitert wird. Standardmäßig verfügen [System. Array](/dotnet/api/System.Array) -Objekte über eine `Length` Eigenschaft, die die Anzahl der Objekte im Array auflistet. Da der Name "length" die Eigenschaft jedoch nicht eindeutig beschreibt, fügt Windows PowerShell die Alias- `Count` Eigenschaft hinzu, die denselben Wert wie die Eigenschaft anzeigt `Length` . Im folgenden XML-Code wird die- `Count` Eigenschaft dem [System. Array](/dotnet/api/System.Array) -Typ hinzugefügt.

```xml
<Type>
  <Name>System.Array</Name>
  <Members>
    <AliasProperty>
      <Name>Count</Name>
      <ReferencedMemberName>Length</ReferencedMemberName>
    </AliasProperty>
  </Members>
</Type>

```

Um diese neue Alias Eigenschaft anzuzeigen, verwenden [Sie einen Get-Member-](/powershell/module/Microsoft.PowerShell.Utility/Get-Member) Befehl für ein beliebiges Array, wie im folgenden Beispiel gezeigt.

```powershell
Get-Member -InputObject (1,2,3,4)
```

Der Befehl gibt die folgenden Ergebnisse zurück.

```output
Name           MemberType    Definition
----           ----------    ----------
Count          AliasProperty Count = Length
Address        Method        System.Object& Address(Int32 )
Clone          Method        System.Object Clone()
CopyTo         Method        System.Void CopyTo(Array array, Int32 index):
Equals         Method        System.Boolean Equals(Object obj)
Get            Method        System.Object Get(Int32 )
...
Length         Property      System.Int32 Length {get;}
```

Sie können entweder die- `Count` Eigenschaft oder die- `Length` Eigenschaft verwenden, um zu bestimmen, wie viele Objekte in einem Array sind. Zum Beispiel:

```powershell
PS> (1, 2, 3, 4).Count
```

```output
4
```

```powershell
PS> (1, 2, 3, 4).Length
```

```output
4
```

## <a name="custom-types-files"></a>Benutzerdefinierte Typen Dateien

Wenn Sie eine benutzerdefinierte Typen Datei erstellen möchten, kopieren Sie zunächst eine vorhandene Typen Datei. Die neue Datei kann einen beliebigen Namen haben, Sie muss jedoch über die Dateinamenerweiterung. ps1xml verfügen. Wenn Sie die Datei kopieren, können Sie die neue Datei in einem beliebigen Verzeichnis platzieren, das für Windows PowerShell zugänglich ist, aber es ist hilfreich, die Dateien im Windows PowerShell-Installationsverzeichnis ( `$pshome` ) oder in einem Unterverzeichnis des-Installationsverzeichnisses zu platzieren.

Fügen Sie für jedes Objekt, das Sie erweitern möchten, ein Types-Element hinzu, um der Datei eigene erweiterte Typen hinzuzufügen. In den folgenden Themen werden Beispiele bereitgestellt.

- Weitere Informationen zum Hinzufügen von Eigenschaften und Eigenschafts Sätzen finden Sie unter [Erweiterte Eigenschaften](./extending-properties-for-objects.md) .

- Weitere Informationen zum Hinzufügen von Methoden finden Sie unter [Erweiterte Methoden](./defining-default-methods-for-objects.md).

- Weitere Informationen zum Hinzufügen von Element Sätzen finden Sie unter [Erweiterte Element Sätze](./defining-default-member-sets-for-objects.md).

Nachdem Sie Ihre eigenen erweiterten Typen definiert haben, verwenden Sie eine der folgenden Methoden, um die erweiterten Objekte verfügbar zu machen:

- Verwenden Sie das [Update-typedata-](/powershell/module/Microsoft.PowerShell.Utility/Update-TypeData) Cmdlet, um die Datei mit erweiterten Typen für die aktuelle Sitzung verfügbar zu machen. Wenn Sie möchten, dass Ihre Typen Vorrang vor den Typen haben, die in anderen Typen Dateien (einschließlich der Types.ps1XML-Datei) definiert sind, verwenden Sie den- `PrependData` Parameter des [Update-typedata-](/powershell/module/Microsoft.PowerShell.Utility/Update-TypeData) Cmdlets.
- Um die Datei mit erweiterten Typen für alle zukünftigen Sitzungen verfügbar zu machen, fügen Sie die Typdatei einem Modul hinzu, exportieren die aktuelle Sitzung oder fügen den [Update-typedata-](/powershell/module/Microsoft.PowerShell.Utility/Update-TypeData) Befehl zu Ihrem Windows PowerShell-Profil hinzu.

## <a name="signing-types-files"></a>Signierungs Typen Dateien

Typen Dateien sollten digital signiert werden, um Manipulationen zu verhindern, da XML Skriptblöcke enthalten kann. Weitere Informationen zum Hinzufügen digitaler Signaturen finden Sie unter [about_Signing](/powershell/module/microsoft.powershell.core/about/about_signing)

## <a name="see-also"></a>Weitere Informationen

[Definieren von Standardeigenschaften für Objekte](./extending-properties-for-objects.md)

[Definieren von Standardmethoden für Objekte](./defining-default-methods-for-objects.md)

[Definieren von Standardelementgruppen für Objekte](./defining-default-member-sets-for-objects.md)

[Schreiben eines Windows PowerShell-Cmdlets](./writing-a-windows-powershell-cmdlet.md)
