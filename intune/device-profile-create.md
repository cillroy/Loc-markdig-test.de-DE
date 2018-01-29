---
title: "Erstellen von Intune-Gerätekonfigurationsprofilen"
titlesuffix: Azure portal
description: "In diesem Artikel erfahren Sie, wie Sie Intune-Gerätekonfigurationsprofile erstellen."
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 05/16/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d98aceff-eb35-4e3e-8e40-5f300e7335cc
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 309678406dd9f887c0f9ca0ab79c4580421024d1
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2018
---
# <a name="how-to-create-device-configuration-profiles-in-microsoft-intune"></a><span data-ttu-id="1eb3d-103">Erstellen von Gerätekonfigurationsprofilen in Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="1eb3d-103">How to create device configuration profiles in Microsoft Intune</span></span>

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

1. <span data-ttu-id="1eb3d-104">Melden Sie sich beim Azure-Portal an.</span><span class="sxs-lookup"><span data-stu-id="1eb3d-104">Sign into the Azure portal.</span></span>
2. <span data-ttu-id="1eb3d-105">Wählen Sie **Weitere Dienste** > **Überwachung und Verwaltung** > **Intune** aus.</span><span class="sxs-lookup"><span data-stu-id="1eb3d-105">Choose **More Services** > **Monitoring + Management** > **Intune**.</span></span>
3. <span data-ttu-id="1eb3d-106">Wählen Sie auf dem Blatt **Intune** die Option **Geräte konfigurieren** aus.</span><span class="sxs-lookup"><span data-stu-id="1eb3d-106">On the **Intune** blade, choose **Configure devices**.</span></span>
4. <span data-ttu-id="1eb3d-107">Wählen Sie auf dem Blatt **Gerätekonfiguration** die Option **Verwalten** > **Profile** aus.</span><span class="sxs-lookup"><span data-stu-id="1eb3d-107">On the **Device Configuration** blade, choose **Manage** > **Profiles**.</span></span>
5. <span data-ttu-id="1eb3d-108">Wählen Sie auf dem Blatt mit der Profilliste **Profil erstellen** aus.</span><span class="sxs-lookup"><span data-stu-id="1eb3d-108">On the blade showing the list of profiles, choose **Create Profile**.</span></span>
6. <span data-ttu-id="1eb3d-109">Geben Sie auf dem Blatt **Profil erstellen** folgende Elemente an:</span><span class="sxs-lookup"><span data-stu-id="1eb3d-109">On the **Create Profile** blade, specify the following items:</span></span>
   - <span data-ttu-id="1eb3d-110">**Name:** Geben Sie einen aussagekräftigen Namen für das neue Profil ein.</span><span class="sxs-lookup"><span data-stu-id="1eb3d-110">**Name** - Enter a descriptive name for the new profile.</span></span>
   - <span data-ttu-id="1eb3d-111">**Beschreibung:** Geben Sie eine Beschreibung für das Profil ein (optional).</span><span class="sxs-lookup"><span data-stu-id="1eb3d-111">**Description** -  Enter an optional description for the profile.</span></span>
   - <span data-ttu-id="1eb3d-112">**Plattform:** Wählen Sie den Plattformtyp für das Profil aus, das Sie erstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="1eb3d-112">**Platform** -  Select the platform type for the profile you want to create.</span></span>
   - <span data-ttu-id="1eb3d-113">**Profiltyp:** Wählen Sie den Profiltyp aus, den Sie erstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="1eb3d-113">**Profile type** - Select the type of profile you want to create.</span></span> <span data-ttu-id="1eb3d-114">Die Liste der verfügbaren Typen variiert je nach der ausgewählten Plattform.</span><span class="sxs-lookup"><span data-stu-id="1eb3d-114">The list of available types differs depending on the platform you chose.</span></span>
   - <span data-ttu-id="1eb3d-115">**Einstellungen:** In den folgenden Themen finden Sie Informationen zu den Einstellungen für die einzelnen Profiltypen:</span><span class="sxs-lookup"><span data-stu-id="1eb3d-115">**Settings** - See the following topics for information about the settings for each profile type:</span></span>
       -  [<span data-ttu-id="1eb3d-116">Gerätefunktionseinstellungen</span><span class="sxs-lookup"><span data-stu-id="1eb3d-116">Device feature settings</span></span>](device-features-configure.md)
       -  [<span data-ttu-id="1eb3d-117">Einstellungen für Geräteeinschränkungen</span><span class="sxs-lookup"><span data-stu-id="1eb3d-117">Device restriction settings</span></span>](device-restrictions-configure.md)
       -  [<span data-ttu-id="1eb3d-118">E-Mail-Einstellungen</span><span class="sxs-lookup"><span data-stu-id="1eb3d-118">Email settings</span></span>](email-settings-configure.md)
       -  [<span data-ttu-id="1eb3d-119">VPN-Einstellungen</span><span class="sxs-lookup"><span data-stu-id="1eb3d-119">VPN settings</span></span>](vpn-settings-configure.md)
       -  [<span data-ttu-id="1eb3d-120">WLAN-Einstellungen</span><span class="sxs-lookup"><span data-stu-id="1eb3d-120">Wi-Fi settings</span></span>](wi-fi-settings-configure.md)
       -  [<span data-ttu-id="1eb3d-121">Einstellungen für Windows 10-Editionsupgrades</span><span class="sxs-lookup"><span data-stu-id="1eb3d-121">Windows 10 edition upgrade settings</span></span>](edition-upgrade-configure-windows-10.md)
       -  [<span data-ttu-id="1eb3d-122">Zertifikateinstellungen</span><span class="sxs-lookup"><span data-stu-id="1eb3d-122">Certificate settings</span></span>](certificates-configure.md)
       -  [<span data-ttu-id="1eb3d-123">Windows Information Protection-Einstellungen</span><span class="sxs-lookup"><span data-stu-id="1eb3d-123">Windows Information Protection settings</span></span>](windows-information-protection-configure.md)
       -  [<span data-ttu-id="1eb3d-124">Education-Einstellungen</span><span class="sxs-lookup"><span data-stu-id="1eb3d-124">Education settings</span></span>](education-settings-configure.md)
       -  [<span data-ttu-id="1eb3d-125">Benutzerdefinierte Einstellungen</span><span class="sxs-lookup"><span data-stu-id="1eb3d-125">Custom settings</span></span>](custom-settings-configure.md)

     ![Erstellen von Geräteprofilen](./media/create-device-profile.png)
