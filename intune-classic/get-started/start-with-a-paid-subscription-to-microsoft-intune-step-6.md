---
title: Bereitstellen von Richtlinien und Apps
description: "Sie können Richtlinieneinstellungen aktivieren und Apps bereitstellen, die angewendet werden, sobald die Geräte für die Verwaltung registriert wurden."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 02/14/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e0d8e98f-7dd8-4cbf-887c-a9af63ffe970
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 9068e9462226f70150f06cd65e9ba044dc96ac99
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2017
---
# <a name="create-policies-and-publish-apps"></a><span data-ttu-id="c6aed-103">Erstellen von Richtlinien und Veröffentlichen von Apps</span><span class="sxs-lookup"><span data-stu-id="c6aed-103">Create policies and publish apps</span></span>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="c6aed-104">In diesem Thema erfahren Administratoren, wie Sie Richtlinien erstellen und Apps veröffentlichen können, die sie für verwaltetet Geräte bereitstellen können.</span><span class="sxs-lookup"><span data-stu-id="c6aed-104">This topic tells Intune administrators how they can create policies and publish apps that they can then deploy to managed devices.</span></span>

<span data-ttu-id="c6aed-105">Bevor Sie Apps in Intune registrieren, können Sie Richtlinieneinstellungen und Apps aktivieren, die bereitgestellt werden, sobald diese Geräte der Verwaltung hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="c6aed-105">Before you start enrolling apps into Intune, you can enable policy settings and apps that will be deployed as soon as those devices come into management.</span></span> <span data-ttu-id="c6aed-106">Mit Intune-Richtlinien stehen Einstellungen bereit, mit deren Hilfe Sie die Sicherheitseinstellungen auf mobilen Geräten steuern, die Windows-Firewall- und Endpoint Protection-Einstellungen für Computer warten und Anwendungen bereitstellen können.</span><span class="sxs-lookup"><span data-stu-id="c6aed-106">Intune policies provide settings that help you control the security settings on mobile devices, maintain Windows Firewall and Endpoint Protection settings for computers, and deploy applications.</span></span> <span data-ttu-id="c6aed-107">Sie können Richtlinien konfigurieren, Apps hinzufügen und diese Apps bereitstellen, damit Geräte die Einstellungen und Apps empfangen, sobald sie in Intune registriert werden.</span><span class="sxs-lookup"><span data-stu-id="c6aed-107">You can configure policy, add apps, and deploy those apps so that devices receive settings and apps as soon as they enroll in Intune.</span></span>

<span data-ttu-id="c6aed-108">Richtlinien und Apps sind plattformspezifisch.</span><span class="sxs-lookup"><span data-stu-id="c6aed-108">Policies and apps are platform-specific.</span></span>

## <a name="manage-device-settings"></a><span data-ttu-id="c6aed-109">Verwalten von Geräteeinstellungen</span><span class="sxs-lookup"><span data-stu-id="c6aed-109">Manage device settings</span></span>

 <span data-ttu-id="c6aed-110">Richtlinieneinstellungen für Geräte werden plattformbasiert konfiguriert und verwaltet.</span><span class="sxs-lookup"><span data-stu-id="c6aed-110">Device policy settings are configured and managed on a per-platform basis.</span></span> <span data-ttu-id="c6aed-111">Die folgenden Links enthalten Listen der verfügbaren Einstellungen für deren jeweilige Plattformen:</span><span class="sxs-lookup"><span data-stu-id="c6aed-111">The following links provide lists of available settings for their respective platforms:</span></span>

