---
title: "Schützen des Zugriffs auf Netzwerke mit Cisco ISE"
description: "Verwenden Sie Cisco ISE mit Intune, damit Geräte bei Intune registriert sind und mit der Richtlinie kompatibel sind, bevor sie auf WLAN und VPN zugreifen, die von Cisco ISE gesteuert werden."
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 01/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5631bac3-921d-438e-a320-d9061d88726c
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: muhosabe
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: f96ed2a203f1b0edf28bebac9f79680b046fe0dd
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2017
---
# <a name="using-cisco-ise-with-microsoft-intune"></a><span data-ttu-id="55cf0-103">Verwenden von Cisco ISE mit Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="55cf0-103">Using Cisco ISE with Microsoft Intune</span></span>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="55cf0-104">Die Intune-Integration mit Cisco Identity Services Engine (ISE) erlaubt Ihnen, in Ihrer ISE-Umgebung Netzwerkrichtlinien mithilfe der Intune-Geräteregistrierung und des Kompatibilitätszustands zu verfassen.</span><span class="sxs-lookup"><span data-stu-id="55cf0-104">Intune integration with Cisco Identity Services Engine (ISE) allows you to author network policies in your ISE environment by using the Intune device-enrollment and compliance state.</span></span> <span data-ttu-id="55cf0-105">Sie können diese Richtlinien so einsetzen, dass der Zugriff auf Ihr Unternehmensnetzwerk auf Geräte beschränkt wird, die von Intune verwaltet werden und mit Intune-Richtlinien kompatibel sind.</span><span class="sxs-lookup"><span data-stu-id="55cf0-105">You can use these policies to ensure that access to your company network is restricted to devices that are managed by Intune and compliant with Intune policies.</span></span>

## <a name="configuration-steps"></a><span data-ttu-id="55cf0-106">Konfigurationsschritte</span><span class="sxs-lookup"><span data-stu-id="55cf0-106">Configuration steps</span></span>

<span data-ttu-id="55cf0-107">Sie müssen keine Einrichtungsschritte in Ihrem Intune-Mandanten vornehmen, um diese Integration zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="55cf0-107">To enable this integration, you don’t need to do any setup in your Intune tenant.</span></span> <span data-ttu-id="55cf0-108">Sie müssen Berechtigungen für Ihren Cisco ISE-Server für den Zugriff auf den Intune-Mandanten bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="55cf0-108">You will need to provide permissions to your Cisco ISE server to access your Intune tenant.</span></span> <span data-ttu-id="55cf0-109">Nachdem dies erfolgt ist, wird der Rest des Setups auf Ihrem Cisco ISE-Server durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="55cf0-109">After that's done, the rest of the setup happens in your Cisco ISE server.</span></span> <span data-ttu-id="55cf0-110">In diesem Artikel erhalten Sie Anweisungen, wie Sie für Ihren ISE-Server die Berechtigungen bereitstellen, auf Ihren Intune-Mandanten zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="55cf0-110">This article gives you instructions on providing your ISE server with permissions to access your Intune tenant.</span></span>

### <a name="step-1-manage-the-certificates"></a><span data-ttu-id="55cf0-111">Schritt 1: Verwalten der Zertifikate</span><span class="sxs-lookup"><span data-stu-id="55cf0-111">Step 1: Manage the certificates</span></span>
<span data-ttu-id="55cf0-112">Exportieren Sie die Zertifikate aus der Azure Active Directory-Konsole (Azure AD), und importieren Sie sie anschließend in den Speicher „Vertrauenswürdige Zertifikate“ der ISE-Konsole:</span><span class="sxs-lookup"><span data-stu-id="55cf0-112">Export the certificate from the Azure Active Directory (Azure AD) console, then import it into the Trusted Certificates store of the ISE console:</span></span>

