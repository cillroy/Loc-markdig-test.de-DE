---
title: "Überwachen der Kompatibilität mit bedingtem Zugriff bei Exchange lokal und Exchange Online"
titlesuffix: Azure portal
description: "Überwachen der Kompatibilität mit bedingtem Zugriff bei Exchange lokal und Exchange Online durch das Azure-Portal für Intune"
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 04/24/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5712682d-285b-43fd-9978-3dcfd95ec5f9
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: a3088f8d7ec43e122e8d296a01c0f6572744079f
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2018
---
# <a name="monitor-conditional-access-compliance-for-on-premises-exchange-and-exchange-online-in-intune"></a>Überwachen der Konformität mit bedingtem Zugriff für Exchange lokal und Exchange Online in Intune

Ab Version Intune 1704 können Administratoren Berichtsinformationen in Zusammenhang mit Exchange ActiveSync-Gerät-Geräteeinträgen sehen, die entweder über den lokalen Exchange-Connector oder dem Intune Service to Service Connector (Exchange Online-Connector) mit Intune synchronisiert werden. Berichte zur Kompatibilität mit bedingtem Zugriff enthalten eine Zusammenfassung der Geräte mit unterschiedlichen Synchronisierungsstatus:

-   **Zulassen**

-   **Blockieren**

-   **Quarantäne**

## <a name="to-monitor-conditional-access-compliance"></a>Überwachen der Kompatibilität mit bedingtem Zugriff

1.  Melden Sie sich im [Azure-Portal](https://portal.azure.com/) mit Ihren Intune-Anmeldeinformationen an.

2.  Sobald Sie erfolgreich angemeldet sind, wird das **Azure-Dashboard** angezeigt.

3.  Wählen Sie im linken Menü **Weitere Dienste** aus, und geben Sie in das Filtertextfeld die Zeichenfolge **Intune** ein.

4.  Wählen Sie **Intune** aus. Das **Intune-Dashboard** wird angezeigt.

5.  Wählen Sie **Bedingter Zugriff** und dann **Übersicht** aus.

6.  Wählen Sie im Diagramm einen der drei Bereiche (**Blockiert**, **Unter Quarantäne** oder **Zugelassen**) aus, um Ihre Berichte zur Kompatibilität mit bedingtem Zugriff anzuzeigen.

    ![Dashboard für den bedingten Zugriff](./media/CA-reporting-intune-1.png)

Nachdem Sie einen der drei Bereiche ausgewählt haben, können Sie weitere Details über zugelassene, blockierte oder unter Quarantäne gestellte Geräte sehen.

Sie können auch ein Drilldown auf bestimmte Geräte ausführen, um weitere Details anzuzeigen. Beispielsweise ist das in der nachfolgenden Abbildung ausgewählte Gerät blockiert. Intune bietet Ihnen die Möglichkeit, Unternehmensdaten auf dem Blatt zum Bericht zur Kompatibilität mit bedingtem Zugriff zu entfernen.

![Bericht mit Informationen zu Geräten mit bedingtem Zugriff](./media/CA-reporting-intune-3.png)

Auf dem Blatt mit den Gerätedetails finden Sie weitere Informationen:

-   **Übersicht:** Folgende Eigenschaften des Geräts werden angezeigt: Betriebssystemversion, Gerätemodell, Besitz, Seriennummer, Gerätehersteller, Telefonnummer und Zeitpunkt, an dem das Gerät zuletzt eingecheckt wurde.

-   **Eigenschaften:** Sie können den Gerätebesitz (privat oder Unternehmen) festlegen.

-   **Hardware:** Dieser Abschnitt enthält Informationen, die Sie in der Übersicht sehen, sowie Speicherdetails (gesamter und freier Speicherplatz), Systemgehäuse, Netzwerkdetails, Netzwerkdienst und weitere Details über Sperrungen des bedingten Zugriffs.

-   **Ermittelte Apps:** In diesem Abschnitt werden alle Programme angezeigt, die auf Ihrem Gerät installiert sind. Sie können die Liste der installierten Apps auch im .CSV-Format exportieren.

-   **Kompatibilität:** In diesem Abschnitt werden alle Details zu Richtlinien für die Gerätekompatibilität angezeigt.

-   **Gerätekonfiguration:** In diesem Abschnitt werden alle Details zur Gerätekonfiguration angezeigt.

-   **Exchange-Zugriff:** Hier finden Sie weitere Informationen über den Gerätestatus nach der Anwendung von Richtlinien für den bedingten Zugriff.
