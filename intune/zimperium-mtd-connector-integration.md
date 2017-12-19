---
title: Integrieren von Zimperium in Intune
titleSuffix: Intune on Azure
description: Integrieren von Intune in Zimperium
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 09/06/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 363fd280-1865-4a61-855b-eb75c3c62753
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 1b4adb2db14c2e1c83be8e7b3644944c1910cb97
ms.sourcegitcommit: d434dfab7ef7a6c4082d675717fa22d5581b4f51
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2017
---
# <a name="integrate-zimperium-with-intune"></a>Integrieren von Zimperium in Intune

Sie müssen die nachfolgenden Schritte befolgen, um die Zimperium Mobile Threat Defense-Lösung in Intune zu integrieren.

## <a name="before-you-begin"></a>Vorbereitung

> [!NOTE]
> Die folgenden Schritte müssen in der [Zimperium MTD-Konsole](https://staging2-console.zimperium.com) ausgeführt werden.

Stellen Sie vor der Integration von Zimperium in Intune sicher, dass Sie über Folgendes verfügen:

-   Microsoft Intune-Abonnement

-   Azure Active Directory-Administratoranmeldeinformationen zum Erteilen folgender Berechtigungen:

    -   Anmelden und Lesen des Benutzerprofils

    -   Zugriff auf das Verzeichnis als angemeldeter Benutzer

    -   Lesen der Verzeichnisdaten

    -   Senden von Geräteinformationen an Intune

-   Administratoranmeldeinformationen für den Zugriff auf die Zimperium MTD-Konsole

### <a name="zimperium-app-authorization"></a>Zimperium-App-Autorisierung

Der Autorisierungsprozess von Zimperium umfasst Folgendes:

-   Der Zimperium-Dienst darf Informationen zum Integritätszustand des Geräts an Intune übertragen.

-   Zimperium wird mit der Azure AD Enrollment Group-Mitgliedschaft synchronisiert, um die Datenbank des Geräts aufzufüllen.

-   Die Zimperium-Verwaltungskonsole darf Azure AD-SSO (Single Sign On) verwenden.

-   Die Zimperium-App darf für die Anmeldung Azure AD-SSO verwenden.

## <a name="to-set-up-zimperium-integration"></a>Einrichten der Zimperium Integration

1.  Wechseln Sie zur [Zimperium MTD-Konsole](https://staging2-console.zimperium.com), und melden Sie sich mit Ihren Anmeldeinformationen an.

2.  Wählen Sie im linken Menü **Verwaltung** aus.

3.  Wählen Sie die Registerkarte **MDM settings** (MDM-Einstellungen) aus.

4.  Wählen Sie **Add MDM** (MDM hinzufügen) aus, und wählen Sie dann **Microsoft Intune** aus der Liste der **MDM-Anbieter** aus.

5.  Sobald Sie Microsoft Intune als MDM-Dienst festgelegt haben, öffnet sich das Fenster zur **Microsoft Intune-Konfiguration**. Wählen Sie **Azure Active Directory hinzufügen** für jede Option aus: **iOS- und Android-Apps Zimperium zConsole** und **zIPS** zur Autorisierung von Zimperium für die Kommunikation mit Intune und Azure AD über Azure AD-SSO.

    > [!IMPORTANT]
    > Sie müssen die iOS- und Android-Apps Zimperium zConsole und zIPS hinzufügen, um den Integrationsvorgang in Intune abzuschließen.

6.  Wählen Sie **Annehmen** aus, um die Zimperium-App für die Kommunikation mit Intune und Azure Active Directory zu autorisieren.

7.  Nachdem Sie die **iOS- und Android-Apps Zimperium zConsole** und **zIPS** zu Azure AD hinzugefügt haben, müssen Sie die Azure AD-Sicherheitsgruppen hinzufügen, sodass Zimperium die Azure AD-Sicherheitsgruppe mit seinem Dienst synchronisieren kann.

8.  Wählen Sie **Fertig stellen** aus, um die Konfiguration zu speichern und die erste Azure AD-Sicherheitsgruppensynchronisierung zu starten.

## <a name="next-steps"></a>Nächste Schritte

-   [Einrichten von Zimperium-Apps](mtd-apps-ios-app-configuration-policy-add-assign.md)
