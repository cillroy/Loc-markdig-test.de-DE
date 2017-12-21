---
title: "Hinzufügen von Skycure-Apps, der Microsoft Authenticator-App und der iOS-Konfigurationsrichtlinie"
description: "Fügen Sie Skycure-Apps, die Microsoft Authenticator-App und die iOS-Konfigurationsrichtlinie im klassischen Intune-Portal hinzu."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 03/16/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 018d26f4-4a75-4e27-bb04-54f54106cb2f
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: cedf3db964c2a5c186af3033b44ee50a345c729e
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2017
---
# <a name="add-skycure-apps-microsoft-authenticator-app-and-ios-configuration-policy"></a><span data-ttu-id="597f7-103">Hinzufügen von Skycure-Apps, der Microsoft Authenticator-App und der iOS-Konfigurationsrichtlinie</span><span class="sxs-lookup"><span data-stu-id="597f7-103">Add Skycure apps, Microsoft Authenticator app and iOS configuration policy</span></span>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="597f7-104">Sie müssen Intune verwenden, um die Skycure-Apps hinzuzufügen und bereitzustellen, damit Endbenutzer Benachrichtigungen über auf ihren mobilen Geräten erkannte Bedrohungen sowie eine Anleitung zur Behebung der Bedrohungen erhalten können.</span><span class="sxs-lookup"><span data-stu-id="597f7-104">You need to use Intune to add and deploy the Skycure apps so end-users can receive notifications when a threat is identified in their mobile devices, and to receive guidance to remediate the threats.</span></span>

