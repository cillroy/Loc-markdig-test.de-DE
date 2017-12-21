---
title: Datenmodell von Data Warehouse | Microsoft-Dokumentation
description: "Intune Data Warehouse prüft täglich die Daten, um eine Verlaufsansicht Ihrer sich ständig ändernden mobilen Umgebung bereitzustellen."
keywords: Intune Data Warehouse
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 11/14/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4D04D3D9-4B6C-41CD-AAF8-466AF8FA6032
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 29825c58febc813c7b11072699d06106725584d3
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2017
---
# <a name="data-warehouse-data-model"></a><span data-ttu-id="99edc-104">Datenmodell von Data Warehouse</span><span class="sxs-lookup"><span data-stu-id="99edc-104">Data Warehouse data model</span></span>

<span data-ttu-id="99edc-105">Intune Data Warehouse entnimmt täglich Datenstichproben, um eine Verlaufsansicht Ihrer sich ständig ändernden Umgebung mobiler Geräte bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="99edc-105">The Intune Data Warehouse samples data daily to provide a historical view of your continually changing environment of mobile devices.</span></span> <span data-ttu-id="99edc-106">Die Ansicht besteht aus zeitlich aufeinander bezogenen Elementen.</span><span class="sxs-lookup"><span data-stu-id="99edc-106">The view is composed of related things in time.</span></span>

## <a name="things-entity-sets"></a><span data-ttu-id="99edc-107">Elemente: Entitätenmengen</span><span class="sxs-lookup"><span data-stu-id="99edc-107">Things: Entity sets</span></span>

<span data-ttu-id="99edc-108">Das Warehouse macht Daten in den folgenden allgemeinen Bereichen verfügbar:</span><span class="sxs-lookup"><span data-stu-id="99edc-108">The warehouse exposes data in the following high-level areas:</span></span>

  -  <span data-ttu-id="99edc-109">Apps und Nutzung mit aktiviertem App-Schutz</span><span class="sxs-lookup"><span data-stu-id="99edc-109">App protection enabled apps and usage</span></span>
  -  <span data-ttu-id="99edc-110">Registrierte Geräte, Eigenschaften und Inventar</span><span class="sxs-lookup"><span data-stu-id="99edc-110">Enrolled devices, properties, and inventory</span></span>
  -  <span data-ttu-id="99edc-111">Apps- und Softwareinventar</span><span class="sxs-lookup"><span data-stu-id="99edc-111">Apps and software inventory</span></span>
  -  <span data-ttu-id="99edc-112">Gerätekonfiguration und Konformitätsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="99edc-112">Device configuration and compliance policies</span></span>

<span data-ttu-id="99edc-113">Diese Bereiche enthalten die Entitäten, oder Elemente, die für Ihre Intune-Umgebung von Bedeutung sind.</span><span class="sxs-lookup"><span data-stu-id="99edc-113">These areas contain the entities, or things, that are meaningful to your Intune environment.</span></span> <span data-ttu-id="99edc-114">Informationen zu den Entitätenmengen finden Sie in den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="99edc-114">You find details about the entity sets in the following topics:</span></span>

  -  [<span data-ttu-id="99edc-115">Anwendung</span><span class="sxs-lookup"><span data-stu-id="99edc-115">Application</span></span>](reports-ref-application.md)
  -  [<span data-ttu-id="99edc-116">Datum</span><span class="sxs-lookup"><span data-stu-id="99edc-116">Date</span></span>](reports-ref-date.md)
  -  [<span data-ttu-id="99edc-117">Geräte</span><span class="sxs-lookup"><span data-stu-id="99edc-117">Devices</span></span>](reports-ref-devices.md)
  -  [<span data-ttu-id="99edc-118">Intune-Verwaltungserweiterung</span><span class="sxs-lookup"><span data-stu-id="99edc-118">Intune Management Extension</span></span>](reports-ref-intunemanagementextension.md)
  -  [<span data-ttu-id="99edc-119">Richtlinie</span><span class="sxs-lookup"><span data-stu-id="99edc-119">Policy</span></span>](reports-ref-policy.md)
  -  [<span data-ttu-id="99edc-120">Mobile App-Verwaltung (MAM)</span><span class="sxs-lookup"><span data-stu-id="99edc-120">Mobile App Management (MAM)</span></span>](reports-ref-mobile-app-management.md)
  -  [<span data-ttu-id="99edc-121">Benutzer</span><span class="sxs-lookup"><span data-stu-id="99edc-121">User</span></span>](reports-ref-user.md)
  -  [<span data-ttu-id="99edc-122">Aktueller Benutzer</span><span class="sxs-lookup"><span data-stu-id="99edc-122">Current User</span></span>](reports-ref-current-user.md)
  -  [<span data-ttu-id="99edc-123">Zuordnung der Benutzergeräte</span><span class="sxs-lookup"><span data-stu-id="99edc-123">User Device Associations</span></span>](reports-ref-user-device.md)

