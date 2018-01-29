---
title: "Einstellungen für Geräteeinschränkungen für Windows 10 in Intune"
titlesuffix: Azure portal
description: "In diesem Artikel lernen Sie die Intune-Einstellungen zur Steuerung von Geräteeinstellungen und -funktionen auf Windows 10-Geräten kennen."
keywords: 
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 12/13/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 89f2d806-2e97-430c-a9a1-70688269627f
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 0dd4bd3052fcdb26193bb935dae729eab8d19f1e
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2018
---
# <a name="windows-10-and-later-device-restriction-settings-in-microsoft-intune"></a>Einstellungen für Geräteeinschränkungen für Windows 10 und höher in Microsoft Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

## <a name="general"></a>Allgemein
- **Bildschirmaufnahme (nur Mobilgerät):** Erlaubt dem Benutzer, den Bildschirm des Geräts als Bild zu erfassen.
- **Kopieren und einfügen (nur mobil):** Erlaubt Kopier- und Einfügevorgänge zwischen Apps auf dem Gerät.
- **Manuelle Aufhebung der Registrierung:** Erlaubt dem Benutzer das manuelle Löschen des Unternehmensbereichskontos vom Gerät.
- **Manuelle Installation von Stammzertifikaten (nur Mobilgerät):** Hindert den Benutzer daran, Stammzertifikate und CAP-Zwischenzertifikate manuell zu installieren.
- **Übermitteln von Diagnosedaten:** Mögliche Werte:
    - **Keine**: Es werden keine Daten an Microsoft gesendet.
    - **Einfach** – begrenzte Informationen werden an Microsoft gesendet
    - **Erweitert**: Es werden erweiterte Diagnosen an Microsoft gesendet.
    - **Vollständig:** Das Gerät sendet die gleichen Daten wie mit „Erweitert“ sowie zusätzliche Daten über den Gerätezustand.
- **Kamera:** Erlaubt oder sperrt die Verwendung der Kamera auf dem Gerät.
- **OneDrive-Dateisynchronisierung:** Hindert das Gerät daran, Dateien mit OneDrive zu synchronisieren.
- **Wechselmedien:** Gibt an, ob externe Speichergeräte wie SD-Karten mit dem Gerät verwendet werden können.
- **Geolocation:** Gibt an, ob das Gerät Standortdienstinformationen verwenden kann.
- **Internetfreigabe:** Erlaubt die gemeinsame Nutzung der Internetverbindung auf dem Gerät.
- **Zurücksetzung des Telefons:** Steuert, ob Benutzer ihre Geräte auf die Werkseinstellungen zurücksetzen können.
- **USB-Verbindung (nur Mobilgerät):** Steuert, ob Geräte über eine USB-Verbindung auf externe Speichergeräte zugreifen können.
- **AntiTheft-Modus (nur Mobilgerät)**: Konfigurieren Sie, ob der Windows-AntiTheft-Modus aktiviert ist.
- **Cortana:** Aktiviert oder deaktiviert den Cortana-Sprach-Assistenten.
- **Sprachaufzeichnung (nur Mobilgerät):** Erlaubt oder sperrt die Verwendung der Sprachaufzeichnung des Geräts.
- **Bearbeitung des Gerätenamens:** Verhindert, dass der Endbenutzer den Gerätenamen ändert (nur Windows 10 Mobile).
- **Bereitstellungspakete hinzufügen:** Blockiert den Laufzeitkonfigurations-Agent, der Bereitstellungspakete installiert.
- **Bereitstellungspakete entfernen:** Blockiert den Laufzeitkonfigurations-Agent, der Bereitstellungspakete entfernt.
- **Geräteerkennung:** Verhindert, dass ein Gerät von anderen Geräten erkannt wird.
- **Programmumschaltung (nur mobile Geräte):** Blockiert die Programmumschaltung auf dem Gerät.
- **Dialogfeld bei SIM-Kartenfehler (nur mobile Geräte):** Blockiert die Anzeige einer Fehlermeldung auf dem Gerät, wenn keine SIM-Karte erkannt wird.
  <!--- **Automatic redeployment** - Allows users with administrative rights to delete all user data and settings using **CTRL + Win + R** at the device lock screen. The device is automatically reconfigured and reenrolled into management. -->


