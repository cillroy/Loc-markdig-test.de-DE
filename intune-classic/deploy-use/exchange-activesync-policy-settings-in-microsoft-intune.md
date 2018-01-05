---
title: "Einstellungen für Exchange ActiveSync-Richtlinien"
description: "Verwenden Sie die Intune Exchange ActiveSync-Richtlinie, um Einstellungen zu konfigurieren, mit denen Sie Features und Funktionen auf Geräten steuern können, die von Exchange ActiveSync verwaltet werden."
keywords: 
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 12/27/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e9cbb826-b155-4df6-abf3-60c6f05b2783
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: ce07a0c9ac2d7ad32e31248aa97a967843862a21
ms.sourcegitcommit: e37e916e2bf14f092d3a767bc90d68c181d739fb
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/03/2018
---
# <a name="exchange-activesync-policy-settings-in-microsoft-intune"></a><span data-ttu-id="e89a5-103">Einstellungen für Exchange ActiveSync-Richtlinien in Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="e89a5-103">Exchange ActiveSync policy settings in Microsoft Intune</span></span>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="e89a5-104">Verwenden Sie die Microsoft Intune **Exchange ActiveSync**-Richtlinie, um Einstellungen zu konfigurieren, mit denen Sie eine Reihe von Features und Funktionen auf Geräten steuern können, die von Exchange ActiveSync verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="e89a5-104">Use the Microsoft Intune **Exchange ActiveSync** policy to configure settings that control a range of features and functionality on devices that are managed by Exchange ActiveSync.</span></span>


## <a name="password-settings"></a><span data-ttu-id="e89a5-105">Kennworteinstellungen</span><span class="sxs-lookup"><span data-stu-id="e89a5-105">Password settings</span></span>

