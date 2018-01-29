---
title: "Zertifikatprofile für den Ressourcenzugriff"
description: "Sichern von VPN-, WLAN- und E-Mail-Zugriff mit einem Zertifikat, das auf jedem Benutzergerät installiert ist."
keywords: 
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 02/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 8cbb8499-611d-4217-a7b4-e9b864785dd0
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: kmyrup
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: ccfd69579832c553dc1416c21ca93b85cd93cd78
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2018
---
# <a name="secure-resource-access-with-certificate-profiles-in-microsoft-intune"></a><span data-ttu-id="ab687-103">Sicherer Zugriff auf Ressourcen mit Zertifikatprofilen in Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="ab687-103">Secure resource access with certificate profiles in Microsoft Intune</span></span>

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="ab687-104">Wenn Sie Benutzern den Zugriff auf Unternehmensressourcen über VPN, WLAN oder E-Mail-Profile gestatten, können Sie diesen Zugriff mit einem Zertifikat absichern, das auf jedem Benutzergerät installiert wird.</span><span class="sxs-lookup"><span data-stu-id="ab687-104">When you give users access to corporate resources through VPN, Wi-Fi, or email profiles, you can secure the access by using a certificate that is installed on each user device.</span></span> <span data-ttu-id="ab687-105">Gehen Sie dazu folgendermaßen vor:</span><span class="sxs-lookup"><span data-stu-id="ab687-105">Here's how it works:</span></span>

1. <span data-ttu-id="ab687-106">Stellen Sie sicher, dass die richtige Zertifikatinfrastruktur eingerichtet ist, wie unter [Konfigurieren der Zertifikatinfrastruktur für SCEP](configure-certificate-infrastructure-for-scep.md) und [Konfigurieren der Zertifikatinfrastruktur für PFX](configure-certificate-infrastructure-for-pfx.md) beschrieben.</span><span class="sxs-lookup"><span data-stu-id="ab687-106">Make sure you have the right certificate infrastructure in place, as described in [Configure certificate infrastructure for SCEP](configure-certificate-infrastructure-for-scep.md) and [Configure certificate infrastructure for PFX](configure-certificate-infrastructure-for-pfx.md).</span></span>

2. <span data-ttu-id="ab687-107">Installieren Sie auf jedem Gerät ein Stammzertifikat oder ein Zertifikat einer Zwischenzertifizierungsstelle, damit das Gerät die Rechtmäßigkeit Ihrer Zertifizierungsstelle erkennt.</span><span class="sxs-lookup"><span data-stu-id="ab687-107">Install a root certificate or an intermediate Certification Authority (CA) certificate on each device so that the device recognizes the legitimacy of your CA.</span></span> <span data-ttu-id="ab687-108">Zu diesem Zweck erstellen Sie ein **vertrauenswürdiges Zertifikatprofil** und stellen dieses bereit.</span><span class="sxs-lookup"><span data-stu-id="ab687-108">To do this, create and deploy a **Trusted Certificate Profile**.</span></span> <span data-ttu-id="ab687-109">Wenn Sie dieses Profil bereitstellen, wird das Stammzertifikat von den Geräten, die Sie mit Intune verwalten, angefordert und empfangen.</span><span class="sxs-lookup"><span data-stu-id="ab687-109">When you deploy this profile, the devices that you manage with Intune will request and receive the root certificate.</span></span> <span data-ttu-id="ab687-110">Sie müssen für jede Plattform ein eigenes Profil erstellen.</span><span class="sxs-lookup"><span data-stu-id="ab687-110">You have to create a separate profile for each platform.</span></span> <span data-ttu-id="ab687-111">Das **vertrauenswürdige Zertifikatprofil** ist für folgende Plattformen verfügbar:</span><span class="sxs-lookup"><span data-stu-id="ab687-111">The **Trusted Certificate Profile** is available for these platforms:</span></span>
   -  <span data-ttu-id="ab687-112">iOS 8.0 und höher</span><span class="sxs-lookup"><span data-stu-id="ab687-112">iOS 8.0 and later</span></span>
   -  <span data-ttu-id="ab687-113">Mac OS X 10.9 und höher</span><span class="sxs-lookup"><span data-stu-id="ab687-113">Mac OS X 10.9 and later</span></span>
   -  <span data-ttu-id="ab687-114">Android 4,0 und höher</span><span class="sxs-lookup"><span data-stu-id="ab687-114">Android 4.0 and later</span></span>
   -  <span data-ttu-id="ab687-115">Android for Work</span><span class="sxs-lookup"><span data-stu-id="ab687-115">Android for Work</span></span>
   -  <span data-ttu-id="ab687-116">Windows 8.1 und höher</span><span class="sxs-lookup"><span data-stu-id="ab687-116">Windows 8.1 and later</span></span>
   -  <span data-ttu-id="ab687-117">Windows Phone 8.1 und höher</span><span class="sxs-lookup"><span data-stu-id="ab687-117">Windows Phone 8.1 and later</span></span>

