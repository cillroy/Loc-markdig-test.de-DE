---
title: "Die Einrichtung des Pro-App-VPN in Microsoft Intune für iOS-Geräte"
titleSuffix: Intune on Azure
description: "Geben Sie an, welche verwalteten Apps Ihr VPN auf mit Intune verwalteten iOS-Geräten verwenden können."
keywords: 
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 10/5/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: D9958CBF-34BF-41C2-A86C-28F832F87C94
ms.reviewer: karanda
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: c883ab2b96618502be20583908a4caa52ac5432b
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2017
---
# <a name="set-up-per-app-vpn-in-microsoft-intune-for-ios-devices"></a><span data-ttu-id="2851f-103">Die Einrichtung des Pro-App-VPN in Microsoft Intune für iOS-Geräte</span><span class="sxs-lookup"><span data-stu-id="2851f-103">Set up Per-App VPN in Microsoft Intune for iOS devices</span></span>

<span data-ttu-id="2851f-104">Sie können angeben, welche verwalteten Apps Ihr virtuelles privates Netzwerk (Virtual Private Network, VPN) auf mit Intune verwalteten iOS-Geräten verwenden können.</span><span class="sxs-lookup"><span data-stu-id="2851f-104">You can specify which managed apps can use your Virtual Private Network (VPN) on Intune managed iOS devices.</span></span> <span data-ttu-id="2851f-105">Wenn Sie ein Pro-App-VPN in Intune angeben, verbindet sich ein Benutzer automatisch über Ihr VPN, wenn dieser auf Unternehmensdokumente zugreift.</span><span class="sxs-lookup"><span data-stu-id="2851f-105">When you specify a Per-APP VPN in Intune, an end user automatically connects through your VPN when accessing corporate documents.</span></span>

## <a name="prerequisites-for-the-per-app-vpn"></a><span data-ttu-id="2851f-106">Voraussetzungen für das Pro-App-VPN</span><span class="sxs-lookup"><span data-stu-id="2851f-106">Prerequisites for the Per-App VPN</span></span>

<span data-ttu-id="2851f-107">Um ihre Identität nachzuweisen, zeigt der VPN-Server das Zertifikat an, das vom Gerät ohne Aufforderung akzeptiert werden muss.</span><span class="sxs-lookup"><span data-stu-id="2851f-107">To prove its identity, the VPN server presents the certificate that must be accepted without a prompt by the device.</span></span> <span data-ttu-id="2851f-108">Um die automatische Genehmigung des Zertifikats sicherzustellen, erstellen Sie ein vertrauenswürdiges Zertifikatprofil, das das durch die Zertifizierungsstelle (CA) ausgegebene Stammzertifikat des VPN-Servers enthält.</span><span class="sxs-lookup"><span data-stu-id="2851f-108">To ensure the automatic approval of the certificate, create a trusted certificate profile that contains the VPN server's root certificate issued by the Certificate Authority (CA).</span></span> 

<span data-ttu-id="2851f-109">Exportieren Sie das Zertifikat, und fügen Sie die CA hinzu.</span><span class="sxs-lookup"><span data-stu-id="2851f-109">Export the certificate and add the CA.</span></span>

1. <span data-ttu-id="2851f-110">Öffnen Sie die Verwaltungskonsole auf Ihrem VPN-Server.</span><span class="sxs-lookup"><span data-stu-id="2851f-110">Open the administration console on your VPN server.</span></span>
2. <span data-ttu-id="2851f-111">Überprüfen Sie, dass Ihr VPN-Server die zertifikatbasierte Authentifizierung verwendet.</span><span class="sxs-lookup"><span data-stu-id="2851f-111">Verify that your VPN server uses Certificate-based Authentication.</span></span> 
3. <span data-ttu-id="2851f-112">Exportieren Sie das vertrauenswürdige Zertifikat der Stammzertifizierungsstelle.</span><span class="sxs-lookup"><span data-stu-id="2851f-112">Export the trusted root certificate file.</span></span> <span data-ttu-id="2851f-113">Es verfügt über eine CER-Erweiterung, und Sie fügen es hinzu, wenn Sie ein vertrauenswürdiges Zertifikatprofil erstellen.</span><span class="sxs-lookup"><span data-stu-id="2851f-113">It has a .cer extension, and you add it when creating a trusted certificate profile.</span></span>
4. <span data-ttu-id="2851f-114">Fügen Sie den Namen der Zertifizierungsstelle hinzu, die das Zertifikat für die Authentifizierung an den VPN-Server ausgestellt hat.</span><span class="sxs-lookup"><span data-stu-id="2851f-114">Add the name of the CA that issued the certificate for authentication to the VPN server.</span></span>
    <span data-ttu-id="2851f-115">Wenn die vom Gerät vorgelegte Zertifizierungsstelle mit einer der CAs in der Liste der vertrauenswürdigen Zertifizierungsstellen auf dem VPN-Server übereinstimmt, dann authentifiziert der VPN-Server das Gerät erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="2851f-115">If the CA presented by the device matches one of the CAs in the Trusted CA list on the VPN server, then the VPN server successfully authenticates the device.</span></span>

