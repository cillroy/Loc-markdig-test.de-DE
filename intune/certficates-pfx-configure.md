---
title: Konfigurieren und Verwalten von PKCS-Zertifikaten mit Intune
titleSuffix: Intune on Azure
description: "Erstellen und weisen Sie PKCS-Zertifikate mit Intune zu.“"
keywords: 
author: MicrosoftGuyJFlo
ms.author: joflore
manager: angrobe
ms.date: 12/09/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 2f4dda4b4972b2a715ce956c0212a8ff06dc9c0f
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2017
---
# <a name="configure-and-manage-pkcs-certificates-with-intune"></a><span data-ttu-id="fb5c3-103">Konfigurieren und Verwalten von PKCS-Zertifikaten mit Intune</span><span class="sxs-lookup"><span data-stu-id="fb5c3-103">Configure and manage PKCS certificates with Intune</span></span>

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

## <a name="requirements"></a><span data-ttu-id="fb5c3-104">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="fb5c3-104">Requirements</span></span>

<span data-ttu-id="fb5c3-105">Um PKCS-Zertifikate mit Intune zu verwenden, müssen Sie über folgende Infrastruktur verfügen:</span><span class="sxs-lookup"><span data-stu-id="fb5c3-105">To use PKCS certificates with Intune, you must have the following infrastructure:</span></span>

