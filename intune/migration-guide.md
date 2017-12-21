---
title: "Migrationshandbuch für die Verwaltung mobiler Geräte mit Intune"
description: "Dieses Handbuch führt Sie durch die detaillierten Informationen zu den verschiedenen Aspekten bei der Migration von einem MDM-Drittanbieter zu Microsoft Intune."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 07/11/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: dcfc21f9-1bcd-4371-a46d-f2e18154ec50
ms.reviewer: dagerrit
ms.suite: ems
ms.openlocfilehash: d86260872230bb0a9274fa302acac5caeaa682a7
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2017
---
# <a name="intune-migration-guide"></a><span data-ttu-id="c9f3d-103">Intune-Migrationshandbuch</span><span class="sxs-lookup"><span data-stu-id="c9f3d-103">Intune migration guide</span></span>

![Artikel MDM-Intune-Migrationshandbuch](./media/MDM-migration-guide-art.PNG)

<span data-ttu-id="c9f3d-105">Eine erfolgreiche Migration in Intune beginnt mit einem soliden Plan, der Ihre aktuelle MDM-Umgebung (Mobile Device Management, Verwaltung mobiler Geräte), Geschäftsziele und technische Anforderungen miteinbezieht.</span><span class="sxs-lookup"><span data-stu-id="c9f3d-105">A successful migration to Intune starts with a solid plan that factors in your current mobile device management (MDM) environment, business goals, and technical requirements.</span></span> <span data-ttu-id="c9f3d-106">Zusätzlich müssen Sie die wichtigsten Stakeholder kennen, die Ihren Migrationsplan unterstützen und bei diesem mit Ihnen zusammenarbeiten werden.</span><span class="sxs-lookup"><span data-stu-id="c9f3d-106">Additionally, you need to have the key stakeholders whose will support and collaborate with your migration plan.</span></span>

<span data-ttu-id="c9f3d-107">Hier finden Sie detaillierte Informationen zu den verschiedenen Aspekten bei der Migration von einem MDM-Drittanbieter zu Intune.</span><span class="sxs-lookup"><span data-stu-id="c9f3d-107">This guide walks you through the various details involved in migrating from a third-party MDM provider to Intune.</span></span>

## <a name="whats-included-in-this-guide"></a><span data-ttu-id="c9f3d-108">Inhalt dieses Handbuchs</span><span class="sxs-lookup"><span data-stu-id="c9f3d-108">What’s included in this guide?</span></span>

<span data-ttu-id="c9f3d-109">Dieses Handbuch teilt die Migration in zwei Phasen auf, die beide Aufgaben, Strategien und Unterstützung bei der Vorgehensweise beinhalten, die Sie während der Migration zu Intune MDM Schritt für Schritt begleiten.</span><span class="sxs-lookup"><span data-stu-id="c9f3d-109">This guide breaks down the migration into two phases, both of which include tasks, strategies, and tactical guidance that will help you step through the end-to-end process of migrating to Intune MDM.</span></span>

