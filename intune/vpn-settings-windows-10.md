---
title: "VPN-Einstellungen für Windows 10-Geräte in Intune"
titlesuffix: Azure portal
description: "Erfahren Sie etwas über die Intune-Einstellungen, die Sie zum Konfigurieren von VPN-Verbindungen auf Windows 10-Geräten verwenden können.\""
keywords: 
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 10/20/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 495e4ed6-b2ef-47cc-a110-13fa9b5f85a6
ms.reviewer: karanda
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 78df2fffe14c375d874731564b1f481db1837b23
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2018
---
# <a name="vpn-settings-for-windows-10-devices-in-microsoft-intune"></a><span data-ttu-id="161d8-103">VPN-Einstellungen für Windows 10-Geräte in Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="161d8-103">VPN settings for Windows 10 devices in Microsoft Intune</span></span>

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="161d8-104">Je nach den ausgewählten Einstellungen können nicht alle Werte in der folgenden Liste konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="161d8-104">Depending on the settings you choose, not all values in the list below will be configurable.</span></span>


## <a name="base-vpn-settings"></a><span data-ttu-id="161d8-105">Grundlegende VPN-Einstellungen</span><span class="sxs-lookup"><span data-stu-id="161d8-105">Base VPN settings</span></span>


- <span data-ttu-id="161d8-106">**Verbindungsname:** Geben Sie einen Namen für diese Verbindung ein.</span><span class="sxs-lookup"><span data-stu-id="161d8-106">**Connection name** - Enter a name for this connection.</span></span> <span data-ttu-id="161d8-107">Endbenutzern wird dieser Name angezeigt, wenn sie auf ihrem Gerät die Liste der verfügbaren VPN-Verbindungen durchsuchen.</span><span class="sxs-lookup"><span data-stu-id="161d8-107">End users will see this name when they browse their device for the list of available VPN connections.</span></span>
- <span data-ttu-id="161d8-108">**Server:** Fügen Sie einen oder mehrere VPN-Server hinzu, mit denen Geräte eine Verbindung herstellen.</span><span class="sxs-lookup"><span data-stu-id="161d8-108">**Servers** - Add one or more VPN servers that devices will connect to.</span></span>
    - <span data-ttu-id="161d8-109">**Hinzufügen:** öffnet das Blatt **Zeile hinzufügen**, auf dem Sie die folgende Informationen angeben können:</span><span class="sxs-lookup"><span data-stu-id="161d8-109">**Add** - Opens the **Add Row** blade where you can specify the following information:</span></span>
        - <span data-ttu-id="161d8-110">**Beschreibung:** Geben Sie einen beschreibenden Namen für den Server ein, z.B. **Contoso-VPN-Server**.</span><span class="sxs-lookup"><span data-stu-id="161d8-110">**Description** - Specify a descriptive name for the server like **Contoso VPN server**.</span></span>
        - <span data-ttu-id="161d8-111">**IP-Adresse oder FQDN:** Geben Sie die IP-Adresse oder den vollqualifizierten Domänennamen des VPN-Servers an, mit dem Geräte eine Verbindung herstellen.</span><span class="sxs-lookup"><span data-stu-id="161d8-111">**IP address or FQDN** - Provide the IP address or fully qualified domain name of the VPN server that devices will connect to.</span></span> <span data-ttu-id="161d8-112">Beispiele: **192.168.1.1**, **vpn.contoso.com**.</span><span class="sxs-lookup"><span data-stu-id="161d8-112">Examples: **192.168.1.1**, **vpn.contoso.com**.</span></span>
        - <span data-ttu-id="161d8-113">**Standardserver:** aktiviert diesen Server als Standardserver, über den Geräte die Verbindung herstellen.</span><span class="sxs-lookup"><span data-stu-id="161d8-113">**Default server** - Enables this server as the default server that devices will use to establish the connection.</span></span> <span data-ttu-id="161d8-114">Achten Sie darauf, nur einen Server als Standard festzulegen.</span><span class="sxs-lookup"><span data-stu-id="161d8-114">Make sure to set only one server as the default.</span></span>
    - <span data-ttu-id="161d8-115">**Importieren:** Suchen Sie nach einer Datei, die eine durch Trennzeichen getrennte Liste von Servern im Format „Beschreibung, IP-Adresse oder FQDN, Standardserver“ enthält.</span><span class="sxs-lookup"><span data-stu-id="161d8-115">**Import** - Browse to a file containing a comma-separated list of servers in the format description, IP address or FQDN, Default server.</span></span> <span data-ttu-id="161d8-116">Wählen Sie **OK** aus, um diese in die Liste **Server** zu importieren.</span><span class="sxs-lookup"><span data-stu-id="161d8-116">Choose **OK** to import these into the **Servers** list.</span></span>
    - <span data-ttu-id="161d8-117">**Exportieren:** exportiert die Liste der Server in eine CSV-Datei (Comma-Separated Values, durch Trennzeichen getrennte Werte).</span><span class="sxs-lookup"><span data-stu-id="161d8-117">**Export** - Exports the list of servers to a comma-separated-values (csv) file.</span></span>

