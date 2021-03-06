---
title: "Einstellungen für App-Schutzrichtlinien für iOS"
titlesuffix: Azure portal
description: "In diesem Thema werden die Einstellungen für App-Schutzrichtlinien für iOS-Geräte beschrieben.\""
keywords: 
author: erikre
ms.author: erikre
manager: angrobe
ms.date: 12/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 0f8b08f2-504c-4b38-bea2-b8a4ef0526b8
ms.reviewer: andcerat
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: a5a2a3b23ade3ab0c29f70b2c76a7d0f23430bf0
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2018
---
#  <a name="ios-app-protection-policy-settings"></a>Einstellungen für App-Schutzrichtlinien für iOS
[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Die in diesem Thema beschriebenen Richtlinieneinstellungen können im Azure-Portal auf dem Blatt **Einstellungen** für eine Schutzrichtlinie [konfiguriert](app-protection-policies.md) werden.

Es gibt zwei Kategorien von Richtlinieneinstellungen: Datenverlagerungs- und Zugriffseinstellungen. In diesem Thema bezieht sich der Begriff ***richtlinienverwaltete Apps*** auf Apps, die mit App-Schutzrichtlinien konfiguriert sind.

##  <a name="data-relocation-settings"></a>Einstellungen für die Datenverlagerung

| Einstellung | Verwendung | Standardwert |
|------|------|------|
| **iTunes- und iCloud-Sicherungen verhindern** | Wählen Sie **Ja**, um zu verhindern, dass diese App Geschäfts-, Schul- oder Unidaten in iTunes und iCloud sichert. Wählen Sie **Nein**, um dieser App zu erlauben, Geschäfts-, Schul- oder Unidaten in iTunes und iCloud zu sichern.| Ja  |
| **App Übertragung von Daten an andere Apps erlauben** | Geben Sie an, welche Apps Daten von dieser App empfangen können: <ul><li> **Richtlinienverwaltete Apps**: Datenübertragung nur an andere richtlinienverwaltete Apps zulassen</li> <li>**Alle Apps**: Datenübertragung an beliebige Apps zulassen </li> <li>**Keine**: Keine Datenübertragung an beliebige Apps zulassen, auch nicht an andere richtlinienverwaltete Apps.</li></ul> Wenn Sie diese Option auf **Richtlinienverwaltete Apps** oder **Keine** festlegen, wird zudem das iOS 9-Feature blockiert, das der Spotlight-Suche die Suche von Daten in Apps erlaubt. <br><br> Es gibt einige ausgenommene Apps und Dienste, für die Intune möglicherweise die Datenübertragung zulässt. Unter [Datenübertragungsausnahmen](#data-transfer-exemptions) finden Sie eine vollständige Liste der Apps und Dienste. | Alle Apps |
| **App Empfang von Daten aus anderen Apps erlauben** | Geben Sie an, welche Apps Daten an diese App übertragen können: <ul><li>**Richtlinienverwaltete Apps**: Datenübertragung nur von anderen richtlinienverwalteten Apps zulassen</li><li>**Alle Apps**: Datenübertragung von beliebigen Apps zulassen</li><li>**Keine**: Keine Datenübertragung von beliebigen Apps zulassen, auch nicht von anderen richtlinienverwalteten Apps</li></ul> Es gibt einige ausgenommene Apps und Dienste, von denen Intune möglicherweise die Datenübertragung zulässt. Unter [Datenübertragungsausnahmen](#data-transfer-exemptions) finden Sie eine vollständige Liste der Apps und Dienste. MAM-fähige Anwendungen für mehrere Identitäten auf nicht registrierten iOS-Geräten ignorieren diese Richtlinie und lassen sämtliche eingehende Daten zu. | Alle Apps |
| **„Speichern unter“ verhindern** | Wählen Sie **Ja** aus, um die Verwendung der Option „Speichern unter“ in dieser App zu deaktivieren. Wählen Sie **Nein** aus, wenn die Verwendung von „Speichern unter“ zulässig sein soll. | Nein |
| **Beschränken von Ausschneiden, Kopieren und Einfügen mit anderen Apps** | Geben Sie an, wann Ausschneide-, Kopier- und Einfügeaktionen in dieser App erlaubt sind. Es stehen die folgenden Optionen zur Auswahl: <ul><li>**Blockiert**: Ausschneide-, Kopier- und Einfügeaktionen zwischen dieser App und anderen Apps nicht zulassen.</li><li>**Richtlinienverwaltete Apps**: Nur Ausschneide-, Kopier- und Einfügeaktionen zwischen dieser App und anderen richtlinienverwalteten Apps zulassen.</li><li>**Richtlinienverwaltete Apps mit Einfügen**: Ausschneiden oder Kopieren zwischen dieser App und anderen richtlinienverwalteten Apps zulassen. Einfügen von Daten aus beliebigen Apps in diese App zulassen.</li><li>**Jede App**: Keine Einschränkungen für das Ausschneiden, Kopieren und Einfügen in und aus dieser App. | Jede App |
|**Anzeige von Webinhalten auf den Managed Browser beschränken** | Wählen Sie **Ja**, um zu erzwingen, dass Weblinks in der App in der Managed Browser-App geöffnet werden. <br><br> Auf Geräten, die nicht bei Intune registriert sind, können Weblinks in richtlinienverwalteten Apps nur in der Managed Browser-App geöffnet werden. <br><br> Wenn Sie Intune zum Verwalten Ihrer Geräte verwenden, lesen Sie [Verwalten des Internetzugriffs mittels Richtlinien für Managed Browser mit Microsoft Intune](app-configuration-managed-browser.md). | Nein |
| **App-Daten verschlüsseln** | Für richtlinienverwaltete Apps werden Daten im Ruhezustand mithilfe des von iOS bereitgestellten Verschlüsselungsschemas auf Geräteebene verschlüsselt. Wenn eine PIN erforderlich ist, werden die Daten gemäß den Einstellungen in der App-Schutzrichtlinie verschlüsselt. <br><br> Wechseln Sie [hier](https://support.apple.com/HT202739) zur offiziellen Apple-Dokumentation, um zu prüfen, welche iOS-Verschlüsselungsmodule FIPS 140-2-zertifiziert sind bzw. bei welchen die FIPS 140-2-Zertifizierung aussteht. <br><br> Geben Sie an, wann Geschäfts-, Schul- oder Unidaten in dieser App verschlüsselt werden. Es stehen die folgenden Optionen zur Auswahl: <ul><li>**Wenn das Gerät gesperrt ist**: Alle App-Daten, die dieser Richtlinie unterliegen, werden verschlüsselt, solange das Gerät gesperrt ist.</li><li>**Wenn das Gerät gesperrt ist und Dateien geöffnet sind**: Alle App-Daten, die dieser Richtlinie unterliegen, werden verschlüsselt, solange das Gerät gesperrt ist, außer den Daten in Dateien, die derzeit in der App geöffnet sind.</li><li>**Nach Geräteneustart**: Alle App-Daten unter dieser Richtlinie werden verschlüsselt, wenn das Gerät neu gestartet wird, bis das Gerät zum ersten Mal entsperrt wird.</li><li>**Geräteeinstellungen verwenden**: App-Daten werden basierend auf den Standardeinstellungen des Geräts verschlüsselt. </li></ul> Wenn Sie diese Einstellung aktivieren, muss der Benutzer eine PIN einrichten und verwenden, um auf sein Gerät zuzugreifen.  Wenn keine PIN eingerichtet wurde, werden die Apps nicht geöffnet, und der Benutzer wird mit der Meldung „Ihre Organisation hat festgelegt, dass Sie zunächst eine Geräte-PIN aktivieren müssen, um auf diese App zuzugreifen“ aufgefordert, eine PIN einzurichten.  | Wenn das Gerät gesperrt ist |
| **Kontaktsynchronisierung deaktivieren** | Wählen Sie **Ja**, um zu verhindern, dass die App Daten in der nativen App „Kontakte“ auf dem Gerät speichert. Wenn Sie **Nein** wählen, darf die App Daten in der nativen App „Kontakte“ auf dem Gerät speichern. <br><br>Bei Ausführung eines selektiven Zurücksetzens zum Entfernen von Geschäfts-, Schul- oder Unidaten aus der App werden Kontakte entfernt, die direkt aus der App in die native App „Kontakte“ synchronisiert wurden. Kontakte, die aus dem nativen Adressbuch mit einer anderen externen Quelle synchronisiert werden, können nicht zurückgesetzt werden. Dies gilt derzeit nur für die Microsoft Outlook-App. | Nein |
| **Drucken deaktivieren** | Wählen Sie **Ja**, um zu verhindern, dass die App Geschäfts-, Schul- oder Unidaten druckt. | Nein |
| **Speicherdienste zum Speichern von Unternehmensdaten auswählen** | Benutzer können Speichervorgänge in den ausgewählten Diensten (OneDrive for Business, SharePoint und lokaler Speicher) durchführen. Alle anderen Dienste werden blockiert. | 0 ausgewählt |

> [!NOTE]
> Keine der Einstellungen für die Datenverlagerung steuert die von Apple verwaltete Funktion „Öffnen in“ auf iOS-Geräten. Informationen zum Verwalten der Apple-Funktion „Öffnen in“ finden Sie unter [Verwalten der Datenübertragung zwischen iOS-Apps mit Microsoft Intune](data-transfer-between-apps-manage-ios.md).

## <a name="data-transfer-exemptions"></a>Datenübertragungsausnahmen

Die App-Schutzrichtlinie von Intune erlaubt unter bestimmten Umständen die Datenübertragung zu und von einigen ausgenommenen Apps und Plattformdiensten. Diese Liste unterliegt Änderungen und gibt die Dienste und Apps wieder, die als nützlich für die sichere Produktivität gelten.

| Name der App/des Diensts | Beschreibung |
| ---- | --- |
|Tel; telprompt | Native Phone-App |
| Skype | Skype |
| App-Einstellungen | Geräteeinstellungen |
| itms; itmss; itms-Apps; itms-appss; itms-Dienste | App Store |
| calshow | Nativer Kalender |




## <a name="access-settings"></a>Zugriffseinstellungen

| Einstellung | Verwendung | Standardwert |
|------|------|------|
| **PIN für Zugriff anfordern** | Wählen Sie **Ja**, um zum Verwenden dieser App eine PIN anzufordern. Benutzer werden beim ersten Ausführen der App in einem Geschäfts-, Schul- oder Unikontext aufgefordert, diese PIN einzurichten. Die PIN wird entweder beim Online- oder beim Offlinearbeiten angewendet. Standardwert = **Ja**<br><br> Konfigurieren Sie die folgenden Einstellungen für die PIN: <ul><li>**Typ auswählen**: Legen Sie eine Anforderung für numerische PINs oder Kennungen fest, bevor Sie auf eine App zugreifen, für die App-Schutzrichtlinien angewendet werden. Numerische PINs enthalten nur Zahlen, während eine Kennung mit mindestens 1 Buchstaben oder Sonderzeichen definiert werden kann. Standardwert = **Numerisch**.</li><li>**Anzahl der Versuche vor dem Zurücksetzen der PIN**: Geben Sie die Anzahl der Versuche an, die der Benutzer zum erfolgreichen Eingeben seiner PIN hat, ehe diese zurückgesetzt werden muss. Standardwert = **5**.</li><li> **Einfache PIN zulassen:** Wählen Sie **Ja** aus, um Benutzern das Verwenden einfacher PIN-Sequenzen wie 1234, 1111, abcd oder aaaa zu erlauben. Wählen Sie **Nein**, um zu verhindern, dass einfache Sequenzen verwendet werden. Standardwert = **Ja** </li><li> **PIN-Länge:** Geben Sie die Mindestanzahl von Ziffern in einer PIN-Sequenz an. Standardwert = **4** </li><li> **Fingerabdruck anstelle von PIN zulassen (iOS 8.0 und höher):** Wählen Sie **Ja**, um Benutzern für den Zugriff auf die App das Verwenden einer [Touch ID](https://support.apple.com/HT201371) anstelle einer PIN zu erlauben. Standardwert = **Ja**</li></ul> Auf iOS-Geräten können Sie Benutzern erlauben, ihre Identität mithilfe einer [Touch ID](https://support.apple.com/HT201371) statt einer PIN nachzuweisen. Wenn der Benutzer versucht, diese App mit seinem Geschäfts-, Schul- oder Unikonto zu nutzen, wird er aufgefordert, seine Identität per Fingerabdruck und nicht durch Eingabe einer PIN zu bestätigen. Wenn diese Einstellung aktiviert ist, wird das Vorschaubild für den App-Schnellzugriff unscharf, wenn diese App mit einem Geschäfts-, Schul- oder Unikonto verwendet wird. </li></ul><!-- <br><br>You can require a PIN expiration for targeted iOS apps. You can configure the PIN requirement and expiration date in days through the Azure portal. When required, a user will be required to set and use a new PIN before getting access to an iOS app. Only iOS apps that have app protection enabled with the Intune App SDK will support this feature.-->| PIN für Zugriff anfordern: Ja <br><br> Typ auswählen: Numerisch <br><br> Versuche zum Zurücksetzen der PIN: 5 <br><br> Einfache PIN zulassen: Ja <br><br> PIN-Länge: 4 <br><br> Fingerabdruckentsperrung zulassen: Ja |
| **Unternehmensanmeldeinformationen für Zugriff erforderlich** | Wählen Sie **Ja**, um anzufordern, dass sich der Benutzer für den Zugriff auf die App mit seinem Geschäfts-, Schul- oder Unikonto anmeldet, anstatt eine PIN einzugeben. Wenn Sie diese Einstellung auf **Ja** festlegen, sind PIN oder Fingerabdruckidentifizierung damit hinfällig.  | Nein |
| **Ausführen verwalteter Apps auf Geräten mit Jailbreak oder Rootzugriff blockieren** |  Wählen Sie **Ja** aus, um die Ausführung dieser App auf per Jailbreak oder Rootzugriff manipulierten Geräten zu verhindern. Der Benutzer kann diese App weiterhin für private Zwecke verwenden, muss jedoch für den Zugriff auf Geschäfts-, Schul- oder Unidaten ein anderes Gerät verwenden. | Ja  |
| **Überprüfen der Zugriffsanforderungen nach (Minuten)** | Konfigurieren Sie die folgenden Einstellungen: <ul><li>**Timeout**: Dies ist die Anzahl der Minuten, bis die (zuvor in der Richtlinie definierten) Zugriffsanforderungen erneut überprüft worden sind. Beispielsweise ein Administrator aktiviert die PIN in der Richtlinie, und ein Benutzer öffnet eine MAP-App und muss eine PIN eingeben. Wenn Sie diese Einstellung verwenden, muss der Benutzer für weitere **30 Minuten** (Standardwert) keine PIN bei MAM-Apps eingeben.</li><li>**Offline-Toleranzperiode**: Dies ist die Anzahl der Minuten, in den MAM-Apps offline sind. Geben Sie die Zeit (in Minuten) an, bevor die Zugriffsanforderungen für die App erneut geprüft werden. Standardwert = **720** Minuten (12 Stunden). Nachdem dieser Zeitraum abgelaufen ist, erfordert die App Benutzerauthentifizierung für AAD, sodass die App weiterhin ausgeführt werden kann.</li></ul>| Timeout: 30 <br><br> Offline: 720 |
| **Offline-Intervall (in Tagen), bevor App-Daten zurückgesetzt werden** | Nach diesem Zeitraum (durch den Administrator definiert) im Offline-Modus, muss der Benutzer für die App eine Verbindung mit dem Netzwerk herstellen und sich erneut authentifizieren. Wenn sich Benutzer erfolgreich authentifiziert haben, können sie weiterhin auf ihre Daten zugreifen, und das Offline-Intervall wird zurückgesetzt.  Wenn sich der Benutzer nicht authentifizieren kann, führt die App eine selektive Zurücksetzung des Benutzerkontos und der -daten durch.  Weitere Informationen darüber, welche Daten mit dem selektiven Zurücksetzen entfernt werden, finden Sie unter [Zurücksetzen nur von Unternehmensdaten in einer in Intune verwalteten App](https://docs.microsoft.com/en-us/intune/apps-selective-wipe). | 90 Tage |
| **App-PIN deaktivieren, wenn die Geräte-PIN verwaltet wird** | Wählen Sie **Ja**, um die App-PIN zu deaktivieren, wenn eine Gerätesperre auf einem registrierten Gerät erkannt wird. <br><br> **Hinweis:** Die App muss Intune SDK Version 7.0.1 oder höher aufweisen. | Nein |
| **iOS-Mindestbetriebssystem anfordern** | Wählen Sie **Ja**, um zum Verwenden dieser App ein iOS-Mindestbetriebssystem anzufordern. Der Zugriff des Benutzers wird blockiert, wenn die iOS-Version auf dem Gerät diese Anforderung nicht erfüllt. Diese Richtlinie unterstützt nur ein einzelnes Dezimaltrennzeichen, z.B. iOS 10.3. <br><br> **Hinweis:** Die App muss Intune SDK Version 7.0.1 oder höher aufweisen. | Nein |
| **iOS-Mindestbetriebssystem anfordern (nur Warnung)** | Wählen Sie **Ja**, um zum Verwenden dieser App ein iOS-Mindestbetriebssystem anzufordern. Dem Benutzer wird eine Benachrichtigung angezeigt, wenn die iOS-Version auf dem Gerät diese Anforderung nicht erfüllt. Diese Benachrichtigung kann verworfen werden. Diese Richtlinie unterstützt nur ein einzelnes Dezimaltrennzeichen, z.B. iOS 10.3. <br><br> **Hinweis:** Die App muss Intune SDK Version 7.0.1 oder höher aufweisen. | Nein |
| **App-Mindestversion anfordern** | Wählen Sie **Ja** aus, um zum Verwenden der App eine App-Mindestversion anzufordern. Der Zugriff des Benutzers wird blockiert, wenn die App-Version auf dem Gerät die Anforderung nicht erfüllt.<br><br>Da Apps selbst häufig individuelle Versionsschemas aufweisen, erstellen Sie eine Richtlinie mit einer minimalen App-Version, die auf eine App abzielt (z.B. „Outlook-Versionsrichtlinie“). <br><br> **Hinweis:** Die App muss Intune SDK Version 7.0.1 oder höher aufweisen. | Nein | 
| **App-Mindestversion anfordern (nur Warnung)** | Wählen Sie **Ja** aus, um zum Verwenden dieser App eine App-Mindestversion zu empfehlen. Dem Benutzer wird eine Benachrichtigung angezeigt, wenn die App-Version auf dem Gerät die Anforderung nicht erfüllt. Diese Benachrichtigung kann verworfen werden.<br><br>Da Apps selbst häufig individuelle Versionsschemas aufweisen, erstellen Sie eine Richtlinie mit einer minimalen App-Version, die auf eine App abzielt (z.B. „Outlook-Versionsrichtlinie“). <br><br> **Hinweis:** Die App muss Intune SDK Version 7.0.1 oder höher aufweisen. | Nein | 
| **Mindestversion des Intune SDK für App-Schutzrichtlinien anfordern** | Wählen Sie **Ja** aus, um zum Verwenden dieser App eine Mindestversion des Intune SDK für App-Schutzrichtlinien anzufordern. Der Zugriff des Benutzers wird blockiert, wenn die Version des Intune SDK für App-Schutzrichtlinien auf dem Gerät die Anforderung nicht erfüllt. <br> <br> Weitere Informationen zum Intune SDK für App-Schutzrichtlinien finden Sie unter [Übersicht über das Intune App SDK](app-sdk.md). <br><br> **Hinweis:** Die App muss Intune SDK Version 7.0.1 oder höher aufweisen. | Nein |


##  <a name="add-ins-for-outlook-app"></a>Add-Ins für die Outlook-App

Outlook hat kürzlich Add-Ins für Outlook für iOS eingeführt, mit denen Sie beliebte Apps in den E-Mail-Client integrieren können. Add-Ins für Outlook sind im Internet, unter Windows und Mac und für Outlook für iOS verfügbar. Da Add-Ins über Microsoft Exchange verwaltet werden, können die Benutzer Daten und Nachrichten über Outlook und nicht verwaltete Add-In-Anwendungen freigeben, sofern diese Add-Ins von Exchange nicht für den Benutzer deaktiviert wurden.

Wenn Sie verhindern möchten, dass Endbenutzer auf Outlook-Add-Ins zugreifen und diese installieren (dies hat Auswirkungen auf alle Outlook-Clients), nehmen Sie im Exchange Admin Center die folgenden Änderungen an den Rollen vor:

- Um zu verhindern, dass Benutzer Office Store-Add-Ins installieren, entfernen Sie die Rolle My Marketplace.
- Um zu verhindern, dass Benutzer ein Sideloading von Add-Ins durchführen können, entfernen Sie die Rolle My Custom Apps.
- Um zu verhindern, dass Benutzer alle Add-Ins installieren, entfernen Sie beide Rollen – My Custom Apps und My Marketplace.

Diese Anweisungen gelten für Office 365, Exchange 2016, Exchange 2013 für Outlook im Web, unter Windows, auf Mac-PCs und mobil.

- Weitere Informationen finden Sie unter [Add-Ins für Outlook](https://technet.microsoft.com/library/jj943753(v=exchg.150).aspx).
- Weitere Informationen finden Sie unter [Angeben der Administratoren und Benutzer, die Add-Ins für die Outlook-App installieren und verwalten können](https://technet.microsoft.com/library/jj943754(v=exchg.150).aspx).
