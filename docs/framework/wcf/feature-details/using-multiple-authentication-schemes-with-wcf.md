---
title: Verwenden von mehreren Authentifizierungsschemen mit WCF
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: f32a56a0-e2b2-46bf-a302-29e1275917f9
caps.latest.revision: "4"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: cf74b38c15cf8dc68218c39246c8999c4ec44493
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="using-multiple-authentication-schemes-with-wcf"></a>Verwenden von mehreren Authentifizierungsschemen mit WCF
Mit WCF können Sie nun mehrere Authentifizierungsschemas für einen einzelnen Endpunkt angeben. Darüber hinaus können webgehostete Dienste ihre Authentifizierungseinstellungen direkt von IIS erben. Selbst gehostete Dienste können angeben, welche Authentifizierungsschemas verwendet werden können. Weitere Informationen zum Einrichten der Authentifizierungseinstellungen in IIS finden Sie unter [IIS-Authentifizierung](http://go.microsoft.com/fwlink/?LinkId=232458)  
  
## <a name="iis-hosted-services"></a>IIS-gehostete Dienste  
 Legen Sie für IIS-gehostete Dienste die Authentifizierungsschemas fest, die Sie in IIS verwenden möchten. Geben Sie dann in der Datei "Web.config" des Diensts, in der Bindungskonfiguration ClientCredential-Typ als "InheritedFromHost" wie im folgenden XML-Ausschnitt gezeigt:  
  
```xml  
<bindings>  
      <basicHttpBinding>  
        <binding name="secureBinding">  
          <security mode="Transport">  
            <transport clientCredentialType="InheritedFromHost" />  
          </security>  
        </binding>  
      </basicHttpBinding>  
    </bindings>  
```  
  
 Sie können angeben, dass nur eine Teilmenge der Authentifizierungsschemas mit Ihrem Dienst mithilfe von "serviceauthenticationbehavior" verwendet werden soll oder die \<ServiceAuthenticationManager >-Element. Beim Konfigurieren im Code verwenden Sie ServiceAuthenticationBehavior wie im folgenden Codeausschnitt dargestellt.  
  
```csharp  
// ...  
ServiceAuthenticationBehavior sab = null;  
sab = serviceHost.Description.Behaviors.Find<ServiceAuthenticationBehavior>();  
  
if (sab == null)  
{  
    sab = new ServiceAuthenticationBehavior();  
    sab.AuthenticationSchemes = AuthenticationSchemes.Basic | AuthenticationSchemes.Negotiate | AuthenticationSchemes.Digest;  
    serviceHost.Description.Behaviors.Add(sab);  
}  
else  
{  
     sab.AuthenticationSchemes = AuthenticationSchemes.Basic | AuthenticationSchemes.Negotiate | AuthenticationSchemes.Digest;  
}  
// ...  
```  
  
 Wenn Sie dies in einer Konfigurationsdatei konfigurieren, verwenden die \<ServiceAuthenticationManager >-Element wie im folgenden XML-Ausschnitt gezeigt.  
  
```xml  
<behaviors>  
      <serviceBehaviors>  
        <behavior name="limitedAuthBehavior">  
          <serviceAuthenticationManager authenticationSchemes="Negotiate, Digest, Basic"/>  
          <!-- ... -->  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
```  
  
 Dadurch wird sichergestellt, dass nur eine Teilmenge der hier aufgeführten Authentifizierungsschemas für den Dienstendpunkt infrage kommt, je nachdem, was in IIS ausgewählt wurde. Dies bedeutet, dass ein Entwickler z. B. die Standardauthentifizierung aus der Liste ausschließen kann, indem er sie in der serviceAuthenticationManager-Liste auslässt. Sie wird auch nicht auf den Dienstendpunkt angewendet, wenn sie in IIS aktiviert ist.  
  
## <a name="self-hosted-services"></a>Selbst gehostete Dienste  
 Selbst gehostete Dienste werden geringfügig anders konfiguriert, da keine Einstellungen von IIS geerbt werden können. Hier verwenden Sie die \<ServiceAuthenticationManager >-Element oder "serviceauthenticationbehavior", um die Authentifizierungseinstellungen anzugeben, die vererbt werden. Der Code sieht folgendermaßen aus:  
  
```csharp  
// ...  
ServiceAuthenticationBehavior sab = null;  
sab = serviceHost.Description.Behaviors.Find<ServiceAuthenticationBehavior>();  
  
if (sab == null)  
{  
    sab = new ServiceAuthenticationBehavior();  
    sab.AuthenticationSchemes = AuthenticationSchemes.Basic | AuthenticationSchemes.Negotiate | AuthenticationSchemes.Digest;  
    serviceHost.Description.Behaviors.Add(sab);  
}  
else  
{  
     sab.AuthenticationSchemes = AuthenticationSchemes.Basic | AuthenticationSchemes.Negotiate | AuthenticationSchemes.Digest;  
}  
// ...  
```  
  
 In der config-Datei sieht das wie folgt aus:  
  
```xml  
<behaviors>  
      <serviceBehaviors>  
        <behavior name="limitedAuthBehavior">  
          <serviceAuthenticationManager authenticationSchemes="Negotiate, Digest, Basic"/>  
          <!-- ... -->  
        </behavior>  
      </serviceBehaviors>  
    </behaviors>  
```  
  
 Außerdem können Sie InheritFromHost in den Bindungseinstellungen angeben, wie im folgenden XML-Ausschnitt gezeigt.  
  
```xml  
<bindings>  
      <basicHttpBinding>  
        <binding name="secureBinding">  
          <security mode="Transport">  
            <transport clientCredentialType="InheritedFromHost" />  
          </security>  
        </binding>  
      </basicHttpBinding>  
    </bindings>  
```  
  
 Alternativ können Sie die Authentifizierungsschemas in einer benutzerdefinierten Bindung angeben, indem Sie die Authentifizierungsschemas für das HTTP-Transportbindungselement festlegen, wie im folgenden Konfigurationsausschnitt dargestellt.  
  
```xml  
<binding name="multipleBinding">  
      <textMessageEncoding/>  
      <httpTransport authenticationScheme="Negotiate, Ntlm, Digest, Basic" />  
    </binding>  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Bindungen und Sicherheit](../../../../docs/framework/wcf/feature-details/bindings-and-security.md)  
 [Endpunkte: Adressen, Bindungen und Verträge](../../../../docs/framework/wcf/feature-details/endpoints-addresses-bindings-and-contracts.md)  
 [Konfigurieren der vom System bereitgestellte Bindungen](../../../../docs/framework/wcf/feature-details/configuring-system-provided-bindings.md)  
 [Sicherheitsfunktionen mit benutzerdefinierten Bindungen](../../../../docs/framework/wcf/feature-details/security-capabilities-with-custom-bindings.md)  
 [Bindungen](../../../../docs/framework/wcf/feature-details/bindings.md)  
 [Bindungen](../../../../docs/framework/wcf/feature-details/bindings.md)  
 [Benutzerdefinierte Bindungen](../../../../docs/framework/wcf/extending/custom-bindings.md)
