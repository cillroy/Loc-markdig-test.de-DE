---
title: "VPN-Einstellungen für Windows Phone 8.1-Geräte in Intune"
titleSuffix: Azure portal
description: "Erfahren Sie etwas über die Intune-Einstellungen, die Sie zum Konfigurieren von VPN-Verbindungen auf Windows Phone 8.1-Geräten verwenden können.\""
keywords: 
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c1a9053f-02a7-4735-bc0d-fe4573b31ed4
ms.reviewer: karanda
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 2ac89492be4ab1dc0a2a45338883105bcf23ce6e
ms.sourcegitcommit: e37e916e2bf14f092d3a767bc90d68c181d739fb
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/03/2018
---
# <a name="vpn-settings-for-windows-phone-81-devices-in-microsoft-intune"></a><span data-ttu-id="83afd-103">VPN-Einstellungen für Windows Phone 8.1-Geräte in Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="83afd-103">VPN settings for Windows Phone 8.1 devices in Microsoft Intune</span></span>

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="83afd-104">Je nach den ausgewählten Einstellungen können nicht alle Werte in der folgenden Liste konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="83afd-104">Depending on the settings you choose, not all values in the list below will be configurable.</span></span>

## <a name="base-vpn-settings"></a><span data-ttu-id="83afd-105">Grundlegende VPN-Einstellungen</span><span class="sxs-lookup"><span data-stu-id="83afd-105">Base VPN settings</span></span>

- <span data-ttu-id="83afd-106">**Alle Einstellungen nur auf Windows Phone 8.1 anwenden:** Diese Einstellung können Sie im klassischen Intune-Portal konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="83afd-106">**Apply all settings to Windows Phone 8.1 only** - This is a setting you can configure in the Intune classic portal.</span></span> <span data-ttu-id="83afd-107">Im Azure-Portal kann diese Einstellung nicht geändert werden.</span><span class="sxs-lookup"><span data-stu-id="83afd-107">In the Azure portal, this setting cannot be changed.</span></span> <span data-ttu-id="83afd-108">Wenn hierfür **Konfiguriert** festgelegt wird, werden sämtliche Einstellungen nur auf Windows Phone 8.1-Geräte angewendet.</span><span class="sxs-lookup"><span data-stu-id="83afd-108">If this is set to **Configured**, any settings will only be applied to Windows Phone 8.1 devices.</span></span> <span data-ttu-id="83afd-109">Wenn hierfür **Nicht konfiguriert** festgelegt wird, gelten diese Einstellungen auch für Windows 10 Mobile-Geräte.</span><span class="sxs-lookup"><span data-stu-id="83afd-109">If set to **Not Configured**, these settings will also apply to Windows 10 Mobile devices.</span></span>
- <span data-ttu-id="83afd-110">**Verbindungsname:** Geben Sie einen Namen für diese Verbindung ein.</span><span class="sxs-lookup"><span data-stu-id="83afd-110">**Connection name** - Enter a name for this connection.</span></span> <span data-ttu-id="83afd-111">Endbenutzern wird dieser Name angezeigt, wenn sie auf ihrem Gerät die Liste der verfügbaren VPN-Verbindungen durchsuchen.</span><span class="sxs-lookup"><span data-stu-id="83afd-111">End users will see this name when they browse their device for the list of available VPN connections.</span></span>
- <span data-ttu-id="83afd-112">**Authentifizierungsmethode:** Wählen Sie unter folgenden Optionen aus, wie sich Geräte beim VPN-Server authentifizieren:</span><span class="sxs-lookup"><span data-stu-id="83afd-112">**Authentication method** - Choose how devices will authenticate to the VPN server from:</span></span>
    - <span data-ttu-id="83afd-113">**Zertifikate:** Wählen Sie unter **Authentifizierungszertifikat** ein zuvor erstelltes SCEP- oder PKCS-Zertifikatprofil zum Authentifizieren der Verbindung aus.</span><span class="sxs-lookup"><span data-stu-id="83afd-113">**Certificates** - Under **Authentication certificate**, Choose a SCEP or PKCS certificate profile you previously created to authenticate the connection.</span></span> <span data-ttu-id="83afd-114">Ausführliche Informationen zu Zertifikatprofilen finden Sie unter [Konfigurieren von Zertifikaten](certificates-configure.md).</span><span class="sxs-lookup"><span data-stu-id="83afd-114">For more details about certificate profiles, see [How to configure certificates](certificates-configure.md).</span></span>
    - <span data-ttu-id="83afd-115">**Benutzername und Kennwort:** Endbenutzer müssen einen Benutzernamen und ein Kennwort für die Anmeldung beim VPN-Server angeben.</span><span class="sxs-lookup"><span data-stu-id="83afd-115">**Username and password** - End users must supply a username and password to log into the VPN server.</span></span>
