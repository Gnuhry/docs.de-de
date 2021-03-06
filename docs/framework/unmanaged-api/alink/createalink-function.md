---
title: CreateALink-Funktion
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CreateALink
api_location: alink.dll
api_type: DLLExport
f1_keywords: CreateALink
helpviewer_keywords:
- CreateALink function
- Alink API, CreateALink function
ms.assetid: fc73bcb9-6af6-44d8-bc39-2f4400325dae
topic_type: apiref
caps.latest.revision: "4"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: a102e9601f751ee8c7e325293e83467b1314ff41
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="createalink-function"></a>CreateALink-Funktion
Erstellt eine Instanz der Assembly Linker aus, und legt einen Zeiger auf die angegebene Schnittstelle fest.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT CreateALink (  
   REFIID riid,  
   IUnknown **ppInterface  
);  
```  
  
#### <a name="parameters"></a>Parameter  
  
|Parameter|Beschreibung|  
|---------------|-----------------|  
|`riid`|Der physische Name einer Assembly Linker-Schnittstellen.|  
|`ppInterface`|Das Verzeichnis, bei erfolgreichem Abschluss einen Zeiger auf die `riid` Schnittstelle.|  
  
## <a name="requirements"></a>Anforderungen  
 **Bibliothek**: alink.dll  
  
## <a name="see-also"></a>Siehe auch  
 [Al.exe (Assembly Linker-Tool)](../../../../docs/framework/tools/al-exe-assembly-linker.md)
