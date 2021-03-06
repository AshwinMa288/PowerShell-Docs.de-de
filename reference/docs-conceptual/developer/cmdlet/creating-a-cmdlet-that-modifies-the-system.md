---
ms.date: 09/13/2016
ms.topic: reference
title: Erstellen eines Cmdlet, das das System ändert
description: Erstellen eines Cmdlet, das das System ändert
ms.openlocfilehash: 757f2c97bb4b5dcf2fb633cd35fe52bc5f6c5cf9
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "93355543"
---
# <a name="creating-a-cmdlet-that-modifies-the-system"></a>Erstellen eines Cmdlet, das das System ändert

Manchmal muss ein Cmdlet den Lauf Zustand des Systems ändern, nicht nur den Status der Windows PowerShell-Laufzeit. In diesen Fällen sollte das Cmdlet dem Benutzer die Möglichkeit geben, zu bestätigen, ob die Änderung vorgenommen werden soll.

Zur Unterstützung der Bestätigung muss ein Cmdlet zwei Aktionen ausführen.

- Deklarieren Sie, dass das Cmdlet die Bestätigung unterstützt, wenn Sie das [System. Management. Automation. CmdletAttribute](/dotnet/api/System.Management.Automation.CmdletAttribute) -Attribut angeben, indem Sie das Schlüsselwort supportsschulter dprocess auf festlegen `true` .

- Während der Ausführung des Cmdlets wird [System. Management. Automation. Cmdlet. rudprocess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) aufgerufen (wie im folgenden Beispiel gezeigt).

Durch die Unterstützung der Bestätigung macht ein Cmdlet den `Confirm` -Parameter und den-Parameter verfügbar, die `WhatIf` von Windows PowerShell bereitgestellt werden, und erfüllt außerdem die Entwicklungs Richtlinien für Cmdlets (Weitere Informationen zu Cmdlet-Entwicklungs Richtlinien finden Sie unter [Cmdlet-Entwicklungs Richtlinien](./cmdlet-development-guidelines.md)).

## <a name="changing-the-system"></a>Ändern des Systems

Der Vorgang "Ändern des Systems" bezieht sich auf jedes Cmdlet, das möglicherweise den Status des Systems außerhalb von Windows PowerShell ändert. Das Beenden eines Prozesses, das Aktivieren oder Deaktivieren eines Benutzerkontos oder das Hinzufügen einer Zeile zu einer Datenbanktabelle sind alle Änderungen am System, die bestätigt werden sollen.
Im Gegensatz dazu ändern Vorgänge, die Daten lesen oder vorübergehende Verbindungen herstellen, das System nicht und erfordern im Allgemeinen keine Bestätigung. Die Bestätigung wird auch nicht für Aktionen benötigt, deren Auswirkung auf in der Windows PowerShell-Laufzeit beschränkt ist, z `set-variable` . b.. Cmdlets, die eine permanente Änderung möglicherweise vornehmen, sollten die Deklaration `SupportsShouldProcess` von [System. Management. Automation. Cmdlet. dauerdprocess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) nur dann deklarieren, wenn Sie eine permanente Änderung durchführen.

> [!NOTE]
> Die Bestätigungsprozess Bestätigung gilt nur für Cmdlets. Wenn ein Befehl oder ein Skript den Lauf Zustand eines Systems durch direktes Aufrufen von .NET-Methoden oder-Eigenschaften oder durch Aufrufen von Anwendungen außerhalb von Windows PowerShell ändert, ist diese Form der Bestätigung nicht verfügbar.

## <a name="the-stopproc-cmdlet"></a>Das stopproc-Cmdlet

In diesem Thema wird ein Stop-Proc Cmdlet beschrieben, das versucht, Prozesse zu verhindern, die mithilfe des Get-Proc-Cmdlets abgerufen werden (siehe [Erstellen des ersten Cmdlets](./creating-a-cmdlet-without-parameters.md)).

## <a name="defining-the-cmdlet"></a>Definieren des Cmdlets

Der erste Schritt bei der Cmdlet-Erstellung ist die Benennung des Cmdlets und das Deklarieren der .NET-Klasse, die das Cmdlet implementiert. Da Sie ein Cmdlet schreiben, um das System zu ändern, sollte es entsprechend benannt werden. Dieses Cmdlet beendet System Prozesse, sodass der hier gewählte Verb Name "Stopp" ist, der von der [System. Management. Automation. verbslifecycle](/dotnet/api/System.Management.Automation.VerbsLifeCycle) -Klasse definiert wird, mit dem Substantiv "proc", um anzugeben, dass das Cmdlet Prozesse beendet. Weitere Informationen zu genehmigten Cmdlet-Verben finden Sie unter [Cmdlet-Verb Namen](./approved-verbs-for-windows-powershell-commands.md).

