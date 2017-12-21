---
title: Neuerungen in Microsoft Intune
titlesuffix: Azure portal
description: Erfahren Sie, welche Neuerungen es im Intune-Azure-Portal gibt
keywords: 
author: ErikjeMS
ms.author: erikje
manager: angrobe
ms.date: 12/15/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 791ed23f-bd13-4ef0-a3dd-cd2d7332c5cc
ms.reviewer: angrobe
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 24ec619a2e11a81c5988f6c95a268222a454360e
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2017
---
# <a name="whats-new-in-microsoft-intune"></a>Neuerungen in Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Erfahren Sie jede Woche, welche Neuerungen Microsoft Intune zu bieten hat. Sie erhalten auch Informationen zu [bevorstehenden Änderungen](#whats-coming), [wichtige Hinweise](#notices) zum Dienst und Informationen zu [vorherigen Versionen](whats-new-archive.md).

> [!Note]
> Informationen zu neuen Funktionen der hybriden Verwaltung mobiler Geräte (MDM) finden Sie auf der Seite [Neuheiten bei der hybriden Verwaltung mobiler Geräte ](/sccm/mdm/understand/whats-new-in-hybrid-mobile-device-management).


<!-- Common categories:  
  ### Device enrollment
  ### Device management
  ### App management
  ### Device configuration
  ### Role-based access control
  ### Intune apps
  ### Monitor and troubleshoot
 
-->   

## <a name="week-of-december-11-2017"></a>Woche des 11 Dezember 2017

### <a name="device-configuration"></a>Gerätekonfiguration

#### <a name="new-windows-defender-security-center-wdsc-device-configuration-profile-settings----1335507---"></a>Neue Einstellungen des WDSC-Gerätekonfigurationsprofils (Windows Defender Security Center) <!-- 1335507 -->

Unter dem Endpunktschutz namens **Windows Defender Security Center** fügt Intune einen neuen Abschnitt mit Einstellungen des Gerätekonfigurationsprofils hinzu. IT-Administratoren können konfigurieren, welche ///Komponenten der Windows Defender Security Center-App für Endbenutzer zugänglich sind. Wenn ein IT-Administrator eine Komponente in der Windows Defender Security Center-App ausblendet, werden Benachrichtigungen in Zusammenhang mit der ausgeblendeten Komponente nicht auf dem Gerät des Benutzers angezeigt.

Folgende Komponenten können von Administratoren aus den Einstellungen des Gerätekonfigurationsprofils von Windows Defender Security Center ausgeblendet werden:
- Viren- und Bedrohungsschutz
- Geräteleistung und -integrität
- Firewall- und Netzwerkschutz
- App- und Browsersteuerung
- Familienoptionen

IT-Administratoren können auch anpassen, welche Benutzer Benachrichtigungen empfangen können. Beispielsweise können Sie konfigurieren, ob Benutzer alle von sichtbaren Komponenten in WDSC generierten Benachrichtigungen oder nur kritische Benachrichtigungen erhalten. Zu nicht kritischen Benachrichtigungen gehören regelmäßige Zusammenfassungen von Windows Defender Antivirus-Aktivitäten und Benachrichtigungen bei Abschluss von Überprüfungen. Alle übrigen Benachrichtigungen gelten als kritisch. Darüber hinaus können Sie auch den Inhalt der Benachrichtigung anpassen. Beispielsweise können Sie die IT-Kontaktinformationen angeben, um sie in die Benachrichtigungen einzubetten, die auf den Geräten der Benutzer angezeigt werden.

#### <a name="multiple-connector-support-for-scep-and-pfx-certificate-handling----1361755---"></a>Unterstützung für mehrere Connectors für die Behandlung von SCEP- und PFX-Zertifikaten <!-- 1361755 -->

Kunden, die den lokalen NDES-Connector verwenden, um Zertifikate auf Geräten zu übermitteln, können jetzt mehrere Connectors in einem einzigen Mandanten konfigurieren.

Diese neue Funktion unterstützt das folgende Szenario:

- **Hochverfügbarkeit**

Jeder NDES-Connector bezieht Zertifikatanforderungen mithilfe von Pull von Intune.  Wenn ein NDES-Connector offline geschaltet wird, kann der andere Connector weiterhin Anforderungen verarbeiten.

#### <a name="customer-subject-name-can-use-aaddeviceid-variable-----1468599---"></a>Antragstellername Kunden kann AAD_DEVICE_ID Variable verwenden.<!-- 1468599 -->

Beim Erstellen eines SCEP-Zertifikatprofils in Intune können Sie jetzt die AAD_DEVICE_ID Variable verwenden, bei der Erstellung der benutzerdefinierten Antragstellername.   Wenn das Zertifikat mit diesem SCEP-Profil angefordert wird, wird die Variable durch die AAD-Geräte-ID des Geräts anfordernde Zertifikat ersetzt.


### <a name="device-management"></a>Geräteverwaltung

#### <a name="manage-jamf-enrolled-macos-devices-with-intunes-device-compliance-engine----1592747---"></a>Verwalten von über Jamf registrierten macOS-Geräten mit dem Gerätekonformitätsmodul von Intune <!-- 1592747 -->
Sie können jetzt Jamf verwenden, MacOS Zustandsinformationen Gerät in Intune, senden, der dann es für die Einhaltung von Richtlinien, die in der Intune-Verwaltungskonsole definiert ausgewertet wird. Basierend auf dem Konformitätszustand des Geräts und anderen Bedingungen (z.B. Standort, Benutzerrisiko usw.) wird die Konformität für macOS-Geräte, die auf mit Azure AD verbundene Cloud- und lokale Anwendungen zugreifen (einschließlich Office 365) mithilfe des bedingten Zugriffs erzwungen. Erfahren Sie mehr über [Jamf-Integration einrichten](conditional-access-integrate-jamf.md) und [Erzwingen der Kompatibilität für Geräte verwaltet werden Jamf](conditional-access-assign-jamf.md).

#### <a name="new-ios-device-action------1424701---"></a>Neue iOS-Geräteaktion <!-- 1424701 -->

Sie können jetzt iOS 10.3 überwachte Geräten Herunterfahren. Diese Aktion fährt das Gerät sofort und ohne Warnung für den Endbenutzer herunter. Die Aktion **Herunterfahren (nur überwacht)** finden Sie in den Geräteeigenschaften bei der Auswahl eines Geräts in der Workload **Gerät**.

#### <a name="disallow-datetime-changes-to-samsung-knox-devices----1468103---"></a>Zu unterbinden, Datum/Uhrzeit-Änderungen für Samsung KNOX-Geräte<!-- 1468103 -->

Wir haben ein neues Feature hinzugefügt, das Blockieren von Datum und Uhrzeit der Änderungen für Samsung KNOX-Geräte ermöglicht. Sie finden diese in **Konfiguration Geräteprofile** > **geräteeinschränkungen (Android)** > **allgemeine**.

#### <a name="surface-hub-resource-account-supported----1566442----"></a>Unterstützung für Surface Hub-Ressourcenkonto <!-- 1566442  -->

Eine neue Gerät-Aktion wurde hinzugefügt, damit Administratoren definieren und der Ressource, das ein Surface Hub zugeordnet aktualisieren werden können.

Das Ressourcenkonto wird von einem Surface Hub für die Authentifizierung bei Skype/Exchange verwendet, um seine Teilnahme an einer Besprechung zu ermöglichen. Sie können ein eindeutiges Ressourcenkonto erstellen, damit der Surface Hub in der Besprechung als Konferenzraum angezeigt wird. Beispielsweise kann das Ressourcenkonto als *Konferenzraum B41/6233* angezeigt werden. Das Ressourcenkonto (auch als Gerätekonto bezeichnet) für den Surface Hub muss in der Regel für den Standort des Konferenzraums konfiguriert werden, wenn andere Parameter des Ressourcenkontos geändert werden müssen.

Wenn Administratoren das Ressourcenkonto auf einem Gerät aktualisieren möchten, müssen sie die aktuellen Active Directory-/Azure Active Directory-Anmeldeinformationen angeben, die dem Gerät zugeordnet sind. Wenn die Kennwortrotation für das Gerät aktiviert ist, müssen Administratoren zu Azure Active Directory wechseln, um das Kennwort zu finden.

> [!NOTE]
> Alle Felder werden im Paket nach unten gesendet und überschreiben alle Felder, die zuvor konfiguriert wurden. Leere Felder überschreiben auch vorhandene Felder.

Administratoren können folgende Einstellungen konfigurieren:

- **Ressourcenkonto**
   - **Active Directory-Benutzer**

      Domänenname\Benutzername oder Benutzerprinzipalname (UPN): user@domainname.com

   - **Passwort**

- **Optionaler Ressourcenkontoparameter** (muss über das angegebene Ressourcenkonto festgelegt werden)

   - **Kennwort Drehung Zeitraum**

     Stellt sicher, dass das Kontokennwort aus Sicherheitsgründen jede Woche automatisch durch den Surface Hub aktualisiert wird. Um nach dem Aktivieren dieser Option Parameter zu konfigurieren, muss das Kennwort für das Konto in Azure Active Directory zuerst zurückgesetzt werden.

   - **SIP (Session Initiation Protocol)-Adresse**

     Wird nur verwendet, wenn die AutoErmittlung nicht möglich ist.

   - **E-Mail**

     E-Mail-Adresse des Geräte-/Ressourcenkontos.

   - **Exchange-server**

     Nur erforderlich, wenn die AutoErmittlung nicht möglich ist.

   - **Calendar-Synchronisierung**

     Gibt an, ob die Kalendersynchronisierung und andere Exchange-Serverdienste aktiviert sind. Beispiel: die Besprechungssynchronisierung.

#### <a name="install-office-apps-on-macos-devices----1494311---"></a>Installieren von Office-Apps auf macOS-Geräten <!-- 1494311 -->
Sie werden können Office-apps auf Geräten MacOS installieren. Dieser neue App-Typ ermöglicht Ihnen die Installation von Word, Excel, PowerPoint, Outlook und OneNote. Diese apps werden auch mit dem Microsoft AutoUpdate (MAU), um Ihre apps sicher und auf dem neuesten Stand zu halten.

### <a name="app-management"></a>App-Verwaltung

#### <a name="delete-an-ios--volume-purchasing-program-token----820879---"></a>Löschen eines iOS Volume Purchase Program-Tokens <!-- 820879 -->
Sie können das iOS Volume Erwerb Program (VPP) an, die mithilfe der Konsole löschen. Dies kann erforderlich sein, wenn doppelte Instanzen eines VPP-Tokens vorliegen.

### <a name="intune-apps"></a>Intune-Apps

#### <a name="end-user-messaging-for-accounts---1573558-for-1712--"></a>Endbenutzer-messaging für Konten<!--1573558 for 1712-->

Benutzer von der Unternehmensportal-Website blockiert Maßnahmen, die Schreibzugriff auf Ihren Mandanten zu erfordern. Sie sehen die entsprechenden Fehler messaging erläutert, die ihrem Konto gewartet wird. Ähnliche Änderungen an den Unternehmensportal-apps für Android, iOS, Mac OS und Windows in Kürze verfügbar. Sie können daher die Fehlermeldung in der [Neuheiten bei app-Benutzeroberfläche](whats-new-app-ui.md). 



### <a name="role-based-access-control"></a>Rollenbasierte Zugriffssteuerung

#### <a name="a-new-entity-collection-named-current-user-is-limited-to-currently-active-user-data----1667026---"></a>Eine neue Entitätssammlung namens „Aktueller Benutzer“ ist auf die Daten der momentan aktiven Benutzer beschränkt.<!-- 1667026 -->

Die **Benutzer** entitätsauflistung enthält alle Azure Active Directory (Azure AD)-Benutzer mit zugewiesenen Lizenzen in Ihrem Unternehmen. Beispielsweise kann ein Benutzer in Intune hinzugefügt und dann im Verlauf des letzten Monats entfernt worden sein. Auch wenn dieser Benutzer zum Zeitpunkt der Berichterstellung nicht vorhanden ist, liegen Angaben zu Benutzer und Zustand in den Daten vor. Sie können einen Bericht erstellen, der die Dauer der Präsenz des Benutzers in Ihren Daten zeigt.

Im Gegensatz dazu enthält die neue Entitätssammlung **Aktueller Benutzer** nur Benutzer, die nicht entfernt wurden. Die Entitätssammlung **Aktueller Benutzer** enthält nur die derzeit aktiven Benutzer. Informationen zur Entitätssammlung **Aktueller Benutzer** finden Sie unter [Referenz für die Entität „Aktueller Benutzer“](reports-ref-current-user.md).


### <a name="updated-graph-apis----1736360---"></a>Aktualisierte Graph-APIs<!-- 1736360 -->

