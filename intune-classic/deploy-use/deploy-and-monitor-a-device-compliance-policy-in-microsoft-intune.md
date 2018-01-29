---
title: "Bereitstellen und Überwachen einer Konformitätsrichtlinie"
description: "Befolgen Sie die schrittweisen Anweisungen in diesem Thema zum Bereitstellen und Überwachen einer Konformitätsrichtlinie für Geräte."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 11/14/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d8f246d4-0d86-4c8b-a1bf-9977985506d8
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: chrisgre
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: bcdda16626e56414cd9dc7681c834e642ef1ec0d
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2018
---
# <a name="deploy-and-monitor-a-device-compliance-policy-in-microsoft-intune"></a><span data-ttu-id="a1e29-103">Bereitstellen und Überwachen einer in Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="a1e29-103">Deploy and monitor a device compliance policy in Microsoft Intune</span></span>

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

## <a name="deploy-a-compliance-policy"></a><span data-ttu-id="a1e29-104">Bereitstellen einer Konformitätsrichtlinie</span><span class="sxs-lookup"><span data-stu-id="a1e29-104">Deploy a compliance policy</span></span>
<span data-ttu-id="a1e29-105">Stellen Sie die von Ihnen [erstellte](create-a-device-compliance-policy-in-microsoft-intune.md) Kompatibilitätsrichtlinie für eine oder mehrere Gruppen von Benutzern in Ihrer Organisation bereit.</span><span class="sxs-lookup"><span data-stu-id="a1e29-105">Deploy the compliance policy that you [created](create-a-device-compliance-policy-in-microsoft-intune.md) to one or more groups of users in your organization.</span></span> <span data-ttu-id="a1e29-106">Wenn Sie eine Kompatibilitätsrichtlinie für einen Benutzer bereitstellen, wird die Kompatibilität der Geräte des Benutzers überprüft.</span><span class="sxs-lookup"><span data-stu-id="a1e29-106">When a compliance policy is deployed to a user, the user's devices are checked for compliance.</span></span>

1.  <span data-ttu-id="a1e29-107">Wählen Sie im Arbeitsbereich **Richtlinie** die Richtlinie aus, die Sie bereitstellen möchten, und wählen Sie anschließend **Bereitstellung verwalten** aus.</span><span class="sxs-lookup"><span data-stu-id="a1e29-107">In the **Policy** workspace, select the policy you want to deploy, and then choose **Manage Deployment**.</span></span>
<span data-ttu-id="a1e29-108">![Screenshot der Seite „Kompatibilitätsrichtlinie“ mit der Menüoption „Bereitstellung verwalten“ ganz oben](./media/intune-sa-3c-deploy-compliance-policy2.png)</span><span class="sxs-lookup"><span data-stu-id="a1e29-108">![Screenshot of the compliance policy page showing the Manage Deployment menu option at the top](./media/intune-sa-3c-deploy-compliance-policy2.png)</span></span>

2.  <span data-ttu-id="a1e29-109">Wählen Sie im Dialogfeld **Bereitstellung verwalten** mindestens eine Gruppe aus, für die die Richtlinie bereitgestellt werden soll, und wählen Sie dann **Hinzufügen** > **OK** aus.</span><span class="sxs-lookup"><span data-stu-id="a1e29-109">In the **Manage Deployment** dialog box, choose one or more groups to which you want to deploy the policy, and then choose **Add** > **OK**.</span></span>
<span data-ttu-id="a1e29-110">![Screenshot des Dialogfelds „Bereitstellung verwalten“](./media/intune-sa-3d-deploy-compliance-policy3-Manage.png) Verwenden Sie bereits erstellte und mit Intune synchronisierte Active Directory-Gruppen aus, oder erstellen Sie diese Gruppen manuell in der Intune-Konsole.</span><span class="sxs-lookup"><span data-stu-id="a1e29-110">![Screenshot of the Manage Deployment dialog box](./media/intune-sa-3d-deploy-compliance-policy3-Manage.png) Use Active Directory groups that you have already created and synced to Intune, or create these groups manually in the Intune console.</span></span> <span data-ttu-id="a1e29-111">Weitere Informationen zum Bereitstellen von Richtlinien finden Sie unter [Bereitstellen einer Konfigurationsrichtlinie](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md).</span><span class="sxs-lookup"><span data-stu-id="a1e29-111">To learn more about how to deploy policies, see [Deploy a configuration policy](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md).</span></span>

