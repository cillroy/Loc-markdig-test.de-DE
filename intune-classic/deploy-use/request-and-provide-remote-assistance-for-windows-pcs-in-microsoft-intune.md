---
title: "Anfordern und Bereitstellen von Remoteunterstützung für Windows-PCs"
description: "Beschreibt Schritte für Endbenutzer und IT-Administratoren zur Bereitstellung von Remoteunterstützung für Windows-Desktops, die als PCs verwaltet werden, und zum Remotestarten eines PCs."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 12/15/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c2654491-5144-408a-a45a-644eb91ac1bb
ms.reviewer: owenyen
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: f8cddd66d1defaf7f6840d4e5642bf550cfd3e93
ms.sourcegitcommit: e37e916e2bf14f092d3a767bc90d68c181d739fb
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/03/2018
---
# <a name="request-and-provide-remote-assistance-for-windows-pcs"></a><span data-ttu-id="22200-103">Anfordern und Bereitstellen von Remoteunterstützung für Windows-PCs</span><span class="sxs-lookup"><span data-stu-id="22200-103">Request and provide remote assistance for Windows PCs</span></span>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]


<span data-ttu-id="22200-104">Die Informationen in diesem Thema gelten nur für Windows-Desktops, die Sie als PCs mithilfe des Intune-Softwareclients verwalten.</span><span class="sxs-lookup"><span data-stu-id="22200-104">The information in this topic applies only to Windows desktops that you are managing as PCs by using the Intune software client.</span></span>

