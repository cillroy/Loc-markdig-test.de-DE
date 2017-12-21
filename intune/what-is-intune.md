---
title: "Einführung in Intune im Azure-Portal"
titlesuffix: Azure portal
description: "Lernen Sie die Grundlagen von Intune im Azure-Portal kennen, und erfahren Sie, wie es Ihnen beim Verwalten Ihrer Geräte helfen kann."
keywords: 
author: arob98
ms.author: angrobe
nmanager: angrobe
ms.date: 10/30/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4a085264-232a-4af0-97f1-747496c44517
ms.suite: ems
ms.custom: 
ms.openlocfilehash: ae9924cc23d85322c18d7637675a6c65e2c6001b
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2017
---
# <a name="introduction-to-microsoft-intune-in-the-azure-portal"></a><span data-ttu-id="a4aec-103">Einführung in Microsoft Intune im Azure-Portal</span><span class="sxs-lookup"><span data-stu-id="a4aec-103">Introduction to Microsoft Intune in the Azure portal</span></span>


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="a4aec-104">Microsoft Intune befindet sich nun im Azure-Portal. Dies bedeutet, dass die gewohnten Workflows und Funktionen jetzt anders sind.</span><span class="sxs-lookup"><span data-stu-id="a4aec-104">Microsoft Intune is now in the Azure portal, meaning that the workflows and functionality you are used to are now different.</span></span>
<span data-ttu-id="a4aec-105">Das neue Portal bietet neue und aktualisierte Funktionen im Azure-Portal, in dem Sie die mobilen Geräte, PCs und Apps Ihrer Organisation verwalten können.</span><span class="sxs-lookup"><span data-stu-id="a4aec-105">The new portal offers you new and updated functionality in the Azure portal where you can manage your organization's mobile devices, PCs, and apps.</span></span>

* <span data-ttu-id="a4aec-106">[Wo befinden sich meine Funktionen in Azure jetzt?](ui-changes.md) bezieht sich darauf, Ihnen die bestimmten Workloads und UIs zu zeigen, die sich mit dem Umzug zu Azure verändert haben.</span><span class="sxs-lookup"><span data-stu-id="a4aec-106">[Where did my features go in Azure?](ui-changes.md) is a reference to show you the specific workflows and UIs that have changed with the move to Azure.</span></span>
* <span data-ttu-id="a4aec-107">[Klassische Intune-Gruppen im Azure-Portal](groups-get-started.md) erklärt die Auswirkungen des Umzugs zu Azure Active Directory-Sicherheitsgruppen für die Gruppenverwaltung.</span><span class="sxs-lookup"><span data-stu-id="a4aec-107">[Intune classic groups in the Azure portal](groups-get-started.md) explains the implications of the shift to Azure Active Directory security groups for group management.</span></span>




<span data-ttu-id="a4aec-108">In dieser Bibliothek finden Sie Informationen zum neuen Portal, die ständig aktualisiert werden.</span><span class="sxs-lookup"><span data-stu-id="a4aec-108">You can find information about the new portal in this library, and it is continually updated.</span></span> <span data-ttu-id="a4aec-109">Wenn Sie Vorschläge haben soll, hinterlassen Sie in den Kommentaren zum Thema Ihr Feedback.</span><span class="sxs-lookup"><span data-stu-id="a4aec-109">If you have suggestions you'd like to see, leave feedback in the topic comments.</span></span> <span data-ttu-id="a4aec-110">Wir freuen uns, von Ihnen zu hören.</span><span class="sxs-lookup"><span data-stu-id="a4aec-110">We'd love to hear from you.</span></span>

<span data-ttu-id="a4aec-111">Wichtige Funktionen der neuen Benutzeroberfläche:</span><span class="sxs-lookup"><span data-stu-id="a4aec-111">Highlights of the new experience include:</span></span>

