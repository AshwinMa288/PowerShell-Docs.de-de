---
ms.date: 09/13/2016
ms.topic: reference
title: Deklarieren von dynamischen Parametern
description: Deklarieren von dynamischen Parametern
ms.openlocfilehash: 0f5a8f249b414663aa9702a908ea5c8ca24755ff
ms.sourcegitcommit: ba7315a496986451cfc1296b659d73ea2373d3f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "92667078"
---
# <a name="how-to-declare-dynamic-parameters"></a>Deklarieren von dynamischen Parametern

Dieses Beispiel zeigt, wie Sie dynamische Parameter definieren, die dem Cmdlet zur Laufzeit hinzugefügt werden. In diesem Beispiel wird der `Department` Parameter zum Cmdlet hinzugefügt, wenn der Benutzer den `Employee` Switch-Parameter angibt. Weitere Informationen zu dynamischen Parametern finden [Sie unter Cmdlet Dynamic Parameters](./cmdlet-dynamic-parameters.md).

## <a name="to-define-dynamic-parameters"></a>So definieren Sie dynamische Parameter

1. Fügen Sie in der Cmdlet-Klassen Deklaration die [System. Management. Automation. idynamicparameters](/dotnet/api/System.Management.Automation.IDynamicParameters) -Schnittstelle wie gezeigt hinzu.

   ```csharp
   public class SendGreetingCommand : Cmdlet, IDynamicParameters
   ```

2. Aufrufen der [System. Management. Automation. idynamicparameters. getdynamicparameters *](/dotnet/api/System.Management.Automation.IDynamicParameters.GetDynamicParameters) -Methode, die das Objekt zurückgibt, in dem die dynamischen Parameter definiert sind. In diesem Beispiel wird die-Methode aufgerufen, wenn der- `Employee` Parameter angegeben wird.

   ```csharp
   public object GetDynamicParameters()
   {
       if (employee)
       {
         context= new SendGreetingCommandDynamicParameters();
         return context;
       }
       return null;
   }
   private SendGreetingCommandDynamicParameters context;
   ```

3. Deklarieren Sie eine Klasse, die die dynamischen Parameter definiert, die hinzugefügt werden sollen. Sie können die Attribute verwenden, die Sie zum Deklarieren der statischen Cmdlet-Parameter verwendet haben, um die dynamischen Parameter zu deklarieren.

   ```csharp
   public class SendGreetingCommandDynamicParameters
   {
     [Parameter]
     [ValidateSet ("Marketing", "Sales", "Development")]
     public string Department
     {
       get { return department; }
       set { department = value; }
     }
     private string department;
   }
   ```

## <a name="example"></a>Beispiel

In diesem Beispiel wird der- `Department` Parameter hinzugefügt, wenn der Benutzer den- `Employee` Parameter angibt. Der `Department` -Parameter ist ein optionaler Parameter, und das validateset-Attribut wird verwendet, um die zulässigen Argumente anzugeben.

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
using System.Management.Automation;     // PowerShell assembly.

namespace SendGreeting
{
  // Declare the cmdlet class that supports the
  // IDynamicParameters interface.
  [Cmdlet(VerbsCommunications.Send, "Greeting")]
  public class SendGreetingCommand : Cmdlet, IDynamicParameters
  {
    // Declare the parameters for the cmdlet.
    [Parameter(Mandatory = true)]
    public string Name
    {
      get { return name; }
      set { name = value; }
    }
    private string name;

    [Parameter]
    [Alias ("FTE")]
    public SwitchParameter Employee
    {
      get { return employee; }
      set { employee = value; }
    }
    private Boolean employee;

    // Implement GetDynamicParameters to
    // retrieve the dynamic parameter.
    public object GetDynamicParameters()
    {
      if (employee)
      {
        context= new SendGreetingCommandDynamicParameters();
        return context;
      }
      return null;
   }
   private SendGreetingCommandDynamicParameters context;

    // Overide the ProcessRecord method to process the
    // supplied user name and write out a greeting to
    // the user by calling the WriteObject method.
    protected override void ProcessRecord()
    {
      WriteObject("Hello " + name + "! ");
      if (employee)
      {
        WriteObject("Department: " + context.Department);
      }
    }
  }

  // Define the dynamic parameters to be added
  public class SendGreetingCommandDynamicParameters
  {
    [Parameter]
    [ValidateSet ("Marketing", "Sales", "Development")]
    public string Department
    {
      get { return department; }
      set { department = value; }
    }
    private string department;
  }
}
```

## <a name="see-also"></a>Weitere Informationen

[System. Management. Automation. runtimedefinedparameterdictionary](/dotnet/api/System.Management.Automation.RuntimeDefinedParameterDictionary)

[System. Management. Automation. idynamicparameters. getdynamicparameters *](/dotnet/api/System.Management.Automation.IDynamicParameters.GetDynamicParameters)

[Dynamische Cmdlet-Parameter](./cmdlet-dynamic-parameters.md)

[Windows PowerShell SDK](../windows-powershell-reference.md)
