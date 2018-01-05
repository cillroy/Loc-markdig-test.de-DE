---
title: Erste Schritte mit Apps
titlesuffix: Azure portal
description: "Suchen Sie Apps, und fügen Sie sie auf Geräten hinzu, um Ihren Mitarbeitern die Arbeit zu erleichtern."
keywords: 
author: erikre
ms.author: erikre
manager: angrobe
ms.date: 12/06/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a1542fc3-672e-47c1-a21f-82826a2f8ac4
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 89f3585b97bd1a074b45af815792ec4949215aab
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2017
---
# <a name="get-started-with-adding-apps"></a>Erste Schritte mit dem Hinzufügen von Apps

Intune unterstützt einige unterschiedliche Bereitstellungsmethoden für Apps auf Ihren Unternehmensgeräten:

* **Softwareinstallationsprogramme**: Hochladen einer heruntergeladenen Datei auf das Gerät Ihres Benutzers
* __Externe Links__: für eine App in einem öffentlichen App-Store oder eine Web-App
* **Verwaltete Apps**: für iOS-Geräte, für die zusätzliche mobile Anwendungsverwaltung für im App-Store verfügbare Apps erforderlich ist

Eine der schnelleren Bereitstellungsmethoden für Apps ist das Zuweisen einer öffentlichen Store-App.

## <a name="how-do-i-assign-a-public-store-app"></a>Wie weise ich eine öffentliche Store-App zu?

1. Melden Sie sich beim [Azure-Portal](https://portal.azure.com) an.
2. Suchen Sie über **Ressourcen durchsuchen** nach **Intune**.
3. Klicken Sie auf **Mobile Apps** und dann auf **Apps**.
4. Klicken Sie auf **Hinzufügen**, und wählen Sie unter **Store-App** dann **iOS** als **App-Typ** aus.
5. Wählen Sie **App auswählen**, um das Blatt **App Store durchsuchen** anzuzeigen.
6. Suchen Sie über das Textfeld nach einer App, die Sie dem Gerät zuweisen können. Wählen Sie die App aus, und klicken Sie dann auf **Auswählen**.
7. Klicken Sie auf dem Blatt **App hinzufügen** auf **App-Information**, und stellen Sie dann sicher, dass alle App-Informationen ausgefüllt wurden. Sie können andere optionale Details hinzufügen, um diese App zu organisieren, wie z.B. **Besitzer**, **Anmerkungen**, **Entwickler** und **URL zu den Datenschutzbestimmungen** für die Datenschutzrichtlinie Ihres Unternehmens.
8. Achten Sie darauf, dass Sie **Ja** für **Diese App als ausgewählte App im Unternehmensportal anzeigen** ausgewählt haben, und klicken Sie dann auf **OK**.
9. Wählen Sie **Hinzufügen** auf dem Blatt **App hinzufügen** aus, um die App hinzuzufügen. Dann werden Sie zur **Übersicht** der App weitergeleitet. Klicken Sie auf **Zuweisungen** und dann auf **Gruppe auswählen**, um sie Ihrer Testgruppe hinzuzufügen. Machen Sie die App zum Herunterladen **verfügbar**. Dann sollte die App als **Empfohlene App** auf Ihrem Testgerät angezeigt werden.

## <a name="learn-more"></a>Erfahren Sie mehr

* [Was ist die Microsoft Intune App-Verwaltung?](app-management.md)
* [Übersicht über den App-Lebenszyklus](app-lifecycle.md)
* [Was sind App-Schutzrichtlinien?](app-protection-policy.md)
