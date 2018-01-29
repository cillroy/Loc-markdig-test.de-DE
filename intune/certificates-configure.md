---
title: Konfigurieren von Zertifikaten mit Intune
titlesuffix: Azure portal
description: "Erfahren Sie, wie Sie mit Intune Zertifikate erstellen und zuweisen, mit denen Sie WLAN-, VPN- und andere Verbindungen sichern können.\""
keywords: 
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 11/28/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5eccfa11-52ab-49eb-afef-a185b4dccde1
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 59bd1afa299620b8b2f1d35a9141cf752d459c07
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2018
---
# <a name="how-to-configure-certificates-in-microsoft-intune"></a><span data-ttu-id="28fc5-103">Konfigurieren von Zertifikaten in Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="28fc5-103">How to configure certificates in Microsoft Intune</span></span>

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="28fc5-104">Wenn Sie Benutzern den Zugriff auf Unternehmensressourcen über VPN, WLAN oder E-Mail-Profile gestatten, können Sie diese Verbindungen mit Zertifikaten authentifizieren.</span><span class="sxs-lookup"><span data-stu-id="28fc5-104">When you give users access to corporate resources through VPN, Wi-Fi, or email profiles, you can authenticate these connections by using certificates.</span></span> <span data-ttu-id="28fc5-105">Wenn Sie Zertifikate verwenden, ist die Eingabe von Benutzernamen und Kennwörtern zum Authentifizieren von Verbindungen überflüssig.</span><span class="sxs-lookup"><span data-stu-id="28fc5-105">You don't need to enter user names and passwords to authenticate connections when you use certificates.</span></span>

<span data-ttu-id="28fc5-106">Mit Intune können Sie diese Zertifikate Geräten zuweisen, die Sie verwalten.</span><span class="sxs-lookup"><span data-stu-id="28fc5-106">You can use Intune to assign these certificates to devices you manage.</span></span> <span data-ttu-id="28fc5-107">Intune unterstützt das Zuweisen und Verwalten dieser Zertifikattypen:</span><span class="sxs-lookup"><span data-stu-id="28fc5-107">Intune supports assigning and managing these certificate types:</span></span>

- <span data-ttu-id="28fc5-108">Simple Certificate Enrollment-Protokoll (SCEP)</span><span class="sxs-lookup"><span data-stu-id="28fc5-108">Simple Certificate Enrollment Protocol (SCEP)</span></span>
- <span data-ttu-id="28fc5-109">PKCS#12 (oder PFX)</span><span class="sxs-lookup"><span data-stu-id="28fc5-109">PKCS#12 (or PFX)</span></span>

<span data-ttu-id="28fc5-110">Jeder dieser Zertifikattypen hat eigene Voraussetzungen und Infrastrukturanforderungen.</span><span class="sxs-lookup"><span data-stu-id="28fc5-110">Each of these certificate types has its own prerequisites and infrastructure requirements.</span></span>

## <a name="general-workflow"></a><span data-ttu-id="28fc5-111">Allgemeiner Workflow</span><span class="sxs-lookup"><span data-stu-id="28fc5-111">General workflow</span></span>

