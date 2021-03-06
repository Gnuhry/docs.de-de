---
title: Allgemeine Datentypen (Referenz zur nicht verwalteten API)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: e4ab2c4c-9433-4eba-9e9a-096de406cafb
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 03350825b3de4515a0d30e8644f34df71efa25db
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="common-data-types-unmanaged-api-reference"></a>Allgemeine Datentypen (Referenz zur nicht verwalteten API)
In diesem Thema werden einfache Datentypen aufgelistet, die unverwaltete APIs für .NET Framework verwenden und die über `typedef`-Argumente aus C/C++ definiert sind. Diese Datentypen sind meist Aliase für primitive Datentypen aus C/C++. Die Werte dieser Datentypen sind meist nicht transparent. Das bedeutet, sie werden von einer bestimmten Funktion oder Methode zurückgegeben, sodass sie ohne Änderungen an andere Funktionen oder Methoden übergeben werden können.  
  
|Datentyp|Definition|Definiert in|Beschreibung|  
|---------------|----------------|----------------|-----------------|  
|AppDomainID|`typedef UINT_PTR AppDomainID;`|corprof.h|Der Bezeichner einer Anwendungsdomäne.|  
|AssemblyID|`typedef UINT_PTR AssemblyID;`|corprof.h|Der Bezeichner einer Assembly.|  
|ClassID|`typedef UINT_PTR ClassID;`|corprof.h|Der Bezeichner einer verwalteten Klasse.|  
|CONNID|`typedef DWORD CONNID;`|cordebug.h, mscoree.h|Die Verbindungs-ID eines Threads ist mit einer Instanz von Microsoft SQL Server verbunden.|  
|ContextID|`typedef UINT_PTR ContextID;`|corprof.h|Der Bezeichner des Kontexts, der mit einem bestimmten verwalteten Thread verknüpft ist.|  
|COR_PRF_ELT_INFO|`typedef UINT_PTR COR_PRF_ELT_INFO;`|corprof.h|Ein nicht transparenter Handle, der Informationen über einen bestimmten Stapelrahmen repräsentiert.|  
|COR_PRF_FRAME_INFO|`typedef UINT_PTR COR_PRF_FRAME_INFO;`|corprof.h|Ein nicht transparenter Handle, der auf einen Stapelrahmen zeigt. Er ist nur gültig während des Rückrufs, an den er übergeben wird.|  
|CORDB_ADDRESS|`typedef ULONG64 CORDB_ADDRESS;`|cordebug.h|Eine Adresse im Speicher.|  
|CORDB_CONTINUE_STATUS|`typedef DWORD CORDB_CONTINUE_STATUS;`|cordebug.h|Der Status der Fortsetzung.|  
|CORDB_REGISTER|`typedef ULONG64 CORDB_REGISTER;`|cordebug.h|Der Wert eines CPU-Registers.|  
|FunctionID|`typedef UINT_PTR FunctionID;`|corprof.h|Der Bezeichner einer Funktion oder Methode.|  
|GCHandleID|`typedef UINT_PTR GCHandleID;`|corprof.h|Ein Garbage Collection-Handle.|  
|mdToken|`typedef UINT32 mdToken;`|corprof.h|Ein Metadatentoken (eine Zeile in einer Metadatentabelle).|  
|ModuleID|`typedef UINT_PTR ModuleID;`|corprof.h|Der Bezeichner eines Assemblymoduls.|  
|ObjectID|`typedef UINT_PTR ObjectID;`|corprof.h|Der Bezeichner eines Objekts.|  
|ProcessID|`typedef UINT_PTR ProcessID;`|corprof.h|Der Bezeichner eines verwalteten Prozesses.|  
|ReJITID|`typedef UINT_PTR ReJITID;`|corprof.h|Der Bezeichner einer mit JIT kompilierten Funktion.|  
|AUFGABEN-ID|`typedef UINT64 TASKID;`|cordebug.h, mscoree.h|Der Bezeichner des ein [ICLRTask](../../../docs/framework/unmanaged-api/hosting/iclrtask-interface.md) Instanz.|  
|ThreadID|`typedef UINT_PTR ThreadID;`|corprof.h|Der Bezeichner eines verwalteten Threads.|  
  
## <a name="see-also"></a>Siehe auch  
 [Referenz zur nicht verwalteten API](../../../docs/framework/unmanaged-api/index.md)
