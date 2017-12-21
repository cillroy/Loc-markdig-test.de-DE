---
title: "Remote-Sperren von verwalteten Geräten durch Intune"
titlesuffix: Azure portal
description: "In diesem Artikel erfahren Sie, wie Sie die von Ihnen verwalteten Geräte mit Intune remote sperren."
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 11/21/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3b67f285-229d-4a0f-ae34-0402a20b4518
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 8905b97a5912010a2516788a8da66441fc6f89ae
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2017
---
# <a name="remotely-lock-managed-devices-with-intune"></a><span data-ttu-id="d8f78-103">Remote-Sperren von verwalteten Geräten durch Intune</span><span class="sxs-lookup"><span data-stu-id="d8f78-103">Remotely lock managed devices with Intune</span></span>


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="d8f78-104">Mit der Geräteaktion **Remote sperren** wird das ausgewählte Gerät gesperrt.</span><span class="sxs-lookup"><span data-stu-id="d8f78-104">The **Remote lock** device locks the selected device.</span></span> <span data-ttu-id="d8f78-105">Der Eigentümer des Geräts muss zum Entsperren seine Kennung verwenden.</span><span class="sxs-lookup"><span data-stu-id="d8f78-105">The device owner must use their passcode to unlock it.</span></span> <span data-ttu-id="d8f78-106">Sie können nur Remotesperrungen von Geräten durchführen, für die eine PIN oder ein Kennwort festgelegt wurde.</span><span class="sxs-lookup"><span data-stu-id="d8f78-106">You can only remotely lock a device that has a PIN or password set.</span></span>

## <a name="supported-platforms"></a><span data-ttu-id="d8f78-107">Unterstützte Plattformen</span><span class="sxs-lookup"><span data-stu-id="d8f78-107">Supported platforms</span></span>

- <span data-ttu-id="d8f78-108">Windows – Nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="d8f78-108">Windows - Not supported</span></span>
- <span data-ttu-id="d8f78-109">Windows Phone – Unterstützt auf Windows Phone 8.1 und später</span><span class="sxs-lookup"><span data-stu-id="d8f78-109">Windows Phone - Supported on Windows Phone 8.1 and later</span></span>
- <span data-ttu-id="d8f78-110">iOS – Unterstützt</span><span class="sxs-lookup"><span data-stu-id="d8f78-110">iOS - Supported</span></span>
- <span data-ttu-id="d8f78-111">macOs – Unterstützt</span><span class="sxs-lookup"><span data-stu-id="d8f78-111">macOS - Supported</span></span>

    > [!Note]  
    > <span data-ttu-id="d8f78-112">Legen Sie eine Wiederherstellungs-PIN mit 6 Ziffern fest.</span><span class="sxs-lookup"><span data-stu-id="d8f78-112">Set a 6-digit recovery PIN.</span></span> <span data-ttu-id="d8f78-113">Wenn das Gerät gesperrt ist, wird im Blatt **Device overview** (Geräteübersicht) die PIN solange angezeigt, bis eine andere Geräteaktion gesendet wurde.</span><span class="sxs-lookup"><span data-stu-id="d8f78-113">When locked, the **Device overview** blade displays the PIN until another device action is sent.</span></span>
- <span data-ttu-id="d8f78-114">Android – Unterstützung</span><span class="sxs-lookup"><span data-stu-id="d8f78-114">Android - Supported</span></span>

## <a name="how-to-remote-lock-a-device"></a><span data-ttu-id="d8f78-115">So sperren Sie ein Gerät aus der Ferne</span><span class="sxs-lookup"><span data-stu-id="d8f78-115">How to remote lock a device</span></span>

1. <span data-ttu-id="d8f78-116">Melden Sie sich beim Azure-Portal an.</span><span class="sxs-lookup"><span data-stu-id="d8f78-116">Sign into the Azure portal.</span></span>
2. <span data-ttu-id="d8f78-117">Wählen Sie **Weitere Dienste** > **Überwachung und Verwaltung** > **Intune** aus.</span><span class="sxs-lookup"><span data-stu-id="d8f78-117">Choose **More Services** > **Monitoring + Management** > **Intune**.</span></span>
3. <span data-ttu-id="d8f78-118">Wählen Sie auf dem Blatt **Intune** die Option **Geräte** aus.</span><span class="sxs-lookup"><span data-stu-id="d8f78-118">On the **Intune** blade, choose **Devices**.</span></span>
4. <span data-ttu-id="d8f78-119">Wählen Sie auf dem Blatt **Geräte und Gruppen** die Option **Alle Geräte** aus.</span><span class="sxs-lookup"><span data-stu-id="d8f78-119">On the **Devices and groups** blade, choose **All devices**.</span></span>
5. <span data-ttu-id="d8f78-120">Wählen Sie aus der Liste der verwalteten Geräte ein Gerät aus, und wählen Sie dann die Remotegeräteaktion **Remote sperren**.</span><span class="sxs-lookup"><span data-stu-id="d8f78-120">From the list of devices you manage, choose a device, and then choose the **Remote lock** device remote action.</span></span>

## <a name="next-steps"></a><span data-ttu-id="d8f78-121">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="d8f78-121">Next steps</span></span>

<span data-ttu-id="d8f78-122">Um den Status der gerade ausgeführten Aktion anzuzeigen, wählen Sie auf dem Blatt **Geräte und Gruppen** die Option **Geräteaktionen** aus.</span><span class="sxs-lookup"><span data-stu-id="d8f78-122">To see the status of the action you just took, on the **Devices and groups** blade, choose **Device Actions**.</span></span>
