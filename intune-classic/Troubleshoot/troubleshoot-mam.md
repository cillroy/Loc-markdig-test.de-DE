---
title: "Problembehandlung der Verwaltung von mobilen Geräten"
description: "Dieses Thema enthält einige Tipps zur Behandlung von Problemen bei Bereitstellungen mit bedingtem Zugriff."
keywords: 
author: oydang
ms.author: oydang
manager: angerobe
ms.date: 12/19/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: cd5a0a3b-0013-4be3-a233-ce6e9083149f
ROBOTS: NOINDEX,NOFOLLOW
ms.custom: intune-classic
ms.openlocfilehash: f98d2cd0c678bebcaa743a88992dc6dba64d9dec
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2017
---
# <a name="troubleshoot-mobile-application-management"></a>Problembehandlung der Verwaltung von mobilen Geräten

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Wenn bei der mobilen Anwendungsverwaltung mit Intune Probleme auftreten, beginnen Sie hier. Dieses Thema behandelt einige allgemeine Probleme und Fragen, die bei Ihnen auftreten könnten, und stellt Lösungen und Antworten bereit.

Wenn sich das Problem mit diesen Informationen nicht beheben lässt, finden Sie unter [How to get support for Microsoft Intune](how-to-get-support-for-microsoft-intune.md) (Anfordern von Support für Microsoft Intune) weitere Möglichkeiten, Hilfe zu erhalten.


## <a name="common-it-administrator-issues"></a>Häufige Probleme von IT-Administratoren

Dies sind Probleme, die bei Verwendung der Intune-App-Schutzrichtlinie für den IT-Administrator häufig auftreten können.

