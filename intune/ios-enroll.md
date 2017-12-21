---
title: "Auswählen, wie Windows-Geräte in Intune registriert werden"
titlesuffix: Azure portal
description: "Erfahren Sie, wie Sie die Registrierung von Windows-Geräten in Microsoft Intune einrichten."
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 10/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 439c33a6-e80c-4da9-ba09-a51fc36f62ad
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 307f4b8d5ba27ce8136569e0c58711f9b1364d93
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2017
---
# <a name="enroll-ios-devices-in-intune"></a>Registrieren von iOS-Geräten in Intune

Intune ermöglicht die Verwaltung mobiler Geräte (mobile device management, MDM) wie iPads und iPhones, was Benutzern den Zugriff auf Unternehmens-E-Mails und -Apps ermöglicht.

Als Intune-Administrator können Sie die Registrierung für iOS-Geräte aktivieren. Sie können Benutzern erlauben, persönliche Geräte zu registrieren, was auch als BYOD-Registrierung („bring your own device“) bekannt ist. Sie können auch die Registrierung von unternehmenseigenen Geräten aktivieren.

## <a name="prerequisites-for-ios-enrollment"></a>Voraussetzungen für die iOS-Registrierung
Bevor Sie iOS-Geräte aktivieren können, schließen Sie die folgenden Schritte ab:
- [Einrichten von Intune:](setup-steps.md) Mit diesen Schritten wird Ihre Intune-Infrastruktur eingerichtet. Besonders für die Geräteregistrierung ist es erforderlich, dass Sie [die MDM-Autorität festlegen](mdm-authority-set.md).
- [Abrufen eines Apple-MDM-Push-Zertifikats:](apple-mdm-push-certificate-get.md) Apple benötigt ein Zertifikat, um die Verwaltung von iOS- und macOS-Geräten zu aktivieren.

## <a name="user-owned-ios-devices-byod"></a>iOS-Gerät im Besitz des Benutzers (BYOD)

Benutzer können ihre persönlichen Geräte für die Intune-Verwaltung registrieren. Dies wird als „bring your own device“ oder BYOD bezeichnet. Sobald Sie über die Voraussetzungen verfügen und den Benutzern Lizenzen zugewiesen haben, können diese die Unternehmensportal-App für iOS aus dem App Store herunterladen und den Registrierungsanweisungen in der App folgen.

## <a name="company-owned-ios-devices"></a>Unternehmenseigenes iOS-Gerät
Für Organisationen, die Geräte für Ihre Benutzer erwerben, unterstützt Intune die folgenden Methoden für die Registrierung von firmeneigenen iOS-Geräten:

- Apple-Programm zur Geräteregistrierung (DEP)
- Apple School Manager
- Registrierung über den Setup-Assistenten für Apple Configurator
- Apple Configurator – Direkte Registrierung

Sie können firmeneigene iOS-Geräte auch mit einem Konto für den [Geräteregistrierungs-Manager](device-enrollment-manager-enroll.md) registrieren.

## <a name="device-enrollment-program"></a>Geräteregistrierungsprogramm
Organisationen können iOS-Geräte über das Apple Device Enrollment Program (DEP) erwerben. Mit DEP können Sie drahtlos (Over The Air) ein Registrierungsprofil bereitstellen, das Geräte für die Verwaltung registriert. Erfahren Sie mehr über das [Programm zur Geräteregistrierung](device-enrollment-program-enroll-ios.md).

## <a name="apple-school-manager"></a>Apple School Manager
Apple School Manager ist Programm zum Kauf von Geräten und deren Registrierung für Schulen. Wie bei DEP können Sie ein Profil zum Registrieren von Geräten in der Verwaltung bereitstellen. Erfahren Sie mehr über [Apple School Manager](apple-school-manager-set-up-ios.md).

## <a name="apple-configurator"></a>Apple Configurator
Sie können iOS-Geräte mit Apple Configurator auf einem Mac-Computer registrieren. Um Geräte vorzubereiten, verbinden Sie sie über USB, und installieren Sie das Registrierungsprogramm. Sie können Geräte mit Apple Configurator auf zwei Arten registrieren:
- Registrierung per Setup-Assistent: Dieser Prozess setzt das Gerät auf die Werkseinstellungen zurück, bereitet es auf die Ausführung des Setup-Assistenten vor und installiert die Unternehmensrichtlinien für den neuen Benutzer des Geräts.
- Direkte Registrierung: Dieser Prozess setzt das Gerät nicht auf die Werkseinstellungen zurück und registriert das Gerät mit einer vordefinierten Richtlinie. Diese Methode eignet sich für Geräte ohne Benutzeraffinität.

Erfahren Sie mehr über die [Apple Configurator-Registrierung](apple-configurator-setup-assistant-enroll-ios.md).
