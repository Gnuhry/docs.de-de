---
title: Erstellen einer Klasse zum Halten von DLL-Funktionen
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- COM interop, DLL functions
- unmanaged functions
- COM interop, platform invoke
- interoperation with unmanaged code, DLL functions
- interoperation with unmanaged code, platform invoke
- platform invoke, creating class for functions
- DLL functions
ms.assetid: e08e4c34-0223-45f7-aa55-a3d8dd979b0f
caps.latest.revision: "6"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: ac3c3542e46168f5903ff0425740a29f16253733
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="creating-a-class-to-hold-dll-functions"></a>Erstellen einer Klasse zum Halten von DLL-Funktionen
Das Umschließen einer häufig verwendeten DLL-Funktion in einer verwalteten Klasse ist als effektiver Ansatz zu verstehen, Plattformfunktionen zu kapseln. Obwohl es nicht in jedem Fall erforderlich ist, können Sie mithilfe von Klassenwrappern DLL-Funktionen mit weniger Aufwand und geringerer Fehleranfälligkeit definieren. Wenn Sie in Visual Basic oder C# programmieren, müssen Sie die DLL-Funktionen innerhalb einer Klasse oder eines Visual Basic-Moduls deklarieren.  
  
 Innerhalb einer Klasse definieren Sie eine statische Methode für jede DLL-Funktion, die Sie aufrufen möchten. Die Definition kann zusätzliche Informationen wie den Zeichensatz oder die Aufrufkonvention, die bei der Übergabe von Methodenargumenten verwendet wird, enthalten; werden diese Informationen weggelassen, werden die Standardeinstellungen verwendet. Eine vollständige Liste der Deklarationsoptionen und deren Standardeinstellungen finden Sie unter [Erstellen von Prototypen in verwaltetem Code](../../../docs/framework/interop/creating-prototypes-in-managed-code.md).  
  
 Sobald eine Funktion umschlossen ist, können Sie Methoden für die Funktion wie für jede andere statische Funktion aufrufen. Der Plattformaufruf behandelt automatisch die zugrunde liegenden exportierten Funktionen.  
  
 Beim Entwurf einer verwalteten Klasse für Plattformaufruf, beachten Sie die Beziehungen zwischen Klassen und DLL-Funktionen. Sie haben unter anderem folgende Möglichkeiten:  
  
-   Deklarieren von DLL-Funktionen innerhalb einer vorhandenen Klasse.  
  
-   Erstellen Sie eine einzelne Klasse für jede DLL-Funktion, indem Funktionen isoliert und leicht auffindbar bleiben.  
  
-   Erstellen Sie eine Klasse für eine Gruppe von verwandten DLL-Funktionen, um logische Gruppierungen zu bilden und den Verwaltungsaufwand zu reduzieren.  
  
 Sie können die Klasse und ihre Methoden beliebig benennen. Beispiele für die Vorgehensweise beim Erstellen von .NET-basierten Deklarationen, die mit dem Plattformaufruf verwendet werden können, finden Sie unter [Marshaling Data with Platform Invoke (Marshallen von Daten mit Plattformaufruf)](../../../docs/framework/interop/marshaling-data-with-platform-invoke.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden nicht verwalteter DLL-Funktionen](../../../docs/framework/interop/consuming-unmanaged-dll-functions.md)  
 [Identifizieren von Funktionen in DLLs](../../../docs/framework/interop/identifying-functions-in-dlls.md)  
 [Creating Prototypes in Managed Code (Erstellen von Prototypen in verwaltetem Code)](../../../docs/framework/interop/creating-prototypes-in-managed-code.md)  
 [Calling a DLL Function (Aufrufen einer DLL-Funktion)](../../../docs/framework/interop/calling-a-dll-function.md)
