---
title: "Installieren Sie Office 365 für MacOS-Geräte mit Intune"
titlesuffix: Azure portal
description: "Erfahren Sie, wie Sie Intune verwenden, installieren Sie Office 365-apps auf Geräten MacOS erleichtern."
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
ms.openlocfilehash: 5e0ad0b99a2c8a602b5e542530a1d437065461b2
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2017
---
# <a name="how-to-assign-office-365-to-macos-devices-with-microsoft-intune"></a><span data-ttu-id="46d34-103">Zuweisen von Office 365 zu MacOS-Geräten mit Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="46d34-103">How to assign Office 365 to macOS devices with Microsoft Intune</span></span>

<span data-ttu-id="46d34-104">Diese app-Typ ganz einfach für Office 365-apps auf Geräten MacOS zuweisen.</span><span class="sxs-lookup"><span data-stu-id="46d34-104">This app type makes it easy for you to assign Office 365 apps to macOS devices.</span></span> <span data-ttu-id="46d34-105">Diese neue Art der app können Sie Word, Excel, PowerPoint, Outlook und OneNote installieren.</span><span class="sxs-lookup"><span data-stu-id="46d34-105">This new app type allows you to install Word, Excel, PowerPoint, Outlook, and OneNote.</span></span> <span data-ttu-id="46d34-106">Diese apps werden auch mit dem Microsoft AutoUpdate (MAU), um die apps sicherer und auf dem neuesten Stand zu halten.</span><span class="sxs-lookup"><span data-stu-id="46d34-106">These apps also come with the Microsoft AutoUpdate (MAU), to help keep the apps more secure and up-to-date.</span></span> <span data-ttu-id="46d34-107">Die Apps, die als eine App in der Liste der Apps in der Intune-Konsole erscheinen sollen.</span><span class="sxs-lookup"><span data-stu-id="46d34-107">The apps you want appear as one app in the list of apps in the Intune console.</span></span>


## <a name="before-you-start"></a><span data-ttu-id="46d34-108">Vorbereitung</span><span class="sxs-lookup"><span data-stu-id="46d34-108">Before you start</span></span>

- <span data-ttu-id="46d34-109">Geräte, die auf die Bereitstellung dieser apps müssen MacOS 10.10 oder höher ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="46d34-109">Devices to which you deploy these apps must be running macOS 10.10 or later.</span></span>
- <span data-ttu-id="46d34-110">Intune unterstützt nur Hinzufügen von Office-apps, die mit Office 2016 für Mac-Suite enthalten.</span><span class="sxs-lookup"><span data-stu-id="46d34-110">Intune only supports adding Office apps included with Office 2016 for Mac suite.</span></span>
- <span data-ttu-id="46d34-111">Wenn alle Office-apps geöffnet werden, wenn Intune das app-Suite installiert wird, können Endbenutzer-Daten aus nicht gespeicherte Dateien verloren gehen.</span><span class="sxs-lookup"><span data-stu-id="46d34-111">If any Office apps are opened when Intune installs the app suite, end users might lose data from unsaved files.</span></span>


## <a name="get-started"></a><span data-ttu-id="46d34-112">Erste Schritte</span><span class="sxs-lookup"><span data-stu-id="46d34-112">Get started</span></span>
<span data-ttu-id="46d34-113">Fügen Sie Office 365 using der **Apps** Blatt.</span><span class="sxs-lookup"><span data-stu-id="46d34-113">Add Office 365 using the **Apps** blade.</span></span>
1.  <span data-ttu-id="46d34-114">Melden Sie sich beim Azure-Portal an.</span><span class="sxs-lookup"><span data-stu-id="46d34-114">Sign into the Azure portal.</span></span>
2.  <span data-ttu-id="46d34-115">Wählen Sie **Weitere Dienste** > **Überwachung und Verwaltung** > **Intune** aus.</span><span class="sxs-lookup"><span data-stu-id="46d34-115">Choose **More Services** > **Monitoring + Management** > **Intune**.</span></span>
3.  <span data-ttu-id="46d34-116">Wählen Sie auf dem Blatt **Intune** die Option **Mobile Apps** aus.</span><span class="sxs-lookup"><span data-stu-id="46d34-116">On the **Intune** blade, choose **Mobile apps**.</span></span>
4.  <span data-ttu-id="46d34-117">In der **mobilapps** arbeitsauslastung, wählen Sie **Apps** in der **verwalten** Gruppe.</span><span class="sxs-lookup"><span data-stu-id="46d34-117">In the **Mobile apps** workload, choose **Apps** in the **Manage** group.</span></span> <span data-ttu-id="46d34-118">Wählen Sie **Hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="46d34-118">Choose **Add**.</span></span>
5.  <span data-ttu-id="46d34-119">Auf der **App hinzufügen** Blatt, wählen Sie **Office 365** > **MacOS**.</span><span class="sxs-lookup"><span data-stu-id="46d34-119">On the **Add App** blade, choose **Office 365** > **macOS**.</span></span>
6.  <span data-ttu-id="46d34-120">Wählen Sie **Hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="46d34-120">Select **Add**.</span></span>

