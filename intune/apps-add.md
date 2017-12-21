---
title: "Hinzufügen von Apps zu Microsoft Intune"
titlesuffix: Azure portal
description: "Mit diesen Vorgehensweisen können Sie Ihre Apps in Intune für die Zuweisung zu Benutzern und Geräten vorbereiten. \""
keywords: 
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 07/17/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a1ded457-0ecf-4f9c-a2d2-857d57f8d30a
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 108f789f16304498cf54387326d112353bf70aa2
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2017
---
# <a name="how-to-add-an-app-to-microsoft-intune"></a><span data-ttu-id="420bc-104">So fügen Sie eine App zu Microsoft Intune hinzu</span><span class="sxs-lookup"><span data-stu-id="420bc-104">How to add an app to Microsoft Intune</span></span>

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="420bc-105">Bevor Sie Apps verwalten und Benutzern zuweisen können, müssen Sie diese in Intune hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="420bc-105">Before you can manage and assign apps for your users, you must add them to Intune.</span></span> <span data-ttu-id="420bc-106">Intune unterstützt eine ganze Palette unterschiedlicher App-Typen, die Optionen können sich je nach Typ unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="420bc-106">Intune supports a wide range of different app types, and the options might be different for each type.</span></span>

<span data-ttu-id="420bc-107">Über Intune können Sie folgende App-Typen hinzufügen und zuweisen:</span><span class="sxs-lookup"><span data-stu-id="420bc-107">Intune lets you add and assign these app types:</span></span>

![Von Intune unterstützte App-Typen](./media/app-types.png)

<span data-ttu-id="420bc-109">Die folgenden Plattformen werden unterstützt.</span><span class="sxs-lookup"><span data-stu-id="420bc-109">The following platforms are supported.</span></span>

- <span data-ttu-id="420bc-110">Android Store-Apps</span><span class="sxs-lookup"><span data-stu-id="420bc-110">Android store apps</span></span>
- <span data-ttu-id="420bc-111">Branchenspezifische Android-Apps</span><span class="sxs-lookup"><span data-stu-id="420bc-111">Android line-of-business (LOB) apps</span></span>
- <span data-ttu-id="420bc-112">iOS Store-Apps</span><span class="sxs-lookup"><span data-stu-id="420bc-112">iOS store apps</span></span>
- <span data-ttu-id="420bc-113">Branchenspezifische iOS-Apps</span><span class="sxs-lookup"><span data-stu-id="420bc-113">iOS line-of-business (LOB) apps</span></span>
- <span data-ttu-id="420bc-114">Web-Apps</span><span class="sxs-lookup"><span data-stu-id="420bc-114">Web apps</span></span>
- <span data-ttu-id="420bc-115">Windows Phone 8.1 Store-Apps</span><span class="sxs-lookup"><span data-stu-id="420bc-115">Windows Phone 8.1 store apps</span></span>
- <span data-ttu-id="420bc-116">Branchenspezifische Windows Phone-Apps (XAP-Dateien)</span><span class="sxs-lookup"><span data-stu-id="420bc-116">Windows Phone line-of-business apps (.xap files)</span></span>
- <span data-ttu-id="420bc-117">Windows Store-Apps</span><span class="sxs-lookup"><span data-stu-id="420bc-117">Windows store apps</span></span>
- <span data-ttu-id="420bc-118">Branchenspezifische Windows-Apps (nur MSI-Dateien)</span><span class="sxs-lookup"><span data-stu-id="420bc-118">Windows line-of-business apps (.msi files only)</span></span>

>[!TIP]
> <span data-ttu-id="420bc-119">Eine branchenspezifische App ist eine App, die Sie nicht über einen App Store, sondern über die App-Installationsdatei installieren.</span><span class="sxs-lookup"><span data-stu-id="420bc-119">A line-of-business (or LOB) app is one that you do not install from an app store, but install from the app installation file.</span></span> <span data-ttu-id="420bc-120">Um beispielsweise eine branchenspezifische iOS-App zu installieren, fügen Sie die Anwendungsarchivdatei (mit der Erweiterung „.ipa“) hinzu.</span><span class="sxs-lookup"><span data-stu-id="420bc-120">For example, to install an iOS LOB app, you add the application archive file (with the extension .ipa).</span></span> <span data-ttu-id="420bc-121">In der Regel handelt es sich um Apps, die intern geschrieben wurden.</span><span class="sxs-lookup"><span data-stu-id="420bc-121">These are typically apps you have written in-house.</span></span>

