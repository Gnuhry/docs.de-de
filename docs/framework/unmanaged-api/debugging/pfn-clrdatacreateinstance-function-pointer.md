---
title: PFN_CLRDataCreateInstance-Funktionszeiger
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: PFN_CLRDataCreateInstance
api_location: mscordbi.dll
api_type: COM
f1_keywords: PFN_CLRDataCreateInstance
helpviewer_keywords: PFN_CLRDataCreateInstance function pointer [.NET Framework debugging]
ms.assetid: 5c66ac57-d751-4de5-af9f-26ceb949af8b
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 7ec5783381c667d666c447b6d9861d9baaad3907
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="pfnclrdatacreateinstance-function-pointer"></a>PFN_CLRDataCreateInstance-Funktionszeiger
Zeigt auf eine Funktion, die ein Schnittstellenobjekt für das angegebene Ziel-Element erstellt.  
  
## <a name="syntax"></a>Syntax  
  
```  
typedef HRESULT (STDAPICALLTYPE* PFN_CLRDataCreateInstance) (  
    [in]  REFIID           iid,  
    [in]  ICLRDataTarget  *target,  
    [out] void           **iface  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `iid`  
 [in] Der Bezeichner der Schnittstelle instanziiert werden.  
  
 `target`  
 [in] Ein Zeiger auf eine vom Benutzer implementierte [ICLRDataTarget](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget-interface.md) Objekt, das des Zielelements für die zum Erstellen des Schnittstellenobjekts darstellt.  
  
 `iface`  
 [out] Ein Zeiger auf die Adresse des Objekts zurückgegebene Schnittstelle.  
  
## <a name="remarks"></a>Hinweise  
 Die `ICLRDataTarget` Objekt wird vom Writer der Debuganwendung implementiert. Die Implementierung hängt vom Typ des Zielelements dargestellt wird. Das Zielelement ist möglicherweise ein Prozess, Speicherabbild Remotecomputer und So weiter.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** ClrData.idl  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [Debuggen von globalen statischen Funktionen](../../../../docs/framework/unmanaged-api/debugging/debugging-global-static-functions.md)