## <a name="password"></a>Kennwort
-   **Kennwort:** Der Endbenutzer muss ein Kennwort eingeben, um auf das Gerät zugreifen zu können.
    -   **Erforderlicher Kennworttyp:** Gibt an, ob das Kennwort nur numerisch sein muss oder alphanumerisch.
    -   **Minimale Kennwortlänge:** Gilt nur für Windows 10 Mobile.
    -   **Anzahl von Anmeldefehlern, bevor das Gerät zurückgesetzt wird:** Für Geräte mit Microsoft 10: Wenn auf dem Gerät BitLocker aktiviert ist, wird in den BitLocker-Wiederherstellungsmodus gewechselt, sobald die Anzahl der von Ihnen angegebenen Anmeldefehler erreicht ist. Wenn BitLocker nicht für dieses Gerät aktiviert ist, wird diese Einstellung nicht angewendet.
Für Geräte mit Windows 10 Mobile: Das Gerät wird zurückgesetzt, sobald die Anzahl der von Ihnen angegebenen Anmeldeversuche fehlgeschlagen ist.
    -   **Maximaler Zeitraum der Inaktivität (in Minuten) bis zur Bildschirmsperrung:** Gibt den Zeitraum der Inaktivität für ein Gerät an, bevor der Bildschirm gesperrt wird.
    -   **Kennwortablauf (Tage):** Gibt die Zeitdauer an, nach der das Kennwort für das Gerät geändert werden muss.
    -   **Wiederverwendung vorheriger Kennwörter verhindern:** Gibt an, wie viele zuvor verwendete Kennwörter vom Gerät gespeichert werden.
    -   **Kennwort anfordern, wenn Gerät aus Leerlaufzustand zurückkehrt (nur Mobile):** Gibt an, dass der Benutzer ein Kennwort zum Entsperren des Geräts eingeben muss (nur Windows 10 Mobile).
    -   **Einfache Kennwörter:** Erlaubt die Verwendung einfacher Kennwörter wie 1111 oder 1234. Diese Einstellung ermöglicht es auch, die Verwendung von Windows-Bildcodes zu blockieren.
-   **Verschlüsselung**: Aktivieren der Verschlüsselung auf Zielgeräten

## <a name="personalization"></a>Personalization

-   **URL zu Desktophintergrundbild (nur Desktop):** Gibt die URL zu einem Bild im PNG-, JPG- oder JPEG-Format an, das Sie als Windows-Desktophintergrund verwenden möchten. Benutzer können dies nicht ändern.

## <a name="privacy"></a>Datenschutz

-   **Eingabepersonalisierung:** Verhindert die Verwendung cloudbasierter Sprachdienste für Cortana, Diktierfunktionen oder Microsoft Store-Apps. Wenn Sie diese Dienste zulassen, kann Microsoft Voice-Daten erfassen, um den Dienst zu verbessern.
-   **Automatisches Akzeptieren der Zustimmungsaufforderung des Benutzers zu Kopplung und Datenschutz:** Erlaubt Windows beim Ausführen von Apps das automatische Akzeptieren von Benachrichtigungen zur Zustimmung zu Kopplung und Datenschutz.


## <a name="locked-screen-experience"></a>Gesperrter Bildschirm


-   **Info-Center-Benachrichtigungen (nur Mobilgerät):** Lässt Info-Center-Benachrichtigungen auf dem Gerätesperrbildschirm anzeigen (nur Windows 10 Mobile).
-   **URL zu Bild für gesperrten Bildschirm (nur Desktop):** Gibt die URL zu einem Bild im PNG-, JPG- oder JPEG-Format an, das als Hintergrund für den Windows-Sperrbildschirm verwendet wird. Benutzer können dies nicht ändern.
-   **Vom Benutzer konfigurierbares Bildschirmtimeout (nur Mobilgeräte):** Ermöglicht Benutzern das Einstellen der Zeitspanne. 
-   **Cortana auf Sperrbildschirm (nur Desktop):** Lässt nicht zu, dass der Benutzer mit Cortana interagiert, wenn auf dem Gerät der Sperrbildschirm zu sehen ist (nur Windows 10 Desktop).
-   **Popupbenachrichtigungen auf Sperrbildschirm:** Verhindert, dass Warnmeldungen auf dem Gerätesperrbildschirm angezeigt werden.
-   **Bildschirmtimeout (nur Mobilgerät):** Gibt die Zeit in Sekunden an, nach der der gesperrte Bildschirm ausgeschaltet wird.



## <a name="app-store"></a>App Store

