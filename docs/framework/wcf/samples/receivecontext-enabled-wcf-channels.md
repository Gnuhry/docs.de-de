---
title: "ReceiveContext-aktivierte WCF-Kanäle"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d990d119-7321-4b8c-852b-10256f59f9b0
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 729bf8bd1371bf64b9b05a235331120608824083
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="receivecontext-enabled-wcf-channels"></a>ReceiveContext-aktivierte WCF-Kanäle
In diesem Beispiel wird die Nützlichkeit WCF-Kanälen mit Aktivierung von <xref:System.ServiceModel.Channels.ReceiveContext> erläutert. Im Beispiel wird ein Dienst für die Suche nach dem Produkt von zwei Zahlen mithilfe eines NetMSMQ-Kanals implementiert.  
  
 Mit der <xref:System.ServiceModel.Channels.ReceiveContext>-Klasse kann eine Anwendung entscheiden, ob auf die Meldung zugegriffen werden oder sie für die weitere Verarbeitung in der Warteschlange belassen werden soll, selbst nachdem der Inhalt der Meldung überprüft wurde. In diesem Beispiel sendet ein Client zufällige ganze Zahlen an eine Transaktionswarteschlange. Der `ProductCalculator`-Dienst empfängt die Meldungen und überprüft den Meldungsinhalt, der aus ganzen Zahlen besteht, um zu bestimmen, ob das Produkt berechnet werden kann. Wenn der Dienstvorgang das Produkt nicht berechnet, wird die Meldung zurück an die Warteschlange gesendet und kann erneut vom Dienst empfangen werden, der die Warteschlange überwacht.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren:  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] - und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] -Beispiele herunterzuladen. Dieses Beispiel befindet sich im folgenden Verzeichnis:  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Binding\Net\MSMQ\ReceiveContextProductGenerator`  
  
#### <a name="to-use-this-sample"></a>So verwenden Sie dieses Beispiel  
  
1.  Stellen Sie sicher, dass Microsoft Message Queuing (MSMQ) installiert ist.  
  
    1.  So installieren Sie MSMQ unter [!INCLUDE[lserver](../../../../includes/lserver-md.md)]  
  
        1.  In **Server-Manager**, klicken Sie auf **Funktionen**.  
  
        2.  Im rechten Bereich unter **Featureübersicht**, klicken Sie auf **Features hinzufügen**.  
  
        3.  Erweitern Sie im jetzt geöffneten Fenster **Message Queuing**.  
  
        4.  Erweitern Sie **Message Queuing-Dienste**.  
  
        5.  Klicken Sie auf **Verzeichnisdienstintegration** (für Computer Mitglied einer Domäne), und klicken Sie dann auf **HTTP-Unterstützung**.  
  
        6.  Klicken Sie auf **Weiter**, und klicken Sie dann auf **installieren**.  
  
    2.  So installieren Sie MSMQ unter [!INCLUDE[wv](../../../../includes/wv-md.md)]  
  
        1.  Open **in der Systemsteuerung**.  
  
        2.  Klicken Sie auf **Programme** und dann unter **Programme und Funktionen**, klicken Sie auf **Windows-Funktionen ein- oder ausschalten**.  
  
        3.  Erweitern Sie **Microsoft Message Queue (MSMQ) Server**, erweitern Sie **Microsoft Message Queue (MSMQ)-serverkernkomponenten**, und wählen Sie dann die Kontrollkästchen für die Message Queuing-Funktionen installieren:  
  
            -   Message Queuing Server  
  
            -   MSMQ-Active Directory-Domänendienstintegration (bei Computern, die einer Domäne zugewiesen sind)  
  
            -   MSMQ-HTTP-Unterstützung  
  
        4.  Klicken Sie auf **OK**.  
  
        5.  Wenn Sie aufgefordert werden, den Computer neu starten, klicken Sie auf **OK** um die Installation abzuschließen.  
  
2.  Stellen Sie sicher, dass [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] auf dem Computer installiert ist.  
  
3.  Öffnen Sie mit [!INCLUDE[vs_current_long](../../../../includes/vs-current-long-md.md)] die ReceiveContextProductGenerator.sln-Projektmappendatei.  
  
4.  Drücken Sie STRG+UMSCHALT+B, um die Projektmappe zu erstellen.  
  
5.  Drücken Sie STRG+F5, um die Projektmappe auszuführen.
