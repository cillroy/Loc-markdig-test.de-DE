---
title: "Aktivieren des Modus für verlorene iOS-Geräte mit Intune"
titlesuffix: Azure portal
description: "In diesem Artikel erfahren Sie, wie Sie den Modus für verlorene oder gestohlene iOS-Geräte mithilfe von Intune aktivieren."
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 08/09/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 126a7489-fe3e-43fd-a681-defb2fe0bb66
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: c4baeed6e2549b19ccb58cebd051baeac755ff47
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2018
---
# <a name="activate-lost-mode-on-ios-devices"></a><span data-ttu-id="4539d-103">Aktivieren des Modus für verlorene Geräte auf iOS-Geräten</span><span class="sxs-lookup"><span data-stu-id="4539d-103">Activate lost mode on iOS devices</span></span>


[!INCLUDE [azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="4539d-104">Durch die Geräteaktion **Modus für verlorene Geräte** können Sie den Modus für verlorene Geräte auf verlorenen oder gestohlenen iOS-Geräten aktivieren.</span><span class="sxs-lookup"><span data-stu-id="4539d-104">The **Lost mode** device action helps you enable lost mode on lost or stolen iOS devices.</span></span> <span data-ttu-id="4539d-105">Dieser Modus ermöglicht die Angabe einer Nachricht und einer Telefonnummer, die auf dem Sperrbildschirm des Geräts angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="4539d-105">This mode lets you specify a message and a phone number that is displayed on the lock screen of the device.</span></span>

## <a name="supported-platforms"></a><span data-ttu-id="4539d-106">Unterstützte Plattformen</span><span class="sxs-lookup"><span data-stu-id="4539d-106">Supported platforms</span></span>

- <span data-ttu-id="4539d-107">Windows – Nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="4539d-107">Windows - Not supported</span></span>
- <span data-ttu-id="4539d-108">Windows Phone – Nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="4539d-108">Windows Phone - Not supported</span></span>
- <span data-ttu-id="4539d-109">iOS – Unterstützt unter iOS 9.3 oder höher, überwacht, und in Unternehmenbesitz</span><span class="sxs-lookup"><span data-stu-id="4539d-109">iOS - Supported on iOS 9.3 and later, supervised, and corp owned</span></span>
- <span data-ttu-id="4539d-110">macOS – Nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="4539d-110">macOS - Not supported</span></span>
- <span data-ttu-id="4539d-111">Android – Nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="4539d-111">Android - Not supported</span></span>

## <a name="how-to-activate-lost-mode"></a><span data-ttu-id="4539d-112">So aktivieren Sie den Modus für verlorene Geräte</span><span class="sxs-lookup"><span data-stu-id="4539d-112">How to activate lost mode</span></span>

1. <span data-ttu-id="4539d-113">Melden Sie sich beim Azure-Portal an.</span><span class="sxs-lookup"><span data-stu-id="4539d-113">Sign into the Azure portal.</span></span>
2. <span data-ttu-id="4539d-114">Wählen Sie **Weitere Dienste** > **Überwachung und Verwaltung** > **Intune** aus.</span><span class="sxs-lookup"><span data-stu-id="4539d-114">Choose **More Services** > **Monitoring + Management** > **Intune**.</span></span>
3. <span data-ttu-id="4539d-115">Wählen Sie auf dem Blatt **Intune** die Option **Geräte** aus.</span><span class="sxs-lookup"><span data-stu-id="4539d-115">On the **Intune** blade, choose **Devices**.</span></span>
4. <span data-ttu-id="4539d-116">Wählen Sie auf dem Blatt **Geräte und Gruppen** die Option **Alle Geräte** aus.</span><span class="sxs-lookup"><span data-stu-id="4539d-116">On the **Devices and groups** blade, choose **All devices**.</span></span>
5. <span data-ttu-id="4539d-117">Wählen Sie aus der Liste der von Ihnen verwalteten Geräte ein iOS-Gerät aus, und wählen Sie dann die Remoteaktion **Modus für verlorene Geräte**.</span><span class="sxs-lookup"><span data-stu-id="4539d-117">From the list of devices you manage, choose an iOS device, and then choose the **Lost mode** remote action.</span></span>
6. <span data-ttu-id="4539d-118">Aktivieren Sie im Blatt **Modus für verlorene Geräte** den gleichnamigen Modus.</span><span class="sxs-lookup"><span data-stu-id="4539d-118">On the **Lost mode** blade, enable lost mode.</span></span> <span data-ttu-id="4539d-119">Geben Sie dann die Meldung ein, die angezeigt werden soll, und optional eine Telefonnummer.</span><span class="sxs-lookup"><span data-stu-id="4539d-119">Then, enter the message to be displayed, and optionally, a contact phone number.</span></span>
7. <span data-ttu-id="4539d-120">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="4539d-120">Click **OK**.</span></span>

<span data-ttu-id="4539d-121">Wenn Sie den Modus für verlorene Geräte aktivieren, kann das Gerät nicht mehr verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="4539d-121">When you enable lost mode, you block all use of the device.</span></span> <span data-ttu-id="4539d-122">Der Benutzer kann erst wieder auf das Gerät zugreifen, wenn Sie den Modus für verlorene Geräte wieder deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="4539d-122">The end user cannot access the device until you disable lost mode.</span></span> <span data-ttu-id="4539d-123">Bei aktiviertem Modus für verlorene Geräte können Sie mithilfe der Aktion **Gerät suchen** ermitteln, wo sich das Gerät befindet.</span><span class="sxs-lookup"><span data-stu-id="4539d-123">While lost mode is enabled, you can use the **Locate device** action to find out where the device is.</span></span>
<span data-ttu-id="4539d-124">Um den Modus für verlorene Geräte nutzen zu können, muss es sich bei dem Gerät um ein firmeneigenes iOS-Gerät im überwachten Modus handeln.</span><span class="sxs-lookup"><span data-stu-id="4539d-124">To use lost mode, the device must be a corporate-owned iOS device that is in supervised mode.</span></span>

## <a name="security-and-privacy-information-for-the-lost-mode-and-locate-device-actions"></a><span data-ttu-id="4539d-125">Sicherheit und Datenschutz im Zusammenhang mit dem Modus für verlorene Geräte und der Aktion „Gerät suchen“</span><span class="sxs-lookup"><span data-stu-id="4539d-125">Security and privacy information for the lost mode and locate device actions</span></span>
- <span data-ttu-id="4539d-126">Vor der Aktivierung dieser Aktion werden keinerlei Informationen zum Standort des Geräts an Intune gesendet.</span><span class="sxs-lookup"><span data-stu-id="4539d-126">No device location information is sent to Intune until you turn on this action.</span></span>
- <span data-ttu-id="4539d-127">Bei Verwendung der Aktion „Gerät suchen“ werden die Koordinaten des Geräts in Form von Breiten- und Längengrad an Intune gesendet und im Azure-Portal angezeigt.</span><span class="sxs-lookup"><span data-stu-id="4539d-127">When you use the locate device action, the latitude and longitude coordinates of the device are sent to Intune, and displayed in the Azure portal.</span></span>
- <span data-ttu-id="4539d-128">Die Daten werden 24 Stunden lang gespeichert und dann entfernt.</span><span class="sxs-lookup"><span data-stu-id="4539d-128">The data is stored for 24 hours, then removed.</span></span> <span data-ttu-id="4539d-129">Die Standortdaten können nicht manuell entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="4539d-129">You cannot manually remove the location data.</span></span>
- <span data-ttu-id="4539d-130">Die Standortdaten werden sowohl im gespeicherten Zustand als auch bei der Übertragung verschlüsselt.</span><span class="sxs-lookup"><span data-stu-id="4539d-130">Location data is encrypted, both while stored, and while being transmitted.</span></span>
- <span data-ttu-id="4539d-131">Es empfiehlt es sich, in der Nachricht für den Sperrbildschirm Informationen anzugeben, die der Person, die das Gerät findet, eine Rückgabe ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="4539d-131">We recommend that the message you enter to display on the lock screen includes information that helps someone who finds the device to return it.</span></span>

## <a name="next-steps"></a><span data-ttu-id="4539d-132">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="4539d-132">Next steps</span></span>

<span data-ttu-id="4539d-133">Um den Status der gerade ausgeführten Aktion anzuzeigen, wählen Sie auf dem Blatt **Geräte und Gruppen** die Option **Geräteaktionen** aus.</span><span class="sxs-lookup"><span data-stu-id="4539d-133">To see the status of the action you just took, on the **Devices and groups** blade, choose **Device Actions**.</span></span>

