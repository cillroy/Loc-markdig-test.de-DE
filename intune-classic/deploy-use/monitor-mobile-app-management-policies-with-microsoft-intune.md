---
title: "Überwachen von MAM-Richtlinien mit Microsoft Intune"
description: "Finden Sie heraus, für wie viele Benutzer die Richtlinie gilt, und zeigen Sie weitere Details an."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 02/07/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d3aa6c74-6b5d-4b50-aa66-a040ec44393e
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: de26b7614578b275802ca048ed17bfa5969f0387
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2017
---
# <a name="monitor-app-protection-policies-with-microsoft-intune"></a><span data-ttu-id="b0f58-103">Überprüfen von App-Schutzrichtlinien mit Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="b0f58-103">Monitor app protection policies with Microsoft Intune</span></span>
<span data-ttu-id="b0f58-104">Sie können den Konformitätsstatus der App-Schutzrichtlinien überwachen, die Sie auf Benutzer angewendet haben.</span><span class="sxs-lookup"><span data-stu-id="b0f58-104">You can monitor the compliance status of the app protection policies that you've applied to users.</span></span> <span data-ttu-id="b0f58-105">Sie können Informationen über die Benutzer finden, die von den App-Schutzrichtlinien betroffen sind, deren Konformitätsstatus sowie Probleme, die bei den Benutzern möglicherweise auftreten.</span><span class="sxs-lookup"><span data-stu-id="b0f58-105">You'll be able to find information about the users affected by the app protection policies, its compliance status, and any issues that your users might be experiencing.</span></span>

<span data-ttu-id="b0f58-106">Es gibt drei verschiedenen Stellen, an denen der Konformitätsstatus überwacht werden kann:</span><span class="sxs-lookup"><span data-stu-id="b0f58-106">There are three different places to monitor the compliance status:</span></span>

-   <span data-ttu-id="b0f58-107">Zusammenfassungsansicht</span><span class="sxs-lookup"><span data-stu-id="b0f58-107">Summary view</span></span>

-   <span data-ttu-id="b0f58-108">Detailansicht</span><span class="sxs-lookup"><span data-stu-id="b0f58-108">Detailed view</span></span>

-   <span data-ttu-id="b0f58-109">Berichterstellung</span><span class="sxs-lookup"><span data-stu-id="b0f58-109">Reporting view</span></span>

## <a name="summary-view"></a><span data-ttu-id="b0f58-110">Zusammenfassungsansicht</span><span class="sxs-lookup"><span data-stu-id="b0f58-110">Summary view</span></span>

<span data-ttu-id="b0f58-111">Führen Sie die folgenden drei Schritte aus,um die Ansicht „Zusammenfassung“ zu öffnen:</span><span class="sxs-lookup"><span data-stu-id="b0f58-111">Follow the three steps below to open the Summary view:</span></span>

