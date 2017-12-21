---
title: Konfigurieren von Windows 10-Editionsupgrades mit Intune
titlesuffix: Azure portal
description: "In diesem Artikel erfahren Sie, wie Sie mit Intune Windows 10-Geräte, die Sie verwalten, auf eine andere Edition aktualisieren."
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 12/16/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: ae8b6528-7979-47d8-abe0-58cea1905270
ms.reviewer: coryfe
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 408cb88cabe96ad1226c4189bd1337ec95ba8d37
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2017
---
# <a name="how-to-configure-windows-10-edition-upgrades-in-microsoft-intune"></a>Konfigurieren von Windows 10-Editionsupgrades in Microsoft Intune

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

In diesem Thema erfahren Sie, wie Sie ein Profil für Windows 10 Editionsupgrades konfigurieren. Mit diesem Profil können Sie Geräte, auf denen eine der folgenden Windows 10-Versionen ausgeführt wird, automatisch auf eine andere Edition aktualisieren:

- Windows 10 Home
- Windows 10 Holographic
- Windows 10 Mobile


Die folgenden Upgradepfade werden unterstützt:

- Von Windows 10 Pro auf Windows 10 Enterprise
- Von Windows 10 Home auf Windows 10 Education
- Von Windows 10 Mobile auf Windows 10 Mobile Enterprise
- Von Windows 10 holographic oder Windows 10 Holographic for Business


## <a name="before-you-start"></a>Vorbereitung
Bevor Sie beginnen, Geräte auf die neueste Version zu aktualisieren, benötigen Sie eines der folgenden Dinge:

- Einen gültigen Product Key für die Installation der neuen Version von Windows auf allen Geräten, die das Ziel dieser Richtlinie sind (für Windows 10-Desktopeditionen) Sie können entweder Mehrfachaktivierungsschlüssel (Multiple Activation Keys, MAK) oder KMS-Schlüssel (Key Management Server) oder eine Lizenzdatei von Microsoft verwenden, die die Lizenzierungsinformationen zum Installieren der neuen Version von Windows auf allen Geräten enthält, die das Ziel dieser Richtlinie sind (für Windows 10 Mobile- und Windows 10 Holographic-Editionen).
- Die Windows 10-Geräte, für die Sie die Richtlinie zuweisen, müssen bei Microsoft Intune registriert sein. Die Editionsupgraderichtlinie kann nicht für PCs verwendet werden, auf denen die Intune-PC-Clientsoftware ausgeführt wird.

## <a name="create-a-device-profile-containing-device-restriction-settings"></a>Erstellen von Geräteprofilen mit Einstellungen für Geräteeinschränkungen

1. Melden Sie sich beim Azure-Portal an.
2. Wählen Sie **Weitere Dienste** > **Überwachung und Verwaltung** > **Intune** aus.
3. Wählen Sie auf dem Blatt **Intune** die Option **Gerätekonfiguration** aus.
2. Wählen Sie auf dem Blatt **Gerätekonfiguration** die Option **Verwalten** > **Profile** aus.
3. Wählen Sie auf dem Blatt „Profile“ die Option **Profil erstellen** aus.
4. Geben Sie auf dem Blatt **Profil erstellen** einen **Namen** und eine **Beschreibung** für das Editionsupgradeprofil ein.
5. Wählen Sie in der Dropdownliste **Plattform** die Option **Windows 10 und höher** aus.
6. Wählen Sie in der Dropdownliste **Profiltyp** die Option **Editionsupgrade** aus.
7. Auf dem Blatt **Editionsupgrade** konfigurieren Sie folgende Einstellungen:
    - **Edition, auf die ein Upgrade durchgeführt wird:** Wählen Sie in der Dropdownliste die Version von Windows 10 Desktop, Windows 10 Holographic oder Windows 10 Mobile aus, auf die die als Ziel angegebenen Geräte aktualisiert werden sollen.
    - **Product Key:** Geben Sie den Product Key an, den Sie von Microsoft erhalten haben, und der für das Upgrade aller als Ziel festgelegten Windows 10 Desktop-Geräte verwendet werden kann.<br>Nach der Erstellung einer Richtlinie, die einen Product Key enthält, können Sie den Product Key später nicht mehr bearbeiten. Grund hierfür ist, dass der Schlüssel aus Sicherheitsgründen verborgen wird. Um den Product Key zu ändern, müssen Sie den gesamten Schlüssel erneut eingeben.
    - **Lizenzdatei:** Klicken Sie auf **Durchsuchen**, um die von Microsoft erhaltene Lizenzdatei auszuwählen, die Lizenzinformationen für die Windows Holographic-Edition oder für die Windows 10 Mobile-Edition enthält, auf die das Upgrade bei den als Ziel festgelegten Geräten erfolgen soll.
8. Navigieren Sie anschließend zurück zum Blatt **Profil erstellen**, und klicken Sie auf **Erstellen**.

Das Profil wird erstellt und auf dem Blatt mit der Profilliste angezeigt.

## <a name="next-steps"></a>Nächste Schritte

Wenn Sie fortfahren und dieses Profil Gruppen zuweisen möchten, lesen Sie unter [Zuweisen von Geräteprofilen](device-profile-assign.md) nach.

>[!NOTE]
>Wenn Sie später die Richtlinienzuweisung entfernen, wird die Windows-Version auf dem Gerät nicht wiederhergestellt und wird weiterhin normal ausgeführt.

