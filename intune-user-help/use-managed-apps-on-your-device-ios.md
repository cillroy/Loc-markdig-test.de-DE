---
title: "Verwenden verwalteter Apps auf Ihrem iOS-Gerät | Microsoft-Dokumentation"
description: 
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 07/14/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3232c5c1-cb9f-45ca-806f-7e74eeb3533e
searchScope: User help
ROBOTS: 
ms.reviewer: maxles
ms.suite: ems
ms.custom: intune-enduser
ms.openlocfilehash: 8c3d9285408f2cfa394ed31ec36fcaea47306eb5
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2017
---
# <a name="use-managed-apps-on-your-ios-device"></a><span data-ttu-id="660e8-102">Verwenden verwalteter Apps auf Ihrem iOS-Gerät</span><span class="sxs-lookup"><span data-stu-id="660e8-102">Use managed apps on your iOS device</span></span>

<span data-ttu-id="660e8-103">Verwaltete Apps sind Apps, die der Support Ihres Unternehmens einrichten kann, um Unternehmensdaten zu schützen, auf die Sie in der App zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="660e8-103">Managed apps are apps that your company support can set up to help protect company data that you can access in that app.</span></span> <span data-ttu-id="660e8-104">Wenn Sie in einer verwalteten App auf Ihrem iOS-Gerät auf Unternehmensdaten zugreifen, werden Sie feststellen, dass die App ein wenig anders als erwartet funktioniert.</span><span class="sxs-lookup"><span data-stu-id="660e8-104">When you access company data in a managed app on your iOS device, you may notice that the app works a little differently than what you expect.</span></span> <span data-ttu-id="660e8-105">Sie können beispielsweise ggf. geschützte Unternehmensdaten nicht kopieren und einfügen oder diese Daten nicht an bestimmten Speicherorten speichern.</span><span class="sxs-lookup"><span data-stu-id="660e8-105">For example, you might not be able to copy and paste protected company data, or you might not be able to save that data to certain locations.</span></span>

<span data-ttu-id="660e8-106">Unterschiedliche verwaltete Apps können auch auf Ihrem Gerät zusammenarbeiten, um Ihnen das Erledigen Ihrer täglichen Aufgaben zu ermöglichen, während Unternehmensdaten geschützt bleiben.</span><span class="sxs-lookup"><span data-stu-id="660e8-106">Different managed apps can also work together on your device to allow you to do your daily tasks, while keeping corporate data protected.</span></span> <span data-ttu-id="660e8-107">Wenn Sie z. B. eine Unternehmensdatei in einer verwalteten App öffnen und eine andere verwaltete App zum Anzeigen dieser Datei erforderlich ist, erlaubt die verwaltete App Ihnen automatisch das Anzeigen der Datei.</span><span class="sxs-lookup"><span data-stu-id="660e8-107">For example, if you open a company file in one managed app, and another managed app is required to view that file, the managed app that allows you to view the file opens automatically.</span></span> <span data-ttu-id="660e8-108">Wenn eine erforderliche App nicht verfügbar ist, sind bestimmte Vorgänge, z. B. Öffnen eines Dokuments oder Zugreifen auf einen Weblink aus einem verwalteten Dokument, ggf. nicht möglich.</span><span class="sxs-lookup"><span data-stu-id="660e8-108">If a required app is not available, certain actions, like opening a document or accessing a web link from within a managed document, might not be available.</span></span>

<span data-ttu-id="660e8-109">Wenn Sie in einer verwalteten App auf Unternehmensdaten zugreifen, wird eine Meldung wie die folgende angezeigt, die Sie informiert, dass die App, die Sie öffnen, verwaltet wird.</span><span class="sxs-lookup"><span data-stu-id="660e8-109">When you access company data in a managed app, you see a message like the one below, which lets you know that the app you are opening is managed.</span></span>

![managed-apps-message-ios](./media/managed-apps-message.png)

### <a name="how-do-i-get-managed-apps"></a><span data-ttu-id="660e8-111">Wie erhalte ich verwaltete Apps?</span><span class="sxs-lookup"><span data-stu-id="660e8-111">How do I get managed apps?</span></span>
<span data-ttu-id="660e8-112">Es gibt verschiedene Möglichkeiten, verwaltete Apps zu erhalten:</span><span class="sxs-lookup"><span data-stu-id="660e8-112">You get managed apps in a couple of different ways:</span></span>

-   <span data-ttu-id="660e8-113">Wenn Ihr Gerät bei Microsoft Intune registriert ist, installieren Sie die App entweder über die Unternehmensportal-App oder -Website, oder der Support Ihres Unternehmens installiert sie auf Ihrem Gerät.</span><span class="sxs-lookup"><span data-stu-id="660e8-113">When your device is enrolled in Microsoft Intune, you either install the app from your Company Portal app or Company Portal website, or your company support might install it on your device.</span></span> <span data-ttu-id="660e8-114">Informationen zum Registrieren finden Sie unter [Registrieren Ihres iOS-Geräts bei Intune](enroll-your-device-in-intune-ios.md) oder [Registrieren Ihres macOS-Geräts bei Intune](enroll-your-device-in-intune-macos.md).</span><span class="sxs-lookup"><span data-stu-id="660e8-114">To learn about enrolling, see [Enroll your iOS device in Intune](enroll-your-device-in-intune-ios.md) or [Enroll your macOS device in Intune](enroll-your-device-in-intune-macos.md).</span></span>

