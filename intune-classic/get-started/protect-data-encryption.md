---
title: "Schützen von Unternehmensdaten durch Datenverschlüsselung"
description: "Dieser Leitfaden hilft Ihnen dabei, Ihr Unternehmen vor Datenverlust zu schützen, indem durch die Verwendung einer Richtlinie in mobilen Apps eine Kennung sowie die Datenverschlüsselung erzwungen wird."
keywords: "Verschlüsselung, PIN, Daten"
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 11/22/2016
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: b1e84ef8-a260-4e3d-aaf1-8b3facfecafa
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: pchacon
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 2f7bfca5f17d663461f778ce270989b8971ca1bc
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2017
---
# <a name="quick-start-guide-protect-company-data-with-data-encryption"></a><span data-ttu-id="ff39f-104">Erste Schritte: Schützen von Unternehmensdaten durch Datenverschlüsselung</span><span class="sxs-lookup"><span data-stu-id="ff39f-104">Quick Start Guide: Protect company data with data encryption</span></span>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="ff39f-105">Microsoft Intune kann Ihnen dabei helfen, den Verlust von Daten aus mobilen Office-Apps auf unterschiedlichste Weise zu verhindern, z.B.:</span><span class="sxs-lookup"><span data-stu-id="ff39f-105">Microsoft Intune can help you prevent data loss from Office mobile apps in a variety of ways, including:</span></span>
- <span data-ttu-id="ff39f-106">Durch Verschlüsseln von Unternehmensdaten mit der höchsten Geräteverschlüsselungsstufe, die von iOS und Android bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="ff39f-106">By encrypting corporate data with the highest level of device encryption provided by iOS and Android.</span></span>
- <span data-ttu-id="ff39f-107">Auf iOS- und Android-Geräten, die aufgrund von Datenschutzanforderungen oder rechtlichen Anforderungen nicht bei einer Lösung für die Verwaltung mobiler Geräte registriert werden können.</span><span class="sxs-lookup"><span data-stu-id="ff39f-107">On iOS and Android devices that, because of privacy or legal requirements, cannot be enrolled in a mobile device management solution.</span></span>

<span data-ttu-id="ff39f-108">Microsoft Intune kann Ihnen auch dabei helfen, den Verlust von Daten aus mobilen Office-Apps zu verhindern, sowie Office 365-Daten (O365) zu sichern, ohne mobile iOS- oder Android-Geräte bei einer vollständigen Verwaltung mobiler Geräte registrieren zu müssen.</span><span class="sxs-lookup"><span data-stu-id="ff39f-108">Microsoft Intune can also help you prevent data loss from Office mobile apps and secure Office 365 (O365) data without having to enroll iOS or Android mobile devices in full mobile device management.</span></span> <span data-ttu-id="ff39f-109">Dies gilt auch, wenn Sie für die verwalteten mobilen Geräte eine Drittanbieterlösung für die Verwaltung mobiler Geräte verwenden.</span><span class="sxs-lookup"><span data-stu-id="ff39f-109">This is true even if you use a third-party mobile device management solution to managed mobile devices.</span></span>

## <a name="is-this-quick-start-guide-right-for-me"></a><span data-ttu-id="ff39f-110">Ist dieses Schnellstarthandbuch für mich geeignet?</span><span class="sxs-lookup"><span data-stu-id="ff39f-110">Is this quick start guide right for me?</span></span>
<span data-ttu-id="ff39f-111">Dieses Schnellstarthandbuch stellt eine gute Ressource für Sie dar, wenn Sie die folgenden Voraussetzungen erfüllen:</span><span class="sxs-lookup"><span data-stu-id="ff39f-111">This quick start guide is a good resource if you meet the following prerequisites:</span></span>
- <span data-ttu-id="ff39f-112">Sie verwenden bzw. verfügen bereits über O365-Lizenzen, die Sie verwenden möchten, und Sie verwalten mobile Office-Apps.</span><span class="sxs-lookup"><span data-stu-id="ff39f-112">You already use or have O365 licenses that you want to use and you manage Office mobile apps.</span></span>
- <span data-ttu-id="ff39f-113">Sie planen, mobile Office-Apps unter iOS oder Android zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="ff39f-113">You are planning to use Office mobile apps on iOS or Android.</span></span>
- <span data-ttu-id="ff39f-114">Sie verwenden eine beliebige Lösung für die Verwaltung mobiler Geräte (von Microsoft oder einem Drittanbieter).</span><span class="sxs-lookup"><span data-stu-id="ff39f-114">You use any mobile device management solution - Microsoft or non-Microsoft.</span></span> <span data-ttu-id="ff39f-115">Wenn Sie aufgrund gesetzlicher Vorschriften keine Lösung für die Verwaltung mobiler Geräte verwenden können, können Sie diesen Leitfaden verwenden.</span><span class="sxs-lookup"><span data-stu-id="ff39f-115">If you cannot use a mobile device management solution because of statutory rules, this guide is something that you can use.</span></span>

