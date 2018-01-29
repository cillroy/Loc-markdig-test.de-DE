---
title: Android-Apps mit App-Schutzrichtlinien
titlesuffix: Azure portal
description: In diesem Thema erfahren Sie, was Sie erwartet, wenn Ihre Android-App von App-Schutzrichtlinien verwaltet wird."
keywords: 
author: erikre
ms.author: erikre
manager: angrobe
ms.date: 12/07/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a6816285-8e43-4dc8-bca0-e80ec5ef01e6
ms.reviewer: andcerat
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: aad6949e8e433236c0a62a54bfdb69ef295ef253
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2018
---
# <a name="what-to-expect-when-your-android-app-is-managed-by-app-protection-policies"></a><span data-ttu-id="58a37-103">Was Sie erwartet, wenn Ihre Android-App von App-Schutzrichtlinien verwaltet wird</span><span class="sxs-lookup"><span data-stu-id="58a37-103">What to expect when your Android app is managed by app protection policies</span></span> 

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="58a37-104">Dieses Thema beschreibt die Benutzererfahrung für Apps mit App-Schutzrichtlinien.</span><span class="sxs-lookup"><span data-stu-id="58a37-104">This topic describes the user experience for apps with app protection policies.</span></span> <span data-ttu-id="58a37-105">App-Schutzrichtlinien gelten nur, wenn Apps im geschäftlichen Kontext verwendet werden, z.B. wenn Sie Ihr Geschäftskonto für den Zugriff auf Apps verwenden oder auf Dateien zugreifen, die am OneDrive for Business-Speicherort Ihres Unternehmens gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="58a37-105">App protection polices are applied only when apps are used in the work context: like accessing apps using your work account, or accessing files stored in your company OneDrive business location.</span></span>
##  <a name="accessing-apps"></a><span data-ttu-id="58a37-106">Zugreifen auf Apps</span><span class="sxs-lookup"><span data-stu-id="58a37-106">Accessing apps</span></span>

<span data-ttu-id="58a37-107">Die Unternehmensportal-App ist auf Android-Geräten für alle Apps erforderlich, die App-Schutzrichtlinien zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="58a37-107">The Company Portal app is required for all apps associated with app protection policies on Android devices.</span></span>

<span data-ttu-id="58a37-108">Bei Geräten, die nicht bei Intune registriert sind, muss die Unternehmensportal-App auf dem Gerät installiert sein.</span><span class="sxs-lookup"><span data-stu-id="58a37-108">For devices not enrolled in Intune, the Company Portal app must be installed on the device.</span></span> <span data-ttu-id="58a37-109">Benutzer müssen jedoch die Unternehmensportal-App nicht starten bzw. sich darin anmelden, bevor sie Apps verwenden können, die von App-Schutzrichtlinien verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="58a37-109">However, user does not have to launch  or sign into the Company Portal app before they can use apps managed by app protection policies.</span></span>
<span data-ttu-id="58a37-110">Die Unternehmensportal-App stellt für Intune eine Methode zum Freigeben von Daten an einen sicheren Speicherort dar. Daher wird diese App angefordert, auch wenn das Gerät nicht bei Intune registriert ist.</span><span class="sxs-lookup"><span data-stu-id="58a37-110">The Company Portal app is a way for Intune to share data in a secure location, hence this is a requirement even if the device is not enrolled in Intune.</span></span>


##  <a name="using-apps-with-multi-identity-support"></a><span data-ttu-id="58a37-111">Verwenden von Apps mit Multi-Identity Support (Unterstützung für mehrere Identitäten)</span><span class="sxs-lookup"><span data-stu-id="58a37-111">Using apps with multi-identity support</span></span>

<span data-ttu-id="58a37-112">App-Schutzrichtlinien gelten nur, wenn die App im geschäftlichen Kontext verwendet wird. Daher kann das App-Verhalten abhängig vom Kontext (geschäftlich oder privat) abweichen.</span><span class="sxs-lookup"><span data-stu-id="58a37-112">App protection polices are only applied in the work context when using the app, so you may see different app behaviors depending on the context: work or personal.</span></span>