-   <span data-ttu-id="660e8-115">Sie installieren eine App aus dem App Store und melden sich dann mit Ihrem Unternehmensbenutzerkonto an, das von Intune verwaltet wird.</span><span class="sxs-lookup"><span data-stu-id="660e8-115">You install an app from the App Store, and then sign in with your corporate user account that is managed by Intune.</span></span>

<span data-ttu-id="660e8-116">Der Support Ihres Unternehmens kauft womöglich in einigen Fällen mehrere Lizenzen für eine App, die Sie installieren.</span><span class="sxs-lookup"><span data-stu-id="660e8-116">Your company support might sometimes purchase multiple licenses for an app you install.</span></span> <span data-ttu-id="660e8-117">Wenn Sie eine Meldung sehen, die Sie auffordert, die Apple Volume Purchase Program-Vereinbarung zu akzeptieren, ist dies normal, und Sie können sie akzeptieren.</span><span class="sxs-lookup"><span data-stu-id="660e8-117">If you see a message asking you to accept the Apple Volume Purchase Program agreement, this is normal, and you can accept it.</span></span> <span data-ttu-id="660e8-118">Wenn Sie die Vereinbarung nicht akzeptieren, können Sie die App nicht installieren.</span><span class="sxs-lookup"><span data-stu-id="660e8-118">If you don’t accept it, you won’t be able to install the app.</span></span>

### <a name="what-can-my-company-support-manage-in-an-app"></a><span data-ttu-id="660e8-119">Was kann der Support meines Unternehmens in einer App verwalten?</span><span class="sxs-lookup"><span data-stu-id="660e8-119">What can my company support manage in an app?</span></span>
<span data-ttu-id="660e8-120">Es folgen einige Beispiele für Optionen, die der Support Ihres Unternehmens in einer App verwalten kann und die sich auf Ihre Interaktionen mit Unternehmensdaten auf Ihrem Gerät auswirken können:</span><span class="sxs-lookup"><span data-stu-id="660e8-120">Here are some examples of options that your company support can manage in an app, and that can affect your interactions with company data on your device:</span></span>

-   <span data-ttu-id="660e8-121">Zugriff auf bestimmte Websites</span><span class="sxs-lookup"><span data-stu-id="660e8-121">Access to specific websites</span></span>

-   <span data-ttu-id="660e8-122">Übertragung von Daten zwischen Anwendungen</span><span class="sxs-lookup"><span data-stu-id="660e8-122">Transfers of data between apps</span></span>

-   <span data-ttu-id="660e8-123">Speichern von Dateien</span><span class="sxs-lookup"><span data-stu-id="660e8-123">Saving files</span></span>

-   <span data-ttu-id="660e8-124">Kopier- und Einfügevorgänge</span><span class="sxs-lookup"><span data-stu-id="660e8-124">Copy and paste operations</span></span>

-   <span data-ttu-id="660e8-125">PIN-Zugriffsanforderungen</span><span class="sxs-lookup"><span data-stu-id="660e8-125">PIN access requirements</span></span>

-   <span data-ttu-id="660e8-126">Ihre Anmeldung mit Unternehmensanmeldeinformationen</span><span class="sxs-lookup"><span data-stu-id="660e8-126">Your sign in, using company credentials</span></span>

-   <span data-ttu-id="660e8-127">Fähigkeit zur Sicherung in der Cloud</span><span class="sxs-lookup"><span data-stu-id="660e8-127">Ability to back up to the cloud</span></span>

-   <span data-ttu-id="660e8-128">Fähigkeit zur Erstellung von Screenshots</span><span class="sxs-lookup"><span data-stu-id="660e8-128">Ability to take screenshots</span></span>

-   <span data-ttu-id="660e8-129">Anforderungen für die Verschlüsselung von Daten</span><span class="sxs-lookup"><span data-stu-id="660e8-129">Data encryption requirements</span></span>

<span data-ttu-id="660e8-130">Wenden Sie sich an den Support Ihres Unternehmens, um weitere Informationen zu den verwalteten Apps auf dem Gerät zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="660e8-130">Contact your company support for more information about the managed apps on your device.</span></span> <span data-ttu-id="660e8-131">Die entsprechenden Kontaktinformationen finden Sie auf der [Unternehmensportal-Website](https://portal.manage.microsoft.com#HelpDeskDialog).</span><span class="sxs-lookup"><span data-stu-id="660e8-131">For contact information, check the [Company Portal website](https://portal.manage.microsoft.com#HelpDeskDialog).</span></span>
