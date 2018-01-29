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
# <a name="identify-devices-as-corporate-owned"></a>Identifizieren von Geräten als unternehmenseigen

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Als Intune-Administrator können Sie Geräte als unternehmenseigen identifizieren, um die Verwaltung und Identifizierung zu optimieren. Intune kann zusätzliche Verwaltungsaufgaben durchführen und zusätzliche Informationen sammeln, wie etwa die vollständige Telefonnummer und einen Bestand an Apps von unternehmenseigenen Geräten. Sie haben auch die Möglichkeit, Gerätebeschränkungen festzulegen, um die Registrierung von Geräten, die kein Unternehmenseigentum sind, zu blockieren.

Ein Gerät gilt als unternehmenseigenes Gerät, wenn eine der folgenden Bedingungen zutrifft:

- Mit einem [Geräteregistrierungs-Manager](device-enrollment-manager-enroll.md)-Konto registriert (alle Plattformen)
- Mit dem [Apple-Programm zur Geräteregistrierung](device-enrollment-program-enroll-ios.md), dem [Apple School Manager](apple-school-manager-set-up-ios.md) oder dem [Apple Configurator](apple-configurator-enroll-ios.md) registriert (iOS-Geräte).
- Mit einer IMEI-Nummer (alle Plattformen mit IMEI-Nummern) oder Seriennummer (iOS und Android) [vor der Registrierung als unternehmenseigen identifiziert](#identify-corporate-owned-devices-with-imei-or-serial-number)
- In Azure Active Directory oder Enterprise Mobility + Security als Windows 10 Enterprise-Gerät registriert
- Zu den Eigenschaften des Geräts zählt der [Gerätebesitz als unternehmenseigen](#change-device-ownership)

## <a name="identify-corporate-owned-devices-with-imei-or-serial-number"></a>Identifizieren von unternehmenseigenen Geräten mit IMEI- oder Seriennummer

Als Intune-Administrator können Sie eine durch Trennzeichen getrennte Datei (CSV-Datei) erstellen und importieren, die IMEI-Nummern oder Seriennummern auflistet. Intune verwendet diese Bezeichner, um den Gerätebesitz während der Registrierung als unternehmenseigen anzugeben. Sie können die IMEI-Nummern für alle unterstützten Plattformen deklarieren. Sie können die Seriennummer nur für iOS-, macOS- und Android-Geräte deklarieren. Jede IMEI-Nummer oder Seriennummer kann Details enthalten, die in der Liste zu administrativen Zwecken angegeben sind.

<!-- When you upload serial numbers for company-owned iOS devices, they must be paired with a corporate enrollment profile. Devices must then be enrolled using either Apple’s device enrollment program (DEP) or Apple Configurator to have them appear as company-owned. -->

[Erfahren Sie, wie Sie die Seriennummer eines Apple-Geräts finden](https://support.apple.com/HT204308).<br>
[Erfahren Sie, wie Sie die Seriennummer Ihres Android-Geräts finden](https://support.google.com/store/answer/3333000).

## <a name="add-corporate-identifiers"></a>Hinzufügen von Unternehmensbezeichnern
Erstellen Sie dazu eine Liste mit zwei Spalten, die durch Trennzeichen getrennt ist (CSV) und keinen Header enthält. Fügen Sie die IMEI- oder Seriennummer in der linken Spalte und die Details in der rechten Spalte hinzu. Nur ein Typ von ID, IMEI- oder Seriennummer kann in eine CSV-Datei importiert werden. Details sind auf 128 Zeichen beschränkt und nur für administrative Zwecke bestimmt. Details werden nicht auf dem Gerät angezeigt. Die aktuelle Begrenzung beträgt 5.000 Zeilen pro CSV-Datei.

**Eine CSV-Datei mit Seriennummern hochladen**: Erstellen Sie eine durch Trennzeichen getrennte Liste (.csv) mit zwei Spalten ohne Header, und beschränken Sie die Liste auf 5.000 Geräte oder 5 MB pro CSV-Datei.

|||
|-|-|
|&lt;ID #1&gt;|&lt;Details zu Gerät 1&gt;|
|&lt;ID #2&gt;|&lt;Details zu Gerät 2&gt;|

Diese CSV-Datei wird bei der Anzeige in einem Text-Editor folgendermaßen angezeigt:

```
01234567890123,device details
02234567890123,device details
```

> [!IMPORTANT]
> Einige Android-Geräte verfügen über mehrere IMEI-Nummern. Intune liest nur eine IMEI-Nummer pro registriertem Gerät. Wenn Sie eine IMEI-Nummer importieren, es sich aber nicht um die IMEI-Nummer handelt, die von Intune inventarisiert wurde, wird das Gerät als ein persönliches Gerät und nicht als ein unternehmenseigenes Gerät eingestuft. Wenn Sie mehrere IMEI-Nummern für ein Gerät importieren, werden nicht inventarisierte Nummern als Anmeldungsstatus **Unbekannt** anzeigen.<br>
>Beachten Sie auch: Android-Seriennummern sind garantiert eindeutig oder vorhanden. Wenden Sie sich an Ihren Gerätehersteller, um herauszufinden, ob die Seriennummer eine zuverlässige Geräte-ID ist.
>Seriennummern, die vom Gerät an Intune übermittelt werden, stimmen möglicherweise nicht mit der angezeigten ID in den Menüs „Einstellungen für Android/Info“ auf dem Gerät überein. Überprüfen Sie den Typ der Seriennummer, die vom Gerätehersteller übermittelt wurde.

### <a name="add-a-csv-list-of-corporate-identifiers"></a>Hinzufügen einer CSV-Liste von Unternehmensbezeichnern

1. Wählen Sie im Azure-Portal in Intune die Optionen **Geräteregistrierung** > **Bezeichner von Unternehmensgeräten** aus, und klicken Sie dann auf **Hinzufügen**.

   ![Screenshot des Arbeitsbereichs des Bezeichners von Unternehmensgeräten mit hervorgehobener Schaltfläche „Hinzufügen“](./media/add-corp-id.png)

2. Geben Sie auf dem Blatt **Bezeichner hinzufügen** den Bezeichnertyp an, **IMEI** oder **Seriennummer**. Sie können angeben, ob für zuvor importierte Zahlen Folgendes gilt: **Hiermit überschreiben Sie Details für vorhandene Bezeichner**.

3. Klicken Sie auf das Ordnersymbol, und geben Sie den Pfad zu der Liste an, die Sie importieren möchten. Navigieren Sie zu der CSV-Datei, und wählen Sie **Hinzufügen** aus. Sie können auf **Aktualisieren** klicken, um neue Gerätebezeichner anzuzeigen.

Importierte Geräte sind nicht zwangsläufig registriert. Geräte können entweder **Registriert** oder **Nicht kontaktiert** sein. **Nicht kontaktiert** bedeutet, dass das Gerät noch nie mit dem Intune-Dienst kommuniziert hat.

### <a name="delete-corporate-identifiers"></a>Löschen von Unternehmensbezeichnern

1. Wählen Sie im Azure-Portal in Intune die Optionen **Geräteregistrierung** > **Bezeichner von Unternehmensgeräten** aus.
2. Wählen Sie die Gerätebezeichner aus, die Sie löschen möchten, und klicken Sie auf **Löschen**.
3. Bestätigen Sie den Löschvorgang.

Das Löschen eines Unternehmensbezeichners für ein registriertes Gerät hat keine Auswirkungen auf den Besitzstatus des Geräts. Gehen Sie zum Ändern des Gerätebesitzes zu **Geräte** > **Alle Geräte**, klicken Sie auf das Gerät und dann auf **Eigenschaften**, und ändern Sie den **Gerätebesitz**.

### <a name="imei-specifications"></a>IMEI-Spezifikationen
Detaillierte Angaben über International Mobile Equipment Identifier finden Sie unter [3GGPP TS 23.003](https://portal.3gpp.org/desktopmodules/Specifications/SpecificationDetails.aspx?specificationId=729).

## <a name="change-device-ownership"></a>Ändern des Gerätebesitzes

Die Geräteeigenschaften zeigen den **Besitz** für jeden Gerätedatensatz in Intune an. Als Administrator können Sie Geräte als **Persönlich** oder **Unternehmen** festlegen.

**So ändern Sie den Gerätebesitz:**
1. Navigieren Sie in Intune im Azure-Portal zu **Geräte** > **Alle Geräte**, und wählen Sie das Gerät aus.
2. Wählen Sie **Eigenschaften** aus.
3. Geben Sie den **Gerätebesitz** als **Persönlich** oder **Unternehmen** an.

   ![Screenshot der Geräteeigenschaften, der die Optionen der Gerätekategorie und des Gerätebesitzes anzeigt.](./media/device-properties.png)
