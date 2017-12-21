---
title: "VPN-Einstellungen in Intune für Windows 8.1-Geräte"
titleSuffix: Azure portal
description: "Erfahren Sie etwas über die Intune-Einstellungen, die Sie zum Konfigurieren von VPN-Verbindungen auf Windows 8.1-Geräten verwenden können.\""
keywords: 
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 02/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 00a602d9-b339-4fd8-ab70-defbf6686855
ms.reviewer: karanda
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 60f488341f0e8ee373c8ded1684f6e03006b479a
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2017
---
# <a name="vpn-settings-for-windows-81-devices-in-microsoft-intune"></a><span data-ttu-id="833e2-103">VPN-Einstellungen für Windows 8.1-Geräte in Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="833e2-103">VPN settings for Windows 8.1 devices in Microsoft Intune</span></span>

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="833e2-104">Je nach den ausgewählten Einstellungen können nicht alle Werte in der folgenden Liste konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="833e2-104">Depending on the settings you choose, not all values in the list below will be configurable.</span></span>

## <a name="base-vpn-settings"></a><span data-ttu-id="833e2-105">Grundlegende VPN-Einstellungen</span><span class="sxs-lookup"><span data-stu-id="833e2-105">Base VPN settings</span></span>


- <span data-ttu-id="833e2-106">**Alle Einstellungen nur auf Windows 8.1 anwenden:** Diese Einstellung können Sie im klassischen Intune-Portal konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="833e2-106">**Apply all settings to Windows 8.1 only** - This is a setting you can configure in the Intune classic portal.</span></span> <span data-ttu-id="833e2-107">Im Azure-Portal kann diese Einstellung nicht geändert werden.</span><span class="sxs-lookup"><span data-stu-id="833e2-107">In the Azure portal, this setting cannot be changed.</span></span> <span data-ttu-id="833e2-108">Wenn hierfür **Konfiguriert** festgelegt wird, werden sämtliche Einstellungen nur auf Windows 8.1-Geräte angewendet.</span><span class="sxs-lookup"><span data-stu-id="833e2-108">If this is set to **Configured**, any settings will only be applied to Windows 8.1 devices.</span></span> <span data-ttu-id="833e2-109">Wenn **Nicht konfiguriert** festgelegt wird, gelten diese Einstellungen auch für Windows 10-Geräte.</span><span class="sxs-lookup"><span data-stu-id="833e2-109">If set to **Not Configured**, these settings will also apply to Windows 10 devices.</span></span>
- <span data-ttu-id="833e2-110">**Verbindungsname:** Geben Sie einen Namen für diese Verbindung ein.</span><span class="sxs-lookup"><span data-stu-id="833e2-110">**Connection name** - Enter a name for this connection.</span></span> <span data-ttu-id="833e2-111">Endbenutzern wird dieser Name angezeigt, wenn sie auf ihrem Gerät die Liste der verfügbaren VPN-Verbindungen durchsuchen.</span><span class="sxs-lookup"><span data-stu-id="833e2-111">End users will see this name when they browse their device for the list of available VPN connections.</span></span>
- <span data-ttu-id="833e2-112">**Server:** Fügen Sie einen oder mehrere VPN-Server hinzu, mit denen Geräte eine Verbindung herstellen.</span><span class="sxs-lookup"><span data-stu-id="833e2-112">**Servers** - Add one or more VPN servers that devices will connect to.</span></span>
    - <span data-ttu-id="833e2-113">**Hinzufügen:** öffnet das Blatt **Zeile hinzufügen**, auf dem Sie die folgende Informationen angeben können:</span><span class="sxs-lookup"><span data-stu-id="833e2-113">**Add** - Opens the **Add Row** blade where you can specify the following information:</span></span>
        - <span data-ttu-id="833e2-114">**Beschreibung:** Geben Sie einen beschreibenden Namen für den Server ein, z.B. **Contoso-VPN-Server**.</span><span class="sxs-lookup"><span data-stu-id="833e2-114">**Description** - Specify a descriptive name for the server like **Contoso VPN server**.</span></span>
        - <span data-ttu-id="833e2-115">**IP-Adresse oder FQDN:** Geben Sie die IP-Adresse oder den vollqualifizierten Domänennamen des VPN-Servers an, mit dem Geräte eine Verbindung herstellen.</span><span class="sxs-lookup"><span data-stu-id="833e2-115">**IP address or FQDN** - Provide the IP address or fully qualified domain name of the VPN server that devices will connect to.</span></span> <span data-ttu-id="833e2-116">Beispiele: **192.168.1.1**, **vpn.contoso.com**.</span><span class="sxs-lookup"><span data-stu-id="833e2-116">Examples: **192.168.1.1**, **vpn.contoso.com**.</span></span>
        - <span data-ttu-id="833e2-117">**Standardserver:** aktiviert diesen Server als Standardserver, über den Geräte die Verbindung herstellen.</span><span class="sxs-lookup"><span data-stu-id="833e2-117">**Default server** - Enables this server as the default server that devices will use to establish the connection.</span></span> <span data-ttu-id="833e2-118">Achten Sie darauf, nur einen Server als Standard festzulegen.</span><span class="sxs-lookup"><span data-stu-id="833e2-118">Make sure to set only one server as the default.</span></span>
    - <span data-ttu-id="833e2-119">**Importieren:** Suchen Sie nach einer Datei, die eine durch Trennzeichen getrennte Liste von Servern im Format „Beschreibung, IP-Adresse oder FQDN, Standardserver“ enthält.</span><span class="sxs-lookup"><span data-stu-id="833e2-119">**Import** - Browse to a file containing a comma-seperated list of servers in the format description, IP address or FQDN, Default server.</span></span> <span data-ttu-id="833e2-120">Wählen Sie **OK** aus, um diese in die Liste **Server** zu importieren.</span><span class="sxs-lookup"><span data-stu-id="833e2-120">Choose **OK** to import these into the **Servers** list.</span></span>
    - <span data-ttu-id="833e2-121">**Exportieren:** exportiert die Liste der Server in eine CSV-Datei (Comma-Separated Values, durch Trennzeichen getrennte Werte).</span><span class="sxs-lookup"><span data-stu-id="833e2-121">**Export** - Exports the list of servers to a comma-seperated-values (csv) file.</span></span>

