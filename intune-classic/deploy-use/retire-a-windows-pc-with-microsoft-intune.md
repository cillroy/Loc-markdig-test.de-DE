---
title: Abkoppeln eines Windows-PCs
description: Abkoppeln eines mit Intune verwalteten Windows-PCs.
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 12/15/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5c916182-d99c-44c5-a779-3f596f261c40
ms.reviewer: owenyen
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 99dc86bf20a50710cf1661702d46a3124861a619
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2018
---
# <a name="retire-a-windows-pc"></a><span data-ttu-id="5ed5f-103">Abkoppeln eines Windows-PCs</span><span class="sxs-lookup"><span data-stu-id="5ed5f-103">Retire a Windows PC</span></span>

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="5ed5f-104">Gehen Sie folgendermaßen vor, um Desktops abzukoppeln, die durch Ausführen des Intune-Softwareclients als PCs verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="5ed5f-104">Use the following steps to retire desktops that you are managing as PCs by running the Intune software client on them.</span></span> <span data-ttu-id="5ed5f-105">Wenn Sie einen PC abkoppeln, wird dieser aus der Intune-Verwaltung entfernt.</span><span class="sxs-lookup"><span data-stu-id="5ed5f-105">When you retire a PC, it removes it from Intune management.</span></span> <span data-ttu-id="5ed5f-106">Ein PC kann von Intune aus nicht auf die ursprünglichen Werkseinstellungen zurückgesetzt werden.</span><span class="sxs-lookup"><span data-stu-id="5ed5f-106">You cannot factory reset a PC from Intune to set it back to its original factory settings.</span></span>

