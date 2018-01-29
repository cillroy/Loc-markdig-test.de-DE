---
title: Konfigurieren von Zertifikatprofilen
description: Erfahren Sie, wie Sie ein Intune-Zertifikatprofil erstellen.
keywords: 
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 10/25/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 679a20a1-e66f-4b6b-bd8f-896daf1f8175
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: kmyrup
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 3b16dca7bd604ba74384a9f329d4efe5e5790dc2
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2018
---
# <a name="configure-intune-certificate-profiles"></a><span data-ttu-id="4ecd0-103">Konfigurieren von Intune-Zertifikatprofilen</span><span class="sxs-lookup"><span data-stu-id="4ecd0-103">Configure Intune certificate profiles</span></span>

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="4ecd0-104">Nachdem Sie Ihre Infrastruktur und Zertifikate konfiguriert haben (gemäß der Beschreibung in [Konfigurieren der Zertifikatinfrastruktur für SCEP](configure-certificate-infrastructure-for-scep.md) oder [Konfigurieren der Zertifikatinfrastruktur für PFX](configure-certificate-infrastructure-for-pfx.md)), können Sie Zertifikatprofile erstellen.</span><span class="sxs-lookup"><span data-stu-id="4ecd0-104">After you've configured your infrastructure and certificates as described in [Configure certificate infrastructure for SCEP](configure-certificate-infrastructure-for-scep.md) or [Configure certificate infrastructure for PFX](configure-certificate-infrastructure-for-pfx.md), you can create certificate profiles.</span></span> <span data-ttu-id="4ecd0-105">Gehen Sie dazu folgendermaßen vor:</span><span class="sxs-lookup"><span data-stu-id="4ecd0-105">Here's the process:</span></span>

- <span data-ttu-id="4ecd0-106">**Aufgabe 1**: Exportieren des Zertifikats der vertrauenswürdigen Stamm-CA</span><span class="sxs-lookup"><span data-stu-id="4ecd0-106">**Task 1**: Export the Trusted Root CA certificate</span></span>
- <span data-ttu-id="4ecd0-107">**Aufgabe 2**: Erstellen von vertrauenswürdigen Zertifikatprofilen</span><span class="sxs-lookup"><span data-stu-id="4ecd0-107">**Task 2**: Create Trusted certificate profiles</span></span>
- <span data-ttu-id="4ecd0-108">**Aufgabe 3**: Erstellen eines von zwei Zertifikatprofiltypen:</span><span class="sxs-lookup"><span data-stu-id="4ecd0-108">**Task 3**: Create one of two certificate profile types:</span></span>
  - <span data-ttu-id="4ecd0-109">SCEP-Zertifikatprofile</span><span class="sxs-lookup"><span data-stu-id="4ecd0-109">SCEP certificate profiles</span></span>
  - <span data-ttu-id="4ecd0-110">PFX-Zertifikatprofile</span><span class="sxs-lookup"><span data-stu-id="4ecd0-110">.PFX certificate profiles</span></span>

## <a name="task-1-export-the-trusted-root-ca-certificate"></a><span data-ttu-id="4ecd0-111">**Aufgabe 1**: Exportieren des Zertifikats der vertrauenswürdigen Stamm-CA</span><span class="sxs-lookup"><span data-stu-id="4ecd0-111">**Task 1**: Export the Trusted Root CA certificate</span></span>
<span data-ttu-id="4ecd0-112">Exportieren Sie das Zertifikat vertrauenswürdigen Stammzertifizierungsstelle als **CER**-Datei aus der ausstellenden Zertifizierungsstelle oder von einem beliebigen Gerät, das die ausstellende Zertifizierungsstelle als vertrauenswürdig erachtet.</span><span class="sxs-lookup"><span data-stu-id="4ecd0-112">Export the Trusted Root Certification Authorities (CA) certificate as a **.cer** file from the issuing CA, or from any device that trusts your issuing CA.</span></span> <span data-ttu-id="4ecd0-113">Exportieren Sie auf keinen Fall den privaten Schlüssel.</span><span class="sxs-lookup"><span data-stu-id="4ecd0-113">Do not export the private key.</span></span>

