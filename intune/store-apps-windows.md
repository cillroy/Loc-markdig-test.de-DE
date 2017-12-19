---
title: "Hinzufügen von Windows Store-Apps in Intune"
titleSuffix: Azure portal
description: "Erfahren Sie mehr über das Hinzufügen von Windows Store-Apps in Intune.\""
keywords: 
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 05/04/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 07241b6d-86d8-4abb-83a2-3fc5feae5788
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: f10da996f8587e63320e31ae57e88a5f14f3f9c2
ms.sourcegitcommit: e10dfc9c123401fabaaf5b487d459826c1510eae
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/09/2017
---
# <a name="how-to-add-windows-store-apps-to-microsoft-intune"></a>Hinzufügen von Windows Store-Apps in Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]


1. Melden Sie sich beim Azure-Portal an.
2. Wählen Sie **Weitere Dienste** > **Überwachung und Verwaltung** > **Intune** aus.
3. Wählen Sie auf dem Blatt **Intune** die Option **Apps verwalten** aus.
4. Wählen Sie in der Workload **Mobile Apps** die Option **Verwalten** > **Apps** aus.
5. Wählen Sie über der Liste der Apps **Hinzufügen** aus.
6. Wählen Sie auf dem Blatt **App hinzufügen** die Option **App-Informationen** aus.
7. Konfigurieren Sie auf dem Blatt **App bearbeiten** die folgenden Informationen. Klicken Sie abschließend auf **Hinzufügen**. Abhängig von der ausgewählten App werden einige der Werte auf diesem Blatt möglicherweise automatisch ausgefüllt:
    - **App-Name:** Geben Sie den Namen der App ein, wie er im Unternehmensportal angezeigt werden soll. Stellen Sie sicher, dass alle App-Namen eindeutig sind. Wenn ein App-Name zweimal vergeben wird, wird den Benutzern im Unternehmensportal nur eine der Apps angezeigt.
    - **App-Beschreibung:** Geben Sie eine Beschreibung für die App ein. Diese Beschreibung wird den Benutzern im Unternehmensportal angezeigt.
    - **Herausgeber:** Geben Sie den Namen des Herausgebers der App ein.
    - **App Store-URL:** Geben Sie die App Store-URL der App an, die Sie erstellen möchten.
    - **Mindestens erforderliches Betriebssystem:** Wählen Sie in der Liste die mindestens erforderliche Betriebssystemversion aus, auf der die App installiert werden kann. Wenn Sie die App einem Gerät mit einem älteren Betriebssystem zuweisen, wird sie nicht installiert.
    - **Kategorie (optional):** Wählen Sie eine der integrierten oder von Ihnen erstellten App-Kategorien aus. Dadurch wird es für die Benutzer leichter, die App im Unternehmensportal zu finden.
    - **Diese App als ausgewählte App im Unternehmensportal anzeigen:** Zeigen Sie die App auf der Hauptseite des Unternehmensportal hervorgehoben an, wenn Benutzer nach Apps suchen.
    - **Informations-URL:** Geben Sie optional eine URL zu einer Website ein, die Informationen über diese App enthält. Diese URL wird den Benutzern im Unternehmensportal angezeigt.
    - **URL zu den Datenschutzbestimmungen:** Geben Sie optional eine URL zu einer Website ein, die Datenschutzinformationen für diese App enthält. Diese URL wird den Benutzern im Unternehmensportal angezeigt.
    - **Entwickler:** Geben Sie optional den Namen des App-Entwicklers ein.
    - **Besitzer:** Geben Sie optional einen Namen für den Besitzer dieser App ein, z.B. **Personalabteilung**.
    - **Anmerkungen:** Geben Sie Hinweise zu dieser App ein.
    - **Symbol hochladen:** Laden Sie ein Symbol hoch, das der App zugeordnet wird. Dies ist das Symbol, das gemeinsam mit der App angezeigt wird, wenn die Benutzer das Unternehmensportal durchsuchen.
8. Wenn Sie fertig sind, wählen Sie auf dem Blatt **App hinzufügen** die Option **Speichern** aus.

Die von Ihnen erstellte App wird in der Liste der Apps angezeigt, in der Sie sie ausgewählten Gruppen zuweisen können. Hilfe finden Sie unter [Zuweisen von Apps zu Gruppen](apps-deploy.md).

