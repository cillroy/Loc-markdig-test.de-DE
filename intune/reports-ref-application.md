---
title: Anwendung | Microsoft-Dokumentation
description: "Referenzthema für die Kategorie „Anwendung“ der Entitätsauflistungen in der Intune Data Warehouse-API"
keywords: Intune Data Warehouse
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 12/11/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: A92DEF30-5D01-4774-9917-E26F5F0E2E68
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: e80758f0fc96394a4f1c474037b7584fa39b1678
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2017
---
# <a name="reference-for-application-entities"></a>Verweis für Anwendungsentitäten

Die Kategorie **Anwendung** (Application) enthält Entitäten für mobile Geräte, die folgende Informationen nachverfolgen:

  -  Version einer App
  -  Installationsquelle einer App
  -  Typ der Entwickler, die eine App entwickelt haben
  -  Typen verwalteter Software für eine App, z.B. **sidecar** oder **desktop**
  -  Volume Purchasing Program (VPP) – Status einer App

## <a name="apprevision"></a>AppRevision

Die Entität **AppRevision** führt alle Versionen einer App auf.

| Eigenschaft  | Beschreibung | Beispiel |
|---------|------------|--------|
| AppKey |Eindeutiger Bezeichner der App |123 |
| ApplicationId |Eindeutiger Bezeichner einer App. Ähnlich wie AppKey, dieser Schlüssel ist jedoch ein natürlicher Schlüssel. |b66bc706-ffff-7437-0340-032819502773 |
| Revision |Die Version, die vom Administrator beim Upload der Binärdatei erwähnt wurde |2 |
| Titel |Titel der App |Excel |
| Herausgeber |Herausgeber der App |Microsoft |
| UploadState |Hochladestatus der App |1 |
| AppTypeKey |Der Verweis zu AppType wird im folgenden Abschnitt beschrieben. | |
| VppProgramTypeKey |Der Verweis zu VppProgramType wird weiter unten beschrieben. | |
| CreationTime |Die Uhrzeit, zu der diese Revision erstellt wurde |23.11.2016 12:00:00 Uhr |
| ModifiedTime |Der letzte Zeitpunkt, zu dem eine Änderung an einem mit dieser Revision verknüpften Element vorgenommen wurde |23.11.2016 12:00:00 Uhr |
| Size |Größe der Binärdatei | |
| StartDateInclusiveUTC |Datum und Uhrzeit in UTC, als diese App-Revision im Data Warehouse erstellt wurde |23.11.2016 12:00:00 Uhr |
| EndDateExclusiveUTC |Datum und Uhrzeit in UTC, als diese App-Revision als veraltet gekennzeichnet wurde |23.11.2016 12:00:00 Uhr |
| IsCurrent |Gibt an, ob diese App-Version im Data Warehouse aktuell ist |Wahr/falsch |
| RowLastModifiedDateTimeUTC |Datum und Uhrzeit in UTC, als diese App-Version zuletzt im Data Warehouse geändert wurde |23.11.2016 12:00:00 Uhr |

## <a name="apptypes"></a>AppTypes

Die Entität **AppTypes** führt die Installationsquelle einer App auf.

| Eigenschaft  | Beschreibung |
|---------|------------|
| AppTypeID |ID für den Typ |
| AppTypeKey |Untergeordneter Schlüssel für den Schlüssel |
| AppTypeName |App-Typ |

### <a name="example"></a>Beispiel

