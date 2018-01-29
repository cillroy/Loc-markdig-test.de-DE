---
title: "Überwachen von App-Informationen und -Zuweisungen"
titlesuffix: Azure portal
description: "Nachdem Sie Benutzern oder Geräten eine App zugewiesen haben, können Sie mithilfe dieser Informationen den Status der App überwachen."
keywords: 
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 11/21/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 64e5133d-1e23-4ee6-b556-f5d32c0e95da
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 8d8a77c472e9d62aa92ac10278fa895a2343de3f
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2018
---
# <a name="how-to-monitor-app-information-and-assignments-with-microsoft-intune"></a><span data-ttu-id="ebad4-103">Überwachen von App-Informationen und -Zuweisungen mit Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="ebad4-103">How to monitor app information and assignments with Microsoft Intune</span></span>

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="ebad4-104">Intune bietet eine Reihe von Möglichkeiten, mit denen Sie die Eigenschaften von verwalteten Apps sowie deren Zuweisungsstatus überwachen können.</span><span class="sxs-lookup"><span data-stu-id="ebad4-104">Intune provides a number of ways in which you can monitor the properties of apps you manage, as well as their assignment status.</span></span>

1. <span data-ttu-id="ebad4-105">Melden Sie sich im Azure-Portal an.</span><span class="sxs-lookup"><span data-stu-id="ebad4-105">Sign in to the Azure portal.</span></span>
2. <span data-ttu-id="ebad4-106">Wählen Sie **Weitere Dienste** > **Überwachung und Verwaltung** + **Intune** aus.</span><span class="sxs-lookup"><span data-stu-id="ebad4-106">Choose **More Services** > **Monitoring + Management** + **Intune**.</span></span>
3. <span data-ttu-id="ebad4-107">Klicken Sie in der Workload **Mobile Apps** auf **Apps** in der Gruppe **Verwalten**.</span><span class="sxs-lookup"><span data-stu-id="ebad4-107">In the **Mobile Apps** workload, choose **Apps** in the **Manage** group.</span></span>
5. <span data-ttu-id="ebad4-108">Wählen Sie in der Liste auf dem Blatt „Apps“ eine App aus.</span><span class="sxs-lookup"><span data-stu-id="ebad4-108">In the list of apps blade, choose an app.</span></span> <span data-ttu-id="ebad4-109">Ihnen wird dann das Blatt <*App-Name*> **Geräteinstallationsstatus** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ebad4-109">You'll then see the <*app name*> **Device install status** blade.</span></span>

## <a name="app-overview-blade"></a><span data-ttu-id="ebad4-110">Übersicht über das Blatt „App“</span><span class="sxs-lookup"><span data-stu-id="ebad4-110">App overview blade</span></span>

<span data-ttu-id="ebad4-111">Auf dem Blatt <*App-Name*> **Geräteinstallationsstatus** können Sie Details zum Status einer App in Ihrer Umgebung überprüfen.</span><span class="sxs-lookup"><span data-stu-id="ebad4-111">You can use the <*app name*> **Device install status** blade to review details about the status of an app in your environment.</span></span>

### <a name="essentials"></a><span data-ttu-id="ebad4-112">Essentials</span><span class="sxs-lookup"><span data-stu-id="ebad4-112">Essentials</span></span>

<span data-ttu-id="ebad4-113">Der Abschnitt **Zusammenfassung** enthält die folgenden Informationen zur App:</span><span class="sxs-lookup"><span data-stu-id="ebad4-113">The **Essentials** section contains the following information about the app:</span></span>

 - <span data-ttu-id="ebad4-114">**Herausgeber**</span><span class="sxs-lookup"><span data-stu-id="ebad4-114">**Publisher**</span></span>  
<span data-ttu-id="ebad4-115">Herausgeber der App</span><span class="sxs-lookup"><span data-stu-id="ebad4-115">Publisher of the app.</span></span>
 - <span data-ttu-id="ebad4-116">**Betriebssystem**</span><span class="sxs-lookup"><span data-stu-id="ebad4-116">**Operating system**</span></span>  
