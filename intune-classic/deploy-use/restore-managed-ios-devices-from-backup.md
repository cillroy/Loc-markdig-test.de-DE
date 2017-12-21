---
title: "Wiederherstellen von durch Intune verwalteten iOS-Geräten aus einer Sicherung"
description: "Stellen Sie einen Leitfaden für Endbenutzer bereit, der erklärt, wie sie ihre Geräte nach der Wiederherstellung aus einer Sicherung erneut registrieren können."
keywords: wiederherstellen, verwaltet, iOS
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 10/18/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a19e5612-8805-4bd7-a86a-b734bde293ae
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: esmich
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 7f451e5ce8ddd3943dcd043046889a2fe72dc256
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2017
---
# <a name="restore-intune-managed-ios-devices-from-backup"></a><span data-ttu-id="13fd2-104">Wiederherstellen von durch Intune verwalteten iOS-Geräten aus einer Sicherung</span><span class="sxs-lookup"><span data-stu-id="13fd2-104">Restore Intune managed iOS devices from backup</span></span>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="13fd2-105">Es werden Fälle auftreten, in denen Sie oder Ihre Benutzer ein iOS-Gerät aus einer Sicherung wiederherstellen müssen, z.B. wenn ein Benutzer ein neues Gerät erhält.</span><span class="sxs-lookup"><span data-stu-id="13fd2-105">There will be cases when you or your users will need to restore an iOS device from a backup, such as when a user gets a new device.</span></span> <span data-ttu-id="13fd2-106">In diesem Thema werden zusätzliche Schritte erläutert, die Sie möglicherweise durchführen müssen, um die Intune-Verwaltung nach dem Wiederherstellen eines Geräts einzurichten.</span><span class="sxs-lookup"><span data-stu-id="13fd2-106">This topic explains additional steps that you might have to take to set up Intune management after restoring the device.</span></span>

## <a name="restoring-backups-onto-the-same-device"></a><span data-ttu-id="13fd2-107">Wiederherstellen von Sicherungen auf dem gleichen Gerät</span><span class="sxs-lookup"><span data-stu-id="13fd2-107">Restoring backups onto the same device</span></span>

<span data-ttu-id="13fd2-108">Wenn die Sicherung auf dem gleichen Gerät wiederhergestellt wird, wird auch der Registrierungsstatus auf diesem Gerät wiederhergestellt.</span><span class="sxs-lookup"><span data-stu-id="13fd2-108">If the backup is being restored onto the same device, then the enrollment state on that device will also be restored.</span></span> <span data-ttu-id="13fd2-109">Es sind keine weiteren Aktionen erforderlich.</span><span class="sxs-lookup"><span data-stu-id="13fd2-109">There is no need for additional action.</span></span>

## <a name="restoring-backups-onto-different-devices"></a><span data-ttu-id="13fd2-110">Wiederherstellen von Sicherungen auf verschiedenen Geräten</span><span class="sxs-lookup"><span data-stu-id="13fd2-110">Restoring backups onto different devices</span></span>

<span data-ttu-id="13fd2-111">Wenn die Sicherung auf einem anderen Gerät wiederhergestellt wird, wird der Registrierungsstatus nicht automatisch auf dem neuen Gerät wiederhergestellt.</span><span class="sxs-lookup"><span data-stu-id="13fd2-111">If the backup is being restored onto a different device, then the enrollment state is not automatically restored on the new device.</span></span> <span data-ttu-id="13fd2-112">Benutzer müssen die Standardregistrierungsschritte in der Unternehmensportal-App Version 2.1.22 oder höher durchführen, um [ihr iOS-Gerät bei Intune zu registrieren](/intune-user-help/enroll-your-device-in-intune-ios).</span><span class="sxs-lookup"><span data-stu-id="13fd2-112">Users need to follow standard enrollment steps in the Company Portal app on app version 2.1.22 or later to [enroll their iOS device into Intune](/intune-user-help/enroll-your-device-in-intune-ios).</span></span>

> [!NOTE]
> <span data-ttu-id="13fd2-113">Wenn Sie für Ihre Benutzer Richtlinien für den bedingten Zugriff verwenden, können sie nicht auf die Unternehmens-E-Mails zugreifen, bis sie sich erneut registriert haben.</span><span class="sxs-lookup"><span data-stu-id="13fd2-113">If you’re targeting your end users with conditional access policies, they will not be able to access corporate email until after they re-enroll.</span></span>

