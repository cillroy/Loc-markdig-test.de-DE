---
title: "App-bezogenes VPN-Profile für Android – Pulse Secure"
titlesuffix: Azure portal
description: "Erfahren Sie, wie ein VPN-Profil pro App für Android-Geräte erstellt wird, die von Intune verwaltet werden.\""
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
ms.openlocfilehash: 4151280509f225a4434d5813ac0405653b8929b6
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2018
---
# <a name="use-a-microsoft-intune-custom-profile-to-create-a-per-app-vpn-profile-for-android-devices"></a><span data-ttu-id="42a7d-103">Verwenden eines benutzerdefinierten Microsoft Intune-Profils zum Erstellen eines VPN-Profils pro App für Android-Geräte</span><span class="sxs-lookup"><span data-stu-id="42a7d-103">Use a Microsoft Intune custom profile to create a per-app VPN profile for Android devices</span></span>

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="42a7d-104">Sie können ein App-bezogenes VPN-Profil für Android 5.0-Geräte oder höher erstellen, die von Intune verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="42a7d-104">You can create a per-app VPN profile for Android 5.0 and later devices that are managed by Intune.</span></span> <span data-ttu-id="42a7d-105">Erstellen Sie zunächst ein VPN-Profil, das den Pulse Secure-Verbindungstyp verwendet.</span><span class="sxs-lookup"><span data-stu-id="42a7d-105">First, create a VPN profile that uses the Pulse Secure connection type.</span></span> <span data-ttu-id="42a7d-106">Erstellen Sie anschließend eine benutzerdefinierte Konfigurationsrichtlinie, die das VPN-Profil angegebenen Apps zuordnet.</span><span class="sxs-lookup"><span data-stu-id="42a7d-106">Then, create a custom configuration policy that associates the VPN profile with specific apps.</span></span>

<span data-ttu-id="42a7d-107">Nachdem Sie die Richtlinie auf Ihrem Android-Gerät oder für Benutzergruppen zugewiesen haben, müssen Benutzer das Pulse Secure-VPN starten.</span><span class="sxs-lookup"><span data-stu-id="42a7d-107">After you assign the policy to your Android device or user groups, users should start the PulseSecure VPN.</span></span> <span data-ttu-id="42a7d-108">Pulse Secure erlaubt es dann lediglich den angegebenen Apps, die offene VPN-Verbindung für ihren Datenverkehr zu nutzen.</span><span class="sxs-lookup"><span data-stu-id="42a7d-108">PulseSecure then allows only traffic from the specified apps to use the open VPN connection.</span></span>

> [!NOTE]
>
> <span data-ttu-id="42a7d-109">Für dieses Profil wird nur der Verbindungstyp „Pulse Secure“ unterstützt.</span><span class="sxs-lookup"><span data-stu-id="42a7d-109">Only the Pulse Secure connection type is supported for this profile.</span></span>


## <a name="step-1-create-a-vpn-profile"></a><span data-ttu-id="42a7d-110">Schritt 1: Erstellen eines VPN-Profils</span><span class="sxs-lookup"><span data-stu-id="42a7d-110">Step 1: Create a VPN profile</span></span>


