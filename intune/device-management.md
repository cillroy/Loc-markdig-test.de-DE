---
title: "Verwalten von Geräten mit Intune"
titleSuffix: Intune on Azure
description: "In diesem Artikel erfahren Sie, wie Sie die mit Intune verwalteten Geräte anzeigen und verschiedene Vorgänge auf diesen ausführen."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 08/31/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d2412418-d91a-4767-a3d6-bc88bb29caa2
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 941a7d17a672f9315d1d99812494650f8247b4c1
ms.sourcegitcommit: e37e916e2bf14f092d3a767bc90d68c181d739fb
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/03/2018
---
# <a name="what-is-microsoft-intune-device-management"></a><span data-ttu-id="44be0-103">Was ist die Microsoft Intune Geräteverwaltung?</span><span class="sxs-lookup"><span data-stu-id="44be0-103">What is Microsoft Intune device management?</span></span>


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="44be0-104">Als IT-Administrator müssen Sie sicherstellen, dass verwaltete Geräte die Ressourcen bereitstellen, die Ihre Endbenutzer für Ihre Arbeit benötigen, während gleichzeitig die Daten vor Risiken geschützt werden.</span><span class="sxs-lookup"><span data-stu-id="44be0-104">As an IT admin, you must ensure that managed devices are providing the resources your end users need to do their work while protecting that data from risk.</span></span>

<span data-ttu-id="44be0-105">Die Workload **Geräte** liefert Informationen zu den verwalteten Geräten und ermöglicht die Ausführung von Remoteaufgaben auf diesen Geräten.</span><span class="sxs-lookup"><span data-stu-id="44be0-105">The **Devices** workload gives you insights into the devices you manage, and lets you perform remote tasks on those devices.</span></span> <span data-ttu-id="44be0-106">So greifen Sie auf die Workload zu</span><span class="sxs-lookup"><span data-stu-id="44be0-106">To access the workload:</span></span>

