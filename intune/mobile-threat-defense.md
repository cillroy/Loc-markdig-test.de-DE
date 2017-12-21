---
title: Mobile Threat Defense mit Intune
titleSuffix: Azure portal
description: "Schützen Sie den Zugriff auf Unternehmensressourcen auf der Basis des Geräterisikos."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 11/28/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: ac77b590-a7ec-45a0-9516-ebf5243b6210
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 16402b30895e61d9a4ff8393fd4d4c6efa061e9e
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2017
---
# <a name="mobile-threat-defense-integration-with-intune"></a><span data-ttu-id="42fb1-103">Integration von Mobile Threat Defense in Intune</span><span class="sxs-lookup"><span data-stu-id="42fb1-103">Mobile Threat Defense integration with Intune</span></span>


<span data-ttu-id="42fb1-104">Mit Intune Mobile Threat Defense-Connectors können Sie Ihren ausgewählten Mobile Threat Defense-Hersteller als Informationsquelle für Ihre Konformitätsrichtlinien und bedingte Zugriffsregeln nutzen.</span><span class="sxs-lookup"><span data-stu-id="42fb1-104">Intune Mobile Threat Defense connectors allow you to leverage your chosen Mobile Threat Defense vendor as a source of information for your compliance policies and conditional access rules.</span></span> <span data-ttu-id="42fb1-105">Dadurch können IT-Administratoren insbesondere für gefährdete Mobilgeräte eine Schutzebene zu ihren Unternehmensressourcen wie Exchange und SharePoint hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="42fb1-105">This allows IT administrators to add a layer of protection to their corporate resources such as Exchange and Sharepoint, specifically from compromised mobile devices.</span></span>

## <a name="what-problem-does-this-solve"></a><span data-ttu-id="42fb1-106">Welches Problem wird dadurch gelöst?</span><span class="sxs-lookup"><span data-stu-id="42fb1-106">What problem does this solve?</span></span>

<span data-ttu-id="42fb1-107">Unternehmen müssen vertrauliche Daten vor auftretenden Bedrohungen schützen. Dazu gehören physische, App-und netzwerkbasierte Bedrohungen sowie Sicherheitsrisiken beim Betriebssystem.</span><span class="sxs-lookup"><span data-stu-id="42fb1-107">Companies need to protect sensitive data from emerging threats including physical, app-based, and network-based threats, as well as operating system vulnerabilities.</span></span>

<span data-ttu-id="42fb1-108">In der Vergangenheit haben Firmen PCs vor Angriffen proaktiv geschützt, während mobile Geräte nicht überwacht wurden und ungeschützt blieben.</span><span class="sxs-lookup"><span data-stu-id="42fb1-108">Historically, companies have been proactive when protecting PCs from attack, while mobile devices go un-monitored and unprotected.</span></span> <span data-ttu-id="42fb1-109">Mobile Plattformen bieten integrierten Schutz in Form von App-Isolierung und sicherheitsgeprüfter App Stores für Verbraucher, doch diese Plattformen bleiben weiterhin für komplexe Angriffe anfällig.</span><span class="sxs-lookup"><span data-stu-id="42fb1-109">Mobile platforms have built-in protection such as app isolation and vetted consumer app stores, but these platforms remain vulnerable to sophisticated attacks.</span></span> <span data-ttu-id="42fb1-110">Immer mehr Mitarbeiter nutzen ihre Geräte für die Arbeit und benötigen Zugriff auf vertrauliche Informationen.</span><span class="sxs-lookup"><span data-stu-id="42fb1-110">Today, more employees use devices for work and need access to sensitive information.</span></span> <span data-ttu-id="42fb1-111">Geräte müssen gegen zunehmend raffinierter werdende Angriffe geschützt werden.</span><span class="sxs-lookup"><span data-stu-id="42fb1-111">Devices need to be protected from increasingly sophisticated attacks.</span></span>

## <a name="how-the-intune-mobile-threat-defense-connectors-work"></a><span data-ttu-id="42fb1-112">Wie funktioniert der Intune Mobile Threat Defense-Connector?</span><span class="sxs-lookup"><span data-stu-id="42fb1-112">How the Intune Mobile Threat Defense connectors work?</span></span>

