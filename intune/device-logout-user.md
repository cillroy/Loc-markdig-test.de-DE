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
ms.openlocfilehash: f8907eff47b87fa0e4266c213b750357db172695
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2018
---
# <a name="logout-the-current-user-on-intune-managed-ios-devices"></a><span data-ttu-id="919a9-103">Abmelden des aktuellen Benutzers eines mit Intune verwalteten iOS-Geräts</span><span class="sxs-lookup"><span data-stu-id="919a9-103">Logout the current user on Intune-managed iOS devices</span></span>


[!INCLUDE [azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="919a9-104">Die Aktion **Aktiven Benutzer abmelden** meldet den aktuellen Benutzer auf einem freigegebenen iPad-Gerät ab, das für die Verwaltung der iOS Classroom-App mit einem [iOS-Bildungsprofil](education-settings-configure-ios.md) konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="919a9-104">The **Logout current user** action logs out the current user on a shared iPad device that is configured to manage the iOS Classroom app using an [iOS education profile](education-settings-configure-ios.md).</span></span> 

## <a name="supported-platforms"></a><span data-ttu-id="919a9-105">Unterstützte Plattformen</span><span class="sxs-lookup"><span data-stu-id="919a9-105">Supported platforms</span></span>

- <span data-ttu-id="919a9-106">Windows – Nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="919a9-106">Windows - Not supported</span></span>
- <span data-ttu-id="919a9-107">Windows Phone – Nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="919a9-107">Windows Phone - Not supported</span></span>
- <span data-ttu-id="919a9-108">iOS – Unterstützt auf iOS 9.3 und höher (nur freigegebene iPad-Geräte)</span><span class="sxs-lookup"><span data-stu-id="919a9-108">iOS - Supported on iOS 9.3 and later (shared iPad devices only)</span></span>
- <span data-ttu-id="919a9-109">macOS – Nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="919a9-109">macOS - Not supported</span></span>
- <span data-ttu-id="919a9-110">Android – Nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="919a9-110">Android - Not supported</span></span>

## <a name="how-to-logout-the-current-user"></a><span data-ttu-id="919a9-111">So melden Sie den aktuellen Benutzer ab</span><span class="sxs-lookup"><span data-stu-id="919a9-111">How to logout the current user</span></span>

1.  <span data-ttu-id="919a9-112">Melden Sie sich beim Azure-Portal an.</span><span class="sxs-lookup"><span data-stu-id="919a9-112">Sign into the Azure portal.</span></span>
2.  <span data-ttu-id="919a9-113">Wählen Sie **Weitere Dienste** > **Überwachung und Verwaltung** > **Intune** aus.</span><span class="sxs-lookup"><span data-stu-id="919a9-113">Choose **More Services** > **Monitoring + Management** > **Intune**.</span></span>
3.  <span data-ttu-id="919a9-114">Wählen Sie auf dem Blatt **Intune** die Option **Geräte** aus.</span><span class="sxs-lookup"><span data-stu-id="919a9-114">On the **Intune** blade, choose **Devices**.</span></span>
4.  <span data-ttu-id="919a9-115">Wählen Sie auf dem Blatt **Geräte und Gruppen** die Option **Alle Geräte** aus.</span><span class="sxs-lookup"><span data-stu-id="919a9-115">On the **Devices and groups** blade, choose **All devices**.</span></span>
5.  <span data-ttu-id="919a9-116">Wählen Sie aus der Liste der von Ihnen verwalteten Geräte ein iOS-Gerät und dann den Geräteremotevorgang **Aktiven Benutzer abmelden** aus.</span><span class="sxs-lookup"><span data-stu-id="919a9-116">From the list of devices you manage, choose an iOS device, and then choose the **Logout current user** device remote action.</span></span>

## <a name="next-steps"></a><span data-ttu-id="919a9-117">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="919a9-117">Next steps</span></span>

<span data-ttu-id="919a9-118">Um den Status der gerade ausgeführten Aktion anzuzeigen, wählen Sie auf dem Blatt **Geräte und Gruppen** die Option **Geräteaktionen** aus.</span><span class="sxs-lookup"><span data-stu-id="919a9-118">To see the status of the action you just took, on the **Devices and groups** blade, choose **Device Actions**.</span></span>
