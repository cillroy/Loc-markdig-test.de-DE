---
title: "Einstellungen von Windows Intune Endpoint Protection für Windows 10"
titlesuffix: Azure portal
description: "In diesem Artikel lernen Sie die Intune-Einstellungen zur Steuerung von Endpoint Protection wie z.B. BitLocker auf Windows 10-Geräten kennen."
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 08/23/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3af7c91b-8292-4c7e-8d25-8834fcf3517a
ms.reviewer: ilwu
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 66d13a5a5d4b74cc70696239514875fe0092a164
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2017
---
# <a name="endpoint-protection-settings-for-windows-10-and-later-in-microsoft-intune"></a>Endpoint Protection-Einstellungen für Windows 10 und höher in Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Mit dem Endpoint Protection-Profil können Sie Sicherheitsfunktionen auf Windows 10-Geräten steuern, wie z.B. BitLocker und Windows Defender.

In diesem Thema erfahren Sie, wie Sie Endpoint Protection-Profile erstelle können.

> [!Note]
> Diese Einstellungen werden nicht auf der Home Edition und auf der Professional Edition von Windows 10 unterstützt.

## <a name="create-an-endpoint-protection-profile"></a>Erstellen eines Endpoint Protection-Profils

1. Melden Sie sich beim Azure-Portal an.
2. Wählen Sie **Weitere Dienste** > **Überwachung und Verwaltung** > **Intune** aus.
3. Wählen Sie auf dem Blatt **Intune** die Option **Gerätekonfiguration** aus.
2. Wählen Sie auf dem Blatt **Gerätekonfiguration** die Option **Verwalten** > **Profile** aus.
3. Wählen Sie auf dem Blatt „Profile“ die Option **Profil erstellen** aus.
4. Geben Sie auf dem Blatt **Profil erstellen** einen **Namen** und eine **Beschreibung** für das Gerätefunktionsprofil ein.
5. Wählen Sie in der Dropdownliste **Plattform** die Option **Windows 10 und höher** aus.
6. Wählen Sie in der Dropdownliste **Profiltyp** die Option **Endpoint Protection** aus.
7. Nehmen Sie auf dem Blatt **Windows-Verschlüsselung** die gewünschten Einstellungen vor. Die Angaben in diesem Thema helfen Ihnen dabei zu verstehen, was die Auswirkungen jeder Einstellung sind. Wenn Sie fertig sind, wählen Sie **OK** aus.
8. Gehen Sie zurück zum Blatt **Profil erstellen**, und klicken Sie auf **Erstellen**.

Das Profil wird erstellt und auf dem Blatt mit der Profilliste angezeigt.

## <a name="windows-defender-smartscreen-settings"></a>Einstellungen für Windows Defender SmartScreen

- **SmartScreen für Apps und Dateien**: Hiermit wird Windows SmartScreen für die Datei- und App-Ausführung aktiviert.
- **Ausführung nicht überprüfter Dateien**: Hiermit wird die Ausführung von Dateien durch den Benutzer gesperrt, die nicht durch Windows SmartScreen überprüft wurden.

## <a name="windows-encryption-settings"></a>Windows-Verschlüsselungseinstellungen

### <a name="windows-settings"></a>Windows-Einstellungen

- **Geräte müssen verschlüsselt sein (nur Desktop)**: Wenn diese Einstellung aktiv ist, werden Benutzer aufgefordert, die Geräteverschlüsselung zu aktivieren. Zusätzlich werden Sie gebeten zu bestätigen, dass keine Verschlüsselung eines anderen Anbieters aktiviert ist. Wenn die Windows-Verschlüsselung eingeschaltet wird, während eine andere Verschlüsselungsmethode aktiv ist, wird das Gerät möglicherweise instabil.
- **Speicherkarte muss verschlüsselt sein (nur mobil)**: Wenn diese Einstellung aktiv ist, werden alle vom Gerät verwendeten Wechselspeicherkarten verschlüsselt.


### <a name="bitlocker-base-settings"></a>BitLocker-Grundeinstellungen

