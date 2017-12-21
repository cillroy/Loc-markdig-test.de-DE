---
title: Herunterladen der Skycure iOS-App-Konfigurationsrichtlinie zur Verwendung mit Intune
titlesuffix: Azure portal
description: Laden Sie die Skycure iOS-App-Konfigurationsrichtlinie zur Verwendung mit Intune herunter.
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 06/21/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 1bdc2ecf-32d0-4b6a-80b4-dbcdb9909010
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 296d5545530e8001c0648bafac3101b94f45529d
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2017
---
# <a name="download-skycure-ios-app-configuration-policy"></a>Herunterladen der Skycure iOS-App-Konfigurationsrichtlinie

## <a name="before-you-begin"></a>Vorbereitung

Zur Ausführung der nächsten Schritte müssen Sie sich in der Skycure-Verwaltungskonsole anmelden.

> [!TIP] 
> Wenn Sie Microsoft Internet Explorer 11 oder Edge verwenden, müssen Sie die Skycure-Verwaltungskonsole möglicherweise im privaten Modus öffnen.

## <a name="to-download-the-ios-app-configuration-policy"></a>Herunterladen der iOS-App-Konfigurationsrichtlinie

1.  Gehen Sie zur [Skycure-Verwaltungskonsole](https://aad.skycure.com).

2.  Geben Sie Ihre **Skycure-Administratoranmeldeinformationen** ein, und klicken Sie dann auf **Continue** (Weiter).

    ![Skycure-Verwaltungskonsolenanmeldung](./media/skycure-ios-app-1.png)

    > [!IMPORTANT] 
    > Der Skycure-Administratorbenutzername ist ein E-Mail-Konto, das eine gültiges Benutzerkonto in Azure Active Directory sein muss, andernfalls schlägt die Anmeldung fehl. Skycure verwendet Azure Active Directory zum Authentifizieren des Administratorbenutzernamens mithilfe von einmaligem Anmelden (SSO).

3.  Wechseln Sie zu **Settings** &gt; **Device Management Integrations** &gt; **EMM Integration Selection** (Einstellungen > Geräteverwaltungsintegrationen > EMM-Integrationsauswahl), wählen Sie **Microsoft Intune** aus, und speichern Sie dann Ihre Auswahl.

4.  Klicken Sie auf den Link **Integration setup files** (Integrationssetupdateien), und speichern Sie die generierte \*.zip-Datei. Die ZIP-Datei enthält die Datei **skycure\_configuration.plist**, die zum Erstellen der iOS-App-Konfigurationsrichtlinie im klassischen Intune-Portal verwendet wird.

![Skycure-Integrationssetupdateien](./media/skycure-ios-app-2.png)

## <a name="next-steps"></a>Nächste Schritte

[Hinzufügen und Zuweisen von Skycure-Apps, der Microsoft Authenticator-App und der iOS-Konfigurationsrichtlinie](mtd-apps-ios-app-configuration-policy-add-assign.md)
