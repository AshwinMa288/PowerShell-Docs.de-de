---
ms.date: 06/05/2017
title: Das PowerShellTabCollection-Objekt
description: Das PowerShellTab-Sammlungsobjekt ist eine Sammlung von PowerShellTab-Objekten. Jedes PowerShellTab-Objekt fungiert als eine separate Laufzeitumgebung.
ms.openlocfilehash: 60f8001f096b50bd8433a5685f1f70a350f07f61
ms.sourcegitcommit: 488a940c7c828820b36a6ba56c119f64614afc29
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/27/2020
ms.locfileid: "92658274"
---
# <a name="the-powershelltabcollection-object"></a>Das PowerShellTabCollection-Objekt

Das **PowerShellTab** -Sammlungsobjekt ist eine Sammlung von **PowerShellTab** -Objekten. Jedes **PowerShellTab** -Objekt fungiert als eine separate Laufzeitumgebung. Dies ist eine Instanz der Microsoft.PowerShell.Host.ISE.PowerShellTabs-Klasse. Ein Beispiel ist das `$psISE.PowerShellTabs`-Objekt.

## <a name="methods"></a>Methoden

### <a name="add"></a>Add\(\)

In Windows PowerShell ISE 2.0 und höher unterstützt.

Fügt eine neue PowerShell-Registerkarte zur Sammlung hinzu. Die neu hinzugefügte Registerkarte wird zurückgegeben.

```powershell
$newTab = $psISE.PowerShellTabs.Add()
$newTab.DisplayName = 'Brand New Tab'
```

### <a name="removemicrosoftpowershellhostisepowershelltab-pstab"></a>Remove\(Microsoft.PowerShell.Host.ISE.PowerShellTab psTab\)

In Windows PowerShell ISE 2.0 und höher unterstützt.

Entfernt die Registerkarte, die durch den **psTab** -Parameter angegeben wird.

**psTab** Die zu entfernende PowerShell-Registerkarte.

```powershell
$newTab = $psISE.PowerShellTabs.Add()
Change the DisplayName of the new PowerShell tab.
$newTab.DisplayName = 'This tab will go away in 5 seconds'
sleep 5
$psISE.PowerShellTabs.Remove($newTab)
```

### <a name="setselectedpowershelltabmicrosoftpowershellhostisepowershelltab-pstab"></a>SetSelectedPowerShellTab\(Microsoft.PowerShell.Host.ISE.PowerShellTab psTab\)

In Windows PowerShell ISE 2.0 und höher unterstützt.

Wählt die PowerShell-Registerkarte aus, die durch den **psTab** -Parameter angegeben wird, um diese als aktuell aktive PowerShell-Registerkarte festzulegen.

**psTab** Die auszuwählende PowerShell-Registerkarte.

```powershell
# Save the current tab in a variable and rename it
$oldTab = $psISE.CurrentPowerShellTab
$psISE.CurrentPowerShellTab.DisplayName = 'Old Tab'
# Create a new tab and give it a new display name
$newTab = $psISE.PowerShellTabs.Add()
$newTab.DisplayName = 'Brand New Tab'
# Switch back to the original tab
$psISE.PowerShellTabs.SelectedPowerShellTab = $oldTab
```

## <a name="see-also"></a>Weitere Informationen

- [Das PowerShellTab-Objekt](The-PowerShellTab-Object.md)
- [Zweck des Windows PowerShell ISE-Skriptobjektmodells](Purpose-of-the-Windows-PowerShell-ISE-Scripting-Object-Model.md)
- [Die ISE-Objektmodellhierarchie](The-ISE-Object-Model-Hierarchy.md)
