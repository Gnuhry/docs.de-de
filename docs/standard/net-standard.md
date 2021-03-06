---
title: .NET-Standard
description: "Erfahren Sie mehr über .NET Standard, dessen Versionen und die .NET-Implementierungen, von denen es unterstützt wird."
keywords: .NET Standard, PCL, .NET
author: mairaw
ms.author: mairaw
ms.date: 08/13/2017
ms.topic: article
ms.prod: .net
ms.technology: dotnet-standard
ms.devlang: dotnet
ms.assetid: c044882c-af15-45f2-96d1-534557a5ee9b
ms.openlocfilehash: ccb44b94f1b3ce2fb369de368454679b25ed351f
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="net-standard"></a>.NET-Standard

[.NET Standard](https://github.com/dotnet/standard) ist eine formale Spezifikation von .NET-APIs, die für alle .NET-Implementierungen verfügbar sein sollen. Die Motivation hinter .NET Standard ist das Herstellen einer umfassenderen Einheitlichkeit im .NET-Ökosystem. Auch wenn [ECMA-335](https://github.com/dotnet/coreclr/blob/master/Documentation/project-docs/dotnet-standards.md) weiterhin für Einheitlichkeit im .NET-Implementierungsverhalten sorgt, gibt es keine ähnliche Spezifikation für die .NET-Basisklassenbibliotheken (BCL) für Implementierungen der .NET-Bibliothek. 

.NET Standard ermöglicht im Wesentlichen die folgenden Szenarios: 

- Sie definiert einen einheitlichen Satz von BCL-APIs, die unabhängig von der Arbeitsauslastung für alle .NET-Implementierungen implementiert werden.
- Sie ermöglicht Entwicklern die Erstellung portabler Bibliotheken, die anhand desselben Satzes von APIs in .NET-Implementierungen eingesetzt werden können.
- Sie reduziert oder beseitigt sogar die bedingte Kompilierung freigegebener Quellen aufgrund von .NET-APIs (nur für Betriebssystem-APIs).

Die verschiedenen .NET-Implementierungen verwenden spezifische Versionen von .NET Standard als Ziel. Jede .NET-Implementierung kündigt die höchste .NET Standardversion an, die von ihr unterstützt wird, was bedeutet, dass sie auch frühere Versionen unterstützt. .NET Framework 4.6 implementiert z.B. .NET Standard 1.3 und macht damit alle APIs verfügbar, die in den Versionen 1.0 bis 1.3 von .NET Standard definiert sind. Auf ähnliche Weise implementiert .NET Framework 4.6.1 .NET Standard 1.4, während .NET Core 1.0 .NET Standard 1.6 implementiert.

## <a name="net-implementation-support"></a>Unterstützung der .NET-Implementierung

In der folgenden Tabelle sind alle Versionen von .NET Standard und die unterstützten Plattformen aufgeführt:

[!INCLUDE [net-standard-table](~/includes/net-standard-table.md)]

Gehen Sie folgendermaßen vor, um die höchste Version von .NET Standard zu suchen, die Sie als Ziel verwenden können:
1. Suchen Sie die Zeile, die die .NET-Implementierung enthält, die Sie ausführen möchten.
2. Suchen Sie in dieser Zeile die Spalte, in der Ihre Version angegeben ist (von rechts nach links).
3. Die Spaltenüberschrift gibt die .NET Standard-Version an, die Ihr Ziel unterstützt (alle niedrigeren .NET Standard-Versionen werden ebenfalls unterstützt).
4. Wiederholen Sie diesen Vorgang für jede Plattform, die als Ziel verwendet werden soll. Wenn Sie mehrere Zielplattformen verwenden, sollten Sie die kleinste unterstützten Versionen auswählen. Wenn Sie .NET Standard z.B. auf .NET Framework 4.5 und .NET Core 1.0 ausführen möchten, ist die höchste .NET Standard-Version, die Sie verwenden können, .NET Standard 1.1.

### <a name="which-net-standard-version-to-target"></a>Auswahl der .NET Standard-Zielversion

Bei der Auswahl der .NET Standard-Version sollten Sie diesen Kompromiss berücksichtigen:

- Je höher die Version, desto mehr APIs stehen zur Verfügung.
- Je niedriger die Version, desto mehr Plattformen unterstützen sie.

Im Allgemeinen sollten Sie als Zielversion die *niedrigste* mögliche Version von .NET Standard verwenden. Nachdem Sie also die höchste .NET Standard-Zielversion gefunden, gehen Sie folgendermaßen vor:
1. Wählen Sie die nächst niedrigere .NET Standard-Version als Zielversion, und erstellen Sie Ihr Projekt.
2. Wenn das Projekt erfolgreich erstellt wurde, wiederholen Sie Schritt 1. Andernfalls wählen Sie die nächst höhere Version als Zielversion aus, und das ist die Version, die Sie verwenden sollten.

### <a name="net-standard-versioning-rules"></a>Regeln für die .NET Standard-Versionskontrolle

Es gibt zwei primäre Versionskontrollregeln:

- Additiv: .NET Standard-Versionen sind logisch konzentrische Kreise: höhere Versionen umfassen alle APIs früherer Versionen. Zwischen den Versionen gibt es keine die Lauffähigkeit der Anwendung beeinträchtigenden Änderungen.
- Unveränderlich. Nach der Auslieferung von .NET Standard-Versionen erfolgen keine Änderungen. Neue APIs werden mit bestimmten .NET-Implementierungen wie .NET Core zum ersten Mal verfügbar. Wenn das .NET Standard-Prüfungsgremium der Ansicht ist, dass die neuen APIs allgemein bereitgestellt werden sollten, werden sie in einer neuen Version von .NET Standard hinzugefügt.

## <a name="comparison-to-portable-class-libraries"></a>Vergleich mit portablen Klassenbibliotheken

.NET Standard ersetzt [portable Klassenbibliotheken (PCL)](./cross-platform/cross-platform-development-with-the-portable-class-library.md). .NET Standard profitiert von der Erfahrung mit der Erstellung portabler Bibliotheken, indem eine Standard-BCL zusammengestellt und damit eine umfassendere Einheitlichkeit für .NET-Implementierungen hergestellt wird. Eine Bibliothek, die .NET Standard als Ziel verwendet, ist eine PCL oder eine „auf .NET Standard basierende PCL“. Vorhandene PCLs werden als „profilbasierte PCLs“ bezeichnet.

.NET Standard und PCL-Profile wurden zu ähnlichen Zwecke erstellt, unterscheiden sich jedoch in wesentlichen Bereichen.

Ähnlichkeiten:

- Definiert die APIs, die zur Freigabe von binärem Code verwendet werden können.

Unterschiede:

- .NET Standard ist ein zusammengestellter Satz von APIs, während PCL-Profile durch Schnittpunkte vorhandener Plattformen definiert werden.
- .NET Standard weist im Gegensatz zu PCL-Profilen eine lineare Versionierung auf.
- PCL-Profile stehen für Microsoft-Plattformen, während .NET Standard plattformunabhängig ist.

## <a name="specification"></a>Spezifikation

Die Spezifikation von .NET Standard ist ein standardisierter Satz von APIs. Die Spezifikation wird durch Implementierungen von .NET verwaltet, insbesondere Microsoft (einschließlich .NET Framework, .NET Core und Mono) und Unity. Im Rahmen der Einrichtung neuer Versionen von .NET Standard über [GitHub](https://github.com/dotnet/standard) wird ein öffentlicher Feedbackprozess verwendet.

### <a name="official-artifacts"></a>Offizielle Artefakte

Die offizielle Spezifikation ist ein Satz von CS-Dateien zur Definition der APIs, die Bestandteile des Standards sind. Das [ref-Verzeichnis](https://github.com/dotnet/standard/tree/master/netstandard/ref) im [dotnet/standard-Repository](https://github.com/dotnet/corefx/tree/master/src) definiert die .NET Standard-APIs.

Das [NETStandard.Library](https://www.nuget.org/packages/NETStandard.Library)-Metapaket ([Quelle](https://github.com/dotnet/standard/blob/master/netstandard/pkg/NETStandard.Library.dependencies.props)) beschreibt den Satz von Bibliotheken, die (teilweise) eine oder mehrere Versionen von .NET Standard definieren.

Eine bestimmte Komponente, wie System.Runtime, beschreibt Folgendes:

- Teil von .NET Standard (nur der Bereich).
- Mehrere Versionen von .NET Standard für diesen Bereich.

Abgeleitete Elemente werden bereitgestellt, um ein einfacheres Lesen und bestimmte Entwicklungsszenarios (z.B. die Verwendung eines Compilers) zu ermöglichen.

- [API-Liste in Markdown](https://github.com/dotnet/standard/tree/master/docs/versions)
- Referenzassemblys, die als [NuGet-Pakete](../core/packages.md) verteilt und vom Metapaket [NETStandard.Library](https://www.nuget.org/packages/NETStandard.Library/) referenziert werden.

### <a name="package-representation"></a>Paketdarstellung

Das primäre Verteilungsinstrument für .NET Standard sind [NuGet-Pakete](../core/packages.md). Implementierungen werden in einer Vielzahl von Methoden abgeleitet, die jeweils für die einzelnen .NET-Implementierungen geeignet sind.

NuGet-Pakete sind auf mindestens ein [Framework](frameworks.md) ausgerichtet. Die Pakete von .NET Standard sind für das Framework „.NET Standard“ ausgelegt. Sie können über den [komprimierten TFM](frameworks.md) `netstandard` (z.B. `netstandard1.4`) das .NET Standard Framework als Ziel angeben. Bibliotheken, die auf mehreren Runtimes ausgeführt werden sollen, sollten dieses Framework als Ziel verwenden. 

Das Metapaket `NETStandard.Library` verweist auf den vollständigen Satz von NuGet-Paketen, die .NET Standard definieren.  Die gängigste Methode, `netstandard` als Ziel auszuwählen, ist das Verweisen auf dieses Metapaket. Es beschreibt und bietet Zugriff auf etwa 40 .NET-Bibliotheken und zugehörige APIs, die .NET Standard definieren. Sie können auf zusätzliche Pakete verweisen, die `netstandard` als Ziel verwenden, um Zugriff auf weitere APIs zu erhalten. 

### <a name="versioning"></a>Versionskontrolle

Die Spezifikation ist nicht singulär, sondern ein ständig wachsender und linear versionierter Satz von APIs. In der ersten Version des Standards wird ein Basissatz von APIs eingerichtet. Nachfolgende Versionen fügen APIs hinzu und erben APIs, die in früheren Versionen definiert wurden. Es gibt keine festgelegte Möglichkeit zum Entfernen von APIs aus dem Standard.

.NET Standard ist weder spezifisch auf eine bestimmte .NET-Implementierung ausgelegt, noch entspricht sie dem Versionierungsschema einer dieser Runtimes.

APIs, die einer der Implementierungen (z.B. .NET Framework, .NET Core und Mono) hinzugefügt werden, können als Kandidaten für die Spezifikation betrachtet werden, insbesondere, wenn sie von grundlegender Natur sind. Neue [Versionen von .NET Standard](https://github.com/dotnet/standard/blob/master/docs/versions.md) werden basierend auf .NET-Implementierungsversionen erstellt, sodass Sie neue APIs über eine .NET Standard-PCL adressieren können. Die Mechanismen der Versionskontrolle werden ausführlich unter [.NET Core-Versionskontrolle](../core/versions/index.md) beschrieben.

Die Versionskontrolle von .NET Standard ist wichtig für die Nutzung. Mit einer bestimmten Version von .NET Standard können Sie Bibliotheken verwenden, die auf dieselbe oder eine niedrigere Version ausgerichtet sind. Die folgende Vorgehensweise beschreibt den Workflow für die Verwendung von PCLs von .NET Standard, die auf .NET Standard ausgerichtet sind.

- Wählen Sie eine Version von .NET Standard für Ihre PCL.
- Verwenden Sie Bibliotheken, die von derselben oder einer niedrigeren Version von .NET Standard abhängig sind.
- Wenn Sie eine Bibliothek finden, die von einer höheren Version von .NET Standard abhängig ist, müssen Sie entweder dieselbe Version implementieren oder von der Verwendung dieser Bibliothek absehen.

### <a name="pcl-compatibility"></a>PCL-Kompatibilität

.NET Standard ist mit einer Teilmenge von PCL-Profilen kompatibel. .NET Standard der Versionen 1.0, 1.1 und 1.2 überschneiden sich jeweils mit einem Satz von PCL-Profilen. Diese Überschneidung wurde aus zwei Gründen erstellt:

- Auf dem .NET-Standard basierende PCLs können auf profilbasierte PCLs verweisen.
- Profilbasierte PCLs können als auf dem .NET-Standard basierende PCLs paketiert werden.

Die Kompatibilität profilbasierter PCLs wird über das NuGet-Paket [Microsoft.NETCore.Portable.Compatibility](https://www.nuget.org/packages/Microsoft.NETCore.Portable.Compatibility) gewährleistet. Diese Abhängigkeit ist erforderlich, wenn Sie auf NuGet-Pakete verweisen, die profilbasierte PCLs enthalten.

Profilbasierte PCLs, die als `netstandard` paketiert wurden, sind einfacher zu verwenden als normal paketierte profilbasierte PCLs. `netstandard`-Verpackung ist mit vorhandenen Benutzern kompatibel.

Sehen Sie sich den Satz von PCL-Profilen an, die mit dem .NET-Standard kompatibel sind: 

| PCL-Profil | .NET-Standard | PCL-Plattformen
|:-----------:|:-------------:|------------------------------------------------------------------------------
| Profile7    | 1.1           | .NET Framework 4.5, Windows 8
| Profile31   | 1.0           | Windows 8.1, Windows Phone Silverlight 8.1
| Profile32   | 1.2           | Windows 8.1, Windows Phone 8.1
| Profile44   | 1.2           | .NET Framework 4.5.1, Windows 8.1
| Profile49   | 1.0           | .NET Framework 4.5, Windows Phone Silverlight 8
| Profile78   | 1.0           | .NET Framework 4.5, Windows 8, Windows Phone Silverlight 8
| Profile84   | 1.0           | Windows Phone 8.1, Windows Phone Silverlight 8.1
| Profile111  | 1.1           | .NET Framework 4.5, Windows 8, Windows Phone 8.1
| Profile151  | 1.2           | .NET Framework 4.5.1, Windows 8.1, Windows Phone 8.1
| Profile157  | 1.0           | Windows 8.1, Windows Phone 8.1, Windows Phone Silverlight 8.1
| Profile259  | 1.0           | .NET Framework 4.5, Windows 8, Windows Phone 8.1, Windows Phone Silverlight 8


## <a name="targeting-net-standard"></a>Festlegen von .NET Standard als Ziel

Sie können .NET-Standardbibliotheken anhand einer Kombination aus dem `netstandard`-Framework und dem NETStandard.Library-Metapaket [erstellen](../core/tutorials/libraries.md). Sehen Sie sich Beispiele dafür an, wie [.NET Standard mithilfe von .NET Core-Tools als Ziel festgelegt wird](../core/packages.md).

## <a name="see-also"></a>Siehe auch
[.NET Standard-Versionen](https://github.com/dotnet/standard/blob/master/docs/versions.md)
