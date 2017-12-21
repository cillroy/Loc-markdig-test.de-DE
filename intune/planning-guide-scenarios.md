---
title: "Bestimmen von Szenarien für Anwendungsfälle"
description: "Dieser Artikel hilft Ihnen, Szenarien für Intune-Anwendungsfälle und untergeordnete Anwendungsfälle für eine reine Cloudimplementierung von Microsoft Intune zu bestimmen."
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 10/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4b3c9af9-78da-44d2-8bd2-3f0f8885952d
ms.reviewer: jeffbu, cgerth
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 864f99f52e0c8b46307f1ec24d11da51d8f52662
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2017
---
# <a name="identify-mobile-device-management-use-case-scenarios"></a><span data-ttu-id="d51cc-103">Bestimmen von Szenarien für Anwendungsfälle für die Verwaltung von Mobilgeräten</span><span class="sxs-lookup"><span data-stu-id="d51cc-103">Identify mobile device management use-case scenarios</span></span>

<span data-ttu-id="d51cc-104">Das Bestimmen Ihrer Szenarien für Anwendungsfälle ist ein wichtiger Bestandteil des Planungsprozesses einer erfolgreichen Intune-Bereitstellung.</span><span class="sxs-lookup"><span data-stu-id="d51cc-104">Identifying your use-case scenarios is an important part of the planning process for a successful Intune deployment.</span></span> <span data-ttu-id="d51cc-105">Szenarien für Anwendungsfälle sind hilfreich, da Sie mit ihnen Ihre Benutzer in verwaltbare Gruppen unterteilen können, entweder nach Benutzertyp oder Rolle oder nach Besitzer des Gerät des Benutzers (z.B. das Unternehmen oder der Benutzer selbst).</span><span class="sxs-lookup"><span data-stu-id="d51cc-105">Use-case scenarios are helpful because they let you segment your users into manageable groups by user type or role, and the ownership of the user's device (for example, company or personal).</span></span>

<span data-ttu-id="d51cc-106">Betrachten wir einige Beispiele, die Sie Ihre Organisation beim Festlegen der Intune-Anwendungsfallszenarien sowie der Organisationsgruppen und der den einzelnen Anwendungsfällen zugeordneten mobilen Geräteplattformen unterstützen können.</span><span class="sxs-lookup"><span data-stu-id="d51cc-106">Let’s discuss a few examples to help your organization identify Intune use-case scenarios, as well as organizational groups, and mobile device platforms associated with each use case.</span></span>

## <a name="device-ownership"></a><span data-ttu-id="d51cc-107">Gerätebesitz</span><span class="sxs-lookup"><span data-stu-id="d51cc-107">Device ownership</span></span>
<span data-ttu-id="d51cc-108">Als Erstes können Sie die Intune-Bereitstellungsziele und sonstigen Ziele Ihrer Organisation zurate ziehen, um die Hauptanwendungsszenarien für Ihre Bereitstellung zu bestimmen.</span><span class="sxs-lookup"><span data-stu-id="d51cc-108">You can begin by referring to your organization's Intune deployment goals and objectives to help identity the main use-case scenarios for your deployment.</span></span> <span data-ttu-id="d51cc-109">Beantworten Sie im Rahmen Ihres Intune-Bereitstellungsplans die folgenden Fragen:</span><span class="sxs-lookup"><span data-stu-id="d51cc-109">Within the scope of your Intune deployment plan, answer the following questions:</span></span>

-   <span data-ttu-id="d51cc-110">Möchten Sie unternehmenseigene Geräte unterstützen?</span><span class="sxs-lookup"><span data-stu-id="d51cc-110">Are you planning to support corporate owned devices?</span></span>

-   <span data-ttu-id="d51cc-111">Möchten Sie persönliche Geräte (BYOD) unterstützen?</span><span class="sxs-lookup"><span data-stu-id="d51cc-111">Are you planning to support personally owned devices (BYOD)?</span></span>

