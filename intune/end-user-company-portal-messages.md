---
title: "Unternehmensportalmeldungen, die Benutzern möglicherweise unter Android angezeigt werden"
description: "Beschreibt Unternehmensportal-App-Meldungen, die Intune-Endbenutzern möglicherweise angezeigt werden."
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 03/09/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3df993aa-48c5-4799-b68d-c85fe4f7b02c
ms.reviewer: jeffgilb
ms.suite: ems
ms.openlocfilehash: f1a5c8a15007a38942fe543e6c1062bf957a481c
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2017
---
# <a name="help-end-users-understand-company-portal-app-messages"></a><span data-ttu-id="3e085-103">Grundlegendes zum Verständnis von Meldungen in der Unternehmensportal-App</span><span class="sxs-lookup"><span data-stu-id="3e085-103">Help end users understand Company Portal app messages</span></span>

[!INCLUDE[both-portals](./includes/note-for-both-portals.md)]

> [!NOTE]
> <span data-ttu-id="3e085-104">Die folgenden Informationen gelten nur für Geräte mit Android 6.0 und höher.</span><span class="sxs-lookup"><span data-stu-id="3e085-104">The following information applies only on devices with Android 6.0+.</span></span>

<span data-ttu-id="3e085-105">An verschiedenen Punkten des Registrierungsprozesses sehen Benutzer zwei verschiedene Meldungen, die Anlass zur Sorge geben könnten.</span><span class="sxs-lookup"><span data-stu-id="3e085-105">At different points in the enrollment process, end users will see two different messages that could be cause for concern.</span></span>

- <span data-ttu-id="3e085-106">__Zulassen, dass das Unternehmensportal Telefonanrufe tätigt und verwaltet?__</span><span class="sxs-lookup"><span data-stu-id="3e085-106">__Allow Company Portal to make and manage phone calls?__</span></span>
- <span data-ttu-id="3e085-107">__Unternehmensportal den Zugriff auf Fotos, Medien und Dateien auf Ihrem Gerät erlauben?__</span><span class="sxs-lookup"><span data-stu-id="3e085-107">__Allow Company Portal to access photos, media, and files on your device?__</span></span>

## <a name="allow-company-portal-to-make-and-manage-phone-calls"></a><span data-ttu-id="3e085-108">Zulassen, dass das Unternehmensportal Telefonanrufe tätigt und verwaltet?</span><span class="sxs-lookup"><span data-stu-id="3e085-108">Allow Company Portal to make and manage phone calls?</span></span>

### <a name="where-it-appears"></a><span data-ttu-id="3e085-109">Position in der Oberfläche</span><span class="sxs-lookup"><span data-stu-id="3e085-109">Where it appears</span></span>
<span data-ttu-id="3e085-110">Die Meldung **Zulassen, dass das Unternehmensportal Telefonanrufe tätigt und verwaltet?** wird angezeigt, wenn Benutzer in der Unternehmensportal-App auf **Registrieren** tippen, während sie ihr Gerät registrieren.</span><span class="sxs-lookup"><span data-stu-id="3e085-110">The message **Allow Company Portal to make and manage phone calls?** appears when users tap **Enroll** in the Company Portal app while they are enrolling their device.</span></span>

### <a name="what-it-means"></a><span data-ttu-id="3e085-111">Bedeutung</span><span class="sxs-lookup"><span data-stu-id="3e085-111">What it means</span></span>
<span data-ttu-id="3e085-112">Mit Akzeptieren dieser Aufforderung lassen Benutzer zu, dass die Telefon- und IMEI-Nummern ihrer Geräte an den Intune-Dienst gesendet werden.</span><span class="sxs-lookup"><span data-stu-id="3e085-112">By accepting this prompt, users allow their device's phone and IMEI numbers to be sent to the Intune service.</span></span> <span data-ttu-id="3e085-113">Diese werden in der Verwaltungskonsole auf der Seite __Hardware__ angezeigt.</span><span class="sxs-lookup"><span data-stu-id="3e085-113">These will appear on the admin console on the __Hardware__ page.</span></span>

> [!NOTE]
> <span data-ttu-id="3e085-114">**Die Unternehmensportal-App tätigt oder verwaltet keine Telefonanrufe!**</span><span class="sxs-lookup"><span data-stu-id="3e085-114">**The Company Portal app never makes or manages phone calls!**</span></span> <span data-ttu-id="3e085-115">Der Meldungstext wird von Google gesteuert und kann nicht geändert werden.</span><span class="sxs-lookup"><span data-stu-id="3e085-115">The message text is controlled by Google and cannot be changed.</span></span>