- <span data-ttu-id="83afd-116">**Server:** Fügen Sie einen oder mehrere VPN-Server hinzu, mit denen Geräte eine Verbindung herstellen.</span><span class="sxs-lookup"><span data-stu-id="83afd-116">**Servers** - Add one or more VPN servers that devices will connect to.</span></span>
    - <span data-ttu-id="83afd-117">**Hinzufügen:** öffnet das Blatt **Zeile hinzufügen**, auf dem Sie die folgende Informationen angeben können:</span><span class="sxs-lookup"><span data-stu-id="83afd-117">**Add** - Opens the **Add Row** blade where you can specify the following information:</span></span>
        - <span data-ttu-id="83afd-118">**Beschreibung:** Geben Sie einen beschreibenden Namen für den Server ein, z.B. **Contoso-VPN-Server**.</span><span class="sxs-lookup"><span data-stu-id="83afd-118">**Description** - Specify a descriptive name for the server like **Contoso VPN server**.</span></span>
        - <span data-ttu-id="83afd-119">**IP-Adresse oder FQDN:** Geben Sie die IP-Adresse oder den vollqualifizierten Domänennamen des VPN-Servers an, mit dem Geräte eine Verbindung herstellen.</span><span class="sxs-lookup"><span data-stu-id="83afd-119">**IP address or FQDN** - Provide the IP address or fully qualified domain name of the VPN server that devices will connect to.</span></span> <span data-ttu-id="83afd-120">Beispiele: **192.168.1.1**, **vpn.contoso.com**.</span><span class="sxs-lookup"><span data-stu-id="83afd-120">Examples: **192.168.1.1**, **vpn.contoso.com**.</span></span>
        - <span data-ttu-id="83afd-121">**Standardserver:** aktiviert diesen Server als Standardserver, über den Geräte die Verbindung herstellen.</span><span class="sxs-lookup"><span data-stu-id="83afd-121">**Default server** - Enables this server as the default server that devices will use to establish the connection.</span></span> <span data-ttu-id="83afd-122">Achten Sie darauf, nur einen Server als Standard festzulegen.</span><span class="sxs-lookup"><span data-stu-id="83afd-122">Make sure to set only one server as the default.</span></span>
    - <span data-ttu-id="83afd-123">**Importieren:** Suchen Sie nach einer Datei, die eine durch Trennzeichen getrennte Liste von Servern im Format „Beschreibung, IP-Adresse oder FQDN, Standardserver“ enthält.</span><span class="sxs-lookup"><span data-stu-id="83afd-123">**Import** - Browse to a file containing a comma-separated list of servers in the format description, IP address or FQDN, Default server.</span></span> <span data-ttu-id="83afd-124">Wählen Sie **OK** aus, um diese in die Liste **Server** zu importieren.</span><span class="sxs-lookup"><span data-stu-id="83afd-124">Choose **OK** to import these into the **Servers** list.</span></span>
    - <span data-ttu-id="83afd-125">**Exportieren:** exportiert die Liste der Server in eine CSV-Datei (Comma-Separated Values, durch Trennzeichen getrennte Werte).</span><span class="sxs-lookup"><span data-stu-id="83afd-125">**Export** - Exports the list of servers to a comma-separated-values (csv) file.</span></span>

- <span data-ttu-id="83afd-126">**VPN bei Verbindung mit Unternehmens-WLAN umgehen:** Aktivieren Sie diese Option, um anzugeben, dass die VPN-Verbindung nicht verwendet wird, wenn das Gerät mit dem Unternehmens-WLAN verbunden ist.</span><span class="sxs-lookup"><span data-stu-id="83afd-126">**Bypass VPN on company Wi-Fi network** - Enable this option to specify that the VPN connection will not be used when the device is connected to the company Wi-Fi network.</span></span>
- <span data-ttu-id="83afd-127">**VPN bei Verbindung mit Heim-WLAN umgehen:** Aktivieren Sie diese Option, um anzugeben, dass die VPN-Verbindung nicht verwendet wird, wenn das Gerät mit einem Heim-WLAN verbunden ist.</span><span class="sxs-lookup"><span data-stu-id="83afd-127">**Bypass VPN on home Wi-Fi network** - Enable this option to specify that the VPN connection will not be used when the device is connected to a home Wi-Fi network.</span></span>

