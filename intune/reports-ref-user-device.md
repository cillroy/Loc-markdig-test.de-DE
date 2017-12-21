---
title: "Zuordnung von Benutzergeräten – Intune Data Warehouse | Microsoft-Dokumentation"
description: "Eine Liste der Änderungen in der Intune Data Warehouse-API."
keywords: Intune Data Warehouse
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 10/19/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 777484A7-09CE-4409-987F-76B3F87DFE93
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 4c47455b0139f7451796257a77859cbd9899a7dd
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2017
---
# <a name="user-device-association"></a>Zuordnung der Benutzergeräte

Die Entität **UserDeviceAssociation** enthält Zuweisungen von Benutzergeräten in Ihrer Organisation.

| Name               | Beschreibung                                                                                      | Beispiel                |
|--------------------|--------------------------------------------------------------------------------------------------|------------------------|
| UserKey            | Eindeutiger Bezeichner für den Benutzer im Data Warehouse (Ersatzschlüssel)                              | 123                    |
| DeviceKey          | Eindeutiger Bezeichner für das Gerät im Data Warehouse                                            | 123                    |
| CreatedDateTimeUTC | Datum und Uhrzeit, als die Benutzergerätezuordnung erstellt wurde Verwendet UTC-Format                                | 23.11.2016 12:00:00 Uhr |
| IsDeleted          | Gibt an, dass der Benutzer dieses Geräts die Registrierung aufgehoben hat und die Zuordnung nicht mehr aktuell ist | Wahr/falsch             |
| EndedDateTimeUTC   | Datum und Uhrzeit in UTC, als IsDeleted in **TRUE** geändert wurde                                              | 23.06.2017, 12:00:00 Uhr |
