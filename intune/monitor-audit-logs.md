---
title: "Überwachungsprotokolle für Intune-Aktivitäten"
description: "Erfahren Sie, wie Überwachungsprotokolle zu überprüfen, die Intune-Aktivitäten erfassen"
keywords: 
author: dougeby
manager: angrobe
ms.date: 12/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6ee841cc-5694-4ba1-8f66-1d58edec30a4
ms.openlocfilehash: 30067f60163a644f4347c51c249c25fb3428f8ba
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2017
---
# <a name="audit-logs-for-intune-activities"></a><span data-ttu-id="cf965-103">Überwachungsprotokolle für Intune-Aktivitäten</span><span class="sxs-lookup"><span data-stu-id="cf965-103">Audit logs for Intune activities</span></span>
<span data-ttu-id="cf965-104">Überwachungsprotokolle bieten Ihnen einen Datensatz von Aktivitäten, die eine Änderung in Microsoft Intune zu generieren.</span><span class="sxs-lookup"><span data-stu-id="cf965-104">Audit logs provide you with a record of activities that generate a change in Microsoft Intune.</span></span> <span data-ttu-id="cf965-105">Erstellen, aktualisieren (Bearbeiten), zu löschen, und weisen Sie Aktionen oder Remoteaufgaben, Überwachungsereignisse, die Sie überprüfen können, generieren.</span><span class="sxs-lookup"><span data-stu-id="cf965-105">Create, Update (edit), Delete, and Assign actions, or remote tasks, generate audit events that you can review.</span></span> <span data-ttu-id="cf965-106">Sie können die Überwachungsprotokolle für die meisten Arbeitslasten für Intune überprüfen.</span><span class="sxs-lookup"><span data-stu-id="cf965-106">You can review audit logs for most Intune workloads.</span></span> 

## <a name="who-can-access-the-data"></a><span data-ttu-id="cf965-107">Wer die Daten zugreifen können?</span><span class="sxs-lookup"><span data-stu-id="cf965-107">Who can access the data?</span></span>
<span data-ttu-id="cf965-108">Benutzer mit den folgenden Berechtigungen können Überwachungsprotokolle überprüfen:</span><span class="sxs-lookup"><span data-stu-id="cf965-108">Users with the following permissions can review audit logs:</span></span>
- <span data-ttu-id="cf965-109">Globaler Administrator</span><span class="sxs-lookup"><span data-stu-id="cf965-109">Global Administrator</span></span>
- <span data-ttu-id="cf965-110">Intune-Dienstadministrators</span><span class="sxs-lookup"><span data-stu-id="cf965-110">Intune Service Administrator</span></span>
- <span data-ttu-id="cf965-111">Eine Rolle "Intune" mit zugewiesene Administratoren **Überwachungsdaten** - **lesen** Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="cf965-111">Administrators assigned to an Intune role with **Audit data** - **Read** permissions</span></span>

