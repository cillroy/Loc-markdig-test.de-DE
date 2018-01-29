---
title: Bestimmen der Bereitstellungsziele, sonstigen Ziele und Herausforderungen
description: "Dieser Artikel hilft Ihnen beim Bestimmen von langfristigen und kurzfristigen Zielen sowie von Herausforderungen bei der Intune-Bereitstellung für eine reine Microsoft Intune-Cloudimplementierung."
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 10/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 24cf9d97-db39-4b95-a664-4aa2e33edb87
ms.reviewer: jeffbu, cgerth
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 93607152cfe007fb13e8695301debd87c9384394
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2018
---
# <a name="determine-deployment-goals-objectives-and-challenges"></a><span data-ttu-id="78d21-103">Bestimmen der Bereitstellungsziele, sonstigen Ziele und Herausforderungen</span><span class="sxs-lookup"><span data-stu-id="78d21-103">Determine deployment goals, objectives, and challenges</span></span>

<span data-ttu-id="78d21-104">Ein guter Bereitstellungsplan beginnt mit dem Ermitteln der langfristigen und kurzfristigen Ziele der Bereitstellung sowie von möglichen Herausforderungen für Ihre Organisation.</span><span class="sxs-lookup"><span data-stu-id="78d21-104">Having a good deployment plan begins with first identifying your organization’s deployment goals and objectives, along with potential challenges.</span></span> <span data-ttu-id="78d21-105">Betrachten wir die einzelnen Bereiche im Detail.</span><span class="sxs-lookup"><span data-stu-id="78d21-105">Let’s discuss each area in more detail.</span></span>

## <a name="deployment-goals"></a><span data-ttu-id="78d21-106">Langfristige Bereitstellungsziele</span><span class="sxs-lookup"><span data-stu-id="78d21-106">Deployment goals</span></span>

<span data-ttu-id="78d21-107">Bereitstellungsziele sind langfristig angelegt und sollen durch das Bereitstellen von Intune in Ihrer Organisation realisiert werden.</span><span class="sxs-lookup"><span data-stu-id="78d21-107">Deployment goals are the long-term achievements you intend to gain by deploying Intune in your organization.</span></span> <span data-ttu-id="78d21-108">Nachstehend finden Sie einige Beispiele solcher Ziele, jeweils mit Beschreibung und geschäftlichem Nutzen.</span><span class="sxs-lookup"><span data-stu-id="78d21-108">Listed below are some examples of such goals along with the description and business value for each.</span></span>

-   <span data-ttu-id="78d21-109">**Integration in Office 365 und Unterstützung der Verwendung von Office Mobile-Apps**</span><span class="sxs-lookup"><span data-stu-id="78d21-109">**Integrate with Office 365 and support the use of Office mobile apps**</span></span>

    -   <span data-ttu-id="78d21-110">**Beschreibung:** Bereitstellen einer engen Integration in Office 365 und Verwendung von Office Mobile-Apps mit App-Schutz.</span><span class="sxs-lookup"><span data-stu-id="78d21-110">**Description:** Provide tight integration with Office 365 and the use of Office mobile apps with app protection.</span></span>

    -   <span data-ttu-id="78d21-111">**Geschäftlicher Nutzen:** Sichere und verbesserte Benutzeroberfläche, da Benutzer Apps verwenden können, die sie kennen und bevorzugen.</span><span class="sxs-lookup"><span data-stu-id="78d21-111">**Business value:** Secure and improved user experience by allowing users to use apps they are familiar with and prefer.</span></span>

-   <span data-ttu-id="78d21-112">**Aktivieren des Zugriffs auf interne Unternehmensdienste auf mobilen Geräten**</span><span class="sxs-lookup"><span data-stu-id="78d21-112">**Enable access to internal corporate services on mobile devices**</span></span>

    -   <span data-ttu-id="78d21-113">**Beschreibung:** Mitarbeitern an jedem beliebigen Ort und mit dem jeweils geeigneten Gerät Produktivität ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="78d21-113">**Description:** Enable employees to be productive wherever they need to work from, and with whichever device is most appropriate for them.</span></span> <span data-ttu-id="78d21-114">Dieses Projekt sollte darauf ausgerichtet sein, mobile Produktivität und Zugriff auf Unternehmensdaten auf sichere Weise zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="78d21-114">This project should look to enable mobile productivity and access to corporate data in a safe manner.</span></span>

    -   <span data-ttu-id="78d21-115">**Geschäftlicher Nutzen:** Indem Mitarbeitern die Flexibilität eingeräumt wird, an jedem beliebigen Standort zu arbeiten, ist das Unternehmen konkurrenzfähiger und kann eine interessante Arbeitsumgebung bieten.</span><span class="sxs-lookup"><span data-stu-id="78d21-115">**Business value:** Enabling employees to be agile and work from where they need allows the business to be more competitive and to provide a more rewarding working environment.</span></span>

