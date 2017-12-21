---
title: "Verstehen Sie Ihre Geräte mithilfe des Inventars"
description: "Verwenden Sie Intune zum Anzeigen von Informationen zur Hardware der Geräte, die Sie verwalten."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 09/05/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 312911fe-b963-4949-9911-ae425e0590b2
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: ccb5c17eeb3e965c8ac268dcfae18febd620b0c0
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2017
---
# <a name="understand-your-devices-with-inventory-in-microsoft-intune"></a><span data-ttu-id="32e08-103">Verstehen Sie Ihre Geräte mithilfe des Inventars in Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="32e08-103">Understand your devices with inventory in Microsoft Intune</span></span>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="32e08-104">Mit Microsoft Intune können Sie das Inventar an registrierten Geräten und Windows-PCs anzeigen, auf denen die Intune-Clientsoftware ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="32e08-104">Microsoft Intune lets you view the inventory of enrolled devices and Windows PCs that run the Intune client software.</span></span>
<span data-ttu-id="32e08-105">Intune sammelt normalerweise alle 7 Tage den Bestand von verwalteten Geräten.</span><span class="sxs-lookup"><span data-stu-id="32e08-105">Intune typically collects inventory from managed devices every 7 days.</span></span> <span data-ttu-id="32e08-106">Aus diesem Grund entsteht möglicherweise eine Verzögerung, bevor Berichte die Ergebnisse von kürzlich durchgeführten Änderungen an Geräten anzeigen, z.B. eine Änderung am Gerätenamen oder am freien Speicherplatz.</span><span class="sxs-lookup"><span data-stu-id="32e08-106">Because of this, there might be a delay before reports show the results of any recent changes to devices, for example, a change to the device name, or free storage space.</span></span>

## <a name="whats-collected-from-enrolled-devices"></a><span data-ttu-id="32e08-107">Welche Daten registrierter Geräte werden gesammelt?</span><span class="sxs-lookup"><span data-stu-id="32e08-107">What's collected from enrolled devices?</span></span>
<span data-ttu-id="32e08-108">Um das von den mobilen Geräten gesammelte Inventar anzuzeigen, führen Sie die [Inventurberichte für mobile Geräte](understand-microsoft-intune-operations-by-using-reports.md) aus.</span><span class="sxs-lookup"><span data-stu-id="32e08-108">To view the inventory that's collected by mobile devices, run the [Mobile Device Inventory Reports](understand-microsoft-intune-operations-by-using-reports.md).</span></span> <span data-ttu-id="32e08-109">Intune sammelt das folgende Inventar von den mobilen Geräten:</span><span class="sxs-lookup"><span data-stu-id="32e08-109">Intune collects the following inventory from enrolled devices:</span></span>

