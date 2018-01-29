---
title: "Installieren von Office 365 für macOS-Geräte mit Intune"
titlesuffix: Azure portal
description: "Erfahren Sie, wie Sie Intune verwenden können, um Office 365-Apps einfacher auf macOS-Geräten installieren zu können."
keywords: 
author: erikre
ms.author: erikre
manager: angrobe
ms.date: 12/13/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 2372332a-7e3a-4a9c-91a9-86654e0fabe2
ms.reviewer: aiwang
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: cd071927955f5047067ba1d982e7078d89675cd0
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2018
---
# <a name="how-to-assign-office-365-to-macos-devices-with-microsoft-intune"></a><span data-ttu-id="faa8f-103">Zuweisen von Office 365 zu macOS-Geräten mit Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="faa8f-103">How to assign Office 365 to macOS devices with Microsoft Intune</span></span>

<span data-ttu-id="faa8f-104">Dieser App-Typ macht es Ihnen einfach, Office 365-Apps macOS-Geräten zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="faa8f-104">This app type makes it easy for you to assign Office 365 apps to macOS devices.</span></span> <span data-ttu-id="faa8f-105">Dieser neue App-Typ ermöglicht Ihnen die Installation von Word, Excel, PowerPoint, Outlook und OneNote.</span><span class="sxs-lookup"><span data-stu-id="faa8f-105">This new app type allows you to install Word, Excel, PowerPoint, Outlook, and OneNote.</span></span> <span data-ttu-id="faa8f-106">Diese Apps sind auch im Lieferumfang von Microsoft AutoUpdate (MAU) enthalten, um die Apps sicherer und auf dem neuesten Stand zu halten.</span><span class="sxs-lookup"><span data-stu-id="faa8f-106">These apps also come with the Microsoft AutoUpdate (MAU), to help keep the apps more secure and up-to-date.</span></span> <span data-ttu-id="faa8f-107">Die Apps, die als eine App in der Liste der Apps in der Intune-Konsole erscheinen sollen.</span><span class="sxs-lookup"><span data-stu-id="faa8f-107">The apps you want appear as one app in the list of apps in the Intune console.</span></span>


## <a name="before-you-start"></a><span data-ttu-id="faa8f-108">Vorbereitung</span><span class="sxs-lookup"><span data-stu-id="faa8f-108">Before you start</span></span>

- <span data-ttu-id="faa8f-109">Auf Geräten, für die Sie diese Apps bereitstellen, muss macOS 10.10 oder höher ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="faa8f-109">Devices to which you deploy these apps must be running macOS 10.10 or later.</span></span>
- <span data-ttu-id="faa8f-110">Intune unterstützt nur das Hinzufügen von Office-Apps, die in der Office 2016 für Mac-Suite enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="faa8f-110">Intune only supports adding Office apps included with Office 2016 for Mac suite.</span></span>
- <span data-ttu-id="faa8f-111">Wenn bei der Installation der App-Suite durch Intune Office-Apps geöffnet sind, verlieren Endbenutzer möglicherweise Daten aus nicht gespeicherten Dateien.</span><span class="sxs-lookup"><span data-stu-id="faa8f-111">If any Office apps are opened when Intune installs the app suite, end users might lose data from unsaved files.</span></span>


## <a name="get-started"></a><span data-ttu-id="faa8f-112">Erste Schritte</span><span class="sxs-lookup"><span data-stu-id="faa8f-112">Get started</span></span>
<span data-ttu-id="faa8f-113">Fügen Sie Office 365 auf dem Blatt **Apps** hinzu.</span><span class="sxs-lookup"><span data-stu-id="faa8f-113">Add Office 365 using the **Apps** blade.</span></span>
1.  <span data-ttu-id="faa8f-114">Melden Sie sich beim Azure-Portal an.</span><span class="sxs-lookup"><span data-stu-id="faa8f-114">Sign into the Azure portal.</span></span>
2.  <span data-ttu-id="faa8f-115">Wählen Sie **Weitere Dienste** > **Überwachung und Verwaltung** > **Intune** aus.</span><span class="sxs-lookup"><span data-stu-id="faa8f-115">Choose **More Services** > **Monitoring + Management** > **Intune**.</span></span>
3.  <span data-ttu-id="faa8f-116">Wählen Sie auf dem Blatt **Intune** die Option **Mobile Apps** aus.</span><span class="sxs-lookup"><span data-stu-id="faa8f-116">On the **Intune** blade, choose **Mobile apps**.</span></span>
4.  <span data-ttu-id="faa8f-117">Klicken Sie in der Workload **Mobile Apps** auf **Apps** in der Gruppe **Verwalten**.</span><span class="sxs-lookup"><span data-stu-id="faa8f-117">In the **Mobile apps** workload, choose **Apps** in the **Manage** group.</span></span> <span data-ttu-id="faa8f-118">Wählen Sie **Hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="faa8f-118">Choose **Add**.</span></span>
5.  <span data-ttu-id="faa8f-119">Wählen Sie auf dem Blatt **App hinzufügen** die Optionen **Office 365** > **macOS** aus.</span><span class="sxs-lookup"><span data-stu-id="faa8f-119">On the **Add App** blade, choose **Office 365** > **macOS**.</span></span>
6.  <span data-ttu-id="faa8f-120">Wählen Sie **Hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="faa8f-120">Select **Add**.</span></span>

