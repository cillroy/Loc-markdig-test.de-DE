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
ms.openlocfilehash: edbc6502ce7e0d7b3c8aaa49c0fd084bfda43dea
ms.sourcegitcommit: e37e916e2bf14f092d3a767bc90d68c181d739fb
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/03/2018
---
# <a name="user-device-association"></a><span data-ttu-id="528f6-104">Zuordnung der Benutzergeräte</span><span class="sxs-lookup"><span data-stu-id="528f6-104">User Device Association</span></span>

<span data-ttu-id="528f6-105">Die Entität **UserDeviceAssociation** enthält Zuweisungen von Benutzergeräten in Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="528f6-105">The **UserDeviceAssociation** entity contains user device associations in your organization.</span></span>


| <span data-ttu-id="528f6-106">Name</span><span class="sxs-lookup"><span data-stu-id="528f6-106">Name</span></span>               | <span data-ttu-id="528f6-107">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="528f6-107">Description</span></span>                                                                                      | <span data-ttu-id="528f6-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="528f6-108">Example</span></span>                |
|--------------------|--------------------------------------------------------------------------------------------------|------------------------|
| <span data-ttu-id="528f6-109">UserKey</span><span class="sxs-lookup"><span data-stu-id="528f6-109">UserKey</span></span>            | <span data-ttu-id="528f6-110">Eindeutiger Bezeichner für den Benutzer im Data Warehouse</span><span class="sxs-lookup"><span data-stu-id="528f6-110">Unique identifier of the user in the data warehouse.</span></span> <span data-ttu-id="528f6-111">(Ersatzschlüssel)</span><span class="sxs-lookup"><span data-stu-id="528f6-111">(Surrogate key).</span></span>                              | <span data-ttu-id="528f6-112">123</span><span class="sxs-lookup"><span data-stu-id="528f6-112">123</span></span>                    |
| <span data-ttu-id="528f6-113">DeviceKey</span><span class="sxs-lookup"><span data-stu-id="528f6-113">DeviceKey</span></span>          | <span data-ttu-id="528f6-114">Eindeutiger Bezeichner für das Gerät im Data Warehouse</span><span class="sxs-lookup"><span data-stu-id="528f6-114">Unique identifier of the device in the data warehouse.</span></span>                                            | <span data-ttu-id="528f6-115">123</span><span class="sxs-lookup"><span data-stu-id="528f6-115">123</span></span>                    |
| <span data-ttu-id="528f6-116">CreatedDateTimeUTC</span><span class="sxs-lookup"><span data-stu-id="528f6-116">CreatedDateTimeUTC</span></span> | <span data-ttu-id="528f6-117">Datum und Uhrzeit, als die Benutzergerätezuordnung erstellt wurde</span><span class="sxs-lookup"><span data-stu-id="528f6-117">Date and time when the user device association was created.</span></span> <span data-ttu-id="528f6-118">Verwendet UTC-Format</span><span class="sxs-lookup"><span data-stu-id="528f6-118">Uses UTC format.</span></span>                                | <span data-ttu-id="528f6-119">23.11.2016 12:00:00 Uhr</span><span class="sxs-lookup"><span data-stu-id="528f6-119">11/23/2016 12:00:00 AM</span></span> |
| <span data-ttu-id="528f6-120">isDeleted</span><span class="sxs-lookup"><span data-stu-id="528f6-120">IsDeleted</span></span>          | <span data-ttu-id="528f6-121">Gibt an, dass der Benutzer dieses Geräts die Registrierung aufgehoben hat und die Zuordnung nicht mehr aktuell ist</span><span class="sxs-lookup"><span data-stu-id="528f6-121">Indicates that the user unenrolled that device, and that the association is not current anymore.</span></span> | <span data-ttu-id="528f6-122">Wahr/falsch</span><span class="sxs-lookup"><span data-stu-id="528f6-122">True/False</span></span>             |
| <span data-ttu-id="528f6-123">EndedDateTimeUTC</span><span class="sxs-lookup"><span data-stu-id="528f6-123">EndedDateTimeUTC</span></span>   | <span data-ttu-id="528f6-124">Datum und Uhrzeit in UTC, als IsDeleted in **TRUE** geändert wurde</span><span class="sxs-lookup"><span data-stu-id="528f6-124">Date and time in UTC when IsDeleted changed to **True**.</span></span>                                              | <span data-ttu-id="528f6-125">23.06.2017, 12:00:00 Uhr</span><span class="sxs-lookup"><span data-stu-id="528f6-125">06/23/2017 12:00:00 AM</span></span> |

