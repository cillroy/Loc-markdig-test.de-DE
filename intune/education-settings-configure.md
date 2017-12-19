---
title: "Konfigurieren der Intune-Einstellungen für Bildungseinrichtungen für Windows 10"
titleSuffix: Azure portal
description: "In diesem Artikel erfahren Sie, wie Sie mit Intune Einstellungen für Windows 10 Education auf Geräten konfigurieren, die Sie verwalten."
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 09/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6f4de4bd-3dde-4a8d-8e22-46c5d06c3eea
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 12e36761320557f6af9554d3b671fc133253c13c
ms.sourcegitcommit: 769db6599d5eb0e2cca537d0f60a5df9c9f05079
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2017
---
# <a name="how-to-configure-windows-10-education-settings-in-microsoft-intune"></a>Konfigurieren von Einstellungen für Bildungseinrichtungen für Windows 10 in Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Mit Education-Profilen können Sie Details für die Konfiguration der Windows Take a Test-App einschließlich Kontodetails und die Test-URL angeben. Wenn Sie diese Konfiguration vornehmen, öffnet sich die Take a Test-App mit dem angegebenen Test, und auf dem Gerät können keine anderen Apps ausgeführt werden, bevor der Test abgeschlossen ist.

Informationen zur „Take a Test“-App finden Sie unter [Durchführen von Prüfungen in Windows 10](https://docs.microsoft.com/education/windows/take-tests-in-windows-10).

## <a name="create-a-device-profile-containing-education-profile-settings"></a>Erstellen eines Geräteprofils mit Education-Profileinstellungen

1. Melden Sie sich beim Azure-Portal an.
2. Wählen Sie **Weitere Dienste** > **Überwachung und Verwaltung** > **Intune** aus.
3. Wählen Sie auf dem Blatt **Intune** die Option **Gerätekonfiguration** aus.
2. Wählen Sie auf dem Blatt **Gerätekonfiguration** die Option **Verwalten** > **Profile** aus.
3. Wählen Sie auf dem Blatt „Profile“ die Option **Profil erstellen** aus.
4. Geben Sie auf dem Blatt **Profil erstellen** einen **Namen** und eine **Beschreibung** für das Geräteeinschränkungsprofil ein.
5. Wählen Sie in der Dropdownliste **Plattform** die Option **Windows 10 und höher** aus.
6. Wählen Sie in der Dropdownliste **Profiltyp** die Option **Education-Profil** aus. 
7. Wählen Sie „Einstellungen“ > „Konfigurieren“ aus, und konfigurieren Sie auf dem Blatt **Prüfung** Folgendes:
    - **Kontobenutzername** – Geben Sie den Benutzernamen des Kontos ein, das mit Take a Test verwendet wird. Dies kann ein Domänenkonto, ein Azure Active Directory (AAD)-Konto oder ein lokales Computerkonto sein.
    - **Bewertungs-URL** – Geben Sie die URL des Tests an, den Benutzer ausführen sollen. Weitere Informationen finden Sie in der Take a Test-Dokumentation.
    - **Bildschirmaufnahme** – Geben Sie an, ob sie die Bildschirmaktivität aufnehmen möchten, während Benutzer einen Test ausführen.
    - **Textvorschlag** – Lassen Sie Textvorschläge zu oder blockieren sie diese, während Benutzer einen Test ausführen.
8. Navigieren Sie anschließend zurück zum Blatt **Profil erstellen**, und klicken Sie auf **Erstellen**.

Das Profil wird erstellt und auf dem Blatt mit der Profilliste angezeigt.

## <a name="next-steps"></a>Nächste Schritte

Wenn Sie fortfahren und dieses Profil Gruppen zuweisen möchten, lesen Sie unter [Zuweisen von Geräteprofilen](device-profile-assign.md) nach.



