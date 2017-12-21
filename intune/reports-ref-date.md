---
title: "Daten – Intune Data Warehouse | Microsoft-Dokumentation"
description: "Referenzthema für die Kategorie „Datum“ der Entitätsauflistungen in der Intune Data Warehouse-API."
keywords: Intune Data Warehouse
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 07/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6B4BC650-62F7-4049-9DE4-CDECB579B58F
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 93d0f08697c8ee17ff44d599cb7b1bb262daa7ee
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2017
---
# <a name="reference-for-date-entity"></a><span data-ttu-id="ee4c3-104">Verweis für die Datumsentität</span><span class="sxs-lookup"><span data-stu-id="ee4c3-104">Reference for Date entity</span></span>

<span data-ttu-id="ee4c3-105">Die Kategorie **Datum** enthält die **Datumsentität**, die zum Definieren von Datumsverweisen im Datenmodell verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="ee4c3-105">The **Date** category contains the **Date** entity used to define date references in the data model.</span></span>

<span data-ttu-id="ee4c3-106">**Datum**</span><span class="sxs-lookup"><span data-stu-id="ee4c3-106">**Date**</span></span>

<span data-ttu-id="ee4c3-107">Die **Datumsentität** stellt Datumsangaben dar, die auf mehrere Data Warehouse-Entitäten verweisen.</span><span class="sxs-lookup"><span data-stu-id="ee4c3-107">The **Date** entity represents dates that are referenced across multiple data warehouse entities.</span></span>

