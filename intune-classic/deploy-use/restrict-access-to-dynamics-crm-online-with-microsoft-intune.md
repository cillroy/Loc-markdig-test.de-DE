---
title: "Schützen von Dynamics CRM Online"
description: "Schützen und steuern Sie den Zugriff auf Dynamics CRM Online mit bedingtem Zugriff."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 01/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f1c4522b-5a34-4f5a-89d2-7809c4352af7
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: chrisgre
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 150fd3ddc51d814bcd038b75648dbf436a857f1f
ms.sourcegitcommit: e37e916e2bf14f092d3a767bc90d68c181d739fb
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/03/2018
---
# <a name="protect-access-to-dynamics-crm-online-with-intune"></a><span data-ttu-id="4e351-103">Schützen des Zugriffs auf Dynamics CRM Online mit Intune</span><span class="sxs-lookup"><span data-stu-id="4e351-103">Protect access to Dynamics CRM Online with Intune</span></span>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="4e351-104">Sie können den Zugriff auf Microsoft Dynamics CRM Online von iOS- und Android-Geräten mithilfe des bedingten Zugriffs von Microsoft Intune steuern.</span><span class="sxs-lookup"><span data-stu-id="4e351-104">You can control access to Microsoft Dynamics CRM Online from iOS and Android devices by using Microsoft Intune conditional access.</span></span>  <span data-ttu-id="4e351-105">Der bedingte Zugriff in Intune besteht aus zwei Komponenten:</span><span class="sxs-lookup"><span data-stu-id="4e351-105">Intune conditional access has two components:</span></span>
* <span data-ttu-id="4e351-106">Einer [Gerätekompatibilitätsrichtlinie](introduction-to-device-compliance-policies-in-microsoft-intune.md), die das Gerät erfüllen muss, um als kompatibel bewertet zu werden</span><span class="sxs-lookup"><span data-stu-id="4e351-106">A [device compliance policy](introduction-to-device-compliance-policies-in-microsoft-intune.md) that the device must comply with in order to be considered compliant.</span></span>
* <span data-ttu-id="4e351-107">Einer [Richtlinie für bedingten Zugriff](restrict-access-to-email-and-o365-services-with-microsoft-intune.md), in der Sie die Bedingungen festlegen, die das Gerät erfüllen muss, um auf den Dienst zugreifen zu können</span><span class="sxs-lookup"><span data-stu-id="4e351-107">A [conditional access policy](restrict-access-to-email-and-o365-services-with-microsoft-intune.md) where you specify the conditions that the device must meet in order to access the service.</span></span>

<span data-ttu-id="4e351-108">Weitere Informationen zur Funktionsweise des bedingten Zugriffs finden Sie im Artikel [protect access to email, 0365, and other services (Schützen des Zugriffs auf E-Mail, Office 365 und andere Dienste mit Microsoft Intune)](restrict-access-to-email-and-o365-services-with-microsoft-intune.md).</span><span class="sxs-lookup"><span data-stu-id="4e351-108">To learn more about how conditional access works, read the [protect access to email, 0365, and other services](restrict-access-to-email-and-o365-services-with-microsoft-intune.md) article.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4e351-109">Zum Bereitstellen des bedingten Zugriffs müssen Sie über Abonnements für Intune und Azure Active Directory Premium verfügen, und Benutzer müssen für beide Produkte lizenziert sein.</span><span class="sxs-lookup"><span data-stu-id="4e351-109">To deploy conditional access, you must have subscriptions for Intune and Azure Active Directory Premium, and users must be licensed for both products.</span></span> <span data-ttu-id="4e351-110">Das **Abonnement für Enterprise Mobility + Security (EMS)** umfasst sowohl das Intune- als auch das Azure Active Directory Premium-Abonnement.</span><span class="sxs-lookup"><span data-stu-id="4e351-110">The **Enterprise Mobility + Security (EMS) subscription** includes both Intune and Azure Active Directory Premium subscriptions.</span></span> <span data-ttu-id="4e351-111">Weitere Informationen finden Sie in der [Preisübersicht für Enterprise Mobility](https://www.microsoft.com/cloud-platform/enterprise-mobility-pricing).</span><span class="sxs-lookup"><span data-stu-id="4e351-111">For more details, see the [Enterprise Mobility pricing page](https://www.microsoft.com/cloud-platform/enterprise-mobility-pricing).</span></span> <span data-ttu-id="4e351-112">Falls Sie nicht über ein EMS-Abonnement verfügen, können Sie ein Abonnement für Azure Active Directory Premium erwerben.</span><span class="sxs-lookup"><span data-stu-id="4e351-112">If you don't have the EMS subscription, you can get a subscription for Azure Active Directory Premium.</span></span> <span data-ttu-id="4e351-113">Weitere Informationen finden Sie in der [Preisübersicht für Azure Active Directory](https://azure.microsoft.com/pricing/details/active-directory/).</span><span class="sxs-lookup"><span data-stu-id="4e351-113">See the [Azure Active Directory pricing page](https://azure.microsoft.com/pricing/details/active-directory/).</span></span>

