---
title: ICLRDomainManager-Schnittstelle
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRDomainManager
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRDomainManager
helpviewer_keywords: ICLRDomainManager interface [.NET Framework hosting]
ms.assetid: f08b2390-d872-4521-a815-e9c237c4c45d
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 75a7e93d26a5c77484d78ad4632bedf8def6a44b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="iclrdomainmanager-interface"></a>ICLRDomainManager-Schnittstelle
Ermöglicht es dem Host den Anwendungsdomänen-Manager an, der die Standardanwendungsdomäne initialisiert werden, sowie an Initialisierungseigenschaften verwendet werden.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[SetAppDomainManagerType-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrdomainmanager-setappdomainmanagertype-method.md)|Gibt den Typ abgeleitet wurde. die <xref:System.AppDomainManager?displayProperty=nameWithType> Klasse, der den Anwendungsdomänen-Manager, der verwendet wird, um die Standardanwendungsdomäne zu initialisieren.|  
|[SetPropertiesForDefaultAppDomain-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrdomainmanager-setpropertiesfordefaultappdomain-method.md)|Legt die Eigenschaften, die verwendet werden, um die Standardanwendungsdomäne zu initialisieren.|  
  
## <a name="remarks"></a>Hinweise  
 Um eine Instanz dieser Schnittstelle abzurufen, rufen die [ICLRControl:: GetCLRManager](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-getclrmanager-method.md) Methode mit dem Managertyp IID `IID_ICLRDomainManager`.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MetaHost.h  
  
 **Bibliothek:** als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [Hosten von Schnittstellen](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [Hosting](../../../../docs/framework/unmanaged-api/hosting/index.md)
