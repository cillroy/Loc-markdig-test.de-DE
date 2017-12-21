---
title: IntuneManagementExtension Entity | Microsoft-Dokumentation
description: "Referenzthema für die Entitätskategorie „IntuneManagementExtension“ von Entitätensammlungen in der Intune Data Warehouse-API."
keywords: Intune Data Warehouse
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 11/06/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 73DF3B90-6D52-4EF6-AFFD-1873A18C7421
ms.reviewer: dariusz
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 30908e4dbb55e16db0e253330175f65fb127d523
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2017
---
# <a name="reference-for-intune-management-extension"></a><span data-ttu-id="5c59d-104">Referenz für die Intune-Verwaltungserweiterung</span><span class="sxs-lookup"><span data-stu-id="5c59d-104">Reference for Intune Management Extension</span></span>

<span data-ttu-id="5c59d-105">Die Kategorie **IntuneManagementExtension** enthält Entitäten für mobile Geräte zur Nachverfolgung von Informationen wie etwa der folgenden:</span><span class="sxs-lookup"><span data-stu-id="5c59d-105">The **IntuneManagementExtension** category contains entities for mobile devices that track information such as:</span></span>

  -  <span data-ttu-id="5c59d-106">Versionen einer IntuneManagementExtension</span><span class="sxs-lookup"><span data-stu-id="5c59d-106">Versions of an IntuneManagementExtension</span></span>
  -  <span data-ttu-id="5c59d-107">Installationsstatus einer IntuneManagementExtension</span><span class="sxs-lookup"><span data-stu-id="5c59d-107">Installation status of an IntuneManagementExtension</span></span>

## <a name="intunemanagementextensionversion"></a><span data-ttu-id="5c59d-108">IntuneManagementExtensionVersion</span><span class="sxs-lookup"><span data-stu-id="5c59d-108">IntuneManagementExtensionVersion</span></span>

<span data-ttu-id="5c59d-109">Die Entität **IntuneManagementExtensionVersion** listet alle von IntuneManagementExtension verwendeten Versionen auf.</span><span class="sxs-lookup"><span data-stu-id="5c59d-109">The **IntuneManagementExtensionVersion** entity lists all the versions used by IntuneManagementExtension.</span></span>

| <span data-ttu-id="5c59d-110">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="5c59d-110">Property</span></span>  | <span data-ttu-id="5c59d-111">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5c59d-111">Description</span></span> | <span data-ttu-id="5c59d-112">Beispiel</span><span class="sxs-lookup"><span data-stu-id="5c59d-112">Example</span></span> |
|---------|------------|--------|
| <span data-ttu-id="5c59d-113">ExtensionVersionKey</span><span class="sxs-lookup"><span data-stu-id="5c59d-113">ExtensionVersionKey</span></span> |<span data-ttu-id="5c59d-114">Eindeutiger Bezeichner für die IntuneManagementExtension-Version.</span><span class="sxs-lookup"><span data-stu-id="5c59d-114">Unique identifier of the IntuneManagementExtension version.</span></span> | <span data-ttu-id="5c59d-115">1</span><span class="sxs-lookup"><span data-stu-id="5c59d-115">1</span></span> |
| <span data-ttu-id="5c59d-116">ExtensionVersion</span><span class="sxs-lookup"><span data-stu-id="5c59d-116">ExtensionVersion</span></span> |<span data-ttu-id="5c59d-117">Die vierstellige Versionsnummer</span><span class="sxs-lookup"><span data-stu-id="5c59d-117">The 4 digit version number.</span></span> |<span data-ttu-id="5c59d-118">1.0.2.0</span><span class="sxs-lookup"><span data-stu-id="5c59d-118">1.0.2.0</span></span> |

## <a name="intunemanagementextensionhealthstate"></a><span data-ttu-id="5c59d-119">IntuneManagementExtensionHealthState</span><span class="sxs-lookup"><span data-stu-id="5c59d-119">IntuneManagementExtensionHealthState</span></span>

<span data-ttu-id="5c59d-120">**IntuneManagementExtensionHealthState** listet alle möglichen Status der IntuneManagementExtension auf.</span><span class="sxs-lookup"><span data-stu-id="5c59d-120">The **IntuneManagementExtensionHealthState** lists all possible health states of the IntuneManagementExtension.</span></span>

