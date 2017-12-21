---
title: Aktivieren von Lookout MTP in Intune
description: Aktivieren von Lookout Mobile Threat Protection in der Intune-Verwaltungskonsole.
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 12/19/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 2f835fd0-4e62-42f3-b7ca-ce8b7ddd40e4
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: sandera
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: f430d55ded52e9f8d00db1c2a7d8412673a4e4d3
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2017
---
# <a name="enable-lookout-mtd-connection-in-the-intune-classic-portal"></a><span data-ttu-id="469fe-103">Aktivieren der Lookout MTD-Verbindung im klassischen Intune-Portal</span><span class="sxs-lookup"><span data-stu-id="469fe-103">Enable Lookout MTD connection in the Intune classic portal</span></span>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="469fe-104">Um die Verbindung mit Lookout Mobile Threat Defense (MTD) in Intune zu aktivieren, muss der Intune-Connector in der Lookout-Konsole bereits konfiguriert sein.</span><span class="sxs-lookup"><span data-stu-id="469fe-104">To enable the Lookout Mobile Threat Defense (MTD) connection in Intune, you should have already configured the Intune Connector in the Lookout console.</span></span>  <span data-ttu-id="469fe-105">Wenn dies noch nicht erfolgt ist, führen Sie die in [Einrichten Ihres Lookout Mobile Threat Defense-Abonnements](setup-your-lookout-mtd-subscription.md) beschriebenen Schritte aus.</span><span class="sxs-lookup"><span data-stu-id="469fe-105">If you have not already done so, you should [Set up your Lookout Mobile Threat Defense subscription](setup-your-lookout-mtd-subscription.md).</span></span>

<span data-ttu-id="469fe-106">Um die Lookout MTP-Verbindung in Intune zu aktivieren, wählen Sie auf der Seite **Verwaltung** der [Microsoft Intune-Verwaltungskonsole](https://manage.microsoft.com) die Option **Integration von Drittanbieterdiensten** aus.</span><span class="sxs-lookup"><span data-stu-id="469fe-106">To enable the Lookout MTP connection in Intune, on the **Administration** page in the [Microsoft Intune administrator console](https://manage.microsoft.com), choose **Third Party Service Integration**.</span></span> <span data-ttu-id="469fe-107">Wählen Sie **Lookout-Status** aus, und aktivieren Sie **Synchronisierung mit MTP** mithilfe der Umschaltfläche.</span><span class="sxs-lookup"><span data-stu-id="469fe-107">Choose **Lookout status** and enable **Synchronization with MTP** using the toggle button.</span></span>

![Screenshot der Lookout-Synchronisierungsseite mit hervorgehobener Umschaltfläche „Aktivieren“](../media/mtp/lookout-intune-synchronization.png)

>[!IMPORTANT]
> <span data-ttu-id="469fe-109">Sie **müssen** die Lookout for Work-App konfigurieren, bevor Sie die Regeln der Kompatibilitätsrichtlinie erstellen und den bedingten Zugriff konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="469fe-109">You **must** configure the Lookout for Work app before creating compliance policy rules and configuring conditional access.</span></span> <span data-ttu-id="469fe-110">Dadurch wird sichergestellt, dass die App für die Installation durch Endbenutzer bereit und verfügbar ist, bevor sie Zugriff auf E-Mail oder andere Unternehmensressourcen erhalten.</span><span class="sxs-lookup"><span data-stu-id="469fe-110">This ensures that the app is ready and available for end users to install before they can get access to email or other company resources.</span></span>

<span data-ttu-id="469fe-111">Damit wird das Setup der Lookout- und Intune-Integration in der Intune-Administratorkonsole abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="469fe-111">This completes the setup of the Lookout and Intune integration in the Intune administrator console.</span></span>  <span data-ttu-id="469fe-112">Die nächsten Schritte zum Implementieren dieser Lösung umfassen die Bereitstellung der [Lookout for Work-Apps](/intune-classic/deploy-use/device-threat-protection-policy)-Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="469fe-112">The next few steps to implement this solution involve deploying the [Lookout for Work apps](/intune-classic/deploy-use/device-threat-protection-policy) policy.</span></span>


## <a name="next-steps"></a><span data-ttu-id="469fe-113">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="469fe-113">Next steps</span></span>
[<span data-ttu-id="469fe-114">Konfigurieren der Lookout for Work-App</span><span class="sxs-lookup"><span data-stu-id="469fe-114">Configure Lookout for Work app </span></span>](/intune-classic/deploy-use/device-threat-protection-apps)
