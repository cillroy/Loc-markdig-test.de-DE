---
title: Konfigurieren von Windows 10-Editionsupgrades mit Intune
titlesuffix: Azure portal
description: "In diesem Artikel erfahren Sie, wie Sie mit Intune Windows 10-Geräte, die Sie verwalten, auf eine andere Edition aktualisieren."
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 12/16/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: ae8b6528-7979-47d8-abe0-58cea1905270
ms.reviewer: coryfe
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 408cb88cabe96ad1226c4189bd1337ec95ba8d37
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2017
---
# <a name="how-to-configure-windows-10-edition-upgrades-in-microsoft-intune"></a><span data-ttu-id="6f9fe-103">Konfigurieren von Windows 10-Editionsupgrades in Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="6f9fe-103">How to configure Windows 10 edition upgrades in Microsoft Intune</span></span>

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="6f9fe-104">In diesem Thema erfahren Sie, wie Sie ein Profil für Windows 10 Editionsupgrades konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="6f9fe-104">Use the information in this topic to learn how to configure a Windows 10 edition upgrade profile.</span></span> <span data-ttu-id="6f9fe-105">Mit diesem Profil können Sie Geräte, auf denen eine der folgenden Windows 10-Versionen ausgeführt wird, automatisch auf eine andere Edition aktualisieren:</span><span class="sxs-lookup"><span data-stu-id="6f9fe-105">This profile lets you automatically upgrade devices that run one of the following Windows 10 versions to a different edition:</span></span>

- <span data-ttu-id="6f9fe-106">Windows 10 Home</span><span class="sxs-lookup"><span data-stu-id="6f9fe-106">Windows 10 Home</span></span>
- <span data-ttu-id="6f9fe-107">Windows 10 Holographic</span><span class="sxs-lookup"><span data-stu-id="6f9fe-107">Windows 10 Holographic</span></span>
- <span data-ttu-id="6f9fe-108">Windows 10 Mobile</span><span class="sxs-lookup"><span data-stu-id="6f9fe-108">Windows 10 Mobile</span></span>


<span data-ttu-id="6f9fe-109">Die folgenden Upgradepfade werden unterstützt:</span><span class="sxs-lookup"><span data-stu-id="6f9fe-109">The following upgrade paths are supported:</span></span>

- <span data-ttu-id="6f9fe-110">Von Windows 10 Pro auf Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="6f9fe-110">From Windows 10 Pro to Windows 10 Enterprise</span></span>
- <span data-ttu-id="6f9fe-111">Von Windows 10 Home auf Windows 10 Education</span><span class="sxs-lookup"><span data-stu-id="6f9fe-111">From Windows 10 Home to Windows 10 Education</span></span>
- <span data-ttu-id="6f9fe-112">Von Windows 10 Mobile auf Windows 10 Mobile Enterprise</span><span class="sxs-lookup"><span data-stu-id="6f9fe-112">From Windows 10 Mobile to Windows 10 Mobile Enterprise</span></span>
- <span data-ttu-id="6f9fe-113">Von Windows 10 holographic oder Windows 10 Holographic for Business</span><span class="sxs-lookup"><span data-stu-id="6f9fe-113">From Windows 10 Holographic to Windows 10 Holographic for Business</span></span>


## <a name="before-you-start"></a><span data-ttu-id="6f9fe-114">Vorbereitung</span><span class="sxs-lookup"><span data-stu-id="6f9fe-114">Before you start</span></span>
<span data-ttu-id="6f9fe-115">Bevor Sie beginnen, Geräte auf die neueste Version zu aktualisieren, benötigen Sie eines der folgenden Dinge:</span><span class="sxs-lookup"><span data-stu-id="6f9fe-115">Before you begin to upgrade devices to the latest version, you need one of:</span></span>

