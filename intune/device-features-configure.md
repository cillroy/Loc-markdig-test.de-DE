---
title: "Konfigurieren der Einstellungen für Gerätefunktionen in Intune"
titleSuffix: Azure portal
description: "Erfahren Sie, wie Sie mit Intune Funktionen auf Geräten konfigurieren, die Sie verwalten.\""
keywords: 
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 12/7/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 42f9b104-c1f6-4dfc-8aa4-1d33e1eaf61f
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: e32db4d990f3c5af3eed2f1785bc23287f7288cd
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2018
---
# <a name="how-to-configure-device-feature-settings-in-microsoft-intune"></a><span data-ttu-id="26851-103">Konfigurieren der Einstellungen für Gerätefunktionen in Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="26851-103">How to configure device feature settings in Microsoft Intune</span></span>

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="26851-104">Mit Geräteeinschränkungen können Sie Funktionen auf iOS- und macOS-Geräten wie AirPrint, Benachrichtigungen und freigegebene Gerätekonfigurationen steuern.</span><span class="sxs-lookup"><span data-stu-id="26851-104">Device restrictions let you control features on iOS and macOS devices like AirPrint, notifications, and shared device configurations.</span></span>

<span data-ttu-id="26851-105">Anhand der Informationen in diesem Thema lernen Sie die Grundlagen zum Konfigurieren von Gerätefunktionsprofilen kennen. In den weiterführenden Themen zu den einzelnen Plattformen erfahren Sie etwas über Besonderheiten der jeweiligen Geräte.</span><span class="sxs-lookup"><span data-stu-id="26851-105">Use the information in this topic to learn the basics about configuring device feature profiles, and then read further topics for each platform to learn about device specifics.</span></span>

## <a name="create-a-device-profile-containing-device-restriction-settings"></a><span data-ttu-id="26851-106">Erstellen von Geräteprofilen mit Einstellungen für Geräteeinschränkungen</span><span class="sxs-lookup"><span data-stu-id="26851-106">Create a device profile containing device restriction settings</span></span>

1. <span data-ttu-id="26851-107">Melden Sie sich beim Azure-Portal an.</span><span class="sxs-lookup"><span data-stu-id="26851-107">Sign into the Azure portal.</span></span>
2. <span data-ttu-id="26851-108">Wählen Sie **Weitere Dienste** > **Überwachung und Verwaltung** > **Intune** aus.</span><span class="sxs-lookup"><span data-stu-id="26851-108">Choose **More Services** > **Monitoring + Management** > **Intune**.</span></span>
3. <span data-ttu-id="26851-109">Wählen Sie auf dem Blatt **Intune** die Option **Gerätekonfiguration** aus.</span><span class="sxs-lookup"><span data-stu-id="26851-109">On the **Intune** blade, choose **Device configuration**.</span></span>
2. <span data-ttu-id="26851-110">Wählen Sie auf dem Blatt **Gerätekonfiguration** die Option **Verwalten** > **Profile** aus.</span><span class="sxs-lookup"><span data-stu-id="26851-110">On the **Device Configuration** blade, choose **Manage** > **Profiles**.</span></span>
3. <span data-ttu-id="26851-111">Wählen Sie auf dem Blatt „Profile“ die Option **Profil erstellen** aus.</span><span class="sxs-lookup"><span data-stu-id="26851-111">On the profiles blade, choose **Create Profile**.</span></span>
4. <span data-ttu-id="26851-112">Geben Sie auf dem Blatt **Profil erstellen** einen **Namen** und eine **Beschreibung** für das Gerätefunktionsprofil ein.</span><span class="sxs-lookup"><span data-stu-id="26851-112">On the **Create Profile** blade, enter a **Name** and **Description** for the device features profile.</span></span>
5. <span data-ttu-id="26851-113">Wählen Sie in der Dropdownliste **Plattform** die Geräteplattform aus, auf die Sie die Einstellungen anwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="26851-113">From the **Platform** drop-down list, select the device platform to which you want to apply the settings.</span></span> <span data-ttu-id="26851-114">Derzeit können Sie eine der folgenden Plattformen für Gerätefunktionen auswählen:</span><span class="sxs-lookup"><span data-stu-id="26851-114">Currently, you can choose one of the following platforms for device features:</span></span>
    - <span data-ttu-id="26851-115">**iOS**</span><span class="sxs-lookup"><span data-stu-id="26851-115">**iOS**</span></span>
    - <span data-ttu-id="26851-116">**macOS**</span><span class="sxs-lookup"><span data-stu-id="26851-116">**macOS**</span></span>