| <span data-ttu-id="5c59d-121">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="5c59d-121">Property</span></span>  | <span data-ttu-id="5c59d-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5c59d-122">Description</span></span> | <span data-ttu-id="5c59d-123">Beispiel</span><span class="sxs-lookup"><span data-stu-id="5c59d-123">Example</span></span> |
|---------|------------|--------|
| <span data-ttu-id="5c59d-124">ExtensionStateKey</span><span class="sxs-lookup"><span data-stu-id="5c59d-124">ExtensionStateKey</span></span> |<span data-ttu-id="5c59d-125">Eindeutiger Bezeichner des Integritätszustands</span><span class="sxs-lookup"><span data-stu-id="5c59d-125">Unique identifier of health state.</span></span> | <span data-ttu-id="5c59d-126">2</span><span class="sxs-lookup"><span data-stu-id="5c59d-126">2</span></span> |
| <span data-ttu-id="5c59d-127">ExtensionState</span><span class="sxs-lookup"><span data-stu-id="5c59d-127">ExtensionState</span></span> |<span data-ttu-id="5c59d-128">Der Integritätsstatus einer IntuneManagementExtension</span><span class="sxs-lookup"><span data-stu-id="5c59d-128">Health state of a IntuneManagementExtension.</span></span> | <span data-ttu-id="5c59d-129">Healthy</span><span class="sxs-lookup"><span data-stu-id="5c59d-129">Healthy</span></span> |

## <a name="intunemanagementextension"></a><span data-ttu-id="5c59d-130">IntuneManagementExtension</span><span class="sxs-lookup"><span data-stu-id="5c59d-130">IntuneManagementExtension</span></span>

<span data-ttu-id="5c59d-131">Die **IntuneManagementExtension** listet täglich den Integritätsstatus von IntuneManagementExtension auf jedem Windows 10-Gerät auf.</span><span class="sxs-lookup"><span data-stu-id="5c59d-131">The **IntuneManagementExtension** lists the IntuneManagementExtension health on each Windows 10 device per day.</span></span>
<span data-ttu-id="5c59d-132">Die Daten der letzten 60 Tage werden aufbewahrt.</span><span class="sxs-lookup"><span data-stu-id="5c59d-132">The data is retained for the last 60 days.</span></span> 

| <span data-ttu-id="5c59d-133">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="5c59d-133">Property</span></span>  | <span data-ttu-id="5c59d-134">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5c59d-134">Description</span></span> | <span data-ttu-id="5c59d-135">Beispiel</span><span class="sxs-lookup"><span data-stu-id="5c59d-135">Example</span></span> |
|---------|------------|--------|
| <span data-ttu-id="5c59d-136">DateKey</span><span class="sxs-lookup"><span data-stu-id="5c59d-136">DateKey</span></span> |<span data-ttu-id="5c59d-137">Eindeutiger Datumsbezeichner</span><span class="sxs-lookup"><span data-stu-id="5c59d-137">Unique identifier of the Date.</span></span> | <span data-ttu-id="5c59d-138">123</span><span class="sxs-lookup"><span data-stu-id="5c59d-138">123</span></span> |
| <span data-ttu-id="5c59d-139">TenantKey</span><span class="sxs-lookup"><span data-stu-id="5c59d-139">TenantKey</span></span> |<span data-ttu-id="5c59d-140">Eindeutiger Mandantenbezeichner</span><span class="sxs-lookup"><span data-stu-id="5c59d-140">Unique identifier of the Tenant.</span></span> | <span data-ttu-id="5c59d-141">456</span><span class="sxs-lookup"><span data-stu-id="5c59d-141">456</span></span> |
| <span data-ttu-id="5c59d-142">DeviceKey</span><span class="sxs-lookup"><span data-stu-id="5c59d-142">DeviceKey</span></span> |<span data-ttu-id="5c59d-143">Eindeutiger Bezeichner des Geräts</span><span class="sxs-lookup"><span data-stu-id="5c59d-143">Unique identifier of the Device.</span></span> | <span data-ttu-id="5c59d-144">789</span><span class="sxs-lookup"><span data-stu-id="5c59d-144">789</span></span> |
| <span data-ttu-id="5c59d-145">ExtensionVersionKey</span><span class="sxs-lookup"><span data-stu-id="5c59d-145">ExtensionVersionKey</span></span> |<span data-ttu-id="5c59d-146">Eindeutiger Bezeichner für die IntuneManagementExtension-Version.</span><span class="sxs-lookup"><span data-stu-id="5c59d-146">Unique identifier of the IntuneManagementExtension version.</span></span> | <span data-ttu-id="5c59d-147">1</span><span class="sxs-lookup"><span data-stu-id="5c59d-147">1</span></span> |
| <span data-ttu-id="5c59d-148">ExtensionStateKey</span><span class="sxs-lookup"><span data-stu-id="5c59d-148">ExtensionStateKey</span></span>|<span data-ttu-id="5c59d-149">Eindeutiger Bezeichner des Integritätszustands</span><span class="sxs-lookup"><span data-stu-id="5c59d-149">Unique identifier of health state.</span></span> | <span data-ttu-id="5c59d-150">2</span><span class="sxs-lookup"><span data-stu-id="5c59d-150">2</span></span> |