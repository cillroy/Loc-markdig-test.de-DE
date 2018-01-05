---
title: App-basierter bedingter Zugriff auf O365
description: "Informationen dazu, wie Sie mit bedingtem Zugriff für die Verwaltung mobiler Anwendungen bestimmen können, welche Apps auf O365-Dienste zugreifen dürfen."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 12/05/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: bd6bee60-5e39-42c8-a2e9-f5865ac3573f
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: chrisgre
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 8400204d11a5a8981a0dac5107e95a9dfde45f16
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2017
---
# <a name="allow-only-mobile-apps-that-support-intune-app-protection-policies-to-access-office-365-services"></a><span data-ttu-id="b2ac4-103">Zulassen des Zugriffs auf Office 365-Dienste ausschließlich für mobile Apps, die Intune-App-Richtlinien für die Verwaltung mobiler Anwendungen unterstützen</span><span class="sxs-lookup"><span data-stu-id="b2ac4-103">Allow only mobile apps that support Intune app protection policies to access Office 365 services</span></span>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="b2ac4-104">[Intune-App-Schutzrichtlinien](protect-apps-and-data-with-microsoft-intune.md) unterstützen Sie beim Schutz Ihrer Unternehmensdaten auf Geräten, die für die Verwaltung in Intune registriert sind.</span><span class="sxs-lookup"><span data-stu-id="b2ac4-104">[Intune app protection policies](protect-apps-and-data-with-microsoft-intune.md) help protect your company data on devices that are enrolled for management in Intune.</span></span> <span data-ttu-id="b2ac4-105">App-Schutzrichtlinien können Sie auch auf **mitarbeitereigenen Geräten verwenden, die nicht für die Verwaltung in Intune registriert sind**.</span><span class="sxs-lookup"><span data-stu-id="b2ac4-105">You can also use app protection policies on **employee owned devices that are not enrolled for management in Intune**.</span></span>  <span data-ttu-id="b2ac4-106">Auch wenn Sie das Gerät nicht verwalten, müssen Sie in diesem Fall dennoch sicherstellen, dass Unternehmensdaten und -ressourcen geschützt sind.</span><span class="sxs-lookup"><span data-stu-id="b2ac4-106">In this case, even though you don't manage the device, you still need to make sure that your company data and resources is protected.</span></span> <span data-ttu-id="b2ac4-107">Mithilfe des App-basierten bedingten Zugriffs mit MAM können Sie eine Richtlinie erstellen, die nur mobilen Apps mit Unterstützung für Intune-App-Schutzrichtlinien den Zugriff auf O365-Dienste wie Exchange Online gestattet.</span><span class="sxs-lookup"><span data-stu-id="b2ac4-107">Using app-based conditional access with MAM, you can create a policy that allows only mobile apps that support Intune app protection policies to access O365 services like Exchange Online.</span></span>

<span data-ttu-id="b2ac4-108">Wenn Sie beispielsweise zulassen, dass nur die **Microsoft Outlook-App** auf Exchange Online zugreifen kann, können Sie so **verhindern, dass die in iOS und Android integrierten Mail-Apps**, die nicht über den Datenschutz von Intune-Richtlinien für die Verwaltung mobiler Anwendungen verfügen, E-Mails von **Exchange Online** empfangen.</span><span class="sxs-lookup"><span data-stu-id="b2ac4-108">For example, by only allowing the **Microsoft Outlook app** to access Exchange Online, you can **block the built-in mail apps on iOS and Android**, which don't have the data protection from Intune MAM policies to get email from **Exchange Online**.</span></span> <span data-ttu-id="b2ac4-109">Sie können auch verhindern, dass mobile Apps, die nicht über MAM-Unterstützung verfügen, auf **SharePoint Online** zugreifen.</span><span class="sxs-lookup"><span data-stu-id="b2ac4-109">Or you can block mobile apps that don’t have Intune MAM support from accessing **SharePoint Online**.</span></span>

