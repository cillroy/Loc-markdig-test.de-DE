---
title: Intune Mobile Threat Defense
description: "Schützen Sie den Zugriff auf Unternehmensressourcen auf der Basis von Geräterisiko."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 03/01/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 08d87906-8158-4d5e-a49d-ad919efef3d1
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: f565ab0bca4fd2c283a4c8251f78c44ccd304065
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2017
---
# <a name="intune-mobile-threat-defense-connectors"></a><span data-ttu-id="f188c-103">Intune Mobile Threat Defense-Connector</span><span class="sxs-lookup"><span data-stu-id="f188c-103">Intune Mobile Threat Defense connectors</span></span>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="f188c-104">Mit Intune Mobile Threat Defense-Connectors können Sie Ihren ausgewählten Mobile Threat Defense-Hersteller als Informationsquelle für Ihre Konformitätsrichtlinien und bedingte Zugriffsregeln nutzen.</span><span class="sxs-lookup"><span data-stu-id="f188c-104">Intune Mobile Threat Defense connectors allow you to leverage your chosen Mobile Threat Defense vendor as a source of information for your compliance policies and conditional access rules.</span></span> <span data-ttu-id="f188c-105">Dadurch können IT-Administratoren eine Schutzeben auf ihre Unternehmensressoucen wie Exchange und Sharepoint anwenden, besonders von gefährdeten Mobilgeräten.</span><span class="sxs-lookup"><span data-stu-id="f188c-105">This allows IT Administrators to add a layer of protection to their corporate resources such as Exchange and Sharepoint, specifically from compromised mobile devices.</span></span>

## <a name="what-problem-does-this-solve"></a><span data-ttu-id="f188c-106">Welches Problem wird dadurch gelöst?</span><span class="sxs-lookup"><span data-stu-id="f188c-106">What problem does this solve?</span></span>

<span data-ttu-id="f188c-107">Unternehmen müssen vertrauliche Daten vor auftretenden Bedrohungen schützen. Dazu gehören physische, App-und netzwerkbasierte Bedrohungen sowie Sicherheitsrisiken beim Betriebssystem.</span><span class="sxs-lookup"><span data-stu-id="f188c-107">Companies need to protect sensitive data from emerging threats including physical, app-based, and network-based threats, as well as operating system vulnerabilities.</span></span>
<span data-ttu-id="f188c-108">In der Vergangenheit haben Firmen PCs vor Angriffen proaktiv geschützt, während mobile Geräte nicht überwacht wurden und ungeschützt blieben.</span><span class="sxs-lookup"><span data-stu-id="f188c-108">Historically, companies have been proactive when protecting PCs from attack, while mobile devices go un-monitored and unprotected.</span></span> <span data-ttu-id="f188c-109">Mobile Plattformen bieten integrierten Schutz in Form von App-Isolierung und sicherheitsgeprüfter App Stores für Verbraucher, doch diese Plattformen bleiben weiterhin für komplexe Angriffe anfällig.</span><span class="sxs-lookup"><span data-stu-id="f188c-109">Mobile platforms have built-in protection such as app isolation and vetted consumer app stores, but these platforms remain vulnerable to sophisticated attacks.</span></span> <span data-ttu-id="f188c-110">Immer mehr Mitarbeiter nutzen ihre Geräte für die Arbeit und benötigen Zugriff auf vertrauliche Informationen.</span><span class="sxs-lookup"><span data-stu-id="f188c-110">Today, more employees use devices for work and need access to sensitive information.</span></span> <span data-ttu-id="f188c-111">Geräte müssen gegen zunehmend raffinierter werdende Angriffe geschützt werden.</span><span class="sxs-lookup"><span data-stu-id="f188c-111">Devices need to be protected from increasingly sophisticated attacks.</span></span>

## <a name="how-the-intune-mobile-threat-defense-connectors-work"></a><span data-ttu-id="f188c-112">Wie funktioniert der Intune Mobile Threat Defense-Connector?</span><span class="sxs-lookup"><span data-stu-id="f188c-112">How the Intune Mobile Threat Defense connectors work?</span></span>