-   <span data-ttu-id="78d21-116">**Bereitstellen von Datenschutz auf mobilen Geräten**</span><span class="sxs-lookup"><span data-stu-id="78d21-116">**Provide data protection on mobile devices**</span></span>

    -   <span data-ttu-id="78d21-117">**Beschreibung:** Wenn Daten auf einem mobilen Gerät gespeichert sind, müssen sie vor böswilligem und unbeabsichtigtem Datenverlust oder vor Freigabe geschützt werden.</span><span class="sxs-lookup"><span data-stu-id="78d21-117">**Description:** When data is stored on a mobile device, it should be protected from malicious and accidental loss or sharing.</span></span>

    -   <span data-ttu-id="78d21-118">**Geschäftlicher Nutzen:** Datenschutz ist wichtig, um sicherzustellen, dass wir wettbewerbsfähig bleiben und unsere Kunden und deren Daten mit den größtmöglichen Sorgfalt behandeln.</span><span class="sxs-lookup"><span data-stu-id="78d21-118">**Business value:** Data protection is vital to ensure that we remain competitive, and that we treat our clients and their data with the utmost diligence.</span></span>

-   <span data-ttu-id="78d21-119">**Kostensenkung**</span><span class="sxs-lookup"><span data-stu-id="78d21-119">**Reduce costs**</span></span>

    -   <span data-ttu-id="78d21-120">**Beschreibung:** Nach Möglichkeit werden durch das Projekt die Kosten für Bereitstellung und Betrieb verringert.</span><span class="sxs-lookup"><span data-stu-id="78d21-120">**Description:** When possible, the project reduces deployment and operating costs.</span></span>

    -    <span data-ttu-id="78d21-121">**Geschäftlicher Nutzen:** Durch die effiziente Verwendung von Ressourcen kann das Unternehmen in andere Bereiche investieren, wirksamer konkurrieren und den Kunden einen besseren Service bieten.</span><span class="sxs-lookup"><span data-stu-id="78d21-121">**Business value:** The efficient use of resources enables the business to invest in other areas, compete more effectively, and provide better service to clients.</span></span>

## <a name="deployment-objectives"></a><span data-ttu-id="78d21-122">Kurzfristige Bereitstellungsziele</span><span class="sxs-lookup"><span data-stu-id="78d21-122">Deployment objectives</span></span>

<span data-ttu-id="78d21-123">Diese Ziele der Bereitstellung sind die Aktionen, mit denen Ihr Unternehmen seine langfristigen Ziele der Intune-Bereitstellungsziele umsetzen kann.</span><span class="sxs-lookup"><span data-stu-id="78d21-123">Deployment objectives are the actions your organization can take to reach its Intune deployment goals.</span></span> <span data-ttu-id="78d21-124">Im Folgenden sind einige Beispiele für kurzfristige Bereitstellungsziele aufgeführt. Zudem wird erläutert, wie sie jeweils zu erreichen sind.</span><span class="sxs-lookup"><span data-stu-id="78d21-124">Below are listed some examples of deployment objectives, and how each would be accomplished.</span></span>

-   <span data-ttu-id="78d21-125">**Verringern der Anzahl von Geräteverwaltungslösungen**</span><span class="sxs-lookup"><span data-stu-id="78d21-125">**Reduce the number of device management solutions**</span></span>

    -   <span data-ttu-id="78d21-126">**Umsetzung:** Konsolidieren Sie auf eine einzige Lösung zur Verwaltung mobiler Geräte, nämlich Microsoft Intune, für den Schutz von Unternehmensdaten von Apps und Geräten.</span><span class="sxs-lookup"><span data-stu-id="78d21-126">**Implementation:** Consolidate to a single mobile device management solution: Microsoft Intune for corporate data protection of apps and devices.</span></span>

