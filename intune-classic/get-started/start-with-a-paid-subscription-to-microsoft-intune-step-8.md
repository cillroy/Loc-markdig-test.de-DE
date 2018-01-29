---
title: "Aktivieren der Geräteregistrierung"
description: "Legen Sie die MDM-Autorität fest, und aktivieren Sie die Registrierung für iOS-, Windows-, Android- und Mac-Geräte."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 02/14/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5d3215e7-0a5c-44bd-afb0-aeafce98c43f
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 343e579855e1f90cfc84ce821b711faa18c41390
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2018
---
# <a name="enable-enrollment-for-mobile-devices"></a><span data-ttu-id="15b52-103">Aktivieren der Registrierung für mobile Geräte</span><span class="sxs-lookup"><span data-stu-id="15b52-103">Enable enrollment for mobile devices</span></span>

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="15b52-104">In diesem Thema wird beschrieben, wie ein Intune-Administrator die Registrierung mobiler Geräte aktivieren kann.</span><span class="sxs-lookup"><span data-stu-id="15b52-104">This topic describes how an Intune administrator can enable mobile device enrollment.</span></span> <span data-ttu-id="15b52-105">Hilfe zur Verwendung von Intune auf Ihrem Telefon finden Sie unter [Verwenden verwalteter Geräte zum Erledigen von Aufgaben](https://docs.microsoft.com/intune-user-help/company-portal-frequently-asked-questions).</span><span class="sxs-lookup"><span data-stu-id="15b52-105">For help using Intune on your phone, see [using managed devices to get work done](https://docs.microsoft.com/intune-user-help/company-portal-frequently-asked-questions).</span></span>

<span data-ttu-id="15b52-106">Um die Verwaltung mobiler Geräte mit Intune einzurichten, müssen Sie zunächst die *Autorität für die Verwaltung mobiler Geräte* (Mobile Device Management, MDM) festlegen, die den Dienst identifiziert, der Ihrem Konto zugeordnete Geräte verwalten kann.</span><span class="sxs-lookup"><span data-stu-id="15b52-106">To set up mobile device management with Intune, you must first set the *mobile device management authority*, which identifies the service that can manage devices associated with your account.</span></span> <span data-ttu-id="15b52-107">In diesem Leitfaden wird vorausgesetzt, dass Sie nicht den System Center Configuration Manager, sondern den Intune-Dienst verwenden.</span><span class="sxs-lookup"><span data-stu-id="15b52-107">This guidance assumes you will use the Intune service instead of System Center Configuration Manager.</span></span> <span data-ttu-id="15b52-108">Nachdem die MDM-Autorität festgelegt wurde, können Sie die Verwaltung für Geräteplattformen aktivieren und Ihre Geräte mit der Unternehmensportal-App registrieren.</span><span class="sxs-lookup"><span data-stu-id="15b52-108">Once the MDM authority is set, you can enable management for device platforms, and enroll your devices with the Company Portal app.</span></span>

## <a name="enable-device-enrollment"></a><span data-ttu-id="15b52-109">Aktivieren der Geräteregistrierung</span><span class="sxs-lookup"><span data-stu-id="15b52-109">Enable device enrollment</span></span>

1. <span data-ttu-id="15b52-110">**Festlegen von Intune als Verwaltungsstelle für mobile Geräte**: Klicken Sie in der [Intune-Verwaltungskonsole](https://manage.microsoft.com/) auf **Verwaltung** > **Verwaltung mobiler Geräte**. Wählen Sie anschließend unter **Aufgaben** die Option **MDM-Autorität festlegen** aus.</span><span class="sxs-lookup"><span data-stu-id="15b52-110">**Make Intune your mobile device management authority** In the [Intune administration console](https://manage.microsoft.com/), choose **Admin** > **Mobile Device Management**, and then choose **Set MDM Authority** under **Tasks**.</span></span>  

2. <span data-ttu-id="15b52-111">Klicken Sie im Dialogfeld „MDM-Autorität“ auf **Ja**.</span><span class="sxs-lookup"><span data-stu-id="15b52-111">Choose **Yes** in the MDM Authority dialog box.</span></span>

    ![Verwaltungskonsole –](../media/intune-mdm-authority.png)

## <a name="choose-how-to-enroll-devices"></a><span data-ttu-id="15b52-114">Auswählen der Registrierungsmethode für Geräte</span><span class="sxs-lookup"><span data-stu-id="15b52-114">Choose how to enroll devices</span></span>

<span data-ttu-id="15b52-115">Intune kann je nach Unternehmensanforderungen Geräte in unterschiedlicher Weise verwalten.</span><span class="sxs-lookup"><span data-stu-id="15b52-115">Intune can manage devices in a variety of ways depending upon your company's requirements.</span></span> <span data-ttu-id="15b52-116">Zu den verfügbaren Registrierungsszenarien gehören beispielsweise BYOD (Bring Your Own Device), unternehmenseigene Geräte, CYOD (Choose Your Own Device) und Geräte im Kioskmodus.</span><span class="sxs-lookup"><span data-stu-id="15b52-116">"Bring your own device" (BYOD), corpoarte-owned devices, "choose your own device" (CYOD), and kiosk-mode devices are just a few available enrollment scenarios.</span></span>

<span data-ttu-id="15b52-117">Führen Sie diese Schritte zum [Auswählen der Registrierungsmethode für Geräte](choose-how-to-enroll-devices1.md) aus.</span><span class="sxs-lookup"><span data-stu-id="15b52-117">Follow these steps to [Choose how to enroll devices](choose-how-to-enroll-devices1.md).</span></span>

## <a name="enable-mdm-for-your-device-platform"></a><span data-ttu-id="15b52-118">Aktivieren von MDM für Ihre Geräteplattform</span><span class="sxs-lookup"><span data-stu-id="15b52-118">Enable MDM for your device platform</span></span>
<span data-ttu-id="15b52-119">Die Registrierung muss für iOS-, Mac- und Android for Work-Geräte aktiviert werden, indem eine Beziehung zwischen dem Plattformanbieter und Ihrem Intune-Mandanten eingerichtet wird.</span><span class="sxs-lookup"><span data-stu-id="15b52-119">Enrollment must be enabled for iOS, Mac, and Android for Work devices establishing a relationship between the platform provider and your Intune tenant.</span></span> <span data-ttu-id="15b52-120">Für Windows- und Android-Geräte sind keine zusätzlichen Schritte erforderlich, aber für Windows-Geräte können Sie die Geräteregistrierung für Ihre Benutzer vereinfachen, indem Sie einen besonderen DNS-Registrierungseintrag erstellen.</span><span class="sxs-lookup"><span data-stu-id="15b52-120">Windows and Android devices do not require additional steps, but for Windows devices you can simplify device enrollment for your users by creating a special DNS registry entry.</span></span>

<span data-ttu-id="15b52-121">Aktivieren Sie die Geräteregistrierung für die Geräteplattform, die Sie verwalten möchten.</span><span class="sxs-lookup"><span data-stu-id="15b52-121">Enable device enrollment for the device platform you want to manage.</span></span> <span data-ttu-id="15b52-122">Je nach Plattform sind andere Anforderungen relevant:</span><span class="sxs-lookup"><span data-stu-id="15b52-122">Depending on your platform, different requirements are needed:</span></span>

- [<span data-ttu-id="15b52-123">iOS und Mac OS</span><span class="sxs-lookup"><span data-stu-id="15b52-123">iOS and macOS</span></span>](/intune-classic/deploy-use/set-up-ios-and-mac-management-with-microsoft-intune)
- [<span data-ttu-id="15b52-124">Windows 10 und Windows Phone</span><span class="sxs-lookup"><span data-stu-id="15b52-124">Window 10 and Windows Phone</span></span>](/intune-classic/deploy-use/set-up-windows-device-management-with-microsoft-intune)
- <span data-ttu-id="15b52-125">[Windows-PC](/intune-classic/deploy-use/manage-windows-pcs-with-microsoft-intune) (Intune-Software-Client)</span><span class="sxs-lookup"><span data-stu-id="15b52-125">[Window PC](/intune-classic/deploy-use/manage-windows-pcs-with-microsoft-intune) (Intune software client)</span></span>
- [<span data-ttu-id="15b52-126">Android for Work</span><span class="sxs-lookup"><span data-stu-id="15b52-126">Android for Work</span></span>](/intune-classic/deploy-use/set-up-android-for-work)

<span data-ttu-id="15b52-127">Sobald die Registrierung aktiviert wurde, können Benutzer die Unternehmensportal-App auf ihr Gerät herunterladen und den Vorgang zur Geräteregistrierung durchführen.</span><span class="sxs-lookup"><span data-stu-id="15b52-127">Once enrollment is enabled, users can download the Company Portal app to their device and complete the device enrollment process.</span></span>

### <a name="enable-company-owned-device-enrollment"></a><span data-ttu-id="15b52-128">Aktivieren der Registrierung für unternehmenseigene Geräte</span><span class="sxs-lookup"><span data-stu-id="15b52-128">Enable company-owned device enrollment</span></span>
<span data-ttu-id="15b52-129">Sie können auch verschiedene Szenarien für die [Registrierung unternehmenseigener Geräte](/intune-classic/deploy-use/manage-corporate-owned-devices) unterstützen, darunter:</span><span class="sxs-lookup"><span data-stu-id="15b52-129">You can also enable a variety of [company-owned device enrollment](/intune-classic/deploy-use/manage-corporate-owned-devices) scenarios including:</span></span>
- [<span data-ttu-id="15b52-130">Apple-Geräteregistrierungsprogramm</span><span class="sxs-lookup"><span data-stu-id="15b52-130">Apple Device Enrollment Program</span></span>](/intune-classic/deploy-use/ios-device-enrollment-program-in-microsoft-intune)
- [<span data-ttu-id="15b52-131">Registrierung über den Setup-Assistenten für Apple Configurator</span><span class="sxs-lookup"><span data-stu-id="15b52-131">Apple Configurator Setup Assistant enrollment</span></span>](/intune-classic/deploy-use/ios-setup-assistant-enrollment-in-microsoft-intune)
- [<span data-ttu-id="15b52-132">Apple Configurator – Direkte Registrierung</span><span class="sxs-lookup"><span data-stu-id="15b52-132">Apple Configurator direct enrollment</span></span>](/intune-classic/deploy-use/ios-direct-enrollment-in-microsoft-intune)
- [<span data-ttu-id="15b52-133">Geräteregistrierungs-Manager</span><span class="sxs-lookup"><span data-stu-id="15b52-133">Device Enrollment Manager</span></span>](/intune-classic/deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune)

### <a name="next-steps"></a><span data-ttu-id="15b52-134">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="15b52-134">Next steps</span></span>
<span data-ttu-id="15b52-135">Gratulation!</span><span class="sxs-lookup"><span data-stu-id="15b52-135">Congratulations!</span></span> <span data-ttu-id="15b52-136">Sie haben den letzten Schritt der Kurzanleitung *Erste Schritte mit Intune* abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="15b52-136">You have just completed the last step of the *Intune quick start guide*.</span></span> <span data-ttu-id="15b52-137">Ihre anfängliche Konfiguration ist jetzt abgeschlossen, und Sie können in Betracht ziehen, weitere MDM-Funktionen zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="15b52-137">Now that your initial configuration is complete, you can consider enabling additional MDM functionality.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="15b52-138">[&larr; **Registrieren von Geräten**](.\start-with-a-paid-subscription-to-microsoft-intune-step-8.md)     [**Aufgaben nach der Konfiguration** &rarr;](.\post-configuration-tasks.md)</span><span class="sxs-lookup"><span data-stu-id="15b52-138">[&larr; **Enroll devices**](.\start-with-a-paid-subscription-to-microsoft-intune-step-8.md)     [**Post-configuration tasks** &rarr;](.\post-configuration-tasks.md)</span></span>  