Im folgenden finden Sie die Klassendefinition für dieses Stop-Proc-Cmdlet.

```csharp
[Cmdlet(VerbsLifecycle.Stop, "Proc",
        SupportsShouldProcess = true)]
public class StopProcCommand : Cmdlet
```

Beachten Sie, dass das Attribut Schlüsselwort in der [System. Management. Automation. CmdletAttribute](/dotnet/api/System.Management.Automation.CmdletAttribute) -Deklaration `SupportsShouldProcess` auf festgelegt ist, `true` um das Cmdlet zum Aufrufen von [System. Management. Automation. Cmdlet. Schulter dprocess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) und [System. Management. Automation. Cmdlet. Schulter dcontinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue)zu aktivieren.
Wenn dieses Schlüsselwort nicht festgelegt ist, sind der `Confirm` - `WhatIf` Parameter und der-Parameter für den Benutzer nicht verfügbar.

### <a name="extremely-destructive-actions"></a>Äußerst zerstörerische Aktionen

Einige Vorgänge sind äußerst destruktiv, z. b. die Neuformatierung einer aktiven Festplatten Partition. In diesen Fällen muss das Cmdlet `ConfirmImpact`  =  `ConfirmImpact.High` beim Deklarieren des [System. Management. Automation. CmdletAttribute](/dotnet/api/System.Management.Automation.CmdletAttribute) -Attributs festgelegt werden. Diese Einstellung erzwingt, dass das Cmdlet die Benutzer Bestätigung anfordert, auch wenn der Benutzer den Parameter nicht angegeben hat `Confirm` . Cmdlet-Entwickler sollten jedoch die übermäßige Verwendung `ConfirmImpact` von Vorgängen vermeiden, die nur potenziell destruktiv sind, z. b. das Löschen eines Benutzerkontos. Beachten Sie, dass, wenn `ConfirmImpact` auf [System. Management. Automation. confirmimpact](/dotnet/api/System.Management.Automation.ConfirmImpact) 
 **High** festgelegt ist.

Ebenso ist es unwahrscheinlich, dass einige Vorgänge destruktiv sind, obwohl Sie theoretisch den Lauf Zustand eines Systems außerhalb von Windows PowerShell ändern. Diese Cmdlets können `ConfirmImpact` auf [System. Management. Automation. confirmimpact. Low](/dotnet/api/system.management.automation.confirmimpact)festgelegt werden.
Dadurch werden Bestätigungs Anforderungen umgangen, bei denen der Benutzer aufgefordert wurde, nur Vorgänge mit mittlerer Auswirkung und hohem Einfluss zu bestätigen.

## <a name="defining-parameters-for-system-modification"></a>Definieren von Parametern für die System Änderung

In diesem Abschnitt wird beschrieben, wie Sie die Cmdlet-Parameter definieren, einschließlich derjenigen, die zur Unterstützung der Systemänderung benötigt werden. Weitere Informationen zum Definieren von Parametern finden Sie unter [Hinzufügen von Parametern, die die Befehlszeilen Eingabe verarbeiten](./adding-parameters-that-process-command-line-input.md) .

Das-Cmdlet "Stop-Proc" definiert drei Parameter: `Name` , `Force` und `PassThru` .

Der- `Name` Parameter entspricht der- `Name` Eigenschaft des Process Input-Objekts. Beachten Sie, dass der `Name` Parameter in diesem Beispiel obligatorisch ist, da das Cmdlet fehlschlägt, wenn kein benannter Prozess zum Abbrechen vorhanden ist.

Der- `Force` Parameter ermöglicht es dem Benutzer, Aufrufe von [System. Management. Automation. Cmdlet. daudcontinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue)zu überschreiben.
Tatsächlich sollte jedes Cmdlet, das [System. Management. Automation. Cmdlet. schuldcontinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) aufruft, über einen-Parameter verfügen, `Force` sodass `Force` das Cmdlet den Aufruf von [System. Management. Automation. Cmdlet](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) überspringt und den Vorgang fortsetzt, wenn angegeben wird. Beachten Sie, dass dies keine Auswirkungen auf Aufrufe von [System. Management. Automation. Cmdlet. schuldprocess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess)hat.

