---
title: "Zurücksetzen der Kennung auf Windows-Geräten mit Intune"
titlesuffix: Azure portal
description: "In diesem Artikel erfahren Sie, wie Sie mithilfe von Intune die Kennung auf Windows-Geräten mit dem integrierten PIN-Zurücksetzungsdienst von Microsoft zurücksetzen können."
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 08/09/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5027d012-d6c2-4971-a9ac-217f91d67d87
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: faf3e9b81f76755135f73f8753305d96d227ec14
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2017
---
# <a name="reset-the-passcode-on-windows-devices-integrated-with-the-microsoft-pin-reset-service-using-intune"></a>Zurücksetzen der Kennung auf Windows-Geräten mit dem integrierten PIN-Zurücksetzungsdienst von Microsoft mithilfe von Intune

Die Zurücksetzungsfunktion der Kennung ist bei Windows-Geräten in den PIN-Zurücksetzungsdienst von Microsoft integriert, mit dem Sie für Geräte, auf denen Windows 10 Mobile ausgeführt wird, eine neue Kennung generieren können. Auf den Geräten muss das Windows 10 Creators Update oder höher ausgeführt werden.

## <a name="supported-platforms"></a>Unterstützte Plattformen

- Windows – Unterstützt unter Windows 10 Creators Update und höher (mit Azure AD verknüpft)
- Windows Phone – Nicht unterstützt
- iOS – Nicht unterstützt
- macOS – Nicht unterstützt
- Android – Nicht unterstützt


## <a name="before-you-start"></a>Vorbereitung

Bevor Sie die Kennung auf von Ihnen verwalteten Windows-Geräten remote zurücksetzen können, müssen Sie den PIN-Zurücksetzungsdienst in Ihren Intune-Mandanten integrieren und die Geräte, die Sie verwalten, konfigurieren. Gehen Sie dazu folgendermaßen vor:

### <a name="connect-intune-with-the-pin-reset-service"></a>Verbinden von Intune mit dem PIN-Zurücksetzungsdienst

1. Melden Sie sich auf der [Website zur Integration des PIN-Zurücksetzungsdiensts von Microsoft](https://login.windows.net/common/oauth2/authorize?response_type=code&client_id=b8456c59-1230-44c7-a4a2-99b085333e84&resource=https%3A%2F%2Fgraph.windows.net&redirect_uri=https%3A%2F%2Fcred.microsoft.com&state=e9191523-6c2f-4f1d-a4f9-c36f26f89df0&prompt=admin_consent) an. Verwenden Sie hierzu das Mandantenadministratorkonto, mit dem Sie Ihren Intune-Mandanten verwalten.
2. Klicken Sie nach der Anmeldung auf **Annehmen**, um dem PIN-Zurücksetzungsdienst Zugriff auf Ihr Konto zu gewähren.<br>
![Seite "Berechtigungen" für den Dienst Zurücksetzen der PIN](./media/pin-reset-service-application.png)
3. Im Azure-Portal wird angezeigt, dass Intune und der PIN-Zurücksetzungsdienst aus dem Blatt „Unternehmensanwendungen > Alle Anwendungen“ integriert wurden, wie der folgende Screenshot verdeutlicht:<br>
![Zurücksetzen der PIN-dienstanwendung in Azure](./media/pin-reset-service-home-screen.png)
4. Melden Sie sich auf [dieser Website](https://login.windows.net/common/oauth2/authorize?response_type=code&client_id=9115dd05-fad5-4f9c-acc7-305d08b1b04e&resource=https%3A%2F%2Fcred.microsoft.com%2F&redirect_uri=ms-appx-web%3A%2F%2FMicrosoft.AAD.BrokerPlugin%2F9115dd05-fad5-4f9c-acc7-305d08b1b04e&state=6765f8c5-f4a7-4029-b667-46a6776ad611&prompt=admin_consent) mit Ihren Anmeldeinformationen des Intune-Mandantenadministrators an. Klicken Sie erneut auf **Annehmen**, um dem Dienst Zugriff auf Ihr Konto zu gewähren.

### <a name="configure-windows-devices-to-use-pin-reset"></a>Konfigurieren von Windows-Geräten zur Verwendung des PIN-Zurücksetzungsdiensts

Verwenden Sie zum Konfigurieren der PIN-Zurücksetzung auf von Ihnen verwalteten Windows-Geräten eine [benutzerdefinierte Intune-Geräterichtlinie für Windows 10](custom-settings-windows-10.md), um die Funktion zu aktivieren. Konfigurieren Sie die Richtlinie mithilfe des folgenden Konfigurationsdienstanbieters für Windows-Richtlinien (Configuration Service Provider, CSPs):


- **Für Geräte** - **./Device/Vendor/MSFT/PassportForWork/*Mandanten-ID*/Policies/EnablePinRecovery**

Die *Mandanten-ID* bezieht sich auf Ihre Azure Active Directory-ID, die Sie auf der Seite **Eigenschaften** in Azure Active Directory finden.

Legen Sie den Wert diesen CSP auf **TRUE** fest.

## <a name="steps-to-reset-the-passcode"></a>Vorgehensweise zur Zurücksetzung der Kennung

1. Melden Sie sich beim Azure-Portal an.
2. Wählen Sie **Weitere Dienste** > **Überwachung und Verwaltung** > **Intune** aus.
3. Wählen Sie auf dem Blatt **Intune** die Option **Geräte** aus.
4. Wählen Sie auf dem Blatt **Geräte** die Optionen **Verwalten** > **Alle Geräte** aus.
5. Wählen Sie das Gerät aus, für das Sie die Kennung zurücksetzen möchten. Wählen Sie dann auf dem Blatt „Geräteeigenschaften“ die Option **Neue Kennung** aus.
6. Bestätigen Sie anschließend mit **Ja**. Die Kennung wird generiert und für die folgenden sieben Tage im Portal angezeigt.

## <a name="next-steps"></a>Nächste Schritte

Sollte bei der Zurücksetzung der Kennung ein Fehler auftreten, wird im Portal ein Link mit weiteren Informationen angezeigt.


