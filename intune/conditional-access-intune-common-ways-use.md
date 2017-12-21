---
title: "Bedingter Zugriff über Intune"
titlesuffix: Azure portal
description: "Gängige Möglichkeiten der Verwendung des bedingten Zugriffs in Intune"
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 11/14/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a0b8e55e-c3d8-4599-be25-dc10c1027b62
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: d3509dbf1bc0b415803bb003c342f5b5df69e235
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2017
---
# <a name="common-ways-to-use-conditional-access-with-intune"></a><span data-ttu-id="9d63e-103">Gängige Möglichkeiten der Verwendung des bedingten Zugriffs in Intune</span><span class="sxs-lookup"><span data-stu-id="9d63e-103">Common ways to use conditional access with Intune</span></span>

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="9d63e-104">Sie müssen die Intune-Konformitätsrichtlinie für mobile Geräte und die Intune-Funktionen für die mobile Anwendungsverwaltung (Mobile Application Management, MAM) konfigurieren, um die Konformität mit dem bedingten Zugriff in Ihrer Organisation zu erzwingen.</span><span class="sxs-lookup"><span data-stu-id="9d63e-104">You need to configure Intune mobile device compliance policy, and the Intune mobile application management (MAM) capabilities to drive conditional access compliance at your organization.</span></span> <span data-ttu-id="9d63e-105">Im Folgenden werden gängige Möglichkeiten für die Verwendung des bedingten Zugriffs mit Intune erläutert.</span><span class="sxs-lookup"><span data-stu-id="9d63e-105">Let’s talk about the common ways to use conditional access with Intune.</span></span>

## <a name="device-based-conditional-access"></a><span data-ttu-id="9d63e-106">Gerätebasierter bedingter Zugriff</span><span class="sxs-lookup"><span data-stu-id="9d63e-106">Device-based conditional access</span></span>