- <span data-ttu-id="833e2-122">**Verbindungstyp:** Wählen Sie den VPN-Verbindungstyp in der folgenden Liste von Anbietern aus:</span><span class="sxs-lookup"><span data-stu-id="833e2-122">**Connection type** - Select the VPN connection type from the following list of vendors:</span></span>
- <span data-ttu-id="833e2-123">**Check Point Capsule VPN**</span><span class="sxs-lookup"><span data-stu-id="833e2-123">**Check Point Capsule VPN**</span></span>
- <span data-ttu-id="833e2-124">**Dell SonicWALL Mobile Connect**</span><span class="sxs-lookup"><span data-stu-id="833e2-124">**Dell SonicWALL Mobile Connect**</span></span>
- <span data-ttu-id="833e2-125">**F5 Edge Client**</span><span class="sxs-lookup"><span data-stu-id="833e2-125">**F5 Edge Client**</span></span>
- <span data-ttu-id="833e2-126">**Pulse Secure**</span><span class="sxs-lookup"><span data-stu-id="833e2-126">**Pulse Secure**</span></span>

<!--- **Fingerprint** (Check Point Capsule VPN only) - Specify a string (for example, "Contoso Fingerprint Code") that will be used to verify that the VPN server can be trusted. A fingerprint can be sent to the client so it knows to trust any server that presents the same fingerprint when connecting. If the device doesn’t already have the fingerprint, it will prompt the user to trust the VPN server that they are connecting to while showing the fingerprint. (The user manually verifies the fingerprint and chooses **trust** to connect.) --->

- <span data-ttu-id="833e2-127">**Anmeldegruppe oder -domäne** (nur Dell SonicWALL Mobile Connect): Geben Sie den Namen der Anmeldegruppe oder -domäne an, mit der Sie eine Verbindung herstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="833e2-127">**Login group or domain** (Dell SonicWALL Mobile Connect only) - Specify the name of the login group or domain that you want to connect to.</span></span>

- <span data-ttu-id="833e2-128">**Rolle** (nur Pulse Secure): Geben Sie den Namen der Benutzerrolle an, die Zugriff auf diese Verbindung hat.</span><span class="sxs-lookup"><span data-stu-id="833e2-128">**Role** (Pulse Secure only) - Specify the name of the user role that has access to this connection.</span></span> <span data-ttu-id="833e2-129">Eine Benutzerrolle definiert persönliche Einstellungen und Optionen und aktiviert oder deaktiviert bestimmte Zugriffsfeatures.</span><span class="sxs-lookup"><span data-stu-id="833e2-129">A user role defines personal settings and options, and it enables or disables certain access features.</span></span>

- <span data-ttu-id="833e2-130">**Bereich** (nur Pulse Secure): Geben Sie den Namen des gewünschten Authentifizierungsbereichs an.</span><span class="sxs-lookup"><span data-stu-id="833e2-130">**Realm** (Pulse Secure only) - Specify the name of the authentication realm that you want to use.</span></span> <span data-ttu-id="833e2-131">Ein Authentifizierungsbereich ist eine Gruppe von Authentifizierungsressourcen, die vom Verbindungstyp „Pulse Secure“ verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="833e2-131">An authentication realm is a grouping of authentication resources that the Pulse Secure connection type uses.</span></span>


- <span data-ttu-id="833e2-132">**Benutzerdefiniertes XML:** Geben Sie benutzerdefinierte XML-Befehle zum Konfigurieren der VPN-Verbindung an.</span><span class="sxs-lookup"><span data-stu-id="833e2-132">**Custom XML** - Specify any custom XML commands that configure the VPN connection.</span></span>

