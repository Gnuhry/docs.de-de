---
title: GetPublicKeyToken-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IALink2.GetPublicKeyToken
api_location: alink.dll
api_type: COM
f1_keywords: GetPublicKeyToken
helpviewer_keywords: GetPublicKeyToken method
ms.assetid: 4a16374c-94b0-47b0-9fed-88c2b0cdccd4
topic_type: apiref
caps.latest.revision: "6"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 5f41c8088f095802cf35239afab279d6324adb55
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="getpublickeytoken-method"></a>GetPublicKeyToken-Methode
Ruft das Token des öffentlichen Schlüssels für eine angegebene Schlüsseldatei oder eines Schlüsselcontainers ab.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetPublicKeyToken(  
    LPCWSTR pszKeyFile,  
    LPCWSTR pszKeyContainer,  
    void* pvPublicKeyToken,  
    DWORD* pcbPublicKeyToken  
) PURE;  
```  
  
#### <a name="parameters"></a>Parameter  
 `pszKeyFile`  
 Der Dateiname des Schlüssels.  
  
 `pszKeyContainer`  
 Der Name des Schlüsselcontainers.  
  
 `pvPublicKeyToken`  
 Adresse des Standorts Schlüsseltoken gespeichert werden soll.  
  
 `pcbPublicKeyToken`  
 Gibt die Größe in Bytes, des Puffers erkennbar `pvPublicKeyToken`. Enthält bei der Rückgabe die tatsächliche Anzahl von Bytes verwendet.  
  
## <a name="return-value"></a>Rückgabewert  
 Gibt S_OK zurück, wenn die Methode erfolgreich ausgeführt wird.  
  
## <a name="requirements"></a>Anforderungen  
 Erfordert alink.h.  
  
## <a name="see-also"></a>Siehe auch  
 [IALink2-Schnittstelle](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [IALink-Schnittstelle](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [ALink-API](../../../../docs/framework/unmanaged-api/alink/index.md)
