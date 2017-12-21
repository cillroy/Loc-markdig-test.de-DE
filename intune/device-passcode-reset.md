---
title: "Zurücksetzen und Entfernen von Gerätekennungen mit Intune"
titlesuffix: Azure portal
description: "Erfahren Sie, wie Sie die Kennung von Geräten zurücksetzen oder entfernen, die Sie mit Intune verwalten."
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 11/06/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 47181d19-4049-4c7a-a8de-422206c4027e
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: dfa94d11f978bbe4d23b6672423c849e1f061986
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2017
---
# <a name="reset-and-remove-the-passcode-on-intune-managed-devices"></a><span data-ttu-id="05877-103">Zurücksetzen und Entfernen der Kennung auf von Intune verwalteten Geräten</span><span class="sxs-lookup"><span data-stu-id="05877-103">Reset and remove the passcode on Intune-managed devices</span></span>


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="05877-104">Die Begriffe *entfernen* und *zurücksetzen* sind im Kontext dieses Artikels austauschbar.</span><span class="sxs-lookup"><span data-stu-id="05877-104">The terms *remove* and *reset* are used interchangeably in this article.</span></span>

<span data-ttu-id="05877-105">Durch die Aktion **Kennung entfernen** wird eine neue Kennung für das Gerät generiert, die auf dem Blatt <*Gerätename*> **Übersicht** angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="05877-105">The **Remove passcode** action generates a new passcode for the device, which is displayed on the <*device name*> **Overview** blade.</span></span>

## <a name="supported-platforms"></a><span data-ttu-id="05877-106">Unterstützte Plattformen</span><span class="sxs-lookup"><span data-stu-id="05877-106">Supported platforms</span></span>

- <span data-ttu-id="05877-107">Windows – Nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="05877-107">Windows - Not supported</span></span>
- <span data-ttu-id="05877-108">Windows Phone – Unterstützt unter Windows Phone 8.1 bis Windows 10 Creators Update nicht in Azure AD eingebunden, Windows 10 Creators Update und höher</span><span class="sxs-lookup"><span data-stu-id="05877-108">Windows Phone - Supported on Windows Phone 8.1 to Windows 10 Creators update not Azure AD joined, Windows 10 Creators Update and later</span></span>
- <span data-ttu-id="05877-109">iOS – Unterstützt</span><span class="sxs-lookup"><span data-stu-id="05877-109">iOS - Supported</span></span>
- <span data-ttu-id="05877-110">macOS – Nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="05877-110">macOS - Not supported</span></span>
- <span data-ttu-id="05877-111">Android– Unterstützt für ältere Versionen vor Android 7.</span><span class="sxs-lookup"><span data-stu-id="05877-111">Android - Supported on Android versions earlier than Android 7.</span></span> <span data-ttu-id="05877-112">Android for Work wird nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="05877-112">Android for Work is not supported.</span></span>

## <a name="how-to-reset-a-passcode"></a><span data-ttu-id="05877-113">So setzen Sie eine Kennung zurück</span><span class="sxs-lookup"><span data-stu-id="05877-113">How to reset a passcode</span></span>

1. <span data-ttu-id="05877-114">Melden Sie sich beim Azure-Portal an.</span><span class="sxs-lookup"><span data-stu-id="05877-114">Sign into the Azure portal.</span></span>
2. <span data-ttu-id="05877-115">Wählen Sie **Weitere Dienste** > **Überwachung und Verwaltung** > **Intune** aus.</span><span class="sxs-lookup"><span data-stu-id="05877-115">Choose **More Services** > **Monitoring + Management** > **Intune**.</span></span>
3. <span data-ttu-id="05877-116">Wählen Sie auf dem Blatt **Intune** die Option **Geräte** aus.</span><span class="sxs-lookup"><span data-stu-id="05877-116">On the **Intune** blade, choose **Devices**.</span></span>
4. <span data-ttu-id="05877-117">Wählen Sie auf dem Blatt **Geräte und Gruppen** die Option **Alle Geräte** aus.</span><span class="sxs-lookup"><span data-stu-id="05877-117">On the **Devices and groups** blade, choose **All devices**.</span></span>
5. <span data-ttu-id="05877-118">Wählen Sie aus der Liste der verwalteten Geräte ein Gerät aus, und wählen Sie dann die Remotegeräteaktion **Kennung entfernen**.</span><span class="sxs-lookup"><span data-stu-id="05877-118">From the list of devices you manage, choose a device, and then choose the **Remove passcode** device remote action.</span></span>

## <a name="next-steps"></a><span data-ttu-id="05877-119">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="05877-119">Next steps</span></span>

<span data-ttu-id="05877-120">Um den Status der gerade ausgeführten Aktion anzuzeigen, wählen Sie auf dem Blatt **Geräte und Gruppen** die Option **Geräteaktionen** aus.</span><span class="sxs-lookup"><span data-stu-id="05877-120">To see the status of the action you just took, on the **Devices and groups** blade, choose **Device Actions**.</span></span>