<span data-ttu-id="833e2-133">**Beispiel für Pulse Secure:**</span><span class="sxs-lookup"><span data-stu-id="833e2-133">**Example for Pulse Secure:**</span></span>

```
    <pulse-schema><isSingleSignOnCredential>true</isSingleSignOnCredential></pulse-schema>

```

<span data-ttu-id="833e2-134">**Beispiel für CheckPoint Mobile VPN:**</span><span class="sxs-lookup"><span data-stu-id="833e2-134">**Example for CheckPoint Mobile VPN:**</span></span>
```
    <CheckPointVPN port="443" name="CheckPointSelfhost" sso="true" debug="3" />

```

<span data-ttu-id="833e2-135">**Beispiel für Dell SonicWALL Mobile Connect:**</span><span class="sxs-lookup"><span data-stu-id="833e2-135">**Example for Dell SonicWALL Mobile Connect:**</span></span>
```
    <MobileConnect><Compression>false</Compression><debugLogging>True</debugLogging><packetCapture>False</packetCapture></MobileConnect>

```

<span data-ttu-id="833e2-136">**Beispiel für F5 Edge Client:**</span><span class="sxs-lookup"><span data-stu-id="833e2-136">**Example for F5 Edge Client:**</span></span>

```
    <f5-vpn-conf><single-sign-on-credential /></f5-vpn-conf>

```

<span data-ttu-id="833e2-137">Weitere Informationen zum Erstellen von benutzerdefinierten XML-Befehlen finden Sie in der VPN-Dokumentation des jeweiligen Herstellers.</span><span class="sxs-lookup"><span data-stu-id="833e2-137">Refer to each manufacturer's VPN documentation for more information about how to write custom XML commands.</span></span>


## <a name="proxy-settings"></a><span data-ttu-id="833e2-138">Proxyeinstellungen</span><span class="sxs-lookup"><span data-stu-id="833e2-138">Proxy settings</span></span>

- <span data-ttu-id="833e2-139">**Proxyeinstellungen automatisch erkennen:** Wenn der VPN-Server einen Proxyserver für die Verbindung erfordert, geben Sie an, ob Geräte die Verbindungseinstellungen automatisch erkennen können sollen.</span><span class="sxs-lookup"><span data-stu-id="833e2-139">**Automatically detect proxy settings** - If your VPN server requires a proxy server for the connection, specify whether you want devices to automatically detect the connection settings.</span></span> <span data-ttu-id="833e2-140">Weitere Informationen finden Sie in der Windows Server-Dokumentation.</span><span class="sxs-lookup"><span data-stu-id="833e2-140">For more information, see your Windows Server documentation.</span></span>
- <span data-ttu-id="833e2-141">**Automatisches Konfigurationsskript:** Verwenden Sie eine Datei zum Konfigurieren des Proxyservers.</span><span class="sxs-lookup"><span data-stu-id="833e2-141">**Automatic configuration script** - Use a file to configure the proxy server.</span></span> <span data-ttu-id="833e2-142">Geben Sie die **Proxyserver-URL** ein (z.B. **http://proxy.contoso.com**), unter der die Konfigurationsdatei zu finden ist.</span><span class="sxs-lookup"><span data-stu-id="833e2-142">Enter the **Proxy server URL** (for example **http://proxy.contoso.com**) which contains the configuration file.</span></span>
- <span data-ttu-id="833e2-143">**Proxyserver verwenden:** Aktivieren Sie diese Option, wenn Sie die Proxyeinstellungen für den Server manuell eingeben möchten.</span><span class="sxs-lookup"><span data-stu-id="833e2-143">**Use proxy server** - Enable this option if you want to manually enter the proxy server settings.</span></span>
    - <span data-ttu-id="833e2-144">**Adresse:** Geben Sie die Adresse des Proxyservers (als IP-Adresse) ein.</span><span class="sxs-lookup"><span data-stu-id="833e2-144">**Address** - Enter the proxy server address (as an IP address).</span></span>
    - <span data-ttu-id="833e2-145">**Portnummer:** Geben Sie die Portnummer ein, die dem Proxyserver zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="833e2-145">**Port number** - Enter the port number associated with the proxy server.</span></span>
- <span data-ttu-id="833e2-146">**Proxy für lokale Adressen umgehen:** Wenn der VPN-Server einen Proxyserver für die Verbindung erfordert, aktivieren Sie diese Option, wenn der Proxyserver für von Ihnen angegebene lokale Adressen nicht verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="833e2-146">**Bypass proxy for local addresses** - If your VPN server requires a proxy server for the connection, select this option if you do not want to use the proxy server for local addresses that you specify.</span></span> <span data-ttu-id="833e2-147">Weitere Informationen finden Sie in der Windows Server-Dokumentation.</span><span class="sxs-lookup"><span data-stu-id="833e2-147">For more information, see your Windows Server documentation.</span></span>
