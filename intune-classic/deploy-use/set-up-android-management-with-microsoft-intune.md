---
title: Einrichten der Android-Verwaltung
description: "Aktivieren Sie die Verwaltung mobiler Geräte (Mobile Device Management, MDM) für Android- und KNOX Standard-Geräte mit Microsoft Intune."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 03/20/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: dbe5cad1-3e0d-41a9-966b-738156089700
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: lacranda
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 6aeb5ca7ed25015eec7be0039280e9f4d2610df8
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2017
---
# <a name="set-up-android-device-management"></a><span data-ttu-id="1666e-103">Einrichten der Android-Geräteverwaltung</span><span class="sxs-lookup"><span data-stu-id="1666e-103">Set up Android device management</span></span>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="1666e-104">Als Intune-Administrator können Sie die Verwaltung von Android-Geräten, einschließlich Samsung KNOX Standard-Geräten, über das Unternehmensportal aktivieren.</span><span class="sxs-lookup"><span data-stu-id="1666e-104">As an Intune administrator, you can enable management of Android devices, including Samsung Knox Standard devices, from the Company Portal.</span></span> <span data-ttu-id="1666e-105">Benutzer können ihre Geräte anschließend über die Unternehmensportal-App registrieren, die in Google Play zur Verfügung steht.</span><span class="sxs-lookup"><span data-stu-id="1666e-105">Users can then enroll their devices using the Company Portal app that is available from Google Play.</span></span>

