---
title: "Skycure-Connector für Intune"
titlesuffix: Azure portal
description: Skycure-Connectorintegration in Intune.
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 06/09/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: df4ce3f6-a093-432c-ab86-7a83865e389e
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 47df2c4a909c397ac5a6c0f736d11344de44736e
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2017
---
# <a name="skycure-mobile-threat-defense-connector"></a><span data-ttu-id="8adba-103">Skycure Mobile Threat Defense-Connector</span><span class="sxs-lookup"><span data-stu-id="8adba-103">Skycure Mobile Threat Defense connector</span></span>

<span data-ttu-id="8adba-104">Sie können den Zugriff mobiler Geräte auf Unternehmensressourcen mit bedingtem Zugriff basierend auf Risikobewertungen steuern, die von Skycure vorgenommen werden, einer Mobile Threat Defense-Lösung, die mit Microsoft Intune zusammenarbeitet.</span><span class="sxs-lookup"><span data-stu-id="8adba-104">You can control mobile device access to corporate resources using conditional access based on risk assessment conducted by Skycure, a mobile threat defense solution that integrates with Microsoft Intune.</span></span> <span data-ttu-id="8adba-105">Das Risiko wird basierend auf Telemetriedaten von Geräten bewertet, auf denen Skycure ausgeführt wird, wie z.B.:</span><span class="sxs-lookup"><span data-stu-id="8adba-105">Risk is assessed based on telemetry collected from devices running Skycure, including:</span></span>

-   <span data-ttu-id="8adba-106">Physische Verteidigung</span><span class="sxs-lookup"><span data-stu-id="8adba-106">Physical defense</span></span>

-   <span data-ttu-id="8adba-107">Netzwerkverteidigung</span><span class="sxs-lookup"><span data-stu-id="8adba-107">Network defense</span></span>

-   <span data-ttu-id="8adba-108">Anwendungsverteidigung</span><span class="sxs-lookup"><span data-stu-id="8adba-108">Application defense</span></span>

-   <span data-ttu-id="8adba-109">Verteidigung gegen Sicherheitsrisiken</span><span class="sxs-lookup"><span data-stu-id="8adba-109">Vulnerabilities defense</span></span>

<span data-ttu-id="8adba-110">Sie können Richtlinien für bedingten Zugriff basierend auf der Skycure-Risikobewertung konfigurieren, die über Intune-Gerätekompatibilitätsrichtlinien aktiviert werden, und so anhand der erkannten Bedrohungen nicht kompatible Geräte für den Zugriff auf Unternehmensressourcen zulassen oder blockieren.</span><span class="sxs-lookup"><span data-stu-id="8adba-110">You can configure conditional access policies based on Skycure risk assessment enabled through Intune device compliance policies, which you can use to allow or block non-compliant devices to access corporate resources based on detected threats.</span></span>

## <a name="how-do-intune-and-skycure-help-protect-your-company-resources"></a><span data-ttu-id="8adba-111">Wie helfen Intune und Skycure beim Schutz von Unternehmensressourcen?</span><span class="sxs-lookup"><span data-stu-id="8adba-111">How do Intune and Skycure help protect your company resources?</span></span>

<span data-ttu-id="8adba-112">Die mobile Skycure-App für Android oder iOS erfasst Telemetriedaten des Dateisystems, Netzwerkstapels sowie von Geräten und Anwendungen, sofern verfügbar, und sendet diese dann an den Skycure-Clouddienst, mit dessen Hilfe die Anfälligkeit des Geräts für mobile Bedrohungen bewertet wird.</span><span class="sxs-lookup"><span data-stu-id="8adba-112">Skycure mobile app for Android or iOS captures file system, network stack, device and application telemetry where available, then sends it to the Skycure cloud service to assess the device's risk for mobile threats.</span></span>

<span data-ttu-id="8adba-113">Die Intune-Gerätekompatibilitätsrichtlinie enthält eine Regel für Skycure Mobile Threat Defense, die auf der Skycure-Risikobewertung basiert.</span><span class="sxs-lookup"><span data-stu-id="8adba-113">The Intune device compliance policy includes a rule for Skycure Mobile Threat Defense, which is based on the Skycure risk assessment.</span></span> <span data-ttu-id="8adba-114">Wenn diese Regel aktiviert ist, bewertet Intune die Gerätekompatibilität mit der von Ihnen aktivierten Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="8adba-114">When this rule is enabled, Intune evaluates device compliance with the policy that you enabled.</span></span>

<span data-ttu-id="8adba-115">Wird das Gerät als nicht kompatibel eingestuft, wird der Zugriff auf Ressourcen wie Exchange Online und SharePoint Online blockiert.</span><span class="sxs-lookup"><span data-stu-id="8adba-115">If the device is found non-compliant, access to resources like Exchange Online and SharePoint Online are blocked.</span></span> <span data-ttu-id="8adba-116">Benutzer auf blockierten Geräten erhalten Anleitungen von der mobilen Skycure-App, um das Problem zu beheben und den Zugriff auf Unternehmensressourcen zurückzuerlangen.</span><span class="sxs-lookup"><span data-stu-id="8adba-116">Users on blocked devices receive guidance from the Skycure mobile app to resolve the issue and regain access to corporate resources.</span></span>

