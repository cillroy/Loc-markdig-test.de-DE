---
title: "Benutzerdefinierte Intune-Einstellungen für Windows 10-Geräte"
titlesuffix: Azure portal
description: "Erfahren Sie etwas über die Einstellungen, die Sie in einem benutzerdefinierten Windows 10-Profil verwenden können.\""
keywords: 
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 05/09/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 7bcea136-7260-4042-b21b-c7dab86b380d
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 5801a129eb93420797fca8f49d172f77dd955527
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2017
---
# <a name="custom-device-settings-for-windows-10-devices-in-microsoft-intune"></a>Benutzerdefinierte Geräteeinstellungen für Windows 10-Geräte in Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

 Stellen Sie mithilfe des **benutzerdefinierten** Profils von Microsoft Intune für Windows 10 und Windows 10 Mobile OMA-URI-Einstellungen (Open Mobile Alliance Uniform Resource Identifier) bereit, um Features auf Geräten zu steuern. Windows 10 stellt viele CSP-Einstellungen zur Verfügung, z. B. den [Richtlinienkonfigurationsdienst-Anbieter (Policy Configuration Service Provider; Policy CSP)](https://technet.microsoft.com/itpro/windows/manage/how-it-pros-can-use-configuration-service-providers).
Wenn Sie nach einer bestimmten Einstellung suchen, beachten Sie, dass das [Geräteeinschränkungsprofil von Windows 10](device-restrictions-windows-10.md) viele Einstellungen enthält, die in Intune integriert sind und keine Angabe benutzerdefinierter Werte erfordern.

1. Anweisungen zu den ersten Schritten finden Sie unter [Konfigurieren von benutzerdefinierten Geräteeinstellungen in Microsoft Intune](custom-settings-configure.md).
2. Wählen Sie auf dem Blatt **Profil erstellen** die Option **Einstellungen** aus, um eine oder mehrere OMA-URI-Einstellungen hinzufügen.
3. Klicken Sie auf dem Blatt **Benutzerdefinierte OMA-URI-Einstellungen** auf **Hinzufügen**, um einen neuen Wert hinzuzufügen. Sie können auch auf **Exportieren** klicken, um eine Liste aller konfigurierten Werte in einer durch Trennzeichen getrennten Wertedatei (CSV) anzuzeigen.
4. Geben Sie für jede OMA-URI-Einstellung, die Sie hinzufügen möchten, die folgenden Informationen ein. Verwenden Sie die Liste in diesem Thema, um weitere Informationen zu den Einstellungen zu erhalten, die Sie verwenden können:
    - **Einstellungsname** – Geben Sie einen eindeutigen Namen für die OMA-URI-Einstellung ein, damit Sie sie in der Liste der Einstellungen leichter identifizieren können.
    - **Beschreibung der Einstellung** – Geben Sie optional eine Beschreibung für die Einstellung ein.
    - **Datentyp** – Wählen Sie aus:
        - **Zeichenfolge**
        - **Zeichenfolge (XML)**
        - **Datum und Uhrzeit**
        - **Ganze Zahl**
        - **Gleitkomma**
        - **Boolesch**
    - **OMA-URI (Groß-/Kleinschreibung beachten)** – Geben Sie den OMA-URI an, für den Sie eine Einstellung festlegen möchten.
    - **Wert** – Geben Sie den Wert an, der mit der von Ihnen eingegebenen OMA-URI verknüpft werden soll.
5. Navigieren Sie anschließend zurück zum Blatt **Profil erstellen**, und klicken Sie auf **Erstellen**.
Das Profil wird erstellt und auf dem Blatt mit der Profilliste angezeigt.

## <a name="example"></a>Beispiel
Im folgenden Screenshot ist die Einstellung **Connectivity/AllowVPNOverCellular** aktiviert. Dadurch kann ein Windows 10-Gerät eine VPN-Verbindung über ein Mobilfunknetz öffnen.

> ![Beispiel für eine benutzerdefinierte Richtlinie mit VPN-Einstellungen](./media/custom-policy-example.png)


## <a name="how-to-find-the-policies-you-can-configure"></a>Suchen konfigurierbarer Richtlinien

Eine vollständige Liste aller Konfigurationsdienstanbieter (CSP), die von Windows 10 unterstützt werden, finden Sie in der [Konfigurationsdienstanbieter-Referenz](https://msdn.microsoft.com/windows/hardware/commercialize/customize/mdm/configuration-service-provider-reference) in der Windows-Dokumentationsbibliothek.

Nicht alle Einstellungen sind mit allen Windows 10-Versionen kompatibel. Die Tabelle im Windows-Abschnitt enthält entsprechende Informationen, welche Versionen für die einzelnen Konfigurationsdienstanbieter unterstützt werden.

Darüber hinaus unterstützt Intune nicht alle Einstellungen, die in diesem Abschnitt aufgeführt werden. Öffnen Sie den Abschnitt für die jeweilige Einstellung, um herauszufinden, ob die gewünschte Einstellung von Intune unterstützt wird. Jede Einstellungsseite zeigt ihren unterstützten Vorgang an. Damit die Einstellung mit Intune funktioniert, muss sie die Vorgänge **Hinzufügen** oder **Ersetzen** unterstützen.


