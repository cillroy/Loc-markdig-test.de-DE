---
title: Date Warehouse-API von Intune | Microsoft-Dokumentation
description: "Mithilfe dieser API können Sie Berichte erstellen, die einen Einblick in Ihre mobile Unternehmensumgebung ermöglichen."
keywords: Intune Data Warehouse
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 07/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 701D6CE9-43F6-4A29-8E84-E2B59931C635
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: a0d6bcb4ccac3563dd642ec0ad621645b7053dea
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2017
---
#  <a name="intune-data-warehouse-api"></a><span data-ttu-id="d62bf-104">Intune Data Warehouse-API</span><span class="sxs-lookup"><span data-stu-id="d62bf-104">Intune Data Warehouse API</span></span>

<span data-ttu-id="d62bf-105">Die Data Warehouse-API von Intune ermöglicht es Ihnen, auf Ihre Intune-Daten in einem computerlesbaren Format zuzugreifen, um sie in Ihrem bevorzugten analytischen Tool zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="d62bf-105">The Intune Data Warehouse API lets you access your Intune data in a machine-readable format for use in your favorite analytics tool.</span></span> <span data-ttu-id="d62bf-106">Mithilfe dieser API können Sie Berichte erstellen, die einen Einblick in Ihre mobile Unternehmensumgebung ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="d62bf-106">You can use the API to build reports that provide insight into your enterprise mobile environment.</span></span> <span data-ttu-id="d62bf-107">Die API verwendet das OData-Protokoll, das folgenden Standardmustern folgt:</span><span class="sxs-lookup"><span data-stu-id="d62bf-107">The API uses the OData protocol, which follows standard patterns for:</span></span>

  -   <span data-ttu-id="d62bf-108">Anforderungs- und Antwortheader</span><span class="sxs-lookup"><span data-stu-id="d62bf-108">Request and response headers</span></span>
  -   <span data-ttu-id="d62bf-109">Statuscodes</span><span class="sxs-lookup"><span data-stu-id="d62bf-109">Status codes</span></span>
  -   <span data-ttu-id="d62bf-110">HTTP-Methoden</span><span class="sxs-lookup"><span data-stu-id="d62bf-110">HTTP methods</span></span>
  -   <span data-ttu-id="d62bf-111">URL-Konventionen</span><span class="sxs-lookup"><span data-stu-id="d62bf-111">URL conventions</span></span>
  -   <span data-ttu-id="d62bf-112">Medientypen</span><span class="sxs-lookup"><span data-stu-id="d62bf-112">Media types</span></span>
  -   <span data-ttu-id="d62bf-113">Nutzlastformate</span><span class="sxs-lookup"><span data-stu-id="d62bf-113">Payload formats</span></span>
  -   <span data-ttu-id="d62bf-114">Abfrageoptionen</span><span class="sxs-lookup"><span data-stu-id="d62bf-114">Query options</span></span>

<span data-ttu-id="d62bf-115">OData (Open Data Protocol) erfüllt den OASIS-Standard (Organization for the Advancement of Structured Information Standards), der die bewährten Methoden zum Erstellen und Nutzen von Rest-APIs definiert.</span><span class="sxs-lookup"><span data-stu-id="d62bf-115">The OData (Open Data Protocol) is an Organization for the Advancement of Structured Information Standards (OASIS) standard that defines the best practice for building and consuming RESTful APIs.</span></span> <span data-ttu-id="d62bf-116">Intune Data Warehouse verwendet OData Version 4.0.</span><span class="sxs-lookup"><span data-stu-id="d62bf-116">The Intune Data Warehouse uses OData version 4.0.</span></span>

<span data-ttu-id="d62bf-117">Dieser Abschnitt enthält einen Überblick über die Endpunkte, unterstützten HTTP-Methoden, zurückgegebenen Nutzlastformate und Dokumentation zum Intune Data Warehouse-Datenmodell.</span><span class="sxs-lookup"><span data-stu-id="d62bf-117">This reference section provides an overview of endpoints, supported HTTP methods, return payload formats, and documentation of the Intune Data Warehouse data model.</span></span>

