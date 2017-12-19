---
title: "Anzeigen des Hardware- und Softwarebestands für Windows-PCs"
description: Anzeigen von Hardware- und Softwareinformationen zu Windows-Desktops, die Sie mithilfe des Intune-Softwareclients als PCs verwalten.
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 12/15/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3c10f4c9-520b-4864-92fc-a45a9f640ad4
ms.reviewer: owenyen
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: d985da553637e684f4773848fa8832e4aadd1775
ms.sourcegitcommit: 1a54bdf22786aea1cf1b497d54024470e1024aeb
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/10/2017
---
# <a name="view-hardware-and-software-inventory-for-windows-pcs"></a>Anzeigen des Hardware- und Softwarebestands für Windows-PCs

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

Intune sammelt detaillierte Informationen zur Hardware und Software von Desktops, die Sie mithilfe des Intune-Softwareclients als PCs verwalten. In den nachfolgend beschriebenen Verfahren lernen Sie Folgendes:

-   Erstellen eines Berichts, der Informationen zu den Hardwarefunktionen der von Ihnen verwalteten PCs auflistet

-   Erstellen eines Berichts, der die auf den jeweiligen PCs installierte Software auflistet

-   Aktualisieren des Inventars eines PCs, um sicherzustellen, dass die Daten im Bericht aktuell sind

## <a name="to-display-information-about-pcs-you-manage"></a>Anzeigen von Informationen zu den von Ihnen verwalteten PCs

1.  Wählen Sie in der [Microsoft Intune-Verwaltungskonsole](https://manage.microsoft.com/) die Option **Berichte** &gt; **Computerinventurberichte** aus.

2.  Übernehmen Sie auf der Seite **Neuen Bericht erstellen** die Vorgaben, oder passen Sie sie an, um die im Bericht zurückgegebenen Ergebnisse zu filtern. Sie können beispielsweise auswählen, dass nur PCs im Bericht angezeigt werden, auf denen Windows 8.1 ausgeführt wird.

3.  Wählen Sie **Bericht anzeigen** aus, um den **Computerinventurbericht** in einem neuen Fenster anzuzeigen.

    Sie können den Bericht durch Auswählen der entsprechenden Spaltenüberschrift nach jeder Spalte sortieren, z. B. **Name**, **Gehäusetyp** oder **Hersteller**.

## <a name="to-display-software-installed-on-pcs-you-manage"></a>Anzeigen der auf den von Ihnen verwalteten PCs installierten Software

1.  Wählen Sie in der [Microsoft Intune-Verwaltungskonsole](https://manage.microsoft.com/) die Option **Berichte** &gt; **Berichte zu ermittelter Software** aus.

2.  Übernehmen Sie auf der Seite **Neuen Bericht erstellen** die Vorgaben, oder passen Sie sie an, um die im Bericht zurückgegebenen Ergebnisse zu filtern. Sie können beispielsweise auswählen, dass nur von Microsoft herausgegebene Software im Bericht angezeigt wird.

3.  Wählen Sie **Bericht anzeigen** aus, um den **Bericht zu ermittelter Software** in einem neuen Fenster anzuzeigen.

    Sie können den Bericht durch Auswählen der entsprechenden Spaltenüberschrift nach jeder Spalte sortieren, z. B. **Name**, **Herausgeber** oder **Kategorie**. Durch Auswahl des Richtungspfeils neben dem Listenelement können Sie die Updates in der Liste erweitern, um weitere Details anzuzeigen (zum Beispiel die PCs, auf denen ein Update installiert ist).

## <a name="to-refresh-computer-inventory-to-ensure-it-is-current"></a>So aktualisieren Sie das Computerinventar, um sicherzustellen, dass es aktuell ist

1.  Wählen Sie in der [Microsoft Intune-Verwaltungskonsole](https://manage.microsoft.com/) die Option **Gruppen** &gt; **Alle Geräte** aus (oder eine andere Gruppe, die den PC enthält, für den Sie das Inventar aktualisieren möchten).

2.  Wählen Sie einen PC aus, oder halten Sie die **STRG**-Taste gedrückt, um mehrere Computer auszuwählen.

3.  Wählen Sie auf der Taskleiste **Remoteaufgaben** &gt; **Inventar aktualisieren** aus.

4.  Zur Anzeige des Aufgabenstatus wählen Sie **Remoteaufgaben** unten rechts auf der Seite aus.

    Im Dialogfeld **Taskstatus** werden aktuelle Remoteaufgaben, ihr Status, der Gerätename und etwaige gemeldete Fehler mit einem Link zu Problembehandlungsinformationen aufgelistet.

### <a name="see-also"></a>Weitere Informationen:

[Allgemeine Aufgaben zur Verwaltung von Windows-PCs mit dem Intune-Softwareclient](common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client.md)