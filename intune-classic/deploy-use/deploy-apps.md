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
ms.openlocfilehash: eaea92f2cd2208086a544a192d620e1cdd96cfc2
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2017
---
# <a name="deploy-apps-with-microsoft-intune"></a><span data-ttu-id="6bd04-103">Bereitstellen von Apps mit Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="6bd04-103">Deploy apps with Microsoft Intune</span></span>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="6bd04-104">In diesem Thema werden einige Grundlagen erläutert, die Sie kennen müssen, bevor Sie mit dem Bereitstellen von Apps mit Microsoft Intune beginnen.</span><span class="sxs-lookup"><span data-stu-id="6bd04-104">This topic explains some of the concepts you need to understand before you start deploying apps with Microsoft Intune.</span></span>


## <a name="app-deployment-actions"></a><span data-ttu-id="6bd04-105">App-Bereitstellungsaktionen</span><span class="sxs-lookup"><span data-stu-id="6bd04-105">App deployment actions</span></span>
<span data-ttu-id="6bd04-106">Wenn Sie Apps bereitstellen, können Sie eine der folgenden Bereitstellungsaktionen auswählen:</span><span class="sxs-lookup"><span data-stu-id="6bd04-106">When you deploy apps, you can choose from one of the following deployment actions:</span></span>

-   <span data-ttu-id="6bd04-107">**Erforderliche Installation** – Die App wird auf dem Gerät installiert, ohne dass ein Benutzereingriff erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="6bd04-107">**Required install** – The app is installed onto the device with no user intervention required.</span></span>

    > [!TIP]
    > <span data-ttu-id="6bd04-108">Bei iOS-Geräten, die nicht betreut werden, und bei allen Android-Geräten muss der Benutzer das App-Angebot vor der Installation akzeptieren.</span><span class="sxs-lookup"><span data-stu-id="6bd04-108">For iOS devices that are not in supervised mode, and for all Android devices, the user must accept the app offer before it is installed.</span></span>
    >
    >  <span data-ttu-id="6bd04-109">Wenn ein Benutzer eine App deinstalliert, die Sie als erforderliche Installation bereitgestellt haben, installiert Intune diese App nach dem nächsten Inventurzyklus (in der Regel nach sieben Tagen) automatisch erneut.</span><span class="sxs-lookup"><span data-stu-id="6bd04-109">If a user uninstalls an app that you deployed as a required install, Intune automatically reinstalls the app after the next inventory cycle, which typically occurs every seven days.</span></span>

-   <span data-ttu-id="6bd04-110">**Verfügbare Installation** – Die App wird im Unternehmensportal angezeigt, und Benutzer können sie bei Bedarf installieren.</span><span class="sxs-lookup"><span data-stu-id="6bd04-110">**Available install** – The app is displayed in the company portal, and users can install it on demand.</span></span>

-   <span data-ttu-id="6bd04-111">**Deinstallieren** : Die App wird vom Gerät deinstalliert.</span><span class="sxs-lookup"><span data-stu-id="6bd04-111">**Uninstall** – The app is uninstalled from the device.</span></span>

-   <span data-ttu-id="6bd04-112">**Nicht verfügbar** – Die App wird nicht im Unternehmensportal angezeigt und wird auf keinem Gerät installiert.</span><span class="sxs-lookup"><span data-stu-id="6bd04-112">**Not applicable** – The app is not displayed in the company portal and is not installed on any devices.</span></span>

#### <a name="understand-which-deployment-actions-are-available-for-each-installer-type"></a><span data-ttu-id="6bd04-113">Verfügbare Bereitstellungsaktionen für die verschiedenen Installationsprogrammtypen</span><span class="sxs-lookup"><span data-stu-id="6bd04-113">Understand which deployment actions are available for each installer type</span></span>