<span data-ttu-id="9d63e-107">Intune und Azure Active Directory stellen gemeinsam sicher, dass nur verwaltete und konforme Geräte Zugriff auf E-Mails, Office 365-Dienste, SaaS-Apps (Software-as-a-Service) und [lokale Apps](https://docs.microsoft.com/azure/active-directory/active-directory-application-proxy-get-started) erhalten.</span><span class="sxs-lookup"><span data-stu-id="9d63e-107">Intune and Azure Active Directory work together to make sure only managed and compliant devices are allowed access to email, Office 365 services, Software as a service (SaaS) apps, and [on-premises apps](https://docs.microsoft.com/azure/active-directory/active-directory-application-proxy-get-started).</span></span> <span data-ttu-id="9d63e-108">Zusätzlich können Sie in Azure Active Directory eine Richtlinie festlegen, die nur Computern, die der Domäne angehören, oder mobilen Geräten, die in Intune registriert sind, den Zugriff auf Office 365-Dienste erlaubt.</span><span class="sxs-lookup"><span data-stu-id="9d63e-108">Additionally, you can set a policy in Azure Active Directory to only enable computers that are domain-joined, or mobile devices that are enrolled in Intune to access Office 365 services.</span></span>

<span data-ttu-id="9d63e-109">Intune stellt Funktionen für Gerätekonformitätsrichtlinien bereit, die den Konformitätsstatus der Geräte bewerten.</span><span class="sxs-lookup"><span data-stu-id="9d63e-109">Intune provides device compliance policy capabilities that evaluate the compliance status of the devices.</span></span> <span data-ttu-id="9d63e-110">Der Konformitätsstatus wird an Azure Active Directory gemeldet, um die in Azure Active Directory erstellte Richtlinie für den bedingten Zugriff zu erzwingen, wenn der Benutzer versucht, auf Unternehmensressourcen zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="9d63e-110">The compliance status is reported to Azure Active Directory that uses it to enforce the conditional access policy created in Azure Active Directory when the user tries to access company resources.</span></span>

<span data-ttu-id="9d63e-111">Seit es das [neue Azure-Portal](https://docs.microsoft.com/intune-azure/introduction/what-is-microsoft-intune) gibt, werden gerätebasierte Richtlinien für den bedingten Zugriff für Exchange Online und andere Office 365-Produkte über das Azure-Portal konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="9d63e-111">Starting at the [new Azure portal](https://docs.microsoft.com/intune-azure/introduction/what-is-microsoft-intune), device-based conditional access policies for Exchange online and other Office 365 products are configured through the Azure portal.</span></span>

-   <span data-ttu-id="9d63e-112">Erfahren Sie mehr über den [bedingten Zugriff in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal).</span><span class="sxs-lookup"><span data-stu-id="9d63e-112">Learn more about [conditional access in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal).</span></span>

-   <span data-ttu-id="9d63e-113">Erfahren Sie mehr über die [Gerätekonformität in Intune](device-compliance.md).</span><span class="sxs-lookup"><span data-stu-id="9d63e-113">Learn more about [what is Intune device compliance](device-compliance.md).</span></span>

-   <span data-ttu-id="9d63e-114">Erfahren Sie mehr über den [Schutz von E-Mail-, Office 365- und anderen Diensten mithilfe des bedingen Zugriffs in Intune](https://docs.microsoft.com/intune-classic/deploy-use/restrict-access-to-email-and-o365-services-with-microsoft-intune).</span><span class="sxs-lookup"><span data-stu-id="9d63e-114">Learn more about [protecting e-mail, Office 365, and other services using conditional access with Intune](https://docs.microsoft.com/intune-classic/deploy-use/restrict-access-to-email-and-o365-services-with-microsoft-intune).</span></span>

### <a name="conditional-access-for-exchange-on-premises"></a><span data-ttu-id="9d63e-115">Bedingter Zugriff für Exchange lokal</span><span class="sxs-lookup"><span data-stu-id="9d63e-115">Conditional access for Exchange on-premises</span></span>

<span data-ttu-id="9d63e-116">Der bedingte Zugriff kann zum Zulassen oder Sperren des Zugriffs auf **Exchange lokal** basierend auf den Konformitätsrichtlinien für Geräte und dem Registrierungsstatus verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="9d63e-116">Conditional access can be used to allow or block access to **Exchange on-premises** based on the device compliance policies and enrollment state.</span></span> <span data-ttu-id="9d63e-117">Wenn der bedingte Zugriff zusammen mit einer Gerätekonformitätsrichtlinie verwendet wird, ist nur konformen Geräten der Zugriff auf Exchange lokal gestattet.</span><span class="sxs-lookup"><span data-stu-id="9d63e-117">When conditional access is used in combination with a device compliance policy, only compliant devices are allowed access to Exchange on-premises.</span></span>

<span data-ttu-id="9d63e-118">Sie können erweiterte Einstellungen wie die folgenden für den bedingten Zugriff konfigurieren, um eine präzisere Steuerung zu erzielen:</span><span class="sxs-lookup"><span data-stu-id="9d63e-118">You can configure advanced settings in conditional access for more granular control such as:</span></span>

-   <span data-ttu-id="9d63e-119">Zulassen oder Blockieren bestimmter Plattformen</span><span class="sxs-lookup"><span data-stu-id="9d63e-119">Allow or block certain platforms.</span></span>

-   <span data-ttu-id="9d63e-120">Sofortiges Blockieren von nicht über Intune verwalteten Geräten</span><span class="sxs-lookup"><span data-stu-id="9d63e-120">Immediately block devices that are not managed by Intune.</span></span>

<span data-ttu-id="9d63e-121">Jedes Gerät, mit dem auf Exchange lokal zugegriffen wird, wird auf Konformität überprüft, wenn Richtlinien für Gerätekonformität und bedingten Zugriff angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="9d63e-121">Any device used to access Exchange on-premises is checked for compliance when device compliance and conditional access policies are applied.</span></span>

<span data-ttu-id="9d63e-122">Wenn Geräte die Bedingungen nicht erfüllen, erhält der Benutzer Anweisungen zum Registrieren des Geräts und zum Beheben des Problems, das die Konformität des Geräts verhindert.</span><span class="sxs-lookup"><span data-stu-id="9d63e-122">When devices do not meet the conditions set, the end user is guided through the process of enrolling the device to fix the issue that is making the device non-compliant.</span></span>

#### <a name="how-conditional-access-for-exchange-on-premises-works"></a><span data-ttu-id="9d63e-123">Funktionsweise des bedingten Zugriffs für Exchange lokal</span><span class="sxs-lookup"><span data-stu-id="9d63e-123">How conditional access for Exchange on-premises works</span></span>

<span data-ttu-id="9d63e-124">Der Intune Exchange-Connector ruft alle EAS-Datensätze (Exchange Active Sync) ab, die auf dem Exchange-Server vorhanden sind, damit Intune diese Datensätze verwenden und den Intune-Gerätedatensätzen zuordnen kann.</span><span class="sxs-lookup"><span data-stu-id="9d63e-124">The Intune Exchange connector pulls in all the Exchange Active Sync (EAS) records that exist at the Exchange server so Intune can take these EAS records and map them to Intune device records.</span></span> <span data-ttu-id="9d63e-125">Bei diesen Datensätzen handelt es sich um Geräte, die bei Intune registriert sind und von Intune erkannt werden.</span><span class="sxs-lookup"><span data-stu-id="9d63e-125">These records are devices enrolled and recognized by Intune.</span></span> <span data-ttu-id="9d63e-126">Dieser Prozess erlaubt oder blockiert den E-Mail-Zugriff.</span><span class="sxs-lookup"><span data-stu-id="9d63e-126">This process allows or blocks e-mail access.</span></span>

<span data-ttu-id="9d63e-127">Wenn ein EAS-Datensatz neu und Intune noch nicht bekannt ist, gibt Intune ein Cmdlet aus, das den Zugriff auf E-Mails blockiert.</span><span class="sxs-lookup"><span data-stu-id="9d63e-127">If the EAS record is brand new, and Intune is not aware of it, Intune issues a command-let that blocks access to e-mail.</span></span> <span data-ttu-id="9d63e-128">Im Folgenden finden Sie weitere Details zur Funktionsweise dieses Prozesses:</span><span class="sxs-lookup"><span data-stu-id="9d63e-128">Here are more details on how this process works:</span></span>

![Flussdiagramm: Exchange lokal mit bedingtem Zugriff](./media/ca-intune-common-ways-1.png)

1.  <span data-ttu-id="9d63e-130">Ein Benutzer versucht, auf Unternehmens-E-Mails zuzugreifen, die in Exchange lokal 2010 SP1 oder höher gehostet werden.</span><span class="sxs-lookup"><span data-stu-id="9d63e-130">User tries to access corporate email, which is hosted on Exchange on-premises 2010 SP1 or later.</span></span>

2.  <span data-ttu-id="9d63e-131">Wenn das Gerät nicht durch Intune verwaltet wird, wird der E-Mail-Zugriff blockiert.</span><span class="sxs-lookup"><span data-stu-id="9d63e-131">If the device is not managed by Intune, it will be blocked access to email.</span></span> <span data-ttu-id="9d63e-132">Intune senden eine Benachrichtigung zur Blockierung an den EAS-Client.</span><span class="sxs-lookup"><span data-stu-id="9d63e-132">Intune sends block notification to the EAS client.</span></span>

3.  <span data-ttu-id="9d63e-133">EAS empfängt die Benachrichtigung, verschiebt das Gerät in die Quarantäne und sendet eine Quarantäne-E-Mail mit Schritten zur Behebung und entsprechenden Links, sodass der Benutzer das Gerät registrieren kann.</span><span class="sxs-lookup"><span data-stu-id="9d63e-133">EAS receives block notification, moves the device to quarantine, and sends the quarantine email with remediation steps that contain links so the users can enroll their devices.</span></span>

4.  <span data-ttu-id="9d63e-134">Der Prozess für den Arbeitsplatzbeitritt wird ausgeführt. Dies ist der erste Schritt, mit dem ein Gerät zur Verwaltung in Intune eingebunden wird.</span><span class="sxs-lookup"><span data-stu-id="9d63e-134">The Workplace join process happens, which is the first step to have the device managed by Intune.</span></span>

5.  <span data-ttu-id="9d63e-135">Das Gerät wird in Intune registriert.</span><span class="sxs-lookup"><span data-stu-id="9d63e-135">The device gets enrolled into Intune.</span></span>

6.  <span data-ttu-id="9d63e-136">Intune ordnet den EAS-Datensatz einem Gerätedatensatz zu und speichert den Konformitätszustand des Geräts.</span><span class="sxs-lookup"><span data-stu-id="9d63e-136">Intune maps the EAS record to a device record, and saves the device compliance state.</span></span>

7.  <span data-ttu-id="9d63e-137">Die EAS-Client-ID wird vom Azure AD Device Registration-Prozess registriert, der eine Beziehung zwischen dem Intune-Gerätedatensatz und der EAS-Client-ID erstellt.</span><span class="sxs-lookup"><span data-stu-id="9d63e-137">The EAS client ID gets registered by the Azure AD Device Registration process, which creates a relationship between the Intune device record, and the EAS client ID.</span></span>

8.  <span data-ttu-id="9d63e-138">Der Azure AD Device Registration-Prozess speichert die Informationen zum Gerätezustand.</span><span class="sxs-lookup"><span data-stu-id="9d63e-138">The Azure AD Device Registration saves the device state information.</span></span>

9.  <span data-ttu-id="9d63e-139">Wenn der Benutzer die Richtlinien für den bedingten Zugriff erfüllt, gibt Intune ein Cmdlet über den Intune Exchange-Connector aus, mit dem das Postfach synchronisiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="9d63e-139">If the user meets the conditional access policies, Intune issues a command-let through the Intune Exchange connector that allows the mailbox to sync.</span></span>

10. <span data-ttu-id="9d63e-140">Der Exchange-Server sendet eine Benachrichtigung an den EAS-Client, damit der Benachrichtigung auf die E-Mails zugreifen kann.</span><span class="sxs-lookup"><span data-stu-id="9d63e-140">Exchange server sends the notification to EAS client so the user can access e-mail.</span></span>

#### <a name="whats-the-intune-role"></a><span data-ttu-id="9d63e-141">Was ist die Intune-Rolle?</span><span class="sxs-lookup"><span data-stu-id="9d63e-141">What’s the Intune role?</span></span>

<span data-ttu-id="9d63e-142">Intune bewertet und verwaltet den Gerätezustand.</span><span class="sxs-lookup"><span data-stu-id="9d63e-142">Intune evaluates and manage the device state.</span></span>

#### <a name="whats-the-exchange-server-role"></a><span data-ttu-id="9d63e-143">Was ist die Exchange-Server-Rolle?</span><span class="sxs-lookup"><span data-stu-id="9d63e-143">What’s the Exchange server role?</span></span>

<span data-ttu-id="9d63e-144">Der Exchange-Server stellt die API und die Infrastruktur bereit, um Geräte in die Quarantäne zu verschieben.</span><span class="sxs-lookup"><span data-stu-id="9d63e-144">Exchange server provides API and infrastructure to move devices to its quarantine.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9d63e-145">Denken Sie daran, dass dem Benutzer, der das Gerät verwendet, ein Konformitätsprofil zugewiesen sein muss, damit das Gerät hinsichtlich der Konformität bewertet werden kann.</span><span class="sxs-lookup"><span data-stu-id="9d63e-145">Keep in mind that the user who’s using the device must have a compliance profile assigned to them so the device to be evaluated for compliance.</span></span> <span data-ttu-id="9d63e-146">Wenn keine Konformitätsrichtlinie für den Benutzer bereitgestellt wird, wird das Gerät als konform behandelt, und es werden keine Zugriffsbeschränkungen angewendet.</span><span class="sxs-lookup"><span data-stu-id="9d63e-146">If no compliance policy is deployed to the user, the device is treated as compliant and no access restrictions are applied.</span></span>

### <a name="conditional-access-based-on-network-access-control"></a><span data-ttu-id="9d63e-147">Bedingter Zugriff basierend auf der Netzwerkzugriffssteuerung</span><span class="sxs-lookup"><span data-stu-id="9d63e-147">Conditional access based on network access control</span></span>

<span data-ttu-id="9d63e-148">Intune ist in Partnerlösungen wie Cisco ISE, Aruba Clear Pass und Citrix NetScaler integriert, um die Zugriffssteuerung basierend auf der Intune-Registrierung und dem Konformitätszustand des Geräts bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="9d63e-148">Intune integrated with partners like Cisco ISE, Aruba Clear Pass, and Citrix NetScaler to provide access controls based on the Intune enrollment and the device compliance state.</span></span>

<span data-ttu-id="9d63e-149">Benutzern kann der Zugriff auf unternehmenseigene WLAN- oder VPN-Ressourcen erlaubt oder verweigert werden, je nachdem, ob das verwendete Gerät verwaltet wird und den Intune-Konformitätsrichtlinien für Geräte entspricht.</span><span class="sxs-lookup"><span data-stu-id="9d63e-149">Users can be allowed or denied access when trying to access corporate Wi-Fi or VPN resources based on whether the device is managed and compliant with Intune device compliance policies.</span></span>

-   <span data-ttu-id="9d63e-150">Erfahren Sie mehr über die [NAC-Integration in Intune](network-access-control-integrate.md).</span><span class="sxs-lookup"><span data-stu-id="9d63e-150">Learn more about the [NAC integration with Intune](network-access-control-integrate.md).</span></span>

### <a name="conditional-access-based-on-device-risk"></a><span data-ttu-id="9d63e-151">Bedingter Zugriff basierend auf dem Geräterisiko</span><span class="sxs-lookup"><span data-stu-id="9d63e-151">Conditional access based on device risk</span></span>

<span data-ttu-id="9d63e-152">Intune arbeitet mit MTD-Anbietern (Mobile Threat Defense) zusammen, um eine Sicherheitslösung bereitzustellen, die Schadsoftware, Trojaner und andere Bedrohungen auf mobilen Geräten erkennt.</span><span class="sxs-lookup"><span data-stu-id="9d63e-152">Intune partnered with Mobile Threat Defense vendors that provides a security solution to detect malwares, Trojans, and other threats on mobile devices.</span></span>

#### <a name="how-the-intune-and-mobile-threat-defense-integration-works"></a><span data-ttu-id="9d63e-153">Funktionsweise von Intune und der Integration von MTD-Lösungen</span><span class="sxs-lookup"><span data-stu-id="9d63e-153">How the Intune and Mobile Threat Defense integration works</span></span>

<span data-ttu-id="9d63e-154">Wenn der Mobile Threat Defense-Agent auf mobilen Geräten installiert ist, kann dieser Benachrichtigungen zum Konformitätszustand an Intune zurücksenden, um zu melden, ob auf dem mobilen Gerät eine Bedrohung gefunden wurde.</span><span class="sxs-lookup"><span data-stu-id="9d63e-154">When mobile devices have the Mobile Threat Defense agent installed, the agent can send compliance state messages back to Intune reporting if a threat has been found in the mobile device itself.</span></span>

<span data-ttu-id="9d63e-155">Die Integration von Intune und Mobile Threat Defense-Lösungen spielt eine wichtige Rolle bei Entscheidungen zum bedingten Zugriff basierend auf dem Geräterisiko.</span><span class="sxs-lookup"><span data-stu-id="9d63e-155">The Intune and mobile threat defense integration plays a factor at the conditional access decisions based on device risk.</span></span>

-   <span data-ttu-id="9d63e-156">Erfahren Sie mehr über [Intune Mobile Threat Defense](https://docs.microsoft.com/intune-classic/deploy-use/mobile-threat-defense).</span><span class="sxs-lookup"><span data-stu-id="9d63e-156">Learn more about [Intune mobile threat defense](https://docs.microsoft.com/intune-classic/deploy-use/mobile-threat-defense).</span></span>

### <a name="conditional-access-for-windows-pcs"></a><span data-ttu-id="9d63e-157">Bedingter Zugriff für Windows-PCs</span><span class="sxs-lookup"><span data-stu-id="9d63e-157">Conditional access for Windows PCs</span></span>

<span data-ttu-id="9d63e-158">Der bedingte Zugriff für PCs bietet eine ähnliche Funktionalität wie für mobile Geräte.</span><span class="sxs-lookup"><span data-stu-id="9d63e-158">Conditional access for PCs provide similar capabilities available for mobile devices.</span></span> <span data-ttu-id="9d63e-159">Im Folgenden finden Sie Informationen zu den verschiedenen Möglichkeiten, den bedingten Zugriff beim Verwalten von PCs mit Intune zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="9d63e-159">Let’s talk about the ways you can use conditional access when managing PCs with Intune.</span></span>

#### <a name="corporate-owned"></a><span data-ttu-id="9d63e-160">Unternehmenseigene Geräte</span><span class="sxs-lookup"><span data-stu-id="9d63e-160">Corporate-owned</span></span>

-   <span data-ttu-id="9d63e-161">**In die lokale AD-Domäne eingebunden**: Dies ist die häufigste Bereitstellungsoption für bedingen Zugriff für Organisationen, denen die Tatsache genügt, dass sie ihre PCs bereits über AD-Gruppenrichtlinien und/oder mit System Center Configuration Manager verwalten.</span><span class="sxs-lookup"><span data-stu-id="9d63e-161">**On premises AD domain joined:** This has been the most common conditional access deployment option for organizations, whose are reasonable comfortable with the fact they’re already managing their PCs through AD group policies and/or with System Center Configuration Manager.</span></span>

-   <span data-ttu-id="9d63e-162">**In die Azure AD-Domäne eingebunden und über Intune verwaltet**: Diese Option zielt üblicherweise auf CYOD-Bereitstellungen (Choose Your Own Device) und Roamingszenarien mit Laptops ab, die selten mit dem Unternehmensnetzwerk verbunden sind.</span><span class="sxs-lookup"><span data-stu-id="9d63e-162">**Azure AD domain joined and Intune management:** This scenario is typically geared to Choose Your Own Device (CYOD), and roaming laptop scenarios where these devices are rarely connected to corporate-network.</span></span> <span data-ttu-id="9d63e-163">Das Gerät tritt der Azure AD-Domäne bei und wird bei Intune registriert. Dadurch entsteht keinerlei Abhängigkeit von einer lokalen Active Directory-Instanz oder Domänencontrollern.</span><span class="sxs-lookup"><span data-stu-id="9d63e-163">The device joins to the Azure AD and gets enrolled to Intune, which removes any dependency on on-premises AD, and domain controllers.</span></span> <span data-ttu-id="9d63e-164">Diese Option kann als Kriterium für den bedingten Zugriff auf Unternehmensressourcen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="9d63e-164">This can be used as a conditional access criteria when accessing corporate resources.</span></span>

-   <span data-ttu-id="9d63e-165">**In die AD-Domäne eingebunden und System Center Configuration Manager**: Im aktuellen Branch stellt System Center Configuration Manager Funktionen für den bedingten Zugriff bereit, die bestimmte Konformitätskriterien auswerten können. Zusätzlich muss der PC in die Domäne eingebunden sein:</span><span class="sxs-lookup"><span data-stu-id="9d63e-165">**AD domain joined and System Center Configuration Manager:** As of current branch, System Center Configuration Manager provides conditional access capabilities that can evaluate specific compliance criteria, in addition to be a domain-joined PC:</span></span>

    -   <span data-ttu-id="9d63e-166">Ist der PC verschlüsselt?</span><span class="sxs-lookup"><span data-stu-id="9d63e-166">Is the PC encrypted?</span></span>

    -   <span data-ttu-id="9d63e-167">Ist Schadsoftware installiert?</span><span class="sxs-lookup"><span data-stu-id="9d63e-167">Is malware installed?</span></span> <span data-ttu-id="9d63e-168">Ist der PC auf dem neuesten Stand?</span><span class="sxs-lookup"><span data-stu-id="9d63e-168">Is it up-to-date?</span></span>

    -   <span data-ttu-id="9d63e-169">Wurde das Gerät per Jailbreak oder Rooting manipuliert?</span><span class="sxs-lookup"><span data-stu-id="9d63e-169">Is the device jailbroken or rooted?</span></span>

#### <a name="bring-your-own-device-byod"></a><span data-ttu-id="9d63e-170">Bring Your Own Device (BYOD)</span><span class="sxs-lookup"><span data-stu-id="9d63e-170">Bring your own device (BYOD)</span></span>

-   <span data-ttu-id="9d63e-171">**Arbeitsplatzbeitritt und Intune-Verwaltung**: Bei dieser Option können Benutzer ihre persönlichen Geräte einbinden, um auf Unternehmensressourcen und -dienste zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="9d63e-171">**Workplace join and Intune management:** Here the user can join their personal devices to access corporate resources and services.</span></span> <span data-ttu-id="9d63e-172">Sie können den Arbeitsplatzbeitritt verwenden und Geräte bei Intune registrieren, um Richtlinien auf Geräteebene zu erhalten. Dies ist eine weitere Option zum Auswerten von Kriterien für den bedingten Zugriff.</span><span class="sxs-lookup"><span data-stu-id="9d63e-172">You can use Workplace join and enroll devices into Intune to receive device-level policies, which is also another option to evaluate conditional access criteria.</span></span>

## <a name="app-based-conditional-access"></a><span data-ttu-id="9d63e-173">App-basierter bedingter Zugriff</span><span class="sxs-lookup"><span data-stu-id="9d63e-173">App-based conditional access</span></span>

<span data-ttu-id="9d63e-174">Intune und Azure Active Directory stellen gemeinsam sicher, dass nur verwaltete Geräte auf Unternehmens-E-Mails oder andere Office 365-Dienste zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="9d63e-174">Intune and Azure Active Directory work together to make sure only managed apps can access corporate e-mail or other Office 365 services.</span></span>

-   <span data-ttu-id="9d63e-175">Erfahren Sie mehr über den [App-basierten bedingten Zugriff mit Intune](app-based-conditional-access-intune.md).</span><span class="sxs-lookup"><span data-stu-id="9d63e-175">Learn more about [app-based conditional access with Intune](app-based-conditional-access-intune.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="9d63e-176">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="9d63e-176">Next steps</span></span>

[<span data-ttu-id="9d63e-177">Konfigurieren des bedingten Zugriffs in Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="9d63e-177">How to configure conditional access in Azure Active Directory</span></span>](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal)

<span data-ttu-id="9d63e-178">[Installieren des lokalen Exchange Connectors für Intune](https://docs.microsoft.com/intune/exchange-connector-install)</span><span class="sxs-lookup"><span data-stu-id="9d63e-178">[How to install on-premises Exchange connector with Intune](https://docs.microsoft.com/intune/exchange-connector-install).</span></span>

[<span data-ttu-id="9d63e-179">Erstellen einer Richtlinie für den bedingten Zugriff auf Exchange lokal</span><span class="sxs-lookup"><span data-stu-id="9d63e-179">How to create a conditional access policy for Exchange on-premises</span></span>](conditional-access-exchange-create.md)
