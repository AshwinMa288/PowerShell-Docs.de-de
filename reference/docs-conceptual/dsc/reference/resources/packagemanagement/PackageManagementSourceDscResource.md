---
ms.date: 07/15/2020
ms.topic: reference
title: DSC-Ressource „PackageManagementSource“
description: DSC-Ressource „PackageManagementSource“
ms.openlocfilehash: 495b6548ef86f639e93b914ec8bd8ea7818ff8dd
ms.sourcegitcommit: 196c7f8cd24560cac70c88acc89909f17a86aea9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2020
ms.locfileid: "93142853"
---
# <a name="dsc-packagemanagementsource-resource"></a>DSC-Ressource „PackageManagementSource“

> Gilt für: Windows PowerShell 4.0, Windows PowerShell 5.x

Die Ressource **PackageManagementSource** in Windows PowerShell Desired State Configuration (DSC) bietet einen Mechanismus zum Registrieren von Paketverwaltungsquellen auf einem Zielknoten sowie zum Aufheben der Registrierung.
**Auf diese Weise registrierte Verwaltungspaketquellen werden im Systemkontext registriert und können vom Systemkonto oder der DSC-Engine verwendet werden.** Diese Ressource erfordert das Modul **PackageManagement** , das im [PowerShell-Katalog](https://PowerShellGallery.com) verfügbar ist.

> [!IMPORTANT]
> Die folgenden Eigenschaftsinformationen gelten nur für das **PackageManagement** -Modul Version 1.1.7.0 oder höher.

[!INCLUDE [Updated DSC Resources](../../../../../includes/dsc-resources.md)]

## <a name="syntax"></a>Syntax

```Syntax
PackageManagementSource [String] #ResourceName
{
    Name = [string]
    ProviderName = [string]
    SourceLocation = [string]
    [ InstallationPolicy = [string]{ Trusted | Untrusted } ]
    [ SourceCredential = [PSCredential] ]
    [ DependsOn = [string[]] ]
    [ Ensure = [string]{ Absent | Present } ]
    [ PsDscRunAsCredential = [PSCredential] ]
}
```

## <a name="properties"></a>Eigenschaften

|Eigenschaft |BESCHREIBUNG |
|---|---|
|Name |Gibt den Namen der Paketquelle an, die auf Ihrem System registriert bzw. deren Registrierung aufgehoben werden soll. |
|ProviderName |Gibt den Namen des OneGet-Anbieters an, über den Sie mit der Paketquelle zusammenarbeiten können. |
|SourceLocation |Gibt den URI der Paketquelle an. |
|InstallationPolicy |Wird von Anbietern wie dem integrierten NuGet-Anbieter verwendet. Bestimmt, ob Sie der Paketquelle vertrauen. Enthält einen der folgenden Werte: **Untrusted** (Nicht vertrauenswürdig) oder **Trusted** (Vertrauenswürdig). |
|SourceCredential |Ermöglicht den Zugriff auf das Paket für eine Remotequelle. |

## <a name="common-properties"></a>Allgemeine Eigenschaften

|Eigenschaft |BESCHREIBUNG |
|---|---|
|DependsOn |Gibt an, dass die Konfiguration einer anderen Ressource ausgeführt werden muss, bevor diese Ressource konfiguriert wird. Wenn beispielsweise die ID des Skriptblocks mit der Ressourcenkonfiguration, den Sie zuerst ausführen möchten, „ResourceName“ und dessen Typ „ResourceType“ ist, lautet die Syntax für das Verwenden dieser Eigenschaft `DependsOn = "[ResourceType]ResourceName"`. |
|Ensure |Bestimmt, ob die Paketquelle registriert oder die Registrierung aufgehoben werden soll. Der Standardwert ist **Present** . |
|PsDscRunAsCredential |Legt die Anmeldeinformationen für die Ausführung der gesamten Ressource fest. |

> [!NOTE]
> Die allgemeine Eigenschaft **PsDscRunAsCredential** wurde in WMF 5.0 hinzugefügt, um das Ausführen einer beliebigen DSC-Ressource in Verbindung mit anderen Anmeldeinformationen zu ermöglichen. Weitere Informationen finden Sie unter [Use Credentials with DSC Resources](../../../configurations/runasuser.md) (Verwenden von Anmeldeinformationen mit DSC-Ressourcen).

## <a name="example"></a>Beispiel

Dieses Beispiel registriert die Paketquelle `https://nuget.org` mithilfe der DSC-Ressource **PackageManagementSource** .

```powershell
Configuration PackageManagementSourceTest
{
    PackageManagementSource SourceRepository
    {
        Ensure      = "Present"
        Name        = "MyNuget"
        ProviderName= "Nuget"
        SourceLocation   = "https://api.nuget.org/api/v3/"
        InstallationPolicy ="Trusted"
    }
}
```
