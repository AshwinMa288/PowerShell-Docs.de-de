---
title: Überschreiben von Eingabe Verarbeitungsmethoden | Microsoft-Dokumentation
ms.date: 09/13/2016
ms.openlocfilehash: b245dc56b78ce9b7f1dea80b5d4988057c2f125f
ms.sourcegitcommit: 0907b8c6322d2c7c61b17f8168d53452c8964b41
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/05/2020
ms.locfileid: "87784111"
---
# <a name="how-to-override-input-processing-methods"></a>Überschreiben von Eingabeverarbeitungsmethoden

In diesen Beispielen wird gezeigt, wie die Eingabe Verarbeitungsmethoden innerhalb eines Cmdlets überschrieben werden. Diese Methoden werden verwendet, um die folgenden Vorgänge auszuführen:

- Die [System. Management. Automation. Cmdlet. BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing) -Methode wird zum Ausführen von einmaligen Start Vorgängen verwendet, die für alle vom Cmdlet verarbeiteten Objekte gültig sind. Die Windows PowerShell-Laufzeit ruft diese Methode nur einmal auf.

- Die [System. Management. Automation. Cmdlet. ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) -Methode wird verwendet, um die Objekte zu verarbeiten, die an das Cmdlet übergeben werden. Die Windows PowerShell-Laufzeit ruft diese Methode für jedes Objekt auf, das an das Cmdlet übergeben wird.

- Die [System. Management. Automation. Cmdlet. EndProcessing](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing) -Methode wird verwendet, um einmal nach Verarbeitungsvorgänge auszuführen. Die Windows PowerShell-Laufzeit ruft diese Methode nur einmal auf.

## <a name="to-override-the-beginprocessing-method"></a>So überschreiben Sie die BeginProcessing-Methode

- Deklarieren Sie eine geschützte außer Kraft setzung der [System. Management. Automation. Cmdlet. BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing) -Methode.

Die folgende Klasse druckt eine Beispiel Nachricht. Um diese Klasse zu verwenden, ändern Sie das Verb und das Nomen im Cmdlet-Attribut, ändern Sie den Namen der Klasse, um das neue Verb und das neue Substantiv widerzuspiegeln, und fügen Sie dann die erforderliche Funktionalität zur außer Kraft setzung der [System. Management. Automation. Cmdlet. BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing) -Methode hinzu.

```csharp
[Cmdlet(VerbsDiagnostic.Test, "BeginProcessingClass")]
public class TestBeginProcessingClassTemplate : Cmdlet
{
  // Override the BeginProcessing method to add preprocessing
  //operations to the cmdlet.
  protected override void BeginProcessing()
  {
    // Replace the WriteObject method with the logic required
    // by your cmdlet. It is used here to generate the following
    // output:
    // "This is a test of the BeginProcessing template."
    WriteObject("This is a test of the BeginProcessing template.");
  }
}
```

## <a name="to-override-the-processrecord-method"></a>So überschreiben Sie die ProcessRecord-Methode

- Deklarieren Sie eine geschützte außer Kraft setzung der [System. Management. Automation. Cmdlet. ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) -Methode.

Die folgende Klasse druckt eine Beispiel Nachricht. Um diese Klasse zu verwenden, ändern Sie das Verb und das Nomen im Cmdlet-Attribut, ändern Sie den Namen der Klasse, um das neue Verb und das neue Substantiv widerzuspiegeln, und fügen Sie dann die erforderliche Funktionalität zur außer Kraft setzung der [System. Management. Automation. Cmdlet. ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord) -Methode hinzu.

```csharp
[Cmdlet(VerbsDiagnostic.Test, "ProcessRecordClass")]
public class TestProcessRecordClassTemplate : Cmdlet
{
    // Override the ProcessRecord method to add processing
    //operations to the cmdlet.
    protected override void ProcessRecord()
    {
        // Replace the WriteObject method with the logic required
        // by your cmdlet. It is used here to generate the following
        // output:
        // "This is a test of the ProcessRecord template."
        WriteObject("This is a test of the ProcessRecord template.");
    }
}

```

## <a name="to-override-the-endprocessing-method"></a>So überschreiben Sie die EndProcessing-Methode

- Deklarieren Sie eine geschützte außer Kraft setzung der [System. Management. Automation. Cmdlet. EndProcessing](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing) -Methode.

Die folgende Klasse druckt ein Beispiel. Um diese Klasse zu verwenden, ändern Sie das Verb und das Nomen im Cmdlet-Attribut, ändern Sie den Namen der Klasse, um das neue Verb und das neue Substantiv widerzuspiegeln, und fügen Sie dann die erforderliche Funktionalität zur außer Kraft setzung der [System. Management. Automation. Cmdlet. EndProcessing](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing) -Methode hinzu.

```csharp
[Cmdlet(VerbsDiagnostic.Test, "EndProcessingClass")]
public class TestEndProcessingClassTemplate : Cmdlet
{
  // Override the EndProcessing method to add postprocessing
  //operations to the cmdlet.
  protected override void EndProcessing()
  {
    // Replace the WriteObject method with the logic required
    // by your cmdlet. It is used here to generate the following
    // output:
    // "This is a test of the BeginProcessing template."
    WriteObject("This is a test of the EndProcessing template.");
  }
}
```

## <a name="see-also"></a>Weitere Informationen

[System. Management. Automation. Cmdlet. BeginProcessing](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing)

[System. Management. Automation. Cmdlet. EndProcessing](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing)

[System. Management. Automation. Cmdlet. ProcessRecord](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)

[Schreiben eines Windows PowerShell-Cmdlets](./writing-a-windows-powershell-cmdlet.md)