<span data-ttu-id="1666e-106">Standardmäßig können Android-Geräte in Intune registriert werden.</span><span class="sxs-lookup"><span data-stu-id="1666e-106">By default, Android devices are allowed to enroll in Intune.</span></span> <span data-ttu-id="1666e-107">Um Android-Geräte für die Registrierung zu blockieren, melden Sie sich mit Ihren Administratoranmeldeinformationen im [Microsoft Intune-Verwaltungsportal](https://manage.microsoft.com) an.</span><span class="sxs-lookup"><span data-stu-id="1666e-107">To block Android devices from enrolling, sign to the [Microsoft Intune admin portal](https://manage.microsoft.com) with your admin credentials.</span></span> <span data-ttu-id="1666e-108">Wählen Sie **Admin** (Administrator) > **Verwaltung mobiler Geräte** > **Registrierungsregeln** aus, und deaktivieren Sie das Kontrollkästchen **Android-Geräte zulassen**.</span><span class="sxs-lookup"><span data-stu-id="1666e-108">Choose **Admin** > **Mobile Device Management** > **Enrollment Rules** and then clear the **Allow Android devices** check box.</span></span>

1.  <span data-ttu-id="1666e-109">**Einrichten von Intune**</span><span class="sxs-lookup"><span data-stu-id="1666e-109">**Set up Intune**</span></span><br>
    <span data-ttu-id="1666e-110">Wenn nicht bereits geschehen, bereiten Sie die Verwaltung mobiler Geräte durch [Festlegen der Autorität für die Verwaltung mobiler Geräte](prerequisites-for-enrollment.md#step-2-set-mdm-authority) auf **Microsoft Intune** und Einrichten von MDM vor.</span><span class="sxs-lookup"><span data-stu-id="1666e-110">If you haven’t already, prepare for mobile device management by  [setting the mobile device management authority](prerequisites-for-enrollment.md#step-2-set-mdm-authority) as **Microsoft Intune** and setting up MDM.</span></span>

2.  <span data-ttu-id="1666e-111">**Android-Registrierung aktiviert**</span><span class="sxs-lookup"><span data-stu-id="1666e-111">**Android enrollment enabled**</span></span><br>
    <span data-ttu-id="1666e-112">Um die Registrierung mobiler Android-Geräte zu ermöglichen, sind keine weiteren Konfigurationen in der Intune-Konsole erforderlich.</span><span class="sxs-lookup"><span data-stu-id="1666e-112">No additional configurations in the Intune console are needed to enable Android mobile device enrollment.</span></span>

3.  <span data-ttu-id="1666e-113">**Benutzern erklären, wie sie ihre Geräte registrieren, um auf Unternehmensressourcen zugreifen zu können**</span><span class="sxs-lookup"><span data-stu-id="1666e-113">**Tell your users how to enroll their devices to get access to company resources.**</span></span>

    <span data-ttu-id="1666e-114">Registrierungsanleitungen für Endbenutzer finden Sie unter [Registrieren Ihres Android-Geräts bei Intune](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-android).</span><span class="sxs-lookup"><span data-stu-id="1666e-114">For end-user enrollment instructions, see [Enroll your Android device in Intune](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-android).</span></span> <span data-ttu-id="1666e-115">Im Laufe des Registrierungsprozesses werden Benutzer darüber informiert, was sie erwarten können und was IT-Administratoren auf ihren Geräten sehen können und was nicht.</span><span class="sxs-lookup"><span data-stu-id="1666e-115">The enrollment process tells users what they can expect, and what IT administrators can and can't see on their devices.</span></span>

    <span data-ttu-id="1666e-116">Informationen zu anderen Endbenutzeraufgaben finden Sie in den folgenden Artikeln:</span><span class="sxs-lookup"><span data-stu-id="1666e-116">For information about other end-user tasks, see these articles:</span></span>
  - [<span data-ttu-id="1666e-117">Ressourcen zu Endbenutzerszenarios in Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="1666e-117">Resources about the end-user experience with Microsoft Intune</span></span>](/intune/end-user-educate)
  - [<span data-ttu-id="1666e-118">Endbenutzer-Leitfaden für Android-Geräte</span><span class="sxs-lookup"><span data-stu-id="1666e-118">End user guidance for Android devices</span></span>](https://docs.microsoft.com/intune-user-help/using-your-android-device-with-intune)

<span data-ttu-id="1666e-119">Da der Google Play Store in China nicht verfügbar ist, müssen Android-Geräte das Unternehmensportal von chinesischen App-Marktplätzen beziehen.</span><span class="sxs-lookup"><span data-stu-id="1666e-119">Due to the absence of Google Play Store in China, Android devices must obtain the Company Portal from Chinese app marketplaces.</span></span> <span data-ttu-id="1666e-120">Die Unternehmensportal-App für Android wird in den folgenden Stores zum Download zur Verfügung stehen:</span><span class="sxs-lookup"><span data-stu-id="1666e-120">The Company Portal app for Android will be available for download on the following stores:</span></span>
* [<span data-ttu-id="1666e-121">Baidu</span><span class="sxs-lookup"><span data-stu-id="1666e-121">Baidu</span></span>](https://go.microsoft.com/fwlink/?linkid=836946)
* [<span data-ttu-id="1666e-122">Huawei</span><span class="sxs-lookup"><span data-stu-id="1666e-122">Huawei</span></span>](https://go.microsoft.com/fwlink/?linkid=836948)
* [<span data-ttu-id="1666e-123">Tencent</span><span class="sxs-lookup"><span data-stu-id="1666e-123">Tencent</span></span>](https://go.microsoft.com/fwlink/?linkid=836949)
* [<span data-ttu-id="1666e-124">Wandoujia</span><span class="sxs-lookup"><span data-stu-id="1666e-124">Wandoujia</span></span>](https://go.microsoft.com/fwlink/?linkid=836950)
* [<span data-ttu-id="1666e-125">Xiaomi</span><span class="sxs-lookup"><span data-stu-id="1666e-125">Xiaomi</span></span>](https://go.microsoft.com/fwlink/?linkid=836947)

<span data-ttu-id="1666e-126">Die Unternehmensportal-App für Android verwendet Google Play Services für die Kommunikation mit dem Microsoft Intune-Dienst.</span><span class="sxs-lookup"><span data-stu-id="1666e-126">The Company Portal app for Android uses Google Play Services to communicate with the Microsoft Intune service.</span></span> <span data-ttu-id="1666e-127">Da Google Play Services in China noch nicht verfügbar sind, kann die Ausführung der folgenden Aufgaben bis zu 8 Stunden dauern.</span><span class="sxs-lookup"><span data-stu-id="1666e-127">Since Google Play Services are not yet available in China, performing any of the following tasks can take up to 8 hours to complete.</span></span> 

|<span data-ttu-id="1666e-128">Intune-Administratorkonsole</span><span class="sxs-lookup"><span data-stu-id="1666e-128">Intune Admin Console</span></span>| <span data-ttu-id="1666e-129">Intune-Unternehmensportal-App für Android</span><span class="sxs-lookup"><span data-stu-id="1666e-129">Intune Company Portal app for Android</span></span> |<span data-ttu-id="1666e-130">Intune Unternehmensportalwebsite</span><span class="sxs-lookup"><span data-stu-id="1666e-130">Intune Company Portal Website</span></span>|   
|---|---|---|
|<span data-ttu-id="1666e-131">Vollständiges Zurücksetzen</span><span class="sxs-lookup"><span data-stu-id="1666e-131">Full wipe</span></span>| <span data-ttu-id="1666e-132">Entfernen eines Remotegeräts</span><span class="sxs-lookup"><span data-stu-id="1666e-132">Remove a remote device</span></span>| <span data-ttu-id="1666e-133">Entfernen eines Geräts (lokal und remote)</span><span class="sxs-lookup"><span data-stu-id="1666e-133">Remove device (local and remote)</span></span>|
|<span data-ttu-id="1666e-134">Selektives Zurücksetzen</span><span class="sxs-lookup"><span data-stu-id="1666e-134">Selective wipe</span></span>| <span data-ttu-id="1666e-135">Zurücksetzen eines Geräts</span><span class="sxs-lookup"><span data-stu-id="1666e-135">Reset device</span></span>| <span data-ttu-id="1666e-136">Zurücksetzen eines Geräts</span><span class="sxs-lookup"><span data-stu-id="1666e-136">Reset device</span></span>|
|<span data-ttu-id="1666e-137">Bereitstellung neuer oder aktualisierter Apps</span><span class="sxs-lookup"><span data-stu-id="1666e-137">New or updated app deployments</span></span>| <span data-ttu-id="1666e-138">Installieren von verfügbaren Branchen-Apps</span><span class="sxs-lookup"><span data-stu-id="1666e-138">Install available line-of-business apps</span></span>| <span data-ttu-id="1666e-139">Zurücksetzen der Gerätekennung</span><span class="sxs-lookup"><span data-stu-id="1666e-139">Device passcode reset</span></span>|
|<span data-ttu-id="1666e-140">Remotesperre</span><span class="sxs-lookup"><span data-stu-id="1666e-140">Remote lock</span></span>|||
|<span data-ttu-id="1666e-141">Zurücksetzen der Kennung</span><span class="sxs-lookup"><span data-stu-id="1666e-141">Passcode reset</span></span>|||

### <a name="see-also"></a><span data-ttu-id="1666e-142">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="1666e-142">See also</span></span>
[<span data-ttu-id="1666e-143">Voraussetzungen für die Registrierung von Geräten in Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="1666e-143">Prerequisites to enrolling devices in Microsoft Intune</span></span>](prerequisites-for-enrollment.md)