## <a name="create-a--group-for-your-vpn-users"></a><span data-ttu-id="2851f-116">Erstellen einer Gruppe für Ihre VPN-Benutzer</span><span class="sxs-lookup"><span data-stu-id="2851f-116">Create a  group for your VPN users</span></span>

<span data-ttu-id="2851f-117">Erstellen oder wählen Sie eine vorhandene Gruppe in Azure Active Directory (Azure AD), die die Mitglieder enthalten soll, die Zugriff auf das Pro-App-VPN besitzen.</span><span class="sxs-lookup"><span data-stu-id="2851f-117">Create or choose an existing group in Azure Active Directory (Azure AD) to contain the members who have access to the per-App VPN.</span></span>

1. <span data-ttu-id="2851f-118">Öffnen Sie das Azure-Portal.</span><span class="sxs-lookup"><span data-stu-id="2851f-118">Open the Azure portal.</span></span> <span data-ttu-id="2851f-119">Wählen Sie **Weitere Dienste** > **Überwachung und Verwaltung** > **Intune** aus.</span><span class="sxs-lookup"><span data-stu-id="2851f-119">Choose **More Services** > **Monitoring + Management** > **Intune**.</span></span>
2. <span data-ttu-id="2851f-120">Wählen Sie **Gruppen** aus, und klicken Sie dann auf **Neue Gruppe**.</span><span class="sxs-lookup"><span data-stu-id="2851f-120">Choose **Groups** and click **New group**.</span></span>
3. <span data-ttu-id="2851f-121">Geben Sie den **Namen** der Gruppe ein.</span><span class="sxs-lookup"><span data-stu-id="2851f-121">Type the **Name** of the group.</span></span> 
4. <span data-ttu-id="2851f-122">Gibt die **Beschreibung** der Gruppe an.</span><span class="sxs-lookup"><span data-stu-id="2851f-122">Type the **Description** of the group.</span></span> 
5. <span data-ttu-id="2851f-123">Legen Sie den **Mitgliedschaftstyp** auf **Zugewiesen** fest.</span><span class="sxs-lookup"><span data-stu-id="2851f-123">Select **Assigned** for the **Membership type**.</span></span>
6. <span data-ttu-id="2851f-124">Wählen Sie für **Office-Features aktivieren?** die Option **Nein**.</span><span class="sxs-lookup"><span data-stu-id="2851f-124">Select **No** for **Enable Office features**.</span></span>
7. <span data-ttu-id="2851f-125">Suchen Sie auf dem Blatt **Mitglieder** nach dem VPN-Benutzer anhand dessen Namens oder E-Mail-Adresse.</span><span class="sxs-lookup"><span data-stu-id="2851f-125">Search for the VPN users by name or email address in the **Members** blade.</span></span>
8. <span data-ttu-id="2851f-126">Wählen Sie jeden Benutzer aus, und klicken Sie auf **Auswählen**.</span><span class="sxs-lookup"><span data-stu-id="2851f-126">Select each user and click **Select**.</span></span>
9. <span data-ttu-id="2851f-127">Klicken Sie auf **Erstellen**.</span><span class="sxs-lookup"><span data-stu-id="2851f-127">Click **Create**</span></span>

## <a name="create-a-trusted-certificate-profile"></a><span data-ttu-id="2851f-128">Erstellen eines vertrauenswürdigen Zertifikatprofils</span><span class="sxs-lookup"><span data-stu-id="2851f-128">Create a trusted certificate profile</span></span>

<span data-ttu-id="2851f-129">Importieren Sie das Stammzertifikat des VPN-Servers, das von der Zertifizierungsstelle ausgegeben wurde, in ein in Intune erstelltes Profil.</span><span class="sxs-lookup"><span data-stu-id="2851f-129">Import the VPN server's root certificate issued by the CA into a profile created in Intune.</span></span> <span data-ttu-id="2851f-130">Das Profil des vertrauenswürdigen Zertifikats weist das iOS-Gerät an, automatisch der CA zu vertrauen, die der VPN-Server präsentiert.</span><span class="sxs-lookup"><span data-stu-id="2851f-130">The trusted certificate profile instructs the iOS device to automatically trust the CA that the VPN server presents.</span></span>

