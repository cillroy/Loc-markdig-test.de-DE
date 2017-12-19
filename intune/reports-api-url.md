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
ms.openlocfilehash: f36327f21fbb2f08906a7621b701a4e6c9deee03
ms.sourcegitcommit: bb2c181fd6de929cf1e5d3856e048d617eb72063
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/20/2017
---
# <a name="intune-data-warehouse-api-endpoint"></a>Endpunkt der Intune Data Warehouse-API

Sie können die Intune-Data Warehouse-API mit einem Konto mit bestimmten rollenbasierten Zugriffssteuerungen und Azure AD-Anmeldeinformationen verwenden. Anschließend autorisieren Sie Ihren REST-Client mithilfe von OAuth 2.0 für Azure AD. Schließlich erstellen Sie eine aussagekräftige URL, um eine Data Warehouse-Ressource aufzurufen.

[!INCLUDE[reports-credential-reqs](./includes/reports-credential-reqs.md)]

## <a name="authorization"></a>Autorisierung

Azure Active Directory (Azure AD) bietet Ihnen über OAuth 2.0 die Möglichkeit, den Zugriff auf Webanwendungen und Web-APIs in Ihrem Azure AD-Mandanten zu autorisieren. Dieses Handbuch ist sprachenunabhängig und beschreibt, wie HTTP-Nachrichten gesendet und empfangen werden können, ohne irgendeine unserer Open Source-Bibliotheken zu verwenden. Der Codefluss zur Autorisierung mit OAuth 2.0 wird in [section 4.1 (Abschnitt 4.1)](https://tools.ietf.org/html/rfc6749#section-4.1) der OAuth 2.0-Spezifikation beschrieben.

Weitere Informationen finden Sie unter [Authorize access to web applications using OAuth 2.0 and Azure Active Directory (Autorisieren des Zugriffs zu Webanwendungen mithilfe von OAuth 2.0 und Azure Active Directory)](https://docs.microsoft.com/azure/active-directory/develop/active-directory-protocols-oauth-code).

## <a name="api-url-structure"></a>API-URL-Struktur

Die Endpunkte der Data Warehouse-API lesen die Entitäten für jeden Satz. Die API unterstützt ein **GET** HTTP-Verb und eine Teilmenge der Abfrageoptionen.

Die URL für Intune verwendet das folgende Format:  
https://fef.{***Speicherort***}.manage.microsoft.com/ReportingService/DataWarehouseFEService/ {***Entitätssammlung***}? api-Version = {***-API-Version***}

Die URL enthält die folgenden Elemente:

| Element | Beispiel | Beschreibung |
|-------------------|------------|--------------------------------------------------------------------------------------------------------------------|
| location | msua06 | Die Basis-URL kann im Blatt „Data Warehouse API“ im Azure Portal gefunden werden. |
| Entitätssammlung | Daten | Der Name der OData-Entitätssammlung. Weitere Informationen zu Sammlungen und Entitäten im Datenmodell finden Sie unter [Data Model (Datenmodell)](reports-ref-data-model.md). |
| api-version | Beta | Die Version ist die Version der API, auf die zugegriffen wird. Weitere Informationen finden Sie unter [Version](#API-version-information). |


## <a name="api-version-information"></a>Information zur API-Version

Die aktuelle Version der API ist `beta`. 

## <a name="odata-query-options"></a>OData-Abfrageoptionen

Die aktuelle Version unterstützt die OData-Abfrageparameter `$filter, $orderby, $select, $skip,` und `$top`.