---
title: Verwenden von Richtlinien zum Vereinfachen der Verwaltung von Windows-PCs
description: "Beschreibt die Verwaltungsrichtlinien für Windows-PCs und die Einstellungen für das Microsoft Intune Center."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 12/15/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f0afda7e-f4c3-4bcd-b4bf-4304103cf73e
ms.reviewer: owenyen
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 9d67bf344be7a20853e21cf580939f1156d1a723
ms.sourcegitcommit: 1a54bdf22786aea1cf1b497d54024470e1024aeb
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/10/2017
---
# <a name="use-policies-to-simplify-windows-pc-management"></a>Verwenden von Richtlinien zum Vereinfachen der Verwaltung von Windows-PCs

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Um Windows-Desktops durch Ausführen des Intune-Softwareclients als PCs zu verwalten, können Sie nur die Richtlinien verwenden, die sich in der Intune-Verwaltungskonsole in den Richtlinien zur **Computerverwaltung** befinden. Alle anderen Richtlinien in der Verwaltungskonsole gelten nur für mobile Geräte. Mit den Richtlinien zur **Computerverwaltung** können Sie die Einstellungen im Microsoft Intune Center konfigurieren, Updates auf PCs steuern und die Windows-Firewall für PCs konfigurieren.

![Richtlinienvorlage für Windows-PCs](../media/pc_policy_template.png)

### <a name="manage-the-microsoft-intune-center"></a>Verwalten des Microsoft Intune Center
Benutzern wird der Intune-Softwareclient als das **Microsoft Intune Center** angezeigt. Das Microsoft Intune Center bietet Benutzern folgende Möglichkeiten:

-   Abrufen von Anwendungen aus dem Unternehmensportal

-   Suchen nach Updates

-   Verwalten von Microsoft Intune Endpoint Protection

-  Anfordern von Remoteunterstützung

Das Microsoft Intune Center ist auf allen verwalteten Computern installiert. Sie können die folgenden Einstellungen in einer Intune Center-Richtlinie konfigurieren, die anschließend Benutzern im Microsoft Intune Center angezeigt werden:

|Richtlinieneinstellung|Details|
|------------------|--------------------|
|**Name**|Name des Administrators, der den Computer verwaltet<br />Maximale Länge: 40 Zeichen|
|**Telefonnummer**|Telefonnummer des Administrators, der den Computer verwaltet<br />Maximale Länge: 20 Zeichen|
|**E-Mail-Adresse**|E-Mail-Adresse des Administrators, der den Computer verwaltet<br />Maximale Länge: 40 Zeichen|
|**Name der Website**|Name der Supportwebsite für Benutzer<br />>Maximale Länge: 40 Zeichen|
|**URL der Website**|URL der Supportwebsite<br />Maximale Länge: 150 Zeichen|
|**Anmerkungen**|Hinweis, der Benutzern angezeigt wird<br />Maximale Länge: 120 Zeichen|

Finden Sie Informationen zu Richtlinien und Einstellungen für Windows-PCs in den folgenden Ressourcen:

- [Aktualisieren Ihrer Windows-PCs mit Softwareupdates in Microsoft Intune](keep-windows-pcs-up-to-date-with-software-updates-in-microsoft-intune.md): Aufgrund dieser Richtlinien suchen verwaltete Computer nach Softwareupdates und laden diese von Microsoft und Drittanbietern herunter. Diese Updates enthalten keine Upgrades des Betriebssystems (d.h. keine Upgrades von Windows 7 auf Windows 10 oder von Windows 10 auf eine höhere Version).

- [Schützen von Windows-PCs mit Endpoint Protection für Microsoft Intune](help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune.md): Zu diesen Einstellungen gehören Überprüfungszeitpläne und zu ergreifende Maßnahmen, wenn Malware erkannt wird.

- [Unterstützen des Schutzes von Windows-PCs mithilfe von Windows-Firewall-Richtlinien in Microsoft Intune](help-protect-windows-pcs-using-windows-firewall-policies-in-microsoft-intune.md): Diese Richtlinien vereinfachen die Verwaltung von Windows-Firewalleinstellungen auf verwalteten Computern.


### <a name="see-also"></a>Weitere Informationen:

[Allgemeine Aufgaben zur Verwaltung von Windows-PCs mit dem Intune-Softwareclient](common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client.md)