## <a name="relationships-star-schema-model"></a><span data-ttu-id="99edc-124">Beziehungen: Sternschemamodell</span><span class="sxs-lookup"><span data-stu-id="99edc-124">Relationships: Star-schema model</span></span>

<span data-ttu-id="99edc-125">Das Warehouse strukturiert die Entitäten in Beziehungen, die für die von Ihnen gestellten Fragen relevant sind.</span><span class="sxs-lookup"><span data-stu-id="99edc-125">The warehouse organizes the entities in relationships that are meaningful to the type of questions you want to ask.</span></span> <span data-ttu-id="99edc-126">Beispielsweise können Sie die Anzahl von Installationen einer intern entwickelten Android-Anwendung überprüfen.</span><span class="sxs-lookup"><span data-stu-id="99edc-126">For example, you can review the number of installations of an in-house developed Android application.</span></span> <span data-ttu-id="99edc-127">Die Struktur des Data Warehouse ermöglicht Ihnen Einblicke in Ihre mobile Umgebung.</span><span class="sxs-lookup"><span data-stu-id="99edc-127">The structure of the data warehouse enables you to gain insight into your mobile environment.</span></span> <span data-ttu-id="99edc-128">Andere Analysetools wie Microsoft Power BI können das Datenmodell von Data Warehouse wiederum nutzen, um Visualisierungen und dynamische Dashboards zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="99edc-128">In turn, analytics tools, such as Microsoft Power BI, can use the Data Warehouse data model to create visualizations and dynamic dashboards.</span></span>

<span data-ttu-id="99edc-129">Die Entitäten und Beziehungen verwenden ein Sternschemamodell.</span><span class="sxs-lookup"><span data-stu-id="99edc-129">The entities and relationships use a star-schema model.</span></span> <span data-ttu-id="99edc-130">Ein Sternschema stellt Zusammenhänge zwischen Fakten über die Zeitdimension dar.</span><span class="sxs-lookup"><span data-stu-id="99edc-130">A star-schema correlates facts over the dimension of time.</span></span> <span data-ttu-id="99edc-131">Im Kontext des Modells ist ein *Fakt* eine quantitative Messung, z.B. die Anzahl der Geräte, die Anzahl von Apps oder der Zeitpunkt der Registrierung.</span><span class="sxs-lookup"><span data-stu-id="99edc-131">A *fact* in the context of the model is a quantitative measurement such as the number of devices, number of apps, or time of enrollment.</span></span> <span data-ttu-id="99edc-132">In Faktentabellen werden große Datenmengen gespeichert.</span><span class="sxs-lookup"><span data-stu-id="99edc-132">Fact tables store a lot of data.</span></span> <span data-ttu-id="99edc-133">Sie können sehr groß werden, daher werden Informationen normalerweise auf 30 Tage beschränkt.</span><span class="sxs-lookup"><span data-stu-id="99edc-133">They can get very large, and so they typically limit information to 30 days.</span></span> <span data-ttu-id="99edc-134">Eine *Dimension* stellt Kontext zu den Fakten bereit.</span><span class="sxs-lookup"><span data-stu-id="99edc-134">A *dimension* provides context to the facts.</span></span> <span data-ttu-id="99edc-135">Während Fakten darstellen, was passiert ist, geben Dimensionen an, wem etwas passiert ist.</span><span class="sxs-lookup"><span data-stu-id="99edc-135">Where the fact measures what happened, the dimensions indicate to whom it happened.</span></span> <span data-ttu-id="99edc-136">Dimensionstabellen, wie z.B. die Tabelle **Benutzer**, sind kleiner und können Daten für längere Zeit aufbewahren als Faktentabellen.</span><span class="sxs-lookup"><span data-stu-id="99edc-136">Dimension tables, such as the like the **User** table are smaller and can retrain data for longer periods of time= than fact tables.</span></span> 