1. <span data-ttu-id="28fc5-112">Stellen Sie sicher, dass Sie die richtige Zertifikatinfrastruktur eingerichtet haben.</span><span class="sxs-lookup"><span data-stu-id="28fc5-112">Ensure you have the right certificate infrastructure in place.</span></span> <span data-ttu-id="28fc5-113">Sie können [SCEP-Zertifikate](certificates-scep-configure.md) und [PKCS-Zertifikate](certficates-pfx-configure.md) verwenden.</span><span class="sxs-lookup"><span data-stu-id="28fc5-113">You can use [SCEP certificates](certificates-scep-configure.md), and [PKCS certificates](certficates-pfx-configure.md).</span></span>
2. <span data-ttu-id="28fc5-114">Installieren Sie auf jedem Gerät ein Stammzertifikat oder ein Zertifikat einer Zwischenzertifizierungsstelle, damit das Gerät die Rechtmäßigkeit Ihrer Zertifizierungsstelle erkennt.</span><span class="sxs-lookup"><span data-stu-id="28fc5-114">Install a root certificate or an intermediate Certification Authority (CA) certificate on each device so that the device recognizes the legitimacy of your CA.</span></span> <span data-ttu-id="28fc5-115">Erstellen Sie zu diesem Zweck ein **vertrauenswürdiges Zertifikatprofil** und weisen Sie es zu.</span><span class="sxs-lookup"><span data-stu-id="28fc5-115">To do this, create and assign a **trusted certificate profile**.</span></span> <span data-ttu-id="28fc5-116">Wenn Sie dieses Profil zuweisen, wird das Stammzertifikat von den Geräten, die Sie mit Intune verwalten, angefordert und empfangen.</span><span class="sxs-lookup"><span data-stu-id="28fc5-116">When you assign this profile, the devices that you manage with Intune request and receive the root certificate.</span></span> <span data-ttu-id="28fc5-117">Sie müssen für jede Plattform ein eigenes Profil erstellen.</span><span class="sxs-lookup"><span data-stu-id="28fc5-117">You must create a separate profile for each platform.</span></span> <span data-ttu-id="28fc5-118">Vertrauenswürdige Zertifikatprofile sind für folgende Plattformen verfügbar:</span><span class="sxs-lookup"><span data-stu-id="28fc5-118">Trusted certificate profiles are available for these platforms:</span></span>
    - <span data-ttu-id="28fc5-119">iOS 8.0 und höher</span><span class="sxs-lookup"><span data-stu-id="28fc5-119">iOS 8.0 and later</span></span>
    - <span data-ttu-id="28fc5-120">macOS 10.9 und höher</span><span class="sxs-lookup"><span data-stu-id="28fc5-120">macOS 10.9 and later</span></span>
    - <span data-ttu-id="28fc5-121">Android 4,0 und höher</span><span class="sxs-lookup"><span data-stu-id="28fc5-121">Android 4.0 and later</span></span>
    - <span data-ttu-id="28fc5-122">Android for Work</span><span class="sxs-lookup"><span data-stu-id="28fc5-122">Android for Work</span></span>
    - <span data-ttu-id="28fc5-123">Windows 8.1 und höher</span><span class="sxs-lookup"><span data-stu-id="28fc5-123">Windows 8.1 and later</span></span>
    - <span data-ttu-id="28fc5-124">Windows Phone 8.1 und höher</span><span class="sxs-lookup"><span data-stu-id="28fc5-124">Windows Phone 8.1 and later</span></span>
    - <span data-ttu-id="28fc5-125">Windows 10 und höher</span><span class="sxs-lookup"><span data-stu-id="28fc5-125">Windows 10 and later</span></span>
3. <span data-ttu-id="28fc5-126">Erstellen Sie Zertifikatprofile, damit Geräte ein Zertifikat für die Authentifizierung des VPN-, WLAN- und E-Mail-Zugriffs anfordern.</span><span class="sxs-lookup"><span data-stu-id="28fc5-126">Create certificate profiles so that devices request a certificate to be used for authentication of VPN, Wi-Fi, and email access.</span></span>

   <span data-ttu-id="28fc5-127">Sie können ein **PKCS**- oder **SCEP**-Zertifikatprofil für Geräte auf diesen Plattformen erstellen und zuweisen:</span><span class="sxs-lookup"><span data-stu-id="28fc5-127">You can create and assign a **PKCS** or **SCEP** certificate profile for devices running these platforms:</span></span>

   - <span data-ttu-id="28fc5-128">iOS 8.0 und höher</span><span class="sxs-lookup"><span data-stu-id="28fc5-128">iOS 8.0 and later</span></span>
   - <span data-ttu-id="28fc5-129">Android 4,0 und höher</span><span class="sxs-lookup"><span data-stu-id="28fc5-129">Android 4.0 and later</span></span>
   - <span data-ttu-id="28fc5-130">Android for Work</span><span class="sxs-lookup"><span data-stu-id="28fc5-130">Android for Work</span></span>
   - <span data-ttu-id="28fc5-131">Windows 10 (Desktop und Mobile) und höher</span><span class="sxs-lookup"><span data-stu-id="28fc5-131">Windows 10 (desktop and mobile) and later</span></span>

   <span data-ttu-id="28fc5-132">Für Geräte, die diese Plattformen ausführen, können Sie nur ein **SCEP**-Zertifikatprofil verwenden:</span><span class="sxs-lookup"><span data-stu-id="28fc5-132">You can only use a **SCEP** certificate profile for devices running these platforms:</span></span>

   - <span data-ttu-id="28fc5-133">macOS 10.9 und höher</span><span class="sxs-lookup"><span data-stu-id="28fc5-133">macOS 10.9 and later</span></span>
   - <span data-ttu-id="28fc5-134">Windows Phone 8.1 und höher</span><span class="sxs-lookup"><span data-stu-id="28fc5-134">Windows Phone 8.1 and later</span></span>