<span data-ttu-id="d51cc-112">Dies sind keine Entweder/Oder-Optionen.</span><span class="sxs-lookup"><span data-stu-id="d51cc-112">These are not either/or options.</span></span> <span data-ttu-id="d51cc-113">Sie finden ggf. heraus, dass Sie beide Formen des Gerätebesitzes unterstützen müssen, um die Ziele Ihrer Organisation zu erreichen.</span><span class="sxs-lookup"><span data-stu-id="d51cc-113">You may find you need to support both forms of device ownership to meet your organizational goals.</span></span> <span data-ttu-id="d51cc-114">Die untergeordneten Anwendungsfälle helfen bei der Klärung, wo die verschiedenen Geräteverwaltungsrichtlinien gelten sollen.</span><span class="sxs-lookup"><span data-stu-id="d51cc-114">The sub-use-cases will help clarify where to apply the different device management policies.</span></span>

### <a name="user-type-or-device-role"></a><span data-ttu-id="d51cc-115">Benutzertyp oder Geräterolle</span><span class="sxs-lookup"><span data-stu-id="d51cc-115">User type or device role</span></span>

<span data-ttu-id="d51cc-116">Bestimmen Sie, ob es für jedes Anwendungsfallszenario untergeordnete Anwendungsfälle gibt.</span><span class="sxs-lookup"><span data-stu-id="d51cc-116">Determine if each use-case scenario also includes sub-use-cases.</span></span> <span data-ttu-id="d51cc-117">Zum Beispiel hat Ihre Organisation möglicherweise Anforderungen für die Unterstützung eines unternehmensweiten Anwendungsfallszenarios erkannt, das basierend auf Benutzertyp oder Geräterolle zusätzliche untergeordnete Anwendungsfälle aufweist:</span><span class="sxs-lookup"><span data-stu-id="d51cc-117">For example, your organization may have identified requirements to support a corporate use-case scenario that includes additional sub-use-cases based on user type or device role, such as:</span></span>

-   <span data-ttu-id="d51cc-118">Information-Worker</span><span class="sxs-lookup"><span data-stu-id="d51cc-118">Information worker</span></span>

-   <span data-ttu-id="d51cc-119">Management</span><span class="sxs-lookup"><span data-stu-id="d51cc-119">Executive</span></span>

-   <span data-ttu-id="d51cc-120">Kiosk</span><span class="sxs-lookup"><span data-stu-id="d51cc-120">Kiosk</span></span>

<span data-ttu-id="d51cc-121">Hier sind einige Beispiele von Szenarien für Anwendungsfälle und untergeordnete Anwendungsfälle:</span><span class="sxs-lookup"><span data-stu-id="d51cc-121">Here are a few examples of use-case and sub-use-case scenarios:</span></span>

| <span data-ttu-id="d51cc-122">**Anwendungsfälle**</span><span class="sxs-lookup"><span data-stu-id="d51cc-122">**Use cases**</span></span> | <span data-ttu-id="d51cc-123">**Untergeordnete Anwendungsfälle**</span><span class="sxs-lookup"><span data-stu-id="d51cc-123">**Sub-use cases**</span></span> |
|:---:|:---:|
| <span data-ttu-id="d51cc-124">Unternehmen</span><span class="sxs-lookup"><span data-stu-id="d51cc-124">Corporate</span></span> | <span data-ttu-id="d51cc-125">Information-Worker</span><span class="sxs-lookup"><span data-stu-id="d51cc-125">Information worker</span></span> |              
| <span data-ttu-id="d51cc-126">Unternehmen</span><span class="sxs-lookup"><span data-stu-id="d51cc-126">Corporate</span></span> | <span data-ttu-id="d51cc-127">Führungskräfte</span><span class="sxs-lookup"><span data-stu-id="d51cc-127">Executives</span></span> |           
| <span data-ttu-id="d51cc-128">Unternehmen</span><span class="sxs-lookup"><span data-stu-id="d51cc-128">Corporate</span></span> | <span data-ttu-id="d51cc-129">Kiosk</span><span class="sxs-lookup"><span data-stu-id="d51cc-129">Kiosk</span></span> |
| <span data-ttu-id="d51cc-130">BYOD</span><span class="sxs-lookup"><span data-stu-id="d51cc-130">BYOD</span></span> | <span data-ttu-id="d51cc-131">Information-Worker</span><span class="sxs-lookup"><span data-stu-id="d51cc-131">Information worker</span></span> |           
| <span data-ttu-id="d51cc-132">BYOD</span><span class="sxs-lookup"><span data-stu-id="d51cc-132">BYOD</span></span> | <span data-ttu-id="d51cc-133">Führungskräfte</span><span class="sxs-lookup"><span data-stu-id="d51cc-133">Executives</span></span> |

