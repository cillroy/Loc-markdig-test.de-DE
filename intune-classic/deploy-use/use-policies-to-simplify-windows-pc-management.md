---
title: Verwenden von Richtlinien zum Vereinfachen der Verwaltung von Windows-PCs
description: "Beschreibt die Verwaltungsrichtlinien für Windows-PCs und die Einstellungen für das Microsoft Intune Center."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 12/15/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f0afda7e-f4c3-4bcd-b4bf-4304103cf73e
ms.reviewer: owenyen
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 9d67bf344be7a20853e21cf580939f1156d1a723
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2017
---
# <a name="use-policies-to-simplify-windows-pc-management"></a><span data-ttu-id="57abc-103">Verwenden von Richtlinien zum Vereinfachen der Verwaltung von Windows-PCs</span><span class="sxs-lookup"><span data-stu-id="57abc-103">Use policies to simplify Windows PC management</span></span>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="57abc-104">Um Windows-Desktops durch Ausführen des Intune-Softwareclients als PCs zu verwalten, können Sie nur die Richtlinien verwenden, die sich in der Intune-Verwaltungskonsole in den Richtlinien zur **Computerverwaltung** befinden.</span><span class="sxs-lookup"><span data-stu-id="57abc-104">To manage Windows desktops as PCs, by running the Intune software client on them, you can use only the policies that are under **Computer Management** policies in the Intune admin console.</span></span> <span data-ttu-id="57abc-105">Alle anderen Richtlinien in der Verwaltungskonsole gelten nur für mobile Geräte.</span><span class="sxs-lookup"><span data-stu-id="57abc-105">All of the other policies listed in the admin console are for mobile devices only.</span></span> <span data-ttu-id="57abc-106">Mit den Richtlinien zur **Computerverwaltung** können Sie die Einstellungen im Microsoft Intune Center konfigurieren, Updates auf PCs steuern und die Windows-Firewall für PCs konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="57abc-106">Using the **Computer Management** policies, you can configure the settings in the Microsoft Intune Center, control updates to PCs, and configure Windows Firewall for PCs.</span></span>

![Richtlinienvorlage für Windows-PCs](../media/pc_policy_template.png)

### <a name="manage-the-microsoft-intune-center"></a><span data-ttu-id="57abc-108">Verwalten des Microsoft Intune Center</span><span class="sxs-lookup"><span data-stu-id="57abc-108">Manage the Microsoft Intune Center</span></span>
<span data-ttu-id="57abc-109">Benutzern wird der Intune-Softwareclient als das **Microsoft Intune Center** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="57abc-109">Users see the Intune software client as the **Microsoft Intune Center**.</span></span> <span data-ttu-id="57abc-110">Das Microsoft Intune Center bietet Benutzern folgende Möglichkeiten:</span><span class="sxs-lookup"><span data-stu-id="57abc-110">The Microsoft Intune Center lets users:</span></span>

-   <span data-ttu-id="57abc-111">Abrufen von Anwendungen aus dem Unternehmensportal</span><span class="sxs-lookup"><span data-stu-id="57abc-111">Get applications from the company portal.</span></span>

-   <span data-ttu-id="57abc-112">Suchen nach Updates</span><span class="sxs-lookup"><span data-stu-id="57abc-112">Check for updates.</span></span>

-   <span data-ttu-id="57abc-113">Verwalten von Microsoft Intune Endpoint Protection</span><span class="sxs-lookup"><span data-stu-id="57abc-113">Manage Microsoft Intune Endpoint Protection.</span></span>

-  <span data-ttu-id="57abc-114">Anfordern von Remoteunterstützung</span><span class="sxs-lookup"><span data-stu-id="57abc-114">Request remote assistance.</span></span>

<span data-ttu-id="57abc-115">Das Microsoft Intune Center ist auf allen verwalteten Computern installiert.</span><span class="sxs-lookup"><span data-stu-id="57abc-115">The Microsoft Intune Center is installed on all managed computers.</span></span> <span data-ttu-id="57abc-116">Sie können die folgenden Einstellungen in einer Intune Center-Richtlinie konfigurieren, die anschließend Benutzern im Microsoft Intune Center angezeigt werden:</span><span class="sxs-lookup"><span data-stu-id="57abc-116">You can configure the following settings in an Intune policy, and these are displayed to users in the Microsoft Intune Center:</span></span>