## <a name="configure-the-app-suite"></a><span data-ttu-id="faa8f-121">Konfigurieren der App-Sammlung</span><span class="sxs-lookup"><span data-stu-id="faa8f-121">Configure the app suite</span></span>

<span data-ttu-id="faa8f-122">Stellen Sie Informationen über die App-Suite bereit.</span><span class="sxs-lookup"><span data-stu-id="faa8f-122">Provide information about the app suite.</span></span> <span data-ttu-id="faa8f-123">Diese Informationen helfen Ihnen, die Sammlung in Intune zu identifizieren, und Endbenutzer können sie in der Unternehmensportal-App finden.</span><span class="sxs-lookup"><span data-stu-id="faa8f-123">This information helps you to identify it in Intune, and also helps users to find it in the Company Portal app.</span></span>

1.  <span data-ttu-id="faa8f-124">Wählen Sie auf dem Blatt **App hinzufügen** die Option **App Suite Information** (Informationen über die App-Sammlung) aus.</span><span class="sxs-lookup"><span data-stu-id="faa8f-124">On the **Add App** blade, choose **App Suite Information**.</span></span>
2.  <span data-ttu-id="faa8f-125">Geben Sie die folgenden Informationen an:</span><span class="sxs-lookup"><span data-stu-id="faa8f-125">Specify the following information:</span></span>
    - <span data-ttu-id="faa8f-126">**Sammlungsname:** Geben Sie den Namen der App-Sammlung ein, wie er im Unternehmensportal angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="faa8f-126">**Suite Name** - Enter the name of the app suite as it is displayed in the company portal.</span></span> <span data-ttu-id="faa8f-127">Stellen Sie sicher, dass alle Sammlungsnamen eindeutig sind.</span><span class="sxs-lookup"><span data-stu-id="faa8f-127">Make sure all suite names that you use are unique.</span></span> <span data-ttu-id="faa8f-128">Wenn ein Sammlungsname zweimal vergeben wird, wird den Benutzern im Unternehmensportal nur eine der Apps angezeigt.</span><span class="sxs-lookup"><span data-stu-id="faa8f-128">If the same app suite name exists twice, only one of the apps is displayed to users in the company portal.</span></span>
    - <span data-ttu-id="faa8f-129">**Sammlungsbeschreibung:** Geben Sie eine Beschreibung für die Sammlung ein.</span><span class="sxs-lookup"><span data-stu-id="faa8f-129">**Suite Description** - Enter a description for the app suite.</span></span>
    - <span data-ttu-id="faa8f-130">**Herausgeber**: Als Herausgeber wird Microsoft angezeigt.</span><span class="sxs-lookup"><span data-stu-id="faa8f-130">**Publisher** - Microsoft appears as the publisher.</span></span>
    - <span data-ttu-id="faa8f-131">**Kategorie:** Wählen Sie optional eine der integrierten oder von Ihnen erstellten App-Kategorien aus.</span><span class="sxs-lookup"><span data-stu-id="faa8f-131">**Category** - Optionally, select one or more of the built-in app categories, or a category you created.</span></span> <span data-ttu-id="faa8f-132">Dadurch wird es für Benutzer leichter, die App-Sammlung im Unternehmensportal zu finden.</span><span class="sxs-lookup"><span data-stu-id="faa8f-132">This makes it easier for users to find the app suite when they browse the company portal.</span></span>
    - <span data-ttu-id="faa8f-133">**Diese App als ausgewählte App im Unternehmensportal anzeigen**: Hierdurch wird die App-Suite auf der Hauptseite des Unternehmensportals hervorgehoben angezeigt, wenn Benutzer nach Apps suchen.</span><span class="sxs-lookup"><span data-stu-id="faa8f-133">**Display this as a featured app in the Company Portal** - This will display the app suite prominently on the main page of the company portal when users browse for apps.</span></span>
    - <span data-ttu-id="faa8f-134">**Informations-URL:** Geben Sie optional eine URL zu einer Website ein, die Informationen über diese App enthält.</span><span class="sxs-lookup"><span data-stu-id="faa8f-134">**Information URL** - Optionally, enter the URL of a website that contains information about this app.</span></span> <span data-ttu-id="faa8f-135">Diese URL wird Benutzern im Unternehmensportal angezeigt.</span><span class="sxs-lookup"><span data-stu-id="faa8f-135">The URL is displayed to users in the company portal.</span></span>
    - <span data-ttu-id="faa8f-136">**URL zu den Datenschutzbestimmungen:** Geben Sie optional eine URL zu einer Website ein, die Datenschutzinformationen für diese App enthält.</span><span class="sxs-lookup"><span data-stu-id="faa8f-136">**Privacy URL** - Optionally, enter the URL of a website that contains privacy information for this app.</span></span> <span data-ttu-id="faa8f-137">Diese URL wird Benutzern im Unternehmensportal angezeigt.</span><span class="sxs-lookup"><span data-stu-id="faa8f-137">The URL is displayed to users in the company portal.</span></span>
    - <span data-ttu-id="faa8f-138">**Entwickler**: Als Entwickler wird Microsoft angezeigt.</span><span class="sxs-lookup"><span data-stu-id="faa8f-138">**Developer** - Microsoft appears as the developer.</span></span>
    - <span data-ttu-id="faa8f-139">**Besitzer**: Als Besitzer wird Microsoft angezeigt.</span><span class="sxs-lookup"><span data-stu-id="faa8f-139">**Owner** - Microsoft appears as the owner.</span></span>
    - <span data-ttu-id="faa8f-140">**Anmerkungen:** Geben Sie Hinweise zu dieser App ein.</span><span class="sxs-lookup"><span data-stu-id="faa8f-140">**Notes** - Enter any notes you would like to associate with this app.</span></span>
    - <span data-ttu-id="faa8f-141">**Symbol hochladen:** Laden Sie ein Symbol hoch, das gemeinsam mit der App angezeigt wird, wenn die Benutzer das Unternehmensportal durchsuchen.</span><span class="sxs-lookup"><span data-stu-id="faa8f-141">**Upload Icon** - Upload an icon that is displayed with the app when users browse the company portal.</span></span>
