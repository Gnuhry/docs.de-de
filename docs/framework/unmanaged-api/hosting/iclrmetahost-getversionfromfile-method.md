---
title: ICLRMetaHost::GetVersionFromFile-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRMetaHost.GetVersionFromFile
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRMetaHost::GetVersionFromFile
helpviewer_keywords:
- ICLRMetaHost::GetVersionFromFile method [.NET Framework hosting]
- GetVersionFromFile method [.NET Framework hosting]
ms.assetid: 55bb3eb4-f665-42fc-973c-465567570e82
topic_type: apiref
caps.latest.revision: "20"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 90fcf5ca8306c4e91ff6b96bac36ad2639d81d5d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="iclrmetahostgetversionfromfile-method"></a>ICLRMetaHost::GetVersionFromFile-Methode
Ruft eine Assembly .NET Framework Kompilierung Originalversion (in den Metadaten gespeichert), bei Angabe des Dateipfads ab. Diese Methode hat Vorrang vor den [GetFileVersion](../../../../docs/framework/unmanaged-api/hosting/getfileversion-function.md) Funktion.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetVersionFromFile (  
    [in] LPCWSTR pwzFilePath,  
    [out, size_is(*pcchBuffer)] LPWSTR pwzBuffer,  
    [in, out] DWORD *pcchBuffer);  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 `pwzFilePath`  
 [in] Der vollständige Pfad der Assemblydatei.  
  
 `pwzbuffer`  
 [out] Version von .NET Framework Kompilierung gespeichert, die in den Metadaten, im Format "V*ein*. *B*[. *X*] ". *Ein*, *B*, und *X* sind Dezimalzahlen, die die Hauptversion, die Nebenversion und die Nummer des Builds entsprechen. Die Länge dieser Zeichenfolge ist auf MAX_PATH beschränkt.  
  
> [!NOTE]
>  Diese Ausgabe entspricht den Verzeichnisnamen für die .NET Framework-Version an, wie er unter C:\Windows\Microsoft.NET\Framework angezeigt wird.  
  
 Beispielwerte sind "Version 1.0.3705", "v1.1.4322", "v2.0.50727" und "v4. 0. *X*", wobei *X* richtet sich nach die Buildnummer installiert. Beachten Sie, dass das Präfix "V" erforderlich ist.  
  
 `pcchBuffer`  
 [in, out] Die Größe des `pwzbuffer` um Pufferüberläufe zu vermeiden.  
  
## <a name="return-value"></a>Rückgabewert  
 Diese Methode gibt die folgenden spezifischen HRESULTs sowie HRESULT-Fehler zurück, die Methodenfehler anzeigen.  
  
|HRESULT|Beschreibung|  
|-------------|-----------------|  
|S_OK|Die Methode wurde erfolgreich abgeschlossen.|  
|E_POINTER|`pwzbuffer` oder `pcchBuffer` ist NULL.|  
|HRESULT_FROM_WIN32(ERROR_INSUFFICIENT_BUFFER)|Der Puffer ist zu klein.|  
  
## <a name="requirements"></a>Anforderungen  
 **Plattformen:** finden Sie unter [Systemanforderungen](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Header:** MetaHost.h  
  
 **Bibliothek:** als Ressource in MSCorEE.dll enthalten  
  
 **.NET Framework-Versionen:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Siehe auch  
 [ICLRMetaHost-Schnittstelle](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md)  
 [Hosting](../../../../docs/framework/unmanaged-api/hosting/index.md)