<span data-ttu-id="a1e29-112">Verwenden Sie die Statuszusammenfassung und Warnungen auf der Seite **Übersicht** des Arbeitsbereichs **Richtlinie**, um Probleme mit der Richtlinie zu identifizieren, die Ihre Aufmerksamkeit erfordern.</span><span class="sxs-lookup"><span data-stu-id="a1e29-112">Use the status summary and alerts on the **Overview** page of the **Policy** workspace to identify problems with the policy that need your attention.</span></span> <span data-ttu-id="a1e29-113">Darüber hinaus wird eine Statusübersicht im Arbeitsbereich **Dashboard** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a1e29-113">Additionally, a status summary appears in the **Dashboard** workspace.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a1e29-114">Wenn Sie keine Kompatibilitätsrichtlinie bereitgestellt haben und dann die Exchange-Richtlinie für bedingten Zugriff aktivieren, erhalten alle betreffenden Geräte Zugriff.</span><span class="sxs-lookup"><span data-stu-id="a1e29-114">If you have not deployed a compliance policy and you enable an Exchange conditional access policy, all targeted devices will have access.</span></span>

## <a name="monitor-the-compliance-policy"></a><span data-ttu-id="a1e29-115">Überwachen der Konformitätsrichtlinie</span><span class="sxs-lookup"><span data-stu-id="a1e29-115">Monitor the compliance policy</span></span>

#### <a name="to-view-devices-that-do-not-conform-to-a-compliance-policy"></a><span data-ttu-id="a1e29-116">So zeigen Sie Geräte an, die keiner Konformitätsrichtlinie entsprechen</span><span class="sxs-lookup"><span data-stu-id="a1e29-116">To view devices that do not conform to a compliance policy</span></span>

