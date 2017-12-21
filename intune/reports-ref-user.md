---
title: "Benutzer – Intune Data Warehouse | Microsoft-Dokumentation"
description: "Referenzthema für die Kategorie „Benutzer“ der Entitätsauflistungen in der Intune Data Warehouse-API."
keywords: Intune Data Warehouse
author: erikre
ms.author: erikre
manager: angrobe
ms.date: 12/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: C29A6EEA-72B7-427E-9601-E05B408F3BB0
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 917c9585ffe17f9d090c519f716d284aa1b932b8
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2017
---
# <a name="reference-for-user-entity"></a>Verweis für die Benutzerentität

Die **Benutzer** Kategorie enthält die **Benutzer** Entität, die Eigenschaften der Benutzerrolle in das Datenmodell definiert.

## <a name="user"></a>User

Die Entität **User** (Benutzer) listet alle Benutzer von Azure Active Directory (Azure AD) mit zugewiesenen Lizenzen in Ihrem Unternehmen auf.

Die **Benutzer** entitätsauflistung Benutzerdaten enthält. Zu diesen Datensätzen gehören Benutzerzustände während der Datensammlung, selbst wenn der Benutzer entfernt wurde. Beispielsweise kann ein Benutzer in Intune hinzugefügt und dann im Verlauf des letzten Monats entfernt worden sein. Auch wenn dieser Benutzer zum Zeitpunkt der Berichterstellung nicht vorhanden ist, liegen Angaben zu Benutzer und Zustand in den Daten aus dem vorherigen Monat vor. Sie können einen Bericht erstellen, der die Dauer der Präsenz des Benutzers in Ihren Daten zeigt.

| Eigenschaft  | Beschreibung | Beispiel |
|---------|------------|--------|
| UserKey |Eindeutiger Bezeichner des Benutzers im Data Warehouse – Ersatzschlüssel |123 |
| UserId |Eindeutiger Bezeichner des Benutzers – Ähnlich wie UserKey, ist jedoch ein natürlicher Schlüssel |b66bc706-ffff-7437-0340-032819502773 |
| UserEmail |E-Mail-Adresse des Benutzers |John@constoso.com |
| UPN | Der Prinzipalname des Benutzers. | John@constoso.com |
| DisplayName |Anzeigename des Benutzers |John |
| IntuneLicensed |Gibt an, ob dieser Benutzer über Intune lizenziert ist oder nicht. |Wahr/falsch |
| IsDeleted | Gibt an, ob alle Lizenzen des Benutzers abgelaufen sind und ob der Benutzer daher aus Intune entfernt wurde. Dieses Flag wird für einen einzelnen Datensatz nicht geändert. Stattdessen wird ein neuer Datensatz für einen neuen Benutzerzustand erstellt. |Wahr/falsch |
| StartDateInclusiveUTC |Bei „IsDeleted = FALSE“ gibt dieser DateTime-Wert in UTC an, wann dem Benutzer eine Lizenz zugewiesen wurde und ab wann er in Intune vorhanden war. Bei „IsDeleted = TRUE“ gibt dieser DateTime-Wert in UTC an, wann die Lizenz des Benutzers abgelaufen ist und wann der Benutzer aus Intune entfernt wurde. |23.11.2016 12:00:00 Uhr |
| EndDateExclusiveUTC |Bei „IsDeleted = FALSE“ gibt dieser DateTime-Wert in UTC an, wann die Lizenz des Benutzers abgelaufen ist und wann der Benutzer aus Intune entfernt wurde. Die Lizenz ist irgendwann am Vortag abgelaufen. Bei „IsDeleted = TRUE“ gibt dieser DateTime-Wert in UTC an, wann der Benutzer eine neue Lizenz erhalten hat und in Intune neu erstellt wurde.  |23.11.2016 12:00:00 Uhr |
| IsCurrent |Gibt an, ob dieser Datensatz den aktuellen Zustand des Benutzers darstellt. Für einen einzelnen Benutzer können mehrere Datensätze vorhanden sein, aber nur einer davon stellt den aktuellen Zustand dar.  |Wahr/falsch |
| RowLastModifiedDateTimeUTC |Datum und Uhrzeit in UTC, als der Datensatz im Data Warehouse zuletzt geändert wurde  |23.11.2016 12:00:00 Uhr |

## <a name="next-steps"></a>Nächste Schritte
 - Sie können die Entitätssammlung **Aktueller Benutzer** verwenden, um die Benutzerdaten auf Benutzer zu beschränken, die derzeit aktiv sind. Weitere Informationen finden Sie unter [Referenz für die Entität „Aktueller Benutzer“](reports-ref-current-user.md).
 - Weitere Informationen zur Nachverfolgung der Benutzerlebensdauer über das Data Warehouse in Intune finden Sie unter [Darstellung der Benutzerlebensdauer im Intune Data Warehouse](reports-ref-user-timeline.md).
