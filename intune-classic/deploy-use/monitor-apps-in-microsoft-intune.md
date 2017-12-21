---
title: "Überwachen von App-Bereitstellungen"
description: "Erfahren Sie, wie Sie Apps überwachen, die Sie mit Intune bereitgestellt haben."
keywords: 
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 11/10/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5daad56d-71c8-455b-8a55-f8b33e279a8a
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 2ffb84e4956885cbc892dec92c4687a2f8691082
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2017
---
# <a name="monitor-app-deployments-in-microsoft-intune"></a><span data-ttu-id="639a3-103">Überwachen von App-Bereitstellungen in Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="639a3-103">Monitor app deployments in Microsoft Intune</span></span>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

## <a name="monitor-an-app-deployment"></a><span data-ttu-id="639a3-104">Überwachen einer App-Bereitstellung</span><span class="sxs-lookup"><span data-stu-id="639a3-104">Monitor an app deployment</span></span>
<span data-ttu-id="639a3-105">Sie können die verwalteten Apps und den Status aller Bereitstellungen in der Intune-Verwaltungskonsole anzeige.</span><span class="sxs-lookup"><span data-stu-id="639a3-105">You can see the apps that you manage and the status of any deployments in the Intune administration console.</span></span> <!---App status is displayed in real-time. You don't have to wait for the device to check-in before you can see this.--->

### <a name="to-view-apps-that-you-manage-and-their-status"></a><span data-ttu-id="639a3-106">So zeigen Sie die von Ihnen verwalteten Apps und ihren Status an</span><span class="sxs-lookup"><span data-stu-id="639a3-106">To view apps that you manage and their status</span></span>
<span data-ttu-id="639a3-107">Wählen Sie im Arbeitsbereich **Apps** den Knoten **Apps** und dann die Option **Apps** aus.</span><span class="sxs-lookup"><span data-stu-id="639a3-107">In the **Apps** workspace, choose the **Apps** node, and then choose **Apps**.</span></span>

<span data-ttu-id="639a3-108">Die Liste der von Ihnen verwalteten Apps wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="639a3-108">The list of apps that you manage appears.</span></span> <span data-ttu-id="639a3-109">Sie können eine beliebige App auswählen, um im unteren Bereich des Konsolenfensters den Installationsstatus anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="639a3-109">You can choose any app to see an installation status in the lower pane of the console windows.</span></span> <span data-ttu-id="639a3-110">Klicken Sie auf diesen Status, um weitere Details anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="639a3-110">Choose this status to see further details.</span></span> <span data-ttu-id="639a3-111">Angenommen, es wird folgender Status angezeigt: **1 Benutzer steht diese Software zur Verfügung**. Sie können dann auf diese Meldung klicken, um den Namen des Benutzers anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="639a3-111">For example, if the status shows **1 user has this software available**, you can choose the message to see the name of the user.</span></span>

> [!TIP]
> <span data-ttu-id="639a3-112">Über die Dropdownliste **Filter** können Sie die Anzeige auf diejenigen Apps beschränken, die von Ihnen angegebenen Kriterien entsprechen, z. B. die Apps, bei denen ein Installationsfehler aufgetreten ist oder die erfolgreich installiert wurden.</span><span class="sxs-lookup"><span data-stu-id="639a3-112">You can use the **Filters** drop-down list to show only apps that meet the criteria that you specify, like apps that failed to install or apps that were successfully deployed.</span></span>
>
> ![Beispiel für App-Filter](./media/app-filters.png)

<span data-ttu-id="639a3-114">Außerdem wird im Arbeitsbereich **Dashboard** eine Übersicht über den Status der Apps angezeigt.</span><span class="sxs-lookup"><span data-stu-id="639a3-114">Additionally, the **Dashboard** workspace shows an overview of the status of your apps.</span></span> <span data-ttu-id="639a3-115">Wenn Sie in der Übersicht auf eine beliebige Stelle klicken, gelangen Sie zur Liste der Apps.</span><span class="sxs-lookup"><span data-stu-id="639a3-115">If you click anywhere in the overview, you'll be taken to the list of apps.</span></span>

## <a name="to-view-more-detailed-information-about-an-app"></a><span data-ttu-id="639a3-116">So zeigen Sie detailliertere Informationen über eine App an</span><span class="sxs-lookup"><span data-stu-id="639a3-116">To view more detailed information about an app</span></span>
<span data-ttu-id="639a3-117">Wählen Sie in der Liste der Apps eine beliebige App aus, und klicken Sie dann auf **Eigenschaften anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="639a3-117">In the list of apps, select any app, and then choose **View Properties**.</span></span>

<span data-ttu-id="639a3-118">Wählen Sie auf der Seite **Softwareeigenschaften** für die App eine dieser Registerkarten aus: **Allgemein:** Zeigt allgemeine Informationen über die App und deren Installationsstatus an. **Geräte:** Zeigt die Geräte an, bei denen eine gezielte Bereitstellung der App erfolgreich installiert wurde. **Benutzer:** Zeigt die Benutzer an, auf deren Geräten eine gezielte Bereitstellung der App erfolgreich installiert wurde.</span><span class="sxs-lookup"><span data-stu-id="639a3-118">On the **Software Properties** page for the app, choose one of these tabs: **General** - Shows general information about the app and its installation status, **Devices** - Shows the devices that successfully installed a targeted deployment of the app, and **Users** - Shows the users whose devices successfully installed a targeted deployment of the app.</span></span>

<span data-ttu-id="639a3-119">Wie bereits zuvor können Sie auch hier die Dropdownliste **Filter** verwenden, um die auf den Registerkarten angezeigten Werte zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="639a3-119">As before, you can use the **Filters** drop-down list to configure the values shown on each of the tabs.</span></span>
