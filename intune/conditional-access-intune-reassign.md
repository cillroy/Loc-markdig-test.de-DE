---
title: "Migrieren von Richtlinien für bedingten Zugriff über das klassische Intune-Porta zum Azure-Portal"
titlesuffix: Azure portal
description: "Migrieren von Richtlinien für bedingten Zugriff über das klassische Intune-Porta zum Azure-Portal"
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 06/28/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 301159ad-5f7e-4fcc-86c7-f72a71701ff4
ms.reviewer: chrisgree
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 18ee7adcdb396c1b7010100803c82dbf0daa767c
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2017
---
# <a name="reassign-conditional-access-policies-from-intune-classic-portal-to-the-azure-portal"></a><span data-ttu-id="151a7-103">Erneutes Zuweisen von Richtlinien für bedingten Zugriff über das klassische Intune-Porta zum Azure-Portal</span><span class="sxs-lookup"><span data-stu-id="151a7-103">Reassign conditional access policies from Intune classic portal to the Azure portal</span></span>

<span data-ttu-id="151a7-104">Ab dem neuen Azure-Portal bietet der bedingt Zugriff Unterstützung für mehrere Richtlinien pro Anwendung zusammen mit erweiterter Anpassbarkeit.</span><span class="sxs-lookup"><span data-stu-id="151a7-104">Starting in the new Azure portal, conditional access offers support for multiple policies per application, along with more customizability.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="151a7-105">Vorbereitung</span><span class="sxs-lookup"><span data-stu-id="151a7-105">Before you begin</span></span>

<span data-ttu-id="151a7-106">Wenn Sie bereit für das Azure-Portal sind, befolgen Sie die in diesem Thema angegebenen Schritte, um die Richtlinien des bedingten Zugriffs, die Sie zuvor im klassischen Intune-Portal erstellt haben, erneut zuzuweisen:</span><span class="sxs-lookup"><span data-stu-id="151a7-106">If you’re ready to move to the Azure portal, follow the steps in this topic to reassign the conditional access policies you previously created in the Intune classic portal:</span></span>

- <span data-ttu-id="151a7-107">Sammeln Sie die Richtlinien für bedingten Zugriff, die zuvor erstellt wurden, damit Sie wissen, welche Einstellungen Sie für die spätere Neuzuweisung benötigen.</span><span class="sxs-lookup"><span data-stu-id="151a7-107">Gather the conditional access policies previously created, so you know what settings you need to reassign later.</span></span>

- <span data-ttu-id="151a7-108">Führen Sie die Schritte in diesem Thema aus, um diese Richtlinien im Azure-Portal neu zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="151a7-108">Follow the steps in this topic to re-create these policies in the Azure portal.</span></span>

- <span data-ttu-id="151a7-109">Deaktivieren Sie die bedingten Richtlinien im klassischen Intune-Portal, nachdem Sie überprüft haben, ob die neuen Richtlinien im Azure-Portal wie erwartet funktionieren.</span><span class="sxs-lookup"><span data-stu-id="151a7-109">Disable the conditional policies in the Intune classic portal, after you have verified that the new policies are working as expected in the Azure portal.</span></span>
<br /><br />
    - <span data-ttu-id="151a7-110">**Vor dem Deaktivieren** der Richtlinien für bedingten Zugriff im klassischen Intune-Portal, planen Sie, wie Sie Benutzer zur neuen Richtlinie verschieben.</span><span class="sxs-lookup"><span data-stu-id="151a7-110">**Before you disable** the conditional access policies in the Intune classic portal, plan how you'll move users over to the new policy.</span></span> <span data-ttu-id="151a7-111">Es gibt zwei Ansätze:</span><span class="sxs-lookup"><span data-stu-id="151a7-111">There are two approaches:</span></span>
<br /><br />
        - <span data-ttu-id="151a7-112">**Verwenden Sie dieselbe Einschlussgruppe, um die im Azure-Portal erstellten Richtlinien anzuwenden, und erstellen Sie eine neue Ausnahmegruppe, die mit den vom klassischen Intune-Portal angewendeten Richtlinien verwendet wird**.</span><span class="sxs-lookup"><span data-stu-id="151a7-112">**Use the same inclusion group to apply policies created in the Azure portal, and create a new exemption group to use with the policies applied by the Intune classic portal**.</span></span>
            - <span data-ttu-id="151a7-113">Verschieben Sie einige Benutzer allmählich in die Ausnahmegruppe, die im klassischen Portal angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="151a7-113">Gradually move some users into the exemption group specified in the classic portal.</span></span> <span data-ttu-id="151a7-114">Dies verhindert, dass die Richtlinien, die das Ziel des klassischen Intune-Portals sind, angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="151a7-114">This prevents the policies targeted by the Intune classic portal from being applied.</span></span> <span data-ttu-id="151a7-115">Die Richtlinien, die für die gleiche Benutzergruppe im Azure-Portal erstellt wurden und konzipiert sind, werden zusätzlich zu den im klassischen Intune-Portal angewendeten Richtlinien angewendet.</span><span class="sxs-lookup"><span data-stu-id="151a7-115">The policies created and targeted to the same user group in the Azure portal are applied, in addition to the ones applied in the Intune classic portal.</span></span> 
