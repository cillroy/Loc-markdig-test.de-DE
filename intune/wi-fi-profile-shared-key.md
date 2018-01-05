---
title: "Erstellen eines WLAN-Profils über einen vorinstallierten Schlüssel"
titleSuffix: Azure portal
description: "Verwenden Sie ein benutzerdefiniertes Profil von Intune, um ein WLAN-Profil mit einem vorinstallierten Schlüssel zu erstellen."
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 11/09/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c6fd72a6-7dc8-48fc-9df1-db5627a51597
ms.reviewer: karanda
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 8930c574f083b58ed5f1bdbabc3fe0daad545301
ms.sourcegitcommit: e37e916e2bf14f092d3a767bc90d68c181d739fb
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/03/2018
---
# <a name="use-a-custom-device-profile-to-create-a-wi-fi-profile-with-a-pre-shared-key"></a><span data-ttu-id="e96a0-103">Verwenden Sie ein benutzerdefiniertes Geräteprofil zum Erstellen eines WLAN-Profils mit einem vorinstallierten Schlüssel</span><span class="sxs-lookup"><span data-stu-id="e96a0-103">Use a custom device profile to create a Wi-Fi profile with a pre-shared key</span></span>
[!INCLUDE[azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="e96a0-104">Erfahren Sie, wie Sie mithilfe von **benutzerdefinierten Geräteprofilen** in Intune ein WLAN-Profil mit einem vorinstallierten Schlüssel erstellen.</span><span class="sxs-lookup"><span data-stu-id="e96a0-104">Here's how to use Intune’s **Custom device profiles** to create a Wi-Fi profile with a pre-shared key.</span></span> <span data-ttu-id="e96a0-105">Dieses Thema umfasst außerdem ein Beispiel für die Erstellung eines EAP-basierten WLAN-Profils.</span><span class="sxs-lookup"><span data-stu-id="e96a0-105">This topic also has an example of how to create an EAP-based Wi-Fi profile.</span></span>

> [!NOTE]
> -   <span data-ttu-id="e96a0-106">Möglicherweise ist es für Sie einfacher, den Code von einem Computer zu kopieren, der eine Verbindung mit dem jeweiligen Netzwerk herstellt, wie unten beschrieben.</span><span class="sxs-lookup"><span data-stu-id="e96a0-106">You might find it easier to copy the code from a computer that connects to that network, as described below.</span></span>
> - <span data-ttu-id="e96a0-107">Bei Android haben Sie auch die Möglichkeit, diesen von Johnathon Biersack bereitgestellten [Android PSK Generator](http://johnathonb.com/2015/05/intune-android-pre-shared-key-generator/) zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="e96a0-107">For Android, you also have the option of using this [Android PSK Generator](http://johnathonb.com/2015/05/intune-android-pre-shared-key-generator/) provided by Johnathon Biersack.</span></span>
> -   <span data-ttu-id="e96a0-108">Sie können mehrere Netzwerke und Schlüssel hinzufügen, indem Sie weitere OMA-URI-Einstellungen hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="e96a0-108">You can add multiple networks and keys by adding more OMA-URI settings.</span></span>
> -  <span data-ttu-id="e96a0-109">Verwenden Sie für iOS den Apple Configurator auf einer Mac-Station, um das Profil einzurichten.</span><span class="sxs-lookup"><span data-stu-id="e96a0-109">For iOS, use Apple Configurator on a Mac station to set up the profile.</span></span> <span data-ttu-id="e96a0-110">Verwenden Sie alternativ diesen [iOS PSK Mobile Config Generator](http://johnathonb.com/2015/05/intune-ios-psk-mobile-config-generator/), der von Johnathon Biersack bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="e96a0-110">Alternatively, use this [iOS PSK Mobile Config Generator](http://johnathonb.com/2015/05/intune-ios-psk-mobile-config-generator/) provided by Johnathon Biersack.</span></span>


1. <span data-ttu-id="e96a0-111">Um ein WLAN-Profil mit einem vorinstallierten Schlüssel für Android oder Windows oder ein EAP-basiertes WLAN-Profil zu erstellen, wählen Sie beim Erstellen eines Geräteprofils anstelle eines WLAN-Profils die Option **Benutzerdefiniert** für die jeweilige Geräteplattform aus.</span><span class="sxs-lookup"><span data-stu-id="e96a0-111">To create a Wi-Fi profile with a pre-shared key for Android or Windows or an EAP-based Wi-Fi profile, when you create a device profile choose **Custom** for that device platform rather than a Wi-Fi profile.</span></span>

2. <span data-ttu-id="e96a0-112">Geben Sie einen Namen und eine Beschreibung an.</span><span class="sxs-lookup"><span data-stu-id="e96a0-112">Provide a name and description.</span></span>
3. <span data-ttu-id="e96a0-113">Fügen Sie eine neue OMA-URI-Einstellung hinzu:</span><span class="sxs-lookup"><span data-stu-id="e96a0-113">Add a new OMA-URI setting:</span></span>

   <span data-ttu-id="e96a0-114">ein.</span><span class="sxs-lookup"><span data-stu-id="e96a0-114">a.</span></span>   <span data-ttu-id="e96a0-115">Geben Sie einen Namen für diese WLAN-Netzwerkeinstellung ein.</span><span class="sxs-lookup"><span data-stu-id="e96a0-115">Enter a name for this Wi-Fi network setting.</span></span>

   <span data-ttu-id="e96a0-116">b.</span><span class="sxs-lookup"><span data-stu-id="e96a0-116">b.</span></span>   <span data-ttu-id="e96a0-117">Geben Sie eine Beschreibung für die OMA-URI-Einstellung ein, oder lassen Sie sie leer.</span><span class="sxs-lookup"><span data-stu-id="e96a0-117">Enter a description of the OMA-URI setting or leave blank.</span></span>

   <span data-ttu-id="e96a0-118">c.</span><span class="sxs-lookup"><span data-stu-id="e96a0-118">c.</span></span>   <span data-ttu-id="e96a0-119">**Datentyp:** Legen Sie **String** fest.</span><span class="sxs-lookup"><span data-stu-id="e96a0-119">**Data Type**: Set to **String**.</span></span>

   <span data-ttu-id="e96a0-120">d.</span><span class="sxs-lookup"><span data-stu-id="e96a0-120">d.</span></span>   <span data-ttu-id="e96a0-121">**OMA-URI**:</span><span class="sxs-lookup"><span data-stu-id="e96a0-121">**OMA-URI**:</span></span>

   - <span data-ttu-id="e96a0-122">**Für Android**: ./Vendor/MSFT/WiFi/Profile/<SSID>/Settings</span><span class="sxs-lookup"><span data-stu-id="e96a0-122">**For Android**: ./Vendor/MSFT/WiFi/Profile/<SSID>/Settings</span></span>
   - <span data-ttu-id="e96a0-123">**Für Windows**: ./Vendor/MSFT/WiFi/Profile/MyNetwork/WlanXml</span><span class="sxs-lookup"><span data-stu-id="e96a0-123">**For Windows**: ./Vendor/MSFT/WiFi/Profile/MyNetwork/WlanXml</span></span>

   > [!NOTE]
   > <span data-ttu-id="e96a0-124">Stellen Sie sicher, dass Sie den Punkt am Anfang eingeben.</span><span class="sxs-lookup"><span data-stu-id="e96a0-124">Be sure to include the dot character at the beginning.</span></span>

   <span data-ttu-id="e96a0-125">SSID steht für die SSID, für die Sie die Richtlinie erstellen.</span><span class="sxs-lookup"><span data-stu-id="e96a0-125">SSID is the SSID for which you’re creating the policy.</span></span> <span data-ttu-id="e96a0-126">Beispiel: `./Vendor/MSFT/WiFi/Profile/Hotspot-1/Settings`</span><span class="sxs-lookup"><span data-stu-id="e96a0-126">For example, `./Vendor/MSFT/WiFi/Profile/Hotspot-1/Settings`</span></span>

   <span data-ttu-id="e96a0-127">e.</span><span class="sxs-lookup"><span data-stu-id="e96a0-127">e.</span></span> <span data-ttu-id="e96a0-128">**Wertfeld** Hier fügen Sie Ihren XML-Code ein.</span><span class="sxs-lookup"><span data-stu-id="e96a0-128">**Value Field** is where you paste your XML code.</span></span> <span data-ttu-id="e96a0-129">Hier sehen Sie ein Beispiel.</span><span class="sxs-lookup"><span data-stu-id="e96a0-129">Here’s an example.</span></span> <span data-ttu-id="e96a0-130">Die einzelnen Werte sollten an Ihre Netzwerkeinstellungen angepasst werden.</span><span class="sxs-lookup"><span data-stu-id="e96a0-130">Each value should be adapted to your network settings.</span></span> <span data-ttu-id="e96a0-131">Einige Hinweise finden Sie im Kommentarabschnitt des Codes.</span><span class="sxs-lookup"><span data-stu-id="e96a0-131">See the comments section of the code for some pointers.</span></span>
4. <span data-ttu-id="e96a0-132">Wählen Sie **OK** aus, speichern Sie, und weisen Sie anschließend die Richtlinie zu.</span><span class="sxs-lookup"><span data-stu-id="e96a0-132">Choose **OK**, save, and then assign the policy.</span></span>

    > [!NOTE]
    > <span data-ttu-id="e96a0-133">Diese Richtlinie kann nur Benutzergruppen zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="e96a0-133">This policy can only be assigned to user groups.</span></span>

<span data-ttu-id="e96a0-134">Wenn sich die einzelnen Geräte das nächste Mal anmelden, wird die Richtlinie angewendet, und auf dem Gerät wird ein WLAN-Profil erstellt.</span><span class="sxs-lookup"><span data-stu-id="e96a0-134">The next time each device checks in, the policy will be applied, and a Wi-Fi profile will be created on the device.</span></span> <span data-ttu-id="e96a0-135">Das Gerät kann automatisch eine Verbindung mit dem Netzwerk herstellen.</span><span class="sxs-lookup"><span data-stu-id="e96a0-135">The device will be able to connect to the network automatically.</span></span>

## <a name="android-or-windows-wi-fi-profile"></a><span data-ttu-id="e96a0-136">Android- oder Windows-WLAN-Profil</span><span class="sxs-lookup"><span data-stu-id="e96a0-136">Android or Windows Wi-Fi profile</span></span>

<span data-ttu-id="e96a0-137">Hier sehen Sie ein Beispiel für den XML-Code eines Android- oder Windows-WLAN-Profils:</span><span class="sxs-lookup"><span data-stu-id="e96a0-137">Here’s an example of the XML code for an Android or Windows Wi-Fi profile:</span></span>

> [!IMPORTANT]
>
> <span data-ttu-id="e96a0-138">`<protected>false</protected>` muss auf **false** festgelegt werden, da **true** dazu führen könnte, dass das Gerät ein verschlüsseltes Kennwort erwartet, das es dann zu entschlüsseln versucht, was einen Verbindungsfehler bewirken würde.</span><span class="sxs-lookup"><span data-stu-id="e96a0-138">`<protected>false</protected>`must be set to **false**, as **true** could cause device to expect an encrypted password and then try to decrypt it, which may result in a failed connection.</span></span>
>
>  <span data-ttu-id="e96a0-139">`<hex>53534944</hex>` sollte auf den hexadezimalen Wert von `<name><SSID of wifi profile></name>` festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="e96a0-139">`<hex>53534944</hex>` should be set to the hexadecimal value of `<name><SSID of wifi profile></name>`.</span></span>
>  <span data-ttu-id="e96a0-140">Windows 10-Geräte können fälschlicherweise den Fehler *0x87D1FDE8: Fehler bei Wiederherstellung* zurückgeben, werden aber dennoch mit dem Profil bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="e96a0-140">Windows 10 devices may return a false *0x87D1FDE8 Remediation failed* error, but will still be provisioned with the profile.</span></span>

```
<!--
<Name of wifi profile> = Name of profile
<SSID of wifi profile> = Plain text of SSID. Does not need to be escaped, could be <name>Your Company's Network</name>
<nonBroadcast><true/false></nonBroadcast>
<Type of authentication> = Type of authentication used by the network, such as WPA2PSK.
<Type of encryption> = Type of encryption used by the network
<protected>false</protected> do not change this value, as true could cause device to expect an encrypted password and then try to decrypt it, which may result in a failed connection.
<password> = Password to connect to the network
x>53534944</hex> should be set to the hexadecimal value of <name><SSID of wifi profile></name>
-->
<WLANProfile
xmlns="http://www.microsoft.com/networking/WLAN/profile/v1">
  <name><Name of wifi profile></name>
  <SSIDConfig>
    <SSID>
      <hex>53534944</hex>
 <name><SSID of wifi profile></name>
    </SSID>
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

## <a name="eap-based-wi-fi-profile"></a><span data-ttu-id="e96a0-141">EAP-basiertes WLAN-Profil</span><span class="sxs-lookup"><span data-stu-id="e96a0-141">EAP-based Wi-Fi profile</span></span>
<span data-ttu-id="e96a0-142">Hier sehen Sie ein Beispiel für den XML-Code eines EAP-basierten WLAN-Profils:</span><span class="sxs-lookup"><span data-stu-id="e96a0-142">Here’s  an example of the XML code for an EAP-based Wi-Fi profile:</span></span>

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

## <a name="create-the-xml-file-from-an-existing-wi-fi-connection"></a><span data-ttu-id="e96a0-143">Erstellen der XML-Datei aus einer vorhandenen WLAN-Verbindung</span><span class="sxs-lookup"><span data-stu-id="e96a0-143">Create the XML file from an existing Wi-Fi connection</span></span>
<span data-ttu-id="e96a0-144">Sie können die XML-Datei auch aus einer vorhandenen WLAN-Verbindung erstellen:</span><span class="sxs-lookup"><span data-stu-id="e96a0-144">You can also create an XML file from an existing Wi-Fi connection:</span></span>
1. <span data-ttu-id="e96a0-145">Öffnen Sie auf einem Computer, der mit dem WLAN verbunden ist oder vor kurzem damit verbunden war, den folgenden Ordner: „C:\ProgramData\Microsoft\Wlansvc\Profiles\Interfaces\{guid}“.</span><span class="sxs-lookup"><span data-stu-id="e96a0-145">On a computer that is connected to or has recently connected to the wireless network, open the following folder: C:\ProgramData\Microsoft\Wlansvc\Profiles\Interfaces\{guid}.</span></span>

    <span data-ttu-id="e96a0-146">Es wird empfohlen, einen Computer zu verwenden, der nicht mit allzu vielen WLANs verbunden ist, weil Sie die einzelnen Profile durchsuchen müssen, um das richtige zu finden.</span><span class="sxs-lookup"><span data-stu-id="e96a0-146">It’s best to use a computer that has not connected to many wireless networks, because you’ll have to search through each profile to find the right one.</span></span>
2. <span data-ttu-id="e96a0-147">Durchsuchen Sie die XML-Dateien, um die Datei mit dem richtigen Namen zu finden.</span><span class="sxs-lookup"><span data-stu-id="e96a0-147">Search through the XML files to locate the one with the right name.</span></span>
3. <span data-ttu-id="e96a0-148">Nachdem Sie die richtige XML-Datei gefunden haben, kopieren Sie den XML-Code in das Feld „Daten“ auf der Seite mit den OMA-URI-Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="e96a0-148">After you have located the correct XML file, copy and paste the XML code into the Data field of the OMA-URI settings page.</span></span>

## <a name="best-practices"></a><span data-ttu-id="e96a0-149">Bewährte Methoden</span><span class="sxs-lookup"><span data-stu-id="e96a0-149">Best practices</span></span>
<span data-ttu-id="e96a0-150">Bevor Sie ein WLAN-Profil mit PSK bereitstellen, überprüfen Sie, ob das Gerät eine direkte Verbindung mit dem Endpunkt herstellen kann.</span><span class="sxs-lookup"><span data-stu-id="e96a0-150">Before you deploy a Wi-Fi profile with PSK, verify that the device can connect to the endpoint directly.</span></span>

<span data-ttu-id="e96a0-151">Rechnen Sie beim Rotieren von Schlüsseln (Kennwörtern oder Passphrases) mit Ausfallzeiten, und planen Sie die Bereitstellung entsprechend.</span><span class="sxs-lookup"><span data-stu-id="e96a0-151">When rotating keys (passwords or passphrases), expect downtime and plan deployments accordingly.</span></span> <span data-ttu-id="e96a0-152">Erwägen Sie die Push-Übertragung von neuen WLAN-Profilen in der arbeitsfreien Zeit.</span><span class="sxs-lookup"><span data-stu-id="e96a0-152">Consider pushing new Wi-Fi profiles during non-working hours.</span></span> <span data-ttu-id="e96a0-153">Außerdem sollten Sie die Benutzer warnen, dass die Konnektivität beeinträchtigt sein kann.</span><span class="sxs-lookup"><span data-stu-id="e96a0-153">Also, warn users that connectivity may be impacted.</span></span>
 
<span data-ttu-id="e96a0-154">Um eine reibungslose Umstellung und die zeitnahe Übermittlung von Richtlinienaktualisierungen zu gewährleisten, müssen die Geräte wenigstens einen offenen Kommunikationskanal zu Intune behalten.</span><span class="sxs-lookup"><span data-stu-id="e96a0-154">To ensure a smooth transition experience and deliver timely policy updates, devices must keep at least one open communication channel to Intune.</span></span> <span data-ttu-id="e96a0-155">Verwenden Sie zu diesem Zweck Mobilfunkverbindungen, um WLAN-Gastzugriff bereitzustellen, mit dem Benutzer ausschließlich mit Intune-Endpunkten verbunden werden.</span><span class="sxs-lookup"><span data-stu-id="e96a0-155">To do this, use cellular connectivity or provide guest Wi-Fi access that connects users only to Intune endpoints.</span></span>