<span data-ttu-id="4e351-114">Wenn ein Zielbenutzer versucht, die Dynamics CRM-App auf seinem Gerät zu verwenden, erfolgt folgende Auswertung:</span><span class="sxs-lookup"><span data-stu-id="4e351-114">When a targeted user attempts to use the Dynamics CRM app on their device, the following evaluation occurs:</span></span>

![Das Diagramm veranschaulicht die Entscheidungspunkte, mit denen ermittelt wird, ob ein Gerät Zugriff auf einen Dienst erhält oder blockiert wird](../media/mdm-ca-dynamics-crm-flow-diagram.png)

<span data-ttu-id="4e351-116">Für das Gerät, das auf Dynamics CRM zugreift, gelten die folgenden Anforderungen:</span><span class="sxs-lookup"><span data-stu-id="4e351-116">The device that needs access to Dynamics CRM Online must be:</span></span>
* <span data-ttu-id="4e351-117">Es muss sich um ein **Android**- oder **iOS**-Gerät handeln.</span><span class="sxs-lookup"><span data-stu-id="4e351-117">An **Android** or **iOS** device.</span></span>
* <span data-ttu-id="4e351-118">Es muss bei Intune **registriert** sein.</span><span class="sxs-lookup"><span data-stu-id="4e351-118">**Enrolled** with Intune.</span></span>
* <span data-ttu-id="4e351-119">Es muss mit allen bereitgestellten Konformitätsrichtlinien **kompatibel** sein.</span><span class="sxs-lookup"><span data-stu-id="4e351-119">**Compliant** with any deployed Intune compliance policies.</span></span>

<span data-ttu-id="4e351-120">Der Gerätestatus wird in Azure Active Directory gespeichert, wo der Zugriff entsprechend den von Ihnen angegebenen Bedingungen gewährt oder blockiert wird.</span><span class="sxs-lookup"><span data-stu-id="4e351-120">The device state is stored in Azure Active Directory, which grants or blocks access based on the conditions that you specify.</span></span>

<span data-ttu-id="4e351-121">Wenn eine Bedingung nicht erfüllt wird, erhält der Benutzer bei der Anmeldung die folgenden Meldungen:</span><span class="sxs-lookup"><span data-stu-id="4e351-121">If a condition is not met, the user is presented with one of the following messages when they sign in:</span></span>
* <span data-ttu-id="4e351-122">Wenn das Gerät nicht bei Intune oder in Azure Active Directory registriert ist, wird eine Meldung mit Anweisungen zum Installieren der Unternehmensportal-App und zum Registrieren des Geräts angezeigt.</span><span class="sxs-lookup"><span data-stu-id="4e351-122">If the device is not enrolled with Intune or is not registered in Azure Active Directory, a message is displayed with instructions about how to install the Company Portal app and enroll.</span></span>
* <span data-ttu-id="4e351-123">Falls das Gerät nicht kompatibel ist, wird eine Meldung angezeigt, die den Benutzer zum Microsoft Intune-Unternehmensportal oder der Unternehmensportal-App weiterleitet. Hier findet er Informationen zum Problem und zu dessen Lösung.</span><span class="sxs-lookup"><span data-stu-id="4e351-123">If the device is not compliant, a message is displayed that directs the user to the Microsoft Intune Company Portal website or Company Portal app, where they can find information about the problem and how to remediate it.</span></span>

