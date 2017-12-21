---
title: "Hinzufügen und Zuweisen von MTD-Apps zu Intune"
titleSuffix: Azure portal
description: "Hinzufügen von MTD-Apps, der Microsoft Authenticator-App und der iOS-Konfigurationsrichtlinie mit Intune im Azure-Portal"
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 07/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 00356258-76a8-4a84-9cf5-64ceedb58e72
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 98a5b1b705e79b875b83cecb53cd82d7bf5dff30
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2017
---
# <a name="add-and-assign-mobile-threat-defense-mtd-apps-with-intune"></a><span data-ttu-id="bb753-103">Hinzufügen und Zuweisen von Mobile Threat Defense-Apps (MTD) mit Intune</span><span class="sxs-lookup"><span data-stu-id="bb753-103">Add and assign Mobile Threat Defense (MTD) apps with Intune</span></span>

> [!NOTE] 
> <span data-ttu-id="bb753-104">Dieses Thema gilt für alle Mobile Threat Defense-Partner.</span><span class="sxs-lookup"><span data-stu-id="bb753-104">This topic applies to all Mobile Threat Defense partners.</span></span>

<span data-ttu-id="bb753-105">Sie können Intune verwenden, um MTD-Apps hinzuzufügen und bereitzustellen, damit Endbenutzer Benachrichtigungen über auf ihren mobilen Geräten erkannte Bedrohungen sowie eine Anleitung zur Behebung der Bedrohungen erhalten können.</span><span class="sxs-lookup"><span data-stu-id="bb753-105">You can use Intune to add and deploy MTD apps so end-users can receive notifications when a threat is identified in their mobile devices, and to receive guidance to remediate the threats.</span></span>

