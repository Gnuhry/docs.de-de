---
title: "Verfügbarmachen von COM-Komponenten für .NET Framework"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- exposing COM components to .NET Framework
- interoperation with unmanaged code, exposing COM components
- COM interop, exposing COM components
ms.assetid: e78b14f1-e487-43cd-9c6d-1a07483f1730
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 26efd43a05252e657626063d7dd04b1020dace18
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="exposing-com-components-to-the-net-framework"></a>Verfügbarmachen von COM-Komponenten für .NET Framework
In diesem Abschnitt wird der Prozess zusammengefasst, der benötigt wird, um eine vorhandene COM-Komponente für verwalteten Code verfügbar zu machen. Details zum Schreiben von COM-Servern, die eng in .NET Framework eingebunden sind, finden Sie unter [Entwurfsüberlegungen für die Interoperation](http://msdn.microsoft.com/en-us/b59637f6-fe35-40d6-ae72-901e7a707689).  
  
 Vorhandene COM-Komponenten sind wertvolle Ressourcen in verwaltetem Code als Geschäftsanwendungen mittlerer Ebene oder als isolierte Funktion. Eine ideale Komponente verfügt über eine primäre Interop-Assembly, und entspricht weitgehend den Programmierstandards von COM.  
  
#### <a name="to-expose-com-components-to-the-net-framework"></a>Verfügbarmachen von COM-Komponenten für .NET Framework  
  
1.  [Import a type library as an assembly (Importieren einer Typbibliothek als Assembly)](../../../docs/framework/interop/importing-a-type-library-as-an-assembly.md).  
  
     Die Common Language Runtime erfordert Metadaten für alle Typen, einschließlich COM-Typen. Es gibt mehrere Möglichkeiten zum Abrufen einer Assembly mit COM-Typen, die als Metadaten importiert werden.  
  
2.  [Create COM types in managed Code (Erstellen von COM-Typen in verwaltetem Code)](http://msdn.microsoft.com/en-us/1a95a8ca-c8b8-4464-90b0-5ee1a1135b66).  
  
     Sie können für das COM-Objekt auf die gleiche Weise COM-Typen überprüfen, Instanzen aktivieren und Methoden aufrufen, wie für einen verwalteten Typ.  
  
3.  [Kompilieren Sie ein Interop-Projekt](../../../docs/framework/interop/compiling-an-interop-project.md).  
  
     Die [!INCLUDE[winsdklong](../../../includes/winsdklong-md.md)] bietet Compiler für verschiedene mit der Common Language Specification (CLS) kompatible Sprachen an, einschließlich [!INCLUDE[vbprvblong](../../../includes/vbprvblong-md.md)], C# und C++.  
  
4.  [Geben Sie eine Interop-Anwendung weiter](../../../docs/framework/interop/deploying-an-interop-application.md).  
  
     Interop-Anwendungen werden am besten als signierte Assemblys [mit starkem Namen](../../../docs/framework/app-domains/strong-named-assemblies.md) im globalen Assemblycache bereitgestellt.  
  
## <a name="see-also"></a>Siehe auch  
 [Interoperabilität mit nicht verwaltetem Code](../../../docs/framework/interop/index.md)  
 [Entwurfsüberlegungen für die Interoperation](http://msdn.microsoft.com/en-us/b59637f6-fe35-40d6-ae72-901e7a707689)  
 [COM-Interop-Beispiel: .NET-Client und COM-Server](../../../docs/framework/interop/com-interop-sample-net-client-and-com-server.md)  
 [Sprachunabhängigkeit und sprachunabhängige Komponenten](../../../docs/standard/language-independence-and-language-independent-components.md)  
 [Gacutil.exe (Global Assembly Cache-Tool)](../../../docs/framework/tools/gacutil-exe-gac-tool.md)
