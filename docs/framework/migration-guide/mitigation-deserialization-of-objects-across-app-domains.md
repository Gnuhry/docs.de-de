---
title: "Minderung: Deserialisierung von Objekten über App-Domänen"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 30c2d66c-04a8-41a5-ad31-646b937f61b5
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: c42d3274fcb03bc523367ba71c857144b2d78b72
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="mitigation-deserialization-of-objects-across-app-domains"></a>Minderung: Deserialisierung von Objekten über App-Domänen
In Fällen, in denen eine App zwei oder mehr App-Domänen mit unterschiedlichen Anwendungsbasen verwendet, löst der Versuch, Objekte im logischen Aufrufkontext über App-Domänen hinweg zu deserialisieren, eine Ausnahme aus.  
  
## <a name="diagnosing-the-issue"></a>Diagnose des Problems  
 Das Problem tritt bei der folgenden Abfolge von Bedingungen auf:  
  
1.  Eine Anwendung verwendet zwei oder mehr App-Domänen mit unterschiedlichen Anwendungsbasen.  
  
2.  Einige Typen werden explizit zu <xref:System.Runtime.Remoting.Messaging.LogicalCallContext> hinzugefügt, indem eine Methode wie <xref:System.Runtime.Remoting.Messaging.LogicalCallContext.SetData%2A?displayProperty=nameWithType> oder <xref:System.Runtime.Remoting.Messaging.CallContext.LogicalSetData%2A?displayProperty=nameWithType> aufgerufen wird. Diese Typen werden nicht als serialisierbar markiert und werden nicht im globalen Assemblycache gespeichert.  
  
3.  Später versucht Code, der in der nicht standardmäßigen App-Domäne ausgeführt wird, einen Wert aus einer Konfigurationsdatei zu lesen oder XML für die Deserialisierung eines Objekts zu verwenden.  
  
4.  Um aus einer Konfigurationsdatei zu lesen oder das Objekt zu deserialisieren, versucht ein <xref:System.Xml.XmlReader>-Objekt auf das Konfigurationssystem zuzugreifen.  
  
5.  Wenn das Konfigurationssystem noch nicht initialisiert wurde, muss es seine Initialisierung abschließen. Dies bedeutet unter anderem, dass die Laufzeit wie folgt einen stabilen Pfad für ein Konfigurationssystem erstellen muss:  
  
    1.  Sie sucht nach einem Beweis für die nicht standardmäßige App-Domäne.  
  
    2.  Sie versucht, den Beweis für die nicht standardmäßige App-Domäne auf Grundlage der Standard-App-Domäne zu berechnen.  
  
    3.  Der Aufruf, um einen Beweis für die Standard-App-Domäne zu erhalten, löst einen Aufruf über die App-Domänen hinweg auf, der von der nicht standardmäßigen App-Domäne zur Standard-App-Domäne verläuft.  
  
    4.  Im Rahmen des über die App-Domänengrenzen hinweg geltenden Vertrags in .NET Framework muss der Inhalt des logischen Aufrufkontexts auch über App-Domänengrenzen hinweg gemarshallt werden.  
  
6.  Da die Typen im logischen Aufrufkontext nicht in der Standard-App-Domäne aufgelöst werden können, wird eine Ausnahme ausgelöst.  
  
## <a name="mitigation"></a>Problemumgehung  
 Gehen Sie wie folgt vor, um dieses Problem zu umgehen:  
  
1.  Suchen Sie bei Auftreten der Ausnahme nach dem Aufruf von `get_Evidence` in der Aufrufliste. Bei der Ausnahme kann es sich um verschiedene Ausnahmen handeln, einschließlich <xref:System.IO.FileNotFoundException> und <xref:System.Runtime.Serialization.SerializationException>.  
  
2.  Identifizieren Sie die Position in der App, an der keine Objekte zum logischen Aufrufkontext hinzugefügt werden, und fügen Sie folgenden Code hinzu:  
  
    ```  
    System.Configuration.ConfigurationManager.GetSection("system.xml/xmlReader");  
    ```  
  
## <a name="see-also"></a>Siehe auch  
 [Änderungen zur Laufzeit](../../../docs/framework/migration-guide/runtime-changes-in-the-net-framework-4-5-1.md)
