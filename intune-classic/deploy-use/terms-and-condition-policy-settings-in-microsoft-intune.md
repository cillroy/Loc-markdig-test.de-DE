---
title: "Richtlinieneinstellungen für Geschäftsbedingungen"
description: "Sie können Intune-Nutzungsbedingungen für Benutzergruppen bereitstellen, um zu erläutern, wie sich die Registrierung, der Zugriff auf Arbeitsressourcen und die Verwendung des Unternehmensportals auf Geräte und Benutzer auswirken."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 07/11/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6edf0ac1-4f46-4543-a9e5-f484ac37e9a5
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: b47bd3fa7225ee0f5bf9a8aaa4a92e2d93d92225
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2018
---
# <a name="terms-and-condition-policy-settings-in-microsoft-intune"></a><span data-ttu-id="1a4ec-103">Einstellungen für Nutzungsbedingungsrichtlinien in Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="1a4ec-103">Terms and condition policy settings in Microsoft Intune</span></span>

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="1a4ec-104">Sie können Intune-Nutzungsbedingungen für Benutzergruppen bereitstellen, um zu erläutern, wie sich die Registrierung, der Zugriff auf Arbeitsressourcen und das Unternehmensportal auf Geräte und Benutzer auswirken.</span><span class="sxs-lookup"><span data-stu-id="1a4ec-104">You can deploy Intune terms and conditions to user groups to explain how enrollment, access to work resources, and the Company Portal app affect devices and users.</span></span> <span data-ttu-id="1a4ec-105">Benutzer müssen die Nutzungsbedingungen akzeptieren, bevor sie sich über das Unternehmensportal registrieren und auf ihre Arbeit zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="1a4ec-105">Users must accept the terms and conditions before they can use the Company Portal to enroll and access their work.</span></span>

<span data-ttu-id="1a4ec-106">Sie können mehrere Richtlinien erstellen und bereitstellen, die verschiedene Nutzungsbedingungen enthalten.</span><span class="sxs-lookup"><span data-stu-id="1a4ec-106">You can create and deploy multiple policies containing different terms and conditions.</span></span> <span data-ttu-id="1a4ec-107">Sie können auch Versionen derselben Nutzungsbedingungen in verschiedenen Sprachen erstellen und diese dann für die entsprechenden Gruppen bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="1a4ec-107">You can also produce versions of the same terms and conditions in different languages and then deploy these to their appropriate groups.</span></span>

## <a name="create-a-terms-and-conditions-policy"></a><span data-ttu-id="1a4ec-108">Erstellen einer Nutzungsbedingungsrichtlinie</span><span class="sxs-lookup"><span data-stu-id="1a4ec-108">Create a terms and conditions policy</span></span>

