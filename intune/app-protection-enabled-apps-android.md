---
title: Android-Apps mit App-Schutzrichtlinien
titlesuffix: Azure portal
description: In diesem Thema erfahren Sie, was Sie erwartet, wenn Ihre Android-App von App-Schutzrichtlinien verwaltet wird."
keywords: 
author: erikre
ms.author: erikre
manager: angrobe
ms.date: 12/07/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a6816285-8e43-4dc8-bca0-e80ec5ef01e6
ms.reviewer: andcerat
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: d269f4200560c3d903b9da3d92c021ffb03a78e8
ms.sourcegitcommit: e37e916e2bf14f092d3a767bc90d68c181d739fb
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/03/2018
---
# <a name="what-to-expect-when-your-android-app-is-managed-by-app-protection-policies"></a>Was Sie erwartet, wenn Ihre Android-App von App-Schutzrichtlinien verwaltet wird 

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Dieses Thema beschreibt die Benutzererfahrung für Apps mit App-Schutzrichtlinien. App-Schutzrichtlinien gelten nur, wenn Apps im geschäftlichen Kontext verwendet werden, z.B. wenn Sie Ihr Geschäftskonto für den Zugriff auf Apps verwenden oder auf Dateien zugreifen, die am OneDrive for Business-Speicherort Ihres Unternehmens gespeichert sind.
##  <a name="accessing-apps"></a>Zugreifen auf Apps

Die Unternehmensportal-App ist auf Android-Geräten für alle Apps erforderlich, die App-Schutzrichtlinien zugeordnet sind.

Bei Geräten, die nicht bei Intune registriert sind, muss die Unternehmensportal-App auf dem Gerät installiert sein. Benutzer müssen jedoch die Unternehmensportal-App nicht starten bzw. sich darin anmelden, bevor sie Apps verwenden können, die von App-Schutzrichtlinien verwaltet werden.
Die Unternehmensportal-App stellt für Intune eine Methode zum Freigeben von Daten an einen sicheren Speicherort dar. Daher wird diese App angefordert, auch wenn das Gerät nicht bei Intune registriert ist.


##  <a name="using-apps-with-multi-identity-support"></a>Verwenden von Apps mit Multi-Identity Support (Unterstützung für mehrere Identitäten)

App-Schutzrichtlinien gelten nur, wenn die App im geschäftlichen Kontext verwendet wird. Daher kann das App-Verhalten abhängig vom Kontext (geschäftlich oder privat) abweichen.

Bei Apps, die mehrere Identitäten unterstützen, wendet Intune die App-Schutzrichtlinien nur an, wenn der Endbenutzer die App im geschäftlichen Kontext verwendet.  Beispielsweise erhalten Endbenutzer eine PIN-Eingabeaufforderung, wenn Sie auf Geschäftsdaten zugreifen.  Bei der **Outlook-App** wird der Endbenutzer beim Starten der App zur Eingabe einer PIN aufgefordert. Bei der **OneDrive-App** erfolgt diese Aufforderung, wenn der Endbenutzer das Geschäftskonto eingibt.  Bei Microsoft **Word**, **PowerPoint* und **Excel** erfolgt diese Aufforderung, wenn der Endbenutzer auf Dokumente zugreift, die am OneDrive for Business-Speicherort des Unternehmens gespeichert sind.
##  <a name="managing-user-accounts-on-the-device"></a>Verwalten von Benutzerkonten auf dem Gerät

Intune unterstützt nur die Bereitstellung von App-Schutzrichtlinien auf je einem Benutzerkonto pro Gerät.

* Abhängig von der verwendeten App, ist der zweite Benutzer auf dem Gerät möglicherweise blockiert oder auch nicht. Unter allen Umständen wirken sich die App-Schutzrichtlinien nur auf den ersten Benutzer aus.

  * **Microsoft Word**, **Excel** und **PowerPoint** blockieren ein zweites Benutzerkonto nicht, die App-Schutzrichtlinien wirken sich auf das zweite Benutzerkonto jedoch nicht aus.

  * Für **OneDrive- und Outlook-Apps** kann nur ein geschäftliches Konto verwendet werden.  Das Hinzufügen weiterer Geschäftskonten wird von diesen Apps blockiert.  Sie können jedoch einen Benutzer entfernen und auf dem Gerät einen weiteren Benutzer hinzufügen.