<span data-ttu-id="8adba-117">Intune unterstützt zwei Modi der Integration mit Skycure:</span><span class="sxs-lookup"><span data-stu-id="8adba-117">Intune supports two modes of integration with Skycure:</span></span>

-   <span data-ttu-id="8adba-118">Die **grundlegende Installation** ist ein schreibgeschützter Modus, der die Sichtbarkeit von Skycure für Geräte in Intune zulässt.</span><span class="sxs-lookup"><span data-stu-id="8adba-118">**Basic setup** which is a read only mode that allows Skycure visibility for devices in Intune.</span></span>

-   <span data-ttu-id="8adba-119">Die **vollständige Integration** ermöglicht Skycure, Details zu Geräterisiken und Sicherheitsvorfällen an Intune zu melden.</span><span class="sxs-lookup"><span data-stu-id="8adba-119">**Full integration** which allows Skycure to report device risk and security incident details to Intune.</span></span>

## <a name="sample-scenarios"></a><span data-ttu-id="8adba-120">Beispielszenarien</span><span class="sxs-lookup"><span data-stu-id="8adba-120">Sample scenarios</span></span>

<span data-ttu-id="8adba-121">Hier einige gängige Szenarios:</span><span class="sxs-lookup"><span data-stu-id="8adba-121">Here are some common scenarios:</span></span>

### <a name="control-access-based-on-threats-from-malicious-apps"></a><span data-ttu-id="8adba-122">Steuern des Zugriffs basierend auf Bedrohungen durch Apps, die Schadsoftware enthalten</span><span class="sxs-lookup"><span data-stu-id="8adba-122">Control access based on threats from malicious apps</span></span>

<span data-ttu-id="8adba-123">Wenn Apps, die Schadsoftware enthalten, auf Geräten erkannt werden, können Sie Geräte blockieren, bis die Bedrohung beseitigt ist:</span><span class="sxs-lookup"><span data-stu-id="8adba-123">When malicious apps such as malware are detected on devices, you can block devices until the threat is resolved:</span></span>

-   <span data-ttu-id="8adba-124">Herstellen einer Verbindung mit Unternehmens-E-Mail</span><span class="sxs-lookup"><span data-stu-id="8adba-124">Connecting to corporate e-mail</span></span>

-   <span data-ttu-id="8adba-125">Synchronisieren von Unternehmensdateien mithilfe der OneDrive for Work-App</span><span class="sxs-lookup"><span data-stu-id="8adba-125">Syncing corporate files with the OneDrive for Work app</span></span>

-   <span data-ttu-id="8adba-126">Zugreifen auf Unternehmens-Apps</span><span class="sxs-lookup"><span data-stu-id="8adba-126">Accessing company apps</span></span>

<span data-ttu-id="8adba-127">**Blockieren, wenn Apps mit Schadsoftware entdeckt werden:**</span><span class="sxs-lookup"><span data-stu-id="8adba-127">**Block when malicious apps are detected:**</span></span>

![Apps mit Schadsoftware entdeckt](./media/skycure-arch-1.png)

<span data-ttu-id="8adba-129">**Zugriff nach Beseitigung gewährt:**</span><span class="sxs-lookup"><span data-stu-id="8adba-129">**Access granted on remediation:**</span></span>

![Apps mit Schadsoftware entdeckt, Zugriff gewährt](./media/skycure-arch-2.png)

### <a name="control-access-based-on-threat-to-network"></a><span data-ttu-id="8adba-131">Steuern des Zugriffs basierend auf der Bedrohung für das Netzwerk</span><span class="sxs-lookup"><span data-stu-id="8adba-131">Control access based on threat to network</span></span>

<span data-ttu-id="8adba-132">Erkennen Sie Bedrohungen wie **Man-in-the-Middle** im Netzwerk, und schützen Sie den Zugriff auf WLAN-Netzwerke auf der Grundlage des Geräterisikos.</span><span class="sxs-lookup"><span data-stu-id="8adba-132">Detect threats like **Man-in-the-middle** in network, and protect access to Wi-Fi networks based on the device risk.</span></span>

<span data-ttu-id="8adba-133">**Blockieren des Netzwerkzugriffs über WLAN:**</span><span class="sxs-lookup"><span data-stu-id="8adba-133">**Block network access through Wi-Fi:**</span></span>

![Blockieren des Netzwerkzugriffs über WLAN](./media/skycure-arch-3.png)

<span data-ttu-id="8adba-135">**Zugriff nach Beseitigung gewährt:**</span><span class="sxs-lookup"><span data-stu-id="8adba-135">**Access granted on remediation:**</span></span>

