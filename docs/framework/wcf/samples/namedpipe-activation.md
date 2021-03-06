---
title: NamedPipe-Aktivierung
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f3c0437d-006c-442e-bfb0-6b29216e4e29
caps.latest.revision: "28"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: cf2ca3fb6cf7e17c0c27a4b03d7c61c86d6961a6
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="namedpipe-activation"></a>NamedPipe-Aktivierung
In diesem Beispiel wird das Hosten eines Diensts veranschaulicht, der Windows Process Activation Services (WAS) zum Aktivieren eines Diensts verwendet, der über benannte Pipes kommuniziert. Dieses Beispiel basiert auf der [Einstieg](../../../../docs/framework/wcf/samples/getting-started-sample.md) und erfordert [!INCLUDE[wv](../../../../includes/wv-md.md)] ausgeführt.  
  
> [!NOTE]
>  Die Setupprozedur und die Buildanweisungen für dieses Beispiel befinden sich am Ende dieses Themas.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] - und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] -Beispiele herunterzuladen. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Services\Hosting\WASHost\NamedPipeActivation`  
  
## <a name="sample-details"></a>Beispieldetails  
 Das Beispiel besteht aus einem Clientkonsolenprogramm (.exe) und einer in einem von Windows Process Activation Services (WAS) aktivierten Arbeitsprozess gehosteten Dienstbibliothek (.dll). Die Clientaktivität ist im Konsolenfenster sichtbar.  
  
 Der Dienst implementiert einen Vertrag, der ein Anforderungs-Antwort-Kommunikationsmuster definiert. Der Vertrag wird von der `ICalculator`-Schnittstelle definiert, die mathematische Operationen (Addieren, Subtrahieren, Multiplizieren und Dividieren) verfügbar macht, wie im folgenden Beispielcode dargestellt.  
  
```  
[ServiceContract(Namespace="http://Microsoft.ServiceModel.Samples")]  
public interface ICalculator  
{  
    [OperationContract]  
    double Add(double n1, double n2);  
    [OperationContract]  
    double Subtract(double n1, double n2);  
    [OperationContract]  
    double Multiply(double n1, double n2);  
    [OperationContract]  
    double Divide(double n1, double n2);  
}  
```  
  
 Der Client stellt synchrone Anforderungen an eine gegebene mathematische Operation, und die Dienstimplementierung gibt das entsprechende Ergebnis zurück.  
  
```  
// Service class that implements the service contract.  
public class CalculatorService : ICalculator  
{  
    public double Add(double n1, double n2)  
    {  
        return n1 + n2;  
    }  
    public double Subtract(double n1, double n2)  
    {  
        return n1 - n2;  
    }  
    public double Multiply(double n1, double n2)  
    {  
        return n1 * n2;  
    }  
    public double Divide(double n1, double n2)  
    {  
        return n1 / n2;  
    }  
}  
```  
  
 Im Beispiel wird eine modifizierte `netNamedPipeBinding`-Bindung ohne Sicherheit verwendet. Die Bindung wird in den Konfigurationsdateien für den Client und Dienst angegeben. Der Bindungstyp für den Dienst wird im `binding`-Attribut des Endpunktelements angegeben (siehe folgende Beispielkonfiguration).  
  
 Wenn Sie eine gesicherte benannte Pipe-Bindung verwenden möchten, ändern Sie den Sicherheitsmodus des Servers in die gewünschte Sicherheitseinstellung, und führen Sie auf dem Client "svcutil.exe" erneut aus, um eine aktualisierte Clientkonfigurationsdatei zu erhalten.  
  
```xml  
<system.serviceModel>  
        <services>  
            <service name="Microsoft.ServiceModel.Samples.CalculatorService"  
               behaviorConfiguration="CalculatorServiceBehavior">  
  
        <!-- This endpoint is exposed at the base address provided by host: net.pipe://localhost/servicemodelsamples/service.svc  -->  
        <endpoint address=""   
                  binding="netNamedPipeBinding"  
                  bindingConfiguration="Binding1"   
                  contract="Microsoft.ServiceModel.Samples.ICalculator" />  
        <!-- the mex endpoint is explosed at net.pipe://localhost/servicemodelsamples/service.svc/mex -->  
        <endpoint address="mex"  
                  binding="mexNamedPipeBinding"  
                  contract="IMetadataExchange" />  
      </service>  
        </services>      
        <bindings>  
            <netNamedPipeBinding>  
                <binding name="Binding1" >  
                    <security mode = "None">  
                    </security>  
                </binding >  
            </netNamedPipeBinding>  
        </bindings>  
  
    <!--For debugging purposes set the includeExceptionDetailInFaults attribute to true-->  
    <behaviors>  
      <serviceBehaviors>  
        <behavior name="CalculatorServiceBehavior">  
          <serviceMetadata />  
          <serviceDebug includeExceptionDetailInFaults="False" />  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
  
  </system.serviceModel>  
```  
  
 Die Endpunktinformation des Clients wird wie im folgenden Beispielcode dargestellt konfiguriert.  
  
```xml  
<system.serviceModel>  
  
    <client>  
      <endpoint name=""  
                          address="net.pipe://localhost/servicemodelsamples/service.svc"   
                          binding="netNamedPipeBinding"   
                          bindingConfiguration="Binding1"   
                          contract="Microsoft.ServiceModel.Samples.ICalculator" />  
    </client>  
  
    <bindings>  
  
      <!--  Following is the expanded configuration section for a NetNamedPipeBinding.  
            Each property is configured with the default value.   -->  
  
      <netNamedPipeBinding>  
        <binding name="Binding1"   
                         maxBufferSize="65536"  
                         maxConnections="10">  
          <security mode = "None">  
          </security>  
        </binding >  
  
      </netNamedPipeBinding>  
    </bindings>  
  
  </system.serviceModel>  
