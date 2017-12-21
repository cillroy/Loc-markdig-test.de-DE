---
title: iOS-Apps mit App-Schutzrichtlinien
titlesuffix: Azure portal
description: In diesem Thema erfahren Sie, was Sie erwartet, wenn Ihre iOS-App von App-Schutzrichtlinien verwaltet wird."
keywords: 
author: erikre
ms.author: erikre
manager: angrobe
ms.date: 12/07/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 586d9440-3813-4dec-b865-8bd319befde0
ms.reviewer: andcerat
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: e7f0761124ccb425151ca7b06a9982b61b765db0
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2017
---
# <a name="what-to-expect-when-your-ios-app-is-managed-by-app-protection-policies"></a><span data-ttu-id="a6af4-103">Was Sie erwartet, wenn Ihre iOS-App von App-Schutzrichtlinien verwaltet wird</span><span class="sxs-lookup"><span data-stu-id="a6af4-103">What to expect when your iOS app is managed by app protection policies</span></span>

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="a6af4-104">Dieses Thema beschreibt die Benutzererfahrung für Apps mit App-Schutzrichtlinien.</span><span class="sxs-lookup"><span data-stu-id="a6af4-104">This topic describes the user experience for apps with app protection policies.</span></span> <span data-ttu-id="a6af4-105">App-Schutzrichtlinien gelten nur, wenn Apps im geschäftlichen Kontext verwendet werden, z.B. wenn Sie Ihr Geschäftskonto für den Zugriff auf Apps verwenden oder auf Dateien zugreifen, die am OneDrive for Business-Speicherort Ihres Unternehmens gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="a6af4-105">App protection polices are applied only when apps are used in the work context: like accessing apps using your work account, or accessing files stored in your company OneDrive business location.</span></span>
##  <a name="accessing-apps"></a><span data-ttu-id="a6af4-106">Zugreifen auf Apps</span><span class="sxs-lookup"><span data-stu-id="a6af4-106">Accessing apps</span></span>

<span data-ttu-id="a6af4-107">Wenn das Gerät **nicht bei Intune registriert** ist, wird der Endbenutzer beim ersten Verwenden der App dazu aufgefordert, die App neu zu starten.</span><span class="sxs-lookup"><span data-stu-id="a6af4-107">If the device is **not enrolled in Intune**, the end-user will be asked to restart the app when they first use the app.</span></span>  <span data-ttu-id="a6af4-108">Ein Neustart ist erforderlich, damit App-Schutzrichtlinien auf die App angewendet werden können.</span><span class="sxs-lookup"><span data-stu-id="a6af4-108">A restart is required so app protection polices can be applied to the app.</span></span> <span data-ttu-id="a6af4-109">Der folgende Screenshot stellt dies mithilfe der Skype-App dar:</span><span class="sxs-lookup"><span data-stu-id="a6af4-109">The following screenshot illustrates this using the Skype app:</span></span>


![Screenshot des iOS-Geräts mit der PIN-Eingabeaufforderung](./media/ios-pin-prompt.png)

<span data-ttu-id="a6af4-111">Bei Geräten, die **für die Verwaltung in Intune registriert** sind, wird dem Endbenutzer eine Meldung angezeigt, dass seine App nun verwaltet wird:</span><span class="sxs-lookup"><span data-stu-id="a6af4-111">For devices that are **enrolled for management in Intune**, the end-user will see a message that their app is now managed:</span></span>

![Screenshot des iOS-Geräts mit der Meldung zur Verwaltung durch das Unternehmen und der Eingabeaufforderung](./media/ios-managed-devices-pin-prompt.png)

##  <a name="using-apps-with-multi-identity-support"></a><span data-ttu-id="a6af4-113">Verwenden von Apps mit Multi-Identity Support (Unterstützung für mehrere Identitäten)</span><span class="sxs-lookup"><span data-stu-id="a6af4-113">Using apps with multi-identity support</span></span>

<span data-ttu-id="a6af4-114">App-Schutzrichtlinien gelten nur, wenn die App im geschäftlichen Kontext verwendet wird. Daher kann das App-Verhalten abhängig vom Kontext (geschäftlich oder privat) abweichen.</span><span class="sxs-lookup"><span data-stu-id="a6af4-114">App protection polices are only applied in the work context when using the app, so you may see different app behaviors depending on the context: work or personal.</span></span>  

