---
title: "Hinzufügen von Apps zu Microsoft Intune"
titlesuffix: Azure portal
description: "Mit diesen Vorgehensweisen können Sie Ihre Apps in Intune für die Zuweisung zu Benutzern und Geräten vorbereiten. \""
keywords: 
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 07/17/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a1ded457-0ecf-4f9c-a2d2-857d57f8d30a
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 108f789f16304498cf54387326d112353bf70aa2
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2017
---
# <a name="how-to-add-an-app-to-microsoft-intune"></a>So fügen Sie eine App zu Microsoft Intune hinzu

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Bevor Sie Apps verwalten und Benutzern zuweisen können, müssen Sie diese in Intune hinzufügen. Intune unterstützt eine ganze Palette unterschiedlicher App-Typen, die Optionen können sich je nach Typ unterscheiden.

Über Intune können Sie folgende App-Typen hinzufügen und zuweisen:

![Von Intune unterstützte App-Typen](./media/app-types.png)

Die folgenden Plattformen werden unterstützt.

- Android Store-Apps
- Branchenspezifische Android-Apps
- iOS Store-Apps
- Branchenspezifische iOS-Apps
- Web-Apps
- Windows Phone 8.1 Store-Apps
- Branchenspezifische Windows Phone-Apps (XAP-Dateien)
- Windows Store-Apps
- Branchenspezifische Windows-Apps (nur MSI-Dateien)

>[!TIP]
> Eine branchenspezifische App ist eine App, die Sie nicht über einen App Store, sondern über die App-Installationsdatei installieren. Um beispielsweise eine branchenspezifische iOS-App zu installieren, fügen Sie die Anwendungsarchivdatei (mit der Erweiterung „.ipa“) hinzu. In der Regel handelt es sich um Apps, die intern geschrieben wurden.

## <a name="before-you-start"></a>Vorbereitung

Beachten Sie die folgenden Punkte, bevor Sie damit beginnen, Apps hinzuzufügen und zuzuweisen.

- Wenn Sie eine App aus einem Store hinzufügen und zuweisen, müssen Endbenutzer über ein Konto bei diesem Store verfügen, um die App installieren zu können.
- Einige von Ihnen zugewiesenen Apps oder Elemente sind möglicherweise von integrierten iOS-Apps abhängig. Wenn Sie z. B. ein Buch aus dem iOS-Store zuweisen, muss die iBooks-App auf dem Gerät vorhanden sein. Wenn Sie die integrierte iBooks-App entfernt haben, können Sie Intune nicht dazu verwenden, sie wieder zu aktivieren.

## <a name="cloud-storage-space"></a>Cloudspeicherplatz
Alle Apps, die Sie mithilfe des Software-Installationsprogrammtyps erstellen (beispielsweise eine branchenspezifische App), werden paketiert und in den Intune-Cloudspeicher hochgeladen. Ein Testabonnement von Intune enthält 2 GB cloudbasierten Speicher, der zum Speichern von verwalteten Apps und Updates verwendet wird. Ein vollständiges Abonnement enthält 20 GB Speicherplatz.

Sie können zusätzlichen Speicher für Intune mit Ihrer ursprünglichen Zahlungsweise erwerben.  Wenn Sie per Rechnung oder Kreditkarte gezahlt haben, besuchen Sie das [Portal zur Abonnementverwaltung](https://portal.office.com/adminportal/home?switchtomodern=true#/subscriptions).  Wenden Sie sich alternativ an Ihren Partner oder Vertriebsmitarbeiter.

Anforderungen für Cloudspeicherplatz:

-   Alle App-Installationsdateien müssen sich im selben Ordner befinden.
-   Die maximale Dateigröße für hochgeladene Dateien beträgt 2 GB.

## <a name="how-to-create-and-edit-categories-for-apps"></a>Erstellen und Bearbeiten von Kategorien für Apps

Mithilfe von App-Kategorien können Sie Apps sortieren, damit Benutzer sie einfacher im Unternehmensportal finden können. Sie können einer App auch mehrere Kategorien zuweisen, z.B. **Entwickler-Apps** oder **Kommunikations-Apps**.
Wenn Sie eine App in Intune hinzufügen, können Sie die gewünschte Kategorie auswählen. Verwenden Sie die plattformspezifischen Themen, um eine App hinzuzufügen und Kategorien zuzuweisen. Gehen Sie zum Erstellen und Bearbeiten Ihre eigenen Kategorien folgendermaßen vor:

1. Melden Sie sich beim Azure-Portal an.
2. Wählen Sie **Weitere Dienste** > **Überwachung und Verwaltung** > **Intune** aus.
3. Wählen Sie auf dem Blatt **Intune** die Option **Mobile Apps** aus.
4. Wählen Sie in der Workload **Mobile Apps** die Option **Setup** > **App-Kategorien** aus.
5. Auf dem Blatt **App-Kategorien** wird eine Liste der aktuellen Kategorien angezeigt. Wählen Sie eine der folgenden Aktionen aus:
    - **Erstellen einer Kategorie:** Geben Sie auf dem Blatt **Kategorie erstellen** einen Namen für die neue Kategorie ein. Namen können in nur einer Sprache eingegeben werden, und werden von Intune nicht übersetzt. Klicken Sie auf **Erstellen**, wenn Sie fertig sind.
    - **Bearbeiten einer Kategorie:** Wählen Sie für jede Kategorie in der Liste „**...**“ aus. Auf dem Blatt **Eigenschaften** können Sie einen neuen Namen für die Kategorie eingeben oder die Kategorie löschen.


## <a name="apps-added-automatically-by-intune"></a>Von Intune automatisch hinzugefügte Apps

Zuvor enthielt Intune eine Reihe integrierter Apps, die Sie rasch zuweisen konnten. Auf Grundlage Ihrer Feedbacks haben wir diese Liste entfernt, und es werden keine integrierten Apps mehr angezeigt.
Wenn Sie jedoch schon integrierte Apps zugewiesen haben, werden sie noch immer auf der App-Liste angezeigt. Sie können diese Apps weiter nach Bedarf zuweisen.
Es ist geplant, in einer späteren Version eine einfachere Methode hinzuzufügen, um integrierte Apps über das Azure-Portal auszuwählen und zuzuweisen.

## <a name="next-steps"></a>Nächste Schritte

Wählen Sie eines der folgenden Themen, um zu erfahren, wie Sie Apps für jede Plattform in Intune hinzufügen:

- [Android Store-Apps](store-apps-android.md)
- [Android-Branchen-Apps](lob-apps-android.md)
- [iOS Store-Apps](store-apps-ios.md)
- [iOS-Branchen-Apps](lob-apps-ios.md)
- [Web-Apps (für alle Plattformen)](web-app.md)
- [Windows Phone 8.1 Store-Apps](store-apps-windows-phone-8-1.md)
- [Branchenspezifische Windows Phone-Apps](lob-apps-windows-phone.md)
- [Windows Store-Apps](store-apps-windows.md)
- [Branchenspezifische Windows-Apps](lob-apps-windows.md)
- [Office 365 apps for Windows 10 (Office 365-Apps für Windows 10)](apps-add-office365.md)

