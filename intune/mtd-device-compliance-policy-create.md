---
title: "Erstellen einer Mobile Threat Defense-Gerätekompatibilitätsrichtlinie mit Intune"
titlesuffix: Azure portal
description: "Erstellen einer Mobile Threat Defense-Gerätekompatibilitätsrichtlinie in Intune"
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 06/21/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5d12254f-ffab-4792-b19c-ab37f5e02f35
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 2e9b1a3dc42a9c18d61fc9b55d5a7b71f00c3e29
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2017
---
# <a name="create-mobile-threat-defense-mtd-device-compliance-policy-with-intune"></a><span data-ttu-id="7135b-103">Erstellen einer Mobile Threat Defense-Gerätekompatibilitätsrichtlinie (MTD) mit Intune</span><span class="sxs-lookup"><span data-stu-id="7135b-103">Create Mobile Threat Defense (MTD) device compliance policy with Intune</span></span>

> [!NOTE] 
> <span data-ttu-id="7135b-104">Dieses Thema gilt für alle Mobile Threat Defense-Partner.</span><span class="sxs-lookup"><span data-stu-id="7135b-104">This topic applies to all Mobile Threat Defense partners.</span></span>

<span data-ttu-id="7135b-105">Intune mit MTD hilft Ihnen dabei, Bedrohungen zu erkennen und Risiken auf mobilen Geräten zu bewerten.</span><span class="sxs-lookup"><span data-stu-id="7135b-105">Intune with MTD helps you detect threats and assess risk on mobile devices.</span></span> <span data-ttu-id="7135b-106">Sie können eine Regel für eine Intune-Gerätekompatibilitätsrichtlinie erstellen, mit der das Risiko bewertet wird, um zu ermitteln, ob das Gerät kompatibel ist oder nicht.</span><span class="sxs-lookup"><span data-stu-id="7135b-106">You can create an Intune device compliance policy rule that assesses risk to determine if the device is compliant or not.</span></span> <span data-ttu-id="7135b-107">Anschließend können Sie eine Richtlinie für bedingten Zugriff verwenden, um den Zugriff auf Dienste basierend auf der Gerätekompatibilität zu gewähren oder zu blockieren.</span><span class="sxs-lookup"><span data-stu-id="7135b-107">You can then use a conditional access policy to block access to services based on device compliance.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="7135b-108">Vorbereitung</span><span class="sxs-lookup"><span data-stu-id="7135b-108">Before you begin</span></span>

<span data-ttu-id="7135b-109">Beim Einrichten von MTD haben Sie in der MTD-Partnerkonsole eine Richtlinie erstellt, die verschiedene Bedrohungen als hoch, mittel und niedrig klassifiziert.</span><span class="sxs-lookup"><span data-stu-id="7135b-109">As part of the MTD setup, in the MTD partner console, you created a policy that classifies various threats as high, medium and low.</span></span> <span data-ttu-id="7135b-110">Nun müssen Sie Mobile Threat Defense-Stufe in der Intune-Gerätekompatibilitätsrichtlinie festlegen.</span><span class="sxs-lookup"><span data-stu-id="7135b-110">You now need to set the Mobile Threat Defense level in the Intune device compliance policy.</span></span>

<span data-ttu-id="7135b-111">Voraussetzungen für die Gerätekompatibilitätsrichtlinie mit MTD:</span><span class="sxs-lookup"><span data-stu-id="7135b-111">Prerequisites for device compliance policy with MTD:</span></span>

-   <span data-ttu-id="7135b-112">Einrichten der MTD-Integration in Intune</span><span class="sxs-lookup"><span data-stu-id="7135b-112">Set up MTD integration with Intune</span></span>

## <a name="to-create-a-mtd-device-compliance-policy"></a><span data-ttu-id="7135b-113">So erstellen Sie eine MTD-Gerätekompatibilitätsrichtlinie</span><span class="sxs-lookup"><span data-stu-id="7135b-113">To create a MTD device compliance policy</span></span>

