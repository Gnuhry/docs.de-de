---
title: COR_HEAPINFO-Struktur
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: COR_HEAPINFO
api_location: mscordbi.dll
api_type: COM
f1_keywords: COR_HEAPINFO
helpviewer_keywords: COR_HEAPINFO structure [.NET Framework debugging]
ms.assetid: bfb2cd39-3e0b-4d51-ba0c-f009755c1456
topic_type: apiref
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: e316b964e3e983f50b81228709623e162529b05c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="corheapinfo-structure"></a>COR_HEAPINFO-Struktur
Liefert allgemeine Informationen zum Garbage Collection-Heap, auch zu dessen Aufzählbarkeit.  
  
## <a name="syntax"></a>Syntax  
  
```  
typedef struct _COR_HEAPINFO {  
    BOOL areGCStructuresValid;   
    DWORD pointerSize;   
    DWORD numHeaps;  
    BOOL concurrent;   
    CorDebugGCType gcType;   
} COR_HEAPINFO;  
```  
  
## <a name="members"></a>Member  
  
|Member|Beschreibung|  
|------------|-----------------|  
|`areGCStructuresValid`|`true`Wenn die Garbage Collection-Strukturen gültig sind und der Heap aufgelistet werden kann; andernfalls `false`.|  
|`pointerSize`|Die Größe in Bytes von Zeigern auf der Zielarchitektur.|  
|`numHeaps`|Die Anzahl der logischen Garbagecollection heaps im Prozess.|  
|`concurrent`|`TRUE`Wenn die gleichzeitige Garbagecollection (im Hintergrund) aktiviert ist; andernfalls `FALSE`.|  
|`gcType`|Ein Mitglied der [CorDebugGCType](../../../../docs/framework/unmanaged-api/debugging/cordebuggctype-enumeration.md) -Enumeration, der angibt, ob die Garbage Collection auf einer Arbeitsstation oder einem Server ausgeführt wird.|  
  
## <a name="remarks"></a>Hinweise  
 Eine Instanz von der `COR_HEAPINFO` Struktur wird zurückgegeben, indem die [icordebugprocess5:: Getgcheapinformation](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getgcheapinformation-method.md) Methode.  
  
 Sie müssen immer überprüfen Sie vor dem Auflisten von Objekten auf dem Garbage Collection-Heap aus, die `areGCStructuresValid` Feld, um sicherzustellen, dass der Heap in einen enumerable-Zustand ist. Weitere Informationen finden Sie unter der [icordebugprocess5:: Getgcheapinformation](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess5-getgcheapinformation-method.md) Methode.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [Debuggen von Strukturen](../../../../docs/framework/unmanaged-api/debugging/debugging-structures.md)  
 [Debuggen](../../../../docs/framework/unmanaged-api/debugging/index.md)
