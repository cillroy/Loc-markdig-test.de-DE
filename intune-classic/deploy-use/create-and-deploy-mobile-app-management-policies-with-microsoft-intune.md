---
title: Erstellen und Bereitstellen von MAM-Richtlinien
description: "Verwenden Sie die schrittweisen Anweisungen in diesem Thema zum Erstellen und Bereitstellen von Verwaltungsrichtlinien für mobile Apps."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 11/14/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c1b9a343-1737-4a65-a9c6-aca48acad11c
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 44f1d55866922e57a1ea9be509a86543e0360807
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2018
---
# <a name="create-and-deploy-app-protection-policies-with-microsoft-intune"></a><span data-ttu-id="34d4c-103">Erstellen und Bereitstellen von App-Schutzrichtlinien mit Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="34d4c-103">Create and deploy app protection policies with Microsoft Intune</span></span>

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="34d4c-104">In diesem Thema wird der Erstellungsvorgang einer App-Schutzrichtlinie im **Azure-Portal** beschrieben.</span><span class="sxs-lookup"><span data-stu-id="34d4c-104">This topic describes the process of creating an app protection policy in the **Azure portal**.</span></span> <span data-ttu-id="34d4c-105">Das Azure-Portal ist die neue Verwaltungskonsole zum Erstellen von App-Schutzrichtlinien, und wir empfehlen, dass Sie Ihre App-Schutzrichtlinien in diesem Portal erstellen.</span><span class="sxs-lookup"><span data-stu-id="34d4c-105">The Azure portal is the new admin console for creating app protection policies, and we recommend that you use this portal to create app protection policies.</span></span> <span data-ttu-id="34d4c-106">Das Azure-Portal unterstützt die folgenden MAM-Szenarien:</span><span class="sxs-lookup"><span data-stu-id="34d4c-106">Azure portal supports the following MAM scenarios:</span></span>

- <span data-ttu-id="34d4c-107">Bei Intune registrierte Geräte</span><span class="sxs-lookup"><span data-stu-id="34d4c-107">Devices enrolled in Intune.</span></span>
- <span data-ttu-id="34d4c-108">Geräte, die mithilfe einer MDM-Lösung eines Drittanbieters verwaltet werden</span><span class="sxs-lookup"><span data-stu-id="34d4c-108">Devices managed by a third-party MDM solution.</span></span>
- <span data-ttu-id="34d4c-109">Geräte, die gar keiner Verwaltung durch eine MDM-Lösung unterliegen (BYOD).</span><span class="sxs-lookup"><span data-stu-id="34d4c-109">Devices that are not managed by any MDM solution (BYOD).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="34d4c-110">Hier sind ein paar Überlegungen, wenn Sie aktuell die **Intune-Verwaltungskonsole** zum Verwalten Ihrer Geräte verwenden:</span><span class="sxs-lookup"><span data-stu-id="34d4c-110">Here are a few considerations if you're using the **Intune admin console** to manage your devices:</span></span>
> 
> * <span data-ttu-id="34d4c-111">Sie können mithilfe der [Intune-Verwaltungskonsole](configure-and-deploy-mobile-application-management-policies-in-the-microsoft-intune-console.md) eine App-Schutzrichtlinie erstellen, die Apps für Geräte unterstützt, die bei Intune registriert sind.</span><span class="sxs-lookup"><span data-stu-id="34d4c-111">You can create an app protection policy that supports apps for devices enrolled in Intune using the [Intune admin console](configure-and-deploy-mobile-application-management-policies-in-the-microsoft-intune-console.md).</span></span>
> * <span data-ttu-id="34d4c-112">Die App-Schutzrichtlinien, die in der Intune-Verwaltungskonsole erstellt wurden, können nicht ins Azure-Portal importiert werden.</span><span class="sxs-lookup"><span data-stu-id="34d4c-112">App protection policies created in the Intune admin console cannot be imported into the Azure portal.</span></span>  <span data-ttu-id="34d4c-113">Die App-Schutzrichtlinien müssen im Azure-Portal neu erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="34d4c-113">The app protection policies must be re-created in the Azure portal.</span></span>
> 
> * <span data-ttu-id="34d4c-114">Möglicherweise werden in der Intune-Verwaltungskonsole nicht alle App-Schutzrichtlinieneinstellungen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="34d4c-114">You may not see all app protection policy settings in the Intune admin console.</span></span> <span data-ttu-id="34d4c-115">Das Azure-Portal stellt die neue Verwaltungskonsole zum Erstellen von App-Schutzrichtlinien dar.</span><span class="sxs-lookup"><span data-stu-id="34d4c-115">The Azure portal is the new admin console for creating app protection policies.</span></span>
> 
> * <span data-ttu-id="34d4c-116">Sie müssen in der Intune-Verwaltungskonsole eine App-Schutzrichtlinie erstellen, um verwaltete Apps bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="34d4c-116">To deploy managed apps, you must create a app protection policy in the Intune admin console.</span></span> <span data-ttu-id="34d4c-117">In diesem Fall möchten Sie möglicherweise eine App-Schutzrichtlinie sowohl in der Intune-Verwaltungskonsole als auch im Azure-Portal erstellen: In der Intune-Verwaltungskonsole, um sicherzustellen, dass Sie verwaltete Apps bereitstellen können und im Azure-Portal, da es die neue Verwaltungskonsole darstellt, die über alle App-Schutzrichtlinieneinstellungen verfügt.</span><span class="sxs-lookup"><span data-stu-id="34d4c-117">In this case, you may want to create app protection policies in both the Intune admin console and the Azure portal: Intune admin console to make sure you have the ability to deploy managed apps, and the Azure portal because it is the new admin console that has all the app protection policy settings.</span></span>
> 
> * <span data-ttu-id="34d4c-118">Wenn Sie sowohl in der Intune-Verwaltungskonsole als auch im Azure-Portal App-Schutzrichtlinien erstellen, wird die im Azure-Portal erstellte Richtlinie auf die Apps angewendet.</span><span class="sxs-lookup"><span data-stu-id="34d4c-118">If you create app protection policies on both Intune admin console and Azure portal, the policy that is created in the Azure portal is applied to the apps.</span></span>

