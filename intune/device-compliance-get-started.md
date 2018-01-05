---
title: "Intune-Gerätekonformitätsrichtlinien"
titleSuffix: Azure portal
description: "In diesem Thema erhalten Sie Informationen zur Gerätekonformität in Microsoft Intune\""
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 07/18/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a916fa0d-890d-4efb-941c-7c3c05f8fe7c
ms.reviewer: muhosabe
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: c8fbf0d1b9229dc62a4ab412a03c6adfd94f07cb
ms.sourcegitcommit: e37e916e2bf14f092d3a767bc90d68c181d739fb
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/03/2018
---
# <a name="get-started-with-intune-device-compliance-policies"></a><span data-ttu-id="036bd-103">Erste Schritte mit den Intune-Gerätekonformitätsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="036bd-103">Get started with Intune device compliance policies</span></span>

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

## <a name="what-is-device-compliance-in-intune"></a><span data-ttu-id="036bd-104">Was ist die Gerätekonformität in Intune?</span><span class="sxs-lookup"><span data-stu-id="036bd-104">What is device compliance in Intune?</span></span>

<span data-ttu-id="036bd-105">Intune-Gerätekonformitätsrichtlinien definieren die Regeln und Einstellungen, die ein Gerät erfüllen muss, damit es von Intune als konform eingestuft wird.</span><span class="sxs-lookup"><span data-stu-id="036bd-105">Intune device compliance policies define the rules and settings that a device must comply with in order to be considered compliant by Intune.</span></span>

<span data-ttu-id="036bd-106">Diese Regeln umfassen Folgendes:</span><span class="sxs-lookup"><span data-stu-id="036bd-106">These rules include the following:</span></span>

- <span data-ttu-id="036bd-107">Verwendung eines Kennworts für den Gerätezugriff</span><span class="sxs-lookup"><span data-stu-id="036bd-107">Use a password to access devices</span></span>

- <span data-ttu-id="036bd-108">Verschlüsselung</span><span class="sxs-lookup"><span data-stu-id="036bd-108">Encryption</span></span>

- <span data-ttu-id="036bd-109">Ermittlung, ob das Gerät mit Jailbreak oder Rooting manipuliert wurde</span><span class="sxs-lookup"><span data-stu-id="036bd-109">Whether the device is jail-broken or rooted</span></span>

- <span data-ttu-id="036bd-110">Mindestens erforderliche Betriebssystemversion</span><span class="sxs-lookup"><span data-stu-id="036bd-110">Minimum OS version required</span></span>

- <span data-ttu-id="036bd-111">Maximal zulässige Betriebssystemversion</span><span class="sxs-lookup"><span data-stu-id="036bd-111">Maximum OS version allowed</span></span>

- <span data-ttu-id="036bd-112">Vorgabe, dass das Gerät maximal die Mobile Threat Defense-Stufe aufweisen darf</span><span class="sxs-lookup"><span data-stu-id="036bd-112">Require the device to be at or under the Mobile Threat Defense level</span></span>

<span data-ttu-id="036bd-113">Mithilfe von Kompatibilitätsrichtlinien können Sie den Kompatibilitätsstatus auf Ihren Geräten überwachen.</span><span class="sxs-lookup"><span data-stu-id="036bd-113">You can also use device compliance policies to monitor the compliance status in your devices.</span></span>

### <a name="device-compliance-requirements"></a><span data-ttu-id="036bd-114">Konformitätsanfoderungen für Geräte</span><span class="sxs-lookup"><span data-stu-id="036bd-114">Device compliance requirements</span></span>

<span data-ttu-id="036bd-115">Konformitätsanforderungen sind im Wesentlichen Regeln, mit denen Sie z.B. eine Geräte-PIN erzwingen oder angeben können, ob Verschlüsselung für die Konformitätsrichtlinie erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="036bd-115">Compliance requirements are essentially rules like requiring a device PIN or encryption that you can specify as required or not required for a compliance policy.</span></span>

<!---### Actions for noncompliance

You can specify what needs to happen when a device is determined as noncompliant. This can be a sequence of actions during a specific time.
When you specify these actions, Intune will automatically initiate them in the sequence you specify. See the following example of a sequence of
actions for a device that continues to be in the noncompliant status for
a week:

-   When the device is first determined to be non-compliant, an email with noncompliant notification is sent to the user.

-   3 days after initial noncompliance state, a follow up reminder is sent to the user.

