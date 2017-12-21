---
title: "Mehrstufige Authentifizierung für Intune-Geräteregistrierungen"
titlesuffix: Azure portal
description: "Anfordern der mehrstufigen Authentifizierung in Azure AD für die Geräteregistrierung."
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 10/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 94280c73-c05c-4e72-b0dd-a7cb997782f9
ROBOTS: 
ms.custom: intune-azure
ms.openlocfilehash: a3aabe77257fd7e6964dd7bd83035c8a491a58b4
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2017
---
# <a name="multi-factor-authentication-for-intune-device-enrollments"></a>Multi-Factor Authentication für Intune-Geräteregistrierungen

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Intune kann die mehrstufige Authentifizierung (MFA) von Azure AD für die Geräteregistrierung verwenden, damit Sie Ihre Unternehmensressourcen sichern können.

MFA funktioniert, da zwei oder mehr der folgenden Überprüfungsmethoden erforderlich sind:

- Etwas, das Sie kennen (normalerweise ein Kennwort oder eine PIN)
- Etwas, das Sie besitzen (ein vertrauenswürdiges Gerät, das nicht auf einfache Weise dupliziert werden kann, z.B. ein Telefon)
- Etwas Biometrisches (z.B. ein Fingerabdruck)

MFA wird für iOS-, Android-, Windows 8.1-Geräte oder höher und Windows Phone 8.1-Geräte oder mobile Windows 10-Geräte oder höher unterstützt.

Wenn Sie MFA aktivieren, müssen Benutzer zwei Formen von Anmeldeinformationen angeben, um ein Gerät zu registrieren.

## <a name="configure-intune-to-require-multi-factor-authentication-at-device-enrollment"></a>Konfigurieren von Intune für das Anfordern der mehrstufigen Authentifizierung bei der Geräteregistrierung

Befolgen Sie die folgenden Schritte, um MFA anzufordern, wenn ein Gerät registriert wird:

>[!Important]
>Konfigurieren Sie keine **gerätebasierten Zugriffsregeln** für die Microsoft Intune-Registrierung.

1. Melden Sie sich mit Ihren Anmeldeinformationen beim [Microsoft Azure-Portal](https://portal.azure.com) an.
2. Wählen Sie im Portal **Azure Active Directory** aus.
2. Wählen Sie in **Azure Active Directory** **Verwalten** > **Unternehmensanwendungen** aus.
3. Wählen Sie unter **Unternehmensanwendungen** die Optionen **Verwalten** > **Alle Anwendungen** aus. Daraufhin sehen Sie eine Liste aller Azure-Apps, die Sie verwalten.
3. Wählen Sie aus dieser Liste **Microsoft Intune enrollment** (Microsoft Intune-Registrierung) aus.
4. Wählen Sie unter **Microsoft Intune-Registrierung** die Optionen **Sicherheit** > **Bedingter Zugriff** aus.
5. Wählen Sie **Neue Richtlinie** aus.
6. Geben Sie unter **Neue Richtlinie** einen beschreibenden Namen für die Richtlinie ein.
7. Wählen Sie im Abschnitt **Zuweisungen** die Option **Benutzer und Gruppen** aus.
8. Wählen Sie unter **Benutzer und Gruppen** die Benutzer oder Gruppen aus, die diese Richtlinie empfangen sollen, und klicken Sie dann auf **Fertig**.
9. Wählen Sie im Abschnitt **Zuweisungen** die Option **Cloud-Apps** aus.
10. Wählen Sie auf der Registerkarte **Einbeziehen** von **Cloud-Apps** die Option **Apps auswählen** aus, klicken Sie dann auf **Auswählen** > **Microsoft Intune-Registrierung**, und klicken Sie dann auf **Fertig**.
11. Wählen Sie im Abschnitt **Zuweisungen** die Option **Bedingungen** aus.
12. Sie müssen unter **Bedingungen** keine Einstellungen für MFA konfigurieren.
13. Wählen Sie im Abschnitt **Zugriffssteuerung** die Option **Erteilen** aus.
14. Wählen Sie unter **Erteilen** die Option **Zugriff gewähren** aus, und wählen Sie dann **Mehrstufige Authentifizierung anfordern** aus.
    Wählen Sie nicht **Markieren des Geräts als kompatibel erforderlich** aus, da ein Gerät vor der Registrierung nicht auf Kompatibilität geprüft werden kann.
15. Klicken Sie auf **Auswählen**.
16. Wählen Sie unter **Neue Richtlinie** die Optionen **Richtlinie aktivieren** > **An** aus, und klicken Sie dann auf **Erstellen**.



## <a name="next-steps"></a>Nächste Schritte

Wenn Benutzer ihre Geräte registrieren, müssen Sie sich jetzt mit einer zweiten Identifikationsart, z.B. mit einer PIN, einer Telefonnummer oder mit biometrischen Daten authentifizieren.
