---
title: Aktivieren von Windows Defender | Microsoft-Dokumentation
description: Erfahren Sie, wie Windows Defender aktiviert wird, um auf Unternehmensressourcen zuzugreifen.
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 11/08/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d16dd2de-3ed5-474f-a04b-36dcd350162c
searchScope: User help
ROBOTS: 
ms.reviewer: shburbid
ms.suite: ems
ms.custom: intune-enduser
ms.openlocfilehash: 06471a8d929dc2708917d4860510ba5cbab10fb1
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2017
---
# <a name="turn-on-windows-defender-to-access-company-resources"></a><span data-ttu-id="20623-103">Aktivieren von Windows Defender zum Zugriff auf Unternehmensressourcen</span><span class="sxs-lookup"><span data-stu-id="20623-103">Turn on Windows Defender to access company resources</span></span>

<span data-ttu-id="20623-104">Ihr Arbeitgeber oder Ihre Schule möchte sicherstellen, dass Geräte, die auf ihre Ressourcen zugreifen, gesichert sind.</span><span class="sxs-lookup"><span data-stu-id="20623-104">Your work or school wants to ensure that devices accessing their resources are secured.</span></span> <span data-ttu-id="20623-105">Dabei können sie in verschiedener Weise von [Windows Defender](https://www.microsoft.com/safety/pc-security/windows-defender.aspx), dem in Windows integrierten Schutz vor Schadsoftware, Gebrauch machen.</span><span class="sxs-lookup"><span data-stu-id="20623-105">There are a few ways that they can use [Windows Defender](https://www.microsoft.com/safety/pc-security/windows-defender.aspx), Windows' built-in protection for malicious software.</span></span>

<span data-ttu-id="20623-106">Es gibt einige Einstellungen in Ihrem Windows Defender, die Sie möglicherweise ändern müssen, um Zugriffsprobleme zu beheben.</span><span class="sxs-lookup"><span data-stu-id="20623-106">There are a few settings you may need to change on your Windows Defender to fix any access issues.</span></span> <span data-ttu-id="20623-107">Für diese Schritte kann es erforderlich sein, dass Sie verschiedene Orte auf Ihrem Computer aufsuchen.</span><span class="sxs-lookup"><span data-stu-id="20623-107">These steps may require you to go to a couple of different places on your computer.</span></span>

## <a name="turn-on-windows-defender"></a><span data-ttu-id="20623-108">Aktivieren von Windows Defender</span><span class="sxs-lookup"><span data-stu-id="20623-108">Turn on Windows Defender</span></span>

1. <span data-ttu-id="20623-109">Öffnen Sie im Menü **Start** die **Systemsteuerung**.</span><span class="sxs-lookup"><span data-stu-id="20623-109">In **Start**, open **Control Panel**.</span></span>
2. <span data-ttu-id="20623-110">Öffnen Sie **Verwaltung** > **Gruppenrichtlinie bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="20623-110">Open **Administrative Tools** > **Edit group policy**.</span></span> <span data-ttu-id="20623-111">Dadurch wird der **Editor für lokale Gruppenrichtlinien** in einem neuen Fenster geöffnet.</span><span class="sxs-lookup"><span data-stu-id="20623-111">This will open the **Local Group Policy Editor** in a new window.</span></span>
3. <span data-ttu-id="20623-112">Öffnen Sie **Computerkonfiguration** > **Administrative Vorlagen** > **Windows-Komponenten** > **Windows Defender Antivirus**.</span><span class="sxs-lookup"><span data-stu-id="20623-112">Open **Computer Configuration** > **Administrative Templates** > **Windows Components** > **Windows Defender Antivirus**.</span></span> <span data-ttu-id="20623-113">Die Einstellung **Windows Defender Antivirus deaktivieren** befindet sich unterhalb der Ordner für andere Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="20623-113">The setting **Turn off Windows Defender Antivirus** is underneath the folders of other settings.</span></span> 
4. <span data-ttu-id="20623-114">Öffnen Sie **Windows Defender Antivirus deaktivieren**, und vergewissern Sie sich, dass die Einstellung auf **Deaktiviert** oder **Nicht konfiguriert** festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="20623-114">Open **Turn off Windows Defender Antivirus** and make sure it's set to **Disabled** or **Not configured**.</span></span>

## <a name="turn-on-real-time-protection"></a><span data-ttu-id="20623-115">Aktivieren von Echtzeitschutz</span><span class="sxs-lookup"><span data-stu-id="20623-115">Turn on Real-time Protection</span></span>

<span data-ttu-id="20623-116">Vergewissern Sie sich, dass der Echtzeitschutz aktiviert ist, indem Sie zu **Start** gehen und nach **Windows Defender Security Center** suchen.</span><span class="sxs-lookup"><span data-stu-id="20623-116">Check to make sure that Real-time Protection is turned on by going to **Start** and searching for **Windows Defender Security Center**.</span></span> <span data-ttu-id="20623-117">Wählen Sie **Einstellungen für Viren- & Bedrohungsschutz** aus, und überprüfen Sie, ob sowohl **Echtzeitschutz** als auch **Cloudbasierter Schutz** auf **Ein** festgelegt sind.</span><span class="sxs-lookup"><span data-stu-id="20623-117">Select **Virus and threat protection settings** and confirm that both **Real-time protection** and **Cloud-delivered protection** are switched to **On**.</span></span> <span data-ttu-id="20623-118">Wenn diese Optionen nicht angezeigt werden, gehen Sie wie folgt vor, um sie zu aktivieren:</span><span class="sxs-lookup"><span data-stu-id="20623-118">If these options aren't appearing, do the following to enable them:</span></span>

1. <span data-ttu-id="20623-119">Öffnen Sie im Menü **Start** die **Systemsteuerung**.</span><span class="sxs-lookup"><span data-stu-id="20623-119">In **Start**, open **Control Panel**.</span></span>
2. <span data-ttu-id="20623-120">Öffnen Sie **Verwaltung** > **Gruppenrichtlinie bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="20623-120">Open **Administrative Tools** > **Edit group policy**.</span></span> <span data-ttu-id="20623-121">Dadurch wird der **Editor für lokale Gruppenrichtlinien** in einem neuen Fenster geöffnet.</span><span class="sxs-lookup"><span data-stu-id="20623-121">This will open the **Local Group Policy Editor** in a new window.</span></span>
3. <span data-ttu-id="20623-122">Öffnen Sie **Computerkonfiguration** > **Administrative Vorlagen** > **Windows-Komponenten** > **Windows Defender Security Center** > **Viren- & Bedrohungsschutz**.</span><span class="sxs-lookup"><span data-stu-id="20623-122">Open **Computer Configuration** > **Administrative Templates** > **Windows Components** > **Windows Defender Security Center** > **Virus and threat protection**.</span></span>
4. <span data-ttu-id="20623-123">Öffnen Sie die Einstellung **Viren- und Bedrohungsschutzbereich**, und legen Sie sie auf **Deaktiviert** fest.</span><span class="sxs-lookup"><span data-stu-id="20623-123">Open the setting **Virus and threat protection area** and set it to **Disabled**.</span></span>

## <a name="update-your-antivirus-definitions"></a><span data-ttu-id="20623-124">Aktualisieren Sie Ihre Virusdefinitionen</span><span class="sxs-lookup"><span data-stu-id="20623-124">Update your antivirus definitions</span></span>

<span data-ttu-id="20623-125">Vergewissern Sie sich, dass Ihre Virendefinitionen auf dem aktuellen Stand sind, indem Sie zu **Start** gehen und nach **Windows Defender Security Center** suchen.</span><span class="sxs-lookup"><span data-stu-id="20623-125">Check to make sure that your antivirus definitions are up to date by going to **Start** and searching for **Windows Defender Security Center**.</span></span> <span data-ttu-id="20623-126">Wählen Sie **Schutzupdates** und **Nach Updates suchen** aus, um sicherzustellen, dass Ihr Gerät über aktuellen Schutz gegen Viren verfügt.</span><span class="sxs-lookup"><span data-stu-id="20623-126">Select **Protection updates** and **Check for updates** to make sure that your device has current protection against viruses.</span></span> <span data-ttu-id="20623-127">Wenn diese Option nicht angezeigt wird, führen Sie die unter [Aktivieren von Echtzeitschutz](turn-on-defender-windows.md#turn-on-real-time-protection) beschriebenen Schritte aus.</span><span class="sxs-lookup"><span data-stu-id="20623-127">If this option doesn't appear, follow the steps in [Turn on Real-time Protection](turn-on-defender-windows.md#turn-on-real-time-protection)</span></span>

<span data-ttu-id="20623-128">Benötigen Sie weitere Unterstützung?</span><span class="sxs-lookup"><span data-stu-id="20623-128">Still need help?</span></span> <span data-ttu-id="20623-129">Kontaktieren Sie den Support Ihres Unternehmens.</span><span class="sxs-lookup"><span data-stu-id="20623-129">Contact your company support.</span></span> <span data-ttu-id="20623-130">Die entsprechenden Kontaktinformationen finden Sie auf der [Unternehmensportal-Website](https://portal.manage.microsoft.com#HelpDeskDialog).</span><span class="sxs-lookup"><span data-stu-id="20623-130">For their contact information, check the [Company Portal website](https://portal.manage.microsoft.com#HelpDeskDialog).</span></span>
