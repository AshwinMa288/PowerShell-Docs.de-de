---
ms.date: 09/13/2016
ms.topic: reference
title: Dynamische Anbieter-Cmdlet-Parameter
description: Dynamische Anbieter-Cmdlet-Parameter
ms.openlocfilehash: ac05a847afb0729c34d733fa4ba8da11f46746fe
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92662984"
---
# <a name="provider-cmdlet-dynamic-parameters"></a>Dynamische Anbieter-Cmdlet-Parameter

Anbieter können dynamische Parameter definieren, die einem Anbieter-Cmdlet hinzugefügt werden, wenn der Benutzer einen bestimmten Wert für einen der statischen Parameter des Cmdlets angibt. Ein Anbieter kann z. b. verschiedene dynamische Parameter basierend auf dem Pfad hinzufügen, den der Benutzer angibt, wenn er die- `Get-Item` oder- `Set-Item` Anbieter-Cmdlets aufruft.

## <a name="dynamic-parameter-methods"></a>Dynamische Parameter Methoden

Dynamische Parameter werden definiert, indem eine der dynamischen Parameter Methoden implementiert wird, wie z. b. die [System. Management. Automation. Provider. itemcmdletprovider. getitemdynamicparameters *](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.GetItemDynamicParameters) -und [System. Management. Automation. Provider. itemcmdletprovider. setitemdynamicparameters *](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.SetItemDynamicParameters)s-Methoden. Diese Methoden geben ein Objekt mit öffentlichen Eigenschaften zurück, die mit Attributen versehen sind, die denen von eigenständigen Cmdlets ähneln. Im folgenden finden Sie ein Beispiel für eine Implementierung der [System. Management. Automation. Provider. itemcmdletprovider. getitemdynamicparameters *](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.GetItemDynamicParameters) -Methode, die vom Zertifikat Anbieter stammt:

```csharp
protected override object GetItemDynamicParameters(string path)
{
    return new CertificateProviderDynamicParameters();
}
```

Im Gegensatz zu den statischen Parametern von Provider-Cmdlets können Sie die Eigenschaften dieser Parameter auf die gleiche Weise angeben, wie Parameter in eigenständigen Cmdlets definiert werden. Im folgenden finden Sie ein Beispiel für eine dynamische Parameter Klasse, die vom Zertifikat Anbieter übernommen wird:

```csharp
internal sealed class CertificateProviderDynamicParameters
{
  /// <summary>
  /// Dynamic parameter the controls whether we only return
  /// code signing certs.
  /// </summary>
  [Parameter()]
  public SwitchParameter CodeSigningCert
  {
    get
    {
      {
        return codeSigningCert;
      }
    }

    set
    {
      {
        codeSigningCert = value;
      }
    }
  }

    private SwitchParameter codeSigningCert = new SwitchParameter();
}
```

## <a name="dynamic-parameters"></a>Dynamische Parameter

Im folgenden finden Sie eine Liste der statischen Parameter, die verwendet werden können, um dynamische Parameter hinzuzufügen.

`Clear-Content` -Cmdlet Sie können dynamische Parameter definieren, die durch den- `Path` Parameter des Clear-Clear-Cmdlets ausgelöst werden, indem Sie die [System. Management. Automation. Provider. icontentcmdletprovider. clearcontentdynamicparameters *](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.ClearContentDynamicParameters) -Methode implementieren.

`Clear-Item` -Cmdlet Sie können dynamische Parameter definieren, die durch den- `Path` Parameter des `Clear-Item` Cmdlets ausgelöst werden, indem Sie die [System. Management. Automation. Provider. itemcmdletprovider. clearitemdynamicparameters *](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.ClearItemDynamicParameters) -Methode implementieren.

