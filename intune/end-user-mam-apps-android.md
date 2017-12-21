---
title: Android-Apps mit App-Schutzrichtlinien
description: In diesem Thema erfahren Sie, was Sie erwartet, wenn Ihre App von App-Schutzrichtlinien verwaltet wird.
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 03/06/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 53c8e2ad-f627-425b-9adc-39ca69dbb460
ms.reviewer: andcerat
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 6239e34a06069d4834603a48dba0e10f8c00774d
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2017
---
# <a name="what-to-expect-when-your-android-app-is-managed-by-app-protection-policies"></a><span data-ttu-id="154a7-103">Was Sie erwartet, wenn Ihre Android-App von App-Schutzrichtlinien verwaltet wird</span><span class="sxs-lookup"><span data-stu-id="154a7-103">What to expect when your Android app is managed by app protection policies</span></span>

[!INCLUDE[both-portals](./includes/note-for-both-portals.md)]

<span data-ttu-id="154a7-104">Dieses Thema beschreibt die Benutzererfahrung für Apps mit App-Schutzrichtlinien.</span><span class="sxs-lookup"><span data-stu-id="154a7-104">This topic describes the user experience for apps with app protection policies.</span></span> <span data-ttu-id="154a7-105">App-Schutzrichtlinien gelten nur, wenn Apps in einem geschäftlichen Kontext verwendet werden, z.B. wenn der Benutzer ein Geschäftskonto für den Zugriff auf Apps verwendet oder auf Dateien zugreift, die an einem OneDrive for Business-Speicherort im Unternehmen gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="154a7-105">App protection policies are applied only when apps are used in a work context: for example, when the user is accessing apps with a work account or accessing files that are stored in a company OneDrive business location.</span></span>
##  <a name="access-apps"></a><span data-ttu-id="154a7-106">Zugriff auf Apps</span><span class="sxs-lookup"><span data-stu-id="154a7-106">Access apps</span></span>

<span data-ttu-id="154a7-107">Die Unternehmensportal-App ist auf Android-Geräten für alle Apps erforderlich, die App-Schutzrichtlinien zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="154a7-107">The Company Portal app is required for all apps that are associated with app protection policies on Android devices.</span></span>

<span data-ttu-id="154a7-108">Bei Geräten, die nicht bei Intune registriert sind, muss die Unternehmensportal-App auf dem Gerät installiert sein.</span><span class="sxs-lookup"><span data-stu-id="154a7-108">For devices that are not enrolled in Intune, the Company Portal app must be installed on the device.</span></span> <span data-ttu-id="154a7-109">Jedoch muss der Benutzer die Unternehmensportal-App nicht starten bzw. sich darin anmelden, bevor er Apps verwenden kann, die von App-Schutzrichtlinien verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="154a7-109">However, the user does not have to launch  or sign into the Company Portal app before they can use apps that are managed by app protection policies.</span></span>

<span data-ttu-id="154a7-110">Die Unternehmensportal-App ist in Intune eine Möglichkeit der Freigabe von Daten an einem sicheren Ort.</span><span class="sxs-lookup"><span data-stu-id="154a7-110">The Company Portal app is a way for Intune to share data in a secure location.</span></span> <span data-ttu-id="154a7-111">Daher ist die Unternehmensportal-App eine Voraussetzung für alle Apps, denen App-Schutzrichtlinien zugeordnet sind, auch wenn das Gerät nicht in Intune registriert ist.</span><span class="sxs-lookup"><span data-stu-id="154a7-111">Therefore, the Company Portal app is a requirement for all apps that are associated with app protection policies, even if the device is not enrolled in Intune.</span></span>


##  <a name="use-apps-with-multi-identity-support"></a><span data-ttu-id="154a7-112">Verwenden von Apps mit Unterstützung von mehreren Identitäten</span><span class="sxs-lookup"><span data-stu-id="154a7-112">Use apps with multi-identity support</span></span>

<span data-ttu-id="154a7-113">App-Schutzrichtlinien werden nur im geschäftlichen Kontext angewendet.</span><span class="sxs-lookup"><span data-stu-id="154a7-113">App protection polices are only applied in the work context.</span></span> <span data-ttu-id="154a7-114">Eine App kann sich daher unterschiedlich verhalten, je nachdem, ob sie im geschäftlichen oder privaten Kontext verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="154a7-114">Therefore, the app might behave differently depending on whether the context is work or personal.</span></span>