## <a name="before-you-start"></a><span data-ttu-id="420bc-122">Vorbereitung</span><span class="sxs-lookup"><span data-stu-id="420bc-122">Before you start</span></span>

<span data-ttu-id="420bc-123">Beachten Sie die folgenden Punkte, bevor Sie damit beginnen, Apps hinzuzufügen und zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="420bc-123">Consider the following points before you begin to add and assign apps.</span></span>

- <span data-ttu-id="420bc-124">Wenn Sie eine App aus einem Store hinzufügen und zuweisen, müssen Endbenutzer über ein Konto bei diesem Store verfügen, um die App installieren zu können.</span><span class="sxs-lookup"><span data-stu-id="420bc-124">When you add and assign an app from a store, end users must have an account with that store in order to be able to install the app.</span></span>
- <span data-ttu-id="420bc-125">Einige von Ihnen zugewiesenen Apps oder Elemente sind möglicherweise von integrierten iOS-Apps abhängig.</span><span class="sxs-lookup"><span data-stu-id="420bc-125">Some apps or items you assign might be dependent on built-in iOS apps.</span></span> <span data-ttu-id="420bc-126">Wenn Sie z. B. ein Buch aus dem iOS-Store zuweisen, muss die iBooks-App auf dem Gerät vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="420bc-126">For example, if you assign a book from the iOS store, then the iBooks app must be present on the device.</span></span> <span data-ttu-id="420bc-127">Wenn Sie die integrierte iBooks-App entfernt haben, können Sie Intune nicht dazu verwenden, sie wieder zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="420bc-127">If you have removed the iBooks built-in app, you cannot use Intune to reinstate it.</span></span>

## <a name="cloud-storage-space"></a><span data-ttu-id="420bc-128">Cloudspeicherplatz</span><span class="sxs-lookup"><span data-stu-id="420bc-128">Cloud storage space</span></span>
<span data-ttu-id="420bc-129">Alle Apps, die Sie mithilfe des Software-Installationsprogrammtyps erstellen (beispielsweise eine branchenspezifische App), werden paketiert und in den Intune-Cloudspeicher hochgeladen.</span><span class="sxs-lookup"><span data-stu-id="420bc-129">All apps that you create by using the software installer installation type (for example, a line-of-business app) are packaged and uploaded to Intune cloud storage.</span></span> <span data-ttu-id="420bc-130">Ein Testabonnement von Intune enthält 2 GB cloudbasierten Speicher, der zum Speichern von verwalteten Apps und Updates verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="420bc-130">A trial subscription of Intune includes 2 gigabytes (GB) of cloud-based storage that is used to store managed apps and updates.</span></span> <span data-ttu-id="420bc-131">Ein vollständiges Abonnement enthält 20 GB Speicherplatz.</span><span class="sxs-lookup"><span data-stu-id="420bc-131">A full subscription includes 20 GB of storage space.</span></span>

