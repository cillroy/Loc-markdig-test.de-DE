---
title: "Remotesperre und Zurücksetzen der Kennung"
description: "Intune enthält Funktionen zum Remotesperren und zum Zurücksetzen der Kennung."
keywords: 
author: NathBarn
ms.author: NathBarn
manager: angrobe
ms.date: 03/06/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 970f8c81-7c7f-4789-9ed4-2133d50b9db6
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: chrisgre
ms.custom: intune-classic
ms.openlocfilehash: fc1cad418904de335b434a3726e2772d0558b303
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2018
---
# <a name="help-protect-your-devices-with-remote-lock-and-passcode-reset"></a><span data-ttu-id="9f1b4-103">Geräteschutz durch Remotesperre und Zurücksetzen der Kennung</span><span class="sxs-lookup"><span data-stu-id="9f1b4-103">Help protect your devices with remote lock and passcode reset</span></span>

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="9f1b4-104">Microsoft Intune enthält Funktionen zum Remotesperren und zum Zurücksetzen der Kennung.</span><span class="sxs-lookup"><span data-stu-id="9f1b4-104">Microsoft Intune provides both remote lock and passcode reset capabilities.</span></span>

## <a name="lock-a-device-remotely"></a><span data-ttu-id="9f1b4-105">Remotesperrung eines Geräts</span><span class="sxs-lookup"><span data-stu-id="9f1b4-105">Lock a device remotely</span></span>
<span data-ttu-id="9f1b4-106">Wenn ein Benutzer sein Gerät verliert, können Sie es remote sperren.</span><span class="sxs-lookup"><span data-stu-id="9f1b4-106">If a user loses a device, you can lock the device remotely.</span></span> <span data-ttu-id="9f1b4-107">Das Gerät muss bereits über eine PIN oder eine Kennung verfügen, bevor Sie die Remotesperre verwenden können.</span><span class="sxs-lookup"><span data-stu-id="9f1b4-107">The device must already have a PIN or passcode set on it before you can use remote lock.</span></span>

<span data-ttu-id="9f1b4-108">In der folgenden Tabelle ist die Funktionsweise der Remotesperrung auf verschiedenen mobilen Plattformen aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="9f1b4-108">The following table lists how remote lock works on different mobile platforms.</span></span>

|<span data-ttu-id="9f1b4-109">Plattform</span><span class="sxs-lookup"><span data-stu-id="9f1b4-109">Platform</span></span>|<span data-ttu-id="9f1b4-110">Remotesperre</span><span class="sxs-lookup"><span data-stu-id="9f1b4-110">Remote lock</span></span>|
|------------|---------------|
|<span data-ttu-id="9f1b4-111">macOS</span><span class="sxs-lookup"><span data-stu-id="9f1b4-111">macOS</span></span>|<span data-ttu-id="9f1b4-112">Nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="9f1b4-112">Not supported</span></span>|
|<span data-ttu-id="9f1b4-113">iOS</span><span class="sxs-lookup"><span data-stu-id="9f1b4-113">iOS</span></span>|<span data-ttu-id="9f1b4-114">Unterstützt</span><span class="sxs-lookup"><span data-stu-id="9f1b4-114">Supported</span></span>|
|<span data-ttu-id="9f1b4-115">Android</span><span class="sxs-lookup"><span data-stu-id="9f1b4-115">Android</span></span>|<span data-ttu-id="9f1b4-116">Unterstützt</span><span class="sxs-lookup"><span data-stu-id="9f1b4-116">Supported</span></span>|
|<span data-ttu-id="9f1b4-117">Android for Work</span><span class="sxs-lookup"><span data-stu-id="9f1b4-117">Android for Work</span></span>|<span data-ttu-id="9f1b4-118">Unterstützt</span><span class="sxs-lookup"><span data-stu-id="9f1b4-118">Supported</span></span>|
|<span data-ttu-id="9f1b4-119">Windows 10 (mobil)</span><span class="sxs-lookup"><span data-stu-id="9f1b4-119">Windows 10 (mobile)</span></span>|<span data-ttu-id="9f1b4-120">Unterstützt</span><span class="sxs-lookup"><span data-stu-id="9f1b4-120">Supported</span></span>|
|<span data-ttu-id="9f1b4-121">Windows 10 (Desktop)</span><span class="sxs-lookup"><span data-stu-id="9f1b4-121">Windows 10 (desktop)</span></span>|<span data-ttu-id="9f1b4-122">Nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="9f1b4-122">Not supported</span></span>|
|<span data-ttu-id="9f1b4-123">Windows Phone 8 und Windows Phone 8.1</span><span class="sxs-lookup"><span data-stu-id="9f1b4-123">Windows Phone 8 and Windows Phone 8.1</span></span>|<span data-ttu-id="9f1b4-124">Unterstützt</span><span class="sxs-lookup"><span data-stu-id="9f1b4-124">Supported</span></span>|
|<span data-ttu-id="9f1b4-125">Windows RT 8.1 und Windows RT</span><span class="sxs-lookup"><span data-stu-id="9f1b4-125">Windows RT 8.1 and Windows RT</span></span>|<span data-ttu-id="9f1b4-126">Unterstützt, wenn der aktuelle Benutzer des Geräts derjenige ist, der das Gerät registriert hat.</span><span class="sxs-lookup"><span data-stu-id="9f1b4-126">Supported if the current user of the device is the same user who enrolled the device.</span></span>|
|<span data-ttu-id="9f1b4-127">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="9f1b4-127">Windows 8.1</span></span>|<span data-ttu-id="9f1b4-128">Unterstützt, wenn der aktuelle Benutzer des Geräts derjenige ist, der das Gerät registriert hat.</span><span class="sxs-lookup"><span data-stu-id="9f1b4-128">Supported if the current user of the device is the same user who enrolled the device.</span></span>|

