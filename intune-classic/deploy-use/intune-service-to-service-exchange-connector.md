---
title: "Exchange Connector für Exchange Online"
description: "Verbinden Sie Intune mit dem Office 365-Exchange-Dienst, um die Verwaltung mobiler Geräte (Mobile Device Management, MDM) mit Exchange ActiveSync zu unterstützen."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 07/29/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 05fa5dc9-9bad-4557-987a-9b8ce4edebb0
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: muhosabe
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: e75c456f5f8ef569ff9ad6338796cb753806edf7
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2017
---
# <a name="configure-the-intune-service-to-service-connector-for-exchange-online"></a><span data-ttu-id="114b6-103">Konfigurieren des Microsoft Intune Service to Service Connector für Hosted Exchange</span><span class="sxs-lookup"><span data-stu-id="114b6-103">Configure the Intune service to service connector for Exchange Online</span></span>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="114b6-104">Anhand dieser Informationen können Sie Microsoft Intune und Exchange Online oder den neuen Exchange Online Dedicated-Dienst verbinden.</span><span class="sxs-lookup"><span data-stu-id="114b6-104">Use this information to connect Microsoft Intune and Exchange Online or the new Exchange Online Dedicated service.</span></span> <span data-ttu-id="114b6-105">Wenn Sie herausfinden möchten, ob es sich bei Ihrer Exchange Online Dedicated-Umgebung um die **neue** oder die **ältere** Version handelt, wenden Sie sich an Ihren Kundenbetreuer.</span><span class="sxs-lookup"><span data-stu-id="114b6-105">To determine whether your Exchange Online Dedicated environment is the **new** or **legacy** version, contact your account manager.</span></span> <span data-ttu-id="114b6-106">Intune unterstützt pro Abonnement nur eine Exchange Connector-Verbindung eines beliebigen Typs.</span><span class="sxs-lookup"><span data-stu-id="114b6-106">Intune only supports one Exchange connector connection of any type per subscription.</span></span>

## <a name="service-to-service-connector-requirements"></a><span data-ttu-id="114b6-107">Anforderungen an den Service to Service Connector</span><span class="sxs-lookup"><span data-stu-id="114b6-107">Service to Service Connector requirements</span></span>
<span data-ttu-id="114b6-108">Der **Service to Service Connector** unterstützt nur Exchange Online oder Exchange Online Dedicated und stellt keine Anforderungen an die lokale Infrastruktur.</span><span class="sxs-lookup"><span data-stu-id="114b6-108">The **Service to Service Connector** supports only Exchange Online or Exchange Online Dedicated and has no requirements for on-premises infrastructure.</span></span>

