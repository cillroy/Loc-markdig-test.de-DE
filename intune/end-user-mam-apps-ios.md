---
title: iOS-Apps mit App-Schutzrichtlinien
description: In diesem Thema erfahren Sie, was Sie erwartet, wenn Ihre iOS-App von App-Schutzrichtlinien verwaltet wird.
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 05/05/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: b57e6525-b57c-4cb4-a84c-9f70ba1e8e19
ms.reviewer: andcerat
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 7c0194f3468cffa962a33daea50d13ee8c356d76
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2018
---
# <a name="what-to-expect-when-your-ios-app-is-managed-by-app-protection-policies"></a><span data-ttu-id="55511-103">Was Sie erwartet, wenn Ihre iOS-App von App-Schutzrichtlinien verwaltet wird</span><span class="sxs-lookup"><span data-stu-id="55511-103">What to expect when your iOS app is managed by app protection policies</span></span>

[!INCLUDE [both-portals](./includes/note-for-both-portals.md)]

 <span data-ttu-id="55511-104">Dieses Thema beschreibt die Benutzererfahrung bei der Verwendung von Apps mit angewendeten App-Schutzrichtlinien.</span><span class="sxs-lookup"><span data-stu-id="55511-104">This topic describes the user experience when using apps with app protection policies applied to.</span></span> <span data-ttu-id="55511-105">App-Schutzrichtlinien gelten nur, wenn Apps in einem geschäftlichen Kontext verwendet werden, z. B. wenn der Benutzer ein Geschäftskonto für den Zugriff auf Apps verwendet oder auf Dateien zugreift, die an einem OneDrive for Business-Speicherort im Unternehmen gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="55511-105">App protection policies are applied only when apps are used in the work context; for example, when the user is accessing apps with a work account or accessing files that are stored in a company OneDrive for business location.</span></span>

##  <a name="access-apps"></a><span data-ttu-id="55511-106">Zugriff auf Apps</span><span class="sxs-lookup"><span data-stu-id="55511-106">Access apps</span></span>

<span data-ttu-id="55511-107">Wenn das Gerät **nicht bei Intune registriert** ist, wird der Benutzer beim ersten Verwenden der App aufgefordert, die App neu zu starten.</span><span class="sxs-lookup"><span data-stu-id="55511-107">If the device is **not enrolled in Intune**, the user is asked to restart the app when they first use it.</span></span> <span data-ttu-id="55511-108">Ein Neustart ist erforderlich, damit App-Schutzrichtlinien auf die App angewendet werden können.</span><span class="sxs-lookup"><span data-stu-id="55511-108">A restart is required so that app protection polices can be applied to the app.</span></span>

<!--- The following screenshot from the Skype app illustrates this restart request: --->


<!---  ![Screenshot of the iOS device showing PIN prompt](../media/appmanagement/iOS_AppPINPrompt.png) --->

<span data-ttu-id="55511-109">Bei Geräten, die **für die Verwaltung in Intune registriert** sind, wird dem Benutzer eine Meldung angezeigt, dass seine App nun verwaltet wird.</span><span class="sxs-lookup"><span data-stu-id="55511-109">For devices that are **enrolled for management in Intune**, the user sees a message that their app is now managed.</span></span>

##  <a name="use-apps-with-multi-identity-support"></a><span data-ttu-id="55511-110">Verwenden von Apps mit Unterstützung von mehreren Identitäten</span><span class="sxs-lookup"><span data-stu-id="55511-110">Use apps with multi-identity support</span></span>

<span data-ttu-id="55511-111">Apps, die mehrere Identitäten unterstützen, bieten Ihnen die Möglichkeit, verschiedene Konten (Geschäfts- und persönliche Konten) für den Zugriff auf die gleichen Apps zu verwenden. Hierbei werden App-Schutzrichtlinien nur angewendet, wenn die Apps im Arbeitskontext verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="55511-111">Apps that support multi-identity let you use different accounts (work and personal) to access the same apps, while app protection policies are applied only when the apps are used in the work context.</span></span>  

