---
title: ICorDebugThread Schnittstelle1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugThread
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugThread
helpviewer_keywords: ICorDebugThread interface [.NET Framework debugging]
ms.assetid: 3930fd9b-2bc3-4b72-80a0-b6eeb94d60c6
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 25b5c8f0720402cce56c69394c6fbe2fb70a6177
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugthread-interface1"></a>ICorDebugThread Schnittstelle1
Stellt einen Thread in einem Prozess dar. Die Lebensdauer einer `ICorDebugThread`-Instanz ist identisch mit der Lebensdauer des von ihr dargestellten Threads.  
  
## <a name="methods"></a>Methoden  
  
|Methode|Beschreibung|  
|------------|-----------------|  
|[ClearCurrentException-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-clearcurrentexception-method.md)|Diese Methode ist nicht implementiert. Verwenden Sie sie nicht.|  
|[CreateEval-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-createeval-method.md)|Erstellt ein ICorDebugEval-Objekt, das ausgeführt wird, für dieses `ICorDebugThread`.|  
|[CreateStepper-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-createstepper-method.md)|Erstellt ein ICorDebugStepper-Objekt, die schrittweise Ausführung des aktiven Frames in diesem ermöglicht `ICorDebugThread`.|  
|[EnumerateChains-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-enumeratechains-method.md)|Ruft einen Schnittstellenzeiger auf einem ICorDebugChainEnum-Enumerator, der alle Stapelketten in diesem enthält `ICorDebugThread`.|  
|[GetActiveChain-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getactivechain-method.md)|Ruft einen Schnittstellenzeiger auf die aktive ICorDebugChain für dieses `ICorDebugThread`.|  
|[GetActiveFrame-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getactiveframe-method.md)|Ruft einen Schnittstellenzeiger auf den aktiven ICorDebugFrame für dieses `ICorDebugThread`.|  
|[GetAppDomain-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getappdomain-method.md)|Ruft einen Schnittstellenzeiger auf die Anwendungsdomäne, in der diese `ICorDebugThread` wird gerade ausgeführt.|  
|[GetCurrentException-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getcurrentexception-method.md)|Ruft einen Schnittstellenzeiger auf ein ICorDebugValue-Objekt, das derzeit von verwaltetem Code ausgelöste eine Ausnahme darstellt.|  
|[GetDebugState-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getdebugstate-method.md)|Ruft einen CorDebugThreadState-Wert, der den aktuellen Debugzustand dieses beschreibt `ICorDebugThread`.|  
|[GetHandle-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-gethandle-method.md)|Ruft das aktuelle Handle für den aktiven Teil dieses `ICorDebugThread`.|  
|[GetID-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getid-method.md)|Ruft den Bezeichner des aktuellen Betriebssystems des aktiven Teils dieses `ICorDebugThread`.|  
|[GetObject-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getobject-method.md)|Ruft einen Schnittstellenzeiger auf die common Language Runtime (CLR)-Thread.|  
|[GetProcess-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getprocess-method.md)|Ruft einen Schnittstellenzeiger an den Prozess ab, der diese `ICorDebugThread` bildet einen Teil.|  
|[GetRegisterSet-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getregisterset-method.md)|Ruft einen Schnittstellenzeiger auf den Registersatz zugeordnete `ICorDebugThread`.|  
|[GetUserState-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-getuserstate-method.md)|Ruft eine bitweise Kombination von CorDebugUserState-Werte, die den aktuellen Zustand dieses beschreiben `ICorDebugThread`.|  
|[SetDebugState-Methode](../../../../docs/framework/unmanaged-api/debugging/icordebugthread-setdebugstate-method.md)|Legt eine bitweise Kombination von `CorDebugThreadState` Werte, die den Debugzustand beschreiben `ICorDebugThread`.|  
  
## <a name="remarks"></a>Hinweise  
  
> [!NOTE]
>  Diese Schnittstelle kann weder computerübergreifend noch prozessübergreifend remote aufgerufen werden.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [Debugschnittstellen](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
