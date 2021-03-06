---
title: IMetaDataImport::GetEventProps-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport.GetEventProps
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport::GetEventProps
helpviewer_keywords:
- IMetaDataImport::GetEventProps method [.NET Framework metadata]
- GetEventProps method [.NET Framework metadata]
ms.assetid: 5eaf3b4a-92b7-4d5b-97e0-1e83721e0052
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 9f616e00d79aec864bbb50b168a17e3f131a1aa1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataimportgeteventprops-method"></a>IMetaDataImport::GetEventProps-Methode
Ruft Metadateninformationen für das Ereignis durch das angegebene Ereignistoken, z. B. den deklarierenden Typ, hinzufügen und Entfernen von Entfernungsmethoden für Delegaten und alle Kennzeichnungen und sonstigen zugeordneten Daten dargestellt.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetEventProps (  
   [in]  mdEvent       ev,  
   [out] mdTypeDef     *pClass,   
   [out] LPCWSTR       szEvent,   
   [in]  ULONG         cchEvent,   
   [out] ULONG         *pchEvent,   
   [out] DWORD         *pdwEventFlags,  
   [out] mdToken       *ptkEventType,  
   [out] mdMethodDef   *pmdAddOn,   
   [out] mdMethodDef   *pmdRemoveOn,   
   [out] mdMethodDef   *pmdFire,   
   [out] mdMethodDef   rmdOtherMethod[],   
   [in]  ULONG         cMax,  
   [out] ULONG         *pcOtherMethod  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `ev`  
 [in] Das Ereignis-Metadatentoken, das das Ereignis beim Abrufen von Metadaten für darstellt.  
  
 `pClass`  
 [out] Ein Zeiger auf das TypeDef-Token, das die Klasse darstellt, die das Ereignis deklariert.  
  
 `szEvent`  
 [out] Der Name des Ereignisses verweist `ev`.  
  
 `pchEvent`  
 [in] Die angeforderte Länge in Breitzeichen `szEvent`.  
  
 `pdwEventFlags`  
 [out] Die zurückgegebene Länge in Breitzeichen `szEvent`.  
  
 `ptkEventType`  
 [out] Ein Zeiger auf ein TypeRef-Token oder TypeDef Metadaten token, die <xref:System.Delegate> Typ des Ereignisses.  
  
 `pmdAddOn`  
 [out] Ein Zeiger auf das Metadatentoken, das die Methode für die Handler für das Ereignis fügt darstellt.  
  
 `pmdRemoveOn`  
 [out] Ein Zeiger auf das Metadatentoken, das die Methode für die Handler für das Ereignis entfernt darstellt.  
  
 `pmdFire`  
 [out] Ein Zeiger auf das Metadatentoken der Methode, die das Ereignis auslöst darstellt.  
  
 `rmdOtherMethod`  
 [out] Ein Array von token Zeigern auf andere Methoden, die dem Ereignis zugeordnet werden soll.  
  
 `cMax`  
 [in] Die maximale Größe des `rmdOtherMethod`-Arrays.  
  
 `pcOtherMethod`  
 [out] Die Anzahl der zurückgegebenen Token `rmdOtherMethod`.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor.h  
  
 **Bibliothek:** als Ressource in MsCorEE.dll enthalten  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [IMetaDataImport-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)  
 [IMetaDataImport2-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
