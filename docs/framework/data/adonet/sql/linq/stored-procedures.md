---
title: Gespeicherte Prozeduren
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 4d23dd7a-a85f-44ff-a717-af7d0950c0fc
caps.latest.revision: "3"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 1cf8d155dd04cd4f7b3f860186428c14ce4e462e
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="stored-procedures"></a>Gespeicherte Prozeduren
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]verwendet Methoden in Ihrem Objektmodell, um gespeicherte Prozeduren in der Datenbank darzustellen. Sie kennzeichnen Methoden als gespeicherte Prozeduren, indem Sie das <xref:System.Data.Linq.Mapping.FunctionAttribute>-Attribut und bei Bedarf das <xref:System.Data.Linq.Mapping.ParameterAttribute>-Attribut anwenden. Weitere Informationen finden Sie unter [das LINQ to SQL-Objektmodell](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md).  
  
 Entwickler mit [!INCLUDE[vs_current_short](../../../../../../includes/vs-current-short-md.md)] in der Regel die [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] gespeicherte Prozeduren zuordnen. Dieser Abschnitt erläutert das Bilden und Aufrufen dieser Methoden in Ihrer Anwendung, wenn Sie den Code selbst schreiben.  
  
## <a name="in-this-section"></a>In diesem Abschnitt  
 [Vorgehensweise: Zurückgeben von Rowsets](../../../../../../docs/framework/data/adonet/sql/linq/how-to-return-rowsets.md)  
 Beschreibt das Zurückgeben von Datenzeilen und zeigt, wie ein Eingabeparameter verwendet wird.  
  
 [Vorgehensweise: Verwenden von gespeicherten Prozeduren, die Parameter](../../../../../../docs/framework/data/adonet/sql/linq/how-to-use-stored-procedures-that-take-parameters.md)  
 Beschreibt die Verwendung von Eingabe- und Ausgabeparametern.  
  
 [Vorgehensweise: Verwenden von gespeicherten Prozeduren, die mehrere Ergebnisformen zugeordnet](../../../../../../docs/framework/data/adonet/sql/linq/how-to-use-stored-procedures-mapped-for-multiple-result-shapes.md)  
 Beschreibt, wie in der gleichen gespeicherten Prozedur mehrere Formen zurückgegeben werden können.  
  
 [Vorgehensweise: Verwenden von gespeicherten Prozeduren, die sequenziellen Ergebnisformen zugeordnet](../../../../../../docs/framework/data/adonet/sql/linq/how-to-use-stored-procedures-mapped-for-sequential-result-shapes.md)  
 Beschreibt, wie die Unterstützung für mehrere Formen gewährleistet werden kann, wenn die Rückgabesequenz bekannt ist.  
  
 [Anpassen von Operationen durch Verwendung von gespeicherten Prozeduren](../../../../../../docs/framework/data/adonet/sql/linq/customizing-operations-by-using-stored-procedures.md)  
 Beschreibt, wie gespeicherte Prozeduren zur Implementierung von Insert-, Update- und Delete-Operationen verwendet werden.  
  
 [Anpassen von Operationen mit gespeicherten Prozeduren ausschließlich](../../../../../../docs/framework/data/adonet/sql/linq/customizing-operations-by-using-stored-procedures-exclusively.md)  
 Beschreibt, wie ausschließlich gespeicherte Prozeduren zur Implementierung von Insert-, Update- und Delete-Operationen verwendet werden.  
  
## <a name="related-sections"></a>Verwandte Abschnitte  
 [Programmierhandbuch](../../../../../../docs/framework/data/adonet/sql/linq/programming-guide.md)  
 Stellt Informationen zur Erstellung und Nutzung Ihres [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]-Objektmodells bereit.  
  
 [Exemplarische Vorgehensweise: Ausschließliches Verwenden von gespeicherten Prozeduren (Visual Basic)](../../../../../../docs/framework/data/adonet/sql/linq/walkthrough-using-only-stored-procedures-visual-basic.md)  
 Umfasst Prozeduren, die veranschaulichen, wie gespeicherte Prozeduren in Visual Basic verwendet werden.  
  
 [Exemplarische Vorgehensweise: Ausschließliches Verwenden von gespeicherten Prozeduren (c#)](../../../../../../docs/framework/data/adonet/sql/linq/walkthrough-using-only-stored-procedures-csharp.md)  
 Umfasst Prozeduren, die veranschaulichen, wie gespeicherte Prozeduren in C# verwendet werden.
