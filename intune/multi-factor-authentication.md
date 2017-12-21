---
title: "Mehrstufige Authentifizierung für Intune-Geräteregistrierungen"
titlesuffix: Azure portal
description: "Anfordern der mehrstufigen Authentifizierung in Azure AD für die Geräteregistrierung."
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 10/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 94280c73-c05c-4e72-b0dd-a7cb997782f9
ROBOTS: 
ms.custom: intune-azure
ms.openlocfilehash: a3aabe77257fd7e6964dd7bd83035c8a491a58b4
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2017
---
# <a name="multi-factor-authentication-for-intune-device-enrollments"></a><span data-ttu-id="3c0c9-103">Multi-Factor Authentication für Intune-Geräteregistrierungen</span><span class="sxs-lookup"><span data-stu-id="3c0c9-103">Multi-factor authentication for Intune device enrollments</span></span>

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="3c0c9-104">Intune kann die mehrstufige Authentifizierung (MFA) von Azure AD für die Geräteregistrierung verwenden, damit Sie Ihre Unternehmensressourcen sichern können.</span><span class="sxs-lookup"><span data-stu-id="3c0c9-104">Intune can use Azure Active Directory (AD) multi-factor authentication (MFA) for device enrollment to help you secure your corporate resources.</span></span>

<span data-ttu-id="3c0c9-105">MFA funktioniert, da zwei oder mehr der folgenden Überprüfungsmethoden erforderlich sind:</span><span class="sxs-lookup"><span data-stu-id="3c0c9-105">MFA works by requiring any two or more of the following verification methods:</span></span>

- <span data-ttu-id="3c0c9-106">Etwas, das Sie kennen (normalerweise ein Kennwort oder eine PIN)</span><span class="sxs-lookup"><span data-stu-id="3c0c9-106">Something you know (typically a password or PIN).</span></span>
- <span data-ttu-id="3c0c9-107">Etwas, das Sie besitzen (ein vertrauenswürdiges Gerät, das nicht auf einfache Weise dupliziert werden kann, z.B. ein Telefon)</span><span class="sxs-lookup"><span data-stu-id="3c0c9-107">Something you have (a trusted device that is not easily duplicated, like a phone).</span></span>
- <span data-ttu-id="3c0c9-108">Etwas Biometrisches (z.B. ein Fingerabdruck)</span><span class="sxs-lookup"><span data-stu-id="3c0c9-108">Something you are (biometrics, like a fingerprint).</span></span>

<span data-ttu-id="3c0c9-109">MFA wird für iOS-, Android-, Windows 8.1-Geräte oder höher und Windows Phone 8.1-Geräte oder mobile Windows 10-Geräte oder höher unterstützt.</span><span class="sxs-lookup"><span data-stu-id="3c0c9-109">MFA is supported for iOS, Android, Windows 8.1 or later, Windows Phone 8.1, or Windows 10 Mobile or later devices.</span></span>

<span data-ttu-id="3c0c9-110">Wenn Sie MFA aktivieren, müssen Benutzer zwei Formen von Anmeldeinformationen angeben, um ein Gerät zu registrieren.</span><span class="sxs-lookup"><span data-stu-id="3c0c9-110">When you enable MFA, end users must supply two forms of credentials to enroll a device.</span></span>

## <a name="configure-intune-to-require-multi-factor-authentication-at-device-enrollment"></a><span data-ttu-id="3c0c9-111">Konfigurieren von Intune für das Anfordern der mehrstufigen Authentifizierung bei der Geräteregistrierung</span><span class="sxs-lookup"><span data-stu-id="3c0c9-111">Configure Intune to require multi-factor authentication at device enrollment</span></span>

<span data-ttu-id="3c0c9-112">Befolgen Sie die folgenden Schritte, um MFA anzufordern, wenn ein Gerät registriert wird:</span><span class="sxs-lookup"><span data-stu-id="3c0c9-112">To require MFA when a device is enrolled, follow these steps:</span></span>

>[!Important]
><span data-ttu-id="3c0c9-113">Konfigurieren Sie keine **gerätebasierten Zugriffsregeln** für die Microsoft Intune-Registrierung.</span><span class="sxs-lookup"><span data-stu-id="3c0c9-113">Do not configure **Device based access rules** for Microsoft Intune enrollment.</span></span>

