---
title: Verwalten des Webzugriffs mit der Managed Browser-App
titlesuffix: Azure portal
description: "Stellen Sie die Managed Browser-Anwendung bereit, um das Webbrowsen und die Übertragung von Webdaten an andere Apps einzuschränken.\""
keywords: 
author: erikre
ms.author: erikre
manager: angrobe
ms.date: 11/06/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 1feca24f-9212-4d5d-afa9-7c171c5e8525
ms.reviewer: maxles
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 7619efc305881f1ad56a7c14e5d92c05fb0c6d77
ms.sourcegitcommit: 67ec0606c5440cffa7734f4eefeb7121e9d4f94f
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/08/2017
---
# <a name="manage-internet-access-using-managed-browser-policies-with-microsoft-intune"></a>Verwalten des Internetzugriffs mittels Richtlinien für Managed Browser mit Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Managed Browser ist eine Webbrowser-App, die Sie aus öffentlichen App-Stores für die Verwendung in Ihrer Organisation herunterladen können. Nach der Konfiguration mit Intune kann Managed Browser:
- Auf Unternehmenswebsites und SaaS-Apps mit einmaliger Anmeldung über den MyApps-Dienst zugreifen, während Webdaten geschützt bleiben.
- Mit einer Liste von URLs und Domänen vorkonfiguriert werden, um die Möglichkeit des Zugriffs des Benutzers auf Websites im Unternehmenskontext zu beschränken.
- Mit einer Startseite und von Ihnen angegebenen Lesezeichen vorkonfiguriert werden.

Da diese App die Integration mit dem Intune SDK aufweist, können Sie auch App-Schutzrichtlinien auf sie anwenden, wie beispielsweise:
- Steuern der Verwendung von Ausschneiden, Kopieren und Einfügen
- Verhindern von Bildschirmaufnahmen
- Sicherstellen, dass Links zu Inhalten, die von Benutzern ausgewählt werden, nur in anderen verwalteten Apps geöffnet werden

Weitere Information finden Sie unter [Was sind App-Schutzrichtlinien?](/intune/app-protection-policy).

Sie können diese Einstellungen auf Folgendes anwenden:

- Geräte, die bei Intune registriert sind
- Geräte, die bei einem anderen MDM-Produkt registriert sind
- Nicht verwaltete Geräte

Wenn Benutzer Managed Browser aus dem App Store installieren und die App nicht von Intune verwaltet wird, kann sie als einfacher Webbrowser mit Unterstützung für einmaliges Anmelden über die Microsoft MyApps-Website verwendet werden. Benutzer werden direkt an die MyApps-Website weitergeleitet, wo alle ihre bereitgestellten SaaS-Anwendungen angezeigt werden.
Während Managed Browser nicht von Intune verwaltet wird, kann nicht auf Daten aus anderen von Intune verwalteten Anwendungen zugegriffen werden. 

Managed Browser unterstützt nicht das Kryptografieprotokoll von Secure Sockets Layer-Version 3 (SSLv3).

Sie können Managed Browser-Richtlinien für die folgenden Gerätetypen erstellen:

-   Geräte unter Android 4 und höher

-   Geräte unter iOS 8.0 und höher

>[!IMPORTANT]
>Ab Oktober 2017 unterstützt die Intune Managed Browser-App für Android nur noch Geräte mit Android 4.4 oder höher. Die Intune Managed Browser-App unter iOS unterstützt nur noch Geräte mit iOS 9.0 oder höher.
>Frühere Versionen von Android und iOS können Managed Browser weiterhin verwenden, allerdings können keine neuen Versionen der App installiert werden, und einige App-Funktionen sind möglicherweise nicht verfügbar. Es wird empfohlen, dass Sie diese Geräte auf eine unterstützte Betriebssystemversion aktualisieren.