## <a name="configure-the-app-suite"></a><span data-ttu-id="46d34-121">Konfigurieren der App-Sammlung</span><span class="sxs-lookup"><span data-stu-id="46d34-121">Configure the app suite</span></span>

<span data-ttu-id="46d34-122">Geben Sie Informationen zu den app-Suite.</span><span class="sxs-lookup"><span data-stu-id="46d34-122">Provide information about the app suite.</span></span> <span data-ttu-id="46d34-123">Diese Informationen helfen Ihnen, die Sammlung in Intune zu identifizieren, und Endbenutzer können sie in der Unternehmensportal-App finden.</span><span class="sxs-lookup"><span data-stu-id="46d34-123">This information helps you to identify it in Intune, and also helps users to find it in the Company Portal app.</span></span>

1.  <span data-ttu-id="46d34-124">Wählen Sie auf dem Blatt **App hinzufügen** die Option **App Suite Information** (Informationen über die App-Sammlung) aus.</span><span class="sxs-lookup"><span data-stu-id="46d34-124">On the **Add App** blade, choose **App Suite Information**.</span></span>
2.  <span data-ttu-id="46d34-125">Geben Sie die folgenden Informationen an:</span><span class="sxs-lookup"><span data-stu-id="46d34-125">Specify the following information:</span></span>
    - <span data-ttu-id="46d34-126">**Sammlungsname:** Geben Sie den Namen der App-Sammlung ein, wie er im Unternehmensportal angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="46d34-126">**Suite Name** - Enter the name of the app suite as it is displayed in the company portal.</span></span> <span data-ttu-id="46d34-127">Stellen Sie sicher, dass alle Sammlungsnamen eindeutig sind.</span><span class="sxs-lookup"><span data-stu-id="46d34-127">Make sure all suite names that you use are unique.</span></span> <span data-ttu-id="46d34-128">Wenn ein Sammlungsname zweimal vergeben wird, wird den Benutzern im Unternehmensportal nur eine der Apps angezeigt.</span><span class="sxs-lookup"><span data-stu-id="46d34-128">If the same app suite name exists twice, only one of the apps is displayed to users in the company portal.</span></span>
    - <span data-ttu-id="46d34-129">**Sammlungsbeschreibung:** Geben Sie eine Beschreibung für die Sammlung ein.</span><span class="sxs-lookup"><span data-stu-id="46d34-129">**Suite Description** - Enter a description for the app suite.</span></span>
    - <span data-ttu-id="46d34-130">**Publisher** -Microsoft angezeigt wird, wie der Verleger.</span><span class="sxs-lookup"><span data-stu-id="46d34-130">**Publisher** - Microsoft appears as the publisher.</span></span>
    - <span data-ttu-id="46d34-131">**Kategorie:** Wählen Sie optional eine der integrierten oder von Ihnen erstellten App-Kategorien aus.</span><span class="sxs-lookup"><span data-stu-id="46d34-131">**Category** - Optionally, select one or more of the built-in app categories, or a category you created.</span></span> <span data-ttu-id="46d34-132">Dadurch wird es für Benutzer leichter, die App-Sammlung im Unternehmensportal zu finden.</span><span class="sxs-lookup"><span data-stu-id="46d34-132">This makes it easier for users to find the app suite when they browse the company portal.</span></span>
    - <span data-ttu-id="46d34-133">**Als ausgewählte app im Unternehmensportal anzeigen** -Dies zeigt die app-Suite herausgehoben auf der Hauptseite des Unternehmensportals, wenn Benutzer nach apps suchen.</span><span class="sxs-lookup"><span data-stu-id="46d34-133">**Display this as a featured app in the Company Portal** - This will display the app suite prominently on the main page of the company portal when users browse for apps.</span></span>
    - <span data-ttu-id="46d34-134">**Informations-URL:** Geben Sie optional eine URL zu einer Website ein, die Informationen über diese App enthält.</span><span class="sxs-lookup"><span data-stu-id="46d34-134">**Information URL** - Optionally, enter the URL of a website that contains information about this app.</span></span> <span data-ttu-id="46d34-135">Diese URL wird Benutzern im Unternehmensportal angezeigt.</span><span class="sxs-lookup"><span data-stu-id="46d34-135">The URL is displayed to users in the company portal.</span></span>
    - <span data-ttu-id="46d34-136">**URL zu den Datenschutzbestimmungen:** Geben Sie optional eine URL zu einer Website ein, die Datenschutzinformationen für diese App enthält.</span><span class="sxs-lookup"><span data-stu-id="46d34-136">**Privacy URL** - Optionally, enter the URL of a website that contains privacy information for this app.</span></span> <span data-ttu-id="46d34-137">Diese URL wird Benutzern im Unternehmensportal angezeigt.</span><span class="sxs-lookup"><span data-stu-id="46d34-137">The URL is displayed to users in the company portal.</span></span>
    - <span data-ttu-id="46d34-138">**Entwickler** -Microsoft wird als der Entwickler angezeigt.</span><span class="sxs-lookup"><span data-stu-id="46d34-138">**Developer** - Microsoft appears as the developer.</span></span>
    - <span data-ttu-id="46d34-139">**Besitzer** -Microsoft als Besitzer wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="46d34-139">**Owner** - Microsoft appears as the owner.</span></span>
    - <span data-ttu-id="46d34-140">**Anmerkungen:** Geben Sie Hinweise zu dieser App ein.</span><span class="sxs-lookup"><span data-stu-id="46d34-140">**Notes** - Enter any notes you would like to associate with this app.</span></span>
    - <span data-ttu-id="46d34-141">**Symbol hochladen:** Laden Sie ein Symbol hoch, das gemeinsam mit der App angezeigt wird, wenn die Benutzer das Unternehmensportal durchsuchen.</span><span class="sxs-lookup"><span data-stu-id="46d34-141">**Upload Icon** - Upload an icon that is displayed with the app when users browse the company portal.</span></span>