<span data-ttu-id="ebad4-117">Das Betriebssystem der App (Windows, iOS, Android usw.)</span><span class="sxs-lookup"><span data-stu-id="ebad4-117">The operating system of the app  (Windows, iOS, Android, etc.)</span></span>
 - <span data-ttu-id="ebad4-118">**Erstellen**</span><span class="sxs-lookup"><span data-stu-id="ebad4-118">**Create**</span></span>  
<span data-ttu-id="ebad4-119">Die Uhrzeit, zu der diese Revision erstellt wurde</span><span class="sxs-lookup"><span data-stu-id="ebad4-119">The time when this revision was created.</span></span>
 - <span data-ttu-id="ebad4-120">**Zugewiesen**</span><span class="sxs-lookup"><span data-stu-id="ebad4-120">**Assigned**</span></span>  
<span data-ttu-id="ebad4-121">**Nein** oder **Ja**, wenn die App zugewiesen wurde.</span><span class="sxs-lookup"><span data-stu-id="ebad4-121">**Yes** or **No** if the app has been assigned.</span></span>

### <a name="status"></a><span data-ttu-id="ebad4-122">Status</span><span class="sxs-lookup"><span data-stu-id="ebad4-122">Status</span></span>
<span data-ttu-id="ebad4-123">Jedes Diagramm zeigt die Zähler für die folgenden Status:</span><span class="sxs-lookup"><span data-stu-id="ebad4-123">Each graph shows counts for the following status:</span></span>

 - <span data-ttu-id="ebad4-124">**Installiert**</span><span class="sxs-lookup"><span data-stu-id="ebad4-124">**Installed**</span></span>  
<span data-ttu-id="ebad4-125">Die Anzahl der installierten Apps.</span><span class="sxs-lookup"><span data-stu-id="ebad4-125">The number of apps installed.</span></span>
 - <span data-ttu-id="ebad4-126">**Nicht installiert**</span><span class="sxs-lookup"><span data-stu-id="ebad4-126">**Not Installed**</span></span>  
<span data-ttu-id="ebad4-127">Die Anzahl der nicht installierten Apps.</span><span class="sxs-lookup"><span data-stu-id="ebad4-127">The number of apps not installed.</span></span>
 - <span data-ttu-id="ebad4-128">**Installation steht aus**</span><span class="sxs-lookup"><span data-stu-id="ebad4-128">**Install Pending**</span></span>  
<span data-ttu-id="ebad4-129">Die Anzahl der Apps, deren Installation bevorsteht.</span><span class="sxs-lookup"><span data-stu-id="ebad4-129">The number of apps in the process of being installed.</span></span>
 - <span data-ttu-id="ebad4-130">**Fehlgeschlagen**</span><span class="sxs-lookup"><span data-stu-id="ebad4-130">**Failed**</span></span>  
<span data-ttu-id="ebad4-131">Die Anzahl nicht erfolgreicher Installationen.</span><span class="sxs-lookup"><span data-stu-id="ebad4-131">The number of failed installations.</span></span>
 - <span data-ttu-id="ebad4-132">**Unbekannt**</span><span class="sxs-lookup"><span data-stu-id="ebad4-132">**Unknown**</span></span>  
<span data-ttu-id="ebad4-133">Die Anzahl der Apps mit unbekanntem Status.</span><span class="sxs-lookup"><span data-stu-id="ebad4-133">The number of apps with an unknown status.</span></span>

### <a name="device-status"></a><span data-ttu-id="ebad4-134">Gerätestatus</span><span class="sxs-lookup"><span data-stu-id="ebad4-134">Device status</span></span>

