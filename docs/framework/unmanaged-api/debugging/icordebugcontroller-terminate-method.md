---
title: ICorDebugController::Terminate-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugController.Terminate
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugController::Terminate
helpviewer_keywords:
- Terminate method, ICorDebugController interface [.NET Framework debugging]
- ICorDebugController::Terminate method [.NET Framework debugging]
ms.assetid: 4275af0c-b5a7-4e4c-97c9-7e41f36b2dd8
topic_type: apiref
caps.latest.revision: "14"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: fb3831e2640de8ad34299695b571cb4071974bd6
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugcontrollerterminate-method"></a>ICorDebugController::Terminate-Methode
Beendet den Prozess mit dem angegebenen Exitcode.  
  
> [!NOTE]
>  Diese Methode ist ein Wrapper für die Win32- `TerminateProcess` Funktion. Daher `Terminate` verwendet den Exitcode in der gleichen Weise wie die Win32 `TerminateProcess` Funktion verwendet.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT Terminate (  
    [in] UINT exitCode  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `exitCode`  
 [in] Ein numerischer Wert, der den Exitcode. Die gültigen numerischen Werte sind in Winbase.h definiert.  
  
## <a name="remarks"></a>Hinweise  
 Wenn der Prozess, wenn beendet wird `Terminate` wird aufgerufen, der Prozess sollte weiterhin mithilfe der [ICorDebugController:: Continue](../../../../docs/framework/unmanaged-api/debugging/icordebugcontroller-continue-method.md) Methode, damit der Debugger die Bestätigung für die Beendigung über empfängt die [ ICorDebugManagedCallback:: ExitProcess](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitprocess-method.md) oder [ICorDebugManagedCallback:: ExitAppDomain](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-exitappdomain-method.md) Rückruf.  
  
> [!NOTE]
>  Diese Methode wird durch eine Anwendungsdomäne nicht implementiert. D. h. er ist nicht am implementiert die <xref:System.AppDomain> Ebene.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 
