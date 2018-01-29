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
ms.openlocfilehash: ebe4b31c85e0c0bc88f49d28e28ea7eac191951f
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2018
---
# <a name="how-to-add-web-apps-to-microsoft-intune"></a>Hinzufügen von Web-Apps in Microsoft Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Vor dem Zuweisen einer app für Ihre Benutzer und verwalten können, müssen Sie die app zu Intune hinzufügen. Intune unterstützt eine Vielzahl von App-Typen, einschließlich Web-Apps.

> [!Note]
> Web-Apps werden nicht für Android for Work-Geräte unterstützt.

Das folgende Verfahren können Sie eine app als eine Verknüpfung zu einer app im Web zu Intune hinzufügen:

1. Melden Sie sich beim Azure-Portal an.
2. Suchen Sie über **Mehr Ressourcen** nach **Intune**, und wählen Sie die App aus.
3. Wählen Sie auf dem Blatt **Microsoft Intune** die Option **Mobile Apps** aus.
4. Wählen Sie auf dem Blatt **Mobile Apps** die Option **Apps** aus.
5. Wählen Sie oberhalb der App-Liste **Hinzufügen** aus. Die **Add app** Blatt wird angezeigt.
6. Wählen Sie auf dem Blatt **App hinzufügen** den Typ **Web-App** aus der Dropdownliste **App-Typ** aus.
7. Wählen Sie auf dem Blatt **App-Informationen** die Option **Konfigurieren** aus.
8. Fügen Sie auf dem Blatt **App-Informationen** die folgenden Informationen hinzu:
    - **Name:** Geben Sie den Namen der App ein, wie er im Unternehmensportal angezeigt wird.
    - **Beschreibung:** Geben Sie eine Beschreibung für die App ein. Diese Beschreibung wird den Endbenutzern im Unternehmensportal angezeigt.
    - **Herausgeber:** Geben Sie den Namen des Herausgebers dieser App ein.
    - **App-URL:** Geben Sie die URL der Website an, auf der die zuzuweisende App gehostet wird.
    - **Kategorie (optional):** Wählen Sie eine der integrierten oder von Ihnen erstellten App-Kategorien aus. Dadurch wird es für die Benutzer leichter, die App im Unternehmensportal zu finden.
    - **Diese App als ausgewählte App im Unternehmensportal anzeigen:** Zeigen Sie die App auf der Hauptseite des Unternehmensportal hervorgehoben an, wenn Benutzer nach Apps suchen.
    - **Managed Browser zum Öffnen dieses Links anfordern:** Wenn Sie Benutzern einen Link zu einer Website oder Web-App zuweisen, können sie diesen nur im Intune Managed Browser öffnen. Dieser Browser muss auf ihrem Gerät installiert sein.
    - **Logo** -Hochladen ein Logo, das der app zugeordnet werden soll. Dies ist das Logo, das mit der app angezeigt wird, wenn der Benutzer das Unternehmensportal durchsuchen.
9. Wählen Sie dann auf dem Blatt **Informationen hinzufügen** die Option **OK** aus.
10. Wählen Sie anschließend **Hinzufügen** auf dem Blatt **App hinzufügen** aus.

Die von Ihnen erstellte App wird in der Liste der Apps angezeigt, in der Sie sie ausgewählten Gruppen zuweisen können. Hilfe finden Sie unter [Zuweisen von Apps zu Gruppen](apps-deploy.md).