<span data-ttu-id="28fc5-135">Sie müssen für jede Geräteplattform ein eigenes Profil erstellen.</span><span class="sxs-lookup"><span data-stu-id="28fc5-135">You must create a separate profile for each device platform.</span></span> <span data-ttu-id="28fc5-136">Nachdem Sie das Profil erstellt haben, ordnen Sie es dem bereits erstellten vertrauenswürdigen Stammzertifikatprofil zu.</span><span class="sxs-lookup"><span data-stu-id="28fc5-136">When you create the profile, associate it with the trusted root certificate profile that you've already created.</span></span>

### <a name="further-considerations"></a><span data-ttu-id="28fc5-137">Weitere Überlegungen</span><span class="sxs-lookup"><span data-stu-id="28fc5-137">Further considerations</span></span>

- <span data-ttu-id="28fc5-138">Wenn Sie über keine Unternehmenszertifizierungsstelle verfügen, müssen Sie eine erstellen.</span><span class="sxs-lookup"><span data-stu-id="28fc5-138">If you don't have an Enterprise Certification Authority, you must create one.</span></span>
- <span data-ttu-id="28fc5-139">Sie müssen auch einen NDES-Server (Network Device Enrollment Service, Registrierungsdienst für Netzwerkgeräte) konfigurieren, wenn Sie SCEP-Profile verwenden.</span><span class="sxs-lookup"><span data-stu-id="28fc5-139">You also need to configure a Network Device Enrollment Service (NDES) server if you use SCEP profiles.</span></span>
- <span data-ttu-id="28fc5-140">Unabhängig davon, ob Sie SCEP- oder PKCS-Profile verwenden möchten, müssen Sie den Microsoft Intune Certificate Connector herunterladen und konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="28fc5-140">Whether you plan to use SCEP or PKCS profiles, you must download and configure the Microsoft Intune Certificate Connector.</span></span>


## <a name="step-1-configure-your-certificate-infrastructure"></a><span data-ttu-id="28fc5-141">Schritt 1: Konfigurieren der Zertifikatinfrastruktur</span><span class="sxs-lookup"><span data-stu-id="28fc5-141">Step 1: Configure your certificate infrastructure</span></span>

<span data-ttu-id="28fc5-142">Unter den folgenden Themen finden Sie Hilfe zum Konfigurieren der Infrastruktur für jeden Zertifikatprofiltyp:</span><span class="sxs-lookup"><span data-stu-id="28fc5-142">See one of the following topics for help configuring the infrastructure for each type of certificate profile:</span></span>

- [<span data-ttu-id="28fc5-143">Konfigurieren der Zertifikatinfrastruktur für SCEP in Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="28fc5-143">Configure and manage SCEP certificates with Intune</span></span>](certificates-scep-configure.md)
- [<span data-ttu-id="28fc5-144">Konfigurieren Ihrer Microsoft Intune-Zertifikatsinfrastruktur für PKCS</span><span class="sxs-lookup"><span data-stu-id="28fc5-144">Configure and manage PKCS certificates with Intune</span></span>](certficates-pfx-configure.md)


## <a name="step-2-export-your-trusted-root-ca-certificate"></a><span data-ttu-id="28fc5-145">Schritt 2: Exportieren des vertrauenswürdigen Zertifikats der Stammzertifizierungsstelle</span><span class="sxs-lookup"><span data-stu-id="28fc5-145">Step 2: Export your trusted root CA certificate</span></span>