1. <span data-ttu-id="2851f-131">Öffnen Sie das Azure-Portal.</span><span class="sxs-lookup"><span data-stu-id="2851f-131">Open the Azure portal.</span></span> <span data-ttu-id="2851f-132">Wählen Sie **Weitere Dienste** > **Überwachung und Verwaltung** > **Intune** aus.</span><span class="sxs-lookup"><span data-stu-id="2851f-132">Choose **More Services** > **Monitoring + Management** > **Intune**.</span></span>
2. <span data-ttu-id="2851f-133">Wählen Sie **Gerätekonfiguration** aus, und klicken Sie dann auf **Profile**.</span><span class="sxs-lookup"><span data-stu-id="2851f-133">Choose **Device configuration**, and then click **Profiles**.</span></span>
3. <span data-ttu-id="2851f-134">Klicken Sie auf **+ Profil erstellen**.</span><span class="sxs-lookup"><span data-stu-id="2851f-134">Click **+ Create profile**.</span></span> <span data-ttu-id="2851f-135">Führen Sie unter **Profil erstellen** Folgendes durch:</span><span class="sxs-lookup"><span data-stu-id="2851f-135">In **Create profile**:</span></span>
    1. <span data-ttu-id="2851f-136">Geben Sie den **Namen** ein.</span><span class="sxs-lookup"><span data-stu-id="2851f-136">Type the **Name**.</span></span>
    2. <span data-ttu-id="2851f-137">Geben Sie die **Beschreibung** ein.</span><span class="sxs-lookup"><span data-stu-id="2851f-137">Type the **Description**.</span></span>
    3. <span data-ttu-id="2851f-138">Wählen Sie **iOS** für die **Plattform** aus.</span><span class="sxs-lookup"><span data-stu-id="2851f-138">Select **iOS** for the **Platform**.</span></span>
    4. <span data-ttu-id="2851f-139">Wählen Sie **vertrauenswürdiges Zertifikat** für den **Profiltyp**.</span><span class="sxs-lookup"><span data-stu-id="2851f-139">Select **Trusted certificate** for the **Profile type**.</span></span>
4. <span data-ttu-id="2851f-140">Klicken Sie auf das Ordnersymbol, und navigieren Sie zu Ihrem VPN-Zertifikat (CER-Datei), das Sie von Ihrer VPN-Verwaltungskonsole exportiert haben.</span><span class="sxs-lookup"><span data-stu-id="2851f-140">Click the folder icon and browse to your VPN certificate (.cer file) that you exported from your VPN administration console.</span></span> <span data-ttu-id="2851f-141">Auf "OK" klicken</span><span class="sxs-lookup"><span data-stu-id="2851f-141">Click OK</span></span>
5. <span data-ttu-id="2851f-142">Klicken Sie auf **Erstellen**.</span><span class="sxs-lookup"><span data-stu-id="2851f-142">Click **Create**.</span></span>

    ![Erstellen eines vertrauenswürdigen Zertifikatprofils](media\vpn-per-app-create-trusted-cert.png)

## <a name="create-a-scep-certificate-profile"></a><span data-ttu-id="2851f-144">Erstellen eines SCEP-Zertifikatprofils</span><span class="sxs-lookup"><span data-stu-id="2851f-144">Create a SCEP certificate profile</span></span>

<span data-ttu-id="2851f-145">Das Profil des vertrauenswürdigen Stammzertifikats ermöglicht, dass iOS den VPN-Server automatisch als vertrauenswürdig einstuft.</span><span class="sxs-lookup"><span data-stu-id="2851f-145">The trusted root certificate profile allows the iOS to automatically trust the VPN Server.</span></span> <span data-ttu-id="2851f-146">Das SCEP-Zertifikat stellt Anmeldeinformationen aus dem iOS-VPN-Client an den VPN-Server bereit.</span><span class="sxs-lookup"><span data-stu-id="2851f-146">The SCEP certificate provides credentials from the iOS VPN client to the VPN server.</span></span> <span data-ttu-id="2851f-147">Das Zertifikat lässt zu, dass das Gerät im Hintergrund eine Authentifizierung durchführt, ohne dass das iOS-Gerät den Benutzer zur Eingabe eines Benutzernamens und Kennworts auffordert.</span><span class="sxs-lookup"><span data-stu-id="2851f-147">The certificate allows the device to silently authenticate without prompting the iOS devise user for a username and password.</span></span> 

