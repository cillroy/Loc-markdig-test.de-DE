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
# <a name="assign-intune-licenses-to-your-user-accounts"></a><span data-ttu-id="31e82-103">Ihren Benutzerkonten Intune-Lizenzen zuweisen</span><span class="sxs-lookup"><span data-stu-id="31e82-103">Assign Intune licenses to your user accounts</span></span>

[!INCLUDE[both-portals](./includes/note-for-both-portals.md)]

<span data-ttu-id="31e82-104">Egal, ob Sie manuell Benutzer hinzufügen oder aus Ihrem lokalen Active Directory synchronisieren, Sie müssen zunächst jedem Benutzer eine Intune-Lizenz zuweisen, bevor Benutzer ihre Geräte in Intune registrieren können.</span><span class="sxs-lookup"><span data-stu-id="31e82-104">Whether you manually add users or synchronize from your on-premises Active Directory, you must first assign each user an Intune license before users can enroll their devices in Intune.</span></span>

## <a name="assign-an-intune-license-in-the-office-365-admin-center"></a><span data-ttu-id="31e82-105">Eine Intune-Lizenz im Office 365 Admin Center zuweisen</span><span class="sxs-lookup"><span data-stu-id="31e82-105">Assign an Intune license in the Office 365 Admin center</span></span>