<span data-ttu-id="42fb1-113">Der Connector schützt Unternehmensressourcen, indem er einen Kommunikationskanal zwischen Intune und Ihrem ausgewählten Mobile Threat Defense-Hersteller erstellt.</span><span class="sxs-lookup"><span data-stu-id="42fb1-113">The connector protects company resources by creating a channel of communication between Intune and your chosen Mobile Threat Defense vendor.</span></span> <span data-ttu-id="42fb1-114">Intune Mobile Threat Defense-Partner bieten intuitive und leicht bereitzustellende Anwendungen für Mobilgeräte, die aktiv Informationen zu Bedrohungen überprüfen und analysieren, um sie mit Intune für Berichts- oder Erzwingungszwecke zu teilen.</span><span class="sxs-lookup"><span data-stu-id="42fb1-114">Intune Mobile Threat Defense partners offer intuitive, easy to deploy applications for mobile devices which actively scan and analyze threat information to share with Intune, for either reporting or enforcement purposes.</span></span> 

<span data-ttu-id="42fb1-115">Wenn eine verbundene Mobile Threat Defense-App z.B. einem Mobile Threat Defense-Hersteller mitteilt, dass ein Telefon in Ihrem Netzwerk aktuell mit einem Netzwerk verbunden ist, das anfällig für „Man in the Middle“-Angriffe ist, wird diese Information an eine entsprechende Risikostufe (niedrig/mittel/hoch) weitergeleitet. Diese kann anschließend mit Ihren konfigurierten Zulassungen der Risikostufe in Intune verglichen werden, um zu bestimmen, ob der Zugriff auf bestimmte Ressourcen Ihrer Wahl aufgehoben werden sollte, während das Gerät gefährdet ist.</span><span class="sxs-lookup"><span data-stu-id="42fb1-115">For example, if a connected Mobile Threat Defense app reports to the Mobile Threat Defense vendor that a phone on your network is currently connected to a network which is vulnerable to Man in the Middle attacks, this information is shared with and categorized to an appropriate risk level (low/medium/high) – which can then be compared with your configured risk level allowances in Intune to determine if access to certain resources of your choice should be revoked while the device is compromised.</span></span>

## <a name="what-data-does-intune-collect-for-mobile-threat-defense"></a><span data-ttu-id="42fb1-116">Welche Daten erfasst Intune für Mobile Threat Defense?</span><span class="sxs-lookup"><span data-stu-id="42fb1-116">What data does Intune collect for Mobile Threat Defense?</span></span>

<span data-ttu-id="42fb1-117">Intune erfasst sowohl von privaten als auch von unternehmenseigenen Geräten Informationen zum App-Bestand und stellt diese für Anbieter von Bedrohungserkennung auf Mobilgeräten (Mobile Thread Defense, MTD) wie Lookout for Work zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="42fb1-117">Intune collects app inventory information from both personal and corporate-owned devices and makes it available for Mobile Thread Defense (MTD) providers to fetch, such as Lookout for Work.</span></span> <span data-ttu-id="42fb1-118">Sie können Informationen zum App-Bestand auf iOS 11-Geräten (oder höher) erfassen.</span><span class="sxs-lookup"><span data-stu-id="42fb1-118">You can collect an app inventory from the users of iOS 11+ devices.</span></span>

<span data-ttu-id="42fb1-119">**App-Bestand**</span><span class="sxs-lookup"><span data-stu-id="42fb1-119">**App inventory**</span></span>  
<span data-ttu-id="42fb1-120">Die Bestände von sowohl unternehmenseigenen als auch privaten iOS 11-Geräten (oder höher) werden an Ihren MTD-Dienstanbieter übermittelt.</span><span class="sxs-lookup"><span data-stu-id="42fb1-120">Inventories from both corporate-owned iOS 11+ and personally owned devices are sent to your MTD service provider.</span></span> <span data-ttu-id="42fb1-121">Die Daten in den App-Beständen umfassen:</span><span class="sxs-lookup"><span data-stu-id="42fb1-121">Data in the app inventory includes:</span></span>

 - <span data-ttu-id="42fb1-122">App-ID</span><span class="sxs-lookup"><span data-stu-id="42fb1-122">App ID</span></span>
 - <span data-ttu-id="42fb1-123">App-Version</span><span class="sxs-lookup"><span data-stu-id="42fb1-123">App Version</span></span>
 - <span data-ttu-id="42fb1-124">Kurzversion der App</span><span class="sxs-lookup"><span data-stu-id="42fb1-124">App Short Version</span></span>
 - <span data-ttu-id="42fb1-125">App-Name</span><span class="sxs-lookup"><span data-stu-id="42fb1-125">App Name</span></span>
 - <span data-ttu-id="42fb1-126">Größe des App-Pakets</span><span class="sxs-lookup"><span data-stu-id="42fb1-126">App Bundle Size</span></span>
 - <span data-ttu-id="42fb1-127">Dynamische Größe der App</span><span class="sxs-lookup"><span data-stu-id="42fb1-127">App Dynamic Size</span></span>
 - <span data-ttu-id="42fb1-128">App wird geprüft oder nicht</span><span class="sxs-lookup"><span data-stu-id="42fb1-128">App is validated or not</span></span>
 - <span data-ttu-id="42fb1-129">App wird verwaltet oder nicht</span><span class="sxs-lookup"><span data-stu-id="42fb1-129">App is managed or not</span></span>