-   **App Store (nur mobil):** Erlaubt oder sperrt die Verwendung des App Stores auf Windows 10 Mobile-Geräten.
-   **Apps aus Store automatisch aktualisieren:** Ermöglicht die automatische Aktualisierung von Apps, die aus dem Microsoft Store installiert wurden.
-   **Installation vertrauenswürdiger Apps:** Ermöglicht das Querladen von Apps, die mit einem vertrauenswürdigen Zertifikat signiert sind.
-   **Entwicklersperre aufheben:** Ermöglicht dem Endbenutzer, Windows-Entwicklereinstellungen – z.B. das Zulassen quergeladener Apps – zu ändern.
-   **Gemeinsam genutzte App-Benutzerdaten:** Ermöglicht Apps, die gemeinsame Nutzung von Daten durch verschiedene Benutzer auf dem gleichen Gerät zuzulassen.
-   **Nur privaten Store verwenden:** Aktivieren Sie diese Option, um Endbenutzern das Herunterladen von Apps nur aus Ihrem privaten Store zu ermöglichen.
-   **Store-App starten:** Hiermit werden alle Apps deaktiviert, die bereits auf dem Gerät installiert waren oder aus dem Microsoft Store heruntergeladen wurden.
-   **App-Daten in Systemvolume installieren:** Hindert Apps daran, Daten auf dem Systemvolume des Geräts zu speichern.
-   **Apps auf Systemlaufwerk installieren:** Hindert Apps daran, Daten auf dem Systemlaufwerk des Geräts zu speichern.
-   **Game DVR (nur Desktop):** Konfiguriert, ob Aufzeichnen und Senden von Spielen zulässig ist.
-   **Nur Apps aus dem Store**: Konfiguriert, ob Benutzer Apps von anderen Orten als aus dem App-Store installieren können.



## <a name="edge-browser"></a>Edge-Browser

-   **Microsoft Edge-Browser (nur mobil):** Erlaubt die Verwendung des Edge-Webbrowsers auf dem Gerät.
-   **Adressleisten-Dropdown (nur Desktop):** Verhindert, dass Edge bei der Eingabe weiterhin eine Liste mit Vorschlägen in einer Dropdownliste anzeigt. So kann die zwischen Edge und Microsoft-Diensten genutzte Netzwerkbandbreite minimiert werden.
-   **Favoriten zwischen Microsoft-Browsern synchronisieren (nur Desktop):** Erlaubt Windows das Synchronisieren von Favoriten zwischen Internet Explorer und Edge.
-   **DNT-Kopfzeilen senden:** Konfiguriert den Edge-Browser zum Senden von DNT-Headern (Do Not Track, nicht nachverfolgen) an Websites, die Benutzer besuchen.
-   **Cookies:** Erlaubt Browsern das Speichern von Internetcookies auf dem Gerät.
-   **Javascript:** Erlaubt die Ausführung von Skripts wie z.B. JavaScript im Edge-Browser.
-   **Popups:** Blockiert Popupfenster im Browser (gilt nur für Windows 10 Desktop).
-   **Suchvorschläge:** Ermöglicht dem Suchmodul, Websites während der Eingabe von Suchausdrücken vorzuschlagen.
-   **Datenverkehr im Intranet an Internet Explorer senden:** Erlaubt Benutzern, Intranetsites in Internet Explorer zu öffnen (nur Windows 10 Desktop).
-   **AutoAusfüllen:** Erlaubt Benutzern, die Einstellungen für AutoAusfüllen im Browser zu ändern (nur Windows 10 Desktop).
-   **Kennwort-Manager:** Aktiviert oder deaktiviert den Edge-Kennwort-Manager.
-   **Speicherort der Websiteliste für den Unternehmensmodus:** Gibt an, wo Sie die Liste der Websites finden, die im Unternehmensmodus geöffnet werden. Benutzer können diese Liste nicht bearbeiten.<br>(Nur Windows 10 Desktop)
-   **Entwicklungstools:** Hindert den Endbenutzer daran, die Edge-Entwicklertools aufzurufen.
-   **Erweiterungen:** Erlaubt dem Benutzer, Edge-Erweiterungen auf dem Gerät zu installieren.
-   **InPrivate-Browsen:** Hindert den Endbenutzer daran, InPrivate-Browsersitzungen zu öffnen.
-   **Anzeigen der „Willkommen“-Seite:** Verhindert, dass die Einführungsseite bei der ersten Ausführung von Edge angezeigt wird.
    -   **URL für erste Ausführung:** Gibt die URL einer Seite an, die bei der ersten Ausführung von Edge angezeigt wird (nur Windows 10 Mobile).
