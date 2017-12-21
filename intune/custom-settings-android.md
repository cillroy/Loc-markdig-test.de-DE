---
title: "Benutzerdefinierte Intune-Einstellungen für Android-Geräte"
titleSuffix: Azure portal
description: "Erfahren Sie etwas über die Einstellungen, die Sie in einem benutzerdefinierten Android-Profil verwenden können.\""
keywords: 
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 09/18/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 494b3892-916e-4b40-9b67-61adec889bdf
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 0bbc5c82c349c8a3d19eeb4433763b53e7485bc0
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2017
---
# <a name="custom-settings-for-android-devices-in-microsoft-intune"></a><span data-ttu-id="dea98-103">Benutzerdefinierte Einstellungen für Android-Geräte in Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="dea98-103">Custom settings for Android devices in Microsoft Intune</span></span>

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="dea98-104">Weisen Sie mithilfe des **benutzerdefinierten** Profils für Android von Microsoft Intune die OMA-URI-Einstellungen zu, um Features auf Android-Geräten zu steuern.</span><span class="sxs-lookup"><span data-stu-id="dea98-104">Use the Microsoft Intune Android **Custom** profile to assign OMA-URI settings that can be used to control features on Android devices.</span></span> <span data-ttu-id="dea98-105">Dies sind die Standardeinstellungen, die viele Hersteller von mobilen Geräten verwenden, um Gerätefunktionen zu steuern.</span><span class="sxs-lookup"><span data-stu-id="dea98-105">These are standard settings that many mobile device manufacturers use to control device features.</span></span>

<span data-ttu-id="dea98-106">Diese Funktion soll es Ihnen ermöglichen, die folgenden Android-Einstellungen zuzuweisen, die nicht mit Intune-Richtlinien konfigurierbar sind.</span><span class="sxs-lookup"><span data-stu-id="dea98-106">This capability is intended to allow you to assign the following Android settings that are not configurable with Intune policies:</span></span>

- [<span data-ttu-id="dea98-107">Verwenden eines benutzerdefinierten Geräteprofils von Microsoft Intune zum Erstellen eines WLAN-Profils über einen vorinstallierten Schlüssel</span><span class="sxs-lookup"><span data-stu-id="dea98-107">Use a Microsoft Intune custom device profile to create a Wi-Fi profile with a pre-shared key</span></span>](/intune/wi-fi-profile-shared-key)
- [<span data-ttu-id="dea98-108">Verwenden eines benutzerdefinierten Microsoft Intune-Profils zum Erstellen eines VPN-Profils pro App für Android-Geräte</span><span class="sxs-lookup"><span data-stu-id="dea98-108">Use a Microsoft Intune custom profile to create a per-app VPN profile for Android devices</span></span>](/intune/android-pulse-secure-per-app-vpn)
- [<span data-ttu-id="dea98-109">Verwenden von benutzerdefinierten Richtlinien zum Zulassen und Blockieren von Apps für Samsung KNOX Standardgeräte in Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="dea98-109">Use custom policies to allow and block apps for Samsung KNOX Standard devices in Microsoft Intune</span></span>](/intune/samsung-knox-apps-allow-block)

