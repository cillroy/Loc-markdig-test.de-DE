---
title: Endpunkt der Intune Data Warehouse-API | Microsoft-Dokumentation
description: Das Referenzthema beschreibt die API-URL-Struktur.
keywords: Intune Data Warehouse
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 07/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: A7A174EC-109D-4BB8-B460-F53AA2D033E6
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 09e2e6ed94fcd96857b77e60bb2e617587c3b3f2
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2018
---
# <a name="intune-data-warehouse-api-endpoint"></a><span data-ttu-id="f6fe6-104">Endpunkt der Intune Data Warehouse-API</span><span class="sxs-lookup"><span data-stu-id="f6fe6-104">Intune Data Warehouse API endpoint</span></span>

<span data-ttu-id="f6fe6-105">Sie können die Intune-Data Warehouse-API mit einem Konto mit bestimmten rollenbasierten Zugriffssteuerungen und Azure AD-Anmeldeinformationen verwenden.</span><span class="sxs-lookup"><span data-stu-id="f6fe6-105">You can use the Intune Data Warehouse API with an account with specific role-based access controls and Azure AD credentials.</span></span> <span data-ttu-id="f6fe6-106">Anschließend autorisieren Sie Ihren REST-Client mithilfe von OAuth 2.0 für Azure AD.</span><span class="sxs-lookup"><span data-stu-id="f6fe6-106">You will then authorize your REST client with Azure AD using OAuth 2.0.</span></span> <span data-ttu-id="f6fe6-107">Schließlich erstellen Sie eine aussagekräftige URL, um eine Data Warehouse-Ressource aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="f6fe6-107">And finally, you will form a meaningful URL to call a data warehouse resource.</span></span>

[!INCLUDE [reports-credential-reqs](./includes/reports-credential-reqs.md)]

## <a name="authorization"></a><span data-ttu-id="f6fe6-108">Autorisierung</span><span class="sxs-lookup"><span data-stu-id="f6fe6-108">Authorization</span></span>