<span data-ttu-id="4ecd0-114">Sie importieren dieses Zertifikat, wenn Sie ein vertrauenswürdiges Zertifikatprofil einrichten.</span><span class="sxs-lookup"><span data-stu-id="4ecd0-114">You'll import this certificate when you set up a Trusted certificate profile.</span></span>

## <a name="task-2-create-trusted-certificate-profiles"></a><span data-ttu-id="4ecd0-115">**Aufgabe 2**: Erstellen von vertrauenswürdigen Zertifikatprofilen</span><span class="sxs-lookup"><span data-stu-id="4ecd0-115">**Task 2**: Create Trusted certificate profiles</span></span>
<span data-ttu-id="4ecd0-116">Sie müssen ein vertrauenswürdiges Zertifikatprofil erstellen, bevor Sie ein Simple Certificate Enrollment Protocol- oder ein PKCS #12-Zertifikatprofil erstellen können (d.h. SCEP- oder PFX-Zertifikatprofile).</span><span class="sxs-lookup"><span data-stu-id="4ecd0-116">You must create a Trusted certificate profile before you can create a Simple Certificate Enrollment Protocol (SCEP) or a PKCS #12 (.PFX) certificate profile.</span></span> <span data-ttu-id="4ecd0-117">Sie benötigen ein vertrauenswürdiges Zertifikatprofil und ein SCEP- oder PFS-Profil für jede Plattform für mobile Geräte.</span><span class="sxs-lookup"><span data-stu-id="4ecd0-117">You need a Trusted certificate profile and an SCEP or .PFX profile for each mobile device platform.</span></span>

### <a name="to-create-a-trusted-certificate-profile"></a><span data-ttu-id="4ecd0-118">So erstellen Sie ein vertrauenswürdiges Zertifikatprofil</span><span class="sxs-lookup"><span data-stu-id="4ecd0-118">To create a Trusted certificate profile</span></span>

