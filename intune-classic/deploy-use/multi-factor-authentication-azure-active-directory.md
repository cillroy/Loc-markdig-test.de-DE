---
title: "Mehrstufige Authentifizierung für Intune-Geräteregistrierungen"
description: "Anfordern der mehrstufigen Authentifizierung in Azure AD für die Geräteregistrierung."
keywords: 
author: arob98
ms.author: angrobe
manager: angerobe
ms.date: 02/17/2017
ms.topic: article
ms.prod: 
ms.service: 
ms.technology: 
ms.assetid: 47abdabd-dcd6-48d8-aade-3f3eefb92ee1
ROBOTS: NOINDEX,NOFOLLOW
ms.custom: intune-classic
ms.openlocfilehash: 940187bf6a7a08132469416a063507f5640b4bd6
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2018
---
# <a name="multi-factor-authentication-for-intune-device-enrollments"></a><span data-ttu-id="341ac-103">Multi-Factor Authentication für Intune-Geräteregistrierungen</span><span class="sxs-lookup"><span data-stu-id="341ac-103">Multi-factor authentication for Intune device enrollments</span></span>

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="341ac-104">Intune integriert die mehrstufige Authentifizierung (MFA) von Azure AD, damit Sie Ihre Unternehmensressourcen über die Geräteregistrierung sichern können.</span><span class="sxs-lookup"><span data-stu-id="341ac-104">Intune integrates Azure AD multi-factor authentication (MFA) for device enrollment to help you secure your corporate resources.</span></span>

<span data-ttu-id="341ac-105">MFA funktioniert, da zwei oder mehr der folgenden Überprüfungsmethoden erforderlich sind:</span><span class="sxs-lookup"><span data-stu-id="341ac-105">MFA works by requiring any two or more of the following verification methods:</span></span> 

- <span data-ttu-id="341ac-106">Etwas, das Sie kennen (normalerweise ein Kennwort oder eine PIN)</span><span class="sxs-lookup"><span data-stu-id="341ac-106">Something you know (typically a password or PIN).</span></span>
- <span data-ttu-id="341ac-107">Etwas, das Sie besitzen (ein vertrauenswürdiges Gerät, das nicht auf einfache Weise dupliziert werden kann, z.B. ein Telefon)</span><span class="sxs-lookup"><span data-stu-id="341ac-107">Something you have (a trusted device that is not easily duplicated, like a phone).</span></span>
- <span data-ttu-id="341ac-108">Etwas, das einzigartig für Sie ist (Biometrie)</span><span class="sxs-lookup"><span data-stu-id="341ac-108">Something you are (biometrics).</span></span>

<span data-ttu-id="341ac-109">MFA wird für Geräte unter iOS, Android, Windows 8.1 oder höher und Windows Phone 8.1 oder höher unterstützt.</span><span class="sxs-lookup"><span data-stu-id="341ac-109">MFA is supported for iOS, Android, Windows 8.1 or later, or Windows Phone 8.1 or later devices.</span></span>

> [!NOTE]
> <span data-ttu-id="341ac-110">In älteren Versionen von Configuration Manager (vor Release 1610) wird in der Configuration Manager-Verwaltungskonsole noch immer die MFA-Einstellung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="341ac-110">In older versions of Configuration Manager (earlier than release 1610), you will still see the MFA setting in the Configuration Manager admin console.</span></span> <span data-ttu-id="341ac-111">MFA kann nicht über die Configuration Manager-Verwaltungskonsole konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="341ac-111">Do not attempt to configure MFA in the Configuration Manager admin console, as it will not work.</span></span> <span data-ttu-id="341ac-112">Konfigurieren Sie MFA wie in diesem Thema beschrieben.</span><span class="sxs-lookup"><span data-stu-id="341ac-112">Configure MFA as described in this topic.</span></span>

### <a name="configure-intune-to-require-multi-factor-authentication-at-device-enrollment"></a><span data-ttu-id="341ac-113">Konfigurieren von Intune für das Anfordern der mehrstufigen Authentifizierung bei der Geräteregistrierung</span><span class="sxs-lookup"><span data-stu-id="341ac-113">Configure Intune to require multi-factor authentication at device enrollment</span></span>
<span data-ttu-id="341ac-114">Befolgen Sie die folgenden Schritte, um MFA anzufordern, wenn ein Gerät registriert wird:</span><span class="sxs-lookup"><span data-stu-id="341ac-114">To require MFA when a device is enrolled, follow these steps:</span></span>

