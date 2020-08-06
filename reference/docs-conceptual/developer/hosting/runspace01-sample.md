---
title: Runspace01-Beispiel | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: 1ac286512f3cb3b97a6b3179c9dd45f1fefe1ecf
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87772194"
---
# <a name="runspace01-sample"></a>Runspace01-Beispiel

In diesem Beispiel wird gezeigt, wie die [System. Management. Automation. PowerShell](/dotnet/api/system.management.automation.powershell) -Klasse verwendet wird, um das [Get-Process-](/powershell/module/Microsoft.PowerShell.Management/Get-Process) Cmdlet synchron auszuführen. Das [Get-Process-](/powershell/module/Microsoft.PowerShell.Management/Get-Process) Cmdlet gibt [System. Diagnostics. Process](/dotnet/api/System.Diagnostics.Process) -Objekte für jeden Prozess zurück, der auf dem lokalen Computer ausgeführt wird. Die Werte der Eigenschaften [System. Diagnostics. Process. ProcessName *](/dotnet/api/System.Diagnostics.Process.ProcessName) und [System. Diagnostics. Process. Lenker count *](/dotnet/api/System.Diagnostics.Process.Handlecount) werden dann aus den zurückgegebenen Objekten extrahiert und in einem Konsolenfenster angezeigt.

## <a name="requirements"></a>Requirements (Anforderungen)

 Dieses Beispiel erfordert Windows PowerShell 2,0.

## <a name="demonstrates"></a>Zeigt

- Erstellen eines [System. Management. Automation. PowerShell](/dotnet/api/system.management.automation.powershell) -Objekts zum Ausführen eines Befehls.

- Hinzufügen eines Befehls zur Pipeline des [System. Management. Automation. PowerShell](/dotnet/api/system.management.automation.powershell) -Objekts.

- Synchrones Ausführen des Befehls.

- Verwenden von [System. Management. Automation. psobject](/dotnet/api/System.Management.Automation.PSObject) -Objekten zum Extrahieren von Eigenschaften aus den Objekten, die vom Befehl zurückgegeben werden.

## <a name="example"></a>Beispiel

 Dieses Beispiel führt das [Get-Process-](/powershell/module/Microsoft.PowerShell.Management/Get-Process) Cmdlet synchron in dem von Windows PowerShell bereitgestellten standardrunspace aus.

```csharp
namespace Microsoft.Samples.PowerShell.Runspaces
{
  using System;
  using System.Management.Automation;
  using PowerShell = System.Management.Automation.PowerShell;

  /// <summary>
  /// This class contains the Main entry point for this host application.
  /// </summary>
  internal class Runspace01
  {
    /// <summary>
    /// This sample uses the PowerShell class to execute
    /// the get-process cmdlet synchronously. The name and
    /// handlecount are then extracted from the PSObjects
    /// returned and displayed.
    /// </summary>
    /// <param name="args">Parameter not used.</param>
    /// <remarks>
    /// This sample demonstrates the following:
    /// 1. Creating a PowerShell object to run a command.
    /// 2. Adding a command to the pipeline of the PowerShell object.
    /// 3. Running the command synchronously.
    /// 4. Using PSObject objects to extract properties from the objects
    ///    returned by the command.
    /// </remarks>
    private static void Main(string[] args)
    {
      // Create a PowerShell object. Creating this object takes care of
      // building all of the other data structures needed to run the command.
      using (PowerShell powershell = PowerShell.Create().AddCommand("get-process"))
      {
        Console.WriteLine("Process              HandleCount");
        Console.WriteLine("--------------------------------");

        // Invoke the command synchronously and display the
        // ProcessName and HandleCount properties of the
        // objects that are returned.
        foreach (PSObject result in powershell.Invoke())
        {
          Console.WriteLine(
                      "{0,-20} {1}",
                      result.Members["ProcessName"].Value,
                      result.Members["HandleCount"].Value);
        }
      }

      System.Console.WriteLine("Hit any key to exit...");
      System.Console.ReadKey();
    }
  }
}
```

## <a name="see-also"></a>Weitere Informationen