<span data-ttu-id="28fc5-146">Exportieren Sie das Zertifikat vertrauenswürdigen Stammzertifizierungsstelle als **CER**-Datei aus der ausstellenden Zertifizierungsstelle oder von einem beliebigen Gerät, das die ausstellende Zertifizierungsstelle als vertrauenswürdig erachtet.</span><span class="sxs-lookup"><span data-stu-id="28fc5-146">Export the Trusted Root Certification Authorities (CA) certificate as a **.cer** file from the issuing CA, or from any device that trusts your issuing CA.</span></span> <span data-ttu-id="28fc5-147">Exportieren Sie auf keinen Fall den privaten Schlüssel.</span><span class="sxs-lookup"><span data-stu-id="28fc5-147">Do not export the private key.</span></span>

<span data-ttu-id="28fc5-148">Sie importieren dieses Zertifikat, wenn Sie ein vertrauenswürdiges Zertifikatprofil einrichten.</span><span class="sxs-lookup"><span data-stu-id="28fc5-148">You import this certificate when you set up a trusted certificate profile.</span></span>

## <a name="step-3-create-trusted-certificate-profiles"></a><span data-ttu-id="28fc5-149">Schritt 3: Erstellen von vertrauenswürdigen Zertifikatprofilen</span><span class="sxs-lookup"><span data-stu-id="28fc5-149">Step 3: Create trusted certificate profiles</span></span>
<span data-ttu-id="28fc5-150">Sie müssen ein Profil mit einem vertrauenswürdigen Zertifikat erstellen, bevor Sie ein SCEP- oder PKCS-Zertifikatprofil erstellen können.</span><span class="sxs-lookup"><span data-stu-id="28fc5-150">You must create a trusted certificate profile before you can create a SCEP or PKCS certificate profile.</span></span> <span data-ttu-id="28fc5-151">Sie benötigen ein Profil mit einem vertrauenswürdigen Zertifikat und ein SCEP- oder PKCS-Profil für jede Geräteplattform.</span><span class="sxs-lookup"><span data-stu-id="28fc5-151">You need a trusted certificate profile and a SCEP or PKCS profile for each device platform.</span></span> <span data-ttu-id="28fc5-152">Der Ablauf des Erstellens vertrauenswürdiger Zertifikate ist für jede Geräteplattform ähnlich.</span><span class="sxs-lookup"><span data-stu-id="28fc5-152">The flow for creating trusted certificates is similar for each device platform.</span></span>

### <a name="to-create-a-trusted-certificate-profile"></a><span data-ttu-id="28fc5-153">So erstellen Sie ein vertrauenswürdiges Zertifikatprofil</span><span class="sxs-lookup"><span data-stu-id="28fc5-153">To create a trusted certificate profile</span></span>