1. <span data-ttu-id="2851f-148">Öffnen Sie das Azure-Portal.</span><span class="sxs-lookup"><span data-stu-id="2851f-148">Open the Azure portal.</span></span> <span data-ttu-id="2851f-149">Wählen Sie **Weitere Dienste** > **Überwachung und Verwaltung** > **Intune** aus.</span><span class="sxs-lookup"><span data-stu-id="2851f-149">Choose **More Services** > **Monitoring + Management** > **Intune**.</span></span> 
2. <span data-ttu-id="2851f-150">Wählen Sie **Gerätekonfiguration** aus, und klicken Sie dann auf **Profile**.</span><span class="sxs-lookup"><span data-stu-id="2851f-150">Choose **Device configuration**, and then click **Profiles**.</span></span>
3. <span data-ttu-id="2851f-151">Klicken Sie auf **+ Profil erstellen**.</span><span class="sxs-lookup"><span data-stu-id="2851f-151">Click **+ Create profile**.</span></span> <span data-ttu-id="2851f-152">Führen Sie unter **Profil erstellen** Folgendes durch:</span><span class="sxs-lookup"><span data-stu-id="2851f-152">In **Create profile**:</span></span>
    1. <span data-ttu-id="2851f-153">Geben Sie den **Namen** ein.</span><span class="sxs-lookup"><span data-stu-id="2851f-153">Type the **Name**.</span></span>
    2. <span data-ttu-id="2851f-154">Geben Sie die **Beschreibung** ein.</span><span class="sxs-lookup"><span data-stu-id="2851f-154">Type the **Description**.</span></span>
    3. <span data-ttu-id="2851f-155">Wählen Sie **iOS** für die **Plattform** aus.</span><span class="sxs-lookup"><span data-stu-id="2851f-155">Select **iOS** for the **Platform**.</span></span>
    4. <span data-ttu-id="2851f-156">Wählen Sie **SCEP-Zertifikat** für den **Profiltyp**.</span><span class="sxs-lookup"><span data-stu-id="2851f-156">Select **SCEP certificate** for the **Profile type**.</span></span>
4. <span data-ttu-id="2851f-157">Wählen Sie **Jahre** aus, und geben Sie `2` für **Gültigkeitsdauer des Zertifikats** an.</span><span class="sxs-lookup"><span data-stu-id="2851f-157">Select **Years** and type `2` for **Certificate validity period**.</span></span>
5. <span data-ttu-id="2851f-158">Wählen Sie **Allgemeiner Name** für **Format des Antragstellernamens** aus.</span><span class="sxs-lookup"><span data-stu-id="2851f-158">Select **Common name** for **Subject name format**.</span></span>
6. <span data-ttu-id="2851f-159">Wählen Sie **Benutzerprinzipalname (UPN)** für **Alternativer Antragstellername** aus.</span><span class="sxs-lookup"><span data-stu-id="2851f-159">Select **User principle name (UPN)** for **Subject alternative name**.</span></span>
7. <span data-ttu-id="2851f-160">Wählen Sie **Digitale Signatur** und **Schlüsselverschlüsselung** für **Schlüsselverwendung** aus.</span><span class="sxs-lookup"><span data-stu-id="2851f-160">Select **Digital signature** and **Key encipherment** for **Key usage**.</span></span>
8. <span data-ttu-id="2851f-161">Wählen Sie **2048** für **Schlüsselgröße (Bits)**.</span><span class="sxs-lookup"><span data-stu-id="2851f-161">Select **2048** for **Key size (bits)**.</span></span>
9. <span data-ttu-id="2851f-162">Klicken Sie auf „Stammzertifikat“, und wählen Sie ein SCEP-Zertifikat.</span><span class="sxs-lookup"><span data-stu-id="2851f-162">Click Root Certificate and select a SCEP certificate.</span></span> <span data-ttu-id="2851f-163">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="2851f-163">Click **OK**.</span></span>
10. <span data-ttu-id="2851f-164">Geben Sie unter **Name** für **Erweiterte Schlüsselverwendung** `Client Authentication` ein.</span><span class="sxs-lookup"><span data-stu-id="2851f-164">Type `Client Authentication` in **Name** for **Extended key usage**.</span></span>
11. <span data-ttu-id="2851f-165">Geben Sie unter **Objektkennung** `1.3.6.1.5.5.7.3.2` ein.</span><span class="sxs-lookup"><span data-stu-id="2851f-165">Type `1.3.6.1.5.5.7.3.2` in **Object Identifier**.</span></span>
12. <span data-ttu-id="2851f-166">Klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="2851f-166">Click **Add**.</span></span>
13. <span data-ttu-id="2851f-167">Geben Sie die ***Server-URL*** ein, und klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="2851f-167">Type the ***Server URL*** and click **Add**.</span></span>
14. <span data-ttu-id="2851f-168">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="2851f-168">Click **OK**.</span></span>
15. <span data-ttu-id="2851f-169">Klicken Sie auf **Erstellen**.</span><span class="sxs-lookup"><span data-stu-id="2851f-169">Click **Create**.</span></span>

    ![Erstellen eines SCEP-Zertifikatprofils](media\vpn-per-app-create-scep-cert.png)

