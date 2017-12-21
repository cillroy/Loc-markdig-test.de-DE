---
title: "Konfigurieren von Einstellungen für Geräteeinschränkungen in Intune"
titleSuffix: Azure portal
description: "In diesem Artikel erfahren Sie, wie Sie mit Intune Einstellungen und Funktionen auf Geräten, die Sie verwalten, konfigurieren."
keywords: 
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 04/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 42f9b104-c1f6-4dfc-8aa4-1d33e1eaf61f
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 0f51cb0ef85c772392458b8df328408657a84af8
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2017
---
# <a name="how-to-configure-device-restriction-settings-in-microsoft-intune"></a><span data-ttu-id="0e51c-103">So konfigurieren Sie Einstellungen für Geräteeinschränkungen in Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="0e51c-103">How to configure device restriction settings in Microsoft Intune</span></span>

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="0e51c-104">Mit Geräteeinschränkungen können Sie eine Vielzahl von Einstellungen und Features für eine ganze Reihe von Kategorien steuern, einschließlich Sicherheit, Browser, Hardware und Einstellungen zur Datenfreigabe.</span><span class="sxs-lookup"><span data-stu-id="0e51c-104">Device restrictions let you control a wide range of settings and features you manage across a range of categories including security, browser, hardware, and data sharing settings.</span></span> <span data-ttu-id="0e51c-105">Sie könnten beispielsweise ein Geräteeinschränkungsprofil erstellen, das verhindert, dass Benutzer von iOS-Geräten auf die Kamera des Geräts zugreifen.</span><span class="sxs-lookup"><span data-stu-id="0e51c-105">For example, you could create a device restriction profile that prevents users of iOS devices from accessing the device camera.</span></span>

<span data-ttu-id="0e51c-106">Anhand der Informationen in diesem Thema lernen Sie die Grundlagen zum Konfigurieren von Geräteeinschränkungsprofilen kennen. In den weiterführenden Themen zu den einzelnen Plattformen erfahren Sie etwas über Besonderheiten der jeweiligen Geräte.</span><span class="sxs-lookup"><span data-stu-id="0e51c-106">Use the information in this topic to learn the basics about configuring device restriction profiles, and then read further topics for each platform to learn about device specifics.</span></span>

<span data-ttu-id="0e51c-107">So erstellen Sie ein Geräteprofil, das Einstellungen für Geräteeinschränkungen enthält:</span><span class="sxs-lookup"><span data-stu-id="0e51c-107">To create a device profile containing device restriction settings:</span></span>

1. <span data-ttu-id="0e51c-108">Melden Sie sich beim Azure-Portal an.</span><span class="sxs-lookup"><span data-stu-id="0e51c-108">Sign into the Azure portal.</span></span>
2. <span data-ttu-id="0e51c-109">Wählen Sie **Weitere Dienste** > **Überwachung und Verwaltung** > **Intune** aus.</span><span class="sxs-lookup"><span data-stu-id="0e51c-109">Choose **More Services** > **Monitoring + Management** > **Intune**.</span></span>
3. <span data-ttu-id="0e51c-110">Wählen Sie auf dem Blatt **Intune** die Option **Geräte konfigurieren** aus.</span><span class="sxs-lookup"><span data-stu-id="0e51c-110">On the **Intune** blade, choose **Configure devices**.</span></span>
2. <span data-ttu-id="0e51c-111">Wählen Sie auf dem Blatt **Gerätekonfiguration** die Option **Verwalten** > **Profile** aus.</span><span class="sxs-lookup"><span data-stu-id="0e51c-111">On the **Device Configuration** blade, choose **Manage** > **Profiles**.</span></span>
3. <span data-ttu-id="0e51c-112">Wählen Sie auf dem Blatt „Profile“ die Option **Profil erstellen** aus.</span><span class="sxs-lookup"><span data-stu-id="0e51c-112">On the profiles blade, choose **Create Profile**.</span></span>
4. <span data-ttu-id="0e51c-113">Geben Sie auf dem Blatt **Profil erstellen** einen **Namen** und eine **Beschreibung** für das Geräteeinschränkungsprofil ein.</span><span class="sxs-lookup"><span data-stu-id="0e51c-113">On the **Create Profile** blade, enter a **Name** and **Description** for the device restriction profile.</span></span>
5. <span data-ttu-id="0e51c-114">Wählen Sie in der Dropdownliste **Plattform** die Geräteplattform aus, auf die Sie benutzerdefinierte Einstellungen anwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="0e51c-114">From the **Platform** drop-down list, select the device platform to which you want to apply custom settings.</span></span> <span data-ttu-id="0e51c-115">Derzeit können Sie eine der folgenden Plattformen für die Einstellungen für Geräteeinschränkungen auswählen:</span><span class="sxs-lookup"><span data-stu-id="0e51c-115">Currently, you can choose one of the following platforms for device restriction settings:</span></span>
    - <span data-ttu-id="0e51c-116">**Android**</span><span class="sxs-lookup"><span data-stu-id="0e51c-116">**Android**</span></span>
    - <span data-ttu-id="0e51c-117">**iOS**</span><span class="sxs-lookup"><span data-stu-id="0e51c-117">**iOS**</span></span>
    - <span data-ttu-id="0e51c-118">**macOS**</span><span class="sxs-lookup"><span data-stu-id="0e51c-118">**macOS**</span></span>
    - <span data-ttu-id="0e51c-119">**Windows Phone 8.1**</span><span class="sxs-lookup"><span data-stu-id="0e51c-119">**Windows Phone 8.1**</span></span>
    - <span data-ttu-id="0e51c-120">**Windows 8.1 und höher**</span><span class="sxs-lookup"><span data-stu-id="0e51c-120">**Windows 8.1 and later**</span></span>
    - <span data-ttu-id="0e51c-121">**Windows 10 und höher**</span><span class="sxs-lookup"><span data-stu-id="0e51c-121">**Windows 10 and later**</span></span>
