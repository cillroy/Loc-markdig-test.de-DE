---
title: So konfigurieren Sie Intune-WLAN-Einstellungen
titleSuffix: Azure portal
description: "Erfahren Sie, wie Sie mit Intune WLAN-Einstellungen auf Geräten konfigurieren, die Sie verwalten."
keywords: 
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 06/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 1fadb488-9c6c-43c1-ba23-8c69db633b96
ms.reviewer: karanda
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: f42d12ddcfc0e2eef8d99102cebae460cdcb29bb
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2017
---
# <a name="how-to-configure-wi-fi-settings-in-microsoft-intune"></a><span data-ttu-id="7085a-103">So konfigurieren Sie WLAN-Einstellungen in Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="7085a-103">How to configure Wi-Fi settings in Microsoft Intune</span></span>

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="7085a-104">Verwenden Sie WLAN-Profile in Microsoft Intune, um Benutzern und Geräten in Ihrer Organisation Einstellungen für Drahtlosnetzwerke zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="7085a-104">Use Microsoft Intune Wi-Fi profiles to assign wireless network settings to users and devices in your organization.</span></span> <span data-ttu-id="7085a-105">Wenn Sie ein WLAN-Profil zuweisen, erhalten Ihre Benutzer Zugriff auf Ihr Unternehmens-WLAN, ohne es selbst konfigurieren zu müssen.</span><span class="sxs-lookup"><span data-stu-id="7085a-105">When you assign a Wi-Fi profile, your users will have access to your corporate Wi-Fi network without having to configure it themselves.</span></span>

<span data-ttu-id="7085a-106">Beispiel: Sie installieren ein neues WLAN mit dem Namen „Contoso Wi-Fi“ und möchten alle iOS-Geräte so einrichten, dass sie eine Verbindung mit diesem Netzwerk herstellen können.</span><span class="sxs-lookup"><span data-stu-id="7085a-106">For example, you install a new Wi-Fi network named Contoso Wi-Fi and want to set up all iOS devices to connect to this network.</span></span> <span data-ttu-id="7085a-107">Gehen Sie dazu folgendermaßen vor:</span><span class="sxs-lookup"><span data-stu-id="7085a-107">Here's the process:</span></span>

1. <span data-ttu-id="7085a-108">Erstellen Sie ein WLAN-Profil mit den Einstellungen, die zum Verbinden mit dem Drahtlosnetzwerk „Contoso Wi-Fi“ erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="7085a-108">Create a Wi-Fi profile containing the settings necessary to connect to the Contoso Wi-Fi wireless network.</span></span>
2. <span data-ttu-id="7085a-109">Weisen Sie das Profil einer Gruppe zu, die alle Benutzer von iOS-Geräten enthält.</span><span class="sxs-lookup"><span data-stu-id="7085a-109">Assign the profile to a group containing all users of iOS devices.</span></span>
3. <span data-ttu-id="7085a-110">Auf den Geräten der Benutzer erscheint das Netzwerk „Contoso Wi-Fi“ in der Liste der Drahtlosnetzwerke, und es kann bequem eine Verbindung mit diesem Netzwerk hergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="7085a-110">Users find the new Contoso Wi-Fi network in the list of wireless networks on their device and can easily connect to it.</span></span>

<span data-ttu-id="7085a-111">WLAN-Profile unterstützen folgende Geräteplattformen:</span><span class="sxs-lookup"><span data-stu-id="7085a-111">Wi-Fi profiles support the following device platforms:</span></span>

- <span data-ttu-id="7085a-112">Android 4 und höher</span><span class="sxs-lookup"><span data-stu-id="7085a-112">Android 4 and later</span></span>
- <span data-ttu-id="7085a-113">Android for Work</span><span class="sxs-lookup"><span data-stu-id="7085a-113">Android for Work</span></span>
- <span data-ttu-id="7085a-114">iOS 8.0 und höher</span><span class="sxs-lookup"><span data-stu-id="7085a-114">iOS 8.0 and later</span></span>
- <span data-ttu-id="7085a-115">macOS (Mac OS X 10.9 und höher)</span><span class="sxs-lookup"><span data-stu-id="7085a-115">macOS (Mac OS X 10.9 and later)</span></span>