>[!IMPORTANT]
><span data-ttu-id="dea98-110">Nur die oben aufgeführten Einstellungen können derzeit von diesem Profiltyp konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="dea98-110">Only the settings listed above can currently be configured by this profile type.</span></span> <span data-ttu-id="dea98-111">Android-Geräte stellen keine vollständige Liste der OMA-URI-Einstellungen zur Verfügung, die Sie konfigurieren können.</span><span class="sxs-lookup"><span data-stu-id="dea98-111">Android devices do not expose a complete list of OMA-URI settings you can configure.</span></span> <span data-ttu-id="dea98-112">Wenn Sie weitere Einstellungen hinzugefügt haben möchten, fordern Sie diese auf der [Intune Uservoice-Website](https://microsoftintune.uservoice.com/forums/291681-ideas) an.</span><span class="sxs-lookup"><span data-stu-id="dea98-112">If you want to see further settings added, please request these on the [Intune Uservoice site](https://microsoftintune.uservoice.com/forums/291681-ideas).</span></span>

## <a name="custom-profile-settings-for-android-devices"></a><span data-ttu-id="dea98-113">Benutzerdefinierte Profileinstellungen für Android-Geräte</span><span class="sxs-lookup"><span data-stu-id="dea98-113">Custom profile settings for Android devices</span></span>

1. <span data-ttu-id="dea98-114">Anweisungen zu den ersten Schritten finden Sie unter [Konfigurieren von benutzerdefinierten Geräteeinstellungen in Microsoft Intune](custom-settings-configure.md).</span><span class="sxs-lookup"><span data-stu-id="dea98-114">Use the instructions in [How to configure custom device settings in Microsoft Intune](custom-settings-configure.md) to get started.</span></span>
2. <span data-ttu-id="dea98-115">Wählen Sie auf dem Blatt **Profil erstellen** die Option **Einstellungen** aus, um eine oder mehrere OMA-URI-Einstellungen hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="dea98-115">On the **Create Profile** blade, choose **Settings** to add one or more OMA-URI settings.</span></span>
3. <span data-ttu-id="dea98-116">Konfigurieren Sie auf dem Blatt **Zeile bearbeiten** die folgenden Werte für jede Einstellung:</span><span class="sxs-lookup"><span data-stu-id="dea98-116">On the **Edit Row** blade, configure the following values for each setting:</span></span>
    - <span data-ttu-id="dea98-117">**Name:** Geben Sie einen eindeutigen Namen für die OMA-URI-Einstellung ein, damit Sie sie in der Liste der Einstellungen einfacher identifizieren können.</span><span class="sxs-lookup"><span data-stu-id="dea98-117">**Name** - Enter a unique name for the OMA-URI setting to help you identify it in the list of settings.</span></span>
    - <span data-ttu-id="dea98-118">**Beschreibung:** Geben Sie eine Beschreibung ein, die eine Übersicht über die Einstellung bietet, und andere relevante Informationen, die Ihnen die Suche danach erleichtern.</span><span class="sxs-lookup"><span data-stu-id="dea98-118">**Description** - Provide a description that gives an overview of the setting and other relevant information to help you locate it.</span></span>
    - <span data-ttu-id="dea98-119">**Datentyp:** Wählen Sie den Datentyp aus, in dem Sie diese OMA-URI-Einstellung angeben.</span><span class="sxs-lookup"><span data-stu-id="dea98-119">**Data type** - Select the data type in which you will specify this OMA-URI setting.</span></span> <span data-ttu-id="dea98-120">Wählen Sie aus **Zeichenfolge**, **Zeichenfolge (XML)**, **Datum und Uhrzeit**, **ganze Zahl**, **Gleitkomma** oder **Boolesch** aus.</span><span class="sxs-lookup"><span data-stu-id="dea98-120">Choose from **String**, **String (XML)**, **Date and time**, **Integer**, **Floating point**, or **Boolean**.</span></span>
    - <span data-ttu-id="dea98-121">**OMA-URI:** Geben Sie den OMA-URI an, für den Sie eine Einstellung bereitstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="dea98-121">**OMA-URI** - Specify the OMA-URI you want to supply a setting for.</span></span>
    - <span data-ttu-id="dea98-122">**Wert:** Geben Sie den gewünschten Wert an, der dem von Ihnen eingegebenen OMA-URI zugeordnet werden soll.</span><span class="sxs-lookup"><span data-stu-id="dea98-122">**Value** - Enter the value you want to associate with the OMA-URI you entered.</span></span>
4. <span data-ttu-id="dea98-123">Klicken Sie abschließend auf **OK**, und fahren Sie bei Bedarf mit dem Hinzufügen weiterer Einstellungen fort.</span><span class="sxs-lookup"><span data-stu-id="dea98-123">Click **OK** once you are done, then continue to add more settings as required.</span></span>

## <a name="next-steps"></a><span data-ttu-id="dea98-124">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="dea98-124">Next steps</span></span>

<span data-ttu-id="dea98-125">Wenn Sie die Einstellungen abschließen, wird das Profil erstellt und auf dem Blatt mit der Profilliste angezeigt.</span><span class="sxs-lookup"><span data-stu-id="dea98-125">When you complete the settings, the profile will be created and appears on the profiles list blade.</span></span> <span data-ttu-id="dea98-126">Wenn Sie fortfahren und dieses Profil Gruppen zuweisen möchten, lesen Sie unter [Zuweisen von Geräteprofilen](device-profile-assign.md) nach.</span><span class="sxs-lookup"><span data-stu-id="dea98-126">If you want to go ahead and assign this profile to groups, see [How to assign device profiles](device-profile-assign.md).</span></span>