<span data-ttu-id="a6af4-115">Bei Apps, die mehrere Identitäten unterstützen, wendet Intune die App-Schutzrichtlinien nur an, wenn der Endbenutzer die App im geschäftlichen Kontext verwendet.</span><span class="sxs-lookup"><span data-stu-id="a6af4-115">For apps that support multi-identity, Intune only applies the app protection policies when the end-user is using the app in the work context.</span></span>  <span data-ttu-id="a6af4-116">Beispielsweise erhalten Endbenutzer eine PIN-Eingabeaufforderung, wenn Sie auf Geschäftsdaten zugreifen.</span><span class="sxs-lookup"><span data-stu-id="a6af4-116">For example, the end-user will get a PIN prompt when accessing work data.</span></span>  <span data-ttu-id="a6af4-117">Bei der **Outlook-App** wird der Endbenutzer beim Starten der App zur Eingabe einer PIN aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="a6af4-117">For the **Outlook app**, the end-user is prompted for a PIN on launching the app.</span></span> <span data-ttu-id="a6af4-118">Bei der **OneDrive-App** erfolgt diese Aufforderung, wenn der Endbenutzer das Geschäftskonto eingibt.</span><span class="sxs-lookup"><span data-stu-id="a6af4-118">For the **OneDrive app**, this happens when the end-user types in the work account.</span></span>  <span data-ttu-id="a6af4-119">Bei Microsoft **Word**, **PowerPoint* und **Excel** erfolgt diese Aufforderung, wenn der Endbenutzer auf Dokumente zugreift, die am OneDrive for Business-Speicherort des Unternehmens gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="a6af4-119">For Microsoft **Word**, **PowerPoint*, and **Excel**, this happens when the end-user accesses documents stored in the company OneDrive for Business location.</span></span>
##  <a name="managing-user-accounts-on-the-device"></a><span data-ttu-id="a6af4-120">Verwalten von Benutzerkonten auf dem Gerät</span><span class="sxs-lookup"><span data-stu-id="a6af4-120">Managing user accounts on the device</span></span>

<span data-ttu-id="a6af4-121">Intune unterstützt nur die Bereitstellung von App-Schutzrichtlinien auf je einem Benutzerkonto pro Gerät.</span><span class="sxs-lookup"><span data-stu-id="a6af4-121">Intune only supports deploying app protection policies to only one user account per device.</span></span>

* <span data-ttu-id="a6af4-122">Abhängig von der verwendeten App, ist der zweite Benutzer auf dem Gerät möglicherweise blockiert oder auch nicht.</span><span class="sxs-lookup"><span data-stu-id="a6af4-122">Depending on the app that you are using, the second user may or may not be blocked on the device.</span></span> <span data-ttu-id="a6af4-123">Unter allen Umständen wirken sich die App-Schutzrichtlinien nur auf den ersten Benutzer aus.</span><span class="sxs-lookup"><span data-stu-id="a6af4-123">However, in all cases, only the first user who gets the app protection policies is affected by the policy.</span></span>
  * <span data-ttu-id="a6af4-124">**Microsoft Word**, **Excel** und **PowerPoint** blockieren ein zweites Benutzerkonto nicht, die App-Schutzrichtlinien wirken sich auf das zweite Benutzerkonto jedoch nicht aus.</span><span class="sxs-lookup"><span data-stu-id="a6af4-124">**Microsoft Word**, **Excel**, and **PowerPoint** don't block a second user account, but the second user account is not affected by the app protection policies.</span></span>  

  * <span data-ttu-id="a6af4-125">Für **OneDrive- und Outlook-Apps** kann nur ein geschäftliches Konto verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="a6af4-125">For **OneDrive and Outlook apps**, you can only use one work account.</span></span>  <span data-ttu-id="a6af4-126">Das Hinzufügen weiterer Geschäftskonten wird von diesen Apps blockiert.</span><span class="sxs-lookup"><span data-stu-id="a6af4-126">Adding multiple work accounts are blocked on these apps.</span></span>  <span data-ttu-id="a6af4-127">Sie können jedoch einen Benutzer entfernen und auf dem Gerät einen weiteren Benutzer hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="a6af4-127">You can however, remove a user and add a different user on the device.</span></span>