In dieser Version haben wir ein Paar von der Graph-API für Intune, mit denen in der Betaversion werden aktualisiert. Überprüfen Sie die monatlichen [Graph-API Änderungsprotokoll](https://developer.microsoft.com/graph/docs/concepts/changelog) für Weitere Informationen.


## <a name="week-of-december-4-2017"></a>Woche des 4. Dezember 2017

### <a name="monitor-and-troubleshoot"></a>Überwachung und Problembehandlung

#### <a name="intune-supports-windows-information-protection-wip-denied-apps----1479103---"></a>Intune unterstützt WIP-abgelehnte Apps (Windows Information Protection) <!-- 1479103 -->
Sie können abgelehnte Apps in Intune festlegen. Wenn eine App abgelehnt wird, wird ihr der Zugriff auf Unternehmensinformationen verweigert. Sie ist also genau das Gegenteil einer zugelassenen App. Weitere Informationen finden Sie unter [AppLocker-CSP](https://docs.microsoft.com/windows/client-management/mdm/applocker-csp?f=255&MSPPError=-2147217396#recommended-deny-list-for-windows-information-protection).


## <a name="week-of-november-27-2017"></a>Woche vom 27. November 2017

### <a name="device-enrollment"></a>Geräteregistrierung

#### <a name="troubleshoot-enrollment-issues-----746324---"></a>Behandlung von Problemen bei der Registrierung <!-- 746324 -->

Im Arbeitsbereich **Problembehandlung** werden nun Probleme der Benutzer bei der Registrierung angezeigt. Die Details zum Problem und die vorgeschlagenen Abhilfemaßnahmen können Administratoren und Helpdeskmitarbeiter bei der Behandlung von Problemen unterstützen. Bestimmte Probleme bei der Registrierung werden nicht erfasst, und für einige Fehler liegen möglicherweise keine Wiederherstellungsvorschläge vor.

#### <a name="group-assigned-enrollment-restrictions----747598---"></a>Gruppen zugeordnete Registrierungseinschränkungen <!-- 747598 -->

Als Intune-Administrator können Sie nun [benutzerdefinierte Registrierungsbeschränkungen für Gerätetypen und -limits für Benutzergruppen erstellen](enrollment-restrictions-set.md).

Im Intune Azure-Portal können Sie bis zu 25 Instanzen für jeden Beschränkungstypen erstellen, die Sie Benutzergruppen zuordnen können. Gruppen zugeordnete Beschränkungen setzen die Standardbeschränkungen außer Kraft.

Sämtliche Instanzen eines Beschränkungstypen werden in einer Liste mit einer strengen Reihenfolge verwaltet. Diese Reihenfolge definiert einen Prioritätswert für die Lösung von Konflikten. Ein Benutzer, der von mehr als einer Beschränkungsinstanz betroffen ist, wird nur von der Instanz mit dem höchsten Prioritätswert eingeschränkt. Sie können die Priorität einer vorhandenen Instanz ändern, indem Sie sie an eine andere Stelle in der Liste ziehen.

Diese Funktion wird mit der Migration von Android for Work-Einstellungen aus dem Android for Work-Registrierungsmenü in das Registrierungsmenü freigegeben. Da diese Migration einige Tage in Anspruch nehmen kann, wird Ihr Konto möglicherweise auf andere Teile des Releases im November aktualisiert, bevor die Gruppenzuweisung für Registrierungsbeschränkungen aktiviert ist.

#### <a name="support-for-multiple-network-device-enrollment-service-ndes-connectors----1528104---"></a>Unterstützung von mehreren Konnektoren für den Registrierungsdienst für Netzwerkgeräte <!-- 1528104 -->

Über den Registrierungsdienst für Netzwerkgeräte (Network Device Enrollment Service NDES) können Mobilgeräte, die ohne Domänen-Anmeldeinformationen ausgeführt werden, Zertifikate auf Basis des Simple Certificate Enrollment-Protokolls (SCEP) abrufen.
Mit diesem Update werden mehrere NDES-Connectors unterstützt.

#### <a name="manage-android-for-work-devices-independently-from-android-devices----1490731-eeready--"></a>Verwalten von Android for Work-Geräten unabhängig von Android-Geräten <!-- 1490731 EEready-->

**Hinweis**: Die folgenden Änderungen werden mit dem Update vom November eingeführt. Allerdings kann es einige Zeit dauern, bis sie auch für Ihr Konto erfolgen. Sie erhalten im Office 365-Portal eine Bestätigungsnachricht, wenn diese Änderungen auf Ihrem Konto vorgenommen worden sind. Nach dem Rollout werden Ihnen zusätzliche Verwaltungsfunktionen geboten. Während des Rollouts kommt es zu keinen Änderungen an der Benutzeroberfläche.

Intune unterstützt das Verwalten von Registrierungen von Android for Work-Geräten unabhängig von der Android-Plattform. Diese Einstellungen werden unter **Geräteregistrierung** > **Registrierungsbeschränkungen** > **Gerätetypbeschränkungen** verwaltet. (Zuvor waren sie unter **Geräteregistrierung** > **Android for Work-Registrierung** > **Android for Work-Registrierungseinstellungen** zu finden.)

Standardmäßig ändern sich die Android for Work-Geräteeinstellungen gegenüber Ihren Android-Geräteeinstellungen nicht. Dies ändert sich allerdings, nachdem Sie ihre Android for Work-Einstellungen geändert haben.

Wenn Sie die private Android for Work-Registrierung blockieren, können sich nur unternehmenseigene Android-Geräte als Android for Work-Geräte registrieren.

Ziehen Sie folgendes in Betracht, wenn Sie mit den neuen Einstellungen arbeiten:

##### <a name="if-you-have-never-previously-onboarded-android-for-work-enrollment"></a>Wenn Sie die Android for Work-Registrierung zuvor noch nie integriert haben

Die neue Android for Work Plattform wird in den Standardgerätetypbeschränkungen blockiert. Nachdem Sie die Funktion integriert haben, können Sie zulassen, dass sich Geräte mit Android for Work registrieren. Ändern Sie dafür die Standardeinstellungen, oder erstellen Sie eine neue Gerätetypbeschränkung, um die Standardgerätetypbeschränkungen zu ersetzen.

##### <a name="if-you-have-onboarded-android-for-work-enrollment"></a>Wenn Sie die Android for Work-Registrierung bereits integriert haben

Wenn Sie zuvor bereits eine Integration vorgenommen haben, hängt Ihre Situation von den von Ihnen ausgewählten Einstellungen ab:

| Einstellung | Android for Work-Status in den Standardgerätetypbeschränkungen | Hinweise |
| --- | --- | --- |
| **Alle Geräte als Android-Geräte verwalten** | Gesperrt | Alle Android-Geräte müssen sich ohne Android for Work registrieren. |
| **Unterstützte Geräte als Android for Work-Geräte verwalten** | Zugelassen | Alle Android-Geräte, die Android for Work unterstützen, müssen sich mit Android for Work registrieren. |
| **Nur unterstützte Geräte für Benutzer in diesen Gruppen als Android for Work-Geräte verwalten** | Gesperrt | Eine separate Richtlinie für Gerätetypbeschränkungen wurde erstellt, um die Standareinstellungen außer Kraft zu setzen. Diese Richtlinie definiert die Gruppen, für die Sie zuvor die Android for Work-Registrierung zugelassen haben. Benutzer der ausgewählten Gruppen dürfen ihre Android for Work-Geräte weiterhin registrieren. Alle anderen Benutzer können sich nicht mit Android for Work registrieren. |

In beiden Fällen wird die von Ihnen vorgesehene Regulierung beibehalten. Von Ihrer Seite ist kein weiterer Vorgang erforderlich, um die globalen oder gruppenbedingten Zulassungen von Android for Work in Ihrer Umgebung zu verwalten.

### <a name="app-management"></a>App-Verwaltung

#### <a name="app-install-report-updated-to-include-install-pending-status----1249446---"></a>App-Installationsbericht mit dem Status „Installation steht aus“ aktualisiert <!-- 1249446 -->  

Der Bericht über den **Installationsstatus der App**, der in jeder App über die **App**-Liste im Workload **Mobile Apps** verfügbar ist, enthält nun für Benutzer und Geräte die Angabe **Installation steht aus** samt Anzahl.

#### <a name="ios-11-app-inventory-api-for-mobile-threat-detection----1391759---"></a>App-Bestand-API zur Bedrohungserkennung auf Mobilgeräten unter iOS 11 <!-- 1391759 -->

Intune erfasst sowohl von privaten als auch von unternehmenseigenen Geräten Informationen zum App-Bestand und stellt diese für Anbieter von Bedrohungserkennung auf Mobilgeräten (Mobile Thread Detection, MTD) wie Lookout for Work zur Verfügung. Sie können Informationen zum App-Bestand auf iOS 11-Geräten (oder höher) erfassen.

**App-Bestand**  
Die Bestände von sowohl unternehmenseigenen als auch privaten iOS 11-Geräten (oder höher) werden an Ihren MTD-Dienstanbieter übermittelt. Die Daten in den App-Beständen umfassen:

 - App-ID
 - App-Version
 - Kurzversion der App
 - App-Name
 - Größe des App-Pakets
 - Dynamische Größe der App
 - App wird geprüft oder nicht
 - App wird verwaltet oder nicht


### <a name="device-management"></a>Geräteverwaltung

#### <a name="migrate-hybrid-mdm-users-and-devices-to-intune-standalone----1463747-wnready---"></a>Migrieren von Benutzern und Geräten in eigenständiges Intune <!-- 1463747 wnready -->
Der Prozess und die Tools zum Verschieben von Benutzern und deren zugehörigen Geräten aus hybridem MDM nach Intune im Azure-Portal wurde aktualisiert. Jetzt können Sie Folgendes durchführen:
- Sie können Richtlinien und Profile aus der Configuration Manager-Konsole nach Intune im Azure-Portal verschieben.
- Sie können einen Teil der Benutzer nach Intune im Azure-Portal verschieben und den anderen Teil im hybriden MDM belassen.
- Sie können Geräte zu Intune im Azure-Portal migrieren, ohne erneut eine Registrierung durchführen zu müssen.

Ausführlichere Angaben finden Sie unter [Migrieren von Benutzern und Geräten in einer MDM-Hybridlösung zu eigenständigem Intune](https://docs.microsoft.com/sccm/mdm/deploy-use/migrate-hybridmdm-to-intunesa).

#### <a name="on-premises-exchange-connector-high-availability-support-----676614---"></a>Hochverfügbarkeit der Unterstützung von lokalem Exchange-Connector <!-- 676614 -->
Nachdem der Exchange-Connector eine Verbindung mit Exchange, die mit dem angegebenen CAS erstellt wurde, kann der Connector jetzt mit der Ermittlung andere CASs. Die primäre Zertifizierungsstellen nicht verfügbar, der Connector Failover wird auf einem anderen Zertifizierungsstellen, falls verfügbar, bis die primäre Zertifizierungsstellen verfügbar ist. Weitere Informationen finden Sie unter [auf lokales Exchange Connector-Unterstützung für hohe Verfügbarkeit](exchange-connector-install.md#on-premises-exchange-connector-high-availability-support).

#### <a name="remotely-restart-ios-device-supervised-only----1424595---"></a>Remote-Neustart von iOS-Geräten (nur überwacht) <!-- 1424595 -->

Sie können nun bei einem überwachten iOS 10.3-Gerät (und höher) über eine Geräteaktion einen Neustart auslösen. Weitere Informationen zum Geräteneustart finden Sie unter [Remotely restart devices with Intune (Remote-Neustart von Geräten mit Intune)](device-restart.md).

> [!Note]
> Für diesen Befehl wird ein überwachtes Gerät und das Zugriffsrecht **Gerätesperre** benötigt. Das Gerät wird sofort neu gestartet. Kennungsgeschützte iOS-Geräte verbinden Sie nach dem Neustart nicht wieder mit dem WLAN-Netzwerk und können unter Umständen nicht mehr mit dem Server kommunizieren.

#### <a name="single-sign-on-support-for-ios----1333645---"></a>Unterstützen des einmaligen Anmeldens (Single Sign-On, SSO) für iOS <!-- 1333645 -->  

Sie können SSO für iOS-Benutzer verwenden. Die iOS-Apps, die so programmiert wurden, dass sie nach Benutzeranmeldeinformationen in der Payload für einmaliges Anmelden suchen, sind mit diesem Payload-Konfigurationsupdate weiterhin funktionsfähig. Sie können auch den UPN und die Intune-Geräte-ID verwenden, um den Prinzipalnamen und den Bereich zu identifizieren. Ausführlichere Angaben finden Sie unter [Configure Intune for iOS device single sign-on (Konfigurieren von Intune für SSO von iOS-Geräten)](sso-ios.md).

#### <a name="add-find-my-iphone-for-personal-devices---1427287--"></a>Hinzufügen der Funktion „Find my iPhone“ („Mein iPhone finden“) für private Geräte <!--1427287-->
Ihnen wird jetzt angezeigt, ob für iOS-Geräte eine Aktivierungssperre aktiviert ist. Diese Funktion konnten Sie zuvor im klassischen Intune-Portal finden.


#### <a name="remotely-lock-managed-macos-device-with-intune----1437691---"></a>Remote-Sperren von verwalteten macOS-Geräten durch Intune <!-- 1437691 -->

Sie können ein verlorenes macOS-Gerät sperren und eine sechsstellige Wiederherstellungs-PIN festlegen. Wenn das Gerät gesperrt ist, wird im Blatt **Device overview** (Geräteübersicht) die PIN solange angezeigt, bis eine andere Geräteaktion gesendet wurde.

Weitere Informationen finden Sie unter [Remotely lock managed devices with Intune (Remote-Sperren von verwalteten Geräten durch Intune)](device-remote-lock.md).

#### <a name="new-scep-profile-details-supported----1559808---"></a>Unterstützen von neuen SCEP-Profildetails <!-- 1559808 -->

Administratoren können nun zusätzliche Einstellungen festlegen, wenn sie ein SCEP-Profil auf Windows-, iOS-, macOS- und Android-Plattformen erstellen.  Administratoren können die IMEI, die Seriennummer oder allgemeine Namen, einschließlich der E-Mail-Adresse im Format des Antragstellernamens, festlegen.

<!-- #### Update to what device details your company may see -1616825
The Company Portal app for Android can now use geofencing to protect access to company resources. It uses network details such as IP address, default gateway address, and Domain Name System (DNS) to determine whether to allow access to protected company resources. -->

#### <a name="retain-data-during-a-factory-reset----1588489---"></a>Beibehalten von Daten während einer Zurücksetzung auf Werkseinstellungen <!--1588489 -->
Beim Zurücksetzen der Windows 10-Version 1709 und höher auf die Werkseinstellungen steht eine neue Funktion zur Verfügung. Administratoren können angeben, ob die Geräteregistrierung und andere bereitgestellte Daten während einer Zurücksetzung auf Werkseinstellungen auf einem Gerät erhalten bleiben sollen.

Die folgenden Daten bleiben während der Zurücksetzung auf Werkseinstellungen erhalten:
- Dem Gerät zugeordnete Benutzerkonten
- Status der virtuellen Maschine (Domänenbeitritt, mit Azure Active Directory verknüpft)
- MDM-Registrierung
- Über OEM installierte Apps (Store- und Win32-Apps)
- Benutzerprofil
- Benutzerdaten außerhalb des Benutzerprofils
- Automatische Anmeldung des Benutzers

Die folgenden Daten bleiben nicht erhalten:
- Benutzerdateien
- Vom Benutzer installierte Apps (Store- und Win32-Apps)
- Geräteeinstellungen, die nicht dem Standard entsprechen

### <a name="monitor-and-troubleshoot"></a>Überwachung und Problembehandlung
#### <a name="window-10-update-ring-assignments-are-displayed----1621837---"></a>Zuweisungen des Windows 10-Updaterings werden angezeigt <!-- 1621837 -->
Wenn Sie für den angezeigten Benutzer **Probleme behandeln**, werden Ihnen sämtliche Zuweisungen des Windows 10-Updaterings angezeigt.  

#### <a name="windows-defender-advanced-threat-protection-reporting-frequency-settings-----1455974----"></a>Häufigkeitseinstellungen von Windows Defender Advanced Threat Protection-Berichten <!-- 1455974  -->
Der Dienst Windows Defender Advanced Threat Protection (WDETP) ermöglicht es Administratoren, zu verwalten, wie häufig für verwaltete Geräte Berichte erstellt werden sollen. Mit der neuen Option **Häufigkeit von Telemetrieberichten erhöhen** erfasst WDETP häufiger Daten und prüft Risiken. Die Standardeinstellung für die Berichterstellung optimiert Geschwindigkeit und Leistung. Für Geräte, die ein hohes Risiko darstellen,kann es sehr nützlich sein, häufiger Berichte zu erstellen. Diese Einstellung finden Sie in den **Gerätekonfigurationen** in dem Profil **Windows Defender ATP**.

#### <a name="audit-updates----1412961---"></a>Überwachungsupdates <!-- 1412961 -->  
Die Intune-Überwachung stellt einen Datensatz mit Änderungsvorgängen im Zusammenhang mit Intune zur Verfügung.  Alle Vorgänge zum Erstellen, Aktualisieren, Löschen und von Remoteaufgaben werden erfasst und für ein Jahr gespeichert.  Im Azure-Portal werden die Überwachungsdaten der letzten 30 Tage filterbar in sämtlichen Workloads dargestellt.  Eine dazugehörige Graph-API ermöglicht den Abruf von Überwachungsdaten, die über ein Jahr hinweg gespeichert wurden.

Die Überwachungsfunktion finden Sie unter der Gruppe **MONITOR**. Für jede Workload gibt es das Menüelement **Überwachungsprotokolle**.




## <a name="week-of-november-20-2017"></a>Woche vom 20. November 2017

### <a name="app-management"></a>App-Verwaltung

#### <a name="google-play-protect-support-on-android----908720---"></a>Unterstützung für Google Play Protect unter Android <!-- 908720 -->

Mit der Version Android Oreo führt Google eine Suite von Sicherheitsfunktionen namens „Google Play Protect“ ein, mit denen Benutzer und Organisationen Apps und Android-Images sicher ausführen können. Intune unterstützt Google Play Protect-Funktionen, einschließlich des SafetyNet-Remotenachweises. Administratoren können Konformitätsrichtlinienanforderungen festlegen, für die Google Play Protect konfiguriert sein und sich in einem fehlerfreien Zustand befinden muss.
Für die Verwendung der Einstellung **SafetyNet-Gerätenachweis** muss das Gerät eine Verbindung mit einem Google-Dienst herstellen, damit sichergestellt ist, dass sich das Gerät in einem fehlerfreien Zustand befindet und es nicht beeinträchtigt ist. Administratoren können zudem eine Konfigurationsprofileinstellung für Android for Work festlegen, um zu erfordern, dass installierte Apps von Google Play-Diensten überprüft werden. Wenn ein Gerät nicht mit Google Play Protect-Anforderungen kompatibel ist, können Benutzer durch den bedingten Zugriff daran gehindert werden, auf Unternehmensressourcen zuzugreifen.

- Siehe [Informationen zum Erstellen einer Gerätekonformitätsrichtlinie zum Aktivieren von Google Play Protect](https://docs.microsoft.com/intune/compliance-policy-create-google-play-protect).

#### <a name="text-protocol-allowed-from-managed-apps----1414050----"></a>Zulässige Textprotokolle verwalteter Apps <!-- 1414050  -->

Apps, die über das Intune App SDK verwaltet werden, können SMS-Nachrichten versenden.

## <a name="week-of-november-13-2017"></a>Woche vom 13. November 2017

### <a name="intune-apps"></a>Intune-Apps
#### <a name="company-portal-app-for-macos-is-available---1541700--"></a>Die Unternehmensportal-App für macOS ist verfügbar <!--1541700-->
Das Intune-Unternehmensportal unter macOS besitzt eine aktualisierte Benutzeroberfläche, die für die saubere Darstellung aller Informationen und Konformitätsbenachrichtigungen optimiert wurde, die Ihre Benutzer für alle registrierten Geräte benötigen. Nachdem das Intune-Unternehmensportal auf einem Gerät bereitgestellt wurde, stellt Microsoft AutoUpdate für macOS Updates für sie bereit. Sie können das neue Intune-Unternehmensportal für macOS herunterladen, indem Sie sich von einem macOS-Gerät aus bei der Website des Intune-Unternehmensportals anmelden.

#### <a name="microsoft-planner-is-now-part-of-the-mobile-app-management-mam-list-of-approved-apps-----1248473---"></a>Microsoft Planner ist jetzt Bestandteil der MAM-Liste (Mobile App-Verwaltung) genehmigter Apps <!-- 1248473 -->
Die Microsoft Planner-App für iOS und Android gehört jetzt zu den genehmigten Apps für die mobile App-Verwaltung (MAM). Im Azure-Portal kann die App über das Blatt „Intune-App-Schutz“ für alle Mandanten konfiguriert werden.
- Weitere Informationen zur [MAM-Liste genehmigter Apps](https://www.microsoft.com/cloud-platform/microsoft-intune-apps).

#### <a name="per-app-vpn-requirement-update-frequency-on-ios-devices------1547061---"></a>Aktualisierungshäufigkeit der Pro-App-VPN-Anforderung auf iOS-Geräten <!-- 1547061 -->  
Administratoren können jetzt Pro-App-VPN-Anforderungen für Apps auf iOS-Geräten entfernen. Betroffene Geräte werden nach ihrem nächsten Intune-Check-In aktualisiert, das in der Regel innerhalb von 15 Minuten erfolgt.  

### <a name="monitor-and-troubleshoot"></a>Überwachung und Problembehandlung
#### <a name="support-for-system-center-operations-manager-management-pack-for-exchange-connector----885457---"></a>Unterstützung für das System Center Operations Manager-Management Pack für den Exchange-Connector <!-- 885457 -->
Mit dem SCOM-Management Pack (System Center Operations Manager) für den Exchange-Connector können Sie jetzt die Exchange-Connector-Protokolle analysieren. Dies bietet Ihnen verschiedene Möglichkeiten zur Überwachung des Diensts bei der Problembehandlung.

## <a name="week-of-november-6-2017"></a>Woche vom 6. November 2017

### <a name="device-enrollment"></a>Geräteregistrierung
#### <a name="co-management-for-windows-10-devices-----1243445---"></a>Co-Verwaltung für Windows 10-Geräte <!-- 1243445 -->
Bei der Co-Verwaltung handelt es sich um eine Lösung, die eine Brücke von der herkömmlichen zur modernen Verwaltung schlägt und Ihnen die Möglichkeit bietet, die Umstellung schrittweise durchzuführen. Bei der Co-Verwaltung handelt es sich im Grunde um eine Lösung, mit der Windows 10-Geräte gleichzeitig mit Configuration Manager und Intune verwaltet werden können. Außerdem können sie in Active Directory (AD) und Azure Active Directory (Azure AD) eingebunden werden.  Diese Konfiguration bietet Ihnen eine Möglichkeit, um nach und nach den Bedürfnissen Ihrer Organisation entsprechend eine Modernisierung durchzuführen, wenn Sie nicht alles auf einmal durchführen können.  

#### <a name="new-enrollment-status-page-for-windows-10-enrollments---1063201--"></a>Neue Seite für den Registrierungsstatus für Windows 10-Registrierungen <!--1063201-->    
Sie können nun eine Begrüßung konfigurieren, die angezeigt wird, wenn Ihr Benutzer Windows 10-Geräte registriert. Verwenden Sie den Bildschirm **Registrierungsstatus**, um eine benutzerdefinierte Nachricht und einen Link zu konfigurieren, die Ihren Benutzern angezeigt werden sollen, wenn diese ihre Windows 10-Geräte registrieren.  Der Bildschirm **Registrierungsstatus** gewährt den Benutzern ebenfalls einen Einblick in den Status der Richtlinieneinstellungen, die auf deren Gerät angewendet werden.  

#### <a name="restrict-windows-enrollment-by-os-version----245498---"></a>Einschränkung der Windows-Registrierung nach Betriebssystemversion <!-- 245498 -->
Als Intune-Administrator können Sie jetzt eine Mindest- und eine Höchstversion von Windows 10 für Geräteregistrierungen angeben. Sie können diese Einschränkungen auf dem Blatt **Plattformkonfigurationen** festlegen.

Intune unterstützt auch weiterhin die Registrierung von Windows 8.1-PCs und Smartphones. Allerdings können nur für Windows 10-Versionen Grenzwerte für die Mindest- und Höchstversion festgelegt werden. Um die Registrierung von 8.1-Geräten zu erlauben, lassen Sie die Angabe für die Mindestversion leer.

#### <a name="alerts-for-windows-autopilot-unassigned-devices-----1631236---"></a>Warnungen für nicht zugewiesene Windows AutoPilot-Geräte <!-- 1631236 -->
Auf der Seite **Microsoft Intune** > **Geräteregistrierung** > **Übersicht** steht eine neue Warnung für nicht zugewiesene Windows AutoPilot-Geräte zur Verfügung. Diese Warnung zeigt, wie vielen Geräten aus dem AutoPilot-Programm keine AutoPilot-Bereitstellungsprofile zugewiesen wurden. Verwenden Sie die Informationen aus der Warnung, um Profile zu erstellen und sie den nicht zugeordneten Geräten zuzuweisen. Wenn Sie auf die Warnung klicken, sehen Sie die vollständige Liste der Windows AutoPilot-Geräte zusammen mit detaillierten Informationen. Weitere Informationen finden Sie unter [Enroll Windows devices using Windows AutoPilot Deployment Program (Registrieren von Windows-Geräten mithilfe des Windows AutoPilot Deployment-Programms)](https://docs.microsoft.com/intune/enrollment-autopilot).

### <a name="device-management"></a>Geräteverwaltung

#### <a name="refresh-button-for-devices-list-------1333581---"></a>Schaltfläche „Aktualisieren“ für Geräteliste    <!-- 1333581 -->
Da die Geräteliste nicht automatisch aktualisiert wird, können Sie die neue Schaltfläche „Aktualisieren“ verwenden, um die in der Liste angezeigten Geräte zu aktualisieren.

#### <a name="support-for-symantec-cloud-certification-authority-ca-----1333638---"></a>Unterstützung für die Symantec-Cloudzertifizierungsstelle (ZS) <!-- 1333638 -->    
Intune unterstützt nun die Symantec-Cloud-ZS, die es dem Intune Certificate Connector ermöglicht, PKCS-Zertifikate von der Symantec-Cloud-ZS für von Intune verwaltete Geräte auszustellen. Wenn Sie den Intune Certificate Connector bereits mit der Microsoft-Zertifizierungsstelle (ZS) verwenden, können Sie das vorhandene Intune Certificate Connector-Setup nutzen, um die Unterstützung für die Symantec-ZS hinzuzufügen.

#### <a name="new-items-added-to-device-inventory-----1404455---"></a>Neue Elemente im Geräteinventar   <!--1404455 -->
In dieser Version haben wir dem [Inventar der registrierten Geräte](device-inventory.md) folgende neue Elemente hinzugefügt:

- WLAN-MAC-Adresse
- Gesamtmenge des Speicherplatzes
- Gesamtmenge des freien Speicherplatzes
- MEID
- Netzbetreiber des Abonnenten


### <a name="app-management"></a>App-Verwaltung
#### <a name="set-access-for-apps-by-minimum-android-security-patch-on-the-device---1278463---"></a>Festlegen des Zugriffs für Apps durch einen mindestens erforderlichen Android-Sicherheitspatch auf dem Gerät <!-- 1278463 -->   
Ein Administrator kann den mindestens erforderlichen Android-Sicherheitspatch definieren, der auf dem Gerät installiert sein muss, um Zugriff auf eine verwaltete Anwendung mit einem verwalteten Konto zu erhalten.

> [!Note]  
> Dieses Feature schränkt nur Sicherheitspatches ein, die von Google für Android 6.0+-Geräte veröffentlicht wurden.

#### <a name="app-conditional-launch-support----1193313---"></a>App-bedingte Startunterstützung <!-- 1193313 -->
IT-Administratoren können nun eine Anforderung über das Azure-Verwaltungsportal festlegen, um eine Kennung statt einer numerischen PIN über die mobile App-Verwaltung (Mobile App Management, MAM) zu erzwingen, wenn die Anwendung gestartet wird. Wenn dies konfiguriert ist, muss der Benutzer eine Kennung festlegen und verwenden, wenn er dazu aufgefordert wird, bevor der Zugriff auf MAM-aktivierte Apps gewährt wird. Eine Kennung ist als numerische PIN mit mindestens einem Sonderzeichen oder einem Groß-/Kleinbuchstaben definiert. In dieser Version von Intune wird dieses Feature **nur unter iOS** aktiviert. Intune unterstützt Kennungen auf ähnliche Weise wie numerische PINs, nämlich indem eine Mindestlänge festgelegt wird, sodass wiederholte Zeichen und Sequenzen möglich sind. Für dieses Feature ist die Beteiligung von Anwendungen erforderlich (d.h. WXP, Outlook, Managed Browser, Yammer), um das Intune App SDK in den Code für dieses Feature anstelle der Kennungseinstellungen zu integrieren und für die Zielanwendungen zu erzwingen.

#### <a name="app-version-number-for-line-of-business-in-device-install-status-report----1233999---"></a>App-Versionsnummer für branchenspezifische Apps im Statusbericht der Geräteinstallation <!-- 1233999 -->
Ab dieser Version zeigt der Statusbericht der Geräteinstallation die App-Versionsnummern der branchenspezifischen Apps für iOS und Android an. Sie können diese Informationen verwenden, um Probleme mit Ihren Apps zu beheben oder um Geräte zu suchen, auf denen veraltete App-Versionen ausgeführt werden.


### <a name="device-configuration"></a>Gerätekonfiguration
#### <a name="admins-can-now-configure-the-firewall-settings-on-a-device-using-a-device-configuration-profile----951708---"></a>Administratoren können nun die Firewall-Einstellungen auf einem Gerät mithilfe eines Profils für die Gerätekonfiguration konfigurieren <!-- 951708 -->   
Administratoren können die Firewall für Geräte einschalten sowie verschiedene Protokolle für Domänen sowie private und öffentliche Netzwerke konfigurieren.  Diese Firewall-Einstellungen können im Profil „Endpoint Protection“ gefunden werden.

#### <a name="windows-defender-application-guard-helps-protect-devices-from-untrusted-websites-as-defined-by-your-organization----958257---"></a>Windows Defender Application Guard unterstützt den Schutz von Geräten vor nicht vertrauenswürdigen Websites gemäß den Definitionen Ihrer Organisation <!-- 958257 -->   
Administratoren können Websites mithilfe eines Windows Information Protection-Workflows oder des neuen Profils „Netzwerkgrenze“ in den Gerätekonfigurationen als „trusted“ (vertrauenswürdig) oder „corporate“ (geschäftlich) definieren. Alle Websites, die mit Microsoft Edge angezeigt werden und nicht in der vertrauenswürdigen Netzwerkgrenze eines Windows 10 Geräts (64 Bit) aufgelistet werden, werden stattdessen in einem Browser innerhalb eines virtuellen Hyper-V-Computers geöffnet.

Application Guard kann unter den Profilen für die Gerätekonfiguration im Profil „Endpoint Protection“ gefunden werden. Von dort aus können Administratoren die Interaktionen zwischen dem virtualisierten Browser und dem Hostcomputer, vertrauenswürdigen und nicht vertrauenswürdigen Websites sowie das Speichern von Daten konfigurieren, die im virtualisierten Browser generiert werden. Es muss zunächst eine Netzwerkgrenze konfiguriert werden, um Application Guard auf einem Gerät zu verwenden. Es ist wichtig, nur eine Netzwerkgrenze für ein Gerät zu definieren.  

#### <a name="windows-defender-application-control-on-windows-10-enterprise-provides-mode-to-trust-only-authorized-apps----1031096---"></a>Windows Defender Application Control unter Windows 10 Enterprise bietet einen Modus, um nur autorisierten Apps zu vertrauen <!-- 1031096 -->    
Durch Tausende von neuen, schädlichen Dateien, die jeden Tag erstellt werden, bietet das Verwenden von signaturbasierten Antivirenerkennungen zum Bekämpfen von Schadsoftware keine angemessene Verteidigung mehr gegen neue Angriffe. Indem Sie Windows Defender Application Control unter Windows 10 Enterprise verwenden, können Sie die Gerätekonfiguration von einem Modus, in dem Apps als vertrauenswürdig gelten, wenn Sie nicht von einem Antivirenprogramm oder einer anderen Sicherheitslösung blockiert werden, zu einem Modus ändern, in dem das Betriebssystem nur Apps vertraut, die von Ihrem Unternehmen autorisiert wurden. Sie weisen den Apps die Vertrauensstellung in Windows Defender Application Control zu.

Mithilfe von Intune können Sie die Anwendungssteuerungsrichtlinien entweder für den Modus „Nur überwachen“ oder „Erzwingen“ konfigurieren. Apps werden nicht blockiert, wenn diese im Modus „Nur überwachen“ ausgeführt werden. Der Modus „Nur überwachen“ protokolliert alle Ereignisse in lokalen Clientprotokollen. Sie können ebenfalls konfigurieren, ob nur Windows-Komponenten und Windows Store-Apps ausgeführt werden können, oder ob zusätzliche Apps mit gutem Ruf gemäß der Definition von Intelligent Security Graph ausgeführt werden können.

#### <a name="window-defender-exploit-guard-is-a-new-set-of-intrusion-prevention-capabilities-for-windows-10----1063615---"></a>Window Defender Exploit Guard stellt eine neue Reihe von Funktionen zur Abwendung von Eingriffen für Windows 10 dar <!-- 1063615 -->   
Window Defender Exploit Guard enthält benutzerdefinierte Regeln, um die Angreifbarkeit von Anwendungen zu reduzieren, verhindert Bedrohungen durch Makros und Skripts, blockiert automatisch Netzwerkverbindungen zu IP-Adressen mit schlechtem Ruf und kann Daten vor Ransomware und unbekannten Bedrohungen schützen. Windows Defender Exploit Guard besteht aus folgenden Komponenten:

- Die **Verringerung der Angriffsfläche (Attack Surface Reduction, ASR)** stellt Regeln bereit, die es Ihnen ermöglichen, Bedrohungen durch Makros, Skripts und E-Mails zu verhindern.
- Der **gesteuerte Ordnerzugriff** blockiert automatisch den Zugriff auf Inhalte in geschützten Ordnern.
- Der **Netzwerkfilter** blockiert ausgehende Verbindungen von jeder App mit IPs/Domänen mit schlechtem Ruf.
- Der **Exploit-Schutz** stellt Einschränkungen für den Arbeitsspeicher, die Ablaufsteuerung und Richtlinien bereit, die für den Schutz einer Anwendung vor Exploits verwendet werden können.


#### <a name="manage-powershell-scripts-in-intune-for-windows-10-devices----790537---"></a>Verwalten von PowerShell-Skripts in Intune für Windows 10-Geräte <!-- 790537 -->

Durch die Verwaltungserweiterung von Intune können Sie PowerShell-Skripts in Intune für die Ausführung auf Windows 10-Geräten hochladen. Die Erweiterungen ergänzen Funktionen für die mobile Geräteverwaltung (mobile device management, MDM) von Windows 10 und erleichtern Ihnen die Umstellung auf eine moderne Verwaltung. Details finden Sie unter [Verwalten von PowerShell-Skripts in Intune für Windows 10-Geräte](intune-management-extension.md).

#### <a name="new-device-restriction-settings-for-windows-10---------1308850---"></a>Neue Einstellungen für Geräteeinschränkungen für Windows 10 <!-- 1308850 -->
-    Messaging (nur mobil): Deaktivieren von Test- oder MMS-Nachrichten
-    Kennwort: Einstellungen zum Aktivieren von FIPS und der Verwendung von sekundären Windows Hello-Geräten für die Authentifizierung 
-    Anzeige: Einstellungen zum Aktivieren oder Deaktivieren der GDI-Skalierung für ältere Apps

#### <a name="windows-10-kiosk-mode-device-restrictions----1308872---"></a>Geräteeinschränkungen beim Windows 10-Kioskmodus <!-- 1308872 -->   
Sie können die Benutzer von Windows 10-Geräten auf den Kioskmodus beschränken, der diese auf eine Reihe von vordefinierten Apps einschränkt.  Erstellen Sie dazu ein Einschränkungsprofil für Windows 10-Geräte und legen Sie die Kioskeinstellung fest.

Der Kioskmodus unterstützt zwei Modi: **einzelne App** (ermöglicht dem Benutzer nur das Ausführen einer einzigen App) oder **mehrere Apps** (ermöglicht den Zugriff auf verschiedene Apps).  Sie definieren das Benutzerkonto und den Gerätenamen, der die unterstützten Apps definiert.  Wenn der Benutzer angemeldet ist, ist dieser auf die definierten Apps beschränkt.  Weitere Informationen finden Sie unter [AssignedAccess CSP](https://docs.microsoft.com/windows/client-management/mdm/assignedaccess-csp). 

Der Kioskmodus erfordert Folgendes:

- Intune muss die MDM-Autorität sein.
- Die Apps müssen bereits auf dem Zielgerät installiert sein.
- Das Gerät muss [ordnungsgemäß bereitgestellt](https://docs.microsoft.com/windows/configuration/set-up-a-kiosk-for-windows-10-for-desktop-editions) sein.

#### <a name="new-device-configuration-profile-for-creating-network-boundaries----1311967---"></a>Neues Gerätekonfigurationsprofil für das Erstellen von Netzwerkgrenzen <!-- 1311967 -->   
Es wurde ein Gerätekonfigurationsprofil namens **Netzwerkgrenze** erstellt, das bei Ihren anderen Gerätekonfigurationsprofilen gefunden werden kann. Verwenden Sie dieses Profile, um Onlineressourcen zu definieren, die als „geschäftlich“ oder „vertrauenswürdig“ angesehen werden sollen. Sie müssen eine Netzwerkgrenze für ein Gerät definieren, *bevor* Features wie Windows Defender Application Guard und Windows Information Protection auf dem Gerät verwendet werden können. Es ist wichtig, nur eine Netzwerkgrenze für jedes Gerät zu definieren.

Sie können Unternehmenscloudressourcen, IP-Adressbereiche und interne Proxyserver definieren, die als vertrauenswürdig angesehen werden sollen. Sobald diese definiert sind, kann die Netzwerkgrenze von anderen Features wie Windows Defender Application Guard und Windows Information Protection verwendet werden.

####  <a name="two-additional-settings-for-windows-defender-antivirus----1338409---"></a>Zwei zusätzliche Einstellungen für Windows Defender Antivirus <!-- 1338409 -->  
**Ebene der Dateiblockierung**

| | |
|---|---|
| Nicht konfiguriert | **Nicht konfiguriert** verwendet die Standardblockierungsebene von Windows Defender Antivirus und bietet eine starke Erkennung ohne das Risiko zu erhöhen, zulässige Dateien zu erkennen. |
| Hoch | **Hoch** wendet eine starke Erkennungsebene an.
| Hoch +  | **Hoch +** bietet die Ebene „Hoch“ mit zusätzlichen Schutzmaßnahmen, die sich auf die Clientleistung auswirken können.
| Keine Toleranz  | **Keine Toleranz** blockiert alle unbekannten ausführbaren Dateien. |

Es ist zwar unwahrscheinlich, aber dennoch können bei der Einstellung auf **Hoch** einige zulässige Dateien erkannt werden.
Es wird empfohlen, die Ebene der Datenblockierung auf den Standardwert, **Nicht konfiguriert**, festzulegen.

**Timeouterweiterung für die Dateiüberprüfung durch die Cloud**  

| | |
|--|--|
| Anzahl von Sekunden (0–50) | Geben Sie den maximalen Zeitraum an, für den Windows Defender Antivirus eine Datei blockieren soll, während auf ein Ergebnis von der Cloud gewartet wird. Der Standardzeitraum beträgt 10 Sekunden. Jede zusätzliche Zeit, die hier angegeben wird (bis zu 50 Sekunden), wird zu diesen 10 Sekunden addiert. In den meisten Fällen nimmt der Scan wesentlich weniger als den Maximalwert in Anspruch. Das Erweitern des Zeitraums ermöglicht es der Cloud, verdächtige Dateien gründlich zu überprüfen. Es wird empfohlen, diese Einstellung zu aktivieren und mindestens 20 zusätzliche Sekunden anzugeben. |

#### <a name="citrix-vpn-added-for-windows-10-devices----1512457---"></a>Citrix-VPN wurde für Windows 10-Geräte hinzugefügt <!-- 1512457 -->  
Sie können Citrix-VPN für ihre Windows 10-Geräte konfigurieren. Sie können Citrix-VPN in der Liste *Verbindungstyp auswählen* im Blatt **Basis-VPN** auswählen, wenn Sie ein VPN für Windows 10 oder höher konfigurieren.

> [!Note]
> Die Citrix-Konfiguration ist bereits für iOS und Android vorhanden.

#### <a name="wi-fi-connections-support-pre-shared-keys-on-ios----1550823---"></a>WLAN-Verbindungen unterstützen vorinstallierte Schlüssel unter iOS <!-- 1550823 -->
Kunden können WLAN-Profile konfigurieren, um vordefinierte Schlüssel (pre-shared keys, PSK) für persönliche WPA/WPA2-Verbindungen auf iOS-Geräten zu verwenden. Diese Profile werden per Push an das Gerät des Benutzers übertragen, wenn das Gerät bei Intune registriert wird.

Wenn das Profil an das Gerät übertragen wurde, hängt der nächste Schritt von der Profilkonfiguration ab.  Wenn automatisches Herstellen einer Verbindung festgelegt ist, geschieht das bei der nächsten Gelegenheit, bei der das Netzwerk benötigt wird.  Wenn das Profil manuelles Herstellen der Verbindung festlegt, muss der Benutzer die Verbindung manuell aktivieren.  

### <a name="intune-apps"></a>Intune-Apps

#### <a name="access-to-managed-app-logs-for-ios----1469920---"></a>Zugriff auf Protokolle von verwalteten Geräten für iOS <!-- 1469920 -->
Endbenutzer, bei denen der Managed Browser installiert ist, können jetzt den Verwaltungsstatus aller von Microsoft veröffentlichten Apps anzeigen und Protokolle zur Problembehandlung ihrer verwalteten iOS-Apps senden.

Informationen zum Aktivieren des Problembehandlungsmodus im Managed Browser auf einem iOS-Gerät finden Sie unter [Zugreifen auf Protokolle von verwalteten Apps mithilfe des Managed Browsers unter iOS](app-configuration-managed-browser.md#how-to-access-to-managed-app-logs-using-the-managed-browser-on-ios).

#### <a name="improvements-to-device-setup-workflow-in-the-company-portal-for-ios-in-version-290----1417174---"></a>Verbesserungen des Workflows für das Gerätesetup im Unternehmensportal für iOS in Version 2.9.0 <!-- 1417174 -->

Der Workflow für die Geräteinstallation in der Unternehmensportal-App unter iOS wurde verbessert. Die Sprache ist nun benutzerfreundlicher. Zudem haben wir Bildschirme nach Möglichkeit zusammengefasst. Zudem haben wir die Sprache speziell für Ihr Unternehmen angepasst, indem der Name Ihres Unternehmens im gesamten Setuptext verwendet wird. Dieser aktualisierte Workflow ist auf der Seite mit den  [Aktualisierungen für die Benutzeroberfläche für Endbenutzer-Apps in Intune](whats-new-app-ui.md) zu sehen.

### <a name="monitor-and-troubleshoot"></a>Überwachung und Problembehandlung

#### <a name="user-entity-contains-latest-user-data-in-data-warehouse-data-model----1544273---"></a>Die Benutzerentität enthält die aktuellen Benutzerdaten im Data Warehouse-Datenmodell <!-- 1544273 -->
Die erste Version des Intune Data Warehouse-Datenmodells enthielt lediglich aktuelle Verlaufsdaten für Intune. Berichtersteller konnten den aktuellen Status eines Benutzers nicht erfassen. In diesem Update wird die **Benutzerentität** mit den aktuellen Benutzerdaten voraufgefüllt.


## <a name="week-of-october-30-2017"></a>Woche vom 30. Oktober 2017

### <a name="app-management"></a>App-Verwaltung

#### <a name="ios-and-android-line-of-business-app-version-number-is-visible----1380712---"></a>Die branchenspezifische App-Versionsnummer für iOS und Android ist sichtbar <!-- 1380712 -->.

Apps in Intune zeigen nun die Versionsnummer für branchenspezifische iOS- und Android-Apps an. Die Nummer wird im Azure-Portal in der App-Liste und im Übersichtsblatt der App angezeigt. Benutzer können die App-Nummer in der Unternehmensportal-App und im Webportal anzeigen.

__Vollständige Versionsnummer__: Die vollständige Versionsnummer identifiziert ein bestimmtes Release der App. Die Nummer wird als _Version_(_Build_) angezeigt. Beispielsweise 2.2(2.2.17560800)

Die vollständige Versionsnummer besteht aus zwei Komponenten:

 - **Version**  
   Die Versionsnummer ist die von einem Menschen lesbare Releasenummer der App. Diese wird von Benutzern verwendet, um verschiedene Releases der App zu identifizieren.

 - **Buildnummer**  
    Die Buildnummer ist eine interne Nummer, die in der App-Erkennung und zur programmgesteuerten Verwaltung der App verwendet werden kann. Die Buildnummer bezieht sich auf eine Iteration der App, die auf Änderungen im Code verweist.

Weitere Informationen zu Versionsnummern und dem Entwickeln von branchenspezifischen Apps finden Sie unter [Erste Schritte mit dem Microsoft Intune App SDK](app-sdk-get-started.md#line-of-business-app-version-numbers).

#### <a name="device-and-app-management-integration----677972---"></a>Integration der Verwaltung von Geräten und Apps <!-- 677972 -->   
Da auf die mobile Geräteverwaltung (Mobile Device Management, MDM) und die mobile Anwendungsverwaltung (Mobile Application Management, MAM) nun über das Azure-Portal zugegriffen werden kann, hat Intune damit begonnen, die Vorteile für IT-Administratoren bei der Verwaltung von Anwendungen und Geräten zu integrieren. Diese Änderungen sind darauf ausgerichtet, das Verwalten von Geräten und Apps zu vereinfachen.

Weitere Informationen zu den angekündigten Änderungen an MDM und MAM finden Sie im [Blog des Intune-Supportteams](https://blogs.technet.microsoft.com/intunesupport/2017/09/19/support-tip-setting-up-communication-between-mam-managed-and-mdm-managed-apps/).

#### <a name="new-enrollment-alerts-for-apple-devices----1471790---"></a>Neue Warnungen für Apple-Geräte bei der Registrierung <!-- 1471790 -->
Die Übersichtsseite für die Registrierung zeigt nützliche Warnungen für IT-Administratoren für die Verwaltung von Apple-Geräten an. Warnungen werden auf der Seite „Übersicht“ angezeigt, wenn das Apple-MDM-Push-Zertifikat abläuft oder bereits abgelaufen ist, wenn das Token des Programms zur Geräteregistrierung abläuft oder bereits abgelaufen ist und wenn es nicht zugewiesene Geräte im Programm zur Geräteregistrierung gibt.

#### <a name="support-token-replacement-for-app-configuration-without-device-enrollment----1080364---"></a>Unterstützung des Ersetzens von Tokens für die App-Konfiguration ohne Geräteregistrierung <!-- 1080364 -->

Sie können Tokens für dynamische Werte in App-Konfigurationen für nicht registrierte Geräte verwenden. Weitere Informationen finden Sie unter [Add app configuration policies for managed apps without device enrollment (Hinzufügen von App-Konfigurationsrichtlinien für verwaltete Apps ohne Geräteregistrierung)](app-configuration-policies-managed-app.md).

### <a name="intune-apps"></a>Intune-Apps

#### <a name="updates-to-the-company-portal-app-for-windows-10---1299474--"></a>Updates an der Unternehmensportal-App für Windows 10 <!--1299474-->
Die Seite „Einstellungen“ in der Unternehmensportal-App für Windows 10 wurde aktualisiert, um die Einstellungen und beabsichtigten Benutzeraktionen für alle Einstellungen konsistenter zu gestalten. Sie wurde zudem an das Layout anderer Windows-Apps angepasst. Auf der Seite mit den [Neuheiten in der App-Benutzeroberfläche](whats-new-app-ui.md) finden Sie Abbildungen von vor und nach der Aktualisierung.

#### <a name="inform-end-users-what-device-information-can-be-seen-for-windows-10-devices---1337920--"></a>Informieren von Endbenutzern zu den für Windows 10-Geräte sichtbaren Geräteinformationen<!--1337920-->
Wir haben dem Bildschirm „Gerätedetails“ den **Besitzertyp** für die Unternehmensportal-App für Windows 10 hinzugefügt. So können Benutzer direkt auf dieser Seite mehr über die Privatsphäre in der Dokumentation für Intune-Endbenutzer herausfinden. Diese Informationen sind außerdem auf dem Bildschirm **Info** zu finden.

#### <a name="feedback-prompts-for-the-company-portal-app-for-android---1165249--"></a>Feedbackaufforderungen für die Unternehmensportal-App für Android <!--1165249-->
Die Unternehmensportal-App für Android bittet Endbenutzer jetzt um Feedback. Dieses Feedback wird direkt an Microsoft gesendet. So erhalten Endbenutzer die Möglichkeit, die App im öffentlichen Google Play Store zu rezensieren. Feedback ist nicht erforderlich, und die Meldung kann problemlos geschlossen werden, damit Benutzer die App weiterhin verwenden können.

<!-- #### Update to what device details an organization can see 1616825
The Company Portal app for Android can now use geofencing to protect access to company resources. It uses network details such as IP address, default gateway address, and Domain Name System (DNS) to determine whether to allow access to protected company resources.-->

#### <a name="helping-your-users-help-themselves-with-the-company-portal-app-for-android----1573324-1573150-1558616-1564878---"></a>Unterstützen Ihrer Benutzer bei der eigenständigen Problemlösung über die Unternehmensportal-App für Android <!-- 1573324, 1573150, 1558616, 1564878 -->

In der Unternehmensportal-App für Android wurden Anweisungen für Benutzer hinzugefügt, um ihnen Anwendungsfälle zu erläutern und ihnen nach Möglichkeit das eigenständige Lösen dieser Anwendungsfälle zu ermöglichen.
- Endbenutzer der Assistent unterstützt Sie auf die [Azure Active Directory-Portal](https://account.activedirectory.windowsazure.com/r/#/profile) ein Gerät zu entfernen, wenn sie die maximale Anzahl von Geräten, die sie erreicht haben hinzufügen dürfen.
- Den Benutzern wird eine Anleitung zur Verfügung gestellt, die ihnen dabei helfen soll, [Fehler bei der Aktivierung auf Samsung KNOX-Geräten zu beheben](https://go.microsoft.com/fwlink/?linkid=859718) oder [den Energiesparmodus zu deaktivieren](/intune-user-help/power-saving-mode-android). Wenn keine dieser Lösungen bei der Behebung des Problems hilft, werden wir eine Erklärung zur Verfügung stellen, in der beschrieben wird, [wie Protokolle an Microsoft übermittelt werden können](/intune-user-help/send-logs-to-microsoft-ios).

#### <a name="new-resolve-action-available-for-android-devices----1583480---"></a>Neue „Lösungs“-Aktion für Android-Geräte verfügbar <!-- 1583480 -->

In der Unternehmensportal-App für Android wird eine „Lösungs“-Aktion auf der Seite _Geräteeinstellungen aktualisieren_ eingeführt. Wenn der Benutzer diese Option auswählt, wird er direkt zu der Einstellung weitergeleitet, die dafür verantwortlich ist, dass das Gerät nicht kompatibel ist. Derzeit unterstützt die Unternehmensportal-App für Android diese Aktion für die Einstellungen [Gerätekennung](/intune-user-help/set-your-pin-or-password-android), [USB-Debuggen](/intune-user-help/you-need-to-turn-off-usb-debugging-android) und [Unbekannte Quellen](/intune-user-help/you-need-to-turn-off-unknown-sources-android).

#### <a name="device-setup-progress-indicator-in-android-company-portal----1565657---"></a>Statusanzeige für das Gerätesetup im Android-Unternehmensportal <!-- 1565657 -->
Die Unternehmensportal-App für Android zeigt eine Statusanzeige für das Gerätesetup an, wenn ein Benutzer sein Gerät registriert. Der Indikator zeigt neue Statusangaben an, beginnend bei „Ihr Gerät wird eingerichtet...“, dann „Das Gerät wird registriert...“, dann „Die Registrierung Ihres Geräts wird abgeschlossen...“ und schließlich „Die Einrichtung Ihres Geräts wird abgeschlossen...“.

## <a name="week-of-october-23-2017"></a>Woche vom 23. Oktober 2017

### <a name="intune-apps"></a>Intune-Apps
#### <a name="certificate-based-authentication-support-on-the-company-portal-for-ios---1029830--"></a>Unterstützung der zertifikatbasierten Authentifizierung auf dem Unternehmensportal für iOS <!--1029830-->
Es wurde eine Unterstützung für die zertifikatbasierte Authentifizierung in der Unternehmensportal-App für iOS hinzugefügt. Benutzer mit zertifikatbasierter Authentifizierung geben ihren Benutzernamen ein und tippen dann auf den Link „Sign in with a certificate“ (Mit einem Zertifikat anmelden). Die zertifikatbasierte Authentifizierung wird auf den Unternehmensportal-Apps für Android und Windows bereits unterstützt. Weitere Informationen finden Sie auf der Seite [Anmelden bei der Unternehmensportal-App](https://docs.microsoft.com/intune-user-help/sign-in-to-the-company-portal).

#### <a name="apps-that-are-available-with-or-without-enrollment-can-now-be-installed-without-being-prompted-for-enrollment----1334712---"></a>Apps, die mit oder ohne Registrierung verfügbar sind, können nun installiert werden, ohne dass Sie zur Registrierung aufgefordert werden. <!-- 1334712 -->

Unternehmens-Apps, die mit oder ohne Registrierung in der Android-Unternehmensportal-App zur Verfügung gestellt wurden, können jetzt installiert werden, ohne dass Sie zur Registrierung aufgefordert werden.

## <a name="week-of-october-16-2017"></a>Woche vom 16. Oktober 2017
### <a name="device-enrollment"></a>Geräteregistrierung
#### <a name="windows-autopilot-deployment-program-support-in-microsoft-intune-----747617----"></a>Unterstützung des Windows AutoPilot Deployment-Programms in Microsoft Intune <!-- 747617  -->
Sie können Microsoft Intune jetzt mit dem Windows AutoPilot Deployment-Programm verwenden, um es Ihren Benutzern zu ermöglichen, ihre Unternehmensgeräte bereitzustellen, ohne die IT-Abteilung kontaktieren zu müssen. Sie können die Windows-Willkommensseite anpassen und Benutzer dazu anleiten, ihre Geräte mit Azure AD zu verknüpfen und sich bei Intune zu registrieren. Da Microsoft Intune und Windows AutoPilot zusammenarbeiten, besteht keine Notwendigkeit, Betriebssystemabbilder bereitzustellen, zu aktualisieren und zu verwalten. Weitere Informationen finden Sie unter [Enroll Windows devices using Windows AutoPilot Deployment Program (Registrieren von Windows-Geräten mithilfe des Windows AutoPilot Deployment-Programms)](https://docs.microsoft.com/intune/enrollment-autopilot).

#### <a name="quick-start-for-device-enrollment-----1425655---"></a>Schnellstart für die Geräteregistrierung <!-- 1425655 --> 
Die Schnellstart-Funktion ist jetzt in der **Geräteregistrierung** verfügbar, und es wird eine Tabelle mit Verweisen zur Verfügung gestellt, mit denen Plattformen verwaltet und Registrierungsvorgänge konfiguriert werden. In Kurzbeschreibungen für jedes Element und über verschiedene Links zu Dokumentationen mit ausführlichen Anleitungen werden nützliche Informationen zur Verfügung gestellt, die die ersten Schritte vereinfachen.

#### <a name="device-categorization----1427491---"></a>Gerätekategorisierung <!-- 1427491 -->
Über das Plattformdiagramm für registrierte Geräte auf dem Blatt **Geräte > Übersicht** werden Geräte nach Plattform, u.a. Android. iOS, macOS, Windows und Windows Mobile, angeordnet.  Geräte, auf denen andere Betriebssysteme installiert sind, werden der Gruppe „Andere“ zugeordnet.  Dies betrifft auch Geräte, die von Blackberry, NOKIA und anderen hergestellt werden.  

Um zu erfahren, welche Geräte in Ihrem Mandanten betroffen sind, klicken Sie auf **Verwalten > Alle Geräte**, und verwenden Sie anschließend die Funktion **Filtern**, um das Feld für die **Betriebssysteme** einzuschränken.

### <a name="device-management"></a>Geräteverwaltung
#### <a name="zimperium---new-mobile-threat-defense-partner------954681---"></a>Zimperium: neuer Mobile Threat Defense-Partner <!-- 954681 -->  
Sie können den Zugriff mobiler Geräte auf Unternehmensressourcen mit bedingtem Zugriff basierend auf Risikobewertungen steuern, die von Zimperium vorgenommen werden, einer Mobile Threat Defense-Lösung, die mit Microsoft Intune zusammenarbeitet.

##### <a name="how-integration-with-intune-works"></a>Funktionsweise der Integration mit Intune
Das Risiko wird basierend auf Telemetriedaten von Geräten bewertet, auf denen Zimperium ausgeführt wird. Sie können Richtlinien für bedingten EMS-Zugriff basierend auf der Zimperium-Risikobewertung konfigurieren, die über Intune-Gerätekompatibilitätsrichtlinien aktiviert werden, und so anhand der erkannten Bedrohungen nicht kompatible Geräte für den Zugriff auf Unternehmensressourcen zulassen oder blockieren.

#### <a name="new-settings-for-windows-10-device-restriction-profile------978575-1308849---"></a>Neue Einstellungen für das Windows 10-Geräteeinschränkungsprofil <!--- 978575, 1308849, -->  
Wir fügen neue Einstellungen zum Geräteeinschränkungsprofil für Windows 10 in der Kategorie „Windows Defender SmartScreen“ hinzu.

Details zum Geräteeinschränkungsprofil für Windows 10 finden Sie in den [Einstellungen für die Geräteeinschränkung für Windows 10 und höher]( device-restrictions-windows-10.md).

#### <a name="remote-support-for-windows-and-windows-mobile-devices------1070473---"></a>Remote Support für Windows- und Windows Mobile-Geräte <!-- 1070473 -->  
Intune kann jetzt die nicht im Lieferumfang inbegriffene [TeamViewer](https://www.teamviewer.com)-Software verwenden, damit Sie Ihren Benutzern, die Windows- und Windows Mobile-Geräte ausführen, Remote Support anbieten können.

#### <a name="scan-devices-with-windows-defender----1280988--1280990-----"></a>Überprüfen von Geräten mit Windows Defender <!-- 1280988  1280990   -->
Auf verwalteten Windows 10-Geräten können Sie jetzt mithilfe von Windows Defender Antivirus eine **Schnellüberprüfung** und eine **vollständige Überprüfung** durchführen sowie **Signaturen aktualisieren**. Wählen Sie auf dem Übersichtsblatt des Geräts die Aktion aus, die auf dem Gerät ausgeführt werden soll. Sie werden dann aufgefordert, die Aktion zu bestätigen, bevor der Befehl an das Gerät gesendet wird. 

**Schnellüberprüfung**: Bei einer Schnellüberprüfung werden Speicherorte überprüft, an denen Schadsoftware bei Startvorgängen registriert werden (z.B. Registrierungsschlüssel und bekannte Windows-Startordner). Eine Schnellüberprüfung dauert durchschnittlich fünf Minuten. In Kombination mit der Einstellung **AlwaysOn-Echtzeitschutz**, die Dateien überprüft, wenn ein Benutzer diese öffnet, schließt und in einem Ordner navigiert, kann eine Schnellüberprüfung Schutz vor Schadsoftware bieten, die sich eventuell im System oder Kernel befinden. Die Überprüfungsergebnisse werden Benutzern nach Abschluss der Überprüfung angezeigt. 

**Vollständige Überprüfung**: Eine vollständige Überprüfung kann sich für Geräte als nützlich erweisen, bei denen eine Bedrohung durch eine Schadsoftware erkannt wurde. So kann festgestellt werden, ob inaktive Komponenten vorhanden sind, die eine gründlichere Bereinigung erfordern. Auch bei Bedarf können Überprüfungen ausgeführt werden. Die Ausführung einer vollständigen Überprüfung kann eine Stunde dauern. Die Überprüfungsergebnisse werden Benutzern nach Abschluss der Überprüfung angezeigt. 

**Aktualisieren von Signaturen**: Der Befehl zum Aktualisieren von Signaturen aktualisiert Definitionen von Schadsoftware und Signaturen von Windows Defender Antivirus. Dadurch wird eine effiziente Erkennung von Schadsoftware durch Windows Defender Antivirus sichergestellt. Diese Funktion gilt nur für Windows 10-Geräte bei bestehender Internetkonnektivität. 

#### <a name="the-enabledisable-button-is-removed-from-the-intune-certificate-authority-page-of-the-intune-azure-portal-----1400455---"></a>Die Aktivierungs- bzw. Deaktivierungsschaltfläche wurde von der Seite „Intune-Zertifizierungsstelle“ im Azure-Portal für Intune entfernt <!-- 1400455 -->
 Dadurch wird ein zusätzlicher Schritt bei der Einrichtung des Zertifikatconnectors auf Intune entfernt. Derzeit laden Sie den Zertifikatconnector herunter und aktivieren ihn anschließend in der Intune-Konsole. Wenn Sie allerdings den Connector in der Intune-Konsole deaktivieren, gibt der Connector weiter Zertifikate aus.

##### <a name="how-does-this-affect-me"></a>Inwiefern betrifft das mich?
Ab Oktober wird die Aktivierungs- bzw. Deaktivierungsschaltfläche nicht mehr auf der Seite „Intune-Zertifizierungsstelle“ im Azure-Portal angezeigt. Die Connector-Funktionalität ändert sich nicht. Zertifikate werden weiterhin für Geräte bereitgestellt, die in Intune registriert sind. Sie können ebenfalls weiterhin den Zertifikatconnector herunterladen und installieren. Wenn Sie verhindern wollen, dass Zertifikate ausgestellt werden, müssen Sie jetzt den Zertifikatorconnector deinstallieren anstatt ihn nur zu deaktivieren.

##### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>Wie sollte ich mich für die Änderung vorbereiten?
Wenn derzeit der Zertifikatconnector deaktiviert ist, müssen Sie ihn deinstallieren.

### <a name="device-configuration"></a>Gerätekonfiguration
#### <a name="new-settings-for-windows-10-team-device-restriction-profile-------1308838---"></a>Neue Einstellungen für das Windows 10 Team-Geräteeinschränkungsprofil <!--- 1308838 -->
Zu dieser Version wurden viele neue Einstellungen für das Windows 10 Team-Geräteeinschränkungsprofil hinzugefügt, um Sie bei der Steuerung von Surface Hub-Geräten zu unterstützen.

Weitere Informationen zu diesem Profil finden Sie unter [Einstellungen für Windows 10 Team-Geräteeinschränkungen](device-restrictions-windows-10-teams.md).

#### <a name="prevent-users-of-android-devices-from-changing-their-device-date-and-time-----1333292---"></a>Blockieren von Änderungen an Datums- und Uhrzeiteinstellungen von Android-Geräten durch Benutzer <!-- 1333292 -->
Durch [benutzerdefinierte Android-Geräterichtlinien](custom-settings-android.md) können Sie Benutzer von Android-Geräten daran hindern, Datums- und Uhrzeiteinstellungen von Geräten zu ändern.

Hierfür konfigurieren Sie eine benutzerdefinierte Android-Richtlinie mit dem Einstellungs-URI „./Vendor/MSFT/PolicyManager/My/System/AllowDateTimeChange“, legen diesen auf **TRUE** fest und weisen dann die erforderlichen Gruppen zu.

#### <a name="bitlocker-device-configuration----1397398---"></a>BitLocker-Gerätekonfiguration <!-- 1397398 -->
Die Einstellungen unter **Windows-Verschlüsselung > Basiseinstellungen** umfassen die neue Einstellung **Warnung für andere Datenträgerverschlüsselung**, mit der Sie die [Eingabeaufforderung bei Warnungen](https://docs.microsoft.com/windows/client-management/mdm/bitlocker-csp#allowarningforotherdiskencryption) für andere Datenträgerverschlüsselungen, die eventuell auf dem Gerät des Benutzers verwendet werden, deaktivieren können.  Für die Eingabeaufforderung bei Warnungen ist die Zustimmung des Endbenutzers erforderlich, bevor BitLocker auf dem Gerät eingerichtet wird. Zudem wird das BitLocker-Setup erst durchgeführt, wenn die Eingabeaufforderung vom Endbenutzer bestätigt wurde.  Die neue Einstellung deaktiviert die Warnung für Endbenutzer.


### <a name="app-management"></a>App-Verwaltung
#### <a name="volume-purchase-program-for-business-apps-will-now-sync-to-your-intune-tenant----800882---"></a>Volume Purchase Program für Geschäftsanwendungen werden jetzt mit Ihrem Intune-Mandanten synchronisiert <!-- 800882 -->  
Drittentwickler können, wie in iTunes Connect angegeben, privat ihre Apps an autorisierte Mitglieder von VPP für Unternehmen verteilen. Diese Mitglieder des VPP für Unternehmen können sich im VPP-App Store registrieren und ihre Apps dort erwerben.

Mit dieser Version beginnt die VPP für Geschäftsanwendungen, die der Benutzer erworben hat, jetzt mit der Synchronisierung mit Ihren Intune-Mandanten.

#### <a name="select-apple-country-store-to-sync-vpp-apps-----1332311---"></a>Auswählen des regionalen Apple App Store zum Synchronisieren von VPP-Apps <!-- 1332311 -->  
Beim Hochladen Ihres VPP-Tokens können Sie den regionalen VPP Store (Volume Purchase Program) konfigurieren. Intune synchronisiert VPP-Apps für alle Gebietsschemas aus dem jeweiligen regionalen VPP Store.

> [!NOTE]  
> Derzeit synchronisiert Intune nur VPP-Apps aus dem regionalen VPP Store mit dem Intune-Gebietsschema, in dem der Intune-Mandant erstellt wurde.


### <a name="intune-apps"></a>Intune-Apps
#### <a name="block-copy-and-paste-between-work-and-personal-profiles-in-android-for-work----1098994---"></a>Blockieren der Funktion zum Kopieren und Einfügen zwischen Arbeitsprofilen und persönlichen Profilen in Android for Work <!-- 1098994 -->
Mit dieser Version können Sie das Arbeitsprofil für Android for Work konfigurieren, um die Funktion zum Kopieren und Einfügen zwischen Arbeits- und persönlichen Apps zu blockieren. Sie finden diese neue Einstellung im Profil **Geräteeinschränkungen** für die **Android for Work**-Plattform unter **Arbeitsprofileinstellungen**.

#### <a name="create-ios-apps-limited-to-specific-regional-apple-app-stores----1281692---"></a>Erstellen von auf bestimmten regionalen Apple App Stores beschränkten iOS-Apps <!-- 1281692 -->
Bei der Erstellung einer verwalteten Apple App Store-App haben Sie die Möglichkeit, das Gebietsschema anzugeben.

> [!Note]  
> Derzeit können nur verwaltete Apple App Store-Apps erstellt werden, die im Store für die USA zur Verfügung gestellt werden.

####  <a name="update-ios-vpp-user-and-device-licensed-apps-----1305564---"></a>Aktualisieren von für Benutzer und Geräte lizenzierten iOS-VPP-Apps <!-- 1305564 -->  
Durch Konfigurieren des iOS-VPP-Tokens können Sie alle Apps aktualisieren, die für dieses Token über den Intune-Dienst erworben wurden. Intune erkennt Updates für VPP-Apps in App Store und überträgt diese beim Geräte-Check-In automatisch mithilfe von Push auf das Gerät.

Informationen über die einzelnen Schritte, wie Sie VPP-Token festlegen und automatische Updates aktivieren, finden Sie unter „How to manage iOS apps purchased through a volume-purchase program with Microsoft Intune“ („Verwalten von iOS-Apps, die über ein Volume Purchase Program mit Microsoft Intune erworben werden).


### <a name="monitor-and-troubleshoot"></a>Überwachung und Problembehandlung
#### <a name="user-device-association-entity-collection-added-to-intune-data-warehouse-data-model----1187917---"></a>Hinzufügen der Entitätssammlung von Benutzergerätezuordnungen zum Intune Data Warehouse-Datenmodell <!-- 1187917 -->
Mithilfe von Informationen über Benutzergerätezuordnungen können Sie Berichte und Datenvisualisierungen erstellen, die Entitätssammlungen von Benutzern und Geräten zuordnet. Auf das Datenmodell kann über die Power BI-Datei (PBIX) zugegriffen werden, die über die Data Warehouse-Seite von Intune, den OData-Endpunkt oder durch die Entwicklung eines benutzerdefinierten Clients abgerufen wird.

#### <a name="review-policy-compliance-for-windows-10-update-rings----1067886---"></a>Überprüfen der Richtlinienkonformität für Windows 10-Updateringe <!-- 1067886 -->
Unter „Softwareupdates > Bereitstellungsstatus pro Updatering“ können Sie einen Richtlinienbericht für Ihre Windows 10-Updateringe einsehen. Der Richtlinienbericht gibt den Bereitstellungsstatus für die Updateringe an, die Sie konfiguriert haben. 

#### <a name="new-report-that-lists-ios-devices-with-older-ios-versions------1352223---"></a>Neuer Bericht, der iOS-Geräte mit älteren iOS-Versionen auflistet <!-- 1352223 -->
Der Bericht **Out-of-date iOS Devices (Veraltete iOS-Geräte)** ist im Arbeitsbereich **Softwareupdates** verfügbar. Im Report sehen Sie eine Liste überwachter iOS-Geräte, die unter eine iOS-Updaterichtlinie fallen und mehrere verfügbare Updates besitzen. Für jedes Gerät können Sie einen Status anzeigen, warum das Gerät nicht automatisch aktualisiert wurde. 

#### <a name="view-app-protection-policy-assignments-for-troubleshooting-----1475003---"></a>Anzeigen der Zuweisungen von App-Schutzrichtlinien für die Problembehandlung <!--  1475003 -->
In der kommenden Version wird auf dem Blatt „Problembehandlung“ die Option **App-Schutzrichtlinie** zur Dropdown-Liste **Zuweisungen** hinzugefügt. Nun können Sie App-Schutzrichtlinien auswählen, um die für ausgewählte Benutzer zugewiesenen App-Schutzrichtlinien anzuzeigen.



## <a name="week-of-october-2-2017"></a>Woche vom 2. Oktober 2017
### <a name="intune-apps"></a>Intune-Apps
#### <a name="improvements-to-device-setup-workflow-in-company-portal---1490692--"></a>Verbesserungen des Workflows für die Geräteinstallation im Unternehmensportal <!--1490692-->
Der Workflow für die Geräteinstallation in der Unternehmensportal-App unter Android wurde verbessert. Die Sprache ist nun benutzerfreundlicher und spezifisch für Ihr Unternehmen. Zudem haben wir wo es möglich war Bildschirme vereint. Sie können diese auf der Seite [Was gibt es Neues auf der App-Benutzeroberfläche](whats-new-app-ui.md#week-of-october-2-2017) anzeigen.

#### <a name="improved-guidance-around-the-request-for-access-to-contacts-on-android-devices---1484985--"></a>Verbesserter Leitfaden bezüglich der Anforderung des Zugriffs auf Kontakte auf Android-Geräten <!--1484985-->

Die Unternehmensportal-App für Android erfordert oft, dass Benutzer die Kontaktberechtigungen akzeptieren. Wenn ein Benutzer diesen Zugriff verweigert, wird ihm eine In-App-Benachrichtigung angezeigt, die ihn anweist, diesen für den bedingten Zugriff zu gewähren. 

#### <a name="secure-startup-remediation-for-android---1490712--"></a>Secure Startup-Wartung für Android <!--1490712-->

Benutzer von Android-Geräten können den Grund der Nichtkompatibilität in der Unternehmensportal-App wählen. Wenn möglich werden sie direkt an den korrekten Ort in der Einstellungs-App geleitet, um das Problem zu beheben. 

#### <a name="additional-push-notifications-for-end-users-on-the-company-portal-app-for-android-oreo---1475932--"></a>Zusätzliche Pushbenachrichtigungen für Benutzer in der Unternehmensportal-App für Android Oreo <!--1475932-->

Benutzern werden zusätzliche Benachrichtigungen angezeigt, die ihnen mitteilen, wann die Unternehmensportal-App für Android Oreo Hintergrundaufgaben durchführt, z.B. Abrufen von Richtlinien aus dem Intune-Dienst. So sind Endbenutzer besser darüber informiert, wann die Unternehmensportal-App administrative Aufgaben auf ihren Geräten ausführt. Dies ist Teil der gesamten [Optimierung der Unternehmensportal-Benutzeroberfläche](https://blogs.technet.microsoft.com/intunesupport/2017/08/21/android-8-0-o-behaviour-changes-and-microsoft-intune) für die Unternehmensportal-App für Android Oreo. 

Es gibt weitere Optimierungen für neue Benutzeroberflächenelemente, die in Android Oreo aktiviert sind.  Benutzern werden zusätzliche Benachrichtigungen angezeigt, die angeben, wann das Unternehmensportal Hintergrundaufgaben durchführt, z.B. Abrufen von Richtlinien aus dem Intune-Dienst.  Dadurch wird die Transparenz für Benutzer erhöht, für den Fall, dass das Unternehmensportal administrative Aufgaben auf dem Gerät ausführt.

#### <a name="new-behaviors-for-the-company-portal-app-for-android-with-work-profiles----1485783---"></a>Neue Verhalten für die Unternehmensportal-App für Android mit Arbeitsprofilen<!-- 1485783 -->

Wenn Sie ein Android for Work-Gerät mit einem Arbeitsprofil registrieren, werden Verwaltungsaufgaben auf dem Gerät von der Unternehmensportal-App im Arbeitsprofil ausgeführt. 

Wenn Sie eine MAM-fähige App im persönlichen Profil verwenden, kann die Unternehmensportal-App für Android nicht mehr verwendet werden. Um die Benutzererfahrung bezüglich des Arbeitsprofils zu verbessern, blendet Intune die persönliche Unternehmensportal-App nach erfolgreicher Registrierung eines Arbeitsprofils automatisch aus.

Die Unternehmensportal-App für Android kann jederzeit im persönlichen Profil aktiviert werden, indem Sie zum [Unternehmensportal im Play Store](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal) navigieren und auf **Aktivieren** tippen.

#### <a name="company-portal-for-windows-81-and-windows-phone-81-moving-to-sustaining-mode---1428681--"></a>Aktivieren des Aufrechterhaltungsmodus für das Unternehmensportal für Windows 8.1 und Windows Phone 8.1 <!--1428681-->

Ab Oktober 2017 wird der Aufrechterhaltungsmodus für Unternehmensportal-Apps für Windows 8.1 und Windows Phone 8.1 aktiviert. Dies bedeutet, dass die Apps und vorhandenen Szenarien wie Registrierung und Konformität weiterhin für diese Plattformen unterstützt werden. Diese Apps werden weiterhin über vorhandene Veröffentlichungskanäle wie dem Microsoft Store zum Download zur Verfügung gestellt. 

Sobald sich diese Apps im Aufrechterhaltungsmodus befinden, werden nur kritische Sicherheitsupdates empfangen. Es werden keine weiteren Updates oder Funktionen für diese Apps veröffentlicht. Um von neuen Funktionen profitieren zu können, wird empfohlen, Geräte auf Windows 10 und Windows 10 Mobile zu aktualisieren. 


### <a name="device-enrollment"></a>Geräteregistrierung

#### <a name="block-unsupported-samsung-knox-device-enrollment-----1490695---"></a>Blockieren der nicht unterstützten Samsung KNOX-Geräteregistrierung <!-- 1490695 -->

Die Unternehmensportal-App versucht, ausschließlich unterstützte Samsung KNOX-Geräte zu registrieren. Die Geräteregistrierung wird nur ausgeführt, wenn das Gerät in der [Liste der von Samsung veröffentlichten Geräte](https://www.samsungknox.com/knox-supported-devices/knox-workspace) erscheint, um Aktivierungsfehler von KNOX zu vermeiden, die die MDM-Registrierung verhindern. Samsung-Geräte können über Modellnummern verfügen, die KNOX unterstützen, während andere dies nicht tun. Überprüfen Sie vor dem Kauf und der Bereitstellung daher mithilfe des Wiederverkäufers Ihrer Geräte, ob diese mit KNOX kompatibel sind. Die vollständige Liste verifizierter Geräte finden Sie in den [Einstellungen für Android- und Samsung KNOX Standard-Richtlinien](/intune/supported-devices-browsers.md#intune-supported-devices).

#### <a name="end-of-support-for-android-43-and-lower----1171126-1326920---"></a>Ablauf des Supports für Android 4.3 und niedriger <!-- 1171126, 1326920 -->
Verwaltete Apps und die Unternehmensportal-App für Android benötigen Android 4.4 oder höher, um auf Unternehmensressourcen zugreifen zu können. Ab Dezember werden alle registrierten Geräte deaktiviert und können dann nicht mehr auf Unternehmensressourcen zugreifen. Bei Verwendung von App-Schutzrichtlinien ohne mobile Geräteverwaltung erhalten Apps keine Updates mehr, und die Qualität ihrer Benutzung wird mit der Zeit abnehmen.

#### <a name="inform-end-users-what-device-information-can-be-seen-on-enrolled-devices---1165314--"></a>Informieren von Endbenutzern, welche Geräteinformation auf registrierten Geräten angezeigt werden kann <!--1165314-->
Wir fügen dem Bildschirm „Gerätedetails“ den **Besitzertyp** auf allen Unternehmensportal-Apps hinzu. So können Benutzer direkt im Artikel [Welche Informationen erhält mein Unternehmen, wenn ich mein Gerät registriere?](/intune-user-help/what-info-can-your-company-see-when-you-enroll-your-device-in-intune) mehr über die Privatsphäre herausfinden. Dies wird in allen Unternehmensportal-Apps in Zukunft eingeführt. Für iOS haben wir dies im [September](https://docs.microsoft.com/intune/whats-new#week-of-september-11-2017) angekündigt.


## <a name="week-of-september-25-2017"></a>Die Woche vom 25. September 2017

### <a name="device-enrollment"></a>Geräteregistrierung

#### <a name="intune-supports-ios-11---1428975--"></a>Intune unterstützt iOS 11 <!--1428975-->
Intune unterstützt iOS 11. Dies wurde zuvor auf dem [Blog zum Intune-Support](https://blogs.technet.microsoft.com/intunesupport/2017/09/12/support-tip-intune-support-for-ios-11/) angekündigt.

#### <a name="end-of-support-for-ios-80----1164477---"></a>Ablauf des Supports für iOS 8.0 <!-- 1164477 -->
Verwaltete Apps und die Unternehmensportal-App für iOS benötigen iOS 9.0 und höher, um auf Unternehmensressourcen zugreifen zu können. Geräte, die nicht bis September aktualisiert werden, können nicht mehr auf das Unternehmensportal oder diese Apps zugreifen. 

### <a name="intune-apps"></a>Intune-Apps

#### <a name="refresh-action-added-to-the-company-portal-app-for-windows-10---1132468--"></a>Hinzufügen der Aktualisierungsaktion zur Unternehmensportal-App für Windows 10 <!--1132468-->
In der Unternehmensportal-App für Windows 10 können Benutzer die Daten nun aktualisieren, indem Sie sie aktualisieren (ziehen) oder indem Sie auf dem Desktop auf F5 drücken.



## <a name="notices"></a>Benachrichtigungen

### <a name="plan-for-change-easy-assist-end-of-life----1556480---"></a>Planen der Änderung: Easy Assist End of Life<!-- 1556480 -->
Intune verwendet Microsoft Easy Assist, für die Remoteunterstützung für PC-Verwaltung. Eine Sache, die Sie möglicherweise nicht bekannt ist, dass Microsoft Easy Assist ist eine Komponente von Office Live Meeting, einen Dienst, der 31 Dezember 2017 als veraltet eingestuft ist. Aus diesem Grund wird Intune Easy Assist Angebot auch Ende ihrer Lebensdauer auf 31 Dezember 2017 erreichen.

### <a name="manage-android-for-work-devices-independently-from-android-devices----1490731-eeready--"></a>Verwalten von Android for Work-Geräten unabhängig von Android-Geräten <!-- 1490731 EEready-->    
**Hinweis**: Die folgenden Änderungen werden mit dem Update vom November eingeführt. Allerdings kann es einige Zeit dauern, bis sie auch für Ihr Konto erfolgen. Sie erhalten im Office 365-Portal eine Bestätigungsnachricht, wenn diese Änderungen auf Ihrem Konto vorgenommen worden sind. Nach dem Rollout werden Ihnen zusätzliche Verwaltungsfunktionen geboten. Während des Rollouts kommt es zu keinen Änderungen an der Benutzeroberfläche.

Intune unterstützt das Verwalten von Registrierungen von Android for Work-Geräten unabhängig von der Android-Plattform. Diese Einstellungen werden unter **Geräteregistrierung** > **Registrierungsbeschränkungen** > **Gerätetypbeschränkungen** verwaltet. (Zuvor waren sie unter **Geräteregistrierung** > **Android for Work-Registrierung** > **Android for Work-Registrierungseinstellungen** zu finden.)

Standardmäßig ändern sich die Android for Work-Geräteeinstellungen gegenüber Ihren Android-Geräteeinstellungen nicht. Dies ändert sich allerdings, nachdem Sie ihre Android for Work-Einstellungen geändert haben.

Wenn Sie die private Android for Work-Registrierung blockieren, können sich nur unternehmenseigene Android-Geräte als Android for Work-Geräte registrieren.

Ziehen Sie folgendes in Betracht, wenn Sie mit den neuen Einstellungen arbeiten:

#### <a name="if-you-have-never-previously-onboarded-android-for-work-enrollment"></a>Wenn Sie die Android for Work-Registrierung zuvor noch nie integriert haben

Die neue Android for Work Plattform wird in den Standardgerätetypbeschränkungen blockiert. Nachdem Sie die Funktion integriert haben, können Sie zulassen, dass sich Geräte mit Android for Work registrieren. Ändern Sie dafür die Standardeinstellungen, oder erstellen Sie eine neue Gerätetypbeschränkung, um die Standardgerätetypbeschränkungen zu ersetzen.

#### <a name="if-you-have-onboarded-android-for-work-enrollment"></a>Wenn Sie die Android for Work-Registrierung bereits integriert haben

Wenn Sie zuvor bereits eine Integration vorgenommen haben, hängt Ihre Situation von den von Ihnen ausgewählten Einstellungen ab:

| Einstellung | Android for Work-Status in den Standardgerätetypbeschränkungen | Hinweise |
| --- | --- | --- |
| **Alle Geräte als Android-Geräte verwalten** | Gesperrt | Alle Android-Geräte müssen sich ohne Android for Work registrieren. |
| **Unterstützte Geräte als Android for Work-Geräte verwalten** | Zugelassen | Alle Android-Geräte, die Android for Work unterstützen, müssen sich mit Android for Work registrieren. |
| **Nur unterstützte Geräte für Benutzer in diesen Gruppen als Android for Work-Geräte verwalten** | Gesperrt | Eine separate Richtlinie für Gerätetypbeschränkungen wurde erstellt, um die Standareinstellungen außer Kraft zu setzen. Diese Richtlinie definiert die Gruppen, für die Sie zuvor die Android for Work-Registrierung zugelassen haben. Benutzer der ausgewählten Gruppen dürfen ihre Android for Work-Geräte weiterhin registrieren. Alle anderen Benutzer können sich nicht mit Android for Work registrieren. |

In beiden Fällen wird die von Ihnen vorgesehene Regulierung beibehalten. Von Ihrer Seite ist kein weiterer Vorgang erforderlich, um die globalen oder gruppenbedingten Zulassungen von Android for Work in Ihrer Umgebung zu verwalten.

### <a name="deprecating-support-for-os-x-mavericks-1010-and-previous-versions-of-macos---1489263-plan-for-change-for-1802--"></a>Auslaufende Unterstützung für OS X Mavericks 10.10 und frühere Versionen von macOS <!--1489263, plan for change for 1802-->
Wir kündigen an, dass die Registrierung für Geräte mit OS X Yosemite 10.10 und früheren Versionen von macOS ab Februar 2018 als veraltet gilt. Intune bietet vollständige Unterstützung für OS X El Capitan 10.11 und höher.

### <a name="new-path-for-managed-devices-in-graph-api----1586728---"></a>Neuer Pfad für verwaltete Geräte in der Graph-API <!-- 1586728 -->
Der Pfad, der verwendet wird, um auf verwaltete Geräte in der Betaversion der Graph-API zuzugreifen, wird geändert. 

| | |
|--|--|
| Aktueller Pfad |  https://graph.microsoft.com/beta/managedDevices |
| Neuer Pfad | https://graph.microsoft.com/beta/deviceManagement/managedDevices |

Beide Pfade funktionieren während des gesamten Oktobers. Nach der Dienstversion von Oktober funktioniert nur noch der neue Pfad.  Wenn Sie die Graph-API verwenden, um auf verwaltete Geräte zuzugreifen, aktualisieren und überprüfen Sie Ihre Skripts und Anwendungen mit dem neuen Pfad. Überprüfen Sie das monatliche [Änderungsprotokoll für die Graph-API](https://developer.microsoft.com/graph/docs/concepts/changelog) für zusätzliche Änderungen.


### <a name="direct-access-to-apple-enrollment-scenarios---951869--"></a>Direkter Zugriff auf Apple-Registrierungsszenarien <!--951869-->
Für Intune-Konten, die nach Januar 2017 erstellt wurden, hat Intune direkten Zugriff auf Apple-Registrierungsszenarien mithilfe der Workload „Geräte registrieren“ im Azure-Portal aktiviert. Bisher konnte nur über Links im klassischen Intune-Portal auf die Apple-Registrierungsvorschau zugegriffen werden. Vor Januar 2017 erstellte Intune-Konten erfordern eine einmalige Migration, bevor diese Features in Azure verfügbar sind. Der Zeitplan für die Migration wurde noch nicht angekündigt, aber Sie erfahren so bald wie möglich Näheres. Wir empfehlen Ihnen dringend, ein Testkonto zu erstellen, um die neue Oberfläche zu testen, wenn Sie mit Ihrem vorhandenen Konto nicht auf das Azure-Portal zugreifen können.

### <a name="administration-roles-being-replaced-in-azure-portal"></a>Administratorrollen werden im Azure-Portal ersetzt
Die in der Verwaltung mobiler Anwendungen (Mobile Application Management, MAM) vorhandenen Administratorrollen (Mitwirkender, Besitzer und Schreibgeschützt), die im klassischen Intune-Portal (Silverlight) verwendet werden, werden im Intune-Azure-Portal durch einen vollständigen Satz neuer rollenbasierter Zugriffssteuerung (Role-Based Access Control, RBAC) ersetzt. Nach der Migration zum Azure-Portal müssen Sie Ihre Administratoren diesen neuen Administratorrollen neu zuweisen. Weitere Informationen zu RBAC und den neuen Rollen finden Sie unter [Rollenbasierte Zugriffssteuerung für Microsoft Intune](/intune/role-based-access-control).



## <a name="whats-coming"></a>Was steht an?

### <a name="conditional-access-policies-for-intune-will-only-be-available-from-the-azure-portal-----1737088---"></a>Richtlinien für den bedingten Zugriff für Intune sind nur über das Azure-Portal verfügbar <!-- 1737088 -->
Der Prozess zum Konfigurieren und Verwalten des bedingten Zugriffs wurde vereinfacht. Aktuell können Sie den bedingten Zugriff über das Blatt „Intune-App-Schutz (MAM)“ sowie über Azure AD im [Windows Azure-Portal](https://manage.windowsazure.com) konfigurieren. Ab Januar können Sie Ihre Richtlinien nur noch über das [Azure-Portal](https://portal.azure.com) unter **Azure Active Directory** > **Bedingter Zugriff** konfigurieren und verwalten. Der Einfachheit halber können Sie dieses Blatt auch über **Intune** > **Bedingter Zugriff** im Azure-Portal aufrufen.

### <a name="manage-jamf-enrolled-macos-devices-with-intunes-device-compliance-engine---1592747--"></a>Verwalten von über Jamf registrierten macOS-Geräten mit dem Gerätekonformitätsmodul von Intune <!--1592747-->
Ab Frühjahr 2018 sendet Jamf Informationen über den macOS-Gerätezustand an Intune. Dort werden sie auf Konformität mit den Richtlinien ausgewertet, die in der Intune-Konsole definiert sind. Basierend auf dem Konformitätszustand des Geräts und anderen Bedingungen (z.B. Standort, Benutzerrisiko usw.) wird die Konformität für macOS-Geräte, die auf mit Azure AD verbundene Cloud- und lokale Anwendungen zugreifen (einschließlich Office 365) mithilfe des bedingten Zugriffs erzwungen.

### <a name="changes-in-support-for-the-intune-ios-company-portal-app-----1164474----"></a>Änderungen bei der Unterstützung der Intune-iOS-Unternehmensportal-App <!-- 1164474  -->
In den kommenden Monaten erscheint eine neue Version für die Microsoft Intune-Unternehmensportal-App für iOS, die nur Geräte mit mindestens iOS 9.0 unterstützt. Die Version des Unternehmensportals, die iOS 8 unterstützt, wird für einen sehr kurzen Zeitraum weiterhin verfügbar sein. Beachten Sie jedoch, dass wenn Sie auch die MAM-fähigen iOS-Apps verwenden, für die wir iOS 9.0 und höher unterstützen, sicherstellen müssen, dass Ihre Benutzer ein Update auf das neueste Betriebssystem durchführen. 

#### <a name="how-does-this-affect-me"></a>Inwiefern betrifft das mich?
Wir geben Ihnen früh genug Bescheid, damit Sie genügend Zeit für die Planung haben, auch wenn wir noch kein bestimmtes Datum angeben können. Vergewissern Sie sich, dass Ihre Benutzer auf iOS 9 und höher aktualisiert haben, und Sie bei der Veröffentlichung der Unternehmensportal-App von Ihren Benutzern fordern, dass diese ihre Unternehmensportal-App aktualisieren.

#### <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>Wie sollte ich mich für die Änderung vorbereiten?
Ermutigen Sie Ihre Benutzer, ein Update auf iOS 9.0 oder höher durchzuführen, damit sie in den vollen Genuss der neuen Intune-Features kommen.  Fordern Sie Benutzer auf, die neue Version des Unternehmensportals zu installieren und die neuen darin angebotenen Funktionen zu benutzen.

Wechseln Sie zu Intune im Azure-Portal, und sehen Sie sich „Geräte > Alle Geräte“ an. Filtern Sie nach der iOS-Version, um alle aktuellen Geräte mit einem Betriebssystem vor iOS 9 anzuzeigen.


### <a name="apple-to-require-updates-for-application-transport-security---748318--"></a>Apple erfordert Updates für die Transportsicherheit für Anwendungen <!--748318-->
Apple hat angekündigt, dass bestimmte Anforderungen für die Transportsicherheit für Anwendungen (Application Transport Security, ATS) erzwungen werden. ATS wird verwendet, um eine strengere Sicherheit in allen App-Kommunikationen über HTTPS zu erzwingen. Diese Änderung wirkt sich auf Intune-Kunden aus, die die iOS-Unternehmensportal-App verwenden.

Wir haben im Apple TestFlight-Programm eine Version der Unternehmensportal-App für iOS zur Verfügung gestellt, die die neuen ATS-Anforderungen erzwingt. Wenn Sie sie ausprobieren möchten, um Ihre ATS-Konformität zu testen, senden Sie eine E-Mail mit Angaben zu Vorname, Nachname, E-Mail-Adresse und Firmenname an <a href="mailto:CompanyPortalBeta@microsoft.com?subject=Register to TestFlight ATS Company Portal app">CompanyPortalBeta@microsoft.com</a>. Unter [Intune support blog (Intune-Supportblog)](https://aka.ms/compportalats) finden Sie weitere Informationen.

## <a name="see-also"></a>Weitere Informationen:
* [Microsoft Intune-Blog](http://go.microsoft.com/fwlink/?LinkID=273882)
* [Roadmap für die Cloudplattform](https://www.microsoft.com/server-cloud/roadmap/Indevelopment.aspx?TabIndex=0&dropValue=Intune)
* [What‘s new in the Intune App UI (Neues auf der Intune-App-Benutzeroberfläche)](whats-new-app-ui.md)
* [Neuerungen in den vorherigen Monaten](whats-new-archive.md)
