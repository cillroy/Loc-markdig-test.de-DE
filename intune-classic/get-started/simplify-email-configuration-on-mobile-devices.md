---
title: "Vereinfachen der E-Mail-Konfiguration auf mobilen Geräten"
description: 
keywords: 
author: jeffgilb
ms.author: jeffgilb
manager: angrobe
ms.date: 12/22/2016
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 1696c715-1e9a-401e-a530-77904fd189ad
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: pchacon
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: ce3edb95bcb4211c4592887f9654ab77800e907e
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2018
---
# <a name="quick-start-guide-simplify-email-configuration-on-mobile-devices"></a><span data-ttu-id="250b5-102">Erste Schritte: Vereinfachen der E-Mail-Konfiguration auf mobilen Geräten</span><span class="sxs-lookup"><span data-stu-id="250b5-102">Quick Start Guide: Simplify email configuration on mobile devices</span></span>

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="250b5-103">Microsoft Intune spart Ihrem Unternehmen Zeit und Ressourcen, indem es Ihnen ermöglicht wird, E-Mail-Profile (sowie VPN- und WLAN-Profile) für Windows-, iOS- und Android-Mobilgeräte bereitzustellen, die vom Intune-Dienst verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="250b5-103">Microsoft Intune saves your company time and resources by allowing you to deploy email (as well as VPN and WiFi) profiles to Windows, iOS and Android mobile devices managed by the Intune service.</span></span> <span data-ttu-id="250b5-104">Die automatische Konfiguration von E-Mail-Profilen kann die Endbenutzererfahrung erheblich verbessern und die Kundenzufriedenheit erhöhen sowie gleichzeitig die Kosten für den Helpdesk reduzieren.</span><span class="sxs-lookup"><span data-stu-id="250b5-104">Automatically configuring email profiles can greatly improve the end-user experience and increase satisfaction levels while at the same time reduce your helpdesk costs.</span></span>

## <a name="is-this-quick-start-guide-right-for-me"></a><span data-ttu-id="250b5-105">Ist dieses Schnellstarthandbuch für mich geeignet?</span><span class="sxs-lookup"><span data-stu-id="250b5-105">Is this quick start guide right for me?</span></span>
<span data-ttu-id="250b5-106">Möchten Sie die Zeit und den Aufwand verringern, die Ihre Benutzer zum Konfigurieren neuer E-Mail-Profile auf mobilen Geräten benötigen, während Sie gleichzeitig die Sicherheit der Unternehmensdaten erhöhen, indem nur mobilen Geräten der Zugriff auf geschäftliche E-Mails gestattet wird, die von Intune verwaltet werden?</span><span class="sxs-lookup"><span data-stu-id="250b5-106">Would like to reduce the time and effort required by your users to configure new email profiles on mobile devices from while also increasing your company’s data security by only allowing mobile devices managed by Intune to access your company email?</span></span>

<span data-ttu-id="250b5-107">Wenn dies der Fall ist, kann Microsoft Intune für die von Intune verwalteten Geräte Ihrer Mitarbeiter automatisch die E-Mail-Funktion konfigurieren, indem E-Mail-Profile auf ihren Geräten bereitgestellt werden, damit sie den Zugriff auf geschäftliche E-Mails nicht manuell konfigurieren müssen.</span><span class="sxs-lookup"><span data-stu-id="250b5-107">If yes, Microsoft Intune can automatically configure email for your employees’ Intune-managed devices by deploying email profiles to their devices so that they don’t have to manually configure access to their company email.</span></span> <span data-ttu-id="250b5-108">Diese Funktion bietet eine bessere Endbenutzererfahrung und verringert insgesamt die Kosten für den Helpdesk, indem die Anzahl der Aktivitäten für E-Mail-Konfigurationsprobleme auf den Windows-, iOS- und Android-Geräten der Benutzer reduziert werden.</span><span class="sxs-lookup"><span data-stu-id="250b5-108">This capability provides a better end-user experience and reduces overall helpdesk costs by driving down the number of escalations for email configuration issues on your users Windows, iOS, and Android devices.</span></span>

