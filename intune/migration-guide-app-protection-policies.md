---
title: "Konfigurieren von App-Schutzrichtlinien während einer Migration von Intune"
description: "Dieser Artikel gibt einen Überblick über die für die Einrichtung der App-Schutzrichtlinien notwendigen Schritte während einer Migration von Intune."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 07/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 93cda587-bf56-4d41-b123-9fe203fad788
ms.reviewer: dagerrit
ms.suite: ems
ms.openlocfilehash: c58ce51731b476cfca71851430297aff3edc5cd6
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2017
---
# <a name="configure-app-protection-policies-optional"></a><span data-ttu-id="9b0ce-103">Konfigurieren von App-Schutzrichtlinien (optional)</span><span class="sxs-lookup"><span data-stu-id="9b0ce-103">Configure app protection policies (optional)</span></span>


<span data-ttu-id="9b0ce-104">Mit App-Schutzrichtlinien können Sie Folgendes tun:</span><span class="sxs-lookup"><span data-stu-id="9b0ce-104">App protection policies allow you to:</span></span>
* <span data-ttu-id="9b0ce-105">Apps verschlüsseln</span><span class="sxs-lookup"><span data-stu-id="9b0ce-105">Encrypt apps</span></span>
* <span data-ttu-id="9b0ce-106">Definieren einer PIN, wenn auf die App zugegriffen wird</span><span class="sxs-lookup"><span data-stu-id="9b0ce-106">Define a PIN when the app is accessed</span></span>
* <span data-ttu-id="9b0ce-107">Verhindern, das Apps auf Geräten, bei denen Nutzungsbeschränkungen entfernt wurden, ausgeführt werden und viele weitere Schutzmaßnahmen.</span><span class="sxs-lookup"><span data-stu-id="9b0ce-107">Block apps from running on jail-broken or rooted devices, and many other protections.</span></span>

<span data-ttu-id="9b0ce-108">Wenn das Gerät des Benutzer verloren geht oder gestohlen wurde, können Sie die Unternehmensdaten remote selektiv zurücksetzen, ohne dass die persönlichen Daten davon betroffen wären.</span><span class="sxs-lookup"><span data-stu-id="9b0ce-108">If the user's phone is lost or stolen, you can selectively wipe the corporate data remotely while leaving the personal data intact.</span></span>

<span data-ttu-id="9b0ce-109">App-Schutzrichtlinien wenden Sicherheitsmaßnahmen auf der Geräteebene an und erfordern keine Geräteregistrierung.</span><span class="sxs-lookup"><span data-stu-id="9b0ce-109">App protection policies apply security at the app level and do not require device enrollment.</span></span> <span data-ttu-id="9b0ce-110">Sie können sie sowohl für Geräte, die in Intune registriert sind, als auch für nicht registrierte Geräte verwenden.</span><span class="sxs-lookup"><span data-stu-id="9b0ce-110">You can use them with devices enrolled into Intune or not.</span></span> <span data-ttu-id="9b0ce-111">Des Weiteren können Sie auch für Geräte verwendet werden, die für Drittanbieter-MDM registriert sind.</span><span class="sxs-lookup"><span data-stu-id="9b0ce-111">Additionally, you can apply them to devices enrolled into a third-party MDM provider.</span></span>

## <a name="app-protection-policies-with-lob-apps"></a><span data-ttu-id="9b0ce-112">App-Schutzrichtlinien für branchenspezifische Apps</span><span class="sxs-lookup"><span data-stu-id="9b0ce-112">App protection policies with LOB apps</span></span>

