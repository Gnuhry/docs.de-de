---
title: ISymUnmanagedWriter::UsingNamespace-Methode
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ISymUnmanagedWriter.UsingNamespace
api_location: diasymreader.dll
api_type: COM
f1_keywords: ISymUnmanagedWriter::UsingNamespace
helpviewer_keywords:
- UsingNamespace method [.NET Framework debugging]
- ISymUnmanagedWriter::UsingNamespace method [.NET Framework debugging]
ms.assetid: 8d746e0a-d158-4983-88da-db0a0856bc0b
topic_type: apiref
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: b9bfd5ca0c22a9b4da1acb1f93b29150beba865a
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="isymunmanagedwriterusingnamespace-method"></a><span data-ttu-id="c31a7-102">ISymUnmanagedWriter::UsingNamespace-Methode</span><span class="sxs-lookup"><span data-stu-id="c31a7-102">ISymUnmanagedWriter::UsingNamespace Method</span></span>
<span data-ttu-id="c31a7-103">Gibt an, dass es sich bei der angegebenen Namen für den vollqualifizierten Namespace im geöffneten lexikalischen Gültigkeitsbereich verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="c31a7-103">Specifies that the given fully qualified namespace name is being used within the currently open lexical scope.</span></span> <span data-ttu-id="c31a7-104">Der Namespace wird in allen Bereichen verwendet werden, die von den aktuell geöffneten Bereich erben.</span><span class="sxs-lookup"><span data-stu-id="c31a7-104">The namespace will be used within all scopes that inherit from the currently open scope.</span></span> <span data-ttu-id="c31a7-105">Schließen des aktuellen Bereichs wird auch die Verwendung des Namespaces beendet.</span><span class="sxs-lookup"><span data-stu-id="c31a7-105">Closing the current scope will also stop the use of the namespace.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c31a7-106">Syntax</span><span class="sxs-lookup"><span data-stu-id="c31a7-106">Syntax</span></span>  
  
```  
HRESULT UsingNamespace(  
    [in] const WCHAR *fullName);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c31a7-107">Parameter</span><span class="sxs-lookup"><span data-stu-id="c31a7-107">Parameters</span></span>  
 `fullName`  
 <span data-ttu-id="c31a7-108">[in] Ein Zeiger auf den vollqualifizierten Namen des Namespaces.</span><span class="sxs-lookup"><span data-stu-id="c31a7-108">[in] A pointer to the fully qualified name of the namespace.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c31a7-109">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="c31a7-109">Return Value</span></span>  
 <span data-ttu-id="c31a7-110">S_OK, wenn die Methode erfolgreich ist; andernfalls E_FAIL oder einen anderen Fehlercode.</span><span class="sxs-lookup"><span data-stu-id="c31a7-110">S_OK if the method succeeds; otherwise, E_FAIL or some other error code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c31a7-111">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="c31a7-111">Requirements</span></span>  
 <span data-ttu-id="c31a7-112">**Header:** CorSym.idl, CorSym.h</span><span class="sxs-lookup"><span data-stu-id="c31a7-112">**Header:** CorSym.idl, CorSym.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c31a7-113">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c31a7-113">See Also</span></span>  
 [<span data-ttu-id="c31a7-114">ISymUnmanagedWriter-Schnittstelle</span><span class="sxs-lookup"><span data-stu-id="c31a7-114">ISymUnmanagedWriter Interface</span></span>](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedwriter-interface.md)