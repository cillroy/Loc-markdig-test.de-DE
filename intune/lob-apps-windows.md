---
title: "Hinzufügen branchenspezifischer Windows-Apps zu Intune"
titlesuffix: Azure portal
description: "Erfahren Sie mehr über das Hinzufügen branchenspezifischer Windows-Apps zu Intune."
keywords: 
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 10/3/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f81c5f82-5cfa-4b97-9f73-d6cf77c06896
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 33959b941e39d8694387770e1f3264d74647de69
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2017
---
# <a name="how-to-add-windows-line-of-business-lob-apps-to-microsoft-intune"></a><span data-ttu-id="52f0e-103">Informationen zum Hinzufügen branchenspezifischer Windows-Apps zu Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="52f0e-103">How to add Windows line-of-business (LOB) apps to Microsoft Intune</span></span>

[!INCLUDE[azure_portal](./includes/azure_portal.md)]


## <a name="step-1---specify-the-software-setup-file"></a><span data-ttu-id="52f0e-104">Schritt 1: Angeben der Softwaresetupdatei</span><span class="sxs-lookup"><span data-stu-id="52f0e-104">Step 1 - Specify the software setup file</span></span>

1. <span data-ttu-id="52f0e-105">Melden Sie sich im Azure-Portal an.</span><span class="sxs-lookup"><span data-stu-id="52f0e-105">Sign in to the Azure portal.</span></span>
2. <span data-ttu-id="52f0e-106">Wählen Sie **Weitere Dienste** > **Überwachung und Verwaltung** + **Intune** aus.</span><span class="sxs-lookup"><span data-stu-id="52f0e-106">Choose **More Services** > **Monitoring + Management** + **Intune**.</span></span>
3. <span data-ttu-id="52f0e-107">Wählen Sie auf dem Blatt **Intune** die Option **Apps verwalten** aus.</span><span class="sxs-lookup"><span data-stu-id="52f0e-107">On the **Intune** blade, choose **Manage apps**.</span></span>
4. <span data-ttu-id="52f0e-108">Wählen Sie in der Workload **Mobile Apps** die Option **Verwalten** > **Apps** aus.</span><span class="sxs-lookup"><span data-stu-id="52f0e-108">In the **Mobile apps** workload, choose **Manage** > **Apps**.</span></span>
5. <span data-ttu-id="52f0e-109">Wählen Sie über der Liste der Apps **Hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="52f0e-109">Above the list of apps, choose **Add**.</span></span>
6. <span data-ttu-id="52f0e-110">Wählen Sie auf dem Blatt **App hinzufügen** die Option **Branchen-App** aus.</span><span class="sxs-lookup"><span data-stu-id="52f0e-110">In the **Add App** blade, choose **Line-of-business app**.</span></span>

## <a name="step-2---configure-the-app-package-file"></a><span data-ttu-id="52f0e-111">Schritt 2: Konfigurieren der App-Paketdatei</span><span class="sxs-lookup"><span data-stu-id="52f0e-111">Step 2 - Configure the app package file</span></span>

1. <span data-ttu-id="52f0e-112">Wählen Sie auf dem Blatt **App hinzufügen** die Option **App-Paketdatei** aus.</span><span class="sxs-lookup"><span data-stu-id="52f0e-112">On the **Add app** blade, choose **App package** file.</span></span>
2. <span data-ttu-id="52f0e-113">Klicken Sie auf dem Blatt **App-Paketdatei** auf die Schaltfläche „Durchsuchen“, und wählen Sie eine Windows-Installationsdatei mit der Erweiterung **.msi**, **.appx** oder **.appxbundle** aus.</span><span class="sxs-lookup"><span data-stu-id="52f0e-113">On the **App package** file blade, choose the browse button, and select a Windows installation file with the extension **.msi**, **.appx**, or **.appxbundle**.</span></span>
3. <span data-ttu-id="52f0e-114">Wenn Sie fertig sind, wählen Sie **OK** aus.</span><span class="sxs-lookup"><span data-stu-id="52f0e-114">When you are finished, choose **OK**.</span></span>


## <a name="step-3---configure-app-information"></a><span data-ttu-id="52f0e-115">Schritt 3: Konfigurieren von App-Informationen</span><span class="sxs-lookup"><span data-stu-id="52f0e-115">Step 3 - Configure app information</span></span>

