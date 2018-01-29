---
title: "Änderungsprotokoll für Intune Data Warehouse | Microsoft-Dokumentation"
description: "Eine Liste der Änderungen in der Intune Data Warehouse-API."
keywords: Intune Data Warehouse
author: erikre
ms.author: mabrigg
manager: erikre
ms.date: 12/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: E85DBB2D-67BB-4E10-82D6-E43046B9C43C
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 8582695b94eeeee2e0d219e225139558936e7eea
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2018
---
# <a name="change-log-for-the-intune-data-warehouse-api"></a><span data-ttu-id="8a1e1-104">Änderungsprotokoll für die Intune Data Warehouse-API</span><span class="sxs-lookup"><span data-stu-id="8a1e1-104">Change log for the Intune Data Warehouse API</span></span>

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="8a1e1-105">Bleiben Sie auf dem neuesten Stand bezüglich Updates für Intune Data Warehouse.</span><span class="sxs-lookup"><span data-stu-id="8a1e1-105">Keep current on updates to the Intune Data Warehouse.</span></span>

## <a name="1710"></a><span data-ttu-id="8a1e1-106">1710</span><span class="sxs-lookup"><span data-stu-id="8a1e1-106">1710</span></span>
<span data-ttu-id="8a1e1-107">_Veröffentlicht im November 2017_</span><span class="sxs-lookup"><span data-stu-id="8a1e1-107">_Released November  2017_</span></span>

### <a name="a-new-entity-collection-named-current-user-is-limited-to-currently-active-user-data----1544273---"></a><span data-ttu-id="8a1e1-108">Eine neue Entitätssammlung namens „Aktueller Benutzer“ ist auf die Daten der momentan aktiven Benutzer beschränkt.<!-- 1544273 --></span><span class="sxs-lookup"><span data-stu-id="8a1e1-108">A new entity collection named Current User is limited to currently active user data <!-- 1544273 --></span></span>

<span data-ttu-id="8a1e1-109">Die Entitätssammlung **Benutzer** listet alle Benutzer von Azure Active Directory (Azure AD) mit zugewiesenen Lizenzen in Ihrem Unternehmen auf.</span><span class="sxs-lookup"><span data-stu-id="8a1e1-109">The **Users** entity collection contains all the Azure Active Directory (Azure AD) users with assigned licenses in your enterprise.</span></span> <span data-ttu-id="8a1e1-110">Zu diesen Datensätzen gehören Benutzerzustände während der Datensammlung, selbst wenn der Benutzer entfernt wurde.</span><span class="sxs-lookup"><span data-stu-id="8a1e1-110">These records include user states during the data collection period, even if the user has been removed.</span></span> <span data-ttu-id="8a1e1-111">Beispielsweise kann ein Benutzer in Intune hinzugefügt und dann im Verlauf des letzten Monats entfernt worden sein.</span><span class="sxs-lookup"><span data-stu-id="8a1e1-111">For example, a user may be added to Intune and then removed during the course of the last month.</span></span> <span data-ttu-id="8a1e1-112">Auch wenn dieser Benutzer zum Zeitpunkt der Berichterstellung nicht vorhanden ist, liegen Angaben zu Benutzer und Zustand in den Daten vor.</span><span class="sxs-lookup"><span data-stu-id="8a1e1-112">While this user is not present at the time of the report, the user and state are present in the data.</span></span> <span data-ttu-id="8a1e1-113">Sie können einen Bericht erstellen, der die Dauer der Präsenz des Benutzers in Ihren Daten zeigt.</span><span class="sxs-lookup"><span data-stu-id="8a1e1-113">You could create a report that would show the duration of the user's historic presence in your data.</span></span>

<span data-ttu-id="8a1e1-114">Im Gegensatz dazu enthält die neue Entitätssammlung **Aktueller Benutzer** nur Benutzer, die nicht entfernt wurden.</span><span class="sxs-lookup"><span data-stu-id="8a1e1-114">In contrast, the new **Current User** entity collection only contains users who have not been removed.</span></span> <span data-ttu-id="8a1e1-115">Die Entitätssammlung **Aktueller Benutzer** enthält nur die derzeit aktiven Benutzer.</span><span class="sxs-lookup"><span data-stu-id="8a1e1-115">The **Current User** entity collection only contains currently active users.</span></span> <span data-ttu-id="8a1e1-116">Informationen zur Entitätssammlung **Aktueller Benutzer** finden Sie unter [Referenz für die Entität „Aktueller Benutzer“](reports-ref-current-user.md).</span><span class="sxs-lookup"><span data-stu-id="8a1e1-116">For information about the **current user** entity collection, see [Reference for current user entity](reports-ref-current-user.md).</span></span>

## <a name="1709"></a><span data-ttu-id="8a1e1-117">1709</span><span class="sxs-lookup"><span data-stu-id="8a1e1-117">1709</span></span>
<span data-ttu-id="8a1e1-118">_Veröffentlicht im Oktober 2017_</span><span class="sxs-lookup"><span data-stu-id="8a1e1-118">_Released October  2017_</span></span>

