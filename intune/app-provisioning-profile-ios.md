---
title: App-Bereitstellungsprofile
titlesuffix: Azure portal
description: "Intune stellt Ihnen die Tools zum proaktiven Zuweisen eines neuen Bereitstellungsprofils auf Geräten zur Verfügung, auf denen Apps installiert sind, die bald ablaufen.\""
keywords: 
author: erikre
ms.author: erikre
manager: angrobe
ms.date: 05/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: bbc3ba4a-df48-4aeb-988b-69a177764e3a
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 2b58fb0d9b69e875736b5d2ea884ae9d3453b481
ms.sourcegitcommit: 67ec0606c5440cffa7734f4eefeb7121e9d4f94f
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/08/2017
---
# <a name="use-ios-mobile-provisioning-profiles-to-prevent-your-apps-from-expiring"></a>Verwenden von mobilen iOS-Bereitstellungsprofilen, um zu verhindern, dass Apps ablaufen

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

## <a name="introduction"></a>Einführung

Die iPhones und iPads zugewiesenen branchenspezifischen Apple iOS-Apps wurden mit integriertem Bereitstellungsprofil und per Zertifikat signiertem Code erstellt. Beim Ausführen der App bestätigt iOS die Integrität der iOS-App und erzwingt Richtlinien, die durch das Bereitstellungsprofil definiert werden. Folgende Überprüfungen finden statt:

- **Integrität der Installationsdateien**: iOS vergleicht die Details der App mit dem öffentlichen Schlüssel des Unternehmenssignaturzertifikats. Wenn Unterschiede festgestellt werden, wurde der Inhalt der App möglicherweise verändert, und die Ausführung der App wird nicht zugelassen.
- **Erzwingen von Funktionen**: iOS versucht, die App-Funktionen aus dem Bereitstellungsprofil des Unternehmens (nicht den Bereitstellungsprofilen der einzelnen Entwickler) zu erzwingen, die in der App-Installationsdatei (IPA) enthalten sind.


Das Unternehmenssignaturzertifikat, das Sie zum Signieren von Apps verwenden, ist in der Regel drei Jahre lang gültig. Allerdings läuft das Bereitstellungsprofil nach einem Jahr ab. Während das Zertifikat noch gültig ist, stellt Intune Ihnen die Tools zum proaktiven Zuweisen eines neuen Bereitstellungsprofils auf Geräten zur Verfügung, auf denen Apps installiert sind, die bald ablaufen.
Nach Ablauf des Zertifikats müssen Sie die App mit einem neuen Zertifikat erneut signieren und ein neues Bereitstellungsprofil mit dem Schlüssel des neuen Zertifikats einbetten.


## <a name="how-to-create-an-ios-mobile-app-provisioning-profile"></a>Erstellen eines Bereitstellungsprofils für mobile iOS-Apps

1. Melden Sie sich beim Azure-Portal an.
2. Wählen Sie **Weitere Dienste** > **Überwachung und Verwaltung** > **Intune** aus.
3. Wählen Sie auf dem Blatt **Intune** die Option **Mobile Apps** aus.
1.  Wählen Sie im Abschnitt **Mobile Apps** die Option **Verwalten** > **iOS-Bereitstellungsprofile** aus.
2.  Wählen Sie auf dem Blatt mit der Profilliste die Option **Profil erstellen** aus.
3. Legen Sie auf dem Blatt **Profil erstellen** die folgenden Einstellungen fest:
    - **Name**: Geben Sie einen Namen für dieses mobile Bereitstellungsprofil an.
    - **Beschreibung**: Geben Sie optional eine Beschreibung der Richtlinie ein.
    - **Profildatei hochladen**: Klicken Sie auf **Importieren**, und wählen Sie eine Datei mit einem mobilen Apple-Konfigurationsprofil (mit der Erweiterung **.mobileprovision**) aus, die Sie von der Apple Developer-Website heruntergeladen haben.
4. Wählen Sie abschließend **Erstellen** aus.

## <a name="next-steps"></a>Nächste Schritte

Weisen Sie das Profil den entsprechenden iOS-Geräten zu. Weitere Informationen und Anweisungen finden Sie unter [Zuweisen von Geräteprofilen](device-profile-assign.md).