> [!Important]  
> <span data-ttu-id="d62bf-118">Sie können die neuesten Funktionen des Data Warehouse mithilfe der Betaversion ausprobieren.</span><span class="sxs-lookup"><span data-stu-id="d62bf-118">You can try out the latest functionality of the Data Warehouse by using the beta version.</span></span> <span data-ttu-id="d62bf-119">Für die Verwendung die Betaversion muss Ihre URL den Abfrageparameter `api-version=beta` enthalten.</span><span class="sxs-lookup"><span data-stu-id="d62bf-119">To use the beta version, your URL must contain the query parameter `api-version=beta`.</span></span> <span data-ttu-id="d62bf-120">Die Betaversion bietet Features, bevor sie als unterstützter Dienst allgemein verfügbar gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="d62bf-120">The beta version offers features before they are made generally available as a supported service.</span></span> <span data-ttu-id="d62bf-121">Da Intune kontinuierlich neue Features hinzufügt, könnten sich in der Betaversion Verhalten und Datenverträge ändern.</span><span class="sxs-lookup"><span data-stu-id="d62bf-121">As Intune adds new features, the beta version may change behavior and data contracts.</span></span> <span data-ttu-id="d62bf-122">Benutzerdefinierter Code oder Berichtstools, die von der Betaversion abhängig sind, könnten mit laufenden Updates nicht mehr funktionieren.</span><span class="sxs-lookup"><span data-stu-id="d62bf-122">Any custom code or reporting tools dependent on the beta version may break with ongoing updates.</span></span> <!--If you experience problems with the beta service, follow [link to feedback process]() to report the issue or provide feedback.-->

## <a name="odata-custom-client"></a><span data-ttu-id="d62bf-123">Benutzerdefinierter OData-Client</span><span class="sxs-lookup"><span data-stu-id="d62bf-123">OData custom client</span></span>

<span data-ttu-id="d62bf-124">Sie können auf das Intune-Data Warehouse-Datenmodell über RESTful-Endpunkte zugreifen.</span><span class="sxs-lookup"><span data-stu-id="d62bf-124">You can access the Intune Data Warehouse data model through RESTful endpoints.</span></span> <span data-ttu-id="d62bf-125">Um auf Ihre Daten zugreifen zu können, muss sich der Client mithilfe von OAuth 2.0 bei Azure Active Directory (Azure AD) autorisieren.</span><span class="sxs-lookup"><span data-stu-id="d62bf-125">To gain access to your data, your client must authorize with Azure Active Directory (Azure AD) using OAuth 2.0.</span></span> <span data-ttu-id="d62bf-126">Zuerst richten Sie eine Web-App und eine Client-App in Azure ein und erteilen dem Client Berechtigungen.</span><span class="sxs-lookup"><span data-stu-id="d62bf-126">You first set up a web app and a client app in Azure, grant permissions to the client.</span></span> <span data-ttu-id="d62bf-127">Ihr lokaler Client erhält die Autorisierung und kann anschließend mit den Data Warehouse-Endpunkten kommunizieren.</span><span class="sxs-lookup"><span data-stu-id="d62bf-127">Your local client gets authorization and can then communicate with the Data Warehouse endpoints.</span></span>

<span data-ttu-id="d62bf-128">Weitere Informationen finden Sie unter [Abrufen von Daten aus der Data Warehouse-API mit einem REST-Client](reports-proc-data-rest.md).</span><span class="sxs-lookup"><span data-stu-id="d62bf-128">For more information, see [Get data from the Data Warehouse API with a REST client](reports-proc-data-rest.md)</span></span>