| Problem | Beschreibung | Lösung |
| -- | -- | -- |
| Richtlinie wird nicht auf Skype für Business angewendet. | Eine App-Schutzrichtlinie ohne im Azure-Portal vorgenommene Geräteregistrierung wird auf iOS- und Android-Geräten nicht auf die Skype for Business-App angewendet. | Skype for Business muss für die moderne Authentifizierung eingerichtet werden.  Führen Sie die Anweisungen in [Enable your tenant for modern authentication (Aktivieren Ihres Mandanten für moderne Authentifizierung)](http://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx) aus, um moderne Authentifizierung für Skype einzurichten. |
| Office-App-Richtlinie wird nicht angewendet. | App-Schutzrichtlinien werden für keinen Benutzer und auf keine [unterstützte Office-App](https://www.microsoft.com/cloud-platform/microsoft-intune-partners) angewendet. | Vergewissern Sie sich, dass der Benutzer für Intune lizenziert ist und dass für die Office-Apps eine bereitgestellte App-Schutzrichtlinie gilt. Es kann bis zu 8 Stunden dauern, bis eine neu bereitgestellte App-Schutzrichtlinie angewendet wird. |
| Der Administrator kann im Azure-Portal keine App-Schutzrichtlinie konfigurieren. | Der IT-Administratorbenutzer kann im Azure-Portal keine App-Schutzrichtlinien konfigurieren. | Folgende Benutzerrollen haben Zugriff auf das Azure-Portal: <ul><li>Globaler Administrator, den Sie im [Office-Portal](http://portal.office.com/) einrichten können.</li><li>Besitzer, den Sie im [Azure-Portal](https://portal.azure.com/) einrichten können.</li><li>Mitwirkender, den Sie im [Azure-Portal](https://portal.azure.com/) einrichten können.</li></ul>  Hilfe zum Einrichten dieser Rollen finden Sie unter [Vorbereiten der Konfiguration von Verwaltungsrichtlinien für mobile Apps mit Microsoft Intune](../deploy-use/get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune.md).|
|Benutzerkonten fehlen in Berichten von App-Schutzrichtlinien. | In den Berichten der Verwaltungskonsole werden keine Benutzerkonten angezeigt, für die vor Kurzem eine App-Schutzrichtlinie bereitgestellt wurde. | Wenn ein Benutzer neu als Ziel einer App-Schutzrichtlinie festgelegt worden ist, kann es bis zu 24 Stunden dauern, bis dieser Benutzer in Berichten als Zielbenutzer aufgeführt wird. |
| Richtlinienänderungen funktionieren nicht. | Es kann bis zu 8 Stunden dauern, bis Änderungen und Aktualisierungen für App-Schutzrichtlinien angewendet werden. | Ggf. können Endbenutzer sich bei der App abmelden und wieder anmelden, um die Synchronisierung mit dem Dienst zu erzwingen. |
| App-Schutzrichtlinie funktioniert nicht mit DEP. | Die App-Schutzrichtlinie wird nicht auf Apple DEP-Geräte angewendet. | Stellen Sie sicher, dass Sie User Affinity mit Apple DEP (Device Enrollment Program) verwenden. User Affinity ist für alle Apps erforderlich, die Benutzerauthentifizierung unter DEP benötigen. <br><br>Weitere Informationen zur iOS-DEP-Registrierung finden Sie unter [Registrieren unternehmenseigener iOS-Geräte mithilfe des Programm zur Geräteregistrierung (Device Enrollment Program, DEP)](../deploy-use/ios-device-enrollment-program-in-microsoft-intune.md).|
| Datenübertragungsrichtlinie funktioniert nicht mit iOS. | Die Richtlinien **Zulassen, dass die App Daten an andere Apps überträgt** und **Zulassen, dass die App Daten von anderen Apps empfängt** verwalten die Datenübertragung in iOS nicht erfolgreich. | Weitere Informationen finden Sie unter [Verwalten der Datenübertragung zwischen iOS-Apps mit Microsoft Intune](/deploy-use/manage-data-transfer-between-ios-apps-with-microsoft-intune.md). |






## <a name="common-end-user-issues"></a>Häufige Probleme von Endbenutzern

Häufige Probleme von Endbenutzern lassen sich in folgende Kategorien unterteilen:

* **Normale Verwendungsszenarien**: Diese Szenarien können für Endbenutzer in Apps auftreten, für die eine Intune-App-Schutzrichtlinie gilt. Dies sind keine tatsächlichen Probleme, werden vom Benutzer aber möglicherweise als Fehler wahrgenommen.

* **Dialogfelder bei normaler Verwendung**: Dies sind Dialogfelder, die einem Endbenutzer möglicherweise in Apps angezeigt werden, für die eine Intune-App-Schutzrichtlinie gilt. Diese Meldungen und Dialogfelder weisen **nicht** auf einen Fehler hin.

* **Fehlermeldungen und Dialogfelder**: Dies sind Fehlermeldungen und Dialogfelder, die einem Endbenutzer möglicherweise in Apps angezeigt werden, für die eine Intune-App-Schutzrichtlinie gilt. Diese weisen häufig auf einen Fehler des IT-Administrators oder ein Problem mit dem Intune-App-Schutz hin.



### <a name="normal-usage-scenarios"></a>Normale Verwendungsszenarien

Plattform | Szenario | Erläuterung |
---| --- | --- |
iOS | Der Endbenutzer kann die iOS-Freigabeerweiterung verwenden, um Geschäfts-, Schul- oder Unidaten in nicht verwalteten Apps zu öffnen, auch wenn die Datenübertragungsrichtlinie auf **Nur verwaltete Apps** oder **Keine Apps** festgelegt ist. Führt das nicht zu Datenlecks? | Die Intune-App-Schutzrichtlinie kann die iOS-Freigabeerweiterung nicht steuern, ohne das Gerät zu verwalten. Daher **verschlüsselt Intune „unternehmenseigene“ Daten, bevor diese außerhalb der App freigegeben werden**. Sie können dies überprüfen, indem Sie versuchen, die „unternehmenseigene“ Datei außerhalb der verwalteten App zu öffnen. Die Datei sollte verschlüsselt sein und außerhalb der verwalteten App nicht geöffnet werden können.
Android | Warum müssen Endbenutzer die **Unternehmensportal-App installieren**, auch wenn ich den MAM-App-Schutz ohne Geräteregistrierung verwende?  | Unter Android ist ein Großteil der App-Schutzfunktionen in die Unternehmensportal-App integriert. **Eine Registrierung der Geräte ist nicht erforderlich, allerdings wird immer die Unternehmensportal-App benötigt**. Beim App-Schutz ohne Registrierung muss lediglich die Unternehmensportal-App auf dem Gerät des Endbenutzers installiert sein.

### <a name="normal-usage-dialogs"></a>Dialogfelder bei normaler Verwendung

Plattform | Meldung oder Dialogfeld | Erläuterung |
--- | --- | --- |
iOS, Android | **Anmeldung**: Zum Schutz ihrer Daten muss Ihre Organisation diese App verwalten. Um diese Aktion abzuschließen, melden Sie sich mit Ihrem Geschäfts-, Schul- oder Unikonto an. | Der Endbenutzer muss sich mit seinem Geschäfts-, Schul- oder Unikonto anmelden, um diese App zu verwenden. Hierzu ist eine App-Schutzrichtlinie erforderlich. Damit die Richtlinie angewendet werden kann, muss der Benutzer sich bei Azure Active Directory authentifizieren.
iOS, Android |**Neustart erforderlich**: Ihre Organisation schützt jetzt ihre Daten in dieser App. Sie müssen die App neu starten, um fortzufahren. | Die App hat soeben die Intune-App-Schutzrichtlinie empfangen und muss neu gestartet werden, damit die Richtlinie angewendet wird.
iOS, Android |**Aktion nicht zulässig**: Ihre Organisation lässt nur das Öffnen von Geschäfts-, Schul- oder Unidaten in dieser App zu. | Der IT-Administrator hat die Richtlinie **Zulassen, dass die App Daten von anderen Apps empfängt** auf **Nur verwaltete Apps** festgelegt. Daher kann der Endbenutzer Daten in diese App nur aus anderen Apps übertragen, für die eine App-Schutzrichtlinie gilt.
iOS, Android |**Aktion nicht zulässig**: Ihre Organisation gestattet Ihnen die Übertragung organisationseigener Daten nur an andere verwaltete Apps. | Der IT-Administrator hat die Richtlinie **Zulassen, dass die App Daten an andere Apps überträgt** auf **Nur verwaltete Apps** festgelegt. Daher kann der Endbenutzer Daten aus dieser App nur an andere Apps übertragen, für die eine App-Schutzrichtlinie gilt.
iOS, Android |**Warnung zur Zurücksetzung**: Ihre Organisation hat eigene Daten, die dieser App zugeordnet sind, entfernt. Zum Fortfahren müssen Sie die App neu starten. | Der IT-Administrator hat mithilfe des Intune-App-Schutzes ein Zurücksetzen der App initiiert.
Android | **Unternehmensportal erforderlich**: Sie müssen die Intune-Unternehmensportal-App installieren, um Ihr Geschäfts-, Schul- oder Unikonto mit dieser App zu verwenden. Tippen Sie auf „Zum Store gehen“, um den Vorgang fortzusetzen. | Unter Android ist ein Großteil der App-Schutzfunktionen in die Unternehmensportal-App integriert. **Eine Registrierung der Geräte ist nicht erforderlich, allerdings wird immer die Unternehmensportal-App benötigt**. Beim App-Schutz ohne Registrierung muss lediglich die Unternehmensportal-App auf dem Gerät des Endbenutzers installiert sein.


### <a name="error-messages-and-dialogs-on-ios"></a>Fehlermeldungen und Dialogfelder in iOS


Fehlermeldung oder Dialogfeld | Ursache | Wartung |
-- | --- | --- |
**App nicht eingerichtet**: Diese App wurde für Sie nicht zur Verwendung eingerichtet. Wenden Sie sich an Ihren IT-Administrator, um Unterstützung zu erhalten. | Fehler bei der Ermittlung der erforderlichen App-Schutzrichtlinie für die App. |Stellen Sie sicher, dass eine iOS-App-Schutzrichtlinie für die Sicherheitsgruppe des Benutzers bereitgestellt und diese App als Ziel festgelegt wurde.
**Willkommen bei Intune Managed Browser**: Diese App funktioniert am besten, wenn sie über Microsoft Intune verwaltet wird. Mit dieser App können Sie jederzeit das Web durchsuchen. Wenn sie über Microsoft Intune verwaltet wird, können Sie auf zusätzliche Features zum Schutz von Daten zugreifen. | Fehler bei der Ermittlung der erforderlichen App-Schutzrichtlinie für die Intune Managed Browser-App. <br><br>Der Benutzer kann die App trotzdem verwenden, um das Web zu durchsuchen, aber die App wird nicht von Intune verwaltet. | Stellen Sie sicher, dass eine iOS-App-Schutzrichtlinie für die Sicherheitsgruppe des Benutzers bereitgestellt und die Intune Managed Browser-App als Ziel festgelegt wurde.
**Fehler bei der Anmeldung**: Eine Anmeldung ist zurzeit nicht möglich. Wiederholen Sie den Vorgang zu einem späteren Zeitpunkt. | Fehler bei Registrierung des Benutzers beim MAM-Dienst nach dem Versuch des Benutzers, sich mit seinem Geschäfts-, Schul- oder Unikonto anzumelden. | Stellen Sie sicher, dass eine iOS-App-Schutzrichtlinie für die Sicherheitsgruppe des Benutzers bereitgestellt und diese App als Ziel festgelegt wurde.
**Konto nicht eingerichtet**: Ihre Organisation hat Ihr Konto nicht für den Zugriff auf Geschäfts-, Schul- oder Unidaten eingerichtet. Wenden Sie sich an Ihren IT-Administrator, um Hilfe zu erhalten. | Das Benutzerkonto verfügt über keine Windows Intune A Direct-Lizenz. | Stellen Sie sicher, dass dem Konto des Benutzers im [Office-Portal](http://portal.office.com) eine Intune-Lizenz zugewiesen ist.
**Gerät nicht kompatibel**: Diese App kann nicht verwendet werden, weil Sie ein Gerät mit Jailbreak verwenden. Wenden Sie sich an Ihren IT-Administrator, um Unterstützung zu erhalten. | Intune hat festgestellt, dass der Benutzer ein Gerät mit Jailbreak verwendet. | Setzen Sie das Gerät auf die Werkseinstellungen zurück. Führen Sie [diese Anweisungen](https://support.apple.com/HT201274) über die Apple-Support-Website aus.
**Internetverbindung erforderlich**: Sie benötigen eine Internetverbindung, um zu überprüfen, ob Sie diese App verwenden dürfen. | Das Gerät ist nicht mit dem Internet verbunden. | Verbinden Sie das Gerät mit einem WLAN oder Datennetzwerk.
**Unbekannter Fehler**: Versuchen Sie, die App neu zu starten. Wenn das Problem weiterhin besteht, wenden Sie sich an Ihren IT-Administrator, um Hilfe zu erhalten. | Ein unbekannter Fehler ist aufgetreten. | Warten Sie eine gewisse Zeit, und versuchen Sie es erneut. Wenn der Fehler weiterhin auftritt, erstellen Sie [hier](how-to-get-support-for-microsoft-intune.md) ein Supportticket mit Intune.
**Zugriff auf Daten Ihrer Organisation**: Das angegebene Geschäfts-, Schul oder Unikonto hat keinen Zugriff auf diese App. Sie müssen sich möglicherweise mit einem anderen Konto anmelden. Wenden Sie sich an Ihren IT-Administrator, um Unterstützung zu erhalten. | Intune erkennt, dass der Benutzer versucht hat, sich mit einem anderen als dem bei MAM registrierten Geschäfts-, Schul- oder Unikonto für das Gerät anzumelden. Pro Gerät kann von MAM jeweils nur ein Geschäfts-, Schul- oder Unikonto verwaltet werden. | Fordern Sie den Benutzer auf, sich mit dem Konto anzumelden, mit dessen Benutzername die Anmeldeseite zuvor aufgefüllt wurde. <br> <br> Alternativ kann der Benutzer sich mit dem neuen Geschäfts-, Schul- oder Unikonto anmelden und das vorhandene, bei MAM registrierte Konto entfernen.
**Verbindungsproblem**: Es ist ein unerwartetes Verbindungsproblem aufgetreten. Überprüfen Sie Ihre Verbindung, und versuchen Sie es erneut.  |  Unerwarteter Fehler. | Warten Sie eine gewisse Zeit, und versuchen Sie es erneut. Wenn der Fehler weiterhin auftritt, erstellen Sie [hier](how-to-get-support-for-microsoft-intune.md) ein Supportticket mit Intune.
**Warnung**: Diese App kann nicht mehr verwendet werden. Wenden Sie sich an Ihren IT-Administrator, um weitere Informationen zu erhalten. | Fehler beim Überprüfen des App-Zertifikats. | Stellen Sie sicher, dass die App-Version auf dem neuesten Stand ist. <br><br> Installieren Sie die App neu.
**Fehler**: Diese App hat ein Problem festgestellt und muss geschlossen werden. Wenn dieser Fehler weiterhin auftritt, wenden Sie sich an Ihren IT-Administrator. | Fehler beim Lesen der PIN der MAM-App aus dem Apple iOS-Schlüsselbund. | Starten Sie das Gerät neu. Stellen Sie sicher, dass die App-Version auf dem neuesten Stand ist. <br><br> Installieren Sie die App neu.


### <a name="error-messages-and-dialogs-on-android"></a>Fehlermeldungen und Dialogfelder in Android

Dialog/Fehlermeldung | Ursache | Wartung |
-- | --- | --- |
**App nicht eingerichtet**: Diese App wurde für Sie nicht zur Verwendung eingerichtet. Wenden Sie sich an Ihren IT-Administrator, um Unterstützung zu erhalten. | Fehler bei der Ermittlung der erforderlichen App-Schutzrichtlinie für die App. |Stellen Sie sicher, dass eine Android-App-Schutzrichtlinie für die Sicherheitsgruppe des Benutzers bereitgestellt und diese App als Ziel festgelegt wurde.
**Fehler beim Starten der App**: Beim Starten Ihrer App ist ein Problem aufgetreten. Versuchen Sie, die App oder die Intune-Unternehmensportal-App zu aktualisieren. Wenn Sie Hilfe benötigen, wenden Sie sich an Ihren IT-Administrator. | Intune hat eine gültige App-Schutzrichtlinie für die App gefunden, aber die App stürzt während der Initialisierung von MAM ab. | Stellen Sie sicher, dass die App-Version auf dem neuesten Stand ist. <br><br> Stellen Sie sicher, dass die Intune-Unternehmensportal-App auf dem Gerät installiert und auf dem neuesten Stand ist. <br><br> Wenn der Fehler weiterhin auftritt, verwenden Sie die Unternehmensportal-App, um Protokolle an Intune zu senden, oder erstellen Sie [hier](how-to-get-support-for-microsoft-intune.md) ein Supportticket.
**Keine Apps gefunden**: Auf diesem Gerät gibt es keine Apps, die von Ihrer Organisation zum Öffnen dieser Inhalte zugelassen werden. Wenden Sie sich an Ihren IT-Administrator, um Unterstützung zu erhalten. | Der Benutzer hat versucht, Geschäfts-, Schul- oder Unidaten mit einer anderen App zu öffnen, aber Intune kann keine anderen verwalteten Apps finden, die zum Öffnen der Daten zulässig sind. | Vergewissern Sie sich, dass eine Android-App-Schutzrichtlinie für die Sicherheit des Benutzers bereitgestellt wird und als Ziel mindestens eine andere MAM-fähige App festgelegt ist, die die betreffenden Daten öffnen kann.
**Fehler bei der Anmeldung**: Versuchen Sie erneut, sich anzumelden. Wenn das Problem weiterhin besteht, wenden Sie sich an Ihren IT-Administrator, um Hilfe zu erhalten. | Fehler bei der Authentifizierung des Kontos, mit dem der Benutzer versucht hat, sich anzumelden. | Vergewissern Sie sich, dass sich der Benutzer mit dem bereits beim Intune MAM-Dienst registrierten Geschäfts-, Schul- oder Unikonto anmeldet (dem ersten Geschäfts-, Schul- oder Unikonto, das erfolgreich bei dieser App registriert wurde). <br><br> Löschen Sie die Daten der App. <br><br> Stellen Sie sicher, dass die App-Version auf dem neuesten Stand ist. <br><br> Stellen Sie sicher, dass die Version des Unternehmensportals auf dem neuesten Stand ist.
**Internetverbindung erforderlich**: Sie benötigen eine Internetverbindung, um zu überprüfen, ob Sie diese App verwenden dürfen. | Das Gerät ist nicht mit dem Internet verbunden. | Verbinden Sie das Gerät mit einem WLAN oder Datennetzwerk.
**Gerät nicht kompatibel**: Sie können diese App nicht verwenden, da bei Ihrem Gerät die Nutzungsbeschränkungen entfernt wurden. Wenden Sie sich an Ihren IT-Administrator, um Unterstützung zu erhalten. | Intune hat festgestellt, dass der Benutzer ein Gerät verwendet, bei dem die Nutzungsbeschränkungen entfernt wurden. | Setzen Sie das Gerät auf die Werkseinstellungen zurück.
**Konto nicht eingerichtet**: Diese App muss mit Microsoft Intune verwaltet werden, Ihr Konto wurde jedoch noch nicht eingerichtet. Wenden Sie sich an Ihren IT-Administrator, um Unterstützung zu erhalten. | Das Benutzerkonto verfügt über keine Windows Intune A Direct-Lizenz. | Stellen Sie sicher, dass dem Konto des Benutzers im [Office-Portal](http://portal.office.com) eine Intune-Lizenz zugewiesen ist.
**Registrierung der App nicht möglich**: Diese App muss mit Microsoft Intune verwaltet werden, eine Registrierung der App ist momentan jedoch nicht möglich. Wenden Sie sich an Ihren IT-Administrator, um Unterstützung zu erhalten. | Bei der automatischen Registrierung der App beim MAM-Dienst tritt ein Fehler auf, wenn eine App-Schutzrichtlinie erforderlich ist. | Löschen Sie die Daten der App. <br><br> Senden Sie Protokolle über die Unternehmensportal-App an Intune, oder erstellen Sie [hier](how-to-get-support-for-microsoft-intune.md) ein Supportticket.




### <a name="see-also"></a>Siehe auch
- [Überprüfen des Setups für die Verwaltung Ihrer mobilen Anwendungen](../deploy-use/validate-mobile-application-management.md)
- [Vorbereiten der Konfiguration von Verwaltungsrichtlinien für mobile Apps mit Microsoft Intune](../deploy-use/get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune.md)
- [Anfordern von Support für Microsoft Intune](how-to-get-support-for-microsoft-intune.md)
