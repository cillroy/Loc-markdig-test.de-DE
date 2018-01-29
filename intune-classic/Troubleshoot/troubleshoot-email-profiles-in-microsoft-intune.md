---
title: Behandeln von Problemen mit E-Mail-Profilen
description: "Probleme mit E-Mail-Profilen sowie Informationen zu ihrer Problembehandlung und Lösung."
keywords: 
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 12/27/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f5c944ea-32a6-48af-bb57-16d5f1f3c588
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: tscott
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 729a0a9d7f8ec5851f11dd6608b4aaf8759195d0
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2018
---
# <a name="troubleshoot-email-profiles-in-microsoft-intune"></a><span data-ttu-id="f8279-103">Problembehandlung bei E-Mail-Profilen in Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="f8279-103">Troubleshoot email profiles in Microsoft Intune</span></span>

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="f8279-104">Hier werden einige Probleme mit E-Mail-Profilen sowie Informationen zu ihrer Problembehandlung und Lösung angeführt.</span><span class="sxs-lookup"><span data-stu-id="f8279-104">Listed here are some email profile issues and how to troubleshoot and resolve them.</span></span>

<span data-ttu-id="f8279-105">Wenn sich das Problem mit diesen Informationen nicht beheben lässt, finden Sie unter [How to get support for Microsoft Intune](how-to-get-support-for-microsoft-intune.md) (Anfordern von Support für Microsoft Intune) weitere Möglichkeiten, Hilfe zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="f8279-105">If this information does not solve your problem, see [How to get support for Microsoft Intune](how-to-get-support-for-microsoft-intune.md) to find more ways to get help.</span></span>


## <a name="unable-to-send-images-from--email-account"></a><span data-ttu-id="f8279-106">Senden von Bildern über E-Mail-Konto nicht möglich</span><span class="sxs-lookup"><span data-stu-id="f8279-106">Unable to send images from  email account</span></span>
<span data-ttu-id="f8279-107">Benutzer, deren E-Mail-Konten automatisch konfiguriert wurden, können keine Bilder von ihren Geräten senden.</span><span class="sxs-lookup"><span data-stu-id="f8279-107">Users who have email accounts automatically configured are unable to send pictures or images from their devices.</span></span>
<span data-ttu-id="f8279-108">Dies ist der Fall, wenn die Option **E-Mail-Versand aus Anwendungen von Drittanbietern zulassen**  nicht aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="f8279-108">This occurs when the option **Allow e-mail to be sent from third-party applications** is not enabled.</span></span>

### <a name="intune-solution"></a><span data-ttu-id="f8279-109">Intune-Lösung</span><span class="sxs-lookup"><span data-stu-id="f8279-109">Intune solution</span></span>

1.  <span data-ttu-id="f8279-110">Öffnen Sie die Microsoft Intune-Verwaltungskonsole, und wählen Sie **Richtlinie** Workload &gt;**Konfigurationsrichtlinie**.</span><span class="sxs-lookup"><span data-stu-id="f8279-110">Open the Microsoft Intune Administration Console, select **Policy** workload &gt; **Configuration Policy**.</span></span>

2.  <span data-ttu-id="f8279-111">Wählen Sie das E-Mail-Profil aus, und klicken Sie auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="f8279-111">Select the email profile and choose **Edit**.</span></span>

3.  <span data-ttu-id="f8279-112">Wählen Sie **E-Mail-Versand aus Anwendungen von Drittanbietern zulassen** .</span><span class="sxs-lookup"><span data-stu-id="f8279-112">Select **Allow e-mail to be sent from third-party applications.**</span></span>

### <a name="configuration-manager-integrated-with-intune-solution"></a><span data-ttu-id="f8279-113">Configuration Manager integriert mit Windows Intune</span><span class="sxs-lookup"><span data-stu-id="f8279-113">Configuration Manager integrated with Intune solution</span></span>

1.  <span data-ttu-id="f8279-114">Öffnen Sie in der Configuration Manager-Konsole &gt; **Bestand und Kompatibilität**.</span><span class="sxs-lookup"><span data-stu-id="f8279-114">Open the Configuration Manager console &gt; **Assets and Compliance**.</span></span>

