---
title: "Konfigurieren der Einstellungen für Gerätefunktionen in Intune"
titleSuffix: Azure portal
description: "Erfahren Sie, wie Sie mit Intune Funktionen auf Geräten konfigurieren, die Sie verwalten.\""
keywords: 
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 12/7/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 42f9b104-c1f6-4dfc-8aa4-1d33e1eaf61f
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 382a410fee9abdcb2a3b5670563f25264d477540
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2017
---
# <a name="how-to-configure-device-feature-settings-in-microsoft-intune"></a>Konfigurieren der Einstellungen für Gerätefunktionen in Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Mit Geräteeinschränkungen können Sie Funktionen auf iOS- und macOS-Geräten wie AirPrint, Benachrichtigungen und freigegebene Gerätekonfigurationen steuern.

Anhand der Informationen in diesem Thema lernen Sie die Grundlagen zum Konfigurieren von Gerätefunktionsprofilen kennen. In den weiterführenden Themen zu den einzelnen Plattformen erfahren Sie etwas über Besonderheiten der jeweiligen Geräte.

## <a name="create-a-device-profile-containing-device-restriction-settings"></a>Erstellen von Geräteprofilen mit Einstellungen für Geräteeinschränkungen

1. Melden Sie sich beim Azure-Portal an.
2. Wählen Sie **Weitere Dienste** > **Überwachung und Verwaltung** > **Intune** aus.
3. Wählen Sie auf dem Blatt **Intune** die Option **Gerätekonfiguration** aus.
2. Wählen Sie auf dem Blatt **Gerätekonfiguration** die Option **Verwalten** > **Profile** aus.
3. Wählen Sie auf dem Blatt „Profile“ die Option **Profil erstellen** aus.
4. Geben Sie auf dem Blatt **Profil erstellen** einen **Namen** und eine **Beschreibung** für das Gerätefunktionsprofil ein.
5. Wählen Sie in der Dropdownliste **Plattform** die Geräteplattform aus, auf die Sie die Einstellungen anwenden möchten. Derzeit können Sie eine der folgenden Plattformen für Gerätefunktionen auswählen:
    - **iOS**
    - **macOS**
6. Wählen Sie in der Dropdownliste **Profiltyp** die Option **Gerätefunktionen** aus. 
7. Die konfigurierbaren Einstellungen variieren je nach der ausgewählten Plattform. In den folgenden Themen finden Sie ausführliche Informationen zu den Einstellungen für die einzelnen Plattformen:
    - [AirPrint settings for iOS and MacOS](air-print-settings-ios-macos.md) (AirPrint-Einstellungen für iOS- und macOS-Geräte)
    - [AirPlay settings for iOS](airplay-settings-ios.md) (AirPlay-Einstellungen für iOS-Geräte)
    - [Home screen layout settings for iOS](home-screen-settings-ios.md) (Einstellungen des Startbildschirmlayouts für iOS-Geräte)
    - [App notification settings for iOS](app-notification-settings-ios.md) (App-Benachrichtigungseinstellungen für iOS-Geräte)
    - [Shared device configuration settings for iOS](shared-device-settings-ios.md) (Konfigurationseinstellungen für freigegebene iOS-Geräte)
    - [Konfigurieren von Intune für einmaliges Anmelden von iOS-Geräten](sso-ios.md)
    - [Web content filter settings for iOS](web-content-filter-settings-ios.md) (Filtereinstellungen für Webinhalte für iOS-Geräte)

8. Navigieren Sie anschließend zurück zum Blatt **Profil erstellen**, und klicken Sie auf **Erstellen**.

Das Profil wird erstellt und auf dem Blatt mit der Profilliste angezeigt.
Wenn Sie fortfahren und dieses Profil Gruppen zuweisen möchten, lesen Sie unter [Zuweisen von Geräteprofilen](device-profile-assign.md) nach.



