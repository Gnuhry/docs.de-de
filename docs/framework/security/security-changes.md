---
title: "Änderungen der Sicherheit in .NET Framework"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Allow Partially Trusted Callers attribute
- .NET Framework 4, security changes
- .NET Framework security
- security-transparent code
- security-critical code
- code access security, changes
ms.assetid: 5e87881c-9c13-4b52-8ad1-e34bb46e8aaa
caps.latest.revision: "52"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: c1a96e30527aa3da4274ed55059b24aa5a7eeb47
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/18/2017
---
# <a name="security-changes-in-the-net-framework"></a>Änderungen der Sicherheit in .NET Framework
Die wichtigste Änderung im Hinblick auf die Sicherheit in [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] betrifft starke Namen. Eine Beschreibung dieser Änderungen finden Sie unter [Enhanced Strong Naming](../../../docs/framework/app-domains/enhanced-strong-naming.md) .  
  
 .NET Framework stellt ein Sicherheitsmodell mit zwei Ebenen für verwaltete Anwendungen bereit. [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] -Apps werden in einem Windows-Sicherheitscontainer ausgeführt, der den Zugriff auf Ressourcen beschränkt. Innerhalb dieses Containers werden verwaltete Anwendungen mit voller Vertrauenswürdigkeit ausgeführt. Im Hinblick auf die Codezugriffssicherheit (Code Access Security, CAS) haben Entwickler keine Möglichkeit, Berechtigungen heraufstufen. Informationen zu den von Windows gewährten Berechtigungen finden Sie im Windows Dev Center unter [Deklaration der App-Funktionen (Windows Store-Apps)](http://go.microsoft.com/fwlink/?LinkId=230436) . Informationen zum Erstellen einer [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] -App finden Sie unter [Create your first Windows Runtime app using C# or Visual Basic](http://go.microsoft.com/fwlink/?LinkId=230461)(Erstellen Ihrer ersten Windows-Runtime-App mit C# oder Visual Basic).