## <a name="audit-logs-for-intune-workloads"></a><span data-ttu-id="cf965-112">Überwachungsprotokolle für Intune Arbeitslasten</span><span class="sxs-lookup"><span data-stu-id="cf965-112">Audit logs for Intune workloads</span></span>
<span data-ttu-id="cf965-113">Sie können die Überwachungsprotokolle in der Gruppe der Überwachung für die einzelnen arbeitsauslastungen Intune überprüfen.</span><span class="sxs-lookup"><span data-stu-id="cf965-113">You can review audit logs in the Monitoring group for each Intune workload.</span></span>  
1. <span data-ttu-id="cf965-114">Melden Sie sich beim [Azure-Portal](https://portal.azure.com) an.</span><span class="sxs-lookup"><span data-stu-id="cf965-114">Sign into the [Azure portal](https://portal.azure.com).</span></span>
2. <span data-ttu-id="cf965-115">Wählen Sie **Weitere Dienste** > **Überwachung und Verwaltung** > **Intune** aus.</span><span class="sxs-lookup"><span data-stu-id="cf965-115">Choose **More Services** > **Monitoring + Management** > **Intune**.</span></span>
3. <span data-ttu-id="cf965-116">Auf der **Intune** Blatt, wählen Sie die arbeitsauslastung für die Sie die Überwachungsprotokolle überprüfen möchten.</span><span class="sxs-lookup"><span data-stu-id="cf965-116">On the **Intune** blade, choose the workload for which you want to review audit logs.</span></span>
4. <span data-ttu-id="cf965-117">In der **Überwachung** Gruppe für die arbeitsauslastung **Überwachungsprotokollen**.</span><span class="sxs-lookup"><span data-stu-id="cf965-117">In the **Monitoring** group for the workload, choose **Audit logs**.</span></span>

## <a name="review-audit-events"></a><span data-ttu-id="cf965-118">Überprüfen Sie die Überwachungsereignisse</span><span class="sxs-lookup"><span data-stu-id="cf965-118">Review audit events</span></span>
<span data-ttu-id="cf965-119">![Überwachungsprotokolle](./media/monitor-audit-logs.png "Überwachungsprotokolle")</span><span class="sxs-lookup"><span data-stu-id="cf965-119">![Audit logs](./media/monitor-audit-logs.png "Audit logs")</span></span>

<span data-ttu-id="cf965-120">Ein Überwachungsprotokoll verfügt über eine Standardansicht für die Liste, die die folgenden Elemente angezeigt werden:</span><span class="sxs-lookup"><span data-stu-id="cf965-120">An audit log has a default list view that shows the following items:</span></span>    

- <span data-ttu-id="cf965-121">Datum und Uhrzeit des Auftretens</span><span class="sxs-lookup"><span data-stu-id="cf965-121">date and time of the occurrence</span></span>
- <span data-ttu-id="cf965-122">Initiiert von (Akteur)</span><span class="sxs-lookup"><span data-stu-id="cf965-122">Initiated by (Actor)</span></span>
- <span data-ttu-id="cf965-123">Aktivität</span><span class="sxs-lookup"><span data-stu-id="cf965-123">Activity</span></span>
- <span data-ttu-id="cf965-124">Ziel(en) in Bereiche einteilen</span><span class="sxs-lookup"><span data-stu-id="cf965-124">Target(s)</span></span>
- <span data-ttu-id="cf965-125">Category</span><span class="sxs-lookup"><span data-stu-id="cf965-125">Category</span></span>
- <span data-ttu-id="cf965-126">Status</span><span class="sxs-lookup"><span data-stu-id="cf965-126">Status</span></span>

<span data-ttu-id="cf965-127">Durch Klicken auf ein Element in der Listenansicht, erhalten Sie alle verfügbaren Details an.</span><span class="sxs-lookup"><span data-stu-id="cf965-127">By clicking an item in the list view, you get all available details about it.</span></span>

<span data-ttu-id="cf965-128">![Überwachungsprotokolle](./media/monitor-audit-log-detail.png "Überwachungsprotokolle")</span><span class="sxs-lookup"><span data-stu-id="cf965-128">![Audit logs](./media/monitor-audit-log-detail.png "Audit logs")</span></span>

> [!Note]    
> <span data-ttu-id="cf965-129">Die **gestartet, indem (Akteur)** Abschnitt in der Audit-Protokolldetails enthält Informationen zum zuständigen für der Aktivitäts und aus, auf dem er ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="cf965-129">The **Initiated by (actor)** section in the audit log details provides information about who performed the activity and from where it was performed.</span></span> <span data-ttu-id="cf965-130">Z. B., wenn Sie die Aktivität in Intune in Azure-Portal durchführen **Anwendung** immer listet **Microsoft Intune-portalerweiterung** und **Anwendungs-ID** immer verwendet die gleiche GUID.</span><span class="sxs-lookup"><span data-stu-id="cf965-130">For example, if you perform the activity in Intune in the Azure portal, **Application** always lists **Microsoft Intune portal extension** and the **Application ID** always uses the same GUID.</span></span> 
>    
> <span data-ttu-id="cf965-131">Die **Ziel** Abschnitt mehrere Ziele und Eigenschaften, die auf diesem geändert wurden aufzulisten.</span><span class="sxs-lookup"><span data-stu-id="cf965-131">The **Target(s)** section can list multiple targets and the properties that were changed.</span></span>  


## <a name="filter-audit-events"></a><span data-ttu-id="cf965-132">Filtern von Überwachungsereignissen</span><span class="sxs-lookup"><span data-stu-id="cf965-132">Filter audit events</span></span>
<span data-ttu-id="cf965-133">Jede arbeitsauslastung hat ein Menüelement, das die Kategorie der Überwachungssammeldienste Ereignisse im Zusammenhang mit diesem Blatt vorab filtert.</span><span class="sxs-lookup"><span data-stu-id="cf965-133">Each workload has a menu item that pre-filters the category of audit events associated with that blade.</span></span> <span data-ttu-id="cf965-134">Eine separater Filter-Option können Sie die in verschiedenen Kategorien und Aktion Ereignisdetails innerhalb dieser Kategorie zu ändern.</span><span class="sxs-lookup"><span data-stu-id="cf965-134">A separate filter option lets you change to different categories, and event action details within that category.</span></span> <span data-ttu-id="cf965-135">Sie können suchen, indem UPN (z. B. die Benutzer, die die Aktion wurde).</span><span class="sxs-lookup"><span data-stu-id="cf965-135">You can search by UPN (for example, the user who did the action).</span></span> <span data-ttu-id="cf965-136">Ein Bereich Datumsfilter kann 24 Stunden, 7 Tage oder 30-Tage-Optionen.</span><span class="sxs-lookup"><span data-stu-id="cf965-136">A date range filter allows 24 hours, 7 days, or 30-day options.</span></span> <span data-ttu-id="cf965-137">Standardmäßig werden die letzten 30 Tagen von Überwachungsereignissen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="cf965-137">By default, the last 30 days of audit events are displayed.</span></span>

## <a name="use-graph-api-to-retrieve-audit-events"></a><span data-ttu-id="cf965-138">Verwenden der Graph-API zum Abrufen von Überwachungsereignissen</span><span class="sxs-lookup"><span data-stu-id="cf965-138">Use Graph API to retrieve audit events</span></span>
<span data-ttu-id="cf965-139">Weitere Informationen zur Verwendung die Graph-API zum Abrufen von bis zu einem Jahr von Überwachungsereignissen, finden Sie unter [Liste AuditEvents](https://developer.microsoft.com/en-us/graph/docs/api-reference/beta/api/intune_auditing_auditevent_list).</span><span class="sxs-lookup"><span data-stu-id="cf965-139">For details about how to use the graph API to retrieve up to one year of audit events, see [List auditEvents](https://developer.microsoft.com/en-us/graph/docs/api-reference/beta/api/intune_auditing_auditevent_list).</span></span>