---
title: IHostSyncManager::CreateRWLockWriterEvent-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IHostSyncManager.CreateRWLockWriterEvent
api_location: mscoree.dll
api_type: COM
f1_keywords: IHostSyncManager::CreateRWLockWriterEvent
helpviewer_keywords:
- CreateRWLockWriterEvent method [.NET Framework hosting]
- IHostSyncManager::CreateRWLockWriterEvent method [.NET Framework hosting]
ms.assetid: 70e488c2-cf53-4dc0-ba52-74372d215c41
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: c89dec681102f96f96f1d7f3e802ded0a2df7b4d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="ihostsyncmanagercreaterwlockwriterevent-method"></a><span data-ttu-id="21024-102">IHostSyncManager::CreateRWLockWriterEvent-Methode</span><span class="sxs-lookup"><span data-stu-id="21024-102">IHostSyncManager::CreateRWLockWriterEvent Method</span></span>
<span data-ttu-id="21024-103">Erstellt ein Ereignisobjekt AutoReset-für die Implementierung der eine Sperre des Schreibers.</span><span class="sxs-lookup"><span data-stu-id="21024-103">Creates an auto-reset event object for the implementation of a writer lock.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="21024-104">Syntax</span><span class="sxs-lookup"><span data-stu-id="21024-104">Syntax</span></span>  
  
```  
HRESULT CreateRWLockWriterEvent (  
    [in]  SIZE_T cookie,  
    [out] IHostAutoEvent **ppEvent  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="21024-105">Parameter</span><span class="sxs-lookup"><span data-stu-id="21024-105">Parameters</span></span>  
 `cookie`  
 <span data-ttu-id="21024-106">[in] Ein Cookie, das AutoReset-Ereignis zugeordnet werden soll.</span><span class="sxs-lookup"><span data-stu-id="21024-106">[in] A cookie to associate with the auto-reset event.</span></span>  
  
 `ppEvent`  
 <span data-ttu-id="21024-107">[out] Ein Zeiger auf die Adresse des ein [IHostAutoEvent](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md) -Instanz oder null, wenn das Ereignisobjekt nicht erstellt werden konnte.</span><span class="sxs-lookup"><span data-stu-id="21024-107">[out] A pointer to the address of an [IHostAutoEvent](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md) instance, or null if the event object could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="21024-108">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="21024-108">Return Value</span></span>  
  
|<span data-ttu-id="21024-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="21024-109">HRESULT</span></span>|<span data-ttu-id="21024-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="21024-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="21024-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="21024-111">S_OK</span></span>|<span data-ttu-id="21024-112">`CreateRWLockWriterEvent`wurde erfolgreich zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="21024-112">`CreateRWLockWriterEvent` returned successfully.</span></span>|  
|<span data-ttu-id="21024-113">HOST_E_CLRNOTAVAILABLE ZURÜCK</span><span class="sxs-lookup"><span data-stu-id="21024-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="21024-114">Die common Language Runtime (CLR) wurde nicht in einen Prozess geladen, oder die CLR wird in einem Zustand, in dem er nicht verwalteten Code ausführen oder den Aufruf erfolgreich verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="21024-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="21024-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="21024-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="21024-116">Der Aufruf ist ein Timeout aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="21024-116">The call timed out.</span></span>|  
|<span data-ttu-id="21024-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="21024-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="21024-118">Der Aufrufer ist nicht Besitzer der Sperre.</span><span class="sxs-lookup"><span data-stu-id="21024-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="21024-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="21024-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="21024-120">Ein Ereignis wurde abgebrochen, während ein blockierten Thread oder eine Fiber darauf gewartet.</span><span class="sxs-lookup"><span data-stu-id="21024-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="21024-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="21024-121">E_FAIL</span></span>|<span data-ttu-id="21024-122">Ein Unbekannter Schwerwiegender Fehler aufgetreten ist.</span><span class="sxs-lookup"><span data-stu-id="21024-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="21024-123">Wenn eine Methode E_FAIL zurückgibt, ist die CLR nicht mehr verwendbar innerhalb des Prozesses.</span><span class="sxs-lookup"><span data-stu-id="21024-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="21024-124">Nachfolgende Aufrufe zum Hosten der Methoden HOST_E_CLRNOTAVAILABLE zurück.</span><span class="sxs-lookup"><span data-stu-id="21024-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="21024-125">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="21024-125">E_OUTOFMEMORY</span></span>|<span data-ttu-id="21024-126">Es war nicht genügend Arbeitsspeicher zum Erstellen des angeforderten Ereignisses-Objekts verfügbar.</span><span class="sxs-lookup"><span data-stu-id="21024-126">Not enough memory was available to create the requested event object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="21024-127">Hinweise</span><span class="sxs-lookup"><span data-stu-id="21024-127">Remarks</span></span>  
 <span data-ttu-id="21024-128">Die CLR ruft die `CreateRWLockWriterEvent` Methode zum Abrufen eines Verweises auf eine `IHostAutoEvent` Instanz, in seiner Implementierung von eine Schreibsperre verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="21024-128">The CLR calls the `CreateRWLockWriterEvent` method to get a reference to an `IHostAutoEvent` instance to use in its implementation of a writer lock.</span></span> <span data-ttu-id="21024-129">Der Host kann der angegebenen Cookies verwenden, um zu bestimmen, welche Aufgaben durch Aufrufen der Iterationsmethoden, der auf die Sperre warten der [ICLRSyncManager](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md) Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="21024-129">The host can use the specified cookie to determine which tasks are waiting on the lock by calling the iteration methods of the [ICLRSyncManager](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md) interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="21024-130">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="21024-130">Requirements</span></span>  
 <span data-ttu-id="21024-131">**Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="21024-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="21024-132">**Header:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="21024-132">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="21024-133">**Bibliothek:** als Ressource in MSCorEE.dll enthalten</span><span class="sxs-lookup"><span data-stu-id="21024-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="21024-134">**.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="21024-134">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="21024-135">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="21024-135">See Also</span></span>  
 [<span data-ttu-id="21024-136">ICLRSyncManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="21024-136">ICLRSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrsyncmanager-interface.md)  
 [<span data-ttu-id="21024-137">IHostAutoEvent-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="21024-137">IHostAutoEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostautoevent-interface.md)  
 [<span data-ttu-id="21024-138">IHostManualEvent-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="21024-138">IHostManualEvent Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmanualevent-interface.md)  
 [<span data-ttu-id="21024-139">IHostSyncManager-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="21024-139">IHostSyncManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostsyncmanager-interface.md)