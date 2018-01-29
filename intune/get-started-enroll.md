---
title: "Erste Schritte bei der Geräteregistrierung"
titlesuffix: Azure portal
description: "Lernen Sie die den Registrierungsprozess umfassend kennen, indem Sie ein iOS-Gerät registrieren."
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 10/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: b595848d-c451-43ab-812d-b22e0170fb7a
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 3aae57892dcde2e33c30ede918817ecb6f423d63
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2018
---
# <a name="get-started-enrolling-devices"></a><span data-ttu-id="09fe0-103">Erste Schritte bei der Geräteregistrierung</span><span class="sxs-lookup"><span data-stu-id="09fe0-103">Get started enrolling devices</span></span>

<span data-ttu-id="09fe0-104">Mit Microsoft Intune können Sie Ihre Belegschaft mit mobilen Geräten ausstatten, ohne dass Ihre Unternehmensdaten gefährdet werden.</span><span class="sxs-lookup"><span data-stu-id="09fe0-104">Microsoft Intune helps you enable your workforce with mobile devices while keeping your corporate data protected.</span></span> <span data-ttu-id="09fe0-105">Da Ihre Endbenutzer mit Intune eher auf ihren Geräten als in der Verwaltungskonsole interagieren, sollten Sie mit der Registrierung vertraut sein.</span><span class="sxs-lookup"><span data-stu-id="09fe0-105">Since your end users will interact with Intune on their devices rather than in the admin console, you want to make sure that you are fluent with the enrollment experience.</span></span> <span data-ttu-id="09fe0-106">Auf diese Weise können Sie ausgezeichnete Kompatibilitätsrichtlinien zusammen mit Ihrer Erfahrung nutzen, um sich in die Lage Ihrer Benutzer hineinzuversetzen.</span><span class="sxs-lookup"><span data-stu-id="09fe0-106">This way, you can combine well-crafted compliance policies with your experience to show empathy for your users.</span></span> <span data-ttu-id="09fe0-107">Dies ist besonders wichtig, da Ihre Benutzer genau wissen werden, welche Informationen Sie als Administrator sehen können:</span><span class="sxs-lookup"><span data-stu-id="09fe0-107">This is especially important because your users will know exactly what information that you as an admin can see:</span></span>

| <span data-ttu-id="09fe0-108">Was für die IT nicht einsehbar ist</span><span class="sxs-lookup"><span data-stu-id="09fe0-108">What IT cannot see</span></span> | <span data-ttu-id="09fe0-109">Was für die IT einsehbar ist</span><span class="sxs-lookup"><span data-stu-id="09fe0-109">What IT can see</span></span> |
|---|---|
| <span data-ttu-id="09fe0-110">Ihren Anrufs- und Browserverlauf</span><span class="sxs-lookup"><span data-stu-id="09fe0-110">Calling and web browsing history</span></span> | <span data-ttu-id="09fe0-111">Modell</span><span class="sxs-lookup"><span data-stu-id="09fe0-111">Model</span></span> |
| <span data-ttu-id="09fe0-112">Standort</span><span class="sxs-lookup"><span data-stu-id="09fe0-112">Location</span></span> | <span data-ttu-id="09fe0-113">Seriennummer</span><span class="sxs-lookup"><span data-stu-id="09fe0-113">Serial number</span></span> |
| <span data-ttu-id="09fe0-114">Ihren persönlichen E-Mail-Account</span><span class="sxs-lookup"><span data-stu-id="09fe0-114">Personal email</span></span> | <span data-ttu-id="09fe0-115">Betriebssystemversion</span><span class="sxs-lookup"><span data-stu-id="09fe0-115">Operating system version</span></span> |
| <span data-ttu-id="09fe0-116">SMS</span><span class="sxs-lookup"><span data-stu-id="09fe0-116">Text messages</span></span> | <span data-ttu-id="09fe0-117">App-Namen</span><span class="sxs-lookup"><span data-stu-id="09fe0-117">App names</span></span> |
| <span data-ttu-id="09fe0-118">Kontakte</span><span class="sxs-lookup"><span data-stu-id="09fe0-118">Contacts</span></span> | <span data-ttu-id="09fe0-119">Besitzer</span><span class="sxs-lookup"><span data-stu-id="09fe0-119">Owner</span></span> |
| <span data-ttu-id="09fe0-120">Die Kennwörter für Ihre persönlichen Accounts</span><span class="sxs-lookup"><span data-stu-id="09fe0-120">Passwords to your personal accounts</span></span> | <span data-ttu-id="09fe0-121">Gerätename</span><span class="sxs-lookup"><span data-stu-id="09fe0-121">Device name</span></span> |
| <span data-ttu-id="09fe0-122">Ihre Termine</span><span class="sxs-lookup"><span data-stu-id="09fe0-122">Calendar events</span></span> | <span data-ttu-id="09fe0-123">Der Hersteller (gilt nur für Geräte, die nicht von Apple hergestellt wurden)</span><span class="sxs-lookup"><span data-stu-id="09fe0-123">Manufacturer (for devices not made by Apple)</span></span> |
| <span data-ttu-id="09fe0-124">Ihre Bilder, einschließlich dem, was sich in der Fotos- und Kamera-App befindet</span><span class="sxs-lookup"><span data-stu-id="09fe0-124">Pictures, including what's in the photos app or camera roll</span></span> | <span data-ttu-id="09fe0-125">Telefonnummer (Bei Arbeitsgeräten die vollständige Nummer).</span><span class="sxs-lookup"><span data-stu-id="09fe0-125">Phone number (for work devices, the whole number.</span></span> <span data-ttu-id="09fe0-126">Bei persönlichen Geräten nur die letzten vier Ziffern.)</span><span class="sxs-lookup"><span data-stu-id="09fe0-126">For personal devices, just the last four digits.)</span></span> |
 