<span data-ttu-id="420bc-132">Sie können zusätzlichen Speicher für Intune mit Ihrer ursprünglichen Zahlungsweise erwerben.</span><span class="sxs-lookup"><span data-stu-id="420bc-132">You can purchase additional storage for Intune using your original purchase method.</span></span>  <span data-ttu-id="420bc-133">Wenn Sie per Rechnung oder Kreditkarte gezahlt haben, besuchen Sie das [Portal zur Abonnementverwaltung](https://portal.office.com/adminportal/home?switchtomodern=true#/subscriptions).</span><span class="sxs-lookup"><span data-stu-id="420bc-133">If you paid by invoice or credit card, visit the [Subscription Management portal](https://portal.office.com/adminportal/home?switchtomodern=true#/subscriptions).</span></span>  <span data-ttu-id="420bc-134">Wenden Sie sich alternativ an Ihren Partner oder Vertriebsmitarbeiter.</span><span class="sxs-lookup"><span data-stu-id="420bc-134">Otherwise, contact your partner or sales associate.</span></span>

<span data-ttu-id="420bc-135">Anforderungen für Cloudspeicherplatz:</span><span class="sxs-lookup"><span data-stu-id="420bc-135">Requirements for cloud storage space are as follows:</span></span>

-   <span data-ttu-id="420bc-136">Alle App-Installationsdateien müssen sich im selben Ordner befinden.</span><span class="sxs-lookup"><span data-stu-id="420bc-136">All app installation files must be in the same folder.</span></span>
-   <span data-ttu-id="420bc-137">Die maximale Dateigröße für hochgeladene Dateien beträgt 2 GB.</span><span class="sxs-lookup"><span data-stu-id="420bc-137">The maximum file size for any file that you upload is 2 GB.</span></span>

## <a name="how-to-create-and-edit-categories-for-apps"></a><span data-ttu-id="420bc-138">Erstellen und Bearbeiten von Kategorien für Apps</span><span class="sxs-lookup"><span data-stu-id="420bc-138">How to create and edit categories for apps</span></span>

<span data-ttu-id="420bc-139">Mithilfe von App-Kategorien können Sie Apps sortieren, damit Benutzer sie einfacher im Unternehmensportal finden können.</span><span class="sxs-lookup"><span data-stu-id="420bc-139">App categories can be used to help you sort apps to make them easier for users to find in the company portal.</span></span> <span data-ttu-id="420bc-140">Sie können einer App auch mehrere Kategorien zuweisen, z.B. **Entwickler-Apps** oder **Kommunikations-Apps**.</span><span class="sxs-lookup"><span data-stu-id="420bc-140">You can assign one or more categories to an app, for example, **Developer apps**, or **Communication apps**.</span></span>
<span data-ttu-id="420bc-141">Wenn Sie eine App in Intune hinzufügen, können Sie die gewünschte Kategorie auswählen.</span><span class="sxs-lookup"><span data-stu-id="420bc-141">When you add an app to Intune, you are given the option to select the category you want.</span></span> <span data-ttu-id="420bc-142">Verwenden Sie die plattformspezifischen Themen, um eine App hinzuzufügen und Kategorien zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="420bc-142">Use the platform-specific topics to add an app, and assign categories.</span></span> <span data-ttu-id="420bc-143">Gehen Sie zum Erstellen und Bearbeiten Ihre eigenen Kategorien folgendermaßen vor:</span><span class="sxs-lookup"><span data-stu-id="420bc-143">To create and edit your own categories, use the following procedure:</span></span>

1. <span data-ttu-id="420bc-144">Melden Sie sich beim Azure-Portal an.</span><span class="sxs-lookup"><span data-stu-id="420bc-144">Sign into the Azure portal.</span></span>
2. <span data-ttu-id="420bc-145">Wählen Sie **Weitere Dienste** > **Überwachung und Verwaltung** > **Intune** aus.</span><span class="sxs-lookup"><span data-stu-id="420bc-145">Choose **More Services** > **Monitoring + Management** > **Intune**.</span></span>
3. <span data-ttu-id="420bc-146">Wählen Sie auf dem Blatt **Intune** die Option **Mobile Apps** aus.</span><span class="sxs-lookup"><span data-stu-id="420bc-146">On the **Intune** blade, choose **Mobile apps**.</span></span>
4. <span data-ttu-id="420bc-147">Wählen Sie in der Workload **Mobile Apps** die Option **Setup** > **App-Kategorien** aus.</span><span class="sxs-lookup"><span data-stu-id="420bc-147">In the **Mobile apps** workload, choose **Setup** > **App categories**.</span></span>
5. <span data-ttu-id="420bc-148">Auf dem Blatt **App-Kategorien** wird eine Liste der aktuellen Kategorien angezeigt.</span><span class="sxs-lookup"><span data-stu-id="420bc-148">On the **App categories** blade, a list of the current categories is shown.</span></span> <span data-ttu-id="420bc-149">Wählen Sie eine der folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="420bc-149">Choose one of the following actions:</span></span>
    - <span data-ttu-id="420bc-150">**Erstellen einer Kategorie:** Geben Sie auf dem Blatt **Kategorie erstellen** einen Namen für die neue Kategorie ein.</span><span class="sxs-lookup"><span data-stu-id="420bc-150">**Create a category** - On the **Create category** blade, enter a name for the new category.</span></span> <span data-ttu-id="420bc-151">Namen können in nur einer Sprache eingegeben werden, und werden von Intune nicht übersetzt.</span><span class="sxs-lookup"><span data-stu-id="420bc-151">Names can be entered in one language only, and are not translated by Intune.</span></span> <span data-ttu-id="420bc-152">Klicken Sie auf **Erstellen**, wenn Sie fertig sind.</span><span class="sxs-lookup"><span data-stu-id="420bc-152">When you are done, click **Create**.</span></span>
    - <span data-ttu-id="420bc-153">**Bearbeiten einer Kategorie:** Wählen Sie für jede Kategorie in der Liste „**...**“ aus.</span><span class="sxs-lookup"><span data-stu-id="420bc-153">**Edit a category** - For any category in the list, choose '**...**'.</span></span> <span data-ttu-id="420bc-154">Auf dem Blatt **Eigenschaften** können Sie einen neuen Namen für die Kategorie eingeben oder die Kategorie löschen.</span><span class="sxs-lookup"><span data-stu-id="420bc-154">On the **Properties** blade, you can enter a new name for the category, or delete the category.</span></span>


## <a name="apps-added-automatically-by-intune"></a><span data-ttu-id="420bc-155">Von Intune automatisch hinzugefügte Apps</span><span class="sxs-lookup"><span data-stu-id="420bc-155">Apps added automatically by Intune</span></span>

<span data-ttu-id="420bc-156">Zuvor enthielt Intune eine Reihe integrierter Apps, die Sie rasch zuweisen konnten.</span><span class="sxs-lookup"><span data-stu-id="420bc-156">Previously, Intune contained a number of built-in apps that you could quickly assign.</span></span> <span data-ttu-id="420bc-157">Auf Grundlage Ihrer Feedbacks haben wir diese Liste entfernt, und es werden keine integrierten Apps mehr angezeigt.</span><span class="sxs-lookup"><span data-stu-id="420bc-157">Based on your feedback, we have removed this list, and you will no longer see built-in apps.</span></span>
<span data-ttu-id="420bc-158">Wenn Sie jedoch schon integrierte Apps zugewiesen haben, werden sie noch immer auf der App-Liste angezeigt.</span><span class="sxs-lookup"><span data-stu-id="420bc-158">However, if you have already assigned any built-in apps, these will still be visible in the list of apps.</span></span> <span data-ttu-id="420bc-159">Sie können diese Apps weiter nach Bedarf zuweisen.</span><span class="sxs-lookup"><span data-stu-id="420bc-159">You can continue to assign these apps as required.</span></span>
<span data-ttu-id="420bc-160">Es ist geplant, in einer späteren Version eine einfachere Methode hinzuzufügen, um integrierte Apps über das Azure-Portal auszuwählen und zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="420bc-160">In a later release, we plan to add an easier method to select and assign built-in apps from the Azure portal.</span></span>

## <a name="next-steps"></a><span data-ttu-id="420bc-161">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="420bc-161">Next steps</span></span>

<span data-ttu-id="420bc-162">Wählen Sie eines der folgenden Themen, um zu erfahren, wie Sie Apps für jede Plattform in Intune hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="420bc-162">Choose one of the following topics to find out how to add apps for each platform to Intune:</span></span>

- [<span data-ttu-id="420bc-163">Android Store-Apps</span><span class="sxs-lookup"><span data-stu-id="420bc-163">Android store apps</span></span>](store-apps-android.md)
- [<span data-ttu-id="420bc-164">Android-Branchen-Apps</span><span class="sxs-lookup"><span data-stu-id="420bc-164">Android LOB apps</span></span>](lob-apps-android.md)
- [<span data-ttu-id="420bc-165">iOS Store-Apps</span><span class="sxs-lookup"><span data-stu-id="420bc-165">iOS store apps</span></span>](store-apps-ios.md)
- [<span data-ttu-id="420bc-166">iOS-Branchen-Apps</span><span class="sxs-lookup"><span data-stu-id="420bc-166">iOS LOB apps</span></span>](lob-apps-ios.md)
- [<span data-ttu-id="420bc-167">Web-Apps (für alle Plattformen)</span><span class="sxs-lookup"><span data-stu-id="420bc-167">Web apps (for all platforms)</span></span>](web-app.md)
- [<span data-ttu-id="420bc-168">Windows Phone 8.1 Store-Apps</span><span class="sxs-lookup"><span data-stu-id="420bc-168">Windows Phone 8.1 store apps</span></span>](store-apps-windows-phone-8-1.md)
- [<span data-ttu-id="420bc-169">Branchenspezifische Windows Phone-Apps</span><span class="sxs-lookup"><span data-stu-id="420bc-169">Windows Phone LOB apps</span></span>](lob-apps-windows-phone.md)
- [<span data-ttu-id="420bc-170">Windows Store-Apps</span><span class="sxs-lookup"><span data-stu-id="420bc-170">Windows store apps</span></span>](store-apps-windows.md)
- [<span data-ttu-id="420bc-171">Branchenspezifische Windows-Apps</span><span class="sxs-lookup"><span data-stu-id="420bc-171">Windows LOB app</span></span>](lob-apps-windows.md)
- [<span data-ttu-id="420bc-172">Office 365 apps for Windows 10 (Office 365-Apps für Windows 10)</span><span class="sxs-lookup"><span data-stu-id="420bc-172">Office 365 apps for Windows 10</span></span>](apps-add-office365.md)

