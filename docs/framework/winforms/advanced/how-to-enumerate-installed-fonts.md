---
title: 'Gewusst wie: Auflisten installierter Schriftarten'
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
- fonts [Windows Forms], enumerating installed
- examples [Windows Forms], fonts
ms.assetid: 26d74ef5-0f39-4eeb-8d20-00e66e014abe
caps.latest.revision: "16"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: bca536ed2f3e493e8d50fe8f1a0115327f1d8720
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/22/2017
---
# <a name="how-to-enumerate-installed-fonts"></a>Gewusst wie: Auflisten installierter Schriftarten
Die <xref:System.Drawing.Text.InstalledFontCollection> Klasse erbt von der <xref:System.Drawing.Text.FontCollection> abstrakte Basisklasse. Sie können eine <xref:System.Drawing.Text.InstalledFontCollection> auf dem Computer installierten Schriftarten aufzulistende Objekt. Die <xref:System.Drawing.Text.FontCollection.Families%2A> Eigenschaft ein <xref:System.Drawing.Text.InstalledFontCollection> Objekt ist ein Array von <xref:System.Drawing.FontFamily> Objekte.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel listet die Namen aller Schriftartfamilien, die auf dem Computer installiert. Der Code Ruft die <xref:System.Drawing.FontFamily.Name%2A> -Eigenschaft jedes <xref:System.Drawing.FontFamily> Objekt in das zurückgegebene Array die <xref:System.Drawing.Text.FontCollection.Families%2A> Eigenschaft. Wie die Namen der Produktfamilie abgerufen werden, werden sie eine durch Trennzeichen getrennte Liste verkettet. Die <xref:System.Drawing.Graphics.DrawString%2A> Methode der <xref:System.Drawing.Graphics> Klasse zeichnet eine durch Trennzeichen getrennte Liste die in einem Rechteck.  
  
 Wenn Sie den Beispielcode ausführen, wird die Ausgabe, die in der folgenden Abbildung dargestellten ähnlich sein.  
  
 ![Installierte Schriftarten](../../../../docs/framework/winforms/advanced/media/csfontstext6.png "csfontstext6")  
  
 [!code-csharp[System.Drawing.FontsAndText#11](../../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.FontsAndText/CS/Class1.cs#11)]
 [!code-vb[System.Drawing.FontsAndText#11](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.FontsAndText/VB/Class1.vb#11)]  
  
## <a name="compiling-the-code"></a>Kompilieren des Codes  
 Das obige Beispiel ist für die Verwendung in Windows Forms konzipiert und erfordert die <xref:System.Windows.Forms.PaintEventArgs> `e`-Klasse, die ein Parameter von <xref:System.Windows.Forms.PaintEventHandler> ist. Darüber hinaus sollten Sie importieren die <xref:System.Drawing.Text> Namespace.  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von Schriftarten und Text](../../../../docs/framework/winforms/advanced/using-fonts-and-text.md)