<span data-ttu-id="34d4c-119">Wählen Sie eins der folgenden Themen aus, um eine Liste der für die Plattformen Android und iOS unterstützten Richtlinieneinstellungen anzuzeigen:</span><span class="sxs-lookup"><span data-stu-id="34d4c-119">To see a list of policy settings supported for Android and iOS platforms, select one of the following:</span></span>

> [!div class="op_single_selector"]
> - [iOS-Richtlinien](ios-mam-policy-settings.md)
> - [Android-Richtlinien](android-mam-policy-settings.md)

- <span data-ttu-id="34d4c-122">Eine ausführlichere Beschreibung der Funktionsweise von App-Schutzrichtlinien und der von Intune App-Schutzrichtlinien unterstützten Szenarios finden Sie im Thema [Schützen von App-Daten mithilfe der Verwaltungsrichtlinien für mobile Anwendungen mit Microsoft Intune](protect-app-data-using-mobile-app-management-policies-with-microsoft-intune.md).</span><span class="sxs-lookup"><span data-stu-id="34d4c-122">For a more detailed description of how app protection policies work and the scenarios supported by Intune app protection policies, see [protect app data using app protection policies](protect-app-data-using-mobile-app-management-policies-with-microsoft-intune.md).</span></span>

##  <a name="create-an-app-protection-policy"></a><span data-ttu-id="34d4c-123">Erstellen einer App-Schutzrichtlinie</span><span class="sxs-lookup"><span data-stu-id="34d4c-123">Create an app protection policy</span></span>
<span data-ttu-id="34d4c-124">App-Schutzrichtlinien werden im Azure-Portal erstellt.</span><span class="sxs-lookup"><span data-stu-id="34d4c-124">App protection policies are created at the Azure Portal.</span></span> <span data-ttu-id="34d4c-125">Wenn Sie das Azure-Portal zum ersten Mal verwenden, lesen Sie [Azure portal for Microsoft Intune app protection policies (Azure-Portal für App-Schutzrichtlinien in Microsoft Intune)](azure-portal-for-microsoft-intune-mam-policies.md), um das Azure-Portal besser kennenzulernen.</span><span class="sxs-lookup"><span data-stu-id="34d4c-125">If this is the first time you are using the Azure portal, read [Azure portal for Microsoft Intune app protection policies](azure-portal-for-microsoft-intune-mam-policies.md) to get more familiar with the Azure Portal.</span></span> <span data-ttu-id="34d4c-126">Überprüfen Sie vor dem Erstellen einer App-Schutzrichtlinie die Informationen zu [Voraussetzungen und Support](get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune.md).</span><span class="sxs-lookup"><span data-stu-id="34d4c-126">Before creating an app protection policy, review the [pre-requisites and support](get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune.md) information.</span></span>

<span data-ttu-id="34d4c-127">Gehen Sie folgendermaßen vor, um App-Schutzrichtlinien zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="34d4c-127">Follow the steps below to create app protection policies:</span></span>

