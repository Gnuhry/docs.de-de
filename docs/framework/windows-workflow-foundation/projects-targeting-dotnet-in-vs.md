---
title: "Erstellen von Projekten für .NET Framework 3.0 und 3.5 in Visual Studio 2010"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 81858ab7-763c-4eac-83fe-d7205e5c4c98
caps.latest.revision: "7"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 6dc6657bad5cc11eaa723c733319673468749b79
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="writing-projects-targeting-the-net-framework-30-and-35-in-visual-studio-2010"></a>Erstellen von Projekten für .NET Framework 3.0 und 3.5 in Visual Studio 2010
Mit [!INCLUDE[vs2010](../../../includes/vs2010-md.md)] können Sie Projekte für [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)], Version 3.0 oder 3.5, erstellen. In diesem Thema wird die dafür erforderliche Vorgehensweise beschrieben.  
  
> [!NOTE]
>  Stellen Sie beim Hinzufügen von Aktivitäten sicher, dass die erforderliche Version von [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] festgelegt wurde. Wenn Sie die Zielversion des Workflows ändern, nachdem die Aktivitäten hinzugefügt wurden, kann der Workflow nicht überprüft werden.  
  
> [!WARNING]
>  Wenn Sie einen bestehenden Workflow mit .NET Framework 3.5-Aktivitäten in [!INCLUDE[vs2010](../../../includes/vs2010-md.md)] öffnen, wird ein Fehler bei `this.SetValue()` verursacht. Um Projekte zu öffnen, die mit früheren Versionen von .NET Framework erstellt wurden, öffnen Sie zunächst einen leeren Workflow im Designer, und fügen Sie eine .NET Framework 3.5-Aktivität hinzu.  
  
## <a name="to-create-a-net-framework--30-or-35-project-with-visual-studio-2010"></a>So erstellen Sie ein .NET Framework 3.0- oder 3.5-Projekt mit Visual Studio 2010  
  
1.  Öffnen Sie [!INCLUDE[vs2010](../../../includes/vs2010-md.md)].  
  
2.  Wählen Sie **Datei**, **neue**, **Projekt**.  
  
3.  Wählen Sie in der Dropdownliste oben im Dialogfeld die gewünschte Version von [!INCLUDE[dnprdnshort](../../../includes/dnprdnshort-md.md)] aus.  
  
## <a name="to-upgrade-the-targeted-version-of-the-net-framework"></a>So aktualisieren Sie die Zielversion von .NET Framework  
  
1.  Mit der rechten Maustaste des Projekts im Projektmappen-Explorer, und wählen Sie **Eigenschaften**.  
  
2.  In der **Zielframework** Dropdown-Liste, wählen Sie die gewünschte Version.
