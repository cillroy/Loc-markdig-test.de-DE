---
title: "Schützen von E-Mail-Szenarien"
description: "Einige Beispielszenarien und wie sie mit bedingtem Zugriff implementiert werden könnten."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 01/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 454eab79-b620-42c9-b8e6-fada6e719fcd
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: chrisgre
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: d694204439da004d5860e50fe12625dac03e883a
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2017
---
# <a name="protect-access-to-email-with-microsoft-intune-example-scenarios"></a><span data-ttu-id="c5e59-103">Schützen des E-Mail-Zugriffs mit Microsoft Intune: Beispielszenarios</span><span class="sxs-lookup"><span data-stu-id="c5e59-103">Protect access to email with Microsoft Intune: Example scenarios</span></span>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

## <a name="scenario-1-block-users-from-using-noncompliant-devices-to-access-exchange-online"></a><span data-ttu-id="c5e59-104">Szenario 1: Blockieren des Zugriffs auf Exchange Online durch Benutzer nicht kompatibler Geräte</span><span class="sxs-lookup"><span data-stu-id="c5e59-104">Scenario 1: Block users from using noncompliant devices to access Exchange Online</span></span>
### <a name="scenario-requirements"></a><span data-ttu-id="c5e59-105">Anforderungen für das Szenario</span><span class="sxs-lookup"><span data-stu-id="c5e59-105">Scenario requirements</span></span>
- <span data-ttu-id="c5e59-106">Der Zugriff auf Exchange Online muss für alle Benutzer in der Azure Active Directory-Sicherheitsgruppe **Accounting** blockiert werden, wenn das verwendete Gerät einer von Ihnen bereitgestellten Kompatibilitätsrichtlinie nicht entspricht.</span><span class="sxs-lookup"><span data-stu-id="c5e59-106">All users in the **Accounting** Azure Active Directory security group must be blocked from accessing Exchange Online if their device is not compliant with a compliance policy that you deployed.</span></span>
- <span data-ttu-id="c5e59-107">Wenn in dieser Gruppe Benutzer vorhanden sind, deren Geräte von Intune nicht unterstützt werden, muss der Zugriff auf Exchange Online über diese Geräte blockiert werden.</span><span class="sxs-lookup"><span data-stu-id="c5e59-107">If any users exist in this group whose devices are not supported by Intune, they must be blocked from accessing Exchange Online on that device.</span></span>
- <span data-ttu-id="c5e59-108">Benutzer in der Azure Active Directory-Sicherheitsgruppe **Finance** müssen von der Richtlinie ausgenommen werden, auch wenn sie sich ebenfalls in der Sicherheitsgruppe **Accounting** befinden.</span><span class="sxs-lookup"><span data-stu-id="c5e59-108">Users in the **Finance** Azure Active Directory security group must be exempt from the policy, even if they're also in the **Accounting** security group.</span></span>

<span data-ttu-id="c5e59-109">Um dies zu erreichen, konfigurieren Sie eine Richtlinie für bedingten Zugriff für Exchange Online mit folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="c5e59-109">To accomplish this, configure a conditional access policy for Exchange Online with the following settings:</span></span>

- <span data-ttu-id="c5e59-110">Wählen Sie **Richtlinie für bedingten Zugriff aktivieren** aus.</span><span class="sxs-lookup"><span data-stu-id="c5e59-110">Choose **Enable conditional access policy**.</span></span>

- <span data-ttu-id="c5e59-111">Wählen Sie die Plattformen aus, auf denen Sie Zugriff über Apps mit moderner Authentifizierung zulassen möchten.</span><span class="sxs-lookup"><span data-stu-id="c5e59-111">Choose the platforms that you want to allow access from apps with modern authentication.</span></span>
- <span data-ttu-id="c5e59-112">Wählen Sie für Exchange ActiveSync-Apps **Nicht kompatible Geräte auf Plattformen blockieren, die von Microsoft Intune unterstützt werden** und **Alle weiteren Geräte auf Plattformen blockieren, die nicht von Microsoft Intune unterstützt werden**.</span><span class="sxs-lookup"><span data-stu-id="c5e59-112">For Exchange ActiveSync apps, choose **Block noncompliant devices on platforms supported by Microsoft Intune** and **Block all other devices on platforms not supported by Microsoft Intune.**</span></span>
-   <span data-ttu-id="c5e59-113">Wählen Sie im Abschnitt **Zielgruppe** unter **Ausgewählte Sicherheitsgruppen** die Benutzergruppe **Accounting** aus.</span><span class="sxs-lookup"><span data-stu-id="c5e59-113">In the **Targeted group** section, under **Selected security groups**, choose the **Accounting** user group.</span></span>