- <span data-ttu-id="83afd-128">**Verbindungstyp:** Wählen Sie den VPN-Verbindungstyp in der folgenden Liste von Anbietern aus:</span><span class="sxs-lookup"><span data-stu-id="83afd-128">**Connection type** - Select the VPN connection type from the following list of vendors:</span></span>
    - <span data-ttu-id="83afd-129">**Check Point Capsule VPN**</span><span class="sxs-lookup"><span data-stu-id="83afd-129">**Check Point Capsule VPN**</span></span>
    - <span data-ttu-id="83afd-130">**Dell SonicWALL Mobile Connect**</span><span class="sxs-lookup"><span data-stu-id="83afd-130">**Dell SonicWALL Mobile Connect**</span></span>
    - <span data-ttu-id="83afd-131">**F5 Edge Client**</span><span class="sxs-lookup"><span data-stu-id="83afd-131">**F5 Edge Client**</span></span>
    - <span data-ttu-id="83afd-132">**Pulse Secure**</span><span class="sxs-lookup"><span data-stu-id="83afd-132">**Pulse Secure**</span></span>

- <span data-ttu-id="83afd-133">**Anmeldegruppe oder -domäne** (nur Dell SonicWALL Mobile Connect): Geben Sie den Namen der Anmeldegruppe oder -domäne an, mit der Sie eine Verbindung herstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="83afd-133">**Login group or domain** (Dell SonicWALL Mobile Connect only) - Specify the name of the login group or domain that you want to connect to.</span></span>
- <span data-ttu-id="83afd-134">**Rolle** (nur Pulse Secure): Geben Sie den Namen der Benutzerrolle an, die Zugriff auf diese Verbindung hat.</span><span class="sxs-lookup"><span data-stu-id="83afd-134">**Role** (Pulse Secure only) - Specify the name of the user role that has access to this connection.</span></span> <span data-ttu-id="83afd-135">Eine Benutzerrolle definiert persönliche Einstellungen und Optionen und aktiviert oder deaktiviert bestimmte Zugriffsfeatures.</span><span class="sxs-lookup"><span data-stu-id="83afd-135">A user role defines personal settings and options, and it enables or disables certain access features.</span></span>
- <span data-ttu-id="83afd-136">**Bereich** (nur Pulse Secure): Geben Sie den Namen des gewünschten Authentifizierungsbereichs an.</span><span class="sxs-lookup"><span data-stu-id="83afd-136">**Realm** (Pulse Secure only) - Specify the name of the authentication realm that you want to use.</span></span> <span data-ttu-id="83afd-137">Ein Authentifizierungsbereich ist eine Gruppe von Authentifizierungsressourcen, die vom Verbindungstyp „Pulse Secure“ verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="83afd-137">An authentication realm is a grouping of authentication resources that the Pulse Secure connection type uses.</span></span>

- <span data-ttu-id="83afd-138">**DNS-Suffixsuchliste** - **Fügen** Sie DNS-Suffixe hinzu.</span><span class="sxs-lookup"><span data-stu-id="83afd-138">**DNS suffix search list** - **Add** one or more DNS suffices.</span></span> <span data-ttu-id="83afd-139">Jedes angegebene DNS-Suffix wird beim Verbinden mit einer Website unter Verwendung eines Kurznamens gesucht.</span><span class="sxs-lookup"><span data-stu-id="83afd-139">Each DNS suffix that you specify will be searched when connecting to a website by using a short name.</span></span> <span data-ttu-id="83afd-140">Geben Sie z.B. die DNS-Suffixe **domain1.contoso.com** und **domain2.contoso.com** ein, rufen Sie die URL **http://mywebsite** auf, und die URLs **http://mywebsite.domain1.contoso.com** und **http://mywebsite.domain2.contoso.com** werden durchsucht.</span><span class="sxs-lookup"><span data-stu-id="83afd-140">For example, specify the DNS suffixes **domain1.contoso.com** and **domain2.contoso.com**, visit the URL **http://mywebsite**, and the URLs **http://mywebsite.domain1.contoso.com** and **http://mywebsite.domain2.contoso.com will be searched**.</span></span>

- <span data-ttu-id="83afd-141">**Benutzerdefiniertes XML:** Geben Sie benutzerdefinierte XML-Befehle zum Konfigurieren der VPN-Verbindung an.</span><span class="sxs-lookup"><span data-stu-id="83afd-141">**Custom XML** - Specify any custom XML commands that configure the VPN connection.</span></span>

    <span data-ttu-id="83afd-142">**Beispiel für Pulse Secure:**</span><span class="sxs-lookup"><span data-stu-id="83afd-142">**Example for Pulse Secure:**</span></span>

```
    <pulse-schema><isSingleSignOnCredential>true</isSingleSignOnCredential></pulse-schema>
```

<span data-ttu-id="83afd-143">**Beispiel für CheckPoint Mobile VPN:**</span><span class="sxs-lookup"><span data-stu-id="83afd-143">**Example for CheckPoint Mobile VPN:**</span></span>

```
    <CheckPointVPN port="443" name="CheckPointSelfhost" sso="true" debug="3" />
```

<span data-ttu-id="83afd-144">**Beispiel für Dell SonicWALL Mobile Connect:**</span><span class="sxs-lookup"><span data-stu-id="83afd-144">**Example for Dell SonicWALL Mobile Connect:**</span></span>
```
<MobileConnect><Compression>false</Compression><debugLogging>True</debugLogging><packetCapture>False</packetCapture></MobileConnect>
```