6. <span data-ttu-id="26851-117">Wählen Sie in der Dropdownliste **Profiltyp** die Option **Gerätefunktionen** aus.</span><span class="sxs-lookup"><span data-stu-id="26851-117">From the **Profile type** drop-down list, choose **Device features**.</span></span> 
7. <span data-ttu-id="26851-118">Die konfigurierbaren Einstellungen variieren je nach der ausgewählten Plattform.</span><span class="sxs-lookup"><span data-stu-id="26851-118">Depending on the platform you chose, the settings you can configure will be different.</span></span> <span data-ttu-id="26851-119">In den folgenden Themen finden Sie ausführliche Informationen zu den Einstellungen für die einzelnen Plattformen:</span><span class="sxs-lookup"><span data-stu-id="26851-119">Go to one of the following topics for detailed settings for each platform:</span></span>
    - <span data-ttu-id="26851-120">[AirPrint settings for iOS and MacOS](air-print-settings-ios-macos.md) (AirPrint-Einstellungen für iOS- und macOS-Geräte)</span><span class="sxs-lookup"><span data-stu-id="26851-120">[AirPrint settings for iOS and MacOS](air-print-settings-ios-macos.md)</span></span>
    - <span data-ttu-id="26851-121">[AirPlay settings for iOS](airplay-settings-ios.md) (AirPlay-Einstellungen für iOS-Geräte)</span><span class="sxs-lookup"><span data-stu-id="26851-121">[AirPlay settings for iOS](airplay-settings-ios.md)</span></span>
    - <span data-ttu-id="26851-122">[Home screen layout settings for iOS](home-screen-settings-ios.md) (Einstellungen des Startbildschirmlayouts für iOS-Geräte)</span><span class="sxs-lookup"><span data-stu-id="26851-122">[Home screen layout settings for iOS](home-screen-settings-ios.md)</span></span>
    - <span data-ttu-id="26851-123">[App notification settings for iOS](app-notification-settings-ios.md) (App-Benachrichtigungseinstellungen für iOS-Geräte)</span><span class="sxs-lookup"><span data-stu-id="26851-123">[App notification settings for iOS](app-notification-settings-ios.md)</span></span>
    - <span data-ttu-id="26851-124">[Shared device configuration settings for iOS](shared-device-settings-ios.md) (Konfigurationseinstellungen für freigegebene iOS-Geräte)</span><span class="sxs-lookup"><span data-stu-id="26851-124">[Shared device configuration settings for iOS](shared-device-settings-ios.md)</span></span>
    - [<span data-ttu-id="26851-125">Konfigurieren von Intune für einmaliges Anmelden von iOS-Geräten</span><span class="sxs-lookup"><span data-stu-id="26851-125">Configure Intune for iOS device Single Sign-on</span></span>](sso-ios.md)
    - <span data-ttu-id="26851-126">[Web content filter settings for iOS](web-content-filter-settings-ios.md) (Filtereinstellungen für Webinhalte für iOS-Geräte)</span><span class="sxs-lookup"><span data-stu-id="26851-126">[Web content filter settings for iOS](web-content-filter-settings-ios.md)</span></span>

8. <span data-ttu-id="26851-127">Navigieren Sie anschließend zurück zum Blatt **Profil erstellen**, und klicken Sie auf **Erstellen**.</span><span class="sxs-lookup"><span data-stu-id="26851-127">When you're done, go back to the **Create Profile** blade, and click **Create**.</span></span>

<span data-ttu-id="26851-128">Das Profil wird erstellt und auf dem Blatt mit der Profilliste angezeigt.</span><span class="sxs-lookup"><span data-stu-id="26851-128">The profile is created and appears on the profiles list blade.</span></span>
<span data-ttu-id="26851-129">Wenn Sie fortfahren und dieses Profil Gruppen zuweisen möchten, lesen Sie unter [Zuweisen von Geräteprofilen](device-profile-assign.md) nach.</span><span class="sxs-lookup"><span data-stu-id="26851-129">If you want to go ahead and assign this profile to groups, see [How to assign device profiles](device-profile-assign.md).</span></span>