|<span data-ttu-id="114b6-109">Anforderung</span><span class="sxs-lookup"><span data-stu-id="114b6-109">Requirement</span></span>|<span data-ttu-id="114b6-110">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="114b6-110">More information</span></span>|
|---------------|--------------------|
|<span data-ttu-id="114b6-111">Konfiguration und Ausführung von Exchange Online</span><span class="sxs-lookup"><span data-stu-id="114b6-111">Exchange Online configured and running</span></span>|[<span data-ttu-id="114b6-112">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="114b6-112">Exchange Online</span></span>](https://technet.microsoft.com/library/jj200580.aspx) |
|<span data-ttu-id="114b6-113">Autorität für die Verwaltung mobiler Geräte</span><span class="sxs-lookup"><span data-stu-id="114b6-113">Mobile device management authority</span></span>| [<span data-ttu-id="114b6-114">Festlegen von Microsoft Intune als Autorität für die Verwaltung mobiler Geräte</span><span class="sxs-lookup"><span data-stu-id="114b6-114">Set the mobile device management authority to Microsoft Intune</span></span>](prerequisites-for-enrollment.md#step-2-set-mdm-authority)|
|<span data-ttu-id="114b6-115">Microsoft Exchange-Version</span><span class="sxs-lookup"><span data-stu-id="114b6-115">Microsoft Exchange version</span></span>|<span data-ttu-id="114b6-116">Exchange Online oder Exchange Online Dedicated (neu)</span><span class="sxs-lookup"><span data-stu-id="114b6-116">Exchange Online or the new Exchange Online Dedicated service</span></span>|<span data-ttu-id="114b6-117">/intune/users-permissions-add</span><span class="sxs-lookup"><span data-stu-id="114b6-117">/intune/users-permissions-add</span></span>
|<span data-ttu-id="114b6-118">Active Directory-Synchronisierung</span><span class="sxs-lookup"><span data-stu-id="114b6-118">Active Directory synchronization</span></span>|<span data-ttu-id="114b6-119">Bevor Sie den Intune-Connector verwenden können, müssen Sie die [Active Directory-Synchronisierung einrichten](/intune/users-permissions-add), damit Ihre lokalen Benutzer und Sicherheitsgruppen mit Ihrer Instanz von Azure Active Directory synchronisiert werden.</span><span class="sxs-lookup"><span data-stu-id="114b6-119">Before you can use the Intune Connector, you must [set up Active Directory synchronization](/intune/users-permissions-add) so that your local users and security groups are synchronized with your instance of Azure Active Directory.</span></span>|

### <a name="exchange-cmdlet-requirements"></a><span data-ttu-id="114b6-120">Anforderungen an Exchange-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="114b6-120">Exchange cmdlet requirements</span></span>

<span data-ttu-id="114b6-121">Sie müssen in Exchange Online ein Benutzerkonto erstellen, das vom Intune Exchange Connector verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="114b6-121">You must also create an Exchange Online user account that is used by the Intune Exchange Connector.</span></span> <span data-ttu-id="114b6-122">Das Konto muss über die Berechtigung zum Verwenden der Intune-Verwaltungskonsole und zum Ausführen der folgenden erforderlichen Windows PowerShell-Exchange-Cmdlets verfügen:</span><span class="sxs-lookup"><span data-stu-id="114b6-122">The account must have permission to use the Intune administration console and to run the following required Windows PowerShell Exchange cmdlets:</span></span>

 - <span data-ttu-id="114b6-123">Get-ActiveSyncOrganizationSettings, Set-ActiveSyncOrganizationSettings</span><span class="sxs-lookup"><span data-stu-id="114b6-123">Get-ActiveSyncOrganizationSettings, Set-ActiveSyncOrganizationSettings</span></span>
 - <span data-ttu-id="114b6-124">Get-MobileDeviceMailboxPolicy, Set-MobileDeviceMailboxPolicy, New-MobileDeviceMailboxPolicy, Remove-MobileDeviceMailboxPolicy</span><span class="sxs-lookup"><span data-stu-id="114b6-124">Get-MobileDeviceMailboxPolicy, Set-MobileDeviceMailboxPolicy, New-MobileDeviceMailboxPolicy, Remove-MobileDeviceMailboxPolicy</span></span>
 - <span data-ttu-id="114b6-125">Get-ActiveSyncDeviceAccessRule, Set-ActiveSyncDeviceAccessRule, New-ActiveSyncDeviceAccessRule, Remove-ActiveSyncDeviceAccessRule</span><span class="sxs-lookup"><span data-stu-id="114b6-125">Get-ActiveSyncDeviceAccessRule, Set-ActiveSyncDeviceAccessRule, New-ActiveSyncDeviceAccessRule, Remove-ActiveSyncDeviceAccessRule</span></span>
 - <span data-ttu-id="114b6-126">Get-MobileDeviceStatistics</span><span class="sxs-lookup"><span data-stu-id="114b6-126">Get-MobileDeviceStatistics</span></span>
 - <span data-ttu-id="114b6-127">Get-MobileDevice</span><span class="sxs-lookup"><span data-stu-id="114b6-127">Get-MobileDevice</span></span>
 - <span data-ttu-id="114b6-128">Get-ActiveSyncDeviceClass</span><span class="sxs-lookup"><span data-stu-id="114b6-128">Get-ActiveSyncDeviceClass</span></span>

## <a name="set-up-the-service-to-service-connector"></a><span data-ttu-id="114b6-129">Dienst für Service Connector einrichten</span><span class="sxs-lookup"><span data-stu-id="114b6-129">Set up the Service to Service Connector</span></span>

1. <span data-ttu-id="114b6-130">Öffnen Sie die [Microsoft Intune-Verwaltungskonsole](https://manage.microsoft.com) mit einem Benutzerkonto, das über Administratorrechten für Exchange und Berechtigungen für die [zuvor genannten](#exchange-cmdlet-requirements) Cmdlets verfügt.</span><span class="sxs-lookup"><span data-stu-id="114b6-130">Open the [Microsoft Intune administration console](https://manage.microsoft.com) with a user account that has Exchange admin rights and permissions for the cmdlets [described earlier](#exchange-cmdlet-requirements).</span></span> <span data-ttu-id="114b6-131">Microsoft Intune verwendet die E-Mail-Adresse des aktuell angemeldeten Benutzers, um die Verbindung einzurichten.</span><span class="sxs-lookup"><span data-stu-id="114b6-131">Microsoft Intune uses the email address of the currently signed-in user to set up the connection.</span></span>

2.  <span data-ttu-id="114b6-132">Wählen Sie im Bereich mit den Arbeitsbereichsverknüpfungen **ADMIN**>**Verwaltung mobiler Geräte** > **Microsoft Exchange** > **Exchange-Verbindung einrichten** aus.</span><span class="sxs-lookup"><span data-stu-id="114b6-132">In the workspace shortcuts pane, choose **ADMIN**>**Mobile Device Management** > **Microsoft Exchange** > **Set Up Exchange Connection**.</span></span>
<span data-ttu-id="114b6-133">![Seite „Service to Service Connector einrichten“](../media/intunesa5cservicetoserviceconnector.png)</span><span class="sxs-lookup"><span data-stu-id="114b6-133">![Set up service to service connector page](../media/intunesa5cservicetoserviceconnector.png)</span></span>

3.  <span data-ttu-id="114b6-134">Wählen Sie auf der Seite **Exchange-Verbindung einrichten** die Option **Dienst für Service Connector einrichten** aus.</span><span class="sxs-lookup"><span data-stu-id="114b6-134">On the **Set Up Exchange Connection** page, choose **Set Up Service to Service Connector**.</span></span>


<span data-ttu-id="114b6-135">Der Service to Service Connector wird automatisch konfiguriert und mit Ihrer Exchange Online- oder neuen Exchange Online Dedicated-Umgebung synchronisiert.</span><span class="sxs-lookup"><span data-stu-id="114b6-135">The Service to Service Connector automatically configures and synchronizes your Exchange Online or new Exchange Online Dedicated environment.</span></span>

## <a name="validate-your-exchange-connection"></a><span data-ttu-id="114b6-136">Überprüfen der Exchange-Verbindung</span><span class="sxs-lookup"><span data-stu-id="114b6-136">Validate your Exchange connection</span></span>

<span data-ttu-id="114b6-137">Nachdem Sie den Exchange Connector erfolgreich konfiguriert haben, fahren Sie mit der [Microsoft Intune-Verwaltungskonsole](https://manage.microsoft.com) fort.</span><span class="sxs-lookup"><span data-stu-id="114b6-137">After you have successfully configured the Exchange Connector, go to the [Microsoft Intune administration console](https://manage.microsoft.com).</span></span> <span data-ttu-id="114b6-138">Wählen Sie **Admin**> **Verwaltung mobiler Geräte** > **Microsoft Exchange** aus.</span><span class="sxs-lookup"><span data-stu-id="114b6-138">Choose **Admin**> **Mobile Device Management** > **Microsoft Exchange**.</span></span> <span data-ttu-id="114b6-139">Überprüfen Sie, ob die von Ihnen bereitgestellten Angaben unter **Exchange-Verbindungsinformationen** angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="114b6-139">Then validate that the details you provided appear under **Exchange Connection Information**.</span></span>

<span data-ttu-id="114b6-140">Sie können auch die Uhrzeit und das Datum des letzten erfolgreichen Synchronisationsversuchs überprüfen.</span><span class="sxs-lookup"><span data-stu-id="114b6-140">You can also check the time and date of the last successful synchronization attempt.</span></span>
