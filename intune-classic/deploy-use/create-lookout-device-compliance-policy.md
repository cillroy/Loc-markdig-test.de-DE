---
title: "Aktivieren der Geräteschutzregel"
description: "Aktivieren der Regel zum Schutz vor Bedrohungen von mobilen Geräten in der Gerätekompatibilitätsrichtlinie."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 03/21/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c951692d-6538-46c0-a9f0-d607ded189ae
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: sandera
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: b9a71006bb78ee58db5d55deb59e10bb7280309e
ms.sourcegitcommit: e37e916e2bf14f092d3a767bc90d68c181d739fb
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/03/2018
---
# <a name="create-lookout-device-compliance-policy-in-intune"></a><span data-ttu-id="69fc2-103">Erstellen einer Lookout-Kompatibilitätsrichtlinie in Intune</span><span class="sxs-lookup"><span data-stu-id="69fc2-103">Create Lookout device compliance policy in Intune</span></span>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="69fc2-104">Dank Intune mit Lookout Mobile Threat Defense können Sie Bedrohungen auf mobilen Geräten erkennen und das Risiko auf solchen Geräten bewerten.</span><span class="sxs-lookup"><span data-stu-id="69fc2-104">Intune with Lookout Mobile Threat Defense lets you detect threats on mobile devices and assess risk on those devices.</span></span> <span data-ttu-id="69fc2-105">Sie können eine Regel für die Kompatibilitätsrichtlinie erstellen, mit der das Risiko bewertet wird, um zu ermitteln, ob das Gerät kompatibel ist.</span><span class="sxs-lookup"><span data-stu-id="69fc2-105">You can create a compliance policy rule that assesses risk to determine if the device is compliant.</span></span> <span data-ttu-id="69fc2-106">Anschließend können Sie die Richtlinie für bedingten Zugriff verwenden, um den Zugriff auf Dienste basierend auf der Gerätekompatibilität zuzulassen oder zu blockieren.</span><span class="sxs-lookup"><span data-stu-id="69fc2-106">You can then use conditional access policy to block access to services based on device compliance.</span></span>

<span data-ttu-id="69fc2-107">Voraussetzungen für die Kompatibilitätsrichtlinie mit Lookout Mobile Threat Defense:</span><span class="sxs-lookup"><span data-stu-id="69fc2-107">Prerequisites for compliance policy with Lookout Mobile Threat Defense:</span></span>

- [<span data-ttu-id="69fc2-108">Einrichten des Lookout Mobile Thread Defense-Abonnements</span><span class="sxs-lookup"><span data-stu-id="69fc2-108">Set up Lookout Mobile Threat Defense subscription</span></span>](setup-your-lookout-mtd-subscription.md)
- [<span data-ttu-id="69fc2-109">Aktivieren der Lookout Verbindung in Intune</span><span class="sxs-lookup"><span data-stu-id="69fc2-109">Enable the Lookout connection in Intune</span></span>](enable-lookout-mtd-connection.md)
- [<span data-ttu-id="69fc2-110">Konfigurieren und Bereitstellen der Lookout for Work-App</span><span class="sxs-lookup"><span data-stu-id="69fc2-110">Configure and deploy the Lookout for work app</span></span>](configure-deploy-lookout-for-work-app.md)

