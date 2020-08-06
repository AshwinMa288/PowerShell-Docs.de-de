---
title: GetProcessSample04-Beispiel | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: 4858c44302f7315625be02dd0dc1d335b9c3f158
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87774421"
---
# <a name="getprocesssample04-sample"></a><span data-ttu-id="621c8-102">GetProcessSample04-Beispiel</span><span class="sxs-lookup"><span data-stu-id="621c8-102">GetProcessSample04 Sample</span></span>

<span data-ttu-id="621c8-103">In diesem Beispiel wird gezeigt, wie ein Cmdlet implementiert wird, das die Prozesse auf dem lokalen Computer abruft.</span><span class="sxs-lookup"><span data-stu-id="621c8-103">This sample shows how to implement a cmdlet that retrieves the processes on the local computer.</span></span> <span data-ttu-id="621c8-104">Wenn beim Abrufen eines Prozesses ein Fehler auftritt, wird ein Fehler vom Typ "nicht abgebrochen" generiert.</span><span class="sxs-lookup"><span data-stu-id="621c8-104">It generates a nonterminating error if an error occurs while retrieving a process.</span></span> <span data-ttu-id="621c8-105">Dieses Cmdlet ist eine vereinfachte Version des `Get-Process` Cmdlets, das von Windows PowerShell 2,0 bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="621c8-105">This cmdlet is a simplified version of the `Get-Process` cmdlet provided by Windows PowerShell 2.0.</span></span>

## <a name="how-to-build-the-sample-using-visual-studio"></a><span data-ttu-id="621c8-106">So erstellen Sie das Beispiel mithilfe von Visual Studio.</span><span class="sxs-lookup"><span data-stu-id="621c8-106">How to build the sample using Visual Studio.</span></span>

1. <span data-ttu-id="621c8-107">Navigieren Sie mit installiertem Windows PowerShell 2,0 SDK zum Ordner GetProcessSample04.</span><span class="sxs-lookup"><span data-stu-id="621c8-107">With the Windows PowerShell 2.0 SDK installed, navigate to the GetProcessSample04 folder.</span></span> <span data-ttu-id="621c8-108">Der Standard Speicherort ist "c:\Programme (x86) \Microsoft SDKs\Windows\v7.0\samples\sysmgmt\windowspowershell\csharp\getprocesssample04.".</span><span class="sxs-lookup"><span data-stu-id="621c8-108">The default location is C:\Program Files (x86)\Microsoft SDKs\Windows\v7.0\Samples\sysmgmt\WindowsPowerShell\csharp\GetProcessSample04.</span></span>

2. <span data-ttu-id="621c8-109">Doppelklicken Sie auf das Symbol für die Projektmappendatei (. sln).</span><span class="sxs-lookup"><span data-stu-id="621c8-109">Double-click the icon for the solution (.sln) file.</span></span> <span data-ttu-id="621c8-110">Dadurch wird das Beispiel Projekt in Visual Studio geöffnet.</span><span class="sxs-lookup"><span data-stu-id="621c8-110">This opens the sample project in Visual Studio.</span></span>

3. <span data-ttu-id="621c8-111">Wählen Sie im Menü **Erstellen** die Option **Projektmappe erstellen** aus.</span><span class="sxs-lookup"><span data-stu-id="621c8-111">In the **Build** menu, select **Build Solution**.</span></span>

    <span data-ttu-id="621c8-112">Die Bibliothek für das Beispiel wird im Standardordner \bin oder \bin\Debug erstellt.</span><span class="sxs-lookup"><span data-stu-id="621c8-112">The library for the sample will be built in the default \bin or \bin\debug folders.</span></span>

### <a name="how-to-run-the-sample"></a><span data-ttu-id="621c8-113">Ausführen des Beispiels</span><span class="sxs-lookup"><span data-stu-id="621c8-113">How to run the sample</span></span>

1. <span data-ttu-id="621c8-114">Erstellen Sie den folgenden Modul Ordner:</span><span class="sxs-lookup"><span data-stu-id="621c8-114">Create the following module folder:</span></span>

    `[user]/documents/windowspowershell/modules/GetProcessSample04`

2. <span data-ttu-id="621c8-115">Kopieren Sie die Beispielassembly in den Modul Ordner.</span><span class="sxs-lookup"><span data-stu-id="621c8-115">Copy the sample assembly to the module folder.</span></span>

3. <span data-ttu-id="621c8-116">Starten Sie Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="621c8-116">Start Windows PowerShell.</span></span>

4. <span data-ttu-id="621c8-117">Führen Sie den folgenden Befehl aus, um die Assembly in Windows PowerShell zu laden:</span><span class="sxs-lookup"><span data-stu-id="621c8-117">Run the following command to load the assembly into Windows PowerShell:</span></span>

    `Import-module getprossessample04`

5. <span data-ttu-id="621c8-118">Führen Sie den folgenden Befehl aus, um das Cmdlet auszuführen:</span><span class="sxs-lookup"><span data-stu-id="621c8-118">Run the following command to run the cmdlet:</span></span>

    `get-proc`

## <a name="requirements"></a><span data-ttu-id="621c8-119">Requirements (Anforderungen)</span><span class="sxs-lookup"><span data-stu-id="621c8-119">Requirements</span></span>

<span data-ttu-id="621c8-120">Dieses Beispiel erfordert Windows PowerShell 2,0.</span><span class="sxs-lookup"><span data-stu-id="621c8-120">This sample requires Windows PowerShell 2.0.</span></span>

