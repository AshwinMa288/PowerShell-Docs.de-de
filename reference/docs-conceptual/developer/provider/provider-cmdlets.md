---
ms.date: 09/12/2016
ms.topic: reference
title: Anbieter-Cmdlets
description: Anbieter-Cmdlets
ms.openlocfilehash: 522dacfe4d7190c12ea0de148fe83bf6b5fed10f
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92662893"
---
# <a name="provider-cmdlets"></a>Anbieter-Cmdlets

Die Cmdlets, die der Benutzer ausführen kann, um einen Datenspeicher zu verwalten, werden als Anbieter-Cmdlets bezeichnet. Um diese Cmdlets zu unterstützen, müssen Sie einige der Methoden überschreiben, die von den Basis Anbieter Klassen und-Schnittstellen definiert werden.

## <a name="provider-cmdlets"></a>Anbieter-Cmdlets

Dies sind die Anbieter-Cmdlets, die vom Benutzer ausgeführt werden können:

### <a name="psdrive-cmdlets"></a>PSDrive-Cmdlets

- `Get-PSDrive`: Mit diesem Cmdlet werden die Windows PowerShell-Laufwerke in der aktuellen Sitzung zurückgegeben. Sie müssen keine Methoden überschreiben, um dieses Cmdlet zu unterstützen.

- `New-PSDrive`: Dieses Cmdlet ermöglicht es dem Benutzer, Windows PowerShell-Laufwerke für den Zugriff auf den Datenspeicher zu erstellen. Zur Unterstützung dieses Cmdlets überschreiben Sie die [System. Management. Automation. Provider. drivecmdletprovider. newdrive](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.NewDrive) -Methode und die [System. Management. Automation. Provider. drivecmdletprovider. newdrivedynamicparameters](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.NewDriveDynamicParameters) -Methode.

- `Remove-PSDrive`: Dieses Cmdlet ermöglicht dem Benutzer das Entfernen von Windows PowerShell-Laufwerken, die auf den Datenspeicher zugreifen. Um dieses Cmdlet zu unterstützen, überschreiben Sie die [System. Management. Automation. Provider. drivecmdletprovider. removedrive](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.RemoveDrive) -Methode.

### <a name="item-cmdlets"></a>Item-Cmdlets

- `Clear-Item`: Mit diesem Cmdlet kann der Benutzer den Wert eines Elements im Datenspeicher entfernen. Um dieses Cmdlet zu unterstützen, überschreiben Sie die Methoden " [System. Management. Automation. Provider. itemcmdletprovider. ClearItem](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.ClearItem) " und " [System. Management. Automation. Provider. itemcmdletprovider. clearitemdynamicparameters](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.ClearItemDynamicParameters) ".

- `Copy-Item`: Mit diesem Cmdlet kann der Benutzer ein Element von einem Speicherort in einen anderen kopieren. Zur Unterstützung dieses Cmdlets überschreiben Sie die [System. Management. Automation. Provider. containercmdletprovider. CopyItem](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.CopyItem) -und die [System. Management. Automation. Provider. containercmdletprovider. copyitemdynamicparameters](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.CopyItemDynamicParameters) -Methode.

- `Get-Item`: Dieses Cmdlet ermöglicht dem Benutzer das Abrufen von Daten aus dem Datenspeicher. Zur Unterstützung dieses Cmdlets überschreiben Sie die [System. Management. Automation. Provider. itemcmdletprovider. GetItem](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.GetItem) -Methode und die [System. Management. Automation. Provider. itemcmdletprovider. getitemdynamicparameters](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.GetItemDynamicParameters) -Methode.

