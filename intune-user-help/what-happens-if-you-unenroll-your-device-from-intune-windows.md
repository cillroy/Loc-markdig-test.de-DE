---
title: "Was geschieht, wenn Sie die Registrierung für Ihr Windows-Gerät aufheben? | Microsoft Docs"
description: 
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 01/23/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 47e03edb-0c57-4e25-8e89-4a1069267b8c
searchScope: User help
ROBOTS: 
ms.reviewer: priyar
ms.suite: ems
ms.custom: intune-enduser
ms.openlocfilehash: 710f91f72d9cf97acd0ac117b003eeb542449515
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2017
---
# <a name="what-happens-if-you-unenroll-your-windows-device-from-intune"></a><span data-ttu-id="c9b9c-103">Was geschieht, wenn Sie die Registrierung Ihres Windows-Geräts bei Intune aufheben?</span><span class="sxs-lookup"><span data-stu-id="c9b9c-103">What happens if you unenroll your Windows device from Intune?</span></span>

<span data-ttu-id="c9b9c-104">Informationen zum verwendeten Gerätetyp finden Sie über die Links rechts auf dieser Seite unter **Inhalt dieses Artikels**.</span><span class="sxs-lookup"><span data-stu-id="c9b9c-104">Use the links at the right side of this page, under **In this article**, to find information about the type of device you're using.</span></span>


## <a name="windows-10-windows-81-windows-8-windows-7-windows-vista"></a><span data-ttu-id="c9b9c-105">Windows 10, Windows 8.1, Windows 8, Windows 7, Windows Vista</span><span class="sxs-lookup"><span data-stu-id="c9b9c-105">Windows 10, Windows 8.1, Windows 8, Windows 7, Windows Vista</span></span>

-   <span data-ttu-id="c9b9c-106">Ihr Gerät wird nicht mehr im Unternehmensportal angezeigt, und Sie können über das Unternehmensportal keine Apps mehr installieren.</span><span class="sxs-lookup"><span data-stu-id="c9b9c-106">Your device doesn't appear in the Company Portal anymore, and you can’t install apps from the Company Portal anymore.</span></span>

-   <span data-ttu-id="c9b9c-107">Wenn die Intune-Clientsoftware installiert ist, wird diese von Ihrem Computer entfernt.</span><span class="sxs-lookup"><span data-stu-id="c9b9c-107">If you installed the Intune client software, it’s removed from your computer.</span></span>

-   <span data-ttu-id="c9b9c-108">Die Intune Endpoint Protection-Software wird von Ihrem Computer entfernt.</span><span class="sxs-lookup"><span data-stu-id="c9b9c-108">The Intune Endpoint Protection software is removed from your computer.</span></span> <span data-ttu-id="c9b9c-109">Wenn auf dem Computer eine andere Virenschutzsoftware installiert ist und diese deaktiviert wurde, kann sie nach dem Entfernen von Intune Endpoint Protection wieder aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="c9b9c-109">If your computer has other virus protection software installed and it is disabled, that software can be re-enabled after Intune Endpoint Protection is removed.</span></span> <span data-ttu-id="c9b9c-110">Überprüfen Sie Ihren Computer nach dem Entfernen aus dem Unternehmensportal.</span><span class="sxs-lookup"><span data-stu-id="c9b9c-110">Check your computer after removing it from the Company Portal.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="c9b9c-111">Wenn die andere Virenschutzsoftware nicht wieder aktiviert wird oder keine andere Virenschutzsoftware installiert ist, bleibt der Computer unter Umständen anfällig für Viren und Schadsoftware.</span><span class="sxs-lookup"><span data-stu-id="c9b9c-111">If the other virus protection software is not re-enabled or no other virus protection software is installed, your computer may be vulnerable to viruses and malware.</span></span>

-   <span data-ttu-id="c9b9c-112">Alle Einstellungen, die beim Hinzufügen des Geräts auf diesem geändert wurden (z.B. das Deaktivieren der Kamera), werden unwirksam.</span><span class="sxs-lookup"><span data-stu-id="c9b9c-112">Any settings that were changed on your device when you added it (for example, disabling the camera) no longer apply.</span></span>

-   <span data-ttu-id="c9b9c-113">Automatische Softwareupdates und Updates der Antivirensoftware vom Intune-Dienst werden nicht mehr auf dem Computer empfangen.</span><span class="sxs-lookup"><span data-stu-id="c9b9c-113">Your computer no longer receives automatic software updates or antivirus software updates from the Intune service.</span></span> <span data-ttu-id="c9b9c-114">Der Computer könnte jedoch je nach Einrichtung weiterhin Updates von Windows Server Update Services, Windows Update oder Microsoft Update empfangen.</span><span class="sxs-lookup"><span data-stu-id="c9b9c-114">But, depending on how it is set up, your computer might still receive updates from the Windows Server Update Services, Windows Update, or Microsoft Update.</span></span>

