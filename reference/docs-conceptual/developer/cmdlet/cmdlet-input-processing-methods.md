---
ms.date: 09/13/2016
ms.topic: reference
title: Cmdlet-Eingabeverarbeitungsmethoden
description: Cmdlet-Eingabeverarbeitungsmethoden
ms.openlocfilehash: e1a7b58517d6285250edbf16d14810388c242218
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92653396"
---
# <a name="cmdlet-input-processing-methods"></a>Cmdlet-Eingabeverarbeitungsmethoden

Cmdlets müssen eine oder mehrere der in diesem Thema beschriebenen Eingabe Verarbeitungsmethoden überschreiben, um Ihre Arbeit zu erledigen.
Diese Methoden ermöglichen es dem Cmdlet, Vorgänge der vorab Verarbeitung, der Eingabe Verarbeitung und der Nachbearbeitung auszuführen.
Diese Methoden ermöglichen auch das Abbrechen der Cmdlet-Verarbeitung.
Ein ausführlicheres Beispiel für die Verwendung dieser Methoden finden Sie unter [selectstr-Tutorial](selectstr-tutorial.md).

## <a name="pre-processing-operations"></a>Vorverarbeitungs Vorgänge

Cmdlets sollten die [System. Management. Automation. Cmdlet. BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing) -Methode überschreiben, um Vorverarbeitungs Vorgänge hinzuzufügen, die für alle Datensätze gültig sind, die später vom Cmdlet verarbeitet werden.
Wenn PowerShell eine Befehls Pipeline verarbeitet, ruft PowerShell diese Methode für jede Instanz des Cmdlets in der Pipeline einmal auf.
Weitere Informationen dazu, wie PowerShell die Befehls Pipeline aufruft, finden Sie unter [Cmdlet processing Lifecycle](/previous-versions/ms714429(v=vs.85)).

Der folgende Code zeigt eine Implementierung der BeginProcessing-Methode.

```csharp
protected override void BeginProcessing()
{
  // Replace the WriteObject method with the logic required by your cmdlet.
  WriteObject("This is a test of the BeginProcessing template.");
}
```

## <a name="input-processing-operations"></a>Eingabe Verarbeitungsvorgänge

Cmdlets können die [System. Management. Automation. Cmdlet. ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) -Methode überschreiben, um die Eingabe zu verarbeiten, die an das Cmdlet gesendet wird.
Wenn PowerShell eine Befehls Pipeline verarbeitet, ruft PowerShell diese Methode für jeden Eingabedaten Satz auf, der vom Cmdlet verarbeitet wird.
Weitere Informationen dazu, wie PowerShell die Befehls Pipeline aufruft, finden Sie unter [Cmdlet processing Lifecycle](/previous-versions/ms714429(v=vs.85)).

Der folgende Code zeigt eine Implementierung der ProcessRecord-Methode.

```csharp
protected override void ProcessRecord()
{
  // Replace the WriteObject method with the logic required by your cmdlet.
  WriteObject("This is a test of the ProcessRecord template.");
}
```

## <a name="post-processing-operations"></a>Vorgänge nach der Verarbeitung

Cmdlets sollten die [System. Management. Automation. Cmdlet. EndProcessing](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing) -Methode überschreiben, um alle nach Verarbeitungsvorgänge hinzuzufügen, die für alle vom Cmdlet verarbeiteten Datensätze gültig sind.
Beispielsweise muss das Cmdlet möglicherweise Objektvariablen bereinigen, nachdem die Verarbeitung abgeschlossen ist.

Wenn PowerShell eine Befehls Pipeline verarbeitet, ruft PowerShell diese Methode für jede Instanz des Cmdlets in der Pipeline einmal auf.
Es ist jedoch wichtig zu beachten, dass die PowerShell-Runtime die EndProcessing-Methode nicht aufruft, wenn das Cmdlet in der Mitte durch die Eingabe Verarbeitung abgebrochen wird oder wenn in einem beliebigen Teil des Cmdlets ein Abbruch Fehler auftritt.
Aus diesem Grund sollte ein Cmdlet, das die Objekt Bereinigung erfordert, das komplette [System. iverwerf-](/dotnet/api/System.IDisposable) Muster implementieren, einschließlich eines Finalizers, damit die Laufzeit die EndProcessing-und die [System. iverwerf.](/dotnet/api/System.IDisposable.Dispose) verwerfen-Methode am Ende der Verarbeitung abrufen kann.
Weitere Informationen dazu, wie PowerShell die Befehls Pipeline aufruft, finden Sie unter [Cmdlet processing Lifecycle](/previous-versions/ms714429(v=vs.85)).

Der folgende Code zeigt eine Implementierung der EndProcessing-Methode.

```csharp
protected override void EndProcessing()
{
  // Replace the WriteObject method with the logic required by your cmdlet.
  WriteObject("This is a test of the EndProcessing template.");
}
```

## <a name="see-also"></a>Weitere Informationen

[System. Management. Automation. Cmdlet. BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing)

[System. Management. Automation. Cmdlet. ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)

[System. Management. Automation. Cmdlet. EndProcessing](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing)

[SelectStr-Tutorial](selectstr-tutorial.md)

[System.IDisposable](/dotnet/api/System.IDisposable)

[Referenz zu Windows PowerShell](../windows-powershell-reference.md)
