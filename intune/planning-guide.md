---
title: "Einführung in die Planung und den Entwurf von Intune"
description: "Dieser Artikel bietet eine Einführung in alle Abschnitte der Planung, des Entwurfs und der Implementierung von Intune. Tools zum Bestimmen von Zielen, Anwendungsfallszenarien und Anforderungen, Erstellen von Rollout- und Kommunikationsplänen sowie von Support-, Test- und Überprüfungsplänen."
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 10/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a65efa6e-4a48-47f3-8f6e-34a85ca64ced
ms.reviewer: jeffbu, cgerth
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 81dd87a378e1bbdb2c2c814cbfa254c5ad28a6e5
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2018
---
# <a name="intune-deployment-planning-design-and-implementation-guide"></a><span data-ttu-id="22685-104">Bereitstellungsplanungs-, Entwurfs- und Implementierungshandbuch für Intune</span><span class="sxs-lookup"><span data-stu-id="22685-104">Intune deployment planning, design, and implementation guide</span></span>

[!INCLUDE [note for both-portals](./includes/note-for-both-portals.md)]

<span data-ttu-id="22685-105">Eine erfolgreiche Bereitstellung von Intune beginnt mit einer guten Planung und einem guten Entwurf.</span><span class="sxs-lookup"><span data-stu-id="22685-105">A successful Intune deployment starts with having a good plan and design.</span></span> <span data-ttu-id="22685-106">Zweck dieses Handbuchs ist es, Sie schrittweise durch den Prozess der Entwicklung eines Bereitstellungsplans, Erstellung eines Entwurfs, des Onboardings von Intune und der Einführung in die Produktion zu begleiten.</span><span class="sxs-lookup"><span data-stu-id="22685-106">The purpose of this guide is to step you through the process of developing a deployment plan, creating a design, onboarding Intune, and conducting a production rollout.</span></span>

## <a name="whats-included-in-this-guide"></a><span data-ttu-id="22685-107">Inhalt dieses Handbuchs</span><span class="sxs-lookup"><span data-stu-id="22685-107">What’s included in this guide?</span></span>

<span data-ttu-id="22685-108">Dieses Handbuch enthält Abschnitte, in denen Sie lückenlos durch die Bereitstellung von Intune geführt werden.</span><span class="sxs-lookup"><span data-stu-id="22685-108">This guide includes sections that will walk you through the end-to-end process of deploying Intune.</span></span> <span data-ttu-id="22685-109">Beginnen Sie mit Abschnitt 1, um Ihre lang- und kurzfristigen Ziele und Herausforderungen zu klären.</span><span class="sxs-lookup"><span data-stu-id="22685-109">Start with Section 1 to clarify your goals, objectives, and challenges.</span></span> <span data-ttu-id="22685-110">Fahren Sie dann mit den Abschnitten 2-7 in der Reihenfolge fort, die Ihren Anforderungen am ehesten entspricht.</span><span class="sxs-lookup"><span data-stu-id="22685-110">Then move on to Sections 2 – 7 in the order that best meets your needs.</span></span> <span data-ttu-id="22685-111">Sie müssen diese Abschnitte nicht nacheinander, sondern können Sie auch parallel durcharbeiten.</span><span class="sxs-lookup"><span data-stu-id="22685-111">You don't need to work through these sections sequentially; you can complete them in parallel.</span></span>

-   [<span data-ttu-id="22685-112">Abschnitt 1: Bestimmen der Bereitstellungsziele, sonstigen Ziele und Herausforderungen</span><span class="sxs-lookup"><span data-stu-id="22685-112">Section 1: Determine deployment goals, objectives, and challenges</span></span>](planning-guide-deployment-goals.md)

-   [<span data-ttu-id="22685-113">Abschnitt 2: Bestimmen von Anwendungsszenarien</span><span class="sxs-lookup"><span data-stu-id="22685-113">Section 2: Identify use case scenarios</span></span>](planning-guide-scenarios.md)