<span data-ttu-id="83afd-145">**Beispiel für F5 Edge Client:**</span><span class="sxs-lookup"><span data-stu-id="83afd-145">**Example for F5 Edge Client:**</span></span>
```
    <f5-vpn-conf><single-sign-on-credential /></f5-vpn-conf>
```

<span data-ttu-id="83afd-146">Weitere Informationen zum Erstellen von benutzerdefinierten XML-Befehlen finden Sie in der VPN-Dokumentation des jeweiligen Herstellers.</span><span class="sxs-lookup"><span data-stu-id="83afd-146">Refer to each manufacturer's VPN documentation for more information about how to write custom XML commands.</span></span>

- <span data-ttu-id="83afd-147">**Tunneling teilen** - **Aktivieren** oder **deaktivieren** Sie diese Option, mit der Geräte anhand des Datenverkehrs selbst entscheiden können, welche Verbindung verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="83afd-147">**Split tunneling** - **Enable** or **Disable** this option which lets devices decide which connection to use depending on the traffic.</span></span> <span data-ttu-id="83afd-148">Beispiel: Ein Benutzer in einem Hotel verwendet die VPN-Verbindung zum Zugreifen auf Arbeitsdateien, jedoch das Standardnetzwerk des Hotels für normales Webbrowsen.</span><span class="sxs-lookup"><span data-stu-id="83afd-148">For example, a user in a hotel will use the VPN connection to access work files, but use the hotel's standard network for regular web browsing.</span></span>




## <a name="proxy-settings"></a><span data-ttu-id="83afd-149">Proxyeinstellungen</span><span class="sxs-lookup"><span data-stu-id="83afd-149">Proxy settings</span></span>

- <span data-ttu-id="83afd-150">**Proxyeinstellungen automatisch erkennen:** Wenn der VPN-Server einen Proxyserver für die Verbindung erfordert, geben Sie an, ob Geräte die Verbindungseinstellungen automatisch erkennen können sollen.</span><span class="sxs-lookup"><span data-stu-id="83afd-150">**Automatically detect proxy settings** - If your VPN server requires a proxy server for the connection, specify whether you want devices to automatically detect the connection settings.</span></span> <span data-ttu-id="83afd-151">Weitere Informationen finden Sie in der Windows Server-Dokumentation.</span><span class="sxs-lookup"><span data-stu-id="83afd-151">For more information, see your Windows Server documentation.</span></span>
- <span data-ttu-id="83afd-152">**Automatisches Konfigurationsskript:** Verwenden Sie eine Datei zum Konfigurieren des Proxyservers.</span><span class="sxs-lookup"><span data-stu-id="83afd-152">**Automatic configuration script** - Use a file to configure the proxy server.</span></span> <span data-ttu-id="83afd-153">Geben Sie die **Proxyserver-URL** ein (z.B. **http://proxy.contoso.com**), unter der die Konfigurationsdatei zu finden ist.</span><span class="sxs-lookup"><span data-stu-id="83afd-153">Enter the **Proxy server URL** (for example **http://proxy.contoso.com**) which contains the configuration file.</span></span>
- <span data-ttu-id="83afd-154">**Proxyserver verwenden:** Aktivieren Sie diese Option, wenn Sie die Proxyeinstellungen für den Server manuell eingeben möchten.</span><span class="sxs-lookup"><span data-stu-id="83afd-154">**Use proxy server** - Enable this option if you want to manually enter the proxy server settings.</span></span>
    - <span data-ttu-id="83afd-155">**Adresse:** Geben Sie die Adresse des Proxyservers (als IP-Adresse) ein.</span><span class="sxs-lookup"><span data-stu-id="83afd-155">**Address** - Enter the proxy server address (as an IP address).</span></span>
    - <span data-ttu-id="83afd-156">**Portnummer:** Geben Sie die Portnummer ein, die dem Proxyserver zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="83afd-156">**Port number** - Enter the port number associated with the proxy server.</span></span>
- <span data-ttu-id="83afd-157">**Proxy für lokale Adressen umgehen:** Wenn der VPN-Server einen Proxyserver für die Verbindung erfordert, aktivieren Sie diese Option, wenn der Proxyserver für von Ihnen angegebene lokale Adressen nicht verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="83afd-157">**Bypass proxy for local addresses** - If your VPN server requires a proxy server for the connection, select this option if you do not want to use the proxy server for local addresses that you specify.</span></span> <span data-ttu-id="83afd-158">Weitere Informationen finden Sie in der Windows Server-Dokumentation.</span><span class="sxs-lookup"><span data-stu-id="83afd-158">For more information, see your Windows Server documentation.</span></span>
