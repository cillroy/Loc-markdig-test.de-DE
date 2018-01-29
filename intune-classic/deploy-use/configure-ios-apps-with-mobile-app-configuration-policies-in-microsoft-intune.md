---
title: Verwenden von Richtlinien zur Konfiguration von mobilen iOS-Apps
description: "Verwenden Sie Konfigurationsrichtlinien für mobile Apps in Intune, um Einstellungen anzugeben, die beim Ausführen einer iOS-App durch Benutzer erforderlich sind."
keywords: 
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 12/27/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: fc6b645a-e837-4b2a-a10f-144065cbd8dd
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 8abf6a84227c640838bfbb1f454dca7fe321f08c
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2018
---
# <a name="configure-ios-apps-with-mobile-app-configuration-policies-in-microsoft-intune"></a><span data-ttu-id="e0e1a-103">Konfigurieren von iOS-Apps mit Konfigurationsrichtlinien für mobile Apps in Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="e0e1a-103">Configure iOS apps with mobile app configuration policies in Microsoft Intune</span></span>

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="e0e1a-104">Verwenden Sie Konfigurationsrichtlinien für mobile Apps in Microsoft Intune, um Einstellungen anzugeben, die beim Ausführen einer App durch Benutzer erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="e0e1a-104">Use mobile app configuration policies in Microsoft Intune to supply settings that might be required when users run an app.</span></span> <span data-ttu-id="e0e1a-105">Beispielsweise kann eine App vom Benutzer Folgendes anfordern:</span><span class="sxs-lookup"><span data-stu-id="e0e1a-105">For example, an app might require users to specify:</span></span>

-   <span data-ttu-id="e0e1a-106">Eine benutzerdefinierte Portnummer</span><span class="sxs-lookup"><span data-stu-id="e0e1a-106">A custom port number.</span></span>

-   <span data-ttu-id="e0e1a-107">Spracheinstellungen</span><span class="sxs-lookup"><span data-stu-id="e0e1a-107">Language settings.</span></span>

-   <span data-ttu-id="e0e1a-108">Sicherheitseinstellungen</span><span class="sxs-lookup"><span data-stu-id="e0e1a-108">Security settings.</span></span>

-   <span data-ttu-id="e0e1a-109">Brandingeinstellungen, z. B. ein Unternehmenslogo</span><span class="sxs-lookup"><span data-stu-id="e0e1a-109">Branding settings such as a company logo.</span></span>

<span data-ttu-id="e0e1a-110">Wenn Benutzer diese Einstellungen nicht ordnungsgemäß eingeben, kann dies zur erhöhten Belastung Ihres Helpdesks führen und die Annahme der neuen Apps verlangsamen.</span><span class="sxs-lookup"><span data-stu-id="e0e1a-110">If users enter these settings incorrectly, this can increase the burden on your help desk and slow the adoption of new apps.</span></span>

<span data-ttu-id="e0e1a-111">Mit Konfigurationsrichtlinien für mobile Apps können Sie diese Probleme beseitigen, da Sie diese Einstellungen für Benutzer in einer Richtlinie bereitstellen können, bevor die Benutzer die App ausführen.</span><span class="sxs-lookup"><span data-stu-id="e0e1a-111">Mobile app configuration policies can help you eliminate these problems by letting you deploy these settings to users in a policy before they run the app.</span></span> <span data-ttu-id="e0e1a-112">Die Einstellungen werden dann automatisch bereitgestellt, und die Benutzer müssen keine weitere Aktion durchführen.</span><span class="sxs-lookup"><span data-stu-id="e0e1a-112">The settings are then supplied automatically, and users need to take no action.</span></span>

<span data-ttu-id="e0e1a-113">Sie stellen diese Richtlinien nicht direkt für Benutzer und Geräte bereit.</span><span class="sxs-lookup"><span data-stu-id="e0e1a-113">You do not deploy these policies directly to users and devices.</span></span> <span data-ttu-id="e0e1a-114">Stattdessen verknüpfen Sie eine Richtlinie mit einer App und stellen dann die App bereit.</span><span class="sxs-lookup"><span data-stu-id="e0e1a-114">Instead, you associate a policy with an app, and then deploy the app.</span></span> <span data-ttu-id="e0e1a-115">Die Richtlinieneinstellungen werden immer dann verwendet, wenn die Anwendung danach sucht (in der Regel beim ersten Ausführen).</span><span class="sxs-lookup"><span data-stu-id="e0e1a-115">The policy settings will be used whenever the app checks for them (typically, the first time it is run).</span></span>

