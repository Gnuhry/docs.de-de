---
title: Steuern der Serialisierung und Deserialisierung mit SerializationBinder
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ba8dcecf-acc7-467c-939d-021bbac797d4
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 67afc6dbc069678c8fb692f70bc0e7a0a12b1076
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="controlling-serialization-and-deserialization-with-serializationbinder"></a>Steuern der Serialisierung und Deserialisierung mit SerializationBinder
Ein Formatierungsprogramm überträgt während der Serialisierung die Informationen, die zum Erstellen einer Instanz eines Objekts mit dem korrekten Typ und der korrekten Version erforderlich sind. Diese Informationen enthalten i. d. R. den vollständigen Typ- und Assemblynamen des Objekts. Standardmäßig verwendet die Deserialisierung diese Informationen zum Erstellen einer Instanz eines identischen Objekts. Einige Benutzer müssen ggf. steuern, welche Klasse serialisiert und deserialisiert werden soll. Der Grund dafür kann sein, dass die ursprüngliche Klasse auf dem Computer, der die Deserialisierung ausführt, nicht vorhanden ist, dass die ursprüngliche Klasse die Assembly gewechselt hat oder dass auf dem Server und Client eine andere Version der Klasse erforderlich ist. [!INCLUDE[crdefault](../../../../includes/crdefault-md.md)][Verwendung des Serialisierungsbinders](../../../../docs/framework/wcf/samples/usage-of-serialization-binder.md).  
  
> [!WARNING]
>  Die Funktion ist nur verfügbar, wenn Sie <xref:System.Runtime.Serialization.Formatters.Binary.BinaryFormatter> oder <xref:System.Runtime.Serialization.NetDataContractSerializer> verwenden.  
  
## <a name="using-serializationbinder"></a>Verwenden von SerializationBinder  
 <xref:System.Runtime.Serialization.SerializationBinder> ist eine abstrakte Klasse, mit der die tatsächlichen Typen gesteuert werden, die während der Serialisierung und Deserialisierung verwendet werden. Zum Steuern der Typen, die während der Serialisierung und Deserialisierung verwendet werden, leiten Sie eine Klasse von <xref:System.Runtime.Serialization.SerializationBinder> ab und überschreiben die Methoden <xref:System.Runtime.Serialization.SerializationBinder.BindToName(System.Type,System.String@,System.String@)> und <xref:System.Runtime.Serialization.SerializationBinder.BindToType(System.String,System.String)>. Die <xref:System.Runtime.Serialization.SerializationBinder.BindToName(System.Type,System.String@,System.String@)>-Methode verwendet einen <xref:System.Type> und gibt eine Assembly und einen Typnamen zurück. Die <xref:System.Runtime.Serialization.SerializationBinder.BindToType(System.String,System.String)>-Methode verwendet eine Assembly und einen Typnamen und gibt <xref:System.Type> zurück.  
  
## <a name="see-also"></a>Siehe auch  
 [Serialisierung und Deserialisierung](../../../../docs/framework/wcf/feature-details/serialization-and-deserialization.md)  
 [Verwendung des Serialisierungsbinders](../../../../docs/framework/wcf/samples/usage-of-serialization-binder.md)
