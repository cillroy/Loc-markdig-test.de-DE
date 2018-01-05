---
title: Zimperium MTD-Connector in Intune
titleSuffix: Intune on Azure
description: Zimperium-Connectorintegration in Intune
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 09/06/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 975d8d84-792a-41ad-925a-4a7f1ae4dcaf
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 78214293a66784d4bc05e441c2c1cdbf718b0a9a
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2017
---
# <a name="zimperium-mobile-threat-defense-connector-with-intune"></a><span data-ttu-id="74c11-103">Zimperium Mobile Threat Defense-Connector in Intune</span><span class="sxs-lookup"><span data-stu-id="74c11-103">Zimperium Mobile Threat Defense connector with Intune</span></span>

<span data-ttu-id="74c11-104">Sie können den Zugriff mobiler Geräte auf Unternehmensressourcen mit bedingtem Zugriff basierend auf Risikobewertungen steuern, die von Zimperium vorgenommen werden, einer Mobile Threat Defense-Lösung (MTD), die mit Microsoft Intune zusammenarbeitet.</span><span class="sxs-lookup"><span data-stu-id="74c11-104">You can control mobile device access to corporate resources using conditional access based on risk assessment conducted by Zimperium, a Mobile Threat Defense (MTD) solution that integrates with Microsoft Intune.</span></span> <span data-ttu-id="74c11-105">Das Risiko wird basierend auf Telemetriedaten von Geräten bewertet, auf denen die Zimperium-App ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="74c11-105">Risk is assessed based on telemetry collected from devices running the Zimperium app.</span></span>

<span data-ttu-id="74c11-106">Sie können Richtlinien für bedingten Zugriff basierend auf der Zimperium-Risikobewertung konfigurieren, die über Intune-Gerätekompatibilitätsrichtlinien aktiviert werden, und so anhand der erkannten Bedrohungen nicht kompatible Geräte für den Zugriff auf Unternehmensressourcen zulassen oder blockieren.</span><span class="sxs-lookup"><span data-stu-id="74c11-106">You can configure conditional access policies based on Zimperium risk assessment enabled through Intune device compliance policies, which you can use to allow or block non-compliant devices to access corporate resources based on detected threats.</span></span>

## <a name="how-do-intune-and-zimperium-help-protect-your-company-resources"></a><span data-ttu-id="74c11-107">Wie helfen Intune und Zimperium beim Schutz von Unternehmensressourcen?</span><span class="sxs-lookup"><span data-stu-id="74c11-107">How do Intune and Zimperium help protect your company resources?</span></span>

<span data-ttu-id="74c11-108">Die Zimperium-App für Android oder iOS erfasst Telemetriedaten des Dateisystems, Netzwerkstapels sowie von Geräten und Anwendungen, sofern verfügbar, und sendet diese dann an den Zimperium-Clouddienst, mit dessen Hilfe die Anfälligkeit des Geräts für mobile Bedrohungen bewertet wird.</span><span class="sxs-lookup"><span data-stu-id="74c11-108">Zimperium app for Android and iOS captures file system, network stack, device and application telemetry where available, then sends the telemetry data to the Zimperium cloud service to assess the device's risk for mobile threats.</span></span>

<span data-ttu-id="74c11-109">Die Intune-Gerätekompatibilitätsrichtlinie enthält eine Regel für Zimperium Mobile Threat Defense, die auf der Zimperium-Risikobewertung basiert.</span><span class="sxs-lookup"><span data-stu-id="74c11-109">The Intune device compliance policy includes a rule for Zimperium Mobile Threat Defense, which is based on the Zimperium risk assessment.</span></span> <span data-ttu-id="74c11-110">Wenn diese Regel aktiviert ist, bewertet Intune die Gerätekompatibilität mit der von Ihnen aktivierten Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="74c11-110">When this rule is enabled, Intune evaluates device compliance with the policy that you enabled.</span></span> <span data-ttu-id="74c11-111">Wird das Gerät als nicht kompatibel eingestuft, wird der Zugriff auf Ressourcen wie Exchange Online und SharePoint Online für Benutzer blockiert.</span><span class="sxs-lookup"><span data-stu-id="74c11-111">If the device is found non-compliant, users are blocked access to corporate resources like Exchange Online and SharePoint Online.</span></span> <span data-ttu-id="74c11-112">Benutzer erhalten zudem einen Leitfaden von der auf ihren Geräten installierten Zimperium-App, um das Problem zu beheben und den Zugriff auf Unternehmensressourcen zurückzuerlangen.</span><span class="sxs-lookup"><span data-stu-id="74c11-112">Users also receive guidance from the Zimperium app installed in their devices to resolve the issue and regain access to corporate resources.</span></span>