#### <a name="internet-explorer-11"></a><span data-ttu-id="55cf0-113">Internet Explorer 11</span><span class="sxs-lookup"><span data-stu-id="55cf0-113">Internet Explorer 11</span></span>


   <span data-ttu-id="55cf0-114">a.</span><span class="sxs-lookup"><span data-stu-id="55cf0-114">a.</span></span> <span data-ttu-id="55cf0-115">Führen Sie Internet Explorer als Administrator aus, und melden Sie sich bei der Azure AD-Konsole an.</span><span class="sxs-lookup"><span data-stu-id="55cf0-115">Run Internet Explorer as an administrator, and sign in to the Azure AD console.</span></span>

   <span data-ttu-id="55cf0-116">b.</span><span class="sxs-lookup"><span data-stu-id="55cf0-116">b.</span></span> <span data-ttu-id="55cf0-117">Wählen Sie das Schlosssymbol in der Adressleiste und **Anzeigen von Zertifikaten** aus.</span><span class="sxs-lookup"><span data-stu-id="55cf0-117">Choose the lock icon in the address bar and choose **View certificates**.</span></span>

   <span data-ttu-id="55cf0-118">c.</span><span class="sxs-lookup"><span data-stu-id="55cf0-118">c.</span></span> <span data-ttu-id="55cf0-119">Wählen Sie auf der Registerkarte **Details** der Zertifikateigenschaften **In Datei kopieren** aus.</span><span class="sxs-lookup"><span data-stu-id="55cf0-119">On the **Details** tab of the certificate properties, choose **Copy to file**.</span></span>

   <span data-ttu-id="55cf0-120">d.</span><span class="sxs-lookup"><span data-stu-id="55cf0-120">d.</span></span> <span data-ttu-id="55cf0-121">Wählen Sie auf der Startseite **Assistent für den Zertifikatexport** **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="55cf0-121">In the **Certificate export wizard** welcome page, choose **Next**.</span></span>

   <span data-ttu-id="55cf0-122">e.</span><span class="sxs-lookup"><span data-stu-id="55cf0-122">e.</span></span> <span data-ttu-id="55cf0-123">Lassen Sie auf der Seite **Format der zu exportierenden Datei** den Standardwert **DER-codiert-binär x. 509 (. CER)**, und wählen Sie **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="55cf0-123">On the **Export file format** page, leave the default, **DER encoded binary x.509 (.CER)**, and choose **Next**.</span></span>  

   <span data-ttu-id="55cf0-124">f.</span><span class="sxs-lookup"><span data-stu-id="55cf0-124">f.</span></span> <span data-ttu-id="55cf0-125">Wählen Sie auf der Seite **Zu exportierende Datei** **Durchsuchen** aus, um einen Speicherort zum Speichern der Datei auszuwählen, und geben Sie einen Dateinamen ein.</span><span class="sxs-lookup"><span data-stu-id="55cf0-125">On the **File to export** page, choose **Browse** to pick a location in which to save the file, and provide a file name.</span></span> <span data-ttu-id="55cf0-126">Obwohl es so aussieht, als ob Sie eine Datei zum exportieren auswählen, benennen Sie tatsächlich die Datei, in der das exportierte Zertifikat gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="55cf0-126">Though it seems like you’re picking a file to export, you’re actually naming the file that the exported certificate will be saved to.</span></span> <span data-ttu-id="55cf0-127">Wählen Sie **Weiter** &gt; **Fertig stellen** aus.</span><span class="sxs-lookup"><span data-stu-id="55cf0-127">Choose **Next** &gt; **Finish**.</span></span>

   <span data-ttu-id="55cf0-128">g.</span><span class="sxs-lookup"><span data-stu-id="55cf0-128">g.</span></span> <span data-ttu-id="55cf0-129">Importieren Sie von der ISE-Konsole aus das Intune-Zertifikat (die Datei, die Sie exportiert haben) in den **Vertrauenswürde Zertifikate**-Speicher.</span><span class="sxs-lookup"><span data-stu-id="55cf0-129">From within the ISE console, import the Intune certificate (the file you exported) into the  **Trusted Certificates** store.</span></span>

#### <a name="safari"></a><span data-ttu-id="55cf0-130">Safari</span><span class="sxs-lookup"><span data-stu-id="55cf0-130">Safari</span></span>

 <span data-ttu-id="55cf0-131">a.</span><span class="sxs-lookup"><span data-stu-id="55cf0-131">a.</span></span> <span data-ttu-id="55cf0-132">Melden Sie sich bei der Azure AD-Konsole an.</span><span class="sxs-lookup"><span data-stu-id="55cf0-132">Sign in to the Azure AD console.</span></span>

<span data-ttu-id="55cf0-133">b.</span><span class="sxs-lookup"><span data-stu-id="55cf0-133">b.</span></span> <span data-ttu-id="55cf0-134">Wählen Sie das Schlosssymbol aus &gt;  **Weitere Informationen**.</span><span class="sxs-lookup"><span data-stu-id="55cf0-134">Choose the lock icon &gt;  **More information**.</span></span>

   <span data-ttu-id="55cf0-135">c.</span><span class="sxs-lookup"><span data-stu-id="55cf0-135">c.</span></span> <span data-ttu-id="55cf0-136">Wählen Sie **Zertifikat anzeigen** &gt; **Details** aus.</span><span class="sxs-lookup"><span data-stu-id="55cf0-136">Choose **View certificate** &gt; **Details**.</span></span>

   <span data-ttu-id="55cf0-137">d.</span><span class="sxs-lookup"><span data-stu-id="55cf0-137">d.</span></span> <span data-ttu-id="55cf0-138">Wählen Sie das Zertifikat und anschließend **Exportieren** aus.</span><span class="sxs-lookup"><span data-stu-id="55cf0-138">Choose the certificate, and then choose **Export**.</span></span> 

   <span data-ttu-id="55cf0-139">e.</span><span class="sxs-lookup"><span data-stu-id="55cf0-139">e.</span></span> <span data-ttu-id="55cf0-140">Importieren Sie von der ISE-Konsole aus das Intune-Zertifikat (die Datei, die Sie exportiert haben) in den **Vertrauenswürde Zertifikate**-Speicher.</span><span class="sxs-lookup"><span data-stu-id="55cf0-140">From within the ISE console, import the Intune certificate (the file you exported) into the  **Trusted Certificates** store.</span></span>

