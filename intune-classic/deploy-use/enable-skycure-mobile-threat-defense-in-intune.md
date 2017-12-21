---
title: Aktivieren von Skycure Mobile Threat Defense in Intune
description: Aktivieren Sie Skycure Mobile Threat Defense im klassischen Intune-Portal.
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 03/16/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 0cc4e59d-819a-47a2-a26f-4f8d0f8df7bf
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 1f033b01520aa047aea0a2b6c94582a454355816
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2017
---
# <a name="enable-skycure-mobile-threat-defense-in-intune"></a><span data-ttu-id="3a150-103">Aktivieren von Skycure Mobile Threat Defense in Intune</span><span class="sxs-lookup"><span data-stu-id="3a150-103">Enable Skycure Mobile Threat Defense in Intune</span></span>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="3a150-104">Um die Verbindung mit Skycure Mobile Threat Defense zu aktivieren, muss der [Intune-Connector in der Skycure-Konsole] (/intune-classic/deploy-use/setup-the-skycure-integration-with-Intune) bereits konfiguriert sein.</span><span class="sxs-lookup"><span data-stu-id="3a150-104">To enable the Skycure mobile threat defense, you should have already configured the [Intune Connector in the Skycure console] (/intune-classic/deploy-use/setup-the-skycure-integration-with-Intune).</span></span>

## <a name="to-enable-the-skycure-mtd-connection-in-intune"></a><span data-ttu-id="3a150-105">So aktivieren Sie die Skycure MTD-Verbindung in Intune</span><span class="sxs-lookup"><span data-stu-id="3a150-105">To enable the Skycure MTD connection in Intune</span></span>

1.  <span data-ttu-id="3a150-106">Wechseln Sie zum [klassischen Intune-Portal](https://manage.microsoft.com/), und geben Sie Ihre Anmeldeinformationen ein.</span><span class="sxs-lookup"><span data-stu-id="3a150-106">Go to the [Intune classic portal](https://manage.microsoft.com/) then enter your credentials.</span></span>

2.  <span data-ttu-id="3a150-107">Wählen Sie **Admin** &gt; **Third Party Service Integration** (Integration von Drittanbieterdiensten), wählen Sie dann **Skycure-Status**, und aktivieren Sie mithilfe der Umschaltfläche **Synchronisierung mit MTD**.</span><span class="sxs-lookup"><span data-stu-id="3a150-107">Choose **Admin** &gt; **Third Party Service Integration**, then choose **Skycure Status** and enable **Synchronization with MTD** using the toggle button.</span></span>

    ![Aktivieren der Skycure-Umschaltfläche im klassischen Intune-Portal](../media/mtp/enable-skycure-1.png)

> [!IMPORTANT] 
> <span data-ttu-id="3a150-109">Sie müssen die Skycure-Apps konfigurieren, bevor Sie die Regeln der Kompatibilitätsrichtlinie erstellen und den bedingten Zugriff konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="3a150-109">You must configure the Skycure apps before creating compliance policy rules and configuring conditional access.</span></span> <span data-ttu-id="3a150-110">Dadurch wird sichergestellt, dass die App für die Installation durch Endbenutzer bereit und verfügbar ist, bevor sie Zugriff auf E-Mail oder andere Unternehmensressourcen erhalten.</span><span class="sxs-lookup"><span data-stu-id="3a150-110">This ensures that the app is ready and available for end users to install before they can get access to email or other company resources.</span></span>

<span data-ttu-id="3a150-111">Damit wird das Einrichten der Skycure- und Intune-Integration in der Intune-Administratorkonsole abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="3a150-111">This completes the setup of the Skycure and Intune integration in the Intune administrator console.</span></span> <span data-ttu-id="3a150-112">Die nächsten Schritte zum Implementieren dieser Lösung umfassen die Bereitstellung der Skycure for Work-Apps und das Einrichten der Kompatibilitätsrichtlinie.</span><span class="sxs-lookup"><span data-stu-id="3a150-112">The next few steps to implement this solution involve deploying the Skycure for Work apps and setting up the compliance policy.</span></span>

## <a name="next-steps"></a><span data-ttu-id="3a150-113">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="3a150-113">Next steps</span></span>

[<span data-ttu-id="3a150-114">Erstellen der Mobile Threat Defense-Kompatibilitätsrichtlinie</span><span class="sxs-lookup"><span data-stu-id="3a150-114">Create Skycure Mobile Threat Defense compliance policy</span></span>](/intune-classic/deploy-use/create-skycure-mobile-threat-defense-compliance-policy)
