---
title: Aktivieren von Windows Defender | Microsoft-Dokumentation
description: Erfahren Sie, wie Windows Defender aktiviert wird, um auf Unternehmensressourcen zuzugreifen.
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 11/08/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d16dd2de-3ed5-474f-a04b-36dcd350162c
searchScope: User help
ROBOTS: 
ms.reviewer: shburbid
ms.suite: ems
ms.custom: intune-enduser
ms.openlocfilehash: 06471a8d929dc2708917d4860510ba5cbab10fb1
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2017
---
# <a name="turn-on-windows-defender-to-access-company-resources"></a>Aktivieren von Windows Defender zum Zugriff auf Unternehmensressourcen

Ihr Arbeitgeber oder Ihre Schule möchte sicherstellen, dass Geräte, die auf ihre Ressourcen zugreifen, gesichert sind. Dabei können sie in verschiedener Weise von [Windows Defender](https://www.microsoft.com/safety/pc-security/windows-defender.aspx), dem in Windows integrierten Schutz vor Schadsoftware, Gebrauch machen.

Es gibt einige Einstellungen in Ihrem Windows Defender, die Sie möglicherweise ändern müssen, um Zugriffsprobleme zu beheben. Für diese Schritte kann es erforderlich sein, dass Sie verschiedene Orte auf Ihrem Computer aufsuchen.

## <a name="turn-on-windows-defender"></a>Aktivieren von Windows Defender

1. Öffnen Sie im Menü **Start** die **Systemsteuerung**.
2. Öffnen Sie **Verwaltung** > **Gruppenrichtlinie bearbeiten**. Dadurch wird der **Editor für lokale Gruppenrichtlinien** in einem neuen Fenster geöffnet.
3. Öffnen Sie **Computerkonfiguration** > **Administrative Vorlagen** > **Windows-Komponenten** > **Windows Defender Antivirus**. Die Einstellung **Windows Defender Antivirus deaktivieren** befindet sich unterhalb der Ordner für andere Einstellungen. 
4. Öffnen Sie **Windows Defender Antivirus deaktivieren**, und vergewissern Sie sich, dass die Einstellung auf **Deaktiviert** oder **Nicht konfiguriert** festgelegt ist.

## <a name="turn-on-real-time-protection"></a>Aktivieren von Echtzeitschutz

Vergewissern Sie sich, dass der Echtzeitschutz aktiviert ist, indem Sie zu **Start** gehen und nach **Windows Defender Security Center** suchen. Wählen Sie **Einstellungen für Viren- & Bedrohungsschutz** aus, und überprüfen Sie, ob sowohl **Echtzeitschutz** als auch **Cloudbasierter Schutz** auf **Ein** festgelegt sind. Wenn diese Optionen nicht angezeigt werden, gehen Sie wie folgt vor, um sie zu aktivieren:

1. Öffnen Sie im Menü **Start** die **Systemsteuerung**.
2. Öffnen Sie **Verwaltung** > **Gruppenrichtlinie bearbeiten**. Dadurch wird der **Editor für lokale Gruppenrichtlinien** in einem neuen Fenster geöffnet.
3. Öffnen Sie **Computerkonfiguration** > **Administrative Vorlagen** > **Windows-Komponenten** > **Windows Defender Security Center** > **Viren- & Bedrohungsschutz**.
4. Öffnen Sie die Einstellung **Viren- und Bedrohungsschutzbereich**, und legen Sie sie auf **Deaktiviert** fest.

## <a name="update-your-antivirus-definitions"></a>Aktualisieren Sie Ihre Virusdefinitionen

Vergewissern Sie sich, dass Ihre Virendefinitionen auf dem aktuellen Stand sind, indem Sie zu **Start** gehen und nach **Windows Defender Security Center** suchen. Wählen Sie **Schutzupdates** und **Nach Updates suchen** aus, um sicherzustellen, dass Ihr Gerät über aktuellen Schutz gegen Viren verfügt. Wenn diese Option nicht angezeigt wird, führen Sie die unter [Aktivieren von Echtzeitschutz](turn-on-defender-windows.md#turn-on-real-time-protection) beschriebenen Schritte aus.

Benötigen Sie weitere Unterstützung? Kontaktieren Sie den Support Ihres Unternehmens. Die entsprechenden Kontaktinformationen finden Sie auf der [Unternehmensportal-Website](https://portal.manage.microsoft.com#HelpDeskDialog).
