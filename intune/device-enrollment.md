---
title: "Was ist die Microsoft Intune Geräteregistrierung?"
titlesuffix: Azure portal
description: "In diesem Artikel finden Sie Informationen zur Registrierung bei iOS-, Android- und Windows-Geräten."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 10/23/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6f67fcd2-5682-4f9c-8d74-d4ab69dc978c
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: b1f30c0d6f4af039306a7cb6eb244bc0c8db1f6e
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2018
---
# <a name="what-is-device-enrollment"></a>Was ist die Geräteregistrierung?
[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Dieses Thema beschreibt die Registrierung und die verschiedenen Methoden zum Registrieren von mobilen Geräten in der Intune-Verwaltung.

Sie registrieren Geräte in Intune, um diese Geräte verwalten zu können. Diese Funktion wird in der Intune-Dokumentation als Verwaltung mobiler Geräte (Mobile Device Management, MDM) bezeichnet. Wenn Geräte in Intune registriert werden, erhalten sie ein MDM-Zertifikat, das von den Geräten dann für die Kommunikation mit dem Intune-Dienst verwendet wird.

Auf welche Weise Sie Ihre Geräte registrieren, hängt von Gerätetyp, Besitz und benötigtem Verwaltungsniveau ab. Bei der BYOD-Registrierung (Bring Your Own Device, private Geräte der Mitarbeiter) können die Benutzer ihre privaten Smartphones, Tablets oder PCs selbst registrieren. Die Registrierung von unternehmenseigenen Geräten (corporate-owned devices, COD) macht Verwaltungsszenarios wie die automatische Registrierung, freigegebene Geräte oder Anforderungen für eine vorautorisierte Registrierung möglich.

Wenn Sie Exchange ActiveSync entweder lokal oder in der Cloud gehostet verwenden, können Sie eine einfache Intune-Verwaltung ohne Registrierung aktivieren (weitere Informationen folgen in Kürze). Sie können Windows-PCs als mobile Geräte verwalten. Dieses Vorgehen wird unten als empfohlenes Verfahren beschrieben.


## <a name="overview-of-device-enrollment-methods"></a>Übersicht über die Geräteregistrierungsmethoden

Die folgende Tabelle bietet einen Überblick über die Intune-Registrierungsmethoden, die zusammen mit den jeweiligen Funktionen und Anforderungen nachfolgend beschrieben werden.

**Legende**

- **Zurücksetzen erforderlich** – Das Gerät wird bei der Registrierung auf die Werkseinstellungen zurückgesetzt.
- **Benutzeraffinität** – Geräte werden Benutzern zugeordnet. Weitere Informationen finden Sie auf der Seite [Registrieren firmeneigener iOS-Geräte in Microsoft Intune](device-enrollment-program-enroll-ios.md).
- **Gesperrt** – Es wird verhindert, dass Benutzer die Registrierung von Geräten aufheben.

**iOS-Registrierungsmethoden**

| **Methode** |  **Zurücksetzen erforderlich** |    **Benutzeraffinität**   |   **Gesperrt** | **Details** |
|:---:|:---:|:---:|:---:|:---:|
|**[BYOD](#byod)** | Nein|    Ja  |   Nein | [Weitere Informationen](./apple-mdm-push-certificate-get.md)|
|**[DEM](#dem)**|   Nein |Nein |Nein  | [Weitere Informationen](./device-enrollment-program-enroll-ios.md)|
|**[DEP](#dep)**|   Ja  |   Optional |  Optional|[Weitere Informationen](./device-enrollment-program-enroll-ios.md)|
|**[USB (Setup-Assistent)](#usb-sa)**| Ja  |   Optional |  Nein| [Weitere Informationen](./apple-configurator-setup-assistant-enroll-ios.md)|
|**[USB (direkt)](#usb-direct)**| Nein |    Nein  | Nein|[Weitere Informationen](./apple-configurator-direct-enroll-ios.md)|

**Windows-Registrierungsmethoden**

| **Methode** |  **Zurücksetzen erforderlich** |    **Benutzeraffinität**   |   **Gesperrt** | **Details**|
|:---:|:---:|:---:|:---:|:---:|:---:|
|**[BYOD](#byod)** | Nein |   Ja  |   Nein | [Weitere Informationen](windows-enroll.md)|
|**[DEM](#dem)**|   Nein |Nein |Nein  |[Weitere Informationen](device-enrollment-manager-enroll.md)|
|**Automatische Registrierung** | Nein |Ja  |Nein | [Weitere Informationen](./windows-enroll.md#enable-windows-10-automatic-enrollment)|
|**Massenregistrierung** |Nein |Nein |Nein | [Weitere Informationen](./windows-bulk-enroll.md) |

**Android-Registrierungsmethoden**

| **Methode** |  **Zurücksetzen erforderlich** |    **Benutzeraffinität**   |   **Gesperrt** | **Details**|
|:---:|:---:|:---:|:---:|:---:|:---:|
|**[BYOD](#byod)** | Nein|    Ja  |   Nein | [Weitere Informationen](./android-enroll.md)|
|**[DEM](#dem)**|   Nein |Nein |Nein  |[Weitere Informationen](./device-enrollment-program-enroll-ios.md)|
|**Android for Work**| Nein | Ja  | Nein| [Weitere Informationen](./android-enroll.md#enable-enrollment-of-android-for-work-devices) |


## <a name="byod"></a>BYOD
BYOD-Benutzer (Bring Your Own Device) installieren die Unternehmensportal-App und führen diese zur Registrierung ihrer Geräte aus. Dieses Programm ermöglicht Benutzern den Zugriff auf Unternehmensressourcen wie E-Mails.

## <a name="corporate-owned-devices"></a>Firmeneigene Geräte
Im Folgenden werden Registrierungsszenarien für unternehmenseigene Geräte vorgestellt. iOS-Geräte können direkt über die von Apple bereitgestellten Tools registriert werden. Alle Gerätetypen können von einem Administrator oder Manager die unter Verwendung des Geräteregistrierungs-Managers registriert werden. Geräte mit einer IMEI-Nummer können auch als firmeneigene Geräte identifiziert und gekennzeichnet werden, um COD-Szenarien zu unterstützen.

### <a name="dem"></a>Geräteregistrierungs-Manager (DEM)
Der Geräteregistrierungs-Manager (DEM) ist ein besonderes Benutzerkonto, das zum Registrieren und Verwalten mehrerer firmeneigener Geräte verwendet wird. Manager können das Unternehmensportal installieren und viele benutzerlose Geräte registrieren. Erfahren Sie mehr über den [DEM](./device-enrollment-manager-enroll.md).

### <a name="dep"></a>DEP (Device Enrollment Program)
Mit der Apple DEP-Verwaltung (Device Enrollment Program, Programm zur Geräteregistrierung) können Sie Richtlinien erstellen und „drahtlos“ auf iOS-Geräten bereitstellen, die mit DEP erworben wurden und verwaltet werden. Das Gerät wird beim ersten Einschalten durch den Benutzer registriert und führt dann den iOS-Setup-Assistenten aus. Diese Methode unterstützt den überwachten Modus von iOS, der zulässt, dass ein Gerät mit bestimmten Funktionen konfiguriert wird.

Weitere Informationen zur iOS DEP-Registrierung finden Sie unter:

- [Auswählen der Registrierungsmethode für iOS-Geräte](ios-enroll.md)
- [Registrieren von iOS-Geräten mithilfe des Programms zur Geräteregistrierung](https://docs.microsoft.com/intune/device-restrictions-ios#device-enrollment-program)

### <a name="usb-sa"></a>USB (Setup-Assistent)
IT-Administratoren benutzen Apple Configurator über USB, um jedes unternehmenseigene Gerät manuell für die Registrierung mit dem Setup-Assistenten vorzubereiten. Der IT- Administrator erstellt ein Registrierungsprofil und exportiert dieses in Apple Configurator. Wenn die Benutzer ihre Geräte erhalten, werden sie aufgefordert, den Setup-Assistenten auszuführen. Diese Methode unterstützt den **überwachten iOS-Modus**, der wiederum folgende Funktionen ermöglicht:
  - Gesperrte Registrierung
  - Kioskmodus und andere erweiterte Konfigurationen und Einschränkungen

Weitere Informationen zur Registrierung über den Setup-Assistenten mit iOS Apple Configurator finden Sie unter:

- [Auswählen der Registrierungsmethode für iOS-Geräte](enrollment-method-choose-ios.md)
- [Registrieren von iOS-Geräten mithilfe von Configurator und Setup-Assistent](apple-configurator-setup-assistant-enroll-ios.md)

### <a name="usb-direct"></a>USB (direkt)
Für die direkte Registrierung muss der Administrator jedes Gerät manuell registrieren, indem er eine Registrierungsrichtlinie erstellt und in Apple Configurator exportiert. Über USB angeschlossene, unternehmenseigene Geräte werden direkt registriert, ohne dass ein Zurücksetzen auf Werkseinstellungen erforderlich ist. Geräte werden als benutzerlose Geräte verwaltet. Sie werden nicht gesperrt oder überwacht und unterstützen nicht den bedingten Zugriff, die Erkennung von Jailbreaks oder die Verwaltung mobiler Geräte.

Weitere Informationen zur iOS-Registrierung finden Sie unter:

- [Auswählen der Registrierungsmethode für iOS-Geräte](enrollment-method-choose-ios.md)
- [Registrieren von iOS-Geräten mithilfe von Configurator und direkter Registrierung](apple-configurator-direct-enroll-ios.md)

## <a name="mobile-device-management-with-exchange-activesync-and-intune"></a>Verwaltung mobiler Geräte mit Exchange ActiveSync und Intune
Mobile Geräte, die nicht registriert, aber mit Exchange ActiveSync (EAS) verbunden sind, können von Intune mit der EAS-MDM-Richtlinie verwaltet werden. Intune verwendet Exchange Connector für die Kommunikation mit EAS, entweder lokal oder in der Cloud gehostet. Weitere Informationen folgen in Kürze.

## <a name="mobile-device-cleanup-after-mdm-certificate-expiration"></a>Bereinigen mobiler Geräte nach Ablauf des MDM-Zertifikats

Das MDM-Zertifikat wird automatisch erneuert, wenn mobile Geräte mit dem Intune-Dienst kommunizieren. Wenn mobile Geräte zurückgesetzt werden oder für längere Zeit keine Kommunikation mit dem Intune-Dienst stattfindet, wird das MDM-Zertifikat nicht erneuert. Das Gerät wird 180 Tage nach Ablauf des MDM-Zertifikats aus dem Azure-Portal entfernt.