1.  <span data-ttu-id="1a4ec-109">Klicken Sie in der [Microsoft Intune-Verwaltungskonsole](https://manage.microsoft.com) auf **Richtlinie** &gt; **Nutzungsbedingungen**.</span><span class="sxs-lookup"><span data-stu-id="1a4ec-109">In the [Microsoft Intune administration console](https://manage.microsoft.com) click **Policy** &gt; **Terms and Conditions**.</span></span>

    ![Screenshot für Nutzungsbedingungsrichtlinien](./media/pol-sa-terms-conditions.png)

2.  <span data-ttu-id="1a4ec-111">Klicken Sie auf **Hinzufügen**, um eine neue Nutzungsbedingungsrichtlinie zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="1a4ec-111">Click **Add** to create a new terms and conditions policy.</span></span>

    <span data-ttu-id="1a4ec-112">Sie können auch eine vorhandene Richtlinie **bearbeiten** oder **löschen**.</span><span class="sxs-lookup"><span data-stu-id="1a4ec-112">You can also **Edit** or **Delete** an existing policy.</span></span>

3.  <span data-ttu-id="1a4ec-113">Geben Sie auf der Seite zum **Erstellen der Nutzungsbedingungen** die folgenden Informationen an:</span><span class="sxs-lookup"><span data-stu-id="1a4ec-113">On the **Create Terms and Conditions** page, specify the following information:</span></span>

    -   <span data-ttu-id="1a4ec-114">**Name**&mdash;Ein eindeutiger Richtlinienname, der in der Intune-Konsole angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="1a4ec-114">**Name**&mdash;A unique policy name displayed in the Intune console.</span></span>

    -   <span data-ttu-id="1a4ec-115">**Beschreibung**&mdash;Details, die Ihnen dabei helfen, die Richtlinie in der Intune-Konsole zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="1a4ec-115">**Description**&mdash;Details that help you identify the policy in the Intune console.</span></span>

    -   <span data-ttu-id="1a4ec-116">**Titel**&mdash;Der Titel, der Benutzern im Unternehmensportal angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="1a4ec-116">**Title**&mdash;The title users see in the company portal.</span></span>

    -   <span data-ttu-id="1a4ec-117">**Text zur Erläuterung der Bedeutung, wenn der Benutzer zustimmt**&mdash;Die für Benutzer angezeigte Bezeichnung hinsichtlich der Zustimmung.</span><span class="sxs-lookup"><span data-stu-id="1a4ec-117">**Text to explain what it means if the user accepts**&mdash;The label users see regarding acceptance.</span></span> <span data-ttu-id="1a4ec-118">Beispiel: „Ich stimme den Nutzungsbedingungen zu.“</span><span class="sxs-lookup"><span data-stu-id="1a4ec-118">For example, “I agree to the terms and conditions.”</span></span>

4.  <span data-ttu-id="1a4ec-119">Wenn Sie fertig sind, klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="1a4ec-119">When you are finished, click **Save**.</span></span> <span data-ttu-id="1a4ec-120">Die neue Richtlinie wird im Knoten für die **Nutzungsbedingungen** des Arbeitsbereichs **Richtlinie** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="1a4ec-120">The new policy is displayed in the **Terms and Conditions** node of the **Policy** workspace.</span></span>

## <a name="deploy-a-terms-and-conditions-policy"></a><span data-ttu-id="1a4ec-121">Bereitstellen einer Nutzungsbedingungsrichtlinie</span><span class="sxs-lookup"><span data-stu-id="1a4ec-121">Deploy a terms and conditions policy</span></span>

1.  <span data-ttu-id="1a4ec-122">Klicken Sie in der [Microsoft Intune-Verwaltungskonsole](https://manage.microsoft.com) auf **Richtlinie** &gt; **Nutzungsbedingungen**.</span><span class="sxs-lookup"><span data-stu-id="1a4ec-122">In the [Microsoft Intune administration console](https://manage.microsoft.com), click **Policy** &gt; **Terms and Conditions**.</span></span>

2.  <span data-ttu-id="1a4ec-123">Wählen Sie in der Liste der **Nutzungsbedingungsrichtlinien** die bereitzustellende Richtlinie aus, und klicken Sie dann auf **Bereitstellung verwalten**.</span><span class="sxs-lookup"><span data-stu-id="1a4ec-123">In the **Terms and Conditions Policies** list, select the policy you want to deploy, and then click **Manage Deployment**.</span></span>

3.  <span data-ttu-id="1a4ec-124">Wählen Sie im Dialogfeld **Bereitstellung verwalten** die Gruppen aus, für die Sie die Richtlinie bereitstellen möchten, und klicken Sie anschließend auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="1a4ec-124">In the **Manage Deployment** dialog box, select the user groups you will deploy the policy to, and then click **OK**.</span></span>

    <span data-ttu-id="1a4ec-125">Wenn die anvisierten Benutzer auf das Unternehmensportal zugreifen, zeigt Intune die bereitgestellten Nutzungsbedingungen an.</span><span class="sxs-lookup"><span data-stu-id="1a4ec-125">When targeted users access the company portal, Intune displays the terms and conditions you deployed.</span></span> <span data-ttu-id="1a4ec-126">Benutzer müssen diese Nutzungsbedingungen akzeptieren, bevor sie Zugriff auf Unternehmensressourcen erhalten.</span><span class="sxs-lookup"><span data-stu-id="1a4ec-126">Users must accept these terms before they can gain access to company resources.</span></span>

## <a name="monitor-a-terms-and-conditions-policy"></a><span data-ttu-id="1a4ec-127">Überwachen einer Nutzungsbedingungsrichtlinie</span><span class="sxs-lookup"><span data-stu-id="1a4ec-127">Monitor a terms and conditions policy</span></span>

1.  <span data-ttu-id="1a4ec-128">Klicken Sie in der [Microsoft Intune-Verwaltungskonsole](https://manage.microsoft.com) auf **Richtlinie** &gt; **Nutzungsbedingungen**.</span><span class="sxs-lookup"><span data-stu-id="1a4ec-128">In the [Microsoft Intune administration console](https://manage.microsoft.com), click **Policy** &gt; **Terms and Conditions**.</span></span>

2.  <span data-ttu-id="1a4ec-129">Klicken Sie im Fenster **Neuen Bericht erstellen** auf **Bericht anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="1a4ec-129">In the **Create New Report** window, click **View Report**.</span></span> <span data-ttu-id="1a4ec-130">Der Bericht wird mit ausführlichen Informationen geöffnet, welche Benutzer die bereitgestellten Nutzungsbedingungen akzeptiert haben.</span><span class="sxs-lookup"><span data-stu-id="1a4ec-130">The report will open detailing which users have accepted the terms and conditions you deployed.</span></span>

### <a name="updates-and-version-control-for-terms-and-conditions"></a><span data-ttu-id="1a4ec-131">Updates und Versionskontrolle für Nutzungsbedingungen</span><span class="sxs-lookup"><span data-stu-id="1a4ec-131">Updates and version control for terms and conditions</span></span>
<span data-ttu-id="1a4ec-132">Beim Bearbeiten einer vorhandenen Nutzungsbedingungsrichtlinie können Sie auswählen, welches Verhalten erfolgt, wenn Sie die Richtlinie bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="1a4ec-132">When you edit an existing terms and conditions policy, you can choose which behavior occurs when you deploy the policy.</span></span> <span data-ttu-id="1a4ec-133">Verwenden Sie das folgende Verfahren beim Aktualisieren vorhandener Nutzungsbedingungsrichtlinien.</span><span class="sxs-lookup"><span data-stu-id="1a4ec-133">Use the following procedure to help you update existing terms and conditions policies.</span></span>

## <a name="work-with-multiple-versions-of-terms-and-conditions"></a><span data-ttu-id="1a4ec-134">Arbeiten mit mehreren Versionen der Nutzungsbedingungen</span><span class="sxs-lookup"><span data-stu-id="1a4ec-134">Work with multiple versions of terms and conditions</span></span>

1.  <span data-ttu-id="1a4ec-135">Klicken Sie in der [Microsoft Intune-Verwaltungskonsole](https://manage.microsoft.com) auf **Richtlinie** &gt; **Nutzungsbedingungen**.</span><span class="sxs-lookup"><span data-stu-id="1a4ec-135">In the [Microsoft Intune administration console](https://manage.microsoft.com), click **Policy** &gt; **Terms and Conditions**.</span></span>

2.  <span data-ttu-id="1a4ec-136">Wählen Sie die zu bearbeitende Nutzungsbedingungsrichtlinie aus, und klicken Sie dann auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="1a4ec-136">Select the terms and conditions policy that you want to edit, and then click **Edit**.</span></span>

3.  <span data-ttu-id="1a4ec-137">Nehmen Sie auf der Seite zum **Bearbeiten der Nutzungsbedingungen** alle erforderlichen Änderungen vor, und geben Sie dann an, ob diese neue Version von allen Benutzern eine Zustimmung zu den Nutzungsbedingungen erfordert oder ob sie nur für neue Benutzer angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="1a4ec-137">On the **Edit Terms and Conditions** page, make any required edits, and then specify whether this new version requires all users to accept the terms and conditions, or if only new users will see the new version.</span></span>

    <span data-ttu-id="1a4ec-138">Es wird empfohlen, dass Sie jedes Mal die Versionsnummer erhöhen und die Zustimmung zu den Nutzungsbedingungen anfordern, wenn Sie wichtige Änderungen an der Nutzungsbedingungsrichtlinie vornehmen.</span><span class="sxs-lookup"><span data-stu-id="1a4ec-138">We recommend that you increase the version number and require acceptance any time you make significant changes to your terms and conditions policy.</span></span> <span data-ttu-id="1a4ec-139">Behalten Sie die aktuelle Versionsnummer bei, wenn Sie z. B. Tippfehler korrigieren oder die Formatierung ändern.</span><span class="sxs-lookup"><span data-stu-id="1a4ec-139">Keep the current version number if you are fixing typos or changing formatting, for example.</span></span>

### <a name="see-also"></a><span data-ttu-id="1a4ec-140">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1a4ec-140">See also</span></span>
[<span data-ttu-id="1a4ec-141">Verwalten von Einstellungen und Features auf Ihren Geräten mit Microsoft Intune-Richtlinien</span><span class="sxs-lookup"><span data-stu-id="1a4ec-141">Manage settings and features on your devices with Microsoft Intune policies</span></span>](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md)