1.  <span data-ttu-id="5ed5f-107">Wählen Sie in der [Microsoft Intune-Verwaltungskonsole](https://manage.microsoft.com/) die Option **Gruppen** &gt; **Alle Geräte** aus (oder eine andere Gruppe, in der der PC enthalten ist, den Sie abkoppeln möchten).</span><span class="sxs-lookup"><span data-stu-id="5ed5f-107">In the [Microsoft Intune administration console](https://manage.microsoft.com/), choose **Groups** &gt; **All Devices** (or another group that contains the PC you want to retire).</span></span>

2.  <span data-ttu-id="5ed5f-108">Wählen Sie die Geräte aus, die Sie abkoppeln möchten, und wählen Sie dann **Abkoppeln/Zurücksetzen** aus.</span><span class="sxs-lookup"><span data-stu-id="5ed5f-108">Select the devices you want to retire, and then choose **Retire/Wipe**.</span></span>

<span data-ttu-id="5ed5f-109">Installieren Sie zum erneuten Registrieren eines PC bei Intune den Softwareclient erneut auf dem PC. Gehen Sie hierzu vor wie unter [Installieren des Windows-PC-Clients mit Microsoft Intune](install-the-windows-pc-client-with-microsoft-intune.md) beschrieben.</span><span class="sxs-lookup"><span data-stu-id="5ed5f-109">To re-enroll a PC into Intune, reinstall the software client on the PC using guidance in [Install the Windows PC client with Microsoft Intune](install-the-windows-pc-client-with-microsoft-intune.md).</span></span>

<span data-ttu-id="5ed5f-110">Wenn von einem PC keine Verbindung mit Intune hergestellt werden kann, wird im Arbeitsbereich **Dashboard** eine Meldung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="5ed5f-110">If a PC cannot connect to Intune, a message is displayed in the **Dashboard** workspace.</span></span>

<span data-ttu-id="5ed5f-111">Wenn Sie einen PC abkoppeln, werden folgende Aktionen ausgeführt:</span><span class="sxs-lookup"><span data-stu-id="5ed5f-111">When you retire a PC:</span></span>

-   <span data-ttu-id="5ed5f-112">Der PC wird aus Intune-Verwaltung und -Inventar entfernt, und die dem PC zugeordnete Lizenz steht zur erneuten Verwendung zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="5ed5f-112">It is removed from the Intune management and inventory, and the license associated with the PC is made available for re-use.</span></span> <span data-ttu-id="5ed5f-113">Durch „Abkoppeln/Zurücksetzen“ wird der Intune-Softwareclient vom PC entfernt, es werden aber keine Apps oder Daten gelöscht.</span><span class="sxs-lookup"><span data-stu-id="5ed5f-113">Retire/Wipe removes the Intune software client but does not remove apps or data from the PC.</span></span> <span data-ttu-id="5ed5f-114">Durch diese Abkopplung wird keine vollständige Zurücksetzung auf dem PC ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="5ed5f-114">This retirement does not perform a full wipe on the PC.</span></span>

-   <span data-ttu-id="5ed5f-115">Der Status des Computers wird nicht mehr in der Intune-Konsole angezeigt.</span><span class="sxs-lookup"><span data-stu-id="5ed5f-115">Its status no longer displays in the Intune console.</span></span>

-   <span data-ttu-id="5ed5f-116">Intune entfernt den Softwareclient vom PC.</span><span class="sxs-lookup"><span data-stu-id="5ed5f-116">Intune removes the software client from the PC.</span></span> <span data-ttu-id="5ed5f-117">Wenn der PC nicht mit Intune verbunden ist, wird der Softwareclient nach der nächsten Verbindungsherstellung entfernt.</span><span class="sxs-lookup"><span data-stu-id="5ed5f-117">If the PC is not connected to the Intune service, the software client will be removed next time it connects.</span></span>

-   <span data-ttu-id="5ed5f-118">Microsoft Intune Endpoint Protection wird vom PC entfernt.</span><span class="sxs-lookup"><span data-stu-id="5ed5f-118">Microsoft Intune Endpoint Protection is removed from the PC.</span></span> <span data-ttu-id="5ed5f-119">Wenn auf dem PC eine andere Endpunktanwendung installiert, aber deaktiviert ist, kann sie unter Umständen nach dem Entfernen von Microsoft Intune Endpoint Protection wieder aktiviert werden, um sicherzustellen, dass Ihr PC geschützt ist.</span><span class="sxs-lookup"><span data-stu-id="5ed5f-119">If the PC has another endpoint application installed and it is disabled, that application can be re-enabled after Microsoft Intune Endpoint Protection is removed to ensure that your PC are protected.</span></span>

-   <span data-ttu-id="5ed5f-120">Alle vorhandenen Richtlinien werden vom PC entfernt, und die durch die Richtlinie festgelegten Werte werden geändert.</span><span class="sxs-lookup"><span data-stu-id="5ed5f-120">Any policies are removed from the PC and the values that were set by the policy will be changed.</span></span>

-   <span data-ttu-id="5ed5f-121">Der PC erhält vom Intune-Dienst keine weiteren Softwareupdates oder aktualisierten Schadsoftwaredefinitionen.</span><span class="sxs-lookup"><span data-stu-id="5ed5f-121">The PC no longer receives software updates or malware definition updates from the Intune service.</span></span>

-   <span data-ttu-id="5ed5f-122">Abgekoppelte PCs können je nach Konfiguration weiterhin Updates über Windows Server Update Services, Windows Update oder Microsoft Update empfangen.</span><span class="sxs-lookup"><span data-stu-id="5ed5f-122">Depending on how they are configured, retired PC can continue to receive updates by using Windows Server Update Services, Windows Update, or Microsoft Update.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="5ed5f-123">Wurde die Clientsoftware mithilfe eines Gruppenrichtlinienobjekts installiert, dann müssen Sie zuerst das Gruppenrichtlinienobjekt entfernen, bevor Sie die Clientsoftware entfernen können. So wird verhindert, dass die Software erneut installiert wird.</span><span class="sxs-lookup"><span data-stu-id="5ed5f-123">If the client software was installed by using a Group Policy Object (GPO), you must remove the Group Policy Object (GPO) before you can remove the client software to prevent the software from being reinstalled.</span></span>

    <span data-ttu-id="5ed5f-124">Wenn der Endpoint Protection-Client nicht deinstalliert werden kann, finden Sie hilfreiche Informationen unter [Problembehandlung für Endpoint Protection](/intune-classic/troubleshoot/troubleshoot-endpoint-protection-in-microsoft-intune).</span><span class="sxs-lookup"><span data-stu-id="5ed5f-124">If the Endpoint Protection client fails to uninstall, read [Troubleshoot Endpoint Protection](/intune-classic/troubleshoot/troubleshoot-endpoint-protection-in-microsoft-intune) for more help.</span></span>

### <a name="see-also"></a><span data-ttu-id="5ed5f-125">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="5ed5f-125">See also</span></span>

[<span data-ttu-id="5ed5f-126">Allgemeine Aufgaben zur Verwaltung von Windows-PCs mit dem Intune-Softwareclient</span><span class="sxs-lookup"><span data-stu-id="5ed5f-126">Common Windows PC management tasks with the Intune software client</span></span>](common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client.md)