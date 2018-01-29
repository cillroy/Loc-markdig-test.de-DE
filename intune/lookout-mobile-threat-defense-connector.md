---
title: Lookout Mobile Threat Defense-Connector mit Intune
titlesuffix: Azure portal
description: Richten Sie den Lookout Mobile Threat Defense-Connector mit Intune ein.
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 06/09/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3a730a5d-2a90-42b0-aa28-aadfc7a18788
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 724e035e6105e2c81007ad89528203555a57a8a4
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2018
---
# <a name="lookout-mobile-threat-defense-connector-with-intune"></a><span data-ttu-id="b4490-103">Lookout Mobile Threat Defense-Connector mit Intune</span><span class="sxs-lookup"><span data-stu-id="b4490-103">Lookout Mobile Threat Defense connector with Intune</span></span>

<span data-ttu-id="b4490-104">Sie können den Zugriff mobiler Geräte auf Unternehmensressourcen basierend auf Risikobewertungen steuern, die von Lookout vorgenommen werden, einer Mobile Threat Defense-Lösung, die in Microsoft Intune integriert ist.</span><span class="sxs-lookup"><span data-stu-id="b4490-104">You can control mobile device access to corporate resources based on risk assessment conducted by Lookout, a Mobile Threat Defense solution integrated with Microsoft Intune.</span></span> <span data-ttu-id="b4490-105">Das Risiko wird basierend auf Telemetriedaten bewertet, die vom Lookout-Dienst auf Geräten erfasst werden, wie z.B.:</span><span class="sxs-lookup"><span data-stu-id="b4490-105">Risk is assessed based on telemetry collected from devices by the Lookout service including:</span></span>
- <span data-ttu-id="b4490-106">Sicherheitsrisiken des Betriebssystems</span><span class="sxs-lookup"><span data-stu-id="b4490-106">Operating system vulnerabilities</span></span>
- <span data-ttu-id="b4490-107">Installierte Apps, die Schadsoftware enthalten</span><span class="sxs-lookup"><span data-stu-id="b4490-107">Malicious apps installed</span></span>
- <span data-ttu-id="b4490-108">Netzwerkprofile mit böswilligen Absichten</span><span class="sxs-lookup"><span data-stu-id="b4490-108">Malicious network profiles</span></span>

<span data-ttu-id="b4490-109">Sie können Richtlinien für bedingten Zugriff basierend auf Risikobewertungen von Lookout konfigurieren, die mithilfe von Intune-Konformitätsrichtlinien aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="b4490-109">You can configure conditional access policies based on Lookout's risk assessment enabled through Intune compliance policies.</span></span> <span data-ttu-id="b4490-110">Mithilfe von Einstellungen können Sie basierend auf den erkannten Bedrohungen nicht kompatible Geräte zulassen oder blockieren.</span><span class="sxs-lookup"><span data-stu-id="b4490-110">Settings let you allow or block non-compliant devices based on detected threats.</span></span>

## <a name="how-do-intune-and-lookout-mobile-threat-defense-help-protect-company-resources"></a><span data-ttu-id="b4490-111">In welcher Form unterstützen Intune und Lookout Mobile Threat Defense den Schutz von Unternehmensressourcen?</span><span class="sxs-lookup"><span data-stu-id="b4490-111">How do Intune and Lookout Mobile Threat Defense help protect company resources?</span></span>
<span data-ttu-id="b4490-112">Die mobile Lookout-App **Lookout for Work** wird auf Mobilgeräten installiert und ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="b4490-112">Lookout’s mobile app, **Lookout for work**, is installed and run on mobile devices.</span></span> <span data-ttu-id="b4490-113">Diese App erfasst Telemetriedaten des Dateisystems, Netzwerkstapels sowie von Geräten und Anwendungen, sofern verfügbar, und sendet diese dann an den Lookout-Clouddienst, mit dessen Hilfe die Anfälligkeit des Geräts für mobile Bedrohungen bewertet wird.</span><span class="sxs-lookup"><span data-stu-id="b4490-113">This app captures file system, network stack, and device and application telemetry where available, then sends it to the Lookout cloud service to assess the device's risk for mobile threats.</span></span> <span data-ttu-id="b4490-114">Sie können die Klassifizierung der Risikostufe für Bedrohungen in der Lookout-Konsole gemäß Ihren Anforderungen ändern.</span><span class="sxs-lookup"><span data-stu-id="b4490-114">You can change risk level classifications for threats in the Lookout console to suit your requirements.</span></span>  

