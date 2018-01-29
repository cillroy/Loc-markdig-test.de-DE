---
title: "Remoteneustart von Geräten mit Intune"
titlesuffix: Azure portal
description: "In diesem Artikel erfahren Sie, wie Geräte über die Aktion zum Neustarten des Geräts remote neu gestartet werden."
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 11/21/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c707e0c4-391a-4bad-9dfd-9a7799c48dd5
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 9e20740c1890faabec7e2e1155007a21d4b090b2
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2018
---
# <a name="remotely-restart-devices-with-intune"></a><span data-ttu-id="9ee0e-103">Remoteneustart von Geräten mit Intune</span><span class="sxs-lookup"><span data-stu-id="9ee0e-103">Remotely restart devices with Intune</span></span>


[!INCLUDE [azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="9ee0e-104">Die Geräteaktion **Neu starten** führt dazu, dass das von Ihnen gewählte Gerät neu gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="9ee0e-104">The **Restart** device action causes the device you choose to be restarted.</span></span> <span data-ttu-id="9ee0e-105">Der Eigentümer des Geräts wird nicht automatisch über den Neustart benachrichtigt und kann daher Daten verlieren.</span><span class="sxs-lookup"><span data-stu-id="9ee0e-105">The device owner is not automatically notified of the restart, therefore might lose work.</span></span>

## <a name="supported-platforms"></a><span data-ttu-id="9ee0e-106">Unterstützte Plattformen</span><span class="sxs-lookup"><span data-stu-id="9ee0e-106">Supported platforms</span></span>

- <span data-ttu-id="9ee0e-107">Windows – unter Windows 8.1 und höher unterstützt</span><span class="sxs-lookup"><span data-stu-id="9ee0e-107">Windows - Supported on Windows 8.1 and later</span></span>
- <span data-ttu-id="9ee0e-108">Windows Phone – Unterstützt auf Windows Phone 8.1 und später</span><span class="sxs-lookup"><span data-stu-id="9ee0e-108">Windows Phone - Supported on Windows Phone 8.1 and later</span></span>
- <span data-ttu-id="9ee0e-109">iOS – Unterstützt</span><span class="sxs-lookup"><span data-stu-id="9ee0e-109">iOS - Supported</span></span>

    > [!Note]  
    > <span data-ttu-id="9ee0e-110">Für diesen Befehl wird ein überwachtes Gerät und das Zugriffsrecht **Gerätesperre** benötigt.</span><span class="sxs-lookup"><span data-stu-id="9ee0e-110">This command requires a supervised devices and the **Device Lock** access right.</span></span> <span data-ttu-id="9ee0e-111">Das Gerät wird sofort neu gestartet.</span><span class="sxs-lookup"><span data-stu-id="9ee0e-111">The device restarts immediately.</span></span> <span data-ttu-id="9ee0e-112">Kennungsgeschützte iOS-Geräte verbinden Sie nach dem Neustart nicht wieder mit dem WLAN-Netzwerk und können unter Umständen nicht mehr mit dem Server kommunizieren.</span><span class="sxs-lookup"><span data-stu-id="9ee0e-112">Passcode-locked iOS devices will not rejoin a Wi-Fi network after restart; after restart, they may not be able to communicate with the server.</span></span>
- <span data-ttu-id="9ee0e-113">macOS – Nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="9ee0e-113">macOS - Not supported</span></span>
- <span data-ttu-id="9ee0e-114">Android – Nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="9ee0e-114">Android - Not supported</span></span>

## <a name="how-to-restart-a-device"></a><span data-ttu-id="9ee0e-115">So starten Sie einen Auftrags neu</span><span class="sxs-lookup"><span data-stu-id="9ee0e-115">How to restart a device</span></span>

1. <span data-ttu-id="9ee0e-116">Melden Sie sich beim Azure-Portal an.</span><span class="sxs-lookup"><span data-stu-id="9ee0e-116">Sign into the Azure portal.</span></span>
2. <span data-ttu-id="9ee0e-117">Wählen Sie **Weitere Dienste** > **Überwachung und Verwaltung** > **Intune** aus.</span><span class="sxs-lookup"><span data-stu-id="9ee0e-117">Choose **More Services** > **Monitoring + Management** > **Intune**.</span></span>
3. <span data-ttu-id="9ee0e-118">Wählen Sie auf dem Blatt **Intune** die Option **Geräte** aus.</span><span class="sxs-lookup"><span data-stu-id="9ee0e-118">On the **Intune** blade, choose **Devices**.</span></span>
4. <span data-ttu-id="9ee0e-119">Wählen Sie auf dem Blatt **Geräte und Gruppen** die Option **Alle Geräte** aus.</span><span class="sxs-lookup"><span data-stu-id="9ee0e-119">on the **Devices and groups** blade, choose **All devices**.</span></span>
5. <span data-ttu-id="9ee0e-120">Wählen Sie aus der Liste der verwalteten Geräte ein Gerät aus, und wählen Sie dann die Remotegeräteaktion **Neu starten**.</span><span class="sxs-lookup"><span data-stu-id="9ee0e-120">From the list of devices you manage, choose a device, and then choose the **Restart** device remote action.</span></span>

## <a name="next-steps"></a><span data-ttu-id="9ee0e-121">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="9ee0e-121">Next steps</span></span>

<span data-ttu-id="9ee0e-122">Um den Status der gerade ausgeführten Aktion anzuzeigen, wählen Sie auf dem Blatt **Geräte und Gruppen** die Option **Geräteaktionen** aus.</span><span class="sxs-lookup"><span data-stu-id="9ee0e-122">To see the status of the action you just took, on the **Devices and groups** blade, choose **Device Actions**.</span></span>
