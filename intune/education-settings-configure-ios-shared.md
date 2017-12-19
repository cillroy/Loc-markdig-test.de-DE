---
title: "Intune-Einstellungen für freigegebene Geräte für die iOS-Classroom-App"
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
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 9b24ee84d339b728addd753cb309b4d8572e5582
ms.sourcegitcommit: e5501cdf08d3e79bc51dc726697606be02110e57
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/21/2017
---
# <a name="how-to-configure-intune-education-settings-for-shared-ipad-devices"></a>Konfigurieren von Intune-Einstellungen für Bildungseinrichtungen für freigegebene iPad-Geräte

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Intune unterstützt die iOS-App „Classroom“, mit der Lehrkräfte Schüler/Studenten durch den Unterricht führen und deren Geräte im Kursraum steuern können. Neben der Classroom-App unterstützt Apple, dass ein iPad-Gerät so konfiguriert werden kann, dass mehrere Schüler/Studenten es benutzen können. In diesem Artikel erfahren Sie, wie Sie dies mit Intune erreichen können.

Informationen zum Konfigurieren dedizierter (1:1) iPad-Geräte zur Verwendung der Classroom-App finden Sie unter [Vorgehensweise: Konfigurieren von Intune-Einstellungen für die iOS-App „Classroom“](education-settings-configure-ios.md).

## <a name="before-you-start"></a>Vorbereitung

Voraussetzungen zum Verwenden der freigegebenen iPad-Funktionen:

- Richten Sie [Apple School Manager](apple-school-manager-set-up-ios.md) und [School Data Sync (SDS)](https://support.office.com/article/Apple-School-Manager-integration-with-Intune-for-Education-and-School-Data-Sync-974bd1f9-2c7a-45cb-9447-b58166108617) ein.
- Konfigurieren Sie beim Einrichten von Apple School Manager [verwaltete Apple-IDs](http://help.apple.com/schoolmanager/#/tes78b477c81) für Schüler/Studenten. [Weitere Informationen zu verwalteten Apple-IDs](https://support.apple.com/en-us/HT205918).
- Erstellen Sie ein Registrierungsprofil für die Geräteseriennummern, die aus Apple School Manager synchronisiert wurden.

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
2. Wählen Sie **Weitere Dienste** > **Andere** > **Intune** aus.
3. Wählen Sie auf dem Blatt **Intune** die Option **Geräte konfigurieren** aus.
4. Wählen Sie auf dem Blatt **Gerätekonfiguration** die Option **Verwalten** > **Profile** aus.
5. Wählen Sie auf dem Blatt „Profile“ die Option **Profil erstellen** aus.
6. Geben Sie auf dem Blatt **Profil erstellen** einen **Namen** und eine **Beschreibung** des iOS-Bildungsprofils ein.
7. Wählen Sie in der Dropdownliste **Plattform** die Option **iOS** aus.
8. Wählen Sie in der Dropdownliste **Profiltyp** die Option **Bildungswesen** aus.
9. Wählen Sie **Einstellungen** > **Konfigurieren** aus.

Als Nächstes benötigen Sie Zertifikate, um eine Vertrauensstellung zwischen iPads von Lehrkräften und Schülern/Studenten herzustellen. Zertifikate werden verwendet, um Verbindungen zwischen Geräten ohne Eingabe von Benutzernamen und Kennwörtern nahtlos und automatisch zu authentifizieren.

>[!Important]
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
- **Gültigkeitsdauer des Zertifikats**: Geben Sie die verbleibende Gültigkeitsdauer vor Ablauf des Zertifikats an. Sie können einen niedrigeren Wert als den für die Gültigkeitsdauer in der angegebenen Zertifikatvorlage angeben, aber keinen höheren. Beispiel: Wenn die Gültigkeitsdauer des Zertifikats in der Zertifikatvorlage zwei Jahre beträgt, können Sie als Wert ein Jahr angeben, aber nicht fünf Jahre. Zudem muss der Wert niedriger als die verbleibende Gültigkeitsdauer des Zertifikats der ausstellenden Zertifizierungsstelle sein.

Wenn Sie das Konfigurieren von Zertifikaten für Lehrer abgeschlossen haben, klicken Sie auf **OK**.

### <a name="configure-student-certificates"></a>Konfigurieren von Zertifikaten für Schüler/Studenten

1. Wählen Sie auf dem Blatt **Bildung** die Option **Zertifikate für Schüler und Studenten** aus.
2. Wählen Sie auf dem Blatt **Zertifikate für Schüler und Studenten** in der Liste **Gerätezertifikattyp für Schüler und Studenten** die Option **Gemeinsam genutztes iPad** aus.

#### <a name="configure-student-root-certificate"></a>Konfigurieren des Stammzertifikats für Schüler und Studenten

Klicken Sie unter **Gerätestammzertifikat** auf die Schaltfläche „Durchsuchen“, um das Stammzertifikat für Schüler und Studenten mit der Erweiterung CER (DER- oder Base64-codiert) oder P7B (mit oder ohne vollständige Kette) auszuwählen.

#### <a name="configure-device-pkcs12-certificate"></a>Konfigurieren von PKCS#12-Gerätezertifikaten

Konfigurieren Sie unter **PKCS#12-Zertifikat für Schüler und Studenten** die folgenden Werte:

- **Format des Antragstellernamens**: Intune setzt vor den allgemeinen Namen des Zertifikats automatisch das Präfix „leader“ für das Lehrerzertifikat und „member“ für das Gerätezertifikat.
- **Zertifizierungsstelle**: Eine Unternehmenszertifizierungsstelle (Certification Authority; CA), die auf einer Enterprise-Edition von Windows Server 2008 R2 oder höher ausgeführt wird. Eine eigenständige Zertifizierungsstelle wird nicht unterstützt.
- **Name der Zertifizierungsstelle**: Geben Sie den Namen Ihrer Zertifizierungsstelle ein.
- **Name der Zertifikatvorlage**: Geben Sie den Namen der Zertifikatvorlage ein, die einer ausstellenden Zertifizierungsstelle hinzugefügt wurde.
- **Erneuerungsschwellenwert (%):** Geben Sie den Prozentsatz der Zertifikatgültigkeitsdauer an, die verbleibt, bevor das Gerät eine Erneuerung des Zertifikats anfordert.
- **Gültigkeitsdauer des Zertifikats**: Geben Sie die verbleibende Gültigkeitsdauer vor Ablauf des Zertifikats an. Sie können einen niedrigeren Wert als den für die Gültigkeitsdauer in der angegebenen Zertifikatvorlage angeben, aber keinen höheren. Beispiel: Wenn die Gültigkeitsdauer des Zertifikats in der Zertifikatvorlage zwei Jahre beträgt, können Sie als Wert ein Jahr angeben, aber nicht fünf Jahre. Zudem muss der Wert niedriger als die verbleibende Gültigkeitsdauer des Zertifikats der ausstellenden Zertifizierungsstelle sein.

Wenn Sie das Konfigurieren von Zertifikaten abgeschlossen haben, klicken Sie auf **OK**.

### <a name="complete-certificate-setup"></a>Abschließen des Zertifikatssetups

1. Klicken Sie auf dem Blatt **Bildung** auf **OK**.
2. Wählen Sie auf dem Blatt **Profil erstellen** die Option **Erstellen** aus.

Das Profil wird erstellt und auf dem Blatt mit der Profilliste angezeigt.

## <a name="step-3---create-a-device-category"></a>Schritt 3: Erstellen einer Gerätekategorie

1. Melden Sie sich beim Azure-Portal an.
2. Wählen Sie **Weitere Dienste** > **Andere** > **Intune** aus.
3. Wählen Sie auf dem Blatt **Intune** die Option **Geräteregistrierung** aus.
4. Wählen Sie auf dem Blatt **Enrollment – Overview** (Registrierung – Übersicht) die Option **Gerätekategorien** aus.
5. Wählen Sie auf dem Blatt **Enrollment – Device Categories** (Registrierung – Gerätekategorien) die Option **Erstellen** aus.
6. Geben Sie auf dem Blatt **Gerätekategorie erstellen** einen **Namen** und eine **Beschreibung** für die Kategorie ein.
7. Wählen Sie auf dem Blatt **Gerätekategorie erstellen** die Option **Erstellen** aus.

Die Gerätekategorie wird auf dem Blatt **Enrollment – Device Categories** (Registrierung – Gerätekategorien) erstellt.

## <a name="step-4--create-a-dynamic-group"></a>Schritt 4: Erstellen einer dynamischen Gruppe

1. Melden Sie sich beim Azure-Portal an.
2. Wählen Sie **Weitere Dienste** > **Andere** > **Intune** aus.
3. Wählen Sie auf dem Blatt **Intune** die Option **Gruppen** aus.
4. Wählen Sie auf dem Blatt **Users and Groups – All Groups** (Benutzer und Gruppen – Alle Gruppen) die Option **Neue Gruppe** aus.
5. Geben Sie auf dem Blatt **Gruppe** einen **Namen** und eine **Beschreibung** für die Gruppe ein.
6. Wählen Sie in der Dropdownliste **Mitgliedschaftstyp** die Option **Dynamisches Gerät** aus.
7. Wählen Sie **Dynamische Gerätemitglieder** aus, um Mitgliedschaftsregeln zu erstellen.
8. Gehen Sie auf dem Blatt **Dynamische Mitgliedschaftsregeln** wie folgt vor:
1. Wählen Sie in der Dropdownliste **Add devices where** (Geräte hinzufügen, bei denen) die Option **deviceCategory** aus.
2. Wählen Sie **Equals** (Gleich) aus.
3. Geben Sie die Gerätekategorie ein, die Sie im leeren Textfeld erstellt haben.
9. Wählen Sie auf dem Blatt **Dynamische Mitgliedschaftsregeln** die Option **Abfrage hinzufügen** aus.
10. Wählen Sie auf dem Blatt **Gruppe** die Option **Erstellen** aus.

Die dynamische Gruppe wird auf dem Blatt **Users and Groups – All Groups** (Benutzer und Gruppen – Alle Gruppen) erstellt.

## <a name="step-5--assign-a-device-to-a-category-carts"></a>Schritt 5: Zuweisen eines Geräts zu einer Kategorie (Carts)

1. Melden Sie sich beim Azure-Portal an.
2. Wählen Sie **Weitere Dienste** > **Andere** > **Intune** aus.
3. Wählen Sie auf dem Blatt **Intune** die Option **Geräte** aus.
4. Wählen Sie auf dem Blatt **Geräte** die Option **Alle Geräte** aus.
5. Wählen Sie auf dem Blatt **Devices – All devices** (Geräte – Alle Geräte) ein Gerät aus.
6. Wählen Sie auf dem Blatt des Geräts **Eigenschaften** aus.
7. Geben Sie auf dem Eigenschaftenblatt des Geräts in das Textfeld **Gerätekategorie** die Gerätekategorie ein.
8. Wählen Sie auf dem Geräteblatt **Speichern** aus.

Das Gerät wurde der Gerätekategorie zugeordnet. Wiederholen Sie diesen Vorgang für alle Geräte, die Sie der erstellten Gerätekategorie zuordnen möchten.

## <a name="step-6--create-classroom-profiles"></a>Schritt 6: Erstellen von Classroom-Profilen

1. Melden Sie sich beim Azure-Portal an.
2. Wählen Sie **Weitere Dienste** > **Andere** > **Intune** aus.
3. Wählen Sie auf dem Blatt **Intune** die Option **Geräte konfigurieren** aus.
4. Wählen Sie auf dem Blatt **Gerätekonfiguration** die Option **Verwalten** > **Cart-Profile** aus.
5. Wählen Sie auf dem Blatt „Profile“ die Option **Profil erstellen** aus.
6. Geben Sie auf dem Blatt **Zuordnung erstellen** einen **Namen** und eine **Beschreibung** ein.
7. Wählen Sie **Klassen auswählen** > **Konfigurieren** aus, um dem Cart-Profil Gruppen zuzuordnen.
8. Wählen Sie die Klassen aus, die im Cart-Profil enthalten sein sollen, und klicken Sie dann auf **Auswählen**. 
9. Wählen Sie **Carts auswählen** > **Konfigurieren** aus, um dem Cart-Profil Gruppen zuzuordnen.
10. Wählen Sie die Gruppen aus, die im Cart-Profil enthalten sein sollen, und klicken Sie dann auf **Auswählen**.
11. Klicken Sie auf dem Blatt **Zuordnung erstellen** auf **Speichern**, um das Cart-Profil zu speichern.

Das Profil wird erstellt und auf dem Blatt mit der Profilliste angezeigt.

## <a name="step-7---assign-the-cart-profile-to-classes"></a>Schritt 7: Zuweisen des Cart-Profils zu Klassen

1. Melden Sie sich beim Azure-Portal an.
2. Wählen Sie **Weitere Dienste** > **Andere** > **Intune** aus.
3. Wählen Sie auf dem Blatt **Intune** die Option **Geräte konfigurieren** aus.
4. Wählen Sie auf dem Blatt **Gerätekonfiguration** die Option **Überwachen** > **Zuweisungsstatus** aus.
5. Wählen Sie auf dem Blatt **Zuweisungsstatus** das erstellte **Cart-Profil** aus.
6. Wählen Sie auf dem Blatt **Cart-Profil** die Option **Zuweisungen** und unter **Einschließen** dann **Select groups to include** (Gruppen auswählen, die eingeschlossen werden sollen) aus.
7. Wählen Sie die Klassen (keine Gruppe) aus, die das Cart-Profil beinhalten soll, und klicken Sie dann auf **Auswählen**. 
8. Wählen Sie anschließend **Speichern** aus.

Die Zuweisung wird abgeschlossen, und Intune stellt das Classroom-Profil basierend auf der Classroom-Zuweisung an die Zielgeräte bereit.

## <a name="next-steps"></a>Nächste Schritte

Schüler und Studenten können nun Geräte gemeinsam nutzen und ein beliebiges iPad in einen Kursraum auswählen, sich mit einer PIN anmelden und es mit ihrem Inhalt personalisieren. Weitere Informationen zu gemeinsam genutzten iPads erhalten Sie auf der [Apple-Website](https://www.apple.com/education/it/).