<br /><br />
        - <span data-ttu-id="151a7-116">**Erstellen Sie eine neue Gruppe für Richtlinien für bedingten Zugriff im Azure-Portal**.</span><span class="sxs-lookup"><span data-stu-id="151a7-116">**Create a new group to target the conditional access policies in the Azure portal**.</span></span> <span data-ttu-id="151a7-117">Wenn Sie sich für diese Vorgehensweise entscheiden, müssen Sie folgende Aktionen ausführen:</span><span class="sxs-lookup"><span data-stu-id="151a7-117">If you choose this approach, you need to do the following:</span></span>
            - <span data-ttu-id="151a7-118">Entfernen Sie Benutzer allmählich aus den Sicherheitsgruppen, die speziell für das klassische Intune-Portal Richtlinien für bedingten Zugriff besitzen.</span><span class="sxs-lookup"><span data-stu-id="151a7-118">Gradually remove users from the security groups that have conditional access policies targeted to them in the Intune classic portal.</span></span>
            - <span data-ttu-id="151a7-119">Nachdem Sie bestätigt haben, dass die neue Richtlinie für diese Benutzer funktioniert, können Sie die Richtlinie im klassischen Intune-Portal deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="151a7-119">After you have confirmed the new policy is working for those users, you can disable the policy in the Intune classic portal.</span></span> 
