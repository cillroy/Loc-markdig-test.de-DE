---
title: "Auf Ihrem Gerät ist ein Zertifikat nicht vorhanden | Microsoft-Dokumentation"
description: 
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 01/04/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f0ba4cbb-ef0a-4335-86bf-f1d006867fa2
searchScope: User help
ROBOTS: 
ms.reviewer: arnab
ms.suite: ems
ms.custom: intune-enduser
ms.openlocfilehash: 4a771416273ee29d0b44cb74b6b32d9535e43e41
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2017
---
# <a name="your-android-device-is-missing-a-certificate-required-by-your-company-support"></a><span data-ttu-id="648eb-102">Auf Ihrem Android-Gerät fehlt ein Zertifikat, das von der Supportabteilung Ihres Unternehmens verlangt wird.</span><span class="sxs-lookup"><span data-stu-id="648eb-102">Your Android device is missing a certificate required by your company support</span></span>

<span data-ttu-id="648eb-103">Wenn Ihr Gerät nicht bei Intune registriert ist und ein bestimmtes Zertifikat fehlt, das von der Supportabteilung Ihres Unternehmens verlangt wird, können Sie sich nicht bei der Unternehmensportal-App anmelden.</span><span class="sxs-lookup"><span data-stu-id="648eb-103">If your device isn’t enrolled in Intune, and it’s missing a certain certificate that is required by your company support, you won’t be able to sign in to the Company Portal app.</span></span> <span data-ttu-id="648eb-104">Wenn Sie versuchen, sich anzumelden, sehen Sie die folgende Meldung:</span><span class="sxs-lookup"><span data-stu-id="648eb-104">When you try to sign in, you'll see the following message:</span></span>

![screenshot-error-message-about-missing-certificate](./media/andr-cert_install-1-cert_missing.png)

<span data-ttu-id="648eb-106">Um dieses Problem zu lösen und das erforderliche Zertifikat zu erhalten, müssen Sie zwei Hauptschritte ausführen:</span><span class="sxs-lookup"><span data-stu-id="648eb-106">To fix this issue and get the required certificate, there are two main steps that you'll need to do:</span></span>

- <span data-ttu-id="648eb-107">Identifizieren Sie das fehlende Zertifikat in einem Unternehmens oder Schul-PC.</span><span class="sxs-lookup"><span data-stu-id="648eb-107">Identify the missing certificate by looking on a company or school PC.</span></span>
- <span data-ttu-id="648eb-108">Laden Sie das fehlende Zertifikat mit Ihrem Gerät aus dem Internet herunter.</span><span class="sxs-lookup"><span data-stu-id="648eb-108">Use your device to download the missing certificate from the Internet.</span></span>

## <a name="identify-the-missing-certificate-by-looking-on-a-company-or-school-pc"></a><span data-ttu-id="648eb-109">Identifizieren des fehlenden Zertifikats durch Suche auf einem Unternehmens oder Schul-PC</span><span class="sxs-lookup"><span data-stu-id="648eb-109">Identify the missing certificate by looking on a company or school PC</span></span>

