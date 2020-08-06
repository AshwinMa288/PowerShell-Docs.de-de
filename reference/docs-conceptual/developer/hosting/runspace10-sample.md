---
title: Runspace10-Beispiel | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: 4d858c432c6221f2347f6de664d1e4ee299f5801
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87784944"
---
# <a name="runspace10-sample"></a><span data-ttu-id="5bc0c-102">Runspace10-Beispiel</span><span class="sxs-lookup"><span data-stu-id="5bc0c-102">Runspace10 Sample</span></span>

<span data-ttu-id="5bc0c-103">In diesem Beispiel wird gezeigt, wie ein ursprünglicher Standard Sitzungszustand erstellt wird, wie ein Cmdlet zum [System.Management.Automation.Runspaces.Initialsessionstate](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState)hinzugefügt wird, wie ein Runspace erstellt wird, der den anfänglichen Sitzungs Status verwendet, und wie der Befehl mithilfe eines [System. Management. Automation. PowerShell](/dotnet/api/system.management.automation.powershell) -Objekts ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="5bc0c-103">This sample shows how to create a default initial session state, how to add a cmdlet to the [System.Management.Automation.Runspaces.Initialsessionstate](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState), how to create a runspace that uses the initial session state, and how to run the command by using a [System.Management.Automation.Powershell](/dotnet/api/system.management.automation.powershell) object.</span></span>

## <a name="requirements"></a><span data-ttu-id="5bc0c-104">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="5bc0c-104">Requirements</span></span>

<span data-ttu-id="5bc0c-105">Dieses Beispiel erfordert Windows PowerShell 2,0.</span><span class="sxs-lookup"><span data-stu-id="5bc0c-105">This sample requires Windows PowerShell 2.0.</span></span>

## <a name="demonstrates"></a><span data-ttu-id="5bc0c-106">Zeigt</span><span class="sxs-lookup"><span data-stu-id="5bc0c-106">Demonstrates</span></span>

<span data-ttu-id="5bc0c-107">In diesem Beispiel wird Folgendes veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="5bc0c-107">This sample demonstrates the following.</span></span>

- <span data-ttu-id="5bc0c-108">Erstellen eines [System.Management.Automation.Runspaces.Initialsessionstate](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) -Objekts.</span><span class="sxs-lookup"><span data-stu-id="5bc0c-108">Creating an [System.Management.Automation.Runspaces.Initialsessionstate](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) object.</span></span>

- <span data-ttu-id="5bc0c-109">Hinzufügen eines Cmdlets (von der Host Anwendung definiert) zum [System.Management.Automation.Runspaces.Initialsessionstate](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) -Objekt.</span><span class="sxs-lookup"><span data-stu-id="5bc0c-109">Adding a cmdlet (defined by the Host application) to the [System.Management.Automation.Runspaces.Initialsessionstate](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) object.</span></span>

- <span data-ttu-id="5bc0c-110">Erstellen eines [System. Management. Automation. Runspaces. Runspace](/dotnet/api/System.Management.Automation.Runspaces.Runspace) -Objekts, das das Objekt verwendet.</span><span class="sxs-lookup"><span data-stu-id="5bc0c-110">Creating a [System.Management.Automation.Runspaces.Runspace](/dotnet/api/System.Management.Automation.Runspaces.Runspace) object that uses the object.</span></span>

- <span data-ttu-id="5bc0c-111">Erstellen eines [System. Management. Automation. PowerShell](/dotnet/api/system.management.automation.powershell) -Objekts, das das [System. Management. Automation. Runspaces. Runspace](/dotnet/api/System.Management.Automation.Runspaces.Runspace) -Objekt verwendet.</span><span class="sxs-lookup"><span data-stu-id="5bc0c-111">Creating a [System.Management.Automation.Powershell](/dotnet/api/system.management.automation.powershell) object that uses the [System.Management.Automation.Runspaces.Runspace](/dotnet/api/System.Management.Automation.Runspaces.Runspace) object.</span></span>

- <span data-ttu-id="5bc0c-112">Hinzufügen des Befehls zur Pipeline des [System. Management. Automation. PowerShell](/dotnet/api/system.management.automation.powershell) -Objekts.</span><span class="sxs-lookup"><span data-stu-id="5bc0c-112">Adding the command to the pipeline of the [System.Management.Automation.Powershell](/dotnet/api/system.management.automation.powershell) object.</span></span>

- <span data-ttu-id="5bc0c-113">Extrahieren von Eigenschaften aus den [System. Management. Automation. psobject](/dotnet/api/System.Management.Automation.PSObject) -Objekten, die vom Befehl zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="5bc0c-113">Extracting properties from the [System.Management.Automation.PSObject](/dotnet/api/System.Management.Automation.PSObject) objects returned by the command.</span></span>

## <a name="example"></a><span data-ttu-id="5bc0c-114">Beispiel</span><span class="sxs-lookup"><span data-stu-id="5bc0c-114">Example</span></span>

