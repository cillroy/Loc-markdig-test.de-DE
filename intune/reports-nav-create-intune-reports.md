---
title: Verwenden des Data Warehouse von Intune | Microsoft-Dokumentation
description: "Verwenden Sie das Data Warehouse von Intune zum Erstellen von Berichten, die einen Einblick in Ihre mobile Unternehmensumgebung ermöglichen."
keywords: Intune Data Warehouse
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 10/18/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 57019B11-DF9B-4D8A-95FE-254C75398DDE
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: d485f0d53ac57a2f159ebd56b6b3823a8a49d5ad
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2017
---
# <a name="use-the-intune-data-warehouse"></a><span data-ttu-id="85c56-104">Verwenden des Data Warehouse von Intune</span><span class="sxs-lookup"><span data-stu-id="85c56-104">Use the Intune Data Warehouse</span></span>

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="85c56-105">Verwenden Sie das Data Warehouse von Intune zum Erstellen von Berichten, die einen Einblick in Ihre mobile Unternehmensumgebung ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="85c56-105">Use the Intune Data Warehouse to build reports that provide insight into your enterprise mobile environment.</span></span> <span data-ttu-id="85c56-106">Einige der Berichte enthalten beispielsweise:</span><span class="sxs-lookup"><span data-stu-id="85c56-106">For example, some of the reports include:</span></span>
-   <span data-ttu-id="85c56-107">Trend der Benutzer, die sich bei Intune registrieren, sodass Sie Ihre Lizenzkäufe optimieren können</span><span class="sxs-lookup"><span data-stu-id="85c56-107">Trend of users enrolling in Intune so you can optimize your license purchases</span></span>
-   <span data-ttu-id="85c56-108">Strukturplan für App- und BS-Versionen, damit Sie den Zustand von Mobilgeräten überprüfen können</span><span class="sxs-lookup"><span data-stu-id="85c56-108">App and OS versions breakdown so you can review that status of mobile devices</span></span>
-   <span data-ttu-id="85c56-109">Trends zur Konformität der Registrierungen und Geräte, sodass Sie reibungslos Richtlinienaktualisierungen durchführen können</span><span class="sxs-lookup"><span data-stu-id="85c56-109">Enrollment and device compliance trends so you can smoothly roll out policy updates</span></span>

<span data-ttu-id="85c56-110">Das Data Warehouse bietet Ihnen Zugriff auf mehr Informationen über Ihre mobile Umgebung als das Azure-Portal.</span><span class="sxs-lookup"><span data-stu-id="85c56-110">The Data Warehouse provides you access to more information about your mobile environment than the Azure portal.</span></span> <span data-ttu-id="85c56-111">Mit dem Data Warehouse von Intune können Sie auf Folgendes zugreifen:</span><span class="sxs-lookup"><span data-stu-id="85c56-111">With the Intune Data Warehouse you can access:</span></span>

  -  <span data-ttu-id="85c56-112">Verlaufsdaten für Intune</span><span class="sxs-lookup"><span data-stu-id="85c56-112">Historical Intune data</span></span>
  -  <span data-ttu-id="85c56-113">Daten, die täglich aktualisiert werden</span><span class="sxs-lookup"><span data-stu-id="85c56-113">Data refreshed on a daily cadence</span></span>
  -  <span data-ttu-id="85c56-114">Ein Datenmodell, das den OData-Standard verwendet</span><span class="sxs-lookup"><span data-stu-id="85c56-114">A data model using the OData standard</span></span>

