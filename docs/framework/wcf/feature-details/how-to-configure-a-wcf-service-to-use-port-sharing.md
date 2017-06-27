---
title: "Vorgehensweise: Konfigurieren eines Windows Communication Foundation-Dienstes zum Durchf&#252;hren der Anschlussfreigabe | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 6400bc71-a858-4ac2-8d5a-caa72d3b5482
caps.latest.revision: 11
author: "Erikre"
ms.author: "erikre"
manager: "erikre"
caps.handback.revision: 11
---
# Vorgehensweise: Konfigurieren eines Windows Communication Foundation-Dienstes zum Durchf&#252;hren der Anschlussfreigabe
Der einfachste Weg, um die net.tcp:\/\/\-Anschlussfreigabe in Ihrer [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)]\-Anwendung zu verwenden, besteht darin, einen Dienst mit der <xref:System.ServiceModel.NetTcpBinding> verfügbar zu machen.  
  
 Diese Bindung verfügt über eine <xref:System.ServiceModel.NetTcpBinding.PortSharingEnabled%2A>\-Eigenschaft, die festlegt, ob die net.tcp:\/\/\-Anschlussfreigabe für den mit dieser Bindung zu konfigurierenden Dienst aktiviert ist.  
  
 Der folgende Vorgang zeigt, wie Sie die <xref:System.ServiceModel.NetTcpBinding>\-Klasse zum Öffnen eines Endpunkts am Uniform Resource Identifier \(URI\) net.tcp:\/\/localhost\/MyService verwenden können, zuerst im Code und dann mithilfe von Konfigurationselementen.  
  
### So aktivieren Sie die net.tcp:\/\/\-Anschlussfreigabe für eine NetTcpBinding im Code  
  
1.  Erstellen Sie einen Dienst, um einen Vertrag mit dem Namen `IMyService` zu implementieren und ihn in `MyService` umzubenennen.  
  
     [!code-csharp[c_ConfigurePortSharing#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_configureportsharing/cs/source.cs#1)]
     [!code-vb[c_ConfigurePortSharing#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_configureportsharing/vb/source.vb#1)]  
  
2.  Erstellen Sie eine Instanz der <xref:System.ServiceModel.NetTcpBinding>\-Klasse, und setzen Sie die <xref:System.ServiceModel.NetTcpBinding.PortSharingEnabled%2A>\-Eigenschaft auf `true` fest.  
  
     [!code-csharp[c_ConfigurePortSharing#2](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_configureportsharing/cs/source.cs#2)]
     [!code-vb[c_ConfigurePortSharing#2](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_configureportsharing/vb/source.vb#2)]  
  
3.  Erstellen Sie einen <xref:System.ServiceModel.ServiceHost>, und fügen Sie ihm den Dienstendpunkt für `MyService` hinzu, der die <xref:System.ServiceModel.NetTcpBinding>, für die die Anschlussfreigabe aktiviert wurde, verwendet und der am Endpunkt\-Adress\-URI "net.tcp:\/\/localhost\/MyService" eine Abhörung durchführt.  
  
     [!code-csharp[c_ConfigurePortSharing#3](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_configureportsharing/cs/source.cs#3)]
     [!code-vb[c_ConfigurePortSharing#3](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_configureportsharing/vb/source.vb#3)]  
  
    > [!NOTE]
    >  In diesem Beispiel wird der Standard\-TCP\-Anschluss 808 verwendet, da der Endpunkt\-Adress\-URI keine andere Anschlussnummer angibt.Da die Anschlussfreigabe explizit für die Transportbindung aktiviert wurde, kann dieser Dienst den Anschluss 808 für andere Dienste in anderen Vorgängen freigeben.Wenn die Anschlussfreigabe nicht zulässig wäre und eine andere Anwendung bereits den Anschluss 808 verwenden würde, würde dieser Dienst beim Öffnen eine <xref:System.ServiceModel.AddressAlreadyInUseException> ausgeben.  
  
### So aktivieren Sie die net.tcp:\/\/\-Anschlussfreigabe für eine NetTcpBinding in der Konfiguration  
  
1.  Das folgende Beispiel zeigt, wie Sie die Anschlussfreigabe aktivieren und den Dienstendpunkt mithilfe von Konfigurationselementen hinzufügen können.  
  
```  
<system.serviceModel>  
  <bindings>  
    <netTcpBinding name="portSharingBinding"   
                   portSharingEnabled="true" />  
  </bindings>  
  <services>  
    <service name="MyService">  
        <endpoint address="net.tcp://localhost/MyService"  
                  binding="netTcpBinding"  
                  contract="IMyService"  
                  bindingConfiguration="portSharingBinding" />  
    </service>  
  </services>  
</system.serviceModel>  
```  
  
## Siehe auch  
 [Net.TCP Port Sharing](http://msdn.microsoft.com/de-de/f13692ee-a179-4439-ae72-50db9534eded)   
 [Vorgehensweise: Aktivieren des Net.TCP\-Portfreigabediensts](../../../../docs/framework/wcf/feature-details/how-to-enable-the-net-tcp-port-sharing-service.md)