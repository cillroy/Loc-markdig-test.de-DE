---
title: Zuweisen von Intune-Lizenzen
description: "Zuweisen von Lizenzen zu Benutzern für Ihr Intune-Abonnement"
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 10/31/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: bb4314ea-88b5-44d3-92ce-4c6aff0587a4
ms.reviewer: amyro
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 1548d55e90fd8bdf22b3949c54bb2eeef5033a7f
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2017
---
# <a name="assign-intune-licenses-to-your-user-accounts"></a>Ihren Benutzerkonten Intune-Lizenzen zuweisen

[!INCLUDE[both-portals](./includes/note-for-both-portals.md)]

Egal, ob Sie manuell Benutzer hinzufügen oder aus Ihrem lokalen Active Directory synchronisieren, Sie müssen zunächst jedem Benutzer eine Intune-Lizenz zuweisen, bevor Benutzer ihre Geräte in Intune registrieren können.

## <a name="assign-an-intune-license-in-the-office-365-admin-center"></a>Eine Intune-Lizenz im Office 365 Admin Center zuweisen

Sie können das [Office 365-Portal](http://go.microsoft.com/fwlink/p/?LinkId=698854) verwenden, um cloudbasierte Benutzer manuell hinzuzufügen; außerdem können Sie es verwenden, um sowohl cloudbasierten Benutzerkonten als auch Konten, die aus Ihrer lokalen Active Directory-Bereitstellung mit Azure AD synchronisiert wurden, Lizenzen zuzuweisen.

1.  Melden Sie sich mit den Anmeldeinformationen Ihres Mandantenadministrators beim [Office 365-Portal](http://go.microsoft.com/fwlink/p/?LinkId=698854) an, und wählen Sie dann **Benutzer** > **Aktive Benutzer**.

2.  Wählen Sie das Benutzerkonto, dem Sie eine Intune-Benutzerlizenz zuweisen möchten, und wählen Sie dann **Produktlizenzen** > **Bearbeiten**.

3.  Schalten Sie **Intune** oder **Enterprise Mobility + Security** auf **An** um, und wählen Sie **Speichern**.

  ![Abbildung des Office 365-Portals, das Produktlizenzen zuweist](./media/office-assign-license.png)

4. Das Benutzerkonto verfügt jetzt über die erforderlichen Berechtigungen, um den Dienst zu nutzen und Geräte für die Verwaltung zu registrieren.

> [!NOTE]
> Benutzer werden erst in der Administratorkonsole angezeigt, nachdem sie ein Gerät registriert haben. Darüber hinaus können Sie eine Gruppe von Benutzern auswählen, die Sie gleichzeitig bearbeiten möchten; so können Sie für alle Benutzer entweder eine Lizenz hinzufügen oder diese ersetzen.

## <a name="use-school-data-sync-to-assign-licenses-to-users-in-intune-for-education"></a>Verwenden der Synchronisierung von Schul-/Unidaten zum Zuweisen von Lizenzen zu Benutzern in Intune for Education
Wenn Sie zu einer Bildungseinrichtung gehören, können Sie mithilfe der Synchronisierung von Schul-/Unidaten (School Data Sync, SDS) synchronisierten Benutzern Intune for Education-Lizenzen zuweisen. Aktivieren Sie dazu lediglich beim Einrichten Ihres SDS-Profils das Kontrollkästchen „Intune for Education“.  

![Abbildung der SDS-Profileinstellung](./media/i4e-sds-profile-setup-setting.png)

Wenn Sie eine Intune Education-Lizenz zuweisen, stellen Sie sicher, dass auch eine Intune A Direct-Lizenz zugewiesen wird.

![Abbildung der Einrichtung der Produktlizenz](./media/i4e-set-licenses.png)

In dieser [Übersicht über die Synchronisierung von Schul-/Unidaten](https://support.office.com/article/Overview-of-School-Data-Sync-and-Classroom-f3d1147b-4ade-4905-8518-508e729f2e91?ui=en-US&rs=en-US&ad=US) erfahren Sie mehr zu diesem Feature.

## <a name="how-user-and-device-licenses-affect-access-to-services"></a>Auswirkungen von Benutzer- und Gerätelizenzen auf den Zugriff auf Dienste
* Jeder **Benutzer**, dem Sie eine Benutzersoftwarelizenz zuweisen, kann die Onlinedienste und zugehörige Software (einschließlich System Center) zum Verwalten von Anwendungen und von bis zu 15 Geräten nutzen.
* Jedes **Gerät**, dem Sie eine Gerätesoftwarelizenz zuweisen, kann von einer beliebigen Anzahl von Benutzern für den Zugriff auf und die Nutzung der Onlinedienste und zugehörigen Software (einschließlich System Center) verwendet werden.
* Wenn ein Gerät von mehreren Benutzern verwendet wird, erfordert jedes Gerät eine Gerätesoftwarelizenz, oder alle Benutzer benötigen eine Benutzersoftwarelizenz.

## <a name="use-powershell-to-selectively-manage-ems-user-licenses"></a>Selektive Verwaltung von EMS-Benutzerlizenzen über PowerShell
Organisationen, die Microsoft Enterprise Mobility + Security (EMS, früher Enterprise Mobility Suite) verwenden, verfügen jedoch möglicherweise über Benutzer, die nur Azure Active Directory Premium- oder Intune-Dienste im EMS-Paket benötigen. Sie können einen oder mehrere Dienste mithilfe von [Azure Active Directory PowerShell-Cmdlets](https://msdn.microsoft.com/library/jj151815.aspx) zuweisen.

Um Benutzerlizenzen für EMS-Dienste selektiv zuzuweisen, öffnen Sie PowerShell als Administrator auf einem Computer, auf dem das [Azure Active Directory-Modul für Windows PowerShell](https://msdn.microsoft.com/library/jj151815.aspx#bkmk_installmodule) installiert ist. Sie können PowerShell auf einem lokalen Computer oder einem AD FS-Server installieren.

Sie müssen eine neue Lizenz-SKU-Definition erstellen, die nur für die gewünschten Servicepläne gilt. Deaktivieren Sie zu diesem Zweck die Pläne, die Sie nicht anwenden möchten. Sie können beispielsweise eine Lizenz-SKU-Definition erstellen, die keine Intune-Lizenzen zuweist. Um eine Liste der verfügbaren Dienste anzuzeigen, geben Sie Folgendes ein:.

    (Get-MsolAccountSku | Where {$_.SkuPartNumber -eq "EMS"}).ServiceStatus

Sie können den folgenden Befehl ausführen, um den Intune-Serviceplan auszuschließen. Mit der gleichen Methode können Sie die Definition auf eine vollständige Sicherheitsgruppe ausweiten oder detailliertere Filter verwenden.

**Beispiel 1**<br>
Erstellen Sie über die Befehlszeile einen neuen Benutzer, und weisen Sie eine EMS-Lizenz zu, ohne den auf Intune bezogenen Teil der Lizenz zu aktivieren:

    Connect-MsolService

    New-MsolUser -DisplayName “Test User” -FirstName FName -LastName LName -UserPrincipalName user@<TenantName>.onmicrosoft.com –Department DName -UsageLocation US

    $CustomEMS = New-MsolLicenseOptions -AccountSkuId "<TenantName>:EMS" -DisabledPlans INTUNE_A
    Set-MsolUserLicense -UserPrincipalName user@<TenantName>.onmicrosoft.com -AddLicenses <TenantName>:EMS -LicenseOptions $CustomEMS


Überprüfen Sie das Ergebnis:

    (Get-MsolUser -UserPrincipalName "user@<TenantName>.onmicrosoft.com").Licenses.ServiceStatus

**Beispiel 2**<br>
Deaktivieren Sie den auf Intune bezogenen Teil der EMS-Lizenz für einen Benutzer, dem bereits eine Lizenz zugewiesen wurde:

    Connect-MsolService

    $CustomEMS = New-MsolLicenseOptions -AccountSkuId "<TenantName>:EMS" -DisabledPlans INTUNE_A
    Set-MsolUserLicense -UserPrincipalName user@<TenantName>.onmicrosoft.com -LicenseOptions $CustomEMS

Überprüfen Sie das Ergebnis:

    (Get-MsolUser -UserPrincipalName "user@<TenantName>.onmicrosoft.com").Licenses.ServiceStatus

![PoSH-AddLic-Verify](./media/posh-addlic-verify.png)
