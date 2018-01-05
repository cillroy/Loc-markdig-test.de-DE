---
title: Bereitstellen von Apps
description: "In diesem Thema werden Grundlagen erläutert, die Sie kennen müssen, bevor Sie mit dem Bereitstellen von Apps mit Intune beginnen."
keywords: 
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 12/27/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: ad5ea85c-aa2e-4110-a184-172cd0b8f270
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 654f84c93e6ca41f902b36f62a184ea820dc4ba6
ms.sourcegitcommit: e37e916e2bf14f092d3a767bc90d68c181d739fb
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/03/2018
---
# <a name="deploy-apps-with-microsoft-intune"></a><span data-ttu-id="7d2cc-103">Bereitstellen von Apps mit Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="7d2cc-103">Deploy apps with Microsoft Intune</span></span>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="7d2cc-104">In diesem Thema werden einige Grundlagen erläutert, die Sie kennen müssen, bevor Sie mit dem Bereitstellen von Apps mit Microsoft Intune beginnen.</span><span class="sxs-lookup"><span data-stu-id="7d2cc-104">This topic explains some of the concepts you need to understand before you start deploying apps with Microsoft Intune.</span></span>


## <a name="app-deployment-actions"></a><span data-ttu-id="7d2cc-105">App-Bereitstellungsaktionen</span><span class="sxs-lookup"><span data-stu-id="7d2cc-105">App deployment actions</span></span>
<span data-ttu-id="7d2cc-106">Wenn Sie Apps bereitstellen, können Sie eine der folgenden Bereitstellungsaktionen auswählen:</span><span class="sxs-lookup"><span data-stu-id="7d2cc-106">When you deploy apps, you can choose from one of the following deployment actions:</span></span>

-   <span data-ttu-id="7d2cc-107">**Erforderliche Installation** – Die App wird auf dem Gerät installiert, ohne dass ein Benutzereingriff erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="7d2cc-107">**Required install** – The app is installed onto the device with no user intervention required.</span></span>

    > [!TIP]
    > <span data-ttu-id="7d2cc-108">Bei iOS-Geräten, die nicht betreut werden, und bei allen Android-Geräten muss der Benutzer das App-Angebot vor der Installation akzeptieren.</span><span class="sxs-lookup"><span data-stu-id="7d2cc-108">For iOS devices that are not in supervised mode, and for all Android devices, the user must accept the app offer before it is installed.</span></span>
    >
    >  <span data-ttu-id="7d2cc-109">Wenn ein Benutzer eine App deinstalliert, die Sie als erforderliche Installation bereitgestellt haben, installiert Intune diese App nach dem nächsten Inventurzyklus (in der Regel nach sieben Tagen) automatisch erneut.</span><span class="sxs-lookup"><span data-stu-id="7d2cc-109">If a user uninstalls an app that you deployed as a required install, Intune automatically reinstalls the app after the next inventory cycle, which typically occurs every seven days.</span></span>

-   <span data-ttu-id="7d2cc-110">**Verfügbare Installation** – Die App wird im Unternehmensportal angezeigt, und Benutzer können sie bei Bedarf installieren.</span><span class="sxs-lookup"><span data-stu-id="7d2cc-110">**Available install** – The app is displayed in the company portal, and users can install it on demand.</span></span>

-   <span data-ttu-id="7d2cc-111">**Deinstallieren** : Die App wird vom Gerät deinstalliert.</span><span class="sxs-lookup"><span data-stu-id="7d2cc-111">**Uninstall** – The app is uninstalled from the device.</span></span>

-   <span data-ttu-id="7d2cc-112">**Nicht verfügbar** – Die App wird nicht im Unternehmensportal angezeigt und wird auf keinem Gerät installiert.</span><span class="sxs-lookup"><span data-stu-id="7d2cc-112">**Not applicable** – The app is not displayed in the company portal and is not installed on any devices.</span></span>

#### <a name="understand-which-deployment-actions-are-available-for-each-installer-type"></a><span data-ttu-id="7d2cc-113">Verfügbare Bereitstellungsaktionen für die verschiedenen Installationsprogrammtypen</span><span class="sxs-lookup"><span data-stu-id="7d2cc-113">Understand which deployment actions are available for each installer type</span></span>