|<span data-ttu-id="6bd04-114">Typ des Installationsprogramms</span><span class="sxs-lookup"><span data-stu-id="6bd04-114">Installer type</span></span>|<span data-ttu-id="6bd04-115">Erforderliche Installation</span><span class="sxs-lookup"><span data-stu-id="6bd04-115">Required install</span></span>|<span data-ttu-id="6bd04-116">Verfügbare Installation</span><span class="sxs-lookup"><span data-stu-id="6bd04-116">Available install</span></span>|<span data-ttu-id="6bd04-117">Deinstallieren</span><span class="sxs-lookup"><span data-stu-id="6bd04-117">Uninstall</span></span>|<span data-ttu-id="6bd04-118">Nicht verfügbar</span><span class="sxs-lookup"><span data-stu-id="6bd04-118">Not applicable</span></span>|
|------------------|--------------------|---------------------|-------------|------------------|
|<span data-ttu-id="6bd04-119">Windows-App-Paket (für eine Benutzergruppe bereitgestellt)</span><span class="sxs-lookup"><span data-stu-id="6bd04-119">Windows app package (deployed to a user group)</span></span>|<span data-ttu-id="6bd04-120">Ja</span><span class="sxs-lookup"><span data-stu-id="6bd04-120">Yes</span></span>|<span data-ttu-id="6bd04-121">Ja</span><span class="sxs-lookup"><span data-stu-id="6bd04-121">Yes</span></span>|<span data-ttu-id="6bd04-122">Ja</span><span class="sxs-lookup"><span data-stu-id="6bd04-122">Yes</span></span>|<span data-ttu-id="6bd04-123">Ja</span><span class="sxs-lookup"><span data-stu-id="6bd04-123">Yes</span></span>|
|<span data-ttu-id="6bd04-124">Windows-App-Paket (auf einer Gerätegruppe bereitgestellt)</span><span class="sxs-lookup"><span data-stu-id="6bd04-124">Windows app package (deployed to a device group)</span></span>|<span data-ttu-id="6bd04-125">Ja</span><span class="sxs-lookup"><span data-stu-id="6bd04-125">Yes</span></span>|<span data-ttu-id="6bd04-126">Nein</span><span class="sxs-lookup"><span data-stu-id="6bd04-126">No</span></span>|<span data-ttu-id="6bd04-127">Ja</span><span class="sxs-lookup"><span data-stu-id="6bd04-127">Yes</span></span>|<span data-ttu-id="6bd04-128">Ja</span><span class="sxs-lookup"><span data-stu-id="6bd04-128">Yes</span></span>|
|<span data-ttu-id="6bd04-129">App-Paket für mobile Geräte (für eine Benutzergruppe bereitgestellt)</span><span class="sxs-lookup"><span data-stu-id="6bd04-129">App package for mobile devices (deployed to a user group)</span></span>|<span data-ttu-id="6bd04-130">Ja</span><span class="sxs-lookup"><span data-stu-id="6bd04-130">Yes</span></span>|<span data-ttu-id="6bd04-131">Ja</span><span class="sxs-lookup"><span data-stu-id="6bd04-131">Yes</span></span>|<span data-ttu-id="6bd04-132">Ja</span><span class="sxs-lookup"><span data-stu-id="6bd04-132">Yes</span></span>|<span data-ttu-id="6bd04-133">Ja</span><span class="sxs-lookup"><span data-stu-id="6bd04-133">Yes</span></span>|
|<span data-ttu-id="6bd04-134">App-Paket für mobile Geräte (auf einer Gerätegruppe bereitgestellt)</span><span class="sxs-lookup"><span data-stu-id="6bd04-134">App package for mobile devices (deployed to a device group)</span></span>|<span data-ttu-id="6bd04-135">Ja</span><span class="sxs-lookup"><span data-stu-id="6bd04-135">Yes</span></span>|<span data-ttu-id="6bd04-136">Nein</span><span class="sxs-lookup"><span data-stu-id="6bd04-136">No</span></span>|<span data-ttu-id="6bd04-137">Ja</span><span class="sxs-lookup"><span data-stu-id="6bd04-137">Yes</span></span>|<span data-ttu-id="6bd04-138">Ja</span><span class="sxs-lookup"><span data-stu-id="6bd04-138">Yes</span></span>|
|<span data-ttu-id="6bd04-139">Windows Installer (für eine Benutzergruppe bereitgestellt)</span><span class="sxs-lookup"><span data-stu-id="6bd04-139">Windows Installer (deployed to a user group)</span></span>|<span data-ttu-id="6bd04-140">Nein</span><span class="sxs-lookup"><span data-stu-id="6bd04-140">No</span></span>|<span data-ttu-id="6bd04-141">Ja</span><span class="sxs-lookup"><span data-stu-id="6bd04-141">Yes</span></span>|<span data-ttu-id="6bd04-142">Nein</span><span class="sxs-lookup"><span data-stu-id="6bd04-142">No</span></span>|<span data-ttu-id="6bd04-143">Ja</span><span class="sxs-lookup"><span data-stu-id="6bd04-143">Yes</span></span>|
|<span data-ttu-id="6bd04-144">Windows Installer (auf einer Gerätegruppe bereitgestellt)</span><span class="sxs-lookup"><span data-stu-id="6bd04-144">Windows Installer (deployed to a device group)</span></span>|<span data-ttu-id="6bd04-145">Ja</span><span class="sxs-lookup"><span data-stu-id="6bd04-145">Yes</span></span>|<span data-ttu-id="6bd04-146">Nein</span><span class="sxs-lookup"><span data-stu-id="6bd04-146">No</span></span>|<span data-ttu-id="6bd04-147">Ja</span><span class="sxs-lookup"><span data-stu-id="6bd04-147">Yes</span></span>|<span data-ttu-id="6bd04-148">Ja</span><span class="sxs-lookup"><span data-stu-id="6bd04-148">Yes</span></span>|
|<span data-ttu-id="6bd04-149">Externer Link (für eine Benutzergruppe bereitgestellt)</span><span class="sxs-lookup"><span data-stu-id="6bd04-149">External link (deployed to a user group)</span></span>|<span data-ttu-id="6bd04-150">Nein</span><span class="sxs-lookup"><span data-stu-id="6bd04-150">No</span></span>|<span data-ttu-id="6bd04-151">Ja</span><span class="sxs-lookup"><span data-stu-id="6bd04-151">Yes</span></span>|<span data-ttu-id="6bd04-152">Nein</span><span class="sxs-lookup"><span data-stu-id="6bd04-152">No</span></span>|<span data-ttu-id="6bd04-153">Ja</span><span class="sxs-lookup"><span data-stu-id="6bd04-153">Yes</span></span>|
|<span data-ttu-id="6bd04-154">Externer Link (auf einer Gerätegruppe bereitgestellt)</span><span class="sxs-lookup"><span data-stu-id="6bd04-154">External link (deployed to a device group)</span></span>|<span data-ttu-id="6bd04-155">Nein</span><span class="sxs-lookup"><span data-stu-id="6bd04-155">No</span></span>|<span data-ttu-id="6bd04-156">Nein</span><span class="sxs-lookup"><span data-stu-id="6bd04-156">No</span></span>|<span data-ttu-id="6bd04-157">Nein</span><span class="sxs-lookup"><span data-stu-id="6bd04-157">No</span></span>|<span data-ttu-id="6bd04-158">Nein</span><span class="sxs-lookup"><span data-stu-id="6bd04-158">No</span></span>|
|<span data-ttu-id="6bd04-159">Verwaltete iOS-App aus dem App Store (für eine Benutzergruppe bereitgestellt)</span><span class="sxs-lookup"><span data-stu-id="6bd04-159">Managed iOS app from the app store (deployed to a user group)</span></span>|<span data-ttu-id="6bd04-160">Ja</span><span class="sxs-lookup"><span data-stu-id="6bd04-160">Yes</span></span>|<span data-ttu-id="6bd04-161">Ja</span><span class="sxs-lookup"><span data-stu-id="6bd04-161">Yes</span></span>|<span data-ttu-id="6bd04-162">Ja</span><span class="sxs-lookup"><span data-stu-id="6bd04-162">Yes</span></span>|<span data-ttu-id="6bd04-163">Ja</span><span class="sxs-lookup"><span data-stu-id="6bd04-163">Yes</span></span>|
|<span data-ttu-id="6bd04-164">Verwaltete iOS-App aus dem App Store (auf einer Gerätegruppe bereitgestellt)</span><span class="sxs-lookup"><span data-stu-id="6bd04-164">Managed iOS app from the app store (deployed to a device group)</span></span>|<span data-ttu-id="6bd04-165">Ja</span><span class="sxs-lookup"><span data-stu-id="6bd04-165">Yes</span></span>|<span data-ttu-id="6bd04-166">Nein</span><span class="sxs-lookup"><span data-stu-id="6bd04-166">No</span></span>|<span data-ttu-id="6bd04-167">Ja</span><span class="sxs-lookup"><span data-stu-id="6bd04-167">Yes</span></span>|<span data-ttu-id="6bd04-168">Ja</span><span class="sxs-lookup"><span data-stu-id="6bd04-168">Yes</span></span>|
> [!TIP]
> <span data-ttu-id="6bd04-169">Wenn Sie beim Bereitstellen von Apps sowohl Benutzer- als auch Gerätegruppen auswählen, können Sie die App nur als **verfügbare Installation** bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="6bd04-169">When you deploy apps, if you select both user and device groups, you can only deploy the app as an **Available install**.</span></span>

