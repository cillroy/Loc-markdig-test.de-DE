---
title: "Registrieren von Geräten – Geräteregistrierungs-Manager"
titlesuffix: Azure portal
description: "Verwenden Sie das Konto „Geräteregistrierungs-Manager“, um Geräte in Intune zu registrieren. \""
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 11/08/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 7196b33e-d303-4415-ad0b-2ecdb14230fd
ms.reviewer: damionw
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 90ebe47cef1fda3fb0de18cc7ae2189a06066406
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2017
---
# <a name="enroll-devices-using-device-enrollment-manager"></a>Registrieren von Geräten mithilfe des Geräteregistrierungs-Managers

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

Mit Intune können Organisationen eine Vielzahl mobiler Geräte mit einem einzelnen Benutzerkonto verwalten. Das Konto *Geräteregistrierungsmanager* (DEM) ist ein spezielles Benutzerkonto, das bis zu 1.000 Geräte registrieren kann. Fügen Sie dem DEM-Konto vorhandene Benutzer hinzu, damit diese bestimmte DEM-Funktionen erhalten. Jedes registrierte Gerät verwendet eine Einzellizenz. Es empfiehlt sich, Geräte zu verwenden, die mithilfe dieses Kontos als freigegebene Geräte registriert wurden, statt persönlicher („BYOD“) Geräte.  

Es müssen Benutzer im Azure-Portal vorhanden sein, damit sie als Geräteregistrierungs-Manager hinzugefügt werden können. Für die optimale Sicherheit darf der DEM-Benutzer nicht zusätzlich Intune-Administrator sein.

>[!NOTE]
>Die Registrierungsmethode mit dem Geräteregistrierungs-Manager (Device Enrollment Manager, DEM) kann nicht zusammen mit den folgenden anderen Registrierungsmethoden verwendet werden: [Apple Configurator mit Setup-Assistent](apple-configurator-setup-assistant-enroll-ios.md), [Apple Configurator mit direkter Registrierung](apple-configurator-direct-enroll-ios.md), [Apple School Manager (ASM)](apple-school-manager-set-up-ios.md) oder [Programm zur Geräteregistrierung (DEP)](device-enrollment-program-enroll-ios.md).

## <a name="example-of-a-device-enrollment-manager-scenario"></a>Beispiel für ein Geräteregistrierungs-Manager-Szenario:

Ein Restaurant möchte 50 Point-of-Sale-Tablets für sein Bedienpersonal bereitstellen sowie Bestellmonitore für seine Küchenmitarbeiter. Die Mitarbeiter müssen niemals auf Unternehmensdaten zugreifen und sich nie als Benutzer anmelden. Der Intune-Administrator erstellt ein Geräteregistrierungs-Manager-Konto und fügt einen Vorgesetzten des Restaurants zum DEM-Konto hinzu, dieser erhält also DEM-Fähigkeiten. Der Vorgesetzte kann nun die 50 Tablets registrieren, indem er die DEM-Anmeldeinformationen verwendet.

Nur Benutzer im Azure-Portal können Geräteregistrierungs-Manager sein. Der Geräteregistrierungs-Manager kann kein Intune-Administrator sein.

Der DEM-Benutzer kann Folgendes tun:

-   Registrieren von bis zu 1000 Geräten in Intune
-   Anmelden beim Unternehmensportal, um Unternehmens-Apps abzurufen
-   Konfigurieren des Zugriffs auf Unternehmensdaten durch Bereitstellen von rollenspezifischen Apps auf den Tablets

## <a name="limitations-of-devices-that-are-enrolled-with-a-dem-account"></a>Einschränkungen der Geräte, die mit dem DEM Konto angemeldet sind