<span data-ttu-id="154a7-115">Beispielsweise erhalten Benutzer eine PIN-Eingabeaufforderung, wenn Sie auf Geschäftsdaten zugreifen.</span><span class="sxs-lookup"><span data-stu-id="154a7-115">For example, the user gets a PIN prompt when accessing work data.</span></span> <span data-ttu-id="154a7-116">Bei der **Outlook-App** wird der Benutzer beim Starten der App zur Eingabe einer PIN aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="154a7-116">For the **Outlook app**, the user is prompted for a PIN when they launch the app.</span></span> <span data-ttu-id="154a7-117">Bei der **OneDrive-App** wird der Benutzer zur Eingabe der PIN aufgefordert, wenn er das Geschäftskonto eingibt.</span><span class="sxs-lookup"><span data-stu-id="154a7-117">For the **OneDrive app**, the user is prompted for the pin when they type in the work account.</span></span> <span data-ttu-id="154a7-118">Bei Microsoft **Word**, **PowerPoint** und **Excel** wird der Benutzer zur Eingabe der PIN aufgefordert, wenn er auf Dokumente zugreift, die am OneDrive for Business-Speicherort des Unternehmens gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="154a7-118">For Microsoft **Word**, **PowerPoint**, and **Excel**, the user is prompted for the pin when they access documents that are stored in the company OneDrive for Business location.</span></span>

##  <a name="manage-user-accounts-on-the-device"></a><span data-ttu-id="154a7-119">Verwalten von Benutzerkonten auf dem Gerät</span><span class="sxs-lookup"><span data-stu-id="154a7-119">Manage user accounts on the device</span></span>

<span data-ttu-id="154a7-120">Intune unterstützt die Bereitstellung von App-Schutzrichtlinien nur auf je einem Benutzerkonto pro Gerät.</span><span class="sxs-lookup"><span data-stu-id="154a7-120">Intune  supports the deployment of app protection policies to one user account per device only.</span></span>

* <span data-ttu-id="154a7-121">Abhängig von der verwendeten App, ist der zweite Benutzer auf dem Gerät möglicherweise blockiert.</span><span class="sxs-lookup"><span data-stu-id="154a7-121">Depending on the app that you're using, the second user might be blocked on the device.</span></span> <span data-ttu-id="154a7-122">Unter allen Umständen wirken sich die App-Schutzrichtlinien nur auf den ersten Benutzer aus.</span><span class="sxs-lookup"><span data-stu-id="154a7-122">However, in all cases, only the first user who gets the app protection policies is affected by the policy.</span></span>

  * <span data-ttu-id="154a7-123">**Microsoft Word**, **Excel** und **PowerPoint** blockieren ein zweites Benutzerkonto nicht, die App-Schutzrichtlinien wirken sich auf das zweite Benutzerkonto jedoch nicht aus.</span><span class="sxs-lookup"><span data-stu-id="154a7-123">**Microsoft Word**, **Excel**, and **PowerPoint** don't block a second user account, but the second user account is not affected by the app protection policies.</span></span>

  * <span data-ttu-id="154a7-124">Für **OneDrive**- und **Outlook-Apps** können Sie nur ein Geschäftskonto verwenden.</span><span class="sxs-lookup"><span data-stu-id="154a7-124">For **OneDrive** and **Outlook apps**, you can only use one work account.</span></span>  <span data-ttu-id="154a7-125">Sie können für diese Apps nicht mehrere Geschäftskonten hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="154a7-125">You can't add multiple work accounts for these apps.</span></span>  <span data-ttu-id="154a7-126">Sie können jedoch einen Benutzer entfernen und auf dem Gerät einen weiteren Benutzer hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="154a7-126">You can however, remove a user and add a different user on the device.</span></span>