<span data-ttu-id="55511-112">Beispielsweise erhalten Benutzer eine PIN-Eingabeaufforderung, wenn Sie auf Geschäftsdaten zugreifen.</span><span class="sxs-lookup"><span data-stu-id="55511-112">For example, the user gets a PIN prompt when accessing work data.</span></span> <span data-ttu-id="55511-113">Bei der **Outlook-App** wird der Benutzer beim Starten der App zur Eingabe einer PIN aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="55511-113">For the **Outlook app**, the user is prompted for a PIN when they launch the app.</span></span> <span data-ttu-id="55511-114">Bei der **OneDrive-App** wird der Benutzer zur Eingabe einer PIN aufgefordert, wenn er das Geschäftskonto eingibt.</span><span class="sxs-lookup"><span data-stu-id="55511-114">For the **OneDrive app**, the user is prompted for a pin when they type in the work account.</span></span>  <span data-ttu-id="55511-115">Bei Microsoft **Word**, **PowerPoint** und **Excel** wird der Benutzer zur Eingabe einer PIN aufgefordert, wenn er auf Dokumente zugreift, die am OneDrive for Business-Speicherort des Unternehmens gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="55511-115">For Microsoft **Word**, **PowerPoint**, and **Excel**, the user is prompted for a pin when they access documents that are stored in the company OneDrive for Business location.</span></span>

