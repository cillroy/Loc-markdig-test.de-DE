---
title: Konfigurieren von iOS-Updaterichtlinien
titlesuffix: Azure portal
description: "Konfigurieren Sie die Richtlinien, damit unter iOS die automatische Installation des neuesten Softwareupdates bei überwachten iOS-Geräten durchgesetzt werden kann."
keywords: 
author: dougeby
manager: dougeby
ms.date: 08/02/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e6334421-85e1-4457-9c44-e5db8d4ee00e
ms.openlocfilehash: 199760a60ee2290560ebdf933192de0eaf569e9e
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2017
---
# <a name="configure-ios-update-policies"></a>Konfigurieren von iOS-Updaterichtlinien
Aktualisieren Sie die Richtlinien, damit Sie unter iOS die automatische Installation des neuesten Softwareupdates bei überwachten iOS-Geräten durchsetzen können. Sie haben die Möglichkeit, die Tage und Uhrzeiten zu konfigurieren, an denen Geräte keine Updates installieren sollen.

## <a name="configure-the-ios-update-policy"></a>Konfigurieren der iOS-Updaterichtlinie
1. Wechseln Sie zu dem Blatt „Intune“ im Azure-Portal.
2. Wählen Sie auf dem Blatt **Intune** die Option **Softwareupdates** > **iOS-Updaterichtlinien** aus.
4. Klicken Sie auf dem Richtlinienblatt auf **Erstellen**, und geben Sie dann einen Namen und eine Beschreibung für die Richtlinie ein.
5. Klicken Sie auf **Einstellungen** > **Konfigurieren**, und geben Sie dann an, wann die Installation der neuesten Updates auf iOS-Geräte nicht erzwungen werden soll.
6. Wählen Sie **OK** aus, um diese Konfiguration zu speichern. Damit befinden Sie sich wieder auf dem Blatt **Updaterichtlinie erstellen**. Wählen Sie **Erstellen** aus, um die Richtlinie zu erstellen und Ihre Einstellungen zu speichern.

Das Profil wird erstellt und auf dem Blatt mit der Liste der iOS-Updaterichtlinien angezeigt.

## <a name="assign-an-ios-update-policy-to-users"></a>Zuweisen einer iOS-Updaterichtlinie zu Benutzern
Um Benutzern eine iOS-Updaterichtlinie zuzuweisen, wählen Sie eine Richtlinie aus, die Sie konfiguriert haben. Vorhandene Richtlinien befinden sich auf dem Blatt **Softwareupdates** > **iOS-Updaterichtlinien**.
1. Wählen Sie die Richtlinie, die Sie Benutzern zuweisen möchten, und abschließend **Zuweisungen** aus. Das Blatt wird geöffnet, auf dem Sie Azure Active Directory-Sicherheitsgruppen auswählen und der Richtlinie zuweisen können.
2. Wählen Sie **Gruppen auswählen** aus, um das Blatt mit den Azure AD-Sicherheitsgruppen zu öffnen. Wählen Sie **Auswählen** aus, um die Richtlinie für Benutzer bereitzustellen.

Sie haben die Richtlinie auf Benutzer angewendet. Die von den Benutzern verwendeten Geräte, denen die Richtlinie zugewiesen wurde, werden auf Updatekompatibilität überprüft.

## <a name="change-the-restricted-days-for-the-policy"></a>Ändern der eingeschränkten Tage für die Richtlinie
1. Wählen Sie auf dem Blatt **Softwareupdates** die Option **iOS-Updaterichtlinien** aus.
2. Wählen Sie die iOS-Updaterichtlinie aus, die Sie aktualisieren möchten.
3. Wählen Sie **Eigenschaften** aus, und aktualisieren Sie die Informationen zu den eingeschränkten Tagen.

## <a name="monitor-ios-devices-with-older-ios-versions"></a>Überwachen von iOS-Geräten mit älteren iOS-Versionen 
<!-- 1352223 -->
Der Bericht **Out-of-date iOS Devices** (Veraltete iOS-Geräte) ist auf dem Blatt **Softwareupdates** > **iOS-Updaterichtlinien** verfügbar. Im Bericht wird Ihnen eine Liste der überwachten iOS-Geräte angezeigt, die unter eine iOS-Updaterichtlinie fallen und nicht aktualisiert werden konnten. Für jedes Gerät können Sie einen Status anzeigen, warum das Gerät nicht automatisch aktualisiert wurde.