|<span data-ttu-id="57abc-117">Richtlinieneinstellung</span><span class="sxs-lookup"><span data-stu-id="57abc-117">Policy setting</span></span>|<span data-ttu-id="57abc-118">Details</span><span class="sxs-lookup"><span data-stu-id="57abc-118">Details</span></span>|
|------------------|--------------------|
|<span data-ttu-id="57abc-119">**Name**</span><span class="sxs-lookup"><span data-stu-id="57abc-119">**Name**</span></span>|<span data-ttu-id="57abc-120">Name des Administrators, der den Computer verwaltet</span><span class="sxs-lookup"><span data-stu-id="57abc-120">The name of the administrator who manages the computer.</span></span><br /><span data-ttu-id="57abc-121">Maximale Länge: 40 Zeichen</span><span class="sxs-lookup"><span data-stu-id="57abc-121">Maximum length: 40 characters</span></span>|
|<span data-ttu-id="57abc-122">**Telefonnummer**</span><span class="sxs-lookup"><span data-stu-id="57abc-122">**Phone number**</span></span>|<span data-ttu-id="57abc-123">Telefonnummer des Administrators, der den Computer verwaltet</span><span class="sxs-lookup"><span data-stu-id="57abc-123">The telephone number of the administrator who manages the computer.</span></span><br /><span data-ttu-id="57abc-124">Maximale Länge: 20 Zeichen</span><span class="sxs-lookup"><span data-stu-id="57abc-124">Maximum length: 20 characters</span></span>|
|<span data-ttu-id="57abc-125">**E-Mail-Adresse**</span><span class="sxs-lookup"><span data-stu-id="57abc-125">**Email address**</span></span>|<span data-ttu-id="57abc-126">E-Mail-Adresse des Administrators, der den Computer verwaltet</span><span class="sxs-lookup"><span data-stu-id="57abc-126">The email address of the administrator who manages the computer.</span></span><br /><span data-ttu-id="57abc-127">Maximale Länge: 40 Zeichen</span><span class="sxs-lookup"><span data-stu-id="57abc-127">Maximum length: 40 characters</span></span>|
|<span data-ttu-id="57abc-128">**Name der Website**</span><span class="sxs-lookup"><span data-stu-id="57abc-128">**Web site name**</span></span>|<span data-ttu-id="57abc-129">Name der Supportwebsite für Benutzer</span><span class="sxs-lookup"><span data-stu-id="57abc-129">The name of your support website for users.</span></span><br /><span data-ttu-id="57abc-130">>Maximale Länge: 40 Zeichen</span><span class="sxs-lookup"><span data-stu-id="57abc-130">>Maximum length: 40 characters</span></span>|
|<span data-ttu-id="57abc-131">**URL der Website**</span><span class="sxs-lookup"><span data-stu-id="57abc-131">**Web site URL**</span></span>|<span data-ttu-id="57abc-132">URL der Supportwebsite</span><span class="sxs-lookup"><span data-stu-id="57abc-132">The URL of your support website.</span></span><br /><span data-ttu-id="57abc-133">Maximale Länge: 150 Zeichen</span><span class="sxs-lookup"><span data-stu-id="57abc-133">Maximum length: 150 characters</span></span>|
|<span data-ttu-id="57abc-134">**Anmerkungen**</span><span class="sxs-lookup"><span data-stu-id="57abc-134">**Notes**</span></span>|<span data-ttu-id="57abc-135">Hinweis, der Benutzern angezeigt wird</span><span class="sxs-lookup"><span data-stu-id="57abc-135">A note that is displayed to users.</span></span><br /><span data-ttu-id="57abc-136">Maximale Länge: 120 Zeichen</span><span class="sxs-lookup"><span data-stu-id="57abc-136">Maximum length: 120 characters</span></span>|

<span data-ttu-id="57abc-137">Finden Sie Informationen zu Richtlinien und Einstellungen für Windows-PCs in den folgenden Ressourcen:</span><span class="sxs-lookup"><span data-stu-id="57abc-137">See the following resources for information about policies and settings that you can configure for Windows PCs:</span></span>

- <span data-ttu-id="57abc-138">[Aktualisieren Ihrer Windows-PCs mit Softwareupdates in Microsoft Intune](keep-windows-pcs-up-to-date-with-software-updates-in-microsoft-intune.md): Aufgrund dieser Richtlinien suchen verwaltete Computer nach Softwareupdates und laden diese von Microsoft und Drittanbietern herunter.</span><span class="sxs-lookup"><span data-stu-id="57abc-138">[Keep Windows PCs up to date with software updates in Microsoft Intune](keep-windows-pcs-up-to-date-with-software-updates-in-microsoft-intune.md) - These policies make managed computers check for, and download software updates from, Microsoft and from third parties.</span></span> <span data-ttu-id="57abc-139">Diese Updates enthalten keine Upgrades des Betriebssystems (d.h. keine Upgrades von Windows 7 auf Windows 10 oder von Windows 10 auf eine höhere Version).</span><span class="sxs-lookup"><span data-stu-id="57abc-139">These updates do not include OS upgrades (e.g., upgrading from Windows 7 to Windows 10, or upgrades from one Windows 10 version to a later version).</span></span>

- <span data-ttu-id="57abc-140">[Schützen von Windows-PCs mit Endpoint Protection für Microsoft Intune](help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune.md): Zu diesen Einstellungen gehören Überprüfungszeitpläne und zu ergreifende Maßnahmen, wenn Malware erkannt wird.</span><span class="sxs-lookup"><span data-stu-id="57abc-140">[Help secure Windows PCs with Endpoint Protection for Microsoft Intune](help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune.md) - These settings include scan schedules and actions to take when malware is detected.</span></span>

- <span data-ttu-id="57abc-141">[Unterstützen des Schutzes von Windows-PCs mithilfe von Windows-Firewall-Richtlinien in Microsoft Intune](help-protect-windows-pcs-using-windows-firewall-policies-in-microsoft-intune.md): Diese Richtlinien vereinfachen die Verwaltung von Windows-Firewalleinstellungen auf verwalteten Computern.</span><span class="sxs-lookup"><span data-stu-id="57abc-141">[Help protect Windows PCs using Windows Firewall policies in Microsoft Intune](help-protect-windows-pcs-using-windows-firewall-policies-in-microsoft-intune.md) - These policies simplify the administration of Windows Firewall settings on managed computers.</span></span>


### <a name="see-also"></a><span data-ttu-id="57abc-142">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="57abc-142">See also</span></span>

[<span data-ttu-id="57abc-143">Allgemeine Aufgaben zur Verwaltung von Windows-PCs mit dem Intune-Softwareclient</span><span class="sxs-lookup"><span data-stu-id="57abc-143">Common Windows PC management tasks with the Intune software client</span></span>](common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client.md)
