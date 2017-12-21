---
title: Funktionsweise eines typischen Migrationszyklus in Intune
description: "In diesem Artikel wird erläutert, wie ein Intune-Migrationszyklus funktioniert. Zudem enthält er Beispiele für den Umgang mit den Migrationszyklen."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 07/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3688b724-9521-4210-bf4d-bcf47d8d4ca0
ms.reviewer: dagerrit
ms.suite: ems
ms.openlocfilehash: 34e748e16449a99bad4c1f3e96c22dda6d8f3018
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2017
---
# <a name="typical-migration-cycle"></a><span data-ttu-id="f7331-103">Typischer Migrationszyklus</span><span class="sxs-lookup"><span data-stu-id="f7331-103">Typical migration cycle</span></span>

<span data-ttu-id="f7331-104">Es ist üblich, dass eine Organisation ihre Intune-Migration mit einem kleinen Pilotversuch mit einer Teilmenge aller Benutzer in ihrer IT-Abteilung startet.</span><span class="sxs-lookup"><span data-stu-id="f7331-104">It’s common for an organization to start their Intune migration with a small pilot by targeting a subset of their users in the IT department.</span></span> <span data-ttu-id="f7331-105">Zusätzlich muss Ihre Organisation möglicherweise Faktoren wie die Änderungsbereitschaft der Gruppe, die Anzahl der Benutzer, die Komplexität, die Anforderungen, den Ort und die Geschäftsrisiken besprechen, um einen Zeitrahmen für die Migration festlegen zu können.</span><span class="sxs-lookup"><span data-stu-id="f7331-105">Additionally, your organization may need to discuss such factors as the group’s willingness for change, number of users, complexity, requirements, location, and business risk to assist in determining the migration time-frame.</span></span>

<span data-ttu-id="f7331-106">Hier ist ein Beispiel, wie Sie Ihre Zielgruppen planen können:</span><span class="sxs-lookup"><span data-stu-id="f7331-106">Here’s an example of how your target groups could be scheduled:</span></span>

  | <span data-ttu-id="f7331-107">**Migration der Zielgruppen**</span><span class="sxs-lookup"><span data-stu-id="f7331-107">**Migration targeted groups**</span></span> | <span data-ttu-id="f7331-108">**Zeitraum 1**</span><span class="sxs-lookup"><span data-stu-id="f7331-108">**Time period 1**</span></span> | <span data-ttu-id="f7331-109">**Zeitraum 2**</span><span class="sxs-lookup"><span data-stu-id="f7331-109">**Time period 2**</span></span> | <span data-ttu-id="f7331-110">**Zeitraum 3**</span><span class="sxs-lookup"><span data-stu-id="f7331-110">**Time period 3**</span></span> | <span data-ttu-id="f7331-111">**Zeitraum 4**</span><span class="sxs-lookup"><span data-stu-id="f7331-111">**Time period 4**</span></span> | <span data-ttu-id="f7331-112">**...**</span><span class="sxs-lookup"><span data-stu-id="f7331-112">**...**</span></span>
|:---:|:---:|:---:|:---:|:---:|:---:|
| <span data-ttu-id="f7331-113">Begrenzter Pilotversuch der IT-Organisation (50 Benutzer)</span><span class="sxs-lookup"><span data-stu-id="f7331-113">Limited Pilot IT org (50 users)</span></span> | <span data-ttu-id="f7331-114">Plan bekannt geben</span><span class="sxs-lookup"><span data-stu-id="f7331-114">Announce Plan</span></span> | <span data-ttu-id="f7331-115">Anweisung zum Registrieren</span><span class="sxs-lookup"><span data-stu-id="f7331-115">Instruct to enroll</span></span> | <span data-ttu-id="f7331-116">Frist setzen</span><span class="sxs-lookup"><span data-stu-id="f7331-116">Give deadline</span></span> | <span data-ttu-id="f7331-117">Erzwingen des bedingten Zugriffs</span><span class="sxs-lookup"><span data-stu-id="f7331-117">Enforce conditional access</span></span> |  |                                                        
| <span data-ttu-id="f7331-118">Erweiterter Pilotversuch der IT-Organisation (200 Benutzer)</span><span class="sxs-lookup"><span data-stu-id="f7331-118">Expanded Pilot IT org (200 users)</span></span> |  | <span data-ttu-id="f7331-119">Plan bekannt geben</span><span class="sxs-lookup"><span data-stu-id="f7331-119">Announce Plan</span></span> | <span data-ttu-id="f7331-120">Anweisung zum Registrieren</span><span class="sxs-lookup"><span data-stu-id="f7331-120">Instruct to enroll</span></span> | <span data-ttu-id="f7331-121">Frist setzen</span><span class="sxs-lookup"><span data-stu-id="f7331-121">Give deadline</span></span> | <span data-ttu-id="f7331-122">Erzwingen des bedingten Zugriffs</span><span class="sxs-lookup"><span data-stu-id="f7331-122">Enforce conditional access</span></span> |
| <span data-ttu-id="f7331-123">Phase 1 der Migration Technologisch kompetente Benutzer (2000)</span><span class="sxs-lookup"><span data-stu-id="f7331-123">Migration phase 1 Tech-savvy users (2000)</span></span> |  |  | <span data-ttu-id="f7331-124">Plan bekannt geben</span><span class="sxs-lookup"><span data-stu-id="f7331-124">Announce Plan</span></span> | <span data-ttu-id="f7331-125">Anweisung zum Registrieren</span><span class="sxs-lookup"><span data-stu-id="f7331-125">Instruct to enroll</span></span> | <span data-ttu-id="f7331-126">Frist setzen</span><span class="sxs-lookup"><span data-stu-id="f7331-126">Give deadline</span></span> |
| <span data-ttu-id="f7331-127">Phase 2 der Migration Osten der USA</span><span class="sxs-lookup"><span data-stu-id="f7331-127">Migration phase 2 Eastern US</span></span> |  |  |  | <span data-ttu-id="f7331-128">Plan bekannt geben</span><span class="sxs-lookup"><span data-stu-id="f7331-128">Announce Plan</span></span> | <span data-ttu-id="f7331-129">Anweisung zum Registrieren</span><span class="sxs-lookup"><span data-stu-id="f7331-129">Instruct to enroll</span></span> |
| <span data-ttu-id="f7331-130">Alle Regionen</span><span class="sxs-lookup"><span data-stu-id="f7331-130">All Regions</span></span> |  |  |  |  | <span data-ttu-id="f7331-131">Plan bekannt geben</span><span class="sxs-lookup"><span data-stu-id="f7331-131">Announce Plan</span></span> |

