---
title: "Verhindern von Datenverlusten auf nicht verwalteten Geräten"
description: "Ermöglichen Sie den Zugriff auf Unternehmensdaten auf Geräten, und schützen Sie Daten vor Datenverlusten."
keywords: "Datenschutz, Verluste verhindern, Gerät, O365, Office 365"
author: arob98
manager: angrobe
ms.date: 09/22/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: b1512c3a-3bbd-4111-a0df-c874a0a335df
ms.reviewer: pchacon
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: ddaa5bc2f2f8ed8b75296fdea826649a9cef125a
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2017
---
# <a name="prevent-data-leaks-on-non-managed-devices"></a><span data-ttu-id="7962e-104">Verhindern von Datenverlusten auf nicht verwalteten Geräten</span><span class="sxs-lookup"><span data-stu-id="7962e-104">Prevent data leaks on non-managed devices</span></span>

<span data-ttu-id="7962e-105">Wenn Sie Zugriff auf Unternehmensdaten gewähren, die von Office 365 gehostet werden, können Sie steuern, wie Benutzer Daten freigeben und speichern, ohne beabsichtigte oder versehentliche Datenverluste zu riskieren.</span><span class="sxs-lookup"><span data-stu-id="7962e-105">If you allow access to company data hosted by Office 365, you can control how users share and save data without risking intentional or accidental data leaks.</span></span> <span data-ttu-id="7962e-106">Microsoft Intune stellt App-Schutzrichtlinien bereit, die Sie festlegen, um Ihre Unternehmensdaten auf benutzereigenen Geräten zu sichern.</span><span class="sxs-lookup"><span data-stu-id="7962e-106">Microsoft Intune provides app protection policies that you set to secure you company data on user-owned devices.</span></span> <span data-ttu-id="7962e-107">Die Geräte müssen nicht beim Intune-Dienst registriert werden.</span><span class="sxs-lookup"><span data-stu-id="7962e-107">The devices do not need to be enrolled in the Intune service.</span></span> 

<span data-ttu-id="7962e-108">Mit Intune eingerichtete App-Schutzrichtlinien funktionieren auch auf Geräten, die mit einer Geräteverwaltungslösung verwaltet werden, die nicht von Microsoft stammt.</span><span class="sxs-lookup"><span data-stu-id="7962e-108">App protection policies set up with Intune also work on devices managed with a non-Microsoft device management solution.</span></span> <span data-ttu-id="7962e-109">Die personenbezogenen Daten auf den Geräten werden nicht angerührt. Nur die Unternehmensdaten werden von der IT-Abteilung verwaltet.</span><span class="sxs-lookup"><span data-stu-id="7962e-109">The personal data on the devices is not touched; only company data is managed by the IT department.</span></span> 

<span data-ttu-id="7962e-110">Sie können App-Schutzrichtlinien für mobile Office-Apps auf Geräten festlegen, auf denen Windows, iOS oder Android ausgeführt wird, um Unternehmensdaten zu schützen.</span><span class="sxs-lookup"><span data-stu-id="7962e-110">You can set app protection policies for Office mobile apps on devices running Windows, iOS, or Android to protect company data.</span></span> <span data-ttu-id="7962e-111">Mit diesen Richtlinien können Sie Richtlinien wie eine App-basierte PIN oder eine Verschlüsselung von Unternehmensdaten sowie erweiterte Einstellungen festlegen, um einzuschränken, wie die Funktionen „Ausschneiden“, „Kopieren“, „Einfügen“ und „Speichern unter“ von Benutzern zwischen verwalteten und nicht verwalteten Apps verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="7962e-111">These policies let you set policies such as app-based PIN or company data encryption, or more advanced settings to restrict how you cut, copy, paste, and save-as features are used by users between managed and unmanaged apps.</span></span> <span data-ttu-id="7962e-112">Sie können Unternehmensdaten auch remote zurücksetzen, ohne dass Benutzer Geräte registrieren müssen.</span><span class="sxs-lookup"><span data-stu-id="7962e-112">You can also remotely wipe company data without requiring users enroll devices.</span></span> 

