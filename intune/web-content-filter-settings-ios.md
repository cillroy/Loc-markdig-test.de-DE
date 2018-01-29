---
title: "Intune-Filtereinstellungen für Webinhalte für iOS-Geräte"
titlesuffix: Azure portal
description: "Lernen Sie die Einstellungen kennen, die Sie verwenden können, um den Zugriff von iOS-Geräten auf Websites zuzulassen und zu blockieren.\""
keywords: 
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 7/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 16aa0f3c-8977-4495-9fbe-ca30ad278c9e
ms.reviewer: karanda
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: fbf2fa33925e049aa1a184a09f2764df558529cd
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2018
---
# <a name="web-content-filter-settings-for-ios-devices"></a>Filtereinstellungen für Webinhalte für iOS-Geräte

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Konfigurieren Sie mit diesen Einstellungen URLs, auf die Endbenutzer in Webbrowsern auf iOS-Geräten zugreifen oder nicht zugreifen dürfen. Ihnen stehen zwei Verfahren zur Konfigurierung von URLs zur Verfügung:

- **Konfigurieren von URLs**: Verwenden Sie den integrierten Webfilter von Apple, der nach nicht jugendfreien Inhalten wie Anzüglichkeiten oder Obszönitäten sucht. Diese Funktion bewertet jede Webseite, sobald diese geladen ist, und versucht, ungeeignete Inhalte zu identifizieren und zu blockieren. Darüber hinaus können Sie URLs konfigurieren, die vom Filter nicht geprüft werden. Sie können auch URLs konfigurieren, die unabhängig von den Filtereinstellungen blockiert werden.

- **Nur bestimmte Websites** (nur für den Safari-Webbrowser): Diese URLs werden zu den Lesezeichen des Safari-Browsers hinzugefügt. Benutzer dürfen **nur** diese Websites besuchen, der Zugriff auf andere Websites ist nicht möglich. Verwenden Sie diese Option nur, wenn Sie genau wissen, auf welche URLs Benutzer zugreifen können.
Wenn Sie hier keine URLs angeben, können Endbenutzer keine Websites außer „microsoft.com“, „microsoft.net“ und „apple.com“ öffnen.



## <a name="get-started"></a>Erste Schritte

1. Wählen Sie auf dem Blatt „Gerätefunktionen“ die Option **Webinhaltsfilter (nur überwacht)**.
2. Wählen Sie auf dem Blatt **Webinhaltsfilter** den **Filtertyp**, den Sie konfigurieren möchten:
    - **Nicht konfiguriert**: Es wird keine Filterung ausgeführt.
    - **Konfigurieren von URLs**
    - **Nur bestimmte Websites**
3. Führen Sie danach je nach verwendetem Filtertyp eines der unten genannten Verfahren aus.


## <a name="configure-urls"></a>Konfigurieren von URLs

1. Wählen Sie auf dem Blatt **Webinhaltsfilter** bei Bedarf eine der folgenden Einstellungen aus:
    - **Zulässige URLs**: Geben Sie auf dem Blatt **Zulässige URLs** die URLs ein, die Sie zulassen möchten (der Apple-Webfilter wird dadurch umgangen), und drücken Sie nach jeder URL die EINGABETASTE.
    - **Blockierte URLs**: Geben Sie auf dem Blatt **Blockierte URLs** die URLs ein, die Sie blockieren möchten (unabhängig von den Apple-Webfiltereinstellungen), und drücken Sie nach jeder URL die EINGABETASTE.
2. Klicken Sie zum Abschluss auf **OK**.


## <a name="specific-websites-only"></a>Nur bestimmte Websites

1. Konfigurieren Sie auf dem Blatt **Webinhaltsfilter** für jede Website, die Sie zulassen möchten, die folgenden Einstellungen:
    - **URL**: Geben Sie die URL der Website ein, die Sie zulassen möchten, z.B. **http://www.contoso.com**.
    - **Pfad als Lesezeichen speichern**: Geben Sie den Pfad ein, in dem Sie Lesezeichen speichern möchten, z.B. **/Contoso/Business Apps**. Wenn Sie keinen Pfad angeben, wird das Lesezeichen zum Standardordner für Lesezeichen auf dem Gerät hinzugefügt.
    - **Titel**: Geben Sie einen beschreibenden Titel für das Lesezeichen ein.
2. Klicken Sie auf **Hinzufügen**, wenn Sie die Informationen für die jeweilige Website eingegeben haben.
3. Klicken Sie zum Abschluss auf **OK**.

> [!IMPORTANT]
> Die folgenden URLs werden von Intune automatisch zugelassen.
> - www.microsoft.com
> - www.microsoft.net
> - www.apple.com

## <a name="finish-up"></a>Fertig stellen

Klicken Sie auf **OK**, um zum Blatt **Profil erstellen** zurückzukehren, und wählen Sie dann **Erstellen** aus.

## <a name="next-steps"></a>Nächste Schritte

Sie können nun das Geräteprofil den von Ihnen ausgewählten Gruppen zuweisen. Weitere Informationen finden Sie unter [Zuweisen von Geräteprofilen](device-profile-assign.md).
