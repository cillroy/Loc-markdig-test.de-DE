---
title: "Erfassen von Geräteprotokollen"
description: "Erfahren Sie, wie Sie Protokolle Ihrer verwalteten Geräte sammeln können."
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 02/07/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d97fb610-9d88-40e5-bb06-447eec533630
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: esmich
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: df63b95582a49ccee3653f5233f88e218b6ee3ad
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2018
---
# <a name="device-logs"></a><span data-ttu-id="88f58-103">Geräteprotokolle</span><span class="sxs-lookup"><span data-stu-id="88f58-103">Device logs</span></span>

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="88f58-104">Im Rahmen der Problembehandlung empfiehlt es sich, die Protokolle der Benutzergeräte zu erfassen und zu sammeln.</span><span class="sxs-lookup"><span data-stu-id="88f58-104">As part of your troubleshooting efforts you might want to collect logs from user devices.</span></span> <span data-ttu-id="88f58-105">Im Folgenden finden Sie Anleitungen zum Sammeln dieser Protokolle.</span><span class="sxs-lookup"><span data-stu-id="88f58-105">Instructions for collecting those logs are described here.</span></span> <span data-ttu-id="88f58-106">In der Regel benötigen Sie Zugriff auf das Gerät, um diese Protokolle abzurufen, oder Sie müssen die Benutzer bitten, dass sie die Protokolle sammeln und Ihnen senden.</span><span class="sxs-lookup"><span data-stu-id="88f58-106">Typically you need to access to the device to get these logs or request from the user that they collect the logs and send them to you.</span></span>

### <a name="android-logs"></a><span data-ttu-id="88f58-107">Android-Protokolle</span><span class="sxs-lookup"><span data-stu-id="88f58-107">Android logs</span></span>
<span data-ttu-id="88f58-108">Android-Protokolle befinden sich unter *<Android Device>\Phone\Android\data\com.microsoft.windowsintune.companyportal\files*.</span><span class="sxs-lookup"><span data-stu-id="88f58-108">Android logs are located in *<Android Device>\Phone\Android\data\com.microsoft.windowsintune.companyportal\files*.</span></span>

<span data-ttu-id="88f58-109">Manchmal – insbesondere bei neueren Android-Geräten – werden die Dateien nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="88f58-109">Sometimes the files don't appear, especially on newer Android devices.</span></span> <span data-ttu-id="88f58-110">In diesem Fall bitten Sie die Benutzer, die Unternehmensportal-App für Android zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="88f58-110">If this happens, have your users open the Company Portal app for Android.</span></span> <span data-ttu-id="88f58-111">Anschließend sollen sie **Einstellungen**>**Protokolle kopieren** auswählen und ihr Gerät neu starten.</span><span class="sxs-lookup"><span data-stu-id="88f58-111">Then they should choose **Settings**>**Copy Logs** and reboot their device.</span></span>

<span data-ttu-id="88f58-112">Weitere Informationen dazu, wie Ihre Benutzer Ihnen Datenprotokolle senden können, finden Sie in folgenden Artikeln:</span><span class="sxs-lookup"><span data-stu-id="88f58-112">For more information about how your users can send you data logs, see the following articles:</span></span>

- <span data-ttu-id="88f58-113">[Verwenden der ausführlichen Protokollierung zur Unterstützung Ihres IT-Administrators bei der Behebung von Geräteproblemen](/intune-user-help/use-verbose-logging-to-help-your-it-administrator-fix-device-issues-android): Beschreibt, wie Benutzer die ausführliche Protokollierung aktivieren, die Ihnen automatisch ihre sämtlichen Datenprotokolle sendet.</span><span class="sxs-lookup"><span data-stu-id="88f58-113">[Use Verbose Logging to help your IT admin fix device issues](/intune-user-help/use-verbose-logging-to-help-your-it-administrator-fix-device-issues-android): Describes how users turn on Verbose Logging, which sends you all of their data logs automatically.</span></span> <span data-ttu-id="88f58-114">Die ausführliche Protokollierung ist standardmäßig aktiviert.</span><span class="sxs-lookup"><span data-stu-id="88f58-114">By default, Verbose Logging is turned on.</span></span>

- [<span data-ttu-id="88f58-115">Senden von Diagnosedatenprotokollen an Ihren IT-Administrator per E-Mail</span><span class="sxs-lookup"><span data-stu-id="88f58-115">Send Android diagnostic data logs to your IT admin using email</span></span>](/intune-user-help/send-logs-to-your-it-admin-by-email-android)

