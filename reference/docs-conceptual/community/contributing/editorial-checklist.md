---
title: Checkliste für die Bearbeitung
description: Dies ist eine zusammengefasste Liste mit Regeln für die Bearbeitung der PowerShell-Dokumentation.
ms.date: 03/05/2020
ms.topic: conceptual
ms.openlocfilehash: b5baf7366239084779d34e23f218e5e6222ed1a3
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "81624736"
---
# <a name="editors-checklist"></a>Checkliste für die Bearbeitung

Dies ist eine Zusammenfassung der Regeln, die beim Schreiben neuer oder Aktualisieren bestehender Artikel gelten. Ausführliche Erläuterungen und Beispiele zu diesen Regeln finden Sie in anderen Artikeln des Leitfadens für Mitwirkende.

## <a name="metadata"></a>Metadaten

- `ms.date`: muss das Format **MM/TT/JJJJ** haben
  - Datum ändern, sobald eine signifikante oder sachliche Aktualisierung vorliegt
    - Neuorganisieren des Artikels
    - Beheben sachlicher Fehler
    - Hinzufügen neuer Informationen
  - Das Datum nicht ändern, wenn die Aktualisierung unerheblich ist
    - Korrigieren von Rechtschreibfehlern und Formatierung
- `title`: eindeutige Zeichenfolge mit 43-59 Zeichen einschließlich Leerzeichen
  - Standortbezeichner nicht einschließen (wird automatisch generiert)
  - Nur ersten Buchstaben des Satzes und von Eigennamen großschreiben
- `description`: 115-145 Zeichen einschließlich Leerzeichen. Diese Zusammenfassung wird im Suchergebnis angezeigt.

## <a name="formatting"></a>Formatierung

- Elemente, die inline in einem Absatz angezeigt werden, in Hochkommas setzen
  - Cmdlet-Namen: `Verb-Noun`
  - Variable: `$counter`
  - Syntaktische Beispiele: `Verb-Noun -Parameter`
  - Dateipfade: `C:\Program Files\PowerShell`, `/usr/bin/pwsh`
  - URLs, auf die im Dokument nicht geklickt werden soll
  - Eigenschafts- oder Parameterwerte
- Formatieren Sie Eigenschaftsnamen, Parameternamen, Klassennamen, Modulnamen, Entitätsnamen sowie Objekt- oder Typnamen fett
  - Fett wird für semantisches Markup verwendet, nicht zur Betonung
  - Fett: Sternchen `**`
- Kursiv: Unterstrich `_`
  - Wird nur zur Betonung verwendet, nicht für semantisches Markup
- Zeilenumbrüche bei 100 Spalten (oder 80 für **about_Topics**)
- Keine harten Tabstoppzeichen, nur Leerzeichen verwenden
- Nachgestellte Leerzeichen in Zeilen

### <a name="headers"></a>Header

- H1 als Erstes. Nur ein H1 pro Artikel
- Nur [ATX-Header](https://github.github.com/gfm/#atx-headings) verwenden
- Ersten Buchstaben in allen Headern großschreiben
- Keine Ebenen überspringen: kein H3 ohne H2
- Maximale Tiefe von H3 oder H4
- Leerzeile davor und dahinter
- PlatyPS erzwingt bestimmte Header in seinem Schema. Keine Header hinzufügen oder entfernen

### <a name="code-blocks"></a>Codeblöcke

- Leerzeile davor und dahinter
- Codeumgrenzungen in Form von Tags verwenden: **PowerShell**, **Ausgabe** oder andere geeignete Sprach-ID
- Umgrenzung ohne Tags: Syntaxblöcke oder andere Shells
- Platzieren Sie die Ausgabe in einem separaten Codeblock (mit Ausnahme von einfachen Beispielen, bei denen Sie nicht beabsichtigen, dass der Leser auf die Schaltfläche **Kopieren** klickt)
- Siehe die Liste der [unterstützten Sprachen](/contribute/code-in-docs#supported-languages)

### <a name="lists"></a>Listen

- Ordnungsgemäß eingerückt
- Leerzeile vor dem ersten und hinter dem letzten Element
- Aufzählungszeichen: Bindestrich (`-`) verwenden, keine Sternchen (`*`) –zu leicht mit Betonung zu verwechseln
- Bei nummerierten Listen lauten alle Zahlen „1“.

## <a name="terminology"></a>Begriff

- PowerShell verglichen mit Windows PowerShell verglichen mit PowerShell Core
- Siehe [Produktterminologie](powershell-style-guide.md#product-terminology)

## <a name="cmdlet-reference-examples"></a>Cmdlet-Referenz: Beispiele

- Mindestens ein Beispiel muss in der Cmdlet-Referenz vorhanden sein.
- Beispiele sollten gerade nur so viel Code enthalten, um die Verwendung zu veranschaulichen.
- PowerShell-Syntax
  - Vollständige Namen von Cmdlets und Parametern verwenden – keine Aliase
  - Aufteilung von Parametern verwenden, wenn die Befehlszeile zu lang wird
  - Hochkommas zur Zeilenfortsetzung vermeiden, nur bei Bedarf verwenden
- Die PowerShell-Eingabeaufforderung (`PS>`) entfernen oder vereinfachen, außer wenn für das Beispiel erforderlich
- Das Cmdlet-Referenzbeispiel muss dem folgenden PlatyPS-Schema folgen

  ~~~Markdown
  ### Example 1 - Descriptive title

  Zero or more short descriptive paragraphs explaining the context of the example followed by one or
  more code blocks. Recommend at least one and no more than two.

  ```powershell
  ... one or more PowerShell code statements ...
  ```

  ```Output
  Example output of the code above.
  ```

  Zero or more optional follow up paragraphs that explain the details of the code and output.
  ~~~

- Setzen Sie keine Absätze zwischen die Codeblöcke. Der gesamte beschreibende Inhalt muss vor oder hinter den Codeblöcken stehen.

## <a name="linking-to-other-documents"></a>Verknüpfen mit anderen Dokumenten

- Verknüpfung außerhalb des Docsets oder zwischen Cmdlet-Referenz und konzeptuellen Inhalten
  - Relative URLs beim Verknüpfen mit docs.microsoft.com verwenden (`https://docs.microsoft.com/en-us` entfernen)
  - Schließen Sie keine Gebietsschemas in URLs in Microsoft-Eigenschaften ein (entfernen Sie beispielsweise `/en-us` aus dem URL)
  - Alle URLs zu externen Websites müssen HTTPS verwenden, es sei denn, dies gilt nicht für die Zielwebsite
- Innerhalb des Docsets
  - Link zu Dateipfad (z. B. `../folder/file.md`)
  - Alle Dateipfade enthalten Schrägstriche (`/`).
- Bildlinks müssen eindeutigen alternativen Text enthalten.
