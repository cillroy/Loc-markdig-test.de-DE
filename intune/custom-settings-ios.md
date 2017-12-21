---
title: "Benutzerdefinierte Intune-Einstellungen für iOS-Geräte"
titleSuffix: Azure portal
description: "Erfahren Sie etwas über die Einstellungen, die Sie in einem benutzerdefinierten iOS-Profil verwenden können.\""
keywords: 
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 05/04/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6da8caa8-65c2-4f47-842f-9570dcb1ac22
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 5786dd863e2c60a19b5472fa94e1924e4502afb0
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2017
---
# <a name="microsoft-intune-custom-settings-for-ios-devices"></a><span data-ttu-id="b66aa-103">Benutzerdefinierte Microsoft Intune-Einstellungen für iOS-Geräte</span><span class="sxs-lookup"><span data-stu-id="b66aa-103">Microsoft Intune custom settings for iOS devices</span></span>

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="b66aa-104">Verwenden Sie das benutzerdefinierte iOS-Profil von Microsoft Intune, um Einstellungen, die Sie mit dem [Apple Configurator-Tool](https://itunes.apple.com/app/apple-configurator-2/id1037126344?mt=12) erstellt haben, auf iOS-Geräten zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="b66aa-104">Use the Microsoft Intune iOS custom profile to assign settings that you created by using the [Apple Configurator tool](https://itunes.apple.com/app/apple-configurator-2/id1037126344?mt=12) to iOS devices.</span></span> <span data-ttu-id="b66aa-105">Mit diesem Tool können Sie zahlreiche Einstellungen zur Betriebssteuerung dieser Geräte erstellen und in ein Konfigurationsprofil exportieren.</span><span class="sxs-lookup"><span data-stu-id="b66aa-105">This tool lets you create many settings that control the operation of these devices and export them to a configuration profile.</span></span> <span data-ttu-id="b66aa-106">Sie können dieses Konfigurationsprofil anschließend in ein benutzerdefiniertes iOS-Profil von Intune importieren und die Einstellungen Benutzern und Geräten in Ihrer Organisation zuweisen.</span><span class="sxs-lookup"><span data-stu-id="b66aa-106">You can then import this configuration profile into an Intune iOS custom profile and assign the settings to users and devices in your organization.</span></span>

<span data-ttu-id="b66aa-107">Diese Funktion ermöglicht die Zuweisung von iOS-Einstellungen, die nicht mit anderen Intune-Profiltypen konfigurierbar sind.</span><span class="sxs-lookup"><span data-stu-id="b66aa-107">This capability allows you to assign iOS settings that are not configurable with other Intune profile types.</span></span>


1. <span data-ttu-id="b66aa-108">Anweisungen zu den ersten Schritten finden Sie unter [Konfigurieren von benutzerdefinierten Geräteeinstellungen in Microsoft Intune](custom-settings-configure.md).</span><span class="sxs-lookup"><span data-stu-id="b66aa-108">Use the instructions in [How to configure custom device settings in Microsoft Intune](custom-settings-configure.md) to get started.</span></span>
2. <span data-ttu-id="b66aa-109">Geben Sie auf dem Blatt **Profil erstellen** Folgendes an:</span><span class="sxs-lookup"><span data-stu-id="b66aa-109">On the **Create Profile** blade, specify the following:</span></span>

- <span data-ttu-id="b66aa-110">**Name des benutzerdefinierten Konfigurationsprofils:** Geben Sie einen Namen für die Richtlinie an, der auf dem Gerät und in Intune-Status angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="b66aa-110">**Custom configuration profile name** - Provide a name for the policy as it will be displayed on the device, and in Intune status.</span></span>
- <span data-ttu-id="b66aa-111">**Konfigurationsprofildatei:** Suchen Sie das mit Apple Configurator erstellte Konfigurationsprofil.</span><span class="sxs-lookup"><span data-stu-id="b66aa-111">**Configuration profile file** - Browse to the configuration profile that you created by using the Apple Configurator.</span></span>
<span data-ttu-id="b66aa-112">Stellen Sie sicher, dass die Einstellungen, die Sie aus dem Apple Configurator-Tool exportieren, mit der iOS-Version auf den Geräten kompatibel sind, denen Sie die benutzerdefinierte iOS-Richtlinie zuweisen.</span><span class="sxs-lookup"><span data-stu-id="b66aa-112">Ensure that the settings you export from the Apple Configurator tool are compatible with the version of iOS on the devices to which you assign the iOS custom policy.</span></span> <span data-ttu-id="b66aa-113">Um Informationen zum Korrigieren inkompatibler Einstellungen zu erhalten, suchen Sie auf der [Apple Developer-Website](https://developer.apple.com/) nach der **Referenz zu Konfigurationsprofilen** und der **Referenz zum Protokoll für die Verwaltung mobiler Geräte**.</span><span class="sxs-lookup"><span data-stu-id="b66aa-113">For information about how incompatible settings are resolved, search for **Configuration Profile Reference** and **Mobile Device Management Protocol Reference** on the [Apple Developer](https://developer.apple.com/) website.</span></span>

<span data-ttu-id="b66aa-114">Die importierte Datei wird im Bereich **Dateiinhalt** des Blatts angezeigt.</span><span class="sxs-lookup"><span data-stu-id="b66aa-114">The file you imported will be displayed in the **File contents** area of the blade.</span></span>