<span data-ttu-id="9f1b4-129">Die Remotesperre wird für Windows-PCs, die mit dem Intune-Softwareclient registriert wurden, nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="9f1b4-129">Remote lock is not supported for Windows PCs enrolled with the Intune software client.</span></span>

### <a name="lock-a-mobile-device-remotely-through-the-intune-console"></a><span data-ttu-id="9f1b4-130">Sperren eines mobilen Geräts remote über die Intune-Konsole</span><span class="sxs-lookup"><span data-stu-id="9f1b4-130">Lock a mobile device remotely through the Intune console</span></span>

1.  <span data-ttu-id="9f1b4-131">Wählen Sie in der [Intune-Verwaltungskonsole](https://manage.microsoft.com/) **Gruppen** &gt; **Alle Geräte** &gt; **Alle mobilen Geräte** aus.</span><span class="sxs-lookup"><span data-stu-id="9f1b4-131">In the [Intune administrator console](https://manage.microsoft.com/), choose **Groups** &gt; **All Devices** &gt; **All Mobile Devices**.</span></span>

2.  <span data-ttu-id="9f1b4-132">Wählen Sie bei Geräten, die bei Intune registriert sind, **Alle direkt verwalteten Geräte** aus. Andernfalls wählen Sie **Alle mit Exchange ActiveSync verwalteten Geräte** aus.</span><span class="sxs-lookup"><span data-stu-id="9f1b4-132">Choose **All Direct Managed Devices** for devices enrolled in Intune or **All Exchange ActiveSync Managed Devices**.</span></span>

    > [!TIP]
    > <span data-ttu-id="9f1b4-133">Sie können auch nach Benutzer zu einem Gerät navigieren.</span><span class="sxs-lookup"><span data-stu-id="9f1b4-133">You can also navigate to a device by user.</span></span> <span data-ttu-id="9f1b4-134">Klicken Sie auf **Alle Benutzer**.</span><span class="sxs-lookup"><span data-stu-id="9f1b4-134">Choose **All Users**.</span></span> <span data-ttu-id="9f1b4-135">Klicken Sie auf der Eigenschaftenseite des Benutzers auf **Geräte** und dann auf den Namen des mobilen Geräts, das Sie sperren möchten.</span><span class="sxs-lookup"><span data-stu-id="9f1b4-135">On the user's properties page, choose **Devices**, and then choose the name of the mobile device you want to lock.</span></span>

3.  <span data-ttu-id="9f1b4-136">Wählen Sie in der Liste die Geräte aus, die Sie sperren möchten.</span><span class="sxs-lookup"><span data-stu-id="9f1b4-136">In the list, choose the device or devices that you want to lock.</span></span> <span data-ttu-id="9f1b4-137">Wählen Sie auf der Taskleiste **Remoteaufgaben** und **Remotesperre** aus.</span><span class="sxs-lookup"><span data-stu-id="9f1b4-137">On the taskbar, choose **Remote Tasks** and select **Remote Lock**.</span></span>

## <a name="reset-the-passcode-on-a-device"></a><span data-ttu-id="9f1b4-138">Zurücksetzen der Kennung auf einem Gerät</span><span class="sxs-lookup"><span data-stu-id="9f1b4-138">Reset the passcode on a device</span></span>
<span data-ttu-id="9f1b4-139">Wenn ein Benutzer eine Kennung vergisst, können Sie ihm helfen, indem Sie die Kennung von einem Gerät entfernen oder eine neue temporäre Kennung auf einem Gerät erzwingen.</span><span class="sxs-lookup"><span data-stu-id="9f1b4-139">If a user forgets a passcode, you can help by removing the passcode from a device or by forcing a new temporary passcode on a device.</span></span> <span data-ttu-id="9f1b4-140">Die folgende Tabelle erläutert, wie das Zurücksetzen der Kennung auf verschiedenen mobilen Plattformen funktioniert.</span><span class="sxs-lookup"><span data-stu-id="9f1b4-140">The following table lists how passcode reset works on different mobile platforms.</span></span>

|<span data-ttu-id="9f1b4-141">Plattform</span><span class="sxs-lookup"><span data-stu-id="9f1b4-141">Platform</span></span>|<span data-ttu-id="9f1b4-142">Zurücksetzen der Kennung</span><span class="sxs-lookup"><span data-stu-id="9f1b4-142">Passcode reset</span></span>|
|------------|------------------|
|<span data-ttu-id="9f1b4-143">macOS</span><span class="sxs-lookup"><span data-stu-id="9f1b4-143">macOS</span></span>|<span data-ttu-id="9f1b4-144">Nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="9f1b4-144">Not supported</span></span>|
|<span data-ttu-id="9f1b4-145">iOS</span><span class="sxs-lookup"><span data-stu-id="9f1b4-145">iOS</span></span>|<span data-ttu-id="9f1b4-146">Wird für das Löschen der Kennung von einem Gerät unterstützt.</span><span class="sxs-lookup"><span data-stu-id="9f1b4-146">Supported for clearing the passcode from a device.</span></span> <span data-ttu-id="9f1b4-147">Es wird keine neue temporäre Kennung erstellt.</span><span class="sxs-lookup"><span data-stu-id="9f1b4-147">Does not create a new temporary passcode.</span></span>|
|<span data-ttu-id="9f1b4-148">Android</span><span class="sxs-lookup"><span data-stu-id="9f1b4-148">Android</span></span>|<span data-ttu-id="9f1b4-149">Unterstützt auf früheren Versionen als Android 7.0.</span><span class="sxs-lookup"><span data-stu-id="9f1b4-149">Supported on versions earlier than Android 7.0.</span></span> <span data-ttu-id="9f1b4-150">Erstellt eine temporäre Kennung.</span><span class="sxs-lookup"><span data-stu-id="9f1b4-150">Creates a temporary passcode.</span></span>|
|<span data-ttu-id="9f1b4-151">Android for Work</span><span class="sxs-lookup"><span data-stu-id="9f1b4-151">Android for Work</span></span>|<span data-ttu-id="9f1b4-152">Nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="9f1b4-152">Not supported</span></span>|
|<span data-ttu-id="9f1b4-153">Windows 10 Mobile</span><span class="sxs-lookup"><span data-stu-id="9f1b4-153">Windows 10 mobile</span></span>|<span data-ttu-id="9f1b4-154">Unterstützt für mobile Geräte mit Windows 10 Creators und höher, die in Azure AD eingebunden sind.</span><span class="sxs-lookup"><span data-stu-id="9f1b4-154">Supported for Windows 10 Creator version and later mobile devices that are Azure AD joined.</span></span>|
|<span data-ttu-id="9f1b4-155">Windows Phone 8 und Windows Phone 8.1</span><span class="sxs-lookup"><span data-stu-id="9f1b4-155">Windows Phone 8 and Windows Phone 8.1</span></span>|<span data-ttu-id="9f1b4-156">Unterstützt</span><span class="sxs-lookup"><span data-stu-id="9f1b4-156">Supported</span></span>|
|<span data-ttu-id="9f1b4-157">Windows RT 8.1</span><span class="sxs-lookup"><span data-stu-id="9f1b4-157">Windows RT 8.1</span></span>|<span data-ttu-id="9f1b4-158">Nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="9f1b4-158">Not Supported</span></span>|
|<span data-ttu-id="9f1b4-159">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="9f1b4-159">Windows 8.1</span></span>|<span data-ttu-id="9f1b4-160">Nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="9f1b4-160">Not Supported</span></span>|
|<span data-ttu-id="9f1b4-161">Windows 10 Desktop</span><span class="sxs-lookup"><span data-stu-id="9f1b4-161">Windows 10 desktop</span></span>|<span data-ttu-id="9f1b4-162">Nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="9f1b4-162">Not Supported</span></span>|

<span data-ttu-id="9f1b4-163">Das Zurücksetzen der Kennung wird für Windows-PCs, die mit dem Intune-Softwareclient registriert wurden, nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="9f1b4-163">Passcode reset is not supported for Windows PCs enrolled with the Intune software client.</span></span>

### <a name="reset-a-passcode"></a><span data-ttu-id="9f1b4-164">Zurücksetzen einer Kennung</span><span class="sxs-lookup"><span data-stu-id="9f1b4-164">Reset a passcode</span></span>

1.  <span data-ttu-id="9f1b4-165">Wählen Sie in der [Intune-Verwaltungskonsole](https://manage.microsoft.com/) **Gruppen** &gt; **Alle Geräte** &gt; **Alle mobilen Geräte** aus.</span><span class="sxs-lookup"><span data-stu-id="9f1b4-165">In the [Intune administrator console](https://manage.microsoft.com/), choose **Groups** &gt; **All Devices** &gt; **All Mobile Devices**.</span></span>

2.  <span data-ttu-id="9f1b4-166">Wählen Sie bei Geräten, die bei Intune registriert sind, **Alle direkt verwalteten Geräte** aus. Andernfalls wählen Sie **Alle mit Exchange ActiveSync verwalteten Geräte** aus.</span><span class="sxs-lookup"><span data-stu-id="9f1b4-166">Choose **All Direct Managed Devices** for devices enrolled in Intune or **All Exchange ActiveSync Managed Devices**.</span></span>

    > [!TIP]
    > <span data-ttu-id="9f1b4-167">Sie können auch nach Benutzer zu einem Gerät navigieren.</span><span class="sxs-lookup"><span data-stu-id="9f1b4-167">You can also navigate to a device by user.</span></span> <span data-ttu-id="9f1b4-168">Klicken Sie auf **Alle Benutzer**.</span><span class="sxs-lookup"><span data-stu-id="9f1b4-168">Click **All Users**.</span></span> <span data-ttu-id="9f1b4-169">Klicken Sie auf der Eigenschaftenseite des Benutzers auf **Geräte** und dann auf den Namen des mobilen Geräts, das Sie zurücksetzen möchten.</span><span class="sxs-lookup"><span data-stu-id="9f1b4-169">On the user's properties page, click **Devices**, and then click the name of the mobile device you want to wipe.</span></span>

3.  <span data-ttu-id="9f1b4-170">Wählen Sie in der Liste die Geräte aus, die Sie sperren möchten.</span><span class="sxs-lookup"><span data-stu-id="9f1b4-170">In the list, choose the device or devices that you want to lock.</span></span> <span data-ttu-id="9f1b4-171">Wählen Sie auf der Taskleiste **Remoteaufgaben** und **Kennungsrückstellung** aus.</span><span class="sxs-lookup"><span data-stu-id="9f1b4-171">On the taskbar, choose **Remote Tasks** and select **Passcode Reset**.</span></span>


### <a name="see-also"></a><span data-ttu-id="9f1b4-172">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="9f1b4-172">See also</span></span>
<span data-ttu-id="9f1b4-173">[Abkoppeln von Geräten](retire-devices-from-microsoft-intune-management.md) und [Windows Selective Wipe for Device Data Management](http://technet.microsoft.com/library/dn486874.aspx) (Selektives Zurücksetzen bei der Gerätedatenverwaltung in Windows)</span><span class="sxs-lookup"><span data-stu-id="9f1b4-173">[Retire devices](retire-devices-from-microsoft-intune-management.md) and [Windows Selective Wipe for Device Data Management](http://technet.microsoft.com/library/dn486874.aspx)</span></span>
