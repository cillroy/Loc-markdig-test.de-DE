---
title: "Suchen nach verlorenen iOS-Geräten mit Intune"
titlesuffix: Azure portal
description: "In diesem Artikel erfahren Sie, wie Sie nach verlorenen oder gestohlenen iOS-Geräten mit Intune suchen."
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 08/09/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3e544286-12ad-4a3a-86f8-d2cf16940b1f
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 9d03555e91a9e759e62b829576a0d39f957ab430
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2017
---
# <a name="locate-lost-or-stolen-ios-devices-with-intune"></a>Suchen nach verlorenen oder gestohlenen iOS-Geräten mit Intune


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Mithilfe der Geräteaktion **Gerät suchen** können Sie den Standort eines verlorenen oder gestohlenen iOS-Geräts auf einer Karte anzeigen. Bei dem Gerät muss es sich um ein firmeneigenes, über DEP registriertes iOS-Gerät im überwachten Modus handeln. Diese Aktion kann erst verwendet werden, wenn das Gerät zuvor in den [Modus für verlorene Geräte](/intune-azure/manage-devices/lost-mode.md) versetzt wurde.

## <a name="supported-platforms"></a>Unterstützte Plattformen

- Windows – Nicht unterstützt
- Windows Phone 8.1 – Nicht unterstützt
- iOS – unter iOS 9.3 oder höher unterstützt (im Modus für verlorene Geräte), überwacht und unternehmenseigen
- macOS – Nicht unterstützt
- Android – Nicht unterstützt

## <a name="how-to-locate-a-lost-or-stolen-device"></a>So suchen Sie ein verloren geganenes oder gestohlenes Geräts

1. Melden Sie sich beim Azure-Portal an.
2. Wählen Sie **Weitere Dienste** > **Überwachung und Verwaltung** > **Intune** aus.
3. Wählen Sie auf dem Blatt **Intune** die Option **Geräte** aus.
4. Wählen Sie auf dem Blatt **Geräte und Gruppen** die Option **Alle Geräte** aus.
5. Wählen Sie aus der Liste der von Ihnen verwalteten Geräte ein iOS-Gerät aus, und wählen Sie dann die Remoteaktion **Gerät suchen**.
6. Wenn das Gerät gefunden wurde, wird seine Position auf dem Blatt **Gerät suchen** angezeigt.
    Blatt ![Gerät suchen](./media/locate-device.png)

>[!NOTE]
>Aus Datenschutzgründen können Sie nur begrenzt in die Karte hineinzoomen.

## <a name="security-and-privacy-information-for-the-lost-mode-and-locate-device-actions"></a>Sicherheit und Datenschutz im Zusammenhang mit dem Modus für verlorene Geräte und der Aktion „Gerät suchen“
- Vor der Aktivierung dieser Aktion werden keinerlei Informationen zum Standort des Geräts an Intune gesendet.
- Bei Verwendung der Aktion „Gerät suchen“ werden die Koordinaten des Geräts in Form von Breiten- und Längengrad an Intune gesendet und im Azure-Portal angezeigt.
- Die Daten werden 24 Stunden lang gespeichert und dann entfernt. Die Standortdaten können nicht manuell entfernt werden.
- Die Standortdaten werden sowohl im gespeicherten Zustand als auch bei der Übertragung verschlüsselt.
- Beim Konfigurieren des Modus für verlorene Geräte empfiehlt es sich, in der Nachricht für den Sperrbildschirm Informationen anzugeben, die der Person, die das Gerät findet, eine Rückgabe ermöglichen.


## <a name="next-steps"></a>Nächste Schritte

Um den Status der gerade ausgeführten Aktion anzuzeigen, wählen Sie auf dem Blatt **Geräte und Gruppen** die Option **Geräteaktionen** aus.