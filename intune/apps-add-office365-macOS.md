---
title: "Installieren Sie Office 365 für MacOS-Geräte mit Intune"
titlesuffix: Azure portal
description: "Erfahren Sie, wie Sie Intune verwenden, installieren Sie Office 365-apps auf Geräten MacOS erleichtern."
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
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2017
---
# <a name="how-to-assign-office-365-to-macos-devices-with-microsoft-intune"></a>Zuweisen von Office 365 zu MacOS-Geräten mit Microsoft Intune

Diese app-Typ ganz einfach für Office 365-apps auf Geräten MacOS zuweisen. Diese neue Art der app können Sie Word, Excel, PowerPoint, Outlook und OneNote installieren. Diese apps werden auch mit dem Microsoft AutoUpdate (MAU), um die apps sicherer und auf dem neuesten Stand zu halten. Die Apps, die als eine App in der Liste der Apps in der Intune-Konsole erscheinen sollen.


## <a name="before-you-start"></a>Vorbereitung

- Geräte, die auf die Bereitstellung dieser apps müssen MacOS 10.10 oder höher ausgeführt werden.
- Intune unterstützt nur Hinzufügen von Office-apps, die mit Office 2016 für Mac-Suite enthalten.
- Wenn alle Office-apps geöffnet werden, wenn Intune das app-Suite installiert wird, können Endbenutzer-Daten aus nicht gespeicherte Dateien verloren gehen.


## <a name="get-started"></a>Erste Schritte
Fügen Sie Office 365 using der **Apps** Blatt.
1.  Melden Sie sich beim Azure-Portal an.
2.  Wählen Sie **Weitere Dienste** > **Überwachung und Verwaltung** > **Intune** aus.
3.  Wählen Sie auf dem Blatt **Intune** die Option **Mobile Apps** aus.
4.  In der **mobilapps** arbeitsauslastung, wählen Sie **Apps** in der **verwalten** Gruppe. Wählen Sie **Hinzufügen** aus.
5.  Auf der **App hinzufügen** Blatt, wählen Sie **Office 365** > **MacOS**.
6.  Wählen Sie **Hinzufügen** aus.

## <a name="configure-the-app-suite"></a>Konfigurieren der App-Sammlung

Geben Sie Informationen zu den app-Suite. Diese Informationen helfen Ihnen, die Sammlung in Intune zu identifizieren, und Endbenutzer können sie in der Unternehmensportal-App finden.

1.  Wählen Sie auf dem Blatt **App hinzufügen** die Option **App Suite Information** (Informationen über die App-Sammlung) aus.
2.  Geben Sie die folgenden Informationen an:
    - **Sammlungsname:** Geben Sie den Namen der App-Sammlung ein, wie er im Unternehmensportal angezeigt wird. Stellen Sie sicher, dass alle Sammlungsnamen eindeutig sind. Wenn ein Sammlungsname zweimal vergeben wird, wird den Benutzern im Unternehmensportal nur eine der Apps angezeigt.
    - **Sammlungsbeschreibung:** Geben Sie eine Beschreibung für die Sammlung ein.
    - **Publisher** -Microsoft angezeigt wird, wie der Verleger.
    - **Kategorie:** Wählen Sie optional eine der integrierten oder von Ihnen erstellten App-Kategorien aus. Dadurch wird es für Benutzer leichter, die App-Sammlung im Unternehmensportal zu finden.
    - **Als ausgewählte app im Unternehmensportal anzeigen** -Dies zeigt die app-Suite herausgehoben auf der Hauptseite des Unternehmensportals, wenn Benutzer nach apps suchen.
    - **Informations-URL:** Geben Sie optional eine URL zu einer Website ein, die Informationen über diese App enthält. Diese URL wird Benutzern im Unternehmensportal angezeigt.
    - **URL zu den Datenschutzbestimmungen:** Geben Sie optional eine URL zu einer Website ein, die Datenschutzinformationen für diese App enthält. Diese URL wird Benutzern im Unternehmensportal angezeigt.
    - **Entwickler** -Microsoft wird als der Entwickler angezeigt.
    - **Besitzer** -Microsoft als Besitzer wird angezeigt.
    - **Anmerkungen:** Geben Sie Hinweise zu dieser App ein.
    - **Symbol hochladen:** Laden Sie ein Symbol hoch, das gemeinsam mit der App angezeigt wird, wenn die Benutzer das Unternehmensportal durchsuchen.
3.  Wählen Sie **OK** aus. Die Suite wird in der Liste der apps als einzelnen Eintrag angezeigt.

## <a name="configure-app-assignments"></a>Konfigurieren von app-Zuweisungen

Konfigurieren Sie in diesem Schritt die Zuweisungen für die app-Suite. Beachten Sie, dass der verfügbare app-Typ in Kürze verfügbar ist.

1.  Wählen Sie die app-Sammlung in der Liste der apps und **Zuweisungen**.
2.  Wählen Sie **wählen Sie Gruppen**.
3.  Weisen Sie die Sammlung an die Gruppen, denen, die Sie auswählen. Weitere Informationen finden Sie unter [Zuweisen von Apps zu Gruppen mit Microsoft Intune](/intune/apps-deploy).
4.  Wählen Sie für jede Gruppe **erfordern installieren**.
        >[!Note]
        > You cannot uninstall Office 365 through Intune.

5. Wählen Sie **speichern** um Ihre Zuweisungen zu übernehmen.

## <a name="next-steps"></a>Nächste Schritte

Zum Hinzufügen von Office 365-apps auf Windows 10-Gerät finden Sie unter [Zuweisen von Office 365 ProPlus 2016 apps für Windows 10-Geräte mit Microsoft Intune](/intune/apps-add-office365).
