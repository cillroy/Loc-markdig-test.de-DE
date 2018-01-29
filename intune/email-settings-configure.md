---
title: So konfigurieren Sie Intune-E-Mail-Einstellungen
titleSuffix: Azure portal
description: "In diesem Artikel erfahren Sie, wie Sie Intune konfigurieren, um Verbindungen mit Unternehmens-E-Mail-Diensten auf Geräten, die Sie verwalten, herzustellen."
keywords: 
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 06/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 484bd9b0-fbf1-4f4f-940c-6b12fa07e228
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: f5c4a0466e4de421a23b70a7beb4d1651d6caf7a
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2018
---
# <a name="how-to-configure-email-settings-in-microsoft-intune"></a>Konfigurieren von E-Mail-Einstellungen in Microsoft Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Mit E-Mail-Profilen können Sie Einstellungen, die zum Herstellen von Verbindungen und zum Synchronisieren mit Unternehmens-E-Mails erforderlich sind, für Geräte konfigurieren. Damit können Sie sicherzustellen, dass die Einstellungen für alle Ihre Geräte einheitlich sind. Außerdem reduzieren Sie damit Supportanfragen von Endbenutzern, die nicht die richtigen E-Mail-Einstellungen kennen.

Der integrierte E-Mail-Client wird auf den meisten Plattformen unterstützt. Die meisten E-Mail-Apps von Drittanbietern werden derzeit nicht unterstützt.

Sie können E-Mail-Profile verwenden, um den systemeigenen E-Mail-Client auf den folgenden Gerätetypen zu konfigurieren:

- Android Samsung KNOX Standard 4.0 und höher
- Android for Work
- iOS 8.0 und höher
- Windows Phone 8.1 und höher
- Windows 10 (Desktop) und Windows 10 Mobile

Anhand der Informationen in diesem Thema lernen Sie die Grundlagen zum Konfigurieren von E-Mail-Profilen kennen. In den weiterführenden Themen zu den einzelnen Plattformen erfahren Sie etwas über Besonderheiten der jeweiligen Geräte.

## <a name="create-a-device-profile-containing-email-settings"></a>Erstellen eines Geräteprofils mit E-Mail-Einstellungen

1. Melden Sie sich beim Azure-Portal an.
2. Wählen Sie **Weitere Dienste** > **Überwachung und Verwaltung** > **Intune** aus.
3. Wählen Sie auf dem Blatt **Intune** die Option **Gerätekonfiguration** aus.
2. Wählen Sie auf dem Blatt **Gerätekonfiguration** die Option **Verwalten** > **Profile** aus.
3. Wählen Sie auf dem Blatt „Profile“ die Option **Profil erstellen** aus.
4. Geben Sie auf dem Blatt **Profil erstellen** einen **Namen** und eine **Beschreibung** für das E-Mail-Profil ein.
5. Wählen Sie in der Dropdownliste **Plattform** die Geräteplattform aus, auf die Sie E-Mail-Einstellungen anwenden möchten. Derzeit können Sie eine der folgenden Plattformen für die E-Mail-Geräteeinstellungen auswählen:
    - **Android** (nur Samsung Android KNOX Standard)
    - **Android for Work**
    - **iOS**
    - **Windows Phone 8.1**
    - **Windows 10 und höher**
6. Wählen Sie in der Dropdownliste **Profiltyp** die Option **E-Mail** aus.
7. Die konfigurierbaren Einstellungen variieren je nach der ausgewählten Plattform. In den folgenden Themen finden Sie ausführliche Informationen zu den Einstellungen für die einzelnen Plattformen:
    - [Android for Work- und Samsung KNOX Standard-Einstellungen](email-settings-android.md)
    - [Einstellungen für iOS](email-settings-ios.md)
    - [Einstellungen für Windows Phone 8.1](email-settings-windows-phone-8-1.md)
    - [Einstellungen für Windows 10](email-settings-windows-10.md)
8. Navigieren Sie anschließend zurück zum Blatt **Profil erstellen**, und klicken Sie auf **Erstellen**.

Das Profil wird erstellt und auf dem Blatt mit der Profilliste angezeigt.
Wenn Sie fortfahren und dieses Profil Gruppen zuweisen möchten, lesen Sie unter [Zuweisen von Geräteprofilen](device-profile-assign.md) nach.

## <a name="further-information"></a>Weitere Informationen

### <a name="remove-an-email-profile"></a>Entfernen eines E-Mail-Profils