7. <span data-ttu-id="1eb3d-127">Wählen Sie nach dem Konfigurieren der Einstellungen auf dem Blatt **Profil erstellen** die Option **Erstellen** aus.</span><span class="sxs-lookup"><span data-stu-id="1eb3d-127">Once you are done configuring settings, on the **Create Profile** blade, choose **Create**.</span></span>

<span data-ttu-id="1eb3d-128">Das Profil wird erstellt und auf dem Blatt mit der Profilliste angezeigt.</span><span class="sxs-lookup"><span data-stu-id="1eb3d-128">The profile is created and appears on the profiles list blade.</span></span>
<span data-ttu-id="1eb3d-129">Wenn Sie fortfahren und dieses Profil Gruppen zuweisen möchten, lesen Sie unter [Zuweisen von Geräteprofilen](device-profile-assign.md) nach.</span><span class="sxs-lookup"><span data-stu-id="1eb3d-129">If you want to go ahead and assign this profile to groups, see [How to assign device profiles](device-profile-assign.md).</span></span>


### <a name="next-steps"></a><span data-ttu-id="1eb3d-130">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="1eb3d-130">Next steps</span></span>
<span data-ttu-id="1eb3d-131">Informationen zum Zuweisen von Geräteprofilen finden Sie unter [Zuweisen von Geräteprofilen mit Microsoft Intune](device-profile-assign.md).</span><span class="sxs-lookup"><span data-stu-id="1eb3d-131">For information about how to assign device profiles, see [How to assign device profiles with Microsoft Intune](device-profile-assign.md).</span></span>
