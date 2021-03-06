---
title: IHostAssemblyManager::GetNonHostStoreAssemblies-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostAssemblyManager.GetNonHostStoreAssemblies
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostAssemblyManager::GetNonHostStoreAssemblies
helpviewer_keywords:
- IHostAssemblyManager::GetNonHostStoreAssemblies method [.NET Framework hosting]
- GetNonHostStoreAssemblies method [.NET Framework hosting]
ms.assetid: d2250b38-c76a-40ce-80c8-ba45149886e8
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 35e22e186b290cc4242275976f5109b73e2cf068
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="ihostassemblymanagergetnonhoststoreassemblies-method"></a>IHostAssemblyManager::GetNonHostStoreAssemblies-Methode
Ruft einen Schnittstellenzeiger auf eine [ICLRAssemblyReferenceList](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md) , die die Liste der Assemblys, die der Host erwartet, die common Language Runtime (CLR dass) geladen darstellt.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetNonHostStoreAssemblies (  
    [out] ICLRAssemblyReferenceList **ppReferenceList  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `ppReferenceList`  
 [out] Ein Zeiger auf die Adresse des ein `ICLRAssemblyReferenceList` , enthält eine Liste der Verweise auf Assemblys, die der Host die CLR geladen erwartet.  
  
## <a name="return-value"></a>Rückgabewert  
  
|HRESULT|Beschreibung|  
|-------------|-----------------|  
|S_OK|`GetNonHostStoreAssemblies`wurde erfolgreich zurückgegeben.|  
|HOST_E_CLRNOTAVAILABLE ZURÜCK|Die CLR wurde nicht in einen Prozess geladen, oder die CLR wird in einem Zustand, in dem er nicht verwalteten Code ausführen oder den Aufruf erfolgreich verarbeitet werden.|  
|HOST_E_TIMEOUT|Der Aufruf ist ein Timeout aufgetreten.|  
|HOST_E_NOT_OWNER|Der Aufrufer ist nicht Besitzer der Sperre.|  
|HOST_E_ABANDONED|Ein Ereignis wurde abgebrochen, während ein blockierten Thread oder eine Fiber darauf gewartet.|  
|E_FAIL|Ein Unbekannter Schwerwiegender Fehler aufgetreten ist. Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr verwendbar innerhalb des Prozesses. Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.|  
|E_OUTOFMEMORY|Es war nicht genügend Arbeitsspeicher verfügbar, um die Liste der Verweise für die angeforderte erstellen `ICLRAssemblyReferenceList`.|  
  
## <a name="remarks"></a>Hinweise  
 Die CLR löst Verweise mithilfe der folgenden Richtlinien:  
  
-   Er fragt zunächst die Liste der Assemblyverweise zurückgegebenes `GetNonHostStoreAssemblies`.  
  
-   Wenn die Assembly in der Liste angezeigt wird, wird die CLR auf die normalerweise gebunden.  
  
-   Wenn die Assembly nicht in der Liste angezeigt, und der Host eine Implementierung der stellt [IHostAssemblyStore](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md), die CLR ruft [IHostAssemblyStore:: ProvideAssembly](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-provideassembly-method.md) auf den Host ermöglichen die die Assembly zum Binden an.  
  
-   Andernfalls schlägt die CLR zum Binden an die Assembly ein.  
  
 Wenn bei der Host `ppReferenceList` Aufrufe um zu null, die erste CLR-Prüfpunkte im globalen Assemblycache `ProvideAssembly`, und klicken Sie dann die Anwendungsbasis, um einen Assemblyverweis aufzulösen Prüfpunkte.  
  
> [!NOTE]
>  Bei der Initialisierung die CLR ruft `GetNonHostStoreAssemblies` nur einmal. Die Methode wird nicht erneut aufgerufen.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MSCorEE.h  
  
 **Bibliothek:** als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [ICLRAssemblyReferenceList-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)  
 [IHostAssemblyManager-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihostassemblymanager-interface.md)  
 [IHostAssemblyStore-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/ihostassemblystore-interface.md)