> [!IMPORTANT]
>
> <span data-ttu-id="55cf0-141">Überprüfen Sie das Ablaufdatum des Zertifikats, da Sie ein neues Zertifikat exportieren und importieren müssen, wenn dieses abläuft.</span><span class="sxs-lookup"><span data-stu-id="55cf0-141">Check the expiration date of the certificate, as you will have to export and import a new certificate when this one expires.</span></span>


### <a name="obtain-a-self-signed-cert-from-ise"></a><span data-ttu-id="55cf0-142">Abrufen eines selbstsignierten Zertifikats von ISE</span><span class="sxs-lookup"><span data-stu-id="55cf0-142">Obtain a self-signed cert from ISE</span></span> 

1.  <span data-ttu-id="55cf0-143">Wechseln Sie in der ISE-Konsole zu **Verwaltung** > **Zertifikate** > **Systemzertifikaten** > **Selbstsigniertes Zertifikat generieren**.</span><span class="sxs-lookup"><span data-stu-id="55cf0-143">In the ISE console, go to **Administration** > **Certificates** > **System Certificates** > **Generate Self Signed Certificate**.</span></span>  
2.       <span data-ttu-id="55cf0-144">Exportieren Sie das selbstsignierte Zertifikat.</span><span class="sxs-lookup"><span data-stu-id="55cf0-144">Export the self-signed certificate.</span></span>
3. <span data-ttu-id="55cf0-145">Bearbeiten Sie das exportierte Zertifikat in einem Texteditor:</span><span class="sxs-lookup"><span data-stu-id="55cf0-145">In a text editor, edit the exported certificate:</span></span>

 - <span data-ttu-id="55cf0-146">Löschen Sie **-----BEGIN CERTIFICATE-----**</span><span class="sxs-lookup"><span data-stu-id="55cf0-146">Delete **-----BEGIN CERTIFICATE-----**</span></span>
 - <span data-ttu-id="55cf0-147">Löschen Sie **-----END CERTIFICATE-----**</span><span class="sxs-lookup"><span data-stu-id="55cf0-147">Delete **-----END CERTIFICATE-----**</span></span>
 
<span data-ttu-id="55cf0-148">Stellen Sie sicher, dass sich der gesamte Text in einer Zeile befindet</span><span class="sxs-lookup"><span data-stu-id="55cf0-148">Ensure all of the text is a single line</span></span>


### <a name="step-2-create-an-app-for-ise-in-your-azure-ad-tenant"></a><span data-ttu-id="55cf0-149">Schritt 2: Erstellen einer App für ISE in Ihrem Azure AD-Mandanten</span><span class="sxs-lookup"><span data-stu-id="55cf0-149">Step 2: Create an app for ISE in your Azure AD tenant</span></span>
1. <span data-ttu-id="55cf0-150">Wählen Sie in der Konsole von Azure AD **Anwendungen** > **Hinzufügen einer Anwendung** > **Eine von meinem Unternehmen entwickelte Anwendung hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="55cf0-150">In the Azure AD console, choose **Applications** > **Add an Application** > **Add an application my organization is developing**.</span></span>
2. <span data-ttu-id="55cf0-151">Stellen Sie einen Namen und eine URL für die App bereit.</span><span class="sxs-lookup"><span data-stu-id="55cf0-151">Provide a name and a URL for the app.</span></span> <span data-ttu-id="55cf0-152">Die URL könnte die Website Ihres Unternehmens sein.</span><span class="sxs-lookup"><span data-stu-id="55cf0-152">The URL could be your company website.</span></span>
3. <span data-ttu-id="55cf0-153">Laden Sie das App-Manifest (eine JSON-Datei) herunter.</span><span class="sxs-lookup"><span data-stu-id="55cf0-153">Download the app manifest (a JSON file).</span></span>
4. <span data-ttu-id="55cf0-154">Bearbeiten Sie die JSON-Manifestdatei.</span><span class="sxs-lookup"><span data-stu-id="55cf0-154">Edit the manifest JSON file.</span></span> <span data-ttu-id="55cf0-155">Geben Sie in der Einstellung namens **keyCredentials** den bearbeiteten Zertifikattext aus Schritt 1 als Einstellungswert an.</span><span class="sxs-lookup"><span data-stu-id="55cf0-155">In the setting called **keyCredentials**, provide the edited certificate text from Step 1 as the setting value.</span></span>
5. <span data-ttu-id="55cf0-156">Speichern Sie die Datei, ohne ihren Namen zu ändern.</span><span class="sxs-lookup"><span data-stu-id="55cf0-156">Save the file without changing its name.</span></span>
6. <span data-ttu-id="55cf0-157">Stellen Sie Ihrer App Berechtigungen für Microsoft Graph und die Microsoft Intune-API bereit.</span><span class="sxs-lookup"><span data-stu-id="55cf0-157">Provide your app with permissions to Microsoft Graph and the Microsoft Intune API.</span></span>

 <span data-ttu-id="55cf0-158">a.</span><span class="sxs-lookup"><span data-stu-id="55cf0-158">a.</span></span> <span data-ttu-id="55cf0-159">Wählen Sie für Microsoft Graph Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="55cf0-159">For Microsoft Graph, choose the following:</span></span>
    - <span data-ttu-id="55cf0-160">**Anwendungsberechtigungen**: Lesen von Verzeichnisdaten</span><span class="sxs-lookup"><span data-stu-id="55cf0-160">**Application permissions**: Read directory data</span></span>
    - <span data-ttu-id="55cf0-161">**Delegierte Berechtigungen**:</span><span class="sxs-lookup"><span data-stu-id="55cf0-161">**Delegated permissions**:</span></span>
        - <span data-ttu-id="55cf0-162">Jederzeit auf die Daten des Benutzers zugreifen</span><span class="sxs-lookup"><span data-stu-id="55cf0-162">Access user’s data anytime</span></span>
        - <span data-ttu-id="55cf0-163">Benutzer anmelden</span><span class="sxs-lookup"><span data-stu-id="55cf0-163">Sign users in</span></span>

 <span data-ttu-id="55cf0-164">b.</span><span class="sxs-lookup"><span data-stu-id="55cf0-164">b.</span></span> <span data-ttu-id="55cf0-165">Wählen Sie für die Microsoft Intune-API in **Anwendungsberechtigungen** **Abrufen des Gerätestatus und der Kompatibilität von Intune** aus.</span><span class="sxs-lookup"><span data-stu-id="55cf0-165">For the Microsoft Intune API, in **Application permissions**, choose **Get device state and compliance from Intune**.</span></span>