## <a name="configure-conditional-access-for-dynamics-crm-online"></a><span data-ttu-id="4e351-124">Konfigurieren des bedingten Zugriffs für Dynamics CRM Online</span><span class="sxs-lookup"><span data-stu-id="4e351-124">Configure conditional access for Dynamics CRM Online</span></span>  
### <a name="step-1-configure-active-directory-security-groups"></a><span data-ttu-id="4e351-125">Schritt 1: Konfigurieren von Active Directory-Sicherheitsgruppen</span><span class="sxs-lookup"><span data-stu-id="4e351-125">Step 1: Configure Active Directory security groups</span></span>

<span data-ttu-id="4e351-126">Bevor Sie beginnen, konfigurieren Sie Azure Active Directory-Sicherheitsgruppen für die bedingte Zugriffsrichtlinien.</span><span class="sxs-lookup"><span data-stu-id="4e351-126">Before you start, configure Azure Active Directory security groups for the conditional access policy.</span></span> <span data-ttu-id="4e351-127">Sie können diese Gruppen im **Office 365 Admin Center** konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="4e351-127">You can configure these groups in the **Office 365 admin center**.</span></span> <span data-ttu-id="4e351-128">Sie verwenden diese Gruppen, um die Richtlinie auf Benutzer anzuwenden oder Benutzer von der Richtlinie auszunehmen.</span><span class="sxs-lookup"><span data-stu-id="4e351-128">You use these groups to target or exempt users from the policy.</span></span> <span data-ttu-id="4e351-129">Bei Benutzern, für die eine Richtlinie gelten soll, muss jedes von ihnen verwendete Gerät die Richtlinie erfüllen, damit sie auf Ressourcen zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="4e351-129">When a user is targeted by a policy, each device they use must be compliant in order to access resources.</span></span>

<span data-ttu-id="4e351-130">Sie können zwei Gruppentypen für die Verwendung mit der Dynamics CRM-Richtlinie angeben:</span><span class="sxs-lookup"><span data-stu-id="4e351-130">You can specify two group types to use for the Dynamics CRM policy:</span></span>
* <span data-ttu-id="4e351-131">**Zielgruppen**.</span><span class="sxs-lookup"><span data-stu-id="4e351-131">**Targeted groups**.</span></span> <span data-ttu-id="4e351-132">Gruppen von Benutzern, für die die Richtlinie gilt.</span><span class="sxs-lookup"><span data-stu-id="4e351-132">Contains groups of users that the policy applies to.</span></span>
* <span data-ttu-id="4e351-133">**Ausgenommene Gruppen**.</span><span class="sxs-lookup"><span data-stu-id="4e351-133">**Exempted groups**.</span></span> <span data-ttu-id="4e351-134">Gruppen von Benutzern, die von der Richtlinie ausgenommen sind.</span><span class="sxs-lookup"><span data-stu-id="4e351-134">Contains groups of users that are exempt from the policy.</span></span>

<span data-ttu-id="4e351-135">Benutzer, die in beiden Gruppen enthalten sind, werden von der Richtlinie ausgenommen.</span><span class="sxs-lookup"><span data-stu-id="4e351-135">If a user is in both groups, they are exempt from the policy.</span></span>

### <a name="step-2-configure-and-deploy-a-compliance-policy"></a><span data-ttu-id="4e351-136">Schritt 2: Konfigurieren und Bereitstellen einer Konformitätsrichtlinie</span><span class="sxs-lookup"><span data-stu-id="4e351-136">Step 2: Configure and deploy a compliance policy</span></span>
<span data-ttu-id="4e351-137">Sie müssen eine Kompatibilitätsrichtlinie [erstellen](create-a-device-compliance-policy-in-microsoft-intune.md) und auf allen Geräten [bereitstellen](deploy-and-monitor-a-device-compliance-policy-in-microsoft-intune.md), die von der Richtlinie betroffen sind.</span><span class="sxs-lookup"><span data-stu-id="4e351-137">[Create](create-a-device-compliance-policy-in-microsoft-intune.md) a compliance policy and [deploy](deploy-and-monitor-a-device-compliance-policy-in-microsoft-intune.md) it to all devices that will be affected by the policy.</span></span> <span data-ttu-id="4e351-138">Dies sind alle Geräte, die von den Benutzern in den Zielgruppen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="4e351-138">These are all the devices that are used by the users in the Targeted groups.</span></span>