- **Verschlüsselungsmethoden konfigurieren**: Wenn diese Einstellung aktiv ist, können Sie Verschlüsselungsalgorithmen für Betriebssystem-, Daten- und Wechseldatenträger konfigurieren.
    - **Verschlüsselung für Betriebssystemlaufwerke**: Wählen Sie die Verschlüsselungsmethode für Betriebssystemlaufwerken. Es wird empfohlen, dass Sie den XTS-AES-Algorithmus verwenden.
    - **Verschlüsselung für Festplattenlaufwerke**: Wählen Sie die Verschlüsselungsmethode für Festplattenlaufwerke (integriert). Es wird empfohlen, dass Sie den XTS-AES-Algorithmus verwenden.
    - **Verschlüsselung für Wechseldatenträger**: Wählen Sie die Verschlüsselungsmethode für Wechseldatenträger. Wenn der Wechseldatenträger mit Geräten verwendet wird, die nicht unter Windows 10 laufen, wird empfohlen, dass Sie den AES-CBC-Algorithmus verwenden.


### <a name="bitlocker-os-drive-settings"></a>Einstellung für BitLocker-OS-Datenträger

- **Zusätzliche Authentifizierung beim Start anfordern** -
    - **BitLocker mit nicht kompatiblem TPM-Chip** -
    - **TPM-Systemstart**: Legen Sie fest, ob ein TPM-Chip verwendet werden darf oder muss.
    - **TPM-Systemstart-PIN**: Legen Sie fest, ob mit dem TPM-Chip ein Systemstart-PIN verwendet werden darf oder muss.
    - **TPM-Systemstartschlüssel**: Legen Sie fest, ob mit dem TPM-Chip ein Systemstartschlüssel verwendet werden darf oder muss.
    - **TPM-Systemstartschlüssel und -Systemstart-PIN**: Legen Sie fest, ob mit dem TPM-Chip ein Systemstartschlüssel und ein PIN verwendet werden darf oder muss.
- **PIN-Mindestlänge**: Wenn diese Einstellung aktiv ist, können Sie eine Mindestlänge für den TPM-Systemstart-PIN festlegen.
    - **Mindestanzahl von Zeichen**: Geben Sie die Zahl an Zeichen an, die für den Systemstart-PIN erforderlich sind, zwischen **4**-**20**.
- **Betriebssystemwiederherstellung aktivieren**: Wenn diese Einstellung aktiv ist, können Sie steuern, wie durch BitLocker geschützte Betriebssystemdatenträger wiederhergestellt werden, wenn die erforderlichen Systemstartinformationen nicht verfügbar sind.
    - **Agent für zertifikatbasierte Datenwiederherstellung**: Wenn diese Einstellung aktiv ist, können Datenwiederherstellungs-Agents mit durch BitLocker geschützten Betriebssystemdatenträgern verwendet werden.
    - **Erstellung des Wiederherstellungskennworts durch den Benutzer**: Legen Sie fest, ob Benutzer ein 48-stelliges Wiederherstellungskennwort generieren dürfen oder müssen.
    - **Erstellung des Wiederherstellungsschlüssels durch den Benutzer**: Legen Sie fest, ob Benutzer ein 256-Bit-Wiederherstellungskennwort generieren dürfen oder müssen.
    - **Wiederherstellungsoptionen im BitLocker-Setup-Assistenten ausblenden**: Wenn Sie diese Einstellung festlegen, können Sie verhindern, dass Benutzer Wiederherstellungsoptionen sehen bzw. ändern können, wenn sie BitLocker aktivieren.
    - **BitLocker-Wiederherstellungsinformationen in AD DS speichern**: Aktiviert das Speichern von BitLocker-Wiederherstellungsinformationen in Active Directory.
    - **Speicherung von BitLocker-Wiederherstellungsinformationen in AD DS konfigurieren**: Legen Sie fest, welche BitLocker-Wiederherstellungsinformationen in Active Directory gespeichert werden. Wählen Sie aus:
        - **Wiederherstellungskennwörter und Schlüsselpakete sichern**
        - **Nur Wiederherstellungskennwörter sichern**
    - **Wiederherstellungsinformationen müssen vor dem Aktivieren von BitLocker in AD DS gespeichert werden**: Wenn diese Einstellung aktiviert ist, verhindern Sie, dass Benutzer BitLocker aktivieren, es sei denn, das Gerät ist mit einer Domäne verbunden.
