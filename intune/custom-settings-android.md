---
title: "Benutzerdefinierte Intune-Einstellungen für Android-Geräte"
titleSuffix: Azure portal
description: "Erfahren Sie etwas über die Einstellungen, die Sie in einem benutzerdefinierten Android-Profil verwenden können.\""
keywords: 
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 09/18/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 494b3892-916e-4b40-9b67-61adec889bdf
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 0bbc5c82c349c8a3d19eeb4433763b53e7485bc0
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2017
---
# <a name="custom-settings-for-android-devices-in-microsoft-intune"></a>Benutzerdefinierte Einstellungen für Android-Geräte in Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Weisen Sie mithilfe des **benutzerdefinierten** Profils für Android von Microsoft Intune die OMA-URI-Einstellungen zu, um Features auf Android-Geräten zu steuern. Dies sind die Standardeinstellungen, die viele Hersteller von mobilen Geräten verwenden, um Gerätefunktionen zu steuern.

Diese Funktion soll es Ihnen ermöglichen, die folgenden Android-Einstellungen zuzuweisen, die nicht mit Intune-Richtlinien konfigurierbar sind.

- [Verwenden eines benutzerdefinierten Geräteprofils von Microsoft Intune zum Erstellen eines WLAN-Profils über einen vorinstallierten Schlüssel](/intune/wi-fi-profile-shared-key)
- [Verwenden eines benutzerdefinierten Microsoft Intune-Profils zum Erstellen eines VPN-Profils pro App für Android-Geräte](/intune/android-pulse-secure-per-app-vpn)
- [Verwenden von benutzerdefinierten Richtlinien zum Zulassen und Blockieren von Apps für Samsung KNOX Standardgeräte in Microsoft Intune](/intune/samsung-knox-apps-allow-block)

>[!IMPORTANT]
>Nur die oben aufgeführten Einstellungen können derzeit von diesem Profiltyp konfiguriert werden. Android-Geräte stellen keine vollständige Liste der OMA-URI-Einstellungen zur Verfügung, die Sie konfigurieren können. Wenn Sie weitere Einstellungen hinzugefügt haben möchten, fordern Sie diese auf der [Intune Uservoice-Website](https://microsoftintune.uservoice.com/forums/291681-ideas) an.

## <a name="custom-profile-settings-for-android-devices"></a>Benutzerdefinierte Profileinstellungen für Android-Geräte

1. Anweisungen zu den ersten Schritten finden Sie unter [Konfigurieren von benutzerdefinierten Geräteeinstellungen in Microsoft Intune](custom-settings-configure.md).
2. Wählen Sie auf dem Blatt **Profil erstellen** die Option **Einstellungen** aus, um eine oder mehrere OMA-URI-Einstellungen hinzufügen.
3. Konfigurieren Sie auf dem Blatt **Zeile bearbeiten** die folgenden Werte für jede Einstellung:
    - **Name:** Geben Sie einen eindeutigen Namen für die OMA-URI-Einstellung ein, damit Sie sie in der Liste der Einstellungen einfacher identifizieren können.
    - **Beschreibung:** Geben Sie eine Beschreibung ein, die eine Übersicht über die Einstellung bietet, und andere relevante Informationen, die Ihnen die Suche danach erleichtern.
    - **Datentyp:** Wählen Sie den Datentyp aus, in dem Sie diese OMA-URI-Einstellung angeben. Wählen Sie aus **Zeichenfolge**, **Zeichenfolge (XML)**, **Datum und Uhrzeit**, **ganze Zahl**, **Gleitkomma** oder **Boolesch** aus.
    - **OMA-URI:** Geben Sie den OMA-URI an, für den Sie eine Einstellung bereitstellen möchten.
    - **Wert:** Geben Sie den gewünschten Wert an, der dem von Ihnen eingegebenen OMA-URI zugeordnet werden soll.
4. Klicken Sie abschließend auf **OK**, und fahren Sie bei Bedarf mit dem Hinzufügen weiterer Einstellungen fort.

## <a name="next-steps"></a>Nächste Schritte

Wenn Sie die Einstellungen abschließen, wird das Profil erstellt und auf dem Blatt mit der Profilliste angezeigt. Wenn Sie fortfahren und dieses Profil Gruppen zuweisen möchten, lesen Sie unter [Zuweisen von Geräteprofilen](device-profile-assign.md) nach.