## <a name="deployment-conflicts"></a><span data-ttu-id="6bd04-170">Bereitstellungskonflikte</span><span class="sxs-lookup"><span data-stu-id="6bd04-170">Deployment conflicts</span></span>
<span data-ttu-id="6bd04-171">Wenn zwei Bereitstellungen mit der gleichen Bereitstellungsaktion von einem Gerät empfangen werden, gelten die folgenden Regeln:</span><span class="sxs-lookup"><span data-stu-id="6bd04-171">When two deployments with the same deployment action are received by a device, the following rules apply:</span></span>

-   <span data-ttu-id="6bd04-172">Bereitstellungen auf einer Gerätegruppe haben Vorrang vor Bereitstellung für eine Benutzergruppe.</span><span class="sxs-lookup"><span data-stu-id="6bd04-172">Deployments to a device group take precedence over deployments to a user group.</span></span> <span data-ttu-id="6bd04-173">Wenn jedoch eine App für eine Benutzergruppe mit der Bereitstellungsaktion **Verfügbar** bereitgestellt wird und dieselbe App auf einer Gerätegruppe mit der Bereitstellungsaktion **Nicht verfügbar** bereitgestellt wird, wird die App im Unternehmensportal Benutzern zur Installation zur Verfügung gestellt.</span><span class="sxs-lookup"><span data-stu-id="6bd04-173">However, if an app is deployed to a user group with a deployment action of **Available**, and the same app is also deployed to a device group with a deployment action of **Not Applicable**, the app will be made available in the company portal for users to install.</span></span>

