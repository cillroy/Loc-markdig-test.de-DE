---
title: "Schützen branchenspezifischer Apps auf nicht registrierten Geräten"
description: "In diesem Thema wird beschrieben, wie Sie Ihre benutzerdefinierte Reihe von Branchen-Anwendungen vorbereiten können, sodass Sie Verwaltungsrichtlinien für mobile Apps anwenden können, die helfen können, Datenverluste zu verhindern."
keywords: 
author: mattbriggs
ms.author: mabriggs
manager: angrobe
ms.date: 11/14/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 00219467-a62e-43b6-954b-3084f54c45ba
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 27e60cc669d5097fe94b23af21b7cde3823bbe12
ms.sourcegitcommit: e37e916e2bf14f092d3a767bc90d68c181d739fb
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/03/2018
---
# <a name="protect-line-of-business-apps-and-data-on-devices-that-are-not-enrolled-in-microsoft-intune"></a><span data-ttu-id="80932-103">Schützen von branchenspezifischen Apps und Daten auf nicht in Microsoft Intune registrierten Geräten</span><span class="sxs-lookup"><span data-stu-id="80932-103">Protect line-of-business apps and data on devices that are not enrolled in Microsoft Intune</span></span>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="80932-104">Mit Richtlinien zur Verwaltung mobiler Anwendungen (Mobile App Management, MAM) können Sie Unternehmensdaten schützen, indem Aktionen, die zu Datenlecks führen könnten, eingeschränkt und Datenzugriffsanforderungen wie die Eingabe einer App-PIN erzwungen werden.</span><span class="sxs-lookup"><span data-stu-id="80932-104">Mobile application management (MAM) policies help protect company data by restricting actions that could leak company data and by enforcing data access requirements, such as an app PIN.</span></span> <span data-ttu-id="80932-105">Zum Anwenden von MAM-Richtlinien auf branchenspezifische iOS- und Android-Apps müssen Sie die App zunächst mit dem Microsoft Intune App Wrapping Tool umschließen.</span><span class="sxs-lookup"><span data-stu-id="80932-105">To apply MAM policies to iOS and Android line-of-business apps, you must first wrap the app with the Microsoft Intune App Wrapping Tool.</span></span> <span data-ttu-id="80932-106">Bei diesem Prozess wird einer mobilen App eine Verwaltungsebene hinzugefügt, ohne dass diese geändert werden muss, und sie wird an Benutzer verteilt.</span><span class="sxs-lookup"><span data-stu-id="80932-106">App wrapping is the process of applying a management layer to a mobile app without requiring any changes to it and distribute it to your users.</span></span>  

<span data-ttu-id="80932-107">In diesem Thema werden die erforderlichen Schritte zum Anwenden von MAM-Richtlinien auf Apps vorgestellt, auf die Benutzer auf **nicht verwalteten Geräten im Besitz von Mitarbeitern** und auf Geräten, die von einer **Lösung für die Verwaltung von Mobilgeräten (Mobile Device Management, MDM) eines Drittanbieters** verwaltet werden, zugreifen.</span><span class="sxs-lookup"><span data-stu-id="80932-107">This topic explains the steps that are required to apply MAM policies for apps that users access on **employee-owned devices that are not managed** and devices that are managed by a **third-party mobile device management (MDM) solution**.</span></span>  <span data-ttu-id="80932-108">Informationen zum Vorbereiten branchenspezifischer Apps, die auf **bei Intune MDM registrierten Geräten** ausgeführt werden, finden Sie unter [Auswählen der Vorbereitung von Apps für die mobile Anwendungsverwaltung mit Microsoft Intune](/intune/apps-prepare-mobile-application-management).</span><span class="sxs-lookup"><span data-stu-id="80932-108">To prepare your line-of-business apps that run on **devices that are enrolled in Intune MDM**, see [Decide how to prepare apps for mobile application management with Microsoft Intune](/intune/apps-prepare-mobile-application-management).</span></span>


##  <a name="step-1-prepare-the-app"></a><span data-ttu-id="80932-109">Schritt 1: Vorbereiten der App</span><span class="sxs-lookup"><span data-stu-id="80932-109">Step 1: Prepare the app</span></span>

<span data-ttu-id="80932-110">Bevor Sie MAM-Richtlinien auf eine App anwenden können, müssen Sie die App zuerst mit dem Microsoft Intune App Wrapping Tool für [iOS](/intune/app-wrapper-prepare-ios) und [Android](/intune/app-wrapper-prepare-android) umschließen, oder das [Intune App SDK](/intune/app-sdk) verwenden, um die Schutzfunktionen der Intune-App manuell zu integrieren.</span><span class="sxs-lookup"><span data-stu-id="80932-110">Before you can apply MAM policies to an app, you must first wrap the app by using the Microsoft Intune App Wrapping Tool for [iOS](/intune/app-wrapper-prepare-ios), [Android](/intune/app-wrapper-prepare-android), or use the [Intune App SDK](/intune/app-sdk) to manually integrate Intune app protection features.</span></span>

