---
title: "Registrieren Ihres iOS-Geräts im Telecom Expense Management mit Intune"
description: "Erfahren Sie, wie Sie ein iOS-Gerät beim Telecom Expense Management registrieren."
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 04/19/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6d8c6372-f2ce-4558-8886-1d7c1966699c
searchScope: User help
ROBOTS: 
ms.reviewer: sumitp
ms.suite: ems
ms.custom: intune-enduser
ms.openlocfilehash: 1b34299070ce732334093275c835079cf9819e1b
ms.sourcegitcommit: e37e916e2bf14f092d3a767bc90d68c181d739fb
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/03/2018
---
# <a name="enroll-your-ios-device-in-telecom-expense-management"></a><span data-ttu-id="a3a4c-103">Registrieren Ihres iOS-Geräts im Telecom Expense Management</span><span class="sxs-lookup"><span data-stu-id="a3a4c-103">Enroll your iOS device in telecom expense management</span></span>

<span data-ttu-id="a3a4c-104">Vielleicht verwendet Ihre Organisation Telecom Expense Management-Software, um sicherzustellen, dass ihre Daten- und Voicepläne zulässige Grenzwerte einhalten.</span><span class="sxs-lookup"><span data-stu-id="a3a4c-104">Your organization may be using telecom expense management software to ensure that their data and voice plans are being used within acceptable limits.</span></span> <span data-ttu-id="a3a4c-105">Nachdem Sie die Registrierung des Geräts abgeschlossen haben, werden Sie aufgefordert, die beste Kategorie für das Gerät auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="a3a4c-105">Once you have completed enrolling your device, you will then be prompted select the best category for that device.</span></span>

  ![Dies ist ein Screenshot des Bildschirms zum „Auswählen der besten Kategorie für ein Gerät“ eines iOS-Geräts.](./media/ios-enroll-10-tem-select-best-category.png)

