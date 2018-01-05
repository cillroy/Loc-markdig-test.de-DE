---
title: "Vorbereitung von Intune für die Verwaltung mobiler Geräte (MDM)"
description: "Bewerten Sie Ihre geschäftlichen und technischen Anforderungen, bevor Sie zu Intune migrieren."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 06/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 58591442-6606-4f39-a06b-f17a1f25af25
ms.reviewer: dagerrit
ms.suite: ems
ms.openlocfilehash: 2c32a5cc45714b929535e0af0f0f664b0d8bad41
ms.sourcegitcommit: e37e916e2bf14f092d3a767bc90d68c181d739fb
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/03/2018
---
# <a name="phase-1-prepare-intune-for-mobile-device-management-mdm"></a><span data-ttu-id="62cf2-103">Phase 1: Vorbereitung von Intune für die Verwaltung mobiler Geräte (MDM)</span><span class="sxs-lookup"><span data-stu-id="62cf2-103">Phase 1: Prepare Intune for mobile device management (MDM)</span></span>

<span data-ttu-id="62cf2-104">Bevor wir uns mit den Details zum Einrichten von Intune befassen, werfen wir einen Blick auf die Anforderungen Ihres Unternehmens an die Verwaltung mobiler Geräte.</span><span class="sxs-lookup"><span data-stu-id="62cf2-104">Before diving into the details of setting up Intune, let’s review the mobile device management requirements of your organization.</span></span> <span data-ttu-id="62cf2-105">Es kann hilfreich sein, Berichte aktiver Benutzer in Ihrem aktuellen MDM-Anbieter auszuführen, um die wichtigen Benutzergruppen zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="62cf2-105">It might be helpful to run reports of active users in your current MDM provider to identify the critical user groups.</span></span> <span data-ttu-id="62cf2-106">Dann können Sie beginnen, die Fragen im Abschnitt [Einschätzen von MDM-Anforderungen](migration-guide-prepare.md#assess-mdm-requirements) zu adressieren.</span><span class="sxs-lookup"><span data-stu-id="62cf2-106">Then you can begin addressing the questions in the [Assess MDM requirements ](migration-guide-prepare.md#assess-mdm-requirements) section.</span></span>

## <a name="assess-mdm-requirements"></a><span data-ttu-id="62cf2-107">Einschätzen von MDM-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="62cf2-107">Assess MDM requirements</span></span>

### <a name="what-kinds-of-devices-do-you-need-to-manage"></a><span data-ttu-id="62cf2-108">Welche Arten von Geräten müssen Sie verwalten?</span><span class="sxs-lookup"><span data-stu-id="62cf2-108">What kinds of devices do you need to manage?</span></span>

-   <span data-ttu-id="62cf2-109">Welche [Plattformen](supported-devices-browsers.md) müssen Sie unterstützen?</span><span class="sxs-lookup"><span data-stu-id="62cf2-109">Which [platforms](supported-devices-browsers.md) do you need to support?</span></span>

-   <span data-ttu-id="62cf2-110">Handelt es sich bei den Geräten, die unterstützt werden müssen, um unternehmenseigene oder BYOD-Geräte?</span><span class="sxs-lookup"><span data-stu-id="62cf2-110">Are the devices you need to support corporate-owned or personal devices?</span></span>

-   <span data-ttu-id="62cf2-111">Welche Art von Verbindung verwenden Sie?</span><span class="sxs-lookup"><span data-stu-id="62cf2-111">What kind of connectivity do you use?</span></span> <span data-ttu-id="62cf2-112">WLAN, Mobiltelefone, VPN?</span><span class="sxs-lookup"><span data-stu-id="62cf2-112">Wi-Fi, cellular, VPN?</span></span>

### <a name="what-do-your-users-need-to-do-on-managed-devices"></a><span data-ttu-id="62cf2-113">Was müssen die Benutzer auf den verwalteten Geräten tun?</span><span class="sxs-lookup"><span data-stu-id="62cf2-113">What do your users need to do on managed devices?</span></span>

-   <span data-ttu-id="62cf2-114">Müssen Sie den Endbenutzern Apps bereitstellen?</span><span class="sxs-lookup"><span data-stu-id="62cf2-114">Do you need to provision apps to your end-users?</span></span>

-   <span data-ttu-id="62cf2-115">Verwenden Sie benutzerdefinierte, branchenspezifische Apps?</span><span class="sxs-lookup"><span data-stu-id="62cf2-115">Do you use custom line-of-business apps?</span></span> <span data-ttu-id="62cf2-116">Oder benötigen Sie nur öffentliche Store-Apps?</span><span class="sxs-lookup"><span data-stu-id="62cf2-116">Or do you only need public store apps?</span></span>

-   <span data-ttu-id="62cf2-117">Müssen Sie E-Mail-Konten bereitstellen?</span><span class="sxs-lookup"><span data-stu-id="62cf2-117">Do you need to provision email accounts?</span></span>

### <a name="what-kinds-of-users"></a><span data-ttu-id="62cf2-118">Um welche Arten von Benutzern handelt es sich?</span><span class="sxs-lookup"><span data-stu-id="62cf2-118">What kinds of users?</span></span>

-   <span data-ttu-id="62cf2-119">Wie viele Benutzer werden ein einzelnes Gerät verwenden?</span><span class="sxs-lookup"><span data-stu-id="62cf2-119">How many users will use a single device?</span></span>

-   <span data-ttu-id="62cf2-120">Welche Nutzungsbedingungen benötigen Sie?</span><span class="sxs-lookup"><span data-stu-id="62cf2-120">What terms of use do you need?</span></span>

    -   <span data-ttu-id="62cf2-121">Stellen Sie sicher, dass Sie Ihre Rechtsabteilung frühzeitig heranziehen.</span><span class="sxs-lookup"><span data-stu-id="62cf2-121">Make sure to involve your legal department early in this.</span></span>
    -   <span data-ttu-id="62cf2-122">Welche Lokalisierung ist erforderlich?</span><span class="sxs-lookup"><span data-stu-id="62cf2-122">What localization is required?</span></span>

-   <span data-ttu-id="62cf2-123">Sind die Benutzer mit Technologie und IT im Allgemeinen vertraut?</span><span class="sxs-lookup"><span data-stu-id="62cf2-123">Are the users familiar with technology and IT in general?</span></span>

### <a name="what-is-your-device-security-policy"></a><span data-ttu-id="62cf2-124">Welche Sicherheitsrichtlinie für Geräte haben Sie?</span><span class="sxs-lookup"><span data-stu-id="62cf2-124">What is your device security policy?</span></span>

- <span data-ttu-id="62cf2-125">Ist Verschlüsselung auf Geräteebene erforderlich?</span><span class="sxs-lookup"><span data-stu-id="62cf2-125">Do you need device-level encryption?</span></span>

- <span data-ttu-id="62cf2-126">Wie ist die Länge Ihres aktuellen Kennworts/PIN-Codes?</span><span class="sxs-lookup"><span data-stu-id="62cf2-126">What are your current device passcode/pin code lengths?</span></span>

- <span data-ttu-id="62cf2-127">Müssen Sie Gerätefunktionen deaktivieren oder bestimmtes Geräteverhalten einschränken?</span><span class="sxs-lookup"><span data-stu-id="62cf2-127">Do you need to disable device features, or restrict certain device behaviors?</span></span> <span data-ttu-id="62cf2-128">Sie können eine Reihe von plattformspezifischen Einstellungen mit Konfigurationsprofilen für Geräte steuern, z.B.:</span><span class="sxs-lookup"><span data-stu-id="62cf2-128">You can control a variety of platform-specific settings with device configuration profiles, for example:</span></span>
    - <span data-ttu-id="62cf2-129">Deaktivieren der Kamera</span><span class="sxs-lookup"><span data-stu-id="62cf2-129">Disable camera</span></span>
    - <span data-ttu-id="62cf2-130">Einzelanwendungsmodus zulassen</span><span class="sxs-lookup"><span data-stu-id="62cf2-130">Lock to single-app mode</span></span><br/>

- <span data-ttu-id="62cf2-131">Welche Arten von Authentifizierung müssen Sie unterstützen?</span><span class="sxs-lookup"><span data-stu-id="62cf2-131">What kinds of authentication must you support?</span></span> <span data-ttu-id="62cf2-132">Welche Zertifikate müssen bereitgestellt werden, wenn Sie zertifikatbasierte Authentifizierung benötigen?</span><span class="sxs-lookup"><span data-stu-id="62cf2-132">If you need certificate-based authentication, what kinds of certificates must be provisioned?</span></span>
  - <span data-ttu-id="62cf2-133">Intune kann Zertifikate mit Ressourcenzugriffsprofilen für registrierte Geräte bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="62cf2-133">Intune can provision certificates with resource access profiles for enrolled devices.</span></span>
  -   <span data-ttu-id="62cf2-134">Welche Art von Public Key-Infrastruktur (PKI) müssen Sie unterstützen?</span><span class="sxs-lookup"><span data-stu-id="62cf2-134">What kind of Public Key Infrastructure (PKI) infra do you need to support?</span></span>
  <br></br>
- <span data-ttu-id="62cf2-135">Müssen Sie virtuelles privates Netzwerk (VPN) auf Geräte- oder App-Ebene unterstützen?</span><span class="sxs-lookup"><span data-stu-id="62cf2-135">Do you need to support Virtual Private Network (VPN) at the device or app level?</span></span>

  -   <span data-ttu-id="62cf2-136">Intune kann VPN-Konfigurationen für VPN-Drittanbieter bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="62cf2-136">Intune can provision VPN configurations for third-party VPN providers.</span></span>
  <br/><br/>
- <span data-ttu-id="62cf2-137">Können vorübergehende Ausnahmen für bestimmte Anforderungen gemacht werden, um Ausfallzeiten zu vermeiden?</span><span class="sxs-lookup"><span data-stu-id="62cf2-137">Can temporary exceptions be made for certain requirements to avoid downtime?</span></span> <span data-ttu-id="62cf2-138">Oder müssen Geräte mit Zugriff immer alle Sicherheitsanforderungen erfüllen?</span><span class="sxs-lookup"><span data-stu-id="62cf2-138">Or must devices with access always comply with all security requirements?</span></span>

## <a name="next-steps"></a><span data-ttu-id="62cf2-139">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="62cf2-139">Next steps</span></span>
<span data-ttu-id="62cf2-140">Lesen Sie diese [Fallstudien](https://customers.microsoft.com/story/mwh-global-now-part-of-stantec-secures-mobile-devices-with-intune) aus verschiedenen Branchen, die Ihnen zeigen, wie Organisationen ihre Anforderungen an die Verwaltung mobiler Geräte eingeschätzt haben.</span><span class="sxs-lookup"><span data-stu-id="62cf2-140">Read these [case studies](https://customers.microsoft.com/story/mwh-global-now-part-of-stantec-secures-mobile-devices-with-intune) from different industry sectors to see how organizations assessed their requirements for mobile device management.</span></span>

<span data-ttu-id="62cf2-141">Überprüfen Sie die [einfache Einrichtung von Intune](migration-guide-setup.md).</span><span class="sxs-lookup"><span data-stu-id="62cf2-141">Review the [basic Intune setup](migration-guide-setup.md).</span></span>