1. <span data-ttu-id="341ac-115">Melden Sie sich mit Ihren Administratoranmeldeinformationen beim [Microsoft Azure-Portal](https://manage.windowsazure.com) an.</span><span class="sxs-lookup"><span data-stu-id="341ac-115">Sign in to your [Microsoft Azure portal](https://manage.windowsazure.com) with your admin credentials.</span></span>
2. <span data-ttu-id="341ac-116">Wählen Sie Ihren Mandanten.</span><span class="sxs-lookup"><span data-stu-id="341ac-116">Choose your tenant.</span></span>
2. <span data-ttu-id="341ac-117">Wählen Sie die Registerkarte **Anwendungen**. Sie sehen eine Liste der Dienste, für die Sie Azure AD-Sicherheitsfeatures konfigurieren können.</span><span class="sxs-lookup"><span data-stu-id="341ac-117">Choose the **applications** tab. You will see a list of services for which you can configure Azure AD security features.</span></span>
3. <span data-ttu-id="341ac-118">Wählen Sie **Microsoft Intune-Registrierung**.</span><span class="sxs-lookup"><span data-stu-id="341ac-118">Choose **Microsoft Intune enrollment**.</span></span>
4. <span data-ttu-id="341ac-119">Wählen Sie **Konfigurieren** aus.</span><span class="sxs-lookup"><span data-stu-id="341ac-119">Choose **Configure**.</span></span> 
5. <span data-ttu-id="341ac-120">Unter **Mehrstufige Authentifizierung und standortbasierte Zugriffsregeln** haben Sie folgende Möglichkeiten:</span><span class="sxs-lookup"><span data-stu-id="341ac-120">Under **multi-factor authentication and location-based access rules** you can:</span></span>
    
    -  <span data-ttu-id="341ac-121">Aktivieren der Zugriffsregeln</span><span class="sxs-lookup"><span data-stu-id="341ac-121">Enable the access rules</span></span>
    -  <span data-ttu-id="341ac-122">Auswählen, ob die Regeln für alle Benutzer oder für bestimmte Azure AD-Sicherheitsgruppen gelten sollen</span><span class="sxs-lookup"><span data-stu-id="341ac-122">Choose whether to apply the rules to all users or to specific Azure AD security groups.</span></span>
    -  <span data-ttu-id="341ac-123">Anfordern der mehrstufigen Authentifizierung für die Registrierung aller Geräte</span><span class="sxs-lookup"><span data-stu-id="341ac-123">Require multi-factor authentication for enrollment of all devices.</span></span>
    -  <span data-ttu-id="341ac-124">Anfordern der mehrstufigen Authentifizierung für die Registrierung, wenn sich das Gerät nicht am Arbeitsplatz befindet</span><span class="sxs-lookup"><span data-stu-id="341ac-124">Require multi-factor authentication for enrollment when the device is not at work.</span></span>
    -  <span data-ttu-id="341ac-125">Wählen Sie **Zugriff auf Unternehmensressourcen blockieren**, um die Registrierung eines Geräts zu verhindern, wenn es nicht mit dem Unternehmensnetzwerk verbunden ist.</span><span class="sxs-lookup"><span data-stu-id="341ac-125">Choose **Block access to corporate resources** to prevent enrollment of a device when it is not connected to the corporate network.</span></span> 
4. <span data-ttu-id="341ac-126">Sie können auch auf den Link klicken, um **Ihre Firmennetzwerkadresse zu definieren oder zu bearbeiten** und die Anforderungen der Geräteregistrierung an die Netzwerkkonnektivität zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="341ac-126">You can also click the link to **define/edit your work network location**, to configure network connectivity requirements for device enrollment.</span></span>

> [!IMPORTANT]
> 
> <span data-ttu-id="341ac-127">Konfigurieren Sie keine **gerätebasierten Zugriffsregeln** für die Microsoft Intune-Registrierung.</span><span class="sxs-lookup"><span data-stu-id="341ac-127">Do not configure **Device based access rules** for Microsoft Intune Enrollment.</span></span>