3. <span data-ttu-id="ab687-118">Erstellen Sie Zertifikatprofile, damit Geräte ein Zertifikat für die Authentifizierung des VPN-, WLAN- und E-Mail-Zugriffs anfordern, wie unter [Konfigurieren von Intune-Zertifikatprofilen](configure-intune-certificate-profiles.md) beschrieben.</span><span class="sxs-lookup"><span data-stu-id="ab687-118">Create certificate profiles so that devices request a certificate to be used for authentication of VPN, Wi-Fi, and email access, as described in [Configure Intune certificate profiles](configure-intune-certificate-profiles.md).</span></span> <span data-ttu-id="ab687-119">Sie können ein **PKCS #12-Zertifikatprofil (.PFX)** *oder* ein **SCEP-Zertifikatprofil** für Geräte auf diesen Plattformen erstellen und bereitstellen:</span><span class="sxs-lookup"><span data-stu-id="ab687-119">You can create and deploy a **PKCS #12 (.PFX) Certificate Profile** *or* a **SCEP Certificate Profile** for devices running these platforms:</span></span>

   -  <span data-ttu-id="ab687-120">iOS 8.0 und höher</span><span class="sxs-lookup"><span data-stu-id="ab687-120">iOS 8.0 and later</span></span>
   -  <span data-ttu-id="ab687-121">Android 4,0 und höher</span><span class="sxs-lookup"><span data-stu-id="ab687-121">Android 4.0 and later</span></span>
   -  <span data-ttu-id="ab687-122">Android for Work</span><span class="sxs-lookup"><span data-stu-id="ab687-122">Android for Work</span></span>
   -  <span data-ttu-id="ab687-123">Windows 10 (Desktop und Mobile) und höher</span><span class="sxs-lookup"><span data-stu-id="ab687-123">Windows 10 (desktop and mobile) and later</span></span>

   <span data-ttu-id="ab687-124">Verwenden Sie ein **SCEP-Zertifikatprofil** für Geräte, die diese Plattformen ausführen:</span><span class="sxs-lookup"><span data-stu-id="ab687-124">Use a **SCEP Certificate Profile** for devices running these platforms:</span></span>
    -   <span data-ttu-id="ab687-125">Mac OS X 10.9 und höher</span><span class="sxs-lookup"><span data-stu-id="ab687-125">Mac OS X 10.9 and later</span></span>
    -   <span data-ttu-id="ab687-126">Windows Phone 8.1</span><span class="sxs-lookup"><span data-stu-id="ab687-126">Windows Phone 8.1</span></span>

<span data-ttu-id="ab687-127">Sie müssen für jede Plattform ein eigenes Profil erstellen.</span><span class="sxs-lookup"><span data-stu-id="ab687-127">You must create a separate profile for each platform.</span></span> <span data-ttu-id="ab687-128">Nachdem Sie das Profil erstellt haben, ordnen Sie es dem bereits erstellten **vertrauenswürdigen Stammzertifikatprofil** zu.</span><span class="sxs-lookup"><span data-stu-id="ab687-128">When you create the profile, associate it with the **Trusted Root Certificate Profile** that you've already created.</span></span>

> [!NOTE]           
> - <span data-ttu-id="ab687-129">Wenn Sie über keine Unternehmenszertifizierungsstelle verfügen, müssen Sie eine erstellen.</span><span class="sxs-lookup"><span data-stu-id="ab687-129">If you don't have an Enterprise Certification Authority, you must create one.</span></span>
>- <span data-ttu-id="ab687-130">Wenn Sie sich basierend auf Ihren Geräteplattformen entschließen, das SCEP-Profil (Simple Certificate Enrollment Protocol) zu verwenden, müssen Sie auch einen NDES-Server (Network Device Enrollment Service) konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="ab687-130">If you decide, based on your device platforms, to use the Simplified Certificate Enrollment Protocol (SCEP) profile, you'll also need to configure a Network Device Enrollment Service (NDES) server.</span></span>
>-  <span data-ttu-id="ab687-131">Unabhängig davon, ob Sie SCEP- oder .PFX-Profile verwenden möchten, müssen Sie den Microsoft Intune-Zertifikatconnector herunterladen und konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="ab687-131">Whether you plan to use SCEP or .PFX profiles, you must download and configure the Microsoft Intune Certificate Connector.</span></span>
>-  <span data-ttu-id="ab687-132">Informationen zur Konfiguration aller erforderlichen Dienste finden Sie unter [Konfigurieren der Zertifikatinfrastruktur für SCEP](configure-certificate-infrastructure-for-scep.md) bzw. unter [Konfigurieren der Zertifikatinfrastruktur für PFX](configure-certificate-infrastructure-for-pfx.md).</span><span class="sxs-lookup"><span data-stu-id="ab687-132">Learn how to configure all of the required services in [Configure certificate infrastructure for SCEP](configure-certificate-infrastructure-for-scep.md) or [Configure certificate infrastructure for PFX](configure-certificate-infrastructure-for-pfx.md).</span></span>

### <a name="next-steps"></a><span data-ttu-id="ab687-133">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="ab687-133">Next steps</span></span>
- [<span data-ttu-id="ab687-134">Konfigurieren der Zertifikatinfrastruktur für SCEP</span><span class="sxs-lookup"><span data-stu-id="ab687-134">Configure certificate infrastructure for SCEP</span></span>](configure-certificate-infrastructure-for-scep.md)
- [<span data-ttu-id="ab687-135">Konfigurieren der Zertifikatinfrastruktur für PFX</span><span class="sxs-lookup"><span data-stu-id="ab687-135">Configure certificate infrastructure for PFX</span></span>](configure-certificate-infrastructure-for-pfx.md)
- [<span data-ttu-id="ab687-136">Konfigurieren von Intune-Zertifikatprofilen</span><span class="sxs-lookup"><span data-stu-id="ab687-136">Configure Intune certificate profiles</span></span>](configure-intune-certificate-profiles.md)
