---
title: "App-Konfigurationsrichtlinien für Intune | Microsoft-Dokumentation"
titlesuffix: Azure portal
description: "Erfahren Sie, wie Sie App-Konfigurationsrichtlinien für Intune verwenden."
keywords: 
author: erikre
ms.author: erikre
manager: angrobe
ms.date: 10/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 834B4557-80A9-48C0-A72C-C98F6AF79708
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 727bf031a9e8a4c761d8d7b0c1d2737398a0fb7e
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2017
---
# <a name="app-configuration-policies-for-intune"></a><span data-ttu-id="4a020-103">App-Konfigurationsrichtlinien für Intune</span><span class="sxs-lookup"><span data-stu-id="4a020-103">App configuration policies for Intune</span></span>

<span data-ttu-id="4a020-104">Geben Sie Einstellungen dafür an, wenn Benutzer eine iOS- oder Android-App mit App-Konfigurationsrichtlinien in Microsoft Intune ausführen.</span><span class="sxs-lookup"><span data-stu-id="4a020-104">Supply settings when users run an iOS or Android app with app configuration policies in Microsoft Intune.</span></span> <span data-ttu-id="4a020-105">Beispielsweise kann eine App vom Benutzer Folgendes anfordern:</span><span class="sxs-lookup"><span data-stu-id="4a020-105">For example, an app might require users to specify:</span></span>

- <span data-ttu-id="4a020-106">Eine benutzerdefinierte Portnummer</span><span class="sxs-lookup"><span data-stu-id="4a020-106">A custom port number.</span></span>
- <span data-ttu-id="4a020-107">Spracheinstellungen</span><span class="sxs-lookup"><span data-stu-id="4a020-107">Language settings.</span></span>
- <span data-ttu-id="4a020-108">Sicherheitseinstellungen</span><span class="sxs-lookup"><span data-stu-id="4a020-108">Security settings.</span></span>
- <span data-ttu-id="4a020-109">Brandingeinstellungen, z. B. ein Unternehmenslogo</span><span class="sxs-lookup"><span data-stu-id="4a020-109">Branding settings such as a company logo.</span></span>

<span data-ttu-id="4a020-110">Wenn Benutzer diese Einstellungen nicht ordnungsgemäß eingeben, kann dies zur erhöhten Belastung Ihres Helpdesks führen und die Annahme der neuen Apps verlangsamen.</span><span class="sxs-lookup"><span data-stu-id="4a020-110">If users enter these settings incorrectly, it can increase the burden on your help desk and slow the adoption of new apps.</span></span>

<span data-ttu-id="4a020-111">Mit App-Konfigurationsrichtlinien können Sie diese Probleme beseitigen, da Sie diese Einstellungen in einer Richtlinie Benutzern zuweisen können, bevor diese die App ausführen.</span><span class="sxs-lookup"><span data-stu-id="4a020-111">App configuration policies can help you eliminate these problems by letting you assign these settings to users in a policy before they run the app.</span></span> <span data-ttu-id="4a020-112">Die Einstellungen werden dann automatisch bereitgestellt, und die Benutzer müssen keine weitere Aktion durchführen.</span><span class="sxs-lookup"><span data-stu-id="4a020-112">The settings are then supplied automatically, and users need to take no action.</span></span>

<span data-ttu-id="4a020-113">Sie weisen diese Richtlinien nicht direkt Benutzern und Geräten zu.</span><span class="sxs-lookup"><span data-stu-id="4a020-113">You do not assign these policies directly to users and devices.</span></span> <span data-ttu-id="4a020-114">Stattdessen verknüpfen Sie eine Richtlinie mit einer App und weisen dann die App zu.</span><span class="sxs-lookup"><span data-stu-id="4a020-114">Instead, you associate a policy with an app, and then assign the app.</span></span> <span data-ttu-id="4a020-115">Die Richtlinieneinstellungen werden immer dann verwendet, wenn die Anwendung danach sucht (in der Regel beim ersten Ausführen).</span><span class="sxs-lookup"><span data-stu-id="4a020-115">The policy settings are used whenever the app checks for them (typically, the first time it is run).</span></span>

<span data-ttu-id="4a020-116">Ihnen stehen zwei Optionen für das Verwenden der App-Konfigurationen mit Intune zur Verfügung:</span><span class="sxs-lookup"><span data-stu-id="4a020-116">You have two options for how to use app configurations with Intune:</span></span>
 - <span data-ttu-id="4a020-117">**Verwaltete Geräte**</span><span class="sxs-lookup"><span data-stu-id="4a020-117">**Managed devices**</span></span>  
   <span data-ttu-id="4a020-118">Das Gerät wird von Intune als MDM-Anbieter (mobile device manager, mobile Geräteverwaltung) verwaltet.</span><span class="sxs-lookup"><span data-stu-id="4a020-118">The device is managed by Intune as the mobile device management (MDM) provider.</span></span>
 - <span data-ttu-id="4a020-119">**Verwaltete Apps**</span><span class="sxs-lookup"><span data-stu-id="4a020-119">**Managed apps**</span></span>  
   <span data-ttu-id="4a020-120">Eine App wird ohne Geräteregistrierung verwaltet.</span><span class="sxs-lookup"><span data-stu-id="4a020-120">An app is managed without device enrollment.</span></span>

## <a name="apps-that-support-app-configuration"></a><span data-ttu-id="4a020-121">Apps, die die App-Konfiguration unterstützen</span><span class="sxs-lookup"><span data-stu-id="4a020-121">Apps that support app configuration</span></span>

