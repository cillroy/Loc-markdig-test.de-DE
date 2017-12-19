---
title: "Hinzufügen branchenspezifischer Windows-Apps zu Intune"
titlesuffix: Azure portal
description: "Erfahren Sie mehr über das Hinzufügen branchenspezifischer Windows-Apps zu Intune."
keywords: 
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 10/3/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f81c5f82-5cfa-4b97-9f73-d6cf77c06896
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 33959b941e39d8694387770e1f3264d74647de69
ms.sourcegitcommit: 4b776d1a87c0707244f4ae0122de882e0eef6fa3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/04/2017
---
# <a name="how-to-add-windows-line-of-business-lob-apps-to-microsoft-intune"></a>Informationen zum Hinzufügen branchenspezifischer Windows-Apps zu Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]


## <a name="step-1---specify-the-software-setup-file"></a>Schritt 1: Angeben der Softwaresetupdatei

1. Melden Sie sich im Azure-Portal an.
2. Wählen Sie **Weitere Dienste** > **Überwachung und Verwaltung** + **Intune** aus.
3. Wählen Sie auf dem Blatt **Intune** die Option **Apps verwalten** aus.
4. Wählen Sie in der Workload **Mobile Apps** die Option **Verwalten** > **Apps** aus.
5. Wählen Sie über der Liste der Apps **Hinzufügen** aus.
6. Wählen Sie auf dem Blatt **App hinzufügen** die Option **Branchen-App** aus.

## <a name="step-2---configure-the-app-package-file"></a>Schritt 2: Konfigurieren der App-Paketdatei

1. Wählen Sie auf dem Blatt **App hinzufügen** die Option **App-Paketdatei** aus.
2. Klicken Sie auf dem Blatt **App-Paketdatei** auf die Schaltfläche „Durchsuchen“, und wählen Sie eine Windows-Installationsdatei mit der Erweiterung **.msi**, **.appx** oder **.appxbundle** aus.
3. Wenn Sie fertig sind, wählen Sie **OK** aus.


## <a name="step-3---configure-app-information"></a>Schritt 3: Konfigurieren von App-Informationen

1. Wählen Sie auf dem Blatt **App hinzufügen** die Option **App-Paketdatei** aus.
2. Konfigurieren Sie folgende Informationen auf dem Blatt **App-Informationen** (einige der Werte auf diesem Blatt werden möglicherweise automatisch ausgefüllt):
    - **Name:** Geben Sie den Namen der App ein, wie er im Unternehmensportal angezeigt wird. Stellen Sie sicher, dass alle App-Namen eindeutig sind. Wenn ein App-Name zweimal vergeben wird, wird den Benutzern im Unternehmensportal nur eine der Apps angezeigt.
    - **Beschreibung:** Geben Sie eine Beschreibung für die App ein. Die Beschreibung wird Benutzern im Unternehmensportal angezeigt.
    - **Herausgeber:** Geben Sie den Namen des Herausgebers der App ein.
    - **Kategorie:** Wählen Sie eine der integrierten oder von Ihnen erstellten App-Kategorien aus. Durch die Kategorisierung von Apps wird es für die Benutzer leichter, die Apps im Unternehmensportal zu finden.
    - **Diese App als ausgewählte App im Unternehmensportal anzeigen:** Zeigen Sie die App auf der Hauptseite des Unternehmensportal hervorgehoben an, wenn Benutzer nach Apps suchen.
    - **Informations-URL:** Geben Sie optional die URL zu einer Website ein, die Informationen über die App enthält. Diese URL wird Benutzern im Unternehmensportal angezeigt.
    - **URL zu den Datenschutzbestimmungen:** Geben Sie optional die URL zu einer Website ein, die Datenschutzinformationen für die App enthält. Diese URL wird Benutzern im Unternehmensportal angezeigt.
    - **Befehlszeilenargumente:** Geben Sie optional Befehlszeilenargumente ein, die für die .msi-Datei gelten sollen, wenn sie ausgeführt wird, wie z.B. **/q**.
    - **Entwickler:** Geben Sie optional den Namen des App-Entwicklers ein.
    - **Besitzer:** Geben Sie optional einen Namen für den Besitzer dieser App ein, z.B. **Personalabteilung**.
    - **Anmerkungen:** Geben Sie Hinweise zu dieser App ein.
    - **Logo:** Laden Sie ein Symbol hoch, das der App zugeordnet wird. Das Symbol wird gemeinsam mit der App angezeigt, wenn Benutzer das Unternehmensportal durchsuchen.
3. Wenn Sie fertig sind, wählen Sie **OK** aus.

## <a name="step-4---finish-up"></a>Schritt 4: Fertig stellen

1. Überprüfen Sie auf dem Blatt **App hinzufügen**, ob Sie die App-Informationen ordnungsgemäß konfiguriert haben.
2. Wählen Sie **Hinzufügen** aus, um die App in Intune hochzuladen.

## <a name="step-5---update-a-line-of-business-app"></a>Schritt 5: Aktualisieren einer branchenspezifischen App

[!INCLUDE[shared-proc-lob-updateapp](./includes/shared-proc-lob-updateapp.md)]

## <a name="next-steps"></a>Nächste Schritte

Die von Ihnen erstellte App wird in der Liste der Apps angezeigt. Sie können sie jetzt den ausgewählten Gruppen zuweisen. Hilfe finden Sie unter [Zuweisen von Apps zu Gruppen](apps-deploy.md).

Erfahren Sie mehr darüber, wie Sie die Eigenschaften und Zuweisungen Ihrer App überwachen können. Weitere Informationen finden Sie unter [Überwachen von App-Informationen und -Zuweisungen](apps-monitor.md).

Erfahren Sie mehr über den Kontext Ihrer App in Intune. Weitere Informationen finden Sie unter [Übersicht über die Lebenszyklen von Geräten und Apps](introduction-device-app-lifecycles.md).