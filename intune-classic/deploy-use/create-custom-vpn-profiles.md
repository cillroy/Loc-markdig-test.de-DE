---
title: "Benutzerdefinierte Konfigurationen für Microsoft Intune-VPN-Profile"
description: Verwenden Sie benutzerdefinierte Konfigurationen, um VPN-Profile in Intune zu erstellen.
keywords: 
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 12/15/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4c0bd439-3b58-420b-9a9a-282886986786
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: karanda
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 3c04fcdadbc3ec2e121b4718b950a7e5e58700fe
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2017
---
# <a name="custom-configurations-for-microsoft-intune-vpn-profiles"></a><span data-ttu-id="7bcef-103">Benutzerdefinierte Konfigurationen für Microsoft Intune-VPN-Profile</span><span class="sxs-lookup"><span data-stu-id="7bcef-103">Custom configurations for Microsoft Intune VPN profiles</span></span>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

## <a name="create-a-custom-configuration"></a><span data-ttu-id="7bcef-104">Erstellen einer benutzerdefinierten Konfiguration</span><span class="sxs-lookup"><span data-stu-id="7bcef-104">Create a custom configuration</span></span>
<span data-ttu-id="7bcef-105">Sie können benutzerdefinierte Intune-Konfigurationsrichtlinien verwenden, um VPN-Profile für folgende Geräte zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="7bcef-105">You can use Intune custom configuration polices to create VPN profiles for:</span></span>

* <span data-ttu-id="7bcef-106">Geräte unter Android 4 und höher</span><span class="sxs-lookup"><span data-stu-id="7bcef-106">Devices that run Android 4 and later</span></span>
* <span data-ttu-id="7bcef-107">Android for Work-Geräte</span><span class="sxs-lookup"><span data-stu-id="7bcef-107">Android for Work devices</span></span>
* <span data-ttu-id="7bcef-108">Registrierte Geräte unter Windows 8.1 und höher</span><span class="sxs-lookup"><span data-stu-id="7bcef-108">Enrolled devices that run Windows 8.1 and later</span></span>
* <span data-ttu-id="7bcef-109">Geräte unter Windows Phone 8.1 und höher</span><span class="sxs-lookup"><span data-stu-id="7bcef-109">Devices that run Windows Phone 8.1 and later</span></span>
* <span data-ttu-id="7bcef-110">Registrierte Geräte unter Windows 10 Desktop</span><span class="sxs-lookup"><span data-stu-id="7bcef-110">Enrolled devices that run Windows 10 desktop</span></span>
* <span data-ttu-id="7bcef-111">Geräte unter Windows 10 Mobile</span><span class="sxs-lookup"><span data-stu-id="7bcef-111">Device that run Windows 10 Mobile</span></span>

<span data-ttu-id="7bcef-112">Dieser Richtlinientyp kann hilfreich sein, wenn die standardmäßigen Intune-VPN-Richtlinien nicht die Einstellungen enthalten, die Sie verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="7bcef-112">This type of policy can be useful when the standard Intune VPN policies do not contain the settings you want to use.</span></span>