<span data-ttu-id="3e085-116">Zum Anzeigen der Seite **Hardware** wechseln Sie zu **Gruppen** > **Alle mobilen Geräte** > **Geräte**.</span><span class="sxs-lookup"><span data-stu-id="3e085-116">To see the **Hardware** page, go to **Groups** > **All mobile devices** > **Devices**.</span></span> <span data-ttu-id="3e085-117">Wählen Sie das Gerät des Benutzers aus, und wechseln Sie zu **Eigenschaften anzeigen** > **Hardware**.</span><span class="sxs-lookup"><span data-stu-id="3e085-117">Select the user's device, and go to **View Properties** > **Hardware**.</span></span>

### <a name="what-happens-if-users-deny-access"></a><span data-ttu-id="3e085-118">Wenn Benutzer den Zugriff nicht zulassen,</span><span class="sxs-lookup"><span data-stu-id="3e085-118">What happens if users deny access</span></span>
<span data-ttu-id="3e085-119">Wenn Benutzer den Zugriff verweigern, können sie weiterhin die Unternehmensportal-App verwenden und ihr Gerät registrieren.</span><span class="sxs-lookup"><span data-stu-id="3e085-119">If users deny access, they can continue to use the Company Portal app and enroll their device.</span></span> <span data-ttu-id="3e085-120">Telefonnummer und IMEI-Nummer des Geräts werden jedoch nicht in der Verwaltungskonsole auf der Seite __Hardware__ angezeigt.</span><span class="sxs-lookup"><span data-stu-id="3e085-120">However, the device phone number and IMEI number will be blank on the __Hardware__ page in the admin console.</span></span> <span data-ttu-id="3e085-121">Wenn Benutzer den Zugriff verweigern und sich dann das nächste Mal bei der Unternehmensportal-App anmelden, wird in der Meldung ein Kontrollkästchen **Nicht mehr nachfragen** angezeigt, das die Benutzer aktivieren können, damit die Eingabeaufforderung nicht mehr angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="3e085-121">The second time that users sign in to the Company Portal app after denying access, the message displays a **Never ask again** check box that users can select to stop the prompt.</span></span>

<span data-ttu-id="3e085-122">Wenn Benutzer den Zugriff zunächst erlauben, später aber verweigern, wird die Meldung wieder angezeigt, wenn sie sich nach der Registrierung das nächste Mal bei der Unternehmensportal-App anmelden.</span><span class="sxs-lookup"><span data-stu-id="3e085-122">If users allow, but then later deny access, the message appears the next time users sign in to the Company Portal app after enrollment.</span></span>

<span data-ttu-id="3e085-123">Wenn Benutzer den Zugriff später erlauben möchten, müssen sie zu **Einstellungen** > **Apps** > **Unternehmensportal** > **Berechtigungen** > **Telefon** wechseln, um die Berechtigung zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="3e085-123">If users later decide to allow access, they can go to **Settings** > **Apps** > **Company Portal** > **Permissions** > **Phone**, and turn it on.</span></span>

### <a name="how-to-explain-this-to-your-users"></a><span data-ttu-id="3e085-124">So erklären Sie dies Ihren Benutzern</span><span class="sxs-lookup"><span data-stu-id="3e085-124">How to explain this to your users</span></span>
<span data-ttu-id="3e085-125">Verweisen Sie Ihre Benutzer an [Registrieren Ihres Android-Geräts bei Intune](/intune-user-help/enroll-your-device-in-intune-android), um weitere Informationen zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="3e085-125">Send your users to [Enroll your Android device in Intune](/intune-user-help/enroll-your-device-in-intune-android) for more information.</span></span>

## <a name="allow-company-portal-to-access-your-contacts"></a><span data-ttu-id="3e085-126">Zulassen, dass das Unternehmensportal auf Ihre Kontakte zugreift?</span><span class="sxs-lookup"><span data-stu-id="3e085-126">Allow Company Portal to access your contacts?</span></span>

