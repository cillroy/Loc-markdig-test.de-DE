---
title: "Hinzufügen von Unternehmensbezeichnern zu Intune"
titlesuffix: Azure portal
description: "Erfahren Sie, wie Sie in Microsoft Intune Unternehmensbezeichner (Registrierungsmethode, IMEI- und Seriennummern) hinzufügen. \""
keywords: 
author: NathBarn
ms.author: nathbarn
manager: angrobe
ms.date: 08/23/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 566ed16d-8030-42ee-bac9-5f8252a83012
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 374511e9fbe9e42de09e9bac9fc3f0b0aa76db13
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2018
---
# <a name="identify-devices-as-corporate-owned"></a><span data-ttu-id="12f0e-104">Identifizieren von Geräten als unternehmenseigen</span><span class="sxs-lookup"><span data-stu-id="12f0e-104">Identify devices as corporate-owned</span></span>

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="12f0e-105">Als Intune-Administrator können Sie Geräte als unternehmenseigen identifizieren, um die Verwaltung und Identifizierung zu optimieren.</span><span class="sxs-lookup"><span data-stu-id="12f0e-105">As an Intune admin, you can identify devices as corporate-owned to refine management and identification.</span></span> <span data-ttu-id="12f0e-106">Intune kann zusätzliche Verwaltungsaufgaben durchführen und zusätzliche Informationen sammeln, wie etwa die vollständige Telefonnummer und einen Bestand an Apps von unternehmenseigenen Geräten.</span><span class="sxs-lookup"><span data-stu-id="12f0e-106">Intune can perform additional management tasks and collect additional information such as the full phone number and an inventory of apps from corporate-owned devices.</span></span> <span data-ttu-id="12f0e-107">Sie haben auch die Möglichkeit, Gerätebeschränkungen festzulegen, um die Registrierung von Geräten, die kein Unternehmenseigentum sind, zu blockieren.</span><span class="sxs-lookup"><span data-stu-id="12f0e-107">You can also set device restrictions to block enrollment by devices that aren't corporate-owned.</span></span>

<span data-ttu-id="12f0e-108">Ein Gerät gilt als unternehmenseigenes Gerät, wenn eine der folgenden Bedingungen zutrifft:</span><span class="sxs-lookup"><span data-stu-id="12f0e-108">A device is identified as corporate-owned if any of the following conditions are true:</span></span>