-   <span data-ttu-id="78d21-127">**Bereitstellen eines sicheren Zugriffs auf Exchange Online und SharePoint Online**</span><span class="sxs-lookup"><span data-stu-id="78d21-127">**Provide secure access to Exchange and SharePoint Online**</span></span>

    -   <span data-ttu-id="78d21-128">**Umsetzung:** Implementieren Sie den bedingten Zugriff für Exchange Online und SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="78d21-128">**Implementation:** Apply conditional access for Exchange and SharePoint Online.</span></span>

-   <span data-ttu-id="78d21-129">**Verhindern, dass Unternehmensdaten gespeichert oder an unternehmensfremde Dienste auf dem mobilen Gerät weitergeleitet werden**</span><span class="sxs-lookup"><span data-stu-id="78d21-129">**Prevent corporate data from being stored or forwarded to non-corporate services on the mobile device**</span></span>

    -   <span data-ttu-id="78d21-130">**Umsetzung:** Implementieren Sie Intune-Richtlinien zum App-Schutz für Microsoft Office- und branchenspezifische Apps.</span><span class="sxs-lookup"><span data-stu-id="78d21-130">**Implementation:** Apply Intune app protection policies for Microsoft Office and line-of-business apps.</span></span>

-   <span data-ttu-id="78d21-131">**Bereitstellen der Funktion zum Entfernen von Unternehmensdaten vom Gerät**</span><span class="sxs-lookup"><span data-stu-id="78d21-131">**Provide capability to wipe corporate data from the device**</span></span>

    -   <span data-ttu-id="78d21-132">**Umsetzung:** Registrieren Sie Geräte bei Intune.</span><span class="sxs-lookup"><span data-stu-id="78d21-132">**Implementation:** Enroll devices into Intune.</span></span> <span data-ttu-id="78d21-133">Dies bietet Ihnen die Möglichkeit, bei Bedarf eine Remotezurücksetzung von Unternehmensdaten und -ressourcen vorzunehmen.</span><span class="sxs-lookup"><span data-stu-id="78d21-133">This gives you the capability to perform a remote wipe of corporate data and resources when appropriate.</span></span>

## <a name="deployment-challenges"></a><span data-ttu-id="78d21-134">Herausforderungen bei der Bereitstellung</span><span class="sxs-lookup"><span data-stu-id="78d21-134">Deployment challenges</span></span>

<span data-ttu-id="78d21-135">Herausforderungen bei der Bereitstellung sind Aspekte, die bei einer Organisation im Vordergrund stehen und sich negativ auf die Bereitstellung auswirken können.</span><span class="sxs-lookup"><span data-stu-id="78d21-135">Deployment challenges are issues that are top of mind for an organization and that may have a negative impact on deployment.</span></span> <span data-ttu-id="78d21-136">Mitunter stehen sie in Zusammenhang mit bei früheren Projekten aufgetretenen Problemen, die vermieden werden sollen, oder es handelt sich um neue Probleme bei den aktuellen Bereitstellungsbemühungen.</span><span class="sxs-lookup"><span data-stu-id="78d21-136">Sometimes they are related to past issues from previous projects that you would like to avoid or new issues related to the current deployment effort.</span></span> <span data-ttu-id="78d21-137">Nachstehend sind einige Beispiele für die Herausforderungen bei der Bereitstellung von Intune sowie mögliche Gegenmaßnahmen aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="78d21-137">Listed below are some examples of Intune deployment challenges along with potential mitigations.</span></span>

-   <span data-ttu-id="78d21-138">Die Bereitschaft des Supports und Endbenutzerfahrung werden im anfänglichen Projektumfang nicht berücksichtigt.</span><span class="sxs-lookup"><span data-stu-id="78d21-138">Support readiness and end-user experience are not included in an initial project scope.</span></span> <span data-ttu-id="78d21-139">Dies führt zu einer schwachen Akzeptanz seitens der Endbenutzer und Herausforderungen für Ihre Supportorganisation.</span><span class="sxs-lookup"><span data-stu-id="78d21-139">This leads to poor end-user adoption and challenges for your support organization.</span></span>

    -   <span data-ttu-id="78d21-140">**Lösung:** Integrieren Sie Schulungen für den Support.</span><span class="sxs-lookup"><span data-stu-id="78d21-140">**Mitigation:** Incorporate support training.</span></span> <span data-ttu-id="78d21-141">Überprüfen Sie die Endbenutzererfahrung anhand der Erfolgsmetriken in Ihrem Bereitstellungsplan.</span><span class="sxs-lookup"><span data-stu-id="78d21-141">Validate the end-user experience with success metrics in your deployment plan.</span></span>

