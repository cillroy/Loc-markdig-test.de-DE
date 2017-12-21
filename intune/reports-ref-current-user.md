---
title: Aktueller Benutzer - Datawarehouse mit Intune | Microsoft Docs
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
ms.assetid: C10E6752-E925-40AD-ABBF-6B621FB7AFC4
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: cabf39f603ac93a0716594c44174908e7c999e5c
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2017
---
# <a name="reference-for-current-user-entity"></a>Referenz für die aktuelle Benutzerentität

Die **Aktueller Benutzer** Kategorie enthaltenen Eigenschaften der Benutzerrolle in das Datenmodell. Die Entitätssammlung **Aktueller Benutzer** ist auf die derzeit aktiven Benutzer begrenzt. Die Entität enthält alle Azure Active Directory-Benutzer, denen derzeit eine Lizenz zugewiesen ist. Bei der Lizenz kann es sich um eine Intune-Lizenz, eine Hybrid-Lizenz oder eine Microsoft Office 365-Lizenz handeln. Wenn ein Benutzer entfernt wurde, werden sie nicht in der Auflistung des aktuellen Benutzers dargestellt. Eine Sammlung mit dem Änderungsverlauf der Benutzerzustände finden Sie unter [Referenz für die Entität „Benutzer“](reports-ref-user.md).


## <a name="current-user"></a>Aktueller Benutzer

Die **Aktueller Benutzer** Entität Listet alle Benutzer auf die Azure Active Directory (Azure AD) mit zugewiesenen Lizenzen in Ihrem Unternehmen.

| Eigenschaft  | Beschreibung | Beispiel |
|---------|------------|--------|
| UserKey |Eindeutiger Bezeichner des Benutzers im Data Warehouse – Ersatzschlüssel |123 |
| UserId |Eindeutiger Bezeichner des Benutzers – Ähnlich wie UserKey, ist jedoch ein natürlicher Schlüssel |b66bc706-ffff-7437-0340-032819502773 |
| UserEmail |E-Mail-Adresse des Benutzers |John@constoso.com |
| UPN | Der Prinzipalname des Benutzers. | John@constoso.com |
| DisplayName |Anzeigename des Benutzers |John |
| IntuneLicensed |Gibt an, ob dieser Benutzer über Intune lizenziert ist oder nicht. |Wahr/falsch |
| StartDateInclusiveUTC |Datum und Uhrzeit in UTC, als der Benutzer im Data Warehouse erstellt wurde |23.11.2016 12:00:00 Uhr |
| RowLastModifiedDateTimeUTC |Datum und Uhrzeit in UTC, als dieser Benutzer das letzte Mal im Data Warehouse geändert wurde |23.11.2016 12:00:00 Uhr |

## <a name="next-steps"></a>Nächste Schritte
 - Sie können die **Benutzer** entitätsauflistung, um die Benutzerdaten für Benutzer zu erweitern, die nicht aktiv sind. Weitere Informationen finden Sie unter [Referenz für die Entität „Benutzer“](reports-ref-user.md).
 - Informationen zur Nachverfolgung der Benutzerlebensdauer über das Data Warehouse in Intune finden Sie unter [Darstellung der Benutzerlebensdauer im Intune Data Warehouse](reports-ref-user-timeline.md).
