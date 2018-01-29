---
title: "Hinzufügen von iOS-Branchen-Apps in Intune"
titlesuffix: Azure portal
description: "Erfahren Sie mehr über das Hinzufügen branchenspezifischer iOS-Apps zu Intune."
keywords: 
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 10/3/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 099101e8-4b22-40ac-ba19-82ba5c71944c
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: e4dd377bf878b3fb2d910df490e4fbc205f4f368
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2018
---
# <a name="how-to-add-ios-line-of-business-lob-apps-to-microsoft-intune"></a><span data-ttu-id="d7ba0-103">Hinzufügen von branchenspezifischen iOS-Apps in Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="d7ba0-103">How to add iOS line-of-business (LOB) apps to Microsoft Intune</span></span>

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="d7ba0-104">Mithilfe der Informationen in diesem Thema können Sie die branchenspezifischen iOS-Apps zu Intune hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="d7ba0-104">Use the information in this topic to help you add iOS line-of-business apps to Intune.</span></span>

>[!NOTE]
><span data-ttu-id="d7ba0-105">Während Benutzer von iOS-Geräten einige der integrierten iOS-Apps wie Stocks und Maps entfernen können, können Sie diese Apps über Intune nicht erneut bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="d7ba0-105">While users of iOS devices can remove some of the built-in iOS apps like Stocks, and Maps, you cannot use Intune to redeploy those apps.</span></span> <span data-ttu-id="d7ba0-106">Wenn Endbenutzer diese Apps löschen, müssen sie zum App Store navigieren und die Apps manuell erneut installieren.</span><span class="sxs-lookup"><span data-stu-id="d7ba0-106">If end users delete these apps, they must go to the app store, and manually re install them.</span></span>

## <a name="step-1---specify-the-software-setup-file"></a><span data-ttu-id="d7ba0-107">Schritt 1: Angeben der Softwaresetupdatei</span><span class="sxs-lookup"><span data-stu-id="d7ba0-107">Step 1 - Specify the software setup file</span></span>

1. <span data-ttu-id="d7ba0-108">Melden Sie sich im Azure-Portal an.</span><span class="sxs-lookup"><span data-stu-id="d7ba0-108">Sign in to the Azure portal.</span></span>
2. <span data-ttu-id="d7ba0-109">Wählen Sie **Weitere Dienste** > **Überwachung und Verwaltung** + **Intune** aus.</span><span class="sxs-lookup"><span data-stu-id="d7ba0-109">Choose **More Services** > **Monitoring + Management** + **Intune**.</span></span>
3. <span data-ttu-id="d7ba0-110">Wählen Sie auf dem Blatt **Intune** die Option **Apps verwalten** aus.</span><span class="sxs-lookup"><span data-stu-id="d7ba0-110">On the **Intune** blade, choose **Manage apps**.</span></span>
4. <span data-ttu-id="d7ba0-111">Wählen Sie in der Workload **Mobile Apps** die Option **Verwalten** > **Apps** aus.</span><span class="sxs-lookup"><span data-stu-id="d7ba0-111">In the **Mobile apps** workload, choose **Manage** > **Apps**.</span></span>
5. <span data-ttu-id="d7ba0-112">Wählen Sie über der Liste der Apps **Hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="d7ba0-112">Above the list of apps, choose **Add**.</span></span>
6. <span data-ttu-id="d7ba0-113">Wählen Sie auf dem Blatt **App hinzufügen** die Option **Branchen-App** aus.</span><span class="sxs-lookup"><span data-stu-id="d7ba0-113">In the **Add App** blade, choose **Line-of-business app**.</span></span>

## <a name="step-2---configure-the-app-package-file"></a><span data-ttu-id="d7ba0-114">Schritt 2: Konfigurieren der App-Paketdatei</span><span class="sxs-lookup"><span data-stu-id="d7ba0-114">Step 2 - Configure the app package file</span></span>

