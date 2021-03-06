---
title: IMetaDataImport2::GetGenericParamProps-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataImport2.GetGenericParamProps
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataImport2::GetGenericParamProps
helpviewer_keywords:
- IMetaDataImport2::GetGenericParamProps method [.NET Framework metadata]
- GetGenericParamProps method [.NET Framework metadata]
ms.assetid: dbb21e67-712b-49e7-a27c-a1e73ffd46c5
topic_type: apiref
caps.latest.revision: "11"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: af6ab8fd6e941f5219c1aad2946479dda0b64264
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="imetadataimport2getgenericparamprops-method"></a>IMetaDataImport2::GetGenericParamProps-Methode
Ruft die Metadaten, die durch das angegebene Token dargestellten generischen Parameter zugeordnet.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetGenericParamProps (  
   [in]  mdGenericParam  gp,  
   [out] ULONG           *pulParamSeq,  
   [out] DWORD           *pdwParamFlags,  
   [out] mdToken         *ptOwner,  
   [out] DWORD           *reserved,  
   [out] LPWSTR          wzName,  
   [in]  ULONG           cchName,  
   [out] ULONG           *pchName  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `gp`  
 [in] Das Token, das den generischen Parameter für die zurückzugebenden Metadaten darstellt.  
  
 `pulParamSeq`  
 [out] Die Ordnungsposition der `Type` Parameter in der übergeordneten Konstruktor oder eine Methode.  
  
 `pdwParamFlags`  
 [out] Der Wert der [CorGenericParamAttr](../../../../docs/framework/unmanaged-api/metadata/corgenericparamattr-enumeration.md) -Enumeration, die beschreibt, die `Type` für den generischen Parameter.  
  
 `ptOwner`  
 [out] Eine TypeDef oder MethodDef-Token, das den Besitzer des Parameters darstellt.  
  
 `reserved`  
 [out] Für zukünftige Erweiterungen reserviert.  
  
 `wzName`  
 [out] Der Name des generischen Parameters.  
  
 `cchName`  
 [in] Die Größe der `wzName` Puffer.  
  
 `pchName`  
 [out] Die zurückgegebene Größe des Namens in Breitzeichen.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor.h  
  
 **Bibliothek:** als Ressource in MsCorEE.dll verwendet  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [IMetaDataImport2-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)  
 [IMetaDataImport-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
