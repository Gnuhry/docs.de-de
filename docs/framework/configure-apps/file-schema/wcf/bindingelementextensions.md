---
title: '&lt;bindingElementExtensions&gt;'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: bb597fc0-c947-451c-afda-bf23d42f4f4d
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 71fdc7c68ff7e672a5adf044bbe0200563772a58
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="ltbindingelementextensionsgt"></a>&lt;bindingElementExtensions&gt;
Dieser Abschnitt aktiviert die Verwendung eines benutzerdefinierten Elements für einen Computer oder eine Anwendungskonfigurationsdatei. Sie können ein benutzerdefiniertes Bindungselement zur Auflistung hinzufügen, indem Sie das `add`-Schlüsselwort verwenden und das `type`-Attribut des Elements auf eine Bindungselementerweiterung sowie das `name`-Attribut auf das benutzerdefinierte Bindungselement festlegen.  
  
 Bindungserweiterungen ermöglichen es dem Benutzer, eigene Bindungselemente als Teil von benutzerdefinierten Bindungen zu erstellen. Eine Bindungserweiterung ist ein Typ, der die abstrakte Klasse <xref:System.ServiceModel.Channels.BindingElement> implementiert. In der Konfigurationsdatei wird der `bindingElementExtensions`-Abschnitt zum Definieren eines Erweiterungselements verwendet.  
  
 Im folgenden Beispiel werden das `add`-Element sowie das `name`-Attribut zum Hinzufügen einer Bindungserweiterung zum `bindingElementExtensions`-Abschnitt der Konfigurationsdatei verwendet.  
  
```xml  
<system.serviceModel>  
    <extensions>  
        <bindingElementExtensions>  
           <add name="udpTransport" type="Microsoft.ServiceModel.Samples.UdpTransportSection, UdpTransport,  
                Version=1.0.0.0, Culture=neutral, PublicKeyToken=null" />  
        </bindingElementExtensions>  
    </extensions>  
</system.serviceModel>  
```  
  
 Zum Hinzufügen von Konfigurationsmöglichkeiten zum Element, muss der Benutzer ein `bindingElementExtensionSection`-Element schreiben und registrieren. Weitere Informationen dazu finden Sie in der <xref:System.Configuration>-Dokumentation.  
  
 Nachdem das Element und sein Konfigurationstyp definiert wurden, kann die Erweiterung wie im folgenden Beispiel dargestellt als Teil einer benutzerdefinierten Bindung verwendet werden.  
  
```xml  
<customBinding>  
     <binding name="test2">  
         <udpTransport />  
         <binaryMessageEncoding maxReadPoolSize="211" maxWritePoolSize="2132"  
             maxSessionSize="3141" />  
         </binding>  
</customBinding>  
```  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.ServiceModel.Configuration.BindingElementExtensionElement>  
 [Erweitern von Bindungen](../../../../../docs/framework/wcf/extending/extending-bindings.md)
