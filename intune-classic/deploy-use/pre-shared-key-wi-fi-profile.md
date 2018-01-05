---
title: "WLAN über PSK"
description: "Erstellen Sie anhand der benutzerdefinierten Konfiguration ein WLAN-Profil mit einem vorinstallierten Schlüssel."
keywords: 
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 10/25/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e977c7c7-e204-47a6-b851-7ad7673ceaab
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: karanda
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 57dff55b7c5a4f9041b618a15cf3f8e22781a62a
ms.sourcegitcommit: e37e916e2bf14f092d3a767bc90d68c181d739fb
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/03/2018
---
# <a name="use-a-custom-policy-to-create-a-wi-fi-profile-with-a-pre-shared-key"></a><span data-ttu-id="e6589-103">Verwenden einer benutzerdefinierten Richtlinie zum Erstellen eines WLAN-Profils mit einem vorinstallierten Schlüssel</span><span class="sxs-lookup"><span data-stu-id="e6589-103">Use a custom policy to create a Wi-Fi profile with a pre-shared key</span></span>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="e6589-104">Hier wird erläutert, wie Sie anhand der **benutzerdefinierten Konfiguration** von Intune ein WLAN-Profil mit einem vorinstallierten Schlüssel erstellen.</span><span class="sxs-lookup"><span data-stu-id="e6589-104">Here's how to use Intune’s **Custom Configuration** to create a Wi-Fi profile with a pre-shared key.</span></span> <span data-ttu-id="e6589-105">Dieses Thema umfasst außerdem ein Beispiel für die Erstellung eines EAP-basierten WLAN-Profils.</span><span class="sxs-lookup"><span data-stu-id="e6589-105">This topic also has an example of how to create an EAP-based Wi-Fi profile.</span></span>