<span data-ttu-id="69fc2-111">Beim Einrichten von Lookout Mobile Threat Defense haben Sie in der [Lookout-Konsole](https://aad.lookout.com) eine Richtlinie erstellt, die verschiedene Bedrohungen als hoch, mittel und niedrig klassifiziert.</span><span class="sxs-lookup"><span data-stu-id="69fc2-111">As part of the Lookout Mobile Threat Defense setup, in the [Lookout console](https://aad.lookout.com), you created a policy that classifies various threats as high, medium and low.</span></span> <span data-ttu-id="69fc2-112">In der Intune-Kompatibilitätsrichtlinie legen Sie die maximal zulässige Bedrohungsstufe fest.</span><span class="sxs-lookup"><span data-stu-id="69fc2-112">In the Intune compliance policy, you set the maximum allowed threat level.</span></span>

1. <span data-ttu-id="69fc2-113">Wechseln Sie in der [Intune-Administratorkonsole](https://manage.microsoft.com) zur Seite **Kompatibilitätsrichtlinien**.</span><span class="sxs-lookup"><span data-stu-id="69fc2-113">In the [Intune administrator console](https://manage.microsoft.com), go to the **Compliance Policies** page.</span></span> <span data-ttu-id="69fc2-114">Sie können entweder eine vorhandene Kompatibilitätsrichtlinie verwenden oder eine neue erstellen.</span><span class="sxs-lookup"><span data-stu-id="69fc2-114">You can either use an existing compliance policy or create a new one.</span></span> <span data-ttu-id="69fc2-115">Wechseln Sie zu **Geräteintegrität**, und aktivieren Sie **Schutz vor Gerätebedrohungen**.</span><span class="sxs-lookup"><span data-stu-id="69fc2-115">Go to **Device Health** and enable **Device Threat Protection**.</span></span>
   <span data-ttu-id="69fc2-116">![Screenshot mit der Einstellung der Regel zum Schutz vor Gerätebedrohungen in ](../media/mtp/mtp-compliance-policy-rule.png)</span><span class="sxs-lookup"><span data-stu-id="69fc2-116">![screenshot showing the device threat protection rule setting in ](../media/mtp/mtp-compliance-policy-rule.png)</span></span>

2. <span data-ttu-id="69fc2-117">Wählen Sie die Option **Maximal zulässige Bedrohungsstufe**:</span><span class="sxs-lookup"><span data-stu-id="69fc2-117">Select the **Maximum allowed threat level**:</span></span>
   * <span data-ttu-id="69fc2-118">**Keine (geschützt)**: Dies ist die sicherste Einstellung.</span><span class="sxs-lookup"><span data-stu-id="69fc2-118">**None (Secured)**: This is the most secure.</span></span>  <span data-ttu-id="69fc2-119">Solange auf einem Gerät Bedrohungen vorhanden sind, ist kein Zugriff auf Unternehmensressourcen möglich.</span><span class="sxs-lookup"><span data-stu-id="69fc2-119">The device cannot have any threats present and still access company resources.</span></span>  <span data-ttu-id="69fc2-120">Wenn Bedrohungen gefunden werden, wird das Gerät als nicht kompatibel bewertet.</span><span class="sxs-lookup"><span data-stu-id="69fc2-120">If any threats are found, the device is evaluated as non-compliant.</span></span>  
   * <span data-ttu-id="69fc2-121">**Niedrig**: Das Gerät ist kompatibel, wenn nur Bedrohungen auf niedriger Stufe vorliegen.</span><span class="sxs-lookup"><span data-stu-id="69fc2-121">**Low**: The device is compliant if only low level threats are present.</span></span> <span data-ttu-id="69fc2-122">Durch Bedrohungen höherer Stufen wird das Gerät in einen nicht kompatiblen Status versetzt.</span><span class="sxs-lookup"><span data-stu-id="69fc2-122">Anything higher puts the device in a non-compliant status.</span></span>
   * <span data-ttu-id="69fc2-123">**Mittel**: Das Gerät ist kompatibel, wenn die auf dem Gerät gefundenen Bedrohungen niedriger oder mittlerer Stufe sind.</span><span class="sxs-lookup"><span data-stu-id="69fc2-123">**Medium**: The device is compliant if the threats found on the device are low or medium level.</span></span> <span data-ttu-id="69fc2-124">Wenn auf dem Gerät Bedrohungen hoher Stufen erkannt werden, wird es als nicht kompatibel bewertet.</span><span class="sxs-lookup"><span data-stu-id="69fc2-124">If high level threats are detected, the device is determined as non-compliant.</span></span>
   * <span data-ttu-id="69fc2-125">**Hoch**: Dies ist die am wenigsten sichere Option.</span><span class="sxs-lookup"><span data-stu-id="69fc2-125">**High**: This is the least secure.</span></span> <span data-ttu-id="69fc2-126">Diese Option lässt alle Bedrohungsstufen zu und verwendet den Lookout-Schutz vor Bedrohungen von mobilen Geräten nur zu Berichtszwecken.</span><span class="sxs-lookup"><span data-stu-id="69fc2-126">This allows all threat levels, and uses Lookout mobile threat protection for reporting purposes only.</span></span>

![Screenshot der Option für die Bedrohungsstufe für die Einstellung der Regel zum Schutz vor Gerätebedrohungen](../media/mtp/mtp-compliance-policy-setting.png)

<span data-ttu-id="69fc2-128">Wenn Sie für Office 365 oder andere Dienste Richtlinien für den bedingten Zugriff erstellen, wird diese Kompatibilitätsbewertung ausgewertet, und auf nicht kompatiblen Geräten wird der Zugriff auf Unternehmensressourcen gesperrt, bis die Bedrohung beseitigt ist.</span><span class="sxs-lookup"><span data-stu-id="69fc2-128">If you create conditional access policies for Office 365 or other services, this compliance evaluation is assessed and non-compliant devices are blocked from accessing those services until the threat is resolved.</span></span>

## <a name="monitor-device-threats"></a><span data-ttu-id="69fc2-129">Überwachen von Gerätebedrohungen</span><span class="sxs-lookup"><span data-stu-id="69fc2-129">Monitor device threats</span></span>
<span data-ttu-id="69fc2-130">Sie können den Kompatibilitätszustand eines Geräts in der **Intune-Verwaltungskonsole** auf der Seite [Alle Geräte](https://manage.microsoft.com) anzeigen.</span><span class="sxs-lookup"><span data-stu-id="69fc2-130">To see the compliance state of a device, go to the [Intune administrator console](https://manage.microsoft.com) and view **All Devices**.</span></span>

![Screenshot der Seite für Geräte in der Intune-Verwaltungskonsole mit Kompatibilitätsstatus eines Geräts](../media/mtp/mtp-device-status-intune-console.png)

## <a name="next-steps"></a><span data-ttu-id="69fc2-132">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="69fc2-132">Next steps</span></span>
* <span data-ttu-id="69fc2-133">Erstellen einer Richtlinie für bedingten Zugriff</span><span class="sxs-lookup"><span data-stu-id="69fc2-133">Create conditional access policy</span></span>
  * [<span data-ttu-id="69fc2-134">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="69fc2-134">Exchange Online</span></span>](restrict-access-to-exchange-online-with-microsoft-intune.md)
  * [<span data-ttu-id="69fc2-135">Exchange lokal</span><span class="sxs-lookup"><span data-stu-id="69fc2-135">Exchange On-premises</span></span>](restrict-access-to-exchange-onpremises-with-microsoft-intune.md)
  * [<span data-ttu-id="69fc2-136">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="69fc2-136">SharePoint Online</span></span>](restrict-access-to-sharepoint-online-with-microsoft-intune.md)
  * [<span data-ttu-id="69fc2-137">Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="69fc2-137">Skype for Business Online</span></span>](restrict-access-to-skype-for-business-online-with-microsoft-intune.md)
  * [<span data-ttu-id="69fc2-138">Dynamics CRM</span><span class="sxs-lookup"><span data-stu-id="69fc2-138">Dynamics CRM</span></span>](restrict-access-to-dynamics-crm-online-with-microsoft-intune.md)
