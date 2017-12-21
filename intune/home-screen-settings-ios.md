---
title: "Einstellungen des Layouts des Intune-Startbildschirms für iOS-Geräte"
titlesuffix: Azure portal
description: "Lernen Sie die Einstellungen kennen, mit denen Sie den Start- und Dockbildschirm von iOS-Geräten anpassen können."
keywords: 
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 07/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6aba4491-afb9-43cd-9ccc-14e6a2a5a3b1
ms.reviewer: karanda
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 0dcc8f5509afa5308f8ae91a3d60ee081d5daa0b
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2017
---
# <a name="intune-home-screen-layout-settings-for-ios-devices"></a><span data-ttu-id="22c6f-103">Einstellungen des Layouts des Intune-Startbildschirms für iOS-Geräte</span><span class="sxs-lookup"><span data-stu-id="22c6f-103">Intune Home screen layout settings for iOS devices</span></span>

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="22c6f-104">Verwenden Sie diese Einstellungen, um das Layout von Apps und Ordnern auf dem iOS-Start- und Dockbildschirm zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="22c6f-104">Use these settings to configure the layout of apps and folders on the dock and Home screen of iOS.</span></span>

<span data-ttu-id="22c6f-105">iOS-Geräte, denen Sie das Profil zuweisen, müssen sich im überwachten Modus befinden und iOS 9.3 oder höher ausführen.</span><span class="sxs-lookup"><span data-stu-id="22c6f-105">iOS devices to which you assign the profile must be in supervised mode and running iOS 9.3 or later.</span></span>

1. <span data-ttu-id="22c6f-106">Wählen Sie auf dem Blatt **Gerätefunktionen** die Option **Layout des Startbildschirms (nur überwacht)** aus.</span><span class="sxs-lookup"><span data-stu-id="22c6f-106">On the **Device features** blades choose **Home Screen Layout (supervised only)**.</span></span>
2. <span data-ttu-id="22c6f-107">Wählen Sie auf dem Blatt **Layout des Startbildschirms (nur überwacht)**, ob Sie das Layout des **Docks** oder der **Seiten** konfigurieren möchten.</span><span class="sxs-lookup"><span data-stu-id="22c6f-107">On the **Home Screen Layout (supervised only)** blade, choose whether you want to configure the **Dock**, or **Pages** layouts.</span></span>

## <a name="add-items-to-the-dock"></a><span data-ttu-id="22c6f-108">Hinzufügen von Elementen zum Dock</span><span class="sxs-lookup"><span data-stu-id="22c6f-108">Add items to the dock</span></span>

<span data-ttu-id="22c6f-109">Auf dem Blatt **Dock** können Sie dem Dock des iOS-Bildschirms bis zu sechs Elemente oder Ordner hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="22c6f-109">On the **Dock** blade, you can add up to six items or folders to the dock of the iOS screen.</span></span> <span data-ttu-id="22c6f-110">Allerdings unterstützen viele Geräte weniger Elemente – z.B. unterstützen iPhone-Geräte bis zu vier Elemente.</span><span class="sxs-lookup"><span data-stu-id="22c6f-110">However, many devices support fewer items; for example, iPhone devices support up to four items.</span></span> <span data-ttu-id="22c6f-111">In diesem Fall werden nur die ersten vier Elemente, die Sie konfiguriert haben, auf dem Gerät angezeigt.</span><span class="sxs-lookup"><span data-stu-id="22c6f-111">In this case, only the first four items you configured are displayed on the device.</span></span>

