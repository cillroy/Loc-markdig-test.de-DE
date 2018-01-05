---
title: Richtlinien | Microsoft-Dokumentation
description: "Referenzthema für die Kategorie „Richtlinien“ der Entitätsauflistungen in der Intune Data Warehouse-API."
keywords: Intune Data Warehouse
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 07/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: D5ADB9D8-D46A-43BD-AB0F-D6927508E3F4
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 72a65fa2dfd3785f6c5ee913f1d29352a8fbeaf0
ms.sourcegitcommit: e37e916e2bf14f092d3a767bc90d68c181d739fb
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/03/2018
---
# <a name="reference-for-policy-entities"></a>Verweis für Richtlinienentitäten

Die Kategorie **Policy** (Richtlinien) enthält Entitäten für mobile Geräte, die folgende Informationen nachverfolgen:

  -  Inventar der Gerätekonfigurationsprofile, Appkonfigurationsprofile und Kompatibilitätsrichtlinien  
  -  Anzahl der Geräte mit dem Zustand „erfolgreich“, „ausstehend“, „fehlerhaft“ oder „Fehler“ pro Tag  
  -  Anzahl der Benutzer mit dem Zustand „erfolgreich“, „ausstehend“, „fehlerhaft“ oder „Fehler“ pro Tag  
  -  Gesamtzahl der Geräte mit dem Zustand „erfolgreich“, „ausstehend“, „fehlerhaft“ oder „Fehler“  

## <a name="policy"></a>Richtlinie

Die Entität **Policy** (Richtlinie) listet Gerätekonfigurationsprofile, Appkonfigurationsprofile und Kompatibilitätsrichtlinien auf. Sie können die Richtlinien mit der mobilen Geräteverwaltung (MDM) zu einer Gruppe in Ihrem Unternehmen zuweisen.

| Eigenschaft  | Beschreibung | Beispiel |
|---------|------------|--------|
| PolicyKey |Eindeutiger Schlüssel, der die Richtlinie im Data Warehouse darstellen soll |123 |
| PolicyId |Eindeutiger Bezeichner der Richtlinie im Data Warehouse |b66bc706-ffff-7437-0340-032819502773 |
| PolicyName |Name der Richtlinie |"Windows 10-Baseline" |
| PolicyVersion |Version der Richtlinie Wenn die Richtlinie bearbeitet oder geändert wird, wird eine neuere Version erstellt. |1, 2, 3 |
| isDeleted |Gibt an, ob der Richtliniendatensatz aktualisiert wurde.  <br>Wahr: Richtlinie verfügt über einen neuen Datensatz mit aktualisierten Feldern. <br>Falsch: der neueste Datensatz für diese Richtlinie. |Wahr/falsch |
| StartDateInclusiveUTC |Datum und Uhrzeit in UTC, als diese Richtlinie im Data Warehouse erstellt wurde |23.11.2016 12:00:00 Uhr |
| DeletedDateUTC |Datum und Uhrzeit in UTC, als IsDeleted in TRUE geändert wurde |23.11.2016 12:00:00 Uhr |
| RowLastModifiedDateTimeUTC |Datum und Uhrzeit in UTC, als diese Richtlinie zuletzt im Data Warehouse geändert wurde |23.11.2016 12:00:00 Uhr |

## <a name="policytype"></a>PolicyType

Die Entität **PolicyType** listet Gerätekonfigurationsprofile, Appkonfigurationsprofile und Kompatibilitätsrichtlinien auf. Sie können die Richtlinien mit der mobilen Geräteverwaltung (MDM) zu einer Gruppe in Ihrem Unternehmen zuweisen.

| Eigenschaft  | Beschreibung | Beispiel |
|---------|------------|--------|
| PolicyTypeId |Eindeutiger Bezeichner der Richtlinie im Quellsystem |123 |
| PolicyTypeKey |Eindeutiger Bezeichner der Richtlinie im Data Warehouse |1 |
| PolicyTypeName |Name des Richtlinientyps |Windows 10-Kompatibilitätsrichtlinie |

## <a name="deviceconfiguration"></a>DeviceConfiguration

