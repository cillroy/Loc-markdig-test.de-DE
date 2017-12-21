---
title: Erste Schritte mit Apps
titlesuffix: Azure portal
description: "Suchen Sie Apps, und fügen Sie sie auf Geräten hinzu, um Ihren Mitarbeitern die Arbeit zu erleichtern."
keywords: 
author: erikre
ms.author: erikre
manager: angrobe
ms.date: 12/06/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a1542fc3-672e-47c1-a21f-82826a2f8ac4
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 89f3585b97bd1a074b45af815792ec4949215aab
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2017
---
# <a name="get-started-with-adding-apps"></a><span data-ttu-id="46349-103">Erste Schritte mit dem Hinzufügen von Apps</span><span class="sxs-lookup"><span data-stu-id="46349-103">Get started with adding apps</span></span>

<span data-ttu-id="46349-104">Intune unterstützt einige unterschiedliche Bereitstellungsmethoden für Apps auf Ihren Unternehmensgeräten:</span><span class="sxs-lookup"><span data-stu-id="46349-104">Intune supports a few different ways for you to deploy apps to your corporate devices:</span></span>

* <span data-ttu-id="46349-105">**Softwareinstallationsprogramme**: Hochladen einer heruntergeladenen Datei auf das Gerät Ihres Benutzers</span><span class="sxs-lookup"><span data-stu-id="46349-105">**Software installers**: where you upload a file that is downloaded to your users' devices</span></span>
* <span data-ttu-id="46349-106">__Externe Links__: für eine App in einem öffentlichen App-Store oder eine Web-App</span><span class="sxs-lookup"><span data-stu-id="46349-106">__External links__: for when you have an app in a public app store or a webapp</span></span>
* <span data-ttu-id="46349-107">**Verwaltete Apps**: für iOS-Geräte, für die zusätzliche mobile Anwendungsverwaltung für im App-Store verfügbare Apps erforderlich ist</span><span class="sxs-lookup"><span data-stu-id="46349-107">**Managed apps**: for iOS devices where you need additional mobile application management applied to apps available in the App Store</span></span>

<span data-ttu-id="46349-108">Eine der schnelleren Bereitstellungsmethoden für Apps ist das Zuweisen einer öffentlichen Store-App.</span><span class="sxs-lookup"><span data-stu-id="46349-108">You’re going to go through one of the quicker application deployment methods by assigning a public store app.</span></span>

## <a name="how-do-i-assign-a-public-store-app"></a><span data-ttu-id="46349-109">Wie weise ich eine öffentliche Store-App zu?</span><span class="sxs-lookup"><span data-stu-id="46349-109">How do I assign a public store app?</span></span>

1. <span data-ttu-id="46349-110">Melden Sie sich beim [Azure-Portal](https://portal.azure.com) an.</span><span class="sxs-lookup"><span data-stu-id="46349-110">Sign in to the [Azure portal](https://portal.azure.com).</span></span>
2. <span data-ttu-id="46349-111">Suchen Sie über **Ressourcen durchsuchen** nach **Intune**.</span><span class="sxs-lookup"><span data-stu-id="46349-111">Using **Search resources**, search for **Intune**.</span></span>
3. <span data-ttu-id="46349-112">Klicken Sie auf **Mobile Apps** und dann auf **Apps**.</span><span class="sxs-lookup"><span data-stu-id="46349-112">Select **Mobile Apps**, then select **Apps**.</span></span>
4. <span data-ttu-id="46349-113">Klicken Sie auf **Hinzufügen**, und wählen Sie unter **Store-App** dann **iOS** als **App-Typ** aus.</span><span class="sxs-lookup"><span data-stu-id="46349-113">Select **Add**, then select **iOS** under **Store app** as the **App type**.</span></span>
5. <span data-ttu-id="46349-114">Wählen Sie **App auswählen**, um das Blatt **App Store durchsuchen** anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="46349-114">Choose **Select app** to display the **Search the App Store** blade.</span></span>
6. <span data-ttu-id="46349-115">Suchen Sie über das Textfeld nach einer App, die Sie dem Gerät zuweisen können.</span><span class="sxs-lookup"><span data-stu-id="46349-115">In the text box, search for an app to assign to the device.</span></span> <span data-ttu-id="46349-116">Wählen Sie die App aus, und klicken Sie dann auf **Auswählen**.</span><span class="sxs-lookup"><span data-stu-id="46349-116">Choose the app, then click **Select**.</span></span>
7. <span data-ttu-id="46349-117">Klicken Sie auf dem Blatt **App hinzufügen** auf **App-Information**, und stellen Sie dann sicher, dass alle App-Informationen ausgefüllt wurden.</span><span class="sxs-lookup"><span data-stu-id="46349-117">In the **Add app** blade, select **App information**, then make sure that all of the app information populated.</span></span> <span data-ttu-id="46349-118">Sie können andere optionale Details hinzufügen, um diese App zu organisieren, wie z.B. **Besitzer**, **Anmerkungen**, **Entwickler** und **URL zu den Datenschutzbestimmungen** für die Datenschutzrichtlinie Ihres Unternehmens.</span><span class="sxs-lookup"><span data-stu-id="46349-118">You can add other optional details to help you organize this app, like **Owner**, **Notes**, **Developer**, and a **Privacy URL** for your company’s privacy policy.</span></span>
8. <span data-ttu-id="46349-119">Achten Sie darauf, dass Sie **Ja** für **Diese App als ausgewählte App im Unternehmensportal anzeigen** ausgewählt haben, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="46349-119">Make sure that you’ve selected **Yes** for **Display this as a featured app in the Company Portal**, then select **OK**.</span></span>
9. <span data-ttu-id="46349-120">Wählen Sie **Hinzufügen** auf dem Blatt **App hinzufügen** aus, um die App hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="46349-120">Select **Add** from the **Add app** blade to add the app.</span></span> <span data-ttu-id="46349-121">Dann werden Sie zur **Übersicht** der App weitergeleitet.</span><span class="sxs-lookup"><span data-stu-id="46349-121">This will take you to that app’s **Overview**.</span></span> <span data-ttu-id="46349-122">Klicken Sie auf **Zuweisungen** und dann auf **Gruppe auswählen**, um sie Ihrer Testgruppe hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="46349-122">Choose **Assignments**, then click **Select groups** to assign it to your test group.</span></span> <span data-ttu-id="46349-123">Machen Sie die App zum Herunterladen **verfügbar**.</span><span class="sxs-lookup"><span data-stu-id="46349-123">Make the app **Available** for download.</span></span> <span data-ttu-id="46349-124">Dann sollte die App als **Empfohlene App** auf Ihrem Testgerät angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="46349-124">The app should then appear as a **Featured App** on your test device.</span></span>

## <a name="learn-more"></a><span data-ttu-id="46349-125">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="46349-125">Learn more</span></span>

* [<span data-ttu-id="46349-126">Was ist die Microsoft Intune App-Verwaltung?</span><span class="sxs-lookup"><span data-stu-id="46349-126">What is app management with Intune?</span></span>](app-management.md)
* [<span data-ttu-id="46349-127">Übersicht über den App-Lebenszyklus</span><span class="sxs-lookup"><span data-stu-id="46349-127">Overview of the app lifecycle</span></span>](app-lifecycle.md)
* [<span data-ttu-id="46349-128">Was sind App-Schutzrichtlinien?</span><span class="sxs-lookup"><span data-stu-id="46349-128">What are app protection policies?</span></span>](app-protection-policy.md)
