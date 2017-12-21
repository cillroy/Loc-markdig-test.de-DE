---
title: "Hinzufügen von Web-Apps in Intune"
titleSuffix: Azure portal
description: "Erfahren Sie mehr über das Hinzufügen von Web-Apps in Intune.\""
keywords: 
author: mattbriggs
ms.author: erikre
manager: angrobe
ms.date: 12/06/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5f08752f-0e87-4ad9-a34c-4991b3150775
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 5ea6b5fc046bd334b2b25e6aac5324f1ceded79a
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2017
---
# <a name="how-to-add-web-apps-to-microsoft-intune"></a>Hinzufügen von Web-Apps in Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Vor dem Zuweisen einer app für Ihre Benutzer und verwalten können, müssen Sie die app zu Intune hinzufügen. Intune unterstützt eine Vielzahl von app-Typen, einschließlich Web-apps.

> [!Note]
> Web-apps werden nicht für Arbeitsaufgaben-Geräte unter Android unterstützt.

Das folgende Verfahren können Sie eine app als eine Verknüpfung zu einer app im Web zu Intune hinzufügen:

1. Melden Sie sich beim Azure-Portal an.
2. Mit **mehr Ressourcen**, suchen und auswählen **Intune**.
3. Auf der **Microsoft Intune** Blatt select **mobilapps**.
4. Auf der **mobilapps** Blatt select **Apps**.
5. Über die Liste der apps, die Option **hinzufügen**. Die **Add app** Blatt wird angezeigt.
6. In der **Add app** Blatt, wählen die **Web-app** -Typ aus der **App-Typ** Dropdown-Liste.
7. Wählen Sie die **konfigurieren** Option zum Anzeigen der **App Informationen** Blatt.
8. In der **App Informationen** Blatt, fügen Sie die folgenden Informationen hinzu:
    - **Name:** Geben Sie den Namen der App ein, wie er im Unternehmensportal angezeigt wird.
    - **Beschreibung:** Geben Sie eine Beschreibung für die App ein. Diese Beschreibung wird den Endbenutzern im Unternehmensportal angezeigt.
    - **Herausgeber:** Geben Sie den Namen des Herausgebers dieser App ein.
    - **App-URL:** Geben Sie die URL der Website an, auf der die zuzuweisende App gehostet wird.
    - **Kategorie (optional):** Wählen Sie eine der integrierten oder von Ihnen erstellten App-Kategorien aus. Dadurch wird es für die Benutzer leichter, die App im Unternehmensportal zu finden.
    - **Diese App als ausgewählte App im Unternehmensportal anzeigen:** Zeigen Sie die App auf der Hauptseite des Unternehmensportal hervorgehoben an, wenn Benutzer nach Apps suchen.
    - **Managed Browser zum Öffnen dieses Links anfordern:** Wenn Sie Benutzern einen Link zu einer Website oder Web-App zuweisen, können sie diesen nur im Intune Managed Browser öffnen. Dieser Browser muss auf ihrem Gerät installiert sein.
    - **Logo** -Hochladen ein Logo, das der app zugeordnet werden soll. Dies ist das Logo, das mit der app angezeigt wird, wenn der Benutzer das Unternehmensportal durchsuchen.
9. Wenn Sie fertig sind, auf die **Informationen hinzufügen** Blatt select **Ok**.
10. Klicken Sie dann aus der **Add app** Blatt wählen **hinzufügen**.

Die von Ihnen erstellte App wird in der Liste der Apps angezeigt, in der Sie sie ausgewählten Gruppen zuweisen können. Hilfe finden Sie unter [Zuweisen von Apps zu Gruppen](apps-deploy.md).