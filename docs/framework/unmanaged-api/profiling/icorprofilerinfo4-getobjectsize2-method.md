---
title: ICorProfilerInfo4::GetObjectSize2-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo4.GetObjectSize2
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo4::GetObjectSize2
helpviewer_keywords:
- GetObjectSize2 method, ICorProfilerInfo4 interface [.NET Framework profiling]
- ICorProfilerInfo4::GetObjectSize2 method [.NET Framework profiling]
ms.assetid: 4a3e43ed-3ee3-4395-ab14-f78b903be13e
topic_type: apiref
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 4898157e6525d3b9da4cfade9862b88252df7b14
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="icorprofilerinfo4getobjectsize2-method"></a>ICorProfilerInfo4::GetObjectSize2-Methode
Gibt die Größe eines angegebenen Objekts zurück. Ersetzt die [ICorProfilerInfo:: GetObjectSize](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-getobjectsize-method.md) Methode, indem die Größen von Objekten, die größer als in ausgedrückt werden können reporting eine `ULONG`.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetObjectSize2(  
    [in]  ObjectID objectId,  
    [out] SIZE_T *pcSize);  
```  
  
#### <a name="parameters"></a>Parameter  
 `objectId`  
 [in] Die ID des Objekts.  
  
 `pcSize`  
 [out] Ein Zeiger auf die Größe des Objekts, in Bytes.  
  
## <a name="remarks"></a>Hinweise  
 Unterschiedliche Objekte der gleichen Typen werden häufig dieselbe Größe aufweisen. Jedoch möglicherweise einige Typen, z. B. Arrays oder Zeichenfolgen, die eine andere Größe für jedes Objekt.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [ICorProfilerInfo4-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo4-interface.md)