- [<span data-ttu-id="c6aed-112">iOS</span><span class="sxs-lookup"><span data-stu-id="c6aed-112">iOS</span></span>](/intune-classic/deploy-use/ios-policy-settings-in-microsoft-intune)
- [<span data-ttu-id="c6aed-113">Android und Samsung KNOX Standard</span><span class="sxs-lookup"><span data-stu-id="c6aed-113">Android and Samsung KNOX Standard</span></span>](/intune-classic/deploy-use/android-policy-settings-in-microsoft-intune)
- [<span data-ttu-id="c6aed-114">Android for Work</span><span class="sxs-lookup"><span data-stu-id="c6aed-114">Android for Work</span></span>](/intune-classic/deploy-use/android-for-work-policy-settings-in-microsoft-intune)
- [<span data-ttu-id="c6aed-115">Windows 10 (PC und mobil)</span><span class="sxs-lookup"><span data-stu-id="c6aed-115">Windows 10  (PC and mobile)</span></span>](/intune-classic/deploy-use/windows-10-policy-settings-in-microsoft-intune)
- [<span data-ttu-id="c6aed-116">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="c6aed-116">Windows 8.1</span></span>](/intune-classic/deploy-use/windows-configuration-policy-settings-in-microsoft-intune)
- [<span data-ttu-id="c6aed-117">Windows Phone 8.1</span><span class="sxs-lookup"><span data-stu-id="c6aed-117">Windows Phone 8.1</span></span>](/intune-classic/deploy-use/windows-phone-8-1-policy-settings-in-microsoft-intune)
- [<span data-ttu-id="c6aed-118">Windows Team</span><span class="sxs-lookup"><span data-stu-id="c6aed-118">Windows Team</span></span>](/intune-classic/deploy-use/windows-team-configuration-policy-settings-in-microsoft-intune)
- [<span data-ttu-id="c6aed-119">Windows-PCs, auf denen die Intune-Clientsoftware ausgeführt wird</span><span class="sxs-lookup"><span data-stu-id="c6aed-119">Windows PCs running Intune software client</span></span>](/intune-classic/deploy-use/policies-to-protect-windows-pcs-in-microsoft-intune)

<span data-ttu-id="c6aed-120">Weitere Informationen finden Sie unter [Verwalten von Einstellungen und Features auf Ihren Geräten mit Microsoft Intune-Richtlinien](/intune-classic/deploy-use/manage-settings-and-features-on-your-devices-with-microsoft-intune-policies).</span><span class="sxs-lookup"><span data-stu-id="c6aed-120">You can learn more about how to [Manage settings and features on your devices with Microsoft Intune policies](/intune-classic/deploy-use/manage-settings-and-features-on-your-devices-with-microsoft-intune-policies).</span></span>

## <a name="add-and-deploy-apps"></a><span data-ttu-id="c6aed-121">Hinzufügen und Bereitstellen von Apps</span><span class="sxs-lookup"><span data-stu-id="c6aed-121">Add and deploy apps</span></span>

<span data-ttu-id="c6aed-122">Sie können Apps zu Intune hinzufügen und sie dann auf zwei Arten auf verwalteten Geräten bereitstellen:</span><span class="sxs-lookup"><span data-stu-id="c6aed-122">You can add apps to Intune and then deploy them to managed devices in two ways:</span></span>
- <span data-ttu-id="c6aed-123">**Erforderliche Installation**: Die Apps werden automatisch auf den verwalteten Geräten installiert.</span><span class="sxs-lookup"><span data-stu-id="c6aed-123">**Required install** - Apps automatically installs the app to managed devices</span></span>
- <span data-ttu-id="c6aed-124">**Verfügbare Installation**: Die Apps werden im Intune-Unternehmensportal angezeigt und die Benutzer können auswählen, ob sie die Apps auf ihren Geräten installieren möchten.</span><span class="sxs-lookup"><span data-stu-id="c6aed-124">**Available install** - Apps appear in the Intune Company Portal so that users can choose whether to install them on their devices</span></span>

### <a name="add-apps"></a><span data-ttu-id="c6aed-125">Hinzufügen von Apps</span><span class="sxs-lookup"><span data-stu-id="c6aed-125">Add apps</span></span>

