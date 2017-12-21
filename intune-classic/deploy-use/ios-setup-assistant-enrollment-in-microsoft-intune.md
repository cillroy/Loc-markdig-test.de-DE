---
title: "Registrieren von iOS-Geräten mithilfe des Setup-Assistenten"
description: "Registrieren von unternehmenseigenen iOS-Geräten mithilfe des Apple Configurator-Tools, um die Geräte auf die Werkseinstellungen zurückzusetzen und für die Ausführung des Setup-Assistenten vorzubereiten."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 03/28/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 46e5b027-4280-4809-b45f-651a6ab6d0cd
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: e8dbcfc2f4bb521e3a48e6eb76a66b815fc45d61
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2017
---
# <a name="enroll-ios-devices-with-apple-configurator-by-using-setup-assistant"></a><span data-ttu-id="f7839-103">Registrieren von iOS-Geräten mithilfe von Apple Configurator und Setup-Assistent</span><span class="sxs-lookup"><span data-stu-id="f7839-103">Enroll iOS devices with Apple Configurator by using Setup Assistant</span></span>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="f7839-104">Intune unterstützt die Registrierung unternehmenseigener iOS-Geräte mithilfe des Tools [Apple Configurator](http://go.microsoft.com/fwlink/?LinkId=518017), das auf einem Mac-Computer ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="f7839-104">Intune supports the enrollment of corporate-owned iOS devices using [Apple Configurator](http://go.microsoft.com/fwlink/?LinkId=518017) running on a Mac computer.</span></span> <span data-ttu-id="f7839-105">Dieser Prozess setzt das Gerät auf die Werkseinstellungen zurück und bereitet es auf die Ausführung des Setup-Assistenten vor, um die Unternehmensrichtlinien für den neuen Benutzer des Geräts zu installieren.</span><span class="sxs-lookup"><span data-stu-id="f7839-105">This process resets the device to factory settings and prepares it to run Setup Assistant, installing the company's policies for the device’s new user.</span></span>

>[!NOTE]
><span data-ttu-id="f7839-106">Diese Registrierungsmethode kann nicht mit dem [Geräteregistrierungs-Manager](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md) verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="f7839-106">This enrollment method can't be used with the [device enrollment manager](enroll-corporate-owned-devices-with-the-device-enrollment-manager-in-microsoft-intune.md) method.</span></span>

<span data-ttu-id="f7839-107">Mit Apple Configurator können Sie ein iOS-Gerät auf die Werkseinstellungen zurücksetzen und auf die Einrichtung für den neuen Benutzer des Geräts vorbereiten.</span><span class="sxs-lookup"><span data-stu-id="f7839-107">Using Apple Configurator, you can reset an iOS device to factory settings and prepare it to be set up for the device’s new user.</span></span> <span data-ttu-id="f7839-108">Bei dieser Methode muss das iOS-Gerät über USB mit einem Mac-Computer verbunden werden, um die Registrierung beim Unternehmen einzurichten. Vorausgesetzt wird die Verwendung von Apple Configurator 2.0.</span><span class="sxs-lookup"><span data-stu-id="f7839-108">This method requires you to connect the iOS device to a Mac computer via USB to set up corporate enrollment, and it assumes you are using Apple Configurator 2.0.</span></span> <span data-ttu-id="f7839-109">Bei den meisten Szenarien ist es erforderlich, dass die auf das iOS-Gerät angewendete Richtlinie **Benutzeraffinität** einschließt, um das Intune-Unternehmensportal zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="f7839-109">Most scenarios require that the policy applied to the iOS device include **user affinity** to enable the Intune Company Portal app.</span></span>

## <a name="prerequisites-for-enrolling-ios-devices-by-using-apple-configurator-with-setup-assistant"></a><span data-ttu-id="f7839-110">Voraussetzungen für die Anmeldung von iOS-Geräten mithilfe von Apple Configurator mit dem Setup-Assistenten</span><span class="sxs-lookup"><span data-stu-id="f7839-110">Prerequisites for enrolling iOS devices by using Apple Configurator with Setup Assistant</span></span>

- [<span data-ttu-id="f7839-111">Installieren eines APNS-Zertifikats</span><span class="sxs-lookup"><span data-stu-id="f7839-111">Install an APNs certificate</span></span>](set-up-ios-and-mac-management-with-microsoft-intune.md)

