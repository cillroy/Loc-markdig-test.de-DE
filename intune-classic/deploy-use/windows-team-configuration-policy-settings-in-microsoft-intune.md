---
title: "Einstellungen für Windows Team-Konfigurationsrichtlinie"
description: "Verwenden Sie die **allgemeine Windows 10 Team-Konfigurationsrichtlinie** von Microsoft Intune, um Einstellungen für registrierte Windows 10 Team-Geräte (z. B. Microsoft Surface Hub) zu konfigurieren."
keywords: 
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 12/27/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 38194ef3-e26e-4682-958d-14b395fccba1
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: bc7b2ea782fb6e8b29815192a3401cd00a02f781
ms.sourcegitcommit: e37e916e2bf14f092d3a767bc90d68c181d739fb
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/03/2018
---
# <a name="windows-team-configuration-policy-settings-in-microsoft-intune"></a>Einstellungen für Windows Team-Konfigurationsrichtlinie in Microsoft Intune

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Verwenden Sie die **allgemeine Windows 10 Team-Konfigurationsrichtlinie** von Microsoft Intune, um Einstellungen für registrierte Windows 10 Team-Geräte (z. B. Microsoft Surface Hub) zu konfigurieren.


|Name der Einstellung|Details|
|----------------|-----------|
|**Zulassen der automatischen Aktivierung des Bildschirms, wenn Sensoren eine Person im Raum feststellen**|Ermöglicht das automatische Aktivieren des Geräts, wenn der Sensor eine Person im Raum erkennt.|
|**PIN für Funkprojektion anfordern**|Gibt an, ob Sie eine PIN eingeben müssen, bevor Sie die drahtlosen Projektionsfunktionen des Geräts verwenden können.|
|**Wartungsfenster für Geräteupdates festlegen**|Konfiguriert das Fenster, in dem Updates am Gerät vorgenommen werden können. Sie können die Startzeit und Länge des Fensters (1 bis 5 Stunden) konfigurieren.|
|**Azure Operational Insights aktivieren**|Azure Operational Insights ist Teil der Microsoft Operations Manager-Suite und sammelt, speichert und analysiert Protokolldaten von Windows 10-Teamgeräten.<br /><br />Sie müssen eine **Arbeitsbereichs-ID** und einen **Arbeitsbereichsschlüssel** angeben, um die Verbindung mit Azure Operational Insights herstellen zu können.|
|**Miracast-Funkprojektion aktivieren**|Aktivieren Sie diese Option, wenn Sie es dem Windows 10-Teamgerät ermöglichen möchten, für Miracast aktivierte Geräte zum Projizieren zu verwenden.<br /><br />Wenn Sie diese Option aktivieren, wählen Sie unter **Miracast-Kanal auswählen** den Miracast-Kanal aus, der zum Projizieren von Inhalten verwendet wurde.|
|**Im Willkommensbildschirm angezeigte Besprechungsinformationen auswählen**|Wenn Sie diese Option aktivieren, können Sie die Informationen auswählen, die auf der Kachel **Besprechungen** des Bildschirms **Willkommen** angezeigt werden. Sie können:<br /><br />-   **Nur Organisator und Zeit anzeigen**<br />-   **Organisator, Zeit und Thema anzeigen (Thema bei privaten Besprechungen ausblenden)**|
|**URL zum Bild für den Sperrbildschirmhintergrund**|Aktivieren Sie diese Einstellung, um auf dem **Willkommensbildschirm** von Windows 10 Team-Geräten einen benutzerdefinierten Hintergrund aus der angegebenen URL anzuzeigen.<br /><br />Das Bild muss im PNG-Format vorliegen und die URL muss mit **https://** beginnen.|


### <a name="see-also"></a>Siehe auch
[Verwalten von Einstellungen und Features auf Ihren Geräten mit Microsoft Intune-Richtlinien](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)