<span data-ttu-id="b2ac4-110">Das folgende Diagramm zeigt den Flow, anhand dessen Richtlinien für den App-basierten bedingten Zugriff festlegen, wann der Zugriff zugelassen oder blockiert wird: ![Diagramm, das die verschiedenen Kriterien anzeigt, die festlegen, wann der Zugriff zugelassen oder blockiert wird](../media/mam-ca-decision-flow_simple.png).</span><span class="sxs-lookup"><span data-stu-id="b2ac4-110">The diagram below illustrates the flow used by app-based conditional access policies to determine when to allow or block access: ![Diagram that shows the various criteria included to determine whether to allow or block access ](../media/mam-ca-decision-flow_simple.png).</span></span>

<span data-ttu-id="b2ac4-111">Beschreibung der Abkürzungen, die in den Diagrammen verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="b2ac4-111">Description of the abbreviations used in the diagrams:</span></span>
* <span data-ttu-id="b2ac4-112">**CP**: Unternehmensportal-App</span><span class="sxs-lookup"><span data-stu-id="b2ac4-112">**CP**: Company Portal app</span></span>
* <span data-ttu-id="b2ac4-113">**AA**: Azure-Authentifikator-App</span><span class="sxs-lookup"><span data-stu-id="b2ac4-113">**AA**: Azure Authenticator app</span></span>
* <span data-ttu-id="b2ac4-114">**AAD**: Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="b2ac4-114">**AAD**: Azure Active Directory</span></span>
* <span data-ttu-id="b2ac4-115">**EAS**: Exchange Active Sync</span><span class="sxs-lookup"><span data-stu-id="b2ac4-115">**EAS**: Exchange Active Sync</span></span>