- <span data-ttu-id="f7839-112">Stellen Sie sicher, dass Sie über physischen Zugriff auf iOS-Geräte verfügen&mdash;Geräte müssen auf die Werkseinstellungen zurückgesetzt sein und dürfen keinen Kennwortschutz aufweisen</span><span class="sxs-lookup"><span data-stu-id="f7839-112">Ensure that you have physical access to iOS devices&mdash;devices must be reset to factory settings without password protection</span></span>

- <span data-ttu-id="f7839-113">Rufen Sie die Geräteseriennummern ab&mdash; siehe [Abrufen einer iOS-Seriennummer](https://support.apple.com/HT204308)</span><span class="sxs-lookup"><span data-stu-id="f7839-113">Get device serial numbers&mdash;see [How to get an iOS serial number](https://support.apple.com/HT204308)</span></span>

- <span data-ttu-id="f7839-114">Haben Sie ein USB-Verbindungskabel zur Hand</span><span class="sxs-lookup"><span data-stu-id="f7839-114">Have USB connection cables on hand</span></span>

- <span data-ttu-id="f7839-115">Verfügen Sie über einen Mac-Computer mit [Apple Configurator 2.0](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12)</span><span class="sxs-lookup"><span data-stu-id="f7839-115">Have a Mac computer with [Apple Configurator 2.0](https://itunes.apple.com/us/app/apple-configurator-2/id1037126344?mt=12)</span></span>


## <a name="steps-to-enroll-ios-devices-by-using-apple-configurator-with-setup-assistant"></a><span data-ttu-id="f7839-116">Schritte für die Registrierung von iOS-Geräten mithilfe von Apple Configurator mit dem Setup-Assistenten</span><span class="sxs-lookup"><span data-stu-id="f7839-116">Steps to enroll iOS devices by using Apple Configurator with Setup Assistant</span></span>

<span data-ttu-id="f7839-117">In den folgenden Schritten wird erläutert, wie Sie iOS-Geräte am „Tag 0“ mithilfe von Apple Configurator mit dem Setup-Assistenten registrieren.</span><span class="sxs-lookup"><span data-stu-id="f7839-117">The following steps explain how to enroll iOS devices on "day 0" by using Apple Configurator with Setup Assistant.</span></span> <span data-ttu-id="f7839-118">Da Geräte zu Ihrer Organisation hinzugefügt und auch wieder aus dieser entfernt werden, werden Sie wahrscheinlich einige dieser Schritte wiederholen, z.B. das Hinzufügen und Entfernen von Seriennummern, so wie unten beschrieben.</span><span class="sxs-lookup"><span data-stu-id="f7839-118">As devices are added and removed from your organization, you will likely repeat some of these steps, such as adding or removing serial numbers, as described below.</span></span>

### <a name="create-mobile-device-groups-optional"></a><span data-ttu-id="f7839-119">Erstellen von mobilen Gerätegruppen (optional)</span><span class="sxs-lookup"><span data-stu-id="f7839-119">Create mobile device groups (optional)</span></span>

<span data-ttu-id="f7839-120">Wenn Ihr Unternehmen mobile Gerätegruppen zur Verwaltung von Geräten erfordert, können Sie optional diese Gruppen erstellen.</span><span class="sxs-lookup"><span data-stu-id="f7839-120">If your business requires mobile device groups to help manage devices, you can optionally create those groups.</span></span> <span data-ttu-id="f7839-121">Weitere Informationen finden Sie unter [Verwenden von Gruppen zum Verwalten von Benutzern und Geräten in Microsoft Intune](use-groups-to-manage-users-and-devices-with-microsoft-intune.md).</span><span class="sxs-lookup"><span data-stu-id="f7839-121">To learn more, see [Use groups to manage users and devices with Microsoft Intune](use-groups-to-manage-users-and-devices-with-microsoft-intune.md).</span></span>

### <a name="create-a-profile-for-devices"></a><span data-ttu-id="f7839-122">Erstellen eines Profils für Geräte</span><span class="sxs-lookup"><span data-stu-id="f7839-122">Create a profile for devices</span></span>

<span data-ttu-id="f7839-123">Ein Registrierungsprofil für Geräte definiert die Einstellungen für eine Gruppe von Geräten.</span><span class="sxs-lookup"><span data-stu-id="f7839-123">A device enrollment profile defines the settings applied to a group of devices.</span></span>

1. <span data-ttu-id="f7839-124">Wechseln Sie in der [Microsoft Intune-Verwaltungskonsole](https://manage.microsoft.com) zu **Richtlinie** &gt; **Unternehmensgeräteregistrierung**, und wählen Sie anschließend **Hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="f7839-124">In the [Microsoft Intune administration console](https://manage.microsoft.com), go to **Policy** &gt; **Corporate Device Enrollment**, and then choose **Add**.</span></span>

  ![Erstellen eines Geräteregistrierungsprofils](../media/pol-sa-corp-enroll.png)

2. <span data-ttu-id="f7839-126">Geben Sie die Details für die Geräteprofile ein:</span><span class="sxs-lookup"><span data-stu-id="f7839-126">Enter details for the device profiles:</span></span>

   -   <span data-ttu-id="f7839-127">**Name:** Der Name des Geräteregistrierungsprofils (für Benutzer nicht sichtbar).</span><span class="sxs-lookup"><span data-stu-id="f7839-127">**Name**&mdash;The name of the device enrollment profile (not visible to users).</span></span>

   -   <span data-ttu-id="f7839-128">**Beschreibung:** Eine Beschreibung des Geräteregistrierungsprofils (für Benutzer nicht sichtbar).</span><span class="sxs-lookup"><span data-stu-id="f7839-128">**Description**&mdash;A description of the device enrollment profile (not visible to users).</span></span>

   -   <span data-ttu-id="f7839-129">**Registrierungsdetails**: Gibt an, wie Geräte registriert werden.</span><span class="sxs-lookup"><span data-stu-id="f7839-129">**Enrollment Details**&mdash;Specifies how devices are enrolled.</span></span>

       -   <span data-ttu-id="f7839-130">**Benutzeraffinität anfordern**: Das Gerät muss während der ersten Installation einem Benutzer zugewiesen werden und kann dann die Berechtigung erhalten, auf Daten und E-Mails des Unternehmens zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="f7839-130">**Prompt for user affinity**&mdash;The device must be affiliated with a user during initial setup and can then be permitted to access company data and email.</span></span> <span data-ttu-id="f7839-131">**Benutzeraffinität** muss für verwaltete Geräte eingerichtet werden, die Benutzern gehören und das Unternehmensportal verwenden müssen, um Dienste wie die Installation von Apps nutzen zu können.</span><span class="sxs-lookup"><span data-stu-id="f7839-131">**User affinity** should be set up for managed devices that belong to users and need to use the company portal for services like installing apps.</span></span>

       -   <span data-ttu-id="f7839-132">**Keine Benutzeraffinität**: Das Gerät ist keinem Benutzer zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="f7839-132">**No user affinity**&mdash;The device is not affiliated with a user.</span></span> <span data-ttu-id="f7839-133">Verwenden Sie diese Zuweisung für Geräte, die Aufgaben ohne den Zugriff auf lokale Benutzerdaten ausführen.</span><span class="sxs-lookup"><span data-stu-id="f7839-133">Use this affiliation for devices that perform tasks without accessing local user data.</span></span> <span data-ttu-id="f7839-134">Apps, die eine Benutzerzugehörigkeit erfordern (einschließlich der Unternehmensportal-App, die für die Installation branchenspezifischer Apps verwendet wird), funktionieren nicht.</span><span class="sxs-lookup"><span data-stu-id="f7839-134">Apps requiring user affiliation (including the Company Portal app used for installing line-of-business apps) won’t work.</span></span>

   -   <span data-ttu-id="f7839-135">**Gerätegruppen-Vorabzuweisung**: Alle Geräte, die mit diesem Profil bereitgestellt werden, gehören anfänglich zu dieser Gruppe.</span><span class="sxs-lookup"><span data-stu-id="f7839-135">**Device group pre-assignment**&mdash;All devices deployed with this profile will initially belong to this group.</span></span> <span data-ttu-id="f7839-136">Sie können die Geräte nach der Registrierung erneut zuweisen.</span><span class="sxs-lookup"><span data-stu-id="f7839-136">You can reassign devices after enrollment.</span></span>

   > [!Important]
   > <span data-ttu-id="f7839-137">Gruppenzuweisungen werden von Intune zu Azure Active Directory verschoben.</span><span class="sxs-lookup"><span data-stu-id="f7839-137">Group assignments are moving from Intune to Azure Active Directory.</span></span> <span data-ttu-id="f7839-138">Sobald Ihr Intune-Konto die anwendbaren Updates erhält, wird Ihnen nicht mehr die Option **Geräte folgender Gruppe zuweisen** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f7839-138">Once your Intune account receives the applicable update, you won't see the **Assign devices to the following group** option.</span></span> <span data-ttu-id="f7839-139">[Erfahren Sie mehr](/intune-classic/deploy-use/ios-device-enrollment-program-in-microsoft-intune#changes-to-intune-group-assignments).</span><span class="sxs-lookup"><span data-stu-id="f7839-139">[Learn more](/intune-classic/deploy-use/ios-device-enrollment-program-in-microsoft-intune#changes-to-intune-group-assignments).</span></span>

   -  <span data-ttu-id="f7839-140">**Geräteregistrierungsprogramm**: Das Apple-Programm zur Geräteregistrierung (Device Enrollment Program, DEP) kann bei der Registrierung mit dem Setup-Assistenten nicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="f7839-140">**Device Enrollment Program**&mdash;The Apple Device Enrollment Program (DEP) cannot be used with Setup Assistant enrollment.</span></span> <span data-ttu-id="f7839-141">Stellen Sie sicher, dass die Umschaltfläche auf **aus** festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="f7839-141">Ensure that the toggle is set to **off**.</span></span>

3.  <span data-ttu-id="f7839-142">Wählen Sie **Profil speichern**, um das Profil hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="f7839-142">Choose **Save Profile** to add the profile.</span></span>

### <a name="add-ios-devices-to-enroll-with-setup-assistant"></a><span data-ttu-id="f7839-143">Mit dem Setup-Assistenten zu registrierende Geräte hinzufügen</span><span class="sxs-lookup"><span data-stu-id="f7839-143">Add iOS devices to enroll with Setup Assistant</span></span>

1. <span data-ttu-id="f7839-144">Wechseln Sie in der [Microsoft Intune-Verwaltungskonsole](https://manage.microsoft.com) zu **Gruppen** &gt; **Alle Geräte** &gt; **Alle unternehmenseigenen Geräte** &gt; **Alle Geräte**, und wählen Sie dann **Geräte hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="f7839-144">In the [Microsoft Intune administration console](https://manage.microsoft.com), go to **Groups** &gt; **All Devices** &gt; **All Corporate-owned Devices** &gt; **All Devices**, and then choose **Add devices**.</span></span>

   <span data-ttu-id="f7839-145">Sie können Geräte auf zwei Arten hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="f7839-145">You can add devices in two ways:</span></span>

   ![Dialogfeld „Geräte hinzufügen“](../media/pol-SA-enroll-iOS-SetupAssistant.png)

   -  <span data-ttu-id="f7839-147">**Hochladen einer CSV-Datei mit Seriennummern**: Erstellen Sie eine durch Trennzeichen getrennte Liste (CSV-Datei) mit zwei Spalten ohne Überschrift, die auf 5.000 Geräte oder 5 MB pro CSV-Datei beschränkt ist.</span><span class="sxs-lookup"><span data-stu-id="f7839-147">**Upload a CSV file containing serial numbers**&mdash;Create a comma-separated value (.csv) list of two columns without a header, limited to 5,000 devices or 5 MB per .csv file.</span></span>

    |||
    |-|-|
    |<span data-ttu-id="f7839-148">&lt;Seriennummer 1&gt;</span><span class="sxs-lookup"><span data-stu-id="f7839-148">&lt;Serial #1&gt;</span></span>|<span data-ttu-id="f7839-149">&lt;Details zu Gerät 1&gt;</span><span class="sxs-lookup"><span data-stu-id="f7839-149">&lt;Device #1 Details&gt;</span></span>|
    |<span data-ttu-id="f7839-150">&lt;Seriennummer 2&gt;</span><span class="sxs-lookup"><span data-stu-id="f7839-150">&lt;Serial#2&gt;</span></span>|<span data-ttu-id="f7839-151">&lt;Details zu Gerät 2&gt;</span><span class="sxs-lookup"><span data-stu-id="f7839-151">&lt;Device #2 Details&gt;</span></span>|

  <span data-ttu-id="f7839-152">Diese CSV-Datei sieht bei Anzeige in einem Text-Editor folgendermaßen aus:</span><span class="sxs-lookup"><span data-stu-id="f7839-152">When viewed in a text editor, this .csv file appears as:</span></span>

    ```
    0000000,PO 1234
    111111111,PO 1234
    ```

  -  <span data-ttu-id="f7839-153">**Manuelles Hinzufügen von Gerätedetails**&mdash;Geben Sie die Seriennummer und alle Anmerkungen und Details von bis zu 15 Geräten ein.</span><span class="sxs-lookup"><span data-stu-id="f7839-153">**Manually add device details**&mdash;Enter the serial number and any notes or details for up to 15 devices.</span></span>

  <span data-ttu-id="f7839-154">Bestätigen Sie im Bereich **Geräte überprüfen** die Seriennummern.</span><span class="sxs-lookup"><span data-stu-id="f7839-154">On the **Review Devices** pane, you can confirm the serial numbers.</span></span> <span data-ttu-id="f7839-155">Sie können auch entscheiden, ob Sie die **Details** für Seriennummern überschreiben, die wieder importiert werden. Alternativ können Sie das Kontrollkästchen **Überschreiben** deaktivieren, um die aktuellen Informationen zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="f7839-155">You can also decide whether to overwrite the **Details** for serial numbers that are being imported again, or you can uncheck the **Overwrite** box to preserve the Current details.</span></span>

  > [!NOTE]
  > <span data-ttu-id="f7839-156">In der vorhandenen Intune-Administratorkonsole können Administratoren zugehörige Details einer hochgeladenen CSV-Datei akzeptieren und die vorhandenen Details für einzelne Seriennummern überschreiben.</span><span class="sxs-lookup"><span data-stu-id="f7839-156">In the existing Intune administrator console, admins can accept associated details from an uploaded CSV and overwrite the existing details for individual serial numbers.</span></span> <span data-ttu-id="f7839-157">Sie können im neuen Azure-Portal nur die Details für alle Seriennummern überschreiben oder die Details für ebendiese ignorieren.</span><span class="sxs-lookup"><span data-stu-id="f7839-157">In the new Azure portal, you’ll only be able to overwrite the details for all serial numbers or to ignore new details for all serial numbers.</span></span>

  > [!NOTE]
  > <span data-ttu-id="f7839-158">Wenn Sie später unternehmenseigene Geräte aus der Intune-Verwaltung entfernen müssen, kann es notwendig sein, aus der Gerätegruppe **Nach iOS-Seriennummer** unter **Vorabregistrierte Unternehmensgeräte** die Seriennummer der Geräte in Intune zu entfernen, um die Geräteregistrierung zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="f7839-158">If you want to remove corporate-owned devices from Intune management later, you might need to go to **By iOS Serial Number** device group under **Corporate Pre-enrolled devices** and remove the device serial number from Intune in order to disable device enrollment.</span></span> <span data-ttu-id="f7839-159">Wenn Intune eine Notfallwiederherstellung durchführt, während oder nachdem Sie Seriennummern entfernt haben, müssen Sie sicherstellen, dass in dieser Gruppe nur die Seriennummern aktiver Geräte vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="f7839-159">If Intune performs a disaster recovery procedure on or around the time you remove serial numbers, you'll need to verify that only active devices’ serial numbers are present in that group.</span></span>

2. <span data-ttu-id="f7839-160">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="f7839-160">Choose **Next**.</span></span>

3. <span data-ttu-id="f7839-161">Wählen Sie die zu registrierenden Geräte aus.</span><span class="sxs-lookup"><span data-stu-id="f7839-161">Select the devices to enroll.</span></span> <span data-ttu-id="f7839-162">Bereits registrierte oder anderweitig registrierte Seriennummern werden nicht importiert.</span><span class="sxs-lookup"><span data-stu-id="f7839-162">Serial numbers already enrolled or enrolled by other means cannot be imported.</span></span> <span data-ttu-id="f7839-163">Klicken Sie auf **Weiter**, um fortzufahren.</span><span class="sxs-lookup"><span data-stu-id="f7839-163">Choose **Next** to continue.</span></span>

### <a name="assign-a-profile"></a><span data-ttu-id="f7839-164">Zuweisen eines Profils</span><span class="sxs-lookup"><span data-stu-id="f7839-164">Assign a profile</span></span>

<span data-ttu-id="f7839-165">Geben Sie das Profil an, das hinzugefügten Geräten aus der Liste der verfügbaren Profile zugewiesen werden soll, überprüfen Sie die **Registrierungsprofildetails**, und wählen Sie dann **Fertig stellen** aus.</span><span class="sxs-lookup"><span data-stu-id="f7839-165">Specify the profile to assign to added devices from the list of available profiles, review the **Enrollment profile details**, and then choose **Finish**.</span></span> <span data-ttu-id="f7839-166">Manuell hinzugefügte Geräte können einem beliebigen Registrierungsprofil zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="f7839-166">Manually added devices can be assigned to any enrollment profile.</span></span>

> [!Important]
> <span data-ttu-id="f7839-167">Derzeit können Sie in Intune ein „Standard“-Geräteregistrierungsprofil bestimmen. Das bedeutet, dass neue Seriennummern automatisch diesem Standardprofil hinzugefügt werden, wenn Sie neue Seriennummern mit dem Apple-Dienst synchronisieren.</span><span class="sxs-lookup"><span data-stu-id="f7839-167">Currently, Intune let you designate a "default" device enrollment profile," which means that new serial numbers are automatically assigned to that default profile when you synchronize new serial numbers with the Apple service.</span></span> <span data-ttu-id="f7839-168">Wenn Ihr Mandant demnächst zum Azure-Portal migriert wird, können Sie kein Standardprofil mehr festlegen, und Seriennummern werden nicht mehr automatisch diesem Profil zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="f7839-168">When your tenant is migrated to the new Azure portal in the near future, you will no longer be able to set a default profile and have serial numbers be automatically assigned to that profile.</span></span> <span data-ttu-id="f7839-169">Sie müssen stattdessen einem Profil Seriennummern zuweisen.</span><span class="sxs-lookup"><span data-stu-id="f7839-169">Instead, you will have to assign serial numbers to a profile.</span></span> [<span data-ttu-id="f7839-170">Erfahren Sie mehr</span><span class="sxs-lookup"><span data-stu-id="f7839-170">Learn more</span></span>](https://docs.microsoft.com/intune/device-enrollment-program-enroll-ios)

### <a name="export-a-profile-to-deploy-to-ios-devices"></a><span data-ttu-id="f7839-171">Exportieren eines Profils zum Bereitstellen auf iOS-Geräten</span><span class="sxs-lookup"><span data-stu-id="f7839-171">Export a profile to deploy to iOS devices</span></span>

1. <span data-ttu-id="f7839-172">Wechseln Sie in der [Microsoft Intune-Verwaltungskonsole](https://manage.microsoft.com) zu **Richtlinie** &gt; **Unternehmensgeräteregistrierung**, und wählen Sie das Geräteprofil aus, das auf mobilen Geräten bereitgestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="f7839-172">In the [Microsoft Intune administration console](https://manage.microsoft.com), go to **Policy** &gt; **Corporate Device Enrollment**, and then select the device profile to deploy to mobile devices.</span></span>

2. <span data-ttu-id="f7839-173">Wählen Sie in der Taskleiste **Exportieren** aus.</span><span class="sxs-lookup"><span data-stu-id="f7839-173">Choose **Export** in the taskbar.</span></span> <span data-ttu-id="f7839-174">Kopieren und speichern Sie die **Profil-URL**.</span><span class="sxs-lookup"><span data-stu-id="f7839-174">Copy and save the **Profile URL**.</span></span> <span data-ttu-id="f7839-175">Sie werden sie später in Apple Configurator hochladen, um das von iOS-Geräten verwendete Intune-Profil zu definieren.</span><span class="sxs-lookup"><span data-stu-id="f7839-175">You will upload it in Apple Configurator later to define the Intune profile used by iOS devices.</span></span>

   <span data-ttu-id="f7839-176">Sie laden im folgenden Verfahren diese Profil-URL mit Apple Configurator in den Apple-Dienst hoch, um das von iOS-Geräten verwendete Intune-Profil zu definieren.</span><span class="sxs-lookup"><span data-stu-id="f7839-176">You will upload this profile URL to the Apple service using Apple Configurator in the following procedure to define the Intune profile used by iOS devices.</span></span>

### <a name="prepare-the-device-with-apple-configurator"></a><span data-ttu-id="f7839-177">Vorbereiten des Geräts mit Apple Configurator</span><span class="sxs-lookup"><span data-stu-id="f7839-177">Prepare the device with Apple Configurator</span></span>

<span data-ttu-id="f7839-178">iOS-Geräte werden mit dem Mac-Computer verbunden und für die Verwaltung mobiler Geräte registriert.</span><span class="sxs-lookup"><span data-stu-id="f7839-178">iOS devices are connected to the Mac computer and enrolled for mobile device management.</span></span>

1.  <span data-ttu-id="f7839-179">Öffnen Sie auf einem Mac-Computer **Apple Configurator 2**.</span><span class="sxs-lookup"><span data-stu-id="f7839-179">On a Mac computer, open **Apple Configurator 2**.</span></span> <span data-ttu-id="f7839-180">Wählen Sie in der Menüleiste **Apple Configurator 2**, und wählen Sie dann **Voreinstellungen**.</span><span class="sxs-lookup"><span data-stu-id="f7839-180">In the menu bar, choose **Apple Configurator 2**, and then choose **Preferences**.</span></span>

   > [!WARNING]
   > <span data-ttu-id="f7839-181">Während des Registrierungsprozesses werden die Geräte auf Werkseinstellungen zurückgesetzt.</span><span class="sxs-lookup"><span data-stu-id="f7839-181">The devices will be reset to factory configurations during the enrollment process.</span></span> <span data-ttu-id="f7839-182">Als bewährte Methode empfiehlt es sich, das Gerät zurückzusetzen und einzuschalten.</span><span class="sxs-lookup"><span data-stu-id="f7839-182">As a best practice, reset the device and turn it on.</span></span> <span data-ttu-id="f7839-183">Nach dem Verbinden eines Geräts sollte der **Begrüßungsbildschirm** angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="f7839-183">Devices should be at the **Hello** screen when you connect the device.</span></span>

2. <span data-ttu-id="f7839-184">Wählen Sie im Bereich „Voreinstellungen“ die Option **Server** aus, und wählen Sie das Pluszeichen, um den MDM-Server-Assistenten zu starten.</span><span class="sxs-lookup"><span data-stu-id="f7839-184">In the preferences pane, select **Servers** and choose the plus symbol (+) to launch the MDM Server wizard.</span></span> <span data-ttu-id="f7839-185">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="f7839-185">Choose **Next**.</span></span>

3. <span data-ttu-id="f7839-186">Geben Sie den **Hostnamen oder die URL** und die **Registrierungs-URL** für den MDM-Server unter „Registrierung von iOS-Geräten bei Microsoft Intune über den Setup-Assistenten“.</span><span class="sxs-lookup"><span data-stu-id="f7839-186">Enter the **Hostname or URL** and **enrollment URL** for the MDM server under Setup Assistant enrollment for iOS devices with Microsoft Intune.</span></span> <span data-ttu-id="f7839-187">Geben Sie für die Registrierungs-URL die aus Intune exportierte Registrierungsprofil-URL ein.</span><span class="sxs-lookup"><span data-stu-id="f7839-187">For the Enrollment URL, enter the enrollment profile URL exported from Intune.</span></span> <span data-ttu-id="f7839-188">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="f7839-188">Choose **Next**.</span></span>  

   <span data-ttu-id="f7839-189">Sie können die Warnung, dass die Server-URL nicht überprüft wird, problemlos ignorieren.</span><span class="sxs-lookup"><span data-stu-id="f7839-189">You can safely disregard a warning stating "server URL is not verified."</span></span> <span data-ttu-id="f7839-190">Um den Vorgang fortzusetzen, wählen Sie **Weiter**, bis der Assistent abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="f7839-190">To continue, choose **Next** until the wizard is finished.</span></span>

4.  <span data-ttu-id="f7839-191">Verbinden Sie die mobilen iOS-Geräte über einen USB-Adapter mit dem Mac-Computer.</span><span class="sxs-lookup"><span data-stu-id="f7839-191">Connect the iOS mobile devices to the Mac computer with a USB adapter.</span></span>

    > [!WARNING]
    > <span data-ttu-id="f7839-192">Während des Registrierungsprozesses werden die Geräte auf Werkseinstellungen zurückgesetzt.</span><span class="sxs-lookup"><span data-stu-id="f7839-192">The devices will be reset to factory configurations during the enrollment process.</span></span> <span data-ttu-id="f7839-193">Als bewährte Methode empfiehlt es sich, das Gerät zurückzusetzen und einzuschalten.</span><span class="sxs-lookup"><span data-stu-id="f7839-193">As a best practice, reset the device and turn it on.</span></span> <span data-ttu-id="f7839-194">Wenn Sie den Setup-Assistenten starten, sollte der **Begrüßungsbildschirm** zu sehen sein.</span><span class="sxs-lookup"><span data-stu-id="f7839-194">Devices should be at the **Hello** screen when you start Setup Assistant.</span></span>

5.  <span data-ttu-id="f7839-195">Wählen Sie **Vorbereiten**.</span><span class="sxs-lookup"><span data-stu-id="f7839-195">Choose **Prepare**.</span></span> <span data-ttu-id="f7839-196">Wählen Sie im Bereich „iOS-Gerät vorbereiten“ die Option **Manuell** aus, und wählen Sie dann **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="f7839-196">On the Prepare iOS Device pane, select **Manual** and then choose **Next**.</span></span>

6. <span data-ttu-id="f7839-197">Wählen Sie im Bereich „Beim MDM-Server registrieren“ den erstellten Servernamen aus, und wählen Sie dann **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="f7839-197">On the Enroll in MDM Server pane, select the server name you created, and then choose **Next**.</span></span>

7. <span data-ttu-id="f7839-198">Wählen Sie im Bereich „Geräte überwachen“ den Grad der Überwachung aus, und wählen Sie dann **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="f7839-198">On the Supervise Devices pane, select the level of supervision, and then choose **Next**.</span></span>

8. <span data-ttu-id="f7839-199">Wählen Sie im Bereich „Organisation erstellen“ die **Organisation** aus, oder erstellen Sie eine neue Organisation, und wählen Sie dann **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="f7839-199">On the Create an Organization pane, choose the **Organization** or create a new organization, and then choose **Next**.</span></span>

9. <span data-ttu-id="f7839-200">Wählen Sie im Bereich „iOS-Setup-Assistenten konfigurieren“ die Schritte aus, die dem Benutzer angezeigt werden sollen, und wählen Sie dann **Vorbereiten**.</span><span class="sxs-lookup"><span data-stu-id="f7839-200">On the Configure iOS Setup Assistant pane, choose the steps to be presented to the user, and then choose **Prepare**.</span></span> <span data-ttu-id="f7839-201">Authentifizieren Sie sich, wenn Sie dazu aufgefordert werden, um die Vertrauenseinstellungen zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="f7839-201">If prompted, authenticate to update trust settings.</span></span>  

10. <span data-ttu-id="f7839-202">Trennen Sie das USB-Kabel, wenn die Vorbereitung des iOS-Geräts abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="f7839-202">When the iOS device finishes preparing, disconnect the USB cable.</span></span>  

### <a name="distribute-devices"></a><span data-ttu-id="f7839-203">Verteilen von Geräten</span><span class="sxs-lookup"><span data-stu-id="f7839-203">Distribute devices</span></span>

<span data-ttu-id="f7839-204">Die Geräte sind nun für die Unternehmensregistrierung bereit.</span><span class="sxs-lookup"><span data-stu-id="f7839-204">The devices are now ready for corporate enrollment.</span></span> <span data-ttu-id="f7839-205">Schalten Sie die Geräte aus, und verteilen Sie sie an Benutzer.</span><span class="sxs-lookup"><span data-stu-id="f7839-205">Turn off the devices and distribute them to users.</span></span> <span data-ttu-id="f7839-206">Wenn die Benutzer die Geräte einschalten, wird der Setup-Assistent gestartet.</span><span class="sxs-lookup"><span data-stu-id="f7839-206">When users turn on their devices, Setup Assistant will start.</span></span>



### <a name="see-also"></a><span data-ttu-id="f7839-207">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="f7839-207">See also</span></span>
[<span data-ttu-id="f7839-208">Voraussetzungen für die Registrierung von Geräten</span><span class="sxs-lookup"><span data-stu-id="f7839-208">Prerequisites for enrolling devices</span></span>](prerequisites-for-enrollment.md)