<span data-ttu-id="c9b9c-115">Zusätzlich für Windows 8.1:</span><span class="sxs-lookup"><span data-stu-id="c9b9c-115">In addition, for Windows 8.1:</span></span>

-   <span data-ttu-id="c9b9c-116">Sie können keine Unternehmens-Apps und Unternehmensdaten mehr auf dem Gerät verwenden.</span><span class="sxs-lookup"><span data-stu-id="c9b9c-116">You can’t use company apps and company data on your device anymore.</span></span>

-   <span data-ttu-id="c9b9c-117">In einigen E-Mail-Apps wie Windows Mail kann nicht mehr auf Unternehmens-E-Mails zugegriffen werden, die auf dem Gerät gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="c9b9c-117">Some email apps, like Windows Mail, can’t access company email that is stored on your device anymore.</span></span>

-   <span data-ttu-id="c9b9c-118">Möglicherweise können Sie keine Verbindung mit dem Unternehmensnetzwerk über WLAN oder ein virtuelles privates Netzwerk herstellen.</span><span class="sxs-lookup"><span data-stu-id="c9b9c-118">You might not be able to connect to your company network by using Wi-Fi or a virtual private network.</span></span>

-   <span data-ttu-id="c9b9c-119">Unter Umständen haben Sie auf dem Gerät keinen Zugriff mehr auf einige Unternehmensressourcen wie Dateifreigaben oder interne Websites.</span><span class="sxs-lookup"><span data-stu-id="c9b9c-119">You might not have access to some company resources, like file shares or internal websites, on your device anymore.</span></span>

## <a name="windows-10-mobile-and-windows-phone-81"></a><span data-ttu-id="c9b9c-120">Windows 10 Mobile und Windows Phone 8.1</span><span class="sxs-lookup"><span data-stu-id="c9b9c-120">Windows 10 mobile and Windows Phone 8.1</span></span>

-   <span data-ttu-id="c9b9c-121">Die Unternehmensportal-App wird auf Ihrem Gerät deinstalliert.</span><span class="sxs-lookup"><span data-stu-id="c9b9c-121">The Company Portal app is uninstalled from your device.</span></span> <span data-ttu-id="c9b9c-122">Ihr Gerät wird nicht mehr im Unternehmensportal angezeigt, und Sie können über die Unternehmensportal-App bzw. die Unternehmensportal-Website keine Apps installieren.</span><span class="sxs-lookup"><span data-stu-id="c9b9c-122">This means that your device doesn’t appear in the Company Portal anymore, and you can't install apps from the Company Portal app or the Company Portal website.</span></span>

-   <span data-ttu-id="c9b9c-123">Sie können keine Unternehmens-Apps und Unternehmensdaten mehr auf dem Gerät verwenden.</span><span class="sxs-lookup"><span data-stu-id="c9b9c-123">You can’t use company apps and company data on your device anymore.</span></span>

-   <span data-ttu-id="c9b9c-124">Alle Einstellungen, die beim Hinzufügen des Geräts auf diesem geändert wurden, z.B. das Deaktivieren der Kamera oder die Anforderung einer bestimmten Kennwortlänge, werden unwirksam.</span><span class="sxs-lookup"><span data-stu-id="c9b9c-124">Any settings that were changed on your device when you added it (for example, disabling the camera or requiring a certain password length) no longer apply.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="c9b9c-125">Die einzige Ausnahme sind die Verschlüsselungsrichtlinien, die weiterhin wirksam sind.</span><span class="sxs-lookup"><span data-stu-id="c9b9c-125">The only exception to this is encryption policies, which still apply.</span></span> <span data-ttu-id="c9b9c-126">Wenn in Ihrer Unternehmensrichtlinie vorgeschrieben war, dass Sie Ihr Windows Phone verschlüsseln, können Sie Ihr Telefon nur noch entschlüsseln, indem Sie es über das Menü **Einstellungen** zurücksetzen.</span><span class="sxs-lookup"><span data-stu-id="c9b9c-126">If your company policy required you to encrypt your Windows Phone, the only way to unencrypt your phone is to reset it by using the **Settings** menu.</span></span>

## <a name="windows-rt-running-windows-81"></a><span data-ttu-id="c9b9c-127">Windows RT, das Windows 8.1 ausführt</span><span class="sxs-lookup"><span data-stu-id="c9b9c-127">Windows RT running Windows 8.1</span></span>