-   **Startseiten:** Fügt eine Liste der Websites hinzu, die Sie im Edge-Browser als Startseiten verwendet möchten (nur Desktop).
-   **Änderungen an Startseite:** Ermöglicht Benutzern das Ändern der Startseiten, die beim Öffnen von Edge angezeigt werden. Nutzen Sie die Einstellung der Startseiten, um die Seite oder Liste von Seiten zu erstellen, die beim Starten von Edge geöffnet werden.
-   **Zugriff auf about:flags-Seite blockieren:** Hindert den Benutzer am Zugriff auf die about:flags-Seite in Edge, die Entwicklungs- und experimentelle Einstellungen enthält.
-   **WebRTC-LocalHost-IP-Adresse:** Blockiert die Anzeige der Localhost-IP-Adresse des Benutzers bei Anrufen über das Internet-RTC-Protokoll.
-   **Standardsuchmodul:** Gibt das zu verwendende Standardsuchmodul an. Endbenutzer können diesen Wert jederzeit ändern.
-   **Browserdaten beim Beenden löschen:** Löscht Verlauf und Browserdaten, wenn der Benutzer Edge beendet.
-   **Datenerfassung für Livekacheln:** Beendet das Sammeln von Daten durch Windows aus den Livekacheln, wenn der Benutzer eine Seite an das Startmenü von Edge anheften.

## <a name="edge-browser-smartscreen"></a>Edge-Browser SmartScreen

-   **SmartScreen:** Aktiviert oder deaktiviert den SmartScreen, durch den betrügerische Websites blockiert werden.
-   **SmartScreen-Aufforderung außer Kraft setzen:** Ermöglicht dem Endbenutzer, SmartScreen-Filterwarnungen zu potenziell bösartigen Websites zu umgehen.
-   **SmartScreen-Aufforderung für Dateien außer Kraft setzen:** Ermöglicht dem Endbenutzer, SmartScreen-Filterwarnungen zum Herunterladen potenziell bösartiger Dateien zu umgehen.

## <a name="search"></a>Suchen
- **SafeSearch (nur Mobilgeräte):** Steuert, wie Cortana nicht jugendfreie Inhalte in den Suchergebnissen filtert. Sie können **Streng** oder **Mittel** auswählen oder dem Endbenutzer ermöglichen, seine eigenen Einstellungen zu wählen.

## <a name="cloud-and-storage"></a>Cloud und Speicher
-   **Microsoft-Konto:** Erlaubt dem Benutzer, das Gerät einem Microsoft-Konto zuzuordnen.
-   **Nicht-Microsoft-Konto:** Erlaubt dem Benutzer, dem Gerät E-Mail-Konten hinzuzufügen, die nicht mit einem Microsoft-Konto verknüpft sind.
-   **Synchronisierung der Einstellungen für Microsoft-Konto:** Erlaubt das Synchronisieren der mit einem Microsoft-Konto verknüpften Geräte- und App-Einstellungen zwischen Geräten.

## <a name="cellular-and-connectivity"></a>Mobilfunk und Konnektivität

-   **Mobilfunkdatenkanal:** Verhindert, dass Benutzer Daten verbrauchen wie z.B. beim Browsen im Web, wenn sie mit einem Mobilfunknetz verbunden sind. 
-   **Datenroaming:** Erlaubt beim Zugriff auf Daten das Roaming zwischen Netzwerken.
-   **VPN über Mobilfunknetz:** Steuert, ob das Gerät auf VPN-Verbindungen zugreifen kann, wenn es mit einem Mobilfunknetz verbunden ist.
-   **VPN-Roaming über Mobilfunknetz:** Steuert, ob das Gerät beim Roaming in einem Mobilfunknetz auf VPN-Verbindungen zugreifen kann.
-   **Bluetooth:** Steuert, ob der Benutzer Bluetooth auf dem Gerät aktivieren und konfigurieren kann.
-   **Bluetooth-Erkennbarkeit:** Ermöglicht die Erkennung dieses Geräts durch andere Bluetooth-Geräte.
-   **Bluetooth-Vorabkopplung:** Ermöglicht das Konfigurieren spezifischer Bluetooth-Geräte für automatisches Koppeln mit einem Hostgerät.
-   **Bluetooth-Werbung:** Ermöglicht das Empfangen von Werbung per Bluetooth durch das Gerät.
-   **Dienst für verbundene Geräte:** Ermöglicht die Entscheidung, ob dem Dienst für verbundene Geräte die Ermittlung von und Verbindung mit anderen Bluetooth-Geräten erlaubt wird.
-   **NFC:** Erlaubt dem Benutzer das Aktivieren und Konfigurieren von Funktionen, die NFC (Near Field Communication, Nahfeldkommunikation) verwenden, auf dem Gerät.
-   **WLAN:** Erlaubt dem Benutzer das Aktivieren und Konfigurieren von WLAN auf dem Gerät (nur Windows 10 Mobile).
-   **Automatische Verbindung mit WLAN-Hotspots herstellen:** Ermöglicht automatische Verbindungen des Geräts mit unverschlüsselten WLAN-Hotspots und das automatische Akzeptieren der Geschäftsbedingungen für die Verbindung.
-   **Manuelle WLAN-Konfiguration:** Steuert, ob die Benutzer eigene WLAN-Verbindungen konfigurieren dürfen oder ob nur über WLAN-Profile konfigurierte Verbindungen verwendet werden dürfen (nur Windows 10 Mobile).
-   **Intervall für WLAN-Suche:** Gibt an, wie oft Geräte nach WLAN-Netzwerken suchen. Geben Sie einen Wert zwischen 1 (am häufigsten) und 500 (am seltensten) an.
-   **Zulässige Bluetooth-Dienste:** Gibt in Form von hexadezimalen Zeichenfolgen eine Liste zulässiger Bluetooth-Dienste und -Profile an.