`Clear-ItemProperty` -Cmdlet Sie können dynamische Parameter definieren, die durch den- `Path` Parameter des `Clear-ItemProperty` Cmdlets ausgelöst werden, indem Sie die [System. Management. Automation. Provider. ipropertycmdletprovider. clearpropertydynamicparameters *](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.ClearPropertyDynamicParameters) -Methode implementieren.

`Copy-Item` Cmdlet Sie können dynamische Parameter definieren, die durch die `Path` Parameter, `Destination` und `Recurse` des Cmdlets ausgelöst werden, indem Sie `Copy-Item` die [System. Management. Automation. Provider. containercmdletprovider. copyitemdynamicparameters *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.CopyItemDynamicParameters) -Methode implementieren.

Get-ChildItems Cmdlet Sie können dynamische Parameter definieren, die durch die `Path` Parameter und `Recurse` des `Get-ChildItem` Cmdlets ausgelöst werden, indem Sie die Methoden [System. Management. Automation. Provider. containercmdletprovider. getchilditemsdynamicparameters *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildItemsDynamicParameters) und [System. Management. Automation. Provider. containercmdletprovider. getchildnamesdynamicparameters *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.GetChildNamesDynamicParameters) implementieren.

`Get-Content` -Cmdlet Sie können dynamische Parameter definieren, die durch den- `Path` Parameter des `Get-Content` Cmdlets ausgelöst werden, indem Sie die [System. Management. Automation. Provider. icontentcmdletprovider. getcontentreaderdynamicparameters *](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentReaderDynamicParameters) -Methode implementieren.

`Get-Item` -Cmdlet Sie können dynamische Parameter definieren, die durch den- `Path` Parameter des `Get-Item` Cmdlets ausgelöst werden, indem Sie die [System. Management. Automation. Provider. itemcmdletprovider. getitemdynamicparameters *](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.GetItemDynamicParameters) -Methode implementieren.

`Get-ItemProperty` -Cmdlet Sie können dynamische Parameter definieren, die durch den `Path` -Parameter und den- `Name` Parameter des `Get-ItemProperty` Cmdlets ausgelöst werden, indem Sie die [System. Management. Automation. Provider. ipropertycmdletprovider. getpropertydynamicparameters *](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.GetPropertyDynamicParameters) -Methode implementieren.

`Invoke-Item` Cmdlet Sie können dynamische Parameter definieren, die durch den- `Path` Parameter des `Invoke-Item` Cmdlets ausgelöst werden, indem Sie die [System. Management. Automation. Provider. itemcmdletprovider. invokedefaultactiondynamicparameters *](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.InvokeDefaultActionDynamicParameters) -Methode implementieren.

`Move-Item` -Cmdlet Sie können dynamische Parameter definieren, die durch den `Path` -Parameter und den- `Destination` Parameter des `Move-Item` Cmdlets ausgelöst werden, indem Sie die [System. Management. Automation. Provider. navigationcmdletprovider. muveitemdynamicparameters *](/dotnet/api/System.Management.Automation.Provider.NavigationCmdletProvider.MoveItemDynamicParameters) -Methode implementieren.

`New-Item` Cmdlet Sie können dynamische Parameter definieren, die durch die `Path` Parameter, `ItemType` und `Value` des Cmdlets ausgelöst werden, indem Sie `New-Item` die [System. Management. Automation. Provider. containercmdletprovider. netwitemdynamicparameters *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.NewItemDynamicParameters) -Methode implementieren.

`New-ItemProperty` Cmdlet Sie können dynamische Parameter definieren, die durch die `Path` Parameter, `Name` , `PropertyType` und `Value` des Cmdlets ausgelöst werden, indem Sie `New-ItemProperty` die [System. Management. Automation. Provider. idynamicpropertycmdletprovider. newpropertydynamicparameters *](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.NewPropertyDynamicParameters) -Methode implementieren.