<span data-ttu-id="a3a4c-108">Wählen Sie die entsprechende Option aus, und Sie erhalten eine Benachrichtigung zum Installieren der [__Datalert__](https://itunes.apple.com/app/datalert/id771029268?mt=8)-App aus dem App Store.</span><span class="sxs-lookup"><span data-stu-id="a3a4c-108">Select the appropriate option, and you will receive a notification to install the [__Datalert__](https://itunes.apple.com/app/datalert/id771029268?mt=8) app from the App Store.</span></span> <span data-ttu-id="a3a4c-109">Mit der Datalert-App kann Ihre Organisation die Datenverwendung messen.</span><span class="sxs-lookup"><span data-stu-id="a3a4c-109">The Datalert app is how your organization can measure data usage.</span></span> <span data-ttu-id="a3a4c-110">Wenn Ihre Organisation die Microsoft-Geschäfts- oder Schulregistrierungsoption konfiguriert hat, werden Sie aufgefordert, sich mit Ihrem Geschäfts- oder Schulkonto anzumelden.</span><span class="sxs-lookup"><span data-stu-id="a3a4c-110">If your organization has configured the Microsoft work or school enrollment option, you will be required to log in with your work or school account.</span></span> <span data-ttu-id="a3a4c-111">Wenn diese Option noch nicht aktiviert wurde, müssen Sie Informationen wie Ihre Telefonnummer angeben und Ihr Gerät mithilfe eines Codes überprüfen, um sich von der App aus beim Datalert-Dienst zu registrieren.</span><span class="sxs-lookup"><span data-stu-id="a3a4c-111">If this hasn't been enabled, you will need to provide information such as your phone number and verify your device using a code to enroll into the Datalert service from the app.</span></span>

  ![Dies ist ein Screenshot des Begrüßungsbildschirms der Datalert-App, in dem Sie nach einer kurzen Erläuterung dazu, wie Sie mit Datalert Ihren Datenplan optimal nutzen können, aufgefordert werden, zum nächsten Bildschirm zu wechseln.](./media/ios-enroll-11-tem-datalert-setup.png)

## <a name="enroll-into-datalert-using-your-microsoft-work-or-school-account"></a><span data-ttu-id="a3a4c-113">Registrieren bei Datalert mit Ihrem Microsoft-Geschäfts- oder -Schulkonto</span><span class="sxs-lookup"><span data-stu-id="a3a4c-113">Enroll into Datalert using your Microsoft work or school account</span></span>

> [!NOTE]
> <span data-ttu-id="a3a4c-114">Für diese Art der Registrierung muss die [Microsoft Authenticator](https://docs.microsoft.com/azure/multi-factor-authentication/end-user/microsoft-authenticator-app-how-to)-App auf Ihrem Mobiltelefon installiert und aktiv sein.</span><span class="sxs-lookup"><span data-stu-id="a3a4c-114">You need to have the [Microsoft Authenticator](https://docs.microsoft.com/azure/multi-factor-authentication/end-user/microsoft-authenticator-app-how-to) app installed and active on your phone to enroll this way.</span></span>

1. <span data-ttu-id="a3a4c-115">Wählen Sie __Mit Microsoft-Konto anmelden__.</span><span class="sxs-lookup"><span data-stu-id="a3a4c-115">Select __Enroll with Microsoft account__.</span></span>

   ![Dies ist ein Bild des Einstellungenbildschirms der Datalert-App, das in der oberen Bildschirmhälfte ein Telefonnummernfeld zum Registrieren eines Geräts und unten „mit Microsoft-Konto registrieren“ enthält, sofern Sie über ein Microsoft Office 365-Konto und ein Intune-Abonnement verfügen.](./media/ios-enroll-11a-tem-datalert-enroll-msft-account.png)

2. <span data-ttu-id="a3a4c-117">Sie erhalten eine Benachrichtigung, dass __„Datalert“ „Authentifikator“ öffnen möchte__.</span><span class="sxs-lookup"><span data-stu-id="a3a4c-117">You'll receive a notification that __"Datalert" wants to open "Authenticator"__.</span></span> <span data-ttu-id="a3a4c-118">Wählen Sie __Öffnen__ aus.</span><span class="sxs-lookup"><span data-stu-id="a3a4c-118">Select __Open__.</span></span>

   ![Dies ist ein Bild des Popups, in dem der Benutzer auf Anforderung der Datalert-App zum Öffnen der Authentifikator-App aufgefordert wird.](./media/ios-enroll-11b-tem-datalert-open-authenticator.png)

3. <span data-ttu-id="a3a4c-120">Melden Sie sich mit Ihrem __Microsoft-Schul- oder -Geschäftskonto__ an.</span><span class="sxs-lookup"><span data-stu-id="a3a4c-120">Sign in with your __Microsoft school or work account__.</span></span> <span data-ttu-id="a3a4c-121">Das Datalert-Setup wird kurz durchgeführt und sollte dann abgeschlossen sein.</span><span class="sxs-lookup"><span data-stu-id="a3a4c-121">Datalert setup will work for a few moments, then should complete.</span></span> <span data-ttu-id="a3a4c-122">Berühren Sie nach Abschluss __Fertig stellen__.</span><span class="sxs-lookup"><span data-stu-id="a3a4c-122">Tap __Finish__ when it completes.</span></span>

## <a name="enroll-into-datalert-using-your-phone-number"></a><span data-ttu-id="a3a4c-123">Registrieren bei Datalert mit Ihrer Telefonnummer</span><span class="sxs-lookup"><span data-stu-id="a3a4c-123">Enroll into Datalert using your phone number</span></span>

1. <span data-ttu-id="a3a4c-124">Geben Sie die Telefonnummer des Geräts an.</span><span class="sxs-lookup"><span data-stu-id="a3a4c-124">Provide your device's phone number.</span></span>

   ![Dies ist ein Screenshot der Datalert-App mit der Aufforderung zur Eingabe einer Telefonnummer.](./media/ios-enroll-12-tem-datalert-phone-number.png)

2. <span data-ttu-id="a3a4c-126">Sie erhalten dann per SMS-Nachricht einen Überprüfungscode.</span><span class="sxs-lookup"><span data-stu-id="a3a4c-126">You will then receive a verification code through an SMS message.</span></span> <span data-ttu-id="a3a4c-127">Geben Sie den Code ein, und tippen Sie auf __OK__.</span><span class="sxs-lookup"><span data-stu-id="a3a4c-127">Provide the code and tap __OK__.</span></span>

   ![Dies ist ein Screenshot der Datalert-App mit der Aufforderung zur Eingabe des SMS-Überprüfungscodes.](./media/ios-enroll-13-tem-datalert-sms.png)

3. <span data-ttu-id="a3a4c-129">Nachdem Sie den Überprüfungscode angegeben haben, ist das Datalert-Setup abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="a3a4c-129">Once you've provided the verification code, Datalert setup will complete.</span></span> <span data-ttu-id="a3a4c-130">Tippen Sie auf __Fertig stellen__, und von nun an können Sie Ihre Daten mit der Datalert-App überwachen.</span><span class="sxs-lookup"><span data-stu-id="a3a4c-130">Tap __Finish__ and you will be able to monitor your data from the Datalert app.</span></span>

   ![Dieser Screenshot zeigt die Überwachung der Datennutzung von heute durch die Datalert-App.](./media/ios-enroll-14-tem-datalert-monitoring-active.png)

<span data-ttu-id="a3a4c-132">Sobald Sie sich registriert haben, zeigt Ihnen die Datalert-App Ihre Datennutzung an.</span><span class="sxs-lookup"><span data-stu-id="a3a4c-132">Once you've enrolled, you will begin to see your data usage in the Datalert app.</span></span>

<span data-ttu-id="a3a4c-133">Benötigen Sie weitere Unterstützung?</span><span class="sxs-lookup"><span data-stu-id="a3a4c-133">Still need help?</span></span> <span data-ttu-id="a3a4c-134">Kontaktieren Sie den Support Ihres Unternehmens.</span><span class="sxs-lookup"><span data-stu-id="a3a4c-134">Contact your company support.</span></span> <span data-ttu-id="a3a4c-135">Die entsprechenden Kontaktinformationen finden Sie auf der [Unternehmensportal-Website](https://portal.manage.microsoft.com#HelpDeskDialog).</span><span class="sxs-lookup"><span data-stu-id="a3a4c-135">For contact information, check the [Company Portal website](https://portal.manage.microsoft.com#HelpDeskDialog).</span></span>