## <a name="create-a-per-app-vpn-profile"></a><span data-ttu-id="2851f-171">Erstellen eines Pro-App-VPN-Profils</span><span class="sxs-lookup"><span data-stu-id="2851f-171">Create a Per-App VPN profile</span></span>

<span data-ttu-id="2851f-172">Das VPN-Profil enthält das SCEP-Zertifikat, das die Anmeldeinformationen des Clients, die Verbindungsinformationen für das VPN und das Pro-App-VPN-Flag enthält. So können Sie die Pro-App-VPN-Funktion für den Gebrauch durch die iOS-Anwendung aktivieren.</span><span class="sxs-lookup"><span data-stu-id="2851f-172">The VPN profile contains the SCEP certificate carrying the client credentials, the connection information to the VPN, and the Per APP VPN flag to enable the Per App VPN feature for use by the iOS application.</span></span>

1. <span data-ttu-id="2851f-173">Öffnen Sie das Azure-Portal.</span><span class="sxs-lookup"><span data-stu-id="2851f-173">Open the Azure portal.</span></span> <span data-ttu-id="2851f-174">Wählen Sie **Weitere Dienste** > **Überwachung und Verwaltung** > **Intune** aus.</span><span class="sxs-lookup"><span data-stu-id="2851f-174">Choose **More Services** > **Monitoring + Management** > **Intune**.</span></span>
2. <span data-ttu-id="2851f-175">Wählen Sie **Gerätekonfiguration** aus, und klicken Sie dann auf **Profile**.</span><span class="sxs-lookup"><span data-stu-id="2851f-175">Choose **Device configuration**, and then click **Profiles**.</span></span>
3. <span data-ttu-id="2851f-176">Klicken Sie auf **+ Profil erstellen**.</span><span class="sxs-lookup"><span data-stu-id="2851f-176">Click **+ Create profile**.</span></span> <span data-ttu-id="2851f-177">Führen Sie unter **Profil erstellen** Folgendes durch:</span><span class="sxs-lookup"><span data-stu-id="2851f-177">In **Create profile**:</span></span>
    1. <span data-ttu-id="2851f-178">Geben Sie den **Namen** ein.</span><span class="sxs-lookup"><span data-stu-id="2851f-178">Type the **Name**.</span></span>
    2. <span data-ttu-id="2851f-179">Geben Sie die **Beschreibung** ein.</span><span class="sxs-lookup"><span data-stu-id="2851f-179">Type the **Description**.</span></span>
    3. <span data-ttu-id="2851f-180">Wählen Sie **iOS** für die **Plattform** aus.</span><span class="sxs-lookup"><span data-stu-id="2851f-180">Select **iOS** for the **Platform**.</span></span>
    4. <span data-ttu-id="2851f-181">Wählen Sie **VPN** für den **Profiltyp** aus.</span><span class="sxs-lookup"><span data-stu-id="2851f-181">Select **VPN** for the **Profile type**.</span></span>
4. <span data-ttu-id="2851f-182">Wählen Sie **Basis-VPN** aus.</span><span class="sxs-lookup"><span data-stu-id="2851f-182">Select **Base VPN**.</span></span> <span data-ttu-id="2851f-183">Gehen Sie unter **Basis-VPN** wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="2851f-183">In **Base VPN**:</span></span>
    1. <span data-ttu-id="2851f-184">Geben Sie den **Verbindungsnamen** ein.</span><span class="sxs-lookup"><span data-stu-id="2851f-184">Type the **Connection name**.</span></span>
    2. <span data-ttu-id="2851f-185">Geben Sie die **IP-Adresse oder FQDN** ein.</span><span class="sxs-lookup"><span data-stu-id="2851f-185">Type the **IP address or FQDN**.</span></span>
    3. <span data-ttu-id="2851f-186">Wählen Sie **Zertifikate** für die **Authentifizierungsmethode** aus.</span><span class="sxs-lookup"><span data-stu-id="2851f-186">Select **Certificates** for the **Authentication method**.</span></span>
    4. <span data-ttu-id="2851f-187">Wählen Sie das SCEP-Zertifikat unter **Authentifizierungszertifikat**, und klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="2851f-187">Select the SCEP certificate under **Authentication certificate** and click **OK**.</span></span>
    5. <span data-ttu-id="2851f-188">Wählen Sie Ihr VPN für den **Verbindungstyp** aus.</span><span class="sxs-lookup"><span data-stu-id="2851f-188">Select your VPN for the **Connection type**.</span></span>
    6. <span data-ttu-id="2851f-189">Konfigurieren Sie bei Bedarf die Attribute für das VPN.</span><span class="sxs-lookup"><span data-stu-id="2851f-189">If necessary, configure the attributes for your VPN.</span></span>
    7. <span data-ttu-id="2851f-190">Wählen Sie „Tunneln“ für **Disable Split** (Teilen deaktivieren) aus.</span><span class="sxs-lookup"><span data-stu-id="2851f-190">Select for **Disable Split** tunneling.</span></span>
