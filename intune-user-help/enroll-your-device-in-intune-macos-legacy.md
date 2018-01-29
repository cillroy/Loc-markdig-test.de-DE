---
title: "Registrieren Ihres macOS-Legacygeräts bei Intune | Microsoft-Dokumentation"
description: "Beschreibt, wie Sie ein Mac OS-Gerät bei Intune registrieren."
keywords: Mac OS X, macOS, OS X
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 11/06/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 58eb0e7a-1321-4c66-a281-88fb01e72c1c
searchScope:
- User help
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: elocholi
ms.suite: ems
ms.custom: intune-enduser
ms.openlocfilehash: 99348421e395bd072cb208c6dd133f00fb522369
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2018
---
# <a name="enroll-your-legacy-macos-device-in-intune"></a><span data-ttu-id="2b2d9-104">Registrieren Ihres macOS-Legacygeräts bei Intune</span><span class="sxs-lookup"><span data-stu-id="2b2d9-104">Enroll your legacy macOS device in Intune</span></span>

<span data-ttu-id="2b2d9-105">Diese Anweisungen beziehen sich auf macOS-Geräte unter OS X Yosemite 10.10 und früher.</span><span class="sxs-lookup"><span data-stu-id="2b2d9-105">These instructions will work for macOS devices on OS X Yosemite 10.10 and previous.</span></span> <span data-ttu-id="2b2d9-106">Anweisungen für das Registrieren von macOS-Geräten unter neueren Versionen von macOS finden Sie [hier](enroll-your-device-in-intune-macos-cp.md).</span><span class="sxs-lookup"><span data-stu-id="2b2d9-106">You can find instructions for enrolling macOS devices on newer versions of macOS [here](enroll-your-device-in-intune-macos-cp.md).</span></span>

<span data-ttu-id="2b2d9-107">Sie benötigen Zugriff auf Apps, Daten und Ressourcen Ihrer Organisation, um Ihre Arbeit erledigen zu können.</span><span class="sxs-lookup"><span data-stu-id="2b2d9-107">Getting access to your organization’s apps, data, and resources makes it possible for you to do your job.</span></span> <span data-ttu-id="2b2d9-108">Wenn Sie bei der Arbeit ein Mac OS-Gerät verwenden, muss ein __Verwaltungsprofil__ installiert werden.</span><span class="sxs-lookup"><span data-stu-id="2b2d9-108">If you're using a macOS device at work, this means installing a __Management Profile__.</span></span> <span data-ttu-id="2b2d9-109">Hierbei handelt es sich um eine vom Support Ihres Unternehmens eingerichtete Datei, mit der Einstellungen und Zugriffsinformationen auf Ihren Mac geladen werden.</span><span class="sxs-lookup"><span data-stu-id="2b2d9-109">This is simply a file set up by your company support that loads settings and access information onto your Mac.</span></span> <span data-ttu-id="2b2d9-110">Möchten Sie mehr erfahren?</span><span class="sxs-lookup"><span data-stu-id="2b2d9-110">Want to know more?</span></span> <span data-ttu-id="2b2d9-111">Finden Sie heraus, [was geschieht, wenn Sie die Unternehmensportal-App installieren und Ihr Gerät bei Intune registrieren](what-happens-if-you-install-the-company-portal-app-and-enroll-your-device-in-intune-ios.md).</span><span class="sxs-lookup"><span data-stu-id="2b2d9-111">Find out [what happens when you install the Company Portal app and enroll your device in Intune](what-happens-if-you-install-the-company-portal-app-and-enroll-your-device-in-intune-ios.md)</span></span>

