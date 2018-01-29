---
title: "Hinzufügen von Web-Apps in Intune"
titleSuffix: Azure portal
description: "Erfahren Sie mehr über das Hinzufügen von Web-Apps in Intune.\""
keywords: 
author: mattbriggs
ms.author: erikre
manager: angrobe
ms.date: 12/06/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5f08752f-0e87-4ad9-a34c-4991b3150775
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: ebe4b31c85e0c0bc88f49d28e28ea7eac191951f
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2018
---
# <a name="how-to-add-web-apps-to-microsoft-intune"></a><span data-ttu-id="af68d-103">Hinzufügen von Web-Apps in Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="af68d-103">How to add web apps to Microsoft Intune</span></span>

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="af68d-104">Vor dem Zuweisen einer app für Ihre Benutzer und verwalten können, müssen Sie die app zu Intune hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="af68d-104">Before you can manage and assign an app for your users, you must add the app to Intune.</span></span> <span data-ttu-id="af68d-105">Intune unterstützt eine Vielzahl von App-Typen, einschließlich Web-Apps.</span><span class="sxs-lookup"><span data-stu-id="af68d-105">Intune supports a variety of app types including web apps.</span></span>

> [!Note]
> <span data-ttu-id="af68d-106">Web-Apps werden nicht für Android for Work-Geräte unterstützt.</span><span class="sxs-lookup"><span data-stu-id="af68d-106">Web apps are not supported on Android for Work devices.</span></span>

<span data-ttu-id="af68d-107">Das folgende Verfahren können Sie eine app als eine Verknüpfung zu einer app im Web zu Intune hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="af68d-107">The following procedure will allow you to add an app to Intune as a shortcut to an app on the web:</span></span>

