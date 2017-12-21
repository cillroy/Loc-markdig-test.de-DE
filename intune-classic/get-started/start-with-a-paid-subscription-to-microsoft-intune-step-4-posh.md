---
title: Verwalten von Intune-Lizenzen mithilfe von PowerShell
description: Verwalten von Intune-Lizenzen mit PowerShell
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 02/14/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d2d31c80-c32c-4315-8271-1b0cf9a1f78a
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 3fddbdee83c6ccf68b86bd2e335930683cb3267e
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2017
---
# <a name="manage-intune-licenses-using-powershell"></a><span data-ttu-id="133ca-103">Verwalten von Intune-Lizenzen mithilfe von PowerShell</span><span class="sxs-lookup"><span data-stu-id="133ca-103">Manage Intune licenses using PowerShell</span></span>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="133ca-104">In diesem Thema erfahren Administratoren, wie sie PowerShell verwenden können, um Benutzerlizenzen in Intune zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="133ca-104">This topic tells administrators how they use PowerShell to manage Intune user licenses.</span></span>

<span data-ttu-id="133ca-105">Bevor Benutzer sich für die Verwendung des Intune-Diensts anmelden oder ihre Geräte für die Verwaltung registrieren können, müssen Sie zunächst jedem Benutzer eine Lizenz für Ihr Intune-Abonnement zuweisen (siehe [Verwalten von Intune-Lizenzen](/intune/licenses-assign)).</span><span class="sxs-lookup"><span data-stu-id="133ca-105">Before users can sign in to use the Intune service or enroll their devices into management, you must first assign each user a license to your Intune subscription, as described in [Manage Intune licenses](/intune/licenses-assign).</span></span> <span data-ttu-id="133ca-106">Unternehmen, die jedoch Microsoft Enterprise Mobility + Security verwenden, verfügen möglicherweise über Benutzer, die nur Azure Active Directory Premium- oder Intune-Dienste im EMS-Paket benötigen.</span><span class="sxs-lookup"><span data-stu-id="133ca-106">However, organizations that use Microsoft Enterprise Mobility + Security might have users who only require Azure Active Directory Premium or Intune services in the EMS package.</span></span> <span data-ttu-id="133ca-107">Sie können einen oder mehrere Dienste mithilfe von [Azure Active Directory PowerShell-Cmdlets](https://msdn.microsoft.com/library/jj151815.aspx) zuweisen.</span><span class="sxs-lookup"><span data-stu-id="133ca-107">You can assign one or a subset of services using [Azure Active Directory PowerShell cmdlets](https://msdn.microsoft.com/library/jj151815.aspx).</span></span>

<span data-ttu-id="133ca-108">Um Benutzerlizenzen für EMS-Dienste selektiv zuzuweisen, öffnen Sie PowerShell als Administrator auf einem Computer, auf dem das [Azure Active Directory-Modul für Windows PowerShell](https://msdn.microsoft.com/library/jj151815.aspx#bkmk_installmodule) installiert ist.</span><span class="sxs-lookup"><span data-stu-id="133ca-108">To selectively assign user licenses for EMS services, open PowerShell as an administrator on a computer with the [Azure Active Directory Module for Windows PowerShell](https://msdn.microsoft.com/library/jj151815.aspx#bkmk_installmodule) installed.</span></span> <span data-ttu-id="133ca-109">Sie können PowerShell auf einem lokalen Computer oder einem AD FS-Server installieren.</span><span class="sxs-lookup"><span data-stu-id="133ca-109">You can install PowerShell on a local computer or on an ADFS server.</span></span>

<span data-ttu-id="133ca-110">Sie müssen eine neue Lizenz-SKU-Definition erstellen, die nur für die gewünschten Servicepläne gilt.</span><span class="sxs-lookup"><span data-stu-id="133ca-110">You must create a new license SKU definition that applies only to the desired service plans.</span></span> <span data-ttu-id="133ca-111">Deaktivieren Sie zu diesem Zweck die Pläne, die Sie nicht anwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="133ca-111">To do this, disable the plans you don’t want to apply.</span></span> <span data-ttu-id="133ca-112">Sie können beispielsweise eine Lizenz-SKU-Definition erstellen, die keine Intune-Lizenzen zuweist.</span><span class="sxs-lookup"><span data-stu-id="133ca-112">For example, you might create a license SKU definition that does not assign an Intune license.</span></span> <span data-ttu-id="133ca-113">Um eine Liste der verfügbaren Dienste anzuzeigen, geben Sie Folgendes ein:.</span><span class="sxs-lookup"><span data-stu-id="133ca-113">To see a list of available services, type:</span></span>

    (Get-MsolAccountSku | Where {$\_.SkuPartNumber -eq "EMS"}).ServiceStatus

<span data-ttu-id="133ca-114">Sie können den folgenden Befehl ausführen, um den Intune-Serviceplan auszuschließen.</span><span class="sxs-lookup"><span data-stu-id="133ca-114">You can run the following command to exclude the Intune service plan.</span></span> <span data-ttu-id="133ca-115">Mit der gleichen Methode können Sie die Definition auf eine vollständige Sicherheitsgruppe ausweiten oder detailliertere Filter verwenden.</span><span class="sxs-lookup"><span data-stu-id="133ca-115">You can use the same method to expand to an entire security group or you can use more granular filters.</span></span>

<span data-ttu-id="133ca-116">**Beispiel 1** Erstellen Sie über die Befehlszeile einen neuen Benutzer, und weisen Sie eine EMS-Lizenz zu, ohne den auf Intune bezogenen Teil der Lizenz zu aktivieren:</span><span class="sxs-lookup"><span data-stu-id="133ca-116">**Example 1** Create a new user on the command line and assign an EMS license without enabling the Intune portion of the license:</span></span>

    Connect-MsolService

    New-MsolUser -DisplayName “Test User” -FirstName FName -LastName LName -UserPrincipalName user@<TenantName>.onmicrosoft.com –Department DName -UsageLocation US

    $CustomEMS = New-MsolLicenseOptions -AccountSkuId "<TenantName>:EMS" -DisabledPlans INTUNE_A
    Set-MsolUserLicense -UserPrincipalName user@<TenantName>.onmicrosoft.com -AddLicenses <TenantName>:EMS -LicenseOptions $CustomEMS


<span data-ttu-id="133ca-117">Überprüfen Sie das Ergebnis:</span><span class="sxs-lookup"><span data-stu-id="133ca-117">Verify with:</span></span>

    (Get-MsolUser -UserPrincipalName "user@<TenantName>.onmicrosoft.com").Licenses.ServiceStatus

<span data-ttu-id="133ca-118">**Beispiel 2** Deaktivieren Sie den auf Intune bezogenen Teil der EMS-Lizenz für einen Benutzer, dem bereits eine Lizenz zugewiesen wurde:</span><span class="sxs-lookup"><span data-stu-id="133ca-118">**Example 2** Disable the Intune portion of EMS license for a user that is already assigned with a license:</span></span>

    Connect-MsolService

    Set-MsolUserLicense -UserPrincipalName user@<TenantName>.onmicrosoft.com -RemoveLicenses IAPProdPartnerTest:EMS

    $CustomEMS = New-MsolLicenseOptions -AccountSkuId "<TenantName>:EMS" -DisabledPlans INTUNE_A
    Set-MsolUserLicense -UserPrincipalName user@<TenantName>.onmicrosoft.com -AddLicenses <TenantName>:EMS -LicenseOptions $CustomEMS

<span data-ttu-id="133ca-119">Überprüfen Sie das Ergebnis:</span><span class="sxs-lookup"><span data-stu-id="133ca-119">Verify with:</span></span>

    (Get-MsolUser -UserPrincipalName "user@<TenantName>.onmicrosoft.com" .Licenses.ServiceStatus

![PoSH-AddLic-Verify](./media/posh-addlic-verify.png)

### <a name="next-steps"></a><span data-ttu-id="133ca-121">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="133ca-121">Next steps</span></span>
<span data-ttu-id="133ca-122">Gratulation!</span><span class="sxs-lookup"><span data-stu-id="133ca-122">Congratulations!</span></span> <span data-ttu-id="133ca-123">Sie haben Schritt 4 der Kurzanleitung *Erste Schritte mit Intune* abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="133ca-123">You have just completed step 4 of the *Intune quick start guide*.</span></span>
>[!div class="step-by-step"]
<span data-ttu-id="133ca-124">(/intune/custom-domain-name-configure) [&larr; **Synchronisieren von Benutzern mit Intune**](/intune/custom-domain-name-configure)     [**Organisieren von Benutzern und Geräten** &rarr;](.\start-with-a-paid-subscription-to-microsoft-intune-step-5.md)</span><span class="sxs-lookup"><span data-stu-id="133ca-124">(/intune/custom-domain-name-configure) [&larr; **Sync users to Intune**](/intune/custom-domain-name-configure)     [**Organize users and devices** &rarr;](.\start-with-a-paid-subscription-to-microsoft-intune-step-5.md)</span></span>  
