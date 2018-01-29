---
title: "Schützen von Skype for Business Online"
description: "Schützen und steuern Sie den Zugriff auf Skype for Business Online unter Verwendung von bedingtem Zugriff."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 01/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 1b2d7125-f63f-43cf-ac1e-94fbedf2a7e8
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: chrisgre
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: d9d912cc0a2d8f815e046d888fc8878a8703c514
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2018
---
# <a name="protect-access-to-skype-for-business-online-with-microsoft-intune"></a><span data-ttu-id="12902-103">Schützen des Zugriffs auf Skype for Business Online mit Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="12902-103">Protect access to Skype for Business Online with Microsoft Intune</span></span>

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="12902-104">Sie können die Richtlinie für bedingten Zugriff für **Skype for Business Online** zum Steuern des Zugriffs auf Skype for Business Online verwenden.</span><span class="sxs-lookup"><span data-stu-id="12902-104">You can use a conditional access policy for **Skype for Business Online** to control access to Skype for Business Online.</span></span>
<span data-ttu-id="12902-105">Der bedingte Zugriff besteht aus zwei Komponenten:</span><span class="sxs-lookup"><span data-stu-id="12902-105">Conditional access has two components:</span></span>
- <span data-ttu-id="12902-106">Einer Gerätekompatibilitätsrichtlinie, die das Gerät erfüllen muss, um als kompatibel bewertet zu werden</span><span class="sxs-lookup"><span data-stu-id="12902-106">A device compliance policy that the device must comply with in order to be considered compliant.</span></span>
- <span data-ttu-id="12902-107">Einer Richtlinie für bedingten Zugriff, in der Sie die Bedingungen festlegen, die das Gerät erfüllen muss, damit Sie auf den Dienst zugreifen können</span><span class="sxs-lookup"><span data-stu-id="12902-107">A conditional access policy where you specify the conditions that the device must meet in order for you to access the service.</span></span>
<span data-ttu-id="12902-108">Weitere Informationen zur Funktionsweise des bedingten Zugriffs finden Sie im Artikel [Protect access to email and O365 services (Schützen des Zugriffs auf E-Mail- und Office 365-Dienste)](restrict-access-to-email-and-o365-services-with-microsoft-intune.md).</span><span class="sxs-lookup"><span data-stu-id="12902-108">To learn more about how conditional access works, read the [Protect access to email and O365 services](restrict-access-to-email-and-o365-services-with-microsoft-intune.md) article.</span></span>

<span data-ttu-id="12902-109">Wenn ein Benutzer, für den der bedingte Zugriff gilt, versucht, Skype for Business Online auf seinem Gerät zu verwenden, erfolgt folgende Auswertung:</span><span class="sxs-lookup"><span data-stu-id="12902-109">When a targeted user attempts to use Skype for Business Online on their device, the following evaluation occurs:</span></span>

![Diagramm mit den Entscheidungspunkten, die bestimmen, ob der Zugriff eines Geräts auf Skype for Business Online zugelassen oder blockiert wird](../media/ConditionalAccess_SkypeforBusiness.png)

