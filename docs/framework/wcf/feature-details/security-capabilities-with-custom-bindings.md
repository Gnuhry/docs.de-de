---
title: Sicherheitsfunktionen mit benutzerdefinierten Bindungen
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a2425679-484a-4e6c-9c98-7da7304f1516
caps.latest.revision: "11"
author: BrucePerlerMS
ms.author: bruceper
manager: mbaldwin
ms.openlocfilehash: 9d252dca363c952dde44b499363e285d4bb7eb82
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="security-capabilities-with-custom-bindings"></a>Sicherheitsfunktionen mit benutzerdefinierten Bindungen
Sie können die meisten der allgemeinen Sicherheitsaufgaben mithilfe einer vom System bereitgestellten Bindung ausführen. Wenn Sie die Sicherheit jedoch detaillierter steuern müssen, können Sie mit <xref:System.ServiceModel.Channels.SecurityBindingElement> eine benutzerdefinierte Bindung erstellen, wie in diesen Themen erläutert. [!INCLUDE[crabout](../../../../includes/crabout-md.md)]Benutzerdefinierte Bindungen finden Sie unter [benutzerdefinierte Bindungen](../../../../docs/framework/wcf/extending/custom-bindings.md).  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [SecurityBindingElement-Authentifizierungsmodi](../../../../docs/framework/wcf/feature-details/securitybindingelement-authentication-modes.md)  
 Beschreibt die Authentifizierungsmodi, die mit einer benutzerdefinierten Bindung möglich sind.  
  
 [Vorgehensweise: Erstellen einer benutzerdefinierten Bindung mit dem SecurityBindingElement](../../../../docs/framework/wcf/feature-details/how-to-create-a-custom-binding-using-the-securitybindingelement.md)  
 Beschreibt die grundlegenden Schritte zum Erstellen einer benutzerdefinierten Bindung mit einem Sicherheitselement.  
  
 [Vorgehensweise: Erstellen eines SecurityBindingElement für einen angegebenen Authentifizierungsmodus](../../../../docs/framework/wcf/feature-details/how-to-create-a-securitybindingelement-for-a-specified-authentication-mode.md)  
 Beschreibt das Erstellen eines Sicherheitselements für einen angegebenen Authentifizierungsmodus.  
  
 [Vorgehensweise: Deaktivieren sicherer Sitzungen auf einer WSFederationHttpBinding](../../../../docs/framework/wcf/feature-details/how-to-disable-secure-sessions-on-a-wsfederationhttpbinding.md)  
 Beschreibt das Deaktivieren von Sicherheitssitzungen beim Erstellen eines Verbunddienstes.  
  
 [Vorgehensweise: Aktivieren der Nachrichtenreplay-Erkennung](../../../../docs/framework/wcf/feature-details/how-to-enable-message-replay-detection.md)  
 Beschreibt, wie ein Replay-Angriff entdeckt werden kann.  
  
 [Vorgehensweise: Erstellen unterstützender Anmeldeinformationen](../../../../docs/framework/wcf/feature-details/how-to-create-a-supporting-credential.md)  
 Beschreibt das Bereitstellen unterstützender Anmeldeinformationen für einen Dienst, wenn sie vom Dienst benötigt werden.  
  
 [Vorgehensweise: Einrichten einer Signaturbestätigung](../../../../docs/framework/wcf/feature-details/how-to-set-up-a-signature-confirmation.md)  
 Beschreibt die Schritte zum Bestätigen von Signaturen beim digitalen Signieren von Nachrichten.  
  
 [Vorgehensweise: Festlegen einer Max Taktverschiebung](../../../../docs/framework/wcf/feature-details/how-to-set-a-max-clock-skew.md)  
 Beschreibt das Festlegen des maximal zulässigen Zeitunterschieds zwischen einem Dienst und einem Client.  
  
 [Vorgehensweise: Deaktivieren der Verschlüsselung von digitalen Signaturen](../../../../docs/framework/wcf/feature-details/how-to-disable-encryption-of-digital-signatures.md)  
 Beschreibt, inwiefern das Deaktivieren der Verschlüsselung von digitalen Signaturen die Leistung verbessern kann.  
  
## <a name="reference"></a>Verweis  
 <xref:System.ServiceModel.Channels.SecurityBindingElement>  
  
 [\<Sicherheit >](../../../../docs/framework/configure-apps/file-schema/wcf/security-of-custombinding.md)  
  
## <a name="related-sections"></a>Verwandte Abschnitte  
 [Grundlagen der Schutzebene](../../../../docs/framework/wcf/understanding-protection-level.md)  
  
 [Sichern von Diensten und Clients](../../../../docs/framework/wcf/feature-details/securing-services-and-clients.md)  
  
## <a name="see-also"></a>Siehe auch  
 [Bindungen und Sicherheit](../../../../docs/framework/wcf/feature-details/bindings-and-security.md)  
 [Sicherheit (Übersicht)](../../../../docs/framework/wcf/feature-details/security-overview.md)  
 [Vom System bereitgestellte Bindungen](../../../../docs/framework/wcf/system-provided-bindings.md)
