---
title: 'Fehler beim Schreiben in die Ausgabedatei &quot;&lt;Dateiname&gt;&quot;: &lt;Fehler&gt; | Microsoft-Dokumentation'
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc31019
- bc31019
dev_langs:
- VB
helpviewer_keywords:
- BC31019
ms.assetid: 0845b245-11bb-46fd-95ca-f6cef3c318ef
caps.latest.revision: 10
author: stevehoag
ms.author: shoag
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: fe093ec3b36ba733cb9b0c162e242c8dce6b7c78
ms.lasthandoff: 03/13/2017

---
# <a name="unable-to-write-to-output-file-39ltfilenamegt39-lterrorgt"></a>Fehler beim Schreiben in die Ausgabedatei "&lt;Dateiname&gt;': &lt;Fehler&gt;
Beim Erstellen der Datei ist ein Fehler aufgetreten.  
  
 Eine Ausgabedatei kann nicht zum Schreiben geöffnet werden. Die Datei (oder der Ordner, der die Datei enthält) kann für die Exklusivnutzung durch einen anderen Prozess geöffnet sein, oder sie ist schreibgeschützt.  
  
 Häufige Situationen, in denen eine Datei exklusiv genutzt wird, sind:  
  
-   Die Anwendung wird bereits ausgeführt und nutzt die Dateien. Stellen Sie zum Lösen dieses Problems sicher, dass die Anwendung nicht ausgeführt wird.  
  
-   Die Datei wurde in einer anderen Anwendung geöffnet. Stellen Sie zum Lösen dieses Problems sicher, dass keine andere Anwendung auf die Dateien zugreift. Es ist nicht immer ersichtlich, welche Anwendung auf Ihre Dateien zugreift; ein Neustart Ihres Computer kann in diesem Fall der einfachste Weg sein, um die Anwendung zu beenden.  
  
 Es reicht aus, dass eine Projektausgabedatei schreibgeschützt ist, um diese Ausnahme auszulösen.  
  
 **Fehler-ID:** BC31019  
  
## <a name="to-correct-this-error"></a>So beheben Sie diesen Fehler  
  
1.  Kompilieren Sie das Programm erneut, um festzustellen, ob der Fehler erneut auftritt.  
  
2.  Wenn der Fehler weiterhin besteht, speichern Sie Ihre Arbeit, und starten Sie [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] erneut.  
  
3.  Wenn der Fehler weiterhin besteht, starten Sie den Computer neu.  
  
4.  Wenn der Fehler erneut auftritt, installieren Sie [!INCLUDE[vbprvb](../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] neu.  
  
5.  Wenn der Fehler auch nach der erneuten Installation auftritt, informieren Sie den Produktsupport von Microsoft.  
  
### <a name="to-check-file-attributes-in-file-explorer"></a>So prüfen Sie Dateiattribute im Datei-Explorer  
  
1.  Öffnen Sie den gewünschten Ordner.  
  
2.  Klicken Sie auf die **Ansichten** Symbol, und wählen Sie **Details**.  
  
3.  Mit der rechten Maustaste in der Kopfzeile der Spalte, und wählen Sie **Attribute** aus der Dropdown-Liste.  
  
### <a name="to-change-the-attributes-of-a-file-or-folder"></a>So ändern Sie die Attribute einer Datei oder eines Ordners  
  
1.  In **Datei-Explorer**mit der rechten Maustaste auf die Datei oder den Ordner, und wählen Sie **Eigenschaften**.  
  
2.  In der **Attribute** Teil der **allgemeine** Registerkarte Deaktivieren der **schreibgeschützt** Feld.  
  
3.  Press **OK**.  
  
## <a name="see-also"></a>Siehe auch  
 [Sprechen Sie mit uns](https://docs.microsoft.com/visualstudio/ide/talk-to-us)