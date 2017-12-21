---
title: Erstellen von benutzerdefinierten VPN-Profilen mit Microsoft Intune
titleSuffix: Azure portal
description: Verwenden Sie benutzerdefinierte Konfigurationen, um VPN-Profile in Intune zu erstellen.
keywords: 
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 06/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4c0bd439-3b58-420b-9a9a-282886986786
ms.reviewer: karanda
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: ec51848fb5145b8bf89370b78b62d8668fcb0092
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2017
---
# <a name="how-to-create-custom-vpn-profiles-in-microsoft-intune"></a>Erstellen von benutzerdefinierten VPN-Profilen in Microsoft Intune

## <a name="create-a-custom-configuration"></a>Erstellen einer benutzerdefinierten Konfiguration
Sie können benutzerdefinierte Intune-Konfigurationsrichtlinien verwenden, um VPN-Profile für folgende Geräte zu erstellen:

* Geräte unter Android 4 und höher
* Registrierte Geräte unter Windows 8.1 und höher
* Geräte unter Windows Phone 8.1 und höher
* Registrierte Geräte unter Windows 10 Desktop 
* Geräte unter Windows 10 Mobile

Dieser Richtlinientyp kann hilfreich sein, wenn die standardmäßigen Intune-VPN-Richtlinien nicht die Einstellungen enthalten, die Sie verwenden möchten.

## <a name="to-create-a-custom-configuration-policy"></a>So erstellen Sie eine benutzerdefinierte Konfigurationsrichtlinie:

1. Melden Sie sich beim Azure-Portal an.
2. Wählen Sie **Weitere Dienste** > **Überwachung und Verwaltung** > **Intune** aus.
3. Wählen Sie auf dem Blatt **Intune** die Option **Gerätekonfiguration** aus.
4. Wählen Sie auf dem Blatt **Gerätekonfiguration** die Option **Verwalten** > **Profile** aus.
5. Wählen Sie auf dem Blatt „Profile“ die Option **Profil erstellen** aus.
6. Geben Sie auf dem Blatt **Profil erstellen** einen **Namen** und eine **Beschreibung** für das VPN-Profil ein.
7. Wählen Sie in der Dropdownliste **Plattform** die Geräteplattform aus, auf die Sie VPN-Einstellungen anwenden möchten. Derzeit können Sie eine der folgenden Plattformen für die benutzerdefinierte Geräteeinstellungen auswählen:
    - **Android**
    - **iOS** (konfiguriert mit einer Datei, die Sie aus Apple Configurator exportiert haben)
    - **macOS** (konfiguriert mit einer Datei, die Sie aus Apple Configurator exportiert haben)
    - **Windows Phone 8.1**
    - **Windows 10 und höher**
6. Wählen Sie in der Dropdownliste **Profiltyp** die Option **Benutzerdefiniert** aus.
7. Wählen Sie auf dem Blatt **Benutzerdefinierte OMA-URI-Einstellungen** für jede URI-Einstellung, die Sie angeben möchten, **Hinzufügen** aus, geben Sie die geforderten Informationen ein, und wählen Sie dann **OK** aus. Beispiel:

   ![Dialogfeld „Benutzerdefinierte VPN-Profilkonfiguration“](./media/Intune_Add_VPN_URI.png)

4.  Nachdem Sie alle erforderlichen URI-Einstellungen eingegeben haben, wählen Sie **OK** und dann auf dem Blatt **Profil erstellen** die Option **Erstellen** aus.

Das Profil wird erstellt und auf dem Blatt mit der Profilliste angezeigt.
Wenn Sie fortfahren und dieses Profil Gruppen zuweisen möchten, lesen Sie unter [Zuweisen von Geräteprofilen](device-profile-assign.md) nach.




