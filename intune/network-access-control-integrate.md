---
title: Integrieren der Netzwerkzugriffssteuerung mit Intune
titlesuffix: Azure portal
description: Integrieren der Netzwerkzugriffssteuerung (NAC) mit Intune
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 06/23/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: aa7ecff7-8579-4009-8fd6-e17074df67de
ms.reviewer: davidra
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 6d75d996f4166fb2a760d1ccb518ca7a228c1a0d
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2017
---
# <a name="network-access-control-nac-integration-with-intune"></a><span data-ttu-id="edb22-103">Integrieren der Netzwerkzugriffssteuerung (NAC) mit Intune</span><span class="sxs-lookup"><span data-stu-id="edb22-103">Network access control (NAC) integration with Intune</span></span>

<span data-ttu-id="edb22-104">Intune arbeitet mit Partnern der Netzwerkzugriffssteuerung zusammen, um Organisationen beim Schützen von Unternehmensdaten zu helfen, wenn Geräte versuchen, auf lokale Ressourcen zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="edb22-104">Intune integrates with network access control partners to help organizations secure corporate data when devices try to access on-premises resources.</span></span>

## <a name="how-do-intune-and-nac-solutions-help-protect-your-organization-resources"></a><span data-ttu-id="edb22-105">Wie helfen Lösungen von Intune und NAC beim Schutz der Ressourcen Ihrer Organisation?</span><span class="sxs-lookup"><span data-stu-id="edb22-105">How do Intune and NAC solutions help protect your organization resources?</span></span>

<span data-ttu-id="edb22-106">Die Aufgabe von NAC-Lösungen besteht darin, den Registrierungs- und Kompatibilitätsstatus des Geräts mit Intune zu überprüfen, um Entscheidungen bezüglich der Zugriffssteuerung zu treffen.</span><span class="sxs-lookup"><span data-stu-id="edb22-106">NAC solutions are responsible for checking the device enrollment and compliance state with Intune to make access control decisions.</span></span> <span data-ttu-id="edb22-107">Wenn das Gerät nicht registriert ist oder registriert ist, aber nicht den Intune-Gerätekompatibilitätsrichtlinien entspricht, sollte das Gerät für die Registrierung und/oder eine Kompatibilitätsprüfung an Intune weitergeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="edb22-107">If the device is not enrolled or is enrolled and not compliant with Intune device compliance policies, the device should be redirected to Intune for enrollment and/or for a device compliance check.</span></span>

### <a name="example"></a><span data-ttu-id="edb22-108">Beispiel</span><span class="sxs-lookup"><span data-stu-id="edb22-108">Example</span></span>

<span data-ttu-id="edb22-109">Wenn das Gerät registriert und mit Intune kompatibel ist, sollte die NAC-Lösung dem Gerät den Zugriff auf Unternehmensressourcen erlauben.</span><span class="sxs-lookup"><span data-stu-id="edb22-109">If the device is enrolled and compliant with Intune, the NAC solution should allow the device access to corporate resources.</span></span> <span data-ttu-id="edb22-110">Benutzern kann beispielsweise der Zugriff auf das Unternehmens-WLAN oder VPN-Ressourcen gewährt oder verweigert werden.</span><span class="sxs-lookup"><span data-stu-id="edb22-110">For example, users can be allowed or denied access when trying to access corporate Wi-Fi or VPN resources.</span></span>

## <a name="nac-and-conditional-access"></a><span data-ttu-id="edb22-111">NAC und bedingter Zugriff</span><span class="sxs-lookup"><span data-stu-id="edb22-111">NAC and conditional access</span></span>

<span data-ttu-id="edb22-112">NAC nutzt bei Entscheidungen bezüglich der Zugriffssteuerung den bedingten Zugriff.</span><span class="sxs-lookup"><span data-stu-id="edb22-112">NAC works with with conditional access to provide access control decisions.</span></span>

- <span data-ttu-id="edb22-113">Weitere Informationen finden Sie unter [Common ways to use conditional access with Intune (Gängige Möglichkeiten der Verwendung des bedingten Zugriffs in Intune)](conditional-access-intune-common-ways-use.md).</span><span class="sxs-lookup"><span data-stu-id="edb22-113">See [common ways to use conditional access with Intune](conditional-access-intune-common-ways-use.md) for more details.</span></span>

## <a name="how-the-nac-integration-works"></a><span data-ttu-id="edb22-114">Funktionsweise der NAC-Integration</span><span class="sxs-lookup"><span data-stu-id="edb22-114">How the NAC integration works</span></span>

<span data-ttu-id="edb22-115">In dieser Übersicht wird gezeigt, wie die NAC-Integration in Intune funktioniert. Die Schritte 1-3 erläutern den Onboarding-Prozess.</span><span class="sxs-lookup"><span data-stu-id="edb22-115">Here’s an overview on how the NAC integration works when integrated with Intune, the first three steps explain the onboarding process.</span></span> <span data-ttu-id="edb22-116">Nachdem die NAC-Lösung in Intune integriert wurde, beschreiben die Schritte 4-9 den laufenden Betrieb.</span><span class="sxs-lookup"><span data-stu-id="edb22-116">Once the NAC solution is integrated with Intune, steps 4-9 describe the on-going operation.</span></span>

