---
title: Grundlegende Einrichtung von Intune
description: "Dieser Artikel enthält die notwendigen Schritte zum Einrichten von Microsoft Intune."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 06/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 60cfa440-0723-4ea0-bacf-3c5d26f9a1d3
ms.reviewer: dagerrit
ms.suite: ems
ms.openlocfilehash: 9ea12f3707b830f0e3426526a7ae91d176d6e809
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2017
---
# <a name="basic-setup"></a><span data-ttu-id="f6ac0-103">Grundlegende Einrichtung</span><span class="sxs-lookup"><span data-stu-id="f6ac0-103">Basic setup</span></span>

<span data-ttu-id="f6ac0-104">Nachdem Sie Ihre Umgebung analysiert haben, können Sie mit dem Einrichten von Intune beginnen.</span><span class="sxs-lookup"><span data-stu-id="f6ac0-104">After you assess your environment, it’s time to set up Intune.</span></span>

## <a name="external-dependencies-for-an-intune-deployment"></a><span data-ttu-id="f6ac0-105">Externe Abhängigkeiten für eine Bereitstellung mit Intune</span><span class="sxs-lookup"><span data-stu-id="f6ac0-105">External dependencies for an Intune deployment</span></span>

### <a name="identity"></a><span data-ttu-id="f6ac0-106">Identität</span><span class="sxs-lookup"><span data-stu-id="f6ac0-106">Identity</span></span>

<span data-ttu-id="f6ac0-107">Intune erfordert Azure Active Directory (AAD) als Identitäts- und Benutzergruppierungsanbieter.</span><span class="sxs-lookup"><span data-stu-id="f6ac0-107">Intune requires Azure Active Directory (AAD) as the identity and user grouping provider.</span></span> <span data-ttu-id="f6ac0-108">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="f6ac0-108">Learn more about:</span></span>