5. <span data-ttu-id="2851f-191">Klicken Sie auf **Automatisches VPN**.</span><span class="sxs-lookup"><span data-stu-id="2851f-191">Click **Automatic VPN**.</span></span> <span data-ttu-id="2851f-192">Führen Sie unter **Automatisches VPN** Folgendes durch:</span><span class="sxs-lookup"><span data-stu-id="2851f-192">In **Automatic VPN**:</span></span>
    1. <span data-ttu-id="2851f-193">Wählen Sie **Pro-App-VPN** für den **Typ des automatischen VPN** aus.</span><span class="sxs-lookup"><span data-stu-id="2851f-193">Select **Per-App VPN** for the **Type of automatic VPN**.</span></span>
    2. <span data-ttu-id="2851f-194">Geben Sie die URL für das VPN ein, und klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="2851f-194">Type the URL for the VPN and click **Add**.</span></span>
    3. <span data-ttu-id="2851f-195">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="2851f-195">Click **OK**.</span></span>
6. <span data-ttu-id="2851f-196">Klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="2851f-196">Click **OK**.</span></span>
7. <span data-ttu-id="2851f-197">Klicken Sie auf **Erstellen**.</span><span class="sxs-lookup"><span data-stu-id="2851f-197">Click **Create**.</span></span>

    ![Erstellen eines Pro-App-VPN-Profils](media\vpn-per-app-create-vpn-profile.png)


## <a name="associate-an-app-with-the-vpn-profile"></a><span data-ttu-id="2851f-199">Ordnen Sie dem VPN-Profil eine App zu.</span><span class="sxs-lookup"><span data-stu-id="2851f-199">Associate an app with the VPN profile</span></span>

<span data-ttu-id="2851f-200">Nachdem Sie Ihr VPN-Profil hinzugefügt haben, ordnen Sie die App und Azure AD-Gruppe dem Profil zu.</span><span class="sxs-lookup"><span data-stu-id="2851f-200">After adding your VPN profile, associate the app and Azure AD group to the profile.</span></span>

1. <span data-ttu-id="2851f-201">Öffnen Sie das Azure-Portal.</span><span class="sxs-lookup"><span data-stu-id="2851f-201">Open the Azure portal.</span></span> <span data-ttu-id="2851f-202">Wählen Sie **Weitere Dienste** > **Überwachung und Verwaltung** > **Intune** aus.</span><span class="sxs-lookup"><span data-stu-id="2851f-202">Choose **More Services** > **Monitoring + Management** > **Intune**.</span></span>
2. <span data-ttu-id="2851f-203">Wählen Sie **Mobile Apps** aus.</span><span class="sxs-lookup"><span data-stu-id="2851f-203">Choose **Mobile Apps**.</span></span>
3. <span data-ttu-id="2851f-204">Klicken Sie auf **Apps**.</span><span class="sxs-lookup"><span data-stu-id="2851f-204">Click **Apps**.</span></span>
4. <span data-ttu-id="2851f-205">Wählen Sie die App aus der Liste der Apps aus.</span><span class="sxs-lookup"><span data-stu-id="2851f-205">Select the app from the list of apps.</span></span>
5. <span data-ttu-id="2851f-206">Klicken Sie auf **Zuweisungen**.</span><span class="sxs-lookup"><span data-stu-id="2851f-206">Click **Assignments.**</span></span>
6. <span data-ttu-id="2851f-207">Klicken Sie auf **Gruppen auswählen**, und wählen Sie anschließend die Gruppe aus, die Sie zuvor definiert haben.</span><span class="sxs-lookup"><span data-stu-id="2851f-207">Click **Select groups**, select the group you defined earlier.</span></span> <span data-ttu-id="2851f-208">Klicken Sie auf **Auswählen**.</span><span class="sxs-lookup"><span data-stu-id="2851f-208">Click **Select**.</span></span>
7. <span data-ttu-id="2851f-209">Wählen Sie für den **Typ** auf dem Blatt **Zuweisungen** die Option **Erforderlich** aus.</span><span class="sxs-lookup"><span data-stu-id="2851f-209">Select **Required** for the **Type** in the **Assignments** blade.</span></span>
8. <span data-ttu-id="2851f-210">Wählen Sie Ihre VPN-Definition für die **VPNS** aus.</span><span class="sxs-lookup"><span data-stu-id="2851f-210">Select your VPN definition for the **VPNS**.</span></span>
 
    > [!NOTE]  
    > <span data-ttu-id="2851f-211">In einigen Fällen benötigt die VPN-Definition bis zu einer Minute, um den Wert abzurufen.</span><span class="sxs-lookup"><span data-stu-id="2851f-211">Sometimes the VPN definition takes up to a minute to retrieve the value.</span></span> <span data-ttu-id="2851f-212">Warten Sie etwa 3–5 Minuten, bevor Sie auf **Speichern** klicken.</span><span class="sxs-lookup"><span data-stu-id="2851f-212">Wait for 3-5 minutes before your click **Save**.</span></span>

