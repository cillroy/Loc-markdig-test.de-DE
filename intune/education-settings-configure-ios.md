---
title: "Intune-Einstellungen für die iOS-Classroom-App"
titlesuffix: Azure portal
description: "In diesem Artikel erfahren Sie etwas über die Intune-Einstellungen zur Steuerung von Einstellungen für die Classroom-App auf iOS-Geräten."
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 06/28/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 1381a5ce-c743-40e9-8a10-4c218085bb5f
ms.reviewer: derriw
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: f31ad2226052b4a681bc79e366e7d1def01c3cc4
ms.sourcegitcommit: 769db6599d5eb0e2cca537d0f60a5df9c9f05079
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2017
---
# <a name="how-to-configure-intune-settings-for-the-ios-classroom-app"></a>Gewusst wie: Konfigurieren von Intune-Einstellungen für die iOS-App „Classroom“

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

## <a name="introduction"></a>Einführung
[Classroom](https://itunes.apple.com/app/id1085319084) ist eine App, mit der Lehrkräfte Schüler/Studenten durch den Unterricht führen und deren Geräte im Schulungsraum steuern können. Mithilfe der App kann eine Lehrkraft beispielsweise folgende Aufgaben ausführen:

- Öffnen von Apps auf Geräten der Schüler/Studenten
- Sperren und Entsperren des iPad-Bildschirms
- Anzeigen des Bildschirms des iPads eines Schülers/Studenten
- Navigieren der iPads von Schüler/Studenten zu einem Lesezeichen oder Kapitel in einem Buch
- Anzeigen des Bildschirms des iPads eines Schülers/Studenten auf einem Apple TV

Nutzen Sie das Intune iOS-Geräteprofil **Bildung** und die Informationen in diesem Thema zum Einrichten der Classroom-App und der Geräte, auf denen Sie sie nutzen.

## <a name="before-you-start"></a>Vorbereitung

Berücksichtigen Sie vor dem Konfigurieren dieser Einstellungen Folgendes:

- Die iPads von Lehrkräften und Schülern/Studenten müssen bei Intune registriert werden.
- Stellen Sie sicher, dass Sie die Apple-App [Classroom](https://itunes.apple.com/us/app/classroom/id1085319084?mt=8) auf dem Gerät der Lehrkraft installiert haben. Sie können entweder die App manuell installieren oder dazu die [Intune-App-Verwaltung](app-management.md) verwenden.
- Sie müssen Zertifikate zum Authentifizieren von Verbindungen zwischen Geräten von Lehrkräften und Schülern/Studenten konfigurieren (siehe Schritt 2).
- Die iPads von Lehrkräften und Schülern/Studenten, auf denen Bluetooth aktiviert sein muss, müssen sich im gleichen WLAN befinden.
- Die Classroom-App wird auf überwachten iPads mit iOS 9.3 oder höher ausgeführt.
- In dieser Version unterstützt Intune ein 1:1-Szenario, in dem jeder Schüler/Student über ein eigenes dediziertes iPad verfügt.


## <a name="step-1---import-your-school-data-into-azure-active-directory"></a>Schritt 1: Importieren der Schul-/Unidaten in Azure Active Directory

Verwenden Sie die Synchronisierung von Schul-/Unidaten (School Data Sync, SDS) von Microsoft zum Importieren von Schul-/Unidatensätzen aus einem vorhandenen Schüler-/Studenteninformationssystem (SIS) in Azure Active Directory (Azure AD).
SDS synchronisiert Informationen aus dem SIS und speichert sie in Azure AD. Azure AD ist ein Microsoft-Verwaltungssystem, das Sie beim Organisieren von Benutzern und Geräten unterstützt. Mithilfe dieser Daten können Sie Ihre Schüler/Studenten und Kurse verwalten. [Weitere Informationen zur Bereitstellung von SDS](https://support.office.com/article/Overview-of-School-Data-Sync-and-Classroom-f3d1147b-4ade-4905-8518-508e729f2e91).

### <a name="how-to-import-data-using-sds"></a>Importieren von Daten in SDS

Sie können Informationen mithilfe einer der folgenden Methoden in SDS importieren:

- [CSV-Dateien](https://support.office.com/article/Follow-these-steps-71d5fe4a-aa51-4f35-9b53-348898a390a1): Exportieren und kompilieren Sie CSV-Dateien (durch Trennzeichen getrennte Dateien) manuell.
- [PowerSchool-API](https://support.office.com/article/Follow-these-steps-851b5edc-558f-43a9-9122-b2d63458cb8f): Ein SIS-Anbieter, der die Synchronisierung mit Azure AD vereinfacht.
- [Clever-API](https://support.office.com/article/Follow-these-steps-f3d92fde-3ad0-48f3-80a1-1ad0ac4a3fae): Eine Identitätsverwaltungslösung, die direkt mit Azure AD synchronisiert wird.
- [OneRoster](https://support.office.com/article/Follow-these-steps-f43cbb2a-b502-497d-a8b1-783dc05a57ab): Ein CSV-Format, das Sie exportieren und zur Synchronisierung mit Azure AD konvertieren können.

### <a name="find-out-more"></a>Weitere Informationen

- [Erfahren Sie mehr über die vollständige Synchronisierung lokaler Schul-/Unidaten in Azure AD](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect)
- [Erfahren Sie mehr über die Synchronisierung von Schul-/Unidaten von Microsoft](https://sds.microsoft.com/)
- [Erfahren Sie mehr über die Lizenzierung in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-whatis-azure-portal)

## <a name="step-2---create-and-assign-an-ios-education-profile-in-intune"></a>Schritt 2: Erstellen und Zuweisen eines iOS-Bildungsprofils in Intune

### <a name="configure-general-settings"></a>Konfigurieren allgemeiner Einstellungen

1. Melden Sie sich beim Azure-Portal an.
2. Wählen Sie **Weitere Dienste** > **Überwachung und Verwaltung** > **Intune** aus.
3.  Wählen Sie auf dem Blatt **Intune** die Option **Geräte konfigurieren** aus.
4.  Wählen Sie auf dem Blatt **Gerätekonfiguration** die Option **Verwalten** > **Profile** aus.
5.  Wählen Sie auf dem Blatt „Profile“ die Option **Profil erstellen** aus.
6.  Geben Sie auf dem Blatt **Profil erstellen** einen **Namen** und eine **Beschreibung** des iOS-Bildungsprofils ein.
7.  Wählen Sie in der Dropdownliste **Plattform** die Option **iOS** aus.
8.  Wählen Sie in der Dropdownliste **Profiltyp** die Option **Bildungswesen** aus.
9.  Wählen Sie **Einstellungen** > **Konfigurieren** aus.


Als Nächstes benötigen Sie Zertifikate, um eine Vertrauensstellung zwischen iPads von Lehrkräften und Schülern/Studenten herzustellen. Zertifikate werden verwendet, um Verbindungen zwischen Geräten ohne Eingabe von Benutzernamen und Kennwörtern nahtlos und automatisch zu authentifizieren.

>[!IMPORTANT]
>Die Zertifikate für Lehrkräfte und Schüler/Studenten, die Sie verwenden, müssen von unterschiedlichen Zertifizierungsstellen ausgestellt werden. Sie müssen zwei neue untergeordnete Zertifizierungsstellen erstellen, die mit Ihrer vorhandenen Zertifikatinfrastruktur verbunden sind: eine für Lehrkräfte und eine für Schüler/Studenten.

iOS-Bildungsprofile unterstützen nur PFX-Zertifikate. SCEP-Zertifikate werden nicht unterstützt.

Von Ihnen erstellte Zertifikate müssen zusätzlich zur Benutzerauthentifizierung die Serverauthentifizierung unterstützen.

### <a name="configure-teacher-certificates"></a>Konfigurieren von Zertifikaten für Lehrkräfte

Wählen Sie **Lehrerzertifikate** auf dem Blatt **Bildung** aus.

#### <a name="configure-teacher-root-certificate"></a>Konfigurieren des Stammzertifikats für Lehrkräfte

Klicken Sie unter **Stammzertifikat für Lehrer** auf die Schaltfläche „Durchsuchen“, um das Stammzertifikat für Lehrkräfte mit der Erweiterung CER (DER- oder Base64-codiert) oder P7B (mit oder ohne vollständige Kette) auszuwählen.

#### <a name="configure-teacher-pkcs12-certificate"></a>Konfigurieren von PKCS#12-Zertifikaten für Lehrkräfte

Konfigurieren Sie unter **PKCS#12-Zertifikat für Lehrer** die folgenden Werte:

- **Format des Antragstellernamens**: Intune setzt vor den allgemeinen Namen des Zertifikats automatisch das Präfix **leader** für das Lehrerzertifikat und **member** für das Schülerzertifikat.
- **Zertifizierungsstelle**: Eine Unternehmenszertifizierungsstelle (Certification Authority; CA), die auf einer Enterprise-Edition von Windows Server 2008 R2 oder höher ausgeführt wird. Eine eigenständige Zertifizierungsstelle wird nicht unterstützt. 
- **Name der Zertifizierungsstelle**: Geben Sie den Namen Ihrer Zertifizierungsstelle ein.
- **Name der Zertifikatvorlage**: Geben Sie den Namen der Zertifikatvorlage ein, die einer ausstellenden Zertifizierungsstelle hinzugefügt wurde. 
- **Erneuerungsschwellenwert (%):** Geben Sie den Prozentsatz der Zertifikatgültigkeitsdauer an, die verbleibt, bevor das Gerät eine Erneuerung des Zertifikats anfordert.
- **Gültigkeitsdauer des Zertifikats**: Geben Sie die verbleibende Gültigkeitsdauer vor Ablauf des Zertifikats an.
Sie können einen niedrigeren Wert als den für die Gültigkeitsdauer in der angegebenen Zertifikatvorlage angeben, aber keinen höheren. Beispiel: Wenn die Gültigkeitsdauer des Zertifikats in der Zertifikatvorlage zwei Jahre beträgt, können Sie als Wert ein Jahr angeben, aber nicht fünf Jahre. Zudem muss der Wert niedriger als die verbleibende Gültigkeitsdauer des Zertifikats der ausstellenden Zertifizierungsstelle sein.

Wenn Sie das Konfigurieren von Zertifikaten abgeschlossen haben, klicken Sie auf **OK**.

### <a name="configure-student-certificates"></a>Konfigurieren von Zertifikaten für Schüler/Studenten

1.  Wählen Sie **Zertifikate für Schüler und Studenten** auf dem Blatt **Bildung** aus.
2.  Wählen Sie auf dem Blatt **Zertifikate für Schüler und Studenten** in der Liste **Gerätezertifikattyp für Schüler und Studenten** die Option **1:1** aus.

#### <a name="configure-student-root-certificate"></a>Konfigurieren des Stammzertifikats für Schüler und Studenten

Klicken Sie unter **Stammzertifikat für Schüler und Studenten** auf die Schaltfläche „Durchsuchen“, um das Stammzertifikat für Schüler und Studenten mit der Erweiterung CER (DER- oder Base64-codiert) oder P7B (mit oder ohne vollständige Kette) auszuwählen.

#### <a name="configure-student-pkcs12-certificate"></a>Konfigurieren von PKCS#12-Zertifikaten für Schüler und Studenten

Konfigurieren Sie unter **PKCS#12-Zertifikat für Schüler und Studenten** die folgenden Werte:

- **Format des Antragstellernamens**: Intune setzt vor den allgemeinen Namen des Zertifikats automatisch das Präfix **leader** für das Lehrerzertifikat und **member** für das Schülerzertifikat.
- **Zertifizierungsstelle**: Eine Unternehmenszertifizierungsstelle (Certification Authority; CA), die auf einer Enterprise-Edition von Windows Server 2008 R2 oder höher ausgeführt wird. Eine eigenständige Zertifizierungsstelle wird nicht unterstützt. 
- **Name der Zertifizierungsstelle**: Geben Sie den Namen Ihrer Zertifizierungsstelle ein.
- **Name der Zertifikatvorlage**: Geben Sie den Namen der Zertifikatvorlage ein, die einer ausstellenden Zertifizierungsstelle hinzugefügt wurde. 
- **Erneuerungsschwellenwert (%):** Geben Sie den Prozentsatz der Zertifikatgültigkeitsdauer an, die verbleibt, bevor das Gerät eine Erneuerung des Zertifikats anfordert.
- **Gültigkeitsdauer des Zertifikats**: Geben Sie die verbleibende Gültigkeitsdauer vor Ablauf des Zertifikats an.
Sie können einen niedrigeren Wert als den für die Gültigkeitsdauer in der angegebenen Zertifikatvorlage angeben, aber keinen höheren. Beispiel: Wenn die Gültigkeitsdauer des Zertifikats in der Zertifikatvorlage zwei Jahre beträgt, können Sie als Wert ein Jahr angeben, aber nicht fünf Jahre. Zudem muss der Wert niedriger als die verbleibende Gültigkeitsdauer des Zertifikats der ausstellenden Zertifizierungsstelle sein.

Wenn Sie das Konfigurieren von Zertifikaten abgeschlossen haben, klicken Sie auf **OK**.

## <a name="finish-up"></a>Fertig stellen

1.  Klicken Sie auf dem Blatt **Bildung** auf „OK“.
2.  Wählen Sie auf dem Blatt **Profil erstellen** die Option **Erstellen** aus.
    
Das Profil wird erstellt und auf dem Blatt mit der Profilliste angezeigt.

Weisen Sie das Profil den Geräten der Schüler und Studenten in den Kursraumgruppen zu, die erstellt wurden, als Sie Ihre Schul-/Unidaten mit Azure AD synchronisiert haben (siehe [Zuweisen von Geräteprofilen](device-profile-assign.md)).

## <a name="next-steps"></a>Nächste Schritte

Wenn nun eine Lehrkraft die Classroom-App nutzt, hat sie die volle Kontrolle über die Geräte der Schüler bzw. Studenten.

Weitere Informationen zur Classroom-App finden Sie auf der Apple-Website unter [Classroom – Hilfe](https://help.apple.com/classroom/ipad/2.0/).

Wenn Sie freigegebene iPad-Geräte für Schüler bzw. Studenten konfigurieren möchten, finden Sie Informationen unter [How to configure Intune education settings for shared iPad devices (Konfigurieren der Intune-Einstellungen für Bildungseinrichtungen für freigegebene iPad-Geräte)](education-settings-configure-ios-shared.md).
