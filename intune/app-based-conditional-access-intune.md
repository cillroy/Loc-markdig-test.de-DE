---
title: App-basierter bedingter Zugriff mit Intune
description: Machen Sie sich mit den Konzepten der Funktionsweise des App-basierten bedingten Zugriffs mit Intune vertraut.
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 05/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: b399fba0-5dd4-4777-bc9b-856af038ec41
ms.reviewer: chrisgre
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: afc24faf135927a5f78c52a4087c0b1522b8bcf7
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2018
---
# <a name="app-based-conditional-access-with-intune"></a><span data-ttu-id="0b70c-103">App-basierter bedingter Zugriff mit Intune</span><span class="sxs-lookup"><span data-stu-id="0b70c-103">App-based conditional access with Intune</span></span>

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="0b70c-104">[Intune-App-Schutzrichtlinien](app-protection-policy.md) unterstützen Sie beim Schutz Ihrer Unternehmensdaten auf Geräten, die bei Intune registriert sind.</span><span class="sxs-lookup"><span data-stu-id="0b70c-104">[Intune app protection policies](app-protection-policy.md) help protect your company data on devices that are enrolled into Intune.</span></span> <span data-ttu-id="0b70c-105">App-Schutzrichtlinien können Sie auch auf mitarbeitereigenen Geräten verwenden, die nicht für die Verwaltung in Intune registriert sind.</span><span class="sxs-lookup"><span data-stu-id="0b70c-105">You can also use app protection policies on employee owned devices that are not enrolled for management in Intune.</span></span> <span data-ttu-id="0b70c-106">Auch wenn Ihr Unternehmen das Gerät nicht verwaltet, müssen Sie in diesem Fall dennoch sicherstellen, dass Unternehmensdaten und -ressourcen geschützt sind.</span><span class="sxs-lookup"><span data-stu-id="0b70c-106">In this case, even though your company doesn't manage the device, you still need to make sure that company data and resources are protected.</span></span>

<span data-ttu-id="0b70c-107">Mit App-basiertem bedingten Zugriff und der Verwaltung von mobilen Apps wird eine Sicherheitsschicht hinzugefügt, indem sichergestellt wird, dass nur mobile Apps, die Intune-App-Schutzrichtlinien unterstützen, auf Exchange Online und andere Office 365-Dienste zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="0b70c-107">App-based conditional access and mobile app management add a security layer by making sure only mobile apps that support Intune app protection policies can access Exchange online and other Office 365 services.</span></span>

> [!NOTE]
> <span data-ttu-id="0b70c-108">Eine verwaltete App ist eine App, auf die App-Schutzrichtlinien angewendet wurden und die von Intune verwaltet werden kann.</span><span class="sxs-lookup"><span data-stu-id="0b70c-108">A managed app is an app that has app protection policies applied to it, and can be managed by Intune.</span></span>

<span data-ttu-id="0b70c-109">Wenn Sie nur für die Microsoft Outlook-App den Zugriff auf Exchange Online zulassen, können Sie die integrierten E-Mail-Apps von iOS und Android blockieren.</span><span class="sxs-lookup"><span data-stu-id="0b70c-109">You can block the built-in mail apps on iOS and Android when you allow only the Microsoft Outlook app to access Exchange Online.</span></span> <span data-ttu-id="0b70c-110">Darüber hinaus können Sie für Apps, auf die keine Intune-App-Schutzrichtlinien angewendet wurden, den Zugriff auf SharePoint Online blockieren.</span><span class="sxs-lookup"><span data-stu-id="0b70c-110">Additionally, you can block apps that don’t have Intune app protection policies applied from accessing SharePoint Online.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="0b70c-111">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="0b70c-111">Prerequisites</span></span>
<span data-ttu-id="0b70c-112">Bevor Sie eine App-basierte bedingte Zugriffsrichtlinie erstellen, benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="0b70c-112">Before you create an app-based conditional access policy, you must have:</span></span>

- <span data-ttu-id="0b70c-113">**Enterprise Mobility + Security (EMS)** oder ein **Azure Active Directory Premium-Abonnement**</span><span class="sxs-lookup"><span data-stu-id="0b70c-113">**Enterprise Mobility + Security (EMS)** or an **Azure Active Directory (AD) Premium subscription**</span></span>
- <span data-ttu-id="0b70c-114">Benutzer müssen für EMS oder Azure AD lizenziert werden.</span><span class="sxs-lookup"><span data-stu-id="0b70c-114">Users must be licensed for EMS or Azure AD</span></span>