<span data-ttu-id="7962e-113">Die App-Schutzrichtlinien von Intune sind unabhängig von der Geräteverwaltung.</span><span class="sxs-lookup"><span data-stu-id="7962e-113">Intune app protection policies are independent of device management.</span></span> <span data-ttu-id="7962e-114">Mit App-Schutzrichtlinien können Sie mobile Office-Apps sowohl auf nicht verwalteten als auch auf von Intune verwalteten Geräten und auf Geräten verwalten, die von MDM-Lösungen verwaltet werden, die nicht von Microsoft stammen.</span><span class="sxs-lookup"><span data-stu-id="7962e-114">App protection policies let you manage Office mobile apps on both unmanaged and Intune-managed devices, as well as device managed by non-Microsoft MDM solutions.</span></span> 

## <a name="before-you-begin"></a><span data-ttu-id="7962e-115">Vorbereitung</span><span class="sxs-lookup"><span data-stu-id="7962e-115">Before you begin</span></span>

<span data-ttu-id="7962e-116">Der folgende Maßnahmenplan kann verwendet werden, wenn Sie die folgenden Anforderungen erfüllen:</span><span class="sxs-lookup"><span data-stu-id="7962e-116">The following action plan can be used when you meet the following requirements:</span></span>
* <span data-ttu-id="7962e-117">Ihr Unternehmen ist für den sicheren Übergang in die Cloud bereit.</span><span class="sxs-lookup"><span data-stu-id="7962e-117">Your company is ready to transition securely to the cloud.</span></span>
* <span data-ttu-id="7962e-118">Ihr Unternehmen verwendet die Office 365 Exchange Online, SharePoint Online, OneDrive for Business oder Yammer.</span><span class="sxs-lookup"><span data-stu-id="7962e-118">Your company uses Office 365 Exchange Online, SharePoint Online, OneDrive for Business, or Yammer.</span></span>
* <span data-ttu-id="7962e-119">Ihr Unternehmen verfügt über Lizenzen für Microsoft-365, Enterprise Mobility + Security (EMS) oder Azure Information Protection.</span><span class="sxs-lookup"><span data-stu-id="7962e-119">Your company has licenses for Microsoft 365, Enterprise Mobility + Security (EMS), or Azure Information Protection.</span></span>
* <span data-ttu-id="7962e-120">Ihr Unternehmen ermöglicht Benutzern den Zugriff auf Unternehmensdaten über unternehmens- oder benutzereigene Windows-, iOS- oder Android-Geräte.</span><span class="sxs-lookup"><span data-stu-id="7962e-120">Your company allows users to access company data from company-owned or personally-owned Windows, iOS, or Android devices.</span></span> 
* <span data-ttu-id="7962e-121">Ihr Unternehmen möchte nicht, dass die Registrierung von benutzereigenen Geräten in einem Geräteverwaltungsdienst erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="7962e-121">Your company does not want to require enrollment of personally-owned devices in a device management service.</span></span> 

## <a name="action-plan"></a><span data-ttu-id="7962e-122">Maßnahmenplan</span><span class="sxs-lookup"><span data-stu-id="7962e-122">Action plan</span></span>

<span data-ttu-id="7962e-123">Für iOS- und Android-Geräte:</span><span class="sxs-lookup"><span data-stu-id="7962e-123">For iOS and Android devices:</span></span> 

1. <span data-ttu-id="7962e-124">Erfahren Sie, wie [App-Schutzrichtlinien](app-protection-policy.md) funktionieren.</span><span class="sxs-lookup"><span data-stu-id="7962e-124">Learn how [app protection policies](app-protection-policy.md) work.</span></span>
2. <span data-ttu-id="7962e-125">Erfahren Sie, wie Sie [App-Schutzrichtlinien für mobile Office-Apps erstellen und bereitstellen](app-protection-policies.md).</span><span class="sxs-lookup"><span data-stu-id="7962e-125">Learn how to [create and deploy app protection policies](app-protection-policies.md) for Office mobile apps.</span></span> 
3. <span data-ttu-id="7962e-126">[Überwachen Sie die App-Schutzrichtlinien](app-protection-policies-monitor.md), die Sie erstellen und bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="7962e-126">[Monitor the app protection policies](app-protection-policies-monitor.md) that you create and deploy.</span></span> 

