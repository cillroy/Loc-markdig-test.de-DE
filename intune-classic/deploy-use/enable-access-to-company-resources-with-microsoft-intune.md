---
title: Aktivieren des Zugriffs auf Unternehmensressourcen
description: "Die WLAN-, VPN- und E-Mail-Profile greifen ineinander, um Ihre Benutzer beim Zugriff auf die Dateien und Ressourcen, die sie benötigen, zu unterstützen."
keywords: 
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 11/02/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3dd8dd4e-e165-4d0c-97b7-b3e86ebab909
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: f15429fe61e08eb9a23123341b5ab8ce70a77e77
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2017
---
# <a name="enable-access-to-company-resources-with-microsoft-intune"></a><span data-ttu-id="4deb8-103">Aktivieren des Zugriffs auf Unternehmensressourcen mit Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="4deb8-103">Enable access to company resources with Microsoft Intune</span></span>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="4deb8-104">Die WLAN-, VPN- und E-Mail-Profile von Microsoft Intune greifen ineinander, um Ihre Benutzer beim Zugriff auf die Dateien und Ressourcen, die sie für ihre Arbeit benötigen, zu unterstützen, unabhängig davon, wo sie gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="4deb8-104">Microsoft Intune Wi-Fi, VPN, and email profiles work together to help your users gain access to the files and resources that they need to do their work wherever they are.</span></span> <span data-ttu-id="4deb8-105">Dieser Zugriff wird mithilfe von Zertifikatprofilen gesichert.</span><span class="sxs-lookup"><span data-stu-id="4deb8-105">Certificate profiles help secure that access.</span></span>

## <a name="wi-fi-profileswi-fi-connections-in-microsoft-intunemd-and-supported-platforms"></a><span data-ttu-id="4deb8-106">[WLAN-Profile](wi-fi-connections-in-microsoft-intune.md) und unterstützte Plattformen</span><span class="sxs-lookup"><span data-stu-id="4deb8-106">[Wi-Fi profiles](wi-fi-connections-in-microsoft-intune.md) and supported platforms</span></span>

<span data-ttu-id="4deb8-107">Bereitstellen von Einstellungen für drahtlose Netzwerke für Ihre Benutzer.</span><span class="sxs-lookup"><span data-stu-id="4deb8-107">Deploy wireless network settings to your users.</span></span> <span data-ttu-id="4deb8-108">Diese Einstellungen erleichtern Ihren Benutzern die Verbindung mit dem Unternehmensnetzwerk.</span><span class="sxs-lookup"><span data-stu-id="4deb8-108">These settings make it easy for your users to connect to the corporate network.</span></span>
#### <a name="supported-platforms"></a><span data-ttu-id="4deb8-109">Unterstützte Plattformen</span><span class="sxs-lookup"><span data-stu-id="4deb8-109">Supported platforms</span></span>

|<span data-ttu-id="4deb8-110">Windows 8.1 und höher</span><span class="sxs-lookup"><span data-stu-id="4deb8-110">Windows 8.1 and later</span></span>|<span data-ttu-id="4deb8-111">Windows Phone 8.1 und höher</span><span class="sxs-lookup"><span data-stu-id="4deb8-111">Windows Phone 8.1 and later</span></span>|<span data-ttu-id="4deb8-112">iOS</span><span class="sxs-lookup"><span data-stu-id="4deb8-112">iOS</span></span>|<span data-ttu-id="4deb8-113">Android</span><span class="sxs-lookup"><span data-stu-id="4deb8-113">Android</span></span>|<span data-ttu-id="4deb8-114">Samsung KNOX Standard</span><span class="sxs-lookup"><span data-stu-id="4deb8-114">Samsung KNOX Standard</span></span>|
|---------------------|---------------------------|---|-------|------------|
|<span data-ttu-id="4deb8-115">Ja (Sie können ein Windows-WLAN-Profil importieren.)</span><span class="sxs-lookup"><span data-stu-id="4deb8-115">Yes (You can import a Windows Wi-Fi profile.)</span></span>|<span data-ttu-id="4deb8-116">Ja (Sie können OMA-URI konfigurieren.)</span><span class="sxs-lookup"><span data-stu-id="4deb8-116">Yes (You can configure OMA-URI.)</span></span> |<span data-ttu-id="4deb8-117">Ja</span><span class="sxs-lookup"><span data-stu-id="4deb8-117">Yes</span></span>|<span data-ttu-id="4deb8-118">Ja</span><span class="sxs-lookup"><span data-stu-id="4deb8-118">Yes</span></span>|<span data-ttu-id="4deb8-119">Ja</span><span class="sxs-lookup"><span data-stu-id="4deb8-119">Yes</span></span>|