Intune Managed Browser unterstützt das Öffnen von Webinhalten von [Microsoft Intune-Anwendungspartnern](https://www.microsoft.com/server-cloud/products/microsoft-intune/partners.aspx).

## <a name="create-a-managed-browser-app-configuration"></a>Erstellen einer Managed Browser-App-Konfiguration

1.  Melden Sie sich beim Azure-Portal an.
2.  Wählen Sie **Weitere Dienste** > **Überwachung und Verwaltung** > **Intune** aus.
3.  Gehen Sie zur Liste „Verwalten“ auf dem Blatt **Mobile Apps**, und wählen Sie die Option **App-Konfigurationsrichtlinien** aus.
4.  Wählen Sie auf dem Blatt **App-Konfigurationsrichtlinien** die Option **Hinzufügen** aus.
5.  Geben Sie auf dem Blatt **App-Konfiguration hinzufügen** einen **Namen** und optional eine **Beschreibung** für die App-Konfigurationseinstellungen ein.
6.  Wählen Sie als Typ der **Geräteregistrierung** die Option **Verwaltete Apps** aus.
7.  Wählen Sie **Erforderliche Apps auswählen** aus, und wählen Sie auf dem Blatt **Ziel-Apps** die Option **Managed Browser** für iOS, für Android oder für beides aus.
8.  Wählen Sie **OK** aus, um zum Blatt **App-Konfiguration hinzufügen** zurückzukehren.
9.  Wählen Sie **Konfigurationseinstellungen** aus. Auf dem Blatt **Konfiguration** definieren Sie Schlüssel-Wert-Paare, um Konfigurationen für Managed Browser bereitzustellen. In den folgenden Abschnitten erhalten Sie weitere Informationen zu den unterschiedlichen Schlüssel-Wert-Paaren, die Sie definieren können.
10. Wählen Sie abschließend **OK** aus.
11. Wählen Sie auf dem Blatt **App-Konfiguration hinzufügen** die Option **Erstellen** aus.
12. Die neue Konfiguration wird erstellt und auf dem Blatt **App-Konfiguration** angezeigt.

>[!IMPORTANT]
>Derzeit verwendet Managed Browser die automatische Registrierung. Damit die App-Konfigurationen angewendet werden können, muss eine andere Anwendung auf dem Gerät bereits mit den Intune-App-Schutzrichtlinien verwaltet werden.

## <a name="assign-the-configuration-settings-you-created"></a>Zuweisen der erstellten Konfigurationseinstellungen

Sie weisen die Einstellungen Azure AD-Gruppen von Benutzern zu. Haben diese Benutzer die Managed Browser-App installiert, wird die App durch die angegebenen Einstellungen verwaltet.

1. Wählen Sie auf dem Blatt **Einstellungen** im Intune-Dashboard für die Verwaltung von mobilen Anwendungen **App-Konfiguration** aus.
2. Wählen Sie aus der Liste der App-Konfigurationen diejenige aus, die Sie zuweisen möchten.
3. Wählen Sie auf dem nächsten Blatt **Benutzergruppen** aus.
4. Wählen Sie auf dem Blatt **Benutzergruppen** die Azure AD-Gruppe aus, die Sie der App-Konfiguration zuweisen möchten, und wählen Sie dann **OK** aus.


## <a name="how-to-configure-application-proxy-settings-for-the-managed-browser"></a>Konfigurieren von Anwendungsproxyeinstellungen für Managed Browser

Intune Managed Browser und [Azure AD-Anwendungsproxy]( https://docs.microsoft.com/azure/active-directory/active-directory-application-proxy-get-started) können gemeinsam verwendet werden, um die folgenden Szenarios für Benutzer von iOS- und Android-Geräten zu unterstützen:

- Ein Benutzer lädt die Microsoft Outlook-App herunter und meldet sich an. Die Intune-App-Schutzrichtlinien werden automatisch angewendet. Diese verschlüsseln gespeicherte Daten und hindern den Benutzer daran, Unternehmensdateien auf nicht verwaltete Apps oder Speicherorte auf dem Gerät zu übertragen. Klickt der Benutzer dann auf einen Link zu einem Intranetwebsite in Outlook, können Sie angeben, dass der Link in der Managed Browser-App anstatt in einem anderen Browser geöffnet wird. Managed Browser erkennt, dass diese Intranetwebsite dem Benutzer über den Anwendungsproxy verfügbar gemacht wurde. Benutzer werden automatisch über den Anwendungsproxy zur Authentifizierung mit jeder anwendbaren Multi-Factor Authentication und bedingtem Zugriff weitergeleitet, bevor sie die Intranetwebsite erreichen. Auf diese Website, die im Remotezugriff zuvor noch nicht gefunden werden konnte, kann nun zugegriffen werden, und der Link funktioniert in Outlook erwartungsgemäß.
- Ein Remotebenutzer öffnet die Managed Browser-Anwendung und navigiert mit der internen URL zu einer Intranetwebsite. Managed Browser erkennt, dass diese Intranetwebsite dem Benutzer über den Anwendungsproxy verfügbar gemacht wurde. Benutzer werden automatisch über den Anwendungsproxy zur Authentifizierung mit jeder anwendbaren Multi-Factor Authentication und bedingtem Zugriff weitergeleitet, bevor sie die Intranetwebsite erreichen. Auf diese Website, die im Remotezugriff zuvor noch nicht gefunden werden konnte, kann nun zugegriffen werden.

### <a name="before-you-start"></a>Vorbereitung

- Richten Sie Ihre internen Anwendungen über den Azure AD-Anwendungsproxy ein.
    - Informationen zum Konfigurieren des Anwendungsproxys und zum Veröffentlichen von Anwendungen finden Sie in der [Setup-Dokumentation]( https://docs.microsoft.com/azure/active-directory/active-directory-application-proxy-get-started#how-to-get-started). 
- Die Managed Browser-App muss in der Version 1.2.0 oder höher ausgeführt werden.
- Benutzer der Managed Browser-App verfügen über eine der App zugewiesene [Intune-App-Schutzrichtlinie]( app-protection-policy.md).
Hinweis: Es kann bis zu 24 Stunden dauern, bis aktualisierte Anwendungsproxy-Umleitungsdaten in Managed Browser in Kraft treten.

#### <a name="step-1-enable-automatic-redirection-to-the-managed-browser-from-outlook"></a>Schritt 1: Aktivieren der automatischen Umleitung zu Managed Browser aus Outlook
Outlook muss mit einer App-Schutzrichtlinie konfiguriert werden, mit der Einstellung **Anzeige von Webinhalten auf den Managed Browser beschränken** möglich ist.

#### <a name="step-2-assign-an-app-configuration-policy-assigned-for-the-managed-browser"></a>Schritt 2: Zuweisen einer App-Konfigurationsrichtlinie für Managed Browser
Dieses Verfahren konfiguriert die Managed Browser-App, damit die App-Proxyumleitung verwendet wird. Geben Sie mit dem Verfahren zum Erstellen einer Managed Browser-App-Konfiguration das folgende Schlüssel-Wert-Paar an:

|||
|-|-|
|Key|Wert|
|**com.microsoft.intune.mam.managedbrowser.AppProxyRedirection**|**TRUE**|


## <a name="how-to-configure-the-homepage-for-the-managed-browser"></a>Konfigurieren der Homepage für Managed Browser

Mit dieser Einstellung können Sie die Startseite konfigurieren, die Benutzern beim Starten von Managed Browser oder beim Erstellen einer neuen Registerkarte angezeigt wird. Geben Sie mit dem Verfahren zum Erstellen einer Managed Browser-App-Konfiguration das folgende Schlüssel-Wert-Paar an:

|||
|-|-|
|Key|Wert|
|**com.microsoft.intune.mam.managedbrowser.homepage**|Geben Sie eine gültige URL ein. Ungültige URLs werden zur Sicherheit gesperrt.<br>Beispiel: **https://www.bing.com**|


## <a name="how-to-configure-bookmarks-for-the-managed-browser"></a>Konfigurieren von Lesezeichen für Managed Browser

Mit dieser Einstellung können Sie einen Satz Lesezeichen konfigurieren, der den Benutzern von Managed Browser zur Verfügung steht.

- Diese Lesezeichen können von den Benutzern nicht gelöscht oder bearbeitet werden.
- Diese Lesezeichen werden oben in der Liste angezeigt. Alle von den Benutzern erstellten Lesezeichen werden unterhalb dieser Lesezeichen angezeigt.
- Wenn Sie die App-Proxyumleitung aktiviert haben, können Sie App-Proxy-Web-Apps mit deren interner oder externer URL hinzufügen.

Geben Sie mit dem Verfahren zum Erstellen einer Managed Browser-App-Konfiguration das folgende Schlüssel-Wert-Paar an:

|||
|-|-|
|Key|Wert|
|**com.microsoft.intune.mam.managedbrowser.bookmarks**|Der Wert für diese Konfiguration ist eine Liste von Lesezeichen. Jedes Lesezeichen besteht aus dem Lesezeichentitel und der Lesezeichen-URL. Trennen Sie Titel und URL mit dem **&#124;**-Zeichen.<br><br>Beispiel: **Microsoft Bing&#124;https://www.bing.com**<br><br>Zum Konfigurieren von mehreren Lesezeichen trennen Sie jedes Paar mit einem doppelten **&#124;&#124;**-Zeichen.<br><br>Beispiel: **Bing&#124;https://www.bing.com&#124;&#124;Contoso&#124;https://www.contoso.com**|

## <a name="how-to-specify-allowed-and-blocked-urls-for-the-managed-browser"></a>Angeben von zugelassenen und blockierten URLs für Managed Browser

Geben Sie mit dem Verfahren zum Erstellen einer Managed Browser-App-Konfiguration das folgende Schlüssel-Wert-Paar an:

|||
|-|-|
|Key|Wert|
|Wählen Sie aus:<br><br>- Angeben von zugelassenen URLs (nur diese URLs sind zugelassen, auf keine weiteren Websites kann zugegriffen werden): **com.microsoft.intune.mam.managedbrowser.AllowListURLs**<br><br>- Angeben von blockierten URLs (auf alle anderen Websites kann zugegriffen werden): <br><br>**com.microsoft.intune.mam.managedbrowser.BlockListURLs**|Der entsprechende Wert für den Schlüssel ist eine Liste mit URLs. Geben Sie alle URLs, die Sie zulassen oder blockieren möchten, als einen einzelnen Wert ein, der durch einen senkrechten Strich **&#124;** getrennt ist.<br><br>Beispiele:<br><br>**URL1&#124;URL2&#124;URL3**<br>**http://*.contoso.com/*&#124;https://*.bing.com/*&#124;https://expenses.contoso.com**|

>[!IMPORTANT]
>Geben Sie nicht beide Schlüssel an. Wenn beide Schlüssel für einen Benutzer eingerichtet sind, wird der Schlüssel für zugelassene URLs verwendet, da dies die restriktivste Option ist.
>Stellen Sie außerdem sicher, dass Sie keine wichtigen Seiten wie Ihre Unternehmenswebsites blockieren.

### <a name="url-format-for-allowed-and-blocked-urls"></a>URL-Format für zulässige und blockierte URLs
Nachfolgend wird erläutert, welche Formate und Platzhalter Sie zum Festlegen von URLs in den Zulassungs- und Blockierungslisten verwenden können:

-   Sie können das Platzhaltersymbol (**&#42;**) gemäß den Regeln in der folgenden Liste mit zulässigen Mustern verwenden:

-   Stellen Sie sicher, dass Sie bei der Eingabe in die Liste allen URLs **http** oder **https** voranstellen.

-   Sie können Portnummern in der Adresse angeben. Wenn Sie keine Portnummer angeben, werden folgende Werte verwendet:

    -   Port 80 für http

    -   Port 443 für https

    Die Verwendung von Platzhaltern für die Portnummer wird nicht unterstützt. **http&colon;//www&period;contoso&period;com:*;** und **http&colon;//www&period;contoso&period;com: /*;** werden beispielsweise nicht unterstützt.

-   In der folgenden Tabelle sind die zulässigen Muster aufgeführt, die Sie zum Festlegen von URLs verwenden können:

|URL|Details|Treffer|Stimmt nicht überein mit|
|-------|---------------|-----------|------------------|
|http://www.contoso.com|Entspricht einer einzelnen Seite|www.contoso.com|host.contoso.com<br /><br />www.contoso.com/images<br /><br />contoso.com/|
|http://contoso.com|Entspricht einer einzelnen Seite|contoso.com/|host.contoso.com<br /><br />www.contoso.com/images<br /><br />www.contoso.com|
|http://www.contoso.com/&#42;|Entspricht allen URLs, die mit „www.contoso.com“ beginnen|www.contoso.com<br /><br />www.contoso.com/images<br /><br />www.contoso.com/videos/tvshows|host.contoso.com<br /><br />host.contoso.com/images|
|http://&#42;.contoso.com/&#42;|Entspricht allen Unterdomänen unter „contoso.com“|developer.contoso.com/resources<br /><br />news.contoso.com/images<br /><br />news.contoso.com/videos|contoso.host.com|
|http://www.contoso.com/images|Entspricht einem einzelnen Ordner|www.contoso.com/images|www.contoso.com/images/dogs|
|http://www.contoso.com:80|Entspricht einer einzelnen Seite mit einer Portnummer|http://www.contoso.com:80|
|https://www.contoso.com|Entspricht einer einzelnen, sicheren Seite|https://www.contoso.com|http://www.contoso.com|
|http://www.contoso.com/images/&#42;|Entspricht einem einzelnen Ordner und allen Unterordnern|www.contoso.com/images/dogs<br /><br />www.contoso.com/images/cats|www.contoso.com/videos|

-   Im Folgenden Beispiele für Eingaben, die nicht unterstützt werden:

    -   &#42;.com

    -   &#42;.contoso/&#42;

    -   www.contoso.com/&#42;images

    -   www.contoso.com/&#42;images&#42;pigs

    -   www.contoso.com/page&#42;

    -   IP-Adressen

    -   https://&#42;

    -   http://&#42;

    -   http://www.contoso.com:&#42;

    -   http://www.contoso.com: /&#42;

## <a name="how-to-access-to-managed-app-logs-using-the-managed-browser-on-ios"></a>Zugreifen auf Protokolle von verwalteten Apps mithilfe des Managed Browsers unter iOS

Endbenutzer, auf deren iOS-Gerät der Managed Browser installiert ist, können den Verwaltungsstatus aller von Microsoft veröffentlichten Apps anzeigen. Sie können Protokolle für die Problembehandlung ihrer verwalteten iOS-Apps senden.

1. Öffnen Sie die iOS-**Einstellungen**.
2. Wählen Sie die Anwendungseinstellungen für den **Managed Browser** aus.
3. Schalten Sie **Intune-Diagnose aktivieren** um, um den Browser in den Problembehandlungsmodus zu versetzen.
4. Öffnen Sie den **Managed Browser**. Klicken Sie auf **Intune-App-Status anzeigen**, um die Richtlinieneinstellungen für einzelne Anwendungen zu überprüfen.
5. Drücken Sie **Erste Schritte** und **Protokolle freigeben** oder **Protokolle an Microsoft senden**, um die Problembehandlungsprotokolle an Ihren IT-Administrator oder an Microsoft zu senden.

Sie können den Browser außerdem auch aus der App im Problembehandlungsmodus öffnen.

1. Öffnen Sie den Managed Browser.
2. Geben Sie im Adressfeld `about:intunehelp` ein.
Der Browser wird im Problembehandlungsmodus gestartet.

Eine Liste der in den App-Protokollen gespeicherten Einstellungen finden Sie unter [Prüfung der App-Schutzprotokolle in Managed Browser](app-protection-policy-settings-log.md).

## <a name="security-and-privacy-for-the-managed-browser"></a>Sicherheit und Datenschutz für Managed Browser

-   Einstellungen, die Benutzer für den integrierten Browser auf ihren Geräten vornehmen, werden von Managed Browser nicht verwendet. Managed Browser kann auf diese Einstellungen nicht zugreifen.

-   Wenn Sie die Option **Einfache PIN für den Zugriff erforderlich** oder **Unternehmensanmeldeinformationen für den Zugriff erforderlich** in einer App-Schutzrichtlinie konfigurieren, die Managed Browser zugeordnet ist, und ein Benutzer auf der Authentifizierungsseite den Hilfelink auswählt, kann er beliebige Websites besuchen. Dies gilt unabhängig davon, ob sie in der Richtlinie einer Blockierungsliste hinzugefügt wurden.

-   Managed Browser kann den Zugriff auf Websites nur blockieren, wenn direkt darauf zugegriffen wird. Der Zugriff auf die Website wird nicht blockiert, wenn dafür Zwischendienste (z.B. ein Übersetzungsdienst) verwendet werden.

-   Um die Authentifizierung und den Zugriff auf die Intune-Dokumentation zuzulassen, ist **&#42;.microsoft.com** von den Zulassungs- oder Blockierungslisten ausgenommen. und immer zulässig.

### <a name="turn-off-usage-data"></a>Deaktivieren von Nutzungsdaten
Microsoft sammelt automatisch anonyme Daten über die Leistung und die Verwendung von Managed Browser, um Microsoft-Produkte und -Dienste zu verbessern. Benutzer können die Erfassung von Daten mithilfe der Einstellung für **Nutzungsdaten** auf ihren Geräten deaktivieren. Sie haben keine Kontrolle über die Erfassung dieser Daten.


-   Auf iOS-Geräten können von Benutzern besuchte Websites, deren Zertifikat abgelaufen oder nicht vertrauenswürdig ist, nicht geöffnet werden.
-   Einstellungen, die Benutzer für den integrierten Browser auf ihren Geräten vornehmen, werden von Managed Browser nicht verwendet. Managed Browser kann auf diese Einstellungen nicht zugreifen.

-   Wenn Sie die Option **Einfache PIN für den Zugriff erforderlich** oder **Unternehmensanmeldeinformationen für den Zugriff erforderlich** in einer App-Schutzrichtlinie konfigurieren, die Managed Browser zugeordnet ist, und ein Benutzer auf der Authentifizierungsseite den Hilfelink auswählt, kann er beliebige Websites besuchen. Dies gilt unabhängig davon, ob sie in der Richtlinie einer Blockierungsliste hinzugefügt wurden.

-   Managed Browser kann den Zugriff auf Websites nur blockieren, wenn direkt darauf zugegriffen wird. Der Zugriff auf die Website wird nicht blockiert, wenn dafür Zwischendienste (z.B. ein Übersetzungsdienst) verwendet werden.

-   Um die Authentifizierung und den Zugriff auf die Intune-Dokumentation zuzulassen, ist **&#42;.microsoft.com** von den Zulassungs- oder Blockierungslisten ausgenommen. und immer zulässig.

### <a name="turn-off-usage-data"></a>Deaktivieren von Nutzungsdaten
Microsoft sammelt automatisch anonyme Daten über die Leistung und die Verwendung von Managed Browser, um Microsoft-Produkte und -Dienste zu verbessern. Benutzer können die Erfassung von Daten mithilfe der Einstellung für **Nutzungsdaten** auf ihren Geräten deaktivieren. Sie haben keine Kontrolle über die Erfassung dieser Daten.