* <span data-ttu-id="a6af4-128">Wenn für ein Gerät vor der Bereitstellung der App-Schutzrichtlinien mehrere Benutzerkonten vorhanden sind, wird das Konto, für das die App-Schutzrichtlinien zuerst bereitgestellt werden, durch die Intune-App-Schutzrichtlinien verwaltet.</span><span class="sxs-lookup"><span data-stu-id="a6af4-128">If a device has existing multiple user accounts before the app protection policies are deployed, the account that the app protection policies is deployed to first is managed by Intune app protection policies.</span></span>


<span data-ttu-id="a6af4-129">Lesen Sie das Beispielszenario unten, um genauer zu verstehen, wie mehrere Benutzerkonten behandelt werden.</span><span class="sxs-lookup"><span data-stu-id="a6af4-129">Read the example scenario below to get a deeper understanding of how multiple user accounts are treated.</span></span>

<span data-ttu-id="a6af4-130">Benutzer A arbeitet für zwei Unternehmen – **Unternehmen X** und **Unternehmen Y**. Benutzer A verfügt für jedes Unternehmen über ein geschäftliches Konto, und beide verwenden Intune zum Bereitstellen von App-Schutzrichtlinien.</span><span class="sxs-lookup"><span data-stu-id="a6af4-130">User A works for two companies - **Company X**, and **Company Y**. User A has a work account for each company, and both use Intune to deploy app protection policies.</span></span> <span data-ttu-id="a6af4-131">**Unternehmen X** stellt App-Schutzrichtlinien **vor** **Unternehmen Y** bereit. Das **Unternehmen X** zugeordnete Konto erhält die App-Schutzrichtlinie, nicht jedoch das dem Unternehmen Y zugeordnete Konto. Wenn das Unternehmen Y zugeordnete Konto durch die App-Schutzrichtlinien verwaltet werden soll, müssen Sie das Unternehmen X zugeordnete Benutzerkonto entfernen.</span><span class="sxs-lookup"><span data-stu-id="a6af4-131">**Company X** deploys app protection policies **before** **Company Y**. The account associated with **Company X** will get the app protection policy, but not the account associated with Company Y. If you want the user account associated with Company Y to be managed by the app protection policies, you must remove the user account associated with Company X.</span></span>
### <a name="adding-a-second-account"></a><span data-ttu-id="a6af4-132">Hinzufügen eines zweiten Kontos</span><span class="sxs-lookup"><span data-stu-id="a6af4-132">Adding a second account</span></span>

<span data-ttu-id="a6af4-133">Wenn Sie ein iOS-Gerät verwenden und versuchen, auf demselben Gerät ein zweites Geschäftskonto einzurichten, wird möglicherweise eine Sperrnachricht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a6af4-133">If you are using an iOS device, when you try to add a second work account on the same device, you may see a blocking message.</span></span>  <span data-ttu-id="a6af4-134">Die Konten werden angezeigt, und Sie können das Konto auswählen, das Sie entfernen möchten.</span><span class="sxs-lookup"><span data-stu-id="a6af4-134">The accounts will be displayed and you can choose the account you want to remove.</span></span>

![Screenshot des Dialogfelds mit der Sperrnachricht und den Optionen „Ja“ und „Nein“](./media/ios-switch-user.PNG)

## <a name="next-steps"></a><span data-ttu-id="a6af4-136">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="a6af4-136">Next steps</span></span>
[<span data-ttu-id="a6af4-137">Was Sie erwartet, wenn Ihre Android-App von App-Schutzrichtlinien verwaltet wird</span><span class="sxs-lookup"><span data-stu-id="a6af4-137">What to expect when your Android app is managed by app protection policies</span></span>](app-protection-enabled-apps-android.md)
### <a name="see-also"></a><span data-ttu-id="a6af4-138">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="a6af4-138">See also</span></span>
[<span data-ttu-id="a6af4-139">Erstellen und Bereitstellen von App-Schutzrichtlinien mit Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="a6af4-139">Create and deploy app protection policies with Microsoft Intune</span></span>](app-protection-policies.md)