### <a name="where-it-appears"></a><span data-ttu-id="3e085-127">Position in der Oberfläche</span><span class="sxs-lookup"><span data-stu-id="3e085-127">Where it appears</span></span>
<span data-ttu-id="3e085-128">Die Meldung **Zulassen, dass das Unternehmensportal auf Ihre Kontakte zugreift?** wird angezeigt, wenn Benutzer in der Unternehmensportal-App auf **Registrieren** tippen, während sie ihr Gerät registrieren.</span><span class="sxs-lookup"><span data-stu-id="3e085-128">The message **Allow Company Portal to access your contacts?** appears when users tap **Enroll** in the Company Portal app while they are enrolling their device.</span></span>

### <a name="what-it-means"></a><span data-ttu-id="3e085-129">Bedeutung</span><span class="sxs-lookup"><span data-stu-id="3e085-129">What it means</span></span>
<span data-ttu-id="3e085-130">Mit Akzeptieren dieser Aufforderung erlauben Benutzer Intune das Erstellen ihres Arbeitskontos und das Verwalten ihrer Azure Active Directory-Identität, die für den Benutzer auf dem betreffenden Gerät registriert ist.</span><span class="sxs-lookup"><span data-stu-id="3e085-130">By accepting this prompt, users allow Intune to create their work account and manage the Azure Active Directory identity that is registered for the user on that device.</span></span>

> [!NOTE]
> <span data-ttu-id="3e085-131">**Microsoft greift nie auf Ihre Kontakte zu!**</span><span class="sxs-lookup"><span data-stu-id="3e085-131">**Microsoft never accesses your contacts!**</span></span> <span data-ttu-id="3e085-132">Der Meldungstext wird von Google gesteuert und kann nicht geändert werden.</span><span class="sxs-lookup"><span data-stu-id="3e085-132">The message text is controlled by Google and cannot be changed.</span></span>

### <a name="what-happens-if-users-deny-access"></a><span data-ttu-id="3e085-133">Wenn Benutzer den Zugriff nicht zulassen,</span><span class="sxs-lookup"><span data-stu-id="3e085-133">What happens if users deny access</span></span>
<span data-ttu-id="3e085-134">Wenn Benutzer den Zugriff verweigern, werden ihre Geräte nicht bei Intune registriert und können nicht verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="3e085-134">If users deny access, their device will not be enrolled in Intune and cannot be managed.</span></span> <span data-ttu-id="3e085-135">Wenn Benutzer den Zugriff verweigern und sich dann das nächste Mal bei der Unternehmensportal-App anmelden, wird in der Meldung ein Kontrollkästchen **Nicht mehr nachfragen** angezeigt, das die Benutzer aktivieren können, damit die Eingabeaufforderung nicht mehr angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="3e085-135">The second time that users sign in to the Company Portal app after denying access, the message displays a **Never ask again** check box that users can select to stop the prompt.</span></span>

<span data-ttu-id="3e085-136">Wenn Benutzer den Zugriff zunächst erlauben, später aber verweigern, wird die Meldung wieder angezeigt, wenn sie sich nach der Registrierung das nächste Mal bei der Unternehmensportal-App anmelden.</span><span class="sxs-lookup"><span data-stu-id="3e085-136">If users allow, but then later deny access, the message appears the next time users sign in to the Company Portal app after enrollment.</span></span>

<span data-ttu-id="3e085-137">Wenn Benutzer den Zugriff später erlauben möchten, müssen sie zu **Einstellungen** > **Apps** > **Unternehmensportal** > **Berechtigungen** > **Telefon** wechseln, um die Berechtigung zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="3e085-137">If users later decide to allow access, they can go to **Settings** > **Apps** > **Company Portal** > **Permissions** > **Phone**, and turn it on.</span></span>

### <a name="how-to-explain-this-to-your-users"></a><span data-ttu-id="3e085-138">So erklären Sie dies Ihren Benutzern</span><span class="sxs-lookup"><span data-stu-id="3e085-138">How to explain this to your users</span></span>
<span data-ttu-id="3e085-139">Verweisen Sie Ihre Benutzer an [Registrieren Ihres Android-Geräts bei Intune](/intune-user-help/enroll-your-device-in-intune-android), um weitere Informationen zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="3e085-139">Send your users to [Enroll your Android device in Intune](/intune-user-help/enroll-your-device-in-intune-android) for more information.</span></span>

## <a name="allow-company-portal-to-access-photos-media-and-files-on-your-device"></a><span data-ttu-id="3e085-140">Unternehmensportal den Zugriff auf Fotos, Medien und Dateien auf Ihrem Gerät erlauben?</span><span class="sxs-lookup"><span data-stu-id="3e085-140">Allow Company Portal to access photos, media, and files on your device?</span></span>

