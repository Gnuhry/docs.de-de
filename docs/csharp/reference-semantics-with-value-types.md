---
title: Verweissemantik mit Werttypen
description: Grundlegendes zu Sprachfeatures, die das Kopieren von Strukturen auf ein Minimum reduzieren
author: billwagner
ms.author: wiwagn
ms.date: 11/10/2017
ms.topic: article
ms.prod: .net
ms.technology: devlang-csharp
ms.devlang: csharp
ms.custom: mvc
ms.openlocfilehash: 0c6e44a3e1a1458f4211b66b6d1ef5b4b30cd7c1
ms.sourcegitcommit: 5177d6ae2e9baf026f07ee0631556700a5a193f7
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/28/2017
---
# <a name="reference-semantics-with-value-types"></a>Verweissemantik mit Werttypen

Das Verwenden von Werttypen hat den Vorteil, dass sie häufig Heapzuweisungen vermeiden.
Ihr Nachteil ist, dass sie nach Wert kopiert werden. Dies macht es schwieriger, Algorithmen zu optimieren, die mit großen Datenmengen arbeiten. Neue Sprachfeatures in C# 7.2 bieten Mechanismen, die eine Semantik zur Übergabe als Verweis mit Werttypen ermöglichen. Wenn Sie diese Features geschickt einsetzen, können Sie sowohl Zuweisungen als auch Kopiervorgänge minimieren. In diesem Artikel werden diese neuen Features untersucht.

Viele der Codebeispiele in diesem Artikel veranschaulichen die neuen Features von C# 7.2. Um diese Features nutzen zu können, müssen Sie Ihr Projekt für die Verwendung von C# 7.2 oder höher konfigurieren. Sie können zur Auswahl Visual Studio verwenden. Klicken Sie für jedes Projekt im Menü **Projekt** auf **Eigenschaften**. Wählen Sie die Registerkarte **Build** aus, und klicken Sie auf **Erweitert**. Hier können Sie die Sprachversion konfigurieren. Wählen Sie entweder „7.2“ oder „Neueste“.  Alternativ können Sie die *CSPROJ*-Datei bearbeiten und den folgenden Knoten hinzufügen:

```XML
  <PropertyGroup>
    <LangVersion>7.2</LangVersion>
  </PropertyGroup>
```

Sie können als Wert entweder „7.2“ oder „latest“ verwenden.

## <a name="specifying-in-parameters"></a>Angeben von `in`-Parametern

In C# 7.2 wird das Schlüsselwort `in` hinzugefügt, um die vorhandenen Schlüsselwörter `ref` und `out` beim Schreiben einer Methode zu ergänzen, die Argumente als Verweis übergibt. Das Schlüsselwort `in` gibt an, dass Sie den Parameter als Verweis übergeben und die aufgerufene Methode den an sie übergebenen Wert nicht ändert. 

Dieser Zusatz bietet zahlreiche Möglichkeiten, Ihre Entwurfsabsicht auszudrücken. Werttypen werden bei der Übergabe an eine aufgerufene Methode kopiert, wenn Sie keinen der folgenden Modifizierer angeben. Jeder dieser Modifizierer gibt an, dass ein Werttyp als Verweis übergeben wird, um das Kopieren zu vermeiden. Jeder Modifizierer drückt eine andere Absicht aus:

- `out`: Diese Methode legt den Wert des Arguments fest, das als dieser Parameter verwendet wird.
- `ref`: Diese Methode kann den Wert des Arguments festlegen, das als dieser Parameter verwendet wird.
- `in`: Diese Methode ändert den Wert des Arguments nicht, das als dieser Parameter verwendet wird.

Wenn Sie den Modifizierer `in` zur Übergabe eines Arguments als Verweis hinzufügen, erklären Sie, dass Ihre Entwurfsabsicht darin besteht, Argumente als Verweis zu übergeben, um ein unnötiges Kopieren zu vermeiden. Sie beabsichtigen nicht, das als Argument verwendete Objekt zu ändern. Der folgende Code zeigt als Beispiel eine Methode, die den Abstand zwischen Punkten in einem 3D-Raum berechnet. 

