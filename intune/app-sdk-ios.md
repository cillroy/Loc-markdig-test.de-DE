---
title: "Microsoft Intune App SDK für iOS –Entwicklerhandbuch"
description: "Mit dem Microsoft Intune App SDK für iOS können Sie die Intune-App-Schutzrichtlinien in Form von Mobile App Management (MAM) in Ihre iOS-App integrieren."
keywords: 
author: erikre
manager: angrobe
ms.author: erikre
ms.date: 11/10/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 8e280d23-2a25-4a84-9bcb-210b30c63c0b
ms.reviewer: oydang
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 6ff0e98c710676c257822c14661e6908849ae053
ms.sourcegitcommit: 67ec0606c5440cffa7734f4eefeb7121e9d4f94f
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/08/2017
---
# <a name="microsoft-intune-app-sdk-for-ios-developer-guide"></a>Microsoft Intune App SDK für iOS –Entwicklerhandbuch

> [!NOTE]
> Lesen Sie am besten zuerst das Handbuch [Erste Schritte mit dem Microsoft Intune App SDK](app-sdk-get-started.md). Dort finden Sie Informationen zu den Vorbereitungen, die Sie auf den verschiedenen unterstützten Plattformen für die Integration treffen müssen.

Mit dem Microsoft Intune App SDK für iOS können Sie die Intune-App-Schutzrichtlinien (auch als **APP**- oder **MAM-Richtlinien** bezeichnet) in Ihre native iOS-App integrieren. MAM-fähige Anwendungen sind in das Intune App SDK integrierte Anwendungen. Sie ermöglichen IT-Administratoren, App-Schutzrichtlinien für Ihre mobile App bereitzustellen, wenn diese aktiv von Intune verwaltet wird.

## <a name="prerequisites"></a>Voraussetzungen

* Sie benötigen einen Mac OS-Computer, auf dem OS X 10.8.5 oder höher ausgeführt wird, und auf dem Xcode 8 oder höher installiert hat.

* Ihre App muss für iOS 9 oder höher vorgesehen sein.