1. <span data-ttu-id="2b2d9-112">Suchen Sie im __Dock__ nach __Safari__, und öffnen Sie ein neues Fenster. Öffnen Sie dann die [Unternehmensportal-Website](https://portal.manage.microsoft.com#HelpDeskDialog).</span><span class="sxs-lookup"><span data-stu-id="2b2d9-112">On your __Dock__, find __Safari__ and open a new window, then open the [Company Portal website](https://portal.manage.microsoft.com#HelpDeskDialog).</span></span>
2. <span data-ttu-id="2b2d9-113">Melden Sie sich bei mit Ihrem Geschäfts-, Schul- oder Unikonto bei der Unternehmensportal-Website an.</span><span class="sxs-lookup"><span data-stu-id="2b2d9-113">Log into the Company Portal website with your work or school account.</span></span>

   [!INCLUDE [wit_nextref](includes/end-user-password-guidance.md)]


3. <span data-ttu-id="2b2d9-114">Klicken Sie nach der Anmeldung in der linken Ecke der Seite auf das **Menü**, und klicken sie auf **My Devices** (Meine Geräte).</span><span class="sxs-lookup"><span data-stu-id="2b2d9-114">After logging in, click on the **Menu** in the top left corner of the page and select **My Devices**.</span></span>

   ![Ein Screenshot der Startseite des Webportals; im Webportal wird angezeigt, dass noch keine Apps installiert werden können; darunter die Schaltfläche „Meine Geräte“.](./media/macOS_enroll_001_landing_page.png)

4. <span data-ttu-id="2b2d9-116">Auf der Seite __Meine Geräte__ wird entweder eine Liste der registrierten Geräte angezeigt oder einfach nur ein Banner.</span><span class="sxs-lookup"><span data-stu-id="2b2d9-116">On the __My Devices__ page, you will either see a list of enrolled devices or simply a banner.</span></span> <span data-ttu-id="2b2d9-117">Dies hängt davon ab, ob Sie bereits ein macOS- oder ein anderes Gerät registriert haben.</span><span class="sxs-lookup"><span data-stu-id="2b2d9-117">This depends on if you already have a device enrolled, macOS or otherwise.</span></span> <span data-ttu-id="2b2d9-118">Wählen Sie zum Registrieren eines nicht aufgelisteten Geräts das Banner mit dem folgenden Hinweis aus: __Wenn Ihr Gerät aufgelistet ist, klicken Sie hier, um es zu identifizieren. Sie können auch hier klicken, um ein nicht aufgelistetes Gerät zu registrieren.__</span><span class="sxs-lookup"><span data-stu-id="2b2d9-118">To enroll a device that is not listed, select the banner that says __If your device is listed, tap here to identify it. You can also tap here to enroll your device if it is not listed__.</span></span> <span data-ttu-id="2b2d9-119">Wenn Sie noch keine Geräte registriert haben, wird auf dem Banner Folgendes angezeigt: **You don't have any devices enrolled. Enroll this one by tapping here.** (Sie haben noch keine Geräte registriert. Tippen Sie hier, um dieses Gerät zu registrieren.)</span><span class="sxs-lookup"><span data-stu-id="2b2d9-119">If you don't have any enrolled devices, the banner will read **You don't have any devices enrolled. Enroll this one by tapping here.**</span></span>

   ![Ein Screenshot der Seite „Meine Geräte“ mit mehreren nicht identifizierten Geräten oberhalb der Banneraufforderung, nicht aufgelistete Geräte zu registrieren oder nicht identifizierte Geräte zu identifizieren.](./media/macOS_enroll_002_tap_here_banner.png)

5. <span data-ttu-id="2b2d9-121">Es wird ein Popupfenster mit einer kurzen Erläuterung dazu geöffnet, warum Sie __dieses Gerät identifizieren oder registrieren__ müssen.</span><span class="sxs-lookup"><span data-stu-id="2b2d9-121">A popup window will appear with a brief explanation of why you are going to __Identify or enroll this device__.</span></span> <span data-ttu-id="2b2d9-122">Lesen Sie die angezeigten Informationen, und klicken Sie auf __Registrieren__, um den Vorgang fortzusetzen.</span><span class="sxs-lookup"><span data-stu-id="2b2d9-122">Review this, then click __Enroll__ to proceed.</span></span>

   ![Dieses Mac OS-Gerät identifizieren oder registrieren](./media/macOS_enroll_003_IDenroll_popup.png)

6. <span data-ttu-id="2b2d9-124">Es wird ein zweites Popupfenster mit einer kurzen Erläuterung dazu geöffnet, was bei der __Registrierung dieses Geräts__ geschieht.</span><span class="sxs-lookup"><span data-stu-id="2b2d9-124">A second popup window will appear with a brief explanation of what will happen when you __Enroll this device__.</span></span> <span data-ttu-id="2b2d9-125">Lesen Sie die angezeigten Informationen, und klicken Sie auf __Installieren__, um den Vorgang fortzusetzen.</span><span class="sxs-lookup"><span data-stu-id="2b2d9-125">Review this, then click __Install__ to proceed.</span></span>

   ![Dieses Mac OS-Gerät registrieren](./media/macOS_enroll_004_enroll_popup.png)

   > [!NOTE]
   > <span data-ttu-id="2b2d9-127">Intune benötigt Zugriff auf Ihren Computer, um sicherzustellen, dass die Gerätesicherheit für den Zugriff auf Organisationsinformationen ausreicht.</span><span class="sxs-lookup"><span data-stu-id="2b2d9-127">Intune needs access to your computer to make sure that your device is secure enough to access your organization's resources.</span></span> <span data-ttu-id="2b2d9-128">Finden Sie heraus, [was geschieht, wenn Sie Ihr Gerät bei Intune registrieren](what-happens-if-you-install-the-Company-Portal-app-and-enroll-your-device-in-intune-ios.md).</span><span class="sxs-lookup"><span data-stu-id="2b2d9-128">Find out [what happens when you enroll your device in Intune](what-happens-if-you-install-the-Company-Portal-app-and-enroll-your-device-in-intune-ios.md).</span></span>

7. <span data-ttu-id="2b2d9-129">Die __Systemeinstellungen__ werden geöffnet, und Sie erhalten die Meldung __„Verwaltungsprofil“ installieren?__</span><span class="sxs-lookup"><span data-stu-id="2b2d9-129">__System Preferences__ will open, and ask you if you want to __Install "Management Profile"?__</span></span> <span data-ttu-id="2b2d9-130">Klicken Sie auf __Installieren__, um den Vorgang fortzusetzen, oder zeigen Sie weitere Details an, indem Sie auf __Profil anzeigen__ klicken.</span><span class="sxs-lookup"><span data-stu-id="2b2d9-130">Click __Install__ to proceed, or get more details by clicking __Show Profile__.</span></span>

   ![Verwaltungsprofil installieren](./media/macOS_enroll_005_sysprefs_mgmt_profile.png)

8. <span data-ttu-id="2b2d9-132">Ein Mac OS-Popupfenster wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="2b2d9-132">A macOS popup window will appear.</span></span> <span data-ttu-id="2b2d9-133">Bestätigen Sie, dass Sie die Änderungen durchführen möchten, indem Sie den __Benutzernamen__ und das __Kennwort__ für Ihren Computer eingeben, und klicken Sie auf __OK__.</span><span class="sxs-lookup"><span data-stu-id="2b2d9-133">Confirm that you want to make changes by providing your computer's __User Name__ and __Password__, then clicking __OK__.</span></span> <span data-ttu-id="2b2d9-134">Daraufhin wird das Verwaltungsprofil auf Ihrem Mac installiert.</span><span class="sxs-lookup"><span data-stu-id="2b2d9-134">This will install the management profile onto your Mac.</span></span>

   ![Popupfenster zur Mac OS-Profilinstallation](./media/macOS_enroll_006_sysprefs_admin_login.png)

9. <span data-ttu-id="2b2d9-136">Möglicherweise werden auf Ihrem Mac zusätzliche Meldungen mit weiteren Details zum Profil angezeigt, oder Sie müssen die __Installation__ bestätigen.</span><span class="sxs-lookup"><span data-stu-id="2b2d9-136">You may see some additional messages from your Mac with more details about the profile, or whether you're sure that you want to __Install__.</span></span> <span data-ttu-id="2b2d9-137">Klicken Sie auf __Weiter__ und __Installieren__, um den Vorgang fortzusetzen.</span><span class="sxs-lookup"><span data-stu-id="2b2d9-137">Click __Continue__ and __Install__ through these to proceed.</span></span> <span data-ttu-id="2b2d9-138">Sobald die Installation abgeschlossen ist, können Sie das neu installierte __Verwaltungsprofil__ in der Liste der __Geräteprofile__ anzeigen.</span><span class="sxs-lookup"><span data-stu-id="2b2d9-138">Once the installation finishes, you will be able to view your newly-installed __Management Profile__ in the list of __Device Profiles__.</span></span>

   ![Installiertes Mac OS-Profil](./media/macOS_enroll_007_sysprefs_installed_profile.png)

<span data-ttu-id="2b2d9-140">Bei einigen Profilen wird möglicherweise angezeigt, dass sie **Unverified** (Nicht überprüft) sind. Solange Sie zu Ihrem Unternehmen gehören, ist dies unbedenklich.</span><span class="sxs-lookup"><span data-stu-id="2b2d9-140">Some profiles may say that they're **Unverified**; as long as they're from your company, this is normal.</span></span>

<span data-ttu-id="2b2d9-141">Benötigen Sie weitere Unterstützung?</span><span class="sxs-lookup"><span data-stu-id="2b2d9-141">Still need help?</span></span> <span data-ttu-id="2b2d9-142">Kontaktieren Sie die Supportabteilung Ihres Unternehmens.</span><span class="sxs-lookup"><span data-stu-id="2b2d9-142">Check in with your company support.</span></span> <span data-ttu-id="2b2d9-143">Sie finden entsprechende Kontaktinformationen auf der [Unternehmensportal-Website](https://portal.manage.microsoft.com#HelpDeskDialog).</span><span class="sxs-lookup"><span data-stu-id="2b2d9-143">You can find their contact information on the [Company Portal website](https://portal.manage.microsoft.com#HelpDeskDialog).</span></span>