|<span data-ttu-id="32e08-110">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="32e08-110">Property</span></span>|<span data-ttu-id="32e08-111">Gesammelt von</span><span class="sxs-lookup"><span data-stu-id="32e08-111">Collected by</span></span>|
|------------|-----------------------|
|<span data-ttu-id="32e08-112">**Name**</span><span class="sxs-lookup"><span data-stu-id="32e08-112">**Name**</span></span>|<span data-ttu-id="32e08-113">Alle Geräte</span><span class="sxs-lookup"><span data-stu-id="32e08-113">All devices</span></span>|
|<span data-ttu-id="32e08-114">**Betriebssystem**</span><span class="sxs-lookup"><span data-stu-id="32e08-114">**Operating System**</span></span>|<span data-ttu-id="32e08-115">Alle Geräte</span><span class="sxs-lookup"><span data-stu-id="32e08-115">All devices</span></span>|
|<span data-ttu-id="32e08-116">**Hersteller**</span><span class="sxs-lookup"><span data-stu-id="32e08-116">**Manufacturer**</span></span>|<span data-ttu-id="32e08-117">Alle Geräte</span><span class="sxs-lookup"><span data-stu-id="32e08-117">All devices</span></span>|
|<span data-ttu-id="32e08-118">**Modell**</span><span class="sxs-lookup"><span data-stu-id="32e08-118">**Model**</span></span>|<span data-ttu-id="32e08-119">Alle Geräte</span><span class="sxs-lookup"><span data-stu-id="32e08-119">All devices</span></span>|
|<span data-ttu-id="32e08-120">**Verwaltungskanal**</span><span class="sxs-lookup"><span data-stu-id="32e08-120">**Management Channel**</span></span>|<span data-ttu-id="32e08-121">Alle Geräte</span><span class="sxs-lookup"><span data-stu-id="32e08-121">All devices</span></span>|
|<span data-ttu-id="32e08-122">**Bei AAD registriert**</span><span class="sxs-lookup"><span data-stu-id="32e08-122">**AAD Registered**</span></span>|<span data-ttu-id="32e08-123">Alle Geräte mit Ausnahme von Mac OS X</span><span class="sxs-lookup"><span data-stu-id="32e08-123">All devices except Mac OS X</span></span>|
|<span data-ttu-id="32e08-124">**Kompatibel**</span><span class="sxs-lookup"><span data-stu-id="32e08-124">**Compliant**</span></span>|<span data-ttu-id="32e08-125">Alle Geräte</span><span class="sxs-lookup"><span data-stu-id="32e08-125">All devices</span></span>|
|<span data-ttu-id="32e08-126">**EAS-aktiviert**</span><span class="sxs-lookup"><span data-stu-id="32e08-126">**EAS Activated**</span></span>|<span data-ttu-id="32e08-127">Alle Geräte mit Ausnahme von Mac OS X</span><span class="sxs-lookup"><span data-stu-id="32e08-127">All devices except Mac OS X</span></span>|
|<span data-ttu-id="32e08-128">**EAS-Aktivierungs-ID**</span><span class="sxs-lookup"><span data-stu-id="32e08-128">**EAS Activation ID**</span></span>|<span data-ttu-id="32e08-129">Alle Geräte mit Ausnahme von Mac OS X</span><span class="sxs-lookup"><span data-stu-id="32e08-129">All devices except Mac OS X</span></span>|
|<span data-ttu-id="32e08-130">**EAS-Aktivierungszeitpunkt**</span><span class="sxs-lookup"><span data-stu-id="32e08-130">**EAS Activation Time**</span></span>|<span data-ttu-id="32e08-131">Alle Geräte mit Ausnahme von Mac OS X</span><span class="sxs-lookup"><span data-stu-id="32e08-131">All devices except Mac OS X</span></span>|
|<span data-ttu-id="32e08-132">**Verwaltungsstatus**</span><span class="sxs-lookup"><span data-stu-id="32e08-132">**Management State**</span></span>|<span data-ttu-id="32e08-133">Alle Geräte</span><span class="sxs-lookup"><span data-stu-id="32e08-133">All devices</span></span>|
|<span data-ttu-id="32e08-134">**E-Mail-Adresse**</span><span class="sxs-lookup"><span data-stu-id="32e08-134">**Email Address**</span></span>|<span data-ttu-id="32e08-135">Alle Geräte</span><span class="sxs-lookup"><span data-stu-id="32e08-135">All devices</span></span>|
|<span data-ttu-id="32e08-136">**Exchange ActiveSync-ID**</span><span class="sxs-lookup"><span data-stu-id="32e08-136">**Exchange ActiveSync ID**</span></span>|<span data-ttu-id="32e08-137">Alle Geräte</span><span class="sxs-lookup"><span data-stu-id="32e08-137">All devices</span></span>|
|<span data-ttu-id="32e08-138">**Jailbreak oder Rooting**</span><span class="sxs-lookup"><span data-stu-id="32e08-138">**Jailbroken or Rooted**</span></span>|<span data-ttu-id="32e08-139">Nur iOS- und Android-Geräte</span><span class="sxs-lookup"><span data-stu-id="32e08-139">iOS and Android devices only</span></span>|
|<span data-ttu-id="32e08-140">**Eindeutige Geräte-ID**</span><span class="sxs-lookup"><span data-stu-id="32e08-140">**Unique Device ID**</span></span>|<span data-ttu-id="32e08-141">Alle Geräte mit Ausnahme von Exchange ActiveSync</span><span class="sxs-lookup"><span data-stu-id="32e08-141">All devices except Exchange ActiveSync</span></span>|
|<span data-ttu-id="32e08-142">**Seriennummer**</span><span class="sxs-lookup"><span data-stu-id="32e08-142">**Serial number**</span></span>|<span data-ttu-id="32e08-143">iOS-, Mac OS X-, Android-, Windows 8.1- und Windows 10-Desktopgeräte</span><span class="sxs-lookup"><span data-stu-id="32e08-143">iOS, Mac OS X, Android, Windows 8.1, and Windows 10 desktop devices</span></span>|
|<span data-ttu-id="32e08-144">**Gesamtmenge des Speicherplatzes**</span><span class="sxs-lookup"><span data-stu-id="32e08-144">**Total Storage Space**</span></span>|<span data-ttu-id="32e08-145">iOS-, Mac OS X-, Android-, Windows 8.1- und Windows 10-Desktopgeräte und -mobile Geräte</span><span class="sxs-lookup"><span data-stu-id="32e08-145">iOS, Mac OS X, Windows 8.1, and Windows 10 desktop and Mobile devices</span></span>|
|<span data-ttu-id="32e08-146">**Freier Speicherplatz**</span><span class="sxs-lookup"><span data-stu-id="32e08-146">**Free Storage Space**</span></span>|<span data-ttu-id="32e08-147">iOS-, Mac OS X-, Windows 8.1- und Windows 10-Desktopgeräte</span><span class="sxs-lookup"><span data-stu-id="32e08-147">iOS, Mac OS X, Windows 8.1, and Windows 10 desktop devices</span></span>|
|<span data-ttu-id="32e08-148">**Telefonnummer**</span><span class="sxs-lookup"><span data-stu-id="32e08-148">**Phone Number**</span></span><br><span data-ttu-id="32e08-149">Telefone, die als geschäftlich eingestuft sind, werden jetzt mit der vollständigen Telefonnummer identifiziert, wenn Sie beispielsweise einen Inventurbericht für mobile Geräte ausführen.</span><span class="sxs-lookup"><span data-stu-id="32e08-149">Phones that are categorized as corporate are identified with their full phone number (for example, when you run a mobile device inventory report).</span></span> <span data-ttu-id="32e08-150">BYOD-Telefonnummern werden mit &#42; maskiert, und nur die letzten vier Ziffern werden angezeigt.</span><span class="sxs-lookup"><span data-stu-id="32e08-150">BYOD phone numbers are masked with &#42;, and only the last four digits are displayed.</span></span>|<span data-ttu-id="32e08-151">iOS-, Android- und Windows Phone-Geräte</span><span class="sxs-lookup"><span data-stu-id="32e08-151">iOS, Android, and Windows Phone devices</span></span>|
|<span data-ttu-id="32e08-152">**IMEI**</span><span class="sxs-lookup"><span data-stu-id="32e08-152">**IMEI**</span></span>|<span data-ttu-id="32e08-153">Exchange ActiveSync-, iOS-, Android- und Windows Phone-Geräte</span><span class="sxs-lookup"><span data-stu-id="32e08-153">Exchange ActiveSync, iOS, Android, and Windows Phone devices</span></span>|
|<span data-ttu-id="32e08-154">**MEID**</span><span class="sxs-lookup"><span data-stu-id="32e08-154">**MEID**</span></span><br><span data-ttu-id="32e08-155">Mobile Equipment Identifier</span><span class="sxs-lookup"><span data-stu-id="32e08-155">Mobile Equipment Identifier</span></span>|<span data-ttu-id="32e08-156">Nur iOS-Geräte</span><span class="sxs-lookup"><span data-stu-id="32e08-156">iOS devices only</span></span>|
|<span data-ttu-id="32e08-157">**WiFi-MAC**</span><span class="sxs-lookup"><span data-stu-id="32e08-157">**Wi-Fi MAC**</span></span>|<span data-ttu-id="32e08-158">Alle Geräte mit Ausnahme von Exchange ActiveSync</span><span class="sxs-lookup"><span data-stu-id="32e08-158">All devices except Exchange ActiveSync</span></span>|
|<span data-ttu-id="32e08-159">**Netzbetreiber des Abonnenten**</span><span class="sxs-lookup"><span data-stu-id="32e08-159">**Subscriber Carrier**</span></span>|<span data-ttu-id="32e08-160">Nur iOS- und Android-Geräte</span><span class="sxs-lookup"><span data-stu-id="32e08-160">iOS and Android devices only</span></span>|
|<span data-ttu-id="32e08-161">**Mobilfunktechnologie**</span><span class="sxs-lookup"><span data-stu-id="32e08-161">**Cellular Technology**</span></span>|<span data-ttu-id="32e08-162">Nur iOS- und Android-Geräte</span><span class="sxs-lookup"><span data-stu-id="32e08-162">iOS and Android devices only</span></span>|
|<span data-ttu-id="32e08-163">**Überwacht**</span><span class="sxs-lookup"><span data-stu-id="32e08-163">**Supervised**</span></span>|<span data-ttu-id="32e08-164">Nur iOS-Geräte</span><span class="sxs-lookup"><span data-stu-id="32e08-164">iOS devices only</span></span>|
|<span data-ttu-id="32e08-165">**Aktivierungssperrenstatus**</span><span class="sxs-lookup"><span data-stu-id="32e08-165">**Activation Lock State**</span></span>|<span data-ttu-id="32e08-166">Nur iOS-Geräte</span><span class="sxs-lookup"><span data-stu-id="32e08-166">iOS devices only</span></span>|
|<span data-ttu-id="32e08-167">**Registrierungsdatum**</span><span class="sxs-lookup"><span data-stu-id="32e08-167">**Enrolled Date**</span></span>|<span data-ttu-id="32e08-168">Alle Geräte</span><span class="sxs-lookup"><span data-stu-id="32e08-168">All devices</span></span>|
|<span data-ttu-id="32e08-169">**Zuletzt aktualisiert**</span><span class="sxs-lookup"><span data-stu-id="32e08-169">**Last Updated**</span></span>|<span data-ttu-id="32e08-170">Alle Geräte</span><span class="sxs-lookup"><span data-stu-id="32e08-170">All devices</span></span>|
|<span data-ttu-id="32e08-171">**Ethernet MAC**</span><span class="sxs-lookup"><span data-stu-id="32e08-171">**Ethernet MAC**</span></span>|<span data-ttu-id="32e08-172">Nur Mac OS X-Geräte</span><span class="sxs-lookup"><span data-stu-id="32e08-172">Mac OS X devices only</span></span>|
|<span data-ttu-id="32e08-173">**Aktivierungssperre aktiviert**</span><span class="sxs-lookup"><span data-stu-id="32e08-173">**Activation Lock Enabled**</span></span>|<span data-ttu-id="32e08-174">Nur iOS-Geräte</span><span class="sxs-lookup"><span data-stu-id="32e08-174">iOS devices only</span></span>|
|<span data-ttu-id="32e08-175">**Verschlüsselung aktiviert**</span><span class="sxs-lookup"><span data-stu-id="32e08-175">**Encryption Enabled**</span></span>|<span data-ttu-id="32e08-176">Alle Geräte</span><span class="sxs-lookup"><span data-stu-id="32e08-176">All devices</span></span>|

