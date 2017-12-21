---
title: "Konfigurieren von Einstellungen für Geräteeinschränkungen in Intune"
titleSuffix: Azure portal
description: "In diesem Artikel erfahren Sie, wie Sie mit Intune Einstellungen und Funktionen auf Geräten, die Sie verwalten, konfigurieren."
keywords: 
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 04/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 42f9b104-c1f6-4dfc-8aa4-1d33e1eaf61f
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 0f51cb0ef85c772392458b8df328408657a84af8
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2017
---
# <a name="how-to-configure-device-restriction-settings-in-microsoft-intune"></a>So konfigurieren Sie Einstellungen für Geräteeinschränkungen in Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Mit Geräteeinschränkungen können Sie eine Vielzahl von Einstellungen und Features für eine ganze Reihe von Kategorien steuern, einschließlich Sicherheit, Browser, Hardware und Einstellungen zur Datenfreigabe. Sie könnten beispielsweise ein Geräteeinschränkungsprofil erstellen, das verhindert, dass Benutzer von iOS-Geräten auf die Kamera des Geräts zugreifen.

Anhand der Informationen in diesem Thema lernen Sie die Grundlagen zum Konfigurieren von Geräteeinschränkungsprofilen kennen. In den weiterführenden Themen zu den einzelnen Plattformen erfahren Sie etwas über Besonderheiten der jeweiligen Geräte.

So erstellen Sie ein Geräteprofil, das Einstellungen für Geräteeinschränkungen enthält:

1. Melden Sie sich beim Azure-Portal an.
2. Wählen Sie **Weitere Dienste** > **Überwachung und Verwaltung** > **Intune** aus.
3. Wählen Sie auf dem Blatt **Intune** die Option **Geräte konfigurieren** aus.
2. Wählen Sie auf dem Blatt **Gerätekonfiguration** die Option **Verwalten** > **Profile** aus.
3. Wählen Sie auf dem Blatt „Profile“ die Option **Profil erstellen** aus.
4. Geben Sie auf dem Blatt **Profil erstellen** einen **Namen** und eine **Beschreibung** für das Geräteeinschränkungsprofil ein.
5. Wählen Sie in der Dropdownliste **Plattform** die Geräteplattform aus, auf die Sie benutzerdefinierte Einstellungen anwenden möchten. Derzeit können Sie eine der folgenden Plattformen für die Einstellungen für Geräteeinschränkungen auswählen:
    - **Android**
    - **iOS**
    - **macOS**
    - **Windows Phone 8.1**
    - **Windows 8.1 und höher**
    - **Windows 10 und höher**
6. Wählen Sie in der Dropdownliste **Profiltyp** die Option **Geräteeinschränkungen** aus. Wenn Sie ein Geräteeinschränkungsprofil für Windows 10 Team-Geräte wie etwa ein Surface Hub erstellen möchten, wählen Sie **Geräteeinschränkungen (Windows 10 Team)** aus.
7. Die konfigurierbaren Einstellungen variieren je nach der ausgewählten Plattform. In den folgenden Themen finden Sie ausführliche Informationen zu den Einstellungen für die einzelnen Plattformen:
    - [Einstellungen für Android](device-restrictions-android.md)
    - [Einstellungen für iOS](device-restrictions-ios.md)
    - [Einstellungen für macOS](device-restrictions-macos.md)
    - [Einstellungen für Windows Phone 8.1](device-restrictions-windows-phone-8-1.md)
    - [Windows 8.1](device-restrictions-windows-8-1.md)
    - [Einstellungen für Windows 10](device-restrictions-windows-10.md)
    - [Einstellungen für Windows 10 Team](device-restrictions-windows-10-teams.md)
    - [Einstellungen für Android for Work](device-restrictions-android-for-work.md)
8. Navigieren Sie anschließend zurück zum Blatt **Profil erstellen**, und klicken Sie auf **Erstellen**.

Das Profil wird erstellt und auf dem Blatt mit der Profilliste angezeigt.
Wenn Sie fortfahren und dieses Profil Gruppen zuweisen möchten, lesen Sie unter [Zuweisen von Geräteprofilen](device-profile-assign.md) nach.

<!--  Removing image as part of design review; retaining source until we known the disposition.

## Example of device restriction settings

In this high-level example, you'll create a device restriction policy that blocks the use of the built-in camera app on Android devices.

![How to disable the camera on Android devices](./media/disable-android-camera.png)

-->