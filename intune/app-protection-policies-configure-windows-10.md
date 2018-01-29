---
title: "Vorbereitungen zum Konfigurieren von App-Schutzrichtlinien für Windows 10"
titlesuffix: Azure portal
description: Einrichten des MAM-Anbieters (Mobile Application Management) in Azure AD
keywords: 
author: erikre
ms.author: erikre
manager: angrobe
ms.date: 10/25/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 949fddec-5318-4c9a-957e-ea260e6e05be
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: c30718b2237ee246344cbaf7acc89ffb19fe6767
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2018
---
# <a name="get-ready-to-configure-app-protection-policies-for-windows-10"></a><span data-ttu-id="5dee1-103">Vorbereitungen zum Konfigurieren von App-Schutzrichtlinien für Windows 10</span><span class="sxs-lookup"><span data-stu-id="5dee1-103">Get ready to configure app protection policies for Windows 10</span></span>

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="5dee1-104">Aktivieren Sie die Verwaltung für mobile Anwendungen (Mobile Application Management, MAM) für Windows 10, indem Sie den MAM-Anbieter in Azure AD festlegen.</span><span class="sxs-lookup"><span data-stu-id="5dee1-104">Enable mobile application management (MAM) for Windows 10 by setting the MAM provider in Azure AD.</span></span> <span data-ttu-id="5dee1-105">Durch die Festlegung eines MAM-Anbieters in Azure AD können Sie den Registrierungsstatus definieren, wenn Sie eine neue WIP-Richtlinie (Windows Information Protection) in Intune erstellen.</span><span class="sxs-lookup"><span data-stu-id="5dee1-105">Setting a MAM provider in Azure AD allows you to define the enrollment state when creating a new Windows Information Protection (WIP) policy with Intune.</span></span> <span data-ttu-id="5dee1-106">Der Registrierungsstatus kann entweder „MAM“ oder „Mobile Geräteverwaltung (MDM)“ lauten.</span><span class="sxs-lookup"><span data-stu-id="5dee1-106">The enrollment state can be either MAM or mobile device management (MDM).</span></span>

> [!NOTE]
> <span data-ttu-id="5dee1-107">Geräte mit einem MAM-Registrierungsstatus müssen mit Azure AD verknüpft sein.</span><span class="sxs-lookup"><span data-stu-id="5dee1-107">Devices with a MAM enrollment state are required to be Azure AD joined.</span></span>

## <a name="to-configure-the-mam-provider"></a><span data-ttu-id="5dee1-108">Konfigurieren des MAM-Anbieters</span><span class="sxs-lookup"><span data-stu-id="5dee1-108">To configure the MAM provider</span></span>

1. <span data-ttu-id="5dee1-109">Melden Sie sich beim Azure-Portal an, und klicken Sie auf **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="5dee1-109">Sign in to the Azure portal, and choose **Azure Active Directory.**</span></span>

2. <span data-ttu-id="5dee1-110">Wählen Sie **Mobilität (MDM und MAM)** in der Gruppe **Verwalten** aus.</span><span class="sxs-lookup"><span data-stu-id="5dee1-110">Choose **Mobility (MDM and MAM)** in the **Manage** group.</span></span>

3. <span data-ttu-id="5dee1-111">Klicken Sie auf **Microsoft Intune**.</span><span class="sxs-lookup"><span data-stu-id="5dee1-111">Click **Microsoft Intune**.</span></span>