9. <span data-ttu-id="2851f-213">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="2851f-213">Click **Save**.</span></span>

    ![Zuordnen einer App zu einem VPN](media\vpn-per-app-app-to-vpn.png)

## <a name="verify-the-connection-on-the-ios-device"></a><span data-ttu-id="2851f-215">Überprüfen der Verbindung auf dem iOS-Gerät</span><span class="sxs-lookup"><span data-stu-id="2851f-215">Verify the connection on the iOS device</span></span>

<span data-ttu-id="2851f-216">Sobald Ihr App-bezogenes VPN eingerichtet und Ihrer App zugeordnet ist, überprüfen Sie, ob die Verbindung von einem Gerät aus funktioniert.</span><span class="sxs-lookup"><span data-stu-id="2851f-216">With your Per-App VPN set-up and associated with your app, verify the connection works from a device.</span></span>

### <a name="before-you-attempt-to-connect"></a><span data-ttu-id="2851f-217">Bevor Sie eine Verbindung herstellen</span><span class="sxs-lookup"><span data-stu-id="2851f-217">Before you attempt to connect</span></span>

 - <span data-ttu-id="2851f-218">stellen Sie sicher, dass iOS 7 oder höher ausgeführt wird</span><span class="sxs-lookup"><span data-stu-id="2851f-218">Make sure you’re running iOS 7 or later.</span></span>
 - <span data-ttu-id="2851f-219">stellen Sie sicher, dass Sie *alle* der oben erwähnten Richtlinien derselben Gruppe von Benutzern bereitstellen</span><span class="sxs-lookup"><span data-stu-id="2851f-219">Make sure you deploy *all* of the above mentioned policies to the same group of users.</span></span> <span data-ttu-id="2851f-220">Wenn Sie nicht so vorgehen, wird wahrscheinlich die Servicequalität des App-bezogenen VPN beeinträchtigt.</span><span class="sxs-lookup"><span data-stu-id="2851f-220">Failure to do so will most definitely break the Per-App VPN experience.</span></span>  
 - <span data-ttu-id="2851f-221">stellen Sie sicher, dass Sie die unterstützende Drittanbieter-VPN-App installiert haben</span><span class="sxs-lookup"><span data-stu-id="2851f-221">Makes sure you have the supported third-party VPN app installed.</span></span> <span data-ttu-id="2851f-222">Die folgenden VPN-Apps werden unterstützt:</span><span class="sxs-lookup"><span data-stu-id="2851f-222">The following VPN apps are supported:</span></span>
    - <span data-ttu-id="2851f-223">Pulse Secure</span><span class="sxs-lookup"><span data-stu-id="2851f-223">Pulse Secure</span></span>
    - <span data-ttu-id="2851f-224">Checkpoint</span><span class="sxs-lookup"><span data-stu-id="2851f-224">Checkpoint</span></span>
    - <span data-ttu-id="2851f-225">F5</span><span class="sxs-lookup"><span data-stu-id="2851f-225">F5</span></span>
    - <span data-ttu-id="2851f-226">SonicWall</span><span class="sxs-lookup"><span data-stu-id="2851f-226">SonicWall</span></span>

