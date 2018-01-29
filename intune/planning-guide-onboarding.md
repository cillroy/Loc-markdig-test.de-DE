---
title: Intune-Onboardingprozess
description: "Dieser Artikel hilft Ihnen bei allen Details, die beim Onboarding einer reinen Intune-Cloudlösung in Ihrer Umgebung berücksichtigt werden müssen."
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 10/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: ac7bd764-5365-4920-8fd0-ea57d5ebe039
ms.reviewer: jeffbu, cgerth
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 6286a0a844cf1d9e665ed29d1eba7fb25876a8e6
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2018
---
# <a name="implement-your-intune-plan"></a><span data-ttu-id="5ae41-103">Implementieren Ihres Intune-Plans</span><span class="sxs-lookup"><span data-stu-id="5ae41-103">Implement your Intune plan</span></span>

<span data-ttu-id="5ae41-104">Während der Onboarding-Phase stellen Sie Intune in Ihrer Produktionsumgebung bereit.</span><span class="sxs-lookup"><span data-stu-id="5ae41-104">During the onboarding phase, you deploy Intune into your production environment.</span></span> <span data-ttu-id="5ae41-105">Der Implementierungsprozess besteht aus dem Einrichten und Konfigurieren von Intune und externen Abhängigkeiten (falls erforderlich), basierend auf den [Anforderungen Ihres Anwendungsfalls](planning-guide-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5ae41-105">The implementation process consists of setting up and configuring Intune and external dependencies (if required) based on your [use-case requirements](planning-guide-requirements.md).</span></span>

<span data-ttu-id="5ae41-106">Der folgende Abschnitt enthält eine Übersicht über den Intune-Implementierungsprozess, der Anforderungen und allgemeine Aufgaben umfasst.</span><span class="sxs-lookup"><span data-stu-id="5ae41-106">The following section provides an overview of the Intune implementation process that includes requirements and high-level tasks.</span></span>

## <a name="intune-requirements"></a><span data-ttu-id="5ae41-107">Intune-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="5ae41-107">Intune requirements</span></span>

<span data-ttu-id="5ae41-108">Die wichtigsten Anforderungen der eigenständigen Intune-Version lauten wie folgt:</span><span class="sxs-lookup"><span data-stu-id="5ae41-108">The main Intune standalone requirements are:</span></span>

-   <span data-ttu-id="5ae41-109">Enterprise Mobility + Security (EMS)/Intune-Abonnement</span><span class="sxs-lookup"><span data-stu-id="5ae41-109">Enterprise Mobility + Security (EMS)/Intune subscription</span></span>

-   <span data-ttu-id="5ae41-110">Office 365-Abonnement (für Office-Apps und über die durch die App-Schutzrichtlinie verwalteten Apps)</span><span class="sxs-lookup"><span data-stu-id="5ae41-110">Office 365 subscription (for Office apps and app-protection-policy managed apps)</span></span>

-   <span data-ttu-id="5ae41-111">Apple APNs-Zertifikat (zum Aktivieren der Verwaltung der iOS-Geräteplattform)</span><span class="sxs-lookup"><span data-stu-id="5ae41-111">Apple APNs Certificate (to enable iOS device platform management)</span></span>

-   <span data-ttu-id="5ae41-112">Azure AD Connect (zur Verzeichnissynchronisierung)</span><span class="sxs-lookup"><span data-stu-id="5ae41-112">Azure AD Connect (for directory synchronization)</span></span>

-   <span data-ttu-id="5ae41-113">Intune-Connector für lokale Exchange-Umgebungen (für bedingten Zugriff für Exchange lokal, falls erforderlich)</span><span class="sxs-lookup"><span data-stu-id="5ae41-113">Intune On-Premises Connector for Exchange (for conditional access for Exchange On-Premises, if needed)</span></span>

-   <span data-ttu-id="5ae41-114">Intune Certificate Connector (für die SCEP-Zertifikatbereitstellung, falls erforderlich)</span><span class="sxs-lookup"><span data-stu-id="5ae41-114">Intune Certificate Connector (for SCEP certificate deployment, if needed)</span></span>

>[!TIP]
> <span data-ttu-id="5ae41-115">Die Liste [Unterstützte Geräte](supported-devices-browsers.md) umfasst eine vollständige Auflistung der Geräte, die mit Intune verwaltet werden können.</span><span class="sxs-lookup"><span data-stu-id="5ae41-115">See the list of [supported devices](supported-devices-browsers.md) for a complete list of devices you can manage with Intune.</span></span>

## <a name="intune-implementation-process"></a><span data-ttu-id="5ae41-116">Intune-Implementierungsprozess</span><span class="sxs-lookup"><span data-stu-id="5ae41-116">Intune implementation process</span></span>

<span data-ttu-id="5ae41-117">Es wurden 13 diskrete Aufgaben für die Implementierung einer Intune-Bereitstellung identifiziert.</span><span class="sxs-lookup"><span data-stu-id="5ae41-117">We've identified 13 discrete tasks for implementing an Intune deployment.</span></span> <span data-ttu-id="5ae41-118">Abhängig von Ihren Geschäftsanforderungen, der vorhandenen Infrastruktur und der Verwaltungsstrategie für Geräte sind einige dieser Aufgaben möglicherweise bereits abgeschlossen worden.</span><span class="sxs-lookup"><span data-stu-id="5ae41-118">Depending on your business requirements, existing infrastructure, and device management strategy, some of these tasks may already be finished.</span></span> <span data-ttu-id="5ae41-119">Andere finden möglicherweise keine Anwendung auf Ihren Plan.</span><span class="sxs-lookup"><span data-stu-id="5ae41-119">Others may not apply to your plan.</span></span>

### <a name="task-1-get-an-intune-subscription"></a><span data-ttu-id="5ae41-120">Aufgabe 1: Abschließen eines Intune-Abonnements</span><span class="sxs-lookup"><span data-stu-id="5ae41-120">Task 1: Get an Intune subscription</span></span>

<span data-ttu-id="5ae41-121">Wie oben im Abschnitt „Intune-Anforderungen“ angegeben, benötigen Sie ein EMS- oder Intune-Abonnement.</span><span class="sxs-lookup"><span data-stu-id="5ae41-121">As indicated in the Intune requirements section above, you need an EMS or Intune subscription.</span></span> <span data-ttu-id="5ae41-122">Wenn Ihre Organisation nicht über ein solches Abonnement verfügt, wenden Sie sich an Microsoft oder das Microsoft-Konto-Team, und teilen Sie Ihr Interesse am Kauf von Enterprise Mobility + Security (EMS) oder Intune mit.</span><span class="sxs-lookup"><span data-stu-id="5ae41-122">If your organization does not have one, contact Microsoft or your Microsoft account team regarding your interest in purchasing Enterprise Mobility + Security (EMS) or Intune.</span></span>

-   <span data-ttu-id="5ae41-123">Informationen zum [Kauf von Microsoft Intune](https://www.microsoft.com/cloud-platform/microsoft-intune-pricing).</span><span class="sxs-lookup"><span data-stu-id="5ae41-123">Learn more about [how to buy Microsoft Intune](https://www.microsoft.com/cloud-platform/microsoft-intune-pricing).</span></span>

### <a name="task-2-add-office-365-subscription"></a><span data-ttu-id="5ae41-124">Aufgabe 2: Hinzufügen eines Office 365-Abonnements</span><span class="sxs-lookup"><span data-stu-id="5ae41-124">Task 2: Add Office 365 subscription</span></span>

<span data-ttu-id="5ae41-125">Dieser Schritt ist optional.</span><span class="sxs-lookup"><span data-stu-id="5ae41-125">This step is optional.</span></span> <span data-ttu-id="5ae41-126">Sie benötigen ein Office 365-Abonnement, wenn Sie planen, Exchange Online zu verwenden und mobile Office-Apps mit App-Schutzrichtlinien zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="5ae41-126">You need an Office 365 subscription if you plan to use Exchange Online and manage Office mobile apps with app protection policies.</span></span> <span data-ttu-id="5ae41-127">Wenn Ihre Organisation nicht über ein Office 365-Abonnement verfügt, wenden Sie sich an Microsoft oder das Microsoft-Konto-Team, und teilen Sie Ihr Interesse am Kauf von Office 365 mit.</span><span class="sxs-lookup"><span data-stu-id="5ae41-127">If your organization does not have an Office 365 subscription, contact Microsoft or your Microsoft account team regarding your interest in purchasing Office 365.</span></span>

-   <span data-ttu-id="5ae41-128">Weitere Informationen zu [Office 365-Bezugsquellen](https://products.office.com/business/compare-office-365-for-business-plans).</span><span class="sxs-lookup"><span data-stu-id="5ae41-128">Learn more about [how to buy Office 365](https://products.office.com/business/compare-office-365-for-business-plans).</span></span>

### <a name="task-3-add-users-groups-in-azure-ad"></a><span data-ttu-id="5ae41-129">Aufgabe 3: Hinzufügen von Benutzergruppen in Azure AD</span><span class="sxs-lookup"><span data-stu-id="5ae41-129">Task 3: Add users groups in Azure AD</span></span>

<span data-ttu-id="5ae41-130">Möglicherweise müssen Sie je nach den Anwendungsszenarios und Anforderungen Ihrer Intune-Bereitstellung Benutzer oder Sicherheitsgruppen in Active Directory oder Azure Active Directory hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="5ae41-130">You may need to add users or security groups in Active Directory or Azure Active Directory based on your Intune deployment use-case scenarios and requirements.</span></span> <span data-ttu-id="5ae41-131">Überprüfen Sie Ihre aktuellen Benutzer und Sicherheitsgruppen in Active Directory oder Azure Active Directory, und ermitteln Sie, ob diese vollständig Ihren Anforderungen entsprechen.</span><span class="sxs-lookup"><span data-stu-id="5ae41-131">Review your current users and security groups in Active Directory or Azure Active Directory and determine if they fully meet your needs.</span></span> <span data-ttu-id="5ae41-132">Wenn Sie neue Benutzer und Sicherheitsgruppen hinzufügen, wird empfohlen, diese in Active Directory hinzuzufügen und sie über Azure AD Connect mit Azure Active Directory zu synchronisieren.</span><span class="sxs-lookup"><span data-stu-id="5ae41-132">When adding new users and security groups, we recommend adding them in Active Directory and synchronizing with Azure Active Directory using Azure AD Connect.</span></span>


- <span data-ttu-id="5ae41-133">Weitere Informationen zum [Hinzufügen von Benutzern/Gruppen in Intune](users-permissions-add.md).</span><span class="sxs-lookup"><span data-stu-id="5ae41-133">Learn more about [how to add users/groups in Intune](users-permissions-add.md).</span></span>
  <!---why not send them to the AAD connect topic? Question out to Andre: https://docs.microsoft.com/en-us/azure/active-directory/connect/active-directory-aadconnect--->



### <a name="task-4-assign-intune-and-office-365-user-licenses"></a><span data-ttu-id="5ae41-134">Aufgabe 4: Zuweisen von Intune- und Office 365-Benutzerlizenzen</span><span class="sxs-lookup"><span data-stu-id="5ae41-134">Task 4: Assign Intune and Office 365 user licenses</span></span>

<span data-ttu-id="5ae41-135">Allen Zielbenutzern für das EMS/Intune- und Office 365-Rollout muss eine Lizenz zugewiesen sein.</span><span class="sxs-lookup"><span data-stu-id="5ae41-135">All users you target for EMS/Intune and Office 365 rollout need to have a license assigned to them.</span></span> <span data-ttu-id="5ae41-136">Sie können im Office 365 Admin Center-Portal EMS/Intune- und Office 365-Lizenzen zuweisen.</span><span class="sxs-lookup"><span data-stu-id="5ae41-136">You can assign EMS/Intune and Office 365 licenses in the Office 365 Admin Center Portal.</span></span>

-   <span data-ttu-id="5ae41-137">Weitere Informationen zum [Zuweisen von Intune-Lizenzen](licenses-assign.md).</span><span class="sxs-lookup"><span data-stu-id="5ae41-137">Learn more about [how to assign Intune licenses](licenses-assign.md).</span></span>

### <a name="task-5-set-mobile-device-management-authority-to-intune"></a><span data-ttu-id="5ae41-138">Aufgabe 5: Festlegen der Autorität für die Verwaltung mobiler Geräte auf Intune</span><span class="sxs-lookup"><span data-stu-id="5ae41-138">Task 5: Set mobile device management authority to Intune</span></span>

<span data-ttu-id="5ae41-139">Bevor Sie mit dem Einrichten, Konfigurieren, Verwalten und Registrieren von Geräten mit Intune beginnen können, müssen Sie die Autorität für die Geräteverwaltung in Intune festlegen.</span><span class="sxs-lookup"><span data-stu-id="5ae41-139">Before you can begin to set up, configure, manage and enroll devices using Intune, you must set the device management authority to Intune.</span></span>

-   <span data-ttu-id="5ae41-140">Weitere Informationen zum [Festlegen der Autorität für die Geräteverwaltung](mdm-authority-set.md).</span><span class="sxs-lookup"><span data-stu-id="5ae41-140">Learn more about [how to set the device management authority](mdm-authority-set.md).</span></span>

### <a name="task-6-enable-device-platforms"></a><span data-ttu-id="5ae41-141">Aufgabe 6: Aktivieren von Geräteplattformen</span><span class="sxs-lookup"><span data-stu-id="5ae41-141">Task 6: Enable device platforms</span></span>

<span data-ttu-id="5ae41-142">Die meisten Geräteplattformen sind standardmäßig aktiviert, mit Ausnahme von Apple-Geräten (iOS und Mac).</span><span class="sxs-lookup"><span data-stu-id="5ae41-142">By default, most device platforms are enabled except for Apple devices (iOS and Mac).</span></span> <span data-ttu-id="5ae41-143">Damit iOS-Geräte registriert und in Intune verwaltet werden können, muss die Geräteplattform aktiviert sein.</span><span class="sxs-lookup"><span data-stu-id="5ae41-143">Before iOS devices can be enrolled and managed in Intune, the device platform must be enabled.</span></span> <span data-ttu-id="5ae41-144">Zu diesem Zweck müssen Sie ein MDM-Push-Zertifikat erstellen und zu Intune hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="5ae41-144">To do so, you need to create an MDM Push certificate, and add it to Intune.</span></span>

-   <span data-ttu-id="5ae41-145">Weitere Informationen zum [Aktivieren von Apple-Geräten für die Registrierung](apple-mdm-push-certificate-get.md).</span><span class="sxs-lookup"><span data-stu-id="5ae41-145">Learn more about [how to enable Apple devices for enrollment](apple-mdm-push-certificate-get.md).</span></span>

### <a name="task-7-add-and-deploy-terms-and-conditions-policies"></a><span data-ttu-id="5ae41-146">Aufgabe 7: Hinzufügen und Bereitstellen von Richtlinien für Geschäftsbedingungen</span><span class="sxs-lookup"><span data-stu-id="5ae41-146">Task 7: Add and deploy terms and conditions policies</span></span>

<span data-ttu-id="5ae41-147">Intune unterstützt Richtlinien für Geschäftsbedingungen.</span><span class="sxs-lookup"><span data-stu-id="5ae41-147">Intune supports terms and conditions policies.</span></span> <span data-ttu-id="5ae41-148">Fügen Sie Richtlinien für Geschäftsbedingungen nach Bedarf hinzu, und stellen Sie sie basierend auf den Anwendungsfällen und Anforderungen Ihrer Intune-Bereitstellung für Zielgruppen bereit.</span><span class="sxs-lookup"><span data-stu-id="5ae41-148">Add terms and conditions policies as appropriate and deploy them to targeted groups based on your Intune deployment use cases and requirements.</span></span>

-   <span data-ttu-id="5ae41-149">Weitere Informationen zum [Hinzufügen und Bereitstellen von Richtlinien für Geschäftsbedingungen](terms-and-conditions-create.md).</span><span class="sxs-lookup"><span data-stu-id="5ae41-149">Learn more about [how to add and deploy terms and condition policies](terms-and-conditions-create.md).</span></span>

### <a name="task-8-add-and-deploy-configuration-policies"></a><span data-ttu-id="5ae41-150">Aufgabe 8: Hinzufügen und Bereitstellen von Konfigurationsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="5ae41-150">Task 8: Add and deploy configuration policies</span></span>

<span data-ttu-id="5ae41-151">Intune unterstützt zwei Arten von Konfigurationsrichtlinien: allgemeine und benutzerdefinierte.</span><span class="sxs-lookup"><span data-stu-id="5ae41-151">Intune supports two types of configuration policies, general and custom.</span></span> <span data-ttu-id="5ae41-152">Fügen Sie Konfigurationsrichtlinien nach Bedarf hinzu, und stellen Sie sie basierend auf den Anwendungsfällen und Anforderungen Ihrer Intune-Bereitstellung für Zielgruppen bereit.</span><span class="sxs-lookup"><span data-stu-id="5ae41-152">Add the configuration policies as appropriate and deploy them to targeted groups based on your Intune deployment use cases and requirements.</span></span>

-   <span data-ttu-id="5ae41-153">Weitere Informationen zum [Hinzufügen und Bereitstellen von Konfigurationsrichtlinien](device-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="5ae41-153">Learn more about [how to add and deploy configuration policies](device-profiles.md).</span></span>

### <a name="task-9-add-and-deploy-resource-profiles"></a><span data-ttu-id="5ae41-154">Aufgabe 9: Hinzufügen und Bereitstellen von Ressourcenprofilen</span><span class="sxs-lookup"><span data-stu-id="5ae41-154">Task 9: Add and deploy resource profiles</span></span>

<span data-ttu-id="5ae41-155">Intune unterstützt E-Mail-, WLAN- und VPN-Profile.</span><span class="sxs-lookup"><span data-stu-id="5ae41-155">Intune supports email, Wi-Fi, and VPN profiles.</span></span> <span data-ttu-id="5ae41-156">Fügen Sie diese Profile nach Bedarf hinzu, und stellen Sie sie basierend auf den Anwendungsfällen und Anforderungen Ihrer Intune-Bereitstellung für Zielgruppen bereit.</span><span class="sxs-lookup"><span data-stu-id="5ae41-156">Add these profiles as appropriate and deploy them to targeted groups based on your Intune deployment use cases and requirements.</span></span>

-   <span data-ttu-id="5ae41-157">Weitere Informationen zum [Aktivieren des Zugriffs auf Unternehmensressourcen mit Intune](device-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="5ae41-157">Learn more about [how to enable access to company resources with Intune](device-profiles.md).</span></span>

### <a name="task-10-add-and-deploy-apps"></a><span data-ttu-id="5ae41-158">Aufgaben 10: Hinzufügen und Bereitstellen von Apps</span><span class="sxs-lookup"><span data-stu-id="5ae41-158">Task 10: Add and deploy apps</span></span>

<span data-ttu-id="5ae41-159">Intune unterstützt die Bereitstellung von Web-Apps, branchenspezifischen Apps und Apps aus öffentlichen Stores.</span><span class="sxs-lookup"><span data-stu-id="5ae41-159">Intune supports the deployment of web, line-of-business, and public Store apps.</span></span> <span data-ttu-id="5ae41-160">Sie können auch Apps mit integriertem Intune SDK verwalten, indem Sie ihnen App-Schutzrichtlinien zuordnen.</span><span class="sxs-lookup"><span data-stu-id="5ae41-160">You can also manage apps that have integrated the Intune SDK by associating them with app protection policies.</span></span> <span data-ttu-id="5ae41-161">Fügen Sie Apps nach Bedarf hinzu, und stellen Sie sie basierend auf den Anwendungsfällen und Anforderungen Ihrer Intune-Bereitstellung für Zielgruppen bereit.</span><span class="sxs-lookup"><span data-stu-id="5ae41-161">Add apps as appropriate and deploy them to targeted groups based on your Intune deployment use cases and requirements.</span></span>

-   <span data-ttu-id="5ae41-162">Weitere Informationen zum [Hinzufügen und Bereitstellen von Apps](app-management.md).</span><span class="sxs-lookup"><span data-stu-id="5ae41-162">Learn more about [adding and deploying apps](app-management.md).</span></span>

### <a name="task-11-add-and-deploy-compliance-policies"></a><span data-ttu-id="5ae41-163">Aufgabe 11: Hinzufügen und Bereitstellen von Konformitätsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="5ae41-163">Task 11: Add and deploy compliance policies</span></span>

<span data-ttu-id="5ae41-164">Intune unterstützt Kompatibilitätsrichtlinien.</span><span class="sxs-lookup"><span data-stu-id="5ae41-164">Intune supports compliance policies.</span></span> <span data-ttu-id="5ae41-165">Fügen Sie Kompatibilitätsrichtlinien nach Bedarf hinzu, und stellen Sie sie basierend auf den Anwendungsfällen und Anforderungen Ihrer Intune-Bereitstellung für Zielgruppen bereit.</span><span class="sxs-lookup"><span data-stu-id="5ae41-165">Add compliance policies as appropriate and deploy them to targeted groups based on your Intune deployment use cases and requirements.</span></span>

-   <span data-ttu-id="5ae41-166">Weitere Informationen zu [Konformitätsrichtlinien](device-compliance.md).</span><span class="sxs-lookup"><span data-stu-id="5ae41-166">Learn more about [compliance policies](device-compliance.md).</span></span>

### <a name="task-12-enable-conditional-access-policies"></a><span data-ttu-id="5ae41-167">Aufgabe 12: Aktivieren von Richtlinien für bedingten Zugriff</span><span class="sxs-lookup"><span data-stu-id="5ae41-167">Task 12: Enable conditional access policies</span></span>

<span data-ttu-id="5ae41-168">Intune unterstützt den bedingten Zugriff für Exchange Online und lokal, SharePoint Online, Skype for Business Online und Dynamics CRM Online.</span><span class="sxs-lookup"><span data-stu-id="5ae41-168">Intune supports conditional access for Exchange Online, Exchange on-premises, SharePoint Online, Skype for Business Online, and Dynamics CRM Online.</span></span> <span data-ttu-id="5ae41-169">Aktivieren und konfigurieren Sie den bedingten Zugriff nach Bedarf basierend auf den Anwendungsfällen und Anforderungen Ihrer Intune-Bereitstellung.</span><span class="sxs-lookup"><span data-stu-id="5ae41-169">Enable and configure conditional access as appropriate based on your Intune deployment use cases and requirements.</span></span>

-   <span data-ttu-id="5ae41-170">Weitere Informationen zum [bedingten Zugriff](conditional-access.md).</span><span class="sxs-lookup"><span data-stu-id="5ae41-170">Learn more about [conditional access](conditional-access.md).</span></span>

### <a name="task-13-enroll-devices"></a><span data-ttu-id="5ae41-171">Aufgabe 13: Registrieren von Geräten</span><span class="sxs-lookup"><span data-stu-id="5ae41-171">Task 13: Enroll devices</span></span>

<span data-ttu-id="5ae41-172">Intune unterstützt die Geräteplattformen iOS, Mac OS, Android, Windows Desktop und Windows Mobile.</span><span class="sxs-lookup"><span data-stu-id="5ae41-172">Intune supports iOS, Mac OS, Android, Windows desktop, and Windows mobile device platforms.</span></span> <span data-ttu-id="5ae41-173">Registrieren Sie Mobilgeräteplattformen nach Bedarf basierend auf den Anwendungsfällen und Anforderungen Ihrer Intune-Bereitstellung.</span><span class="sxs-lookup"><span data-stu-id="5ae41-173">Enroll mobile device platforms as appropriate based on your Intune deployment use cases and requirements.</span></span>

-   <span data-ttu-id="5ae41-174">Weitere Informationen zum [Registrieren von Geräten](device-enrollment.md).</span><span class="sxs-lookup"><span data-stu-id="5ae41-174">Learn more about [how to enroll devices](device-enrollment.md).</span></span>


## <a name="next-steps"></a><span data-ttu-id="5ae41-175">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="5ae41-175">Next steps</span></span>

<span data-ttu-id="5ae41-176">Weitere Informationen zum Prozess der Intune-Implementierung finden Sie in diesem [Intune-Sitzungsmodul der Microsoft Virtual Academy](https://mva.microsoft.com/en-US/training-courses/deploying-microsoft-enterprise-mobility-suite-16408).</span><span class="sxs-lookup"><span data-stu-id="5ae41-176">Check out this [Microsoft Virtual Academy Intune session module](https://mva.microsoft.com/en-US/training-courses/deploying-microsoft-enterprise-mobility-suite-16408) for more information on the Intune implementation process.</span></span>


<span data-ttu-id="5ae41-177">Weitere Informationen finden Sie im Leitfaden zum [Testen und Überprüfen Ihrer Intune-Bereitstellung](planning-guide-test-validation.md).</span><span class="sxs-lookup"><span data-stu-id="5ae41-177">See guidance on [testing and validating your Intune deployment](planning-guide-test-validation.md).</span></span>
