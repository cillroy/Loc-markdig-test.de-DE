---
title: "Behandeln von Problemen mit Geräteprofilen in Microsoft Intune"
titlesuffix: Azure portal
description: "Wenn Sie nicht weiter kommen, verwenden Sie zur Behebung von Problemen mit Intune-Geräteprofilen die Informationen in diesem Thema."
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 11/09/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 4aaa25bb36b0125350e3ab8b25e7e8ba89626c3f
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2018
---
# <a name="troubleshooting-device-profiles-in-microsoft-intune"></a>Behandeln von Problemen mit Geräteprofilen in Microsoft Intune


[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Anhand der Informationen in diesem Thema können Sie bekannte Probleme im Zusammenhang mit Intune-Geräteprofilen behandeln.

## <a name="why-doesnt-a-user-get-a-new-profile-when-changing-a-password-or-passphrase-on-an-existing-wi-fi-profile"></a>Warum erhält ein Benutzer kein neues Profil, wenn er ein Kennwort oder eine Passphrase für ein vorhandenes WLAN-Profil ändert? 
Wenn Sie ein WLAN-Unternehmensprofil erstellen, das Profil für eine Gruppe bereitstellen, das Kennwort ändern und das Profil speichern, erwarten Sie vermutlich, dass Benutzer das neue Profil auch erhalten. Jedoch erhalten Benutzer das neue Profil möglicherweise nicht. 

Um dieses Problem zu entschärfen, achten Sie darauf, dass ein WLAN-Gastzugang eingerichtet ist, damit die Benutzer beim Ausfall des Unternehmens-WLANs auf das Gast-WLAN zurückgreifen können. Dazu muss die Einstellung zum automatischen Herstellen einer Verbindung aktiviert sein. Dieses WLAN-Gastprofil muss an alle Benutzer bereitgestellt worden sein.

Sie können sich außerdem nach einer Reihe von empfohlenen Methoden richten:
- Da das WLAN-Netzwerk, mit dem Sie die Verbindung herstellen, ein Kennwort oder eine Passphrase anfordert, vergewissern Sie sich, dass Sie eine direkte Verbindung mit dem Router herstellen können. Sie können das mit einem iOS-Gerät testen.
- Nachdem Sie erfolgreich eine Verbindung mit dem WLAN-Endpunkt (WLAN-Router) hergestellt haben, notieren Sie die verwendete SSID und die verwendete Anmeldeinformation (diese stellt das Kennwort oder die Passphrase dar.)
- Geben Sie die SSID und die Anmeldeinformation (Kennwort oder Passphrase) im Feld für den vorinstallierten Schlüssel ein. 
- Führen Sie die Bereitstellung an eine Testgruppe mit eingeschränkter Benutzeranzahl aus, vorzugsweise nur das IT-Team. 
- Synchronisieren Sie Ihr iOS-Gerät mit Intune. Registrieren Sie sich, wenn Sie noch nicht registriert sind. 
- Probieren Sie, erneut eine Verbindung mit dem gleichen WLAN-Endpunkt (wie im ersten Schritt erwähnt) herzustellen.
- Nehmen Sie das Rollout an größere Gruppen und zu gegebener Zeit an alle erwarteten Benutzer in Ihrer Organisation durch. 

## <a name="how-long-does-it-take-for-mobile-devices-to-get-a-policy-or-apps-after-they-have-been-assigned"></a>Wie lange dauert es, bis mobile Geräte Richtlinien oder Apps nach ihrer Zuweisung abrufen können?
Wenn eine Richtlinie oder App zugewiesen wird, beginnt Intune sofort mit dem Versuch, das Gerät zu benachrichtigen und zum Einchecken beim Intune-Dienst zu veranlassen. Dies dauert normalerweise weniger als fünf Minuten.

Wenn ein Gerät sich nach der ersten Benachrichtigung nicht zum Abrufen der Richtlinie eincheckt, unternimmt Intune drei weitere Versuche.  Wenn das Gerät offline ist (z. B. ausgeschaltet oder nicht mit einem Netzwerk verbunden), erhält es die Benachrichtigungen möglicherweise nicht. In diesem Fall erhält das Gerät die Richtlinie beim nächsten geplanten Einchecken beim Intune-Dienst wie folgt:

- iOS und macOS: alle sechs Stunden.
- Android: alle acht Stunden.
- Windows Phone: alle acht Stunden.
- Als Geräte registrierte PCs unter Windows 8.1 und Windows 10: alle acht Stunden.

Wenn das Gerät gerade registriert wurde, ist die Eincheckfrequenz höher:

- iOS und macOS: sechs Stunden lang alle 15 Minuten, danach alle sechs Stunden.
- Android: 15 Minuten lang alle drei Minuten, danach zwei Stunden lang alle 15 Minuten, anschließend alle acht Stunden.
- Windows Phone: 15 Minuten lang alle fünf Minuten, danach zwei Stunden lang alle 15 Minuten, anschließend alle acht Stunden.
- Als Geräte registrierte Windows-PCs: 30 Minuten lang alle drei Minuten, danach alle acht Stunden.

Benutzer können auch jederzeit die Unternehmensportal-App öffnen und das Gerät synchronisieren, um sofort auf Richtlinien zu prüfen.

## <a name="what-actions-cause-intune-to-immediately-send-a-notification-to-a-device"></a>Bei welchen Aktionen sendet Intune sofort eine Benachrichtigung an ein Gerät?
Geräte checken bei Intune entweder beim Erhalt einer Benachrichtigung ein, die sie dazu auffordert, oder während ihres regelmäßigen geplanten Eincheckvorgangs.  Wenn Sie für ein Gerät oder einen Benutzer ausdrücklich eine Aktion durchführen, z. B. Zurücksetzen, Sperren, Zurücksetzen der Kennung, App-Zuweisung, Profilzuweisung (WLAN, VPN, E-Mail usw.) oder Richtlinienzuweisung, beginnt Intune sofort mit dem Versuch, das Gerät zu benachrichtigen, dass es sich zum Erhalten dieser Updates beim Intune-Dienst einchecken soll.

Andere Änderungen, wie z. B. die Überarbeitung der Kontaktinformationen im Unternehmensportal, führen nicht zu einer sofortigen Benachrichtigung von Geräten.

## <a name="if-multiple-policies-are-assigned-to-the-same-user-or-device-how-do-i-know-which-settings-will-get-applied"></a>Wie finde ich heraus, welche Einstellungen angewendet werden, wenn für denselben Benutzer oder dasselbe Gerät mehrere Richtlinien zugewiesen werden?
Bei Zuweisung mehrerer Richtlinien für denselben Benutzer oder dasselbe Gerät erfolgt die Auswertung, welche Einstellung angewendet werden soll, auf der Ebene der einzelnen Einstellungen:

-   Kompatibilitätsrichtlinieneinstellungen haben immer Vorrang vor Konfigurationsrichtlinieneinstellungen.

-   Die restriktivste Kompatibilitätsrichtlinie wird angewendet, wenn sie anhand derselben Einstellung in einer anderen Kompatibilitätsrichtlinie ausgewertet wird.

-   Falls eine Konfigurationsrichtlinieneinstellung im Konflikt mit einer Einstellung in einer anderen Konfigurationsrichtlinie steht, wird dieser Konflikt im Azure-Portal angezeigt. Konflikte dieser Art müssen Sie manuell auflösen.

## <a name="what-happens-when-app-protection-policies-conflict-with-each-other-which-one-will-be-applied-to-the-app"></a>Was geschieht, wenn App-Schutzrichtlinien in Konflikt stehen? Welche wird auf die App angewendet?
Konfliktwerte sind die restriktivsten Einstellungen, die in einer App-Schutzrichtlinie zur Verfügung stehen, außer für die Zahleneingabefelder (z. B. PIN-Versuche vor dem Zurücksetzen).  Die Zahleneingabefelder werden auf dieselben Werte gesetzt, die auch verwendet werden, wenn Sie in der Konsole eine MAM-Richtlinie erstellen und die empfohlenen Einstellungen verwenden.

Konflikte treten auf, wenn zwei Profileinstellungen identisch sind.  Beispielsweise haben Sie zwei MAM-Richtlinien konfiguriert, die mit Ausnahme der Einstellung für Kopieren/Einfügen identisch sind.  In diesem Szenario wird die Einstellung für Kopieren und Einfügen auf den restriktivsten Wert festgelegt, die übrigen Einstellungen werden jedoch wie konfiguriert angewendet.

Wenn ein Profil der App zugewiesen ist und in Kraft tritt und anschließend ein zweites zugewiesen wird, erhält das erste Vorrang und bleibt wirksam, während das zweite als in Konflikt stehend angezeigt wird. Wenn beide Profile gleichzeitig angewendet werden, also kein vorheriges Profil vorhanden ist, stehen beide in Konflikt. Alle in Konflikt stehenden Einstellungen werden auf die restriktivsten Werte festgelegt.

## <a name="what-happens-when-ios-custom-policies-conflict"></a>Was geschieht, wenn Sie benutzerdefinierte iOS-Richtlinien in Konflikt stehen?
Intune bewertet nicht die Nutzlast von Apple-Konfigurationsdateien oder eines benutzerdefinierten OMA-URI-Profils (Open Mobile Alliance Uniform Resource Identifier). Es dient lediglich als Übermittlungsmechanismus.

Wenn Sie ein benutzerdefiniertes Profil zuweisen, stellen Sie sicher, dass die konfigurierten Einstellungen nicht mit Konformitäts-, Konfigurations- oder anderen benutzerdefinierten Richtlinien in Konflikt stehen. Bei einem benutzerdefinierten Profil mit Einstellungskonflikten werden die Einstellungen in zufälliger Reihenfolge angewendet.

## <a name="what-happens-when-a-profile-is-deleted-or-no-longer-applicable"></a>Was geschieht, wenn ein Profil gelöscht wird oder nicht mehr gilt?
Wenn Sie ein Profil löschen oder ein Gerät aus einer Gruppe entfernen, für die ein Profil zugewiesen wurde, werden das Profil und die Einstellungen gemäß den folgenden Listen vom Gerät entfernt.

### <a name="enrolled-devices"></a>Angemeldete Geräte

- WLAN-, VPN-, Zertifikat- und E-Mail-Profile: Diese Profile werden von allen unterstützten registrierten Geräten entfernt.
- Alle anderen Profiltypen:
    - **Windows- und Android-Geräte**: Einstellungen werden nicht vom Gerät entfernt.
    - **Windows Phone 8.1-Geräte**: Die folgenden Einstellungen werden entfernt:
        - Anfordern eines Kennworts zum Entsperren mobiler Geräte
        - Einfache Kennwörter zulassen
        - Minimale Kennwortlänge
        - Erforderlicher Kennworttyp
        - Kennwortablauf (Tage)
        - Kennwortverlauf speichern
        - Anzahl zulässiger wiederholter Anmeldefehler, bevor das Gerät zurückgesetzt wird
        - Minuten der Inaktivität, bevor ein Kennwort erforderlich ist
        - Erforderlicher Kennworttyp – Mindestanzahl von Zeichensätzen
        - Kamera zulassen
        - Verschlüsselung auf mobilem Gerät anfordern
        - Wechselspeichermedien zulassen
        - Webbrowser zulassen
        - App Store zulassen
        - Bildschirmaufnahme zulassen
        - Geolocation zulassen
        - Microsoft-Konto erlauben
        - Kopieren und Einfügen zulassen
        - WLAN-Tethering zulassen
        - Automatische Verbindung mit unverschlüsselten WLAN-Hotspots zulassen
        - Berichterstellung für WLAN-Hotspots zulassen
        - Zurücksetzen auf Werkseinstellungen zulassen
        - Bluetooth zulassen
        - NFC zulassen
        - WLAN zulassen

    - **iOS**: Alle Einstellungen werden entfernt, außer:
        - Sprachroaming zulassen
        - Datenroaming zulassen
        - Automatische Synchronisierung beim Roaming zulassen

## <a name="i-changed-a-device-restriction-profile-but-the-changes-havent-taken-effect"></a>Ich habe ein Profil für Geräteeinschränkungen geändert, aber die Änderungen wurden nicht übernommen
Windows Phone-Geräte gestatten keine Verringerung der Sicherheitsstufe in Sicherheitsrichtlinien, die mittels MDM oder EAS festgelegt wurden, nachdem diese festgelegt wurden. Angenommen, Sie legen ein **Kennwort mit Mindestanzahl von Zeichen** auf 8 fest und versuchen dann, diesen Wert auf 4 zu verringern. Das restriktivere Profil wurde bereits auf das Gerät angewendet.

Je nach Geräteplattform müssen Sie, wenn Sie das Profil auf einen niedrigeren Sicherheitswert ändern möchten, Sicherheitsrichtlinien möglicherweise zurücksetzen.
In Windows wischen Sie beispielsweise auf dem Desktop von rechts nach innen, um die Leiste **Charms** zu öffnen, und wählen Sie **Einstellungen** &gt; **Systemsteuerung**.  Wählen Sie das Applet **Benutzerkonten** aus.
Im linken Navigationsmenü befindet sich unten ein Link **Sicherheitsrichtlinien zurücksetzen** . Klicken Sie darauf, und klicken Sie dann auf die Schaltfläche **Richtlinien zurücksetzen**.
Andere MDM-Geräte, wie Android, Windows Phone 8.1 und höher sowie iOS, müssen möglicherweise außer Kraft gesetzt und bei dem Dienst neu registriert werden, damit Sie ein weniger restriktives Profil anwenden können.


### <a name="next-steps"></a>Nächste Schritte
Wenn diese Informationen zur Problembehandlung für Sie nicht hilfreich waren, wenden Sie sich wie in [Anfordern von Support für Microsoft Intune](get-support.md) beschrieben an den Microsoft Support.