---
title: "dotnet restore-Befehl – .NET Core-CLI"
description: "Erfahren Sie mehr über das Wiederherstellen von Abhängigkeiten und projektspezifischen Tools mit dem Befehl dotnet-restore."
keywords: dotnet-restore, CLI, CLI-Befehl, .NET Core
author: mairaw
ms.author: mairaw
ms.date: 11/30/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.openlocfilehash: 887f562803226d99901a6ee13175c1a43956b0cd
ms.sourcegitcommit: f416ac259c1a771e4e6c72728d8c11a77082f11c
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/01/2017
---
# <a name="dotnet-restore"></a>dotnet restore

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a>Name

`dotnet restore`: Stellt die Abhängigkeiten und Tools eines Projekts wieder her

## <a name="synopsis"></a>Übersicht

# <a name="net-core-2xtabnetcore2x"></a>[.NET Core 2.x](#tab/netcore2x)

```
dotnet restore [<ROOT>] [--configfile] [--disable-parallel] [--force] [--ignore-failed-sources] [--no-cache] [--no-dependencies] [--packages] [-r|--runtime] [-s|--source] [-v|--verbosity]
dotnet restore [-h|--help]
```

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

```
dotnet restore [<ROOT>] [--configfile] [--disable-parallel] [--ignore-failed-sources] [--no-cache] [--no-dependencies] [--packages] [-r|--runtime] [-s|--source] [-v|--verbosity]
dotnet restore [-h|--help]
```

---

## <a name="description"></a>Beschreibung

Der Befehl `dotnet restore` verwendet NuGet zum Wiederherstellen von Abhängigkeiten sowie projektspezifischen Tools, die in der Projektdatei angegeben sind. Standardmäßig wird die Wiederherstellung von Abhängigkeiten und Tools parallel ausgeführt.

[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]

Zum Wiederherstellen der Abhängigkeiten benötigt NuGet die Feeds, wo sich die Pakete befinden. Feeds werden in der Regel über die Konfigurationsdatei *NuGet.config* bereitgestellt. Eine standardmäßige Konfigurationsdatei wird bereitgestellt, wenn die CLI-Tools installiert sind. Sie geben zusätzliche Feeds an, indem Sie eine eigene *NuGet.config*-Datei im Projektverzeichnis erstellen. Sie können auch zusätzliche Feeds pro Aufruf an der Eingabeaufforderung angeben.

Für Abhängigkeiten geben Sie mithilfe des Arguments `--packages` an, wo die wiederhergestellten Pakete während der Wiederherstellung platziert werden. Wenn nichts angegeben wurde, wird der Standardcache des NuGet-Pakets verwendet. Er befindet sich im Verzeichnis `.nuget/packages` im Basisverzeichnis des Benutzers auf allen Betriebssystemen (z.B. */home/user1* unter Linux oder *C:\Users\user1* unter Windows).

Für projektspezifische Tools stellt `dotnet restore` zunächst das Paket wieder her, in dem sich das Tool befindet, und danach die Abhängigkeiten des Tools gemäß seiner Projektdatei.

Das Verhalten des Befehls `dotnet restore` wird durch einige Einstellungen in der *NuGet.Config*-Datei (falls vorhanden) beeinflusst. Das Festlegen von `globalPackagesFolder` in *NuGet.Config* platziert z.B. die wiederhergestellten NuGet-Pakete in den angegebenen Ordner. Dies ist eine Alternative zur Angabe der Option `--packages` im `dotnet restore`-Befehl. Weitere Informationen finden Sie im [NuGet.Config-Referenzthema](/nuget/schema/nuget-config-file).

## <a name="implicit-dotnet-restore"></a>Impliziter `dotnet restore`

Ab .NET Core 2.0 wird `dotnet restore` bei Bedarf implizit ausgeführt, wenn Sie die folgenden Befehle ausführen:

- [`dotnet new`](dotnet-new.md)
- [`dotnet build`](dotnet-build.md)
- [`dotnet run`](dotnet-run.md)
- [`dotnet test`](dotnet-test.md)
- [`dotnet publish`](dotnet-publish.md)
- [`dotnet pack`](dotnet-pack.md)

In den meisten Fällen müssen Sie den `dotnet restore`-Befehl nicht länger explizit verwenden. 

In einigen Fällen ist eine implizite Ausführung von `dotnet restore` unpraktisch. Zum Beispiel müssen einige automatisierte Systeme, wie etwa Buildsysteme, `dotnet restore` explizit aufrufen, um zu kontrollieren, wann die Wiederherstellung stattfindet, damit sie die Netzwerknutzung steuern können. Um eine implizite Ausführung von `dotnet restore` zu verhindern, können Sie die Option `--no-restore` mit einem beliebigen dieser Befehle verwenden, um die implizite Wiederherstellung zu deaktivieren.

## <a name="arguments"></a>Argumente

`ROOT`

Optionaler Pfad zur wiederherzustellenden Projektdatei.

## <a name="options"></a>Optionen

# <a name="net-core-2xtabnetcore2x"></a>[.NET Core 2.x](#tab/netcore2x)

`--configfile <FILE>`

Die NuGet-Konfigurationsdatei (*NuGet.config*) für den Wiederherstellungsvorgang.