<span data-ttu-id="22200-105">In Intune können Sie die nicht im Lieferumfang inbegriffene [TeamViewer](https://www.teamviewer.com)-Software verwenden, um Ihre Benutzer, bei denen der Intune-Softwareclient ausgeführt wird, remote zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="22200-105">Intune can use the [TeamViewer](https://www.teamviewer.com) software, purchased separately, to enable you to give remote assistance to your users who are running the Intune software client.</span></span> <span data-ttu-id="22200-106">Sobald ein Benutzer Hilfe über das Microsoft Intune Center anfordert, werden Sie durch eine Warnung benachrichtigt, können die Anforderung annehmen und Unterstützung leisten.</span><span class="sxs-lookup"><span data-stu-id="22200-106">When a user requests help from the Microsoft Intune Center, you are informed by an alert, can accept the request, and then provide assistance.</span></span> <span data-ttu-id="22200-107">Diese Funktion ersetzt die vorhandene Funktion „Windows-Remoteunterstützung“ in Intune.</span><span class="sxs-lookup"><span data-stu-id="22200-107">This functionality replaces the existing Windows Remote Assistance functionality in Intune.</span></span>


## <a name="before-you-start"></a><span data-ttu-id="22200-108">Vorbereitung</span><span class="sxs-lookup"><span data-stu-id="22200-108">Before you start</span></span>

<span data-ttu-id="22200-109">Bevor Sie entsprechende Einrichtungsschritte ausführen und auf Anforderungen für Remoteunterstützung reagieren können, stellen Sie sicher, dass folgende Voraussetzungen erfüllt sind:</span><span class="sxs-lookup"><span data-stu-id="22200-109">Before you begin to establish and to respond to remote assistance requests, ensure that the following prerequisites are in place:</span></span>

- <span data-ttu-id="22200-110">Sie müssen sich für ein [TeamViewer-Konto registriert haben](https://login.teamviewer.com/LogOn#register), um sich bei der TeamViewer-Website anzumelden.</span><span class="sxs-lookup"><span data-stu-id="22200-110">You must have [signed up for a TeamViewer account](https://login.teamviewer.com/LogOn#register) to log in to the TeamViewer website.</span></span>
- <span data-ttu-id="22200-111">Die Windows-PCs, die auf denen Sie Administrationsaufgaben ausführen möchten, müssen [durch den Windows-Softwareclient verwaltet werden](manage-windows-pcs-with-microsoft-intune.md).</span><span class="sxs-lookup"><span data-stu-id="22200-111">Windows PCs that you want to administer must be [managed by the Windows software client](manage-windows-pcs-with-microsoft-intune.md)</span></span>
- <span data-ttu-id="22200-112">Auf allen von Intune unterstützten Windows-PC-Betriebssystemen können Administrationsaufgaben ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="22200-112">All Windows PC operating systems supported by Intune can be administered.</span></span>

## <a name="configure-the-teamviewer-connector"></a><span data-ttu-id="22200-113">Konfigurieren des TeamViewer Connectors</span><span class="sxs-lookup"><span data-stu-id="22200-113">Configure the TeamViewer Connector</span></span>

1. <span data-ttu-id="22200-114">Wählen Sie in der [Microsoft Intune-Verwaltungskonsole](https://manage.microsoft.com) die Option **Verwaltung** aus.</span><span class="sxs-lookup"><span data-stu-id="22200-114">In the [Microsoft Intune administration console](https://manage.microsoft.com), choose **Admin**.</span></span>
2. <span data-ttu-id="22200-115">Wählen Sie im Arbeitsbereich **Verwaltung** die Option **TeamViewer** aus.</span><span class="sxs-lookup"><span data-stu-id="22200-115">In the **Admin** workspace, choose **TeamViewer**.</span></span>
3. <span data-ttu-id="22200-116">Wählen Sie auf der Seite **TeamViewer** unter **TeamViewer Connector** die Option **Aktivieren**.</span><span class="sxs-lookup"><span data-stu-id="22200-116">On the **TeamViewer** page, under **TeamViewer Connector**, choose **Enable**.</span></span>
4. <span data-ttu-id="22200-117">Lesen Sie im Dialogfeld **TeamViewer aktivieren** die Lizenzbedingungen, und klicken Sie auf **Annehmen**, um sie zu akzeptieren.</span><span class="sxs-lookup"><span data-stu-id="22200-117">In the **Enable TeamViewer** dialog box, view, then **Accept** the license terms.</span></span> <span data-ttu-id="22200-118">Wenn Sie noch keine TeamViewer-Lizenz besitzen, wählen Sie **TeamViewer-Lizenz erwerben** aus.</span><span class="sxs-lookup"><span data-stu-id="22200-118">If you don't already own a TeamViewer license, choose **Purchase a TeamViewer license**.</span></span>
5. <span data-ttu-id="22200-119">Wenn das TeamViewer-Browserfenster angezeigt wird, melden Sie sich mit Ihren TeamViewer-Anmeldeinformationen bei der Website an.</span><span class="sxs-lookup"><span data-stu-id="22200-119">After the TeamViewer browser window opens, sign into the site with your TeamViewer credentials.</span></span>
6. <span data-ttu-id="22200-120">Lesen Sie auf der TeamViewer-Website die Optionen, um das Herstellen einer Verbindung zwischen Intune und TeamViewer zuzulassen, und akzeptieren Sie sie.</span><span class="sxs-lookup"><span data-stu-id="22200-120">On the TeamViewer site, read, then accept the options to allow Intune to connect with TeamViewer.</span></span>
7. <span data-ttu-id="22200-121">Vergewissern Sie sich in der Intune-Konsole, dass das Element **TeamViewer Connector** als **Aktiviert** angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="22200-121">In the Intune console, verify that the **TeamViewer Connector** item shows as **Enabled**.</span></span>


## <a name="open-a-remote-assistance-request-end-user"></a><span data-ttu-id="22200-122">Öffnen einer Remoteunterstützungsanforderung (Endbenutzer)</span><span class="sxs-lookup"><span data-stu-id="22200-122">Open a remote assistance request (end user)</span></span>

1. <span data-ttu-id="22200-123">Öffnen Sie auf einem Windows-Client-PC das **Microsoft Intune Center**.</span><span class="sxs-lookup"><span data-stu-id="22200-123">On a client Windows PC, open the **Microsoft Intune Center**.</span></span>
2. <span data-ttu-id="22200-124">Wählen Sie unter **Remoteunterstützung** die Option **Remoteunterstützung anfordern** aus.</span><span class="sxs-lookup"><span data-stu-id="22200-124">Under **Remote Assistance**, choose **Request Remote Assistance**.</span></span>
3. <span data-ttu-id="22200-125">Nach der Genehmigung der Anforderung (siehe unten) wird TeamViewer auf dem Client geöffnet.</span><span class="sxs-lookup"><span data-stu-id="22200-125">After you approve the request (see below), TeamViewer opens on the client.</span></span> <span data-ttu-id="22200-126">Der Benutzer muss alle Meldungen akzeptieren, die darauf hinweisen, dass der Webbrowser die TeamViewer-Anwendung zu öffnen versucht.</span><span class="sxs-lookup"><span data-stu-id="22200-126">The user must accept any messages indicating that the web browser is trying to open the TeamViewer application.</span></span>
4. <span data-ttu-id="22200-127">Der Benutzer wird in einer Meldung gebeten zuzulassen, dass Sie die Kontrolle über seinen PC übernehmen.</span><span class="sxs-lookup"><span data-stu-id="22200-127">The user sees a message asking if you can control their PC.</span></span> <span data-ttu-id="22200-128">Er muss diese Meldung akzeptieren, damit weitere Schritte möglich sind.</span><span class="sxs-lookup"><span data-stu-id="22200-128">They must accept this message to continue.</span></span>
5. <span data-ttu-id="22200-129">Während der Remoteunterstützungssitzung sieht der Benutzer ein Fenster, das anzeigt, dass Sie mit dem Computer des Benutzers verbunden sind.</span><span class="sxs-lookup"><span data-stu-id="22200-129">During the remote assistance session, the user sees a window that shows them you are connected.</span></span> <span data-ttu-id="22200-130">Wenn der Benutzer das Fenster schließt, wird die Remotesitzung beendet.</span><span class="sxs-lookup"><span data-stu-id="22200-130">If they close this window, the remote session ends.</span></span>

## <a name="respond-to-a-remote-assistance-request"></a><span data-ttu-id="22200-131">Reagieren auf eine Remoteunterstützungsanforderung</span><span class="sxs-lookup"><span data-stu-id="22200-131">Respond to a remote assistance request</span></span>

1. <span data-ttu-id="22200-132">Wenn ein Benutzer eine Remoteunterstützungsanforderung übermittelt, können Sie sie im Arbeitsbereich **Warnungen** unter **Überwachung** > **Remoteunterstützung** anzeigen.</span><span class="sxs-lookup"><span data-stu-id="22200-132">When a user submits a remote assistance request, you can view it in the **Alerts** workspace, under **Monitoring** > **Remote Assistance**.</span></span> <span data-ttu-id="22200-133">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="22200-133">For example:</span></span>
   > ![Screenshot einer Remoteunterstützungsanforderung](./media/team-viewer.png)

<br><span data-ttu-id="22200-135">Wenn die Anforderung länger als 4 Stunden unbeantwortet bleibt, wird sie entfernt.</span><span class="sxs-lookup"><span data-stu-id="22200-135">If a request goes unanswered for more than 4 hours, it is removed.</span></span>
2. <span data-ttu-id="22200-136">Um die Anforderung anzunehmen, wählen Sie **Anforderung genehmigen und Remoteunterstützung starten** aus.</span><span class="sxs-lookup"><span data-stu-id="22200-136">To accept the request, choose **Approve request and launch Remote Assistance**.</span></span>
3. <span data-ttu-id="22200-137">Wählen Sie im Dialogfeld **Eine neue Remoteunterstützungsanforderung steht aus** die Option **Remoteunterstützungsanforderung annehmen** aus.</span><span class="sxs-lookup"><span data-stu-id="22200-137">In the **A New Remote Assistance Request is Pending** dialog box, choose **Accept the remote assistance request**.</span></span> <span data-ttu-id="22200-138">Falls sie noch nicht vorhanden sind, installiert TeamViewer alle nötigen Apps auf Ihrem PC.</span><span class="sxs-lookup"><span data-stu-id="22200-138">If it's not already installed, TeamViewer will install any necessary apps on your PC.</span></span>
4. <span data-ttu-id="22200-139">Anschließend benachrichtigt TeamViewer den Endbenutzer, dass Sie die Kontrolle seinen PC übernehmen möchten.</span><span class="sxs-lookup"><span data-stu-id="22200-139">TeamViewer then notifies the end user that you want to take control of their PC.</span></span> <span data-ttu-id="22200-140">Nachdem der Benutzer dies akzeptiert hat, wird das TeamViewer-Fenster geöffnet, und Sie können den PC steuern.</span><span class="sxs-lookup"><span data-stu-id="22200-140">After the user has accepted the request, the TeamViewer windows opens, and you can control the PC.</span></span>

<span data-ttu-id="22200-141">Während einer Remoteunterstützungssitzung können Sie in alle verfügbaren TeamViewer-Befehle nutzen, um den Remote-PC zu steuern.</span><span class="sxs-lookup"><span data-stu-id="22200-141">While in a remote assistance session, you can use all available TeamViewer commands to control the remote PC.</span></span> <span data-ttu-id="22200-142">Weitere Informationen und Hilfe zu diesen Befehlen finden Sie auf der TeamViewer-Website im [Handbuch für Fernsteuerung](http://www.teamviewer.com/en/support/documents/).</span><span class="sxs-lookup"><span data-stu-id="22200-142">For help with these commands, download the [Manual for remote control](http://www.teamviewer.com/en/support/documents/) from the TeamViewer website.</span></span>

## <a name="close-the-remote-assistance-session"></a><span data-ttu-id="22200-143">Beenden der Remoteunterstützungssitzung</span><span class="sxs-lookup"><span data-stu-id="22200-143">Close the remote assistance session</span></span>

<span data-ttu-id="22200-144">Wählen Sie im **TeamViewer**-Fenster im Menü **Aktionen** den Befehl **Sitzung beenden** aus.</span><span class="sxs-lookup"><span data-stu-id="22200-144">From the **Actions** menu of the **TeamViewer** window, choose **End Session**.</span></span>

## <a name="remotely-restart-a-windows-pc"></a><span data-ttu-id="22200-145">Remoteneustart eines Windows-PCs</span><span class="sxs-lookup"><span data-stu-id="22200-145">Remotely restart a Windows PC</span></span>
<span data-ttu-id="22200-146">Wenn Sie Ihre Benutzer bei Problemen unterstützen, müssen Sie deren PC möglicherweise von Zeit zu Zeit remote neu starten.</span><span class="sxs-lookup"><span data-stu-id="22200-146">When helping your users with issues, you might need to remotely restart their PC from time to time.</span></span> <span data-ttu-id="22200-147">Gehen Sie folgendermaßen vor, um einen Remoteneustart für einen Windows-PC auszuführen.</span><span class="sxs-lookup"><span data-stu-id="22200-147">Use the following steps to remotely restart a Windows PC.</span></span>

1.  <span data-ttu-id="22200-148">Wählen Sie in der [Microsoft Intune-Verwaltungskonsole](https://manage.microsoft.com/) die Option **Gruppen** &gt; **Alle Geräte** aus (oder eine andere Gruppe, in der der PC enthalten ist, den Sie erneut starten möchten).</span><span class="sxs-lookup"><span data-stu-id="22200-148">In the [Microsoft Intune administration console](https://manage.microsoft.com/), choose **Groups** &gt; **All Devices** (or another group that contains the PC you want to restart).</span></span>

2.  <span data-ttu-id="22200-149">Wählen Sie mindestens einen PC aus, und wählen Sie dann **Remoteaufgaben** &gt; **Computer neu starten**.</span><span class="sxs-lookup"><span data-stu-id="22200-149">Select one or more PCs, and then choose **Remote Tasks** &gt; **Restart Computer**.</span></span>

3.  <span data-ttu-id="22200-150">Zur Anzeige des Aufgabenstatus wählen Sie **Remoteaufgaben** unten rechts auf der Seite aus.</span><span class="sxs-lookup"><span data-stu-id="22200-150">To view the task status, choose **Remote Tasks** in the bottom right corner of the page.</span></span>

4.  <span data-ttu-id="22200-151">Überprüfen Sie im Dialogfeld **Taskstatus** die aktuellen Remoteaufgaben, den Aufgabenstatus, den Gerätenamen und etwaige gemeldete Fehler.</span><span class="sxs-lookup"><span data-stu-id="22200-151">In the **Task Status** dialog box, review the current remote tasks, task status, device name, and any reported errors.</span></span>

### <a name="see-also"></a><span data-ttu-id="22200-152">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="22200-152">See also</span></span>

[<span data-ttu-id="22200-153">Allgemeine Aufgaben zur Verwaltung von Windows-PCs mit dem Intune-Softwareclient</span><span class="sxs-lookup"><span data-stu-id="22200-153">Common Windows PC management tasks with the Intune software client</span></span>](common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client.md)