---
title: 'Gewusst wie: Wiederverwenden einer Verbindung zwischen einem ADO.NET-Befehl und einem "DataContext"'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
ms.assetid: 7e26c7eb-c18a-43b5-a8f0-28fd8b04b0f0
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: 483a97817162140af61df6a58c3e9ab003235c74
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-reuse-a-connection-between-an-adonet-command-and-a-datacontext"></a>Gewusst wie: Wiederverwenden einer Verbindung zwischen einem ADO.NET-Befehl und einem "DataContext"
Da [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] ist ein Teil der [!INCLUDE[vstecado](../../../../../../includes/vstecado-md.md)] Technologiefamilie und basiert auf Dienste von [!INCLUDE[vstecado](../../../../../../includes/vstecado-md.md)], können Sie eine Verbindung zwischen Wiederverwenden einer [!INCLUDE[vstecado](../../../../../../includes/vstecado-md.md)] Befehl und einem <xref:System.Data.Linq.DataContext>.  
  
## <a name="example"></a>Beispiel  
 Im folgenden Beispiel wird gezeigt, wie die gleiche Verbindung zwischen einem [!INCLUDE[vstecado](../../../../../../includes/vstecado-md.md)]-Befehl und dem <xref:System.Data.Linq.DataContext> wiederverwendet wird.  
  
 [!code-csharp[DLinqCommunicatingWithDatabase#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCommunicatingWithDatabase/cs/Program.cs#4)]
 [!code-vb[DLinqCommunicatingWithDatabase#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCommunicatingWithDatabase/vb/Module1.vb#4)]  
  
## <a name="see-also"></a>Siehe auch  
 [Hintergrundinformationen](../../../../../../docs/framework/data/adonet/sql/linq/background-information.md)  
 [ADO.NET und LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/ado-net-and-linq-to-sql.md)  
 [Bei der Kommunikation mit der Datenbank](../../../../../../docs/framework/data/adonet/sql/linq/communicating-with-the-database.md)
