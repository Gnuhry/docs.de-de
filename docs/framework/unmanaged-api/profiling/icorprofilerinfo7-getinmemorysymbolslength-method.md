---
title: 'Icorprofilerinfo7:: Getinmemorysymbolslength-Methode'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
api_name: ICorProfilerInfo7.GetInMemorySymbolsLength
api_location:
- mscorwks.dll
- icorprof.idl
api_type: COM
ms.assetid: d62c4a4c-8a62-45aa-8f01-a8387cf36159
caps.latest.revision: "3"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 34da00bdc33a836e5f459e6e4314f252e1e39e9b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="icorprofilerinfo7getinmemorysymbolslength-method"></a><span data-ttu-id="4e617-102">Icorprofilerinfo7:: Getinmemorysymbolslength-Methode</span><span class="sxs-lookup"><span data-stu-id="4e617-102">ICorProfilerInfo7::GetInMemorySymbolsLength Method</span></span>
<span data-ttu-id="4e617-103">[Wird nur in .NET Framework 4.6.1 und höheren Versionen unterstützt]</span><span class="sxs-lookup"><span data-stu-id="4e617-103">[Supported in the .NET Framework 4.6.1 and later versions]</span></span>  
  
 <span data-ttu-id="4e617-104">Gibt die Länge eines Datenstroms in-Memory-Symbols zurück.</span><span class="sxs-lookup"><span data-stu-id="4e617-104">Returns the length of an in-memory symbol stream.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4e617-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="4e617-105">Syntax</span></span>  
  
```  
HRESULT GetInMemorySymbolsLength(  
        [in] ModuleID moduleId,  
        [out] DWORD* pCountSymbolBytes  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4e617-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="4e617-106">Parameters</span></span>  
 `moduleId`  
 <span data-ttu-id="4e617-107">[in] Der Bezeichner des Moduls, das in-Memory-Datenstrom enthält.</span><span class="sxs-lookup"><span data-stu-id="4e617-107">[in] The identifier of the module containing the in-memory stream.</span></span>  
  
 <span data-ttu-id="4e617-108">pCountSymbolBytes</span><span class="sxs-lookup"><span data-stu-id="4e617-108">pCountSymbolBytes</span></span>  
 <span data-ttu-id="4e617-109">[out] Ein Zeiger auf eine `DWORD` Wert, der, wenn der Rückgabewert dieser Methode die Länge des Streams in Bytes enthält.</span><span class="sxs-lookup"><span data-stu-id="4e617-109">[out] A pointer to a `DWORD` value that, when the method returns, contains the length of the stream in bytes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4e617-110">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="4e617-110">Return Value</span></span>  
 <span data-ttu-id="4e617-111">Gibt die Methode `S_OK` , wenn die Länge des Streams Arbeitsspeicher bestimmt werden kann, auch wenn es auf 0 (null) ist.</span><span class="sxs-lookup"><span data-stu-id="4e617-111">The method returns `S_OK` if the length of the memory stream can be determined, even if it is zero (0).</span></span>  
  
 <span data-ttu-id="4e617-112">Gibt die Methode `CORPROF_E_MODULE_IS_DYNAMIC` , wenn die Methode erstellt wurde mit <xref:System.Reflection.Emit?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="4e617-112">The method returns `CORPROF_E_MODULE_IS_DYNAMIC` if the method was created using <xref:System.Reflection.Emit?displayProperty=nameWithType>.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="4e617-113">Hinweise</span><span class="sxs-lookup"><span data-stu-id="4e617-113">Remarks</span></span>  
 <span data-ttu-id="4e617-114">Wenn in-Memory-Symbole für das Modul ist, wird die Länge des Streams platziert `pCountSymbolBytes`.</span><span class="sxs-lookup"><span data-stu-id="4e617-114">If the module has in-memory symbols, the length of the stream is placed in `pCountSymbolBytes`.</span></span> <span data-ttu-id="4e617-115">Wenn das Modul in-Memory-Symbole, keine `*pCountSymbolBytes = 0`.</span><span class="sxs-lookup"><span data-stu-id="4e617-115">If the module doesn't have in-memory     symbols, `*pCountSymbolBytes = 0`.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4e617-116">Die aktuelle Implementierung unterstützt keine "Reflection.Emit".</span><span class="sxs-lookup"><span data-stu-id="4e617-116">The current implementation does not support Reflection.Emit.</span></span> <span data-ttu-id="4e617-117">Wenn das Modul mithilfe von "Reflection.Emit" erstellt wurde, gibt die Methode `CORPROF_E_MODULE_IS_DYNAMIC`.</span><span class="sxs-lookup"><span data-stu-id="4e617-117">If the module was created by using Reflection.Emit, the method returns `CORPROF_E_MODULE_IS_DYNAMIC`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4e617-118">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="4e617-118">Requirements</span></span>  
 <span data-ttu-id="4e617-119">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4e617-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4e617-120">**Header:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="4e617-120">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="4e617-121">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4e617-121">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4e617-122">**.NET Framework-Versionen:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4e617-122">**.NET Framework Versions:** [!INCLUDE[net_current_v461plus](../../../../includes/net-current-v461plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e617-123">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4e617-123">See Also</span></span>  
 [<span data-ttu-id="4e617-124">ICorProfilerInfo7-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="4e617-124">ICorProfilerInfo7 Interface</span></span>](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo7-interface.md)