1. <span data-ttu-id="22c6f-112">Wählen Sie **Hinzufügen**, um dem Dock ein Element hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="22c6f-112">Choose **Add** to add an item to the dock.</span></span>
2. <span data-ttu-id="22c6f-113">Wählen Sie auf dem Blatt **Zeile hinzufügen** aus, ob Sie eine **App** oder einen **Ordner** hinzufügen möchten.</span><span class="sxs-lookup"><span data-stu-id="22c6f-113">On the **Add Row** blade, choose whether you want to add an **App**, or a **Folder**.</span></span>
3. <span data-ttu-id="22c6f-114">Konfigurieren Sie mit den Informationen in diesem Thema die Apps und Ordner, die im Dock angezeigt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="22c6f-114">Using the information in this topic, configure the apps and folders you want to appear in the dock.</span></span>
4. <span data-ttu-id="22c6f-115">Fügen Sie nach Bedarf weitere Elemente hinzu.</span><span class="sxs-lookup"><span data-stu-id="22c6f-115">Continue to add items.</span></span> <span data-ttu-id="22c6f-116">Wenn Sie fertig sind, klicken Sie auf jedem Blatt auf **OK**, bis wieder das Blatt **Profil erstellen** angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="22c6f-116">When you are finished, click **OK** on each blade until you return to the **Create Profile** blade.</span></span> <span data-ttu-id="22c6f-117">Wählen Sie **Erstellen** aus.</span><span class="sxs-lookup"><span data-stu-id="22c6f-117">Choose **Create**.</span></span>

>[!TIP]
> <span data-ttu-id="22c6f-118">In jedem Startbildschirm und auf allen Seiten können Sie Elemente mittels Ziehen und Ablegen sortieren.</span><span class="sxs-lookup"><span data-stu-id="22c6f-118">You can drag and drop items in any Home screen and pages lists to reorder them.</span></span> 

### <a name="example"></a><span data-ttu-id="22c6f-119">Beispiel</span><span class="sxs-lookup"><span data-stu-id="22c6f-119">Example</span></span>

<span data-ttu-id="22c6f-120">In diesem Beispiel haben Sie den Dockbildschirm so konfiguriert, dass nur die Apps „Safari“, „Mail“ und „Stocks“ angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="22c6f-120">In this example, you've configured the dock screen to show only the Safari, Mail, and Stocks apps.</span></span> <span data-ttu-id="22c6f-121">In der folgenden Abbildung wird die App „Mail“ ausgewählt, um ihre Eigenschaften zu veranschaulichen:</span><span class="sxs-lookup"><span data-stu-id="22c6f-121">In the following image, the Mail app is selected to illustrate its properties:</span></span>