<span data-ttu-id="58a37-113">Bei Apps, die mehrere Identitäten unterstützen, wendet Intune die App-Schutzrichtlinien nur an, wenn der Endbenutzer die App im geschäftlichen Kontext verwendet.</span><span class="sxs-lookup"><span data-stu-id="58a37-113">For apps that support multi-identity, Intune only applies the app protection policies when the end-user is using the app in the work context.</span></span>  <span data-ttu-id="58a37-114">Beispielsweise erhalten Endbenutzer eine PIN-Eingabeaufforderung, wenn Sie auf Geschäftsdaten zugreifen.</span><span class="sxs-lookup"><span data-stu-id="58a37-114">For example, the end-user will get a PIN prompt when accessing work data.</span></span>  <span data-ttu-id="58a37-115">Bei der <strong>Outlook-App</strong> wird der Endbenutzer beim Starten der App zur Eingabe einer PIN aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="58a37-115">For the <strong>Outlook app</strong>, the end-user is prompted for a PIN on launching the app.</span></span> <span data-ttu-id="58a37-116">Bei der <strong>OneDrive-App</strong> erfolgt diese Aufforderung, wenn der Endbenutzer das Geschäftskonto eingibt.</span><span class="sxs-lookup"><span data-stu-id="58a37-116">For the <strong>OneDrive app</strong>, this happens when the end-user types in the work account.</span></span>  <span data-ttu-id="58a37-117">Für Microsoft <strong>Word</strong>, <strong>PowerPoint \* und \*\* Excel</strong>, dies geschieht, wenn der Endbenutzer im Unternehmen OneDrive for Business-Speicherort gespeicherte Dokumente zugreift.</span><span class="sxs-lookup"><span data-stu-id="58a37-117">For Microsoft <strong>Word</strong>, <strong>PowerPoint\*, and \*\*Excel</strong>, this happens when the end-user accesses documents stored in the company OneDrive for Business location.</span></span>
##  <a name="managing-user-accounts-on-the-device"></a><span data-ttu-id="58a37-118">Verwalten von Benutzerkonten auf dem Gerät</span><span class="sxs-lookup"><span data-stu-id="58a37-118">Managing user accounts on the device</span></span>

<span data-ttu-id="58a37-119">Intune unterstützt nur die Bereitstellung von App-Schutzrichtlinien auf je einem Benutzerkonto pro Gerät.</span><span class="sxs-lookup"><span data-stu-id="58a37-119">Intune only supports deploying app protection policies to only one user account per device.</span></span>

* <span data-ttu-id="58a37-120">Abhängig von der verwendeten App, ist der zweite Benutzer auf dem Gerät möglicherweise blockiert oder auch nicht.</span><span class="sxs-lookup"><span data-stu-id="58a37-120">Depending on the app that you are using, the second user may or may not be blocked on the device.</span></span> <span data-ttu-id="58a37-121">Unter allen Umständen wirken sich die App-Schutzrichtlinien nur auf den ersten Benutzer aus.</span><span class="sxs-lookup"><span data-stu-id="58a37-121">However, in all cases, only the first user who gets the app protection policies is affected by the policy.</span></span>

  * <span data-ttu-id="58a37-122">**Microsoft Word**, **Excel** und **PowerPoint** blockieren ein zweites Benutzerkonto nicht, die App-Schutzrichtlinien wirken sich auf das zweite Benutzerkonto jedoch nicht aus.</span><span class="sxs-lookup"><span data-stu-id="58a37-122">**Microsoft Word**, **Excel**, and **PowerPoint** don't block a second user account, but the second user account is not affected by the app protection policies.</span></span>

  * <span data-ttu-id="58a37-123">Für **OneDrive- und Outlook-Apps** kann nur ein geschäftliches Konto verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="58a37-123">For **OneDrive and Outlook apps**, you can only use one work account.</span></span>  <span data-ttu-id="58a37-124">Das Hinzufügen weiterer Geschäftskonten wird von diesen Apps blockiert.</span><span class="sxs-lookup"><span data-stu-id="58a37-124">Adding multiple work accounts are blocked on these apps.</span></span>  <span data-ttu-id="58a37-125">Sie können jedoch einen Benutzer entfernen und auf dem Gerät einen weiteren Benutzer hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="58a37-125">You can however, remove a user and add a different user on the device.</span></span>


