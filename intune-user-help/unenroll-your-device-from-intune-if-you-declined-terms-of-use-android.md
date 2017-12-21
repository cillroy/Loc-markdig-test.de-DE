---
title: "Aufheben der Registrierung Ihres Geräts bei Ablehnung der Nutzungsbedingungen | Microsoft-Dokumentation"
description: 
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 03/13/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4278f000-0258-4de5-93a1-195b48e5061e
searchScope: User help
ROBOTS: 
ms.reviewer: chrisbal
ms.suite: ems
ms.custom: intune-enduser
ms.openlocfilehash: 779e822c7b04a9839495d5d5c8c4687a0340d9af
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2017
---
# <a name="unenroll-your-device-if-you-declined-terms-of-use"></a><span data-ttu-id="26fe0-102">Aufheben der Registrierung Ihres Geräts bei Ablehnung der „Nutzungsbedingungen“</span><span class="sxs-lookup"><span data-stu-id="26fe0-102">Unenroll your device if you declined "Terms of Use"</span></span>

<span data-ttu-id="26fe0-103">Die beste Methode zum Aufheben der Registrierung Ihres Android-Geräts ist, die Nutzungsbedingungen zu akzeptieren, sich bei der Unternehmensportal-App anzumelden und die Registrierung anschließend unter Beachtung [dieser Anweisungen](unenroll-your-device-from-intune-android.md) aufzuheben.</span><span class="sxs-lookup"><span data-stu-id="26fe0-103">The best way to unenroll your Android device is to accept the terms of use, sign in to the Company Portal app, and then use [these instructions](unenroll-your-device-from-intune-android.md) to unenroll.</span></span> <span data-ttu-id="26fe0-104">Wenn Sie allerdings beim Versuch, sich bei der Unternehmensportal-App anzumelden, die Nutzungsbedingungen abgelehnt haben, können Sie sich bei späteren Versuchen nicht mehr bei der Unternehmensportal-App anmelden, d.h. Sie müssen diese Anweisungen zur Problemumgehung verwenden, um das Gerät zu registrieren.</span><span class="sxs-lookup"><span data-stu-id="26fe0-104">However, if you declined the terms of use while trying to sign in to the Company Portal app, you are prevented from signing in to the Company Portal app on future tries, so you need to use these "workaround" instructions to unenroll your device.</span></span>

<span data-ttu-id="26fe0-105">Wenn Sie die Unternehmensportal-App deinstallieren, wird auch die Registrierung Ihres Geräts bei Intune aufgehoben.</span><span class="sxs-lookup"><span data-stu-id="26fe0-105">When you uninstall the Company Portal app, you are also unenrolling your device from Intune.</span></span> <span data-ttu-id="26fe0-106">Ihr Gerät wird nicht mehr auf Unternehmensressourcen zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="26fe0-106">Your device will no longer be able to access company resources.</span></span> <span data-ttu-id="26fe0-107">Weitere Informationen dazu, was bei Aufheben der Registrierung bei Intune geschieht, finden Sie unter [Was geschieht, wenn Sie die Registrierung Ihres Geräts bei Intune aufheben?](what-happens-if-you-unenroll-your-device-from-intune-android.md).</span><span class="sxs-lookup"><span data-stu-id="26fe0-107">For more about what happens when you unenroll, see [What happens if you unenroll your device from Intune?](what-happens-if-you-unenroll-your-device-from-intune-android.md).</span></span>

<span data-ttu-id="26fe0-108">Vor der Deinstallation der Unternehmensportal-App müssen Sie zur Einstellung **Geräteadministratoren** wechseln und **Unternehmensportal** deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="26fe0-108">Before you can uninstall the Company Portal app, you have to go to the **Device administrators** setting, and turn off **Company Portal**.</span></span> <span data-ttu-id="26fe0-109">Je nach Android-Gerät können sich diese Schritte geringfügig unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="26fe0-109">The steps may differ a little, depending on which Android device you have.</span></span>

<span data-ttu-id="26fe0-110">So können Sie die Registrierung Ihres Geräts bei Intune aufheben und die Unternehmensportal-App deinstallieren</span><span class="sxs-lookup"><span data-stu-id="26fe0-110">To unenroll your device from Intune and uninstall the Company Portal app:</span></span>

1.  <span data-ttu-id="26fe0-111">Wechseln Sie zu **Einstellungen**&gt;**Sicherheit&amp; Sperrbildschirm** &gt; **Geräteadministratoren**.</span><span class="sxs-lookup"><span data-stu-id="26fe0-111">Go to **Settings** &gt; **Security &amp; Screen Lock** &gt; **Device administrators**.</span></span>

    <span data-ttu-id="26fe0-112">Durch das Ausführen dieses Schritts wird die Registrierung Ihres Geräts sofort aufgehoben.</span><span class="sxs-lookup"><span data-stu-id="26fe0-112">Completing this step immediately unenrolls your device.</span></span>

2.  <span data-ttu-id="26fe0-113">Deaktivieren Sie das Kontrollkästchen neben **Unternehmensportal**, oder schalten Sie das Unternehmensportal aus.</span><span class="sxs-lookup"><span data-stu-id="26fe0-113">Uncheck the box next to, or turn off, **Company Portal**.</span></span>

    <span data-ttu-id="26fe0-114">Sie können die Unternehmensportal-App jetzt deinstallieren.</span><span class="sxs-lookup"><span data-stu-id="26fe0-114">You can now uninstall the Company Portal app.</span></span>

<span data-ttu-id="26fe0-115">Benötigen Sie weitere Unterstützung?</span><span class="sxs-lookup"><span data-stu-id="26fe0-115">Still need help?</span></span> <span data-ttu-id="26fe0-116">Wenden Sie sich an den Support Ihres Unternehmens (suchen Sie auf der [Unternehmensportal-Website](https://portal.manage.microsoft.com#HelpDeskDialog) nach Kontaktinformationen) oder an das <a href="mailto:wintunedroidfbk@microsoft.com?subject=I'm having unenrolling my Android device&body=Describe the issue you're experiencing here.">Microsoft Android-Team</a>.</span><span class="sxs-lookup"><span data-stu-id="26fe0-116">Contact your company support (check the [Company Portal website](https://portal.manage.microsoft.com#HelpDeskDialog) for contact information), or write the <a href="mailto:wintunedroidfbk@microsoft.com?subject=I'm having unenrolling my Android device&body=Describe the issue you're experiencing here.">Microsoft Android team</a>.</span></span>
