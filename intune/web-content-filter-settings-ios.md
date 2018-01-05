---
title: "Intune-Filtereinstellungen für Webinhalte für iOS-Geräte"
titlesuffix: Azure portal
description: "Lernen Sie die Einstellungen kennen, die Sie verwenden können, um den Zugriff von iOS-Geräten auf Websites zuzulassen und zu blockieren.\""
keywords: 
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 7/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 16aa0f3c-8977-4495-9fbe-ca30ad278c9e
ms.reviewer: karanda
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 785260cab5b0f4dc4437d424f04c7bf4086d152c
ms.sourcegitcommit: e37e916e2bf14f092d3a767bc90d68c181d739fb
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/03/2018
---
# <a name="web-content-filter-settings-for-ios-devices"></a><span data-ttu-id="fdd85-103">Filtereinstellungen für Webinhalte für iOS-Geräte</span><span class="sxs-lookup"><span data-stu-id="fdd85-103">Web content filter settings for iOS devices</span></span>

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="fdd85-104">Konfigurieren Sie mit diesen Einstellungen URLs, auf die Endbenutzer in Webbrowsern auf iOS-Geräten zugreifen oder nicht zugreifen dürfen.</span><span class="sxs-lookup"><span data-stu-id="fdd85-104">Use these settings to configure URLs that end users of web browsers, on iOS devices, can, or cannot visit.</span></span> <span data-ttu-id="fdd85-105">Ihnen stehen zwei Verfahren zur Konfigurierung von URLs zur Verfügung:</span><span class="sxs-lookup"><span data-stu-id="fdd85-105">There are two methods you can use to do configure URLs:</span></span>

- <span data-ttu-id="fdd85-106">**Konfigurieren von URLs**: Verwenden Sie den integrierten Webfilter von Apple, der nach nicht jugendfreien Inhalten wie Anzüglichkeiten oder Obszönitäten sucht.</span><span class="sxs-lookup"><span data-stu-id="fdd85-106">**Configure URLs** - Use Apple’s built-in web filter that looks for adult terms like profanity or sexually explicit language.</span></span> <span data-ttu-id="fdd85-107">Diese Funktion bewertet jede Webseite, sobald diese geladen ist, und versucht, ungeeignete Inhalte zu identifizieren und zu blockieren.</span><span class="sxs-lookup"><span data-stu-id="fdd85-107">This function evaluates each web page as it is loaded and attempts to identify and block unsuitable content.</span></span> <span data-ttu-id="fdd85-108">Darüber hinaus können Sie URLs konfigurieren, die vom Filter nicht geprüft werden. Sie können auch URLs konfigurieren, die unabhängig von den Filtereinstellungen blockiert werden.</span><span class="sxs-lookup"><span data-stu-id="fdd85-108">You can also configure URLs that are not checked by the filter, or URLs that are blocked, regardless of the filter settings.</span></span>

- <span data-ttu-id="fdd85-109">**Nur bestimmte Websites** (nur für den Safari-Webbrowser): Diese URLs werden zu den Lesezeichen des Safari-Browsers hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="fdd85-109">**Specific websites only** (for the Safari web browser only) - These URLs are added to the Safari browser’s bookmarks.</span></span> <span data-ttu-id="fdd85-110">Benutzer dürfen **nur** diese Websites besuchen, der Zugriff auf andere Websites ist nicht möglich.</span><span class="sxs-lookup"><span data-stu-id="fdd85-110">The user is **only** allowed to visit these sites; no other sites can be accessed.</span></span> <span data-ttu-id="fdd85-111">Verwenden Sie diese Option nur, wenn Sie genau wissen, auf welche URLs Benutzer zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="fdd85-111">Use this option only if you know the exact list of URLs that users can access.</span></span>
<span data-ttu-id="fdd85-112">Wenn Sie hier keine URLs angeben, können Endbenutzer keine Websites außer „microsoft.com“, „microsoft.net“ und „apple.com“ öffnen.</span><span class="sxs-lookup"><span data-stu-id="fdd85-112">If you do not specify any URLs, then end users cannot access any websites except for microsoft.com, microsoft.net, and apple.com.</span></span>



