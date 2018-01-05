---
title: "Vorbereitungen zum Konfigurieren von App-Schutzrichtlinien für Windows 10"
description: Einrichten des MAM-Anbieters (Mobile Application Management) in Azure AD
keywords: 
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 04/18/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: ebc7cfc8-40b9-47c2-8357-d392ebbb27c8
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: c94fe06c186dd33f7497236fc70a2a41f4141d87
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2017
---
# <a name="get-ready-to-configure-app-protection-policies-for-windows-10"></a><span data-ttu-id="7ff31-103">Vorbereitungen zum Konfigurieren von App-Schutzrichtlinien für Windows 10</span><span class="sxs-lookup"><span data-stu-id="7ff31-103">Get ready to configure app protection policies for Windows 10</span></span>

[!INCLUDE[note for both-portals](../includes/note-for-both-portals.md)]

<span data-ttu-id="7ff31-104">Vor der Erstellung einer Windows 10-App-Schutzrichtlinie müssen Sie die mobile Anwendungsverwaltung (MAM) für Windows 10 aktivieren, indem Sie den MAM-Anbieter in Azure AD einrichten.</span><span class="sxs-lookup"><span data-stu-id="7ff31-104">Before creating a Windows 10 app protection policy using, you need to enable mobile application management (MAM) for Windows 10 by setting up the MAM provider in Azure AD.</span></span> <span data-ttu-id="7ff31-105">Mit dieser Konfiguration können Sie den Registrierungsstatus definieren, wenn Sie eine neue WIP-Richtlinie (Windows Information Protection) in Intune erstellen.</span><span class="sxs-lookup"><span data-stu-id="7ff31-105">This configuration allows you to define the enrollment state when creating a new Windows Information Protection (WIP) policy with Intune.</span></span>

> [!NOTE]
> <span data-ttu-id="7ff31-106">Der Registrierungsstatus kann entweder „MAM“ oder „Mobile Geräteverwaltung (MDM)“ lauten.</span><span class="sxs-lookup"><span data-stu-id="7ff31-106">The enrollment state can be either MAM or mobile device management (MDM).</span></span>

## <a name="to-configure-the-mam-provider"></a><span data-ttu-id="7ff31-107">Konfigurieren des MAM-Anbieters</span><span class="sxs-lookup"><span data-stu-id="7ff31-107">To configure the MAM provider</span></span>

1.  <span data-ttu-id="7ff31-108">Navigieren Sie zum [Azure-Portal](https://portal.azure.com/) und melden Sie sich mit Ihren Intune-Anmeldeinformationen an.</span><span class="sxs-lookup"><span data-stu-id="7ff31-108">Go to the [Azure portal](https://portal.azure.com/) and sign in with your Intune credentials.</span></span>

2.  <span data-ttu-id="7ff31-109">Wählen Sie im linken Menü **Azure Active Directory** aus.</span><span class="sxs-lookup"><span data-stu-id="7ff31-109">From the left menu, choose **Azure Active Directory**.</span></span>

    ![Konfiguration des MAM-Anbieters](../media/AppManagement/mam-provider-sc-1.png)

3.  <span data-ttu-id="7ff31-111">Das Blatt **Azure AD** wird geöffnet. Wählen Sie **Mobilität (MDM und MAM)** und klicken Sie dann auf **Microsoft Intune**.</span><span class="sxs-lookup"><span data-stu-id="7ff31-111">**Azure AD** blade opens, choose **Mobility (MDM and MAM)**, then click **Microsoft Intune**.</span></span>

    ![Mobilität (MDM und MAM)](../media/AppManagement/mam-provider-sc-2.png)

4.  <span data-ttu-id="7ff31-113">Das Blatt zur Konfiguration wird geöffnet. Wählen Sie zuerst **Standard-MAM-URLs wiederherstellen** aus und konfigurieren Sie dann Folgendes:</span><span class="sxs-lookup"><span data-stu-id="7ff31-113">The configure blade opens, choose **Restore default MAM URLs** first, then configure the following:</span></span>

    <span data-ttu-id="7ff31-114">ein.</span><span class="sxs-lookup"><span data-stu-id="7ff31-114">a.</span></span>  <span data-ttu-id="7ff31-115">MAM-Benutzerbereich: Mit MAM können Sie Unternehmensdaten für bestimmte Benutzergruppen, die Windows 10-Geräte verwenden, oder alle Benutzer schützen.</span><span class="sxs-lookup"><span data-stu-id="7ff31-115">MAM user scope: You can use MAM to protect corporate data on specific group of users that use Windows 10 devices or all users.</span></span>

    <span data-ttu-id="7ff31-116">b.</span><span class="sxs-lookup"><span data-stu-id="7ff31-116">b.</span></span>  <span data-ttu-id="7ff31-117">URL zu den MAM-Nutzungsbedingungen: Die URL zum Endpunkt für die Nutzungsbedingungen des MAM-Diensts.</span><span class="sxs-lookup"><span data-stu-id="7ff31-117">MAM terms of use URL: The URL of the terms of use endpoint of the MAM service.</span></span> <span data-ttu-id="7ff31-118">Hierdurch werden die Bedingungen des MAM-Diensts für Endbenutzer angezeigt.</span><span class="sxs-lookup"><span data-stu-id="7ff31-118">This is used to display the term of MAM service to end-users.</span></span>

    <span data-ttu-id="7ff31-119">c.</span><span class="sxs-lookup"><span data-stu-id="7ff31-119">c.</span></span>  <span data-ttu-id="7ff31-120">URL für MAM-Ermittlung: Dies ist die URL, nach denen Geräte beim Anwenden von App-Schutzrichtlinien suchen müssen.</span><span class="sxs-lookup"><span data-stu-id="7ff31-120">MAM discovery URL: This the URL devices seek when they need to apply app protection policies.</span></span>

    <span data-ttu-id="7ff31-121">d.</span><span class="sxs-lookup"><span data-stu-id="7ff31-121">d.</span></span>  <span data-ttu-id="7ff31-122">URL für MAM-Kompatibilität:</span><span class="sxs-lookup"><span data-stu-id="7ff31-122">MAM compliance URL:</span></span>

5.  <span data-ttu-id="7ff31-123">Nachdem Sie diese Einstellungen konfiguriert haben, wählen Sie **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="7ff31-123">Once you configure these settings, choose **Save**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="7ff31-124">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="7ff31-124">Next steps</span></span>

[<span data-ttu-id="7ff31-125">Erstellen einer WIP-App-Schutzrichtlinie</span><span class="sxs-lookup"><span data-stu-id="7ff31-125">Create a WIP app protection policy</span></span>](/intune-classic/deploy-use/create-windows-information-protection-policy-with-intune)
