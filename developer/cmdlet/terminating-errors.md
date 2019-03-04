---
title: Beenden Sie die Fehler | Microsoft-Dokumentation
ms.custom: ''
ms.date: 09/13/2016
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b804e738-aefa-41bb-9649-f9ed897fd96c
caps.latest.revision: 8
ms.openlocfilehash: c593da1f7bdb6ddf09ba8d5de92af730687dbc8a
ms.sourcegitcommit: b6871f21bd666f9cd71dd336bb3f844cf472b56c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/03/2019
ms.locfileid: "56859236"
---
# <a name="terminating-errors"></a>Fehler mit Abbruch

In diesem Thema wird erläutert, die Methode zum Bericht Fehler beendet. Außerdem wird erläutert, wie die Methode aus, in dem-Cmdlet aufrufen, und es wird erläutert, die Ausnahmen, die von der Windows PowerShell-Laufzeit zurückgegeben werden können, wenn die Methode aufgerufen wird.

Wenn ein Abbruch Fehler auftritt, das Cmdlet sollte der Fehler gemeldet, durch den Aufruf der [System.Management.Automation.Cmdlet.Throwterminatingerror*](/dotnet/api/System.Management.Automation.Cmdlet.ThrowTerminatingError) Methode. Diese Methode ermöglicht das Cmdlet, um einen Fehlerdatensatz zu senden, der die Bedingung beschreibt, die den Fehler mit Abbruch verursacht hat. Weitere Informationen zu Datensätzen, finden Sie unter [Windows PowerShell-Fehlerdatensätze](./windows-powershell-error-records.md).

Wenn die [System.Management.Automation.Cmdlet.Throwterminatingerror*](/dotnet/api/System.Management.Automation.Cmdlet.ThrowTerminatingError) -Methode aufgerufen wird, die Windows PowerShell-Laufzeit dauerhaft beendet die Ausführung der Pipeline und löst eine [ System.Management.Automation.Pipelinestoppedexception](/dotnet/api/System.Management.Automation.PipelineStoppedException) Ausnahme. Alle nachfolgenden Verwendungsversuche Aufrufen [System.Management.Automation.Cmdlet.Writeobject*](/dotnet/api/System.Management.Automation.Cmdlet.WriteObject), [System.Management.Automation.Cmdlet.Writeerror*](/dotnet/api/System.Management.Automation.Cmdlet.WriteError), oder mehrere andere APIs bewirkt, dass diese Aufrufe an das Auslösen einer [System.Management.Automation.Pipelinestoppedexception](/dotnet/api/System.Management.Automation.PipelineStoppedException) Ausnahme.

Die [System.Management.Automation.Pipelinestoppedexception](/dotnet/api/System.Management.Automation.PipelineStoppedException) Ausnahme kann auch auftreten, wenn ein anderes Cmdlet in der Pipeline einen Fehler mit Abbruch, meldet, wenn der Benutzer aufgefordert wurde, um die Pipeline zu beenden oder die Pipeline angehalten wurde vor dem Abschluss aus irgendeinem Grund. Muss das Cmdlet nicht zum Abfangen der [System.Management.Automation.Pipelinestoppedexception](/dotnet/api/System.Management.Automation.PipelineStoppedException) Ausnahme, wenn Ressourcen oder seinen internen Status Cleanup öffnen müssen.

Cmdlets können eine beliebige Anzahl von Ausgabeobjekte oder Fehler ohne Abbruch schreiben, bevor gemeldet wird, einen Fehler mit Abbruch. Allerdings der Fehler mit Abbruch dauerhaft beendet werden, der Pipeline, und keine weiteren Ausgabe, Fehler, Abbruch oder Fehler ohne Abbruch gemeldet werden können.

Cmdlets aufrufen können [System.Management.Automation.Cmdlet.Throwterminatingerror*](/dotnet/api/System.Management.Automation.Cmdlet.ThrowTerminatingError) nur aus dem Thread, der Namen der [System.Management.Automation.Cmdlet.Beginprocessing*](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing), [ System.Management.Automation.Cmdlet.Processrecord*](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord), oder [System.Management.Automation.Cmdlet.Endprocessing*](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing) Geben Sie die Verarbeitungsmethode aus. Versuchen Sie nicht, rufen Sie [System.Management.Automation.Cmdlet.Throwterminatingerror*](/dotnet/api/System.Management.Automation.Cmdlet.ThrowTerminatingError) oder [System.Management.Automation.Cmdlet.Writeerror*](/dotnet/api/System.Management.Automation.Cmdlet.WriteError) aus einem anderen Thread. Stattdessen müssen die Fehler an den Hauptthread übermittelt werden.

Es ist möglich, für ein Cmdlet, um eine Ausnahme auszulösen, in seiner Implementierung von der [System.Management.Automation.Cmdlet.Beginprocessing*](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing), [System.Management.Automation.Cmdlet.Processrecord*](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord), oder [System.Management.Automation.Cmdlet.Endprocessing*](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing) Methode. Eine Ausnahme ausgelöst, die von diesen Methoden (mit Ausnahme von ein paar schwerwiegenden fehlerbedingungen, die den Windows PowerShell-Host zu beenden) wird als ein Fehler mit Abbruch interpretiert, die die Pipeline, aber nicht die Windows PowerShell als Ganzes beendet. (Dies gilt nur für die wichtigsten Cmdlet-Thread. Nicht abgefangene Ausnahmen in Threads, die vom Cmdlet erzeugt an, ist im Allgemeinen den Windows PowerShell-Host.) Wir empfehlen die Verwendung [System.Management.Automation.Cmdlet.Throwterminatingerror*](/dotnet/api/System.Management.Automation.Cmdlet.ThrowTerminatingError) anstatt eine Ausnahme auszulösen, da der Fehlerdatensatz Weitere Informationen zu den Fehlerzustand bereitstellt, dies ist hilfreich, um der Endbenutzer. Cmdlets muss die Richtlinie verwalteten Code für das Abfangen und behandeln alle Ausnahmen berücksichtigt (`catch (Exception e)`). Konvertieren Sie nur von Ausnahmen eines bekannten und erwarteten Typen, in der Error-Datensätze.

## <a name="see-also"></a>Weitere Informationen

[System.Management.Automation.Cmdlet.Beginprocessing*](/dotnet/api/System.Management.Automation.Cmdlet.BeginProcessing)

[System.Management.Automation.Cmdlet.Endprocessing*](/dotnet/api/System.Management.Automation.Cmdlet.EndProcessing)

[System.Management.Automation.Cmdlet.Processrecord*](/dotnet/api/System.Management.Automation.Cmdlet.ProcessRecord)

[System.Management.Automation.Pipelinestoppedexception](/dotnet/api/System.Management.Automation.PipelineStoppedException)

[System.Management.Automation.Cmdlet.Throwterminatingerror*](/dotnet/api/System.Management.Automation.Cmdlet.ThrowTerminatingError)

[System.Management.Automation.Cmdlet.Writeerror*](/dotnet/api/System.Management.Automation.Cmdlet.WriteError)

[Windows PowerShell-Error-Datensätze](./windows-powershell-error-records.md)

[Schreiben eines Windows PowerShell-Cmdlets](./writing-a-windows-powershell-cmdlet.md)