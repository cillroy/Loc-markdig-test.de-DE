---
title: "Schützen von Office 365 Exchange Online ohne erforderliche Geräteverwaltung"
description: "Gewähren Sie Mitarbeitern Zugriff auf ihre geschäftlichen E-Mails. Es ist keine Geräteverwaltung erforderlich."
keywords: Office 365 Exchange-E-Mail-Zugriff
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 10/31/2017
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 88a0d3b9-2622-403b-8374-1396afd8066e
ms.reviewer: pchacon
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: cfd4453fe4b50a111a1f43efcdc6ba6447c46f40
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2017
---
# <a name="protect-office-365-exchange-online-without-requiring-device-management"></a><span data-ttu-id="be589-105">Schützen von Office 365 Exchange Online ohne erforderliche Geräteverwaltung</span><span class="sxs-lookup"><span data-stu-id="be589-105">Protect Office 365 Exchange Online without requiring device management</span></span>

<span data-ttu-id="be589-106">Sie möchten Mitarbeitern Zugriff auf ihre geschäftlichen E-Mails geben, ohne mit viel Aufwand ein Geräteverwaltungssystem einzurichten? Kein Problem.</span><span class="sxs-lookup"><span data-stu-id="be589-106">If you want to give employees access to their work email without the overhead of setting up a device management system, you can.</span></span> <span data-ttu-id="be589-107">Sie können über Intune Zugriff auf Office 365 Exchange Online gewähren.</span><span class="sxs-lookup"><span data-stu-id="be589-107">You can give access to Office 365 Exchange Online through Intune.</span></span> <span data-ttu-id="be589-108">Um die notwendigen Schritte durchzuführen, vergewissern Sie sich, dass Sie über Lizenzen für Microsoft 365 oder Azure Active Directory (Premium) und Intune verfügen.</span><span class="sxs-lookup"><span data-stu-id="be589-108">To complete the necessary steps, confirm you have licenses for Microsoft 365, or Azure Active Directory (premium) and Intune.</span></span> <span data-ttu-id="be589-109">Mitarbeiter müssen über ein [unterstütztes iOS- oder Android-Gerät](supported-devices-browsers.md) verfügen.</span><span class="sxs-lookup"><span data-stu-id="be589-109">Employees need to have a [supported iOS or Android device](supported-devices-browsers.md).</span></span> 

<span data-ttu-id="be589-110">Wenn Sie sich dafür entscheiden, ein Geräteverwaltungssystem einzurichten, können Sie das tun.</span><span class="sxs-lookup"><span data-stu-id="be589-110">If you decide to set up a device management system, you can.</span></span> <span data-ttu-id="be589-111">Diese Art von App-Schutz funktioniert unabhängig von der Geräteverwaltung.</span><span class="sxs-lookup"><span data-stu-id="be589-111">This type of app protection works independently of device management.</span></span> 

## <a name="action-plan"></a><span data-ttu-id="be589-112">Maßnahmenplan</span><span class="sxs-lookup"><span data-stu-id="be589-112">Action plan</span></span>

1. <span data-ttu-id="be589-113">[Weitere Informationen zum bedingten Zugriff](conditional-access.md).</span><span class="sxs-lookup"><span data-stu-id="be589-113">[Learn about conditional access](conditional-access.md).</span></span> 
2. <span data-ttu-id="be589-114">[Weitere Informationen zum App-basierten bedingten Zugriff](app-based-conditional-access-intune.md).</span><span class="sxs-lookup"><span data-stu-id="be589-114">[Learn about app-based conditional access](app-based-conditional-access-intune.md).</span></span>
3. <span data-ttu-id="be589-115">[Einrichten App-basierter Richtlinien für bedingten Zugriff](app-based-conditional-access-intune-create.md).</span><span class="sxs-lookup"><span data-stu-id="be589-115">[Set up app-based conditional access policies for Exchange Online](app-based-conditional-access-intune-create.md).</span></span>
4. <span data-ttu-id="be589-116">[Blockieren von Apps, die nicht verwaltet werden können](app-modern-authentication-block.md), insbesondere Apps, die nicht die Authentifizierungsbibliothek von Azure Active Directory (ADAL) verwenden.</span><span class="sxs-lookup"><span data-stu-id="be589-116">[Block apps that cannot be managed](app-modern-authentication-block.md), specifically apps that do not use the Azure Active Directory Authentication Library (ADAL).</span></span>
5. <span data-ttu-id="be589-117">(Optional) [Einrichten App-basierter Richtlinien für bedingten Zugriff](app-based-conditional-access-intune-create.md).</span><span class="sxs-lookup"><span data-stu-id="be589-117">(Optional) [Set up app-based conditional access policies for SharePoint Online](app-based-conditional-access-intune-create.md).</span></span> <span data-ttu-id="be589-118">Diese Richtlinien blockieren den Zugriff auf Ihre Unternehmensdaten über Apps, die nicht verwaltet und geschützt werden können.</span><span class="sxs-lookup"><span data-stu-id="be589-118">These policies block access to your company data from apps that cannot be managed and secured.</span></span> <span data-ttu-id="be589-119">Die Richtlinien beschränken auch den Zugriff über die mobile Version von SharePoint.</span><span class="sxs-lookup"><span data-stu-id="be589-119">The policies also limit access through SharePoint mobile.</span></span> 