4. <span data-ttu-id="5dee1-112">Konfigurieren Sie die Einstellungen in der Gruppe **Standard-MAM-URLs wiederherstellen** auf dem Blatt **Konfigurieren**.</span><span class="sxs-lookup"><span data-stu-id="5dee1-112">Configure the settings in the  **Restore default MAM URLs** group on the **Configure** blade.</span></span>

    <span data-ttu-id="5dee1-113">**MAM-Benutzerbereich**</span><span class="sxs-lookup"><span data-stu-id="5dee1-113">**MAM user scope**</span></span>  
      <span data-ttu-id="5dee1-114">Verwenden Sie die automatische Registrierung von MAM, um Unternehmensdaten auf den Windows-Geräten Ihrer Mitarbeiter zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="5dee1-114">Use MAM auto-enrollment to manage enterprise data on your employees' Windows devices.</span></span> <span data-ttu-id="5dee1-115">Die automatische MAM-Registrierung wird für BYOD-Szenarios konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="5dee1-115">MAM auto-enrollment will be configured for bring your own device scenarios.</span></span><ul><li><span data-ttu-id="5dee1-116">**Keine**</span><span class="sxs-lookup"><span data-stu-id="5dee1-116">**None**</span></span><br><span data-ttu-id="5dee1-117">Wählen Sie diese Option, wenn alle Benutzer in MAM registriert werden können.</span><span class="sxs-lookup"><span data-stu-id="5dee1-117">Select if all users can be enrolled in MAM.</span></span></li><li><span data-ttu-id="5dee1-118">**Einige**</span><span class="sxs-lookup"><span data-stu-id="5dee1-118">**Some**</span></span><br><span data-ttu-id="5dee1-119">Wählen Sie Azure AD-Gruppen aus, die Benutzer enthalten, die in MAM registriert werden.</span><span class="sxs-lookup"><span data-stu-id="5dee1-119">Select Azure AD groups that contain users who will be enrolled in MAM.</span></span></li><li><span data-ttu-id="5dee1-120">**Alle**</span><span class="sxs-lookup"><span data-stu-id="5dee1-120">**All**</span></span><br><span data-ttu-id="5dee1-121">Wählen Sie diese Option, wenn alle Benutzer in MAM registriert werden können.</span><span class="sxs-lookup"><span data-stu-id="5dee1-121">Select if all users can be enrolled in MAM.</span></span></li></ul>

    <span data-ttu-id="5dee1-122">**URL für MDM-Nutzungsbedingungen**</span><span class="sxs-lookup"><span data-stu-id="5dee1-122">**MAM terms of use URL**</span></span>  
     <span data-ttu-id="5dee1-123">Die URL zum Endpunkt für die Nutzungsbedingungen des MAM-Diensts.</span><span class="sxs-lookup"><span data-stu-id="5dee1-123">The URL of the terms of use endpoint of the MAM service.</span></span> <span data-ttu-id="5dee1-124">Der Endpunkt für die Nutzungsbedingungen wird verwendet, um die Nutzungsbedingungen Endbenutzern anzuzeigen, bevor diese ihre Geräte für die Verwaltung registrieren.</span><span class="sxs-lookup"><span data-stu-id="5dee1-124">The terms-of-use endpoint is used to display the terms of service to end-users before enrolling their devices for management.</span></span> <span data-ttu-id="5dee1-125">Im Text der Nutzungsbedingungen werden Benutzer über die auf dem mobilen Gerät erzwungenen Richtlinien informiert.</span><span class="sxs-lookup"><span data-stu-id="5dee1-125">The terms-of-use text informs users about the policies enforced on the mobile device.</span></span>

    <span data-ttu-id="5dee1-126">**URL für MDM-Ermittlung**</span><span class="sxs-lookup"><span data-stu-id="5dee1-126">**MAM discovery URL**</span></span>  
    <span data-ttu-id="5dee1-127">Die URL des Endpunkt der Registrierung des MAM-Diensts.</span><span class="sxs-lookup"><span data-stu-id="5dee1-127">The URL of the enrollment endpoint of the MAM service.</span></span> <span data-ttu-id="5dee1-128">Der Registrierungsendpunkt wird zum Registrieren von Geräten für die Verwaltung mit dem MAM-Dienst verwendet.</span><span class="sxs-lookup"><span data-stu-id="5dee1-128">The enrollment endpoint is used to enroll devices for management with the MAM service.</span></span>

    <span data-ttu-id="5dee1-129">**URL für MAM-Kompatibilität**</span><span class="sxs-lookup"><span data-stu-id="5dee1-129">**MAM compliance URL**</span></span>  
      <span data-ttu-id="5dee1-130">Die URL des Kompatibilitätsendpunkts des MAM-Diensts.</span><span class="sxs-lookup"><span data-stu-id="5dee1-130">The URL of the compliance endpoint of the MAM service.</span></span> <span data-ttu-id="5dee1-131">Wenn einem Benutzer der Zugriff auf eine Ressource von einem nicht-kompatiblen Gerät aus verweigert wird, wird dem Benutzer ein Link zur Kompatibilitäts-URL angezeigt.</span><span class="sxs-lookup"><span data-stu-id="5dee1-131">When a user is denied access to a resource from a non-compliant device, a link to the compliance URL is displayed to the user.</span></span> <span data-ttu-id="5dee1-132">Benutzer können zu dieser URL navigieren, die vom MAM-Dienst gehostet wird, um zu verstehen, warum Ihr Gerät als nicht kompatibel eingestuft ist.</span><span class="sxs-lookup"><span data-stu-id="5dee1-132">Users can navigate to this URL hosted by the MAM service, in order to understand why their device is considered non-compliant.</span></span> <span data-ttu-id="5dee1-133">Benutzer können ebenso eine eigenständige Wartung durchführen, damit ihr Gerät kompatibel wird und sie damit fortfahren können, auf Ressourcen zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="5dee1-133">Users can also initiate self-service remediation so their device becomes compliant and they can continue to access resources.</span></span>

5.  <span data-ttu-id="5dee1-134">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="5dee1-134">Click **Save**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="5dee1-135">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="5dee1-135">Next steps</span></span>

[<span data-ttu-id="5dee1-136">Erstellen einer WIP-App-Schutzrichtlinie</span><span class="sxs-lookup"><span data-stu-id="5dee1-136">Create a WIP app protection policy</span></span>](windows-information-protection-policy-create.md)