* <span data-ttu-id="fb5c3-106">Eine vorhandene konfigurierte AD DS-Domäne (Active Directory Domain Services).</span><span class="sxs-lookup"><span data-stu-id="fb5c3-106">An existing Active Directory Domain Services (AD DS) domain configured.</span></span>
 
  <span data-ttu-id="fb5c3-107">Weitere Informationen zur Installation und Konfiguration von AD DS finden Sie im Artikel [AD DS-Entwurf und Planung](https://docs.microsoft.com/windows-server/identity/ad-ds/plan/ad-ds-design-and-planning).</span><span class="sxs-lookup"><span data-stu-id="fb5c3-107">If you need more information about how to install and configure AD DS see the article [AD DS Design and Planning](https://docs.microsoft.com/windows-server/identity/ad-ds/plan/ad-ds-design-and-planning).</span></span>

* <span data-ttu-id="fb5c3-108">Eine vorhandene konfigurierte Unternehmenszertifizierungsstelle.</span><span class="sxs-lookup"><span data-stu-id="fb5c3-108">An existing Enterprise Certification Authority (CA) configured.</span></span>

  <span data-ttu-id="fb5c3-109">Weitere Informationen zum Installieren und Konfigurieren von Active Directory-Zertifikatdiensten (AD CS) finden Sie im Artikel [Schrittweise Anleitung zu den Windows Server Active Directory-Zertifikatdiensten](https://technet.microsoft.com/library/cc772393).</span><span class="sxs-lookup"><span data-stu-id="fb5c3-109">If you need more information about how to install and configure Active Directory Certificate Services (AD CS) see the article [Active Directory Certificate Services Step-by-Step Guide](https://technet.microsoft.com/library/cc772393).</span></span>

  > [!WARNING]
  > <span data-ttu-id="fb5c3-110">Für Intune müssen AD CS mit einer Unternehmenszertifizierungsstelle, nicht mit einer eigenständigen Zertifizierungsstelle ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="fb5c3-110">Intune requires you to run AD CS with an Enterprise Certification Authority (CA), not a Standalone CA.</span></span>

* <span data-ttu-id="fb5c3-111">Ein Client mit Konnektivität zur Unternehmenszertifizierungsstelle.</span><span class="sxs-lookup"><span data-stu-id="fb5c3-111">A client that has connectivity to the Enterprise CA.</span></span>
* <span data-ttu-id="fb5c3-112">Eine exportierte Kopie Ihres Stammzertifikats aus Ihrer Unternehmenszertifizierungsstelle.</span><span class="sxs-lookup"><span data-stu-id="fb5c3-112">An exported copy of your root certificate from your Enterprise CA.</span></span>
* <span data-ttu-id="fb5c3-113">Der Microsoft Intune Certificate Connector (NDESConnectorSetup.exe) muss aus dem Intune-Portal heruntergeladen worden sein.</span><span class="sxs-lookup"><span data-stu-id="fb5c3-113">The Microsoft Intune Certificate Connector (NDESConnectorSetup.exe) downloaded from your Intune Portal.</span></span>
* <span data-ttu-id="fb5c3-114">Eine verfügbare Windows Server-Instanz zum Hosten des Microsoft Intune Certificate Connectors (NDESConnectorSetup.exe).</span><span class="sxs-lookup"><span data-stu-id="fb5c3-114">A Windows Server available to host the Microsoft Intune Certificate Connector (NDESConnectorSetup.exe).</span></span>

## <a name="export-the-root-certificate-from-the-enterprise-ca"></a><span data-ttu-id="fb5c3-115">Exportieren des Stammzertifikats aus der Unternehmenszertifizierungsstelle</span><span class="sxs-lookup"><span data-stu-id="fb5c3-115">Export the root certificate from the Enterprise CA</span></span>

<span data-ttu-id="fb5c3-116">Sie benötigen auf jedem Gerät ein Zertifikat einer Stamm- oder Zwischenzertifizierungsstelle für die Authentifizierung bei VPN, WLAN und anderen Ressourcen.</span><span class="sxs-lookup"><span data-stu-id="fb5c3-116">You need a root or intermediate CA certificate on each device for authentication with VPN, WiFi, and other resources.</span></span> <span data-ttu-id="fb5c3-117">Die folgenden Schritte erläutern, wie das erforderliche Zertifikat von Ihrer Unternehmenszertifizierungsstelle abgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="fb5c3-117">The following steps explain how to get the required certificate from your Enterprise CA.</span></span>

1. <span data-ttu-id="fb5c3-118">Melden Sie sich bei Ihrer Unternehmenszertifizierungsstelle mit einem Konto an, das über Administratorrechte verfügt.</span><span class="sxs-lookup"><span data-stu-id="fb5c3-118">Log in to your Enterprise CA with an account that has administrative privileges.</span></span>
2. <span data-ttu-id="fb5c3-119">Öffnen Sie eine Eingabeaufforderung als Administrator.</span><span class="sxs-lookup"><span data-stu-id="fb5c3-119">Open a command prompt as an administrator.</span></span>
3. <span data-ttu-id="fb5c3-120">Exportieren Sie das Zertifikat der Stammzertifizierungsstelle an einen Speicherort, an dem Sie später darauf zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="fb5c3-120">Export the Root CA Certificate to a location where you can access it later.</span></span>

   <span data-ttu-id="fb5c3-121">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="fb5c3-121">For example:</span></span>

4.  <span data-ttu-id="fb5c3-122">Nach Abschluss des Assistenten, jedoch vor dem Schließen des Assistenten, klicken Sie auf **Zertifikatconnector-Benutzeroberfläche starten**.</span><span class="sxs-lookup"><span data-stu-id="fb5c3-122">After the wizard completes, but before closing the wizard, click **Launch the Certificate Connector UI**.</span></span>

   `certutil -ca.cert certnew.cer`

   <span data-ttu-id="fb5c3-123">Weitere Informationen finden Sie unter [Certutil-Tasks zum Verwalten von Zertifikaten](https://technet.microsoft.com/library/cc772898.aspx#BKMK_ret_sign).</span><span class="sxs-lookup"><span data-stu-id="fb5c3-123">For more information, see [Certutil tasks for managing certificates](https://technet.microsoft.com/library/cc772898.aspx#BKMK_ret_sign).</span></span>

## <a name="configure-certificate-templates-on-the-certification-authority"></a><span data-ttu-id="fb5c3-124">Konfigurieren von Zertifikatvorlagen für die Zertifizierungsstelle</span><span class="sxs-lookup"><span data-stu-id="fb5c3-124">Configure certificate templates on the certification authority</span></span>

1. <span data-ttu-id="fb5c3-125">Melden Sie sich bei Ihrer Unternehmenszertifizierungsstelle mit einem Konto an, das über Administratorrechte verfügt.</span><span class="sxs-lookup"><span data-stu-id="fb5c3-125">Log in to your Enterprise CA with an account that has administrative privileges.</span></span>
2. <span data-ttu-id="fb5c3-126">Öffnen Sie die Konsole der **Zertifizierungsstelle**.</span><span class="sxs-lookup"><span data-stu-id="fb5c3-126">Open the **Certification Authority** console.</span></span>
3. <span data-ttu-id="fb5c3-127">Klicken Sie mit der rechten Maustaste auf **Zertifikatvorlagen**, und wählen Sie **Verwalten**.</span><span class="sxs-lookup"><span data-stu-id="fb5c3-127">Right-click **Certificate Templates** and choose **Manage**.</span></span>
4. <span data-ttu-id="fb5c3-128">Suchen Sie die Zertifikatvorlage **Benutzer**, klicken Sie mit der rechten Maustaste darauf, und wählen Sie **Vorlage duplizieren**.</span><span class="sxs-lookup"><span data-stu-id="fb5c3-128">Locate the **User** certificate template, right-click it and choose **Duplicate Template**.</span></span> <span data-ttu-id="fb5c3-129">Das Fenster **Eigenschaften der neuen Vorlage** wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="fb5c3-129">A window opens, **Properties of New Template**.</span></span>
5. <span data-ttu-id="fb5c3-130">Auf der Registerkarte **Kompatibilität**:</span><span class="sxs-lookup"><span data-stu-id="fb5c3-130">On the **Compatibility** tab</span></span>
   * <span data-ttu-id="fb5c3-131">Legen Sie **Zertifizierungsstelle** auf **Windows Server 2008 R2** fest.</span><span class="sxs-lookup"><span data-stu-id="fb5c3-131">Set **Certification Authority** to **Windows Server 2008 R2**</span></span>
   * <span data-ttu-id="fb5c3-132">Legen Sie **Zertifizierungsstelle** auf **Windows 7/Server 2008 R2** fest.</span><span class="sxs-lookup"><span data-stu-id="fb5c3-132">Set **Certificate recipient** to **Windows 7 / Server 2008 R2**</span></span>
6. <span data-ttu-id="fb5c3-133">Auf der Registerkarte **Allgemein** :</span><span class="sxs-lookup"><span data-stu-id="fb5c3-133">On the **General** tab:</span></span>
   * <span data-ttu-id="fb5c3-134">Legen Sie für **Vorlagenanzeigename** einen für Sie aussagekräftigen Namen fest.</span><span class="sxs-lookup"><span data-stu-id="fb5c3-134">Set **Template display name** to something meaningful to you.</span></span>

   > [!WARNING]
   > <span data-ttu-id="fb5c3-135">**Vorlagenname** entspricht standardmäßig dem **Vorlagenanzeigenamen** *ohne Leerzeichen*.</span><span class="sxs-lookup"><span data-stu-id="fb5c3-135">**Template name** by default is the same as **Template display name** with *no spaces*.</span></span> <span data-ttu-id="fb5c3-136">Notieren Sie sich den Vorlagennamen zur späteren Verwendung.</span><span class="sxs-lookup"><span data-stu-id="fb5c3-136">Note the template name for later use.</span></span>

7. <span data-ttu-id="fb5c3-137">Aktivieren Sie auf der Registerkarte **Anforderungsverarbeitung** das Kontrollkästchen **Exportieren von privatem Schlüssel zulassen**.</span><span class="sxs-lookup"><span data-stu-id="fb5c3-137">On the **Request Handling** tab, check the **Allow private key to be exported** box.</span></span>
8. <span data-ttu-id="fb5c3-138">Bestätigen Sie auf der Registerkarte **Kryptografie**, dass die **Minimale Schlüsselgröße** auf 2048 festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="fb5c3-138">On the **Cryptography** tab, confirm that the **Minimum key size** is set to 2048.</span></span>
9. <span data-ttu-id="fb5c3-139">Wählen Sie auf der Registerkarte **Antragstellername** das Optionsfeld **Informationen werden in der Anforderung angegeben**.</span><span class="sxs-lookup"><span data-stu-id="fb5c3-139">On the **Subject Name** tab, choose the radio button **Supply in the request**.</span></span>
10. <span data-ttu-id="fb5c3-140">Überprüfen Sie auf der Registerkarte **Erweiterungen**, dass „Verschlüsselndes Dateisystem“, „Sichere E-Mail“ und „Clientauthentifizierung“ unter **Anwendungsrichtlinien** angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="fb5c3-140">On the **Extensions** tab, confirm that you see Encrypting File System, Secure Email, and Client Authentication under **Application Policies**.</span></span>
    
      > [!IMPORTANT]
      > <span data-ttu-id="fb5c3-141">Bearbeiten Sie für iOS- und macOS-Zertifikatvorlagen auf der Registerkarte **Erweiterungen** die Option **Schlüsselverwendung**, und stellen Sie sicher, dass die Option **Signatur ist Ursprungsnachweis** nicht aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="fb5c3-141">For iOS and macOS certificate templates, on the **Extensions** tab, edit **Key Usage** and ensure that **Signature is proof of origin** is not selected.</span></span>

11. <span data-ttu-id="fb5c3-142">Fügen Sie auf der Registerkarte **Sicherheit** das Computerkonto für den Server hinzu, auf dem Sie den Microsoft Intune Certificate Connector installieren.</span><span class="sxs-lookup"><span data-stu-id="fb5c3-142">On the **Security** tab, add the Computer Account for the server where you install the Microsoft Intune Certificate Connector.</span></span>
    * <span data-ttu-id="fb5c3-143">Weisen Sie diesem Konto die Berechtigungen **Lesen** und **Registrieren** zu.</span><span class="sxs-lookup"><span data-stu-id="fb5c3-143">Allow this account **Read** and **Enroll** permissions.</span></span>
12. <span data-ttu-id="fb5c3-144">Klicken Sie auf **Anwenden**, und klicken Sie dann auf **OK**, um die Zertifikatvorlage zu speichern.</span><span class="sxs-lookup"><span data-stu-id="fb5c3-144">Click **Apply**, then click **OK** to save the certificate template.</span></span>
13. <span data-ttu-id="fb5c3-145">Schließen Sie die **Zertifikatvorlagenkonsole**.</span><span class="sxs-lookup"><span data-stu-id="fb5c3-145">Close the **Certificate Templates Console**.</span></span>
14. <span data-ttu-id="fb5c3-146">Klicken Sie in der Konsole der **Zertifizierungsstelle** mit der rechten Maustaste auf **Zertifikatvorlagen**, und klicken Sie dann auf **Neu** und auf **Auszustellende Zertifikatvorlage**.</span><span class="sxs-lookup"><span data-stu-id="fb5c3-146">From the **Certification Authority** console, right-click **Certificate Templates**, **New**, **Certificate Template to Issue**.</span></span>
    * <span data-ttu-id="fb5c3-147">Wählen Sie die Vorlage, die Sie in den vorherigen Schritten erstellt haben, und klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="fb5c3-147">Choose the template that you created in the preceding steps and click **OK**.</span></span>
15. <span data-ttu-id="fb5c3-148">Gehen Sie folgendermaßen vor, damit der Server Zertifikate im Namen von bei Intune registrierten Geräten und Benutzern verwaltet:</span><span class="sxs-lookup"><span data-stu-id="fb5c3-148">For the server to manage certificates on behalf of Intune enrolled devices and users, follow these steps:</span></span>

    <span data-ttu-id="fb5c3-149">a.</span><span class="sxs-lookup"><span data-stu-id="fb5c3-149">a.</span></span> <span data-ttu-id="fb5c3-150">Klicken Sie mit der rechten Maustaste auf die Zertifizierungsstelle, und wählen Sie **Eigenschaften**.</span><span class="sxs-lookup"><span data-stu-id="fb5c3-150">Right-click the Certification Authority, choose **Properties**.</span></span>

    <span data-ttu-id="fb5c3-151">b.</span><span class="sxs-lookup"><span data-stu-id="fb5c3-151">b.</span></span> <span data-ttu-id="fb5c3-152">Fügen Sie auf der Registerkarte „Sicherheit“ das Computerkonto des Servers hinzu, auf dem Sie den Microsoft Intune Certificate Connector ausführen.</span><span class="sxs-lookup"><span data-stu-id="fb5c3-152">On the security tab, add the Computer account of the server where you run the Microsoft Intune Certificate Connector.</span></span>
      * <span data-ttu-id="fb5c3-153">Erteilen Sie dem Computerkonto die Zulassungsberechtigungen **Zertifikate ausstellen und verwalten** und **Zertifikate anfordern**.</span><span class="sxs-lookup"><span data-stu-id="fb5c3-153">Grant **Issue and Manage Certificates** and **Request Certificates** Allow permissions to the computer account.</span></span>
16. <span data-ttu-id="fb5c3-154">Melden Sie sich von der Unternehmenszertifizierungsstelle ab.</span><span class="sxs-lookup"><span data-stu-id="fb5c3-154">Log out of the Enterprise CA.</span></span>

## <a name="download-install-and-configure-the-microsoft-intune-certificate-connector"></a><span data-ttu-id="fb5c3-155">Laden Sie den Microsoft Intune Certificate Connector herunter, und installieren und konfigurieren Sie ihn.</span><span class="sxs-lookup"><span data-stu-id="fb5c3-155">Download install and configure the Microsoft Intune Certificate Connector</span></span>

<span data-ttu-id="fb5c3-156">![ConnectorDownload][ConnectorDownload]</span><span class="sxs-lookup"><span data-stu-id="fb5c3-156">![ConnectorDownload][ConnectorDownload]</span></span>

1. <span data-ttu-id="fb5c3-157">Wählen Sie im Azure-Portal **Weitere Dienste** > **Überwachung + Verwaltung** > **Intune** aus.</span><span class="sxs-lookup"><span data-stu-id="fb5c3-157">In the Azure portal, select **More Services** > **Monitoring + Management** > **Intune**.</span></span>
2. <span data-ttu-id="fb5c3-158">Wählen Sie auf dem Blatt **Intune** die Option **Gerätekonfiguration** aus.</span><span class="sxs-lookup"><span data-stu-id="fb5c3-158">On the **Intune** blade, select **Device Configuration**.</span></span> 
3. <span data-ttu-id="fb5c3-159">Wählen Sie auf dem Blatt **Gerätekonfiguration** die Option **Zertifizierungsstelle** aus.</span><span class="sxs-lookup"><span data-stu-id="fb5c3-159">On the **Device Configuration** blade, select **Certification Authority**.</span></span> 
4. <span data-ttu-id="fb5c3-160">Klicken Sie auf **Hinzufügen** und dann auf **Connectordatei herunterladen**.</span><span class="sxs-lookup"><span data-stu-id="fb5c3-160">Click **Add** and select **Download Connector file**.</span></span> <span data-ttu-id="fb5c3-161">Speichern Sie den Download an einem Speicherort, auf den Sie auf dem Server, auf dem der Connector installiert wird, zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="fb5c3-161">Save the download to a location where you can access it from the server where you are going to install it.</span></span> 
5.  <span data-ttu-id="fb5c3-162">Melden Sie sich bei dem Server an, auf dem Sie den Microsoft Intune Certificate Connector installieren möchten.</span><span class="sxs-lookup"><span data-stu-id="fb5c3-162">Log in to the server where you will install the Microsoft Intune Certificate Connector.</span></span>
6.  <span data-ttu-id="fb5c3-163">Führen Sie das Installationsprogramm aus, und übernehmen Sie den Standardspeicherort.</span><span class="sxs-lookup"><span data-stu-id="fb5c3-163">Run the installer and accept the default location.</span></span> <span data-ttu-id="fb5c3-164">Der Connector wird unter „C:\Programme\Microsoft Intune\NDESConnectorUI\NDESConnectorUI.exe“ installiert.</span><span class="sxs-lookup"><span data-stu-id="fb5c3-164">It installs the connector to C:\Program Files\Microsoft Intune\NDESConnectorUI\NDESConnectorUI.exe.</span></span>
    1. <span data-ttu-id="fb5c3-165">Wählen Sie auf der Seite mit den Optionen des Installationsprogramms **PFX-Verteilung** aus, und klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="fb5c3-165">On the Installer Options page chose **PFX Distribution** and click **Next**.</span></span>
    2. <span data-ttu-id="fb5c3-166">Klicken Sie auf **Installieren**, und warten Sie auf den Abschluss der Installation.</span><span class="sxs-lookup"><span data-stu-id="fb5c3-166">Click **Install** and wait for installation to complete.</span></span>
    3. <span data-ttu-id="fb5c3-167">Aktivieren Sie auf der Seite zur Fertigstellung das Kontrollkästchen mit der Bezeichnung **Intune-Connector starten**, und klicken Sie auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="fb5c3-167">On the Completion page, check the box labeled **Launch Intune Connector** and click **Finish**.</span></span>
7.  <span data-ttu-id="fb5c3-168">Das Fensters des NDES-Connectors wird jetzt mit der Registerkarte **Registrierung** geöffnet. Um die Verbindung mit Intune zu aktivieren, klicken Sie auf **Anmelden** und geben ein Konto mit Administratorrechten an.</span><span class="sxs-lookup"><span data-stu-id="fb5c3-168">The NDES Connector window should now open to the **Enrollment** tab. To enable the connection to Intune, click **Sign In** and provide an account with administrative permissions.</span></span>
8.  <span data-ttu-id="fb5c3-169">Auf der Registerkarte **Erweitert** können Sie das Optionsfeld **Konto "SYSTEM" dieses Computers verwenden (Standard)** ausgewählt lassen.</span><span class="sxs-lookup"><span data-stu-id="fb5c3-169">On the **Advanced** tab, you can leave the radio button **Use this computer's SYSTEM account (default)** selected.</span></span>
9.  <span data-ttu-id="fb5c3-170">Klicken Sie auf **Anwenden** und dann auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="fb5c3-170">Click **Apply** then **Close**.</span></span>
10. <span data-ttu-id="fb5c3-171">Wechseln Sie zurück zum Azure-Portal.</span><span class="sxs-lookup"><span data-stu-id="fb5c3-171">Now go back on the Azure portal.</span></span> <span data-ttu-id="fb5c3-172">Unter **Intune** > **Gerätekonfiguration** > **Zertifizierungsstelle** werden Ihnen nach einigen Minuten ein grünes Häkchen und das Wort **Aktiv** unter **Verbindungsstatus** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="fb5c3-172">After a few minutes, you should see a green check mark and the word **Active** under **Connection status** in **Intune** > **Device Configuration** > **Certification Authority**.</span></span> <span data-ttu-id="fb5c3-173">Anhand dieser Bestätigung können Sie erkennen, dass der Connector-Server mit Intune kommunizieren kann.</span><span class="sxs-lookup"><span data-stu-id="fb5c3-173">This confirmation lets you know that your connector server can communicate with Intune.</span></span>


## <a name="create-a-device-configuration-profile"></a><span data-ttu-id="fb5c3-174">Erstellen eines Gerätekonfigurationsprofils</span><span class="sxs-lookup"><span data-stu-id="fb5c3-174">Create a device configuration profile</span></span>

1. <span data-ttu-id="fb5c3-175">Melden Sie sich beim [Azure-Portal](https://portal.azure.com) an.</span><span class="sxs-lookup"><span data-stu-id="fb5c3-175">Sign in to the [Azure portal](https://portal.azure.com).</span></span>
2. <span data-ttu-id="fb5c3-176">Navigieren Sie zu **Intune** > **Gerätekonfiguration** > **Profile**, und klicken Sie auf **Profil erstellen**.</span><span class="sxs-lookup"><span data-stu-id="fb5c3-176">Navigate to **Intune**, **Device configuration**, **Profiles**, and click **Create profile**.</span></span>

   <span data-ttu-id="fb5c3-177">![NavigateIntune][NavigateIntune]</span><span class="sxs-lookup"><span data-stu-id="fb5c3-177">![NavigateIntune][NavigateIntune]</span></span>

3. <span data-ttu-id="fb5c3-178">Geben Sie die folgenden Informationen ein:</span><span class="sxs-lookup"><span data-stu-id="fb5c3-178">Populate the following information:</span></span>
   * <span data-ttu-id="fb5c3-179">**Name** für das Profil</span><span class="sxs-lookup"><span data-stu-id="fb5c3-179">**Name** for the profile</span></span>
   * <span data-ttu-id="fb5c3-180">Optional eine Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fb5c3-180">Optionally set a description</span></span>
   * <span data-ttu-id="fb5c3-181">**Plattform**, auf der das Profil bereitgestellt werden soll</span><span class="sxs-lookup"><span data-stu-id="fb5c3-181">**Platform** to deploy the profile to</span></span>
   * <span data-ttu-id="fb5c3-182">Für **Profiltyp** die Option **Vertrauenswürdiges Zertifikat**</span><span class="sxs-lookup"><span data-stu-id="fb5c3-182">Set **Profile type** to **Trusted certificate**</span></span>
4. <span data-ttu-id="fb5c3-183">Navigieren Sie zu **Einstellungen**, und geben Sie die zuvor exportierte CER-Datei mit dem Zertifikat der Stammzertifizierungsstelle an.</span><span class="sxs-lookup"><span data-stu-id="fb5c3-183">Navigate to **Settings** and provide the .cer file Root CA Certificate exported previously.</span></span>

   > [!NOTE]
   > <span data-ttu-id="fb5c3-184">Abhängig von der in **Schritt 3** ausgewählten Plattform besitzen Sie möglicherweise die Option zum Auswählen des **Zielspeichers** für das Zertifikat.</span><span class="sxs-lookup"><span data-stu-id="fb5c3-184">Depending on the Platform you chose in **Step 3** you may or may not have an option to choose the **Destination store** for the certificate.</span></span>

   <span data-ttu-id="fb5c3-185">![ProfileSettings][ProfileSettings]</span><span class="sxs-lookup"><span data-stu-id="fb5c3-185">![ProfileSettings][ProfileSettings]</span></span>

5. <span data-ttu-id="fb5c3-186">Klicken Sie auf **OK** und dann auf **Erstellen**, um Ihr Profil zu speichern.</span><span class="sxs-lookup"><span data-stu-id="fb5c3-186">Click **OK** then **Create** to save your profile.</span></span>
6. <span data-ttu-id="fb5c3-187">Informationen zum Zuweisen des neuen Profils zu einem oder mehreren Geräten finden Sie unter [Zuweisen von Microsoft Intune-Geräteprofilen](device-profile-assign.md).</span><span class="sxs-lookup"><span data-stu-id="fb5c3-187">To assign the new profile to one or more devices see [How to assign Microsoft Intune device profiles](device-profile-assign.md).</span></span>

## <a name="create-a-pkcs-certificate-profile"></a><span data-ttu-id="fb5c3-188">Erstellen eines PKCS-Zertifikatprofils</span><span class="sxs-lookup"><span data-stu-id="fb5c3-188">Create a PKCS Certificate profile</span></span>

1. <span data-ttu-id="fb5c3-189">Melden Sie sich beim [Azure-Portal](https://portal.azure.com) an.</span><span class="sxs-lookup"><span data-stu-id="fb5c3-189">Sign in to the [Azure portal](https://portal.azure.com).</span></span>
2. <span data-ttu-id="fb5c3-190">Navigieren Sie zu **Intune** > **Gerätekonfiguration** > **Profile**, und klicken Sie auf **Profil erstellen**.</span><span class="sxs-lookup"><span data-stu-id="fb5c3-190">Navigate to **Intune**, **Device configuration**, **Profiles**, and click **Create profile**.</span></span>
3. <span data-ttu-id="fb5c3-191">Geben Sie die folgenden Informationen ein:</span><span class="sxs-lookup"><span data-stu-id="fb5c3-191">Populate the following information:</span></span>
   * <span data-ttu-id="fb5c3-192">**Name** für das Profil</span><span class="sxs-lookup"><span data-stu-id="fb5c3-192">**Name** for the profile</span></span>
   * <span data-ttu-id="fb5c3-193">Optional eine Beschreibung</span><span class="sxs-lookup"><span data-stu-id="fb5c3-193">Optionally set a description</span></span>
   * <span data-ttu-id="fb5c3-194">**Plattform**, auf der das Profil bereitgestellt werden soll</span><span class="sxs-lookup"><span data-stu-id="fb5c3-194">**Platform** to deploy the profile to</span></span>
   * <span data-ttu-id="fb5c3-195">Für **Profiltyp** die Option **PKCS-Zertifikat**</span><span class="sxs-lookup"><span data-stu-id="fb5c3-195">Set **Profile type** to **PKCS Certificate**</span></span>
4. <span data-ttu-id="fb5c3-196">Wechseln Sie zu **Einstellungen**, und geben Sie die folgenden Informationen an:</span><span class="sxs-lookup"><span data-stu-id="fb5c3-196">Navigate to **Settings** and provide the following information:</span></span>
   * <span data-ttu-id="fb5c3-197">**Erneuerungsschwellenwert (%)**: Empfohlen wird ein Wert von 20 %.</span><span class="sxs-lookup"><span data-stu-id="fb5c3-197">**Renewal threshold (%)** - Recommended is 20%.</span></span>
   * <span data-ttu-id="fb5c3-198">**Gültigkeitsdauer des Zertifikats**: Wenn Sie die Zertifikatvorlage nicht geändert haben, ist diese Option auf ein Jahr festgelegt.</span><span class="sxs-lookup"><span data-stu-id="fb5c3-198">**Certificate validity period** - If you did not change the certificate template this option should be set to one year.</span></span>
   * <span data-ttu-id="fb5c3-199">**Zertifizierungsstelle**: Diese Option ist der interne vollqualifizierte Domänenname (FQDN) Ihrer Unternehmenszertifizierungsstelle.</span><span class="sxs-lookup"><span data-stu-id="fb5c3-199">**Certification authority** - This option is the internal fully qualified domain name (FQDN) of your Enterprise CA.</span></span>
   * <span data-ttu-id="fb5c3-200">**Name der Zertifizierungsstelle**: Diese Option ist der Name Ihrer Unternehmenszertifizierungsstelle, der sich ggf. vom vorherigen Element unterscheidet.</span><span class="sxs-lookup"><span data-stu-id="fb5c3-200">**Certification authority name** - This option is the name of your Enterprise CA and may be different than the previous item.</span></span>
   * <span data-ttu-id="fb5c3-201">**Name der Zertifikatvorlage**: Diese Option ist der Name der zuvor erstellten Vorlage.</span><span class="sxs-lookup"><span data-stu-id="fb5c3-201">**Certificate template name** - This option is the name of the template created earlier.</span></span> <span data-ttu-id="fb5c3-202">Beachten Sie, dass der **Vorlagenname** standardmäßig dem **Vorlagenanzeigenamen** *ohne Leerzeichen* entspricht.</span><span class="sxs-lookup"><span data-stu-id="fb5c3-202">Remember **Template name** by default is the same as **Template display name** with *no spaces*.</span></span>
   * <span data-ttu-id="fb5c3-203">**Format des Antragstellernamens**: Legen Sie diese Option auf **Allgemeiner Name** fest, sofern kein anderes Format erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="fb5c3-203">**Subject name format** - Set this option to **Common name** unless otherwise required.</span></span>
   * <span data-ttu-id="fb5c3-204">**Alternativer Antragstellername**: Legen Sie diese Option auf **Benutzerprinzipalname (UPN)** fest, sofern nichts anderes erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="fb5c3-204">**Subject alternative name** - Set this option to **User principal name (UPN)** unless otherwise required.</span></span>
   * <span data-ttu-id="fb5c3-205">**Erweiterte Schlüsselverwendung**: Sofern Sie im vorherigen Abschnitt, **Konfigurieren von Zertifikatvorlagen für die Zertifizierungsstelle**, in Schritt 10 die Standardeinstellungen verwendet haben, fügen Sie aus dem Auswahlfeld die folgenden **vordefinierten Werte** hinzu:</span><span class="sxs-lookup"><span data-stu-id="fb5c3-205">**Extended key usage** - As long as you used the default settings in Step 10 in the preceding section **Configure certificate templates on the certification authority**, add the following **Predefined values** from the selection box:</span></span>
      * <span data-ttu-id="fb5c3-206">**Verwendung für beliebigen Zweck**</span><span class="sxs-lookup"><span data-stu-id="fb5c3-206">**Any Purpose**</span></span>
      * <span data-ttu-id="fb5c3-207">**Clientauthentifizierung**</span><span class="sxs-lookup"><span data-stu-id="fb5c3-207">**Client Authentication**</span></span>
      * <span data-ttu-id="fb5c3-208">**Sichere E-Mail**</span><span class="sxs-lookup"><span data-stu-id="fb5c3-208">**Secure Email**</span></span>
   * <span data-ttu-id="fb5c3-209">**Stammzertifikat** (für Android-Profile): Diese Option ist die CER-Datei, die in Schritt 3 im vorherigen Abschnitt [Exportieren des Stammzertifikats aus der Unternehmenszertifizierungsstelle](#export-the-root-certificate-from-the-enterprise-ca) exportiert wurde.</span><span class="sxs-lookup"><span data-stu-id="fb5c3-209">**Root Certificate** - (For Android Profiles) This option is the .cer file exported in Step 3 under the previous section [Export the root certificate from the Enterprise CA](#export-the-root-certificate-from-the-enterprise-ca).</span></span>

5. <span data-ttu-id="fb5c3-210">Klicken Sie auf **OK** und dann auf **Erstellen**, um Ihr Profil zu speichern.</span><span class="sxs-lookup"><span data-stu-id="fb5c3-210">Click **OK**, then click **Create** to save your profile.</span></span>
6. <span data-ttu-id="fb5c3-211">Informationen zum Zuweisen des neuen Profils zu einem oder mehreren Geräten finden Sie im Artikel [Zuweisen von Microsoft Intune-Geräteprofilen](device-profile-assign.md).</span><span class="sxs-lookup"><span data-stu-id="fb5c3-211">To assign the new profile to one or more devices, see the article [How to assign Microsoft Intune device profiles](device-profile-assign.md).</span></span>


[NavigateIntune]: ./media/certificates-pfx-configure-profile-new.png "Im Azure-Portal zu Intune navigieren und ein neues Profil für ein vertrauenswürdiges Zertifikat erstellen"
[ProfileSettings]: ./media/certificates-pfx-configure-profile-fill.png "Profil erstellen und ein vertrauenswürdiges Zertifikat hochladen"
[ConnectorDownload]: ./media/certificates-download-connector.png "Certificate Connector aus dem Azure-Portal herunterladen"  
