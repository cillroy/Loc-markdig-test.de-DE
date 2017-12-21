---
title: "Einstellungen für Geräteeinschränkungen für Android in Intune"
titlesuffix: Azure portal
description: "In diesem Artikel lernen Sie die Intune-Einstellungen zur Steuerung von Geräteeinstellungen und -funktionen auf Android-Geräten kennen."
keywords: 
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 12/11/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6bdf714a-5d93-485c-8b52-513635c60cb6
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 0934e9f45cfee88fe12fac2ceda963c4afc2969c
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2017
---
# <a name="android-and-samsung-knox-standard-device-restriction-settings-in-microsoft-intune"></a>Einstellungen für Standardgeräteeinschränkungen für Android- und Samsung KNOX in Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Verwenden Sie diese Einstellungen mit einer Einschränkungsrichtlinie für Android-Geräte, um Geräte in Ihrer Organisation zu konfigurieren.

>[!TIP]
>Wenn Ihre gewünschten Einstellungen nicht verfügbar sind, können Sie Ihre Geräte möglicherweise mit einem [benutzerdefinierten Profil](custom-settings-android.md) konfigurieren.

## <a name="general"></a>Allgemein

- **Kamera:** Erlaubt die Verwendung der Gerätekamera.
- **Kopieren und einfügen (nur Samsung KNOX):** Lässt Kopier- und Einfügefunktionen auf dem Gerät zu oder sperrt diese Funktionen.
- **Gemeinsame Nutzung der Zwischenablage durch Apps (nur Samsung KNOX):** Erlaubt die Verwendung der Zwischenablage für das Kopieren und Einfügen zwischen Apps.
- **Übermittlung von Diagnosedaten (nur Samsung KNOX):** Hindert den Benutzer an der Übermittlung von Diagnosedaten vom Gerät.
- **Zurücksetzung auf Werkseinstellungen (nur Samsung KNOX):** Erlaubt dem Benutzer das Zurücksetzen des Geräts auf die Werkseinstellungen.
- **Geolocation (nur Samsung KNOX):** Erlaubt dem Gerät die Nutzung von Standortinformationen.
- **Ausschalten (nur Samsung KNOX):** Erlaubt dem Benutzer das Ausschalten des Geräts.<br>Wenn diese Option deaktiviert ist, kann die **Anzahl von fehlgeschlagenen Anmeldungen, bevor das Gerät zurückgesetzt wird** nicht festgelegt werden.
- **Bildschirmaufnahme (nur Samsung KNOX):** Erlaubt dem Benutzer, den Bildschirminhalt als Bild zu erfassen.
- **Sprach-Assistent (nur Samsung KNOX):** Erlaubt die Verwendung von Sprach-Assistent-Software auf dem Gerät.
- **YouTube (nur Samsung KNOX):** Erlaubt die Verwendung der YouTube-App auf dem Gerät.
- **Freigegebene Geräte (nur Samsung KNOX):** Konfigurieren Sie ein verwaltetes Samsung KNOX-Standardgerät als freigegeben. In diesem Modus können sich Endbenutzer des Geräts mit ihren Azure AD-Anmeldeinformationen an- und abmelden. Das Gerät wird weiterhin verwaltet, ganz gleich, ob es verwendet oder nicht.<br>In Verbindung mit einem SCEP-Zertifikatsprofil ermöglicht diese Funktion Endbenutzern die gemeinsame Nutzung eines Geräts mit denselben Apps für alle Benutzer, jedoch mit eigenem SCEP-Benutzerzertifikat.  Wenn sich Benutzer abmelden, werden alle App-Daten gelöscht.  Dieses Feature ist ausschließlich auf branchenspezifische Apps beschränkt.
- **Datum und Uhrzeit-Änderungen (Samsung KNOX) blockieren** : verhindern, dass den Benutzer das Datum und Uhrzeit auf dem Gerät. 

## <a name="password"></a>Kennwort

- **Kennwort:** Der Endbenutzer muss ein Kennwort eingeben, um auf das Gerät zugreifen zu können.|Ja|Ja|
- **Minimale Kennwortlänge:** Geben Sie die Mindestanzahl von Zeichen an, die Benutzer für das Kennwort festlegen müssen (zwischen 4 und 16 Zeichen).
- **Maximaler Zeitraum der Inaktivität (in Minuten) bis zur Bildschirmsperrung:** Gibt die Anzahl der Minuten der Inaktivität an, bevor das Gerät automatisch gesperrt wird.
- **Anzahl von Anmeldefehlern, bevor das Gerät zurückgesetzt wird:** Gibt die Anzahl zulässiger Anmeldefehler an, bevor das Gerät zurückgesetzt wird.
- **Kennwortablauf (Tage):** Gibt die Anzahl der Tage an, bevor das Gerätekennwort geändert werden muss.
-  **Erforderlicher Kennworttyp:** Gibt den erforderlichen Grad der Kennwortkomplexität an. Zudem wird angegeben, ob biometrische Geräte zulässig sind. Wählen Sie aus:
    - **Gerätestandard**
    - **Biometrie auf niedriger Sicherheitsstufe**
    - **Mindestens numerisch**
    - **Numerisch komplex**: Sich wiederholende oder fortlaufende Ziffern wie „1111“ oder „1234“ sind nicht zulässig.<sup>1</sup>
    - **Mindestens alphabetisch**
    - **Mindestens alphanumerisch**
    - **Mindestens alphanumerisch mit Symbolen**