### <a name="where-it-appears"></a><span data-ttu-id="3e085-141">Position in der Oberfläche</span><span class="sxs-lookup"><span data-stu-id="3e085-141">Where it appears</span></span>
<span data-ttu-id="3e085-142">Die Meldung **Unternehmensportal den Zugriff auf Fotos, Medien und Dateien auf Ihrem Gerät erlauben?** wird angezeigt, wenn Benutzer auf **Daten senden** tippen, um Datenprotokolle an den IT-Administrator zu senden.</span><span class="sxs-lookup"><span data-stu-id="3e085-142">The message **Allow Company Portal to access photos, media, and files on your device?** appears when users tap **Send Data** to send logs to their IT admin.</span></span>

### <a name="what-it-means"></a><span data-ttu-id="3e085-143">Bedeutung</span><span class="sxs-lookup"><span data-stu-id="3e085-143">What it means</span></span>
<span data-ttu-id="3e085-144">Mit Akzeptieren dieser Aufforderung erlauben Benutzer ihrem Gerät, Datenprotokolle auf die SD-Karte des Geräts zu schreiben und ermöglichen das Verschieben dieser Protokolle mithilfe eines USB-Kabels.</span><span class="sxs-lookup"><span data-stu-id="3e085-144">By accepting this prompt, users allow their device to write data logs to the device's SD card and enable those logs to be moved using a USB cable.</span></span>   

> [!NOTE]
> <span data-ttu-id="3e085-145">**Die Unternehmensportal-App greift nicht auf Fotos, Medien und Dateien der Benutzer zu!**</span><span class="sxs-lookup"><span data-stu-id="3e085-145">**The Company Portal app never accesses users' photos, media, and files!**</span></span> <span data-ttu-id="3e085-146">Der Meldungstext wird von Google gesteuert und kann nicht geändert werden.</span><span class="sxs-lookup"><span data-stu-id="3e085-146">The message text is controlled by Google and cannot be changed.</span></span>

### <a name="what-happens-if-users-deny-access"></a><span data-ttu-id="3e085-147">Wenn Benutzer den Zugriff nicht zulassen,</span><span class="sxs-lookup"><span data-stu-id="3e085-147">What happens if users deny access</span></span>
<span data-ttu-id="3e085-148">Wenn Benutzer den Zugriff verweigern, können sie weiterhin Datenprotokolle per E-Mail senden, aber die Protokolle werden nicht auf die SD-Karte des Geräts kopiert.</span><span class="sxs-lookup"><span data-stu-id="3e085-148">If users deny access, they can still send data logs via email, but the logs won't be copied to the device's SD card.</span></span>

<span data-ttu-id="3e085-149">Wenn Benutzer den Zugriff verweigern und sich dann das nächste Mal bei der Unternehmensportal-App anmelden, wird in der Meldung ein Kontrollkästchen **Nicht mehr nachfragen** angezeigt, das die Benutzer aktivieren können, damit diese Meldung nicht mehr angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="3e085-149">The second time that users sign in to the Company Portal app after denying access, the message displays a **Never ask again** check box that users can select so that the message never shows again.</span></span> <span data-ttu-id="3e085-150">Wenn Benutzer den Zugriff zunächst erlauben, später aber verweigern, wird die Meldung wieder angezeigt, wenn sie das nächste Mal Protokolle senden.</span><span class="sxs-lookup"><span data-stu-id="3e085-150">If users allow, but then later deny access, the message appears the next time users try to send logs.</span></span> <span data-ttu-id="3e085-151">Wenn Benutzer den Zugriff später erlauben möchten, müssen sie zu **Einstellungen** > **Apps** > **Unternehmensportal** > **Berechtigungen** > **Speicherung** wechseln, um die Berechtigung zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="3e085-151">If users later decide to allow access, they can go to **Settings** > **Apps** > **Company Portal** > **Permissions** > **Storage**, and then turn on the permission.</span></span>


