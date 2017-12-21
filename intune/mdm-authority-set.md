---
title: "Festlegen der Autorität für die Verwaltung mobiler Geräte"
titlesuffix: Azure portal
description: "Erfahren Sie, wie die Autorität für die Verwaltung mobiler Geräte in Intune festlegen. \""
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 10/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 8deff871-5dff-4767-9484-647428998d82
ms.reviewer: damionw
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 581cbc5ef9a6a02deb4e266b0845b95b65215c0f
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2017
---
# <a name="set-the-mobile-device-management-authority"></a><span data-ttu-id="627aa-104">Festlegen der Autorität für die Verwaltung mobiler Geräte</span><span class="sxs-lookup"><span data-stu-id="627aa-104">Set the mobile device management authority</span></span>

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="627aa-105">Die Einstellung für die Autorität für die Verwaltung mobiler Geräte (Mobile Device Management, MDM) bestimmt, wie Sie Ihre Geräte verwalten.</span><span class="sxs-lookup"><span data-stu-id="627aa-105">The mobile device management (MDM) authority setting determines how you manage your devices.</span></span> <span data-ttu-id="627aa-106">Als IT-Administrator müssen Sie eine MDM-Autorität festlegen, damit Benutzer Geräte zur Verwaltung registrieren können.</span><span class="sxs-lookup"><span data-stu-id="627aa-106">As an IT admin, you must set an MDM authority before users can enroll devices for management.</span></span>

<span data-ttu-id="627aa-107">Die möglichen Konfigurationen sind Folgende:</span><span class="sxs-lookup"><span data-stu-id="627aa-107">Possible configurations are:</span></span>

