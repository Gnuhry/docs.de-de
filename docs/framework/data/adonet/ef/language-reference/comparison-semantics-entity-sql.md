---
title: Vergleichssemantik (Entity SQL)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b36ce28a-2fe4-4236-b782-e5f7c054deae
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.openlocfilehash: f1fd1c21fc4f156bfe7a5abf9f76bd341e2d0f10
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="comparison-semantics-entity-sql"></a>Vergleichssemantik (Entity SQL)
Beim Ausführen aller folgenden [!INCLUDE[esql](../../../../../../includes/esql-md.md)]-Operationen werden Typinstanzen verglichen:  
  
## <a name="explicit-comparison"></a>Expliziter Vergleich  
 Gleichheitsoperationen:  
  
-   =  
  
-   !=  
  
 Sortieroperationen:  
  
-   <  
  
-   \<=  
  
-   >  
  
-   \>=  
  
 NULL-Zulässigkeitsoperationen:  
  
-   IS NULL  
  
-   IS NOT NULL  
  
## <a name="explicit-distinction"></a>Explizite Unterscheidung  
 Gleichheitsunterscheidung:  
  
-   DISTINCT  
  
-   GROUP BY  
  
 Sortierunterscheidung:  
  
-   ORDER BY  
  
## <a name="implicit-distinction"></a>Implizite Unterscheidung  
 Mengenoperationen und Prädikate (Gleichheit):  
  
-   UNION  
  
-   INTERSECT  
  
-   EXCEPT  
  
-   SET  
  
-   OVERLAPS  
  
 Elementprädikate (Gleichheit):  
  
-   IN  
  
## <a name="supported-combinations"></a>Unterstützte Kombinationen  
 In der folgenden Tabelle werden alle unterstützten Kombinationen von Vergleichsoperatoren für jede Art von Typ angezeigt:  
  
|**Typ**|**=**<br /><br /> **!=**|**GRUPPIEREN NACH**<br /><br /> **DISTINCT**|**UNION**<br /><br /> **INTERSECT**<br /><br /> **AUSNAHME:**<br /><br /> **FESTLEGEN**<br /><br /> **(ÜBERLAPPUNGEN)**|**IN**|**<   <=**<br /><br /> **>   >=**|**ORDER BY**|**IST NULL.**<br /><br /> **IST UNGLEICH NULL**|  
|-|-|-|-|-|-|-|-|  
|Entitätstyp|Ref<sup>1</sup>|Alle Eigenschaften<sup>2</sup>|Alle Eigenschaften<sup>2</sup>|Alle Eigenschaften<sup>2</sup>|Löst<sup>3</sup>|Löst<sup>3</sup>|Ref<sup>1</sup>|  
|Komplexer Typ|Löst<sup>3</sup>|Löst<sup>3</sup>|Löst<sup>3</sup>|Löst<sup>3</sup>|Löst<sup>3</sup>|Löst<sup>3</sup>|Löst<sup>3</sup>|  
|Zeile|Alle Eigenschaften<sup>4</sup>|Alle Eigenschaften<sup>4</sup>|Alle Eigenschaften<sup>4</sup>|Löst<sup>3</sup>|Löst<sup>3</sup>|Alle Eigenschaften<sup>4</sup>|Löst<sup>3</sup>|  
|Primitiver Typ|Anbieterspezifisch|Anbieterspezifisch|Anbieterspezifisch|Anbieterspezifisch|Anbieterspezifisch|Anbieterspezifisch|Anbieterspezifisch|  
|Multiset|Löst<sup>3</sup>|Löst<sup>3</sup>|Löst<sup>3</sup>|Löst<sup>3</sup>|Löst<sup>3</sup>|Löst<sup>3</sup>|Löst<sup>3</sup>|  
|Ref|Ja<sup>5</sup>|Ja<sup>5</sup>|Ja<sup>5</sup>|Ja<sup>5</sup>|Throw|Throw|Ja<sup>5</sup>|  
|Zuordnung<br /><br /> Typ|Löst<sup>3</sup>|Throw|Throw|Throw|Löst<sup>3</sup>|Löst<sup>3</sup>|Löst<sup>3</sup>|  
  
 <sup>1</sup>die Verweise der angegebenen Entitätstypinstanzen werden implizit verglichen, wie im folgenden Beispiel gezeigt:  
  
```  
SELECT p1, p2   
FROM AdventureWorksEntities.Product AS p1   
     JOIN AdventureWorksEntities.Product AS p2   
WHERE p1 != p2 OR p1 IS NULL  
```  
  
 Eine Entitätsinstanz kann nicht mit einem expliziten Verweis verglichen werden. Eine Ausnahme wird ausgelöst, wenn dies versucht wird. Folgende Abfrage löst beispielsweise eine Ausnahme aus:  
  
```  
SELECT p1, p2   
FROM AdventureWorksEntities.Product AS p1   
     JOIN AdventureWorksEntities.Product AS p2   
WHERE p1 != REF(p2)  
```  
  
 <sup>2</sup>Eigenschaften komplexer Typen werden vor dem Senden in den Speicher, sodass sie vergleichbar werden (sofern alle ihre Eigenschaften vergleichbar sind) vereinfacht. Siehe auch <sup>4.</sup>  
  
 <sup>3</sup>die Entity Framework-Laufzeit erkennt den nicht unterstützten Fall und löst eine angemessene Ausnahme aus, ohne den Anbieter/Speicher Anspruch zu nehmen.  
  
 <sup>4</sup>es wird versucht, alle Eigenschaften verglichen werden soll. Wenn eine Eigenschaft einen nicht vergleichbaren Typ hat, wie beispielsweise text, ntext oder image, kann eine Serverausnahme ausgelöst werden.  
  
 <sup>5</sup>alle Einzelelemente der Verweise werden verglichen (einschließlich des Namens der Entitätenmenge und aller Schlüsseleigenschaften des Entitätstyps).  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht über Entity SQL](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)