>[!NOTE]
><span data-ttu-id="32e08-177">Je nachdem, welchen Netzbetreiber Sie mit dem Gerät verwenden, werden einige der oben aufgeführten Elemente vielleicht nicht erfasst.</span><span class="sxs-lookup"><span data-stu-id="32e08-177">Some of the above items might not be collected depending on the carrier you use with the device.</span></span>

## <a name="whats-collected-from-windows-pcs"></a><span data-ttu-id="32e08-178">Was wird von Windows-PCs gesammelt?</span><span class="sxs-lookup"><span data-stu-id="32e08-178">What's collected from Windows PCs?</span></span>
> [!IMPORTANT]
> <span data-ttu-id="32e08-179">Dieser Abschnitt gilt nur für Windows-PCs, auf denen die Intune-Windows-PC-Clientsoftware ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="32e08-179">This section applies only to Windows PCs that run the Intune Windows PC client software.</span></span>

<span data-ttu-id="32e08-180">Um das von den Windows-PCs gesammelte Inventar anzuzeigen, führen Sie die [Computerinventurberichte](understand-microsoft-intune-operations-by-using-reports.md) aus.</span><span class="sxs-lookup"><span data-stu-id="32e08-180">To view the inventory that's collected by Windows PCs, run the [Computer Inventory Reports](understand-microsoft-intune-operations-by-using-reports.md).</span></span> <span data-ttu-id="32e08-181">Intune sammelt das folgende Inventar von den Windows-PCs:</span><span class="sxs-lookup"><span data-stu-id="32e08-181">Intune collects the following inventory from Windows PCs:</span></span>

