---
title: "VPN-Einstellungen für macOS-Geräte in Intune"
titlesuffix: Azure portal
description: "Erfahren Sie etwas über die Intune-Einstellungen, die Sie zum Konfigurieren von VPN-Verbindungen auf macOS-Geräten verwenden können.\""
keywords: 
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 05/04/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d203a70d-37df-4195-85f7-ad5ef14ac2a1
ms.reviewer: karanda
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: d786cc307dcbbf070882f72d3a870454a78c7262
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2017
---
# <a name="vpn-settings-for-macos-devices-in-microsoft-intune"></a><span data-ttu-id="7c3c9-103">VPN-Einstellungen für macOS-Geräte in Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="7c3c9-103">VPN settings for macOS devices in Microsoft Intune</span></span>

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="7c3c9-104">Je nach den ausgewählten Einstellungen können nicht alle Werte in der folgenden Liste konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="7c3c9-104">Depending on the settings you choose, not all values in the list below will be configurable.</span></span>

## <a name="base-vpn-settings"></a><span data-ttu-id="7c3c9-105">**Grundlegende VPN-Einstellungen**</span><span class="sxs-lookup"><span data-stu-id="7c3c9-105">**Base VPN settings**</span></span>

<span data-ttu-id="7c3c9-106">**Verbindungsname:** Geben Sie einen Namen für diese Verbindung ein.</span><span class="sxs-lookup"><span data-stu-id="7c3c9-106">**Connection name** - Enter a name for this connection.</span></span> <span data-ttu-id="7c3c9-107">Endbenutzern wird dieser Name angezeigt, wenn sie auf ihrem Gerät die Liste der verfügbaren VPN-Verbindungen durchsuchen.</span><span class="sxs-lookup"><span data-stu-id="7c3c9-107">End users will see this name when they browse their device for the list of available VPN connections.</span></span>
- <span data-ttu-id="7c3c9-108">**IP-Adresse oder FQDN:** Geben Sie die IP-Adresse oder den vollqualifizierten Domänennamen des VPN-Servers an, mit dem Geräte eine Verbindung herstellen.</span><span class="sxs-lookup"><span data-stu-id="7c3c9-108">**IP address or FQDN** - Provide the IP address or fully qualified domain name of the VPN server that devices will connect to.</span></span> <span data-ttu-id="7c3c9-109">Beispiele: **192.168.1.1**, **vpn.contoso.com**.</span><span class="sxs-lookup"><span data-stu-id="7c3c9-109">Examples: **192.168.1.1**, **vpn.contoso.com**.</span></span>
- <span data-ttu-id="7c3c9-110">**Authentifizierungsmethode:** Wählen Sie unter folgenden Optionen aus, wie sich Geräte beim VPN-Server authentifizieren:</span><span class="sxs-lookup"><span data-stu-id="7c3c9-110">**Authentication method** - Choose how devices will authenticate to the VPN server from:</span></span>
    - <span data-ttu-id="7c3c9-111">**Zertifikate:** Wählen Sie unter **Authentifizierungszertifikat** ein zuvor erstelltes SCEP- oder PKCS-Zertifikatprofil zum Authentifizieren der Verbindung aus.</span><span class="sxs-lookup"><span data-stu-id="7c3c9-111">**Certificates** - Under **Authentication certificate**, Choose a SCEP or PKCS certificate profile you previously created to authenticate the connection.</span></span> <span data-ttu-id="7c3c9-112">Ausführliche Informationen zu Zertifikatprofilen finden Sie unter [Konfigurieren von Zertifikaten](certificates-configure.md).</span><span class="sxs-lookup"><span data-stu-id="7c3c9-112">For more details about certificate profiles, see [How to configure certificates](certificates-configure.md).</span></span>
    - <span data-ttu-id="7c3c9-113">**Benutzername und Kennwort:** Endbenutzer müssen einen Benutzernamen und ein Kennwort für die Anmeldung beim VPN-Server angeben.</span><span class="sxs-lookup"><span data-stu-id="7c3c9-113">**Username and password** - End users must supply a username and password to log into the VPN server.</span></span>
