---
title: ICorProfilerCallback2::GarbageCollectionStarted-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback2.GarbageCollectionStarted
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback2::GarbageCollectionStarted
helpviewer_keywords:
- GarbageCollectionStarted method [.NET Framework profiling]
- ICorProfilerCallback2::GarbageCollectionStarted method [.NET Framework profiling]
ms.assetid: 44eef087-f21f-4fe2-b481-f8a0ee022e7d
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 1e79eea059fab4810ece12dbc264f3d3b08b7ff4
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilercallback2garbagecollectionstarted-method"></a><span data-ttu-id="b8ab3-102">ICorProfilerCallback2::GarbageCollectionStarted-Methode</span><span class="sxs-lookup"><span data-stu-id="b8ab3-102">ICorProfilerCallback2::GarbageCollectionStarted Method</span></span>
<span data-ttu-id="b8ab3-103">Benachrichtigt den Profiler, dass die Garbagecollection gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="b8ab3-103">Notifies the code profiler that garbage collection has started.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b8ab3-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b8ab3-104">Syntax</span></span>  
  
```  
HRESULT GarbageCollectionStarted(  
    [in] int cGenerations,  
    [in, size_is(cGenerations), length_is(cGenerations)] BOOL generationCollected[],  
    [in] COR_PRF_GC_REASON reason);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b8ab3-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="b8ab3-105">Parameters</span></span>  
 `cGenerations`  
 <span data-ttu-id="b8ab3-106">[in] Die Gesamtanzahl der Einträge in der `generationCollected` Array.</span><span class="sxs-lookup"><span data-stu-id="b8ab3-106">[in] The total number of entries in the `generationCollected` array.</span></span>  
  
 `generationCollected`  
 <span data-ttu-id="b8ab3-107">[in] Ein Array von booleschen Werten `true` Wenn die Generierung, der Index des Arrays entspricht von der diese Garbagecollection gesammelt wurden, andernfalls wird `false`.</span><span class="sxs-lookup"><span data-stu-id="b8ab3-107">[in] An array of Boolean values, which are `true` if the generation that corresponds to the array index is being collected by this garbage collection; otherwise, `false`.</span></span>  
  
 <span data-ttu-id="b8ab3-108">Das Array wird durch den Wert indiziert die [COR_PRF_GC_GENERATION](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-generation-enumeration.md) -Enumeration, die die Generierung angibt.</span><span class="sxs-lookup"><span data-stu-id="b8ab3-108">The array is indexed by a value of the [COR_PRF_GC_GENERATION](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-generation-enumeration.md) enumeration, which indicates the generation.</span></span>  
  
 `reason`  
 <span data-ttu-id="b8ab3-109">[in] Der Wert der [COR_PRF_GC_REASON](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-reason-enumeration.md) -Enumeration, die die Ursache der Garbagecollection ausgelöst wurde.</span><span class="sxs-lookup"><span data-stu-id="b8ab3-109">[in] A value of the [COR_PRF_GC_REASON](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-reason-enumeration.md) enumeration that indicates the reason the garbage collection was induced.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b8ab3-110">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b8ab3-110">Remarks</span></span>  
 <span data-ttu-id="b8ab3-111">Alle Rückrufe, die diese Garbagecollection betreffen treten zwischen den `GarbageCollectionStarted` Rückruf und dem entsprechenden [ICorProfilerCallback2:: GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md) Rückruf.</span><span class="sxs-lookup"><span data-stu-id="b8ab3-111">All callbacks that pertain to this garbage collection will occur between the `GarbageCollectionStarted` callback and the corresponding [ICorProfilerCallback2::GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md) callback.</span></span> <span data-ttu-id="b8ab3-112">Diese Rückrufe müssen nicht im selben Thread ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="b8ab3-112">These callbacks need not occur on the same thread.</span></span>  
  
 <span data-ttu-id="b8ab3-113">Gefahrlos für den Profiler zum Überprüfen von Objekten in ihren ursprünglichen Speicherorten während der `GarbageCollectionStarted` Rückruf.</span><span class="sxs-lookup"><span data-stu-id="b8ab3-113">It is safe for the profiler to inspect objects in their original locations during the `GarbageCollectionStarted` callback.</span></span> <span data-ttu-id="b8ab3-114">Der Garbage Collector beginnt Verschieben von Objekten nach der Rückgabe von `GarbageCollectionStarted`.</span><span class="sxs-lookup"><span data-stu-id="b8ab3-114">The garbage collector will begin moving objects after the return from `GarbageCollectionStarted`.</span></span> <span data-ttu-id="b8ab3-115">Nachdem der Profiler von diesem Rückruf zurückgegeben wurde, sollten der Profiler alle Objekt-IDs ungültig werden, bis er erhält eine `ICorProfilerCallback2::GarbageCollectionFinished` Rückruf.</span><span class="sxs-lookup"><span data-stu-id="b8ab3-115">After the profiler has returned from this callback, the profiler should consider all object IDs to be invalid until it receives a `ICorProfilerCallback2::GarbageCollectionFinished` callback.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b8ab3-116">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b8ab3-116">Requirements</span></span>  
 <span data-ttu-id="b8ab3-117">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b8ab3-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b8ab3-118">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="b8ab3-118">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="b8ab3-119">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b8ab3-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b8ab3-120">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b8ab3-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b8ab3-121">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b8ab3-121">See Also</span></span>  
 [<span data-ttu-id="b8ab3-122">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b8ab3-122">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="b8ab3-123">ICorProfilerCallback2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="b8ab3-123">ICorProfilerCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)