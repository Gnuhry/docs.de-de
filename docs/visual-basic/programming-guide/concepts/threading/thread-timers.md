---
title: Threadzeitgeber (Visual Basic)
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 809cba93-cc93-4e21-afda-f299f9a39818
caps.latest.revision: "3"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: b828476301424ca767e2b581c173d6a2dcd184ed
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="thread-timers-visual-basic"></a>Threadzeitgeber (Visual Basic)
Die <xref:System.Threading.Timer?displayProperty=nameWithType>-Klasse eignet sich für eine Aufgabe, die in regelmäßigen Abständen in einem separaten Thread ausgeführt wird. Beispielsweise können Sie einen Threadzeitgeber verwenden, um den Status und die Integrität einer Datenbank zu überprüfen oder wichtige Dateien zu sichern.  
  
## <a name="thread-timer-example"></a>Beispiel für Threadzeitgeber  
 Im folgenden Beispiel wird eine Aufgabe alle zwei Sekunden gestartet, und ein Flag genutzt, das die <xref:System.IDisposable.Dispose%2A>-Methode initiiert, die den Timer anhält. In diesem Beispiel wird der Status an das Ausgabefenster übermittelt.  
  
```vb  
Private Class StateObjClass  
    ' Used to hold parameters for calls to TimerTask.  
    Public SomeValue As Integer  
    Public TimerReference As System.Threading.Timer  
    Public TimerCanceled As Boolean  
End Class  
  
Public Sub RunTimer()  
    Dim StateObj As New StateObjClass  
    StateObj.TimerCanceled = False  
    StateObj.SomeValue = 1  
    Dim TimerDelegate As New System.Threading.TimerCallback(AddressOf TimerTask)  
    ' Create a timer that calls a procedure every 2 seconds.  
    ' Note: There is no Start method; the timer starts running as soon as   
    ' the instance is created.  
    Dim TimerItem As New System.Threading.Timer(TimerDelegate, StateObj,  
                                                2000, 2000)  
    ' Save a reference for Dispose.  
    StateObj.TimerReference = TimerItem  
  
    ' Run for ten loops.  
    While StateObj.SomeValue < 10  
        ' Wait one second.  
        System.Threading.Thread.Sleep(1000)  
    End While  
  
    ' Request Dispose of the timer object.  
    StateObj.TimerCanceled = True  
End Sub  
  
Private Sub TimerTask(ByVal StateObj As Object)  
    Dim State As StateObjClass = CType(StateObj, StateObjClass)  
    ' Use the interlocked class to increment the counter variable.  
    System.Threading.Interlocked.Increment(State.SomeValue)  
    System.Diagnostics.Debug.WriteLine("Launched new thread  " & Now.ToString)  
    If State.TimerCanceled Then  
        ' Dispose Requested.  
        State.TimerReference.Dispose()  
        System.Diagnostics.Debug.WriteLine("Done  " & Now)  
    End If  
End Sub  
```  
  
 Threadzeitgeber sind besonders nützlich, wenn das Objekt <xref:System.Windows.Forms.Timer?displayProperty=nameWithType> nicht verfügbar ist, z.B. wenn Sie Konsolenanwendungen entwickeln.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Threading>  
 [Multithreadanwendungen (Visual Basic)](../../../../visual-basic/programming-guide/concepts/threading/multithreaded-applications.md)
