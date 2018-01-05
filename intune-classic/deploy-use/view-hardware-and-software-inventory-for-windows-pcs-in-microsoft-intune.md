---
title: "Anzeigen des Hardware- und Softwarebestands für Windows-PCs"
description: Anzeigen von Hardware- und Softwareinformationen zu Windows-Desktops, die Sie mithilfe des Intune-Softwareclients als PCs verwalten.
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 12/15/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3c10f4c9-520b-4864-92fc-a45a9f640ad4
ms.reviewer: owenyen
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: d985da553637e684f4773848fa8832e4aadd1775
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2017
---
# <a name="view-hardware-and-software-inventory-for-windows-pcs"></a><span data-ttu-id="6fd14-103">Anzeigen des Hardware- und Softwarebestands für Windows-PCs</span><span class="sxs-lookup"><span data-stu-id="6fd14-103">View hardware and software inventory for Windows PCs</span></span>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="6fd14-104">Intune sammelt detaillierte Informationen zur Hardware und Software von Desktops, die Sie mithilfe des Intune-Softwareclients als PCs verwalten.</span><span class="sxs-lookup"><span data-stu-id="6fd14-104">Intune collects detailed information about the hardware and software of desktops that you manage as PCs by using the Intune software client.</span></span> <span data-ttu-id="6fd14-105">In den nachfolgend beschriebenen Verfahren lernen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="6fd14-105">Use the information in the following procedures to learn how to create:</span></span>

-   <span data-ttu-id="6fd14-106">Erstellen eines Berichts, der Informationen zu den Hardwarefunktionen der von Ihnen verwalteten PCs auflistet</span><span class="sxs-lookup"><span data-stu-id="6fd14-106">A report that lists information about the hardware capabilities of PCs you manage.</span></span>

-   <span data-ttu-id="6fd14-107">Erstellen eines Berichts, der die auf den jeweiligen PCs installierte Software auflistet</span><span class="sxs-lookup"><span data-stu-id="6fd14-107">A report that lists the software installed on each PC.</span></span>

-   <span data-ttu-id="6fd14-108">Aktualisieren des Inventars eines PCs, um sicherzustellen, dass die Daten im Bericht aktuell sind</span><span class="sxs-lookup"><span data-stu-id="6fd14-108">How to refresh a PCs inventory to ensure that the data in the report is current.</span></span>

## <a name="to-display-information-about-pcs-you-manage"></a><span data-ttu-id="6fd14-109">Anzeigen von Informationen zu den von Ihnen verwalteten PCs</span><span class="sxs-lookup"><span data-stu-id="6fd14-109">To display information about PCs you manage</span></span>

