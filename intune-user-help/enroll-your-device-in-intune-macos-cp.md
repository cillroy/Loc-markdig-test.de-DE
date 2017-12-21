---
title: "Registrieren Ihres macOS-Geräts bei Intune über das Unternehmensportal | Microsoft-Dokumentation"
description: "Beschreibt, wie Sie ein macOS-Gerät über die Unternehmensportal-App bei Intune registrieren"
keywords: Mac OS X, macOS, OS X
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 11/06/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3bb659cc-9b57-4d19-8631-2c26749fa71c
searchScope: User help
ROBOTS: 
ms.reviewer: elocholi
ms.suite: ems
ms.custom: intune-enduser
ms.openlocfilehash: 77c87d24834066c6ed58eaf004422490fcb81aa4
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2017
---
# <a name="enroll-your-macos-device-in-intune-with-the-company-portal-app"></a><span data-ttu-id="b5cc9-104">Registrieren Ihres macOS-Geräts bei Intune über die Unternehmensportal-App</span><span class="sxs-lookup"><span data-stu-id="b5cc9-104">Enroll your macOS device in Intune with the Company Portal app</span></span>

<span data-ttu-id="b5cc9-105">Durch den Zugriff auf Apps, Daten und Ressourcen Ihrer Organisation wird Ihnen Ihre Arbeit erleichtert.</span><span class="sxs-lookup"><span data-stu-id="b5cc9-105">Getting access to your organization’s apps, data, and resources makes it easier for you to do your job.</span></span> <span data-ttu-id="b5cc9-106">Ihre Organisation verwendet Intune zum [Verwalten des Zugriffs auf diese Ressourcen](what-happens-if-you-install-the-Company-Portal-app-and-enroll-your-device-in-intune-macos.md), weshalb Sie die Unternehmensportal-App für macOS herunterladen müssen.</span><span class="sxs-lookup"><span data-stu-id="b5cc9-106">Your organization is using Intune to [manage access to those resources](what-happens-if-you-install-the-Company-Portal-app-and-enroll-your-device-in-intune-macos.md), which requires you to download the Company Portal app for macOS.</span></span> <span data-ttu-id="b5cc9-107">Diese Anweisungen gelten für macOS-Geräte unter OS X El Capitan 10.11+.</span><span class="sxs-lookup"><span data-stu-id="b5cc9-107">These instructions will work for macOS devices on OS X El Capitan 10.11+.</span></span>

> [!NOTE]
> <span data-ttu-id="b5cc9-108">Anweisungen für das Registrieren von macOS-Geräten unter früheren Versionen von macOS finden Sie [hier](enroll-your-device-in-intune-macos-legacy.md).</span><span class="sxs-lookup"><span data-stu-id="b5cc9-108">You can find instructions for enrolling macOS devices on previous versions of macOS [here](enroll-your-device-in-intune-macos-legacy.md).</span></span>