<span data-ttu-id="ebad4-135">Der Gerätestatus.</span><span class="sxs-lookup"><span data-stu-id="ebad4-135">Device status.</span></span> <span data-ttu-id="ebad4-136">Ein Ringdiagramm, in dem den Installationsstatus der App auf Geräten angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="ebad4-136">A donut chart that displays the install status of the app on devices.</span></span> <span data-ttu-id="ebad4-137">Klicken Sie auf das Diagramm, um eine Liste mit Details zum Gerätestatus zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="ebad4-137">Click the graph to open a list of details about the device status.</span></span> <span data-ttu-id="ebad4-138">Die Tabelle mit den Details enthält die folgenden Spalten:</span><span class="sxs-lookup"><span data-stu-id="ebad4-138">The details table includes the following columns:</span></span>

 - <span data-ttu-id="ebad4-139">**Gerätename**</span><span class="sxs-lookup"><span data-stu-id="ebad4-139">**Device name**</span></span>  
<span data-ttu-id="ebad4-140">Der Name des Geräts auf Plattformen, die das Benennen von Geräten ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="ebad4-140">Name of the device on platforms that allow naming a device.</span></span> <span data-ttu-id="ebad4-141">Auf anderen Plattformen wird von Intune einen Namen aus anderen Eigenschaften erstellt.</span><span class="sxs-lookup"><span data-stu-id="ebad4-141">On other platforms, Intune creates a name from other properties.</span></span> <span data-ttu-id="ebad4-142">Dieses Attribut kann nicht für alle Geräte zur Verfügung stehen.</span><span class="sxs-lookup"><span data-stu-id="ebad4-142">This attribute cannot be available for all devices.</span></span>
 - <span data-ttu-id="ebad4-143">**Benutzername**</span><span class="sxs-lookup"><span data-stu-id="ebad4-143">**User name**</span></span>  
<span data-ttu-id="ebad4-144">Der Name des Benutzers.</span><span class="sxs-lookup"><span data-stu-id="ebad4-144">The name of the user.</span></span>
 - <span data-ttu-id="ebad4-145">**Plattform**</span><span class="sxs-lookup"><span data-stu-id="ebad4-145">**Platform**</span></span>  
<span data-ttu-id="ebad4-146">Das Betriebssystem des Geräts (Windows, iOS, Android usw.)</span><span class="sxs-lookup"><span data-stu-id="ebad4-146">The operating system of the device (Windows, iOS, Android, etc.)</span></span>
 - <span data-ttu-id="ebad4-147">**Version**</span><span class="sxs-lookup"><span data-stu-id="ebad4-147">**Version**</span></span>  
<span data-ttu-id="ebad4-148">Die Versionsnummer der App.</span><span class="sxs-lookup"><span data-stu-id="ebad4-148">The version number of the app.</span></span> <span data-ttu-id="ebad4-149">Für branchenspezifische Apps wird die vollständige Versionsnummer der App angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ebad4-149">For line-of-business apps the full version number of the app is displayed.</span></span> <span data-ttu-id="ebad4-150">Die vollständige Versionsnummer identifiziert ein bestimmtes Release der App.</span><span class="sxs-lookup"><span data-stu-id="ebad4-150">The full version number identifies a specific release of the app.</span></span> <span data-ttu-id="ebad4-151">Die Nummer wird als _Version_(_Build_) angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ebad4-151">The number appears as _Version_(_Build_).</span></span> <span data-ttu-id="ebad4-152">Beispielsweise 2.2(2.2.17560800)</span><span class="sxs-lookup"><span data-stu-id="ebad4-152">For example, 2.2(2.2.17560800)</span></span>
 - <span data-ttu-id="ebad4-153">**Status**</span><span class="sxs-lookup"><span data-stu-id="ebad4-153">**Status**</span></span>  
<span data-ttu-id="ebad4-154">Der Status der App.</span><span class="sxs-lookup"><span data-stu-id="ebad4-154">The status of the app.</span></span>
 - <span data-ttu-id="ebad4-155">**Statusdetails**</span><span class="sxs-lookup"><span data-stu-id="ebad4-155">**Status details**</span></span>  
