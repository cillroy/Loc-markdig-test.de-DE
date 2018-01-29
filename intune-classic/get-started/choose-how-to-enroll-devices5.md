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
ms.assetid: ed9250aa-e894-4eac-92b8-5f1a3748e255
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: dagerrit
ms.custom: intune-classic EXPIERIMENT
ms.openlocfilehash: cfbfae1a9e10c1e2d06939ba88a94d27b7057d5c
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2018
---
# <a name="choose-how-to-enroll-mobile-devices"></a><span data-ttu-id="30ac0-103">Auswählen der Methode zum Registrieren mobiler Geräte</span><span class="sxs-lookup"><span data-stu-id="30ac0-103">Choose how to enroll mobile devices</span></span>

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="30ac0-104">Die Antworten auf die folgenden Fragen helfen Ihnen, die beste Registrierungsmethode für die von Ihnen verwalteten Geräte zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="30ac0-104">Your answers to this series of questions will help determine the best enrollment method for the devices you manage.</span></span>

## <a name="how-will-you-manage-shared-ios-devices"></a><span data-ttu-id="30ac0-105">**Wie werden Sie freigegebene iOS-Geräte verwalten?**</span><span class="sxs-lookup"><span data-stu-id="30ac0-105">**How will you manage shared iOS devices?**</span></span>

> [!div class="button"]
> [<span data-ttu-id="30ac0-106">DEP-Registrierung von iOS-Geräten ></span><span class="sxs-lookup"><span data-stu-id="30ac0-106">iOS DEP Enrollment ></span></span>](/intune-classic/deploy-use/ios-device-enrollment-program-in-microsoft-intune)
> [!div class="button"]
> [<span data-ttu-id="30ac0-107">Direkte Registrierung von iOS-Geräten ></span><span class="sxs-lookup"><span data-stu-id="30ac0-107">iOS Direct enrollment ></span></span>](/intune-classic/deploy-use/ios-direct-enrollment-in-microsoft-intune)
> [!div class="button"]
> [<span data-ttu-id="30ac0-108">DEM-Registrierung ></span><span class="sxs-lookup"><span data-stu-id="30ac0-108">DEM enrollment ></span></span>](/intune-classic/deploy-use/enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune)

  - <span data-ttu-id="30ac0-109">**Apple-Geräteregistrierungsprogramm (DEP)** – Mit DEP erworbene oder verwaltete iOS-Geräte können mit einem Anmeldungsprofil angesprochen werden.</span><span class="sxs-lookup"><span data-stu-id="30ac0-109">**Apple’s Device Enrollment Program (DEP)** - iOS devices purchased or managed with DEP can be targeted with an enrollment profile.</span></span> <span data-ttu-id="30ac0-110">Wenn die Benutzer ihre Geräte zum ersten Mal einschalten, lädt das Gerät das DEP-Profil herunter und registriert sich beim Profil-DEP.</span><span class="sxs-lookup"><span data-stu-id="30ac0-110">When users power on their devices for the first time, the device downloads the DEP profile and enrolls with the profile DEP.</span></span>

  - <span data-ttu-id="30ac0-111">**Apple Configurator auf einem Mac** – Apple Configurator ist eine Apple-Anwendung, die auf einem Mac-Computer ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="30ac0-111">**Apple Configurator on a Mac** - Apple Configurator is an Apple application that runs on a Mac PC.</span></span> <span data-ttu-id="30ac0-112">Sie können die iOS-Geräte über ein USB-Kabel mit dem Mac-Computer verbinden, um ein Registrierungsprofil auf dem Gerät zu installieren.</span><span class="sxs-lookup"><span data-stu-id="30ac0-112">You can connect your iOS devices to the Mac with a USB cable to install an enrollment profile on the device.</span></span> <span data-ttu-id="30ac0-113">Wenn Sie die Geräte zur Registrierung auf die Werkseinstellungen zurücksetzen können, verwenden Sie die Registrierung mithilfe des Setup-Assistenten.</span><span class="sxs-lookup"><span data-stu-id="30ac0-113">If you can factory reset devices to enroll them use Setup Assistant enrollment.</span></span> <span data-ttu-id="30ac0-114">Falls Sie die Geräte nicht auf die Werkseinstellungen zurücksetzen möchten, verwenden Sie die direkte Registrierung.</span><span class="sxs-lookup"><span data-stu-id="30ac0-114">If you don't want to factory reset devices, use Direct enrollment.</span></span>

  - <span data-ttu-id="30ac0-115">**Geräteregistrierungs-Manager** – Mit dem Geräteregistrierungs-Manager (Device Enrollment Manager, DEM) von Intune können Manager oder Administratoren eine Vielzahl mobiler Geräte bei einem einzelnen Benutzerkonto registrieren.</span><span class="sxs-lookup"><span data-stu-id="30ac0-115">**Device Enrollment Manager** - Intune's device enrollment manager (DEM) allows a manager or administrator to enroll many mobile devices with a single user account.</span></span> <span data-ttu-id="30ac0-116">Diese Geräte dürfen keine Benutzeraffinität (d. h. dedizierte Benutzer) aufweisen und müssen registriert werden, indem sie installiert und bei der Unternehmensportal-App angemeldet werden.</span><span class="sxs-lookup"><span data-stu-id="30ac0-116">These devices cannot have user affinity (i.e. dedicated users) and must enroll by installing and signing in to the Company Portal app.</span></span>

> [!div class="button"]
> [<span data-ttu-id="30ac0-117">< Zurück</span><span class="sxs-lookup"><span data-stu-id="30ac0-117">< Back</span></span>](choose-how-to-enroll-devices3.md)
