---
title: ICorProfilerCallback::RuntimeSuspendStarted-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.RuntimeSuspendStarted
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::RuntimeSuspendStarted
helpviewer_keywords:
- ICorProfilerCallback::RuntimeSuspendStarted method [.NET Framework profiling]
- RuntimeSuspendStarted method [.NET Framework profiling]
ms.assetid: c8461cac-e31b-4efa-ad2c-26598173eb96
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 358536aa51dfef2d079813b34eddbd1b01294bcc
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilercallbackruntimesuspendstarted-method"></a>ICorProfilerCallback::RuntimeSuspendStarted-Methode
Benachrichtigt den Profiler, dass die Laufzeit alle Runtime Threads anhalten.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT RuntimeSuspendStarted(  
    [in] COR_PRF_SUSPEND_REASON suspendReason);  
```  
  
#### <a name="parameters"></a>Parameter  
 `suspendReason`  
 [in] Der Wert der [COR_PRF_SUSPEND_REASON](../../../../docs/framework/unmanaged-api/profiling/cor-prf-suspend-reason-enumeration.md) -Enumeration, der den Grund für die Unterbrechung angibt.  
  
## <a name="remarks"></a>Hinweise  
 Alle Common Language Runtime-Threads, die in nicht verwaltetem Code sind dürfen weiter ausgeführt wird, bis sie versuchen, auf die Common Language Runtime erneut eingeben. An diesem Punkt werden sie auch angehalten, bis die Laufzeit fortgesetzt wird. Dies gilt auch für neue Threads, die die Common Language Runtime eingeben. Alle Threads in der Laufzeit sind entweder sofort angehalten, wenn sie bereits im Code parallelisiert sind oder sie aufgefordert werden, angehalten, wenn sie unterbrechbaren Code erreichen.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [ICorProfilerCallback-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [RuntimeSuspendAborted-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendaborted-method.md)  
 [RuntimeSuspendFinished-Methode](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-runtimesuspendfinished-method.md)
