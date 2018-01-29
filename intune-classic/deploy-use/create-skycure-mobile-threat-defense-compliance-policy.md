---
title: "Erstellen der Skycure Mobile Threat Defense-Kompatibilitätsrichtlinie"
description: "Erstellen Sie die Skycure Mobile Threat Defense-Kompatibilitätsrichtlinie im klassischen Intune-Portal."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 03/16/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 56ff1728-1119-4e8a-aae6-ed5c7fafa052
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 72a2179f5c788a252313220fd9e130db13cd0d4a
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2018
---
# <a name="create-skycure-mobile-threat-defense-compliance-policy"></a><span data-ttu-id="33082-103">Erstellen der Skycure Mobile Threat Defense-Kompatibilitätsrichtlinie</span><span class="sxs-lookup"><span data-stu-id="33082-103">Create Skycure Mobile Threat Defense compliance policy</span></span>

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="33082-104">Dank Intune mit Skycure Mobile Threat Defense können Sie Bedrohungen auf mobilen Geräten erkennen und das Risiko auf solchen Geräten bewerten.</span><span class="sxs-lookup"><span data-stu-id="33082-104">Intune with Skycure Mobile Threat Defense lets you detect threats on mobile devices and assess risk on those devices.</span></span> <span data-ttu-id="33082-105">Sie können eine Regel für eine Intune-Kompatibilitätsrichtlinie erstellen, mit der das Risiko bewertet wird, um zu ermitteln, ob das Gerät kompatibel ist.</span><span class="sxs-lookup"><span data-stu-id="33082-105">You can create an Intune compliance policy rule that assesses risk to determine if the device is compliant.</span></span> <span data-ttu-id="33082-106">Anschließend können Sie die Richtlinie für bedingten Zugriff verwenden, um den Zugriff auf Dienste basierend auf der Gerätekompatibilität zuzulassen oder zu blockieren.</span><span class="sxs-lookup"><span data-stu-id="33082-106">You can then use conditional access policy to block access to services based on device compliance.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="33082-107">Vorbereitung</span><span class="sxs-lookup"><span data-stu-id="33082-107">Before you begin</span></span>

<span data-ttu-id="33082-108">Voraussetzungen für die Kompatibilitätsrichtlinie mit dem Skycure-Schutz vor Gerätebedrohungen:</span><span class="sxs-lookup"><span data-stu-id="33082-108">Prerequisites for compliance policy with Skycure device threat protection:</span></span>

-   [<span data-ttu-id="33082-109">Einrichten der Skycure-Integration in Intune</span><span class="sxs-lookup"><span data-stu-id="33082-109">Set up Skycure integration with Intune</span></span>](/intune-classic/deploy-use/setup-the-skycure-integration-with-Intune)

-   [<span data-ttu-id="33082-110">Aktivieren der Skycure-Verbindung in Intune</span><span class="sxs-lookup"><span data-stu-id="33082-110">Enable the Skycure connection in Intune</span></span>](/intune-classic/deploy-use/enable-skycure-mobile-threat-defense-in-intune)

<span data-ttu-id="33082-111">Beim Einrichten von Skycure Mobile Threat Defense haben Sie in der Skycure-Konsole eine Richtlinie erstellt, die verschiedene Bedrohungen als hoch, mittel und niedrig klassifiziert.</span><span class="sxs-lookup"><span data-stu-id="33082-111">As part of the Skycure Mobile Threat Defense setup, in the Skycure console, you created a policy that classifies various threats as high, medium and low.</span></span> <span data-ttu-id="33082-112">Nun müssen Sie die maximal zulässige Bedrohungsstufe in der Intune-Kompatibilitätsrichtlinie festlegen.</span><span class="sxs-lookup"><span data-stu-id="33082-112">You now need to set the maximum allowed threat level in the Intune compliance policy.</span></span>

## <a name="to-create-skycure-compliance-policy"></a><span data-ttu-id="33082-113">Erstellen der Skycure-Kompatibilitätsrichtlinie</span><span class="sxs-lookup"><span data-stu-id="33082-113">To create Skycure compliance policy</span></span>