> [!NOTE]
> -   <span data-ttu-id="e6589-106">Möglicherweise ist es für Sie einfacher, den Code von einem Computer zu kopieren, der eine Verbindung mit dem jeweiligen Netzwerk herstellt, wie unten beschrieben.</span><span class="sxs-lookup"><span data-stu-id="e6589-106">You might find it easier to copy the code from a computer that connects to that network, as described below.</span></span>
> - <span data-ttu-id="e6589-107">Bei Android haben Sie auch die Möglichkeit, diesen von Johnathon Biersack bereitgestellten [Android PSK Generator](http://johnathonb.com/2015/05/intune-android-pre-shared-key-generator/) zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="e6589-107">For Android, you also have the option of using this [Android PSK Generator](http://johnathonb.com/2015/05/intune-android-pre-shared-key-generator/) provided by Johnathon Biersack.</span></span>
> -   <span data-ttu-id="e6589-108">Sie können mehrere Netzwerke und Schlüssel hinzufügen, indem Sie weitere OMA-URI-Einstellungen hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="e6589-108">You can add multiple networks and keys by adding more OMA-URI settings.</span></span>
> -  <span data-ttu-id="e6589-109">Verwenden Sie für iOS den Apple Configurator auf einer Mac-Station, um das Profil einzurichten.</span><span class="sxs-lookup"><span data-stu-id="e6589-109">For iOS, use Apple Configurator on a Mac station to set up the profile.</span></span> <span data-ttu-id="e6589-110">Verwenden Sie alternativ diesen [iOS PSK Mobile Config Generator](http://johnathonb.com/2015/05/intune-ios-psk-mobile-config-generator/), der von Johnathon Biersack bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="e6589-110">Alternatively, use this [iOS PSK Mobile Config Generator](http://johnathonb.com/2015/05/intune-ios-psk-mobile-config-generator/) provided by Johnathon Biersack.</span></span>


1. <span data-ttu-id="e6589-111">Um ein WLAN-Profil mit einem vorinstallierten Schlüssel für Android oder Windows oder ein EAP-basiertes WLAN-Profil zu erstellen, wählen Sie beim Erstellen einer Richtlinie statt eines WLAN-Profils die Option **Benutzerdefinierte Konfiguration** für die jeweilige Geräteplattform aus.</span><span class="sxs-lookup"><span data-stu-id="e6589-111">To create a Wi-Fi profile with a pre-shared key for Android or Windows or an EAP-based Wi-Fi profile, when you create a policy choose **Custom Configuration** for that device platform rather than a Wi-Fi profile.</span></span>

2. <span data-ttu-id="e6589-112">Geben Sie einen Namen und eine Beschreibung an.</span><span class="sxs-lookup"><span data-stu-id="e6589-112">Provide a name and description.</span></span>
3. <span data-ttu-id="e6589-113">Fügen Sie eine neue OMA-URI-Einstellung hinzu:</span><span class="sxs-lookup"><span data-stu-id="e6589-113">Add a new OMA-URI setting:</span></span>

   <span data-ttu-id="e6589-114">ein.</span><span class="sxs-lookup"><span data-stu-id="e6589-114">a.</span></span>   <span data-ttu-id="e6589-115">Geben Sie einen Namen für diese WLAN-Netzwerkeinstellung ein.</span><span class="sxs-lookup"><span data-stu-id="e6589-115">Enter a name for this Wi-Fi network setting.</span></span>

   <span data-ttu-id="e6589-116">b.</span><span class="sxs-lookup"><span data-stu-id="e6589-116">b.</span></span>   <span data-ttu-id="e6589-117">Geben Sie eine Beschreibung für die OMA-URI-Einstellung ein, oder lassen Sie sie leer.</span><span class="sxs-lookup"><span data-stu-id="e6589-117">Enter a description of the OMA-URI setting or leave blank.</span></span>

   <span data-ttu-id="e6589-118">c.</span><span class="sxs-lookup"><span data-stu-id="e6589-118">c.</span></span>   <span data-ttu-id="e6589-119">**Datentyp**: Legen Sie diesen auf "String(XML)" fest.</span><span class="sxs-lookup"><span data-stu-id="e6589-119">**Data Type**: Set to "String(XML)"</span></span>

   <span data-ttu-id="e6589-120">d.</span><span class="sxs-lookup"><span data-stu-id="e6589-120">d.</span></span>   <span data-ttu-id="e6589-121">**OMA-URI**:</span><span class="sxs-lookup"><span data-stu-id="e6589-121">**OMA-URI**:</span></span>

   - <span data-ttu-id="e6589-122">**Für Android**: ./Vendor/MSFT/WiFi/Profile/<SSID>/Settings</span><span class="sxs-lookup"><span data-stu-id="e6589-122">**For Android**: ./Vendor/MSFT/WiFi/Profile/<SSID>/Settings</span></span>
   - <span data-ttu-id="e6589-123">**Für Windows**: ./Vendor/MSFT/WiFi/Profile/MyNetwork/WlanXml</span><span class="sxs-lookup"><span data-stu-id="e6589-123">**For Windows**: ./Vendor/MSFT/WiFi/Profile/MyNetwork/WlanXml</span></span>

   > [!NOTE]
   > <span data-ttu-id="e6589-124">Stellen Sie sicher, dass Sie den Punkt am Anfang eingeben.</span><span class="sxs-lookup"><span data-stu-id="e6589-124">Be sure to include the dot character at the beginning.</span></span>

   <span data-ttu-id="e6589-125">SSID steht für die SSID, für die Sie die Richtlinie erstellen.</span><span class="sxs-lookup"><span data-stu-id="e6589-125">SSID is the SSID for which you’re creating the policy.</span></span> <span data-ttu-id="e6589-126">Beispiel: `./Vendor/MSFT/WiFi/Profile/Hotspot-1/Settings`</span><span class="sxs-lookup"><span data-stu-id="e6589-126">For example, `./Vendor/MSFT/WiFi/Profile/Hotspot-1/Settings`</span></span>

   <span data-ttu-id="e6589-127">e.</span><span class="sxs-lookup"><span data-stu-id="e6589-127">e.</span></span> <span data-ttu-id="e6589-128">**Wertfeld** Hier fügen Sie Ihren XML-Code ein.</span><span class="sxs-lookup"><span data-stu-id="e6589-128">**Value Field** is where you paste your XML code.</span></span> <span data-ttu-id="e6589-129">Hier sehen Sie ein Beispiel.</span><span class="sxs-lookup"><span data-stu-id="e6589-129">Here’s an example.</span></span> <span data-ttu-id="e6589-130">Die einzelnen Werte sollten an Ihre Netzwerkeinstellungen angepasst werden.</span><span class="sxs-lookup"><span data-stu-id="e6589-130">Each value should be adapted to your network settings.</span></span> <span data-ttu-id="e6589-131">Einige Hinweise finden Sie im Kommentarabschnitt des Codes.</span><span class="sxs-lookup"><span data-stu-id="e6589-131">See the comments section of the code for some pointers.</span></span>
4. <span data-ttu-id="e6589-132">Wählen Sie **OK** aus, speichern Sie, und stellen Sie anschließend die Richtlinie bereit.</span><span class="sxs-lookup"><span data-stu-id="e6589-132">Choose **OK**, save, and then deploy the policy.</span></span>

    > [!NOTE]
    > <span data-ttu-id="e6589-133">Diese Richtlinie kann nur für Benutzergruppen bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="e6589-133">This policy can only be deployed to user groups.</span></span>

<span data-ttu-id="e6589-134">Wenn sich die einzelnen Geräte das nächste Mal anmelden, wird die Richtlinie angewendet, und auf dem Gerät wird ein WLAN-Profil erstellt.</span><span class="sxs-lookup"><span data-stu-id="e6589-134">The next time each device checks in, the policy will be applied, and a Wi-Fi profile will be created on the device.</span></span> <span data-ttu-id="e6589-135">Das Gerät kann automatisch eine Verbindung mit dem Netzwerk herstellen.</span><span class="sxs-lookup"><span data-stu-id="e6589-135">The device will be able to connect to the network automatically.</span></span>
## <a name="android-or-windows-wi-fi-profile"></a><span data-ttu-id="e6589-136">Android- oder Windows-WLAN-Profil</span><span class="sxs-lookup"><span data-stu-id="e6589-136">Android or Windows Wi-Fi profile</span></span>

<span data-ttu-id="e6589-137">Hier sehen Sie ein Beispiel für den XML-Code eines Android- oder Windows-WLAN-Profils:</span><span class="sxs-lookup"><span data-stu-id="e6589-137">Here’s an example of the XML code for an Android or Windows Wi-Fi profile:</span></span>

> [!IMPORTANT]
> 
> <span data-ttu-id="e6589-138">`<protected>false</protected>` muss auf **false** festgelegt werden, da **true** dazu führen könnte, dass das Gerät ein verschlüsseltes Kennwort erwartet, das es dann zu entschlüsseln versucht, was einen Verbindungsfehler bewirken würde.</span><span class="sxs-lookup"><span data-stu-id="e6589-138">`<protected>false</protected>`must be set to **false**, as **true** could cause device to expect an encrypted password and then try to decrypt it, which may result in a failed connection.</span></span>
> 
>  <span data-ttu-id="e6589-139">`<hex>53534944</hex>` sollte auf den hexadezimalen Wert von `<name><SSID of wifi profile></name>` festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="e6589-139">`<hex>53534944</hex>` should be set to the hexadecimal value of `<name><SSID of wifi profile></name>`.</span></span>
>  <span data-ttu-id="e6589-140">Windows 10-Geräte können fälschlicherweise den Fehler *0x87D1FDE8: Fehler bei Wiederherstellung* zurückgeben, werden aber dennoch mit dem Profil bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="e6589-140">Windows 10 devices may return a false *0x87D1FDE8 Remediation failed* error, but will still be provisioned with the profile.</span></span>

```
<!--
<Name of wifi profile> = Name of profile
<SSID of wifi profile> = Plain text of SSID. Does not need to be escaped, could be <name>Your Company's Network</name>
<nonBroadcast><true/false></nonBroadcast>
<Type of authentication> = Type of authentication used by the network, such as WPA2PSK.
<Type of encryption> = Type of encryption used by the network
<protected>false</protected> do not change this value, as true could cause device to expect an encrypted password and then try to decrypt it, which may result in a failed connection.
<password> = Password to connect to the network
<hex>53534944</hex> should be set to the hexadecimal value of <name><SSID of wifi profile></name>
-->
<WLANProfile
xmlns="http://www.microsoft.com/networking/WLAN/profile/v1">
  <name><Name of wifi profile></name>
  <SSIDConfig>
    <SSID>
      <hex>53534944</hex>
 <name><SSID of wifi profile></name>        </SSID>
        <nonBroadcast>false</nonBroadcast>
      </SSIDConfig>
      <connectionType>ESS</connectionType>
      <connectionMode>auto</connectionMode>
      <autoSwitch>false</autoSwitch>
      <MSM>
        <security>
          <authEncryption>
            <authentication><Type of authentication></authentication>
            <encryption><Type of encryption></encryption>
            <useOneX>false</useOneX>
          </authEncryption>
          <sharedKey>
            <keyType>networkKey</keyType>
            <protected>false</protected>
            <keyMaterial>MyPassword</keyMaterial>
          </sharedKey>
          <keyIndex>0</keyIndex>
        </security>
      </MSM>
    </WLANProfile>
```

## <a name="eap-based-wi-fi-profile"></a><span data-ttu-id="e6589-141">EAP-basiertes WLAN-Profil</span><span class="sxs-lookup"><span data-stu-id="e6589-141">EAP-based Wi-Fi profile</span></span>
<span data-ttu-id="e6589-142">Hier sehen Sie ein Beispiel für den XML-Code eines EAP-basierten WLAN-Profils:</span><span class="sxs-lookup"><span data-stu-id="e6589-142">Here’s  an example of the XML code for an EAP-based Wi-Fi profile:</span></span>

```
    <WLANProfile xmlns="http://www.microsoft.com/networking/WLAN/profile/v1">
      <name>testcert</name>
      <SSIDConfig>
        <SSID>
          <hex>7465737463657274</hex>
          <name>testcert</name>
        </SSID>
        <nonBroadcast>true</nonBroadcast>
      </SSIDConfig>
      <connectionType>ESS</connectionType>
      <connectionMode>auto</connectionMode>
      <autoSwitch>false</autoSwitch>
      <MSM>
        <security>
          <authEncryption>
            <authentication>WPA2</authentication>
            <encryption>AES</encryption>
            <useOneX>true</useOneX>
            <FIPSMode     xmlns="http://www.microsoft.com/networking/WLAN/profile/v2">false</FIPSMode>
          </authEncryption>
          <PMKCacheMode>disabled</PMKCacheMode>
          <OneX xmlns="http://www.microsoft.com/networking/OneX/v1">
            <cacheUserData>false</cacheUserData>
            <authMode>user</authMode>
            <EAPConfig>
              <EapHostConfig     xmlns="http://www.microsoft.com/provisioning/EapHostConfig">
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
                      <PerformServerValidation xmlns="http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV2">false</PerformServerValidation>
                      <AcceptServerName xmlns="http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV2">false</AcceptServerName>
                      <TLSExtensions xmlns="http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV2">
                        <FilteringInfo xmlns="http://www.microsoft.com/provisioning/EapTlsConnectionPropertiesV3">
                          <AllPurposeEnabled>true</AllPurposeEnabled>
                          <CAHashList Enabled="true">
                            <IssuerHash>75 f5 06 9c a4 12 0e 9b db bc a1 d9 9d d0 f0 75 fa 3b b8 78 </IssuerHash>
                          </CAHashList>
                          <EKUMapping>
                            <EKUMap>
                              <EKUName>Client Authentication</EKUName>
                              <EKUOID>1.3.6.1.5.5.7.3.2</EKUOID>
                            </EKUMap>
                          </EKUMapping>
                          <ClientAuthEKUList Enabled="true"/>
                          <AnyPurposeEKUList Enabled="false">
                            <EKUMapInList>
                              <EKUName>Client Authentication</EKUName>
                            </EKUMapInList>
                          </AnyPurposeEKUList>
                        </FilteringInfo>
                      </TLSExtensions>
                    </EapType>
                  </Eap>
                </Config>
              </EapHostConfig>
            </EAPConfig>
          </OneX>
        </security>
      </MSM>
    </WLANProfile>
```

## <a name="create-the-xml-file-from-an-existing-wi-fi-connection"></a><span data-ttu-id="e6589-143">Erstellen der XML-Datei aus einer vorhandenen WLAN-Verbindung</span><span class="sxs-lookup"><span data-stu-id="e6589-143">Create the XML file from an existing Wi-Fi connection</span></span>
<span data-ttu-id="e6589-144">Sie können die XML-Datei auch aus einer vorhandenen WLAN-Verbindung erstellen:</span><span class="sxs-lookup"><span data-stu-id="e6589-144">You can also create an XML file from an existing Wi-Fi connection:</span></span>
1. <span data-ttu-id="e6589-145">Öffnen Sie auf einem Computer, der mit dem WLAN verbunden ist oder vor kurzem damit verbunden war, den folgenden Ordner: „C:\ProgramData\Microsoft\Wlansvc\Profiles\Interfaces\{guid}“.</span><span class="sxs-lookup"><span data-stu-id="e6589-145">On a computer that is connected to or has recently connected to the wireless network, open the following folder: C:\ProgramData\Microsoft\Wlansvc\Profiles\Interfaces\{guid}.</span></span>

    <span data-ttu-id="e6589-146">Es wird empfohlen, einen Computer zu verwenden, der nicht mit allzu vielen WLANs verbunden ist, weil Sie die einzelnen Profile durchsuchen müssen, um das richtige zu finden.</span><span class="sxs-lookup"><span data-stu-id="e6589-146">It’s best to use a computer that has not connected to many wireless networks, because you’ll have to search through each profile to find the right one.</span></span>
2. <span data-ttu-id="e6589-147">Durchsuchen Sie die XML-Dateien, um die Datei mit dem richtigen Namen zu finden.</span><span class="sxs-lookup"><span data-stu-id="e6589-147">Search through the XML files to locate the one with the right name.</span></span>
3. <span data-ttu-id="e6589-148">Nachdem Sie die richtige XML-Datei gefunden haben, kopieren Sie den XML-Code in das Feld „Daten“ auf der Seite mit den OMA-URI-Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="e6589-148">After you have located the correct XML file, copy and paste the XML code into the Data field of the OMA-URI settings page.</span></span>

## <a name="deploy-the-policy"></a><span data-ttu-id="e6589-149">Bereitstellen der Richtlinie</span><span class="sxs-lookup"><span data-stu-id="e6589-149">Deploy the policy</span></span>

1.  <span data-ttu-id="e6589-150">Wählen Sie im Arbeitsbereich **Richtlinie** die Richtlinie aus, die Sie bereitstellen möchten, und wählen Sie dann **Bereitstellung verwalten** aus.</span><span class="sxs-lookup"><span data-stu-id="e6589-150">In the **Policy** workspace, select the policy that you want to deploy, and then choose **Manage Deployment**.</span></span>

2.  <span data-ttu-id="e6589-151">Führen Sie im Dialogfeld **Bereitstellung verwalten** folgende Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="e6589-151">In the **Manage Deployment** dialog box:</span></span>

    -   <span data-ttu-id="e6589-152">**So stellen Sie die Richtlinie bereit**: Wählen Sie mindestens eine Gruppe aus, für die Sie die Richtlinie bereitstellen möchten, und klicken Sie auf **Hinzufügen** &gt; **OK**.</span><span class="sxs-lookup"><span data-stu-id="e6589-152">**To deploy the policy** - Select one or more groups to which you want to deploy the policy, and then choose **Add** &gt; **OK**.</span></span>

    -   <span data-ttu-id="e6589-153">**So schließen Sie das Dialogfeld, ohne die Richtlinie bereitzustellen**: Klicken Sie auf **Abbrechen**.</span><span class="sxs-lookup"><span data-stu-id="e6589-153">**To close the dialog box without deploying it** - Choose **Cancel**.</span></span>

<span data-ttu-id="e6589-154">Wenn Sie eine bereitgestellte Richtlinie auswählen, können Sie weitere Informationen zur Bereitstellung im unteren Teil der Richtlinienliste anzeigen.</span><span class="sxs-lookup"><span data-stu-id="e6589-154">When you select a deployed policy, you can view more information about the deployment in the lower part of the policies list.</span></span>

### <a name="see-also"></a><span data-ttu-id="e6589-155">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="e6589-155">See also</span></span>
[<span data-ttu-id="e6589-156">WLAN-Verbindungen in Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="e6589-156">Wi-Fi connections in Microsoft Intune</span></span>](wi-fi-connections-in-microsoft-intune.md)