> [!TIP]
> <span data-ttu-id="e0e1a-116">Dieser Richtlinientyp ist zurzeit nur für Geräte unter iOS 8.0 und höher verfügbar.</span><span class="sxs-lookup"><span data-stu-id="e0e1a-116">This policy type is currently available only for devices running iOS 8.0 and later.</span></span> <span data-ttu-id="e0e1a-117">Er unterstützt die folgenden App-Installationstypen:</span><span class="sxs-lookup"><span data-stu-id="e0e1a-117">It supports the following app installation types:</span></span>
>
> -   <span data-ttu-id="e0e1a-118">**Verwaltete iOS-App aus dem App Store**</span><span class="sxs-lookup"><span data-stu-id="e0e1a-118">**Managed iOS app from the app store**</span></span>
> -   <span data-ttu-id="e0e1a-119">**App-Paket für iOS**</span><span class="sxs-lookup"><span data-stu-id="e0e1a-119">**App package for iOS**</span></span>
>
> <span data-ttu-id="e0e1a-120">Weitere Informationen zu Installationstypen von Apps finden Sie unter [Bereitstellen von Apps mit Microsoft Intune](deploy-apps.md).</span><span class="sxs-lookup"><span data-stu-id="e0e1a-120">For more information about app installation types, see [Deploy apps with Microsoft Intune](deploy-apps.md).</span></span>

## <a name="configure-a-mobile-app-configuration-policy"></a><span data-ttu-id="e0e1a-121">Konfigurieren einer Konfigurationsrichtlinie für mobile Apps</span><span class="sxs-lookup"><span data-stu-id="e0e1a-121">Configure a mobile app configuration policy</span></span>