<span data-ttu-id="b4490-115">Die Konformitätsrichtlinie in Intune enthält eine Regel für Lookout Mobile Threat Defense, die auf der Risikobewertung durch Lookout basiert.</span><span class="sxs-lookup"><span data-stu-id="b4490-115">The compliance policy in Intune includes a rule for Lookout Mobile Threat Defense based on Lookout risk assessment.</span></span> <span data-ttu-id="b4490-116">Wenn diese Regel aktiviert ist, bewertet Intune die Gerätekompatibilität mit der von Ihnen aktivierten Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="b4490-116">When this rule is enabled, Intune evaluates device compliance with the policy that you enabled.</span></span>

<span data-ttu-id="b4490-117">Wird das Gerät als nicht kompatibel eingestuft, kann der Zugriff auf Ressourcen wie Exchange Online und SharePoint Online blockiert werden.</span><span class="sxs-lookup"><span data-stu-id="b4490-117">If the device is found non-compliant, access to resources like Exchange Online and SharePoint Online can blocked.</span></span> <span data-ttu-id="b4490-118">Benutzer auf blockierten Geräten erhalten Anweisungen zum Beheben des Problems und erneuten Erlangen des Zugriffs.</span><span class="sxs-lookup"><span data-stu-id="b4490-118">Users on blocked devices receive a steps to resolve the issue and regain access.</span></span> <span data-ttu-id="b4490-119">Die Anleitung wird in der Lookout for Work-App gestartet.</span><span class="sxs-lookup"><span data-stu-id="b4490-119">Guidance is launched from the Lookout for work app.</span></span>

