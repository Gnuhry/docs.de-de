---
title: ICorDebugChain::GetCallee-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugChain.GetCallee
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugChain::GetCallee method
helpviewer_keywords:
- ICorDebugChain::GetCallee method [.NET Framework debugging]
- GetCallee method, ICorDebugChain interface [.NET Framework debugging]
ms.assetid: 19560c79-abdc-4bdf-a5fe-eb362a59edc0
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: ed2bf8d8e91799fd0b01012d5d6e212d26a526be
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugchaingetcallee-method"></a><span data-ttu-id="b6202-102">ICorDebugChain::GetCallee-Methode</span><span class="sxs-lookup"><span data-stu-id="b6202-102">ICorDebugChain::GetCallee Method</span></span>
<span data-ttu-id="b6202-103">Ruft die Kette, die durch diese Kette aufgerufen wurde.</span><span class="sxs-lookup"><span data-stu-id="b6202-103">Gets the chain that was called by this chain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b6202-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="b6202-104">Syntax</span></span>  
  
```  
HRESULT GetCallee (  
    [out] ICorDebugChain     **ppChain  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="b6202-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="b6202-105">Parameters</span></span>  
 `ppChain`  
 <span data-ttu-id="b6202-106">[out] Ein Zeiger auf die Adresse eines ICorDebugChain-Objekts, das die aufgerufene Kette darstellt.</span><span class="sxs-lookup"><span data-stu-id="b6202-106">[out] A pointer to the address of an ICorDebugChain object that represents the called chain.</span></span> <span data-ttu-id="b6202-107">Wenn diese Kette zurzeit ausgeführt wird (d. h., wenn diese Kette nicht für eine aufgerufene Kette zurückzugebenden wartet), `ppChain` wird null sein.</span><span class="sxs-lookup"><span data-stu-id="b6202-107">If this chain is currently executing (that is, if this chain is not waiting for a called chain to return), `ppChain` will be null.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b6202-108">Hinweise</span><span class="sxs-lookup"><span data-stu-id="b6202-108">Remarks</span></span>  
 <span data-ttu-id="b6202-109">Diese Kette wartet für die aufgerufene Kette zurückgegeben werden, bevor sie die Ausführung fortsetzt.</span><span class="sxs-lookup"><span data-stu-id="b6202-109">This chain will wait for the called chain to return before it resumes execution.</span></span> <span data-ttu-id="b6202-110">Die aufgerufene Kette möglicherweise in einem anderen Thread im Fall von threadübergreifende Aufrufe.</span><span class="sxs-lookup"><span data-stu-id="b6202-110">The called chain may be on another thread in the case of cross-thread marshaled calls.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b6202-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="b6202-111">Requirements</span></span>  
 <span data-ttu-id="b6202-112">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b6202-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b6202-113">**Header:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b6202-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b6202-114">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b6202-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b6202-115">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b6202-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>