7. <span data-ttu-id="55cf0-166">Wählen Sie **Endpunkte anzeigen** aus, und kopieren Sie die folgenden Werte für die Verwendung bei der Konfiguration der ISE-Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="55cf0-166">Choose **View Endpoints** and copy the following values for use in configuring ISE settings:</span></span>

|<span data-ttu-id="55cf0-167">Wert im Azure AD-Portal</span><span class="sxs-lookup"><span data-stu-id="55cf0-167">Value in Azure AD portal</span></span>|<span data-ttu-id="55cf0-168">Entsprechendes Feld im ISE-Portal</span><span class="sxs-lookup"><span data-stu-id="55cf0-168">Corresponding field in ISE portal</span></span>|
|-------------------|---------------------------------|
|<span data-ttu-id="55cf0-169">Microsoft Azure AD Graph-API-Endpunkt</span><span class="sxs-lookup"><span data-stu-id="55cf0-169">Microsoft Azure AD Graph API endpoint</span></span>|<span data-ttu-id="55cf0-170">URL für AutoErmittlung</span><span class="sxs-lookup"><span data-stu-id="55cf0-170">Auto Discovery URL</span></span>|
|<span data-ttu-id="55cf0-171">OAuth 2.0-Tokenendpunkt</span><span class="sxs-lookup"><span data-stu-id="55cf0-171">Oauth 2.0 Token endpoint</span></span>|<span data-ttu-id="55cf0-172">Token ausgebende URL</span><span class="sxs-lookup"><span data-stu-id="55cf0-172">Token Issuing URL</span></span>|
|<span data-ttu-id="55cf0-173">Code mit Client-ID aktualisieren</span><span class="sxs-lookup"><span data-stu-id="55cf0-173">Update your code with your Client ID</span></span>|<span data-ttu-id="55cf0-174">Client-ID</span><span class="sxs-lookup"><span data-stu-id="55cf0-174">Client ID</span></span>|

### <a name="step-4-upload-the-self-signed-certificate-from-ise-into-the-ise-app-you-created-in-azure-ad"></a><span data-ttu-id="55cf0-175">Schritt 4: Hochladen des selbstsignierten Zertifikats aus ISE in die ISE-App, die Sie in Azure AD erstellt haben</span><span class="sxs-lookup"><span data-stu-id="55cf0-175">Step 4: Upload the self-signed certificate from ISE into the ISE app you created in Azure AD</span></span>
1.     <span data-ttu-id="55cf0-176">Rufen Sie den base64-codierten Zertifikatswert und Fingerabdruck aus einer öffentlichen CER X509-Zertifikatsdatei ab.</span><span class="sxs-lookup"><span data-stu-id="55cf0-176">Get the base64 encoded cert value and thumbprint from a .cer X509 public cert file.</span></span> <span data-ttu-id="55cf0-177">In diesem Beispiel wird PowerShell verwendet:</span><span class="sxs-lookup"><span data-stu-id="55cf0-177">This example uses PowerShell:</span></span>
   
      
      <span data-ttu-id="55cf0-178">$cer = New-Object System.Security.Cryptography.X509Certificates.X509Certificate2    $cer.Import(“mycer.cer”)    $bin = $cer.GetRawCertData()    $base64Value = [System.Convert]::ToBase64String($bin)    $bin = $cer.GetCertHash()    $base64Thumbprint = [System.Convert]::ToBase64String($bin)    $keyid = [System.Guid]::NewGuid().ToString()</span><span class="sxs-lookup"><span data-stu-id="55cf0-178">$cer = New-Object System.Security.Cryptography.X509Certificates.X509Certificate2    $cer.Import(“mycer.cer”)    $bin = $cer.GetRawCertData()    $base64Value = [System.Convert]::ToBase64String($bin)    $bin = $cer.GetCertHash()    $base64Thumbprint = [System.Convert]::ToBase64String($bin)    $keyid = [System.Guid]::NewGuid().ToString()</span></span>
 
    <span data-ttu-id="55cf0-179">Speichern Sie die Werte für „$base64Thumbprint“, „$base64Value“ und „$keyid“, die im nächsten Schritt verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="55cf0-179">Store the values for $base64Thumbprint, $base64Value and $keyid, to be used in the next step.</span></span>
