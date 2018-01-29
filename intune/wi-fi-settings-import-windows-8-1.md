---
title: "Importieren von WLAN-Einstellungen für Windows 8.1 und höher"
titleSuffix: Azure portal
description: Informationen zum Importieren von WLAN-Einstellungen von Windows in ein Intune-WLAN-Profil
keywords: 
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 06/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 2c4e9b19-b268-4f6d-9663-7cdbe4e4a8dd
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 1b9fd64449c94636040de1692c0fb6e30b3a551b
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2018
---
# <a name="how-to-import-wi-fi-settings-for-windows-81-and-later-devices-in-microsoft-intune"></a>Importieren von WLAN-Einstellungen für Geräte mit Windows 8.1 und höher in Microsoft Intune

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

Sie können für Windows 8.1, Windows 10 Desktop oder Windows 10 Mobile ein WLAN-Konfigurationsprofil importieren, das zuvor in eine Datei exportiert wurde.

## <a name="export-wi-fi-settings-from-a-windows-device"></a>Exportieren von WLAN-Einstellungen von einem Windows-Gerät

In Windows können Sie WLAN-Profile mit dem Hilfsprogramm **netsh wlan** in eine XML-Datei exportieren, die von Intune gelesen werden kann. Führen Sie auf einem Windows-Computer, auf dem das erforderliche WLAN-Profil bereits installiert ist, das folgende Verfahren aus.
1. Erstellen Sie einen lokalen Ordner für die exportierten WLAN-Profile, z.B. **C:\WiFi**.
1. Öffnen Sie eine Eingabeaufforderung als Administrator.
1. Führen Sie den Befehl **netsh wlan show profiles** aus, und notieren Sie den Namen des Profils, das Sie exportieren möchten. In diesem Beispiel lautet der Profilname **WiFiName**.
1. Führen Sie diesen Befehl aus: **netsh wlan export profile name="Profilname" folder=c:\Wifi**. Dadurch wird ein WLAN-Profil namens **Wi-Fi-WiFiName.xml** im Zielordner erstellt.

## <a name="import-the-wi-fi-settings-into-intune"></a>Importieren der WLAN-Einstellungen in Intune

1. Melden Sie sich beim Azure-Portal an.
2. Wählen Sie **Weitere Dienste** > **Überwachung und Verwaltung** > **Intune** aus.
3. Wählen Sie auf dem Blatt **Intune** die Option **Gerätekonfiguration** aus.
2. Wählen Sie auf dem Blatt **Gerätekonfiguration** die Option **Verwalten** > **Profile** aus.
3. Klicken Sie auf dem Blatt „Profile“ auf **Profil erstellen**.
4. Geben Sie auf dem Blatt **Profil erstellen** einen **Namen** und eine **Beschreibung** für das Geräteeinschränkungsprofil ein.
5. Wählen Sie in der Dropdownliste **Plattform** die Option **Windows 8.1 und höher** aus.
6. Wählen Sie in der Dropdownliste **Profiltyp** die Option **WLAN (Import)** aus.
7. Konfigurieren Sie auf dem Blatt **Basis-WLAN** Folgendes:
    - **Verbindungsname:** Geben Sie den Namen der WLAN-Verbindung ein. Dieser Name wird beim Durchsuchen der verfügbaren WLAN-Netzwerke für Endbenutzer angezeigt.
    - **Profil-XML:** Klicken Sie auf die Schaltfläche „Durchsuchen“, und wählen Sie die XML-Datei mit den WLAN-Profileinstellungen aus, die Sie in Intune importieren möchten.
    - **Dateiinhalt:** Zeigt den XML-Code des ausgewählte Konfigurationsprofils an.
8. Navigieren Sie anschließend zurück zum Blatt **Profil erstellen**, und klicken Sie auf **Erstellen**.

Das Profil wird erstellt und auf dem Blatt mit der Profilliste angezeigt.