1.  <span data-ttu-id="4ecd0-119">Wählen Sie in der [Intune-Verwaltungskonsole](https://manage.microsoft.com) **Richtlinie** &gt; **Richtlinie hinzufügen** und anschließend eine Geräteplattform aus.</span><span class="sxs-lookup"><span data-stu-id="4ecd0-119">In the [Intune administration console](https://manage.microsoft.com), choose **Policy** &gt; **Add Policy**, and choose a device platform.</span></span> <span data-ttu-id="4ecd0-120">Sie können ein vertrauenswürdiges Zertifikatprofil für diese Geräte erstellen:</span><span class="sxs-lookup"><span data-stu-id="4ecd0-120">You can create a trusted certificate profile for these devices:</span></span>

-  <span data-ttu-id="4ecd0-121">Android 4 und höher</span><span class="sxs-lookup"><span data-stu-id="4ecd0-121">Android 4 and later</span></span>

-  <span data-ttu-id="4ecd0-122">Android for Work</span><span class="sxs-lookup"><span data-stu-id="4ecd0-122">Android for Work</span></span>

-  <span data-ttu-id="4ecd0-123">iOS 7.1 und höher</span><span class="sxs-lookup"><span data-stu-id="4ecd0-123">iOS 7.1 and later</span></span>

-  <span data-ttu-id="4ecd0-124">Mac OS X 10.9 und höher</span><span class="sxs-lookup"><span data-stu-id="4ecd0-124">Mac OS X 10.9 and later</span></span>

-  <span data-ttu-id="4ecd0-125">Windows 8.1 und höher</span><span class="sxs-lookup"><span data-stu-id="4ecd0-125">Windows 8.1 and later</span></span>

-  <span data-ttu-id="4ecd0-126">Windows Phone 8.1 und höher</span><span class="sxs-lookup"><span data-stu-id="4ecd0-126">Windows Phone 8.1 and later</span></span>

2.  <span data-ttu-id="4ecd0-127">Fügen Sie eine Richtlinie für ein **vertrauenswürdiges Zertifikatprofil** hinzu.</span><span class="sxs-lookup"><span data-stu-id="4ecd0-127">Add a **Trusted Certificate Profile** policy.</span></span>

    <span data-ttu-id="4ecd0-128">Weitere Informationen finden Sie unter [Verwalten von Einstellungen und Features auf Ihren Geräten mit Microsoft Intune-Richtlinien](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md).</span><span class="sxs-lookup"><span data-stu-id="4ecd0-128">Learn more: [Manage settings and features on your devices with Microsoft Intune policies](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md).</span></span>

3.  <span data-ttu-id="4ecd0-129">Geben Sie die angeforderten Informationen ein, um die Profileinstellungen vertrauenswürdiger Zertifikate für Android, iOS, Mac OS X, Windows 8.1 oder Windows Phone 8.1 zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="4ecd0-129">Enter the requested information to configure the Trusted certificate profile settings for Android, iOS, Mac OS X, Windows 8.1, or Windows Phone 8.1.</span></span>
4.  <span data-ttu-id="4ecd0-130">Importieren Sie in der Einstellung **Zertifikatdatei** das Zertifikat der vertrauenswürdigen Stamm-CA (CER-Datei), das Sie aus der ausstellenden Zertifizierungsstelle exportiert haben.</span><span class="sxs-lookup"><span data-stu-id="4ecd0-130">In the **Certificate file** setting, import the Trusted Root CA certificate (.cer file) that you exported from your issuing CA.</span></span> <span data-ttu-id="4ecd0-131">Die Einstellung **Zielspeicher** gilt nur für Geräte mit Windows 8.1 und höher und auch nur, wenn das Gerät über mehr als einen Zertifikatspeicher verfügt.</span><span class="sxs-lookup"><span data-stu-id="4ecd0-131">The **Destination store** setting applies only to devices running Windows 8.1 and later, and only if the device has more than one certificate store.</span></span>

4.  <span data-ttu-id="4ecd0-132">Wählen Sie **Richtlinie speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="4ecd0-132">Choose **Save Policy**.</span></span>

<span data-ttu-id="4ecd0-133">Die neue Richtlinie wird im Arbeitsbereich **Richtlinie** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="4ecd0-133">The new policy is shown in the **Policy** workspace.</span></span> <span data-ttu-id="4ecd0-134">Sie können sie nun bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="4ecd0-134">Now you can deploy it.</span></span>

> [!NOTE]
>
> <span data-ttu-id="4ecd0-135">Android- und Android for Work-Geräte zeigen eine Benachrichtigung an, dass ein Drittanbieter ein vertrauenswürdiges Zertifikat installiert hat.</span><span class="sxs-lookup"><span data-stu-id="4ecd0-135">Android and Android for Work devices will display a notice that a third party has installed a trusted certificate.</span></span>


## <a name="task-3-create-scep-or-pfx-certificate-profiles"></a><span data-ttu-id="4ecd0-136">**Aufgabe 3**: Erstellen von SCEP- oder PFX-Zertifikatprofilen</span><span class="sxs-lookup"><span data-stu-id="4ecd0-136">**Task 3**: Create SCEP or .PFX certificate profiles</span></span>
<span data-ttu-id="4ecd0-137">Nachdem Sie ein Profil des vertrauenswürdigen Zertifizierungsstellenzertifikats erstellt haben, erstellen Sie SCEP- oder PFX-Zertifikatprofile für jede Plattform, die Sie verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="4ecd0-137">After you create a Trusted CA certificate profile, create SCEP or .PFX certificate profiles for each platform you want to use.</span></span> <span data-ttu-id="4ecd0-138">Wenn Sie ein SCEP-Zertifikatprofil erstellen, müssen Sie ein vertrauenswürdiges Zertifikatprofil für dieselbe Plattform angeben.</span><span class="sxs-lookup"><span data-stu-id="4ecd0-138">When you create an SCEP certificate profile, you must specify a Trusted certificate profile for that same platform.</span></span> <span data-ttu-id="4ecd0-139">Auf diese Weise werden die beiden Zertifikatprofile verknüpft. Sie müssen jedes Profil trotzdem separat bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="4ecd0-139">This links the two certificate profiles, but you still must deploy each profile separately.</span></span>

### <a name="to-create-an-scep-certificate-profile"></a><span data-ttu-id="4ecd0-140">So erstellen Sie ein SCEP-Zertifikatprofil</span><span class="sxs-lookup"><span data-stu-id="4ecd0-140">To create an SCEP certificate profile</span></span>

1.  <span data-ttu-id="4ecd0-141">Wählen Sie in der [Intune-Verwaltungskonsole](https://manage.microsoft.com) **Richtlinie** &gt; **Richtlinie hinzufügen** und anschließend eine Geräteplattform aus.</span><span class="sxs-lookup"><span data-stu-id="4ecd0-141">In the [Intune administration console](https://manage.microsoft.com), choose **Policy** &gt; **Add Policy** and choose a device platform.</span></span>  <span data-ttu-id="4ecd0-142">Sie können ein SCEP-Zertifikatprofil für diese Geräte erstellen:</span><span class="sxs-lookup"><span data-stu-id="4ecd0-142">You can create a SCEP certificate profile for these devices:</span></span>

-  <span data-ttu-id="4ecd0-143">Android 4 und höher</span><span class="sxs-lookup"><span data-stu-id="4ecd0-143">Android 4 and later</span></span>

-  <span data-ttu-id="4ecd0-144">Android for Work</span><span class="sxs-lookup"><span data-stu-id="4ecd0-144">Android for Work</span></span>

-  <span data-ttu-id="4ecd0-145">iOS 7.1 und höher</span><span class="sxs-lookup"><span data-stu-id="4ecd0-145">iOS 7.1 and later</span></span>

-  <span data-ttu-id="4ecd0-146">Mac OS X 10.9 und höher</span><span class="sxs-lookup"><span data-stu-id="4ecd0-146">Mac OS X 10.9 and later</span></span>

-  <span data-ttu-id="4ecd0-147">Windows 8.1 und höher</span><span class="sxs-lookup"><span data-stu-id="4ecd0-147">Windows 8.1 and later</span></span>

-  <span data-ttu-id="4ecd0-148">Windows Phone 8.1 und höher</span><span class="sxs-lookup"><span data-stu-id="4ecd0-148">Windows Phone 8.1 and later</span></span>

2. <span data-ttu-id="4ecd0-149">Fügen Sie eine Richtlinie für ein **SCEP-Zertifikatprofil** hinzu.</span><span class="sxs-lookup"><span data-stu-id="4ecd0-149">Add a **SCEP Certificate Profile** policy</span></span>

   <span data-ttu-id="4ecd0-150">Weitere Informationen finden Sie unter [Verwalten von Einstellungen und Features auf Ihren Geräten mit Microsoft Intune-Richtlinien](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md).</span><span class="sxs-lookup"><span data-stu-id="4ecd0-150">Learn more: [Manage settings and features on your devices with Microsoft Intune policies](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md).</span></span>

3. <span data-ttu-id="4ecd0-151">Befolgen Sie die Anweisungen auf der Profilkonfigurationsseite, um die SCEP-Zertifikatprofileinstellungen zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="4ecd0-151">Follow the instructions on the profile configuration page to configure the SCEP certificate profile settings.</span></span>
   > [!NOTE]
   > 
   > <span data-ttu-id="4ecd0-152">Wählen Sie unter **Format des Antragstellernamens** die Option **Benutzerdefiniert** aus, um ein benutzerdefiniertes Format für den Antragstellernamen einzugeben (nur in iOS-Profilen).</span><span class="sxs-lookup"><span data-stu-id="4ecd0-152">Under **Subject name format**, select **Custom** to enter a custom subject name format (in iOS profiles, only).</span></span>
   > 
   > <span data-ttu-id="4ecd0-153">Die beiden derzeit für das benutzerdefinierte Format unterstützten Variablen sind `Common Name (CN)` und `Email (E)`.</span><span class="sxs-lookup"><span data-stu-id="4ecd0-153">The two variables currently supported for the custom format are `Common Name (CN)` and `Email (E)`.</span></span> <span data-ttu-id="4ecd0-154">Durch eine Kombination dieser Variablen mit statischen Zeichenfolgen können Sie ein benutzerdefiniertes Format wie dieses für den Antragstellernamen erstellen:</span><span class="sxs-lookup"><span data-stu-id="4ecd0-154">By using a combination of these variables and static strings, you can create a custom subject name format, like this one:</span></span>
   > 
   >     <span data-ttu-id="4ecd0-155">CN={{UserName}},E={{EmailAddress}},OU=Mobile,O=Finance Group,L=Redmond,ST=Washington,C=US</span><span class="sxs-lookup"><span data-stu-id="4ecd0-155">CN={{UserName}},E={{EmailAddress}},OU=Mobile,O=Finance Group,L=Redmond,ST=Washington,C=US</span></span>
   > 
   > <span data-ttu-id="4ecd0-156">In diesem Beispiel hat der Administrator ein Format für den Antragstellernamen erstellt, das zusätzlich zu den Variablen `CN` und `E` entsprechende Zeichenfolgen für Organisationseinheit (OU), Organisation (O), Ort (L), Bundesland/Kanton (ST) und Land (C) verwendet.</span><span class="sxs-lookup"><span data-stu-id="4ecd0-156">In this example, the admin created a subject name format that, in addition to the `CN` and `E` variables, uses strings for Organizational Unit, Organization, Location, State, and Country values.</span></span> <span data-ttu-id="4ecd0-157">Die [CertStrToName](https://msdn.microsoft.com/library/windows/desktop/aa377160.aspx)-Funktion listet unterstützte Zeichenfolgen auf.</span><span class="sxs-lookup"><span data-stu-id="4ecd0-157">[CertStrToName function](https://msdn.microsoft.com/library/windows/desktop/aa377160.aspx) lists supported strings.</span></span>

4. <span data-ttu-id="4ecd0-158">Wählen Sie **Richtlinie speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="4ecd0-158">Choose **Save Policy**.</span></span>

<span data-ttu-id="4ecd0-159">Die neue Richtlinie wird im Arbeitsbereich **Richtlinie** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="4ecd0-159">The new policy is shown in the **Policy** workspace.</span></span> <span data-ttu-id="4ecd0-160">Sie können sie nun bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="4ecd0-160">Now you can deploy it.</span></span>

### <a name="to-create-a-pfx-certificate-profile"></a><span data-ttu-id="4ecd0-161">So erstellen Sie ein PFX-Zertifikatprofil</span><span class="sxs-lookup"><span data-stu-id="4ecd0-161">To create a .PFX certificate profile</span></span>

1. <span data-ttu-id="4ecd0-162">Wählen Sie in der [Intune-Verwaltungskonsole](https://manage.microsoft.com) **Richtlinie** &gt; **Richtlinie hinzufügen** und anschließend eine Geräteplattform aus.</span><span class="sxs-lookup"><span data-stu-id="4ecd0-162">In the [Intune administration console](https://manage.microsoft.com), choose **Policy** &gt; **Add Policy**, and choose a device platform.</span></span> <span data-ttu-id="4ecd0-163">PFX-Zertifikate werden für folgende Betriebssysteme unterstützt:</span><span class="sxs-lookup"><span data-stu-id="4ecd0-163">.PFX certificates are supported for:</span></span>
   - <span data-ttu-id="4ecd0-164">Android 4 und höher</span><span class="sxs-lookup"><span data-stu-id="4ecd0-164">Android 4 and later</span></span>
   - <span data-ttu-id="4ecd0-165">Android for Work</span><span class="sxs-lookup"><span data-stu-id="4ecd0-165">Android for Work</span></span>
   - <span data-ttu-id="4ecd0-166">Windows 10 und höher</span><span class="sxs-lookup"><span data-stu-id="4ecd0-166">Windows 10 and later</span></span>
   - <span data-ttu-id="4ecd0-167">Windows Phone 10 und höher</span><span class="sxs-lookup"><span data-stu-id="4ecd0-167">Windows Phone 10 and later</span></span>
   - <span data-ttu-id="4ecd0-168">iOS 8.0 und höher)</span><span class="sxs-lookup"><span data-stu-id="4ecd0-168">iOS 8.0 and later)</span></span>    


2. <span data-ttu-id="4ecd0-169">Fügen Sie eine Richtlinie für ein **PFX-Zertifikatprofil** hinzu.</span><span class="sxs-lookup"><span data-stu-id="4ecd0-169">Add a **.PFX Certificate Profile** policy.</span></span>
     <span data-ttu-id="4ecd0-170">Weitere Informationen finden Sie unter [Verwalten von Einstellungen und Features auf Ihren Geräten mit Microsoft Intune-Richtlinien](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md).</span><span class="sxs-lookup"><span data-stu-id="4ecd0-170">Learn more: [Manage settings and features on your devices with Microsoft Intune policies](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md).</span></span>
3. <span data-ttu-id="4ecd0-171">Geben Sie die Informationen ein, die auf dem Richtlinienformular angefordert werden.</span><span class="sxs-lookup"><span data-stu-id="4ecd0-171">Enter the information requested on the policy form.</span></span>
4. <span data-ttu-id="4ecd0-172">Wählen Sie **Richtlinie speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="4ecd0-172">Choose **Save Policy**.</span></span>

<span data-ttu-id="4ecd0-173">Die neue Richtlinie wird im Arbeitsbereich **Richtlinie** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="4ecd0-173">The new policy is shown in the **Policy** workspace.</span></span> <span data-ttu-id="4ecd0-174">Sie können sie nun bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="4ecd0-174">Now you can deploy it.</span></span>

## <a name="deploy-certificate-profiles"></a><span data-ttu-id="4ecd0-175">Bereitstellen von Zertifikatprofilen</span><span class="sxs-lookup"><span data-stu-id="4ecd0-175">Deploy certificate profiles</span></span>
<span data-ttu-id="4ecd0-176">Wenn Sie Zertifikatprofile bereitstellen, wird die Zertifikatdatei aus dem Profil des vertrauenswürdigen Zertifizierungsstellenzertifikats auf dem Gerät installiert.</span><span class="sxs-lookup"><span data-stu-id="4ecd0-176">When you deploy certificate profiles, the certificate file from the Trusted CA certificate profile is installed on the device.</span></span> <span data-ttu-id="4ecd0-177">Das Gerät verwendet das SCEP- oder PFX-Zertifikatprofil, um eine Zertifikatanforderung zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="4ecd0-177">The device uses the SCEP or .PFX certificate profile to create a certificate request by the device.</span></span>

<span data-ttu-id="4ecd0-178">Zertifikatprofile werden nur auf den Geräten installiert, auf denen die beim Erstellen des Profils verwendete Plattform ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="4ecd0-178">Certificate profiles install only on devices running the platform you use when you create the profile.</span></span>

-   <span data-ttu-id="4ecd0-179">Sie können Zertifikatprofile für Benutzer- oder Gerätesammlungen bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="4ecd0-179">You can deploy certificate profiles to user collections or to device collections.</span></span>

    > [!TIP]
    > <span data-ttu-id="4ecd0-180">Damit Zertifikate möglichst schnell nach deren Registrierung auf Geräten veröffentlicht werden können, stellen Sie das Zertifikatprofil lieber für eine Benutzergruppe bereit (und nicht für eine Gerätegruppe).</span><span class="sxs-lookup"><span data-stu-id="4ecd0-180">To publish a certificate to a device quickly after the device enrolls, deploy the certificate profile to a user group rather than to a device group.</span></span> <span data-ttu-id="4ecd0-181">Wenn Sie es für eine Gerätegruppe bereitstellen, muss eine vollständige Geräteregistrierung stattfinden, bevor das Gerät Richtlinien empfängt.</span><span class="sxs-lookup"><span data-stu-id="4ecd0-181">If you deploy to a device group, a full device registration is required before the device receives policies.</span></span>

-   <span data-ttu-id="4ecd0-182">Obwohl Sie jedes Profil separat bereitstellen, müssen Sie auch die vertrauenswürdige Stamm-CA und die SCEP- oder PFX-Profile bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="4ecd0-182">Although you deploy each profile separately, you also need to deploy the Trusted Root CA and the SCEP or .PFX profile.</span></span> <span data-ttu-id="4ecd0-183">Andernfalls schlägt die SCEP- oder PFX-Zertifikatrichtlinie fehl.</span><span class="sxs-lookup"><span data-stu-id="4ecd0-183">Otherwise, the SCEP or .PFX certificate policy will fail.</span></span>

<span data-ttu-id="4ecd0-184">Stellen Sie Zertifikatprofile auf die gleiche Weise bereit wie andere Richtlinien für Intune:</span><span class="sxs-lookup"><span data-stu-id="4ecd0-184">Deploy certificate profiles the same way you deploy other policies for Intune:</span></span>

1.  <span data-ttu-id="4ecd0-185">Wählen Sie im Arbeitsbereich **Richtlinie** die Richtlinie aus, die Sie bereitstellen möchten, und wählen Sie anschließend **Bereitstellung verwalten** aus.</span><span class="sxs-lookup"><span data-stu-id="4ecd0-185">In the **Policy** workspace, select the policy you want to deploy, and then choose **Manage Deployment**.</span></span>
2.  <span data-ttu-id="4ecd0-186">Führen Sie im Dialogfeld **Bereitstellung verwalten** folgende Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="4ecd0-186">In the **Manage Deployment** dialog box:</span></span>
    -   <span data-ttu-id="4ecd0-187">**So stellen Sie die Richtlinie bereit**: Wählen Sie mindestens eine Gruppe aus, für die Sie die Richtlinie bereitstellen möchten, und wählen Sie anschließend **Hinzufügen** &gt; **OK** aus.</span><span class="sxs-lookup"><span data-stu-id="4ecd0-187">**To deploy the policy**, select one or more groups to deploy the policy to, and then choose **Add** &gt; **OK**.</span></span>
    -   <span data-ttu-id="4ecd0-188">**So schließen Sie das Dialogfeld, ohne die Richtlinie bereitzustellen**: Klicken Sie auf **Abbrechen**.</span><span class="sxs-lookup"><span data-stu-id="4ecd0-188">**To close the dialog box without deploying it**, choose **Cancel**.</span></span>

<span data-ttu-id="4ecd0-189">Wenn Sie eine bereitgestellte Richtlinie auswählen, können Sie weitere Informationen zur Bereitstellung im unteren Teil der Richtlinienliste anzeigen.</span><span class="sxs-lookup"><span data-stu-id="4ecd0-189">When you select a deployed policy, you can see more information about the deployment in the lower part of the list of policies.</span></span>

### <a name="next-steps"></a><span data-ttu-id="4ecd0-190">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="4ecd0-190">Next steps</span></span>

<span data-ttu-id="4ecd0-191">Erfahren Sie nun, wie Sie mithilfe von Zertifikaten E-Mail-, WLAN- und VPN-Profile schützen können.</span><span class="sxs-lookup"><span data-stu-id="4ecd0-191">Next, learn how to use certificates to help secure email, Wi-Fi, and VPN profiles.</span></span>

-  [<span data-ttu-id="4ecd0-192">Konfigurieren des Zugriffs auf Unternehmens-E-Mail mithilfe von E-Mail-Profilen</span><span class="sxs-lookup"><span data-stu-id="4ecd0-192">Configure access to corporate email using email profiles</span></span>](configure-access-to-corporate-email-using-email-profiles-with-Microsoft-Intune.md)
-  [<span data-ttu-id="4ecd0-193">WLAN-Verbindungen in Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="4ecd0-193">Wi-Fi connections in Microsoft Intune</span></span>](wi-fi-connections-in-microsoft-intune.md)
-  [<span data-ttu-id="4ecd0-194">VPN-Verbindungen in Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="4ecd0-194">VPN connections in Microsoft Intune</span></span>](vpn-connections-in-microsoft-intune.md)