Mit dem- `PassThru` Parameter kann der Benutzer angeben, ob das Cmdlet ein Ausgabe Objekt über die Pipeline übergibt, in diesem Fall, nachdem ein Prozess angehalten wurde. Beachten Sie, dass dieser Parameter nicht an eine Eigenschaft des Eingabe Objekts, sondern an das Cmdlet selbst gebunden ist.

Hier ist die Parameter Deklaration für das Cmdlet "Stop-Proc".

```csharp
[Parameter(
           Position = 0,
           Mandatory = true,
           ValueFromPipeline = true,
           ValueFromPipelineByPropertyName = true
)]
public string[] Name
{
  get { return processNames; }
  set { processNames = value; }
}
private string[] processNames;

/// <summary>
/// Specify the Force parameter that allows the user to override
/// the ShouldContinue call to force the stop operation. This
/// parameter should always be used with caution.
/// </summary>
[Parameter]
public SwitchParameter Force
{
  get { return force; }
  set { force = value; }
}
private bool force;

/// <summary>
/// Specify the PassThru parameter that allows the user to specify
/// that the cmdlet should pass the process object down the pipeline
/// after the process has been stopped.
/// </summary>
[Parameter]
public SwitchParameter PassThru
{
  get { return passThru; }
  set { passThru = value; }
}
private bool passThru;
```

## <a name="overriding-an-input-processing-method"></a>Überschreiben einer Eingabe Verarbeitungsmethode

Das Cmdlet muss eine Eingabe Verarbeitungsmethode überschreiben. Der folgende Code veranschaulicht die [System. Management. Automation. Cmdlet. ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) -außer Kraft setzung, die im Beispiel Stop-Proc-Cmdlet verwendet wird. Diese Methode stellt für jeden angeforderten Prozessnamen sicher, dass es sich bei dem Prozess nicht um einen speziellen Prozess handelt, versucht, den Prozess zu beenden, und sendet dann ein Ausgabe Objekt, wenn der `PassThru` Parameter angegeben wird.

```csharp
protected override void ProcessRecord()
{
  foreach (string name in processNames)
  {
    // For every process name passed to the cmdlet, get the associated
    // process(es). For failures, write a non-terminating error
    Process[] processes;

    try
    {
      processes = Process.GetProcessesByName(name);
    }
    catch (InvalidOperationException ioe)
    {
      WriteError(new ErrorRecord(ioe,"Unable to access the target process by name",
                 ErrorCategory.InvalidOperation, name));
      continue;
    }

    // Try to stop the process(es) that have been retrieved for a name
    foreach (Process process in processes)
    {
      string processName;

      try
      {
        processName = process.ProcessName;
      }

      catch (Win32Exception e)
        {
          WriteError(new ErrorRecord(e, "ProcessNameNotFound",
                     ErrorCategory.ReadError, process));
          continue;
        }

        // Call Should Process to confirm the operation first.
        // This is always false if WhatIf is set.
        if (!ShouldProcess(string.Format("{0} ({1})", processName,
                           process.Id)))
        {
          continue;
        }
        // Call ShouldContinue to make sure the user really does want
        // to stop a critical process that could possibly stop the computer.
        bool criticalProcess =
             criticalProcessNames.Contains(processName.ToLower());

        if (criticalProcess &&!force)
        {
          string message = String.Format
                ("The process \"{0}\" is a critical process and should not be stopped. Are you sure you wish to stop the process?",
                processName);

          // It is possible that ProcessRecord is called multiple times
          // when the Name parameter receives objects as input from the
          // pipeline. So to retain YesToAll and NoToAll input that the
          // user may enter across multiple calls to ProcessRecord, this
          // information is stored as private members of the cmdlet.
          if (!ShouldContinue(message, "Warning!",
                              ref yesToAll,
                              ref noToAll))
          {
            continue;
          }
        } // if (criticalProcess...
        // Stop the named process.
        try
        {
          process.Kill();
        }
        catch (Exception e)
        {
          if ((e is Win32Exception) || (e is SystemException) ||
              (e is InvalidOperationException))
          {
            // This process could not be stopped so write
            // a non-terminating error.
            string message = String.Format("{0} {1} {2}",
                             "Could not stop process \"", processName,
                             "\".");
            WriteError(new ErrorRecord(e, message,
                       ErrorCategory.CloseError, process));
                       continue;
          } // if ((e is...
          else throw;
        } // catch

        // If the PassThru parameter argument is
        // True, pass the terminated process on.
        if (passThru)
        {
          WriteObject(process);
        }
    } // foreach (Process...
  } // foreach (string...
} // ProcessRecord
```