* <span data-ttu-id="154a7-127">Wenn für ein Gerät vor der Bereitstellung der App-Schutzrichtlinien mehrere Benutzerkonten vorhanden sind, wird das Konto, für das die App-Schutzrichtlinien zuerst bereitgestellt werden, durch die Intune-App-Schutzrichtlinien verwaltet.</span><span class="sxs-lookup"><span data-stu-id="154a7-127">If a device has existing multiple user accounts before the app protection policies are deployed, the account that the app protection policies are deployed to first is managed by Intune app protection policies.</span></span>


<span data-ttu-id="154a7-128">Lesen Sie das folgende Beispielszenario, um genauer zu verstehen, wie mehrere Benutzerkonten behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="154a7-128">Read the following example scenario to get a deeper understanding of how multiple user accounts are treated.</span></span>

<span data-ttu-id="154a7-129">Benutzer A arbeitet für zwei Unternehmen – **Unternehmen X** und **Unternehmen Y**. Benutzer A verfügt für jedes Unternehmen über ein geschäftliches Konto, und beide verwenden Intune zum Bereitstellen von App-Schutzrichtlinien.</span><span class="sxs-lookup"><span data-stu-id="154a7-129">User A works for two companies—**Company X** and **Company Y**. User A has a work account for each company, and both use Intune to deploy app protection policies.</span></span> <span data-ttu-id="154a7-130">**Unternehmen X** stellt App-Schutzrichtlinien **vor** **Unternehmen Y** bereit. Das dem **Unternehmen X** zugeordnete Konto erhält die App-Schutzrichtlinie, nicht jedoch das dem Unternehmen Y zugeordnete Konto. Wenn das dem Unternehmen Y zugeordnete Konto durch die App-Schutzrichtlinien verwaltet werden soll, müssen Sie das dem Unternehmen X zugeordnete Benutzerkonto entfernen.</span><span class="sxs-lookup"><span data-stu-id="154a7-130">**Company X** deploys app protection policies **before** **Company Y**. The account that's associated with **Company X** gets the app protection policy, but not the account that's associated with Company Y. If you want the user account that's associated with Company Y to be managed by the app protection policies, you must remove the user account that's associated with Company X.</span></span>
### <a name="add-a-second-account"></a><span data-ttu-id="154a7-131">Hinzufügen eines zweiten Kontos</span><span class="sxs-lookup"><span data-stu-id="154a7-131">Add a second account</span></span>
####  <a name="android"></a><span data-ttu-id="154a7-132">Android</span><span class="sxs-lookup"><span data-stu-id="154a7-132">Android</span></span>
<span data-ttu-id="154a7-133">Wenn Sie ein Android-Gerät verwenden, wird möglicherweise eine Sperrnachricht mit Anweisungen angezeigt, wie Sie das vorhandene Konto entfernen und ein neues Konto hinzufügen können.</span><span class="sxs-lookup"><span data-stu-id="154a7-133">If you are using an Android device, you might see a blocking message with instructions to remove the existing account and add a new one.</span></span>  <span data-ttu-id="154a7-134">Um das vorhandene Konto zu entfernen, wechseln Sie zu **Einstellungen &gt; Allgemein &gt; Anwendungs-Manager &gt; Unternehmensportal**.</span><span class="sxs-lookup"><span data-stu-id="154a7-134">To remove the existing account, go to **Settings  &gt;General &gt; Application Manager &gt;Company Portal.**</span></span> <span data-ttu-id="154a7-135">Wählen Sie dann **Daten löschen** aus.</span><span class="sxs-lookup"><span data-stu-id="154a7-135">Then choose **Clear Data**.</span></span>

![Screenshot der Fehlermeldung und Anweisungen zum Entfernen des Kontos](./media/Android_SwitchUser.png)

