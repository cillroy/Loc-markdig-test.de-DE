---
title: "Anzeigen des Intune-Gerätebestands"
titlesuffix: Azure portal
description: "Erfahren Sie, wie Sie die von Ihnen über Intune verwalteten Geräte sowie Informationen zu der entsprechenden Hardware und den installierten Apps anzeigen.\""
keywords: 
author: arob98
ms.author: angrobe
nmanager: angrobe
ms.date: 11/10/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e71c6bdb-d75c-404f-8e38-24a663be81c2
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: a910c99454b9c8a7922af3368453feab94803501
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2018
---
# <a name="how-to-view-intune-device-inventory"></a>So zeigen Sie den Intune-Gerätebestand an


[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Die Workload **Geräte** bietet Einblicke in die von Ihnen verwalteten Geräte, einschließlich Informationen zu Hardwarefunktionen und den auf den Geräten installierten Apps. 

So zeigen Sie den Gerätebestand an:

1. Melden Sie sich beim Azure-Portal an.
2. Wählen Sie **Weitere Dienste** > **Überwachung und Verwaltung** > **Intune** aus.
3. Wählen Sie auf dem Blatt **Intune** die Option **Geräte** aus.

Wählen Sie nun eine der folgenden Optionen aus:

- **Übersicht:** Erhalten Sie Informationen zu Geräten, die Sie registriert haben, und zu den Betriebssystemen der einzelnen Geräte.
- **Verwalten:** Wählen Sie **Alle Geräte** aus, um eine Liste aller von Ihnen verwalteten Geräte anzuzeigen.
    Wählen Sie eines dieser Geräte in der Liste aus, um das Blatt **Übersicht über** <*Gerätename*>  zu öffnen, auf dem Sie eine der folgenden Optionen auswählen können:
    - **Übersicht:** Hier finden Sie allgemeine Informationen über das Gerät, einschließlich den Namen, den Besitzer, ob es ein BYOD-Gerät ist, wann es zuletzt eingecheckt wurde u.v.m.
    - **Hardware:** Hier finden Sie ausführliche Informationen über das Gerät, einschließlich dessen freien Speicherplatzes, des Modells und Herstellers usw.
    - **Ermittelte Apps:** Zeigt eine Liste aller auf dem Gerät installierten Apps an, die von Intune gefunden wurden.
    - **Gerätekompatibilität:** Zeigt den Kompatibilitätszustand aller Kompatibilitätsrichtlinien an, die dem Gerät zugewiesen wurden.
    - **Gerätekonfiguration:** Zeigt den Kompatibilitätszustand aller Konfigurationsrichtlinien an, die dem Gerät zugewiesen wurden.
- **Monitor:** Wählen Sie **Geräteaktionen** aus, um eine Liste der Geräteaktionen, die auf Geräten, die Sie verwalten, ausgeführt wurden, und deren aktuellen Status anzuzeigen.
- **Setup** > **TeamViewer-Connector:** Ermöglicht Ihnen die Konfiguration der Remoteverwaltung auf Geräten mithilfe der Software TeamViewer. Weitere Informationen finden Sie unter [Bereitstellen von Remoteunterstützung für mit Intune verwaltete Android-Geräte](/intune/device-profile-android-teamviewer).

Intune sammelt nur auf unternehmenseigenen Geräten App-Inventar. Apps sind auf persönlichen Geräten nicht inventarisiert. Für Windows 10 PCs wird nur Inventar von modernen Apps auf unternehmenseigenen Geräten gesammelt. Intune sammelt keine Informationen über Win32-Apps auf dem Gerät. Je nach Netzbetreiber, den Sie mit dem Gerät verwenden, werden nicht alle Inventarelemente gesammelt.
