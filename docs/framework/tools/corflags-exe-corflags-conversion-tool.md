---
title: CorFlags.exe (Konvertierungstool CorFlags)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- CorFlags conversion tool
- CorFlags.exe
- portable executable files, CorFlags section
ms.assetid: ef900f8f-71ca-4dde-9b8c-95ddb0d7d89c
caps.latest.revision: "17"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: ca3e9dbe5578623ccc67898c6f08213c31ad8e23
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="corflagsexe-corflags-conversion-tool"></a>CorFlags.exe (Konvertierungstool CorFlags)
Das Konvertierungstool „CorFlags“ ermöglicht das Konfigurieren des CorFlags-Abschnitts eines Headers eines portierbaren ausführbaren Images.  
  
 Dieses Tool wird automatisch mit Visual Studio installiert. Zum Ausführen des Tools verwenden Sie die Developer-Eingabeaufforderung (oder die Visual Studio-Eingabeaufforderung in Windows 7). Weitere Informationen finden Sie unter [Eingabeaufforderungen](../../../docs/framework/tools/developer-command-prompt-for-vs.md).  
  
 Geben Sie an der Eingabeaufforderung Folgendes ein:  
  
## <a name="syntax"></a>Syntax  
  
```  
CorFlags.exe assembly [options]  
```  
  
#### <a name="parameters"></a>Parameter  
  
|Erforderlicher Parameter|Beschreibung|  
|------------------------|-----------------|  
|`assembly`|Der Name der Assembly, für die CorFlags konfiguriert werden soll.|  
  
|Option|Beschreibung|  
|------------|-----------------|  
|**/32BIT[REQ]+**|Legt das 32BITREQUIRED-Flag fest.|  
|**/32BIT[REQ]-**|Löscht das 32BITREQUIRED-Flag.|  
|**/32BITPREF+**|Legt das 32BITPREFERRED-Flag fest. Die App wird als 32-Bit-Prozess sogar auf 64-Bit-Plattformen ausgeführt. Legen Sie dieses Flag nur auf EXE-Dateien fest. Wenn das Flag auf eine DLL-Datei festgelegt ist, kann die DLL in 64-Bit-Prozessen nicht geladen werden und eine <xref:System.BadImageFormatException>-Ausnahme ausgelöst. Eine EXE-Datei mit diesem Flag kann in einem 64-Bit-Prozess geladen werden.<br /><br /> Neu im [!INCLUDE[net_v45](../../../includes/net-v45-md.md)].|  
|**/32BITPREF-**|Löscht das 32BITPREFERRED-Flag.<br /><br /> Neu im [!INCLUDE[net_v45](../../../includes/net-v45-md.md)].|  
|**/?**|Zeigt Befehlssyntax und Optionen für das Tool an.|  
|**/Force**|Erzwingt ein Update, auch wenn es sich um eine Assembly mit starkem Namen handelt. **Wichtig**: Nach dem Aktualisieren einer Assembly mit starkem Namen muss diese erneut signiert werden, bevor ihr Code ausgeführt wird.|  
|**/help**|Zeigt Befehlssyntax und Optionen für das Tool an.|  
|**/ILONLY+**|Legt das ILONLY-Flag fest.|  
|**/ILONLY-**|Löscht das ILONLY-Flag.|  
|**/nologo**|Unterdrückt die Anzeige des Startbanners von Microsoft.|  
|**/RevertCLRHeader**|Setzt die CLR-Headerversion auf 2.0 zurück.|  
|**/UpgradeCLRHeader**|Aktualisiert die CLR-Headerversion auf 2.5. **Wichtig**: Assemblys können nur als nativer Code ausgeführt werden, wenn sie mindestens über die CLR-Headerversion 2.5 verfügen.|  
  
## <a name="remarks"></a>Hinweise  
 Wenn keine Optionen angegeben sind, zeigt das Konvertierungstool CorFlags die Flags für die angegebene Assembly an.  
  
## <a name="see-also"></a>Siehe auch  
 [Extras](../../../docs/framework/tools/index.md)  
 [64-Bit-Anwendungen](../../../docs/framework/64-bit-apps.md)  
 [Eingabeaufforderungen](../../../docs/framework/tools/developer-command-prompt-for-vs.md)
