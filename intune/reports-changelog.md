---
title: "Änderungsprotokoll für Intune Data Warehouse | Microsoft-Dokumentation"
description: "Eine Liste der Änderungen in der Intune Data Warehouse-API."
keywords: Intune Data Warehouse
author: erikre
ms.author: mabrigg
manager: erikre
ms.date: 12/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: E85DBB2D-67BB-4E10-82D6-E43046B9C43C
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 0d2625cda3fad8683571059d4ed5f75d6c7ae122
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2017
---
# <a name="change-log-for-the-intune-data-warehouse-api"></a>Änderungsprotokoll für die Intune Data Warehouse-API

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Bleiben Sie auf dem neuesten Stand bezüglich Updates für Intune Data Warehouse.

## <a name="1710"></a>1710
_Veröffentlicht im November 2017_

### <a name="a-new-entity-collection-named-current-user-is-limited-to-currently-active-user-data----1544273---"></a>Eine neue Entitätssammlung namens „Aktueller Benutzer“ ist auf die Daten der momentan aktiven Benutzer beschränkt.<!-- 1544273 -->

Die **Benutzer** entitätsauflistung enthält alle Azure Active Directory (Azure AD)-Benutzer mit zugewiesenen Lizenzen in Ihrem Unternehmen. Zu diesen Datensätzen gehören Benutzerzustände während der Datensammlung, selbst wenn der Benutzer entfernt wurde. Beispielsweise kann ein Benutzer in Intune hinzugefügt und dann im Verlauf des letzten Monats entfernt worden sein. Auch wenn dieser Benutzer zum Zeitpunkt der Berichterstellung nicht vorhanden ist, liegen Angaben zu Benutzer und Zustand in den Daten vor. Sie können einen Bericht erstellen, der die Dauer der Präsenz des Benutzers in Ihren Daten zeigt.

Im Gegensatz dazu enthält die neue Entitätssammlung **Aktueller Benutzer** nur Benutzer, die nicht entfernt wurden. Die Entitätssammlung **Aktueller Benutzer** enthält nur die derzeit aktiven Benutzer. Informationen zur Entitätssammlung **Aktueller Benutzer** finden Sie unter [Referenz für die Entität „Aktueller Benutzer“](reports-ref-current-user.md).

## <a name="1709"></a>1709
_Veröffentlicht im Oktober 2017_

### <a name="user-device-association-entity-collection-added-to-intune-data-warehouse-data-model----1187917---"></a>Hinzufügen der Entitätssammlung von Benutzergerätezuordnungen zum Intune Data Warehouse-Datenmodell <!-- 1187917 -->

Mithilfe von Informationen über Benutzergerätezuordnungen können Sie Berichte und Datenvisualisierungen erstellen, die Entitätssammlungen von Benutzern und Geräten zuordnet. Auf das Datenmodell kann über die Power BI-Datei (PBIX) zugegriffen werden, die über die Data Warehouse-Seite von Intune, den OData-Endpunkt oder durch die Entwicklung eines benutzerdefinierten Clients abgerufen wird. Weitere Informationen finden Sie unter [Zuordnung der Benutzergeräte](reports-ref-user-device.md).

### <a name="new-entities-in-the-in-data-warehouse-data-model----1479526--------"></a>Neue Entitäten im Data Warehouse-Datenmodell<!-- 1479526 --><!-- -->

 - Die Entität [**UserDeviceAssociation**](reports-ref-user-device.md) wurde hinzugefügt. **UserDeviceAssociation** enthält Zuweisungen von Benutzergeräten in Ihrer Organisation. Mithilfe von Informationen über Benutzergerätezuordnungen können Sie Berichte und Datenvisualisierungen erstellen, die Entitätssammlungen von Benutzern und Geräten zuordnet.  
 - Die Entität [ **IntuneManagementExtension**](reports-ref-intunemanagementextension.md) wurde hinzugefügt. **IntuneManagementExtension** enthält Entitäten für mobile Geräte zur Nachverfolgung von Informationen, wie z. B. Version und Installationsstatus.

## <a name="next-steps"></a>Nächste Schritte
 - Erfahren Sie [jede Woche die Neuerungen in Intune](whats-new.md). Sie erhalten auch Informationen zu bevorstehenden Änderungen, wichtige Hinweise zum Dienst und Informationen zu vorherigen Releases.
 - Lesen Sie den [Microsoft Intune-Blog](http://go.microsoft.com/fwlink/?LinkID=273882).