![Beispiel für iOS-Dockeinstellungen](http://i.imgur.com/FfFiUcP.png)

<span data-ttu-id="22c6f-123">Wenn Sie einem iPhone die Richtlinie zuweisen, ist das Ergebnis ein Dock, das etwa so aussieht:</span><span class="sxs-lookup"><span data-stu-id="22c6f-123">When you assign the policy to an iPhone, the result is a dock that looks similar to this screenshot:</span></span>

![Beispiel für das iOS-Docklayout eines iPhones](http://i.imgur.com/bAgCe8F.png)

## <a name="add-home-screen-pages"></a><span data-ttu-id="22c6f-125">Hinzufügen von Startbildschirmseiten</span><span class="sxs-lookup"><span data-stu-id="22c6f-125">Add Home screen pages</span></span>

<span data-ttu-id="22c6f-126">Fügen Sie die Seiten hinzu, die auf dem Startbildschirm angezeigt werden sollen, und die Apps, die auf jeder Seite angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="22c6f-126">Add the pages you want to appear on the home screen, and the apps that appear on each page.</span></span> <span data-ttu-id="22c6f-127">Apps, die Sie einer Seite hinzufügen, sind in der Reihenfolge, in der sie in der Liste angegeben sind, von links nach rechts angeordnet.</span><span class="sxs-lookup"><span data-stu-id="22c6f-127">Apps that you add to a page are arranged from left to right, in the order they are specified in the list.</span></span> <span data-ttu-id="22c6f-128">Wenn Sie mehr Apps hinzufügen, als auf eine Seite passen, werden die Apps auf eine nachfolgende Seite verschoben.</span><span class="sxs-lookup"><span data-stu-id="22c6f-128">If you add more apps than can fit on a page, the apps are moved to a subsequent page.</span></span>


1. <span data-ttu-id="22c6f-129">Wählen Sie auf dem Blatt **Seiten** **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="22c6f-129">On the **Pages** blade, choose **Add**.</span></span>
2. <span data-ttu-id="22c6f-130">Geben Sie auf dem Blatt **Zeile hinzufügen** einen **Seitennamen** ein.</span><span class="sxs-lookup"><span data-stu-id="22c6f-130">On the **Add Row** blade, enter a **Page name**.</span></span> <span data-ttu-id="22c6f-131">Dieser Name wird im Azure-Portal zur Referenz verwendet und auf dem iOS-Gerät *nicht angezeigt*.</span><span class="sxs-lookup"><span data-stu-id="22c6f-131">This name is used for your reference in the Azure portal, and *is not displayed* on the iOS device.</span></span>
3. <span data-ttu-id="22c6f-132">Wählen Sie **Hinzufügen** aus, und wählen Sie dann, ob Sie der Seite eine **App** oder einen **Ordner** hinzufügen möchten.</span><span class="sxs-lookup"><span data-stu-id="22c6f-132">Choose **Add**, then choose whether you want to add an **App**, or a **Folder** to the page.</span></span>
4. <span data-ttu-id="22c6f-133">Konfigurieren Sie mit den Informationen in diesem Thema die Apps und Ordner, die auf der Seite angezeigt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="22c6f-133">Using the information in this topic, configure the apps and folders you want to appear on the page.</span></span>

### <a name="example"></a><span data-ttu-id="22c6f-134">Beispiel</span><span class="sxs-lookup"><span data-stu-id="22c6f-134">Example</span></span>

<span data-ttu-id="22c6f-135">In diesem Beispiel haben Sie eine neue Seite mit dem Namen **Contoso** konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="22c6f-135">In this example, you've configured a new page named **Contoso**.</span></span> <span data-ttu-id="22c6f-136">Diese Seite zeigt nur die Apps „Find Friends“ und „Settings“ an.</span><span class="sxs-lookup"><span data-stu-id="22c6f-136">The page shows only the Find Friends, and Settings apps.</span></span> <span data-ttu-id="22c6f-137">In der folgenden Abbildung wird die App „Settings“ ausgewählt, um ihre Eigenschaften zu veranschaulichen:</span><span class="sxs-lookup"><span data-stu-id="22c6f-137">In the following image, the Settings app is selected to illustrate its properties:</span></span>

![Beispiel für Einstellungen des iOS-Startbildschirms](http://i.imgur.com/Jc2OxyX.png)

<span data-ttu-id="22c6f-139">Wenn Sie einem iPhone die Richtlinie zuweisen, ist das Ergebnis eine Seite, die etwa so aussieht:</span><span class="sxs-lookup"><span data-stu-id="22c6f-139">When you assign the policy to an iPhone, the result is a page that looks similar to this screenshot:</span></span>

![iOS-Gerät mit geändertem Startbildschirm](http://i.imgur.com/Bd37PHa.png)

## <a name="how-to-add-an-app-to-the-list"></a><span data-ttu-id="22c6f-141">Hinzufügen einer App zur Liste</span><span class="sxs-lookup"><span data-stu-id="22c6f-141">How to add an app to the list</span></span>

1. <span data-ttu-id="22c6f-142">Geben Sie den **App-Namen** ein.</span><span class="sxs-lookup"><span data-stu-id="22c6f-142">Enter the **App Name**.</span></span> <span data-ttu-id="22c6f-143">Dieser Name wird im Azure-Portal zur Referenz verwendet und auf dem iOS-Gerät *nicht angezeigt*.</span><span class="sxs-lookup"><span data-stu-id="22c6f-143">This name is used for your reference in the Azure portal, and *is not displayed* on the iOS device.</span></span>
2. <span data-ttu-id="22c6f-144">Geben Sie die **App-Bündel-ID** der App ein, die Sie anzeigen möchten.</span><span class="sxs-lookup"><span data-stu-id="22c6f-144">Enter the **App Bundle ID** of the app you want to display.</span></span> <span data-ttu-id="22c6f-145">Hilfe finden Sie weiter unten in diesem Thema unter **Bündel-ID-Referenz für integrierte iOS-Apps**.</span><span class="sxs-lookup"><span data-stu-id="22c6f-145">See **Bundle ID reference for built-in iOS apps** later in this topic for help.</span></span>
3. <span data-ttu-id="22c6f-146">Klicken Sie auf **OK**, und fahren Sie mit dem Hinzufügen von Elementen bis zu einem Maximum von **6** für das Gerätedock und **60** für eine Geräteseite fort.</span><span class="sxs-lookup"><span data-stu-id="22c6f-146">Click **OK**, then continue to add items, up to a maximum of **6** for the device dock, and **60** for a device page.</span></span>
4. <span data-ttu-id="22c6f-147">Klicken Sie zum Abschluss auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="22c6f-147">When you are finished, click **OK**.</span></span>

## <a name="how-to-add-a-folder-to-the-list"></a><span data-ttu-id="22c6f-148">Hinzufügen eines Ordners zur Liste</span><span class="sxs-lookup"><span data-stu-id="22c6f-148">How to add a folder to the list</span></span>

<span data-ttu-id="22c6f-149">Apps, die Sie einer Seite in einem Ordner hinzufügen, sind in der Reihenfolge, in der sie in der Liste angegeben sind, von links nach rechts angeordnet.</span><span class="sxs-lookup"><span data-stu-id="22c6f-149">Apps that you add to a page in a folder are arranged from left to right, in the order they are specified in the list.</span></span> <span data-ttu-id="22c6f-150">Wenn Sie mehr Apps hinzufügen, als auf eine Seite passen, werden die Apps auf eine nachfolgende Seite verschoben.</span><span class="sxs-lookup"><span data-stu-id="22c6f-150">If you add more apps than can fit on a page, the apps are moved to a subsequent page.</span></span>

1. <span data-ttu-id="22c6f-151">Geben Sie den **Ordnernamen** ein.</span><span class="sxs-lookup"><span data-stu-id="22c6f-151">Enter the **Folder name**.</span></span> <span data-ttu-id="22c6f-152">Dieser Name wird Benutzern auf ihren Geräten angezeigt.</span><span class="sxs-lookup"><span data-stu-id="22c6f-152">This name is displayed to users on their device.</span></span>
2. <span data-ttu-id="22c6f-153">Wählen Sie **Hinzufügen**, um eine Seite im Ordner zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="22c6f-153">Choose **Add** to create a page in the folder.</span></span> <span data-ttu-id="22c6f-154">Sie können bis zu 20 Seiten hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="22c6f-154">You can add up to 20 pages.</span></span>
3. <span data-ttu-id="22c6f-155">Geben Sie auf dem Blatt **Zeile hinzufügen** einen Namen für die Seite ein.</span><span class="sxs-lookup"><span data-stu-id="22c6f-155">On the **Add Row** blade, enter a name for the page.</span></span> <span data-ttu-id="22c6f-156">Dieser Name wird im Azure-Portal zur Referenz verwendet und auf dem iOS-Gerät *nicht angezeigt*.</span><span class="sxs-lookup"><span data-stu-id="22c6f-156">This name is used for your reference in the Azure portal, and *is not displayed* on the iOS device.</span></span>
3. <span data-ttu-id="22c6f-157">Geben Sie den **App-Namen** ein.</span><span class="sxs-lookup"><span data-stu-id="22c6f-157">Enter the **App Name**.</span></span> <span data-ttu-id="22c6f-158">Dieser Name wird im Azure-Portal zur Referenz verwendet und auf dem iOS-Gerät *nicht angezeigt*.</span><span class="sxs-lookup"><span data-stu-id="22c6f-158">This name is used for your reference in the Azure portal, and *is not displayed* on the iOS device.</span></span>
2. <span data-ttu-id="22c6f-159">Geben Sie die **App-Bündel-ID** der App ein, die Sie anzeigen möchten.</span><span class="sxs-lookup"><span data-stu-id="22c6f-159">Enter the **App Bundle ID** of the app you want to display.</span></span> <span data-ttu-id="22c6f-160">Hilfe finden Sie unter **Hinzufügen einer App zur Liste**.</span><span class="sxs-lookup"><span data-stu-id="22c6f-160">See **How to add an app to the list** for help.</span></span>
3. <span data-ttu-id="22c6f-161">Wählen Sie **Hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="22c6f-161">Choose **Add**.</span></span> <span data-ttu-id="22c6f-162">Sie können bis zu 60 Elemente hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="22c6f-162">You can add up to 60 items.</span></span>
4. <span data-ttu-id="22c6f-163">Klicken Sie zum Abschluss auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="22c6f-163">When you are finished, click **OK**.</span></span>


## <a name="bundle-id-reference-for-built-in-ios-apps"></a><span data-ttu-id="22c6f-164">Bündel-ID-Referenz für integrierte iOS-Apps</span><span class="sxs-lookup"><span data-stu-id="22c6f-164">Bundle ID reference for built-in iOS apps</span></span>

<span data-ttu-id="22c6f-165">Diese Liste zeigt die Bündel-ID einiger gängiger integrierter iOS-Apps.</span><span class="sxs-lookup"><span data-stu-id="22c6f-165">This list shows the bundle ID of some common built-in iOS apps.</span></span> <span data-ttu-id="22c6f-166">Um die Bündel-ID von anderen Apps zu finden, wenden Sie sich an den Softwarehersteller.</span><span class="sxs-lookup"><span data-stu-id="22c6f-166">To find the bundle ID of other apps, contact your software vendor.</span></span> 

|||
|-|-|
|<span data-ttu-id="22c6f-167">App-Name</span><span class="sxs-lookup"><span data-stu-id="22c6f-167">App name</span></span>|<span data-ttu-id="22c6f-168">Bündel-ID</span><span class="sxs-lookup"><span data-stu-id="22c6f-168">BundleID</span></span>|
|<span data-ttu-id="22c6f-169">App Store</span><span class="sxs-lookup"><span data-stu-id="22c6f-169">App Store</span></span>|<span data-ttu-id="22c6f-170">com.apple.AppStore</span><span class="sxs-lookup"><span data-stu-id="22c6f-170">com.apple.AppStore</span></span>|
|<span data-ttu-id="22c6f-171">Calculator</span><span class="sxs-lookup"><span data-stu-id="22c6f-171">Calculator</span></span>|<span data-ttu-id="22c6f-172">com.apple.calculator</span><span class="sxs-lookup"><span data-stu-id="22c6f-172">com.apple.calculator</span></span>|
|<span data-ttu-id="22c6f-173">Kalender</span><span class="sxs-lookup"><span data-stu-id="22c6f-173">Calendar</span></span>|<span data-ttu-id="22c6f-174">com.apple.mobilecal</span><span class="sxs-lookup"><span data-stu-id="22c6f-174">com.apple.mobilecal</span></span>|
|<span data-ttu-id="22c6f-175">Kamera</span><span class="sxs-lookup"><span data-stu-id="22c6f-175">Camera</span></span>|<span data-ttu-id="22c6f-176">com.apple.camera</span><span class="sxs-lookup"><span data-stu-id="22c6f-176">com.apple.camera</span></span>|
|<span data-ttu-id="22c6f-177">Clock</span><span class="sxs-lookup"><span data-stu-id="22c6f-177">Clock</span></span>|<span data-ttu-id="22c6f-178">com.apple.mobiletimer</span><span class="sxs-lookup"><span data-stu-id="22c6f-178">com.apple.mobiletimer</span></span>|
|<span data-ttu-id="22c6f-179">Compass</span><span class="sxs-lookup"><span data-stu-id="22c6f-179">Compass</span></span>|<span data-ttu-id="22c6f-180">com.apple.compass</span><span class="sxs-lookup"><span data-stu-id="22c6f-180">com.apple.compass</span></span>|
|<span data-ttu-id="22c6f-181">Kontakte</span><span class="sxs-lookup"><span data-stu-id="22c6f-181">Contacts</span></span>|<span data-ttu-id="22c6f-182">com.apple.MobileAddressBook</span><span class="sxs-lookup"><span data-stu-id="22c6f-182">com.apple.MobileAddressBook</span></span>|
|<span data-ttu-id="22c6f-183">FaceTime</span><span class="sxs-lookup"><span data-stu-id="22c6f-183">FaceTime</span></span>|<span data-ttu-id="22c6f-184">com.apple.facetime</span><span class="sxs-lookup"><span data-stu-id="22c6f-184">com.apple.facetime</span></span>|
|<span data-ttu-id="22c6f-185">Find Friends</span><span class="sxs-lookup"><span data-stu-id="22c6f-185">Find Friends</span></span>|<span data-ttu-id="22c6f-186">com.apple.mobileme.fmf1</span><span class="sxs-lookup"><span data-stu-id="22c6f-186">com.apple.mobileme.fmf1</span></span>|
|<span data-ttu-id="22c6f-187">Find iPhone</span><span class="sxs-lookup"><span data-stu-id="22c6f-187">Find iPhone</span></span>|<span data-ttu-id="22c6f-188">com.apple.mobileme.fmip1</span><span class="sxs-lookup"><span data-stu-id="22c6f-188">com.apple.mobileme.fmip1</span></span>|
|<span data-ttu-id="22c6f-189">Gamecenter</span><span class="sxs-lookup"><span data-stu-id="22c6f-189">Game Center</span></span>|<span data-ttu-id="22c6f-190">com.apple.gamecenter</span><span class="sxs-lookup"><span data-stu-id="22c6f-190">com.apple.gamecenter</span></span>|
|<span data-ttu-id="22c6f-191">GarageBand</span><span class="sxs-lookup"><span data-stu-id="22c6f-191">GarageBand</span></span>|<span data-ttu-id="22c6f-192">com.apple.mobilegarageband</span><span class="sxs-lookup"><span data-stu-id="22c6f-192">com.apple.mobilegarageband</span></span>|
|<span data-ttu-id="22c6f-193">Integrität</span><span class="sxs-lookup"><span data-stu-id="22c6f-193">Health</span></span>|<span data-ttu-id="22c6f-194">com.apple.Health</span><span class="sxs-lookup"><span data-stu-id="22c6f-194">com.apple.Health</span></span>|
|<span data-ttu-id="22c6f-195">iBooks</span><span class="sxs-lookup"><span data-stu-id="22c6f-195">iBooks</span></span>|<span data-ttu-id="22c6f-196">com.apple.iBooks</span><span class="sxs-lookup"><span data-stu-id="22c6f-196">com.apple.iBooks</span></span>|
|<span data-ttu-id="22c6f-197">iTunes Store</span><span class="sxs-lookup"><span data-stu-id="22c6f-197">iTunes Store</span></span>|<span data-ttu-id="22c6f-198">com.apple.MobileStore</span><span class="sxs-lookup"><span data-stu-id="22c6f-198">com.apple.MobileStore</span></span>|
|<span data-ttu-id="22c6f-199">iTunes U</span><span class="sxs-lookup"><span data-stu-id="22c6f-199">iTunes U</span></span>|<span data-ttu-id="22c6f-200">com.apple.itunesu</span><span class="sxs-lookup"><span data-stu-id="22c6f-200">com.apple.itunesu</span></span>|
|<span data-ttu-id="22c6f-201">Keynote</span><span class="sxs-lookup"><span data-stu-id="22c6f-201">Keynote</span></span>|<span data-ttu-id="22c6f-202">com.apple.Keynote</span><span class="sxs-lookup"><span data-stu-id="22c6f-202">com.apple.Keynote</span></span>|
|<span data-ttu-id="22c6f-203">Mail</span><span class="sxs-lookup"><span data-stu-id="22c6f-203">Mail</span></span>|<span data-ttu-id="22c6f-204">com.apple.mobilemail</span><span class="sxs-lookup"><span data-stu-id="22c6f-204">com.apple.mobilemail</span></span>|
|<span data-ttu-id="22c6f-205">Zuordnungen</span><span class="sxs-lookup"><span data-stu-id="22c6f-205">Maps</span></span>|<span data-ttu-id="22c6f-206">com.apple.Maps</span><span class="sxs-lookup"><span data-stu-id="22c6f-206">com.apple.Maps</span></span>|
|<span data-ttu-id="22c6f-207">Nachrichten</span><span class="sxs-lookup"><span data-stu-id="22c6f-207">Messages</span></span>|<span data-ttu-id="22c6f-208">com.apple.MobileSMS</span><span class="sxs-lookup"><span data-stu-id="22c6f-208">com.apple.MobileSMS</span></span>|
|<span data-ttu-id="22c6f-209">Musik</span><span class="sxs-lookup"><span data-stu-id="22c6f-209">Music</span></span>|<span data-ttu-id="22c6f-210">com.apple.Music</span><span class="sxs-lookup"><span data-stu-id="22c6f-210">com.apple.Music</span></span>|
|<span data-ttu-id="22c6f-211">News</span><span class="sxs-lookup"><span data-stu-id="22c6f-211">News</span></span>|<span data-ttu-id="22c6f-212">com.apple.news</span><span class="sxs-lookup"><span data-stu-id="22c6f-212">com.apple.news</span></span>|
|<span data-ttu-id="22c6f-213">Hinweise</span><span class="sxs-lookup"><span data-stu-id="22c6f-213">Notes</span></span>|<span data-ttu-id="22c6f-214">com.apple.mobilenotes</span><span class="sxs-lookup"><span data-stu-id="22c6f-214">com.apple.mobilenotes</span></span>|
|<span data-ttu-id="22c6f-215">Zahlen</span><span class="sxs-lookup"><span data-stu-id="22c6f-215">Numbers</span></span>|<span data-ttu-id="22c6f-216">com.apple.Numbers</span><span class="sxs-lookup"><span data-stu-id="22c6f-216">com.apple.Numbers</span></span>|
|<span data-ttu-id="22c6f-217">Seiten</span><span class="sxs-lookup"><span data-stu-id="22c6f-217">Pages</span></span>|<span data-ttu-id="22c6f-218">com.apple.Pages</span><span class="sxs-lookup"><span data-stu-id="22c6f-218">com.apple.Pages</span></span>|
|<span data-ttu-id="22c6f-219">Photo Booth</span><span class="sxs-lookup"><span data-stu-id="22c6f-219">Photo Booth</span></span>|<span data-ttu-id="22c6f-220">com.apple.Photo-Booth</span><span class="sxs-lookup"><span data-stu-id="22c6f-220">com.apple.Photo-Booth</span></span>|
|<span data-ttu-id="22c6f-221">Fotos</span><span class="sxs-lookup"><span data-stu-id="22c6f-221">Photos</span></span>|<span data-ttu-id="22c6f-222">com.apple.mobileslideshow</span><span class="sxs-lookup"><span data-stu-id="22c6f-222">com.apple.mobileslideshow</span></span>|
|<span data-ttu-id="22c6f-223">Podcasts</span><span class="sxs-lookup"><span data-stu-id="22c6f-223">Podcasts</span></span>|<span data-ttu-id="22c6f-224">com.apple.podcasts</span><span class="sxs-lookup"><span data-stu-id="22c6f-224">com.apple.podcasts</span></span>|
|<span data-ttu-id="22c6f-225">Reminders</span><span class="sxs-lookup"><span data-stu-id="22c6f-225">Reminders</span></span>|<span data-ttu-id="22c6f-226">com.apple.reminders</span><span class="sxs-lookup"><span data-stu-id="22c6f-226">com.apple.reminders</span></span>|
|<span data-ttu-id="22c6f-227">Safari</span><span class="sxs-lookup"><span data-stu-id="22c6f-227">Safari</span></span>|<span data-ttu-id="22c6f-228">com.apple.mobilesafari</span><span class="sxs-lookup"><span data-stu-id="22c6f-228">com.apple.mobilesafari</span></span>|
|<span data-ttu-id="22c6f-229">Einstellungen</span><span class="sxs-lookup"><span data-stu-id="22c6f-229">Settings</span></span>|<span data-ttu-id="22c6f-230">com.apple.Preferences</span><span class="sxs-lookup"><span data-stu-id="22c6f-230">com.apple.Preferences</span></span>|
|<span data-ttu-id="22c6f-231">Stocks</span><span class="sxs-lookup"><span data-stu-id="22c6f-231">Stocks</span></span>|<span data-ttu-id="22c6f-232">com.apple.stocks</span><span class="sxs-lookup"><span data-stu-id="22c6f-232">com.apple.stocks</span></span>|
|<span data-ttu-id="22c6f-233">Tipps</span><span class="sxs-lookup"><span data-stu-id="22c6f-233">Tips</span></span>|<span data-ttu-id="22c6f-234">com.apple.tips</span><span class="sxs-lookup"><span data-stu-id="22c6f-234">com.apple.tips</span></span>|
|<span data-ttu-id="22c6f-235">Videos</span><span class="sxs-lookup"><span data-stu-id="22c6f-235">Videos</span></span>|<span data-ttu-id="22c6f-236">com.apple.videos</span><span class="sxs-lookup"><span data-stu-id="22c6f-236">com.apple.videos</span></span>|
|<span data-ttu-id="22c6f-237">VoiceMemos</span><span class="sxs-lookup"><span data-stu-id="22c6f-237">VoiceMemos</span></span>|<span data-ttu-id="22c6f-238">com.apple.VoiceMemos</span><span class="sxs-lookup"><span data-stu-id="22c6f-238">com.apple.VoiceMemos</span></span>|
|<span data-ttu-id="22c6f-239">Wallet</span><span class="sxs-lookup"><span data-stu-id="22c6f-239">Wallet</span></span>|<span data-ttu-id="22c6f-240">com.apple.Passbook</span><span class="sxs-lookup"><span data-stu-id="22c6f-240">com.apple.Passbook</span></span>|
|<span data-ttu-id="22c6f-241">Überwachen</span><span class="sxs-lookup"><span data-stu-id="22c6f-241">Watch</span></span>|<span data-ttu-id="22c6f-242">com.apple.Bridge</span><span class="sxs-lookup"><span data-stu-id="22c6f-242">com.apple.Bridge</span></span>|
|<span data-ttu-id="22c6f-243">Weather</span><span class="sxs-lookup"><span data-stu-id="22c6f-243">Weather</span></span>|<span data-ttu-id="22c6f-244">com.apple.weather</span><span class="sxs-lookup"><span data-stu-id="22c6f-244">com.apple.weather</span></span>|


## <a name="next-steps"></a><span data-ttu-id="22c6f-245">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="22c6f-245">Next steps</span></span>

<span data-ttu-id="22c6f-246">Sie können nun das Geräteprofil den von Ihnen ausgewählten Gruppen zuweisen.</span><span class="sxs-lookup"><span data-stu-id="22c6f-246">You can now assign the device profile to the groups you choose.</span></span> <span data-ttu-id="22c6f-247">Weitere Informationen finden Sie unter [Zuweisen von Geräteprofilen](device-profile-assign.md).</span><span class="sxs-lookup"><span data-stu-id="22c6f-247">For details, see [How to assign device profiles](device-profile-assign.md).</span></span>
