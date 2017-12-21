---
title: "Hinzufügen branchenspezifischer Windows Phone-Apps zu Intune"
titlesuffix: Azure portal
description: "Erfahren Sie mehr über das Hinzufügen branchenspezifischer Windows Phone-Apps zu Intune."
keywords: 
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 10/3/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a097b7b2-d01d-454b-954c-da4f3cd0ae86
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 60776df3774d4f9ca7404ef04b1cc94536bcd164
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2017
---
# <a name="how-to-add-windows-phone-line-of-business-lob-apps-to-microsoft-intune"></a><span data-ttu-id="bc6df-103">Informationen zum Hinzufügen branchenspezifischer Windows Phone-Apps zu Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="bc6df-103">How to add Windows Phone line-of-business (LOB) apps to Microsoft Intune</span></span>

[!INCLUDE[azure_portal](./includes/azure_portal.md)]


## <a name="step-1---specify-the-software-setup-file"></a><span data-ttu-id="bc6df-104">Schritt 1: Angeben der Softwaresetupdatei</span><span class="sxs-lookup"><span data-stu-id="bc6df-104">Step 1 - Specify the software setup file</span></span>

1. <span data-ttu-id="bc6df-105">Melden Sie sich im Azure-Portal an.</span><span class="sxs-lookup"><span data-stu-id="bc6df-105">Sign in to the Azure portal.</span></span>
2. <span data-ttu-id="bc6df-106">Wählen Sie **Weitere Dienste** > **Überwachung und Verwaltung** + **Intune** aus.</span><span class="sxs-lookup"><span data-stu-id="bc6df-106">Choose **More Services** > **Monitoring + Management** + **Intune**.</span></span>
3. <span data-ttu-id="bc6df-107">Wählen Sie auf dem Blatt **Intune** die Option **Apps verwalten** aus.</span><span class="sxs-lookup"><span data-stu-id="bc6df-107">On the **Intune** blade, choose **Manage apps**.</span></span>
4. <span data-ttu-id="bc6df-108">Wählen Sie in der Workload **Mobile Apps** die Option **Verwalten** > **Apps** aus.</span><span class="sxs-lookup"><span data-stu-id="bc6df-108">In the **Mobile apps** workload, choose **Manage** > **Apps**.</span></span>
5. <span data-ttu-id="bc6df-109">Wählen Sie über der Liste der Apps **Hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="bc6df-109">Above the list of apps, choose **Add**.</span></span>
6. <span data-ttu-id="bc6df-110">Wählen Sie auf dem Blatt **App hinzufügen** die Option **Branchen-App** aus.</span><span class="sxs-lookup"><span data-stu-id="bc6df-110">In the **Add App** blade, choose **Line-of-business app**.</span></span>

## <a name="step-2---configure-the-app-package-file"></a><span data-ttu-id="bc6df-111">Schritt 2: Konfigurieren der App-Paketdatei</span><span class="sxs-lookup"><span data-stu-id="bc6df-111">Step 2 - Configure the app package file</span></span>

1. <span data-ttu-id="bc6df-112">Wählen Sie auf dem Blatt **App hinzufügen** die Option **App-Paketdatei** aus.</span><span class="sxs-lookup"><span data-stu-id="bc6df-112">On the **Add app** blade, choose **App package** file.</span></span>
2. <span data-ttu-id="bc6df-113">Wählen Sie auf dem Blatt **App-Paketdatei** die Schaltfläche „Durchsuchen“ und anschließend eine Windows Phone-Installationsdatei mit der Erweiterung **XAP** aus.</span><span class="sxs-lookup"><span data-stu-id="bc6df-113">On the **App package** file blade, choose the browse button, and select a Windows Phone installation file with the extension, **.xap**.</span></span>
3. <span data-ttu-id="bc6df-114">Wenn Sie fertig sind, wählen Sie **OK** aus.</span><span class="sxs-lookup"><span data-stu-id="bc6df-114">When you are finished, choose **OK**.</span></span>


## <a name="step-3---configure-app-information"></a><span data-ttu-id="bc6df-115">Schritt 3: Konfigurieren von App-Informationen</span><span class="sxs-lookup"><span data-stu-id="bc6df-115">Step 3 - Configure app information</span></span>