| <span data-ttu-id="ee4c3-108">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="ee4c3-108">Property</span></span>  | <span data-ttu-id="ee4c3-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ee4c3-109">Description</span></span> | <span data-ttu-id="ee4c3-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="ee4c3-110">Example</span></span> |
|---------|------------|--------|
| <span data-ttu-id="ee4c3-111">DateKey</span><span class="sxs-lookup"><span data-stu-id="ee4c3-111">DateKey</span></span> | <span data-ttu-id="ee4c3-112">Eindeutiger Bezeichner für dieses Datum im Data Warehouse</span><span class="sxs-lookup"><span data-stu-id="ee4c3-112">Unique identifier for this date in the data warehouse.</span></span> | <span data-ttu-id="ee4c3-113">20160703</span><span class="sxs-lookup"><span data-stu-id="ee4c3-113">20160703</span></span> |
| <span data-ttu-id="ee4c3-114">FullDate</span><span class="sxs-lookup"><span data-stu-id="ee4c3-114">FullDate</span></span> | <span data-ttu-id="ee4c3-115">Dieses Datum wird im vollständigen Datums- und Uhrzeitformat dargestellt</span><span class="sxs-lookup"><span data-stu-id="ee4c3-115">This date represented in full Date/Time format.</span></span> | <span data-ttu-id="ee4c3-116">03.07.2016 12:00:00 Uhr</span><span class="sxs-lookup"><span data-stu-id="ee4c3-116">7/3/2016 12:00:00 AM</span></span> |
| <span data-ttu-id="ee4c3-117">DayOfWeek</span><span class="sxs-lookup"><span data-stu-id="ee4c3-117">DayOfWeek</span></span> | <span data-ttu-id="ee4c3-118">Wochentag</span><span class="sxs-lookup"><span data-stu-id="ee4c3-118">Day of week</span></span> | <span data-ttu-id="ee4c3-119">1</span><span class="sxs-lookup"><span data-stu-id="ee4c3-119">1</span></span> |
| <span data-ttu-id="ee4c3-120">DayOfMonth</span><span class="sxs-lookup"><span data-stu-id="ee4c3-120">DayOfMonth</span></span> | <span data-ttu-id="ee4c3-121">Tag des Monats</span><span class="sxs-lookup"><span data-stu-id="ee4c3-121">Day of month</span></span> | <span data-ttu-id="ee4c3-122">3</span><span class="sxs-lookup"><span data-stu-id="ee4c3-122">3</span></span> |
| <span data-ttu-id="ee4c3-123">DayOfYear</span><span class="sxs-lookup"><span data-stu-id="ee4c3-123">DayOfYear</span></span> | <span data-ttu-id="ee4c3-124">Tag des Jahres</span><span class="sxs-lookup"><span data-stu-id="ee4c3-124">Day of year</span></span> | <span data-ttu-id="ee4c3-125">185</span><span class="sxs-lookup"><span data-stu-id="ee4c3-125">185</span></span> |
| <span data-ttu-id="ee4c3-126">WeekOfYear</span><span class="sxs-lookup"><span data-stu-id="ee4c3-126">WeekOfYear</span></span> | <span data-ttu-id="ee4c3-127">Woche des Jahres</span><span class="sxs-lookup"><span data-stu-id="ee4c3-127">Week of year</span></span> | <span data-ttu-id="ee4c3-128">28</span><span class="sxs-lookup"><span data-stu-id="ee4c3-128">28</span></span> |
| <span data-ttu-id="ee4c3-129">MonthOfYear</span><span class="sxs-lookup"><span data-stu-id="ee4c3-129">MonthOfYear</span></span> | <span data-ttu-id="ee4c3-130">Monat des Jahres</span><span class="sxs-lookup"><span data-stu-id="ee4c3-130">Month of the year</span></span> | <span data-ttu-id="ee4c3-131">7</span><span class="sxs-lookup"><span data-stu-id="ee4c3-131">7</span></span> |
| <span data-ttu-id="ee4c3-132">CalendarQuarter</span><span class="sxs-lookup"><span data-stu-id="ee4c3-132">CalendarQuarter</span></span> | <span data-ttu-id="ee4c3-133">Kalenderquartal</span><span class="sxs-lookup"><span data-stu-id="ee4c3-133">Calendar quarter</span></span> | <span data-ttu-id="ee4c3-134">3</span><span class="sxs-lookup"><span data-stu-id="ee4c3-134">3</span></span> |
| <span data-ttu-id="ee4c3-135">CalendarYear</span><span class="sxs-lookup"><span data-stu-id="ee4c3-135">CalendarYear</span></span> | <span data-ttu-id="ee4c3-136">Kalenderjahr</span><span class="sxs-lookup"><span data-stu-id="ee4c3-136">Calendar year</span></span> | <span data-ttu-id="ee4c3-137">2016</span><span class="sxs-lookup"><span data-stu-id="ee4c3-137">2016</span></span> |
| <span data-ttu-id="ee4c3-138">DateKey</span><span class="sxs-lookup"><span data-stu-id="ee4c3-138">DateKey</span></span> | <span data-ttu-id="ee4c3-139">Eindeutiger Bezeichner für dieses Datum im Data Warehouse</span><span class="sxs-lookup"><span data-stu-id="ee4c3-139">Unique identifier for this date in the data warehouse.</span></span> | <span data-ttu-id="ee4c3-140">20160703</span><span class="sxs-lookup"><span data-stu-id="ee4c3-140">20160703</span></span> |
| <span data-ttu-id="ee4c3-141">FullDate</span><span class="sxs-lookup"><span data-stu-id="ee4c3-141">FullDate</span></span> | <span data-ttu-id="ee4c3-142">Dieses Datum wird im vollständigen Datums- und Uhrzeitformat dargestellt</span><span class="sxs-lookup"><span data-stu-id="ee4c3-142">This date represented in full Date/Time format.</span></span> | <span data-ttu-id="ee4c3-143">03.07.2016 12:00:00 Uhr</span><span class="sxs-lookup"><span data-stu-id="ee4c3-143">7/3/2016 12:00:00 AM</span></span> |
| <span data-ttu-id="ee4c3-144">DayOfWeek</span><span class="sxs-lookup"><span data-stu-id="ee4c3-144">DayOfWeek</span></span> | <span data-ttu-id="ee4c3-145">Wochentag</span><span class="sxs-lookup"><span data-stu-id="ee4c3-145">Day of week</span></span> | <span data-ttu-id="ee4c3-146">1</span><span class="sxs-lookup"><span data-stu-id="ee4c3-146">1</span></span> |
| <span data-ttu-id="ee4c3-147">DayOfMonth</span><span class="sxs-lookup"><span data-stu-id="ee4c3-147">DayOfMonth</span></span> | <span data-ttu-id="ee4c3-148">Tag des Monats</span><span class="sxs-lookup"><span data-stu-id="ee4c3-148">Day of month</span></span> | <span data-ttu-id="ee4c3-149">3</span><span class="sxs-lookup"><span data-stu-id="ee4c3-149">3</span></span> |
| <span data-ttu-id="ee4c3-150">DayOfYear</span><span class="sxs-lookup"><span data-stu-id="ee4c3-150">DayOfYear</span></span> | <span data-ttu-id="ee4c3-151">Tag des Jahres</span><span class="sxs-lookup"><span data-stu-id="ee4c3-151">Day of year</span></span> | <span data-ttu-id="ee4c3-152">185</span><span class="sxs-lookup"><span data-stu-id="ee4c3-152">185</span></span> |
| <span data-ttu-id="ee4c3-153">WeekOfYear</span><span class="sxs-lookup"><span data-stu-id="ee4c3-153">WeekOfYear</span></span> | <span data-ttu-id="ee4c3-154">Woche des Jahres</span><span class="sxs-lookup"><span data-stu-id="ee4c3-154">Week of year</span></span> | <span data-ttu-id="ee4c3-155">28</span><span class="sxs-lookup"><span data-stu-id="ee4c3-155">28</span></span> |
| <span data-ttu-id="ee4c3-156">MonthOfYear</span><span class="sxs-lookup"><span data-stu-id="ee4c3-156">MonthOfYear</span></span> | <span data-ttu-id="ee4c3-157">Monat des Jahres</span><span class="sxs-lookup"><span data-stu-id="ee4c3-157">Month of the year</span></span> | <span data-ttu-id="ee4c3-158">7</span><span class="sxs-lookup"><span data-stu-id="ee4c3-158">7</span></span> |
| <span data-ttu-id="ee4c3-159">CalendarQuarter</span><span class="sxs-lookup"><span data-stu-id="ee4c3-159">CalendarQuarter</span></span> | <span data-ttu-id="ee4c3-160">Kalenderquartal</span><span class="sxs-lookup"><span data-stu-id="ee4c3-160">Calendar quarter</span></span> | <span data-ttu-id="ee4c3-161">3</span><span class="sxs-lookup"><span data-stu-id="ee4c3-161">3</span></span> |
| <span data-ttu-id="ee4c3-162">CalendarYear</span><span class="sxs-lookup"><span data-stu-id="ee4c3-162">CalendarYear</span></span> | <span data-ttu-id="ee4c3-163">Kalenderjahr</span><span class="sxs-lookup"><span data-stu-id="ee4c3-163">Calendar year</span></span> | <span data-ttu-id="ee4c3-164">2016</span><span class="sxs-lookup"><span data-stu-id="ee4c3-164">2016</span></span> |
