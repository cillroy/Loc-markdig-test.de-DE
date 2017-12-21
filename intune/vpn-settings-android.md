---
title: "VPN-Einstellungen für Android-Geräte in Intune"
titlesuffix: Azure portal
description: "Erfahren Sie etwas über die Intune-Einstellungen, die Sie zum Konfigurieren von VPN-Verbindungen auf Android-Geräten verwenden können."
keywords: 
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 06/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 16c056ca-320e-4107-ad03-a0cf96c28885
ms.reviewer: karanda
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 455d8f83e04bf72938316b9511e4898df9652808
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2017
---
# <a name="vpn-settings-for-android-devices-in-microsoft-intune"></a>VPN-Einstellungen für Android-Geräte in Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Als Intune-Administrator können Sie VPN-Einstellungen für die folgenden Plattformen konfigurieren:

- [Android](#android-vpn-settings)
- [Android for Work](#android-for-work-vpn-settings)

Je nach den ausgewählten Einstellungen können nicht alle der unten aufgeführten Werte konfiguriert werden.

## <a name="android-vpn-settings"></a>Android-VPN-Einstellungen
**Verbindungsname:** Geben Sie einen Namen für diese Verbindung ein. Endbenutzern wird dieser Name angezeigt, wenn sie auf ihrem Gerät die Liste der verfügbaren VPN-Verbindungen durchsuchen.
- **IP-Adresse oder FQDN:** Geben Sie die IP-Adresse oder den vollqualifizierten Domänennamen des VPN-Servers an, mit dem Geräte eine Verbindung herstellen. Beispiele: **192.168.1.1**, **vpn.contoso.com**.
- **Authentifizierungsmethode:** Wählen Sie unter folgenden Optionen aus, wie sich Geräte beim VPN-Server authentifizieren:
    - **Zertifikate:** Wählen Sie ein zuvor erstelltes SCEP- oder PKCS-Zertifikatprofil zum Authentifizieren der Verbindung aus. Ausführliche Informationen zu Zertifikatprofilen finden Sie unter [Konfigurieren von Zertifikaten](certificates-configure.md).
    - **Benutzername und Kennwort:** Endbenutzer müssen einen Benutzernamen und ein Kennwort für die Anmeldung beim VPN-Server angeben.
- **Verbindungstyp:** Wählen Sie den VPN-Verbindungstyp in der folgenden Liste von Anbietern aus:
    - **Check Point Capsule VPN**
    - **Cisco AnyConnect**
    - **Dell SonicWALL Mobile Connect**
    - **F5 Edge Client**
    - **Pulse Secure**
    - **Citrix**

- **Fingerabdruck** (nur Check Point Capsule VPN): Geben Sie eine Zeichenfolge (z.B. „Contoso-Fingerabdruckcode“) an, mit der überprüft wird, ob der VPN-Server vertrauenswürdig ist. Ein Fingerabdruck kann an den Client gesendet werden, damit dieser weiß, dass alle Server vertrauenswürdig sind, die beim Verbinden den betreffenden Fingerabdruck vorweisen. Wenn das Gerät noch nicht über den Fingerabdruck verfügt, wird der Benutzer aufgefordert, dem VPN-Server zu vertrauen, mit dem eine Verbindung hergestellt wird, während der Fingerabdruck angezeigt wird. (Der Benutzer überprüft den Fingerabdruck manuell und klickt auf „Vertrauen“, um die Verbindung herzustellen.)
- **Geben Sie Schlüssel-Wert-Paare für die Citrix-VPN-Attribute ein** (nur Citrix): Geben Sie von Citrix bereitgestellte Schlüssel-Wert-Paare ein, um die Eigenschaften der VPN-Verbindung zu konfigurieren.

## <a name="android-for-work-vpn-settings"></a>VPN-Einstellungen für Android for Work

**Verbindungsname:** Geben Sie einen Namen für diese Verbindung ein. Endbenutzern wird dieser Name angezeigt, wenn sie auf ihrem Gerät die Liste der verfügbaren VPN-Verbindungen durchsuchen.
- **IP-Adresse oder FQDN:** Geben Sie die IP-Adresse oder den vollqualifizierten Domänennamen des VPN-Servers an, mit dem Geräte eine Verbindung herstellen. Beispiele: **192.168.1.1**, **vpn.contoso.com**.
- **Authentifizierungsmethode:** Wählen Sie unter folgenden Optionen aus, wie sich Geräte beim VPN-Server authentifizieren:
    - **Zertifikate:** Wählen Sie ein zuvor erstelltes SCEP- oder PKCS-Zertifikatprofil zum Authentifizieren der Verbindung aus. Ausführliche Informationen zu Zertifikatprofilen finden Sie unter [Konfigurieren von Zertifikaten](certificates-configure.md).
    - **Benutzername und Kennwort:** Endbenutzer müssen einen Benutzernamen und ein Kennwort für die Anmeldung beim VPN-Server angeben.
- **Verbindungstyp:** Wählen Sie den VPN-Verbindungstyp in der folgenden Liste von Anbietern aus:
    - **Check Point Capsule VPN**
    - **Cisco AnyConnect**
    - **Dell SonicWALL Mobile Connect**
    - **F5 Edge Client**
    - **Pulse Secure**

- **Getrenntes Tunneln:** Aktivieren Sie diese Einstellung, damit bestimmter Webdatenverkehr die VPN-Verbindung verwenden kann, wenn das VPN aktiv ist, während der verbleibende Datenverkehr das Internet verwendet. Deaktivieren Sie diese Einstellung, wenn der gesamte Datenverkehr das VPN verwenden soll, wenn es aktiv ist.
