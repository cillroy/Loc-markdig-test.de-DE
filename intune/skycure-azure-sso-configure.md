---
title: "Konfigurieren von Skycure für die Verwendung des einmaligen Anmeldens von Azure AD mit Intune"
titlesuffix: Azure portal
description: "Konfigurieren von Skycure für die Verwendung des einmaligen Anmeldens von Azure AD mit Intune"
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 06/09/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e0466ac4-4942-4c4c-b8af-996b597c701d
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 93e7f1a21c9badb3cc3ccdf02432267b271e6e94
ms.sourcegitcommit: e10dfc9c123401fabaaf5b487d459826c1510eae
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/09/2017
---
# <a name="configure-skycure-to-use-azure-active-directory-single-sign-on-sso"></a>Skycure für die Verwendung von Azure Active Directory Single Sign-On (SSO) konfigurieren

Azure AD-SSO wird verwendet, wenn Sie Intune mit Skycure integrieren. Dies sind die wichtigsten Vorteile:

-   **Administratoren** können dieselben Anmeldeinformationen verwenden, ohne sie bei jedem An- und Abmelden in den Microsoft-Portalen (Intune, Azure) und der Skycure-Verwaltungskonsole erneut eingeben zu müssen.

-   **Endbenutzer** können dieselben Azure AD-Anmeldeinformationen verwenden, ohne sie bei jedem An- und Abmelden in den Skycure-Apps erneut eingeben zu müssen.

Im Folgenden finden Sie die Schritte, um Skycure mit Azure Active Directory Single Sign-On (SSO) zu integrieren.

## <a name="to-retrieve-the-azure-active-directory-tenant-id"></a>So rufen Sie die Azure Active Directory-Mandanten-ID ab

Sie müssen die Azure AD-Mandanten-ID abrufen.

1.  Navigieren Sie zum [Azure-Portal](https://portal.azure.com/), und melden Sie sich mit Ihren Anmeldeinformationen an.

2.  Wählen Sie im **Dashboard** **Azure Active Directory** aus.

    ![Azure AD-Dashboard](./media/skycure-sso-1.png)

3.  Wählen Sie auf dem Blatt **Azure Active Directory** **Eigenschaften** aus.

    ![Blatt „Azure AD-Eigenschaften“](./media/skycure-sso-2.png)

4.  Klicken Sie auf dem Blatt **Azure Active Directory Properties** (Azure Active Directory-Eigenschaften) unter **Tenant Directory ID** (Directory-Mandanten-ID) auf das **Kopiersymbol**.

5. Fügen Sie den kopierten Directory-ID-Wert in eine Textdatei ein, damit Sie ihn später verwenden können. Der Directory-ID-Wert ist später beim Integrationsvorgang von Skycure und Intune erforderlich.

    ![Azure AD-Dashboard](./media/skycure-sso-3.png)

## <a name="allow-skycure-to-communicate-with-azure-active-directory"></a>Zulassen von Kommunikation zwischen Skycure und Azure Active Directory

1.  Geben Sie folgende URL in Ihren Browser ein. Geben Sie anstatt der **DIRECTORY_ID** Ihre Azure Active Directory-Mandanten-ID ein, die Sie in die Textdatei kopiert haben.

        https://login.microsoftonline.com/<DIRECTORY_ID>/oauth2/authorize?client_id=28fd67fdb1794629a8b0dad420b697c7&prompt=admin_consent&redirect_uri=https%3A%2F%2Fmc.skycure.com%2Fapi%2Fexternal%2Fmdm%2Faad_app_consent%2Fmanagement_callback&response_type=code

2.  Sie müssen sich mit Ihren Azure Active Directory-Anmeldeinformationen anmelden. Klicken Sie auf **Accept** (Annehmen), um den Vorgang fortzusetzen.

![Azure AD, Anmeldeseite](./media/skycure-sso-4.png)

## <a name="create-an-azure-ad-security-group-for-skycure-optional"></a>Erstellen einer Azure AD-Sicherheitsgruppe für Skycure (optional)

Möglicherweise möchten Sie eine dedizierte Benutzergruppe erstellen, die z.B. Skycure-Benutzer enthält. Dies kann bei der Analyse von Skycure-Aktivität in den Berichten hilfreich sein.

-   Erfahren Sie mehr über das [Erstellen einer Gruppe und Hinzufügen von Mitgliedern in Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-groups-create-azure-portal).

> [!NOTE] 
> Sie können auch eine vorhandene Azure AD-Sicherheitsgruppe verwenden.

## <a name="configure-the-azure-ad-account-to-integrate-intune-with-skycure"></a>Konfigurieren des Azure AD-Kontos für die Integration von Skycure und Intune

1.  Geben Sie in der [Skycure-Verwaltungskonsole](https://aad.skycure.com/) die zuvor in der Textdatei gespeicherte Azure Active Directory-Mandanten-ID ein.

![Skycure-Verwaltungskonsole, Feld „Azure AD-Mandanten-ID“](./media/skycure-sso-5.png)

> [!IMPORTANT] 
> Skycure überprüft durch Abfragen von Azure AD, ob die Azure AD-Mandanten-ID vorhanden ist. Wenn Skycure sie gefunden hat, kann der Administrator mit dem nächsten Schritt fortfahren: der grundlegenden Installation.

## <a name="next-steps"></a>Nächste Schritte

[Herunterladen der Skycure iOS-App-Konfigurationsrichtlinie](skycure-ios-app-configuration-policy-download.md)
