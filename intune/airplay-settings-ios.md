---
title: "AirPlay-Einstellungen für iOS-Geräte in Intune"
titlesuffix: Azure portal
description: "Erfahren Sie, wie Sie Intune verwenden können, um iOS-Geräte automatisch mit AirPlay-kompatiblen Geräten zu verbinden."
keywords: 
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 07/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 712a79fb-14ef-4f6b-aba5-1dfca900afd2
ms.reviewer: karanda
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 89c37ac145377a3e5430d31ae54ce3418c71559a
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2018
---
# <a name="intune-airplay-settings-for-ios-devices"></a><span data-ttu-id="2416f-103">AirPlay-Einstellungen für iOS-Geräte in Intune</span><span class="sxs-lookup"><span data-stu-id="2416f-103">Intune AirPlay settings for iOS devices</span></span>

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="2416f-104">Verwenden Sie diese Einstellungen, um von Ihnen verwaltete iOS-Geräte mit AirPlay-kompatiblen Geräten (z.B. Apple TV-Geräten) in Ihrem Netzwerk zu verbinden.</span><span class="sxs-lookup"><span data-stu-id="2416f-104">Use these settings to help connect iOS devices you manage to AirPlay compatible devices (like Apple TVs) on your network.</span></span>
<span data-ttu-id="2416f-105">Diese Funktion ermöglicht Folgendes:</span><span class="sxs-lookup"><span data-stu-id="2416f-105">With this capability you can:</span></span>

- <span data-ttu-id="2416f-106">**Konfigurieren einer Geräte- und Kennwortliste**: Damit können Benutzer automatisch eine Verbindung mit AirPlay-Geräten im Bereich herstellen.</span><span class="sxs-lookup"><span data-stu-id="2416f-106">**Configure a device and password list** - Let users automatically connect to AirPlay devices that are in range.</span></span> <span data-ttu-id="2416f-107">Stellen Sie ihnen den Namen und das Kennwort von AirPlay-Geräten bereit, damit sie dies nicht angeben müssen, wenn sie eine Verbindung herstellen.</span><span class="sxs-lookup"><span data-stu-id="2416f-107">Provision them with the name and password of AirPlay devices so that they don't need to supply it when they connect.</span></span>
- <span data-ttu-id="2416f-108">**Konfigurieren von zulässigen Zielen**: Konfigurieren Sie eine Liste mit AirPlay-Geräten (anhand der Geräte-ID).</span><span class="sxs-lookup"><span data-stu-id="2416f-108">**Configure allowed destinations** - Configure a list of AirPlay devices (by device ID).</span></span> <span data-ttu-id="2416f-109">Endbenutzer können nur die von Ihnen aufgelisteten Geräte sehen und nur mit diesen Geräten eine Verbindung herstellen (nur für überwachte Geräte).</span><span class="sxs-lookup"><span data-stu-id="2416f-109">End users can only see and connect to the devices you list (for supervised devices only).</span></span>

## <a name="get-started"></a><span data-ttu-id="2416f-110">Erste Schritte</span><span class="sxs-lookup"><span data-stu-id="2416f-110">Get started</span></span>

1. <span data-ttu-id="2416f-111">Wählen Sie auf dem Blatt **Gerätefunktionen** die Option **AirPlay** aus.</span><span class="sxs-lookup"><span data-stu-id="2416f-111">On the **Device features** blade, choose **AirPlay**.</span></span>
2. <span data-ttu-id="2416f-112">Wählen Sie auf dem Blatt **AirPlay** eine oder beide der folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="2416f-112">On the **AirPlay** blade, choose one or both of the following actions:</span></span>

## <a name="configure-a-device-and-password-list"></a><span data-ttu-id="2416f-113">Konfigurieren einer Geräte- und Kennwortliste</span><span class="sxs-lookup"><span data-stu-id="2416f-113">Configure a device and password list</span></span>

1. <span data-ttu-id="2416f-114">Geben Sie auf dem Blatt **Kennwörter** den **Gerätenamen** und das **Kennwort** eines AirPlay-Geräts ein, z.B. **Contoso Apple TV**.</span><span class="sxs-lookup"><span data-stu-id="2416f-114">On the **Passwords** blade, enter the **Device Name** and **Password** of an AirPlay device, for example **Contoso Apple TV**.</span></span>
2. <span data-ttu-id="2416f-115">Klicken Sie nach dem Eingeben der Gerätedetails auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="2416f-115">After entering the device details, click **Add**.</span></span> <span data-ttu-id="2416f-116">Das Gerät wird in der Liste **Gerätename** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="2416f-116">The device appears in the **Device Name** list.</span></span>
3. <span data-ttu-id="2416f-117">Fügen Sie nach Bedarf weitere Geräte hinzu.</span><span class="sxs-lookup"><span data-stu-id="2416f-117">Continue to add devices.</span></span> <span data-ttu-id="2416f-118">Wenn Sie fertig sind, wählen Sie **OK** aus.</span><span class="sxs-lookup"><span data-stu-id="2416f-118">When you are finished, choose **OK**.</span></span>


## <a name="configure-allowed-destinations"></a><span data-ttu-id="2416f-119">Konfigurieren von zulässigen Zielen</span><span class="sxs-lookup"><span data-stu-id="2416f-119">Configure allowed destinations</span></span>

1. <span data-ttu-id="2416f-120">Geben Sie auf dem Blatt **Zulässige Ziele (nur überwacht)** die **Geräte-ID** eines AirPlay-Geräts ein, z.B. „52:46:CD:51:83:4C“.</span><span class="sxs-lookup"><span data-stu-id="2416f-120">On the **Allowed destinations (supervised only)** blade, enter the **Device ID** of an AirPlay device, for example 52:46:CD:51:83:4C.</span></span>
2. <span data-ttu-id="2416f-121">Klicken Sie nach dem Eingeben der Geräte-ID auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="2416f-121">After entering the device ID, click **Add**.</span></span> <span data-ttu-id="2416f-122">Die ID wird in der Liste **Geräte-ID** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="2416f-122">The ID appears in the **Device ID** list.</span></span>
3. <span data-ttu-id="2416f-123">Fügen Sie nach Bedarf weitere Geräte hinzu.</span><span class="sxs-lookup"><span data-stu-id="2416f-123">Continue to add devices.</span></span> <span data-ttu-id="2416f-124">Wenn Sie fertig sind, wählen Sie **OK** aus.</span><span class="sxs-lookup"><span data-stu-id="2416f-124">When you are finished, choose **OK**.</span></span>

<span data-ttu-id="2416f-125">Sie können Geräte, Kennwörter und zulässige Ziele auch aus einer Datei mit durch Trennzeichen getrennten Werten (CSV-Datei) importieren.</span><span class="sxs-lookup"><span data-stu-id="2416f-125">You can also import device and passwords, and allowed destinations from a comma-separated values (csv) file.</span></span>


## <a name="next-steps"></a><span data-ttu-id="2416f-126">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="2416f-126">Next steps</span></span>

<span data-ttu-id="2416f-127">Sie können nun das Geräteprofil den von Ihnen ausgewählten Gruppen zuweisen.</span><span class="sxs-lookup"><span data-stu-id="2416f-127">You can now assign the device profile to the groups you choose.</span></span> <span data-ttu-id="2416f-128">Weitere Informationen finden Sie unter [Zuweisen von Geräteprofilen](device-profile-assign.md).</span><span class="sxs-lookup"><span data-stu-id="2416f-128">For details, see [How to assign device profiles](device-profile-assign.md).</span></span>