<span data-ttu-id="161d8-118">**Verbindungstyp:** Wählen Sie den VPN-Verbindungstyp in der folgenden Liste von Anbietern aus:</span><span class="sxs-lookup"><span data-stu-id="161d8-118">**Connection type** - Select the VPN connection type from the following list of vendors:</span></span>
- <span data-ttu-id="161d8-119">**Automatisch**</span><span class="sxs-lookup"><span data-stu-id="161d8-119">**Automatic**</span></span>
- <span data-ttu-id="161d8-120">**Check Point Capsule VPN**</span><span class="sxs-lookup"><span data-stu-id="161d8-120">**Check Point Capsule VPN**</span></span>
- <span data-ttu-id="161d8-121">**Citrix-VPN**</span><span class="sxs-lookup"><span data-stu-id="161d8-121">**Citrix VPN**</span></span>
- <span data-ttu-id="161d8-122">**Dell SonicWALL Mobile Connect**</span><span class="sxs-lookup"><span data-stu-id="161d8-122">**Dell SonicWALL Mobile Connect**</span></span>
- <span data-ttu-id="161d8-123">**F5 Edge Client**</span><span class="sxs-lookup"><span data-stu-id="161d8-123">**F5 Edge Client**</span></span>
- <span data-ttu-id="161d8-124">**IKEv2**</span><span class="sxs-lookup"><span data-stu-id="161d8-124">**IKEv2**</span></span>
- <span data-ttu-id="161d8-125">**L2TP**</span><span class="sxs-lookup"><span data-stu-id="161d8-125">**L2TP**</span></span>
- <span data-ttu-id="161d8-126">**PPTP**</span><span class="sxs-lookup"><span data-stu-id="161d8-126">**PPTP**</span></span>
- <span data-ttu-id="161d8-127">**Pulse Secure**</span><span class="sxs-lookup"><span data-stu-id="161d8-127">**Pulse Secure**</span></span>


<span data-ttu-id="161d8-128">**Anmeldegruppe oder -domäne** (nur Dell SonicWALL Mobile Connect): Geben Sie den Namen der Anmeldegruppe oder -domäne an, mit der Sie eine Verbindung herstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="161d8-128">**Login group or domain** (Dell SonicWALL Mobile Connect only) - Specify the name of the login group or domain that you want to connect to.</span></span>

<span data-ttu-id="161d8-129">**Benutzerdefiniertes XML**/**EAP-XML:** Geben Sie benutzerdefinierte XML-Befehle zum Konfigurieren der VPN-Verbindung an.</span><span class="sxs-lookup"><span data-stu-id="161d8-129">**Custom XML**/**EAP XML** - Specify any custom XML commands that configure the VPN connection.</span></span>

<span data-ttu-id="161d8-130">**Beispiel für Pulse Secure:**</span><span class="sxs-lookup"><span data-stu-id="161d8-130">**Example for Pulse Secure:**</span></span>

```
    <pulse-schema><isSingleSignOnCredential>true</isSingleSignOnCredential></pulse-schema>
```

<span data-ttu-id="161d8-131">**Beispiel für CheckPoint Mobile VPN:**</span><span class="sxs-lookup"><span data-stu-id="161d8-131">**Example for CheckPoint Mobile VPN:**</span></span>

```
    <CheckPointVPN port="443" name="CheckPointSelfhost" sso="true" debug="3" />
```

<span data-ttu-id="161d8-132">**Beispiel für Dell SonicWALL Mobile Connect:**</span><span class="sxs-lookup"><span data-stu-id="161d8-132">**Example for Dell SonicWALL Mobile Connect:**</span></span>

```
    <MobileConnect><Compression>false</Compression><debugLogging>True</debugLogging><packetCapture>False</packetCapture></MobileConnect>
```

<span data-ttu-id="161d8-133">**Beispiel für F5 Edge Client:**</span><span class="sxs-lookup"><span data-stu-id="161d8-133">**Example for F5 Edge Client:**</span></span>