1. <span data-ttu-id="d7ba0-115">Wählen Sie auf dem Blatt **App hinzufügen** die Option **App-Paketdatei** aus.</span><span class="sxs-lookup"><span data-stu-id="d7ba0-115">On the **Add app** blade, choose **App package** file.</span></span>
2. <span data-ttu-id="d7ba0-116">Wählen Sie auf dem Blatt **App-Paketdatei** die Durchsuchen-Schaltfläche aus, und wählen Sie eine iOS-Installationsdatei mit der Erweiterung **IPA** aus.</span><span class="sxs-lookup"><span data-stu-id="d7ba0-116">On the **App package** file blade, choose the browse button, and select an iOS installation file with the extension **.ipa**.</span></span>
3. <span data-ttu-id="d7ba0-117">Wenn Sie fertig sind, wählen Sie **OK** aus.</span><span class="sxs-lookup"><span data-stu-id="d7ba0-117">When you are finished, choose **OK**.</span></span>


## <a name="step-3---configure-app-information"></a><span data-ttu-id="d7ba0-118">Schritt 3: Konfigurieren von App-Informationen</span><span class="sxs-lookup"><span data-stu-id="d7ba0-118">Step 3 - Configure app information</span></span>

1. <span data-ttu-id="d7ba0-119">Wählen Sie auf dem Blatt **App hinzufügen** die Option **App-Paketdatei** aus.</span><span class="sxs-lookup"><span data-stu-id="d7ba0-119">On the **Add app** blade, choose **App package** file.</span></span>
2. <span data-ttu-id="d7ba0-120">Fügen Sie auf dem Blatt **App-Information** Details zu Ihrer App hinzu.</span><span class="sxs-lookup"><span data-stu-id="d7ba0-120">On the **App information** blade, add the details for your app.</span></span> <span data-ttu-id="d7ba0-121">Abhängig von der ausgewählten App werden einige der Werte auf diesem Blatt möglicherweise automatisch ausgefüllt:</span><span class="sxs-lookup"><span data-stu-id="d7ba0-121">Depending on the app you have chosen, some of the values in this blade might have been automatically filled-in:</span></span>
    - <span data-ttu-id="d7ba0-122">**Name:** Geben Sie den Namen der App ein, der im Unternehmensportal angezeigt werde soll.</span><span class="sxs-lookup"><span data-stu-id="d7ba0-122">**Name** - Enter the name of the app to be displayed in the company portal.</span></span> <span data-ttu-id="d7ba0-123">Stellen Sie sicher, dass alle App-Namen eindeutig sind.</span><span class="sxs-lookup"><span data-stu-id="d7ba0-123">Make sure all app names that you use are unique.</span></span> <span data-ttu-id="d7ba0-124">Wenn ein App-Name zweimal vergeben wird, wird den Benutzern im Unternehmensportal nur eine der Apps angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d7ba0-124">If the same app name exists twice, only one of the apps will be displayed to users in the company portal.</span></span>
    - <span data-ttu-id="d7ba0-125">**Beschreibung:** Geben Sie eine Beschreibung für die App ein, die den Benutzern im Unternehmensportal angezeigt werden soll.</span><span class="sxs-lookup"><span data-stu-id="d7ba0-125">**Description** - Enter a description for the app to be displayed to users in the company portal.</span></span>
    - <span data-ttu-id="d7ba0-126">**Herausgeber:** Geben Sie den Namen des Herausgebers der App ein.</span><span class="sxs-lookup"><span data-stu-id="d7ba0-126">**Publisher** - Enter the name of the publisher of the app.</span></span>
    - <span data-ttu-id="d7ba0-127">**Mindestens erforderliches Betriebssystem:** Wählen Sie in der Liste die mindestens erforderliche Betriebssystemversion aus, auf der die App installiert werden kann.</span><span class="sxs-lookup"><span data-stu-id="d7ba0-127">**Minimum Operating System** - From the list, choose the minimum operating system version on which the app can be installed.</span></span> <span data-ttu-id="d7ba0-128">Wenn Sie die App einem Gerät mit einem älteren Betriebssystem zuweisen, wird sie nicht installiert.</span><span class="sxs-lookup"><span data-stu-id="d7ba0-128">If you assign the app to a device with an earlier operating system, it will not be installed.</span></span>
    - <span data-ttu-id="d7ba0-129">**Kategorie:** Wählen Sie eine der integrierten oder von Ihnen erstellten App-Kategorien aus.</span><span class="sxs-lookup"><span data-stu-id="d7ba0-129">**Category** - Select one or more of the built-in app categories, or a category you created.</span></span> <span data-ttu-id="d7ba0-130">Dadurch ist es für Benutzer einfacher, die App im Unternehmensportal zu finden.</span><span class="sxs-lookup"><span data-stu-id="d7ba0-130">This makes it easier for users to find the app when they browse the company portal.</span></span>
    - <span data-ttu-id="d7ba0-131">**Diese App als ausgewählte App im Unternehmensportal anzeigen:** Zeigen Sie die App auf der Hauptseite des Unternehmensportal hervorgehoben an, wenn Benutzer nach Apps suchen.</span><span class="sxs-lookup"><span data-stu-id="d7ba0-131">**Display this as a featured app in the Company Portal** - Display the app prominently on the main page of the company portal when users browse for apps.</span></span>
    - <span data-ttu-id="d7ba0-132">**Informations-URL:** Geben Sie optional eine URL zu einer Website ein, die Informationen über diese App enthält.</span><span class="sxs-lookup"><span data-stu-id="d7ba0-132">**Information URL** - Optionally, enter the URL of a website that contains information about this app.</span></span> <span data-ttu-id="d7ba0-133">Diese URL wird Benutzern im Unternehmensportal angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d7ba0-133">The URL is displayed to users in the company portal.</span></span>
    - <span data-ttu-id="d7ba0-134">**URL zu den Datenschutzbestimmungen:** Geben Sie optional eine URL zu einer Website ein, die Datenschutzinformationen für diese App enthält.</span><span class="sxs-lookup"><span data-stu-id="d7ba0-134">**Privacy URL** - Optionally, enter the URL of a website that contains privacy information for this app.</span></span> <span data-ttu-id="d7ba0-135">Diese URL wird Benutzern im Unternehmensportal angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d7ba0-135">The URL is displayed to users in the company portal.</span></span>
    - <span data-ttu-id="d7ba0-136">**Entwickler:** Geben Sie optional den Namen des App-Entwicklers ein.</span><span class="sxs-lookup"><span data-stu-id="d7ba0-136">**Developer** - Optionally, enter the name of the app developer.</span></span>
    - <span data-ttu-id="d7ba0-137">**Besitzer:** Geben Sie optional einen Namen für den Besitzer dieser App ein, z.B. **Personalabteilung**.</span><span class="sxs-lookup"><span data-stu-id="d7ba0-137">**Owner** - Optionally, enter a name for the owner of this app, for example, **HR department**.</span></span>
    - <span data-ttu-id="d7ba0-138">**Anmerkungen:** Geben Sie Hinweise zu dieser App ein.</span><span class="sxs-lookup"><span data-stu-id="d7ba0-138">**Notes** - Enter any notes you would like to associate with this app.</span></span>
    - <span data-ttu-id="d7ba0-139">**Logo:** Laden Sie ein Symbol hoch, das der App zugeordnet wird.</span><span class="sxs-lookup"><span data-stu-id="d7ba0-139">**Logo** - Upload an icon that is associated with the app.</span></span> <span data-ttu-id="d7ba0-140">Dieses Symbol wird gemeinsam mit der App angezeigt, wenn der Benutzer das Unternehmensportal durchsucht.</span><span class="sxs-lookup"><span data-stu-id="d7ba0-140">This is the icon that is displayed with the app when users browse the company portal.</span></span>
