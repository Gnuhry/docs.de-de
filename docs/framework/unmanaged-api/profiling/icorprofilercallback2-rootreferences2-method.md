---
title: ICorProfilerCallback2::RootReferences2-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback2.RootReferences2
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback2::RootReferences2
helpviewer_keywords:
- RootReferences2 method [.NET Framework profiling]
- ICorProfilerCallback2::RootReferences2 method [.NET Framework profiling]
ms.assetid: 55a2f907-d216-42eb-8f2f-e5d59c2eebd6
topic_type: apiref
caps.latest.revision: "13"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 8a0b2e23ba586e7a20ed11de6433b2d87cbe7219
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilercallback2rootreferences2-method"></a><span data-ttu-id="eb410-102">ICorProfilerCallback2::RootReferences2-Methode</span><span class="sxs-lookup"><span data-stu-id="eb410-102">ICorProfilerCallback2::RootReferences2 Method</span></span>
<span data-ttu-id="eb410-103">Benachrichtigt den Profiler zu Stammverweisen, nach eine Garbagecollection aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="eb410-103">Notifies the profiler about root references after a garbage collection has occurred.</span></span> <span data-ttu-id="eb410-104">Diese Methode ist eine Erweiterung der [ICorProfilerCallback:: RootReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-rootreferences-method.md) Methode.</span><span class="sxs-lookup"><span data-stu-id="eb410-104">This method is an extension of the [ICorProfilerCallback::RootReferences](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-rootreferences-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="eb410-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="eb410-105">Syntax</span></span>  
  
```  
HRESULT RootReferences2(  
    [in] ULONG  cRootRefs,  
    [in, size_is(cRootRefs)] ObjectID rootRefIds[],  
    [in, size_is(cRootRefs)] COR_PRF_GC_ROOT_KIND rootKinds[],  
    [in, size_is(cRootRefs)] COR_PRF_GC_ROOT_FLAGS rootFlags[],  
    [in, size_is(cRootRefs)] UINT_PTR rootIds[]);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="eb410-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="eb410-106">Parameters</span></span>  
 `cRootRefs`  
 <span data-ttu-id="eb410-107">[in] Die Anzahl der Elemente in der `rootRefIds`, `rootKinds`, `rootFlags`, und `rootIds` Arrays.</span><span class="sxs-lookup"><span data-stu-id="eb410-107">[in] The number of elements in the `rootRefIds`, `rootKinds`, `rootFlags`, and `rootIds` arrays.</span></span>  
  
 `rootRefIds`  
 <span data-ttu-id="eb410-108">[in] Ein Array von Objekt-IDs, von denen jeder ein statisches Objekt oder ein Objekt auf dem Stapel verweist.</span><span class="sxs-lookup"><span data-stu-id="eb410-108">[in] An array of object IDs, each of which references either a static object or an object on the stack.</span></span> <span data-ttu-id="eb410-109">Elemente in der `rootKinds` Array enthalten Informationen zum Klassifizieren der entsprechenden Elemente in der `rootRefIds` Array.</span><span class="sxs-lookup"><span data-stu-id="eb410-109">Elements in the `rootKinds` array provide information to classify corresponding elements in the `rootRefIds` array.</span></span>  
  
 `rootKinds`  
 <span data-ttu-id="eb410-110">[in] Ein Array von [COR_PRF_GC_ROOT_KIND](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-root-kind-enumeration.md) Werte, die den Typ der Garbage Collection-Stamm angeben.</span><span class="sxs-lookup"><span data-stu-id="eb410-110">[in] An array of [COR_PRF_GC_ROOT_KIND](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-root-kind-enumeration.md) values that indicate the type of the garbage collection root.</span></span>  
  
 `rootFlags`  
 <span data-ttu-id="eb410-111">[in] Ein Array von [COR_PRF_GC_ROOT_FLAGS](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-root-flags-enumeration.md) Werte, die die Eigenschaften eines Garbage Collection-Stamm zu beschreiben.</span><span class="sxs-lookup"><span data-stu-id="eb410-111">[in] An array of [COR_PRF_GC_ROOT_FLAGS](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-root-flags-enumeration.md) values that describe the properties of a garbage collection root.</span></span>  
  
 `rootIds`  
 <span data-ttu-id="eb410-112">[in] Ein Array von UINT_PTR Werten, die in eine ganze Zahl, die zusätzliche Informationen über die Garbage Collection-Stamm, abhängig vom Wert enthält den `rootKinds` Parameter.</span><span class="sxs-lookup"><span data-stu-id="eb410-112">[in] An array of UINT_PTR values that point to an integer that contains additional information about the garbage collection root, depending on the value of the `rootKinds` parameter.</span></span>  
  
 <span data-ttu-id="eb410-113">Wenn der Typ des Stamms einen Stapel ist, ist die Stamm-ID für die Funktion, die die Variable enthält.</span><span class="sxs-lookup"><span data-stu-id="eb410-113">If the type of the root is a stack, the root ID is for the function that contains the variable.</span></span> <span data-ttu-id="eb410-114">Wenn die Stamm-ID 0 ist, ist die Funktion eine unbenannte Funktion, die für die CLR intern ist.</span><span class="sxs-lookup"><span data-stu-id="eb410-114">If that root ID is 0, the function is an unnamed function that is internal to the CLR.</span></span> <span data-ttu-id="eb410-115">Wenn der Typ des Stamms ein Handle ist, ist die Stamm-ID für die Garbage Collection-Handle.</span><span class="sxs-lookup"><span data-stu-id="eb410-115">If the type of the root is a handle, the root ID is for the garbage collection handle.</span></span> <span data-ttu-id="eb410-116">Die ID für die anderen Stammreferenztypen ist ein nicht transparenter Wert und sollte ignoriert werden.</span><span class="sxs-lookup"><span data-stu-id="eb410-116">For the other root types, the ID is an opaque value and should be ignored.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="eb410-117">Hinweise</span><span class="sxs-lookup"><span data-stu-id="eb410-117">Remarks</span></span>  
 <span data-ttu-id="eb410-118">Die `rootRefIds`, `rootKinds`, `rootFlags`, und `rootIds` Arrays sind parallele Arrays.</span><span class="sxs-lookup"><span data-stu-id="eb410-118">The `rootRefIds`, `rootKinds`, `rootFlags`, and `rootIds` arrays are parallel arrays.</span></span> <span data-ttu-id="eb410-119">D. h. `rootRefIds[i]`, `rootKinds[i]`, `rootFlags[i]`, und `rootIds[i]` betreffen alle mit demselben Stamm.</span><span class="sxs-lookup"><span data-stu-id="eb410-119">That is, `rootRefIds[i]`, `rootKinds[i]`, `rootFlags[i]`, and `rootIds[i]` all concern the same root.</span></span>  
  
 <span data-ttu-id="eb410-120">Beide `RootReferences` und `RootReferences2` werden aufgerufen, um den Profiler zu benachrichtigen.</span><span class="sxs-lookup"><span data-stu-id="eb410-120">Both `RootReferences` and `RootReferences2` are called to notify the profiler.</span></span> <span data-ttu-id="eb410-121">Profiler implementieren normalerweise eine Methode oder die andere aber nicht beides, da die Informationen im übergeben `RootReferences2` ist eine Obermenge der übergebenen `RootReferences`.</span><span class="sxs-lookup"><span data-stu-id="eb410-121">Profilers will normally implement one method or the other, but not both, because the information passed in `RootReferences2` is a superset of that passed in `RootReferences`.</span></span>  
  
 <span data-ttu-id="eb410-122">Es ist möglich, dass Einträge in `rootRefIds` als 0 (null), das bedeutet, dass der entsprechende Stammverweis null ist, und nicht auf ein Objekt auf dem verwalteten Heap verweist.</span><span class="sxs-lookup"><span data-stu-id="eb410-122">It is possible for entries in `rootRefIds` to be zero, which implies that the corresponding root reference is null and does not refer to an object on the managed heap.</span></span>  
  
 <span data-ttu-id="eb410-123">Die Objekt-IDs zurückgegebenes `RootReferences2` sind nicht während des Rückrufs selbst gültig, da die Garbagecollection in der Mitte Verschieben von Objekten von alten Adressen auf neue Adressen werden kann.</span><span class="sxs-lookup"><span data-stu-id="eb410-123">The object IDs returned by `RootReferences2` are not valid during the callback itself, because the garbage collection might be in the middle of moving objects from old addresses to new addresses.</span></span> <span data-ttu-id="eb410-124">Deshalb sollten Profiler nicht versuchen, Objekte während eines `RootReferences2`-Aufrufs zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="eb410-124">Therefore, profilers should not attempt to inspect objects during a `RootReferences2` call.</span></span> <span data-ttu-id="eb410-125">Wenn [ICorProfilerCallback2:: GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md) wird aufgerufen, alle Objekte an die neuen Speicherorte verschoben wurden und können problemlos geprüft werden.</span><span class="sxs-lookup"><span data-stu-id="eb410-125">When [ICorProfilerCallback2::GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md) is called, all objects have been moved to their new locations and can be safely inspected.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="eb410-126">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="eb410-126">Requirements</span></span>  
 <span data-ttu-id="eb410-127">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="eb410-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eb410-128">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="eb410-128">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="eb410-129">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="eb410-129">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="eb410-130">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="eb410-130">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eb410-131">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="eb410-131">See Also</span></span>  
 [<span data-ttu-id="eb410-132">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="eb410-132">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)  
 [<span data-ttu-id="eb410-133">ICorProfilerCallback2-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="eb410-133">ICorProfilerCallback2 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-interface.md)