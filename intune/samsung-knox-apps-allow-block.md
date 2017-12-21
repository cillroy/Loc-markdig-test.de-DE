---
title: "Intune-Richtlinie zum Zulassen/Blockieren von Apps für Samsung KNOX"
titlesuffix: Azure portal
description: "Erstellen Sie ein benutzerdefiniertes Profil zum Zulassen und Blockieren von Apps für Samsung KNOX Standard-Geräte.\""
keywords: 
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 06/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d035ebf5-85f4-4001-a249-75d24325061a
ms.reviewer: chrisbal
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 2974ce27e2eeff66356d26f80b8844b42e6a83b1
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2017
---
# <a name="use-custom-policies-to-allow-and-block-apps-for-samsung-knox-standard-devices-in-microsoft-intune"></a><span data-ttu-id="66858-103">Verwenden von benutzerdefinierten Richtlinien zum Zulassen und Blockieren von Apps für Samsung KNOX Standardgeräte in Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="66858-103">Use custom policies to allow and block apps for Samsung KNOX Standard devices in Microsoft Intune</span></span>

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="66858-104">Verwenden Sie die Verfahren in diesem Thema, um eine benutzerdefinierte Microsoft Intune-Richtlinie zu erstellen, die eine der folgenden Listen erstellt:</span><span class="sxs-lookup"><span data-stu-id="66858-104">Use the procedures in this topic to create a Microsoft Intune custom policy that creates one of the following:</span></span>

- <span data-ttu-id="66858-105">Eine Liste von Apps, deren Ausführung auf dem Gerät blockiert wird.</span><span class="sxs-lookup"><span data-stu-id="66858-105">A list of apps that are blocked from running on the device.</span></span> <span data-ttu-id="66858-106">Die Ausführung der Apps in dieser Liste wird blockiert, auch wenn diese bereits vor der Anwendung der Richtlinie installiert waren.</span><span class="sxs-lookup"><span data-stu-id="66858-106">Apps in this list are blocked from being run, even if they were already installed when the policy was applied.</span></span>
- <span data-ttu-id="66858-107">Eine Liste von Apps, die Benutzer des Geräts aus dem Google Play Store installieren dürfen.</span><span class="sxs-lookup"><span data-stu-id="66858-107">A list of apps that users of the device are allowed to install from the Google Play store.</span></span> <span data-ttu-id="66858-108">Nur die aufgelisteten Apps können installiert werden.</span><span class="sxs-lookup"><span data-stu-id="66858-108">Only the apps you list can be installed.</span></span> <span data-ttu-id="66858-109">Es können keine anderen Apps aus dem Store installiert werden.</span><span class="sxs-lookup"><span data-stu-id="66858-109">No other apps can be installed from the store.</span></span>

<span data-ttu-id="66858-110">Diese Einstellungen können nur von Geräten verwendet werden, auf denen Samsung KNOX Standard ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="66858-110">These settings can only be used by devices that run Samsung KNOX Standard.</span></span>

## <a name="create-an-allowed-or-blocked-app-list"></a><span data-ttu-id="66858-111">Erstellen einer Liste mit zulässigen oder blockierten Apps</span><span class="sxs-lookup"><span data-stu-id="66858-111">Create an allowed or blocked app list</span></span>

