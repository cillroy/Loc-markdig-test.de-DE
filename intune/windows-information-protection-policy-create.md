---
title: Erstellen und Bereitstellen von WIP-App-Schutzrichtlinien (Windows Information Protection) in Intune
titlesuffix: Azure portal
description: Erstellen und Bereitstellen von WIP-App-Schutzrichtlinien in Intune
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 11/13/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4e3627bd-a9fd-49bc-b95e-9b7532f0ed55
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: ab0456b58704f17d3dc5885ab5ae6b902c9ef152
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2017
---
# <a name="create-and-deploy-windows-information-protection-wip-app-protection-policy-with-intune"></a><span data-ttu-id="1c91a-103">Erstellen und Bereitstellen von WIP-App-Schutzrichtlinien (Windows Information Protection) in Intune</span><span class="sxs-lookup"><span data-stu-id="1c91a-103">Create and deploy Windows Information Protection (WIP) app protection policy with Intune</span></span>

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="1c91a-104">Ab Version Intune 1704 können Sie bei Windows 10 App-Schutzrichtlinien zum Schutz von Apps ohne Registrierung verwenden.</span><span class="sxs-lookup"><span data-stu-id="1c91a-104">Beginning with Intune 1704 release, you can use app protection policies with Windows 10 in to protect apps without device enrollment.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="1c91a-105">Vorbereitung</span><span class="sxs-lookup"><span data-stu-id="1c91a-105">Before you begin</span></span>

<span data-ttu-id="1c91a-106">Sprechen Sie wir über einige Konzepte, wenn Sie eine WIP-Richtlinie hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="1c91a-106">Let’s talk about a few concepts when adding a WIP policy.</span></span>

### <a name="list-of-allowed-and-exempt-apps"></a><span data-ttu-id="1c91a-107">Liste der zulässigen und ausgenommenen Apps</span><span class="sxs-lookup"><span data-stu-id="1c91a-107">List of allowed and exempt apps</span></span>

-   <span data-ttu-id="1c91a-108">**Zulässige Apps:** Dies sind die Apps, die dieser Richtlinie entsprechen müssen.</span><span class="sxs-lookup"><span data-stu-id="1c91a-108">**Allowed apps:** These are the apps that need to adhere to this policy.</span></span>

-   <span data-ttu-id="1c91a-109">**Ausgenommene Apps:** Diese Apps sind von dieser Richtlinie ausgenommen und können ohne Einschränkungen auf Unternehmensdaten zugreifen.</span><span class="sxs-lookup"><span data-stu-id="1c91a-109">**Exempt apps:** These apps are exempt from this policy and can access corporate data without restrictions.</span></span>

### <a name="types-of-apps"></a><span data-ttu-id="1c91a-110">App-Typen</span><span class="sxs-lookup"><span data-stu-id="1c91a-110">Types of apps</span></span>

-   <span data-ttu-id="1c91a-111">**Empfohlene Apps:** Eine vorab aufgefüllte Liste von Apps (hauptsächlich Microsoft Office), die Ihnen einen einfachen Import in die Richtlinie ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="1c91a-111">**Recommended apps:** a pre-populated list of (mostly Microsoft Office) apps that allow you easily import into policy.</span></span> <!---I really don't know what you mean by "easily import into policy"--->

-   <span data-ttu-id="1c91a-112">**Store-Apps:** Sie können der Richtlinie eine beliebige App aus dem Windows Store hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="1c91a-112">**Store apps:** You can add any app from the Windows store to the policy.</span></span>

-   <span data-ttu-id="1c91a-113">**Windows Desktop-Apps:** Sie haben außerdem die Möglichkeit,der Richtlinie traditionelle Windows Desktop-Apps hinzufügen (z.B. .exe, .dll, usw.)</span><span class="sxs-lookup"><span data-stu-id="1c91a-113">**Windows desktop apps:** You can add any traditional Windows desktop apps to the policy (for example, .exe, .dll)</span></span>

## <a name="pre-requisites"></a><span data-ttu-id="1c91a-114">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="1c91a-114">Pre-requisites</span></span>