-   <span data-ttu-id="c5e59-114">Wählen Sie im Abschnitt **Ausgenommen Gruppe** unter **Ausgewählte Sicherheitsgruppen** die Benutzergruppe **Finance** aus.</span><span class="sxs-lookup"><span data-stu-id="c5e59-114">In the **Exempted group** section, under **Selected security groups**, choose the **Finance** user group.</span></span>


<span data-ttu-id="c5e59-115">Der folgende Ablauf wird im Szenario verwendet, um zu entscheiden, welche Geräte auf Exchange Online zugreifen können:</span><span class="sxs-lookup"><span data-stu-id="c5e59-115">The following flow is used in the scenario to decide which devices can access Exchange Online:</span></span>

![Ablauf für Gerätezugriff](./media/ConditionalAccess8-5.png)

## <a name="scenario-2-all-ios-devices-that-access-exchange-on-premises-must-be-managed-by-intune"></a><span data-ttu-id="c5e59-117">Szenario 2: Alle iOS-Geräte, die auf lokales Exchange zugreifen, müssen von Intune verwaltet werden</span><span class="sxs-lookup"><span data-stu-id="c5e59-117">Scenario 2: All iOS devices that access Exchange on-premises must be managed by Intune</span></span>
### <a name="scenario-requirements"></a><span data-ttu-id="c5e59-118">Anforderungen für das Szenario</span><span class="sxs-lookup"><span data-stu-id="c5e59-118">Scenario requirements</span></span>
- <span data-ttu-id="c5e59-119">Nur Geräten, auf denen iOS ausgeführt wird, sollte Zugriff auf lokales Exchange gewährt werden.</span><span class="sxs-lookup"><span data-stu-id="c5e59-119">Only devices that run iOS should be allowed access to Exchange on-premises.</span></span>
- <span data-ttu-id="c5e59-120">Die Geräte müssen auch bei Intune registriert sein und die Regeln der Kompatibilitätsrichtlinie erfüllen, bevor sie für den Zugriff auf Exchange verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="c5e59-120">The devices must also be enrolled in Intune and meet the compliance policy rules before they can be used to access Exchange.</span></span>

<span data-ttu-id="c5e59-121">Um dies zu erreichen, konfigurieren Sie die folgende Richtlinie für bedingten Zugriff für lokales Exchange mit folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="c5e59-121">To accomplish this, configure the following conditional access policy for Exchange on-premises with the following settings:</span></span>

-   <span data-ttu-id="c5e59-122">Wählen Sie die Option **Zugriff auf lokales Exchange von E-Mail-Apps blockieren, wenn das Gerät nicht kompatibel oder nicht bei Microsoft Intune registriert ist**.</span><span class="sxs-lookup"><span data-stu-id="c5e59-122">Choose the option **Block email apps from accessing Exchange on-premises if the device is noncompliant or not enrolled in Microsoft Intune**.</span></span> <span data-ttu-id="c5e59-123">Wenn Sie diese Option auswählen, aktivieren Sie die Richtlinie für bedingten Zugriff, die erfordert, dass alle Geräte bei Microsoft Intune registriert sein und die Regeln der Kompatibilitätsrichtlinie erfüllen müssen, bevor sie auf Exchange zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="c5e59-123">By choosing this option, you enable the conditional access policy, which requires that all devices must be enrolled in Microsoft Intune and meet the compliancy policy rules before they can access Exchange.</span></span>

-   <span data-ttu-id="c5e59-124">Erstellen Sie für die erweiterten Exchange ActiveSync-Einstellungen Folgendes:</span><span class="sxs-lookup"><span data-stu-id="c5e59-124">For advanced Exchange Active Sync settings, create:</span></span>

  -   <span data-ttu-id="c5e59-125">Eine Plattformausnahme, die Geräten mit iOS erlaubt, auf Exchange zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="c5e59-125">A platform exception that allows devices that run iOS to access Exchange.</span></span>   

  -   <span data-ttu-id="c5e59-126">Eine Standardregel, die festlegt, dass der Zugriff auf Exchange über ein Gerät, das nicht durch die Plattformausnahmeregel abgedeckt ist, blockiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="c5e59-126">A default rule that specifies that when a device isn't covered by the platform exception rule, it should be blocked from accessing Exchange.</span></span> <span data-ttu-id="c5e59-127">Diese Regel stellt sicher, dass der Zugriff auf Exchange über Geräte, auf denen iOS nicht ausgeführt wird, blockiert wird.</span><span class="sxs-lookup"><span data-stu-id="c5e59-127">This rule makes sure that devices that aren't running iOS are blocked from accessing Exchange.</span></span>

<span data-ttu-id="c5e59-128">Sie verwenden den folgenden Ablauf, um zu entscheiden, welche Geräte auf Exchange zugreifen können:</span><span class="sxs-lookup"><span data-stu-id="c5e59-128">You use the following flow to decide which devices can access Exchange:</span></span>

