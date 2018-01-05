---
title: "Hinzufügen von iOS Store-Apps zu Intune | Microsoft-Dokumentation"
titlesuffix: Azure portal
description: "Erfahren Sie mehr über das Hinzufügen von iOS Store-Apps in Intune.\""
keywords: Intune
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 09/18/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c59514d7-1256-4576-9380-e7a0b85a0378
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 0f7b94562f97c7acb4d8f92cd0450a394cb3871d
ms.sourcegitcommit: e37e916e2bf14f092d3a767bc90d68c181d739fb
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/03/2018
---
# <a name="how-to-add-ios-store-apps-to-microsoft-intune"></a>Hinzufügen von iOS Store-Apps in Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]


Fügen Sie mithilfe der Informationen in diesem Abschnitt iOS Store-Apps zu Intune hinzu.

>[!NOTE]
>Während Benutzer von iOS-Geräten einige der integrierten iOS-Apps wie Stocks und Maps entfernen können, können Sie diese Apps über Intune nicht erneut bereitstellen. Wenn Endbenutzer diese Apps löschen, müssen sie zum App Store navigieren und die Apps manuell erneut installieren.

## <a name="before-you-start"></a>Vorbereitung

Sie können mit dieser Methode nur Apps zuweisen, die im App Store kostenlos angeboten werden. Wenn Sie mithilfe von Intune kostenpflichtige Apps zuweisen möchten, erwägen Sie die Nutzung des [iOS Volume Purchase Program](vpp-apps-ios.md).


## <a name="step-1---search-for-the-app-in-the-store"></a>Schritt 1: Suchen der App im Store

1. Melden Sie sich beim Azure-Portal an.
2. Wählen Sie **Weitere Dienste** > **Überwachung und Verwaltung** > **Intune** aus.
3. Wählen Sie auf dem Blatt **Intune** die Option **Apps verwalten** aus.
4. Wählen Sie in der Workload **Mobile Apps** die Option **Verwalten** > „Apps“ aus.
5. Wählen Sie über der Liste der Apps **Hinzufügen** aus.
6. Wählen Sie auf dem Blatt **App hinzufügen** die Option **App Store durchsuchen** aus.
7. Wählen Sie auf dem Blatt **Apple App Store** das Gebietsschema des App Store aus.
8. Geben Sie den Namen (oder einen Teil des Namens) in das Suchfeld ein. Intune durchsucht den Store und gibt eine Liste mit relevanten Ergebnissen zurück.
9. Wählen Sie in der Liste die gewünschte App aus, und klicken Sie dann auf **OK**.

## <a name="step-2---configure-app-information"></a>Schritt 2: Konfigurieren von App-Informationen

1. Wählen Sie auf dem Blatt **App hinzufügen** die Option **App-Informationen** aus.
2. Konfigurieren Sie auf dem Blatt **App bearbeiten** die App-Informationen. Klicken Sie abschließend auf **Hinzufügen**. Abhängig von der ausgewählten App werden einige der Werte auf diesem Blatt möglicherweise automatisch ausgefüllt:
3. **Name**: Geben Sie den Namen der App ein, der im Unternehmensportal angezeigt werden soll. Stellen Sie sicher, dass alle App-Namen eindeutig sind. Wenn ein App-Name zweimal vergeben wird, zeigt das Unternehmensportal den Benutzern nur eine der Apps an.
4. **Beschreibung**: Geben Sie eine Beschreibung für die App ein, die den Benutzern im Unternehmensportal angezeigt werden soll.
5. **Herausgeber**: Geben Sie den Namen des Herausgebers der App ein.
6. **App Store-URL**: Geben Sie die App Store-URL der App ein, die Sie erstellen möchten.
7. **Land/Region des Store**: Wählen Sie das Gebietsschema des App Store aus.
8. **Mindestens erforderliches Betriebssystem**: Wählen Sie aus der Liste die mindestens erforderliche Betriebssystemversion aus, auf der die App installiert werden kann. Die App wird auf einem Gerät mit einem älteren Betriebssystem nicht installiert.
9. **Verwendbarer Gerätetyp**: Wählen Sie die Geräte aus der Liste aus, die von der App verwendet werden.
10. **Kategorie** (optional). Wählen Sie eine der integrierten oder von Ihnen erstellten App-Kategorien aus. Kategorien erleichtern es dem Benutzer, die App im Unternehmensportal zu finden.
11. **Diese App als ausgewählte App im Unternehmensportal anzeigen**: Zeigen Sie die App auf der Hauptseite des Unternehmensportals hervorgehoben an, wenn Benutzer nach Apps suchen.
12. **Informations-URL**: Geben Sie optional eine URL zu einer Website ein, die Informationen über diese App enthält. Die URL wird Benutzern im Unternehmensportal angezeigt.
13. **URL zu den Datenschutzbestimmungen**: Geben Sie optional eine URL zu einer Website ein, die Datenschutzinformationen für diese App enthält. Die URL wird Benutzern im Unternehmensportal angezeigt.
14. **Entwickler**: Geben Sie optional den Namen des App-Entwicklers ein. Dieses Feld ist nur für einen Administrator sichtbar, nicht aber für die Benutzer.
15. **Besitzer**: Geben Sie optional einen Namen für den Besitzer dieser App ein, z.B. **Personalabteilung**.  Dieses Feld ist nur für einen Administrator sichtbar, nicht aber für die Benutzer.
16. **Anmerkungen**: Geben Sie Hinweise zu dieser App ein. Dieses Feld ist nur für einen Administrator sichtbar, nicht aber für die Benutzer.
17. **Logo**: Laden Sie ein Symbol für die App hoch. Das Symbol wird gemeinsam mit der App angezeigt, wenn Benutzer das Unternehmensportal durchsuchen.
18. Wenn Sie fertig sind, klicken Sie auf dem Blatt **App hinzufügen** auf **OK**.

Die von Ihnen erstellte App wird in der Liste der Apps angezeigt, in der Sie sie den ausgewählten Gruppen zuweisen können. Hilfe finden Sie unter [Zuweisen von Apps zu Gruppen](apps-deploy.md).