> [!NOTE]
> <span data-ttu-id="4e351-139">Kompatibilitätsrichtlinien werden für Intune-Gruppen bereitgestellt, Richtlinien für bedingten Zugriff dagegen werden auf Azure Active Directory-Sicherheitsgruppen angewendet.</span><span class="sxs-lookup"><span data-stu-id="4e351-139">While compliance policies are deployed to Intune groups, conditional access policies are targeted to Azure Active Directory security groups.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="4e351-140">Wenn Sie keine Konformitätsrichtlinie bereitgestellt haben, werden die Geräte als konform ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="4e351-140">If you have not deployed a compliance policy, the devices will be treated as compliant.</span></span>

<span data-ttu-id="4e351-141">Fahren Sie mit Schritt 3 fort.</span><span class="sxs-lookup"><span data-stu-id="4e351-141">When you are ready, continue to Step 3.</span></span>
### <a name="step-3-configure-the-dynamics-crm-policy"></a><span data-ttu-id="4e351-142">Schritt 3: Konfigurieren der Dynamics CRM-Richtlinie</span><span class="sxs-lookup"><span data-stu-id="4e351-142">Step 3: Configure the Dynamics CRM policy</span></span>
<span data-ttu-id="4e351-143">Anschließend konfigurieren Sie die Richtlinie so, dass nur verwaltete und kompatible Geräte auf Dynamics CRM zugreifen dürfen.</span><span class="sxs-lookup"><span data-stu-id="4e351-143">Next, configure the policy to require that only managed and compliant devices can access Dynamics CRM.</span></span> <span data-ttu-id="4e351-144">Diese Richtlinie wird in Azure Active Directory gespeichert.</span><span class="sxs-lookup"><span data-stu-id="4e351-144">This policy will be stored in Azure Active Directory.</span></span>

1. <span data-ttu-id="4e351-145">Wählen Sie in der Intune-Verwaltungskonsole **Richtlinie > bedingter Zugriff > Dynamics CRM Online-Richtlinie** aus.</span><span class="sxs-lookup"><span data-stu-id="4e351-145">In the Intune administration console, choose **Policy > Conditional Access > Dynamics CRM Online Policy**.</span></span>

   ![Screenshot der Seite mit der Dynamics CRM Online-Richtlinie für den bedingten Zugriff](../media/mdm-ca-dynamics-crm-policy-configuration.png)

2. <span data-ttu-id="4e351-147">Wählen Sie **Richtlinie für bedingten Zugriff aktivieren** aus.</span><span class="sxs-lookup"><span data-stu-id="4e351-147">Choose the **Enable conditional access** policy.</span></span>
3. <span data-ttu-id="4e351-148">Unter **Anwendungszugriff** können Sie optional eine Richtlinie für bedingten Zugriff auf Folgendes anwenden:</span><span class="sxs-lookup"><span data-stu-id="4e351-148">Under **Application access**, you can choose to apply conditional access policy to:</span></span>
   * <span data-ttu-id="4e351-149">**iOS**</span><span class="sxs-lookup"><span data-stu-id="4e351-149">**iOS**</span></span>
   * <span data-ttu-id="4e351-150">**Android**</span><span class="sxs-lookup"><span data-stu-id="4e351-150">**Android**</span></span>
4. <span data-ttu-id="4e351-151">Wählen Sie unter **Zielgruppen** **Ändern** aus, um die Azure Active Directory-Sicherheitsgruppen auszuwählen, für die die Richtlinie gelten soll.</span><span class="sxs-lookup"><span data-stu-id="4e351-151">Under **Targeted Groups**, choose **Modify** to select the Azure Active Directory security groups that the policy will apply to.</span></span> <span data-ttu-id="4e351-152">Sie können dies für alle Benutzer oder nur für eine ausgewählte Benutzergruppe festlegen.</span><span class="sxs-lookup"><span data-stu-id="4e351-152">You can choose to target this to all users or just a select group of users.</span></span>
5. <span data-ttu-id="4e351-153">Wählen Sie unter **Exempted Groups** (Ausgenommene Gruppen) optional **Ändern**, um die Azure Active Directory-Sicherheitsgruppen auszuwählen, die von dieser Richtlinie ausgenommen werden.</span><span class="sxs-lookup"><span data-stu-id="4e351-153">Under **Exempted Groups**, optionally, choose **Modify** to select the Azure Active Directory security groups that are exempt from this policy.</span></span>
6. <span data-ttu-id="4e351-154">Wählen Sie abschließend **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="4e351-154">When you are done, choose **Save**.</span></span>