![Zugriff erteilt nach der Behebung](./media/skycure-arch-4.png)

### <a name="control-access-to-sharepoint-online-based-on-threat-to-network"></a><span data-ttu-id="8adba-137">Steuern des Zugriffs auf SharePoint Online basierend auf der Bedrohung für das Netzwerk</span><span class="sxs-lookup"><span data-stu-id="8adba-137">Control access to SharePoint Online based on threat to network</span></span>

<span data-ttu-id="8adba-138">Erkennen von Bedrohungen wie **Man-in-the-Middle** im Netzwerk und Verhindern der Synchronisierung von Unternehmensdateien auf der Grundlage des Geräterisikos.</span><span class="sxs-lookup"><span data-stu-id="8adba-138">Detect threats like **Man-in-the-middle** in network, and prevent synchronization of corporate files based on the device risk.</span></span>

<span data-ttu-id="8adba-139">**Blockieren des Zugriffs auf SharePoint Online bei Erkennen von Bedrohungen für das Netzwerk**</span><span class="sxs-lookup"><span data-stu-id="8adba-139">**Block SharePoint Online when network threats are detected:**</span></span>

![Blockieren von SharePoint Online bei Erkennung von Bedrohungen für das Netzwerk](./media/skycure-arch-5.png)

<span data-ttu-id="8adba-141">**Zugriff nach Beseitigung gewährt:**</span><span class="sxs-lookup"><span data-stu-id="8adba-141">**Access granted on remediation:**</span></span>

![Zugriff erteilt nach der Behebung für Sharepoint-Beispiel](./media/skycure-arch-6.png)

## <a name="supported-platforms"></a><span data-ttu-id="8adba-143">Unterstützte Plattformen</span><span class="sxs-lookup"><span data-stu-id="8adba-143">Supported platforms</span></span>

-   <span data-ttu-id="8adba-144">**Android 4.1 und höher**</span><span class="sxs-lookup"><span data-stu-id="8adba-144">**Android 4.1 and later**</span></span>

-   <span data-ttu-id="8adba-145">**iOS 8 und höher**</span><span class="sxs-lookup"><span data-stu-id="8adba-145">**iOS 8 and later**</span></span>

## <a name="pre-requisites"></a><span data-ttu-id="8adba-146">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="8adba-146">Pre-requisites</span></span>

-   <span data-ttu-id="8adba-147">Azure Active Directory Premium</span><span class="sxs-lookup"><span data-stu-id="8adba-147">Azure Active Directory Premium</span></span>

-   <span data-ttu-id="8adba-148">Microsoft Intune-Abonnement</span><span class="sxs-lookup"><span data-stu-id="8adba-148">Microsoft Intune subscription</span></span>

-   <span data-ttu-id="8adba-149">Skycure Mobile Threat Defense-Abonnement</span><span class="sxs-lookup"><span data-stu-id="8adba-149">Skycure Mobile Threat Defense subscription</span></span>

<span data-ttu-id="8adba-150">Weitere Informationen erhalten Sie auf der [Skycure-Website](https://www.skycure.com/skycure-microsoft-integration/).</span><span class="sxs-lookup"><span data-stu-id="8adba-150">For more information, check [Skycure website](https://www.skycure.com/skycure-microsoft-integration/).</span></span>

## <a name="next-steps"></a><span data-ttu-id="8adba-151">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="8adba-151">Next steps</span></span>

<span data-ttu-id="8adba-152">Dies sind die Schritte, die Sie für die Integration von Intune und Skycure durchführen müssen:</span><span class="sxs-lookup"><span data-stu-id="8adba-152">Here are the steps you need to complete to integrate Intune with Skycure:</span></span>

- [<span data-ttu-id="8adba-153">Einrichten der Skycure-Integration in Intune</span><span class="sxs-lookup"><span data-stu-id="8adba-153">Set up Skycure integration with Intune</span></span>](skycure-mtd-connector-integration.md)

- [<span data-ttu-id="8adba-154">Hinzufügen und Zuweisen von Skycure-Apps, der Microsoft Authenticator-App und der iOS-Konfigurationsrichtlinie</span><span class="sxs-lookup"><span data-stu-id="8adba-154">Add and assign Skycure apps, Microsoft Authenticator and iOS app configuration policy</span></span>](mtd-apps-ios-app-configuration-policy-add-assign.md)

- [<span data-ttu-id="8adba-155">Erstellen einer Skycure-Gerätekompatibilitätsrichtlinie mit Intune</span><span class="sxs-lookup"><span data-stu-id="8adba-155">Create Skycure device compliance policy with Intune</span></span>](mtd-device-compliance-policy-create.md)

- [<span data-ttu-id="8adba-156">Aktivieren des Skycure MTP-Connectors in Intune</span><span class="sxs-lookup"><span data-stu-id="8adba-156">Enable Skycure MTD connector in Intune</span></span>](mtd-connector-enable.md)
