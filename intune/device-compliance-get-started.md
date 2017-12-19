---
title: "Intune-Gerätekonformitätsrichtlinien"
titleSuffix: Azure portal
description: "In diesem Thema erhalten Sie Informationen zur Gerätekonformität in Microsoft Intune\""
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 07/18/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a916fa0d-890d-4efb-941c-7c3c05f8fe7c
ms.reviewer: muhosabe
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: aa78383233950e342c5ab0f83095bba3c8fda1f9
ms.sourcegitcommit: e10dfc9c123401fabaaf5b487d459826c1510eae
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/09/2017
---
# <a name="get-started-with-intune-device-compliance-policies"></a>Erste Schritte mit den Intune-Gerätekonformitätsrichtlinien

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

## <a name="what-is-device-compliance-in-intune"></a>Was ist die Gerätekonformität in Intune?

Intune-Gerätekonformitätsrichtlinien definieren die Regeln und Einstellungen, die ein Gerät erfüllen muss, damit es von Intune als konform eingestuft wird.

Diese Regeln umfassen Folgendes:

- Verwendung eines Kennworts für den Gerätezugriff

- Verschlüsselung

- Ermittlung, ob das Gerät mit Jailbreak oder Rooting manipuliert wurde

- Mindestens erforderliche Betriebssystemversion

- Maximal zulässige Betriebssystemversion

- Vorgabe, dass das Gerät maximal die Mobile Threat Defense-Stufe aufweisen darf

Mithilfe von Kompatibilitätsrichtlinien können Sie den Kompatibilitätsstatus auf Ihren Geräten überwachen.

### <a name="device-compliance-requirements"></a>Konformitätsanfoderungen für Geräte

Konformitätsanforderungen sind im Wesentlichen Regeln, mit denen Sie z.B. eine Geräte-PIN erzwingen oder angeben können, ob Verschlüsselung für die Konformitätsrichtlinie erforderlich ist.

<!---### Actions for noncompliance

You can specify what needs to happen when a device is determined as noncompliant. This can be a sequence of actions during a specific time.
When you specify these actions, Intune will automatically initiate them in the sequence you specify. See the following example of a sequence of
actions for a device that continues to be in the noncompliant status for
a week:

-   When the device is first determined to be non-compliant, an email with noncompliant notification is sent to the user.

-   3 days after initial noncompliance state, a follow up reminder is sent to the user.

-   5 days after initial noncompliance state, a final reminder with a notification that access to company resources will be blocked on the device in 2 days if the compliance issues are not remediated is sent to the user.

-   7 days after initial noncompliance state, access to company resources is blocked. This requires that you have conditional access policy that specifies that access from noncompliant devices should    be blocked for services such as Exchange and SharePoint.

### Grace Period

This is the time between when a device is first determined as
noncompliant to when access to company resources on that device is blocked. This time allows for time that the user has to resolve
compliance issues on the device. You can also use this time to create your action sequences to send notifications to the user before their access is blocked.

Remember that you need to implement conditional access policies in addition to compliance policies in order for access to company resources to be blocked.--->

##  <a name="pre-requisites"></a>Voraussetzungen

Sie benötigen die folgenden Abonnements, um die Gerätekonformitätsrichtlinien mit Intune zu verwenden:

- Intune EMS

- Azure AD Premium

###  <a name="supported-platforms"></a>Unterstützte Plattformen:

-   Android

-   iOS

-   macOS (Vorschau)

-   Windows 8.1

-   Windows Phone 8.1

-   Windows 10

> [!IMPORTANT]
> Geräte müssen in Intune registriert werden, um deren Konformitätsstatus melden zu können.

## <a name="how-intune-device-compliance-policies-work-with-azure-ad"></a>So funktionieren Intune-Gerätekonformitätsrichtlinien mit Azure AD

Wenn ein Gerät in Intune registriert wird, schaltet sich der Azure AD-Registrierungsprozess ein, wodurch die Geräteattribute mit weiteren Informationen in Azure AD aktualisiert werden. Eine der wichtigsten Geräteinformationen ist der Gerätekonformitätsstatus, der von bedingten Zugriffsrichtlinien zum Blockieren oder Zulassen von Zugriff auf E-Mails und andere Unternehmensressourcen verwendet wird.

