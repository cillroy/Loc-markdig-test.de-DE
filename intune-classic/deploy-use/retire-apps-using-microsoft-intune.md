---
title: "Außerbetriebnahme von Apps"
description: "Informationen zur Außerbetriebnahme oder zum Deinstallieren von Apps mithilfe von Intune."
keywords: 
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 12/27/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6fbf0805-1144-4e08-bafd-4f181d932bf2
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: a3fadf497e5db147d12ecf1e32343e94222c65e9
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2018
---
# <a name="retire-apps-using-microsoft-intune"></a><span data-ttu-id="e0145-103">Außerbetriebnahme von Apps mit Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="e0145-103">Retire apps using Microsoft Intune</span></span>

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="e0145-104">Um eine App außer Betrieb zu nehmen, deinstallieren Sie sie einfach.</span><span class="sxs-lookup"><span data-stu-id="e0145-104">To retire an app, you simply uninstall it.</span></span> <span data-ttu-id="e0145-105">Wenn Sie Apps mit Intune bereitstellen und verwalten, ist der Prozess zum Deinstallieren der App für mobile Geräte und Windows-PCs identisch.</span><span class="sxs-lookup"><span data-stu-id="e0145-105">When you deploy and manage apps with Intune, the process for uninstalling the app is the same for both mobile devices and Windows PCs.</span></span> <span data-ttu-id="e0145-106">Damit dieses Verfahren erfolgreich ausgeführt werden kann, muss die App den Deinstallationsprozess unterstützen.</span><span class="sxs-lookup"><span data-stu-id="e0145-106">The app must support the uninstallation process for this procedure to succeed.</span></span>

## <a name="uninstall-an-app"></a><span data-ttu-id="e0145-107">Deinstallieren einer App</span><span class="sxs-lookup"><span data-stu-id="e0145-107">Uninstall an app</span></span>

1.  <span data-ttu-id="e0145-108">Wählen Sie in der [Microsoft Intune-Verwaltungskonsole](https://manage.microsoft.com) **Apps** &gt; **Apps** aus.</span><span class="sxs-lookup"><span data-stu-id="e0145-108">In the [Microsoft Intune administration console](https://manage.microsoft.com), choose **Apps** &gt; **Apps**.</span></span>

2.  <span data-ttu-id="e0145-109">Wählen Sie die zu deinstallierende App aus (eine, die zuvor bereitgestellt wurde), und wählen Sie anschließend **Bereitstellung verwalten** aus.</span><span class="sxs-lookup"><span data-stu-id="e0145-109">Select the app you want to uninstall (one that has been previously deployed), and then choose **Manage Deployment**.</span></span>

3.  <span data-ttu-id="e0145-110">Wählen Sie auf der Seite **Bereitstellungsaktion** die Option **Deinstallieren** aus der Spalte **Genehmigung** aus.</span><span class="sxs-lookup"><span data-stu-id="e0145-110">On the **Deployment Action** page, select **Uninstall** from the **Approval** column.</span></span>

<span data-ttu-id="e0145-111">Wenn das Gerät oder der Computer das nächste Mal die Apps prüft, wird die App deinstalliert.</span><span class="sxs-lookup"><span data-stu-id="e0145-111">When the device or computer next checks for apps, the app will be uninstalled.</span></span>

### <a name="see-also"></a><span data-ttu-id="e0145-112">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e0145-112">See also</span></span>
[<span data-ttu-id="e0145-113">Hinzufügen von Apps in Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="e0145-113">Add apps in Microsoft Intune</span></span>](add-apps.md)
