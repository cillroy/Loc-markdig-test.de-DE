---
title: "Behandlung von Problemen bei der Registrierung von Windows 10-Geräten | Microsoft-Dokumentation"
description: 
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 07/13/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4ab630b6-47ff-443b-a2a5-be23388bcea7
searchScope: User help
ROBOTS: 
ms.reviewer: priyar
ms.suite: ems
ms.custom: intune-enduser
ms.openlocfilehash: 7160f58f60624815137e2990bd06188edd4ede81
ms.sourcegitcommit: f2f147a1177d1cf5bbc8001701eb8f44dd833b7d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/12/2017
---
# <a name="troubleshoot-your-windows-10-device-enrollment"></a>Behandlung von Problemen bei der Registrierung von Windows 10-Geräten
Wenn Sie die Schritte unter [Registrieren Ihres Windows 10 Mobile- oder Windows 10-Desktopgeräts bei Intune](enroll-your-w10-phone-or-w10-pc-windows.md) befolgt haben, aber dennoch nicht auf E-Mails und Dateien Ihres Geschäfts-, Schul- oder Unikontos zugreifen können, führen Sie zur Problembehandlung die folgenden Schritte durch.

1.  Sehen Sie sich die beiden folgenden Bildschirme an, und suchen Sie denjenigen heraus, der der Anzeige auf Ihrem Gerät entspricht. Befolgen Sie die Schritte, die zu diesem Bildschirm gehören.

    Wenn dieser Bildschirm angezeigt wird, befolgen Sie die Schritte unter [Schritte zur Problembehandlung bei Anzeige von „Zugriff auf Geschäfts-, Schul- oder Unikonto“](#troubleshooting-steps-to-follow-if-you-see-access-work-or-school).

    ![settings-accounts-access-work-or-school](./media/w10-enroll-rs1-connect-to-work-or-school.png)

    Wenn dieser Bildschirm angezeigt wird, befolgen Sie die Schritte unter [Schritte zur Problembehandlung bei Anzeige von „Ihr Konto“](#troubleshooting-steps-to-follow-if-you-see-your-account).

    ![settings-accounts-your-account](./media/W10-enroll-2-accounts-your-account.png)

## <a name="troubleshooting-steps-to-follow-if-you-see-access-work-or-school"></a>Schritte zur Problembehandlung bei Anzeige von „Zugriff auf Geschäfts-, Schul- oder Unikonto“

1.  Wenn Sie die obigen Schritte ausgeführt haben und trotzdem nicht auf E-Mails und Dateien Ihres Geschäfts-, Schul- oder Unikontos zugreifen können, wechseln Sie zurück zu **Zugriff auf Geschäfts-, Schul- oder Unikonto**.

2. Führen Sie eines der folgenden Verfahren aus:

    - Wenn eine Verbindung ähnlich der unten gezeigten Abbildung angezeigt wird, tippen sie darauf, und überprüfen Sie, ob die Optionen „Verwalten“, „Info“ und „Trennen“ angezeigt werden. Wenn das der Fall ist, sind Sie jetzt registriert und verbunden.

    ![validate-successful-enrollment](./media/w10-enroll-rs1-validate-successful-enrollment.png)

    - Wenn die oben gezeigten Verbindungsinformationen nicht angezeigt werden oder einige Optionen fehlen, tippen Sie auf **Verbinden**, und melden Sie sich mit den Anmeldeinformationen für Ihr Geschäfts-, Schul- oder Unikonto an. Jetzt sollte eine Verbindung hergestellt sein.

## <a name="troubleshooting-steps-to-follow-if-you-see-your-account"></a>Schritte zur Problembehandlung bei Anzeige von „Mein Konto“

Wenn Sie die obigen Schritte ausgeführt haben und trotzdem nicht auf E-Mails, Dateien und andere Daten Ihres Geschäfts-, Schul- oder Unikontos zugreifen können, wechseln Sie zurück zu **Konten**, und tippen Sie auf **Geschäftszugriff**.

- Wenn Ihr Geschäfts- oder Schulkonto angezeigt wird, sind keine weiteren Schritte erforderlich. Sie sind verbunden.

- Wenn Ihr Geschäfts- oder Schulkonto nicht angezeigt wird, tippen Sie auf **Verbinden**, und melden Sie sich mit den Anmeldeinformationen Ihres Geschäfts- oder Schulkontos an.

## <a name="troubleshooting-steps-to-follow-if-you-see-set-up-a-work-or-school-account"></a>Schritte zur Problembehandlung bei Anzeige von „Geschäfts-, Schul- oder Unikonto einrichten“

Wenn eine Meldung angezeigt wird, die __We couldn't auto-discover a management endpoint matching the username entered. Please check your username and try again. If you know the URL to your management endpoint, please enter it.__ (Es konnte automatisch kein Verwaltungsendpunkt erkannt werden, der mit dem eingegebenen Benutzernamen übereinstimmt. Bitte überprüfen Sie Ihren Benutzernamen, und versuchen Sie es noch einmal. Wenn Sie die URL zu Ihrem Verwaltungsendpunkt kennen, geben Sie sie ein.) angibt, versuchen Sie, Ihren Benutzernamen und das Kennwort erneut anzugeben. Wenn es immer noch nicht funktioniert, wenden Sie sich für die Website, die Sie im Textfeld **Verwaltungsendpunkt** bereitstellen müssen, an den Support Ihres Unternehmens. Dies ist eine Website, die in etwas so aussieht: **www.ihrefirma.aufmicrosoft.com**.

Benötigen Sie weitere Unterstützung? Kontaktieren Sie den Support Ihres Unternehmens. Die entsprechenden Kontaktinformationen finden Sie auf der [Unternehmensportal-Website](https://portal.manage.microsoft.com#HelpDeskDialog).
