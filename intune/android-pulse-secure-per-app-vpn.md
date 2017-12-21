---
title: "App-bezogenes VPN-Profile für Android – Pulse Secure"
titlesuffix: Azure portal
description: "Erfahren Sie, wie ein VPN-Profil pro App für Android-Geräte erstellt wird, die von Intune verwaltet werden.\""
keywords: 
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 06/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d035ebf5-85f4-4001-a249-75d24325061a
ms.reviewer: chrisbal
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 5319913c16710d9a2076e629d8ff57894f95f139
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2017
---
# <a name="use-a-microsoft-intune-custom-profile-to-create-a-per-app-vpn-profile-for-android-devices"></a>Verwenden eines benutzerdefinierten Microsoft Intune-Profils zum Erstellen eines VPN-Profils pro App für Android-Geräte

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Sie können ein App-bezogenes VPN-Profil für Android 5.0-Geräte oder höher erstellen, die von Intune verwaltet werden. Erstellen Sie zunächst ein VPN-Profil, das den Pulse Secure-Verbindungstyp verwendet. Erstellen Sie anschließend eine benutzerdefinierte Konfigurationsrichtlinie, die das VPN-Profil angegebenen Apps zuordnet.

Nachdem Sie die Richtlinie auf Ihrem Android-Gerät oder für Benutzergruppen zugewiesen haben, müssen Benutzer das Pulse Secure-VPN starten. Pulse Secure erlaubt es dann lediglich den angegebenen Apps, die offene VPN-Verbindung für ihren Datenverkehr zu nutzen.

> [!NOTE]
>
> Für dieses Profil wird nur der Verbindungstyp „Pulse Secure“ unterstützt.


## <a name="step-1-create-a-vpn-profile"></a>Schritt 1: Erstellen eines VPN-Profils


1. Melden Sie sich beim Azure-Portal an.
2. Wählen Sie **Weitere Dienste** > **Überwachung und Verwaltung** > **Intune** aus.
3. Wählen Sie auf dem Blatt **Intune** die Option **Gerätekonfiguration** aus.
2. Wählen Sie auf dem Blatt **Gerätekonfiguration** die Option **Verwalten** > **Profile** aus.
2. Wählen Sie auf dem Blatt mit der Profilliste die Option **Profil erstellen** aus.
3. Geben Sie auf dem Blatt **Profil erstellen** einen **Namen** und optional eine **Beschreibung** für das VPN-Profil ein.
4. Wählen Sie in der Dropdownliste **Plattform** die Option **Android** aus.
5. Wählen Sie in der Dropdownliste **Profiltyp** die Option **VPN** aus.
3. Wählen Sie **Einstellungen** > **Konfigurieren** aus, und konfigurieren Sie das VPN-Profil gemäß den Einstellungen in [Konfigurieren von VPN-Einstellungen](vpn-settings-configure.md) und [Intune-VPN-Einstellungen für Android-Geräte](vpn-settings-android.md).

Notieren Sie den Wert für **Verbindungsname**, den Sie beim Erstellen des VPN-Profils angegeben haben. Dieser Name wird im nächsten Schritt benötigt. Beispiel: **MeineApp-VPN-Profil**.

## <a name="step-2-create-a-custom-configuration-policy"></a>Schritt 2: Erstellen einer benutzerdefinierten Konfigurationsrichtlinie

1. Melden Sie sich beim Azure-Portal an.
2. Wählen Sie **Weitere Dienste** > **Überwachung und Verwaltung** > **Intune** aus.
3. Wählen Sie auf dem Blatt **Intune** die Option **Gerätekonfiguration** aus.
2. Wählen Sie auf dem Blatt **Gerätekonfiguration** die Option **Verwalten** > **Profile** aus.
3. Klicken Sie auf dem Blatt „Profile“ auf **Profil erstellen**.
4. Geben Sie auf dem Blatt **Profil erstellen** einen **Namen** und eine **Beschreibung** für das benutzerdefinierte Profil ein.
5. Wählen Sie in der Dropdownliste **Plattform** die Option **Android** aus.
6. Wählen Sie in der Dropdownliste **Profiltyp** die Option **Benutzerdefiniert** aus.
7. Wählen Sie **Einstellungen** > **Konfigurieren** aus.
3. Wählen Sie auf dem Blatt **Benutzerdefinierte OMA-URI-Einstellungen** die Option **Hinzufügen** aus.
    - Geben Sie einen Einstellungsnamen ein.
    - Geben Sie für **Datentyp** **Zeichenfolge** an.
    - Geben Sie für **OMA-URI** diese Zeichenfolge an: **./Vendor/MSFT/VPN/Profile/*Name*/PackageList**. *Name* ist der Name des VPN-Profils, den Sie in Schritt 1 notiert haben. Bei diesem Beispiel lautet die Zeichenfolge **./Vendor/MSFT/VPN/Profile/MyAppVpnProfile/PackageList**.
    - Erstellen Sie für **Wert** eine durch Semikolons getrennte Liste der Pakete, die dem Profil zugeordnet werden sollen. Wenn z.B. Excel und der Google-Browser Chrome die VPN-Verbindung verwenden sollen, geben Sie Folgendes ein: **com.microsoft.office.excel;com.android.chrome**.

![Beispiel einer benutzerdefinierten Richtlinie für ein App-bezogenes VPN für Android](./media/android_per_app_vpn_oma_uri.png)

### <a name="set-your-app-list-to-blacklist-or-whitelist-optional"></a>Festlegen, ob Ihre App-Liste eine Positivliste (Whitelist) oder eine Negativliste (Blacklist) sein soll (optional)
  Sie können eine Liste von Apps angeben, die die VPN-Verbindung *nicht* verwenden können, indem Sie den Wert **BLACKLIST** verwenden. Alle anderen Apps stellen über das VPN eine Verbindung her.
Alternativ können Sie den Wert **WHITELIST** verwenden, um eine Liste von Apps anzugeben, die die VPN-Verbindung verwenden *können*. Apps, die sich nicht auf der Liste befinden, stellen keine Verbindung über das VPN her.
  1.    Wählen Sie auf dem Blatt **Benutzerdefinierte OMA-URI-Einstellungen** die Option **Hinzufügen** aus.
  2.    Geben Sie einen Einstellungsnamen ein.
  3.    Geben Sie für **Datentyp** **Zeichenfolge** an.
  4.    Verwenden Sie für **OMA-URI** diese Zeichenfolge: **./Vendor/MSFT/VPN/Profile/*Name*/Mode**. *Name* ist der Name des VPN-Profils, den Sie in Schritt 1 notiert haben. Bei unserem Beispiel lautet die Zeichenfolge **./Vendor/MSFT/VPN/Profile/MeineApp-VPN-Profil/Mode**.
  5.    Geben Sie für **Wert** entweder **BLACKLIST** oder **WHITELIST** ein.



## <a name="step-3-assign-both-policies"></a>Schritt 3: Zuweisen beider Richtlinien

Verwenden Sie die Anweisungen in [Zuweisen von Geräteprofilen](device-profile-assign.md), um den erforderlichen Benutzern oder Geräten beide Profile zuzuweisen.