## <a name="get-started"></a><span data-ttu-id="fdd85-113">Erste Schritte</span><span class="sxs-lookup"><span data-stu-id="fdd85-113">Get started</span></span>

1. <span data-ttu-id="fdd85-114">Wählen Sie auf dem Blatt „Gerätefunktionen“ die Option **Webinhaltsfilter (nur überwacht)**.</span><span class="sxs-lookup"><span data-stu-id="fdd85-114">On the Device features blade, choose **Web Content Filter (supervised only)**.</span></span>
2. <span data-ttu-id="fdd85-115">Wählen Sie auf dem Blatt **Webinhaltsfilter** den **Filtertyp**, den Sie konfigurieren möchten:</span><span class="sxs-lookup"><span data-stu-id="fdd85-115">On the **Web Content Filter** blade, choose the **Filter type** you want to configure from:</span></span>
    - <span data-ttu-id="fdd85-116">**Nicht konfiguriert**: Es wird keine Filterung ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="fdd85-116">**Not Configured** - No filtering is performed.</span></span>
    - <span data-ttu-id="fdd85-117">**Konfigurieren von URLs**</span><span class="sxs-lookup"><span data-stu-id="fdd85-117">**Configure URLs**</span></span>
    - <span data-ttu-id="fdd85-118">**Nur bestimmte Websites**</span><span class="sxs-lookup"><span data-stu-id="fdd85-118">**Specific websites only**</span></span>
3. <span data-ttu-id="fdd85-119">Führen Sie danach je nach verwendetem Filtertyp eines der unten genannten Verfahren aus.</span><span class="sxs-lookup"><span data-stu-id="fdd85-119">Next, depending on the filter type you are using, use one of the following procedures:</span></span>


## <a name="configure-urls"></a><span data-ttu-id="fdd85-120">Konfigurieren von URLs</span><span class="sxs-lookup"><span data-stu-id="fdd85-120">Configure URLs</span></span>

1. <span data-ttu-id="fdd85-121">Wählen Sie auf dem Blatt **Webinhaltsfilter** bei Bedarf eine der folgenden Einstellungen aus:</span><span class="sxs-lookup"><span data-stu-id="fdd85-121">On the **Web Content Filter** blade, choose one of the following settings as required:</span></span>
    - <span data-ttu-id="fdd85-122">**Zulässige URLs**: Geben Sie auf dem Blatt **Zulässige URLs** die URLs ein, die Sie zulassen möchten (der Apple-Webfilter wird dadurch umgangen), und drücken Sie nach jeder URL die EINGABETASTE.</span><span class="sxs-lookup"><span data-stu-id="fdd85-122">**Permitted URLs** - On the **Permitted URLs** blade, enter the URLs you want to allow (bypassing the Apple web filter), and choose enter after each.</span></span>
    - <span data-ttu-id="fdd85-123">**Blockierte URLs**: Geben Sie auf dem Blatt **Blockierte URLs** die URLs ein, die Sie blockieren möchten (unabhängig von den Apple-Webfiltereinstellungen), und drücken Sie nach jeder URL die EINGABETASTE.</span><span class="sxs-lookup"><span data-stu-id="fdd85-123">**Blocked URLs** - On the **Blocked URLs** blade, enter the URLs you want to block (regardless of the Apple web filter settings), and choose enter after each.</span></span>
2. <span data-ttu-id="fdd85-124">Klicken Sie zum Abschluss auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="fdd85-124">When you are finished, click **OK**.</span></span>


## <a name="specific-websites-only"></a><span data-ttu-id="fdd85-125">Nur bestimmte Websites</span><span class="sxs-lookup"><span data-stu-id="fdd85-125">Specific websites only</span></span>