1. <span data-ttu-id="42a7d-111">Melden Sie sich beim Azure-Portal an.</span><span class="sxs-lookup"><span data-stu-id="42a7d-111">Sign into the Azure portal.</span></span>
2. <span data-ttu-id="42a7d-112">Wählen Sie **Weitere Dienste** > **Überwachung und Verwaltung** > **Intune** aus.</span><span class="sxs-lookup"><span data-stu-id="42a7d-112">Choose **More Services** > **Monitoring + Management** > **Intune**.</span></span>
3. <span data-ttu-id="42a7d-113">Wählen Sie auf dem Blatt **Intune** die Option **Gerätekonfiguration** aus.</span><span class="sxs-lookup"><span data-stu-id="42a7d-113">On the **Intune** blade, choose **Device configuration**.</span></span>
2. <span data-ttu-id="42a7d-114">Wählen Sie auf dem Blatt **Gerätekonfiguration** die Option **Verwalten** > **Profile** aus.</span><span class="sxs-lookup"><span data-stu-id="42a7d-114">On the **Device Configuration** blade, choose **Manage** > **Profiles**.</span></span>
2. <span data-ttu-id="42a7d-115">Wählen Sie auf dem Blatt mit der Profilliste die Option **Profil erstellen** aus.</span><span class="sxs-lookup"><span data-stu-id="42a7d-115">On the list of profiles blade, choose **Create Profile**.</span></span>
3. <span data-ttu-id="42a7d-116">Geben Sie auf dem Blatt **Profil erstellen** einen **Namen** und optional eine **Beschreibung** für das VPN-Profil ein.</span><span class="sxs-lookup"><span data-stu-id="42a7d-116">On the **Create Profile** blade, enter a **Name** and optional **Description** for the VPN profile.</span></span>
4. <span data-ttu-id="42a7d-117">Wählen Sie in der Dropdownliste **Plattform** die Option **Android** aus.</span><span class="sxs-lookup"><span data-stu-id="42a7d-117">From the **Platform** drop-down list, choose **Android**.</span></span>
5. <span data-ttu-id="42a7d-118">Wählen Sie in der Dropdownliste **Profiltyp** die Option **VPN** aus.</span><span class="sxs-lookup"><span data-stu-id="42a7d-118">From the **Profile type** drop-down list, choose **VPN**.</span></span>
3. <span data-ttu-id="42a7d-119">Wählen Sie **Einstellungen** > **Konfigurieren** aus, und konfigurieren Sie das VPN-Profil gemäß den Einstellungen in [Konfigurieren von VPN-Einstellungen](vpn-settings-configure.md) und [Intune-VPN-Einstellungen für Android-Geräte](vpn-settings-android.md).</span><span class="sxs-lookup"><span data-stu-id="42a7d-119">Choose **Settings** > **Configure** and then configure the VPN profile as per the settings in [How to configure VPN settings](vpn-settings-configure.md) and [Intune VPN settings for Android devices](vpn-settings-android.md).</span></span>

<span data-ttu-id="42a7d-120">Notieren Sie den Wert für **Verbindungsname**, den Sie beim Erstellen des VPN-Profils angegeben haben.</span><span class="sxs-lookup"><span data-stu-id="42a7d-120">Take note of the **Connection Name** value you specify when creating the VPN profile.</span></span> <span data-ttu-id="42a7d-121">Dieser Name wird im nächsten Schritt benötigt.</span><span class="sxs-lookup"><span data-stu-id="42a7d-121">This name will be needed in the next step.</span></span> <span data-ttu-id="42a7d-122">Beispiel: **MeineApp-VPN-Profil**.</span><span class="sxs-lookup"><span data-stu-id="42a7d-122">For example, **MyAppVpnProfile**.</span></span>

## <a name="step-2-create-a-custom-configuration-policy"></a><span data-ttu-id="42a7d-123">Schritt 2: Erstellen einer benutzerdefinierten Konfigurationsrichtlinie</span><span class="sxs-lookup"><span data-stu-id="42a7d-123">Step 2: Create a custom configuration policy</span></span>

