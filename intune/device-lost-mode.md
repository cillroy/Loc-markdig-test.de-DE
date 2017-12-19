---
title: "Aktivieren des Modus für verlorene iOS-Geräte mit Intune"
titlesuffix: Azure portal
description: "In diesem Artikel erfahren Sie, wie Sie den Modus für verlorene oder gestohlene iOS-Geräte mithilfe von Intune aktivieren."
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 08/09/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 126a7489-fe3e-43fd-a681-defb2fe0bb66
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 5f16bd212c7a23d847da0929933fbd4b497099d0
ms.sourcegitcommit: 769db6599d5eb0e2cca537d0f60a5df9c9f05079
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2017
---
# <a name="activate-lost-mode-on-ios-devices"></a>Aktivieren des Modus für verlorene Geräte auf iOS-Geräten


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Durch die Geräteaktion **Modus für verlorene Geräte** können Sie den Modus für verlorene Geräte auf verlorenen oder gestohlenen iOS-Geräten aktivieren. Dieser Modus ermöglicht die Angabe einer Nachricht und einer Telefonnummer, die auf dem Sperrbildschirm des Geräts angezeigt werden.

## <a name="supported-platforms"></a>Unterstützte Plattformen

- Windows – Nicht unterstützt
- Windows Phone – Nicht unterstützt
- iOS – Unterstützt unter iOS 9.3 oder höher, überwacht, und in Unternehmenbesitz
- macOS – Nicht unterstützt
- Android – Nicht unterstützt

## <a name="how-to-activate-lost-mode"></a>So aktivieren Sie den Modus für verlorene Geräte

1. Melden Sie sich beim Azure-Portal an.
2. Wählen Sie **Weitere Dienste** > **Überwachung und Verwaltung** > **Intune** aus.
3. Wählen Sie auf dem Blatt **Intune** die Option **Geräte** aus.
4. Wählen Sie auf dem Blatt **Geräte und Gruppen** die Option **Alle Geräte** aus.
5. Wählen Sie aus der Liste der von Ihnen verwalteten Geräte ein iOS-Gerät aus, und wählen Sie dann die Remoteaktion **Modus für verlorene Geräte**.
6. Aktivieren Sie im Blatt **Modus für verlorene Geräte** den gleichnamigen Modus. Geben Sie dann die Meldung ein, die angezeigt werden soll, und optional eine Telefonnummer.
7. Klicken Sie auf **OK**.

Wenn Sie den Modus für verlorene Geräte aktivieren, kann das Gerät nicht mehr verwendet werden. Der Benutzer kann erst wieder auf das Gerät zugreifen, wenn Sie den Modus für verlorene Geräte wieder deaktivieren. Bei aktiviertem Modus für verlorene Geräte können Sie mithilfe der Aktion **Gerät suchen** ermitteln, wo sich das Gerät befindet.
Um den Modus für verlorene Geräte nutzen zu können, muss es sich bei dem Gerät um ein firmeneigenes iOS-Gerät im überwachten Modus handeln.

## <a name="security-and-privacy-information-for-the-lost-mode-and-locate-device-actions"></a>Sicherheit und Datenschutz im Zusammenhang mit dem Modus für verlorene Geräte und der Aktion „Gerät suchen“
- Vor der Aktivierung dieser Aktion werden keinerlei Informationen zum Standort des Geräts an Intune gesendet.
- Bei Verwendung der Aktion „Gerät suchen“ werden die Koordinaten des Geräts in Form von Breiten- und Längengrad an Intune gesendet und im Azure-Portal angezeigt.
- Die Daten werden 24 Stunden lang gespeichert und dann entfernt. Die Standortdaten können nicht manuell entfernt werden.
- Die Standortdaten werden sowohl im gespeicherten Zustand als auch bei der Übertragung verschlüsselt.
- Es empfiehlt es sich, in der Nachricht für den Sperrbildschirm Informationen anzugeben, die der Person, die das Gerät findet, eine Rückgabe ermöglichen.

## <a name="next-steps"></a>Nächste Schritte

Um den Status der gerade ausgeführten Aktion anzuzeigen, wählen Sie auf dem Blatt **Geräte und Gruppen** die Option **Geräteaktionen** aus.

