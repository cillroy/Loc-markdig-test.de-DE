---
title: "WLAN-Einstellungen für iOS-Geräte in Intune"
titleSuffix: Azure portal
description: "Erfahren Sie mehr über die Intune-Einstellungen, die Sie zum Konfigurieren von WLAN-Verbindungen auf iOS-Geräten verwenden können."
keywords: 
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 89229a5e-3421-4221-a62f-fa800620cc0d
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: da4d6cf5c9863e2c471c3e6d3b119dce614528ce
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2017
---
# <a name="wi-fi-settings-for-ios-devices-in-microsoft-intune"></a>WLAN-Einstellungen für iOS-Geräte in Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]



## <a name="wi-fi-settings-for-basic-and-enterprise-profiles"></a>WLAN-Einstellungen für Basic und Enterprise-Profile

- **Netzwerkname:** Geben Sie einen Namen für diese WLAN-Verbindung ein. Dies ist der Name, der Benutzern in der Liste der verfügbaren WLAN-Verbindungen auf ihren Geräten angezeigt wird.
- **SSID:** Abkürzung für Service Set Identifier. Dies ist der tatsächlich Name des Drahtlosnetzwerks, mit dem Geräte eine Verbindung herstellen. Den Benutzern werden jedoch nur die Netzwerknamen angezeigt, die Sie oben erstellt haben, wenn sie die Verbindung auswählen.
- **Automatisch verbinden:** Bei Aktivierung kann das Gerät jederzeit eine Verbindung herzustellen, wenn es sich im Bereich des Netzwerks befindet.
- **Ausgeblendetes Netzwerk:** Verhindert, dass dieses Netzwerk in der Liste der verfügbaren Netzwerke auf dem Gerät angezeigt wird.
- **Proxyeinstellungen:** Wählen Sie aus Folgendem aus:
    - **Keine:** Es werden keine Proxyeinstellungen konfiguriert.
    - **Manuel:** Geben Sie die **Proxyserveradresse** (als IP-Adresse) und die zugehörige **Portnummer** ein.
    - **Automatisch:** Verwenden Sie eine Konfigurationsdatei, um den Proxyserver zu konfigurieren. Geben Sie die **Proxyserver-URL** ein (z.B. **http://proxy.contoso.com**), unter der die Konfigurationsdatei zu finden ist.

## <a name="wi-fi-settings-for-basic-profiles-only"></a>WLAN-Einstellungen für Basic-Profile

- **Sicherheitstyp:** Wählen Sie das Sicherheitsprotokoll zur Authentifizierung mit dem WLAN aus:
    - **Offen (keine Authentifizierung):** Verwenden Sie diese Option nur, wenn das Netzwerk nicht gesichert ist.
    - **WPA/WPA2 – Privat**
    - **Datenverschlüsselung**

## <a name="wi-fi-settings-for-enterprise-profiles-only"></a>WLAN-Einstellungen für Enterprise-Profile

- **EAP-Typ:** Wählen Sie den EAP-Typ (Extensible Authentication-Protokoll) zur Authentifizierung von gesicherten Drahtlosverbindungen aus:
    - **EAP-FAST**
    - **EAP-SIM**
    - **EAP-TLS**
    - **EAP-TTLS**
    - **LEAP**
    - **PEAP**

### <a name="further-options-when-you-choose-an-eap-type"></a>Weitere Optionen bei der Auswahl eines EAP-Typs


|Name der Einstellung|Weitere Informationen|Verwendungsgrund|
|--------------|-------------|----------|
|**PAC-Einstellungen (Protected Access Credential)**|Wählen Sie die Verwendung von geschützten Zugriffsanmeldeinformationen zum Herstellen eines authentifizierten Tunnels zwischen dem Client und dem Authentifizierungsserver. Auswahlmöglichkeiten:<br>- **PAC verwenden:** Verwenden Sie eine vorhandene PAC-Datei, sofern vorhanden.<br>- **PAC verwenden und bereitstellen:** Stellen Sie die PAC-Datei auf Ihren Geräten bereit.<br>- **PAC anonym verwenden und bereitstellen:** Stellen Sie die PAC-Datei auf Ihren Geräten bereit, und stellen Sie die Bereitstellung ohne Authentifizierung des Servers sicher.|Der EAP-Typ ist **EAP-FAST**.|

#### <a name="server-trust"></a>Serververtrauensstellung


|Name der Einstellung|Weitere Informationen|Verwendungsgrund|
|--------------|-------------|----------|
|**Zertifikatservername(n)**|Geben Sie einen oder mehrere allgemeine Namen an, die in den von der vertrauenswürdigen Zertifizierungsstelle (CA) ausgestellten Zertifikaten verwendet werden. Wenn Sie diese Informationen angeben, können Sie den dynamischen Vertrauensstellungsdialog umgehen, der auf Endbenutzergeräten bei der Verbindungsherstellung mit diesem WLAN angezeigt wird.|Der EAP-Typ ist **EAP-TLS**, **EAP-TTLS** oder **PEAP**.|
|**Stammzertifikat zur Servervalidierung**|Wählen Sie das vertrauenswürdige Stammzertifikatprofil zur Authentifizierung der Verbindung aus. |Der EAP-Typ ist **EAP-TLS**, **EAP-TTLS** oder **PEAP**.|
|**Identitätsschutz (äußere Identität)**|Geben Sie den Text ein, der als Antwort auf eine EAP-Identity-Request gesendet werden soll. Dies kann ein beliebiger Text sein. Während der Authentifizierung wird zuerst diese anonyme Identität gesendet und anschließend die echte Kennung über einen sicheren Tunnel.|Der EAP-Typ ist **PEAP**.|


#### <a name="client-authentication"></a>Clientauthentifizierung


|Name der Einstellung|Weitere Informationen|Verwendungsgrund|
|--------------|-------------|----------|
|**Clientzertifikat zur Clientauthentifizierung (Identitätszertifikat)**|Wählen Sie das SCEP- oder PKCS-Zertifikatprofil zur Authentifizierung der Verbindung aus.|Der EAP-Typ ist **EAP-TLS**.|
|**Authentifizierungsmethode**|Wählen Sie die Authentifizierungsmethode für die Verbindung aus:<br>- **Zertifikate** zur Auswahl von SCEP oder PKCS als Clientzertifikat, das als Identitätszertifikat dem Server vorgelegt wird<br><br>- **Benutzername und Kennwort** zur Angabe einer anderen Authentifizierungsmethode <br><br>Bei Auswahl von **Benutzername und Kennwort**, konfigurieren Sie noch Folgendes:<br><br>-  **Nicht-EAP-Methode (innere Identität)**. Wählen Sie anschließend aus, wie Sie die Verbindung authentifizieren möchten:<br>- **Keine**<br>- **Unverschlüsseltes Kennwort (PAP)**<br>- **Challenge Handshake Authentication-Protokoll (CHAP)**<br>- **Microsoft CHAP (MS-CHAP)**<br>- **Microsoft CHAP, Version 2 (MS-CHAP v2)**<br>Die verfügbaren Optionen hängen vom ausgewählten EAP-Typ ab.<br><br>**und**<br><br>- **Identitätsschutz aktivieren (äußere Identität)**. Geben Sie den Text ein, der als Antwort auf eine EAP-Identitätsanforderung gesendet werden soll. Dies kann ein beliebiger Text sein. Während der Authentifizierung wird zuerst diese anonyme Identität gesendet und anschließend die echte Kennung über einen sicheren Tunnel.|Der EAP-Typ ist **EAP-TTLS** oder *
