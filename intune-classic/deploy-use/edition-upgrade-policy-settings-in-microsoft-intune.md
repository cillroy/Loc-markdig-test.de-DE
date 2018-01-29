---
title: "Richtlinieneinstellungen für Windows-Editionsupgrades"
description: "Erfahren Sie, wie Sie Windows 10-Geräte mit Intune automatisch auf eine andere Version aktualisieren."
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 04/14/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 8589866a-3f13-489b-a5cd-cee017d16d54
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: coryfe
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: a3bd14a7116e3d9391bac411aef2d1e968281682
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2018
---
# <a name="windows-edition-upgrade-policy-settings-in-microsoft-intune"></a><span data-ttu-id="c8594-103">Einstellungen der Richtlinie für Windows-Editionsupgrades in Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="c8594-103">Windows edition upgrade policy settings in Microsoft Intune</span></span>

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="c8594-104">Mithilfe der Microsoft Intune-**Richtlinie für Editionsupgrades** können Sie für Geräte, die eine der folgenden Windows 10-Versionen ausführen, automatisch Upgrades auf eine andere Edition vornehmen:</span><span class="sxs-lookup"><span data-stu-id="c8594-104">The Microsoft Intune **Edition Upgrade Policy** lets you automatically upgrade devices that run one of the following Windows 10 versions to a different edition:</span></span>
* <span data-ttu-id="c8594-105">Windows 10 Desktop</span><span class="sxs-lookup"><span data-stu-id="c8594-105">Windows 10 Desktop</span></span>
* <span data-ttu-id="c8594-106">Windows 10 Holographic</span><span class="sxs-lookup"><span data-stu-id="c8594-106">Windows 10 Holographic</span></span>
* <span data-ttu-id="c8594-107">Windows 10 Mobile</span><span class="sxs-lookup"><span data-stu-id="c8594-107">Windows 10 Mobile</span></span>

<span data-ttu-id="c8594-108">Die folgenden Upgradepfade werden unterstützt:</span><span class="sxs-lookup"><span data-stu-id="c8594-108">The following upgrade paths are supported:</span></span>
- <span data-ttu-id="c8594-109">Von Windows 10 Pro auf Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="c8594-109">From Windows 10 Pro to Windows 10 Enterprise</span></span>
- <span data-ttu-id="c8594-110">Von Windows 10 Home auf Windows 10 Education</span><span class="sxs-lookup"><span data-stu-id="c8594-110">From Windows 10 Home to Windows 10 Education</span></span>
- <span data-ttu-id="c8594-111">Von Windows 10 Mobile auf Windows 10 Mobile Enterprise</span><span class="sxs-lookup"><span data-stu-id="c8594-111">From Windows 10 Mobile to Windows 10 Mobile Enterprise</span></span>
- <span data-ttu-id="c8594-112">Von Windows 10 Holographic Pro auf Windows 10 Holographic Enterprise</span><span class="sxs-lookup"><span data-stu-id="c8594-112">From Windows 10 Holographic Pro to Windows 10 Holographic Enterprise</span></span>

## <a name="before-you-start"></a><span data-ttu-id="c8594-113">Vorbereitung</span><span class="sxs-lookup"><span data-stu-id="c8594-113">Before you start</span></span>
<span data-ttu-id="c8594-114">Bevor Sie beginnen, Geräte auf die neueste Version zu aktualisieren, benötigen Sie eines der folgenden Dinge:</span><span class="sxs-lookup"><span data-stu-id="c8594-114">Before you begin to upgrade devices to the latest version, you will need one of the following:</span></span>
* <span data-ttu-id="c8594-115">Einen gültigen Product Key für die Installation der neuen Version von Windows auf allen Geräten, die das Ziel dieser Richtlinie sind (für Windows 10-Desktopeditionen)</span><span class="sxs-lookup"><span data-stu-id="c8594-115">A product key that is valid to install the new version of Windows on all devices that you target with the policy (for Windows 10 Desktop editions).</span></span> <span data-ttu-id="c8594-116">Sie können entweder Mehrfachaktivierungsschlüssel (Multiple Activation Keys, MAK) oder KMS-Schlüssel (Key Management Server, Schlüsselverwaltungsserver) verwenden.</span><span class="sxs-lookup"><span data-stu-id="c8594-116">You can use either Multiple Activation Keys (MAK) or Key Management Server (KMS) keys.</span></span>
<span data-ttu-id="c8594-117">**Alternativ** verwenden Sie eine Lizenzdatei von Microsoft, die die Lizenzierungsinformationen zum Installieren der neuen Version von Windows auf allen Geräten enthält, die das Ziel dieser Richtlinie sind (für Windows 10 Mobile- und Windows 10 Holographic-Editionen).</span><span class="sxs-lookup"><span data-stu-id="c8594-117">**or** A license file from Microsoft that contains the licensing information to install the new version of Windows on all devices that you target with the policy (for Windows 10 Mobile and Windows 10 Holographic editions).</span></span>
* <span data-ttu-id="c8594-118">Die Windows 10-Geräte, die als Ziel vorgesehen sind, müssen bei Microsoft Intune registriert sein.</span><span class="sxs-lookup"><span data-stu-id="c8594-118">The Windows 10 devices that you target must be enrolled in Microsoft Intune.</span></span> <span data-ttu-id="c8594-119">Die Editionsupgraderichtlinie kann nicht für PCs verwendet werden, auf denen die Intune-PC-Clientsoftware ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="c8594-119">You cannot use the edition upgrade policy with PCs that run the Intune PC client software.</span></span>

