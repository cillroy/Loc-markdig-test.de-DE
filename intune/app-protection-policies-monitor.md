---
title: "Überwachen von App-Schutzrichtlinien"
titleSuffix: Azure portal
description: "Finden Sie heraus, für wie viele Benutzer die Richtlinie gilt, und zeigen Sie weitere Details an.\""
keywords: 
author: erikre
ms.author: erikre
manager: angrobe
ms.date: 01/23/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 9b0afb7d-cd4e-4fc6-83e2-3fc0da461d02
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 64c560474173c9b963252f845164d1202d957079
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2017
---
# <a name="how-to-monitor-app-protection-policies"></a>Überwachen von App-Schutzrichtlinien
[!INCLUDE[azure_portal](./includes/azure_portal.md)]

**Falls Sie nicht das Azure-Portal verwenden**, wird in diesem Thema erläutert, wie Sie im klassischen Intune-Portal [App-Schutzrichtlinien erstellen](https://docs.microsoft.com/intune-classic/deploy-use/create-and-deploy-mobile-app-management-policies-with-microsoft-intune).


Sie können den Konformitätsstatus der Verwaltungsrichtlinien für mobile Apps (MAM) überwachen, die Sie auf Benutzer auf dem Blatt „Intune-Schutz für Apps“ im [Azure-Portal](https://portal.azure.com) angewendet haben. Sie können Informationen über die Benutzer finden, die von der MAM-Richtlinie betroffen sind, deren Konformitätsstatus sowie Probleme, die bei den Benutzern möglicherweise auftreten.

Es gibt drei verschiedenen Stellen, an denen der Konformitätsstatus überwacht werden kann:

-   Zusammenfassungsansicht

-   Detailansicht

-   Berichterstellung

## <a name="summary-view"></a>Zusammenfassungsansicht

1. Melden Sie sich beim Azure-Portal an.
2. Wählen Sie **Weitere Dienste** > **Überwachung und Verwaltung** > **Intune** aus.
3. Wählen Sie auf dem Blatt **Intune** die Option **Mobile Apps** aus.
4. Wählen Sie in der Workload **Mobile Apps** die Option **Überwachen** > **Benutzerstatus bei App-Schutz** aus, um die Zusammenfassungsansicht anzuzeigen:

![Kachel „Zusammenfassung“ auf dem Blatt „Mobile Anwendungsverwaltung mit Intune“](./media/app-protection-user-status-summary.png)

-   **Benutzer:** Die Gesamtzahl von Benutzern in Ihrem Unternehmen, die die eine App verwenden, die einer Richtlinie in einem geschäftlichen Kontext zugeordnet ist.

-   **VERWALTET DURCH RICHTLINIE**: Die Anzahl von Benutzern, die eine App verwendet haben und denen eine Richtlinie in einem geschäftlichen Kontext zugeordnet ist.

-   **KEINE RICHTLINIE**: Die Anzahl von Benutzern, die eine App verwenden, die unter keine Richtlinie in einem geschäftlichen Kontext fallen. Sie sollten erwägen, diese Benutzer zur Richtlinie hinzuzufügen.
    > [!NOTE]
    > Wenn Sie über mehrere Richtlinien pro Plattform verfügen, gilt ein Benutzer als durch eine Richtlinie verwaltet, wenn ihm mindestens eine Richtlinie zugewiesen ist.

- **Gekennzeichnete Benutzer:** Die Anzahl von Benutzern, die Probleme feststellen. Derzeit werden nur Benutzer mit per Jailbreak manipulierten Geräten unter **Gekennzeichnete Benutzer** gemeldet.


## <a name="detailed-view"></a>Detailansicht
Sie können zur detaillierten Ansicht der Zusammenfassung gelangen, indem Sie auf die Kachel **Benutzerstatus** (basierend auf der Betriebssystemplattform des Geräts) und dann auf die Kachel **Gekennzeichnete Benutzer** klicken.

### <a name="user-status"></a>Benutzerstatus
Sie können nach einem einzelnen Benutzer suchen und den Kompatibilitätsstatus für diesen Benutzer überprüfen. Auf dem Blatt **App-Berichterstellung** werden für einen ausgewählten Benutzer die folgenden Informationen angezeigt:
- Geräte, die dem Benutzerkonto zugeordnet sind

- Apps mit MAM-Richtlinie auf dem Gerät

- Status:

  - **Eingecheckt:** Die Richtlinie wurde für den Benutzer bereitgestellt, und die App wurde mindestens einmal im Arbeitskontext verwendet.

  - **Nicht eingecheckt:** Die Richtlinie wurde für den Benutzer bereitgestellt, die App seitdem aber nicht im Arbeitskontext verwendet.

>[!NOTE]
> Wenn für den gesuchten Benutzer keine MAM-Richtlinie bereitgestellt wurde, wird Ihnen eine Meldung angezeigt, dass auf den Benutzer keine MAM-Richtlinien angewendet werden.

Um die Berichterstattung für einen Benutzer anzuzeigen, gehen Sie folgendermaßen vor:

1.  Wählen Sie die Kachel **Zusammenfassung** aus, um einen Benutzer auszuwählen.

    ![Screenshot 3](./media/MAM-reporting-6.png)

2. Wählen Sie auf dem Blatt **App-Berichterstellung**, das geöffnet wird, **Benutzer auswählen**, um nach einem Azure Active Directory-Benutzer zu suchen.

    ![Option „Benutzer auswählen“ auf dem Blatt „App-Berichterstellung“](./media/MAM-reporting-2.png)

3. Wählen Sie den Benutzer in der Liste aus. Es werden Details zum Kompatibilitätsstatus für diesen Benutzer angezeigt.

### <a name="flagged-users"></a>Gekennzeichnete Benutzer
In der Detailansicht werden die Fehlermeldung, die App, auf die bei Auftreten des Fehlers zugegriffen wurde, die betroffene Betriebssystemplattform des Geräts und ein Zeitstempel angezeigt.

## <a name="reporting-view"></a>Berichterstellung

Sie können die gleichen Berichte in der Detailansicht finden sowie zusätzliche Berichte, die Ihnen mit dem Konformitätsstatus der MAM-Richtlinie weiterhelfen:

![Screenshot 4](./media/MAM-reporting-7.png)

-   **App protection user report** (Benutzerbericht App-Schutz): Darin werden dieselben Informationen dargestellt, die Sie auch im **Benutzerstatus**-Bericht im Abschnitt „Detailansicht“ weiter hoben sehen können.

-   **App protection app report** (App-Bericht App-Schutz): Es werden zwei verschiedene Status zum App-Schutz bereitgestellt, die Administratoren auswählen können, bevor sie den Bericht generieren. Der Status kann geschützt oder nicht geschützt sein.

    -   Benutzerstatus für verwaltete MAM-Aktivität (Geschützt): Dieser Bericht zeigt die Aktivität von jeder verwalteten MAM-App auf Benutzerebene.

        -   Er zeigt alle Apps, die unter MAM-Richtlinien für jeden Benutzer fallen, und schlüsselt den Status jeder App, die unter MAM-Richtlinien eingecheckt sind oder die unter eine MAM-Richtlinie fallen, doch nie eingecheckt waren.
<br></br>
    -   Benutzerstatus für nicht verwaltete MAM-Aktivität (nicht geschützt): Dieser Bericht beschreibt die Aktivitäten auf Benutzerbasis von mit MAM aktivierten Apps, die derzeit nicht verwaltet sind. Dies kann entsprechend der folgenden Gründe auftreten:

        -   Diese Apps werden entweder von einem Benutzer oder von einer App verwendet, die derzeit nicht unter eine MAM-Richtlinie fällt.

        -   Alle Apps sind eingecheckt, erhalten jedoch keine MAM-Richtlinien.

![Screenshot 2](./media/MAM-reporting-4.png)

## <a name="table-grouping"></a>Tabellengruppierung

Sobald die Daten im **Benutzerbericht zum App-Schutz** angezeigt werden, können Sie Daten folgendermaßen aggregieren:

- **Überprüfungsergebnis:** Die Daten werden nach dem App-Schutzstatus – Fehler, Warnung oder Erfolg – gruppiert.
- **App-Name:** Die Daten werden nach Apps (tatsächlicher App-Name) mit Fehlern, Warnungen oder Erfolgen gruppiert.

## <a name="export-app-protection-activities-to-csv"></a>Exportieren von App-Schutzaktivitäten in eine CSV-Datei

Sie können alle Aktivitäten im Zusammenhang mit Ihren App-Schutzrichtlinien in eine CSV-Datei exportieren. Dies kann hilfreich sein, um alle App-Schutzstatus zu analysieren, die von den Benutzern gemeldeten wurden.

Gehen Sie zum Generieren des App-Schutzberichts wie folgt vor:

1. Wählen Sie auf dem Blatt „Mobile Anwendungsverwaltung mit Intune“ den App-Schutzbericht aus.

    ![Screenshot 6](./media/app-protection-report-csv-2.png)

2. Wählen Sie „Ja“ aus, um den Bericht zu speichern, und wählen Sie dann „Speichern unter“ und den Ordner aus, in dem der Bericht gespeichert werden soll.

    ![Screenshot 7](./media/app-protection-report-csv-1.png)

## <a name="see-also"></a>Weitere Informationen:
[Verwalten der Datenübertragung zwischen iOS-Apps](data-transfer-between-apps-manage-ios.md)

* [Was Sie erwartet, wenn Ihre Android-App von App-Schutzrichtlinien verwaltet wird](app-protection-enabled-apps-android.md)
* [Was Sie erwartet, wenn Ihre iOS-App von App-Schutzrichtlinien verwaltet wird](app-protection-enabled-apps-ios.md)
