---
title: "Hinzufügen von Benutzern und Gewähren von Berechtigungen"
description: "Synchronisieren lokaler Benutzer mit Azure AD und Gewähren von Administratorberechtigungen für Ihr Intune-Abonnement"
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 10/31/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6e9ec662-465b-4ed4-94c1-cff0fe18f126
ms.reviewer: angrobe
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 4efc8be824acc3db869529d39617f376327b3193
ms.sourcegitcommit: 94d3d86f8ae9f82a9872384bbaae53580036a4ff
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/01/2017
---
# <a name="add-users-and-give-administrative-permission-to-intune"></a>Hinzufügen von Benutzern und Gewähren von Administratorrechten für Intune

[!INCLUDE[both-portals](./includes/note-for-both-portals.md)]

In diesem Thema erfahren Administratoren, wie sie Benutzer zu Intune hinzufügen können und welche Administratorberechtigungen im Intune-Dienst verfügbar sind.

Als Administrator können Sie Benutzer direkt oder durch Synchronisieren mit Ihrem lokalen Active Directory hinzufügen. Nachdem ein Benutzer hinzugefügt wurde, kann er Geräte registrieren und auf Unternehmensressourcen zugreifen. Sie können Benutzern auch zusätzliche Berechtigungen erteilen, beispielsweise *globale Administrator*- und *Dienstadministrator*-Berechtigungen.