![Wie NAC und Intune zusammenarbeiten](./media/ca-intune-common-ways-2.png)

1.  <span data-ttu-id="edb22-118">Registrieren Sie die Lösung des NAC-Partners mit Azure Active Directory (AAD), und gewähren Sie delegierte Berechtigungen an die Intune-NAC-API.</span><span class="sxs-lookup"><span data-stu-id="edb22-118">Register the NAC partner solution with Azure Active Directory (AAD), and grant delegated permissions to the Intune NAC API.</span></span>

2.  <span data-ttu-id="edb22-119">Konfigurieren Sie die Lösung des NAC-Partners mit den geeigneten Einstellungen, darunter die URL für die Intune-Ermittlung.</span><span class="sxs-lookup"><span data-stu-id="edb22-119">Configure the NAC partner solution with the appropriate settings including the Intune discovery URL.</span></span>

3.  <span data-ttu-id="edb22-120">Konfigurieren Sie die Lösung des NAC-Partners für die Zertifikatauthentifizierung.</span><span class="sxs-lookup"><span data-stu-id="edb22-120">Configure the NAC partner solution for certificate authentication.</span></span>

4.  <span data-ttu-id="edb22-121">Der Benutzer stellt eine Verbindung zum WLAN-Zugriffspunkt her oder fordert eine VPN-Verbindung an.</span><span class="sxs-lookup"><span data-stu-id="edb22-121">User connects to corporate Wi-Fi access point or makes a VPN connection request.</span></span>

5.  <span data-ttu-id="edb22-122">Die Lösung des NAC-Partners leitet die Geräteinformationen an Intune weiter und fragt Intune nach dem Registrierungs- und Kompatibilitätsstatus des Geräts.</span><span class="sxs-lookup"><span data-stu-id="edb22-122">NAC partner solution forwards the device information to Intune, and asks Intune about the device enrollment and compliance state.</span></span>

6.  <span data-ttu-id="edb22-123">Wenn das Gerät nicht kompatibel oder nicht registriert ist, weist die Lösung des NAC-Partners den Benutzer an, das Gerät zu registrieren oder kompatibel zu machen.</span><span class="sxs-lookup"><span data-stu-id="edb22-123">If the device is not compliant or not enrolled, the NAC partner solution instructs the user to enroll or fix the device compliance.</span></span>

7.  <span data-ttu-id="edb22-124">Das Gerät versucht eine erneute Bestätigung seines Kompatibilitäts- und/oder Registrierungsstatus.</span><span class="sxs-lookup"><span data-stu-id="edb22-124">The device attempts to re-verify its compliance and/or the enrollment state.</span></span>

8.  <span data-ttu-id="edb22-125">Wenn das Gerät registriert wurde und kompatibel ist, erhält die Lösung des NAC-Partners von Intune eine Statusmeldung.</span><span class="sxs-lookup"><span data-stu-id="edb22-125">Once the device is enrolled and compliant, NAC partner solution gets the state from Intune.</span></span>

9.  <span data-ttu-id="edb22-126">Die Verbindung konnte erfolgreich hergestellt werden, und das Gerät erhält Zugriff auf Unternehmensressourcen.</span><span class="sxs-lookup"><span data-stu-id="edb22-126">Connection is successfully established which allows the device access to corporate resources.</span></span>

## <a name="next-steps"></a><span data-ttu-id="edb22-127">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="edb22-127">Next steps</span></span>

-   [<span data-ttu-id="edb22-128">Integrieren von Cisco ISE mit Intune</span><span class="sxs-lookup"><span data-stu-id="edb22-128">Integrate Cisco ISE with Intune</span></span>](http://www.cisco.com/c/en/us/td/docs/security/ise/2-1/admin_guide/b_ise_admin_guide_21/b_ise_admin_guide_20_chapter_01000.html)

-   [<span data-ttu-id="edb22-129">Integrieren von Citrix NetScaler mit Intune</span><span class="sxs-lookup"><span data-stu-id="edb22-129">Integrate Citrix NetScaler with Intune</span></span>](http://docs.citrix.com/en-us/netscaler-gateway/12/microsoft-intune-integration/configuring-network-access-control-device-check-for-netscaler-gateway-virtual-server-for-single-factor-authentication-deployment.html)

-   [<span data-ttu-id="edb22-130">Integrieren von HPE Aruba ClearPass mit Intune</span><span class="sxs-lookup"><span data-stu-id="edb22-130">Integrate HP Aruba Clear Pass with Intune</span></span>](https://support.arubanetworks.com/Documentation/tabid/77/DMXModule/512/Command/Core_Download/Default.aspx?EntryId=23757)
