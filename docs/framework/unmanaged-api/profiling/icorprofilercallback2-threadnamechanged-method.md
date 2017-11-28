---
title: ICorProfilerCallback2::ThreadNameChanged-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback2.ThreadNameChanged
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback2::ThreadNameChanged
helpviewer_keywords:
- ThreadNameChanged method [.NET Framework profiling]
- ICorProfilerCallback2::ThreadNameChanged method [.NET Framework profiling]
ms.assetid: c8bbd76d-a9ff-44f2-87a6-be052819da36
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: b64191bea9abf336b04124adc2de3e713e87d55d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilercallback2threadnamechanged-method"></a><span data-ttu-id="aa400-102">ICorProfilerCallback2::ThreadNameChanged-Methode</span><span class="sxs-lookup"><span data-stu-id="aa400-102">ICorProfilerCallback2::ThreadNameChanged Method</span></span>
<span data-ttu-id="aa400-103">Benachrichtigt den Profiler, dass der Name eines Threads geändert wurde.</span><span class="sxs-lookup"><span data-stu-id="aa400-103">Notifies the code profiler that the name of a thread has changed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aa400-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="aa400-104">Syntax</span></span>  
  
```  
HRESULT ThreadNameChanged(  
    [in] ThreadID threadId,  
    [in] ULONG cchName,  
    [in] WCHAR name[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="aa400-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="aa400-105">Parameters</span></span>  
 `threadId`  
 <span data-ttu-id="aa400-106">[in] Die ID des Threads.</span><span class="sxs-lookup"><span data-stu-id="aa400-106">[in] The ID of the thread.</span></span>  
  
 `cchName`  
 <span data-ttu-id="aa400-107">[in] Die Länge des neuen Namens des Threads.</span><span class="sxs-lookup"><span data-stu-id="aa400-107">[in] The length of the new name of the thread.</span></span>  
  
 `name`  
 <span data-ttu-id="aa400-108">[in] Der neue Name des Threads.</span><span class="sxs-lookup"><span data-stu-id="aa400-108">[in] The new name of the thread.</span></span> <span data-ttu-id="aa400-109">Der Name ist nicht mit Null beendet.</span><span class="sxs-lookup"><span data-stu-id="aa400-109">The name is not null-terminated.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="aa400-110">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="aa400-110">Requirements</span></span>  
 <span data-ttu-id="aa400-111">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="aa400-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="aa400-112">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="aa400-112">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="aa400-113">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="aa400-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="aa400-114">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="aa400-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aa400-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="aa400-115">See Also</span></span>  
 [<span data-ttu-id="aa400-116">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="aa400-116">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="aa400-117">ICorProfilerCallback2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="aa400-117">ICorProfilerCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)