- **Pre-Boot-Wiederherstellungsmeldung und -URL aktivieren**: Legen Sie diese Einstellung fest, um die Meldung und URL zu konfigurieren, die auf dem Pre-Boot-Schlüsselwiederherstellungsbildschirm angezeigt werden.
    - **Pre-Boot-Wiederherstellungsmeldung**: Legen Sie fest, wie die Pre-Boot-Wiederherstellungsmeldung Benutzern angezeigt wird. Wählen Sie aus:
        - **Standardmäßige Wiederherstellungsmeldung und -URL verwenden**
        - **Leere Wiederherstellungsmeldung und -URL verwenden**
        - **Benutzerdefinierte Wiederherstellungsmeldung**
        - **Benutzerdefinierte Wiederherstellungs-URL**


### <a name="bitlocker-fixed-data-drive-settings"></a>Einstellungen für das BitLocker-Festplattenlaufwerk

- **Schreibzugriff auf Festplattenlaufwerke verweigern, die nicht durch BitLocker geschützt sind**: Wenn diese Einstellung festgelegt wurde, muss der BitLocker-Schutz auf allen Festplatten- und integrierten Laufwerken aktiviert sein, damit in sie geschrieben werden kann.
- **Wiederherstellung von Festplattenlaufwerken aktivieren**: Wenn diese Einstellung festgelegt wurde, können Sie steuern, wie durch BitLocker geschützte Festplattenlaufwerke wiederhergestellt, wenn die erforderlichen Systemstartinformationen nicht vorliegen.
    - **Datenwiederherstellungs-Agent**: Wenn diese Einstellung aktiviert ist, können Datenwiederherstellungs-Agents mit durch BitLocker geschützten Festplattenlaufwerken verwendet werden.
    - **Erstellung des Wiederherstellungskennworts durch den Benutzer**: Legen Sie fest, ob Benutzer ein 48-stelliges Wiederherstellungskennwort generieren dürfen oder müssen.  
    - **Erstellung des Wiederherstellungsschlüssels durch den Benutzer**: Legen Sie fest, ob Benutzer ein 256-Bit-Wiederherstellungskennwort generieren dürfen oder müssen.
    - **Wiederherstellungsoptionen im BitLocker-Setup-Assistenten ausblenden**: Wenn Sie diese Einstellung festlegen, können Sie verhindern, dass Benutzer Wiederherstellungsoptionen sehen bzw. ändern können, wenn sie BitLocker aktivieren.
    - **BitLocker-Wiederherstellungsinformationen in AD DS speichern**: Aktiviert das Speichern von BitLocker-Wiederherstellungsinformationen in Active Directory.
    - **Speicherung von BitLocker-Wiederherstellungsinformationen in AD DS konfigurieren**: Legen Sie fest, welche BitLocker-Wiederherstellungsinformationen in Active Directory gespeichert werden. Wählen Sie aus:
        - **Wiederherstellungskennwörter und Schlüsselpakete sichern**
        - **Nur Wiederherstellungskennwörter sichern**
    - **Wiederherstellungsinformationen müssen vor dem Aktivieren von BitLocker in AD DS gespeichert werden**: Aktivieren Sie diese Einstellung, um zu verhindern, dass Benutzer BitLocker aktivieren, es sei denn, das Gerät ist mit einer Domäne verbunden und BitLocker-Wiederherstellungsinformationen wurden erfolgreich in Active Directory gespeichert.


### <a name="bitlocker-removable-data-drive-settings"></a>Einstellungen für den BitLocker-Wechseldatenträger

- **Schreibzugriff auf Wechseldatenträger verweigern, die nicht durch BitLocker geschützt sind**: Legen Sie fest, ob die BitLocker-Verschlüsselung für Wechseldatenträger erforderlich ist.
    - **Schreibzugriff auf Geräte blockieren, die in einer anderen Organisation konfiguriert sind**: Legen Sie fest, ob in Wechseldatenträger, die einer anderen Organisation angehören, geschrieben werden darf.



## <a name="next-steps"></a>Nächste Schritte

Wenn Sie fortfahren und dieses Profil Gruppen zuweisen möchten, lesen Sie unter [Zuweisen von Geräteprofilen](device-profile-assign.md) nach.