<span data-ttu-id="7085a-116">Auf Geräten mit Windows 8.1, Windows 10 und Windows 10 Mobile können Sie eine WLAN-Konfiguration importieren, die zuvor von einem anderen Gerät exportiert wurde.</span><span class="sxs-lookup"><span data-stu-id="7085a-116">For devices running Windows 8.1, Windows 10, and Windows 10 Mobile, you can import a Wi-Fi configuration that was previously exported from another device.</span></span>

<span data-ttu-id="7085a-117">Anhand der Informationen in diesem Thema lernen Sie die Grundlagen zum Konfigurieren von WLAN-Profilen kennen. In den weiterführenden Themen zu den einzelnen Plattformen erfahren Sie etwas über Besonderheiten der jeweiligen Geräte.</span><span class="sxs-lookup"><span data-stu-id="7085a-117">Use the information in this topic to learn the basics about configuring a Wi-Fi profile, and then read further topics for each platform to learn about device specifics.</span></span>

## <a name="create-a-device-profile-containing-wi-fi-settings"></a><span data-ttu-id="7085a-118">Erstellen eines Geräteprofils mit WLAN-Einstellungen</span><span class="sxs-lookup"><span data-stu-id="7085a-118">Create a device profile containing Wi-Fi settings</span></span>

1. <span data-ttu-id="7085a-119">Melden Sie sich beim Azure-Portal an.</span><span class="sxs-lookup"><span data-stu-id="7085a-119">Sign into the Azure portal.</span></span>
2. <span data-ttu-id="7085a-120">Wählen Sie **Weitere Dienste** > **Überwachung und Verwaltung** > **Intune** aus.</span><span class="sxs-lookup"><span data-stu-id="7085a-120">Choose **More Services** > **Monitoring + Management** > **Intune**.</span></span>
3. <span data-ttu-id="7085a-121">Wählen Sie auf dem Blatt **Intune** die Option **Gerätekonfiguration** aus.</span><span class="sxs-lookup"><span data-stu-id="7085a-121">On the **Intune** blade, choose **Device configuration**.</span></span>
2. <span data-ttu-id="7085a-122">Wählen Sie auf dem Blatt **Gerätekonfiguration** die Option **Verwalten** > **Profile** aus.</span><span class="sxs-lookup"><span data-stu-id="7085a-122">On the **Device Configuration** blade, choose **Manage** > **Profiles**.</span></span>
3. <span data-ttu-id="7085a-123">Wählen Sie auf dem Blatt „Profile“ die Option **Profil erstellen** aus.</span><span class="sxs-lookup"><span data-stu-id="7085a-123">On the profiles blade, choose **Create Profile**.</span></span>
4. <span data-ttu-id="7085a-124">Geben Sie auf dem Blatt **Profil erstellen** einen **Namen** und eine **Beschreibung** für das WLAN-Profil ein.</span><span class="sxs-lookup"><span data-stu-id="7085a-124">On the **Create Profile** blade, enter a **Name** and **Description** for the Wi-Fi profile.</span></span>
5. <span data-ttu-id="7085a-125">Wählen Sie in der Dropdownliste **Plattform** die Geräteplattform aus, auf die Sie WLAN-Einstellungen anwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="7085a-125">From the **Platform** drop-down list, select the device platform to which you want to apply Wi-Fi settings.</span></span> <span data-ttu-id="7085a-126">Derzeit können Sie eine der folgenden Plattformen für die WLAN-Einstellungen auswählen:</span><span class="sxs-lookup"><span data-stu-id="7085a-126">Currently, you can choose one of the following platforms for Wi-Fi settings:</span></span>
    - <span data-ttu-id="7085a-127">**Android**</span><span class="sxs-lookup"><span data-stu-id="7085a-127">**Android**</span></span>
    - <span data-ttu-id="7085a-128">**Android for Work**</span><span class="sxs-lookup"><span data-stu-id="7085a-128">**Android for Work**</span></span>
    - <span data-ttu-id="7085a-129">**iOS**</span><span class="sxs-lookup"><span data-stu-id="7085a-129">**iOS**</span></span>
    - <span data-ttu-id="7085a-130">**macOS**</span><span class="sxs-lookup"><span data-stu-id="7085a-130">**macOS**</span></span>
    - <span data-ttu-id="7085a-131">**Windows 8.1 und höher (Profil importieren)**</span><span class="sxs-lookup"><span data-stu-id="7085a-131">**Windows 8.1 and later (import a profile)**</span></span>
