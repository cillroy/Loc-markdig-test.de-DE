---
title: "WLAN-Einstellungen für Android-Geräte in Intune"
titleSuffix: Azure portal
description: "Erfahren Sie mehr über die Intune-Einstellungen zum Konfigurieren von WLAN-Verbindungen auf Android und Android for Work-Geräten."
keywords: 
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 06/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 103e17a4-2993-4359-b340-73e2acf4cf7d
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: c74aa485618840176c7b88af5f123523b07c4480
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2017
---
# <a name="wi-fi-settings-for-android-and-android-for-work-devices-in-microsoft-intune"></a>WLAN-Einstellungen für Android- und Android for Work-Geräte in Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

## <a name="wi-fi-settings-for-basic-and-enterprise-profiles"></a>WLAN-Einstellungen für Basic und Enterprise-Profile

Die folgenden WLAN-Einstellungen sind für Android- und Android for Work-Geräte verfügbar:

- **Netzwerkname:** Geben Sie einen Namen für diese WLAN-Verbindung ein. Dies ist der Name, der Benutzern in der Liste der verfügbaren WLAN-Verbindungen auf ihren Geräten angezeigt wird.
- **SSID:** Abkürzung für Service Set Identifier. Dies ist der tatsächlich Name des Drahtlosnetzwerks, mit dem Geräte eine Verbindung herstellen. Den Benutzern werden jedoch nur die Netzwerknamen angezeigt, die Sie oben erstellt haben, wenn sie die Verbindung auswählen.
- **Automatisch verbinden:** Bei Aktivierung kann das Gerät jederzeit eine Verbindung herzustellen, wenn es sich im Bereich des Netzwerks befindet.
- **Ausgeblendetes Netzwerk:** Verhindert, dass dieses Netzwerk in der Liste der verfügbaren Netzwerke auf dem Gerät angezeigt wird.


## <a name="wi-fi-settings-for-enterprise-profiles-only"></a>WLAN-Einstellungen für Enterprise-Profile

- **EAP-Typ:** Wählen Sie den EAP-Typ (Extensible Authentication-Protokoll) zur Authentifizierung von gesicherten Drahtlosverbindungen aus:
    - **EAP-TLS**
    - **EAP-TTLS**
    - **PEAP**

### <a name="further-options-when-you-choose-an-eap-type"></a>Weitere Optionen bei der Auswahl eines EAP-Typs

#### <a name="server-trust"></a>Serververtrauensstellung



|Name der Einstellung|Weitere Informationen|Verwendungsgrund|
|-------------|---------------|-----------|
|**Zertifikatservername(n)**|Geben Sie einen oder mehrere allgemeine Namen an, die in den von der vertrauenswürdigen Zertifizierungsstelle (CA) ausgestellten Zertifikaten verwendet werden. Wenn Sie diese Informationen angeben, können Sie den dynamischen Vertrauensstellungsdialog umgehen, der auf Endbenutzergeräten bei der Verbindungsherstellung mit diesem WLAN angezeigt wird.|Der EAP-Typ ist **EAP-TLS** oder **EAP-TTLS**.|
|**Stammzertifikat zur Servervalidierung**|Wählen Sie das vertrauenswürdige Stammzertifikatprofil zur Authentifizierung der Verbindung aus. |Der EAP-Typ ist **EAP-TLS**, **EAP-TTLS** oder **PEAP**.|
|**Identitätsschutz (äußere Identität)**|Geben Sie den Text ein, der als Antwort auf eine EAP-Identity-Request gesendet werden soll. Dies kann ein beliebiger Text sein. Während der Authentifizierung wird zuerst diese anonyme Identität gesendet und anschließend die echte Kennung über einen sicheren Tunnel.|Der EAP-Typ ist **PEAP**.|


#### <a name="client-authentication"></a>Clientauthentifizierung


|Name der Einstellung|Weitere Informationen|Verwendungsgrund|
|----------|--------------|----------|
|**Clientzertifikat zur Clientauthentifizierung (Identitätszertifikat)**|Wählen Sie das SCEP- oder PKCS-Zertifikatprofil zur Authentifizierung der Verbindung aus.|Der EAP-Typ ist **EAP-TLS**.|
|**Authentifizierungsmethode**|Wählen Sie die Authentifizierungsmethode für die Verbindung aus:<br>- **Zertifikate** zur Auswahl von SCEP oder PKCS als Clientzertifikat, das als Identitätszertifikat dem Server vorgelegt wird<br><br>- **Benutzername und Kennwort** zur Angabe einer anderen Authentifizierungsmethode <br><br>Bei Auswahl von **Benutzername und Kennwort**, konfigurieren Sie noch Folgendes:<br><br>-  **Nicht-EAP-Methode (innere Identität)**. Wählen Sie anschließend aus, wie Sie die Verbindung authentifizieren möchten:<br>- **Keine**<br>- **Unverschlüsseltes Kennwort (PAP)**<br>- **Challenge Handshake Authentication-Protokoll (CHAP)**<br>- **Microsoft CHAP (MS-CHAP)**<br>- **Microsoft CHAP, Version 2 (MS-CHAP v2)**<br>Die verfügbaren Optionen hängen vom ausgewählten EAP-Typ ab.<br><br>**und**<br><br>- **Identitätsschutz aktivieren (äußere Identität)**. Geben Sie den Text ein, der als Antwort auf eine EAP-Identitätsanforderung gesendet werden soll. Dies kann ein beliebiger Text sein. Während der Authentifizierung wird zuerst diese anonyme Identität gesendet und anschließend die echte Kennung über einen sicheren Tunnel.|Der EAP-Typ ist **EAP-TTLS** oder **PEAP**.|