3.  <span data-ttu-id="faa8f-142">Wählen Sie **OK** aus.</span><span class="sxs-lookup"><span data-stu-id="faa8f-142">Select **OK**.</span></span> <span data-ttu-id="faa8f-143">Die Suite wird in der Liste der Apps als einzelnen Eintrag angezeigt.</span><span class="sxs-lookup"><span data-stu-id="faa8f-143">The suite appears in the list of apps as a single entry.</span></span>

## <a name="configure-app-assignments"></a><span data-ttu-id="faa8f-144">Konfigurieren von App-Zuweisungen</span><span class="sxs-lookup"><span data-stu-id="faa8f-144">Configure app assignments</span></span>

<span data-ttu-id="faa8f-145">In diesem Schritt konfigurieren Sie Zuweisungen für die App-Suite.</span><span class="sxs-lookup"><span data-stu-id="faa8f-145">In this step, configure the assignments for the app suite.</span></span> <span data-ttu-id="faa8f-146">Beachten Sie, dass der verfügbare App-Typ in Kürze verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="faa8f-146">Note that the available app type is coming soon.</span></span>

1. <span data-ttu-id="faa8f-147">Wählen Sie die App-Suite in der Liste der Apps und dann **Zuweisungen** aus.</span><span class="sxs-lookup"><span data-stu-id="faa8f-147">Select the app suite in the list of apps, and select **Assignments**.</span></span>
2. <span data-ttu-id="faa8f-148">Klicken Sie auf **Gruppen auswählen**.</span><span class="sxs-lookup"><span data-stu-id="faa8f-148">Choose **Select groups**.</span></span>
3. <span data-ttu-id="faa8f-149">Ordnen Sie die Suite den von Ihnen ausgewählten Gruppen zu.</span><span class="sxs-lookup"><span data-stu-id="faa8f-149">Assign the suite to the groups you choose.</span></span> <span data-ttu-id="faa8f-150">Weitere Informationen finden Sie unter [Zuweisen von Apps zu Gruppen mit Microsoft Intune](/intune/apps-deploy).</span><span class="sxs-lookup"><span data-stu-id="faa8f-150">For more information, see [How to assign apps to groups with Microsoft Intune](/intune/apps-deploy).</span></span>
4. <span data-ttu-id="faa8f-151">Wählen Sie für jede Gruppe **erfordern installieren**.</span><span class="sxs-lookup"><span data-stu-id="faa8f-151">For each group, you select **Require Install**.</span></span>
       >[!Note]
       > You cannot uninstall Office 365 through Intune.

5. <span data-ttu-id="faa8f-152">Wählen Sie **Speichern**, um Ihre Zuweisungen zu committen.</span><span class="sxs-lookup"><span data-stu-id="faa8f-152">Select **Save** to commit your assignments.</span></span>

## <a name="next-steps"></a><span data-ttu-id="faa8f-153">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="faa8f-153">Next steps</span></span>

<span data-ttu-id="faa8f-154">Weitere Informationen zum Hinzufügen von Office 365-Apps zu Windows 10-Geräten finden Sie unter [Wie Sie Office 365 ProPlus 2016-Apps mit Microsoft Intune](/intune/apps-add-office365) Windows 10-Geräten zuweisen.</span><span class="sxs-lookup"><span data-stu-id="faa8f-154">To learn about adding Office 365 apps to Windows 10 device, see [How to assign Office 365 ProPlus 2016 apps to Windows 10 devices with Microsoft Intune](/intune/apps-add-office365).</span></span>