-   [<span data-ttu-id="22685-114">Abschnitt 3: Bestimmen von Anwendungsfallanforderungen</span><span class="sxs-lookup"><span data-stu-id="22685-114">Section 3: Determine use case requirements</span></span>](planning-guide-requirements.md)

-   [<span data-ttu-id="22685-115">Abschnitt 4: Entwickeln eines Einführungsplans</span><span class="sxs-lookup"><span data-stu-id="22685-115">Section 4: Develop a rollout plan</span></span>](planning-guide-rollout-plan.md)

-   [<span data-ttu-id="22685-116">Abschnitt 5: Entwickeln eines Kommunikationsplans für die Einführung</span><span class="sxs-lookup"><span data-stu-id="22685-116">Section 5: Develop a rollout communication plan</span></span>](planning-guide-communication-plan.md)

-   [<span data-ttu-id="22685-117">Abschnitt 6: Entwickeln eines Unterstützungsplans</span><span class="sxs-lookup"><span data-stu-id="22685-117">Section 6: Develop a support plan</span></span>](planning-guide-support-plan.md)

-   [<span data-ttu-id="22685-118">Abschnitt 7: Erstellen eines Intune-Entwurfs</span><span class="sxs-lookup"><span data-stu-id="22685-118">Section 7: Create an Intune design</span></span>](planning-guide-design.md)

-   [<span data-ttu-id="22685-119">Abschnitt 8: Implementierung von Intune</span><span class="sxs-lookup"><span data-stu-id="22685-119">Section 8: Intune implementation</span></span>](planning-guide-onboarding.md)

-   [<span data-ttu-id="22685-120">Abschnitt 9: Testen und Überprüfen</span><span class="sxs-lookup"><span data-stu-id="22685-120">Section 9: Testing and validation</span></span>](planning-guide-test-validation.md)

<span data-ttu-id="22685-121">Dieses Handbuch enthält außerdem zusätzliche technische Informationen und Tabellenvorlagen zum Unterstützen des Planungs-, Entwurfs- und Implementierungsprozesses zur Bereitstellung von Intune.</span><span class="sxs-lookup"><span data-stu-id="22685-121">This guide also provides additional technical information and table templates that can be used to assist you with the Intune deployment planning, design, and implementation process.</span></span>

-   [<span data-ttu-id="22685-122">Zusätzliche Ressourcen: Links und Tabellenvorlagen</span><span class="sxs-lookup"><span data-stu-id="22685-122">Additional resources: Links and table templates</span></span>](planning-guide-resources.md)

## <a name="assumptions"></a><span data-ttu-id="22685-123">Annahmen</span><span class="sxs-lookup"><span data-stu-id="22685-123">Assumptions</span></span>

-   <span data-ttu-id="22685-124">Sie haben Intune bereits in einer PoC-Umgebung (Proof of Concept) evaluiert und entschieden, diese Lösung zur Verwaltung mobiler Geräte in Ihrer Organisation einzusetzen.</span><span class="sxs-lookup"><span data-stu-id="22685-124">You've already evaluated Intune in a proof of concept (PoC) environment, and have decided to use it as the mobile device management solution in your organization.</span></span>

-   <span data-ttu-id="22685-125">Sie sind bereits mit Intune und seinen Funktionen vertraut.</span><span class="sxs-lookup"><span data-stu-id="22685-125">You're already familiar with Intune and its features.</span></span>

## <a name="next-steps"></a><span data-ttu-id="22685-126">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="22685-126">Next steps</span></span>

<span data-ttu-id="22685-127">Beginnen wir mit dem ersten Abschnitt [Bestimmen der Bereitstellungsziele, sonstigen Ziele und Herausforderungen](planning-guide-deployment-goals.md).</span><span class="sxs-lookup"><span data-stu-id="22685-127">Let’s get started with the first section: [Determine deployment goals, objectives, and challenges](planning-guide-deployment-goals.md).</span></span>
