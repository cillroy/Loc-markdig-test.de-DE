---
title: "Konfigurationsrichtlinie für Android for Work-Apps"
description: "Verwenden Sie Konfigurationsrichtlinien für mobile Apps in Intune, um Einstellungen anzugeben, die beim Ausführen einer Android for Work-App durch Benutzer erforderlich sind."
keywords: 
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 02/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: fc6b645a-e837-4b2a-a10f-144065cbd8dd
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: chrisbal
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: f734c7884d7ffe3671e5fa6e20d44355cfd080ed
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2017
---
# <a name="configure-android-for-work-apps-with-mobile-app-configuration-policies-in-microsoft-intune"></a><span data-ttu-id="751b4-103">Konfigurieren von Apps mit Konfigurationsrichtlinien für mobile Apps in Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="751b4-103">Configure Android for Work apps with mobile app configuration policies in Microsoft Intune</span></span>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="751b4-104">Verwenden Sie Konfigurationsrichtlinien für mobile Apps in Microsoft Intune, um Einstellungen anzugeben, die beim Ausführen einer App durch Benutzer erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="751b4-104">Use mobile app configuration policies in Microsoft Intune to supply settings that might be required when users run an app.</span></span> <span data-ttu-id="751b4-105">Beispielsweise kann eine App vom Benutzer Folgendes anfordern:</span><span class="sxs-lookup"><span data-stu-id="751b4-105">For example, an app might require users to specify:</span></span>

-   <span data-ttu-id="751b4-106">Eine benutzerdefinierte Portnummer</span><span class="sxs-lookup"><span data-stu-id="751b4-106">A custom port number</span></span>
-   <span data-ttu-id="751b4-107">Spracheinstellungen</span><span class="sxs-lookup"><span data-stu-id="751b4-107">Language settings</span></span>
-   <span data-ttu-id="751b4-108">Brandingeinstellungen wie z. B. ein Unternehmenslogo</span><span class="sxs-lookup"><span data-stu-id="751b4-108">Branding settings such as a company logo</span></span>

<span data-ttu-id="751b4-109">Wenn Benutzer Einstellungen nicht ordnungsgemäß eingeben, kann dies zur erhöhten Belastung Ihres Helpdesks führen und die Annahme der neuen Apps verlangsamen.</span><span class="sxs-lookup"><span data-stu-id="751b4-109">If users enter settings incorrectly, it can increase the burden on your help desk and slow the adoption of new apps.</span></span>

<span data-ttu-id="751b4-110">Mit Richtlinien zur Konfiguration von mobilen Apps können Sie diese Einstellungen auf Geräten bereitstellen, bevor Benutzer die App ausführen.</span><span class="sxs-lookup"><span data-stu-id="751b4-110">Mobile app configuration policies let you deploy these settings to devices before users run the app.</span></span> <span data-ttu-id="751b4-111">Die Einstellungen werden automatisch bereitgestellt, und die Benutzer müssen keine weitere Aktion durchführen.</span><span class="sxs-lookup"><span data-stu-id="751b4-111">The settings are supplied automatically, and users need to take no action.</span></span>

<span data-ttu-id="751b4-112">Damit Richtlinien für die App-Konfiguration verwendet werden können, muss der App-Entwickler beim Erstellen der App Konfigurationseinstellungen für Unternehmens-Apps verfügbar machen.</span><span class="sxs-lookup"><span data-stu-id="751b4-112">To utilize app configuration policies, the app developer must have exposed enterprise app configurations when they created it.</span></span> <span data-ttu-id="751b4-113">Für Google Chrome werden beispielsweise Einstellungen bereitgestellt, mit denen Sie Standardlesezeichen, zulässige und verweigerte Websites und vieles mehr festlegen können.</span><span class="sxs-lookup"><span data-stu-id="751b4-113">For example, Google Chrome exposes settings that let you set default bookmarks, allowed and denied sites, and more.</span></span> <span data-ttu-id="751b4-114">Wenden Sie sich an den Entwickler der App, um herauszufinden, ob diese Einstellungen unterstützt und wie sie in der Richtlinie angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="751b4-114">Contact the developer of the app to see if these settings are supported and how to specify them in the policy.</span></span>