<span data-ttu-id="ebad4-156">Details zum Status.</span><span class="sxs-lookup"><span data-stu-id="ebad4-156">Details of the status.</span></span>
 - <span data-ttu-id="ebad4-157">**Letztes Einchecken**</span><span class="sxs-lookup"><span data-stu-id="ebad4-157">**Last check-in**</span></span>  
<span data-ttu-id="ebad4-158">Datum der letzten Synchronisierung mit Intune des Geräts.</span><span class="sxs-lookup"><span data-stu-id="ebad4-158">Date of the device last sync with Intune.</span></span>


### <a name="user-status"></a><span data-ttu-id="ebad4-159">Benutzerstatus</span><span class="sxs-lookup"><span data-stu-id="ebad4-159">User status</span></span>

<span data-ttu-id="ebad4-160">Der Status des Benutzers.</span><span class="sxs-lookup"><span data-stu-id="ebad4-160">User status.</span></span> <span data-ttu-id="ebad4-161">Ein Ringdiagramm, in dem den Installationsstatus der App für Benutzer angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="ebad4-161">A donut chart that displays the install status of the app for users.</span></span> <span data-ttu-id="ebad4-162">Klicken Sie auf das Diagramm, um eine Liste mit Details zum Gerätestatus zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="ebad4-162">Click the graph to open a list of details about the device status.</span></span> <span data-ttu-id="ebad4-163">Die Tabelle mit den Details enthält die folgenden Spalten:</span><span class="sxs-lookup"><span data-stu-id="ebad4-163">The details table includes the following columns:</span></span>
 - <span data-ttu-id="ebad4-164">**Name**</span><span class="sxs-lookup"><span data-stu-id="ebad4-164">**Name**</span></span>  
<span data-ttu-id="ebad4-165">Der Name des Benutzers in Azure AD.</span><span class="sxs-lookup"><span data-stu-id="ebad4-165">The name of the user in Azure AD.</span></span>
 - <span data-ttu-id="ebad4-166">**Benutzername**</span><span class="sxs-lookup"><span data-stu-id="ebad4-166">**User name**</span></span>  
<span data-ttu-id="ebad4-167">Der eindeutige Name des Benutzers.</span><span class="sxs-lookup"><span data-stu-id="ebad4-167">The unique name of the user.</span></span>
 - <span data-ttu-id="ebad4-168">**Installationen**</span><span class="sxs-lookup"><span data-stu-id="ebad4-168">**Installations**</span></span>  
<span data-ttu-id="ebad4-169">Anzahl der installierten Apps, die vom Benutzer verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="ebad4-169">Number of apps installs used by the user.</span></span>
 - <span data-ttu-id="ebad4-170">**Fehler**</span><span class="sxs-lookup"><span data-stu-id="ebad4-170">**Failures**</span></span>  
<span data-ttu-id="ebad4-171">Anzahl der nicht erfolgreichen Installationen des Benutzers.</span><span class="sxs-lookup"><span data-stu-id="ebad4-171">Number of failed install by the user.</span></span>
 - <span data-ttu-id="ebad4-172">**Nicht installiert**</span><span class="sxs-lookup"><span data-stu-id="ebad4-172">**Not installed**</span></span>  
<span data-ttu-id="ebad4-173">Anzahl der nicht vom Benutzer installierten Apps.</span><span class="sxs-lookup"><span data-stu-id="ebad4-173">Number of apps not installed by the user.</span></span>


## <a name="next-steps"></a><span data-ttu-id="ebad4-174">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="ebad4-174">Next steps</span></span>

<span data-ttu-id="ebad4-175">Weitere Informationen zum Arbeiten mit Ihren Intune-Daten finden Sie unter [Verwenden des Data Warehouse von Intune](reports-nav-create-intune-reports.md).</span><span class="sxs-lookup"><span data-stu-id="ebad4-175">To learn more about working with your Intune data, see the [Use the Intune Data Warehouse](reports-nav-create-intune-reports.md).</span></span>