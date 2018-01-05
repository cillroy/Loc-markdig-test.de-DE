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
ms.openlocfilehash: 4467122ac2fd616ebf032c1337ddcb284218fd90
ms.sourcegitcommit: e37e916e2bf14f092d3a767bc90d68c181d739fb
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/03/2018
---
# <a name="reference-for-date-entity"></a><span data-ttu-id="a2e5a-104">Verweis für die Datumsentität</span><span class="sxs-lookup"><span data-stu-id="a2e5a-104">Reference for Date entity</span></span>

<span data-ttu-id="a2e5a-105">Die Kategorie **Datum** enthält die **Datumsentität**, die zum Definieren von Datumsverweisen im Datenmodell verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="a2e5a-105">The **Date** category contains the **Date** entity used to define date references in the data model.</span></span>

<span data-ttu-id="a2e5a-106">**Datum**</span><span class="sxs-lookup"><span data-stu-id="a2e5a-106">**Date**</span></span>

<span data-ttu-id="a2e5a-107">Die **Datumsentität** stellt Datumsangaben dar, die auf mehrere Data Warehouse-Entitäten verweisen.</span><span class="sxs-lookup"><span data-stu-id="a2e5a-107">The **Date** entity represents dates that are referenced across multiple data warehouse entities.</span></span>


