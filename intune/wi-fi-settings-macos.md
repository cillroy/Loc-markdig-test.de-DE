---
title: "WLAN-Einstellungen für macOS-Geräte in Intune"
titleSuffix: Azure portal
description: "Erfahren Sie mehr über die Intune-Einstellungen, die Sie zum Konfigurieren von WLAN-Verbindungen auf macOS-Geräten verwenden können."
keywords: 
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 322a38d5-21f5-48ee-bc59-0a4f9da78d38
ms.reviewer: karanda
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 7f6d2bb745bf8502a7f466e44bebf925f05db9c6
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2018
---
# <a name="wi-fi-settings-for-macos-devices-in-microsoft-intune"></a>WLAN-Einstellungen für macOS-Geräte in Microsoft Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

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


|                                     Name der Einstellung                                     |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         Weitere Informationen                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |                            Verwendungsgrund                            |
|--------------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|----------------------------------------------------------------|
| <strong>Clientzertifikat zur Clientauthentifizierung (Identitätszertifikat)</strong> |                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         Wählen Sie das SCEP- oder PKCS-Zertifikatprofil zur Authentifizierung der Verbindung aus.                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                          |              Der EAP-Typ ist <strong>EAP-TLS</strong>.              |
|                        <strong>Authentifizierungsmethode</strong>                        | Wählen Sie die Authentifizierungsmethode für die Verbindung aus:<br>- <strong>Zertifikate</strong> zur Auswahl von SCEP oder PKCS als Clientzertifikat, das als Identitätszertifikat dem Server vorgelegt wird<br><br>- <strong>Benutzername und Kennwort</strong> zur Angabe einer anderen Authentifizierungsmethode <br><br>Bei Auswahl von <strong>Benutzername und Kennwort</strong>, konfigurieren Sie noch Folgendes:<br><br>-  <strong>Nicht-EAP-Methode (innere Identität)</strong>. Wählen Sie anschließend aus, wie Sie die Verbindung authentifizieren möchten:<br>- <strong>Keine</strong><br>- <strong>Unverschlüsseltes Kennwort (PAP)</strong><br>- <strong>Challenge Handshake Authentication-Protokoll (CHAP)</strong><br>- <strong>Microsoft CHAP (MS-CHAP)</strong><br>- <strong>Microsoft CHAP, Version 2 (MS-CHAP v2)</strong><br>Die verfügbaren Optionen hängen vom ausgewählten EAP-Typ ab.<br><br><strong>und</strong><br><br>- <strong>Identitätsschutz aktivieren (äußere Identität)</strong>. Geben Sie den Text ein, der als Antwort auf eine EAP-Identitätsanforderung gesendet werden soll. Dies kann ein beliebiger Text sein. Während der Authentifizierung wird zuerst diese anonyme Identität gesendet und anschließend die echte Kennung über einen sicheren Tunnel. | Der EAP-Typ ist <strong>EAP-TTLS</strong> oder <strong>PEAP</strong>. |

