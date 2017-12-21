---
title: So konfigurieren Sie Intune-WLAN-Einstellungen
titleSuffix: Azure portal
description: "Erfahren Sie, wie Sie mit Intune WLAN-Einstellungen auf Geräten konfigurieren, die Sie verwalten."
keywords: 
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 06/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 1fadb488-9c6c-43c1-ba23-8c69db633b96
ms.reviewer: karanda
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: f42d12ddcfc0e2eef8d99102cebae460cdcb29bb
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2017
---
# <a name="how-to-configure-wi-fi-settings-in-microsoft-intune"></a>So konfigurieren Sie WLAN-Einstellungen in Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Verwenden Sie WLAN-Profile in Microsoft Intune, um Benutzern und Geräten in Ihrer Organisation Einstellungen für Drahtlosnetzwerke zuzuweisen. Wenn Sie ein WLAN-Profil zuweisen, erhalten Ihre Benutzer Zugriff auf Ihr Unternehmens-WLAN, ohne es selbst konfigurieren zu müssen.

Beispiel: Sie installieren ein neues WLAN mit dem Namen „Contoso Wi-Fi“ und möchten alle iOS-Geräte so einrichten, dass sie eine Verbindung mit diesem Netzwerk herstellen können. Gehen Sie dazu folgendermaßen vor:

1. Erstellen Sie ein WLAN-Profil mit den Einstellungen, die zum Verbinden mit dem Drahtlosnetzwerk „Contoso Wi-Fi“ erforderlich sind.
2. Weisen Sie das Profil einer Gruppe zu, die alle Benutzer von iOS-Geräten enthält.
3. Auf den Geräten der Benutzer erscheint das Netzwerk „Contoso Wi-Fi“ in der Liste der Drahtlosnetzwerke, und es kann bequem eine Verbindung mit diesem Netzwerk hergestellt werden.

WLAN-Profile unterstützen folgende Geräteplattformen:

- Android 4 und höher
- Android for Work
- iOS 8.0 und höher
- macOS (Mac OS X 10.9 und höher)

Auf Geräten mit Windows 8.1, Windows 10 und Windows 10 Mobile können Sie eine WLAN-Konfiguration importieren, die zuvor von einem anderen Gerät exportiert wurde.

Anhand der Informationen in diesem Thema lernen Sie die Grundlagen zum Konfigurieren von WLAN-Profilen kennen. In den weiterführenden Themen zu den einzelnen Plattformen erfahren Sie etwas über Besonderheiten der jeweiligen Geräte.

## <a name="create-a-device-profile-containing-wi-fi-settings"></a>Erstellen eines Geräteprofils mit WLAN-Einstellungen

1. Melden Sie sich beim Azure-Portal an.
2. Wählen Sie **Weitere Dienste** > **Überwachung und Verwaltung** > **Intune** aus.
3. Wählen Sie auf dem Blatt **Intune** die Option **Gerätekonfiguration** aus.
2. Wählen Sie auf dem Blatt **Gerätekonfiguration** die Option **Verwalten** > **Profile** aus.
3. Wählen Sie auf dem Blatt „Profile“ die Option **Profil erstellen** aus.
4. Geben Sie auf dem Blatt **Profil erstellen** einen **Namen** und eine **Beschreibung** für das WLAN-Profil ein.
5. Wählen Sie in der Dropdownliste **Plattform** die Geräteplattform aus, auf die Sie WLAN-Einstellungen anwenden möchten. Derzeit können Sie eine der folgenden Plattformen für die WLAN-Einstellungen auswählen:
    - **Android**
    - **Android for Work**
    - **iOS**
    - **macOS**
    - **Windows 8.1 und höher (Profil importieren)**
6. Wählen Sie in der Dropdownliste **Profiltyp** die Option **Basis-WLAN** oder **Unternehmens-WLAN** aus. Mithilfe von **Basis-WLAN** können Sie grundlegende Eigenschaften wie den Netzwerknamen und die SSID angeben. Mit **Unternehmens-WLAN** können Sie detailliertere Informationen angeben, z.B. das Extensible Authentication Protocol (EAP), sofern dieses in Ihrem WLAN verwendet wird. Mit **WLAN (Import)** (für Windows 8.1 und Windows 10) können Sie WLAN-Einstellungen als XML-Datei importieren, die Sie zuvor von einem anderen Gerät exportiert haben.
7. Die konfigurierbaren Einstellungen variieren je nach der ausgewählten Plattform. In den folgenden Themen finden Sie ausführliche Informationen zu den Einstellungen für die einzelnen Plattformen:
    - [Einstellungen für Android und Android for Work](wi-fi-settings-android.md)
    - [Einstellungen für iOS](wi-fi-settings-ios.md)
    - [Einstellungen für macOS](wi-fi-settings-macos.md)
    - [Einstellungen für Windows Phone 8.1](wi-fi-settings-import-windows-8-1.md)
8. Navigieren Sie anschließend zurück zum Blatt **Profil erstellen**, und klicken Sie auf **Erstellen**.

Das Profil wird erstellt und auf dem Blatt mit der Profilliste angezeigt.
Wenn Sie fortfahren und dieses Profil Gruppen zuweisen möchten, lesen Sie unter [Zuweisen von Geräteprofilen](device-profile-assign.md) nach.