`New-PSDrive` Cmdlet Sie können dynamische Parameter definieren, die durch das [System.Management.Automation.PSDriveinfo](/dotnet/api/System.Management.Automation.PSDriveInfo) -Objekt ausgelöst werden, das vom `New-PSDrive` Cmdlet durch Implementieren der [System. Management. Automation. Provider. drivecmdletprovider. newdrivedynamicparameters *](/dotnet/api/System.Management.Automation.Provider.DriveCmdletProvider.NewDriveDynamicParameters) -Methode zurückgegeben wird.

`Remove-Item` Sie können dynamische Parameter definieren, die durch den `Path` -Parameter und den- `Recurse` Parameter des `Remove-Item` Cmdlets ausgelöst werden, indem Sie die [System. Management. Automation. Provider. containercmdletprovider. removeitemdynamicparameters *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RemoveItemDynamicParameters) -Methode implementieren.

`Remove-ItemProperty` Sie können dynamische Parameter definieren, die durch den `Path` -Parameter und den- `Name` Parameter des `Remove-ItemProperty` Cmdlets ausgelöst werden, indem Sie die [System. Management. Automation. Provider. idynamicpropertycmdletprovider. removepropertydynamicparameters *](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.RemovePropertyDynamicParameters) -Methode implementieren.

`Rename-Item` -Cmdlet Sie können dynamische Parameter definieren, die durch den `Path` -Parameter und den- `NewName` Parameter des `Rename-Item` Cmdlets ausgelöst werden, indem Sie die [System. Management. Automation. Provider. containercmdletprovider. renameitemdynamicparameters *](/dotnet/api/System.Management.Automation.Provider.ContainerCmdletProvider.RenameItemDynamicParameters) -Methode implementieren.

`Rename-ItemProperty` Sie können dynamische Parameter definieren, die durch den `Path` `Name` -Parameter, den-Parameter und den- `NewName` Parameter des `Rename-ItemProperty` Cmdlets ausgelöst werden, indem Sie die [System. Management. Automation. Provider. idynamicpropertycmdletprovider. renamepropertydynamicparameters *](/dotnet/api/System.Management.Automation.Provider.IDynamicPropertyCmdletProvider.RenamePropertyDynamicParameters) -Methode implementieren.

`Set-Content` -Cmdlet Sie können dynamische Parameter definieren, die durch den- `Path` Parameter des `Set-Content` Cmdlets ausgelöst werden, indem Sie die [System. Management. Automation. Provider. icontentcmdletprovider. getcontentschreiterdynamicparameters *](/dotnet/api/System.Management.Automation.Provider.IContentCmdletProvider.GetContentWriterDynamicParameters) -Methode implementieren.

`Set-Item` -Cmdlet Sie können dynamische Parameter definieren, die durch den `Path` -Parameter und den- `Value` Parameter des `Set-Item` Cmdlets ausgelöst werden, indem Sie die [System. Management. Automation. Provider. itemcmdletprovider. setitemdynamicparameters *](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.SetItemDynamicParameters) -Methode implementieren.

`Set-ItemProperty` -Cmdlet Sie können dynamische Parameter definieren, die durch den `Path` -Parameter und den- `Value` Parameter des `Set-Item` Cmdlets ausgelöst werden, indem Sie die [System. Management. Automation. Provider. ipropertycmdletprovider. setpropertydynamicparameters *](/dotnet/api/System.Management.Automation.Provider.IPropertyCmdletProvider.SetPropertyDynamicParameters) -Methode implementieren.

`Test-Path` Cmdlet Sie können dynamische Parameter definieren, die durch den- `Path` Parameter des `Test-Path` Cmdlets ausgelöst werden, indem Sie die [System. Management. Automation. Provider. itemcmdletprovider. invokedefaultactiondynamicparameters *](/dotnet/api/System.Management.Automation.Provider.ItemCmdletProvider.InvokeDefaultActionDynamicParameters) -Methode implementieren.

## <a name="see-also"></a>Weitere Informationen

[Schreiben eines Windows PowerShell-Anbieters](./writing-a-windows-powershell-provider.md)