6. <span data-ttu-id="7085a-132">Wählen Sie in der Dropdownliste **Profiltyp** die Option **Basis-WLAN** oder **Unternehmens-WLAN** aus.</span><span class="sxs-lookup"><span data-stu-id="7085a-132">From the **Profile** type drop-down list, choose **Wi-Fi basic** or **Wi-Fi enterprise**.</span></span> <span data-ttu-id="7085a-133">Mithilfe von **Basis-WLAN** können Sie grundlegende Eigenschaften wie den Netzwerknamen und die SSID angeben.</span><span class="sxs-lookup"><span data-stu-id="7085a-133">You can use **Wi-fi basic** to supply basic features like the network name, and the SSID.</span></span> <span data-ttu-id="7085a-134">Mit **Unternehmens-WLAN** können Sie detailliertere Informationen angeben, z.B. das Extensible Authentication Protocol (EAP), sofern dieses in Ihrem WLAN verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="7085a-134">**Wi-Fi enterprise** lets you supply more advanced information like the  Extensible Authentication Protocol (EAP) if your Wi-Fi network uses this.</span></span> <span data-ttu-id="7085a-135">Mit **WLAN (Import)** (für Windows 8.1 und Windows 10) können Sie WLAN-Einstellungen als XML-Datei importieren, die Sie zuvor von einem anderen Gerät exportiert haben.</span><span class="sxs-lookup"><span data-stu-id="7085a-135">**Wi-Fi import** (for Windows 8.1 and Windows 10) lets you import Wi-Fi settings as an XML file that you previously exported from a different device.</span></span>
7. <span data-ttu-id="7085a-136">Die konfigurierbaren Einstellungen variieren je nach der ausgewählten Plattform.</span><span class="sxs-lookup"><span data-stu-id="7085a-136">Depending on the platform you chose, the settings you can configure will be different.</span></span> <span data-ttu-id="7085a-137">In den folgenden Themen finden Sie ausführliche Informationen zu den Einstellungen für die einzelnen Plattformen:</span><span class="sxs-lookup"><span data-stu-id="7085a-137">Go to one of the following topics for detailed settings for each platform:</span></span>
    - [<span data-ttu-id="7085a-138">Einstellungen für Android und Android for Work</span><span class="sxs-lookup"><span data-stu-id="7085a-138">Android and Android for Work settings</span></span>](wi-fi-settings-android.md)
    - [<span data-ttu-id="7085a-139">Einstellungen für iOS</span><span class="sxs-lookup"><span data-stu-id="7085a-139">iOS settings</span></span>](wi-fi-settings-ios.md)
    - [<span data-ttu-id="7085a-140">Einstellungen für macOS</span><span class="sxs-lookup"><span data-stu-id="7085a-140">macOS settings</span></span>](wi-fi-settings-macos.md)
    - [<span data-ttu-id="7085a-141">Einstellungen für Windows Phone 8.1</span><span class="sxs-lookup"><span data-stu-id="7085a-141">Windows Phone 8.1 settings</span></span>](wi-fi-settings-import-windows-8-1.md)
8. <span data-ttu-id="7085a-142">Navigieren Sie anschließend zurück zum Blatt **Profil erstellen**, und klicken Sie auf **Erstellen**.</span><span class="sxs-lookup"><span data-stu-id="7085a-142">When you're done, go back to the **Create Profile** blade, and hit **Create**.</span></span>

<span data-ttu-id="7085a-143">Das Profil wird erstellt und auf dem Blatt mit der Profilliste angezeigt.</span><span class="sxs-lookup"><span data-stu-id="7085a-143">The profile will be created and appears on the profiles list blade.</span></span>
<span data-ttu-id="7085a-144">Wenn Sie fortfahren und dieses Profil Gruppen zuweisen möchten, lesen Sie unter [Zuweisen von Geräteprofilen](device-profile-assign.md) nach.</span><span class="sxs-lookup"><span data-stu-id="7085a-144">If you want to go ahead and assign this profile to groups, see [How to assign device profiles](device-profile-assign.md).</span></span>
