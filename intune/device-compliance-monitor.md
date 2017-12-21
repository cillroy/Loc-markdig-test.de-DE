---
title: "So überwachen Sie die Gerätekompatibilität"
titlesuffix: Azure portal
description: "Erfahren Sie, wie Sie die Gerätekonformität überwachen.\""
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 12/07/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 0790934b-48b9-435b-a8aa-e83ed5b73191
ms.reviewer: muhosabe
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 65b156923a38d9b3d976604819ede300f063a88b
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2017
---
# <a name="how-to-monitor-device-compliance-in-intune"></a><span data-ttu-id="03975-103">Überwachen der Gerätekonformität in Intune</span><span class="sxs-lookup"><span data-stu-id="03975-103">How to monitor device compliance in Intune</span></span>

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="03975-104">Sie können sich auf dem Blatt **Übersicht** eine Zusammenfassung des Status Ihrer **Konformitätsprofile** ansehen.</span><span class="sxs-lookup"><span data-stu-id="03975-104">You can view the summary of the status of your **compliance profiles** in the **Overview** blade.</span></span>
<span data-ttu-id="03975-105">Sie können interaktiv einen Drilldown in den Diagrammen durchführen, um Details anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="03975-105">You can interactively click through the charts to drill down into the details.</span></span> <span data-ttu-id="03975-106">Wenn Sie mehrere Konformitätsprofile konfiguriert haben, können Sie den Status für jede Richtlinie anzeigen, indem Sie auf dem Blatt „Richtlinie“ im Abschnitt **Verwalten** die Option **Berichte** auswählen.</span><span class="sxs-lookup"><span data-stu-id="03975-106">If you have multiple compliance profiles configured, you can also view the status for each policy by going to the policy blade and choosing **Reports** in the **Manage** section.</span></span>  <span data-ttu-id="03975-107">Die Details der verfügbaren Berichte werden unten aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="03975-107">The details of the reports available are listed below.</span></span>

##  <a name="device-compliance"></a><span data-ttu-id="03975-108">Gerätekompatibilität</span><span class="sxs-lookup"><span data-stu-id="03975-108">Device compliance</span></span>

<span data-ttu-id="03975-109">Die Zusammenfassung des Gerätekonformitätsberichts zeigt zusammengestellte Informationen zur Anzahl der Geräte, für die einer der folgenden Status gemeldet wurde:</span><span class="sxs-lookup"><span data-stu-id="03975-109">The summarized view of the device compliance report shows starts with showing you the aggregated information about the number of devices that are reporting as one of the following:</span></span>

- <span data-ttu-id="03975-110">**Kompatibel:** Das Gerät wurde vor Kurzem auf Konformität überprüft und als konform mit den Einstellungen des angegebenen Konformitätsprofils bewertet.</span><span class="sxs-lookup"><span data-stu-id="03975-110">**Compliant**: Device has been evaluated for compliance recently and has been determined as compliant with the compliance profile settings you specified.</span></span>
- <span data-ttu-id="03975-111">**Nicht kompatibel:**: Das Gerät wurde überprüft und als nicht konform bewertet.</span><span class="sxs-lookup"><span data-stu-id="03975-111">**Noncompliant**: The device has been evaluated and determined as noncompliant.</span></span>  <span data-ttu-id="03975-112">Wenn im Profil eine Karenzzeit angegeben wurde, ist diese abgelaufen, und das Gerät hat damit in einen nicht konformen Status.</span><span class="sxs-lookup"><span data-stu-id="03975-112">If there was a grace period specified in the profile, the grace period has expired putting the device in a noncompliant status.</span></span>
- <span data-ttu-id="03975-113">**Karenzzeit:** Das Gerät wurde überprüft und als nicht konform bewertet.</span><span class="sxs-lookup"><span data-stu-id="03975-113">**Grace period**: Device has been evaluated and determined as noncompliant.</span></span> <span data-ttu-id="03975-114">Die Karenzzeit gilt jedoch immer noch, bis das Gerät als nicht konform gekennzeichnet wird.</span><span class="sxs-lookup"><span data-stu-id="03975-114">However, the grace period still applies before the device is actually marked as noncompliant.</span></span>

<span data-ttu-id="03975-115">Sie können in jedem Abschnitt einen Drilldown durchführen, um weitere Details zu den einzelnen Geräten und Benutzern anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="03975-115">You can drill down on each section to see more details on the individual devices and users.</span></span>

## <a name="setting-compliance"></a><span data-ttu-id="03975-116">Einstellungskonformität</span><span class="sxs-lookup"><span data-stu-id="03975-116">Setting compliance</span></span>

<span data-ttu-id="03975-117">Der Einstellungskonformitätsbericht enthält Einzelheiten zu jeder Konformitätseinstellung. Beispiele:</span><span class="sxs-lookup"><span data-stu-id="03975-117">The setting compliance report provides the details for each compliance settings such as:</span></span>

- <span data-ttu-id="03975-118">Anzahl der Geräte, die mit der Einstellung nicht konform sind</span><span class="sxs-lookup"><span data-stu-id="03975-118">Number of devices that are noncompliant with the setting.</span></span>
- <span data-ttu-id="03975-119">Die Plattform, auf der die Einstellung angewendet wird</span><span class="sxs-lookup"><span data-stu-id="03975-119">The platform that the setting is applied to.</span></span>

<span data-ttu-id="03975-120">Sie können für jede Einstellung einen Drilldown durchführen, um weitere Informationen zu den Profilen, für die diese Einstellungen aktiviert wurden, und den Werten der Einstellungen zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="03975-120">You can drill down on each of the setting to see more information about the profiles on which these settings have been enabled, and the value of the setting.</span></span>