-   <span data-ttu-id="32e08-182">**Name**</span><span class="sxs-lookup"><span data-stu-id="32e08-182">**Name**</span></span>

-   <span data-ttu-id="32e08-183">**Chassistyp**</span><span class="sxs-lookup"><span data-stu-id="32e08-183">**Chassis Type**</span></span>

-   <span data-ttu-id="32e08-184">**Hersteller**</span><span class="sxs-lookup"><span data-stu-id="32e08-184">**Manufacturer**</span></span>

-   <span data-ttu-id="32e08-185">**Modell**</span><span class="sxs-lookup"><span data-stu-id="32e08-185">**Model**</span></span>

-   <span data-ttu-id="32e08-186">**Betriebssystem**</span><span class="sxs-lookup"><span data-stu-id="32e08-186">**Operating System**</span></span>

-   <span data-ttu-id="32e08-187">**TPM-Version**</span><span class="sxs-lookup"><span data-stu-id="32e08-187">**TPM Version**</span></span>

-   <span data-ttu-id="32e08-188">**Gesamter Speicherplatz**</span><span class="sxs-lookup"><span data-stu-id="32e08-188">**Total Disk Space**</span></span>

-   <span data-ttu-id="32e08-189">**Verwendeter Speicherplatz**</span><span class="sxs-lookup"><span data-stu-id="32e08-189">**Used Disk Space**</span></span>

