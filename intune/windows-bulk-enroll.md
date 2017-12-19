---
title: "Massenregistrierung für Windows 10"
titlesuffix: Azure portal
description: "Erstellen eines Pakets für die Massenregistrierung für Microsoft Intune"
keywords: 
author: NathBarn
ms.author: NathBarn
manager: angrobe
ms.date: 10/23/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 1f39c02a-8d8a-4911-b4e1-e8d014dbce95
ms.reviewer: damionw
ms.custom: intune-azure
ms.openlocfilehash: 7738935675595bbdd3ba1f6411a78a2646894073
ms.sourcegitcommit: ce35790090ebe768d5f75c108e8d5934fd19c8c7
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/09/2017
---
# <a name="bulk-enrollment-for-windows-devices"></a>Massenregistrierung für Windows-Geräte

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Als Administrator können Sie eine große Anzahl von neuen Windows-Geräten in Azure Active Directory und Intune einbinden. Um Geräte per Massenvorgang bei Ihrem Azure AD-Mandanten zu registrieren, erstellen Sie mit der Windows Configuration Designer-App (WCD) ein Bereitstellungspaket. Durch Anwenden des Bereitstellungspakets auf unternehmenseigene Geräte werden die Geräte in Ihrem Azure AD-Mandanten eingebunden und für die Verwaltung über Intune registriert. Sobald das Paket angewendet wurde, können sich Ihre Azure AD-Benutzer auf dem betreffenden Gerät anmelden.

Azure AD-Benutzer sind auf diesen Geräten Standardbenutzer und erhalten zugewiesene Intune-Richtlinien sowie erforderliche Apps. Die Verwendung von Self-Service-Funktionen und Unternehmensportalen wird derzeit nicht unterstützt.

## <a name="prerequisites-for-windows-devices-bulk-enrollment"></a>Voraussetzungen für die Massenregistrierung von Windows-Geräten

Für die Massenregistrierung von Windows-Geräten ist Folgendes erforderlich:

- Geräte mit Windows 10 Creators Update oder höher
- [Automatische Windows-Registrierung](windows-enroll.md#enable-windows-10-automatic-enrollment)

## <a name="create-a-provisioning-package"></a>Erstellen eines Bereitstellungspakets

1. Laden Sie [Windows Configuration Designer (WCD)](https://www.microsoft.com/store/apps/9nblggh4tx22) aus dem Microsoft Store herunter.
![Screenshot: Beschreibungen und Screenshots für die Windows Configuration Designer-App im Store](media/bulk-enroll-store.png)

2. Öffnen Sie die **Windows Configuration Designer**-App, und wählen Sie **Desktopgeräte bereitstellen** aus.
![Screenshot: Auswählen der Option zum Bereitstellen von Desktopgeräten in der Windows Configuration Designer-App](media/bulk-enroll-select.png)

3. Ein Fenster **Neues Projekt** wird geöffnet, in dem Sie Folgendes angeben:
  - **Name:** Der Name für das Projekt
  - **Projektordner:** Der Speicherort des Projekts
  - **Beschreibung:** Optionale Beschreibung des Projekts ![Screenshot: Angeben von Name, Projektordner und Beschreibung in der Windows Configuration Designer-App](media/bulk-enroll-name.png)

4.  Geben Sie einen eindeutigen Namen für Ihre Geräte ein. Die Namen können eine Seriennummer (%%SERIENNUMMER%%) oder eine zufällige Folge von Zeichen umfassen. Optional können Sie auch einen Product Key eingeben, wenn Sie die Windows-Edition aktualisieren, das Gerät für die gemeinsame Nutzung konfigurieren und vorinstallierte Software entfernen.
![Screenshot: Angeben von Name, Projektordner und Beschreibung in der Windows Configuration Designer-App](media/bulk-enroll-device.png)

5.  Optional können Sie das WLAN konfigurieren, bei dem sich Geräte beim ersten Start anmelden.  Wenn diese Option nicht konfiguriert wurde, ist beim ersten Start eines Geräts eine kabelgebundene Netzwerkverbindung erforderlich.
![Screenshot: Aktivierung eines WLANs, einschließlich Netzwerk-SSID und Netzwerktyp, in der Windows Configuration Designer-App](media/bulk-enroll-network.png)

6.  Wählen Sie **Bei Azure AD registrieren**, geben Sie ein Datum für den **Ablauf des Massentokens** ein, und wählen Sie dann **Massentoken abrufen** aus.
![Screenshot: Angeben von Name, Projektordner und Beschreibung in der Windows Configuration Designer-App](media/bulk-enroll-account.png)

7. Geben Sie Ihre Azure AD-Anmeldeinformationen an, um ein Massentoken abzurufen.
![Screenshot: Angeben von Name, Projektordner und Beschreibung in der Windows Configuration Designer-App](media/bulk-enroll-cred.png)

8.  Klicken Sie auf **Weiter**, wenn das **Massentoken** erfolgreich abgerufen wurde.

9. Optional können Sie **Anwendungen hinzufügen** und **Zertifikate hinzufügen**. Diese Anwendungen und Zertifikate werden auf dem Gerät bereitgestellt.

10. Optional können Sie Ihr Bereitstellungspaket mit einem Kennwort schützen.  Klicken Sie auf **Erstellen**.
![Screenshot: Angeben von Name, Projektordner und Beschreibung in der Windows Configuration Designer-App](media/bulk-enroll-create.png)

## <a name="provision-devices"></a>Bereitstellen von Geräten

1. Greifen Sie auf das Bereitstellungspaket zu, das sich an dem unter **Projektordner** in der App angegebenen Speicherort befindet.

2. Wählen Sie aus, wie Sie das Bereitstellungspaket auf das Gerät anwenden möchten.  Ein Bereitstellungspaket kann mit einer der folgenden Methoden auf ein Gerät angewendet werden:
 - Speichern Sie das Paket auf einem USB-Laufwerk, verbinden Sie dieses Laufwerk mit dem Gerät, das Sie per Massenvorgang registrieren möchten, und wenden Sie das Paket während des anfänglichen Setups an.
 - Speichern Sie das Paket in einem Netzwerkordner, und wenden Sie es nach dem anfänglichen Setup auf das Gerät an, das Sie per Massenvorgang registrieren möchten.

 Eine Schrittanleitung zum Anwenden eines Bereitstellungspakets finden Sie unter [Anwenden eines Bereitstellungspakets](https://technet.microsoft.com/itpro/windows/configure/provisioning-apply-package).

3. Sobald das Paket angewendet wurde, wird das Gerät nach ca. 1 Minute automatisch neu gestartet.
 ![Screenshot: Angeben von Name, Projektordner und Beschreibung in der Windows Configuration Designer-App](media/bulk-enroll-add.png)

4. Wenn das Gerät neu gestartet wird, stellt es eine Verbindung mit Azure Active Directory her und registriert sich bei Microsoft Intune.

## <a name="troubleshooting-windows-bulk-enrollment"></a>Problembehandlung bei der Massenregistrierung unter Windows

### <a name="provisioning-issues"></a>Probleme beim Bereitstellen
Diese Bereitstellung ist für die Verwendung auf neuen Windows-Geräten gedacht. Bei Bereitstellungsfehlern ist möglicherweise ein Zurücksetzen des Geräts auf die Werkseinstellungen oder eine Wiederherstellung des Geräts von einem Startimage erforderlich. Folgende Beispiele beschreiben einige mögliche Gründe für Fehler bei der Bereitstellung:

- Wenn ein Bereitstellungspaket versucht, ein Gerät in eine Active Directory-Domäne oder einen Azure Active Directory-Mandanten einzubinden, die bzw. der kein lokales Konto erstellt, ist das Gerät möglicherweise nicht erreichbar, wenn der Einbindungsprozess aufgrund einer nicht vorhandenen Netzwerkverbindung nicht durchgeführt werden kann.
- Skripts werden vom Bereitstellungspaket im Systemkontext ausgeführt und können unvorhersehbare Änderungen an Dateisystem und Konfigurationen des Geräts vornehmen. Ein schädliches oder fehlerhaftes Skript kann das Gerät in einen Zustand versetzen, aus dem eine Wiederherstellung nur durch erneutes Aufspielen eines Images oder durch Zurücksetzen des Geräts auf die Werkseinstellungen möglich ist.

### <a name="problems-with-bulk-enrollment-and-company-portal"></a>Probleme mit der Massenregistrierung und dem Unternehmensportal
Wenn ein Benutzer versucht, ein Gerät zu registrieren, dass bereits in einer Massenregistrierung mit dem Unternehmensportal registriert wurde, erhält er eine Warnmeldung, dass für sein Gerät weitere Aktionen erforderlich sind, entweder die Einrichtung oder die Registrierung. Das Gerät wird registriert, aber die Registrierung wird werden von der Unternehmensportal-App oder der -Website erkannt.

### <a name="bulk-enrollment-with-wi-fi"></a>Massenregistrierung über WLAN 

Geräte, die mit der Massenregistrierung registriert wurde, können Zertifikate, die der Benutzer als Ziel verwendet, sowie die WLAN-Bereitstellung nicht verwenden. Diese Verbindungen müssen Sie über [Zertifikate auf Geräteebene](certificates-configure.md) verwalten. 

### <a name="conditional-access"></a>Bedingter Zugriff
Der bedingte Zugriff ist für Windows-Geräte nicht verfügbar, die mit der Massenregistrierung registriert wurden.
