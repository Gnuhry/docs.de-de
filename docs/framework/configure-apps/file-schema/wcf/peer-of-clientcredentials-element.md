---
title: '&lt;peer&gt; des &lt;clientCredentials&gt;-Elements'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 505bd987-0042-4622-b68e-94f439729d53
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 4f2fa776711223ace6a4cebce7783b1fa0c148a4
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="ltpeergt-of-ltclientcredentialsgt-element"></a>&lt;peer&gt; des &lt;clientCredentials&gt;-Elements
Gibt Anmeldeinformationen an, die bei der Authentifizierung von Peer-to-Peer-Clients verwendet werden.  
  
 \<System. ServiceModel >  
\<Verhalten >  
\<EndpointBehaviors >  
\<Verhalten >  
\<ClientCredentials >  
\<Peer >  
  
## <a name="syntax"></a>Syntax  
  
```xml  
<peer>  
  <certificate/>  
  <peerAuthentication/>  
  <messageSenderAuthentication/>  
</peer>  
```  
  
## <a name="attributes-and-elements"></a>Attribute und Elemente  
 In den folgenden Abschnitten werden Attribute sowie untergeordnete und übergeordnete Elemente beschrieben.  
  
### <a name="attributes"></a>Attribute  
 Keine.  
  
### <a name="child-elements"></a>Untergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<Zertifikat >](../../../../../docs/framework/configure-apps/file-schema/wcf/certificate-element.md)|Gibt ein X.509-Zertifikat an, das zum Signieren und Verschlüsseln von Nachrichten für Peer-to-Peer-Clients verwendet wird. .|  
|[\<PeerAuthentication >](../../../../../docs/framework/configure-apps/file-schema/wcf/peerauthentication-element.md)|Gibt die Authentifizierungsoptionen für Peer-Clients an.|  
|[\<MessageSenderAuthentication >](../../../../../docs/framework/configure-apps/file-schema/wcf/messagesenderauthentication-element.md)|Gibt die Authentifizierungsoptionen für Nachrichtenabsender an.|  
  
### <a name="parent-elements"></a>Übergeordnete Elemente  
  
|Element|Beschreibung|  
|-------------|-----------------|  
|[\<ClientCredentials >](../../../../../docs/framework/configure-apps/file-schema/wcf/clientcredentials.md)|Gibt die zum Authentifizieren des Clients beim Dienst verwendeten Anmeldeinformationen an.|  
  
## <a name="remarks"></a>Hinweise  
 Dieses Konfigurationselement gibt die Anmeldeinformationen an, mit denen sich ein Peerknoten gegenüber anderen Knoten im Netz authentifiziert, sowie die Authentifizierungseinstellungen, mit denen ein Peerknoten andere Peerknoten authentifiziert. Weitere Informationen finden Sie unter [Peer Kanal Nachrichtenauthentifizierung](http://msdn.microsoft.com/en-us/80e73386-514e-4c30-9e4a-b9ca8c173a95) und [Sichern von Peer-Kanal Anwendungen](../../../../../docs/framework/wcf/feature-details/securing-peer-channel-applications.md).  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.ServiceModel.Configuration.ClientCredentialsElement>  
 <xref:System.ServiceModel.Description.ClientCredentials>  
 <xref:System.ServiceModel.Configuration.PeerCredentialElement>  
 <xref:System.ServiceModel.Configuration.ClientCredentialsElement.Peer%2A>  
 <xref:System.ServiceModel.Description.ClientCredentials>  
 <xref:System.ServiceModel.Description.ClientCredentials.Peer%2A>  
 <xref:System.ServiceModel.Security.PeerCredential>  
 [Peer-zu-Peer-Netzwerken](../../../../../docs/framework/wcf/feature-details/peer-to-peer-networking.md)  
 [Sichern von Clients](../../../../../docs/framework/wcf/securing-clients.md)  
 [Peerkanal Nachrichtenauthentifizierung](http://msdn.microsoft.com/en-us/80e73386-514e-4c30-9e4a-b9ca8c173a95)  
 [Benutzerdefinierter Peerkanal-Authentifizierung](http://msdn.microsoft.com/en-us/4aa8a82e-41a8-48e2-8621-7e1cbabdca7c)  
 [Sichern von Peerkanalanwendungen](../../../../../docs/framework/wcf/feature-details/securing-peer-channel-applications.md)  
 [Sichern von Diensten und Clients](../../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)