* Lesen Sie [die Lizenzbedingungen für das Intune App SDK für iOS (in englischer Sprache)](https://github.com/msintuneappsdk/ms-intune-app-sdk-ios/blob/master/Microsoft%20License%20Terms%20Intune%20App%20SDK%20for%20iOS%20.pdf). Drucken Sie die Lizenzbedingungen aus, und heben Sie eine Kopie für Ihre Unterlagen auf. Indem Sie das Intune App SDK für iOS herunterladen und verwenden, stimmen Sie diesen Lizenzbestimmungen zu.  Wenn Sie sie nicht akzeptieren, dürfen Sie die Software nicht verwenden.

* Laden Sie die Dateien für das Intune App SDK für iOS von [GitHub](https://github.com/msintuneappsdk/ms-intune-app-sdk-ios) herunter.

## <a name="whats-in-the-sdk"></a>Inhalt des SDK

Das Intune App SDK für iOS enthält eine statische Bibliothek, Ressourcendateien, API-Header, eine PLIST-Datei Liste mit Debug-Einstellungen sowie ein Konfigurationstool. Mobile Apps können einfach nur die Ressourcendateien enthalten und statisch mit den Bibliotheken verknüpft sein, um die meisten Richtlinien durchzusetzen. Erweiterte Intune-MAM-Funktionen werden mithilfe von APIs erzwungen.

Dieses Handbuch befasst sich mit der Verwendung der folgenden Komponenten des Intune App SDK für iOS:

* **libIntuneMAM.a**: Die statische Intune App SDK-Bibliothek. Wenn Ihre App keine Extensions verwendet, können Sie diese Bibliothek mit Ihrem Projekt verknüpfen, um die App für die mobile Anwendungsverwaltung mit Intune zu aktivieren.

* **IntuneMAM.framework**: Das Intune App SDK-Framework. Verknüpfen Sie dieses Framework mit Ihrem Projekt, um die App für die mobile Anwendungsverwaltung mit Intune zu aktivieren. Verwenden Sie das Framework anstelle der statischen Bibliothek, wenn Ihre App Extensions verwendet, damit vom Projekt nicht mehrere Kopien der statischen Bibliothek erstellt werden.

* **IntuneMAMResources.Bundle**: Ein Ressourcenpaket, das die Ressourcen für das SDK enthält.

* **Headers**: Stellt die Intune App SDK-APIs bereit. Wenn Sie eine API verwenden, müssen Sie die Headerdatei einschließen, die die API enthält. Die folgenden Headerdateien enthalten die APIs, die Datentypen und die Protokolle, die vom Intune App SDK für Entwickler zur Verfügung gestellt wurden:

    * IntuneMAMAppConfig.h
    * IntuneMAMAppConfigManager.h
    * IntuneMAMDataProtectionInfo.h
    * IntuneMAMDataProtectionManager.h
    * IntuneMAMDefs.h
    * IntuneMAMEnrollmentDelegate.h
    * IntuneMAMEnrollmentManager.h
    * IntuneMAMEnrollmentStatus.h
    * IntuneMAMFileProtectionInfo.h
    * IntuneMAMFileProtectionManager.h
    * IntuneMAMLogger.h
    * IntuneMAMPolicy.h
    * IntuneMAMPolicyDelegate.h
    * IntuneMAMPolicyManager.h
    * IntuneMAMVersionInfo.h
    
Entwickler können die Inhalte aller oben stehenden Header verfügbar machen, indem sie nur IntuneMAM.h importieren.


## <a name="how-the-intune-app-sdk-works"></a>Funktionsweise des Intune App SDK

Ziel des Intune App SDK für iOS ist es, iOS-Anwendungen mit minimalen Codeänderungen mit Verwaltungsfunktionen zu versehen. Möglichst wenige Codeänderungen bedeuten kürzere Markteinführungszeiten, ohne die Konsistenz und Stabilität Ihrer mobilen Anwendung zu beeinträchtigen.


## <a name="build-the-sdk-into-your-mobile-app"></a>Integrieren des SDK in Ihre mobile App

Gehen Sie folgendermaßen vor, um das Intune App SDK zu aktivieren:

1. **Option 1 (empfohlen)**: Verknüpfen Sie `IntuneMAM.framework` mit Ihrem Projekt. Ziehen Sie `IntuneMAM.framework` in die Liste für **eingebettete Binärdateien** des Projektziels.

    > [!NOTE]
    > Bei Verwendung des Frameworks müssen Sie die Simulatorarchitekturen manuell aus dem universellen Framework entfernen, bevor Sie Ihre App an den App Store übermitteln. Weitere Informationen siehe [Übermitteln Ihrer App an den App Store](#Submit-your-app-to-the-App-Store).

2. **Option 2**: Stellen Sie eine Verknüpfung zur `libIntuneMAM.a`-Bibliothek her. Ziehen Sie die `libIntuneMAM.a`-Bibliothek in die Liste **Verknüpfte Frameworks und Bibliotheken** des Projektziels.

    ![Intune App SDK iOS – verknüpfte Frameworks und Bibliotheken](./media/intune-app-sdk-ios-linked-frameworks-and-libraries.png)

    Fügen Sie `-force_load {PATH_TO_LIB}/libIntuneMAM.a` einem der folgenden Pfade hinzu, wobei Sie `{PATH_TO_LIB}` durch den Speicherort des Intune App SDK ersetzen:
      * Der Buildkonfigurationseinstellung `OTHER_LDFLAGS` des Projekts
      * **Other Linker Flags** der Benutzeroberfläche

        > [!NOTE]
        > Um den `PATH_TO_LIB` zu suchen, wählen Sie die Datei `libIntuneMAM.a` und dann im Menü **Datei** die Option **Informationen abrufen** aus. Kopieren Sie den **Pfad** aus dem Abschnitt **Allgemein** im Fenster **Info**.

    Fügen Sie das Ressourcenpaket `IntuneMAMResources.bundle` zum Projekt hinzu, indem Sie es in **Buildphasen** unter **Paketressourcen kopieren** ziehen.

    ![Intune App SDK iOS: Paketressourcen kopieren](./media/intune-app-sdk-ios-copy-bundle-resources.png)

3. Fügen Sie diese iOS-Frameworks zum Projekt hinzu:
    * MessageUI.framework
    * Security.framework
    * MobileCoreServices.framework
    * SystemConfiguration.framework
    * libsqlite3.tbd
    * libc++.tbd
    * ImageIO.framework
    * LocalAuthentication.framework
    * AudioToolbox.framework

4. Wenn in Ihrer mobilen App in der Datei „Info.plist“ eine Haupt-NIB- oder Hauptstoryboard-Datei definiert ist, entfernen Sie die Felder **Hauptstoryboard** oder **Haupt-NIB**. Fügen Sie diese Felder und ihre jeweiligen Werte in „Info.plist“ unter einem neuen Wörterbuch mit Namen **IntuneMAMSettings** mit den folgenden Schlüsselnamen (sofern zutreffend) hinzu:
    * MainStoryboardFile
    * MainStoryboardFile~ipad
    * MainNibFile
    * MainNibFile~ipad
    > [!NOTE]
  > Wenn in Ihrer mobilen App in der Datei „Info.plist“ keine Haupt-NIB- oder Hauptstoryboard-Datei definiert ist, sind diese Einstellungen nicht erforderlich.

    Sie können die Datei „Info.plist“ im Raw-Format anzeigen (um die Schlüsselnamen zu sehen), indem Sie im Dokument mit der rechten Maustaste auf eine beliebige Stelle klicken und den Anzeigetyp in **Show Raw Keys/Values** ändern.

5. Aktivieren Sie die Freigabe des Schlüsselbunds (sofern noch nicht geschehen), indem Sie in jedem Projektziel **Capabilities** auswählen und den Schalter **Keychain Sharing** aktivieren. Die Freigabe des Schlüsselbunds ist erforderlich, damit Sie mit dem nächsten Schritt fortfahren können.

  > [!NOTE]
    > Ihr Bereitstellungsprofil muss neue Werte für die Freigabe des Schlüsselbunds unterstützen. Die Schlüsselbund-Zugriffsgruppen sollten ein Platzhalterzeichen unterstützen. Sie können dies überprüfen, indem Sie die Datei „.mobileprovision“ in einem Text-Editor öffnen, nach **keychain-access-groups** suchen und sich vergewissern, dass ein Platzhalter vorhanden ist. Beispiel:
    ```xml
    <key>keychain-access-groups</key>
    <array>
    <string>YOURBUNDLESEEDID.*</string>
    </array>
    ```

6. Nachdem Sie die Freigabe des Schlüsselbunds aktiviert haben, folgen Sie den nachstehenden Schritten, um eine separate Zugriffsgruppe zu erstellen, in der das Intune App SDK seine Daten speichert. Sie können eine Zugriffsgruppe für den Schlüsselbund über die Benutzeroberfläche oder mithilfe der Berechtigungsdatei erstellen. Wenn Sie die Benutzeroberfläche zum Erstellen der Zugriffsgruppe für den Schlüsselbund verwenden, führen Sie unbedingt die folgenden Schritte aus:

    1. Wenn in Ihrer mobilen App keine Zugriffsgruppen für den Schlüsselbund definiert sind, fügen Sie die Paket-ID der App als erste Gruppe hinzu.

    2. Fügen Sie die freigegebene Zugriffsgruppe für den Schlüsselbund `com.microsoft.intune.mam` Ihren vorhandenen Zugriffsgruppen hinzu. Diese Zugriffsgruppe wird vom Intune App SDK zum Speichern von Daten verwendet.

    3. Fügen Sie `com.microsoft.adalcache` zu Ihren vorhandenen Zugriffsgruppen hinzu.

        ![Intune App SDK für iOS: Schlüsselbund gemeinsam nutzen](./media/intune-app-sdk-ios-keychain-sharing.png)

    4. Wenn Sie die Berechtigungsdatei direkt bearbeiten, anstatt die oben gezeigte Xcode-Benutzeroberfläche zum Erstellen der Schlüsselbund-Zugriffsgruppen zu verwenden, setzen Sie `$(AppIdentifierPrefix)` vor die Schlüsselbund-Zugriffsgruppen (Xcode verarbeitet dies automatisch). Beispiel:

            * `$(AppIdentifierPrefix)com.microsoft.intune.mam`
            * `$(AppIdentifierPrefix)com.microsoft.adalcache`

    > [!NOTE]
    > Eine Berechtigungsdatei ist eine für die mobile Anwendung eindeutige XML-Datei. Sie wird zum Festlegen spezieller Berechtigungen und Funktionen in Ihrer iOS-App verwendet. Wenn Ihre App vorher noch keine Berechtigungsdatei hatte, sollte die Aktivierung der Schlüsselbundfreigabe (Schritt 6) dazu geführt haben, dass Xcode eine für Ihre App generiert hat.

7. Wenn die Definition von URL-Schemas der App in deren Info.plist-Datei erfolgt, fügen Sie ein weiteres Schema mit dem Suffix `-intunemam` für jedes URL-Schema hinzu.

8. Wenn die App Dokumenttypen in der „Info.plist“-Datei definiert, fügen Sie für das Array „Document Content Type UTIs“ jedes Elements einen duplizierten Eintrag für jede Zeichenfolge mit dem Präfix „com.microsoft.intune.mam.“ hinzu.

9. Bei mobilen Apps, die in iOS 9+ entwickelt wurden, nehmen Sie jedes Protokoll, das Ihre App an `UIApplication canOpenURL` übergibt, in das `LSApplicationQueriesSchemes`-Array der Info.plist-Datei Ihrer App auf. Darüber hinaus fügen Sie `-intunemam` für jedes aufgeführte Protokoll ein neues Protokoll hinzu. Sie müssen auch `http-intunemam`, `https-intunemam`und `ms-outlook-intunemam` in das Array einschließen.

10. Wenn in den Berechtigungen der App App-Gruppen definiert sind, fügen Sie diese Gruppen dem **IntuneMAMSettings**-Wörterbuch unter dem `AppGroupIdentifiers`-Schlüssel als Zeichenfolgenarray hinzu.

## <a name="using-the-intune-mam-configurator-tool"></a>Verwenden des Intune-MAM-Konfigurationstools

Das Intune-MAM-Konfigurationstool übernimmt jetzt alle Änderungen an info.plist-Dateien, die für die manuelle Integration des SDKs erforderlich sind. Sie finden es im Repository für das Intune-App-SDK für iOS. Die zusätzlichen App-spezifischen Einstellungen, wie etwa Multi-ID, AAD-Einstellungen usw. werden nicht von diesem Tool verarbeitet. Das Tool weist 3 Parameter auf:
 
|Eigenschaft|Verwendung|
|---------------|--------------------------------|
|- i |  `<Path to the input plist>` |
|- e | Die Berechtigungsdatei |
|- o |  (Optional) `<Path for the changed input plist>` |
    
Das Intune-MAM-Konfigurationstool kann für diese Aktualisierungen verwendet werden:
* Alle Hauptstoryboard- und/oder Haupt-Nib-Dateien Ihrer App in IntuneMAMSettings.
* Alle definierten URL-Schemas Ihrer App in deren Info.plist-Datei mit dem Suffix „-intunemam“ für jedes URL-Schema.
* Alle definierten Dokumenttypen Ihrer App in deren Info.plist-Datei für das Array „Document Content Type UTIs“; außerdem erstellt das Tool für jede Zeichenfolge ein Duplikat und fügt ihm das Präfix „com.microsoft.intune.mam.“ hinzu.
* Alle App-Gruppen Ihrer Datei, die in deren Berechtigungen definiert sind; diese werden dem IntuneMAMSettings-Wörterbuch unter dem Schlüssel „AppGroupIdentifiers“ als Zeichenfolgenarray hinzugefügt.
    
> [!Note]
> Wenn Sie sich für die Verwendung dieses Tools anstelle der manuellen Bearbeitung der info.plist-Datei entscheiden, empfehlen wir, es erneut auszuführen, sobald Änderungen an der info.plist-Datei oder den Berechtigungen Ihrer Datei vorgenommen wurden.

## <a name="configure-azure-active-directory-authentication-library-adal"></a>Konfigurieren der Authentifizierungsbibliothek von Azure Active Directory (Active Directory Authentication Library, ADAL)

Das Intune App SDK verwendet die [Authentifizierungsbibliothek von Azure Active Directory](https://github.com/AzureAD/azure-activedirectory-library-for-objc) für die Authentifizierung und bedingte Startszenarien. Es verwendet ADAL außerdem zum Registrieren der Benutzeridentität beim MAM-Dienst für Verwaltungsszenarien ohne Geräteregistrierung.

Normalerweise setzt ADAL voraus, dass Apps sich bei Azure Active Directory (AAD) registrieren und eine eindeutige ID (Client-ID) sowie weitere Bezeichner abrufen, um die Sicherheit der Token zu gewährleisten, die an die Anwendung übermittelt werden. Sofern nicht anders angegeben, verwendet das Intune App SDK bei der Kontaktaufnahme mit Azure AD standardmäßige Registrierungswerte.  

Wenn Ihre App bereits ADAL zum Authentifizieren von Benutzern verwendet, muss sie ihre vorhandenen Registrierungswerte verwenden und die Standardwerte des Intune App SDK überschreiben. Dadurch wird sichergestellt, dass Benutzer nicht zweimal zur Authentifizierung aufgefordert werden (einmal vom Intune App SDK und einmal von der App).

### <a name="recommendations"></a>Empfehlungen

Ihre App sollte mit der [aktuellen Version von ADAL](https://github.com/AzureAD/azure-activedirectory-library-for-objc/releases) auf deren Hauptverzweigung verknüpft sein. Das Intune App SDK verwendet derzeit den Brokerbranch von ADAL, um Apps zu unterstützen, für die bedingter Zugriff erforderlich ist. (Diese Apps hängen daher von der Microsoft Authenticator-App ab.) Das SDK ist trotzdem mit dem Hauptbranch von ADAL kompatibel. Verwenden Sie den Branch, der für Ihre App geeignet ist.

### <a name="link-to-adal-binaries"></a>Verknüpfung mit ADAL-Binärdateien

Gehen Sie folgendermaßen vor, um Ihre App mit den ADAL-Binärdateien zu verknüpfen:

1. Laden Sie die [Authentifizierungsbibliothek von Azure Active Directory (ADAL) für Objective-C](https://github.com/AzureAD/azure-activedirectory-library-for-objc) von GitHub herunter, und befolgen Sie dann die [Anweisungen](https://github.com/AzureAD/azure-activedirectory-library-for-objc/blob/master/README.md) zum Herunterladen von ADAL mithilfe von Git-Submodulen oder CocoaPods.

2. Schließen Sie das `ADALiOSBundle.bundle` in das Projekt ein, indem Sie das Ressourcenpaket unter **Copy Bundle Resources** nach **Build Phases** ziehen.

3. Fügen Sie `-force_load {PATH_TO_LIB}/libADALiOS.a` der `OTHER_LDFLAGS`-Buildkonfigurationseinstellung des Projekts hinzu, oder legen Sie auf der Benutzeroberfläche **Other Linker Flags** fest. `PATH_TO_LIB` sollte durch den Speicherort der ADAL-Binärdateien ersetzt werden.



### <a name="share-the-adal-token-cache-with-other-apps-signed-with-the-same-provisioning-profile"></a>Freigeben des ADAL-Tokencaches für andere Apps, die mit dem gleichen Bereitstellungsprofil signiert wurden?**

Befolgen Sie die unten stehenden Anweisungen, wenn Sie ADAL-Token für Apps freigeben möchten, die mit dem gleichen Bereitstellungsprofil signiert wurden:

1. Wenn in Ihrer App keine Zugriffsgruppen für den Schlüsselbund definiert sind, fügen Sie die Paket-ID der App als erste Gruppe hinzu.

2. Aktivieren Sie ADAL-SSO (einmaliges Anmelden), indem Sie den Schlüsselbundberechtigungen die Zugriffsgruppen `com.microsoft.adalcache` und `com.microsoft.workplacejoin` hinzufügen.

3. Falls Sie die Schlüsselbundgruppe für den freigegebenen ADAL-Cache explizit festlegen, achten Sie darauf, dass sie auf `<app_id_prefix>.com.microsoft.adalcache` festgelegt ist. ADAL legt dies für Sie fest, sofern Sie die Einstellung nicht außer Kraft setzen. Wenn Sie eine benutzerdefinierte Schlüsselbundgruppe angeben möchten, die `com.microsoft.adalcache` ersetzt, geben Sie sie in der Datei „Info.plist“ mithilfe des Schlüssels `ADALCacheKeychainGroupOverride` unter „IntuneMAMSettings“ an.

### <a name="configure-adal-settings-for-the-intune-app-sdk"></a>Konfigurieren der ADAL-Einstellungen für das Intune App SDK

Wenn Ihre Anwendung bereits ADAL für die Authentifizierung verwendet und über eigene ADAL-Einstellungen verfügt, können Sie die Verwendung der gleichen Einstellungen durch das Intune App SDK während der Authentifizierung bei Azure Active Directory erzwingen. Dadurch wird sichergestellt, dass die App den Benutzer nicht zweimal zur Authentifizierung auffordert. Unter [Configure settings for the Intune App SDK](#configure-settings-for-the-intune-app-sdk) (Konfigurieren der Einstellungen für das Intune App SDK) finden Sie Informationen zum Auffüllen der folgenden Einstellungen:  

* ADALClientId
* ADALAuthority
* ADALRedirectUri
* ADALRedirectScheme
* ADALCacheKeychainGroupOverride

Wenn Ihre App bereits ADAL verwendet, sind die folgenden Konfigurationen erforderlich:

1. Geben Sie in der Datei „Info.plist“ des Projekts unter dem **IntuneMAMSettings**-Wörterbuch mit dem Schlüsselnamen `ADALClientId` die für ADAL-Aufrufe zu verwendende Client-ID an.

2. Geben Sie außerdem im **IntuneMAMSettings**-Wörterbuch mit dem Schlüsselnamen `ADALAuthority` die Azure AD-Autorität an.

3. Geben Sie außerdem im **IntuneMAMSettings**-Wörterbuch mit dem Schlüsselnamen `ADALRedirectUri` den Umleitungs-URI an, mit dem ADAL-Aufrufe durchgeführt werden sollen. Je nach dem Format des Umleitungs-URIs Ihrer App müssen Sie auch das `ADALRedirectScheme` angeben.


Außerdem können Sie die URL der Azure AD-Autorität zur Laufzeit durch eine mandantenspezifische URL ersetzen. Legen Sie zu diesem Zweck einfach die `aadAuthorityUriOverride`-Eigenschaft auf der `IntuneMAMPolicyManager`-Instanz fest.

> [!NOTE]
> Das Festlegen der URL der Azure AD-Autorität ist für [APP ohne Geräteregistrierung](#App-protection-policy-without-device-enrollment) erforderlich, um dem SDK die erneute Verwendung des ADAL-Aktualisierungstokens, das von der App abgefangen wurde, zu ermöglichen.

Das SDK verwendet weiterhin die URL dieser Autorität für die Aktualisierung von Richtlinien und alle nachfolgenden Registrierungsanforderungen, sofern der Wert nicht gelöscht oder geändert wird.  Daher ist es wichtig, den Wert zu löschen, wenn sich ein verwalteter Benutzer bei der App abmeldet, und den Wert zurückzusetzen, wenn sich ein neuer verwalteter Benutzer anmeldet.

### <a name="if-your-app-does-not-use-adal"></a>Wenn Ihre Anwendung ADAL nicht verwendet

Wenn Ihre Anwendung ADAL nicht verwendet, stellt das Intune App SDK Standardwerte für ADAL-Parameter bereit und verarbeitet die Authentifizierung über Azure AD. Sie müssen keine Werte für die oben aufgeführten ADAL-Einstellungen angeben.

## <a name="app-protection-policy-without-device-enrollment"></a>App-Schutzrichtlinie ohne Geräteregistrierung

### <a name="overview"></a>Übersicht
Intune-App-Schutzrichtlinie ohne Geräteregistrierung, auch bekannt als **APP-WE** oder MAM-WE – ermöglicht, dass Apps von Intune verwaltet werden können, ohne dass das Gerät bei der Verwaltung mobiler Geräte (MDM) von Intune registriert sein muss. Um diese neue Funktionalität zu unterstützen, muss die App an der Registrierung von Benutzerkonten für die Verwaltung zu teilnehmen. Um die neuen APIs zu verwenden, gehen Sie folgendermaßen vor:

1. Verwenden Sie die neueste Version des Intune App SDKs, die Verwaltung von Geräten mit oder ohne Geräteregistrierung unterstützt.

2. Fügen Sie allen Dateien, die die APIs aufrufen, „IntuneMAMEnrollment.h“ hinzu.

### <a name="register-user-accounts"></a>Registrieren von Benutzerkonten

Eine App kann App-Schutzrichtlinien vom Intune-Dienst empfangen, wenn die App im Auftrag eines angegebenen Benutzerkontos bei dem APP-WE-Dienst registriert ist. Es ist Aufgabe der App, alle neu angemeldeten Benutzer beim SDK zu registrieren. Nachdem das neue Benutzerkonto authentifiziert wurde, sollte die App die `registerAndEnrollAccount`-Methode unter „Headers/IntuneMAMEnrollment.h“ aufrufen:

```objc
/**


 *  This method will add the account to the list of registered accounts.
 *  An enrollment request will immediately be started.
 *  @param identity The UPN of the account to be registered with the SDK
 */

(void)registerAndEnrollAccount:(NSString *)identity;

```
Durch Aufrufen der `registerAndEnrollAccount`-Methode registriert das SDK das Benutzerkonto und versucht, die App im Auftrag dieses Kontos zu registrieren. Wenn bei der Registrierung aus irgendeinem Grund ein Fehler auftritt, versucht das SDK die Registrierung 24 Stunden später automatisch erneut. Zu Debugzwecken kann die App über einen Stellvertreter Benachrichtigungen zu den Ergebnissen von Registrierungsanforderungen empfangen.

Nachdem diese API aufgerufen wurde, kann die Anwendung anschließend normal funktionieren. Wenn die Registrierung erfolgreich ist, benachrichtigt das SDK den Benutzer, dass ein Neustart der App erforderlich ist. Zu diesen Zeitpunkt kann der Benutzer die App sofort neu starten.

### <a name="deregister-user-accounts"></a>Aufheben der Registrierung von Benutzerkonten

Bevor ein Benutzer bei einer App abgemeldet wird, sollte die App die Registrierung des Benutzers beim SDK aufheben. Dadurch wird Folgendes sichergestellt:

1. Für das Konto des Benutzers werden keine wiederholten Registrierungsversuche mehr ausgeführt.

2. Die App-Schutzrichtlinie wird entfernt.

3. Wenn die App ein selektives Zurücksetzen einleitet (optional), werden alle Unternehmensdaten gelöscht.

Bevor der Benutzer abgemeldet wird, sollte die App die folgende API unter `Headers/IntuneMAMEnrollment.h` aufrufen:

```objc
/*
 *  This method will remove the provided account from the list of
 *  registered accounts.  Once removed, if the account has enrolled
 *  the application, the account will be un-enrolled.
 *  @note In the case where an un-enroll is required, this method will block
 *  until the Intune MAM AAD token is acquired, then return.  This method must be called before  
 *  the user is removed from the application (so that required AAD tokens are not purged
 *  before this method is called).
 *  @param identity The UPN of the account to be removed.
 *  @param doWipe   If YES, a selective wipe if the account is un-enrolled
 */

(void)deRegisterAndUnenrollAccount:(NSString *)identity withWipe:(BOOL)doWipe;
```

Diese Methode muss aufgerufen werden, bevor die Azure AD-Token des Benutzerkontos gelöscht werden. Das SDK benötigt das/die AAD-Token des Benutzerkontos, um im Auftrag des Benutzers spezifische Anforderungen an den APP-WE-Dienst zu senden.

Wenn die App die Unternehmensdaten des Benutzers aus eigenem Antrieb löscht, kann das `doWipe`-Flag auf FALSCH festgelegt werden. Andernfalls kann die App das selektive Zurücksetzen vom SDK initiieren lassen. Dies führt zu einem Aufruf des Stellvertreters der App für das selektive Zurücksetzen.

```objc
[[IntuneMAMEnrollmentManager instance] deRegisterAndUnenrollAccount:@”user@foo.com” withWipe:YES];
```

### <a name="apps-that-do-not-use-adal"></a>Apps, die nicht ADAL verwenden

Apps, die den Benutzer nicht mit ADAL anmelden, können trotzdem App-Schutzrichtlinien vom Intune-Dienst empfangen, indem sie die API aufrufen, um die Authentifizierung vom SDK ausführen zu lassen. Apps sollten diese Technik verwenden, wenn zwar keine Benutzer mit Azure AD authentifiziert wurden, aber trotzdem App-Schutzrichtlinien zum Schutz der Daten abgerufen werden müssen. Beispielsweise, wenn ein anderer Authentifizierungsdienst für die App-Anmeldung verwendet wird oder wenn die App überhaupt kein Anmelden unterstützt. Zu diesem Zweck sollte die Anwendung die `loginAndEnrollAccount`-Methode unter „Headers/IntuneMAMEnrollment.h“ aufrufen:

```objc
/**
 *  Creates an enrollment request which is started immediately.
 *  If no token can be retrieved for the identity, the user will be prompted
 *  to enter their credentials, after which enrollment will be retried.
 *  @param identity The UPN of the account to be logged in and enrolled.
 */
 (void)loginAndEnrollAccount: (NSString *)identity;

```

Durch Aufrufen dieser Methode wird der Benutzer vom SDK zur Eingabe von Anmeldeinformationen aufgefordert, wenn kein vorhandenes Token gefunden wird. Das SDK versucht dann, die App im Auftrag des angegebenen Benutzerkontos beim APP-WE-Dienst zu registrieren. Die Methode kann mit der Identität „nil“ aufgerufen werden. In diesem Fall nimmt das SDK die Registrierung mit dem vorhandenen verwalteten Benutzer auf dem Gerät vor oder fordert den Benutzer zur Eingabe eines Benutzernamens auf, wenn kein vorhandener Benutzer gefunden wird.

Bei einem Fehler bei der Registrierung sollte die App den erneuten Aufruf dieser API zu einem späteren Zeitpunkt vorsehen, je nach den Fehlerdetails. Die App kann über einen Stellvertreter [Benachrichtigungen](#Status-result-and-debug-notifications) zu den Ergebnissen von Registrierungsanforderungen empfangen.

Nachdem diese API aufgerufen wurde, kann die App anschließend normal funktionieren. Wenn die Registrierung erfolgreich ist, benachrichtigt das SDK den Benutzer, dass ein Neustart der App erforderlich ist.

## <a name="status-result-and-debug-notifications"></a>Status-, Ergebnis- und Debugbenachrichtigungen

Die App kann Status-, Ergebnis- und Debugbenachrichtigungen zu den folgenden Anforderungen an den Intune MAM-Dienst empfangen:

 - Registrierungsanforderungen
 - Anforderungen zur Richtlinienaktualisierung
 - Anforderungen zur Aufhebung der Registrierung

Die Benachrichtigungen werden über Stellvertretermethoden in `Headers/IntuneMAMEnrollmentDelegate.h` angezeigt:

```objc
/**
 *  Called when an enrollment request operation is completed.
 * @param status status object containing debug information
 */

(void)enrollmentRequestWithStatus:(IntuneMAMEnrollmentStatus *)status;

/**
 *  Called when a MAM policy request operation is completed.
 *  @param status status object containing debug information
 */
(void)policyRequestWithStatus:(IntuneMAMEnrollmentStatus *)status;

/**
 *  Called when a un-enroll request operation is completed.
 *  @Note: when a user is un-enrolled, the user is also de-registered with the SDK
 *  @param status status object containing debug information
 */

(void)unenrollRequestWithStatus:(IntuneMAMEnrollmentStatus *)status;

```

Diese Stellvertretermethoden geben ein `IntuneMAMEnrollmentStatus`-Objekt zurück, das die folgenden Informationen enthält:

- Die Identität der Kontos, dem die Anforderung zugeordnet ist
- Ein Statuscode, der das Ergebnis der Anforderung anzeigt
- Eine Fehlerzeichenfolge mit einer Beschreibung des Statuscodes
- Ein `NSError`-Objekt

Dieses Objekt ist in `IntuneMAMEnrollmentStatus.h` zusammen mit den spezifischen Statuscodes definiert, die zurückgegeben werden können.


### <a name="sample-code"></a>Beispielcode

Die folgenden Beispiele zeigen Implementierungen der Stellvertretermethoden:

```objc
- (void)enrollmentRequestWithStatus:(IntuneMAMEnrollmentStatus *)status
{
    NSLog(@"enrollment result for identity %@ with status code %ld", status.identity, (unsigned long)status.statusCode);
    NSLog(@"Debug Message: %@", status.errorString);
}


- (void)policyRequestWithStatus:(IntuneMAMEnrollmentStatus *)status
{
    NSLog(@"policy check-in result for identity %@ with status code %ld", status.identity, (unsigned long)status.statusCode);
    NSLog(@"Debug Message: %@", status.errorString);
}

- (void)unenrollRequestWithStatus:(IntuneMAMEnrollmentStatus *)status
{
    NSLog(@"un-enroll result for identity %@ with status code %ld", status.identity, (unsigned long)status.statusCode);
    NSLog(@"Debug Message: %@", status.errorString);
}

```

## <a name="app-restart"></a>Neustart der App

Wenn eine Anwendung zum ersten Mal App-Schutzrichtlinien empfängt, muss sie neu gestartet werden, um die erforderlichen Hooks anzuwenden. Um die App zu benachrichtigen, dass ein Neustart erfolgen muss, stellt das SDK eine Stellvertretermethode in „Headers/IntuneMAMPolicyDelegate.h“ zur Verfügung.

```objc
 - (BOOL) restartApplication
```
Der Rückgabewert dieser Methode teilt dem SDK mit, ob die Anwendung den erforderlichen Neustart übernehmen muss:   

 - Wenn „true“ zurückgegeben wird, muss die Anwendung den Neustart ausführen.   

 - Wenn FALSCH zurückgegeben wird, führt das SDK den Neustart der Anwendung aus, nachdem diese Methode zurückgegeben wurde. Das SDK zeigt sofort ein Dialogfeld an, in dem der Benutzer zum Neustarten der Anwendung aufgefordert wird.

## <a name="customize-your-apps-behavior"></a>Passen Sie das Verhalten Ihrer App an

Das Intune App SDK hat mehrere APIs, die Sie aufrufen können, um Informationen über die App-Schutzrichtlinie in Intune zu erhalten, die der App bereitgestellt wurde. Diese Daten können Sie benutzen, um das Verhalten Ihrer App anzupassen. Die meisten Einstellungen für App-Schutzrichtlinien werden automatisch vom SDK und nicht von der Anwendung erzwungen. Die einzige Einstellung, die die App implementieren sollte, ist das Steuerelement „Speichern unter“.

### <a name="get-app-protection-policy"></a>Abrufen der App-Schutzrichtlinie

#### <a name="intunemampolicymanagerh"></a>IntuneMAMPolicyManager.h
Die Klasse „IntuneMAMPolicyManager“ stellt die App-Schutzrichtlinie für Intune, die für die App bereitgestellt wurde, bereit. Sie stellt besonders APIs bereit, die beim [Aktivieren mehrerer Identitäten](#-enable-multi-identity-optional) nützlich sind.

#### <a name="intunemampolicyh"></a>IntuneMAMPolicy.h
Die „IntuneMAMPolicy“-Klasse stellt die App-Schutzrichtlinie für Intune, die für die App bereitgestellt wurde, bereit. Die meisten der in dieser Klasse bereitgestellten Richtlinieneinstellungen werden vom SDK erzwungen, aber Sie haben immer die Möglichkeit, das Verhalten Ihrer App anzupassen, je nachdem, wie Richtlinieneinstellungen erzwungen werden.

Diese Klasse stellt einige APIs bereit, die für die Implementierung von „Speichern unter“-Steuerelementen benötigt werden; Details dazu finden Sie im nächsten Abschnitt.

### <a name="implement-save-as-controls"></a>Implementieren von „Speichern unter“-Steuerelementen

Mit Intune können IT-Administratoren auswählen, an welchem Speicherort eine verwaltete App Daten speichern kann. Mit der **isSaveToAllowedForLocation**-API können Apps das Intune-App SDK nach zulässigen Speicherorten abfragen, wie in **IntuneMAMPolicy.h** definiert.

Bevor Apps verwaltete Daten in einem Cloudspeicher oder einem lokalen Pfad speichern können, müssen sie mit der **isSaveToAllowedForLocation**-API überprüfen, ob der IT-Administrator erlaubt hat, die Daten dort zu speichern.

Bei Verwendung der **isSaveToAllowedForLocation**-API müssen Apps den UPN für den Speicherort einreichen, falls er verfügbar ist.

#### <a name="supported-save-locations"></a>Unterstützte Speicherorte

Die **isSaveToAllowedForLocation**-API stellt Konstanten bereit, um zu prüfen, ob der IT-Administrator das Speichern von Daten an folgenden Orten erlaubt, wie in IntuneMAMPolicy.h definiert:

* IntuneMAMSaveLocationOther
* IntuneMAMSaveLocationOneDriveForBusiness
* IntuneMAMSaveLocationSharePoint
* IntuneMAMSaveLocationLocalDrive

Apps sollten die Konstanten in der **isSaveToAllowedForLocation**-API verwenden, um zu überprüfen, ob Daten an Speicherorten gespeichert werden können, die als „verwaltet“ (z. B. OneDrive for Business) oder „privat“ gelten. Darüber hinaus sollte die API verwendet werden, wenn die App nicht ermitteln kann, ob es sich um „verwaltete“ oder „private“ Speicherorte handelt.

Persönliche Speicherorte werden durch die Konstante `IntuneMAMSaveLocationOther` repräsentiert.

Die Konstante `IntuneMAMSaveLocationLocalDrive` sollte verwendet werden, wenn die App Daten an einem beliebigen Speicherort auf dem lokalen Gerät speichert.

## <a name="configure-settings-for-the-intune-app-sdk"></a>Konfigurieren der Einstellungen für Intune App SDK

Sie können das Wörterbuch **IntuneMAMSettings** in der Datei „info.plist“ der Anwendung verwenden, um das Intune App SDK einzurichten und zu konfigurieren. Wenn das IntuneMAMSettings-Wörterbuch in der Datei „Info.plist“ nicht angezeigt wird, sollten Sie ein Wörterbuch in der „Info.plist“ Ihrer App mit dem Feldnamen „IntuneMAMSettings.“ erstellen.

Im IntuneMAMSettings-Wörterbuch können Sie Schlüssel-Wert-Zeilen mit Konfigurationseinstellungen zum Konfigurieren des SDK hinzufügen. Die folgende Tabelle enthält eine Liste aller unterstützten Einstellungen.

Einige dieser Einstellungen wurden möglicherweise schon in vorherigen Abschnitten erörtert, und einige gelten nicht für alle Apps.

Einstellung  | Typ  | Definition | Erforderlich?
--       |  --   |   --       |  --
ADALClientId  | Zeichenfolge  | Die Azure AD-Client-ID der App. | Erforderlich, wenn die App ADAL verwendet. |
ADALAuthority | Zeichenfolge | Die aktive Azure AD-Autorität. Dort wo AAD-Konten konfiguriert wurden, sollten Sie Ihre eigene Umgebung verwenden. | Erforderlich, wenn die App ADAL verwendet. Wenn dieser Wert nicht vorhanden ist, wird der Intune-Standard verwendet.|
ADALRedirectUri  | Zeichenfolge  | Der Azure AD-Umleitungs-URI der App. | ADALRedirectUri oder ADALRedirectScheme ist erforderlich, wenn die App ADAL verwendet.  |
ADALRedirectScheme  | Zeichenfolge  | Das Azure AD-Umleitungsschema der App. Dies kann anstelle von ADALRedirectUri verwendet werden, wenn der Umleitungs-URI der App im Format `scheme://bundle_id` vorliegt. | ADALRedirectUri oder ADALRedirectScheme ist erforderlich, wenn die App ADAL verwendet. |
ADALLogOverrideDisabled | Boolesch  | Gibt an, ob das SDK alle ADAL-Protokolle (einschließlich ADAL-Aufrufe von der App, sofern zutreffend) in die eigene Protokolldatei einschließt. Standardwert ist "NO". Legen Sie den Wert auf „YES“ fest, wenn die App einen eigenen ADAL-Protokollrückruf festlegt. | (Optional) |
ADALCacheKeychainGroupOverride | Zeichenfolge  | Gibt die Schlüsselbundgruppe an, die für den ADAL-Cache anstelle von „com.microsoft.adalcache“ verwendet werden soll. Beachten Sie, dass diese das App-ID-Präfix nicht enthält. Das Präfix wird der angegebenen Zeichenfolge zur Laufzeit vorangestellt. | (Optional) |
AppGroupIdentifiers | Zeichenfolgenarray  | Ein Array mit App-Gruppen aus dem Berechtigungsabschnitt "com.apple.security.application-groups" der App. | Erforderlich, wenn die App Anwendungsgruppen verwendet. |
ContainingAppBundleId | Zeichenfolge | Gibt die Paket-ID der Anwendung an, die die Erweiterung enthält. | Erforderlich für iOS-Extensions. |
DebugSettingsEnabled| Boolesch | Bei der Einstellung JA können innerhalb des Einstellungspakets Testrichtlinien angewendet werden. Diese Einstellungen sollte bei ausgelieferten Anwendungen *nicht* aktiviert sein. | (Optional) |
MainNibFile<br>MainNibFile~ipad  | Zeichenfolge  | Diese Einstellung sollte den Namen der Haupt-NIB-Datei der Anwendung enthalten.  | Erforderlich, wenn MainNibFile für die Anwendung in der Datei „Info.plist“ definiert ist. |
MainStoryboardFile<br>MainStoryboardFile~ipad  | Zeichenfolge  | Diese Einstellung sollte den Namen der Haupt-Storyboard-Datei der Anwendung enthalten. | Erforderlich, wenn UIMainStoryboardFile für die Anwendung in der Datei „Info.plist“ definiert ist. |
AutoEnrollOnLaunch| Boolesch| Gibt an, ob die App versuchen soll, sich beim Start automatisch zu registrieren, wenn eine vorhandene verwaltete Identität erkannt wurde und dies noch nicht passiert ist. Standardwert ist "NO". <br><br> Hinweise: Wenn keine verwaltete Identität gefunden wird oder kein gültiges Token für die Identität im ADAL-Cache verfügbar ist, schlägt die Registrierung ohne die Anforderung nach Anmeldeinformationen im Hintergrund fehl, es sei denn, MAMPolicyRequired ist auf JA festgelegt. | (Optional) |
MAMPolicyRequired| Boolesch| Gibt an, ob das Starten der App blockiert ist, wenn die App über keine Intune App-Schutzrichtlinie verfügt. Standardwert ist "NO". <br><br> Hinweise: Apps, bei denen die MAMPolicyRequired-Einstellung auf „JA“ festgelegt ist, können nicht im App Store eingereicht werden. Wenn MAMPolicyRequired auf JA festgelegt wird, muss auch AutoEnrollOnLaunch auf JA festgelegt werden. | (Optional) |
MAMPolicyWarnAbsent | Boolesch| Gibt an, ob die App den Benutzer beim Start warnt, wenn die App keine App-Schutzrichtlinie für Intune hat. <br><br> Hinweis: Benutzer dürfen noch immer die App ohne Richtlinie verwenden, nachdem die Warnung verworfen wurde. | (Optional) |
MultiIdentity | Boolesch| Gibt an, ob die App den Umgang mit mehreren Identitäten beherrscht. | (Optional) |
SplashIconFile <br>SplashIconFile~ipad | Zeichenfolge  | Gibt die Datei für das Intune-Begrüßungssymbol (Startsymbol) an. | (Optional) |
SplashDuration | Zahl | Mindestdauer in Sekunden, für die der Intune Startbildschirm beim Anwendungsstart angezeigt wird. Standardwert ist 1,5. | (Optional) |
BackgroundColor| Zeichenfolge| Gibt die Hintergrundfarbe für den Start- und den PIN-Bildschirm an. Akzeptiert eine hexadezimale RGB-Zeichenfolge im Format „#XXXXXX“, wobei X Werte von 0-9 bzw. A-F annehmen kann. Das Gatterzeichen kann ausgelassen werden.   | (Optional) Der Standardwert ist „Hellgrau“. |
ForegroundColor| Zeichenfolge| Gibt die Vordergrundfarbe für den Start- und den PIN-Bildschirm an, etwa die Textfarbe. Akzeptiert eine hexadezimale RGB-Zeichenfolge im Format „#XXXXXX“, wobei X Werte von 0-9 bzw. A-F annehmen kann. Das Gatterzeichen kann ausgelassen werden.  | (Optional) Der Standardwert ist „Schwarz“. |
AccentColor | Zeichenfolge| Gibt die Akzentfarbe für den PIN-Bildschirm an, etwa die Textfarbe einer Schaltfläche oder die Hervorhebungsfarbe für ein Feld. Akzeptiert eine hexadezimale RGB-Zeichenfolge im Format „#XXXXXX“, wobei X Werte von 0-9 bzw. A-F annehmen kann. Das Gatterzeichen kann ausgelassen werden.| (Optional) Der Standardwert ist „Blau“ (Systemfarbe). |
MAMTelemetryDisabled| Boolesch| Gibt an, ob das SDK keine Telemetriedaten an sein Back-End sendet.| (Optional) |
WebViewHandledURLSchemes | Array von Zeichenfolgen | Gibt die URL-Schemas an, die WebView für Ihre App verarbeitet. | Erforderlich, wenn Ihre App WebView verwendet, das URLs über Verknüpfungen und/oder JavaScript verarbeitet. |  

> [!NOTE]
> Gemäß den App Store-Standards muss `MAMPolicyRequired` auf „NO“ festgelegt sein, wenn Ihre App im App Store veröffentlicht werden soll.

## <a name="enabling-mam-targeted-configuration-for-your-ios-applications"></a>Aktivieren der MAM-Zielkonfiguration für Ihre iOS-Anwendungen
Die MAM-Zielkonfiguration ermöglicht, dass eine App Konfigurationsdaten über das Intune App SDK erhalten kann. Das Format und die Varianten dieser Daten müssen definiert und Intune-Kunden vom Besitzer oder Entwickler der Anwendung mitgeteilt werden. Intune-Administratoren können Konfigurationsdaten über das Intune Azure-Portal als Ziel festlegen und bereitstellen. Beim Intune App SDK für iOS (Version 7.0.1) können Apps, die an der MAM-Zielkonfiguration teilnehmen, über den MAM-Dienst mit MAM-Zielkonfigurationsdaten versorgt werden. Die Anwendungskonfigurationsdaten werden durch unseren MAM-Dienst direkt an die App übertragen, und nicht über den MDM-Kanal. Das Intune App SDK stellt eine Klasse für den Zugriff auf die Daten bereit, die aus diesen Konsolen abgerufen wurden. Folgende Voraussetzungen sind erforderlich: <br>
* Die App muss für MAM-WE registriert werden, bevor Sie auf die Benutzeroberfläche der MAM-Zielkonfiguration zugreifen. Weitere Informationen zu MAM-WE finden Sie unter [App-Schutzrichtlinie ohne Geräteregistrierung im Intune App SDK-Entwicklerhandbuch](https://docs.microsoft.com/en-us/intune/app-sdk-ios#app-protection-policy-without-device-enrollment).
* In der Quelldatei der App muss ```IntuneMAMAppConfigManager.h``` enthalten sein.
* Rufen Sie ```[[IntuneMAMAppConfig instance] appConfigForIdentity:]``` auf, um das App-Konfigurationsobjekt zu erhalten.
* Rufen Sie den entsprechenden Selektor auf dem Objekt ```IntuneMAMAppConfig``` auf. Wenn es sich zum Beispiel beim Schlüssel Ihrer Anwendung um eine Zeichenfolge handeln, könnten Sie ```stringValueForKey``` oder ```allStringsForKey``` verwenden. Die Datei ```IntuneMAMAppConfig.h header``` enthält Rückgabewerte und Fehlerbedingungen.

Weitere Informationen zu den Funktionen der Graph-API in Bezug auf die MAM-Zielkonfigurationswerte finden Sie unter [Graph API Reference MAM Targeted Config (Graph-API-Referenz für MAM-Zielkonfigurationen)](https://graph.microsoft.io/en-us/docs/api-reference/beta/api/intune_mam_targetedmanagedappconfiguration_create). <br>

Weitere Informationen zum Erstellen einer MAM-Zielkonfigurationsrichtlinie für Apps in iOS finden Sie im Abschnitt zu MAM-Zielkonfiguration für Apps unter [How to use Microsoft Intune app configuration policies for iOS (Verwenden von Microsoft Intune-App-Konfigurationsrichtlinien für iOS)](https://docs.microsoft.com/en-us/intune/app-configuration-policies-use-ios).

## <a name="telemetry"></a>Telemetrie

Standardmäßig protokolliert das Intune App SDK für iOS Telemetriedaten zu den folgenden Nutzungsereignissen. Diese Daten werden an Microsoft Intune gesendet.

* **Start der App**: Übermittelt an Microsoft Intune Daten zur Nutzung von MAM-aktivierten Apps nach Verwaltungsart (MAM mit MDM, MAM ohne MDM-Registrierung usw.).

* **Registrierungsaufruf**: Übermittelt die Erfolgsquote und andere Leistungsindikatoren von Registrierungsaufrufen, die von der Clientseite initiiert wurden,an Microsoft Intune.

> [!NOTE]
> Wenn von Ihrer mobilen Anwendung keine Intune App SDK-Telemetriedaten an Microsoft Intune gesendet werden sollen, müssen Sie die Intune App SDK-Telemetrieerfassung deaktivieren. Legen Sie die Eigenschaft `MAMTelemetryDisabled` im IntuneMAMSettings-Wörterbuch auf „YES“ fest.

## <a name="enable-multi-identity-optional"></a>Aktivierung mehrerer Identitäten (optional)

Standardmäßig wird eine Richtlinie vom SDK auf die gesamte App angewendet. Die Unterstützung für mehrere Identitäten ist ein MAM-Feature, das Sie aktivieren können, um eine Richtlinie auf der Ebene einzelner Identitäten anzuwenden. Dies erfordert eine stärkere Beteiligung der App als andere MAM-Features.

Die App muss das App-SDK informieren, wenn sie die Änderung der aktiven Identität beabsichtigt. Das SDK benachrichtigt seinerseits die App, wenn eine Änderung der Identität erforderlich ist. Aktuell wird nur eine verwaltete Identität unterstützt. Nachdem der Benutzer das Gerät oder die App registriert hat, verwendet das SDK die dabei verwendete Identität und betrachtet sie als die primäre verwaltete Identität. Andere Benutzer der App werden als nicht verwaltet mit uneingeschränkten Richtlinieneinstellungen behandelt.

Beachten Sie, dass eine Identität einfach in Form einer Zeichenfolge definiert wird. Bei Identitäten werden Groß- und Kleinschreibung nicht unterschieden. Anforderungen einer Identität beim SDK werden möglicherweise nicht mit der gleichen Groß-/Kleinschreibung zurückgegeben, die ursprünglich beim Festlegen der Identität verwendet wurde.

### <a name="identity-overview"></a>Identität (Übersicht)

Eine Identität ist einfach der Benutzername eines Kontos (z.B. user@contoso.com). Entwickler können die Identität der App auf den folgenden Ebenen festlegen:

* **Prozessidentität**: Legt die prozessweite Identität fest und wird in der Hauptsache für Anwendungen mit nur einer Identität verwendet. Diese Identität betrifft alle Aufgaben, Dateien und die Benutzeroberfläche.

* **UI-Identität**: Legt fest, welche Richtlinien auf Benutzeroberflächenaufgaben im Hauptthread angewendet werden, z. B. Ausschneiden/Kopieren/Einfügen, PIN, Authentifizierung und Datenfreigabe. Die UI-Identität wirkt sich nicht auf Dateiaufgaben wie Verschlüsselung und Sicherung aus.

* **Threadidentität**: Wirkt sich darauf aus, welche Richtlinien auf den aktuellen Thread angewendet werden. Diese Identität betrifft alle Aufgaben, Dateien und die Benutzeroberfläche.

Es ist Aufgabe der App, die Identitäten passend für verwaltete und nicht verwaltete Benutzer festzulegen.

Jeder Thread weist jederzeit eine effektive Identität für Benutzeroberflächen- und Dateiaufgaben auf. Dies ist die Identität, mit der überprüft wird, welche Richtlinien, sofern zutreffend, angewendet werden sollen. Wenn die Identität „no identity“ ist oder der Benutzer nicht verwaltet ist, werden keine Richtlinien angewendet. Die unten stehenden Diagramme zeigen, wie effektive Identitäten bestimmt werden.

  ![Intune App SDK iOS – verknüpfte Frameworks und Bibliotheken](./media/ios-thread-identities.png)

### <a name="thread-queues"></a>Thread-Warteschlangen

Apps versenden häufig asynchrone und synchrone Aufgaben an Threadwarteschlangen. Das SDK fängt GCD-Aufrufe (Grand Central Dispatch) ab und ordnet den versendeten Aufgaben die aktuelle Threadidentität zu. Wenn die Aufgaben abgeschlossen sind, ändert das SDK die Threadidentität vorübergehend in die den Aufgaben zugeordnete Identität, schließt die Aufgaben ab und stellt die ursprüngliche Threadidentität wieder her.


Da `NSOperationQueue` auf GCD basiert, wird `NSOperations` mit der Identität des Threads zu dem Zeitpunkt ausgeführt, als die Aufgaben zur `NSOperationQueue` hinzugefügt wurden. `NSOperations` oder direkt über GCD versendete Funktionen können die aktuelle Threadidentität ebenfalls bei ihrer Ausführung ändern. Diese Identität setzt die vom versendenden Thread geerbte Identität außer Kraft.

### <a name="file-owner"></a>Dateibesitzer

Das SDK verfolgt die Identitäten der lokalen Dateibesitzer und wendet Richtlinien entsprechend an. Ein Dateibesitzer wird beim Erstellen einer Datei oder beim Öffnen einer Datei im Kürzungsmodus (truncate mode) eingerichtet. Der Besitzer wird auf die effektive Identität für Dateiaufgaben des Threads festgelegt, der die Aufgabe ausführt.

Alternativ können Apps die Identität des Dateibesitzers mithilfe von `IntuneMAMFilePolicyManager` explizit festlegen. Apps können `IntuneMAMFilePolicyManager` verwenden, um den Dateibesitzer abzurufen und die Benutzeroberflächenidentität festzulegen, bevor der Dateiinhalt angezeigt wird.

### <a name="shared-data"></a>Geteilte Daten

Wenn die App Dateien erstellt, die Daten von verwalteten und nicht verwalteten Benutzern enthalten, ist es ihre Aufgabe, die Daten der verwalteten Benutzer zu verschlüsseln. Sie können Daten mithilfe der `protect`- und `unprotect`-APIs in `IntuneMAMDataProtectionManager` verschlüsseln.

Die `protect`-Methode akzeptiert eine Identität, bei der es sich um einen verwalteten oder nicht verwalteten Benutzer handeln kann. Wenn der Benutzer verwaltet ist, werden die Daten verschlüsselt. Wenn es sich um einen nicht verwalteten Benutzer handelt, wird den Daten ein Header hinzugefügt, der die Identität verschlüsselt, die Daten selbst werden jedoch nicht verschlüsselt. Sie können die `protectionInfo`-Methode verwenden, um den Besitzer der Daten abzurufen.

### <a name="share-extensions"></a>Freigabeerweiterungen

Wenn die App eine Freigabeerweiterungen enthält, kann der Besitzer des freigegebenen Elements mithilfe der `protectionInfoForItemProvider`-Methode in `IntuneMAMDataProtectionManager` abgerufen werden. Wenn es sich bei dem freigegebenen Element um eine Datei handelt, übernimmt das SDK das Festlegen des Dateibesitzers. Wenn es sich bei dem freigegebenen Element um Daten handelt, muss die App den Besitzer der Datei festlegen, wenn diese Daten in einer Datei gespeichert werden, und die `setUIPolicyIdentity`-API aufrufen, bevor die Daten in der Benutzeroberfläche angezeigt werden.

### <a name="turning-on-multi-identity"></a>Aktivieren der Unterstützung für mehrere Identitäten

Standardmäßig werden Apps als Einzelidentitäts-Apps betrachtet. Das SDK legt die Prozessidentität auf den registrierten Benutzer fest. Um die Unterstützung für mehrere Identitäten zu aktivieren, fügen Sie dem Wörterbuch „IntuneMAMSettings“ in der Datei „Info.plist“ der App eine boolesche Einstellung mit dem Namen `MultiIdentity` und dem Wert „YES“ hinzu.

> [!NOTE]
> Wenn die Unterstützung für mehrere Identitäten aktiviert ist, werden die Prozessidentität, die Benutzeroberflächenidentität und die Threadidentitäten auf „nil“ festgelegt. Es ist Aufgabe der App, die entsprechenden Einstellungen vorzunehmen.

### <a name="switching-identities"></a>Wechseln von Identitäten

* **Von der App eingeleiteter Identitätswechsel**:

    Beim Starten werden mehrere Identitäten als unter einem unbekannten, nicht verwalteten Konto angesehen. Die Benutzeroberfläche für bedingten Start wird nicht ausgeführt, und für die App werden keine Richtlinien durchgesetzt. Die App muss das SDK bei jedem beabsichtigten Wechsel der Identität benachrichtigen. Normalerweise geschieht das, wenn die App im Begriff ist, Daten für ein bestimmtes Benutzerkonto anzuzeigen.

    Ein Beispiel dafür ist, wenn der Benutzer versucht, ein Dokument, ein Postfach oder eine Registerkarte in einem Notizbuch zu öffnen. Die App muss das SDK benachrichtigen, bevor die Datei, das Postfach oder die Registerkarte tatsächlich geöffnet wird. Dies erfolgt mithilfe der `setUIPolicyIdentity`-API in `IntuneMAMPolicyManager`. Diese API sollte unabhängig davon aufgerufen werden, ob der Benutzer verwaltet ist oder nicht. Wenn der Benutzer verwaltet ist, führt das SDK die Prüfungen für den bedingten Start aus (z. B. Jailbreakerkennung, PIN und Authentifizierung).

    Das Ergebnis des Identitätswechsels wird asynchron mithilfe eines Abschlusshandlers an die App zurückgegeben. Die App sollte mit dem Öffnen von Dokument, Postfach oder Registerkarte solange warten, bis ein Ergebniscode für den Erfolg zurückgegeben wird. Bei einem Fehler beim Identitätswechsel sollte die App die Aufgabe abbrechen.

* **Vom SDK eingeleiteter Identitätswechsel**:

    Manchmal muss das SDK die App bitten, zu einer bestimmten Identität zu wechseln. Apps, die mehrere Identitäten unterstützen, müssen die `identitySwitchRequired`-Methode in `IntuneMAMPolicyDelegate` implementieren, um diese Anforderung zu verarbeiten.

    Wenn die App beim Aufruf der Methode imstande ist, die Anforderung des Wechselns zu einer angegebenen Identität auszuführen, sollte sie `IntuneMAMAddIdentityResultSuccess` im Abschlusshandler übergeben. Wenn sie den Identitätswechsel nicht vornehmen kann, sollte die App `IntuneMAMAddIdentityResultFailed` im Abschlusshandler übergeben.

    Die App muss als Reaktion auf diesen Aufruf nicht `setUIPolicyIdentity` aufrufen. Wenn das SDK bei der App den Wechsel zu einem nicht verwalteten Benutzerkonto anfordern muss, wird im Aufruf `identitySwitchRequired` eine leere Zeichenfolge übergeben.

* **Selektives Zurücksetzen**:

    Wenn die App selektiv zurückgesetzt wird, ruft das SDK die `wipeDataForAccount`-Methode in `IntuneMAMPolicyDelegate` auf. Es ist Aufgabe der App, das Konto des angegebenen Benutzers und alle ihm zugeordneten Daten zu entfernen. Das SDK ist imstande, alle Dateien im Besitz des Benutzer zu entfernen, und führt dies durch, wenn von der App auf den `wipeDataForAccount`-Aufruf „FALSE“ zurückgegeben wird.

    Beachten Sie, dass diese Methode aus einem Hintergrundthread aufgerufen wird. Die App sollte keinen Wert zurückgeben, bevor alle Daten für den Benutzer entfernt wurden (mit Ausnahme der Dateien, wenn die App „FALSE“ zurückgibt).

## <a name="test-app-protection-policy-settings-in-xcode"></a>Testen der Einstellungen für die App-Schutzrichtlinie in Xcode

Bevor Sie Ihre Intune-fähige App in der Produktion testen, können Sie in Xcode eine Settings.bundle-Datei verwenden. Dies ermöglicht Ihnen die Festlegung von App-Schutzrichtlinien zum Testen, ohne dass eine Verbindung mit Intune erforderlich wird.

### <a name="enable-policy-testing"></a>Aktivieren des Testens von Richtlinien

Gehen Sie folgendermaßen vor, um das Testen von Richtlinien in Xcode zu aktivieren:

1. Vergewissern Sie sich, dass Sie mit einem Debugbuild arbeiten. Fügen Sie eine Settings.bundle-Datei hinzu, indem Sie mit der rechten Maustaste auf den Ordner der obersten Ebene im Projekt klicken. Wählen Sie **Add** > **New File** im Menü aus. Wählen Sie unter **Resources** die Vorlage **Settings Bundle** aus.

2.  Kopieren Sie den folgenden Block für den Debugbuild in die Settings.bundle/**Root.plist**-Datei:
    ```xml
    <key>PreferenceSpecifiers</key>
    <array>
        <dict>
            <key>Type</key>
            <string>PSChildPaneSpecifier</string>
            <key>Title</key>
            <string>MDM Debug Settings</string>
            <key>Key</key>
            <string>MAMDebugSettings</string>
            <key>File</key>
            <string>MAMDebugSettings</string>
        </dict>
    </array>
    ```

3. Fügen Sie im **IntuneMAMSettings**-Wörterbuch in der „Info.plist“ der App einen booleschen Wert namens DebugSettingsEnabled hinzu. Legen Sie für DebugSettingsEnabled den Wert „YES“ fest.



### <a name="app-protection-policy-settings"></a>Einstellungen für die App-Schutzrichtlinie

In der folgenden Tabelle werden die Einstellungen der App-Schutzrichtlinie beschrieben, die Sie mit MAMDebugSettings.plist testen können. Um eine Einstellung zu aktivieren, fügen Sie sie MAMDebugSettings.plist hinzu.

| Name der Richtlinieneinstellung | Beschreibung | Mögliche Werte |
| -- | -- | -- |
| AccessRecheckOfflineTimeout | Der Zeitraum in Minuten, für den die App offline sein kann, bevor Intune das Starten der App oder ihre Fortsetzung blockiert, wenn die Authentifizierung aktiviert ist. | Beliebige ganze Zahl größer als 0 |
|   AccessRecheckOnlineTimeout | Der Zeitraum in Minuten, für den die App ausgeführt werden kann, bevor der Benutzer beim Starten oder Fortsetzen zur Eingabe der PIN oder zur Authentifizierung aufgefordert wird (wenn Authentifizierung oder PIN für den Zugriff aktiviert ist). | Beliebige ganze Zahl größer als 0 |
| AppSharingFromLevel | Gibt an, von welchen Apps diese App Daten akzeptieren kann. | 0 = |
## <a name="ios-best-practices"></a>Empfohlene Methoden für iOS

Hier finden Sie empfohlene und bewährte Methoden für die Entwicklung für iOS:

* Beim iOS-Dateisystem werden Groß-/Kleinschreibung berücksichtigt. Vergewissern Sie sich, dass Dateinamen wie `libIntuneMAM.a` und `IntuneMAMResources.bundle` die richtige Groß-/Kleinschreibung aufweisen.

* Wenn Xcode Probleme beim Suchen nach `libIntuneMAM.a` hat, können Sie das Problem beheben, indem Sie den Pfad zu dieser Bibliothek den Linkersuchpfaden hinzufügen.

## <a name="faqs"></a>Häufig gestellte Fragen


**Sind alle APIs durch die native Swift- oder die Objective-C- und Swift-Interoperabilität erreichbar?**

Die Intune App SDK-APIs arbeiten ausschließlich in der Objective-C-Programmiersprache und unterstützen nicht die **native** Sprache Swift. Swift-Interoperabilität mit Objective-C ist erforderlich.


**Müssen alle Benutzer meiner Anwendung beim APP-WE-Dienst registriert werden?**

Nein. Nur Arbeits-, Schul- oder Unikonten sollten beim Intune App SDK registriert werden. Die Apps sind dafür zuständig, zu bestimmen, ob ein Konto in einem Arbeits-, Schul- oder Unikontext verwendet wird.   

**Was ist mit Benutzern, die bereits bei der Anwendung angemeldet sind? Müssen sie registriert sein?**

Es ist Aufgabe der Anwendung, Benutzer zu registrieren, nachdem sie erfolgreich authentifiziert wurden. Die Anwendung muss außerdem alle vorhandenen Konten registrieren, die bereits vorhanden waren, bevor die Anwendung über MAM-Funktionalität ohne MDM-Registrierung verfügte.   

Zu diesem Zweck sollte die Anwendung die `registeredAccounts:`-Methode verwenden. Diese Methode gibt ein NSDictionary zurück, das sämtliche beim Intune MAM-Dienst registrierten Konten enthält. Wenn in der Anwendung bestehende Konten in der Liste nicht vorhanden sind, sollte die Anwendung diese Konten mithilfe von `registerAndEnrollAccount:` registrieren.

**Wie oft wiederholt das SDK Registrierungsversuche?**

Das SDK wiederholt alle zuvor mit einem Fehler abgebrochenen Registrierungsversuche in einem 24-Stunden-Intervall. Das SDK geht so vor, um sicherzustellen, dass ein Benutzer erfolgreich registriert wird und Richtlinien auf sein Konto angewendet werden, wenn die Organisation MAM erst nach der Anmeldung des Benutzers bei der Anwendung aktiviert hat.

Das SDK stellt die Wiederholungsversuche ein, wenn es feststellt, dass ein Benutzer die Anwendung erfolgreich registriert hat. Dies hat den Grund, dass immer nur ein Benutzer eine Anwendung registrieren kann. Wenn die Registrierung des Benutzers aufgehoben wird, beginnen die Registrierungsversuche wieder mit dem gleichen 24-Stunden-Intervall.

**Warum muss die Registrierung des Benutzers aufgehoben werden?**

Das SDK führt im Hintergrund in regelmäßigen Abständen die folgenden Aktionen aus:

 - Wenn die Anwendung noch nicht registriert ist, versucht es, alle registrierten Konten alle 24 Stunden zu registrieren.
 - Wenn die Anwendung registriert ist, prüft das SDK alle 8 Stunden auf App-Schutzrichtlinienaktualisierungen.

Durch Aufheben der Registrierung eines Benutzers teilt die Anwendung dem SDK mit, dass der Benutzer die Anwendung nicht mehr verwendet und alle regelmäßigen Aktionen für dieses Benutzerkonto vom SDK eingestellt werden können. Dadurch werden außerdem das Aufheben der Registrierung und ggf. das selektive Zurücksetzen ausgelöst.

**Soll das doWipe-Flag in der Methode zum Aufheben der Registrierung auf wahr festgelegt werden?**

Diese Methode sollte aufgerufen werden, bevor der Benutzer bei der Anwendung abgemeldet wird.  Wenn die Daten des Benutzers im Rahmen der Abmeldung aus der Anwendung gelöscht werden, kann `doWipe` auf „false“ festgelegt werden. Wenn die Anwendung die Daten des Benutzers jedoch nicht entfernt, sollte `doWipe` auf „true“ festgelegt werden, damit das SDK die Daten löschen kann.

**Gibt es andere Möglichkeiten zum Aufheben der Registrierung einer Anwendung?**

Ja, der IT-Administrator kann einen Befehl zum selektiven Zurücksetzen an die Anwendung senden. Dadurch wird die Registrierung aufgehoben und der Benutzer abgemeldet, und die Daten des Benutzers werden zurückgesetzt. Das SDK wickelt dieses Szenario automatisch ab und sendet mithilfe der Stellvertretermethode zum Aufheben der Registrierung eine Benachrichtigung.



## <a name="submit-your-app-to-the-app-store"></a>Übermitteln Ihrer App an den App Store

Sowohl die statische Bibliothek als auf Frameworkbuilds des Intune App SDK sind universelle Binärdateien. Das bedeutet, dass sie Code für alle Geräte- und Simulatorarchitekturen enthalten. Apple lehnt für den App Store eingereichte Apps ab, wenn sie Simulatorcode enthalten. Beim Kompilieren mit der statischen Bibliothek für nur für Geräte bestimmte Builds entfernt der Linker den Simulatorcode automatisch. Gehen Sie folgendermaßen vor, um sicherzustellen, dass der gesamte Simulatorcode entfernt wird, bevor Sie Ihre App in den App Store hochladen.

1. Stellen Sie sicher, dass sich `IntuneMAM.framework` auf dem Desktop befindet.

2. Führen Sie diese Befehle aus:

    ```bash
    lipo ~/Desktop/IntuneMAM.framework/IntuneMAM -remove i386 -remove x86_64 -output ~/Desktop/IntuneMAM.device_only
    ```

    ```bash
    cp ~/Desktop/IntuneMAM.device_only ~/Desktop/IntuneMAM.framework/IntuneMAM
    ```
    Der erste Befehl entfernt die Simulatorarchitekturen aus der DYLIB-Datei des Frameworks. Der zweite Befehl kopiert die nur für Geräte zuständige DYLIB-Datei wieder in das Frameworkverzeichnis.