![Ablauf für Gerätezugriff](./media/ConditionalAccess8-3.png)

## <a name="scenario-3-no-android-devices-can-access-exchange-on-premises"></a><span data-ttu-id="c5e59-130">Szenario 3: Kein Android-Gerät darf auf lokales Exchange zugreifen</span><span class="sxs-lookup"><span data-stu-id="c5e59-130">Scenario 3: No Android devices can access Exchange on-premises</span></span>
### <a name="scenario-requirements"></a><span data-ttu-id="c5e59-131">Anforderungen für das Szenario</span><span class="sxs-lookup"><span data-stu-id="c5e59-131">Scenario requirements</span></span>
- <span data-ttu-id="c5e59-132">Der Zugriff auf Exchange soll für alle Android-Geräte blockiert werden.</span><span class="sxs-lookup"><span data-stu-id="c5e59-132">All Android devices should be blocked from accessing Exchange.</span></span>
- <span data-ttu-id="c5e59-133">Alle anderen unterstützten Geräte können auf Exchange zugreifen, solange sie von Intune verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="c5e59-133">All other supported devices can access Exchange, as long as they're managed by Intune.</span></span>

<span data-ttu-id="c5e59-134">Um dies zu erreichen, konfigurieren Sie eine Richtlinie für bedingten Zugriff für lokales Exchange mit folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="c5e59-134">To accomplish this, configure a conditional access policy for Exchange on-premises with the following settings:</span></span>

-   <span data-ttu-id="c5e59-135">Wählen Sie die Option **Zugriff auf lokales Exchange von E-Mail-Apps blockieren, wenn das Gerät nicht kompatibel oder nicht bei Microsoft Intune registriert ist**.</span><span class="sxs-lookup"><span data-stu-id="c5e59-135">Choose the option **Block email apps from accessing Exchange on-premises if the device is noncompliant or not enrolled in Microsoft Intune**.</span></span> <span data-ttu-id="c5e59-136">Durch Auswahl dieser Option legen Sie fest, dass alle Geräte bei Intune registriert sein und die Regeln der Kompatibilitätsrichtlinie erfüllen müssen.</span><span class="sxs-lookup"><span data-stu-id="c5e59-136">By choosing this option, you require that any device must be enrolled in Intune and meet the compliance policy rules.</span></span>

- <span data-ttu-id="c5e59-137">Erstellen Sie für die erweiterten Exchange ActiveSync-Einstellungen Folgendes:</span><span class="sxs-lookup"><span data-stu-id="c5e59-137">For advanced Exchange Active Sync settings, create:</span></span>
  -   <span data-ttu-id="c5e59-138">Eine Plattformausnahme, die verhindert, dass Geräte mit Android auf Exchange zugreifen.</span><span class="sxs-lookup"><span data-stu-id="c5e59-138">A platform exception that blocks devices that run Android from accessing Exchange.</span></span> <span data-ttu-id="c5e59-139">Diese Regel stellt sicher, dass Android-Geräte nicht für den Zugriff auf Exchange verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="c5e59-139">This rule makes sure that Android devices can't be used to access Exchange.</span></span>

  -   <span data-ttu-id="c5e59-140">Eine Standardregel, die angibt, dass ein Gerät für den Zugriff auf Exchange zugelassen werden soll, wenn es nicht durch andere Regeln abgedeckt wird.</span><span class="sxs-lookup"><span data-stu-id="c5e59-140">A default rule that specifies that when a device isn't covered by other rules, it should be allowed to access Exchange.</span></span> <span data-ttu-id="c5e59-141">Diese Standardregel stellt sicher, dass Geräte, auf denen andere Plattformen als Android ausgeführt werden, die aber von Microsoft Intune unterstützt werden, für den Zugriff auf Exchange verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="c5e59-141">This default rule makes sure that devices that run platforms other than Android, but are supported by Microsoft Intune, can be used to access Exchange.</span></span> <span data-ttu-id="c5e59-142">Sie müssen jedoch bei Intune registriert sein und die Regeln der Kompatibilitätsrichtlinie erfüllen.</span><span class="sxs-lookup"><span data-stu-id="c5e59-142">They must, however, be enrolled in Intune and meet the compliance policy rules.</span></span>

<span data-ttu-id="c5e59-143">Sie verwenden den folgenden Ablauf, um zu entscheiden, welche Geräte auf Exchange zugreifen können:</span><span class="sxs-lookup"><span data-stu-id="c5e59-143">You use the following flow to decide which devices can access Exchange:</span></span>

![Ablauf für Gerätezugriff](./media/ConditionalAccess8-4.png)
