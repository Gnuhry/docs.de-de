---
title: ILCodeKind-Enumeration
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs: cpp
api_name: ILCodeKind
api_location: mscordbi.dll
api_type: COM
ms.assetid: b91765e4-82db-46f9-a6dc-6b80610276af
topic_type: apiref
caps.latest.revision: "5"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 61fd5ad93c198000556e8e0be3a278a842ab5716
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="ilcodekind-enumeration"></a>ILCodeKind-Enumeration
[Wird nur in .NET Framework 4.5.2 und neueren Versionen unterstützt]  
  
 Stellt Werte bereit, die angeben, ob der Debugger auf lokale Variablen oder Code, die in der Profiler-ReJIT-Instrumentierung hinzugefügt wurden, zugreifen kann.  
  
## <a name="syntax"></a>Syntax  
  
```cpp
typedef enum ILCodeKind {  
   ILCODE_ORIGINAL_IL = 0x1,  
   ILCODE_REJIT_IL = 0x2,  
} ILCodeKind;  
```  
  
## <a name="members"></a>Member  
  
|Membername|Beschreibung|  
|-----------------|-----------------|  
|`ILCODE_ORIGINAL_IL`|Der Debugger hat keinen Zugriff auf Informationen aus der ReJIT-Instrumentation.|  
|`ILCODE_REJIT_IL`|Der Debugger hat Zugriff auf Informationen aus der ReJIT-Instrumentierung.|  
  
## <a name="remarks"></a>Hinweise  
 Ein Mitglied der `ILCodeKind` Enumeration übergeben werden kann, um die [EnumerateLocalVariablesEx](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-enumeratelocalvariablesex-method.md) und [GetLocalVariableEx](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-getlocalvariableex-method.md) Methoden, um zu bestimmen, ob der Debugger in der Profiler hinzugefügte Variablen zugreifen kann ReJIT-Instrumentierung und die [GetCodeEx](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-getcodeex-method.md) IL instrumentiert, Methode, um zu bestimmen, ob der Debugger zugreifen kann.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [Debuggen von Enumerationen](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)  
 [ICorDebugILFrame4-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-interface.md)  
 [ReJIT: Eine Anleitung](http://blogs.msdn.com/b/davbr/archive/2011/10/12/rejit-a-how-to-guide.aspx)