1. <span data-ttu-id="42a7d-124">Melden Sie sich beim Azure-Portal an.</span><span class="sxs-lookup"><span data-stu-id="42a7d-124">Sign into the Azure portal.</span></span>
2. <span data-ttu-id="42a7d-125">Wählen Sie **Weitere Dienste** > **Überwachung und Verwaltung** > **Intune** aus.</span><span class="sxs-lookup"><span data-stu-id="42a7d-125">Choose **More Services** > **Monitoring + Management** > **Intune**.</span></span>
3. <span data-ttu-id="42a7d-126">Wählen Sie auf dem Blatt **Intune** die Option **Gerätekonfiguration** aus.</span><span class="sxs-lookup"><span data-stu-id="42a7d-126">On the **Intune** blade, choose **Device configuration**.</span></span>
2. <span data-ttu-id="42a7d-127">Wählen Sie auf dem Blatt **Gerätekonfiguration** die Option **Verwalten** > **Profile** aus.</span><span class="sxs-lookup"><span data-stu-id="42a7d-127">On the **Device Configuration** blade, choose **Manage** > **Profiles**.</span></span>
3. <span data-ttu-id="42a7d-128">Klicken Sie auf dem Blatt „Profile“ auf **Profil erstellen**.</span><span class="sxs-lookup"><span data-stu-id="42a7d-128">On the profiles blade, click **Create Profile**.</span></span>
4. <span data-ttu-id="42a7d-129">Geben Sie auf dem Blatt **Profil erstellen** einen **Namen** und eine **Beschreibung** für das benutzerdefinierte Profil ein.</span><span class="sxs-lookup"><span data-stu-id="42a7d-129">On the **Create Profile** blade, enter a **Name** and **Description** for the custom profile.</span></span>
5. <span data-ttu-id="42a7d-130">Wählen Sie in der Dropdownliste **Plattform** die Option **Android** aus.</span><span class="sxs-lookup"><span data-stu-id="42a7d-130">From the **Platform** drop-down list, choose **Android**.</span></span>
6. <span data-ttu-id="42a7d-131">Wählen Sie in der Dropdownliste **Profiltyp** die Option **Benutzerdefiniert** aus.</span><span class="sxs-lookup"><span data-stu-id="42a7d-131">From the **Profile type** drop-down list, choose **Custom**.</span></span>
7. <span data-ttu-id="42a7d-132">Wählen Sie **Einstellungen** > **Konfigurieren** aus.</span><span class="sxs-lookup"><span data-stu-id="42a7d-132">Choose **Settings** > **Configure**.</span></span>
3. <span data-ttu-id="42a7d-133">Wählen Sie auf dem Blatt **Benutzerdefinierte OMA-URI-Einstellungen** die Option **Hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="42a7d-133">On the **Custom OMA-URI Settings** blade, choose **Add**.</span></span>
    - <span data-ttu-id="42a7d-134">Geben Sie einen Einstellungsnamen ein.</span><span class="sxs-lookup"><span data-stu-id="42a7d-134">Enter a setting name.</span></span>
    - <span data-ttu-id="42a7d-135">Geben Sie für **Datentyp** **Zeichenfolge** an.</span><span class="sxs-lookup"><span data-stu-id="42a7d-135">For **Data type**, specify **String**.</span></span>
    - <span data-ttu-id="42a7d-136">Für **OMA-URI**, geben Sie diese Zeichenfolge: **./Vendor/MSFT/VPN/Profile/*Namen*/PackageList**, wobei *Namen* ist das VPN-Profil nennen Sie Sie in Schritt 1 notiert haben.</span><span class="sxs-lookup"><span data-stu-id="42a7d-136">For **OMA-URI**, specify this string: **./Vendor/MSFT/VPN/Profile/*Name*/PackageList**, where *Name* is the VPN profile name you noted in Step 1.</span></span> <span data-ttu-id="42a7d-137">Bei diesem Beispiel lautet die Zeichenfolge **./Vendor/MSFT/VPN/Profile/MyAppVpnProfile/PackageList**.</span><span class="sxs-lookup"><span data-stu-id="42a7d-137">In this example, the string would be **./Vendor/MSFT/VPN/Profile/MyAppVpnProfile/PackageList**.</span></span>
    - <span data-ttu-id="42a7d-138">Erstellen Sie für **Wert** eine durch Semikolons getrennte Liste der Pakete, die dem Profil zugeordnet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="42a7d-138">For **Value**, create a semicolon-separated list of packages to associate with the profile.</span></span> <span data-ttu-id="42a7d-139">Wenn z.B. Excel und der Google-Browser Chrome die VPN-Verbindung verwenden sollen, geben Sie Folgendes ein: **com.microsoft.office.excel;com.android.chrome**.</span><span class="sxs-lookup"><span data-stu-id="42a7d-139">For example, if you want Excel and the Google Chrome browser to use the VPN connection, enter **com.microsoft.office.excel;com.android.chrome**.</span></span>

![Beispiel einer benutzerdefinierten Richtlinie für ein App-bezogenes VPN für Android](./media/android_per_app_vpn_oma_uri.png)

