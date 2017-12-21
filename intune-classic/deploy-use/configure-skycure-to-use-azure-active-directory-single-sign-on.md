---
title: "Konfigurieren von Skycure für die Verwendung von Azure Active Directory Single Sign-On (SSO)"
description: "Skycure für die Verwendung von Azure Active Directory Single Sign-On (SSO) konfigurieren"
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 03/16/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 34d5d359-5c7c-4225-a205-8ce890b6f890
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 790a687aba5e28cd9d6e5266b77365e00d8d0cd0
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2017
---
# <a name="configure-skycure-to-use-azure-active-directory-single-sign-on-sso"></a><span data-ttu-id="46854-103">Skycure für die Verwendung von Azure Active Directory Single Sign-On (SSO) konfigurieren</span><span class="sxs-lookup"><span data-stu-id="46854-103">Configure Skycure to use Azure Active Directory Single Sign On (SSO)</span></span>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="46854-104">Azure AD-SSO wird verwendet, wenn Sie Intune mit Skycure integrieren.</span><span class="sxs-lookup"><span data-stu-id="46854-104">Azure AD SSO is used when you integrate Intune with Skycure.</span></span> <span data-ttu-id="46854-105">Dies sind die wichtigsten Vorteile:</span><span class="sxs-lookup"><span data-stu-id="46854-105">Here are the main benefits:</span></span>

-   <span data-ttu-id="46854-106">**Administratoren** können dieselben Anmeldeinformationen verwenden, ohne sie bei jedem An- und Abmelden in den Microsoft-Portalen (Intune, Azure) und der Skycure-Verwaltungskonsole erneut eingeben zu müssen.</span><span class="sxs-lookup"><span data-stu-id="46854-106">**Admins** can use the same credentials without having to type it again every time they log in and out from the Microsoft portals (Intune, Azure) and Skycure Management console.</span></span>

-   <span data-ttu-id="46854-107">**Endbenutzer** können dieselben Azure AD-Anmeldeinformationen verwenden, ohne sie bei jedem An- und Abmelden in den Skycure-Apps erneut eingeben zu müssen.</span><span class="sxs-lookup"><span data-stu-id="46854-107">**End-users** can use the same Azure AD credentials without having to type it again every time they log in and out from the Skycure apps.</span></span>

<span data-ttu-id="46854-108">Im Folgenden finden Sie die Schritte, um Skycure mit Azure Active Directory Single Sign-On (SSO) zu integrieren.</span><span class="sxs-lookup"><span data-stu-id="46854-108">Below are the steps to integrate Skycure with Azure Active Directory Single Sign On (SSO).</span></span>

## <a name="to-retrieve-the-azure-active-directory-tenant-id"></a><span data-ttu-id="46854-109">So rufen Sie die Azure Active Directory-Mandanten-ID ab</span><span class="sxs-lookup"><span data-stu-id="46854-109">To retrieve the Azure Active Directory Tenant ID</span></span>

<span data-ttu-id="46854-110">Sie müssen die Azure AD-Mandanten-ID abrufen.</span><span class="sxs-lookup"><span data-stu-id="46854-110">You need to retrieve the Azure AD Tenant ID.</span></span>