1. <span data-ttu-id="bc6df-116">Wählen Sie auf dem Blatt **App hinzufügen** die Option **App-Paketdatei** aus.</span><span class="sxs-lookup"><span data-stu-id="bc6df-116">On the **Add app** blade, choose **App package** file.</span></span>
2. <span data-ttu-id="bc6df-117">Konfigurieren Sie auf dem Blatt **App-Informationen** die App-Informationen.</span><span class="sxs-lookup"><span data-stu-id="bc6df-117">On the **App information** blade, configure the app information.</span></span> <span data-ttu-id="bc6df-118">Abhängig von der ausgewählten App werden einige der Werte auf diesem Blatt möglicherweise automatisch ausgefüllt:</span><span class="sxs-lookup"><span data-stu-id="bc6df-118">Depending on the app you have chosen, some of the values in this blade might have been automatically filled-in:</span></span>
    - <span data-ttu-id="bc6df-119">**Name:** Geben Sie den Namen der App ein, wie er im Unternehmensportal angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="bc6df-119">**Name** - Enter the name of the app as it is displayed in the company portal.</span></span> <span data-ttu-id="bc6df-120">Stellen Sie sicher, dass alle App-Namen eindeutig sind.</span><span class="sxs-lookup"><span data-stu-id="bc6df-120">Make sure all app names that you use are unique.</span></span> <span data-ttu-id="bc6df-121">Wenn ein App-Name zweimal vergeben wird, wird den Benutzern im Unternehmensportal nur eine der Apps angezeigt.</span><span class="sxs-lookup"><span data-stu-id="bc6df-121">If the same app name exists twice, only one of the apps is displayed to users in the company portal.</span></span>
    - <span data-ttu-id="bc6df-122">**Beschreibung:** Geben Sie eine Beschreibung für die App ein.</span><span class="sxs-lookup"><span data-stu-id="bc6df-122">**Description** - Enter a description for the app.</span></span> <span data-ttu-id="bc6df-123">Die Beschreibung wird Benutzern im Unternehmensportal angezeigt.</span><span class="sxs-lookup"><span data-stu-id="bc6df-123">The description is displayed to users in the company portal.</span></span>
    - <span data-ttu-id="bc6df-124">**Herausgeber:** Geben Sie den Namen des Herausgebers der App ein.</span><span class="sxs-lookup"><span data-stu-id="bc6df-124">**Publisher** - Enter the name of the publisher of the app.</span></span>
    - <span data-ttu-id="bc6df-125">**Kategorie:** Wählen Sie eine der integrierten oder von Ihnen erstellten App-Kategorien aus.</span><span class="sxs-lookup"><span data-stu-id="bc6df-125">**Category** - Select one or more of the built-in app categories, or a category you created.</span></span> <span data-ttu-id="bc6df-126">Durch Kategorien wird es für Benutzer leichter, die App im Unternehmensportal zu finden.</span><span class="sxs-lookup"><span data-stu-id="bc6df-126">Using categories makes it easier for users to find the app when they browse the company portal.</span></span>
    - <span data-ttu-id="bc6df-127">**Diese App als ausgewählte App im Unternehmensportal anzeigen:** Zeigen Sie die App auf der Hauptseite des Unternehmensportal hervorgehoben an, wenn Benutzer nach Apps suchen.</span><span class="sxs-lookup"><span data-stu-id="bc6df-127">**Display this as a featured app in the Company Portal** - Display the app prominently on the main page of the company portal when users browse for apps.</span></span>
    - <span data-ttu-id="bc6df-128">**Informations-URL:** Geben Sie optional eine URL zu einer Website ein, die Informationen über diese App enthält.</span><span class="sxs-lookup"><span data-stu-id="bc6df-128">**Information URL** - Optionally, enter the URL of a website that contains information about this app.</span></span> <span data-ttu-id="bc6df-129">Diese URL wird Benutzern im Unternehmensportal angezeigt.</span><span class="sxs-lookup"><span data-stu-id="bc6df-129">The URL is displayed to users in the company portal.</span></span>
    - <span data-ttu-id="bc6df-130">**URL zu den Datenschutzbestimmungen:** Geben Sie optional eine URL zu einer Website ein, die Datenschutzinformationen für diese App enthält.</span><span class="sxs-lookup"><span data-stu-id="bc6df-130">**Privacy URL** - Optionally, enter the URL of a website that contains privacy information for this app.</span></span> <span data-ttu-id="bc6df-131">Diese URL wird Benutzern im Unternehmensportal angezeigt.</span><span class="sxs-lookup"><span data-stu-id="bc6df-131">The URL is displayed to users in the company portal.</span></span>
    - <span data-ttu-id="bc6df-132">**Entwickler:** Geben Sie optional den Namen des App-Entwicklers ein.</span><span class="sxs-lookup"><span data-stu-id="bc6df-132">**Developer** - Optionally, enter the name of the app developer.</span></span>
    - <span data-ttu-id="bc6df-133">**Besitzer:** Geben Sie optional einen Namen für den Besitzer dieser App ein, z.B. **Personalabteilung**.</span><span class="sxs-lookup"><span data-stu-id="bc6df-133">**Owner** - Optionally, enter a name for the owner of this app, for example, **HR department**.</span></span>
    - <span data-ttu-id="bc6df-134">**Anmerkungen:** Geben Sie Hinweise zu dieser App ein.</span><span class="sxs-lookup"><span data-stu-id="bc6df-134">**Notes** - Enter any notes you would like to associate with this app.</span></span>
    - <span data-ttu-id="bc6df-135">**Logo:** Laden Sie ein Symbol hoch, das der App zugeordnet wird.</span><span class="sxs-lookup"><span data-stu-id="bc6df-135">**Logo** - Upload an icon that is associated with the app.</span></span> <span data-ttu-id="bc6df-136">Dieses Symbol wird mit der App angezeigt, wenn Benutzer das Unternehmensportal durchsuchen.</span><span class="sxs-lookup"><span data-stu-id="bc6df-136">This icon is displayed with the app when users browse the company portal.</span></span>
