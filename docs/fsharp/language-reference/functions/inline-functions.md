---
title: Inlinefunktionen (F#)
description: Informationen Sie zum F#-Inline-Funktionen verwenden, die direkt in den aufrufenden Code integriert werden.
keywords: Visual F#, F#, funktionale Programmierung
author: cartermp
ms.author: phcart
ms.date: 05/16/2016
ms.topic: language-reference
ms.prod: .net
ms.technology: devlang-fsharp
ms.devlang: fsharp
ms.assetid: 3fa31178-08f8-463d-9d41-d29220a90027
ms.openlocfilehash: 0489d411e2754eaab6a10ff0feb4405491b3b511
ms.sourcegitcommit: 425524461530f020f9747492b42f8cd72b011ae7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/25/2017
---
# <a name="inline-functions"></a>Inlinefunktionen

*Inlinefunktionen* sind Funktionen, die direkt in den aufrufenden Code integriert werden.


## <a name="using-inline-functions"></a>Verwendung von Inlinefunktionen
Wenn Sie statische Typparameter verwenden, müssen alle Funktionen, die durch Typparameter parametrisiert werden Inline sein. Damit wird sichergestellt, dass der Compiler diese Typparameter auflösen kann. Bei Verwendung von normalen generischen Typparametern besteht keine derartige Einschränkung.

Als die Verwendung von Membereinschränkungen aktivieren, können Inline-Funktionen bei der Optimierung von Code hilfreich sein. Übermäßige Verwendung von Inlinefunktionen kann jedoch den Code weniger beständiger gegen compileroptimierungen und die Implementierung von Bibliotheksfunktionen vorgenommenen Änderungen werden verursachen. Aus diesem Grund sollten Sie vermeiden, Inline-Funktionen für die Optimierung verwenden, es sei denn, Sie, alle anderen Optimierungstechniken versucht haben. Erstellen eine Inline-Funktion oder Methode kann die Leistung in einigen Fällen verbessern, aber das ist nicht immer die Groß-/Kleinschreibung. Aus diesem Grund sollten Sie Leistungsindikatoren verwenden, um sicherzustellen, dass eine bestimmte Funktion Inline ausführenden tatsächlich eine positive Auswirkung haben.

Die `inline` Modifizierer auf Funktionen auf der obersten Ebene, auf der Modulebene oder auf Methodenebene in einer Klasse angewendet werden kann.

Im folgenden Codebeispiel veranschaulicht eine Inlinefunktion auf der obersten Ebene, eine Inline-Instanzmethode und eine Inline-statische Methode.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-3/snippet201.fs)]
    
## <a name="inline-functions-and-type-inference"></a>Inlinefunktionen und Typrückschluss
Das Vorhandensein von `inline` wirkt sich auf den Typrückschluss. Grund hierfür ist Inlinefunktionen Statisch aufgelöste Typparameter aufweisen können während nicht-Inline-Funktionen nicht möglich. Das folgende Codebeispiel zeigt einen Fall, in dem `inline` ist hilfreich, da Sie eine Funktion verwenden, die einen statisch aufgelösten Typparameter hat den `float` Konvertierungsoperator.

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-3/snippet202.fs)]

Ohne die `inline` Modifizierer, zwingt die Funktion ein bestimmtes Typs in diesem Fall wird der Typrückschluss `int`. Mit der `inline` Modifizierer, die Funktion wird auch abgeleitet, dass Sie einen statisch aufgelösten Typparameter hat. Mit der `inline` Modifizierer, der Typ wird abgeleitet, folgendermaßen:

```fsharp
^a -> unit when ^a : (static member op_Explicit : ^a -> float)
```

Dies bedeutet, dass die Funktion einen beliebigen Typ akzeptiert, die eine Konvertierung in unterstützt **"float"**.


## <a name="see-also"></a>Siehe auch
[Funktionen](index.md)

[Einschränkungen](../generics/constraints.md)

[Statisch aufgelöste Typparameter](../generics/statically-resolved-type-parameters.md)