- <span data-ttu-id="6f9fe-116">Einen gültigen Product Key für die Installation der neuen Version von Windows auf allen Geräten, die das Ziel dieser Richtlinie sind (für Windows 10-Desktopeditionen)</span><span class="sxs-lookup"><span data-stu-id="6f9fe-116">A product key that is valid to install the new version of Windows on all devices that you target with the policy (for Windows 10 Desktop editions).</span></span> <span data-ttu-id="6f9fe-117">Sie können entweder Mehrfachaktivierungsschlüssel (Multiple Activation Keys, MAK) oder KMS-Schlüssel (Key Management Server) oder eine Lizenzdatei von Microsoft verwenden, die die Lizenzierungsinformationen zum Installieren der neuen Version von Windows auf allen Geräten enthält, die das Ziel dieser Richtlinie sind (für Windows 10 Mobile- und Windows 10 Holographic-Editionen).</span><span class="sxs-lookup"><span data-stu-id="6f9fe-117">You can use either Multiple Activation Keys (MAK) or Key Management Server (KMS) keys or A license file from Microsoft that contains the licensing information to install the new version of Windows on all devices that you target with the policy (for Windows 10 Mobile and Windows 10 Holographic editions).</span></span>
- <span data-ttu-id="6f9fe-118">Die Windows 10-Geräte, für die Sie die Richtlinie zuweisen, müssen bei Microsoft Intune registriert sein.</span><span class="sxs-lookup"><span data-stu-id="6f9fe-118">The Windows 10 devices to which you assign the policy must be enrolled in Microsoft Intune.</span></span> <span data-ttu-id="6f9fe-119">Die Editionsupgraderichtlinie kann nicht für PCs verwendet werden, auf denen die Intune-PC-Clientsoftware ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="6f9fe-119">You cannot use the edition upgrade policy with PCs that run the Intune PC client software.</span></span>

## <a name="create-a-device-profile-containing-device-restriction-settings"></a><span data-ttu-id="6f9fe-120">Erstellen von Geräteprofilen mit Einstellungen für Geräteeinschränkungen</span><span class="sxs-lookup"><span data-stu-id="6f9fe-120">Create a device profile containing device restriction settings</span></span>

