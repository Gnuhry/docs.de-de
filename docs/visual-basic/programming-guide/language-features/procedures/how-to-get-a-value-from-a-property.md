---
title: 'Gewusst wie: Abrufen eines Werts aus einer Eigenschaft (Visual Basic)'
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- property values [Visual Basic]
- Visual Basic code, procedures
- values [Visual Basic], properties
- Visual Basic code, properties
- properties [Visual Basic], values
ms.assetid: 3954423e-6ab7-4a4c-b55c-a8d27be47891
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 6cde5408ea09398a79a3da01ae9b2d0202c58eaf
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-get-a-value-from-a-property-visual-basic"></a>Gewusst wie: Abrufen eines Werts aus einer Eigenschaft (Visual Basic)
Rufen Sie den Wert einer Eigenschaft den Namen der Eigenschaft in einen Ausdruck einschließen.  
  
 Der Eigenschaft `Get` Prozedur ruft den Wert ab, aber Sie rufen sie nicht explizit nach Namen. Sie können die Eigenschaft verwenden, wie Sie eine Variable verwenden würden. [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)]Ruft die Eigenschaftenprozeduren.  
  
### <a name="to-retrieve-a-value-from-a-property"></a>Zum Abrufen eines Werts aus einer Eigenschaft  
  
1.  Verwenden Sie den Namen der Eigenschaft in einem Ausdruck die gleiche Weise wie ein Variablenname. Sie können eine Eigenschaft an einer beliebigen Stelle können Sie eine Variable oder eine Konstante.  
  
     - oder -   
  
     Verwenden Sie den Namen der Eigenschaft, nach dem Gleichheitszeichen (`=`) in einer zuweisungsanweisung signieren.  
  
     Das folgende Beispiel liest den Wert der [!INCLUDE[vbprvb](~/includes/vbprvb-md.md)] `Now` Eigenschaft implizit Aufrufen seiner `Get` Prozedur.  
  
     [!code-vb[VbVbalrDateProperties#4](./codesnippet/VisualBasic/how-to-get-a-value-from-a-property_1.vb)]  
  
2.  Wenn die Eigenschaft Argumente akzeptiert, führen Sie die Namen der Eigenschaft in Klammern einschließen, um die Argumentliste einschließen. Wenn keine Argumente vorhanden sind, können Sie die Klammern optional weglassen.  
  
3.  Platzieren Sie die Argumente in der Argumentliste innerhalb der Klammern durch Kommas getrennt ein. Achten Sie darauf, dass Sie die Argumente in der gleichen Reihenfolge angeben, dass die Eigenschaft die entsprechenden Parameter definiert.  
  
 Der Wert der Eigenschaft beteiligt ist, in dem Ausdruck ebenso wie eine Variable oder Konstante oder befindet sich in der Variablen oder Eigenschaft auf der linken Seite der Zuweisung.  
  
## <a name="see-also"></a>Siehe auch  
 [Verfahren](./index.md)  
 [Eigenschaftenprozeduren](./property-procedures.md)  
 [Parameter und Argumente von Prozeduren](./procedure-parameters-and-arguments.md)  
 [Property-Anweisung](../../../../visual-basic/language-reference/statements/property-statement.md)  
 [Unterschiede zwischen Eigenschaften und Variablen in Visual Basic](./differences-between-properties-and-variables.md)  
 [Gewusst wie: Erstellen einer Eigenschaft](./how-to-create-a-property.md)  
 [Gewusst wie: Deklarieren einer Eigenschaft mit gemischten Zugriffsebenen](./how-to-declare-a-property-with-mixed-access-levels.md)  
 [Gewusst wie: Aufrufen einer Eigenschaftenprozedur](./how-to-call-a-property-procedure.md)  
 [Vorgehensweise: Deklarieren und Aufrufen einer Standardeigenschaft in Visual Basic](./how-to-declare-and-call-a-default-property.md)  
 [Gewusst wie: Ablegen eines Werts in einer Eigenschaft](./how-to-put-a-value-in-a-property.md)