-   5 days after initial noncompliance state, a final reminder with a notification that access to company resources will be blocked on the device in 2 days if the compliance issues are not remediated is sent to the user.

-   7 days after initial noncompliance state, access to company resources is blocked. This requires that you have conditional access policy that specifies that access from noncompliant devices should    be blocked for services such as Exchange and SharePoint.

### Grace Period

This is the time between when a device is first determined as
noncompliant to when access to company resources on that device is blocked. This time allows for time that the user has to resolve
compliance issues on the device. You can also use this time to create your action sequences to send notifications to the user before their access is blocked.

Remember that you need to implement conditional access policies in addition to compliance policies in order for access to company resources to be blocked.--->

##  <a name="pre-requisites"></a><span data-ttu-id="036bd-116">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="036bd-116">Pre-requisites</span></span>

<span data-ttu-id="036bd-117">Sie benötigen die folgenden Abonnements, um die Gerätekonformitätsrichtlinien mit Intune zu verwenden:</span><span class="sxs-lookup"><span data-stu-id="036bd-117">You need to have the following subscriptions to use device compliance policies with Intune:</span></span>

- <span data-ttu-id="036bd-118">Intune EMS</span><span class="sxs-lookup"><span data-stu-id="036bd-118">Intune EMS</span></span>

- <span data-ttu-id="036bd-119">Azure AD Premium</span><span class="sxs-lookup"><span data-stu-id="036bd-119">Azure AD Premium</span></span>

###  <a name="supported-platforms"></a><span data-ttu-id="036bd-120">Unterstützte Plattformen:</span><span class="sxs-lookup"><span data-stu-id="036bd-120">Supported Platforms:</span></span>

-   <span data-ttu-id="036bd-121">Android</span><span class="sxs-lookup"><span data-stu-id="036bd-121">Android</span></span>

-   <span data-ttu-id="036bd-122">iOS</span><span class="sxs-lookup"><span data-stu-id="036bd-122">iOS</span></span>

-   <span data-ttu-id="036bd-123">macOS (Vorschau)</span><span class="sxs-lookup"><span data-stu-id="036bd-123">macOS (preview)</span></span>

-   <span data-ttu-id="036bd-124">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="036bd-124">Windows 8.1</span></span>

-   <span data-ttu-id="036bd-125">Windows Phone 8.1</span><span class="sxs-lookup"><span data-stu-id="036bd-125">Windows Phone 8.1</span></span>

-   <span data-ttu-id="036bd-126">Windows 10</span><span class="sxs-lookup"><span data-stu-id="036bd-126">Windows 10</span></span>

> [!IMPORTANT]
> <span data-ttu-id="036bd-127">Geräte müssen in Intune registriert werden, um deren Konformitätsstatus melden zu können.</span><span class="sxs-lookup"><span data-stu-id="036bd-127">Devices must be enrolled into Intune to report their compliance statuses.</span></span>

## <a name="how-intune-device-compliance-policies-work-with-azure-ad"></a><span data-ttu-id="036bd-128">So funktionieren Intune-Gerätekonformitätsrichtlinien mit Azure AD</span><span class="sxs-lookup"><span data-stu-id="036bd-128">How Intune device compliance policies work with Azure AD</span></span>

<span data-ttu-id="036bd-129">Wenn ein Gerät in Intune registriert wird, schaltet sich der Azure AD-Registrierungsprozess ein, wodurch die Geräteattribute mit weiteren Informationen in Azure AD aktualisiert werden.</span><span class="sxs-lookup"><span data-stu-id="036bd-129">When a device is enrolled into Intune, the Azure AD registration process happens, which updates the device atributes with more information into Azure AD.</span></span> <span data-ttu-id="036bd-130">Eine der wichtigsten Geräteinformationen ist der Gerätekonformitätsstatus, der von bedingten Zugriffsrichtlinien zum Blockieren oder Zulassen von Zugriff auf E-Mails und andere Unternehmensressourcen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="036bd-130">One of the key device information is the device compliance status, which is used by conditional access policies to block or allow access to e-mail and other corporate resources.</span></span>