-   <span data-ttu-id="32e08-190">**Freier Speicherplatz**</span><span class="sxs-lookup"><span data-stu-id="32e08-190">**Free Disk Space**</span></span>

-   <span data-ttu-id="32e08-191">**Name des Betriebssystem-Datenträgers**</span><span class="sxs-lookup"><span data-stu-id="32e08-191">**OS Disk Name**</span></span>

-   <span data-ttu-id="32e08-192">**Speicherplatz des Betriebssystem-Datenträgers**</span><span class="sxs-lookup"><span data-stu-id="32e08-192">**OS Disk Space**</span></span>

-   <span data-ttu-id="32e08-193">**Freier Speicherplatz des Betriebssystem-Datenträgers**</span><span class="sxs-lookup"><span data-stu-id="32e08-193">**OS Disk Free Space**</span></span>

-   <span data-ttu-id="32e08-194">**Physischer Speicher**</span><span class="sxs-lookup"><span data-stu-id="32e08-194">**Physical Memory**</span></span>

-   <span data-ttu-id="32e08-195">**Name des Prozessors**</span><span class="sxs-lookup"><span data-stu-id="32e08-195">**Processor Name**</span></span>

-   <span data-ttu-id="32e08-196">**Prozessorarchitektur**</span><span class="sxs-lookup"><span data-stu-id="32e08-196">**Processor Architecture**</span></span>

-   <span data-ttu-id="32e08-197">**CPU-Geschwindigkeit**</span><span class="sxs-lookup"><span data-stu-id="32e08-197">**CPU Speed**</span></span>

-   <span data-ttu-id="32e08-198">**IP-Adresse**</span><span class="sxs-lookup"><span data-stu-id="32e08-198">**IP Address**</span></span>

-   <span data-ttu-id="32e08-199">**Seriennummer**</span><span class="sxs-lookup"><span data-stu-id="32e08-199">**Serial number**</span></span>

-   <span data-ttu-id="32e08-200">**Letzter Benutzer, der sich angemeldet hat**</span><span class="sxs-lookup"><span data-stu-id="32e08-200">**Last User to Log On**</span></span>

-   <span data-ttu-id="32e08-201">**Zugewiesener Benutzer**</span><span class="sxs-lookup"><span data-stu-id="32e08-201">**Assigned User**</span></span>

-   <span data-ttu-id="32e08-202">**Zuletzt aktualisiert**</span><span class="sxs-lookup"><span data-stu-id="32e08-202">**Last Updated**</span></span>

<!-- this section below belongs in the planning journey
### See Also
[Monitoring and reports with Microsoft Intune](monitoring-and-reports-with-microsoft-intune.md)
-->