<span data-ttu-id="4a020-122">Sie können App-Konfigurationsrichtlinien für Apps verwenden, die diese unterstützen.</span><span class="sxs-lookup"><span data-stu-id="4a020-122">You can use app configuration polices for apps that support it.</span></span> <span data-ttu-id="4a020-123">Für die Unterstützung der App-Konfiguration in Intune müssen Apps dafür geschrieben sein, die Verwendung von App-Konfigurationen zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="4a020-123">To support app configuration in Intune, apps must have been written to support the use of app configurations.</span></span> <span data-ttu-id="4a020-124">Wenden Sie sich für Details an Ihren App-Anbieter.</span><span class="sxs-lookup"><span data-stu-id="4a020-124">Consult your app vendor for details.</span></span>

<span data-ttu-id="4a020-125">Sie können Ihre branchenspezifischen Apps dafür vorbereiten, indem Sie entweder das Intune App SDK in die App integrieren oder die App nach der Entwicklung damit umschließen.</span><span class="sxs-lookup"><span data-stu-id="4a020-125">You can prepare your line-of-business apps by either incorporating the Intune App SDK into the app, or wrapping the app after it is developed.</span></span> <span data-ttu-id="4a020-126">Das für IOS und Android verfügbare Intune App SDK aktiviert Ihre App für Intune-App-Schutzrichtlinien.</span><span class="sxs-lookup"><span data-stu-id="4a020-126">The Intune App SDK, available for both iOS and Android, enables your app for Intune app protection policies.</span></span> <span data-ttu-id="4a020-127">Es zielt darauf ab, die vom App-Entwickler vorzunehmenden Codeänderungen zu minimieren.</span><span class="sxs-lookup"><span data-stu-id="4a020-127">It strives to minimize the amount of code changes required from the app developer.</span></span> <span data-ttu-id="4a020-128">Weitere Informationen finden Sie unter [Übersicht über das Intune App SDK](app-sdk.md).</span><span class="sxs-lookup"><span data-stu-id="4a020-128">For more information, see the [Intune App SDK overview](app-sdk.md).</span></span>

## <a name="graph-api-support-for-app-configuration"></a><span data-ttu-id="4a020-129">Graph-API-Unterstützung für die App-Konfiguration</span><span class="sxs-lookup"><span data-stu-id="4a020-129">Graph API support for app configuration</span></span>

<span data-ttu-id="4a020-130">Zusätzlich können Sie die Graph-API verwenden, um die App-Konfiguration abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="4a020-130">Additionally, you can use Graph API to accomplish app configuration tasks.</span></span> <span data-ttu-id="4a020-131">Weitere Informationen finden Sie in der [Graph-API-Referenz für die MAM-Zielkonfiguration](https://graph.microsoft.io/docs/api-reference/beta/api/intune_mam_targetedmanagedappconfiguration_create).</span><span class="sxs-lookup"><span data-stu-id="4a020-131">For details, see [Graph API Reference MAM Targeted Config](https://graph.microsoft.io/docs/api-reference/beta/api/intune_mam_targetedmanagedappconfiguration_create).</span></span>

## <a name="next-steps"></a><span data-ttu-id="4a020-132">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="4a020-132">Next steps</span></span>

### <a name="managed-devices"></a><span data-ttu-id="4a020-133">Verwaltete Geräte</span><span class="sxs-lookup"><span data-stu-id="4a020-133">Managed devices</span></span>

 - <span data-ttu-id="4a020-134">Erfahren Sie, wie Sie die App-Konfiguration mit Ihren iOS-Geräten verwenden.</span><span class="sxs-lookup"><span data-stu-id="4a020-134">Learn how to use app configuration with your iOS devices.</span></span>  <span data-ttu-id="4a020-135">Siehe [Add app configuration policies for managed iOS devices (Hinzufügen von App-Konfigurationsrichtlinien für verwaltete iOS-Geräte)](app-configuration-policies-use-ios.md).</span><span class="sxs-lookup"><span data-stu-id="4a020-135">See [ Add app configuration policies for managed iOS devices](app-configuration-policies-use-ios.md).</span></span>
 - <span data-ttu-id="4a020-136">Erfahren Sie, wie Sie die App-Konfiguration mit Ihren Android-Geräten verwenden.</span><span class="sxs-lookup"><span data-stu-id="4a020-136">Learn how to use app configuration with your Android devices.</span></span>  <span data-ttu-id="4a020-137">Siehe [Add app configuration policies for managed Android devices (Hinzufügen von App-Konfigurationsrichtlinien für verwaltete Android-Geräte)](app-configuration-policies-use-android.md).</span><span class="sxs-lookup"><span data-stu-id="4a020-137">See [Add app configuration policies for managed Android devices](app-configuration-policies-use-android.md).</span></span>

### <a name="managed-apps"></a><span data-ttu-id="4a020-138">Verwaltete Apps</span><span class="sxs-lookup"><span data-stu-id="4a020-138">Managed apps</span></span>

 - <span data-ttu-id="4a020-139">Erfahren Sie, wie Sie die App-Konfiguration mit verwalteten Geräten verwenden.</span><span class="sxs-lookup"><span data-stu-id="4a020-139">Learn how to use app configuration with managed apps.</span></span> <span data-ttu-id="4a020-140">Siehe [Add app configuration policies for managed apps without device enrollment (Hinzufügen von App-Konfigurationsrichtlinien für verwaltete Apps ohne Geräteregistrierung)](app-configuration-policies-managed-app.md).</span><span class="sxs-lookup"><span data-stu-id="4a020-140">See [Add app configuration policies for managed apps without device enrollment](app-configuration-policies-managed-app.md).</span></span>