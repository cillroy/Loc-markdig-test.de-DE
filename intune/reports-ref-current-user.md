---
title: Aktueller Benutzer - Datawarehouse mit Intune | Microsoft Docs
description: "Referenzthema für die Kategorie „Benutzer“ der Entitätsauflistungen in der Intune Data Warehouse-API."
keywords: Intune Data Warehouse
author: erikre
ms.author: erikre
manager: angrobe
ms.date: 12/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: C10E6752-E925-40AD-ABBF-6B621FB7AFC4
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: cabf39f603ac93a0716594c44174908e7c999e5c
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2017
---
# <a name="reference-for-current-user-entity"></a><span data-ttu-id="cca48-104">Referenz für die aktuelle Benutzerentität</span><span class="sxs-lookup"><span data-stu-id="cca48-104">Reference for Current User entity</span></span>

<span data-ttu-id="cca48-105">Die **Aktueller Benutzer** Kategorie enthaltenen Eigenschaften der Benutzerrolle in das Datenmodell.</span><span class="sxs-lookup"><span data-stu-id="cca48-105">The **Current User** category contains user properties in the data model.</span></span> <span data-ttu-id="cca48-106">Die Entitätssammlung **Aktueller Benutzer** ist auf die derzeit aktiven Benutzer begrenzt.</span><span class="sxs-lookup"><span data-stu-id="cca48-106">The **Current User** entity collection is limited to currently active users.</span></span> <span data-ttu-id="cca48-107">Die Entität enthält alle Azure Active Directory-Benutzer, denen derzeit eine Lizenz zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="cca48-107">The entity contains all the Azure Active Directory users that are currently assigned a license.</span></span> <span data-ttu-id="cca48-108">Bei der Lizenz kann es sich um eine Intune-Lizenz, eine Hybrid-Lizenz oder eine Microsoft Office 365-Lizenz handeln.</span><span class="sxs-lookup"><span data-stu-id="cca48-108">The license could be an Intune license, a Hybrid license, or a Microsoft Office 365 license.</span></span> <span data-ttu-id="cca48-109">Wenn ein Benutzer entfernt wurde, werden sie nicht in der Auflistung des aktuellen Benutzers dargestellt.</span><span class="sxs-lookup"><span data-stu-id="cca48-109">If a user has been removed, they will not be represented in the Current User collection.</span></span> <span data-ttu-id="cca48-110">Eine Sammlung mit dem Änderungsverlauf der Benutzerzustände finden Sie unter [Referenz für die Entität „Benutzer“](reports-ref-user.md).</span><span class="sxs-lookup"><span data-stu-id="cca48-110">For a collection that contains a history of changes in user state, see [Reference for user entity](reports-ref-user.md).</span></span>


## <a name="current-user"></a><span data-ttu-id="cca48-111">Aktueller Benutzer</span><span class="sxs-lookup"><span data-stu-id="cca48-111">Current User</span></span>

<span data-ttu-id="cca48-112">Die **Aktueller Benutzer** Entität Listet alle Benutzer auf die Azure Active Directory (Azure AD) mit zugewiesenen Lizenzen in Ihrem Unternehmen.</span><span class="sxs-lookup"><span data-stu-id="cca48-112">The **Current User** entity lists all the Azure Active Directory (Azure AD) users with assigned licenses in your enterprise.</span></span>

