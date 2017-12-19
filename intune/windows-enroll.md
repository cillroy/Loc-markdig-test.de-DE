---
title: "Windows-Geräte registrieren"
titlesuffix: Azure portal
description: "Aktivieren der Verwaltung mobiler Geräte (Mobile Device Management, MDM) für Windows-Geräte in Intune."
keywords: 
author: nathbarn
manager: nathbarn
ms.date: 11/29/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f94dbc2e-a855-487e-af6e-8d08fabe6c3d
ms.reviewer: damionw
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: bf9ae5f05e21fa2ca7be4af08dace5b96315cec3
ms.sourcegitcommit: 3b397b1dcb780e2f82a3d8fba693773f1a9fcde1
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/12/2017
---
# <a name="enroll-windows-devices"></a>Windows-Geräte registrieren

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Dieses Thema hilft IT-Administratoren, die Windows-Registrierung für ihre Benutzer zu vereinfachen. Sobald Sie [Intune eingerichtet](setup-steps.md) haben, können Benutzer Windows-Geräte registrieren, indem sie sich mit ihrem Geschäfts-, Schul- oder Unikonto [anmelden](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-windows).  

Als Intune-Administrator können Sie die Registrierung auf folgende Weise vereinfachen:
- [Aktivieren der automatischen Registrierung](#enable-windows-10-automatic-enrollment) (Azure AD Premium erforderlich)
- [CNAME-Registrierung](#simplify-windows-enrollment-without-azure-ad-premium)
- [Aktivieren der Massenregistrierung](windows-bulk-enroll.md) (Azure AD Premium und Windows Configuration Designer erforderlich)
- [Hinzufügen einer benutzerdefinierten Nachricht](windows-enrollment-status.md), um Ihre Benutzer bei der Registrierung zu begrüßen und den Status der Durchsetzung von Richtlinieneinstellungen anzuzeigen

Zwei Faktoren bestimmen, wie Sie die Registrierung von Windows-Geräten vereinfachen können:

- **Verwenden Sie Azure Active Directory Premium?** <br>[Azure AD Premium](https://docs.microsoft.com/azure/active-directory/active-directory-get-started-premium) ist in Enterprise Mobility + Security und in anderen Lizenzierungsplänen enthalten.
- **Welche Versionen von Windows-Clients werden von Benutzern registriert?** <br>Windows 10-Geräte können automatisch durch Hinzufügen eines Geschäfts-oder Schulkontos registriert werden. Frühere Versionen müssen mithilfe der Unternehmensportal-App registriert werden.

||**Azure AD Premium**|**AD (Sonstiges)**|
|----------|---------------|---------------|  
|**Windows 10**|[Automatische Registrierung](#enable-windows-10-automatic-enrollment) |[Benutzerregistrierung](#enable-windows-enrollment-without-azure-ad-premium)|
|**Frühere Windows-Versionen**|[Benutzerregistrierung](#enable-windows-enrollment-without-azure-ad-premium)|[Benutzerregistrierung](#enable-windows-enrollment-without-azure-ad-premium)|

Organisationen, die die automatische Registrierung nutzen, können mithilfe der Windows Configuration Designer-App auch [Geräte für die Massenregistrierung](windows-bulk-enroll.md) konfigurieren.

**Unterstützung mehrerer Benutzer**<br>
Für Geräte, die das Windows 10 Creators Update ausführen und in die Azure Active Directory-Domäne eingebunden sind, haben wir Unterstützung für die Mehrbenutzerverwaltung hinzugefügt. Wenn sich Standardbenutzer mit ihren Azure AD-Anmeldeinformationen anmelden, erhalten sie Apps und Richtlinien, die ihrem Benutzernamen zugewiesen wurden. Benutzer können das Unternehmensportal derzeit nicht für Self-Service-Szenarien beispielsweise zum Installieren von Apps verwenden.

[!INCLUDE[AAD-enrollment](./includes/win10-automatic-enrollment-aad.md)]

## <a name="simplify-windows-enrollment-without-azure-ad-premium"></a>Vereinfachen der Windows-Registrierung ohne Azure AD Premium
Sie können die Registrierung für Ihre Benutzer vereinfachen, indem Sie einen Domänennamenserver-Alias (DNS) (Eintragstyp CNAME) erstellen, der Registrierungsanforderungen automatisch an Intune-Server umleitet. Wenn Sie keinen DNS-CNAME-Ressourceneintrag erstellen, müssen Benutzer beim Herstellen einer Verbindung mit Intune den Intune-Servernamen angeben.

**Schritt 1: Erstellen von CNAME-Einträgen** (optional)<br>
Erstellen Sie CNAME-DNS-Ressourceneinträge für die Domäne des Unternehmens. Wenn der Name Ihrer Unternehmenswebsite beispielsweise „contoso.com“ lautet, erstellen Sie einen CNAME-Eintrag im DNS, der „EnterpriseEnrollment.contoso.com“ auf „enterpriseenrollment-s.manage.microsoft.com“ umleitet.

Obwohl die Erstellung von CNAME DNS-Einträgen optional ist, vereinfachen diese die Registrierung für Benutzer. Wenn kein CNAME-Eintrag für die Registrierung gefunden wurde, werden Benutzer aufgefordert, manuell den MDM-Servernamen „enrollment.manage.microsoft.com“ einzugeben.

|Typ|Hostname|Verweist auf|TTL|
|----------|---------------|---------------|---|
|CNAME|EnterpriseEnrollment.company_domain.com|EnterpriseEnrollment-s.manage.microsoft.com| 1 Stunde|
|CNAME|EnterpriseRegistration.company_domain.com|EnterpriseRegistration.windows.net|1 Stunde|

Wenn Sie mehr als ein UPN-Suffix haben, müssen Sie einen CNAME für jeden Domänennamen erstellen und jeden auf EnterpriseEnrollment-s.manage.microsoft.com zeigen. Wenn Benutzer bei Contoso name@contoso.com sowie name@us.contoso.com und name@eu.constoso.com als E-Mail/UPN verwenden, sollte der Contoso-DNS-Administrator die folgenden CNAMEs erstellen:

|Typ|Hostname|Verweist auf|TTL|  
|----------|---------------|---------------|---|
|CNAME|EnterpriseEnrollment.contoso.com|EnterpriseEnrollment-s.manage.microsoft.com|1 Stunde|
|CNAME|EnterpriseEnrollment.us.contoso.com|EnterpriseEnrollment-s.manage.microsoft.com|1 Stunde|
|CNAME|EnterpriseEnrollment.eu.contoso.com|EnterpriseEnrollment-s.manage.microsoft.com| 1 Stunde|

`EnterpriseEnrollment-s.manage.microsoft.com` – unterstützt eine Umleitung zum Intune-Dienst mit Domänenerkennung anhand des E-Mail-Domänennamens.

Es kann bis zu 72 Stunden dauern, bis Änderungen an DNS-Einträgen vollständig verteilt sind. Sie können die DNS-Änderung in Intune erst überprüfen, wenn der DNS-Eintrag verteilt ist.

**Schritt 2: Verifizieren des CNAME-Eintrags** (optional)<br>
Wählen Sie im Azure-Portal **Weitere Dienste** > **Überwachung und Verwaltung** > **Intune** aus. Wählen Sie auf dem Blatt „Intune“ die Option **Geräte registrieren** > **Windows-Registrierung aktivieren** aus. Geben Sie die URL der Unternehmenswebsite in das Feld **Verifizierten Domänennamen eingeben** ein, und wählen Sie anschließend **Automatische Erkennung testen** aus.

## <a name="tell-users-how-to-enroll-windows-devices"></a>Benutzern mitteilen, wie Windows-Geräte registriert werden
Benutzern erklären, wie sie ihre Windows-Geräte registrieren können, und sie darüber informieren, was sie erwarten können, wenn ihre Geräte verwaltet werden.

> [!NOTE]
> Endbenutzer müssen über Microsoft Edge auf die Website des Unternehmensportals zugreifen, um Windows-Anwendungen anzuzeigen, die Sie für bestimmte Versionen von Windows zugewiesen haben. Andere Browser wie Google Chrome, Mozilla Firefox und Internet Explorer unterstützen diese Art der Filterung nicht.

Registrierungsanleitungen für Endbenutzer finden Sie unter [Registrieren Ihres Windows-Geräts bei Intune](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-windows). Sie können Benutzer auch auf [Welche Informationen erhält mein Unternehmen, wenn ich mein Gerät in Intune registriere?](https://docs.microsoft.com/intune-user-help/what-can-your-it-administrator-see-when-you-enroll-your-device-in-intune-windows) verweisen.

Weitere Informationen zu Endbenutzeraufgaben finden Sie unter [Ressourcen zu Endbenutzerszenarios in Microsoft Intune](end-user-educate.md).

## <a name="next-steps"></a>Nächste Schritte

- [Überlegungen bei der Verwaltung von Windows-Geräten mit Intune in Azure](/intune-classic/deploy-use/intune-on-azure).