<span data-ttu-id="597f7-105">Außerdem benötigen Sie [Microsoft Authenticator](https://docs.microsoft.com/azure/multi-factor-authentication/end-user/microsoft-authenticator-app-how-to), damit Benutzer ihre Identität von Azure AD überprüfen lassen können, und die iOS-App-Konfigurationsrichtlinie, die signalisiert, dass die Skycure iOS-App Intune und Azure AD Single Sign-On (SSO) verwenden soll, damit Benutzer nicht bei jeder Anmeldung in der Skycure-App Benutzername und Kennwort eingeben müssen.</span><span class="sxs-lookup"><span data-stu-id="597f7-105">Additionally, you need the [Microsoft Authenticator](https://docs.microsoft.com/azure/multi-factor-authentication/end-user/microsoft-authenticator-app-how-to) so users can have their identities checked by Azure AD, and the iOS app configuration policy which signals the Skycure iOS app to use Intune and Azure AD Single Sign On (SSO) so users don’t need to type username and password every time they log in the Skycure app.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="597f7-106">Vorbereitung</span><span class="sxs-lookup"><span data-stu-id="597f7-106">Before you begin</span></span>

-   <span data-ttu-id="597f7-107">Die unten beschriebenen Schritte müssen im [klassischen Intune-Portal](https://manage.microsoft.com/) durchgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="597f7-107">The below steps need to be completed in the [Intune classic portal](https://manage.microsoft.com/).</span></span>

-   <span data-ttu-id="597f7-108">Verwenden Sie dasselbe Azure AD-Konto, das zuvor in der Skycure-Verwaltungskonsole konfiguriert wurde. Dabei sollte es sich um das Konto handeln, mit dem Sie sich beim klassischen Intune-Portal anmelden.</span><span class="sxs-lookup"><span data-stu-id="597f7-108">Use the same Azure AD account previously configured in the Skycure Management console, which should be the same account used to log in into the Intune classic portal.</span></span>

-   <span data-ttu-id="597f7-109">Die Skycure-Integrationsdatei muss zur Verwendung bereit sein.</span><span class="sxs-lookup"><span data-stu-id="597f7-109">You need to have the Skycure integration file ready to use.</span></span> <span data-ttu-id="597f7-110">Dies ist die ZIP-Datei, die zuvor aus der Skycure-Verwaltungskonsole heruntergeladen wurde und die Datei **skycure\_configuration.plist** mit den Richtlinienparametern für die iOS-App-Konfiguration enthält.</span><span class="sxs-lookup"><span data-stu-id="597f7-110">This is the .zip file previously downloaded from the Skycure Management console, which contains the file **skycure\_configuration.plist** with the iOS app configuration policy parameters.</span></span>

-   <span data-ttu-id="597f7-111">Stellen Sie sicher, dass Sie mit den folgenden Prozessen vertraut sind:</span><span class="sxs-lookup"><span data-stu-id="597f7-111">Make sure you’re familiar with the process of:</span></span>

    -   <span data-ttu-id="597f7-112">[Hinzufügen von Apps in Microsoft Intune](/intune-classic/deploy-use/add-apps)</span><span class="sxs-lookup"><span data-stu-id="597f7-112">[Adding an app into Intune](/intune-classic/deploy-use/add-apps).</span></span>

    -   <span data-ttu-id="597f7-113">[Hinzufügen von iOS-Apps mit Konfigurationsrichtlinien in Microsoft Intune](/intune-classic/deploy-use/configure-ios-apps-with-mobile-app-configuration-policies-in-microsoft-intune)</span><span class="sxs-lookup"><span data-stu-id="597f7-113">[Adding an iOS app configuration policy into Intune](/intune-classic/deploy-use/configure-ios-apps-with-mobile-app-configuration-policies-in-microsoft-intune).</span></span>

## <a name="to-add-the-skycure-app-for-android"></a><span data-ttu-id="597f7-114">So fügen Sie die Skycure-App für Android hinzu</span><span class="sxs-lookup"><span data-stu-id="597f7-114">To add the Skycure app for Android</span></span>

1.  <span data-ttu-id="597f7-115">Wählen Sie im klassischen Intune-Portal die Option **Apps** &gt; **Apps hinzufügen**, um den Intune-Softwareherausgeber zu starten, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="597f7-115">In the Intune classic portal, choose **Apps** &gt; **Add Apps** to start the Intune Software Publisher, then click **Next**.</span></span>

2.  <span data-ttu-id="597f7-116">Wählen Sie auf der Seite **Softwaresetup** die Option **Externer Link** aus, und fügen Sie dann unter **Specify the URL** (URL angeben) die [Skycure-App für Android-URL](https://play.google.com/store/apps/details?id=com.skycure.skycure) ein.</span><span class="sxs-lookup"><span data-stu-id="597f7-116">On the **Software setup** page, choose **External link**, then paste the [Skycure app for Android url](https://play.google.com/store/apps/details?id=com.skycure.skycure) under **Specify the URL**.</span></span>

    ![Intune-Softwareherausgeber, URL angeben](../media/mtp/skycure-add-apps-1.png)

3.  <span data-ttu-id="597f7-118">Geben Sie auf der Seite **Softwarebeschreibung** den **Herausgeber**, den **Namen** und die **Beschreibung** ein, wählen Sie die Option **Als ausgewählte App anzeigen und im Unternehmensportal hervorheben**, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="597f7-118">On the **Software description** page, enter the **Publisher**, **Name** and **Description**, select the option **Display this as a featured app and highlight it in the company portal**, then click **Next**.</span></span>

    ![Intune-Softwareherausgeber, Softwarebeschreibung](../media/mtp/skycure-add-apps-2.png)

4.  <span data-ttu-id="597f7-120">Klicken Sie auf **Hochladen** und dann auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="597f7-120">Click **Upload**, then **Close**.</span></span>

## <a name="to-add-the-skycure-app-for-ios"></a><span data-ttu-id="597f7-121">So fügen Sie die Skycure-App für iOS hinzu</span><span class="sxs-lookup"><span data-stu-id="597f7-121">To add the Skycure app for iOS</span></span>

1.  <span data-ttu-id="597f7-122">Wählen Sie im klassischen Intune-Portal die Option **Apps** &gt; **Apps hinzufügen**, um den Intune-Softwareherausgeber zu starten, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="597f7-122">In the Intune classic portal, choose **Apps** &gt; **Add Apps** to start the Intune Software Publisher, then click **Next**.</span></span>

2.  <span data-ttu-id="597f7-123">Wählen Sie auf der Seite **Softwaresetup** die Option **Verwaltete iOS-App aus dem App Store** aus, und fügen Sie dann unter **Specify the URL** (URL angeben) die [Skycure-App für iOS-URL](https://itunes.apple.com/us/app/skycure/id695620821?mt=8) ein.</span><span class="sxs-lookup"><span data-stu-id="597f7-123">On the **Software setup** page, choose **Managed iOS App from the App Store**, then paste the [Skycure app for iOS url](https://itunes.apple.com/us/app/skycure/id695620821?mt=8) under **Specify the URL**.</span></span>

    ![Intune-Softwareherausgeber, verwaltete iOS-App](../media/mtp/skycure-add-apps-3.png)

3.  <span data-ttu-id="597f7-125">Geben Sie auf der Seite **Softwarebeschreibung** den **Herausgeber**, den **Namen** und die **Beschreibung** ein, wählen Sie die Option **Als ausgewählte App anzeigen und im Unternehmensportal hervorheben**, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="597f7-125">On the **Software description** page, enter the **Publisher**, **Name** and **Description**, select the option **Display this as a featured app and highlight it in the company portal**, then click **Next**.</span></span>

    ![Intune-Softwareherausgeber, Optionen](../media/mtp/skycure-add-apps-4.png)

4.  <span data-ttu-id="597f7-127">Wählen Sie auf der Seite **Anforderungen** unter **Typ des mobilen Geräts** die Option **Any** (Beliebig) aus, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="597f7-127">On the **Requirements** page, select the option **Any** under **Mobile device type**, then click **Next**.</span></span>

5.  <span data-ttu-id="597f7-128">Klicken Sie auf **Hochladen** und dann auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="597f7-128">Click **Upload**, then **Close**.</span></span>

## <a name="to-add-the-microsoft-authenticator-app-for-ios"></a><span data-ttu-id="597f7-129">So fügen Sie die Microsoft Authenticator-App für iOS hinzu</span><span class="sxs-lookup"><span data-stu-id="597f7-129">To add the Microsoft Authenticator app for iOS</span></span>

1.  <span data-ttu-id="597f7-130">Wählen Sie im klassischen Intune-Portal die Option **Apps** &gt; **Apps hinzufügen**, um den Intune-Softwareherausgeber zu starten, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="597f7-130">In the Intune classic portal, choose **Apps** &gt; **Add Apps** to start the Intune Software Publisher, then click **Next**.</span></span>

2.  <span data-ttu-id="597f7-131">Wählen Sie auf der Seite **Softwaresetup** die Option **Verwaltete iOS-App aus dem App Store** aus, und fügen Sie dann unter **Specify the URL** (URL angeben) die [Microsoft Authenticator-App für iOS-URL](https://itunes.apple.com/us/app/microsoft-authenticator/id983156458?mt=8) ein.</span><span class="sxs-lookup"><span data-stu-id="597f7-131">On the **Software setup** page, choose **Managed iOS App from the App Store**, then paste the [Microsoft Authenticator app for iOS url](https://itunes.apple.com/us/app/microsoft-authenticator/id983156458?mt=8) under **Specify the URL**.</span></span>

    ![Intune-Softwareherausgeber, verwaltete iOS-App 2](../media/mtp/skycure-add-apps-5.png)

3.  <span data-ttu-id="597f7-133">Geben Sie auf der Seite **Softwarebeschreibung** den **Herausgeber**, den **Namen** und die **Beschreibung** ein, wählen Sie die Option **Als ausgewählte App anzeigen und im Unternehmensportal hervorheben**, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="597f7-133">On the **Software description** page, enter the **Publisher**, **Name** and **Description**, select the option **Display this as a featured app and highlight it in the company portal**, then click **Next**.</span></span>

    ![Intune-Softwareherausgeber, verwaltete iOS-App 3](../media/mtp/skycure-add-apps-6.png)

4.  <span data-ttu-id="597f7-135">Wählen Sie auf der Seite **Anforderungen** unter **Typ des mobilen Geräts** die Option **Any** (Beliebig) aus, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="597f7-135">On the **Requirements** page, select the option **Any** under **Mobile device type**, then click **Next**.</span></span>

5.  <span data-ttu-id="597f7-136">Klicken Sie auf **Hochladen** und dann auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="597f7-136">Click **Upload**, then **Close**.</span></span>

## <a name="to-add-the-skycure-ios-app-configuration-policy"></a><span data-ttu-id="597f7-137">Hinzufügen der Skycure iOS-App-Konfigurationsrichtlinie</span><span class="sxs-lookup"><span data-stu-id="597f7-137">To add the Skycure iOS app configuration policy</span></span>

1.  <span data-ttu-id="597f7-138">Wählen Sie im klassischen Intune-Portal **Richtlinie** &gt; **Übersicht &gt; Richtlinie hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="597f7-138">In the Intune classic portal, choose **Policy** &gt; **Overview &gt; Add Policy**.</span></span>

2.  <span data-ttu-id="597f7-139">Erweitern Sie in der Liste der Richtlinien den Eintrag **iOS**, wählen Sie **Richtlinie zur Konfiguration mobiler Apps (iOS 8.0 und höher)** und dann **Richtlinie erstellen** aus.</span><span class="sxs-lookup"><span data-stu-id="597f7-139">In the list of policies, expand **iOS**, choose **Mobile App Configuration Policy (iOS 8.0 and later)**, then choose **Create Policy**.</span></span>

    ![iOS-App-Konfigurationsrichtlinie](../media/mtp/skycure-add-apps-7.png)

3.  <span data-ttu-id="597f7-141">Geben Sie im Abschnitt **Allgemein** der Seite **Richtlinie erstellen** einen Namen und eine optionale Beschreibung für die Konfigurationsrichtlinie für iOS-Apps an.</span><span class="sxs-lookup"><span data-stu-id="597f7-141">In the **General** section of the **Create Policy** page, supply a name and an optional description for the iOS app configuration policy.</span></span>

    <span data-ttu-id="597f7-142">a.</span><span class="sxs-lookup"><span data-stu-id="597f7-142">a.</span></span>  <span data-ttu-id="597f7-143">Öffnen Sie die Datei **skycure\_configuration.plist** mit einem Text-Editor wie Editor. Kopieren Sie den Inhalt und fügen Sie ihn in den Text unter **Richtlinie zur Konfiguration mobiler Apps** ein. Wählen Sie dann **Überprüfen** und schließlich **Richtlinie speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="597f7-143">Open the **skycure\_configuration.plist** file using a text editor like notepad, copy the content and paste it into the **Mobile App Configuration Policy** body, choose **Validate**, then choose **Save Policy**.</span></span>

       ![iOS-App-Konfigurationsrichtlinie 2](../media/mtp/skycure-add-apps-8.png)

## <a name="next-steps"></a><span data-ttu-id="597f7-145">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="597f7-145">Next steps</span></span>

[<span data-ttu-id="597f7-146">Bereitstellen von Skycure-Apps, der Microsoft Authenticator-App und der iOS-Konfigurationsrichtlinie</span><span class="sxs-lookup"><span data-stu-id="597f7-146">Deploy Skycure apps, Microsoft Authenticator app and iOS app configuration policy</span></span>](/intune-classic/deploy-use/deploy-skycure-apps-microsoft-authenticator-app-and-ios-app-configuration-policy)
