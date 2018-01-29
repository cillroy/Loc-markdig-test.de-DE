---
title: Erstellen von benutzerdefinierten VPN-Profilen mit Microsoft Intune
titleSuffix: Azure portal
description: Verwenden Sie benutzerdefinierte Konfigurationen, um VPN-Profile in Intune zu erstellen.
keywords: 
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 06/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4c0bd439-3b58-420b-9a9a-282886986786
ms.reviewer: karanda
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: d21f479d5cc350a0c55ae94a427aea35ad9ecf00
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2018
---
# <a name="how-to-create-custom-vpn-profiles-in-microsoft-intune"></a><span data-ttu-id="47819-103">Erstellen von benutzerdefinierten VPN-Profilen in Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="47819-103">How to create custom VPN profiles in Microsoft Intune</span></span>

## <a name="create-a-custom-configuration"></a><span data-ttu-id="47819-104">Erstellen einer benutzerdefinierten Konfiguration</span><span class="sxs-lookup"><span data-stu-id="47819-104">Create a custom configuration</span></span>
<span data-ttu-id="47819-105">Sie können benutzerdefinierte Intune-Konfigurationsrichtlinien verwenden, um VPN-Profile für folgende Geräte zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="47819-105">You can use Intune custom configuration polices to create VPN profiles for:</span></span>

* <span data-ttu-id="47819-106">Geräte unter Android 4 und höher</span><span class="sxs-lookup"><span data-stu-id="47819-106">Devices that run Android 4 and later</span></span>
* <span data-ttu-id="47819-107">Registrierte Geräte unter Windows 8.1 und höher</span><span class="sxs-lookup"><span data-stu-id="47819-107">Enrolled devices that run Windows 8.1 and later</span></span>
* <span data-ttu-id="47819-108">Geräte unter Windows Phone 8.1 und höher</span><span class="sxs-lookup"><span data-stu-id="47819-108">Devices that run Windows Phone 8.1 and later</span></span>
* <span data-ttu-id="47819-109">Registrierte Geräte unter Windows 10 Desktop</span><span class="sxs-lookup"><span data-stu-id="47819-109">Enrolled devices that run Windows 10 desktop</span></span> 
* <span data-ttu-id="47819-110">Geräte unter Windows 10 Mobile</span><span class="sxs-lookup"><span data-stu-id="47819-110">Devices that run Windows 10 Mobile</span></span>

<span data-ttu-id="47819-111">Dieser Richtlinientyp kann hilfreich sein, wenn die standardmäßigen Intune-VPN-Richtlinien nicht die Einstellungen enthalten, die Sie verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="47819-111">This type of policy can be useful when the standard Intune VPN policies do not contain the settings you want to use.</span></span>

## <a name="to-create-a-custom-configuration-policy"></a><span data-ttu-id="47819-112">So erstellen Sie eine benutzerdefinierte Konfigurationsrichtlinie:</span><span class="sxs-lookup"><span data-stu-id="47819-112">To create a custom configuration policy:</span></span>

