---
title: "Zulässige und blockierte Apps für KNOX"
description: "Benutzerdefiniertes Profil, um eine Liste der zulässigen und blockierten Apps für KNOX zu erstellen."
keywords: 
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 11/02/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: bbc8e0df-7bf3-494e-8bc4-dac59a98ab41
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: chrisbal
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: e0857ac8e7f57779c46968996c467544ba9fbb35
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2018
---
# <a name="use-custom-policies-to-allow-and-block-apps-for-samsung-knox-standard-devices"></a><span data-ttu-id="e321f-103">Verwenden von benutzerdefinierten Richtlinien zum Zulassen und Blockieren von Apps für Samsung KNOX Standard-Geräte</span><span class="sxs-lookup"><span data-stu-id="e321f-103">Use custom policies to allow and block apps for Samsung KNOX Standard devices</span></span>

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="e321f-104">Verwenden Sie die Verfahren in diesem Thema, um eine benutzerdefinierte Microsoft Intune-Richtlinie zu erstellen, die eine der folgenden Listen erstellt:</span><span class="sxs-lookup"><span data-stu-id="e321f-104">Use the procedures in this topic to create a Microsoft Intune custom policy that creates one of the following:</span></span>

- <span data-ttu-id="e321f-105">Eine Liste von Apps, deren Ausführung auf dem Gerät blockiert wird.</span><span class="sxs-lookup"><span data-stu-id="e321f-105">A list of apps that are blocked from running on the device.</span></span> <span data-ttu-id="e321f-106">Die Ausführung der Apps in dieser Liste wird blockiert, auch wenn diese bereits vor der Anwendung der Richtlinie installiert waren.</span><span class="sxs-lookup"><span data-stu-id="e321f-106">Apps in this list are blocked from being run, even if they were already installed when the policy was applied.</span></span>
- <span data-ttu-id="e321f-107">Eine Liste von Apps, die Benutzer des Geräts aus dem Google Play Store installieren dürfen.</span><span class="sxs-lookup"><span data-stu-id="e321f-107">A list of apps that users of the device are allowed to install from the Google Play store.</span></span> <span data-ttu-id="e321f-108">Nur die aufgelisteten Apps können installiert werden.</span><span class="sxs-lookup"><span data-stu-id="e321f-108">Only the apps you list can be installed.</span></span> <span data-ttu-id="e321f-109">Es können keine anderen Apps aus dem Store installiert werden.</span><span class="sxs-lookup"><span data-stu-id="e321f-109">No other apps can be installed from the store.</span></span>

<span data-ttu-id="e321f-110">Diese Einstellungen können nur von Geräten verwendet werden, auf denen Samsung KNOX Standard ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="e321f-110">These settings can only be used by devices that run Samsung KNOX Standard.</span></span>

## <a name="to-create-an-allowed-or-blocked-app-list"></a><span data-ttu-id="e321f-111">So erstellen Sie eine Liste mit zulässigen oder blockierten Apps</span><span class="sxs-lookup"><span data-stu-id="e321f-111">To create an allowed or blocked app list</span></span>

