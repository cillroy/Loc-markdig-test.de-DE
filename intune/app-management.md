---
title: Was ist die App-Verwaltung?
titlesuffix: Azure portal
description: In diesem Thema lernen Sie die Grundlagen der App-Verwaltung mit Microsoft Intune kennen."
keywords: 
author: erikre
ms.author: erikre
manager: angrobe
ms.date: 07/11/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 1975a2dc-3a14-4cb9-9afb-e2ba01a1c51b
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 5a1cbd6fc3244686c1f5a1db3e4365e615662f0e
ms.sourcegitcommit: 67ec0606c5440cffa7734f4eefeb7121e9d4f94f
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/08/2017
---
# <a name="what-is-microsoft-intune-app-management"></a>Was ist die Microsoft Intune App-Verwaltung?


[!INCLUDE[azure_portal](./includes/azure_portal.md)]


Als IT-Administrator müssen Sie sicherstellen, dass die Endbenutzer Zugriff auf die Apps haben, die sie für ihre Arbeit benötigen. Dies kann aus verschiedenen Gründen eine große Herausforderung darstellen:
- Es gibt eine Vielzahl von Geräteplattformen und App-Typen.
- Sie müssen möglicherweise Apps auf unternehmenseigenen Geräten und auf Geräten von Benutzern verwalten.
- Sie müssen sicherstellen, dass Ihr Netzwerk und Ihre Daten sicher bleiben.

Darüber hinaus müssen Sie ggf. auch Apps auf Geräten, die nicht in Intune registriert sind, zuweisen und verwalten.

Intune bietet eine Reihe von Funktionen, die Ihnen dabei helfen, die benötigten Apps auf allen erforderlichen Geräten bereitzustellen.

## <a name="app-management-capabilities-by-platform"></a>App-Verwaltungsfunktionen nach Plattform

||||||
|-|-|-|-|-|
|&nbsp; |Android|iOS|Windows Phone 8.1|Windows 10|
|Hinzufügen und Zuweisen von Apps für Geräte und Benutzer|Ja|Ja|Ja|Ja|
|Zuweisen von Apps für Geräte, die nicht bei Intune registriert sind|Ja|Ja|Nein|Nein|
|Steuern des Startverhaltens von Apps mithilfe von App-Konfigurationsrichtlinien|Nein|Ja|Nein|Nein|
|Verwenden von Richtlinien für die Bereitstellung mobiler Apps zum Verlängern abgelaufener Apps|Nein|Ja|Nein|Nein|
|Schützen von Unternehmensdaten in Apps mit App-Schutzrichtlinien|Ja|Ja|Nein|Nein<sup>1</sup>|
|Entfernen ausschließlich von Unternehmensdaten aus einer installierten App (Selektive App-Zurücksetzung)|Ja|Ja|Ja|Ja|
|Überwachen von App-Zuweisungen|Ja|Ja|Ja|Ja|
|Zuweisen und Nachverfolgen von Per Volumenlizenz in einem App-Store erworbenen Apps|Nein|Nein|Nein|Ja|
|Verpflichtende Installation von Apps auf Geräten (erforderlich)<sup>2</sup>|Ja|Ja|Ja|Ja|
|Optionale Installation auf Geräten über das Unternehmensportal (verfügbare Installation)|Ja|Ja|Ja|Ja|
|Installieren von Verknüpfungen zu Apps im Internet (Webclip)|Ja|Ja|Ja|Ja|
|Interne (branchenspezifische) Apps|Ja|Ja|Nein|Nein|
|Apps aus einem Store|Ja|Ja|Ja|Ja|
|Aktualisierung von Apps|Ja|Ja|Ja|Ja|

<sup>1</sup> Erwägen Sie die Verwendung [Windows Information Protection](windows-information-protection-configure.md) für den Schutz von Apps auf Geräten mit Windows 10.

<sup>2</sup> Gilt nur für Geräte, die von Intune verwaltet werden.

## <a name="how-to-get-started"></a>Erste Schritte

