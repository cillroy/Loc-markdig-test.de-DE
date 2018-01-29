---
title: "App-Benachrichtigungseinstellungen für iOS-Geräte in Intune"
titlesuffix: Azure portal
description: "Erfahren Sie mehr über die Einstellungen zur Steuerung von Benachrichtigungen von Apps auf iOS-Geräten.\""
keywords: 
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 07/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: bda26d1d-2a3b-4669-adf8-a5aa7f994916
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: f5b7c1c5d2286bbf14d82e4c09895c520177fdb6
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2018
---
# <a name="intune-app-notifications-settings-for-ios-devices"></a>App-Benachrichtigungseinstellungen für iOS-Geräte in Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Hiermit können Sie konfigurieren, wie auf einem Gerät installierte Apps Benachrichtigungen senden. Diese Einstellungen unterstützen überwachte Geräte, auf denen iOS 9.3 oder höher ausgeführt wird.

## <a name="configure-settings"></a>Konfigurieren der Einstellungen

1. Wählen Sie auf dem Blatt „Gerätefunktionen“ die Option **App-Benachrichtigungen (nur überwacht)** aus.
2. Wählen Sie auf dem Blatt **App-Benachrichtigungen** die Option **Hinzufügen**, und konfigurieren Sie die folgenden Werte:
    - **App-Bündel-ID**: Geben Sie die **App-Bündel-ID** der App ein, die Sie konfigurieren möchten. Hilfe finden Sie weiter unten in diesem Thema unter **Bündel-ID-Referenz für integrierte iOS-Apps**.
    - **App-Name**: Geben Sie den Namen der App ein, die Sie konfigurieren möchten. Dieser Name wird nicht auf dem Gerät angezeigt und hilft Ihnen dabei, die App in der Liste zu identifizieren.
    - **Herausgeber**: Geben Sie den Namen des Herausgebers der App ein, die Sie konfigurieren möchten. Der Name des Herausgebers wird nicht auf dem Gerät angezeigt und hilft Ihnen nur dabei, die App in der Liste zu identifizieren.
    - **Benachrichtigungen**: Aktivieren oder deaktivieren Sie das Senden von Benachrichtigungen von der App an das Gerät. Wenn Sie diese Einstellung deaktivieren, werden die folgenden Einstellungen ebenfalls deaktiviert.
        - **In Mitteilungszentrale anzeigen**: Aktivieren Sie diese Einstellung, um zuzulassen, dass Benachrichtigungen der App in der Mitteilungszentrale angezeigt werden.
        - **In Sperrbildschirm anzeigen**: Aktivieren Sie diese Einstellung, damit Benachrichtigungen der App auf dem Sperrbildschirm des Geräts angezeigt werden.
        - **Warnungstyp**: Wählen Sie die Art der Benachrichtigung aus, die beim Entsperren des Geräts angezeigt werden soll. Diese Optionen sind verfügbar:
            - **Keine**: Es wird keine Benachrichtigung angezeigt.
            - **Banner**: Es wird kurz ein Banner mit der Benachrichtigung angezeigt.
            - **Modal**: Die Benachrichtigung wird angezeigt, und der Benutzer muss sie manuell schließen, um das Gerät weiter verwenden zu können.
        - **Badge für App-Symbol**: Aktivieren Sie diese Einstellung, um dem App-Symbol einen Badge hinzuzufügen, der darauf hinweist, dass die App eine Benachrichtigung gesendet hat.
        - **Sounds**: Aktivieren Sie diese Einstellung, um einen Sound wiederzugeben, wenn eine Benachrichtigung eintrifft.
3. Fügen Sie so viele Apps hinzu, wie Sie benötigen. Wenn Sie fertig sind, wählen Sie **OK** aus.
4. Klicken Sie auf **OK**, bis Sie zum Blatt **Profil erstellen** zurückkehren, und wählen Sie dann **Erstellen** aus. 


## <a name="bundle-id-reference-for-built-in-ios-apps"></a>Bündel-ID-Referenz für integrierte iOS-Apps

Diese Liste zeigt die Bündel-ID einiger gängiger integrierter iOS-Apps. Um die Bündel-ID von anderen Apps zu finden, wenden Sie sich an den Softwarehersteller. 

|||
|-|-|
|App-Name|Bündel-ID|
|App Store|com.apple.AppStore|
|Calculator|com.apple.calculator|
|Kalender|com.apple.mobilecal|
|Kamera|com.apple.camera|
|Clock|com.apple.mobiletimer|
|Compass|com.apple.compass|
|Kontakte|com.apple.MobileAddressBook|
|FaceTime|com.apple.facetime|
|Find Friends|com.apple.mobileme.fmf1|
|Find iPhone|com.apple.mobileme.fmip1|
|Gamecenter|com.apple.gamecenter|
|GarageBand|com.apple.mobilegarageband|
|Integrität|com.apple.Health|
|iBooks|com.apple.iBooks|
|iTunes Store|com.apple.MobileStore|
|iTunes U|com.apple.itunesu|
|Keynote|com.apple.Keynote|
|Mail|com.apple.mobilemail|
|Zuordnungen|com.apple.Maps|
|Nachrichten|com.apple.MobileSMS|
|Musik|com.apple.Music|
|News|com.apple.news|
|Hinweise|com.apple.mobilenotes|
|Zahlen|com.apple.Numbers|
|Seiten|com.apple.Pages|
|Photo Booth|com.apple.Photo-Booth|
|Fotos|com.apple.mobileslideshow|
|Podcasts|com.apple.podcasts|
|Reminders|com.apple.reminders|
|Safari|com.apple.mobilesafari|
|Einstellung|com.apple.Preferences|
|Stocks|com.apple.stocks|
|Tipps|com.apple.tips|
|Videos|com.apple.videos|
|VoiceMemos|com.apple.VoiceMemos|
|Wallet|com.apple.Passbook|
|Überwachen|com.apple.Bridge|
|Weather|com.apple.weather|

## <a name="next-steps"></a>Nächste Schritte

Sie können nun das Geräteprofil den von Ihnen ausgewählten Gruppen zuweisen. Weitere Informationen finden Sie unter [Zuweisen von Geräteprofilen](device-profile-assign.md).