3. <span data-ttu-id="d7ba0-141">Wenn Sie fertig sind, wählen Sie **OK** aus.</span><span class="sxs-lookup"><span data-stu-id="d7ba0-141">When you are finished, choose **OK**.</span></span>

## <a name="step-4---finish-up"></a><span data-ttu-id="d7ba0-142">Schritt 4: Fertig stellen</span><span class="sxs-lookup"><span data-stu-id="d7ba0-142">Step 4 - Finish up</span></span>

1. <span data-ttu-id="d7ba0-143">Prüfen Sie Ihre Angaben auf dem Blatt **App hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="d7ba0-143">On the **Add app** blade, verify that the details for your app is correct.</span></span>
2. <span data-ttu-id="d7ba0-144">Wählen Sie **Hinzufügen** aus, um die App in Intune hochzuladen.</span><span class="sxs-lookup"><span data-stu-id="d7ba0-144">Choose **Add**, to upload the app to Intune.</span></span>

<span data-ttu-id="d7ba0-145">Die von Ihnen erstellte App erscheint in der Liste der Apps, in der Sie sie den ausgewählten Gruppen zuweisen können.</span><span class="sxs-lookup"><span data-stu-id="d7ba0-145">The app you have created appears in the apps list where you can assign it to the groups you choose.</span></span> <span data-ttu-id="d7ba0-146">Hilfe finden Sie unter [Zuweisen von Apps zu Gruppen](apps-deploy.md).</span><span class="sxs-lookup"><span data-stu-id="d7ba0-146">For help, see [How to assign apps to groups](apps-deploy.md).</span></span>