1. <span data-ttu-id="34d4c-128">Navigieren Sie zum [Azure-Portal](https://portal.azure.com), und geben Sie Ihre-Anmeldeinformationen ein.</span><span class="sxs-lookup"><span data-stu-id="34d4c-128">Go to the [Azure portal](https://portal.azure.com), and enter your credentials.</span></span>

2. <span data-ttu-id="34d4c-129">Wählen Sie **Weitere Dienste** aus, und geben Sie „Intune“ ein.</span><span class="sxs-lookup"><span data-stu-id="34d4c-129">Choose **More Services**, and type "Intune".</span></span>

3. <span data-ttu-id="34d4c-130">Wählen Sie **Intune-Schutz für Apps** aus.</span><span class="sxs-lookup"><span data-stu-id="34d4c-130">Choose **Intune App Protection**.</span></span>

4. <span data-ttu-id="34d4c-131">Wählen Sie **Intune-Verwaltung von mobilen Anwendungen &gt; Einstellungen** aus, um das Blatt **Alle Einstellungen** zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="34d4c-131">Choose **Intune mobile application management &gt; Settings** to open the **All Settings** blade.</span></span>

    ![Screenshot des Blatts „Mobile Anwendungsverwaltung mit Intune“](../media/AppManagement/AzurePortal_MAM_Mainblade-2.png)

2.  <span data-ttu-id="34d4c-133">Wählen Sie auf dem Blatt **Alle Einstellungen** **App-Richtlinie** aus.</span><span class="sxs-lookup"><span data-stu-id="34d4c-133">In the **All Settings** blade, choose **App policy**.</span></span> <span data-ttu-id="34d4c-134">Hiermit wird das Blatt **App-Richtlinie** geöffnet, auf dem Sie neue Richtlinien erstellen und vorhandene bearbeiten können.</span><span class="sxs-lookup"><span data-stu-id="34d4c-134">This opens the **App policy** blade, where you'll create new policies and edit existing policies.</span></span> <span data-ttu-id="34d4c-135">Wählen Sie **Richtlinie hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="34d4c-135">Choose **Add a policy**.</span></span>

    ![<span data-ttu-id="34d4c-136">Screenshot des Blatts „App-Richtlinie“ mit hervorgehobener Menüoption „Richtlinie hinzufügen“</span><span class="sxs-lookup"><span data-stu-id="34d4c-136">Screenshot of the App policy blade with the Add a policy menu option highlighted</span></span> ](../media/AppManagement/AzurePortal_MAM_AddPolicy.png)

3.  <span data-ttu-id="34d4c-137">Geben Sie einen Namen für die Richtlinie sowie eine kurze Beschreibung ein, und wählen Sie den Plattformtyp aus, um eine Richtlinie für iOS oder Android zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="34d4c-137">Type a name for the policy, add a brief description, and select the platform type to create a policy for iOS or Android.</span></span> <span data-ttu-id="34d4c-138">Sie können für jede Plattform mehr als eine Richtlinie erstellen.</span><span class="sxs-lookup"><span data-stu-id="34d4c-138">You can create more than one policy for each platform.</span></span>

    ![Screenshot des Blatts „Richtlinie hinzufügen“](../media/AppManagement/AzurePortal_MAM_AddPolicy_only.png)

4.  <span data-ttu-id="34d4c-140">Wählen Sie **Apps** aus, um das Blatt **Apps** zu öffnen, auf dem eine Liste der verfügbaren Apps angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="34d4c-140">Choose **Apps** to open the **Apps blade**, where a list of available apps is displayed.</span></span> <span data-ttu-id="34d4c-141">Wählen Sie eine oder mehrere Apps in der Liste aus, mit denen Sie die von Ihnen zu erstellende Richtlinie verknüpfen möchten.</span><span class="sxs-lookup"><span data-stu-id="34d4c-141">Select one or more apps from the list that you want to associate with the policy that you are creating.</span></span> <span data-ttu-id="34d4c-142">Nachdem Sie die Apps ausgewählt haben, wählen Sie **Auswählen** unten auf dem Blatt **Apps** aus, um Ihre Auswahl zu speichern.</span><span class="sxs-lookup"><span data-stu-id="34d4c-142">Once you have selected the apps, choose **Select** at the bottom of the **Apps** blade to save your selection.</span></span>

    > [!IMPORTANT]
    > Sie müssen mindestens eine App auswählen, um eine Richtlinie erstellen zu können.

5.  <span data-ttu-id="34d4c-144">Wählen Sie auf dem Blatt **Richtlinie hinzufügen** **Erforderliche Einstellungen konfigurieren** aus, um das Blatt mit den Richtlinieneinstellungen zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="34d4c-144">On the **Add a policy blade**, choose **Configure required settings** to open the policy settings blade.</span></span>

    <span data-ttu-id="34d4c-145">Es gibt zwei Kategorien von Richtlinieneinstellungen: **Datenverlagerung** und **Zugriff**.</span><span class="sxs-lookup"><span data-stu-id="34d4c-145">There are two categories of policy settings, **Data relocation** and **Access**.</span></span>  <span data-ttu-id="34d4c-146">Richtlinien für die Datenverlagerung beziehen sich auf die Datenverschiebung in und aus Apps, während mit Zugriffsrichtlinien bestimmt wird, wie der Endbenutzer auf die Apps im beruflichen Kontext zugreift.</span><span class="sxs-lookup"><span data-stu-id="34d4c-146">Data relocation policies are applicable to data movement in and out of the apps, while the access polices determine how the end user accesses the apps in a work context.</span></span>
    <span data-ttu-id="34d4c-147">Um Ihnen bei den ersten Schritten zu helfen, enthalten die Richtlinieneinstellung Standardwerte.</span><span class="sxs-lookup"><span data-stu-id="34d4c-147">To get you started, the policy settings have default values.</span></span> <span data-ttu-id="34d4c-148">Sie müssen keine Änderungen vornehmen, wenn die Standardwerte Ihren Anforderungen entsprechen.</span><span class="sxs-lookup"><span data-stu-id="34d4c-148">You do not have to make any changes if the default values meet your requirements.</span></span>

    > [!TIP]
    > Diese Richtlinieneinstellungen werden nur durchgesetzt, wenn Apps im beruflichen Kontext verwendet werden.  Wenn der Endbenutzer die App zum Erledigen einer privaten Aufgabe verwendet, ist er von diesen Richtlinien nicht betroffen.

    ![Screenshot des Blatts „Einstellungen“ zusammen mit dem Blatt „Richtlinie hinzufügen“](../media/AppManagement/AzurePortal_MAM_PolicySettings.png)

6.  <span data-ttu-id="34d4c-152">Wählen Sie **OK** aus, um diese Konfiguration zu speichern.</span><span class="sxs-lookup"><span data-stu-id="34d4c-152">Choose **OK** to save this configuration.</span></span> <span data-ttu-id="34d4c-153">Damit befinden Sie sich wieder auf dem Blatt **Richtlinie hinzufügen** .</span><span class="sxs-lookup"><span data-stu-id="34d4c-153">You are now back in the **Add a policy** blade.</span></span> <span data-ttu-id="34d4c-154">Wählen Sie **Erstellen** aus, um die Richtlinie zu erstellen und Ihre Einstellungen zu speichern.</span><span class="sxs-lookup"><span data-stu-id="34d4c-154">Choose **Create** to create the policy and save your settings.</span></span>

    ![Screenshot eines Blatts „Richtlinie hinzufügen“ mit konfigurierten Apps und Einstellungen](../media/AppManagement/AzurePortal_MAM_CreatePolicy.png)

<span data-ttu-id="34d4c-156">Wenn Sie mit dem Erstellen einer Richtlinie wie im vorherigen Verfahren beschrieben fertig sind, wird sie noch nicht für Benutzer bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="34d4c-156">When you finish creating a policy as described in the previous procedure, it is not deployed to any users.</span></span> <span data-ttu-id="34d4c-157">Informationen zum Bereitstellen einer Richtlinie finden Sie im Abschnitt „Bereitstellen einer Richtlinie für Benutzer“.</span><span class="sxs-lookup"><span data-stu-id="34d4c-157">To deploy a policy, see the following section, "Deploy a policy to users."</span></span>

> [!IMPORTANT]
> Wenn Sie eine App-Schutzrichtlinie für eine App mithilfe der Intune-Verwaltungskonsole und eine App-Schutzrichtlinie mithilfe des Azure-Portals erstellen, erhält die im Azure-Portal erstellte Richtlinie den Vorrang. Mit der Berichterstattung in der Intune- oder Configuration Manager-Verwaltungskonsole werden jedoch die Richtlinieneinstellungen zurückgegeben, die in der Intune-Verwaltungskonsole erstellt wurden. Beispiel:
>
> -   Sie haben eine App-Schutzrichtlinie in der Intune-Verwaltungskonsole erstellt, mit der Kopien aus einer Anwendung verhindert werden.
> -   Sie haben eine App-Schutzrichtlinie in der Azure-Konsole erstellt, die Kopien aus einer Anwendung zulässt.
> -   Sie führen beide Richtlinien in derselben App zusammen.
> -   Die Richtlinie, die Sie in der Azure-Verwaltungskonsole erstellt haben, hat Vorrang, und Kopien sind möglich.
> -   Status und Berichte der Intune-Verwaltungskonsole geben jedoch fälschlicherweise an, dass Kopien nicht möglich sind.

## <a name="line-of-business-lob-apps-optional"></a><span data-ttu-id="34d4c-166">Verwaltete branchenspezifische Apps (Line-of-Business, LOB) (optional)</span><span class="sxs-lookup"><span data-stu-id="34d4c-166">Line of Business (LOB) apps (optional)</span></span>

<span data-ttu-id="34d4c-167">Ab der Intune-Version 1703 haben Sie die Möglichkeit, LOB-Apps allgemein in Intune hinzuzufügen, wenn Sie eine neue App-Schutzrichtlinie erstellen.</span><span class="sxs-lookup"><span data-stu-id="34d4c-167">Beginning with Intune 1703 version, you have the option to generally add LOB apps into Intune when creating a new app protection policy.</span></span> <span data-ttu-id="34d4c-168">Dadurch erhalten Sie die Option, App-Schutzrichtlinien für LOB-Apps mithilfe des MAM SDK zu definieren, ohne dass Sie vollständige Berechtigungen für die App-Bereitstellung benötigen.</span><span class="sxs-lookup"><span data-stu-id="34d4c-168">This gives you the option to define app protection policies for LOB apps using the MAM SDK without requiring full app deployment permissions.</span></span>
<span data-ttu-id="34d4c-169">/intune/app-sdk-get-started</span><span class="sxs-lookup"><span data-stu-id="34d4c-169">/intune/app-sdk-get-started</span></span>
> [!TIP]
> Sie können LOB-Apps in Intune hinzufügen, wenn Sie den [Intune App SDK](/intune/app-sdk-get-started)-Workflow durchlaufen.

> [!IMPORTANT]
> Wenn Benutzer nur über bestimmte Berechtigungen zum Bereitstellen von MAM-Apps verfügen und nicht über vollständige Berechtigungen zur App-Bereitstellung, womit Sie beliebige Apps in Intune bereitstellen könnten, könnten Sie den Intune SDK-Workflow nicht durchlaufen, jedoch können Sie noch immer ihre LOB-Apps über den Workflow zur Erstellung der MAM-App-Schutzrichtlinie hinzufügen.

### <a name="to-add-lob-apps-ios-and-android"></a><span data-ttu-id="34d4c-172">Hinzufügen von branchenspezifischen Apps (iOS und Android)</span><span class="sxs-lookup"><span data-stu-id="34d4c-172">To add LOB apps (iOS and Android)</span></span>

1.  <span data-ttu-id="34d4c-173">Wählen Sie auf dem Blatt „Richtlinie hinzufügen“ die Option „Konfigurieren von **Apps** aus, um das Blatt „Apps“ zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="34d4c-173">On the Add a policy blade, choose Configure **Apps** to open the Apps blade.</span></span>

    ![MAM-Blatt „Richtlinie hinzufügen“](../media/AppManagement/mam-lob-apps-1.png)

2.  <span data-ttu-id="34d4c-175">Klicken Sie auf **Weitere Apps**, und geben Sie dann die **Bündel-ID** (für iOS) und die **Paket-ID** (für Android) ein, und klicken Sie dann auf „Select to add your LOB apps“ (Auswählen, Ihre branchenspezifischen Apps hinzuzufügen).</span><span class="sxs-lookup"><span data-stu-id="34d4c-175">Click **More apps**, then enter the **Bundle ID** (for iOS), **package ID** (for Android), then click Select to add your LOB apps.</span></span>

    ![MAM-Blatt „Weitere Apps“](../media/AppManagement/mam-lob-apps-2.png)

### <a name="to-add-lob-apps-windows"></a><span data-ttu-id="34d4c-177">So fügen Sie branchenspezifische Apps hinzu (Windows)</span><span class="sxs-lookup"><span data-stu-id="34d4c-177">To add LOB apps (Windows)</span></span>

> [!IMPORTANT]
> Sie müssen Windows 10 aus der Dropdown-Liste der Plattform auswählen, wenn Sie eine neue App-Schutzrichtlinie erstellen.

1. <span data-ttu-id="34d4c-179">Wählen Sie auf dem Blatt „Richtlinie hinzufügen“ **Zulässige Apps** oder **Ausgenommene Apps** aus, um das Blatt „Allowed or Exempt apps“ (Zulässige oder ausgenommene Apps) zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="34d4c-179">On the Add a policy blade, choose **Allowed apps** or **Exempt apps** to open the Allowed or Exempt apps blade.</span></span>

   > [!NOTE]
   > 
   > - **Zulässige Apps**: Dies sind die Apps, die mit dieser Richtlinie übereinstimmen müssen.
   > - **Ausgeschlossene Apps**: Diese Apps sind von dieser Richtlinie ausgeschlossen und können ohne Einschränkungen auf Unternehmensdaten zugreifen.
   > <br></br>
2. <span data-ttu-id="34d4c-182">Klicken Sie auf dem Blatt „Zulässige Apps“ oder „Ausgeschlossene Apps“ auf **Hinzufügen von Apps**.</span><span class="sxs-lookup"><span data-stu-id="34d4c-182">On Allowed or Exempt apps blade, click **Add apps**.</span></span> <span data-ttu-id="34d4c-183">Sie können empfohlene Microsoft-Apps sowie Store- oder Desktop-Apps hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="34d4c-183">You can add recommended Microsoft apps, add store or desktop apps.</span></span>

    <span data-ttu-id="34d4c-184">ein.</span><span class="sxs-lookup"><span data-stu-id="34d4c-184">a.</span></span>  <span data-ttu-id="34d4c-185">**Empfohlene Apps:** Eine voraufgefüllte Liste der Apps (hauptsächlich Office), die Administratoren einfach in die Richtlinie importieren dürfen.</span><span class="sxs-lookup"><span data-stu-id="34d4c-185">**Recommended apps:** a pre-populated list of (mostly Office) apps that we let admins easily import into policy.</span></span>

    <span data-ttu-id="34d4c-186">b.</span><span class="sxs-lookup"><span data-stu-id="34d4c-186">b.</span></span>  <span data-ttu-id="34d4c-187">**Store-Apps:** Administratoren können eine beliebige App aus dem Windows Store in die Richtlinie einfügen.</span><span class="sxs-lookup"><span data-stu-id="34d4c-187">**Store apps:** Admin can add any app from the Windows store to policy.</span></span>

    <span data-ttu-id="34d4c-188">c.</span><span class="sxs-lookup"><span data-stu-id="34d4c-188">c.</span></span>  <span data-ttu-id="34d4c-189">**Windows Desktop-Apps:** Administratoren können traditionelle Windows Desktop-Apps der Richtlinie hinzufügen (z.B. .exe, .dll, usw.)</span><span class="sxs-lookup"><span data-stu-id="34d4c-189">**Windows desktop apps:** Admin can add any traditional Windows desktop apps to the policy (e.g. exe, dll, etc.)</span></span>

## <a name="deploy-a-policy-to-users"></a><span data-ttu-id="34d4c-190">Bereitstellen einer Richtlinie für Benutzer</span><span class="sxs-lookup"><span data-stu-id="34d4c-190">Deploy a policy to users</span></span>

1.  <span data-ttu-id="34d4c-191">Wählen Sie auf dem Blatt **Richtlinie** **Benutzergruppen** aus. Damit wird das Blatt **Benutzergruppen**geöffnet.</span><span class="sxs-lookup"><span data-stu-id="34d4c-191">In the **Policy** blade, choose  **User groups**, which opens the **User groups** blade.</span></span> <span data-ttu-id="34d4c-192">Wählen Sie auf dem Blatt **Benutzergruppen** **Benutzergruppe hinzufügen** aus, um das Blatt **Benutzergruppe hinzufügen** zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="34d4c-192">Choose **Add user group** in the **User groups** blade to open the **Add user group** blade.</span></span>

    ![Screenshot des Blatts „Benutzergruppen“ mit hervorgehobener Menüoption „Benutzergruppe hinzufügen“](../media/AppManagement/AzurePortal_MAM_AddUserstoPolicy.png)

2.  <span data-ttu-id="34d4c-194">Auf dem Blatt **Benutzergruppe hinzufügen** wird eine Liste der Benutzergruppen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="34d4c-194">A list of user groups is displayed on the **Add user group** blade.</span></span> <span data-ttu-id="34d4c-195">Dies ist eine Liste aller Sicherheitsgruppen in Ihrem **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="34d4c-195">This is a list of all the security groups in your **Azure Active Directory**.</span></span> <span data-ttu-id="34d4c-196">Wählen Sie die Benutzergruppen aus, auf die diese Richtlinie angewendet werden soll, und anschließend **Auswählen**.</span><span class="sxs-lookup"><span data-stu-id="34d4c-196">Select the user groups you want this policy to apply to, and then choose **Select**.</span></span> <span data-ttu-id="34d4c-197">Die Auswahl von **Auswählen** bewirkt die Bereitstellung der Richtlinie für Benutzer.</span><span class="sxs-lookup"><span data-stu-id="34d4c-197">Choosing **Select**, deploys the policy to users.</span></span>

    ![Screenshot des Blatts „Benutzergruppe hinzufügen“ mit der Liste der Azure Active Directory-Benutzer](../media/AppManagement/AzurePortal_MAM_SelectUserstoDeploy.png)

    <span data-ttu-id="34d4c-199">Damit haben Sie eine Richtlinie erstellt und für die Benutzer bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="34d4c-199">You have now created a policy and deployed it to users.</span></span>

<span data-ttu-id="34d4c-200">Von der Richtlinie sind nur Benutzer betroffen, denen Intune-Lizenzen zugewiesen wurden.</span><span class="sxs-lookup"><span data-stu-id="34d4c-200">Only users with Intune licenses assigned to them are affected by the policy.</span></span> <span data-ttu-id="34d4c-201">Benutzer, die sich in einer von Ihnen ausgewählten Sicherheitsgruppe befinden und die nicht über eine Intune-Lizenz verfügen, sind nicht betroffen.</span><span class="sxs-lookup"><span data-stu-id="34d4c-201">Users who are in the security group that you selected who don’t have a Intune license assigned to them are not affected.</span></span>

>[!IMPORTANT]
> Wenn Sie Intune mit Configuration Manager verwenden, um Ihre iOS- und Android-Geräte zu verwalten, wird die Richtlinie nur auf Benutzer in der Gruppe angewendet, die Sie ausgewählt haben. Mitglieder untergeordneter Gruppen, die in der ausgewählten Gruppe geschachtelt sind, sind nicht betroffen.

<span data-ttu-id="34d4c-204">Endbenutzer können die Apps aus dem App Store oder aus Google Play herunterladen.</span><span class="sxs-lookup"><span data-stu-id="34d4c-204">End users can download the apps from the App store or Google Play.</span></span> <span data-ttu-id="34d4c-205">Weitere Informationen finden Sie in folgenden Quellen:</span><span class="sxs-lookup"><span data-stu-id="34d4c-205">For more information, see:</span></span>
* [<span data-ttu-id="34d4c-206">Was Sie erwartet, wenn Ihre Android-App von App-Schutzrichtlinien verwaltet wird</span><span class="sxs-lookup"><span data-stu-id="34d4c-206">What to expect when your Android app is managed by app protection policies</span></span>](/intune/end-user-mam-apps-android)
* [<span data-ttu-id="34d4c-207">Was Sie erwartet, wenn Ihre iOS-App von App-Schutzrichtlinien verwaltet wird</span><span class="sxs-lookup"><span data-stu-id="34d4c-207">What to expect when your iOS app is managed by app protection policies</span></span>](/intune/end-user-mam-apps-ios)

##  <a name="change-existing-policies"></a><span data-ttu-id="34d4c-208">Ändern vorhandener Richtlinien</span><span class="sxs-lookup"><span data-stu-id="34d4c-208">Change existing policies</span></span>
<span data-ttu-id="34d4c-209">Sie können eine vorhandene Richtlinie bearbeiten und sie auf die als Ziel festgelegten Benutzer anwenden.</span><span class="sxs-lookup"><span data-stu-id="34d4c-209">You can edit an existing policy and apply it to the targeted users.</span></span> <span data-ttu-id="34d4c-210">Wenn Sie vorhandene Richtlinien ändern, werden diese Änderungen für Benutzer, die bereits bei der App angemeldet sind, jedoch in den nächsten acht Stunden nicht wirksam.</span><span class="sxs-lookup"><span data-stu-id="34d4c-210">However, when you change existing policies,  users who are already signed  in to the apps won’t see the changes for an 8-hour period.</span></span>

<span data-ttu-id="34d4c-211">Um die Auswirkungen der Änderungen sofort zu erfahren, muss der Endbenutzer sich bei der App abmelden und sich dann erneut anmelden.</span><span class="sxs-lookup"><span data-stu-id="34d4c-211">To see the effect of the changes immediately, the end user will have to log out of the app, and sign back in.</span></span>

### <a name="to-change-the-list-of-apps-associated-with-the-policy"></a><span data-ttu-id="34d4c-212">So ändern Sie die Liste der Apps, die einer Richtlinie zugeordnet sind</span><span class="sxs-lookup"><span data-stu-id="34d4c-212">To change the list of apps associated with the policy</span></span>

1.  <span data-ttu-id="34d4c-213">Wählen Sie auf dem Blatt **App-Richtlinie** die Richtlinie aus, die Sie ändern möchten.</span><span class="sxs-lookup"><span data-stu-id="34d4c-213">In  the **App policy** blade, choose the policy you want to change.</span></span> <span data-ttu-id="34d4c-214">Damit wird ein Blatt speziell für die Richtlinie geöffnet, die Sie soeben ausgewählt haben.</span><span class="sxs-lookup"><span data-stu-id="34d4c-214">This opens a blade specific to the policy you just selected.</span></span>

    ![Screenshot einer vorhandenen Richtlinie, die auf einem separaten Blatt geöffnet ist](../media/AppManagement/AzurePortal_MAM_OpenPolicy.png)

2.  <span data-ttu-id="34d4c-216">Wählen Sie auf diesem Richtlinienblatt **Ziel-Apps** aus, um eine Liste der Apps zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="34d4c-216">In the policy blade, choose **Targeted apps** to open the list of apps.</span></span>

3.  <span data-ttu-id="34d4c-217">Fügen Sie der Liste Apps hinzu, oder entfernen Sie Apps hieraus, und wählen Sie dann das Symbol **Speichern** aus, um die Änderungen zu speichern.</span><span class="sxs-lookup"><span data-stu-id="34d4c-217">Remove or add apps from the list and choose the **Save** icon to save your changes.</span></span>

### <a name="to-change-the-list-of-user-groups"></a><span data-ttu-id="34d4c-218">So ändern Sie die Liste der Benutzergruppen</span><span class="sxs-lookup"><span data-stu-id="34d4c-218">To change the list of user groups</span></span>

1.  <span data-ttu-id="34d4c-219">Wählen Sie auf dem Blatt **App-Richtlinie** die Richtlinie aus, die Sie ändern möchten.</span><span class="sxs-lookup"><span data-stu-id="34d4c-219">In  the **App policy** blade, choose the policy you want to change.</span></span> <span data-ttu-id="34d4c-220">Damit wird ein Blatt speziell für die Richtlinie geöffnet, die Sie soeben ausgewählt haben.</span><span class="sxs-lookup"><span data-stu-id="34d4c-220">This opens the blade specific to the policy you selected.</span></span>

2.  <span data-ttu-id="34d4c-221">Wählen Sie auf dem Richtlinienblatt **Benutzergruppen** aus, um das Blatt **Benutzergruppe** zu öffnen, auf dem die Liste der Benutzergruppen angezeigt wird, auf die die Richtlinie gegenwärtig angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="34d4c-221">In the policy blade, choose **User groups** to open the **User group** blade that shows the list of current user groups who have this policy.</span></span>

3.  <span data-ttu-id="34d4c-222">Zum Hinzufügen einer neuen Benutzergruppe wählen Sie **Benutzergruppe hinzufügen** und anschließend die Benutzergruppe aus.</span><span class="sxs-lookup"><span data-stu-id="34d4c-222">To add a new user group to the policy, choose **Add user group**, and select the user group.</span></span> <span data-ttu-id="34d4c-223">Wählen Sie **Auswählen** aus, um die Richtlinie für die ausgewählte Gruppe bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="34d4c-223">Choose **Select** to deploy the policy to the group you selected.</span></span>

    ![Screenshot des Blatts „Benutzergruppe hinzufügen“ mit zwei ausgewählten Benutzergruppen](../media/AppManagement/AzurePortal_MAM_ChangePolicy_SelectUser.png)

4.  <span data-ttu-id="34d4c-225">Zum Löschen einer Benutzergruppe markieren Sie die Benutzergruppe, die Sie entfernen möchten.</span><span class="sxs-lookup"><span data-stu-id="34d4c-225">To delete a user group, highlight the user group you want to remove.</span></span> <span data-ttu-id="34d4c-226">Anschließend wählen Sie die Auslassungspunkte (...) und die Option **Löschen** aus, um die Benutzergruppe zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="34d4c-226">Then choose the ellipses (…), and choose **Delete** to remove the user group.</span></span>

    ![<span data-ttu-id="34d4c-227">Screenshot mit Löschoption</span><span class="sxs-lookup"><span data-stu-id="34d4c-227">Screenshot showing Delete option</span></span> ](../media/AppManagement/AzurePortal_MAM_ChangePolicy_DeleteUser.png)

### <a name="to-change-policy-settings"></a><span data-ttu-id="34d4c-228">So ändern Sie Richtlinieneinstellungen</span><span class="sxs-lookup"><span data-stu-id="34d4c-228">To change policy settings</span></span>

1.  <span data-ttu-id="34d4c-229">Wählen Sie auf dem Blatt **App-Richtlinie** die Richtlinie aus, die Sie ändern möchten.</span><span class="sxs-lookup"><span data-stu-id="34d4c-229">In the **App policy** blade, choose the policy you want to change.</span></span> <span data-ttu-id="34d4c-230">Damit wird ein Blatt speziell für die Richtlinie geöffnet, die Sie soeben ausgewählt haben.</span><span class="sxs-lookup"><span data-stu-id="34d4c-230">This opens a blade specific to the policy you just selected.</span></span>

    ![<span data-ttu-id="34d4c-231">Screenshot einer vorhandenen Richtlinie, die auf einem separaten Blatt geöffnet ist</span><span class="sxs-lookup"><span data-stu-id="34d4c-231">Screenshot of an existing policy open in a separate blade</span></span> ](../media/AppManagement/AzurePortal_MAM_OpenPolicy.png)

2.  <span data-ttu-id="34d4c-232">Wählen Sie **Richtlinieneinstellungen** aus, um das Blatt **Richtlinieneinstellungen** zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="34d4c-232">Choose **Policy settings** to open the **Policy settings** blade.</span></span>

3.  <span data-ttu-id="34d4c-233">Ändern Sie die Einstellungen, und wählen Sie das Symbol **Speichern** aus, um die Änderungen zu speichern.</span><span class="sxs-lookup"><span data-stu-id="34d4c-233">Change the settings, and choose the **Save** icon to save your changes.</span></span>

    ![Screenshot des Blatts „Richtlinieneinstellungen“ mit der Menüoption „Speichern“ ganz oben](../media/AppManagement/AzurePortal_MAM_ChangePolicy_ChangeSettings.png)

## <a name="policy-settings"></a><span data-ttu-id="34d4c-235">Richtlinieneinstellungen</span><span class="sxs-lookup"><span data-stu-id="34d4c-235">Policy settings</span></span>
<span data-ttu-id="34d4c-236">Eine vollständige Liste der Richtlinieneinstellungen für iOS und Android finden Sie in den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="34d4c-236">To see a full list of the policy settings for iOS and Android, select one of the following:</span></span>

> [!div class="op_single_selector"]
> - [iOS-Richtlinien](ios-mam-policy-settings.md)
> - [Android-Richtlinien](android-mam-policy-settings.md)

## <a name="next-steps"></a><span data-ttu-id="34d4c-239">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="34d4c-239">Next steps</span></span>
[<span data-ttu-id="34d4c-240">Überwachen der Verwaltungsrichtlinien für mobile Apps mit Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="34d4c-240">Monitor compliance and user status</span></span>](monitor-mobile-app-management-policies-with-microsoft-intune.md)

### <a name="see-also"></a><span data-ttu-id="34d4c-241">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="34d4c-241">See also</span></span>
* [<span data-ttu-id="34d4c-242">Was Sie erwartet, wenn Ihre Android-App von App-Schutzrichtlinien verwaltet wird</span><span class="sxs-lookup"><span data-stu-id="34d4c-242">What to expect when your Android app is managed by app protection policies</span></span>](/intune/end-user-mam-apps-android)
* [<span data-ttu-id="34d4c-243">Was Sie erwartet, wenn Ihre iOS-App von App-Schutzrichtlinien verwaltet wird</span><span class="sxs-lookup"><span data-stu-id="34d4c-243">What to expect when your iOS app is managed by app protection policies</span></span>](/intune/end-user-mam-apps-ios)
