---
title: "Hinzufügen von Store-Apps für Android in Intune"
titleSuffix: Azure portal
description: "Erfahren Sie mehr über das Hinzufügen von Android Store-Apps in Intune.\""
keywords: 
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 05/04/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4433000a-23e9-4cad-a818-48c28eedc1f5
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 6c5e409501dc983f26cfe8d74c98b06d4dce76b3
ms.sourcegitcommit: e10dfc9c123401fabaaf5b487d459826c1510eae
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/09/2017
---
# <a name="how-to-add-android-store-apps-to-microsoft-intune"></a>Hinzufügen von Android Store-Apps in Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]


1. Melden Sie sich beim Azure-Portal an.
2. Wählen Sie **Weitere Dienste** > **Überwachung und Verwaltung** > **Intune** aus.
3. Wählen sie auf dem Blatt „Intune“ die Option **Manage Apps** (Verwalten von Apps) aus.
4. Wählen Sie in der Workload **Mobile Apps** die Option **Verwalten** > **Apps** aus.
5. Wählen Sie über der Liste der Apps **Hinzufügen** aus.
6. Wählen Sie auf dem Blatt **App hinzufügen** die Option **App-Informationen** aus.
7. Konfigurieren Sie auf dem Blatt **App bearbeiten** die folgenden Informationen. Klicken Sie abschließend auf **Hinzufügen**. Abhängig von der ausgewählten App werden einige der Werte auf diesem Blatt möglicherweise automatisch ausgefüllt:
    - **App-Name:** Geben Sie den Namen der App ein, wie er im Unternehmensportal angezeigt werden soll. Stellen Sie sicher, dass alle App-Namen eindeutig sind. Wenn ein App-Name zweimal vergeben wird, wird den Benutzern im Unternehmensportal nur eine der Apps angezeigt.
    - **App-Beschreibung:** Geben Sie eine Beschreibung für die App ein. Diese Beschreibung wird den Benutzern im Unternehmensportal angezeigt.
    - **Herausgeber:** Geben Sie den Namen des Herausgebers der App ein.
    - **App Store-URL:** Geben Sie die App Store-URL der App an, die Sie erstellen möchten.
    - **Mindestens erforderliches Betriebssystem:** Wählen Sie in der Liste die mindestens erforderliche Betriebssystemversion aus, auf der die App installiert werden kann. Wenn Sie die App einem Gerät mit einem älteren Betriebssystem zuweisen, wird sie nicht installiert.
    - **Kategorie (optional):** Wählen Sie eine der integrierten oder von Ihnen erstellten App-Kategorien aus. Dadurch wird es für die Benutzer leichter, die App im Unternehmensportal zu finden.
    - **Diese App als ausgewählte App im Unternehmensportal anzeigen:** Zeigen Sie die App auf der Hauptseite des Unternehmensportal hervorgehoben an, wenn Benutzer nach Apps suchen.
    - **Informations-URL:** Geben Sie optional eine URL zu einer Website ein, die Informationen über diese App enthält. Diese URL wird den Benutzern im Unternehmensportal angezeigt.
    - **URL zu den Datenschutzbestimmungen:** Geben Sie optional eine URL zu einer Website ein, die Datenschutzinformationen für diese App enthält. Diese URL wird den Benutzern im Unternehmensportal angezeigt.
    - **Entwickler:** Geben Sie optional den Namen des App-Entwicklers ein.
    - **Besitzer:** Geben Sie optional einen Namen für den Besitzer dieser App ein, z.B. **Personalabteilung**.
    - **Anmerkungen:** Geben Sie Hinweise zu dieser App ein.
    - **Symbol hochladen:** Laden Sie ein Symbol hoch, das der App zugeordnet wird. Dies ist das Symbol, das gemeinsam mit der App angezeigt wird, wenn die Benutzer das Unternehmensportal durchsuchen.
8. Wenn Sie fertig sind, wählen Sie auf dem Blatt **App hinzufügen** die Option **Speichern** aus.

Die von Ihnen erstellte App wird in der Liste der Apps angezeigt, in der Sie sie ausgewählten Gruppen zuweisen können. Hilfe finden Sie unter [Zuweisen von Apps zu Gruppen](apps-deploy.md).