- <span data-ttu-id="a4aec-112">Eine integrierte Konsole für alle Komponenten von Enterprise Mobility + Security (EMS)</span><span class="sxs-lookup"><span data-stu-id="a4aec-112">An integrated console for all your Enterprise Mobility + Security (EMS) components</span></span>
- <span data-ttu-id="a4aec-113">Eine HTML-Konsole basierend auf Webstandards</span><span class="sxs-lookup"><span data-stu-id="a4aec-113">An HTML-based console built on web standards</span></span>
- <span data-ttu-id="a4aec-114">Microsoft Graph-API-Unterstützung zur Automatisierung vieler Aktionen</span><span class="sxs-lookup"><span data-stu-id="a4aec-114">Microsoft Graph API support to automate many actions</span></span>
- <span data-ttu-id="a4aec-115">Azure Active Directory-Gruppen (AD) für Kompatibilität zwischen all Ihren Azure-Anwendungen</span><span class="sxs-lookup"><span data-stu-id="a4aec-115">Azure Active Directory (AD) groups to provide compatibility across all your Azure applications</span></span>
- <span data-ttu-id="a4aec-116">Unterstützung für die meisten modernen Webbrowser</span><span class="sxs-lookup"><span data-stu-id="a4aec-116">Support for most modern web browsers</span></span>

## <a name="before-you-start"></a><span data-ttu-id="a4aec-117">Vorbereitung</span><span class="sxs-lookup"><span data-stu-id="a4aec-117">Before you start</span></span>