Wenn Sie ein E-Mail-Profil von einem Gerät entfernen möchten, bearbeiten Sie die Zuweisung, und entfernen Sie alle Gruppen, in denen das Gerät Mitglied ist. Beachten Sie, dass Sie ein E-Mail-Profil nur dann auf diese Weise entfernen können, wenn es nicht das einzige E-Mail-Profil auf dem Gerät ist.

### <a name="securing-email-access"></a>Schützen des E-Mail-Zugriffs

E-Mail-Profile können mit einer von zwei Methoden geschützt werden:

1. **Zertifikate:** Beim Erstellen des E-Mail-Profils wählen Sie ein Zertifikatprofil aus, das Sie zuvor in Intune erstellt haben. Dieses wird als Identitätszertifikat bezeichnet und dient zur Authentifizierung anhand eines vertrauenswürdigen Zertifikatprofils (oder eines Stammzertifikats), mit dem überprüft wird, ob das Gerät des Benutzers eine Verbindung herstellen darf. Das vertrauenswürdige Zertifikat wird auf dem Computer zugewiesen, der die E-Mail-Verbindung authentifiziert. In der Regel ist dies der native Mailserver.
Weitere Informationen zum Erstellen und Verwenden von Zertifikatprofilen in Intune finden Sie unter [Konfigurieren von Zertifikaten mit Intune](certificates-configure.md).
2. **Benutzername und Kennwort:** Der Benutzer authentifiziert sich beim nativen Mailserver durch Angabe seines Benutzernamens und Kennworts.
Das Kennwort ist nicht im E-Mail-Profil enthalten, sodass der Benutzer dieses beim Herstellen einer Verbindung mit dem E-Mail-System bereitstellen muss.


### <a name="how-intune-handles-existing-email-accounts"></a>Behandlung vorhandener E-Mail-Konten in Intune

Wenn für den Benutzer bereits ein E-Mail-Konto konfiguriert wurde, hängt das Ergebnis der Zuweisung eines Intune-E-Mail-Profils von der Geräteplattform ab:

- **iOS:** Basierend auf dem Hostnamen und der E-Mail-Adresse wird ein vorhandenes doppeltes E-Mail-Profil erkannt. Das doppelte E-Mail-Profil verhindert die Zuweisung eines Intune-Profils. In diesem Fall informiert das Unternehmensportal den Benutzer über die fehlende Konformität fordert ihn auf, das manuell konfigurierte E-Mail-Profil zu entfernen. Weisen Sie Ihre Benutzer an, sich vor der Installation eines E-Mail-Profils zu registrieren und die Einrichtung des Profils durch Intune zuzulassen, um das Problem zu vermeiden.
- **Windows:** Basierend auf dem Hostnamen und der E-Mail-Adresse wird ein vorhandenes doppeltes E-Mail-Profil erkannt. Intune überschreibt das vorhandene vom Benutzer erstellte E-Mail-Profil.
- **Android Samsung KNOX Standard** Basierend auf der E-Mail-Adresse wird ein vorhandenes doppeltes E-Mail-Profil erkannt und durch das Intune-Profil überschrieben.
Da Android zum Identifizieren des Profils keinen Hostnamen verwendet, wird davon abgeraten, mehrere E-Mail-Profile für die Verwendung unter derselben E-Mail-Adresse auf unterschiedlichen Hosts zu erstellen, da sie sich gegenseitig überschreiben.
- **Android for Work** Intune stellt zwei Android for Work-E-Mail-Profile bereit: eines für die E-Mail-App Gmail und eines für die E-Mail-App Nine Work. Diese Apps können im Google Play Store heruntergeladen werden; sie installieren ein Arbeitsprofil auf dem Gerät, sodass keine doppelten Profile erstellt werden. Beide Apps unterstützen Verbindungen mit Exchange. Stellen Sie auf den Geräten der Benutzer eine dieser E-Mail-Apps bereit, erstellen Sie das entsprechende Profil, und stellen Sie das entsprechende E-Mail-Profil bereit, um die E-Mail-Konnektivität zu ermöglichen. E-Mail-Apps, z.B. Nine Work, können möglicherweise kostenpflichtig sein. Lesen Sie die Lizenzierungsdetails der App oder kontaktieren Sie das Unternehmen, das die App bereitstellt, um Fragen zu stellen.

### <a name="update-an-email-profile"></a>Aktualisieren eines E-Mail-Profils

Wenn Sie ein zuvor zugewiesenes E-Mail-Profil ändern, werden Endbenutzer möglicherweise in einer Meldung aufgefordert, die Neukonfiguration ihrer E-Mail-Einstellungen zu genehmigen.