1. <span data-ttu-id="b5cc9-109">Suchen Sie im __Dock__ nach __Safari__, und öffnen Sie ein neues Fenster. Öffnen Sie dann die [Unternehmensportal-Website](https://portal.manage.microsoft.com#HelpDeskDialog).</span><span class="sxs-lookup"><span data-stu-id="b5cc9-109">On your __Dock__, find __Safari__ and open a new window, then open the [Company Portal website](https://portal.manage.microsoft.com#HelpDeskDialog).</span></span>

2. <span data-ttu-id="b5cc9-110">Melden Sie sich bei mit Ihrem Geschäfts-, Schul- oder Unikonto bei der Unternehmensportal-Website an.</span><span class="sxs-lookup"><span data-stu-id="b5cc9-110">Log into the Company Portal website with your work or school account.</span></span>

[!INCLUDE[wit_nextref](includes/end-user-password-guidance.md)]

3. <span data-ttu-id="b5cc9-111">Klicken Sie nach der Anmeldung in der linken Ecke der Seite auf das **Menü**, und klicken sie auf **My Devices** (Meine Geräte).</span><span class="sxs-lookup"><span data-stu-id="b5cc9-111">After logging in, click on the **Menu** in the top left corner of the page and select **My Devices**.</span></span>

   ![Ein Screenshot der Startseite des Webportals; im Webportal wird angezeigt, dass noch keine Apps installiert werden können; darunter die Schaltfläche „Meine Geräte“.](./media/macOS_enroll_001_landing_page.png)

4. <span data-ttu-id="b5cc9-113">Auf der Seite __Meine Geräte__ wird entweder eine Liste der registrierten Geräte angezeigt oder einfach nur ein Banner.</span><span class="sxs-lookup"><span data-stu-id="b5cc9-113">On the __My Devices__ page, you will either see a list of enrolled devices or simply a banner.</span></span> <span data-ttu-id="b5cc9-114">Dies hängt davon ab, ob Sie bereits ein macOS- oder ein anderes Gerät registriert haben.</span><span class="sxs-lookup"><span data-stu-id="b5cc9-114">This depends on if you already have a device enrolled, macOS or otherwise.</span></span> <span data-ttu-id="b5cc9-115">Wählen Sie zum Registrieren eines nicht aufgelisteten Geräts das Banner mit dem folgenden Hinweis aus: __Wenn Ihr Gerät aufgelistet ist, klicken Sie hier, um es zu identifizieren. Sie können auch hier klicken, um ein nicht aufgelistetes Gerät zu registrieren.__</span><span class="sxs-lookup"><span data-stu-id="b5cc9-115">To enroll a device that is not listed, select the banner that says __If your device is listed, tap here to identify it. You can also tap here to enroll your device if it is not listed__.</span></span> <span data-ttu-id="b5cc9-116">Wenn Sie noch keine Geräte registriert haben, wird auf dem Banner Folgendes angezeigt: **You don't have any devices enrolled. Enroll this one by tapping here.** (Sie haben noch keine Geräte registriert. Tippen Sie hier, um dieses Gerät zu registrieren.)</span><span class="sxs-lookup"><span data-stu-id="b5cc9-116">If you don't have any enrolled devices, the banner will read **You don't have any devices enrolled. Enroll this one by tapping here.**</span></span>

    ![Ein Screenshot der Seite „Meine Geräte“ mit mehreren nicht identifizierten Geräten oberhalb der Banneraufforderung, nicht aufgelistete Geräte zu registrieren oder nicht identifizierte Geräte zu identifizieren.](./media/macOS_enroll_002_tap_here_banner.png)

5. <span data-ttu-id="b5cc9-118">Laden Sie die Unternehmensportal-App auf Ihr macOS-Gerät herunter, um die Registrierung fortzusetzen.</span><span class="sxs-lookup"><span data-stu-id="b5cc9-118">Download the Company Portal app to your macOS device to continue enrolling.</span></span>

    ![Der Hinweis, der einen Benutzer zum Herunterladen der macOS-Unternehmensportal-App auffordert.](./media/macOS_enroll_IWP_CP_app_notice.png)

6. <span data-ttu-id="b5cc9-121">Ihr Mac überprüft anschließend, ob der Download von **CompanyPortal.pkg** sicher geöffnet werden kann.</span><span class="sxs-lookup"><span data-stu-id="b5cc9-121">Your Mac will check to make sure that the download of **CompanyPortal.pkg** is safe to open.</span></span> <span data-ttu-id="b5cc9-122">Öffnen Sie das Installationsprogramm, und absolvieren Sie den Installationsvorgang.</span><span class="sxs-lookup"><span data-stu-id="b5cc9-122">Open the installer and go through the install process.</span></span>

7. <span data-ttu-id="b5cc9-123">Wenn das Installationsprogramm abgeschlossen ist, öffnen Sie den Ordner **Anwendungen** oder das **Launchpad**, und öffnen Sie anschließend **Unternehmensportal**.</span><span class="sxs-lookup"><span data-stu-id="b5cc9-123">When the installer has finished, open your **Applications** folder or the **Launchpad**, then open **Company Portal**.</span></span>

8. <span data-ttu-id="b5cc9-124">Ihr Mac wird Ihnen eine Meldung anzeigen, die folgendermaßen lautet: **Unternehmensportal ist eine Anwendung, die aus dem Internet heruntergeladen wurde. Sind Sie sicher, dass Sie diese öffnen möchten?**</span><span class="sxs-lookup"><span data-stu-id="b5cc9-124">Your Mac will show you a message that says, **"CompanyPortal" is an application downloaded from the Internet. Are you sure you want to open it?**</span></span> <span data-ttu-id="b5cc9-125">Klicken Sie auf **Öffnen**.</span><span class="sxs-lookup"><span data-stu-id="b5cc9-125">Click **Open**.</span></span>

  > [!NOTE]
  > <span data-ttu-id="b5cc9-126">Intune benötigt Zugriff auf Ihren Computer, um sicherzustellen, dass die Gerätesicherheit für den Zugriff auf Organisationsinformationen ausreicht.</span><span class="sxs-lookup"><span data-stu-id="b5cc9-126">Intune needs access to your computer to make sure that your device is secure enough to access your organization's resources.</span></span> <span data-ttu-id="b5cc9-127">Wenn Ihr Computer die Unternehmensportal-App nicht öffnen möchte, versuchen Sie, [den Gatekeeper auszuschalten](https://support.apple.com/HT202491) und die App anschließend zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="b5cc9-127">If your computer refuses to open the Company Portal app, try [turning off Gatekeeper](https://support.apple.com/HT202491) and then opening the app.</span></span>

9. <span data-ttu-id="b5cc9-128">Der erste Bildschirm, der Ihnen in der Unternehmensportal-App angezeigt wird, fordert Sie dazu auf, sich mit dem gleichen Geschäfts-, Schul- oder Unikonto **anzumelden**, mit dem Sie sich auf der Webseite des Unternehmensportals angemeldet haben.</span><span class="sxs-lookup"><span data-stu-id="b5cc9-128">The first screen you see in the Company Portal app prompts you to **Sign In** with the same work or school account you used to log in to the Company Portal website.</span></span>

10. <span data-ttu-id="b5cc9-129">Das Unternehmensportal bestätigt Ihre Kontoinformationen und zeigt Ihnen anschließend Ihre **Geräteregistrierungs-** und **Gerätekompatibilitätsstatus** an.</span><span class="sxs-lookup"><span data-stu-id="b5cc9-129">The Company Portal confirms your account information, then shows you your **Device Enrollment** and **Device Compliance** statuses.</span></span> <span data-ttu-id="b5cc9-130">Es werden gelbe Dreiecke angezeigt, durch die Ihnen mitgeteilt wird, dass Sie Maßnahmen ergreifen müssen, um sicherzustellen, dass Ihr Mac für die Verwendung bei der Arbeit sicher ist.</span><span class="sxs-lookup"><span data-stu-id="b5cc9-130">There will be yellow triangles letting you know that you have actions you'll need to take to make sure your Mac is safe for use at work.</span></span> <span data-ttu-id="b5cc9-131">Klicken Sie auf **Begin** (Starten), um mit der [Registrierung Ihres Geräts bei der Verwaltung](what-info-can-your-company-see-when-you-enroll-your-device-in-intune.md) zu beginnen.</span><span class="sxs-lookup"><span data-stu-id="b5cc9-131">Click **Begin** to start [enrolling your device into management](what-info-can-your-company-see-when-you-enroll-your-device-in-intune.md).</span></span>

11. <span data-ttu-id="b5cc9-132">Ihr Mac wird mit der Registrierung bei der Verwaltung starten.</span><span class="sxs-lookup"><span data-stu-id="b5cc9-132">Your Mac will begin enrolling into management.</span></span> <span data-ttu-id="b5cc9-133">Sie werden während dieser Zeit möglicherweise dazu aufgefordert, die Anmeldeinformationen Ihres Computers bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="b5cc9-133">You might be prompted to provide your computer's login information during this time.</span></span> <span data-ttu-id="b5cc9-134">Die Registrierung kann einige Minuten dauern.</span><span class="sxs-lookup"><span data-stu-id="b5cc9-134">This may take a few minutes to enroll.</span></span> <span data-ttu-id="b5cc9-135">Während dieser Zeit können Sie auf dem Computer andere Dinge tun.</span><span class="sxs-lookup"><span data-stu-id="b5cc9-135">During this time, you can do other things on your computer.</span></span> <span data-ttu-id="b5cc9-136">Sobald das Setup des Unternehmenszugriffs abgeschlossen ist, wird Ihnen eine Meldung angezeigt, die Sie darüber informiert.</span><span class="sxs-lookup"><span data-stu-id="b5cc9-136">A message appears once you've completed Company Access Setup to let you know you're done.</span></span>

<span data-ttu-id="b5cc9-137">Benötigen Sie weitere Unterstützung?</span><span class="sxs-lookup"><span data-stu-id="b5cc9-137">Still need help?</span></span> <span data-ttu-id="b5cc9-138">Kontaktieren Sie die Supportabteilung Ihres Unternehmens.</span><span class="sxs-lookup"><span data-stu-id="b5cc9-138">Check in with your company support.</span></span> <span data-ttu-id="b5cc9-139">Sie finden entsprechende Kontaktinformationen auf der [Unternehmensportal-Website](https://portal.manage.microsoft.com#HelpDeskDialog).</span><span class="sxs-lookup"><span data-stu-id="b5cc9-139">You can find their contact information on the [Company Portal website](https://portal.manage.microsoft.com#HelpDeskDialog).</span></span>