<span data-ttu-id="a4aec-118">Um Intune im Azure-Portal verwenden zu können, benötigen Sie ein Administrator- und ein Mandantenkonto für Intune.</span><span class="sxs-lookup"><span data-stu-id="a4aec-118">To use Intune in the Azure portal, you must have an Intune admin and tenant account.</span></span> <span data-ttu-id="a4aec-119">[Registrieren Sie sich für ein Konto](https://portal.office.com/Signup/Signup.aspx?OfferId=40BE278A-DFD1-470a-9EF7-9F2596EA7FF9&dl=INTUNE_A&ali=1#0%20), wenn Sie noch keines haben.</span><span class="sxs-lookup"><span data-stu-id="a4aec-119">[Sign up for an account](https://portal.office.com/Signup/Signup.aspx?OfferId=40BE278A-DFD1-470a-9EF7-9F2596EA7FF9&dl=INTUNE_A&ali=1#0%20) if you don't already have one.</span></span>

## <a name="supported-web-browsers-for-the-azure-portal"></a><span data-ttu-id="a4aec-120">Unterstützte Webbrowser für das Azure-Portal</span><span class="sxs-lookup"><span data-stu-id="a4aec-120">Supported web browsers for the Azure portal</span></span>

<span data-ttu-id="a4aec-121">Das Azure-Portal kann auf die meisten modernen PCs, Macs und Tablets ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="a4aec-121">The Azure portal runs on most modern PCs, Macs, and tablets.</span></span> <span data-ttu-id="a4aec-122">Mobiltelefone werden nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="a4aec-122">Mobile phones are not supported.</span></span>
<span data-ttu-id="a4aec-123">Zurzeit werden die folgenden Browser unterstützt:</span><span class="sxs-lookup"><span data-stu-id="a4aec-123">Currently, the following browsers are supported:</span></span>

- <span data-ttu-id="a4aec-124">Microsoft Edge (neueste Version)</span><span class="sxs-lookup"><span data-stu-id="a4aec-124">Microsoft Edge (latest version)</span></span>
- <span data-ttu-id="a4aec-125">Microsoft Internet Explorer 11</span><span class="sxs-lookup"><span data-stu-id="a4aec-125">Microsoft Internet Explorer 11</span></span>
- <span data-ttu-id="a4aec-126">Safari (neueste Version, nur auf Mac)</span><span class="sxs-lookup"><span data-stu-id="a4aec-126">Safari (latest version, Mac only)</span></span>
- <span data-ttu-id="a4aec-127">Chrome (neueste Version)</span><span class="sxs-lookup"><span data-stu-id="a4aec-127">Chrome (latest version)</span></span>
- <span data-ttu-id="a4aec-128">Firefox (neueste Version)</span><span class="sxs-lookup"><span data-stu-id="a4aec-128">Firefox (latest version)</span></span>

<span data-ttu-id="a4aec-129">Aktuelle Informationen zu den unterstützten Browsern finden Sie im [Azure-Portal](https://docs.microsoft.com/azure/azure-preview-portal-supported-browsers-devices).</span><span class="sxs-lookup"><span data-stu-id="a4aec-129">Check the [Azure portal](https://docs.microsoft.com/azure/azure-preview-portal-supported-browsers-devices) for the latest information about supported browsers.</span></span>

## <a name="whats-in-this-library"></a><span data-ttu-id="a4aec-130">Inhalt dieser Bibliothek</span><span class="sxs-lookup"><span data-stu-id="a4aec-130">What's in this library?</span></span>

<span data-ttu-id="a4aec-131">Die Dokumentation orientiert sich am Layout des Azure-Portals, damit Sie die gewünschten Informationen einfacher finden.</span><span class="sxs-lookup"><span data-stu-id="a4aec-131">The documentation reflects the layout of the Azure portal to make it easier to find the information you need.</span></span>

![Azure-Portal-Workloads](./media/azure-portal-workloads.png)

### <a name="introduction-and-get-started"></a><span data-ttu-id="a4aec-133">Einführung und erste Schritte</span><span class="sxs-lookup"><span data-stu-id="a4aec-133">Introduction and get started</span></span>
<span data-ttu-id="a4aec-134">Dieser Abschnitt enthält [einführende Informationen](introduction-intune.md) für die ersten Schritte mit Intune.</span><span class="sxs-lookup"><span data-stu-id="a4aec-134">This section contains [introductory information](introduction-intune.md) that helps you get started using Intune.</span></span>
### <a name="plan-and-design"></a><span data-ttu-id="a4aec-135">Planung und Entwurf</span><span class="sxs-lookup"><span data-stu-id="a4aec-135">Plan and design</span></span>
<span data-ttu-id="a4aec-136">Informationen zum [Planen und Entwerfen](/intune-classic/plan-design/introduction) Ihrer Intune-Umgebung.</span><span class="sxs-lookup"><span data-stu-id="a4aec-136">Information to help you [plan and design](/intune-classic/plan-design/introduction) your Intune environment.</span></span>
### <a name="device-enrollment"></a><span data-ttu-id="a4aec-137">Geräteregistrierung</span><span class="sxs-lookup"><span data-stu-id="a4aec-137">Device enrollment</span></span>
<span data-ttu-id="a4aec-138">[Erfahren Sie, wie Sie Ihre Geräte mit Intune verwalten](device-enrollment.md).</span><span class="sxs-lookup"><span data-stu-id="a4aec-138">[How to get your devices managed by Intune](device-enrollment.md).</span></span>
### <a name="device-compliance"></a><span data-ttu-id="a4aec-139">Gerätekompatibilität</span><span class="sxs-lookup"><span data-stu-id="a4aec-139">Device compliance</span></span>
<span data-ttu-id="a4aec-140">[Definieren Sie eine Konformitätsebene für Ihre Geräte, und erstellen Sie anschließend Berichte zu allen Geräten, die nicht konform sind](device-compliance.md).</span><span class="sxs-lookup"><span data-stu-id="a4aec-140">[Define a compliance level for your devices, then report any devices that are not compliant](device-compliance.md).</span></span>
### <a name="device-configuration"></a><span data-ttu-id="a4aec-141">Gerätekonfiguration</span><span class="sxs-lookup"><span data-stu-id="a4aec-141">Device configuration</span></span>
<span data-ttu-id="a4aec-142">[Erfahren Sie etwas über die Profile, die Sie verwenden können, um Einstellungen und Funktionen auf den von Ihnen verwalteten Geräten zu konfigurieren](device-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="a4aec-142">[Understand the profiles you can use to configure settings and features on devices you manage](device-profiles.md).</span></span>
### <a name="devices"></a><span data-ttu-id="a4aec-143">Geräte</span><span class="sxs-lookup"><span data-stu-id="a4aec-143">Devices</span></span>
<span data-ttu-id="a4aec-144">[Lernen Sie die verwalteten Geräte im Inventar und in den Berichten kennen](device-management.md).</span><span class="sxs-lookup"><span data-stu-id="a4aec-144">[Get to know the devices you manage with inventory and reports](device-management.md).</span></span>
### <a name="mobile-apps"></a><span data-ttu-id="a4aec-145">Mobile Apps</span><span class="sxs-lookup"><span data-stu-id="a4aec-145">Mobile apps</span></span>
<span data-ttu-id="a4aec-146">[So veröffentlichen, verwalten, konfigurieren und schützen Sie Apps](app-management.md).</span><span class="sxs-lookup"><span data-stu-id="a4aec-146">[How to publish, manage, configure, and protect apps](app-management.md).</span></span>
### <a name="conditional-access"></a><span data-ttu-id="a4aec-147">Bedingter Zugriff</span><span class="sxs-lookup"><span data-stu-id="a4aec-147">Conditional access</span></span>
<span data-ttu-id="a4aec-148">[Beschränken Sie den Zugriff auf Exchange-Dienste basierend auf von Ihnen festgelegte Bedingungen](conditional-access.md).</span><span class="sxs-lookup"><span data-stu-id="a4aec-148">[Restrict access to Exchange services depending on conditions you specify](conditional-access.md).</span></span>
### <a name="on-premises-access"></a><span data-ttu-id="a4aec-149">Lokaler Zugriff</span><span class="sxs-lookup"><span data-stu-id="a4aec-149">On-premises access</span></span>
[<span data-ttu-id="a4aec-150">Konfigurieren Sie den Zugriff auf Exchange ActiveSync und Exchange lokal.</span><span class="sxs-lookup"><span data-stu-id="a4aec-150">Configure access to Exchange ActiveSync, and Exchange on-premises</span></span>](/intune-classic/deploy-use/mobile-device-management-with-exchange-activesync-and-microsoft-intune)
### <a name="users"></a><span data-ttu-id="a4aec-151">Users</span><span class="sxs-lookup"><span data-stu-id="a4aec-151">Users</span></span>
<span data-ttu-id="a4aec-152">[Informieren Sie sich über die Benutzer der Geräte, die Sie verwalten, und organisieren Sie Ressourcen in Gruppen](users-add.md).</span><span class="sxs-lookup"><span data-stu-id="a4aec-152">[Learn about the users of devices you manage and sort resources into groups](users-add.md).</span></span>
### <a name="groups"></a><span data-ttu-id="a4aec-153">Gruppen</span><span class="sxs-lookup"><span data-stu-id="a4aec-153">Groups</span></span>
[<span data-ttu-id="a4aec-154">Erfahren Sie, wie Sie Azure Active Directory-Gruppen in Intune verwenden können.</span><span class="sxs-lookup"><span data-stu-id="a4aec-154">Learn about how you can use Azure Active Directory groups with Intune</span></span>](groups-get-started.md)
### <a name="intune-roles"></a><span data-ttu-id="a4aec-155">Intune-Rollen</span><span class="sxs-lookup"><span data-stu-id="a4aec-155">Intune roles</span></span>
<span data-ttu-id="a4aec-156">[Steuern Sie, welche Benutzer welche Intune-Aktionen ausführen dürfen, und für wen diese Aktionen gelten](role-based-access-control.md).</span><span class="sxs-lookup"><span data-stu-id="a4aec-156">[Control who can perform various Intune actions, and who those actions apply to](role-based-access-control.md).</span></span> <span data-ttu-id="a4aec-157">Sie können entweder die integrierten Rollen verwenden, die einige allgemeine Intune-Szenarien abdecken, oder Sie können eigene Rollen erstellen.</span><span class="sxs-lookup"><span data-stu-id="a4aec-157">You can either use the built-in roles that cover some common Intune scenarios, or you can create your own roles.</span></span>
### <a name="software-updates"></a><span data-ttu-id="a4aec-158">Softwareupdates</span><span class="sxs-lookup"><span data-stu-id="a4aec-158">Software updates</span></span>
<span data-ttu-id="a4aec-159">[Erfahren Sie, wie Sie Softwareupdates für Windows 10-Geräte konfigurieren](windows-update-for-business-configure.md).</span><span class="sxs-lookup"><span data-stu-id="a4aec-159">[Learn about how to configure software updates for Windows 10 devices](windows-update-for-business-configure.md).</span></span>



## <a name="whats-new"></a><span data-ttu-id="a4aec-160">Was gibt es Neues?</span><span class="sxs-lookup"><span data-stu-id="a4aec-160">What's new?</span></span>

<span data-ttu-id="a4aec-161">[Erfahren Sie mehr zu den Neuerungen in Intune](whats-new.md).</span><span class="sxs-lookup"><span data-stu-id="a4aec-161">[Find out what's new in Intune](whats-new.md).</span></span>
