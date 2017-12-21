---
title: "Fördern der Akzeptanz durch Endbenutzer mit bedingtem Zugriff"
description: "Dieser Artikel bietet Ihnen Einblick, wie der bedingte Zugriff verwendet werden kann, um die Registrierung in Intune zu fördern."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 06/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c2d7ce3f-fe97-4044-ad9e-25ac8fa301c9
ms.reviewer: dagerrit
ms.suite: ems
ms.openlocfilehash: 7a9c3bef955239ad653a9ca45c55c533be36c5ce
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2017
---
# <a name="drive-end-user-adoption-with-conditional-access"></a><span data-ttu-id="fedaa-103">Fördern der Akzeptanz durch Endbenutzer mit bedingtem Zugriff</span><span class="sxs-lookup"><span data-stu-id="fedaa-103">Drive end-user adoption with conditional access</span></span>

<span data-ttu-id="fedaa-104">Funktionen für bedingten Zugriff wie das Blockieren von E-Mails für nicht registrierte Geräte mit Intune zu aktivieren, kann die Registrierung und Kompatibilität fördern, ist aber keine Voraussetzung für eine erfolgreiche Migration.</span><span class="sxs-lookup"><span data-stu-id="fedaa-104">Enabling conditional access features with Intune, such as blocking email for unenrolled devices, can help drive enrollment and compliance but they are not required for a migration to be successful.</span></span> <span data-ttu-id="fedaa-105">Ihre Ziele bei der Einführung der Migration und die Sicherheitsanforderungen sollten den Erfolg bestimmen.</span><span class="sxs-lookup"><span data-stu-id="fedaa-105">Your migration adoption goals and security requirements should dictate the success.</span></span>

## <a name="migration-campaign-with-conditional-access"></a><span data-ttu-id="fedaa-106">Migrationskampagne mit bedingtem Zugriff</span><span class="sxs-lookup"><span data-stu-id="fedaa-106">Migration campaign with conditional access</span></span>

<span data-ttu-id="fedaa-107">Hier ist ein typischer Ansatz, wie eine Migrationskampagne durch bedingten Zugriff erweitert werden kann:</span><span class="sxs-lookup"><span data-stu-id="fedaa-107">Here is a typical approach to enhancing a migration campaign with conditional access:</span></span>

1.  <span data-ttu-id="fedaa-108">Legen Sie Regeln für bedingten Zugriff fest, der für alle Benutzer erzwungen wird, aber schließen Sie speziell die Benutzer aus, die vom alten MDM-Anbieter migrieren müssen.</span><span class="sxs-lookup"><span data-stu-id="fedaa-108">Set conditional access rules to be enforced for all users but specifically exclude the users who need to migrate from the old MDM provider.</span></span> <span data-ttu-id="fedaa-109">Sie können eine Azure AD-Benutzergruppe mit allen Benutzern erstellen, die vom bedingten Zugriff ausgeschlossen sind.</span><span class="sxs-lookup"><span data-stu-id="fedaa-109">You can create an Azure AD user group with all conditional access excluded users.</span></span>

2.  <span data-ttu-id="fedaa-110">Entfernen Sie die Benutzer aus dieser Gruppe, wenn sie migriert haben.</span><span class="sxs-lookup"><span data-stu-id="fedaa-110">As users migrate, remove them from the conditional access exclusion group.</span></span>

3.  <span data-ttu-id="fedaa-111">Konfigurieren Sie nach dem Abschluss der Migration alle Richtlinien für bedingten Zugriff so, dass sie standardmäßig blockieren, wenn Intune den Zugriff nicht erlaubt.</span><span class="sxs-lookup"><span data-stu-id="fedaa-111">After migration completes, configure all conditional access policies to block by default unless Intune allows access.</span></span>

### <a name="advantages"></a><span data-ttu-id="fedaa-112">Vorteile</span><span class="sxs-lookup"><span data-stu-id="fedaa-112">Advantages</span></span>

-   <span data-ttu-id="fedaa-113">Bietet Zugriffsteuerung für neue Benutzerkonten oder Benutzerkonten, die von der vorherigen Lösung nicht verwaltet wurden.</span><span class="sxs-lookup"><span data-stu-id="fedaa-113">Provides access control for new user accounts or user account who were not managed by the previous solution.</span></span>

-   <span data-ttu-id="fedaa-114">Bietet Benutzern der vorherigen Lösung einen Toleranzzeitraum für die Migration.</span><span class="sxs-lookup"><span data-stu-id="fedaa-114">Provides grace period for users of previous solution to migration.</span></span>

-   <span data-ttu-id="fedaa-115">Produktivitätsverluste werden minimiert</span><span class="sxs-lookup"><span data-stu-id="fedaa-115">Minimizes loss of productivity</span></span>