<span data-ttu-id="f6fe6-109">Azure Active Directory (Azure AD) bietet Ihnen über OAuth 2.0 die Möglichkeit, den Zugriff auf Webanwendungen und Web-APIs in Ihrem Azure AD-Mandanten zu autorisieren.</span><span class="sxs-lookup"><span data-stu-id="f6fe6-109">Azure Active Directory (Azure AD) uses OAuth 2.0 to enable you to authorize access to web applications and web APIs in your Azure AD tenant.</span></span> <span data-ttu-id="f6fe6-110">Dieses Handbuch ist sprachenunabhängig und beschreibt, wie HTTP-Nachrichten gesendet und empfangen werden können, ohne irgendeine unserer Open Source-Bibliotheken zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="f6fe6-110">This guide is language independent, and describes how to send and receive HTTP messages without using any of our open-source libraries.</span></span> <span data-ttu-id="f6fe6-111">Der Codefluss zur Autorisierung mit OAuth 2.0 wird in [section 4.1 (Abschnitt 4.1)](https://tools.ietf.org/html/rfc6749#section-4.1) der OAuth 2.0-Spezifikation beschrieben.</span><span class="sxs-lookup"><span data-stu-id="f6fe6-111">The OAuth 2.0 authorization code flow is described in [section 4.1](https://tools.ietf.org/html/rfc6749#section-4.1) of the OAuth 2.0 specification.</span></span>

<span data-ttu-id="f6fe6-112">Weitere Informationen finden Sie unter [Authorize access to web applications using OAuth 2.0 and Azure Active Directory (Autorisieren des Zugriffs zu Webanwendungen mithilfe von OAuth 2.0 und Azure Active Directory)](https://docs.microsoft.com/azure/active-directory/develop/active-directory-protocols-oauth-code).</span><span class="sxs-lookup"><span data-stu-id="f6fe6-112">For more information, see [Authorize access to web applications using OAuth 2.0 and Azure Active Directory](https://docs.microsoft.com/azure/active-directory/develop/active-directory-protocols-oauth-code).</span></span>

## <a name="api-url-structure"></a><span data-ttu-id="f6fe6-113">API-URL-Struktur</span><span class="sxs-lookup"><span data-stu-id="f6fe6-113">API URL structure</span></span>

<span data-ttu-id="f6fe6-114">Die Endpunkte der Data Warehouse-API lesen die Entitäten für jeden Satz.</span><span class="sxs-lookup"><span data-stu-id="f6fe6-114">The Data Warehouse API endpoints read the entities for each set.</span></span> <span data-ttu-id="f6fe6-115">Die API unterstützt ein **GET** HTTP-Verb und eine Teilmenge der Abfrageoptionen.</span><span class="sxs-lookup"><span data-stu-id="f6fe6-115">The API supports a **GET** HTTP verb, and a subset of query options.</span></span>

<span data-ttu-id="f6fe6-116">Die URL für Intune verwendet das folgende Format:</span><span class="sxs-lookup"><span data-stu-id="f6fe6-116">The URL for Intune uses the following format:</span></span>  
<span data-ttu-id="f6fe6-117">https://fef.{<strong><em>location</em></strong>}.manage.microsoft.com/ReportingService/DataWarehouseFEService/{<strong><em>entity-collection</em></strong>}?api-version={<strong><em>api-version</em></strong>}</span><span class="sxs-lookup"><span data-stu-id="f6fe6-117">https://fef.{<strong><em>location</em></strong>}.manage.microsoft.com/ReportingService/DataWarehouseFEService/{<strong><em>entity-collection</em></strong>}?api-version={<strong><em>api-version</em></strong>}</span></span>

<span data-ttu-id="f6fe6-118">Die URL enthält die folgenden Elemente:</span><span class="sxs-lookup"><span data-stu-id="f6fe6-118">The URL contains the following elements:</span></span>

| <span data-ttu-id="f6fe6-119">Element</span><span class="sxs-lookup"><span data-stu-id="f6fe6-119">Element</span></span> | <span data-ttu-id="f6fe6-120">Beispiel</span><span class="sxs-lookup"><span data-stu-id="f6fe6-120">Example</span></span> | <span data-ttu-id="f6fe6-121">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f6fe6-121">Description</span></span> |
|-------------------|------------|--------------------------------------------------------------------------------------------------------------------|
| <span data-ttu-id="f6fe6-122">location</span><span class="sxs-lookup"><span data-stu-id="f6fe6-122">location</span></span> | <span data-ttu-id="f6fe6-123">msua06</span><span class="sxs-lookup"><span data-stu-id="f6fe6-123">msua06</span></span> | <span data-ttu-id="f6fe6-124">Die Basis-URL kann im Blatt „Data Warehouse API“ im Azure Portal gefunden werden.</span><span class="sxs-lookup"><span data-stu-id="f6fe6-124">The base URL can be found by viewing the Data Warehouse API blade in the Azure portal.</span></span> |
| <span data-ttu-id="f6fe6-125">Entitätssammlung</span><span class="sxs-lookup"><span data-stu-id="f6fe6-125">entity-collection</span></span> | <span data-ttu-id="f6fe6-126">Daten</span><span class="sxs-lookup"><span data-stu-id="f6fe6-126">dates</span></span> | <span data-ttu-id="f6fe6-127">Der Name der OData-Entitätssammlung.</span><span class="sxs-lookup"><span data-stu-id="f6fe6-127">The name of the OData entity collection.</span></span> <span data-ttu-id="f6fe6-128">Weitere Informationen zu Sammlungen und Entitäten im Datenmodell finden Sie unter [Data Model (Datenmodell)](reports-ref-data-model.md).</span><span class="sxs-lookup"><span data-stu-id="f6fe6-128">For more information on collections and entities in the data model, see [Data Model](reports-ref-data-model.md).</span></span> |
| <span data-ttu-id="f6fe6-129">api-version</span><span class="sxs-lookup"><span data-stu-id="f6fe6-129">api-version</span></span> | <span data-ttu-id="f6fe6-130">Beta</span><span class="sxs-lookup"><span data-stu-id="f6fe6-130">beta</span></span> | <span data-ttu-id="f6fe6-131">Die Version ist die Version der API, auf die zugegriffen wird.</span><span class="sxs-lookup"><span data-stu-id="f6fe6-131">Version is the version of the API to access.</span></span> <span data-ttu-id="f6fe6-132">Weitere Informationen finden Sie unter [Version](#API-version-information).</span><span class="sxs-lookup"><span data-stu-id="f6fe6-132">For more information, see [Version](#API-version-information).</span></span> |


## <a name="api-version-information"></a><span data-ttu-id="f6fe6-133">Information zur API-Version</span><span class="sxs-lookup"><span data-stu-id="f6fe6-133">API version information</span></span>

<span data-ttu-id="f6fe6-134">Die aktuelle Version der API ist `beta`.</span><span class="sxs-lookup"><span data-stu-id="f6fe6-134">The current version of the API is: `beta`.</span></span> 

## <a name="odata-query-options"></a><span data-ttu-id="f6fe6-135">OData-Abfrageoptionen</span><span class="sxs-lookup"><span data-stu-id="f6fe6-135">OData query options</span></span>

<span data-ttu-id="f6fe6-136">Die aktuelle Version unterstützt die OData-Abfrageparameter `$filter, $orderby, $select, $skip,` und `$top`.</span><span class="sxs-lookup"><span data-stu-id="f6fe6-136">The current version supports the following OData query parameters: `$filter, $orderby, $select, $skip,` and `$top`.</span></span>