## <a name="sample-scenarios"></a><span data-ttu-id="74c11-113">Beispielszenarien</span><span class="sxs-lookup"><span data-stu-id="74c11-113">Sample scenarios</span></span>

<span data-ttu-id="74c11-114">Nachstehend finden Sie einige Szenarios für die Integration von Zimperium in Intune:</span><span class="sxs-lookup"><span data-stu-id="74c11-114">See below a few scenarios when integrating Zimperium with Intune:</span></span>

### <a name="control-access-based-on-threats-from-malicious-apps"></a><span data-ttu-id="74c11-115">Steuern des Zugriffs basierend auf Bedrohungen durch Apps, die Schadsoftware enthalten</span><span class="sxs-lookup"><span data-stu-id="74c11-115">Control access based on threats from malicious apps</span></span>

<span data-ttu-id="74c11-116">Wenn Apps, die Schadsoftware enthalten, auf Geräten erkannt werden, können Sie Geräte blockieren, bis die Bedrohung beseitigt ist:</span><span class="sxs-lookup"><span data-stu-id="74c11-116">When malicious apps such as malware are detected on devices, you can block devices until the threat is resolved:</span></span>

-   <span data-ttu-id="74c11-117">Herstellen einer Verbindung mit Unternehmens-E-Mail</span><span class="sxs-lookup"><span data-stu-id="74c11-117">Connecting to corporate e-mail</span></span>

-   <span data-ttu-id="74c11-118">Synchronisieren von Unternehmensdateien mithilfe der OneDrive for Work-App</span><span class="sxs-lookup"><span data-stu-id="74c11-118">Syncing corporate files with the OneDrive for Work app</span></span>

-   <span data-ttu-id="74c11-119">Zugreifen auf Unternehmens-Apps</span><span class="sxs-lookup"><span data-stu-id="74c11-119">Accessing company apps</span></span>

<span data-ttu-id="74c11-120">**Blockieren, wenn Apps mit Schadsoftware entdeckt werden:**</span><span class="sxs-lookup"><span data-stu-id="74c11-120">**Block when malicious apps are detected:**</span></span>

![Apps mit Schadsoftware entdeckt](./media/Maliciousapps_blocked_Zimperium.png)

<span data-ttu-id="74c11-122">**Zugriff nach Beseitigung gewährt:**</span><span class="sxs-lookup"><span data-stu-id="74c11-122">**Access granted on remediation:**</span></span>

![Apps mit Schadsoftware entdeckt, Zugriff gewährt](./media/maliciousapps_unblocked_Zimperium.png)

### <a name="control-access-based-on-threat-to-network"></a><span data-ttu-id="74c11-124">Steuern des Zugriffs basierend auf der Bedrohung für das Netzwerk</span><span class="sxs-lookup"><span data-stu-id="74c11-124">Control access based on threat to network</span></span>

<span data-ttu-id="74c11-125">Erkennen Sie Bedrohungen wie **Man-in-the-Middle** im Netzwerk, und schützen Sie den Zugriff auf WLAN-Netzwerke auf der Grundlage des Geräterisikos.</span><span class="sxs-lookup"><span data-stu-id="74c11-125">Detect threats like **Man-in-the-middle** in network, and protect access to Wi-Fi networks based on the device risk.</span></span>

<span data-ttu-id="74c11-126">**Blockieren des Netzwerkzugriffs über WLAN:**</span><span class="sxs-lookup"><span data-stu-id="74c11-126">**Block network access through Wi-Fi:**</span></span>

![Blockieren des Netzwerkzugriffs über WLAN](./media/network_wifi_blocked_Zimperium.png)

<span data-ttu-id="74c11-128">**Zugriff nach Beseitigung gewährt:**</span><span class="sxs-lookup"><span data-stu-id="74c11-128">**Access granted on remediation:**</span></span>

![Zugriff erteilt nach der Behebung](./media/network_wifi_unblocked_Zimperium.png)

