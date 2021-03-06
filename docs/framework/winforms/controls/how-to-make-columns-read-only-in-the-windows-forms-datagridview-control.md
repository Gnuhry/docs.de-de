---
title: "Gewusst wie: Zuweisen von schreibgeschützten Spalten im DataGridView-Steuerelement in Windows Forms"
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
- data grids [Windows Forms], read-only columns
- DataGridView control [Windows Forms], read-only columns
ms.assetid: 2bb73ebb-1a55-4362-9fda-e50574c087d5
caps.latest.revision: "18"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: f3fb80b5baeafff53781cb1ff430ad05dd93f2ad
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-make-columns-read-only-in-the-windows-forms-datagridview-control"></a>Gewusst wie: Zuweisen von schreibgeschützten Spalten im DataGridView-Steuerelement in Windows Forms
Nicht alle Daten sind zum Bearbeiten bestimmt. Im <xref:System.Windows.Forms.DataGridView>-Steuerelement bestimmt der Wert der Spalteneigenschaft <xref:System.Windows.Forms.DataGridViewColumn.ReadOnly%2A>, ob Benutzer Zellen in dieser Spalte bearbeiten können. Informationen dazu, wie Sie das Steuerelement vollständig schreibgeschützt machen, finden Sie unter [wie: verhindern Hinzufügens und Löschens im DataGridView-Steuerelement von Windows Forms](../../../../docs/framework/winforms/controls/prevent-row-addition-and-deletion-datagridview.md).  
  
 Visual Studio bietet Unterstützung für diese Aufgabe.  Siehe auch [Vorgehensweise: Stellen Spalten schreibgeschützter in der Windows Forms DataGridView-Steuerelement mithilfe des Designers](http://msdn.microsoft.com/library/xd4k3c7e\(v=vs.110\)).  
  
### <a name="to-make-a-column-read-only-programmatically"></a>So weisen Sie eine schreibgeschützte Spalte programmgesteuert zu  
  
-   Legen Sie die <xref:System.Windows.Forms.DataGridViewColumn.ReadOnly%2A?displayProperty=nameWithType>-Eigenschaft auf `true` fest.  
  
     [!code-csharp[System.Windows.Forms.DataGridViewMisc#064](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/CS/datagridviewmisc.cs#064)]
     [!code-vb[System.Windows.Forms.DataGridViewMisc#064](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DataGridViewMisc/VB/datagridviewmisc.vb#064)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Für dieses Beispiel benötigen Sie Folgendes:  
  
-   Ein <xref:System.Windows.Forms.DataGridView>-Steuerelement mit dem Namen `dataGridView1` mit einer Spalte namens `CompanyName`.  
  
-   Verweise auf die <xref:System?displayProperty=nameWithType>-Assembly und die <xref:System.Windows.Forms?displayProperty=nameWithType>-Assembly.  
  
## <a name="see-also"></a>Siehe auch  
 <xref:System.Windows.Forms.DataGridView>  
 <xref:System.Windows.Forms.DataGridView.Columns%2A?displayProperty=nameWithType>  
 <xref:System.Windows.Forms.DataGridViewColumn.ReadOnly%2A?displayProperty=nameWithType>  
 [Grundlegende Spalten-, Zeilen- und Zellfunktionen im DataGridView-Steuerelement in Windows Forms](../../../../docs/framework/winforms/controls/basic-column-row-and-cell-features-wf-datagridview-control.md)  
 [Gewusst wie: Verhindern, das Zeilen im DataGridView-Steuerelement in Windows Forms hinzugefügt und gelöscht werden](../../../../docs/framework/winforms/controls/prevent-row-addition-and-deletion-datagridview.md)
