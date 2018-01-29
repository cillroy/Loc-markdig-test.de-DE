---
title: Einrichten der Skycure-Integration in Intune
titlesuffix: Azure portal
description: Richten Sie die Skycure-Integration mit Microsoft Intune ein.
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 06/21/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 359448d9-2384-42ac-a21c-a25148c20a7b
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: ae89f97e1769d2bbd75c43cba4848711a0ad1bea
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2018
---
# <a name="set-up-the-skycure-integration-with-intune"></a><span data-ttu-id="18b49-103">Einrichten der Skycure-Integration in Intune</span><span class="sxs-lookup"><span data-stu-id="18b49-103">Set up the Skycure integration with Intune</span></span>

<span data-ttu-id="18b49-104">Sie müssen Skycure-Apps in Azure AD für SSO-Funktionen hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="18b49-104">You need to add Skycure apps into Azure AD to have Single Sign On capabilities.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="18b49-105">Vorbereitung</span><span class="sxs-lookup"><span data-stu-id="18b49-105">Before you begin</span></span>

### <a name="azure-ad-account-used-to-integrate-intune-and-skycure"></a><span data-ttu-id="18b49-106">Azure AD-Konto, mit dem Intune und Skycure integriert werden</span><span class="sxs-lookup"><span data-stu-id="18b49-106">Azure AD account used to integrate Intune and Skycure</span></span>