- <span data-ttu-id="036bd-131">Erfahren Sie mehr über den [Azure AD-Registrierungsprozess](https://docs.microsoft.com/azure/active-directory/active-directory-device-registration-overview).</span><span class="sxs-lookup"><span data-stu-id="036bd-131">Learn more about [Azure AD registration process](https://docs.microsoft.com/azure/active-directory/active-directory-device-registration-overview).</span></span>

##  <a name="ways-to-use-device-compliance-policies"></a><span data-ttu-id="036bd-132">Möglichkeiten, die Gerätekonformitätsrichtlinien zu verwalten</span><span class="sxs-lookup"><span data-stu-id="036bd-132">Ways to use device compliance policies</span></span>

### <a name="with-conditional-access"></a><span data-ttu-id="036bd-133">Mit bedingten Zugriff</span><span class="sxs-lookup"><span data-stu-id="036bd-133">With conditional access</span></span>
<span data-ttu-id="036bd-134">Sie können die Konformitätsrichtlinie mit dem bedingten Zugriff verwenden, um den Zugriff auf E-Mails und andere Unternehmensressourcen nur für Geräte zuzulassen, die mindestens eine Regel der Gerätekonformitätsrichtlinie erfüllen.</span><span class="sxs-lookup"><span data-stu-id="036bd-134">You can use compliance policy with conditional access to allow only devices that comply with one or more device compliance policy rules to access email and other corporate resources.</span></span>

### <a name="without-conditional-access"></a><span data-ttu-id="036bd-135">Ohne bedingten Zugriff</span><span class="sxs-lookup"><span data-stu-id="036bd-135">Without conditional access</span></span>
<span data-ttu-id="036bd-136">Gerätekonformitätsrichtlinien können auch unabhängig vom bedingten Zugriff verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="036bd-136">You can also use device compliance policies independently of conditional access.</span></span> <span data-ttu-id="036bd-137">Bei unabhängiger Nutzung von Kompatibilitätsrichtlinien werden die Zielgeräte ausgewertet und mit ihrem Kompatibilitätsstatus gemeldet.</span><span class="sxs-lookup"><span data-stu-id="036bd-137">When you use compliance policies independently, the targeted devices are evaluated and reported with their compliance status.</span></span> <span data-ttu-id="036bd-138">So können Sie beispielsweise einen Bericht dazu erstellen, wie viele Geräte nicht verschlüsselt sind oder mit Jailbreak oder Rootzugriff manipuliert wurden.</span><span class="sxs-lookup"><span data-stu-id="036bd-138">For example, you can get a report on how many devices are not encrypted, or which devices are jail-broken or rooted.</span></span> <span data-ttu-id="036bd-139">Aber wenn Sie Kompatibilitätsrichtlinien unabhängig nutzen, gelten keine Zugriffsbeschränkungen für Unternehmensressourcen.</span><span class="sxs-lookup"><span data-stu-id="036bd-139">But when you use compliance policies independently, no access restrictions to company resources are in place.</span></span>

<span data-ttu-id="036bd-140">Sie stellen Konformitätsrichtlinien für Benutzer bereit.</span><span class="sxs-lookup"><span data-stu-id="036bd-140">You deploy compliance policy to users.</span></span> <span data-ttu-id="036bd-141">Wenn Sie eine Kompatibilitätsrichtlinie für einen Benutzer bereitstellen, wird die Kompatibilität der Geräte des Benutzers überprüft.</span><span class="sxs-lookup"><span data-stu-id="036bd-141">When a compliance policy is deployed to a user, the user's devices are checked for compliance.</span></span> <span data-ttu-id="036bd-142">Informationen darüber, wie lange es dauert, bis eine Richtlinie für mobile Geräte nach der Bereitstellung der Richtlinie abgerufen wird, finden Sie unter „Verwalten von Einstellungen und Features auf Ihren Geräten“.</span><span class="sxs-lookup"><span data-stu-id="036bd-142">To learn about how long it takes for mobile devices to get a policy after the policy is deployed, see Manage settings and features on your devices.</span></span>

##  <a name="using-device-compliance-policies-in-the-intune-classic-portal-vs-azure-portal"></a><span data-ttu-id="036bd-143">Verwendung von Gerätekonformitätsrichtlinien im klassischen Intune-Portal vs. Azure-Portal</span><span class="sxs-lookup"><span data-stu-id="036bd-143">Using device compliance policies in the Intune classic portal vs. Azure portal</span></span>

<span data-ttu-id="036bd-144">Beachten Sie die wichtigsten Unterschiede beim Übergang in den neuen Workflow zur Gerätekonformitätsrichtlinie im Azure-Portal.</span><span class="sxs-lookup"><span data-stu-id="036bd-144">Note the main differences to help you transition to the new device compliance policy work-flow in the Azure portal.</span></span>

- <span data-ttu-id="036bd-145">In Azure-Portal werden die Konformitätsrichtlinien separat für jede unterstützte Plattform erstellt.</span><span class="sxs-lookup"><span data-stu-id="036bd-145">In the Azure portal, the compliance policies are created separately for each supported platform.</span></span>
- <span data-ttu-id="036bd-146">Im klassischen Intune-Portal wurde eine Gerätekonformitätsrichtlinie für alle unterstützten Plattformen verwendet.</span><span class="sxs-lookup"><span data-stu-id="036bd-146">In the Intune classic portal, one device compliance policy was common to all supported platforms.</span></span>

<!--- -   In the Azure portal, you have the ability to specify actions and notifications that are intiated when a device is determined to be noncompliant. This ability does not exist in the Intune admin console.

-   In the Azure portal, you can set a grace period to allow time for the end-user to get their device back to compliance status before they completely lose the ability to get company data on their device. This is not available in the Intune admin console.--->

##  <a name="migrate-device-compliance-policies-from-the-intune-classic-portal-to-the-azure-portal"></a><span data-ttu-id="036bd-147">Migrieren von Gerätekonformitätsrichtlinien vom klassischen Intune-Portal zum Azure-Portal</span><span class="sxs-lookup"><span data-stu-id="036bd-147">Migrate device compliance policies from the Intune classic portal to the Azure portal</span></span>

<span data-ttu-id="036bd-148">Gerätekonformitätsrichtlinien, die im [klassischen Intune-Portal](https://manage.microsoft.com) erstellt wurden, erscheinen nicht im neuen [Intune Azure-Portal](https://portal.azure.com).</span><span class="sxs-lookup"><span data-stu-id="036bd-148">Device compliance policies created in the [Intune classic portal](https://manage.microsoft.com) will not appear in the new [Intune Azure portal](https://portal.azure.com).</span></span> <span data-ttu-id="036bd-149">Sie sind jedoch weiterhin für Benutzer bestimmt und können über das klassische Intune-Portal verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="036bd-149">However, they’re still targeted to users and manageable via the Intune classic portal.</span></span>

<span data-ttu-id="036bd-150">Wenn Sie von den neuen Funktionen für Gerätekonformität im Azure-Portal profitieren wollen, müssen Sie neue Gerätekonformitätsrichtlinien im Azure-Portal selbst erstellen.</span><span class="sxs-lookup"><span data-stu-id="036bd-150">If you want to take advantage of the new device compliance related features in the Azure portal, you need to create new device compliance policies in the Azure portal itself.</span></span> <span data-ttu-id="036bd-151">Wenn Sie eine neue Gerätekonformitätsrichtlinie im Azure-Portal einem Benutzer zuweisen, dem auch eine Gerätekonformitätsrichtlinie aus dem klassischen Intune-Portal zugewiesen wurde, haben die Gerätekonformitätsrichtlinien aus dem Intune-Azure-Portal Vorrang vor denen, die im klassischen Intune-Portal erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="036bd-151">If you assign a new device compliance policy in the Azure portal to a user who also has been assigned with a device compliance policy from the Intune classic portal, the device compliance policies from the Intune Azure portal takes precedence over the ones created in the Intune classic portal.</span></span>

##  <a name="next-steps"></a><span data-ttu-id="036bd-152">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="036bd-152">Next steps</span></span>

<span data-ttu-id="036bd-153">Plattformspezifische Informationen zum Erstellen einer Gerätekonformitätsrichtlinie finden Sie hier:</span><span class="sxs-lookup"><span data-stu-id="036bd-153">Create a device compliance policy for the following platforms:</span></span>

- [<span data-ttu-id="036bd-154">Android</span><span class="sxs-lookup"><span data-stu-id="036bd-154">Android</span></span>](compliance-policy-create-android.md)
- [<span data-ttu-id="036bd-155">Android for Work</span><span class="sxs-lookup"><span data-stu-id="036bd-155">Android for work</span></span>](compliance-policy-create-android-for-work.md)
- [<span data-ttu-id="036bd-156">iOS</span><span class="sxs-lookup"><span data-stu-id="036bd-156">iOS</span></span>](compliance-policy-create-ios.md)
- [<span data-ttu-id="036bd-157">macOS</span><span class="sxs-lookup"><span data-stu-id="036bd-157">macOS</span></span>](compliance-policy-create-mac-os.md)
- [<span data-ttu-id="036bd-158">Windows</span><span class="sxs-lookup"><span data-stu-id="036bd-158">Windows</span></span>](compliance-policy-create-windows.md)