1. <span data-ttu-id="3c0c9-114">Melden Sie sich mit Ihren Anmeldeinformationen beim [Microsoft Azure-Portal](https://portal.azure.com) an.</span><span class="sxs-lookup"><span data-stu-id="3c0c9-114">Sign in to your [Microsoft Azure portal](https://portal.azure.com) with your credentials.</span></span>
2. <span data-ttu-id="3c0c9-115">Wählen Sie im Portal **Azure Active Directory** aus.</span><span class="sxs-lookup"><span data-stu-id="3c0c9-115">In the portal, choose **Azure Active Directory**.</span></span>
2. <span data-ttu-id="3c0c9-116">Wählen Sie in **Azure Active Directory** **Verwalten** > **Unternehmensanwendungen** aus.</span><span class="sxs-lookup"><span data-stu-id="3c0c9-116">In **Azure Active Directory**, choose **Manage** > **Enterprise applications**.</span></span>
3. <span data-ttu-id="3c0c9-117">Wählen Sie unter **Unternehmensanwendungen** die Optionen **Verwalten** > **Alle Anwendungen** aus.</span><span class="sxs-lookup"><span data-stu-id="3c0c9-117">In **Enterprise applications**, choose **Manage** > **All applications**.</span></span> <span data-ttu-id="3c0c9-118">Daraufhin sehen Sie eine Liste aller Azure-Apps, die Sie verwalten.</span><span class="sxs-lookup"><span data-stu-id="3c0c9-118">You see a list of all Azure apps that you manage.</span></span>
3. <span data-ttu-id="3c0c9-119">Wählen Sie aus dieser Liste **Microsoft Intune enrollment** (Microsoft Intune-Registrierung) aus.</span><span class="sxs-lookup"><span data-stu-id="3c0c9-119">From the list, choose **Microsoft Intune enrollment**.</span></span>
4. <span data-ttu-id="3c0c9-120">Wählen Sie unter **Microsoft Intune-Registrierung** die Optionen **Sicherheit** > **Bedingter Zugriff** aus.</span><span class="sxs-lookup"><span data-stu-id="3c0c9-120">In **Microsoft Intune Enrollment**, choose **Security** > **Conditional access**.</span></span>
5. <span data-ttu-id="3c0c9-121">Wählen Sie **Neue Richtlinie** aus.</span><span class="sxs-lookup"><span data-stu-id="3c0c9-121">Choose **New policy**.</span></span>
6. <span data-ttu-id="3c0c9-122">Geben Sie unter **Neue Richtlinie** einen beschreibenden Namen für die Richtlinie ein.</span><span class="sxs-lookup"><span data-stu-id="3c0c9-122">In **New** policy, type a descriptive name for the policy.</span></span>
7. <span data-ttu-id="3c0c9-123">Wählen Sie im Abschnitt **Zuweisungen** die Option **Benutzer und Gruppen** aus.</span><span class="sxs-lookup"><span data-stu-id="3c0c9-123">In the **Assignments** section, choose **Users and groups**.</span></span>
8. <span data-ttu-id="3c0c9-124">Wählen Sie unter **Benutzer und Gruppen** die Benutzer oder Gruppen aus, die diese Richtlinie empfangen sollen, und klicken Sie dann auf **Fertig**.</span><span class="sxs-lookup"><span data-stu-id="3c0c9-124">In **Users and groups**, choose the users or groups that will receive this policy, then choose **Done**.</span></span>
9. <span data-ttu-id="3c0c9-125">Wählen Sie im Abschnitt **Zuweisungen** die Option **Cloud-Apps** aus.</span><span class="sxs-lookup"><span data-stu-id="3c0c9-125">In the **Assignments** section, choose **Cloud apps**.</span></span>
10. <span data-ttu-id="3c0c9-126">Wählen Sie auf der Registerkarte **Einbeziehen** von **Cloud-Apps** die Option **Apps auswählen** aus, klicken Sie dann auf **Auswählen** > **Microsoft Intune-Registrierung**, und klicken Sie dann auf **Fertig**.</span><span class="sxs-lookup"><span data-stu-id="3c0c9-126">On the **Include** tab of **Cloud apps**, choose **Select apps**, then choose **Select** > **Microsoft Intune Enrollment**, and then choose **Done**.</span></span>
11. <span data-ttu-id="3c0c9-127">Wählen Sie im Abschnitt **Zuweisungen** die Option **Bedingungen** aus.</span><span class="sxs-lookup"><span data-stu-id="3c0c9-127">In the **Assignments** section, choose **Conditions**.</span></span>
12. <span data-ttu-id="3c0c9-128">Sie müssen unter **Bedingungen** keine Einstellungen für MFA konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="3c0c9-128">In **Conditions**, you do not need to configure any settings for MFA.</span></span>
13. <span data-ttu-id="3c0c9-129">Wählen Sie im Abschnitt **Zugriffssteuerung** die Option **Erteilen** aus.</span><span class="sxs-lookup"><span data-stu-id="3c0c9-129">In the **Access controls** section, choose **Grant**.</span></span>
14. <span data-ttu-id="3c0c9-130">Wählen Sie unter **Erteilen** die Option **Zugriff gewähren** aus, und wählen Sie dann **Mehrstufige Authentifizierung anfordern** aus.</span><span class="sxs-lookup"><span data-stu-id="3c0c9-130">In **Grant**, choose **Grant access**, and then select **Require multi-factor authentication**.</span></span>
    <span data-ttu-id="3c0c9-131">Wählen Sie nicht **Markieren des Geräts als kompatibel erforderlich** aus, da ein Gerät vor der Registrierung nicht auf Kompatibilität geprüft werden kann.</span><span class="sxs-lookup"><span data-stu-id="3c0c9-131">Do not select **Require device to be marked as compliant** because a device cannot be evaluated for compliance until it is enrolled.</span></span>
15. <span data-ttu-id="3c0c9-132">Klicken Sie auf **Auswählen**.</span><span class="sxs-lookup"><span data-stu-id="3c0c9-132">Choose **Select**.</span></span>
16. <span data-ttu-id="3c0c9-133">Wählen Sie unter **Neue Richtlinie** die Optionen **Richtlinie aktivieren** > **An** aus, und klicken Sie dann auf **Erstellen**.</span><span class="sxs-lookup"><span data-stu-id="3c0c9-133">In **New policy**, choose **Enable policy** > **On**, and then choose **Create**.</span></span>



## <a name="next-steps"></a><span data-ttu-id="3c0c9-134">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="3c0c9-134">Next steps</span></span>

<span data-ttu-id="3c0c9-135">Wenn Benutzer ihre Geräte registrieren, müssen Sie sich jetzt mit einer zweiten Identifikationsart, z.B. mit einer PIN, einer Telefonnummer oder mit biometrischen Daten authentifizieren.</span><span class="sxs-lookup"><span data-stu-id="3c0c9-135">When end users enroll their device, they now must authenticate with a second form of identification, like a PIN, a phone, or biometrics.</span></span>
