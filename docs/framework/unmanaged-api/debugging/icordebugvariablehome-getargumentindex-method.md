---
title: ICorDebugVariableHome::GetArgumentIndex-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
api_name: ICorDebugVariableHome.GetArgumentIndex
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugVariableHome::GetArgumentIndex
helpviewer_keywords:
- ICorDebugVariableHome::GetArgumentiIndex method [.NET Framework debugging]
- GetArgumentIndex method, ICorDebugVariableHome interface [.NET Framework debugging]
ms.assetid: e86fcc72-388d-4009-ab21-8f9c3323e9a3
topic_type: apiref
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 175e45758d26d8168279c825d41ee58d049edf0b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugvariablehomegetargumentindex-method"></a>ICorDebugVariableHome::GetArgumentIndex-Methode
Ruft den Index ein Funktionsargument ab.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetArgumentIndex(  
    [out] ULONG32* pArgumentIndex  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `pArgumentIndex`  
 [out] Ein Zeiger auf den Argumentindex.  
  
## <a name="return-value"></a>Rückgabewert  
 Die Methode gibt die folgenden Werte zurück.  
  
|Wert|Beschreibung|  
|-----------|-----------------|  
|`S_OK`|Der Methodenaufruf zurückgegebene einen gültiges Argumentindex.|  
|`E_FAIL`|Die aktuelle [ICorDebugVariableHome](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md) Instanz darstellt, eine lokale Variable.|  
  
## <a name="remarks"></a>Hinweise  
 Der Argumentindex kann zum Abrufen von Metadaten für dieses Argument verwendet werden.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorDebug.idl, CorDebug.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v462plus](../../../../includes/net-current-v462plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [ICorDebugVariableHome-Schnittstelle](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablehome-interface.md)
