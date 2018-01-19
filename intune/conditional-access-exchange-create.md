---
title: "Erstellen und Zuweisen einer Richtlinie für bedingten Zugriff für Exchange lokal"
titlesuffix: Azure portal
description: "Konfigurieren Sie den bedingten Zugriff für eine lokale Installation von Exchange und für das ältere Exchange Online Dedicated in Intune."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 04/24/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 127dafcb-3f30-4745-a561-f62c9f095907
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 953f78de15d292346ec7d618e976fc085ba4d428
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2017
---
# <a name="how-to-create-and-assign-a-conditional-access-policy-for-exchange-on-premises-and-legacy-exchange-online-dedicated-in-microsoft-intune"></a>Erstellen und Zuweisen einer Richtlinie für bedingten Zugriff für Exchange lokal und das ältere Exchange Online Dedicated in Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Dieses Thema führt Sie durch die Konfiguration des bedingten Zugriffs für Exchange lokal basierend auf der Gerätekonformität.

Wenn Sie über eine Exchange Online Dedicated-Umgebung verfügen und herausfinden müssen, ob es sich um die neue oder die ältere Konfiguration handelt, wenden Sie sich an Ihren Kundenbetreuer. Um den E-Mail-Zugriff auf lokales Exchange oder Ihre ältere Exchange Online Dedicated-Umgebung zu steuern, konfigurieren Sie den bedingten Zugriff für lokales Exchange in Intune.

## <a name="before-you-begin"></a>Vorbereitung

Bevor Sie den bedingten Zugriff konfigurieren können, müssen Sie Folgendes überprüfen:

- Bei Ihrer Exchange-Version muss es sich um **Exchange 2010 SP1 oder höher** handeln. Exchange Server-Clientzugriffsserver-Arrays werden unterstützt.

- Sie müssen den [lokalen Exchange-Connector für Exchange Active Sync](exchange-connector-install.md) verwenden, der Intune mit Exchange lokal verbindet.

    >[!IMPORTANT]
    >Der lokale Exchange-Connector ist spezifisch für Ihren Intune-Mandanten und kann mit keinem anderen Mandanten verwendet werden. Sie müssen auch sicherstellen, dass der Exchange-Connector für Ihren Mandanten **nur auf einem Computer** installiert ist.

- Der Connector kann auf jedem Computer installiert werden, solange dieser Computer mit dem Exchange-Server kommunizieren kann.

- Der Connector unterstützt die **Exchange-Clientzugriffsserver-Umgebung**. Technisch können Sie den Connector auch direkt auf dem Exchange-Clientzugriffsserver installieren, aber dies ist nicht zu empfehlen, da die Last auf dem Server dadurch erhöht wird. Sie müssen den Connector so konfigurieren, dass er mit einem der Exchange-Clientzugriffsserver kommuniziert.

- **Exchange ActiveSync** muss für die zertifikatbasierte Authentifizierung oder die Eingabe von Anmeldeinformationen durch Benutzer konfiguriert werden.

- Wenn Richtlinien für bedingten Zugriff konfiguriert und auf einen Benutzer angewendet wurden, muss das **Gerät**, das der Benutzer zum Abrufen von E-Mails verwendet, folgende Voraussetzungen erfüllen:
    - Es muss bei Intune **registriert** sein oder sich um einen in die Domäne eingebundenen PC handeln.
    - **Es muss in Azure Active Directory registriert sein**. Darüber hinaus muss die Exchange ActiveSync-ID des Clients in Azure Active Directory registriert sein.
<br></br>
- AAD DRS wird automatisch für Intune und Office 365-Kunden aktiviert. Kunden, die bereits den AD FS Device Registration Service bereitgestellt haben, sehen keine registrierten Geräte in ihrem lokalen Active Directory. **Dies gilt nicht für Windows-PCs und Windows Phone-Geräte.**

- Es besteht **Konformität** mit allen für das Gerät festgelegten Konformitätsrichtlinien.