```
    <f5-vpn-conf><single-sign-on-credential /></f5-vpn-conf>
```

<span data-ttu-id="161d8-134">Weitere Informationen zum Erstellen von benutzerdefinierten XML-Befehlen finden Sie in der VPN-Dokumentation des jeweiligen Herstellers.</span><span class="sxs-lookup"><span data-stu-id="161d8-134">Refer to each manufacturer's VPN documentation for more information about how to write custom XML commands.</span></span>

<span data-ttu-id="161d8-135">**Tunneling teilen** - **Aktivieren** oder **deaktivieren** Sie diese Option, mit der Geräte anhand des Datenverkehrs selbst entscheiden können, welche Verbindung verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="161d8-135">**Split tunneling** - **Enable** or **Disable** this option which lets devices decide which connection to use depending on the traffic.</span></span> <span data-ttu-id="161d8-136">Beispiel: Ein Benutzer in einem Hotel verwendet die VPN-Verbindung zum Zugreifen auf Arbeitsdateien, jedoch das Standardnetzwerk des Hotels für normales Webbrowsen.</span><span class="sxs-lookup"><span data-stu-id="161d8-136">For example, a user in a hotel will use the VPN connection to access work files, but use the hotel's standard network for regular web browsing.</span></span>
- <span data-ttu-id="161d8-137">**Tunnelingrouten für diese VPN-Verbindung teilen:** Fügen Sie optionale Routen für VPN-Drittanbieter hinzu.</span><span class="sxs-lookup"><span data-stu-id="161d8-137">**Split tunneling routes for this VPN connection** - Add optional routes for third-party VPN providers.</span></span> <span data-ttu-id="161d8-138">Geben Sie jedes Mal ein Zielpräfix und eine Präfixgröße für an.</span><span class="sxs-lookup"><span data-stu-id="161d8-138">Specify a destination prefix, and a prefix size for each.</span></span>

## <a name="apps-and-traffic-rules"></a><span data-ttu-id="161d8-139">Regeln für Apps und Datenverkehr</span><span class="sxs-lookup"><span data-stu-id="161d8-139">Apps and Traffic Rules</span></span>

<span data-ttu-id="161d8-140">**VPN-Verbindung auf diese Apps beschränken:** Aktivieren Sie diese Option, wenn nur die angegebenen Apps die VPN-Verbindung verwenden sollen.</span><span class="sxs-lookup"><span data-stu-id="161d8-140">**Restrict VPN connection to these apps** - Enable this option if you only want apps you specify to use the VPN connection.</span></span>
<span data-ttu-id="161d8-141">**Zugeordnete Apps:** Stellen Sie eine Liste von Apps bereit, die automatisch die VPN-Verbindung verwenden.</span><span class="sxs-lookup"><span data-stu-id="161d8-141">**Associated Apps** - Provide a list of apps that will automatically use the VPN connection.</span></span> <span data-ttu-id="161d8-142">Der Typ der App bestimmt den App-Bezeichner.</span><span class="sxs-lookup"><span data-stu-id="161d8-142">The type of app will determine the app identifier.</span></span> <span data-ttu-id="161d8-143">Stellen Sie für eine universelle App den Paketfamiliennamen bereit.</span><span class="sxs-lookup"><span data-stu-id="161d8-143">For a universal app, provide the package family name.</span></span> <span data-ttu-id="161d8-144">Stellen Sie für eine Desktop-App den Dateipfad der App bereit.</span><span class="sxs-lookup"><span data-stu-id="161d8-144">For a desktop app, provide the file path of the app.</span></span>

>[!IMPORTANT]
><span data-ttu-id="161d8-145">Es wird empfohlen, alle Listen mit Apps zu schützen, die Sie für die Verwendung in der Konfiguration eines App-bezogenen VPN zusammenstellen.</span><span class="sxs-lookup"><span data-stu-id="161d8-145">We recommend that you secure all lists of apps that you compile for use in configuration of per-app VPN.</span></span> <span data-ttu-id="161d8-146">Wenn ein nicht autorisierter Benutzer die Liste ändert und Sie sie in die Liste der Apps für App-bezogenes VPN importieren, autorisieren Sie möglicherweise den VPN-Zugriff auf Apps, auf die nicht zugegriffen werden soll.</span><span class="sxs-lookup"><span data-stu-id="161d8-146">If an unauthorized user modifies your list and you import it into the per-app VPN app list, you will potentially authorize VPN access to apps that should not have access.</span></span> <span data-ttu-id="161d8-147">Eine Möglichkeit, App-Listen zu schützen, ist die Verwendung einer Zugriffssteuerungsliste (Access Control List, ACL).</span><span class="sxs-lookup"><span data-stu-id="161d8-147">One way you can secure app lists is by using an access control list (ACL).</span></span>

