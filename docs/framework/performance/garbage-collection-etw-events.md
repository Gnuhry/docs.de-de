---
title: Garbage Collection-ETW-Ereignisse
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- GC events
- garbage collection events [.NET Framework]
- ETW, garbage collection events (CLR)
ms.assetid: f14b6fd7-0966-4d87-bc89-54ef3a44a94a
caps.latest.revision: "21"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 06fc335e4b8011afd92e698b20e4b84572b153c3
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="garbage-collection-etw-events"></a>Garbage Collection-ETW-Ereignisse
<a name="top"></a> Diese Ereignisse sammeln Informationen, die die Garbage Collection betreffen. Sie helfen beim Analysieren und Debuggen, einschließlich der Ermittlung, wie oft die Garbage Collection durchgeführt wurde, wie viel Arbeitsspeicher während der Garbage Collection freigegeben wurde usw.  
  
 Diese Kategorie umfasst die folgenden Ereignisse:  
  
-   [GCStart_V1-Ereignis](#gcstart_v1_event)  
  
-   [GCEnd_V1-Ereignis](#gcend_v1_event)  
  
-   [GCHeapStats_V1-Ereignis](#gcheapstats_v1_event)  
  
-   [GCCreateSegment_V1-Ereignis](#gccreatesegment_v1_event)  
  
-   [GCFreeSegment_V1-Ereignis](#gcfreesegment_v1_event)  
  
-   [GCRestartEEBegin_V1-Ereignis](#gcrestarteebegin_v1_event)  
  
-   [GCRestartEEEnd_V1-Ereignis](#gcrestarteeend_v1_event)  
  
-   [GCSuspendEE_V1-Ereignis](#gcsuspendee_v1_event)  
  
-   [GCSuspendEEEnd_V1-Ereignis](#gcsuspendeeend_v1_event)  
  
-   [GCAllocationTick_V2-Ereignis](#gcallocationtick_v2_event)  
  
-   [GCFinalizersBegin_V1-Ereignis](#gcfinalizersbegin_v1_event)  
  
-   [GCFinalizersEnd_V1-Ereignis](#gcfinalizersend_v1_event)  
  
-   [GCCreateConcurrentThread_V1-Ereignis](#gccreateconcurrentthread_v1_event)  
  
-   [GCTerminateConcurrentThread_V1-Ereignis](#gcterminateconcurrentthread_v1_event)  
  
<a name="gcstart_v1_event"></a>   
## <a name="gcstartv1-event"></a>GCStart_V1-Ereignis  
 Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an. (Weitere Informationen finden Sie unter [CLR ETW Keywords and Levels](../../../docs/framework/performance/clr-etw-keywords-and-levels.md).)  
  
|Schlüsselwort zum Auslösen des Ereignisses|Ebene|  
|-----------------------------------|-----------|  
|`GCKeyword` (0x1)|Information (4)|  
  
 Die folgende Tabelle zeigt die Ereignisinformationen an.  
  
|Ereignis|Ereignis-ID|Wird ausgelöst, wenn|  
|-----------|--------------|-----------------|  
|`GCStart_V1`|1|Eine Garbage Collection gestartet wurde.|  
  
 Die folgende Tabelle zeigt die Ereignisdaten an.  
  
|Feldname|Datentyp|Beschreibung|  
|----------------|---------------|-----------------|  
|Anzahl|win:UInt32|Die *n*-te Garbage Collection.|  
|Tiefe|win:UInt32|Die erfasste Generation.|  
|Grund|win:UInt32|Grund für die Auslösung der Garbage Collection:<br /><br /> 0x0 – Zuordnung für kleinen Objektheap.<br /><br /> 0x1 – Induziert.<br /><br /> 0x2 – Wenig Arbeitsspeicher<br /><br /> 0x3 – Leer.<br /><br /> 0x4 – Zuordnung für großen Objektheap.<br /><br /> 0x5 – Nicht genug Speicherplatz (für kleinen Objektheap).<br /><br /> 0x6 – Nicht genügend Speicherplatz (für großen Objektheap)<br /><br /> 0x7 – Induziert, aber nicht als blockierend erzwungen.|  
|Typ|win:UInt32|0x0 – Blockieren der Garbage Collection außerhalb der Garbage Collection im Hintergrund aufgetreten.<br /><br /> 0x1 – Garbage Collection im Hintergrund.<br /><br /> 0x2 – Blockieren der Garbage Collection während der Garbage Collection im Hintergrund aufgetreten.|  
|ClrInstanceID|win:UInt16|Eindeutige ID für die Instanz von CLR oder CoreCLR.|  
  
 [Zurück nach oben](#top)  
  
<a name="gcend_v1_event"></a>   
## <a name="gcendv1-event"></a>GCEnd_V1-Ereignis  
 Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an.  
  
|Schlüsselwort zum Auslösen des Ereignisses|Ebene|  
|-----------------------------------|-----------|  
|`GCKeyword` (0x1)|Information (4)|  
  
 Die folgende Tabelle zeigt die Ereignisinformationen an.  
  
|Ereignis|Ereignis-ID|Wird ausgelöst, wenn|  
|-----------|--------------|-----------------|  
|`GCEnd_V1`|2|Die Garbage Collection beendet wurde.|  
  
 Die folgende Tabelle zeigt die Ereignisdaten an.  
  
|Feldname|Datentyp|Beschreibung|  
|----------------|---------------|-----------------|  
|Anzahl|win:UInt32|Die *n*-te Garbage Collection.|  
|Tiefe|win:UInt32|Die Generation, die erfasst wurde.|  
|ClrInstanceID|win:UInt16|Eindeutige ID für die Instanz von CLR oder CoreCLR.|  
  
 [Zurück nach oben](#top)  
  
<a name="gcheapstats_v1_event"></a>   
## <a name="gcheapstatsv1-event"></a>GCHeapStats_V1-Ereignis  
 Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an.  
  
|Schlüsselwort zum Auslösen des Ereignisses|Ebene|  
|-----------------------------------|-----------|  
|`GCKeyword` (0x1)|Information (4)|  
  
 Die folgende Tabelle zeigt die Ereignisinformationen an.  
  
|Ereignis|Ereignis-ID|Beschreibung|  
|-----------|--------------|-----------------|  
|`GCHeapStats_V1`|4|Zeigt die Heapstatistik am Ende jeder Garbage Collection an.|  
  
 Die folgende Tabelle zeigt die Ereignisdaten an.  
  
|Feldname|Datentyp|Beschreibung|  
|----------------|---------------|-----------------|  
|GenerationSize0|win:UInt64|Die Größe des Arbeitsspeichers der Generation 0 in Bytes.|  
|TotalPromotedSize0|win:UInt64|Die Anzahl der Bytes, die von Generation 0 zu Generation 1 höher gestuft werden.|  
|GenerationSize1|win:UInt64|Die Größe des Arbeitsspeichers der Generation 1 in Bytes.|  
|TotalPromotedSize1|win:UInt64|Die Anzahl der Bytes, die von Generation 1 zu Generation 2 höher gestuft werden.|  
|GenerationSize2|win:UInt64|Die Größe des Arbeitsspeichers der Generation 2 in Bytes.|  
|TotalPromotedSize2|win:UInt64|Die Anzahl der Bytes, die nach der letzten Garbage Collection in Generation 2 noch vorhanden sind.|  
|GenerationSize3|win:UInt64|Die Größe des großen Objektheaps in Bytes.|  
|TotalPromotedSize3|win:UInt64|Die Anzahl der Bytes, die nach der letzten Garbage Collection im großen Objektheap noch vorhanden sind.|  
|FinalizationPromotedSize|win:UInt64|Die Gesamtgröße der Objekte in Bytes, die auf einen Abschluss warten.|  
|FinalizationPromotedCount|win:UInt64|Die Anzahl der Objekte, die auf einen Abschluss warten.|  
|PinnedObjectCount|win:UInt32|Die Anzahl der fixierten (unverschiebbaren) Objekte.|  
|SinkBlockCount|win:UInt32|Die Anzahl der verwendeten Synchronisierungsblöcke.|  
|GCHandleCount|win:UInt32|Die Anzahl der verwendeten Garbage Collection-Handles.|  
|ClrInstanceID|win:UInt16|Eindeutige ID für die Instanz von CLR oder CoreCLR.|  
  
 [Zurück nach oben](#top)  
  
<a name="gccreatesegment_v1_event"></a>   
## <a name="gccreatesegmentv1-event"></a>GCCreateSegment_V1-Ereignis  
 Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an.  
  
|Schlüsselwort zum Auslösen des Ereignisses|Ebene|  
|-----------------------------------|-----------|  
|`GCKeyword` (0x1)|Information (4)|  
  
 Die folgende Tabelle zeigt die Ereignisinformationen an.  
  
|Ereignis|Ereignis-ID|Wird ausgelöst, wenn|  
|-----------|--------------|-----------------|  
|`GCCreateSegment_V1`|5|Neues Garbage Collection-Segment wurde erstellt. Darüber hinaus wird dieses Ereignis für jedes vorhandene Segment ausgelöst, wenn die Ablaufverfolgung für einen Prozess aktiviert ist, der bereits ausgeführt wird.|  
  
 Die folgende Tabelle zeigt die Ereignisdaten an.  
  
|Feldname|Datentyp|Beschreibung|  
|----------------|---------------|-----------------|  
|Adresse|win:UInt64|Die Adresse des Segments.|  
|Größe|win:UInt64|Die Größe des Segments.|  
|Typ|win:UInt32|0x0 – Kleiner Objektheap.<br /><br /> 0x1 – Großer Objektheap.<br /><br /> 0x2 – Schreibgeschützter Heap.|  
|ClrInstanceID|win:UInt16|Eindeutige ID für die Instanz von CLR oder CoreCLR.|  
  
 Beachten Sie, dass die Größe der Segmente, die vom Garbage Collector zugeordnet werden, implementierungsspezifisch ist und jederzeit, auch in regelmäßigen Updates, geändert werden kann. Für eine Anwendung darf weder eine bestimmte Segmentgröße vorausgesetzt werden, noch darf sie von einer bestimmten Segmentgröße abhängen noch darf in ihr versucht werden, die Menge des für Segmentbelegungen verfügbaren Speichers zu konfigurieren.  
  
 [Zurück nach oben](#top)  
  
<a name="gcfreesegment_v1_event"></a>   
## <a name="gcfreesegmentv1-event"></a>GCFreeSegment_V1-Ereignis  
 Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an.  
  
|Schlüsselwort zum Auslösen des Ereignisses|Ebene|  
|-----------------------------------|-----------|  
|`GCKeyword` (0x1)|Information (4)|  
  
 Die folgende Tabelle zeigt die Ereignisinformationen an.  
  
|Ereignis|Ereignis-ID|Wird ausgelöst, wenn|  
|-----------|--------------|-----------------|  
|`GCFreeSegment_V1`|6|Ein Garbage Collection-Segment freigegeben wurde.|  
  
 Die folgende Tabelle zeigt die Ereignisdaten an.  
  
|Feldname|Datentyp|Beschreibung|  
|----------------|---------------|-----------------|  
|Adresse|win:UInt64|Die Adresse des Segments.|  
|ClrInstanceID|win:UInt16|Eindeutige ID für die Instanz von CLR oder CoreCLR.|  
  
 [Zurück nach oben](#top)  
  
<a name="gcrestarteebegin_v1_event"></a>   
## <a name="gcrestarteebeginv1-event"></a>GCRestartEEBegin_V1-Ereignis  
 Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an.  
  
|Schlüsselwort zum Auslösen des Ereignisses|Ebene|  
|-----------------------------------|-----------|  
|`GCKeyword` (0x1)|Information (4)|  
  
 Die folgende Tabelle zeigt die Ereignisinformationen an.  
  
|Ereignis|Ereignis-ID|Wird ausgelöst, wenn|  
|-----------|--------------|-----------------|  
|`GCRestartEEBegin_V1`|7|Die Wiederaufnahme der Common Language Runtime-Unterbrechung begonnen hat.|  
  
 Keine Ereignisdaten.  
  
 [Zurück nach oben](#top)  
  
<a name="gcrestarteeend_v1_event"></a>   
## <a name="gcrestarteeendv1-event"></a>GCRestartEEEnd_V1-Ereignis  
 Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an.  
  
|Schlüsselwort zum Auslösen des Ereignisses|Ebene|  
|-----------------------------------|-----------|  
|`GCKeyword` (0x1)|Information (4)|  
  
 Die folgende Tabelle zeigt die Ereignisinformationen an.  
  
|Ereignis|Ereignis-ID|Wird ausgelöst, wenn|  
|-----------|--------------|-----------------|  
|`GCRestartEEEnd_V1`|3|Die Wiederaufnahme der Common Language Runtime-Unterbrechung beendet wurde.|  
  
 Keine Ereignisdaten.  
  
 [Zurück nach oben](#top)  
  
<a name="gcsuspendee_v1_event"></a>   
## <a name="gcsuspendeev1-event"></a>GCSuspendEE_V1-Ereignis  
 Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an.  
  
|Schlüsselwort zum Auslösen des Ereignisses|Ebene|  
|-----------------------------------|-----------|  
|`GCKeyword` (0x1)|Information (4)|  
  
 Die folgende Tabelle zeigt die Ereignisinformationen an.  
  
|Ereignis|Ereignis-ID|Wird ausgelöst, wenn|  
|-----------|--------------|-----------------|  
|`GCSuspendEE_V1`|9|Die Unterbrechung des Ausführungsmoduls für die Garbage Collection gestartet wurde.|  
  
 Die folgende Tabelle zeigt die Ereignisdaten an.  
  
|Feldname|Datentyp|Beschreibung|  
|----------------|---------------|-----------------|  
|Grund|win:UInt16|0x0 – Andere.<br /><br /> 0x1 – Garbage Collection.<br /><br /> 0x2 – Herunterfahren der Anwendungsdomäne.<br /><br /> 0x3 – Codepitching.<br /><br /> 0x4 – Herunterfahren.<br /><br /> 0x5 – Debugger.<br /><br /> 0x6 – Vorbereitung auf Garbage Collection.|  
|Anzahl|win:UInt32|Die Anzahl der GCs zu diesem Zeitpunkt. Normalerweise würde Ihnen danach ein nachfolgender GC-Start angezeigt werden. Diese Anzahl würde dabei um 1 erhöht werden, da der GC-Index während der Garbage Collection erhöht wird.|  
|ClrInstanceID|win:UInt16|Eindeutige ID für die Instanz von CLR oder CoreCLR.|  
  
 [Zurück nach oben](#top)  
  
<a name="gcsuspendeeend_v1_event"></a>   
## <a name="gcsuspendeeendv1-event"></a>GCSuspendEEEnd_V1-Ereignis  
 Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an:  
  
|Schlüsselwort zum Auslösen des Ereignisses|Ebene|  
|-----------------------------------|-----------|  
|`GCKeyword` (0x1)|Information (4)|  
  
 Die folgende Tabelle zeigt die Ereignisinformationen an:  
  
|Ereignis|Ereignis-ID|Wird ausgelöst, wenn|  
|-----------|--------------|-----------------|  
|`GCSuspendEEEnd_V1`|8|Die Unterbrechung des Ausführungsmoduls für die Garbage Collection beendet wurde.|  
  
 Keine Ereignisdaten.  
  
 [Zurück nach oben](#top)  
  
<a name="gcallocationtick_v2_event"></a>   
## <a name="gcallocationtickv2-event"></a>GCAllocationTick_V2-Ereignis  
 Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an.  
  
|Schlüsselwort zum Auslösen des Ereignisses|Ebene|  
|-----------------------------------|-----------|  
|`GCKeyword` (0x1)|Information (4)|  
  
 Die folgende Tabelle zeigt die Ereignisinformationen an.  
  
|Ereignis|Ereignis-ID|Wird ausgelöst, wenn|  
|-----------|--------------|-----------------|  
|`GCAllocationTick_V2`|10|Jedes Mal werden ungefähr 100 KB zugeordnet.|  
  
 Die folgende Tabelle zeigt die Ereignisdaten an.  
  
|Feldname|Datentyp|Beschreibung|  
|----------------|---------------|-----------------|  
|AllocationAmount|win:UInt32|Die Zuordnungsgröße in Bytes. Dieser Wert ist für Zuordnungen präzise, die kleiner als die Länge von ULONG sind (4.294.967.295 Bytes). Wenn die Zuordnung größer ist, enthält dieses Feld einen abgeschnittenen Wert. Verwenden Sie `AllocationAmount64` für sehr große Zuordnungen.|  
|AllocationKind|win:UInt32|0x0 – Kleine Objektzuordnung (Zuordnung erfolgt im kleinen Objektheap).<br /><br /> 0x1 – Große Objektzuordnung (Zuordnung erfolgt im großen Objektheap).|  
|ClrInstanceID|win:UInt16|Eindeutige ID für die Instanz von CLR oder CoreCLR.|  
|AllocationAmount64|win:UInt64|Die Zuordnungsgröße in Bytes. Dieser Wert ist für sehr große Zuordnungen präzise.|  
|TypeId|win:Pointer|Die Adresse der Methodentabelle. Wenn es verschiedene Typen von Objekten gibt, die während dieses Ereignisses zugeordnet wurden, ist dies die Adresse der Methodentabelle, die dem zuletzt zugeordneten Objekt (das Objekt, das den Schwellenwert von 100 KB überschritten hat) entspricht.|  
|TypeName|win:UnicodeString|Der Name des zugeordneten Typs. Wenn es verschiedene Typen von Objekten gibt, die während dieses Ereignisses zugeordnet wurden, ist dies der Typ des zuletzt zugeordneten Objekts (das Objekt, das den Schwellenwert von 100 KB überschritten hat).|  
|HeapIndex|win:UInt32|Der Heap, auf dem das Objekt zugeordnet wurde. Dieser Wert ist 0 (null), wenn die Ausführung mit Garbage Collection für die Arbeitsstation erfolgt.|  
  
 [Zurück nach oben](#top)  
  
<a name="gcfinalizersbegin_v1_event"></a>   
## <a name="gcfinalizersbeginv1-event"></a>GCFinalizersBegin_V1-Ereignis  
 Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an.  
  
|Schlüsselwort zum Auslösen des Ereignisses|Ebene|  
|-----------------------------------|-----------|  
|`GCKeyword` (0x1)|Information (4)|  
  
 Die folgende Tabelle zeigt die Ereignisinformationen an.  
  
|Ereignis|Ereignis-ID|Wird ausgelöst, wenn|  
|-----------|--------------|-----------------|  
|`GCFinalizersBegin_V1`|14|Die Ausführung von Finalizern gestartet wird.|  
  
 Keine Ereignisdaten.  
  
 [Zurück nach oben](#top)  
  
<a name="gcfinalizersend_v1_event"></a>   
## <a name="gcfinalizersendv1-event"></a>GCFinalizersEnd_V1-Ereignis  
 Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an.  
  
|Schlüsselwort zum Auslösen des Ereignisses|Ebene|  
|-----------------------------------|-----------|  
|`GCKeyword` (0x1)|Information (4)|  
  
 Die folgende Tabelle zeigt die Ereignisinformationen an.  
  
|Ereignis|Ereignis-ID|Wird ausgelöst, wenn|  
|-----------|--------------|-----------------|  
|`GCFinalizersEnd_V1`|13|Die Ausführung von Finalizern beendet wird.|  
  
 Die folgende Tabelle zeigt die Ereignisdaten an.  
  
|Feldname|Datentyp|Beschreibung|  
|----------------|---------------|-----------------|  
|Anzahl|win:UInt32|Die Anzahl der ausgeführten Finalizer.|  
|ClrInstanceID|win:UInt16|Eindeutige ID für die Instanz von CLR oder CoreCLR.|  
  
 [Zurück nach oben](#top)  
  
<a name="gccreateconcurrentthread_v1_event"></a>   
## <a name="gccreateconcurrentthreadv1-event"></a>GCCreateConcurrentThread_V1-Ereignis  
 Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an.  
  
|Schlüsselwort zum Auslösen des Ereignisses|Ebene|  
|-----------------------------------|-----------|  
|`GCKeyword` (0x1)|Information (4)|  
|`ThreadingKeyword` (0x10000)|Information (4)|  
  
 Die folgende Tabelle zeigt die Ereignisinformationen an.  
  
|Ereignis|Ereignis-ID|Wird ausgelöst, wenn|  
|-----------|--------------|-----------------|  
|`GCCreateConcurrentThread_V1`|11|Thread für parallele Garbage Collection erstellt wurde.|  
  
 Keine Ereignisdaten.  
  
 [Zurück nach oben](#top)  
  
<a name="gcterminateconcurrentthread_v1_event"></a>   
## <a name="gcterminateconcurrentthreadv1-event"></a>GCTerminateConcurrentThread_V1-Ereignis  
 Die folgende Tabelle zeigt das Schlüsselwort und die Ebene an.  
  
|Schlüsselwort zum Auslösen des Ereignisses|Ebene|  
|-----------------------------------|-----------|  
|`GCKeyword` (0x1)|Information (4)|  
|`ThreadingKeyword` (0x10000)|Information (4)|  
  
 Die folgende Tabelle zeigt die Ereignisinformationen an.  
  
|Ereignis|Ereignis-ID|Wird ausgelöst, wenn|  
|-----------|--------------|-----------------|  
|`GCTerminateConcurrentThread_V1`|12|Thread für parallele Garbage Collection beendet wurde.|  
  
 Keine Ereignisdaten.  
  
## <a name="see-also"></a>Siehe auch  
 [CLR-ETW-Ereignisse](../../../docs/framework/performance/clr-etw-events.md)
