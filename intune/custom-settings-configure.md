---
title: "Konfigurieren von benutzerdefinierten Intune-Geräteeinstellungen"
titleSuffix: Azure portal
description: "Erfahren Sie, wie Sie mit Intune benutzerdefinierte Einstellungen auf Geräten konfigurieren, die Sie verwalten.\""
keywords: 
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 06/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 42f9b104-c1f6-4dfc-8aa4-1d33e1eaf61f
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: d3b44cb606f0764fb655651a441889862fcbbe62
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2018
---
# <a name="how-to-configure-custom-device-settings-in-microsoft-intune"></a><span data-ttu-id="237ce-103">Konfigurieren von benutzerdefinierten Geräteeinstellungen in Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="237ce-103">How to configure custom device settings in Microsoft Intune</span></span>

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

## <a name="when-to-use-custom-settings"></a><span data-ttu-id="237ce-104">Verwenden von benutzerdefinierten Einstellungen</span><span class="sxs-lookup"><span data-stu-id="237ce-104">When to use custom settings</span></span>

<span data-ttu-id="237ce-105">Benutzerdefinierte Geräteeinstellungen können nützlich sein, wenn Intune nicht über die Einstellungen verfügt, die Sie konfigurieren möchten, diese aber für andere Geräteprofile verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="237ce-105">Custom device settings can be useful when Intune doesn't have the settings you want to configure built-in, and available from other device profiles.</span></span>
<span data-ttu-id="237ce-106">Benutzerdefinierte Einstellungen werden für jede Plattform anders konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="237ce-106">Custom settings are configured differently for each platform.</span></span> <span data-ttu-id="237ce-107">Bei Android- und Windows-Geräten können Sie beispielsweise OMA-URI-Werte (Open Mobile Alliance Uniform Resource Identifier) zum Steuern von Features auf Geräten angeben.</span><span class="sxs-lookup"><span data-stu-id="237ce-107">For example, with Android and Windows devices, you can specify Open Mobile Alliance Uniform Resource Identifier (OMA-URI) values to control features on devices.</span></span> <span data-ttu-id="237ce-108">Auf Apple-Geräten können Sie eine Datei importieren, die Sie mit [Apple Configurator](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12) erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="237ce-108">For Apple devices, you can import a file you created with the [Apple Configurator](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12).</span></span>

<span data-ttu-id="237ce-109">Anhand der Informationen in diesem Thema lernen Sie die Grundlagen zum Konfigurieren von Profilen mit benutzerdefinierten Einstellungen kennen. In den weiterführenden Themen zu den einzelnen Plattformen erfahren Sie etwas über Besonderheiten der jeweiligen Geräte.</span><span class="sxs-lookup"><span data-stu-id="237ce-109">Use the information in this topic to learn the basics about configuring profiles with custom settings, and then read further topics for each platform to learn about device specifics.</span></span>

## <a name="create-a-device-profile-containing-custom-settings"></a><span data-ttu-id="237ce-110">Erstellen eines Geräteprofils mit benutzerdefinierten Einstellungen</span><span class="sxs-lookup"><span data-stu-id="237ce-110">Create a device profile containing custom settings</span></span>

