---
title: Lookout Mobile Threat Defense-Connector
description: "Schützen Sie den Zugriff auf Unternehmensressourcen basierend auf dem Gerät, Netzwerk und Anwendungsrisiko mithilfe des Lookout Mobile Threat Defense-Connectors und Intune."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 01/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 725d9e40-e70c-461a-9413-72ff1b89a938
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: sandera
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 70fe5087dabae5d2eb7b3e60c3e716d3f0e927f8
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2017
---
# <a name="lookout-mobile-threat-defense-connector-with-intune"></a><span data-ttu-id="154a1-103">Lookout Mobile Threat Defense-Connector mit Intune</span><span class="sxs-lookup"><span data-stu-id="154a1-103">Lookout Mobile Threat Defense connector with Intune</span></span>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="154a1-104">Sie können den Zugriff mobiler Geräte auf Unternehmensressourcen basierend auf Risikobewertungen steuern, die von Lookout vorgenommen werden, einer Mobile Threat Defense-Lösung, die in Microsoft Intune integriert ist.</span><span class="sxs-lookup"><span data-stu-id="154a1-104">You can control mobile device access to corporate resources based on risk assessment conducted by Lookout, a Mobile Threat Defense solution integrated with Microsoft Intune.</span></span> <span data-ttu-id="154a1-105">Das Risiko wird basierend auf Telemetriedaten bewertet, die vom Lookout-Dienst auf Geräten erfasst werden, wie z.B.:</span><span class="sxs-lookup"><span data-stu-id="154a1-105">Risk is assessed based on telemetry collected from devices by the Lookout service including:</span></span>
- <span data-ttu-id="154a1-106">Sicherheitsrisiken des Betriebssystems</span><span class="sxs-lookup"><span data-stu-id="154a1-106">Operating system vulnerabilities</span></span>
- <span data-ttu-id="154a1-107">Installierte Apps, die Schadsoftware enthalten</span><span class="sxs-lookup"><span data-stu-id="154a1-107">Malicious apps installed</span></span>
- <span data-ttu-id="154a1-108">Netzwerkprofile mit böswilligen Absichten</span><span class="sxs-lookup"><span data-stu-id="154a1-108">Malicious network profiles</span></span>

<span data-ttu-id="154a1-109">Sie können Richtlinien für bedingten Zugriff basierend auf Risikobewertungen von Lookout konfigurieren, die mithilfe von Intune-Kompatibilitätsrichtlinien aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="154a1-109">You can  configure conditional access policies based on Lookout's risk assessment enabled through Intune compliance policies.</span></span> <span data-ttu-id="154a1-110">Mithilfe von Einstellungen können Sie basierend auf den erkannten Bedrohungen nicht kompatible Geräte zulassen oder blockieren.</span><span class="sxs-lookup"><span data-stu-id="154a1-110">Settings let you allow or block non-compliant devices based on detected threats.</span></span>

## <a name="how-do-intune-and-lookout-mobile-threat-defense-help-protect-company-resources"></a><span data-ttu-id="154a1-111">In welcher Form unterstützen Intune und Lookout Mobile Threat Defense den Schutz von Unternehmensressourcen?</span><span class="sxs-lookup"><span data-stu-id="154a1-111">How do Intune and Lookout Mobile Threat Defense help protect company resources?</span></span>
<span data-ttu-id="154a1-112">Die mobile Lookout-App **Lookout for Work** wird auf Mobilgeräten installiert und ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="154a1-112">Lookout’s mobile app, **Lookout for work**, is installed and run on mobile devices.</span></span> <span data-ttu-id="154a1-113">Diese App erfasst Telemetriedaten des Dateisystems, Netzwerkstapels sowie von Geräten und Anwendungen, sofern verfügbar, und sendet diese dann an den Lookout-Clouddienst, mit dessen Hilfe die Anfälligkeit des Geräts für mobile Bedrohungen bewertet wird.</span><span class="sxs-lookup"><span data-stu-id="154a1-113">This app captures file system, network stack, and device and application telemetry where available, then sends it to the Lookout cloud service to assess the device's risk for mobile threats.</span></span> <span data-ttu-id="154a1-114">Sie können die Klassifizierung der Risikostufe für Bedrohungen in der Lookout-Konsole gemäß Ihren Anforderungen ändern.</span><span class="sxs-lookup"><span data-stu-id="154a1-114">You can change risk level classifications for threats in the Lookout console to suit your requirements.</span></span>  

