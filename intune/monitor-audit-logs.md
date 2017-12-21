---
title: "Überwachungsprotokolle für Intune-Aktivitäten"
description: "Erfahren Sie, wie Überwachungsprotokolle zu überprüfen, die Intune-Aktivitäten erfassen"
keywords: 
author: dougeby
manager: angrobe
ms.date: 12/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6ee841cc-5694-4ba1-8f66-1d58edec30a4
ms.openlocfilehash: 30067f60163a644f4347c51c249c25fb3428f8ba
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2017
---
# <a name="audit-logs-for-intune-activities"></a>Überwachungsprotokolle für Intune-Aktivitäten
Überwachungsprotokolle bieten Ihnen einen Datensatz von Aktivitäten, die eine Änderung in Microsoft Intune zu generieren. Erstellen, aktualisieren (Bearbeiten), zu löschen, und weisen Sie Aktionen oder Remoteaufgaben, Überwachungsereignisse, die Sie überprüfen können, generieren. Sie können die Überwachungsprotokolle für die meisten Arbeitslasten für Intune überprüfen. 

## <a name="who-can-access-the-data"></a>Wer die Daten zugreifen können?
Benutzer mit den folgenden Berechtigungen können Überwachungsprotokolle überprüfen:
- Globaler Administrator
- Intune-Dienstadministrators
- Eine Rolle "Intune" mit zugewiesene Administratoren **Überwachungsdaten** - **lesen** Berechtigungen

## <a name="audit-logs-for-intune-workloads"></a>Überwachungsprotokolle für Intune Arbeitslasten
Sie können die Überwachungsprotokolle in der Gruppe der Überwachung für die einzelnen arbeitsauslastungen Intune überprüfen.  
1. Melden Sie sich beim [Azure-Portal](https://portal.azure.com) an.
2. Wählen Sie **Weitere Dienste** > **Überwachung und Verwaltung** > **Intune** aus.
3. Auf der **Intune** Blatt, wählen Sie die arbeitsauslastung für die Sie die Überwachungsprotokolle überprüfen möchten.
4. In der **Überwachung** Gruppe für die arbeitsauslastung **Überwachungsprotokollen**.

## <a name="review-audit-events"></a>Überprüfen Sie die Überwachungsereignisse
![Überwachungsprotokolle](./media/monitor-audit-logs.png "Überwachungsprotokolle")

Ein Überwachungsprotokoll verfügt über eine Standardansicht für die Liste, die die folgenden Elemente angezeigt werden:    

- Datum und Uhrzeit des Auftretens
- Initiiert von (Akteur)
- Aktivität
- Ziel(en) in Bereiche einteilen
- Category
- Status

Durch Klicken auf ein Element in der Listenansicht, erhalten Sie alle verfügbaren Details an.

![Überwachungsprotokolle](./media/monitor-audit-log-detail.png "Überwachungsprotokolle")

> [!Note]    
> Die **gestartet, indem (Akteur)** Abschnitt in der Audit-Protokolldetails enthält Informationen zum zuständigen für der Aktivitäts und aus, auf dem er ausgeführt wurde. Z. B., wenn Sie die Aktivität in Intune in Azure-Portal durchführen **Anwendung** immer listet **Microsoft Intune-portalerweiterung** und **Anwendungs-ID** immer verwendet die gleiche GUID. 
>    
> Die **Ziel** Abschnitt mehrere Ziele und Eigenschaften, die auf diesem geändert wurden aufzulisten.  


## <a name="filter-audit-events"></a>Filtern von Überwachungsereignissen
Jede arbeitsauslastung hat ein Menüelement, das die Kategorie der Überwachungssammeldienste Ereignisse im Zusammenhang mit diesem Blatt vorab filtert. Eine separater Filter-Option können Sie die in verschiedenen Kategorien und Aktion Ereignisdetails innerhalb dieser Kategorie zu ändern. Sie können suchen, indem UPN (z. B. die Benutzer, die die Aktion wurde). Ein Bereich Datumsfilter kann 24 Stunden, 7 Tage oder 30-Tage-Optionen. Standardmäßig werden die letzten 30 Tagen von Überwachungsereignissen angezeigt.

## <a name="use-graph-api-to-retrieve-audit-events"></a>Verwenden der Graph-API zum Abrufen von Überwachungsereignissen
Weitere Informationen zur Verwendung die Graph-API zum Abrufen von bis zu einem Jahr von Überwachungsereignissen, finden Sie unter [Liste AuditEvents](https://developer.microsoft.com/en-us/graph/docs/api-reference/beta/api/intune_auditing_auditevent_list).