- <span data-ttu-id="627aa-108">**Intune Standalone:** Ausschließliche Verwaltung in der Cloud, die Sie mithilfe des Azure-Portals konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="627aa-108">**Intune Standalone** - cloud-only management, which you configure by using the Azure portal.</span></span> <span data-ttu-id="627aa-109">Ihnen stehen alle Funktionen von Intune zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="627aa-109">Includes the full set of capabilities that Intune offers.</span></span> <span data-ttu-id="627aa-110">[Legen Sie die MDM-Autorität in der Intune-Konsole fest](#set-mdm-authority-to-intune).</span><span class="sxs-lookup"><span data-stu-id="627aa-110">[Set the MDM authority in the Intune console](#set-mdm-authority-to-intune).</span></span>

- <span data-ttu-id="627aa-111">**Intune Hybrid:** Integration der Intune-Cloudlösung in System Center Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="627aa-111">**Intune Hybrid** - integration of the Intune cloud solution with System Center Configuration Manager.</span></span> <span data-ttu-id="627aa-112">Sie konfigurieren Intune mithilfe der Configuration Manager-Konsole.</span><span class="sxs-lookup"><span data-stu-id="627aa-112">You configure Intune by using the Configuration Manager console.</span></span> <span data-ttu-id="627aa-113">[Legen Sie die MDM-Autorität im Configuration Manager fest](https://docs.microsoft.com/sccm/mdm/deploy-use/configure-intune-subscription).</span><span class="sxs-lookup"><span data-stu-id="627aa-113">[Set the MDM authority in Configuration Manager](https://docs.microsoft.com/sccm/mdm/deploy-use/configure-intune-subscription).</span></span>

- <span data-ttu-id="627aa-114">**Verwaltung mobiler Geräte für Office 365:** Integration von Office 365 in die Intune-Cloudlösung.</span><span class="sxs-lookup"><span data-stu-id="627aa-114">**Mobile Device Management for Office 365** - integration of Office 365 with the Intune cloud solution.</span></span> <span data-ttu-id="627aa-115">Sie konfigurieren Intune über das Office 365 Admin Center.</span><span class="sxs-lookup"><span data-stu-id="627aa-115">You configure Intune from your Office 365 Admin Center.</span></span> <span data-ttu-id="627aa-116">Ihnen steht eine Teilmenge der Funktionen von Intune Standalone zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="627aa-116">Includes a subset of the capabilities that are available with Intune Standalone.</span></span> <span data-ttu-id="627aa-117">Legen Sie die MDM-Autorität im Office 365 Admin Center fest.</span><span class="sxs-lookup"><span data-stu-id="627aa-117">Set the MDM authority in Office 365 Admin Center.</span></span>

>[!IMPORTANT]    
<span data-ttu-id="627aa-118">In Configuration Manager, Version 1610 oder höher, und Microsoft Intune, Version 1705, können Sie Ihre MDM-Autorität ändern, ohne sich an den Microsoft Support wenden und die Aufhebung der Registrierung sowie die erneute Registrierung vorhandener verwalteten Geräte durchführen zu müssen.</span><span class="sxs-lookup"><span data-stu-id="627aa-118">In Configuration Manager version 1610 or later and Microsoft Intune version 1705, you change the MDM authority without having to contact Microsoft Support, and without having to unenroll and reenroll your existing managed devices.</span></span> <span data-ttu-id="627aa-119">Details finden Sie unter [Was Sie machen können, wenn Sie die falsche MDM-Autoritätseinstellung vorgenommen haben](/intune-classic/deploy-use/prerequisites-for-enrollment#what-to-do-if-you-choose-the-wrong-mdm-authority-setting).</span><span class="sxs-lookup"><span data-stu-id="627aa-119">For details, see [What to do if you choose the wrong MDM authority setting](/intune-classic/deploy-use/prerequisites-for-enrollment#what-to-do-if-you-choose-the-wrong-mdm-authority-setting).</span></span>

## <a name="set-mdm-authority-to-intune"></a><span data-ttu-id="627aa-120">Festlegen der MDM-Autorität in Intune</span><span class="sxs-lookup"><span data-stu-id="627aa-120">Set MDM authority to Intune</span></span>

1. <span data-ttu-id="627aa-121">Wählen Sie im [Azure-Portal](https://portal.azure.com) die Optionen **Weitere Dienste** > **Überwachung + Verwaltung** > **Intune** aus.</span><span class="sxs-lookup"><span data-stu-id="627aa-121">In the [Azure portal](https://portal.azure.com), choose **More Services** > **Monitoring + Management** > **Intune**.</span></span>
2. <span data-ttu-id="627aa-122">Wählen Sie den orangefarbenen Banner aus, um die Einstellung **Autorität für die Verwaltung mobiler Geräte** zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="627aa-122">Select the orange banner to open the **Mobile Device Management Authority** setting.</span></span>
3. <span data-ttu-id="627aa-123">Wählen Sie unter **Autorität für die Verwaltung mobiler Geräte** Ihre MDM-Autorität aus den folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="627aa-123">Under **Mobile Device Management Authority**, choose your MDM authority from the following options:</span></span>
  - <span data-ttu-id="627aa-124">**Intune-MDM-Autorität**</span><span class="sxs-lookup"><span data-stu-id="627aa-124">**Intune MDM Authority**</span></span>
  - <span data-ttu-id="627aa-125">**Configuration Manager-MDM-Autorität**</span><span class="sxs-lookup"><span data-stu-id="627aa-125">**Configuration Manager MDM Authority**</span></span>
  - <span data-ttu-id="627aa-126">**Keine**</span><span class="sxs-lookup"><span data-stu-id="627aa-126">**None**</span></span>

  ![Screenshot vom Intune-Bildschirm zum Festlegen der Autorität für die mobile Geräteverwaltung](media/set-mdm-auth.png)

  <span data-ttu-id="627aa-128">Eine Meldung zeigt an, dass Sie die MDM-Autorität erfolgreich auf Intune festgelegt haben.</span><span class="sxs-lookup"><span data-stu-id="627aa-128">A message indicates that you have successfully set your MDM authority to Intune.</span></span>

## <a name="enable-device-enrollment"></a><span data-ttu-id="627aa-129">Aktivieren der Geräteregistrierung</span><span class="sxs-lookup"><span data-stu-id="627aa-129">Enable device enrollment</span></span>

<span data-ttu-id="627aa-130">Mit Intune als MDM-Autorität können Benutzer private Geräte registrieren und durch das Installieren der Unternehmensportal-App (iOS und Android), das Hinzufügen von Unternehmensanmeldeinformationen (Windows) oder das Zugreifen auf die Unternehmensportal-Website (iOS, Android, macOS) Zugriff auf Ressourcen wie E-Mails erhalten.</span><span class="sxs-lookup"><span data-stu-id="627aa-130">With Intune set as your MDM authority, users can enroll personally owned devices and gain access to resources like email in the following ways by installing the Company Portal (iOS and Android), adding work credentials (Windows), or accessing the Company Portal website (iOS, Android, macOS).</span></span>

<span data-ttu-id="627aa-131">Verschiedene Plattformen haben die folgenden Anforderungen für das Aktivieren oder Vereinfachen der Registrierung:</span><span class="sxs-lookup"><span data-stu-id="627aa-131">Different platforms have the following requirements to enable or simplify enrollment:</span></span>
- <span data-ttu-id="627aa-132">**iOS** – (erforderlich): [Rufen Sie ein MDM-Pushzertifikat von Apple ab](apple-mdm-push-certificate-get.md), und [registrieren Sie dann unternehmenseigene iOS-Geräte](ios-enroll.md) (optional).</span><span class="sxs-lookup"><span data-stu-id="627aa-132">**iOS** - (required) [Get an Apple MDM push certificate](apple-mdm-push-certificate-get.md) and then [enable enrollment for company-owned iOS devices](ios-enroll.md) (optional).</span></span>
- <span data-ttu-id="627aa-133">**Android** – (optional): [Aktivieren Sie Android-Arbeitsprofile.](android-enroll.md)</span><span class="sxs-lookup"><span data-stu-id="627aa-133">**Android** - (optional) [Enable Android work profiles](android-enroll.md)</span></span>
- <span data-ttu-id="627aa-134">**Windows** – (optional): Aktivieren Sie die [automatische Registrierung](windows-enroll.md) oder die [Massenregistrierung](windows-bulk-enroll.md).</span><span class="sxs-lookup"><span data-stu-id="627aa-134">**Windows** - (optional) Enable [Automatic enrollment](windows-enroll.md) or [bulk enrollment](windows-bulk-enroll.md)</span></span>
- <span data-ttu-id="627aa-135">**macOS**: Keine Anforderungen</span><span class="sxs-lookup"><span data-stu-id="627aa-135">**macOS** - No requirements</span></span>


## <a name="mobile-device-cleanup-after-mdm-certificate-expiration"></a><span data-ttu-id="627aa-136">Bereinigen mobiler Geräte nach Ablauf des MDM-Zertifikats</span><span class="sxs-lookup"><span data-stu-id="627aa-136">Mobile device cleanup after MDM certificate expiration</span></span>

<span data-ttu-id="627aa-137">Das MDM-Zertifikat wird automatisch erneuert, wenn mobile Geräte mit dem Intune-Dienst kommunizieren.</span><span class="sxs-lookup"><span data-stu-id="627aa-137">The MDM certificate is renewed automatically when mobile devices are communicating with the Intune service.</span></span> <span data-ttu-id="627aa-138">Wenn mobile Geräte zurückgesetzt werden oder für längere Zeit keine Kommunikation mit dem Intune-Dienst stattfindet, wird das MDM-Zertifikat nicht erneuert.</span><span class="sxs-lookup"><span data-stu-id="627aa-138">If mobile devices are wiped, or they fail to communicate with the Intune service for some period of time, the MDM certificate will not get renewed.</span></span> <span data-ttu-id="627aa-139">Das Gerät wird 180 Tage nach Ablauf des MDM-Zertifikats aus dem Azure-Portal entfernt.</span><span class="sxs-lookup"><span data-stu-id="627aa-139">The device is removed from the Azure portal 180 days after the MDM certificate expires.</span></span>
