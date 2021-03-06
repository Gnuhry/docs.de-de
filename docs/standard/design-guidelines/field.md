---
title: Feldentwurf
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- fields, design guidelines
- read-only fields
- member design guidelines, fields
ms.assetid: 7cb4b0f3-7a10-4c93-b84d-733f7134fcf8
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: dc3249518dd1e1c751de08c22d1c5eb4fa28dc6d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="field-design"></a>Feldentwurf
Das Prinzip der Kapselung ist einer der wichtigsten Konzepte in eines objektorientierten Entwurfs. Dieses Prinzip gibt an, dass in einem Objekt gespeicherte Daten nur auf dieses Objekt zugegriffen werden soll.  
  
 Eine gute Möglichkeit, interpretiert das Prinzip ist zu sagen, dass ein Typ, damit Änderungen an Felder des Typs (Änderungen, Name oder Typ) vorgenommen werden können, ohne Unterbrechung Code nur für Elemente des Typs entworfen werden soll. Diese Interpretation impliziert sofort, dass alle Felder privat sein müssen.  
  
 Wir ausschließen Konstanten und statische schreibgeschützte Felder aus dieser Einschränkung strict, da Suchfelder, fast per Definition nie erforderlich sind, ändern.  
  
 **X nicht** bieten Instanzfelder, die öffentlich und/oder geschützt sind.  
  
 Sie sollten Eigenschaften für den Zugriff auf Felder und trifft diese öffentliche oder geschützte bereitstellen.  
  
 **Führen Sie ✓** verwenden Sie Konstante Felder für Konstanten, die nie geändert wird.  
  
 Der Compiler brennt const Felder die Werte direkt in Aufrufen von Code. Aus diesem Grund können Konstante Werte ohne beschädigen Kompatibilität nie geändert werden.  
  
 **Führen Sie ✓** öffentliche statische `readonly` Felder für vordefinierte Objektinstanzen.  
  
 Wenn die vordefinierten Instanzen des Typs vorhanden sind, deklarieren Sie diese als öffentliche schreibgeschützte statische Felder des Typs selbst.  
  
 **X nicht** Zuweisen von Instanzen von Typen, die auf änderbare `readonly` Felder.  
  
 Ein änderbarer Typ ist ein Typ mit Instanzen, die geändert werden können, nachdem sie instanziiert werden. Z. B. Arrays, die meisten Auflistungen und Streams änderbare Typen sind jedoch <xref:System.Int32?displayProperty=nameWithType>, <xref:System.Uri?displayProperty=nameWithType>, und <xref:System.String?displayProperty=nameWithType> sind alle unveränderlich. Den schreibgeschützten Modifizierer auf einen Typ Verweisfeld wird verhindert, dass die Instanz, die in das Feld ersetzt wird gespeichert, aber es verhindert jedoch nicht das Feld Instanzdaten bearbeitet werden durch Aufrufen von Membern die Instanz ändern.  
  
 *Teilen © 2005, 2009 Microsoft Corporation. Alle Rechte vorbehalten.*  
  
 *Nachdruck mit Genehmigung von Pearson-Education, Inc. aus [Framework-Entwurfsrichtlinien: Konventionen, Idiome und Muster für Wiederverwendbaren .NET-Bibliotheken, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) Krzysztof Cwalina und Brad Abrams veröffentlicht 22 Oktober 2008 durch Addison Wesley Professional als Teil der Microsoft Windows-Entwicklung Reihe.*  
  
## <a name="see-also"></a>Siehe auch  
 [Entwurfsrichtlinien für Member](../../../docs/standard/design-guidelines/member.md)  
 [Frameworkentwurfsrichtlinien](../../../docs/standard/design-guidelines/index.md)