<span data-ttu-id="161d8-148">**Regeln für den Netzwerkdatenverkehr für diese VPN-Verbindung:** Wählen Sie die Protokolle, die lokalen und Remoteports sowie die Adressbereiche aus, die für die VPN-Verbindung aktiviert werden sollen.</span><span class="sxs-lookup"><span data-stu-id="161d8-148">**Network traffic rules for this VPN connection** - Select which protocols, and which local and remote port and address ranges, will be enabled for the VPN connection.</span></span> <span data-ttu-id="161d8-149">Wenn Sie keine Regel für den Netzwerkdatenverkehr erstellen, werden alle Protokolle, Ports und Adressbereiche aktiviert.</span><span class="sxs-lookup"><span data-stu-id="161d8-149">If you do not create a network traffic rule, all protocols, ports, and address ranges are enabled.</span></span> <span data-ttu-id="161d8-150">Nachdem Sie eine Regel erstellt haben, werden nur die in dieser Regel festgelegten Protokolle, Ports und Adressbereiche von der VPN-Verbindung verwendet.</span><span class="sxs-lookup"><span data-stu-id="161d8-150">After you create a rule, the VPN connection will use only the protocols, ports, and address ranges that you specify in that rule.</span></span>


## <a name="conditional-access"></a><span data-ttu-id="161d8-151">Bedingter Zugriff</span><span class="sxs-lookup"><span data-stu-id="161d8-151">Conditional Access</span></span>

<span data-ttu-id="161d8-152">**Bedingter Zugriff für diese VPN-Verbindung**: Aktiviert den Gerätekompatibilitätsfluss vom Client.</span><span class="sxs-lookup"><span data-stu-id="161d8-152">**Conditional access for this VPN connection** - Enables device compliance flow from the client.</span></span> <span data-ttu-id="161d8-153">Wenn aktiviert, versucht der VPN-Client, mit Azure AD zu kommunizieren, um ein Zertifikat für die Authentifizierung abzurufen.</span><span class="sxs-lookup"><span data-stu-id="161d8-153">When enabled, the VPN client will attempt to communicate with Azure Active Directory to get a certificate to use for authentication.</span></span> <span data-ttu-id="161d8-154">Der VPN sollte für die Zertifikatauthentifizierung eingerichtet sein, und der VPN-Server muss dem Server vertrauen, der von Azure Active Directory zurückgegeben wird.</span><span class="sxs-lookup"><span data-stu-id="161d8-154">The VPN should be set up to use certificate authentication, and the VPN server must trust the server returned by Azure Active Directory.</span></span>

<span data-ttu-id="161d8-155">**Einmaliges Anmelden (Single Sign-On, SSO) mit alternativem Zertifikat**: Verwenden Sie aus Gründen der Gerätekonformität ein anderes Zertifikat als das VPN-Authentifizierungszertifikat für die Kerberos-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="161d8-155">**Single sign-on (SSO) with alternate certificate** - For device compliance, use a certificate different from the VPN authentication certificate for Kerberos authentication.</span></span> <span data-ttu-id="161d8-156">Geben Sie das Zertifikat mit den folgenden Einstellungen an:</span><span class="sxs-lookup"><span data-stu-id="161d8-156">Specify the certificate with the following settings:</span></span> 

- <span data-ttu-id="161d8-157">**Erweiterte Schlüsselverwendung:** Name der erweiterten Schlüsselverwendung (Extended Key Usage, EKU)</span><span class="sxs-lookup"><span data-stu-id="161d8-157">**Extended key usage** - Name for extended key usage (EKU).</span></span>
- <span data-ttu-id="161d8-158">**Objektbezeichner:** Objektbezeichner für EKU</span><span class="sxs-lookup"><span data-stu-id="161d8-158">**Object Identifier** - Object identifier for EKU.</span></span>
- <span data-ttu-id="161d8-159">**Ausstellerhash:** Fingerabdruck des SSO-Zertifikats</span><span class="sxs-lookup"><span data-stu-id="161d8-159">**Issuer hash** - Thumbprint for SSO certificate.</span></span>

## <a name="dns-settings"></a><span data-ttu-id="161d8-160">DNS-Einstellungen</span><span class="sxs-lookup"><span data-stu-id="161d8-160">DNS Settings</span></span>

