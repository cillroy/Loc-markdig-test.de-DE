---
title: "Einstellungen für Windows Team-Konfigurationsrichtlinie"
description: "Verwenden Sie die **allgemeine Windows 10 Team-Konfigurationsrichtlinie** von Microsoft Intune, um Einstellungen für registrierte Windows 10 Team-Geräte (z. B. Microsoft Surface Hub) zu konfigurieren."
keywords: 
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 12/27/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 38194ef3-e26e-4682-958d-14b395fccba1
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: f3dd28b88ae2ef20963ae709c0b283c8a894551e
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2017
---
# <a name="windows-team-configuration-policy-settings-in-microsoft-intune"></a><span data-ttu-id="37bf8-103">Einstellungen für Windows Team-Konfigurationsrichtlinie in Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="37bf8-103">Windows Team configuration policy settings in Microsoft Intune</span></span>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="37bf8-104">Verwenden Sie die **allgemeine Windows 10 Team-Konfigurationsrichtlinie** von Microsoft Intune, um Einstellungen für registrierte Windows 10 Team-Geräte (z. B. Microsoft Surface Hub) zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="37bf8-104">Use the Microsoft Intune **Windows 10 Team general configuration policy** to configure settings for enrolled Windows 10 Team devices such as the Microsoft Surface Hub.</span></span>