| <span data-ttu-id="cca48-113">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="cca48-113">Property</span></span>  | <span data-ttu-id="cca48-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cca48-114">Description</span></span> | <span data-ttu-id="cca48-115">Beispiel</span><span class="sxs-lookup"><span data-stu-id="cca48-115">Example</span></span> |
|---------|------------|--------|
| <span data-ttu-id="cca48-116">UserKey</span><span class="sxs-lookup"><span data-stu-id="cca48-116">UserKey</span></span> |<span data-ttu-id="cca48-117">Eindeutiger Bezeichner des Benutzers im Data Warehouse – Ersatzschlüssel</span><span class="sxs-lookup"><span data-stu-id="cca48-117">Unique identifier of the user in the data warehouse - surrogate key.</span></span> |<span data-ttu-id="cca48-118">123</span><span class="sxs-lookup"><span data-stu-id="cca48-118">123</span></span> |
| <span data-ttu-id="cca48-119">UserId</span><span class="sxs-lookup"><span data-stu-id="cca48-119">UserId</span></span> |<span data-ttu-id="cca48-120">Eindeutiger Bezeichner des Benutzers – Ähnlich wie UserKey, ist jedoch ein natürlicher Schlüssel</span><span class="sxs-lookup"><span data-stu-id="cca48-120">Unique identifier of the user  - similar to UserKey, but is a natural key.</span></span> |<span data-ttu-id="cca48-121">b66bc706-ffff-7437-0340-032819502773</span><span class="sxs-lookup"><span data-stu-id="cca48-121">b66bc706-ffff-7437-0340-032819502773</span></span> |
| <span data-ttu-id="cca48-122">UserEmail</span><span class="sxs-lookup"><span data-stu-id="cca48-122">UserEmail</span></span> |<span data-ttu-id="cca48-123">E-Mail-Adresse des Benutzers</span><span class="sxs-lookup"><span data-stu-id="cca48-123">Email address of the user.</span></span> |John@constoso.com |
| <span data-ttu-id="cca48-124">UPN</span><span class="sxs-lookup"><span data-stu-id="cca48-124">UPN</span></span> | <span data-ttu-id="cca48-125">Der Prinzipalname des Benutzers.</span><span class="sxs-lookup"><span data-stu-id="cca48-125">User principal name of the user.</span></span> | John@constoso.com |
| <span data-ttu-id="cca48-126">DisplayName</span><span class="sxs-lookup"><span data-stu-id="cca48-126">DisplayName</span></span> |<span data-ttu-id="cca48-127">Anzeigename des Benutzers</span><span class="sxs-lookup"><span data-stu-id="cca48-127">Display name of the user.</span></span> |<span data-ttu-id="cca48-128">John</span><span class="sxs-lookup"><span data-stu-id="cca48-128">John</span></span> |
| <span data-ttu-id="cca48-129">IntuneLicensed</span><span class="sxs-lookup"><span data-stu-id="cca48-129">IntuneLicensed</span></span> |<span data-ttu-id="cca48-130">Gibt an, ob dieser Benutzer über Intune lizenziert ist oder nicht.</span><span class="sxs-lookup"><span data-stu-id="cca48-130">Specifies if this user is Intune licensed or not.</span></span> |<span data-ttu-id="cca48-131">Wahr/falsch</span><span class="sxs-lookup"><span data-stu-id="cca48-131">True/False</span></span> |
| <span data-ttu-id="cca48-132">StartDateInclusiveUTC</span><span class="sxs-lookup"><span data-stu-id="cca48-132">StartDateInclusiveUTC</span></span> |<span data-ttu-id="cca48-133">Datum und Uhrzeit in UTC, als der Benutzer im Data Warehouse erstellt wurde</span><span class="sxs-lookup"><span data-stu-id="cca48-133">Date and time in UTC when this user was created in the data warehouse.</span></span> |<span data-ttu-id="cca48-134">23.11.2016 12:00:00 Uhr</span><span class="sxs-lookup"><span data-stu-id="cca48-134">11/23/2016 12:00:00 AM</span></span> |
| <span data-ttu-id="cca48-135">RowLastModifiedDateTimeUTC</span><span class="sxs-lookup"><span data-stu-id="cca48-135">RowLastModifiedDateTimeUTC</span></span> |<span data-ttu-id="cca48-136">Datum und Uhrzeit in UTC, als dieser Benutzer das letzte Mal im Data Warehouse geändert wurde</span><span class="sxs-lookup"><span data-stu-id="cca48-136">Date and time in UTC when this user was last modified in the data warehouse.</span></span> |<span data-ttu-id="cca48-137">23.11.2016 12:00:00 Uhr</span><span class="sxs-lookup"><span data-stu-id="cca48-137">11/23/2016 12:00:00 AM</span></span> |

## <a name="next-steps"></a><span data-ttu-id="cca48-138">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="cca48-138">Next steps</span></span>
 - <span data-ttu-id="cca48-139">Sie können die **Benutzer** entitätsauflistung, um die Benutzerdaten für Benutzer zu erweitern, die nicht aktiv sind.</span><span class="sxs-lookup"><span data-stu-id="cca48-139">You can use the **Users** entity collection to expand the user data to users who are not currently active.</span></span> <span data-ttu-id="cca48-140">Weitere Informationen finden Sie unter [Referenz für die Entität „Benutzer“](reports-ref-user.md).</span><span class="sxs-lookup"><span data-stu-id="cca48-140">For more information, see [Reference for user entity](reports-ref-user.md).</span></span>
 - <span data-ttu-id="cca48-141">Informationen zur Nachverfolgung der Benutzerlebensdauer über das Data Warehouse in Intune finden Sie unter [Darstellung der Benutzerlebensdauer im Intune Data Warehouse](reports-ref-user-timeline.md).</span><span class="sxs-lookup"><span data-stu-id="cca48-141">Learn more about how the data warehouse tracks a user's lifetime in Intune, see [User lifetime representation in the Intune Data Warehouse](reports-ref-user-timeline.md).</span></span>
