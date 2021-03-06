---
title: IMetaDataAssemblyEmit::DefineManifestResource-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataAssemblyEmit.DefineManifestResource
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataAssemblyEmit::DefineManifestResource
helpviewer_keywords:
- DefineManifestResource method [.NET Framework metadata]
- IMetaDataAssemblyEmit::DefineManifestResource method [.NET Framework metadata]
ms.assetid: 27f6d295-0fe9-4cda-b77e-6e7d5c53df09
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 516099f0735e83982fcbab62936bb398c4f7b02d
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="imetadataassemblyemitdefinemanifestresource-method"></a>IMetaDataAssemblyEmit::DefineManifestResource-Methode
Erstellt eine `ManifestResource`-Struktur, die Metadaten für die angegebene Manifestressource enthält, und gibt das zugeordnete Metadatentoken zurück.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT DefineManifestResource (  
    [in] LPCWSTR                szName,   
    [in] mdToken                tkImplementation,   
    [in] DWORD                  dwOffset,   
    [in] DWORD                  dwResourceFlags,  
    [out] mdManifestResource    *pmdmr  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `szName`  
 [in] Der Name der Ressource.  
  
 `tkImplementation`  
 [in] Ein Metadatentoken des Typs `mdtFile` oder `mdtAssemblyRef` , der der Ressourcenanbieter zugeordnet. Ein NULL-Wert gibt an, dass die Datei, in der die Metadaten eingebettet ist, der Ressourcenanbieter ist.  
  
 `dwOffset`  
 [in] Der Offset auf den Anfang der Ressource in der Datei. Für Ressourcen in eigenständigen Dateien wird dies immer 0 (null) sein. Wenn die Ressource in einer PE (portable ausführbare) Datei eingebettet ist, ist dies ein Offset der Ressource-BLOB, das an die in der Headerdatei cor.h angegebenen Position beginnt.  
  
 `dwResourceFlags`  
 [in] Eine bitweise Kombination der Flagwerte, die eigenschafteneinstellungen für die in der Ressourcendefinition angeben.  
  
 `pmdmr`  
 [out] Ein Zeiger auf die zurückgegebenen Metadaten-Token.  
  
## <a name="remarks"></a>Hinweise  
 Eine `ManifestResource` Metadatenstruktur muss definiert werden, für jede Ressource, die in der Assembly aneinander gehängt Dateien implementiert wird.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattform:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** Cor.h  
  
 **Bibliothek:** als Ressource in MsCorEE.dll verwendet  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [IMetaDataAssemblyEmit-Schnittstelle](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