1.  <span data-ttu-id="46854-111">Navigieren Sie zum [Azure-Portal](https://portal.azure.com/), und melden Sie sich mit Ihren Anmeldeinformationen an.</span><span class="sxs-lookup"><span data-stu-id="46854-111">Go to the [Azure portal](https://portal.azure.com/) and sign in with your credentials.</span></span>

2.  <span data-ttu-id="46854-112">Wählen Sie im **Dashboard** **Azure Active Directory** aus.</span><span class="sxs-lookup"><span data-stu-id="46854-112">You can see the **Dashboard,** choose **Azure Active Directory**.</span></span>

![Azure AD-Dashboard](../media/mtp/skycure-sso-1.png)

1.  <span data-ttu-id="46854-114">Wählen Sie auf dem Blatt **Azure Active Directory** **Eigenschaften** aus.</span><span class="sxs-lookup"><span data-stu-id="46854-114">The **Azure Active Directory** blade opens, choose **Properties**.</span></span>

![Blatt „Azure AD-Eigenschaften“](../media/mtp/skycure-sso-2.png)

1.  <span data-ttu-id="46854-116">Klicken Sie auf dem Blatt **Azure Active Directory Properties** (Azure Active Directory-Eigenschaften) unter **Tenant Directory ID** (Directory-Mandanten-ID) auf das **Kopiersymbol**.</span><span class="sxs-lookup"><span data-stu-id="46854-116">Click on the **Copy icon** under the **Tenant Directory ID** at **Azure Active Directory Properties** blade.</span></span>

> <span data-ttu-id="46854-117">Fügen Sie den kopierten Directory-ID-Wert in eine Textdatei ein, damit Sie ihn später verwenden können.</span><span class="sxs-lookup"><span data-stu-id="46854-117">Paste the copied Directory ID value in a text file so you can use it later.</span></span> <span data-ttu-id="46854-118">Der Directory-ID-Wert ist später beim Integrationsvorgang von Skycure und Intune erforderlich.</span><span class="sxs-lookup"><span data-stu-id="46854-118">The Directory ID value will be required later in the Skycure and Intune integration process.</span></span>

![Azure AD-Dashboard](../media/mtp/skycure-sso-3.png)

## <a name="allow-skycure-to-communicate-with-azure-active-directory"></a><span data-ttu-id="46854-120">Zulassen von Kommunikation zwischen Skycure und Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="46854-120">Allow Skycure to communicate with Azure Active Directory</span></span>

1.  <span data-ttu-id="46854-121">Geben Sie folgende URL in Ihren Browser ein.</span><span class="sxs-lookup"><span data-stu-id="46854-121">Enter the below URL in your browser.</span></span> <span data-ttu-id="46854-122">Geben Sie anstatt der **DIRECTORY_ID** Ihre Azure Active Directory-Mandanten-ID ein, die Sie in die Textdatei kopiert haben.</span><span class="sxs-lookup"><span data-stu-id="46854-122">Instead of **DIRECTORY_ID**, enter your Azure Active Directory Tenant ID previously copied to the text file.</span></span>

        https://login.microsoftonline.com/<DIRECTORY_ID>/oauth2/authorize?client_id=28fd67fdb1794629a8b0dad420b697c7&prompt=admin_consent&redirect_uri=https%3A%2F%2Fmc.skycure.com%2Fapi%2Fexternal%2Fmdm%2Faad_app_consent%2Fmanagement_callback&response_type=code

2.  <span data-ttu-id="46854-123">Sie müssen sich mit Ihren Azure Active Directory-Anmeldeinformationen anmelden.</span><span class="sxs-lookup"><span data-stu-id="46854-123">You need to login using your Azure Active Directory credentials.</span></span> <span data-ttu-id="46854-124">Klicken Sie auf **Accept** (Annehmen), um den Vorgang fortzusetzen.</span><span class="sxs-lookup"><span data-stu-id="46854-124">Click **Accept** to continue.</span></span>

![Azure AD, Anmeldeseite](../media/mtp/skycure-sso-4.png)

## <a name="create-an-azure-ad-security-group-for-skycure-optional"></a><span data-ttu-id="46854-126">Erstellen einer Azure AD-Sicherheitsgruppe für Skycure (optional)</span><span class="sxs-lookup"><span data-stu-id="46854-126">Create an Azure AD Security group for Skycure (optional)</span></span>

<span data-ttu-id="46854-127">Möglicherweise möchten Sie eine dedizierte Benutzergruppe erstellen, die z.B. Skycure-Benutzer enthält.</span><span class="sxs-lookup"><span data-stu-id="46854-127">You might want to create a dedicated user group which contain users running Skycure (e.g Skycure users).</span></span> <span data-ttu-id="46854-128">Dies kann bei der Analyse von Skycure-Aktivität in den Berichten hilfreich sein.</span><span class="sxs-lookup"><span data-stu-id="46854-128">This can be helpful when analyzing Skycure activity through the reports.</span></span>

-   <span data-ttu-id="46854-129">Erfahren Sie mehr über das [Erstellen einer Gruppe und Hinzufügen von Mitgliedern in Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-groups-create-azure-portal).</span><span class="sxs-lookup"><span data-stu-id="46854-129">Learn more [how to create a group and add members in Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-groups-create-azure-portal).</span></span>

> [!NOTE] 
> <span data-ttu-id="46854-130">Sie können auch eine vorhandene Azure AD-Sicherheitsgruppe verwenden.</span><span class="sxs-lookup"><span data-stu-id="46854-130">You can also use an existing Azure AD security group.</span></span>

## <a name="configure-the-azure-ad-account-to-integrate-intune-with-skycure"></a><span data-ttu-id="46854-131">Konfigurieren des Azure AD-Kontos für die Integration von Skycure und Intune</span><span class="sxs-lookup"><span data-stu-id="46854-131">Configure the Azure AD account to integrate Intune with Skycure</span></span>

1.  <span data-ttu-id="46854-132">Geben Sie in der [Skycure-Verwaltungskonsole](https://aad.skycure.com/) die zuvor in der Textdatei gespeicherte Azure Active Directory-Mandanten-ID ein.</span><span class="sxs-lookup"><span data-stu-id="46854-132">From the [Skycure Management Console](https://aad.skycure.com/), enter the Azure Active Directory Tenant ID previously saved in the text file.</span></span>

![Skycure-Verwaltungskonsole, Feld „Azure AD-Mandanten-ID“](../media/mtp/skycure-sso-5.png)

> [!IMPORTANT] 
> <span data-ttu-id="46854-134">Skycure überprüft durch Abfragen von Azure AD, ob die Azure AD-Mandanten-ID vorhanden ist. Wenn Skycure sie gefunden hat, kann der Administrator mit dem nächsten Schritt fortfahren: der grundlegenden Installation.</span><span class="sxs-lookup"><span data-stu-id="46854-134">Skycure validates if the Azure AD Tenant ID exists by querying Azure AD, once Skycure finds it, the admin can proceed to next step, which is the Basic setup.</span></span>

## <a name="next-steps"></a><span data-ttu-id="46854-135">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="46854-135">Next steps</span></span>

[<span data-ttu-id="46854-136">Herunterladen der Skycure iOS-App-Konfigurationsrichtlinie</span><span class="sxs-lookup"><span data-stu-id="46854-136">Download Skycure iOS app configuration policy</span></span>](/intune-classic/deploy-use/download-skycure-ios-app-configuration-policy)
