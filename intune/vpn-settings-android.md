---
title: "VPN-Einstellungen für Android-Geräte in Intune"
titlesuffix: Azure portal
description: "Erfahren Sie etwas über die Intune-Einstellungen, die Sie zum Konfigurieren von VPN-Verbindungen auf Android-Geräten verwenden können."
keywords: 
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 06/15/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 16c056ca-320e-4107-ad03-a0cf96c28885
ms.reviewer: karanda
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: bdf7d25bcadec74198b03997c441e1fef68d171a
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2018
---
# <a name="vpn-settings-for-android-devices-in-microsoft-intune"></a><span data-ttu-id="24b9b-103">VPN-Einstellungen für Android-Geräte in Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="24b9b-103">VPN settings for Android devices in Microsoft Intune</span></span>

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="24b9b-104">Als Intune-Administrator können Sie VPN-Einstellungen für die folgenden Plattformen konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="24b9b-104">As an Intune admin, you can configure VPN settings for the following platforms:</span></span>

- [<span data-ttu-id="24b9b-105">Android</span><span class="sxs-lookup"><span data-stu-id="24b9b-105">Android</span></span>](#android-vpn-settings)
- [<span data-ttu-id="24b9b-106">Android for Work</span><span class="sxs-lookup"><span data-stu-id="24b9b-106">Android for Work</span></span>](#android-for-work-vpn-settings)

<span data-ttu-id="24b9b-107">Je nach den ausgewählten Einstellungen können nicht alle der unten aufgeführten Werte konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="24b9b-107">Depending on the settings you choose, not all values listed below are configurable.</span></span>

## <a name="android-vpn-settings"></a><span data-ttu-id="24b9b-108">Android-VPN-Einstellungen</span><span class="sxs-lookup"><span data-stu-id="24b9b-108">Android VPN settings</span></span>
<span data-ttu-id="24b9b-109">**Verbindungsname:** Geben Sie einen Namen für diese Verbindung ein.</span><span class="sxs-lookup"><span data-stu-id="24b9b-109">**Connection name** - Enter a name for this connection.</span></span> <span data-ttu-id="24b9b-110">Endbenutzern wird dieser Name angezeigt, wenn sie auf ihrem Gerät die Liste der verfügbaren VPN-Verbindungen durchsuchen.</span><span class="sxs-lookup"><span data-stu-id="24b9b-110">End users will see this name when they browse their device for the list of available VPN connections.</span></span>
- <span data-ttu-id="24b9b-111">**IP-Adresse oder FQDN:** Geben Sie die IP-Adresse oder den vollqualifizierten Domänennamen des VPN-Servers an, mit dem Geräte eine Verbindung herstellen.</span><span class="sxs-lookup"><span data-stu-id="24b9b-111">**IP address or FQDN** - Provide the IP address or fully qualified domain name of the VPN server that devices will connect to.</span></span> <span data-ttu-id="24b9b-112">Beispiele: **192.168.1.1**, **vpn.contoso.com**.</span><span class="sxs-lookup"><span data-stu-id="24b9b-112">Examples: **192.168.1.1**, **vpn.contoso.com**.</span></span>
- <span data-ttu-id="24b9b-113">**Authentifizierungsmethode:** Wählen Sie unter folgenden Optionen aus, wie sich Geräte beim VPN-Server authentifizieren:</span><span class="sxs-lookup"><span data-stu-id="24b9b-113">**Authentication method** - Choose how devices will authenticate to the VPN server from:</span></span>
    - <span data-ttu-id="24b9b-114">**Zertifikate:** Wählen Sie ein zuvor erstelltes SCEP- oder PKCS-Zertifikatprofil zum Authentifizieren der Verbindung aus.</span><span class="sxs-lookup"><span data-stu-id="24b9b-114">**Certificates** - Select a SCEP or PKCS certificate profile you previously created to authenticate the connection.</span></span> <span data-ttu-id="24b9b-115">Ausführliche Informationen zu Zertifikatprofilen finden Sie unter [Konfigurieren von Zertifikaten](certificates-configure.md).</span><span class="sxs-lookup"><span data-stu-id="24b9b-115">For more details about certificate profiles, see [How to configure certificates](certificates-configure.md).</span></span>
    - <span data-ttu-id="24b9b-116">**Benutzername und Kennwort:** Endbenutzer müssen einen Benutzernamen und ein Kennwort für die Anmeldung beim VPN-Server angeben.</span><span class="sxs-lookup"><span data-stu-id="24b9b-116">**Username and password** - End users must supply a user name and password to log into the VPN server.</span></span>
- <span data-ttu-id="24b9b-117">**Verbindungstyp:** Wählen Sie den VPN-Verbindungstyp in der folgenden Liste von Anbietern aus:</span><span class="sxs-lookup"><span data-stu-id="24b9b-117">**Connection type** - Select the VPN connection type from the following list of vendors:</span></span>
    - <span data-ttu-id="24b9b-118">**Check Point Capsule VPN**</span><span class="sxs-lookup"><span data-stu-id="24b9b-118">**Check Point Capsule VPN**</span></span>
    - <span data-ttu-id="24b9b-119">**Cisco AnyConnect**</span><span class="sxs-lookup"><span data-stu-id="24b9b-119">**Cisco AnyConnect**</span></span>
    - <span data-ttu-id="24b9b-120">**Dell SonicWALL Mobile Connect**</span><span class="sxs-lookup"><span data-stu-id="24b9b-120">**Dell SonicWALL Mobile Connect**</span></span>
    - <span data-ttu-id="24b9b-121">**F5 Edge Client**</span><span class="sxs-lookup"><span data-stu-id="24b9b-121">**F5 Edge Client**</span></span>
    - <span data-ttu-id="24b9b-122">**Pulse Secure**</span><span class="sxs-lookup"><span data-stu-id="24b9b-122">**Pulse Secure**</span></span>
    - <span data-ttu-id="24b9b-123">**Citrix**</span><span class="sxs-lookup"><span data-stu-id="24b9b-123">**Citrix**</span></span>

- <span data-ttu-id="24b9b-124">**Fingerabdruck** (nur Check Point Capsule VPN): Geben Sie eine Zeichenfolge (z.B. „Contoso-Fingerabdruckcode“) an, mit der überprüft wird, ob der VPN-Server vertrauenswürdig ist.</span><span class="sxs-lookup"><span data-stu-id="24b9b-124">**Fingerprint** (Check Point Capsule VPN only) - Specify a string (for example, "Contoso Fingerprint Code") that will be used to verify that the VPN server can be trusted.</span></span> <span data-ttu-id="24b9b-125">Ein Fingerabdruck kann an den Client gesendet werden, damit dieser weiß, dass alle Server vertrauenswürdig sind, die beim Verbinden den betreffenden Fingerabdruck vorweisen.</span><span class="sxs-lookup"><span data-stu-id="24b9b-125">A fingerprint can be sent to the client so it knows to trust any server that presents the same fingerprint when connecting.</span></span> <span data-ttu-id="24b9b-126">Wenn das Gerät noch nicht über den Fingerabdruck verfügt, wird der Benutzer aufgefordert, dem VPN-Server zu vertrauen, mit dem eine Verbindung hergestellt wird, während der Fingerabdruck angezeigt wird. (Der Benutzer überprüft den Fingerabdruck manuell und klickt auf „Vertrauen“, um die Verbindung herzustellen.)</span><span class="sxs-lookup"><span data-stu-id="24b9b-126">If the device doesn’t already have the fingerprint, it will prompt the user to trust the VPN server that they are connecting to while showing the fingerprint (The user manually verifies the fingerprint and chooses trust to connect).</span></span>
- <span data-ttu-id="24b9b-127">**Geben Sie Schlüssel-Wert-Paare für die Citrix-VPN-Attribute ein** (nur Citrix): Geben Sie von Citrix bereitgestellte Schlüssel-Wert-Paare ein, um die Eigenschaften der VPN-Verbindung zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="24b9b-127">**Enter key and value pairs for the Citrix VPN attributes** (Citrix only) - Enter key and value pairs, provided by Citrix, to configure the properties of the VPN connection.</span></span>

## <a name="android-for-work-vpn-settings"></a><span data-ttu-id="24b9b-128">VPN-Einstellungen für Android for Work</span><span class="sxs-lookup"><span data-stu-id="24b9b-128">Android for Work VPN settings</span></span>

<span data-ttu-id="24b9b-129">**Verbindungsname:** Geben Sie einen Namen für diese Verbindung ein.</span><span class="sxs-lookup"><span data-stu-id="24b9b-129">**Connection name** - Enter a name for this connection.</span></span> <span data-ttu-id="24b9b-130">Endbenutzern wird dieser Name angezeigt, wenn sie auf ihrem Gerät die Liste der verfügbaren VPN-Verbindungen durchsuchen.</span><span class="sxs-lookup"><span data-stu-id="24b9b-130">End users will see this name when they browse their device for the list of available VPN connections.</span></span>
- <span data-ttu-id="24b9b-131">**IP-Adresse oder FQDN:** Geben Sie die IP-Adresse oder den vollqualifizierten Domänennamen des VPN-Servers an, mit dem Geräte eine Verbindung herstellen.</span><span class="sxs-lookup"><span data-stu-id="24b9b-131">**IP address or FQDN** - Provide the IP address or fully qualified domain name of the VPN server that devices will connect to.</span></span> <span data-ttu-id="24b9b-132">Beispiele: **192.168.1.1**, **vpn.contoso.com**.</span><span class="sxs-lookup"><span data-stu-id="24b9b-132">Examples: **192.168.1.1**, **vpn.contoso.com**.</span></span>
- <span data-ttu-id="24b9b-133">**Authentifizierungsmethode:** Wählen Sie unter folgenden Optionen aus, wie sich Geräte beim VPN-Server authentifizieren:</span><span class="sxs-lookup"><span data-stu-id="24b9b-133">**Authentication method** - Choose how devices will authenticate to the VPN server from:</span></span>
    - <span data-ttu-id="24b9b-134">**Zertifikate:** Wählen Sie ein zuvor erstelltes SCEP- oder PKCS-Zertifikatprofil zum Authentifizieren der Verbindung aus.</span><span class="sxs-lookup"><span data-stu-id="24b9b-134">**Certificates** - Select a SCEP or PKCS certificate profile you previously created to authenticate the connection.</span></span> <span data-ttu-id="24b9b-135">Ausführliche Informationen zu Zertifikatprofilen finden Sie unter [Konfigurieren von Zertifikaten](certificates-configure.md).</span><span class="sxs-lookup"><span data-stu-id="24b9b-135">For more details about certificate profiles, see [How to configure certificates](certificates-configure.md).</span></span>
    - <span data-ttu-id="24b9b-136">**Benutzername und Kennwort:** Endbenutzer müssen einen Benutzernamen und ein Kennwort für die Anmeldung beim VPN-Server angeben.</span><span class="sxs-lookup"><span data-stu-id="24b9b-136">**Username and password** - End users must supply a user name and password to log into the VPN server.</span></span>
- <span data-ttu-id="24b9b-137">**Verbindungstyp:** Wählen Sie den VPN-Verbindungstyp in der folgenden Liste von Anbietern aus:</span><span class="sxs-lookup"><span data-stu-id="24b9b-137">**Connection type** - Select the VPN connection type from the following list of vendors:</span></span>
    - <span data-ttu-id="24b9b-138">**Check Point Capsule VPN**</span><span class="sxs-lookup"><span data-stu-id="24b9b-138">**Check Point Capsule VPN**</span></span>
    - <span data-ttu-id="24b9b-139">**Cisco AnyConnect**</span><span class="sxs-lookup"><span data-stu-id="24b9b-139">**Cisco AnyConnect**</span></span>
    - <span data-ttu-id="24b9b-140">**Dell SonicWALL Mobile Connect**</span><span class="sxs-lookup"><span data-stu-id="24b9b-140">**Dell SonicWALL Mobile Connect**</span></span>
    - <span data-ttu-id="24b9b-141">**F5 Edge Client**</span><span class="sxs-lookup"><span data-stu-id="24b9b-141">**F5 Edge Client**</span></span>
    - <span data-ttu-id="24b9b-142">**Pulse Secure**</span><span class="sxs-lookup"><span data-stu-id="24b9b-142">**Pulse Secure**</span></span>

- <span data-ttu-id="24b9b-143">**Getrenntes Tunneln:** Aktivieren Sie diese Einstellung, damit bestimmter Webdatenverkehr die VPN-Verbindung verwenden kann, wenn das VPN aktiv ist, während der verbleibende Datenverkehr das Internet verwendet.</span><span class="sxs-lookup"><span data-stu-id="24b9b-143">**Split tunneling** - Enable to let certain web traffic use the VPN connection when the VPN while other traffic uses the internet.</span></span> <span data-ttu-id="24b9b-144">Deaktivieren Sie diese Einstellung, wenn der gesamte Datenverkehr das VPN verwenden soll, wenn es aktiv ist.</span><span class="sxs-lookup"><span data-stu-id="24b9b-144">Disable this setting if you want all traffic to use the VPN when active.</span></span>