|<span data-ttu-id="7d2cc-114">Typ des Installationsprogramms</span><span class="sxs-lookup"><span data-stu-id="7d2cc-114">Installer type</span></span>|<span data-ttu-id="7d2cc-115">Erforderliche Installation</span><span class="sxs-lookup"><span data-stu-id="7d2cc-115">Required install</span></span>|<span data-ttu-id="7d2cc-116">Verfügbare Installation</span><span class="sxs-lookup"><span data-stu-id="7d2cc-116">Available install</span></span>|<span data-ttu-id="7d2cc-117">Deinstallieren</span><span class="sxs-lookup"><span data-stu-id="7d2cc-117">Uninstall</span></span>|<span data-ttu-id="7d2cc-118">Nicht verfügbar</span><span class="sxs-lookup"><span data-stu-id="7d2cc-118">Not applicable</span></span>|
|------------------|--------------------|---------------------|-------------|------------------|
|<span data-ttu-id="7d2cc-119">Windows-App-Paket (für eine Benutzergruppe bereitgestellt)</span><span class="sxs-lookup"><span data-stu-id="7d2cc-119">Windows app package (deployed to a user group)</span></span>|<span data-ttu-id="7d2cc-120">Ja </span><span class="sxs-lookup"><span data-stu-id="7d2cc-120">Yes</span></span>|<span data-ttu-id="7d2cc-121">Ja </span><span class="sxs-lookup"><span data-stu-id="7d2cc-121">Yes</span></span>|<span data-ttu-id="7d2cc-122">Ja </span><span class="sxs-lookup"><span data-stu-id="7d2cc-122">Yes</span></span>|<span data-ttu-id="7d2cc-123">Ja </span><span class="sxs-lookup"><span data-stu-id="7d2cc-123">Yes</span></span>|
|<span data-ttu-id="7d2cc-124">Windows-App-Paket (auf einer Gerätegruppe bereitgestellt)</span><span class="sxs-lookup"><span data-stu-id="7d2cc-124">Windows app package (deployed to a device group)</span></span>|<span data-ttu-id="7d2cc-125">Ja </span><span class="sxs-lookup"><span data-stu-id="7d2cc-125">Yes</span></span>|<span data-ttu-id="7d2cc-126">Nein</span><span class="sxs-lookup"><span data-stu-id="7d2cc-126">No</span></span>|<span data-ttu-id="7d2cc-127">Ja </span><span class="sxs-lookup"><span data-stu-id="7d2cc-127">Yes</span></span>|<span data-ttu-id="7d2cc-128">Ja </span><span class="sxs-lookup"><span data-stu-id="7d2cc-128">Yes</span></span>|
|<span data-ttu-id="7d2cc-129">App-Paket für mobile Geräte (für eine Benutzergruppe bereitgestellt)</span><span class="sxs-lookup"><span data-stu-id="7d2cc-129">App package for mobile devices (deployed to a user group)</span></span>|<span data-ttu-id="7d2cc-130">Ja </span><span class="sxs-lookup"><span data-stu-id="7d2cc-130">Yes</span></span>|<span data-ttu-id="7d2cc-131">Ja </span><span class="sxs-lookup"><span data-stu-id="7d2cc-131">Yes</span></span>|<span data-ttu-id="7d2cc-132">Ja </span><span class="sxs-lookup"><span data-stu-id="7d2cc-132">Yes</span></span>|<span data-ttu-id="7d2cc-133">Ja </span><span class="sxs-lookup"><span data-stu-id="7d2cc-133">Yes</span></span>|
|<span data-ttu-id="7d2cc-134">App-Paket für mobile Geräte (auf einer Gerätegruppe bereitgestellt)</span><span class="sxs-lookup"><span data-stu-id="7d2cc-134">App package for mobile devices (deployed to a device group)</span></span>|<span data-ttu-id="7d2cc-135">Ja </span><span class="sxs-lookup"><span data-stu-id="7d2cc-135">Yes</span></span>|<span data-ttu-id="7d2cc-136">Nein</span><span class="sxs-lookup"><span data-stu-id="7d2cc-136">No</span></span>|<span data-ttu-id="7d2cc-137">Ja </span><span class="sxs-lookup"><span data-stu-id="7d2cc-137">Yes</span></span>|<span data-ttu-id="7d2cc-138">Ja </span><span class="sxs-lookup"><span data-stu-id="7d2cc-138">Yes</span></span>|
|<span data-ttu-id="7d2cc-139">Windows Installer (für eine Benutzergruppe bereitgestellt)</span><span class="sxs-lookup"><span data-stu-id="7d2cc-139">Windows Installer (deployed to a user group)</span></span>|<span data-ttu-id="7d2cc-140">Nein</span><span class="sxs-lookup"><span data-stu-id="7d2cc-140">No</span></span>|<span data-ttu-id="7d2cc-141">Ja </span><span class="sxs-lookup"><span data-stu-id="7d2cc-141">Yes</span></span>|<span data-ttu-id="7d2cc-142">Nein</span><span class="sxs-lookup"><span data-stu-id="7d2cc-142">No</span></span>|<span data-ttu-id="7d2cc-143">Ja </span><span class="sxs-lookup"><span data-stu-id="7d2cc-143">Yes</span></span>|
|<span data-ttu-id="7d2cc-144">Windows Installer (auf einer Gerätegruppe bereitgestellt)</span><span class="sxs-lookup"><span data-stu-id="7d2cc-144">Windows Installer (deployed to a device group)</span></span>|<span data-ttu-id="7d2cc-145">Ja </span><span class="sxs-lookup"><span data-stu-id="7d2cc-145">Yes</span></span>|<span data-ttu-id="7d2cc-146">Nein</span><span class="sxs-lookup"><span data-stu-id="7d2cc-146">No</span></span>|<span data-ttu-id="7d2cc-147">Ja </span><span class="sxs-lookup"><span data-stu-id="7d2cc-147">Yes</span></span>|<span data-ttu-id="7d2cc-148">Ja </span><span class="sxs-lookup"><span data-stu-id="7d2cc-148">Yes</span></span>|
|<span data-ttu-id="7d2cc-149">Externer Link (für eine Benutzergruppe bereitgestellt)</span><span class="sxs-lookup"><span data-stu-id="7d2cc-149">External link (deployed to a user group)</span></span>|<span data-ttu-id="7d2cc-150">Nein</span><span class="sxs-lookup"><span data-stu-id="7d2cc-150">No</span></span>|<span data-ttu-id="7d2cc-151">Ja </span><span class="sxs-lookup"><span data-stu-id="7d2cc-151">Yes</span></span>|<span data-ttu-id="7d2cc-152">Nein</span><span class="sxs-lookup"><span data-stu-id="7d2cc-152">No</span></span>|<span data-ttu-id="7d2cc-153">Ja </span><span class="sxs-lookup"><span data-stu-id="7d2cc-153">Yes</span></span>|
|<span data-ttu-id="7d2cc-154">Externer Link (auf einer Gerätegruppe bereitgestellt)</span><span class="sxs-lookup"><span data-stu-id="7d2cc-154">External link (deployed to a device group)</span></span>|<span data-ttu-id="7d2cc-155">Nein</span><span class="sxs-lookup"><span data-stu-id="7d2cc-155">No</span></span>|<span data-ttu-id="7d2cc-156">Nein</span><span class="sxs-lookup"><span data-stu-id="7d2cc-156">No</span></span>|<span data-ttu-id="7d2cc-157">Nein</span><span class="sxs-lookup"><span data-stu-id="7d2cc-157">No</span></span>|<span data-ttu-id="7d2cc-158">Nein</span><span class="sxs-lookup"><span data-stu-id="7d2cc-158">No</span></span>|
|<span data-ttu-id="7d2cc-159">Verwaltete iOS-App aus dem App Store (für eine Benutzergruppe bereitgestellt)</span><span class="sxs-lookup"><span data-stu-id="7d2cc-159">Managed iOS app from the app store (deployed to a user group)</span></span>|<span data-ttu-id="7d2cc-160">Ja </span><span class="sxs-lookup"><span data-stu-id="7d2cc-160">Yes</span></span>|<span data-ttu-id="7d2cc-161">Ja </span><span class="sxs-lookup"><span data-stu-id="7d2cc-161">Yes</span></span>|<span data-ttu-id="7d2cc-162">Ja </span><span class="sxs-lookup"><span data-stu-id="7d2cc-162">Yes</span></span>|<span data-ttu-id="7d2cc-163">Ja </span><span class="sxs-lookup"><span data-stu-id="7d2cc-163">Yes</span></span>|
|<span data-ttu-id="7d2cc-164">Verwaltete iOS-App aus dem App Store (auf einer Gerätegruppe bereitgestellt)</span><span class="sxs-lookup"><span data-stu-id="7d2cc-164">Managed iOS app from the app store (deployed to a device group)</span></span>|<span data-ttu-id="7d2cc-165">Ja </span><span class="sxs-lookup"><span data-stu-id="7d2cc-165">Yes</span></span>|<span data-ttu-id="7d2cc-166">Nein</span><span class="sxs-lookup"><span data-stu-id="7d2cc-166">No</span></span>|<span data-ttu-id="7d2cc-167">Ja </span><span class="sxs-lookup"><span data-stu-id="7d2cc-167">Yes</span></span>|<span data-ttu-id="7d2cc-168">Ja </span><span class="sxs-lookup"><span data-stu-id="7d2cc-168">Yes</span></span>|