- `Get-ChildItem`: Mit diesem Cmdlet kann der Benutzer die untergeordneten Elemente des übergeordneten Elements abrufen. Überschreiben Sie die folgenden Methoden, um dieses Cmdlet zu unterstützen:

  - [System. Management. Automation. Provider. containercmdletprovider. getchilditems *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildItems)

  - [System. Management. Automation. Provider. containercmdletprovider. getchilditemsdynamicparameters *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildItemsDynamicParameters)

  - [System. Management. Automation. Provider. containercmdletprovider. getchildnames *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildNames)

  - [System. Management. Automation. Provider. containercmdletprovider. getchildnamesdynamicparameters *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildNamesDynamicParameters)

- `Invoke-Item`: Mit diesem Cmdlet kann der Benutzer die vom Element angegebene Standardaktion ausführen. Um dieses Cmdlet zu unterstützen, überschreiben Sie die Methoden " [System. Management. Automation. Provider. itemcmdletprovider. invokedefaultaction](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.InvokeDefaultAction) " und " [System. Management. Automation. Provider. itemcmdletprovider. invokedefaultaction](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.InvokeDefaultAction) ".

- `Move-Item`: Mit diesem Cmdlet kann der Benutzer ein Element von einem Speicherort an einen anderen Speicherort verschieben. Um dieses Cmdlet zu unterstützen, überschreiben Sie die Methoden " [System. Management. Automation. Provider. navigationcmdletprovider. muveitem](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MoveItem) " und " [System. Management. Automation. Provider. navigationcmdletprovider. muveitemdynamicparameters](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MoveItemDynamicParameters)s".

- `New-ItemProperty`: Mit diesem Cmdlet kann der Benutzer ein neues Element im Datenspeicher erstellen.

- `Remove-Item`: Dieses Cmdlet ermöglicht dem Benutzer das Entfernen von Elementen aus dem Datenspeicher. Zur Unterstützung dieses Cmdlets überschreiben Sie die [System. Management. Automation. Provider. containercmdletprovider. RemoveItem](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RemoveItem) -Methode und die [System. Management. Automation. Provider. containercmdletprovider. removeitemdynamicparameters](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RemoveItemDynamicParameters) -Methode.

- `Rename-Item`: Mit diesem Cmdlet kann der Benutzer Elemente im Datenspeicher umbenennen. Zur Unterstützung dieses Cmdlets überschreiben Sie die [System. Management. Automation. Provider. containercmdletprovider. RenameItem](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RenameItem) -und die [System. Management. Automation. Provider. containercmdletprovider. renameitemdynamicparameters](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RenameItemDynamicParameters) -Methode.

- `Set-Item`: Dieses Cmdlet ermöglicht dem Benutzer, die Werte von Elementen im Datenspeicher zu aktualisieren. Zur Unterstützung dieses Cmdlets überschreiben Sie die [System. Management. Automation. Provider. itemcmdletprovider. SetItem](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.SetItem) -Methode und die [System. Management. Automation. Provider. itemcmdletprovider. setitemdynamicparameters](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.SetItemDynamicParameters) -Methode.

### <a name="item-content-cmdlets"></a>Cmdlets für Element Inhalt

- `Add-Content`: Dieses Cmdlet ermöglicht dem Benutzer das Hinzufügen von Inhalt zu einem Element.

- `Clear-Content`: Dieses Cmdlet ermöglicht dem Benutzer das Löschen von Inhalt aus einem Element, ohne das Element zu löschen. Zur Unterstützung dieses Cmdlets überschreiben Sie die [System. Management. Automation. Provider. icontentcmdletprovider. ClearContent](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.ClearContent) -Methode und die [System. Management. Automation. Provider. icontentcmdletprovider. clearcontentdynamicparameters](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.ClearContentDynamicParameters) -Methode.

