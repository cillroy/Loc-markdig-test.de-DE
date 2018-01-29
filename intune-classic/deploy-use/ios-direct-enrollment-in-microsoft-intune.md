---
title: "Direkte Registrierung für iOS-Geräte"
description: "Verwenden Sie den Apple Configurator, um unternehmenseigene iOS-Geräte direkt mit einer vordefinierten Richtlinie zu registrieren, indem Sie sie über USB an einen Mac-Computer anschließen."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 01/29/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a692b90c-72ae-47d1-ba9c-67a2e2576cc2
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: e295aaa16828206685acf9a461eaa953478d772e
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2018
---
# <a name="directly-enroll-ios-devices-by-using-apple-configurator"></a><span data-ttu-id="61b79-103">Direkte Registrierung von iOS-Geräten mithilfe von Apple Configurator</span><span class="sxs-lookup"><span data-stu-id="61b79-103">Directly enroll iOS devices by using Apple Configurator</span></span>

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="61b79-104">Intune unterstützt die Registrierung unternehmenseigener iOS-Geräte mithilfe des Tools [Apple Configurator](http://go.microsoft.com/fwlink/?LinkId=518017), das auf einem Mac-Computer ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="61b79-104">Intune supports the enrollment of corporate-owned iOS devices by using the [Apple Configurator](http://go.microsoft.com/fwlink/?LinkId=518017) tool running on a Mac computer.</span></span> <span data-ttu-id="61b79-105">Dieser Prozess setzt das Gerät nicht auf die Werkseinstellungen zurück und registriert das Gerät mit einer vordefinierten Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="61b79-105">This process does not factory-reset the device and enrolls the device with a predefined policy.</span></span> <span data-ttu-id="61b79-106">Diese Methode ist für Geräte mit der Einstellung **Keine Benutzeraffinität** vorgesehen und erfordert eine USB-Verbindung des iOS-Geräts mit einem Mac-Computer, um die Registrierung beim Unternehmen einzurichten.</span><span class="sxs-lookup"><span data-stu-id="61b79-106">This method is for devices with **No user affinity** and requires you to USB-connect the iOS device to a Mac computer to set up corporate enrollment.</span></span>

<span data-ttu-id="61b79-107">Wenn Sie iOS-Geräte direkt registrieren, können Sie ein Gerät registrieren, ohne die Seriennummer des Geräts abrufen zu müssen.</span><span class="sxs-lookup"><span data-stu-id="61b79-107">When you're directly enrolling iOS devices, you can enroll a device without acquiring the device's serial number.</span></span> <span data-ttu-id="61b79-108">Sie können dem Gerät zu Identifikationszwecken auch einen Namen zuweisen, bevor Intune den Gerätenamen während der Registrierung erfasst.</span><span class="sxs-lookup"><span data-stu-id="61b79-108">You can also name the device for identification purposes before Intune captures the device name during enrollment.</span></span> <span data-ttu-id="61b79-109">Die Unternehmensportal-App wird für direkt registrierte Geräte nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="61b79-109">The Company Portal app is not supported for directly enrolled devices.</span></span> <span data-ttu-id="61b79-110">Diese Anleitung setzt voraus, dass Sie Apple Configurator 2.0 auf einem Mac-Computer verwenden.</span><span class="sxs-lookup"><span data-stu-id="61b79-110">This guidance assumes you are using Apple Configurator 2.0 on a Mac computer.</span></span>

>[!NOTE]
><span data-ttu-id="61b79-111">Diese Registrierungsmethode kann nicht mit dem [Geräteregistrierungs-Manager](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md) verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="61b79-111">This enrollment method can't be used with the [device enrollment manager](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md) method.</span></span>

1. <span data-ttu-id="61b79-112">Wenn Sie dies noch nicht getan haben, erstellen Sie ein Registrierungsprofil für iOS-Geräte, die über Apple Configurator registriert werden.</span><span class="sxs-lookup"><span data-stu-id="61b79-112">If you haven't already, create a device enrollment profile for iOS devices enrolled through Apple Configurator.</span></span> <span data-ttu-id="61b79-113">Ein Registrierungsprofil für Geräte definiert die Einstellungen für Geräte.</span><span class="sxs-lookup"><span data-stu-id="61b79-113">A device enrollment profile defines the settings applied to devices.</span></span>

   1. <span data-ttu-id="61b79-114">Wechseln Sie in der [Microsoft Intune-Verwaltungskonsole](https://manage.microsoft.com) zu **Richtlinie** &gt; **Unternehmensgeräteregistrierung**, und wählen Sie anschließend **Hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="61b79-114">In the [Microsoft Intune administration console](https://manage.microsoft.com) go to **Policy** &gt; **Corporate Device Enrollment**, and then choose **Add**.</span></span>

      ![Erstellen einer Profilseite für die Geräteregistrierung](../media/pol-sa-corp-enroll.png)

   2. <span data-ttu-id="61b79-116">Geben Sie die Details für die Geräteprofile ein:</span><span class="sxs-lookup"><span data-stu-id="61b79-116">Enter details for the device profiles:</span></span>

      - <span data-ttu-id="61b79-117">**Name** : Name des Geräteregistrierungsprofils.</span><span class="sxs-lookup"><span data-stu-id="61b79-117">**Name**: Name of the device enrollment profile.</span></span> <span data-ttu-id="61b79-118">Für Benutzer nicht sichtbar.</span><span class="sxs-lookup"><span data-stu-id="61b79-118">Not visible to users.</span></span>

      - <span data-ttu-id="61b79-119">**Beschreibung**: Beschreibung des Geräteregistrierungsprofils.</span><span class="sxs-lookup"><span data-stu-id="61b79-119">**Description**: Description of the device enrollment profile.</span></span> <span data-ttu-id="61b79-120">Für Benutzer nicht sichtbar.</span><span class="sxs-lookup"><span data-stu-id="61b79-120">Not visible to users.</span></span>

      - <span data-ttu-id="61b79-121">**Benutzerzuweisung**: Gibt an, wie Geräte registriert werden.</span><span class="sxs-lookup"><span data-stu-id="61b79-121">**User affiliation**: Specifies how devices are enrolled.</span></span> <span data-ttu-id="61b79-122">Wählen Sie für die direkte Registrierung **Keine Benutzeraffinität**aus.</span><span class="sxs-lookup"><span data-stu-id="61b79-122">For Direct Enrollment, choose **No user affinity**.</span></span>

      - <span data-ttu-id="61b79-123">**Gerätegruppe-Vorabzuweisung**: Alle Geräte mit diesem Profil gehören anfänglich zu dieser Gruppe.</span><span class="sxs-lookup"><span data-stu-id="61b79-123">**Device group pre-assignment**: All devices that have this profile will initially belong to this group.</span></span> <span data-ttu-id="61b79-124">Sie können die Geräte nach der Registrierung erneut zuweisen.</span><span class="sxs-lookup"><span data-stu-id="61b79-124">You can reassign devices after enrollment.</span></span>

        [!INCLUDE [groups deprecated](../includes/group-deprecation.md)]


   3. <span data-ttu-id="61b79-125">Wählen Sie **Profil speichern**, um das Profil hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="61b79-125">Choose **Save Profile** to add the profile.</span></span>

2. <span data-ttu-id="61b79-126">Exportieren Sie ein Profil als MOBILECONFIG-Datei zum Bereitstellen auf iOS-Geräten:</span><span class="sxs-lookup"><span data-stu-id="61b79-126">Export a profile as .mobileconfig to deploy to iOS devices:</span></span>

   1.   <span data-ttu-id="61b79-127">Wählen Sie das Geräteprofil aus, das Sie erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="61b79-127">Select the device profile that you created.</span></span>

   2.   <span data-ttu-id="61b79-128">Wählen Sie in der Taskleiste **Exportieren** aus.</span><span class="sxs-lookup"><span data-stu-id="61b79-128">Choose **Export** in the taskbar.</span></span>

   3.   <span data-ttu-id="61b79-129">Wählen Sie **Profil herunterladen**, und speichern Sie die heruntergeladene MOBILECONFIG-Datei.</span><span class="sxs-lookup"><span data-stu-id="61b79-129">Choose **Download profile** and save the downloaded .mobileconfig file.</span></span>

3. <span data-ttu-id="61b79-130">Übertragen Sie die Datei, indem Sie die heruntergeladene MOBILECONFIG-Datei auf einen Mac-Computer kopieren.</span><span class="sxs-lookup"><span data-stu-id="61b79-130">Transfer the file by copying the downloaded .mobileconfig file to a Mac computer.</span></span>
   > [!NOTE]
   > <span data-ttu-id="61b79-131">Die Anmeldungsprofil-URL ist ab dem Export zwei Wochen lang gültig.</span><span class="sxs-lookup"><span data-stu-id="61b79-131">The enrollment profile URL is valid for two weeks from when it is exported.</span></span> <span data-ttu-id="61b79-132">Nach zwei Wochen müssen Sie eine neue Anmeldungsprofil-URL zum Registrieren von iOS-Geräten mit dem Setup-Assistenten exportieren.</span><span class="sxs-lookup"><span data-stu-id="61b79-132">After two weeks, you must export a new enrollment profile URL to enroll iOS devices with Setup Assistant.</span></span>

4. <span data-ttu-id="61b79-133">Bereiten Sie das Gerät mit Apple Configurator vor.</span><span class="sxs-lookup"><span data-stu-id="61b79-133">Prepare the device with Apple Configurator.</span></span> <span data-ttu-id="61b79-134">iOS-Geräte werden mit dem Mac-Computer verbunden und für die Verwaltung mobiler Geräte registriert.</span><span class="sxs-lookup"><span data-stu-id="61b79-134">iOS devices are connected to the Mac computer and enrolled for mobile device management.</span></span>

   1.  <span data-ttu-id="61b79-135">Öffnen Sie auf einem Mac-Computer **Apple Configurator 2.0**.</span><span class="sxs-lookup"><span data-stu-id="61b79-135">On a Mac computer, open **Apple Configurator 2.0**.</span></span>

   2.  <span data-ttu-id="61b79-136">Verbinden Sie das iOS-Gerät mit dem Mac-Computer über ein USB-Kabel.</span><span class="sxs-lookup"><span data-stu-id="61b79-136">Connect the iOS device to the Mac computer with a USB cord.</span></span> <span data-ttu-id="61b79-137">Schließen **Fotos**, **iTunes** und andere Apps, die für das Gerät geöffnet werden, wenn das Gerät erkannt wird.</span><span class="sxs-lookup"><span data-stu-id="61b79-137">Close **Photos**, **iTunes**, and other apps that open for the device when the device is detected.</span></span>

   3.  <span data-ttu-id="61b79-138">Wählen Sie in Apple Configurator das verbundene iOS-Gerät und anschließend die Schaltfläche **Hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="61b79-138">In Apple Configurator, choose the connected iOS device, and then choose the **Add** button.</span></span> <span data-ttu-id="61b79-139">Optionen, die dem Gerät hinzugefügt werden können, werden in der Dropdownliste angezeigt.</span><span class="sxs-lookup"><span data-stu-id="61b79-139">Options that can be added to the device appear in the drop-down list.</span></span> <span data-ttu-id="61b79-140">Wählen Sie **Profile** aus.</span><span class="sxs-lookup"><span data-stu-id="61b79-140">Choose **Profiles**.</span></span>

   4.  <span data-ttu-id="61b79-141">Verwenden Sie die Dateiauswahl zum Auswählen der aus Intune exportierten MOBILECONFIG-Datei, und wählen Sie anschließend **Hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="61b79-141">Use the file picker to select the .mobileconfig file that you exported from Intune, and then choose **Add**.</span></span> <span data-ttu-id="61b79-142">Das Profil wird zum Gerät hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="61b79-142">The profile is added to the device.</span></span>  <span data-ttu-id="61b79-143">Wenn das Gerät **nicht überwacht** wird, muss der Installation auf dem Gerät zugestimmt werden.</span><span class="sxs-lookup"><span data-stu-id="61b79-143">If the device is **Unsupervised**, the installation will require acceptance on the device.</span></span>

5. <span data-ttu-id="61b79-144">Sie können das Profil nun auf dem iOS-Gerät installieren.</span><span class="sxs-lookup"><span data-stu-id="61b79-144">You are ready to install the profile on the iOS device.</span></span> <span data-ttu-id="61b79-145">Auf dem Gerät muss der Setup-Assistent ausgeführt worden sein, und es muss einsatzbereit sein.</span><span class="sxs-lookup"><span data-stu-id="61b79-145">The device must have already completed the Setup Assistant and be ready to use.</span></span> <span data-ttu-id="61b79-146">Wenn bei der Registrierung Apps bereitgestellt werden müssen, sollten Sie über eine Apple-ID verfügen, da Sie für App-Bereitstellungen mit einer Apple-ID beim App Store angemeldet sein müssen.</span><span class="sxs-lookup"><span data-stu-id="61b79-146">If enrollment entails app deployments, the device should have an Apple ID set up because the app deployments will require that you have an Apple ID signed in for the App Store.</span></span>

   1.  <span data-ttu-id="61b79-147">Entsperren Sie das iOS-Gerät.</span><span class="sxs-lookup"><span data-stu-id="61b79-147">Unlock the iOS device.</span></span>

   2.  <span data-ttu-id="61b79-148">Wählen Sie im Dialogfeld **Profil installieren** für das **Verwaltungsprofil** **Installieren** aus.</span><span class="sxs-lookup"><span data-stu-id="61b79-148">In the **Install profile** dialog box for **Management profile**,  choose **Install**.</span></span>

   3.  <span data-ttu-id="61b79-149">Geben Sie die **Gerätekennung** oder die **Apple-ID** ein, falls erforderlich.</span><span class="sxs-lookup"><span data-stu-id="61b79-149">Provide **Device Passcode** or **Apple ID**, if required.</span></span>

   4.  <span data-ttu-id="61b79-150">Akzeptieren Sie die **Warnung**, und wählen Sie **Installieren** aus.</span><span class="sxs-lookup"><span data-stu-id="61b79-150">Accept the **Warning**, and choose **Install**.</span></span>

   5.  <span data-ttu-id="61b79-151">Akzeptieren Sie die **Remotewarnung**, und wählen Sie **Vertrauen** aus.</span><span class="sxs-lookup"><span data-stu-id="61b79-151">Accept the **Remote Warning**, and choose **Trust**.</span></span>

   6.  <span data-ttu-id="61b79-152">Wenn mit der Meldung **Profil installiert** bestätigt wird, dass das Profil **installiert** wurde, wählen Sie **Fertig** aus.</span><span class="sxs-lookup"><span data-stu-id="61b79-152">When the **Profile Installed** box confirms the profile as **Installed**, choose **Done**.</span></span>

6. <span data-ttu-id="61b79-153">Öffnen Sie auf dem iOS-Gerät **Einstellungen**, und wechseln Sie zu **Allgemein** &gt; **Geräteverwaltung** &gt; **Management Profile** (Verwaltungsprofil).</span><span class="sxs-lookup"><span data-stu-id="61b79-153">On the iOS device, open **Settings** and go to **General** &gt; **Device Management** &gt; **Management Profile**.</span></span> <span data-ttu-id="61b79-154">Vergewissern Sie sich, dass die Profilinstallation aufgelistet ist, und überprüfen Sie die iOS-Richtlinieneinschränkungen und die installierten Apps.</span><span class="sxs-lookup"><span data-stu-id="61b79-154">Confirm that the profile installation is listed, and check the iOS policy restrictions and installed apps.</span></span> <span data-ttu-id="61b79-155">Es kann bis zu 10 Minuten dauern, bis Richtlinieneinschränkungen und Apps auf dem Gerät angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="61b79-155">Policy restrictions and apps might take up to 10 minutes to appear on the device.</span></span>

7. <span data-ttu-id="61b79-156">Verteilen von Geräten.</span><span class="sxs-lookup"><span data-stu-id="61b79-156">Distribute devices.</span></span> <span data-ttu-id="61b79-157">Das iOS-Gerät ist jetzt bei Intune registriert und wird verwaltet.</span><span class="sxs-lookup"><span data-stu-id="61b79-157">The iOS device is now enrolled with Intune and managed.</span></span>