## <a name="control-panel-and-settings"></a>Systemsteuerung und Einstellungen

-   **App „Einstellungen“:** Blockiert den Zugriff auf die Windows-Einstellungen-App.
    -   **System:** Blockiert den Zugriff auf den Systembereich der Einstellungen-App.
        -   **Änderung der Energie- und Energiesparmoduseinstellungen (nur Desktop):** Verhindert, dass der Endbenutzer Energie- und Energiesparmoduseinstellungen auf dem Gerät ändert.
    -   **Geräte:** Blockiert den Zugriff auf den Gerätebereich der Einstellungen-App.
    -   **Netzwerk-Internet** -blockiert den Zugriff auf das Netzwerk und Internet-Bereich der einstellungs-app.
    -   **Personalisierung:** Blockiert den Zugriff auf den Personalisierungsbereich der Einstellungen-App.
    -   **Konten:** Blockiert den Zugriff auf den Kontenbereich der Einstellungen-App.
    -   **Zeit und Sprache:** Blockiert den Zugriff auf den Zeit- und Sprachenbereich der Einstellungen-App.
        -   **Änderung der Systemzeit:** Verhindert, dass der Endbenutzer auf dem Gerät Datum und Uhrzeit ändert.
        -   **Änderung von Regionseinstellungen (nur Desktop):** Verhindert, dass der Endbenutzer Regionseinstellungen auf dem Gerät ändert.
        -   **Änderung der Spracheinstellungen (nur Desktop):** Verhindert, dass der Benutzer Spracheinstellungen auf dem Gerät ändert.
    -   **Gaming**: Blockiert den Zugriff auf die Gaming-App in den Einstellungen.
    -   **Erleichterte Bedienung:** Blockiert den Zugriff auf den Bereich „Erleichterte Bedienung“ der Einstellungen-App.
    -   **Datenschutz:** Blockiert den Zugriff auf den Datenschutzbereich der Einstellungen-App.
    -   **Update und Sicherheit:** Blockiert den Zugriff auf den Update- und Sicherheitsbereich der Einstellungen-App.

## <a name="kiosk"></a>Kiosk