-   [<span data-ttu-id="c9f3d-110">Phase 1: Vorbereitung von Intune für die Verwaltung mobiler Geräte</span><span class="sxs-lookup"><span data-stu-id="c9f3d-110">Phase 1: Prepare Intune for mobile device management</span></span>](migration-guide-prepare.md)

    -   [<span data-ttu-id="c9f3d-111">Anforderungen Ihrer MDM-Migration analysieren</span><span class="sxs-lookup"><span data-stu-id="c9f3d-111">Assess your MDM migration requirements</span></span>](migration-guide-prepare.md#assess-mdm-requirements)

    -   [<span data-ttu-id="c9f3d-112">Grundlegende Einrichtung</span><span class="sxs-lookup"><span data-stu-id="c9f3d-112">Basic setup</span></span>](migration-guide-setup.md)

    -   [<span data-ttu-id="c9f3d-113">Konfigurieren von Richtlinien für die Verwaltung von Apps und Geräten</span><span class="sxs-lookup"><span data-stu-id="c9f3d-113">Configure device and app management policies</span></span>](migration-guide-configure-policies.md)

    -   [<span data-ttu-id="c9f3d-114">Konfigurieren von App-Schutzrichtlinien</span><span class="sxs-lookup"><span data-stu-id="c9f3d-114">Configure app protection policies</span></span>](migration-guide-app-protection-policies.md)

    -   [<span data-ttu-id="c9f3d-115">Besondere Überlegungen bei der Migration</span><span class="sxs-lookup"><span data-stu-id="c9f3d-115">Special migration considerations</span></span>](migration-guide-considerations.md)

-   [<span data-ttu-id="c9f3d-116">Phase 2: Die Migration</span><span class="sxs-lookup"><span data-stu-id="c9f3d-116">Phase 2: Migration campaign</span></span>](migration-guide-campaign.md)

    -   [<span data-ttu-id="c9f3d-117">Kommunikationsplan</span><span class="sxs-lookup"><span data-stu-id="c9f3d-117">Communication plan</span></span>](migration-guide-communication-plan.md)

    -   [<span data-ttu-id="c9f3d-118">Fördern der Einführung mit bedingtem Zugriff für Endbenutzer</span><span class="sxs-lookup"><span data-stu-id="c9f3d-118">Drive end-user adoption with conditional access</span></span>](migration-guide-drive-adoption.md)

    -   [<span data-ttu-id="c9f3d-119">typischer Migrationszyklus</span><span class="sxs-lookup"><span data-stu-id="c9f3d-119">Typical migration cycle</span></span>](migration-guide-cycle.md)
        -   [<span data-ttu-id="c9f3d-120">Migrationsüberwachung</span><span class="sxs-lookup"><span data-stu-id="c9f3d-120">Monitoring migration</span></span>](migration-guide-cycle.md#monitoring-migration)
        -   [<span data-ttu-id="c9f3d-121">Aufgaben nach der Migration</span><span class="sxs-lookup"><span data-stu-id="c9f3d-121">Post migration</span></span>](migration-guide-cycle.md#post-migration)

## <a name="assumptions"></a><span data-ttu-id="c9f3d-122">Annahmen</span><span class="sxs-lookup"><span data-stu-id="c9f3d-122">Assumptions</span></span>

-   <span data-ttu-id="c9f3d-123">Sie haben Intune bereits in einer PoC-Umgebung (Proof of Concept) evaluiert und entschieden, diese Lösung zur Verwaltung mobiler Geräte in Ihrer Organisation einzusetzen.</span><span class="sxs-lookup"><span data-stu-id="c9f3d-123">You've already evaluated Intune in a proof of concept (PoC) environment, and have decided to use it as the MDM solution in your organization.</span></span>

-   <span data-ttu-id="c9f3d-124">Sie sind bereits mit Intune und seinen Funktionen vertraut.</span><span class="sxs-lookup"><span data-stu-id="c9f3d-124">You are already familiar with Intune and its features.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="c9f3d-125">Vorbereitung</span><span class="sxs-lookup"><span data-stu-id="c9f3d-125">Before you begin</span></span>

<span data-ttu-id="c9f3d-126">Es ist wichtig, dass Sie wissen, dass Ihre Bereitstellung mit Intune möglicherweise von Ihrer alten MDM-Bereitstellung unterscheidet.</span><span class="sxs-lookup"><span data-stu-id="c9f3d-126">It's important to recognize that your new Intune deployment might be different from your old MDM deployment.</span></span> <span data-ttu-id="c9f3d-127">Im Gegensatz zu herkömmlichen MDM-Diensten baut Intune auf der identitätsgesteuerten Zugriffssteuerung auf, weshalb keine Netzwerkproxyvorrichtung zur Zugriffssteuerung auf Unternehmensdaten von mobilen Geräten außerhalb des Netzwerkumkreises der Organisation erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="c9f3d-127">Unlike traditional MDM services, Intune centers on identity-driven access control, and so does not require a network proxy appliance to control access to corporate data from mobile devices outside the organization's network perimeter.</span></span> <span data-ttu-id="c9f3d-128">Microsoft bietet Lösungen zur Sicherung von Datendiensten innerhalb der Cloud selbst durch eine Folge von fest integrierten Clouddiensten, die zusammen als Angebot von Enterprise Client und Security bezeichnet werden.</span><span class="sxs-lookup"><span data-stu-id="c9f3d-128">Microsoft offers solutions to secure data services within the cloud itself through a suite of tightly integrated cloud services, collectively referred to as the Enterprise Client + Security offering.</span></span>

-   <span data-ttu-id="c9f3d-129">Erfahren Sie mehr über die [gängigsten Arten der Verwendung von Intune](common-scenarios.md).</span><span class="sxs-lookup"><span data-stu-id="c9f3d-129">Review the [common ways to use Intune](common-scenarios.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="c9f3d-130">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="c9f3d-130">Next steps</span></span>

[<span data-ttu-id="c9f3d-131">Phase 1: Vorbereitung von Intune für die Verwaltung mobiler Geräte</span><span class="sxs-lookup"><span data-stu-id="c9f3d-131">Phase 1: Prepare Intune for mobile device management</span></span>](migration-guide-prepare.md)