1. <span data-ttu-id="6f9fe-121">Melden Sie sich beim Azure-Portal an.</span><span class="sxs-lookup"><span data-stu-id="6f9fe-121">Sign into the Azure portal.</span></span>
2. <span data-ttu-id="6f9fe-122">Wählen Sie **Weitere Dienste** > **Überwachung und Verwaltung** > **Intune** aus.</span><span class="sxs-lookup"><span data-stu-id="6f9fe-122">Choose **More Services** > **Monitoring + Management** > **Intune**.</span></span>
3. <span data-ttu-id="6f9fe-123">Wählen Sie auf dem Blatt **Intune** die Option **Gerätekonfiguration** aus.</span><span class="sxs-lookup"><span data-stu-id="6f9fe-123">On the **Intune** blade, choose **Device configuration**.</span></span>
2. <span data-ttu-id="6f9fe-124">Wählen Sie auf dem Blatt **Gerätekonfiguration** die Option **Verwalten** > **Profile** aus.</span><span class="sxs-lookup"><span data-stu-id="6f9fe-124">On the **Device Configuration** blade, choose **Manage** > **Profiles**.</span></span>
3. <span data-ttu-id="6f9fe-125">Wählen Sie auf dem Blatt „Profile“ die Option **Profil erstellen** aus.</span><span class="sxs-lookup"><span data-stu-id="6f9fe-125">On the profiles blade, choose **Create Profile**.</span></span>
4. <span data-ttu-id="6f9fe-126">Geben Sie auf dem Blatt **Profil erstellen** einen **Namen** und eine **Beschreibung** für das Editionsupgradeprofil ein.</span><span class="sxs-lookup"><span data-stu-id="6f9fe-126">On the **Create Profile** blade, enter a **Name** and **Description** for the edition upgrade profile.</span></span>
5. <span data-ttu-id="6f9fe-127">Wählen Sie in der Dropdownliste **Plattform** die Option **Windows 10 und höher** aus.</span><span class="sxs-lookup"><span data-stu-id="6f9fe-127">From the **Platform** drop-down list, choose **Windows 10 and later**.</span></span>
6. <span data-ttu-id="6f9fe-128">Wählen Sie in der Dropdownliste **Profiltyp** die Option **Editionsupgrade** aus.</span><span class="sxs-lookup"><span data-stu-id="6f9fe-128">From the **Profile type** drop-down list, choose **Edition upgrade**.</span></span>
7. <span data-ttu-id="6f9fe-129">Auf dem Blatt **Editionsupgrade** konfigurieren Sie folgende Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="6f9fe-129">On the **Edition Upgrade** blade, configure the following settings:</span></span>
    - <span data-ttu-id="6f9fe-130">**Edition, auf die ein Upgrade durchgeführt wird:** Wählen Sie in der Dropdownliste die Version von Windows 10 Desktop, Windows 10 Holographic oder Windows 10 Mobile aus, auf die die als Ziel angegebenen Geräte aktualisiert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="6f9fe-130">**Edition to upgrade to** - From the drop-down list, select the version of Windows 10 Desktop, Windows 10 Holographic, or Windows 10 Mobile that you want to upgrade targeted devices to.</span></span>
    - <span data-ttu-id="6f9fe-131">**Product Key:** Geben Sie den Product Key an, den Sie von Microsoft erhalten haben, und der für das Upgrade aller als Ziel festgelegten Windows 10 Desktop-Geräte verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="6f9fe-131">**Product Key** - Specify the product key that you obtained from Microsoft, which can be used to upgrade all targeted Windows 10 Desktop devices.</span></span><br><span data-ttu-id="6f9fe-132">Nach der Erstellung einer Richtlinie, die einen Product Key enthält, können Sie den Product Key später nicht mehr bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="6f9fe-132">.After you create a policy that contains a product key, you cannot edit the product key later.</span></span> <span data-ttu-id="6f9fe-133">Grund hierfür ist, dass der Schlüssel aus Sicherheitsgründen verborgen wird.</span><span class="sxs-lookup"><span data-stu-id="6f9fe-133">This is because the key is obscured for security reasons.</span></span> <span data-ttu-id="6f9fe-134">Um den Product Key zu ändern, müssen Sie den gesamten Schlüssel erneut eingeben.</span><span class="sxs-lookup"><span data-stu-id="6f9fe-134">To change the product key, you must enter the entire key again.</span></span>
    - <span data-ttu-id="6f9fe-135">**Lizenzdatei:** Klicken Sie auf **Durchsuchen**, um die von Microsoft erhaltene Lizenzdatei auszuwählen, die Lizenzinformationen für die Windows Holographic-Edition oder für die Windows 10 Mobile-Edition enthält, auf die das Upgrade bei den als Ziel festgelegten Geräten erfolgen soll.</span><span class="sxs-lookup"><span data-stu-id="6f9fe-135">**License File** - Choose **Browse** to select the license file you obtained from Microsoft that contains license information for the Windows Holographic, or Windows 10 Mobile edition that you want to upgrade targeted devices to.</span></span>
8. <span data-ttu-id="6f9fe-136">Navigieren Sie anschließend zurück zum Blatt **Profil erstellen**, und klicken Sie auf **Erstellen**.</span><span class="sxs-lookup"><span data-stu-id="6f9fe-136">When you're done, go back to the **Create Profile** blade, and hit **Create**.</span></span>

<span data-ttu-id="6f9fe-137">Das Profil wird erstellt und auf dem Blatt mit der Profilliste angezeigt.</span><span class="sxs-lookup"><span data-stu-id="6f9fe-137">The profile is created and appears on the profiles list blade.</span></span>

## <a name="next-steps"></a><span data-ttu-id="6f9fe-138">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="6f9fe-138">Next steps</span></span>

<span data-ttu-id="6f9fe-139">Wenn Sie fortfahren und dieses Profil Gruppen zuweisen möchten, lesen Sie unter [Zuweisen von Geräteprofilen](device-profile-assign.md) nach.</span><span class="sxs-lookup"><span data-stu-id="6f9fe-139">If you want to go ahead and assign this profile to groups, see [How to assign device profiles](device-profile-assign.md).</span></span>

>[!NOTE]
><span data-ttu-id="6f9fe-140">Wenn Sie später die Richtlinienzuweisung entfernen, wird die Windows-Version auf dem Gerät nicht wiederhergestellt und wird weiterhin normal ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="6f9fe-140">If you later remove the policy assignment, the version of Windows on the device is not reverted, and continues to function normally.</span></span>