<span data-ttu-id="c6aed-126">Zunächst müssen Sie die Apps mithilfe einer der folgenden Methoden in Intune verfügbar machen:</span><span class="sxs-lookup"><span data-stu-id="c6aed-126">First you must make apps available in Intune by one of the following methods:</span></span>
- [<span data-ttu-id="c6aed-127">Hinzufügen von Apps für registrierte Geräte</span><span class="sxs-lookup"><span data-stu-id="c6aed-127">Add apps for enrolled devices</span></span>](/intune-classic/deploy-use/add-apps-for-mobile-devices-in-microsoft-intune)
- [<span data-ttu-id="c6aed-128">Hinzufügen von Apps für Intune-Softwareclient-PCs</span><span class="sxs-lookup"><span data-stu-id="c6aed-128">Add apps for Intune software client PCs</span></span>](/intune-classic/deploy-use/add-apps-for-windows-pcs-in-microsoft-intune)

### <a name="deploy-apps"></a><span data-ttu-id="c6aed-129">Bereitstellen von Apps</span><span class="sxs-lookup"><span data-stu-id="c6aed-129">Deploy apps</span></span>

<span data-ttu-id="c6aed-130">Sobald die App in Intune zur Verfügung steht, können Sie sie auf verwalteten Geräten bereitstellen:</span><span class="sxs-lookup"><span data-stu-id="c6aed-130">Now that the app is availabile in Intune, you can deploy it to managed devices:</span></span>
- [<span data-ttu-id="c6aed-131">Bereitstellen von Apps auf Geräten</span><span class="sxs-lookup"><span data-stu-id="c6aed-131">Deploy apps to devices</span></span>](/intune-classic/deploy-use/deploy-use/deploy-apps-in-microsoft-intune)
- <span data-ttu-id="c6aed-132">Bereitstellen von Apps aus einem Volumenprogramm:</span><span class="sxs-lookup"><span data-stu-id="c6aed-132">Deploy volume-purchased apps:</span></span>
    - [<span data-ttu-id="c6aed-133">iOS: Volume Purchase Program (VPP)</span><span class="sxs-lookup"><span data-stu-id="c6aed-133">iOS - Volume-purchase Program</span></span>](/intune-classic/deploy-use/manage-ios-apps-you-purchased-through-a-volume-purchase-program-with-microsoft-intune)
    - [<span data-ttu-id="c6aed-134">Microsoft Store für Unternehmen</span><span class="sxs-lookup"><span data-stu-id="c6aed-134">Microsoft Store for Business</span></span>](/intune-classic/deploy-use/manage-apps-you-purchased-from-the-windows-store-for-business-with-microsoft-intune)
    - [<span data-ttu-id="c6aed-135">Android for Work</span><span class="sxs-lookup"><span data-stu-id="c6aed-135">Android for Work</span></span>](/intune-classic/deploy-use/android-for-work-apps)

    <span data-ttu-id="c6aed-136">Nachdem Sie die Apps für die Bereitstellung konfiguriert haben, können Sie [Apps konfigurieren](/intune-classic/deploy-use/monitor-apps-in-microsoft-intune).</span><span class="sxs-lookup"><span data-stu-id="c6aed-136">Once you have configured apps for deployment you can [configure apps](/intune-classic/deploy-use/monitor-apps-in-microsoft-intune).</span></span>

>[!div class="step-by-step"]

><span data-ttu-id="c6aed-137">[&larr; **Organisieren von Benutzern und Geräten**](.\start-with-a-paid-subscription-to-microsoft-intune-step-5.md)[**Anpassen des Unternehmensportals** &rarr;](/intune/company-portal-customize)</span><span class="sxs-lookup"><span data-stu-id="c6aed-137">[&larr; **Organize users and devices**](.\start-with-a-paid-subscription-to-microsoft-intune-step-5.md)       [**Customize Company Portal** &rarr;](/intune/company-portal-customize)</span></span>  