Sie finden die meisten Informationen zu Apps in der Workload **Mobile Apps**, auf die Sie wie folgt zugreifen können:

1. Melden Sie sich beim Azure-Portal an.
2. Wählen Sie **Weitere Dienste** > **Überwachung und Verwaltung** > **Intune** aus.
3. Wählen Sie auf dem Blatt **Intune** die Option **Mobile Apps** aus.

    ![Workload „Mobile Apps“](./media/apps-workload.png)

### <a name="manage"></a>Verwalten von
- **Apps:** Mit diesem Knoten können Sie die meisten Apps hinzufügen, zuweisen und überwachen.
    - [Hinzufügen von Apps](apps-add.md)
    - [Zuweisen von Apps](apps-deploy.md)
    - [Überwachen von Apps](apps-monitor.md)
- **App-Konfigurationsrichtlinien:** Verwenden Sie App-Konfigurationsrichtlinien, um Einstellungen anzugeben, die beim Ausführen einer App durch den Benutzer erforderlich sein können.
    - [Richtlinien zur Konfiguration von iOS-Apps](app-configuration-policies-use-ios.md)
    - [Richtlinien zur Konfiguration von Android-Apps](app-configuration-policies-use-android.md)
- **App-Schutzrichtlinien:** Ermöglichen Ihnen das Zuordnen von Einstellungen für eine App zum Schutz der Unternehmensdaten, die diese verwendet. Sie können z.B. die Funktionen einer App zur Kommunikation mit anderen Apps einschränken oder erzwingen, dass der Benutzer eine PIN eingeben muss, um auf eine Unternehmens-App zuzugreifen.
    - [App-Schutzrichtlinien](app-protection-policies.md)
- **Selektive App-Zurücksetzung:** Entfernt nur Unternehmensdaten von einem Benutzergerät, das Sie auswählen.
    - [Selektive App-Zurücksetzung](apps-selective-wipe.md)
- **iOS-Bereitstellungsprofil:**: iOS-Apps enthalten ein Bereitstellungsprofil und Code, der von einem Zertifikat signiert ist. Wenn das Zertifikat abläuft, kann die App nicht mehr ausgeführt werden. Intune stellt Ihnen die Tools zum proaktiven Zuweisen einer neuen Richtlinie für Bereitstellungsprofile auf Geräten zur Verfügung, auf denen Apps installiert sind, die bald ablaufen.
    - [iOS-App-Bereitstellungsprofile](app-provisioning-profile-ios.md)

### <a name="monitor"></a>Überwachen
- **Lizenzierte Apps:** Ermöglicht das Anzeigen, Zuweisen und Überwachen von per Volumenlizenz in den App Stores erworbenen Apps.
    - [Per Volumenlizenz erworbene Apps aus dem Microsoft Store für Unternehmen](windows-store-for-business.md)
- **Erkannte Apps:** Zeigt alle Apps, die von Intune zugewiesen und auf einem Gerät installiert wurden.
- **App-Installationsstatus:** Zeigt den Status einer App-Zuweisung, die Sie erstellt haben.
- **App-Schutzstatus:** Zeigt den Status einer App-Schutzrichtlinie für einen ausgewählten Benutzer an.

Weitere Informationen finden Sie unter [Überwachen von Apps](apps-monitor.md).

### <a name="setup"></a>Setup
<!--- **iOS VPP Tokens**
    - [iOS volume-purchased apps](vpp-apps-ios.md) --->
- **Microsoft Store für Unternehmen:** Richten Sie die Integration in den Microsoft Store für Unternehmen ein. Anschließend können Sie erworbene Anwendungen mit Intune synchronisieren, sie zuweisen und Ihre Lizenznutzung verfolgen.
    - [Per Volumenlizenz erworbene Apps aus dem Microsoft Store für Unternehmen](windows-store-for-business.md)
- **Unternehmensportalbranding:** Passen Sie das Unternehmensportal mit Ihrem Unternehmensbranding an.
    - [Konfiguration des Unternehmensportals](company-portal-app.md)
