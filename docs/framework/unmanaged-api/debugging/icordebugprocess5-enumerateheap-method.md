---
title: ICorDebugProcess5::EnumerateHeap-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugProcess5.EnumerateHeap
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugProcess5::EnumerateHeap
helpviewer_keywords:
- EnumerateHeap method, ICorDebugProcess5 interface [.NET Framework debugging]
- ICorDebugProcess5::EnumerateHeap method [.NET Framework debugging]
ms.assetid: b0192104-6073-4089-a4df-dc29ee033074
topic_type: apiref
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 41cd7d47650cdfe6a3598ba126be489107181a44
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="icordebugprocess5enumerateheap-method"></a>ICorDebugProcess5::EnumerateHeap-Methode
Ruft einen Enumerator für die Objekte im verwalteten Heap.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT EnumerateHeap(  
    [out] ICorDebugHeapEnum **ppObjects  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `ppObject`  
 [out] Ein Zeiger auf die Adresse des ein [ICorDebugHeapEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md) Schnittstellenobjekt, das einen Enumerator für die Objekte, die auf dem verwalteten Heap gespeichert sind.  
  
## <a name="remarks"></a>Hinweise  
 Vor dem Aufruf der `ICorDebugProcess5::EnumerateHeap` -Methode, die Sie aufrufen sollte die [icordebugprocess5:: Getgcheapinformation](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getgcheapinformation-method.md) Methode und überprüfen Sie den Wert von der `areGCStructuresValid` Feld des zurückgegebenen [COR_HEAPINFO](../../../../docs/framework/unmanaged-api/debugging/cor-heapinfo-structure.md) Objekt, um sicherzustellen, dass die Garbage Collection-Heap in seinem aktuellen Status aufzählbar ist. Darüber hinaus die `ICorDebugProcess5::EnumerateHeap` gibt `E_FAIL` , wenn Sie zu früh in der Lebensdauer des Prozesses, bevor Speicher anfügen, für der verwaltete Heap zugeordnet ist.  
  
 Die [ICorDebugHeapEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md) -Schnittstellenobjekt ist eine standard-Enumerator ICorDebugEnum-Schnittstelle, die Ihnen ermöglicht, Auflisten von abgeleitet [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) Objekte. Diese Methode füllt die [ICorDebugHeapEnum](../../../../docs/framework/unmanaged-api/debugging/icordebugheapenum-interface.md) -Auflistungsobjekts mit [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) Instanzen, die Informationen zu allen Objekten bereitstellen. Die Auflistung kann außerdem enthalten [COR_HEAPOBJECT](../../../../docs/framework/unmanaged-api/debugging/cor-heapobject-structure.md) Instanzen, die Informationen über Objekte bereitzustellen, die von einer nicht als Stammelement werden-Objekt jedoch noch nicht vom Garbage Collector erfasst wurden.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [ICorDebugProcess5-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-interface.md)  
 [Debugschnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