> [!Note]  
> <span data-ttu-id="d62bf-129">Codebeispiele finden Sie im [GitHub Intune Data Warehouse repo (GitHub-Repository für Intune Data Warehouse)](https://github.com/Microsoft/Intune-Data-Warehouse) auf GitHub.</span><span class="sxs-lookup"><span data-stu-id="d62bf-129">You can access the [GitHub Intune Data Warehouse repo](https://github.com/Microsoft/Intune-Data-Warehouse) on Github for code samples.</span></span>

## <a name="interacting-with-the-api"></a><span data-ttu-id="d62bf-130">Interagieren mit der API</span><span class="sxs-lookup"><span data-stu-id="d62bf-130">Interacting with the API</span></span>

<span data-ttu-id="d62bf-131">Die API erfordert eine Autorisierung mit Azure AD.</span><span class="sxs-lookup"><span data-stu-id="d62bf-131">The API requires authorization with Azure AD.</span></span> <span data-ttu-id="d62bf-132">Azure AD verwendet OAuth 2.0.</span><span class="sxs-lookup"><span data-stu-id="d62bf-132">Azure AD uses OAuth 2.0.</span></span> <span data-ttu-id="d62bf-133">Nach der Autorisierung können Sie Daten aus der API abrufen, indem Sie ein HTTP GET-Verb verwenden und sich die verfügbar gemachten Entitätsauflistungen wenden.</span><span class="sxs-lookup"><span data-stu-id="d62bf-133">Once authorized, you can get data from the API using an HTTP GET verb and contacting the exposed entity collections.</span></span> <span data-ttu-id="d62bf-134">Weitere Informationen finden Sie hier:</span><span class="sxs-lookup"><span data-stu-id="d62bf-134">For details see:</span></span>

 -  [<span data-ttu-id="d62bf-135">Authorization (Autorisierung)</span><span class="sxs-lookup"><span data-stu-id="d62bf-135">Authorization</span></span>](reports-api-url.md)
 -  [<span data-ttu-id="d62bf-136">API URL Structure (API-URL-Struktur)</span><span class="sxs-lookup"><span data-stu-id="d62bf-136">API URL Structure</span></span>](reports-api-url.md)

## <a name="intune-data-warehouse-data-model"></a><span data-ttu-id="d62bf-137">Intune Data Warehouse-Datenmodell</span><span class="sxs-lookup"><span data-stu-id="d62bf-137">Intune Data Warehouse data model</span></span>

<span data-ttu-id="d62bf-138">OData definiert ein abstraktes Datenmodell und ein Protokoll, mit denen alle Clients auf Informationen zugreifen können, die von einer beliebigen Datenquelle verfügbar gemacht wurden.</span><span class="sxs-lookup"><span data-stu-id="d62bf-138">OData defines an abstract data model and a protocol that let any client access information exposed by any data source.</span></span> <span data-ttu-id="d62bf-139">Das Dokumentationsthema zum Datenmodell enthält eine Erläuterung der Namespaces, Entitäten und zurückgegebenen Objekte im Intune Data Warehouse-Datenmodell.</span><span class="sxs-lookup"><span data-stu-id="d62bf-139">The data model documentation topic contains an explanation of the namespaces, entities, and return objects in the Intune Data Warehouse data model.</span></span> <span data-ttu-id="d62bf-140">Weitere Informationen finden Sie unter [Data Warehouse Data Model (Data Warehouse-Datenmodell)](reports-ref-data-model.md).</span><span class="sxs-lookup"><span data-stu-id="d62bf-140">For more information, see [Data Warehouse Data Model](reports-ref-data-model.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="d62bf-141">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="d62bf-141">Next steps</span></span>

<span data-ttu-id="d62bf-142">Erfahren Sie mehr über die Arbeit mit Azure AD unter [Authentifizierungsszenarios für Azure AD](https://docs.microsoft.com/azure/active-directory/develop/active-directory-authentication-scenarios).</span><span class="sxs-lookup"><span data-stu-id="d62bf-142">Learn more about working with Azure AD by reading the [Authentication Scenarios for Azure AD](https://docs.microsoft.com/azure/active-directory/develop/active-directory-authentication-scenarios).</span></span>

<span data-ttu-id="d62bf-143">OData-Ressourcen finden Sie unter [odata.org](http://www.odata.org).</span><span class="sxs-lookup"><span data-stu-id="d62bf-143">Find OData resources at [odata.org](http://www.odata.org).</span></span>
  
<span data-ttu-id="d62bf-144">Prüfen Sie die Standardversion 4.0 von OData [OData Version 4.0] (http://docs.oasis-open.org/odata/odata/v4.0/odata-v4.0-part1-protocol.html).</span><span class="sxs-lookup"><span data-stu-id="d62bf-144">Review the OData Version 4.0 standard at [OData Version 4.0] (http://docs.oasis-open.org/odata/odata/v4.0/odata-v4.0-part1-protocol.html)</span></span>  
