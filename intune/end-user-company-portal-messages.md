---
title: "Unternehmensportalmeldungen, die Benutzern möglicherweise unter Android angezeigt werden"
description: "Beschreibt Unternehmensportal-App-Meldungen, die Intune-Endbenutzern möglicherweise angezeigt werden."
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 03/09/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3df993aa-48c5-4799-b68d-c85fe4f7b02c
ms.reviewer: jeffgilb
ms.suite: ems
ms.openlocfilehash: f1a5c8a15007a38942fe543e6c1062bf957a481c
ms.sourcegitcommit: 769db6599d5eb0e2cca537d0f60a5df9c9f05079
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/15/2017
---
# <a name="help-end-users-understand-company-portal-app-messages"></a>Grundlegendes zum Verständnis von Meldungen in der Unternehmensportal-App

[!INCLUDE[both-portals](./includes/note-for-both-portals.md)]

> [!NOTE]
> Die folgenden Informationen gelten nur für Geräte mit Android 6.0 und höher.

An verschiedenen Punkten des Registrierungsprozesses sehen Benutzer zwei verschiedene Meldungen, die Anlass zur Sorge geben könnten.

- __Zulassen, dass das Unternehmensportal Telefonanrufe tätigt und verwaltet?__
- __Unternehmensportal den Zugriff auf Fotos, Medien und Dateien auf Ihrem Gerät erlauben?__

## <a name="allow-company-portal-to-make-and-manage-phone-calls"></a>Zulassen, dass das Unternehmensportal Telefonanrufe tätigt und verwaltet?

### <a name="where-it-appears"></a>Position in der Oberfläche
Die Meldung **Zulassen, dass das Unternehmensportal Telefonanrufe tätigt und verwaltet?** wird angezeigt, wenn Benutzer in der Unternehmensportal-App auf **Registrieren** tippen, während sie ihr Gerät registrieren.

### <a name="what-it-means"></a>Bedeutung
Mit Akzeptieren dieser Aufforderung lassen Benutzer zu, dass die Telefon- und IMEI-Nummern ihrer Geräte an den Intune-Dienst gesendet werden. Diese werden in der Verwaltungskonsole auf der Seite __Hardware__ angezeigt.

> [!NOTE]
> **Die Unternehmensportal-App tätigt oder verwaltet keine Telefonanrufe!** Der Meldungstext wird von Google gesteuert und kann nicht geändert werden.

Zum Anzeigen der Seite **Hardware** wechseln Sie zu **Gruppen** > **Alle mobilen Geräte** > **Geräte**. Wählen Sie das Gerät des Benutzers aus, und wechseln Sie zu **Eigenschaften anzeigen** > **Hardware**.

### <a name="what-happens-if-users-deny-access"></a>Wenn Benutzer den Zugriff nicht zulassen,
Wenn Benutzer den Zugriff verweigern, können sie weiterhin die Unternehmensportal-App verwenden und ihr Gerät registrieren. Telefonnummer und IMEI-Nummer des Geräts werden jedoch nicht in der Verwaltungskonsole auf der Seite __Hardware__ angezeigt. Wenn Benutzer den Zugriff verweigern und sich dann das nächste Mal bei der Unternehmensportal-App anmelden, wird in der Meldung ein Kontrollkästchen **Nicht mehr nachfragen** angezeigt, das die Benutzer aktivieren können, damit die Eingabeaufforderung nicht mehr angezeigt wird.

Wenn Benutzer den Zugriff zunächst erlauben, später aber verweigern, wird die Meldung wieder angezeigt, wenn sie sich nach der Registrierung das nächste Mal bei der Unternehmensportal-App anmelden.

Wenn Benutzer den Zugriff später erlauben möchten, müssen sie zu **Einstellungen** > **Apps** > **Unternehmensportal** > **Berechtigungen** > **Telefon** wechseln, um die Berechtigung zu aktivieren.

### <a name="how-to-explain-this-to-your-users"></a>So erklären Sie dies Ihren Benutzern
Verweisen Sie Ihre Benutzer an [Registrieren Ihres Android-Geräts bei Intune](/intune-user-help/enroll-your-device-in-intune-android), um weitere Informationen zu erhalten.

## <a name="allow-company-portal-to-access-your-contacts"></a>Zulassen, dass das Unternehmensportal auf Ihre Kontakte zugreift?

### <a name="where-it-appears"></a>Position in der Oberfläche
Die Meldung **Zulassen, dass das Unternehmensportal auf Ihre Kontakte zugreift?** wird angezeigt, wenn Benutzer in der Unternehmensportal-App auf **Registrieren** tippen, während sie ihr Gerät registrieren.

### <a name="what-it-means"></a>Bedeutung
Mit Akzeptieren dieser Aufforderung erlauben Benutzer Intune das Erstellen ihres Arbeitskontos und das Verwalten ihrer Azure Active Directory-Identität, die für den Benutzer auf dem betreffenden Gerät registriert ist.

> [!NOTE]
> **Microsoft greift nie auf Ihre Kontakte zu!** Der Meldungstext wird von Google gesteuert und kann nicht geändert werden.