- [<span data-ttu-id="88f58-116">Senden von Diagnosedatenprotokollen an Ihren IT-Administrator über ein USB-Kabel</span><span class="sxs-lookup"><span data-stu-id="88f58-116">Send diagnostic data logs to your IT admin using a USB cable</span></span>](/intune-user-help/send-diagnostic-data-logs-to-your-it-administrator-using-a-usb-cable-android)

### <a name="ios-logs"></a><span data-ttu-id="88f58-117">iOS-Protokolle</span><span class="sxs-lookup"><span data-stu-id="88f58-117">iOS logs</span></span>

<span data-ttu-id="88f58-118">Benutzer können Ihnen Fehler beim Registrieren senden. Die entsprechende Vorgehensweise finden Sie unter [Senden von iOS-Registrierungsfehlern an Ihren IT-Administrator](/intune-user-help/send-errors-to-your-it-admin-ios).</span><span class="sxs-lookup"><span data-stu-id="88f58-118">Users can send you enrollment errors, as described in [Send iOS enrollment errors to your IT administrator](/intune-user-help/send-errors-to-your-it-admin-ios).</span></span>

<span data-ttu-id="88f58-119">Benutzer können wie unter [Send iOS Device Logs (Senden von iOS-Geräteprotokollen)](/intune-user-help/send-logs-to-microsoft-ios) beschrieben, Geräteprotokolle senden.</span><span class="sxs-lookup"><span data-stu-id="88f58-119">Users can send device logs, as described in [Send iOS Device Logs](/intune-user-help/send-logs-to-microsoft-ios).</span></span>

### <a name="mac-os-x-logs"></a><span data-ttu-id="88f58-120">Mac OS X-Protokolle</span><span class="sxs-lookup"><span data-stu-id="88f58-120">Mac OS X logs</span></span>

1. <span data-ttu-id="88f58-121">Öffnen Sie die App **Konsole**.</span><span class="sxs-lookup"><span data-stu-id="88f58-121">Open the **Console** app.</span></span>
2. <span data-ttu-id="88f58-122">Wählen Sie unter **DATEIEN** die Datei **system.log** aus.</span><span class="sxs-lookup"><span data-stu-id="88f58-122">Under **FILES**, choose **system.log**.</span></span>
3. <span data-ttu-id="88f58-123">Wählen Sie oben auf der Menüleiste **Datei** > **Kopie speichern unter…** aus.</span><span class="sxs-lookup"><span data-stu-id="88f58-123">On the menu bar on the top, choose **File** > **Save a Copy As…**.</span></span> <span data-ttu-id="88f58-124">Speichern Sie die Datei dann.</span><span class="sxs-lookup"><span data-stu-id="88f58-124">Then save the file.</span></span>

### <a name="windows-phone"></a><span data-ttu-id="88f58-125">Windows Phone</span><span class="sxs-lookup"><span data-stu-id="88f58-125">Windows Phone</span></span>

<span data-ttu-id="88f58-126">In der Windows Phone-Unternehmensportal-App klicken Benutzer auf die drei Punkte (**...**), um das Menü zu öffnen, und wählen dann **Protokolle senden** aus.</span><span class="sxs-lookup"><span data-stu-id="88f58-126">In the Windows Phone Company Portal app, users choose the three dots (**…**) to access the menu, and then choose **Send Logs**.</span></span> <span data-ttu-id="88f58-127">Diese Option steht vor und nach der Anmeldung bei der Unternehmensportal-App zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="88f58-127">This option is available both before and after signing in to the Company Portal app.</span></span>

### <a name="windows"></a><span data-ttu-id="88f58-128">Windows</span><span class="sxs-lookup"><span data-stu-id="88f58-128">Windows</span></span>

<span data-ttu-id="88f58-129">Für das Windows-Unternehmensportal befinden sich die Protokolle unter *%localappdata%\Packages\Microsoft.CompanyPortal_8wekyb3d8bbwe\LocalState*.</span><span class="sxs-lookup"><span data-stu-id="88f58-129">For the Windows Company Portal, the logs are located in *%localappdata%\Packages\Microsoft.CompanyPortal_8wekyb3d8bbwe\LocalState*.</span></span>