<span data-ttu-id="12902-111">**Bevor** Sie eine bedingte Zugriffsrichtlinie für Skype for Business Online konfigurieren, müssen folgende Voraussetzungen erfüllt sein:</span><span class="sxs-lookup"><span data-stu-id="12902-111">**Before** configuring a conditional access policy for Skype for Business Online, you must:</span></span>
- <span data-ttu-id="12902-112">Sie müssen über ein **Skype for Business Online-Abonnement** verfügen und Benutzern die Skype for Business Online-Lizenz zuweisen.</span><span class="sxs-lookup"><span data-stu-id="12902-112">Have a **Skype for Business Online subscription** and assign the Skype for Business Online license to users.</span></span>
- <span data-ttu-id="12902-113">Sie müssen über ein **Enterprise Mobility + Security- (EMS)** oder **Azure Active Directory (Azure AD) Premium-Abonnement** verfügen, und Benutzer müssen für EMS oder Azure AD lizenziert sein.</span><span class="sxs-lookup"><span data-stu-id="12902-113">Have an **Enterprise Mobility + Security (EMS) subscription** or an **Azure Active Directory (Azure AD) Premium subscription**, and have users be licensed for EMS or Azure AD.</span></span> <span data-ttu-id="12902-114">Weitere Informationen finden Sie in der [Preisübersicht für Enterprise Mobility](https://www.microsoft.com/cloud-platform/enterprise-mobility-pricing) oder der [Preisübersicht für Azure Active Directory](https://azure.microsoft.com/pricing/details/active-directory/).</span><span class="sxs-lookup"><span data-stu-id="12902-114">For more details, see [Enterprise Mobility pricing](https://www.microsoft.com/cloud-platform/enterprise-mobility-pricing) or [Azure Active Directory pricing](https://azure.microsoft.com/pricing/details/active-directory/).</span></span>

-   <span data-ttu-id="12902-115">[Aktivieren Sie die moderne Authentifizierung](/intune-classic/deploy-use/restrict-access-to-skype-for-business-online-with-microsoft-intune) für Skype for Business Online.</span><span class="sxs-lookup"><span data-stu-id="12902-115">[Enable modern authentication](/intune-classic/deploy-use/restrict-access-to-skype-for-business-online-with-microsoft-intune) for Skype for Business Online.</span></span>
-  <span data-ttu-id="12902-116">All Ihre Benutzer müssen **Skype for Business Online** verwenden.</span><span class="sxs-lookup"><span data-stu-id="12902-116">Have all your users using **Skype for Business Online**.</span></span> <span data-ttu-id="12902-117">Wenn in Ihrer Bereitstellung sowohl Skype for Business Online als auch lokales Skype for Business verwendet werden, wird die Richtlinie für bedingten Zugriff nicht auf Benutzer angewendet.</span><span class="sxs-lookup"><span data-stu-id="12902-117">If you have a deployment with both Skype for Business Online and Skype for Business on-premises, the conditional access policy will not be applied to users.</span></span>

<span data-ttu-id="12902-118">Für das Gerät, dass Zugriff auf Skype for Business Online benötigt, müssen folgende Voraussetzungen erfüllt sein:</span><span class="sxs-lookup"><span data-stu-id="12902-118">The device that needs access to Skype for Business Online must:</span></span>

-   <span data-ttu-id="12902-119">Es muss sich um ein **Android**- oder **iOS**-Gerät handeln.</span><span class="sxs-lookup"><span data-stu-id="12902-119">Be an **Android** or **iOS** device.</span></span>

-   <span data-ttu-id="12902-120">Es muss bei Intune **registriert** sein.</span><span class="sxs-lookup"><span data-stu-id="12902-120">Be **enrolled** with Intune.</span></span>

-   <span data-ttu-id="12902-121">Es muss mit allen bereitgestellten Konformitätsrichtlinien **konform** sein.</span><span class="sxs-lookup"><span data-stu-id="12902-121">Be **compliant** with any deployed Intune compliance policies.</span></span>


<span data-ttu-id="12902-122">Der Gerätestatus wird in Azure Active Directory gespeichert, wo der Zugriff entsprechend den von Ihnen angegebenen Bedingungen gewährt oder blockiert wird.</span><span class="sxs-lookup"><span data-stu-id="12902-122">The device state is stored in Azure Active Directory, which grants or blocks access based on the conditions that you specify.</span></span>

<span data-ttu-id="12902-123">Wenn eine Bedingung nicht erfüllt wird, erhält der Benutzer bei der Anmeldung die folgenden Meldungen:</span><span class="sxs-lookup"><span data-stu-id="12902-123">If a condition is not met, the user is presented with one of the following messages when they sign in:</span></span>

-   <span data-ttu-id="12902-124">Wenn das Gerät nicht bei Intune oder in Azure Active Directory registriert ist, wird eine Meldung mit Anweisungen zum Installieren der Unternehmensportal-App und zum Registrieren des Geräts angezeigt.</span><span class="sxs-lookup"><span data-stu-id="12902-124">If the device is not enrolled with Intune or is not registered in Azure Active Directory, a message is displayed with instructions about how to install the Company Portal app and enroll.</span></span>

-   <span data-ttu-id="12902-125">Wenn das Gerät nicht konform ist, wird eine Meldung angezeigt, die den Benutzer zur Intune-Unternehmensportalwebsite oder zur Unternehmensportal-App weiterleitet. Dort findet der Benutzer Informationen zum Problem und dessen Lösung.</span><span class="sxs-lookup"><span data-stu-id="12902-125">If the device is not compliant, a message is displayed that directs the user to the Intune Company Portal website or Company Portal app, where they can find information about the problem and how to fix it.</span></span>

## <a name="configure-conditional-access-for-skype-for-business-online"></a><span data-ttu-id="12902-126">Konfigurieren des bedingten Zugriffs für Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="12902-126">Configure conditional access for Skype for Business Online</span></span>

### <a name="step-1-configure-azure-active-directory-security-groups"></a><span data-ttu-id="12902-127">Schritt 1: Konfigurieren von Azure Active Directory-Sicherheitsgruppen</span><span class="sxs-lookup"><span data-stu-id="12902-127">Step 1: Configure Azure Active Directory security groups</span></span>
<span data-ttu-id="12902-128">Bevor Sie beginnen, konfigurieren Sie Azure Active Directory-Sicherheitsgruppen für die bedingte Zugriffsrichtlinien.</span><span class="sxs-lookup"><span data-stu-id="12902-128">Before you start, configure Azure Active Directory security groups for the conditional access policy.</span></span> <span data-ttu-id="12902-129">Sie können diese Gruppen im **Office 365 Admin Center** konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="12902-129">You can configure these groups in the **Office 365 admin center**.</span></span> <span data-ttu-id="12902-130">Diese Gruppen werden verwendet, um die Richtlinie auf Benutzer anzuwenden oder Benutzer von der Richtlinie auszunehmen.</span><span class="sxs-lookup"><span data-stu-id="12902-130">These groups will be used to target or exempt users from the policy.</span></span> <span data-ttu-id="12902-131">Bei Benutzern, für die die Richtlinie gelten soll, muss jedes von ihnen verwendete Gerät die Richtlinie erfüllen, damit sie auf Ressourcen zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="12902-131">When a user is targeted by the policy, each device they use must be compliant in order to access resources.</span></span>

<span data-ttu-id="12902-132">Sie können zwei Gruppen angeben, die für die Skype for Business-Richtlinie verwendet werden können:</span><span class="sxs-lookup"><span data-stu-id="12902-132">You can specify two group types to use for the Skype for Business policy:</span></span>

-   <span data-ttu-id="12902-133">**Zielgruppen**: Gruppen von Benutzern, für die die Richtlinie gilt.</span><span class="sxs-lookup"><span data-stu-id="12902-133">**Targeted groups**: Contains groups of users that the policy applies to.</span></span>

-   <span data-ttu-id="12902-134">**Ausgenommene Gruppen**: Gruppen von Benutzern, die von der Richtlinie ausgenommen sind.</span><span class="sxs-lookup"><span data-stu-id="12902-134">**Exempted groups**: Contains groups of users that are exempt from the policy.</span></span>

<span data-ttu-id="12902-135">Benutzer, die in beiden Gruppen enthalten sind, werden von der Richtlinie ausgenommen.</span><span class="sxs-lookup"><span data-stu-id="12902-135">If a user is in both groups, they will be exempt from the policy.</span></span>

### <a name="step-2-configure-and-deploy-a-compliance-policy"></a><span data-ttu-id="12902-136">Schritt 2: Konfigurieren und Bereitstellen einer Konformitätsrichtlinie</span><span class="sxs-lookup"><span data-stu-id="12902-136">Step 2: Configure and deploy a compliance policy</span></span>
<span data-ttu-id="12902-137">Sie müssen eine Kompatibilitätsrichtlinie [erstellen](create-a-device-compliance-policy-in-microsoft-intune.md) und auf allen Geräten [bereitstellen](deploy-and-monitor-a-device-compliance-policy-in-microsoft-intune.md), die von der Richtlinie betroffen sind.</span><span class="sxs-lookup"><span data-stu-id="12902-137">[Create](create-a-device-compliance-policy-in-microsoft-intune.md) and [deploy](deploy-and-monitor-a-device-compliance-policy-in-microsoft-intune.md) a compliance policy to all devices that will be affected by the policy.</span></span> <span data-ttu-id="12902-138">Dies sind alle Geräte, die von den Benutzern in den **Zielgruppen** verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="12902-138">These will be all the devices that are used by the users in the **Targeted groups**.</span></span>

> [!NOTE]
> <span data-ttu-id="12902-139">Kompatibilitätsrichtlinien werden für Intune-Gruppen bereitgestellt, Richtlinien für bedingten Zugriff dagegen werden auf Azure Active Directory-Sicherheitsgruppen angewendet.</span><span class="sxs-lookup"><span data-stu-id="12902-139">While compliance policies are deployed to Intune groups, conditional access policies are targeted to Azure Active Directory security groups.</span></span>


> [!IMPORTANT]
> <span data-ttu-id="12902-140">Wenn Sie keine Kompatibilitätsrichtlinie bereitgestellt haben, werden die Geräte als kompatibel ausgewertet.</span><span class="sxs-lookup"><span data-stu-id="12902-140">If you haven't deployed a compliance policy, the devices will be treated as compliant.</span></span>

<span data-ttu-id="12902-141">Fahren Sie anschließend mit **Schritt 3** fort.</span><span class="sxs-lookup"><span data-stu-id="12902-141">When you're ready, continue to **Step 3**.</span></span>

### <a name="step-3-configure-the-skype-for-business-online-policy"></a><span data-ttu-id="12902-142">Schritt 3: Konfigurieren der Skype for Business Online-Richtlinie</span><span class="sxs-lookup"><span data-stu-id="12902-142">Step 3: Configure the Skype for Business Online policy</span></span>
<span data-ttu-id="12902-143">Jetzt konfigurieren Sie die Richtlinie so, dass nur verwaltete und kompatible Geräte auf Skype for Business Online zugreifen dürfen.</span><span class="sxs-lookup"><span data-stu-id="12902-143">Next, configure the policy to require that only managed and compliant devices can access Skype for Business Online.</span></span> <span data-ttu-id="12902-144">Diese Richtlinie wird in Azure Active Directory gespeichert.</span><span class="sxs-lookup"><span data-stu-id="12902-144">This policy will be stored in Azure Active Directory.</span></span>

1. <span data-ttu-id="12902-145">Wählen Sie in der [Microsoft Intune-Verwaltungskonsole](https://manage.microsoft.com) die Optionen **Richtlinie** > **Bedingter Zugriff** > **Skype for Business Online-Richtlinie** aus.</span><span class="sxs-lookup"><span data-stu-id="12902-145">In the [Microsoft Intune administration console](https://manage.microsoft.com), choose **Policy** > **Conditional Access** > **Skype for Business Online Policy**.</span></span>

   ![Screenshot der Seite mit der Skype for Business Online-Richtlinie für bedingten Zugriff](./media/conditional_access_SFBPolicy.png)

2. <span data-ttu-id="12902-147">Wählen Sie **Richtlinie für bedingten Zugriff aktivieren** aus.</span><span class="sxs-lookup"><span data-stu-id="12902-147">Choose **Enable conditional access policy**.</span></span>

3. <span data-ttu-id="12902-148">Unter **Anwendungszugriff** können Sie optional eine Richtlinie für bedingten Zugriff auf Folgendes anwenden:</span><span class="sxs-lookup"><span data-stu-id="12902-148">Under **Application access**, you can choose to apply conditional access policy to:</span></span>

   -   <span data-ttu-id="12902-149">**iOS**</span><span class="sxs-lookup"><span data-stu-id="12902-149">**iOS**</span></span>

   -   <span data-ttu-id="12902-150">**Android**</span><span class="sxs-lookup"><span data-stu-id="12902-150">**Android**</span></span>

4. <span data-ttu-id="12902-151">Wählen Sie unter **Zielgruppen** **Ändern** aus, um die Azure Active Directory-Sicherheitsgruppen auszuwählen, für die die Richtlinie gelten soll.</span><span class="sxs-lookup"><span data-stu-id="12902-151">Under **Targeted Groups**, choose **Modify** to select the Azure Active Directory security groups that the policy will apply to.</span></span> <span data-ttu-id="12902-152">Sie können dies für alle Benutzer oder nur für eine ausgewählte Benutzergruppe festlegen.</span><span class="sxs-lookup"><span data-stu-id="12902-152">You can choose to target this to all users or just a select group of users.</span></span>

5. <span data-ttu-id="12902-153">Wählen Sie unter **Exempted Groups** (Ausgenommene Gruppen) optional **Ändern**, um die Azure Active Directory-Sicherheitsgruppen auszuwählen, die von dieser Richtlinie ausgenommen werden.</span><span class="sxs-lookup"><span data-stu-id="12902-153">Under **Exempted Groups**, optionally, choose **Modify** to select the Azure Active Directory security groups that are exempt from this policy.</span></span>

6. <span data-ttu-id="12902-154">Wenn Sie fertig sind, wählen Sie **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="12902-154">When you're done, choose **Save**.</span></span>

<span data-ttu-id="12902-155">Sie haben jetzt den bedingten Zugriff für Skype for Business Online konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="12902-155">You have now configured conditional access for Skype for Business Online.</span></span> <span data-ttu-id="12902-156">Die Richtlinie für bedingten Zugriff wird sofort wirksam und muss nicht explizit bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="12902-156">You don't have to deploy the conditional access policy—it takes effect immediately.</span></span>


## <a name="monitor-the-compliance-and-conditional-access-policies"></a><span data-ttu-id="12902-157">Überwachen der Richtlinien für Konformität und bedingten Zugriff</span><span class="sxs-lookup"><span data-stu-id="12902-157">Monitor the compliance and conditional access policies</span></span>
<span data-ttu-id="12902-158">Im Arbeitsbereich **Gruppen** können Sie den Status beim bedingten Zugriff Ihrer Geräte anzeigen.</span><span class="sxs-lookup"><span data-stu-id="12902-158">In the **Groups** workspace, you can view the conditional access status of your devices.</span></span>

<span data-ttu-id="12902-159">Wählen Sie eine beliebige Gruppe von Mobilgeräten aus.</span><span class="sxs-lookup"><span data-stu-id="12902-159">Select any mobile device group.</span></span> <span data-ttu-id="12902-160">Wählen Sie dann auf der Registerkarte **Geräte** einen der folgenden **Filter** aus:</span><span class="sxs-lookup"><span data-stu-id="12902-160">Then, on the **Devices** tab, choose one of the following **Filters**:</span></span>

* <span data-ttu-id="12902-161">**Geräte, die nicht bei AAD registriert sind**: Diese Geräte werden für Skype for Business Online blockiert.</span><span class="sxs-lookup"><span data-stu-id="12902-161">**Devices that are not registered with AAD**: These devices are blocked from Skype for Business Online.</span></span>

* <span data-ttu-id="12902-162">**Geräte, die nicht kompatibel sind**: Diese Geräte werden für Skype for Business Online blockiert.</span><span class="sxs-lookup"><span data-stu-id="12902-162">**Devices that are not compliant**: These devices are blocked from Skype for Business Online.</span></span>

* <span data-ttu-id="12902-163">**Geräte, die bei AAD registriert und kompatibel sind**: Diese Geräte können auf Skype for Business Online zugreifen.</span><span class="sxs-lookup"><span data-stu-id="12902-163">**Devices that are registered with AAD and compliant**: These devices can access Skype for Business Online.</span></span>
