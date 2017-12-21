---
title: Starten einer Intune-Migration
description: "Dieser Artikel enthält einen Leitfaden für die Vorgehensweise beim Starten einer Migrationskampagne."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 07/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f781b029-50f2-46ee-8ff7-03b4a6719e80
ms.reviewer: dagerrit
ms.suite: ems
ms.openlocfilehash: a272d9c822a2c17592d7800c20278ce222d615bd
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2017
---
# <a name="phase-2-migration-campaign"></a><span data-ttu-id="1b384-103">Phase 2: Migrationskampagne</span><span class="sxs-lookup"><span data-stu-id="1b384-103">Phase 2: Migration campaign</span></span>

<span data-ttu-id="1b384-104">Wählen Sie einen Migrationsansatz aus, der am besten für die Anforderungen Ihres Unternehmens geeignet ist, und passen Sie Implementierungstaktiken basierend auf Ihren speziellen Anforderungen entsprechend an.</span><span class="sxs-lookup"><span data-stu-id="1b384-104">Choose a migration approach that is most suitable for your organization's needs and adjust implementation tactics based on your specific requirements.</span></span> <span data-ttu-id="1b384-105">Diese Anleitung hilft Ihnen bei der Registrierung Ihrer Geräte in Intune.</span><span class="sxs-lookup"><span data-stu-id="1b384-105">The remainder of this guide will equip you with the tools you need to achieve the goal of getting your users’ devices enrolled into Intune.</span></span>

## <a name="keys-to-a-successful-migration"></a><span data-ttu-id="1b384-106">Wichtige Faktoren für eine erfolgreiche Migration</span><span class="sxs-lookup"><span data-stu-id="1b384-106">Keys to a successful migration</span></span>

<span data-ttu-id="1b384-107">Dies sind die Schlüssel für die erfolgreiche Migration eines MDM-Drittanbieters in Intune:</span><span class="sxs-lookup"><span data-stu-id="1b384-107">These are the keys to migrating successfully from a third-party MDM provider to Intune:</span></span>

-   <span data-ttu-id="1b384-108">Durch eine klare und hilfreiche Kommunikation können Ausfallzeiten und Unzufriedenheit von Endbenutzern minimiert werden.</span><span class="sxs-lookup"><span data-stu-id="1b384-108">Clear and helpful communication can minimize end-user downtime and dissatisfaction.</span></span>

-   <span data-ttu-id="1b384-109">Achten Sie darauf, dass Sie genaue Anweisungen für die Migration geben.</span><span class="sxs-lookup"><span data-stu-id="1b384-109">Be sure to have specific and concrete migration instructions.</span></span>

-   <span data-ttu-id="1b384-110">Die Registrierung aller verwalteten Geräte Ihres vorhandenen MDM-Anbieters muss vor der Registrierung in Intune aufgehoben werden.</span><span class="sxs-lookup"><span data-stu-id="1b384-110">All managed devices must be unenrolled from your existing MDM provider before they can be enrolled in Intune.</span></span>

-   <span data-ttu-id="1b384-111">Stellen Sie für die Endbenutzer eine Anleitung des alten MDM-Anbieters für das Aufheben der Geräteregistrierung bereit.</span><span class="sxs-lookup"><span data-stu-id="1b384-111">Provide guidance from your existing MDM provider to end-users for how to unenroll their devices.</span></span>

-   <span data-ttu-id="1b384-112">Gehen Sie schrittweise vor.</span><span class="sxs-lookup"><span data-stu-id="1b384-112">Use a phased approach.</span></span> <span data-ttu-id="1b384-113">Beginnen Sie mit einer kleinen Gruppe von Pilotbenutzern und fügen Sie nach und nach mehr Benutzergruppen hinzu, bis alle bereitgestellt wurden.</span><span class="sxs-lookup"><span data-stu-id="1b384-113">Start with a small group of pilot users and incrementally add more groups of users until you reach full scale deployment.</span></span>

