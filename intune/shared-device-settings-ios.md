---
title: "Intune-Konfigurationseinstellungen für freigegebene iOS-Geräte"
titlesuffix: Azure portal
description: "Erfahren Sie mehr über die Intune-Einstellungen zur Anzeige von Informationen auf dem Sperrbildschirm von iOS-Geräten.\""
keywords: 
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 07/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f122e4ee-90e7-4b42-b801-8c1c7c0a5bf7
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 1f9256594493aeebda9ab65e3df269ea7acaca5b
ms.sourcegitcommit: 3b397b1dcb780e2f82a3d8fba693773f1a9fcde1
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/12/2017
---
# <a name="shared-device-configuration-settings-to-display-messages-on-the-ios-device-lock-screen"></a>Konfigurationseinstellungen für freigegebene Geräte zum Anzeigen von Nachrichten auf dem iOS-Geräte-Sperrbildschirm

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Mit Konfigurationseinstellungen für freigegebene Geräte können Sie optionalen Text angeben, der im Anmeldefenster und auf dem Sperrbildschirm angezeigt wird. So können Sie z.B. eine „Wenn verloren, zurück an“-Nachricht und Bestandskennzeicheninformationen eingeben. 

>[!IMPORTANT]
> Diese Funktion wird auf überwachten Geräten mit iOS 9.3 und höher unterstützt.

## <a name="create-shared-device-settings"></a>Erstellen von freigegebenen Geräteeinstellungen

1. Wählen Sie auf dem Blatt **Gerätefunktionen** die Option **Konfiguration freigegebener Geräte (nur überwacht)**.
2. Konfigurieren Sie auf dem Blatt **Konfiguration freigegebener Geräte (nur überwacht)** die folgenden Einstellungen:
    - **Bestandskennzeicheninformationen**: Geben Sie Informationen zum Bestandskennzeichen des Geräts ein. Beispiel: **Im Besitz von Contoso Corp**. Die von Ihnen eingegebenen Informationen werden auf alle Geräte angewendet, denen Sie dieses Profil zuweisen.
    - **Fußnote zum Sperrbildschirm**: Geben Sie einen Hinweis ein, der Ihnen helfen könnte, das Gerät zurückzubekommen, wenn es verloren geht oder gestohlen wird. Beispiel: **Wenn Sie dieses Gerät gefunden haben, rufen Sie bitte „Nummer“ an**.
3. Wenn Sie fertig sind, klicken Sie auf **OK**, bis Sie zum Blatt **Profil erstellen** zurückkehren, und wählen Sie dann **Erstellen** aus. 


## <a name="next-steps"></a>Nächste Schritte

Sie können nun das Geräteprofil den von Ihnen ausgewählten Gruppen zuweisen. Weitere Informationen finden Sie unter [Zuweisen von Geräteprofilen](device-profile-assign.md).
