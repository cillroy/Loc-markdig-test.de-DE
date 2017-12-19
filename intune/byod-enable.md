---
title: Aktivieren von BYOD mit Microsoft Intune
description: "Ein allgemeiner Workflow für die Einrichtung von Intune, um eine BYOD-Lösung (BYOD = Bring Your Own Device) für Ihre Organisation zu aktivieren."
keywords: 
author: lindavr
ms.author: lindavr
manager: angrobe
ms.date: 07/26/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 
ms.reviewer: vlpetros
ms.suite: ems
ms.openlocfilehash: f4e414f3696c64f8ea450394928aa055ad427afd
ms.sourcegitcommit: e10dfc9c123401fabaaf5b487d459826c1510eae
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/09/2017
---
# <a name="enable-byod-with-intune"></a>Aktivieren von BYOD mit Intune

Dieses Thema enthält einen allgemeinen Workflow für die Einrichtung von Intune, um eine BYOD-Lösung (BYOD = Bring Your Own Device) für Ihre Organisation zu aktivieren. Die Aufgabe wird in drei Prozessen organisiert und enthält unterstützende Links zu Themen zur Vorgehensweise.

Der Workflow wird in folgende drei Prozesse unterteilt. Sie können die Aspekte der einzelnen Prozesse zum Erfüllen der Anforderungen Ihrer Organisation anpassen.