|<span data-ttu-id="37bf8-105">Name der Einstellung</span><span class="sxs-lookup"><span data-stu-id="37bf8-105">Setting name</span></span>|<span data-ttu-id="37bf8-106">Details</span><span class="sxs-lookup"><span data-stu-id="37bf8-106">Details</span></span>|
|----------------|-----------|
|<span data-ttu-id="37bf8-107">**Zulassen der automatischen Aktivierung des Bildschirms, wenn Sensoren eine Person im Raum feststellen**</span><span class="sxs-lookup"><span data-stu-id="37bf8-107">**Allow screen to wake automatically when someone in the room**</span></span>|<span data-ttu-id="37bf8-108">Ermöglicht das automatische Aktivieren des Geräts, wenn der Sensor eine Person im Raum erkennt.</span><span class="sxs-lookup"><span data-stu-id="37bf8-108">Allows the device to wake automatically when its sensor detects someone in the room.</span></span>|
|<span data-ttu-id="37bf8-109">**PIN für Funkprojektion anfordern**</span><span class="sxs-lookup"><span data-stu-id="37bf8-109">**Require PIN for wireless projection**</span></span>|<span data-ttu-id="37bf8-110">Gibt an, ob Sie eine PIN eingeben müssen, bevor Sie die drahtlosen Projektionsfunktionen des Geräts verwenden können.</span><span class="sxs-lookup"><span data-stu-id="37bf8-110">Specifies whether you must enter a PIN before you can use the wireless projection capabilities of the device.</span></span>|
|<span data-ttu-id="37bf8-111">**Wartungsfenster für Geräteupdates festlegen**</span><span class="sxs-lookup"><span data-stu-id="37bf8-111">**Set a maintenance window for device updates**</span></span>|<span data-ttu-id="37bf8-112">Konfiguriert das Fenster, in dem Updates am Gerät vorgenommen werden können.</span><span class="sxs-lookup"><span data-stu-id="37bf8-112">Configures the window when updates can take place to the device.</span></span> <span data-ttu-id="37bf8-113">Sie können die Startzeit und Länge des Fensters (1 bis 5 Stunden) konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="37bf8-113">You can configure the start time of the window and the duration (from 1-5 hours).</span></span>|
|<span data-ttu-id="37bf8-114">**Azure Operational Insights aktivieren**</span><span class="sxs-lookup"><span data-stu-id="37bf8-114">**Enable Azure Operational Insights**</span></span>|<span data-ttu-id="37bf8-115">Azure Operational Insights ist Teil der Microsoft Operations Manager-Suite und sammelt, speichert und analysiert Protokolldaten von Windows 10-Teamgeräten.</span><span class="sxs-lookup"><span data-stu-id="37bf8-115">Azure Operational Insights , part of the Microsoft Operations Manager suite collects, stores, and analyzes log file data from Windows 10 Team devices.</span></span><br /><br /><span data-ttu-id="37bf8-116">Sie müssen eine **Arbeitsbereichs-ID** und einen **Arbeitsbereichsschlüssel** angeben, um die Verbindung mit Azure Operational Insights herstellen zu können.</span><span class="sxs-lookup"><span data-stu-id="37bf8-116">To connect to Azure Operational insights, you must specify a **Workspace ID** and a **Workspace Key**.</span></span>|
|<span data-ttu-id="37bf8-117">**Miracast-Funkprojektion aktivieren**</span><span class="sxs-lookup"><span data-stu-id="37bf8-117">**Enable Miracast wireless projection**</span></span>|<span data-ttu-id="37bf8-118">Aktivieren Sie diese Option, wenn Sie es dem Windows 10-Teamgerät ermöglichen möchten, für Miracast aktivierte Geräte zum Projizieren zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="37bf8-118">Enable this option if you want to let the Windows 10 Team device use Miracast enabled devices to project.</span></span><br /><br /><span data-ttu-id="37bf8-119">Wenn Sie diese Option aktivieren, wählen Sie unter **Miracast-Kanal auswählen** den Miracast-Kanal aus, der zum Projizieren von Inhalten verwendet wurde.</span><span class="sxs-lookup"><span data-stu-id="37bf8-119">If you enable this option, from **Choose Miracast channel** select the Miracast channel used to project content.</span></span>|
|<span data-ttu-id="37bf8-120">**Im Willkommensbildschirm angezeigte Besprechungsinformationen auswählen**</span><span class="sxs-lookup"><span data-stu-id="37bf8-120">**Choose the meeting information displayed on the welcome screen**</span></span>|<span data-ttu-id="37bf8-121">Wenn Sie diese Option aktivieren, können Sie die Informationen auswählen, die auf der Kachel **Besprechungen** des Bildschirms **Willkommen** angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="37bf8-121">If you enable this option, you can choose the information that will be displayed on the **Meetings** tile of the **Welcome** screen.</span></span> <span data-ttu-id="37bf8-122">Sie können:</span><span class="sxs-lookup"><span data-stu-id="37bf8-122">You can:</span></span><br /><br /><span data-ttu-id="37bf8-123">-   **Nur Organisator und Zeit anzeigen**</span><span class="sxs-lookup"><span data-stu-id="37bf8-123">-   **Show organizer and time only**</span></span><br /><span data-ttu-id="37bf8-124">-   **Organisator, Zeit und Thema anzeigen (Thema bei privaten Besprechungen ausblenden)**</span><span class="sxs-lookup"><span data-stu-id="37bf8-124">-   **Show organizer, time and subject (subject hidden for private meetings)**</span></span>|
|<span data-ttu-id="37bf8-125">**URL zum Bild für den Sperrbildschirmhintergrund**</span><span class="sxs-lookup"><span data-stu-id="37bf8-125">**Lockscreen background image URL**</span></span>|<span data-ttu-id="37bf8-126">Aktivieren Sie diese Einstellung, um auf dem **Willkommensbildschirm** von Windows 10 Team-Geräten einen benutzerdefinierten Hintergrund aus der angegebenen URL anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="37bf8-126">Enable this setting to display a custom background on the **Welcome** screen of Windows 10 Team devices from the URL you specify.</span></span><br /><br /><span data-ttu-id="37bf8-127">Das Bild muss im PNG-Format vorliegen und die URL muss mit **https://** beginnen.</span><span class="sxs-lookup"><span data-stu-id="37bf8-127">The image must be in PNG format and the URL must begin with **https://**.</span></span>|


### <a name="see-also"></a><span data-ttu-id="37bf8-128">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="37bf8-128">See also</span></span>
[<span data-ttu-id="37bf8-129">Verwalten von Einstellungen und Features auf Ihren Geräten mit Microsoft Intune-Richtlinien</span><span class="sxs-lookup"><span data-stu-id="37bf8-129">Manage settings and features on your devices with Microsoft Intune policies</span></span>](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)

