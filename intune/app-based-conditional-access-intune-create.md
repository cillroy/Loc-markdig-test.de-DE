---
title: "App-basierte Richtlinie für bedingten Zugriff mit Intune"
description: "In diesem Thema wird beschrieben, wie Sie eine App-basierte Richtlinie für bedingten Zugriff mit Intune konfigurieren können."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 06/28/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d1693515-de18-4553-91ef-801976cd3ec7
ms.reviewer: chrisgre
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 1e48effd28d1e0598abbdfbf1c48298366c07a4f
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2018
---
# <a name="set-up-app-based-conditional-access-policies"></a><span data-ttu-id="ce4a8-103">Einrichten App-basierter Richtlinien für bedingten Zugriff</span><span class="sxs-lookup"><span data-stu-id="ce4a8-103">Set up app-based conditional access policies</span></span>

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="ce4a8-104">Dieses Thema enthält Anweisungen zum Einrichten App-basierter Richtlinien für bedingten Zugriff für Apps, die in der Liste der genehmigten Apps aufgeführt sind.</span><span class="sxs-lookup"><span data-stu-id="ce4a8-104">This topic provides instructions on how to set up app-based conditional access policies for apps that are part of the list of approved apps.</span></span> <span data-ttu-id="ce4a8-105">Die Liste der genehmigten Apps enthält Apps, die von Microsoft getestet wurden.</span><span class="sxs-lookup"><span data-stu-id="ce4a8-105">The list of approved apps consists of apps that were tested by Microsoft.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ce4a8-106">Dieses Thema führt durch die Schritte zum Hinzufügen einer App-basierten Richtlinie für bedingten Zugriff mit Exchange Online. Sie können dieselben Schritte aber auch beim Hinzufügen anderer Apps aus der Liste der genehmigten Apps wie SharePoint Online, Microsoft Teams usw. verwenden.</span><span class="sxs-lookup"><span data-stu-id="ce4a8-106">This topic walks through the steps to add an app-based conditional access policy using Exchange Online, but you can use the same steps when adding other apps like SharePoint Online, Microsoft Teams, etc. from the list of approved apps.</span></span>