-   <span data-ttu-id="6bd04-174">Eine Installationsaktion hat Vorrang vor einer Deinstallationsaktion.</span><span class="sxs-lookup"><span data-stu-id="6bd04-174">An install action takes precedence over an uninstall action.</span></span>

-   <span data-ttu-id="6bd04-175">Wenn eine erforderliche Installation und eine verfügbare Installation von einem Gerät empfangen werden, werden die Aktionen zusammengefasst.</span><span class="sxs-lookup"><span data-stu-id="6bd04-175">If both a required and an available install are received by a device, the actions are combined.</span></span> <span data-ttu-id="6bd04-176">Das bedeutet, dass der Benutzer die App aus dem Unternehmensportal installieren kann, bevor die erforderliche Installation beginnt.</span><span class="sxs-lookup"><span data-stu-id="6bd04-176">In other words, the user can install the available app from the company portal before the required install begins.</span></span>


## <a name="next-steps"></a><span data-ttu-id="6bd04-177">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="6bd04-177">Next steps</span></span>

<span data-ttu-id="6bd04-178">Erfahren Sie mehr zum [Bereitstellen von Apps in Microsoft Intune](deploy-apps-in-microsoft-intune.md).</span><span class="sxs-lookup"><span data-stu-id="6bd04-178">Learn how to [deploy apps in Microsoft Intune](deploy-apps-in-microsoft-intune.md).</span></span>