## <a name="vpn-profilesvpn-connections-in-microsoft-intunemd-and-supported-platforms"></a><span data-ttu-id="4deb8-120">[VPN-Profile](vpn-connections-in-microsoft-intune.md) und unterstützte Plattformen</span><span class="sxs-lookup"><span data-stu-id="4deb8-120">[VPN profiles](vpn-connections-in-microsoft-intune.md) and supported platforms</span></span>
<span data-ttu-id="4deb8-121">Stellen Sie Einstellungen für ein virtuelles privates Netzwerk (VPN) für Ihre Benutzer bereit.</span><span class="sxs-lookup"><span data-stu-id="4deb8-121">Deploy virtual private network (VPN) settings to your users.</span></span> <span data-ttu-id="4deb8-122">Diese Einstellungen erleichtern Ihren Benutzern die Verbindung mit Ressourcen im Unternehmensnetzwerk.</span><span class="sxs-lookup"><span data-stu-id="4deb8-122">These settings make it easy for users to connect to resources on the corporate network.</span></span>

|<span data-ttu-id="4deb8-123">Windows 8.1 und höher</span><span class="sxs-lookup"><span data-stu-id="4deb8-123">Windows 8.1 and later</span></span>|<span data-ttu-id="4deb8-124">Windows Phone 8.1 und höher</span><span class="sxs-lookup"><span data-stu-id="4deb8-124">Windows Phone 8.1 and later</span></span>|<span data-ttu-id="4deb8-125">iOS</span><span class="sxs-lookup"><span data-stu-id="4deb8-125">iOS</span></span>|<span data-ttu-id="4deb8-126">Android</span><span class="sxs-lookup"><span data-stu-id="4deb8-126">Android</span></span>|<span data-ttu-id="4deb8-127">Samsung KNOX Standard</span><span class="sxs-lookup"><span data-stu-id="4deb8-127">Samsung KNOX Standard</span></span>|
|---------------------|---------------------------|---|-------|------------|
|<span data-ttu-id="4deb8-128">Ja</span><span class="sxs-lookup"><span data-stu-id="4deb8-128">Yes</span></span>|<span data-ttu-id="4deb8-129">Ja</span><span class="sxs-lookup"><span data-stu-id="4deb8-129">Yes</span></span>|<span data-ttu-id="4deb8-130">Ja</span><span class="sxs-lookup"><span data-stu-id="4deb8-130">Yes</span></span>|<span data-ttu-id="4deb8-131">Ja</span><span class="sxs-lookup"><span data-stu-id="4deb8-131">Yes</span></span>|<span data-ttu-id="4deb8-132">Ja</span><span class="sxs-lookup"><span data-stu-id="4deb8-132">Yes</span></span>|

## <a name="email-profilesconfigure-access-to-corporate-email-using-email-profiles-with-microsoft-intunemd-and-supported-platforms"></a><span data-ttu-id="4deb8-133">[E-Mail-Profile](configure-access-to-corporate-email-using-email-profiles-with-microsoft-intune.md) und unterstützte Plattformen</span><span class="sxs-lookup"><span data-stu-id="4deb8-133">[Email profiles](configure-access-to-corporate-email-using-email-profiles-with-microsoft-intune.md) and supported platforms</span></span>
<span data-ttu-id="4deb8-134">Erstellen, Bereitstellen und Überwachen von nativen E-Mail-Clienteinstellungen auf den Geräten in Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="4deb8-134">Create, deploy, and monitor native email client settings on devices in your organization.</span></span>