<span data-ttu-id="154a1-115">Die Konformitätsrichtlinie in Intune enthält eine Regel für Lookout Mobile Threat Defense, die auf der Risikobewertung durch Lookout basiert.</span><span class="sxs-lookup"><span data-stu-id="154a1-115">The compliance policy in Intune includes a rule for Lookout Mobile Threat Defense based on Lookout risk assessment.</span></span> <span data-ttu-id="154a1-116">Wenn diese Regel aktiviert ist, bewertet Intune die Gerätekompatibilität mit der von Ihnen aktivierten Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="154a1-116">When this rule is enabled, Intune evaluates device compliance with the policy that you enabled.</span></span>

<span data-ttu-id="154a1-117">Wird das Gerät als nicht kompatibel eingestuft, kann der Zugriff auf Ressourcen wie Exchange Online und SharePoint Online blockiert werden.</span><span class="sxs-lookup"><span data-stu-id="154a1-117">If the device is found non-compliant, access to resources like Exchange Online and SharePoint Online can blocked.</span></span> <span data-ttu-id="154a1-118">Benutzer auf blockierten Geräten erhalten Anweisungen zum Beheben des Problems und erneuten Erlangen des Zugriffs.</span><span class="sxs-lookup"><span data-stu-id="154a1-118">Users on blocked devices receive a steps to resolve the issue and regain access.</span></span> <span data-ttu-id="154a1-119">Die Anleitung wird in der Lookout for Work-App gestartet.</span><span class="sxs-lookup"><span data-stu-id="154a1-119">Guidance is launched from the Lookout for work app.</span></span>

