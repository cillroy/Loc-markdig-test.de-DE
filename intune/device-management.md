---
title: "Verwalten von Geräten mit Intune"
titleSuffix: Intune on Azure
description: "In diesem Artikel erfahren Sie, wie Sie die mit Intune verwalteten Geräte anzeigen und verschiedene Vorgänge auf diesen ausführen."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 08/31/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d2412418-d91a-4767-a3d6-bc88bb29caa2
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 941a7d17a672f9315d1d99812494650f8247b4c1
ms.sourcegitcommit: e37e916e2bf14f092d3a767bc90d68c181d739fb
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/03/2018
---
# <a name="what-is-microsoft-intune-device-management"></a>Was ist die Microsoft Intune Geräteverwaltung?


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Als IT-Administrator müssen Sie sicherstellen, dass verwaltete Geräte die Ressourcen bereitstellen, die Ihre Endbenutzer für Ihre Arbeit benötigen, während gleichzeitig die Daten vor Risiken geschützt werden.

Die Workload **Geräte** liefert Informationen zu den verwalteten Geräten und ermöglicht die Ausführung von Remoteaufgaben auf diesen Geräten. So greifen Sie auf die Workload zu

1. Melden Sie sich beim Azure-Portal an.
2. Wählen Sie **Weitere Dienste** > **Überwachung und Verwaltung** > **Intune** aus.
3. Wählen Sie in **Intune** die Option **Geräte** aus.
4. Sie können Informationen über Geräte anzeigen und die folgenden Remotegeräteaktionen durchführen:
   - **Übersicht**: Eine Momentaufnahme der registrierten Geräte, die Sie verwalten können.
   - **Alle Geräte**: Eine Liste der registrierten Geräte, die Sie verwalten. Wählen Sie **Filter** oder **Spalten** aus, um die angezeigten Informationen einzuschränken. Wählen Sie ein Gerät aus, um den [Gerätebestand](device-inventory.md) anzuzeigen.
   - **Azure AD-Geräte**: Eine Liste der Geräte, die in Azure Active Directory (AD) registriert oder damit verbunden sind. Weitere Informationen zur [Azure AD-Geräteverwaltung](https://docs.microsoft.com/azure/active-directory/device-management-introduction).
   - **Geräteaktionen**: Ein Verlauf der Remoteaktionen, die auf Geräten ausgeführt wurden, einschließlich die Aktion, der Status, wer die Aktion initiiert hat und der Zeitpunkt.

     ![Überwachen von Geräteaktionen](./media/monitor-device-actions.png)

   - **TeamViewer**: Über den TeamViewer-Dienst können Benutzer von mit Intune verwalteten Android-Geräten Remoteunterstützung von ihrem IT-Administrator erhalten. Erfahren Sie mehr über [TeamViewer](device-profile-android-teamviewer.md).

## <a name="available-device-actions"></a>Verfügbare Geräteaktionen
Die verfügbaren Aktionen hängen von der Geräteplattform und der Konfiguration des Geräts ab.

- [Anzeigen des Gerätebestands](device-inventory.md)
- So führen Sie Remotegeräteaktionen durch:
    - [Unternehmensdaten entfernen](devices-wipe.md#remove-company-data)
    - [Zurücksetzen auf Werkseinstellungen](devices-wipe.md#factory-reset)
    - [Remotesperre](device-remote-lock.md)
    - [Kennung zurücksetzen](device-passcode-reset.md)
    - [Umgehen der Aktivierungssperre](device-activation-lock-bypass.md) (nur iOS)
    - [Sauberer Start](device-fresh-start.md) (nur Windows)
    - [Modus für verlorene Geräte](device-lost-mode.md) (nur iOS)
    - [Gerät suchen](device-locate.md) (nur iOS)
    - [Neu starten](device-restart.md) (nur Windows)
    - [Zurücksetzen der PIN unter Windows 10](device-windows-pin-reset.md)
    - [Remotesteuerung für Android](device-profile-android-teamviewer.md)
    - [Synchronisieren von Geräten](device-sync.md)


## <a name="next-steps"></a>Nächste Schritte

- Wählen Sie **Geräteaktionen** aus, um den Status von Aktionen auf von Ihnen verwalteten Geräten anzuzeigen.