6. <span data-ttu-id="0e51c-122">Wählen Sie in der Dropdownliste **Profiltyp** die Option **Geräteeinschränkungen** aus.</span><span class="sxs-lookup"><span data-stu-id="0e51c-122">From the **Profile type** type drop-down list, choose **Device restrictions**.</span></span> <span data-ttu-id="0e51c-123">Wenn Sie ein Geräteeinschränkungsprofil für Windows 10 Team-Geräte wie etwa ein Surface Hub erstellen möchten, wählen Sie **Geräteeinschränkungen (Windows 10 Team)** aus.</span><span class="sxs-lookup"><span data-stu-id="0e51c-123">If you want to create a device restrictions profile for Windows 10 Team devices like a Surface Hub, choose **Device restrictions (Windows 10 Team)**.</span></span>
7. <span data-ttu-id="0e51c-124">Die konfigurierbaren Einstellungen variieren je nach der ausgewählten Plattform.</span><span class="sxs-lookup"><span data-stu-id="0e51c-124">Depending on the platform you chose, the settings you can configure will be different.</span></span> <span data-ttu-id="0e51c-125">In den folgenden Themen finden Sie ausführliche Informationen zu den Einstellungen für die einzelnen Plattformen:</span><span class="sxs-lookup"><span data-stu-id="0e51c-125">Go to one of the following topics for detailed settings for each platform:</span></span>
    - [<span data-ttu-id="0e51c-126">Einstellungen für Android</span><span class="sxs-lookup"><span data-stu-id="0e51c-126">Android settings</span></span>](device-restrictions-android.md)
    - [<span data-ttu-id="0e51c-127">Einstellungen für iOS</span><span class="sxs-lookup"><span data-stu-id="0e51c-127">iOS settings</span></span>](device-restrictions-ios.md)
    - [<span data-ttu-id="0e51c-128">Einstellungen für macOS</span><span class="sxs-lookup"><span data-stu-id="0e51c-128">macOS settings</span></span>](device-restrictions-macos.md)
    - [<span data-ttu-id="0e51c-129">Einstellungen für Windows Phone 8.1</span><span class="sxs-lookup"><span data-stu-id="0e51c-129">Windows Phone 8.1 settings</span></span>](device-restrictions-windows-phone-8-1.md)
    - [<span data-ttu-id="0e51c-130">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="0e51c-130">Windows 8.1</span></span>](device-restrictions-windows-8-1.md)
    - [<span data-ttu-id="0e51c-131">Einstellungen für Windows 10</span><span class="sxs-lookup"><span data-stu-id="0e51c-131">Windows 10 settings</span></span>](device-restrictions-windows-10.md)
    - [<span data-ttu-id="0e51c-132">Einstellungen für Windows 10 Team</span><span class="sxs-lookup"><span data-stu-id="0e51c-132">Windows 10 Team settings</span></span>](device-restrictions-windows-10-teams.md)
    - [<span data-ttu-id="0e51c-133">Einstellungen für Android for Work</span><span class="sxs-lookup"><span data-stu-id="0e51c-133">Android for Work settings</span></span>](device-restrictions-android-for-work.md)
8. <span data-ttu-id="0e51c-134">Navigieren Sie anschließend zurück zum Blatt **Profil erstellen**, und klicken Sie auf **Erstellen**.</span><span class="sxs-lookup"><span data-stu-id="0e51c-134">When you're done, go back to the **Create Profile** blade, and hit **Create**.</span></span>

<span data-ttu-id="0e51c-135">Das Profil wird erstellt und auf dem Blatt mit der Profilliste angezeigt.</span><span class="sxs-lookup"><span data-stu-id="0e51c-135">The profile will be created and appears on the profiles list blade.</span></span>
<span data-ttu-id="0e51c-136">Wenn Sie fortfahren und dieses Profil Gruppen zuweisen möchten, lesen Sie unter [Zuweisen von Geräteprofilen](device-profile-assign.md) nach.</span><span class="sxs-lookup"><span data-stu-id="0e51c-136">If you want to go ahead and assign this profile to groups, see [How to assign device profiles](device-profile-assign.md).</span></span>

<!--  Removing image as part of design review; retaining source until we known the disposition.

## Example of device restriction settings

In this high-level example, you'll create a device restriction policy that blocks the use of the built-in camera app on Android devices.

![How to disable the camera on Android devices](./media/disable-android-camera.png)

-->