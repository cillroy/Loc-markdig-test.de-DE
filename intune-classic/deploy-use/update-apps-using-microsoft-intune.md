---
title: Aktualisierung von Apps
description: Verwenden Sie die Informationen in diesem Thema, um zu erfahren, wie Sie Apps aktualisieren, wenn eine neue Version erforderlich ist.
keywords: 
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 12/27/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: beee6933-876a-4be0-b395-4c24cfbd519b
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: b8495c50a040e6c6a7fe7777b9e415333088b5ac
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2018
---
# <a name="update-apps-using-microsoft-intune"></a><span data-ttu-id="825c5-103">Aktualisieren von Apps mit </span><span class="sxs-lookup"><span data-stu-id="825c5-103">Update apps using Microsoft Intune</span></span>

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="825c5-104">Microsoft Intune unterstützt Sie bei der Verwaltung von App-Updates.</span><span class="sxs-lookup"><span data-stu-id="825c5-104">Microsoft Intune can help you manage app updates.</span></span> <span data-ttu-id="825c5-105">Verwenden Sie die Informationen in diesem Thema, um zu erfahren, wie Sie Apps aktualisieren, wenn eine neue Version erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="825c5-105">Use the information in this topic to understand how to update apps when a new version is required.</span></span>

## <a name="how-to-update-apps"></a><span data-ttu-id="825c5-106">Aktualisieren von Apps</span><span class="sxs-lookup"><span data-stu-id="825c5-106">How to update apps</span></span>
<span data-ttu-id="825c5-107">Wenn eine neue Version einer von Ihnen bereitgestellten App veröffentlicht wird, können Sie mit Intune die neuere Version der App aktualisieren und bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="825c5-107">When a new version of an app that you've deployed is released, Intune lets you update and deploy the newer version of the app.</span></span> <span data-ttu-id="825c5-108">Sie können eine Bereitstellung nur durch eine neuere Version der gleichen App (mit derselben ID) ersetzen.</span><span class="sxs-lookup"><span data-stu-id="825c5-108">You can only replace a deployment with a newer version of the same app (that has the same identifier).</span></span> <span data-ttu-id="825c5-109">App-Updates können nicht zum Aktualisieren einer Bereitstellung mit einem anderen App-Paket verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="825c5-109">You cannot use app updates to update a deployment with a different app package.</span></span>

### <a name="app-identifiers"></a><span data-ttu-id="825c5-110">App-Bezeichner</span><span class="sxs-lookup"><span data-stu-id="825c5-110">App identifiers</span></span>
<span data-ttu-id="825c5-111">Der App-Bezeichner ist eine Eigenschaft, die eine App eindeutig identifiziert.</span><span class="sxs-lookup"><span data-stu-id="825c5-111">The app identifier is a property that uniquely identifies an app.</span></span> <span data-ttu-id="825c5-112">Sie können nicht mehrere Kopien einer App mit dem gleichen Bezeichner installieren.</span><span class="sxs-lookup"><span data-stu-id="825c5-112">You cannot install multiple copies of an app with the same identifier.</span></span> <span data-ttu-id="825c5-113">Im Folgenden sind einige Beispiele für App-IDs aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="825c5-113">Following are some examples of app identifiers:</span></span>

- <span data-ttu-id="825c5-114">**iOS** – Paket-ID (z. B. com.microsoft.excel)</span><span class="sxs-lookup"><span data-stu-id="825c5-114">**iOS** - Bundle ID (for example: com.microsoft.excel)</span></span>
- <span data-ttu-id="825c5-115">**Android** – Paket-ID (z. B. com.microsoft.excel)</span><span class="sxs-lookup"><span data-stu-id="825c5-115">**Android** - Package ID (for example: com.microsoft.excel)</span></span>
- <span data-ttu-id="825c5-116">**Windows Phone-** – (XAP-Installer) mit Produkt-ID (GUID)</span><span class="sxs-lookup"><span data-stu-id="825c5-116">**Windows Phone** - (xap installer) use Product ID (GUID)</span></span>
- <span data-ttu-id="825c5-117">**Windows** – (Appx/Appxbundle), verwenden Sie den vollständigen Paketnamen</span><span class="sxs-lookup"><span data-stu-id="825c5-117">**Windows** - (appx/appxbundle), use the Package Full Name</span></span>