> [!NOTE]
> <span data-ttu-id="ff39f-116">Windows stellt für mobile Office-Apps noch keine unterstützte Plattform dar.</span><span class="sxs-lookup"><span data-stu-id="ff39f-116">Windows is not yet a supported platform for Office mobile apps.</span></span> <span data-ttu-id="ff39f-117">Die Verwaltung mobiler Anwendungen ohne Registrierung ist bisher nicht kompatibel mit Exchange oder lokalem SharePoint.</span><span class="sxs-lookup"><span data-stu-id="ff39f-117">Mobile application management without enrollment is not yet compatible with Exchange or SharePoint on-premise.</span></span> <span data-ttu-id="ff39f-118">Sie können nur Daten schützen, die in Online-Versionen gehostet werden.</span><span class="sxs-lookup"><span data-stu-id="ff39f-118">You can only protect data hosted in online versions.</span></span>

<span data-ttu-id="ff39f-119">Dieser Leitfaden hilft Ihnen dabei, Ihr Unternehmen vor Datenverlust zu schützen, indem eine Kennung sowie die Datenverschlüsselung erzwungen wird. Dies erfolgt durch die Verwendung von Richtlinien in mobilen Apps, die Ihre Mitarbeiter für den Zugriff auf sensible Daten verwenden, ohne dass eine vollständige Registrierung bei einer Geräteverwaltungslösung erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="ff39f-119">This guide can help you protect your company from data loss by forcing passcodes and data encryption using policies on the mobile apps that your employees use to access sensitive data, without requiring full enrollment in any device management solution.</span></span> <span data-ttu-id="ff39f-120">Microsoft Intune ermöglicht Ihnen das Festlegen von MAM-Richtlinien (mobile application management, Verwaltung mobiler Anwendungen) in mobilen Office-Apps für [iOS](https://products.office.com/mobile/office-mobile-apps-for-ios) und [Android](https://products.office.com/mobile/office-mobile-apps-for-android).</span><span class="sxs-lookup"><span data-stu-id="ff39f-120">Microsoft Intune allows you to set mobile application management (MAM) policies on Office mobile apps for [iOS](https://products.office.com/mobile/office-mobile-apps-for-ios) and [Android](https://products.office.com/mobile/office-mobile-apps-for-android).</span></span> <span data-ttu-id="ff39f-121">Dadurch werden O365-Daten geschützt, ohne dass Benutzer ihre Geräte in einer MDM-Lösung (mobile device management, Verwaltung mobiler Geräte) registrieren müssen, wobei zudem gleichzeitig eine hervorragende Endbenutzerfreundlichkeit der mobilen Office-Apps bewahrt wird.</span><span class="sxs-lookup"><span data-stu-id="ff39f-121">This approach protects O365 data without requiring users to enroll their devices into a mobile device management solution while also maintaining a great end-user experience with Office mobile apps.</span></span>

## <a name="how-do-i-do-it"></a><span data-ttu-id="ff39f-122">Wie gehe ich dabei vor?</span><span class="sxs-lookup"><span data-stu-id="ff39f-122">How do I do it?</span></span>
1.  [<span data-ttu-id="ff39f-123">Lesen Sie, wie Sie App-Daten schützen können</span><span class="sxs-lookup"><span data-stu-id="ff39f-123">Review how you can protect app data</span></span>](/intune-classic/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune)
2.  [<span data-ttu-id="ff39f-124">Vorbereiten der Konfiguration von Verwaltungsrichtlinien für mobile Apps</span><span class="sxs-lookup"><span data-stu-id="ff39f-124">Get ready to configure mobile app management policies</span></span>](/intune-classic/deploy-use/get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune)
3.  [<span data-ttu-id="ff39f-125">Erstellen und Bereitstellen von Verwaltungsrichtlinien für mobile Apps</span><span class="sxs-lookup"><span data-stu-id="ff39f-125">Create and deploy mobile app management policies</span></span>](/intune-classic/deploy-use/create-and-deploy-mobile-app-management-policies-with-microsoft-intune)

## <a name="additional-information"></a><span data-ttu-id="ff39f-126">Zusätzliche Informationen:</span><span class="sxs-lookup"><span data-stu-id="ff39f-126">Additional information:</span></span>
- [<span data-ttu-id="ff39f-127">Erfahren Sie mehr über die Endbenutzererfahrung für MAM-fähige Apps mit Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="ff39f-127">Find out about the end user experience for MAM enabled apps with Microsoft Intune.</span></span>](/intune-classic/eploy-use/end-user-experience-for-mam-enabled-apps-with-microsoft-intune)
- [<span data-ttu-id="ff39f-128">Entscheiden Sie, wie Sie Apps für die mobile Anwendungsverwaltung mit Microsoft Intune vorbereiten.</span><span class="sxs-lookup"><span data-stu-id="ff39f-128">Decide how to prepare apps for mobile application management with Microsoft Intune.</span></span>](/intune/apps-prepare-mobile-application-management)
- [<span data-ttu-id="ff39f-129">Zeigen Sie die Liste der Microsoft Intune-Anwendungspartner an.</span><span class="sxs-lookup"><span data-stu-id="ff39f-129">View the list of Microsoft Intune application partners</span></span>](https://www.microsoft.com/cloud-platform/microsoft-intune-partners)
