---
title: "Installieren von Office 365 für macOS-Geräte mit Intune"
titlesuffix: Azure portal
description: "Erfahren Sie, wie Sie Intune verwenden können, um Office 365-Apps einfacher auf macOS-Geräten installieren zu können."
keywords: 
author: erikre
ms.author: erikre
manager: angrobe
ms.date: 12/13/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 2372332a-7e3a-4a9c-91a9-86654e0fabe2
ms.reviewer: aiwang
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 5e0ad0b99a2c8a602b5e542530a1d437065461b2
ms.sourcegitcommit: 22ab1c6a6bfeb4fef9850d12b29829c3fecbbeed
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2018
---
# <a name="how-to-assign-office-365-to-macos-devices-with-microsoft-intune"></a>Zuweisen von Office 365 zu macOS-Geräten mit Microsoft Intune

Dieser App-Typ macht es Ihnen einfach, Office 365-Apps macOS-Geräten zuzuweisen. Dieser neue App-Typ ermöglicht Ihnen die Installation von Word, Excel, PowerPoint, Outlook und OneNote. Diese Apps sind auch im Lieferumfang von Microsoft AutoUpdate (MAU) enthalten, um die Apps sicherer und auf dem neuesten Stand zu halten. Die Apps, die als eine App in der Liste der Apps in der Intune-Konsole erscheinen sollen.


## <a name="before-you-start"></a>Vorbereitung

- Auf Geräten, für die Sie diese Apps bereitstellen, muss macOS 10.10 oder höher ausgeführt werden.
- Intune unterstützt nur das Hinzufügen von Office-Apps, die in der Office 2016 für Mac-Suite enthalten sind.
- Wenn bei der Installation der App-Suite durch Intune Office-Apps geöffnet sind, verlieren Endbenutzer möglicherweise Daten aus nicht gespeicherten Dateien.


## <a name="get-started"></a>Erste Schritte
Fügen Sie Office 365 auf dem Blatt **Apps** hinzu.
1.  Melden Sie sich beim Azure-Portal an.
2.  Wählen Sie **Weitere Dienste** > **Überwachung und Verwaltung** > **Intune** aus.
3.  Wählen Sie auf dem Blatt **Intune** die Option **Mobile Apps** aus.
4.  Klicken Sie in der Workload **Mobile Apps** auf **Apps** in der Gruppe **Verwalten**. Wählen Sie **Hinzufügen** aus.
5.  Wählen Sie auf dem Blatt **App hinzufügen** die Optionen **Office 365** > **macOS** aus.
6.  Wählen Sie **Hinzufügen** aus.

## <a name="configure-the-app-suite"></a>Konfigurieren der App-Sammlung

Stellen Sie Informationen über die App-Suite bereit. Diese Informationen helfen Ihnen, die Sammlung in Intune zu identifizieren, und Endbenutzer können sie in der Unternehmensportal-App finden.

1.  Wählen Sie auf dem Blatt **App hinzufügen** die Option **App Suite Information** (Informationen über die App-Sammlung) aus.
2.  Geben Sie die folgenden Informationen an:
    - **Sammlungsname:** Geben Sie den Namen der App-Sammlung ein, wie er im Unternehmensportal angezeigt wird. Stellen Sie sicher, dass alle Sammlungsnamen eindeutig sind. Wenn ein Sammlungsname zweimal vergeben wird, wird den Benutzern im Unternehmensportal nur eine der Apps angezeigt.
    - **Sammlungsbeschreibung:** Geben Sie eine Beschreibung für die Sammlung ein.
    - **Herausgeber**: Als Herausgeber wird Microsoft angezeigt.
    - **Kategorie:** Wählen Sie optional eine der integrierten oder von Ihnen erstellten App-Kategorien aus. Dadurch wird es für Benutzer leichter, die App-Sammlung im Unternehmensportal zu finden.
    - **Diese App als ausgewählte App im Unternehmensportal anzeigen**: Hierdurch wird die App-Suite auf der Hauptseite des Unternehmensportals hervorgehoben angezeigt, wenn Benutzer nach Apps suchen.
    - **Informations-URL:** Geben Sie optional eine URL zu einer Website ein, die Informationen über diese App enthält. Diese URL wird Benutzern im Unternehmensportal angezeigt.
    - **URL zu den Datenschutzbestimmungen:** Geben Sie optional eine URL zu einer Website ein, die Datenschutzinformationen für diese App enthält. Diese URL wird Benutzern im Unternehmensportal angezeigt.
    - **Entwickler**: Als Entwickler wird Microsoft angezeigt.
    - **Besitzer**: Als Besitzer wird Microsoft angezeigt.
    - **Anmerkungen:** Geben Sie Hinweise zu dieser App ein.
    - **Symbol hochladen:** Laden Sie ein Symbol hoch, das gemeinsam mit der App angezeigt wird, wenn die Benutzer das Unternehmensportal durchsuchen.
3.  Wählen Sie **OK** aus. Die Suite wird in der Liste der Apps als einzelnen Eintrag angezeigt.

## <a name="configure-app-assignments"></a>Konfigurieren von App-Zuweisungen

In diesem Schritt konfigurieren Sie Zuweisungen für die App-Suite. Beachten Sie, dass der verfügbare App-Typ in Kürze verfügbar ist.

1.  Wählen Sie die App-Suite in der Liste der Apps und dann **Zuweisungen** aus.
2.  Klicken Sie auf **Gruppen auswählen**.
3.  Ordnen Sie die Suite den von Ihnen ausgewählten Gruppen zu. Weitere Informationen finden Sie unter [Zuweisen von Apps zu Gruppen mit Microsoft Intune](/intune/apps-deploy).
4.  Wählen Sie für jede Gruppe **erfordern installieren**.
        >[!Note]
        > You cannot uninstall Office 365 through Intune.

5. Wählen Sie **Speichern**, um Ihre Zuweisungen zu committen.

## <a name="next-steps"></a>Nächste Schritte

Weitere Informationen zum Hinzufügen von Office 365-Apps zu Windows 10-Geräten finden Sie unter [Wie Sie Office 365 ProPlus 2016-Apps mit Microsoft Intune](/intune/apps-add-office365) Windows 10-Geräten zuweisen.