> [!IMPORTANT]
> <span data-ttu-id="825c5-118">Beim Bereitstellen einer App mit der Bereitstellungsaktion **Erforderliche Installation** und einer späteren Änderung der Bereitstellungsaktion in **Verfügbare Installation**werden Updates für die App auf Geräten, auf denen die App vor der Bereitstellungsänderung installiert war, nicht automatisch installiert.</span><span class="sxs-lookup"><span data-stu-id="825c5-118">When you deploy an app with a deployment action of **Required install** and later change the deployment action to **Available install**, updates to the app are not automatically installed on devices that installed the app before the deployment change was made.</span></span> <span data-ttu-id="825c5-119">Gehen Sie wie folgt vor, um dieses Problem zu beheben:</span><span class="sxs-lookup"><span data-stu-id="825c5-119">To fix this issue, you can do the following:</span></span>
>
> -   <span data-ttu-id="825c5-120">Bitten Sie den Benutzer des Geräts, das Unternehmensportal zu öffnen, die installierte App auszuwählen und **Installieren** auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="825c5-120">Have the user of the device go to the company portal, select the installed app, and then choose **Install**.</span></span>
> -   <span data-ttu-id="825c5-121">Ändern Sie die Bereitstellungsaktion in **Deinstallieren**, und stellen Sie die App nach der Deinstallation der App erneut mit der Bereitstellungsaktion **Verfügbare Installation**bereit.</span><span class="sxs-lookup"><span data-stu-id="825c5-121">Change the deployment action to **Uninstall**, and after the app has been uninstalled, redeploy the app with a deployment action of **Available install**.</span></span>

### <a name="to-update-an-app"></a><span data-ttu-id="825c5-122">So aktualisieren Sie eine App</span><span class="sxs-lookup"><span data-stu-id="825c5-122">To update an app</span></span>

1.  <span data-ttu-id="825c5-123">Wählen Sie in der [Microsoft Intune-Verwaltungskonsole](https://manage.microsoft.com) **Apps** &gt; **Apps** aus.</span><span class="sxs-lookup"><span data-stu-id="825c5-123">In the [Microsoft Intune administration console](https://manage.microsoft.com), choose **Apps** &gt; **Apps**.</span></span>

2.  <span data-ttu-id="825c5-124">Wählen Sie in der Liste **Apps** die zu aktualisierende App und anschließend **Bearbeiten** aus.</span><span class="sxs-lookup"><span data-stu-id="825c5-124">From the **Apps** list, select the app you want to update, and then choose **Edit**.</span></span>

3.  <span data-ttu-id="825c5-125">Geben Sie im Assistenten **Software bearbeiten** neue Details für das App-Paket ein.</span><span class="sxs-lookup"><span data-stu-id="825c5-125">In the **Edit Software** wizard, supply any new details for the app package.</span></span>

4.  <span data-ttu-id="825c5-126">Wählen Sie anschließend **Aktualisieren** aus.</span><span class="sxs-lookup"><span data-stu-id="825c5-126">When you are finished, choose **Update**.</span></span>

<span data-ttu-id="825c5-127">Wenn Geräte das nächste Mal prüfen, ob Apps verfügbar sind, wird die App automatisch auf die neueste Version aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="825c5-127">When devices next check for available apps, the app will be automatically updated to the latest version.</span></span>
<span data-ttu-id="825c5-128">Bei Apps, die aus einem App-Paket installiert wurden (branchenspezifische Apps), erfolgt das Upgrade für erforderliche sowie verfügbare Bereitstellungen automatisch, solange die App über denselben Bezeichner verfügt.</span><span class="sxs-lookup"><span data-stu-id="825c5-128">For apps installed from an app package (line of business apps), the app will be upgraded automatically for both required and available deployments, as long as the app has the same identifier.</span></span>

<span data-ttu-id="825c5-129">Bei Apps, die als Link zu einem Store bereitgestellt wurden, wird das Update von dem Store verwaltet, aus dem die App stammt.</span><span class="sxs-lookup"><span data-stu-id="825c5-129">For apps deployed as a link to a store, the update is managed by the store from which the app originates.</span></span>