[!code-csharp[InArgument](../../samples/csharp/reference-semantics/Program.cs#InArgument "Specifying an In argument")]

Die Argumente sind zwei Strukturen, die jeweils drei double-Werte enthalten. Ein double-Wert ist 8 Byte groß, also umfasst jedes Argument 24 Byte. Durch Angabe des Modifizierers `in` übergeben Sie – abhängig von der Architektur des Computers – einen 4-Byte- oder 8-Byte-Verweis an diese Argumente. Der Größenunterschied ist gering, kann sich aber schnell summieren, wenn Ihre Anwendung diese Methode in einer kurzen Schleife mit vielen unterschiedlichen Werten aufruft.
 
Der Modifizierer `in` ergänzt `out` und `ref` auch in anderer Weise. Sie können keine Überladungen einer Methode erstellen, die sich nur durch das Vorhandensein von `in`, `out` oder `ref` unterscheiden. Diese neuen Regeln erweitern dasselbe Verhalten, das stets für `out`- und `ref`-Parameter definiert wurde.

Der Modifizierer `in` kann auf einen beliebigen Member angewendet werden, der Parameter akzeptiert: Methoden, Delegaten, Lambdas, lokale Funktionen, Indexer, Operatoren.

Im Gegensatz zu `ref`- und `out`-Argumenten können Sie Literalwerte oder Konstanten für die Argumente für einen `in`-Parameter verwenden. Außerdem müssen Sie im Gegensatz zu einem `ref`- oder `out`-Parameter den Modifizierer `in` nicht an der Aufrufsite anwenden. Der folgende Code zeigt zwei Beispiele zum Aufruf der `CalculateDistance`-Methode. Im ersten Beispiel werden zwei lokale Variablen als Verweis übergeben. Im zweiten Beispiel wird als Teil des Methodenaufrufs eine temporäre Variable erstellt. 

[!code-csharp[UseInArgument](../../samples/csharp/reference-semantics/Program.cs#UseInArgument "Specifying an In argument")]

Der Compiler kann auf verschiedene Weise sicherstellen, dass der Schreibschutz eines `in`-Arguments erzwungen wird.  Zunächst kann die aufgerufene Methode nicht direkt einem `in`-Parameter zugewiesen werden. Eine direkte Zuweisung zu einem Feld eines `in`-Parameters ist nicht möglich. Außerdem können Sie keinen `in`-Parameter an eine Methode übergeben, die den Modifizierer `ref` oder `out` erfordert.
Der Compiler erzwingt, dass das Argument `in` eine schreibgeschützte Variable ist. Sie können eine beliebige Instanzmethode aufrufen, die eine Semantik zur Übergabe als Wert verwendet. In diesen Instanzen wird eine Kopie des `in`-Parameters erstellt. Da der Compiler eine temporäre Variable für jeden `in`-Parameter erstellen kann, können Sie auch Standardwerte für jeden `in`-Parameter angeben. Der folgende Code macht sich dies zunutze, um den Ursprung (Punkt 0,0) als Standardwert für den zweiten Punkt anzugeben:

[!code-csharp[InArgumentDefault](../../samples/csharp/reference-semantics/Program.cs#InArgumentDefault "Specifying defaults for an in parameter")]

Der Parameter `in` kann auch mit Verweistypen oder integrierten numerischen Werten verwendet werden. Allerdings sind die Vorteile in beiden Fällen – wenn überhaupt – nur minimal.

## <a name="ref-readonly-returns"></a>`ref readonly`-Rückgaben

Sie möchten vielleicht auch einen Werttyp als Verweis zurückgeben, aber dem Aufrufer verbieten, diesen Wert zu ändern. Verwenden Sie den Modifizierer `ref readonly`, um diese Entwurfsabsicht auszudrücken. So werden Leser darüber informiert, dass Sie einen Verweis auf vorhandene Daten zurückgeben, aber keine Änderungen zulassen. 

Der Compiler erzwingt, dass der Aufrufer den Verweis nicht ändern kann. Versuche einer direkten Zuweisung zum Wert führen zu einem Kompilierzeitfehler. Der Compiler kann jedoch nicht wissen, ob eine Membermethode den Zustand der Struktur ändert.
Um sicherzustellen, dass das Objekt nicht geändert wird, erstellt der Compiler eine und ruft Memberverweise mit dieser Kopie auf. Alle Änderungen werden an der Defensivkopie vorgenommen. 

Wahrscheinlich würde die Bibliothek, die `Point3D` verwendet, im Code oft den Ursprung verwenden. Jede Instanz erstellt ein neues Objekt im Stapel. Es kann vorteilhaft sein, eine Konstante zu erstellen und diese als Verweis zurückzugeben. Wenn Sie jedoch einen Verweis auf den internen Speicher zurückgeben, möchten Sie möglicherweise erzwingen, dass der Aufrufer den referenzierten Speicher nicht ändern kann. Der folgende Code definiert eine schreibgeschützte Eigenschaft zur Rückgabe von `readonly ref` an einen `Point3D`, der den Ursprung angibt.

[!code-csharp[OriginReference](../../samples/csharp/reference-semantics/Point3D.cs#OriginReference "Creating a readonly Origin reference")]

Das Kopieren einer ref readonly-Rückgabe ist einfach: Weisen Sie sie einfach einer Variablen zu, die nicht mit dem Modifizierer `ref readonly` deklariert wurde. Der Compiler generiert Code, um das Objekt im Rahmen der Zuweisung zu kopieren. 

Wenn Sie `ref readonly return` eine Variable zuweisen, können Sie entweder eine `ref readonly`-Variable oder eine wertweise Kopie des schreibgeschützten Verweises angeben:

[!code-csharp[AssignRefReadonly](../../samples/csharp/reference-semantics/Program.cs#AssignRefReadonly "Assigning a ref readonly")]

Die erste Zuweisung im vorhergehenden Code erstellt eine Kopie der Konstanten `Origin` und weist diese Kopie zu. Die zweite weist einen Verweis zu. Beachten Sie, dass der Modifizierer `readonly` Teil der Variablendeklaration sein muss. Der referenzierte Verweis kann nicht geändert werden. Derartige Versuche führen zu einem Kompilierzeitfehler.

## <a name="readonly-struct-type"></a>`readonly struct`-Typ

Das Anwenden von `ref readonly` auf Strukturen mit hoher Auslastung kann ausreichend sein.
In anderen Fällen möchten Sie vielleicht eine unveränderliche Struktur erstellen. Dann können Sie immer eine Übergabe als schreibgeschützter Verweis durchführen. Durch diese Vorgehensweise entfallen die Defensivkopien, die beim Zugriff auf Methoden einer Struktur erstellt werden, die als `in`-Parameter verwendet wird.

Sie erreichen dies, indem Sie einen `readonly struct`-Typ erstellen. Sie können den Modifizierer `readonly` einer Strukturdeklaration hinzufügen. Der Compiler erzwingt, dass alle Instanzmember der Struktur als `readonly` festgelegt sind. `struct` muss unveränderlich sein.

Es gibt weitere Optimierungen für `readonly struct`. Sie können den Modifizierer `in` überall dort verwenden, wo `readonly struct` ein Argument ist. Zusätzlich können Sie `readonly struct` als `ref return` zurückgeben, wenn Sie ein Objekt zurückgeben, dessen Lebensdauer über den Bereich der Methode hinausgeht, die das Objekt zurückgibt.

Schließlich erzeugt der Compiler effizienteren Code, wenn Sie Member von `readonly struct` aufrufen: Der `this`-Verweis – anstelle einer Kopie des Empfängers – ist immer ein `in`-Parameter, der als Verweis an die Membermethode übergeben wird. Durch diese Optimierung entfallen weitere Kopiervorgänge, wenn Sie `readonly struct` verwenden. `Point3D` ist ein hervorragender Kandidat für diese Änderung. Der folgende Code zeigt eine aktualisierte `ReadonlyPoint3D`-Struktur:

[!code-csharp[ReadonlyOnlyPoint3D](../../samples/csharp/reference-semantics/Point3D.cs#ReadonlyOnlyPoint3D "Defining an immutable structure")]

## <a name="ref-struct-type"></a>`ref struct`-Typ

Ein weiteres zugehöriges Sprachfeature ist die Möglichkeit, einen Werttyp zu deklarieren, der im Stapel zugeordnet werden muss. Anders ausgedrückt: Diese Typen können nie im Heap als Member einer anderen Klasse erstellt werden. Der primäre Beweggrund für dieses Feature waren <xref:System.Span%601> und zugehörige Strukturen. <xref:System.Span%601> kann einen verwalteten Zeiger als einen seiner Member enthalten, wobei der andere die span-Länge angibt. Die Implementierung erfolgt tatsächlich etwas anders, weil C# keine Zeiger auf verwalteten Speicher außerhalb eines unsicheren Kontexts unterstützt. Jeder Schreibvorgang, der den Zeiger und die Länge ändert, ist nicht unteilbar. Das bedeutet, dass ein <xref:System.Span%601> Bereichsfehlern oder anderen Sicherheitsverletzungen unterliegen würde, wenn es nicht auf einen einzelnen Stapelrahmen beschränkt wäre. Zusätzlich führt das Platzieren eines verwalteten Zeigers im GC-Heap typischerweise zu einem Absturz zur JIT-Zeit.

Möglicherweise haben Sie ähnliche Anforderungen, wenn Sie mit Speicher arbeiten, der mit [`stackalloc`](language-reference/keywords/stackalloc.md) erstellt wurde, oder wenn Sie Speicher aus Interop-APIs verwenden. Sie können für diese Anforderungen eigene `ref struct`-Typen definieren. In diesem Artikel wird aus Gründen der Einfachheit `Span<T>` in den Beispielen verwendet.

Über die `ref struct`-Deklaration wird deklariert, dass eine solche Struktur sich im Stapel befinden muss. Die Sprache stellt die sichere Verwendung dieser Typen sicher. Zu den weiteren als `ref struct` deklarierten Typen gehört <xref:System.ReadOnlySpan%601>. 

Das Ziel, einen `ref struct`-Typ als im Stapel zugewiesene Variable zu behalten, führt zu verschiedenen Regeln, die der Compiler für alle `ref struct`-Typen erzwingt.

- Sie können für `ref struct` kein Boxing durchführen. Sie können einen `ref struct`-Typ nicht einer Variablen vom Typ `object`, `dynamic` oder einem Schnittstellentyp zuweisen.
- Sie können `ref struct` nicht als Member einer Klasse oder einer normalen Struktur deklarieren.
- Sie können keine lokalen Variablen deklarieren, bei denen es sich um `ref struct`-Typen in asynchronen Methoden handelt. Sie können sie in synchronen Methoden deklarieren, die `Task`, `Task<T>` oder taskähnliche Typen zurückgeben.
- Sie können lokale `ref struct`-Variablen nicht in Iteratoren deklarieren.
- Sie können `ref struct`-Variablen nicht in Lambda-Ausdrücken oder lokalen Funktionen erfassen.

Diese Einschränkungen stellen sicher, dass Sie `ref struct` nicht versehentlich in einer Weise verwenden, die zu einer Höherstufung in den verwalteten Heap führt.

## <a name="conclusions"></a>Zusammenfassung

Diese Erweiterungen der Sprache C# wurden für leistungskritische Algorithmen entwickelt, bei denen Speicherbelegungen entscheidend sein können, um die erforderliche Leistung zu erzielen. Sie werden feststellen, dass Sie diese Features möglicherweise nicht oft in dem Code verwenden, den Sie schreiben. Diese Verbesserungen wurden jedoch an vielen Stellen im .NET Framework übernommen. Da immer mehr APIs diese Features nutzen, werden Sie feststellen, dass sich die Leistung Ihrer eigenen Anwendungen verbessert.
