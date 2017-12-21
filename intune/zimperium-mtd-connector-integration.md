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
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2017
---
# <a name="integrate-zimperium-with-intune"></a><span data-ttu-id="1454a-103">Integrieren von Zimperium in Intune</span><span class="sxs-lookup"><span data-stu-id="1454a-103">Integrate Zimperium with Intune</span></span>

<span data-ttu-id="1454a-104">Sie müssen die nachfolgenden Schritte befolgen, um die Zimperium Mobile Threat Defense-Lösung in Intune zu integrieren.</span><span class="sxs-lookup"><span data-stu-id="1454a-104">You need to follow the steps below to integrate the Zimperium Mobile Threat Defense solution with Intune.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="1454a-105">Vorbereitung</span><span class="sxs-lookup"><span data-stu-id="1454a-105">Before you begin</span></span>

> [!NOTE]
> <span data-ttu-id="1454a-106">Die folgenden Schritte müssen in der [Zimperium MTD-Konsole](https://staging2-console.zimperium.com) ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="1454a-106">The steps below need to be taken in the [Zimperium MTD console](https://staging2-console.zimperium.com).</span></span>

<span data-ttu-id="1454a-107">Stellen Sie vor der Integration von Zimperium in Intune sicher, dass Sie über Folgendes verfügen:</span><span class="sxs-lookup"><span data-stu-id="1454a-107">Before starting the process of integrating Zimperium with Intune, make sure you have the following:</span></span>

-   <span data-ttu-id="1454a-108">Microsoft Intune-Abonnement</span><span class="sxs-lookup"><span data-stu-id="1454a-108">Microsoft Intune subscription</span></span>

-   <span data-ttu-id="1454a-109">Azure Active Directory-Administratoranmeldeinformationen zum Erteilen folgender Berechtigungen:</span><span class="sxs-lookup"><span data-stu-id="1454a-109">Azure Active Directory admin credentials to grant the following permissions:</span></span>

    -   <span data-ttu-id="1454a-110">Anmelden und Lesen des Benutzerprofils</span><span class="sxs-lookup"><span data-stu-id="1454a-110">Sign in and read user profile</span></span>

    -   <span data-ttu-id="1454a-111">Zugriff auf das Verzeichnis als angemeldeter Benutzer</span><span class="sxs-lookup"><span data-stu-id="1454a-111">Access the directory as the signed-in user</span></span>

    -   <span data-ttu-id="1454a-112">Lesen der Verzeichnisdaten</span><span class="sxs-lookup"><span data-stu-id="1454a-112">Read directory data</span></span>

    -   <span data-ttu-id="1454a-113">Senden von Geräteinformationen an Intune</span><span class="sxs-lookup"><span data-stu-id="1454a-113">Send device information to Intune</span></span>

-   <span data-ttu-id="1454a-114">Administratoranmeldeinformationen für den Zugriff auf die Zimperium MTD-Konsole</span><span class="sxs-lookup"><span data-stu-id="1454a-114">Admin credentials to access Zimperium MTD console.</span></span>

### <a name="zimperium-app-authorization"></a><span data-ttu-id="1454a-115">Zimperium-App-Autorisierung</span><span class="sxs-lookup"><span data-stu-id="1454a-115">Zimperium app authorization</span></span>

<span data-ttu-id="1454a-116">Der Autorisierungsprozess von Zimperium umfasst Folgendes:</span><span class="sxs-lookup"><span data-stu-id="1454a-116">The Zimperium app authorization process consists of the following:</span></span>

-   <span data-ttu-id="1454a-117">Der Zimperium-Dienst darf Informationen zum Integritätszustand des Geräts an Intune übertragen.</span><span class="sxs-lookup"><span data-stu-id="1454a-117">Allow the Zimperium service to communicate information related to device health state back to Intune.</span></span>

-   <span data-ttu-id="1454a-118">Zimperium wird mit der Azure AD Enrollment Group-Mitgliedschaft synchronisiert, um die Datenbank des Geräts aufzufüllen.</span><span class="sxs-lookup"><span data-stu-id="1454a-118">Zimperium syncs with Azure AD Enrollment Group membership to populate its device’s database.</span></span>

-   <span data-ttu-id="1454a-119">Die Zimperium-Verwaltungskonsole darf Azure AD-SSO (Single Sign On) verwenden.</span><span class="sxs-lookup"><span data-stu-id="1454a-119">Allow Zimperium admin console to use Azure AD Single Sign On (SSO).</span></span>

-   <span data-ttu-id="1454a-120">Die Zimperium-App darf für die Anmeldung Azure AD-SSO verwenden.</span><span class="sxs-lookup"><span data-stu-id="1454a-120">Allow the Zimperium app to sign in using Azure AD SSO.</span></span>

## <a name="to-set-up-zimperium-integration"></a><span data-ttu-id="1454a-121">Einrichten der Zimperium Integration</span><span class="sxs-lookup"><span data-stu-id="1454a-121">To set up Zimperium integration</span></span>

1.  <span data-ttu-id="1454a-122">Wechseln Sie zur [Zimperium MTD-Konsole](https://staging2-console.zimperium.com), und melden Sie sich mit Ihren Anmeldeinformationen an.</span><span class="sxs-lookup"><span data-stu-id="1454a-122">Go to [Zimperium MTD console](https://staging2-console.zimperium.com) and sign in with your credentials.</span></span>

2.  <span data-ttu-id="1454a-123">Wählen Sie im linken Menü **Verwaltung** aus.</span><span class="sxs-lookup"><span data-stu-id="1454a-123">Choose **Management** from the left menu.</span></span>

3.  <span data-ttu-id="1454a-124">Wählen Sie die Registerkarte **MDM settings** (MDM-Einstellungen) aus.</span><span class="sxs-lookup"><span data-stu-id="1454a-124">Choose the **MDM settings** tab.</span></span>

4.  <span data-ttu-id="1454a-125">Wählen Sie **Add MDM** (MDM hinzufügen) aus, und wählen Sie dann **Microsoft Intune** aus der Liste der **MDM-Anbieter** aus.</span><span class="sxs-lookup"><span data-stu-id="1454a-125">Choose **Add MDM,** then select **Microsoft Intune** from the **MDM provider** list.</span></span>

5.  <span data-ttu-id="1454a-126">Sobald Sie Microsoft Intune als MDM-Dienst festgelegt haben, öffnet sich das Fenster zur **Microsoft Intune-Konfiguration**. Wählen Sie **Azure Active Directory hinzufügen** für jede Option aus: **iOS- und Android-Apps Zimperium zConsole** und **zIPS** zur Autorisierung von Zimperium für die Kommunikation mit Intune und Azure AD über Azure AD-SSO.</span><span class="sxs-lookup"><span data-stu-id="1454a-126">Once you set Microsoft Intune as the MDM service, the **Microsoft Intune Configuration** window pops up, choose the **Add Azure Active Directory** for each option: **Zimperium zConsole**, **zIPS iOS and Android apps** to authorize Zimperium to communicate with Intune and Azure AD through Azure AD Single Sign-On.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="1454a-127">Sie müssen die iOS- und Android-Apps Zimperium zConsole und zIPS hinzufügen, um den Integrationsvorgang in Intune abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="1454a-127">You must add the Zimperium zConsole, zIPS iOS and Android apps to complete to the integration process with Intune.</span></span>

6.  <span data-ttu-id="1454a-128">Wählen Sie **Annehmen** aus, um die Zimperium-App für die Kommunikation mit Intune und Azure Active Directory zu autorisieren.</span><span class="sxs-lookup"><span data-stu-id="1454a-128">Choose **Accept** to authorize the Zimperium app to communicate with Intune and Azure Active Directory.</span></span>

7.  <span data-ttu-id="1454a-129">Nachdem Sie die **iOS- und Android-Apps Zimperium zConsole** und **zIPS** zu Azure AD hinzugefügt haben, müssen Sie die Azure AD-Sicherheitsgruppen hinzufügen, sodass Zimperium die Azure AD-Sicherheitsgruppe mit seinem Dienst synchronisieren kann.</span><span class="sxs-lookup"><span data-stu-id="1454a-129">Once you added the **Zimperium zConsole** and the **zIPS iOS and Android** apps to Azure AD, you need to add the Azure AD security groups so Zimperium can synchronize the Azure AD security group with its service.</span></span>

8.  <span data-ttu-id="1454a-130">Wählen Sie **Fertig stellen** aus, um die Konfiguration zu speichern und die erste Azure AD-Sicherheitsgruppensynchronisierung zu starten.</span><span class="sxs-lookup"><span data-stu-id="1454a-130">Choose **Finish** to save the configuration and start the first Azure AD security group synchronization.</span></span>

## <a name="next-steps"></a><span data-ttu-id="1454a-131">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="1454a-131">Next steps</span></span>

-   [<span data-ttu-id="1454a-132">Einrichten von Zimperium-Apps</span><span class="sxs-lookup"><span data-stu-id="1454a-132">Set up Zimperium apps</span></span>](mtd-apps-ios-app-configuration-policy-add-assign.md)
