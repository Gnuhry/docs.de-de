---
title: 'Gewusst wie: Erstellen eines Anforderung-Antwort-Vertrags'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 801d90da-3d45-4284-9c9f-56c8aadb4060
caps.latest.revision: "19"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 79ef7b899adfb068a03e41cf0f3aa29f34f27b88
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="how-to-create-a-request-reply-contract"></a>Gewusst wie: Erstellen eines Anforderung-Antwort-Vertrags
Ein Anforderung-Antwort-Vertrag gibt eine Methode an, die eine Antwort zurückgibt. Die Antwort muss gesendet und unter den Bedingungen dieses Vertrags mit der Anforderung in Beziehung gesetzt werden. Selbst wenn die Methode keine Antwort (`void` in C# oder `Sub` in Visual Basic) zurückgibt, wird von der Infrastruktur eine leere Nachricht erstellt und gesendet, um dem Aufrufer mitzuteilen, dass die Methode einen Wert zurückgegeben hat. Verwenden Sie einen unidirektionalen Vertrag für die Operation, um das Senden einer leeren Mitteilung zu unterbinden.  
  
### <a name="to-create-a-request-reply-contract"></a>So erstellen Sie einen Anforderung-Antwort-Vertrag  
  
1.  Erstellen Sie in der Programmiersprache Ihrer Wahl eine Schnittstelle.  
  
2.  Fügen Sie das <xref:System.ServiceModel.ServiceContractAttribute>-Attribut der Schnittstelle hinzu.  
  
3.  Fügen Sie das <xref:System.ServiceModel.OperationContractAttribute>-Attribut jeder von Clients aufrufbaren Methode hinzu.  
  
4.  Dies ist optional. Legen Sie den Wert der <xref:System.ServiceModel.OperationContractAttribute.IsOneWay%2A>-Eigenschaft auf `true` fest, um das Senden einer leeren Mitteilung zu verhindern. Standardmäßig sind alle Operationen Anforderung-Antwort-Verträge.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird ein Vertrag für einen Rechnerdienst definiert, der die `Add`-Methode und die `Subtract`-Methode bereitstellt. Die `Multiply`-Methode ist nicht Teil des Vertrags, weil sie von der <xref:System.ServiceModel.OperationContractAttribute>-Klasse nicht gekennzeichnet wurde und somit nicht für Clients verfügbar ist.  
  
```
using System.ServiceModel;

[ServiceContract]
public interface ICalculator
{
    [OperationContract]
    // It would be equivalent to write explicitly:
    // [OperationContract(IsOneWay=false)]
    int Add(int a, int b);
    
    [OperationContract]
    int Subtract(int a, int b);
    
    int Multiply(int a, int b)
}
```
  
-   [!INCLUDE[crabout](../../../../includes/crabout-md.md)] zum Angeben von Vorgangsverträgen finden Sie in der Beschreibung der <xref:System.ServiceModel.OperationContractAttribute>-Klasse und der <xref:System.ServiceModel.OperationContractAttribute.IsOneWay%2A>-Eigenschaft.  
  
-   Durch Anwenden des <xref:System.ServiceModel.ServiceContractAttribute>-Attributs und des <xref:System.ServiceModel.OperationContractAttribute>-Attributs wird die automatische Generierung von Dienstvertragsdefinitionen in einem WSDL (Web Services Description Language)-Dokument ermöglicht, sobald der Dienst bereitgestellt wird. Das Dokument wird durch Anfügen von `?wsdl` an die HTTP-Basisadresse des Diensts heruntergeladen. Beispiel: `http://microsoft/CalculatorService?wsdl`  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.ServiceModel.OperationContractAttribute>  
 [Entwerfen von Dienstverträgen](../../../../docs/framework/wcf/designing-service-contracts.md)  
 [Vorgehensweise: Erstellen eines Duplexvertrags](../../../../docs/framework/wcf/feature-details/how-to-create-a-duplex-contract.md)