## <a name="to-create-a-custom-configuration-policy"></a><span data-ttu-id="7bcef-113">So erstellen Sie eine benutzerdefinierte Konfigurationsrichtlinie:</span><span class="sxs-lookup"><span data-stu-id="7bcef-113">To create a custom configuration policy:</span></span>

   1. <span data-ttu-id="7bcef-114">Wählen Sie in der [Intune-Verwaltungskonsole](https://manage.microsoft.com) die Optionen **Richtlinie** > **Richtlinie hinzufügen** > *Plattform erweitern* > **Benutzerdefinierte Konfiguration** > **Richtlinie erstellen** aus.</span><span class="sxs-lookup"><span data-stu-id="7bcef-114">In the [Intune admin console](https://manage.microsoft.com), choose **Policy** > **Add Policy** > *Expand platform* > **Custom configuration** > **Create Policy**.</span></span>
   2. <span data-ttu-id="7bcef-115">Geben Sie einen Namen für die Richtlinie ein.</span><span class="sxs-lookup"><span data-stu-id="7bcef-115">Enter a name for the policy.</span></span>
   3. <span data-ttu-id="7bcef-116">Wählen Sie für jede URI-Einstellung, die Sie festlegen möchten, die Option **Hinzufügen** aus, und geben Sie die erforderlichen Informationen an.</span><span class="sxs-lookup"><span data-stu-id="7bcef-116">For each URI setting you want to specify, choose **Add**, and provide the requested information.</span></span> <span data-ttu-id="7bcef-117">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="7bcef-117">Here's an example:</span></span>

   ![Dialogfeld „Benutzerdefinierte VPN-Profilkonfiguration“](./media/Intune_Add_VPN_URI.png)

   4.  <span data-ttu-id="7bcef-119">Nachdem Sie alle URI-Einstellungen eingegeben haben, wählen Sie **Richtlinie speichern** aus, und stellen Sie die Richtlinie anschließend bereit.</span><span class="sxs-lookup"><span data-stu-id="7bcef-119">After you've entered all of URI settings, choose **Save policy**, and then deploy the policy.</span></span>

<span data-ttu-id="7bcef-120">[Stellen Sie die Richtlinie dann wie immer bereit](/intune-classic/deploy-use/manage-settings-and-features-on-your-devices-with-microsoft-intune-policies#deploy-a-configuration-policy).</span><span class="sxs-lookup"><span data-stu-id="7bcef-120">Then, [deploy the policy](/intune-classic/deploy-use/manage-settings-and-features-on-your-devices-with-microsoft-intune-policies#deploy-a-configuration-policy) as normal.</span></span>

## <a name="example-uri-settings"></a><span data-ttu-id="7bcef-121">Beispiel für URI-Einstellungen</span><span class="sxs-lookup"><span data-stu-id="7bcef-121">Example URI settings</span></span>

<span data-ttu-id="7bcef-122">Diese Einstellungen können verwendet werden, um eine benutzerdefinierte Konfiguration für ein VPN in einem fiktiven Unternehmen namens Contoso zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="7bcef-122">These settings can be used to create a custom configuration for a VPN in a fictitious company called Contoso.</span></span>
<span data-ttu-id="7bcef-123">Details zu allen verfügbaren Einstellungen finden Sie unter [VPNv2 CSP](https://msdn.microsoft.com/library/windows/hardware/dn914776.aspx).</span><span class="sxs-lookup"><span data-stu-id="7bcef-123">For full details about all the settings you can use, see [VPNv2 CSP](https://msdn.microsoft.com/library/windows/hardware/dn914776.aspx).</span></span>

<span data-ttu-id="7bcef-124">**Natives Contoso-VPN (IKEv2):**</span><span class="sxs-lookup"><span data-stu-id="7bcef-124">**Native Contoso VPN (IKEv2):**</span></span><br />
<span data-ttu-id="7bcef-125">./Vendor/MSFT/VPNv2/ContosoVPN/NativeProfile/Servers</span><span class="sxs-lookup"><span data-stu-id="7bcef-125">./Vendor/MSFT/VPNv2/ContosoVPN/NativeProfile/Servers</span></span>

<span data-ttu-id="7bcef-126">**vpn.contoso.com**</span><span class="sxs-lookup"><span data-stu-id="7bcef-126">**vpn.contoso.com**</span></span><br />
<span data-ttu-id="7bcef-127">./Vendor/MSFT/VPNv2/ContosoVPN/NativeProfile/NativeProtocolType</span><span class="sxs-lookup"><span data-stu-id="7bcef-127">./Vendor/MSFT/VPNv2/ContosoVPN/NativeProfile/NativeProtocolType</span></span>

<span data-ttu-id="7bcef-128">**Ikev2<br />** ./Vendor/MSFT/VPNv2/ContosoVPN/NativeProfile/RoutingPolicyType</span><span class="sxs-lookup"><span data-stu-id="7bcef-128">**Ikev2<br />** ./Vendor/MSFT/VPNv2/ContosoVPN/NativeProfile/RoutingPolicyType</span></span>

<span data-ttu-id="7bcef-129">**SplitTunnel**</span><span class="sxs-lookup"><span data-stu-id="7bcef-129">**SplitTunnel**</span></span><br />
<span data-ttu-id="7bcef-130">./Vendor/MSFT/VPNv2/ContosoVPN/NativeProfile/Authentication/UserMethod</span><span class="sxs-lookup"><span data-stu-id="7bcef-130">./Vendor/MSFT/VPNv2/ContosoVPN/NativeProfile/Authentication/UserMethod</span></span>

<span data-ttu-id="7bcef-131">**Eap**</span><span class="sxs-lookup"><span data-stu-id="7bcef-131">**Eap**</span></span><br />
<span data-ttu-id="7bcef-132">./Vendor/MSFT/VPNv2/ContosoVPN/NativeProfile/Authentication/Eap/Configuration</span><span class="sxs-lookup"><span data-stu-id="7bcef-132">./Vendor/MSFT/VPNv2/ContosoVPN/NativeProfile/Authentication/Eap/Configuration</span></span>
``` xml
<EapHostConfig xmlns="http://www.microsoft.com/provisioning/EapHostConfig">
   <EapMethod>
      <Type xmlns="http://www.microsoft.com/provisioning/EapCommon">13</Type>
      <VendorId xmlns="http://www.microsoft.com/provisioning/EapCommon">0</VendorId>
      <VendorType xmlns="http://www.microsoft.com/provisioning/EapCommon">0</VendorType>
      <AuthorId xmlns="http://www.microsoft.com/provisioning/EapCommon">0</AuthorId>
   </EapMethod>
   <Config xmlns="http://www.microsoft.com/provisioning/EapHostConfig">
      <Eap xmlns="http://www.microsoft.com/provisioning/BaseEapConnectionPropertiesV1">
         <Type>13</Type>
         <EapType xmlns="http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV1">
            <CredentialsSource>
               <CertificateStore>
                  <SimpleCertSelection>true</SimpleCertSelection>
               </CertificateStore>
            </CredentialsSource>
            <ServerValidation>
               <DisableUserPromptForServerValidation>false</DisableUserPromptForServerValidation>
               <ServerNames></ServerNames>
            </ServerValidation>
            <DifferentUsername>false</DifferentUsername>
            <PerformServerValidation xmlns="http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV2">
               false
            </PerformServerValidation>
            <AcceptServerName xmlns="http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV2">
               false
            </AcceptServerName>
         </EapType>
      </Eap>
   </Config>
</EapHostConfig>
```
<span data-ttu-id="7bcef-133">**./Vendor/MSFT/VPNv2/ContosoVPN/ByPassForLocal**</span><span class="sxs-lookup"><span data-stu-id="7bcef-133">**./Vendor/MSFT/VPNv2/ContosoVPN/ByPassForLocal**</span></span><br />
<span data-ttu-id="7bcef-134">True</span><span class="sxs-lookup"><span data-stu-id="7bcef-134">True</span></span>

<span data-ttu-id="7bcef-135">**./Vendor/MSFT/VPNv2/ContosoVPN/RememberCredentials**</span><span class="sxs-lookup"><span data-stu-id="7bcef-135">**./Vendor/MSFT/VPNv2/ContosoVPN/RememberCredentials**</span></span><br />
<span data-ttu-id="7bcef-136">1</span><span class="sxs-lookup"><span data-stu-id="7bcef-136">1</span></span>

<span data-ttu-id="7bcef-137">**./Vendor/MSFT/VPNv2/ContosoVPN/DomainNameInformationList/1/DomainName**</span><span class="sxs-lookup"><span data-stu-id="7bcef-137">**./Vendor/MSFT/VPNv2/ContosoVPN/DomainNameInformationList/1/DomainName**</span></span><br />
<span data-ttu-id="7bcef-138">Corp.Contoso.com</span><span class="sxs-lookup"><span data-stu-id="7bcef-138">Corp.Contoso.com</span></span>

<span data-ttu-id="7bcef-139">**./Vendor/MSFT/VPNv2/ContosoVPN/DnsSuffix**</span><span class="sxs-lookup"><span data-stu-id="7bcef-139">**./Vendor/MSFT/VPNv2/ContosoVPN/DnsSuffix**</span></span><br />
<span data-ttu-id="7bcef-140">Corp.Contoso.com</span><span class="sxs-lookup"><span data-stu-id="7bcef-140">Corp.Contoso.com</span></span>

<span data-ttu-id="7bcef-141">**./Vendor/MSFT/VPNv2/ContosoVPN/TrustedNetworkDetection**</span><span class="sxs-lookup"><span data-stu-id="7bcef-141">**./Vendor/MSFT/VPNv2/ContosoVPN/TrustedNetworkDetection**</span></span><br />
<span data-ttu-id="7bcef-142">Corp.Contoso.com</span><span class="sxs-lookup"><span data-stu-id="7bcef-142">Corp.Contoso.com</span></span>

<span data-ttu-id="7bcef-143">**./Vendor/MSFT/VPNv2/ContosoVPN/RouteList/1/Address**</span><span class="sxs-lookup"><span data-stu-id="7bcef-143">**./Vendor/MSFT/VPNv2/ContosoVPN/RouteList/1/Address**</span></span><br />
<span data-ttu-id="7bcef-144">10.0.0.0</span><span class="sxs-lookup"><span data-stu-id="7bcef-144">10.0.0.0</span></span>

<span data-ttu-id="7bcef-145">**./Vendor/MSFT/VPNv2/ContosoVPN/RouteList/1/PrefixSize**</span><span class="sxs-lookup"><span data-stu-id="7bcef-145">**./Vendor/MSFT/VPNv2/ContosoVPN/RouteList/1/PrefixSize**</span></span><br />
<span data-ttu-id="7bcef-146">8</span><span class="sxs-lookup"><span data-stu-id="7bcef-146">8</span></span>

<span data-ttu-id="7bcef-147">**./Vendor/MSFT/VPNv2/ContosoVPN/AlwaysOn**</span><span class="sxs-lookup"><span data-stu-id="7bcef-147">**./Vendor/MSFT/VPNv2/ContosoVPN/AlwaysOn**</span></span><br />
<span data-ttu-id="7bcef-148">true</span><span class="sxs-lookup"><span data-stu-id="7bcef-148">true</span></span>

<span data-ttu-id="7bcef-149">**./Vendor/MSFT/VPNv2/ContosoVPN/AppTriggerList/0/App/Id**</span><span class="sxs-lookup"><span data-stu-id="7bcef-149">**./Vendor/MSFT/VPNv2/ContosoVPN/AppTriggerList/0/App/Id**</span></span><br />
<span data-ttu-id="7bcef-150">%PROGRAMFILES%\Internet Explorer\iexplore.exe</span><span class="sxs-lookup"><span data-stu-id="7bcef-150">%PROGRAMFILES%\Internet Explorer\iexplore.exe</span></span>

<span data-ttu-id="7bcef-151">**./Vendor/MSFT/VPNv2/ContosoVPN/AppTriggerList/1/App/Id**</span><span class="sxs-lookup"><span data-stu-id="7bcef-151">**./Vendor/MSFT/VPNv2/ContosoVPN/AppTriggerList/1/App/Id**</span></span><br />
<span data-ttu-id="7bcef-152">%PROGRAMFILES% (x86)\Internet Explorer\iexplore.exe</span><span class="sxs-lookup"><span data-stu-id="7bcef-152">%PROGRAMFILES% (x86)\Internet Explorer\iexplore.exe</span></span>

<span data-ttu-id="7bcef-153">**./Vendor/MSFT/VPNv2/ContosoVPN/AppTriggerList/2/App/Id**</span><span class="sxs-lookup"><span data-stu-id="7bcef-153">**./Vendor/MSFT/VPNv2/ContosoVPN/AppTriggerList/2/App/Id**</span></span><br />
<span data-ttu-id="7bcef-154">Microsoft.MicrosoftEdge_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="7bcef-154">Microsoft.MicrosoftEdge_8wekyb3d8bbwe</span></span>

<span data-ttu-id="7bcef-155">**./Vendor/MSFT/VPNv2/ContosoVPN/TrafficFilterList/0/App/Id**</span><span class="sxs-lookup"><span data-stu-id="7bcef-155">**./Vendor/MSFT/VPNv2/ContosoVPN/TrafficFilterList/0/App/Id**</span></span><br />
<span data-ttu-id="7bcef-156">%PROGRAMFILES% (x86)\Internet Explorer\iexplore.exe</span><span class="sxs-lookup"><span data-stu-id="7bcef-156">%PROGRAMFILES% (x86)\Internet Explorer\iexplore.exe</span></span>

<span data-ttu-id="7bcef-157">**./Vendor/MSFT/VPNv2/ContosoVPN/TrafficFilterList/1/App/Id**</span><span class="sxs-lookup"><span data-stu-id="7bcef-157">**./Vendor/MSFT/VPNv2/ContosoVPN/TrafficFilterList/1/App/Id**</span></span><br />
<span data-ttu-id="7bcef-158">Microsoft.MicrosoftEdge_8wekyb3d8bbwe</span><span class="sxs-lookup"><span data-stu-id="7bcef-158">Microsoft.MicrosoftEdge_8wekyb3d8bbwe</span></span>

<span data-ttu-id="7bcef-159">Fragen zur Verwendung dieser Einstellungen und weitere Details zu ihrer Funktion finden Kunden in der [Dokumentation des Konfigurationsdienstanbieters](https://msdn.microsoft.com/library/windows/hardware/dn914776(v=vs.85).aspx).</span><span class="sxs-lookup"><span data-stu-id="7bcef-159">For any questions about how these settings should be used or more details about what they do, customers should refer to the [configuration service provider (CSP) documentation](https://msdn.microsoft.com/library/windows/hardware/dn914776(v=vs.85).aspx).</span></span>

## <a name="uri-settings-for-android-per-app-vpn-on-pulsesecure"></a><span data-ttu-id="7bcef-160">URI-Einstellungen für Android pro App VPN auf PulseSecure</span><span class="sxs-lookup"><span data-stu-id="7bcef-160">URI settings for Android per-app VPN on PulseSecure</span></span>
### <a name="custom-uri-for-package-list"></a><span data-ttu-id="7bcef-161">BENUTZERDEFINIERTE URI FÜR DIE PAKETLISTE</span><span class="sxs-lookup"><span data-stu-id="7bcef-161">CUSTOM URI FOR PACKAGE LIST</span></span>
-  <span data-ttu-id="7bcef-162">Datentyp = String</span><span class="sxs-lookup"><span data-stu-id="7bcef-162">Data type = String</span></span>
-  <span data-ttu-id="7bcef-163">OMA-URI = ./Vendor/MSFT/VPN/Profile/Name/PackageList</span><span class="sxs-lookup"><span data-stu-id="7bcef-163">OMA-URI = ./Vendor/MSFT/VPN/Profile/Name/PackageList</span></span>
-  <span data-ttu-id="7bcef-164">Wert = durch Trennzeichen getrennte Paketliste.</span><span class="sxs-lookup"><span data-stu-id="7bcef-164">Value = Delimiter separated package list.</span></span>
   - <span data-ttu-id="7bcef-165">Trennzeichen: Semikolon (;), Doppelpunkt (:), Komma (,), senkrechter Strich (|)</span><span class="sxs-lookup"><span data-stu-id="7bcef-165">Delimiters:  semicolon (;), colon (:), comma (,), Pipe (|)</span></span>

<span data-ttu-id="7bcef-166">Beispiele:</span><span class="sxs-lookup"><span data-stu-id="7bcef-166">Examples:</span></span>
- <span data-ttu-id="7bcef-167">com.android.chrome</span><span class="sxs-lookup"><span data-stu-id="7bcef-167">com.android.chrome</span></span>
- <span data-ttu-id="7bcef-168">com.android.chrome;com.android.browser</span><span class="sxs-lookup"><span data-stu-id="7bcef-168">com.android.chrome;com.android.browser</span></span>

### <a name="custom-uri-for-mode-optional"></a><span data-ttu-id="7bcef-169">BENUTZERDEFINIERTE URI FÜR MODUS (OPTIONAL)</span><span class="sxs-lookup"><span data-stu-id="7bcef-169">CUSTOM URI FOR MODE (OPTIONAL)</span></span>
- <span data-ttu-id="7bcef-170">Datentyp = String</span><span class="sxs-lookup"><span data-stu-id="7bcef-170">Data Type = String</span></span>
- <span data-ttu-id="7bcef-171">OMA-URI = ./Vendor/MSFT/VPN/Profile/NAME/Mode</span><span class="sxs-lookup"><span data-stu-id="7bcef-171">OMA-URI = ./Vendor/MSFT/VPN/Profile/NAME/Mode</span></span>

> <span data-ttu-id="7bcef-172">Hinweise</span><span class="sxs-lookup"><span data-stu-id="7bcef-172">Notes</span></span>
> - <span data-ttu-id="7bcef-173">Verwenden Sie den gleichen *Namen*, dem Sie dem benutzerdefinierten Profil zugewiesen haben.</span><span class="sxs-lookup"><span data-stu-id="7bcef-173">Use the same *name* that you assigned to the custom profile</span></span>
> - <span data-ttu-id="7bcef-174">Mögliche Werte: *GLOBAL*, *WHITELIST*, *BLACKLIST*</span><span class="sxs-lookup"><span data-stu-id="7bcef-174">Possible values: *GLOBAL*, *WHITELIST*, *BLACKLIST*</span></span>
> - <span data-ttu-id="7bcef-175">Der Standardlist ist *GLOBAL*, wenn keine PackageList angegeben ist (Abwärtskompatibilität mit systemweiten Profilen)</span><span class="sxs-lookup"><span data-stu-id="7bcef-175">Defaults to *GLOBAL* if no PackageList is provided (backward compatibility with system-wide profiles)</span></span>
> - <span data-ttu-id="7bcef-176">Standardmäßig *WHITELIST*, wenn eine PackageList angegeben ist</span><span class="sxs-lookup"><span data-stu-id="7bcef-176">Defaults to *WHITELIST* if a PackageList is provided</span></span>


### <a name="see-also"></a><span data-ttu-id="7bcef-177">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="7bcef-177">See also</span></span>
[<span data-ttu-id="7bcef-178">VPN-Verbindungen in Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="7bcef-178">VPN connections in Microsoft Intune</span></span>](vpn-connections-in-microsoft-intune.md)