3. <span data-ttu-id="bc6df-137">Wenn Sie fertig sind, wählen Sie **OK** aus.</span><span class="sxs-lookup"><span data-stu-id="bc6df-137">When you are finished, choose **OK**.</span></span>

## <a name="step-4---finish-up"></a><span data-ttu-id="bc6df-138">Schritt 4: Fertig stellen</span><span class="sxs-lookup"><span data-stu-id="bc6df-138">Step 4 - Finish up</span></span>

1. <span data-ttu-id="bc6df-139">Überprüfen Sie auf dem Blatt **App hinzufügen**, ob die konfigurierten Informationen richtig sind.</span><span class="sxs-lookup"><span data-stu-id="bc6df-139">On the **Add app** blade, verify that you configured the information correctly.</span></span>
2. <span data-ttu-id="bc6df-140">Wählen Sie **Hinzufügen** aus, um die App in Intune hochzuladen.</span><span class="sxs-lookup"><span data-stu-id="bc6df-140">Choose **Add**, to upload the app to Intune.</span></span>

## <a name="next-steps"></a><span data-ttu-id="bc6df-141">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="bc6df-141">Next steps</span></span>

<span data-ttu-id="bc6df-142">Die von Ihnen erstellte App wird in der Liste der Apps angezeigt.</span><span class="sxs-lookup"><span data-stu-id="bc6df-142">The app you have created is displayed in the apps list.</span></span> <span data-ttu-id="bc6df-143">Sie können sie jetzt den ausgewählten Gruppen zuweisen.</span><span class="sxs-lookup"><span data-stu-id="bc6df-143">You can now assign it to the groups you choose.</span></span> <span data-ttu-id="bc6df-144">Hilfe finden Sie unter [Zuweisen von Apps zu Gruppen](apps-deploy.md).</span><span class="sxs-lookup"><span data-stu-id="bc6df-144">For help, see [How to assign apps to groups](apps-deploy.md).</span></span>

<span data-ttu-id="bc6df-145">Erfahren Sie mehr darüber, wie Sie die Eigenschaften und Zuweisungen Ihrer App überwachen können.</span><span class="sxs-lookup"><span data-stu-id="bc6df-145">Learn more about the ways in which you can monitor the properties and assignment of your app.</span></span> <span data-ttu-id="bc6df-146">Weitere Informationen finden Sie unter [Überwachen von App-Informationen und -Zuweisungen](apps-monitor.md).</span><span class="sxs-lookup"><span data-stu-id="bc6df-146">For more information, see [How to monitor app information and assignments](apps-monitor.md).</span></span>

<span data-ttu-id="bc6df-147">Erfahren Sie mehr über den Kontext Ihrer App in Intune.</span><span class="sxs-lookup"><span data-stu-id="bc6df-147">Learn more about the context of your app in Intune.</span></span> <span data-ttu-id="bc6df-148">Weitere Informationen finden Sie unter [Übersicht über die Lebenszyklen von Geräten und Apps](introduction-device-app-lifecycles.md).</span><span class="sxs-lookup"><span data-stu-id="bc6df-148">For more information, see [Overview of device and app lifecycles](introduction-device-app-lifecycles.md)</span></span>