<span data-ttu-id="161d8-161">**DNS-Namen und -Server für diese VPN-Verbindung:** Wählen Sie die DNS-Server aus, die von der VPN-Verbindung verwendet werden, nachdem die Verbindung hergestellt wurde.</span><span class="sxs-lookup"><span data-stu-id="161d8-161">**DNS names and servers for this VPN connection** - Select which DNS servers the VPN connection will use after the connection is established.</span></span>
<span data-ttu-id="161d8-162">Geben Sie für jeden Server</span><span class="sxs-lookup"><span data-stu-id="161d8-162">For each server.</span></span> <span data-ttu-id="161d8-163">Folgendes an:</span><span class="sxs-lookup"><span data-stu-id="161d8-163">specify:</span></span>
- <span data-ttu-id="161d8-164">**DNS-Name**</span><span class="sxs-lookup"><span data-stu-id="161d8-164">**DNS Name**</span></span>
- <span data-ttu-id="161d8-165">**DNS-Server**</span><span class="sxs-lookup"><span data-stu-id="161d8-165">**DNS Server**</span></span>
- <span data-ttu-id="161d8-166">**Proxy**</span><span class="sxs-lookup"><span data-stu-id="161d8-166">**Proxy**</span></span>

## <a name="proxy-settings"></a><span data-ttu-id="161d8-167">Proxyeinstellungen</span><span class="sxs-lookup"><span data-stu-id="161d8-167">Proxy settings</span></span>

- <span data-ttu-id="161d8-168">**Proxyeinstellungen automatisch erkennen:** Wenn der VPN-Server einen Proxyserver für die Verbindung erfordert, geben Sie an, ob Geräte die Verbindungseinstellungen automatisch erkennen können sollen.</span><span class="sxs-lookup"><span data-stu-id="161d8-168">**Automatically detect proxy settings** - If your VPN server requires a proxy server for the connection, specify whether you want devices to automatically detect the connection settings.</span></span> <span data-ttu-id="161d8-169">Weitere Informationen finden Sie in der Windows Server-Dokumentation.</span><span class="sxs-lookup"><span data-stu-id="161d8-169">For more information, see your Windows Server documentation.</span></span>
- <span data-ttu-id="161d8-170">**Automatisches Konfigurationsskript:** Verwenden Sie eine Datei zum Konfigurieren des Proxyservers.</span><span class="sxs-lookup"><span data-stu-id="161d8-170">**Automatic configuration script** - Use a file to configure the proxy server.</span></span> <span data-ttu-id="161d8-171">Geben Sie die **Proxyserver-URL** ein (z.B. **http://proxy.contoso.com**), unter der die Konfigurationsdatei zu finden ist.</span><span class="sxs-lookup"><span data-stu-id="161d8-171">Enter the **Proxy server URL** (for example **http://proxy.contoso.com**) which contains the configuration file.</span></span>
- <span data-ttu-id="161d8-172">**Proxyserver verwenden:** Aktivieren Sie diese Option, wenn Sie die Proxyeinstellungen für den Server manuell eingeben möchten.</span><span class="sxs-lookup"><span data-stu-id="161d8-172">**Use proxy server** - Enable this option if you want to manually enter the proxy server settings.</span></span>
    - <span data-ttu-id="161d8-173">**Adresse:** Geben Sie die Adresse des Proxyservers (als IP-Adresse) ein.</span><span class="sxs-lookup"><span data-stu-id="161d8-173">**Address** - Enter the proxy server address (as an IP address).</span></span>
    - <span data-ttu-id="161d8-174">**Portnummer:** Geben Sie die Portnummer ein, die dem Proxyserver zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="161d8-174">**Port number** - Enter the port number associated with the proxy server.</span></span>
- <span data-ttu-id="161d8-175">**Proxy für lokale Adressen umgehen:** Wenn der VPN-Server einen Proxyserver für die Verbindung erfordert, aktivieren Sie diese Option, wenn der Proxyserver für von Ihnen angegebene lokale Adressen nicht verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="161d8-175">**Bypass proxy for local addresses** - If your VPN server requires a proxy server for the connection, select this option if you do not want to use the proxy server for local addresses that you specify.</span></span> <span data-ttu-id="161d8-176">Weitere Informationen finden Sie in der Windows Server-Dokumentation.</span><span class="sxs-lookup"><span data-stu-id="161d8-176">For more information, see your Windows Server documentation.</span></span>