1.  <span data-ttu-id="33082-114">Wechseln Sie zum [klassischen Intune-Portal](https://manage.microsoft.com/), und geben Sie Ihre Anmeldeinformationen ein.</span><span class="sxs-lookup"><span data-stu-id="33082-114">Go to the [Intune classic portal](https://manage.microsoft.com/) then enter your credentials.</span></span>

2.  <span data-ttu-id="33082-115">Wählen Sie **Richtlinie** &gt; **Kompatibilitätsrichtlinien** aus.</span><span class="sxs-lookup"><span data-stu-id="33082-115">Choose **Policy** &gt; **Compliance Policies**.</span></span> <span data-ttu-id="33082-116">Sie können entweder eine vorhandene Kompatibilitätsrichtlinie verwenden oder eine neue erstellen.</span><span class="sxs-lookup"><span data-stu-id="33082-116">You can either use an existing compliance policy or create a new one.</span></span>

3.  <span data-ttu-id="33082-117">Wählen Sie **Hinzufügen** &gt; **Device Health** (Integrität für Geräte), und aktivieren Sie **Schutz vor Gerätebedrohungen**.</span><span class="sxs-lookup"><span data-stu-id="33082-117">Choose **Add** &gt; **Device Health**, then enable **Device Threat Protection**.</span></span>

4.  <span data-ttu-id="33082-118">Wählen Sie die Option **Maximal zulässige Bedrohungsstufe**:</span><span class="sxs-lookup"><span data-stu-id="33082-118">Select the **Maximum allowed threat level**:</span></span>

    <span data-ttu-id="33082-119">ein.</span><span class="sxs-lookup"><span data-stu-id="33082-119">a.</span></span>  <span data-ttu-id="33082-120">**Keine (geschützt)**: Dies ist die sicherste Einstellung.</span><span class="sxs-lookup"><span data-stu-id="33082-120">**None (Secured)**: This is the most secure.</span></span> <span data-ttu-id="33082-121">Solange auf einem Gerät Bedrohungen vorhanden sind, ist kein Zugriff auf Unternehmensressourcen möglich.</span><span class="sxs-lookup"><span data-stu-id="33082-121">The device cannot have any threats present and still access company resources.</span></span> <span data-ttu-id="33082-122">Wenn Bedrohungen gefunden werden, wird das Gerät als nicht kompatibel bewertet.</span><span class="sxs-lookup"><span data-stu-id="33082-122">If any threats are found, the device is evaluated as non-compliant.</span></span>

    <span data-ttu-id="33082-123">b.</span><span class="sxs-lookup"><span data-stu-id="33082-123">b.</span></span>  <span data-ttu-id="33082-124">**Niedrig**: Das Gerät ist kompatibel, wenn nur Bedrohungen auf niedriger Stufe vorliegen.</span><span class="sxs-lookup"><span data-stu-id="33082-124">**Low**: The device is compliant if only low level threats are present.</span></span> <span data-ttu-id="33082-125">Durch Bedrohungen höherer Stufen wird das Gerät in einen nicht kompatiblen Status versetzt.</span><span class="sxs-lookup"><span data-stu-id="33082-125">Anything higher puts the device in a non-compliant status.</span></span>

    <span data-ttu-id="33082-126">c.</span><span class="sxs-lookup"><span data-stu-id="33082-126">c.</span></span>  <span data-ttu-id="33082-127">**Mittel**: Das Gerät ist kompatibel, wenn die auf dem Gerät gefundenen Bedrohungen niedriger oder mittlerer Stufe sind.</span><span class="sxs-lookup"><span data-stu-id="33082-127">**Medium**: The device is compliant if the threats found on the device are low or medium level.</span></span> <span data-ttu-id="33082-128">Wenn auf dem Gerät Bedrohungen hoher Stufen erkannt werden, wird es als nicht kompatibel bewertet.</span><span class="sxs-lookup"><span data-stu-id="33082-128">If high level threats are detected, the device is determined as non-compliant.</span></span>

    <span data-ttu-id="33082-129">d.</span><span class="sxs-lookup"><span data-stu-id="33082-129">d.</span></span>  <span data-ttu-id="33082-130">**Hoch**: Dies ist die am wenigsten sichere Option.</span><span class="sxs-lookup"><span data-stu-id="33082-130">**High**: This is the least secure.</span></span> <span data-ttu-id="33082-131">Diese Option lässt alle Bedrohungsstufen zu und verwendet Skycure Mobile Threat Defense nur zu Berichtszwecken.</span><span class="sxs-lookup"><span data-stu-id="33082-131">This allows all threat levels, and uses Skycure mobile threat defense for reporting purposes only.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="33082-132">Wenn Sie für Office 365 oder andere Dienste Richtlinien für den bedingten Zugriff erstellen, wird diese Kompatibilitätsbewertung ausgewertet, und auf nicht kompatiblen Geräten wird der Zugriff auf Unternehmensressourcen gesperrt, bis die Bedrohung beseitigt ist.</span><span class="sxs-lookup"><span data-stu-id="33082-132">If you create conditional access policies for Office 365 or other services, this compliance evaluation is assessed and non-compliant devices are blocked from accessing those services until the threat is resolved.</span></span>

## <a name="span-idmonitor-device-threats-classanchorspan-idnext-steps-classanchorspan-idtoc477360344-classanchorspanspanspannext-steps"></a><span data-ttu-id="33082-133"><span id="monitor-device-threats" class="anchor"><span id="next-steps" class="anchor"><span id="_Toc477360344" class="anchor"></span></span></span>Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="33082-133"><span id="monitor-device-threats" class="anchor"><span id="next-steps" class="anchor"><span id="_Toc477360344" class="anchor"></span></span></span>Next steps</span></span>

-   <span data-ttu-id="33082-134">Erstellen einer Richtlinie für bedingten Zugriff für:</span><span class="sxs-lookup"><span data-stu-id="33082-134">Create a conditional access policy for:</span></span>

    -   [<span data-ttu-id="33082-135">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="33082-135">Exchange Online</span></span>](/intune-classic/deploy-use/restrict-access-to-exchange-online-with-microsoft-intune)
    -   [<span data-ttu-id="33082-136">Exchange lokal</span><span class="sxs-lookup"><span data-stu-id="33082-136">Exchange On-premises</span></span>](/intune-classic/deploy-use/restrict-access-to-exchange-onpremises-with-microsoft-intune)
    -   [<span data-ttu-id="33082-137">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="33082-137">SharePoint Online</span></span>](/intune-classic/deploy-use/restrict-access-to-sharepoint-online-with-microsoft-intune)
    -   [<span data-ttu-id="33082-138">Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="33082-138">Skype for Business Online</span></span>](/intune-classic/deploy-use/restrict-access-to-skype-for-business-online-with-microsoft-intune)
    -   [<span data-ttu-id="33082-139">Dynamics CRM</span><span class="sxs-lookup"><span data-stu-id="33082-139">Dynamics CRM</span></span>](/intune-classic/deploy-use/restrict-access-to-dynamics-crm-online-with-microsoft-intune)