* Wenn für ein Gerät vor der Bereitstellung der App-Schutzrichtlinien mehrere Benutzerkonten vorhanden sind, wird das Konto, für das die App-Schutzrichtlinien zuerst bereitgestellt werden, durch die Intune-App-Schutzrichtlinien verwaltet.


Lesen Sie das Beispielszenario unten, um genauer zu verstehen, wie mehrere Benutzerkonten behandelt werden.

Benutzer A arbeitet für zwei Unternehmen – **Unternehmen X** und **Unternehmen Y**. Benutzer A verfügt für jedes Unternehmen über ein geschäftliches Konto, und beide verwenden Intune zum Bereitstellen von App-Schutzrichtlinien. **Unternehmen X** stellt App-Schutzrichtlinien **vor** **Unternehmen Y** bereit. Das **Unternehmen X** zugeordnete Konto erhält die App-Schutzrichtlinie, nicht jedoch das dem Unternehmen Y zugeordnete Konto. Wenn das Unternehmen Y zugeordnete Konto durch die App-Schutzrichtlinien verwaltet werden soll, müssen Sie das Unternehmen X zugeordnete Benutzerkonto entfernen.
### <a name="adding-a-second-account"></a>Hinzufügen eines zweiten Kontos
####  <a name="android"></a>Android
Wenn Sie ein Android-Gerät verwenden, wird möglicherweise eine Sperrnachricht mit Anweisungen angezeigt, wie Sie das vorhandene Konto entfernen und ein neues Konto hinzufügen können.  Um das vorhandene Konto zu entfernen, wechseln Sie zu **Einstellungen &gt; Allgemein &gt; Anwendungs-Manager &gt; Unternehmensportal**, und wählen Sie „Daten löschen“ aus.

![Screenshot der Fehlermeldung und Anweisungen zum Entfernen des Kontos](./media/android-switch-user.png)

##  <a name="viewing-media-files-with-the-azure-information-protection-app-previously-known-as-rights-management-sharing-app"></a>Anzeigen von Mediendateien mit der Azure Information Protection-App (zuvor bekannt als Rights Management-Freigabeanwendung)
Verwenden Sie zum Anzeigen unternehmenseigener AV-, PDF- und Bilddateien auf Android-Geräten die [Azure Information Protection-App](https://play.google.com/store/apps/details?id=com.microsoft.ipviewer).

Laden Sie diese App aus dem Google Play herunter.  

Die folgenden Dateitypen werden unterstützt:

* **Audio:** AAC LC, HE-AACv1 (AAC+), HE-AACv2 (erweitertes AAC+), AAC ELD (enhanced low delay ACC, erweitertes AAC mit geringer Verzögerung), AMR-NB, AMR-WB, FLAC, MP3, MIDI, Ogg Vorbis, PCM/WAVE.
* **Video:** H.263, H.264 AVC, MPEG-4 SP, VP8.
* **Bild:** JPG, PJPG, PNG, PPNG, BMP, PBMP, GIF, PGIF, JPEG, PJPEG.
* **Dokumente:** PDF, PPDF

------------

|**pfile**|**text**|
|----|----|
|Pfile ist ein generisches „Wrapper“-Format für geschützte Dateien, das den verschlüsselten Inhalt sowie die Azure Information Protection-Lizenzen kapselt und zum Schützen beliebiger Dateitypen verwendet werden kann.|Textdateien, einschließlich XML, CSV, etc. können zum Anzeigen in der App geöffnet werden, selbst wenn sie geschützt sind. Dateitypen: TXT, PTXT, CSV, PCSV, LOG, PLOG, XML, PXML.|

---------------
## <a name="next-steps"></a>Nächste Schritte
[Was Sie erwartet, wenn Ihre iOS-App von App-Schutzrichtlinien verwaltet wird](app-protection-enabled-apps-ios.md)

### <a name="see-also"></a>Siehe auch
[Erstellen und Bereitstellen von App-Schutzrichtlinien mit Microsoft Intune](app-protection-policies.md)
