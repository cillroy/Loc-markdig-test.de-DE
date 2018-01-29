---
title: "Suchen nach verlorenen iOS-Geräten mit Intune"
titlesuffix: Azure portal
description: "In diesem Artikel erfahren Sie, wie Sie nach verlorenen oder gestohlenen iOS-Geräten mit Intune suchen."
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 08/09/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3e544286-12ad-4a3a-86f8-d2cf16940b1f
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 4cbb245a3c3ea31b262951fa3bbcb90f39e2b854
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2018
---
# <a name="locate-lost-or-stolen-ios-devices-with-intune"></a><span data-ttu-id="014ad-103">Suchen nach verlorenen oder gestohlenen iOS-Geräten mit Intune</span><span class="sxs-lookup"><span data-stu-id="014ad-103">Locate lost or stolen iOS devices with Intune</span></span>


[!INCLUDE [azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="014ad-104">Mithilfe der Geräteaktion **Gerät suchen** können Sie den Standort eines verlorenen oder gestohlenen iOS-Geräts auf einer Karte anzeigen.</span><span class="sxs-lookup"><span data-stu-id="014ad-104">The **Locate Device** device action displays the location of a lost or stolen iOS device on a map.</span></span> <span data-ttu-id="014ad-105">Bei dem Gerät muss es sich um ein firmeneigenes, über DEP registriertes iOS-Gerät im überwachten Modus handeln.</span><span class="sxs-lookup"><span data-stu-id="014ad-105">The device must be a corporate-owned iOS device, enrolled through DEP, that is in supervised mode.</span></span> <span data-ttu-id="014ad-106">Diese Aktion kann erst verwendet werden, wenn das Gerät zuvor in den [Modus für verlorene Geräte](/intune-azure/manage-devices/lost-mode.md) versetzt wurde.</span><span class="sxs-lookup"><span data-stu-id="014ad-106">Before you use this action, the device must have been placed into [lost mode](/intune-azure/manage-devices/lost-mode.md).</span></span>

## <a name="supported-platforms"></a><span data-ttu-id="014ad-107">Unterstützte Plattformen</span><span class="sxs-lookup"><span data-stu-id="014ad-107">Supported platforms</span></span>

- <span data-ttu-id="014ad-108">Windows – Nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="014ad-108">Windows - Not supported</span></span>
- <span data-ttu-id="014ad-109">Windows Phone 8.1 – Nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="014ad-109">Windows Phone - Not supported</span></span>
- <span data-ttu-id="014ad-110">iOS – unter iOS 9.3 oder höher unterstützt (im Modus für verlorene Geräte), überwacht und unternehmenseigen</span><span class="sxs-lookup"><span data-stu-id="014ad-110">iOS - Supported on iOS 9.3 and later (in Lost mode), supervised, and corp owned</span></span>
- <span data-ttu-id="014ad-111">macOS – Nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="014ad-111">macOS - Not supported</span></span>
- <span data-ttu-id="014ad-112">Android – Nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="014ad-112">Android - Not supported</span></span>

## <a name="how-to-locate-a-lost-or-stolen-device"></a><span data-ttu-id="014ad-113">So suchen Sie ein verloren geganenes oder gestohlenes Geräts</span><span class="sxs-lookup"><span data-stu-id="014ad-113">How to locate a lost or stolen device</span></span>

1. <span data-ttu-id="014ad-114">Melden Sie sich beim Azure-Portal an.</span><span class="sxs-lookup"><span data-stu-id="014ad-114">Sign into the Azure portal.</span></span>
2. <span data-ttu-id="014ad-115">Wählen Sie **Weitere Dienste** > **Überwachung und Verwaltung** > **Intune** aus.</span><span class="sxs-lookup"><span data-stu-id="014ad-115">Choose **More Services** > **Monitoring + Management** > **Intune**.</span></span>
3. <span data-ttu-id="014ad-116">Wählen Sie auf dem Blatt **Intune** die Option **Geräte** aus.</span><span class="sxs-lookup"><span data-stu-id="014ad-116">On the **Intune** blade, choose **Devices**.</span></span>
4. <span data-ttu-id="014ad-117">Wählen Sie auf dem Blatt **Geräte und Gruppen** die Option **Alle Geräte** aus.</span><span class="sxs-lookup"><span data-stu-id="014ad-117">On the **Devices and groups** blade, choose **All devices**.</span></span>
5. <span data-ttu-id="014ad-118">Wählen Sie aus der Liste der von Ihnen verwalteten Geräte ein iOS-Gerät aus, und wählen Sie dann die Remoteaktion **Gerät suchen**.</span><span class="sxs-lookup"><span data-stu-id="014ad-118">From the list of devices you manage, choose an iOS device, and then choose the **Locate Device** remote action.</span></span>
6. <span data-ttu-id="014ad-119">Wenn das Gerät gefunden wurde, wird seine Position auf dem Blatt **Gerät suchen** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="014ad-119">After the device has been located, it's location is displayed on the **Locate device** blade.</span></span>
    <span data-ttu-id="014ad-120">Blatt ![Gerät suchen](./media/locate-device.png)</span><span class="sxs-lookup"><span data-stu-id="014ad-120">![Locate device blade](./media/locate-device.png)</span></span>

>[!NOTE]
><span data-ttu-id="014ad-121">Aus Datenschutzgründen können Sie nur begrenzt in die Karte hineinzoomen.</span><span class="sxs-lookup"><span data-stu-id="014ad-121">For privacy purposes, the distance you can zoom into the map is limited.</span></span>

## <a name="security-and-privacy-information-for-the-lost-mode-and-locate-device-actions"></a><span data-ttu-id="014ad-122">Sicherheit und Datenschutz im Zusammenhang mit dem Modus für verlorene Geräte und der Aktion „Gerät suchen“</span><span class="sxs-lookup"><span data-stu-id="014ad-122">Security and privacy information for the lost mode and locate device actions</span></span>
- <span data-ttu-id="014ad-123">Vor der Aktivierung dieser Aktion werden keinerlei Informationen zum Standort des Geräts an Intune gesendet.</span><span class="sxs-lookup"><span data-stu-id="014ad-123">No device location information is sent to Intune until you turn this action on.</span></span>
- <span data-ttu-id="014ad-124">Bei Verwendung der Aktion „Gerät suchen“ werden die Koordinaten des Geräts in Form von Breiten- und Längengrad an Intune gesendet und im Azure-Portal angezeigt.</span><span class="sxs-lookup"><span data-stu-id="014ad-124">When you use the locate device action, the latitude and longitude coordinates of the device are sent to Intune, and displayed in the Azure portal.</span></span>
- <span data-ttu-id="014ad-125">Die Daten werden 24 Stunden lang gespeichert und dann entfernt.</span><span class="sxs-lookup"><span data-stu-id="014ad-125">The data is stored for 24 hours, then removed.</span></span> <span data-ttu-id="014ad-126">Die Standortdaten können nicht manuell entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="014ad-126">You cannot manually remove the location data.</span></span>
- <span data-ttu-id="014ad-127">Die Standortdaten werden sowohl im gespeicherten Zustand als auch bei der Übertragung verschlüsselt.</span><span class="sxs-lookup"><span data-stu-id="014ad-127">Location data is encrypted, both while stored, and while being transmitted.</span></span>
- <span data-ttu-id="014ad-128">Beim Konfigurieren des Modus für verlorene Geräte empfiehlt es sich, in der Nachricht für den Sperrbildschirm Informationen anzugeben, die der Person, die das Gerät findet, eine Rückgabe ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="014ad-128">When you configure lost mode, we recommend that the message you enter to display on the lock screen includes information that helps someone who finds the device to return it.</span></span>


## <a name="next-steps"></a><span data-ttu-id="014ad-129">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="014ad-129">Next steps</span></span>

<span data-ttu-id="014ad-130">Um den Status der gerade ausgeführten Aktion anzuzeigen, wählen Sie auf dem Blatt **Geräte und Gruppen** die Option **Geräteaktionen** aus.</span><span class="sxs-lookup"><span data-stu-id="014ad-130">To see the status of the action you just took, on the **Devices and groups** blade, choose **Device Actions**.</span></span>