1. <span data-ttu-id="44be0-107">Melden Sie sich beim Azure-Portal an.</span><span class="sxs-lookup"><span data-stu-id="44be0-107">Sign into the Azure portal.</span></span>
2. <span data-ttu-id="44be0-108">Wählen Sie **Weitere Dienste** > **Überwachung und Verwaltung** > **Intune** aus.</span><span class="sxs-lookup"><span data-stu-id="44be0-108">Choose **More Services** > **Monitoring + Management** > **Intune**.</span></span>
3. <span data-ttu-id="44be0-109">Wählen Sie in **Intune** die Option **Geräte** aus.</span><span class="sxs-lookup"><span data-stu-id="44be0-109">In **Intune**, choose **Devices**.</span></span>
4. <span data-ttu-id="44be0-110">Sie können Informationen über Geräte anzeigen und die folgenden Remotegeräteaktionen durchführen:</span><span class="sxs-lookup"><span data-stu-id="44be0-110">You can view information about devices and perform the remote device actions as follows:</span></span>
   - <span data-ttu-id="44be0-111">**Übersicht**: Eine Momentaufnahme der registrierten Geräte, die Sie verwalten können.</span><span class="sxs-lookup"><span data-stu-id="44be0-111">**Overview** - A snapshot of the enrolled devices you can manage.</span></span>
   - <span data-ttu-id="44be0-112">**Alle Geräte**: Eine Liste der registrierten Geräte, die Sie verwalten.</span><span class="sxs-lookup"><span data-stu-id="44be0-112">**All devices** - A list of the enrolled devices you manage.</span></span> <span data-ttu-id="44be0-113">Wählen Sie **Filter** oder **Spalten** aus, um die angezeigten Informationen einzuschränken.</span><span class="sxs-lookup"><span data-stu-id="44be0-113">Choose **Filter** or **Columns** to refine the information displayed.</span></span> <span data-ttu-id="44be0-114">Wählen Sie ein Gerät aus, um den [Gerätebestand](device-inventory.md) anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="44be0-114">Select a device to [view device inventory](device-inventory.md).</span></span>
   - <span data-ttu-id="44be0-115">**Azure AD-Geräte**: Eine Liste der Geräte, die in Azure Active Directory (AD) registriert oder damit verbunden sind.</span><span class="sxs-lookup"><span data-stu-id="44be0-115">**Azure AD devices** - A list of the devices registered or joined with Azure Active Directory (AD).</span></span> <span data-ttu-id="44be0-116">Weitere Informationen zur [Azure AD-Geräteverwaltung](https://docs.microsoft.com/azure/active-directory/device-management-introduction).</span><span class="sxs-lookup"><span data-stu-id="44be0-116">Learn more about [Azure AD device management](https://docs.microsoft.com/azure/active-directory/device-management-introduction).</span></span>
   - <span data-ttu-id="44be0-117">**Geräteaktionen**: Ein Verlauf der Remoteaktionen, die auf Geräten ausgeführt wurden, einschließlich die Aktion, der Status, wer die Aktion initiiert hat und der Zeitpunkt.</span><span class="sxs-lookup"><span data-stu-id="44be0-117">**Device actions** - A history of the remote actions performed on devices including the action, its status, who initiated the action, and the time.</span></span>

     ![Überwachen von Geräteaktionen](./media/monitor-device-actions.png)

   - <span data-ttu-id="44be0-119">**TeamViewer**: Über den TeamViewer-Dienst können Benutzer von mit Intune verwalteten Android-Geräten Remoteunterstützung von ihrem IT-Administrator erhalten.</span><span class="sxs-lookup"><span data-stu-id="44be0-119">**TeamViewer** - TeamViewer service allows users of Intune-managed Android devices to get remote assistance from their IT administrator.</span></span> <span data-ttu-id="44be0-120">Erfahren Sie mehr über [TeamViewer](device-profile-android-teamviewer.md).</span><span class="sxs-lookup"><span data-stu-id="44be0-120">Learn more about [TeamViewer](device-profile-android-teamviewer.md).</span></span>

## <a name="available-device-actions"></a><span data-ttu-id="44be0-121">Verfügbare Geräteaktionen</span><span class="sxs-lookup"><span data-stu-id="44be0-121">Available device actions</span></span>
<span data-ttu-id="44be0-122">Die verfügbaren Aktionen hängen von der Geräteplattform und der Konfiguration des Geräts ab.</span><span class="sxs-lookup"><span data-stu-id="44be0-122">The actions available depend on the device platform, and the configuration of the device.</span></span>

- [<span data-ttu-id="44be0-123">Anzeigen des Gerätebestands</span><span class="sxs-lookup"><span data-stu-id="44be0-123">View device inventory</span></span>](device-inventory.md)
- <span data-ttu-id="44be0-124">So führen Sie Remotegeräteaktionen durch:</span><span class="sxs-lookup"><span data-stu-id="44be0-124">Perform remote device actions:</span></span>
    - [<span data-ttu-id="44be0-125">Unternehmensdaten entfernen</span><span class="sxs-lookup"><span data-stu-id="44be0-125">Remove company data</span></span>](devices-wipe.md#remove-company-data)
    - [<span data-ttu-id="44be0-126">Zurücksetzen auf Werkseinstellungen</span><span class="sxs-lookup"><span data-stu-id="44be0-126">Factory reset</span></span>](devices-wipe.md#factory-reset)
    - [<span data-ttu-id="44be0-127">Remotesperre</span><span class="sxs-lookup"><span data-stu-id="44be0-127">Remote lock</span></span>](device-remote-lock.md)
    - [<span data-ttu-id="44be0-128">Kennung zurücksetzen</span><span class="sxs-lookup"><span data-stu-id="44be0-128">Reset passcode</span></span>](device-passcode-reset.md)
    - <span data-ttu-id="44be0-129">[Umgehen der Aktivierungssperre](device-activation-lock-bypass.md) (nur iOS)</span><span class="sxs-lookup"><span data-stu-id="44be0-129">[Bypass Activation Lock](device-activation-lock-bypass.md) (iOS only)</span></span>
    - <span data-ttu-id="44be0-130">[Sauberer Start](device-fresh-start.md) (nur Windows)</span><span class="sxs-lookup"><span data-stu-id="44be0-130">[Fresh Start](device-fresh-start.md) (Windows only)</span></span>
    - <span data-ttu-id="44be0-131">[Modus für verlorene Geräte](device-lost-mode.md) (nur iOS)</span><span class="sxs-lookup"><span data-stu-id="44be0-131">[Lost mode](device-lost-mode.md) (iOS only)</span></span>
    - <span data-ttu-id="44be0-132">[Gerät suchen](device-locate.md) (nur iOS)</span><span class="sxs-lookup"><span data-stu-id="44be0-132">[Locate device](device-locate.md) (iOS only)</span></span>
    - <span data-ttu-id="44be0-133">[Neu starten](device-restart.md) (nur Windows)</span><span class="sxs-lookup"><span data-stu-id="44be0-133">[Restart](device-restart.md) (Windows only)</span></span>
    - [<span data-ttu-id="44be0-134">Zurücksetzen der PIN unter Windows 10</span><span class="sxs-lookup"><span data-stu-id="44be0-134">Windows 10 PIN reset</span></span>](device-windows-pin-reset.md)
    - [<span data-ttu-id="44be0-135">Remotesteuerung für Android</span><span class="sxs-lookup"><span data-stu-id="44be0-135">Remote control for Android</span></span>](device-profile-android-teamviewer.md)
    - [<span data-ttu-id="44be0-136">Synchronisieren von Geräten</span><span class="sxs-lookup"><span data-stu-id="44be0-136">Synchronize device</span></span>](device-sync.md)


## <a name="next-steps"></a><span data-ttu-id="44be0-137">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="44be0-137">Next steps</span></span>

- <span data-ttu-id="44be0-138">Wählen Sie **Geräteaktionen** aus, um den Status von Aktionen auf von Ihnen verwalteten Geräten anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="44be0-138">Choose **Device Actions** to see the status of actions taken on devices you manage.</span></span>
