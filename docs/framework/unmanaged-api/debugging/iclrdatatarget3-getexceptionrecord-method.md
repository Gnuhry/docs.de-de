---
title: ICLRDataTarget3::GetExceptionRecord-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs: cpp
api_name: ICLRDataTarget3.GetExceptionRecord
api_location: mscordbi.dll
api_type: COM
ms.assetid: 6643c2af-2ee6-4789-aa25-1d8eaf500c94
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: f8c9ac4ecc0cffda4038129b1244b81501e9a1f7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="iclrdatatarget3getexceptionrecord-method"></a><span data-ttu-id="81129-102">ICLRDataTarget3::GetExceptionRecord-Methode</span><span class="sxs-lookup"><span data-stu-id="81129-102">ICLRDataTarget3::GetExceptionRecord Method</span></span>
<span data-ttu-id="81129-103">Wird durch die Common Language Runtime (CLR)- Datenzugriffsdienste aufgerufen, um den Ausnahmedatensatz abzurufen, der dem Zielprozess zugordnet ist.</span><span class="sxs-lookup"><span data-stu-id="81129-103">Called by the common language runtime (CLR) data access services to retrieve the exception record associated with the target process.</span></span> <span data-ttu-id="81129-104">Z. B. bei einem, wäre dies entspricht dem Ausnahmedatensatz, der über übergeben der `ExceptionParam` Argument an die [MiniDumpWriteDump](http://msdn.microsoft.com/library/windows/desktop/ms680360.aspx) -Funktion in der Windows Debug-Hilfe-Bibliothek (DbgHelp).</span><span class="sxs-lookup"><span data-stu-id="81129-104">For example, for a dump target, this would be equivalent to the exception record passed in via the `ExceptionParam` argument to the [MiniDumpWriteDump](http://msdn.microsoft.com/library/windows/desktop/ms680360.aspx) function in the Windows Debug Help Library (DbgHelp).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="81129-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="81129-105">Syntax</span></span>  
  
```cpp  
HRESULT GetExceptionRecord(  
    [in] ULONG32 bufferSize,  
    [out] ULONG32* bufferUsed,  
    [out, size_is(bufferSize] BYTE* buffer  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="81129-106">Parameter</span><span class="sxs-lookup"><span data-stu-id="81129-106">Parameters</span></span>  
 `bufferSize`  
 <span data-ttu-id="81129-107">[in] Die Eingabepuffergröße, in Bytes.</span><span class="sxs-lookup"><span data-stu-id="81129-107">[in] The input buffer size, in bytes.</span></span> <span data-ttu-id="81129-108">Diese Angabe muss gleich `sizeof(` [MINIDUMP_EXCEPTION](http://msdn.microsoft.com/library/windows/desktop/ms680367.aspx)`)`.</span><span class="sxs-lookup"><span data-stu-id="81129-108">This must be equal to `sizeof(`[MINIDUMP_EXCEPTION](http://msdn.microsoft.com/library/windows/desktop/ms680367.aspx)`)`.</span></span>  
  
 `bufferUsed`  
 <span data-ttu-id="81129-109">[out] Ein Zeiger auf ein `ULONG32`-Typ, der die Anzahl von Bytes empfängt, die tatsächlich in den Puffer geschrieben werden.</span><span class="sxs-lookup"><span data-stu-id="81129-109">[out] A pointer to a `ULONG32` type that receives the number of bytes actually written to the buffer.</span></span>  
  
 `buffer`  
 <span data-ttu-id="81129-110">[out] Ein Zeiger zu einem Arbeitsspeicherpuffer, der eine Kopie des Ausnahmedatensatzes empfängt.</span><span class="sxs-lookup"><span data-stu-id="81129-110">[out] A pointer to a memory buffer that receives a copy of the exception record.</span></span> <span data-ttu-id="81129-111">Der Ausnahmedatensatz wird zurückgegeben, als eine [MINIDUMP_EXCEPTION](http://msdn.microsoft.com/library/windows/desktop/ms680367.aspx) Typ.</span><span class="sxs-lookup"><span data-stu-id="81129-111">The exception record is returned as a [MINIDUMP_EXCEPTION](http://msdn.microsoft.com/library/windows/desktop/ms680367.aspx) type.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="81129-112">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="81129-112">Return Value</span></span>  
 <span data-ttu-id="81129-113">Der Rückgabewert ist `S_OK` bei Erfolg oder ein Fehler-`HRESULT`-Code bei einem Fehler.</span><span class="sxs-lookup"><span data-stu-id="81129-113">The return value is `S_OK` on success, or a failure `HRESULT` code on failure.</span></span> <span data-ttu-id="81129-114">Zu den `HRESULT`-Codes können u. a. folgende Codes gehören:</span><span class="sxs-lookup"><span data-stu-id="81129-114">The `HRESULT` codes can include but are not limited to the following:</span></span>  
  
|<span data-ttu-id="81129-115">Rückgabecode</span><span class="sxs-lookup"><span data-stu-id="81129-115">Return code</span></span>|<span data-ttu-id="81129-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="81129-116">Description</span></span>|  
|-----------------|-----------------|  
|`S_OK`|<span data-ttu-id="81129-117">Methode war erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="81129-117">Method succeeded.</span></span> <span data-ttu-id="81129-118">Der Ausnahmedatensatz ist in den Ausgabepuffer kopiert worden.</span><span class="sxs-lookup"><span data-stu-id="81129-118">The exception record has been copied to the output buffer.</span></span>|  
|`HRESULT_FROM_WIN32(ERROR_NOT_FOUND)`|<span data-ttu-id="81129-119">Kein Ausnahmedatensatz ist dem Ziel zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="81129-119">No exception record is associated with the target.</span></span>|  
|`HRESULT_FROM_WIN32(ERROR_BAD_LENGTH)`|<span data-ttu-id="81129-120">Die Eingabepuffergröße ist ungleich `sizeof(MINIDUMP_EXCEPTION)`.</span><span class="sxs-lookup"><span data-stu-id="81129-120">The input buffer size is not equal to `sizeof(MINIDUMP_EXCEPTION)`.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="81129-121">Hinweise</span><span class="sxs-lookup"><span data-stu-id="81129-121">Remarks</span></span>  
 <span data-ttu-id="81129-122">[MINIDUMP_EXCEPTION](http://msdn.microsoft.com/library/windows/desktop/ms680367.aspx) ist eine Struktur, die in dbghelp.h und imagehlp.h im Windows SDK definiert.</span><span class="sxs-lookup"><span data-stu-id="81129-122">[MINIDUMP_EXCEPTION](http://msdn.microsoft.com/library/windows/desktop/ms680367.aspx) is a structure defined in dbghelp.h and imagehlp.h in the Windows SDK.</span></span>  
  
 <span data-ttu-id="81129-123">Diese Methode wird vom Writer der Debuganwendung implementiert.</span><span class="sxs-lookup"><span data-stu-id="81129-123">This method is implemented by the writer of the debugging application.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="81129-124">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="81129-124">Requirements</span></span>  
 <span data-ttu-id="81129-125">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="81129-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="81129-126">**Header:** ClrData.idl, ClrData.h</span><span class="sxs-lookup"><span data-stu-id="81129-126">**Header:** ClrData.idl, ClrData.h</span></span>  
  
 <span data-ttu-id="81129-127">**Bibliothek:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="81129-127">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="81129-128">**.NET Framework-Versionen:**[!INCLUDE[v451_update](../../../../includes/v451-update-md.md)]</span><span class="sxs-lookup"><span data-stu-id="81129-128">**.NET Framework Versions:** [!INCLUDE[v451_update](../../../../includes/v451-update-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="81129-129">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="81129-129">See Also</span></span>  
 [<span data-ttu-id="81129-130">ICLRDataTarget3-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="81129-130">ICLRDataTarget3 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget3-interface.md)  
 [<span data-ttu-id="81129-131">GetExceptionContextRecord-Methode</span><span class="sxs-lookup"><span data-stu-id="81129-131">GetExceptionContextRecord Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget3-getexceptioncontextrecord-method.md)  
 [<span data-ttu-id="81129-132">GetExceptionThreadID-Methode</span><span class="sxs-lookup"><span data-stu-id="81129-132">GetExceptionThreadID Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/iclrdatatarget3-getexceptionthreadid-method.md)