-   **Kioskmodus**: Gibt den Typ des [Kioskmodus](https://docs.microsoft.com/en-us/windows/configuration/kiosk-shared-pc) an, der von der Richtlinie unterstützt wird.  Zu den Optionen gehören:

      - **Nicht konfiguriert**: (Standard). Die Richtlinie aktiviert keinen Kioskmodus. 
      - **Kiosk mit einzelner App**: Das Profil aktiviert das Gerät als Kiosk mit einer einzelnen App.
      - **Kiosk mit mehreren Apps**: Das Profil aktiviert das Gerät als Kiosk mit mehreren Apps.

    Für Kioske mit einer einzelnen App sind die folgenden Einstellungen erforderlich:

      - **Benutzerkonto**: Gibt das (auf das Gerät bezogen) lokale Benutzerkonto oder die Azure AD-Kontoanmeldung an, das bzw. die der Kiosk-App zugeordnet ist.  Geben Sie für Konten, die Mitglieder von Azure AD-Domänen sind, das Konto in der Form `domain\\username@tenant.org` an.

         Verwenden Sie für Geräte in öffentlichen Umgebungen Konten mit minimalen Berechtigungen, um autorisierte Aktivitäten zu verhindern.  

      - **Anwendungsbenutzermodell-ID (AUMID) der App**: Gibt die AUMID der Kiosk-App an.  Weitere Informationen finden Sie unter [Find the Application User Model ID of an installed app (Ermitteln der Anwendungsbenutzer-ID einer installierten App)](https://docs.microsoft.com/en-us/windows-hardware/customize/enterprise/find-the-application-user-model-id-of-an-installed-app).

    Für Kioske mit mehreren Anwendungen ist eine Kioskkonfiguration erforderlich.  Verwenden Sie die Schaltfläche **Hinzufügen**, um eine Kioskkonfiguration zu erstellen oder eine vorhandene auszuwählen.

    Kiosk-Konfigurationen für mehrere Apps umfassen die folgenden Einstellungen:

    - **Kioskkonfigurationsname**: Ein Anzeigename, der zur Identifikation einer bestimmten Konfiguration dient.

    - Eine oder mehrere **Kiosk-Apps** mit den folgenden Angaben:

        - **App-Typ** mit dem Typ der Kiosk-App.  Unterstützte Werte:   

            - **Win32-App**: Eine herkömmliche Desktop-App.  (Sie benötigen den vollqualifizierten Pfadnamen der ausführbaren Datei bezogen auf das Gerät.)

            - **UWP-App**: Eine universelle Windows-App.  Sie benötigen die [AUMID für die App](https://docs.microsoft.com/en-us/windows-hardware/customize/enterprise/find-the-application-user-model-id-of-an-installed-app).

        - **App-Bezeichner**: Gibt entweder den vollqualifizierten Pfadnamen für die ausführbare Datei (Win32-Apps) oder die [AUMID der App](https://docs.microsoft.com/en-us/windows-hardware/customize/enterprise/find-the-application-user-model-id-of-an-installed-app) (UWP-Apps) an.

    - **Taskleiste** gibt an, ob die Taskleiste im Kiosk angezeigt wird (**Aktiviert**) oder ausgeblendet ist (**Nicht konfiguriert**).

    - **Layout des Startmenüs**: Gibt eine XML-Datei an, die beschreibt, wie die Apps [im Startmenü dargestellt werden](https://docs.microsoft.com/en-us/windows/configuration/lock-down-windows-10-to-specific-apps#create-xml-file).

    - **Zugewiesene Benutzer**: Gibt ein oder mehrere Benutzerkonten an, die der Kioskkonfiguration zugeordnet sind.  Das Konto ist entweder für das Gerät lokal oder stellt eine Azure AD-Kontoanmeldung dar, die der Kiosk-App zugeordnet ist.  Geben Sie Konten in Domänen in der Form `domain\\username@tenant.org` an.

## <a name="defender"></a>Defender

- **Echtzeitüberwachung:** Aktiviert die Echtzeitüberwachung auf Schadsoftware, Spyware und andere unerwünschte Software.
- **Verhaltensüberwachung:** Ermöglicht Defender, Geräte auf bestimmte bekannte Muster verdächtiger Aktivitäten zu überprüfen.
- **Netzwerkinspektionssystem (NIS):** NIS trägt zum Schutz von Geräten vor netzwerkbasierten Exploits bei. Es verwendet die Signaturen bekannter Sicherheitsrisiken aus dem Microsoft Endpoint Protection Center, um schädlichen Datenverkehr zu erkennen und zu blockieren.
- **Alle Downloads überprüfen:** Steuert, ob Defender alle aus dem Internet heruntergeladenen Dateien überprüft.
- **In Microsoft-Webbrowsern geladene Skripts überprüfen:** Ermöglicht Defender die Überprüfung von Skripts, die in Internet Explorer verwendet werden.
- **Endbenutzerzugriff auf Defender:** Steuert, ob die Benutzeroberfläche von Windows Defender für Endbenutzer ausgeblendet ist.
  Wenn diese Einstellung geändert wird, wird die Änderung wirksam, wenn der Endbenutzer-PC das nächste Mal neu gestartet wird.
- **Intervall für Signaturaktualisierung (in Stunden):** Gibt das Intervall an, in dem Defender auf neue Signaturdateien prüft.
- **Datei- und Programmaktivität überwachen:** Ermöglicht Defender die Überwachung der Datei- und Programmaktivität auf Geräten.
- **Tage bis zum Löschen von in Quarantäne befindlicher Schadsoftware:** Ermöglicht Defender die fortgesetzte Nachverfolgung behandelter Schadsoftware für die angegebene Anzahl von Tagen, damit Sie zuvor betroffene Geräte manuell überprüfen können. Wenn Sie die Anzahl von Tagen auf **0** festlegen, bleibt Schadsoftware im Quarantäneordner und wird nicht automatisch entfernt.
- **CPU-Nutzungslimit während einer Überprüfung:** Ermöglicht die Begrenzung der CPU-Nutzung, die bei Überprüfungen genutzt werden darf (von **1** bis **100**).
- **Archivdateien überprüfen:** Ermöglicht Defender die Überprüfung von Archivdateien wie ZIP- oder CAB-Dateien.
- **Eingehende E-Mail überprüfen:** Ermöglicht Defender das Überprüfen von E-Mail-Nachrichten beim Eingang auf dem Gerät.
- **Bei einer vollständigen Überprüfung Wechseldatenträger überprüfen:** Ermöglicht Defender das Überprüfen von Wechseldatenträgern wie USB-Sticks.
- **Bei einer vollständigen Überprüfung zugeordnete Netzlaufwerke überprüfen:** Ermöglicht Defender das Überprüfen von Dateien auf zugeordneten Netzwerklaufwerken.<br>Wenn die Dateien auf dem Laufwerk schreibgeschützt sind, kann Defender gefundene Schadsoftware nicht entfernen.
- **Über Netzwerkordner geöffnete Dateien überprüfen:** Ermöglicht Defender das Überprüfen von Dateien auf freigegebenen Netzlaufwerken (z.B. Dateien, auf die über einen UNC-Pfad zugegriffen wird).
  Wenn die Dateien auf dem Laufwerk schreibgeschützt sind, kann Defender gefundene Schadsoftware nicht entfernen.
- **Cloudschutz:** Erlaubt oder sperrt den Empfang von Informationen über Schadsoftwareaktivitäten der von Ihnen verwalteten Geräten durch den Microsoft Active Protection Service. Diese Informationen werden verwendet, um den Dienst in der Zukunft zu verbessern.
- **Vor dem Senden von Beispielen bei Benutzern nachfragen:** Steuert, ob potenziell schädliche Dateien, die möglicherweise genauer analysiert werden müssen, automatisch an Microsoft gesendet werden.
- **Uhrzeit für die Durchführung einer täglichen Schnellüberprüfung:** Ermöglicht Ihnen die Planung einer Schnellüberprüfung, die täglich zum ausgewählten Zeitpunkt erfolgt.
- **Art der durchzuführenden Systemüberprüfung:** Ermöglicht die Angabe der Überprüfungsebene für eine geplante Systemüberprüfung.
- **Möglicherweise unerwünschte Software erkennen:** Ermöglicht die Auswahl einer der folgenden Schutzebenen, wenn Windows potenziell unerwünschte Software erkennt:
      - **Blockieren**
      - **Überprüfen** Weitere Informationen zu potenziell unerwünschten Apps finden Sie in [diesem Thema](https://docs.microsoft.com/windows/threat-protection/windows-defender-antivirus/detect-block-potentially-unwanted-apps-windows-defender-antivirus).
- **Aktionen für erkannte Schadsoftwarebedrohungen:** Aktivieren Sie diese Option, um die Maßnahmen zu bestimmen, die Defender bei den einzelnen erkannten Bedrohungsstufen (Niedrig, Mittel, Hoch und Schwerwiegend) ergreifen soll. Sie können folgende Maßnahmen ergreifen:
  -   **Bereinigen**
  -   **Quarantäne**
  -   **Entfernen**
  -   **Zulassen**
  -   **Benutzerdefiniert**
  -   **Blockieren**



## <a name="defender-exclusions"></a>Defender-Ausschlüsse

-   **Dateien und Ordner, die bei Überprüfungen und Echtzeitschutz ausgeschlossen werden sollen:** Fügt Dateien und Ordner wie **C:\Pfad** oder **%ProgramFiles%\Pfad\Dateiname.exe** der Ausschlussliste hinzu. Diese Dateien und Ordner werden nicht in Echtzeitüberprüfungen oder geplante Überprüfungen einbezogen.
-   **Dateierweiterungen, die bei Überprüfungen und Echtzeitschutz ausgeschlossen werden sollen:** Fügt der Ausschlussliste eine oder mehrere Erweiterungen wie **jpg** oder **txt** hinzu. Dateien mit diesen Erweiterungen werden nicht in Echtzeitüberprüfungen oder geplante Überprüfungen einbezogen.
-   **Prozesse, die von Überprüfungen und Echtzeitschutz ausgenommen werden sollen:** Fügt der Ausschlussliste einen oder mehrere Prozesse vom Typ **.exe**, **.com** oder **.scr** hinzu. Diese Prozesse werden nicht in Echtzeitüberprüfungen oder geplante Überprüfungen einbezogen.


## <a name="network-proxy"></a>Netzwerkproxy

-   **Proxyeinstellungen automatisch ermitteln:** Bei Aktivierung versucht das Gerät, den Pfad zu einem PAC-Skript zu finden.
-   **Proxyskript verwenden:** Wählen Sie diese Option, um einen Pfad zu einem PAC-Skript zum Konfigurieren des Proxyservers anzugeben.
    -   **Adress-URL für Setupskript:** Geben Sie die URL eines PAC-Skripts an, das Sie verwenden möchten, um den Proxyserver zu konfigurieren.
-   **Manuellen Proxyserver verwenden:** Wählen Sie diese Option, wenn Sie manuell Proxyserverinformationen angeben möchten.
    -   **Adresse**: Geben Sie den Namen oder die IP-Adresse des Proxyservers an.
    -   **Portnummer:** Geben Sie die Portnummer Ihres Proxyservers ein.
    -   **Proxyausnahmen:** Geben Sie URLs an, die den Proxyserver nicht verwenden dürfen. Trennen Sie die einzelnen Elemente durch Semikola.
    -   **Proxyserver für lokale Adresse umgehen:** Aktivieren Sie diese Option, wenn Sie den Proxyserver nicht für lokale Adressen in Ihrem Intranet verwenden möchten.


## <a name="windows-spotlight"></a>Windows-Blickpunkt


- **Windows-Blickpunkt:** Verwenden Sie diese Einstellung, um auf Windows 10-Geräten alle Funktionen von Windows-Blickpunkt zu blockieren. Wenn Sie diese Einstellung blockieren, sind die folgenden Einstellungen nicht verfügbar.
    - **Windows-Blickpunkt auf dem Sperrbildschirm:** Verhindert, dass Windows-Blickpunkt Informationen auf dem Gerätesperrbildschirm anzeigt.
    - **Drittanbietervorschläge in Windows-Blickpunkt:** Verhindert, dass Windows-Blickpunkt Inhalte vorschlägt, die nicht von Microsoft stammen.
    - **Endbenutzerfeatures:** Blockiert Endbenutzerfeatures wie Startmenüvorschläge und Mitgliedschaftsbenachrichtigungen.
    - **Windows-Tipps:** Blockiert die Anzeige von Popuptipps in Windows.
    - **Windows-Blickpunkt im Info-Center:** Verhindert, dass Vorschläge von Windows-Blickpunkt wie neue Apps oder Sicherheitsinhalte im Windows-Info-Center angezeigt werden.
    - **Personalisierung von Windows-Blickpunkt:** Verhindert, dass Windows-Blickpunkt Ergebnisse basierend auf der Nutzung eines Geräts personalisiert.
    - **Windows-Begrüßungsseite:** Blockiert die Windows-Begrüßungsseite, die dem Benutzer Informationen zu neuen oder aktualisierten Funktionen anzeigt.


## <a name="projection"></a>Projektion

- **Benutzereingabe über Empfänger der drahtlosen Anzeige:** Blockiert Benutzereingaben über Empfänger der drahtlosen Anzeige.
- **Projektion auf diesem PC:** Verhindert, dass andere Geräte den PC für die Projektion erkennen.
- **PIN für Kopplung erforderlich:** Erfordert eine PIN beim Herstellen der Verbindung mit einem Projektionsgerät.

## <a name="start"></a>Starten

- **Apps von der Taskleiste lösen:** Hindert den Benutzer daran, Apps vom Startmenü zu lösen.
- **Dokumente im Startmenü:** Blendet den Ordner „Dokumente“ im Windows-Startmenü aus oder ein.
- **Downloads im Startmenü:** Blendet den Ordner „Downloads“ im Windows-Startmenü aus oder ein.
- **Datei-Explorer im Startmenü:** Blendet die Datei-Explorer-App im Windows-Startmenü aus oder ein.
- **Heimnetzgruppe im Startmenü:** Blendet den Ordner „Heimnetzgruppe“ im Windows-Startmenü aus oder ein.
- **Musik im Startmenü:** Blendet den Ordner „Musik“ im Windows-Startmenü aus oder ein.
- **Netzwerk im Startmenü:** Blendet den Ordner „Netzwerk“ im Windows-Startmenü aus oder ein.
- **Persönlicher Ordner im Startmenü**: Blendet den persönlichen Ordner im Windows-Startmenü aus oder ein.
- **Bilder im Startmenü:** Blendet den Ordner für Bilder im Windows-Startmenü aus oder ein.
- **Einstellungen im Startmenü:** Blendet die Einstellungen-App im Windows-Startmenü aus oder ein.
- **Videos im Startmenü:** Blendet den Ordner für Videos im Windows-Startmenü aus oder ein.