<span data-ttu-id="7962e-127">Für Windows 10-Geräte:</span><span class="sxs-lookup"><span data-stu-id="7962e-127">For Windows 10 devices:</span></span> 

1. <span data-ttu-id="7962e-128">Erfahren Sie, [wie Windows Information Protection (WIP) funktioniert](https://docs.microsoft.com/windows/threat-protection/windows-information-protection/protect-enterprise-data-using-wip).</span><span class="sxs-lookup"><span data-stu-id="7962e-128">Learn [how Windows Information Protection (WIP) works](https://docs.microsoft.com/windows/threat-protection/windows-information-protection/protect-enterprise-data-using-wip).</span></span> 
2. <span data-ttu-id="7962e-129">Machen Sie sich bereit für die Konfiguration von [App-Schutzrichtlinien für Windows 10](app-protection-policies-configure-windows-10.md).</span><span class="sxs-lookup"><span data-stu-id="7962e-129">Get ready to configure [app protection policies for Windows 10](app-protection-policies-configure-windows-10.md).</span></span>
3. <span data-ttu-id="7962e-130">[Erstellen Sie WIP-App-Schutzrichtlinien in Intune, und stellen Sie diese bereit](windows-information-protection-policy-create.md).</span><span class="sxs-lookup"><span data-stu-id="7962e-130">[Create and deploy WIP app protection policies with Intune](windows-information-protection-policy-create.md).</span></span>

## <a name="what-to-tell-employees-and-students"></a><span data-ttu-id="7962e-131">Informationen für Mitarbeiter und Studenten</span><span class="sxs-lookup"><span data-stu-id="7962e-131">What to tell employees and students</span></span>

<span data-ttu-id="7962e-132">Geben Sie nach Bedarf die folgenden Links frei, um zusätzliche Informationen bereitzustellen:</span><span class="sxs-lookup"><span data-stu-id="7962e-132">As appropriate, share the following links to provide additional information:</span></span> 
* [<span data-ttu-id="7962e-133">Was Sie erwartet, wenn Ihre iOS-App von App-Schutzrichtlinien verwaltet wird</span><span class="sxs-lookup"><span data-stu-id="7962e-133">What to expect when your iOS app is managed by app protection policies</span></span>](app-protection-enabled-apps-ios.md)
* [<span data-ttu-id="7962e-134">Was Sie erwartet, wenn Ihre Android-App von App-Schutzrichtlinien verwaltet wird</span><span class="sxs-lookup"><span data-stu-id="7962e-134">What to expect when your Android app is managed by app protection policies</span></span>](app-protection-enabled-apps-android.md) 

## <a name="next-steps"></a><span data-ttu-id="7962e-135">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="7962e-135">Next steps</span></span>

<span data-ttu-id="7962e-136">Benötigen Sie Hilfe bei der Aktivierung dieses oder anderer EMS- oder Office 365-Szenarios?</span><span class="sxs-lookup"><span data-stu-id="7962e-136">Want help enabling this or other EMS or Office 365 scenarios?</span></span> <span data-ttu-id="7962e-137">Wenn Sie über mindestens 150 Lizenzen für Microsoft 365, Enterprise Mobility + Security oder Azure Active Directory Premium verfügen, nutzen Sie Ihre [FastTrack-Vorteile](https://docs.microsoft.com/enterprise-mobility-security/solutions/enterprise-mobility-fasttrack-program).</span><span class="sxs-lookup"><span data-stu-id="7962e-137">If you have at least 150 licenses for Microsoft 365, Enterprise Mobility + Security, or Azure Active Directory Premium, use your [FastTrack benefits](https://docs.microsoft.com/enterprise-mobility-security/solutions/enterprise-mobility-fasttrack-program).</span></span> 