---
title: ICorProfilerCallback::FunctionUnloadStarted-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerCallback.FunctionUnloadStarted
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerCallback::FunctionUnloadStarted
helpviewer_keywords:
- FunctionUnloadStarted method [.NET Framework profiling]
- ICorProfilerCallback::FunctionUnloadStarted method [.NET Framework profiling]
ms.assetid: d6a5fa8b-09c6-47a5-b60e-6cf2e355df30
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: efd08eedf6812a46a46135eaa6f0089257f0a209
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="icorprofilercallbackfunctionunloadstarted-method"></a><span data-ttu-id="46f3a-102">ICorProfilerCallback::FunctionUnloadStarted-Methode</span><span class="sxs-lookup"><span data-stu-id="46f3a-102">ICorProfilerCallback::FunctionUnloadStarted Method</span></span>
<span data-ttu-id="46f3a-103">Benachrichtigt den Profiler, dass die Laufzeit gestartet wurde, um eine Funktion zu entladen.</span><span class="sxs-lookup"><span data-stu-id="46f3a-103">Notifies the profiler that the runtime has started to unload a function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="46f3a-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="46f3a-104">Syntax</span></span>  
  
```  
HRESULT FunctionUnloadStarted(  
    [in] FunctionID functionId);   
```  
  
#### <a name="parameters"></a><span data-ttu-id="46f3a-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="46f3a-105">Parameters</span></span>  
 `functionId`  
 <span data-ttu-id="46f3a-106">[in] Die ID der Funktion, die entladen wird.</span><span class="sxs-lookup"><span data-stu-id="46f3a-106">[in] The ID of the function that is being unloaded.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="46f3a-107">Hinweise</span><span class="sxs-lookup"><span data-stu-id="46f3a-107">Remarks</span></span>  
 <span data-ttu-id="46f3a-108">Der Wert, der die `functionId` Parameter ist nicht mehr gültig, nachdem diese Methode an den Aufrufer zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="46f3a-108">The value of the `functionId` parameter is no longer valid after this method returns to the caller.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="46f3a-109">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="46f3a-109">Requirements</span></span>  
 <span data-ttu-id="46f3a-110">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="46f3a-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="46f3a-111">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="46f3a-111">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="46f3a-112">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="46f3a-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="46f3a-113">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="46f3a-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="46f3a-114">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="46f3a-114">See Also</span></span>  
 [<span data-ttu-id="46f3a-115">ICorProfilerCallback-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="46f3a-115">ICorProfilerCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback-interface.md)