> [!TIP]
> <span data-ttu-id="7d2cc-169">Wenn Sie beim Bereitstellen von Apps sowohl Benutzer- als auch Gerätegruppen auswählen, können Sie die App nur als **verfügbare Installation** bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="7d2cc-169">When you deploy apps, if you select both user and device groups, you can only deploy the app as an **Available install**.</span></span>

## <a name="deployment-conflicts"></a><span data-ttu-id="7d2cc-170">Bereitstellungskonflikte</span><span class="sxs-lookup"><span data-stu-id="7d2cc-170">Deployment conflicts</span></span>
<span data-ttu-id="7d2cc-171">Wenn zwei Bereitstellungen mit der gleichen Bereitstellungsaktion von einem Gerät empfangen werden, gelten die folgenden Regeln:</span><span class="sxs-lookup"><span data-stu-id="7d2cc-171">When two deployments with the same deployment action are received by a device, the following rules apply:</span></span>

-   <span data-ttu-id="7d2cc-172">Bereitstellungen auf einer Gerätegruppe haben Vorrang vor Bereitstellung für eine Benutzergruppe.</span><span class="sxs-lookup"><span data-stu-id="7d2cc-172">Deployments to a device group take precedence over deployments to a user group.</span></span> <span data-ttu-id="7d2cc-173">Wenn jedoch eine App für eine Benutzergruppe mit der Bereitstellungsaktion **Verfügbar** bereitgestellt wird und dieselbe App auf einer Gerätegruppe mit der Bereitstellungsaktion **Nicht verfügbar** bereitgestellt wird, wird die App im Unternehmensportal Benutzern zur Installation zur Verfügung gestellt.</span><span class="sxs-lookup"><span data-stu-id="7d2cc-173">However, if an app is deployed to a user group with a deployment action of **Available**, and the same app is also deployed to a device group with a deployment action of **Not Applicable**, the app will be made available in the company portal for users to install.</span></span>