- **Wiederverwendung vorheriger Kennwörter verhindern:** Hindert den Endbenutzer daran, ein bereits verwendetes Kennwort erneut festzulegen.
- **Entsperrung durch Fingerabdruck (nur Samsung KNOX):** Erlaubt die Verwendung eines Fingerabdrucks zum Entsperren unterstützter Geräte.
- **Smart Lock und andere Vertrauens-Agents:** Ermöglicht die Steuerung des Smart Lock-Features auf kompatible Android-Geräten (Samsung KNOX Standard 5.0 und höher). Diese Telefonfunktion wird manchmal als Vertrauens-Agent bezeichnet und ermöglicht Ihnen, das Kennwort für den Gerätesperrbildschirm zu deaktivieren oder zu umgehen, wenn sich das Gerät an einem vertrauenswürdigen Standort befindet. Diese kann beispielsweise verwendet werden, wenn das Gerät mit einem bestimmten Bluetooth-Gerät verbunden ist oder sich in der Nähe eines NFC-Tags befindet. Mit dieser Einstellung können Sie verhindern, dass Benutzer Smart Lock konfigurieren.
- **Verschlüsselung:** Schreibt vor, dass die Dateien auf den Geräten verschlüsselt werden müssen.

<sup>1</sup> Bevor Sie diese Einstellung Geräten zuweisen, aktualisieren Sie die Unternehmensportal-App auf diesen Geräten auf jeden Fall auf die neueste Version.

Wenn Sie die Einstellung **Numerisch komplex** konfigurieren und sie dann einem Gerät mit einer früheren Android-Version als 5.0 zuweisen, gilt das folgende Verhalten.
- Wenn die Unternehmensportal-App eine ältere Version als 1704 ausführt, wird keine PIN-Richtlinie auf das Gerät angewendet, und eine Fehlermeldung wird im Azure-Portal angezeigt.
- Wenn die Unternehmensportal-App die Version 1704 oder höher ausführt, kann nur eine einfache PIN angewendet werden. Frühere Android-Versionen als 5.0 unterstützen diese Einstellung nicht. Es wird keine Fehlermeldung im Azure-Portal angezeigt.


## <a name="google-play-store"></a>Google Play Store

- **Google Play Store (nur Samsung KNOX):** Erlaubt dem Benutzer den Zugriff auf den Google Play Store auf dem Gerät.

## <a name="restricted-apps"></a>Eingeschränkte Apps

In der Liste der eingeschränkten Apps können Sie eine der folgenden Listen für Android-Geräte als auch Geräte, die dem Samsung KNOX Standard entsprechen, konfigurieren:

**Unzulässige Apps:** Listet die (nicht von Intune verwalteten) Apps auf, die gemeldet werden, wenn Benutzer sie installieren und ausführen.
**Genehmigte Apps:** Listet die Apps auf, die Benutzer installieren dürfen. Um die Kompatibilität zu gewährleisten, dürfen Benutzer keine anderen Apps installieren. Apps, die von Intune verwaltet werden, sind automatisch zugelassen.
Geräteprofile, die Einstellungen für eingeschränkte Apps enthalten, müssen Benutzergruppen zugewiesen werden.

Klicken Sie zum Konfigurieren einer Liste auf **Hinzufügen**. Geben Sie einen Namen Ihrer Wahl sowie die URL zur App im App-Store und optional den Herausgeber der App an.

### <a name="how-to-specify-the-url-to-an-app-in-the-store"></a>Angeben der URL zu einer App im Store

Verwenden Sie zum Festlegen einer App-URL in der Liste kompatibler und nicht kompatibler Apps die folgenden Schritte:

Suchen Sie im [Apps-Bereich von Google Play](https://play.google.com/store/apps) nach der App, die Sie verwenden möchten.

Öffnen Sie die Installationsseite für die App, und kopieren Sie dann die URL in die Zwischenablage. Jetzt können Sie diese URL in der Liste mit kompatiblen oder nicht kompatiblen Apps verwenden.

Beispiel: Suchen Sie in Google Play nach Microsoft Office Mobile. Verwenden Sie die URL **https://play.google.com/store/apps/details?id=com.microsoft.office.officehub**.

### <a name="additional-options"></a>Zusätzliche Optionen

Sie können auch auf **Importieren** klicken, um die Liste über eine CSV-Datei abzurufen. Verwenden Sie das Format <*App-URL*>, <*App-Name*>, <*App-Herausgeber*>. Sie können auch auf **Exportieren** klicken, um eine CSV-Datei mit dem Inhalt der Liste der eingeschränkten Apps im selben Format zu erstellen.      

## <a name="browser"></a>Browser

- **Webbrowser (nur Samsung KNOX):** Gibt an, ob der Standardwebbrowser des Geräts verwendet werden darf.
- **AutoAusfüllen (nur Samsung KNOX):** Erlaubt die Verwendung der AutoAusfüllen-Funktion des Webbrowsers.
- **Cookies (nur Samsung KNOX):** Erlaubt die Verwendung von Cookies durch den Webbrowser des Geräts.
- **Javascript (nur Samsung KNOX):** Erlaubt die Ausführung von Java-Skripts im Webbrowser.
- **Popups (nur Samsung KNOX):** Erlaubt die Verwendung des Popupblockers im Webbrowser.

## <a name="allow-or-block-apps"></a>Zulassen oder Blockieren von Apps

Diese Einstellungen können verwendet werden, um Apps anzugeben, die auf Geräten installiert oder gestartet werden können, die nur Samsung KNOX Standard ausführen.
Darüber hinaus können Sie auch installierte Apps angeben, die für den Benutzer des Geräts ausgeblendet werden. Diese Apps können die Benutzer nicht ausführen.

- **Zur Installation zugelassene Apps (nur Samsung KNOX Standard)**
- **Apps, deren Start blockiert wird (nur Samsung KNOX Standard)**
- **Für den Benutzer ausgeblendete Apps (nur Samsung KNOX Standard)**

Konfigurieren Sie für jede Einstellung eine Liste von Apps mit einer der folgenden Optionen:

- **Apps nach Paketname hinzufügen**: Wird in erster Linie für Geschäftsanwendungen verwendet. Geben Sie den Namen der App und den Namen des App-Pakets ein.
- **Apps nach URL hinzufügen**: Geben Sie den Namen der App und ihre URL im Google Play Store ein.
- **Verwaltete Apps hinzufügen**: Wählen Sie in der Liste der Apps, die Sie mit Intune verwalten, die benötigte App aus.

## <a name="cloud-and-storage"></a>Cloud und Speicher

- **Google-Sicherung (nur Samsung KNOX):** Erlaubt die Verwendung der Google-Sicherung.
- **Automatische Google-Kontosynchronisierung (nur Samsung KNOX):** Erlaubt die automatische Synchronisierung der Einstellungen von Google-Konten.
- **Wechselmedien (nur Samsung KNOX):** Erlaubt dem Gerät Wechselmedien wie SD-Karten zu verwenden.
- **Verschlüsselung auf Speicherkarten (nur Samsung KNOX):** Gibt an, ob die Gerätespeicherkarte verschlüsselt werden muss.

## <a name="cellular-and-connectivity"></a>Mobilfunk und Konnektivität

- **Datenroaming (nur Samsung KNOX):** Erlaubt das Datenroaming, wenn das Gerät in einem Mobilfunknetz verwendet wird.
- **SMS-/MMS-Nachrichten (nur Samsung KNOX):** Erlaubt die Verwendung von SMS und MMS-Nachrichten auf dem Gerät.
- **Sprachwahlverfahren (nur Samsung KNOX):** Aktiviert oder deaktiviert die Sprachwahlfunktion auf dem Gerät.
- **Sprachroaming (nur Samsung KNOX):** Erlaubt das Sprachroaming, wenn das Gerät in einem Mobilfunknetz verwendet wird.
- **Bluetooth (nur Samsung KNOX):** Erlaubt die Verwendung von Bluetooth auf dem Gerät.
- **NFC (nur Samsung KNOX):** Erlaubt Vorgänge, bei dem NFC (Near Field Communication) auf unterstützten Geräten zum Einsatz kommt.
- **WLAN (nur Samsung KNOX):** Erlaubt die Verwendung der WLAN-Funktionen des Geräts.
- **WLAN-Tethering (nur Samsung KNOX):** Erlaubt die Verwendung von WLAN-Tethering auf dem Gerät.

## <a name="kiosk"></a>Kiosk

Kioskeinstellungen gelten nur für Samsung KNOX Standard-Geräte, und nur für Apps, die Sie mit Intune verwalten.

- **Verwaltete App auswählen:** Wählen Sie eine der folgenden Optionen aus, um eine oder mehrere verwaltete Apps hinzuzufügen, die ausgeführt werden können, wenn sich das Gerät im Kioskmodus befindet. Es dürfen keine anderen Apps auf dem Gerät ausgeführt werden.
    - **Hinzufügen von Apps nach Paketname**
    - **Hinzufügen von Apps nach URL**
    - **Hinzufügen von verwalteten Apps**
- **Standbytaste:** Aktiviert oder deaktiviert die Standbytaste am Gerät.
- **Lautstärketasten** – Aktiviert oder deaktiviert die Verwendung der Lautstärketasten am Gerät.


## <a name="next-steps"></a>Nächste Schritte

Folgen Sie den Anweisungen unter [So konfigurieren Sie Einstellungen für Geräteeinschränkungen in Microsoft Intune](device-restrictions-configure.md), um das Geräteeinschränkungsprofil zu erstellen und anschließend zuzuweisen.
