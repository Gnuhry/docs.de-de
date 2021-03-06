---
title: ISymUnmanagedDocument::GetURL-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedDocument.GetURL
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedDocument::GetURL
helpviewer_keywords:
- GetURL method [.NET Framework debugging]
- ISymUnmanagedDocument::GetURL method [.NET Framework debugging]
ms.assetid: 60600178-c2b5-4cab-b3a5-f0f61acebaf1
topic_type: apiref
caps.latest.revision: "9"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 591383fee2f9b22a00956193555c719e72d722bb
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanageddocumentgeturl-method"></a>ISymUnmanagedDocument::GetURL-Methode
Gibt die URL (uniform Resource Locator) für dieses Dokument zurück.  
  
## <a name="syntax"></a>Syntax  
  
```  
HRESULT GetURL(  
    [in]  ULONG32  cchUrl,  
    [out] ULONG32  *pcchUrl,  
    [out, size_is(cchUrl), length_is(*pcchUrl)] WCHAR szUrl[]);  
```  
  
#### <a name="parameters"></a>Parameter  
 `cchUrl`  
 [in] Die Größe des `szURL`-Puffers in Zeichen.  
  
 `pcchUrl`  
 [out] Ein Zeiger auf eine Variable, die Größe der URL, einschließlich der null-Terminierung empfängt.  
  
 `szUrl`  
 [out] Der Puffer, der die URL.  
  
## <a name="return-value"></a>Rückgabewert  
 S_OK, wenn die Methode erfolgreich ist; andernfalls ein Fehlercode.  
  
## <a name="see-also"></a>Siehe auch  
 [ISymUnmanagedDocument-Schnittstelle](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanageddocument-interface.md)