1.  <span data-ttu-id="7135b-114">Melden Sie sich im [Azure-Portal](https://portal.azure.com/) mit Ihren Intune-Anmeldeinformationen an.</span><span class="sxs-lookup"><span data-stu-id="7135b-114">Go to the [Azure portal](https://portal.azure.com/), and sign in with your Intune credentials.</span></span>

2.  <span data-ttu-id="7135b-115">Wählen Sie im **Azure-Dashboard** im linken Menü **Weitere Dienste** aus, und geben Sie in das Filtertextfeld **Intune** ein.</span><span class="sxs-lookup"><span data-stu-id="7135b-115">On the **Azure Dashboard**, choose **More services** from the left menu, then type **Intune** in the text box filter.</span></span>

3.  <span data-ttu-id="7135b-116">Wählen Sie **Intune** aus. Das **Intune-Dashboard** wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="7135b-116">Choose **Intune**, the **Intune Dashboard** opens.</span></span>

4. <span data-ttu-id="7135b-117">Wählen Sie im **Intune-Dashboard** **Gerätekompatibilität** und dann im Abschnitt **Verwalten** die Option **Richtlinien** aus.</span><span class="sxs-lookup"><span data-stu-id="7135b-117">On the **Intune Dashboard**, choose **Device compliance**, then choose **Policies** under the **Manage** section.</span></span>

5.  <span data-ttu-id="7135b-118">Wählen Sie **Richtlinie erstellen** aus, geben Sie den **Namen** und die **Beschreibung** der Gerätekompatibilität ein, wählen Sie die **Plattform** aus, und wählen Sie dann **Konfigurieren** im Abschnitt **Einstellungen** aus.</span><span class="sxs-lookup"><span data-stu-id="7135b-118">Choose **Create policy**, enter the device compliance **Name**, **Description**, select the **Platform**, then choose **Configure** under the **Settings** section.</span></span>

6.  <span data-ttu-id="7135b-119">Wählen Sie auf dem Blatt **Kompatibilitätsrichtlinie** **Geräteintegrität** aus.</span><span class="sxs-lookup"><span data-stu-id="7135b-119">On the **compliance policy** blade, choose **Device Health**.</span></span>

7.  <span data-ttu-id="7135b-120">Wählen Sie auf dem Blatt **Geräteintegrität** die Mobile Threat-Stufe aus der Dropdownliste unter **Require the device to be at or under the Mobile threat Defense Level** (Fordern Sie, dass das Gerät maximal auf dieser Mobile Threat Defense-Stufe ist) aus.</span><span class="sxs-lookup"><span data-stu-id="7135b-120">On the **Device Health** blade, choose the Mobile Threat Level from the drop-down list under the **Require the device to be at or under the Mobile threat Defense Level**.</span></span>

    <span data-ttu-id="7135b-121">a.</span><span class="sxs-lookup"><span data-stu-id="7135b-121">a.</span></span>  <span data-ttu-id="7135b-122">**Geschützt**: Dies ist die sicherste Einstellung.</span><span class="sxs-lookup"><span data-stu-id="7135b-122">**Secured**: This is the most secure.</span></span> <span data-ttu-id="7135b-123">Solange auf einem Gerät Bedrohungen vorhanden sind, ist kein Zugriff auf Unternehmensressourcen möglich.</span><span class="sxs-lookup"><span data-stu-id="7135b-123">The device cannot have any threats present and still access company resources.</span></span> <span data-ttu-id="7135b-124">Wenn Bedrohungen gefunden werden, wird das Gerät als nicht kompatibel bewertet.</span><span class="sxs-lookup"><span data-stu-id="7135b-124">If any threats are found, the device is evaluated as non-compliant.</span></span>

    <span data-ttu-id="7135b-125">b.</span><span class="sxs-lookup"><span data-stu-id="7135b-125">b.</span></span>  <span data-ttu-id="7135b-126">**Niedrig**: Das Gerät ist kompatibel, wenn nur Bedrohungen auf niedriger Stufe vorliegen.</span><span class="sxs-lookup"><span data-stu-id="7135b-126">**Low**: The device is compliant if only low level threats are present.</span></span> <span data-ttu-id="7135b-127">Durch Bedrohungen höherer Stufen wird das Gerät in einen nicht kompatiblen Status versetzt.</span><span class="sxs-lookup"><span data-stu-id="7135b-127">Anything higher puts the device in a non-compliant status.</span></span>

    <span data-ttu-id="7135b-128">c.</span><span class="sxs-lookup"><span data-stu-id="7135b-128">c.</span></span>  <span data-ttu-id="7135b-129">**Mittel**: Das Gerät ist kompatibel, wenn die auf dem Gerät gefundenen Bedrohungen niedriger oder mittlerer Stufe sind.</span><span class="sxs-lookup"><span data-stu-id="7135b-129">**Medium**: The device is compliant if the threats found on the device are low or medium level.</span></span> <span data-ttu-id="7135b-130">Wenn auf dem Gerät Bedrohungen hoher Stufen erkannt werden, wird es als nicht kompatibel bewertet.</span><span class="sxs-lookup"><span data-stu-id="7135b-130">If high level threats are detected, the device is determined as non-compliant.</span></span>

    <span data-ttu-id="7135b-131">d.</span><span class="sxs-lookup"><span data-stu-id="7135b-131">d.</span></span>  <span data-ttu-id="7135b-132">**Hoch**: Dies ist die am wenigsten sichere Option.</span><span class="sxs-lookup"><span data-stu-id="7135b-132">**High**: This is the least secure.</span></span> <span data-ttu-id="7135b-133">Sie lässt alle Bedrohungsstufen zu und verwendet Mobile Threat Defense nur zu Berichtszwecken.</span><span class="sxs-lookup"><span data-stu-id="7135b-133">This allows all threat levels, and uses Mobile Threat Defense for reporting purposes only.</span></span> <span data-ttu-id="7135b-134">Auf Geräten muss mit dieser Einstellung die MTD-App aktiviert sein.</span><span class="sxs-lookup"><span data-stu-id="7135b-134">Devices are required to have the MTD app activated with this setting.</span></span>

8.  <span data-ttu-id="7135b-135">Klicken Sie zweimal auf **OK**, und wählen Sie dann **Erstellen** aus.</span><span class="sxs-lookup"><span data-stu-id="7135b-135">Click **OK** twice, then choose **Create**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7135b-136">Wenn Sie für Office 365 oder andere Dienste Richtlinien für den bedingten Zugriff erstellen, wird die Kompatibilitätsbewertung ausgewertet, und auf nicht kompatiblen Geräten wird der Zugriff auf Unternehmensressourcen gesperrt, bis die Bedrohung auf dem Gerät beseitigt ist.</span><span class="sxs-lookup"><span data-stu-id="7135b-136">If you create conditional access policies for Office 365 or other services, the device compliance evaluation is assessed and non-compliant devices are blocked from accessing corporate resources until the threat is resolved in the device.</span></span>

## <a name="to-assign-a-mtd-device-compliance-policy"></a><span data-ttu-id="7135b-137">So weisen Sie eine MTD-Gerätekompatibilitätsrichtlinie zu</span><span class="sxs-lookup"><span data-stu-id="7135b-137">To assign a MTD device compliance policy</span></span>

<span data-ttu-id="7135b-138">Wählen Sie zum Zuweisen einer Gerätekompatibilitätsrichtlinie zu Benutzern eine Richtlinie aus, die Sie zuvor konfiguriert haben.</span><span class="sxs-lookup"><span data-stu-id="7135b-138">To assign a device compliance policy to users, choose a policy that you have previously configured.</span></span> <span data-ttu-id="7135b-139">Vorhandene Richtlinien finden Sie auf dem Blatt **Gerätekompatibilitätsrichtlinien**.</span><span class="sxs-lookup"><span data-stu-id="7135b-139">Existing policies can be found in the **Device Compliance policies** blade.</span></span>

1. <span data-ttu-id="7135b-140">Wählen Sie die Richtlinie, die Sie Benutzern zuweisen möchten, und abschließend **Zuweisungen** aus.</span><span class="sxs-lookup"><span data-stu-id="7135b-140">Choose the policy you want to assign to users and choose **Assignments**.</span></span> <span data-ttu-id="7135b-141">Damit öffnen Sie das Blatt, auf dem Sie **Azure Active Directory-Sicherheitsgruppen** auswählen und der Richtlinie zuweisen können.</span><span class="sxs-lookup"><span data-stu-id="7135b-141">This opens the blade where you can select **Azure Active Directory security groups** and assign them to the policy.</span></span>

2. <span data-ttu-id="7135b-142">Wählen Sie **Gruppen auswählen** aus, um das Blatt mit den Azure AD-Sicherheitsgruppen zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="7135b-142">Choose **Select groups** to open the blade that displays the Azure AD security groups.</span></span>  <span data-ttu-id="7135b-143">Die Auswahl von **Auswählen** bewirkt die Bereitstellung der Richtlinie für Benutzer.</span><span class="sxs-lookup"><span data-stu-id="7135b-143">Choosing **Select**  deploys the policy to users.</span></span>

    > [!NOTE] 
    > <span data-ttu-id="7135b-144">Sie haben die Richtlinie auf Benutzer angewendet.</span><span class="sxs-lookup"><span data-stu-id="7135b-144">You have applied the policy to users.</span></span> <span data-ttu-id="7135b-145">Die von den Benutzern, denen die Richtlinie zugewiesen wurde, verwendeten Geräte werden auf Konformität überprüft.</span><span class="sxs-lookup"><span data-stu-id="7135b-145">The devices used by the users who are targeted by the policy will be evaluated for compliance.</span></span>

## <a name="next-steps"></a><span data-ttu-id="7135b-146">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="7135b-146">Next steps</span></span>

- [<span data-ttu-id="7135b-147">Aktivieren von Mobile Threat Defense in Intune</span><span class="sxs-lookup"><span data-stu-id="7135b-147">Enable MTD with Intune</span></span>](mtd-connector-enable.md)