## <a name="prerequisites"></a><span data-ttu-id="b2ac4-116">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="b2ac4-116">Prerequisites</span></span>
<span data-ttu-id="b2ac4-117">**Bevor** Sie Richtlinien für den App-basierten bedingten Zugriff konfigurieren können, müssen Sie über ein **Enterprise Mobility + Security- oder ein Azure Active Directory Premium-Abonnement** verfügen, und die Benutzer müssen für EMS oder Azure AD lizenziert sein.</span><span class="sxs-lookup"><span data-stu-id="b2ac4-117">**Before** you create an app-based conditional access policy, you must have an **Enterprise Mobility + Security or an Azure Active Directory premium subscription**, and the users must be licensed for EMS or Azure AD.</span></span> <span data-ttu-id="b2ac4-118">Weitere Informationen finden Sie in der [Preisübersicht für Enterprise Mobility](https://www.microsoft.com/cloud-platform/enterprise-mobility-pricing) oder der [Preisübersicht für Azure Active Directory](https://azure.microsoft.com/pricing/details/active-directory/).</span><span class="sxs-lookup"><span data-stu-id="b2ac4-118">For more details, see the [Enterprise Mobility pricing page](https://www.microsoft.com/cloud-platform/enterprise-mobility-pricing) or the [Azure Active Directory pricing page](https://azure.microsoft.com/pricing/details/active-directory/).</span></span>


## <a name="supported-apps"></a><span data-ttu-id="b2ac4-119">Unterstützte Apps</span><span class="sxs-lookup"><span data-stu-id="b2ac4-119">Supported apps</span></span>
<span data-ttu-id="b2ac4-120">**Exchange Online**:</span><span class="sxs-lookup"><span data-stu-id="b2ac4-120">**Exchange Online**:</span></span>
* <span data-ttu-id="b2ac4-121">**Microsoft Outlook** für Android und iOS</span><span class="sxs-lookup"><span data-stu-id="b2ac4-121">**Microsoft Outlook** for Android and iOS.</span></span>

<span data-ttu-id="b2ac4-122">**SharePoint Online**</span><span class="sxs-lookup"><span data-stu-id="b2ac4-122">**SharePoint Online**</span></span>
* <span data-ttu-id="b2ac4-123">Microsoft Word für iOS und Android</span><span class="sxs-lookup"><span data-stu-id="b2ac4-123">Microsoft Word for iOS and Android</span></span>
* <span data-ttu-id="b2ac4-124">Microsoft Excel für iOS und Android</span><span class="sxs-lookup"><span data-stu-id="b2ac4-124">Microsoft Excel for iOS and Android</span></span>
* <span data-ttu-id="b2ac4-125">Microsoft PowerPoint für iOS und Android</span><span class="sxs-lookup"><span data-stu-id="b2ac4-125">Microsoft PowerPoint for iOS and Android</span></span>
* <span data-ttu-id="b2ac4-126">Microsoft OneDrive for Business für iOS und Android</span><span class="sxs-lookup"><span data-stu-id="b2ac4-126">Microsoft OneDrive for Business for iOS and Android</span></span>
* <span data-ttu-id="b2ac4-127">Microsoft OneNote für iOS</span><span class="sxs-lookup"><span data-stu-id="b2ac4-127">Microsoft OneNote for iOS</span></span>

>[!IMPORTANT]
><span data-ttu-id="b2ac4-128">Bei Android-Geräten muss die anfängliche Geräteregistrierung durch Anmeldung bei der OneDrive-App oder bei der Outlook-App erfolgen.</span><span class="sxs-lookup"><span data-stu-id="b2ac4-128">For Android devices, the initial device registration must be done by logging into either the OneDrive app, or the Outlook app.</span></span> <span data-ttu-id="b2ac4-129">Die OneNote-App für Android unterstützt MAM ohne Registrierung noch nicht.</span><span class="sxs-lookup"><span data-stu-id="b2ac4-129">The OneNote app for Android does not yet support MAM without enrollment.</span></span>

<span data-ttu-id="b2ac4-130">Informationen zur Benutzerumgebung mit einer App, die Richtlinien für den App-basierten bedingten Zugriff beinhaltet, finden Sie unter [Was ist bei der Verwendung einer App mit App-basierter Zertifizierungsstelle (CA) zu erwarten](use-apps-with-mam-ca.md).</span><span class="sxs-lookup"><span data-stu-id="b2ac4-130">To learn about the user experience with an app that has app-based conditional access policies, see [What to expect when using an app with MAM CA](use-apps-with-mam-ca.md).</span></span>


## <a name="next-steps"></a><span data-ttu-id="b2ac4-131">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="b2ac4-131">Next steps</span></span>
[<span data-ttu-id="b2ac4-132">Erstellen einer Exchange Online-Richtlinie für MAM-Apps</span><span class="sxs-lookup"><span data-stu-id="b2ac4-132">Create an Exchange Online Policy for MAM apps</span></span>](mam-ca-for-exchange-online.md)

[<span data-ttu-id="b2ac4-133">Erstellen einer SharePoint Online-Richtlinie für MAM-Apps</span><span class="sxs-lookup"><span data-stu-id="b2ac4-133">Create a SharePoint Online Policy for MAM apps</span></span>](mam-ca-for-sharepoint-online.md)

[<span data-ttu-id="b2ac4-134">Blockieren von Apps, die über keine moderne Authentifizierung verfügen</span><span class="sxs-lookup"><span data-stu-id="b2ac4-134">Block apps that do not have modern authentication</span></span>](block-apps-with-no-modern-authentication.md)

### <a name="see-also"></a><span data-ttu-id="b2ac4-135">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b2ac4-135">See also</span></span>

[<span data-ttu-id="b2ac4-136">Protect app data with app protection policies (Schützen von App-Daten mithilfe von App-Schutzrichtlinien)</span><span class="sxs-lookup"><span data-stu-id="b2ac4-136">Protect app data with app protection policies</span></span>](protect-app-data-using-mobile-app-management-policies-with-microsoft-intune.md)