1. <span data-ttu-id="b0f58-112">Navigieren Sie zum [Azure-Portal](https://portal.azure.com), und geben Sie Ihre-Anmeldeinformationen ein.</span><span class="sxs-lookup"><span data-stu-id="b0f58-112">Go to the [Azure portal](https://portal.azure.com), and enter your credentials.</span></span>
2. <span data-ttu-id="b0f58-113">Wählen Sie **Weitere Dienste** aus, und geben Sie in das Filtertextfeld **Intune** ein.</span><span class="sxs-lookup"><span data-stu-id="b0f58-113">Choose **More Services**, and type **Intune** in the filter textbox.</span></span>
3. <span data-ttu-id="b0f58-114">Wählen Sie **Intune-Schutz für Apps** aus.</span><span class="sxs-lookup"><span data-stu-id="b0f58-114">Choose **Intune App Protection**.</span></span>

<span data-ttu-id="b0f58-115">Auf dem Blatt **Mobile Anwendungsverwaltung mit Intune** sehen Sie eine Zusammenfassung des Kompatibilitätsstatus:</span><span class="sxs-lookup"><span data-stu-id="b0f58-115">On **Intune mobile application management** blade, you can see a summary of the compliance status:</span></span>

![Kachel „Zusammenfassung“ auf dem Blatt „Mobile Anwendungsverwaltung mit Intune“](../media/mam-azure-portal-user-status-summary.png)

-   <span data-ttu-id="b0f58-117">**Benutzer:** Die Gesamtzahl von Benutzern in Ihrem Unternehmen, die die eine App verwenden, die einer Richtlinie in einem geschäftlichen Kontext zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="b0f58-117">**Users**: The total number of users in your company who are using an app which is associated with a policy in a work context.</span></span>

-   <span data-ttu-id="b0f58-118">**VERWALTET DURCH RICHTLINIE**: Die Anzahl von Benutzern, die eine App verwendet haben und denen eine Richtlinie in einem geschäftlichen Kontext zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="b0f58-118">**MANAGED BY POLICY**: The number of users who have used an app who have a policy assigned to them in a work context.</span></span>

-   <span data-ttu-id="b0f58-119">**KEINE RICHTLINIE**: Die Anzahl von Benutzern, die eine App verwenden, die unter keine Richtlinie in einem geschäftlichen Kontext fallen.</span><span class="sxs-lookup"><span data-stu-id="b0f58-119">**NO POLICY**: The number of users who are using an app that is not targeted by any policy in a work context.</span></span> <span data-ttu-id="b0f58-120">Sie sollten erwägen, diese Benutzer zur Richtlinie hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="b0f58-120">You might consider adding these users to the policy.</span></span>
    > [!NOTE]
    > <span data-ttu-id="b0f58-121">Wenn Sie über mehrere Richtlinien pro Plattform verfügen, gilt ein Benutzer als durch eine Richtlinie verwaltet, wenn ihm mindestens eine Richtlinie zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="b0f58-121">If you have multiple policies per platform, a user will be considered managed by policy when they have at least one policy assigned to them.</span></span>

- <span data-ttu-id="b0f58-122">**Gekennzeichnete Benutzer:** Die Anzahl von Benutzern, die Probleme feststellen.</span><span class="sxs-lookup"><span data-stu-id="b0f58-122">**Flagged users**: The number of users who are experiencing issues.</span></span> <span data-ttu-id="b0f58-123">Derzeit werden nur Benutzer mit per Jailbreak manipulierten Geräten unter **Gekennzeichnete Benutzer** gemeldet.</span><span class="sxs-lookup"><span data-stu-id="b0f58-123">Currently, only users with jailbroken devices are reported under **Flagged users**.</span></span>


## <a name="detailed-view"></a><span data-ttu-id="b0f58-124">Detailansicht</span><span class="sxs-lookup"><span data-stu-id="b0f58-124">Detailed view</span></span>
<span data-ttu-id="b0f58-125">Sie können zur detaillierten Ansicht der Zusammenfassung gelangen, indem Sie auf die Kachel **Benutzerstatus** (basierend auf der Betriebssystemplattform des Geräts) und dann auf die Kachel **Gekennzeichnete Benutzer** klicken.</span><span class="sxs-lookup"><span data-stu-id="b0f58-125">You can get to the detailed view of the summary by choosing the **User status** tile (based on device OS platform), and the **Flagged users** tile.</span></span>

### <a name="user-status"></a><span data-ttu-id="b0f58-126">Benutzerstatus</span><span class="sxs-lookup"><span data-stu-id="b0f58-126">User status</span></span>
<span data-ttu-id="b0f58-127">Sie können nach einem einzelnen Benutzer suchen und den Kompatibilitätsstatus für diesen Benutzer überprüfen.</span><span class="sxs-lookup"><span data-stu-id="b0f58-127">You can search for a single user and check the compliance status for that user.</span></span> <span data-ttu-id="b0f58-128">Auf dem Blatt **App-Berichterstellung** werden für einen ausgewählten Benutzer die folgenden Informationen angezeigt:</span><span class="sxs-lookup"><span data-stu-id="b0f58-128">The **App reporting** blade shows the following information for a selected user:</span></span>
- <span data-ttu-id="b0f58-129">Geräte, die dem Benutzerkonto zugeordnet sind</span><span class="sxs-lookup"><span data-stu-id="b0f58-129">Devices that are associated with the user account</span></span>

- <span data-ttu-id="b0f58-130">Apps mit einer App-Schutzrichtlinie auf dem Gerät</span><span class="sxs-lookup"><span data-stu-id="b0f58-130">Apps with an app protection policy on the device</span></span>

- <span data-ttu-id="b0f58-131">Status:</span><span class="sxs-lookup"><span data-stu-id="b0f58-131">Status:</span></span>

  - <span data-ttu-id="b0f58-132">**Eingecheckt:** Die Richtlinie wurde für den Benutzer bereitgestellt, und die App wurde mindestens einmal im Arbeitskontext verwendet.</span><span class="sxs-lookup"><span data-stu-id="b0f58-132">**Checked in**: The policy was deployed to the user, and the app was used in the work context at least once.</span></span>

  - <span data-ttu-id="b0f58-133">**Nicht eingecheckt:** Die Richtlinie wurde für den Benutzer bereitgestellt, die App seitdem aber nicht im Arbeitskontext verwendet.</span><span class="sxs-lookup"><span data-stu-id="b0f58-133">**Not checked in**: The policy was deployed to the user, but the app has not been used in the work context since then.</span></span>

>[!NOTE]
> <span data-ttu-id="b0f58-134">Wenn für den gesuchten Benutzer keine App-Schutzrichtlinie bereitgestellt wurde, wird Ihnen eine Meldung angezeigt, dass auf den Benutzer keine App-Schutzrichtlinien angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="b0f58-134">If the users you searched for does not have the app protection policy deployed to them, you'll see a message informing you that the user is not targeted by any app protection policies.</span></span>

<span data-ttu-id="b0f58-135">Um die Berichterstattung für einen Benutzer anzuzeigen, gehen Sie folgendermaßen vor:</span><span class="sxs-lookup"><span data-stu-id="b0f58-135">To see the reporting for a user, follow these steps:</span></span>

1.  <span data-ttu-id="b0f58-136">Wählen Sie die Kachel **Zusammenfassung** aus, um einen Benutzer auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="b0f58-136">To select a user, choose the **Summary** tile.</span></span>

    ![Screenshot 3](../media/MAM-reporting-6.png)

2. <span data-ttu-id="b0f58-138">Wählen Sie auf dem Blatt **App-Berichterstellung**, das geöffnet wird, **Benutzer auswählen**, um nach einem Azure Active Directory-Benutzer zu suchen.</span><span class="sxs-lookup"><span data-stu-id="b0f58-138">On the **App reporting** blade that opens, choose **Select user** to search for an Azure Active Directory user.</span></span>

    ![Option „Benutzer auswählen“ auf dem Blatt „App-Berichterstellung“](../media/MAM-reporting-2.png)

3. <span data-ttu-id="b0f58-140">Wählen Sie den Benutzer in der Liste aus.</span><span class="sxs-lookup"><span data-stu-id="b0f58-140">Select the user from the list.</span></span> <span data-ttu-id="b0f58-141">Es werden Details zum Kompatibilitätsstatus für diesen Benutzer angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b0f58-141">You will see the details of the compliance status for that user.</span></span>

### <a name="flagged-users"></a><span data-ttu-id="b0f58-142">Gekennzeichnete Benutzer</span><span class="sxs-lookup"><span data-stu-id="b0f58-142">Flagged users</span></span>
<span data-ttu-id="b0f58-143">In der Detailansicht werden die Fehlermeldung, die App, auf die bei Auftreten des Fehlers zugegriffen wurde, die betroffene Betriebssystemplattform des Geräts und ein Zeitstempel angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b0f58-143">The detailed view shows the error message, the app that was accessed when the error happened, the device OS platform affected, and a time stamp.</span></span>

## <a name="reporting-view"></a><span data-ttu-id="b0f58-144">Berichterstellung</span><span class="sxs-lookup"><span data-stu-id="b0f58-144">Reporting view</span></span>

<span data-ttu-id="b0f58-145">Sie können die gleichen Berichte in der Detailansicht finden sowie zusätzliche Berichte, die Ihnen mit dem Konformitätsstatus der App-Schutzrichtlinie weiterhelfen:</span><span class="sxs-lookup"><span data-stu-id="b0f58-145">You can find the same reports from the Detailed view, and additional reports to help you with the app protection policy compliance status:</span></span>

![Screenshot 4](../media/MAM-reporting-7.png)

-   <span data-ttu-id="b0f58-147">**App protection user report** (Benutzerbericht App-Schutz): Darin werden dieselben Informationen dargestellt, die Sie auch im **Benutzerstatus**-Bericht im Abschnitt „Detailansicht“ weiter hoben sehen können.</span><span class="sxs-lookup"><span data-stu-id="b0f58-147">**App protection user report:** It outlines the same information you can find at the **User status** report under the Detailed view section above.</span></span>

-   <span data-ttu-id="b0f58-148">**App protection app report** (App-Bericht App-Schutz): Es werden zwei verschiedene Status zum App-Schutz bereitgestellt, die Administratoren auswählen können, bevor sie den Bericht generieren.</span><span class="sxs-lookup"><span data-stu-id="b0f58-148">**App protection app report:** It provides two different app protection statuses that admins can select before generating the report.</span></span> <span data-ttu-id="b0f58-149">Der Status kann geschützt oder nicht geschützt sein.</span><span class="sxs-lookup"><span data-stu-id="b0f58-149">The statuses can be protected or unprotected.</span></span>

    -   <span data-ttu-id="b0f58-150">Benutzerstatus für verwaltete MAM-Aktivität (Geschützt): Dieser Bericht zeigt die Aktivität von jeder verwalteten MAM-App auf Benutzerebene.</span><span class="sxs-lookup"><span data-stu-id="b0f58-150">User status for managed MAM activity (Protected): This report outlines the activity of each managed MAM app, on a per user basis.</span></span>

        -   <span data-ttu-id="b0f58-151">Er zeigt alle Apps, die unter App-Schutzrichtlinien für jeden Benutzer fallen, und schlüsselt den Status jeder App auf, die unter den App-Schutzrichtlinien eingecheckt sind oder die unter eine App-Schutzrichtlinie fallen, doch nie eingecheckt waren.</span><span class="sxs-lookup"><span data-stu-id="b0f58-151">It shows all apps targeted by app protection policies for each user, and break down the status of each app as checked in with app protection policies, or that was targeted with an app protection policy but the app was never checked in.</span></span>
<br></br>
    -   <span data-ttu-id="b0f58-152">Benutzerstatus für nicht verwaltete MAM-Aktivität (nicht geschützt): Dieser Bericht beschreibt die Aktivitäten auf Benutzerbasis von mit MAM aktivierten Apps, die derzeit nicht verwaltet sind.</span><span class="sxs-lookup"><span data-stu-id="b0f58-152">User status for unmanaged MAM activity (Unprotected): This report outlines the activity of MAM-enabled apps that are currently unmanaged, on a per user basis.</span></span> <span data-ttu-id="b0f58-153">Dies kann entsprechend der folgenden Gründe auftreten:</span><span class="sxs-lookup"><span data-stu-id="b0f58-153">This might happen according to the following reasons:</span></span>

        -   <span data-ttu-id="b0f58-154">Diese Apps werden entweder von einem Benutzer oder einer App verwendet, die derzeit nicht unter eine App-Schutzrichtlinie fällt.</span><span class="sxs-lookup"><span data-stu-id="b0f58-154">These apps are either being used by a user or an app that is not currently targeted by an app protection policy.</span></span>

        -   <span data-ttu-id="b0f58-155">Alle Apps sind eingecheckt, erhalten jedoch keine App-Schutzrichtlinien.</span><span class="sxs-lookup"><span data-stu-id="b0f58-155">All apps are checked in, but aren't getting any app protection policies.</span></span>

![Screenshot 2](../media/MAM-reporting-4.png)

## <a name="table-grouping"></a><span data-ttu-id="b0f58-157">Tabellengruppierung</span><span class="sxs-lookup"><span data-stu-id="b0f58-157">Table grouping</span></span>

<span data-ttu-id="b0f58-158">Sobald die Daten im **Benutzerbericht zum App-Schutz** angezeigt werden, können Sie Daten folgendermaßen aggregieren:</span><span class="sxs-lookup"><span data-stu-id="b0f58-158">Once the **App protection user report** data shows up, you can aggregate data by the following:</span></span>

- <span data-ttu-id="b0f58-159">**Überprüfungsergebnis:** Die Daten werden nach dem App-Schutzstatus – Fehler, Warnung oder Erfolg – gruppiert.</span><span class="sxs-lookup"><span data-stu-id="b0f58-159">**Validation result:** The data shows up grouped by app protection status, which can be failure, warning or success.</span></span>
- <span data-ttu-id="b0f58-160">**App-Name:** Die Daten werden nach Apps (tatsächlicher App-Name) mit Fehlern, Warnungen oder Erfolgen gruppiert.</span><span class="sxs-lookup"><span data-stu-id="b0f58-160">**App name:** The data shows up grouped by apps (the actual app name) with failure, warning or success.</span></span>

## <a name="export-app-protection-activities-to-csv"></a><span data-ttu-id="b0f58-161">Exportieren von App-Schutzaktivitäten in eine CSV-Datei</span><span class="sxs-lookup"><span data-stu-id="b0f58-161">Export app protection activities to CSV</span></span>

<span data-ttu-id="b0f58-162">Sie können alle Aktivitäten im Zusammenhang mit Ihren App-Schutzrichtlinien in eine CSV-Datei exportieren.</span><span class="sxs-lookup"><span data-stu-id="b0f58-162">You can export all your app protection policy activities to a single .csv file.</span></span> <span data-ttu-id="b0f58-163">Dies kann hilfreich sein, um alle App-Schutzstatus zu analysieren, die von den Benutzern gemeldeten wurden.</span><span class="sxs-lookup"><span data-stu-id="b0f58-163">This can be helpful to analyze all the app protection statuses reported from the users.</span></span>

<span data-ttu-id="b0f58-164">Gehen Sie zum Generieren des App-Schutzberichts wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="b0f58-164">Follow these steps to generate the App protection report:</span></span>

1. <span data-ttu-id="b0f58-165">Wählen Sie auf dem Blatt „Mobile Anwendungsverwaltung mit Intune“ den App-Schutzbericht aus.</span><span class="sxs-lookup"><span data-stu-id="b0f58-165">On the Intune mobile application management blade, choose App protection report.</span></span>

    ![Screenshot 6](../media/app-protection-report-csv-2.png)

2. <span data-ttu-id="b0f58-167">Wählen Sie „Ja“ aus, um den Bericht zu speichern, und wählen Sie dann „Speichern unter“ und den Ordner aus, in dem der Bericht gespeichert werden soll.</span><span class="sxs-lookup"><span data-stu-id="b0f58-167">Choose Yes to save your report, then choose Save As and select the folder you want to save the report in.</span></span>

    ![Screenshot 7](../media/app-protection-report-csv-1.png)

## <a name="see-also"></a><span data-ttu-id="b0f58-169">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="b0f58-169">See also</span></span>
[<span data-ttu-id="b0f58-170">Verwalten der Datenübertragung zwischen iOS-Apps</span><span class="sxs-lookup"><span data-stu-id="b0f58-170">Manage data transfer between iOS apps</span></span>](manage-data-transfer-between-ios-apps-with-microsoft-intune.md)

* [<span data-ttu-id="b0f58-171">Was Sie erwartet, wenn Ihre Android-App von App-Schutzrichtlinien verwaltet wird</span><span class="sxs-lookup"><span data-stu-id="b0f58-171">What to expect when your Android app is managed by app protection policies</span></span>](/intune/end-user-mam-apps-android)
* [<span data-ttu-id="b0f58-172">Was Sie erwartet, wenn Ihre iOS-App von App-Schutzrichtlinien verwaltet wird</span><span class="sxs-lookup"><span data-stu-id="b0f58-172">What to expect when your iOS app is managed by app protection policies</span></span>](/intune/end-user-mam-apps-ios)