### <a name="set-your-app-list-to-blacklist-or-whitelist-optional"></a><span data-ttu-id="42a7d-141">Festlegen, ob Ihre App-Liste eine Positivliste (Whitelist) oder eine Negativliste (Blacklist) sein soll (optional)</span><span class="sxs-lookup"><span data-stu-id="42a7d-141">Set your app list to blacklist or whitelist (optional)</span></span>
  <span data-ttu-id="42a7d-142">Sie können eine Liste von Apps angeben, die die VPN-Verbindung *nicht* verwenden können, indem Sie den Wert **BLACKLIST** verwenden.</span><span class="sxs-lookup"><span data-stu-id="42a7d-142">You can specify a list of apps that *cannot* use the VPN connection by using the **BLACKLIST** value.</span></span> <span data-ttu-id="42a7d-143">Alle anderen Apps stellen über das VPN eine Verbindung her.</span><span class="sxs-lookup"><span data-stu-id="42a7d-143">All other apps connect through the VPN.</span></span>
<span data-ttu-id="42a7d-144">Alternativ können Sie den Wert **WHITELIST** verwenden, um eine Liste von Apps anzugeben, die die VPN-Verbindung verwenden *können*.</span><span class="sxs-lookup"><span data-stu-id="42a7d-144">Alternatively, you can use the **WHITELIST** value to specify a list of apps that *can* use the VPN connection.</span></span> <span data-ttu-id="42a7d-145">Apps, die sich nicht auf der Liste befinden, stellen keine Verbindung über das VPN her.</span><span class="sxs-lookup"><span data-stu-id="42a7d-145">Apps that are not on the list do not connect through the VPN.</span></span>
  1.    <span data-ttu-id="42a7d-146">Wählen Sie auf dem Blatt **Benutzerdefinierte OMA-URI-Einstellungen** die Option **Hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="42a7d-146">On the **Custom OMA-URI Settings** blade, choose **Add**.</span></span>
  2.    <span data-ttu-id="42a7d-147">Geben Sie einen Einstellungsnamen ein.</span><span class="sxs-lookup"><span data-stu-id="42a7d-147">Enter a setting name.</span></span>
  3.    <span data-ttu-id="42a7d-148">Geben Sie für **Datentyp** **Zeichenfolge** an.</span><span class="sxs-lookup"><span data-stu-id="42a7d-148">For **Data type**, specify **String**.</span></span>
  4.    <span data-ttu-id="42a7d-149">Für **OMA-URI**, verwenden Sie diese Zeichenfolge: **./Vendor/MSFT/VPN/Profile/*Namen*/Mode**, wobei *Namen* wird von den in Schritt notiert haben Namen für die VPN-Profils 1.</span><span class="sxs-lookup"><span data-stu-id="42a7d-149">For **OMA-URI**, use this string: **./Vendor/MSFT/VPN/Profile/*Name*/Mode**, where *Name* is the VPN profile name you noted in Step 1.</span></span> <span data-ttu-id="42a7d-150">Bei unserem Beispiel lautet die Zeichenfolge **./Vendor/MSFT/VPN/Profile/MeineApp-VPN-Profil/Mode**.</span><span class="sxs-lookup"><span data-stu-id="42a7d-150">In our example, the string would be **./Vendor/MSFT/VPN/Profile/MyAppVpnProfile/Mode**.</span></span>
  5.    <span data-ttu-id="42a7d-151">Geben Sie für **Wert** entweder **BLACKLIST** oder **WHITELIST** ein.</span><span class="sxs-lookup"><span data-stu-id="42a7d-151">For **Value**, enter **BLACKLIST** or **WHITELIST**.</span></span>



## <a name="step-3-assign-both-policies"></a><span data-ttu-id="42a7d-152">Schritt 3: Zuweisen beider Richtlinien</span><span class="sxs-lookup"><span data-stu-id="42a7d-152">Step 3: Assign both policies</span></span>

<span data-ttu-id="42a7d-153">Verwenden Sie die Anweisungen in [Zuweisen von Geräteprofilen](device-profile-assign.md), um den erforderlichen Benutzern oder Geräten beide Profile zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="42a7d-153">Use the instructions in [How to assign device profiles](device-profile-assign.md) to assign both profiles to the required users or devices.</span></span>