1.  <span data-ttu-id="a1e29-117">Wählen Sie in der [Microsoft Intune-Verwaltungskonsole](https://manage.microsoft.com) **Gruppen** > **Alle Geräte** aus.</span><span class="sxs-lookup"><span data-stu-id="a1e29-117">In the [Microsoft Intune administration console](https://manage.microsoft.com), choose **Groups** > **All Devices**.</span></span>

2.  <span data-ttu-id="a1e29-118">Doppelklicken Sie in der Geräteliste auf den Namen eines Geräts.</span><span class="sxs-lookup"><span data-stu-id="a1e29-118">Double-click the name of a device in the list of devices.</span></span>

3.  <span data-ttu-id="a1e29-119">Wählen Sie die Registerkarte **Richtlinie** aus, um eine Liste der Richtlinien für das Gerät anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="a1e29-119">Choose the **Policy** tab to see a list of the policies for that device.</span></span>

4.  <span data-ttu-id="a1e29-120">Wählen Sie in der Dropdownliste **Filter** die Option **Entspricht nicht der Kompatibilitätsrichtlinie** aus.</span><span class="sxs-lookup"><span data-stu-id="a1e29-120">From the **Filters** drop-down list, choose **Does not conform to compliance policy**.</span></span>
<span data-ttu-id="a1e29-121">![Screenshot mit der Liste der Optionen in der Filterliste](./media/intune-sa-3e-view-device-noncompliance.png)</span><span class="sxs-lookup"><span data-stu-id="a1e29-121">![Screenshot that shows the list of options in the filters list](./media/intune-sa-3e-view-device-noncompliance.png)</span></span>

#### <a name="to-view-the-health-attestation-reports"></a><span data-ttu-id="a1e29-122">So zeigen Sie die Integritätsnachweisberichte an</span><span class="sxs-lookup"><span data-stu-id="a1e29-122">To view the health attestation reports</span></span>

1.  <span data-ttu-id="a1e29-123">Wählen Sie in der [Microsoft Intune-Verwaltungskonsole](https://manage.microsoft.com) die Option **Berichte** aus.</span><span class="sxs-lookup"><span data-stu-id="a1e29-123">In the [Microsoft Intune administration console](https://manage.microsoft.com), choose **Reports**.</span></span>

2.  <span data-ttu-id="a1e29-124">Auf der Seite **Integritätsnachweisbericht - Neuen Bericht erstellen** können Sie einen Bericht mit allen von Intune erfassten Windows 10-Integritätsnachweisdaten anzeigen.</span><span class="sxs-lookup"><span data-stu-id="a1e29-124">On the **Health Attestation Report - Create a new report** page, you can view a report with all the Windows 10 health attestation data that Intune has collected.</span></span> <span data-ttu-id="a1e29-125">Sie können mithilfe von Filtern auch einen Bericht für eine Teilmenge der Daten erstellen.</span><span class="sxs-lookup"><span data-stu-id="a1e29-125">You can also create a report with a subset of the data by using filters.</span></span> <span data-ttu-id="a1e29-126">Die Filter können auf dem Gerätetyp, Betriebssystem oder auf einer Teilmenge der Datenpunkte basieren.</span><span class="sxs-lookup"><span data-stu-id="a1e29-126">The filters can be based on the type of device, the operating system, or only a subset of data points.</span></span>

## <a name="how-intune-resolves-policy-conflicts"></a><span data-ttu-id="a1e29-127">Wie Intune-Richtlinienkonflikte löst</span><span class="sxs-lookup"><span data-stu-id="a1e29-127">How Intune resolves policy conflicts</span></span>
<span data-ttu-id="a1e29-128">Richtlinienkonflikte können auftreten, wenn mehrere Intune-Richtlinien auf ein Gerät angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="a1e29-128">Policy conflicts can occur when multiple Intune policies are applied to a device.</span></span> <span data-ttu-id="a1e29-129">Wenn sich Richtlinieneinstellungen überschneiden, löst Intune Konflikte nach den folgenden Regeln:</span><span class="sxs-lookup"><span data-stu-id="a1e29-129">If the policy settings overlap, Intune resolves any conflicts by using the following rules:</span></span>

-   <span data-ttu-id="a1e29-130">Wenn die in Konflikt stehenden Einstellungen zu einer Intune-Konfigurationsrichtlinie und einer Kompatibilitätsrichtlinie gehören, haben die Einstellungen in der Kompatibilitätsrichtlinie Vorrang vor den Einstellungen in der Konfigurationsrichtlinie.</span><span class="sxs-lookup"><span data-stu-id="a1e29-130">If the conflicting settings are from an Intune configuration policy and a compliance policy, the settings in the compliance policy take precedence over the settings in the configuration policy.</span></span> <span data-ttu-id="a1e29-131">Dies geschieht auch, wenn die Einstellungen in der Konfigurationsrichtlinie sicherer sind.</span><span class="sxs-lookup"><span data-stu-id="a1e29-131">This happens even if the settings in the configuration policy are more secure.</span></span>

-   <span data-ttu-id="a1e29-132">Wenn Sie mehrere Kompatibilitätsrichtlinien bereitgestellt haben, verwendet Intune die sichersten dieser Richtlinien.</span><span class="sxs-lookup"><span data-stu-id="a1e29-132">If you have deployed multiple compliance policies, Intune will use the most secure of these policies.</span></span>

## <a name="next-steps"></a><span data-ttu-id="a1e29-133">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="a1e29-133">Next steps</span></span>
<span data-ttu-id="a1e29-134">Wie Sie die Kompatibilitätsrichtlinie zusammen mit Richtlinien für bedingten Zugriff verwenden können, um den Zugriff auf Dienste in Ihrer Organisation zu steuern, erfahren Sie unter [Beschränken des Zugriffs auf E-Mail- und Office 365-Dienste](restrict-access-to-email-and-o365-services-with-microsoft-intune.md).</span><span class="sxs-lookup"><span data-stu-id="a1e29-134">To learn how to use the compliance policy with conditional access policies to control access to services in your organization, see [Restrict access to email and O365 services](restrict-access-to-email-and-o365-services-with-microsoft-intune.md).</span></span>


### <a name="see-also"></a><span data-ttu-id="a1e29-135">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="a1e29-135">See also</span></span>
[<span data-ttu-id="a1e29-136">Einführung in Richtlinien zur Gerätekompatibilität in Intune</span><span class="sxs-lookup"><span data-stu-id="a1e29-136">Introduction to device compliance polices in Intune</span></span>](introduction-to-device-compliance-policies-in-microsoft-intune.md)
