---
title: "Entfernen eines Benutzers von einem iOS-Gerät mit Intune"
titlesuffix: Azure portal
description: "Erfahren Sie, wie Sie einen Benutzer von einem gemeinsam genutzten iOS-Gerät mit Intune entfernen."
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 08/09/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 2ea5941c-a69b-4e1c-b42c-a1fc0c3a7de7
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 5740a508a1a2d97de6eb0eada3398c4632980920
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2018
---
# <a name="remove-a-user-from-a-shared-ios-device-with-intune"></a><span data-ttu-id="a1ae2-103">Entfernen eines Benutzers von einem gemeinsam genutzten iOS-Gerät mit Intune</span><span class="sxs-lookup"><span data-stu-id="a1ae2-103">Remove a user from a shared iOS device with Intune</span></span>


[!INCLUDE [azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="a1ae2-104">Die Aktion **Benutzer entfernen** löscht den von Ihnen ausgewählten Benutzer aus dem lokalen Cache auf einem freigegebenen iPad-Gerät ab, das für die Verwaltung der iOS Classroom-App mit einem [iOS-Bildungsprofil](education-settings-configure-ios.md) konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="a1ae2-104">The **Remove user** action deletes a user you choose from the local cache on a shared iPad device that has been configured to manage the iOS Classroom app with an [iOS education profile](education-settings-configure-ios.md).</span></span> 

## <a name="supported-platforms"></a><span data-ttu-id="a1ae2-105">Unterstützte Plattformen</span><span class="sxs-lookup"><span data-stu-id="a1ae2-105">Supported platforms</span></span>

- <span data-ttu-id="a1ae2-106">Windows – Nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="a1ae2-106">Windows - Not supported</span></span>
- <span data-ttu-id="a1ae2-107">Windows Phone – Nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="a1ae2-107">Windows Phone - Not supported</span></span>
- <span data-ttu-id="a1ae2-108">iOS – Unterstützt auf iOS 9.3 und höher (nur freigegebene iPad-Geräte)</span><span class="sxs-lookup"><span data-stu-id="a1ae2-108">iOS - Supported on iOS 9.3 and later (shared iPad devices only)</span></span>
- <span data-ttu-id="a1ae2-109">macOS – Nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="a1ae2-109">macOS - Not supported</span></span>
- <span data-ttu-id="a1ae2-110">Android – Nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="a1ae2-110">Android - Not supported</span></span>

## <a name="how-to-remove-a-user"></a><span data-ttu-id="a1ae2-111">So entfernen Sie einen Benutzer</span><span class="sxs-lookup"><span data-stu-id="a1ae2-111">How to remove a user</span></span>

1. <span data-ttu-id="a1ae2-112">Melden Sie sich beim Azure-Portal an.</span><span class="sxs-lookup"><span data-stu-id="a1ae2-112">Sign into the Azure portal.</span></span>
2. <span data-ttu-id="a1ae2-113">Wählen Sie **Weitere Dienste** > **Überwachung und Verwaltung** > **Intune** aus.</span><span class="sxs-lookup"><span data-stu-id="a1ae2-113">Choose **More Services** > **Monitoring + Management** > **Intune**.</span></span>
3. <span data-ttu-id="a1ae2-114">Wählen Sie auf dem Blatt **Intune** die Option **Geräte** aus.</span><span class="sxs-lookup"><span data-stu-id="a1ae2-114">On the **Intune** blade, choose **Devices**.</span></span>
4. <span data-ttu-id="a1ae2-115">Wählen Sie auf dem Blatt **Geräte** die Option **Alle Geräte** aus.</span><span class="sxs-lookup"><span data-stu-id="a1ae2-115">On the **Devices** blade, choose **All devices**.</span></span>
5. <span data-ttu-id="a1ae2-116">Wählen Sie aus der Liste der von Ihnen verwalteten Geräten ein iOS-Gerät aus.</span><span class="sxs-lookup"><span data-stu-id="a1ae2-116">From the list of devices you manage, choose an iOS device.</span></span>
6. <span data-ttu-id="a1ae2-117">Wählen Sie auf dem Blatt für dieses Gerät **Benutzer** aus.</span><span class="sxs-lookup"><span data-stu-id="a1ae2-117">On the blade for that device, choose **Users**.</span></span>
7. <span data-ttu-id="a1ae2-118">Klicken Sie über die Liste mit der rechten Maustaste auf den Benutzer, den Sie entfernen möchten, und wählen Sie dann **Benutzer entfernen** aus.</span><span class="sxs-lookup"><span data-stu-id="a1ae2-118">From the list, right-click the user you want to remove, and then choose **Remove user**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="a1ae2-119">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="a1ae2-119">Next steps</span></span>

<span data-ttu-id="a1ae2-120">Um den Status der gerade ausgeführten Aktion anzuzeigen, wählen Sie auf dem Blatt **Geräte und Gruppen** die Option **Geräteaktionen** aus.</span><span class="sxs-lookup"><span data-stu-id="a1ae2-120">To see the status of the action you just took, on the **Devices and groups** blade, choose **Device Actions**.</span></span>