1. <span data-ttu-id="648eb-110">Öffnen Sie auf einem PC den Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="648eb-110">On a PC, open Internet Explorer.</span></span> <span data-ttu-id="648eb-111">Wenn Ihnen dafür kein PC zur Verfügung steht, wenden Sie sich an die Supportabteilung Ihres Unternehmens.</span><span class="sxs-lookup"><span data-stu-id="648eb-111">If you don't have a PC to use for this purpose, contact your company support.</span></span> <span data-ttu-id="648eb-112">Die Kontaktinformationen für die Supportabteilung Ihres Unternehmens finden Sie auf der [Unternehmensportal-Website](https://portal.manage.microsoft.com#HelpDeskDialog).</span><span class="sxs-lookup"><span data-stu-id="648eb-112">For your company support's contact information, check the [Company Portal website](https://portal.manage.microsoft.com#HelpDeskDialog).</span></span>

2. <span data-ttu-id="648eb-113">Öffnen Sie die [Unternehmensportal-Website](https://portal.manage.microsoft.com#HelpDeskDialog), und melden Sie sich mit Ihren Geschäfts- oder Schulanmeldeinformationen an.</span><span class="sxs-lookup"><span data-stu-id="648eb-113">Go to the [Company Portal website](https://portal.manage.microsoft.com#HelpDeskDialog), and sign in using your work or school credentials.</span></span>

3. <span data-ttu-id="648eb-114">Wählen Sie ganz rechts in der Adressleiste des Browsers das Symbol aus, das wie ein Vorhängeschloss aussieht, wie im nachstehenden Screenshot dargestellt.</span><span class="sxs-lookup"><span data-stu-id="648eb-114">At the far right of the browser's address bar, choose the symbol that looks like a padlock, as shown in the following screenshot.</span></span>

    ![screenshot-internet-explorer-address-bar-padlock-symbol](./media/andr-missing-cert-ie-padlock-symbol.png)

    <span data-ttu-id="648eb-116">Wenn das Vorhängeschlosssymbol nicht angezeigt wird, beenden Sie den Vorgang, und wenden Sie sich an die Supportabteilung Ihres Unternehmens.</span><span class="sxs-lookup"><span data-stu-id="648eb-116">If you don't see the padlock symbol, stop and contact your company support.</span></span> <span data-ttu-id="648eb-117">Das Vorhängeschlosssymbol bedeutet, dass Sie sicher angemeldet sind, Sie sollten also nicht fortfahren, solange dieses Symbol nicht angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="648eb-117">The lock means that you are securely signed in, so you should not proceed unless you see that symbol.</span></span>

4. <span data-ttu-id="648eb-118">Wählen Sie **Zertifikate anzeigen** aus.</span><span class="sxs-lookup"><span data-stu-id="648eb-118">Choose **View certificates**.</span></span>

    ![screenshot-internet-explorer-view-certificates-button-on-website-identification-dialog](./media/andr-missg-cert-ie-view-cert-button.png)

5. <span data-ttu-id="648eb-120">Wählen Sie im Dialogfeld **Zertifikat** die Registerkarte **Zertifizierungspfad** aus, und identifizieren Sie das Zertifikat, das Sie aus dem Internet abrufen müssen.</span><span class="sxs-lookup"><span data-stu-id="648eb-120">In the **Certificate** dialog box, choose the **Certification path** tab, and then identify the certificate that you need to get from the Internet.</span></span> <span data-ttu-id="648eb-121">Der Name des Zertifikats, das Sie benötigen, befindet sich an der gleichen Position wie der, der im vorherigen Beispielscreenshot hervorgehoben ist.</span><span class="sxs-lookup"><span data-stu-id="648eb-121">The name of the certificate that you need will be in the same position as the one that is highlighted in the previous example screenshot.</span></span>

## <a name="download-and-install-the-missing-certificate-on-your-android-mobile-device"></a><span data-ttu-id="648eb-122">Herunterladen des fehlenden Zertifikats auf das Android-Gerät und Installation</span><span class="sxs-lookup"><span data-stu-id="648eb-122">Download and install the missing certificate on your Android mobile device</span></span>

1. <span data-ttu-id="648eb-123">Suchen Sie mithilfe einer Suchmaschine wie Bing oder Google nach dem Namen des fehlenden Zertifikats, das Sie im vorherigen Abschnitt angegeben haben.</span><span class="sxs-lookup"><span data-stu-id="648eb-123">Using a search engine like Bing or Google, search for the name of the missing certificate that you identified in the previous section.</span></span> <span data-ttu-id="648eb-124">Das Zertifikat kann mit verschiedenen Erweiterungen wie CRT oder PEM usw. enden.</span><span class="sxs-lookup"><span data-stu-id="648eb-124">The certificate may end in different "extensions," like ".crt" or ".pem", etc.</span></span>

2. <span data-ttu-id="648eb-125">Laden Sie das Stammzertifikat von der Website herunter.</span><span class="sxs-lookup"><span data-stu-id="648eb-125">Download the root certificate from the website.</span></span>

3. <span data-ttu-id="648eb-126">Ziehen Sie nach dem Herunterladen des Zertifikats vom oberen Rand Ihres Geräts nach unten, um Ihre Benachrichtigungen zu öffnen, und tippen Sie dann in der Liste der Benachrichtigungen auf den Namen des Zertifikats.</span><span class="sxs-lookup"><span data-stu-id="648eb-126">After the certificate downloads, drag down from the top of your device to open your notifications, and then tap the name of the certificate in the list of notifications.</span></span>

4. <span data-ttu-id="648eb-127">Übernehmen Sie im Dialogfeld **Name the Certificate** (Zertifikat benennen), das im folgenden Screenshot angezeigt wird, den Standardzertifikatnamen.</span><span class="sxs-lookup"><span data-stu-id="648eb-127">In the **Name the Certificate** dialog box shown in the following screenshot, accept the default certificate name.</span></span>

5. <span data-ttu-id="648eb-128">Stellen Sie sicher, dass **Verwendung von Anmeldeinformationen** auf **Für VPN und Apps** festgelegt ist, und tippen Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="648eb-128">Ensure that **Credential Use** is set to **Used for VPN and apps**, and then tap **OK**.</span></span>

    ![screenshot-certificate-name-dialog-showing-certificate-name](./media/andr-missing-cert-cert-name.png)

6. <span data-ttu-id="648eb-130">Schließen Sie die Unternehmensportal-App.</span><span class="sxs-lookup"><span data-stu-id="648eb-130">Close the Company Portal app.</span></span>

7. <span data-ttu-id="648eb-131">Öffnen Sie die Unternehmensportal-App erneut.</span><span class="sxs-lookup"><span data-stu-id="648eb-131">Reopen the Company Portal app.</span></span> <span data-ttu-id="648eb-132">Sie sollten sich jetzt bei der Unternehmensportal-App anmelden können.</span><span class="sxs-lookup"><span data-stu-id="648eb-132">You should now be able to sign in to the Company Portal app.</span></span> <span data-ttu-id="648eb-133">Wenn Sie Hilfe benötigen, wenden Sie sich an die Supportabteilung Ihres Unternehmens.</span><span class="sxs-lookup"><span data-stu-id="648eb-133">If you need help, contact your company support.</span></span>

<span data-ttu-id="648eb-134">Wenn Ihnen die gleiche „Zertifikat fehlt“-Meldung wie in der Abbildung oben angezeigt wird, und Sie den oben beschriebenen Vorgang bereits ausgeführt haben, benötigt die Supportabteilung Ihres Unternehmens wahrscheinlich noch ein anderes Zertifikat, um Ihnen bei der Installation helfen zu können.</span><span class="sxs-lookup"><span data-stu-id="648eb-134">If you see the same "missing certificate" message as the one shown previously, and you have already followed the procedure, there is probably still another certificate that your company support will need to help you install.</span></span> <span data-ttu-id="648eb-135">Verwenden Sie die Kontaktinformationen auf der [Unternehmensportal-Website](https://portal.manage.microsoft.com#HelpDeskDialog), wenn Sie sich an die Supportabteilung Ihres Unternehmens wenden möchten.</span><span class="sxs-lookup"><span data-stu-id="648eb-135">Contact your company support for help using contact information available at the [Company Portal website](https://portal.manage.microsoft.com#HelpDeskDialog).</span></span>
