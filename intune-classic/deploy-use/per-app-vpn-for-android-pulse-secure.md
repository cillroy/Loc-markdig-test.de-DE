---
title: "App-bezogenes VPN für Android mithilfe von Pulse Secure"
description: "Sie können ein App-bezogenes VPN-Profil für Android-Geräte erstellen, die von Intune verwaltet werden."
keywords: 
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 06/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: ac65e906-3922-429f-8d9c-d313d3126645
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: chrisbal
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 283818c9e83d123d336ef7ad99c6225f4f783d7e
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2018
---
# <a name="use-a-custom-policy-to-create-a-per-app-vpn-profile-for-android-devices"></a><span data-ttu-id="e1621-103">Verwenden einer benutzerdefinierten Richtlinie zum Erstellen eines Profils für ein App-bezogenes VPN für Android-Geräte</span><span class="sxs-lookup"><span data-stu-id="e1621-103">Use a custom policy to create a per-app VPN profile for Android devices</span></span>

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="e1621-104">Sie können ein App-bezogenes VPN-Profil für Android 5.0-Geräte oder höher erstellen, die von Intune verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="e1621-104">You can create a per-app VPN profile for Android 5.0 and later devices that are managed by Intune.</span></span> <span data-ttu-id="e1621-105">Erstellen Sie zunächst ein VPN-Profil, das den Pulse Secure- oder Citrix-Verbindungstyp verwendet.</span><span class="sxs-lookup"><span data-stu-id="e1621-105">First, create a VPN profile that uses the Pulse Secure or Citrix connection type.</span></span> <span data-ttu-id="e1621-106">Erstellen Sie anschließend eine benutzerdefinierte Konfigurationsrichtlinie, die das VPN-Profil angegebenen Apps zuordnet.</span><span class="sxs-lookup"><span data-stu-id="e1621-106">Then, create a custom configuration policy that associates the VPN profile with specific apps.</span></span> 

<span data-ttu-id="e1621-107">Nachdem Sie die Richtlinie auf Ihrem Android-Gerät oder für Ihre Benutzergruppe bereitstellen, sollten Benutzer den Pulse Secure- oder Citrix-VPN starten.</span><span class="sxs-lookup"><span data-stu-id="e1621-107">After you deploy the policy to your Android device or user groups, users should start the Pulse Secure or Citrix VPN.</span></span> <span data-ttu-id="e1621-108">Pulse Secure erlaubt es dann nur den angegebenen Apps, die offene VPN-Verbindung zu nutzen.</span><span class="sxs-lookup"><span data-stu-id="e1621-108">The connection will then allow traffic only from the specified apps to use the open VPN connection.</span></span>

> [!NOTE]
>
> <span data-ttu-id="e1621-109">Es werden nur die Verbindungstypen „Pulse Secure“ und „Citrix“ für dieses Profil unterstützt.</span><span class="sxs-lookup"><span data-stu-id="e1621-109">Only the Pulse Secure and Citrix connection types are supported for this profile.</span></span>


### <a name="step-1-create-a-vpn-profile"></a><span data-ttu-id="e1621-110">Schritt 1: Erstellen eines VPN-Profils</span><span class="sxs-lookup"><span data-stu-id="e1621-110">Step 1: Create a VPN profile</span></span>

