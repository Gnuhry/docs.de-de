---
title: ICLRStrongName::StrongNameSignatureGeneration-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRStrongName.StrongNameSignatureGeneration
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRStrongName::StrongNameSignatureGeneration
helpviewer_keywords:
- StrongNameSignatureGeneration method, ICLRStrongName interface [.NET Framework hosting]
- ICLRStrongName::StrongNameSignatureGeneration method [.NET Framework hosting]
ms.assetid: 4cdb1284-947a-4ed4-94c1-c5ff5cdfce56
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 739dc0b08955b774f7fa15c3c346ec889f717dd2
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="iclrstrongnamestrongnamesignaturegeneration-method"></a>ICLRStrongName::StrongNameSignatureGeneration-Methode
Generiert eine starke Namenssignatur für die angegebene Assembly an.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT StrongNameSignatureGeneration (   
    [in]  LPCWSTR   wszFilePath,  
    [in]  LPCWSTR   wszKeyContainer,  
    [in]  BYTE      *pbKeyBlob,  
    [in]  ULONG     cbKeyBlob,  
    [out] BYTE      **ppbSignatureBlob,  
    [out] ULONG     *pcbSignatureBlob  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `wszFilePath`  
 [in] Der Pfad zur Datei, die das Manifest der Assembly enthält, für die Signatur des starken Namens generiert wird.  
  
 `wszKeyContainer`  
 [in] Der Name des Schlüsselcontainers an, die das öffentlich/privat-Schlüsselpaar enthält.  
  
 Wenn `pbKeyBlob` ist null, `wszKeyContainer` müssen einen gültigen Container innerhalb der Kryptografiedienstanbieter (CSP) angeben. In diesem Fall wird das Schlüsselpaar in dem Container gespeichert verwendet, um die Datei zu signieren.  
  
 Wenn `pbKeyBlob` ist ungleich null, das Schlüsselpaar wird davon ausgegangen, dass im Schlüssel binary large Object (BLOB) enthalten sein soll.  
  
 Die Schlüssel müssen 1024-Bit-Rivest-Shamir-Adleman (RSA) Signaturschlüssel sein. Zu diesem Zeitpunkt werden keine anderen Arten von Schlüsseln unterstützt.  
  
 `pbKeyBlob`  
 [in] Ein Zeiger auf das öffentlich/privat-Schlüsselpaar. Dieses Paar weist das Format, das erstellt wird, durch die Win32- `CryptExportKey` Funktion. Wenn `pbKeyBlob` null ist, die vom angegebenen Schlüsselcontainer `wszKeyContainer` wird davon ausgegangen, dass das Schlüsselpaar enthält.  
  
 `cbKeyBlob`  
 [in] Die Größe in Bytes, der `pbKeyBlob`.  
  
 `ppbSignatureBlob`  
 [out] Ein Zeiger auf den Speicherort, an dem die common Language Runtime die Signatur zurückgibt. Wenn `ppbSignatureBlob` ist null, die Common Language Runtime speichert-Signatur in der Datei gemäß `wszFilePath`.  
  
 Wenn `ppbSignatureBlob` ist ungleich null, die common Language Runtime reserviert Speicherplatz in dem die Signatur zurückgegeben. Der Aufrufer muss diesen Speicherplatz freigeben, mithilfe der [ICLRStrongName:: StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) Methode.  
  
 `pcbSignatureBlob`  
 [out] Die Größe in Bytes, der zurückgegebenen Signatur.  
  
## <a name="return-value"></a>Rückgabewert  
 `S_OK`Wenn die Methode erfolgreich abgeschlossen. andernfalls ein HRESULT-Wert, der Fehler weist darauf hin (finden Sie unter [häufig auftretende HRESULT-Werte](http://go.microsoft.com/fwlink/?LinkId=213878) eine Liste).  
  
## <a name="remarks"></a>Hinweise  
 Geben Sie null für `wszFilePath` auf die Größe der Signatur zu berechnen, ohne die Signatur zu erstellen.  
  
 Die Signatur kann entweder direkt in der Datei gespeichert oder an den Aufrufer zurückgegeben.  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MetaHost.h  
  
 **Bibliothek:** als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [StrongNameSignatureGenerationEx-Methode](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamesignaturegenerationex-method.md)  
 [ICLRStrongName-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
