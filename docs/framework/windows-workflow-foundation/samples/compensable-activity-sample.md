---
title: "Kompensierbare Aktivität – Beispiel"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 58f4898c-b2b8-44a4-9a73-3bef4da6d5ba
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 8b6b8eff89ebded7681a88cc4b1aee877828e021
ms.sourcegitcommit: ce279f2d7fe2220e6ea0a25a8a7a5370ddf8d9f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2017
---
# <a name="compensable-activity-sample"></a>Kompensierbare Aktivität – Beispiel
In diesem Beispiel wird veranschaulicht, wie die `CompensableActivity`-Aktivität verwendet wird, um die Arbeit zu definieren, die für eine angegebene Aktion während der normalen Ausführung erledigt werden soll, und die Arbeit, die erledigt werden muss, um diese Aktion auszugleichen, falls zu einem späteren Zeitpunkt erforderlich.  Der erste Teil des Beispiels zeigt, wie Einheiten kompensierbarer Arbeit in [!INCLUDE[wf](../../../../includes/wf-md.md)] mit einer `CompensableActivity`-Aktivität definiert werden können und wie sie bei einer erfolgreichen Ausführung ausgeführt werden.  Der zweite Teil des Beispiels zeigt, wie die gleichen Einheiten kompensierbarer Arbeit die Kompensation automatisch vornehmen, wenn ein unerwartetes Ereignis eintritt und die Workflowinstanz abgebrochen wird.  
  
### <a name="to-set-up-build-and-run-the-sample"></a>So können Sie das Beispiel einrichten, erstellen und ausführen  
  
1.  Öffnen Sie mit Visual Studio 2010 die Datei "CompensableActivity.sln".  
  
2.  Erstellen Sie die Projektmappe, indem Sie STRG+UMSCHALT+B drücken.  
  
3.  Drücken Sie F5, um die Anwendung auszuführen.  
  
> [!IMPORTANT]
>  Die Beispiele sind möglicherweise bereits auf dem Computer installiert. Suchen Sie nach dem folgenden Verzeichnis (Standardverzeichnis), bevor Sie fortfahren.  
>   
>  `<InstallDrive>:\WF_WCF_Samples`  
>   
>  Wenn dieses Verzeichnis nicht vorhanden ist, rufen Sie [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](http://go.microsoft.com/fwlink/?LinkId=150780) auf, um alle [!INCLUDE[indigo1](../../../../includes/indigo1-md.md)] - und [!INCLUDE[wf1](../../../../includes/wf1-md.md)] -Beispiele herunterzuladen. Dieses Beispiel befindet sich im folgenden Verzeichnis.  
>   
>  `<InstallDrive>:\WF_WCF_Samples\WF\Basic\Compensation\BasicCompensableActivity`