### <a name="control-access-to-sharepoint-online-based-on-threat-to-network"></a><span data-ttu-id="74c11-130">Steuern des Zugriffs auf SharePoint Online basierend auf der Bedrohung für das Netzwerk</span><span class="sxs-lookup"><span data-stu-id="74c11-130">Control access to SharePoint Online based on threat to network</span></span>

<span data-ttu-id="74c11-131">Erkennen von Bedrohungen wie **Man-in-the-Middle** im Netzwerk und Verhindern der Synchronisierung von Unternehmensdateien auf der Grundlage des Geräterisikos.</span><span class="sxs-lookup"><span data-stu-id="74c11-131">Detect threats like **Man-in-the-middle** in network, and prevent synchronization of corporate files based on the device risk.</span></span>

<span data-ttu-id="74c11-132">**Blockieren des Zugriffs auf SharePoint Online bei Erkennen von Bedrohungen für das Netzwerk**</span><span class="sxs-lookup"><span data-stu-id="74c11-132">**Block SharePoint Online when network threats are detected:**</span></span>

![Blockieren von SharePoint Online bei Erkennung von Bedrohungen für das Netzwerk](./media/network_spo_blocked_Zimperium.png)

<span data-ttu-id="74c11-134">**Zugriff nach Beseitigung gewährt:**</span><span class="sxs-lookup"><span data-stu-id="74c11-134">**Access granted on remediation:**</span></span>

![Zugriff erteilt nach der Behebung für Sharepoint-Beispiel](./media/network_spo_unblocked_Zimperium.png)

## <a name="supported-platforms"></a><span data-ttu-id="74c11-136">Unterstützte Plattformen</span><span class="sxs-lookup"><span data-stu-id="74c11-136">Supported platforms</span></span>

-   <span data-ttu-id="74c11-137">**Android 4.1 und höher**</span><span class="sxs-lookup"><span data-stu-id="74c11-137">**Android 4.1 and later**</span></span>

-   <span data-ttu-id="74c11-138">**iOS 8 und höher**</span><span class="sxs-lookup"><span data-stu-id="74c11-138">**iOS 8 and later**</span></span>

## <a name="prerequisites"></a><span data-ttu-id="74c11-139">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="74c11-139">Prerequisites</span></span>

-   <span data-ttu-id="74c11-140">Azure Active Directory Premium</span><span class="sxs-lookup"><span data-stu-id="74c11-140">Azure Active Directory Premium</span></span>

-   <span data-ttu-id="74c11-141">Microsoft Intune-Abonnement</span><span class="sxs-lookup"><span data-stu-id="74c11-141">Microsoft Intune subscription</span></span>

-   <span data-ttu-id="74c11-142">Zimperium Mobile Threat Defense-Abonnement</span><span class="sxs-lookup"><span data-stu-id="74c11-142">Zimperium Mobile Threat Defense subscription</span></span>

    -   <span data-ttu-id="74c11-143">Weitere Informationen finden Sie auf der [Zimperium-Website](https://www.zimperium.com/zips-mobile-ips).</span><span class="sxs-lookup"><span data-stu-id="74c11-143">See [Zimperium website](https://www.zimperium.com/zips-mobile-ips) for more information.</span></span>

## <a name="next-steps"></a><span data-ttu-id="74c11-144">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="74c11-144">Next steps</span></span>

- [<span data-ttu-id="74c11-145">Integrate Zimperium with Intune (Integrieren von Zimperium in Intune)</span><span class="sxs-lookup"><span data-stu-id="74c11-145">Integrate Zimperium with Intune</span></span>](zimperium-mtd-connector-integration.md)

- [<span data-ttu-id="74c11-146">Einrichten von Zimperium-Apps</span><span class="sxs-lookup"><span data-stu-id="74c11-146">Set up Zimperium apps</span></span>](mtd-apps-ios-app-configuration-policy-add-assign.md)

- [<span data-ttu-id="74c11-147">Erstellen einer Zimperium-Gerätekompatibilitätsrichtlinie</span><span class="sxs-lookup"><span data-stu-id="74c11-147">Create Zimperium device compliance policy</span></span>](mtd-device-compliance-policy-create.md)

- [<span data-ttu-id="74c11-148">Aktivieren des Zimperium MTD-Connectors</span><span class="sxs-lookup"><span data-stu-id="74c11-148">Enable Zimperium MTD connector</span></span>](mtd-connector-enable.md)