```  
  
 Wenn Sie das Beispiel ausführen, werden die Anforderungen und Antworten für den Vorgang im Clientkonsolenfenster angezeigt. Drücken Sie im Clientfenster die EINGABETASTE, um den Client zu schließen.  
  
```  
Add(100,15.99) = 115.99  
Subtract(145,76.54) = 68.46  
Multiply(9,81.25) = 731.25  
Divide(22,7) = 3.14285714285714  
  
Press <ENTER> to terminate client.  
```  
  
#### <a name="to-set-up-build-and-run-the-sample"></a>So können Sie das Beispiel einrichten, erstellen und ausführen  
  
1.  Stellen Sie sicher, dass [!INCLUDE[iisver](../../../../includes/iisver-md.md)] installiert ist. [!INCLUDE[iisver](../../../../includes/iisver-md.md)] ist für die WAS-Aktivierung erforderlich.  
  
2.  Stellen Sie sicher, die von Ihnen ausgeführte der [Setupprozedur für die Windows Communication Foundation-Beispiele zum einmaligen](../../../../docs/framework/wcf/samples/one-time-setup-procedure-for-the-wcf-samples.md).  
  
     Außerdem müssen Sie die [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Aktivierungskomponenten für andere Protokolle als HTTP installieren:  
  
    1.  Aus der **starten** Menü wählen **Systemsteuerung**.  
  
    2.  Wählen Sie **Programme und Funktionen**.  
  
    3.  Klicken Sie auf **aktivieren oder Deaktivieren von Windows-Komponenten**.  
  
    4.  Erweitern Sie die **Microsoft .NET Framework 3.0** Knoten, und überprüfen Sie die **Windows Communication Foundation-nicht-HTTP-Aktivierung** Funktion.  
  
3.  Konfigurieren Sie den Windows Process Activation Service (WAS), um die Aktivierung benannter Pipes zu unterstützen.  
  
     Zur Vereinfachung sind die folgenden beiden Schritte in der Batchdatei "AddNetPipeSiteBinding.cmd" implementiert, die sich im Beispielverzeichnis befindet.  
  
    1.  Zur Unterstützung der net.pipe-Aktivierung muss die Standardwebsite zuerst an das net.pipe-Protokoll gebunden werden. Sie können hierzu das Tool "appcmd.exe" verwenden, das mit dem IIS 7.0-Verwaltungstoolset installiert wird. Führen Sie an einer Eingabeaufforderung auf höherer Ebene (Administrator) den folgenden Befehl aus.  
  
        ```  
        %windir%\system32\inetsrv\appcmd.exe set site "Default Web Site"   
        -+bindings.[protocol='net.pipe',bindingInformation='*']  
        ```  
  
        > [!NOTE]
        >  Dieser Befehl ist eine einzelne Textzeile.  
  
         Dieser Befehl fügt der Standardwebsite eine net.pipe-Sitebindung hinzu.  
  
    2.  Alle Anwendungen innerhalb einer Site nutzen zwar eine gemeinsame net.pipe-Bindung, aber jede Anwendung kann die net.pipe-Unterstützung unabhängig von den anderen Anwendungen aktivieren. Um net.pipe für die Anwendung /servicemodelsamples zu aktivieren, führen Sie den folgenden Befehl in einer Eingabeaufforderung mit erweiterten Berechtigungen (Administrator) aus.  
  
        ```  
        %windir%\system32\inetsrv\appcmd.exe set app "Default Web Site/servicemodelsamples" /enabledProtocols:http,net.pipe  
        ```  
  
        > [!NOTE]
        >  Dieser Befehl ist eine einzelne Textzeile.  
  
         Mit diesem Befehl wird die Anwendung "/servicemodelsamples" so konfiguriert, dass sowohl über http://localhost//servicemodelsamples als auch über net.tcp://localhost//servicemodelsamples darauf zugegriffen werden kann.  
  
4.  Um die C#- oder Visual Basic .NET-Edition der Projektmappe zu erstellen, befolgen Sie die unter [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md)aufgeführten Anweisungen.  
  
5.  Entfernen Sie die net.pipe-Sitebindung, die für dieses Beispiel hinzugefügt wurde.  
  
     Zur Vereinfachung sind die folgenden beiden Schritte in einer Batchdatei namens RemoveNetPipeSiteBinding.cmd implementiert, die sich im Beispielverzeichnis befindet:  
  
    1.  Entfernen Sie net.tcp aus der Liste der aktivierten Protokolle, indem Sie den folgenden Befehl an einer Eingabeaufforderung mit erweiterten Berechtigungen (Administrator) ausführen.  
  
        ```  
        %windir%\system32\inetsrv\appcmd.exe set app "Default Web Site/servicemodelsamples" /enabledProtocols:http  
        ```  
  
        > [!NOTE]
        >  Dieser Befehl muss als eine Textzeile eingegeben werden.  
  
    2.  Entfernen Sie die net.tcp-Sitebindung, indem Sie den folgenden Befehl an einer Eingabeaufforderung mit erweiterten Berechtigungen ausführen.  
  
        ```  
        %windir%\system32\inetsrv\appcmd.exe set site "Default Web Site" --bindings.[protocol='net.pipe',bindingInformation='*']  
        ```  
  
        > [!NOTE]
        >  Dieser Befehl muss als eine Textzeile eingegeben werden.  
  
## <a name="see-also"></a>Siehe auch  
 [AppFabric-Hosting und Persistenzbeispiele](http://go.microsoft.com/fwlink/?LinkId=193961)
