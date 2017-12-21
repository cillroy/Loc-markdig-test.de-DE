---
title: "Benutzerdefinierte Einstellungen für macOS-Geräte"
titleSuffix: Azure portal
description: "Erfahren Sie etwas über die Einstellungen, die Sie in einem benutzerdefinierten macOS-Profil verwenden können.\""
keywords: 
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 05/04/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 68100ea5-7d9b-4c0b-8df7-b9a24b2442c8
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: e2c3fc3f95fb1f3f1bfea8b3b151ff774d6c2b46
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2017
---
# <a name="custom-settings-for-macos-devices-in-microsoft-intune"></a>Benutzerdefinierte Einstellungen für macOS-Geräte in Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Verwenden Sie das benutzerdefinierte macOS-Profil von Microsoft Intune, um macOS-Geräten Einstellungen zuzuweisen, die Sie mit dem [Apple Configurator-Tool](https://itunes.apple.com/app/apple-configurator-2/id1037126344?mt=12) erstellt haben. Mit diesem Tool können Sie zahlreiche Einstellungen zur Betriebssteuerung dieser Geräte erstellen und in ein Konfigurationsprofil exportieren. Sie können dieses Konfigurationsprofil anschließend in ein benutzerdefiniertes macOS-Profil von Intune importieren und die Einstellungen Benutzern und Geräten in Ihrer Organisation zuweisen.

Diese Funktion ermöglicht die Zuweisung von macOS-Einstellungen, die nicht mit anderen Intune-Profiltypen konfigurierbar sind.


1. Anweisungen zu den ersten Schritten finden Sie unter [Konfigurieren von benutzerdefinierten Geräteeinstellungen in Microsoft Intune](custom-settings-configure.md).
2. Geben Sie auf dem Blatt **Profil erstellen** Folgendes an:

- **Name des benutzerdefinierten Konfigurationsprofils:** Geben Sie einen Namen für die Richtlinie an, der auf dem Gerät und in Intune-Status angezeigt wird.
- **Konfigurationsprofildatei:** Suchen Sie das mit Apple Configurator erstellte Konfigurationsprofil.
Stellen Sie sicher, dass die Einstellungen, die Sie aus dem Apple Configurator-Tool exportieren, mit der macOS-Version auf den Geräten kompatibel sind, denen Sie die benutzerdefinierte macOS-Richtlinie zuweisen. Um Informationen zum Korrigieren inkompatibler Einstellungen zu erhalten, suchen Sie auf der [Apple Developer-Website](https://developer.apple.com/) nach der **Referenz zu Konfigurationsprofilen** und der **Referenz zum Protokoll für die Verwaltung mobiler Geräte**.

Die importierte Datei wird im Bereich **Dateiinhalt** des Blatts angezeigt.
