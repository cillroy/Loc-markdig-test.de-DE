---
title: "Aktivieren von Google Play Protect-Konformität mit Intune"
titleSuffix: Azure portal
description: "Erfahren Sie, wie Sie eine Konformitätsrichtlinie für Android-Geräte erstellen, um Google Play Protect zu aktivieren."
keywords: 
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 11/20/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: E9810BEB-000A-4DFB-B5C7-A22A92082B22
ms.reviewer: muhosabe
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: d610bc338c1bcf81ed3bc71f1357e001914c5877
ms.sourcegitcommit: 71e6e80b7370024624ce2e5fad1ca5b372975748
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-a-device-compliance-policy-to-enable-google-play-protect"></a>Informationen zum Erstellen einer Gerätekonformitätsrichtlinie zum Aktivieren von Google Play Protect

Sie können eine neue Konformitätsrichtlinie für die Android-Plattform erstellen, um die Konformität mit Google Play Protect (GPP) zu überprüfen.

Die Konformitätsrichtlinie, die diese Einstellungen erfordert, kann dann einer Gruppe von Android-Benutzern oder -Geräten zugeordnet werden. Wenn bei einem Gerät diese Einstellungen nicht aktiviert sind, ist keine Konformität gegeben.

## <a name="create-a-compliance-policy"></a>Erstellen einer Konformitätsrichtlinie

1. Melden Sie sich im Azure-Portal an. Wählen Sie **Weitere Dienste** > **Überwachung und Verwaltung** + **Intune** aus.
2. Wählen Sie **Gerätekonformität** in der Gruppe **Verwalten** aus. 
3. Wählen Sie **Richtlinien** aus, und klicken Sie dann auf **Richtlinie erstellen**.
4. Füllen Sie die Felder **Name** und **Beschreibung** für die Richtlinie aus.
5. Wählen Sie **Android** als Plattform aus.
6. Wählen Sie **Einstellungen** > **Integrität für Geräte**.
7. Konfigurieren Sie die Einstellungen für **Google Play Protect**.
8. Wenn Sie die Einstellungen für Google Play Protect festgelegt haben, geben Sie die Einstellungen **Sicherheit** und **Geräteeigenschaft** an. Wählen Sie abschließend **OK** aus.

## <a name="configure-the-google-play-protect-settings"></a>Konfigurieren der Einstellungen für Google Play Protect

 - **Google Play Services ist konfiguriert**  
   Erfordert, dass die Google Play Services-App installiert und aktiviert ist. Google Play Services ermöglicht Sicherheitsupdates und stellt eine grundlegende Abhängigkeit für viele Sicherheitsfunktionen auf zertifizierten Google-Geräten dar.
 - **Aktueller Sicherheitsanbieter**  
   Dient zum Anfordern, dass ein aktueller Sicherheitsanbieter ein Gerät vor bekannten Sicherheitslücken schützen kann.
 - **Bedrohungsüberprüfung für Apps**  
   Dient zum Anfordern, dass die Android-Funktion **Apps überprüfen** aktiviert wird.
    > [!Note]  
    > Auf der älteren Android-Plattform ist diese Funktion eine Konformitätseinstellung. Intune kann nur prüfen, ob diese Einstellung auf Geräteebene aktiviert ist. Auf Geräten mit Arbeitsprofilen, früher Android for Work, ist diese Einstellung als Konfigurationsrichtlinieneinstellung zu finden. Dies ermöglicht Administratoren, die Einstellung für ein Gerät zu aktivieren.

    Wenn Ihr Unternehmen Android-Arbeitsprofile verwendet, können Sie **Bedrohungsüberprüfung für Apps** für Ihre registrierten Geräte aktivieren. Richten Sie ein Geräteprofil ein, und fordern Sie die Systemsicherheitseinstellung an. Weitere Informationen finden Sie unter [Einstellungen für Geräteeinschränkungen für Android for Work-Geräte in Microsoft Intune](device-restrictions-android-for-work.md).

 - **SafetyNet-Gerätenachweis**  
   Legen Sie die Integritätsstufe des SafetyNet-Gerätenachweises fest, die eingehalten werden muss. Zu den Stufen zählen **Nicht konfiguriert**, **Grundlegende Integrität prüfen** und **Grundlegende Integrität prüfen & zertifizierte Geräte**.




## <a name="next-steps"></a>Nächste Schritte

Weitere Informationen zum Arbeiten mit Gerätekonformitätsrichtlinien finden Sie unter [Erste Schritte mit Intune-Gerätekonformitätsrichtlinien](device-compliance-get-started.md).