> [!Note]
> <span data-ttu-id="85c56-115">Wenn Sie eine hybride Verwaltung mobiler Geräte (mobile device management, MDM) mit System Center Configuration Manager und Microsoft Intune verwenden, sollten Sie Ihre Daten aus SCCM abrufen.</span><span class="sxs-lookup"><span data-stu-id="85c56-115">If you are a using hybrid mobile device management (MDM) with System Center Configuration Manager and Microsoft Intune, you want to retrieve your data from SCCM.</span></span> <span data-ttu-id="85c56-116">Das Intune Data Warehouse enthält nur Intune-Daten.</span><span class="sxs-lookup"><span data-stu-id="85c56-116">The Intune Data Warehouse only contains Intune data.</span></span> <span data-ttu-id="85c56-117">Sie können ein SCCM Power BI-Dashboard für Ihre benutzerdefinierten Berichte verwenden.</span><span class="sxs-lookup"><span data-stu-id="85c56-117">You can use an SCCM Power BI dashboard for your custom reports.</span></span> <span data-ttu-id="85c56-118">Weitere Informationen finden Sie unter [Announcing the Power BI solution template for System Center Configuration Manager (Ankündigung der Power BI-Lösungsvorlage für System Center Configuration Manager)]( https://powerbi.microsoft.com/blog/sccm-solution-template).</span><span class="sxs-lookup"><span data-stu-id="85c56-118">For more information, see "[Announcing the Power BI solution template for System Center Configuration Manager]( https://powerbi.microsoft.com/blog/sccm-solution-template)."</span></span> <span data-ttu-id="85c56-119">und [Create a Power BI report and dashboard (Erstellen eines Power BI-Berichts und -Dashboards)](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/analytics/create-powerbi-report-dashboard).</span><span class="sxs-lookup"><span data-stu-id="85c56-119">and "[Create a Power BI report and dashboard](https://docs.microsoft.com/dynamics365/unified-operations/dev-itpro/analytics/create-powerbi-report-dashboard)."</span></span>


> [!Important]  
> <span data-ttu-id="85c56-120">Sie können die neuesten Funktionen des Data Warehouse mithilfe der Betaversion ausprobieren.</span><span class="sxs-lookup"><span data-stu-id="85c56-120">You can try out the latest functionality of the Data Warehouse by using the beta version.</span></span> <span data-ttu-id="85c56-121">Für die Verwendung die Betaversion muss Ihre URL den Abfrageparameter `api-version=beta` enthalten.</span><span class="sxs-lookup"><span data-stu-id="85c56-121">To use the beta version, your URL must contain the query parameter `api-version=beta`.</span></span> <span data-ttu-id="85c56-122">Die Betaversion bietet Features, bevor sie als unterstützter Dienst allgemein verfügbar gemacht werden.</span><span class="sxs-lookup"><span data-stu-id="85c56-122">The beta version offers features before they are made generally available as a supported service.</span></span> <span data-ttu-id="85c56-123">Da Intune kontinuierlich neue Features hinzufügt, könnten sich in der Betaversion Verhalten und Datenverträge ändern.</span><span class="sxs-lookup"><span data-stu-id="85c56-123">As Intune adds new features, the beta version may change behavior and data contracts.</span></span> <span data-ttu-id="85c56-124">Benutzerdefinierter Code oder Berichtstools, die von der Betaversion abhängig sind, könnten mit laufenden Updates nicht mehr funktionieren.</span><span class="sxs-lookup"><span data-stu-id="85c56-124">Any custom code or reporting tools dependent on the beta version may break with ongoing updates.</span></span>

<span data-ttu-id="85c56-125">**Nächste Schritte**</span><span class="sxs-lookup"><span data-stu-id="85c56-125">**Next steps**</span></span>

- <span data-ttu-id="85c56-126">Rufen Sie einen Link ab und verwenden Sie Power BI, um Einblicke zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="85c56-126">Get a link and use Power BI to get insight.</span></span> <span data-ttu-id="85c56-127">Anweisungen hierzu finden Sie unter [Connect to the Intune Data Warehouse with Power BI (Verbinden mit dem Data Warehouse von Intune mit Power BI)](reports-proc-get-a-link-powerbi.md).</span><span class="sxs-lookup"><span data-stu-id="85c56-127">For instructions, see [Connect to the Intune Data Warehouse with Power BI](reports-proc-get-a-link-powerbi.md).</span></span>
- <span data-ttu-id="85c56-128">Erstellen Sie mit Ihrem Link einen benutzerdefinierten Bericht mit Power BI.</span><span class="sxs-lookup"><span data-stu-id="85c56-128">With your link, create a custom report with Power BI.</span></span> <span data-ttu-id="85c56-129">Weitere Anweisungen hierzu finden Sie unter [Create a report from the OData feed with Power BI (Erstellen eines Berichts aus dem OData-Feed mit Power BI)](reports-proc-create-with-odata.md).</span><span class="sxs-lookup"><span data-stu-id="85c56-129">For instructions, see [Create a report from the OData feed with Power BI](reports-proc-create-with-odata.md).</span></span>
- <span data-ttu-id="85c56-130">Weitere Informationen über die Intune-Data Warehouse-API, das Datenmodell und Beziehungen zwischen Entitäten<!-- , and an example of creating a custom client to retrieve data,--> finden Sie unter [Intune Data Warehouse-API](reports-nav-intune-data-warehouse.md).</span><span class="sxs-lookup"><span data-stu-id="85c56-130">Get more information about the Intune Data Warehouse API, the data model, and relationships between entities<!-- , and an example of creating a custom client to retrieve data,--> see [Intune Data Warehouse API](reports-nav-intune-data-warehouse.md).</span></span>