## <a name="add-users-to-intune"></a>Hinzufügen von Benutzern zu Intune
Sie können Benutzer manuell über das [Office 365-Portal](https://www.office.com/signin) oder das [Azure-Portal](https://portal.azure.com/#blade/Microsoft_Intune_DeviceSettings/ExtensionLandingBlade/overview) Ihrem Intune-Abonnement hinzufügen. Ein Administrator kann Benutzerkonten bearbeiten, um Intune-Lizenzen zuzuweisen. Sie können Lizenzen entweder im Office 365-Portal oder im Intune Azure-Portal zuweisen. Weitere Informationen zum Gebrauch des Office 365-Portals finden Sie unter [Hinzufügen von einzelnen Benutzern oder Massenhinzufügen von Benutzern zu Office 365 – Administratorhilfe](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec).

### <a name="add-intune-users-in-the-office-365-admin-center"></a>Hinzufügen von Intune-Benutzern im Office 365 Admin Center
1. Melden Sie sich mit einem globalen Administratorkonto oder einem Konto für Benutzerverwaltungsadministratoren im [Office 365-Portal](https://www.office.com/signin) an.
2. Wählen Sie im Office 365-Menü **Administrator** aus.
3. Wählen Sie im Admin Center **Benutzer hinzufügen** aus.

  ![Screenshot des Office 365 Admin Center](media/office-add-user.png)

4. Geben Sie die folgenden Benutzerdetails an:
  - **Vorname**
  - **Nachname**
  - **Anzeigename**
  - **Benutzername**: Universal Principle Name (UPN), der in Azure Active Directory gespeichert und für den Zugriff auf den Dienst verwendet wird
  - **Speicherort**
  - **Kontaktinformationen** (optional)
  - **Kennwort**: automatisch generiert oder angegeben

     ![Screenshot des Office 365 Admin Center](media/office-add-user-details.png)

5. Weisen Sie eine Intune-Lizenz hinzu. Wählen Sie **Produktlizenzen** aus, und wählen Sie die Produktlizenz. Es ist eine Lizenz erforderlich, die Intune enthält.
6. Wählen Sie **Hinzufügen** aus, um den neuen Benutzer zu erstellen.

### <a name="add-intune-users-in-the-azure-portal"></a>Hinzufügen von Intune-Benutzern im Azure-Portal
1. Melden Sie sich im [Azure-Portal](https://portal.azure.com) an, und navigieren Sie zu **Weitere Dienste** > **Überwachung + Verwaltung** > **Intune**. Sie können auch *Ressourcen* für **Intune** suchen.
2. Wählen Sie **Benutzer** aus.
3. Klicken Sie im Admin Center auf **Neuer Benutzer**.
  ![Screenshot des Office 365 Admin Center](media/intune-add-user.png)
4. Geben Sie die folgenden Benutzerdetails an:
  - **Name**
  - **Benutzername**: Der neue Name im Azure Active Directory-Portal ![Screenshot des Office 365 Admin Center](media/intune-add-user-info.png) Klicken Sie auf **OK**, um fortzufahren.
5. Optional können Sie die folgenden Benutzereigenschaften angeben:
  - **Profil**: Informationen zum Beruf, einschließlich **Position** und **Abteilung**
  -  **Gruppen**: Gruppen auswählen, die zum Benutzer hinzugefügt werden
  - **Verzeichnisrolle**: Weisen Sie dem Benutzer Administratorberechtigungen zu, einschließlich einer Intune-Dienstadministratorrolle.

  Wählen Sie **Erstellen** aus, um in Intune einen neuen Benutzer hinzuzufügen.
6. Wählen Sie **Profil** aus und dann einen **Verwendungsstandort** für den neuen Benutzer. Der Verwendungsstandort wird benötigt, bevor Sie dem neuen Benutzer eine Intune-Lizenz zuweisen können. Klicken Sie auf **Speichern**, um fortzufahren.
    ![Screenshot des Office 365 Admin Center](media/intune-add-user-loc.png)
7. Wählen Sie **Lizenzen** aus und dann **Zuweisen**, um diesem Benutzer eine Intune-Lizenz zuzuweisen. Eine Intune-Lizenz ist erforderlich, um Geräte zu registrieren oder auf Unternehmensressourcen zuzugreifen. Wählen Sie **Produkte** aus, dann den Lizenztyp, klicken Sie auf **Auswählen** und dann auf **Zuweisen**.

## <a name="grant-admin-permissions"></a>Gewähren von Administratorberechtigungen

Nachdem Sie Ihrem Intune-Abonnement Benutzer hinzugefügt haben, sollten Sie einigen Benutzern Administratorrechte gewähren.  Befolgen Sie diese Schritte, um Administratorberechtigungen zu gewähren:

### <a name="give-admin-permissions-in-office-365"></a>Gewähren von Administratorberechtigungen in Office 365
1. Melden Sie sich mit einem globalen Administratorkonto im [Office 365-Portal](https://www.office.com/signin) an.
2. Wählen Sie im Office 365-Menü **Administrator** aus.
3. Wählen Sie im Admin Center **Aktive Benutzer** und anschließend den Benutzer aus, dem Sie Administratorberechtigungen zuweisen möchten.
4. Wählen Sie in der Spalte **Rollen** die Option **Bearbeiten** aus.
  ![Screenshot des Bildschirms zum Zuweisen von Rollen in Office 365](./media/office-assign-roles-open.png)
5. Wählen Sie die Administratorberechtigungen aus der Liste der verfügbaren Rollen, die Sie zuweisen möchten.
![Abbildung des Office 365-Portals, das Rollen zuweist](./media/office-assign-roles.png)
6. Wählen Sie **Speichern** aus.

### <a name="give-admin-permissions-in-the-azure-portal"></a>Vergeben von Administratorberechtigungen im Azure-Portal
1. Melden Sie sich mit einem globalen Administratorkonto im [Azure-Portal](https://www.office.com/signin) an.
2. Wählen Sie im Azure-Portal **Benutzer** aus, und wählen Sie anschließend den Benutzer aus, dem Sie Administratorberechtigungen zuweisen möchten.
3. Klicken Sie auf **Verzeichnisrolle** und dann auf die Berechtigung.
  ![Screenshot](./media/add-intune-directory-role.png)
4. Wählen Sie **Speichern** aus.

### <a name="types-of-administrators"></a>Typen von Administratoren

Weisen Sie Benutzern mindestens eine Administratorberechtigung zu. Diese Berechtigungen definieren den administrativen Bereich für Benutzer sowie die Aufgaben, die sie verwalten können. Administratorberechtigungen sind den verschiedenen Microsoft-Clouddiensten gemeinsam, und einige Berechtigungen werden möglicherweise nicht von allen Diensten unterstützt. Das Azure-Portal und das Office 365-Portal führen jeweils eingeschränkte Administratorrollen auf, die von Intune nicht verwendet werden. Intune-Administratorberechtigungen enthalten folgende Optionen:

- **Globaler Administrator**: (Office 365 und Intune) Besitzt Zugriff auf alle Verwaltungsfunktionen in Intune. Standardmäßig wird die Person, die sich für Intune angemeldet hat, zum globalen Administrator. Globale Administratoren sind die einzigen Administratoren, die andere Administratorrollen zuweisen können. Sie können in Ihrer Organisation über mehrere globale Administratoren verfügen. Als bewährte Methode wird empfohlen, nur wenigen Personen in Ihrem Unternehmen diese Funktion zuzuweisen, um Risiken für Ihr Unternehmen so gering wie möglich zu halten.
- **Kennwortadministrator**: (Office 365 und Intune) Setzt Kennwörter zurück, verwaltet Serviceanfragen und überwacht den Dienststatus. Die Rechte von Kennwortadministratoren beschränken sich auf das Zurücksetzen von Kennwörtern für Benutzer.
- **Dienstadministrator**: (Office 365 und Intune) Öffnet Supportanfragen an Microsoft und überwacht das Servicedashboard und das Nachrichtencenter. Sie verfügen über „Nur-Anzeige“-Berechtigungen, können allerdings Supporttickets öffnen und lesen.
- **Rechnungsadministrator**: (Office 365 und Intune) Tätigt Erwerbe, verwaltet Abonnements, verwaltet Supporttickets und überwacht den Dienststatus.
- **Benutzerdministrator**: (Office 365 und Intune) Setzt Kennwörter zurück, überwacht den Dienststatus, kann Benutzerkonten hinzufügen oder löschen und verwaltet Serviceanfragen. Der Benutzerverwaltungsadministrator kann keine globalen Administratoren löschen, keine andere Administratorrollen erstellen und keine Kennwörter für andere Administratoren zurücksetzen.
- **Intune-Dienstadministrator**: Alle globalen Intune-Administratorberechtigungen außer die Berechtigung zum Erstellen von Administratoren mit den Optionen von **Verzeichnisrolle**.

Das Konto, mit dem Sie Ihr Microsoft Intune-Abonnement erstellen, ist ein globaler Administrator. Als Best Practice empfiehlt es sich, für die täglichen Verwaltungsaufgaben keinen globalen Administrator zu verwenden. Ein Administrator benötigt keine Intune-Lizenz für den Zugriff auf das Azure-Portal. 

Für den Zugriff auf das Office 365-Portal muss für Ihr Konto **Anmeldung zulässig** festgelegt sein. Setzen Sie im Azure-Portal unter **Profil** **Anmeldung blockieren** auf **Nein**, um den Zugriff zu gewähren. Dieser Status unterscheidet sich vom Besitz einer Abonnementlizenz. Standardmäßig haben alle Benutzerkonten den Status **Zugelassen**. Benutzer ohne Administratorrechte können Intune-Kennwörter über das Office 365-Portal zurücksetzen.

## <a name="sync-active-directory-and-add-users-to-intune"></a>Synchronisieren von Active Directory und Hinzufügen von Benutzern zu Intune
Sie können die Verzeichnissynchronisierung so konfigurieren, dass Benutzerkonten aus Ihrem lokalen Active Directory in Microsoft Azure Active Directory (Azure AD) importiert werden. Dies schließt Intune Benutzer ein. Wenn Ihr lokaler Active Directory-Dienst mit all Ihren Azure Active Directory-basierten Diensten verbunden ist, gestaltet sich die Verwaltung der Benutzeridentität viel einfacher. Sie können auch Features für die einmalige Anmeldung konfigurieren, damit die Benutzer mit der Art der Authentifizierung vertraut sind und diese problemlos verläuft. Durch das Verknüpfen eines [Azure AD-Mandanten](https://azure.microsoft.com/documentation/articles/active-directory-aadconnect/) mit mehreren Diensten sind die zuvor synchronisierten Benutzerkonten für alle cloudbasierten Dienste verfügbar.

### <a name="how-to-sync-on-premises-users-with-azure-ad"></a>Synchronisieren lokaler Benutzer mit Azure AD
Das einzige Tool, das Sie zur Synchronisierung der Benutzerkonten mit Azure AD benötigen, ist der [Azure AD Connect-Assistent](https://www.microsoft.com/download/details.aspx?id=47594). Der Azure AD Connect-Assistent stellt eine Anleitung zum Herstellen der Verbindung zwischen Ihrer lokalen Identitätsinfrastruktur und der Cloud bereit.  Wählen Sie Ihre Topologie und Bedürfnisse (einzelnen oder mehrere Verzeichnisse, Kennwortsynchronisierung oder -verbund). Der Assistent konfiguriert alle Komponenten, die für die erfolgreiche Verbindung nötig sind, und stellt sie bereit. Hierzu gehören: Synchronisierungsdienste, Active Directory-Verbunddienste (AD FS) und das Azure AD PowerShell-Modul.

> [!TIP]
> Azure AD Connect umfasst Funktionen, die zuvor als Dirsync und Azure AD Sync veröffentlicht wurden. Erfahren Sie mehr über die [Verzeichnisintegration](http://technet.microsoft.com/library/jj573653.aspx). Informationen zur Synchronisierung von Benutzerkonten aus einem lokalen Verzeichnis mit Azure AD finden Sie unter [Ähnlichkeiten zwischen Active Directory und Azure AD](http://technet.microsoft.com/library/dn518177.aspx).
