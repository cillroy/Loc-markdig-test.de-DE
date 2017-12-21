---
title: "Überlegungen bei der Verwaltung von Windows-Geräten mit Intune in Azure"
description: "Überlegungen bei der Verwaltung der Windows-Geräte Ihrer Organisation mit Intune in Azure"
keywords: 
author: ErikjeMS
ms.author: erikje
manager: angrobe
ms.date: 11/14/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 
ms.reviewer: owenyen
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: f4018f505626b05dc84be509ca1e42cefff94b90
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2017
---
# <a name="intune-on-azure-console-and-legacy-intune-pc-client"></a><span data-ttu-id="a80e2-103">Intune in der Azure-Konsole und der Legacy-Intune-PC-Client</span><span class="sxs-lookup"><span data-stu-id="a80e2-103">Intune on Azure console and legacy Intune PC Client</span></span>

<span data-ttu-id="a80e2-104">Intune wurde vor kurzem in eine Azure-basierte SaaS-Anwendungsdienstarchitektur verschoben.</span><span class="sxs-lookup"><span data-stu-id="a80e2-104">Intune recently moved to an Azure-based SaaS application service architecture.</span></span> <span data-ttu-id="a80e2-105">Azure bietet erhebliche Verbesserungen in den Bereichen Skalierung, Kapazität und Leistung.</span><span class="sxs-lookup"><span data-stu-id="a80e2-105">Azure provides significant improvements in scale, capacity, and performance.</span></span> <span data-ttu-id="a80e2-106">Diese Umstellung beinhaltet außerdem erweiterte Funktionen für Intune-Administratoren sowie optimierte Workflows im Azure-Portal.</span><span class="sxs-lookup"><span data-stu-id="a80e2-106">This transition also offers enhanced Intune admin experiences and optimized workflows in the Azure portal.</span></span> 

<span data-ttu-id="a80e2-107">Ziehen Sie bei der Verwaltung der Windows-Geräte Ihrer Organisation mit Intune in Azure die folgenden Punkte in Betracht:</span><span class="sxs-lookup"><span data-stu-id="a80e2-107">When using Intune on Azure to manage your organization’s Windows devices, consider the following points:</span></span>

## <a name="legacy-pc-client-features-are-only-available-in-the-silverlight-console"></a><span data-ttu-id="a80e2-108">Legacy-PC-Client-Funktionen sind nur in der Silverlight-Konsole verfügbar.</span><span class="sxs-lookup"><span data-stu-id="a80e2-108">Legacy PC Client features are only available in the Silverlight console</span></span>