- Wenn das Gerät die Einstellungen für den bedingten Zugriff nicht erfüllt, erhält der Benutzer bei der Anmeldung eine der folgenden Meldungen:
    - Wenn das Gerät nicht bei Intune oder in Azure Active Directory registriert ist, wird eine Meldung mit Anweisungen zum Installieren der Unternehmensportal-App, zum Registrieren des Geräts und zum Aktivieren des E-Mail-Zugriffs angezeigt. Dieser Prozess verknüpft auch die Exchange ActiveSync-ID mit dem Eintrag des Geräts in Azure Active Directory.
    - Wenn das Gerät nicht konform ist, wird eine Meldung angezeigt, die Benutzer zum Intune-Unternehmensportal oder zur Unternehmensportal-App weiterleitet. Hier finden sie Informationen zum Problem und zu dessen Lösung.

### <a name="support-for-mobile-devices"></a>Unterstützung für mobile Geräte

- Windows Phone 8.1 und höher
- Systemeigene E-Mail-App unter iOS.
- EAS-E-Mail-Clients wie Gmail unter Android 4 oder höher.
- EAS-E-Mail-Clients für **Android for Work-Geräte:** Nur **Gmail**- und **Nine Work**-Apps im **Arbeitsprofil** werden auf Android for Work-Geräten unterstützt. Damit der bedingte Zugriff unter Android for Work funktioniert, müssen Sie ein E-Mail-Profil für die Gmail- oder Nine Work-App sowie diese Apps als erforderliche Installation bereitstellen.

> [!NOTE]
> Microsoft Outlook-App unter Android und iOS wird nicht unterstützt. Android for Work wird derzeit über die nächsten Monate mandantenübergreifend in Intune eingeführt.

### <a name="support-for-pcs"></a>Unterstützung für PCs

Die systemeigene **E-Mail**-Anwendung unter Windows 8.1 und höher (bei Registrierung bei Intune)


## <a name="configure-exchange-on-premises-access"></a>Konfigurieren des Zugriffs auf Exchange lokal

