---
title: "Übersicht über den MDM-Lebenszyklus"
description: "Erfahren Sie, wie Ihnen Intune mit der Verwaltung von Geräten während ihres Lebenszyklus (vom Registrieren über das Konfigurieren bis zum letztendlichen Abkoppeln) behilflich sein kann."
keywords: 
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 06/07/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f6051fa7-133f-4712-86a5-e5f5bc5ab3c7
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: b91b8bf7508b7589f5ba5922cec8df576445cf27
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2018
---
# <a name="overview-of-the-mobile-device-management-mdm-lifecycle"></a>Übersicht über den MDM-Lebenszyklus (mobile Geräteverwaltung)

[!INCLUDE [both-portals](./includes/note-for-both-portals.md)]

Alle Geräte, die Sie verwalten, verfügen über einen sogenannten *Lebenszyklus*. Intune hilft Ihnen bei der Verwaltung dieses Lebenszyklus – vom Registrieren über das Konfigurieren und Schützen bis zum Abkoppeln zum Abkoppeln des Gerätes, wenn es nicht mehr benötigt wird:

![Der Gerätelebenszyklus](./media/device-lifecycle.png "Der Intune-Lebenszyklus von Geräten")

## <a name="enroll"></a>Registrieren
Die heutigen Strategien zur Verwaltung mobiler Geräte (Mobile Device Management, MDM) befassen sich mit einer Vielzahl von Mobiltelefonen, Tablets und PCs (iOS, Android, Windows und Mac OS X). Wenn Sie das Gerät verwalten müssen, was bei unternehmenseigenen Geräten im Allgemeinen der Fall ist, besteht der erste Schritt darin, die [Geräteregistrierung einzurichten](device-enrollment.md) ([klassisches Portal](/intune-classic/deploy-use/enroll-devices-in-microsoft-intune)). Durch das Registrieren bei Intune (MDM) oder durch [Installieren der Intune-Clientsoftware](/intune-classic/deploy-use/manage-windows-pcs-with-microsoft-intune) können Sie auch Windows-PCs verwalten.

## <a name="configure"></a>Konfigurieren
Das Registrieren Ihrer Geräte ist nur der erste Schritt. Um alle Intune-Angebote zu nutzen und um sicherzustellen, dass die Geräte sicher und mit Unternehmensstandards kompatibel sind, können Sie aus einer Vielzahl von Richtlinien auswählen. Mit diesen können Sie nahezu jeden Aspekt des Betriebs von verwalteten Geräten konfigurieren. Sollen Benutzer beispielsweise ein Kennwort für Geräte verwenden, die Unternehmensdaten enthalten? Sie können festlegen, dass ein Kennwort erforderlich ist. Haben Sie ein Unternehmens-WLAN? Sie können es automatisch konfigurieren. Hier sind die verfügbaren Typen von Konfigurationsoptionen aufgeführt:

- [**Gerätekonfiguration** ](device-profiles.md) ([klassisches Portal](/intune-classic/deploy-use/manage-settings-and-features-on-your-devices-with-microsoft-intune-policies)). Mit diesen Richtlinien können Sie die Features und Funktionen der von Ihnen verwalteten Geräten konfigurieren. Beispielsweise können Sie die Verwendung eines Kennworts auf Windows Phones verlangen oder die Verwendung der Kamera auf iPhones deaktivieren.
- [**Zugriff auf Unternehmensressourcen**](device-profiles.md) ([klassisches Portal](/intune-classic/deploy-use/enable-access-to-company-resources-with-microsoft-intune)) Wenn Sie Ihren Benutzern den Zugriff auf ihre Arbeit über ihre persönlichen Geräte gestatten, stellt Sie dies vor gewisse Herausforderungen. Wie gewährleisten Sie beispielsweise, dass alle Geräte, die auf Unternehmens-E-Mail zugreifen müssen, ordnungsgemäß konfiguriert sind? Wie können Sie sicherstellen, dass Benutzer über eine VPN-Verbindung auf das Unternehmensnetzwerk zugreifen können, ohne die komplexen Einstellungen kennen zu müssen? Intune kann Sie entlasten, indem die von Ihnen verwalteten Geräte automatisch für den Zugriff auf allgemeine Unternehmensressourcen konfiguriert werden.
- [**Windows-PC-Verwaltungsrichtlinien (mit der Intune-Clientsoftware)**](/intune-classic/deploy-use/common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client). Auch wenn Ihnen durch die Registrierung von Windows-PCs bei Intune die meisten Verwaltungsfunktionen für Geräte bereitgestellt werden, unterstützt Intune weiterhin das Verwalten von Windows-PCs über die Intune-Clientsoftware. Wenn Sie Informationen über einige Aufgaben benötigen, die Sie mit PCs ausführen können, beginnen Sie hier.

## <a name="protect"></a>Schützen
In der modernen IT-Welt ist der Schutz von Geräten vor unbefugtem Zugriff eine der wichtigsten Aufgaben, die Sie erfüllen müssen. Zusätzlich zu den Elementen im Schritt **Konfigurieren** des Gerätelebenszyklus stellt Intune diese Funktionen bereit, mit denen Sie von Ihnen verwaltete Geräte vor unbefugtem Zugriff oder böswilligen Angriffen schützen können:
- [**Mehrstufige Authentifizierung**](/intune-classic/deploy-use/protect-your-devices-with-microsoft-intune). Durch das Hinzufügen einer zusätzlichen Authentifizierungsebene zu den Benutzeranmeldungen können Sie Geräte noch sicherer machen. Viele Geräte unterstützen die mehrstufige Authentifizierung, die eine zweite Authentifizierungsebene wie einen Telefonanruf oder eine SMS erfordert, bevor Benutzer Zugriff erhalten.
- [**Windows Hello for Business-Einstellungen**](windows-hello.md) ([klassisches Portal](/intune-classic/deploy-use/control-microsoft-passport-settings-on-devices-with-microsoft-intune)) Windows Hello for Business ist eine alternative Anmeldemethode, die Benutzern das Verwenden einer *Geste*, z. B. Fingerabdruck oder Windows Hello, ermöglicht, um sich ohne Kennwort anzumelden.
- [**Richtlinien zum Schutz von Windows-PCs (mit der Intune-Clientsoftware)**](/intune-classic/deploy-use/policies-to-protect-windows-pcs-in-microsoft-intune). Wenn Sie Windows-PCs mit der Intune-Clientsoftware verwalten, stehen Richtlinien zur Verfügung, mit denen Sie die Einstellungen für Endpoint Protection, Softwareupdates und Windows-Firewall auf von Ihnen verwalteten PCs steuern können.

## <a name="retire"></a>Außerkraftsetzen
Wenn ein Gerät verloren geht, gestohlen wird oder ausgetauscht werden muss, oder wenn Benutzer in eine andere Position wechseln, ist es in der Regel an der Zeit, das Gerät [abzukoppeln oder zurückzusetzen](device-management.md) ([klassisches Portal](/intune-classic/deploy-use/use-remote-wipe-to-help-protect-data-using-microsoft-intune)). Hierzu gibt es verschiedene Möglichkeiten, angefangen beim Zurücksetzen des Geräts über das Entfernen des Geräts aus der Verwaltung bis hin zum Löschen der darauf befindlichen Unternehmensdaten.