|<span data-ttu-id="e89a5-106">Name der Einstellung</span><span class="sxs-lookup"><span data-stu-id="e89a5-106">Setting name</span></span>|<span data-ttu-id="e89a5-107">Details</span><span class="sxs-lookup"><span data-stu-id="e89a5-107">Details</span></span>
|----------------|---|
|<span data-ttu-id="e89a5-108">**Anfordern eines Kennworts zum Entsperren mobiler Geräte**</span><span class="sxs-lookup"><span data-stu-id="e89a5-108">**Require a password to unlock mobile devices**</span></span>|<span data-ttu-id="e89a5-109">Gibt an, ob Geräte mithilfe eines Kennworts gesperrt werden müssen.</span><span class="sxs-lookup"><span data-stu-id="e89a5-109">Specifies whether devices must be locked by using a password.</span></span><br><span data-ttu-id="e89a5-110">(Dies trifft nicht auf Geräte zu, auf denen Windows RT ausgeführt wird.)</span><span class="sxs-lookup"><span data-stu-id="e89a5-110">(not applicable to devices running Windows RT).</span></span>|
|<span data-ttu-id="e89a5-111">**Erforderlicher Kennworttyp**</span><span class="sxs-lookup"><span data-stu-id="e89a5-111">**Required password type**</span></span>|<span data-ttu-id="e89a5-112">Gibt den erforderlichen Typ des Kennworts an, z. B. nur numerisch oder alphanumerisch.</span><span class="sxs-lookup"><span data-stu-id="e89a5-112">Specifies the type of password that will be required, such as numeric only or alphanumeric.</span></span>|
|<span data-ttu-id="e89a5-113">**Minimale Kennwortlänge**</span><span class="sxs-lookup"><span data-stu-id="e89a5-113">**Minimum password length**</span></span>|<span data-ttu-id="e89a5-114">Gibt die Mindestanzahl von Zeichen an, die das Gerätekennwort enthalten muss.</span><span class="sxs-lookup"><span data-stu-id="e89a5-114">Specifies the minimum number of required characters in the device password.</span></span>|
|<span data-ttu-id="e89a5-115">**Einfache Kennwörter zulassen**</span><span class="sxs-lookup"><span data-stu-id="e89a5-115">**Allow simple passwords**</span></span>|<span data-ttu-id="e89a5-116">Gibt an, ob Sie einfache Kennwörter verwenden können, z. B. '0000' und '1234'.</span><span class="sxs-lookup"><span data-stu-id="e89a5-116">Specifies whether you can use simple passwords, which include ‘0000’ and ‘1234’.</span></span>|
|<span data-ttu-id="e89a5-117">**Anzahl zulässiger wiederholter Anmeldefehler, bevor das Gerät zurückgesetzt wird**</span><span class="sxs-lookup"><span data-stu-id="e89a5-117">**Number of repeated sign-in failures to allow before the device is wiped**</span></span>|<span data-ttu-id="e89a5-118">Gibt an, nach wie vielen Eingabeversuchen eines falschen Kennworts das Gerät zurückgesetzt wird.</span><span class="sxs-lookup"><span data-stu-id="e89a5-118">Specifies the number of times that a user can enter an incorrect password before the device is wiped.</span></span>|
|<span data-ttu-id="e89a5-119">**Kennwortablauf (Tage)**</span><span class="sxs-lookup"><span data-stu-id="e89a5-119">**Password expiration (days)**</span></span>|<span data-ttu-id="e89a5-120">Gibt die Anzahl der Tage an, nach denen das Gerätekennwort geändert werden muss.</span><span class="sxs-lookup"><span data-stu-id="e89a5-120">Specifies the number of days after which the device password must be changed.</span></span>
|<span data-ttu-id="e89a5-121">**Kennwortverlauf speichern**</span><span class="sxs-lookup"><span data-stu-id="e89a5-121">**Remember password history**</span></span>|<span data-ttu-id="e89a5-122">Gibt an, ob dem Benutzer zuvor bereits verwendete Kennwörter erlaubt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="e89a5-122">Specifies whether to not allow the use of previously used passwords.</span></span>|
|<span data-ttu-id="e89a5-123">**Kennwortverlauf speichern** – **Wiederverwendung vorheriger Kennwörter verhindern**</span><span class="sxs-lookup"><span data-stu-id="e89a5-123">**Remember password history** – **Prevent reuse of previous passwords**</span></span>|<span data-ttu-id="e89a5-124">Gibt die Anzahl der zuvor bereits verwendeten Kennwörter an, die nicht erneut verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="e89a5-124">Specifies the number of previously used passwords that can't be used again.</span></span>|
|<span data-ttu-id="e89a5-125">**Minuten Inaktivität vor Anforderung des Kennworts**</span><span class="sxs-lookup"><span data-stu-id="e89a5-125">**Minutes of inactivity before password is required**</span></span>|<span data-ttu-id="e89a5-126">Gibt den Zeitraum an, über den sich das Gerät im Leerlauf befinden muss, bevor der Bildschirm gesperrt wird.</span><span class="sxs-lookup"><span data-stu-id="e89a5-126">Specifies the amount of time that a device must be idle before the screen is locked.</span></span>

## <a name="encryption-settings"></a><span data-ttu-id="e89a5-127">Verschlüsselungseinstellungen</span><span class="sxs-lookup"><span data-stu-id="e89a5-127">Encryption settings</span></span>

|<span data-ttu-id="e89a5-128">Name der Einstellung</span><span class="sxs-lookup"><span data-stu-id="e89a5-128">Setting name</span></span>|<span data-ttu-id="e89a5-129">Details</span><span class="sxs-lookup"><span data-stu-id="e89a5-129">Details</span></span>|
|----------------|---|
|<span data-ttu-id="e89a5-130">**Verschlüsselung auf mobilen Geräten vorschreiben**<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="e89a5-130">**Require encryption on mobile device**<sup>1</sup></span></span>|<span data-ttu-id="e89a5-131">Erfordert die Verschlüsselung der Daten auf einem Gerät, falls dies unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="e89a5-131">Requires the data on a device to be encrypted when supported.</span></span><br><br><span data-ttu-id="e89a5-132">Für Windows Phone 8-Geräte müssen Sie hier **Ja**festlegen.</span><span class="sxs-lookup"><span data-stu-id="e89a5-132">For Windows Phone 8 devices, you must set this to **Yes**.</span></span><br /><br /><span data-ttu-id="e89a5-133">Aktivieren Sie zum Verwenden der Verschlüsselung auf iOS-Geräten die Einstellung **Kennwort zum Entsperren mobiler Geräte erforderlich**.</span><span class="sxs-lookup"><span data-stu-id="e89a5-133">To enable encryption on iOS devices, enable the **Require a password to unlock mobile devices** setting.</span></span>|
|<span data-ttu-id="e89a5-134">**Verschlüsselung auf Speicherkarten vorschreiben**</span><span class="sxs-lookup"><span data-stu-id="e89a5-134">**Require encryption on storage cards**</span></span>|<span data-ttu-id="e89a5-135">Erfordert die Verschlüsselung von Daten, die auf externen Speichern, wie etwa SD-Karten, gespeichert sind (auf unterstützten Geräten).</span><span class="sxs-lookup"><span data-stu-id="e89a5-135">Requires data that is stored on external storage such as an SD card to be encrypted (on supported devices).</span></span>

