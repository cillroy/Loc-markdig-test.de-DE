---
title: "Einstellungen für Geräteeinschränkungen für Android for Work in Intune"
titlesuffix: Azure portal
description: "In diesem Artikel lernen Sie die Intune-Einstellungen zur Steuerung von Geräteeinstellungen und -funktionen auf Android for Work-Geräten kennen."
keywords: 
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 08/01/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 1830720b-16cb-4f2f-a71a-62967f882563
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: beb8368aa2db33df84bb64985177b47beebc80ac
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2017
---
# <a name="android-for-work-device-restriction-settings-in-microsoft-intune"></a>Einstellungen für Geräteeinschränkungen für Android for Work-Geräte in Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

## <a name="work-profile-settings"></a>Arbeitsprofileinstellungen
-   **Kopieren und Einfügen zwischen Arbeitsprofilen und persönlichen Profilen**: Steuert das Kopieren und Einfügen zwischen Arbeits-Apps und persönlichen Apps. Klicken Sie auf **Blockieren**, um eine Blockierung zu aktivieren. Wählen Sie **Nicht konfiguriert** aus, um eine Blockierung zu deaktivieren.
- **Datenfreigabe zwischen Arbeitsprofilen und persönlichen Profilen** – Verwenden Sie diese Einstellung, um zu steuern, ob Apps im Arbeitsprofil Daten für Apps im persönlichen Profil freigeben können. Durch diese Einstellung werden Freigabeaktionen in Anwendungen (z.B. die Option **Freigeben...** in der Browser-App Chrome) gesteuert. Sie wird nicht auf das Verhalten beim Kopieren von Daten in die Zwischenablage und Einfügen angewendet. Im Gegensatz zu [Richtlinieneinstellungen für den App-Schutz](https://docs.microsoft.com/intune-classic/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune) werden Einstellungen für Geräteeinschränkungen über das Intune-Portal verwaltet und mithilfe der Android for Work-Arbeitsprofilpartition zum Isolieren von verwalteten Apps eingesetzt. Wählen Sie aus:
    - **Standardeinschränkungen für Freigabe**: Diese Einstellung ist das standardmäßige Freigabeverhalten des Geräts, das abhängig von der ausgeführten Android-Version variiert. Standardmäßig ist die Freigabe von Daten des persönlichen Profils für das Arbeitsprofil zulässig. Die Freigabe von Daten des Arbeitsprofils für das persönliche Profil ist dagegen standardmäßig blockiert. Durch diese Einstellung wird die Freigabe von Daten des Arbeitsprofils für das persönliche Profil verhindert. Google bietet auf Geräten, auf denen die Version 6.0 und höher ausgeführt wird, keine Möglichkeit, um die Freigabe von Daten aus dem persönlichen Profil für das Arbeitsprofil zu blockieren.   
    - **Apps im Arbeitsprofil können Freigabeanforderungen vom persönlichen Profil verarbeiten**: Aktivieren Sie mit dieser Option das integrierte Android-Feature, dass die Freigabe vom persönlichen Profil aus im Arbeitsprofil ermöglicht. Wenn diese Option aktiviert ist, können Daten durch eine Freigabeanfrage einer App im persönlichen Profil für Apps im Arbeitsprofil freigegeben werden. Diese Einstellung ist das Standardverhalten für Android-Geräte, die frühere Versionen als 6.0 ausführen.
    - **Grenzübergreifende Freigabe zulassen** – Diese Option ermöglicht die Freigabe von Daten in beide Richtungen über die Begrenzungen des Arbeitsprofils hinaus. Wenn Sie diese Einstellung auswählen, können Apps im Arbeitsprofil Daten für Apps ohne Badgeverwendung im persönlichen Profil freigeben. Verwenden Sie diese Einstellung mit Vorsicht, da sie verwalteten Apps im Arbeitsprofil die Freigabe von Daten für Apps auf der nicht verwalteten Seite des Geräts ermöglicht.

-   **Arbeitsprofilbenachrichtigungen bei Gerätesperre** – Durch diese Option wird gesteuert, ob Apps im Arbeitsprofil Daten in Benachrichtigungen anzeigen können, wenn das Gerät gesperrt ist.
-   **Standardmäßige App-Berechtigungen**: Legt die Standardberechtigungsrichtlinie für alle Apps im Arbeitsprofil fest. Ab Android 6 wird der Benutzer aufgefordert, bestimmte von den Apps benötigte Berechtigungen zu erteilen, wenn die App gestartet wird. Bei dieser Richtlinieneinstellung können Sie festlegen, ob Benutzer aufgefordert werden sollen, Berechtigungen für alle Apps im Arbeitsprofil zu gewähren. Beispielsweise können Sie dem Arbeitsprofil eine App zuweisen, die Standortzugriff benötigt. In der Regel fordert diese App den Benutzer dazu auf, den Standortzugriff durch die App zu genehmigen oder abzulehnen. Mit dieser Richtlinie können Sie entscheiden, ob alle Berechtigungen automatisch ohne Aufforderung gewährt werden sollen, ohne Aufforderung automatisch verweigert werden sollen oder ob der Endbenutzer entscheiden kann. Wählen Sie aus:
    -   **Gerätestandard**
    -   **Eingabeaufforderung**
    -   **Automatisch gewähren**
    -   **Automatisch verweigern**

    Der Status zur Erteilung der Berechtigungen kann für bestimmte Apps weitergehend definiert werden, indem eine App-Konfigurationsrichtlinie für eine einzelne App (unter **Mobile Apps** > **App-Konfigurationsrichtlinien**) definiert wird.

### <a name="work-profile-password"></a>Arbeitsprofilkennwort
- **Arbeitsprofilkennwort erforderlich** (Android 7.0 und höher mit aktiviertem Arbeitsprofil) – Definieren Sie eine Kennungsrichtlinie, die nur für die Apps im Arbeitsprofil gilt. Standardmäßig hat der Endbenutzer die Möglichkeit, die beiden separat definierten PINs zu verwenden oder diese zu einer PIN zu kombinieren, die die Stärke der jeweils stärkeren PIN übernimmt.
- **Minimale Kennwortlänge** – Geben Sie die Mindestanzahl (von **4**-**16**) an Zeichen an, die das Benutzerkennwort enthalten muss.
- **Maximaler Zeitraum der Inaktivität (in Minuten) bis zur Bildschirmsperrung**: Wählen Sie den Zeitraum, nach dessen Verstreichen das Arbeitsprofil gesperrt wird. Der Benutzer muss dann seine Anmeldeinformationen eingeben, um wieder Zugriff zu erhalten.
- **Anzahl von Anmeldefehlern, bevor das Gerät zurückgesetzt wird** – Geben Sie an, wie häufig ein falsches Kennwort eingegeben werden kann, bevor das Arbeitsprofil auf dem Gerät zurückgesetzt wird.
- **Kennwortablauf (Tage)**: Geben Sie die Anzahl der Tage an (von **1**-**255**), nach deren Verstreichen das Kennwort eines Endbenutzers geändert werden muss.
- **Erforderlicher Kennworttyp**: Wählen Sie den Typ des Kennworts, das auf dem Gerät festgelegt werden muss. Wählen Sie aus:
    - **Gerätestandard**
    - **Biometrie auf niedriger Sicherheitsstufe**
    - **Erforderlich**
    - **Mindestens numerisch**
    - **Numerisch komplex**: (sich wiederholende oder fortlaufende Ziffern wie „1111“ oder „1234“ sind nicht zulässig)
    - **Mindestens alphabetisch**
    - **Mindestens alphanumerisch**
    - **Mindestens alphanumerisch mit Symbolen**
- **Wiederverwendung vorheriger Kennwörter verhindern**: Geben Sie die Anzahl neuer Kennwörter ein (von **1**-**24**), die verwendet werden müssen, bevor ein altes wiederverwendet werden kann.
- **Entsperrung durch Fingerabdruck**: Verhindert, dass ein Endbenutzer das Gerät mithilfe des Fingerabdruckscanners entsperren kann.
- **Smart Lock und andere Vertrauens-Agents**: Ermöglicht Ihnen die Steuerung des Smart Lock-Features auf kompatiblen Geräten. Diese Telefonfunktion wird manchmal als Vertrauens-Agent bezeichnet und ermöglicht Ihnen das Deaktivieren oder Umgehen des Kennworts für das Arbeitsprofil, wenn sich das Gerät an einem vertrauenswürdigen Standort befindet, (wenn es z.B. mit einem bestimmten Bluetooth-Gerät verbunden ist oder sich in der Nähe eines NFC-Tags befindet). Mit dieser Einstellung können Sie verhindern, dass Benutzer Smart Lock konfigurieren.

## <a name="device-password"></a>Gerätekennwort

- **Minimale Kennwortlänge:** Geben Sie die Mindestanzahl (von **4**-**14**) an Ziffern oder Zeichen an, die das Benutzerkennwort enthalten muss.
- **Maximaler Zeitraum der Inaktivität (in Minuten) bis zur Bildschirmsperrung**: Wählen Sie den Zeitraum, nach dessen Verstreichen ein inaktives Gerät automatisch gesperrt wird.
- **Anzahl von Anmeldefehlern, bevor das Gerät zurückgesetzt wird**: Geben Sie an, wie häufig ein falsches Kennwort eingegeben werden kann, bevor alle Daten auf dem Gerät gelöscht werden.
- **Kennwortablauf (Tage)**: Geben Sie die Anzahl der Tage an (von **1**-**255**), nach deren Verstreichen das Kennwort eines Endbenutzers geändert werden muss.
- **Erforderlicher Kennworttyp**: Wählen Sie den Typ des Kennworts, das auf dem Gerät festgelegt werden muss. Wählen Sie aus:
    - **Gerätestandard**
    - **Biometrie auf niedriger Sicherheitsstufe**
    - **Erforderlich**
    - **Mindestens numerisch**
    - **Numerisch komplex**: (sich wiederholende oder fortlaufende Ziffern wie „1111“ oder „1234“ sind nicht zulässig)
    - **Mindestens alphabetisch**
    - **Mindestens alphanumerisch**
    - **Mindestens alphanumerisch mit Symbolen**
- **Wiederverwendung vorheriger Kennwörter verhindern**: Geben Sie die Anzahl neuer Kennwörter ein (von **1**-**24**), die verwendet werden müssen, bevor ein altes wiederverwendet werden kann.
- **Entsperrung durch Fingerabdruck**: Verhindert, dass ein Endbenutzer das Gerät mithilfe des Fingerabdruckscanners entsperren kann.
- **Smart Lock und andere Vertrauens-Agents**: Ermöglicht Ihnen die Steuerung des Smart Lock-Features auf kompatiblen Geräten. Diese Telefonfunktion wird manchmal als Vertrauens-Agent bezeichnet und ermöglicht Ihnen das Deaktivieren oder Umgehen des Kennworts für den Gerätesperrbildschirm, wenn sich das Gerät an einem vertrauenswürdigen Standort befindet, (wenn es z.B. mit einem bestimmten Bluetooth-Gerät verbunden ist oder sich in der Nähe eines NFC-Tags befindet). Mit dieser Einstellung können Sie verhindern, dass Benutzer Smart Lock konfigurieren.

## <a name="system-security"></a>Systemsicherheit

 - **Bedrohungsüberprüfung für Apps**: Erzwingen Sie, dass die Einstellung **Apps überprüfen** für Arbeits- und persönliche Profile aktiviert ist.

   > [!Note]  
   > Diese Einstellung funktioniert nur auf Geräten mit Android O und höher. 

## <a name="next-steps"></a>Nächste Schritte

Verwenden Sie die Informationen im Thema [So konfigurieren Sie Einstellungen für Geräteeinschränkungen in Microsoft Intune](device-restrictions-configure.md), um das Profil zu speichern und es Benutzern und Geräten zuzuordnen.
