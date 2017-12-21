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
ms.openlocfilehash: 24baa001c735ff6f9354d8992591c0848ef6fe48
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2017
---
# <a name="retire-apps-using-microsoft-intune"></a><span data-ttu-id="a301e-103">Außerbetriebnahme von Apps mit Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="a301e-103">Retire apps using Microsoft Intune</span></span>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="a301e-104">Um eine App außer Betrieb zu nehmen, deinstallieren Sie sie einfach.</span><span class="sxs-lookup"><span data-stu-id="a301e-104">To retire an app, you simply uninstall it.</span></span> <span data-ttu-id="a301e-105">Wenn Sie Apps mit Intune bereitstellen und verwalten, ist der Prozess zum Deinstallieren der App für mobile Geräte und Windows-PCs identisch.</span><span class="sxs-lookup"><span data-stu-id="a301e-105">When you deploy and manage apps with Intune, the process for uninstalling the app is the same for both mobile devices and Windows PCs.</span></span> <span data-ttu-id="a301e-106">Damit dieses Verfahren erfolgreich ausgeführt werden kann, muss die App den Deinstallationsprozess unterstützen.</span><span class="sxs-lookup"><span data-stu-id="a301e-106">The app must support the uninstallation process for this procedure to succeed.</span></span>

## <a name="uninstall-an-app"></a><span data-ttu-id="a301e-107">Deinstallieren einer App</span><span class="sxs-lookup"><span data-stu-id="a301e-107">Uninstall an app</span></span>

1.  <span data-ttu-id="a301e-108">Wählen Sie in der [Microsoft Intune-Verwaltungskonsole](https://manage.microsoft.com) **Apps** &gt; **Apps** aus.</span><span class="sxs-lookup"><span data-stu-id="a301e-108">In the [Microsoft Intune administration console](https://manage.microsoft.com), choose **Apps** &gt; **Apps**.</span></span>

2.  <span data-ttu-id="a301e-109">Wählen Sie die zu deinstallierende App aus (eine, die zuvor bereitgestellt wurde), und wählen Sie anschließend **Bereitstellung verwalten** aus.</span><span class="sxs-lookup"><span data-stu-id="a301e-109">Select the app you want to uninstall (one that has been previously deployed), and then choose **Manage Deployment**.</span></span>

3.  <span data-ttu-id="a301e-110">Wählen Sie auf der Seite **Bereitstellungsaktion** die Option **Deinstallieren** aus der Spalte **Genehmigung** aus.</span><span class="sxs-lookup"><span data-stu-id="a301e-110">On the **Deployment Action** page, select **Uninstall** from the **Approval** column.</span></span>

<span data-ttu-id="a301e-111">Wenn das Gerät oder der Computer das nächste Mal die Apps prüft, wird die App deinstalliert.</span><span class="sxs-lookup"><span data-stu-id="a301e-111">When the device or computer next checks for apps, the app will be uninstalled.</span></span>

### <a name="see-also"></a><span data-ttu-id="a301e-112">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="a301e-112">See also</span></span>
[<span data-ttu-id="a301e-113">Hinzufügen von Apps in Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="a301e-113">Add apps in Microsoft Intune</span></span>](add-apps.md)
