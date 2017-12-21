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
ms.openlocfilehash: dde251482dd951200e5c1a7f19749ee863cd71b4
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2017
---
# <a name="remotely-restart-devices-with-intune"></a><span data-ttu-id="c4548-103">Remoteneustart von Geräten mit Intune</span><span class="sxs-lookup"><span data-stu-id="c4548-103">Remotely restart devices with Intune</span></span>


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="c4548-104">Die Geräteaktion **Neu starten** führt dazu, dass das von Ihnen gewählte Gerät neu gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="c4548-104">The **Restart** device action causes the device you choose to be restarted.</span></span> <span data-ttu-id="c4548-105">Der Eigentümer des Geräts wird nicht automatisch über den Neustart benachrichtigt und kann daher Daten verlieren.</span><span class="sxs-lookup"><span data-stu-id="c4548-105">The device owner is not automatically notified of the restart, therefore might lose work.</span></span>

## <a name="supported-platforms"></a><span data-ttu-id="c4548-106">Unterstützte Plattformen</span><span class="sxs-lookup"><span data-stu-id="c4548-106">Supported platforms</span></span>

- <span data-ttu-id="c4548-107">Windows – unter Windows 8.1 und höher unterstützt</span><span class="sxs-lookup"><span data-stu-id="c4548-107">Windows - Supported on Windows 8.1 and later</span></span>
- <span data-ttu-id="c4548-108">Windows Phone – Unterstützt auf Windows Phone 8.1 und später</span><span class="sxs-lookup"><span data-stu-id="c4548-108">Windows Phone - Supported on Windows Phone 8.1 and later</span></span>
- <span data-ttu-id="c4548-109">iOS – Unterstützt</span><span class="sxs-lookup"><span data-stu-id="c4548-109">iOS - Supported</span></span>

    > [!Note]  
    > <span data-ttu-id="c4548-110">Für diesen Befehl wird ein überwachtes Gerät und das Zugriffsrecht **Gerätesperre** benötigt.</span><span class="sxs-lookup"><span data-stu-id="c4548-110">This command requires a supervised devices and the **Device Lock** access right.</span></span> <span data-ttu-id="c4548-111">Das Gerät wird sofort neu gestartet.</span><span class="sxs-lookup"><span data-stu-id="c4548-111">The device restarts immediately.</span></span> <span data-ttu-id="c4548-112">Kennungsgeschützte iOS-Geräte verbinden Sie nach dem Neustart nicht wieder mit dem WLAN-Netzwerk und können unter Umständen nicht mehr mit dem Server kommunizieren.</span><span class="sxs-lookup"><span data-stu-id="c4548-112">Passcode-locked iOS devices will not rejoin a Wi-Fi network after restart; after restart, they may not be able to communicate with the server.</span></span>
- <span data-ttu-id="c4548-113">macOS – Nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="c4548-113">macOS - Not supported</span></span>
- <span data-ttu-id="c4548-114">Android – Nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="c4548-114">Android - Not supported</span></span>

## <a name="how-to-restart-a-device"></a><span data-ttu-id="c4548-115">So starten Sie einen Auftrags neu</span><span class="sxs-lookup"><span data-stu-id="c4548-115">How to restart a device</span></span>

1. <span data-ttu-id="c4548-116">Melden Sie sich beim Azure-Portal an.</span><span class="sxs-lookup"><span data-stu-id="c4548-116">Sign into the Azure portal.</span></span>
2. <span data-ttu-id="c4548-117">Wählen Sie **Weitere Dienste** > **Überwachung und Verwaltung** > **Intune** aus.</span><span class="sxs-lookup"><span data-stu-id="c4548-117">Choose **More Services** > **Monitoring + Management** > **Intune**.</span></span>
3. <span data-ttu-id="c4548-118">Wählen Sie auf dem Blatt **Intune** die Option **Geräte** aus.</span><span class="sxs-lookup"><span data-stu-id="c4548-118">On the **Intune** blade, choose **Devices**.</span></span>
4. <span data-ttu-id="c4548-119">Wählen Sie auf dem Blatt **Geräte und Gruppen** die Option **Alle Geräte** aus.</span><span class="sxs-lookup"><span data-stu-id="c4548-119">on the **Devices and groups** blade, choose **All devices**.</span></span>
5. <span data-ttu-id="c4548-120">Wählen Sie aus der Liste der verwalteten Geräte ein Gerät aus, und wählen Sie dann die Remotegeräteaktion **Neu starten**.</span><span class="sxs-lookup"><span data-stu-id="c4548-120">From the list of devices you manage, choose a device, and then choose the **Restart** device remote action.</span></span>

## <a name="next-steps"></a><span data-ttu-id="c4548-121">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="c4548-121">Next steps</span></span>

<span data-ttu-id="c4548-122">Um den Status der gerade ausgeführten Aktion anzuzeigen, wählen Sie auf dem Blatt **Geräte und Gruppen** die Option **Geräteaktionen** aus.</span><span class="sxs-lookup"><span data-stu-id="c4548-122">To see the status of the action you just took, on the **Devices and groups** blade, choose **Device Actions**.</span></span>
