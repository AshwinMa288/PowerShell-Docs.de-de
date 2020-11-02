---
ms.date: 01/02/2020
title: Verwenden von Vervollständigung mit der TAB-TASTE im Skriptbereich und Konsolenbereich
description: Verwenden von Vervollständigung mit der TAB-TASTE im Skriptbereich und Konsolenbereich
ms.openlocfilehash: d59a324ef5ca8eb882814c51bd9b7780b5916e81
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92663682"
---
# <a name="how-to-use-tab-completion-in-the-script-pane-and-console-pane"></a>Verwenden von Vervollständigung mit der TAB-TASTE im Skriptbereich und Konsolenbereich

Vervollständigung mit der TAB-TASTE bietet automatische Hilfe, wenn Sie eine Eingabe im Skriptbereich oder Befehlsbereich vornehmen. Gehen Sie folgendermaßen vor, um dieses Feature zu nutzen:

## <a name="to-automatically-complete-a-command-entry"></a>So wird ein Befehlseintrag automatisch vervollständigt

Geben Sie im Befehlsbereich oder Skriptbereich einige Zeichen eines Befehls ein, und drücken Sie dann die <kbd>TAB-TASTE</kbd>, um den gewünschten Vervollständigungstext auszuwählen. Gibt es mehrere Elemente, die mit dem Text beginnen, den Sie ursprünglich eingegeben haben, drücken Sie so lange die <kbd>TAB-TASTE</kbd>, bis das gewünschte Element angezeigt wird. Vervollständigung mit der TAB-TASTE kann als Unterstützung beim Eingeben eines Cmdlet-Namens, Parameternamens, Variablennamens, Objekteigenschaftsnamens oder Dateipfads verwendet werden.

> [!NOTE]
> Im Skriptbereich wird durch Drücken der <kbd>TAB-TASTE</kbd> ein Befehl nur dann automatisch vervollständigt, wenn Sie `.ps1`-, `.psd1`- oder `.psm1`-Dateien bearbeiten. Vervollständigung mit der TAB-TASTE funktioniert immer, wenn Sie im Befehlsbereich eingeben.

## <a name="to-automatically-complete-a-cmdlet-parameter-entry"></a>So wird ein Parametereintrag eines Cmdlets automatisch vervollständigt

Geben Sie im Befehlsbereich oder Skriptbereich ein Cmdlet gefolgt von einem Bindestrich ein, und drücken Sie dann die <kbd>TAB-TASTE</kbd>.

Geben Sie z. B. `Get-Process -` ein, und drücken Sie dann mehrmals die <kbd>TAB-TASTE</kbd>, um jeden der Parameter des Cmdlets der Reihe nach anzuzeigen.

## <a name="see-also"></a>Weitere Informationen

- [Einführung in die Windows PowerShell ISE](Introducing-the-Windows-PowerShell-ISE.md)
- [Erstellen einer PowerShell-Registerkarte](How-to-Create-a-PowerShell-Tab-in-Windows-PowerShell-ISE.md)