* <span data-ttu-id="58a37-126">Wenn für ein Gerät vor der Bereitstellung der App-Schutzrichtlinien mehrere Benutzerkonten vorhanden sind, wird das Konto, für das die App-Schutzrichtlinien zuerst bereitgestellt werden, durch die Intune-App-Schutzrichtlinien verwaltet.</span><span class="sxs-lookup"><span data-stu-id="58a37-126">If a device has existing multiple user accounts before the app protection policies are deployed, the account that the app protection policies is deployed to first is managed by Intune app protection policies.</span></span>


<span data-ttu-id="58a37-127">Lesen Sie das Beispielszenario unten, um genauer zu verstehen, wie mehrere Benutzerkonten behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="58a37-127">Read the example scenario below to get a deeper understanding of how multiple user accounts are treated.</span></span>

<span data-ttu-id="58a37-128">Benutzer A arbeitet für zwei Unternehmen – **Unternehmen X** und **Unternehmen Y**. Benutzer A verfügt für jedes Unternehmen über ein geschäftliches Konto, und beide verwenden Intune zum Bereitstellen von App-Schutzrichtlinien.</span><span class="sxs-lookup"><span data-stu-id="58a37-128">User A works for two companies - **Company X**, and **Company Y**. User A has a work account for each company, and both use Intune to deploy app protection policies.</span></span> <span data-ttu-id="58a37-129">**Unternehmen X** stellt App-Schutzrichtlinien **vor** **Unternehmen Y** bereit. Das **Unternehmen X** zugeordnete Konto erhält die App-Schutzrichtlinie, nicht jedoch das dem Unternehmen Y zugeordnete Konto. Wenn das Unternehmen Y zugeordnete Konto durch die App-Schutzrichtlinien verwaltet werden soll, müssen Sie das Unternehmen X zugeordnete Benutzerkonto entfernen.</span><span class="sxs-lookup"><span data-stu-id="58a37-129">**Company X** deploys app protection policies **before** **Company Y**. The account associated with **Company X** will get the app protection policy, but not the account associated with Company Y. If you want the user account associated with Company Y to be managed by the app protection policies, you must remove the user account associated with Company X.</span></span>
### <a name="adding-a-second-account"></a><span data-ttu-id="58a37-130">Hinzufügen eines zweiten Kontos</span><span class="sxs-lookup"><span data-stu-id="58a37-130">Adding a second account</span></span>
####  <a name="android"></a><span data-ttu-id="58a37-131">Android</span><span class="sxs-lookup"><span data-stu-id="58a37-131">Android</span></span>
<span data-ttu-id="58a37-132">Wenn Sie ein Android-Gerät verwenden, wird möglicherweise eine Sperrnachricht mit Anweisungen angezeigt, wie Sie das vorhandene Konto entfernen und ein neues Konto hinzufügen können.</span><span class="sxs-lookup"><span data-stu-id="58a37-132">If you are using an Android device, you may see a blocking message with instructions to remove the existing account and add a new one.</span></span>  <span data-ttu-id="58a37-133">Um das vorhandene Konto zu entfernen, wechseln Sie zu **Einstellungen &gt; Allgemein &gt; Anwendungs-Manager &gt; Unternehmensportal**, und wählen Sie „Daten löschen“ aus.</span><span class="sxs-lookup"><span data-stu-id="58a37-133">To remove the existing account, go to **Settings  &gt;General &gt; Application Manager &gt;Company Portal and select "Clear Data"**.</span></span>

![Screenshot der Fehlermeldung und Anweisungen zum Entfernen des Kontos](./media/android-switch-user.png)