<span data-ttu-id="5bc0c-115">In diesem Beispiel wird ein Runspace erstellt, der ein [System.Management.Automation.Runspaces.Initialsessionstate](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) -Objekt verwendet, um die Elemente zu definieren, die beim Öffnen des Runspace verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="5bc0c-115">This sample creates a runspace that uses an [System.Management.Automation.Runspaces.Initialsessionstate](/dotnet/api/System.Management.Automation.Runspaces.InitialSessionState) object to define the elements that are available when the runspace is opened.</span></span> <span data-ttu-id="5bc0c-116">In diesem Beispiel wird das Get-proc-Cmdlet (definiert durch die Host Anwendung) dem anfänglichen Sitzungszustand hinzugefügt, und das Cmdlet wird mithilfe eines [System. Management. Automation. PowerShell](/dotnet/api/system.management.automation.powershell) -Objekts synchron ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="5bc0c-116">In this sample, the Get-Proc cmdlet (defined by the Host application) is added to the initial session state, and the cmdlet is run synchronously by using a [System.Management.Automation.Powershell](/dotnet/api/system.management.automation.powershell) object.</span></span>

```csharp
namespace Microsoft.Samples.PowerShell.Runspaces
{
  using System;
  using System.Collections.Generic;
  using System.Collections.ObjectModel;
  using System.Diagnostics;
  using System.Management.Automation;
  using System.Management.Automation.Runspaces;
  using PowerShell = System.Management.Automation.PowerShell;

  #region GetProcCommand

  /// <summary>
  /// Class that implements the GetProcCommand.
  /// </summary>
  [Cmdlet(VerbsCommon.Get, "Proc")]
  public class GetProcCommand : Cmdlet
  {
    #region Cmdlet Overrides

    /// <summary>
    /// For each of the requested process names, retrieve and write
    /// the associated processes.
    /// </summary>
    protected override void ProcessRecord()
    {
      // Get the current processes.
      Process[] processes = Process.GetProcesses();

      // Write the processes to the pipeline making them available
      // to the next cmdlet. The second argument (true) tells the
      // system to enumerate the array, and send one process object
      // at a time to the pipeline.
      WriteObject(processes, true);
    }

    #endregion Overrides
  } // End GetProcCommand class.

  #endregion GetProcCommand

  /// <summary>
  /// This class contains the Main entry point for this host application.
  /// </summary>
  internal class Runspace10
  {
    /// <summary>
    /// This sample shows how to create a default initial session state, how to add
    /// add a cmdlet to the InitialSessionState object, and then how to create
    /// a Runspace object.
    /// </summary>
    /// <param name="args">Parameter is not used.</param>
    /// This sample demonstrates:
    /// 1. Creating an InitialSessionState object.
    /// 2. Adding a cmdlet to the InitialSessionState object.
    /// 3. Creating a runspace that uses the InitialSessionState object.
    /// 4. Creating a PowerShell object that uses the Runspace object.
    /// 5. Running the added command synchronously.
    /// 6. Working with PSObject objects to extract properties
    ///    from the objects returned by the pipeline.
    private static void Main(string[] args)
    {
      // Create a default InitialSessionState object. The default
      // InitialSessionState object contains all the elements provided
      // by Windows PowerShell.
      InitialSessionState iss = InitialSessionState.CreateDefault();

      // Add the get-proc cmdlet to the InitialSessionState object.
      SessionStateCmdletEntry ssce = new SessionStateCmdletEntry("get-proc", typeof(GetProcCommand), null);
      iss.Commands.Add(ssce);

      // Create a Runspace object that uses the InitialSessionState object.
      // Notice that no PSHost object is specified, so the default host is used.
      // See the Hosting samples for information on creating your own custom host.
      using (Runspace myRunSpace = RunspaceFactory.CreateRunspace(iss))
      {
        myRunSpace.Open();

        using (PowerShell powershell = PowerShell.Create())
        {
          powershell.Runspace = myRunSpace;

          // Add the get-proc cmdlet to the pipeline of the PowerShell object.
          powershell.AddCommand("get-proc");

          Collection<PSObject> results = powershell.Invoke();

          Console.WriteLine("Process              HandleCount");
          Console.WriteLine("--------------------------------");

          // Display the output of the pipeline.
          foreach (PSObject result in results)
          {
             Console.WriteLine(
                               "{0,-20} {1}",
                               result.Members["ProcessName"].Value,
                               result.Members["HandleCount"].Value);
          }
        }

        // Close the runspace to release resources.
        myRunSpace.Close();
      }

      System.Console.WriteLine("Hit any key to exit...");
      System.Console.ReadKey();
    }
  }
}
```

## <a name="see-also"></a><span data-ttu-id="5bc0c-117">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="5bc0c-117">See Also</span></span>

[<span data-ttu-id="5bc0c-118">Schreiben einer Windows PowerShell-Hostanwendung</span><span class="sxs-lookup"><span data-stu-id="5bc0c-118">Writing a Windows PowerShell Host Application</span></span>](./writing-a-windows-powershell-host-application.md)
