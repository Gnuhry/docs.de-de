---
title: "Gewusst wie: Erstellen von Registrierungsschlüsseln und Festlegen von deren Werten in Visual Basic"
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- RegistryKey.CreateSubKey
- RegistryKey.SetValue
helpviewer_keywords:
- registry keys [Visual Basic], creating
- registry [Visual Basic], adding values
- registry [Visual Basic], adding keys
- registry keys [Visual Basic], setting values
- examples [Visual Basic], registry
ms.assetid: d3e40f74-c283-480c-ab18-e5e9052cd814
caps.latest.revision: "30"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: b6e71c106592490b92cf6f2dc02e59cddb28b95d
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-a-registry-key-and-set-its-value-in-visual-basic"></a>Gewusst wie: Erstellen von Registrierungsschlüsseln und Festlegen von deren Werten in Visual Basic
Die `CreateSubKey`-Methode des `My.Computer.Registry`-Objekts kann verwendet werden, um einen Registrierungsschlüssel zu erstellen.  
  
## <a name="procedure"></a>Prozedur  
  
#### <a name="to-create-a-registry-key"></a>Erstellen eines Registrierungsschlüssels  
  
-   Verwenden Sie die `CreateSubKey`-Methode, geben sie dabei an, unter welcher Struktur der Schlüssel platziert werden soll sowie den Namen des Schlüssels. Der Parameter `Subkey` unterscheidet nicht zwischen Groß- und Kleinschreibung. Dieses Beispiel erstellt den Registrierungsschlüssel `MyTestKey` unter HKEY_CURRENT_USER.  
  
     [!code-vb[VbResourceTasks#17](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-create-a-registry-key-and-set-its-value_1.vb)]  
  
#### <a name="to-create-a-registry-key-and-set-a-value-in-it"></a>So erstellen Sie einen Registrierungsschlüssel und legen einen Wert darin fest  
  
1.  Verwenden Sie die `CreateSubkey`-Methode, geben sie dabei an, unter welcher Struktur der Schlüssel platziert werden soll sowie den Namen des Schlüssels. Dieses Beispiel erstellt den Registrierungsschlüssel `MyTestKey` unter HKEY_CURRENT_USER.  
  
     [!code-vb[VbResourceTasks#17](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-create-a-registry-key-and-set-its-value_1.vb)]  
  
2.  Legen Sie den Wert mit der `SetValue`-Methode fest. Im folgenden Beispiel wird der Zeichenfolgenwert festgelegt. „MyTestKeyValue“ zu „Dies ist ein Testwert“.  
  
     [!code-vb[VbResourceTasks#14](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-create-a-registry-key-and-set-its-value_2.vb)]  
  
## <a name="example"></a>Beispiel  
 Dieses Beispiel erstellt den Registrierungsschlüssel `MyTestKey` unter HKEY_CURRENT_USER und legt den Zeichenfolgenwert `MyTestKeyValue` auf `This is a test value` fest.  
  
 [!code-vb[VbResourceTasks#15](../../../../visual-basic/developing-apps/programming/computer-resources/codesnippet/VisualBasic/how-to-create-a-registry-key-and-set-its-value_3.vb)]  
  
## <a name="robust-programming"></a>Stabile Programmierung  
 Untersuchen Sie die Registrierungsstruktur, um eine adäquate Position für den Schlüssel zu ermitteln. Sie können beispielsweise den Schlüssel HKEY_CURRENT_USER\Software des aktuellen Benutzers öffnen und einen Schlüssel mit dem Namen Ihres Unternehmens erstellen. Anschließend fügen Sie die Registrierungswerte dem Schlüssel für das Unternehmen hinzu.  
  
 Wenn Sie die Registrierung von einer Webanwendung lesen, hängt der aktuelle Benutzer von der Authentifizierung und dem Identitätswechsel ab, die in der Webanwendung implementiert sind.  
  
 Es ist sicherer, die Daten in den Benutzerordner (<xref:Microsoft.Win32.Registry.CurrentUser>) anstatt auf den lokalen Computer (<xref:Microsoft.Win32.Registry.LocalMachine>) zu schreiben.  
  
 Wenn Sie einen Registrierungswert erstellen, müssen Sie festlegen, was geschehen soll, wenn der Wert bereits vorhanden ist. Möglicherweise wurde der Wert bereits von einem bösartigen Prozess erstellt, der nun darauf zugreifen kann. Wenn Sie dem Registrierungswert Daten hinzufügen, kann der andere Prozess darauf zugreifen. Um dies zu verhindern, verwenden Sie die <xref:Microsoft.Win32.RegistryKey.GetValue%2A>-Methode. Die Methode gibt `Nothing` zurück, wenn der Schlüssel noch nicht vorhanden ist.  
  
 Es ist nicht sicher, geheime Daten wie Kennwörter in der Registrierung als Klartext zu speichern. Dies gilt auch, wenn der Registrierungsschlüssel durch Zugriffssteuerungslisten (ACLs) geschützt ist.  
  
 Die folgenden Bedingungen können einen Ausnahmefehler verursachen:  
  
-   Der Name des Schlüssels lautet `Nothing` (<xref:System.ArgumentNullException>).  
  
-   Der Benutzer ist nicht zum Erstellen von Registrierungsschlüsseln berechtigt (<xref:System.Security.SecurityException>).  
  
-   Der Name des Schlüssels überschreitet das Limit von 255 Zeichen (<xref:System.ArgumentException>).  
  
-   Der Schlüssel ist geschlossen (<xref:System.IO.IOException>).  
  
-   Der Registrierungsschlüssel ist schreibgeschützt (<xref:System.UnauthorizedAccessException>).  
  
## <a name="net-framework-security"></a>.NET Framework-Sicherheit  
 Die Assembly benötigt zum Ausführen dieses Prozesses eine von der <xref:System.Security.Permissions.RegistryPermission>-Klasse gewährte Berechtigungsebene. Wenn Sie in einem teilweise vertrauenswürdigen Kontext arbeiten, kann der Vorgang möglicherweise aufgrund fehlender Berechtigungen eine Ausnahme auslösen. Ebenso muss der Benutzer die richtigen Zugriffssteuerungslisten zum Erstellen von oder Schreiben auf Einstellungen verfügen. Beispielsweise besitzt eine lokale Anwendung, die die Sicherheitsberechtigung für den Codezugriff besitzt, möglicherweise keine Betriebssystemberechtigung. Weitere Informationen finden Sie unter [Grundlagen der Codezugriffssicherheit](https://msdn.microsoft.com/library/33tceax8).  
  
## <a name="see-also"></a>Siehe auch  
 <xref:Microsoft.VisualBasic.MyServices.RegistryProxy>  
 <xref:Microsoft.VisualBasic.MyServices.RegistryProxy.CurrentUser%2A>  
 <xref:Microsoft.Win32.RegistryKey.CreateSubKey%2A>  
 [Lesen aus der und Schreiben in die Registrierung](../../../../visual-basic/developing-apps/programming/computer-resources/reading-from-and-writing-to-the-registry.md)  
 [Grundlagen der Codezugriffssicherheit](https://msdn.microsoft.com/library/33tceax8)