## <a name="edition-upgrade-policy-settings"></a><span data-ttu-id="c8594-120">Einstellungen der Richtlinie für Editionsupgrades</span><span class="sxs-lookup"><span data-stu-id="c8594-120">Edition upgrade policy settings</span></span>

|<span data-ttu-id="c8594-121">Name der Einstellung</span><span class="sxs-lookup"><span data-stu-id="c8594-121">Setting name</span></span>|<span data-ttu-id="c8594-122">Details</span><span class="sxs-lookup"><span data-stu-id="c8594-122">Details</span></span>|
|-|-|
|<span data-ttu-id="c8594-123">**Name**</span><span class="sxs-lookup"><span data-stu-id="c8594-123">**Name**</span></span>|<span data-ttu-id="c8594-124">Geben Sie einen Namen für die Richtlinie für Editionsupgrades ein.</span><span class="sxs-lookup"><span data-stu-id="c8594-124">Enter a name for the edition upgrade policy.</span></span>|
|<span data-ttu-id="c8594-125">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="c8594-125">**Description**</span></span>|<span data-ttu-id="c8594-126">Geben Sie optional eine Beschreibung für die Richtlinie ein, damit Sie sie in der Intune-Konsole besser identifizieren können.</span><span class="sxs-lookup"><span data-stu-id="c8594-126">Optionally, enter a description for the policy that helps you identify it in the Intune console.</span></span>
|<span data-ttu-id="c8594-127">**Edition, auf die das Upgrade erfolgen soll**</span><span class="sxs-lookup"><span data-stu-id="c8594-127">**Edition to upgrade to**</span></span>|<span data-ttu-id="c8594-128">Wählen Sie aus der Dropdownliste die Version von Windows 10 Desktop, Windows 10 Holographic oder Windows 10 Mobile aus, auf die ein Upgrade für die als Ziel angegebenen Geräte erfolgen soll.</span><span class="sxs-lookup"><span data-stu-id="c8594-128">From the drop-down list, select the version of Windows 10 Desktop, Windows 10 Holographic, or Windows 10 Mobile that you want to upgrade targeted devices to.</span></span>
|<span data-ttu-id="c8594-129">**Product Key**</span><span class="sxs-lookup"><span data-stu-id="c8594-129">**Product Key**</span></span>|<span data-ttu-id="c8594-130">Geben Sie den Product Key an, den Sie von Microsoft erhalten haben, und der für das Upgrade aller als Ziel festgelegten Windows 10 Desktop-Geräte verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="c8594-130">Specify the product key that you obtained from Microsoft, which can be used to upgrade all targeted Windows 10 Desktop devices.</span></span><br><span data-ttu-id="c8594-131">Nach der Erstellung einer Richtlinie, die einen Product Key enthält, können Sie den Product Key später nicht mehr bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="c8594-131">After you create a policy that contains a product key, you cannot edit the product key later.</span></span> <span data-ttu-id="c8594-132">Grund hierfür ist, dass der Schlüssel aus Sicherheitsgründen verborgen wird.</span><span class="sxs-lookup"><span data-stu-id="c8594-132">This is because the key is obscured for security reasons.</span></span> <span data-ttu-id="c8594-133">Um den Product Key zu ändern, müssen Sie den gesamten Schlüssel erneut eingeben.</span><span class="sxs-lookup"><span data-stu-id="c8594-133">To change the product key, you must enter the entire key again.</span></span>
|<span data-ttu-id="c8594-134">**Lizenzdatei**</span><span class="sxs-lookup"><span data-stu-id="c8594-134">**License File**</span></span>|<span data-ttu-id="c8594-135">Klicken Sie auf **Durchsuchen**, um die von Microsoft erhaltene Lizenzdatei auszuwählen, die Lizenzinformationen für die Windows Holographic-Edition oder für die Windows 10 Mobile-Edition enthält, auf die das Upgrade bei den als Ziel festgelegten Geräten erfolgen soll.</span><span class="sxs-lookup"><span data-stu-id="c8594-135">Choose **Browse** to select the license file you obtained from Microsoft that contains license information for the Windows Holographic, or Windows 10 Mobile edition that you want to upgrade targeted devices to.</span></span>

### <a name="see-also"></a><span data-ttu-id="c8594-136">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="c8594-136">See also</span></span>
[<span data-ttu-id="c8594-137">Verwalten von Einstellungen und Features auf Ihren Geräten mit Microsoft Intune-Richtlinien</span><span class="sxs-lookup"><span data-stu-id="c8594-137">Manage settings and features on your devices with Microsoft Intune policies</span></span>](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)