- Erfahren Sie mehr über den [Azure AD-Registrierungsprozess](https://docs.microsoft.com/azure/active-directory/active-directory-device-registration-overview).

##  <a name="ways-to-use-device-compliance-policies"></a>Möglichkeiten, die Gerätekonformitätsrichtlinien zu verwalten

### <a name="with-conditional-access"></a>Mit bedingten Zugriff
Sie können die Konformitätsrichtlinie mit dem bedingten Zugriff verwenden, um den Zugriff auf E-Mails und andere Unternehmensressourcen nur für Geräte zuzulassen, die mindestens eine Regel der Gerätekonformitätsrichtlinie erfüllen.

### <a name="without-conditional-access"></a>Ohne bedingten Zugriff
Gerätekonformitätsrichtlinien können auch unabhängig vom bedingten Zugriff verwendet werden. Bei unabhängiger Nutzung von Kompatibilitätsrichtlinien werden die Zielgeräte ausgewertet und mit ihrem Kompatibilitätsstatus gemeldet. So können Sie beispielsweise einen Bericht dazu erstellen, wie viele Geräte nicht verschlüsselt sind oder mit Jailbreak oder Rootzugriff manipuliert wurden. Aber wenn Sie Kompatibilitätsrichtlinien unabhängig nutzen, gelten keine Zugriffsbeschränkungen für Unternehmensressourcen.

Sie stellen Konformitätsrichtlinien für Benutzer bereit. Wenn Sie eine Kompatibilitätsrichtlinie für einen Benutzer bereitstellen, wird die Kompatibilität der Geräte des Benutzers überprüft. Informationen darüber, wie lange es dauert, bis eine Richtlinie für mobile Geräte nach der Bereitstellung der Richtlinie abgerufen wird, finden Sie unter „Verwalten von Einstellungen und Features auf Ihren Geräten“.

##  <a name="using-device-compliance-policies-in-the-intune-classic-portal-vs-azure-portal"></a>Verwendung von Gerätekonformitätsrichtlinien im klassischen Intune-Portal vs. Azure-Portal

Beachten Sie die wichtigsten Unterschiede beim Übergang in den neuen Workflow zur Gerätekonformitätsrichtlinie im Azure-Portal.

- In Azure-Portal werden die Konformitätsrichtlinien separat für jede unterstützte Plattform erstellt.
- Im klassischen Intune-Portal wurde eine Gerätekonformitätsrichtlinie für alle unterstützten Plattformen verwendet.

<!--- -   In the Azure portal, you have the ability to specify actions and notifications that are intiated when a device is determined to be noncompliant. This ability does not exist in the Intune admin console.

-   In the Azure portal, you can set a grace period to allow time for the end-user to get their device back to compliance status before they completely lose the ability to get company data on their device. This is not available in the Intune admin console.--->

##  <a name="migrate-device-compliance-policies-from-the-intune-classic-portal-to-the-azure-portal"></a>Migrieren von Gerätekonformitätsrichtlinien vom klassischen Intune-Portal zum Azure-Portal

Gerätekonformitätsrichtlinien, die im [klassischen Intune-Portal](https://manage.microsoft.com) erstellt wurden, erscheinen nicht im neuen [Intune Azure-Portal](https://portal.azure.com). Sie sind jedoch weiterhin für Benutzer bestimmt und können über das klassische Intune-Portal verwaltet werden.

Wenn Sie von den neuen Funktionen für Gerätekonformität im Azure-Portal profitieren wollen, müssen Sie neue Gerätekonformitätsrichtlinien im Azure-Portal selbst erstellen. Wenn Sie eine neue Gerätekonformitätsrichtlinie im Azure-Portal einem Benutzer zuweisen, dem auch eine Gerätekonformitätsrichtlinie aus dem klassischen Intune-Portal zugewiesen wurde, haben die Gerätekonformitätsrichtlinien aus dem Intune-Azure-Portal Vorrang vor denen, die im klassischen Intune-Portal erstellt wurden.

##  <a name="next-steps"></a>Nächste Schritte

Plattformspezifische Informationen zum Erstellen einer Gerätekonformitätsrichtlinie finden Sie hier:

- [Android](compliance-policy-create-android.md)
- [Android for Work](compliance-policy-create-android-for-work.md)
- [iOS](compliance-policy-create-ios.md)
- [macOS](compliance-policy-create-mac-os.md)
- [Windows](compliance-policy-create-windows.md)
