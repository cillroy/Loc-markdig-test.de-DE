---
title: "Aktivieren von Google Play Protect-Konformität mit Intune"
titleSuffix: Azure portal
description: "Erfahren Sie, wie Sie eine Konformitätsrichtlinie für Android-Geräte erstellen, um Google Play Protect zu aktivieren."
keywords: 
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 11/20/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: E9810BEB-000A-4DFB-B5C7-A22A92082B22
ms.reviewer: muhosabe
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: d610bc338c1bcf81ed3bc71f1357e001914c5877
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2017
---
# <a name="how-to-create-a-device-compliance-policy-to-enable-google-play-protect"></a><span data-ttu-id="1dc61-103">Informationen zum Erstellen einer Gerätekonformitätsrichtlinie zum Aktivieren von Google Play Protect</span><span class="sxs-lookup"><span data-stu-id="1dc61-103">How to create a device compliance policy to enable Google Play Protect</span></span>

<span data-ttu-id="1dc61-104">Sie können eine neue Konformitätsrichtlinie für die Android-Plattform erstellen, um die Konformität mit Google Play Protect (GPP) zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="1dc61-104">You can create a new compliance policy for the Android platform to check for Google Play Protect (GPP) compliance.</span></span>

<span data-ttu-id="1dc61-105">Die Konformitätsrichtlinie, die diese Einstellungen erfordert, kann dann einer Gruppe von Android-Benutzern oder -Geräten zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="1dc61-105">The compliance policy that requires these settings can then be targeted to a group of Android users or devices.</span></span> <span data-ttu-id="1dc61-106">Wenn bei einem Gerät diese Einstellungen nicht aktiviert sind, ist keine Konformität gegeben.</span><span class="sxs-lookup"><span data-stu-id="1dc61-106">If a device does not have these settings enabled, it falls out of compliance.</span></span>

## <a name="create-a-compliance-policy"></a><span data-ttu-id="1dc61-107">Erstellen einer Konformitätsrichtlinie</span><span class="sxs-lookup"><span data-stu-id="1dc61-107">Create a compliance policy</span></span>

1. <span data-ttu-id="1dc61-108">Melden Sie sich im Azure-Portal an.</span><span class="sxs-lookup"><span data-stu-id="1dc61-108">Sign in to the Azure portal.</span></span> <span data-ttu-id="1dc61-109">Wählen Sie **Weitere Dienste** > **Überwachung und Verwaltung** + **Intune** aus.</span><span class="sxs-lookup"><span data-stu-id="1dc61-109">Choose **More Services** > **Monitoring + Management** + **Intune**.</span></span>
2. <span data-ttu-id="1dc61-110">Wählen Sie **Gerätekonformität** in der Gruppe **Verwalten** aus.</span><span class="sxs-lookup"><span data-stu-id="1dc61-110">Choose **Device compliance** in the **Manage** group.</span></span> 
3. <span data-ttu-id="1dc61-111">Wählen Sie **Richtlinien** aus, und klicken Sie dann auf **Richtlinie erstellen**.</span><span class="sxs-lookup"><span data-stu-id="1dc61-111">Choose **Policies**, and choose **Create Policy**.</span></span>
4. <span data-ttu-id="1dc61-112">Füllen Sie die Felder **Name** und **Beschreibung** für die Richtlinie aus.</span><span class="sxs-lookup"><span data-stu-id="1dc61-112">Type the policy **Name** and **Description**.</span></span>
5. <span data-ttu-id="1dc61-113">Wählen Sie **Android** als Plattform aus.</span><span class="sxs-lookup"><span data-stu-id="1dc61-113">Select **Android** for the Platform.</span></span>
6. <span data-ttu-id="1dc61-114">Wählen Sie **Einstellungen** > **Integrität für Geräte**.</span><span class="sxs-lookup"><span data-stu-id="1dc61-114">Choose **Settings** > **Device Health**.</span></span>
7. <span data-ttu-id="1dc61-115">Konfigurieren Sie die Einstellungen für **Google Play Protect**.</span><span class="sxs-lookup"><span data-stu-id="1dc61-115">Configure the **Google Play Protect** settings.</span></span>
8. <span data-ttu-id="1dc61-116">Wenn Sie die Einstellungen für Google Play Protect festgelegt haben, geben Sie die Einstellungen **Sicherheit** und **Geräteeigenschaft** an.</span><span class="sxs-lookup"><span data-stu-id="1dc61-116">When you have set the Google Play Protect settings, specify the **Security** and **Device property** settings.</span></span> <span data-ttu-id="1dc61-117">Wählen Sie abschließend **OK** aus.</span><span class="sxs-lookup"><span data-stu-id="1dc61-117">When you are done, choose **OK**.</span></span>