- `Get-Content`: Dieses Cmdlet ermöglicht dem Benutzer das Abrufen des Inhalts eines Elements. Um dieses Cmdlet zu unterstützen, überschreiben Sie die Methoden " [System. Management. Automation. Provider. icontentcmdletprovider. getcontentreader](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentReader) " und " [System. Management. Automation. Provider. icontentcmdletprovider. getcontentreaderdynamicparameters](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentReaderDynamicParameters) ". Die [System. Management. Automation. Provider. icontentcmdletprovider. getcontentreader *](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentReader) -Methode gibt eine [System. Management. Automation. Provider. icontentreader](/dotnet/api/System.Management.Automation.Provider.IContentReader) -Schnittstelle zurück, die die zum Lesen des Inhalts verwendeten Methoden definiert.

- `Set-Content`: Dieses Cmdlet ermöglicht dem Benutzer, den Inhalt eines Elements zu aktualisieren. Um dieses Cmdlet zu unterstützen, überschreiben Sie die Methoden [System. Management. Automation. Provider. icontentcmdletprovider. getcontentwriter](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentWriter) und [System. Management. Automation. Provider. icontentcmdletprovider. getcontentschreiterdynamicparameters](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentWriterDynamicParameters) . Die [System. Management. Automation. Provider. icontentcmdletprovider. getcontentwriter *](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentWriter) -Methode gibt eine [System. Management. Automation. Provider. icontentwriter](/dotnet/api/System.Management.Automation.Provider.IContentWriter) -Schnittstelle zurück, die die Methoden definiert, mit denen der Inhalt geschrieben wird.

### <a name="item-property-cmdlets"></a>Cmdlets für Element Eigenschaften

- `Clear-ItemProperty`: Mit diesem Cmdlet kann der Benutzer den Wert einer Eigenschaft löschen. Zur Unterstützung dieses Cmdlets überschreiben Sie die [System. Management. Automation. Provider. ipropertycmdletprovider. clearproperty](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.ClearProperty) -und die [System. Management. Automation. Provider. ipropertycmdletprovider. clearpropertydynamicparameters](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.ClearPropertyDynamicParameters) -Methode.

- `Copy-ItemProperty`: Mit diesem Cmdlet kann der Benutzer eine Eigenschaft und ihren Wert von einem Speicherort in einen anderen kopieren. Um dieses Cmdlet zu unterstützen, überschreiben Sie die Methoden " [System. Management. Automation. Provider. idynamicpropertycmdletprovider. copyproperty](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.CopyProperty) " und " [System. Management. Automation. Provider. idynamicpropertycmdletprovider. copypropertydynamicparameters](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.CopyPropertyDynamicParameters) ".

- `Get-ItemProperty`: Mit diesem Cmdlet werden die Eigenschaften eines Elements abgerufen. Zur Unterstützung dieses Cmdlets überschreiben Sie die [System. Management. Automation. Provider. ipropertycmdletprovider. GetProperty](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.GetProperty) -Methode und die [System. Management. Automation. Provider. ipropertycmdletprovider. getpropertydynamicparameters](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.GetPropertyDynamicParameters) -Methode.

- `Move-ItemProperty`: Mit diesem Cmdlet kann der Benutzer eine Eigenschaft und ihren Wert von einem Speicherort an einen anderen verschieben. Um dieses Cmdlet zu unterstützen, überschreiben Sie die Methoden " [System. Management. Automation. Provider. idynamicpropertycmdletprovider. muveproperty](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.MoveProperty) " und " [System. Management. Automation. Provider. idynamicpropertycmdletprovider. muvepropertydynamicparameters](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.MovePropertyDynamicParameters) ".

- `New-ItemProperty`: Mit diesem Cmdlet kann der Benutzer eine neue Eigenschaft erstellen und deren Wert festlegen. Um dieses Cmdlet zu unterstützen, überschreiben Sie die Methoden " [System. Management. Automation. Provider. idynamicpropertycmdletprovider. newproperty](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.NewProperty) " und " [System. Management. Automation. Provider. idynamicpropertycmdletprovider. newpropertydynamicparameters](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.NewPropertyDynamicParameters) ".