<span data-ttu-id="a80e2-109">Für die Intune-PC-Client-Verwaltungsworkflows wird die [Silverlight-basierte Intune-Verwaltungskonsole](https://manage.microsoft.com/) verwendet. Das hat folgende Konsequenzen:</span><span class="sxs-lookup"><span data-stu-id="a80e2-109">The Intune PC Client management workflows use the [Silverlight-based Intune Admin Console](https://manage.microsoft.com/), which has the following consequences:</span></span>

- <span data-ttu-id="a80e2-110">Für alle Verwaltungsaufgaben ohne Gruppierung, die mithilfe des Intune-PC-Clients durchgeführt werden, müssen Sie die Silverlight-Konsole verwenden.</span><span class="sxs-lookup"><span data-stu-id="a80e2-110">For all non-grouping management tasks using the Intune PC Client, you must use the Silverlight console.</span></span>
- <span data-ttu-id="a80e2-111">Wenn Sie Gruppen verwalten, müssen Sie [Intune im Azure-Portal](https://portal.azure.com/) verwenden.</span><span class="sxs-lookup"><span data-stu-id="a80e2-111">When managing groups, you must use the [Intune on Azure portal](https://portal.azure.com/).</span></span> <span data-ttu-id="a80e2-112">Diese Anforderung gilt, weil Intune jetzt Azure AD-Gruppen anstelle der Legacy-Intune-Gruppen verwendet.</span><span class="sxs-lookup"><span data-stu-id="a80e2-112">This requirement exists because Intune now uses Azure AD Groups instead of legacy Intune Groups.</span></span> 

<span data-ttu-id="a80e2-113">Aufgrund der Umstellung auf Azure AD-Gruppen hat sich die „gruppenbasierte“ Filterung in den Dashboardansichten der Silverlight-Konsole leicht verändert.</span><span class="sxs-lookup"><span data-stu-id="a80e2-113">Because of the switch to Azure AD Groups, “group-based” filtering in the Silverlight console dashboard views has changed slightly.</span></span> <span data-ttu-id="a80e2-114">Gehen Sie folgendermaßen vor, um in der aktualisierten Silverlight-Benutzeroberfläche zu filtern:</span><span class="sxs-lookup"><span data-stu-id="a80e2-114">To filter in the updated Silverlight UI, follow these steps:</span></span>

1. <span data-ttu-id="a80e2-115">Wählen Sie eine Ansicht aus.</span><span class="sxs-lookup"><span data-stu-id="a80e2-115">Select a view.</span></span>
2. <span data-ttu-id="a80e2-116">Geben Sie im Feld **Filter** den Namen der Gruppe ein, nach der Sie filtern möchten, und drücken Sie die EINGABETASTE.</span><span class="sxs-lookup"><span data-stu-id="a80e2-116">In the **Filters** box, enter the name of the group that you want to filter by and press enter.</span></span> <span data-ttu-id="a80e2-117">Dadurch wird die Listenansicht auf die Geräte in dieser jeweiligen Gruppe gefiltert.</span><span class="sxs-lookup"><span data-stu-id="a80e2-117">This will filter the list view to the devices in that particular group.</span></span>

   ![](media/intune_on_azure/image01.png)

## <a name="manage-windows-10-devices-by-using-mdm"></a><span data-ttu-id="a80e2-118">Verwalten von Windows 10-Geräten mithilfe von MDM</span><span class="sxs-lookup"><span data-stu-id="a80e2-118">Manage Windows 10 devices by using MDM</span></span>

<span data-ttu-id="a80e2-119">Wir empfehlen die Verwendung der [mobilen Geräteverwaltung (Mobile Device Management, MDM) zum Verwalten Ihrer Windows 10-Geräte](https://docs.microsoft.com/intune/device-restrictions-windows-10) anstelle des Legacy-Intune-PC-Clients.</span><span class="sxs-lookup"><span data-stu-id="a80e2-119">We recommend that you use [Mobile Device Management (MDM) to manage your Windows 10 devices](https://docs.microsoft.com/intune/device-restrictions-windows-10) instead of using the legacy Intune PC client.</span></span> <span data-ttu-id="a80e2-120">Die Möglichkeit zum Verwalten von Windows 10 über MDM steht in Intune über das Azure-Portal zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="a80e2-120">The ability to manage Windows 10 via MDM is available in the Intune on Azure portal.</span></span> <span data-ttu-id="a80e2-121">MDM für Windows 10 bietet viele neue Verwaltungs- und Sicherheitsfunktionen, die über den Legacy-Intune-PC-Client nicht verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="a80e2-121">Windows 10 MDM provides many new management and security capabilities that are not available via the legacy Intune PC client.</span></span>

## <a name="continue-to-manage-windows-7-by-using-intune-pc-client"></a><span data-ttu-id="a80e2-122">Weiteres Verwalten von Windows 7 mit dem Intune-PC-Client</span><span class="sxs-lookup"><span data-stu-id="a80e2-122">Continue to manage Windows 7 by using Intune PC Client</span></span>

<span data-ttu-id="a80e2-123">Da Windows 7 nicht über MDM verwaltet werden kann, stellen wir nur in der Silverlight-Konsole weiterhin Unterstützung für vorhandene Intune-PC-Client-Funktionen zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="a80e2-123">For Windows 7, which can’t be managed by using MDM, we will continue to support existing Intune PC Client capabilities in the Silverlight console only.</span></span> <span data-ttu-id="a80e2-124">Erwägen Sie bei einem Upgrade auf Windows 10 eine Migration zur MDM-Verwaltung.</span><span class="sxs-lookup"><span data-stu-id="a80e2-124">Consider migrating to MDM management when you upgrade to Windows 10.</span></span>

## <a name="mdm-capabilities"></a><span data-ttu-id="a80e2-125">MDM-Funktionen</span><span class="sxs-lookup"><span data-stu-id="a80e2-125">MDM Capabilities</span></span>

<span data-ttu-id="a80e2-126">Einen ausführlichen Vergleich zwischen PC-Client und MDM-Funktionen finden Sie unter [Vergleichen der Verwaltung von Windows-PCs als Computer oder mobile Geräte](https://docs.microsoft.com/intune-classic/deploy-use/pc-management-comparison).</span><span class="sxs-lookup"><span data-stu-id="a80e2-126">For a detailed comparison between PC Client and MDM capabilities, see [Compare managing Windows PCs as computers or mobile devices](https://docs.microsoft.com/intune-classic/deploy-use/pc-management-comparison).</span></span> <span data-ttu-id="a80e2-127">Über MDM-Updates werden weiterhin neue Verwaltungsfunktionen für in MDM registrierte Windows 10-Geräte bereitgestellt, einschließlich Auswertungsoptionen für Win32-Apps.</span><span class="sxs-lookup"><span data-stu-id="a80e2-127">MDM updates will continue to bring new management capabilities to MDM-enrolled, Windows 10 devices, inclusive of evaluating options for Win 32 apps.</span></span> <span data-ttu-id="a80e2-128">Unter [Neuerungen](https://docs.microsoft.com/intune/whats-new) finden Sie die neuesten Features, die dem Dienst hinzugefügt wurden.</span><span class="sxs-lookup"><span data-stu-id="a80e2-128">View the [What’s New](https://docs.microsoft.com/intune/whats-new) for the latest release additions to the service.</span></span>

## <a name="switch-from-pc-client-to-mdm"></a><span data-ttu-id="a80e2-129">Umstellen vom PC-Client auf MDM</span><span class="sxs-lookup"><span data-stu-id="a80e2-129">Switch from PC Client to MDM</span></span>

<span data-ttu-id="a80e2-130">Um die Verwaltung von Windows 10-Geräten mit dem Intune-PC-Client auf die Verwaltung mit MDM umzustellen, gehen Sie folgendermaßen vor:</span><span class="sxs-lookup"><span data-stu-id="a80e2-130">To switch from managing Windows 10 devices with the Intune PC Client to managing with MDM, follow these steps:</span></span>

1. <span data-ttu-id="a80e2-131">Führen Sie in der Silverlight-Konsole eine **selektive Zurücksetzung** durch, um die Registrierung des Geräts beim PC-Client aufzuheben.</span><span class="sxs-lookup"><span data-stu-id="a80e2-131">In the Silverlight console, perform a **Selective wipe** to un-enroll the device from the PC Client.</span></span>
  ![](media/intune_on_azure/image02.png)
2. <span data-ttu-id="a80e2-132">Registrieren Sie das Gerät neu bei [MDM (und/oder Azure AD Join)](https://docs.microsoft.com/intune/windows-enroll).</span><span class="sxs-lookup"><span data-stu-id="a80e2-132">Re-enroll the device by using [MDM (and/or Azure AD Join)](https://docs.microsoft.com/intune/windows-enroll).</span></span> 

## <a name="next-steps"></a><span data-ttu-id="a80e2-133">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="a80e2-133">Next steps</span></span>
[<span data-ttu-id="a80e2-134">Registrieren von Windows-Geräten</span><span class="sxs-lookup"><span data-stu-id="a80e2-134">Enroll Windows devices</span></span>](https://docs.microsoft.com/intune/windows-enroll)

 
