---
title: "Abmelden eines Benutzers eines iOS-Geräts mit Intune"
titlesuffix: Azure portal
description: "Erfahren Sie, wie Sie den aktuellen Benutzer eines iOS-Geräts mit Intune abmelden."
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 07/13/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 702bc46c-1a6f-4689-bd53-3b778a447baa
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 839815417a6b7ad54ea974fac3e885a0cd862fc8
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2017
---
# <a name="logout-the-current-user-on-intune-managed-ios-devices"></a><span data-ttu-id="b065d-103">Abmelden des aktuellen Benutzers eines mit Intune verwalteten iOS-Geräts</span><span class="sxs-lookup"><span data-stu-id="b065d-103">Logout the current user on Intune-managed iOS devices</span></span>


[!INCLUDE[azure_portal](./includes/azure_portal.md)]


<span data-ttu-id="b065d-104">Die Aktion **Aktiven Benutzer abmelden** meldet den aktuellen Benutzer auf einem freigegebenen iPad-Gerät ab, das für die Verwaltung der iOS Classroom-App mit einem [iOS-Bildungsprofil](education-settings-configure-ios.md) konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="b065d-104">The **Logout current user** action logs out the current user on a shared iPad device that is configured to manage the iOS Classroom app using an [iOS education profile](education-settings-configure-ios.md).</span></span> 

## <a name="supported-platforms"></a><span data-ttu-id="b065d-105">Unterstützte Plattformen</span><span class="sxs-lookup"><span data-stu-id="b065d-105">Supported platforms</span></span>

- <span data-ttu-id="b065d-106">Windows – Nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="b065d-106">Windows - Not supported</span></span>
- <span data-ttu-id="b065d-107">Windows Phone 8.1 – Nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="b065d-107">Windows Phone - Not supported</span></span>
- <span data-ttu-id="b065d-108">iOS – Unterstützt auf iOS 9.3 und höher (nur freigegebene iPad-Geräte)</span><span class="sxs-lookup"><span data-stu-id="b065d-108">iOS - Supported on iOS 9.3 and later (shared iPad devices only)</span></span>
- <span data-ttu-id="b065d-109">macOS – Nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="b065d-109">macOS - Not supported</span></span>
- <span data-ttu-id="b065d-110">Android – Nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="b065d-110">Android - Not supported</span></span>

## <a name="how-to-logout-the-current-user"></a><span data-ttu-id="b065d-111">So melden Sie den aktuellen Benutzer ab</span><span class="sxs-lookup"><span data-stu-id="b065d-111">How to logout the current user</span></span>

1.  <span data-ttu-id="b065d-112">Melden Sie sich beim Azure-Portal an.</span><span class="sxs-lookup"><span data-stu-id="b065d-112">Sign into the Azure portal.</span></span>
2.  <span data-ttu-id="b065d-113">Wählen Sie **Weitere Dienste** > **Überwachung und Verwaltung** > **Intune** aus.</span><span class="sxs-lookup"><span data-stu-id="b065d-113">Choose **More Services** > **Monitoring + Management** > **Intune**.</span></span>
3.  <span data-ttu-id="b065d-114">Wählen Sie auf dem Blatt **Intune** die Option **Geräte** aus.</span><span class="sxs-lookup"><span data-stu-id="b065d-114">On the **Intune** blade, choose **Devices**.</span></span>
4.  <span data-ttu-id="b065d-115">Wählen Sie auf dem Blatt **Geräte und Gruppen** die Option **Alle Geräte** aus.</span><span class="sxs-lookup"><span data-stu-id="b065d-115">On the **Devices and groups** blade, choose **All devices**.</span></span>
5.  <span data-ttu-id="b065d-116">Wählen Sie aus der Liste der von Ihnen verwalteten Geräte ein iOS-Gerät und dann den Geräteremotevorgang **Aktiven Benutzer abmelden** aus.</span><span class="sxs-lookup"><span data-stu-id="b065d-116">From the list of devices you manage, choose an iOS device, and then choose the **Logout current user** device remote action.</span></span>

## <a name="next-steps"></a><span data-ttu-id="b065d-117">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="b065d-117">Next steps</span></span>

<span data-ttu-id="b065d-118">Um den Status der gerade ausgeführten Aktion anzuzeigen, wählen Sie auf dem Blatt **Geräte und Gruppen** die Option **Geräteaktionen** aus.</span><span class="sxs-lookup"><span data-stu-id="b065d-118">To see the status of the action you just took, on the **Devices and groups** blade, choose **Device Actions**.</span></span>