1. Melden Sie sich im [Azure-Portal](https://portal.azure.com/) mit Ihren Intune-Anmeldeinformationen an.

2. Sobald Sie erfolgreich angemeldet sind, wird das **Azure-Dashboard** angezeigt.

3. Wählen Sie im linken Menü **Weitere Dienste** aus, und geben Sie in das Filtertextfeld die Zeichenfolge **Intune** ein.

4. Wählen Sie **Intune** aus. Das **Intune-Dashboard** wird angezeigt.

5. Wählen Sie **Lokaler Zugriff**, und wählen Sie dann

6. Das Blatt **Lokal** enthält den Status der Richtlinie für bedingten Zugriff und die Geräte, die davon betroffen sind.

7. Wählen Sie unter **Verwalten** die Option **Zugriff auf Exchange lokal** aus.

8. Wählen Sie auf dem Blatt **Zugriff auf Exchange lokal** die Option **Ja** aus, um Access Control für Exchange lokal zu aktivieren.

    > [!NOTE]
    > Wenn Sie den lokalen Connector für Exchange Active Sync nicht konfiguriert haben, ist diese Option deaktiviert.  Sie müssen diesen Connector zunächst installieren und konfigurieren, bevor Sie den bedingten Zugriff auf Exchange lokal aktivieren. Weitere Informationen finden Sie unter [Installieren des lokalen Exchange Connectors für Intune](exchange-connector-install.md).

9. Wählen Sie unter **Zuweisung** die Option **Eingeschlossene Gruppen** aus.  Verwenden Sie die Sicherheitsbenutzergruppe, auf die bedingter Zugriff angewendet werden soll. In diesem Fall müssen die Benutzer ihre Geräte selbst in Intune registrieren und die Konformität mit den Konformitätsprofilen sicherstellen.

10. Wenn Sie eine bestimmte Gruppen von Benutzern ausschließen möchten, können Sie dazu **Ausgeschlossene Gruppen** auswählen. Wählen Sie anschließend eine Benutzergruppe aus, die Sie von der erforderlichen Registrierung des Geräts und der Konformitätsprüfung ausschließen möchten.

11. Wählen Sie unter **Einstellungen** die Option **Benutzerbenachrichtigungen** aus, um die Standard-E-Mail-Nachricht zu ändern. Diese Meldung wird an Benutzer gesendet, wenn ihr Gerät nicht konform ist und sie auf Exchange lokal zugreifen möchten. Die Nachrichtenvorlage verwendet Markupsprache.  Sie sehen während der Eingabe auch eine Vorschau der Nachricht.
    > [!TIP]
    > Weitere Informationen zur Markupsprache finden Sie in diesem Wikipedia-[Artikel](https://en.wikipedia.org/wiki/Markup_language).

12. Legen Sie auf dem Blatt **Erweiterte Zugriffseinstellungen für Exchange ActiveSync** die globale Standardregel für den Zugriff von Geräten, die nicht von Intune verwaltet werden, sowie Regeln auf Plattformebene fest, wie in den nächsten beiden Schritten beschrieben.

13. Bei Geräten, die nicht durch den bedingten Zugriff oder andere Regeln abgedeckt werden, können Sie auswählen, ob der Zugriff auf Exchange zugelassen oder blockiert werden soll.
  - Wenn Sie den Zugriff zulassen, können alle Geräte sofort auf Exchange lokal zugreifen.  Geräte, die Benutzern in **Eingeschlossene Gruppen** gehören, werden blockiert, wenn sie später als nicht konform mit den Konformitätsrichtlinien ausgewertet werden oder nicht in Intune registriert sind.
  - Wenn Sie diese Option auf das Blockieren des Zugriffs festlegen, wird der Zugriff auf Exchange lokal sofort für alle Geräte blockiert.  Geräte, die Benutzern in **Eingeschlossene Gruppen** gehören, erhalten Zugriff, sobald das Gerät in Intune registriert und als konform ausgewertet wurde. Android-Geräte ohne Samsung KNOX Standard werden immer blockiert, da sie diese Einstellung nicht unterstützen.
<br></br>
14. Wählen Sie unter **Geräteplattformausnahmen** die Option **Hinzufügen** aus, um die Plattformen anzugeben. Wenn die Einstellung **Zugriff nicht verwalteter Geräte** auf **blockiert** festgelegt ist, erhalten Geräte, die registriert und konform sind, auch dann Zugriff, wenn eine Plattformausnahme diesen blockieren würde. Wählen Sie **OK** aus, um die Einstellungen zu speichern.

15. Klicken Sie auf dem Blatt **Lokal** auf **Speichern**, um die Richtlinie für bedingten Zugriff zu speichern.

## <a name="create-azure-ad-conditional-access-policies-in-intune"></a>Erstellen von Azure AD-Richtlinien für den bedingten Zugriff in Intune

Ab Intune Version 1704 können Administratoren im Azure-Portal für Intune Azure AD-Richtlinien für den bedingten Zugriff erstellen. Diese bieten Ihnen den Komfort, nicht zwischen Azure- und Intune-Workloads wechseln zu müssen.

> [!IMPORTANT]
> Sie benötigen eine Azure AD Premium-Lizenz, um im Azure-Portal für Intune Azure AD-Richtlinien für den bedingten Zugriff zu erstellen.

### <a name="to-create-azure-ad-conditional-access-policy"></a>Erstellen einer Azure AD-Richtlinie für den bedingten Zugriff

1. Wählen Sie auf dem **Intune-Dashboard** die Option **Bedingter Zugriff** aus.

2. Wählen Sie auf dem Blatt **Richtlinien** **Neue Richtlinie** aus, um die neue Azure AD-Richtlinie für den bedingten Zugriff zu erstellen.

## <a name="see-also"></a>Weitere Informationen:

[Bedingter Zugriff in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access)