<span data-ttu-id="1c91a-115">Sie müssen den MAM-Anbieter konfigurieren, bevor Sie eine WIP-App-Schutzrichtlinie erstellen können.</span><span class="sxs-lookup"><span data-stu-id="1c91a-115">You must configure the MAM provider before you can create a WIP app protection policy.</span></span> <span data-ttu-id="1c91a-116">Weitere Informationen finden Sie unter [Konfigurieren Ihres MAM-Anbieters in Intune](https://docs.microsoft.com/app-protection-policies-configure-windows-10.md).</span><span class="sxs-lookup"><span data-stu-id="1c91a-116">Learn more about [how to configure your MAM provider with Intune](https://docs.microsoft.com/app-protection-policies-configure-windows-10.md).</span></span>

<span data-ttu-id="1c91a-117">Darüber hinaus benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="1c91a-117">Additionally, you need to have the following:</span></span>

-   <span data-ttu-id="1c91a-118">[Azure AD Premium](https://docs.microsoft.com/azure/active-directory/active-directory-get-started-premium)-Lizenz</span><span class="sxs-lookup"><span data-stu-id="1c91a-118">[Azure AD Premium](https://docs.microsoft.com/azure/active-directory/active-directory-get-started-premium) license.</span></span>
-   [<span data-ttu-id="1c91a-119">Windows Creators Update</span><span class="sxs-lookup"><span data-stu-id="1c91a-119">Windows Creators Update</span></span>](https://blogs.windows.com/windowsexperience/2017/04/11/how-to-get-the-windows-10-creators-update/#o61bC2PdrHslHG5J.97)

> [!IMPORTANT]
> <span data-ttu-id="1c91a-120">WIP unterstützt nicht mehrere Identitäten; nur jeweils eine verwaltete Identität darf vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="1c91a-120">WIP does not support multi-identity, only one managed identity can exist at a time.</span></span>
<!---Should you be linking to a topic that explains what multi-identity is?--->

## <a name="to-add-a-wip-policy"></a><span data-ttu-id="1c91a-121">Hinzufügen einer WIP-Richtlinie</span><span class="sxs-lookup"><span data-stu-id="1c91a-121">To add a WIP policy</span></span>

<span data-ttu-id="1c91a-122">Nachdem Sie in Ihrer Organisation Intune eingerichtet haben, können Sie eine WIP-spezifische Richtlinie durch das [Azure-Portal](https://docs.microsoft.com/intune-classic/deploy-use/azure-portal-for-microsoft-intune-mam-policies) erstellen.</span><span class="sxs-lookup"><span data-stu-id="1c91a-122">After you set up Intune in your organization, you can create a WIP-specific policy through the [Azure portal](https://docs.microsoft.com/intune-classic/deploy-use/azure-portal-for-microsoft-intune-mam-policies).</span></span> <!---Is there an azure topic you can use instead of a classic? if not, should this topic be moved into the azure docset?--->

1.  <span data-ttu-id="1c91a-123">Wechseln Sie zum **Intune-Dashboard für die mobile Anwendungsverwaltung**, wählen Sie **Alle Einstellungen** und anschließend **App-Richtlinie** aus.</span><span class="sxs-lookup"><span data-stu-id="1c91a-123">Go to the **Intune mobile application management dashboard**, choose **All settings**, > **App policy**.</span></span>

2.  <span data-ttu-id="1c91a-124">Wählen Sie auf dem Blatt **App-Richtlinie** die Option **Richtlinie hinzufügen** aus und geben Sie folgende Werte ein:</span><span class="sxs-lookup"><span data-stu-id="1c91a-124">In the **App policy** blade, choose **Add a policy**, then enter the following values:</span></span>

    <span data-ttu-id="1c91a-125">a.</span><span class="sxs-lookup"><span data-stu-id="1c91a-125">a.</span></span>  <span data-ttu-id="1c91a-126">**Name:** Geben Sie einen Namen (Pflichtfeld) für Ihre neue Richtlinie ein.</span><span class="sxs-lookup"><span data-stu-id="1c91a-126">**Name:** Type a name (required) for your new policy.</span></span>

    <span data-ttu-id="1c91a-127">b.</span><span class="sxs-lookup"><span data-stu-id="1c91a-127">b.</span></span>  <span data-ttu-id="1c91a-128">**Beschreibung:** Geben Sie eine optionale Beschreibung ein.</span><span class="sxs-lookup"><span data-stu-id="1c91a-128">**Description:** Type an optional description.</span></span>

    <span data-ttu-id="1c91a-129">c.</span><span class="sxs-lookup"><span data-stu-id="1c91a-129">c.</span></span>  <span data-ttu-id="1c91a-130">**Plattform:** Wählen Sie **Windows 10** als unterstützte Plattform für Ihre App-Schutzrichtlinie aus.</span><span class="sxs-lookup"><span data-stu-id="1c91a-130">**Platform:** Choose **Windows 10** as the supported platform for your app protection policy.</span></span>

    <span data-ttu-id="1c91a-131">d.</span><span class="sxs-lookup"><span data-stu-id="1c91a-131">d.</span></span>  <span data-ttu-id="1c91a-132">**Registrierungsstatus:** Wählen Sie **Ohne Registrierung** als Registrierungsstatus für Ihre Richtlinie aus.</span><span class="sxs-lookup"><span data-stu-id="1c91a-132">**Enrollment state:** Choose **Without enrollment** as the enrollment state for your policy.</span></span>

3.  <span data-ttu-id="1c91a-133">Wählen Sie **Erstellen** aus.</span><span class="sxs-lookup"><span data-stu-id="1c91a-133">Choose **Create**.</span></span> <span data-ttu-id="1c91a-134">Die Richtlinie wird erstellt und in der Tabelle auf dem Blatt **App-Richtlinie** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="1c91a-134">The policy is created and appears in the table on the **App Policy** blade.</span></span>

## <a name="to-add-recommended-apps-to-your-allowed-apps-list"></a><span data-ttu-id="1c91a-135">So fügen Sie empfohlene Apps zur Liste der zulässigen Apps hinzu</span><span class="sxs-lookup"><span data-stu-id="1c91a-135">To add recommended apps to your allowed apps list</span></span>

1.  <span data-ttu-id="1c91a-136">Wählen Sie auf dem Blatt **App-Richtlinie** den Namen Ihrer Richtlinie und anschließend die Option **Zulässige Apps** auf dem Blatt **Richtlinie hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="1c91a-136">From the **App policy** blade, choose the name of your policy, then choose **Allowed apps** from the **Add a policy** blade.</span></span> <span data-ttu-id="1c91a-137">Das Blatt **Zulässige Apps** wird geöffnet, auf dem alle Apps angezeigt werden, die bereits in der Liste für diese App-Schutzrichtlinie enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="1c91a-137">The **Allowed apps** blade opens, showing you all apps that are already included in the list for this app protection policy.</span></span>

2.  <span data-ttu-id="1c91a-138">Wählen Sie auf dem Blatt **Zulässige Apps** die Option **Apps hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="1c91a-138">From the **Allowed apps** blade, choose **Add apps**.</span></span> <span data-ttu-id="1c91a-139">Das Blatt **Apps hinzufügen** wird geöffnet, auf dem alle zu dieser Liste gehörenden Apps angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="1c91a-139">The **Add apps** blade opens, showing you all apps that are part of this list.</span></span>

3.  <span data-ttu-id="1c91a-140">Wählen Sie alle Apps aus, die auf Ihre Unternehmensdaten zugreifen dürfen, und wählen Sie dann **OK** aus.</span><span class="sxs-lookup"><span data-stu-id="1c91a-140">Select each app you want to access your corporate data, and then choose **OK**.</span></span> <span data-ttu-id="1c91a-141">Das Blatt **Zulässige Apps** wird aktualisiert und zeigt alle ausgewählten Apps an.</span><span class="sxs-lookup"><span data-stu-id="1c91a-141">The **Allowed apps** blade gets updated showing you all selected apps.</span></span>

## <a name="add-a-store-app-to-your-allowed-apps-list"></a><span data-ttu-id="1c91a-142">Hinzufügen einer Store-App zur Liste der zulässigen Apps</span><span class="sxs-lookup"><span data-stu-id="1c91a-142">Add a Store app to your allowed apps list</span></span>

<span data-ttu-id="1c91a-143">**Hinzufügen eine Store-App**</span><span class="sxs-lookup"><span data-stu-id="1c91a-143">**To add a Store app**</span></span>

1.  <span data-ttu-id="1c91a-144">Wählen Sie auf dem Blatt **App-Richtlinie** den Namen Ihrer Richtlinie und im angezeigten Menü **Zulässige Apps** aus. Daraufhin werden alle Apps angezeigt, die bereits in der Liste für diese App-Schutzrichtlinie enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="1c91a-144">From the **App policy** blade, choose the name of your policy, then choose **Allowed apps** from the menu that appears showing all apps that are already included in the list for this app protection policy.</span></span>

2.  <span data-ttu-id="1c91a-145">Wählen Sie auf dem Blatt **Zulässige Apps** die Option **Apps hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="1c91a-145">From the **Allowed apps** blade, choose **Add apps**.</span></span>

3.  <span data-ttu-id="1c91a-146">Wählen Sie auf dem Blatt **Apps hinzufügen** die Option **Store-Apps** aus der Dropdownliste aus.</span><span class="sxs-lookup"><span data-stu-id="1c91a-146">On the **Add apps** blade, choose **Store apps** from the dropdown list.</span></span> <span data-ttu-id="1c91a-147">Auf dem Blatt werden dann Felder angezeigt, mit denen Sie einen **Herausgeber** und App-**Namen** hinzufügen können.</span><span class="sxs-lookup"><span data-stu-id="1c91a-147">The blade changes to show boxes for you to add a **publisher** and app **name**.</span></span>

4.  <span data-ttu-id="1c91a-148">Geben Sie den Namen der App und des jeweiligen Herausgebers ein und wählen Sie dann **OK** aus.</span><span class="sxs-lookup"><span data-stu-id="1c91a-148">Type the name of the app and the name of its publisher, and then choose **OK**.</span></span>

    > [!TIP]
    > <span data-ttu-id="1c91a-149">Im Folgenden wird ein Beispiel für eine App gezeigt: Der **Herausgeber** ist dabei *CN = Microsoft Corporation, O = Microsoft Corporation, L = Redmond, S = Washington, C = US* und der **Name** des Produkts lautet *Microsoft.MicrosoftAppForWindows*.</span><span class="sxs-lookup"><span data-stu-id="1c91a-149">Here’s an app example, where the **Publisher** is *CN=Microsoft Corporation, O=Microsoft Corporation, L=Redmond, S=Washington, C=US* and the Product **name** is *Microsoft.MicrosoftAppForWindows*.</span></span>

5.  <span data-ttu-id="1c91a-150">Nachdem Sie die Informationen in die Felder eingegeben haben, wählen Sie **OK** aus, um die App zur Liste **Zulässige Apps** hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="1c91a-150">After you’ve entered the info into the fields, choose **OK** to add the app to your **Allowed apps** list.</span></span>

> [!NOTE]
> <span data-ttu-id="1c91a-151">Um mehrere Store-Apps gleichzeitig hinzuzufügen, können Sie auf das Menü **(...)** am Ende der App-Zeile klicken. Anschließend können Sie weitere Apps hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="1c91a-151">To add multiple Store apps at the same time, you can click the menu **(…)** at the end of the app row, then continue to add more apps.</span></span> <span data-ttu-id="1c91a-152">Wenn Sie fertig sind, wählen Sie **OK** aus.</span><span class="sxs-lookup"><span data-stu-id="1c91a-152">Once you’re done, choose **OK**.</span></span>

## <a name="add-a-desktop-app-to-your-allowed-apps-list"></a><span data-ttu-id="1c91a-153">Hinzufügen einer Desktop-App zur Liste der zulässigen Apps</span><span class="sxs-lookup"><span data-stu-id="1c91a-153">Add a desktop app to your allowed apps list</span></span>

<span data-ttu-id="1c91a-154">**So fügen Sie eine Desktop-App hinzu**</span><span class="sxs-lookup"><span data-stu-id="1c91a-154">**To add a desktop app**</span></span>

1.  <span data-ttu-id="1c91a-155">Wählen Sie auf dem Blatt **App-Richtlinie** den Namen Ihrer Richtlinie und anschließend die Option **Zulässige Apps** aus.</span><span class="sxs-lookup"><span data-stu-id="1c91a-155">From the **App policy** blade, choose the name of your policy, and then choose **Allowed apps.**</span></span> <span data-ttu-id="1c91a-156">Das Blatt **Zulässige Apps** wird geöffnet, auf dem alle Apps angezeigt werden, die bereits in der Liste für diese App-Schutzrichtlinie enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="1c91a-156">The **Allowed apps** blade opens showing you all apps that are already included in the list for this app protection policy.</span></span>

2.  <span data-ttu-id="1c91a-157">Wählen Sie auf dem Blatt **Zulässige Apps** die Option **Apps hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="1c91a-157">From the **Allowed apps** blade, choose **Add apps**.</span></span>

3.  <span data-ttu-id="1c91a-158">Wählen Sie auf dem Blatt **Apps hinzufügen** die Option **Desktop-Apps** aus der Dropdownliste aus.</span><span class="sxs-lookup"><span data-stu-id="1c91a-158">On the **Add apps** blade, choose **Desktop apps** from the drop-down list.</span></span>

4.  <span data-ttu-id="1c91a-159">Nachdem Sie die Informationen in die Felder eingegeben haben, wählen Sie **OK** aus, um die App zur Liste **Zulässige Apps** hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="1c91a-159">After you entered the info into the fields, choose **OK** to add the app to your **Allowed apps** list.</span></span>

> [!NOTE]
> <span data-ttu-id="1c91a-160">Um mehrere **Desktop-Apps** gleichzeitig hinzuzufügen, können Sie auf das Menü **(...)** am Ende der App-Zeile klicken. Anschließend können Sie weitere Apps hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="1c91a-160">To add multiple **desktop apps** at the same time, you can click the menu **(…)** at the end of the app row, then continue to add more apps.</span></span> <span data-ttu-id="1c91a-161">Wenn Sie fertig sind, wählen Sie **OK** aus.</span><span class="sxs-lookup"><span data-stu-id="1c91a-161">Once you’re done, choose **OK**.</span></span>

## <a name="wip-learning"></a><span data-ttu-id="1c91a-162">WIP Learning</span><span class="sxs-lookup"><span data-stu-id="1c91a-162">WIP Learning</span></span>
<!---You've already defined WIP earlier in the topic. You don't need to keep doing so. --->
<span data-ttu-id="1c91a-163">Nachdem Sie die Apps hinzugefügt haben, die durch WIP geschützt werden sollen, müssen Sie mittels **WIP Learning** einen Schutzmodus anwenden.</span><span class="sxs-lookup"><span data-stu-id="1c91a-163">After you add the apps you want to protect with WIP, you need to apply a protection mode by using **WIP Learning**.</span></span>

### <a name="before-you-begin"></a><span data-ttu-id="1c91a-164">Vorbereitung</span><span class="sxs-lookup"><span data-stu-id="1c91a-164">Before you begin</span></span>

<span data-ttu-id="1c91a-165">WIP Learning ist ein Bericht, mit dem Sie Ihre WIP unbekannten Apps überwachen können.</span><span class="sxs-lookup"><span data-stu-id="1c91a-165">WIP Learning is a report that allows you to monitor your WIP-unknown apps.</span></span> <span data-ttu-id="1c91a-166">Unbekannte Apps sind Apps, die nicht von der IT-Abteilung Ihrer Organisation bereitgestellt wurden.</span><span class="sxs-lookup"><span data-stu-id="1c91a-166">The unknown apps are the ones not deployed by your organization’s IT department.</span></span> <span data-ttu-id="1c91a-167">Sie können diese Apps vor der Erzwingung von WIP im Modus „Blockieren“ über den Bericht exportieren und zu Ihren WIP-Richtlinien hinzufügen, um Produktivitätseinbußen zu verhindern.</span><span class="sxs-lookup"><span data-stu-id="1c91a-167">You can export these apps from the report and add them to your WIP policies to avoid productivity disruption before they enforce WIP in “Block” mode.</span></span>

<span data-ttu-id="1c91a-168">Es wird empfohlen, mit **Automatisch** oder **Außerkraftsetzungen zulassen** zu beginnen und bei einer kleinen Gruppe zu überprüfen, ob die Liste der zulässigen Apps die richtigen Apps enthält.</span><span class="sxs-lookup"><span data-stu-id="1c91a-168">We recommend that you start with **Silent** or **Allow Overrides** while verifying with a small group that you have the right apps on your allowed apps list.</span></span> <span data-ttu-id="1c91a-169">Wenn Sie fertig sind, können Sie Ihre endgültige Erzwingungsrichtlinie in **Blockieren** ändern.</span><span class="sxs-lookup"><span data-stu-id="1c91a-169">After you're done, you can change to your final enforcement policy, **Block**.</span></span>

### <a name="what-are-the-protection-modes"></a><span data-ttu-id="1c91a-170">Was sind Schutzmodi?</span><span class="sxs-lookup"><span data-stu-id="1c91a-170">What are the protection modes?</span></span>

#### <a name="block"></a><span data-ttu-id="1c91a-171">Blockieren</span><span class="sxs-lookup"><span data-stu-id="1c91a-171">Block</span></span>
<span data-ttu-id="1c91a-172">WIP prüft auf ungeeignete Datenfreigabeverfahren und hindert den Benutzer an der Durchführung der Aktion.</span><span class="sxs-lookup"><span data-stu-id="1c91a-172">WIP looks for inappropriate data sharing practices and stops the user from completing the action.</span></span> <span data-ttu-id="1c91a-173">Dies kann die Freigabe von Informationen über nicht geschützte Unternehmens-Apps hinweg sowie die Freigabe von Unternehmensdaten zwischen anderen Personen und Geräten außerhalb Ihrer Organisation einschließen.</span><span class="sxs-lookup"><span data-stu-id="1c91a-173">This can include sharing info across non-corporate-protected apps, and sharing corporate data between other people and devices outside of your organization.</span></span>

#### <a name="allow-overrides"></a><span data-ttu-id="1c91a-174">Außerkraftsetzungen zulassen</span><span class="sxs-lookup"><span data-stu-id="1c91a-174">Allow Overrides</span></span>
<span data-ttu-id="1c91a-175">WIP prüft auf ungeeignete Datenfreigabeverfahren, bei dem Benutzer gewarnt werden, wenn sie einen potenziell unsicheren Vorgang durchführen.</span><span class="sxs-lookup"><span data-stu-id="1c91a-175">WIP looks for inappropriate data sharing, warning users if they do something deemed potentially unsafe.</span></span> <span data-ttu-id="1c91a-176">In diesem Modus können Benutzer jedoch die Richtlinie überschreiben und die Daten freigeben. Die Aktion wird dabei in Ihrem Überwachungsprotokoll protokolliert.</span><span class="sxs-lookup"><span data-stu-id="1c91a-176">However, this mode lets the user override the policy and share the data, logging the action to your audit log.</span></span>

#### <a name="silent"></a><span data-ttu-id="1c91a-177">Automatisch</span><span class="sxs-lookup"><span data-stu-id="1c91a-177">Silent</span></span>
<span data-ttu-id="1c91a-178">WIP wird automatisch ausgeführt, wobei ungeeignete Datenfreigabeverfahren protokolliert werden. Dabei werden im Modus „Außerkraftsetzungen zulassen“ keine Vorgänge blockiert, die zu einer Mitarbeiterinteraktion auffordern würden.</span><span class="sxs-lookup"><span data-stu-id="1c91a-178">WIP runs silently, logging inappropriate data sharing, without blocking anything that would have been prompted for employee interaction while in Allow Override mode.</span></span> <span data-ttu-id="1c91a-179">Unzulässige Aktionen wie bei Apps, die unzulässigerweise versuchen, auf eine Netzwerkressource oder auf WIP-geschützte Daten zuzugreifen, werden trotzdem angehalten.</span><span class="sxs-lookup"><span data-stu-id="1c91a-179">Unallowed actions, like apps inappropriately trying to access a network resource or WIP-protected data, are still stopped.</span></span>

#### <a name="off-not-recommended"></a><span data-ttu-id="1c91a-180">Inaktiv (nicht empfohlen)</span><span class="sxs-lookup"><span data-stu-id="1c91a-180">Off (not recommended)</span></span>
<span data-ttu-id="1c91a-181">WIP ist deaktiviert und unterstützt nicht beim Schutz oder der Überwachung Ihrer Daten.</span><span class="sxs-lookup"><span data-stu-id="1c91a-181">WIP is turned off and doesn't help to protect or audit your data.</span></span>

<span data-ttu-id="1c91a-182">Nachdem Sie WIP deaktiviert haben, wird versucht, WIP-getaggte Dateien auf den lokalen Laufwerken zu entschlüsseln.</span><span class="sxs-lookup"><span data-stu-id="1c91a-182">After you turn off WIP, an attempt is made to decrypt any WIP-tagged files on the locally attached drives.</span></span> <span data-ttu-id="1c91a-183">Denken Sie daran, dass Ihre vorherigen Informationen zu Entschlüsselungen und Richtlinien nicht automatisch erneut angewendet werden, wenn Sie den WIP-Schutz wieder aktivieren.</span><span class="sxs-lookup"><span data-stu-id="1c91a-183">Be aware that previous decryption and policy info isn’t automatically reapplied if you turn WIP protection back on.</span></span>

### <a name="add-a-protection-mode"></a><span data-ttu-id="1c91a-184">Hinzufügen eines Schutzmodus</span><span class="sxs-lookup"><span data-stu-id="1c91a-184">Add a protection mode</span></span>

1.  <span data-ttu-id="1c91a-185">Wählen Sie auf dem Blatt **App-Richtlinie** den Namen Ihrer Richtlinie und anschließend die Option **Erforderliche Einstellungen** aus.</span><span class="sxs-lookup"><span data-stu-id="1c91a-185">From the **App policy** blade, choose the name of your policy, then chose **Required settings**.</span></span>

    ![Screenshot des Learning-Modus](./media/learning-mode-sc1.png)

1.  <span data-ttu-id="1c91a-187">Wählen Sie **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="1c91a-187">Choose **Save**.</span></span>

### <a name="use-wip-learning"></a><span data-ttu-id="1c91a-188">Verwenden von WIP Learning</span><span class="sxs-lookup"><span data-stu-id="1c91a-188">Use WIP Learning</span></span>

1. <span data-ttu-id="1c91a-189">Öffnen Sie das Azure-Portal.</span><span class="sxs-lookup"><span data-stu-id="1c91a-189">Open the Azure portal.</span></span> <span data-ttu-id="1c91a-190">Wählen Sie **Weitere Dienste** aus.</span><span class="sxs-lookup"><span data-stu-id="1c91a-190">Choose **More services**.</span></span> <span data-ttu-id="1c91a-191">Geben Sie **Intune** in das Filtertextfeld ein.</span><span class="sxs-lookup"><span data-stu-id="1c91a-191">Type **Intune** in the text box filter.</span></span>

3. <span data-ttu-id="1c91a-192">Klicken Sie auf **Intune** > **Mobile Apps**.</span><span class="sxs-lookup"><span data-stu-id="1c91a-192">Choose **Intune** > **Mobile Apps**.</span></span>

4. <span data-ttu-id="1c91a-193">Klicken Sie anschließend auf **Status des App-Schutzes** > **Berichte** > **Windows Information Protection-Tutorial**.</span><span class="sxs-lookup"><span data-stu-id="1c91a-193">Choose **App protection status** > **Reports** > **Windows Information Protection learning**.</span></span>  
 
    <span data-ttu-id="1c91a-194">Wenn dann die Apps im WIP Learning-Protokollierungsbericht angezeigt werden, können Sie sie zu Ihren App-Schutzrichtlinien hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="1c91a-194">Once you have the apps showing up in the WIP Learning logging report, you can add them to your app protection policies.</span></span>

## <a name="deploy-your-wip-app-protection-policy"></a><span data-ttu-id="1c91a-195">Bereitstellen der WIP-App-Schutzrichtlinie</span><span class="sxs-lookup"><span data-stu-id="1c91a-195">Deploy your WIP app protection policy</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1c91a-196">Dies gilt für WIP ohne Geräteregistrierung.</span><span class="sxs-lookup"><span data-stu-id="1c91a-196">This applies for WIP without device enrollment.</span></span>

<!---not sure why you need the Important note. Isn't this what the topic is about? app protection w/o enrollment?--->

<span data-ttu-id="1c91a-197">Nachdem Sie Ihre WIP-App-Schutzrichtlinie erstellt haben, müssen Sie sie Ihrer Organisation über MAM bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="1c91a-197">After you created your WIP app protection policy, you need to deploy it to your organization using MAM.</span></span>

1.  <span data-ttu-id="1c91a-198">Wählen Sie auf dem Blatt **App-Richtlinie** die neu erstellte App-Schutzrichtlinie aus. Wählen Sie anschließend **Benutzergruppen** > **Benutzergruppe hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="1c91a-198">On the **App policy** blade, choose your newly created app protection policy, choose **User groups** > **Add user group**.</span></span>

    <span data-ttu-id="1c91a-199">Auf dem Blatt **Benutzergruppe hinzufügen** wird eine Liste von Benutzergruppen geöffnet, die aus allen Sicherheitsgruppen in Azure Active Directory besteht.</span><span class="sxs-lookup"><span data-stu-id="1c91a-199">A list of user groups, made up of all the security groups in your Azure Active Directory, opens in the **Add user group** blade.</span></span>

1.  <span data-ttu-id="1c91a-200">Wählen Sie die Gruppe aus, auf die Ihre Richtlinie angewendet werden soll, und klicken Sie dann auf **Auswählen**, um die Richtlinie bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="1c91a-200">Choose the group you want your policy to apply to, then choose **Select** to deploy the policy.</span></span>