1. <span data-ttu-id="237ce-111">Melden Sie sich beim Azure-Portal an.</span><span class="sxs-lookup"><span data-stu-id="237ce-111">Sign into the Azure portal.</span></span>
2. <span data-ttu-id="237ce-112">Wählen Sie **Weitere Dienste** > **Überwachung und Verwaltung** > **Intune** aus.</span><span class="sxs-lookup"><span data-stu-id="237ce-112">Choose **More Services** > **Monitoring + Management** > **Intune**.</span></span>
3. <span data-ttu-id="237ce-113">Wählen Sie auf dem Blatt **Intune** die Option **Gerätekonfiguration** aus.</span><span class="sxs-lookup"><span data-stu-id="237ce-113">On the **Intune** blade, choose **Device configuration**.</span></span>
2. <span data-ttu-id="237ce-114">Wählen Sie auf dem Blatt **Gerätekonfiguration** die Option **Verwalten** > **Profile** aus.</span><span class="sxs-lookup"><span data-stu-id="237ce-114">On the **Device Configuration** blade, choose **Manage** > **Profiles**.</span></span>
3. <span data-ttu-id="237ce-115">Wählen Sie auf dem Blatt „Profile“ die Option **Profil erstellen** aus.</span><span class="sxs-lookup"><span data-stu-id="237ce-115">On the profiles blade, choose **Create Profile**.</span></span>
4. <span data-ttu-id="237ce-116">Geben Sie auf dem Blatt **Profil erstellen** einen **Namen** und eine **Beschreibung** für das benutzerdefinierte Profil ein.</span><span class="sxs-lookup"><span data-stu-id="237ce-116">On the **Create Profile** blade, enter a **Name** and **Description** for the custom profile.</span></span>
5. <span data-ttu-id="237ce-117">Wählen Sie in der Dropdownliste **Plattform** die Geräteplattform aus, auf die Sie benutzerdefinierte Einstellungen anwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="237ce-117">From the **Platform** drop-down list, select the device platform to which you want to apply custom settings.</span></span> <span data-ttu-id="237ce-118">Derzeit können Sie eine der folgenden Plattformen für die benutzerdefinierte Geräteeinstellungen auswählen:</span><span class="sxs-lookup"><span data-stu-id="237ce-118">Currently, you can choose one of the following platforms for custom device settings:</span></span>
    - <span data-ttu-id="237ce-119">**Android**</span><span class="sxs-lookup"><span data-stu-id="237ce-119">**Android**</span></span>
    - <span data-ttu-id="237ce-120">**iOS**</span><span class="sxs-lookup"><span data-stu-id="237ce-120">**iOS**</span></span>
    - <span data-ttu-id="237ce-121">**macOS**</span><span class="sxs-lookup"><span data-stu-id="237ce-121">**macOS**</span></span>
    - <span data-ttu-id="237ce-122">**Windows Phone 8.1**</span><span class="sxs-lookup"><span data-stu-id="237ce-122">**Windows Phone 8.1**</span></span>
    - <span data-ttu-id="237ce-123">**Windows 10 und höher**</span><span class="sxs-lookup"><span data-stu-id="237ce-123">**Windows 10 and later**</span></span>
6. <span data-ttu-id="237ce-124">Wählen Sie in der Dropdownliste **Profiltyp** die Option **Benutzerdefiniert** aus.</span><span class="sxs-lookup"><span data-stu-id="237ce-124">From the **Profile** type drop-down list, choose **Custom**.</span></span>
7. <span data-ttu-id="237ce-125">Die konfigurierbaren Einstellungen variieren je nach der ausgewählten Plattform.</span><span class="sxs-lookup"><span data-stu-id="237ce-125">Depending on the platform you chose, the settings you can configure will be different.</span></span> <span data-ttu-id="237ce-126">In den folgenden Themen finden Sie ausführliche Informationen zu den Einstellungen für die einzelnen Plattformen:</span><span class="sxs-lookup"><span data-stu-id="237ce-126">Go to one of the following topics for detailed settings for each platform:</span></span>
    - [<span data-ttu-id="237ce-127">Einstellungen für Android</span><span class="sxs-lookup"><span data-stu-id="237ce-127">Android settings</span></span>](custom-settings-android.md)
    - [<span data-ttu-id="237ce-128">Einstellungen für iOS</span><span class="sxs-lookup"><span data-stu-id="237ce-128">iOS settings</span></span>](custom-settings-ios.md)
    - [<span data-ttu-id="237ce-129">Einstellungen für macOS</span><span class="sxs-lookup"><span data-stu-id="237ce-129">macOS settings</span></span>](custom-settings-macos.md)
    - [<span data-ttu-id="237ce-130">Einstellungen für Windows Phone 8.1</span><span class="sxs-lookup"><span data-stu-id="237ce-130">Windows Phone 8.1 settings</span></span>](custom-settings-windows-phone-8-1.md)
    - [<span data-ttu-id="237ce-131">Einstellungen für Windows 10</span><span class="sxs-lookup"><span data-stu-id="237ce-131">Windows 10 settings</span></span>](custom-settings-windows-10.md)
    - [<span data-ttu-id="237ce-132">Einstellungen für Android for Work</span><span class="sxs-lookup"><span data-stu-id="237ce-132">Android for Work settings</span></span>](custom-settings-android-for-work.md)
8. <span data-ttu-id="237ce-133">Navigieren Sie anschließend zurück zum Blatt **Profil erstellen**, und klicken Sie auf **Erstellen**.</span><span class="sxs-lookup"><span data-stu-id="237ce-133">When you're done, go back to the **Create Profile** blade, and hit **Create**.</span></span>

<span data-ttu-id="237ce-134">Das Profil wird erstellt und auf dem Blatt mit der Profilliste angezeigt.</span><span class="sxs-lookup"><span data-stu-id="237ce-134">The profile will be created and appears on the profiles list blade.</span></span>
<span data-ttu-id="237ce-135">Wenn Sie fortfahren und dieses Profil Gruppen zuweisen möchten, lesen Sie unter [Zuweisen von Geräteprofilen](device-profile-assign.md) nach.</span><span class="sxs-lookup"><span data-stu-id="237ce-135">If you want to go ahead and assign this profile to groups, see [How to assign device profiles](device-profile-assign.md).</span></span>