1. <span data-ttu-id="28fc5-154">Melden Sie sich beim Azure-Portal an.</span><span class="sxs-lookup"><span data-stu-id="28fc5-154">Sign into the Azure portal.</span></span>
2. <span data-ttu-id="28fc5-155">Wählen Sie **Weitere Dienste** > **Überwachung und Verwaltung** > **Intune** aus.</span><span class="sxs-lookup"><span data-stu-id="28fc5-155">Choose **More Services** > **Monitoring + Management** > **Intune**.</span></span>
3. <span data-ttu-id="28fc5-156">Wählen Sie auf dem Blatt **Intune** die Option **Gerätekonfiguration** aus.</span><span class="sxs-lookup"><span data-stu-id="28fc5-156">On the **Intune** blade, choose **Device configuration**.</span></span>
2. <span data-ttu-id="28fc5-157">Wählen Sie auf dem Blatt **Gerätekonfiguration** die Option **Verwalten** > **Profile** aus.</span><span class="sxs-lookup"><span data-stu-id="28fc5-157">On the **Device Configuration** blade, choose **Manage** > **Profiles**.</span></span>
3. <span data-ttu-id="28fc5-158">Wählen Sie auf dem Blatt „Profile“ die Option **Profil erstellen** aus.</span><span class="sxs-lookup"><span data-stu-id="28fc5-158">On the profiles blade, choose **Create Profile**.</span></span>
4. <span data-ttu-id="28fc5-159">Geben Sie auf dem Blatt **Profil erstellen** einen **Namen** und eine **Beschreibung** für das vertrauenswürdige Zertifikatprofil ein.</span><span class="sxs-lookup"><span data-stu-id="28fc5-159">On the **Create Profile** blade, enter a **Name** and **Description** for the trusted certificate profile.</span></span>
5. <span data-ttu-id="28fc5-160">Wählen Sie in der Dropdownliste **Plattform** die Geräteplattform für das vertrauenswürdige Zertifikat aus.</span><span class="sxs-lookup"><span data-stu-id="28fc5-160">From the **Platform** drop-down list, select the device platform for this trusted certificate.</span></span> <span data-ttu-id="28fc5-161">Derzeit können Sie eine der folgenden Plattformen für Zertifikateinstellungen auswählen:</span><span class="sxs-lookup"><span data-stu-id="28fc5-161">Currently, you can choose one of the following platforms for certificate settings:</span></span>
    - <span data-ttu-id="28fc5-162">**Android**</span><span class="sxs-lookup"><span data-stu-id="28fc5-162">**Android**</span></span>
    - <span data-ttu-id="28fc5-163">**iOS**</span><span class="sxs-lookup"><span data-stu-id="28fc5-163">**iOS**</span></span>
    - <span data-ttu-id="28fc5-164">**macOS**</span><span class="sxs-lookup"><span data-stu-id="28fc5-164">**macOS**</span></span>
    - <span data-ttu-id="28fc5-165">**Windows Phone 8.1**</span><span class="sxs-lookup"><span data-stu-id="28fc5-165">**Windows Phone 8.1**</span></span>
    - <span data-ttu-id="28fc5-166">**Windows 8.1 und höher**</span><span class="sxs-lookup"><span data-stu-id="28fc5-166">**Windows 8.1 and later**</span></span>
    - <span data-ttu-id="28fc5-167">**Windows 10 und höher**</span><span class="sxs-lookup"><span data-stu-id="28fc5-167">**Windows 10 and later**</span></span>
6. <span data-ttu-id="28fc5-168">Wählen Sie in der Dropdownliste **Profiltyp** die Option **Vertrauenswürdiges Zertifikat** aus.</span><span class="sxs-lookup"><span data-stu-id="28fc5-168">From the **Profile type** drop-down list, choose **Trusted certificate**.</span></span>
7. <span data-ttu-id="28fc5-169">Navigieren Sie zu dem Zertifikat, das Sie in Aufgabe 1 gespeichert haben, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="28fc5-169">Browse to the certificate you saved in task 1, then click **OK**.</span></span>
8. <span data-ttu-id="28fc5-170">Wählen Sie (nur bei Windows 8.1- und Windows 10-Geräten) den **Zielspeicher** für das vertrauenswürdige Zertifikat aus:</span><span class="sxs-lookup"><span data-stu-id="28fc5-170">For Windows 8.1 and Windows 10 devices only, select the **Destination Store** for the trusted certificate from:</span></span>
    - <span data-ttu-id="28fc5-171">**Computerzertifikatspeicher – Stamm**</span><span class="sxs-lookup"><span data-stu-id="28fc5-171">**Computer certificate store - Root**</span></span>
    - <span data-ttu-id="28fc5-172">**Computerzertifikatspeicher – Zwischenspeicher**</span><span class="sxs-lookup"><span data-stu-id="28fc5-172">**Computer certificate store - Intermediate**</span></span>
    - <span data-ttu-id="28fc5-173">**Benutzerzertifikatspeicher – Zwischenspeicher**</span><span class="sxs-lookup"><span data-stu-id="28fc5-173">**User certificate store - Intermediate**</span></span>