### <a name="how-to-explain-this-to-your-users"></a><span data-ttu-id="3e085-152">So erklären Sie dies Ihren Benutzern</span><span class="sxs-lookup"><span data-stu-id="3e085-152">How to explain this to your users</span></span>
<span data-ttu-id="3e085-153">Verweisen Sie Ihre Benutzer an [Senden von Protokollen an Ihren IT-Administrator per E-Mail](/intune-user-help/send-logs-to-your-it-admin-by-email-android).</span><span class="sxs-lookup"><span data-stu-id="3e085-153">Send your users to [Send logs to your IT admin by email](/intune-user-help/send-logs-to-your-it-admin-by-email-android).</span></span> <span data-ttu-id="3e085-154">Sie können sie auch an [Protokolle an Ihren IT-Administrator über ein Kabel senden](/intune-user-help/send-logs-to-your-it-admin-by-cable-android) verweisen, wenn Sie möchten, dass sie die beiden Methoden vergleichen.</span><span class="sxs-lookup"><span data-stu-id="3e085-154">You can also send them to [Send logs to your IT admin by cable](/intune-user-help/send-logs-to-your-it-admin-by-cable-android) if you want to let them compare the two methods.</span></span>

## <a name="your-company-support-needs-to-give-you-access-to-company-resources"></a><span data-ttu-id="3e085-155">Der Support Ihres Unternehmens muss Ihnen Zugriff auf Unternehmensressourcen gewähren.</span><span class="sxs-lookup"><span data-stu-id="3e085-155">Your company support needs to give you access to company resources</span></span>

### <a name="where-it-appears"></a><span data-ttu-id="3e085-156">Position in der Oberfläche</span><span class="sxs-lookup"><span data-stu-id="3e085-156">Where it appears</span></span>
<span data-ttu-id="3e085-157">Wenn Sie die Unternehmensportal-App nicht zur Liste **Zulässige Apps** oder **Ausgenommene Apps** hinzugefügt haben, und ein Benutzer versucht, sich anzumelden, schlägt die Anmeldung fehl.</span><span class="sxs-lookup"><span data-stu-id="3e085-157">If you have not added the Company Portal app to the **Allowed apps** or **Exempt apps** list, and a user attempts to sign in, the sign in will fail.</span></span> <span data-ttu-id="3e085-158">Die folgende Meldung wird angezeigt:</span><span class="sxs-lookup"><span data-stu-id="3e085-158">The following message displays:</span></span>

> <span data-ttu-id="3e085-159">**Der Support Ihres Unternehmens muss Ihnen Zugriff auf Unternehmensressourcen gewähren**</span><span class="sxs-lookup"><span data-stu-id="3e085-159">**Your company support needs to give you access to company resources**</span></span>  
> <span data-ttu-id="3e085-160">Ihr Unternehmen verwendet Windows Information Protection-Richtlinien, um Ihr Gerät zu schützen.</span><span class="sxs-lookup"><span data-stu-id="3e085-160">Your company is using Windows Information Protection policies to protect your device.</span></span> <span data-ttu-id="3e085-161">Der Support Ihres Unternehmens muss sicherstellen, dass die Unternehmensportal-App auf diese zugreifen kann.</span><span class="sxs-lookup"><span data-stu-id="3e085-161">Your company support will need to make sure they allow the Company Portal to access those.</span></span>

### <a name="what-it-means"></a><span data-ttu-id="3e085-162">Bedeutung</span><span class="sxs-lookup"><span data-stu-id="3e085-162">What it means</span></span>

<span data-ttu-id="3e085-163">Fügen Sie dem Unternehmensportal die Liste der **zulässigen Apps** und **ausgenommenen Apps** hinzu, die in der Windows Information Protection-App-Schutzrichtlinie aufgeführt sind.</span><span class="sxs-lookup"><span data-stu-id="3e085-163">Add the Company Portal the **Allowed apps** or **Exempt apps** list in the Windows Information Protection (WIP) app protection policy.</span></span> <span data-ttu-id="3e085-164">Weitere Informationen finden Sie unter [Erstellen und Bereitstellen von WIP-App-Schutzrichtlinien (Windows Information Protection) in Intune](/intune-classic/deploy-use/create-windows-information-protection-policy-with-intune).</span><span class="sxs-lookup"><span data-stu-id="3e085-164">For more information, see [Create and deploy Windows Information Protection (WIP) app protection policy with Intune](/intune-classic/deploy-use/create-windows-information-protection-policy-with-intune).</span></span>

### <a name="see-also"></a><span data-ttu-id="3e085-165">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="3e085-165">See also</span></span>
[<span data-ttu-id="3e085-166">Informieren der Endbenutzer über den Einsatz von Intune</span><span class="sxs-lookup"><span data-stu-id="3e085-166">What to tell your end users about using Intune</span></span>](end-user-educate.md)