<span data-ttu-id="0b70c-115">Weitere Informationen finden Sie in der [Enterprise Mobility – Preise](https://www.microsoft.com/cloud-platform/enterprise-mobility-pricing) oder der [Azure Active Directory – Preise](https://azure.microsoft.com/pricing/details/active-directory/).</span><span class="sxs-lookup"><span data-stu-id="0b70c-115">For more information, see [Enterprise Mobility pricing ](https://www.microsoft.com/cloud-platform/enterprise-mobility-pricing) or [Azure Active Directory pricing](https://azure.microsoft.com/pricing/details/active-directory/).</span></span>

## <a name="supported-apps"></a><span data-ttu-id="0b70c-116">Unterstützte Apps</span><span class="sxs-lookup"><span data-stu-id="0b70c-116">Supported apps</span></span>

<span data-ttu-id="0b70c-117">Eine Liste von Apps, die den App-basierten bedingten Zugriff unterstützen, finden Sie in der [Dokumentation zur Technischen Referenz zum bedingen Zugriff von Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-technical-reference).</span><span class="sxs-lookup"><span data-stu-id="0b70c-117">A list of apps that support app-based conditional access can be found in the [Azure Active Directory conditional access technical reference documentation.](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-technical-reference)</span></span>

<span data-ttu-id="0b70c-118">Der App-basierte bedingte Zugriff [unterstützt auch branchenspezifische Apps](https://docs.microsoft.com/intune-classic/deploy-use/block-apps-with-no-modern-authentication), aber diese Apps müssen die [moderne Authentifizierung von Office 365](https://support.office.com/article/Using-Office-365-modern-authentication-with-Office-clients-776c0036-66fd-41cb-8928-5495c0f9168a) nutzen.</span><span class="sxs-lookup"><span data-stu-id="0b70c-118">App-based conditional access [also supports line-of-business (LOB) apps](https://docs.microsoft.com/intune-classic/deploy-use/block-apps-with-no-modern-authentication), but these apps need to use [Office 365 modern authentication](https://support.office.com/article/Using-Office-365-modern-authentication-with-Office-clients-776c0036-66fd-41cb-8928-5495c0f9168a).</span></span>

## <a name="how-app-based-conditional-access-works"></a><span data-ttu-id="0b70c-119">Funktionsweise des App-basierten bedingten Zugriffs</span><span class="sxs-lookup"><span data-stu-id="0b70c-119">How app-based conditional access works</span></span>

<span data-ttu-id="0b70c-120">In diesem Beispiel hat der Administrator App-Schutzrichtlinien auf die Outlook-App angewendet. Zudem gilt eine Regel für bedingten Zugriff, mit der die Outlook-App einer genehmigten Liste von Apps hinzugefügt wird, die beim Zugriff auf Unternehmens-E-Mails verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="0b70c-120">In this example, the admin has applied app protection policies to the Outlook app followed by a conditional access rule that adds the Outlook app to an approved list of apps that can be used when accessing corporate e-mail.</span></span>

> [!NOTE]
> <span data-ttu-id="0b70c-121">Die Struktur aus dem nachfolgenden Flussdiagramm kann für andere verwaltete Apps verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="0b70c-121">The flowchart structure below can be used for other managed apps.</span></span>

![App-basierter bedingter Zugriff mit Intune, Flussdiagramm](./media/ca-intune-common-ways-3.png)

1. <span data-ttu-id="0b70c-123">Der Benutzer versucht, sich über die Outlook-App bei Azure AD zu authentifizieren.</span><span class="sxs-lookup"><span data-stu-id="0b70c-123">The user tries to authenticate to Azure AD from the Outlook app.</span></span>

2. <span data-ttu-id="0b70c-124">Der Benutzer wird an den App Store umgeleitet, um eine Broker-App zu installieren, wenn er zum ersten Mal versucht, sich zu authentifizieren.</span><span class="sxs-lookup"><span data-stu-id="0b70c-124">The user gets redirected to the app store to install a broker app when trying to authenticate for the first time.</span></span> <span data-ttu-id="0b70c-125">Die Broker-App kann der Microsoft Authenticator für iOS oder das Microsoft-Unternehmensportal für Android-Geräte sein.</span><span class="sxs-lookup"><span data-stu-id="0b70c-125">The broker app can be either the Microsoft Authenticator for iOS, or the Microsoft Company portal for Android devices.</span></span>

   <span data-ttu-id="0b70c-126">Wenn Benutzer versuchen, eine native E-Mail-App zu verwenden, werden sie an den App Store umgeleitet, um dann die Outlook-App zu installieren.</span><span class="sxs-lookup"><span data-stu-id="0b70c-126">If users try to use a native e-mail app, they’ll be redirected to the app store to then install the Outlook app.</span></span>

3. <span data-ttu-id="0b70c-127">Die Broker-App wird auf dem Gerät installiert.</span><span class="sxs-lookup"><span data-stu-id="0b70c-127">The broker app gets installed on the device.</span></span>

4. <span data-ttu-id="0b70c-128">Die Broker-App startet die Azure AD-Registrierung, durch die ein Gerätedatensatz in Azure AD erstellt wird.</span><span class="sxs-lookup"><span data-stu-id="0b70c-128">The broker app starts the Azure AD registration process which creates a device record in Azure AD.</span></span> <span data-ttu-id="0b70c-129">Dies ist nicht mit der Registrierung für die mobile Geräteverwaltung (MDM) identisch, aber dieser Datensatz ist erforderlich, damit bedingte Zugriffsrichtlinien auf dem Gerät erzwungen werden können.</span><span class="sxs-lookup"><span data-stu-id="0b70c-129">This is not the same as the mobile device management (MDM) enrollment process, but this record is necessary so the conditional access policies can be enforced on the device.</span></span>

5. <span data-ttu-id="0b70c-130">Die Broker-App überprüft die Identität der App.</span><span class="sxs-lookup"><span data-stu-id="0b70c-130">The broker app verifies the identity of the app.</span></span> <span data-ttu-id="0b70c-131">Es gibt eine Sicherheitsschicht, sodass die Broker-App überprüfen kann, ob die App für die Verwendung durch den Benutzer autorisiert ist.</span><span class="sxs-lookup"><span data-stu-id="0b70c-131">There’s a security layer so the broker app can validate if the app is authorized to be used by the user.</span></span>

6. <span data-ttu-id="0b70c-132">Die Broker-App sendet die App-Client-ID während der Benutzerauthentifizierung an Azure AD, um zu überprüfen, ob sie in der durch die Richtlinie genehmigten Liste enthalten ist.</span><span class="sxs-lookup"><span data-stu-id="0b70c-132">The broker app sends the App Client ID to Azure AD as part of the user authentication process to check if it’s in the policy approved list.</span></span>

7. <span data-ttu-id="0b70c-133">Azure AD ermöglicht dem Benutzer die Authentifizierung und die Verwendung der App basierend auf der durch die Richtlinie genehmigte Liste.</span><span class="sxs-lookup"><span data-stu-id="0b70c-133">Azure AD allows the user to authenticate and use the app based on the policy approved list.</span></span> <span data-ttu-id="0b70c-134">Wenn die App nicht auf der Liste enthalten ist, verweigert Azure AD den Zugriff auf die App.</span><span class="sxs-lookup"><span data-stu-id="0b70c-134">If the app is not on the list, Azure AD denies access to the app.</span></span>

8. <span data-ttu-id="0b70c-135">Die Outlook-App kommuniziert mit dem Outlook-Clouddienst, um die Kommunikation mit Exchange Online zu initiieren.</span><span class="sxs-lookup"><span data-stu-id="0b70c-135">The Outlook app communicates with Outlook Cloud Service to initiate communication with Exchange Online.</span></span>

9. <span data-ttu-id="0b70c-136">Der Outlook-Clouddienst kommuniziert mit Azure AD, um Exchange Online-Dienstzugriffstoken für den Benutzer abzurufen.</span><span class="sxs-lookup"><span data-stu-id="0b70c-136">Outlook Cloud Service communicates with Azure AD to retrieve Exchange Online service access token for the user.</span></span>

10. <span data-ttu-id="0b70c-137">Die Outlook-App kommuniziert mit Exchange Online, um die Unternehmens-E-Mails des Benutzers abzurufen.</span><span class="sxs-lookup"><span data-stu-id="0b70c-137">The Outlook app communicates with Exchange Online to retrieve the user's corporate e-mail.</span></span>

11. <span data-ttu-id="0b70c-138">Unternehmens-E-Mails werden an das Postfach des Benutzers übermittelt.</span><span class="sxs-lookup"><span data-stu-id="0b70c-138">Corporate e-mail is delivered to the user's mailbox.</span></span>

## <a name="next-steps"></a><span data-ttu-id="0b70c-139">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="0b70c-139">Next steps</span></span>
[<span data-ttu-id="0b70c-140">Erstellen einer App-basierten Richtlinie für bedingten Zugriff</span><span class="sxs-lookup"><span data-stu-id="0b70c-140">Create an app-based conditional access policy</span></span>](app-based-conditional-access-intune-create.md)

[<span data-ttu-id="0b70c-141">Blockieren von Apps, die über keine moderne Authentifizierung verfügen</span><span class="sxs-lookup"><span data-stu-id="0b70c-141">Block apps that do not have modern authentication</span></span>](app-modern-authentication-block.md)