## <a name="how-do-i-enroll-a-device"></a><span data-ttu-id="09fe0-127">Wie registriere ich ein Gerät?</span><span class="sxs-lookup"><span data-stu-id="09fe0-127">How do I enroll a device?</span></span>

<span data-ttu-id="09fe0-128">Das Registrieren eines Geräts ist für viele Endbenutzer beim Zugriff auf Unternehmensressourcen die erste Erfahrung.</span><span class="sxs-lookup"><span data-stu-id="09fe0-128">Enrolling a device is the first experience that many end users will have with accessing corporate resources.</span></span> <span data-ttu-id="09fe0-129">[Vertrautheit mit dieser Erfahrung](end-user-educate.md) kann ein möglicherweise unangenehmes Erlebnis in ein besseres verwandeln.</span><span class="sxs-lookup"><span data-stu-id="09fe0-129">[Understanding that experience](end-user-educate.md) can help make a potentially unpleasant experience into a better one.</span></span>

1. <span data-ttu-id="09fe0-130">Öffnen Sie den **App Store**, und suchen Sie nach **Intune-Unternehmensportal**.</span><span class="sxs-lookup"><span data-stu-id="09fe0-130">Open the **App Store** and search for **Intune Company Portal**.</span></span>
2. <span data-ttu-id="09fe0-131">Laden Sie die App **Microsoft Intune-Unternehmensportal** herunter.</span><span class="sxs-lookup"><span data-stu-id="09fe0-131">Download the **Microsoft Intune Company Portal** app.</span></span>
3. <span data-ttu-id="09fe0-132">Öffnen Sie die **Unternehmensportal-App**, geben Sie die E-Mail-Adresse und das Kennwort Ihres Testbenutzers ein, und tippen Sie dann auf **Anmelden**.</span><span class="sxs-lookup"><span data-stu-id="09fe0-132">Open the **Company Portal** app, enter your test user’s email address and password, then tap **Sign in**.</span></span>
4. <span data-ttu-id="09fe0-133">Ersetzen Sie das temporäre Kennwort durch ein neues.</span><span class="sxs-lookup"><span data-stu-id="09fe0-133">Update the temporary password to a new one.</span></span>
5. <span data-ttu-id="09fe0-134">Tippen Sie auf der Seite **Unternehmenszugriff einrichten** auf **Geräteregistrierung**.</span><span class="sxs-lookup"><span data-stu-id="09fe0-134">On the **Company Access Setup** page, tap **Device Enrollment**.</span></span>
6. <span data-ttu-id="09fe0-135">Lesen Sie auf der Seite **Gründe für das Registrieren Ihres Geräts**, welche Möglichkeiten ein Benutzer bei der Geräteregistrierung hat, und tippen Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="09fe0-135">On the **Why enroll your device?** page, read about what a user can do when they enroll their device, then tap **Continue**.</span></span>
7. <span data-ttu-id="09fe0-136">Sehen Sie sich in einer Liste an, welchen Zugriff ein Benutzer bei der Registrierung erhält, und tippen Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="09fe0-136">Review a list of what access a user gets when they enroll, then tap **Continue**.</span></span>
8. <span data-ttu-id="09fe0-137">Sehen Sie sich an, was IT-Administratoren auf einem Gerät sehen können und was nicht, und tippen Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="09fe0-137">Review what IT admins can and can’t see on a device, then tap **Continue**.</span></span>
9. <span data-ttu-id="09fe0-138">Lesen Sie auf der Seite **Was ist der nächste Schritt?**, was während der Registrierung passiert, und tippen Sie dann auf **Registrieren**.</span><span class="sxs-lookup"><span data-stu-id="09fe0-138">On the **What comes next** page, read about what happens during enrollment, then tap **Enroll**.</span></span>
10. <span data-ttu-id="09fe0-139">Tippen Sie auf der Seite **Profil installieren** auf **Installieren**, und geben Sie dann bei Aufforderung die Gerätekennung ein.</span><span class="sxs-lookup"><span data-stu-id="09fe0-139">On the **Install Profile** page, tap **Install**, then enter the device passcode if prompted.</span></span>
11. <span data-ttu-id="09fe0-140">Tippen Sie auf **Installieren**.</span><span class="sxs-lookup"><span data-stu-id="09fe0-140">Tap **Install**.</span></span>
12. <span data-ttu-id="09fe0-141">Tippen Sie erneut auf **Installieren**, um anzugeben, dass Sie die Warnung gelesen haben.</span><span class="sxs-lookup"><span data-stu-id="09fe0-141">Tap **Install** again to indicate that you’ve read the warning.</span></span>
13. <span data-ttu-id="09fe0-142">Tippen Sie im Popupfenster **Warnung** auf **Vertrauen**.</span><span class="sxs-lookup"><span data-stu-id="09fe0-142">On the **Warning** popup, tap **Trust**.</span></span>
14. <span data-ttu-id="09fe0-143">Wenn auf dem Bildschirm angezeigt wird, dass die Installation des Profils abgeschlossen ist, tippen Sie auf **Fertig**.</span><span class="sxs-lookup"><span data-stu-id="09fe0-143">When the screen changes to show that the profile has finished installing, tap **Done**.</span></span>
15. <span data-ttu-id="09fe0-144">Auf dem Bildschirm wird die Meldung „Gerät wird registriert“ angezeigt und im Anschluss gemeldet, dass das Gerät erfolgreich registriert wurde.</span><span class="sxs-lookup"><span data-stu-id="09fe0-144">An “Enrolling device” message shows on the screen, then shows that the device has successfully enrolled.</span></span> <span data-ttu-id="09fe0-145">Es öffnet sich ein Popupfenster mit der Aufforderung, die Seite im Unternehmensportal zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="09fe0-145">A popup will appear asking to open the page in the Company Portal.</span></span> <span data-ttu-id="09fe0-146">Tippen Sie auf **Öffnen**.</span><span class="sxs-lookup"><span data-stu-id="09fe0-146">Tap **Open**.</span></span>
16. <span data-ttu-id="09fe0-147">Sie kehren zur Seite **Unternehmenszugriff einrichten** zurück.</span><span class="sxs-lookup"><span data-stu-id="09fe0-147">You return to the **Company Access Setup** screen.</span></span> <span data-ttu-id="09fe0-148">Wenn Sie keine Testrichtlinien eingerichtet haben, sollte das Gerät als kompatibel angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="09fe0-148">If you have no test policies set up, then the device should appear compliant.</span></span> <span data-ttu-id="09fe0-149">Wenn Testrichtlinien vorhanden sind, tippen Sie auf **Gerätekompatibilität** und es wird angezeigt, dass Schritte durchgeführt werden müssen, um das Gerät sicherer zu machen.</span><span class="sxs-lookup"><span data-stu-id="09fe0-149">If you have any test policies, then tapping **Device Compliance** will show that there are things that need to be done to make the device secure.</span></span>

