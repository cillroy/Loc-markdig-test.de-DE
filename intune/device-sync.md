---
title: "Synchronisieren von Geräten mit Intune"
titlesuffix: Azure portal
description: "Erfahren Sie, wie Sie Geräte mit Intune synchronisieren, um die neuesten Richtlinien und Aktionen zu erhalten."
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 08/09/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 02ad249e-f098-421f-861f-6b2ff733ac7c
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: dadcd33f39827365fc3f22c46d4332f3ea3cbf09
ms.sourcegitcommit: a1c751959c9b3d5678bd9d67007e762df30eab59
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/23/2017
---
# <a name="sync-devices-with-intune-to-get-the-latest-policies-and-actions"></a>Synchronisieren von Geräten mit Intune, um die neuesten Richtlinien und Aktionen zu erhalten


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Die Geräteaktion **Sync** (Synchronsieren) zwingt das ausgewählte Gerät dazu, sofort bei Intune einzuchecken. Checkt ein Gerät ein, empfängt es sofort alle ihm zugewiesenen ausstehenden Aktionen oder Richtlinien.  Dadurch können Sie sofort zugewiesene Richtlinien überprüfen und Probleme beheben, ohne den nächsten geplanten Check-In abwarten zu müssen.

## <a name="supported-platforms"></a>Unterstützte Plattformen

- Windows
- Windows Phone
- iOS
- macOS
- Android

## <a name="how-to-sync-a-device"></a>So synchronisieren Sie ein Gerät

1. Melden Sie sich beim Azure-Portal an.
2. Wählen Sie **Weitere Dienste** > **Überwachung und Verwaltung** > **Intune** aus.
3. Wählen Sie auf dem Blatt **Intune** die Option **Geräte** aus.
4. Wählen Sie auf dem Blatt **Geräte und Gruppen** die Option **Alle Geräte** aus.
5. Wählen Sie aus der Liste der verwalteten Geräte ein Gerät aus, und wählen Sie dann die Remotegeräteaktion **Sync** aus.
7. Wählen Sie zum Bestätigen der Aktion **Ja** aus.


## <a name="retriable-error-codes"></a>Wiederholbare Fehlercodes

Wenn ein Administrator die Geräteaktion **Sync** ausführt, sind iOS- und Android-Apps, die zwar fehlgeschlagen sind, aber einen wiederholbaren Fehlercode ausgelöst haben, auf dem Gerät verfügbar. Allerdings dauert es sieben Tage, bis Apps, die einen nicht wiederholbaren Fehlercode ausgelöst haben, auf dem Gerät verfügbar gemacht werden können.


| Fehlercode  | Vorgeschlagene Beschreibung                                                                                                                  | Wiederholbar |
|-------------|----------------------------------------------------------------------------------------------------------------------------------------|-----------|
| 2016330898 | Unbekannter Fehler aufgetreten.                                                                                                             | Nein        |
| 2016330897 | Ihre Verbindung zu Intune wurde aufgrund einer Zeitüberschreitung abgebrochen. Setzen Sie Ihre Verbindung zurück.                                                                             | Ja       |
| 2016330896 | Ihre Internetverbindung wurde getrennt. Setzen Sie Ihre Verbindung zurück.                                                                            | Ja       |
| 2016330895 | Ihre Internetverbindung wurde getrennt. Setzen Sie Ihre Verbindung zurück.                                                                            | Ja       |
| 2016330894 | Ihre Internetverbindung wurde getrennt. Setzen Sie Ihre Verbindung zurück.                                                                            | Ja       |
| 2016330893 | Ihre Internetverbindung wurde getrennt. Setzen Sie Ihre Verbindung zurück.                                                                            | Ja       |
| 2016330892 | Internationales Roaming ist deaktiviert.                                                                                                     | Nein        |
| 2016330891 | Während eines Anrufs kann für dieses Gerät nicht auf die Mobilfunkverbindung zugegriffen werden. Warten Sie, bis der Anruf beendet wird. | Ja       |
| 2016330890 | Das Mobilfunknetz für dieses Gerät: Diese Geräte konnten zu diesem Zeitpunkt nicht verwendet werden.                                                   | Nein        |
| 2016330889 | Fehler bei der sicheren Verbindung: Setzen Sie Ihre Verbindung zurück.                                                                                   | Ja       |
| 2016330888 | Fehler bei der Auswertung der Serververtrauensstellung                                                                                                | Nein        |

## <a name="next-steps"></a>Nächste Schritte

Wählen Sie **Geräteaktionen** aus, um den Status der Synchronisierung anzuzeigen. 