##  <a name="view-media-files-with-the-azure-information-protection-app"></a><span data-ttu-id="154a7-137">Anzeigen von Mediendateien mit der Azure Information Protection-App</span><span class="sxs-lookup"><span data-stu-id="154a7-137">View media files with the Azure Information Protection app</span></span>
<span data-ttu-id="154a7-138">Verwenden Sie zum Anzeigen unternehmenseigener AV-, PDF- und Bilddateien auf Android-Geräten die [Azure Information Protection-App](https://play.google.com/store/apps/details?id=com.microsoft.ipviewer) (ehemals Rights Management-Freigabe-App).</span><span class="sxs-lookup"><span data-stu-id="154a7-138">To view company AV, PDF, and image files on Android devices, use the [Azure Information Protection app](https://play.google.com/store/apps/details?id=com.microsoft.ipviewer) (previously known as the Rights Management sharing app).</span></span>

<span data-ttu-id="154a7-139">Laden Sie diese App aus dem Google Play Store herunter.</span><span class="sxs-lookup"><span data-stu-id="154a7-139">Download this app from the Google Play store.</span></span>  

<span data-ttu-id="154a7-140">Die folgenden Dateitypen werden unterstützt:</span><span class="sxs-lookup"><span data-stu-id="154a7-140">The following file types are supported:</span></span>

* <span data-ttu-id="154a7-141">**Audio:** AAC LC, HE-AACv1 (AAC+), HE-AACv2 (erweitertes AAC+), AAC ELD (erweitertes AAC mit geringer Verzögerung), AMR-NB, AMR-WB, FLAC, MP3, MIDI, Ogg Vorbis, PCM/WAVE</span><span class="sxs-lookup"><span data-stu-id="154a7-141">**Audio:** AAC LC, HE-AACv1 (AAC+), HE-AACv2 (enhanced AAC+), AAC ELD (enhanced low delay AAC), AMR-NB, AMR-WB, FLAC, MP3, MIDI, Ogg Vorbis, PCM/WAVE</span></span>
* <span data-ttu-id="154a7-142">**Video:** H.263, H.264 AVC, MPEG-4 SP, VP8</span><span class="sxs-lookup"><span data-stu-id="154a7-142">**Video:** H.263, H.264 AVC, MPEG-4 SP, VP8</span></span>
* <span data-ttu-id="154a7-143">**Bild:** JPG, PJPG, PNG, PPNG, BMP, PBMP, GIF, PGIF, JPEG, PJPEG</span><span class="sxs-lookup"><span data-stu-id="154a7-143">**Image:** .jpg, .pjpg, .png, .ppng, .bmp, .pbmp, .gif, .pgif, .jpeg, .pjpeg</span></span>
* <span data-ttu-id="154a7-144">**Dokumente:** PDF, PPDF</span><span class="sxs-lookup"><span data-stu-id="154a7-144">**Documents:** PDF, PPDF</span></span>


|<span data-ttu-id="154a7-145">**pfile**</span><span class="sxs-lookup"><span data-stu-id="154a7-145">**pfile**</span></span>|<span data-ttu-id="154a7-146">**text**</span><span class="sxs-lookup"><span data-stu-id="154a7-146">**text**</span></span>|
|----|----|
|<span data-ttu-id="154a7-147">Pfile ist ein generisches „Wrapper“-Format für geschützte Dateien, das den verschlüsselten Inhalt sowie die Azure Information Protection-Lizenzen kapselt.</span><span class="sxs-lookup"><span data-stu-id="154a7-147">Pfile is a generic “wrapper” format for protected files that encapsulates the encrypted content and the Azure Information Protection licenses.</span></span> <span data-ttu-id="154a7-148">Es kann zum Schützen beliebiger Dateitypen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="154a7-148">It can be used to protect any file type.</span></span>|<span data-ttu-id="154a7-149">Textdateien, einschließlich XML, CSV, etc., können zum Anzeigen in der App geöffnet werden, selbst wenn sie geschützt sind.</span><span class="sxs-lookup"><span data-stu-id="154a7-149">Text files, including XML, CSV, and so on, can be opened for viewing in the app even when they are protected.</span></span> <span data-ttu-id="154a7-150">Dateitypen: TXT, PTXT, CSV, PCSV, LOG, PLOG, XML, PXML.</span><span class="sxs-lookup"><span data-stu-id="154a7-150">File types: .txt, .ptxt, .csv, .pcsv, .log, .plog, .xml, .pxml.</span></span>|

## <a name="next-steps"></a><span data-ttu-id="154a7-151">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="154a7-151">Next steps</span></span>
[<span data-ttu-id="154a7-152">Was Sie erwartet, wenn Ihre iOS-App von App-Schutzrichtlinien verwaltet wird</span><span class="sxs-lookup"><span data-stu-id="154a7-152">What to expect when your iOS app is managed by app protection policies</span></span>](end-user-mam-apps-ios.md)