## <a name="customer-migration-case-study"></a><span data-ttu-id="f7331-132">Fallstudie für die Kundenmigration</span><span class="sxs-lookup"><span data-stu-id="f7331-132">Customer migration case study</span></span>

### <a name="adatum-corporation"></a><span data-ttu-id="f7331-133">Adatum Corporation</span><span class="sxs-lookup"><span data-stu-id="f7331-133">Adatum Corporation</span></span>

<span data-ttu-id="f7331-134">Schauen Sie sich an, [wie Adatum Corporation von einer Drittanbieter-MDM zu Intune migriert ist](https://gallery.technet.microsoft.com/Intune-migration-guide-893a95e3?redir=0).</span><span class="sxs-lookup"><span data-stu-id="f7331-134">Check out [how Adatum Corporation went through the process of migration from a third-party MDM provider to Intune](https://gallery.technet.microsoft.com/Intune-migration-guide-893a95e3?redir=0).</span></span>

## <a name="monitoring-migration"></a><span data-ttu-id="f7331-135">Migrationsüberwachung</span><span class="sxs-lookup"><span data-stu-id="f7331-135">Monitoring migration</span></span>

<span data-ttu-id="f7331-136">Intune stellt mehrere Methoden bereit, mit denen Sie Ihre Migration überwachen können:</span><span class="sxs-lookup"><span data-stu-id="f7331-136">Intune provides several ways that you can monitor your migration:</span></span>

* <span data-ttu-id="f7331-137">Gruppenansichten für Intune-Benutzer</span><span class="sxs-lookup"><span data-stu-id="f7331-137">Intune user group views</span></span>

* <span data-ttu-id="f7331-138">Integrierte Berichte</span><span class="sxs-lookup"><span data-stu-id="f7331-138">Set of built-in reports</span></span>

* <span data-ttu-id="f7331-139">Konsoleninterne Warnungen</span><span class="sxs-lookup"><span data-stu-id="f7331-139">In-console alerts</span></span>

<span data-ttu-id="f7331-140">Verfolgen Sie nach, wie viele Benutzer nach jeder Phase Geräte registriert haben, damit Sie:</span><span class="sxs-lookup"><span data-stu-id="f7331-140">Track how many users have enrolled devices after each phase so that you can:</span></span>

-   <span data-ttu-id="f7331-141">die Effektivität der Kommunikationsplan bewerten können</span><span class="sxs-lookup"><span data-stu-id="f7331-141">Evaluate the effectiveness of your communication plan.</span></span>

-   <span data-ttu-id="f7331-142">die Auswirkungen des Erzwingens von bedingtem Zugriff einschätzen können</span><span class="sxs-lookup"><span data-stu-id="f7331-142">Estimate the impact of enforcing conditional access.</span></span>


## <a name="post-migration"></a><span data-ttu-id="f7331-143">Aufgaben nach der Migration</span><span class="sxs-lookup"><span data-stu-id="f7331-143">Post-migration</span></span>

<span data-ttu-id="f7331-144">Setzen Sie den vorherigen MDM-Anbieter außer Kraft, und beenden Sie das Abonnement des Diensts, nachdem Sie zu Intune migriert sind.</span><span class="sxs-lookup"><span data-stu-id="f7331-144">Retire the previous MDM provider and unsubscribe from the service after migrating to Intune.</span></span> <span data-ttu-id="f7331-145">Darüber hinaus müssen Sie alle nicht benötigten Infrastrukturanforderungen entfernen, indem Sie den Anweisungen des MDM-Anbieters folgen.</span><span class="sxs-lookup"><span data-stu-id="f7331-145">Additionally, remove any unneeded infrastructure requirements by following the MDM provider’s instructions.</span></span>
