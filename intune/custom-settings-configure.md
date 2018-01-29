---
title: "Konfigurieren von benutzerdefinierten Intune-Geräteeinstellungen"
titleSuffix: Azure portal
description: "Erfahren Sie, wie Sie mit Intune benutzerdefinierte Einstellungen auf Geräten konfigurieren, die Sie verwalten.\""
keywords: 
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 06/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 42f9b104-c1f6-4dfc-8aa4-1d33e1eaf61f
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: d3b44cb606f0764fb655651a441889862fcbbe62
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2018
---
# <a name="how-to-configure-custom-device-settings-in-microsoft-intune"></a>Konfigurieren von benutzerdefinierten Geräteeinstellungen in Microsoft Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

## <a name="when-to-use-custom-settings"></a>Verwenden von benutzerdefinierten Einstellungen

Benutzerdefinierte Geräteeinstellungen können nützlich sein, wenn Intune nicht über die Einstellungen verfügt, die Sie konfigurieren möchten, diese aber für andere Geräteprofile verfügbar sind.
Benutzerdefinierte Einstellungen werden für jede Plattform anders konfiguriert. Bei Android- und Windows-Geräten können Sie beispielsweise OMA-URI-Werte (Open Mobile Alliance Uniform Resource Identifier) zum Steuern von Features auf Geräten angeben. Auf Apple-Geräten können Sie eine Datei importieren, die Sie mit [Apple Configurator](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12) erstellt haben.

Anhand der Informationen in diesem Thema lernen Sie die Grundlagen zum Konfigurieren von Profilen mit benutzerdefinierten Einstellungen kennen. In den weiterführenden Themen zu den einzelnen Plattformen erfahren Sie etwas über Besonderheiten der jeweiligen Geräte.

## <a name="create-a-device-profile-containing-custom-settings"></a>Erstellen eines Geräteprofils mit benutzerdefinierten Einstellungen

1. Melden Sie sich beim Azure-Portal an.
2. Wählen Sie **Weitere Dienste** > **Überwachung und Verwaltung** > **Intune** aus.
3. Wählen Sie auf dem Blatt **Intune** die Option **Gerätekonfiguration** aus.
2. Wählen Sie auf dem Blatt **Gerätekonfiguration** die Option **Verwalten** > **Profile** aus.
3. Wählen Sie auf dem Blatt „Profile“ die Option **Profil erstellen** aus.
4. Geben Sie auf dem Blatt **Profil erstellen** einen **Namen** und eine **Beschreibung** für das benutzerdefinierte Profil ein.
5. Wählen Sie in der Dropdownliste **Plattform** die Geräteplattform aus, auf die Sie benutzerdefinierte Einstellungen anwenden möchten. Derzeit können Sie eine der folgenden Plattformen für die benutzerdefinierte Geräteeinstellungen auswählen:
    - **Android**
    - **iOS**
    - **macOS**
    - **Windows Phone 8.1**
    - **Windows 10 und höher**
6. Wählen Sie in der Dropdownliste **Profiltyp** die Option **Benutzerdefiniert** aus.
7. Die konfigurierbaren Einstellungen variieren je nach der ausgewählten Plattform. In den folgenden Themen finden Sie ausführliche Informationen zu den Einstellungen für die einzelnen Plattformen:
    - [Einstellungen für Android](custom-settings-android.md)
    - [Einstellungen für iOS](custom-settings-ios.md)
    - [Einstellungen für macOS](custom-settings-macos.md)
    - [Einstellungen für Windows Phone 8.1](custom-settings-windows-phone-8-1.md)
    - [Einstellungen für Windows 10](custom-settings-windows-10.md)
    - [Einstellungen für Android for Work](custom-settings-android-for-work.md)
8. Navigieren Sie anschließend zurück zum Blatt **Profil erstellen**, und klicken Sie auf **Erstellen**.

Das Profil wird erstellt und auf dem Blatt mit der Profilliste angezeigt.
Wenn Sie fortfahren und dieses Profil Gruppen zuweisen möchten, lesen Sie unter [Zuweisen von Geräteprofilen](device-profile-assign.md) nach.