## <a name="supported-platforms"></a><span data-ttu-id="154a1-120">Unterstützte Plattformen:</span><span class="sxs-lookup"><span data-stu-id="154a1-120">Supported platforms:</span></span>
<span data-ttu-id="154a1-121">Bei Registrierung in Intune werden die folgenden Plattformen für Lookout unterstützt:</span><span class="sxs-lookup"><span data-stu-id="154a1-121">The following platforms are supported for Lookout when enrolled in Intune:</span></span>
* <span data-ttu-id="154a1-122">**Android 4.1 und höher**</span><span class="sxs-lookup"><span data-stu-id="154a1-122">**Android 4.1 and later**</span></span>
* <span data-ttu-id="154a1-123">**iOS 8 und höher** Weitere Informationen zur Unterstützung von Plattformen und Sprachen finden Sie auf der [Lookout-Website](https://personal.support.lookout.com/hc/articles/114094140253).</span><span class="sxs-lookup"><span data-stu-id="154a1-123">**iOS 8 and later** For additional information about platform and language support, visit the [Lookout website](https://personal.support.lookout.com/hc/articles/114094140253).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="154a1-124">Voraussetzungen:</span><span class="sxs-lookup"><span data-stu-id="154a1-124">Prerequisites:</span></span>
* <span data-ttu-id="154a1-125">Microsoft Intune-Abonnement</span><span class="sxs-lookup"><span data-stu-id="154a1-125">Microsoft Intune subscription</span></span>
* <span data-ttu-id="154a1-126">Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="154a1-126">Azure Active Directory</span></span>
* <span data-ttu-id="154a1-127">Ein Enterprise-Abonnement für Lookout Mobile EndPoint Security.</span><span class="sxs-lookup"><span data-stu-id="154a1-127">Lookout Mobile Endpoint Security enterprise subscription</span></span>  

<span data-ttu-id="154a1-128">Weitere Informationen finden Sie unter [Lookout Mobile EndPoint Security](https://www.lookout.com/products/mobile-endpoint-security).</span><span class="sxs-lookup"><span data-stu-id="154a1-128">For more information, see [Lookout Mobile Endpoint Security](https://www.lookout.com/products/mobile-endpoint-security)</span></span>

## <a name="sample-scenarios"></a><span data-ttu-id="154a1-129">Beispielszenarien</span><span class="sxs-lookup"><span data-stu-id="154a1-129">Sample scenarios</span></span>
<span data-ttu-id="154a1-130">Es folgen einige gängige Szenarien:</span><span class="sxs-lookup"><span data-stu-id="154a1-130">Following are some common scenarios:</span></span>

### <a name="control-access-based-on-threats-from-malicious-apps"></a><span data-ttu-id="154a1-131">Steuern des Zugriffs basierend auf Bedrohungen durch Apps, die Schadsoftware enthalten</span><span class="sxs-lookup"><span data-stu-id="154a1-131">Control access based on threats from malicious apps</span></span>
<span data-ttu-id="154a1-132">Wenn Apps, die Schadsoftware enthalten, auf Geräten erkannt werden, können Sie Geräte an folgenden Aktionen hindern, bis die Bedrohung beseitigt ist:</span><span class="sxs-lookup"><span data-stu-id="154a1-132">When malicious apps such as malware are detected on devices, you can block devices from the following until the threat is resolved:</span></span>
* <span data-ttu-id="154a1-133">Herstellen einer Verbindung mit Unternehmens-E-Mail</span><span class="sxs-lookup"><span data-stu-id="154a1-133">Connecting to corporate e-mail</span></span>
* <span data-ttu-id="154a1-134">Synchronisieren von Unternehmensdateien mithilfe der OneDrive for Work-App</span><span class="sxs-lookup"><span data-stu-id="154a1-134">Syncing corporate files with the OneDrive for Work app</span></span>
* <span data-ttu-id="154a1-135">Zugreifen auf Unternehmens-Apps</span><span class="sxs-lookup"><span data-stu-id="154a1-135">Accessing company apps</span></span>

<span data-ttu-id="154a1-136">**Zugriff blockiert, wenn Apps mit Schadsoftware erkannt werden:**
![Diagramm, das eine Richtlinie für bedingten Zugriff zeigt, die den Zugriff blockiert, wenn ein Gerät aufgrund vorhandener Apps mit Schadsoftware als nicht kompatibel eingestuft wird](../media/mtp/malicious-apps-blocked.png)</span><span class="sxs-lookup"><span data-stu-id="154a1-136">**Block when malicious apps are detected:**
![diagram showing conditional access policy blocking access when device is determined to be non-compliant due to malicious apps on the device](../media/mtp/malicious-apps-blocked.png)</span></span>

<span data-ttu-id="154a1-137">**Zugriff erteilt nach der Sanierung:**</span><span class="sxs-lookup"><span data-stu-id="154a1-137">**Access granted on remediation:**</span></span>

![Diagramm, das die Richtlinie für bedingten Zugriff darstellt, die den Zugriff erteilt, nachdem das Gerät nach der Sanierung als kompatibel bewertet wurde](../media/mtp/malicious-apps-unblocked.png)

### <a name="control-access-based-on-threat-to-network"></a><span data-ttu-id="154a1-139">Steuern des Zugriffs basierend auf der Bedrohung für das Netzwerk</span><span class="sxs-lookup"><span data-stu-id="154a1-139">Control access based on threat to network</span></span>
<span data-ttu-id="154a1-140">Erkennen von Bedrohungen Ihres Netzwerks, wie etwa Man-in-the-Middle-Angriffe, und Schutz des Zugriffs auf WLANs auf der Grundlage des Geräterisikos.</span><span class="sxs-lookup"><span data-stu-id="154a1-140">Detect threats to your network such as Man-in-the-middle attacks and protect access to WiFi networks based on the device risk.</span></span>

<span data-ttu-id="154a1-141">**Zugriff auf das Netzwerk über WLAN blockiert:**
![Diagramm, das die Blockierung des WLAN-Zugriffs durch bedingten Zugriff auf Grundlage von Netzwerkbedrohungen zeigt](../media/mtp/network-wifi-blocked.png)</span><span class="sxs-lookup"><span data-stu-id="154a1-141">**Block network access through WiFi:**
![diagram showing conditional access blocking WiFi access based on network threats](../media/mtp/network-wifi-blocked.png)</span></span>

<span data-ttu-id="154a1-142">**Nach Korrektur erteilter Zugriff:**</span><span class="sxs-lookup"><span data-stu-id="154a1-142">**Access granted on remediation:**</span></span>

![Diagramm, das den Zugriff durch bedingten Zugriff nach der Beseitigung der Bedrohung erteilt](../media/mtp/network-wifi-unblocked.png)
### <a name="control-access-to-sharepoint-online-based-on-threat-to-network"></a><span data-ttu-id="154a1-144">Steuern des Zugriffs auf SharePoint Online basierend auf der Bedrohung für das Netzwerk</span><span class="sxs-lookup"><span data-stu-id="154a1-144">Control access to SharePoint Online based on threat to network</span></span>

<span data-ttu-id="154a1-145">Erkennen von Bedrohungen Ihres Netzwerks, wie etwa Man-in-the-Middle-Angriffen, und Verhindern der Synchronisierung von Unternehmensdateien auf der Grundlage des Geräterisikos.</span><span class="sxs-lookup"><span data-stu-id="154a1-145">Detect threats to your network such as Man-in-the-middle attacks, and prevent synchronization of corporate files based on the device risk.</span></span>

<span data-ttu-id="154a1-146">**Blockieren des Zugriffs auf SharePoint Online bei Erkennen von Bedrohungen für das Netzwerk**</span><span class="sxs-lookup"><span data-stu-id="154a1-146">**Block SharePoint Online when network threats are detected:**</span></span>

![Diagramm, das die Blockierung des Gerätezugriffs auf SharePoint Online mithilfe von bedingtem Zugriff basierend auf der Erkennung von Bedrohungen darstellt](../media/mtp/network-spo-blocked.png)


<span data-ttu-id="154a1-148">**Zugriff erteilt nach der Sanierung:**</span><span class="sxs-lookup"><span data-stu-id="154a1-148">**Access granted on remediation:**</span></span>

![Diagramm, das den bedingten Zugriff nach dem Beheben der Netzwerkbedrohung darstellt](../media/mtp/network-spo-unblocked.png)

## <a name="next-steps"></a><span data-ttu-id="154a1-150">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="154a1-150">Next steps</span></span>
<span data-ttu-id="154a1-151">Hier sind die wichtigsten Schritte, die Sie ausführen müssen, um diese Lösung zu implementieren:</span><span class="sxs-lookup"><span data-stu-id="154a1-151">Here are the main steps you must do to implement this solution:</span></span>
1.  [<span data-ttu-id="154a1-152">Ihr Lookout-Abonnement einrichten</span><span class="sxs-lookup"><span data-stu-id="154a1-152">Set up your Lookout subscription</span></span>](setup-your-lookout-mtd-subscription.md)
2.  [<span data-ttu-id="154a1-153">Lookout Mobile Threat Defense in Intune aktivieren</span><span class="sxs-lookup"><span data-stu-id="154a1-153">Enable Lookout Mobile Threat Defense in Intune</span></span>](enable-lookout-mtd-connection.md)
3.  [<span data-ttu-id="154a1-154">Die Lookout Mobile Threat Defense-App konfigurieren und bereitstellen</span><span class="sxs-lookup"><span data-stu-id="154a1-154">Configure and deploy Lookout Mobile Threat Defense app</span></span>](configure-deploy-lookout-for-work-app.md)
4.  [<span data-ttu-id="154a1-155">Die Lookout-Gerätekonformitätsrichtlinie konfigurieren</span><span class="sxs-lookup"><span data-stu-id="154a1-155">Configure Lookout device compliance policy</span></span>](create-lookout-device-compliance-policy.md)
5.  [<span data-ttu-id="154a1-156">Problembehandlung der Lookout Mobile Threat Defense-Integration durchführen</span><span class="sxs-lookup"><span data-stu-id="154a1-156">Troubleshoot Lookout Mobile Threat Defense integration</span></span>](/intune-classic/troubleshoot/device-threat-protection-troubleshooting)
