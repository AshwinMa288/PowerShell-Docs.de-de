---
ms.date: 07/16/2020
keywords: DSC,PowerShell,Konfiguration,Setup,Einrichtung
title: DSC-Ressourcen „Archive“
ms.openlocfilehash: cbe32012c2035fb3e145bd06fadd73cdba93fd3e
ms.sourcegitcommit: 41e1acbd9ce0f49a23c6eb99facd2c280d836836
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/18/2020
ms.locfileid: "86463787"
---
# <a name="dsc-archive-resource"></a>DSC-Ressourcen „Archive“

> Gilt für: Windows PowerShell 4.0, Windows PowerShell 5.x

Die Ressource „Archive“ in Windows PowerShell DSC bietet einen Mechanismus zum Entpacken von Archivdateien (.zip).

## <a name="syntax"></a>Syntax

```Syntax
Archive [string] #ResourceName
{
    Destination = [string]
    Path = [string]
    [ Checksum = [string] { CreatedDate | ModifiedDate | SHA-1 | SHA-256 | SHA-512 } ]
    [ Credential = [PSCredential] ]
    [ Force = [bool] ]
    [ Validate = [bool] ]
    [ Ensure = [string] { Absent | Present } ]
    [ DependsOn = [string[]] ]
    [ PsDscRunAsCredential = [PSCredential] ]
}
```

## <a name="properties"></a>Eigenschaften

|Eigenschaft |BESCHREIBUNG |
|---|---|
| Destination | Gibt den Speicherort an, an dem der Archivinhalt einer Datei extrahiert werden soll. |
| `Path` | Gibt den Quellpfad der Archivdatei an. |
| Checksum | Definiert den zu verwendenden Typ, wenn bestimmt wird, ob zwei Dateien identisch sind. Wenn **Checksum** nicht angegeben ist, wird nur der Datei- oder Verzeichnisnamen für den Vergleich verwendet. Gültige Werte: **SHA-1**, **SHA-256**, **SHA-512**, **createdDate**, **modifiedDate**. Wenn Sie **Checksum** ohne **Validate** angeben, schlägt die Konfiguration fehl. |
| Anmeldeinformationen | Die Anmeldeinformationen eines Benutzerkontos mit Zugriffsberechtigung (falls erforderlich) auf den angegebenen Archivpfad und das angegebene Ziel. |
| Force | Bestimmte Dateioperationen (z. B. das Überschreiben einer Datei oder Löschen eines Verzeichnisses, das nicht leer ist), führen zu einem Fehler. Bei Verwenden der **Force**-Eigenschaft werden solche Fehler überschrieben. Der Standardwert ist **False**. |
| Überprüfen| Verwendet die Eigenschaft **Checksum**, um zu bestimmen, ob das Archiv der Signatur entspricht. Wenn Sie **Checksum** ohne **Validate** angeben, schlägt die Konfiguration fehl. Wenn Sie **Validate** ohne **Checksum** angeben, wird standardmäßig eine _SHA-256-_ **Prüfsumme** verwendet. |

## <a name="common-properties"></a>Allgemeine Eigenschaften

|Eigenschaft |BESCHREIBUNG |
|---|---|
|DependsOn |Gibt an, dass die Konfiguration einer anderen Ressource ausgeführt werden muss, bevor diese Ressource konfiguriert wird. Wenn beispielsweise die ID des Skriptblocks mit der Ressourcenkonfiguration, den Sie zuerst ausführen möchten, „ResourceName“ und dessen Typ „ResourceType“ ist, lautet die Syntax für das Verwenden dieser Eigenschaft `DependsOn = "[ResourceType]ResourceName"`. |
|Ensure |Bestimmt, ob geprüft wird, ob der Inhalt der Archivdatei am **Ziel** vorhanden ist. Legen Sie diese Eigenschaft auf **Present** fest, um sicherzustellen, dass der Inhalt vorhanden ist. Legen Sie sie auf **Absent** fest, um sicherzustellen, dass der Inhalt nicht vorhanden ist. Der Standardwert ist **Present**. |
|PsDscRunAsCredential |Legt die Anmeldeinformationen für die Ausführung der gesamten Ressource fest. |

> [!NOTE]
> Die allgemeine Eigenschaft **PsDscRunAsCredential** wurde in WMF 5.0 hinzugefügt, um das Ausführen einer beliebigen DSC-Ressource in Verbindung mit anderen Anmeldeinformationen zu ermöglichen. Weitere Informationen finden Sie unter [Use Credentials with DSC Resources](../../../configurations/runasuser.md) (Verwenden von Anmeldeinformationen mit DSC-Ressourcen).

## <a name="example"></a>Beispiel

Im folgenden Beispiel wird veranschaulicht, wie Sie die Ressource „Archive“ verwenden, um sicherzustellen, dass der Inhalt einer Archivdatei mit dem Namen `Test.zip` vorhanden ist und an einem bestimmten Zielspeicherort extrahiert, verwendet und autorisiert wird.

```powershell
Archive ArchiveExample {
    Ensure = "Present"
    Path = "C:\Users\Public\Documents\Test.zip"
    Destination = "C:\Users\Public\Documents\ExtractionPath"
}
```