<span data-ttu-id="751b4-115">Die Richtlinie für die App-Konfiguration stellen Sie für die Benutzer bereit, für die Sie die App bereitgestellt haben, die Sie konfigurieren möchten.</span><span class="sxs-lookup"><span data-stu-id="751b4-115">You deploy the app configuration policy to the same users to whom you have deployed the app you want to configure.</span></span> <span data-ttu-id="751b4-116">App-Einstellungen werden angewendet, wenn die App ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="751b4-116">App settings are applied when the app is run.</span></span>

## <a name="configure-a-mobile-app-configuration-policy"></a><span data-ttu-id="751b4-117">Konfigurieren einer Konfigurationsrichtlinie für mobile Apps</span><span class="sxs-lookup"><span data-stu-id="751b4-117">Configure a mobile app configuration policy</span></span>

1.  <span data-ttu-id="751b4-118">Wählen Sie in der [Microsoft Intune-Verwaltungskonsole](https://manage.microsoft.com) die Optionen **Richtlinie** &gt; **Übersicht** &gt; **Richtlinie hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="751b4-118">In the [Microsoft Intune administration console](https://manage.microsoft.com), choose **Policy** &gt; **Overview** &gt; **Add Policy**.</span></span>

2.  <span data-ttu-id="751b4-119">Erweitern Sie in der Liste der Richtlinien den Eintrag **Android for Work**, wählen Sie **Richtlinie zur Konfiguration mobiler Apps (Android for Work)** und anschließend **Richtlinie erstellen** aus.</span><span class="sxs-lookup"><span data-stu-id="751b4-119">In the list of policies, expand **Android for Work**, choose **Mobile App Configuration Policy (Android for Work)**, and then choose **Create Policy**.</span></span>

    > [!TIP]
    > <span data-ttu-id="751b4-120">Sie können für diesen Richtlinientyp nur benutzerdefinierte Einstellungen konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="751b4-120">You can configure only custom settings for this policy type.</span></span> <span data-ttu-id="751b4-121">Empfohlene Einstellungen sind nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="751b4-121">Recommended settings are not available.</span></span>

3.  <span data-ttu-id="751b4-122">Im Abschnitt **Allgemein** der Seite **Richtlinie erstellen** geben Sie einen Namen und eine optionale Beschreibung für die Konfigurationsrichtlinie für mobile Apps an.</span><span class="sxs-lookup"><span data-stu-id="751b4-122">In the **General** section of the **Create Policy** page, supply a name and an optional description for the mobile app configuration policy.</span></span>

4. <span data-ttu-id="751b4-123">Geben Sie im Abschnitt **Richtlinie zur Konfiguration mobiler Apps** der Seite die folgenden Informationen an:</span><span class="sxs-lookup"><span data-stu-id="751b4-123">In the **Mobile App Configuration Policy** section of the page, specify the following information:</span></span>
    - <span data-ttu-id="751b4-124">**Paket-ID für die Anwendung, auf die diese Konfiguration angewendet wird**: Die Paket-ID finden Sie im Abschnitt „id=“ der App-URL auf der entsprechenden Google Play-Seite.</span><span class="sxs-lookup"><span data-stu-id="751b4-124">**Package ID for the application that this configuration applies to** - The package ID can be found in the 'id=' section of the app URL on it's Google Play page.</span></span> <span data-ttu-id="751b4-125">Die Paket-ID der Microsoft Excel-App lautet z.B. **com.microsoft.office.excel**.</span><span class="sxs-lookup"><span data-stu-id="751b4-125">For example, the package ID for the Microsoft Excel app is **com.microsoft.office.excel**.</span></span>
    - <span data-ttu-id="751b4-126">Geben Sie in das Textfeld die Daten für die App-Einstellungen ein, die Sie konfigurieren möchten.</span><span class="sxs-lookup"><span data-stu-id="751b4-126">In the text box, enter the data for the app settings you want to configure.</span></span> <span data-ttu-id="751b4-127">Diese Einstellungen erhalten Sie vom Anbieter der App.</span><span class="sxs-lookup"><span data-stu-id="751b4-127">You get these settings from the supplier of the app.</span></span> <span data-ttu-id="751b4-128">Nicht alle Apps unterstützen diese Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="751b4-128">Not all apps support these settings.</span></span>
5.  <span data-ttu-id="751b4-129">Klicken Sie auf **Überprüfen** um sicherzustellen, dass die eingegebenen Daten einem gültigen Format für Eigenschaftenlisten entspricht.</span><span class="sxs-lookup"><span data-stu-id="751b4-129">Click **Validate** to ensure that the data that you entered is in a valid property list format.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="751b4-130">Beim Klicken auf **Überprüfen** prüft Intune, ob die von Ihnen eingegebenen Konfigurationsdaten in einem gültigen Format vorliegen.</span><span class="sxs-lookup"><span data-stu-id="751b4-130">When you click **Validate**, Intune checks that the configuration data you entered is in a valid format.</span></span> <span data-ttu-id="751b4-131">Es wird nicht überprüft, ob die Daten mit der App verwendet werden können, der sie zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="751b4-131">It does not check that the data will work with the app that it is associated with.</span></span>

6.  <span data-ttu-id="751b4-132">Klicken Sie abschließend auf **Richtlinie speichern**.</span><span class="sxs-lookup"><span data-stu-id="751b4-132">When you are done, click **Save Policy**.</span></span>

<span data-ttu-id="751b4-133">Die neue Richtlinie wird im Knoten **Konfigurationsrichtlinien** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="751b4-133">The new policy is displayed in the **Configuration Policies** node.</span></span>


## <a name="deploy-the-app-configuration-policy"></a><span data-ttu-id="751b4-134">Bereitstellen der Richtlinie für die App-Konfiguration</span><span class="sxs-lookup"><span data-stu-id="751b4-134">Deploy the app configuration policy</span></span>
<span data-ttu-id="751b4-135">Nachdem Sie die Richtlinie zur Konfiguration mobiler Apps erstellt haben, müssen Sie sie für die Benutzer bereitstellen, für die Sie die App bereitstellen, für die die Einstellungen gelten.</span><span class="sxs-lookup"><span data-stu-id="751b4-135">After you have created a mobile app configuration policy, you must deploy it to the same users to whom you deploy the app to which the settings will apply.</span></span>

<span data-ttu-id="751b4-136">Informationen zum Bereitstellen von Richtlinien finden Sie unter [Bereitstellen einer Konfigurationsrichtlinie](/intune-classic/deploy-use/manage-settings-and-features-on-your-devices-with-microsoft-intune-policies#deploy-a-configuration-policy).</span><span class="sxs-lookup"><span data-stu-id="751b4-136">For information about how to deploy policies, see [deploy a configuration policy](/intune-classic/deploy-use/manage-settings-and-features-on-your-devices-with-microsoft-intune-policies#deploy-a-configuration-policy)</span></span>

<span data-ttu-id="751b4-137">Informationen zum Bereitstellen von Apps für Android for Work-Geräte finden Sie unter [How to deploy apps to Android for Work devices with Intune (Bereitstellen von Apps für Android for Work-Geräte mit Intune)](android-for-work-apps.md).</span><span class="sxs-lookup"><span data-stu-id="751b4-137">For information about how to deploy apps to Android for Work devices, see [How to deploy Android for Work apps with Intune](android-for-work-apps.md).</span></span>

<span data-ttu-id="751b4-138">Wenn die bereitgestellte App auf einem Gerät gestartet wird, wird sie mit den Einstellungen ausgeführt, die Sie in der Konfigurationsrichtlinie für mobile Apps konfiguriert haben.</span><span class="sxs-lookup"><span data-stu-id="751b4-138">When the deployed app is run on a device, it will run with the settings that you configured in the mobile app configuration policy.</span></span>

> [!TIP]
> <span data-ttu-id="751b4-139">Stellen Sie für jede App nur eine App-Konfigurationsrichtlinie für einen Benutzer bereit.</span><span class="sxs-lookup"><span data-stu-id="751b4-139">Only deploy one app configuration policy for each app to a user.</span></span>