<br /><br />
- <span data-ttu-id="151a7-120">Wenn Sie die Einstellungen für die Richtlinien für den bedingten Zugriff konfiguriert haben, um Exchange Active Sync (EAS) im klassischen Intune-Portal zu verwenden, gehen Sie zu den [Anweisungen in diesem Thema](#to-reassign-intune-device-based-conditional-access-policies-for-eas-clients), um **die Einstellungen der Richtlinie für bedingten Zugriff für EAS im Azure-Portal erneut zuzuweisen**.</span><span class="sxs-lookup"><span data-stu-id="151a7-120">If you have your conditional access policy settings configured to use Exchange ActiveSync (EAS) in the Intune classic portal, see the [instructions in this topic](#to-reassign-intune-device-based-conditional-access-policies-for-eas-clients) to **reassign EAS conditional access policy settings in the Azure portal**.</span></span>

### <a name="to-verify-your-device-based-conditional-access-policies-in-the-intune-classic-portal"></a><span data-ttu-id="151a7-121">So überprüfen Sie Ihre Richtlinien für den gerätebasierten bedingten Zugriff im klassischen Intune-Portal</span><span class="sxs-lookup"><span data-stu-id="151a7-121">To verify your device-based conditional access policies in the Intune classic portal</span></span>

1.  <span data-ttu-id="151a7-122">Wechseln Sie zum [klassischen Intune-Portal](https://manage.microsoft.com), und melden Sie sich mit Ihren Anmeldeinformationen an.</span><span class="sxs-lookup"><span data-stu-id="151a7-122">Go to the [Intune classic portal](https://manage.microsoft.com), and sign in with your credentials.</span></span>

2.  <span data-ttu-id="151a7-123">Wählen Sie **Richtlinie** im linken Menü aus.</span><span class="sxs-lookup"><span data-stu-id="151a7-123">Choose **Policy** from the left menu.</span></span>

3.  <span data-ttu-id="151a7-124">Wählen Sie **Bedingter Zugriff** aus und anschließend den Microsoft-Clouddienst (z.B. Exchange Online oder SharePoint Online), für den Sie eine Richtlinie für bedingten Zugriff erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="151a7-124">Choose **Conditional access**, and then select the Microsoft cloud service (for example, Exchange Online or SharePoint Online) you created a conditional access policy for.</span></span>

4.  <span data-ttu-id="151a7-125">Notieren Sie sich die Einstellungen für den bedingten Zugriff, und beziehen Sie sich auf diese Notizen, wenn Sie die gleichen Richtlinien für bedingten Zugriff im Azure-Portal erstellen.</span><span class="sxs-lookup"><span data-stu-id="151a7-125">Take note of your conditional access settings, and refer to these when you create the same conditional access policies in the Azure portal.</span></span>

### <a name="app-and-device-based-conditional-access-policies-working-together"></a><span data-ttu-id="151a7-126">Richtlinien für den App- und gerätebasierten bedingten Zugriffs, die zusammen arbeiten</span><span class="sxs-lookup"><span data-stu-id="151a7-126">App and device-based conditional access policies working together</span></span>

<span data-ttu-id="151a7-127">Das Blatt **Intune-App-Schutz** im Azure-Portal erlaubt Administratoren, App-basierte bedingte Regeln festzulegen, sodass nur Apps, die die App-Schutzrichtlinien von Intune unterstützen, auf Unternehmensressourcen zugreifen dürfen.</span><span class="sxs-lookup"><span data-stu-id="151a7-127">The **Intune App Protection** blade in the Azure portal enables admins to set app-based conditional rules so that only apps that support the Intune app protection policies are allowed access to corporate resources.</span></span> <span data-ttu-id="151a7-128">Sie können diese Richtlinien für den App-basierten bedingten Zugriff mithilfe von Richtlinien für den gerätebasierten bedingten Zugriff überlappen.</span><span class="sxs-lookup"><span data-stu-id="151a7-128">You can choose to overlap these app-based conditional access policies by using device-based conditional access policies.</span></span> <span data-ttu-id="151a7-129">Sie können die gerätebasierte und App-basierte bedingte Richtlinie kombinieren (logischer UND-Vorgang) oder eine Option bereitstellen (logischer ODER-Vorgang).</span><span class="sxs-lookup"><span data-stu-id="151a7-129">You can combine the device-based and app-based conditional policies (logical AND), or you can provide either option (logical OR).</span></span> <span data-ttu-id="151a7-130">Wenn die Anforderungen für Ihre Richtlinie für den bedingten Zugriffs Folgende sind:</span><span class="sxs-lookup"><span data-stu-id="151a7-130">If your conditional access policy requirements are to:</span></span>

- <span data-ttu-id="151a7-131">Ein kompatibles Gerät **UND** die Verwendung der genehmigten App sind erforderlich.</span><span class="sxs-lookup"><span data-stu-id="151a7-131">Require a compliant device **AND** use the approved app.</span></span>
    - <span data-ttu-id="151a7-132">Sie müssen Ihre Richtlinie für den bedingten Zugriff mithilfe des [Blatts des bedingten Zugriffs von Azure Active Directory](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies) und des [Blatts des Intune-App-Schutzes](https://portal.azure.com/#blade/Microsoft_Intune/SummaryBlade/0) festlegen.</span><span class="sxs-lookup"><span data-stu-id="151a7-132">You should set your conditional access policy by using the [Azure Active Directory conditional access blade](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies) and the [Intune App Protection blade](https://portal.azure.com/#blade/Microsoft_Intune/SummaryBlade/0).</span></span>
<br /><br />
- <span data-ttu-id="151a7-133">Ein kompatibles Gerät **ODER** die Verwendung der genehmigten App sind erforderlich.</span><span class="sxs-lookup"><span data-stu-id="151a7-133">Require a compliant device **OR** use the approved app.</span></span>
    - <span data-ttu-id="151a7-134">Sie müssen Ihre Richtlinie für den bedingten Zugriff mithilfe des [klassischen Intune-Portals](https://manage.microsoft.com) und dem [Blatt des Intune-App-Schutzes](https://portal.azure.com/#blade/Microsoft_Intune/SummaryBlade/0) festlegen.</span><span class="sxs-lookup"><span data-stu-id="151a7-134">You should set your conditional access policy by using the [Intune classic portal](https://manage.microsoft.com) and the [Intune App Protection blade](https://portal.azure.com/#blade/Microsoft_Intune/SummaryBlade/0).</span></span>

> [!TIP] 
> <span data-ttu-id="151a7-135">Dieses Thema enthält Screenshots, die die Benutzererfahrung im klassischen Intune-Portal und dem Azure-Portal vergleichen.</span><span class="sxs-lookup"><span data-stu-id="151a7-135">This topic provides screenshots comparing the user experience in both the Intune classic portal and the Azure portal.</span></span>

## <a name="reassign-intune-device-based-conditional-access-policies"></a><span data-ttu-id="151a7-136">Erneutes Zuweisen von Richtlinien für den gerätebasierten bedingten Zugriff für Intune</span><span class="sxs-lookup"><span data-stu-id="151a7-136">Reassign Intune device-based conditional access policies</span></span>

1. <span data-ttu-id="151a7-137">Wechseln Sie zum [bedingten Zugriff im Azure-Portal](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies), und melden Sie sich mit Ihren Anmeldeinformationen an.</span><span class="sxs-lookup"><span data-stu-id="151a7-137">Go to [Conditional access in the Azure portal](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies), and sign in with your credentials.</span></span>

2. <span data-ttu-id="151a7-138">Wählen Sie **Neue Richtlinie** aus.</span><span class="sxs-lookup"><span data-stu-id="151a7-138">Choose **New policy**.</span></span>

3. <span data-ttu-id="151a7-139">Geben Sie einen Namen für die Richtlinie an.</span><span class="sxs-lookup"><span data-stu-id="151a7-139">Provide a name for the policy.</span></span>

4. <span data-ttu-id="151a7-140">Wählen Sie **Benutzer und Gruppen** unter dem **Abschnitt Zuweisungen** für die neue Richtlinie für den bedingten Zugriff aus.</span><span class="sxs-lookup"><span data-stu-id="151a7-140">Under the **Assignments section**, choose **Users and groups** to target the new conditional access policy.</span></span>
    
    ![Vergleich der Benutzergruppen-Benutzeroberfläche zwischen den Portalen Intune und Azure](./media/reassign-ca-1.png)

    > [!IMPORTANT] 
    > <span data-ttu-id="151a7-142">Diese Auswahl, die Sie für das Azure-Portal treffen, muss mit der Auswahl übereinstimmen, die Sie bereits für das klassische Portal getroffen haben.</span><span class="sxs-lookup"><span data-stu-id="151a7-142">The selection you make for the Azure portal should correspond to the selection you made for the Classic portal.</span></span> <span data-ttu-id="151a7-143">Wenn Sie z.B. alle Benutzer im klassischen Intune-Portal ausgewählt haben, wählen Sie im Azure-Portal **Alle Benutzer** aus.</span><span class="sxs-lookup"><span data-stu-id="151a7-143">For example, if you have all users selected in the Intune classic portal, select **All users** in the Azure portal.</span></span> <span data-ttu-id="151a7-144">Wenn Sie darüber hinaus die Option **Ausgenommene Gruppen** im klassischen Intune-Portal ausgewählt haben, schließen Sie diese ausgewählten Gruppen im Azure-Portal aus.</span><span class="sxs-lookup"><span data-stu-id="151a7-144">Additionally, if you’ve chosen the **Exempt groups** option in the Intune classic portal, also exclude those select groups in the Azure portal.</span></span>

5. <span data-ttu-id="151a7-145">Nachdem Sie Ihre Gruppe ausgewählt haben, wählen Sie **Auswählen** aus, und klicken Sie dann auf **Fertig**.</span><span class="sxs-lookup"><span data-stu-id="151a7-145">After you choose your group, click **Select**, and then click **Done**.</span></span>

6. <span data-ttu-id="151a7-146">Wählen Sie **Cloud-Apps** unter dem Abschnitt **Zuweisungen** aus.</span><span class="sxs-lookup"><span data-stu-id="151a7-146">Under the **Assignments** section, choose **Cloud apps**.</span></span>

7. <span data-ttu-id="151a7-147">Wählen Sie auf dem **Cloud-Apps**-Blatt **Apps auswählen** aus.</span><span class="sxs-lookup"><span data-stu-id="151a7-147">On the **Cloud apps** blade, choose **Select apps**.</span></span>

8. <span data-ttu-id="151a7-148">Wählen Sie die App, für die Sie die neue Richtlinie für bedingten Zugriff anwenden möchten, und klicken Sie auf **Auswählen**.</span><span class="sxs-lookup"><span data-stu-id="151a7-148">Choose the app you want to apply the new conditional access policy to, and click **Select**.</span></span>

9. <span data-ttu-id="151a7-149">Klicken Sie auf **Fertig**.</span><span class="sxs-lookup"><span data-stu-id="151a7-149">Click **Done**.</span></span>

    ![Vergleich der Cloud-App-Benutzeroberfläche zwischen den Portalen Intune und Azure](./media/reassign-ca-3.png)

    > [!TIP] 
    > <span data-ttu-id="151a7-151">Wenn Sie mehrere Apps mit derselben Richtlinie haben, ziehen Sie in Betracht, sie in einer einzelnen Richtlinie im Azure-Portal zu konsolidieren.</span><span class="sxs-lookup"><span data-stu-id="151a7-151">If you have multiple apps with the same policy, consider consolidating them into a single policy in the Azure portal.</span></span>

10. <span data-ttu-id="151a7-152">Wählen Sie **Bedingungen** unter dem Abschnitt **Zuweisungen** aus.</span><span class="sxs-lookup"><span data-stu-id="151a7-152">Under the **Assignments** section, choose **Conditions**.</span></span>

11. <span data-ttu-id="151a7-153">Wählen Sie auf dem Blatt **Bedingungen** die Option **Geräteplattformen** aus, dann wählen Sie die zutreffende Geräteplattform aus.</span><span class="sxs-lookup"><span data-stu-id="151a7-153">On the **Conditions** blade, choose **Device platforms**, and then choose the applicable device platforms.</span></span>

12. <span data-ttu-id="151a7-154">Sobald Sie damit fertig sind, klicken Sie zweimal auf **Fertig**.</span><span class="sxs-lookup"><span data-stu-id="151a7-154">When you are finished choosing the device platforms, click **Done** twice.</span></span>

    ![Vergleich der Geräteplattform-Benutzeroberfläche zwischen den Portalen Intune und Azure](./media/reassign-ca-4.png)

    > [!TIP] 
    > <span data-ttu-id="151a7-156">Wenn Sie einzelne Plattformen im klassischen Intune-Portal ausgewählt haben, wählen Sie die einzelnen Plattformen im Azure-Portal aus.</span><span class="sxs-lookup"><span data-stu-id="151a7-156">If you have chosen individual platforms in the Intune classic portal, choose the individual platforms in the Azure portal.</span></span>

    > [!NOTE] 
    > <span data-ttu-id="151a7-157">Sie können später den Domänenbeitritt oder kompatible Optionen für Windows angeben.</span><span class="sxs-lookup"><span data-stu-id="151a7-157">You can specify the domain join or compliant options for Windows later.</span></span>

13. <span data-ttu-id="151a7-158">Wählen Sie **Bedingungen** unter dem Abschnitt **Zuweisungen** aus.</span><span class="sxs-lookup"><span data-stu-id="151a7-158">Under the **Assignments** section, choose **Conditions**.</span></span>

14. <span data-ttu-id="151a7-159">Wählen Sie auf dem Blatt **Bedingungen** **Client-Apps** aus, wählen Sie dann die zutreffende Client-App aus.</span><span class="sxs-lookup"><span data-stu-id="151a7-159">On the **Conditions** blade, choose **Client apps**, and then choose the applicable client app.</span></span>

15. <span data-ttu-id="151a7-160">Sobald Sie damit fertig sind, klicken Sie auf zweimal auf **Fertig**.</span><span class="sxs-lookup"><span data-stu-id="151a7-160">When you have finished choosing the client app, click **Done** twice.</span></span>

    ![Vergleich der Client-Apps-Benutzeroberfläche zwischen den Portalen Intune und Azure](./media/reassign-ca-6.png)

16. <span data-ttu-id="151a7-162">Wenn Sie die Browsereinstellungen im klassischen Intune-Portal ausgewählt haben, wählen Sie jeweils **Browser** und **Mobile Apps und Desktopclients** im Azure-Portal aus.</span><span class="sxs-lookup"><span data-stu-id="151a7-162">If you have chosen the browser settings in the Intune classic portal, select both **Browser** and **Mobile apps and desktop clients** in the Azure portal.</span></span> <span data-ttu-id="151a7-163">Wählen Sie für den Fall, dass Sie nicht die Browsereinstellungen im klassischen Intune-Portal ausgewählt haben, nur **Mobile Apps und Desktopclients** aus.</span><span class="sxs-lookup"><span data-stu-id="151a7-163">In case you have not chosen the browser settings in the Intune classic portal, choose **Mobile apps and desktop clients** only.</span></span> 

17. <span data-ttu-id="151a7-164">Wählen Sie im Abschnitt **Zugriffssteuerung** die Option **Grant** (Gewähren) aus.</span><span class="sxs-lookup"><span data-stu-id="151a7-164">Under the **Access controls** section, choose **Grant**.</span></span>

18. <span data-ttu-id="151a7-165">Wählen Sie **Markieren des Geräts als kompatibel erforderlich** unter **Grant Access Controls** (Zugriffssteuerungen gewähren) aus, klicken Sie dann auf **Auswählen**.</span><span class="sxs-lookup"><span data-stu-id="151a7-165">Under **Grant Access Controls**, choose **Require device to be marked as compliant**, and then click **Select**.</span></span>

19. <span data-ttu-id="151a7-166">Wenn Sie eine Richtlinie besitzen, die mit einer Domäne verknüpfte Windows-Geräte erfordert, und Sie auch in Intune registrierte und mit Windows kompatible Geräte zulassen, wählen Sie **In Domäne eingebundenes Gerät anfordern** und **Markieren des Geräts als kompatibel erforderlich** zusammen mit **Eine der ausgewählten Kontrollen anfordern** aus.</span><span class="sxs-lookup"><span data-stu-id="151a7-166">If you have a policy to require domain joined Windows devices, and you also allow Intune-enrolled and compliant Windows devices, choose **Require domain joined device** and **Require device to be marked as compliant**, along with **Require one of the selected controls**.</span></span>

20. <span data-ttu-id="151a7-167">Wenn Sie keine mit Intune registrierten und mit Windows kompatiblen Geräte erlauben, schließen Sie Windows-Richtlinien von der aktuellen Richtlinie aus.</span><span class="sxs-lookup"><span data-stu-id="151a7-167">If you do not allow Intune enrolled and compliant Windows devices, exempt the Windows policy from the current policy.</span></span> <span data-ttu-id="151a7-168">Erstellen Sie anschließend eine separate Richtlinie, für die **Geräteplattformen** auf **Windows** festgelegt sind, einschließlich der anderen Bedingungen, die wie oben festgelegt sind. Wählen Sie dann **In Domäne eingebundenes Gerät anfordern** unter **Grant Access Controls** (Zugriffssteuerungen genehmigen) aus.</span><span class="sxs-lookup"><span data-stu-id="151a7-168">Then create a separate policy with **Device platforms** set to **Windows**, include the other conditions as set per above, and choose **Require domain joined device** under **Grant Access Controls**.</span></span>

21. <span data-ttu-id="151a7-169">Aktivieren Sie die Umschaltfläche **Richtlinie aktivieren** auf dem Blatt **Neu** der Richtlinie für den bedingten Zugriff, klicken Sie dann auf **Erstellen**.</span><span class="sxs-lookup"><span data-stu-id="151a7-169">On the **New** conditional access policy blade, turn on the **Enable policy** toggle, and then click **Create**.</span></span>

    ![Zulassen des Vergleichs der Benutzeroberfläche für die Richtlinie für bedingten Zugriff zwischen den Portalen Intune und Azure](./media/reassign-ca-11.png)

## <a name="reassign-intune-device-based-conditional-access-policies-for-eas-clients"></a><span data-ttu-id="151a7-171">Erneutes Zuweisen von Richtlinien für den gerätebasierten bedingten Zugriff für EAS-Clients für Intune</span><span class="sxs-lookup"><span data-stu-id="151a7-171">Reassign Intune device-based conditional access policies for EAS clients</span></span>

<span data-ttu-id="151a7-172">Wenn Sie Exchange Active Sync-Einstellungen als Teil einer Exchange Online-Richtlinie im klassischen Intune-Portal konfiguriert haben, müssen Sie eine zweite Richtlinie für den bedingten Zugriff im Azure-Portal erstellen.</span><span class="sxs-lookup"><span data-stu-id="151a7-172">If you have configured Exchange ActiveSync settings as part of an Exchange Online policy in the Intune classic portal, you need to create a second conditional access policy in the Azure portal.</span></span>

1. <span data-ttu-id="151a7-173">Wechseln Sie zum [bedingten Zugriff im Azure-Portal](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies), und melden Sie sich mit Ihren Anmeldeinformationen an.</span><span class="sxs-lookup"><span data-stu-id="151a7-173">Go to [Conditional access in the Azure portal](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies), and sign in with your credentials.</span></span>

2. <span data-ttu-id="151a7-174">Wählen Sie **Neue Richtlinie** aus.</span><span class="sxs-lookup"><span data-stu-id="151a7-174">Choose **New policy**.</span></span>

3. <span data-ttu-id="151a7-175">Geben Sie einen Namen für die Richtlinie an.</span><span class="sxs-lookup"><span data-stu-id="151a7-175">Provide a name for the policy.</span></span>

4. <span data-ttu-id="151a7-176">Wählen Sie **Benutzer und Gruppen** unter dem Abschnitt **Zuweisungen** für die neue Richtlinie für den bedingten Zugriff aus.</span><span class="sxs-lookup"><span data-stu-id="151a7-176">Under the **Assignments** section, choose **Users and groups** to target the new conditional access policy.</span></span>

    ![Vergleich der Benutzergruppen-Benutzeroberfläche zwischen den Portalen Intune und Azure](./media/reassign-ca-12.png)

    > [!IMPORTANT] 
    > <span data-ttu-id="151a7-178">Diese Auswahl, die Sie für das Azure-Portal treffen, muss mit der Auswahl übereinstimmen, die Sie bereits für das Azure-Portal getroffen haben.</span><span class="sxs-lookup"><span data-stu-id="151a7-178">The selection you make for the Azure portal should correspond to the selection you made for the Azure portal.</span></span> <span data-ttu-id="151a7-179">Wenn Sie z.B. alle Benutzer im klassischen Intune-Portal ausgewählt haben, wählen Sie im Azure-Portal **Alle Benutzer** aus.</span><span class="sxs-lookup"><span data-stu-id="151a7-179">For example, if you have all users selected in the Intune classic portal, select **All users** in the Azure portal.</span></span> <span data-ttu-id="151a7-180">Wenn Sie darüber hinaus die Option **Ausgenommene Gruppen** im klassischen Intune-Portal ausgewählt haben, schließen Sie diese ausgewählten Gruppen im Azure-Portal aus.</span><span class="sxs-lookup"><span data-stu-id="151a7-180">Additionally, if you’ve chosen the **Exempt groups** option in the Intune classic portal, also exclude those select groups in the Azure portal.</span></span>

5. <span data-ttu-id="151a7-181">Nachdem Sie Ihre Gruppe ausgewählt haben, wählen Sie **Auswählen** aus, und klicken Sie dann auf **Fertig**.</span><span class="sxs-lookup"><span data-stu-id="151a7-181">After you choose your group, click **Select**, and then click **Done**.</span></span>

6. <span data-ttu-id="151a7-182">Wählen Sie **Cloud-Apps** unter dem Abschnitt **Zuweisungen** aus.</span><span class="sxs-lookup"><span data-stu-id="151a7-182">Under the **Assignments** section, choose **Cloud apps**.</span></span>

7. <span data-ttu-id="151a7-183">Klicken Sie auf dem Blatt **Cloud-Apps** auf **Apps auswählen**, und wählen Sie **Exchange Online** aus.</span><span class="sxs-lookup"><span data-stu-id="151a7-183">On the **Cloud apps** blade, click **Select apps**, and choose **Exchange Online**.</span></span> <span data-ttu-id="151a7-184">Klicken Sie dann auf **Auswählen** und **Fertig**.</span><span class="sxs-lookup"><span data-stu-id="151a7-184">Then click **Select** and **Done**.</span></span>

    ![Vergleich der Cloud-Apps-Benutzeroberfläche zwischen den Portalen Intune und Azure](./media/reassign-ca-14.png)

    > [!IMPORTANT] 
    > <span data-ttu-id="151a7-186">Bedingte Zugriffsrichtlinien für EAS-Clients können keine andere Cloud-App enthalten.</span><span class="sxs-lookup"><span data-stu-id="151a7-186">Conditional access policies for EAS clients cannot include any other cloud app.</span></span>

8. <span data-ttu-id="151a7-187">Wählen Sie auf dem Blatt **Bedingungen** **Client-Apps** aus, wählen Sie dann die zutreffende Client-App aus.</span><span class="sxs-lookup"><span data-stu-id="151a7-187">On the **Conditions** blade, choose **Client apps**, and then choose the applicable client app.</span></span> <span data-ttu-id="151a7-188">Wenn Sie Clients blockieren möchten, die nicht von Intune unterstützt werden, verwenden Sie die Option **Richtlinie nur auf unterstützte Plattformen anwenden**.</span><span class="sxs-lookup"><span data-stu-id="151a7-188">If you have chosen to block clients that aren’t supported by Intune, use the **Apply policy only to supported platforms** option.</span></span>

    ![Vergleich der Client-Apps-Benutzeroberfläche zwischen den Portalen Intune und Azure](./media/reassign-ca-15.png)

9. <span data-ttu-id="151a7-190">Sobald Sie damit fertig sind, klicken Sie auf zweimal auf **Fertig**.</span><span class="sxs-lookup"><span data-stu-id="151a7-190">When you have finished choosing the client app, click **Done** twice.</span></span>

10. <span data-ttu-id="151a7-191">Wählen Sie im Abschnitt **Zugriffssteuerung** die Option **Grant** (Gewähren) aus.</span><span class="sxs-lookup"><span data-stu-id="151a7-191">Under the **Access controls** section, choose **Grant**.</span></span>

11. <span data-ttu-id="151a7-192">Wählen Sie **Markieren des Geräts als kompatibel erforderlich** unter **Grant Access Controls** (Zugriffssteuerungen gewähren) aus, klicken Sie dann auf **Auswählen**.</span><span class="sxs-lookup"><span data-stu-id="151a7-192">Under **Grant Access Controls**, choose **Require device to be marked as compliant**, and then click **Select**.</span></span>

    ![Vergleich der Benutzeroberfläche für das Erteilen von Zugriff zwischen den Portalen Intune und Azure](./media/reassign-ca-16.png)

12. <span data-ttu-id="151a7-194">Aktivieren Sie die Umschaltfläche **Richtlinie aktivieren** auf dem Blatt **Neu** der Richtlinie für den bedingten Zugriff, klicken Sie dann auf **Erstellen**.</span><span class="sxs-lookup"><span data-stu-id="151a7-194">On the **New** conditional access policy blade, turn on the **Enable policy** toggle, and then click **Create**.</span></span>

    ![Zulassen des Vergleichs der Benutzeroberfläche für die Richtlinie für bedingten Zugriff zwischen den Portalen Intune und Azure](./media/reassign-ca-17.png)

## <a name="disable-conditional-access-policies-in-the-intune-classic-portal"></a><span data-ttu-id="151a7-196">Deaktivieren von Richtlinien für bedingten Zugriff im klassischen Intune-Portal</span><span class="sxs-lookup"><span data-stu-id="151a7-196">Disable conditional access policies in the Intune classic portal</span></span>

<span data-ttu-id="151a7-197">Sobald Sie Ihre Richtlinien für den bedingten Zugriff erneut im Azure-Portal zugewiesen haben, ist es wichtig, dass Sie die Richtlinien für bedingten Zugriff, die Sie zuvor im klassischen Intune-Portal erstellt haben, allmählich deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="151a7-197">After you have reassigned your conditional access policies in the Azure portal, it's important to gradually disable the conditional access policies previously created in the Intune classic portal.</span></span> <span data-ttu-id="151a7-198">Darüber hinaus müssen Sie möglicherweise die gleiche Sicherheitsgruppe verwenden, um die im Azure-Portal erstellten Richtlinien für bedingten Zugriff anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="151a7-198">Additionally, you might need to use the same security group to apply the conditional access policies created in the Azure portal.</span></span>

> [!NOTE] 
    > <span data-ttu-id="151a7-199">Sehen Sie sich den Abschnitt mit den [Vorbereitungen](#before-you-begin) zu Beginn dieses Themas an, bevor Sie Ihre Richtlinien für den bedingten Zugriff im klassischen Intune-Portal deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="151a7-199">Before disabling your conditional access policies in the Intune classic portal, see the [Before you begin](#before-you-begin) section at the beginning of this topic.</span></span>

### <a name="to-disable-the-conditional-access-policies"></a><span data-ttu-id="151a7-200">So deaktivieren Sie die Richtlinien für den bedingten Zugriff</span><span class="sxs-lookup"><span data-stu-id="151a7-200">To disable the conditional access policies</span></span>

1.  <span data-ttu-id="151a7-201">Wechseln Sie zum [klassischen Intune-Portal](https://manage.microsoft.com), und melden Sie sich mit Ihren Anmeldeinformationen an.</span><span class="sxs-lookup"><span data-stu-id="151a7-201">Go to the [Intune classic portal](https://manage.microsoft.com), and sign in with your credentials.</span></span>

2.  <span data-ttu-id="151a7-202">Wählen Sie **Richtlinie** im linken Menü aus.</span><span class="sxs-lookup"><span data-stu-id="151a7-202">Choose **Policy** from the left menu.</span></span>

3.  <span data-ttu-id="151a7-203">Wählen Sie **Bedingter Zugriff** aus und anschließend den Microsoft-Clouddienst (Exchange Online, SharePoint Online usw.), für den Sie eine Richtlinie für bedingten Zugriff erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="151a7-203">Choose **Conditional access**, and then select the Microsoft cloud service (for example, Exchange Online or SharePoint Online) that you created a conditional access policy for.</span></span>

4.  <span data-ttu-id="151a7-204">Deaktivieren Sie die Option **Bedingte Zugriffsrichtlinie für Exchange Online aktivieren**, und klicken Sie dann auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="151a7-204">Uncheck the option **Enable conditional access policy**, and then click **Save**.</span></span>

    ![Deaktivieren von Richtlinien für bedingten Zugriff im klassischen Intune-Portal](./media/reassign-ca-18.png)

## <a name="see-also"></a><span data-ttu-id="151a7-206">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="151a7-206">See also</span></span>

- [<span data-ttu-id="151a7-207">Gängige Möglichkeiten der Verwendung des bedingten Zugriffs in Intune</span><span class="sxs-lookup"><span data-stu-id="151a7-207">Common ways to use conditional access with Intune</span></span>](conditional-access-intune-common-ways-use.md)
- [<span data-ttu-id="151a7-208">App-basierter bedingter Zugriff mit Intune</span><span class="sxs-lookup"><span data-stu-id="151a7-208">app-based conditional access with Intune</span></span>](app-based-conditional-access-intune.md)
- [<span data-ttu-id="151a7-209">Bedingter Zugriff in Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="151a7-209">Conditional access in Azure Active Directory</span></span>](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access-azure-portal-get-started)