<span data-ttu-id="4e351-155">Sie haben den bedingten Zugriff für Dynamics CRM konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="4e351-155">You have now configured conditional access for Dynamics CRM.</span></span> <span data-ttu-id="4e351-156">Die Richtlinie für bedingten Zugriff wird sofort wirksam und muss nicht explizit bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="4e351-156">You do not have to deploy the conditional access policy—it takes effect immediately.</span></span>
##  <a name="monitor-the-compliance-and-conditional-access-policies"></a><span data-ttu-id="4e351-157">Überwachen der Richtlinien für Konformität und bedingten Zugriff</span><span class="sxs-lookup"><span data-stu-id="4e351-157">Monitor the compliance and conditional access policies</span></span>

<span data-ttu-id="4e351-158">Im Arbeitsbereich **Gruppen** können Sie den Status beim bedingten Zugriff Ihrer Geräte anzeigen.</span><span class="sxs-lookup"><span data-stu-id="4e351-158">In the **Groups** workspace, you can view the conditional access status of your devices.</span></span>

<span data-ttu-id="4e351-159">Wählen Sie eine beliebige Gruppe von Mobilgeräten und dann auf der Registerkarte **Geräte** einen der folgenden **Filter** aus:</span><span class="sxs-lookup"><span data-stu-id="4e351-159">Choose any mobile device group and then, on the **Devices** tab, choose one of the following **Filters**:</span></span>
* <span data-ttu-id="4e351-160">**Geräte, die nicht bei AAD registriert sind**.</span><span class="sxs-lookup"><span data-stu-id="4e351-160">**Devices that are not registered with AAD**.</span></span> <span data-ttu-id="4e351-161">Diesen Geräten wird der Zugriff auf Dynamics CRM verweigert.</span><span class="sxs-lookup"><span data-stu-id="4e351-161">These devices are blocked from Dynamics CRM.</span></span>
* <span data-ttu-id="4e351-162">**Geräte, die nicht kompatibel sind**.</span><span class="sxs-lookup"><span data-stu-id="4e351-162">**Devices that are not compliant**.</span></span> <span data-ttu-id="4e351-163">Diesen Geräten wird der Zugriff auf Dynamics CRM verweigert.</span><span class="sxs-lookup"><span data-stu-id="4e351-163">These devices are blocked from Dynamics CRM.</span></span>
* <span data-ttu-id="4e351-164">**Geräte, die bei AAD registriert und kompatibel sind**.</span><span class="sxs-lookup"><span data-stu-id="4e351-164">**Devices that are registered with AAD and compliant**.</span></span> <span data-ttu-id="4e351-165">Diese Geräte können auf Dynamics CRM zugreifen.</span><span class="sxs-lookup"><span data-stu-id="4e351-165">These devices can access Dynamics CRM.</span></span>

##  <a name="next-steps"></a><span data-ttu-id="4e351-166">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="4e351-166">Next steps</span></span>
* [<span data-ttu-id="4e351-167">Protect access to Exchange Online (Beschränken des Zugriffs auf Exchange Online)</span><span class="sxs-lookup"><span data-stu-id="4e351-167">Protect access to Exchange Online</span></span>](restrict-access-to-exchange-online-with-microsoft-intune.md)

* [<span data-ttu-id="4e351-168">Protect access to Exchange on-premises (Schützen des Zugriffs auf Exchange lokal)</span><span class="sxs-lookup"><span data-stu-id="4e351-168">Protect access to Exchange on-premises</span></span>](restrict-access-to-exchange-onpremises-with-microsoft-intune.md)
* [<span data-ttu-id="4e351-169">Protect access to SharePoint Online (Schützen des Zugriffs auf SharePoint Online)</span><span class="sxs-lookup"><span data-stu-id="4e351-169">Protect access to SharePoint Online</span></span>](restrict-access-to-sharepoint-online-with-microsoft-intune.md)

* [<span data-ttu-id="4e351-170">Protect access to Skype for Business Online (Schützen des Zugriffs auf Skype for Business Online)</span><span class="sxs-lookup"><span data-stu-id="4e351-170">Protect access to Skype for Business Online</span></span>](restrict-access-to-skype-for-business-online-with-microsoft-intune.md)
