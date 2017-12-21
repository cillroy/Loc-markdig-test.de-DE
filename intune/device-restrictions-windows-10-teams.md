---
title: "Intune-Geräteeinschränkungen für Windows 10 Team"
titlesuffix: Azure portal
description: "In diesem Artikel erfahren Sie etwas über die verfügbaren Geräteeinschränkungen für Windows 10 Team-Geräte."
keywords: 
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 08/01/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 677c41a2-5344-4c52-85f0-809dce3a5d5b
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 776fe5e67e99ea50798813717c90d9e52cb7812a
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2017
---
# <a name="windows-10-team-device-restriction-settings-in-microsoft-intune"></a><span data-ttu-id="f0884-103">Einstellungen für Geräteeinschränkungen für Windows 10 Team in Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="f0884-103">Windows 10 Team device restriction settings in Microsoft Intune</span></span>

[!INCLUDE[azure_portal](./includes/azure_portal.md)]


## <a name="apps-and-experience"></a><span data-ttu-id="f0884-104">Apps und Benutzerfreundlichkeit</span><span class="sxs-lookup"><span data-stu-id="f0884-104">Apps and experience</span></span>

- <span data-ttu-id="f0884-105">**Bildschirm aktivieren, wenn eine Person im Raum ist:** Erlaubt das automatische Aktivieren des Geräts, wenn der Sensor eine Person im Raum erkennt.</span><span class="sxs-lookup"><span data-stu-id="f0884-105">**Wake screen when someone in room** - Allows the device to wake automatically when its sensor detects someone in the room.</span></span>
- <span data-ttu-id="f0884-106">**Anzeige von Besprechungsinformationen auf dem Willkommensbildschirm:** Aktivieren Sie diese Option, um die Informationen auszuwählen, die auf der Kachel „Besprechungen“ auf dem Willkommensbildschirm angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="f0884-106">**Meeting information displayed on welcome screen** - Enable this option to choose the information that is displayed on the Meetings tile of the Welcome screen.</span></span> <span data-ttu-id="f0884-107">Sie können:</span><span class="sxs-lookup"><span data-stu-id="f0884-107">You can:</span></span>
    - <span data-ttu-id="f0884-108">**Nur Organisator und Zeit anzeigen**</span><span class="sxs-lookup"><span data-stu-id="f0884-108">**Show organizer and time only**</span></span>
    - <span data-ttu-id="f0884-109">**Organisator, Zeit und Thema anzeigen (Thema bei privaten Besprechungen ausblenden)**</span><span class="sxs-lookup"><span data-stu-id="f0884-109">**Show organizer, time, and subject (subject hidden for private meetings)**</span></span>
- <span data-ttu-id="f0884-110">**URL für Hintergrundbild des Willkommensbildschirms:** Aktivieren Sie diese Einstellung, um auf dem **Willkommensbildschirm** von Windows 10 Team-Geräten einen benutzerdefinierten Hintergrund aus der angegebenen URL anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="f0884-110">**Welcome screen background image URL** - Enable this setting to display a custom background on the **Welcome** screen of Windows 10 Team devices from the URL you specify.</span></span><br><span data-ttu-id="f0884-111">Das Bild muss im PNG-Format vorliegen und die URL muss mit **https://** beginnen.</span><span class="sxs-lookup"><span data-stu-id="f0884-111">The image must be in PNG format and the URL must begin with **https://**.</span></span>

## <a name="azure-operational-insights"></a><span data-ttu-id="f0884-112">Azure Operational Insights</span><span class="sxs-lookup"><span data-stu-id="f0884-112">Azure operational insights</span></span>

- <span data-ttu-id="f0884-113">**Azure Operational Insights:** Azure Operational Insights ist Teil der Microsoft Operations Manager-Suite und sammelt, speichert und analysiert Protokolldateidaten von Windows 10-Team-Geräten.</span><span class="sxs-lookup"><span data-stu-id="f0884-113">**Azure Operational Insights** - Azure Operational Insights, part of the Microsoft Operations Manager suite collects, stores, and analyzes log file data from Windows 10 Team devices.</span></span>
<span data-ttu-id="f0884-114">Sie müssen eine **Arbeitsbereichs-ID** und einen **Arbeitsbereichsschlüssel** angeben, um die Verbindung mit Azure Operational Insights herstellen zu können.</span><span class="sxs-lookup"><span data-stu-id="f0884-114">To connect to Azure Operational insights, you must specify a **Workspace ID** and a **Workspace Key**.</span></span>

## <a name="maintenance"></a><span data-ttu-id="f0884-115">Wartung</span><span class="sxs-lookup"><span data-stu-id="f0884-115">Maintenance</span></span>

- <span data-ttu-id="f0884-116">**Wartungsfenster für Updates:** Konfiguriert das Fenster, in dem Updates am Gerät vorgenommen werden können.</span><span class="sxs-lookup"><span data-stu-id="f0884-116">**Maintenance window for updates** - Configures the window when updates can take place to the device.</span></span> <span data-ttu-id="f0884-117">Sie können die **Startzeit** des Fensters und **Dauer in Stunden** (1 bis 5 Stunden) konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="f0884-117">You can configure the **Start time** of the window and the **Duration in hours** (from 1-5 hours).</span></span>

## <a name="wireless-projection"></a><span data-ttu-id="f0884-118">Drahtlose Projektion</span><span class="sxs-lookup"><span data-stu-id="f0884-118">Wireless projection</span></span>

- <span data-ttu-id="f0884-119">**PIN für Funkprojektion:** Gibt an, ob Sie eine PIN eingeben müssen, bevor Sie die drahtlosen Projektionsfunktionen des Geräts verwenden können.</span><span class="sxs-lookup"><span data-stu-id="f0884-119">**PIN for wireless projection** - Specifies whether you must enter a PIN before you can use the wireless projection capabilities of the device.</span></span>
- <span data-ttu-id="f0884-120">**Miracast-Funkprojektion:** Aktivieren Sie diese Option, wenn Sie auf dem Gerät mit Windows 10-Team erlauben möchten, für Miracast aktivierte Geräte zum Projizieren zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="f0884-120">**Miracast wireless projection** - If you want to let the Windows 10 Team device use Miracast enabled devices to project, select this option.</span></span>
- <span data-ttu-id="f0884-121">**Miracast – drahtloser Projektionskanal**: Wählen Sie den Miracast-Kanal, der zum Herstellen der Verbindung verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="f0884-121">**Miracast wireless projection channel** - Choose the Miracast channel that will be used to establish the connection.</span></span>


## <a name="next-steps"></a><span data-ttu-id="f0884-122">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="f0884-122">Next steps</span></span>

<span data-ttu-id="f0884-123">Verwenden Sie die Informationen unter [Konfigurieren von Einstellungen für Geräteeinschränkungen](device-restrictions-configure.md), um das Profil zu speichern und es Benutzern und Geräten zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="f0884-123">Use the information in [How to configure device restriction settings](device-restrictions-configure.md) to save, and assign the profile to users and devices.</span></span>
