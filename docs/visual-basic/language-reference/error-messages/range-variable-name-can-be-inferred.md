---
title: Der Name einer Bereichsvariablen kann nur von einem einfachen oder qualifizierten Namen ohne Argumente abgeleitet werden
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc36599
- bc36599
helpviewer_keywords: BC36599
ms.assetid: 17763dbe-f74f-4ccb-8086-cb7e45ec4d12
caps.latest.revision: "6"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 5c986fcf188482c526c53ddf3019cec5163d0b62
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="range-variable-name-can-be-inferred-only-from-a-simple-or-qualified-name-with-no-arguments"></a>Der Name einer Bereichsvariablen kann nur von einem einfachen oder qualifizierten Namen ohne Argumente abgeleitet werden
Ein Programmierelement, die eine oder mehrere Argumente akzeptiert, ist in einer LINQ-Abfrage enthalten. Der Compiler kann eine Bereichsvariable aus dieser Programmierelement abzuleiten.  
  
 **Fehler-ID:** BC36599  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1.  Geben Sie einen expliziten Variablennamen für das Programmierelement an, wie im folgenden Code gezeigt:  
  
```  
Dim query = From var1 In collection1   
            Select VariableAlias= SampleFunction(var1), var1  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Einführung in LINQ in Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)  
 [Select-Klausel](../../../visual-basic/language-reference/queries/select-clause.md)