8. <span data-ttu-id="28fc5-174">Klicken Sie zum Abschluss auf **OK**. Navigieren Sie, wenn Sie fertig sind, zurück zum Blatt **Profil erstellen**, und klicken Sie auf **Erstellen**.</span><span class="sxs-lookup"><span data-stu-id="28fc5-174">When you're done, choose **OK**, go back to the **Create Profile** blade, and hit **Create**.</span></span>

<span data-ttu-id="28fc5-175">Das Profil wird erstellt und auf dem Blatt mit der Profilliste angezeigt.</span><span class="sxs-lookup"><span data-stu-id="28fc5-175">The profile is created and appears on the profiles list blade.</span></span>

<span data-ttu-id="28fc5-176">Wenn Sie fortfahren und dieses Profil Gruppen zuweisen möchten, lesen Sie unter [Zuweisen von Geräteprofilen](device-profile-assign.md) nach.</span><span class="sxs-lookup"><span data-stu-id="28fc5-176">If you want to go ahead and assign this profile to groups, see [How to assign device profiles](device-profile-assign.md).</span></span>


> [!Note]
> <span data-ttu-id="28fc5-177">Android-Geräte zeigen eine Benachrichtigung an, dass ein Drittanbieter ein vertrauenswürdiges Zertifikat installiert hat.</span><span class="sxs-lookup"><span data-stu-id="28fc5-177">Android devices display a notice that a third party has installed a trusted certificate.</span></span>

## <a name="step-4-create-scep-or-pkcs-certificate-profiles"></a><span data-ttu-id="28fc5-178">Schritt 4: Erstellen von SCEP- oder PKCS-Zertifikatprofilen</span><span class="sxs-lookup"><span data-stu-id="28fc5-178">Step 4: Create SCEP or PKCS certificate profiles</span></span>

<span data-ttu-id="28fc5-179">Unter den folgenden Themen finden Sie Hilfe zum Konfigurieren und Zuweisen jedes Zertifikatprofiltyps:</span><span class="sxs-lookup"><span data-stu-id="28fc5-179">See one of the following topics for help configuring and assigning each type of certificate profile:</span></span>

- [<span data-ttu-id="28fc5-180">Konfigurieren der Zertifikatinfrastruktur für SCEP in Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="28fc5-180">Configure and manage SCEP certificates with Intune</span></span>](certificates-scep-configure.md)
- [<span data-ttu-id="28fc5-181">Konfigurieren Ihrer Microsoft Intune-Zertifikatsinfrastruktur für PKCS</span><span class="sxs-lookup"><span data-stu-id="28fc5-181">Configure and manage PKCS certificates with Intune</span></span>](certficates-pfx-configure.md)

<span data-ttu-id="28fc5-182">Nachdem Sie ein Profil des vertrauenswürdigen Zertifikats erstellt haben, erstellen Sie SCEP- oder PKCS-Zertifikatprofile für jede Plattform, die Sie verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="28fc5-182">After you create a trusted certificate profile, create SCEP or PKCS certificate profiles for each platform you want to use.</span></span> <span data-ttu-id="28fc5-183">Wenn Sie ein SCEP-Zertifikatprofil erstellen, müssen Sie ein vertrauenswürdiges Zertifikatprofil für dieselbe Plattform angeben.</span><span class="sxs-lookup"><span data-stu-id="28fc5-183">When you create a SCEP certificate profile, you must specify a trusted certificate profile for that same platform.</span></span> <span data-ttu-id="28fc5-184">Auf diese Weise werden die beiden Zertifikatprofile verknüpft. Sie müssen jedes Profil trotzdem separat zuweisen.</span><span class="sxs-lookup"><span data-stu-id="28fc5-184">This links the two certificate profiles, but you still must assign each profile separately.</span></span>


## <a name="next-steps"></a><span data-ttu-id="28fc5-185">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="28fc5-185">Next steps</span></span>
<span data-ttu-id="28fc5-186">Allgemeine Informationen zum Zuweisen von Geräteprofilen finden Sie unter [Zuweisen von Geräteprofilen](device-profile-assign.md).</span><span class="sxs-lookup"><span data-stu-id="28fc5-186">See [How to assign device profiles](device-profile-assign.md) for general information about how to assign device profiles.</span></span>
