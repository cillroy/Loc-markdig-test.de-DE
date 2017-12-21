---
title: Verhindern von Kompromittierungen im Unternehmen durch mobile Office 365-Apps
description: "Verwenden Sie Intune, um die Daten Ihres Unternehmens mithilfe von MAM-Richtlinien (mobile Anwendungsverwaltung) zu schützen, die dabei helfen, Verluste von Unternehmensdaten aus mobilen Office 365-Apps oder anderen branchenspezifischen Apps zu verhindern."
keywords: 
author: jeffgilb
ms.author: jeffgilb
manager: angrobe
ms.date: 11/22/2016
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 19be3de7-539c-49f5-8c46-5363b987fef9
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: pchacon
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: a1b792148371d61132b5c5d7f16be6c3eb2d2355
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2017
---
# <a name="quick-start-guide-prevent-company-data-leaks-from-office-365-mobile-apps"></a><span data-ttu-id="e2d0c-103">Erste Schritte: Verhindern von Kompromittierungen im Unternehmen durch mobile Office 365-Apps</span><span class="sxs-lookup"><span data-stu-id="e2d0c-103">Quick Start Guide: Prevent company data leaks from Office 365 mobile apps</span></span>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="e2d0c-104">Microsoft Intune kann Sie dabei unterstützen, die Daten im Unternehmen mithilfe von MAM-Richtlinien (mobile Anwendungsverwaltung) zu schützen, die dabei helfen, die Kompromittierung von Daten im Unternehmen durch mobile Office 365-Apps oder andere branchenspezifische Apps zu verhindern.</span><span class="sxs-lookup"><span data-stu-id="e2d0c-104">Microsoft Intune can help you secure your organization’s data using mobile application management (MAM) policies that help prevent company data leaks from Office 365 mobile apps or other line of business (LOB) apps.</span></span> <span data-ttu-id="e2d0c-105">Für die Verwendung der MAM-Richtlinien von Intune ist keine Registrierung der Geräte der Benutzer in MDM (mobile Geräteverwaltung) erforderlich.</span><span class="sxs-lookup"><span data-stu-id="e2d0c-105">Intune MAM policies can be used without requiring end users to enroll their devices in Intune mobile device management (MDM).</span></span> <span data-ttu-id="e2d0c-106">Wenn daher Benutzer vorhanden sind, die Ihre privaten mobilen iOS- oder Android-Geräte nicht in einer Microsoft MDM-Lösung (Intune, Configuration Manager oder EAS) registrieren möchten, kann Intune Ihnen dabei helfen, die Datensicherheit im Unternehmen zu erhöhen, wenn Sie die Unternehmensdaten ohne Verwaltung der Endbenutzergeräte schützen möchten oder Sie bereits eine nicht von Microsoft stammende MDM-Lösung verwenden.</span><span class="sxs-lookup"><span data-stu-id="e2d0c-106">So, if you have users who do not want to enroll their BYOD iOS or Android mobile devices into a Microsoft MDM solution (Intune, Configuration Manager, or EAS), you want to protect corporate data without managing end users devices, or you are already using a non-Microsoft MDM solution, Intune can help you increase your company’s data security.</span></span>   

## <a name="is-this-quick-start-guide-right-for-me"></a><span data-ttu-id="e2d0c-107">Ist dieses Schnellstarthandbuch für mich geeignet?</span><span class="sxs-lookup"><span data-stu-id="e2d0c-107">Is this quick start guide right for me?</span></span>
<span data-ttu-id="e2d0c-108">Möchten Sie Ihren Endbenutzern den Zugriff auf Ihre Office 365-Daten und Daten branchenspezifischer Apps auf ihren iOS- und Android-Geräten gestatten, ohne eine Registrierung in einer MDM-Lösung (mobile Geräteverwaltung) zu erfordern, wobei Sie dennoch kontrollieren können, welche Aktionen die Benutzer mit diesen Daten durchführen können (z. B. Daten kopieren und in privaten Apps einfügen)?</span><span class="sxs-lookup"><span data-stu-id="e2d0c-108">Would you like to allow your end users to access your Office 365 and LOB app data on their iOS and Android devices without requiring device enrollment in a Mobile Device Management (MDM) solution, but still control what they can or cannot do with that data such as copying and pasting it onto personal apps?</span></span>