> [!TIP]
> <span data-ttu-id="13fd2-114">Eine Beispielmitteilung für Ihre Benutzer könnte wie folgt lauten: Um sich auf Ihrem neuen Gerät zu registrieren, vergewissern Sie sich, dass die Version der Unternehmensportal-App Version 2.1.22 oder höher ist.</span><span class="sxs-lookup"><span data-stu-id="13fd2-114">An example communication for your users could be as follows: To enroll on your new device, make sure that the Company Portal app is on version 2.1.22 or later.</span></span> <span data-ttu-id="13fd2-115">Um die Version zu überprüfen, öffnen Sie die Unternehmensportal-App, tippen Sie auf die Schaltfläche „Menu“ (Menü) oben rechts und anschließend auf „About“ (Info).</span><span class="sxs-lookup"><span data-stu-id="13fd2-115">To check the version, open the Company Portal app, tap the Menu button in the upper right, and then tap About.</span></span> <span data-ttu-id="13fd2-116">Wenn Sie eine ältere Version installiert haben, beenden Sie die Unternehmensportal-App, und öffnen Sie den App Store.</span><span class="sxs-lookup"><span data-stu-id="13fd2-116">If you are on an earlier version, exit the Company Portal app and open the App Store.</span></span> <span data-ttu-id="13fd2-117">Tippen Sie in der unteren rechten Ecke auf die Schaltfläche „Updates“ und anschließend auf die Schaltfläche „Update“ (Aktualisieren) neben dem Element der Unternehmensportal-App in der Liste.</span><span class="sxs-lookup"><span data-stu-id="13fd2-117">Tap the Updates button in the bottom right corner, then tap the Update button next to the Company Portal item in the list.</span></span> <span data-ttu-id="13fd2-118">Sobald das Update abgeschlossen ist, starten Sie die Unternehmensportal-App, und [registrieren Sie Ihr iOS-Gerät bei Intune](/intune-user-help/enroll-your-device-in-intune-ios).</span><span class="sxs-lookup"><span data-stu-id="13fd2-118">Once the update completes, launch the Company Portal app and [enroll your iOS device into Intune](/intune-user-help/enroll-your-device-in-intune-ios).</span></span>

## <a name="resolving-known-issues-with-restores"></a><span data-ttu-id="13fd2-119">Lösen von bekannten Problemen beim Wiederherstellen</span><span class="sxs-lookup"><span data-stu-id="13fd2-119">Resolving known issues with restores</span></span>

<span data-ttu-id="13fd2-120">Benutzer können mit Problemen konfrontiert sein, wenn sie ihr Gerät wiederhergestellt und die Unternehmensportal-App gestartet haben, während sie noch Version 2.1.21 oder eine frühere Version der Unternehmensportal-App verwendeten.</span><span class="sxs-lookup"><span data-stu-id="13fd2-120">Users may experience some difficulty if they restored their device and launched the Company Portal app when they still had Company Portal version 2.1.21 or earlier.</span></span> <span data-ttu-id="13fd2-121">Diese Probleme können durch die entsprechenden Schritte für die Situation des Benutzers behoben werden.</span><span class="sxs-lookup"><span data-stu-id="13fd2-121">These difficulties can be addressed by taking the appropriate steps for the user’s situation.</span></span>

### <a name="for-users-who-will-only-use-their-new-device"></a><span data-ttu-id="13fd2-122">Für Benutzer, die nur ihr neues Gerät verwenden</span><span class="sxs-lookup"><span data-stu-id="13fd2-122">For users who will only use their new device</span></span>
<span data-ttu-id="13fd2-123">Starten Sie die Unternehmensportal-App, und heben Sie die Registrierung auf, indem Sie die Kachel des aktuellen Geräts auswählen und auf die Schaltfläche __Entfernen__ tippen.</span><span class="sxs-lookup"><span data-stu-id="13fd2-123">Launch the Company Portal app and unenroll by selecting the current device tile and tapping the __Remove__ button.</span></span> <span data-ttu-id="13fd2-124">Befolgen Sie nach dem Entfernen die Standardschritte zum [Registrieren eines iOS-Geräts bei Intune](/intune-user-help/enroll-your-device-in-intune-ios).</span><span class="sxs-lookup"><span data-stu-id="13fd2-124">After removing, follow the standard enrollment steps to [enroll an iOS device into Intune](/intune-user-help/enroll-your-device-in-intune-ios).</span></span>

### <a name="for-users-who-will-use-both-their-old-and-new-devices"></a><span data-ttu-id="13fd2-125">Für Benutzer, die sowohl ihre alten als auch ihre neuen Geräte verwenden</span><span class="sxs-lookup"><span data-stu-id="13fd2-125">For users who will use both their old and new devices</span></span>
<span data-ttu-id="13fd2-126">Löschen Sie die Cookies von Safari, indem Sie auf __Einstellungen__ > __Safari__ > __Verlauf und Websitedaten löschen__ tippen.</span><span class="sxs-lookup"><span data-stu-id="13fd2-126">Clear cookies from Safari by tapping __Settings__ > __Safari__ > __Clear History and Website Data__.</span></span> <span data-ttu-id="13fd2-127">Deinstallieren Sie die Unternehmensportal-App nach dem Löschen der Cookies, und installieren Sie diese erneut. Befolgen Sie anschließend die Standardschritte zum [Registrieren eines iOS-Geräts bei Intune](/intune-user-help/enroll-your-device-in-intune-ios).</span><span class="sxs-lookup"><span data-stu-id="13fd2-127">After clearing,  uninstall and reinstall the Company Portal app, then follow the standard enrollment steps to [enroll an iOS device into Intune](/intune-user-help/enroll-your-device-in-intune-ios).</span></span>
