---
title: "Einstellungen für Geräteeinschränkungen für macOS"
titlesuffix: Azure portal
description: "In diesem Artikel lernen Sie die Intune-Einstellungen zur Steuerung von Geräteeinstellungen und -funktionen auf macOS-Geräten kennen."
keywords: 
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 08/01/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3129cbaf-96c2-4837-8907-ca87a605a496
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: e88ab829b2ced4693a804abcaf8b65a0794a84cc
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2017
---
# <a name="macos-device-restriction-settings-in-microsoft-intune"></a>Einstellungen für Geräteeinschränkungen für macOS-Geräte in Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Verwenden Sie diese Einstellungen zum Verwalten von macOS-Geräten in einem Geräteeinschränkungsprofil.

## <a name="password"></a>Kennwort
-   **Kennwort:** Der Endbenutzer muss ein Kennwort eingeben, um auf das Gerät zugreifen zu können.
    -   **Erforderlicher Kennworttyp:** Geben Sie an, ob das Kennwort rein numerisch sein darf oder ob es alphanumerisch sein muss (also Buchstaben und Zahlen enthalten muss). Diese Einstellung wird lediglich unter Mac OS X 10.10.3 und höher unterstützt.
    -   **Anzahl nicht alphanumerischer Zeichen im Kennwort:** Geben Sie die erforderliche Anzahl komplexer Zeichen im Kennwort an (**0** bis **4**).<br>Bei einem komplexen Zeichen handelt es sich um ein Symbol, wie **?**
    -   **Minimale Kennwortlänge:** Geben Sie die Mindestanzahl von Zeichen an, die Benutzer für das Kennwort festlegen müssen (zwischen **4** und **16** Zeichen).
    -   **Einfache Kennwörter:** Erlauben Sie die Verwendung einfacher Kennwörter wie **0000** oder **1234**.
    -   **Maximaler Zeitraum der Bildschirmsperre (in Minuten) bis zur Anforderung eines Kennworts:** Geben Sie an, wie lange der Computer inaktiv sein muss, bevor er mithilfe eines Kennworts entsperrt werden muss.
    -   **Maximaler Zeitraum der Inaktivität (in Minuten) bis zur Bildschirmsperrung:** Geben Sie die Zeitdauer an, die der Computer inaktiv sein muss, bevor der Bildschirms gesperrt wird.
    -   **Kennwortablauf (Tage):** Geben Sie an, nach wie vielen Tagen der Benutzer das Kennwort ändern muss (**1** bis **255** Tage).
    -   **Wiederverwendung vorheriger Kennwörter verhindern:** Geben Sie die Anzahl von vorherigen Kennwörtern an, die nicht erneut verwendet werden dürfen (**1** bis **24**).

## <a name="restricted-apps"></a>Eingeschränkte Apps

In der Liste der eingeschränkten Apps können Sie eine der folgenden Listen konfigurieren:

**Unzulässige Apps:** Listet die (nicht von Intune verwalteten) Apps auf, die Benutzer nicht installieren und ausführen dürfen.
**Genehmigte Apps:** Listet die Apps auf, die Benutzer installieren dürfen. Um die Kompatibilität zu gewährleisten, dürfen Benutzer keine Apps installieren, die in dieser Liste nicht aufgeführt sind. Apps, die von Intune verwaltet werden, sind automatisch zugelassen.

Klicken Sie zum Konfigurieren einer Liste auf **Hinzufügen**. Geben Sie dann einen Namen Ihrer Wahl sowie optional den Herausgeber der App und die Paket-ID der App an (z.B. *com.apple.calculator*).

## <a name="domains"></a>Domains

### <a name="unmarked-email-domains"></a>Nicht markierte E-Mail-Domänen

Fügen Sie im Feld **E-Mail-Domänen-URL** eine oder mehrere URLs der Liste hinzu. Wenn Endbenutzer eine E-Mail von einer anderen Domäne als einer erhalten, die Sie konfiguriert haben, wird die E-Mail in der iOS-Mail-App als nicht vertrauenswürdig gekennzeichnet.

