---
title: Erstellen eines Windows PowerShell-Anbieters | Microsoft-Dokumentation
ms.date: 09/13/2016
helpviewer_keywords:
- providers [PowerShell Programmer's Guide]
- providers [PowerShellProgrammer's Guide], creating
- Windows PowerShell Programmer's Guide, providers
ms.openlocfilehash: 5e7424c035d22d0f5eb154b369427a6da80b1c49
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87787103"
---
# <a name="how-to-create-a-windows-powershell-provider"></a>Erstellen eines Windows PowerShell-Anbieters

In diesem Abschnitt wird beschrieben, wie Sie einen Windows PowerShell-Anbieter erstellen. Ein Windows PowerShell-Anbieter kann auf zwei Arten berücksichtigt werden. Für den Benutzer stellt der Anbieter einen Satz gespeicherter Daten dar. Die gespeicherten Daten können z. b. die Internetinformationsdienste (IIS) Metabase, die Microsoft Windows-Registrierung, das Windows-Dateisystem, Active Directory und die von Windows PowerShell gespeicherten Variablen-und Alias Daten sein.

Für den Entwickler ist der Windows PowerShell-Anbieter die Schnittstelle zwischen dem Benutzer und den Daten, auf die der Benutzer zugreifen muss. Aus dieser Perspektive unterstützt jeder in diesem Abschnitt beschriebene Anbietertyp eine Reihe spezifischer Basisklassen und Schnittstellen, mit denen die Windows PowerShell-Laufzeit bestimmte Cmdlets auf gängige Weise für den Benutzer verfügbar machen kann.

## <a name="providers-provided-by-windows-powershell"></a>Von Windows PowerShell bereitgestellte Anbieter

Windows PowerShell stellt mehrere Anbieter (z. b. den File System-Anbieter, Registrierungs Anbieter und Alias Anbieter) bereit, die für den Zugriff auf bekannte Datenspeicher verwendet werden. Weitere Informationen zu den von Windows PowerShell bereitgestellten Anbietern erhalten Sie, indem Sie den folgenden Befehl verwenden, um auf die Online Hilfe zuzugreifen:

**PS>Get-Help about_Providers**

## <a name="accessing-the-stored-data-using-windows-powershell-paths"></a>Zugreifen auf die gespeicherten Daten mithilfe von Windows PowerShell-Pfaden

Windows PowerShell-Anbieter sind für die Windows PowerShell-Laufzeit und Befehle Programm gesteuert durch die Verwendung von Windows PowerShell-Pfaden zugänglich. In den meisten Fällen werden diese Pfade verwendet, um direkt über den Anbieter auf die Daten zuzugreifen. Einige Pfade können jedoch in Anbieter interne Pfade aufgelöst werden, die einem Cmdlet die Verwendung von nicht-Windows PowerShell-APIs (Application Programming Interface) für den Zugriff auf die Daten ermöglichen. Weitere Informationen zur Funktionsweise von Windows PowerShell-Anbietern in Windows PowerShell finden Sie unter [Funktionsweise](/previous-versions/ms714658(v=vs.85))von Windows PowerShell.

## <a name="exposing-provider-cmdlets-using-windows-powershell-drives"></a>Verfügbar machen von Anbieter-Cmdlets mit Windows PowerShell-Laufwerken

Ein Windows PowerShell-Anbieter stellt mithilfe virtueller Windows PowerShell-Laufwerke seine unterstützten Cmdlets zur Verfügung.
Windows PowerShell wendet die folgenden Regeln für ein Windows PowerShell-Laufwerk an:

- Der Name eines Laufwerks kann eine beliebige alphanumerische Sequenz sein.
- Ein Laufwerk kann an einem beliebigen gültigen Punkt auf einem Pfad angegeben werden, der als "root" bezeichnet wird.
- Ein Laufwerk kann für alle gespeicherten Daten implementiert werden, nicht nur für das Dateisystem.
- Jedes Laufwerk behält seinen eigenen aktuellen Arbeits Speicherort bei, sodass der Benutzer beim Wechseln zwischen den Laufwerken den Kontext beibehalten kann.

## <a name="in-this-section"></a>In diesem Abschnitt

In der folgenden Tabelle sind Themen aufgeführt, die Codebeispiele enthalten, die aufeinander aufbauen. Beginnend mit dem zweiten Thema kann der grundlegende Windows PowerShell-Anbieter von der Windows PowerShell-Laufzeit initialisiert und nicht initialisiert werden. im nächsten Thema werden Funktionen für den Datenzugriff hinzugefügt. das nächste Thema bietet Funktionen zum Bearbeiten der Daten (die Elemente in den gespeicherten Daten) usw.

|                                                    Thema                                                    |                                                                                         Definition                                                                                          |
| ----------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [Entwerfen eines Windows PowerShell-Anbieters](./designing-your-windows-powershell-provider.md)               | In diesem Thema werden Aspekte erläutert, die Sie vor der Implementierung eines Windows PowerShell-Anbieters berücksichtigen sollten. Es fasst die verwendeten Basisklassen und Schnittstellen des Windows PowerShell-Anbieters zusammen. |
| [Erstellen eines Windows PowerShell-Standardanbieters](./creating-a-basic-windows-powershell-provider.md)           | In diesem Thema wird gezeigt, wie Sie einen Windows PowerShell-Anbieter erstellen, der es der Windows PowerShell-Laufzeit ermöglicht, den Anbieter zu initialisieren und dessen Initialisierung zu deaktivieren.                                        |
| [Erstellen eines Windows PowerShell-Laufwerkanbieters](./creating-a-windows-powershell-drive-provider.md)           | In diesem Thema wird gezeigt, wie Sie einen Windows PowerShell-Anbieter erstellen, der es dem Benutzer ermöglicht, über ein Windows PowerShell-Laufwerk auf einen Datenspeicher zuzugreifen.                                                |
| [Erstellen eines Windows PowerShell-Elementanbieters](./creating-a-windows-powershell-item-provider.md)             | In diesem Thema wird gezeigt, wie Sie einen Windows PowerShell-Anbieter erstellen, der es dem Benutzer ermöglicht, die Elemente in einem Datenspeicher zu bearbeiten.                                                                  |
| [Erstellen eines Windows PowerShell-Containeranbieters](./creating-a-windows-powershell-container-provider.md)   | In diesem Thema wird gezeigt, wie Sie einen Windows PowerShell-Anbieter erstellen, der es dem Benutzer ermöglicht, an mehrschichtigen Daten speichern zu arbeiten.                                                                        |
| [Erstellen eines Windows PowerShell-Navigationsanbieters](./creating-a-windows-powershell-navigation-provider.md) | In diesem Thema wird gezeigt, wie Sie einen Windows PowerShell-Anbieter erstellen, der es dem Benutzer ermöglicht, die Elemente eines Datenspeicher hierarchisch zu navigieren.                                           |
| [Erstellen eines Windows PowerShell-Inhaltsanbieters](./creating-a-windows-powershell-content-provider.md)       | In diesem Thema wird gezeigt, wie Sie einen Windows PowerShell-Anbieter erstellen, der es dem Benutzer ermöglicht, den Inhalt von Elementen in einem Datenspeicher zu bearbeiten.                                                       |
| [Erstellen eines Windows PowerShell-Eigenschaftenanbieters](./creating-a-windows-powershell-property-provider.md)     | In diesem Thema wird gezeigt, wie Sie einen Windows PowerShell-Anbieter erstellen, der es dem Benutzer ermöglicht, die Eigenschaften von Elementen in einem Datenspeicher zu bearbeiten.                                                    |

## <a name="see-also"></a>Weitere Informationen

[Funktionsweise von Windows PowerShell](/previous-versions/ms714658(v=vs.85))

[Windows PowerShell SDK](../windows-powershell-reference.md)

[Windows PowerShell-Programmiererhandbuch](./windows-powershell-programmer-s-guide.md)