## <a name="calling-the-shouldprocess-method"></a>Aufrufen der Methode "tiondprocess"

Die Eingabe Verarbeitungsmethode des Cmdlets muss die [System. Management. Automation. Cmdlet. Schulter dprocess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) -Methode aufgerufen werden, um die Ausführung eines Vorgangs vor einer Änderung (z. b. das Löschen von Dateien) zu bestätigen. Dadurch kann die Windows PowerShell-Laufzeit das richtige "WhatIf"-und "Confirm"-Verhalten innerhalb der Shell bereitstellen.

> [!NOTE]
> Wenn ein Cmdlet angibt, dass es von unterstützt wird, und den [System. Management. Automation. Cmdlet.](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) --Prozess nicht aufzurufen, kann der Benutzer das System möglicherweise unerwartet ändern.

Der [System. Management. Automation. Cmdlet. tiondprocess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) -Befehl sendet den Namen der Ressource, die an den Benutzer geändert werden soll, wobei die Windows PowerShell-Laufzeit alle Befehlszeilen Einstellungen oder Einstellungs Variablen berücksichtigt, um zu bestimmen, was dem Benutzer angezeigt werden soll.

Im folgenden Beispiel wird der System [. Management. Automation. Cmdlet. dendprocess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) -Befehl aus der Überschreibung der [System. Management. Automation. Cmdlet. ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) -Methode im Sample Stop-Proc-Cmdlet gezeigt.

```csharp
if (!ShouldProcess(string.Format("{0} ({1})", processName,
                   process.Id)))
{
  continue;
}
```

## <a name="calling-the-shouldcontinue-method"></a>Aufrufen der Methode "schuldcontinue"

Der Aufrufe der [System. Management. Automation. Cmdlet. Schulter dcontinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) -Methode sendet eine sekundäre Nachricht an den Benutzer. Dieser-Befehl wird nach dem Aufrufen von [System. Management. Automation. Cmdlet. daudprocess](/dotnet/api/System.Management.Automation.Cmdlet.ShouldProcess) zurückgegeben `true` und, wenn der- `Force` Parameter nicht auf festgelegt wurde `true` . Der Benutzer kann dann Feedback geben, um anzugeben, ob der Vorgang fortgesetzt werden soll. Ihr Cmdlet ruft die [System. Management. Automation. Cmdlet. tiondcontinue](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) auf, um eine zusätzliche Überprüfung auf potenziell gefährliche System Änderungen vorzunehmen, oder wenn Sie dem Benutzer die Optionen Yes-to-all und No-to-all bereitstellen möchten.

Im folgenden Beispiel wird der System [. Management. Automation. Cmdlet.](/dotnet/api/System.Management.Automation.Cmdlet.ShouldContinue) Wing-Befehl von der Überschreibung der [System. Management. Automation. Cmdlet. ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) -Methode des Cmdlets Sample Stop-Proc gezeigt.

```csharp
if (criticalProcess &&!force)
{
  string message = String.Format
        ("The process \"{0}\" is a critical process and should not be stopped. Are you sure you wish to stop the process?",
        processName);

  // It is possible that ProcessRecord is called multiple times
  // when the Name parameter receives objects as input from the
  // pipeline. So to retain YesToAll and NoToAll input that the
  // user may enter across multiple calls to ProcessRecord, this
  // information is stored as private members of the cmdlet.
  if (!ShouldContinue(message, "Warning!",
                      ref yesToAll,
                      ref noToAll))
  {
    continue;
  }
} // if (criticalProcess...
```

## <a name="stopping-input-processing"></a>Beenden der Eingabe Verarbeitung

Die Eingabe Verarbeitungsmethode eines Cmdlets, das Systemänderungen vornimmt, muss eine Möglichkeit zum Beenden der Verarbeitung von Eingaben bereitstellen. Bei diesem Stop-Proc Cmdlet wird von der [System. Management. Automation. Cmdlet. ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) -Methode der System. [Diagnostics. Process. Kill *](/dotnet/api/System.Diagnostics.Process.Kill) -Methode aufgerufen. Da der- `PassThru` Parameter auf festgelegt ist, wird von `true` [System. Management. Automation. Cmdlet. ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) auch [System. Management. Automation. Cmdlet. Write Object](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject) aufgerufen, um das Prozess Objekt an die Pipeline zu senden.

## <a name="code-sample"></a>Codebeispiel

Den gesamten c#-Beispielcode finden Sie unter [StopProcessSample01 Sample](./stopprocesssample01-sample.md).

