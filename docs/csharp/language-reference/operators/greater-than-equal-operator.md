---
title: Operator &gt;= (C#-Referenz)
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: '>=_CSharpKeyword'
helpviewer_keywords:
- greater than or equal to operator (>=) [C#]
- '>= operator [C#]'
ms.assetid: 0db4dcaf-56a3-4884-a7ad-35f64978a58d
caps.latest.revision: "16"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: f020c2bd8756899908681ab72cac7aa2a203c6a1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="gt-operator-c-reference"></a>Operator &gt;= (C#-Referenz)
Alle numerischen und Emumerationstypen definieren einen relationalen „größer oder gleich“-Operator (`>=`), der `true` zurückgibt, wenn der erste Operand größer oder gleich dem zweiten ist, andernfalls `false`.  
  
## <a name="remarks"></a>Hinweise  
 Benutzerdefinierte Typen können den Operator `>=` überladen. Weitere Informationen finden Sie unter [Operator](../../../csharp/language-reference/keywords/operator.md). Wenn `>=` überladen ist, muss [<=](../../../csharp/language-reference/operators/less-than-equal-operator.md) auch überladen werden. Operationen mit Ganzzahltypen sind grundsätzlich auch für Aufzählungen (enum) zulässig.  
  
## <a name="example"></a>Beispiel  
 [!code-csharp[csRefOperators#39](../../../csharp/language-reference/operators/codesnippet/CSharp/greater-than-equal-operator_1.cs)]  
  
## <a name="see-also"></a>Siehe auch  
 [C#-Referenz](../../../csharp/language-reference/index.md)  
 [C#-Programmierhandbuch](../../../csharp/programming-guide/index.md)  
 [C#-Operatoren](../../../csharp/language-reference/operators/index.md)