<span data-ttu-id="31e82-106">Sie können das [Office 365-Portal](http://go.microsoft.com/fwlink/p/?LinkId=698854) verwenden, um cloudbasierte Benutzer manuell hinzuzufügen; außerdem können Sie es verwenden, um sowohl cloudbasierten Benutzerkonten als auch Konten, die aus Ihrer lokalen Active Directory-Bereitstellung mit Azure AD synchronisiert wurden, Lizenzen zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="31e82-106">You can use the [Office 365 portal](http://go.microsoft.com/fwlink/p/?LinkId=698854) to manually add cloud-based users and assign licenses to both cloud-based user accounts and accounts synchronized from your on-premises Active Directory to Azure AD.</span></span>

1.  <span data-ttu-id="31e82-107">Melden Sie sich mit den Anmeldeinformationen Ihres Mandantenadministrators beim [Office 365-Portal](http://go.microsoft.com/fwlink/p/?LinkId=698854) an, und wählen Sie dann **Benutzer** > **Aktive Benutzer**.</span><span class="sxs-lookup"><span data-stu-id="31e82-107">Sign in to the [Office 365 portal](http://go.microsoft.com/fwlink/p/?LinkId=698854) using your tenant administrator credentials, and then choose **Users** > **Active Users**.</span></span>

2.  <span data-ttu-id="31e82-108">Wählen Sie das Benutzerkonto, dem Sie eine Intune-Benutzerlizenz zuweisen möchten, und wählen Sie dann **Produktlizenzen** > **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="31e82-108">Select the user account that you want to assign an Intune user license to, and then choose **Product licenses** > **Edit**.</span></span>

3.  <span data-ttu-id="31e82-109">Schalten Sie **Intune** oder **Enterprise Mobility + Security** auf **An** um, und wählen Sie **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="31e82-109">Toggle **Intune** or **Enterprise Mobility + Security** to **On**, and choose **Save**.</span></span>

  ![Abbildung des Office 365-Portals, das Produktlizenzen zuweist](./media/office-assign-license.png)

4. <span data-ttu-id="31e82-111">Das Benutzerkonto verfügt jetzt über die erforderlichen Berechtigungen, um den Dienst zu nutzen und Geräte für die Verwaltung zu registrieren.</span><span class="sxs-lookup"><span data-stu-id="31e82-111">The user account now has the permissions needed to use the service and enroll devices into management.</span></span>

> [!NOTE]
> <span data-ttu-id="31e82-112">Benutzer werden erst in der Administratorkonsole angezeigt, nachdem sie ein Gerät registriert haben.</span><span class="sxs-lookup"><span data-stu-id="31e82-112">Users will appear in the Admin console only after they have enrolled a device.</span></span> <span data-ttu-id="31e82-113">Darüber hinaus können Sie eine Gruppe von Benutzern auswählen, die Sie gleichzeitig bearbeiten möchten; so können Sie für alle Benutzer entweder eine Lizenz hinzufügen oder diese ersetzen.</span><span class="sxs-lookup"><span data-stu-id="31e82-113">Also, you can select a group of users to edit at once,  either selecting to add or replace a license for all selected users.</span></span>

## <a name="use-school-data-sync-to-assign-licenses-to-users-in-intune-for-education"></a><span data-ttu-id="31e82-114">Verwenden der Synchronisierung von Schul-/Unidaten zum Zuweisen von Lizenzen zu Benutzern in Intune for Education</span><span class="sxs-lookup"><span data-stu-id="31e82-114">Use School Data Sync to assign licenses to users in Intune for Education</span></span>
<span data-ttu-id="31e82-115">Wenn Sie zu einer Bildungseinrichtung gehören, können Sie mithilfe der Synchronisierung von Schul-/Unidaten (School Data Sync, SDS) synchronisierten Benutzern Intune for Education-Lizenzen zuweisen.</span><span class="sxs-lookup"><span data-stu-id="31e82-115">If you are an educational organization, you can use School Data Sync (SDS) to assign Intune for Education licenses to synced users.</span></span> <span data-ttu-id="31e82-116">Aktivieren Sie dazu lediglich beim Einrichten Ihres SDS-Profils das Kontrollkästchen „Intune for Education“.</span><span class="sxs-lookup"><span data-stu-id="31e82-116">Just choose the Intune for Education checkbox when you're setting up your SDS profile.</span></span>  

![Abbildung der SDS-Profileinstellung](./media/i4e-sds-profile-setup-setting.png)

<span data-ttu-id="31e82-118">Wenn Sie eine Intune Education-Lizenz zuweisen, stellen Sie sicher, dass auch eine Intune A Direct-Lizenz zugewiesen wird.</span><span class="sxs-lookup"><span data-stu-id="31e82-118">When you assign an Intune for Education license, make sure that Intune A Direct license is also assigned.</span></span>

![Abbildung der Einrichtung der Produktlizenz](./media/i4e-set-licenses.png)

<span data-ttu-id="31e82-120">In dieser [Übersicht über die Synchronisierung von Schul-/Unidaten](https://support.office.com/article/Overview-of-School-Data-Sync-and-Classroom-f3d1147b-4ade-4905-8518-508e729f2e91?ui=en-US&rs=en-US&ad=US) erfahren Sie mehr zu diesem Feature.</span><span class="sxs-lookup"><span data-stu-id="31e82-120">See this [overview of School Data Sync](https://support.office.com/article/Overview-of-School-Data-Sync-and-Classroom-f3d1147b-4ade-4905-8518-508e729f2e91?ui=en-US&rs=en-US&ad=US) to learn more about SDS.</span></span>

## <a name="how-user-and-device-licenses-affect-access-to-services"></a><span data-ttu-id="31e82-121">Auswirkungen von Benutzer- und Gerätelizenzen auf den Zugriff auf Dienste</span><span class="sxs-lookup"><span data-stu-id="31e82-121">How user and device licenses affect access to services</span></span>
* <span data-ttu-id="31e82-122">Jeder **Benutzer**, dem Sie eine Benutzersoftwarelizenz zuweisen, kann die Onlinedienste und zugehörige Software (einschließlich System Center) zum Verwalten von Anwendungen und von bis zu 15 Geräten nutzen.</span><span class="sxs-lookup"><span data-stu-id="31e82-122">Each **user** that you assign a user software license to may access and use the online services and related software (including System Center software) to manage applications and up to 15 devices.</span></span>
* <span data-ttu-id="31e82-123">Jedes **Gerät**, dem Sie eine Gerätesoftwarelizenz zuweisen, kann von einer beliebigen Anzahl von Benutzern für den Zugriff auf und die Nutzung der Onlinedienste und zugehörigen Software (einschließlich System Center) verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="31e82-123">Each **device** that you assign a device software license to may access and use the online services and related software (including System Center software) for use by any number of users.</span></span>
* <span data-ttu-id="31e82-124">Wenn ein Gerät von mehreren Benutzern verwendet wird, erfordert jedes Gerät eine Gerätesoftwarelizenz, oder alle Benutzer benötigen eine Benutzersoftwarelizenz.</span><span class="sxs-lookup"><span data-stu-id="31e82-124">If a device is used by more than one user, each requires a device software license or all users require a user software license.</span></span>

## <a name="use-powershell-to-selectively-manage-ems-user-licenses"></a><span data-ttu-id="31e82-125">Selektive Verwaltung von EMS-Benutzerlizenzen über PowerShell</span><span class="sxs-lookup"><span data-stu-id="31e82-125">Use PowerShell to selectively manage EMS user licenses</span></span>
<span data-ttu-id="31e82-126">Organisationen, die Microsoft Enterprise Mobility + Security (EMS, früher Enterprise Mobility Suite) verwenden, verfügen jedoch möglicherweise über Benutzer, die nur Azure Active Directory Premium- oder Intune-Dienste im EMS-Paket benötigen.</span><span class="sxs-lookup"><span data-stu-id="31e82-126">Organizations that use Microsoft Enterprise Mobility + Security (formerly Enterprise Mobility Suite) might have users who only require Azure Active Directory Premium or Intune services in the EMS package.</span></span> <span data-ttu-id="31e82-127">Sie können einen oder mehrere Dienste mithilfe von [Azure Active Directory PowerShell-Cmdlets](https://msdn.microsoft.com/library/jj151815.aspx) zuweisen.</span><span class="sxs-lookup"><span data-stu-id="31e82-127">You can assign one or a subset of services using [Azure Active Directory PowerShell cmdlets](https://msdn.microsoft.com/library/jj151815.aspx).</span></span>

<span data-ttu-id="31e82-128">Um Benutzerlizenzen für EMS-Dienste selektiv zuzuweisen, öffnen Sie PowerShell als Administrator auf einem Computer, auf dem das [Azure Active Directory-Modul für Windows PowerShell](https://msdn.microsoft.com/library/jj151815.aspx#bkmk_installmodule) installiert ist.</span><span class="sxs-lookup"><span data-stu-id="31e82-128">To selectively assign user licenses for EMS services, open PowerShell as an administrator on a computer with the [Azure Active Directory Module for Windows PowerShell](https://msdn.microsoft.com/library/jj151815.aspx#bkmk_installmodule) installed.</span></span> <span data-ttu-id="31e82-129">Sie können PowerShell auf einem lokalen Computer oder einem AD FS-Server installieren.</span><span class="sxs-lookup"><span data-stu-id="31e82-129">You can install PowerShell on a local computer or on an ADFS server.</span></span>

<span data-ttu-id="31e82-130">Sie müssen eine neue Lizenz-SKU-Definition erstellen, die nur für die gewünschten Servicepläne gilt.</span><span class="sxs-lookup"><span data-stu-id="31e82-130">You must create a new license SKU definition that applies only to the desired service plans.</span></span> <span data-ttu-id="31e82-131">Deaktivieren Sie zu diesem Zweck die Pläne, die Sie nicht anwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="31e82-131">To do this, disable the plans you don’t want to apply.</span></span> <span data-ttu-id="31e82-132">Sie können beispielsweise eine Lizenz-SKU-Definition erstellen, die keine Intune-Lizenzen zuweist.</span><span class="sxs-lookup"><span data-stu-id="31e82-132">For example, you might create a license SKU definition that does not assign an Intune license.</span></span> <span data-ttu-id="31e82-133">Um eine Liste der verfügbaren Dienste anzuzeigen, geben Sie Folgendes ein:.</span><span class="sxs-lookup"><span data-stu-id="31e82-133">To see a list of available services, type:</span></span>

    (Get-MsolAccountSku | Where {$_.SkuPartNumber -eq "EMS"}).ServiceStatus

<span data-ttu-id="31e82-134">Sie können den folgenden Befehl ausführen, um den Intune-Serviceplan auszuschließen.</span><span class="sxs-lookup"><span data-stu-id="31e82-134">You can run the following command to exclude the Intune service plan.</span></span> <span data-ttu-id="31e82-135">Mit der gleichen Methode können Sie die Definition auf eine vollständige Sicherheitsgruppe ausweiten oder detailliertere Filter verwenden.</span><span class="sxs-lookup"><span data-stu-id="31e82-135">You can use the same method to expand to an entire security group or you can use more granular filters.</span></span>

<span data-ttu-id="31e82-136">**Beispiel 1**</span><span class="sxs-lookup"><span data-stu-id="31e82-136">**Example 1**</span></span><br>
<span data-ttu-id="31e82-137">Erstellen Sie über die Befehlszeile einen neuen Benutzer, und weisen Sie eine EMS-Lizenz zu, ohne den auf Intune bezogenen Teil der Lizenz zu aktivieren:</span><span class="sxs-lookup"><span data-stu-id="31e82-137">Create a new user on the command line and assign an EMS license without enabling the Intune portion of the license:</span></span>

    Connect-MsolService

    New-MsolUser -DisplayName “Test User” -FirstName FName -LastName LName -UserPrincipalName user@<TenantName>.onmicrosoft.com –Department DName -UsageLocation US

    $CustomEMS = New-MsolLicenseOptions -AccountSkuId "<TenantName>:EMS" -DisabledPlans INTUNE_A
    Set-MsolUserLicense -UserPrincipalName user@<TenantName>.onmicrosoft.com -AddLicenses <TenantName>:EMS -LicenseOptions $CustomEMS


<span data-ttu-id="31e82-138">Überprüfen Sie das Ergebnis:</span><span class="sxs-lookup"><span data-stu-id="31e82-138">Verify with:</span></span>

    (Get-MsolUser -UserPrincipalName "user@<TenantName>.onmicrosoft.com").Licenses.ServiceStatus

<span data-ttu-id="31e82-139">**Beispiel 2**</span><span class="sxs-lookup"><span data-stu-id="31e82-139">**Example 2**</span></span><br>
<span data-ttu-id="31e82-140">Deaktivieren Sie den auf Intune bezogenen Teil der EMS-Lizenz für einen Benutzer, dem bereits eine Lizenz zugewiesen wurde:</span><span class="sxs-lookup"><span data-stu-id="31e82-140">Disable the Intune portion of EMS license for a user that is already assigned with a license:</span></span>

    Connect-MsolService

    $CustomEMS = New-MsolLicenseOptions -AccountSkuId "<TenantName>:EMS" -DisabledPlans INTUNE_A
    Set-MsolUserLicense -UserPrincipalName user@<TenantName>.onmicrosoft.com -LicenseOptions $CustomEMS

<span data-ttu-id="31e82-141">Überprüfen Sie das Ergebnis:</span><span class="sxs-lookup"><span data-stu-id="31e82-141">Verify with:</span></span>

    (Get-MsolUser -UserPrincipalName "user@<TenantName>.onmicrosoft.com").Licenses.ServiceStatus

![PoSH-AddLic-Verify](./media/posh-addlic-verify.png)
