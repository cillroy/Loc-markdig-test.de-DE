---
title: "AirPlay-Einstellungen für iOS-Geräte in Intune"
titlesuffix: Azure portal
description: "Erfahren Sie, wie Sie Intune verwenden können, um iOS-Geräte automatisch mit AirPlay-kompatiblen Geräten zu verbinden."
keywords: 
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 07/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 712a79fb-14ef-4f6b-aba5-1dfca900afd2
ms.reviewer: karanda
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 89c37ac145377a3e5430d31ae54ce3418c71559a
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2018
---
# <a name="intune-airplay-settings-for-ios-devices"></a>AirPlay-Einstellungen für iOS-Geräte in Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Verwenden Sie diese Einstellungen, um von Ihnen verwaltete iOS-Geräte mit AirPlay-kompatiblen Geräten (z.B. Apple TV-Geräten) in Ihrem Netzwerk zu verbinden.
Diese Funktion ermöglicht Folgendes:

- **Konfigurieren einer Geräte- und Kennwortliste**: Damit können Benutzer automatisch eine Verbindung mit AirPlay-Geräten im Bereich herstellen. Stellen Sie ihnen den Namen und das Kennwort von AirPlay-Geräten bereit, damit sie dies nicht angeben müssen, wenn sie eine Verbindung herstellen.
- **Konfigurieren von zulässigen Zielen**: Konfigurieren Sie eine Liste mit AirPlay-Geräten (anhand der Geräte-ID). Endbenutzer können nur die von Ihnen aufgelisteten Geräte sehen und nur mit diesen Geräten eine Verbindung herstellen (nur für überwachte Geräte).

## <a name="get-started"></a>Erste Schritte

1. Wählen Sie auf dem Blatt **Gerätefunktionen** die Option **AirPlay** aus.
2. Wählen Sie auf dem Blatt **AirPlay** eine oder beide der folgenden Aktionen aus:

## <a name="configure-a-device-and-password-list"></a>Konfigurieren einer Geräte- und Kennwortliste

1. Geben Sie auf dem Blatt **Kennwörter** den **Gerätenamen** und das **Kennwort** eines AirPlay-Geräts ein, z.B. **Contoso Apple TV**.
2. Klicken Sie nach dem Eingeben der Gerätedetails auf **Hinzufügen**. Das Gerät wird in der Liste **Gerätename** angezeigt.
3. Fügen Sie nach Bedarf weitere Geräte hinzu. Wenn Sie fertig sind, wählen Sie **OK** aus.


## <a name="configure-allowed-destinations"></a>Konfigurieren von zulässigen Zielen

1. Geben Sie auf dem Blatt **Zulässige Ziele (nur überwacht)** die **Geräte-ID** eines AirPlay-Geräts ein, z.B. „52:46:CD:51:83:4C“.
2. Klicken Sie nach dem Eingeben der Geräte-ID auf **Hinzufügen**. Die ID wird in der Liste **Geräte-ID** angezeigt.
3. Fügen Sie nach Bedarf weitere Geräte hinzu. Wenn Sie fertig sind, wählen Sie **OK** aus.

Sie können Geräte, Kennwörter und zulässige Ziele auch aus einer Datei mit durch Trennzeichen getrennten Werten (CSV-Datei) importieren.


## <a name="next-steps"></a>Nächste Schritte

Sie können nun das Geräteprofil den von Ihnen ausgewählten Gruppen zuweisen. Weitere Informationen finden Sie unter [Zuweisen von Geräteprofilen](device-profile-assign.md).