Die Entität **DeviceConfigurationProfileDeviceActivity** listet die Anzahl der Geräte mit dem Zustand „erfolgreich“, „ausstehend“, „fehlerhaft“ oder „Fehler“ pro Tag auf. Die Anzahl gibt die Gerätekonfigurationsprofile an, die der Entität zugewiesen sind. Wenn ein Gerät beispielsweise den Zustand „erfolgreich“ für alle zugewiesenen Richtlinien aufweist, wird der Zähler für „erfolgreich“ für diesen Tag um eins erhöht. Wenn einem Gerät zwei Profile zugewiesen sind, von denen eines den Zustand „erfolgreich“ und eines den Zustand „Fehler“ aufweist, erhöht die Entität den Zähler für „erfolgreich“ und versetzt das Gerät in den Zustand „Fehler“. Die Entität listet für die letzten 30 Tage auf, wie viele Geräte an einem bestimmten Tag in welchem Zustand waren.

| Eigenschaft  | Beschreibung | Beispiel |
|---------|------------|--------|
| DateKey |Date Key für den Zeitpunkt als das Einchecken der Gerätekonfigurationsprofile im Data Warehouse aufgezeichnet wurde |20160703 |
| Pending |Anzahl eindeutiger Geräte im Zustand „ausstehend“ |123 |
| Succeeded |Anzahl eindeutiger Geräte im Zustand „erfolgreich“ |12 |
| Fehler |Anzahl eindeutiger Geräte im Zustand „Fehler“ |10 |
| Failed |Anzahl eindeutiger Geräte im Zustand „fehlerhaft“ |2 |

## <a name="userconfiguration"></a>UserConfiguration

Die Entität **UserConfigurationProfileDeviceActivity** listet die Anzahl der Benutzer mit dem Zustand „erfolgreich“, „ausstehend“, „fehlerhaft“ oder „Fehler“ pro Tag auf. Die Anzahl gibt die Gerätekonfigurationsprofile an, die der Entität zugewiesen sind. Wenn ein Benutzer beispielsweise den Zustand „erfolgreich“ für alle zugewiesenen Richtlinien aufweist, wird der Zähler für „erfolgreich“ für diesen Tag um eins erhöht. Wenn einem Benutzer zwei Profile zugewiesen sind, von denen eines den Zustand „erfolgreich“ und eines den Zustand „Fehler“ aufweist, zählen wir den Benutzer für den Zustand „Fehler“.  Die Entität **UserConfigurationProfileDeviceActivity** listet für die letzten 30 Tage auf, wie viele Benutzer an einem bestimmten Tag in welchem Zustand waren.

| Eigenschaft  | Beschreibung | Beispiel |
|---------|------------|--------|
| DateKey |Date Key für den Zeitpunkt als das Einchecken der Gerätekonfigurationsprofile im Data Warehouse aufgezeichnet wurde |20160703 |
| Pending |Anzahl eindeutiger Benutzer im Zustand „ausstehend“ |123 |
| Succeeded |Anzahl eindeutiger Benutzer im Zustand „erfolgreich“ |12 |
| Fehler |Anzahl eindeutiger Benutzer im Zustand „Fehler“ |10 |
| Failed |Anzahl eindeutiger Benutzer im Zustand „fehlerhaft“ |2 |

## <a name="policytypeactivity"></a>PolicyTypeActivity

Die Entität **PolicyTypeActivity** listet die Gesamtzahl der Geräte im Zustand „erfolgreich“, „ausstehend“, „fehlerhaft“ oder „Fehler“ auf. Diese Zustände werden im Bezug auf ein Gerätekonfigurationsprofil, ein Appkonfigurationsprofil oder eine Kompatibiliätsrichtlinie pro Tag aufgelistet.


| Eigenschaft  | Beschreibung | Beispiel |
|---------|------------|--------|
| DateKey |Date Key für den Zeitpunkt, als das Einchecken der Gerätekonfigurationsprofile im Data Warehouse aufgezeichnet wurde |20160703 |
| PolicyKey |Der Richtlinienschlüssel kann mit der Richtlinie verknüpft werden, um den Richtliniennamen zu erhalten. |Windows 10-Baseline |
| PolicyTypeKey |Der Typ des Richtlinienschlüssels kann mit dem Richtlinientyp verknüpft werden, um den Namen des Richtlinientyps zu erhalten. |Windows 10-Kompatibilitätsrichtlinien |
| Pending |Anzahl eindeutiger Geräte im Zustand „ausstehend“ |123 |
| Succeeded |Anzahl eindeutiger Geräte im Zustand „erfolgreich“ |12 |
| Fehler |Anzahl eindeutiger Geräte im Zustand „Fehler“ |10 |
| Fehlerhaft |Anzahl eindeutiger Geräte im Zustand „fehlerhaft“ |2 |