## <a name="next-steps"></a><span data-ttu-id="09fe0-150">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="09fe0-150">Next steps</span></span>

<span data-ttu-id="09fe0-151">[Erste Schritte beim Hinzufügen von Apps:](get-started-apps.md) Suchen Sie Apps, und fügen Sie sie auf Geräten hinzu, um Ihren Mitarbeitern die Arbeit zu erleichtern.</span><span class="sxs-lookup"><span data-stu-id="09fe0-151">[Get started with adding apps](get-started-apps.md) - Find and add apps to devices to make it possible for your employees to get work done.</span></span>

## <a name="learn-more"></a><span data-ttu-id="09fe0-152">Erfahren Sie mehr</span><span class="sxs-lookup"><span data-stu-id="09fe0-152">Learn more</span></span>

* [<span data-ttu-id="09fe0-153">Registrierungsoptionen für Intune</span><span class="sxs-lookup"><span data-stu-id="09fe0-153">Enrollment options for Intune</span></span>](enrollment-options.md)
* [<span data-ttu-id="09fe0-154">Aktivieren von BYOD mit Intune</span><span class="sxs-lookup"><span data-stu-id="09fe0-154">Enable bring your own device with Intune</span></span>](byod-enable.md)
* [<span data-ttu-id="09fe0-155">So informieren sie Ihre Benutzer über Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="09fe0-155">Educating your end users about enrollment and device management</span></span>](end-user-educate.md)