- <span data-ttu-id="55511-116">Erfahren Sie mehr über die Apps, die [App-Schutz und mehrere Identitäten](https://www.microsoft.com/cloud-platform/microsoft-intune-apps) mit Intune unterstützen.</span><span class="sxs-lookup"><span data-stu-id="55511-116">Learn more about the apps that support [app protection and multi-identity](https://www.microsoft.com/cloud-platform/microsoft-intune-apps) with Intune.</span></span>

<span data-ttu-id="55511-117">App-Schutzrichtlinien werden nur im geschäftlichen Kontext angewendet.</span><span class="sxs-lookup"><span data-stu-id="55511-117">App protection polices are only applied in the work context.</span></span> <span data-ttu-id="55511-118">Eine App kann sich daher unterschiedlich verhalten, je nachdem, ob sie im geschäftlichen oder privaten Kontext verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="55511-118">Therefore, the app might behave differently depending on whether the context is work or personal.</span></span>

##  <a name="manage-user-accounts-on-the-device"></a><span data-ttu-id="55511-119">Verwalten von Benutzerkonten auf dem Gerät</span><span class="sxs-lookup"><span data-stu-id="55511-119">Manage user accounts on the device</span></span>

<span data-ttu-id="55511-120">Intune unterstützt die Bereitstellung von App-Schutzrichtlinien nur auf je einem Benutzerkonto pro Gerät.</span><span class="sxs-lookup"><span data-stu-id="55511-120">Intune supports the deployment of app protection policies to  one user account per device only.</span></span>

* <span data-ttu-id="55511-121">Abhängig von der verwendeten App, ist der zweite Benutzer auf dem Gerät möglicherweise blockiert.</span><span class="sxs-lookup"><span data-stu-id="55511-121">Depending on the app that you are using, the second user might be blocked on the device.</span></span> <span data-ttu-id="55511-122">Unter allen Umständen wirken sich die App-Schutzrichtlinien nur auf den ersten Benutzer aus.</span><span class="sxs-lookup"><span data-stu-id="55511-122">However, in all cases, only the first user who gets the app protection policies is affected by the policy.</span></span>
  * <span data-ttu-id="55511-123">**Microsoft Word**, **Excel** und **PowerPoint** blockieren ein zweites Benutzerkonto nicht, die App-Schutzrichtlinien wirken sich auf das zweite Benutzerkonto jedoch nicht aus.</span><span class="sxs-lookup"><span data-stu-id="55511-123">**Microsoft Word**, **Excel**, and **PowerPoint** don't block a second user account, but the second user account is not affected by the app protection policies.</span></span>  

  * <span data-ttu-id="55511-124">Für **OneDrive**- und **Outlook-Apps** können Sie nur ein Geschäftskonto verwenden.</span><span class="sxs-lookup"><span data-stu-id="55511-124">For **OneDrive** and **Outlook apps**, you can only use one work account.</span></span> <span data-ttu-id="55511-125">Sie können für diese Apps nicht mehrere Geschäftskonten hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="55511-125">You can't add multiple work accounts for these apps.</span></span> <span data-ttu-id="55511-126">Sie können jedoch einen Benutzer entfernen und auf dem Gerät einen weiteren Benutzer hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="55511-126">You can however, remove a user and add a different user on the device.</span></span>

* <span data-ttu-id="55511-127">Wenn für ein Gerät vor der Bereitstellung der App-Schutzrichtlinien mehrere Benutzerkonten vorhanden sind, wird das Konto, für das die App-Schutzrichtlinien zuerst bereitgestellt werden, durch die Intune-App-Schutzrichtlinien verwaltet.</span><span class="sxs-lookup"><span data-stu-id="55511-127">If a device has existing multiple user accounts before the app protection policies are deployed, the account that the app protection policies are deployed to first is managed by Intune app protection policies.</span></span>


<span data-ttu-id="55511-128">Lesen Sie das folgende Beispielszenario, um genauer zu verstehen, wie mehrere Benutzerkonten behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="55511-128">Read the following example scenario to get a deeper understanding of how multiple user accounts are treated.</span></span>

<span data-ttu-id="55511-129">Benutzer A arbeitet für zwei Unternehmen – **Unternehmen X** und **Unternehmen Y**. Benutzer A verfügt für jedes Unternehmen über ein geschäftliches Konto, und beide verwenden Intune zum Bereitstellen von App-Schutzrichtlinien.</span><span class="sxs-lookup"><span data-stu-id="55511-129">User A works for two companies—**Company X** and **Company Y**. User A has a work account for each company, and both use Intune to deploy app protection policies.</span></span> <span data-ttu-id="55511-130">**Unternehmen X** stellt App-Schutzrichtlinien **vor** **Unternehmen Y** bereit. Das dem **Unternehmen X** zugeordnete Konto erhält die App-Schutzrichtlinie, nicht jedoch das dem Unternehmen Y zugeordnete Konto. Wenn das dem Unternehmen Y zugeordnete Konto durch die App-Schutzrichtlinien verwaltet werden soll, müssen Sie das dem Unternehmen X zugeordnete Benutzerkonto entfernen.</span><span class="sxs-lookup"><span data-stu-id="55511-130">**Company X** deploys app protection policies **before** **Company Y**. The account that's associated with **Company X** gets the app protection policy, but not the account that's associated with Company Y. If you want the user account that's associated with Company Y to be managed by the app protection policies, you must remove the user account that's associated with Company X.</span></span>

### <a name="add-a-second-account"></a><span data-ttu-id="55511-131">Hinzufügen eines zweiten Kontos</span><span class="sxs-lookup"><span data-stu-id="55511-131">Add a second account</span></span>

<span data-ttu-id="55511-132">Wenn Sie ein iOS-Gerät verwenden und versuchen, auf diesem Gerät ein zweites Geschäftskonto einzurichten, wird möglicherweise eine Sperrnachricht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="55511-132">If you are using an iOS device, when you try to add a second work account on that device, you might see a blocking message.</span></span> <span data-ttu-id="55511-133">Die Konten werden angezeigt, und Sie können das Konto auswählen, das Sie entfernen möchten.</span><span class="sxs-lookup"><span data-stu-id="55511-133">The accounts will be displayed, and then you can choose the account you want to remove.</span></span>

## <a name="next-steps"></a><span data-ttu-id="55511-134">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="55511-134">Next steps</span></span>
[<span data-ttu-id="55511-135">Was Sie erwartet, wenn Ihre Android-App von App-Schutzrichtlinien verwaltet wird</span><span class="sxs-lookup"><span data-stu-id="55511-135">What to expect when your Android app is managed by app protection policies</span></span>](end-user-mam-apps-android.md)
