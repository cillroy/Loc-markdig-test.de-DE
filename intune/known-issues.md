---
title: Bekannte Probleme in Microsoft Intune im Azure-Portal
titlesuffix: Azure portal
description: Informationen zu bekannten Problemen in Intune
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 10/31/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f33a6645-a57e-4424-a1e9-0ce932ea83c5
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 9ad436878bcc6ed3d9e6fc4c6e7bd92ae4bf336a
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2018
---
# <a name="known-issues-in-microsoft-intune"></a>Bekannte Probleme in Microsoft Intune


[!INCLUDE [azure_portal](./includes/azure_portal.md)]

In diesem Thema erhalten Sie Informationen zu bekannten Problemen in Microsoft Intune.

Wenn Sie einen Fehler melden möchten, der hier nicht aufgeführt ist, [öffnen Sie eine Supportanfrage](get-support.md).

Wenn Sie sich ein neues Feature für Intune wünschen, können Sie auf unserer [Uservoice](https://microsoftintune.uservoice.com/forums/291681-ideas/category/189016-azure-admin-console)-Website einen Bericht erstellen.

## <a name="migration"></a>Migration

### <a name="intune-legacy-pc-client-features-are-only-available-in-the-silverlight-console"></a>Intune-Funktionen für Legacy-PC-Clients sind nur in der Silverlight-Konsole verfügbar

Die Möglichkeit zum Verwalten von Windows 10 über die Registrierung bei Windows MDM steht in Intune über das Azure-Portal zur Verfügung. Weitere Informationen finden Sie unter [Intune in der Azure-Konsole und der Legacy-Intune-PC-Client](https://docs.microsoft.com/intune-classic/deploy-use/intune-on-azure).

### <a name="groups-created-by-intune-during-migration-might-affect-functionality-of-other-microsoft-products"></a>Während der Migration von Intune erstellte Gruppen könnten die Funktionalität anderer Microsoft-Produkte beeinträchtigen.

Beim Migrieren von Intune zum Azure-Portal könnten Sie eine neue Gruppe mit dem Namen **All Users - b0b08746-4dbe-4a37-9adf-9e7652c0b421** sehen. Diese Gruppe enthält alle Benutzer in Ihrem Azure Active Directory, nicht nur Benutzer mit Intune-Lizenz. Dies könnte zu Problemen mit anderen Microsoft-Produkten führen, wenn Sie erwarten, dass einige vorhandene oder neue Benutzer nicht Mitglieder von Gruppen sind.

### <a name="secondary-migration-required-for-select-capabilities"></a>Sekundäre Migration für ausgewählte Funktionen erforderlich

Vor Januar 2017 erstellte Intune-Konten müssen migriert werden, ehe die folgenden Funktionen im Azure-Portal verwendet werden können:

- Profile für die Unternehmensgeräteregistrierung
- Apple-Programm zur Geräteregistrierung
- Firmeneigene Geräten über die iOS-Seriennummer vorab deklarieren
- Konten für den Geräteregistrierungs-Manager
- Apple Volume Purchase Program

Da diese Funktionen nicht über die Intune-Konsole (Silverlight) und das Azure-Portal verwaltet werden können, erfolgt bei der Migration Folgendes:
- Werden im klassischen Portal deaktiviert
- Werden im Azure-Portal aktiviert  

Nach dem 22. September 2017 wird die Migration dieser Funktionen in der primären Migration zu Azure zusammengeführt. Wenn Ihr Konto bereits zum Azure-Portal migriert wurde, ist es möglich, dass diese sekundäre Migration bereits abgeschlossen ist. Falls dies nicht der Fall ist, werden diese Funktionen bis November 2017 zu Azure migriert. Sobald Ihre Kontomigration eingeleitet wurde, wird sie auch am selben Tag abgeschlossen. Die Migration kann ab dem Zeitpunkt der Deaktivierung dieser Funktionen im klassischen Intune-Portal bis zu 6 Stunden in Anspruch nehmen.

Wenn Sie diese Intune-Funktionen nun im Azure-Portal verwalten, achten Sie auf die folgenden Punkte:

#### <a name="removes-default-corporate-device-enrollment-profiles-in-apple-dep"></a>Profile für die Unternehmensgeräteregistrierung im Apple-Programm zur Geräteregistrierung (DEP) wurden entfernt.
Das Azure-Portal unterstützt nicht das Standardprofil für Unternehmensgeräteregistrierungen für Geräte im Apple DEP. Diese Funktionalität, die in der Intune-Konsole (Silverlight) zur Verfügung steht, wird nicht fortgeführt, um unbeabsichtigte Zuweisungen von Profilen zu verhindern. Wenn DEP-Seriennummern im Azure-Portal synchronisiert werden, wird kein Profil zur Unternehmensgeräteregistrierung zugewiesen. Vor der Nutzung des Geräts muss ein Registrierungsprofil zugewiesen werden.

#### <a name="apple-dep-token-restored-with-migration"></a>Apple DEP-Token bei Migration wiederhergestellt

Wenn Sie ein Token für das Apple-Programm zur Geräteregistrierung im Intune-Portal (Silverlight) gelöscht haben und kein neues Token im Azure-Portal hochladen, wird das ursprüngliche Token während der Migration im Azure-Portal wiederhergestellt. Wenn Sie dieses Token entfernen und die DEP-Registrierung verhindern möchten, löschen Sie das Token aus dem Azure-Portal.

### <a name="status-blades-for-migrated-policies-do-not-work"></a>Statusblätter für migrierte Richtlinien funktionieren nicht

Sie können keine Statusinformationen für Richtlinien anzeigen, die aus dem klassischen Intune-Portal in das Azure-Portal migriert wurden. Im klassischen Portal können Sie jedoch weiterhin Berichte für diese Richtlinien anzeigen. Zum Anzeigen von Statusinformationen für migrierte Konfigurationsrichtlinien müssen Sie diese im Azure-Portal neu erstellen.

## <a name="apps"></a>Apps

### <a name="ios-volume-purchased-apps-only-available-in-default-intune-tenant-language"></a>Per Volumenlizenz erworbene Apps nur in Standardsprache des Intune-Mandanten verfügbar
Per Volumenlizenz erworbene iOS-Apps werden angezeigt und können nur für den gleichen Ländercode wie Ihr Intune-Konto zugewiesen werden. Intune synchronisiert nur Apps aus dem gleichen iTunes-Gebietsschema wie der Ländercode des Intune-Mandantenkontos. Wenn Sie beispielsweise eine App kaufen, die nur im US-Store verfügbar ist, Ihr Intune-Konto jedoch auf Deutsch ist, zeigt Intune diese App nicht an.

### <a name="multiple-copies-of-the-same-ios-volume-purchase-program-are-uploaded"></a>Es werden mehrere Kopien desselben iOS-Volumenlizenzprogramms hochgeladen.
Klicken Sie nicht mehrmals für das gleiche VPP-Token auf die Schaltfläche **Hochladen**. Dies führt dazu, dass doppelte VPP-Token hochgeladen und Apps mehrmals für das gleiche VPP-Token synchronisiert werden.

<!-- ## Groups -->

## <a name="device-configuration"></a>Gerätekonfiguration

### <a name="you-cannot-save-a-windows-information-protection-policy-for-some-devices"></a>Eine Windows Information Protection-Richtlinie kann für einige Geräte nicht gespeichert werden

Für Geräte, die nicht bei Intune registriert sind, können Sie in den Einstellungen für eine Windows Information Protection-Richtlinie im Feld **Unternehmensidentität** nur eine primäre Domäne angeben.
Wenn Sie (über **Erweiterte Einstellungen** > **Umkreisnetzwerk** > **Geschützte Domäne hinzufügen**) weitere Domänen hinzufügen, können Sie die Richtlinie nicht speichern. Die angezeigte Fehlermeldung wird in Kürze geändert, um mehr Genauigkeit zu bieten.

### <a name="cisco-anyconnect-vpn-client-support"></a>Cisco AnyConnect VPN-Client-Unterstützung

Das neueste Release des Cisco AnyConnect VPN-Clients (4.0.07072) ist derzeit nicht mit Intune kompatibel.
Ein zukünftiges Intune-Update wird die Kompatibilität mit dieser Version des VPN-Clients beinhalten. Bis dahin wird empfohlen, dass Sie Ihren Cisco AnyConnect VPN-Client nicht aktualisieren und weiterhin die vorhandene Version verwenden.

### <a name="using-the-numeric-password-type-with-macos-sierra-devices"></a>Verwenden des numerischen Kennworttyps mit macOS Sierra-Geräten

Wenn Sie derzeit in einem Geräteregistrierungsprofil für macOS Sierra-Geräte **Numerisch** **Erforderlicher Kennworttyp** auswählen, wird **Alphanumerisch** erzwungen. Wenn Sie kein numerisches Kennwort mit diesen Geräten verwenden möchten, konfigurieren Sie diese Einstellung nicht.
Dieses Problem wird ggf. in einer künftigen Version von MacOS korrigiert.

Weitere Informationen zu diesen Einstellungen finden Sie unter [Einstellungen für Geräteeinschränkungen für macOS-Geräte in Microsoft Intune](device-restrictions-macos.md).

## <a name="compliance"></a>Konformität

### <a name="compliance-policies-from-intune-do-not-show-up-in-new-console"></a>Konformitätsrichtlinien von Intune werden in der neuen Konsole nicht angezeigt

Konformitätsrichtlinien, die Sie im klassischen Intune-Portal erstellt haben, werden migriert, jedoch im Azure-Portal aufgrund von Änderungen am Design nicht angezeigt. Konformitätsrichtlinien, die Sie im klassischen Intune-Portal erstellt haben, werden noch erzwungen, jedoch müssen Sie sie im klassischen Portal anzeigen und bearbeiten.

Darüber hinaus werden neue Konformitätsrichtlinien, die Sie im Azure-Portal erstellen, im klassischen Portal nicht angezeigt.

Weitere Informationen finden Sie unter [Was ist die Gerätekonformität in Intune in Azure (Vorschau)?](device-compliance.md).

<!-- ## Enrollment -->


## <a name="data-protection"></a>Datenschutz

### <a name="ios-app-protection-policies"></a>iOS-App-Schutzrichtlinien

Sie können [App-Schutzrichtlinien für iOS](app-protection-policy-settings-ios.md) definieren, die für Benutzer auf Geräten verfügbar sind, die über die Verwaltung mobiler Geräte (MAM) ohne Registrierung verwaltet werden. Aufgrund eines temporären Fehlers können Sie diese Richtlinien nur für iOS-Versionen mit einer Version mit einem einzelnen Dezimaltrennzeichen anstatt mehreren Dezimaltrennzeichen definieren. Anstatt also eine Mindestversion von iOS 10.3.1 festzulegen, legen Sie sie für iOS 10.3. fest. Diese Problem wird mit einem zukünftigen Update für das iOS SDK gelöst.


## <a name="administration-and-accounts"></a>Verwaltung und Konten

Globale Administratoren (auch als Mandantenadministratoren bezeichnet) können weiterhin alltägliche Verwaltungsaufgaben ausführen, ohne über eine separate Intune- oder EMS-Lizenz (Enterprise Mobility Suite) zu verfügen. Wenn sie den Dienst jedoch verwenden möchten, um z. B. ihr eigenes Gerät oder ein unternehmenseigenes Gerät zu registrieren bzw. das Intune-Unternehmensportal zu verwenden, benötigen sie eine Intune- oder EMS-Lizenz.

<!-- ## Additional items -->