| <span data-ttu-id="a2e5a-108">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="a2e5a-108">Property</span></span>  | <span data-ttu-id="a2e5a-109">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="a2e5a-109">Description</span></span> | <span data-ttu-id="a2e5a-110">Beispiel</span><span class="sxs-lookup"><span data-stu-id="a2e5a-110">Example</span></span> |
|---------|------------|--------|
| <span data-ttu-id="a2e5a-111">DateKey</span><span class="sxs-lookup"><span data-stu-id="a2e5a-111">DateKey</span></span> | <span data-ttu-id="a2e5a-112">Eindeutiger Bezeichner für dieses Datum im Data Warehouse</span><span class="sxs-lookup"><span data-stu-id="a2e5a-112">Unique identifier for this date in the data warehouse.</span></span> | <span data-ttu-id="a2e5a-113">20160703</span><span class="sxs-lookup"><span data-stu-id="a2e5a-113">20160703</span></span> |
| <span data-ttu-id="a2e5a-114">FullDate</span><span class="sxs-lookup"><span data-stu-id="a2e5a-114">FullDate</span></span> | <span data-ttu-id="a2e5a-115">Dieses Datum wird im vollständigen Datums- und Uhrzeitformat dargestellt</span><span class="sxs-lookup"><span data-stu-id="a2e5a-115">This date represented in full Date/Time format.</span></span> | <span data-ttu-id="a2e5a-116">03.07.2016 12:00:00 Uhr</span><span class="sxs-lookup"><span data-stu-id="a2e5a-116">7/3/2016 12:00:00 AM</span></span> |
| <span data-ttu-id="a2e5a-117">DayOfWeek</span><span class="sxs-lookup"><span data-stu-id="a2e5a-117">DayOfWeek</span></span> | <span data-ttu-id="a2e5a-118">Wochentag</span><span class="sxs-lookup"><span data-stu-id="a2e5a-118">Day of week</span></span> | <span data-ttu-id="a2e5a-119">1</span><span class="sxs-lookup"><span data-stu-id="a2e5a-119">1</span></span> |
| <span data-ttu-id="a2e5a-120">DayOfMonth</span><span class="sxs-lookup"><span data-stu-id="a2e5a-120">DayOfMonth</span></span> | <span data-ttu-id="a2e5a-121">Tag des Monats</span><span class="sxs-lookup"><span data-stu-id="a2e5a-121">Day of month</span></span> | <span data-ttu-id="a2e5a-122">3</span><span class="sxs-lookup"><span data-stu-id="a2e5a-122">3</span></span> |
| <span data-ttu-id="a2e5a-123">DayOfYear</span><span class="sxs-lookup"><span data-stu-id="a2e5a-123">DayOfYear</span></span> | <span data-ttu-id="a2e5a-124">Tag des Jahres</span><span class="sxs-lookup"><span data-stu-id="a2e5a-124">Day of year</span></span> | <span data-ttu-id="a2e5a-125">185</span><span class="sxs-lookup"><span data-stu-id="a2e5a-125">185</span></span> |
| <span data-ttu-id="a2e5a-126">WeekOfYear</span><span class="sxs-lookup"><span data-stu-id="a2e5a-126">WeekOfYear</span></span> | <span data-ttu-id="a2e5a-127">Woche des Jahres</span><span class="sxs-lookup"><span data-stu-id="a2e5a-127">Week of year</span></span> | <span data-ttu-id="a2e5a-128">28</span><span class="sxs-lookup"><span data-stu-id="a2e5a-128">28</span></span> |
| <span data-ttu-id="a2e5a-129">MonthOfYear</span><span class="sxs-lookup"><span data-stu-id="a2e5a-129">MonthOfYear</span></span> | <span data-ttu-id="a2e5a-130">Monat des Jahres</span><span class="sxs-lookup"><span data-stu-id="a2e5a-130">Month of the year</span></span> | <span data-ttu-id="a2e5a-131">7</span><span class="sxs-lookup"><span data-stu-id="a2e5a-131">7</span></span> |
| <span data-ttu-id="a2e5a-132">CalendarQuarter</span><span class="sxs-lookup"><span data-stu-id="a2e5a-132">CalendarQuarter</span></span> | <span data-ttu-id="a2e5a-133">Kalenderquartal</span><span class="sxs-lookup"><span data-stu-id="a2e5a-133">Calendar quarter</span></span> | <span data-ttu-id="a2e5a-134">3</span><span class="sxs-lookup"><span data-stu-id="a2e5a-134">3</span></span> |
| <span data-ttu-id="a2e5a-135">CalendarYear</span><span class="sxs-lookup"><span data-stu-id="a2e5a-135">CalendarYear</span></span> | <span data-ttu-id="a2e5a-136">Kalenderjahr</span><span class="sxs-lookup"><span data-stu-id="a2e5a-136">Calendar year</span></span> | <span data-ttu-id="a2e5a-137">2016</span><span class="sxs-lookup"><span data-stu-id="a2e5a-137">2016</span></span> |
| <span data-ttu-id="a2e5a-138">DateKey</span><span class="sxs-lookup"><span data-stu-id="a2e5a-138">DateKey</span></span> | <span data-ttu-id="a2e5a-139">Eindeutiger Bezeichner für dieses Datum im Data Warehouse</span><span class="sxs-lookup"><span data-stu-id="a2e5a-139">Unique identifier for this date in the data warehouse.</span></span> | <span data-ttu-id="a2e5a-140">20160703</span><span class="sxs-lookup"><span data-stu-id="a2e5a-140">20160703</span></span> |
| <span data-ttu-id="a2e5a-141">FullDate</span><span class="sxs-lookup"><span data-stu-id="a2e5a-141">FullDate</span></span> | <span data-ttu-id="a2e5a-142">Dieses Datum wird im vollständigen Datums- und Uhrzeitformat dargestellt</span><span class="sxs-lookup"><span data-stu-id="a2e5a-142">This date represented in full Date/Time format.</span></span> | <span data-ttu-id="a2e5a-143">03.07.2016 12:00:00 Uhr</span><span class="sxs-lookup"><span data-stu-id="a2e5a-143">7/3/2016 12:00:00 AM</span></span> |
| <span data-ttu-id="a2e5a-144">DayOfWeek</span><span class="sxs-lookup"><span data-stu-id="a2e5a-144">DayOfWeek</span></span> | <span data-ttu-id="a2e5a-145">Wochentag</span><span class="sxs-lookup"><span data-stu-id="a2e5a-145">Day of week</span></span> | <span data-ttu-id="a2e5a-146">1</span><span class="sxs-lookup"><span data-stu-id="a2e5a-146">1</span></span> |
| <span data-ttu-id="a2e5a-147">DayOfMonth</span><span class="sxs-lookup"><span data-stu-id="a2e5a-147">DayOfMonth</span></span> | <span data-ttu-id="a2e5a-148">Tag des Monats</span><span class="sxs-lookup"><span data-stu-id="a2e5a-148">Day of month</span></span> | <span data-ttu-id="a2e5a-149">3</span><span class="sxs-lookup"><span data-stu-id="a2e5a-149">3</span></span> |
| <span data-ttu-id="a2e5a-150">DayOfYear</span><span class="sxs-lookup"><span data-stu-id="a2e5a-150">DayOfYear</span></span> | <span data-ttu-id="a2e5a-151">Tag des Jahres</span><span class="sxs-lookup"><span data-stu-id="a2e5a-151">Day of year</span></span> | <span data-ttu-id="a2e5a-152">185</span><span class="sxs-lookup"><span data-stu-id="a2e5a-152">185</span></span> |
| <span data-ttu-id="a2e5a-153">WeekOfYear</span><span class="sxs-lookup"><span data-stu-id="a2e5a-153">WeekOfYear</span></span> | <span data-ttu-id="a2e5a-154">Woche des Jahres</span><span class="sxs-lookup"><span data-stu-id="a2e5a-154">Week of year</span></span> | <span data-ttu-id="a2e5a-155">28</span><span class="sxs-lookup"><span data-stu-id="a2e5a-155">28</span></span> |
| <span data-ttu-id="a2e5a-156">MonthOfYear</span><span class="sxs-lookup"><span data-stu-id="a2e5a-156">MonthOfYear</span></span> | <span data-ttu-id="a2e5a-157">Monat des Jahres</span><span class="sxs-lookup"><span data-stu-id="a2e5a-157">Month of the year</span></span> | <span data-ttu-id="a2e5a-158">7</span><span class="sxs-lookup"><span data-stu-id="a2e5a-158">7</span></span> |
| <span data-ttu-id="a2e5a-159">CalendarQuarter</span><span class="sxs-lookup"><span data-stu-id="a2e5a-159">CalendarQuarter</span></span> | <span data-ttu-id="a2e5a-160">Kalenderquartal</span><span class="sxs-lookup"><span data-stu-id="a2e5a-160">Calendar quarter</span></span> | <span data-ttu-id="a2e5a-161">3</span><span class="sxs-lookup"><span data-stu-id="a2e5a-161">3</span></span> |
| <span data-ttu-id="a2e5a-162">CalendarYear</span><span class="sxs-lookup"><span data-stu-id="a2e5a-162">CalendarYear</span></span> | <span data-ttu-id="a2e5a-163">Kalenderjahr</span><span class="sxs-lookup"><span data-stu-id="a2e5a-163">Calendar year</span></span> | <span data-ttu-id="a2e5a-164">2016</span><span class="sxs-lookup"><span data-stu-id="a2e5a-164">2016</span></span> |