-   <span data-ttu-id="1b384-114">Überwachen Sie das Laden des Helpdesks und den Registrierungserfolg der jeweiligen Zyklen.</span><span class="sxs-lookup"><span data-stu-id="1b384-114">Monitor the helpdesk load and enrollment success of each cycle.</span></span> <span data-ttu-id="1b384-115">Planen Sie großzügig, um sicherzustellen, dass Erfolgskriterien für jede Gruppe ausgewertet werden können, bevor Sie mit der Migration der nächsten beginnen.</span><span class="sxs-lookup"><span data-stu-id="1b384-115">Leave time in the schedule to ensure success criteria can be evaluated for each group before migrating the next.</span></span> <span data-ttu-id="1b384-116">Ihre Pilotbereitstellung sollte Folgendes überprüfen:</span><span class="sxs-lookup"><span data-stu-id="1b384-116">Your pilot deployment should validate the following:</span></span>

    -   <span data-ttu-id="1b384-117">ob sich die Registrierungerfolgs- und Fehlerraten im Rahmen bewegen</span><span class="sxs-lookup"><span data-stu-id="1b384-117">Enrollment success and failure rates are within expectations.</span></span>

    -   <span data-ttu-id="1b384-118">Benutzerproduktivität:</span><span class="sxs-lookup"><span data-stu-id="1b384-118">User productivity:</span></span>

        -   <span data-ttu-id="1b384-119">Unternehmensressourcen wie z.B. VPN, Wi-Fi, E-Mail und Zertifikate funktionieren ordnungsgemäß.</span><span class="sxs-lookup"><span data-stu-id="1b384-119">Corporate resources such as VPN, Wi-Fi, email, and certificates are working.</span></span>

        -   <span data-ttu-id="1b384-120">Auf bereitgestellte Apps kann zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="1b384-120">Provisioned apps are accessible.</span></span>

    -   <span data-ttu-id="1b384-121">Datensicherheit:</span><span class="sxs-lookup"><span data-stu-id="1b384-121">Data security:</span></span>

        -   <span data-ttu-id="1b384-122">Kompatibilitätsberichte treten auf.</span><span class="sxs-lookup"><span data-stu-id="1b384-122">Compliance reporting is occurring.</span></span>

        -   <span data-ttu-id="1b384-123">Schutzmaßnahmen für mobile Apps werden erzwungen.</span><span class="sxs-lookup"><span data-stu-id="1b384-123">Mobile app protections are enforced.</span></span>

<span data-ttu-id="1b384-124">Wenn Sie mit der ersten Phase der Migration zufrieden sind, wiederholen Sie den [Migrationszyklus](migration-guide-cycle.md) für die nächste Phase.</span><span class="sxs-lookup"><span data-stu-id="1b384-124">When you are satisfied with the first phase of migrations, repeat the [migration cycle](migration-guide-cycle.md) for the next phase.</span></span>

-   <span data-ttu-id="1b384-125">Wiederholen Sie die Zyklen in Phasen, bis alle Benutzer zu Intune migriert wurden.</span><span class="sxs-lookup"><span data-stu-id="1b384-125">Repeat phased cycles until all users are migrated to Intune.</span></span>

-   <span data-ttu-id="1b384-126">Stellen Sie sicher, dass das Helpdesk-Team zur Unterstützung der Endbenutzer während der gesamten Migration zur Verfügung steht.</span><span class="sxs-lookup"><span data-stu-id="1b384-126">Ensure the helpdesk team is ready to support end users throughout the migration campaign.</span></span> <span data-ttu-id="1b384-127">Führen Sie eine freiwillige Migration aus, bis Sie die Arbeitsauslastung für Supportanrufe einschätzen können.</span><span class="sxs-lookup"><span data-stu-id="1b384-127">Run a voluntary migration until you can estimate support call workload.</span></span>

-   <span data-ttu-id="1b384-128">Legen Sie keine Frist für die Registrierung fest, bis die verbleibende Auffüllung von Ihrem Helpdesk verarbeitet werden kann</span><span class="sxs-lookup"><span data-stu-id="1b384-128">Don’t set deadlines for enrollment until the remaining population can be handled by your helpdesk</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1b384-129">Konfigurieren Sie Intune und Ihre vorhandene Drittanbieter-MDM-Projektmappe nicht gleichzeitig so, dass Zugriffssteuerelemente auf Ressourcen wie Exchange oder SharePoint Online angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="1b384-129">Do not configure both Intune and your existing third party MDM solution to apply access controls to resources such as Exchange or SharePoint Online.</span></span> <span data-ttu-id="1b384-130">Zusätzlich sollten Geräte immer nur in einer Projektmappe gleichzeitig registriert sein.</span><span class="sxs-lookup"><span data-stu-id="1b384-130">Additionally, devices should only be enrolled in one solution at a time.</span></span>

## <a name="next-steps"></a><span data-ttu-id="1b384-131">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="1b384-131">Next steps</span></span>

<span data-ttu-id="1b384-132">Erstellen Sie Ihren [Kommunikationsplan](migration-guide-communication-plan.md).</span><span class="sxs-lookup"><span data-stu-id="1b384-132">Create your [communication plan](migration-guide-communication-plan.md).</span></span>