1. <span data-ttu-id="66858-112">Melden Sie sich beim Azure-Portal an.</span><span class="sxs-lookup"><span data-stu-id="66858-112">Sign into the Azure portal.</span></span>
2. <span data-ttu-id="66858-113">Wählen Sie **Weitere Dienste** > **Überwachung und Verwaltung** > **Intune** aus.</span><span class="sxs-lookup"><span data-stu-id="66858-113">Choose **More Services** > **Monitoring + Management** > **Intune**.</span></span>
3. <span data-ttu-id="66858-114">Wählen Sie auf dem Blatt **Intune** die Option **Gerätekonfiguration** aus.</span><span class="sxs-lookup"><span data-stu-id="66858-114">On the **Intune** blade, choose **Device configuration**.</span></span>
2. <span data-ttu-id="66858-115">Wählen Sie auf dem Blatt **Gerätekonfiguration** die Option **Verwalten** > **Profile** aus.</span><span class="sxs-lookup"><span data-stu-id="66858-115">On the **Device Configuration** blade, choose **Manage** > **Profiles**.</span></span>
2. <span data-ttu-id="66858-116">Wählen Sie auf dem Blatt mit der Profilliste die Option **Profil erstellen** aus.</span><span class="sxs-lookup"><span data-stu-id="66858-116">In the list of profiles blade, choose **Create Profile**.</span></span>
3. <span data-ttu-id="66858-117">Geben Sie auf dem Blatt **Profil erstellen** einen **Namen** und eine optionale **Beschreibung** für dieses Geräteprofil ein.</span><span class="sxs-lookup"><span data-stu-id="66858-117">On the **Create Profile** blade, enter a **Name** and optional **Description** for this device profile.</span></span>
2. <span data-ttu-id="66858-118">Wählen Sie als **Plattformtyp** die Option **Android** und als Profiltyp **Benutzerdefiniert** aus.</span><span class="sxs-lookup"><span data-stu-id="66858-118">Choose a **Platform type** of **Android**, and a Profile type of **Custom**.</span></span>
3. <span data-ttu-id="66858-119">Klicken Sie auf **Einstellungen**.</span><span class="sxs-lookup"><span data-stu-id="66858-119">Click **Settings**.</span></span>
3. <span data-ttu-id="66858-120">Wählen Sie auf dem Blatt **Benutzerdefinierte OMA-URI-Einstellungen** die Option **Hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="66858-120">On the **Custom OMA-URI Settings** blade, choose **Add**.</span></span>
4. <span data-ttu-id="66858-121">Geben Sie im Dialogfeld **OMA-URI-Einstellung hinzufügen oder bearbeiten** Folgendes an:</span><span class="sxs-lookup"><span data-stu-id="66858-121">In the **Add or Edit OMA-URI Setting** dialog box, specify the following:</span></span>

### <a name="for-a-list-of-apps-that-are-blocked-from-running-on-the-device"></a><span data-ttu-id="66858-122">Für eine Liste von Apps, deren Ausführung auf dem Gerät blockiert wird:</span><span class="sxs-lookup"><span data-stu-id="66858-122">For a list of apps that are blocked from running on the device:</span></span>

- <span data-ttu-id="66858-123">**Name:** Geben Sie **PreventStartPackages** ein.</span><span class="sxs-lookup"><span data-stu-id="66858-123">**Name** - Enter **PreventStartPackages**.</span></span>
- <span data-ttu-id="66858-124">**Beschreibung:** Geben Sie optional eine Beschreibung wie z.B. „Liste der Apps, deren Ausführung blockiert wird“ ein.</span><span class="sxs-lookup"><span data-stu-id="66858-124">**Description** - Enter an optional description like 'List of apps that are blocked from running.'</span></span>
-   <span data-ttu-id="66858-125">**Datentyp:** Wählen Sie in der Dropdownliste **Zeichenfolge** aus.</span><span class="sxs-lookup"><span data-stu-id="66858-125">**Data type** - From the drop-down list, choose **String**.</span></span>
-   <span data-ttu-id="66858-126">**OMA-URI:** Geben Sie **./Vendor/MSFT/PolicyManager/My/ApplicationManagement/PreventStartPackages** ein.</span><span class="sxs-lookup"><span data-stu-id="66858-126">**OMA-URI** - Enter **./Vendor/MSFT/PolicyManager/My/ApplicationManagement/PreventStartPackages**</span></span>
-   <span data-ttu-id="66858-127">**Wert:** Geben Sie eine Liste mit den Namen der App-Pakete ein, die Sie zulassen möchten.</span><span class="sxs-lookup"><span data-stu-id="66858-127">**Value** - Enter a list of the app package names you want to allow.</span></span> <span data-ttu-id="66858-128">Sie können **; : ,** oder **|** als Trennzeichen verwenden.</span><span class="sxs-lookup"><span data-stu-id="66858-128">You can use **; : ,** or **|** as a delimiter.</span></span> <span data-ttu-id="66858-129">(Beispiel: Paket1; Paket2;)</span><span class="sxs-lookup"><span data-stu-id="66858-129">(Example: package1;package2;)</span></span>