2.  <span data-ttu-id="f8279-115">Erweitern Sie **Übersicht** -&gt; **Kompatibilitätseinstellungen** -&gt; **Zugriff auf Unternehmensressourcen**, und wählen Sie **E-Mail-Profile** aus.</span><span class="sxs-lookup"><span data-stu-id="f8279-115">Expand **Overview** -&gt; **Compliance Settings** -&gt; **Company Resource Access**, and select **Email Profiles**.</span></span>

3.  <span data-ttu-id="f8279-116">Klicken Sie mit der rechten Maustaste auf das E-Mail-Profil, und öffnen Sie **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="f8279-116">Right-click the e-mail profile, and open **Properties**.</span></span>

4.  <span data-ttu-id="f8279-117">Wählen Sie auf der Registerkarte **Synchronisierungseinstellungen** die Option **E-Mail-Versand aus Anwendungen von Drittanbietern zulassen** aus.</span><span class="sxs-lookup"><span data-stu-id="f8279-117">On the **Synchronization Settings** tab, select **Allow e-mail to be sent from third-party applications**.</span></span>


## <a name="device-already-has-an-email-profile-installed"></a><span data-ttu-id="f8279-118">Auf dem Gerät ist bereits ein E-Mail-Profil installiert</span><span class="sxs-lookup"><span data-stu-id="f8279-118">Device already has an email profile installed</span></span>

<span data-ttu-id="f8279-119">Wenn der Benutzer ein E-Mail-Profil installiert hat, bevor ein Profil durch Intune bereitgestellt wurde, hat die Bereitstellung des Intune-E-Mail-Profils je nach Geräteplattform folgende Auswirkungen:</span><span class="sxs-lookup"><span data-stu-id="f8279-119">If the user has installed an email profile prior to provision of a profile by Intune, the result of the Intune email profile deployment depends on the device platform:</span></span>

<span data-ttu-id="f8279-120">-**iOS**: Intune erkennt basierend auf dem Hostnamen und der E-Mail-Adresse ein vorhandenes doppeltes E-Mail-Profil.</span><span class="sxs-lookup"><span data-stu-id="f8279-120">-**iOS**: Intune detects an existing, duplicate email profile based on hostname and email address.</span></span> <span data-ttu-id="f8279-121">Das vom Benutzer erstellte doppelte E-Mail-Profil blockiert die Bereitstellung eines Profils, das vom Intune-Administrator erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="f8279-121">The duplicate email profile created by the user will block the deployment of an Intune admin-created profile.</span></span> <span data-ttu-id="f8279-122">Das ist ein häufig auftretendes Problem, da iOS-Benutzer in der Regel ein E-Mail-Profil erstellen und anschließend die Registrierung vornehmen.</span><span class="sxs-lookup"><span data-stu-id="f8279-122">This is a common problem as iOS users will typically create an email profile, then enroll.</span></span> <span data-ttu-id="f8279-123">Das Unternehmensportal informiert den Benutzer darüber, dass es aufgrund seines manuell konfigurierten E-Mail-Profils nicht kompatibel ist, und fordert ihn dazu auf, dieses Profil zu entfernen. Der Benutzer sollte sein E-Mail-Profil entfernen, damit das Intune-Profil bereitgestellt werden kann.</span><span class="sxs-lookup"><span data-stu-id="f8279-123">The company portal will inform the user that they are not compliant due to their manually-configured email profile, and will prompt the user to remove that profile.The user should remove their email profile so that the Intune profile can be deployed.</span></span> <span data-ttu-id="f8279-124">Weisen Sie Ihre Benutzer an, sich vor der Installation eines E-Mail-Profils zu registrieren und die Bereitstellung des Profils durch Intune zuzulassen, um das Problem zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="f8279-124">To prevent the problem instruct your users to enroll before installing an email profile and to allow Intune to deploy the profile.</span></span>

<span data-ttu-id="f8279-125">-**Windows**: Intune erkennt basierend auf dem Hostnamen und der E-Mail-Adresse ein vorhandenes doppeltes E-Mail-Profil.</span><span class="sxs-lookup"><span data-stu-id="f8279-125">-**Windows**: Intune detects an existing, duplicate email profile based on hostname and email address.</span></span> <span data-ttu-id="f8279-126">Intune überschreibt das vorhandene, vom Benutzer erstellte E-Mail-Profil.</span><span class="sxs-lookup"><span data-stu-id="f8279-126">Intune will overwrite the existing email profile created by the user.</span></span>