- <span data-ttu-id="7c3c9-114">**Verbindungstyp:** Wählen Sie den VPN-Verbindungstyp in der folgenden Liste von Anbietern aus:</span><span class="sxs-lookup"><span data-stu-id="7c3c9-114">**Connection type** - Select the VPN connection type from the following list of vendors:</span></span>
    - <span data-ttu-id="7c3c9-115">**Check Point Capsule VPN**</span><span class="sxs-lookup"><span data-stu-id="7c3c9-115">**Check Point Capsule VPN**</span></span>
    - <span data-ttu-id="7c3c9-116">**Cisco AnyConnect**</span><span class="sxs-lookup"><span data-stu-id="7c3c9-116">**Cisco AnyConnect**</span></span>
    - <span data-ttu-id="7c3c9-117">**Dell SonicWALL Mobile Connect**</span><span class="sxs-lookup"><span data-stu-id="7c3c9-117">**Dell SonicWALL Mobile Connect**</span></span>
    - <span data-ttu-id="7c3c9-118">**F5 Edge Client**</span><span class="sxs-lookup"><span data-stu-id="7c3c9-118">**F5 Edge Client**</span></span>
    - <span data-ttu-id="7c3c9-119">**Pulse Secure**</span><span class="sxs-lookup"><span data-stu-id="7c3c9-119">**Pulse Secure**</span></span>
    - <span data-ttu-id="7c3c9-120">**Benutzerdefiniertes VPN**</span><span class="sxs-lookup"><span data-stu-id="7c3c9-120">**Custom VPN**</span></span>
- <span data-ttu-id="7c3c9-121">**Tunneling teilen** - **Aktivieren** oder **deaktivieren** Sie diese Option, mit der Geräte anhand des Datenverkehrs selbst entscheiden können, welche Verbindung verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="7c3c9-121">**Split tunneling** - **Enable** or **Disable** this option which lets devices decide which connection to use depending on the traffic.</span></span> <span data-ttu-id="7c3c9-122">Beispiel: Ein Benutzer in einem Hotel verwendet die VPN-Verbindung zum Zugreifen auf Arbeitsdateien, jedoch das Standardnetzwerk des Hotels für normales Webbrowsen.</span><span class="sxs-lookup"><span data-stu-id="7c3c9-122">For example, a user in a hotel will use the VPN connection to access work files, but use the hotel's standard network for regular web browsing.</span></span>

<!--- **Per-app VPN** - Select this option if you want to associate this VPN connection with an iOS or macOS app so that the connection will be opened when the app is run. You can associate the VPN profile with an app when you assign the software. For more information, see [How to assign and monitor apps](apps-deploy.md). --->

## <a name="custom-vpn-settings"></a><span data-ttu-id="7c3c9-123">Benutzerdefinierte VPN-Einstellungen</span><span class="sxs-lookup"><span data-stu-id="7c3c9-123">Custom VPN settings</span></span>

<span data-ttu-id="7c3c9-124">Wenn Sie **Benutzerdefiniertes VPN** ausgewählt haben, konfigurieren Sie diese weiteren Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="7c3c9-124">If you selected **Custom VPN**, configure these further settings:</span></span>

- <span data-ttu-id="7c3c9-125">**VPN-Bezeichner:** Dies ist ein Bezeichner für die verwendete VPN-App und wird von Ihrem VPN-Anbieter bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="7c3c9-125">**VPN identifier** This is an identifier for the VPN app you are using, and is supplied by your VPN provider.</span></span>
- <span data-ttu-id="7c3c9-126">**Geben Sie Schlüssel-Wert-Paare für die benutzerdefinierten VPN-Attribute ein:** Fügen Sie **Schlüssel** und **Werte** zum Anpassen der VPN-Verbindung hinzu, oder importieren Sie sie.</span><span class="sxs-lookup"><span data-stu-id="7c3c9-126">**Enter key and value pairs for the custom VPN attributes** Add or import **Keys** and **Values** that customize your VPN connection.</span></span> <span data-ttu-id="7c3c9-127">Auch diese Werte werden in der Regel von Ihrem VPN-Anbieter bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="7c3c9-127">Again, these values are typically supplied by your VPN provider.</span></span>


## <a name="proxy-settings"></a><span data-ttu-id="7c3c9-128">Proxyeinstellungen</span><span class="sxs-lookup"><span data-stu-id="7c3c9-128">Proxy settings</span></span>

- <span data-ttu-id="7c3c9-129">**Automatisches Konfigurationsskript:** Verwenden Sie eine Datei zum Konfigurieren des Proxyservers.</span><span class="sxs-lookup"><span data-stu-id="7c3c9-129">**Automatic configuration script** - Use a file to configure the proxy server.</span></span> <span data-ttu-id="7c3c9-130">Geben Sie die **Proxyserver-URL** ein (z.B. **http://proxy.contoso.com**), unter der die Konfigurationsdatei zu finden ist.</span><span class="sxs-lookup"><span data-stu-id="7c3c9-130">Enter the **Proxy server URL** (for example **http://proxy.contoso.com**) which contains the configuration file.</span></span>
- <span data-ttu-id="7c3c9-131">**Adresse:** Geben Sie die Adresse des Proxyservers (als IP-Adresse) ein.</span><span class="sxs-lookup"><span data-stu-id="7c3c9-131">**Address** - Enter the proxy server address (as an IP address).</span></span>
- <span data-ttu-id="7c3c9-132">**Portnummer:** Geben Sie die Portnummer ein, die dem Proxyserver zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="7c3c9-132">**Port number** - Enter the port number associated with the proxy server.</span></span>