<span data-ttu-id="9b0ce-113">Sie können die App-Schutzrichtlinien auch auf branchenspezifische Apps ausweiten, indem Sie das [Microsoft Intune App SDK](app-sdk-get-started.md) oder das Microsoft Intune App Wrapping Tool sowohl für [iOS](https://www.microsoft.com/download/details.aspx?id=45218&751be11f-ede8-5a0c-058c-2ee190a24fa6=True)- als auch für [Android](https://www.microsoft.com/download/details.aspx?id=47267)-Plattformen verwenden.</span><span class="sxs-lookup"><span data-stu-id="9b0ce-113">You can also extend the mobile app protection policies to your line-of-business (LOB) apps by using the [Microsoft Intune App SDK](app-sdk-get-started.md) or the Microsoft Intune App Wrapping Tool for both [IOS](https://www.microsoft.com/download/details.aspx?id=45218&751be11f-ede8-5a0c-058c-2ee190a24fa6=True) and [Android](https://www.microsoft.com/download/details.aspx?id=47267) platforms.</span></span>

## <a name="how-do-app-protection-policies-help-during-migration"></a><span data-ttu-id="9b0ce-114">Wie helfen App-Schutzrichtlinien bei der Migration?</span><span class="sxs-lookup"><span data-stu-id="9b0ce-114">How do app protection policies help during migration?</span></span>

<span data-ttu-id="9b0ce-115">Bei der Migration müssen Sie Geräte vom alten MDM-Anbieter entfernen und in Intune registrieren.</span><span class="sxs-lookup"><span data-stu-id="9b0ce-115">In a migration, you must remove devices from the old MDM provider and enroll them into Intune.</span></span> <span data-ttu-id="9b0ce-116">Dies sollten Sie berücksichtigen und Ihre Endbenutzer dazu anhalten, den alten MDM-Anbieter zu verlassen und sich umgehend in Intune zu registrieren.</span><span class="sxs-lookup"><span data-stu-id="9b0ce-116">You should plan for this and encourage your end-users to leave the old MDM provider and immediately enroll into Intune.</span></span> <span data-ttu-id="9b0ce-117">Bei der Migration kann es allerdings Benutzer geben, die den Abschluss des Registrierungsprozesses verzögern, weil Ihre Geräte von keinem der beiden MDM-Anbieter verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="9b0ce-117">However, during the migration there may be users who delay completing the enrollment process and whose devices are not managed by either MDM provider.</span></span>

<span data-ttu-id="9b0ce-118">In diesem Zeitraum kann Ihre Organisation anfälliger sein für den Geräteklau und den Verlust von Unternehmensdaten, wenn der Zugriff auf Unternehmensressourcen immer noch möglich ist.</span><span class="sxs-lookup"><span data-stu-id="9b0ce-118">This period can leave your organization more vulnerable to device theft and corporate data loss if corporate resource access is still allowed.</span></span> <span data-ttu-id="9b0ce-119">Außerdem kann die Benutzerproduktivität abnehmen, wenn der Zugriff auf Unternehmensressourcen blockiert ist.</span><span class="sxs-lookup"><span data-stu-id="9b0ce-119">It may also lead to lower user productivity if corporate resource access is blocked.</span></span>

<span data-ttu-id="9b0ce-120">Intune bietet Schutz für Unternehmensdaten während der Migration, damit Ihre Unternehmensdaten weiterhin geschützt sind, auch wenn es gerade keine Verwaltung auf der Geräteebene gibt.</span><span class="sxs-lookup"><span data-stu-id="9b0ce-120">Intune can offer corporate data protections during the migration so you can still have security coverage for your corporate data when there’s no device-level management.</span></span>

<span data-ttu-id="9b0ce-121">Wenn Sie den bedingten Zugriff beim alten MDM-Anbieter deaktivieren, können die Benutzer immer noch produktiv sein, während Sie sie zu Intune überführen.</span><span class="sxs-lookup"><span data-stu-id="9b0ce-121">As you disable conditional access in the old MDM provider, users can still be productive while you on-board them into Intune.</span></span>

## <a name="task-list-for-app-protection-policies"></a><span data-ttu-id="9b0ce-122">Aufgabenliste für App-Schutzrichtlinien</span><span class="sxs-lookup"><span data-stu-id="9b0ce-122">Task list for app protection policies</span></span>

1. [<span data-ttu-id="9b0ce-123">Erstellen einer App-Schutzrichtlinie</span><span class="sxs-lookup"><span data-stu-id="9b0ce-123">Create an app protection policy</span></span>](app-protection-policies.md#create-an-app-protection-policy)
2. [<span data-ttu-id="9b0ce-124">Bereitstellen einer Richtlinie</span><span class="sxs-lookup"><span data-stu-id="9b0ce-124">Deploy a policy</span></span>](app-protection-policies.md#deploy-a-policy-to-users)


## <a name="next-steps"></a><span data-ttu-id="9b0ce-125">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="9b0ce-125">Next steps</span></span>

[<span data-ttu-id="9b0ce-126">Besondere Überlegungen bei der Migration</span><span class="sxs-lookup"><span data-stu-id="9b0ce-126">Special migration considerations</span></span>](migration-guide-considerations.md)