1. <span data-ttu-id="52f0e-116">Wählen Sie auf dem Blatt **App hinzufügen** die Option **App-Paketdatei** aus.</span><span class="sxs-lookup"><span data-stu-id="52f0e-116">On the **Add app** blade, choose **App package** file.</span></span>
2. <span data-ttu-id="52f0e-117">Konfigurieren Sie folgende Informationen auf dem Blatt **App-Informationen** (einige der Werte auf diesem Blatt werden möglicherweise automatisch ausgefüllt):</span><span class="sxs-lookup"><span data-stu-id="52f0e-117">On the **App information** blade, configure the following information (some of the values in this blade might be automatically filled-in):</span></span>
    - <span data-ttu-id="52f0e-118">**Name:** Geben Sie den Namen der App ein, wie er im Unternehmensportal angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="52f0e-118">**Name** - Enter the name of the app as it is displayed in the company portal.</span></span> <span data-ttu-id="52f0e-119">Stellen Sie sicher, dass alle App-Namen eindeutig sind.</span><span class="sxs-lookup"><span data-stu-id="52f0e-119">Make sure all app names that you use are unique.</span></span> <span data-ttu-id="52f0e-120">Wenn ein App-Name zweimal vergeben wird, wird den Benutzern im Unternehmensportal nur eine der Apps angezeigt.</span><span class="sxs-lookup"><span data-stu-id="52f0e-120">If the same app name exists twice, only one of the apps is displayed to users in the company portal.</span></span>
    - <span data-ttu-id="52f0e-121">**Beschreibung:** Geben Sie eine Beschreibung für die App ein.</span><span class="sxs-lookup"><span data-stu-id="52f0e-121">**Description** - Enter a description for the app.</span></span> <span data-ttu-id="52f0e-122">Die Beschreibung wird Benutzern im Unternehmensportal angezeigt.</span><span class="sxs-lookup"><span data-stu-id="52f0e-122">The description is displayed to users in the company portal.</span></span>
    - <span data-ttu-id="52f0e-123">**Herausgeber:** Geben Sie den Namen des Herausgebers der App ein.</span><span class="sxs-lookup"><span data-stu-id="52f0e-123">**Publisher** - Enter the name of the publisher of the app.</span></span>
    - <span data-ttu-id="52f0e-124">**Kategorie:** Wählen Sie eine der integrierten oder von Ihnen erstellten App-Kategorien aus.</span><span class="sxs-lookup"><span data-stu-id="52f0e-124">**Category** - Select one or more of the built-in app categories, or a category you created.</span></span> <span data-ttu-id="52f0e-125">Durch die Kategorisierung von Apps wird es für die Benutzer leichter, die Apps im Unternehmensportal zu finden.</span><span class="sxs-lookup"><span data-stu-id="52f0e-125">Categorizing apps makes it easier for users to find the app when they browse the company portal.</span></span>
    - <span data-ttu-id="52f0e-126">**Diese App als ausgewählte App im Unternehmensportal anzeigen:** Zeigen Sie die App auf der Hauptseite des Unternehmensportal hervorgehoben an, wenn Benutzer nach Apps suchen.</span><span class="sxs-lookup"><span data-stu-id="52f0e-126">**Display this as a featured app in the Company Portal** - Display the app prominently on the main page of the company portal when users browse for apps.</span></span>
    - <span data-ttu-id="52f0e-127">**Informations-URL:** Geben Sie optional die URL zu einer Website ein, die Informationen über die App enthält.</span><span class="sxs-lookup"><span data-stu-id="52f0e-127">**Information URL** - Optionally, enter the URL of a website that contains information about the app.</span></span> <span data-ttu-id="52f0e-128">Diese URL wird Benutzern im Unternehmensportal angezeigt.</span><span class="sxs-lookup"><span data-stu-id="52f0e-128">The URL is displayed to users in the company portal.</span></span>
    - <span data-ttu-id="52f0e-129">**URL zu den Datenschutzbestimmungen:** Geben Sie optional die URL zu einer Website ein, die Datenschutzinformationen für die App enthält.</span><span class="sxs-lookup"><span data-stu-id="52f0e-129">**Privacy URL** - Optionally, enter the URL of a website that contains privacy information for the app.</span></span> <span data-ttu-id="52f0e-130">Diese URL wird Benutzern im Unternehmensportal angezeigt.</span><span class="sxs-lookup"><span data-stu-id="52f0e-130">The URL is displayed to users in the company portal.</span></span>
    - <span data-ttu-id="52f0e-131">**Befehlszeilenargumente:** Geben Sie optional Befehlszeilenargumente ein, die für die .msi-Datei gelten sollen, wenn sie ausgeführt wird, wie z.B. **/q**.</span><span class="sxs-lookup"><span data-stu-id="52f0e-131">**Command-line arguments** - Optionally, enter any command-line arguments that you want to apply to the .msi file when it runs, like **/q**.</span></span>
    - <span data-ttu-id="52f0e-132">**Entwickler:** Geben Sie optional den Namen des App-Entwicklers ein.</span><span class="sxs-lookup"><span data-stu-id="52f0e-132">**Developer** - Optionally, enter the name of the app developer.</span></span>
    - <span data-ttu-id="52f0e-133">**Besitzer:** Geben Sie optional einen Namen für den Besitzer dieser App ein, z.B. **Personalabteilung**.</span><span class="sxs-lookup"><span data-stu-id="52f0e-133">**Owner** - Optionally, enter a name for the owner of this app, for example, **HR department**.</span></span>
    - <span data-ttu-id="52f0e-134">**Anmerkungen:** Geben Sie Hinweise zu dieser App ein.</span><span class="sxs-lookup"><span data-stu-id="52f0e-134">**Notes** - Enter any notes you would like to associate with this app.</span></span>
    - <span data-ttu-id="52f0e-135">**Logo:** Laden Sie ein Symbol hoch, das der App zugeordnet wird.</span><span class="sxs-lookup"><span data-stu-id="52f0e-135">**Logo** - Upload an icon that is associated with the app.</span></span> <span data-ttu-id="52f0e-136">Das Symbol wird gemeinsam mit der App angezeigt, wenn Benutzer das Unternehmensportal durchsuchen.</span><span class="sxs-lookup"><span data-stu-id="52f0e-136">The icon is displayed with the app when users browse the company portal.</span></span>
