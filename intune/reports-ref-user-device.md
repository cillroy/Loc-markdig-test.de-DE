---
title: "Zuordnung von Benutzergeräten – Intune Data Warehouse | Microsoft-Dokumentation"
description: "Eine Liste der Änderungen in der Intune Data Warehouse-API."
keywords: Intune Data Warehouse
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 10/19/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 777484A7-09CE-4409-987F-76B3F87DFE93
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: cc8d775eec58d55eec83ccdb6687d0451d3a4dfc
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2018
---
# <a name="user-device-association"></a><span data-ttu-id="7f355-104">Zuordnung der Benutzergeräte</span><span class="sxs-lookup"><span data-stu-id="7f355-104">User Device Association</span></span>

<span data-ttu-id="7f355-105">Die Entität **UserDeviceAssociation** enthält Zuweisungen von Benutzergeräten in Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="7f355-105">The **UserDeviceAssociation** entity contains user device associations in your organization.</span></span>


|        <span data-ttu-id="7f355-106">Name</span><span class="sxs-lookup"><span data-stu-id="7f355-106">Name</span></span>        |                                           <span data-ttu-id="7f355-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="7f355-107">Description</span></span>                                            |        <span data-ttu-id="7f355-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="7f355-108">Example</span></span>         |
|--------------------|--------------------------------------------------------------------------------------------------|------------------------|
|      <span data-ttu-id="7f355-109">UserKey</span><span class="sxs-lookup"><span data-stu-id="7f355-109">UserKey</span></span>       |              <span data-ttu-id="7f355-110">Eindeutiger Bezeichner für den Benutzer im Data Warehouse</span><span class="sxs-lookup"><span data-stu-id="7f355-110">Unique identifier of the user in the data warehouse.</span></span> <span data-ttu-id="7f355-111">(Ersatzschlüssel)</span><span class="sxs-lookup"><span data-stu-id="7f355-111">(Surrogate key).</span></span>               |          <span data-ttu-id="7f355-112">123</span><span class="sxs-lookup"><span data-stu-id="7f355-112">123</span></span>           |
|     <span data-ttu-id="7f355-113">DeviceKey</span><span class="sxs-lookup"><span data-stu-id="7f355-113">DeviceKey</span></span>      |                      <span data-ttu-id="7f355-114">Eindeutiger Bezeichner für das Gerät im Data Warehouse</span><span class="sxs-lookup"><span data-stu-id="7f355-114">Unique identifier of the device in the data warehouse.</span></span>                      |          <span data-ttu-id="7f355-115">123</span><span class="sxs-lookup"><span data-stu-id="7f355-115">123</span></span>           |
| <span data-ttu-id="7f355-116">CreatedDateTimeUTC</span><span class="sxs-lookup"><span data-stu-id="7f355-116">CreatedDateTimeUTC</span></span> |           <span data-ttu-id="7f355-117">Datum und Uhrzeit, als die Benutzergerätezuordnung erstellt wurde</span><span class="sxs-lookup"><span data-stu-id="7f355-117">Date and time when the user device association was created.</span></span> <span data-ttu-id="7f355-118">Verwendet UTC-Format</span><span class="sxs-lookup"><span data-stu-id="7f355-118">Uses UTC format.</span></span>           | <span data-ttu-id="7f355-119">23.11.2016 12:00:00 Uhr</span><span class="sxs-lookup"><span data-stu-id="7f355-119">11/23/2016 12:00:00 AM</span></span> |
|     <span data-ttu-id="7f355-120">isDeleted</span><span class="sxs-lookup"><span data-stu-id="7f355-120">IsDeleted</span></span>      | <span data-ttu-id="7f355-121">Gibt an, dass der Benutzer dieses Geräts die Registrierung aufgehoben hat und die Zuordnung nicht mehr aktuell ist</span><span class="sxs-lookup"><span data-stu-id="7f355-121">Indicates that the user unenrolled that device, and that the association is not current anymore.</span></span> |       <span data-ttu-id="7f355-122">Wahr/falsch</span><span class="sxs-lookup"><span data-stu-id="7f355-122">True/False</span></span>       |
|  <span data-ttu-id="7f355-123">EndedDateTimeUTC</span><span class="sxs-lookup"><span data-stu-id="7f355-123">EndedDateTimeUTC</span></span>  |              <span data-ttu-id="7f355-124">Datum und Uhrzeit in UTC, als IsDeleted in <strong>TRUE</strong> geändert wurde</span><span class="sxs-lookup"><span data-stu-id="7f355-124">Date and time in UTC when IsDeleted changed to <strong>True</strong>.</span></span>               | <span data-ttu-id="7f355-125">23.06.2017, 12:00:00 Uhr</span><span class="sxs-lookup"><span data-stu-id="7f355-125">06/23/2017 12:00:00 AM</span></span> |