### <a name="user-device-association-entity-collection-added-to-intune-data-warehouse-data-model----1187917---"></a><span data-ttu-id="8a1e1-119">Hinzufügen der Entitätssammlung von Benutzergerätezuordnungen zum Intune Data Warehouse-Datenmodell <!-- 1187917 --></span><span class="sxs-lookup"><span data-stu-id="8a1e1-119">User device association entity collection added to Intune Data Warehouse data model <!-- 1187917 --></span></span>

<span data-ttu-id="8a1e1-120">Mithilfe von Informationen über Benutzergerätezuordnungen können Sie Berichte und Datenvisualisierungen erstellen, die Entitätssammlungen von Benutzern und Geräten zuordnet.</span><span class="sxs-lookup"><span data-stu-id="8a1e1-120">You can now build reports and data visualizations using the user device association information that associates user and device entity collections.</span></span> <span data-ttu-id="8a1e1-121">Auf das Datenmodell kann über die Power BI-Datei (PBIX) zugegriffen werden, die über die Data Warehouse-Seite von Intune, den OData-Endpunkt oder durch die Entwicklung eines benutzerdefinierten Clients abgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="8a1e1-121">The data model can be accessed through the Power BI file (PBIX) retrieved from the Data Warehouse Intune page, through the OData endpoint, or by developing a custom client.</span></span> <span data-ttu-id="8a1e1-122">Weitere Informationen finden Sie unter [Zuordnung der Benutzergeräte](reports-ref-user-device.md).</span><span class="sxs-lookup"><span data-stu-id="8a1e1-122">For more information, see the [User Device Association](reports-ref-user-device.md).</span></span>

### <a name="new-entities-in-the-in-data-warehouse-data-model----1479526--------"></a><span data-ttu-id="8a1e1-123">Neue Entitäten im Data Warehouse-Datenmodell<!-- 1479526 --><!-- --></span><span class="sxs-lookup"><span data-stu-id="8a1e1-123">New entities in the in Data Warehouse data model <!-- 1479526 --><!-- --></span></span>

 - <span data-ttu-id="8a1e1-124">Die Entität [**UserDeviceAssociation**](reports-ref-user-device.md) wurde hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="8a1e1-124">The entity, [**UserDeviceAssociation**](reports-ref-user-device.md), added.</span></span> <span data-ttu-id="8a1e1-125">**UserDeviceAssociation** enthält Zuweisungen von Benutzergeräten in Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="8a1e1-125">**UserDeviceAssociation** contains user device associations in your organization.</span></span> <span data-ttu-id="8a1e1-126">Mithilfe von Informationen über Benutzergerätezuordnungen können Sie Berichte und Datenvisualisierungen erstellen, die Entitätssammlungen von Benutzern und Geräten zuordnet.</span><span class="sxs-lookup"><span data-stu-id="8a1e1-126">You can now build reports and data visualizations using the user device association information that associates user and device entity collections.</span></span>  
 - <span data-ttu-id="8a1e1-127">Die Entität [ **IntuneManagementExtension**](reports-ref-intunemanagementextension.md) wurde hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="8a1e1-127">The entity, [**IntuneManagementExtension**](reports-ref-intunemanagementextension.md), added.</span></span> <span data-ttu-id="8a1e1-128">**IntuneManagementExtension** enthält Entitäten für mobile Geräte zur Nachverfolgung von Informationen, wie z. B. Version und Installationsstatus.</span><span class="sxs-lookup"><span data-stu-id="8a1e1-128">**IntuneManagementExtension** contains entities for mobile devices that track information such as version and installation status.</span></span>

## <a name="next-steps"></a><span data-ttu-id="8a1e1-129">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="8a1e1-129">Next steps</span></span>
 - <span data-ttu-id="8a1e1-130">Erfahren Sie [jede Woche die Neuerungen in Intune](whats-new.md).</span><span class="sxs-lookup"><span data-stu-id="8a1e1-130">Learn [what’s new each week in Intune](whats-new.md).</span></span> <span data-ttu-id="8a1e1-131">Sie erhalten auch Informationen zu bevorstehenden Änderungen, wichtige Hinweise zum Dienst und Informationen zu vorherigen Releases.</span><span class="sxs-lookup"><span data-stu-id="8a1e1-131">You can also find out about upcoming changes, important notices about the service, and information about past releases.</span></span>
 - <span data-ttu-id="8a1e1-132">Lesen Sie den [Microsoft Intune-Blog](http://go.microsoft.com/fwlink/?LinkID=273882).</span><span class="sxs-lookup"><span data-stu-id="8a1e1-132">Read the [Microsoft Intune Blog](http://go.microsoft.com/fwlink/?LinkID=273882).</span></span>