3. <span data-ttu-id="52f0e-137">Wenn Sie fertig sind, wählen Sie **OK** aus.</span><span class="sxs-lookup"><span data-stu-id="52f0e-137">When you are finished, choose **OK**.</span></span>

## <a name="step-4---finish-up"></a><span data-ttu-id="52f0e-138">Schritt 4: Fertig stellen</span><span class="sxs-lookup"><span data-stu-id="52f0e-138">Step 4 - Finish up</span></span>

1. <span data-ttu-id="52f0e-139">Überprüfen Sie auf dem Blatt **App hinzufügen**, ob Sie die App-Informationen ordnungsgemäß konfiguriert haben.</span><span class="sxs-lookup"><span data-stu-id="52f0e-139">On the **Add app** blade, verify you configured the app information correctly.</span></span>
2. <span data-ttu-id="52f0e-140">Wählen Sie **Hinzufügen** aus, um die App in Intune hochzuladen.</span><span class="sxs-lookup"><span data-stu-id="52f0e-140">Choose **Add**, to upload the app to Intune.</span></span>

## <a name="step-5---update-a-line-of-business-app"></a><span data-ttu-id="52f0e-141">Schritt 5: Aktualisieren einer branchenspezifischen App</span><span class="sxs-lookup"><span data-stu-id="52f0e-141">Step 5 - Update a line of business app</span></span>

[!INCLUDE[shared-proc-lob-updateapp](./includes/shared-proc-lob-updateapp.md)]

## <a name="next-steps"></a><span data-ttu-id="52f0e-142">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="52f0e-142">Next steps</span></span>

<span data-ttu-id="52f0e-143">Die von Ihnen erstellte App wird in der Liste der Apps angezeigt.</span><span class="sxs-lookup"><span data-stu-id="52f0e-143">The app you have created is displayed in the apps list.</span></span> <span data-ttu-id="52f0e-144">Sie können sie jetzt den ausgewählten Gruppen zuweisen.</span><span class="sxs-lookup"><span data-stu-id="52f0e-144">You can now assign it to the groups you choose.</span></span> <span data-ttu-id="52f0e-145">Hilfe finden Sie unter [Zuweisen von Apps zu Gruppen](apps-deploy.md).</span><span class="sxs-lookup"><span data-stu-id="52f0e-145">For help, see [How to assign apps to groups](apps-deploy.md).</span></span>

<span data-ttu-id="52f0e-146">Erfahren Sie mehr darüber, wie Sie die Eigenschaften und Zuweisungen Ihrer App überwachen können.</span><span class="sxs-lookup"><span data-stu-id="52f0e-146">Learn more about the ways in which you can monitor the properties and assignment of your app.</span></span> <span data-ttu-id="52f0e-147">Weitere Informationen finden Sie unter [Überwachen von App-Informationen und -Zuweisungen](apps-monitor.md).</span><span class="sxs-lookup"><span data-stu-id="52f0e-147">For more information, see [How to monitor app information and assignments](apps-monitor.md).</span></span>

<span data-ttu-id="52f0e-148">Erfahren Sie mehr über den Kontext Ihrer App in Intune.</span><span class="sxs-lookup"><span data-stu-id="52f0e-148">Learn more about the context of your app in Intune.</span></span> <span data-ttu-id="52f0e-149">Weitere Informationen finden Sie unter [Übersicht über die Lebenszyklen von Geräten und Apps](introduction-device-app-lifecycles.md).</span><span class="sxs-lookup"><span data-stu-id="52f0e-149">For more information, see [Overview of device and app lifecycles](introduction-device-app-lifecycles.md)</span></span>