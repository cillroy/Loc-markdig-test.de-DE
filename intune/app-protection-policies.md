---
title: Erstellen und Bereitstellen von App-Schutzrichtlinien
titleSuffix: Azure portal
description: "Erfahren Sie, wie Intune-App-Schutzrichtlinien dabei helfen, Unternehmensdaten zu schützen, die von den von Ihnen verwalteten Apps verwendet werden.\""
keywords: 
author: erikre
ms.author: erikre
manager: angrobe
ms.date: 04/24/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f31b2964-e932-4cee-95c4-8d5506966c85
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 50690dadb0fe27b407d5460d5847e6703a4d6b75
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2018
---
# <a name="how-to-create-and-assign-app-protection-policies"></a><span data-ttu-id="4dfdb-103">Erstellen und Zuweisen von App-Schutzrichtlinien</span><span class="sxs-lookup"><span data-stu-id="4dfdb-103">How to create and assign app protection policies</span></span>

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

## <a name="before-you-begin"></a><span data-ttu-id="4dfdb-104">Vorbereitung</span><span class="sxs-lookup"><span data-stu-id="4dfdb-104">Before you begin</span></span>

<span data-ttu-id="4dfdb-105">Wenn Sie nach Anweisungen für das klassische Intune-Portal suchen, finden Sie weitere Informationen unter [Erstellen von App-Schutzrichtlinien](https://docs.microsoft.com/intune-classic/deploy-use/create-and-deploy-mobile-app-management-policies-with-microsoft-intune).</span><span class="sxs-lookup"><span data-stu-id="4dfdb-105">If you're looking for instructions in the Intune classic portal, see [how to create app protection policies](https://docs.microsoft.com/intune-classic/deploy-use/create-and-deploy-mobile-app-management-policies-with-microsoft-intune).</span></span>

<span data-ttu-id="4dfdb-106">App-Schutzrichtlinien können angewendet werden, unabhängig davon, ob die Geräte, auf denen die Apps ausgeführt werden, von Intune verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="4dfdb-106">App protection policies can be applied to apps running on devices that may or may not be managed by Intune.</span></span> <span data-ttu-id="4dfdb-107">Eine ausführlichere Beschreibung der Funktionsweise von App-Schutzrichtlinien und der von Intune-App-Schutzrichtlinien unterstützten Szenarien finden Sie im Thema [Was sind Microsoft Intune-App-Schutzrichtlinien](app-protection-policy.md).</span><span class="sxs-lookup"><span data-stu-id="4dfdb-107">For a more detailed description of how app protection policies work and the scenarios supported by Intune app protection policies, see [What is Microsoft Intune app protection policies](app-protection-policy.md).</span></span>

<span data-ttu-id="4dfdb-108">Wenn Sie nach einer Liste der unterstützten MAM-Apps suchen, finden Sie weitere Informationen in der [Liste der MAM-Apps](https://www.microsoft.com/cloud-platform/microsoft-intune-apps).</span><span class="sxs-lookup"><span data-stu-id="4dfdb-108">If you're looking for a list of MAM supported apps, see [MAM apps list](https://www.microsoft.com/cloud-platform/microsoft-intune-apps).</span></span>

##  <a name="create-an-app-protection-policy"></a><span data-ttu-id="4dfdb-109">Erstellen einer App-Schutzrichtlinie</span><span class="sxs-lookup"><span data-stu-id="4dfdb-109">Create an app protection policy</span></span>
1. <span data-ttu-id="4dfdb-110">Wählen Sie in der Workload **Mobile Apps** die Option **Verwalten** > **App-Schutzrichtlinien** aus.</span><span class="sxs-lookup"><span data-stu-id="4dfdb-110">In the **Mobile apps** workload, choose **Manage** > **App protection policies**.</span></span>

2. <span data-ttu-id="4dfdb-111">Hiermit wird das Blatt **App-Schutzrichtlinien** geöffnet, auf dem Sie neue Richtlinien erstellen und vorhandene bearbeiten können.</span><span class="sxs-lookup"><span data-stu-id="4dfdb-111">This opens the **App protection policies** blade, where you'll create new policies and edit existing policies.</span></span> <span data-ttu-id="4dfdb-112">Wählen Sie **Richtlinie hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="4dfdb-112">Choose **Add a policy**.</span></span>

   ![Screenshot des Blatts „Richtlinie hinzufügen“](./media/app-protection-add-policy.png)

3. <span data-ttu-id="4dfdb-114">Geben Sie einen Namen für die Richtlinie sowie eine kurze Beschreibung ein, und wählen Sie den Plattformtyp aus, um eine Richtlinie für iOS oder Android zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="4dfdb-114">Type a name for the policy, add a brief description, and select the platform type to create a policy for iOS or Android.</span></span> <span data-ttu-id="4dfdb-115">Sie können für jede Plattform mehr als eine Richtlinie erstellen.</span><span class="sxs-lookup"><span data-stu-id="4dfdb-115">You can create more than one policy for each platform.</span></span>

4. <span data-ttu-id="4dfdb-116">Wählen Sie **Apps** aus, um das Blatt **Apps** zu öffnen, auf dem eine Liste der verfügbaren Apps angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="4dfdb-116">Choose **Apps** to open the **Apps blade**, where a list of available apps is displayed.</span></span> <span data-ttu-id="4dfdb-117">Wählen Sie eine oder mehrere Apps in der Liste aus, mit denen Sie die von Ihnen zu erstellende Richtlinie verknüpfen möchten.</span><span class="sxs-lookup"><span data-stu-id="4dfdb-117">Select one or more apps from the list that you want to associate with the policy that you are creating.</span></span> <span data-ttu-id="4dfdb-118">Nachdem Sie die Apps ausgewählt haben, wählen Sie **Auswählen** unten auf dem Blatt **Apps** aus, um Ihre Auswahl zu speichern.</span><span class="sxs-lookup"><span data-stu-id="4dfdb-118">Once you have selected the apps, choose **Select** at the bottom of the **Apps** blade to save your selection.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="4dfdb-119">Sie müssen mindestens eine App auswählen, um eine Richtlinie erstellen zu können.</span><span class="sxs-lookup"><span data-stu-id="4dfdb-119">You must select at least one app to create a policy.</span></span>

5. <span data-ttu-id="4dfdb-120">Wählen Sie auf dem Blatt **Richtlinie hinzufügen** **Erforderliche Einstellungen konfigurieren** aus, um das Blatt mit den Richtlinieneinstellungen zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="4dfdb-120">On the **Add a policy blade**, choose **Configure required settings** to open the policy settings blade.</span></span>

   <span data-ttu-id="4dfdb-121">Es gibt zwei Kategorien von Richtlinieneinstellungen: **Datenverlagerung** und **Zugriff**.</span><span class="sxs-lookup"><span data-stu-id="4dfdb-121">There are two categories of policy settings, **Data relocation** and **Access**.</span></span>  <span data-ttu-id="4dfdb-122">Richtlinien für die Datenverlagerung beziehen sich auf die Datenverschiebung in und aus Apps, während mit Zugriffsrichtlinien bestimmt wird, wie der Endbenutzer auf die Apps im beruflichen Kontext zugreift.</span><span class="sxs-lookup"><span data-stu-id="4dfdb-122">Data relocation policies are applicable to data movement in and out of the apps, while the access polices determine how the end user accesses the apps in a work context.</span></span>
   <span data-ttu-id="4dfdb-123">Um Ihnen bei den ersten Schritten zu helfen, enthalten die Richtlinieneinstellung Standardwerte.</span><span class="sxs-lookup"><span data-stu-id="4dfdb-123">To get you started, the policy settings have default values.</span></span> <span data-ttu-id="4dfdb-124">Sie müssen keine Änderungen vornehmen, wenn die Standardwerte Ihren Anforderungen entsprechen.</span><span class="sxs-lookup"><span data-stu-id="4dfdb-124">You do not have to make any changes if the default values meet your requirements.</span></span>

   > [!TIP]
   > <span data-ttu-id="4dfdb-125">Diese Richtlinieneinstellungen werden nur durchgesetzt, wenn Apps im beruflichen Kontext verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="4dfdb-125">These policy settings are enforced only when using apps in the work context.</span></span>  <span data-ttu-id="4dfdb-126">Wenn der Endbenutzer die App zum Erledigen einer privaten Aufgabe verwendet, ist er von diesen Richtlinien nicht betroffen.</span><span class="sxs-lookup"><span data-stu-id="4dfdb-126">When the end user uses the app to do a personal task, they will not be affected by these policies.</span></span>



6. <span data-ttu-id="4dfdb-127">Wählen Sie **OK** aus, um diese Konfiguration zu speichern.</span><span class="sxs-lookup"><span data-stu-id="4dfdb-127">Choose **OK** to save this configuration.</span></span> <span data-ttu-id="4dfdb-128">Damit befinden Sie sich wieder auf dem Blatt **Richtlinie hinzufügen** .</span><span class="sxs-lookup"><span data-stu-id="4dfdb-128">You are now back in the **Add a policy** blade.</span></span> <span data-ttu-id="4dfdb-129">Wählen Sie **Erstellen** aus, um die Richtlinie zu erstellen und Ihre Einstellungen zu speichern.</span><span class="sxs-lookup"><span data-stu-id="4dfdb-129">Choose **Create** to create the policy and save your settings.</span></span>


<span data-ttu-id="4dfdb-130">Wenn Sie mit dem Erstellen einer Richtlinie wie im vorherigen Verfahren beschrieben fertig sind, wird sie noch nicht für Benutzer bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="4dfdb-130">When you finish creating a policy as described in the previous procedure, it is not deployed to any users.</span></span> <span data-ttu-id="4dfdb-131">Informationen zum Bereitstellen einer Richtlinie finden Sie im Abschnitt „Bereitstellen einer Richtlinie für Benutzer“.</span><span class="sxs-lookup"><span data-stu-id="4dfdb-131">To deploy a policy, see the following section, "Deploy a policy to users."</span></span>

## <a name="deploy-a-policy-to-users"></a><span data-ttu-id="4dfdb-132">Bereitstellen einer Richtlinie für Benutzer</span><span class="sxs-lookup"><span data-stu-id="4dfdb-132">Deploy a policy to users</span></span>

1. <span data-ttu-id="4dfdb-133">Wählen Sie auf dem Blatt **Richtlinie** **Benutzergruppen** aus. Damit wird das Blatt **Benutzergruppen**geöffnet.</span><span class="sxs-lookup"><span data-stu-id="4dfdb-133">In the **Policy** blade, choose  **User groups**, which opens the **User groups** blade.</span></span> <span data-ttu-id="4dfdb-134">Wählen Sie auf dem Blatt **Benutzergruppen** **Benutzergruppe hinzufügen** aus, um das Blatt **Benutzergruppe hinzufügen** zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="4dfdb-134">Choose **Add user group** in the **User groups** blade to open the **Add user group** blade.</span></span>

   ![Screenshot des Blatts „Benutzergruppen“ mit hervorgehobener Menüoption „Benutzergruppe hinzufügen“](./media/app-protection-policy-add-users.png)

2. <span data-ttu-id="4dfdb-136">Auf dem Blatt **Benutzergruppe hinzufügen** wird eine Liste der Benutzergruppen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="4dfdb-136">A list of user groups is displayed on the **Add user group** blade.</span></span> <span data-ttu-id="4dfdb-137">Dies ist eine Liste aller Sicherheitsgruppen in Ihrem **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="4dfdb-137">This is a list of all the security groups in your **Azure Active Directory**.</span></span> <span data-ttu-id="4dfdb-138">Wählen Sie die Benutzergruppen aus, auf die diese Richtlinie angewendet werden soll, und anschließend **Auswählen**.</span><span class="sxs-lookup"><span data-stu-id="4dfdb-138">Select the user groups you want this policy to apply to, and then choose **Select**.</span></span> <span data-ttu-id="4dfdb-139">Die Auswahl von **Auswählen** bewirkt die Bereitstellung der Richtlinie für Benutzer.</span><span class="sxs-lookup"><span data-stu-id="4dfdb-139">Choosing **Select**, deploys the policy to users.</span></span>
   <span data-ttu-id="4dfdb-140">![Screenshot des Blatts „Benutzergruppe hinzufügen“ mit der Liste der Azure Active Directory-Benutzer](./media/azure-ad-user-group-list.png)</span><span class="sxs-lookup"><span data-stu-id="4dfdb-140">![Screenshot of the Add user group blade showing the list of Azure Active Directory users](./media/azure-ad-user-group-list.png)</span></span>

<span data-ttu-id="4dfdb-141">Damit haben Sie eine Richtlinie erstellt und für die Benutzer bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="4dfdb-141">You have now created a policy and deployed it to users.</span></span>

<span data-ttu-id="4dfdb-142">Von der Richtlinie sind nur Benutzer betroffen, denen Microsoft Intune-Lizenzen zugewiesen wurden.</span><span class="sxs-lookup"><span data-stu-id="4dfdb-142">Only users with Microsoft Intune licenses assigned to them are affected by the policy.</span></span> <span data-ttu-id="4dfdb-143">Benutzer, die sich in der von Ihnen ausgewählten Sicherheitsgruppe befinden und nicht über eine Microsoft Intune-Lizenz verfügen, sind nicht betroffen.</span><span class="sxs-lookup"><span data-stu-id="4dfdb-143">Users who are in the security group that you selected who don’t have a Microsoft Intune license assigned to them are not affected.</span></span>

>[!IMPORTANT]
> <span data-ttu-id="4dfdb-144">Wenn Sie Intune mit Configuration Manager verwenden, um Ihre iOS- und Android-Geräte zu verwalten, wird die Richtlinie nur auf Benutzer in der Gruppe angewendet, die Sie ausgewählt haben.</span><span class="sxs-lookup"><span data-stu-id="4dfdb-144">If you are using Intune with Configuration Manager to manage your iOS and Android devices, the policy is only applied to the users directly in the group that you selected.</span></span> <span data-ttu-id="4dfdb-145">Mitglieder untergeordneter Gruppen, die in der ausgewählten Gruppe geschachtelt sind, sind nicht betroffen.</span><span class="sxs-lookup"><span data-stu-id="4dfdb-145">Members of child groups nested within the group you selected are not affected.</span></span>

<span data-ttu-id="4dfdb-146">Endbenutzer können die Apps aus dem App Store oder aus Google Play herunterladen.</span><span class="sxs-lookup"><span data-stu-id="4dfdb-146">End users can download the apps from the App store or Google Play.</span></span> <span data-ttu-id="4dfdb-147">Weitere Informationen finden Sie in folgenden Quellen:</span><span class="sxs-lookup"><span data-stu-id="4dfdb-147">For more information, see:</span></span>
* [<span data-ttu-id="4dfdb-148">Was Sie erwartet, wenn Ihre Android-App von App-Schutzrichtlinien verwaltet wird</span><span class="sxs-lookup"><span data-stu-id="4dfdb-148">What to expect when your Android app is managed by app protection policies</span></span>](app-protection-enabled-apps-android.md)
* [<span data-ttu-id="4dfdb-149">Was Sie erwartet, wenn Ihre iOS-App von App-Schutzrichtlinien verwaltet wird</span><span class="sxs-lookup"><span data-stu-id="4dfdb-149">What to expect when your iOS app is managed by app protection policies</span></span>](app-protection-enabled-apps-ios.md)

##  <a name="change-existing-policies"></a><span data-ttu-id="4dfdb-150">Ändern vorhandener Richtlinien</span><span class="sxs-lookup"><span data-stu-id="4dfdb-150">Change existing policies</span></span>
<span data-ttu-id="4dfdb-151">Sie können eine vorhandene Richtlinie bearbeiten und sie auf die als Ziel festgelegten Benutzer anwenden.</span><span class="sxs-lookup"><span data-stu-id="4dfdb-151">You can edit an existing policy and apply it to the targeted users.</span></span> <span data-ttu-id="4dfdb-152">Wenn Sie vorhandene Richtlinien ändern, werden diese Änderungen für Benutzer, die bereits bei der App angemeldet sind, jedoch in den nächsten acht Stunden nicht wirksam.</span><span class="sxs-lookup"><span data-stu-id="4dfdb-152">However, when you change existing policies,  users who are already signed  in to the apps won’t see the changes for an 8-hour period.</span></span>

<span data-ttu-id="4dfdb-153">Um die Auswirkungen der Änderungen sofort zu erfahren, muss der Endbenutzer sich bei der App abmelden und sich dann erneut anmelden.</span><span class="sxs-lookup"><span data-stu-id="4dfdb-153">To see the effect of the changes immediately, the end user will have to log out of the app, and sign back in.</span></span>

### <a name="to-change-the-list-of-apps-associated-with-the-policy"></a><span data-ttu-id="4dfdb-154">So ändern Sie die Liste der Apps, die einer Richtlinie zugeordnet sind</span><span class="sxs-lookup"><span data-stu-id="4dfdb-154">To change the list of apps associated with the policy</span></span>

1.  <span data-ttu-id="4dfdb-155">Wählen Sie auf dem Blatt **App-Richtlinie** die Richtlinie aus, die Sie ändern möchten.</span><span class="sxs-lookup"><span data-stu-id="4dfdb-155">In  the **App policy** blade, choose the policy you want to change.</span></span> <span data-ttu-id="4dfdb-156">Damit wird ein Blatt speziell für die Richtlinie geöffnet, die Sie soeben ausgewählt haben.</span><span class="sxs-lookup"><span data-stu-id="4dfdb-156">This opens a blade specific to the policy you just selected.</span></span>

2.  <span data-ttu-id="4dfdb-157">Wählen Sie auf diesem Richtlinienblatt **Ziel-Apps** aus, um eine Liste der Apps zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="4dfdb-157">In the policy blade, choose **Targeted apps** to open the list of apps.</span></span>

3.  <span data-ttu-id="4dfdb-158">Fügen Sie der Liste Apps hinzu, oder entfernen Sie Apps hieraus, und wählen Sie dann das Symbol **Speichern** aus, um die Änderungen zu speichern.</span><span class="sxs-lookup"><span data-stu-id="4dfdb-158">Remove or add apps from the list and choose the **Save** icon to save your changes.</span></span>

### <a name="to-change-the-list-of-user-groups"></a><span data-ttu-id="4dfdb-159">So ändern Sie die Liste der Benutzergruppen</span><span class="sxs-lookup"><span data-stu-id="4dfdb-159">To change the list of user groups</span></span>

1.  <span data-ttu-id="4dfdb-160">Wählen Sie auf dem Blatt **App-Richtlinie** die Richtlinie aus, die Sie ändern möchten.</span><span class="sxs-lookup"><span data-stu-id="4dfdb-160">In  the **App policy** blade, choose the policy you want to change.</span></span> <span data-ttu-id="4dfdb-161">Damit wird ein Blatt speziell für die Richtlinie geöffnet, die Sie soeben ausgewählt haben.</span><span class="sxs-lookup"><span data-stu-id="4dfdb-161">This opens the blade specific to the policy you selected.</span></span>

2.  <span data-ttu-id="4dfdb-162">Wählen Sie auf dem Richtlinienblatt **Benutzergruppen** aus, um das Blatt **Benutzergruppe** zu öffnen, auf dem die Liste der Benutzergruppen angezeigt wird, auf die die Richtlinie gegenwärtig angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="4dfdb-162">In the policy blade, choose **User groups** to open the **User group** blade that shows the list of current user groups who have this policy.</span></span>

3.  <span data-ttu-id="4dfdb-163">Zum Hinzufügen einer neuen Benutzergruppe wählen Sie **Benutzergruppe hinzufügen** und anschließend die Benutzergruppe aus.</span><span class="sxs-lookup"><span data-stu-id="4dfdb-163">To add a new user group to the policy, choose **Add user group**, and select the user group.</span></span> <span data-ttu-id="4dfdb-164">Wählen Sie **Auswählen** aus, um die Richtlinie für die ausgewählte Gruppe bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="4dfdb-164">Choose **Select** to deploy the policy to the group you selected.</span></span>

4.  <span data-ttu-id="4dfdb-165">Zum Löschen einer Benutzergruppe markieren Sie die Benutzergruppe, die Sie entfernen möchten.</span><span class="sxs-lookup"><span data-stu-id="4dfdb-165">To delete a user group, highlight the user group you want to remove.</span></span> <span data-ttu-id="4dfdb-166">Anschließend wählen Sie die Auslassungspunkte (...) und die Option **Löschen** aus, um die Benutzergruppe zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="4dfdb-166">Then choose the ellipses (…), and choose **Delete** to remove the user group.</span></span>
  <span data-ttu-id="4dfdb-167">![Screenshot mit Löschoption](./media/app-protection-policy-delete-user.png)</span><span class="sxs-lookup"><span data-stu-id="4dfdb-167">![Screenshot showing Delete option ](./media/app-protection-policy-delete-user.png)</span></span>

### <a name="to-change-policy-settings"></a><span data-ttu-id="4dfdb-168">So ändern Sie Richtlinieneinstellungen</span><span class="sxs-lookup"><span data-stu-id="4dfdb-168">To change policy settings</span></span>

1.  <span data-ttu-id="4dfdb-169">Wählen Sie auf dem Blatt **App-Richtlinie** die Richtlinie aus, die Sie ändern möchten.</span><span class="sxs-lookup"><span data-stu-id="4dfdb-169">In the **App policy** blade, choose the policy you want to change.</span></span> <span data-ttu-id="4dfdb-170">Damit wird ein Blatt speziell für die Richtlinie geöffnet, die Sie soeben ausgewählt haben.</span><span class="sxs-lookup"><span data-stu-id="4dfdb-170">This opens a blade specific to the policy you just selected.</span></span>


2.  <span data-ttu-id="4dfdb-171">Wählen Sie **Richtlinieneinstellungen** aus, um das Blatt **Richtlinieneinstellungen** zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="4dfdb-171">Choose **Policy settings** to open the **Policy settings** blade.</span></span>

3.  <span data-ttu-id="4dfdb-172">Ändern Sie die Einstellungen, und wählen Sie das Symbol **Speichern** aus, um die Änderungen zu speichern.</span><span class="sxs-lookup"><span data-stu-id="4dfdb-172">Change the settings, and choose the **Save** icon to save your changes.</span></span>

## <a name="policy-settings"></a><span data-ttu-id="4dfdb-173">Richtlinieneinstellungen</span><span class="sxs-lookup"><span data-stu-id="4dfdb-173">Policy settings</span></span>
<span data-ttu-id="4dfdb-174">Eine vollständige Liste der Richtlinieneinstellungen für iOS und Android finden Sie in den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="4dfdb-174">To see a full list of the policy settings for iOS and Android, select one of the following:</span></span>

- [<span data-ttu-id="4dfdb-175">iOS-Richtlinien</span><span class="sxs-lookup"><span data-stu-id="4dfdb-175">iOS policies</span></span>](app-protection-policy-settings-ios.md)
- [<span data-ttu-id="4dfdb-176">Android-Richtlinien</span><span class="sxs-lookup"><span data-stu-id="4dfdb-176">Android policies</span></span>](app-protection-policy-settings-android.md)

## <a name="next-steps"></a><span data-ttu-id="4dfdb-177">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="4dfdb-177">Next steps</span></span>
[<span data-ttu-id="4dfdb-178">Überwachen der Verwaltungsrichtlinien für mobile Apps mit Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="4dfdb-178">Monitor compliance and user status</span></span>](app-protection-policies-monitor.md)

### <a name="see-also"></a><span data-ttu-id="4dfdb-179">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="4dfdb-179">See also</span></span>
* [<span data-ttu-id="4dfdb-180">Was Sie erwartet, wenn Ihre Android-App von App-Schutzrichtlinien verwaltet wird</span><span class="sxs-lookup"><span data-stu-id="4dfdb-180">What to expect when your Android app is managed by app protection policies</span></span>](app-protection-enabled-apps-android.md)
* [<span data-ttu-id="4dfdb-181">Was Sie erwartet, wenn Ihre iOS-App von App-Schutzrichtlinien verwaltet wird</span><span class="sxs-lookup"><span data-stu-id="4dfdb-181">What to expect when your iOS app is managed by app protection policies</span></span>](app-protection-enabled-apps-ios.md)