<span data-ttu-id="bb753-106">Für iOS-Geräte benötigen Sie [Microsoft Authenticator](https://docs.microsoft.com/azure/multi-factor-authentication/end-user/microsoft-authenticator-app-how-to), damit Benutzer ihre Identitäten von Azure AD überprüfen lassen können.</span><span class="sxs-lookup"><span data-stu-id="bb753-106">For iOS devices, you need the [Microsoft Authenticator](https://docs.microsoft.com/azure/multi-factor-authentication/end-user/microsoft-authenticator-app-how-to) so users can have their identities checked by Azure AD.</span></span> <span data-ttu-id="bb753-107">Sie benötigen zusätzlich die iOS-App-Konfigurationsrichtlinie, die die MTD-iOS-App anweist, Intune zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="bb753-107">Additionally, you need the iOS app configuration policy which signals the MTD iOS app to use with Intune.</span></span>

> [!TIP]
> <span data-ttu-id="bb753-108">Das Intune-Unternehmensportal arbeitet als Broker auf Android-Geräten, damit Benutzer ihre Identitäten von Azure AD überprüfen lassen können.</span><span class="sxs-lookup"><span data-stu-id="bb753-108">The Intune company portal works as the broker on Android devices so users can have their identities checked by Azure AD.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="bb753-109">Vorbereitung</span><span class="sxs-lookup"><span data-stu-id="bb753-109">Before you begin</span></span>

-   <span data-ttu-id="bb753-110">Die unten beschriebenen Schritte müssen in der [Azure-Portal](https://portal.azure.com/) durchgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="bb753-110">The below steps need to be completed in the [Azure portal](https://portal.azure.com/).</span></span>

-   <span data-ttu-id="bb753-111">Stellen Sie sicher, dass Sie mit den folgenden Prozessen vertraut sind:</span><span class="sxs-lookup"><span data-stu-id="bb753-111">Make sure you’re familiar with the process of:</span></span>

    -   <span data-ttu-id="bb753-112">[Hinzufügen von Apps in Microsoft Intune](apps-add.md)</span><span class="sxs-lookup"><span data-stu-id="bb753-112">[Adding an app into Intune](apps-add.md).</span></span>

    -   <span data-ttu-id="bb753-113">[Hinzufügen von iOS-Apps mit Konfigurationsrichtlinien in Microsoft Intune](https://docs.microsoft.com/intune/deploy-use/configure-ios-apps-with-mobile-app-configuration-policies-in-microsoft-intune)</span><span class="sxs-lookup"><span data-stu-id="bb753-113">[Adding an iOS app configuration policy into Intune](https://docs.microsoft.com/intune/deploy-use/configure-ios-apps-with-mobile-app-configuration-policies-in-microsoft-intune).</span></span>

    -   <span data-ttu-id="bb753-114">[Zuweisen einer App mit Intune](https://docs.microsoft.com/intune/deploy-use/deploy-apps-in-microsoft-intune)</span><span class="sxs-lookup"><span data-stu-id="bb753-114">[Assigning an app with Intune](https://docs.microsoft.com/intune/deploy-use/deploy-apps-in-microsoft-intune).</span></span>

    -   <span data-ttu-id="bb753-115">[Hinzufügen einer iOS-App-Konfigurationsrichtlinien](https://docs.microsoft.com/intune/deploy-use/configure-ios-apps-with-mobile-app-configuration-policies-in-microsoft-intune)</span><span class="sxs-lookup"><span data-stu-id="bb753-115">[ Adding an iOS app configuration policy](https://docs.microsoft.com/intune/deploy-use/configure-ios-apps-with-mobile-app-configuration-policies-in-microsoft-intune).</span></span>

## <a name="to-add-apps"></a><span data-ttu-id="bb753-116">So fügen Sie Apps hinzu</span><span class="sxs-lookup"><span data-stu-id="bb753-116">To add apps</span></span>

### <a name="all-mtd-partners"></a><span data-ttu-id="bb753-117">Alle MTD-Partner</span><span class="sxs-lookup"><span data-stu-id="bb753-117">All MTD partners</span></span>

#### <a name="microsoft-authenticator-app-for-ios"></a><span data-ttu-id="bb753-118">Microsoft Authenticator-App für iOS</span><span class="sxs-lookup"><span data-stu-id="bb753-118">Microsoft Authenticator app for iOS</span></span>

- <span data-ttu-id="bb753-119">Sehen Sie sich die Anleitungen für [das Hinzufügen von iOS Store-Apps zu Microsoft Intune](store-apps-ios.md) an.</span><span class="sxs-lookup"><span data-stu-id="bb753-119">See the instructions for [adding iOS store apps to Microsoft Intune](store-apps-ios.md).</span></span> <span data-ttu-id="bb753-120">Verwenden Sie diese [Store-URL der Microsoft Authenticator-App](https://itunes.apple.com/us/app/microsoft-authenticator/id983156458?mt=8) für **Schritt 5** im Abschnitt **Konfigurieren von App-Informationen**.</span><span class="sxs-lookup"><span data-stu-id="bb753-120">Use this [Microsoft Authenticator app store URL](https://itunes.apple.com/us/app/microsoft-authenticator/id983156458?mt=8) on **step 5** under the **Configure app information** section.</span></span>

### <a name="lookout"></a><span data-ttu-id="bb753-121">Lookout</span><span class="sxs-lookup"><span data-stu-id="bb753-121">Lookout</span></span>

#### <a name="android"></a><span data-ttu-id="bb753-122">Android</span><span class="sxs-lookup"><span data-stu-id="bb753-122">Android</span></span>
- <span data-ttu-id="bb753-123">Sehen Sie sich die Anleitungen für [das Hinzufügen von Android Store-Apps zu Microsoft Intune](store-apps-android.md) an.</span><span class="sxs-lookup"><span data-stu-id="bb753-123">See the instructions for [adding Android store apps to Microsoft Intune](store-apps-android.md).</span></span> <span data-ttu-id="bb753-124">Verwenden Sie diese [Store-URL der Lookout for Work-Google-App](https://play.google.com/store/apps/details?id=com.lookout.enterprise) in **Schritt 7**.</span><span class="sxs-lookup"><span data-stu-id="bb753-124">Use this [Lookout for work Google app store URL](https://play.google.com/store/apps/details?id=com.lookout.enterprise) on **step 7**.</span></span>

#### <a name="ios"></a><span data-ttu-id="bb753-125">iOS</span><span class="sxs-lookup"><span data-stu-id="bb753-125">iOS</span></span>

- <span data-ttu-id="bb753-126">Sehen Sie sich die Anleitungen für [das Hinzufügen von iOS Store-Apps zu Microsoft Intune](store-apps-ios.md) an.</span><span class="sxs-lookup"><span data-stu-id="bb753-126">See the instructions for [adding iOS store apps to Microsoft Intune](store-apps-ios.md).</span></span> <span data-ttu-id="bb753-127">Verwenden Sie diese [Store-URL der Lookout for Work-iOS-App](https://itunes.apple.com/us/app/lookout-for-work/id997193468?mt=8) für **Schritt 5** im Abschnitt **Konfigurieren von App-Informationen**.</span><span class="sxs-lookup"><span data-stu-id="bb753-127">Use this [Lookout for Work iOS app store URL](https://itunes.apple.com/us/app/lookout-for-work/id997193468?mt=8) on **step 5** under the **Configure app information** section.</span></span>

#### <a name="lookout-for-work-app-outside-the-apple-store"></a><span data-ttu-id="bb753-128">Lookout for Work-App außerhalb des Apple Store</span><span class="sxs-lookup"><span data-stu-id="bb753-128">Lookout for Work app outside the Apple store</span></span>

<span data-ttu-id="bb753-129">Sie müssen nun die Lookout for Work-App für iOS erneut signieren.</span><span class="sxs-lookup"><span data-stu-id="bb753-129">You need to re-sign the Lookout for Work iOS app.</span></span> <span data-ttu-id="bb753-130">Lookout verteilt die Lookout for Work-App für iOS außerhalb von iOS App Store.</span><span class="sxs-lookup"><span data-stu-id="bb753-130">Lookout distributes its Lookout for Work iOS app outside of the iOS App Store.</span></span> <span data-ttu-id="bb753-131">Bevor Sie die App verteilen, müssen Sie die App mit Ihrem iOS Enterprise Developer Certificate neu signieren.</span><span class="sxs-lookup"><span data-stu-id="bb753-131">Before distributing the app, you must re-sign the app with your iOS Enterprise Developer Certificate.</span></span>

<span data-ttu-id="bb753-132">Ausführliche Anweisungen zum erneuten Signieren der Lookout for Work-Apps für iOS finden Sie unter [iOS App Re-Signing Process (Erneute Signatur bei iOS-Apps)](https://personal.support.lookout.com/hc/articles/114094038714) auf der Lookout-Website.</span><span class="sxs-lookup"><span data-stu-id="bb753-132">For detailed instructions to re-sign the Lookout for Work iOS apps, see [Lookout for Work iOS app re-signing process](https://personal.support.lookout.com/hc/articles/114094038714) on the Lookout website.</span></span>

##### <a name="enable-azure-ad-authentication-for-lookout-for-work-ios-app"></a><span data-ttu-id="bb753-133">Aktivieren der Azure AD-Authentifizierung für die Lookout for Work-iOS-App</span><span class="sxs-lookup"><span data-stu-id="bb753-133">Enable Azure AD authentication for Lookout for Work iOS app</span></span>

<span data-ttu-id="bb753-134">Aktivieren Sie die Azure Active Directory-Authentifizierung für iOS-Benutzer, indem Sie folgendermaßen vorgehen:</span><span class="sxs-lookup"><span data-stu-id="bb753-134">Enable Azure Active Directory authentication for the iOS users by doing the following:</span></span>

1. <span data-ttu-id="bb753-135">Wechseln Sie zum [Azure-Portal](https://portal.sazure.com), melden Sie sich mit Ihren Anmeldeinformationen an, und navigieren Sie zur Seite „Anwendungen“.</span><span class="sxs-lookup"><span data-stu-id="bb753-135">Go to the [Azure portal](https://portal.sazure.com), sign in with your credentials, then navigate to the application page.</span></span>
  
2. <span data-ttu-id="bb753-136">Fügen Sie die **Lookout for Work iOS-App** als eine **native Clientanwendung** hinzu.</span><span class="sxs-lookup"><span data-stu-id="bb753-136">Add the **Lookout for Work iOS app** as a **native client application**.</span></span>

3. <span data-ttu-id="bb753-137">Ersetzen Sie **com.lookout.enterprise.yourcompanyname** mit der Kundenbundle-ID, die Sie beim Unterzeichnen der IPA ausgewählt haben.</span><span class="sxs-lookup"><span data-stu-id="bb753-137">Replace the **com.lookout.enterprise.yourcompanyname** with the customer bundle ID you selected when you signed the IPA.</span></span>

4.  <span data-ttu-id="bb753-138">Hinzufügen von zusätzlichen Umleitungs-URI: **&lt;companyportal://code/>** gefolgt von einer URL-codierten Version Ihrer ursprünglichen URI-Umleitung.</span><span class="sxs-lookup"><span data-stu-id="bb753-138">Add additional redirect URI: **&lt;companyportal://code/>** followed by a URL encoded version of your original redirect URI.</span></span>

5.  <span data-ttu-id="bb753-139">Fügen Sie **Delegierte Berechtigungen** zu Ihrer App hinzu.</span><span class="sxs-lookup"><span data-stu-id="bb753-139">Add **Delegated Permissions** to your app.</span></span>

    > [!NOTE] 
    > <span data-ttu-id="bb753-140">Weitere Informationen finden Sie unter [Konfigurieren Sie eine native Clientanwendung](https://azure.microsoft.com/documentation/articles/app-service-mobile-how-to-configure-active-directory-authentication/#optional-configure-a-native-client-application).</span><span class="sxs-lookup"><span data-stu-id="bb753-140">See [configure a native client application with Azure AD](https://azure.microsoft.com/documentation/articles/app-service-mobile-how-to-configure-active-directory-authentication/#optional-configure-a-native-client-application) for more details.</span></span>

##### <a name="add-the-lookout-for-work-ipa-file"></a><span data-ttu-id="bb753-141">Hinzufügen der IPA-Datei für Lookout for Work</span><span class="sxs-lookup"><span data-stu-id="bb753-141">Add the Lookout for Work ipa file</span></span>

- <span data-ttu-id="bb753-142">Laden Sie die neu signierte IPA-Datei hoch, wie im Thema [Hinzufügen von branchenspezifischen iOS-Apps in Microsoft Intune](lob-apps-ios.md) beschrieben.</span><span class="sxs-lookup"><span data-stu-id="bb753-142">Upload the re-signed .ipa file as described in the [Add iOS LOB apps with Intune](lob-apps-ios.md) topic.</span></span> <span data-ttu-id="bb753-143">Sie müssen auch iOS 8.0 oder höher als die mindestens erforderliche Betriebssystemversion festlegen.</span><span class="sxs-lookup"><span data-stu-id="bb753-143">You also need to set the minimum OS version to iOS 8.0 or later.</span></span>

### <a name="skycure"></a><span data-ttu-id="bb753-144">Skycure</span><span class="sxs-lookup"><span data-stu-id="bb753-144">Skycure</span></span>

#### <a name="android"></a><span data-ttu-id="bb753-145">Android</span><span class="sxs-lookup"><span data-stu-id="bb753-145">Android</span></span>

- <span data-ttu-id="bb753-146">Sehen Sie sich die Anleitungen für [das Hinzufügen von Android Store-Apps zu Microsoft Intune](store-apps-android.md) an.</span><span class="sxs-lookup"><span data-stu-id="bb753-146">See the instructions for [adding Android store apps to Microsoft Intune](store-apps-android.md).</span></span> <span data-ttu-id="bb753-147">Verwenden Sie diese [Store-URL der Skycure-App](https://play.google.com/store/apps/details?id=com.skycure.skycure) in **Schritt 7**.</span><span class="sxs-lookup"><span data-stu-id="bb753-147">Use this [Skycure app store URL](https://play.google.com/store/apps/details?id=com.skycure.skycure) on **step 7**.</span></span>

#### <a name="ios"></a><span data-ttu-id="bb753-148">iOS</span><span class="sxs-lookup"><span data-stu-id="bb753-148">iOS</span></span>

- <span data-ttu-id="bb753-149">Sehen Sie sich die Anleitungen für [das Hinzufügen von iOS Store-Apps zu Microsoft Intune](store-apps-ios.md) an.</span><span class="sxs-lookup"><span data-stu-id="bb753-149">See the instructions for [adding iOS store apps to Microsoft Intune](store-apps-ios.md).</span></span> <span data-ttu-id="bb753-150">Verwenden Sie diese [Store-URL der Skycure-App](https://itunes.apple.com/us/app/skycure/id695620821?mt=8) für **Schritt 5** im Abschnitt **Konfigurieren von App-Informationen**.</span><span class="sxs-lookup"><span data-stu-id="bb753-150">Use this [Skycure app store URL](https://itunes.apple.com/us/app/skycure/id695620821?mt=8) on **step 5** under the **Configure app information** section.</span></span>

### <a name="check-point-sandblast-mobile"></a><span data-ttu-id="bb753-151">Check Point SandBlast Mobile</span><span class="sxs-lookup"><span data-stu-id="bb753-151">Check Point SandBlast Mobile</span></span>

#### <a name="android"></a><span data-ttu-id="bb753-152">Android</span><span class="sxs-lookup"><span data-stu-id="bb753-152">Android</span></span>

- <span data-ttu-id="bb753-153">Sehen Sie sich die Anleitungen für [das Hinzufügen von Android Store-Apps zu Microsoft Intune](store-apps-android.md) an.</span><span class="sxs-lookup"><span data-stu-id="bb753-153">See the instructions for [adding Android store apps to Microsoft Intune](store-apps-android.md).</span></span> <span data-ttu-id="bb753-154">Verwenden Sie diese [Store-URL der Check Point SandBlast Mobile-App](https://play.google.com/store/apps/details?id=com.lacoon.security.fox) in **Schritt 7**.</span><span class="sxs-lookup"><span data-stu-id="bb753-154">Use this [Check Point SandBlast Mobile app store URL](https://play.google.com/store/apps/details?id=com.lacoon.security.fox) on **step 7**.</span></span>

#### <a name="ios"></a><span data-ttu-id="bb753-155">iOS</span><span class="sxs-lookup"><span data-stu-id="bb753-155">iOS</span></span>

- <span data-ttu-id="bb753-156">Wenden Sie sich an [Check Point SandBlast Mobile](https://www.checkpoint.com/products/sandblast-mobile/), um die iOS-App zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="bb753-156">Contact [Check Point SandBlast Mobile](https://www.checkpoint.com/products/sandblast-mobile/) to get the iOS app.</span></span> <span data-ttu-id="bb753-157">Sehen Sie sich die Anweisungen zum [Hinzufügen von iOS Store-Apps zu Microsoft Intune](store-apps-ios.md) an, verwenden Sie anschließend die Apple Store-URL in **Schritt 5** im Abschnitt **Konfigurieren von App-Informationen**.</span><span class="sxs-lookup"><span data-stu-id="bb753-157">See the instructions for [adding iOS store apps to Microsoft Intune](store-apps-ios.md), then use the Apple store URL on **step 5** under the **Configure app information** section.</span></span>

### <a name="zimperium"></a><span data-ttu-id="bb753-158">Zimperium</span><span class="sxs-lookup"><span data-stu-id="bb753-158">Zimperium</span></span>

#### <a name="android"></a><span data-ttu-id="bb753-159">Android</span><span class="sxs-lookup"><span data-stu-id="bb753-159">Android</span></span>

- <span data-ttu-id="bb753-160">Sehen Sie sich die Anleitungen für [das Hinzufügen von Android Store-Apps zu Microsoft Intune](store-apps-android.md) an.</span><span class="sxs-lookup"><span data-stu-id="bb753-160">See the instructions for [adding Android store apps to Microsoft Intune](store-apps-android.md).</span></span> <span data-ttu-id="bb753-161">Verwenden Sie diese [URL des Zimperium-App Stores](https://play.google.com/store/apps/details?id=com.zimperium.zips&hl=en) in **Schritt 7**.</span><span class="sxs-lookup"><span data-stu-id="bb753-161">Use this [Zimperium app store URL](https://play.google.com/store/apps/details?id=com.zimperium.zips&hl=en) on **step 7**.</span></span>

#### <a name="ios"></a><span data-ttu-id="bb753-162">iOS</span><span class="sxs-lookup"><span data-stu-id="bb753-162">iOS</span></span>

- <span data-ttu-id="bb753-163">Sehen Sie sich die Anleitungen für [das Hinzufügen von iOS Store-Apps zu Microsoft Intune](store-apps-ios.md) an.</span><span class="sxs-lookup"><span data-stu-id="bb753-163">See the instructions for [adding iOS store apps to Microsoft Intune](store-apps-ios.md).</span></span> <span data-ttu-id="bb753-164">Verwenden Sie diese [URL des Zimperium-App Stores](https://itunes.apple.com/us/app/zimperium-zips/id1030924459?mt=8) in **Schritt 5** im Abschnitt **Konfigurieren von App-Informationen**.</span><span class="sxs-lookup"><span data-stu-id="bb753-164">Use this [Zimperium app store URL](https://itunes.apple.com/us/app/zimperium-zips/id1030924459?mt=8) on **step 5** under the **Configure app information** section.</span></span>

## <a name="to-associate-the-mtd-app-with-an-ios-app-configuration-policy"></a><span data-ttu-id="bb753-165">So ordnen Sie die MTD-App einer iOS-App-Konfigurationsrichtlinie zu</span><span class="sxs-lookup"><span data-stu-id="bb753-165">To associate the MTD app with an iOS app configuration policy</span></span>

### <a name="for-lookout"></a><span data-ttu-id="bb753-166">Für Lookout</span><span class="sxs-lookup"><span data-stu-id="bb753-166">For Lookout</span></span>

- <span data-ttu-id="bb753-167">Erstellen Sie die iOS-App-Konfigurationsrichtlinie wie im Thema [zur Verwendung der iOS-App-Konfigurationsrichtlinie](app-configuration-policies-use-ios.md) beschrieben.</span><span class="sxs-lookup"><span data-stu-id="bb753-167">Create the iOS app configuration policy as described in the [using iOS app configuration policy](app-configuration-policies-use-ios.md) topic.</span></span>

### <a name="for-skycure"></a><span data-ttu-id="bb753-168">Für Skycure</span><span class="sxs-lookup"><span data-stu-id="bb753-168">For Skycure</span></span>

-   <span data-ttu-id="bb753-169">Verwenden Sie dasselbe Azure AD-Konto, das zuvor in der [Skycure-Verwaltungskonsole](https://aad.skycure.com) konfiguriert wurde. Dabei sollte es sich um das Konto handeln, mit dem Sie sich beim klassischen Intune-Portal anmelden.</span><span class="sxs-lookup"><span data-stu-id="bb753-169">Use the same Azure AD account previously configured in the [Skycure Management console](https://aad.skycure.com), which should be the same account used to log in to the Intune classic portal.</span></span>

-   <span data-ttu-id="bb753-170">Sie müssen die iOS-App-Konfigurationsrichtlinie **herunterladen**.</span><span class="sxs-lookup"><span data-stu-id="bb753-170">You need to **download** the iOS app configuration policy file:</span></span> 
    -   <span data-ttu-id="bb753-171">Wechseln Sie zur [Skycure-Verwaltungskonsole](https://aad.skycure.com), und melden Sie sich mit Ihren Anmeldeinformationen an.</span><span class="sxs-lookup"><span data-stu-id="bb753-171">Go to [Skycure Management console](https://aad.skycure.com) and sign in with your admin credentials.</span></span>
    
    -   <span data-ttu-id="bb753-172">Wechseln Sie zu **Settings** &gt; **Device Management Integrations** &gt; **EMM Integration Selection** (Einstellungen > Geräteverwaltungsintegrationen > EMM-Integrationsauswahl), wählen Sie **Microsoft Intune** aus, und speichern Sie dann Ihre Auswahl.</span><span class="sxs-lookup"><span data-stu-id="bb753-172">Go to **Settings** &gt; **Device Management Integrations** &gt; **EMM Integration Selection**, choose **Microsoft Intune**, then save your selection.</span></span>
    
    -   <span data-ttu-id="bb753-173">Klicken Sie auf den Link **Integration setup files** (Integrationssetupdateien), und speichern Sie die generierte \*.zip-Datei.</span><span class="sxs-lookup"><span data-stu-id="bb753-173">Click on the **Integration setup files** link and save the generated \*.zip file.</span></span> <span data-ttu-id="bb753-174">Die ZIP-Datei enthält die Datei **skycure\_configuration.plist**, die zum Erstellen der iOS-App-Konfigurationsrichtlinie in Intune verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="bb753-174">The .zip file contains the **skycure\_configuration.plist** file, which will be used to create the iOS app configuration policy in Intune.</span></span>
    
    -   <span data-ttu-id="bb753-175">In den Anweisungen für [die Verwendung der iOS-App-Konfigurationsrichtlinien von Microsoft Intune](app-configuration-policies-use-ios.md) erfahren Sie, wie Sie die iOS-App-Konfigurationsrichtlinie für Skycure hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="bb753-175">See the instructions for [using Microsoft Intune app configuration policies for iOS](app-configuration-policies-use-ios.md) to add the Skycure iOS app configuration policy.</span></span>
    
    - <span data-ttu-id="bb753-176">Verwenden Sie in **Schritt 8** die Option **XML-Daten eingeben**, kopieren Sie den Inhalt aus der Datei **skycure_configuration.plist**, und fügen Sie den Inhalt in den Text der Konfigurationsrichtlinie ein.</span><span class="sxs-lookup"><span data-stu-id="bb753-176">On **step 8**, use the option **Enter XML data**, copy the content from the **skycure_configuration.plist** file and paste its content into the configuration policy body.</span></span>

<span data-ttu-id="bb753-177">Sie können auch den Inhalt von **skycure_configuration.plist** hieraus kopieren:</span><span class="sxs-lookup"><span data-stu-id="bb753-177">You can also copy the **skycure_configuration.plist** content from here:</span></span>

```
<dict>
    <key>MdmType</key>
    <string>Intune</string>
    <key>UserEmail</key>
    <string>{{userprincipalname}}</string>
</dict>

```
### <a name="for-check-point-sandblast-mobile"></a><span data-ttu-id="bb753-178">Für Check Point SandBlast Mobile</span><span class="sxs-lookup"><span data-stu-id="bb753-178">For Check Point SandBlast Mobile</span></span>

- <span data-ttu-id="bb753-179">In den Anweisungen für [die Verwendung der iOS-App-Konfigurationsrichtlinien von Microsoft Intune](app-configuration-policies-use-ios.md) erfahren Sie, wie Sie die iOS-App-Konfigurationsrichtlinie für Check Point SandBlast Mobile hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="bb753-179">See the instructions for [using Microsoft Intune app configuration policies for iOS](app-configuration-policies-use-ios.md) to add the Check Point SandBlast Mobile iOS app configuration policy.</span></span>
    - <span data-ttu-id="bb753-180">Verwenden Sie in **Schritt 8** die Option **XML-Daten eingeben**, kopieren Sie den nachstehenden Inhalt, und fügen Sie den diesen in den Text der Konfigurationsrichtlinie ein.</span><span class="sxs-lookup"><span data-stu-id="bb753-180">On **step 8**, use the option **Enter XML data**, copy the content below and paste it into the configuration policy body.</span></span>

```
<dict><key>MDM</key><string>INTUNE</string></dict>

```

### <a name="for-zimperium"></a><span data-ttu-id="bb753-181">Für Zimperium</span><span class="sxs-lookup"><span data-stu-id="bb753-181">For Zimperium</span></span>

- <span data-ttu-id="bb753-182">In den Anweisungen für [die Verwendung der iOS-App-Konfigurationsrichtlinien von Microsoft Intune](app-configuration-policies-use-ios.md) erfahren Sie, wie Sie die iOS-App-Konfigurationsrichtlinie für Zimperium hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="bb753-182">See the instructions for [using Microsoft Intune app configuration policies for iOS](app-configuration-policies-use-ios.md) to add the Zimperium iOS app configuration policy.</span></span>
    - <span data-ttu-id="bb753-183">Verwenden Sie in **Schritt 8** die Option **XML-Daten eingeben**, kopieren Sie den nachstehenden Inhalt, und fügen Sie den diesen in den Text der Konfigurationsrichtlinie ein.</span><span class="sxs-lookup"><span data-stu-id="bb753-183">On **step 8**, use the option **Enter XML data**, copy the content below and paste it into the configuration policy body.</span></span>

```
<dict>
<key>provider</key><string>Intune</string>
<key>userprincipalname</key><string>{{userprincipalname}}</string>
<key>deviceid</key>
<string>{{deviceid}}</string>
<key>serialnumber</key>
<string>{{serialnumber}}</string>
<key>udidlast4digits</key>
<string>{{udidlast4digits}}</string>
</dict>

```

## <a name="to-assign-apps-all-mtd-partners"></a><span data-ttu-id="bb753-184">So weisen Sie Apps zu (Alle MTD-Partner)</span><span class="sxs-lookup"><span data-stu-id="bb753-184">To assign apps (All MTD partners)</span></span>

- <span data-ttu-id="bb753-185">Anweisungen hierzu finden Sie im Thema [Zuweisen von Apps zu Gruppen mit Microsoft Intune](apps-deploy.md).</span><span class="sxs-lookup"><span data-stu-id="bb753-185">See instructions for [assigning apps to groups with Intune](apps-deploy.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="bb753-186">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="bb753-186">Next steps</span></span>

- [<span data-ttu-id="bb753-187">Erstellen einer Mobile Threat Defense-Gerätekompatibilitätsrichtlinie (MTD) mit Intune</span><span class="sxs-lookup"><span data-stu-id="bb753-187">Add device compliance policy for MTD</span></span>](mtd-device-compliance-policy-create.md)
