---
title: "Gewusst wie: Hinzufügen einer ungebundenen Spalte zu einem datengebundenen DataGridView-Steuerelement in Windows Forms"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- columns [Windows Forms], unbound data
- data grids [Windows Forms], adding unbound columns
- DataGridView control [Windows Forms], unbound data
ms.assetid: f7bdc4d8-ba8e-421b-ad62-82d936f01372
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 2cd6a1494a98d912469f7e45c7751a0a9741ff17
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-add-an-unbound-column-to-a-data-bound-windows-forms-datagridview-control"></a>Gewusst wie: Hinzufügen einer ungebundenen Spalte zu einem datengebundenen DataGridView-Steuerelement in Windows Forms
Die Daten, die Sie im <xref:System.Windows.Forms.DataGridView>-Steuerelement anzeigen, stammen normalerweise aus einer Datenquelle einer bestimmten Art, aber möglicherweise möchten Sie eine Spalte mit Daten anzeigen, die nicht aus der Datenquelle stammen. Diese Art von Spalte wird als ungebundene Spalte bezeichnet. Ungebundene Spalten können viele Formen annehmen. Häufig werden sie verwendet, um Zugriff auf die Details einer Datenzeile bereitzustellen.  
  
 Im folgenden Codebeispiel wird veranschaulicht, wie zum Erstellen einer nicht gebundenen Spalte des **Details** Schaltflächen für die Anzeige einer untergeordneten Tabelle im Zusammenhang mit einer bestimmten Zeile in einer übergeordneten Tabelle, wenn Sie eine Master/Detail-Szenario implementieren. Um auf Klicks auf Schaltflächen zu reagieren, implementieren Sie einen <xref:System.Windows.Forms.DataGridView.CellClick?displayProperty=nameWithType>-Ereignishandler, der ein Formular mit der untergeordneten Tabelle anzeigt.  
  
 Visual Studio bietet Unterstützung für diese Aufgabe.  Siehe auch [wie: Hinzufügen und Entfernen von Spalten in der Windows Forms DataGridView-Steuerelement mithilfe des Designers](http://msdn.microsoft.com/library/dyyesckz\(v=vs.110\))  
  
## <a name="example"></a>Beispiel  
 [!code-csharp[System.Windows.Forms.DataGridViewMisc#010](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#010)]
 [!code-vb[System.Windows.Forms.DataGridViewMisc#010](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#010)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Für dieses Beispiel benötigen Sie Folgendes:  
  
-   Ein <xref:System.Windows.Forms.DataGridView>-Steuerelement namens `dataGridView1`.  
  
-   Verweise auf die <xref:System?displayProperty=nameWithType>-Assembly und die <xref:System.Windows.Forms?displayProperty=nameWithType>-Assembly.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Forms.DataGridView>  
 [Anzeigen von Daten im DataGridView-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/displaying-data-in-the-windows-forms-datagridview-control.md)  
 [Datenanzeigemodi im DataGridView-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/data-display-modes-in-the-windows-forms-datagridview-control.md)