##  <a name="viewing-media-files-with-the-azure-information-protection-app-previously-known-as-rights-management-sharing-app"></a><span data-ttu-id="58a37-135">Anzeigen von Mediendateien mit der Azure Information Protection-App (zuvor bekannt als Rights Management-Freigabeanwendung)</span><span class="sxs-lookup"><span data-stu-id="58a37-135">Viewing media files with the Azure Information Protection app (previously known as Rights Management sharing app)</span></span>
<span data-ttu-id="58a37-136">Verwenden Sie zum Anzeigen unternehmenseigener AV-, PDF- und Bilddateien auf Android-Geräten die [Azure Information Protection-App](https://play.google.com/store/apps/details?id=com.microsoft.ipviewer).</span><span class="sxs-lookup"><span data-stu-id="58a37-136">To view company AV, PDF, and image files on Android devices, use the [Azure Information Protection app](https://play.google.com/store/apps/details?id=com.microsoft.ipviewer).</span></span>

<span data-ttu-id="58a37-137">Laden Sie diese App aus dem Google Play herunter.</span><span class="sxs-lookup"><span data-stu-id="58a37-137">Download this app from the  Google Play store.</span></span>  

<span data-ttu-id="58a37-138">Die folgenden Dateitypen werden unterstützt:</span><span class="sxs-lookup"><span data-stu-id="58a37-138">The following filetypes are supported:</span></span>

* <span data-ttu-id="58a37-139">**Audio:** AAC LC, HE-AACv1 (AAC+), HE-AACv2 (erweitertes AAC+), AAC ELD (enhanced low delay ACC, erweitertes AAC mit geringer Verzögerung), AMR-NB, AMR-WB, FLAC, MP3, MIDI, Ogg Vorbis, PCM/WAVE.</span><span class="sxs-lookup"><span data-stu-id="58a37-139">**Audio:** AAC LC, HE-AACv1 (AAC+), HE-AACv2 (enhanced AAC+), AAC ELD (enhanced low delay AAC), AMR-NB, AMR-WB, FLAC, MP3, MIDI, Ogg Vorbis, PCM/WAVE.</span></span>
* <span data-ttu-id="58a37-140">**Video:** H.263, H.264 AVC, MPEG-4 SP, VP8.</span><span class="sxs-lookup"><span data-stu-id="58a37-140">**Video:** H.263, H.264 AVC, MPEG-4 SP, VP8.</span></span>
* <span data-ttu-id="58a37-141">**Bild:** JPG, PJPG, PNG, PPNG, BMP, PBMP, GIF, PGIF, JPEG, PJPEG.</span><span class="sxs-lookup"><span data-stu-id="58a37-141">**Image:** jpg, pjpg, png, ppng, bmp, pbmp, gif, pgif, jpeg, pjpeg.</span></span>
* <span data-ttu-id="58a37-142">**Dokumente:** PDF, PPDF</span><span class="sxs-lookup"><span data-stu-id="58a37-142">**Documents:** PDF, PPDF</span></span>

------------

|                                                                                 <span data-ttu-id="58a37-143"><strong>pfile</strong></span><span class="sxs-lookup"><span data-stu-id="58a37-143"><strong>pfile</strong></span></span>                                                                                  |                                                                      <span data-ttu-id="58a37-144"><strong>text</strong></span><span class="sxs-lookup"><span data-stu-id="58a37-144"><strong>text</strong></span></span>                                                                      |
|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="58a37-145">Pfile ist ein generisches „Wrapper“-Format für geschützte Dateien, das den verschlüsselten Inhalt sowie die Azure Information Protection-Lizenzen kapselt und zum Schützen beliebiger Dateitypen verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="58a37-145">Pfile is a generic “wrapper” format for protected files that encapsulates the encrypted content and the Azure Information Protection licenses and can be used to protect any file type.</span></span> | <span data-ttu-id="58a37-146">Textdateien, einschließlich XML, CSV, etc. können zum Anzeigen in der App geöffnet werden, selbst wenn sie geschützt sind.</span><span class="sxs-lookup"><span data-stu-id="58a37-146">Text files, including XML, CSV, etc. can be opened for viewing in the app even when they are protected.</span></span> <span data-ttu-id="58a37-147">Dateitypen: TXT, PTXT, CSV, PCSV, LOG, PLOG, XML, PXML.</span><span class="sxs-lookup"><span data-stu-id="58a37-147">File types: txt, ptxt, csv, pcsv, log, plog, xml, pxml.</span></span> |

---------------
## <a name="next-steps"></a><span data-ttu-id="58a37-148">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="58a37-148">Next steps</span></span>
[<span data-ttu-id="58a37-149">Was Sie erwartet, wenn Ihre iOS-App von App-Schutzrichtlinien verwaltet wird</span><span class="sxs-lookup"><span data-stu-id="58a37-149">What to expect when your iOS app is managed by app protection policies</span></span>](app-protection-enabled-apps-ios.md)

### <a name="see-also"></a><span data-ttu-id="58a37-150">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="58a37-150">See also</span></span>
[<span data-ttu-id="58a37-151">Erstellen und Bereitstellen von App-Schutzrichtlinien mit Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="58a37-151">Create and deploy app protection policies with Microsoft Intune</span></span>](app-protection-policies.md)