<span data-ttu-id="f188c-113">Der Connector schützt Unternehmensressourcen, indem er einen Kommunikationskanal zwischen Intune und Ihrem ausgewählten Mobile Threat Defense-Hersteller erstellt.</span><span class="sxs-lookup"><span data-stu-id="f188c-113">The connector protects company resources by creating a channel of communication between Intune and your chosen Mobile Threat Defense vendor.</span></span> <span data-ttu-id="f188c-114">Intune Mobile Threat Defense-Partner bieten intuitive und leicht bereitzustellende Anwendungen für Mobilgeräte, die aktiv Informationen zu Bedrohungen überprüfen und analysieren, um sie mit Intune für Berichts- oder Erzwingungszwecke zu teilen.</span><span class="sxs-lookup"><span data-stu-id="f188c-114">Intune Mobile Threat Defense partners offer intuitive, easy to deploy applications for mobile devices which actively scan and analyze threat information to share with Intune, for either reporting or enforcement purposes.</span></span> <span data-ttu-id="f188c-115">Wenn eine verbundene Mobile Threat Defense-App z.B. einem Mobile Threat Defense-Hersteller mitteilt, dass ein Telefon in Ihrem Netzwerk aktuell mit einem Netzwerk verbunden ist, das anfällig für „Man in the Middle“-Angriffe ist, wird diese Information an eine entsprechende Risikostufe (niedrig/mittel/hoch) weitergeleitet. Diese kann anschließend mit Ihren konfigurierten Zulassungen der Risikostufe in Intune verglichen werden, um zu bestimmen, ob der Zugriff auf bestimmte Ressourcen Ihrer Wahl aufgehoben werden sollte, während das Gerät gefährdet ist.</span><span class="sxs-lookup"><span data-stu-id="f188c-115">For example, if a connected Mobile Threat Defense app reports to the Mobile Threat Defense vendor that a phone on your network is currently connected to a network which is vulnerable to Man in the Middle attacks, this information is shared with and categorized to an appropriate risk level (low/medium/high) – which can then be compared with your configured risk level allowances in Intune to determine if access to certain resources of your choice should be revoked while the device is compromised.</span></span>

## <a name="sample-scenarios"></a><span data-ttu-id="f188c-116">Beispielszenarien</span><span class="sxs-lookup"><span data-stu-id="f188c-116">Sample scenarios</span></span>

<span data-ttu-id="f188c-117">Wenn ein Gerät von der Mobile Threat Defense-Lösung als gefährdet eingestuft wird:</span><span class="sxs-lookup"><span data-stu-id="f188c-117">When a device is considered infected by the Mobile Threat Defense solution:</span></span>

![Mobile Threat Defense infected device (Mobile Threat Defense – Gefährdetes Gerät)](../media/mtp/MTD-image-1.png)

<span data-ttu-id="f188c-119">Der Zugriff wird gewährt, wenn das Gerät wiederhergestellt ist:</span><span class="sxs-lookup"><span data-stu-id="f188c-119">Access is granted when the device is remediated:</span></span>

![Mobile Threat Defense Access granted (Mobile Threat Defense – Zugriff gewährt)](../media/mtp/MTD-image-2.png)

## <a name="mobile-threat-defense-partners"></a><span data-ttu-id="f188c-121">Mobile Threat Defense-Partner</span><span class="sxs-lookup"><span data-stu-id="f188c-121">Mobile Threat Defense partners</span></span>

<span data-ttu-id="f188c-122">Lernen Sie, wie Sie den Zugriffs auf Unternehmensressourcen auf der Basis von Geräte-, Netzwerk- und Anwendungsrisiko schützen:</span><span class="sxs-lookup"><span data-stu-id="f188c-122">Learn how to protect access to company resource based on device, network, and application risk with:</span></span>

- [<span data-ttu-id="f188c-123">Lookout</span><span class="sxs-lookup"><span data-stu-id="f188c-123">Lookout</span></span>](/intune-classic/deploy-use/lookout-mobile-threat-defense-connector)
- [<span data-ttu-id="f188c-124">Skycure</span><span class="sxs-lookup"><span data-stu-id="f188c-124">Skycure</span></span>](/intune-classic/deploy-use/skycure-mobile-threat-defense-connector)