1. <span data-ttu-id="fdd85-126">Konfigurieren Sie auf dem Blatt **Webinhaltsfilter** für jede Website, die Sie zulassen möchten, die folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="fdd85-126">On the **Web Content Filter** blade, for each web site you want to permit, configure the following settings:</span></span>
    - <span data-ttu-id="fdd85-127">**URL**: Geben Sie die URL der Website ein, die Sie zulassen möchten, z.B. **http://www.contoso.com**.</span><span class="sxs-lookup"><span data-stu-id="fdd85-127">**URL** - Enter the URL of the website you want to permit, for example, **http://www.contoso.com**.</span></span>
    - <span data-ttu-id="fdd85-128">**Pfad als Lesezeichen speichern**: Geben Sie den Pfad ein, in dem Sie Lesezeichen speichern möchten, z.B. **/Contoso/Business Apps**.</span><span class="sxs-lookup"><span data-stu-id="fdd85-128">**Bookmark Path** - Enter the path to where you want to store the bookmark, for example **/Contoso/Business Apps**.</span></span> <span data-ttu-id="fdd85-129">Wenn Sie keinen Pfad angeben, wird das Lesezeichen zum Standardordner für Lesezeichen auf dem Gerät hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="fdd85-129">If you don't add a path, the bookmark is added to the default bookmark folder on the device.</span></span>
    - <span data-ttu-id="fdd85-130">**Titel**: Geben Sie einen beschreibenden Titel für das Lesezeichen ein.</span><span class="sxs-lookup"><span data-stu-id="fdd85-130">**Title** - Enter a descriptive title for the bookmark.</span></span>
2. <span data-ttu-id="fdd85-131">Klicken Sie auf **Hinzufügen**, wenn Sie die Informationen für die jeweilige Website eingegeben haben.</span><span class="sxs-lookup"><span data-stu-id="fdd85-131">Click **Add** after you enter the information for each website.</span></span>
3. <span data-ttu-id="fdd85-132">Klicken Sie zum Abschluss auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="fdd85-132">When you are finished, click **OK**.</span></span>

> [!IMPORTANT] 
> <span data-ttu-id="fdd85-133">Die folgenden URLs werden von Intune automatisch zugelassen.</span><span class="sxs-lookup"><span data-stu-id="fdd85-133">The following URLs are permitted automatically by Intune.</span></span>
> - <span data-ttu-id="fdd85-134">www.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="fdd85-134">www.microsoft.com</span></span>
> - <span data-ttu-id="fdd85-135">www.microsoft.net</span><span class="sxs-lookup"><span data-stu-id="fdd85-135">www.microsoft.net</span></span>
> - <span data-ttu-id="fdd85-136">www.apple.com</span><span class="sxs-lookup"><span data-stu-id="fdd85-136">www.apple.com</span></span>

## <a name="finish-up"></a><span data-ttu-id="fdd85-137">Fertig stellen</span><span class="sxs-lookup"><span data-stu-id="fdd85-137">Finish up</span></span>

<span data-ttu-id="fdd85-138">Klicken Sie auf **OK**, um zum Blatt **Profil erstellen** zurückzukehren, und wählen Sie dann **Erstellen** aus.</span><span class="sxs-lookup"><span data-stu-id="fdd85-138">Choose **OK** to return to the **Create Profile** blade, and then choose **Create**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="fdd85-139">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="fdd85-139">Next steps</span></span>

<span data-ttu-id="fdd85-140">Sie können nun das Geräteprofil den von Ihnen ausgewählten Gruppen zuweisen.</span><span class="sxs-lookup"><span data-stu-id="fdd85-140">You can now assign the device profile to the groups you choose.</span></span> <span data-ttu-id="fdd85-141">Weitere Informationen finden Sie unter [Zuweisen von Geräteprofilen](device-profile-assign.md).</span><span class="sxs-lookup"><span data-stu-id="fdd85-141">For details, see [How to assign device profiles](device-profile-assign.md).</span></span>