-   <span data-ttu-id="78d21-142">Das Fehlen klar definierter Ziele und Erfolgsmetriken führt zu vagen Ergebnissen.</span><span class="sxs-lookup"><span data-stu-id="78d21-142">Lack of clearly defined goals and success metrics leads to intangible results.</span></span> <span data-ttu-id="78d21-143">Es kann auch bewirken, dass Ihre Organisation in den Reaktionsmodus wechselt, sobald Probleme auftreten.</span><span class="sxs-lookup"><span data-stu-id="78d21-143">It may also shift your organization into reactive mode when issues arise.</span></span>

    -   <span data-ttu-id="78d21-144">**Lösung:** Definieren Sie Ihre Ziele und Erfolgsmetriken frühzeitig in Ihrem Projektumfang, und verwenden Sie diese Datenpunkte zur Ausarbeitung der übrigen Rolloutphasen.</span><span class="sxs-lookup"><span data-stu-id="78d21-144">**Mitigation:** Define your goals and success metrics early in your project scope, and use these data points to flesh out your other rollout phases.</span></span> <span data-ttu-id="78d21-145">Stellen Sie sicher, dass Ihre Ziele spezifisch, messbar, erreichbar, realistisch und zeitgerecht sind.</span><span class="sxs-lookup"><span data-stu-id="78d21-145">Make sure goals are SMART (Specific, Measurable, Attainable, Realistic, and Timely).</span></span> <span data-ttu-id="78d21-146">Planen Sie in allen Phasen Vergleichsmessungen mit Ihren Zielen ein, um sicherzustellen, dass Ihr Rolloutprojekt auf Kurs bleibt.</span><span class="sxs-lookup"><span data-stu-id="78d21-146">Plan to measure against your goals at each phase and to ensure your rollout project stays on track.</span></span>

-   <span data-ttu-id="78d21-147">Sie vernachlässigen das Erstellen, Überprüfen und proaktive Vermitteln eines deutlichen Nutzenversprechens für Ihre Organisation.</span><span class="sxs-lookup"><span data-stu-id="78d21-147">You neglect to create, validate, and aggressively share a clear value proposition that resonates for your organization.</span></span> <span data-ttu-id="78d21-148">Dies führt häufig zu begrenzter Akzeptanz und einem Mangel an Rendite.</span><span class="sxs-lookup"><span data-stu-id="78d21-148">This often leads to limited adoption and a lack of return on investment (ROI).</span></span>

    -   <span data-ttu-id="78d21-149">**Lösung:** Auch wenn Sie sich gerne sofort in Ihr Projekt stürzen möchten, stellen Sie zuerst sicher, dass Sie Ihre langfristigen und kurzfristigen Ziele eindeutig definieren.</span><span class="sxs-lookup"><span data-stu-id="78d21-149">**Mitigation:** While you may be excited to jump into your project, ensure you have clearly-defined your goals and objectives.</span></span> <span data-ttu-id="78d21-150">Beziehen Sie diese in alle Sensibilisierungs- und Trainingsaktivitäten ein, um sicherzustellen, dass den Benutzern klar ist, warum das Unternehmen sich für Intune entschieden hat.</span><span class="sxs-lookup"><span data-stu-id="78d21-150">Include these in all awareness and training activities to help ensure users understand why your organization selected Intune.</span></span>

## <a name="next-steps"></a><span data-ttu-id="78d21-151">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="78d21-151">Next steps</span></span>

<span data-ttu-id="78d21-152">Sie haben Ihre langfristigen und kurzfristigen Ziele sowie die möglichen Herausforderungen Ihrer Bereitstellung identifiziert. Fahren Sie nun mit dem nächsten Abschnitt fort: [Identifizieren von Anwendungsszenarien](planning-guide-scenarios.md).</span><span class="sxs-lookup"><span data-stu-id="78d21-152">Now that you have identified your deployment goals, objectives, and potential challenges, let’s move to the next section: [Identify use case scenarios](planning-guide-scenarios.md).</span></span>