### <a name="disadvantages"></a><span data-ttu-id="fedaa-116">Nachteile</span><span class="sxs-lookup"><span data-stu-id="fedaa-116">Disadvantages</span></span>

-   <span data-ttu-id="fedaa-117">Benutzer der vorherigen Lösung können möglicherweise über nicht verwaltete Geräte auf Ressourcen zugreifen, bis der bedingte Zugriff für diese Benutzer aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="fedaa-117">Users of previous solution could potentially access resources using unmanaged devices until conditional access is enabled for those users.</span></span>


<span data-ttu-id="fedaa-118">Dies ist ein Ansatz unter vielen.</span><span class="sxs-lookup"><span data-stu-id="fedaa-118">This is one approach among many.</span></span> <span data-ttu-id="fedaa-119">Sie können auch einen einfacheren Prozess auswählen, der jeglichen bedingten Zugriff aufschiebt, bis in jeder Phase die Registrierung angewiesen wurde, oder einen strengeren Prozess, der bedingten Zugriff von Anfang an erzwingt und für jeden Zugriff vollständige Kompatibilität erfordert.</span><span class="sxs-lookup"><span data-stu-id="fedaa-119">You may choose a simpler process that defers all conditional access until after every phase has been instructed to enroll, or a stricter process that enforces conditional access from the very beginning and requires full compliance for all access.</span></span>

-   <span data-ttu-id="fedaa-120">Weitere Informationen zum [bedingten Zugriff](conditional-access.md).</span><span class="sxs-lookup"><span data-stu-id="fedaa-120">Learn more about [conditional access](conditional-access.md).</span></span>

## <a name="task-list-for-conditional-access"></a><span data-ttu-id="fedaa-121">Aufgabenliste für bedingten Zugriff</span><span class="sxs-lookup"><span data-stu-id="fedaa-121">Task list for conditional access</span></span>

### <a name="task-1-decide-how-you-are-going-to-implement-conditional-access"></a><span data-ttu-id="fedaa-122">Aufgabe 1: Entscheiden Sie, wie Sie den bedingten Zugriff implementieren möchten.</span><span class="sxs-lookup"><span data-stu-id="fedaa-122">Task 1: Decide how you are going to implement conditional access</span></span>

<span data-ttu-id="fedaa-123">[Gängige Möglichkeiten der Nutzung des bedingten Zugriffs](conditional-access-intune-common-ways-use.md)</span><span class="sxs-lookup"><span data-stu-id="fedaa-123">[Common ways to use conditional access](conditional-access-intune-common-ways-use.md).</span></span>

### <a name="task-2-set-up-intune-conditional-access"></a><span data-ttu-id="fedaa-124">Aufgabe 2: Richten Sie den bedingten Zugriff für Intune ein.</span><span class="sxs-lookup"><span data-stu-id="fedaa-124">Task 2: Set up Intune conditional access</span></span>

<span data-ttu-id="fedaa-125">Wählen Sie eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="fedaa-125">Choose one of the following options:</span></span>

-   [<span data-ttu-id="fedaa-126">Konfigurieren des bedingten Zugriffs in Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="fedaa-126">Configure conditional access in Azure Active Directory</span></span>](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal)

-   [<span data-ttu-id="fedaa-127">Installieren des lokalen Exchange Connectors für Intune</span><span class="sxs-lookup"><span data-stu-id="fedaa-127">Install on-premises Exchange connector with Intune</span></span>](exchange-connector-install.md)

-   [<span data-ttu-id="fedaa-128">Einrichten von App-basierten bedingten Zugriffsrichtlinien für Exchange Online</span><span class="sxs-lookup"><span data-stu-id="fedaa-128">Set up app-based conditional access policies for Exchange Online</span></span>](app-based-conditional-access-intune-create.md)

-   [<span data-ttu-id="fedaa-129">Einrichten von App-basierten bedingten Zugriffsrichtlinien für SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="fedaa-129">Set up app-based conditional access policies for SharePoint Online</span></span>](app-based-conditional-access-intune-create.md)

-   [<span data-ttu-id="fedaa-130">Blockieren von Apps, die keine moderne Authentifizierung verwenden (ADAL)</span><span class="sxs-lookup"><span data-stu-id="fedaa-130">Block apps that do not use modern authentication (ADAL)</span></span>](app-modern-authentication-block.md)

## <a name="next-steps"></a><span data-ttu-id="fedaa-131">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="fedaa-131">Next steps</span></span>

<span data-ttu-id="fedaa-132">Erfahren Sie mehr über den [typischen Migrationszyklus](migration-guide-cycle.md).</span><span class="sxs-lookup"><span data-stu-id="fedaa-132">Learn about the [typical migration cycle](migration-guide-cycle.md).</span></span>