- <span data-ttu-id="12f0e-109">Mit einem [Geräteregistrierungs-Manager](device-enrollment-manager-enroll.md)-Konto registriert (alle Plattformen)</span><span class="sxs-lookup"><span data-stu-id="12f0e-109">Enrolled with a [device enrollment manager](device-enrollment-manager-enroll.md) account (all platforms)</span></span>
- <span data-ttu-id="12f0e-110">Mit dem [Apple-Programm zur Geräteregistrierung](device-enrollment-program-enroll-ios.md), dem [Apple School Manager](apple-school-manager-set-up-ios.md) oder dem [Apple Configurator](apple-configurator-enroll-ios.md) registriert (iOS-Geräte).</span><span class="sxs-lookup"><span data-stu-id="12f0e-110">Enrolled with the Apple [Device Enrollment Program](device-enrollment-program-enroll-ios.md), [Apple School Manager](apple-school-manager-set-up-ios.md), or [Apple Configurator](apple-configurator-enroll-ios.md) (iOS only)</span></span>
- <span data-ttu-id="12f0e-111">Mit einer IMEI-Nummer (alle Plattformen mit IMEI-Nummern) oder Seriennummer (iOS und Android) [vor der Registrierung als unternehmenseigen identifiziert](#identify-corporate-owned-devices-with-imei-or-serial-number)</span><span class="sxs-lookup"><span data-stu-id="12f0e-111">[Identified as corporate-owned before enrollment](#identify-corporate-owned-devices-with-imei-or-serial-number) with an international mobile equipment identifier (IMEI) numbers (all platforms with IMEI numbers) or serial number (iOS and Android)</span></span>
- <span data-ttu-id="12f0e-112">In Azure Active Directory oder Enterprise Mobility + Security als Windows 10 Enterprise-Gerät registriert</span><span class="sxs-lookup"><span data-stu-id="12f0e-112">Registered in Azure Active Directory or Enterprise Mobility + Security as a Windows 10 Enterprise device</span></span>
- <span data-ttu-id="12f0e-113">Zu den Eigenschaften des Geräts zählt der [Gerätebesitz als unternehmenseigen](#change-device-ownership)</span><span class="sxs-lookup"><span data-stu-id="12f0e-113">The device's properties list [device ownership as corporate](#change-device-ownership)</span></span>

## <a name="identify-corporate-owned-devices-with-imei-or-serial-number"></a><span data-ttu-id="12f0e-114">Identifizieren von unternehmenseigenen Geräten mit IMEI- oder Seriennummer</span><span class="sxs-lookup"><span data-stu-id="12f0e-114">Identify corporate-owned devices with IMEI or serial number</span></span>

<span data-ttu-id="12f0e-115">Als Intune-Administrator können Sie eine durch Trennzeichen getrennte Datei (CSV-Datei) erstellen und importieren, die IMEI-Nummern oder Seriennummern auflistet.</span><span class="sxs-lookup"><span data-stu-id="12f0e-115">As an Intune admin, you can create and import a comma-separated value (.csv) file that lists IMEI numbers or serial numbers.</span></span> <span data-ttu-id="12f0e-116">Intune verwendet diese Bezeichner, um den Gerätebesitz während der Registrierung als unternehmenseigen anzugeben.</span><span class="sxs-lookup"><span data-stu-id="12f0e-116">Intune uses these identifiers to specify device ownership as corporate during device enrollment.</span></span> <span data-ttu-id="12f0e-117">Sie können die IMEI-Nummern für alle unterstützten Plattformen deklarieren.</span><span class="sxs-lookup"><span data-stu-id="12f0e-117">You can declare IMEI numbers for all supported platforms.</span></span> <span data-ttu-id="12f0e-118">Sie können die Seriennummer nur für iOS-, macOS- und Android-Geräte deklarieren.</span><span class="sxs-lookup"><span data-stu-id="12f0e-118">You can only declare serial number for iOS, macOS, and Android devices.</span></span> <span data-ttu-id="12f0e-119">Jede IMEI-Nummer oder Seriennummer kann Details enthalten, die in der Liste zu administrativen Zwecken angegeben sind.</span><span class="sxs-lookup"><span data-stu-id="12f0e-119">Each IMEI or serial number can have details specified in the list for administrative purposes.</span></span>

<!-- When you upload serial numbers for company-owned iOS devices, they must be paired with a corporate enrollment profile. Devices must then be enrolled using either Apple’s device enrollment program (DEP) or Apple Configurator to have them appear as company-owned. -->

<span data-ttu-id="12f0e-120">[Erfahren Sie, wie Sie die Seriennummer eines Apple-Geräts finden](https://support.apple.com/HT204308).</span><span class="sxs-lookup"><span data-stu-id="12f0e-120">[Learn how to find an Apple device serial number](https://support.apple.com/HT204308).</span></span><br>
<span data-ttu-id="12f0e-121">[Erfahren Sie, wie Sie die Seriennummer Ihres Android-Geräts finden](https://support.google.com/store/answer/3333000).</span><span class="sxs-lookup"><span data-stu-id="12f0e-121">[Learn how to find your Android device serial number](https://support.google.com/store/answer/3333000).</span></span>

## <a name="add-corporate-identifiers"></a><span data-ttu-id="12f0e-122">Hinzufügen von Unternehmensbezeichnern</span><span class="sxs-lookup"><span data-stu-id="12f0e-122">Add corporate identifiers</span></span>
<span data-ttu-id="12f0e-123">Erstellen Sie dazu eine Liste mit zwei Spalten, die durch Trennzeichen getrennt ist (CSV) und keinen Header enthält.</span><span class="sxs-lookup"><span data-stu-id="12f0e-123">To create the list, create a two-column, comma-separated value (.csv) list without a header.</span></span> <span data-ttu-id="12f0e-124">Fügen Sie die IMEI- oder Seriennummer in der linken Spalte und die Details in der rechten Spalte hinzu.</span><span class="sxs-lookup"><span data-stu-id="12f0e-124">Add the IMEI or serial numbers in the left column, and the details in the right column.</span></span> <span data-ttu-id="12f0e-125">Nur ein Typ von ID, IMEI- oder Seriennummer kann in eine CSV-Datei importiert werden.</span><span class="sxs-lookup"><span data-stu-id="12f0e-125">Only one type of ID, IMEI or serial number, can be imported in a single .csv file.</span></span> <span data-ttu-id="12f0e-126">Details sind auf 128 Zeichen beschränkt und nur für administrative Zwecke bestimmt.</span><span class="sxs-lookup"><span data-stu-id="12f0e-126">Details are limited to 128 characters and are for administrative use only.</span></span> <span data-ttu-id="12f0e-127">Details werden nicht auf dem Gerät angezeigt.</span><span class="sxs-lookup"><span data-stu-id="12f0e-127">Details aren't displayed on the device.</span></span> <span data-ttu-id="12f0e-128">Die aktuelle Begrenzung beträgt 5.000 Zeilen pro CSV-Datei.</span><span class="sxs-lookup"><span data-stu-id="12f0e-128">The current limit is 5,000 rows per .csv file.</span></span>

<span data-ttu-id="12f0e-129">**Eine CSV-Datei mit Seriennummern hochladen**: Erstellen Sie eine durch Trennzeichen getrennte Liste (.csv) mit zwei Spalten ohne Header, und beschränken Sie die Liste auf 5.000 Geräte oder 5 MB pro CSV-Datei.</span><span class="sxs-lookup"><span data-stu-id="12f0e-129">**Upload a .csv file that has serial numbers** – Create a two-column, comma-separated value (.csv) list without a header, and limit the list to 5,000 devices or 5 MB per .csv file.</span></span>

|||
|-|-|
|<span data-ttu-id="12f0e-130">&lt;ID #1&gt;</span><span class="sxs-lookup"><span data-stu-id="12f0e-130">&lt;ID #1&gt;</span></span>|<span data-ttu-id="12f0e-131">&lt;Details zu Gerät 1&gt;</span><span class="sxs-lookup"><span data-stu-id="12f0e-131">&lt;Device #1 Details&gt;</span></span>|
|<span data-ttu-id="12f0e-132">&lt;ID #2&gt;</span><span class="sxs-lookup"><span data-stu-id="12f0e-132">&lt;ID #2&gt;</span></span>|<span data-ttu-id="12f0e-133">&lt;Details zu Gerät 2&gt;</span><span class="sxs-lookup"><span data-stu-id="12f0e-133">&lt;Device #2 Details&gt;</span></span>|

<span data-ttu-id="12f0e-134">Diese CSV-Datei wird bei der Anzeige in einem Text-Editor folgendermaßen angezeigt:</span><span class="sxs-lookup"><span data-stu-id="12f0e-134">This .csv file when viewed in a text editor appears as:</span></span>

```
01234567890123,device details
02234567890123,device details
```

> [!IMPORTANT]
> <span data-ttu-id="12f0e-135">Einige Android-Geräte verfügen über mehrere IMEI-Nummern.</span><span class="sxs-lookup"><span data-stu-id="12f0e-135">Some Android devices have multiple IMEI numbers.</span></span> <span data-ttu-id="12f0e-136">Intune liest nur eine IMEI-Nummer pro registriertem Gerät.</span><span class="sxs-lookup"><span data-stu-id="12f0e-136">Intune only reads one IMEI number per enrolled device.</span></span> <span data-ttu-id="12f0e-137">Wenn Sie eine IMEI-Nummer importieren, es sich aber nicht um die IMEI-Nummer handelt, die von Intune inventarisiert wurde, wird das Gerät als ein persönliches Gerät und nicht als ein unternehmenseigenes Gerät eingestuft.</span><span class="sxs-lookup"><span data-stu-id="12f0e-137">If you import an IMEI number but it is not the IMEI inventoried by Intune, the device is classified as a personal device instead of a company-owned device.</span></span> <span data-ttu-id="12f0e-138">Wenn Sie mehrere IMEI-Nummern für ein Gerät importieren, werden nicht inventarisierte Nummern als Anmeldungsstatus **Unbekannt** anzeigen.</span><span class="sxs-lookup"><span data-stu-id="12f0e-138">If you import multiple IMEI numbers for a device, uninventoried numbers display **Unknown** for enrollment status.</span></span><br>
><span data-ttu-id="12f0e-139">Beachten Sie auch: Android-Seriennummern sind garantiert eindeutig oder vorhanden.</span><span class="sxs-lookup"><span data-stu-id="12f0e-139">Also note: Android Serial numbers are not guaranteed to be unique or present.</span></span> <span data-ttu-id="12f0e-140">Wenden Sie sich an Ihren Gerätehersteller, um herauszufinden, ob die Seriennummer eine zuverlässige Geräte-ID ist.</span><span class="sxs-lookup"><span data-stu-id="12f0e-140">Check with your device supplier to understand if serial number is a reliable device ID.</span></span>
><span data-ttu-id="12f0e-141">Seriennummern, die vom Gerät an Intune übermittelt werden, stimmen möglicherweise nicht mit der angezeigten ID in den Menüs „Einstellungen für Android/Info“ auf dem Gerät überein.</span><span class="sxs-lookup"><span data-stu-id="12f0e-141">Serial numbers reported by the device to Intune might not match the displayed ID in the Android Settings/About menus on the device.</span></span> <span data-ttu-id="12f0e-142">Überprüfen Sie den Typ der Seriennummer, die vom Gerätehersteller übermittelt wurde.</span><span class="sxs-lookup"><span data-stu-id="12f0e-142">Verify the type of serial number reported by the device manufacturer.</span></span>

### <a name="add-a-csv-list-of-corporate-identifiers"></a><span data-ttu-id="12f0e-143">Hinzufügen einer CSV-Liste von Unternehmensbezeichnern</span><span class="sxs-lookup"><span data-stu-id="12f0e-143">Add a .csv list of corporate identifiers</span></span>

1. <span data-ttu-id="12f0e-144">Wählen Sie im Azure-Portal in Intune die Optionen **Geräteregistrierung** > **Bezeichner von Unternehmensgeräten** aus, und klicken Sie dann auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="12f0e-144">In Intune in the Azure portal, choose **Device enrollment** > **Corporate Device Identifiers**, and then click **Add**.</span></span>

   ![Screenshot des Arbeitsbereichs des Bezeichners von Unternehmensgeräten mit hervorgehobener Schaltfläche „Hinzufügen“](./media/add-corp-id.png)

2. <span data-ttu-id="12f0e-146">Geben Sie auf dem Blatt **Bezeichner hinzufügen** den Bezeichnertyp an, **IMEI** oder **Seriennummer**.</span><span class="sxs-lookup"><span data-stu-id="12f0e-146">In the **Add Identifiers** blade, specify the identifier type: **IMEI** or **Serial**.</span></span> <span data-ttu-id="12f0e-147">Sie können angeben, ob für zuvor importierte Zahlen Folgendes gilt: **Hiermit überschreiben Sie Details für vorhandene Bezeichner**.</span><span class="sxs-lookup"><span data-stu-id="12f0e-147">You can specify whether previously imported numbers should **Overwrite details for existing identifiers**.</span></span>

3. <span data-ttu-id="12f0e-148">Klicken Sie auf das Ordnersymbol, und geben Sie den Pfad zu der Liste an, die Sie importieren möchten.</span><span class="sxs-lookup"><span data-stu-id="12f0e-148">Click the folder icon and specify the path to the list you want to import.</span></span> <span data-ttu-id="12f0e-149">Navigieren Sie zu der CSV-Datei, und wählen Sie **Hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="12f0e-149">Navigate to the .csv file, and select **Add**.</span></span> <span data-ttu-id="12f0e-150">Sie können auf **Aktualisieren** klicken, um neue Gerätebezeichner anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="12f0e-150">You can click **Refresh** to see new device identifiers.</span></span>

<span data-ttu-id="12f0e-151">Importierte Geräte sind nicht zwangsläufig registriert.</span><span class="sxs-lookup"><span data-stu-id="12f0e-151">Imported devices are not necessarily enrolled.</span></span> <span data-ttu-id="12f0e-152">Geräte können entweder **Registriert** oder **Nicht kontaktiert** sein.</span><span class="sxs-lookup"><span data-stu-id="12f0e-152">Devices can have a state of either **Enrolled** or **Not contacted**.</span></span> <span data-ttu-id="12f0e-153">**Nicht kontaktiert** bedeutet, dass das Gerät noch nie mit dem Intune-Dienst kommuniziert hat.</span><span class="sxs-lookup"><span data-stu-id="12f0e-153">**Not contacted** means that the device has never communicated in with the Intune service.</span></span>

### <a name="delete-corporate-identifiers"></a><span data-ttu-id="12f0e-154">Löschen von Unternehmensbezeichnern</span><span class="sxs-lookup"><span data-stu-id="12f0e-154">Delete corporate identifiers</span></span>

1. <span data-ttu-id="12f0e-155">Wählen Sie im Azure-Portal in Intune die Optionen **Geräteregistrierung** > **Bezeichner von Unternehmensgeräten** aus.</span><span class="sxs-lookup"><span data-stu-id="12f0e-155">In Intune in the Azure portal, choose **Device enrollment** > **Corporate Device Identifiers**.</span></span>
2. <span data-ttu-id="12f0e-156">Wählen Sie die Gerätebezeichner aus, die Sie löschen möchten, und klicken Sie auf **Löschen**.</span><span class="sxs-lookup"><span data-stu-id="12f0e-156">Select the device identifiers you want to delete, and choose **Delete**.</span></span>
3. <span data-ttu-id="12f0e-157">Bestätigen Sie den Löschvorgang.</span><span class="sxs-lookup"><span data-stu-id="12f0e-157">Confirm the deletion.</span></span>

<span data-ttu-id="12f0e-158">Das Löschen eines Unternehmensbezeichners für ein registriertes Gerät hat keine Auswirkungen auf den Besitzstatus des Geräts.</span><span class="sxs-lookup"><span data-stu-id="12f0e-158">Deleting a corporate identifier for an enrolled device does not change the device's ownership.</span></span> <span data-ttu-id="12f0e-159">Gehen Sie zum Ändern des Gerätebesitzes zu **Geräte** > **Alle Geräte**, klicken Sie auf das Gerät und dann auf **Eigenschaften**, und ändern Sie den **Gerätebesitz**.</span><span class="sxs-lookup"><span data-stu-id="12f0e-159">To change a device's ownership, go **Devices** > **All devices**, select the device, choose **Properties**, and change **Device ownership**.</span></span>

### <a name="imei-specifications"></a><span data-ttu-id="12f0e-160">IMEI-Spezifikationen</span><span class="sxs-lookup"><span data-stu-id="12f0e-160">IMEI specifications</span></span>
<span data-ttu-id="12f0e-161">Detaillierte Angaben über International Mobile Equipment Identifier finden Sie unter [3GGPP TS 23.003](https://portal.3gpp.org/desktopmodules/Specifications/SpecificationDetails.aspx?specificationId=729).</span><span class="sxs-lookup"><span data-stu-id="12f0e-161">For detailed specifications about International Mobile Equipment Identifiers, see [3GGPP TS 23.003](https://portal.3gpp.org/desktopmodules/Specifications/SpecificationDetails.aspx?specificationId=729).</span></span>

## <a name="change-device-ownership"></a><span data-ttu-id="12f0e-162">Ändern des Gerätebesitzes</span><span class="sxs-lookup"><span data-stu-id="12f0e-162">Change device ownership</span></span>

<span data-ttu-id="12f0e-163">Die Geräteeigenschaften zeigen den **Besitz** für jeden Gerätedatensatz in Intune an.</span><span class="sxs-lookup"><span data-stu-id="12f0e-163">Devices properties display **Ownership** for each device records in Intune.</span></span> <span data-ttu-id="12f0e-164">Als Administrator können Sie Geräte als **Persönlich** oder **Unternehmen** festlegen.</span><span class="sxs-lookup"><span data-stu-id="12f0e-164">As an admin, you can specify devices as **Personal** or **Corporate**.</span></span>

<span data-ttu-id="12f0e-165">**So ändern Sie den Gerätebesitz:**</span><span class="sxs-lookup"><span data-stu-id="12f0e-165">**To change device ownership:**</span></span>
1. <span data-ttu-id="12f0e-166">Navigieren Sie in Intune im Azure-Portal zu **Geräte** > **Alle Geräte**, und wählen Sie das Gerät aus.</span><span class="sxs-lookup"><span data-stu-id="12f0e-166">In Intune in the Azure portal, go **Devices** > **All devices**, and choose the device.</span></span>
2. <span data-ttu-id="12f0e-167">Wählen Sie **Eigenschaften** aus.</span><span class="sxs-lookup"><span data-stu-id="12f0e-167">Choose **Properties**.</span></span>
3. <span data-ttu-id="12f0e-168">Geben Sie den **Gerätebesitz** als **Persönlich** oder **Unternehmen** an.</span><span class="sxs-lookup"><span data-stu-id="12f0e-168">Specify **Device ownership** as **Personal** or **Corporate**.</span></span>

   ![Screenshot der Geräteeigenschaften, der die Optionen der Gerätekategorie und des Gerätebesitzes anzeigt.](./media/device-properties.png)