`--disable-parallel`

Deaktiviert paralleles Erstellen von mehreren Projekten.

`--force`

Erzwingt das Auflösen aller Abhängigkeiten, auch wenn die letzte Wiederherstellung erfolgreich war. Dies entspricht dem Löschen der Datei *project.assets.json*.

`-h|--help`

Druckt eine kurze Hilfe für den Befehl.

`--ignore-failed-sources`

Bei fehlerhaften Quellen nur warnen, wenn Pakete die Versionsanforderung erfüllen.

`--no-cache`

Gibt an, dass Pakete und HTTP-Anfragen nicht zwischengespeichert werden.

`--no-dependencies`

Wenn Sie ein Projekt mit Projekt-zu-Projekt-Verweisen (P2P) wiederherstellen, stellen Sie das Stammprojekt wieder her und nicht die Verweise.

`--packages <PACKAGES_DIRECTORY>`

Gibt das Verzeichnis für wiederhergestellte Pakete an.

`-r|--runtime <RUNTIME_IDENTIFIER>`

Gibt eine Laufzeit für die Wiederherstellung des Pakets an. Wird für das Wiederherstellen von Paketen für Laufzeiten verwendet, die nicht explizit im `<RuntimeIdentifiers>`-Tag in der *.csproj*-Datei aufgeführt sind. Eine Liste der Runtime-IDs (RIDs) finden Sie unter [RID-Katalog](../rid-catalog.md). Es können mehrere RIDs bereitgestellt werden, indem diese Option mehrmals angegeben wird.

`-s|--source <SOURCE>`

Gibt eine NuGet-Paketquelle an, die während des Wiederherstellungsvorgangs zu verwenden ist. Dies überschreibt alle Quellen, die in der/den *NuGet.config*-Datei(en) angegeben sind. Es können mehrere Quellen bereitgestellt werden, indem diese Option mehrmals angegeben wird.

`--verbosity <LEVEL>`

Legt den Ausführlichkeitsgrad für den Befehl fest. Zulässige Werte sind `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` und `diag[nostic]`.

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

`--configfile <FILE>`

Die NuGet-Konfigurationsdatei (*NuGet.config*) für den Wiederherstellungsvorgang.

`--disable-parallel`

Deaktiviert paralleles Erstellen von mehreren Projekten.

`-h|--help`

Druckt eine kurze Hilfe für den Befehl.

`--ignore-failed-sources`

Bei fehlerhaften Quellen nur warnen, wenn Pakete die Versionsanforderung erfüllen.

`--no-cache`

Gibt an, dass Pakete und HTTP-Anfragen nicht zwischengespeichert werden.

`--no-dependencies`

Wenn Sie ein Projekt mit Projekt-zu-Projekt-Verweisen (P2P) wiederherstellen, stellen Sie das Stammprojekt wieder her und nicht die Verweise.

`--packages <PACKAGES_DIRECTORY>`

Gibt das Verzeichnis für wiederhergestellte Pakete an.

`-r|--runtime <RUNTIME_IDENTIFIER>`

Gibt eine Laufzeit für die Wiederherstellung des Pakets an. Wird für das Wiederherstellen von Paketen für Laufzeiten verwendet, die nicht explizit im `<RuntimeIdentifiers>`-Tag in der *.csproj*-Datei aufgeführt sind. Eine Liste der Runtime-IDs (RIDs) finden Sie unter [RID-Katalog](../rid-catalog.md). Es können mehrere RIDs bereitgestellt werden, indem diese Option mehrmals angegeben wird.

`-s|--source <SOURCE>`

Gibt eine NuGet-Paketquelle an, die während des Wiederherstellungsvorgangs zu verwenden ist. Dies überschreibt alle Quellen, die in der/den *NuGet.config*-Datei(en) angegeben sind. Es können mehrere Quellen bereitgestellt werden, indem diese Option mehrmals angegeben wird.

`--verbosity <LEVEL>`

Legt den Ausführlichkeitsgrad für den Befehl fest. Zulässige Werte sind `q[uiet]`, `m[inimal]`, `n[ormal]`, `d[etailed]` und `diag[nostic]`.

## <a name="examples"></a>Beispiele

Wiederherstellen von Abhängigkeiten und Tools für das Projekt im aktuellen Verzeichnis:

`dotnet restore`

Wiederherstellen von Abhängigkeiten und Tools für das Projekt `app1` im vorgegebenen Pfad:

`dotnet restore ~/projects/app1/app1.csproj`

Wiederherstellen der Abhängigkeiten und Tools für das Projekt im aktuellen Verzeichnis mit dem bereitgestellten Dateipfad als Quelle:

`dotnet restore -s c:\packages\mypackages`

Wiederherstellen der Abhängigkeiten und Tools für das Projekt im aktuellen Verzeichnis mit den beiden bereitgestellten Dateipfaden als Quellen:

`dotnet restore -s c:\packages\mypackages -s c:\packages\myotherpackages`

Wiederherstellen von Abhängigkeiten und Tools für das Projekt im aktuellen Verzeichnis und nur Anzeige von nur minimaler Ausgabe:

`dotnet restore --verbosity minimal`
