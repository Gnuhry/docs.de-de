---
title: Numerische Operatoren und Vergleichsoperatoren
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 25b4a26a-06f2-4f80-87a9-76705ed46197
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: f77cb612468b401f6aa526e46cc7481d0b47d385
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="numeric-and-comparison-operators"></a>Numerische Operatoren und Vergleichsoperatoren
Arithmetische Operatoren und Vergleichsoperatoren funktionieren mit folgenden Ausnahmen wie in der Common Language Runtime (CLR):  
  
-   SQL unterstützt den Modulusoperator bei Gleitkommazahlen nicht.  
  
-   SQL unterstützt ungeprüfte arithmetische Operatoren nicht.  
  
-   Inkrementoperatoren und Dekrementoperatoren führen zu Nebeneffekten, wenn Sie diese in Ausdrücken verwenden, die nicht in SQL repliziert werden können und daher nicht unterstützt werden.  
  
## <a name="supported-operators"></a>Unterstützte Operatoren  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] unterstützt die folgenden Operatoren.  
  
-   Grundlegende arithmetische Operatoren  
  
    -   `+`  
  
    -   `-` (Subtraktion)  
  
    -   `*`  
  
    -   `/`  
  
    -   Visual Basic-Ganzzahlendivision (`\`)  
  
    -   `%` (Visual Basic `Mod`)  
  
    -   `<<`  
  
    -   `>>`  
  
    -   `-` (unäre Negation)  
  
-   Grundlegende Vergleichsoperatoren:  
  
    -   Visual Basic `=` und C# `==`  
  
    -   Visual Basic `<>` und C# `!=`  
  
    -   Visual Basic `Is/IsNot`  
  
    -   `<`  
  
    -   `<=`  
  
    -   `>`  
  
    -   `>=`  
  
## <a name="see-also"></a>Siehe auch  
 [Datentypen und Funktionen](../../../../../../docs/framework/data/adonet/sql/linq/data-types-and-functions.md)  
 [C#-Operatoren](http://msdn.microsoft.com/library/0301e31f-22ad-49af-ac3c-d5eae7f0ac43)  
 [Operatoren](../../../../../visual-basic/language-reference/operators/index.md)
