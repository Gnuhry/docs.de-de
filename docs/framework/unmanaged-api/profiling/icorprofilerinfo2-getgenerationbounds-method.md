---
title: ICorProfilerInfo2::GetGenerationBounds-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorProfilerInfo2.GetGenerationBounds
api_location: mscorwks.dll
api_type: COM
f1_keywords: ICorProfilerInfo2::GetGenerationBounds
helpviewer_keywords:
- ICorProfilerInfo2::GetGenerationBounds method [.NET Framework profiling]
- GetGenerationBounds method [.NET Framework profiling]
ms.assetid: 9c37185f-d1e0-4a6e-8b99-707f7df61d88
topic_type: apiref
caps.latest.revision: "17"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 33f1e130d214e28b8153b1aaf722c3df97edef37
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="icorprofilerinfo2getgenerationbounds-method"></a>ICorProfilerInfo2::GetGenerationBounds-Methode
Ruft die Arbeitsspeicherbereiche ab, die Segmente des Heaps sind, aus dem sich die verschiedenen Garbage Collection-Generationen zusammensetzen.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetGenerationBounds(  
    [in]  ULONG cObjectRanges,  
    [out] ULONG *pcObjectRanges,  
    [out, size_is(cObjectRanges), length_is(*pcObjectRanges)] COR_PRF_GC_GENERATION_RANGE ranges[]);  
```  
  
#### <a name="parameters"></a>Parameter  
 `cObjectRanges`  
 [in] Die Anzahl der Elemente, die der Aufrufer dem `ranges`-Array zugeordnet hat.  
  
 `pcObjectRanges`  
 [out] Ein Zeiger auf eine ganze Zahl, die die Gesamtzahl der Bereiche angibt, von denen einige oder alle im `ranges`-Array zurückgegeben werden.  
  
 `ranges`  
 [out] Ein Array von [COR_PRF_GC_GENERATION_RANGE](../../../../docs/framework/unmanaged-api/profiling/cor-prf-gc-generation-range-structure.md) Strukturen, von denen jedes einen Bereich (d. h. einen Block) des Arbeitsspeichers innerhalb der Generation, die Garbagecollection unterzogen wird beschreibt.  
  
## <a name="remarks"></a>Hinweise  
 Die `GetGenerationBounds`-Methode kann von jedem Profilerrückruf aufgerufen werden, solange die Garbage Collection nicht durchgeführt wird. Es kann also aufgerufen werden, von einem beliebigen Rückruf mit Ausnahme von those, die occur an zwischen [ICorProfilerCallback2:: GarbageCollectionStarted](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionstarted-method.md) und [ICorProfilerCallback2:: GarbageCollectionFinished](../../../../docs/framework/unmanaged-api/profiling/icorprofilercallback2-garbagecollectionfinished-method.md).  
  
 Die meisten Generationenverschiebungen finden während der Garbage Collections statt. Generationen können zwischen Auflistungen anwachsen, verschieben sich im Allgemeinen jedoch nicht. Deshalb befinden sich die interessantesten Positionen zum Aufrufen von `GetGenerationBounds` in `ICorProfilerCallback2::GarbageCollectionStarted` und `ICorProfilerCallback2::GarbageCollectionFinished`.  
  
 Während des Programmstarts werden einige Objekte in der Regel in den Generationen 3 und 0 von der Common Language Runtime (CLR) selbst zugeordnet. Daher enthalten diese Generationen zu dem Zeitpunkt, an dem der verwaltete Code die Ausführung startet, bereits Objekte. Die Generationen 1 und 2 sind normalerweise (bis auf vom Garbage Collector generierte Dummyobjekte) leer. (Die Größe der Dummyobjekte beträgt in 32-Bit-Implementierungen der CLR 12 Bytes. In 64-Bit-Implementierungen sind diese Objekte größer.) Es sind möglicherweise auch Bereiche der Generation 2 in den Modulen vorhanden, die von Native Image Generator ("NGen.exe") erzeugt wurden. In diesem Fall werden von die Objekten in Generation 2 *fixierte Objekte*, die beim Ausführen von NGen.exe und nicht vom Garbage Collector reserviert werden.  
  
 Diese Funktion verwendet vom Aufrufer reservierte Puffer.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** CorProf.idl, CorProf.h  
  
 **Bibliothek:** CorGuids.lib  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [ICorProfilerInfo-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo-interface.md)  
 [ICorProfilerInfo2-Schnittstelle](../../../../docs/framework/unmanaged-api/profiling/icorprofilerinfo2-interface.md)  
 [Profilerstellungsschnittstellen](../../../../docs/framework/unmanaged-api/profiling/profiling-interfaces.md)  
 [Profilerstellung](../../../../docs/framework/unmanaged-api/profiling/index.md)
