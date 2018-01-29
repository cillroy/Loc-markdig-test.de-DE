---
title: "Intune-Konfigurationseinstellungen für freigegebene iOS-Geräte"
titlesuffix: Azure portal
description: "Erfahren Sie mehr über die Intune-Einstellungen zur Anzeige von Informationen auf dem Sperrbildschirm von iOS-Geräten.\""
keywords: 
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 07/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f122e4ee-90e7-4b42-b801-8c1c7c0a5bf7
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 6090a78682629a47547bfb2eb916764f0e992e29
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2018
---
# <a name="shared-device-configuration-settings-to-display-messages-on-the-ios-device-lock-screen"></a><span data-ttu-id="1257d-103">Konfigurationseinstellungen für freigegebene Geräte zum Anzeigen von Nachrichten auf dem iOS-Geräte-Sperrbildschirm</span><span class="sxs-lookup"><span data-stu-id="1257d-103">Shared device configuration settings to display messages on the iOS device lock screen</span></span>

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="1257d-104">Mit Konfigurationseinstellungen für freigegebene Geräte können Sie optionalen Text angeben, der im Anmeldefenster und auf dem Sperrbildschirm angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="1257d-104">Shared device configuration settings let you specify optional text displayed on the login window and lock screen.</span></span> <span data-ttu-id="1257d-105">So können Sie z.B. eine „Wenn verloren, zurück an“-Nachricht und Bestandskennzeicheninformationen eingeben.</span><span class="sxs-lookup"><span data-stu-id="1257d-105">For example, you can enter an "If Lost, Return to" message and Asset Tag Information.</span></span> 

>[!IMPORTANT]
> <span data-ttu-id="1257d-106">Diese Funktion wird auf überwachten Geräten mit iOS 9.3 und höher unterstützt.</span><span class="sxs-lookup"><span data-stu-id="1257d-106">This capability is supported on supervised devices running iOS 9.3 and later.</span></span>

## <a name="create-shared-device-settings"></a><span data-ttu-id="1257d-107">Erstellen von freigegebenen Geräteeinstellungen</span><span class="sxs-lookup"><span data-stu-id="1257d-107">Create shared device settings</span></span>

1. <span data-ttu-id="1257d-108">Wählen Sie auf dem Blatt **Gerätefunktionen** die Option **Konfiguration freigegebener Geräte (nur überwacht)**.</span><span class="sxs-lookup"><span data-stu-id="1257d-108">On the **Device features** blade, choose **Shared Device Configuration (supervised only)**.</span></span>
2. <span data-ttu-id="1257d-109">Konfigurieren Sie auf dem Blatt **Konfiguration freigegebener Geräte (nur überwacht)** die folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="1257d-109">On the **Shared Device Configuration (supervised only)** blade, configure the following settings:</span></span>
    - <span data-ttu-id="1257d-110">**Bestandskennzeicheninformationen**: Geben Sie Informationen zum Bestandskennzeichen des Geräts ein.</span><span class="sxs-lookup"><span data-stu-id="1257d-110">**Asset tag information** - Enter information about the asset tag of the device.</span></span> <span data-ttu-id="1257d-111">Beispiel: **Im Besitz von Contoso Corp**. Die von Ihnen eingegebenen Informationen werden auf alle Geräte angewendet, denen Sie dieses Profil zuweisen.</span><span class="sxs-lookup"><span data-stu-id="1257d-111">For example: **Owned by Contoso Corp**. The information you enter is applied to all devices you assign this profile to.</span></span>
    - <span data-ttu-id="1257d-112">**Fußnote zum Sperrbildschirm**: Geben Sie einen Hinweis ein, der Ihnen helfen könnte, das Gerät zurückzubekommen, wenn es verloren geht oder gestohlen wird.</span><span class="sxs-lookup"><span data-stu-id="1257d-112">**Lock screen footnote** - If the device is lost or stolen, enter a note that might help get the device returned.</span></span> <span data-ttu-id="1257d-113">Beispiel: **Wenn Sie dieses Gerät gefunden haben, rufen Sie bitte „Nummer“ an**.</span><span class="sxs-lookup"><span data-stu-id="1257d-113">For example: **If found, call 'number'**.</span></span>
3. <span data-ttu-id="1257d-114">Wenn Sie fertig sind, klicken Sie auf **OK**, bis Sie zum Blatt **Profil erstellen** zurückkehren, und wählen Sie dann **Erstellen** aus.</span><span class="sxs-lookup"><span data-stu-id="1257d-114">When you are finished, choose **OK** until you return to the **Create Profile** blade, then choose **Create**.</span></span> 


## <a name="next-steps"></a><span data-ttu-id="1257d-115">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="1257d-115">Next steps</span></span>

<span data-ttu-id="1257d-116">Sie können nun das Geräteprofil den von Ihnen ausgewählten Gruppen zuweisen.</span><span class="sxs-lookup"><span data-stu-id="1257d-116">You can now assign the device profile to the groups you choose.</span></span> <span data-ttu-id="1257d-117">Weitere Informationen finden Sie unter [Zuweisen von Geräteprofilen](device-profile-assign.md).</span><span class="sxs-lookup"><span data-stu-id="1257d-117">For details, see [How to assign device profiles](device-profile-assign.md).</span></span>
