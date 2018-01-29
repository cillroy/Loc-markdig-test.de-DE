---
title: "Auswählen der Methode zum Registrieren mobiler Geräte"
description: "Entscheiden Sie über die Registrierung mobiler Geräte in Intune durch Beantworten einiger einfacher Fragen"
keywords: 
author: NathBarn
ms.author: nathbarn
manager: angrobe
ms.date: 03/27/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 40262e47-1ab4-437d-8ca5-c89b5022f91f
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: dagerrit
ms.custom: intune-classic EXPIERIMENT
ms.openlocfilehash: 08d4d40241456c0941d5d9aa11e20827da6201b9
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2018
---
# <a name="choose-how-to-enroll-mobile-devices"></a><span data-ttu-id="ff0d8-103">Auswählen der Methode zum Registrieren mobiler Geräte</span><span class="sxs-lookup"><span data-stu-id="ff0d8-103">Choose how to enroll mobile devices</span></span>

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="ff0d8-104">Die Antworten auf die folgenden Fragen helfen Ihnen, die beste Registrierungsmethode für die von Ihnen verwalteten Geräte zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="ff0d8-104">Your answers to this series of questions will help determine the best enrollment method for the devices you manage.</span></span>

## <a name="how-will-you-manage-dedicated-corporate-owned-devices"></a><span data-ttu-id="ff0d8-105">**Wie werden dedizierte, unternehmenseigene Geräte verwaltet?**</span><span class="sxs-lookup"><span data-stu-id="ff0d8-105">**How will you manage dedicated, corporate-owned devices?**</span></span>

> [!div class="button"]
> [<span data-ttu-id="ff0d8-106">iOS DEP ></span><span class="sxs-lookup"><span data-stu-id="ff0d8-106">iOS DEP ></span></span>](/intune-classic/deploy-use/ios-device-enrollment-program-in-microsoft-intune)  
> [!div class="button"]
> [<span data-ttu-id="ff0d8-107">iOS-Setup-Assistent ></span><span class="sxs-lookup"><span data-stu-id="ff0d8-107">iOS Setup Assistant ></span></span>](/intune-classic/deploy-use/ios-setup-assistant-enrollment-in-microsoft-intune)
> [!div class="button"]
> [<span data-ttu-id="ff0d8-108">Tag mit IMEI ></span><span class="sxs-lookup"><span data-stu-id="ff0d8-108">Tag with IMEI ></span></span>](/intune-classic/deploy-use/specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers)

  <span data-ttu-id="ff0d8-109">Sie können unternehmenseigene Geräte mit dedizierten Benutzern wie folgt registrieren:</span><span class="sxs-lookup"><span data-stu-id="ff0d8-109">You can enroll corporate-owned devices with dedicated users in the following ways:</span></span>

  - <span data-ttu-id="ff0d8-110">**Apple-Geräteregistrierungsprogramm (DEP)** – Mit DEP erworbene oder verwaltete iOS-Geräte können mit einem Anmeldungsprofil angesprochen werden.</span><span class="sxs-lookup"><span data-stu-id="ff0d8-110">**Apple’s Device Enrollment Program (DEP)** - iOS devices purchased or managed with DEP can be targeted with an enrollment profile.</span></span> <span data-ttu-id="ff0d8-111">Wenn die Benutzer ihre Geräte zum ersten Mal einschalten, lädt das Gerät das DEP-Profil herunter und registriert sich bei Intune.</span><span class="sxs-lookup"><span data-stu-id="ff0d8-111">When users power on their devices for the first time, the device downloads the DEP profile and enrolls with Intune.</span></span>

  - <span data-ttu-id="ff0d8-112">**Apple Configurator auf einem Mac** – Apple Configurator ist eine Apple-Anwendung, die auf einem Mac-Computer ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="ff0d8-112">**Apple Configurator on a Mac** - Apple Configurator is an Apple application that runs on a Mac PC.</span></span> <span data-ttu-id="ff0d8-113">Sie können die iOS-Geräte über ein USB-Kabel mit dem Mac-Computer verbinden, um ein Registrierungsprofil auf dem Gerät zu installieren.</span><span class="sxs-lookup"><span data-stu-id="ff0d8-113">You can connect your iOS devices to the Mac with a USB cable to install an enrollment profile on the device.</span></span> <span data-ttu-id="ff0d8-114">Wenn Sie die Geräte zur Registrierung auf die Werkseinstellungen zurücksetzen können, verwenden Sie die Registrierung mithilfe des Setup-Assistenten.</span><span class="sxs-lookup"><span data-stu-id="ff0d8-114">If you can factory reset devices to enroll them use Setup Assistant enrollment.</span></span>

  - <span data-ttu-id="ff0d8-115">**Mit IMEI-Nummer markieren** – Durch das Importieren der IMEI-Nummern (International Mobile Equipment Identity) unternehmenseigener Geräte können Sie diese in Intune als unternehmenseigene Geräte markieren.</span><span class="sxs-lookup"><span data-stu-id="ff0d8-115">**Tag with IMEI number** - By importing the international mobile equipment identity (IMEI) numbers of company-owned devices you can tag them as company-owned devices in Intune.</span></span> <span data-ttu-id="ff0d8-116">Dies ist die einzige Möglichkeit, dedizierte Windows- und Android-Geräte („Einzelbenutzermodus“) als unternehmenseigen zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="ff0d8-116">This is the only way to identify dedicated ("single-user") Windows and Android devices as corporate-owned.</span></span> <span data-ttu-id="ff0d8-117">iOS-Geräte, die nicht über das Apple-Geräteregistrierungsprogramm oder den Apple Configurator registriert werden, können auch mit einer IMEI-Nummer gekennzeichnet werden.</span><span class="sxs-lookup"><span data-stu-id="ff0d8-117">iOS devices that won't be enrolled with Apple's device enrollment program or Apple Configurator can also be tagged with an IMEI number.</span></span> <span data-ttu-id="ff0d8-118">Nach dem Vordeklarieren von Geräten, damit diese als „unternehmenseigen“ markiert werden, können Sie die Geräte an Benutzer verteilen.</span><span class="sxs-lookup"><span data-stu-id="ff0d8-118">After predeclaring the device so it will be tagged as "corporate", you can distribute devices to users.</span></span> <span data-ttu-id="ff0d8-119">Anschließend können die Benutzer ihre Geräte als dedizierte Geräte registrieren, indem sie das Unternehmensportal installieren, um den Zugriff auf Unternehmensressourcen wie E-Mail, Apps und Daten zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="ff0d8-119">Users can then enroll their devices as a dedicated devices by installing the Company Portal to access company resources such as email, apps, and data.</span></span>

> [!div class="button"]
> [<span data-ttu-id="ff0d8-120">< Zurück</span><span class="sxs-lookup"><span data-stu-id="ff0d8-120">< Back</span></span>](choose-how-to-enroll-devices3.md)
