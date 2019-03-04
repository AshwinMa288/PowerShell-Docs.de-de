---
title: 'Gewusst wie: Aufrufen von Skripts in einem Cmdlet | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: cc0bc6ce-48a5-4d9c-927e-636bca743e9f
caps.latest.revision: 9
ms.openlocfilehash: 4b4d5645785b751eb1390e196f5b9437b4a1e13b
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/03/2019
ms.locfileid: "56855836"
---
# <a name="how-to-invoke-scripts-within-a-cmdlet"></a>Aufrufen von Skripts in einem Cmdlet

Dieses Beispiel zeigt, wie Sie ein Skript aufrufen, die an ein Cmdlet bereitgestellt werden. Das Skript vom Cmdlet ausgeführt wird, und die Ergebnisse werden an das Cmdlet zurückgegeben, als eine Auflistung von [System.Management.Automation.Psobject](/dotnet/api/System.Management.Automation.PSObject) Objekte.

## <a name="to-invoke-a-script-block"></a>Um einen Skriptblock aufzurufen.

1. Der Befehl wird überprüft, dass ein Skriptblock an das Cmdlet übergeben wurde. Wenn ein Skriptblock angegeben wurde, ruft den Befehl den Skriptblock der erforderliche Parameter.

    ```csharp
    if (script != null)
    {
      WriteDebug("Executing script block.");

      // Invoke the script block with the required arguments.
      Collection<PSObject> PSObjects =
                     script.Invoke(
                                   line,
                                   simpleMatch,
                                   caseSensitive
                                  );
    ```

2. Klicken Sie dann die zurückgegebene Auflistung von das Skript durchläuft [System.Management.Automation.Psobject](/dotnet/api/System.Management.Automation.PSObject) Objekte und die erforderlichen Vorgänge ausführen.

    ```c
    foreach (PSObject psObject in psObjects)
    {
      if (LanguagePrimitives.IsTrue(psObject))
      {
        result = new MatchInfo();
        result.Line = line;
        result.IgnoreCase = !caseSensitive;

        break;
      }
    }

    ```

## <a name="see-also"></a>Weitere Informationen

[Schreiben eines Windows PowerShell-Cmdlets](./writing-a-windows-powershell-cmdlet.md)