- `Remove-ItemProperty`: Mit diesem Cmdlet kann der Benutzer eine Eigenschaft und ihren Wert löschen. Um dieses Cmdlet zu unterstützen, überschreiben Sie die Methoden " [System. Management. Automation. Provider. idynamicpropertycmdletprovider. RemoveProperty](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.RemoveProperty) " und " [System. Management. Automation. Provider. idynamicpropertycmdletprovider. removepropertydynamicparameters](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.RemovePropertyDynamicParameters) ".

- `Rename-ItemProperty`: Mit diesem Cmdlet kann der Benutzer den Namen einer Eigenschaft ändern. Um dieses Cmdlet zu unterstützen, überschreiben Sie die Methoden " [System. Management. Automation. Provider. idynamicpropertycmdletprovider. renameproperty](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.RenameProperty) " und " [System. Management. Automation. Provider. idynamicpropertycmdletprovider. renamepropertydynamicparameters](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.RenamePropertyDynamicParameters) ".

- `Set-ItemProperty`: Mit diesem Cmdlet kann der Benutzer die Eigenschaften eines Elements aktualisieren. Zur Unterstützung dieses Cmdlets überschreiben Sie die [System. Management. Automation. Provider. ipropertycmdletprovider. SetProperty](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.SetProperty) -Methode und die [System. Management. Automation. Provider. ipropertycmdletprovider. setpropertydynamicparameters](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.SetPropertyDynamicParameters) -Methode.

### <a name="location-cmdlets"></a>Location-Cmdlets

- `Get-Location`: Ruft Informationen über den aktuellen Arbeits Speicherort ab. Sie müssen keine Methoden überschreiben, um dieses Cmdlet zu unterstützen.

- `Pop-Location`: Dieses Cmdlet ändert den aktuellen Speicherort in den Speicherort, der zuletzt auf den Stapel verschoben wurde. Sie müssen keine Methoden überschreiben, um dieses Cmdlet zu unterstützen.

- `Push-Location`: Mit diesem Cmdlet wird der aktuelle Speicherort am Anfang einer Liste von Standorten (einem "Stapel") hinzugefügt. Sie müssen keine Methoden überschreiben, um dieses Cmdlet zu unterstützen.

- `Set-Location`: Dieses Cmdlet legt den aktuellen Arbeits Speicherort auf einen angegebenen Speicherort fest. Sie müssen keine Methoden überschreiben, um dieses Cmdlet zu unterstützen.

### <a name="path-cmdlets"></a>Pfad-Cmdlets

- `Join-Path`: Dieses Cmdlet ermöglicht dem Benutzer, ein über-und untergeordnetes Pfad Segment zu kombinieren, um einen Anbieter internen Pfad zu erstellen. Um dieses Cmdlet zu unterstützen, überschreiben Sie die [System. Management. Automation. Provider. navigationcmdletprovider. makepath](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MakePath) -Methode.

- `Convert-Path`: Dieses Cmdlet konvertiert einen Pfad aus einem Windows PowerShell-Pfad in einen Windows PowerShell-Anbieter Pfad.

- `Split-Path`: Gibt den angegebenen Teil eines Pfads zurück.

- `Resolve-Path`: Löst die Platzhalter Zeichen in einem Pfad auf und zeigt den Pfad Inhalt an.

- `Test-Path`: Dieses Cmdlet bestimmt, ob alle Elemente eines Pfads vorhanden sind. Zur Unterstützung dieses Cmdlets überschreiben Sie die [System. Management. Automation. Provider. itemcmdletprovider. itemexists](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.ItemExists) -und die [System. Management. Automation. Provider. itemcmdletprovider. itemexistsdynamicparameters](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.ItemExistsDynamicParameters) -Methode.

### <a name="psprovider-cmdlets"></a>Psprovider-Cmdlets

- `Get-PSProvider`: Dieses Cmdlet gibt Informationen zu den Anbietern zurück, die in der Sitzung verfügbar sind. Sie müssen keine Methoden überschreiben, um dieses Cmdlet zu unterstützen.