<span data-ttu-id="e2d0c-109">Wenn dies der Fall ist, können Sie mit Microsoft Intune entsprechende MAM-Richtlinien für mobile Office 365-Apps auf iOS- und Android-Geräten festlegen (einschließlich der Einschränkungen zum Ausschneiden/Kopieren/Einfügen, der Verhinderung von „Speichern unter“, dem Festlegen von PIN-Anforderungen sowie die Möglichkeit zur Remotezurücksetzung von Daten, die MAM-geschützt sind.</span><span class="sxs-lookup"><span data-stu-id="e2d0c-109">If yes, Microsoft Intune allows you to set MAM policies for Office 365 mobile apps on iOS and Android, including cut/copy/paste restrictions, preventing ‘save-as’, setting PIN requirements, and the ability to remotely wipe MAM protected data.</span></span>  <span data-ttu-id="e2d0c-110">Dadurch werden Unternehmensdaten geschützt, ohne dass Benutzer ihre Geräte in einer MDM-Lösung registrieren müssen, wobei gleichzeitig eine hervorragende Endbenutzererfahrung mit mobilen Office-Apps bewahrt wird.</span><span class="sxs-lookup"><span data-stu-id="e2d0c-110">This protects company data without requiring users to enroll their devices into an MDM solution while maintaining a great end-user experience with Office mobile apps.</span></span>

## <a name="how-do-i-do-it"></a><span data-ttu-id="e2d0c-111">Wie gehe ich dabei vor?</span><span class="sxs-lookup"><span data-stu-id="e2d0c-111">How do I do it?</span></span>
1.  <span data-ttu-id="e2d0c-112">Erhalten Sie grundlegende Kenntnisse zur [Funktionsweise der mobilen Anwendungsverwaltung (MAM) mit Intune](/intune-classic/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune).</span><span class="sxs-lookup"><span data-stu-id="e2d0c-112">Get a basic understanding of [how Intune mobile application management (MAM)](/intune-classic/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune) works.</span></span>
2.  <span data-ttu-id="e2d0c-113">Erhalten Sie weitere Informationen dazu, [welche Schritte Sie ausführen müssen, bevor Sie im Azure-Portal Richtlinien für die Verwaltung von mobilen Apps (MAM, Mobile App Management) erstellen können](/intune-classic/deploy-use/get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune).</span><span class="sxs-lookup"><span data-stu-id="e2d0c-113">Find out [what you need to do before you can create MAM policies](/intune-classic/deploy-use/get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune) in the Azure portal.</span></span>
3.  <span data-ttu-id="e2d0c-114">[Erstellen und Bereitstellen von MAM-Richtlinien](/intune-classic/deploy-use/get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune) mit Intune.</span><span class="sxs-lookup"><span data-stu-id="e2d0c-114">[Create and deploy MAM policies](/intune-classic/deploy-use/get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune) with Intune.</span></span>

### <a name="additional-information"></a><span data-ttu-id="e2d0c-115">Zusätzliche Informationen:</span><span class="sxs-lookup"><span data-stu-id="e2d0c-115">Additional information:</span></span>
- <span data-ttu-id="e2d0c-116">[Endbenutzererfahrung](/intune-classic/deploy-use/end-user-experience-for-mam-enabled-apps-with-microsoft-intune) mit MAM-fähigen Apps</span><span class="sxs-lookup"><span data-stu-id="e2d0c-116">[End user experience](/intune-classic/deploy-use/end-user-experience-for-mam-enabled-apps-with-microsoft-intune) using MAM enabled apps.</span></span>
- [<span data-ttu-id="e2d0c-117">Vorbereiten von branchenspezifischen Apps für MAM mit Intune</span><span class="sxs-lookup"><span data-stu-id="e2d0c-117">Prepare LOB apps for MAM with Intune</span></span>](/intune/apps-prepare-mobile-application-management)
- <span data-ttu-id="e2d0c-118"><a href="https://www.microsoft.com/cloud-platform/microsoft-intune-partners" target="_blank">Liste der Microsoft Intune-Anwendungspartner&rarr;</a>, die MAM-fähige Apps bereitstellen</span><span class="sxs-lookup"><span data-stu-id="e2d0c-118"><a href="https://www.microsoft.com/cloud-platform/microsoft-intune-partners" target="_blank"> List of Microsoft Intune application partners &rarr;</a> providing MAM-enabled apps.</span></span>

## <a name="what-should-i-do-next"></a><span data-ttu-id="e2d0c-119">Wie sollte ich als nächstes vorgehen?</span><span class="sxs-lookup"><span data-stu-id="e2d0c-119">What should I do next?</span></span>
[<span data-ttu-id="e2d0c-120">Migration von einer Nicht-Microsoft-MDM-Lösung zu Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="e2d0c-120">Migrate from a non-Microsoft MDM solution to Microsoft Intune</span></span>](/intune-classic/deploy-use/migrate-to-intune)

[<span data-ttu-id="e2d0c-121">Registrieren von Geräten bei Intune MDM</span><span class="sxs-lookup"><span data-stu-id="e2d0c-121">Enroll devices into Intune MDM</span></span>](/intune-classic/deploy-use/enroll-devices-in-microsoft-intune)
