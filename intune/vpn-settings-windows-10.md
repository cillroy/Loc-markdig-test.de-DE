---
title: "VPN-Einstellungen für Windows 10-Geräte in Intune"
titlesuffix: Azure portal
description: "Erfahren Sie etwas über die Intune-Einstellungen, die Sie zum Konfigurieren von VPN-Verbindungen auf Windows 10-Geräten verwenden können.\""
keywords: 
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 10/20/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 495e4ed6-b2ef-47cc-a110-13fa9b5f85a6
ms.reviewer: karanda
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: ced6a9620d0f4f12aba1d329cbf22f6b17622ae7
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2017
---
# <a name="vpn-settings-for-windows-10-devices-in-microsoft-intune"></a>VPN-Einstellungen für Windows 10-Geräte in Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Je nach den ausgewählten Einstellungen können nicht alle Werte in der folgenden Liste konfiguriert werden.


## <a name="base-vpn-settings"></a>Grundlegende VPN-Einstellungen


- **Verbindungsname:** Geben Sie einen Namen für diese Verbindung ein. Endbenutzern wird dieser Name angezeigt, wenn sie auf ihrem Gerät die Liste der verfügbaren VPN-Verbindungen durchsuchen.
- **Server:** Fügen Sie einen oder mehrere VPN-Server hinzu, mit denen Geräte eine Verbindung herstellen.
    - **Hinzufügen:** öffnet das Blatt **Zeile hinzufügen**, auf dem Sie die folgende Informationen angeben können:
        - **Beschreibung:** Geben Sie einen beschreibenden Namen für den Server ein, z.B. **Contoso-VPN-Server**.
        - **IP-Adresse oder FQDN:** Geben Sie die IP-Adresse oder den vollqualifizierten Domänennamen des VPN-Servers an, mit dem Geräte eine Verbindung herstellen. Beispiele: **192.168.1.1**, **vpn.contoso.com**.
        - **Standardserver:** aktiviert diesen Server als Standardserver, über den Geräte die Verbindung herstellen. Achten Sie darauf, nur einen Server als Standard festzulegen.
    - **Importieren:** Suchen Sie nach einer Datei, die eine durch Trennzeichen getrennte Liste von Servern im Format „Beschreibung, IP-Adresse oder FQDN, Standardserver“ enthält. Wählen Sie **OK** aus, um diese in die Liste **Server** zu importieren.
    - **Exportieren:** exportiert die Liste der Server in eine CSV-Datei (Comma-Separated Values, durch Trennzeichen getrennte Werte).

**Verbindungstyp:** Wählen Sie den VPN-Verbindungstyp in der folgenden Liste von Anbietern aus:
- **Automatisch**
- **Check Point Capsule VPN**
- **Citrix-VPN**
- **Dell SonicWALL Mobile Connect**
- **F5 Edge Client**
- **IKEv2**
- **L2TP**
- **PPTP**
- **Pulse Secure**


**Anmeldegruppe oder -domäne** (nur Dell SonicWALL Mobile Connect): Geben Sie den Namen der Anmeldegruppe oder -domäne an, mit der Sie eine Verbindung herstellen möchten.

