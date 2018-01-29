---
title: Einrichten der Check Point SandBlast-Integration in Intune
titlesuffix: Azure portal
description: Einrichten der Check Point SandBlast-Integration in Intune
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 07/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 1e9b1576-b239-48cc-a672-da6b5fb7be0a
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: eb0c41093656cd04843345e32dd1f8e80447346a
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2018
---
# <a name="integrate-check-point-sandblast-mobile-with-intune"></a><span data-ttu-id="5563a-103">Integrieren von Check Point SandBlast Mobile in Intune</span><span class="sxs-lookup"><span data-stu-id="5563a-103">Integrate Check Point SandBlast Mobile with Intune</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="5563a-104">Vorbereitung</span><span class="sxs-lookup"><span data-stu-id="5563a-104">Before you begin</span></span>

> [!NOTE] 
> <span data-ttu-id="5563a-105">Folgende Schritte müssen in der [Check Point SandBlast Mobile MTD-Konsole](https://intune-4.eu1.locsec.net/) ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="5563a-105">The steps below need to be taken in the [Check Point SandBlast Mobile MTD console](https://intune-4.eu1.locsec.net/).</span></span>

<span data-ttu-id="5563a-106">Stellen Sie vor der Integration von Check Point SandBlast Mobile in Intune sicher, dass Sie über Folgendes verfügen:</span><span class="sxs-lookup"><span data-stu-id="5563a-106">Before starting the process of integrating Check Point SandBlast Mobile with Intune, make sure you have the following:</span></span>

-   <span data-ttu-id="5563a-107">Microsoft Intune-Abonnement</span><span class="sxs-lookup"><span data-stu-id="5563a-107">Microsoft Intune subscription</span></span>

-   <span data-ttu-id="5563a-108">Azure Active Directory-Administratoranmeldeinformationen zum Erteilen folgender Berechtigungen:</span><span class="sxs-lookup"><span data-stu-id="5563a-108">Azure Active Directory admin credentials to grant the following permissions:</span></span>

    -   <span data-ttu-id="5563a-109">Anmelden und Lesen des Benutzerprofils</span><span class="sxs-lookup"><span data-stu-id="5563a-109">Sign in and read user profile</span></span>

    -   <span data-ttu-id="5563a-110">Zugriff auf das Verzeichnis als angemeldeter Benutzer</span><span class="sxs-lookup"><span data-stu-id="5563a-110">Access the directory as the signed-in user</span></span>

    -   <span data-ttu-id="5563a-111">Lesen der Verzeichnisdaten</span><span class="sxs-lookup"><span data-stu-id="5563a-111">Read directory data</span></span>

    -   <span data-ttu-id="5563a-112">Senden von Geräteinformationen an Intune</span><span class="sxs-lookup"><span data-stu-id="5563a-112">Send device information to Intune</span></span>

-   <span data-ttu-id="5563a-113">Administratoranmeldeinformationen für den Zugriff auf die Check Point SandBlast Mobile MTD-Konsole.</span><span class="sxs-lookup"><span data-stu-id="5563a-113">Admin credentials to access Check Point SandBlast Mobile MTD console.</span></span>

### <a name="check-point-sandblast-app-authorization"></a><span data-ttu-id="5563a-114">Autorisierung der Check Point SandBlast-App</span><span class="sxs-lookup"><span data-stu-id="5563a-114">Check Point SandBlast app authorization</span></span>

<span data-ttu-id="5563a-115">Der Autorisierungsprozess der Check Point SandBlast-App umfasst Folgendes:</span><span class="sxs-lookup"><span data-stu-id="5563a-115">The Check Point SandBlast app authorization process consists of the following:</span></span>

-   <span data-ttu-id="5563a-116">Der Check Point SandBlast Mobile-Dienst darf Informationen zum Integritätszustand des Geräts wieder an Intune übertragen.</span><span class="sxs-lookup"><span data-stu-id="5563a-116">Allow the Check Point SandBlast Mobile service to communicate information related to device health state back to Intune.</span></span>

-   <span data-ttu-id="5563a-117">Check Point SandBlast Mobile wird mit der Azure AD Enrollment Group-Mitgliedschaft synchronisiert, um die Datenbank des Geräts aufzufüllen.</span><span class="sxs-lookup"><span data-stu-id="5563a-117">CheckPoint SandBlast Mobile syncs with Azure AD Enrollment Group membership to populate its device’s database.</span></span>

-   <span data-ttu-id="5563a-118">Die Check Point SandBlast-Verwaltungskonsole darf Azure AD-SSO (Single Sign On, SSO) verwenden.</span><span class="sxs-lookup"><span data-stu-id="5563a-118">Allow Check Point SandBlast admin console to use Azure AD Single Sign On (SSO).</span></span>

-   <span data-ttu-id="5563a-119">Die Check Point SandBlast Mobile-App darf sich über Azure AD-SSO anmelden.</span><span class="sxs-lookup"><span data-stu-id="5563a-119">Allow the Check Point SandBlast Mobile app to sign in using Azure AD SSO.</span></span>

## <a name="to-set-up-check-point-sandblast-mobile-integration"></a><span data-ttu-id="5563a-120">So richten Sie die Check Point SandBlast Mobile-Integration ein</span><span class="sxs-lookup"><span data-stu-id="5563a-120">To set up Check Point SandBlast Mobile integration</span></span>

1.  <span data-ttu-id="5563a-121">Wechseln Sie zu [Check Point SandBlast Mobile MTD-Konsole](https://intune-4.eu1.locsec.net/), und melden Sie sich mit Ihren Anmeldeinformationen an.</span><span class="sxs-lookup"><span data-stu-id="5563a-121">Go to [Check Point SandBlast Mobile MTD console](https://intune-4.eu1.locsec.net/) and sign in with your credentials.</span></span>

2.  <span data-ttu-id="5563a-122">Klicken Sie auf die Registerkarte **Einstellungen**.</span><span class="sxs-lookup"><span data-stu-id="5563a-122">Click on the **Settings** tab.</span></span>

3.  <span data-ttu-id="5563a-123">Wählen Sie **Geräteverwaltung** aus, und klicken Sie anschließend auf **Einstellungen**.</span><span class="sxs-lookup"><span data-stu-id="5563a-123">Choose **Device management**, then **Settings**.</span></span>

4.  <span data-ttu-id="5563a-124">Wählen Sie **Microsoft Intune** aus der Dropdown-Liste **MDM-Dienst** aus.</span><span class="sxs-lookup"><span data-stu-id="5563a-124">Choose **Microsoft Intune** from the **MDM Service** drop-down list.</span></span>

5.  <span data-ttu-id="5563a-125">Nachdem Sie Microsoft Intune als MDM-Dienst festgelegt haben, wird das Fenster **Microsoft Intune-Konfiguration** geöffnet. Wählen Sie für jede Geräteplattform (iOS, Android und Windows) **Zu eigener Organisation hinzufügen** aus, um Check Point SandBlast Mobile für die Kommunikation mit Intune und Azure AD zu autorisieren.</span><span class="sxs-lookup"><span data-stu-id="5563a-125">Once you set Microsoft Intune as the MDM Service, the **Microsoft Intune Configuration** window pops up, choose the **Add to my organization** for each device platform: iOS, Android and Windows to authorize Check Point SandBlast Mobile to communicate with Intune and Azure AD.</span></span>

    ![Check Point MTD-Konfiguration in Intune](./media/checkpoint-MTD-1.PNG)

    > [!IMPORTANT]
    > <span data-ttu-id="5563a-127">Sie müssen alle Geräteplattformen hinzufügen, um mit dem nächsten Schritt fortfahren zu können.</span><span class="sxs-lookup"><span data-stu-id="5563a-127">You must add all device platforms to proceed to the next step.</span></span>

6.  <span data-ttu-id="5563a-128">Wählen Sie **Annehmen** aus, um die Check Point SandBlast Mobile-App für die Kommunikation mit Intune und Azure Active Directory zu autorisieren.</span><span class="sxs-lookup"><span data-stu-id="5563a-128">Choose **Accept** to authorize the Check Point SandBlast Mobile app to communicate with Intune and Azure Active Directory.</span></span>

7.  <span data-ttu-id="5563a-129">Nachdem Sie alle Geräteplattformen aktiviert haben, müssen Sie die Azure AD-Sicherheitsgruppe eingeben.</span><span class="sxs-lookup"><span data-stu-id="5563a-129">Once you enabled all device platforms, you need to enter the Azure AD security group.</span></span>

8.  <span data-ttu-id="5563a-130">Wählen Sie **Überprüfen** aus. Wählen Sie **Speichern** aus, sobald die Azure AD-Sicherheitsgruppe erfolgreich überprüft wurde.</span><span class="sxs-lookup"><span data-stu-id="5563a-130">Choose **Verify**, once the Azure AD security group is successfully verified, choose **Save**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="5563a-131">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="5563a-131">Next steps</span></span>

- [<span data-ttu-id="5563a-132">Einrichten von Check Point SandBlast Mobile-Apps</span><span class="sxs-lookup"><span data-stu-id="5563a-132">Set up Check Point SandBlast Mobile apps</span></span>](mtd-apps-ios-app-configuration-policy-add-assign.md)