1. <span data-ttu-id="af68d-108">Melden Sie sich beim Azure-Portal an.</span><span class="sxs-lookup"><span data-stu-id="af68d-108">Sign into the Azure portal.</span></span>
2. <span data-ttu-id="af68d-109">Suchen Sie über **Mehr Ressourcen** nach **Intune**, und wählen Sie die App aus.</span><span class="sxs-lookup"><span data-stu-id="af68d-109">Using **More resources**, search for and select **Intune**.</span></span>
3. <span data-ttu-id="af68d-110">Wählen Sie auf dem Blatt **Microsoft Intune** die Option **Mobile Apps** aus.</span><span class="sxs-lookup"><span data-stu-id="af68d-110">On the **Microsoft Intune** blade, select **Mobile apps**.</span></span>
4. <span data-ttu-id="af68d-111">Wählen Sie auf dem Blatt **Mobile Apps** die Option **Apps** aus.</span><span class="sxs-lookup"><span data-stu-id="af68d-111">On the **Mobile apps** blade, select **Apps**.</span></span>
5. <span data-ttu-id="af68d-112">Wählen Sie oberhalb der App-Liste **Hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="af68d-112">Above the list of apps, select **Add**.</span></span> <span data-ttu-id="af68d-113">Die **Add app** Blatt wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="af68d-113">The **Add app** blade will be displayed.</span></span>
6. <span data-ttu-id="af68d-114">Wählen Sie auf dem Blatt **App hinzufügen** den Typ **Web-App** aus der Dropdownliste **App-Typ** aus.</span><span class="sxs-lookup"><span data-stu-id="af68d-114">In the **Add app** blade, select the **Web app** type from the **App type** drop-down list.</span></span>
7. <span data-ttu-id="af68d-115">Wählen Sie auf dem Blatt **App-Informationen** die Option **Konfigurieren** aus.</span><span class="sxs-lookup"><span data-stu-id="af68d-115">Select the **Configure** option to display the **App information** blade.</span></span>
8. <span data-ttu-id="af68d-116">Fügen Sie auf dem Blatt **App-Informationen** die folgenden Informationen hinzu:</span><span class="sxs-lookup"><span data-stu-id="af68d-116">In the **App information** blade, add the following information:</span></span>
    - <span data-ttu-id="af68d-117">**Name:** Geben Sie den Namen der App ein, wie er im Unternehmensportal angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="af68d-117">**Name** - Enter the name of the app as it will be displayed in the company portal.</span></span>
    - <span data-ttu-id="af68d-118">**Beschreibung:** Geben Sie eine Beschreibung für die App ein.</span><span class="sxs-lookup"><span data-stu-id="af68d-118">**Description** - Enter a description for the app.</span></span> <span data-ttu-id="af68d-119">Diese Beschreibung wird den Endbenutzern im Unternehmensportal angezeigt.</span><span class="sxs-lookup"><span data-stu-id="af68d-119">This will be displayed to end users in the company portal.</span></span>
    - <span data-ttu-id="af68d-120">**Herausgeber:** Geben Sie den Namen des Herausgebers dieser App ein.</span><span class="sxs-lookup"><span data-stu-id="af68d-120">**Publisher** - Enter the name of the publisher of this app.</span></span>
    - <span data-ttu-id="af68d-121">**App-URL:** Geben Sie die URL der Website an, auf der die zuzuweisende App gehostet wird.</span><span class="sxs-lookup"><span data-stu-id="af68d-121">**App URL** - Enter the URL of the web site that hosts the app you want to assign.</span></span>
    - <span data-ttu-id="af68d-122">**Kategorie (optional):** Wählen Sie eine der integrierten oder von Ihnen erstellten App-Kategorien aus.</span><span class="sxs-lookup"><span data-stu-id="af68d-122">**Category (optional)** - Select one or more of the built-in app categories, or a category you created.</span></span> <span data-ttu-id="af68d-123">Dadurch wird es für die Benutzer leichter, die App im Unternehmensportal zu finden.</span><span class="sxs-lookup"><span data-stu-id="af68d-123">This will make it easier for users to find the app when they browse the company portal.</span></span>
    - <span data-ttu-id="af68d-124">**Diese App als ausgewählte App im Unternehmensportal anzeigen:** Zeigen Sie die App auf der Hauptseite des Unternehmensportal hervorgehoben an, wenn Benutzer nach Apps suchen.</span><span class="sxs-lookup"><span data-stu-id="af68d-124">**Display this as a featured app in the Company Portal** - Display the app prominently on the main page of the company portal when users browse for apps.</span></span>
    - <span data-ttu-id="af68d-125">**Managed Browser zum Öffnen dieses Links anfordern:** Wenn Sie Benutzern einen Link zu einer Website oder Web-App zuweisen, können sie diesen nur im Intune Managed Browser öffnen.</span><span class="sxs-lookup"><span data-stu-id="af68d-125">**Require a managed browser to open this link** - When you assign a link to a website or web app to users, they will be able to open it only in the Intune managed browser.</span></span> <span data-ttu-id="af68d-126">Dieser Browser muss auf ihrem Gerät installiert sein.</span><span class="sxs-lookup"><span data-stu-id="af68d-126">This browser must be installed on their device.</span></span>
    - <span data-ttu-id="af68d-127">**Logo** -Hochladen ein Logo, das der app zugeordnet werden soll.</span><span class="sxs-lookup"><span data-stu-id="af68d-127">**Logo** - Upload an logo that will be associated with the app.</span></span> <span data-ttu-id="af68d-128">Dies ist das Logo, das mit der app angezeigt wird, wenn der Benutzer das Unternehmensportal durchsuchen.</span><span class="sxs-lookup"><span data-stu-id="af68d-128">This is the logo that will be displayed with the app when users browse the company portal.</span></span>
9. <span data-ttu-id="af68d-129">Wählen Sie dann auf dem Blatt **Informationen hinzufügen** die Option **OK** aus.</span><span class="sxs-lookup"><span data-stu-id="af68d-129">When you are done, on the **Add information** blade, select **Ok**.</span></span>
10. <span data-ttu-id="af68d-130">Wählen Sie anschließend **Hinzufügen** auf dem Blatt **App hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="af68d-130">Then, from the **Add app** blade, select **Add**.</span></span>

<span data-ttu-id="af68d-131">Die von Ihnen erstellte App wird in der Liste der Apps angezeigt, in der Sie sie ausgewählten Gruppen zuweisen können.</span><span class="sxs-lookup"><span data-stu-id="af68d-131">The app you have created will be displayed in the apps list where you can assign it to the groups you choose.</span></span> <span data-ttu-id="af68d-132">Hilfe finden Sie unter [Zuweisen von Apps zu Gruppen](apps-deploy.md).</span><span class="sxs-lookup"><span data-stu-id="af68d-132">For help, see [How to assign apps to groups](apps-deploy.md).</span></span>