Für Geräte, die mit einem Geräteregistrierungs-Manager-Konto registriert wurden, gelten folgende Einschränkungen:

  - Kein Zugriff auf Benutzerebene. Da Geräten kein Benutzer zugewiesen ist, hat das Gerät keinen Zugriff auf E-Mails oder Unternehmensdaten. VPN-Konfigurationen beispielsweise können noch immer dazu verwendet werden, um Geräte-Apps Zugriff auf Daten zu gestatten.
  - Kein bedingter Zugriff, da dies benutzerspezifische Szenarien voraussetzen würde.
  - Der DEM-Benutzer kann die Registrierung von DEM-Geräten auf dem Gerät mit dem Unternehmensportal nicht aufheben. Der Intune-Administrator ist dazu imstande, der DEM-Benutzer jedoch nicht.
  - Nur das lokale Gerät erscheint in der Unternehmensportal-App oder -Website.
  - Benutzer können Apps aus dem Apple Volume Purchase Program (VPP) nicht verwenden, weil für die Verwaltung dieser Apps benutzerspezifische Apple-IDs erforderlich sind.
  - (Nur iOS) Wenn Sie DEM zur Registrierung von iOS-Geräten verwenden, können Sie zum Registrieren von Geräten nicht Apple Configurator, das Apple-Programm zur Geräteregistrierung (DEP) oder Apple School Manager (ASM) verwenden.
  - (Nur Android) Die Anzahl der Android for Work-Geräte, die mit einem einzelnen DEM-Konto registriert werden können, ist eingeschränkt. Pro DEM-Konto können maximal zehn Android-Geräte mit Arbeitsprofil registriert werden. Diese Einschränkung gilt nicht für die Android-Legacy-Registrierung.
  - Jedes Gerät benötigt eine Gerätelizenz. In diesem Artikel erfahren Sie mehr über [Benutzer- und Gerätelizenzen](licenses-assign.md#how-user-and-device-licenses-affect-access-to-services).


> [!NOTE]
> Um Unternehmens-Apps auf Geräten bereitzustellen, die mit dem Geräteregistrierungs-Manager verwaltet werden, stellen Sie die Unternehmensportal-App als **erforderliche Installation** für das Benutzerkonto des Geräteregistrierungs-Managers bereit.
> Zur Verbesserung der Leistung werden beim Anzeigen der Unternehmensportal-App auf einem mit dem Geräteregistrierungs-Manager verwalteten Gerät nur das lokale Gerät angezeigt. Für die Remoteverwaltung anderer vom Geräteregistrierungs-Manager verwalteter Geräte muss die Intune-Verwaltungskonsole verwendet werden.


## <a name="add-a-device-enrollment-manager"></a>Hinzufügen eines Geräteregistrierungs-Managers

1.  Wählen Sie im Azure-Portal **Weitere Dienste** > **Überwachung und Verwaltung** > **Intune** aus.

2.  Wählen Sie auf dem Blatt „Intune“ die Option **Geräte registrieren** und dann **Geräteregistrierungs-Manager** aus.

3.  Wählen Sie **Hinzufügen** aus.

4.  Geben Sie auf dem Blatt **Benutzer hinzufügen** einen Benutzerprinzipalnamen für den Geräteregistrierungs-Manager-Benutzer ein, und wählen Sie **Hinzufügen** aus. Der Geräteregistrierungs-Manager-Benutzer wird der Liste der Geräteregistrierungs-Manager-Benutzer hinzugefügt.

## <a name="permissions-for-dem"></a>Berechtigungen für DEM

Um Aufgaben zur DEM-Registrierung durchzuführen, sind globale Azure AD-Rollen oder Azure AD-Rollen für Intune-Dienstadministratoren erforderlich. Diese Rollen sind auch erforderlich, um alle DEM-Benutzer trotz RBAC-Berechtigungen anzuzeigen und werden unter der benutzerdefinierten Benutzerrolle angezeigt. Ein Benutzer, dem keine globale Administratorrolle oder Intune-Dienstadministratorrolle zugewiesen ist, jedoch über Leseberechtigungen für die Rolle „Geräteregistrierungs-Manager“ verfügt, kann nur die von ihm erstellten DEM-Benutzer sehen. Die Unterstützung von RBAC-Rollen für diese Features werden in der Zukunft bekannt gegeben.

Wenn einem Benutzer keine globale Administratorrolle oder Intune-Dienstadministratorrolle zugewiesen ist, aber für den Leseberechtigungen für die Rolle „Geräteregistrierungs-Manager“ aktiviert sind, kann dieser nur die von ihm erstellten DEM-Benutzer sehen.

## <a name="remove-a-device-enrollment-manager"></a>Entfernen eines Geräteregistrierungs-Managers

Wenn Sie einen Geräteregistrierungs-Manager entfernen, wirkt sich dies nicht auf registrierte Geräte aus. Wenn ein Geräteregistrierungs-Manager entfernt wird:

-   Registrierte Geräte sind nicht betroffen und werden weiterhin vollständig verwaltet.
-   Die Anmeldedaten für das entfernte Geräteregistrierungs-Manager-Konto bleiben gültig.
-   Der entfernte Geräteregistrierungs-Manager kann weiterhin keine Geräte zurücksetzen oder deaktivieren.
-   Der entfernte Geräteregistrierungs-Manager kann nur eine Anzahl von Geräten mit dem Limit pro Benutzer registrieren, die vom Intune-Administrator konfiguriert wurde.

**So entfernen Sie einen Geräteregistrierungs-Manager**

1. Wählen Sie im Azure-Portal **Weitere Dienste** > **Überwachung und Verwaltung** > **Intune** aus.
2. Wählen Sie auf dem Blatt „Intune“ die Option **Geräte registrieren** und dann **Geräteregistrierungs-Manager** aus.
3. Klicken Sie auf dem Blatt **Geräteregistrierungs-Manager** mit der rechten Maustaste auf den Geräteregistrierungs-Manager-Benutzer, und wählen Sie **Entfernen** aus.

## <a name="view-the-properties-of-a-device-enrollment-manager"></a>Anzeigen der Eigenschaften des Geräteregistrierungs-Managers

1. Wählen Sie im Azure-Portal erst **Geräteregistrierung** und dann **Geräteregistrierungs-Manager** aus.
2. Klicken Sie auf dem Blatt **Geräteregistrierungs-Manager** mit der rechten Maustaste auf den Geräteregistrierungs-Manager-Benutzer, und wählen Sie **Eigenschaften** aus.
