---
title: "Schützen von E-Mail und Office 365"
description: "In diesem Thema wird beschrieben, wie Sie bedingten Zugriff verwenden können, damit nur kompatible Geräte auf Unternehmens-E-Mail und -daten in SharePoint Online und anderen Diensten zugreifen können."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 01/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c564d292-b83b-440d-bf08-3f5b299b7a5e
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: chrisgre
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: ba8b8517abbf778d787177ac170a3ce58ac7ec0a
ms.sourcegitcommit: e37e916e2bf14f092d3a767bc90d68c181d739fb
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/03/2018
---
# <a name="protect-access-to-email-office-365-and-other-services-with-microsoft-intune"></a><span data-ttu-id="dc042-103">Schützen des Zugriffs auf E-Mail, Office 365 und andere Dienste mit Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="dc042-103">Protect access to email, Office 365, and other services with Microsoft Intune</span></span>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="dc042-104">Sie können den Zugriff auf Ihre geschäftlichen E-Mails, Office 365-Dienste wie **lokales Exchange**, **Exchange Online**, **Exchange Online Dedicated**, **SharePoint Online**, **Skype for Business Online** und andere Dienste mithilfe des bedingten EMS-Zugriffs (Enterprise Mobility + Security) schützen.</span><span class="sxs-lookup"><span data-stu-id="dc042-104">You can protect access to your company email, Office 365 services like **Exchange On-premises**, **Exchange Online**, **Exchange Online Dedicated**,  **SharePoint Online**, **Skype for Business Online**, and other services by using Enterprise Mobility + Security (EMS) Conditional Access.</span></span> <span data-ttu-id="dc042-105">Mithilfe dieser Funktion können Sie sicherstellen, dass der Zugriff auf die E-Mail- und Office 365-Dienste Ihres Unternehmens auf Geräte beschränkt ist, die den von Ihnen festgelegten Regeln für den bedingten Zugriff entsprechen. Diese werden entweder in der Intune-Verwaltungskonsole oder im klassischen Azure-Portal festgelegt.</span><span class="sxs-lookup"><span data-stu-id="dc042-105">This capability allows you to make sure that access to your company email and Office 365 services is restricted to devices that are compliant with the conditional access rules that you set either in the Intune admin console, or Azure classic portal.</span></span>
## <a name="how-does-conditional-access-work"></a><span data-ttu-id="dc042-106">Funktionsweise des bedingten Zugriffs</span><span class="sxs-lookup"><span data-stu-id="dc042-106">How does conditional access work?</span></span>
<span data-ttu-id="dc042-107">Mit den Kompatibilitätsrichtlinieneinstellungen können Sie die Kompatibilität eines Geräts bewerten.</span><span class="sxs-lookup"><span data-stu-id="dc042-107">You can use compliance policy settings to evaluate the compliance of a device.</span></span> <span data-ttu-id="dc042-108">Eine Richtlinie für bedingten Zugriff verwendet diese Bewertung, um den Zugriff auf einen bestimmten Dienst zuzulassen oder zu beschränken.</span><span class="sxs-lookup"><span data-stu-id="dc042-108">A conditional access policy uses the evaluation to restrict or allow access to a specific service.</span></span> <span data-ttu-id="dc042-109">Wenn Sie eine Richtlinie für bedingten Zugriff in Kombination mit einer Gerätekompatibilitätsrichtlinie verwenden, erhalten nur kompatible Geräte Zugriff auf den Dienst.</span><span class="sxs-lookup"><span data-stu-id="dc042-109">When you use a conditional access policy in combination with a device compliance policy, only compliant devices are allowed to access the service.</span></span> <span data-ttu-id="dc042-110">Die Richtlinien für Konformität und bedingten Zugriff werden dem Benutzer bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="dc042-110">The compliance policy and the conditional access policy are deployed to the user.</span></span> <span data-ttu-id="dc042-111">Jedes Gerät, das der Benutzer zum Zugriff auf die Dienste verwendet, wird auf die Einhaltung der Richtlinien überprüft.</span><span class="sxs-lookup"><span data-stu-id="dc042-111">Any device that the user uses to access the services is checked for compliance with the policies.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="dc042-112">Bedenken Sie, dass für den Benutzer, der das Gerät verwendet, eine Kompatibilitätsrichtlinie bereitgestellt werden muss, damit das Gerät hinsichtlich der Kompatibilität bewertet werden kann.</span><span class="sxs-lookup"><span data-stu-id="dc042-112">Keep in mind that the user who is using the device must have a compliance policy that is deployed to them in order for the device to be evaluated for compliance.</span></span>
> <span data-ttu-id="dc042-113">Wenn keine Kompatibilitätsrichtlinie für den Benutzer bereitgestellt wird, wird das Gerät als kompatibel behandelt, und es werden keine Zugriffsbeschränkungen angewendet.</span><span class="sxs-lookup"><span data-stu-id="dc042-113">If no compliance policy is deployed to the user, the device is treated as compliant, and no access restrictions are applied.</span></span>