3.  <span data-ttu-id="46d34-142">Wählen Sie **OK** aus.</span><span class="sxs-lookup"><span data-stu-id="46d34-142">Select **OK**.</span></span> <span data-ttu-id="46d34-143">Die Suite wird in der Liste der apps als einzelnen Eintrag angezeigt.</span><span class="sxs-lookup"><span data-stu-id="46d34-143">The suite appears in the list of apps as a single entry.</span></span>

## <a name="configure-app-assignments"></a><span data-ttu-id="46d34-144">Konfigurieren von app-Zuweisungen</span><span class="sxs-lookup"><span data-stu-id="46d34-144">Configure app assignments</span></span>

<span data-ttu-id="46d34-145">Konfigurieren Sie in diesem Schritt die Zuweisungen für die app-Suite.</span><span class="sxs-lookup"><span data-stu-id="46d34-145">In this step, configure the assignments for the app suite.</span></span> <span data-ttu-id="46d34-146">Beachten Sie, dass der verfügbare app-Typ in Kürze verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="46d34-146">Note that the available app type is coming soon.</span></span>

1.  <span data-ttu-id="46d34-147">Wählen Sie die app-Sammlung in der Liste der apps und **Zuweisungen**.</span><span class="sxs-lookup"><span data-stu-id="46d34-147">Select the app suite in the list of apps, and select **Assignments**.</span></span>
2.  <span data-ttu-id="46d34-148">Wählen Sie **wählen Sie Gruppen**.</span><span class="sxs-lookup"><span data-stu-id="46d34-148">Choose **Select groups**.</span></span>
3.  <span data-ttu-id="46d34-149">Weisen Sie die Sammlung an die Gruppen, denen, die Sie auswählen.</span><span class="sxs-lookup"><span data-stu-id="46d34-149">Assign the suite to the groups you choose.</span></span> <span data-ttu-id="46d34-150">Weitere Informationen finden Sie unter [Zuweisen von Apps zu Gruppen mit Microsoft Intune](/intune/apps-deploy).</span><span class="sxs-lookup"><span data-stu-id="46d34-150">For more information, see [How to assign apps to groups with Microsoft Intune](/intune/apps-deploy).</span></span>
4.  <span data-ttu-id="46d34-151">Wählen Sie für jede Gruppe **erfordern installieren**.</span><span class="sxs-lookup"><span data-stu-id="46d34-151">For each group, you select **Require Install**.</span></span>
        >[!Note]
        > You cannot uninstall Office 365 through Intune.

5. <span data-ttu-id="46d34-152">Wählen Sie **speichern** um Ihre Zuweisungen zu übernehmen.</span><span class="sxs-lookup"><span data-stu-id="46d34-152">Select **Save** to commit your assignments.</span></span>

## <a name="next-steps"></a><span data-ttu-id="46d34-153">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="46d34-153">Next steps</span></span>

<span data-ttu-id="46d34-154">Zum Hinzufügen von Office 365-apps auf Windows 10-Gerät finden Sie unter [Zuweisen von Office 365 ProPlus 2016 apps für Windows 10-Geräte mit Microsoft Intune](/intune/apps-add-office365).</span><span class="sxs-lookup"><span data-stu-id="46d34-154">To learn about adding Office 365 apps to Windows 10 device, see [How to assign Office 365 ProPlus 2016 apps to Windows 10 devices with Microsoft Intune](/intune/apps-add-office365).</span></span>