-   <span data-ttu-id="18b49-107">Stellen Sie sicher, dass das Azure AD-Konto ordnungsgemäß in der [Skycure-Verwaltungskonsole](https://aad.skycure.com) konfiguriert ist, bevor Sie den grundlegenden Skycure-Installationsvorgang starten.</span><span class="sxs-lookup"><span data-stu-id="18b49-107">Make sure you have the Azure AD account properly configured in the [Skycure Management console](https://aad.skycure.com), before starting the Skycure Basic setup process.</span></span>

### <a name="full-integration-vs-read-only"></a><span data-ttu-id="18b49-108">Die vollständige Integration unterstützt im Vergleich zu Read-only</span><span class="sxs-lookup"><span data-stu-id="18b49-108">Full integration vs. Read-only</span></span>

<span data-ttu-id="18b49-109">Skycure unterstützt zwei Integrationsweisen mit Intune:</span><span class="sxs-lookup"><span data-stu-id="18b49-109">Skycure supports two modes of integration with Intune:</span></span>

-   <span data-ttu-id="18b49-110">**Schreibgeschützte Integration (Grundlegende Installation):** Inventarisiert nur Geräte aus Azure Active Directory und füllt sie in der Skycure-Konsole auf.</span><span class="sxs-lookup"><span data-stu-id="18b49-110">**Read-only integration (Basic setup):** Only inventories devices from Azure Active Directory and populates them in the Skycure console.</span></span>
<br>
    -   <span data-ttu-id="18b49-111">Wenn in der Skycure-Verwaltungskonsole **Report the health and risk of devices to Intune** (Integrität und Risiken der Geräte an Intune melden) und **Also report security incidents to Intune** (Auch Sicherheitsvorfälle an Intune melden) nicht aktiviert sind, ist die Integration schreibgeschützt, und ein Gerätestatus („kompatibel“ oder „nicht kompatibel“) wird in Intune nie geändert.</span><span class="sxs-lookup"><span data-stu-id="18b49-111">If the **Report the health and risk of devices to Intune**, and **Also report security incidents to Intune** boxes are not selected in the Skycure Management console, the integration is read-only and therefore will never change a devices state (compliant or non-compliant) in Intune.</span></span>
<br></br>
-   <span data-ttu-id="18b49-112">**Vollständige Integration:** Ermöglicht Skycure, Risiken und Details zu Sicherheitsvorfällen von Geräten an Intune zu melden, wodurch eine bidirektionale Kommunikation zwischen den beiden Cloud-Diensten entsteht.</span><span class="sxs-lookup"><span data-stu-id="18b49-112">**Full integration:** Allows Skycure to report devices on risk and security incident details to Intune, which creates a bi-directional communication between both cloud services.</span></span>

### <a name="how-the-skycure-apps-are-used-with-azure-ad-and-intune"></a><span data-ttu-id="18b49-113">Wie werden die Skycure-Apps mit Azure AD und Intune verwendet?</span><span class="sxs-lookup"><span data-stu-id="18b49-113">How the Skycure apps are used with Azure AD and Intune?</span></span>

-   <span data-ttu-id="18b49-114">**iOS-App:** Ermöglicht Endbenutzern die Anmeldung bei Azure AD mithilfe einer iOS-App.</span><span class="sxs-lookup"><span data-stu-id="18b49-114">**iOS app:** Allows end-users to sign in to Azure AD using an iOS app.</span></span>

-   <span data-ttu-id="18b49-115">**Android-App:** Ermöglicht Endbenutzern die Anmeldung bei Azure AD mithilfe einer Android-App.</span><span class="sxs-lookup"><span data-stu-id="18b49-115">**Android app:** Allows end-users to sign in to Azure AD using an Android app.</span></span>

-   <span data-ttu-id="18b49-116">**Management-App:** Dies ist die Skycure Azure AD-App für mehrere Mandanten, die dienstübergreifende Kommunikation mit Intune ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="18b49-116">**Management app:** This is the Skycure Azure AD multi-tenant app which enables service-to-service communication with Intune.</span></span>

## <a name="to-set-up-the-read-only-integration-between-intune-and-skycure"></a><span data-ttu-id="18b49-117">So richten Sie die schreibgeschützte Integration zwischen Intune und Skycure ein</span><span class="sxs-lookup"><span data-stu-id="18b49-117">To set up the read-only integration between Intune and Skycure</span></span>

> [!IMPORTANT]
> <span data-ttu-id="18b49-118">Die Skycure-Administratoranmeldeinformationen sind eine E-Mail-Nachricht, die einem gültigen Benutzer in Azure Active Directory gehören muss, andernfalls schlägt die Anmeldung fehl.</span><span class="sxs-lookup"><span data-stu-id="18b49-118">The Skycure admin credentials is an e-mail that must belong to a valid user in the Azure Active Directory, otherwise the login will fail.</span></span> <span data-ttu-id="18b49-119">Skycure verwendet Azure Active Directory zum Authentifizieren des Administrators mithilfe von einmaligem Anmelden (SSO).</span><span class="sxs-lookup"><span data-stu-id="18b49-119">Skycure uses Azure Active Directory to authenticate its admin using Single Sign On (SSO).</span></span>

1.  <span data-ttu-id="18b49-120">Gehen Sie zur [Skycure-Verwaltungskonsole](https://aad.skycure.com).</span><span class="sxs-lookup"><span data-stu-id="18b49-120">Go to [Skycure Management Console](https://aad.skycure.com).</span></span>

2.  <span data-ttu-id="18b49-121">Geben Sie Ihre **Skycure-Administratoranmeldeinformationen** ein, und klicken Sie dann auf **Continue** (Weiter).</span><span class="sxs-lookup"><span data-stu-id="18b49-121">Enter your **Skycure admin credentials**, then click **Continue**.</span></span>

3.  <span data-ttu-id="18b49-122">Wechseln Sie zu **Einstellungen**, und wählen Sie unter **Intune-Integration** **Basic Setup** (Grundlegende Installation) aus.</span><span class="sxs-lookup"><span data-stu-id="18b49-122">Go to **Settings**, choose **Basic Setup** under **Intune Integration**.</span></span>

4.  <span data-ttu-id="18b49-123">Klicken Sie auf dem Label **iOS-App** auf **Add to Active Directory** (Zu Active Directory hinzufügen).</span><span class="sxs-lookup"><span data-stu-id="18b49-123">On the **iOS App** label, click on **Add to Active Directory**.</span></span>

    ![iOS-App auf der Skycure-Verwaltungskonsole](./media/skycure-setup-1.png)

5.  <span data-ttu-id="18b49-125">Die Anmeldeseite wird geöffnet, geben Sie Ihre Intune-Anmeldeinformationen ein, und klicken Sie dann auf **Accept** (Annehmen).</span><span class="sxs-lookup"><span data-stu-id="18b49-125">Login page opens, enter your Intune credentials, then click **Accept**.</span></span>

    ![iOS-App Intune-Anmeldeaufforderung](./media/skycure-setup-2.png)

6.  <span data-ttu-id="18b49-127">Sobald die App zu Azure AD hinzugefügt wurde, sehen Sie auf der Skycure-Verwaltungskonsole einen Hinweis darauf, dass die App erfolgreich zu Azure AD hinzugefügt wurde.</span><span class="sxs-lookup"><span data-stu-id="18b49-127">Once the app is added into Azure AD, you can see an indication that the app was successfully added into Azure AD on the Skycure Management console.</span></span>

    ![iOS-App Abgeschlossen-Screenshot](./media/skycure-setup-3.png)

> [!NOTE]
> <span data-ttu-id="18b49-129">Wiederholen Sie den gleichen Vorgang für die **Skycure Android**- und **Verwaltungs**-Apps.</span><span class="sxs-lookup"><span data-stu-id="18b49-129">Repeat the same process for the **Skycure Android** and **Management** apps.</span></span>

### <a name="add-an-azure-ad-security-group-into-skycure"></a><span data-ttu-id="18b49-130">Hinzufügen einer Azure AD-Sicherheitsgruppe in Skycure</span><span class="sxs-lookup"><span data-stu-id="18b49-130">Add an Azure AD Security group into Skycure</span></span>

<span data-ttu-id="18b49-131">Sie müssen eine Azure AD-Sicherheitsgruppe hinzufügen, die alle Geräte enthält, auf denen Skycure ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="18b49-131">You need to add an Azure AD security group that contains all devices running Skycure.</span></span>

1.  <span data-ttu-id="18b49-132">Geben Sie alle Sicherheitsgruppen von Geräten ein, auf denen Skycure ausgeführt wird, wählen Sie diese aus, und klicken Sie auf **Apply changes** (Änderungen übernehmen).</span><span class="sxs-lookup"><span data-stu-id="18b49-132">Enter and select all the security groups of devices that are running Skycure, then click on **Apply changes**.</span></span>

    ![Konfigurieren der Sicherheitsgruppe Skycure-Verwaltungskonsole](./media/skycure-setup-4.png)

<span data-ttu-id="18b49-134">Skycure synchronisiert die Geräte und führt den Mobile Threat Defense-Dienst mit den Azure AD-Sicherheitsgruppen aus.</span><span class="sxs-lookup"><span data-stu-id="18b49-134">Skycure syncs the devices running its Mobile Threat Defense service with the Azure AD security groups.</span></span>

![Sicherheitsgruppenkonfiguration auf Skycure-Verwaltungskonsole abgeschlossen](./media/skycure-setup-5.png)

## <a name="set-up-the-full-integration-between-intune-and-skycure"></a><span data-ttu-id="18b49-136">Die vollständige Integration zwischen Intune und Skycure einrichten</span><span class="sxs-lookup"><span data-stu-id="18b49-136">Set up the full integration between Intune and Skycure</span></span>

1.  <span data-ttu-id="18b49-137">Gehen Sie zur [Skycure-Verwaltungskonsole](https://aad.skycure.com).</span><span class="sxs-lookup"><span data-stu-id="18b49-137">Go to [Skycure Management Console](https://aad.skycure.com).</span></span>

2.  <span data-ttu-id="18b49-138">Geben Sie Ihre **Skycure-Administratoranmeldeinformationen** ein, und klicken Sie dann auf **Continue** (Weiter).</span><span class="sxs-lookup"><span data-stu-id="18b49-138">Enter your **Skycure admin credentials**, then click **Continue**.</span></span>

3.  <span data-ttu-id="18b49-139">Wechseln Sie zu **Settings** (Einstellungen), und wählen Sie unter **Intune Integration** (Intune-Integration) **Full Integration** (Vollständige Integration) aus.</span><span class="sxs-lookup"><span data-stu-id="18b49-139">Go to **Settings**, choose **Full Integration** under **Intune Integration**.</span></span>

4.  <span data-ttu-id="18b49-140">Überprüfen Sie die folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="18b49-140">Check the following settings:</span></span>

    <span data-ttu-id="18b49-141">ein.</span><span class="sxs-lookup"><span data-stu-id="18b49-141">a.</span></span>  <span data-ttu-id="18b49-142">Report the health and risk of device to Intune (Integrität und Risiken des Geräts an Intune melden)</span><span class="sxs-lookup"><span data-stu-id="18b49-142">Report the health and risk of device to Intune</span></span>

    <span data-ttu-id="18b49-143">b.</span><span class="sxs-lookup"><span data-stu-id="18b49-143">b.</span></span>  <span data-ttu-id="18b49-144">Also report security incidents to Intune (Auch Sicherheitsvorfälle an Intune melden)</span><span class="sxs-lookup"><span data-stu-id="18b49-144">Also report security incidents to Intune</span></span>

5.  <span data-ttu-id="18b49-145">Klicken Sie auf **Apply changes** (Änderungen übernehmen).</span><span class="sxs-lookup"><span data-stu-id="18b49-145">Click on **Apply changes**.</span></span>

    ![Vollständige Integration von Skycure abgeschlossen](./media/skycure-setup-6.png)

## <a name="next-steps"></a><span data-ttu-id="18b49-147">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="18b49-147">Next steps</span></span>

[<span data-ttu-id="18b49-148">Einrichten von Skycure-Apps</span><span class="sxs-lookup"><span data-stu-id="18b49-148">Set up Skycure apps</span></span>](mtd-apps-ios-app-configuration-policy-add-assign.md)