|<span data-ttu-id="4deb8-135">Windows 8.1 und höher</span><span class="sxs-lookup"><span data-stu-id="4deb8-135">Windows 8.1 and later</span></span>|<span data-ttu-id="4deb8-136">Windows Phone 8.1 und höher</span><span class="sxs-lookup"><span data-stu-id="4deb8-136">Windows Phone 8.1 and later</span></span>|<span data-ttu-id="4deb8-137">iOS</span><span class="sxs-lookup"><span data-stu-id="4deb8-137">iOS</span></span>|<span data-ttu-id="4deb8-138">Android</span><span class="sxs-lookup"><span data-stu-id="4deb8-138">Android</span></span>|<span data-ttu-id="4deb8-139">Samsung KNOX Standard</span><span class="sxs-lookup"><span data-stu-id="4deb8-139">Samsung KNOX Standard</span></span>|
|---------------------|---------------------------|---|-------|------------|
|<span data-ttu-id="4deb8-140">Nein</span><span class="sxs-lookup"><span data-stu-id="4deb8-140">No</span></span>|<span data-ttu-id="4deb8-141">Ja</span><span class="sxs-lookup"><span data-stu-id="4deb8-141">Yes</span></span>|<span data-ttu-id="4deb8-142">Ja</span><span class="sxs-lookup"><span data-stu-id="4deb8-142">Yes</span></span>|<span data-ttu-id="4deb8-143">Nein</span><span class="sxs-lookup"><span data-stu-id="4deb8-143">No</span></span>|<span data-ttu-id="4deb8-144">Ja</span><span class="sxs-lookup"><span data-stu-id="4deb8-144">Yes</span></span>|
> [!NOTE]
> <span data-ttu-id="4deb8-145">[Dieser Beitrag im Intune-Teamblog](https://blogs.technet.microsoft.com/enterprisemobility/2015/02/19/using-oma-uri-to-create-custom-wi-fi-profiles-for-windows-phone-8-1/) enthält Informationen zum Konfigurieren von Windows Phone 8.1-WLAN-Profilen mithilfe von OMA-URI.</span><span class="sxs-lookup"><span data-stu-id="4deb8-145">[This Intune team blog post](https://blogs.technet.microsoft.com/enterprisemobility/2015/02/19/using-oma-uri-to-create-custom-wi-fi-profiles-for-windows-phone-8-1/) gives information about how to configure a Windows Phone 8.1 Wi-Fi profile using OMA-URI.</span></span>

## <a name="certificate-profilessecure-resource-access-with-certificate-profilesmd-and-supported-platforms"></a><span data-ttu-id="4deb8-146">[Zertifikatprofile](secure-resource-access-with-certificate-profiles.md) und unterstützte Plattformen</span><span class="sxs-lookup"><span data-stu-id="4deb8-146">[Certificate profiles](secure-resource-access-with-certificate-profiles.md) and supported platforms</span></span>
<span data-ttu-id="4deb8-147">Ermöglichen den sicheren Zugriff auf Unternehmensressourcen einschließlich Drahtlosnetzwerken und VPN-Verbindungen.</span><span class="sxs-lookup"><span data-stu-id="4deb8-147">Help secure access to company resources including wireless networks and VPN connections.</span></span>

|<span data-ttu-id="4deb8-148">Windows 8.1 und höher</span><span class="sxs-lookup"><span data-stu-id="4deb8-148">Windows 8.1 and later</span></span>|<span data-ttu-id="4deb8-149">Windows Phone 8.1 und höher</span><span class="sxs-lookup"><span data-stu-id="4deb8-149">Windows Phone 8.1 and later</span></span>|<span data-ttu-id="4deb8-150">iOS</span><span class="sxs-lookup"><span data-stu-id="4deb8-150">iOS</span></span>|<span data-ttu-id="4deb8-151">Android</span><span class="sxs-lookup"><span data-stu-id="4deb8-151">Android</span></span>|<span data-ttu-id="4deb8-152">Samsung KNOX Standard</span><span class="sxs-lookup"><span data-stu-id="4deb8-152">Samsung KNOX Standard</span></span>|
|---------------------|---------------------------|---|-------|------------|
|<span data-ttu-id="4deb8-153">Ja</span><span class="sxs-lookup"><span data-stu-id="4deb8-153">Yes</span></span>|<span data-ttu-id="4deb8-154">Ja</span><span class="sxs-lookup"><span data-stu-id="4deb8-154">Yes</span></span>|<span data-ttu-id="4deb8-155">Ja</span><span class="sxs-lookup"><span data-stu-id="4deb8-155">Yes</span></span>|<span data-ttu-id="4deb8-156">Ja</span><span class="sxs-lookup"><span data-stu-id="4deb8-156">Yes</span></span>|<span data-ttu-id="4deb8-157">Ja</span><span class="sxs-lookup"><span data-stu-id="4deb8-157">Yes</span></span>|