1. <span data-ttu-id="47819-113">Melden Sie sich beim Azure-Portal an.</span><span class="sxs-lookup"><span data-stu-id="47819-113">Sign into the Azure portal.</span></span>
2. <span data-ttu-id="47819-114">Wählen Sie **Weitere Dienste** > **Überwachung und Verwaltung** > **Intune** aus.</span><span class="sxs-lookup"><span data-stu-id="47819-114">Choose **More Services** > **Monitoring + Management** > **Intune**.</span></span>
3. <span data-ttu-id="47819-115">Wählen Sie auf dem Blatt **Intune** die Option **Gerätekonfiguration** aus.</span><span class="sxs-lookup"><span data-stu-id="47819-115">On the **Intune** blade, choose **Device configuration**.</span></span>
4. <span data-ttu-id="47819-116">Wählen Sie auf dem Blatt **Gerätekonfiguration** die Option **Verwalten** > **Profile** aus.</span><span class="sxs-lookup"><span data-stu-id="47819-116">On the **Device Configuration** blade, choose **Manage** > **Profiles**.</span></span>
5. <span data-ttu-id="47819-117">Wählen Sie auf dem Blatt „Profile“ die Option **Profil erstellen** aus.</span><span class="sxs-lookup"><span data-stu-id="47819-117">On the profiles blade, choose **Create Profile**.</span></span>
6. <span data-ttu-id="47819-118">Geben Sie auf dem Blatt **Profil erstellen** einen **Namen** und eine **Beschreibung** für das VPN-Profil ein.</span><span class="sxs-lookup"><span data-stu-id="47819-118">On the **Create Profile** blade, enter a **Name** and **Description** for the VPN profile.</span></span>
7. <span data-ttu-id="47819-119">Wählen Sie in der Dropdownliste **Plattform** die Geräteplattform aus, auf die Sie VPN-Einstellungen anwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="47819-119">From the **Platform** drop-down list, select the device platform to which you want to apply VPN settings.</span></span> <span data-ttu-id="47819-120">Derzeit können Sie eine der folgenden Plattformen für die benutzerdefinierte Geräteeinstellungen auswählen:</span><span class="sxs-lookup"><span data-stu-id="47819-120">Currently, you can choose one of the following platforms for custom device settings:</span></span>
    - <span data-ttu-id="47819-121">**Android**</span><span class="sxs-lookup"><span data-stu-id="47819-121">**Android**</span></span>
    - <span data-ttu-id="47819-122">**iOS** (konfiguriert mit einer Datei, die Sie aus Apple Configurator exportiert haben)</span><span class="sxs-lookup"><span data-stu-id="47819-122">**iOS** (configured using a file you exported from Apple Configurator).</span></span>
    - <span data-ttu-id="47819-123">**macOS** (konfiguriert mit einer Datei, die Sie aus Apple Configurator exportiert haben)</span><span class="sxs-lookup"><span data-stu-id="47819-123">**macOS** (configured using a file you exported from Apple Configurator).</span></span>
    - <span data-ttu-id="47819-124">**Windows Phone 8.1**</span><span class="sxs-lookup"><span data-stu-id="47819-124">**Windows Phone 8.1**</span></span>
    - <span data-ttu-id="47819-125">**Windows 10 und höher**</span><span class="sxs-lookup"><span data-stu-id="47819-125">**Windows 10 and later**</span></span>
6. <span data-ttu-id="47819-126">Wählen Sie in der Dropdownliste **Profiltyp** die Option **Benutzerdefiniert** aus.</span><span class="sxs-lookup"><span data-stu-id="47819-126">From the **Profile** type drop-down list, choose **Custom**.</span></span>
7. <span data-ttu-id="47819-127">Wählen Sie auf dem Blatt **Benutzerdefinierte OMA-URI-Einstellungen** für jede URI-Einstellung, die Sie angeben möchten, **Hinzufügen** aus, geben Sie die geforderten Informationen ein, und wählen Sie dann **OK** aus.</span><span class="sxs-lookup"><span data-stu-id="47819-127">On the **Custom OMA-URI Settings** blade, for each URI setting you want to specify, choose **Add**, provide the requested information, then choose **OK**.</span></span> <span data-ttu-id="47819-128">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="47819-128">Here's an example:</span></span>

   ![Dialogfeld „Benutzerdefinierte VPN-Profilkonfiguration“](./media/Intune_Add_VPN_URI.png)

4.  <span data-ttu-id="47819-130">Nachdem Sie alle erforderlichen URI-Einstellungen eingegeben haben, wählen Sie **OK** und dann auf dem Blatt **Profil erstellen** die Option **Erstellen** aus.</span><span class="sxs-lookup"><span data-stu-id="47819-130">After you've entered all of URI settings you need, choose **OK**, and then, on the **Create Profile** blade, choose **Create**.</span></span>

<span data-ttu-id="47819-131">Das Profil wird erstellt und auf dem Blatt mit der Profilliste angezeigt.</span><span class="sxs-lookup"><span data-stu-id="47819-131">The profile will be created and appears on the profiles list blade.</span></span>
<span data-ttu-id="47819-132">Wenn Sie fortfahren und dieses Profil Gruppen zuweisen möchten, lesen Sie unter [Zuweisen von Geräteprofilen](device-profile-assign.md) nach.</span><span class="sxs-lookup"><span data-stu-id="47819-132">If you want to go ahead and assign this profile to groups, see [How to assign device profiles](device-profile-assign.md).</span></span>