<span data-ttu-id="f8279-127">-**Samsung KNOX**: Intune identifiziert basierend auf der E-Mail-Adresse ein doppeltes E-Mail-Konto und überschreibt es mit dem Intune-Profil.</span><span class="sxs-lookup"><span data-stu-id="f8279-127">-**Samsung KNOX Standard**: Intune identifies a duplicate email account based on the email address, and will overwrite it with the Intune profile.</span></span> <span data-ttu-id="f8279-128">Wenn der Benutzer dieses Konto konfiguriert, wird es erneut durch das Intune-Profil überschrieben.</span><span class="sxs-lookup"><span data-stu-id="f8279-128">If the user configures that account, it will be overwritten again by the Intune profile.</span></span> <span data-ttu-id="f8279-129">Dies kann für den Benutzer, dessen Kontokonfiguration überschrieben wird, verwirrend sein.</span><span class="sxs-lookup"><span data-stu-id="f8279-129">Note that this may cause some confusion to the user whose account configuration gets overwritten.</span></span>

<span data-ttu-id="f8279-130">Da Samsung KNOX zum Identifizieren des Profils keinen Hostnamen verwendet, wird davon abgeraten, mehrere E-Mail-Profile für die Bereitstellung unter derselben E-Mail-Adresse auf unterschiedlichen Hosts zu erstellen, da sie sich gegenseitig überschreiben.</span><span class="sxs-lookup"><span data-stu-id="f8279-130">Since Samsung KNOX does not use hostname to identify the profile, we recommend that you not create multiple email profiles to deploy to the same email address on different hosts, as these will overwrite each other.</span></span>

## <a name="error--0x87d1fde8-for-knox-standard-device"></a><span data-ttu-id="f8279-131">Fehler „0x87D1FDE8“ für KNOX Standard-Gerät</span><span class="sxs-lookup"><span data-stu-id="f8279-131">Error  0x87D1FDE8 for KNOX Standard device</span></span>
<span data-ttu-id="f8279-132">**Problem**: Nach dem Erstellen und Bereitstellen eines Exchange ActiveSync-E-Mail-Profils für Samsung KNOX Standard für verschiedene Android-Geräte melden diese den Fehler **0x87D1FDE8** oder **Fehler bei Wiederherstellung** auf der Registerkarte „Eigenschaften“ &gt; „Richtlinie“ des Geräts.</span><span class="sxs-lookup"><span data-stu-id="f8279-132">**Issue**: After creating and deploying an Exchange Active Sync email profile for Samsung KNOX Standard for various Android devices, the error **0x87D1FDE8** or **remediation failed** is reported in the device's properties &gt; policy tab.</span></span>

<span data-ttu-id="f8279-133">Überprüfen Sie die Konfiguration Ihres EAS-Profils für Samsung KNOX und die Quellrichtlinie.</span><span class="sxs-lookup"><span data-stu-id="f8279-133">Review the configuration of your EAS profile for Samsung KNOX and source policy.</span></span> <span data-ttu-id="f8279-134">Die Samsung-Option zum Synchronisieren von Notizen wird nicht mehr unterstützt, und diese Option sollte in Ihrem Profil nicht ausgewählt werden.</span><span class="sxs-lookup"><span data-stu-id="f8279-134">The Samsung Notes sync option is no longer supported and that option should not be selected in your profile.</span></span> <span data-ttu-id="f8279-135">Achten Sie darauf, dass Geräte genug Zeit hatten, um die Richtlinie zu verarbeiten (bis zu 24 Stunden).</span><span class="sxs-lookup"><span data-stu-id="f8279-135">Be sure devices have had enough time to process the policy, up to 24 hours.</span></span>

## <a name="next-steps"></a><span data-ttu-id="f8279-136">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="f8279-136">Next steps</span></span>
<span data-ttu-id="f8279-137">Wenn diese Informationen zur Problembehandlung für Sie nicht hilfreich waren, wenden Sie sich wie in [Anfordern von Support für Microsoft Intune](how-to-get-support-for-microsoft-intune.md) beschrieben an den Microsoft Support.</span><span class="sxs-lookup"><span data-stu-id="f8279-137">If this troubleshooting information didn't help you, contact Microsoft Support as described in [How to get support for Microsoft Intune](how-to-get-support-for-microsoft-intune.md).</span></span>
