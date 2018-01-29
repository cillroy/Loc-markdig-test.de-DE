---
title: "Vorbereitungen zum Konfigurieren von App-Schutzrichtlinien für Windows 10"
titlesuffix: Azure portal
description: Einrichten des MAM-Anbieters (Mobile Application Management) in Azure AD
keywords: 
author: erikre
ms.author: erikre
manager: angrobe
ms.date: 10/25/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 949fddec-5318-4c9a-957e-ea260e6e05be
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: c30718b2237ee246344cbaf7acc89ffb19fe6767
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2018
---
# <a name="get-ready-to-configure-app-protection-policies-for-windows-10"></a>Vorbereitungen zum Konfigurieren von App-Schutzrichtlinien für Windows 10

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Aktivieren Sie die Verwaltung für mobile Anwendungen (Mobile Application Management, MAM) für Windows 10, indem Sie den MAM-Anbieter in Azure AD festlegen. Durch die Festlegung eines MAM-Anbieters in Azure AD können Sie den Registrierungsstatus definieren, wenn Sie eine neue WIP-Richtlinie (Windows Information Protection) in Intune erstellen. Der Registrierungsstatus kann entweder „MAM“ oder „Mobile Geräteverwaltung (MDM)“ lauten.

> [!NOTE]
> Geräte mit einem MAM-Registrierungsstatus müssen mit Azure AD verknüpft sein.

## <a name="to-configure-the-mam-provider"></a>Konfigurieren des MAM-Anbieters

1. Melden Sie sich beim Azure-Portal an, und klicken Sie auf **Azure Active Directory**.

2. Wählen Sie **Mobilität (MDM und MAM)** in der Gruppe **Verwalten** aus.

3. Klicken Sie auf **Microsoft Intune**.

4. Konfigurieren Sie die Einstellungen in der Gruppe **Standard-MAM-URLs wiederherstellen** auf dem Blatt **Konfigurieren**.

    **MAM-Benutzerbereich**  
      Verwenden Sie die automatische Registrierung von MAM, um Unternehmensdaten auf den Windows-Geräten Ihrer Mitarbeiter zu verwalten. Die automatische MAM-Registrierung wird für BYOD-Szenarios konfiguriert.<ul><li>**Keine**<br>Wählen Sie diese Option, wenn alle Benutzer in MAM registriert werden können.</li><li>**Einige**<br>Wählen Sie Azure AD-Gruppen aus, die Benutzer enthalten, die in MAM registriert werden.</li><li>**Alle**<br>Wählen Sie diese Option, wenn alle Benutzer in MAM registriert werden können.</li></ul>

    **URL für MDM-Nutzungsbedingungen**  
     Die URL zum Endpunkt für die Nutzungsbedingungen des MAM-Diensts. Der Endpunkt für die Nutzungsbedingungen wird verwendet, um die Nutzungsbedingungen Endbenutzern anzuzeigen, bevor diese ihre Geräte für die Verwaltung registrieren. Im Text der Nutzungsbedingungen werden Benutzer über die auf dem mobilen Gerät erzwungenen Richtlinien informiert.

    **URL für MDM-Ermittlung**  
    Die URL des Endpunkt der Registrierung des MAM-Diensts. Der Registrierungsendpunkt wird zum Registrieren von Geräten für die Verwaltung mit dem MAM-Dienst verwendet.

    **URL für MAM-Kompatibilität**  
      Die URL des Kompatibilitätsendpunkts des MAM-Diensts. Wenn einem Benutzer der Zugriff auf eine Ressource von einem nicht-kompatiblen Gerät aus verweigert wird, wird dem Benutzer ein Link zur Kompatibilitäts-URL angezeigt. Benutzer können zu dieser URL navigieren, die vom MAM-Dienst gehostet wird, um zu verstehen, warum Ihr Gerät als nicht kompatibel eingestuft ist. Benutzer können ebenso eine eigenständige Wartung durchführen, damit ihr Gerät kompatibel wird und sie damit fortfahren können, auf Ressourcen zuzugreifen.

5.  Klicken Sie auf **Speichern**.

## <a name="next-steps"></a>Nächste Schritte

[Erstellen einer WIP-App-Schutzrichtlinie](windows-information-protection-policy-create.md)