## <a name="demonstrates"></a><span data-ttu-id="621c8-121">Zeigt</span><span class="sxs-lookup"><span data-stu-id="621c8-121">Demonstrates</span></span>

<span data-ttu-id="621c8-122">In diesem Beispiel wird Folgendes veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="621c8-122">This sample demonstrates the following.</span></span>

- <span data-ttu-id="621c8-123">Deklarieren einer Cmdlet-Klasse mithilfe des Cmdlet-Attributs.</span><span class="sxs-lookup"><span data-stu-id="621c8-123">Declaring a cmdlet class using the Cmdlet attribute.</span></span>

- <span data-ttu-id="621c8-124">Deklarieren eines Cmdlet-Parameters mithilfe des Parameter-Attributs.</span><span class="sxs-lookup"><span data-stu-id="621c8-124">Declaring a cmdlet parameter using the Parameter attribute.</span></span>

- <span data-ttu-id="621c8-125">Angeben der Position des Parameters.</span><span class="sxs-lookup"><span data-stu-id="621c8-125">Specifying the position of the parameter.</span></span>

- <span data-ttu-id="621c8-126">Angeben, dass der Parameter Eingaben aus der Pipeline annimmt.</span><span class="sxs-lookup"><span data-stu-id="621c8-126">Specifying that the parameter takes input from the pipeline.</span></span> <span data-ttu-id="621c8-127">Die Eingabe kann aus einem Objekt oder einem Wert aus einer Eigenschaft eines Objekts entnommen werden, dessen Eigenschaftsname mit dem Parameternamen identisch ist.</span><span class="sxs-lookup"><span data-stu-id="621c8-127">The input can be taken from an object or a value from a property of an object whose property name is the same as the parameter name.</span></span>

- <span data-ttu-id="621c8-128">Deklarieren eines Validierungs Attributs für die Parameter Eingabe.</span><span class="sxs-lookup"><span data-stu-id="621c8-128">Declaring a validation attribute for the parameter input.</span></span>

- <span data-ttu-id="621c8-129">Das Abfangen eines Fehlers ohne Abbruch und das Schreiben einer Fehlermeldung in den Fehler Datenstrom.</span><span class="sxs-lookup"><span data-stu-id="621c8-129">Trapping a nonterminating error and writing an error message to the error stream.</span></span>

## <a name="example"></a><span data-ttu-id="621c8-130">Beispiel</span><span class="sxs-lookup"><span data-stu-id="621c8-130">Example</span></span>

<span data-ttu-id="621c8-131">In diesem Beispiel wird gezeigt, wie ein Cmdlet erstellt wird, das nicht abschließende Fehler behandelt und Fehlermeldungen in den Fehler Datenstrom schreibt.</span><span class="sxs-lookup"><span data-stu-id="621c8-131">This sample shows how to create a cmdlet that handles nonterminating errors and writes error messages to the error stream.</span></span>

```csharp
namespace Microsoft.Samples.PowerShell.Commands
{
    using System;
    using System.Diagnostics;
    using System.Management.Automation;      // Windows PowerShell namespace.
   #region GetProcCommand

   /// <summary>
   /// This class implements the get-proc cmdlet.
   /// </summary>
   [Cmdlet(VerbsCommon.Get, "Proc")]
   public class GetProcCommand : Cmdlet
   {
      #region Parameters

       /// <summary>
       /// The names of the processes to act on.
       /// </summary>
       private string[] processNames;

      /// <summary>
      /// Gets or sets the list of process names on
      /// which the Get-Proc cmdlet will work.
      /// </summary>
      [Parameter(
         Position = 0,
         ValueFromPipeline = true,
         ValueFromPipelineByPropertyName = true)]
      [ValidateNotNullOrEmpty]
      public string[] Name
      {
         get { return this.processNames; }
         set { this.processNames = value; }
      }

      #endregion Parameters

      #region Cmdlet Overrides

      /// <summary>
      /// The ProcessRecord method calls the Process.GetProcesses
      /// method to retrieve the processes specified by the Name
      /// parameter. Then, the WriteObject method writes the
      /// associated processes to the pipeline.
      /// </summary>
      protected override void ProcessRecord()
      {
          // If no process names are passed to cmdlet, get all
          // processes.
          if (this.processNames == null)
          {
              WriteObject(Process.GetProcesses(), true);
          }
          else
          {
              // If process names are passed to the cmdlet, get and write
              // the associated processes.
              // If a nonterminating error occurs while retrieving processes,
              // call the WriteError method to send an error record to the
              // error stream.
              foreach (string name in this.processNames)
              {
                  Process[] processes;

                  try
                  {
                      processes = Process.GetProcessesByName(name);
                  }
                  catch (InvalidOperationException ex)
                  {
                      WriteError(new ErrorRecord(
                         ex,
                         "UnableToAccessProcessByName",
                         ErrorCategory.InvalidOperation,
                         name));
                      continue;
                  }

                  WriteObject(processes, true);
              } // foreach (string name...
          } // else
      } // ProcessRecord

      #endregion Overrides
    } // End GetProcCommand class.

   #endregion GetProcCommand
}
```

## <a name="see-also"></a><span data-ttu-id="621c8-132">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="621c8-132">See Also</span></span>

[<span data-ttu-id="621c8-133">Schreiben eines Windows PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="621c8-133">Writing a Windows PowerShell Cmdlet</span></span>](./writing-a-windows-powershell-cmdlet.md)
