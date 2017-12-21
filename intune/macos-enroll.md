---
title: "Registrieren von macOS-Geräten in Intune"
titlesuffix: Azure portal
description: "Erfahren Sie, wie Sie macOS-Geräte in Intune registrieren."
keywords: 
author: arob98
ms.author: angrobe
nmanager: angrobe
ms.date: 10/30/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 46429114-2e26-4ba7-aa21-b2b1a5643e01
ms.reviewer: chrisbal
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 5f48ae6bdc64f694f33e6eac98a95419b24e6a95
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2017
---
# <a name="enroll-macos-devices-in-intune"></a><span data-ttu-id="47601-103">Registrieren von macOS-Geräten in Intune</span><span class="sxs-lookup"><span data-stu-id="47601-103">Enroll macOS devices in Intune</span></span>

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="47601-104">Intune ermöglicht es Ihnen, macOS-Geräte zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="47601-104">Intune enables you to manage macOS devices.</span></span> <span data-ttu-id="47601-105">Um die Geräteverwaltung zu aktivieren, müssen Ihre Benutzer ihre Geräte registrieren, indem sie auf die [Unternehmensportal-Website](http://portal.manage.microsoft.com) gehen und die Aufforderungen befolgen.</span><span class="sxs-lookup"><span data-stu-id="47601-105">To enable device management, your users must enroll their devices by going to the [Company Portal website](http://portal.manage.microsoft.com), and following the prompts.</span></span> <span data-ttu-id="47601-106">Sobald sich macOS-Geräte unter Verwaltung befinden, können Sie [benutzerdefinierte Einstellungen für macOS-Geräte erstellen](custom-settings-macos.md).</span><span class="sxs-lookup"><span data-stu-id="47601-106">Once macOS devices are under management, you can [create custom settings for macOS devices](custom-settings-macos.md).</span></span> <span data-ttu-id="47601-107">Weitere Funktionen sind in Kürze verfügbar.</span><span class="sxs-lookup"><span data-stu-id="47601-107">More capabilities are coming soon.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="47601-108">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="47601-108">Prerequisites</span></span>

<span data-ttu-id="47601-109">Die folgenden Voraussetzungen müssen vor dem Einrichten der Registrierung von macOS-Geräten erfüllt sein:</span><span class="sxs-lookup"><span data-stu-id="47601-109">Complete the following prerequisites before setting up macOS device enrollment:</span></span>

- [<span data-ttu-id="47601-110">Konfigurieren von Domänen</span><span class="sxs-lookup"><span data-stu-id="47601-110">Configure domains</span></span>](custom-domain-name-configure.md)
- [<span data-ttu-id="47601-111">Festlegen der MDM-Autorität</span><span class="sxs-lookup"><span data-stu-id="47601-111">Set the MDM Authority</span></span>](mdm-authority-set.md)
- [<span data-ttu-id="47601-112">Erstellen von Gruppen</span><span class="sxs-lookup"><span data-stu-id="47601-112">Create groups</span></span>](https://docs.microsoft.com/intune-classic/get-started/start-with-a-paid-subscription-to-microsoft-intune-step-5)
- [<span data-ttu-id="47601-113">Konfigurieren des Unternehmensportals</span><span class="sxs-lookup"><span data-stu-id="47601-113">Configure the Company Portal</span></span>](company-portal-app.md)
- <span data-ttu-id="47601-114">Zuweisen von Benutzerlizenzen im [Office 365-Portal](http://go.microsoft.com/fwlink/p/?LinkId=698854)</span><span class="sxs-lookup"><span data-stu-id="47601-114">Assign user licenses in the [Office 365 portal](http://go.microsoft.com/fwlink/p/?LinkId=698854)</span></span>
- [<span data-ttu-id="47601-115">Abrufen eines Apple-MDM-Push-Zertifikats</span><span class="sxs-lookup"><span data-stu-id="47601-115">Get an Apple MDM push certificate</span></span>](apple-mdm-push-certificate-get.md)

## <a name="set-up-macos-enrollment"></a><span data-ttu-id="47601-116">Einrichten der macOS-Registrierung</span><span class="sxs-lookup"><span data-stu-id="47601-116">Set up macOS enrollment</span></span>

<span data-ttu-id="47601-117">Standardmäßig erlaubt Intune bereits die Registrierung von macOS-Geräten.</span><span class="sxs-lookup"><span data-stu-id="47601-117">By default, Intune already allows enrollment of macOS devices.</span></span>

<span data-ttu-id="47601-118">Informationen zum Blockieren der Registrierung von macOS-Geräten finden Sie unter [Festlegen von Gerätetypbeschränkungen](enrollment-restrictions-set.md).</span><span class="sxs-lookup"><span data-stu-id="47601-118">To block macOS devices from enrollment, see [Set device type restrictions](enrollment-restrictions-set.md).</span></span>

## <a name="tell-your-users-how-to-enroll-their-devices-to-access-company-resources"></a><span data-ttu-id="47601-119">Kommunizieren der Geräteregistrierung für den Zugriff auf Unternehmensressourcen an die Benutzer</span><span class="sxs-lookup"><span data-stu-id="47601-119">Tell your users how to enroll their devices to access company resources</span></span>

<span data-ttu-id="47601-120">Ihre Endbenutzer müssen auf die [Unternehmensportal-Website](http://portal.manage.microsoft.com) gehen und den Aufforderungen folgen, um ihre Geräte zu registrieren.</span><span class="sxs-lookup"><span data-stu-id="47601-120">You'll need to tell your end users to go to the [Company Portal website](http://portal.manage.microsoft.com), and follow the prompts to enroll their devices.</span></span> <span data-ttu-id="47601-121">Sie können ihnen auch einen Link für Online-Registrierungsschritte senden: [Registrieren Ihres Mac OS-Geräts bei Intune](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-macos).</span><span class="sxs-lookup"><span data-stu-id="47601-121">You can also send them a link to online enrollment steps: [Enroll your macOS device in Intune](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-macos).</span></span>

<span data-ttu-id="47601-122">Informationen zu anderen Endbenutzeraufgaben finden Sie in den folgenden Artikeln:</span><span class="sxs-lookup"><span data-stu-id="47601-122">For information about other end-user tasks, see these articles:</span></span>

- [<span data-ttu-id="47601-123">Ressourcen zu Endbenutzerszenarios in Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="47601-123">Resources about the end-user experience with Microsoft Intune</span></span>](end-user-educate.md)
- [<span data-ttu-id="47601-124">Verwenden Ihres iOS- oder Mac OS-Geräts mit Intune</span><span class="sxs-lookup"><span data-stu-id="47601-124">Using your iOS or macOS device with Intune</span></span>](https://docs.microsoft.com/intune-user-help/using-your-ios-or-mac-os-x-device-with-intune)