<span data-ttu-id="dc042-114">Wenn Geräte die in den Richtlinien festgelegten Bedingungen nicht erfüllen, erhält der Benutzer Anweisungen zum Registrieren des Geräts und zum Beheben des Problems, das die Konformität des Geräts verhindert.</span><span class="sxs-lookup"><span data-stu-id="dc042-114">When devices don't meet the conditions that are set in the policies, the end user is guided though the process of enrolling the device and fixing the issue that prevents the device from being compliant.</span></span>

<span data-ttu-id="dc042-115">Ein typischer Ablauf des bedingten Zugriffs:</span><span class="sxs-lookup"><span data-stu-id="dc042-115">A typical flow of conditional access:</span></span>

![Das Diagramm veranschaulicht die Entscheidungspunkte, mit denen ermittelt wird, ob ein Gerät Zugriff auf einen Dienst erhält oder blockiert wird](../media/ConditionalAccess4.png)

## <a name="setup-considerations"></a><span data-ttu-id="dc042-117">Überlegungen zur Einrichtung</span><span class="sxs-lookup"><span data-stu-id="dc042-117">Setup considerations</span></span>

### <a name="licensing"></a><span data-ttu-id="dc042-118">Lizenzierung</span><span class="sxs-lookup"><span data-stu-id="dc042-118">Licensing</span></span>

<span data-ttu-id="dc042-119">Microsoft Intune und Azure Active Directory Premium (Azure AD) arbeiten nahtlos zusammen, um mithilfe des bedingten EMS-Zugriffs mehrere Steuerungsebenen zu bieten. Wenn Sie Richtlinien für den bedingten Zugriff mithilfe von Intune bereitstellen möchten, benötigen Sie eine Lizenz für beide Produkte.</span><span class="sxs-lookup"><span data-stu-id="dc042-119">Microsoft Intune and Azure Active Directory (Azure AD) Premium work seamlessly together to provide multiple layers of control through EMS conditional access, if you want to deploy conditional access policies using Intune, you're required to have license for both products.</span></span>

<span data-ttu-id="dc042-120">**Azure AD Premium-Lizenzen** können als eigenständiger Dienst oder im Rahmen von Enterprise Agreement (zusammen mit Intune) erworben werden.</span><span class="sxs-lookup"><span data-stu-id="dc042-120">**Azure AD Premium licenses** can be purchased as a standalone service or can be purchased (along with Intune) as part of the Enterprise agreement.</span></span> <span data-ttu-id="dc042-121">Wenn Sie bedingte Zugriffsrichtlinien mit Intune bereitgestellt haben, stellen Sie sicher, dass Sie die entsprechenden Azure AD Premium- oder **EMS Lizenzen** bezogen haben.</span><span class="sxs-lookup"><span data-stu-id="dc042-121">If you have deployed conditional access policies with Intune, please ensure that you have obtained the proper Azure AD Premium or **EMS licenses**.</span></span>