## <a name="manually-assign-windows-10-company-portal-app"></a>Manuelles Zuweisen der Windows 10-Unternehmensportal-App
Benutzer können die Unternehmensportal-App aus dem Microsoft Store installieren, um Geräte zu verwalten und Apps zu installieren. Wenn Ihr Unternehmen allerdings erfordert, dass Sie die Unternehmensportal-App zuweisen, können Sie die Windows 10-Unternehmensportal-App manuell direkt über Intune zuweisen, auch wenn Intune nicht in den Microsoft Store für Unternehmen integriert wurde.

 > [!NOTE]
 > Bei dieser Option müssen ggf. veröffentlichte App-Updates manuell zugewiesen werden.

1. Melden Sie sich bei Ihrem Konto im [Microsoft Store für Unternehmen](https://www.microsoft.com/business-store) an, und beziehen Sie die **Offlinelizenzversion** der Unternehmensportal-App.  
2. Wenn Sie über die App verfügen, wählen Sie sie auf der Seite **Inventory** (Bestand) aus.  
3. Wählen Sie unter **Plattform** die Option **Windows 10 all devices** (Windows 10: alle Geräte) sowie die passende **Architektur** aus, und starten Sie den Downloadvorgang. Für diese App wird keine App-Lizenzdatei benötigt.
![Abbildung mit Details zum Downloadpaket für „Windows 10 all devices“ (Windows 10: alle Geräte) und x86-Architektur](./media/Win10CP-all-devices.png)
4. Laden Sie alle Pakete unter „Erforderliche Frameworks“ herunter. Dieser Schritt muss für die x86-, x64- und ARM-Architektur ausgeführt werden. Dadurch ergeben sich insgesamt neun Pakete, wie im Anschluss zu sehen.

![Abbildung mit den herunterzuladenden Abhängigkeitsdateien ](./media/Win10CP-dependent-files.png)
5. Erstellen Sie einen Ordner (beispielsweise „C:&#92;Company Portal“), bevor Sie die Unternehmensportal-App in Intune hochladen, und strukturieren Sie die Pakete wie folgt:
  1. Platzieren Sie das Unternehmensportal-Paket im Ordner „C:\Company Portal“. Erstellen Sie dort auch einen Unterordner namens „Dependencies“.  
  ![Abbildung mit dem Ordner „Dependencies“ und der APPXBUN-Datei](./media/Win10CP-Dependencies-save.png)
  2. Platzieren Sie die neun Abhängigkeitspakete im Ordner „Dependencies“.  
  Sind die Abhängigkeiten nicht wie hier beschrieben strukturiert, werden sie von Intune nicht erkannt und nicht hochgeladen. In diesem Fall tritt der folgende Fehler auf:  
  ![Die Windows App-Abhängigkeit für dieses Softwareinstallationsprogramm wurde im Anwendungsordner nicht gefunden. Sie können diese Anwendung weiterhin erstellen und zuweisen. Sie können sie jedoch nicht ausführen, bis die fehlende Windows-App-Abhängigkeit bereitgestellt wird.](./media/Win10CP-error-message.png)
6. Kehren Sie zu Intune zurück, und laden Sie die Unternehmensportal-App als neue App hoch. Weisen Sie sie für die gewünschte Gruppe von Zielbenutzern als erforderliche App zu.  

Weitere Informationen zur Behandlung von Abhängigkeiten für universelle Apps durch Intune finden Sie unter [Deploying an appxbundle with dependencies via Microsoft Intune MDM](https://blogs.technet.microsoft.com/configmgrdogs/2016/11/30/deploying-an-appxbundle-with-dependencies-via-microsoft-intune-mdm/) (Bereitstellen einer APPXBUNDLE-Datei mit Abhängigkeiten über Microsoft Intune MDM).  

### <a name="how-do-i-update-the-company-portal-on-my-users-devices-if-they-have-already-installed-the-older-apps-from-the-store"></a>Wie aktualisiere ich das Unternehmensportal auf den Geräten meiner Benutzer, wenn diese bereits die älteren Apps aus dem Store installiert haben?
Falls Ihre Benutzer bereits die Unternehmensportal-App für Windows 8.1 oder Windows Phone 8.1 aus dem Store installiert haben, sollte diese automatisch auf die neue Version aktualisiert werden, ohne dass Sie oder Ihre Benutzer dazu aktiv werden müssen. Sollte die Aktualisierung nicht erfolgen, fordern Sie die Benutzer auf, sich zu vergewissern, dass sie auf ihren Geräten automatische Updates für Store-Apps aktiviert haben.   

### <a name="how-do-i-upgrade-my-sideloaded-windows-81-company-portal-app-to-the-windows-10-company-portal-app"></a>Wie führe ich ein Upgrade meiner quergeladenen Windows 8.1-Unternehmensportal-App auf die Windows 10-Unternehmensportal-App durch?
Wir empfehlen für die Migration die folgende Vorgehensweise: Legen Sie die Zuweisungsaktion auf „Deinstallieren“ fest, um die Zuweisung der Windows 8.1-Unternehmensportal-App zu löschen. Anschließend kann die Windows 10-Unternehmensportal-App mit einer der oben genannten Optionen zugewiesen werden.  

Wenn Sie die App querladen möchten und das Windows 8.1-Unternehmensportal zugewiesen haben, ohne es mit dem Symantec-Zertifikat zu signieren, führen Sie zur Durchführung des Upgrades die Schritte aus, die weiter oben im Abschnitt zur direkten Zuweisung über Intune beschrieben sind.

Wenn Sie die App querladen möchten und das Windows 8.1-Unternehmensportal mit dem Symantec-Codesignaturzertifikat zugewiesen und signiert haben, führen Sie die Schritte des folgenden Abschnitts aus.  

### <a name="how-do-i-upgrade-my-signed-and-sideloaded-windows-phone-81-company-portal-app-or-windows-81-company-portal-app-to-the-windows-10-company-portal-app"></a>Wie führe ich ein Upgrade meiner signierten quergeladenen Windows Phone 8.1-Unternehmensportal-App oder Windows 8.1-Unternehmensportal-App auf die Windows 10-Unternehmensportal-App durch?
Wir empfehlen für die Migration die folgende Vorgehensweise: Legen Sie die Zuweisungsaktion auf „Deinstallieren“ fest, um die vorhandene Zuweisung der Windows Phone 8.1-Unternehmensportal-App oder Windows 8.1-Unternehmensportal-App zu löschen. Anschließend kann die Windows 10-Unternehmensportal-App ganz normal zugewiesen werden.  

Andernfalls muss die Windows 10-Unternehmensportal-App entsprechend aktualisiert und signiert werden, um sicherzustellen, dass der Upgradepfad eingehalten wird.  

Wenn die Windows 10-Unternehmensportal-App auf diese Weise signiert und zugewiesen wird, müssen Sie diesen Prozess für jedes neue App-Update wiederholen, das im Store verfügbar wird. Die App wird nicht automatisch aktualisiert, wenn der Store aktualisiert wird.  

Im Anschluss erfahren Sie, wie Sie die App auf diese Weise signieren und zuweisen:

1. Laden Sie unter [https://aka.ms/win10cpscript](https://aka.ms/win10cpscript) das Microsoft Intune-Signierungsskript für die Windows 10-Unternehmensportal-App herunter.  Für dieses Skript muss das Windows SDK für Windows 10 auf dem Hostcomputer installiert sein. Das Windows SDK für Windows 10 können Sie unter [https://go.microsoft.com/fwlink/?LinkId=619296](https://go.microsoft.com/fwlink/?LinkId=619296) herunterladen.
2. Laden Sie die Windows 10-Unternehmensportal-App wie weiter oben beschrieben aus dem Microsoft Store für Unternehmen herunter.  
3. Führen Sie das Skript mit den im Skriptheader angegebenen Eingabeparametern aus, um die Windows 10-Unternehmensportal-App zu signieren (siehe Auszug weiter unten). An das Skript müssen keine Abhängigkeiten übergeben werden. Diese sind nur erforderlich, wenn die App in die Intune-Verwaltungskonsole hochgeladen wird.

|Parameter | Beschreibung|
| ------------- | ------------- |
|InputWin10AppxBundle |Der Pfad, an dem sich die APPXBUNDLE-Quelldatei befindet. |
|OutputWin10AppxBundle |Der Ausgabepfad für die signierte APPXBUNDLE-Datei.  Win81Appx Der Pfad, an dem sich die APPX-Datei des Windows 8.1- oder Windows Phone 8.1-Unternehmensportals befindet.|
|PfxFilePath |Der Pfad der PFX-Datei für das Symantec Enterprise Mobile-Codesignaturzertifikat. |
|PfxPassword| Das Kennwort des Symantec Enterprise Mobile-Codesignaturzertifikats. |
|PublisherId |Die Herausgeber-ID des Unternehmens. Wenn sie nicht vorhanden ist, wird das Feld "Subject" von Symantec Enterprise Mobile Code Signing Certificate verwendet.|
|SdkPath | Der Pfad des Stammordners für das Windows SDK für Windows 10. Dieses Argument ist optional und wird standardmäßig auf „${env:ProgramFiles(x86)}\Windows Kits\10“ festgelegt.|
Das Skript gibt nach der Ausführung die signierte Version der Windows 10-Unternehmensportal-App aus. Anschließend können Sie die signierte Version der Anwendung über Intune als branchenspezifische App zuweisen. Dadurch wird für die derzeit zugewiesenen Versionen ein Upgrade auf die neue App durchgeführt.  