| AppTypeID  | Name | Beschreibung |
|---------|------------|--------|
| 0 |Android Store-App | Eine Android Store-App |
| 1 |Android-Branchen-App | Eine branchenspezifische Android-App |
| 2 |Verwaltete Android Store-App (MAM) | Eine Android Store-App, für die die Verwaltung aktiviert ist |
| 3 |iOS Store-App | Eine iOS Store-App |
| 4 |Branchenspezifische iOS-App | Eine branchenspezifische iOS-App |
| 5 |Verwaltete iOS Store-App (MAM?) | Eine iOS Store-App, die für die Verwaltung aktiviert ist |
| 6 |O365 Pro Plus Suite | Die Office 365 Pro Plus Suite für Windows 10 |
| 7 |Web-App | Eine Web-App |
| 8 |Windows Phone 8.1 Store-App | Eine Windows Phone 8.1 Store-App |
| 9 |Windows Store-App | Eine Windows Store-App |
| 10 |Branchenspezifische Windows-Apps | Eine branchenspezifische Windows-APPX-App |
| 11 |Windows Mobile MSI | Eine branchenspezifische MSI-App |
| 12 |Branchenspezifische Windows Phone-App | Eine branchenspezifische Windows Phone-App |


## <a name="vppprogramtypes"></a>VppProgramTypes

Die Entität **VppProgramTypes** führt mögliche VPP-Programmtypen für eine App auf.

| Eigenschaft  | Beschreibung |
|---------|------------|
| VppProgramTypeID | ID für den Typen |
| VppProgramTypeKey | Ersatzschlüssel für den Schlüssel |
| VppProgramTypeName | Typ des VPP-Programms. |

### <a name="example"></a>Beispiel

| VppProgramID  | Name | Beschreibung |
|---------|------------|--------|
| 3DDA2474-470B-4503-9830-2665C21C1945 | Microsoft | VPP-Programm von Microsoft |
| 00000000-0000-0000-0000-000000000000 | Noch nicht verfügbar. | Standardwert, kein VPP |
| B54814E0-68EA-4BA4-8088-B5AAB58E737B | Apple | VPP-Programm von Apple |



## <a name="applicationinventory"></a>ApplicationInventory

Die Entität **ApplicationInventory** listet die Anwendungen auf, die zum Zeitpunkt der Inventursammlung auf dem Gerät gefunden wurden.

| Eigenschaft  | Beschreibung |
|---------|------------|
| DeviceKey | Dies ist ein Verweis auf die Gerätetabelle, die die Intune-Geräte-ID enthält. |
| DateKey | Verweis auf die Datumstabelle, die den Tag der Inventur angibt |
| ApplicationName | Der Anwendungsname. |
| ApplicationVersion | Anwendungsversion |
| BundleSize | Größe der App in Byte |

## <a name="mobileappinstallstate"></a>MobileAppInstallState

Die **MobileAppInstallState** Entität den Installationsstatus für eine mobile Anwendung darstellt, nachdem sie eine Gruppe, die Geräte, Benutzer oder beides zugewiesen wurde.

| Eigenschaft | Beschreibung |
|---|---|
| AppInstallStateKey | Die eindeutige ID der app des Installationsstatus für Ihr Konto. |
| AppInstallState | Enum-Wert, der die app-Installationsstatus. |
| AppInstallStateName | Name des app-Installationsstatus. |

## <a name="mobileappdeviceuserinstallstatus"></a>MobileAppDeviceUserInstallStatus

Die **MobileAppDeviceUserInstallStatus** eine mobile app-Installationsstatus für ein angegebenes Gerät und den Benutzer darstellt.

| Eigenschaft | Beschreibung |
|---|---|
| DateKey | Schlüssel, der das Datum aus, wenn der Installationsstatus die App, aufgezeichnet wurde. |
| AppKey | Der Schlüssel der mobilen Anwendung verwendet, um eine Instanz eines AppRevision identifiziert. |
| DeviceKey | Schlüssel des ein Zielgerät zum Identifizieren einer Instanz des Geräts verwendet. |
| UserKey | Schlüssel des ein bestimmten Benutzer, die zum Identifizieren einer Instanz des Benutzers verwendet. |
|AppInstallStateKey | Schlüssel der app-Installationsstatus verwendet, um eine Instanz eines MobileAppInstallState identifiziert. |
| ErrorCode | Die von der app-Installer, der mobile-Plattform oder den Dienst bezieht sich auf die Installation der app zurückgegebene Fehlercode. |
