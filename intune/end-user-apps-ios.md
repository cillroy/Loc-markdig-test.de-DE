---
title: Wie Ihre iOS-Benutzer Apps erhalten
description: "Methoden, um iOS-Apps für Endbenutzer verfügbar zu machen."
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 10/28/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 7e3135c1-df26-48c9-aa4c-cdab6168897a
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 32bc1910c2d1c781dc09e6d747de727c20ff1989
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2017
---
# <a name="how-your-ios-users-get-their-apps"></a><span data-ttu-id="f75dc-103">Wie Ihre iOS-Benutzer Apps erhalten</span><span class="sxs-lookup"><span data-stu-id="f75dc-103">How your iOS users get their apps</span></span>

[!INCLUDE[both-portals](./includes/note-for-both-portals.md)]

<span data-ttu-id="f75dc-104">Verwenden Sie diese Informationen, um zu verstehen, wie und wo Ihre Endbenutzer die Apps erhalten, die Sie über Microsoft Intune verteilen.</span><span class="sxs-lookup"><span data-stu-id="f75dc-104">Use this information to understand how and where your end users get the apps that you distribute through Microsoft Intune.</span></span>

<span data-ttu-id="f75dc-105">**Erforderliche Apps:** Apps, die vom Administrator benötigt werden und auf dem Gerät (abhängig von der Plattform) mit minimalen Benutzereingriffen installiert werden.</span><span class="sxs-lookup"><span data-stu-id="f75dc-105">**Required apps**--Apps that are required by the admin and that are installed on the device with minimal user involvement, depending on the platform.</span></span>

<span data-ttu-id="f75dc-106">**Verfügbare Apps:** Apps, die in der App-Liste im Unternehmensportal enthalten sind und die ein Benutzer optional installieren kann.</span><span class="sxs-lookup"><span data-stu-id="f75dc-106">**Available apps**--Apps that are provided in the Company Portal app list and that a user may optionally choose to install.</span></span>

<span data-ttu-id="f75dc-107">**Verwaltete Apps:** Apps, die mittels Richtlinien verwaltet werden können und die von Intune „umschlossen“ werden oder mit dem Software Development Kit (SDK) für die Intune-App erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="f75dc-107">**Managed apps**--Apps that can be managed through policies and that have been "wrapped" by Intune or have been built with the Intune App Software Development Kit (SDK).</span></span> <span data-ttu-id="f75dc-108">Diese Apps können von Intune verwaltet werden, und ihnen lassen sich App-Schutzrichtlinien zuweisen.</span><span class="sxs-lookup"><span data-stu-id="f75dc-108">These apps can be managed by Intune, and app protection policies can be applied to them.</span></span>

<span data-ttu-id="f75dc-109">**Nicht verwaltete Apps**: Apps, die mittels Richtlinien verwaltet werden können und die nicht von Intune umschlossen wurden oder nicht in das Intune SDK integriert sind.</span><span class="sxs-lookup"><span data-stu-id="f75dc-109">**Unmanaged apps**--Apps that can be managed through policies and that have not been wrapped by Intune or that do not incorporate the Intune App SDK.</span></span> <span data-ttu-id="f75dc-110">Diesen Apps lassen sich keine Anwendungsrichtlinien zuweisen.</span><span class="sxs-lookup"><span data-stu-id="f75dc-110">Application policies cannot be applied to these apps.</span></span>

<span data-ttu-id="f75dc-111">Einschränkungen seitens Apple verbieten die Auflistung von branchenspezifischen und verwalteten Apps aus dem App Store in der Unternehmensportal-App.</span><span class="sxs-lookup"><span data-stu-id="f75dc-111">Apple restrictions prohibit line-of-business and managed App Store apps from being listed in the Company Portal app.</span></span> <span data-ttu-id="f75dc-112">Um dieses Problem zu umgehen, verweisen die Kacheln in der Unternehmensportal-App für iOS die Benutzer für alle ihre Apps auf verschiedene Ansichten an einem einzigen Speicherort (der Unternehmensportal-Website).</span><span class="sxs-lookup"><span data-stu-id="f75dc-112">To get around this issue, the tiles in the Company Portal app for iOS point users to different views in a single location (the Company Portal website) for all of their apps.</span></span>

<span data-ttu-id="f75dc-113">Registrierte Benutzer erhalten ihre Apps durch Berühren der folgenden Kacheln auf dem Bildschirm „Apps“ der Unternehmensportal-App:</span><span class="sxs-lookup"><span data-stu-id="f75dc-113">Enrolled users get their apps by tapping on the following tiles on the Apps screen of the Company Portal app:</span></span>

- <span data-ttu-id="f75dc-114">**Alle Apps** verweist auf eine Liste aller Apps auf der Registerkarte „ALLE“ der [Unternehmensportal-Website](https://portal.manage.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="f75dc-114">**All Apps** points to a list of all apps in the ALL tab of the [Company Portal website](https://portal.manage.microsoft.com).</span></span>

- <span data-ttu-id="f75dc-115">**Ausgewählte Apps** leitet Benutzer zur Registerkarte „EMPFOHLEN“ der Unternehmensportal-Website.</span><span class="sxs-lookup"><span data-stu-id="f75dc-115">**Featured Apps** take users to the FEATURED tab of the Company Portal website.</span></span>

- <span data-ttu-id="f75dc-116">**Kategorien** verweist auf die Registerkarte „KATEGORIEN“ der Unternehmensportal-Website.</span><span class="sxs-lookup"><span data-stu-id="f75dc-116">**Categories** points to the CATEGORIES tab of the Company Portal website.</span></span>


![Apps-Bildschirm des iOS-Unternehmensportals](./media/ios-cp-app-main-apps-screen.png)

<span data-ttu-id="f75dc-118">Informationen zum Hinzufügen von Apps und ihrer Platzierung auf diesen Kacheln finden Sie unter [Hinzufügen von Apps für registrierte Geräte zu Intune](/intune-classic/deploy-use/add-apps-for-mobile-devices-in-microsoft-intune.md).</span><span class="sxs-lookup"><span data-stu-id="f75dc-118">For information on how to add apps and put them in these tiles, see [Add apps for enrolled devices to Intune](/intune-classic/deploy-use/add-apps-for-mobile-devices-in-microsoft-intune.md).</span></span>

### <a name="see-also"></a><span data-ttu-id="f75dc-119">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f75dc-119">See also</span></span>
[<span data-ttu-id="f75dc-120">Wie Ihre Android-Benutzer Apps erhalten</span><span class="sxs-lookup"><span data-stu-id="f75dc-120">How your Android users get their apps</span></span>](end-user-apps-android.md)

[<span data-ttu-id="f75dc-121">Wie Ihre Windows-Benutzer Apps erhalten</span><span class="sxs-lookup"><span data-stu-id="f75dc-121">How your Windows users get their apps</span></span>](end-user-apps-windows.md)