## <a name="step-5---update-a-line-of-business-app"></a><span data-ttu-id="d7ba0-147">Schritt 5: Aktualisieren einer branchenspezifischen App</span><span class="sxs-lookup"><span data-stu-id="d7ba0-147">Step 5 - Update a line-of-business app</span></span>

[!INCLUDE [shared-proc-lob-updateapp](./includes/shared-proc-lob-updateapp.md)]

<span data-ttu-id="d7ba0-148">Hinweis: Für die Intune-Dienst erfolgreich eine neue IPA-Datei auf dem Gerät bereitstellen müssen Sie die CFBundleVersion-Zeichenfolge in der Datei "Info.plist" in Ihrer Datei IPA-Paket erhöhen.</span><span class="sxs-lookup"><span data-stu-id="d7ba0-148">Note: For the Intune service to successfully deploy a new IPA file to the device you must increment the CFBundleVersion string in the Info.plist file in your IPA package.</span></span>

## <a name="next-steps"></a><span data-ttu-id="d7ba0-149">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="d7ba0-149">Next steps</span></span>

<span data-ttu-id="d7ba0-150">Die von Ihnen erstellte App wird in der Liste der Apps angezeigt.</span><span class="sxs-lookup"><span data-stu-id="d7ba0-150">The app you have created is displayed in the apps list.</span></span> <span data-ttu-id="d7ba0-151">Sie können sie jetzt den ausgewählten Gruppen zuweisen.</span><span class="sxs-lookup"><span data-stu-id="d7ba0-151">You can now assign it to the groups you choose.</span></span> <span data-ttu-id="d7ba0-152">Hilfe finden Sie unter [Zuweisen von Apps zu Gruppen](apps-deploy.md).</span><span class="sxs-lookup"><span data-stu-id="d7ba0-152">For help, see [How to assign apps to groups](apps-deploy.md).</span></span>

<span data-ttu-id="d7ba0-153">Erfahren Sie mehr darüber, wie Sie die Eigenschaften und Zuweisungen Ihrer App überwachen können.</span><span class="sxs-lookup"><span data-stu-id="d7ba0-153">Learn more about the ways in which you can monitor the properties and assignment of your app.</span></span> <span data-ttu-id="d7ba0-154">Weitere Informationen finden Sie unter [Überwachen von App-Informationen und -Zuweisungen](apps-monitor.md).</span><span class="sxs-lookup"><span data-stu-id="d7ba0-154">For more information, see [How to monitor app information and assignments](apps-monitor.md).</span></span>

<span data-ttu-id="d7ba0-155">Erfahren Sie mehr über den Kontext Ihrer App in Intune.</span><span class="sxs-lookup"><span data-stu-id="d7ba0-155">Learn more about the context of your app in Intune.</span></span> <span data-ttu-id="d7ba0-156">Weitere Informationen finden Sie unter [Übersicht über die Lebenszyklen von Geräten und Apps](introduction-device-app-lifecycles.md).</span><span class="sxs-lookup"><span data-stu-id="d7ba0-156">For more information, see [Overview of device and app lifecycles](introduction-device-app-lifecycles.md)</span></span>
