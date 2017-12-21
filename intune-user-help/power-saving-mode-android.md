---
title: Verhindern des E-Mail-Zugriffs durch Energieoptimierung | Microsoft-Dokumentation
description: "Hier erfahren Sie, wie die Energieoptimierung für Android ausgeschaltet wird, um sicherzustellen, dass Sie Ihre E-Mail erhalten."
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 07/07/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: ad713f18-40a9-421f-aa2b-f8c21028d57c
searchScope: User help
ROBOTS: 
ms.reviewer: maxles
ms.suite: ems
ms.custom: intune-enduser
ms.openlocfilehash: 9564ad8700e88e33e6eba806037c743caf455158
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2017
---
# <a name="outlook-wont-sync-managed-email-when-battery-optimization-for-android-is-turned-on"></a><span data-ttu-id="fe4da-103">Bei aktivierter Akkuoptimierung für Android synchronisiert Outlook keine verwalteten E-Mails</span><span class="sxs-lookup"><span data-stu-id="fe4da-103">Outlook won't sync managed email when battery optimization for Android is turned on</span></span>

> [!IMPORTANT]
> <span data-ttu-id="fe4da-104">Dieses Problem wird hier dokumentiert, da diesbezüglich vermehrt Kundenberichte eingetroffen sind.</span><span class="sxs-lookup"><span data-stu-id="fe4da-104">This issue is documented here because we have been receiving an increased number of customer reports about it.</span></span> <span data-ttu-id="fe4da-105">Wenn das Problem nach Ausführung dieser Schritte weiterhin auftritt, wenden Sie sich für zusätzliche Hilfe an [die Supportabteilung Ihres Unternehmens](https://portal.manage.microsoft.com#HelpDeskDialog).</span><span class="sxs-lookup"><span data-stu-id="fe4da-105">If you continue to experience this issue after you have taken these steps, contact [your company support](https://portal.manage.microsoft.com#HelpDeskDialog) for additional help.</span></span>

<span data-ttu-id="fe4da-106">Durch die Registrierung Ihres Geräts bei Intune können Sie auf Unternehmensressourcen zugreifen.</span><span class="sxs-lookup"><span data-stu-id="fe4da-106">Enrolling your device in Intune lets you get access to company resources.</span></span> <span data-ttu-id="fe4da-107">Eine der gebräuchlichsten Ressourcen ist der E-Mail-Zugriff.</span><span class="sxs-lookup"><span data-stu-id="fe4da-107">One of the most common resources is email access.</span></span> <span data-ttu-id="fe4da-108">Ein Problem, das bei Android-Geräten beim Zugriff auf E-Mails über Outlook beobachtet wurde, tritt bei aktivierter Akkuoptimierung auf.</span><span class="sxs-lookup"><span data-stu-id="fe4da-108">An issue that we have seen with accessing email through Outlook for Android devices has been when battery optimization is turned on.</span></span> <span data-ttu-id="fe4da-109">Die Akkuoptimierung wird möglicherweise automatisch aktiviert, damit Ihr Gerät so lange wie möglich eingeschaltet bleibt.</span><span class="sxs-lookup"><span data-stu-id="fe4da-109">Battery optimization may turn on automatically to try to help your device stay powered on for as long as possible.</span></span> <span data-ttu-id="fe4da-110">Auf diese Weise kann die Akkuoptimierung teilweise hilfreich sein, da sie versucht, das automatische Herunterladen von E-Mails zu beenden.</span><span class="sxs-lookup"><span data-stu-id="fe4da-110">Battery optimization is partially able to help you this way because it tries to stop automatic email downloads.</span></span>

<span data-ttu-id="fe4da-111">Das Microsoft Intune-Team arbeitet aktiv an einer Lösung für dieses Problem.</span><span class="sxs-lookup"><span data-stu-id="fe4da-111">The Microsoft Intune team is actively working on a solution for this issue.</span></span> <span data-ttu-id="fe4da-112">Eine Möglichkeit zur Verhinderung, dass das Gerät in den niedrigen Energiestatus wechselt, besteht darin, sicherzustellen, dass der Akkustand immer über 30 % liegt.</span><span class="sxs-lookup"><span data-stu-id="fe4da-112">One way to prevent the device from entering low power mode is by making sure the battery maintains a charge of greater than 30%.</span></span> <span data-ttu-id="fe4da-113">Sie müssen das Unternehmensportal und Outlook aus der Liste der Apps entfernen, die von den Einstellungen für die Akkuoptimierung und den Energiesparmodus betroffen sind, damit das Problem im niedrigen Energiestatus nicht auftritt.</span><span class="sxs-lookup"><span data-stu-id="fe4da-113">To stop the issue from happening when you enter low power mode, you must remove the Company Portal and Outlook from the list of apps that are affected by battery optimization and power saving settings.</span></span>

<span data-ttu-id="fe4da-114">Es gibt viele Android-Geräte von den verschiedensten Herstellern.</span><span class="sxs-lookup"><span data-stu-id="fe4da-114">There are many Android devices that are made by many manufacturers.</span></span> <span data-ttu-id="fe4da-115">Leider können nicht für jedes Gerät die genauen auszuführenden Schritte dokumentiert werden.</span><span class="sxs-lookup"><span data-stu-id="fe4da-115">We cannot document the exact steps you need to take for every device.</span></span> <span data-ttu-id="fe4da-116">Möglicherweise müssen Sie diese Aktion nur in den Systemeinstellungen ausführen oder auch in bestimmten herstellerspezifischen Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="fe4da-116">You may need to take this action in just your system settings or also in certain manufacturer-specific settings.</span></span> <span data-ttu-id="fe4da-117">Wir haben einige gängige Beispiele dafür bereitgestellt, wie Sie dieses Problem auf Android-Geräten beheben können.</span><span class="sxs-lookup"><span data-stu-id="fe4da-117">We have provided some common examples of how you can resolve this issue on Android devices.</span></span>

## <a name="unmodified-android-devices"></a><span data-ttu-id="fe4da-118">Unveränderte Android-Geräte</span><span class="sxs-lookup"><span data-stu-id="fe4da-118">Unmodified Android devices</span></span>

<span data-ttu-id="fe4da-119">Viele Hersteller führen Änderungen an ihren Android-Geräten durch.</span><span class="sxs-lookup"><span data-stu-id="fe4da-119">Many manufacturers add modifications to their Android devices.</span></span> <span data-ttu-id="fe4da-120">Dadurch können sich bestimmte Interaktionen mit dem Gerät, z.B. Designs und Benachrichtigungen, ändern.</span><span class="sxs-lookup"><span data-stu-id="fe4da-120">This can change certain ways you interact with the device, like themes and notifications.</span></span> <span data-ttu-id="fe4da-121">Google nimmt in der Regel keine Änderungen dieser Art an den zugehörigen Telefonen vor.</span><span class="sxs-lookup"><span data-stu-id="fe4da-121">Google generally does not make these types of modifications to their phones.</span></span> <span data-ttu-id="fe4da-122">Beispiel: Auf einem Google Pixel-Gerät mit Android 7.0 oder höher würden Sie folgende Schritte ausführen, um diese Apps aus der Akkuoptimierung zu entfernen:</span><span class="sxs-lookup"><span data-stu-id="fe4da-122">For example, on a Google Pixel device with Android 7.0 or higher, you would follow these steps to remove these apps from battery optimization:</span></span>

1. <span data-ttu-id="fe4da-123">Öffnen Sie **Einstellungen**.</span><span class="sxs-lookup"><span data-stu-id="fe4da-123">Open **Settings**.</span></span>
2. <span data-ttu-id="fe4da-124">Tippen Sie auf **Akku** > **Weitere** > **Akkuoptimierung**.</span><span class="sxs-lookup"><span data-stu-id="fe4da-124">Tap **Battery** > **More** > **Battery optimization**.</span></span>
3. <span data-ttu-id="fe4da-125">Tippen Sie auf den Pfeil nach unten und anschließend auf **Nicht optimiert**.</span><span class="sxs-lookup"><span data-stu-id="fe4da-125">Tap the down arrow, then **Not optimized**.</span></span>
4. <span data-ttu-id="fe4da-126">Wählen Sie die Unternehmensportal-App und die Outlook-App aus, und deaktivieren Sie die Akkuoptimierung.</span><span class="sxs-lookup"><span data-stu-id="fe4da-126">Select the Company Portal and Outlook apps, and turn off battery optimization.</span></span>

## <a name="samsung-devices"></a><span data-ttu-id="fe4da-127">Samsung-Geräte</span><span class="sxs-lookup"><span data-stu-id="fe4da-127">Samsung devices</span></span>

<span data-ttu-id="fe4da-128">Bei anderen Android-Gerätetypen, z.B. Samsung-Geräten mit Android 7.0 oder höher, müssen Sie andere Schritte ausführen, um die Outlook- und die Unternehmensportal-App aus der Akkuoptimierung zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="fe4da-128">For other types of Android devices, such as Samsung devices with Android 7.0 or higher, you would have to follow different steps to remove the Outlook and Company Portal apps from battery optimization.</span></span>

1. <span data-ttu-id="fe4da-129">Öffnen Sie **Einstellungen**.</span><span class="sxs-lookup"><span data-stu-id="fe4da-129">Open **Settings**.</span></span>
2. <span data-ttu-id="fe4da-130">Tippen Sie auf **Menü (...)** > **Beschränkter Zugriff** > **Akkunutzung optimieren**.</span><span class="sxs-lookup"><span data-stu-id="fe4da-130">Tap **Menu (…)** > **Special access** > **Optimize battery usage**.</span></span>
3. <span data-ttu-id="fe4da-131">Wählen Sie **Alle Apps** aus der Dropdown-Liste aus.</span><span class="sxs-lookup"><span data-stu-id="fe4da-131">Select **All apps** from the dropdown.</span></span>
4. <span data-ttu-id="fe4da-132">**Deaktivieren** Sie die Umschalttaste neben der Unternehmensportal- und der Outlook-App, um die Akkuoptimierung zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="fe4da-132">Turn **Off** the toggle next to the Company Portal and Outlook apps to turn off battery optimization.</span></span>

<span data-ttu-id="fe4da-133">Wenn Sie ein Samsung-Gerät mit einer älteren Android-Version verwenden, müssen Sie folgende Schritte ausführen, um diese Apps aus dem Energiesparmodus zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="fe4da-133">In addition, if you are using a Samsung device that has a lower version of Android, you would need to follow these steps to remove these apps from power saving mode.</span></span>

1. <span data-ttu-id="fe4da-134">Öffnen Sie **Einstellungen**.</span><span class="sxs-lookup"><span data-stu-id="fe4da-134">Open **Settings**.</span></span>
2. <span data-ttu-id="fe4da-135">Tippen Sie auf **Gerätewartung** > **Akku** > **Nicht überwachte Apps**.</span><span class="sxs-lookup"><span data-stu-id="fe4da-135">Tap **Device maintenance** > **Battery** > **Unmonitored apps**.</span></span>
3. <span data-ttu-id="fe4da-136">Tippen Sie auf **Apps hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="fe4da-136">Tap **Add apps**.</span></span>
4. <span data-ttu-id="fe4da-137">Wählen Sie die Unternehmensportal- und die Outlook-App aus, und tippen Sie auf **Fertig**.</span><span class="sxs-lookup"><span data-stu-id="fe4da-137">Select the Company Portal and Outlook apps, and tap **Done**.</span></span>

## <a name="oneplus-devices"></a><span data-ttu-id="fe4da-138">OnePlus-Geräte</span><span class="sxs-lookup"><span data-stu-id="fe4da-138">OnePlus devices</span></span>

<span data-ttu-id="fe4da-139">Diese Einstellungen können beispielsweise auch über die Suche in den Systemeinstellungen lokalisiert werden.</span><span class="sxs-lookup"><span data-stu-id="fe4da-139">Another example of a different way to locate these settings is through searching in the system settings.</span></span> <span data-ttu-id="fe4da-140">Bei einem OnePlus 3-Gerät mit Android 7.1.1 würden Sie beispielsweise folgende Schritte ausführen:</span><span class="sxs-lookup"><span data-stu-id="fe4da-140">For example, on a OnePlus 3 with Android 7.1.1, you would follow these steps:</span></span> 

1. <span data-ttu-id="fe4da-141">Öffnen Sie **Systemeinstellungen**.</span><span class="sxs-lookup"><span data-stu-id="fe4da-141">Open **System Settings**.</span></span> 
2. <span data-ttu-id="fe4da-142">Tippen Sie auf die Schaltfläche **Suchen**.</span><span class="sxs-lookup"><span data-stu-id="fe4da-142">Tap the **Search** button.</span></span> <span data-ttu-id="fe4da-143">Diese ähnelt einer Lupe im oberen rechten Bildschirmbereich.</span><span class="sxs-lookup"><span data-stu-id="fe4da-143">This looks like a magnifying glass at the top right of the screen.</span></span> 
3. <span data-ttu-id="fe4da-144">Geben Sie in das Suchfeld **Akkuoptimierung** ein, und wählen Sie anschließend in der Anzeige **Einstellungen** die Option **Akkuoptimierung** aus.</span><span class="sxs-lookup"><span data-stu-id="fe4da-144">Type **battery optimization** into search, then select the **Battery Optimization** option on the **Settings** screen that appears.</span></span> 
4. <span data-ttu-id="fe4da-145">Tippen Sie auf **Akku** > **Akkuoptimierung**.</span><span class="sxs-lookup"><span data-stu-id="fe4da-145">Tap **Battery** > **Battery optimization**.</span></span>
5. <span data-ttu-id="fe4da-146">Wählen Sie die Unternehmensportal- und die Outlook-App aus, und wählen Sie anschließend **Nicht optimieren** aus.</span><span class="sxs-lookup"><span data-stu-id="fe4da-146">Select the Company Portal and Outlook apps, then select **Don't optimize**.</span></span> <span data-ttu-id="fe4da-147">Tippen Sie auf **Fertig**.</span><span class="sxs-lookup"><span data-stu-id="fe4da-147">Tap **Done**.</span></span>

<!--On a OnePlus 5 device with Android 7.1.1, you would follow these steps to remove these apps from battery optimization:
1. Open **Settings**.
2. Tap **Battery** > **Battery optimization**.
3. Select the Company Portal and Outlook apps, then select **Don’t optimize**. Tap **Done**.-->

<span data-ttu-id="fe4da-148">Benötigen Sie weitere Unterstützung?</span><span class="sxs-lookup"><span data-stu-id="fe4da-148">Still need help?</span></span> <span data-ttu-id="fe4da-149">Kontaktieren Sie den Support Ihres Unternehmens.</span><span class="sxs-lookup"><span data-stu-id="fe4da-149">Contact your company support.</span></span> <span data-ttu-id="fe4da-150">Die entsprechenden Kontaktinformationen finden Sie auf der [Unternehmensportal-Website](https://portal.manage.microsoft.com#HelpDeskDialog).</span><span class="sxs-lookup"><span data-stu-id="fe4da-150">For their contact information, check the [Company Portal website](https://portal.manage.microsoft.com#HelpDeskDialog).</span></span>