## <a name="to-create-an-app-based-conditional-access-policy"></a><span data-ttu-id="ce4a8-107">So erstellen Sie eine App-basierte bedingte Zugriffsrichtlinie</span><span class="sxs-lookup"><span data-stu-id="ce4a8-107">To create an app-based conditional access policy</span></span>
1.  <span data-ttu-id="ce4a8-108">Navigieren Sie zum [Azure-Portal](https://portal.azure.com), und melden Sie sich mit Ihren Anmeldeinformationen an.</span><span class="sxs-lookup"><span data-stu-id="ce4a8-108">Go the [Azure portal](https://portal.azure.com) and sign in with your credentials.</span></span>

2.  <span data-ttu-id="ce4a8-109">Wählen Sie **Weitere Dienste** aus, und geben Sie „Intune“ ein.</span><span class="sxs-lookup"><span data-stu-id="ce4a8-109">Choose **More services**, and type: "Intune".</span></span>

3.  <span data-ttu-id="ce4a8-110">Wählen Sie **Intune-Schutz für Apps** aus.</span><span class="sxs-lookup"><span data-stu-id="ce4a8-110">Choose **Intune App Protection**.</span></span>

4.  <span data-ttu-id="ce4a8-111">Wählen Sie auf dem Blatt **Mobile Anwendungsverwaltung mit Intune** **Alle Einstellungen** aus.</span><span class="sxs-lookup"><span data-stu-id="ce4a8-111">On the **Intune mobile application management** blade choose **All Settings**.</span></span>

5.  <span data-ttu-id="ce4a8-112">Wählen Sie im Abschnitt **Bedingter Zugriff** **Exchange Online** aus.</span><span class="sxs-lookup"><span data-stu-id="ce4a8-112">On the **Conditional access** section, choose **Exchange Online**.</span></span>

    ![Screenshot des Blatts „Einstellungen“, das den Abschnitt „Bedingter Zugriff“ anzeigt, wobei die Option „Exchange Online“ hervorgehoben ist](./media/MAM-conditional-access-1.png)

6. <span data-ttu-id="ce4a8-114">Wählen Sie auf dem Blatt **Zulässige Apps** die Option **Allow apps that support Intune app policies** (Apps zulassen, die Intune-App-Richtlinien unterstützen), um nur Apps zuzulassen, die von Intune-App-Schutzrichtlinien unterstützt werden, damit sie auf Exchange Online zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="ce4a8-114">On the **Allowed apps** blade, choose the **Allow apps that support Intune app policies** option to allow only apps that are supported by Intune app protection policies to have the ability to access Exchange Online.</span></span> <span data-ttu-id="ce4a8-115">Wenn Sie diese Option auswählen, wird die Liste der unterstützten Apps angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ce4a8-115">When you select this option, the list of supported apps is displayed.</span></span>

    > [!NOTE]
    > <span data-ttu-id="ce4a8-116">Alle E-Mail-Clients von Exchange Active Sync, einschließlich der integrierten E-Mail-Clients unter iOS und Android, die eine Verbindung mit Exchange Online herstellen, werden daran gehindert, E-Mails zu senden oder zu empfangen.</span><span class="sxs-lookup"><span data-stu-id="ce4a8-116">All Exchange Active Sync mail clients, including the built-in mail clients on iOS and Android that connect to Exchange Online, will be prevented from sending or receiving email.</span></span> <span data-ttu-id="ce4a8-117">Benutzer erhalten stattdessen eine einzige E-Mail, die sie darüber informiert, dass sie die Outlook-E-Mail-App verwenden müssen.</span><span class="sxs-lookup"><span data-stu-id="ce4a8-117">Users will instead receive a single email informing them that they need to use the Outlook mail app.</span></span>

7. <span data-ttu-id="ce4a8-118">Um diese Richtlinie auf Benutzer anzuwenden, öffnen Sie das Blatt **Eingeschränkte Benutzergruppen**, und wählen Sie **Benutzergruppe hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="ce4a8-118">To apply this policy to users, open the **Restricted user groups** blade, and choose **Add user group**.</span></span> <span data-ttu-id="ce4a8-119">Wählen Sie mindestens eine Benutzergruppe aus, auf die diese Richtlinie angewendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="ce4a8-119">Select one or more user groups that should get this policy.</span></span>

    ![Screenshot des Blatts „Eingeschränkte Benutzergruppen“ mit hervorgehobener Option „Benutzergruppe hinzufügen“](./media/mam-ca-add-user-group.png)

8. <span data-ttu-id="ce4a8-121">Möglicherweise möchten Sie, dass einige Benutzer in der Benutzergruppe, die Sie im vorherigen Schritt ausgewählt haben, nicht von dieser Richtlinie betroffen sind.</span><span class="sxs-lookup"><span data-stu-id="ce4a8-121">You may want some users in the user group you selected in the previous step not to be affected by this policy.</span></span> <span data-ttu-id="ce4a8-122">In solchen Fällen fügen Sie die Gruppe der Benutzer der Liste der ausgenommenen Benutzergruppen hinzu.</span><span class="sxs-lookup"><span data-stu-id="ce4a8-122">In such cases, add the group of users to the exempted user groups list.</span></span> <span data-ttu-id="ce4a8-123">Wählen Sie auf dem Blatt **Exchange Online** **Exempted user groups** (Ausgenommene Benutzergruppen) aus.</span><span class="sxs-lookup"><span data-stu-id="ce4a8-123">From the **Exchange Online** blade, choose **Exempted user groups**.</span></span> <span data-ttu-id="ce4a8-124">Wählen Sie **Benutzergruppe hinzufügen** aus, um die Liste der Benutzergruppen zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="ce4a8-124">Choose **Add user group** to open the list of user groups.</span></span> <span data-ttu-id="ce4a8-125">Wählen Sie die Gruppen aus, die Sie von dieser Richtlinie ausnehmen möchten.</span><span class="sxs-lookup"><span data-stu-id="ce4a8-125">Select the groups you want to exempt from this policy.</span></span>

## <a name="to-modify-or-delete-user-groups-from-an-existing-app-based-ca-policy"></a><span data-ttu-id="ce4a8-126">So ändern oder löschen Sie Benutzergruppen einer vorhandenen App-basierten bedingten Zugriffsrichtlinie</span><span class="sxs-lookup"><span data-stu-id="ce4a8-126">To modify or delete user groups from an existing app-based CA policy</span></span>

1. <span data-ttu-id="ce4a8-127">Öffnen Sie das Blatt **Eingeschränkte Benutzergruppen**, und markieren Sie die Benutzergruppe, die Sie löschen möchten.</span><span class="sxs-lookup"><span data-stu-id="ce4a8-127">Open the **Restricted user groups** blade, then highlight the user group you want to delete.</span></span>
2. <span data-ttu-id="ce4a8-128">Klicken Sie auf die Auslassungspunkte, um die Optionen für den Löschvorgang anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="ce4a8-128">Click on the ellipse to see the delete options.</span></span>
3. <span data-ttu-id="ce4a8-129">Wählen Sie **Löschen** aus, um die Benutzergruppe aus der Liste zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="ce4a8-129">Choose **Delete** to remove the user group from the list.</span></span>

## <a name="create-app-based-conditional-access-policies-in-azure-ad-workload"></a><span data-ttu-id="ce4a8-130">Erstellen von App-basierten Richtlinien für den bedingten Zugriff in der Azure AD-Workload</span><span class="sxs-lookup"><span data-stu-id="ce4a8-130">Create app-based conditional access policies in Azure AD workload</span></span>

<span data-ttu-id="ce4a8-131">Ab Intune-Release 1708 können IT-Administratoren App-basierte Richtlinien für den bedingten Zugriff über die Azure AD-Workload erstellen.</span><span class="sxs-lookup"><span data-stu-id="ce4a8-131">Beginning with Intune 1708 release, IT admins can create app-based conditional access policies from the Azure AD workload.</span></span> <span data-ttu-id="ce4a8-132">Dies bietet Ihnen den Komfort, nicht zwischen den Azure- und Intune-Workloads hin und her wechseln zu müssen.</span><span class="sxs-lookup"><span data-stu-id="ce4a8-132">This gives convenience so you don't need to switch between the Azure and the Intune workloads.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ce4a8-133">Sie benötigen eine Azure AD Premium-Lizenz, um im Azure-Portal für Intune Azure AD-Richtlinien für den bedingten Zugriff zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="ce4a8-133">You need to have an Azure AD Premium license to create Azure AD conditional access policies from the Intune Azure portal.</span></span>

### <a name="to-create-an-app-based-conditional-access-policy"></a><span data-ttu-id="ce4a8-134">So erstellen Sie eine App-basierte bedingte Zugriffsrichtlinie</span><span class="sxs-lookup"><span data-stu-id="ce4a8-134">To create an app-based conditional access policy</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ce4a8-135">Bevor Sie App-basierte Richtlinien für den bedingten Zugriff verwenden, müssen Sie Ihren Apps [Intune-App-Schutzrichtlinien](app-protection-policies.md) zugewiesen haben.</span><span class="sxs-lookup"><span data-stu-id="ce4a8-135">You need to have [Intune app protection policies](app-protection-policies.md) applied to your apps before using app-based conditional access policies.</span></span>

1. <span data-ttu-id="ce4a8-136">Wählen Sie auf dem **Intune-Dashboard** die Option **Bedingter Zugriff** aus.</span><span class="sxs-lookup"><span data-stu-id="ce4a8-136">In the **Intune Dashboard**, choose **Conditional access**.</span></span>

2. <span data-ttu-id="ce4a8-137">Wählen Sie auf dem Blatt **Richtlinien** **Neue Richtlinie** aus, um die neue App-basierte Richtlinie für den bedingten Zugriff zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="ce4a8-137">In the **Policies** blade, choose **New policy** to create your new app-based conditional access policy.</span></span>

4. <span data-ttu-id="ce4a8-138">Sobald Sie einen Richtliniennamen eingegeben haben und die verfügbaren Einstellungen im Abschnitt **Zuweisungen** konfiguriert haben, wählen Sie im Abschnitt **Zugriffskontrollen** **Gewähren** aus.</span><span class="sxs-lookup"><span data-stu-id="ce4a8-138">Once you enter a policy name and configure the settings available in the **Assignments** section, then choose **Grant** under the **Access controls** section.</span></span>

5. <span data-ttu-id="ce4a8-139">Klicken Sie auf **Genehmigte Client-App erforderlich (Vorschau)**, **Auswählen** und dann auf **OK**, um die neue Richtlinie zu speichern.</span><span class="sxs-lookup"><span data-stu-id="ce4a8-139">Choose **Require approved client app**, choose **Select**, then choose **OK** to save the new policy.</span></span>

## <a name="next-steps"></a><span data-ttu-id="ce4a8-140">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="ce4a8-140">Next steps</span></span>
[<span data-ttu-id="ce4a8-141">Blockieren von Apps, die über keine moderne Authentifizierung verfügen</span><span class="sxs-lookup"><span data-stu-id="ce4a8-141">Block apps that do not have modern authentication</span></span>](app-modern-authentication-block.md)

### <a name="see-also"></a><span data-ttu-id="ce4a8-142">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="ce4a8-142">See also</span></span>

<span data-ttu-id="ce4a8-143">[Erstellen und Zuweisen von App-Schutzrichtlinien](app-protection-policies.md)
[Bedingter Zugriff im klassischen Azure-Portal](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access)</span><span class="sxs-lookup"><span data-stu-id="ce4a8-143">[Protect app data with app protection policies](app-protection-policies.md)
[Conditional Access in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access)</span></span>