1.  <span data-ttu-id="6fd14-110">Wählen Sie in der [Microsoft Intune-Verwaltungskonsole](https://manage.microsoft.com/) die Option **Berichte** &gt; **Computerinventurberichte** aus.</span><span class="sxs-lookup"><span data-stu-id="6fd14-110">In the [Microsoft Intune administration console](https://manage.microsoft.com/), choose **Reports** &gt; **Computer Inventory Reports**.</span></span>

2.  <span data-ttu-id="6fd14-111">Übernehmen Sie auf der Seite **Neuen Bericht erstellen** die Vorgaben, oder passen Sie sie an, um die im Bericht zurückgegebenen Ergebnisse zu filtern.</span><span class="sxs-lookup"><span data-stu-id="6fd14-111">On the **Create New Report** page, accept the default values or customize them to filter the results that will be returned by the report.</span></span> <span data-ttu-id="6fd14-112">Sie können beispielsweise auswählen, dass nur PCs im Bericht angezeigt werden, auf denen Windows 8.1 ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="6fd14-112">For example, you could select that only PCs that run Windows 8.1 will be displayed in the report.</span></span>

3.  <span data-ttu-id="6fd14-113">Wählen Sie **Bericht anzeigen** aus, um den **Computerinventurbericht** in einem neuen Fenster anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="6fd14-113">Choose **View Report** to open the **Computer Inventory Report** in a new window.</span></span>

    <span data-ttu-id="6fd14-114">Sie können den Bericht durch Auswählen der entsprechenden Spaltenüberschrift nach jeder Spalte sortieren, z. B. **Name**, **Gehäusetyp** oder **Hersteller**.</span><span class="sxs-lookup"><span data-stu-id="6fd14-114">You can sort the report by any of the columns, like **Name**, **Chassis Type** or **Manufacturer** by selecting each column heading.</span></span>

## <a name="to-display-software-installed-on-pcs-you-manage"></a><span data-ttu-id="6fd14-115">Anzeigen der auf den von Ihnen verwalteten PCs installierten Software</span><span class="sxs-lookup"><span data-stu-id="6fd14-115">To display software installed on PCs you manage</span></span>

1.  <span data-ttu-id="6fd14-116">Wählen Sie in der [Microsoft Intune-Verwaltungskonsole](https://manage.microsoft.com/) die Option **Berichte** &gt; **Berichte zu ermittelter Software** aus.</span><span class="sxs-lookup"><span data-stu-id="6fd14-116">In the [Microsoft Intune administration console](https://manage.microsoft.com/), choose **Reports** &gt; **Detected Software Reports**.</span></span>

2.  <span data-ttu-id="6fd14-117">Übernehmen Sie auf der Seite **Neuen Bericht erstellen** die Vorgaben, oder passen Sie sie an, um die im Bericht zurückgegebenen Ergebnisse zu filtern.</span><span class="sxs-lookup"><span data-stu-id="6fd14-117">On the **Create New Report** page, accept the default values or customize them to filter the results that will be returned by the report.</span></span> <span data-ttu-id="6fd14-118">Sie können beispielsweise auswählen, dass nur von Microsoft herausgegebene Software im Bericht angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="6fd14-118">For example, you could select that only software published by Microsoft will be displayed in the report.</span></span>

3.  <span data-ttu-id="6fd14-119">Wählen Sie **Bericht anzeigen** aus, um den **Bericht zu ermittelter Software** in einem neuen Fenster anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="6fd14-119">Choose **View Report** to open the **Detected Software Report** in a new window.</span></span>

    <span data-ttu-id="6fd14-120">Sie können den Bericht durch Auswählen der entsprechenden Spaltenüberschrift nach jeder Spalte sortieren, z. B. **Name**, **Herausgeber** oder **Kategorie**.</span><span class="sxs-lookup"><span data-stu-id="6fd14-120">You can sort the report by any of the columns, like **Name**, **Publisher** or **Category** by selecting each column heading.</span></span> <span data-ttu-id="6fd14-121">Durch Auswahl des Richtungspfeils neben dem Listenelement können Sie die Updates in der Liste erweitern, um weitere Details anzuzeigen (zum Beispiel die PCs, auf denen ein Update installiert ist).</span><span class="sxs-lookup"><span data-stu-id="6fd14-121">You can expand the updates in the list to show more detail (such as the PCs on which it is installed) by choosing the directional arrow next to the list item.</span></span>

## <a name="to-refresh-computer-inventory-to-ensure-it-is-current"></a><span data-ttu-id="6fd14-122">So aktualisieren Sie das Computerinventar, um sicherzustellen, dass es aktuell ist</span><span class="sxs-lookup"><span data-stu-id="6fd14-122">To refresh computer inventory to ensure it is current</span></span>

1.  <span data-ttu-id="6fd14-123">Wählen Sie in der [Microsoft Intune-Verwaltungskonsole](https://manage.microsoft.com/) die Option **Gruppen** &gt; **Alle Geräte** aus (oder eine andere Gruppe, die den PC enthält, für den Sie das Inventar aktualisieren möchten).</span><span class="sxs-lookup"><span data-stu-id="6fd14-123">In the [Microsoft Intune administration console](https://manage.microsoft.com/), choose **Groups** &gt; **All Devices** (or another group that contains the PC for which you want to refresh inventory).</span></span>

2.  <span data-ttu-id="6fd14-124">Wählen Sie einen PC aus, oder halten Sie die **STRG**-Taste gedrückt, um mehrere Computer auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="6fd14-124">Select a PC, or press and hold **Ctrl** to select multiple PCs.</span></span>

3.  <span data-ttu-id="6fd14-125">Wählen Sie auf der Taskleiste **Remoteaufgaben** &gt; **Inventar aktualisieren** aus.</span><span class="sxs-lookup"><span data-stu-id="6fd14-125">On the taskbar, choose **Remote Tasks** &gt; **Refresh Inventory**.</span></span>

4.  <span data-ttu-id="6fd14-126">Zur Anzeige des Aufgabenstatus wählen Sie **Remoteaufgaben** unten rechts auf der Seite aus.</span><span class="sxs-lookup"><span data-stu-id="6fd14-126">To view the task status, choose **Remote Tasks** in the bottom right corner of the page.</span></span>

    <span data-ttu-id="6fd14-127">Im Dialogfeld **Taskstatus** werden aktuelle Remoteaufgaben, ihr Status, der Gerätename und etwaige gemeldete Fehler mit einem Link zu Problembehandlungsinformationen aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="6fd14-127">The **Task Status** dialog box displays showing current remote tasks, task status, device name, and any reported errors, and provides a link to troubleshooting information.</span></span>

### <a name="see-also"></a><span data-ttu-id="6fd14-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="6fd14-128">See also</span></span>

[<span data-ttu-id="6fd14-129">Allgemeine Aufgaben zur Verwaltung von Windows-PCs mit dem Intune-Softwareclient</span><span class="sxs-lookup"><span data-stu-id="6fd14-129">Common Windows PC management tasks with the Intune software client</span></span>](common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client.md)