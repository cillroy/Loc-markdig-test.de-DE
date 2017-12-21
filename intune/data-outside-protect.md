---
title: Verhindern von nicht autorisiertem Zugriff auf Unternehmensdaten
description: "Verhindern Sie nicht autorisierten Zugriff auf Ihre Unternehmensdaten, wenn diese außerhalb des Unternehmensnetzwerks freigegeben werden."
keywords: "Office 365, O365, Azure Information Protection, Daten, schützen, außerhalb des Netzwerks, Unternehmensdaten"
author: arob98
manager: angrobe
ms.date: 09/22/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6a88573a-aa60-455c-858c-74562798246b
ms.reviewer: pchacon
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: bb748bc0a44b796dfb4ad07e404166d1d5c2ef19
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2017
---
# <a name="prevent-unauthorized-access-to-company-data"></a><span data-ttu-id="1a18f-104">Verhindern von nicht autorisiertem Zugriff auf Unternehmensdaten</span><span class="sxs-lookup"><span data-stu-id="1a18f-104">Prevent unauthorized access to company data</span></span> 

<span data-ttu-id="1a18f-105">Sie können Office 365-Dokumente und -E-Mails klassifizieren, bezeichnen und schützen, sodass nur autorisierte Benutzer Zugriff auf die Daten haben.</span><span class="sxs-lookup"><span data-stu-id="1a18f-105">You can classify, label, and protect Office 365 documents and emails so only authorized users have access to the data.</span></span> <span data-ttu-id="1a18f-106">Die Einstellungen werden automatisch verwaltet, nachdem IT-Administratoren oder Benutzer die Regeln und Bedingungen festgelegt haben.</span><span class="sxs-lookup"><span data-stu-id="1a18f-106">The settings are managed automatically after IT administrators or users set the rules and conditions.</span></span> <span data-ttu-id="1a18f-107">Alternativ kann das IT-Team empfohlene Einstellungen bereitstellen, nach denen sich Benutzer richten sollen.</span><span class="sxs-lookup"><span data-stu-id="1a18f-107">Alternatively, the IT team can provide recommended settings for users to follow.</span></span> <span data-ttu-id="1a18f-108">Administratoren und Benutzer können auch ohne die Unterstützung einer anderen Autorität den Zugriff auf Daten widerrufen, die bereits für Andere freigegeben wurden.</span><span class="sxs-lookup"><span data-stu-id="1a18f-108">Administrators and users can also revoke access to data already shared with others without assistance from another authority.</span></span> <span data-ttu-id="1a18f-109">Somit kann gesteuert werden, wer geschützte Daten öffnet und aktualisiert, selbst wenn die Daten das Unternehmensnetzwerk verlassen.</span><span class="sxs-lookup"><span data-stu-id="1a18f-109">The result of this work is to control who opens or updates protected data, even when the data leaves the company's network.</span></span> 

## <a name="before-you-begin"></a><span data-ttu-id="1a18f-110">Vorbereitung</span><span class="sxs-lookup"><span data-stu-id="1a18f-110">Before you begin</span></span>