## <a name="sample-scenarios"></a><span data-ttu-id="42fb1-130">Beispielszenarien</span><span class="sxs-lookup"><span data-stu-id="42fb1-130">Sample scenarios</span></span>

<span data-ttu-id="42fb1-131">Wenn ein Gerät von der Mobile Threat Defense-Lösung als gefährdet eingestuft wird:</span><span class="sxs-lookup"><span data-stu-id="42fb1-131">When a device is considered infected by the Mobile Threat Defense solution:</span></span>

![Mobile Threat Defense infected device (Mobile Threat Defense – Gefährdetes Gerät)](./media/MTD-image-1.png)

<span data-ttu-id="42fb1-133">Der Zugriff wird gewährt, wenn das Gerät wiederhergestellt ist:</span><span class="sxs-lookup"><span data-stu-id="42fb1-133">Access is granted when the device is remediated:</span></span>

![Mobile Threat Defense Access granted (Mobile Threat Defense – Zugriff gewährt)](./media/MTD-image-2.png)

> [!NOTE] 
> <span data-ttu-id="42fb1-135">Das Verwenden von mehreren Anbietern für Mobile Threat Defense (MTD) mit Intune wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="42fb1-135">Using multiple Mobile Threat Defense vendors with Intune is not supported.</span></span> <span data-ttu-id="42fb1-136">Wenn mehrere MTD-Tools aktiviert sind, wird die Installation von allen MTD-Apps erzwungen, die anschließend geräteübergreifend nach Bedrohungen sucht.</span><span class="sxs-lookup"><span data-stu-id="42fb1-136">Having multiple MTD tools enabled will force all MTD apps to be installed and scan across devices for threats.</span></span>

## <a name="mobile-threat-defense-partners"></a><span data-ttu-id="42fb1-137">Mobile Threat Defense-Partner</span><span class="sxs-lookup"><span data-stu-id="42fb1-137">Mobile Threat Defense partners</span></span>

<span data-ttu-id="42fb1-138">Lernen Sie, wie Sie den Zugriffs auf Unternehmensressourcen auf der Basis von Geräte-, Netzwerk- und Anwendungsrisiko schützen:</span><span class="sxs-lookup"><span data-stu-id="42fb1-138">Learn how to protect access to company resource based on device, network, and application risk with:</span></span>

- [<span data-ttu-id="42fb1-139">Lookout</span><span class="sxs-lookup"><span data-stu-id="42fb1-139">Lookout</span></span>](lookout-mobile-threat-defense-connector.md)
- [<span data-ttu-id="42fb1-140">Skycure</span><span class="sxs-lookup"><span data-stu-id="42fb1-140">Skycure</span></span>](skycure-mobile-threat-defense-connector.md)
- [<span data-ttu-id="42fb1-141">Check Point SandBlast Mobile</span><span class="sxs-lookup"><span data-stu-id="42fb1-141">Check Point SandBlast Mobile</span></span>](checkpoint-sandblast-mobile-mobile-threat-defense-connector.md)
- [<span data-ttu-id="42fb1-142">Zimperium</span><span class="sxs-lookup"><span data-stu-id="42fb1-142">Zimperium</span></span>](zimperium-mobile-threat-defense-connector.md)
