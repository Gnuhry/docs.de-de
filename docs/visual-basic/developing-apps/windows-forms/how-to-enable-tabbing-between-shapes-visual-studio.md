---
title: 'Gewusst wie: Aktivieren des Wechselns zwischen Formen mit der Tabulatortaste (Visual Studio)'
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Line control [Visual Basic], implementing tabbing
- Shape control [Visual Basic], implementing tabbing
ms.assetid: 09731b34-3900-4fcb-a9df-ce5280328433
caps.latest.revision: "14"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: a39957ffaa67d6abeb6d394ae9826d42ad2230de
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-enable-tabbing-between-shapes-visual-studio"></a>Gewusst wie: Aktivieren des Wechselns zwischen Formen mit der Tabulatortaste (Visual Studio)
Die Linien- und Formsteuerelemente keine `TabStop` oder `TabIndex` Eigenschaften, aber Sie können weiterhin aktivieren Tabulator-zwischen ihnen. Im folgenden Beispiel wird die STRG-Taste und die TAB-Taste drücken zwischen Formen Registerkarte; zwischen den Schaltflächen Registerkarte wird nur die TAB-Taste drücken.  
  
> [!NOTE]
>  Auf Ihrem Computer werden möglicherweise andere Namen oder Speicherorte für die Benutzeroberflächenelemente von Visual Studio angezeigt als die in den folgenden Anweisungen aufgeführten. Diese Elemente sind von der jeweiligen Visual Studio-Version und den verwendeten Einstellungen abhängig. Weitere Informationen finden Sie unter [Anpassen der Entwicklungseinstellungen in Visual Studio](http://msdn.microsoft.com/en-us/22c4debb-4e31-47a8-8f19-16f328d7dcd3).  
  
## <a name="to-enable-tabbing-among-shapes"></a>So aktivieren Sie die TAB-Taste zwischen Formen  
  
1.  Ziehen Sie drei <xref:Microsoft.VisualBasic.PowerPacks.RectangleShape> Steuerelemente und zwei <xref:System.Windows.Forms.Button> -Steuerelemente aus der **Toolbox** zu einem Formular.  
  
2.  In der **Code-Editor**, Hinzufügen einer `Imports` oder `using` -Anweisung am Anfang des Moduls:  
  
```vb  
Imports Microsoft.VisualBasic.PowerPacks  
```  
  
```csharp  
using Microsoft.VisualBasic.PowerPacks;  
```  

3.  Fügen Sie den folgenden Code in eine Ereignisprozedur:  
  
[!code-csharp[VbPowerPacksTabbing#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/how-to-enable-tabbing-between-shapes-visual-studio_1.cs)]
[!code-vb[VbPowerPacksTabbing#1](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/how-to-enable-tabbing-between-shapes-visual-studio_1.vb)]  
  
4.  Fügen Sie den folgenden Code in die `Button1_PreviewKeyDown` Ereignisprozedur:  
  
[!code-csharp[VbPowerPacksTabbing#2](../../../visual-basic/developing-apps/windows-forms/codesnippet/CSharp/how-to-enable-tabbing-between-shapes-visual-studio_2.cs)]
[!code-vb[VbPowerPacksTabbing#2](../../../visual-basic/developing-apps/windows-forms/codesnippet/VisualBasic/how-to-enable-tabbing-between-shapes-visual-studio_2.vb)]  
  
## <a name="see-also"></a>Siehe auch  
 [Gewusst wie: Zeichnen von Formen mit dem OvalShape-Steuerelement und dem RectangleShape-Steuerelement](../../../visual-basic/developing-apps/windows-forms/how-to-draw-shapes-with-the-ovalshape-and-rectangleshape-controls.md)  
 [Gewusst wie: Zeichnen von Linien mit dem LineShape-Steuerelement](../../../visual-basic/developing-apps/windows-forms/how-to-draw-lines-with-the-lineshape-control-visual-studio.md)  
 [Einführung in das Line-Steuerelement und das Shape-Steuerelement](../../../visual-basic/developing-apps/windows-forms/introduction-to-the-line-and-shape-controls-visual-studio.md)
