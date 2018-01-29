---
title: "Verwalten von Verknüpfungen zwischen Benutzern und Geräten für Windows-PCs"
description: "Verknüpfen eines Benutzers mit einem vom Intune verwalteten Windows-PC."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 12/15/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 53c99d63-c312-442a-8a71-de1b10fcd39b
ms.reviewer: owenyen
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 751355c34fc18cd9a1ededd498724d4652fc1368
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2018
---
# <a name="manage-user-device-linking-for-windows-pcs"></a>Verwalten von Verknüpfungen zwischen Benutzern und Geräten für Windows-PCs

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

Die Informationen in diesem Thema gelten nur für Windows-Desktops, die Sie als PCs mithilfe des Intune-Softwareclients verwalten. 

Damit Sie Software für einen Benutzer bereitstellen können, müssen Sie diesen zunächst mit einem PC verknüpfen. Sie können einen Benutzer mit mehreren PCs verknüpfen, aber einzelne PCs nur mit jeweils einem Benutzer. Benutzer werden automatisch mit den PCs verknüpft, die sie über das Unternehmensportal in Intune registrieren.

So verknüpfen Sie einen Benutzer mit einem PC

1. Wählen Sie in der [Microsoft Intune-Verwaltungskonsole](https://manage.microsoft.com/) die Option **Gruppen** &gt; **Alle Geräte** aus (oder eine andere Gruppe, in der der PC enthalten ist, den Sie mit einem Benutzer verknüpfen möchten).

2. Wählen Sie den PC aus, den Sie mit einem Benutzer verknüpfen möchten, und dann **Benutzer verknüpfen** aus.

   Im Dialogfeld **Benutzer verknüpfen** wird eine Liste verfügbarer Benutzer mit ihren Anzeigenamen, Benutzer-IDs und der Anzahl von PCs angezeigt, mit denen die Benutzer jeweils aktuell verknüpft sind. Wenn ein Benutzer bereits mit dem ausgewählten PC verknüpft ist, werden Name und Benutzer-ID des Benutzers unter **Aktueller Benutzer**angezeigt. Wenn der PC mit keinem Benutzer verknüpft ist, wird unter **Aktueller Benutzer** der Wert **Kein Benutzer**angezeigt.

3. Führen Sie eines der folgenden Verfahren aus:

   - Wählen Sie **Abbrechen** aus, um die Verknüpfung des PC mit einem ggf. vorhandenen aktuellen Benutzer beizubehalten.

   - Um den Link, um den aktuellen Benutzer zu entfernen, falls vorhanden, wählen Sie <strong>Verknüpfung entfernen **&gt; ** OK</strong>.

   - Zum Verknüpfen des PC mit einem neuen Benutzer wählen Sie diesen in der Liste **Alle Benutzer** aus. Überprüfen Sie, ob die Benutzerdaten korrekt sind, und wählen Sie **OK** aus.

> [!TIP]
> Wenn Sie die Fähigkeit der Endbenutzer, sich mit PCs zu verknüpfen, einschränken möchten, aktivieren Sie die Option **Fähigkeit der Benutzer einschränken, sich mit PCs zu verknüpfen** in der Richtlinie **-Microsoft Intune-Agent-Einstellungen**.

### <a name="see-also"></a>Siehe auch

[Allgemeine Aufgaben zur Verwaltung von Windows-PCs mit dem Intune-Softwareclient](common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client.md)