### <a name="connect-using-the-per-app-vpn"></a><span data-ttu-id="2851f-227">Herstellen einer Verbindung mithilfe des App-bezogenen VPNs</span><span class="sxs-lookup"><span data-stu-id="2851f-227">Connect using the Per-App VPN</span></span>

<span data-ttu-id="2851f-228">Überprüfen Sie die Zero Touch-Funktion, indem Sie eine Verbindung herstellen, ohne dabei das VPN auswählen oder Ihre Anmeldeinformationen eingeben zu müssen.</span><span class="sxs-lookup"><span data-stu-id="2851f-228">Verify the zero-touch experience by connecting without having to select the VPN or type your credentials.</span></span> <span data-ttu-id="2851f-229">Die Zero Touch-Funktion bedeutet Folgendes:</span><span class="sxs-lookup"><span data-stu-id="2851f-229">The zero-touch experience means:</span></span>

 - <span data-ttu-id="2851f-230">Das Gerät fordert Sie nicht auf, dem VPN-Server zu vertrauen.</span><span class="sxs-lookup"><span data-stu-id="2851f-230">The device does not ask you to trust the VPN server.</span></span> <span data-ttu-id="2851f-231">Sie sehen aber dennoch das Dialogfeld **Dynamic Trust** (Dynamische Vertrauensstellung).</span><span class="sxs-lookup"><span data-stu-id="2851f-231">That is, you do see the **Dynamic Trust** dialog box.</span></span>
 - <span data-ttu-id="2851f-232">Sie müssen keine Anmeldeinformationen eingeben.</span><span class="sxs-lookup"><span data-stu-id="2851f-232">You do not have to type credentials.</span></span>
 - <span data-ttu-id="2851f-233">Sie werden mit dem VPN nach Tippen auf die korrekte Schaltfläche verbunden.</span><span class="sxs-lookup"><span data-stu-id="2851f-233">You are connected to the VPN after tapping the connect button.</span></span>

<span data-ttu-id="2851f-234">Überprüfen Sie die Verbindung auf dem iOS-Gerät.</span><span class="sxs-lookup"><span data-stu-id="2851f-234">Verify the connection on an iOS device.</span></span>

1. <span data-ttu-id="2851f-235">Tippen Sie auf die VPN-App.</span><span class="sxs-lookup"><span data-stu-id="2851f-235">Tap the VPN app.</span></span>
2. <span data-ttu-id="2851f-236">Tippen Sie auf **Verbinden**.</span><span class="sxs-lookup"><span data-stu-id="2851f-236">Tap on **Connect**.</span></span>  
<span data-ttu-id="2851f-237">Das VPN stellt ohne weitere Aufforderungen erfolgreich eine Verbindung her.</span><span class="sxs-lookup"><span data-stu-id="2851f-237">The VPN successfully connects without any extra prompts.</span></span>

<!-- ## Troubleshooting the Per-App VPN

The user experiences the feature by silently connecting to the VPN. This experience, however, can provide little information for troubleshooting. You can review the event logs crated by the iOS device.

`Note -- use the Apple Configurator as the supported tool. Only runs on a mac.'

To review event logs:

1. Connect your iOS device to a PC
2. Open the **iPhone Configuration Utility** (IPCU). If you do not have a copy, you can install it from [CompatCenter](http://www.microsoft.com/en-us/windows/compatibility/CompatCenter/ProductDetailsViewer?Name=iPhone%20Configuration%20Utility&vendor=Apple&Locale=1033%2C2057%2C3081%2C4105%2C16393&ModelOrVersion=3&BreadCrumbPath=iphone%20configuration%20utility&LastSearchTerm=iphone%2Bconfiguration%2Butility&Type=Software&tempOsid=Windows%208.1)
3. Review the logs. -->

## <a name="next-steps"></a><span data-ttu-id="2851f-238">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="2851f-238">Next steps</span></span>

- <span data-ttu-id="2851f-239">Um die iOS-Einstellungen zu überprüfen, gehen Sie unter [VPN-Einstellungen für iOS-Geräte in Microsoft Intune](vpn-settings-ios.md).</span><span class="sxs-lookup"><span data-stu-id="2851f-239">To review iOS settings, see [VPN settings for iOS devices in Microsoft Intune](vpn-settings-ios.md).</span></span>
-  <span data-ttu-id="2851f-240">Weitere Informationen zur VPN-Einstellung und Intune finden Sie unter [Konfigurieren von VPN-Einstellungen in Microsoft Intune](vpn-settings-configure.md).</span><span class="sxs-lookup"><span data-stu-id="2851f-240">To learn more about VPN setting and Intune, see [How to configure VPN settings in Microsoft Intune](vpn-settings-configure.md).</span></span>