**Benutzerdefiniertes XML**/**EAP-XML:** Geben Sie benutzerdefinierte XML-Befehle zum Konfigurieren der VPN-Verbindung an.

**Beispiel für Pulse Secure:**

```
    <pulse-schema><isSingleSignOnCredential>true</isSingleSignOnCredential></pulse-schema>
```

**Beispiel für CheckPoint Mobile VPN:**

```
    <CheckPointVPN port="443" name="CheckPointSelfhost" sso="true" debug="3" />
```

**Beispiel für Dell SonicWALL Mobile Connect:**

```
    <MobileConnect><Compression>false</Compression><debugLogging>True</debugLogging><packetCapture>False</packetCapture></MobileConnect>
```

**Beispiel für F5 Edge Client:**

```
    <f5-vpn-conf><single-sign-on-credential /></f5-vpn-conf>
```

Weitere Informationen zum Erstellen von benutzerdefinierten XML-Befehlen finden Sie in der VPN-Dokumentation des jeweiligen Herstellers.

**Tunneling teilen** - **Aktivieren** oder **deaktivieren** Sie diese Option, mit der Geräte anhand des Datenverkehrs selbst entscheiden können, welche Verbindung verwendet werden soll. Beispiel: Ein Benutzer in einem Hotel verwendet die VPN-Verbindung zum Zugreifen auf Arbeitsdateien, jedoch das Standardnetzwerk des Hotels für normales Webbrowsen.
- **Tunnelingrouten für diese VPN-Verbindung teilen:** Fügen Sie optionale Routen für VPN-Drittanbieter hinzu. Geben Sie jedes Mal ein Zielpräfix und eine Präfixgröße für an.

## <a name="apps-and-traffic-rules"></a>Regeln für Apps und Datenverkehr

**VPN-Verbindung auf diese Apps beschränken:** Aktivieren Sie diese Option, wenn nur die angegebenen Apps die VPN-Verbindung verwenden sollen.
**Zugeordnete Apps:** Stellen Sie eine Liste von Apps bereit, die automatisch die VPN-Verbindung verwenden. Der Typ der App bestimmt den App-Bezeichner. Stellen Sie für eine universelle App den Paketfamiliennamen bereit. Stellen Sie für eine Desktop-App den Dateipfad der App bereit.

>[!IMPORTANT]
>Es wird empfohlen, alle Listen mit Apps zu schützen, die Sie für die Verwendung in der Konfiguration eines App-bezogenen VPN zusammenstellen. Wenn ein nicht autorisierter Benutzer die Liste ändert und Sie sie in die Liste der Apps für App-bezogenes VPN importieren, autorisieren Sie möglicherweise den VPN-Zugriff auf Apps, auf die nicht zugegriffen werden soll. Eine Möglichkeit, App-Listen zu schützen, ist die Verwendung einer Zugriffssteuerungsliste (Access Control List, ACL).

**Regeln für den Netzwerkdatenverkehr für diese VPN-Verbindung:** Wählen Sie die Protokolle, die lokalen und Remoteports sowie die Adressbereiche aus, die für die VPN-Verbindung aktiviert werden sollen. Wenn Sie keine Regel für den Netzwerkdatenverkehr erstellen, werden alle Protokolle, Ports und Adressbereiche aktiviert. Nachdem Sie eine Regel erstellt haben, werden nur die in dieser Regel festgelegten Protokolle, Ports und Adressbereiche von der VPN-Verbindung verwendet.


## <a name="conditional-access"></a>Bedingter Zugriff

**Bedingter Zugriff für diese VPN-Verbindung**: Aktiviert den Gerätekompatibilitätsfluss vom Client. Wenn aktiviert, versucht der VPN-Client, mit Azure AD zu kommunizieren, um ein Zertifikat für die Authentifizierung abzurufen. Der VPN sollte für die Zertifikatauthentifizierung eingerichtet sein, und der VPN-Server muss dem Server vertrauen, der von Azure Active Directory zurückgegeben wird.

**Einmaliges Anmelden (Single Sign-On, SSO) mit alternativem Zertifikat**: Verwenden Sie aus Gründen der Gerätekonformität ein anderes Zertifikat als das VPN-Authentifizierungszertifikat für die Kerberos-Authentifizierung. Geben Sie das Zertifikat mit den folgenden Einstellungen an: 

- **Erweiterte Schlüsselverwendung:** Name der erweiterten Schlüsselverwendung (Extended Key Usage, EKU)
- **Objektbezeichner:** Objektbezeichner für EKU
- **Ausstellerhash:** Fingerabdruck des SSO-Zertifikats

## <a name="dns-settings"></a>DNS-Einstellungen

**DNS-Namen und -Server für diese VPN-Verbindung:** Wählen Sie die DNS-Server aus, die von der VPN-Verbindung verwendet werden, nachdem die Verbindung hergestellt wurde.
Geben Sie für jeden Server Folgendes an:
- **DNS-Name**
- **DNS-Server**
- **Proxy**

## <a name="proxy-settings"></a>Proxyeinstellungen

- **Proxyeinstellungen automatisch erkennen:** Wenn der VPN-Server einen Proxyserver für die Verbindung erfordert, geben Sie an, ob Geräte die Verbindungseinstellungen automatisch erkennen können sollen. Weitere Informationen finden Sie in der Windows Server-Dokumentation.
- **Automatisches Konfigurationsskript:** Verwenden Sie eine Datei zum Konfigurieren des Proxyservers. Geben Sie die **Proxyserver-URL** ein (z.B. **http://proxy.contoso.com**), unter der die Konfigurationsdatei zu finden ist.
- **Proxyserver verwenden:** Aktivieren Sie diese Option, wenn Sie die Proxyeinstellungen für den Server manuell eingeben möchten.
    - **Adresse:** Geben Sie die Adresse des Proxyservers (als IP-Adresse) ein.
    - **Portnummer:** Geben Sie die Portnummer ein, die dem Proxyserver zugeordnet ist.
- **Proxy für lokale Adressen umgehen:** Wenn der VPN-Server einen Proxyserver für die Verbindung erfordert, aktivieren Sie diese Option, wenn der Proxyserver für von Ihnen angegebene lokale Adressen nicht verwendet werden soll. Weitere Informationen finden Sie in der Windows Server-Dokumentation.