1. <span data-ttu-id="e321f-112">Wählen Sie in der [Microsoft Intune-Verwaltungskonsole](https://manage.microsoft.com/) die Optionen **Richtlinie** &gt; **Konfigurationsrichtlinien** &gt; **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="e321f-112">In the [Microsoft Intune administration console](https://manage.microsoft.com/), choose **Policy** &gt; **Configuration Policies** &gt; **Add**.</span></span>
2. <span data-ttu-id="e321f-113">Erweitern Sie im Dialogfeld **Neue Richtlinie erstellen** **Android**, wählen Sie **Benutzerdefinierte Konfiguration** und anschließend **Richtlinie erstellen** aus.</span><span class="sxs-lookup"><span data-stu-id="e321f-113">In the **Create a New Policy** dialog box, expand **Android**, choose **Custom Configuration**, and then choose **Create Policy**.</span></span>
3. <span data-ttu-id="e321f-114">Geben Sie einen Namen und optional eine Beschreibung für die Richtlinie an, und wählen Sie anschließend im Abschnitt **OMA-URI-Einstellungen** **Hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="e321f-114">Provide a name and optional description for the policy and then, in the **OMA-URI Settings** section, choose **Add**.</span></span>
4. <span data-ttu-id="e321f-115">Geben Sie im Dialogfeld **OMA-URI-Einstellung hinzufügen oder bearbeiten** Folgendes an: Für eine Liste von Apps, deren Ausführung auf dem Gerät blockiert wird:</span><span class="sxs-lookup"><span data-stu-id="e321f-115">In the **Add or Edit OMA-URI Setting** dialog box, specify the following:  For a list of apps that are blocked from running on the device:</span></span>
    
   - <span data-ttu-id="e321f-116">**Name der Einstellung.**</span><span class="sxs-lookup"><span data-stu-id="e321f-116">**Setting name.**</span></span> <span data-ttu-id="e321f-117">Geben Sie **PreventStartPackages** ein.</span><span class="sxs-lookup"><span data-stu-id="e321f-117">Enter **PreventStartPackages**.</span></span>
   - <span data-ttu-id="e321f-118">**Beschreibung der Einstellung.**</span><span class="sxs-lookup"><span data-stu-id="e321f-118">**Setting description.**</span></span> <span data-ttu-id="e321f-119">Geben Sie optional eine Beschreibung wie z.B. „Liste der Apps, deren Ausführung blockiert wird“ ein.</span><span class="sxs-lookup"><span data-stu-id="e321f-119">Enter an optional description like 'List of apps that are blocked from running.'</span></span>
   - <span data-ttu-id="e321f-120">**Datentyp.**</span><span class="sxs-lookup"><span data-stu-id="e321f-120">**Data type.**</span></span> <span data-ttu-id="e321f-121">Wählen Sie in der Dropdownliste **Zeichenfolge** aus.</span><span class="sxs-lookup"><span data-stu-id="e321f-121">From the drop-down list, choose **String**.</span></span>
   - <span data-ttu-id="e321f-122">**OMA-URI.**</span><span class="sxs-lookup"><span data-stu-id="e321f-122">**OMA-URI.**</span></span> <span data-ttu-id="e321f-123">Geben Sie **./Vendor/MSFT/PolicyManager/My/ApplicationManagement/PreventStartPackages** ein.</span><span class="sxs-lookup"><span data-stu-id="e321f-123">Enter **./Vendor/MSFT/PolicyManager/My/ApplicationManagement/PreventStartPackages**</span></span>
   - <span data-ttu-id="e321f-124">**Wert.**</span><span class="sxs-lookup"><span data-stu-id="e321f-124">**Value.**</span></span> <span data-ttu-id="e321f-125">Geben Sie eine Liste mit den Namen der App-Pakete ein, die Sie blockieren möchten.</span><span class="sxs-lookup"><span data-stu-id="e321f-125">Enter a list of the app package names you want to block.</span></span> <span data-ttu-id="e321f-126">Sie können **; : ,** oder **|** als Trennzeichen verwenden.</span><span class="sxs-lookup"><span data-stu-id="e321f-126">You can use **; : ,** or **|** as a delimiter.</span></span> <span data-ttu-id="e321f-127">(Beispiel: Paket1; Paket2;)</span><span class="sxs-lookup"><span data-stu-id="e321f-127">(Example: package1;package2;)</span></span>

     <span data-ttu-id="e321f-128">Für eine Liste von Apps, die Benutzer des Geräts aus Google Play Store installieren dürfen, wobei alle anderen Apps ausgeschlossen werden:</span><span class="sxs-lookup"><span data-stu-id="e321f-128">For a list of apps that users are allowed to install from the Google Play store while excluding all other apps:</span></span>

   - <span data-ttu-id="e321f-129">**Name der Einstellung.**</span><span class="sxs-lookup"><span data-stu-id="e321f-129">**Setting name.**</span></span> <span data-ttu-id="e321f-130">Geben Sie **AllowInstallPackages** ein.</span><span class="sxs-lookup"><span data-stu-id="e321f-130">Enter **AllowInstallPackages**.</span></span>
   - <span data-ttu-id="e321f-131">**Beschreibung der Einstellung.**</span><span class="sxs-lookup"><span data-stu-id="e321f-131">**Setting description.**</span></span> <span data-ttu-id="e321f-132">Geben Sie optional eine Beschreibung wie z.B. „Liste der Apps, die Benutzer aus Google Play Store installieren dürfen“ ein.</span><span class="sxs-lookup"><span data-stu-id="e321f-132">Enter an optional description like 'List of apps that users can install from Google Play.'</span></span>
   - <span data-ttu-id="e321f-133">**Datentyp.**</span><span class="sxs-lookup"><span data-stu-id="e321f-133">**Data type.**</span></span> <span data-ttu-id="e321f-134">Wählen Sie in der Dropdownliste **Zeichenfolge** aus.</span><span class="sxs-lookup"><span data-stu-id="e321f-134">From the drop-down list, choose **String**.</span></span>
   - <span data-ttu-id="e321f-135">**OMA-URI.**</span><span class="sxs-lookup"><span data-stu-id="e321f-135">**OMA-URI.**</span></span> <span data-ttu-id="e321f-136">Geben Sie **./Vendor/MSFT/PolicyManager/My/ApplicationManagement/AllowInstallPackages** ein.</span><span class="sxs-lookup"><span data-stu-id="e321f-136">Enter **./Vendor/MSFT/PolicyManager/My/ApplicationManagement/AllowInstallPackages**</span></span>
   - <span data-ttu-id="e321f-137">**Wert.**</span><span class="sxs-lookup"><span data-stu-id="e321f-137">**Value.**</span></span> <span data-ttu-id="e321f-138">Geben Sie eine Liste mit den Namen der App-Pakete ein, die Sie zulassen möchten.</span><span class="sxs-lookup"><span data-stu-id="e321f-138">Enter a list of the app package names you want to allow.</span></span> <span data-ttu-id="e321f-139">Sie können **; : ,** oder **|** als Trennzeichen verwenden.</span><span class="sxs-lookup"><span data-stu-id="e321f-139">You can use **; : ,** or **|** as a delimiter.</span></span> <span data-ttu-id="e321f-140">(Beispiel: Paket1; Paket2;)</span><span class="sxs-lookup"><span data-stu-id="e321f-140">(Example: package1;package2;)</span></span>

5. <span data-ttu-id="e321f-141">Klicken Sie auf **OK**, und klicken Sie anschließend auf **Richtlinie speichern**.</span><span class="sxs-lookup"><span data-stu-id="e321f-141">Click **OK**, and then click **Save Policy**.</span></span> 

>[!TIP]
> <span data-ttu-id="e321f-142">Sie finden die Paket-ID einer App, indem Sie im Google Play Store zu der App navigieren.</span><span class="sxs-lookup"><span data-stu-id="e321f-142">You can find the package ID of an app by browsing to the app on the Google Play store.</span></span> <span data-ttu-id="e321f-143">Die Paket-ID ist in der URL der Seite der App enthalten.</span><span class="sxs-lookup"><span data-stu-id="e321f-143">The package ID is contained in the URL of the app's page.</span></span> <span data-ttu-id="e321f-144">Die Paket-ID der Microsoft Word-App lautet z.B. **com.microsoft.office.word**.</span><span class="sxs-lookup"><span data-stu-id="e321f-144">For example, the package ID of the Microsoft Word app is **com.microsoft.office.word**.</span></span>

<span data-ttu-id="e321f-145">Die App-Einstellungen werden beim nächsten Einchecken jedes Zielgeräts angewendet.</span><span class="sxs-lookup"><span data-stu-id="e321f-145">The next time each targeted device checks in, the app settings will be applied.</span></span>


## <a name="deploy-the-policy"></a><span data-ttu-id="e321f-146">Bereitstellen der Richtlinie</span><span class="sxs-lookup"><span data-stu-id="e321f-146">Deploy the policy</span></span>

1.  <span data-ttu-id="e321f-147">Wählen Sie im Arbeitsbereich **Richtlinie** die Richtlinie aus, die Sie bereitstellen möchten, und klicken Sie dann auf **Bereitstellung verwalten**.</span><span class="sxs-lookup"><span data-stu-id="e321f-147">In the **Policy** workspace, select the policy you want to deploy, then click **Manage Deployment**.</span></span>

2.  <span data-ttu-id="e321f-148">Wählen Sie im Dialogfeld **Bereitstellung verwalten** mindestens eine Gruppe aus, für die die Richtlinie bereitgestellt werden soll. Klicken Sie anschließend auf **Hinzufügen** &gt; **OK**.</span><span class="sxs-lookup"><span data-stu-id="e321f-148">In the **Manage Deployment** dialog box, select one or more groups to which you want to deploy the policy, then click **Add** &gt; **OK**.</span></span>

 
<span data-ttu-id="e321f-149">Wenn Sie eine bereitgestellte Richtlinie auswählen, können Sie weitere Informationen zur Bereitstellung im unteren Teil der Richtlinienliste anzeigen.</span><span class="sxs-lookup"><span data-stu-id="e321f-149">When you select a deployed policy, you can view further information about the deployment in the lower part of the policies list.</span></span>

### <a name="see-also"></a><span data-ttu-id="e321f-150">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e321f-150">See also</span></span>
[<span data-ttu-id="e321f-151">Einstellungen für Android- und Samsung KNOX-Richtlinien in Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="e321f-151">Android and Samsung KNOX policy settings in Microsoft Intune</span></span>](android-policy-settings-in-microsoft-intune.md)