-   Unter **[Registrieren von Geräten und Prüfen auf Konformität](#enroll-devices-and-check-for-compliance)** wird beschrieben, wie Benutzer ihre persönlichen Geräte für die Verwaltung in Intune registrieren können. Intune verwaltet iOS-, macOS-, Android- und Windows-Geräte. In diesem Abschnitt wird zudem beschrieben, wie Richtlinien für Geräte bereitgestellt werden und wie sichergestellt wird, dass sie grundlegende Sicherheitsanforderungen erfüllen.

- Unter **[Erteilen von Zugriff auf Unternehmensressourcen](#provide-access-to-company-resources)** wird gezeigt, wie Sie es Benutzern ermöglichen können, einfach und sicher auf Unternehmensressourcen zuzugreifen. Hierzu werden Zugriffsprofile für verwaltete Geräte bereitgestellt. In diesem Abschnitt wird zudem erläutert, wie Bereitstellungen von per Volumenlizenz erworbenen Apps in Intune verwaltet werden können.

-   Unter**[Schützen von Unternehmensdaten](#protect-company-data)** erfahren Sie, wie Sie bedingten Zugriff auf Unternehmensressourcen erteilen, Datenverlust verhindern und Unternehmens-Apps und -daten von Geräten entfernen, wenn sie nicht mehr für die Arbeit benötigt werden oder verloren bzw. gestohlen wurden.

[![Allgemeines Workflowdiagramm zur Aktivierung von BYOD mit Microsoft Intune](./media/workflow-diagram-for-byod.png)](./media/workflow-diagram-for-byod.png)

<!--- > <sup>You can download this infographic at https://gallery.technet.microsoft.com/Infographic-Management-3644ae41.</sup> --->

## <a name="before-you-begin"></a>Vorbereitung
Bevor Benutzer Geräte registrieren können, müssen Sie den Intune-Dienst selbst vorbereiten. Hierzu müssen Sie [Benutzern Lizenzen zuweisen](licenses-assign.md) und die [Autorität für die Verwaltung mobiler Geräte festlegen](mdm-authority-set.md).

Zudem sollten Sie das [Unternehmensportal anpassen](company-portal-customize.md). Fügen Sie ein Unternehmensbranding hinzu, und stellen Sie Supportinformationen für Benutzer bereit. Dadurch wird eine vertrauenswürdige Benutzererfahrung der Registrierung und der Unterstützung für Ihre Benutzer erzeugt. Sie können auch [Nutzungsbedingungen](terms-and-conditions-create.md) erstellen, die Benutzer vor der Registrierung akzeptieren müssen. Alternativ auch [Geräteeinschränkungen](enrollment-restrictions-set.md), um anzugeben, welche Plattformen Sie unterstützen.

## <a name="enroll-devices-and-check-for-compliance"></a>Registrieren von Geräten und Prüfen auf Konformität

Nachdem Sie den Intune-Dienst vorbereitet haben, müssen Sie für die verschiedenen Gerätetypen, die Sie verwalten möchten, verschiedene Registrierungsanforderungen erfüllen. Der Prozess zum Registrieren von Geräten bei der Verwaltung ist einfach, unterscheidet sich jedoch abhängig von dem Gerätetyp.

-   **iOS- und Mac-Geräte**: Sie müssen ein [Apple MDM-Push-Zertifikat abrufen](apple-mdm-push-certificate-get.md), um iPads, iPhones oder macOS-Geräte zu registrieren. Nachdem Sie Ihr MDM-Push-Zertifikat in Intune hochgeladen haben, können Benutzer mithilfe der Unternehmensportal-App [iOS-Geräte registrieren](/intune-user-help/enroll-your-device-in-intune-ios) und auf der Unternehmensportal-Website [macOS-Geräte registrieren](/intune-user-help/enroll-your-device-in-intune-macos).

-   **Android-Geräte** Sie müssen nichts tun, um den Intune-Dienst für die Registrierung von Android-Geräten vorzubereiten. Benutzer können einfach über die Unternehmensportal-App, die in Google Play zur Verfügung steht, [Ihre Geräte registrieren](/intune-user-help/enroll-your-device-in-intune-android).

-   **Windows Phones und PCs** Windows-Geräte können mit zusätzlichen Konfigurationen registriert werden. Sie können die automatische Registrierung für Windows 10-PCs und mobile Windows 10-Geräte in Azure Active Directory (AD) Premium aktivieren, um die Benutzererfahrung zu vereinfachen. Wenn Sie nicht über Azure AD Premium verfügen, oder Sie Windows 8.1 unterstützen müssen, können Sie einen [DNS-Alias für den Registrierungsserver](windows-enroll.md#simplify-windows-enrollment-without-azure-ad-premium) erstellen, um die Registrierung einfacher zu gestalten.


### <a name="make-sure-that-managed-devices-meet-basic-security-requirements"></a>Sicherstellen der Erfüllung grundlegender Sicherheitsanforderungen bei verwalteten Geräten

Nachdem Benutzer ihre Geräte für die Verwaltung registriert haben, muss die IT sicherstellen, dass die für den Zugriff auf Unternehmens-Apps und -daten verwendeten Geräte die grundlegenden Sicherheitsanforderungen erfüllen. Diese Regeln könnten die Verwendung einer PIN für den Zugriff auf Geräte und das Verschlüsseln von Daten, die auf Geräten gespeichert sind, einschließen. Eine Gruppe solcher Regeln wird als [Konformitätsrichtlinie](device-compliance.md) bezeichnet.

Wenn Sie für einen Benutzer [eine Konformitätsrichtlinie bereitstellen](device-compliance-get-started.md), werden alle seine von Intune verwalteten Geräte dahingehend überprüft, ob sie die grundlegenden Sicherheitsanforderungen erfüllen, die Sie im Rahmen Ihrer BYOD-Richtlinie definiert haben. Nachdem ein Gerät auf die Konformität der Richtlinien überprüft wurde, meldet es seinen Status an Intune zurück. In einigen Fällen werden Benutzer möglicherweise dazu aufgefordert, Einstellungen wie ihre PIN oder Geräteverschlüsselung zu korrigieren. In anderen Fällen benachrichtigt die Unternehmensportal-App den Benutzer einfach über alle Einstellungen, die Ihre Richtlinie nicht erfüllen.

## <a name="provide-access-to-company-resources"></a>Bereitstellen des Zugriffs auf Unternehmensressourcen

Die meisten Mitarbeiter möchten auf Ihrem Mobilgerät als Erstes Zugriff auf Unternehmens-E-Mails und -Daten erhalten. Sie erwarten, dass die Einrichtung ohne komplexe Schritte verläuft, und dass sie nicht beim Helpdesk anrufen müssen. Intune erleichtert Ihnen das [Erstellen und Bereitstellen von E-Mail-Einstellungen](email-settings-configure.md) für native E-Mail-Apps, die auf mobilen Geräten vorinstalliert sind.


> [!NOTE]
> Intune unterstützt die Konfiguration von Android for Work-E-Mail-Profilen für die Gmail- und Nine Work-E-Mail-Apps, die aus dem Google Play-Store bezogen werden können.

Intune hilft Ihnen auch dabei, den Zugriff auf lokale Unternehmensdaten zu steuern und zu schützen, wenn Benutzer extern arbeiten. Die [WLAN-](wi-fi-settings-configure.md), [VPN-](vpn-settings-configure.md) und E-Mail-Profile von Intune greifen ineinander, um den Zugriff auf die Dateien und Ressourcen zuzulassen, die Benutzer für ihre Arbeit benötigen, unabhängig davon, wo sie gespeichert sind. Die lokal gehosteten Webanwendungen und Services Ihres Unternehmens können mithilfe von Azure Active Directory-Anwendungsproxy und bedingtem Zugriff ebenfalls geschützt und auf sicheren Zugriff eingeschränkt werden.

### <a name="manage-volume-purchased-apps"></a>Verwalten von Apps aus einem Volumenprogramm
Mit Intune können Sie folgende Vorgänge ohne großen Aufwand durchführen:
* Importieren der Volumenlizenzinformationen aus beiden App Stores
* Nachverfolgen der Anzahl der verwendeten Lizenzen
* Verhindern, dass Ihre Benutzer mehr Kopien der App installieren, als Sie besitzen
* [Übermitteln von Store-Apps für verwaltete Geräte](apps-deploy.md)
* Anvisieren von Apps für nicht verwaltete Geräte über die Unternehmensportal-Website

Mit Intune können Sie Apps verwalten und bereitstellen, die Sie im Rahmen von Volumenprogrammen im iOS App Store und dem Microsoft Store für Unternehmen erworben haben. Dadurch können Sie den Verwaltungsaufwand reduzieren, den das Nachverfolgen von erworbenen Volumenlizenzen mit sich bringt.

> [!TIP]
> Sie können [Einmaliges Anmelden (Single Sign On, SSO) mit Azure AD Connect konfigurieren](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect). Mit SSO können sich Benutzer mit dem lokal verwendeten Domänenbenutzernamen und dem zugehörigen Kennwort bei Apps anzumelden. Ferner können Sie mit dem Azure Active Directory-Anwendungsproxy [internetbasierten Zugriff auf lokal gehostete Web-Apps bereitstellen](https://docs.microsoft.com/azure/active-directory/active-directory-application-proxy-get-started).

-   [Verwalten von Apps für iOS-Geräte, die über ein Volumenprogramm erworben wurden](vpp-apps-ios.md). Sie erwerben mehrere Lizenzen für iOS-Apps über das [Programm für Volumenlizenzen für Unternehmen (Volume Purchase Program, VPP) von Apple](http://www.apple.com/business/vpp/). Sie müssen über die Apple-Website ein Apple VPP-Konto einrichten und das Apple VPP-Token in Intune hochladen. Anschließend können Sie Ihre Informationen zum Volumenerwerb mit Intune synchronisieren und die Verwendung der im Rahmen des Volumenprogramms erworbenen App verfolgen.

-   [Verwalten von Apps, die im Microsoft Store für Unternehmen erworben wurden](windows-store-for-business.md). Im [Microsoft Store für Unternehmen](https://www.microsoft.com/business-store) können Sie Apps für Ihre Organisation suchen und einzeln oder im Rahmen eines Volumenprogramms erwerben. Durch die Verbindung des Stores mit Intune können Sie im Rahmen von Volumenprogrammen erworbene Apps über das Azure-Portal verwalten.

## <a name="protect-company-data"></a>Schützen von Unternehmensdaten

Intune schützt Unternehmensdaten auf vielen Technologieebenen. Auf der Ebene der Identität wird der Zugriff auf Dienste durch bedingten Zugriff geschützt. Der bedingte Zugriff erlaubt nur verwalteten und konformen Geräten den Zugriff auf Unternehmensressourcen. Auf Client-App-Ebene schützen App-Schutzrichtlinien vor Datenverlust. App-Schutzrichtlinien verhindern, dass Daten in nicht geschützte Apps oder Speicherorte verschoben werden. Mithilfe dieser Richtlinien können Sie bei Verlust oder Diebstahl eines Geräts auch die Unternehmensdaten zurücksetzen.

### <a name="enforce-conditional-access-to-company-resources"></a>Erzwingen des bedingten Zugriffs auf Unternehmensressourcen

Sie können Konformitätsrichtlinien mit [Richtlinien für bedingten Zugriff](device-compliance.md) kombinieren, um zu prüfen, ob Geräte die grundlegenden Sicherheitsanforderungen erfüllen, die für Ihre BYOD-Richtlinie erforderlich sind. Wenn ein Gerät die Anforderungen nicht erfüllt, werden so lange Regeln erzwungen und der Zugriff verweigert, bis das Gerät die Richtlinienanforderungen erfüllt. Dadurch wird sichergestellt, dass nur verwaltete und konforme Geräte auf Unternehmensdaten von Diensten wie Exchange ([Exchange lokal](exchange-connector-install.md) oder [Exchange Online](conditional-access-exchange-create.md)), SharePoint Online, Skype for Business Online und weiterhin zugreifen können.
<!---first link was (https://docs.microsoft.com/intune/deploy-use/restrict-access-to-email-and-o365-services-with-microsoft-intune)
third link was (https://docs.microsoft.com/intune/deploy-use/restrict-access-to-exchange-online-with-microsoft-intune). check with Andre--->

> [!IMPORTANT]
> Richtlinien für bedingten Zugriff werden nicht funktionieren, wenn keine Kompatibilitätsrichtlinie für die Überprüfung der Kompatibilität vorhanden ist.

### <a name="prevent-data-loss-of-company-data-with-app-protection-policies"></a>Vermeiden von Datenverlust bei Unternehmensdaten mithilfe von App-Schutzrichtlinien

Mit den App-Schutzrichtlinien von Intune können Sie auswählen, wie auf Ihre Daten zugegriffen werden soll – mit oder ohne Geräteregistrierung. Durch diese Vielseitigkeit können Sie Unternehmensdaten schützen, sodass Benutzer weiterhin sicher auf Unternehmensdaten zugreifen können, selbst wenn sie ihr Gerät nicht bei Intune registriert haben.

Sie können [Intune-Geräteschutzrichtlinien](app-protection-policies.md) verwenden, um Unternehmensdaten zu schützen, auf die über iOS- und Android-Geräte zugegriffen wird. Wenn Sie diese App-basierten Richtlinien verwenden, können Sie steuern, wie Unternehmensdaten von Mitarbeitern verwendet und geteilt werden, selbst wenn die zugreifenden Geräte nicht von Intune verwaltet werden

Mithilfe von [Windows Information Protection (WIP)](app-protection-policies-configure-windows-10.md) können Sie das Gleiche für verwaltete Windows 10-Geräte erreichen. Diese Richtlinien beeinträchtigen nicht die Benutzerfreundlichkeit für Mitarbeiter. Sie machen keine Änderungen an Ihrer Netzwerkumgebung oder anderen Apps erforderlich.

### <a name="remove-company-data-while-leaving-personal-data-intact"></a>Entfernen von Unternehmensdaten, ohne personenbezogene Daten zu beeinträchtigen

Wenn ein Gerät nicht mehr für die Arbeit benötigt wird, einem neuen Verwendungszweck dienen soll oder verloren gegangen ist, müssen Sie dazu in der Lage sein, Unternehmens-Apps und -daten davon zu entfernen. Dazu können Sie die Funktionen zum Entfernen von Unternehmensdaten und die Zurücksetzung auf Werkseinstellungen von Intune verwenden. Ihre Benutzer können über das Intune-Unternehmensportal auch ihre eigenen Geräte zurücksetzen, wenn diese Geräte in Intune registriert sind.

Die [Zurücksetzung auf Werkseinstellungen](devices-wipe.md) setzt ein Gerät auf die werkseitigen Standardeinstellungen zurück, entfernt alle Benutzerdaten sowie -einstellungen und entfernt das Gerät aus der Verwaltung durch Intune. [Unternehmensdaten entfernen](devices-wipe.md#remove-company-data) entfernt nur Unternehmensdaten von dem Gerät, die persönlichen Daten des Benutzers bleiben jedoch intakt.

Sobald der Vorgang initiiert wurde, beginnt das Gerät umgehend mit dem Zurücksetzen. Wenn der Prozess beendet ist, sind alle Unternehmensdaten gelöscht, und der Gerätename wird aus Intune entfernt. Dadurch wird der Geräteverwaltungs-Lebenszyklus beendet.