- <span data-ttu-id="dc042-122">Weitere Informationen finden Sie in der [Preisübersicht für Enterprise Mobility](https://www.microsoft.com/cloud-platform/enterprise-mobility-pricing) oder der [Preisübersicht für Azure Active Directory](https://azure.microsoft.com/pricing/details/active-directory/).</span><span class="sxs-lookup"><span data-stu-id="dc042-122">Learn more about [Enterprise Mobility pricing page](https://www.microsoft.com/cloud-platform/enterprise-mobility-pricing) or the [Azure Active Directory pricing page](https://azure.microsoft.com/pricing/details/active-directory/).</span></span>

<span data-ttu-id="dc042-123">Stellen Sie darüber sicher, dass den Benutzern, für die Richtlinien für bedingten Zugriff gelten sollen, [Azure AD Premium- oder EMS-Lizenzen](/intune/licenses-assign) zugewiesen wurden.</span><span class="sxs-lookup"><span data-stu-id="dc042-123">Additionally, make sure the users you plan to apply conditional access policies are [assigned with the Azure AD Premium or EMS licenses](/intune/licenses-assign).</span></span>

### <a name="device-compliance-settings"></a><span data-ttu-id="dc042-124">Gerätekompatibilitätseinstellungen</span><span class="sxs-lookup"><span data-stu-id="dc042-124">Device compliance settings</span></span>

<span data-ttu-id="dc042-125">Um den bedingten Zugriff einzurichten, konfigurieren Sie eine Richtlinie für die Gerätekompatibilität und eine Richtlinie für bedingten Zugriff.</span><span class="sxs-lookup"><span data-stu-id="dc042-125">To set up conditional access, configure a device compliance policy and a conditional access policy.</span></span> <span data-ttu-id="dc042-126">Die Kompatibilitätsrichtlinie enthält Einstellungen wie z. B. Kennung, Verschlüsselung und Informationen dazu, ob ein Gerät per Jailbreak manipuliert wurde.</span><span class="sxs-lookup"><span data-stu-id="dc042-126">The compliance policy includes settings like passcode, encryption, and whether or not a device is jailbroken.</span></span> <span data-ttu-id="dc042-127">Das Gerät muss diesen Regeln entsprechen, um als kompatibel anerkannt zu werden.</span><span class="sxs-lookup"><span data-stu-id="dc042-127">The device must meet these rules in order to be considered compliant.</span></span>

- <span data-ttu-id="dc042-128">Erfahren Sie mehr über die [Richtlinie für die Gerätekompatibilität und ihre Funktionsweise](introduction-to-device-compliance-policies-in-microsoft-intune.md).</span><span class="sxs-lookup"><span data-stu-id="dc042-128">Learn more about [device compliance policy and how it works](introduction-to-device-compliance-policies-in-microsoft-intune.md).</span></span>

### <a name="conditional-access-policy"></a><span data-ttu-id="dc042-129">Richtlinie für bedingten Zugriff</span><span class="sxs-lookup"><span data-stu-id="dc042-129">Conditional access policy</span></span>

<span data-ttu-id="dc042-130">Sie können eine Richtlinie für bedingten Zugriff festlegen, um den Zugriff anhand folgender Aspekte zu schützen:</span><span class="sxs-lookup"><span data-stu-id="dc042-130">You can set a conditional access policy to protect access based on:</span></span>
- <span data-ttu-id="dc042-131">Der Status der Gerätekonformität.</span><span class="sxs-lookup"><span data-stu-id="dc042-131">The device compliance status.</span></span>
- <span data-ttu-id="dc042-132">Die auf dem Gerät ausgeführte Plattform.</span><span class="sxs-lookup"><span data-stu-id="dc042-132">The platform that is running on the device.</span></span>
- <span data-ttu-id="dc042-133">Die Art von Apps, die für den Zugriff auf die Dienste verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="dc042-133">The type of apps that are used to access the services.</span></span>

<span data-ttu-id="dc042-134">Im Gegensatz zu anderen Intune-Richtlinien stellen Sie Richtlinien für bedingten Zugriff nicht bereit.</span><span class="sxs-lookup"><span data-stu-id="dc042-134">Unlike other Intune policies, you don't deploy conditional access policies.</span></span> <span data-ttu-id="dc042-135">Stattdessen konfigurieren Sie die Richtlinie und wählen die Benutzer aus, für die die Richtlinie gelten soll. Dann wird die Richtlinie auf diese Benutzer angewendet.</span><span class="sxs-lookup"><span data-stu-id="dc042-135">Instead, after you configure the policy and select the users that should have the policy, the policy is applied to all targeted users.</span></span> <span data-ttu-id="dc042-136">Bei Benutzern, für die eine Richtlinie gelten soll, muss jedes von ihnen verwendete Gerät die Richtlinie erfüllen, damit sie auf Ressourcen zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="dc042-136">When a user is targeted by a policy, each device they use must be compliant in order for them to access resources.</span></span>


## <a name="next-steps"></a><span data-ttu-id="dc042-137">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="dc042-137">Next steps</span></span>


2. <span data-ttu-id="dc042-138">[Erstellen einer Gerätekompatibilitätsrichtlinie](create-a-device-compliance-policy-in-microsoft-intune.md)</span><span class="sxs-lookup"><span data-stu-id="dc042-138">[Create a device compliance policy](create-a-device-compliance-policy-in-microsoft-intune.md).</span></span>

3. <span data-ttu-id="dc042-139">Erstellen Sie eine Richtlinie für bedingten Zugriff für eines/n der folgenden Microsoft-Clouddienste bzw. -produkte:</span><span class="sxs-lookup"><span data-stu-id="dc042-139">Create a conditional access policy for one of the following Microsoft cloud services/product:</span></span>

   - [<span data-ttu-id="dc042-140">Bedingte Zugriffsrichtlinie für Exchange Online erstellen</span><span class="sxs-lookup"><span data-stu-id="dc042-140">Create a conditional access policy for Exchange Online</span></span>](restrict-access-to-exchange-online-with-microsoft-intune.md)
   - [<span data-ttu-id="dc042-141">Bedingte Zugriffsrichtlinie für Exchange Online lokal erstellen</span><span class="sxs-lookup"><span data-stu-id="dc042-141">Create a conditional access policy for Exchange On-premises</span></span>](restrict-access-to-exchange-onpremises-with-microsoft-intune.md)
   - [<span data-ttu-id="dc042-142">Bedingte Zugriffsrichtlinie für Exchange Online Dedicated (neu) erstellen</span><span class="sxs-lookup"><span data-stu-id="dc042-142">Create a conditional access policy for new Exchange Online Dedicated</span></span>](restrict-access-to-exchange-online-with-microsoft-intune.md)
   - [<span data-ttu-id="dc042-143">Bedingte Zugriffsrichtlinie für Exchange Online Dedicated (älter) erstellen</span><span class="sxs-lookup"><span data-stu-id="dc042-143">Create a conditional access policy for legacy Exchange Online Dedicated</span></span>](restrict-access-to-exchange-onpremises-with-microsoft-intune.md)
   - [<span data-ttu-id="dc042-144">Erstellen einer bedingten Zugriffsrichtlinie für SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="dc042-144">Create a conditional access policy for SharePoint Online</span></span>](restrict-access-to-sharepoint-online-with-microsoft-intune.md)
   - [<span data-ttu-id="dc042-145">Erstellen einer bedingten Zugriffsrichtlinie für Skype for Business</span><span class="sxs-lookup"><span data-stu-id="dc042-145">Create a conditional access policy for Skype for Business Online</span></span>](restrict-access-to-skype-for-business-online-with-microsoft-intune.md)
   - [<span data-ttu-id="dc042-146">Erstellen einer bedingten Zugriffsrichtlinie für Dynamics CRM Online</span><span class="sxs-lookup"><span data-stu-id="dc042-146">Create a conditional access policy for Dynamics CRM Online</span></span>](restrict-access-to-dynamics-crm-online-with-microsoft-intune.md)
