---
title: 222 - OperationFailed
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 6b530ded-8f20-4d78-8bfe-1875276df6ba
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 5d56766dd32acf1ef71f7c06a5c3c94cc7510070
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="222---operationfailed"></a>222 - OperationFailed
## <a name="properties"></a>Eigenschaften  
  
|||  
|-|-|  
|ID|222|  
|Stichwörter|EndToEndMonitoring, HealthMonitoring, Troubleshooting, ServiceModel|  
|Ebene|Warnung|  
|Kanal|Microsoft-Windows-Application Server-Applications/Analytic|  
  
## <a name="description"></a>Beschreibung  
 Dieses Ereignis wird ausgegeben, wenn der standardmäßige `OperationInvoker` des Dienstmodells beim Aufrufen der Methode auf eine Ausnahme gestoßen ist. Beachten Sie, dass von `FaultException` abgeleitete Ausnahmen bewirken, dass dieses Ereignis nicht ausgegeben wird.  
  
## <a name="message"></a>Meldung  
 Die '%1'-Methode hat beim Aufrufen durch den OperationInvoker eine nicht behandelte Ausnahme ausgelöst. Die Methodenaufrufdauer betrug '%2' ms.  
  
## <a name="details"></a>Details  
  
|Datenelementname|Datenelementtyp|Beschreibung|  
|--------------------|--------------------|-----------------|  
|Methodenname|`xs:string`|Der CLR-Name der Methode, die vom `OperationInvoker` aufgerufen wurde.|  
|Dauer|`xs:long`|Die Zeit, in Millisekunden, die der `OperationInvoker` zum Aufrufen der Methode benötigt hat.|  
|HostReference|`xs:string`|Für im Internet gehostete Dienste identifiziert dieses Feld den Dienst in der Webhierarchie eindeutig. Das Format ist definiert als "Website Namen virtueller Anwendungspfad &#124; Virtueller Dienstpfad &#124; ServiceName ". Beispiel: "Default Web Site/CalculatorApplication &#124;/CalculatorService.svc &#124; CalculatorService'.|  
|AppDomain|`xs:string`|Die von AppDomain.CurrentDomain.FriendlyName zurückgegebene Zeichenfolge.|