-   <span data-ttu-id="c9b9c-128">Die Unternehmensportal-App wird auf Ihrem Gerät deinstalliert.</span><span class="sxs-lookup"><span data-stu-id="c9b9c-128">The Company Portal app is uninstalled from your device.</span></span> <span data-ttu-id="c9b9c-129">Das bedeutet, dass Ihr Gerät nicht mehr im Unternehmensportal angezeigt wird, und Sie über das Unternehmensportal keine Apps installieren können.</span><span class="sxs-lookup"><span data-stu-id="c9b9c-129">This means that your device doesn’t appear in the Company Portal anymore, and you can’t install apps from the Company Portal.</span></span>

-   <span data-ttu-id="c9b9c-130">Sie können keine Unternehmens-Apps und Unternehmensdaten mehr auf dem Gerät verwenden.</span><span class="sxs-lookup"><span data-stu-id="c9b9c-130">You can’t use company apps and company data on your device anymore.</span></span>

-   <span data-ttu-id="c9b9c-131">Alle Einstellungen, die beim Hinzufügen des Geräts auf diesem geändert wurden, z.B. das Deaktivieren der Kamera oder die Anforderung einer bestimmten Kennwortlänge, werden unwirksam.</span><span class="sxs-lookup"><span data-stu-id="c9b9c-131">Any settings that were changed on your device when you added it (for example, disabling the camera or requiring a certain password length) no longer apply.</span></span>

-   <span data-ttu-id="c9b9c-132">Möglicherweise können Sie mit dem Unternehmensnetzwerk keine Verbindung mehr über WLAN oder ein virtuelles privates Netzwerk (VPN) herstellen.</span><span class="sxs-lookup"><span data-stu-id="c9b9c-132">You might not be able to connect to your company network by using Wi-Fi or a virtual private network anymore.</span></span>

-   <span data-ttu-id="c9b9c-133">Unter Umständen haben Sie auf dem Gerät keinen Zugriff mehr auf einige Unternehmensressourcen wie Dateifreigaben oder interne Websites.</span><span class="sxs-lookup"><span data-stu-id="c9b9c-133">You might not have access to some company resources, like file shares or internal websites, on your device anymore.</span></span>

-   <span data-ttu-id="c9b9c-134">In einigen E-Mail-Apps wie Windows Mail kann nicht mehr auf Unternehmens-E-Mails zugegriffen werden, die auf dem Gerät gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="c9b9c-134">Some email apps, like Windows Mail, can’t access company email that is stored on your device anymore.</span></span>

<span data-ttu-id="c9b9c-135">Wenn Sie Ihr Windows RT-Gerät entfernen, geschieht Folgendes:</span><span class="sxs-lookup"><span data-stu-id="c9b9c-135">When you remove your Windows RT device, the following happens:</span></span>

-   <span data-ttu-id="c9b9c-136">Die Unternehmensportal-App wird auf Ihrem Gerät deinstalliert.</span><span class="sxs-lookup"><span data-stu-id="c9b9c-136">The Company Portal app is uninstalled from your device.</span></span> <span data-ttu-id="c9b9c-137">Das bedeutet, dass Ihr Gerät nicht mehr im Unternehmensportal angezeigt wird, und Sie über das Unternehmensportal keine Apps installieren können.</span><span class="sxs-lookup"><span data-stu-id="c9b9c-137">This means that your device doesn’t appear in the Company Portal anymore, and you can't install apps from the Company Portal.</span></span>

-   <span data-ttu-id="c9b9c-138">Sie können keine Unternehmens-Apps und Unternehmensdaten mehr auf dem Gerät verwenden.</span><span class="sxs-lookup"><span data-stu-id="c9b9c-138">You can’t use company apps and company data on your device anymore.</span></span>

-   <span data-ttu-id="c9b9c-139">Alle Einstellungen, die beim Hinzufügen des Geräts auf diesem geändert wurden, z.B. das Deaktivieren der Kamera oder die Anforderung einer bestimmten Kennwortlänge, werden unwirksam.</span><span class="sxs-lookup"><span data-stu-id="c9b9c-139">Any settings that were changed on your device when you added it (for example, disabling the camera or requiring a certain password length) no longer apply.</span></span>

<span data-ttu-id="c9b9c-140">Wenn Sie Fragen haben, wenden Sie sich an den Support Ihres Unternehmens.</span><span class="sxs-lookup"><span data-stu-id="c9b9c-140">If you have questions, contact your company support.</span></span> <span data-ttu-id="c9b9c-141">Die entsprechenden Kontaktinformationen finden Sie auf der [Unternehmensportal-Website](https://portal.manage.microsoft.com#HelpDeskDialog).</span><span class="sxs-lookup"><span data-stu-id="c9b9c-141">For contact information, check the [Company Portal website](https://portal.manage.microsoft.com#HelpDeskDialog).</span></span>