### <a name="what-happens-if-users-deny-access"></a>Wenn Benutzer den Zugriff nicht zulassen,
Wenn Benutzer den Zugriff verweigern, werden ihre Geräte nicht bei Intune registriert und können nicht verwaltet werden. Wenn Benutzer den Zugriff verweigern und sich dann das nächste Mal bei der Unternehmensportal-App anmelden, wird in der Meldung ein Kontrollkästchen **Nicht mehr nachfragen** angezeigt, das die Benutzer aktivieren können, damit die Eingabeaufforderung nicht mehr angezeigt wird.

Wenn Benutzer den Zugriff zunächst erlauben, später aber verweigern, wird die Meldung wieder angezeigt, wenn sie sich nach der Registrierung das nächste Mal bei der Unternehmensportal-App anmelden.

Wenn Benutzer den Zugriff später erlauben möchten, müssen sie zu **Einstellungen** > **Apps** > **Unternehmensportal** > **Berechtigungen** > **Telefon** wechseln, um die Berechtigung zu aktivieren.

### <a name="how-to-explain-this-to-your-users"></a>So erklären Sie dies Ihren Benutzern
Verweisen Sie Ihre Benutzer an [Registrieren Ihres Android-Geräts bei Intune](/intune-user-help/enroll-your-device-in-intune-android), um weitere Informationen zu erhalten.

## <a name="allow-company-portal-to-access-photos-media-and-files-on-your-device"></a>Unternehmensportal den Zugriff auf Fotos, Medien und Dateien auf Ihrem Gerät erlauben?

### <a name="where-it-appears"></a>Position in der Oberfläche
Die Meldung **Unternehmensportal den Zugriff auf Fotos, Medien und Dateien auf Ihrem Gerät erlauben?** wird angezeigt, wenn Benutzer auf **Daten senden** tippen, um Datenprotokolle an den IT-Administrator zu senden.

### <a name="what-it-means"></a>Bedeutung
Mit Akzeptieren dieser Aufforderung erlauben Benutzer ihrem Gerät, Datenprotokolle auf die SD-Karte des Geräts zu schreiben und ermöglichen das Verschieben dieser Protokolle mithilfe eines USB-Kabels.   

> [!NOTE]
> **Die Unternehmensportal-App greift nicht auf Fotos, Medien und Dateien der Benutzer zu!** Der Meldungstext wird von Google gesteuert und kann nicht geändert werden.

### <a name="what-happens-if-users-deny-access"></a>Wenn Benutzer den Zugriff nicht zulassen,
Wenn Benutzer den Zugriff verweigern, können sie weiterhin Datenprotokolle per E-Mail senden, aber die Protokolle werden nicht auf die SD-Karte des Geräts kopiert.

Wenn Benutzer den Zugriff verweigern und sich dann das nächste Mal bei der Unternehmensportal-App anmelden, wird in der Meldung ein Kontrollkästchen **Nicht mehr nachfragen** angezeigt, das die Benutzer aktivieren können, damit diese Meldung nicht mehr angezeigt wird. Wenn Benutzer den Zugriff zunächst erlauben, später aber verweigern, wird die Meldung wieder angezeigt, wenn sie das nächste Mal Protokolle senden. Wenn Benutzer den Zugriff später erlauben möchten, müssen sie zu **Einstellungen** > **Apps** > **Unternehmensportal** > **Berechtigungen** > **Speicherung** wechseln, um die Berechtigung zu aktivieren.


### <a name="how-to-explain-this-to-your-users"></a>So erklären Sie dies Ihren Benutzern
Verweisen Sie Ihre Benutzer an [Senden von Protokollen an Ihren IT-Administrator per E-Mail](/intune-user-help/send-logs-to-your-it-admin-by-email-android). Sie können sie auch an [Protokolle an Ihren IT-Administrator über ein Kabel senden](/intune-user-help/send-logs-to-your-it-admin-by-cable-android) verweisen, wenn Sie möchten, dass sie die beiden Methoden vergleichen.

## <a name="your-company-support-needs-to-give-you-access-to-company-resources"></a>Der Support Ihres Unternehmens muss Ihnen Zugriff auf Unternehmensressourcen gewähren.

### <a name="where-it-appears"></a>Position in der Oberfläche
Wenn Sie die Unternehmensportal-App nicht zur Liste **Zulässige Apps** oder **Ausgenommene Apps** hinzugefügt haben, und ein Benutzer versucht, sich anzumelden, schlägt die Anmeldung fehl. Die folgende Meldung wird angezeigt:

> **Der Support Ihres Unternehmens muss Ihnen Zugriff auf Unternehmensressourcen gewähren**  
> Ihr Unternehmen verwendet Windows Information Protection-Richtlinien, um Ihr Gerät zu schützen. Der Support Ihres Unternehmens muss sicherstellen, dass die Unternehmensportal-App auf diese zugreifen kann.

### <a name="what-it-means"></a>Bedeutung

Fügen Sie dem Unternehmensportal die Liste der **zulässigen Apps** und **ausgenommenen Apps** hinzu, die in der Windows Information Protection-App-Schutzrichtlinie aufgeführt sind. Weitere Informationen finden Sie unter [Erstellen und Bereitstellen von WIP-App-Schutzrichtlinien (Windows Information Protection) in Intune](/intune-classic/deploy-use/create-windows-information-protection-policy-with-intune).

### <a name="see-also"></a>Weitere Informationen:
[Informieren der Endbenutzer über den Einsatz von Intune](end-user-educate.md)