<span data-ttu-id="99edc-137">Ein Sternschema-Modell bietet hohe für Flexibilität und Analysefunktionen, damit Sie die Berichte erstellen können, die zum Verständnis der Entwicklung Ihrer mobilen Umgebung benötigen.</span><span class="sxs-lookup"><span data-stu-id="99edc-137">A star-schema model is optimized for flexibility and data analysis so that you can create the reports needed to understand your evolving mobile environment.</span></span>

## <a name="time-daily-snapshots"></a><span data-ttu-id="99edc-138">Zeit: Tägliche Momentaufnahmen</span><span class="sxs-lookup"><span data-stu-id="99edc-138">Time: Daily snapshots</span></span>

<span data-ttu-id="99edc-139">Das Warehouse ist Ihren Intune-Daten nachgelagert.</span><span class="sxs-lookup"><span data-stu-id="99edc-139">The warehouse is downstream from your Intune data.</span></span> <span data-ttu-id="99edc-140">Intune erstellt täglich um Mitternacht UTC eine Momentaufnahme und speichert die Momentaufnahme im Warehouse.</span><span class="sxs-lookup"><span data-stu-id="99edc-140">Intune takes a daily snapshot at Midnight UTC and stores the snapshot in the warehouse.</span></span> <span data-ttu-id="99edc-141">Die Dauer der Aufbewahrung von Momentaufnahmen unterscheidet sich von Faktentabelle zu Faktentabelle.</span><span class="sxs-lookup"><span data-stu-id="99edc-141">The duration of held snapshots vary from fact table to fact table.</span></span> <span data-ttu-id="99edc-142">Einige werden sieben Tage, andere 30 Tage und einige auch länger gespeichert.</span><span class="sxs-lookup"><span data-stu-id="99edc-142">Some may hold seven days, others 30 days, and some even longer durations.</span></span>

## <a name="next-steps"></a><span data-ttu-id="99edc-143">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="99edc-143">Next steps</span></span>

 - <span data-ttu-id="99edc-144">Weitere Informationen zur Nachverfolgung der Benutzerlebensdauer über das Data Warehouse in Intune finden Sie unter [Darstellung der Benutzerlebensdauer im Intune Data Warehouse](reports-ref-user-timeline.md).</span><span class="sxs-lookup"><span data-stu-id="99edc-144">To learn more more about how the data warehouse tracks a user's lifetime in Intune, see [User lifetime representation in the Intune Data Warehouse](reports-ref-user-timeline.md).</span></span>
 - <span data-ttu-id="99edc-145">Weitere Informationen zum Arbeiten mit Data Warehouses finden Sie unter [Create First Data WareHouse](https://www.codeproject.com/Articles/652108/Create-First-Data-WareHouse) (Erstellen eines ersten Data Warehouse).</span><span class="sxs-lookup"><span data-stu-id="99edc-145">To learn more more about working with data warehouses in the [Create First Data WareHouse](https://www.codeproject.com/Articles/652108/Create-First-Data-WareHouse).</span></span>
 - <span data-ttu-id="99edc-146">Weitere Informationen zum Arbeiten mit Power BI und einem Data Warehouse finden Sie unter [Erstellen eines neuen Power BI-Berichts durch Importieren eines Datasets](https://powerbi.microsoft.com/documentation/powerbi-service-create-a-new-report/).</span><span class="sxs-lookup"><span data-stu-id="99edc-146">To learn more about working with Power BI and a data warehouse in [Create a new Power BI report by importing a dataset](https://powerbi.microsoft.com/documentation/powerbi-service-create-a-new-report/).</span></span> 