-  [<span data-ttu-id="f6ac0-109">Identitätsanforderungen</span><span class="sxs-lookup"><span data-stu-id="f6ac0-109">Identity requirements</span></span>](https://docs.microsoft.com/active-directory/active-directory-hybrid-identity-design-considerations-overview#design-considerations-overview)

-   [<span data-ttu-id="f6ac0-110">Anforderungen für die Verzeichnissynchronisierung</span><span class="sxs-lookup"><span data-stu-id="f6ac0-110">Directory synchronization requirements</span></span>](https://docs.microsoft.com/active-directory/active-directory-hybrid-identity-design-considerations-directory-sync-requirements)

-   [<span data-ttu-id="f6ac0-111">Anforderungen für mehrstufige Authentifizierung (Multi-Factor Authentication, MFA)</span><span class="sxs-lookup"><span data-stu-id="f6ac0-111">Multi-factor authentication (MFA) requirements</span></span>](https://docs.microsoft.com/active-directory/active-directory-hybrid-identity-design-considerations-multifactor-auth-requirements)

-   [<span data-ttu-id="f6ac0-112">Planen von Benutzer- und Gerätegruppen</span><span class="sxs-lookup"><span data-stu-id="f6ac0-112">Planning your user and device groups</span></span>](users-add.md)

-   [<span data-ttu-id="f6ac0-113">Erstellen von Benutzer- und Gerätegruppen</span><span class="sxs-lookup"><span data-stu-id="f6ac0-113">How to create user and device groups</span></span>](groups-get-started.md)

<span data-ttu-id="f6ac0-114">Wenn in Ihrer Organisation bereits Office 365 verwendet wird, muss Intune dieselbe Azure Active Directory-Umgebung verwenden.</span><span class="sxs-lookup"><span data-stu-id="f6ac0-114">If your organization is already using Office 365, Intune must use the same Azure Active Directory environment.</span></span>

### <a name="pki-optional"></a><span data-ttu-id="f6ac0-115">PKI (optional)</span><span class="sxs-lookup"><span data-stu-id="f6ac0-115">PKI (optional)</span></span>

<span data-ttu-id="f6ac0-116">Wenn Sie Zertifikat-basierte Authentifizierung für VPN-, WLAN- oder E-Mail-Profile von Intune zu verwenden möchten, müssen Sie sicherstellen, dass eine unterstützte [PKI-Infrastruktur vorhanden ist](certificates-configure.md), in der Zertifikatprofile erstellt und bereitgestellt werden können.</span><span class="sxs-lookup"><span data-stu-id="f6ac0-116">If you're planning to use certificate-based authentication for VPN, Wi-Fi, or e-mail profiles with Intune, you’ll need to make sure that you have a supported [PKI infrastructure in place](certificates-configure.md), ready to create and deploy certificate profiles.</span></span> <span data-ttu-id="f6ac0-117">Weitere Informationen zum Konfigurieren von Zertifikaten in Intune:</span><span class="sxs-lookup"><span data-stu-id="f6ac0-117">Learn more about configuring certificates in Intune:</span></span>

-   [<span data-ttu-id="f6ac0-118">Konfigurieren der Zertifikatinfrastruktur für SCEP</span><span class="sxs-lookup"><span data-stu-id="f6ac0-118">How to configure the certificate infrastructure for SCEP</span></span>](/intune/certificates-scep-configure)

-   <span data-ttu-id="f6ac0-119">[Konfigurieren der Zertifikatinfrastruktur für PFX](/intune/certficates-pfx-configure)</span><span class="sxs-lookup"><span data-stu-id="f6ac0-119">[How to configure the certificate infrastructure for PFX](/intune/certficates-pfx-configure).</span></span>


## <a name="task-list-for-an-intune-setup"></a><span data-ttu-id="f6ac0-120">Aufgabenliste für die Einrichtung von Intune</span><span class="sxs-lookup"><span data-stu-id="f6ac0-120">Task list for an Intune setup</span></span>

### <a name="task-1-intune-subscription"></a><span data-ttu-id="f6ac0-121">Aufgabe 1: Intune-Abonnement</span><span class="sxs-lookup"><span data-stu-id="f6ac0-121">Task 1: Intune subscription</span></span>

<span data-ttu-id="f6ac0-122">Bevor Sie zu Intune migrieren können, brauchen Sie ein Intune-Abonnement.</span><span class="sxs-lookup"><span data-stu-id="f6ac0-122">Before you can migrate to Intune, you first need an Intune subscription.</span></span>

-   <span data-ttu-id="f6ac0-123">Suchen Sie [diese Seite](https://portal.office.com/Signup/Signup.aspx?OfferId=40BE278A-DFD1-470a-9EF7-9F2596EA7FF9&dl=INTUNE_A&ali=1#0) auf, um Informationen zu den folgenden Vorgängen zu erhalten:</span><span class="sxs-lookup"><span data-stu-id="f6ac0-123">You can visit [this page](https://portal.office.com/Signup/Signup.aspx?OfferId=40BE278A-DFD1-470a-9EF7-9F2596EA7FF9&dl=INTUNE_A&ali=1#0), which gives you instructions on how to:</span></span>

    -   <span data-ttu-id="f6ac0-124">Erstellen eines neuen Intune-Abonnements, das mit einem neuen AAD-Mandanten verknüpft ist</span><span class="sxs-lookup"><span data-stu-id="f6ac0-124">Create a new Intune subscription linked to a new AAD tenant.</span></span>

    -   <span data-ttu-id="f6ac0-125">Verknüpfen eines Intune-Abonnements, indem Sie sich als bereits vorhandener AAD-Mandant anmelden</span><span class="sxs-lookup"><span data-stu-id="f6ac0-125">Link the Intune subscription by signing into an existing AAD tenant.</span></span>

### <a name="task-2-assign-intune-user-licenses"></a><span data-ttu-id="f6ac0-126">Aufgabe 2: Zuweisen von Intune-Benutzerlizenzen</span><span class="sxs-lookup"><span data-stu-id="f6ac0-126">Task 2: Assign Intune user licenses</span></span>

-   <span data-ttu-id="f6ac0-127">Erfahren Sie, wie Sie [Intune-Benutzerlizenzen zuweisen](licenses-assign.md) können.</span><span class="sxs-lookup"><span data-stu-id="f6ac0-127">Learn [how to assign Intune user licenses](licenses-assign.md).</span></span>

-   <span data-ttu-id="f6ac0-128">Wenn Sie bereits einen neuen AAD-Mandanten erstellt haben, erfahren Sie, wie Sie [neue Benutzer erstellen oder Benutzer aus Ihrem lokalen Active Directory (AD) synchronisieren](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect) können.</span><span class="sxs-lookup"><span data-stu-id="f6ac0-128">If you have created a new Azure Active Directory tenant, learn [how to create new users or sync user from your on-premises Active Directory (AD).](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect)</span></span>

### <a name="task-3-set-your-mdm-authority-to-intune"></a><span data-ttu-id="f6ac0-129">Aufgabe 3: Stellen Sie die MDM-Autorität auf Intune um</span><span class="sxs-lookup"><span data-stu-id="f6ac0-129">Task 3: Set your MDM authority to Intune</span></span>

<span data-ttu-id="f6ac0-130">Intune kann über das Azure-Portal oder über die Konsole von Configuration Manager Current Branch verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="f6ac0-130">Intune can be managed through the Azure portal or the Configuration Manager Current Branch console.</span></span> <span data-ttu-id="f6ac0-131">Wenn Sie Intune nicht in eine Bereitstellung mit Configuration Manager Current Branch integrieren müssen, wird empfohlen, Intune über das [Azure-Portal](https://portal.azure.com) zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="f6ac0-131">Unless you need to integrate Intune with a Configuration Manager Current Branch deployment, we recommend that you manage Intune from the [Azure portal](https://portal.azure.com).</span></span>

<span data-ttu-id="f6ac0-132">Legen Sie Ihre MDM-Autorität auf **Intune** fest, um das Azure-Portal für Intune zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="f6ac0-132">Set your MDM authority to **Intune** to enable the Intune Azure portal.</span></span> <span data-ttu-id="f6ac0-133">Wenn Sie eine andere MDM-Autorität verwenden, ist es Intune möglich, die MDM-Verwaltung auf andere Verwaltungskonsolen von Microsoft zu übertragen.</span><span class="sxs-lookup"><span data-stu-id="f6ac0-133">Using a different MDM authority allows Intune to transfer MDM management to alternate Microsoft management consoles.</span></span> <span data-ttu-id="f6ac0-134">Das geschieht jedoch selten.</span><span class="sxs-lookup"><span data-stu-id="f6ac0-134">These cases are uncommon.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f6ac0-135">Wenn Sie Ihr MDM zum ersten Mal an Intune übertragen, sollten Sie die MDM-Autorität auf Intune festlegen.</span><span class="sxs-lookup"><span data-stu-id="f6ac0-135">If you are transferring your mobile device management to Intune for the first time, you should set the MDM authority to Intune.</span></span>

<span data-ttu-id="f6ac0-136">Erfahren Sie, wie Sie die [Autorität für die Verwaltung mobiler Geräte einrichten](mdm-authority-set.md) können.</span><span class="sxs-lookup"><span data-stu-id="f6ac0-136">Learn [how to set the mobile management authority](mdm-authority-set.md).</span></span>

## <a name="next-step"></a><span data-ttu-id="f6ac0-137">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="f6ac0-137">Next step</span></span>

<span data-ttu-id="f6ac0-138">Konfigurieren Sie [Richtlinien für die Verwaltung von Apps und Geräten](migration-guide-configure-policies.md).</span><span class="sxs-lookup"><span data-stu-id="f6ac0-138">Configure [device and app management policies](migration-guide-configure-policies.md).</span></span>