<span data-ttu-id="80932-111">Weitere Informationen zur Entscheidung zwischen dem App Wrapping Tool und dem SDK finden Sie unter [Auswählen der Vorbereitung von Apps für die mobile Anwendungsverwaltung mit Microsoft Intune](/intune/apps-prepare-mobile-application-management).</span><span class="sxs-lookup"><span data-stu-id="80932-111">For more information on using the App Wrapping Tool vs. the SDK, see [Decide how to prepare apps for mobile application management with Microsoft Intune](/intune/apps-prepare-mobile-application-management).</span></span>

## <a name="step-2-add-the-app"></a><span data-ttu-id="80932-112">Schritt 2: Hinzufügen der App</span><span class="sxs-lookup"><span data-stu-id="80932-112">Step 2: Add the app</span></span>

<span data-ttu-id="80932-113">Um Ihre branchenspezifische App zu MAM-Richtlinien zuzuordnen, müssen Sie Ihrem Intune-Abonnement/-Mandanten die App-Details wie folgt hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="80932-113">To associate your line-of-business app with MAM policies, you must add the app details to your Intune subscription/tenant by using the following steps:</span></span>

1. <span data-ttu-id="80932-114">Wechseln Sie im [Azure-Portal](https://portal.azure.com/) zu **Mobile Anwendungsverwaltung mit Intune** > **Einstellungen**, und wählen Sie **Branchenspezifische Apps**.</span><span class="sxs-lookup"><span data-stu-id="80932-114">In the [Azure portal](https://portal.azure.com/), go to **Intune mobile application management** > **Settings**, and choose **Line-of-business apps**.</span></span>

   ![Screenshot des Blatts „Einstellungen“ mit der Option „Branchenspezifische Apps“](../media/mam-azure-portal-lob-on-settings.png)

2. <span data-ttu-id="80932-116">Wählen Sie auf dem Blatt **Branchenspezifische Apps** die Option **Benutzerdefinierte App hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="80932-116">On the **Line-of-business-apps** blade, choose **Add a custom app**.</span></span>

   ![Screenshot des Blatts „Branchenspezifische Apps“ mit der Schaltfläche „Benutzerdefinierte App hinzufügen“ oben](../media/mam-azure-portal-add-lob-app-action.png)
3. <span data-ttu-id="80932-118">Geben Sie einen Namen für die App, die Paket-ID in das Feld „App-ID“ und die Plattform (iOS oder Android) an.</span><span class="sxs-lookup"><span data-stu-id="80932-118">Provide a name for the app, the bundle identifier in the App Identifier field, and the platform (iOS or Android).</span></span>

   ![Screenshot des Blatts „Benutzerdefinierte App hinzufügen“](../media/mam-azure-portal-add-app-details.png)

   <span data-ttu-id="80932-120">Dieser Schritt dient zum Erstellen einer eindeutigen Auflistung Ihrer App.</span><span class="sxs-lookup"><span data-stu-id="80932-120">This step helps create a unique listing of your app.</span></span> <span data-ttu-id="80932-121">Die App wird auch in der Liste der Ziel-Apps für eine MAM-Richtlinie für Ihren Mandanten angezeigt (siehe den nächsten Schritt).</span><span class="sxs-lookup"><span data-stu-id="80932-121">The app will also be displayed in the list of Targeted apps for a MAM policy for your tenant, as described in the next step.</span></span>

## <a name="step-3-apply-mam-policies"></a><span data-ttu-id="80932-122">Schritt 3: Anwenden von MAM-Richtlinien</span><span class="sxs-lookup"><span data-stu-id="80932-122">Step 3: Apply MAM policies</span></span>
<span data-ttu-id="80932-123">Nachdem die App-Metadaten in den Dienst hochgeladen wurden, zeigt die App die Liste mit Apps an.</span><span class="sxs-lookup"><span data-stu-id="80932-123">After the app metadata is uploaded to the service, the app shows up in the list of apps.</span></span> <span data-ttu-id="80932-124">Sie können jetzt [eine neue Richtlinie erstellen oder eine vorhandene Richtlinie verwenden](create-and-deploy-mobile-app-management-policies-with-microsoft-intune.md) und sie auf die branchenspezifische App anwenden, die Sie in Schritt 2 hinzugefügt haben.</span><span class="sxs-lookup"><span data-stu-id="80932-124">You can now [create a new policy or use an existing policy](create-and-deploy-mobile-app-management-policies-with-microsoft-intune.md), and apply it to the line-of-business app that you added in step 2.</span></span>

>[!IMPORTANT]
><span data-ttu-id="80932-125">Die MAM-Richtlinie muss für die Benutzer erstellt werden, die die umschlossene App verwenden werden.</span><span class="sxs-lookup"><span data-stu-id="80932-125">You must target the MAM policy to the users who are going to use the wrapped app.</span></span>  <span data-ttu-id="80932-126">Benutzer, für die diese Richtlinie nicht bereitgestellt wird, können die App nicht verwenden.</span><span class="sxs-lookup"><span data-stu-id="80932-126">Users who don’t have this policy deployed to them won't be able to use the app.</span></span>


  ![Screenshot des Blatts mit der Zielliste der Apps mit der angezeigten neuen branchenspezifischen App](../media/mam-azure-portal-lob-on-targeted-app-list.png)
## <a name="step-4-distribute-the-app"></a><span data-ttu-id="80932-128">Schritt 4: Verteilen der App</span><span class="sxs-lookup"><span data-stu-id="80932-128">Step 4: Distribute the app</span></span>
<span data-ttu-id="80932-129">Sie können Apps für Ihre Benutzer wie folgt bereitstellen:</span><span class="sxs-lookup"><span data-stu-id="80932-129">You can deploy apps to your users in the following ways:</span></span>
* <span data-ttu-id="80932-130">Für Geräte, die bei einer MDM-Lösung eines Drittanbieters registriert sind, können Sie die Apps über Ihre MDM-Lösung verteilen.</span><span class="sxs-lookup"><span data-stu-id="80932-130">For devices that are enrolled in a third-party MDM solution, you can distribute the apps through your MDM solution.</span></span>
* <span data-ttu-id="80932-131">Für Geräte, die von keiner MDM-Lösung verwaltet werden, benötigen Sie eine benutzerdefinierte Lösung.</span><span class="sxs-lookup"><span data-stu-id="80932-131">For devices that aren't managed by any MDM solution, you need a custom solution.</span></span> <span data-ttu-id="80932-132">Benutzer müssen die App herunterladen und auf ihrem Gerät installieren.</span><span class="sxs-lookup"><span data-stu-id="80932-132">Users must download and install the app on their device.</span></span>

## <a name="change-the-metadata"></a><span data-ttu-id="80932-133">Ändern der Metadaten</span><span class="sxs-lookup"><span data-stu-id="80932-133">Change the metadata</span></span>
<span data-ttu-id="80932-134">Falls Sie App-Details wie den Namen der App oder die Paket-ID ändern müssen, müssen Sie [die App entfernen](#remove-apps) und mit den neuen Metadaten [hinzufügen](#step-2-add-the-app).</span><span class="sxs-lookup"><span data-stu-id="80932-134">If you need to change the app details, like the name of the app or the bundle identifier, you must [remove the app](#remove-apps) and [add it](#step-2-add-the-app) with the new metadata.</span></span>

##  <a name="remove-apps"></a><span data-ttu-id="80932-135">Entfernen von Apps</span><span class="sxs-lookup"><span data-stu-id="80932-135">Remove apps</span></span>
<span data-ttu-id="80932-136">Sie können eine branchenspezifische App aus der App-Liste entfernen.</span><span class="sxs-lookup"><span data-stu-id="80932-136">You can remove a line-of-business app from the app list.</span></span> <span data-ttu-id="80932-137">Dadurch wird die App aus der Liste und die Zuordnung zu MAM-Richtlinien entfernt, ohne dass die App jedoch vom Gerät des Benutzers entfernt oder deinstalliert wird.</span><span class="sxs-lookup"><span data-stu-id="80932-137">This will remove the app from the list and will remove the association with MAM policies, but will not remove or uninstall the app from the user’s device.</span></span>  

1. <span data-ttu-id="80932-138">Wechseln Sie im [Azure-Portal](https://portal.azure.com/) zu **Intune-Verwaltung von mobilen Anwendungen** > **Einstellungen**.</span><span class="sxs-lookup"><span data-stu-id="80932-138">In the [Azure portal](https://portal.azure.com/), go to **Intune mobile app management** > **Settings**.</span></span> <span data-ttu-id="80932-139">Wählen Sie auf dem Blatt **Einstellungen** den Eintrag **Branchenspezifische Apps**, um die Liste vorhandener Apps anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="80932-139">On the **Settings** blade, choose **Line-of-business** to open the list of existing apps.</span></span>  
2. <span data-ttu-id="80932-140">Wählen Sie die App aus, die Sie entfernen möchten, und klicken Sie auf **(...)**, um das Kontextmenü zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="80932-140">Choose the app that you want to remove, and choose the **(…) context** menu.</span></span>

   ![Screenshot des Blatts „Branchenspezifische Apps“ mit der Schaltfläche mit den Auslassungszeichen](../media/mam-azure-portal-lob-context-menu.png)
3. <span data-ttu-id="80932-142">Wählen Sie **Anwendung löschen** aus, um die App zu löschen.</span><span class="sxs-lookup"><span data-stu-id="80932-142">Choose **Delete Application** to delete the app.</span></span>

   ![Screenshot des Blatts „Branchenspezifische Apps“ mit der Option „Anwendung löschen“](../media/mam-azure-portal-delete-app.png)

   <span data-ttu-id="80932-144">Dies entfernt Apps aus der Liste der branchenspezifischen Apps und der Zielliste von Apps in der MAM-Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="80932-144">This will remove apps from the list of line-of-business apps and the Targeted list of apps in the MAM policy.</span></span>
