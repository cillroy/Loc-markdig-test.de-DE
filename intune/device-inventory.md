---
title: "Anzeigen des Intune-Gerätebestands"
titlesuffix: Azure portal
description: "Erfahren Sie, wie Sie die von Ihnen über Intune verwalteten Geräte sowie Informationen zu der entsprechenden Hardware und den installierten Apps anzeigen.\""
keywords: 
author: arob98
ms.author: angrobe
nmanager: angrobe
ms.date: 11/10/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e71c6bdb-d75c-404f-8e38-24a663be81c2
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: a910c99454b9c8a7922af3368453feab94803501
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2018
---
# <a name="how-to-view-intune-device-inventory"></a><span data-ttu-id="af8a8-103">So zeigen Sie den Intune-Gerätebestand an</span><span class="sxs-lookup"><span data-stu-id="af8a8-103">How to view Intune device inventory</span></span>


[!INCLUDE [azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="af8a8-104">Die Workload **Geräte** bietet Einblicke in die von Ihnen verwalteten Geräte, einschließlich Informationen zu Hardwarefunktionen und den auf den Geräten installierten Apps.</span><span class="sxs-lookup"><span data-stu-id="af8a8-104">The **Devices** workload gives you insights into the devices you manage, including their hardware capabilities, and the apps installed on them.</span></span> 

<span data-ttu-id="af8a8-105">So zeigen Sie den Gerätebestand an:</span><span class="sxs-lookup"><span data-stu-id="af8a8-105">To view device inventory:</span></span>

1. <span data-ttu-id="af8a8-106">Melden Sie sich beim Azure-Portal an.</span><span class="sxs-lookup"><span data-stu-id="af8a8-106">Sign into the Azure portal.</span></span>
2. <span data-ttu-id="af8a8-107">Wählen Sie **Weitere Dienste** > **Überwachung und Verwaltung** > **Intune** aus.</span><span class="sxs-lookup"><span data-stu-id="af8a8-107">Choose **More Services** > **Monitoring + Management** > **Intune**.</span></span>
3. <span data-ttu-id="af8a8-108">Wählen Sie auf dem Blatt **Intune** die Option **Geräte** aus.</span><span class="sxs-lookup"><span data-stu-id="af8a8-108">On the **Intune** blade, choose **Devices**.</span></span>

<span data-ttu-id="af8a8-109">Wählen Sie nun eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="af8a8-109">Now, choose one of the following options:</span></span>

- <span data-ttu-id="af8a8-110">**Übersicht:** Erhalten Sie Informationen zu Geräten, die Sie registriert haben, und zu den Betriebssystemen der einzelnen Geräte.</span><span class="sxs-lookup"><span data-stu-id="af8a8-110">**Overview** Get information about devices you've enrolled, and the operating systems each device runs.</span></span>
- <span data-ttu-id="af8a8-111">**Verwalten:** Wählen Sie **Alle Geräte** aus, um eine Liste aller von Ihnen verwalteten Geräte anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="af8a8-111">**Manage** - Choose **All Devices** to see a list of all the devices you manage.</span></span>
    <span data-ttu-id="af8a8-112">Wählen Sie eines dieser Geräte in der Liste aus, um das Blatt **Übersicht über** <*Gerätename*>  zu öffnen, auf dem Sie eine der folgenden Optionen auswählen können:</span><span class="sxs-lookup"><span data-stu-id="af8a8-112">Select one of those devices in the list to open the <*device name*> **Overview** blade where you can select one of:</span></span>
    - <span data-ttu-id="af8a8-113">**Übersicht:** Hier finden Sie allgemeine Informationen über das Gerät, einschließlich den Namen, den Besitzer, ob es ein BYOD-Gerät ist, wann es zuletzt eingecheckt wurde u.v.m.</span><span class="sxs-lookup"><span data-stu-id="af8a8-113">**Overview**  - See general information about the device including its name, owner, whether it is a BYOD device, when it checked-in, and more.</span></span>
    - <span data-ttu-id="af8a8-114">**Hardware:** Hier finden Sie ausführliche Informationen über das Gerät, einschließlich dessen freien Speicherplatzes, des Modells und Herstellers usw.</span><span class="sxs-lookup"><span data-stu-id="af8a8-114">**Hardware** - See more detailed information about the device including its free storage space, model and manufacturer, and more.</span></span>
    - <span data-ttu-id="af8a8-115">**Ermittelte Apps:** Zeigt eine Liste aller auf dem Gerät installierten Apps an, die von Intune gefunden wurden.</span><span class="sxs-lookup"><span data-stu-id="af8a8-115">**Discovered apps** - Displays a list of all apps that Intune found installed on the device.</span></span>
    - <span data-ttu-id="af8a8-116">**Gerätekompatibilität:** Zeigt den Kompatibilitätszustand aller Kompatibilitätsrichtlinien an, die dem Gerät zugewiesen wurden.</span><span class="sxs-lookup"><span data-stu-id="af8a8-116">**Device compliance** - Displays the compliance state of all compliance policies that have been assigned to the device.</span></span>
    - <span data-ttu-id="af8a8-117">**Gerätekonfiguration:** Zeigt den Kompatibilitätszustand aller Konfigurationsrichtlinien an, die dem Gerät zugewiesen wurden.</span><span class="sxs-lookup"><span data-stu-id="af8a8-117">**Device configuration** - Displays the compliance state of all device configuration policies that have been assigned to the device.</span></span>
- <span data-ttu-id="af8a8-118">**Monitor:** Wählen Sie **Geräteaktionen** aus, um eine Liste der Geräteaktionen, die auf Geräten, die Sie verwalten, ausgeführt wurden, und deren aktuellen Status anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="af8a8-118">**Monitor** Choose **Device Actions** to see a list of device actions that have been performed on devices you manage and their current state.</span></span>
- <span data-ttu-id="af8a8-119">**Setup** > **TeamViewer-Connector:** Ermöglicht Ihnen die Konfiguration der Remoteverwaltung auf Geräten mithilfe der Software TeamViewer.</span><span class="sxs-lookup"><span data-stu-id="af8a8-119">**Setup** > **TeamViewer Connector** - Let's you configure remote administration on devices using the TeamViewer software.</span></span> <span data-ttu-id="af8a8-120">Weitere Informationen finden Sie unter [Bereitstellen von Remoteunterstützung für mit Intune verwaltete Android-Geräte](/intune/device-profile-android-teamviewer).</span><span class="sxs-lookup"><span data-stu-id="af8a8-120">For details, see [Provide remote assistance for Intune managed Android devices](/intune/device-profile-android-teamviewer).</span></span>

<span data-ttu-id="af8a8-121">Intune sammelt nur auf unternehmenseigenen Geräten App-Inventar.</span><span class="sxs-lookup"><span data-stu-id="af8a8-121">Intune collects app inventory only on corporate-owned devices.</span></span> <span data-ttu-id="af8a8-122">Apps sind auf persönlichen Geräten nicht inventarisiert.</span><span class="sxs-lookup"><span data-stu-id="af8a8-122">Apps are not inventoried on personal devices.</span></span> <span data-ttu-id="af8a8-123">Für Windows 10 PCs wird nur Inventar von modernen Apps auf unternehmenseigenen Geräten gesammelt.</span><span class="sxs-lookup"><span data-stu-id="af8a8-123">For Windows 10 PCs, only modern app inventory is collected on corporate-owned devices.</span></span> <span data-ttu-id="af8a8-124">Intune sammelt keine Informationen über Win32-Apps auf dem Gerät.</span><span class="sxs-lookup"><span data-stu-id="af8a8-124">Intune does not collect information about Win32 apps on the device.</span></span> <span data-ttu-id="af8a8-125">Je nach Netzbetreiber, den Sie mit dem Gerät verwenden, werden nicht alle Inventarelemente gesammelt.</span><span class="sxs-lookup"><span data-stu-id="af8a8-125">Depending on the carrier you use with devices, not all inventory items might be collected.</span></span>