<span data-ttu-id="e89a5-136"><sup>1</sup> Zusätzliche Informationen für Geräte unter Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="e89a5-136"><sup>1</sup> Additional information for devices that run Windows 8.1</span></span>

-   <span data-ttu-id="e89a5-137">Um die Verschlüsselung auf Geräten zu erzwingen, auf denen Windows 8.1 ausgeführt wird, installieren Sie das [MDM-Clientupdate für Windows von Dezember 2014](https://support.microsoft.com/kb/3013816) auf jedem Gerät.</span><span class="sxs-lookup"><span data-stu-id="e89a5-137">If you want to enforce encryption on devices that run Windows 8.1, you must install the [December 2014 MDM client update for Windows](https://support.microsoft.com/kb/3013816) on each device.</span></span>

-   <span data-ttu-id="e89a5-138">Wenn Sie diese Einstellung für Windows 8.1-Geräte aktivieren, müssen alle Benutzer des Geräts ein Microsoft-Konto haben.</span><span class="sxs-lookup"><span data-stu-id="e89a5-138">If you enable this setting for Windows 8.1 devices, all users of the device must have a Microsoft account.</span></span>

-   <span data-ttu-id="e89a5-139">Damit die Verschlüsselung für Windows 8.1-Geräte funktioniert, muss das Gerät die Hardwarezertifizierungsanforderungen für Microsoft [InstantGo](http://blogs.windows.com/bloggingwindows/2014/06/19/instantgo-a-better-way-to-sleep/) erfüllen.</span><span class="sxs-lookup"><span data-stu-id="e89a5-139">If you want encryption to work for Windows 8.1 devices, the device must meet the Microsoft [InstantGo](http://blogs.windows.com/bloggingwindows/2014/06/19/instantgo-a-better-way-to-sleep/) hardware certification requirements.</span></span>

-   <span data-ttu-id="e89a5-140">Wenn Sie die Verschlüsselung auf einem Windows 8.1-Gerät erzwingen, ist der Wiederherstellungsschlüssel nur über das Microsoft-Konto des Benutzers zugänglich. Der Zugriff erfolgt über das OneDrive-Konto des Benutzers.</span><span class="sxs-lookup"><span data-stu-id="e89a5-140">If you enforce encryption on a Windows 8.1 device, the recovery key is only accessible from the user's Microsoft account, which is accessed from the user's OneDrive account.</span></span> <span data-ttu-id="e89a5-141">Sie können diesen Schlüssel nicht im Auftrag eines Benutzers wiederherstellen.</span><span class="sxs-lookup"><span data-stu-id="e89a5-141">You cannot recover this key on behalf of a user.</span></span>

## <a name="email-settings"></a><span data-ttu-id="e89a5-142">E-Mail-Einstellungen</span><span class="sxs-lookup"><span data-stu-id="e89a5-142">Email settings</span></span>

|<span data-ttu-id="e89a5-143">Name der Einstellung</span><span class="sxs-lookup"><span data-stu-id="e89a5-143">Setting name</span></span>|<span data-ttu-id="e89a5-144">Details</span><span class="sxs-lookup"><span data-stu-id="e89a5-144">Details</span></span>
|----------------|---|
|<span data-ttu-id="e89a5-145">**Herunterladen von E-Mail-Anhängen für Benutzer zulassen**</span><span class="sxs-lookup"><span data-stu-id="e89a5-145">**Allow users to download email attachments**</span></span>|<span data-ttu-id="e89a5-146">Gibt an, ob E-Mail-Anlagen auf das Gerät heruntergeladen werden können.</span><span class="sxs-lookup"><span data-stu-id="e89a5-146">Specifies whether email attachments can be downloaded to the device.</span></span>|
|<span data-ttu-id="e89a5-147">**Synchronisierungszeitraum für E-Mail**</span><span class="sxs-lookup"><span data-stu-id="e89a5-147">**Email synchronization period**</span></span>|<span data-ttu-id="e89a5-148">Gibt die Anzahl der Tage an, über die empfangene E-Mails mit dem Gerät synchronisiert werden.</span><span class="sxs-lookup"><span data-stu-id="e89a5-148">Specifies the number of days of received email that will be synchronized to the device.</span></span>
|<span data-ttu-id="e89a5-149">**Synchronisierung mit Exchange für mobile Geräte zulassen, von denen Exchange ActiveSync-Einstellungen nicht vollständig unterstützt werden**</span><span class="sxs-lookup"><span data-stu-id="e89a5-149">**Allow mobile devices that don’t fully support Exchange ActiveSync settings to synchronize with Exchange**</span></span>|<span data-ttu-id="e89a5-150">Gibt an, ob Exchange der Zugriff auf Geräte erlaubt wird, die eine oder mehrere Exchange ActiveSync-Einstellungen nicht unterstützen.</span><span class="sxs-lookup"><span data-stu-id="e89a5-150">Specifies whether to allow Exchange access on devices that don't support one or more Exchange ActiveSync settings.</span></span>

## <a name="browser-settings"></a><span data-ttu-id="e89a5-151">Browsereinstellungen</span><span class="sxs-lookup"><span data-stu-id="e89a5-151">Browser settings</span></span>

|<span data-ttu-id="e89a5-152">Name der Einstellung</span><span class="sxs-lookup"><span data-stu-id="e89a5-152">Setting name</span></span>|<span data-ttu-id="e89a5-153">Details</span><span class="sxs-lookup"><span data-stu-id="e89a5-153">Details</span></span>
|----------------|---|
|<span data-ttu-id="e89a5-154">**Webbrowser zulassen**</span><span class="sxs-lookup"><span data-stu-id="e89a5-154">**Allow web browser**</span></span>|<span data-ttu-id="e89a5-155">Gibt an, ob der Webbrowser des Geräts verwendet werden darf.</span><span class="sxs-lookup"><span data-stu-id="e89a5-155">Specifies whether the web browser on the device can be used.</span></span><br><span data-ttu-id="e89a5-156">(Für Windows RT oder Windows Phone nicht verfügbar.)</span><span class="sxs-lookup"><span data-stu-id="e89a5-156">(Not available for Windows RT or Windows Phone).</span></span>

## <a name="hardware-settings"></a><span data-ttu-id="e89a5-157">Hardware-Einstellungen</span><span class="sxs-lookup"><span data-stu-id="e89a5-157">Hardware settings</span></span>

|<span data-ttu-id="e89a5-158">Name der Einstellung</span><span class="sxs-lookup"><span data-stu-id="e89a5-158">Setting name</span></span>|<span data-ttu-id="e89a5-159">Details</span><span class="sxs-lookup"><span data-stu-id="e89a5-159">Details</span></span>
|----------------|---|
|<span data-ttu-id="e89a5-160">**Kamera zulassen**</span><span class="sxs-lookup"><span data-stu-id="e89a5-160">**Allow camera**</span></span>|<span data-ttu-id="e89a5-161">Gibt an, ob die Kamera des Geräts verwendet werden darf.</span><span class="sxs-lookup"><span data-stu-id="e89a5-161">Specifies whether the camera on the device can be used.</span></span><br><span data-ttu-id="e89a5-162">(Für Windows RT oder Windows Phone nicht verfügbar.)</span><span class="sxs-lookup"><span data-stu-id="e89a5-162">(Not available for Windows RT or Windows Phone).</span></span>



### <a name="see-also"></a><span data-ttu-id="e89a5-163">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e89a5-163">See also</span></span>
[<span data-ttu-id="e89a5-164">Verwalten von Einstellungen und Features auf Ihren Geräten mit Microsoft Intune-Richtlinien</span><span class="sxs-lookup"><span data-stu-id="e89a5-164">Manage settings and features on your devices with Microsoft Intune policies</span></span>](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)