2.       <span data-ttu-id="55cf0-180">Laden Sie das Zertifikat mithilfe der Manifestdatei hoch.</span><span class="sxs-lookup"><span data-stu-id="55cf0-180">Upload the certificate through the manifest file.</span></span> <span data-ttu-id="55cf0-181">Melden Sie sich beim [Azure-Verwaltungsportal](https://manage.windowsazure.com) an</span><span class="sxs-lookup"><span data-stu-id="55cf0-181">Log in to the [Azure Management Portal](https://manage.windowsazure.com)</span></span>
2.      <span data-ttu-id="55cf0-182">Suchen Sie im Azure AD-Snap-In die Anwendung, die Sie mit einem X.509-Zertifikat konfigurieren möchten.</span><span class="sxs-lookup"><span data-stu-id="55cf0-182">In to the Azure AD snap-in find the application that you want to configure with an X.509 certificate.</span></span>
3.      <span data-ttu-id="55cf0-183">Laden Sie die Anwendungsmanifestdatei herunter.</span><span class="sxs-lookup"><span data-stu-id="55cf0-183">Download the application manifest file.</span></span> 
5.      <span data-ttu-id="55cf0-184">Ersetzen Sie die leere Eigenschaft „KeyCredentials“: [] durch den folgenden JSON-Code.</span><span class="sxs-lookup"><span data-stu-id="55cf0-184">Replace the empty “KeyCredentials”: [], property with the following JSON.</span></span>  <span data-ttu-id="55cf0-185">Der komplexe Typ „KeyCredentials“ ist in der [Entity and complex type reference (Referenz zu Entitäten und komplexen Typen)](https://msdn.microsoft.com/library/azure/ad/graph/api/entity-and-complex-type-reference#KeyCredentialType) dokumentiert.</span><span class="sxs-lookup"><span data-stu-id="55cf0-185">The KeyCredentials complex type is documented in[Entity and complex type reference](https://msdn.microsoft.com/library/azure/ad/graph/api/entity-and-complex-type-reference#KeyCredentialType).</span></span>

 
    <span data-ttu-id="55cf0-186">“keyCredentials“: [ { “customKeyIdentifier“: “$base64Thumbprint_from_above”, “keyId“: “$keyid_from_above“, “type”: “AsymmetricX509Cert”, “usage”: “Verify”, “value”:  “$base64Value_from_above” }2.</span><span class="sxs-lookup"><span data-stu-id="55cf0-186">“keyCredentials“: [ { “customKeyIdentifier“: “$base64Thumbprint_from_above”, “keyId“: “$keyid_from_above“, “type”: “AsymmetricX509Cert”, “usage”: “Verify”, “value”:  “$base64Value_from_above” }2.</span></span> 
     <span data-ttu-id="55cf0-187">],</span><span class="sxs-lookup"><span data-stu-id="55cf0-187">],</span></span> 
 
<span data-ttu-id="55cf0-188">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="55cf0-188">For example:</span></span>
 
    “keyCredentials“: [
    {
    “customKeyIdentifier“: “ieF43L8nkyw/PEHjWvj+PkWebXk=”,
    “keyId“: “2d6d849e-3e9e-46cd-b5ed-0f9e30d078cc”,
    “type”: “AsymmetricX509Cert”,
    “usage”: “Verify”,
    “value”: “MIICWjCCAgSgAwIBA***omitted for brevity***qoD4dmgJqZmXDfFyQ”
    }
    ],
 
6.      <span data-ttu-id="55cf0-189">Speichern Sie die Änderung an der Anwendungsmanifestdatei.</span><span class="sxs-lookup"><span data-stu-id="55cf0-189">Save the change to the application manifest file.</span></span>
7.      <span data-ttu-id="55cf0-190">Laden Sie die bearbeitete Anwendungsmanifestdatei mithilfe des Azure-Verwaltungsportals hoch.</span><span class="sxs-lookup"><span data-stu-id="55cf0-190">Upload the edited application manifest file through the Azure management mortal.</span></span>
8.      <span data-ttu-id="55cf0-191">Optional: Laden Sie das Manifest erneut herunter, um zu überprüfen, ob Ihr X.509-Zertifikat in der Anwendung vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="55cf0-191">Optional:  Download the manifest again, to check that your X.509 cert is present on the application.</span></span>

>[!NOTE]
>
> <span data-ttu-id="55cf0-192">„KeyCredentials“ ist eine Sammlung, daher können Sie in Rolloverszenarien mehrere X.509-Zertifikate hochladen oder Zertifikate in Kompromittierungsszenarien löschen.</span><span class="sxs-lookup"><span data-stu-id="55cf0-192">KeyCredentials is a collection, so you can upload multiple X.509 certificates for rollover scenarios, or delete certficates in compromise scenarios.</span></span>


### <a name="step-4-configure-ise-settings"></a><span data-ttu-id="55cf0-193">Schritt 4: Konfigurieren der ISE-Einstellungen</span><span class="sxs-lookup"><span data-stu-id="55cf0-193">Step 4: Configure ISE Settings</span></span>
<span data-ttu-id="55cf0-194">Geben Sie in der Verwaltungskonsole von ISE diese Einstellungswerte ein:</span><span class="sxs-lookup"><span data-stu-id="55cf0-194">In the ISE admin console, provide these setting values:</span></span>
  - <span data-ttu-id="55cf0-195">**Servertyp**: Mobile Device Manager</span><span class="sxs-lookup"><span data-stu-id="55cf0-195">**Server Type**: Mobile Device Manager</span></span>
  - <span data-ttu-id="55cf0-196">**Authentifizierungstyp**: OAuth – Anmeldeinformationen des Clients</span><span class="sxs-lookup"><span data-stu-id="55cf0-196">**Authentication type**: OAuth – Client Credentials</span></span>
  - <span data-ttu-id="55cf0-197">**AutoErmittlung**: Ja</span><span class="sxs-lookup"><span data-stu-id="55cf0-197">**Auto Discovery**: Yes</span></span>
  - <span data-ttu-id="55cf0-198">**URL für AutoErmittlung**: *Geben Sie den Wert aus Schritt 1 ein.*</span><span class="sxs-lookup"><span data-stu-id="55cf0-198">**Auto Discover URL**: *Enter the value from Step 1.*</span></span>
  - <span data-ttu-id="55cf0-199">**Client-ID**: *Geben Sie den Wert aus Schritt 1 ein.*</span><span class="sxs-lookup"><span data-stu-id="55cf0-199">**Client ID**: *Enter the value from Step 1.*</span></span>
  - <span data-ttu-id="55cf0-200">**Token ausgebende URL**: *Geben Sie den Wert aus Schritt 1 ein.*</span><span class="sxs-lookup"><span data-stu-id="55cf0-200">**Token issuing URL**: *Enter the value from Step 1.*</span></span>



## <a name="information-shared-between-your-intune-tenant-and-your-cisco-ise-server"></a><span data-ttu-id="55cf0-201">Informationen die zwischen Ihrem Intune-Mandanten und Ihrem Cisco ISE-Server freigegeben sind.</span><span class="sxs-lookup"><span data-stu-id="55cf0-201">Information shared between your Intune tenant and your Cisco ISE server</span></span>
<span data-ttu-id="55cf0-202">Diese Tabelle listet die Informationen auf, die zwischen Ihrem Intune-Mandanten und Ihrem Cisco ISE-Server für die mit Intune verwalteten Geräte freigegeben sind.</span><span class="sxs-lookup"><span data-stu-id="55cf0-202">This table lists the information that is shared between your Intune tenant and your Cisco ISE server for devices that are managed by Intune.</span></span>

|<span data-ttu-id="55cf0-203">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="55cf0-203">Property</span></span>|  <span data-ttu-id="55cf0-204">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="55cf0-204">Description</span></span>|
|---------------|------------------------------------------------------------|
|<span data-ttu-id="55cf0-205">complianceState</span><span class="sxs-lookup"><span data-stu-id="55cf0-205">complianceState</span></span>|<span data-ttu-id="55cf0-206">Die Zeichenfolge TRUE oder FALSE, die angibt, ob das Gerät kompatibel ist oder nicht.</span><span class="sxs-lookup"><span data-stu-id="55cf0-206">The true or false string that indicates whether the device is compliant or noncompliant.</span></span>|
|<span data-ttu-id="55cf0-207">isManaged</span><span class="sxs-lookup"><span data-stu-id="55cf0-207">isManaged</span></span>|<span data-ttu-id="55cf0-208">Die Zeichenfolge TRUE oder FALSE, die angibt, ob der Client durch Intune verwaltet wird oder nicht.</span><span class="sxs-lookup"><span data-stu-id="55cf0-208">The true or false string that indicates whether the client is managed by Intune or not.</span></span>|
|<span data-ttu-id="55cf0-209">macAddress</span><span class="sxs-lookup"><span data-stu-id="55cf0-209">macAddress</span></span>|<span data-ttu-id="55cf0-210">Die MAC-Adresse des Geräts.</span><span class="sxs-lookup"><span data-stu-id="55cf0-210">The MAC address of the device.</span></span>|
|<span data-ttu-id="55cf0-211">serialNumber</span><span class="sxs-lookup"><span data-stu-id="55cf0-211">serialNumber</span></span>|<span data-ttu-id="55cf0-212">Die Seriennummer des Geräts.</span><span class="sxs-lookup"><span data-stu-id="55cf0-212">The serial number of the device.</span></span> <span data-ttu-id="55cf0-213">Gilt nur für iOS-Geräte.</span><span class="sxs-lookup"><span data-stu-id="55cf0-213">It applies only to iOS devices.</span></span>|
|<span data-ttu-id="55cf0-214">imei</span><span class="sxs-lookup"><span data-stu-id="55cf0-214">imei</span></span>|<span data-ttu-id="55cf0-215">Die IMEI-Nummer (15 Dezimalzahlen: 14 Ziffern plus eine Prüfziffer) oder IMEISV-Nummer (16 Ziffern) enthält Informationen zum Ursprung, Modell und der Seriennummer des Geräts.</span><span class="sxs-lookup"><span data-stu-id="55cf0-215">The IMEI (15 decimal digits: 14 digits plus a check digit) or IMEISV (16 digits) number includes information on the origin, model, and serial number of the device.</span></span> <span data-ttu-id="55cf0-216">Die Struktur dieser Nummer ist in 3GPP TS 23.003 angegeben.</span><span class="sxs-lookup"><span data-stu-id="55cf0-216">The structure of this number is specified in 3GPP TS 23.003.</span></span> <span data-ttu-id="55cf0-217">Gilt nur für Geräte mit SIM-Karten.</span><span class="sxs-lookup"><span data-stu-id="55cf0-217">It applies only to devices with SIM cards.</span></span>|
|<span data-ttu-id="55cf0-218">udid</span><span class="sxs-lookup"><span data-stu-id="55cf0-218">udid</span></span>|<span data-ttu-id="55cf0-219">Die eindeutige Geräte-ID (unique device identifier; UDID) ist eine Sequenz von 40 Buchstaben und Zahlen.</span><span class="sxs-lookup"><span data-stu-id="55cf0-219">The Unique Device Identifier, which is a sequence of 40 letters and numbers.</span></span> <span data-ttu-id="55cf0-220">Dies ist spezifisch für iOS-Geräte.</span><span class="sxs-lookup"><span data-stu-id="55cf0-220">It is specific to iOS devices.</span></span>|
|<span data-ttu-id="55cf0-221">meid</span><span class="sxs-lookup"><span data-stu-id="55cf0-221">meid</span></span>|<span data-ttu-id="55cf0-222">Mobile Equipment Identifier, eine global eindeutige Identifikationsnummer eines physischen Arbeitsgeräts einer mobilen CDMA-Station.</span><span class="sxs-lookup"><span data-stu-id="55cf0-222">The mobile equipment identifier, which is a globally unique number that identifies a physical piece of CDMA mobile station equipment.</span></span> <span data-ttu-id="55cf0-223">Das Zahlenformat wird durch den Bericht „S.R0048“ des Gremiums 3GPP2 definiert.</span><span class="sxs-lookup"><span data-stu-id="55cf0-223">The number format is defined by the 3GPP2 report S. R0048.</span></span> <span data-ttu-id="55cf0-224">Für die praktische Anwendung kann es auch als eine IMEI mit hexadezimalen Zahlen betrachtet werden.</span><span class="sxs-lookup"><span data-stu-id="55cf0-224">However, in practical terms, it can be seen as an IMEI, but with hexadecimal digits.</span></span> <span data-ttu-id="55cf0-225">Ein MEID ist 56 Bits lang (14 hexadeximale Zahlen).</span><span class="sxs-lookup"><span data-stu-id="55cf0-225">An MEID is 56 bits long (14 hex digits).</span></span> <span data-ttu-id="55cf0-226">Er besteht aus drei Feldern, inklusive einem 8-Bit-Regionscode (RR), einem 24-Bit-Herstellercode und einer vom Hersteller vergebenen 24-Bit Seriennummer.</span><span class="sxs-lookup"><span data-stu-id="55cf0-226">It consists of three fields, including an 8-bit regional code (RR), a 24-bit manufacturer code, and a 24-bit manufacturer-assigned serial number.</span></span>|
|<span data-ttu-id="55cf0-227">osVersion</span><span class="sxs-lookup"><span data-stu-id="55cf0-227">osVersion</span></span>|<span data-ttu-id="55cf0-228">Die Betriebssystemversion für das Gerät.</span><span class="sxs-lookup"><span data-stu-id="55cf0-228">The operating system version for the device.</span></span>
|<span data-ttu-id="55cf0-229">model</span><span class="sxs-lookup"><span data-stu-id="55cf0-229">model</span></span>|<span data-ttu-id="55cf0-230">Das Gerätemodell.</span><span class="sxs-lookup"><span data-stu-id="55cf0-230">The device model.</span></span>
|<span data-ttu-id="55cf0-231">Hersteller</span><span class="sxs-lookup"><span data-stu-id="55cf0-231">manufacturer</span></span>|<span data-ttu-id="55cf0-232">Der Hersteller des Geräts.</span><span class="sxs-lookup"><span data-stu-id="55cf0-232">The device manufacturer.</span></span>
|<span data-ttu-id="55cf0-233">azureDeviceId</span><span class="sxs-lookup"><span data-stu-id="55cf0-233">azureDeviceId</span></span>|<span data-ttu-id="55cf0-234">Die Geräte-ID, nach der Arbeitsplatzeinbindung mit Azure AD.</span><span class="sxs-lookup"><span data-stu-id="55cf0-234">The device ID after it has workplace joined with Azure AD.</span></span> <span data-ttu-id="55cf0-235">Ist für nicht verknüpfte Geräte eine leere GUID.</span><span class="sxs-lookup"><span data-stu-id="55cf0-235">It is an empty GUID for devices that are not joined.</span></span>|
|<span data-ttu-id="55cf0-236">lastContactTimeUtc</span><span class="sxs-lookup"><span data-stu-id="55cf0-236">lastContactTimeUtc</span></span>|<span data-ttu-id="55cf0-237">Das Datum und die Uhrzeit, zu der das Gerät sich das letzte Mal beim Intune-Verwaltungsdienst gemeldet hat.</span><span class="sxs-lookup"><span data-stu-id="55cf0-237">The date and time when the device last checked in with the Intune management service.</span></span>


## <a name="user-experience"></a><span data-ttu-id="55cf0-238">Benutzerfreundlichkeit</span><span class="sxs-lookup"><span data-stu-id="55cf0-238">User experience</span></span>

<span data-ttu-id="55cf0-239">Wenn ein Benutzer versucht, auf Ressourcen mittels eines Gerätes zuzugreifen, das nicht registriert ist, wird er zur Registrierung aufgefordert, so wie hier gezeigt.</span><span class="sxs-lookup"><span data-stu-id="55cf0-239">When a user attempts to access resources by using an unenrolled device, they receive a prompt to enroll, such as the one shown here:</span></span>

![Beispiel für eine Registrierungsaufforderung](../media/cisco-ise-user-iphone.png)

<span data-ttu-id="55cf0-241">Wenn der Benutzer sich für die Registrierung entscheidet, wird er zum Intune-Registrierungsprozess umgeleitet.</span><span class="sxs-lookup"><span data-stu-id="55cf0-241">When a user chooses to enroll, they are redirected to the Intune enrollment process.</span></span> <span data-ttu-id="55cf0-242">Die benutzerfreundliche Registrierung für Intune wird in den folgenden Themen beschrieben:</span><span class="sxs-lookup"><span data-stu-id="55cf0-242">The user enrollment experience for Intune is described in these topics:</span></span>

- [<span data-ttu-id="55cf0-243">Registrieren Ihres Android-Geräts bei Intune</span><span class="sxs-lookup"><span data-stu-id="55cf0-243">Enroll your Android device in Intune</span></span>](/intune-user-help/enroll-your-device-in-Intune-android)</br>
- [<span data-ttu-id="55cf0-244">Registrieren Ihres iOS-Geräts bei Intune</span><span class="sxs-lookup"><span data-stu-id="55cf0-244">Enroll your iOS device in Intune</span></span>](/intune-user-help/enroll-your-device-in-intune-ios)</br>
- [<span data-ttu-id="55cf0-245">Registrieren Ihres Mac OS X-Geräts bei Intune</span><span class="sxs-lookup"><span data-stu-id="55cf0-245">Enroll your Mac OS X device in Intune</span></span>](/intune-user-help/enroll-your-device-in-intune-mac-os-x)</br>
- [<span data-ttu-id="55cf0-246">Registrieren Ihres Windows-Geräts bei Intune</span><span class="sxs-lookup"><span data-stu-id="55cf0-246">Enroll your Windows device in Intune</span></span>](/intune-user-help/enroll-your-device-in-intune-windows)</br>

<span data-ttu-id="55cf0-247">Es gibt auch [herunterladbare Registrierungsanweisungen](https://gallery.technet.microsoft.com/End-user-Intune-enrollment-55dfd64a), die Sie verwenden können, um einen angepassten Leitfaden für Ihre Benutzerfreundlichkeit zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="55cf0-247">There is also a [downloadable set of enrollment instructions](https://gallery.technet.microsoft.com/End-user-Intune-enrollment-55dfd64a) that you can use to create customized guidance for your user experience.</span></span>


### <a name="see-also"></a><span data-ttu-id="55cf0-248">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="55cf0-248">See also</span></span>

[<span data-ttu-id="55cf0-249">Cisco Identity Services Engine-Administratorhandbuch, Version 2.1</span><span class="sxs-lookup"><span data-stu-id="55cf0-249">Cisco Identity Services Engine Administrator Guide, Release 2.1</span></span>](http://www.cisco.com/c/en/us/td/docs/security/ise/2-1/admin_guide/b_ise_admin_guide_21/b_ise_admin_guide_20_chapter_01000.html#task_820C9C2A1A6647E995CA5AAB01E1CDEF)