## <a name="defining-object-types-and-formatting"></a>Definieren von Objekttypen und Formatierung

Windows PowerShell übergibt Informationen zwischen Cmdlets mithilfe von .NET-Objekten. Folglich muss ein Cmdlet möglicherweise seinen eigenen Typ definieren, oder das Cmdlet muss möglicherweise einen vorhandenen Typ erweitern, der von einem anderen Cmdlet bereitgestellt wird. Weitere Informationen zum Definieren neuer Typen oder zum Erweitern vorhandener Typen finden Sie unter [Erweitern von Objekttypen und Formatierung](/previous-versions//ms714665(v=vs.85)).

## <a name="building-the-cmdlet"></a>Cmdlet wird aufgebaut

Nachdem ein Cmdlet implementiert wurde, muss es über ein Windows PowerShell-Snap-in in Windows PowerShell registriert werden. Weitere Informationen zum Registrieren von Cmdlets finden [Sie unter Registrieren von Cmdlets, Anbietern und Host Anwendungen](/previous-versions//ms714644(v=vs.85)).

## <a name="testing-the-cmdlet"></a>Testen des Cmdlets

Wenn das Cmdlet bei Windows PowerShell registriert wurde, können Sie es in der Befehlszeile testen. Es folgen mehrere Tests, bei denen das Stop-Proc-Cmdlet getestet wird. Weitere Informationen zur Verwendung von Cmdlets über die Befehlszeile finden Sie unter [Getting Started with Windows PowerShell](/powershell/scripting/getting-started/getting-started-with-windows-powershell).

- Starten Sie Windows PowerShell, und verwenden Sie das Cmdlet "Stop-Proc", um die Verarbeitung wie unten dargestellt zu starten Da das Cmdlet den `Name` Parameter als obligatorisch angibt, fragt das Cmdlet den Parameter ab.

    ```powershell
    PS> stop-proc
    ```

    Die folgende Ausgabe wird angezeigt.

    ```
    Cmdlet stop-proc at command pipeline position 1
    Supply values for the following parameters:
    Name[0]:
    ```

- Nun verwenden wir das Cmdlet, um den Prozess mit dem Namen "Notepad" zu unterbinden. Mit dem-Cmdlet werden Sie aufgefordert, die Aktion zu bestätigen.

    ```powershell
    PS> stop-proc -Name notepad
    ```

    Die folgende Ausgabe wird angezeigt.

    ```
    Confirm
    Are you sure you want to perform this action?
    Performing operation "stop-proc" on Target "notepad (4996)".
    [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): Y
    ```

- Verwenden Sie Stop-Proc wie gezeigt, um den kritischen Prozess mit dem Namen "Winlogon" zu verhindern. Sie werden dazu aufgefordert, diese Aktion auszuführen, da dies dazu führt, dass das Betriebssystem neu gestartet wird.

    ```powershell
    PS> stop-proc -Name Winlogon
    ```

    Die folgende Ausgabe wird angezeigt.

    ```Output
    Confirm
    Are you sure you want to perform this action?
    Performing operation "stop-proc" on Target "winlogon (656)".
    [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): Y
    Warning!
    The process " winlogon " is a critical process and should not be stopped. Are you sure you wish to stop the process?
    [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): N
    ```

- Versuchen Sie jetzt, den Winlogon-Prozess anzuhalten, ohne eine Warnung zu erhalten. Beachten Sie, dass dieser Befehls Eintrag den- `Force` Parameter verwendet, um die Warnung zu überschreiben.

    ```powershell
    PS> stop-proc -Name winlogon -Force
    ```

    Die folgende Ausgabe wird angezeigt.

    ```Output
    Confirm
    Are you sure you want to perform this action?
    Performing operation "stop-proc" on Target "winlogon (656)".
    [Y] Yes  [A] Yes to All  [N] No  [L] No to All  [S] Suspend  [?] Help (default is "Y"): N
    ```

## <a name="see-also"></a>Weitere Informationen

[Hinzufügen von Parametern, die Command-Line Eingabe verarbeiten](./adding-parameters-that-process-command-line-input.md)

[Erweitern von Objekttypen und Formatierung](/previous-versions//ms714665(v=vs.85))

[Registrieren von Cmdlets, Anbietern und Host Anwendungen](/previous-versions//ms714644(v=vs.85))

[Windows PowerShell SDK](../windows-powershell-reference.md)

[Cmdlet-Beispiele](./cmdlet-samples.md)