## <a name="supported-platforms"></a><span data-ttu-id="b4490-120">Unterstützte Plattformen</span><span class="sxs-lookup"><span data-stu-id="b4490-120">Supported platforms</span></span>
<span data-ttu-id="b4490-121">Bei Registrierung in Intune werden die folgenden Plattformen für Lookout unterstützt:</span><span class="sxs-lookup"><span data-stu-id="b4490-121">The following platforms are supported for Lookout when enrolled in Intune:</span></span>
* <span data-ttu-id="b4490-122">**Android 4.1 und höher**</span><span class="sxs-lookup"><span data-stu-id="b4490-122">**Android 4.1 and later**</span></span>
* <span data-ttu-id="b4490-123">**iOS 8 und höher** Weitere Informationen zur Unterstützung von Plattformen und Sprachen finden Sie auf der [Lookout-Website](https://personal.support.lookout.com/hc/articles/114094140253).</span><span class="sxs-lookup"><span data-stu-id="b4490-123">**iOS 8 and later** For additional information about platform and language support, visit the [Lookout website](https://personal.support.lookout.com/hc/articles/114094140253).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="b4490-124">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="b4490-124">Prerequisites</span></span>
* <span data-ttu-id="b4490-125">Microsoft Intune-Abonnement</span><span class="sxs-lookup"><span data-stu-id="b4490-125">Microsoft Intune subscription</span></span>
* <span data-ttu-id="b4490-126">Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="b4490-126">Azure Active Directory</span></span>
* <span data-ttu-id="b4490-127">Ein Enterprise-Abonnement für Lookout Mobile EndPoint Security.</span><span class="sxs-lookup"><span data-stu-id="b4490-127">Lookout Mobile Endpoint Security enterprise subscription</span></span>  

<span data-ttu-id="b4490-128">Weitere Informationen finden Sie unter [Lookout Mobile EndPoint Security](https://www.lookout.com/products/mobile-endpoint-security).</span><span class="sxs-lookup"><span data-stu-id="b4490-128">For more information, see [Lookout Mobile Endpoint Security](https://www.lookout.com/products/mobile-endpoint-security)</span></span>

## <a name="sample-scenarios"></a><span data-ttu-id="b4490-129">Beispielszenarien</span><span class="sxs-lookup"><span data-stu-id="b4490-129">Sample scenarios</span></span>

<span data-ttu-id="b4490-130">Nachstehend sind die allgemeinen Szenarien bei Verwenden von Lookout Mobile Threat Defense mit Intune aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="b4490-130">Here are the common scenarios when using Lookout Mobile Threat Defense with Intune.</span></span>

### <a name="control-access-based-on-threats-from-malicious-apps"></a><span data-ttu-id="b4490-131">Steuern des Zugriffs basierend auf Bedrohungen durch Apps, die Schadsoftware enthalten</span><span class="sxs-lookup"><span data-stu-id="b4490-131">Control access based on threats from malicious apps</span></span>
<span data-ttu-id="b4490-132">Wenn Apps, die Schadsoftware enthalten, auf Geräten erkannt werden, können Sie Geräte an folgenden Aktionen hindern, bis die Bedrohung beseitigt ist:</span><span class="sxs-lookup"><span data-stu-id="b4490-132">When malicious apps such as malware are detected on devices, you can block devices from the following until the threat is resolved:</span></span>
* <span data-ttu-id="b4490-133">Herstellen einer Verbindung mit Unternehmens-E-Mail</span><span class="sxs-lookup"><span data-stu-id="b4490-133">Connecting to corporate e-mail</span></span>
* <span data-ttu-id="b4490-134">Synchronisieren von Unternehmensdateien mithilfe der OneDrive for Work-App</span><span class="sxs-lookup"><span data-stu-id="b4490-134">Syncing corporate files with the OneDrive for Work app</span></span>
* <span data-ttu-id="b4490-135">Zugreifen auf Unternehmens-Apps</span><span class="sxs-lookup"><span data-stu-id="b4490-135">Accessing company apps</span></span>

<span data-ttu-id="b4490-136">**Blockieren, wenn Apps mit Schadsoftware entdeckt werden:**</span><span class="sxs-lookup"><span data-stu-id="b4490-136">**Block when malicious apps are detected:**</span></span>

![Diagramm das zeigt, wie die Richtlinie für bedingten Zugriff den Zugriff blockiert, wenn das Gerät aufgrund von böswilligen Apps auf dem Gerät als nicht konform eingestuft wird](./media/malicious-apps-blocked.png)

<span data-ttu-id="b4490-138">**Zugriff nach Beseitigung gewährt:**</span><span class="sxs-lookup"><span data-stu-id="b4490-138">**Access granted on remediation:**</span></span>

![Diagramm, das die Richtlinie für bedingten Zugriff darstellt, die den Zugriff erteilt, nachdem das Gerät nach der Sanierung als kompatibel bewertet wurde](./media/malicious-apps-unblocked.png)

### <a name="control-access-based-on-threat-to-network"></a><span data-ttu-id="b4490-140">Steuern des Zugriffs basierend auf der Bedrohung für das Netzwerk</span><span class="sxs-lookup"><span data-stu-id="b4490-140">Control access based on threat to network</span></span>
<span data-ttu-id="b4490-141">Erkennen Sie Bedrohungen Ihres Netzwerks, wie etwa Man-in-the-Middle-Angriffe, und Schützen Sie den Zugriff auf WLANs auf der Grundlage des Geräterisikos.</span><span class="sxs-lookup"><span data-stu-id="b4490-141">Detect threats to your network such as man-in-the-middle attacks and protect access to WiFi networks based on the device risk.</span></span>

<span data-ttu-id="b4490-142">**Blockieren des Netzwerkzugriffs über WLAN:**</span><span class="sxs-lookup"><span data-stu-id="b4490-142">**Block network access through WiFi:**</span></span>

![Diagramm das zeigt, wie bedingter Zugriff den Zugriff auf WLAN basierend auf Netzwerkbedrohungen blockiert](./media/network-wifi-blocked.png)

<span data-ttu-id="b4490-144">**Zugriff nach Beseitigung gewährt:**</span><span class="sxs-lookup"><span data-stu-id="b4490-144">**Access granted on remediation:**</span></span>

![Diagramm, das den Zugriff durch bedingten Zugriff nach der Beseitigung der Bedrohung erteilt](./media/network-wifi-unblocked.png)
### <a name="control-access-to-sharepoint-online-based-on-threat-to-network"></a><span data-ttu-id="b4490-146">Steuern des Zugriffs auf SharePoint Online basierend auf der Bedrohung für das Netzwerk</span><span class="sxs-lookup"><span data-stu-id="b4490-146">Control access to SharePoint Online based on threat to network</span></span>

<span data-ttu-id="b4490-147">Erkennen von Bedrohungen Ihres Netzwerks, wie etwa Man-in-the-Middle-Angriffen, und Verhindern der Synchronisierung von Unternehmensdateien auf der Grundlage des Geräterisikos.</span><span class="sxs-lookup"><span data-stu-id="b4490-147">Detect threats to your network such as Man-in-the-middle attacks, and prevent synchronization of corporate files based on the device risk.</span></span>

<span data-ttu-id="b4490-148">**Blockieren des Zugriffs auf SharePoint Online bei Erkennen von Bedrohungen für das Netzwerk**</span><span class="sxs-lookup"><span data-stu-id="b4490-148">**Block SharePoint Online when network threats are detected:**</span></span>

![Diagramm, das die Blockierung des Gerätezugriffs auf SharePoint Online mithilfe von bedingtem Zugriff basierend auf der Erkennung von Bedrohungen darstellt](./media/network-spo-blocked.png)


<span data-ttu-id="b4490-150">**Zugriff nach Beseitigung gewährt:**</span><span class="sxs-lookup"><span data-stu-id="b4490-150">**Access granted on remediation:**</span></span>

![Diagramm, das den bedingten Zugriff nach dem Beheben der Netzwerkbedrohung darstellt](./media/network-spo-unblocked.png)

## <a name="next-steps"></a><span data-ttu-id="b4490-152">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="b4490-152">Next steps</span></span>
<span data-ttu-id="b4490-153">Hier sind die wichtigsten Schritte, die Sie ausführen müssen, um diese Lösung zu implementieren:</span><span class="sxs-lookup"><span data-stu-id="b4490-153">Here are the main steps you must do to implement this solution:</span></span>
1.  [<span data-ttu-id="b4490-154">Einrichten Ihrer Lookout-Integration</span><span class="sxs-lookup"><span data-stu-id="b4490-154">Set up your Lookout integration</span></span>](lookout-mtd-connector-integration.md)
2.  [<span data-ttu-id="b4490-155">Lookout Mobile Threat Defense in Intune aktivieren</span><span class="sxs-lookup"><span data-stu-id="b4490-155">Enable Lookout Mobile Threat Defense in Intune</span></span>](mtd-connector-enable.md)
3.  [<span data-ttu-id="b4490-156">Die Lookout for Work-App hinzufügen und zuweisen</span><span class="sxs-lookup"><span data-stu-id="b4490-156">Add and assign the Lookout for Work app</span></span>](mtd-apps-ios-app-configuration-policy-add-assign.md)
4.  [<span data-ttu-id="b4490-157">Die Lookout-Gerätekonformitätsrichtlinie konfigurieren</span><span class="sxs-lookup"><span data-stu-id="b4490-157">Configure Lookout device compliance policy</span></span>](mtd-device-compliance-policy-create.md)
