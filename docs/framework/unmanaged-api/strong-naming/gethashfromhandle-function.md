---
title: GetHashFromHandle-Funktion
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: GetHashFromHandle
api_location: mscoree.dll
api_type: DLLExport
f1_keywords: GetHashFromHandle
helpviewer_keywords: GetHashFromHandle function [.NET Framework strong naming]
ms.assetid: 9e00337f-b307-4602-9bc3-965a8dbf02cd
topic_type: apiref
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 1ccb6d3b50e70d69b706f63be8a783ad6d7f7cdf
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="gethashfromhandle-function"></a><span data-ttu-id="f9323-102">GetHashFromHandle-Funktion</span><span class="sxs-lookup"><span data-stu-id="f9323-102">GetHashFromHandle Function</span></span>
<span data-ttu-id="f9323-103">Generiert einen Hash des Inhalts der Datei mit das angegebene Dateihandle mithilfe des angegebenen Hashalgorithmus.</span><span class="sxs-lookup"><span data-stu-id="f9323-103">Generates a hash over the contents of the file with the specified file handle, using the specified hash algorithm.</span></span>  
  
 <span data-ttu-id="f9323-104">Diese Funktion ist veraltet.</span><span class="sxs-lookup"><span data-stu-id="f9323-104">This function has been deprecated.</span></span> <span data-ttu-id="f9323-105">Verwenden der [ICLRStrongName:: GetHashFromHandle](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromhandle-method.md) Methode stattdessen.</span><span class="sxs-lookup"><span data-stu-id="f9323-105">Use the [ICLRStrongName::GetHashFromHandle](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromhandle-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f9323-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="f9323-106">Syntax</span></span>  
  
```  
HRESULT GetHashFromHandle (  
    [in]  HANDLE   hFile,  
    [in, out] unsigned int   *piHashAlg,  
    [out] BYTE     *pbHash,  
    [in]  DWORD    cchHash,  
    [out] DWORD    *pchHash  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f9323-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="f9323-107">Parameters</span></span>  
 `hFile`  
 <span data-ttu-id="f9323-108">[in] Das Handle der Datei, der Hashwert berechnet werden soll.</span><span class="sxs-lookup"><span data-stu-id="f9323-108">[in] The handle of the file to be hashed.</span></span>  
  
 `piHashAlg`  
 <span data-ttu-id="f9323-109">[in, out] Eine Konstante, die den Hashalgorithmus angibt.</span><span class="sxs-lookup"><span data-stu-id="f9323-109">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="f9323-110">Verwenden Sie 0 (null) für den Standardalgorithmus.</span><span class="sxs-lookup"><span data-stu-id="f9323-110">Use zero for the default algorithm.</span></span>  
  
 `pbHash`  
 <span data-ttu-id="f9323-111">[out] Der zurückgegebene Hashpuffer.</span><span class="sxs-lookup"><span data-stu-id="f9323-111">[out] The returned hash buffer.</span></span>  
  
 `cchHash`  
 <span data-ttu-id="f9323-112">[in] Die angeforderte maximale Größe der `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="f9323-112">[in] The requested maximum size of `pbHash`.</span></span>  
  
 `pchHash`  
 <span data-ttu-id="f9323-113">[out] Die Größe in Bytes, der zurückgegebenen `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="f9323-113">[out] The size, in bytes, of the returned `pbHash`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f9323-114">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="f9323-114">Requirements</span></span>  
 <span data-ttu-id="f9323-115">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f9323-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f9323-116">**Header:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="f9323-116">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="f9323-117">**Bibliothek:** als Ressource in MsCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="f9323-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="f9323-118">**.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f9323-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f9323-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f9323-119">See Also</span></span>  
 [<span data-ttu-id="f9323-120">GetHashFromHandle-Methode</span><span class="sxs-lookup"><span data-stu-id="f9323-120">GetHashFromHandle Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromhandle-method.md)  
 [<span data-ttu-id="f9323-121">ICLRStrongName-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="f9323-121">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)