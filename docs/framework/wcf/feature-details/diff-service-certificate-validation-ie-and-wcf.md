---
title: "Unterschiede zwischen von Internet Explorer und WCF durchgeführter Dienstzertifikatsvalidierung"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- service certificate validation [WCF]
- certificates [WCF], service certificate validation
ms.assetid: 9dffcab2-70a9-40f0-99fd-d3a0b296028f
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: b74886f05ca6dc38c724e02cd091c6dd212c554f
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="differences-between-service-certificate-validation-done-by-internet-explorer-and-wcf"></a>Unterschiede zwischen von Internet Explorer und WCF durchgeführter Dienstzertifikatsvalidierung
Aufgrund der Unterschiede zwischen der von Internet Explorer und [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] durchgeführten Dienstzertifikatsvalidierung bei der Verwendung von HTTPS ist es möglich, dass Internet Explorer nicht auf die Hilfeseite oder die Web Services Description Language (WSDL) eines Diensts zugreifen kann, obwohl ein [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)]-Client erfolgreich Nachrichten an die Dienstendpunkte senden kann. Dies liegt daran, dass Internet Explorer überprüft, ob das Dienstzertifikat die `ServerAuthentication`-Objektbezeichner (OIDs) in den verbesserten Verwendungsflags aufweist, während [!INCLUDE[indigo2](../../../../includes/indigo2-md.md)] eine solche Einschränkung nicht erzwingt. Wenn Internet Explorer nicht auf die Diensthilfeseite oder die WSDL für den Dienst zugreifen kann, verwenden Sie die [ServiceModel Metadata Utility Tool (Svcutil.exe)](../../../../docs/framework/wcf/servicemodel-metadata-utility-tool-svcutil-exe.md) Zugriff auf die Dienstmetadaten.  
  
## <a name="see-also"></a>Siehe auch  
 [Unterschiede bei der Zertifikatsvalidierung zwischen HTTPS, SSL über TCP und SOAP-Sicherheit](../../../../docs/framework/wcf/feature-details/cert-val-diff-https-ssl-over-tcp-and-soap.md)  
 [Vorgehensweise: Abrufen von Metadaten und Implementieren eines kompatiblen Diensts](../../../../docs/framework/wcf/feature-details/how-to-retrieve-metadata-and-implement-a-compliant-service.md)
