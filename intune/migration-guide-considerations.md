---
title: "Besondere Überlegungen bei der Migration"
description: "Dieser Artikel bietet spezielle Überlegungen bei der Migration, bevor Sie eine Migrationskampagne starten."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 07/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f29d2894-e98b-4f2c-b444-a8ccc1b7efdd
ms.reviewer: dagerrit
ms.suite: ems
ms.openlocfilehash: 7ff1180275fddc7f0d6ef957c4680d7c34ad471e
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2017
---
# <a name="special-migration-considerations"></a>Besondere Überlegungen bei der Migration

Es gibt spezielle Aspekte bei der Migration, die je nach vorhandener Umgebung des MDM-Anbieters zu berücksichtigen sind.

## <a name="factory-reset-for-apples-device-enrollment-program-dep"></a>Apple Device Enrollment Programm (DEP) auf Werkseinstellungen zurücksetzen

Das Apple-Programm zur Geräteregistrierung (Device Enrollment Program, DEP) legt Gerätekonfigurationen fest, die vom Endbenutzer nicht entfernt werden können. Wenn Sie die erweiterten Verwaltungsfunktionen von DEP beibehalten möchten, muss das Gerät für die Anmeldung bei Intune auf die Werkseinstellungen zurückgesetzt werden.

Um die Geräte in Intune weiter mit dem Programm zur Geräteregistrierung zu verwalten, [richten Sie die iOS-Geräteregistrierung mit dem Programm zur Geräteregistrierung ein](device-enrollment-program-enroll-ios.md).


## <a name="next-steps"></a>Nächste Schritte

[Phase 2: Die Migration](migration-guide-campaign.md)
