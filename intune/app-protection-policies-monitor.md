---
title: "Überwachen von App-Schutzrichtlinien"
titleSuffix: Azure portal
description: "Finden Sie heraus, für wie viele Benutzer die Richtlinie gilt, und zeigen Sie weitere Details an.\""
keywords: 
author: erikre
ms.author: erikre
manager: angrobe
ms.date: 01/23/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 9b0afb7d-cd4e-4fc6-83e2-3fc0da461d02
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 0ddb9deaae8fed504daa8e4ba5250208c6458506
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2018
---
# <a name="how-to-monitor-app-protection-policies"></a><span data-ttu-id="e1425-103">Überwachen von App-Schutzrichtlinien</span><span class="sxs-lookup"><span data-stu-id="e1425-103">How to monitor app protection policies</span></span>
[!INCLUDE [azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="e1425-104">**Falls Sie nicht das Azure-Portal verwenden**, wird in diesem Thema erläutert, wie Sie im klassischen Intune-Portal [App-Schutzrichtlinien erstellen](https://docs.microsoft.com/intune-classic/deploy-use/create-and-deploy-mobile-app-management-policies-with-microsoft-intune).</span><span class="sxs-lookup"><span data-stu-id="e1425-104">**If you are not in the Azure portal**, this topic explains [how to create app protection policies](https://docs.microsoft.com/intune-classic/deploy-use/create-and-deploy-mobile-app-management-policies-with-microsoft-intune) in the Intune classic portal.</span></span>


<span data-ttu-id="e1425-105">Sie können den Konformitätsstatus der Verwaltungsrichtlinien für mobile Apps (MAM) überwachen, die Sie auf Benutzer auf dem Blatt „Intune-Schutz für Apps“ im [Azure-Portal](https://portal.azure.com) angewendet haben.</span><span class="sxs-lookup"><span data-stu-id="e1425-105">You can monitor the compliance status of the mobile app management (MAM) policies that you've applied to users at the Intune app protection blade on the [Azure portal](https://portal.azure.com).</span></span> <span data-ttu-id="e1425-106">Sie können Informationen über die Benutzer finden, die von der MAM-Richtlinie betroffen sind, deren Konformitätsstatus sowie Probleme, die bei den Benutzern möglicherweise auftreten.</span><span class="sxs-lookup"><span data-stu-id="e1425-106">You'll be able to find information about the users affected by the MAM policies, its compliance status, and any issues that your users might be experiencing.</span></span>

<span data-ttu-id="e1425-107">Es gibt drei verschiedenen Stellen, an denen der Konformitätsstatus überwacht werden kann:</span><span class="sxs-lookup"><span data-stu-id="e1425-107">There are three different places to monitor the compliance status:</span></span>

-   <span data-ttu-id="e1425-108">Zusammenfassungsansicht</span><span class="sxs-lookup"><span data-stu-id="e1425-108">Summary view</span></span>

-   <span data-ttu-id="e1425-109">Detailansicht</span><span class="sxs-lookup"><span data-stu-id="e1425-109">Detailed view</span></span>

-   <span data-ttu-id="e1425-110">Berichterstellung</span><span class="sxs-lookup"><span data-stu-id="e1425-110">Reporting view</span></span>

## <a name="summary-view"></a><span data-ttu-id="e1425-111">Zusammenfassungsansicht</span><span class="sxs-lookup"><span data-stu-id="e1425-111">Summary view</span></span>

1. <span data-ttu-id="e1425-112">Melden Sie sich beim Azure-Portal an.</span><span class="sxs-lookup"><span data-stu-id="e1425-112">Sign into the Azure portal.</span></span>
2. <span data-ttu-id="e1425-113">Wählen Sie **Weitere Dienste** > **Überwachung und Verwaltung** > **Intune** aus.</span><span class="sxs-lookup"><span data-stu-id="e1425-113">Choose **More Services** > **Monitoring + Management** > **Intune**.</span></span>
3. <span data-ttu-id="e1425-114">Wählen Sie auf dem Blatt **Intune** die Option **Mobile Apps** aus.</span><span class="sxs-lookup"><span data-stu-id="e1425-114">On the **Intune** blade, choose **Mobile apps**.</span></span>
4. <span data-ttu-id="e1425-115">Wählen Sie in der Workload **Mobile Apps** die Option **Überwachen** > **Benutzerstatus bei App-Schutz** aus, um die Zusammenfassungsansicht anzuzeigen:</span><span class="sxs-lookup"><span data-stu-id="e1425-115">In the **Mobile apps** workload, choose **Monitor** > **App protection user status**, to see the summary view:</span></span>

![Kachel „Zusammenfassung“ auf dem Blatt „Mobile Anwendungsverwaltung mit Intune“](./media/app-protection-user-status-summary.png)

-   <span data-ttu-id="e1425-117">**Benutzer:** Die Gesamtzahl von Benutzern in Ihrem Unternehmen, die die eine App verwenden, die einer Richtlinie in einem geschäftlichen Kontext zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="e1425-117">**Users**: The total number of users in your company who are using an app which is associated with a policy in a work context.</span></span>

-   <span data-ttu-id="e1425-118">**VERWALTET DURCH RICHTLINIE**: Die Anzahl von Benutzern, die eine App verwendet haben und denen eine Richtlinie in einem geschäftlichen Kontext zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="e1425-118">**MANAGED BY POLICY**: The number of users who have used an app who have a policy assigned to them in a work context.</span></span>

-   <span data-ttu-id="e1425-119">**KEINE RICHTLINIE**: Die Anzahl von Benutzern, die eine App verwenden, die unter keine Richtlinie in einem geschäftlichen Kontext fallen.</span><span class="sxs-lookup"><span data-stu-id="e1425-119">**NO POLICY**: The number of users who are using an app that is not targeted by any policy in a work context.</span></span> <span data-ttu-id="e1425-120">Sie sollten erwägen, diese Benutzer zur Richtlinie hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="e1425-120">You might consider adding these users to the policy.</span></span>
    > [!NOTE]
    > <span data-ttu-id="e1425-121">Wenn Sie über mehrere Richtlinien pro Plattform verfügen, gilt ein Benutzer als durch eine Richtlinie verwaltet, wenn ihm mindestens eine Richtlinie zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="e1425-121">If you have multiple policies per platform, a user will be considered managed by policy when they have at least one policy assigned to them.</span></span>

- <span data-ttu-id="e1425-122">**Gekennzeichnete Benutzer:** Die Anzahl von Benutzern, die Probleme feststellen.</span><span class="sxs-lookup"><span data-stu-id="e1425-122">**Flagged users**: The number of users who are experiencing issues.</span></span> <span data-ttu-id="e1425-123">Derzeit werden nur Benutzer mit per Jailbreak manipulierten Geräten unter **Gekennzeichnete Benutzer** gemeldet.</span><span class="sxs-lookup"><span data-stu-id="e1425-123">Currently, only users with jailbroken devices are reported under **Flagged users**.</span></span>


## <a name="detailed-view"></a><span data-ttu-id="e1425-124">Detailansicht</span><span class="sxs-lookup"><span data-stu-id="e1425-124">Detailed view</span></span>
<span data-ttu-id="e1425-125">Sie können zur detaillierten Ansicht der Zusammenfassung gelangen, indem Sie auf die Kachel **Benutzerstatus** (basierend auf der Betriebssystemplattform des Geräts) und dann auf die Kachel **Gekennzeichnete Benutzer** klicken.</span><span class="sxs-lookup"><span data-stu-id="e1425-125">You can get to the detailed view of the summary by choosing the **User status** tile (based on device OS platform), and the **Flagged users** tile.</span></span>

### <a name="user-status"></a><span data-ttu-id="e1425-126">Benutzerstatus</span><span class="sxs-lookup"><span data-stu-id="e1425-126">User status</span></span>
<span data-ttu-id="e1425-127">Sie können nach einem einzelnen Benutzer suchen und den Kompatibilitätsstatus für diesen Benutzer überprüfen.</span><span class="sxs-lookup"><span data-stu-id="e1425-127">You can search for a single user and check the compliance status for that user.</span></span> <span data-ttu-id="e1425-128">Auf dem Blatt **App-Berichterstellung** werden für einen ausgewählten Benutzer die folgenden Informationen angezeigt:</span><span class="sxs-lookup"><span data-stu-id="e1425-128">The **App reporting** blade shows the following information for a selected user:</span></span>
- <span data-ttu-id="e1425-129">Geräte, die dem Benutzerkonto zugeordnet sind</span><span class="sxs-lookup"><span data-stu-id="e1425-129">Devices that are associated with the user account</span></span>

- <span data-ttu-id="e1425-130">Apps mit MAM-Richtlinie auf dem Gerät</span><span class="sxs-lookup"><span data-stu-id="e1425-130">Apps with a MAM policy on the device</span></span>

- <span data-ttu-id="e1425-131">Status:</span><span class="sxs-lookup"><span data-stu-id="e1425-131">Status:</span></span>

  - <span data-ttu-id="e1425-132">**Eingecheckt:** Die Richtlinie wurde für den Benutzer bereitgestellt, und die App wurde mindestens einmal im Arbeitskontext verwendet.</span><span class="sxs-lookup"><span data-stu-id="e1425-132">**Checked in**: The policy was deployed to the user, and the app was used in the work context at least once.</span></span>

  - <span data-ttu-id="e1425-133">**Nicht eingecheckt:** Die Richtlinie wurde für den Benutzer bereitgestellt, die App seitdem aber nicht im Arbeitskontext verwendet.</span><span class="sxs-lookup"><span data-stu-id="e1425-133">**Not checked in**: The policy was deployed to the user, but the app has not been used in the work context since then.</span></span>

>[!NOTE]
> <span data-ttu-id="e1425-134">Wenn für den gesuchten Benutzer keine MAM-Richtlinie bereitgestellt wurde, wird Ihnen eine Meldung angezeigt, dass auf den Benutzer keine MAM-Richtlinien angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="e1425-134">If the users you searched for does not have the MAM policy deployed to them, you'll see a message informing you that the user is not targeted by any MAM policies.</span></span>

<span data-ttu-id="e1425-135">Um die Berichterstattung für einen Benutzer anzuzeigen, gehen Sie folgendermaßen vor:</span><span class="sxs-lookup"><span data-stu-id="e1425-135">To see the reporting for a user, follow these steps:</span></span>

1.  <span data-ttu-id="e1425-136">Wählen Sie die Kachel **Zusammenfassung** aus, um einen Benutzer auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="e1425-136">To select a user, choose the **Summary** tile.</span></span>

    ![Screenshot 3](./media/MAM-reporting-6.png)

2. <span data-ttu-id="e1425-138">Wählen Sie auf dem Blatt **App-Berichterstellung**, das geöffnet wird, **Benutzer auswählen**, um nach einem Azure Active Directory-Benutzer zu suchen.</span><span class="sxs-lookup"><span data-stu-id="e1425-138">On the **App reporting** blade that opens, choose **Select user** to search for an Azure Active Directory user.</span></span>

    ![Option „Benutzer auswählen“ auf dem Blatt „App-Berichterstellung“](./media/MAM-reporting-2.png)

3. <span data-ttu-id="e1425-140">Wählen Sie den Benutzer in der Liste aus.</span><span class="sxs-lookup"><span data-stu-id="e1425-140">Select the user from the list.</span></span> <span data-ttu-id="e1425-141">Es werden Details zum Kompatibilitätsstatus für diesen Benutzer angezeigt.</span><span class="sxs-lookup"><span data-stu-id="e1425-141">You will see the details of the compliance status for that user.</span></span>

### <a name="flagged-users"></a><span data-ttu-id="e1425-142">Gekennzeichnete Benutzer</span><span class="sxs-lookup"><span data-stu-id="e1425-142">Flagged users</span></span>
<span data-ttu-id="e1425-143">In der Detailansicht werden die Fehlermeldung, die App, auf die bei Auftreten des Fehlers zugegriffen wurde, die betroffene Betriebssystemplattform des Geräts und ein Zeitstempel angezeigt.</span><span class="sxs-lookup"><span data-stu-id="e1425-143">The detailed view shows the error message, the app that was accessed when the error happened, the device OS platform affected, and a time stamp.</span></span>

## <a name="reporting-view"></a><span data-ttu-id="e1425-144">Berichterstellung</span><span class="sxs-lookup"><span data-stu-id="e1425-144">Reporting view</span></span>

<span data-ttu-id="e1425-145">Sie können die gleichen Berichte in der Detailansicht finden sowie zusätzliche Berichte, die Ihnen mit dem Konformitätsstatus der MAM-Richtlinie weiterhelfen:</span><span class="sxs-lookup"><span data-stu-id="e1425-145">You can find the same reports from the Detailed view, and additional reports to help you with the MAM policy compliance status:</span></span>

![Screenshot 4](./media/MAM-reporting-7.png)

-   <span data-ttu-id="e1425-147">**App protection user report** (Benutzerbericht App-Schutz): Darin werden dieselben Informationen dargestellt, die Sie auch im **Benutzerstatus**-Bericht im Abschnitt „Detailansicht“ weiter hoben sehen können.</span><span class="sxs-lookup"><span data-stu-id="e1425-147">**App protection user report:** It outlines the same information you can find at the **User status** report under the Detailed view section above.</span></span>

-   <span data-ttu-id="e1425-148">**App protection app report** (App-Bericht App-Schutz): Es werden zwei verschiedene Status zum App-Schutz bereitgestellt, die Administratoren auswählen können, bevor sie den Bericht generieren.</span><span class="sxs-lookup"><span data-stu-id="e1425-148">**App protection app report:** It provides two different app protection statuses that admins can select before generating the report.</span></span> <span data-ttu-id="e1425-149">Der Status kann geschützt oder nicht geschützt sein.</span><span class="sxs-lookup"><span data-stu-id="e1425-149">The statuses can be protected or unprotected.</span></span>

    -   <span data-ttu-id="e1425-150">Benutzerstatus für verwaltete MAM-Aktivität (Geschützt): Dieser Bericht zeigt die Aktivität von jeder verwalteten MAM-App auf Benutzerebene.</span><span class="sxs-lookup"><span data-stu-id="e1425-150">User status for managed MAM activity (Protected): This report outlines the activity of each managed MAM app, on a per user basis.</span></span>

        -   <span data-ttu-id="e1425-151">Er zeigt alle Apps, die unter MAM-Richtlinien für jeden Benutzer fallen, und schlüsselt den Status jeder App, die unter MAM-Richtlinien eingecheckt sind oder die unter eine MAM-Richtlinie fallen, doch nie eingecheckt waren.</span><span class="sxs-lookup"><span data-stu-id="e1425-151">It shows all apps targeted by MAM policies for each user, and break down the status of each app as checked in with MAM policies, or that was targeted with a MAM policy but the app was never checked in.</span></span>
<br></br>
    -   <span data-ttu-id="e1425-152">Benutzerstatus für nicht verwaltete MAM-Aktivität (nicht geschützt): Dieser Bericht beschreibt die Aktivitäten auf Benutzerbasis von mit MAM aktivierten Apps, die derzeit nicht verwaltet sind.</span><span class="sxs-lookup"><span data-stu-id="e1425-152">User status for unmanaged MAM activity (Unprotected): This report outlines the activity of MAM-enabled apps that are currently unmanaged, on a per user basis.</span></span> <span data-ttu-id="e1425-153">Dies kann entsprechend der folgenden Gründe auftreten:</span><span class="sxs-lookup"><span data-stu-id="e1425-153">This might happen according to the following reasons:</span></span>

        -   <span data-ttu-id="e1425-154">Diese Apps werden entweder von einem Benutzer oder von einer App verwendet, die derzeit nicht unter eine MAM-Richtlinie fällt.</span><span class="sxs-lookup"><span data-stu-id="e1425-154">These apps are either being used by a user or an app that is not currently targeted by a MAM policy.</span></span>

        -   <span data-ttu-id="e1425-155">Alle Apps sind eingecheckt, erhalten jedoch keine MAM-Richtlinien.</span><span class="sxs-lookup"><span data-stu-id="e1425-155">All apps are checked in, but aren't getting any MAM policies.</span></span>

![Screenshot 2](./media/MAM-reporting-4.png)

## <a name="table-grouping"></a><span data-ttu-id="e1425-157">Tabellengruppierung</span><span class="sxs-lookup"><span data-stu-id="e1425-157">Table grouping</span></span>

<span data-ttu-id="e1425-158">Sobald die Daten im **Benutzerbericht zum App-Schutz** angezeigt werden, können Sie Daten folgendermaßen aggregieren:</span><span class="sxs-lookup"><span data-stu-id="e1425-158">Once the **App protection user report** data shows up, you can aggregate data by the following:</span></span>

- <span data-ttu-id="e1425-159">**Überprüfungsergebnis:** Die Daten werden nach dem App-Schutzstatus – Fehler, Warnung oder Erfolg – gruppiert.</span><span class="sxs-lookup"><span data-stu-id="e1425-159">**Validation result:** The data shows up grouped by app protection status, which can be failure, warning or success.</span></span>
- <span data-ttu-id="e1425-160">**App-Name:** Die Daten werden nach Apps (tatsächlicher App-Name) mit Fehlern, Warnungen oder Erfolgen gruppiert.</span><span class="sxs-lookup"><span data-stu-id="e1425-160">**App name:** The data shows up grouped by apps (the actual app name) with failure, warning or success.</span></span>

## <a name="export-app-protection-activities-to-csv"></a><span data-ttu-id="e1425-161">Exportieren von App-Schutzaktivitäten in eine CSV-Datei</span><span class="sxs-lookup"><span data-stu-id="e1425-161">Export app protection activities to CSV</span></span>

<span data-ttu-id="e1425-162">Sie können alle Aktivitäten im Zusammenhang mit Ihren App-Schutzrichtlinien in eine CSV-Datei exportieren.</span><span class="sxs-lookup"><span data-stu-id="e1425-162">You can export all your app protection policy activities to a single .csv file.</span></span> <span data-ttu-id="e1425-163">Dies kann hilfreich sein, um alle App-Schutzstatus zu analysieren, die von den Benutzern gemeldeten wurden.</span><span class="sxs-lookup"><span data-stu-id="e1425-163">This can be helpful to analyze all the app protection statuses reported from the users.</span></span>

<span data-ttu-id="e1425-164">Gehen Sie zum Generieren des App-Schutzberichts wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="e1425-164">Follow these steps to generate the App protection report:</span></span>

1. <span data-ttu-id="e1425-165">Wählen Sie auf dem Blatt „Mobile Anwendungsverwaltung mit Intune“ den App-Schutzbericht aus.</span><span class="sxs-lookup"><span data-stu-id="e1425-165">On the Intune mobile application management blade, choose App protection report.</span></span>

    ![Screenshot 6](./media/app-protection-report-csv-2.png)

2. <span data-ttu-id="e1425-167">Wählen Sie „Ja“ aus, um den Bericht zu speichern, und wählen Sie dann „Speichern unter“ und den Ordner aus, in dem der Bericht gespeichert werden soll.</span><span class="sxs-lookup"><span data-stu-id="e1425-167">Choose Yes to save your report, then choose Save As and select the folder you want to save the report in.</span></span>

    ![Screenshot 7](./media/app-protection-report-csv-1.png)

## <a name="see-also"></a><span data-ttu-id="e1425-169">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e1425-169">See also</span></span>
[<span data-ttu-id="e1425-170">Verwalten der Datenübertragung zwischen iOS-Apps</span><span class="sxs-lookup"><span data-stu-id="e1425-170">Manage data transfer between iOS apps</span></span>](data-transfer-between-apps-manage-ios.md)

* [<span data-ttu-id="e1425-171">Was Sie erwartet, wenn Ihre Android-App von App-Schutzrichtlinien verwaltet wird</span><span class="sxs-lookup"><span data-stu-id="e1425-171">What to expect when your Android app is managed by app protection policies</span></span>](app-protection-enabled-apps-android.md)
* [<span data-ttu-id="e1425-172">Was Sie erwartet, wenn Ihre iOS-App von App-Schutzrichtlinien verwaltet wird</span><span class="sxs-lookup"><span data-stu-id="e1425-172">What to expect when your iOS app is managed by app protection policies</span></span>](app-protection-enabled-apps-ios.md)
