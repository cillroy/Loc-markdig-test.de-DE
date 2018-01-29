---
title: "Zurücksetzen von Windows 10-Geräten mit Intune"
titlesuffix: Azure portal
description: "Erfahren Sie, wie Sie die Aktion „Sauberer Start“ verwenden, um Windows 10-PCs zurückzusetzen, auf denen Intune ausgeführt wird.\""
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 08/09/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5aa5cfa3-c483-4099-b40f-578ff8dca425
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 503780de384521bfae2ca8e22bdbae1b60d3a64d
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2018
---
# <a name="use-fresh-start-to-reset-windows-10-devices-with-intune"></a><span data-ttu-id="887f0-103">Verwenden der Aktion „Sauberer Start“ zum Zurücksetzen von Windows 10-Geräten mit Intune</span><span class="sxs-lookup"><span data-stu-id="887f0-103">Use Fresh Start to reset Windows 10 devices with Intune</span></span>


[!INCLUDE [azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="887f0-104">Die Geräteaktion **Sauberer Start** entfernt alle Apps, die auf einem Windows 10-PC mit Creators Update installiert wurden, und aktualisiert den PC dann automatisch auf die neueste Windows-Version.</span><span class="sxs-lookup"><span data-stu-id="887f0-104">The **Fresh Start** device action removes any apps that were installed on a Windows 10 PC running the Creators Update, then automatically updates the PC to the latest version of Windows.</span></span>
<span data-ttu-id="887f0-105">Mit dieser Option können vorinstallierte OEM-Apps entfernt werden, die oft mit einem neuen PC geliefert werden.</span><span class="sxs-lookup"><span data-stu-id="887f0-105">This can be used to help remove pre-installed (OEM) apps that are often delivered with a new PC.</span></span> <span data-ttu-id="887f0-106">Sie können konfigurieren, ob Benutzerdaten beibehalten werden, wenn diese Geräteaktion ausgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="887f0-106">You can configure if user data is retained when this device action is issued.</span></span> <span data-ttu-id="887f0-107">In diesem Fall werden alle Apps und Einstellungen entfernt, die Inhalte des Basisordners des Benutzers bleiben jedoch erhalten.</span><span class="sxs-lookup"><span data-stu-id="887f0-107">In this case, apps and settings are removed, but the contents of the users Home folder are retained.</span></span>

## <a name="how-to-use-fresh-start"></a><span data-ttu-id="887f0-108">So verwenden Sie Fresh Start</span><span class="sxs-lookup"><span data-stu-id="887f0-108">How to use Fresh Start</span></span>

1. <span data-ttu-id="887f0-109">Melden Sie sich beim Azure-Portal an.</span><span class="sxs-lookup"><span data-stu-id="887f0-109">Sign into the Azure portal.</span></span>
2. <span data-ttu-id="887f0-110">Wählen Sie **Weitere Dienste** > **Überwachung und Verwaltung** > **Intune** aus.</span><span class="sxs-lookup"><span data-stu-id="887f0-110">Choose **More Services** > **Monitoring + Management** > **Intune**.</span></span>
3. <span data-ttu-id="887f0-111">Wählen Sie auf dem Blatt **Intune** die Option **Geräte** aus.</span><span class="sxs-lookup"><span data-stu-id="887f0-111">On the **Intune** blade, choose **Devices**.</span></span>
4. <span data-ttu-id="887f0-112">Wählen Sie auf dem Blatt **Geräte und Gruppen** die Option **Alle Geräte** aus.</span><span class="sxs-lookup"><span data-stu-id="887f0-112">On the **Devices and groups** blade, choose **All devices**.</span></span>
5. <span data-ttu-id="887f0-113">Wählen Sie aus der Liste der verwalteten Geräte ein Windows 10-Desktopgerät aus, und wählen Sie dann die Remotegeräteaktion **Sauberer Start**.</span><span class="sxs-lookup"><span data-stu-id="887f0-113">From the list of devices you manage, choose a Windows 10 desktop device, and then choose the **Fresh Start** device remote action.</span></span>

## <a name="next-steps"></a><span data-ttu-id="887f0-114">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="887f0-114">Next steps</span></span>

<span data-ttu-id="887f0-115">Um den Status der gerade ausgeführten Aktion anzuzeigen, wählen Sie auf dem Blatt **Geräte und Gruppen** die Option **Geräteaktionen** aus.</span><span class="sxs-lookup"><span data-stu-id="887f0-115">To see the status of the action you just took, on the **Devices and groups** blade, choose **Device Actions**.</span></span>

