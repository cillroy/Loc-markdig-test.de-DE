---
title: Check Point Mobile SandBlast-Connector in Intune
titlesuffix: Azure portal
description: Check Point SandBlast-Integration in Intune
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 07/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 706a4228-9bdf-41e0-b8d1-64c923dd2d2b
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: e3f4a51ed34ee0ed8364d2d5ae68526a82412665
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2018
---
# <a name="check-point-sandblast-mobile-threat-defense-connector-with-intune"></a><span data-ttu-id="ac666-103">Check Point SandBlast Mobile Threat Defense-Connector in Intune</span><span class="sxs-lookup"><span data-stu-id="ac666-103">Check Point SandBlast Mobile Threat Defense connector with Intune</span></span>

<span data-ttu-id="ac666-104">Sie können den Zugriff mobiler Geräte auf Unternehmensressourcen mit bedingtem Zugriff basierend auf Risikobewertungen steuern, die von Check Point SandBlast Mobile vorgenommen werden, einer Mobile Threat Defense-Lösung, die in Microsoft Intune integriert ist.</span><span class="sxs-lookup"><span data-stu-id="ac666-104">You can control mobile device access to corporate resources using conditional access based on risk assessment conducted by Check Point SandBlast Mobile, a mobile threat defense solution that integrates with Microsoft Intune.</span></span> <span data-ttu-id="ac666-105">Das Risiko wird basierend auf Telemetriedaten von Geräten bewertet, auf denen die Check Point SandBlast Mobile-App ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="ac666-105">Risk is assessed based on telemetry collected from devices running the Check Point SandBlast Mobile app.</span></span>

<span data-ttu-id="ac666-106">Sie können Richtlinien für bedingten Zugriff basierend auf der Check Point SandBlast Mobile-Risikobewertung konfigurieren, die über Intune-Gerätekompatibilitätsrichtlinien aktiviert werden, und so anhand der erkannten Bedrohungen nicht kompatible Geräte für den Zugriff auf Unternehmensressourcen zulassen oder blockieren.</span><span class="sxs-lookup"><span data-stu-id="ac666-106">You can configure conditional access policies based on Check Point SandBlast Mobile risk assessment enabled through Intune device compliance policies, which you can use to allow or block non-compliant devices to access corporate resources based on detected threats.</span></span>

## <a name="how-do-intune-and-check-point-sandblast-mobile-help-protect-your-company-resources"></a><span data-ttu-id="ac666-107">Wie können Sie mit Intune und Check Point SandBlast Mobile Ihre Unternehmensressourcen schützen?</span><span class="sxs-lookup"><span data-stu-id="ac666-107">How do Intune and Check Point SandBlast Mobile help protect your company resources?</span></span>

<span data-ttu-id="ac666-108">Die Check Point SandBlast Mobile-App für Android oder iOS erfasst Telemetriedaten des Dateisystems, Netzwerkstapels sowie von Geräten und Anwendungen, sofern verfügbar, und sendet diese dann an den Check Point SandBlast-Clouddienst, mit dessen Hilfe die Anfälligkeit des Geräts für mobile Bedrohungen bewertet wird.</span><span class="sxs-lookup"><span data-stu-id="ac666-108">Check Point Sandblast Mobile app for Android and iOS captures file system, network stack, device and application telemetry where available, then sends the telemetry data to the Check Point SandBlast cloud service to assess the device's risk for mobile threats.</span></span>

<span data-ttu-id="ac666-109">Die Intune-Gerätekompatibilitätsrichtlinie enthält eine Regel für Check Point SandBlast Mobile Threat Defense, die auf der Check Point SandBlast-Risikobewertung basiert.</span><span class="sxs-lookup"><span data-stu-id="ac666-109">The Intune device compliance policy includes a rule for Check Point SandBlast Mobile Threat Defense, which is based on the Check Point SandBlast risk assessment.</span></span> <span data-ttu-id="ac666-110">Wenn diese Regel aktiviert ist, bewertet Intune die Gerätekompatibilität mit der von Ihnen aktivierten Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="ac666-110">When this rule is enabled, Intune evaluates device compliance with the policy that you enabled.</span></span> <span data-ttu-id="ac666-111">Wird das Gerät als nicht kompatibel eingestuft, wird der Zugriff auf Ressourcen wie Exchange Online und SharePoint Online für Benutzer blockiert.</span><span class="sxs-lookup"><span data-stu-id="ac666-111">If the device is found non-compliant, users are blocked access to corporate resources like Exchange Online and SharePoint Online.</span></span> <span data-ttu-id="ac666-112">Benutzer erhalten zudem einen Leitfaden von der auf ihren Geräten installierten Check Point SandBlast Mobile-App, um das Problem zu beheben und den Zugriff auf Unternehmensressourcen zurückzuerlangen.</span><span class="sxs-lookup"><span data-stu-id="ac666-112">Users also receive guidance from the Check Point SandBlast mobile app installed in their devices to resolve the issue and regain access to corporate resources.</span></span>

<!-- ## Sample scenarios

Here are some common scenarios:

### Control access based on threats from malicious apps

When malicious apps such as malware are detected on devices, you can block devices until the threat is resolved:

-   Connecting to corporate e-mail

-   Syncing corporate files with the OneDrive for Work app

-   Accessing company apps

**Block when malicious apps are detected:**

![Check Point MTD block when malicious apps are detected](./media/checkpoint-MTD-2.PNG)

**Access granted on remediation:**

![Check Point MTD access granted](./media/checkpoint-MTD-3.PNG)

### Control access based on threat to network

Detect threats like **Man-in-the-middle** in network, and protect access to Wi-Fi networks based on the device risk.

**Block network access through Wi-Fi:**

![Check Point MTD block network access through Wi-Fi](./media/checkpoint-MTD-4.PNG)

**Access granted on remediation:**

![Check Point MTD Wi-Fi access granted](./media/checkpoint-MTD-5.PNG)

### Control access to SharePoint Online based on threat to network

Detect threats like **Man-in-the-middle** in network, and prevent synchronization of corporate files based on the device risk.

**Block SharePoint Online when network threats are detected:**

![Check Point MTD block SharePoint Online access](./media/checkpoint-MTD-6.PNG)

**Access granted on remediation:**

![Check Point MTD SharePoint Online access granted](./media/checkpoint-MTD-7.PNG)

## Supported platforms

-   **Android 4.1 and later**

-   **iOS 8 and later**

## Pre-requisites

-   Azure Active Directory Premium

-   Microsoft Intune subscription

-   Check Point SandBlast Mobile Threat Defense subscription
    -   See [CheckPoint SandBlast website](https://www.checkpoint.com/) for more information.

## Next steps

- [Integrate CheckPoint SandBlast with Intune](checkpoint-sandblast-mobile-mtd-connector-integration.md)

- [Set up CheckPoint SandBlast Mobile app](mtd-apps-ios-app-configuration-policy-add-assign.md)

- [Create CheckPoint SandBlast Mobile device compliance policy](mtd-device-compliance-policy-create.md)

- [Enable CheckPoint SandBlast Mobile MTD connector](mtd-connector-enable.md)