## <a name="what-to-tell-employees-and-students"></a><span data-ttu-id="be589-120">Informationen für Mitarbeiter und Studenten</span><span class="sxs-lookup"><span data-stu-id="be589-120">What to tell employees and students</span></span>

* <span data-ttu-id="be589-121">Bitten Sie Ihre Mitarbeiter und Studenten, Microsoft Outlook oder Microsoft SharePoint für iOS aus dem Apple App Store oder für Android aus dem Google Play Store herunterzuladen.</span><span class="sxs-lookup"><span data-stu-id="be589-121">Ask your employees and students to download and install Microsoft Outlook or Microsoft SharePoint for iOS from the Apple App Store or for Android from the Google Play Store.</span></span> 
* <span data-ttu-id="be589-122">Wenn Sie den Zugriff auf Apps blockieren, die keine moderne Authentifizierung verwenden, informieren Sie die Mitarbeiter und Studenten darüber.</span><span class="sxs-lookup"><span data-stu-id="be589-122">If you block access to apps that do not use modern authentication, let the employees and students know of this restriction.</span></span> 

## <a name="next-steps"></a><span data-ttu-id="be589-123">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="be589-123">Next steps</span></span>

<span data-ttu-id="be589-124">Sie haben den App-basierten bedingten Zugriff verwendet, um die Sicherheit der Unternehmensdaten zu erhöhen.</span><span class="sxs-lookup"><span data-stu-id="be589-124">You have used app-based conditional access to increase the security of company data.</span></span> <span data-ttu-id="be589-125">Im Zuge der nächsten Schritte können Sie mehr über die anderen Möglichkeiten erfahren, den Schutz Ihrer Unternehmensdaten zu erhöhen. Dazu zählt Folgendes:</span><span class="sxs-lookup"><span data-stu-id="be589-125">As part of next steps, you can learn more about the other ways you can increase the protection of your company's data, including:</span></span> 

* <span data-ttu-id="be589-126">Einrichten des [bedingten Zugriffs basierend auf der Gerätekompatibilität, dem Geräterisiko, dem Speicherort und Benutzerattributen in Active Directory und Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal)</span><span class="sxs-lookup"><span data-stu-id="be589-126">Setting up [conditional access based on device compliance, device risk, location, and user attributes in Active Directory and Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal).</span></span>  
* <span data-ttu-id="be589-127">Einrichten von App-Schutzrichtlinien zum Schutz Ihrer Unternehmensdaten vor versehentlichen und vorsätzlichen Datenverlusten</span><span class="sxs-lookup"><span data-stu-id="be589-127">Setting up app protection policies to help you protect your company data against intentional or unintentional data leaks.</span></span> 
* <span data-ttu-id="be589-128">Verwenden von Azure Information Protection zum Schutz von Unternehmensdaten außerhalb Ihres Netzwerks</span><span class="sxs-lookup"><span data-stu-id="be589-128">Leveraging Azure Information Protection to protect company data outside your network.</span></span> 

<span data-ttu-id="be589-129">Benötigen Sie Hilfe bei der Aktivierung dieses oder anderer EMS- oder Office 365-Szenarios?</span><span class="sxs-lookup"><span data-stu-id="be589-129">Want help enabling this or other EMS or Office 365 scenarios?</span></span> <span data-ttu-id="be589-130">Wenn Sie über mindestens 150 Lizenzen für Microsoft 365, Enterprise Mobility + Security oder Azure Active Directory Premium verfügen, nutzen Sie Ihre [FastTrack-Vorteile](https://docs.microsoft.com/enterprise-mobility-security/solutions/enterprise-mobility-fasttrack-program).</span><span class="sxs-lookup"><span data-stu-id="be589-130">If you have at least 150 licenses for Microsoft 365, Enterprise Mobility + Security, or Azure Active Directory Premium, use your [FastTrack benefits](https://docs.microsoft.com/enterprise-mobility-security/solutions/enterprise-mobility-fasttrack-program).</span></span> 