---
title: "dotnet list-Verweisbefehl – .NET Core-CLI"
description: "Der Verweisbefehl „dotnet-list“ bietet eine praktische Option zum Listen von Verweisen zwischen Projekten."
author: mairaw
ms.author: mairaw
ms.date: 08/14/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.openlocfilehash: b3e903c15a7486faa279d47ad5e2e00c090b19af
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="dotnet-list-reference"></a>dotnet list reference

[!INCLUDE [topic-appliesto-net-core-all](../../../includes/topic-appliesto-net-core-all.md)]

## <a name="name"></a>Name

`dotnet list reference`: Listet Projekt-zu-Projekt-Verweise auf.

## <a name="synopsis"></a>Übersicht

`dotnet list [<PROJECT>] reference [-h|--help]`

## <a name="description"></a>Beschreibung

Der `dotnet list reference`-Befehl bietet eine praktische Option zum Listen von Projektverweisen auf ein bestimmtes Projekt.

## <a name="arguments"></a>Argumente

`PROJECT`

Gibt die Projektdatei an, die für die Auflistung von Verweisen verwendet werden soll. Ist dieses Argument nicht angegeben, sucht der Befehl im aktuellen Verzeichnis nach einer Projektdatei.

## <a name="options"></a>Optionen

`-h|--help`

Druckt eine kurze Hilfe für den Befehl.

## <a name="examples"></a>Beispiele

Listen Sie die Projektverweise für das angegebene Projekt:

`dotnet list app/app.csproj reference`

Listen Sie die Projektverweise für das Projekt im aktuellen Verzeichnis:

`dotnet list reference`