1. <span data-ttu-id="e1621-111">Klicken Sie in der [Microsoft Intune-Verwaltungskonsole](https://manage.microsoft.com) auf **Richtlinie** > **Richtlinie hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="e1621-111">In the [Microsoft Intune administration console](https://manage.microsoft.com), choose **Policy** > **Add Policy**.</span></span>
2. <span data-ttu-id="e1621-112">Wählen Sie eine Vorlage für die neue Richtlinie aus, indem Sie **Android** erweitern und anschließend **VPN-Profil (Android 4 und höher)** auswählen.</span><span class="sxs-lookup"><span data-stu-id="e1621-112">To select a template for the new policy, expand **Android**, and then choose **VPN Profile (Android 4 and later)**.</span></span>
3. <span data-ttu-id="e1621-113">Wählen Sie in der Vorlage für **Verbindungstyp** die Option **Pulse Secure** oder **Citrix** aus.</span><span class="sxs-lookup"><span data-stu-id="e1621-113">In the template, for **Connection type**, choose **Pulse Secure** or **Citrix**.</span></span>
4. <span data-ttu-id="e1621-114">Stellen Sie das VPN-Profil fertig, und speichern Sie es.</span><span class="sxs-lookup"><span data-stu-id="e1621-114">Finish and save the VPN profile.</span></span> <span data-ttu-id="e1621-115">Weitere Informationen zu VPN-Profilen finden Sie unter [VPN-Verbindungen](../deploy-use/vpn-connections-in-microsoft-intune.md).</span><span class="sxs-lookup"><span data-stu-id="e1621-115">For more details about VPN profiles, see [VPN connections](../deploy-use/vpn-connections-in-microsoft-intune.md).</span></span>

> [!NOTE]
>
> <span data-ttu-id="e1621-116">Notieren Sie den Wert für **VPN-Verbindungsname (wird Benutzern angezeigt)**, den Sie beim Erstellen des VPN-Profils angegeben haben.</span><span class="sxs-lookup"><span data-stu-id="e1621-116">Take note of the **VPN Connection name (displayed to users):** value you specify when creating the VPN profile.</span></span> <span data-ttu-id="e1621-117">Dieser wird im nächsten Schritt benötigt.</span><span class="sxs-lookup"><span data-stu-id="e1621-117">This will be needed in the next step.</span></span> <span data-ttu-id="e1621-118">Beispiel: **MeineApp-VPN-Profil**.</span><span class="sxs-lookup"><span data-stu-id="e1621-118">For example, **MyAppVpnProfile**.</span></span>

### <a name="step-2-create-a-custom-configuration-policy"></a><span data-ttu-id="e1621-119">Schritt 2: Erstellen einer benutzerdefinierten Konfigurationsrichtlinie</span><span class="sxs-lookup"><span data-stu-id="e1621-119">Step 2: Create a custom configuration policy</span></span>

   1. <span data-ttu-id="e1621-120">Wählen Sie in der Intune-Verwaltungskonsole **Richtlinie** > **Richtlinie hinzufügen** > **Android** > **Benutzerdefinierte Konfiguration** > **Richtlinie erstellen** aus.</span><span class="sxs-lookup"><span data-stu-id="e1621-120">In the Intune admin console, choose **Policy** > **Add Policy** > **Android** > **Custom configuration** > **Create Policy**.</span></span>
   2. <span data-ttu-id="e1621-121">Geben Sie einen Namen für die Richtlinie ein.</span><span class="sxs-lookup"><span data-stu-id="e1621-121">Enter a name for the policy.</span></span>
   3. <span data-ttu-id="e1621-122">Wählen Sie unter **OMA-URI-Einstellungen** **Hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="e1621-122">Under **OMA-URI settings**, choose **Add**.</span></span>
   4. <span data-ttu-id="e1621-123">Geben Sie einen Einstellungsnamen ein.</span><span class="sxs-lookup"><span data-stu-id="e1621-123">Enter a setting name.</span></span>
   5. <span data-ttu-id="e1621-124">Geben Sie für **Datentyp** **Zeichenfolge** an.</span><span class="sxs-lookup"><span data-stu-id="e1621-124">For **Data type**, specify **String**.</span></span>
   6. <span data-ttu-id="e1621-125">Für **OMA-URI**, geben Sie diese Zeichenfolge: **./Vendor/MSFT/VPN/Profile/*Namen*/PackageList**, wobei *Namen* ist das VPN-Profil nennen Sie Sie in Schritt 1 notiert haben.</span><span class="sxs-lookup"><span data-stu-id="e1621-125">For **OMA-URI**, specify this string: **./Vendor/MSFT/VPN/Profile/*Name*/PackageList**, where *Name* is the VPN profile name you noted in Step 1.</span></span> <span data-ttu-id="e1621-126">Bei unserem Beispiel lautet die Zeichenfolge **./Vendor/MSFT/VPN/Profile/MeineApp-VPN-Profil/PackageList**.</span><span class="sxs-lookup"><span data-stu-id="e1621-126">In our example, the string would be **./Vendor/MSFT/VPN/Profile/MyAppVpnProfile/PackageList**.</span></span>
   7.   <span data-ttu-id="e1621-127">Erstellen Sie für **Wert** eine durch Semikolons getrennte Liste der Pakete, die dem Profil zugeordnet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="e1621-127">For **Value**, create a semicolon-separated list of packages to associate with the profile.</span></span> <span data-ttu-id="e1621-128">Wenn z.B. Excel und der Google-Browser Chrome die VPN-Verbindung verwenden sollen, geben Sie Folgendes ein: **com.microsoft.office.excel;com.android.chrome**.</span><span class="sxs-lookup"><span data-stu-id="e1621-128">For example, if you want Excel and the Google Chrome browser to use the VPN connection, enter **com.microsoft.office.excel;com.android.chrome**.</span></span>

![Beispiel einer benutzerdefinierten Richtlinie für ein App-bezogenes VPN für Android](./media/android_per_app_vpn_oma_uri.png)

#### <a name="set-your-app-list-to-blacklist-or-whitelist-optional"></a><span data-ttu-id="e1621-130">Festlegen, ob Ihre App-Liste eine Positivliste (Whitelist) oder eine Negativliste (Blacklist) sein soll (optional)</span><span class="sxs-lookup"><span data-stu-id="e1621-130">Set your app list to blacklist or whitelist (optional)</span></span>
  <span data-ttu-id="e1621-131">Sie können eine Liste von Apps angeben, die die VPN-Verbindung *nicht* verwenden können, indem Sie den Wert **BLACKLIST** verwenden.</span><span class="sxs-lookup"><span data-stu-id="e1621-131">You can specify a list of apps that *cannot* use the VPN connection by using the **BLACKLIST** value.</span></span> <span data-ttu-id="e1621-132">Alle anderen Apps stellen über das VPN eine Verbindung her.</span><span class="sxs-lookup"><span data-stu-id="e1621-132">All other apps will connect through the VPN.</span></span>
<span data-ttu-id="e1621-133">Alternativ können Sie den Wert **WHITELIST** verwenden, um eine Liste von Apps anzugeben, die die VPN-Verbindung verwenden *können*.</span><span class="sxs-lookup"><span data-stu-id="e1621-133">Alternatively, you can use the **WHITELIST** value to specify a list of apps that *can* use the VPN connection.</span></span> <span data-ttu-id="e1621-134">Apps, die sich nicht auf der Liste befinden, werden keine Verbindung über das VPN herstellen.</span><span class="sxs-lookup"><span data-stu-id="e1621-134">Apps that are not on the list will not connect through the VPN.</span></span>
  1.    <span data-ttu-id="e1621-135">Wählen Sie unter **OMA-URI-Einstellungen** **Hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="e1621-135">Under **OMA-URI** settings, choose **Add**.</span></span>
  2.    <span data-ttu-id="e1621-136">Geben Sie einen Einstellungsnamen ein.</span><span class="sxs-lookup"><span data-stu-id="e1621-136">Enter a setting name.</span></span>
  3.    <span data-ttu-id="e1621-137">Geben Sie für **Datentyp** **Zeichenfolge** an.</span><span class="sxs-lookup"><span data-stu-id="e1621-137">For **Data type**, specify **String**.</span></span>
  4.    <span data-ttu-id="e1621-138">Für **OMA-URI**, verwenden Sie diese Zeichenfolge: **./Vendor/MSFT/VPN/Profile/*Namen*/Mode**, wobei *Namen* wird von den in Schritt notiert haben Namen für die VPN-Profils 1.</span><span class="sxs-lookup"><span data-stu-id="e1621-138">For **OMA-URI**, use this string: **./Vendor/MSFT/VPN/Profile/*Name*/Mode**, where *Name* is the VPN profile name you noted in Step 1.</span></span> <span data-ttu-id="e1621-139">Bei unserem Beispiel lautet die Zeichenfolge **./Vendor/MSFT/VPN/Profile/MeineApp-VPN-Profil/Mode**.</span><span class="sxs-lookup"><span data-stu-id="e1621-139">In our example, the string would be **./Vendor/MSFT/VPN/Profile/MyAppVpnProfile/Mode**.</span></span>
  5.    <span data-ttu-id="e1621-140">Geben Sie für **Wert** entweder **BLACKLIST** oder **WHITELIST** ein.</span><span class="sxs-lookup"><span data-stu-id="e1621-140">For **Value**, enter **BLACKLIST** or **WHITELIST**.</span></span>



### <a name="step-3-deploy-both-policies"></a><span data-ttu-id="e1621-141">Schritt 3: Bereitstellen beider Richtlinien</span><span class="sxs-lookup"><span data-stu-id="e1621-141">Step 3: Deploy both policies</span></span>

<span data-ttu-id="e1621-142">Sie müssen *beide* Richtlinien für die *gleichen* Intune-Gruppen bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="e1621-142">You must deploy *both* policies to the *same* Intune groups.</span></span>

1.  <span data-ttu-id="e1621-143">Wählen Sie im Arbeitsbereich **Richtlinie** die Richtlinie aus, die Sie bereitstellen möchten, und wählen Sie dann **Bereitstellung verwalten** aus.</span><span class="sxs-lookup"><span data-stu-id="e1621-143">In the **Policy** workspace, select the policy that you want to deploy, and then choose **Manage Deployment**.</span></span>
2.  <span data-ttu-id="e1621-144">Führen Sie im Dialogfeld **Bereitstellung verwalten** folgende Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="e1621-144">In the **Manage Deployment** dialog box:</span></span>
    -   <span data-ttu-id="e1621-145">**So stellen Sie die Richtlinie bereit**: Wählen Sie mindestens eine Gruppe aus, für die Sie die Richtlinie bereitstellen möchten, und wählen Sie anschließend **Hinzufügen** > **OK** aus.</span><span class="sxs-lookup"><span data-stu-id="e1621-145">**To deploy the policy**, select one or more groups to deploy the policy to, then choose **Add** > **OK**.</span></span>
    -   <span data-ttu-id="e1621-146">**So schließen Sie das Dialogfeld, ohne die Richtlinie bereitzustellen**: Wählen Sie **Abbrechen** aus.</span><span class="sxs-lookup"><span data-stu-id="e1621-146">**To close the dialog box without deploying the policy**, choose **Cancel**.</span></span>

<span data-ttu-id="e1621-147">Eine Statuszusammenfassung und Warnungen auf der Seite **Übersicht** des Arbeitsbereichs **Richtlinie** identifiziert Probleme mit der Richtlinie, die Ihre Aufmerksamkeit erfordern.</span><span class="sxs-lookup"><span data-stu-id="e1621-147">A status summary and alerts on the **Overview** page of the **Policy** workspace identify issues with the policy that require your attention.</span></span> <span data-ttu-id="e1621-148">Eine Statuszusammenfassung wird im Arbeitsbereich **Dashboard** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="e1621-148">A status summary also appears in the **Dashboard** workspace.</span></span>