<span data-ttu-id="1a18f-111">Der folgende Maßnahmenplan kann verwendet werden, wenn Sie die folgenden Anforderungen erfüllen:</span><span class="sxs-lookup"><span data-stu-id="1a18f-111">The following action plan can be used when you meet the following requirements:</span></span>
* <span data-ttu-id="1a18f-112">Ihr Unternehmen ist für den sicheren Übergang in die Cloud bereit.</span><span class="sxs-lookup"><span data-stu-id="1a18f-112">Your company is ready to transition securely to the cloud.</span></span>
* <span data-ttu-id="1a18f-113">Ihr Unternehmen verwendet die Office 365 Exchange Online, SharePoint Online, OneDrive for Business oder Yammer.</span><span class="sxs-lookup"><span data-stu-id="1a18f-113">Your company uses Office 365 Exchange Online, SharePoint Online, OneDrive for Business, or Yammer.</span></span>
* <span data-ttu-id="1a18f-114">Ihr Unternehmen verfügt über Lizenzen für Microsoft-365, Enterprise Mobility + Security (EMS) oder Azure Information Protection.</span><span class="sxs-lookup"><span data-stu-id="1a18f-114">Your company has licenses for Microsoft 365, Enterprise Mobility + Security (EMS), or Azure Information Protection.</span></span>
* <span data-ttu-id="1a18f-115">Ihr Unternehmen arbeitet mit Geräten, auf denen Windows 7 Service Pack 1 oder höher ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="1a18f-115">Your company works with devices running Windows 7 Service Pack 1 or later.</span></span>
* <span data-ttu-id="1a18f-116">Ihr Unternehmen verwendet Office 365 ProPlus mit 2016-Apps oder 2013-Apps, Office Professional Plus 2016, Office Professional Plus 2013 mit Service Pack 1 oder Office Professional Plus 2010.</span><span class="sxs-lookup"><span data-stu-id="1a18f-116">Your company uses Office 365 ProPlus with 2016 apps or 2013 apps, Office Professional Plus 2016, Office Professional Plus 2013 with Service Pack 1, or Office Professional Plus 2010.</span></span>

## <a name="action-plan"></a><span data-ttu-id="1a18f-117">Maßnahmenplan</span><span class="sxs-lookup"><span data-stu-id="1a18f-117">Action plan</span></span>

<span data-ttu-id="1a18f-118">Schließen Sie das [Schnellstarttutorial für Azure Information Protection](https://docs.microsoft.com/information-protection/get-started/infoprotect-quick-start-tutorial) ab.</span><span class="sxs-lookup"><span data-stu-id="1a18f-118">Complete the [quick start tutorial for Azure Information Protection](https://docs.microsoft.com/information-protection/get-started/infoprotect-quick-start-tutorial).</span></span>  

## <a name="what-to-tell-employees-and-students"></a><span data-ttu-id="1a18f-119">Informationen für Mitarbeiter und Studenten</span><span class="sxs-lookup"><span data-stu-id="1a18f-119">What to tell employees and students</span></span>

<span data-ttu-id="1a18f-120">Sie können Informationen dazu teilen, [wie und wann Dokumente und E-Mails geschützt werden sollen, die sensible Informationen enthalten](https://docs.microsoft.com/information-protection/deploy-use/help-users).</span><span class="sxs-lookup"><span data-stu-id="1a18f-120">You can share details of [how and when to protect documents and emails that contain sensitive information](https://docs.microsoft.com/information-protection/deploy-use/help-users).</span></span>

## <a name="next-steps"></a><span data-ttu-id="1a18f-121">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="1a18f-121">Next steps</span></span>

<span data-ttu-id="1a18f-122">Im Zuge der nächsten Schritte können Sie mehr über die anderen Möglichkeiten erfahren, den Schutz Ihrer Unternehmensdaten zu erhöhen. Dazu zählt Folgendes:</span><span class="sxs-lookup"><span data-stu-id="1a18f-122">As part of next steps, you can learn more about the other ways you can increase the protection of your company's data, including:</span></span> 

* <span data-ttu-id="1a18f-123">Erfahren Sie, wie Sie [Azure Information Protection auf iOS- und Android-Geräten verwenden](https://docs.microsoft.com/information-protection/rms-client/mobile-app-faq.</span><span class="sxs-lookup"><span data-stu-id="1a18f-123">Learn how to use [Azure Information Protection on iOS and Android devices](https://docs.microsoft.com/information-protection/rms-client/mobile-app-faq.</span></span>
* <span data-ttu-id="1a18f-124">Erhalten Sie für Windows Phone und Mac-Computer Informationen zur [Microsoft Rights Management-Freigabeanwendung](https://technet.microsoft.com/dn451248).</span><span class="sxs-lookup"><span data-stu-id="1a18f-124">For Windows Phone and Mac computers, learn about [Microsoft Rights Management Sharing Application](https://technet.microsoft.com/dn451248).</span></span>