1.  <span data-ttu-id="e0e1a-122">Wählen Sie in der [Microsoft Intune-Verwaltungskonsole](https://manage.microsoft.com) die Optionen **Richtlinie** &gt; **Übersicht** &gt; **Richtlinie hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="e0e1a-122">In the [Microsoft Intune administration console](https://manage.microsoft.com), choose **Policy** &gt; **Overview** &gt; **Add Policy**.</span></span>

2.  <span data-ttu-id="e0e1a-123">Erweitern Sie in der Liste der Richtlinien den Eintrag **iOS**, wählen Sie **Mobile App-Konfiguration** und dann **Richtlinie erstellen** aus.</span><span class="sxs-lookup"><span data-stu-id="e0e1a-123">In the list of policies, expand **iOS**, choose **Mobile App Configuration**, and then choose **Create Policy**.</span></span>

    > [!TIP]
    > <span data-ttu-id="e0e1a-124">Sie können für diesen Richtlinientyp nur benutzerdefinierte Einstellungen konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="e0e1a-124">You can configure only custom settings for this policy type.</span></span> <span data-ttu-id="e0e1a-125">Empfohlene Einstellungen sind nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="e0e1a-125">Recommended settings are not available.</span></span>

3.  <span data-ttu-id="e0e1a-126">Im Abschnitt **Allgemein** der Seite **Richtlinie erstellen** geben Sie einen Namen und eine optionale Beschreibung für die Konfigurationsrichtlinie für mobile Apps an.</span><span class="sxs-lookup"><span data-stu-id="e0e1a-126">In the **General** section of the **Create Policy** page, supply a name and an optional description for the mobile app configuration policy.</span></span>

4.  <span data-ttu-id="e0e1a-127">Geben oder fügen Sie im Abschnitt **Konfigurationsrichtlinie für mobile Apps** der Seite eine XML-Eigenschaftenliste mit den App-Konfigurationseinstellungen in das Feld ein, die verwendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="e0e1a-127">In the **Mobile App Configuration Policy** section of the page, in the box, enter or paste an  XML property list that contains the app configuration settings that you want.</span></span> <span data-ttu-id="e0e1a-128">Das Format der XML-Eigenschaftenliste variiert je nach der App, die Sie konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="e0e1a-128">The format of the XML property list will vary depending on the app you are configuring.</span></span> <span data-ttu-id="e0e1a-129">Wenden Sie sich an den Hersteller der App, um ausführliche Informationen über das genau zu verwendende Format zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="e0e1a-129">Contact the supplier of the app for details about the exact format to use.</span></span>

    > [!TIP]
    > <span data-ttu-id="e0e1a-130">Weitere Informationen zu XML-Eigenschaftenlisten finden Sie unter [Understanding XML Property Lists](https://developer.apple.com/library/ios/documentation/Cocoa/Conceptual/PropertyLists/UnderstandXMLPlist/UnderstandXMLPlist.html) in der iOS Developer Library.</span><span class="sxs-lookup"><span data-stu-id="e0e1a-130">To find out more about XML property lists, see [Understanding XML Property Lists](https://developer.apple.com/library/ios/documentation/Cocoa/Conceptual/PropertyLists/UnderstandXMLPlist/UnderstandXMLPlist.html) in the iOS Developer Library.</span></span>

5.  <span data-ttu-id="e0e1a-131">Klicken Sie auf **Überprüfen** um sicherzustellen, dass der eingegebene XML-Code einem gültigen Format für Eigenschaftenlisten entspricht.</span><span class="sxs-lookup"><span data-stu-id="e0e1a-131">Click **Validate** to ensure that the XML that you entered is in a valid property list format.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="e0e1a-132">Beim Klicken auf **Überprüfen** prüft Intune, ob der von Ihnen eingegebene XML-Code in einem gültigen Format vorliegt.</span><span class="sxs-lookup"><span data-stu-id="e0e1a-132">When you click **Validate**, Intune checks that the XML you entered is in a valid format.</span></span> <span data-ttu-id="e0e1a-133">Es wird nicht überprüft, ob die XML-Eigenschaftenliste mit der App verwendet werden kann, der sie zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="e0e1a-133">It does not check that the XML property list will work with the app that it is associated with.</span></span>

6.  <span data-ttu-id="e0e1a-134">Klicken Sie abschließend auf **Richtlinie speichern**.</span><span class="sxs-lookup"><span data-stu-id="e0e1a-134">When you are done, click **Save Policy**.</span></span>

<span data-ttu-id="e0e1a-135">Die neue Richtlinie wird im Knoten **Konfigurationsrichtlinien** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="e0e1a-135">The new policy is displayed in the **Configuration Policies** node.</span></span>

## <a name="information-about-the-xml-file-format"></a><span data-ttu-id="e0e1a-136">Informationen zum XML-Dateiformat</span><span class="sxs-lookup"><span data-stu-id="e0e1a-136">Information about the XML file format</span></span>

<span data-ttu-id="e0e1a-137">Intune unterstützt die folgenden Datentypen in einer Eigenschaftenliste:</span><span class="sxs-lookup"><span data-stu-id="e0e1a-137">Intune supports the following data types in a property list:</span></span>

- <span data-ttu-id="e0e1a-138">&lt;integer&gt;</span><span class="sxs-lookup"><span data-stu-id="e0e1a-138">&lt;integer&gt;</span></span>
- <span data-ttu-id="e0e1a-139">&lt;real&gt;</span><span class="sxs-lookup"><span data-stu-id="e0e1a-139">&lt;real&gt;</span></span>
- <span data-ttu-id="e0e1a-140">&lt;string&gt;</span><span class="sxs-lookup"><span data-stu-id="e0e1a-140">&lt;string&gt;</span></span>
- <span data-ttu-id="e0e1a-141">&lt;array&gt;</span><span class="sxs-lookup"><span data-stu-id="e0e1a-141">&lt;array&gt;</span></span>
- <span data-ttu-id="e0e1a-142">&lt;dict&gt;</span><span class="sxs-lookup"><span data-stu-id="e0e1a-142">&lt;dict&gt;</span></span>
- <span data-ttu-id="e0e1a-143">&lt;true /&gt; oder &lt;false /&gt;</span><span class="sxs-lookup"><span data-stu-id="e0e1a-143">&lt;true /&gt; or &lt;false /&gt;</span></span>

<span data-ttu-id="e0e1a-144">Weitere Informationen zu Datentypen finden Sie unter [About Property Lists](https://developer.apple.com/library/ios/documentation/Cocoa/Conceptual/PropertyLists/AboutPropertyLists/AboutPropertyLists.html) in der iOS Developer Library.</span><span class="sxs-lookup"><span data-stu-id="e0e1a-144">For more information about data types, see [About Property Lists](https://developer.apple.com/library/ios/documentation/Cocoa/Conceptual/PropertyLists/AboutPropertyLists/AboutPropertyLists.html) in the iOS Developer Library.</span></span>

<span data-ttu-id="e0e1a-145">Darüber hinaus unterstützt Intune die folgenden Tokentypen in der Eigenschaftenliste:</span><span class="sxs-lookup"><span data-stu-id="e0e1a-145">Additionally, Intune supports the following token types in the property list:</span></span>
- <span data-ttu-id="e0e1a-146">\{\{userprincipalname\}\} – (Beispiel: **John@contoso.com**)</span><span class="sxs-lookup"><span data-stu-id="e0e1a-146">\{\{userprincipalname\}\} - (Example: **John@contoso.com**)</span></span>
- <span data-ttu-id="e0e1a-147">\{\{mail\}\} – (Beispiel: **John@contoso.com**)</span><span class="sxs-lookup"><span data-stu-id="e0e1a-147">\{\{mail\}\} - (Example: **John@contoso.com**)</span></span>
- <span data-ttu-id="e0e1a-148">\{\{partialupn\}\} – (Beispiel: **John**)</span><span class="sxs-lookup"><span data-stu-id="e0e1a-148">\{\{partialupn\}\} - (Example: **John**)</span></span>
- <span data-ttu-id="e0e1a-149">\{\{accountid\}\} – (Beispiel: **fc0dc142-71d8-4b12-bbea-bae2a8514c81**)</span><span class="sxs-lookup"><span data-stu-id="e0e1a-149">\{\{accountid\}\} - (Example: **fc0dc142-71d8-4b12-bbea-bae2a8514c81**)</span></span>
- <span data-ttu-id="e0e1a-150">\{\{deviceid\}\} – (Beispiel: **b9841cd9-9843-405f-be28-b2265c59ef97**)</span><span class="sxs-lookup"><span data-stu-id="e0e1a-150">\{\{deviceid\}\} - (Example: **b9841cd9-9843-405f-be28-b2265c59ef97**)</span></span>
- <span data-ttu-id="e0e1a-151">\{\{userid\}\} – (Beispiel: **3ec2c00f-b125-4519-acf0-302ac3761822**)</span><span class="sxs-lookup"><span data-stu-id="e0e1a-151">\{\{userid\}\} - (Example: **3ec2c00f-b125-4519-acf0-302ac3761822**)</span></span>
- <span data-ttu-id="e0e1a-152">\{\{username\}\} – (Beispiel: **John Doe**)</span><span class="sxs-lookup"><span data-stu-id="e0e1a-152">\{\{username\}\} - (Example: **John Doe**)</span></span>
- <span data-ttu-id="e0e1a-153">\{\{serialnumber\}\} – (Beispiel: **F4KN99ZUG5V2**) für iOS-Geräte</span><span class="sxs-lookup"><span data-stu-id="e0e1a-153">\{\{serialnumber\}\} - (Example: **F4KN99ZUG5V2**) for iOS devices</span></span>
- <span data-ttu-id="e0e1a-154">\{\{serialnumberlast4digits\}\} – (Beispiel: **G5V2**) für iOS-Geräte</span><span class="sxs-lookup"><span data-stu-id="e0e1a-154">\{\{serialnumberlast4digits\}\} - (Example: **G5V2**) for iOS devices</span></span>

<span data-ttu-id="e0e1a-155">Die Zeichen \{\{ und \}\} werden nur von Tokentypen verwendet und dürfen nicht für andere Zwecke verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="e0e1a-155">The \{\{ and \}\} characters are used by token types only and must not be used for other purposes.</span></span>

## <a name="associate-a-mobile-app-configuration-policy-with-an-app"></a><span data-ttu-id="e0e1a-156">Zuordnen einer Konfigurationsrichtlinie für mobile Apps zu einer App</span><span class="sxs-lookup"><span data-stu-id="e0e1a-156">Associate a mobile app configuration policy with an app</span></span>
<span data-ttu-id="e0e1a-157">Nachdem Sie eine Konfigurationsrichtlinie für mobile Apps erstellt haben, müssen Sie sie der iOS-App zuordnen, für die die Einstellungen in der Konfigurationsrichtlinie gelten sollen.</span><span class="sxs-lookup"><span data-stu-id="e0e1a-157">After you have created a mobile app configuration policy, you must associate it with the iOS app to which you want the settings in the configuration policy to apply.</span></span>

<span data-ttu-id="e0e1a-158">Führen Sie dazu die Schritte zum Erstellen einer App-Bereitstellung in [Hinzufügen von Apps für mobile Geräte in Microsoft Intune](add-apps-for-mobile-devices-in-microsoft-intune.md) und [Bereitstellen von Apps mit Microsoft Intune](deploy-apps-in-microsoft-intune.md) aus.</span><span class="sxs-lookup"><span data-stu-id="e0e1a-158">To do this, follow the steps to create an app deployment in [Add apps for mobile devices in Microsoft Intune](add-apps-for-mobile-devices-in-microsoft-intune.md) and [Deploy apps with Microsoft Intune](deploy-apps-in-microsoft-intune.md).</span></span> <span data-ttu-id="e0e1a-159">Wenn Sie die Seite **Mobile App-Konfiguration** des Assistenten erreichen, wählen Sie in der Dropdownliste **App-Konfigurationsrichtlinie** die Richtlinie aus, die Sie der App zuordnen möchten.</span><span class="sxs-lookup"><span data-stu-id="e0e1a-159">When you reach the **Mobile App Configuration** page of the wizard, select the policy that you want to associate with the app from the **App Configuration Policy** drop-down list.</span></span>

<span data-ttu-id="e0e1a-160">Fahren Sie mit dem Bereitstellen und Überwachen der App-Bereitstellung wie gewohnt fort.</span><span class="sxs-lookup"><span data-stu-id="e0e1a-160">Then, continue to deploy and monitor the app deployment as usual.</span></span>

<span data-ttu-id="e0e1a-161">Wenn die bereitgestellte App auf einem Gerät gestartet wird, wird sie mit den Einstellungen ausgeführt, die Sie in der Konfigurationsrichtlinie für mobile Apps konfiguriert haben.</span><span class="sxs-lookup"><span data-stu-id="e0e1a-161">When the deployed app is run on a device, it will run with the settings that you configured in the mobile app configuration policy.</span></span>

> [!TIP]
> <span data-ttu-id="e0e1a-162">Wenn mindestens eine Konfigurationsrichtlinie für mobile Apps einen Konflikt verursacht, wird keine Richtlinie durchgesetzt.</span><span class="sxs-lookup"><span data-stu-id="e0e1a-162">If one or more mobile app configuration policies conflict, neither policy is enforced.</span></span> <span data-ttu-id="e0e1a-163">Der Konflikt wird im **Dashboard**  der Intune-Verwaltungskonsole gemeldet.</span><span class="sxs-lookup"><span data-stu-id="e0e1a-163">The conflict will be reported in the Intune administration console **Dashboard**.</span></span>

## <a name="example-format-for-a-mobile-app-configuration-xml-file"></a><span data-ttu-id="e0e1a-164">Beispielformat für die XML-Datei für die Konfiguration mobiler Apps</span><span class="sxs-lookup"><span data-stu-id="e0e1a-164">Example format for a mobile app configuration XML file</span></span>

<span data-ttu-id="e0e1a-165">Wenn Sie eine Datei für die Konfiguration mobiler Apps erstellen, können Sie einen oder mehrere der folgenden Werte mit diesem Format angeben:</span><span class="sxs-lookup"><span data-stu-id="e0e1a-165">When you create a mobile app configuration file, you can specify one or more of the following values by using this format:</span></span>

```
<dict>
  <key>userprincipalname</key>
  <string>{{userprincipalname}}</string>
  <key>mail</key>
  <string>{{mail}}</string>
  <key>partialupn</key>
  <string>{{partialupn}}</string>
  <key>accountid</key>
  <string>{{accountid}}</string>
  <key>deviceid</key>
  <string>{{deviceid}}</string>
  <key>userid</key>
  <string>{{userid}}</string>
  <key>username</key>
  <string>{{username}}</string>
  <key>serialnumber</key>
  <string>{{serialnumber}}</string>
  <key>serialnumberlast4digits</key>
  <string>{{serialnumberlast4digits}}</string>
  <key>udidlast4digits</key>
  <string>{{udidlast4digits}}</string>
</dict>
```
