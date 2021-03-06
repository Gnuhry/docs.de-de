---
title: AssemblyOptions-Enumeration
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: AssemblyOptions
api_location: alink.dll
api_type: COM
f1_keywords: AssemblyOptions
helpviewer_keywords:
- Alink API, AssemblyOptions enumeration
- AssemblyOptions enumeration
ms.assetid: 84f83921-64cb-49e3-ac8b-22a0b77b18a8
topic_type: apiref
caps.latest.revision: "5"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: ccbbcabd3fbb372322ca6334f6ab6db4fdafc2f1
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="assemblyoptions-enumeration"></a>AssemblyOptions-Enumeration
Listet die Assemblyoptionen.  
  
## <a name="syntax"></a>Syntax  
  
```  
typedef enum _AssemblyOptions {  
    optAssemTitle = 0,  
    optAssemDescription,  
    optAssemConfig,  
    optAssemOS,  
    optAssemProcessor,  
    optAssemLocale,  
    optAssemVersion,  
    optAssemCompany,  
    optAssemProduct,  
    optAssemProductVersion,  
    optAssemCopyright,  
    optAssemTrademark,  
    optAssemKeyFile,  
    optAssemKeyName,  
    optAssemAlgID,  
    optAssemFlags,  
    optAssemHalfSign,  
    optAssemFileVersion,  
    optAssemSatelliteVer,  
    optLastAssemOption  
}   AssemblyOptions;  
```  
  
## <a name="fields"></a>Felder  
  
|Feld|Beschreibung|  
|-----------|-----------------|  
|optAssemTitle|Zeichenfolge – der Assemblytitel darstellt.|  
|optAssemDescription|Zeichenfolge – enthält die Beschreibung der Assembly.|  
|optAssemConfig|Zeichenfolge – enthält die Assemblykonfiguration.|  
|optAssemOS|-Codierte Zeichenfolge: "dwOSPlatformId.dwOSMajorVersion.dwOSMinorVersion".|  
|optAssemProcessor|ULONG|  
|optAssemLocale|Zeichenfolge – das Gebietsschema der Assembly enthält.|  
|optAssemVersion|-Codierte Zeichenfolge: "Major.Minor.Build.Revision".|  
|optAssemCompany|Zeichenfolge – enthält das Unternehmen.|  
|optAssemProduct|Zeichenfolge – der Name des Produkts enthält.|  
|optAssemProductVersion|Zeichenfolge (auch bekannt als InformationalVersion bezeichnet).|  
|optAssemCopyright|Zeichenfolge – enthält die copyright-Informationen.|  
|optAssemTrademark|Zeichenfolge – enthält die Markeninformationen.|  
|optAssemKeyFile|Zeichenfolge (Dateiname).|  
|optAssemKeyName|Zeichenfolge (Schlüsselname).|  
|optAssemAlgID|ULONG|  
|optAssemFlags|ULONG|  
|optAssemHalfSign|Bool (auch als DelaySign bezeichnet).|  
|optAssemFileVersion|Codierte "Major.Minor.Build.Revision"--identisch mit ProductVersion - Zeichenfolge.|  
|optAssemSatelliteVer|Zeichenfolge – codiert als "Major.Minor.Build.Revision".|  
|optLastAssemOption|Ein Leistungsindikator, der die Anzahl von Elementen.|  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** alink.h  
  
 **Bibliothek**: alink.dll  
  
## <a name="see-also"></a>Siehe auch  
 [Al.exe (Assembly Linker-Tool)](../../../../docs/framework/tools/al-exe-assembly-linker.md)