### <a name="for-a-list-of-apps-that-users-are-allowed-to-install-from-the-google-play-store-while-excluding-all-other-apps"></a><span data-ttu-id="66858-130">Für eine Liste von Apps, die Benutzer des Geräts aus Google Play Store installieren dürfen, wobei alle anderen Apps ausgeschlossen werden:</span><span class="sxs-lookup"><span data-stu-id="66858-130">For a list of apps that users are allowed to install from the Google Play store while excluding all other apps:</span></span>
- <span data-ttu-id="66858-131">**Name:** Geben Sie **AllowInstallPackages** ein.</span><span class="sxs-lookup"><span data-stu-id="66858-131">**Name** - Enter **AllowInstallPackages**.</span></span>
- <span data-ttu-id="66858-132">**Beschreibung:** Geben Sie optional eine Beschreibung wie z.B. „Liste der Apps, die Benutzer aus Google Play installieren dürfen“ ein.</span><span class="sxs-lookup"><span data-stu-id="66858-132">**Description** - Enter an optional description like 'List of apps that users can install from Google Play.'</span></span>
- <span data-ttu-id="66858-133">**Datentyp:** Wählen Sie in der Dropdownliste **Zeichenfolge** aus.</span><span class="sxs-lookup"><span data-stu-id="66858-133">**Data type** - From the drop-down list, choose **String**.</span></span>
- <span data-ttu-id="66858-134">**OMA-URI:** Geben Sie **./Vendor/MSFT/PolicyManager/My/ApplicationManagement/AllowInstallPackages** ein.</span><span class="sxs-lookup"><span data-stu-id="66858-134">**OMA-URI** - Enter **./Vendor/MSFT/PolicyManager/My/ApplicationManagement/AllowInstallPackages**</span></span>
- <span data-ttu-id="66858-135">**Wert:** Geben Sie eine Liste mit den Namen der App-Pakete ein, die Sie zulassen möchten.</span><span class="sxs-lookup"><span data-stu-id="66858-135">**Value** - Enter a list of the app package names you want to allow.</span></span> <span data-ttu-id="66858-136">Sie können **; : ,** oder **|** als Trennzeichen verwenden.</span><span class="sxs-lookup"><span data-stu-id="66858-136">You can use **; : ,** or **|** as a delimiter.</span></span> <span data-ttu-id="66858-137">(Beispiel: Paket1; Paket2;)</span><span class="sxs-lookup"><span data-stu-id="66858-137">(Example: package1;package2;)</span></span>

4. <span data-ttu-id="66858-138">Klicken Sie auf **OK**, und wählen Sie dann auf dem Blatt **Profil erstellen** die Option **Erstellen** aus.</span><span class="sxs-lookup"><span data-stu-id="66858-138">Click **OK**, and then, on the **Create Profile** blade, choose **Create**.</span></span>

>[!TIP]
> <span data-ttu-id="66858-139">Sie finden die Paket-ID einer App, indem Sie im Google Play Store zu der App navigieren.</span><span class="sxs-lookup"><span data-stu-id="66858-139">You can find the package ID of an app by browsing to the app on the Google Play store.</span></span> <span data-ttu-id="66858-140">Die Paket-ID ist in der URL der Seite der App enthalten.</span><span class="sxs-lookup"><span data-stu-id="66858-140">The package ID is contained in the URL of the app's page.</span></span> <span data-ttu-id="66858-141">Die Paket-ID der Microsoft Word-App lautet z.B. **com.microsoft.office.word**.</span><span class="sxs-lookup"><span data-stu-id="66858-141">For example, the package ID of the Microsoft Word app is **com.microsoft.office.word**.</span></span>

<span data-ttu-id="66858-142">Die App-Einstellungen werden beim nächsten Einchecken jedes Zielgeräts angewendet.</span><span class="sxs-lookup"><span data-stu-id="66858-142">The next time each targeted device checks in, the app settings will be applied.</span></span>


<!---## Assign the custom profile--->