<span data-ttu-id="250b5-109">Nachdem das E-Mail-Profil konfiguriert wurde, können Sie den Zugriff auf geschäftliche E-Mails und Office 365-Dienste mithilfe der Intune-Richtlinien für den bedingten Zugriff problemlos einschränken.</span><span class="sxs-lookup"><span data-stu-id="250b5-109">After the email profile is configured, you can easily restrict access to company email and Office 365 services with Intune conditional access policies.</span></span> <span data-ttu-id="250b5-110">Mithilfe dieser Richtlinien können Sie sicherstellen, dass der Zugriff auf die geschäftlichen E-Mails und Office 365-Dienste auf Geräte beschränkt ist, die den von Ihnen in Intune festgelegten Regeln entsprechen.</span><span class="sxs-lookup"><span data-stu-id="250b5-110">These policies allow you to make sure that access to your company email and Office 365 services is restricted to devices that are compliant with the rules that you set in Intune.</span></span>

## <a name="how-do-i-do-it"></a><span data-ttu-id="250b5-111">Wie gehe ich dabei vor?</span><span class="sxs-lookup"><span data-stu-id="250b5-111">How do I do it?</span></span>
1.  <span data-ttu-id="250b5-112">[Konfigurieren Sie die E-Mail-Profile der Endbenutzer automatisch](/intune-classic/deploy-use/configure-access-to-corporate-email-using-email-profiles-with-microsoft-intune) auf Windows-, iOS- und Android-Geräten.</span><span class="sxs-lookup"><span data-stu-id="250b5-112">Automatically [configure end-user email profiles](/intune-classic/deploy-use/configure-access-to-corporate-email-using-email-profiles-with-microsoft-intune) on Windows, iOS, and Android devices.</span></span>
2.  <span data-ttu-id="250b5-113">[Kontrollieren Sie den Zugriff auf geschäftliche E-Mails](/intune-classic/deploy-use/restrict-access-to-email-and-o365-services-with-microsoft-intune) mithilfe von Richtlinien für den bedingten Zugriff.</span><span class="sxs-lookup"><span data-stu-id="250b5-113">[Control access to company email](/intune-classic/deploy-use/restrict-access-to-email-and-o365-services-with-microsoft-intune) using conditional access policies.</span></span>


### <a name="additional-information"></a><span data-ttu-id="250b5-114">Zusätzliche Informationen:</span><span class="sxs-lookup"><span data-stu-id="250b5-114">Additional information:</span></span>
[<span data-ttu-id="250b5-115">Intune-Geräteeinstellungen und -Sicherheit</span><span class="sxs-lookup"><span data-stu-id="250b5-115">Intune device settings and security</span></span>](/intune-classic/deploy-use/manage-settings-and-features-on-your-devices-with-microsoft-intune-policies)

## <a name="what-should-i-do-next"></a><span data-ttu-id="250b5-116">Wie sollte ich als nächstes vorgehen?</span><span class="sxs-lookup"><span data-stu-id="250b5-116">What should I do next?</span></span>
[<span data-ttu-id="250b5-117">Bereitstellen von VPN-Profilen für verwaltete Geräte</span><span class="sxs-lookup"><span data-stu-id="250b5-117">Deploy VPN profiles to managed devices</span></span>](/intune-classic/deploy-use/vpn-connections-in-microsoft-intune)

[<span data-ttu-id="250b5-118">Bereitstellen von WLAN-Profilen für verwaltete Geräte</span><span class="sxs-lookup"><span data-stu-id="250b5-118">Deploy Wi-Fi profiles to managed devices</span></span>](/intune-classic/deploy-use/wi-fi-connections-in-microsoft-intune)

[<span data-ttu-id="250b5-119">Sicherer Ressourcenzugriff mit Zertifikatprofilen in Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="250b5-119">Secure resource access with certificate profiles in Microsoft Intune</span></span>](/intune-classic/deploy-use/secure-resource-access-with-certificate-profiles)