-   <span data-ttu-id="7d2cc-174">Eine Installationsaktion hat Vorrang vor einer Deinstallationsaktion.</span><span class="sxs-lookup"><span data-stu-id="7d2cc-174">An install action takes precedence over an uninstall action.</span></span>

-   <span data-ttu-id="7d2cc-175">Wenn eine erforderliche Installation und eine verfügbare Installation von einem Gerät empfangen werden, werden die Aktionen zusammengefasst.</span><span class="sxs-lookup"><span data-stu-id="7d2cc-175">If both a required and an available install are received by a device, the actions are combined.</span></span> <span data-ttu-id="7d2cc-176">Das bedeutet, dass der Benutzer die App aus dem Unternehmensportal installieren kann, bevor die erforderliche Installation beginnt.</span><span class="sxs-lookup"><span data-stu-id="7d2cc-176">In other words, the user can install the available app from the company portal before the required install begins.</span></span>


## <a name="next-steps"></a><span data-ttu-id="7d2cc-177">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="7d2cc-177">Next steps</span></span>

<span data-ttu-id="7d2cc-178">Erfahren Sie mehr zum [Bereitstellen von Apps in Microsoft Intune](deploy-apps-in-microsoft-intune.md).</span><span class="sxs-lookup"><span data-stu-id="7d2cc-178">Learn how to [deploy apps in Microsoft Intune](deploy-apps-in-microsoft-intune.md).</span></span>