## <a name="configure-the-google-play-protect-settings"></a><span data-ttu-id="1dc61-118">Konfigurieren der Einstellungen für Google Play Protect</span><span class="sxs-lookup"><span data-stu-id="1dc61-118">Configure the Google Play Protect settings</span></span>

 - <span data-ttu-id="1dc61-119">**Google Play Services ist konfiguriert**</span><span class="sxs-lookup"><span data-stu-id="1dc61-119">**Google Play Services is configured**</span></span>  
   <span data-ttu-id="1dc61-120">Erfordert, dass die Google Play Services-App installiert und aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="1dc61-120">Require that the Google Play services app is installed and enabled.</span></span> <span data-ttu-id="1dc61-121">Google Play Services ermöglicht Sicherheitsupdates und stellt eine grundlegende Abhängigkeit für viele Sicherheitsfunktionen auf zertifizierten Google-Geräten dar.</span><span class="sxs-lookup"><span data-stu-id="1dc61-121">Google Play services allows security updates and is a base-level dependency for many security features on certified-Google devices.</span></span>
 - <span data-ttu-id="1dc61-122">**Aktueller Sicherheitsanbieter**</span><span class="sxs-lookup"><span data-stu-id="1dc61-122">**Up-to-date security provider**</span></span>  
   <span data-ttu-id="1dc61-123">Dient zum Anfordern, dass ein aktueller Sicherheitsanbieter ein Gerät vor bekannten Sicherheitslücken schützen kann.</span><span class="sxs-lookup"><span data-stu-id="1dc61-123">Require that an up-to-date security provider can protect a device from known vulnerabilities.</span></span>
 - <span data-ttu-id="1dc61-124">**Bedrohungsüberprüfung für Apps**</span><span class="sxs-lookup"><span data-stu-id="1dc61-124">**Threat scan on apps**</span></span>  
   <span data-ttu-id="1dc61-125">Dient zum Anfordern, dass die Android-Funktion **Apps überprüfen** aktiviert wird.</span><span class="sxs-lookup"><span data-stu-id="1dc61-125">Require that the Android **Verify Apps** feature is enabled.</span></span>
    > [!Note]  
    > <span data-ttu-id="1dc61-126">Auf der älteren Android-Plattform ist diese Funktion eine Konformitätseinstellung.</span><span class="sxs-lookup"><span data-stu-id="1dc61-126">On the legacy Android platform, this feature is a compliance setting.</span></span> <span data-ttu-id="1dc61-127">Intune kann nur prüfen, ob diese Einstellung auf Geräteebene aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="1dc61-127">Intune can only check whether this setting is enabled at the device level.</span></span> <span data-ttu-id="1dc61-128">Auf Geräten mit Arbeitsprofilen, früher Android for Work, ist diese Einstellung als Konfigurationsrichtlinieneinstellung zu finden.</span><span class="sxs-lookup"><span data-stu-id="1dc61-128">On devices with work profiles, formerly Android for Work, this setting can be found as a configuration policy setting.</span></span> <span data-ttu-id="1dc61-129">Dies ermöglicht Administratoren, die Einstellung für ein Gerät zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="1dc61-129">This allows administrators to enable the setting for a device.</span></span>

    <span data-ttu-id="1dc61-130">Wenn Ihr Unternehmen Android-Arbeitsprofile verwendet, können Sie **Bedrohungsüberprüfung für Apps** für Ihre registrierten Geräte aktivieren.</span><span class="sxs-lookup"><span data-stu-id="1dc61-130">If your enterprise uses Android work profiles, you can enabled **Threat scan on apps** for your enrolled devices.</span></span> <span data-ttu-id="1dc61-131">Richten Sie ein Geräteprofil ein, und fordern Sie die Systemsicherheitseinstellung an.</span><span class="sxs-lookup"><span data-stu-id="1dc61-131">Establish a device profile and require the system security setting.</span></span> <span data-ttu-id="1dc61-132">Weitere Informationen finden Sie unter [Einstellungen für Geräteeinschränkungen für Android for Work-Geräte in Microsoft Intune](device-restrictions-android-for-work.md).</span><span class="sxs-lookup"><span data-stu-id="1dc61-132">For more information, see [Android for Work device restriction settings in Microsoft Intune](device-restrictions-android-for-work.md).</span></span>

 - <span data-ttu-id="1dc61-133">**SafetyNet-Gerätenachweis**</span><span class="sxs-lookup"><span data-stu-id="1dc61-133">**SafetyNet device attestation**</span></span>  
   <span data-ttu-id="1dc61-134">Legen Sie die Integritätsstufe des SafetyNet-Gerätenachweises fest, die eingehalten werden muss.</span><span class="sxs-lookup"><span data-stu-id="1dc61-134">Set the level of SafetyNet device attestation integrity that must be met.</span></span> <span data-ttu-id="1dc61-135">Zu den Stufen zählen **Nicht konfiguriert**, **Grundlegende Integrität prüfen** und **Grundlegende Integrität prüfen & zertifizierte Geräte**.</span><span class="sxs-lookup"><span data-stu-id="1dc61-135">Levels include **Not configured**, **Check basic integrity**, and **Check basic integrity & certified devices**.</span></span>




## <a name="next-steps"></a><span data-ttu-id="1dc61-136">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="1dc61-136">Next steps</span></span>

<span data-ttu-id="1dc61-137">Weitere Informationen zum Arbeiten mit Gerätekonformitätsrichtlinien finden Sie unter [Erste Schritte mit Intune-Gerätekonformitätsrichtlinien](device-compliance-get-started.md).</span><span class="sxs-lookup"><span data-stu-id="1dc61-137">To learn more about working with Intune device compliance policies, see [Get started with Intune device compliance policies](device-compliance-get-started.md).</span></span>