<span data-ttu-id="d51cc-134">Sie können [eine Vorlage der obigen Tabelle herunterladen](https://gallery.technet.microsoft.com/Intune-deployment-planning-fae156c2?redir=0), um die Szenarien für Anwendungsfälle und untergeordnete Anwendungsfälle Ihrer Organisation einzutragen.</span><span class="sxs-lookup"><span data-stu-id="d51cc-134">You can [download a template of the above table](https://gallery.technet.microsoft.com/Intune-deployment-planning-fae156c2?redir=0) to enter your organization’s use-case and sub-use-case scenarios.</span></span>

## <a name="organizational-groups-for-your-scenarios"></a><span data-ttu-id="d51cc-135">Organisationsgruppen für Ihre Szenarien</span><span class="sxs-lookup"><span data-stu-id="d51cc-135">Organizational groups for your scenarios</span></span>

<span data-ttu-id="d51cc-136">Jetzt müssen Sie die Organisationsgruppen festlegen, die den einzelnen Szenarien für Anwendungsfälle und untergeordnete Anwendungsfälle zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="d51cc-136">Now you need to identify the organizational groups that are associated with each use-case and sub-use-case scenario.</span></span> <span data-ttu-id="d51cc-137">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="d51cc-137">For example:</span></span>

| <span data-ttu-id="d51cc-138">**Anwendungsfälle**</span><span class="sxs-lookup"><span data-stu-id="d51cc-138">**Use cases**</span></span> | <span data-ttu-id="d51cc-139">**Untergeordnete Anwendungsfälle**</span><span class="sxs-lookup"><span data-stu-id="d51cc-139">**Sub-use cases**</span></span> | <span data-ttu-id="d51cc-140">**Organisationsgruppen**</span><span class="sxs-lookup"><span data-stu-id="d51cc-140">**Organizational groups**</span></span> |
|:---:|:---:|:---:|
| <span data-ttu-id="d51cc-141">Unternehmen</span><span class="sxs-lookup"><span data-stu-id="d51cc-141">Corporate</span></span> | <span data-ttu-id="d51cc-142">Information-Worker</span><span class="sxs-lookup"><span data-stu-id="d51cc-142">Information worker</span></span> | <span data-ttu-id="d51cc-143">Personalabteilung, Finanzabteilung</span><span class="sxs-lookup"><span data-stu-id="d51cc-143">HR, Finance</span></span> |               
| <span data-ttu-id="d51cc-144">Unternehmen</span><span class="sxs-lookup"><span data-stu-id="d51cc-144">Corporate</span></span> | <span data-ttu-id="d51cc-145">Management</span><span class="sxs-lookup"><span data-stu-id="d51cc-145">Executive</span></span> | <span data-ttu-id="d51cc-146">Personalabteilung, Finanzabteilung</span><span class="sxs-lookup"><span data-stu-id="d51cc-146">HR, Finance</span></span> |            
| <span data-ttu-id="d51cc-147">Unternehmen</span><span class="sxs-lookup"><span data-stu-id="d51cc-147">Corporate</span></span> | <span data-ttu-id="d51cc-148">Kiosk</span><span class="sxs-lookup"><span data-stu-id="d51cc-148">Kiosk</span></span> | <span data-ttu-id="d51cc-149">Einzelhandel</span><span class="sxs-lookup"><span data-stu-id="d51cc-149">Retail</span></span> |
| <span data-ttu-id="d51cc-150">BYOD</span><span class="sxs-lookup"><span data-stu-id="d51cc-150">BYOD</span></span> | <span data-ttu-id="d51cc-151">Information-Worker</span><span class="sxs-lookup"><span data-stu-id="d51cc-151">Information worker</span></span> | <span data-ttu-id="d51cc-152">Marketing, Vertrieb</span><span class="sxs-lookup"><span data-stu-id="d51cc-152">Marketing, Sales</span></span> |            
| <span data-ttu-id="d51cc-153">BYOD</span><span class="sxs-lookup"><span data-stu-id="d51cc-153">BYOD</span></span> | <span data-ttu-id="d51cc-154">Management</span><span class="sxs-lookup"><span data-stu-id="d51cc-154">Executive</span></span> | <span data-ttu-id="d51cc-155">Marketing, Vertrieb</span><span class="sxs-lookup"><span data-stu-id="d51cc-155">Marketing, Sales</span></span> |


## <a name="mobile-device-platforms-for-your-scenarios"></a><span data-ttu-id="d51cc-156">Plattformen für mobile Geräte für Ihre Szenarien</span><span class="sxs-lookup"><span data-stu-id="d51cc-156">Mobile device platforms for your scenarios</span></span>

<span data-ttu-id="d51cc-157">Im nächsten Schritt bestimmen Sie die Plattformen für mobile Geräte , die den einzelnen Anwendungsfallszenarien zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="d51cc-157">The next step is to identify the mobile device platforms associated with each use-case scenario.</span></span> <span data-ttu-id="d51cc-158">Es gibt möglicherweise mehr als eine.</span><span class="sxs-lookup"><span data-stu-id="d51cc-158">There may be more than one.</span></span>

<span data-ttu-id="d51cc-159">Angenommen, im Anwendungsfallszenario Ihres Unternehmens werden die Geräteplattformen iOS und Android Samsung KNOX unterstützt.</span><span class="sxs-lookup"><span data-stu-id="d51cc-159">For example, your corporate use-case scenario may support iOS and Android Samsung KNOX device platforms.</span></span> <span data-ttu-id="d51cc-160">Ihre BYOD-Richtlinie sieht ggf. Unterstützung für weitere Plattformen für mobile Geräte wie Android (nicht Samsung KNOX) und Windows 10 Mobile vor.</span><span class="sxs-lookup"><span data-stu-id="d51cc-160">Your BYOD policy may include support for additional mobile device platforms like Android (non-Samsung KNOX) and Windows 10 Mobile.</span></span> <span data-ttu-id="d51cc-161">Ausgehend von den genannten Beispielen haben wir jedem Anwendungsfallszenario Plattformen für mobile Geräte zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="d51cc-161">Building on the preceding examples, we've associated mobile device platforms with each use-case scenario.</span></span>

| <span data-ttu-id="d51cc-162">**Anwendungsfälle**</span><span class="sxs-lookup"><span data-stu-id="d51cc-162">**Use cases**</span></span> | <span data-ttu-id="d51cc-163">**Untergeordnete Anwendungsfälle**</span><span class="sxs-lookup"><span data-stu-id="d51cc-163">**Sub-use cases**</span></span> | <span data-ttu-id="d51cc-164">**Gruppen**</span><span class="sxs-lookup"><span data-stu-id="d51cc-164">**Groups**</span></span> | <span data-ttu-id="d51cc-165">**Geräteplattformen**</span><span class="sxs-lookup"><span data-stu-id="d51cc-165">**Device platforms**</span></span> |   
|:---:|:---:|:---:|:---:|
| <span data-ttu-id="d51cc-166">Unternehmen</span><span class="sxs-lookup"><span data-stu-id="d51cc-166">Corporate</span></span> | <span data-ttu-id="d51cc-167">Information-Worker</span><span class="sxs-lookup"><span data-stu-id="d51cc-167">Information worker</span></span> | <span data-ttu-id="d51cc-168">Personalabteilung, Finanzabteilung</span><span class="sxs-lookup"><span data-stu-id="d51cc-168">HR, Finance</span></span> | <span data-ttu-id="d51cc-169">iOS</span><span class="sxs-lookup"><span data-stu-id="d51cc-169">iOS</span></span> |                                                           
| <span data-ttu-id="d51cc-170">Unternehmen</span><span class="sxs-lookup"><span data-stu-id="d51cc-170">Corporate</span></span> | <span data-ttu-id="d51cc-171">Führungskräfte</span><span class="sxs-lookup"><span data-stu-id="d51cc-171">Executives</span></span> | <span data-ttu-id="d51cc-172">Personalabteilung, Finanzabteilung</span><span class="sxs-lookup"><span data-stu-id="d51cc-172">HR, Finance</span></span> | <span data-ttu-id="d51cc-173">iOS</span><span class="sxs-lookup"><span data-stu-id="d51cc-173">iOS</span></span> |                                                           
| <span data-ttu-id="d51cc-174">Unternehmen</span><span class="sxs-lookup"><span data-stu-id="d51cc-174">Corporate</span></span> | <span data-ttu-id="d51cc-175">Kiosk</span><span class="sxs-lookup"><span data-stu-id="d51cc-175">Kiosk</span></span> | <span data-ttu-id="d51cc-176">Einzelhandel</span><span class="sxs-lookup"><span data-stu-id="d51cc-176">Retail</span></span> | <span data-ttu-id="d51cc-177">Android</span><span class="sxs-lookup"><span data-stu-id="d51cc-177">Android</span></span> |
| <span data-ttu-id="d51cc-178">BYOD</span><span class="sxs-lookup"><span data-stu-id="d51cc-178">BYOD</span></span> | <span data-ttu-id="d51cc-179">Information-Worker</span><span class="sxs-lookup"><span data-stu-id="d51cc-179">Information worker</span></span> | <span data-ttu-id="d51cc-180">Marketing, Vertrieb</span><span class="sxs-lookup"><span data-stu-id="d51cc-180">Marketing, Sales</span></span> | <span data-ttu-id="d51cc-181">iOS</span><span class="sxs-lookup"><span data-stu-id="d51cc-181">iOS</span></span> |                                                           
| <span data-ttu-id="d51cc-182">BYOD</span><span class="sxs-lookup"><span data-stu-id="d51cc-182">BYOD</span></span> | <span data-ttu-id="d51cc-183">Führungskräfte</span><span class="sxs-lookup"><span data-stu-id="d51cc-183">Executives</span></span> | <span data-ttu-id="d51cc-184">Marketing, Vertrieb</span><span class="sxs-lookup"><span data-stu-id="d51cc-184">Marketing, Sales</span></span> | <span data-ttu-id="d51cc-185">iOS</span><span class="sxs-lookup"><span data-stu-id="d51cc-185">iOS</span></span> |

## <a name="next-steps"></a><span data-ttu-id="d51cc-186">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="d51cc-186">Next steps</span></span>

<span data-ttu-id="d51cc-187">Der nächste Abschnitt enthält Hinweise für das [Identifizieren der Intune-Anforderungen für die einzelnen Anwendungsszenarien](planning-guide-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d51cc-187">The next section provides guidance on [how to identify the Intune requirements for each use case scenario](planning-guide-requirements.md).</span></span>
