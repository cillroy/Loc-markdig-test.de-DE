---
title: "Hinzufügen von App-Konfigurationsrichtlinien für verwaltete iOS-Geräte | Microsoft-Dokumentation"
titlesuffix: Azure portal
description: "Erfahren Sie, wie Sie App-Konfigurationsrichtlinien zum Bereitstellen von Konfigurationsdaten für eine iOS-App beim Ausführen verwenden."
keywords: 
author: erikre
ms.author: erikre
manager: angrobe
ms.date: 10/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c9163693-d748-46e0-842a-d9ba113ae5a8
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: d63963af4b95d10abca8f90c86a3b28c5781da68
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2018
---
# <a name="add-app-configuration-policies-for-managed-ios-devices"></a><span data-ttu-id="01c91-103">Hinzufügen App-Konfigurationsrichtlinien für verwaltete iOS-Geräte</span><span class="sxs-lookup"><span data-stu-id="01c91-103">Add app configuration policies for managed iOS devices</span></span>

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="01c91-104">Verwenden Sie App-Konfigurationsrichtlinien in Microsoft Intune, um Einstellungen anzugeben, wenn Benutzer eine iOS-App ausführen.</span><span class="sxs-lookup"><span data-stu-id="01c91-104">Use app configuration policies in Microsoft Intune to supply settings when users run an iOS app.</span></span> <span data-ttu-id="01c91-105">Sie weisen diese Richtlinien nicht direkt Benutzern und Geräten zu.</span><span class="sxs-lookup"><span data-stu-id="01c91-105">You do not assign these policies directly to users and devices.</span></span> <span data-ttu-id="01c91-106">Stattdessen verknüpfen Sie eine Richtlinie mit einer App und weisen dann die App zu.</span><span class="sxs-lookup"><span data-stu-id="01c91-106">Instead, you associate a policy with an app, and then assign the app.</span></span> <span data-ttu-id="01c91-107">Die Richtlinieneinstellungen werden verwendet, wenn die App danach sucht (in der Regel beim ersten Ausführen).</span><span class="sxs-lookup"><span data-stu-id="01c91-107">The policy settings are used when the app checks for them, typically the first time it is run.</span></span>

> [!TIP]
> <span data-ttu-id="01c91-108">Dieser Richtlinientyp ist zurzeit nur für Geräte unter iOS 8.0 und höher verfügbar.</span><span class="sxs-lookup"><span data-stu-id="01c91-108">This policy type is currently available only for devices running iOS 8.0 and later.</span></span> <span data-ttu-id="01c91-109">Er unterstützt die folgenden App-Installationstypen:</span><span class="sxs-lookup"><span data-stu-id="01c91-109">It supports the following app installation types:</span></span>
>
> -   <span data-ttu-id="01c91-110">**Verwaltete iOS-App aus dem App Store**</span><span class="sxs-lookup"><span data-stu-id="01c91-110">**Managed iOS app from the app store**</span></span>
> -   <span data-ttu-id="01c91-111">**App-Paket für iOS**</span><span class="sxs-lookup"><span data-stu-id="01c91-111">**App package for iOS**</span></span>
>
> <span data-ttu-id="01c91-112">Weitere Informationen zu Installationstypen von Apps finden Sie unter [Hinzufügen von Apps zu Microsoft Intune](apps-add.md).</span><span class="sxs-lookup"><span data-stu-id="01c91-112">For more information about app installation types, see [How to add an app to Microsoft Intune](apps-add.md).</span></span>

## <a name="create-an-app-configuration-policy"></a><span data-ttu-id="01c91-113">Erstellen einer Konfigurationsrichtlinie für Apps</span><span class="sxs-lookup"><span data-stu-id="01c91-113">Create an app configuration policy</span></span>

1. <span data-ttu-id="01c91-114">Melden Sie sich im Azure-Portal an.</span><span class="sxs-lookup"><span data-stu-id="01c91-114">Sign in to the Azure portal.</span></span>
2. <span data-ttu-id="01c91-115">Wählen Sie **Weitere Dienste** > **Überwachung und Verwaltung** + **Intune** aus.</span><span class="sxs-lookup"><span data-stu-id="01c91-115">Choose **More Services** > **Monitoring + Management** + **Intune**.</span></span>
3. <span data-ttu-id="01c91-116">Wählen Sie die Workload **Mobile Apps** aus.</span><span class="sxs-lookup"><span data-stu-id="01c91-116">Choose the **Mobile apps** workload.</span></span>
4. <span data-ttu-id="01c91-117">Wählen Sie in der Gruppe **Verwalten** **App-Konfigurationsrichtlinien** und dann **Hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="01c91-117">Choose **App configuration policies** in the **Manage** group, and then choose **Add**.</span></span>
5. <span data-ttu-id="01c91-118">Legen Sie die folgenden Details fest:</span><span class="sxs-lookup"><span data-stu-id="01c91-118">Set the following details:</span></span>
    - <span data-ttu-id="01c91-119">**Name**</span><span class="sxs-lookup"><span data-stu-id="01c91-119">**Name**</span></span><br>
      <span data-ttu-id="01c91-120">Der Name des Profils, das im Azure-Portal angezeigt wird</span><span class="sxs-lookup"><span data-stu-id="01c91-120">The name of the profile that will appear in the Azure portal.</span></span>
    - <span data-ttu-id="01c91-121">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="01c91-121">**Description**</span></span><br>
      <span data-ttu-id="01c91-122">Die Beschreibung des Profils, das im Azure-Portal angezeigt wird</span><span class="sxs-lookup"><span data-stu-id="01c91-122">The description of the profile that will appear in the Azure portal.</span></span>
    - <span data-ttu-id="01c91-123">**Geräteregistrierungstyp**</span><span class="sxs-lookup"><span data-stu-id="01c91-123">**Device enrollment type**</span></span><br>
      <span data-ttu-id="01c91-124">Klicken Sie auf **Verwaltete Geräte**.</span><span class="sxs-lookup"><span data-stu-id="01c91-124">Choose **Managed devices**.</span></span>
6. <span data-ttu-id="01c91-125">Wählen Sie **iOS** als **Plattform** aus.</span><span class="sxs-lookup"><span data-stu-id="01c91-125">Select **iOS** for **Platform**.</span></span>
7.  <span data-ttu-id="01c91-126">Wählen Sie **Zugeordnete App** aus.</span><span class="sxs-lookup"><span data-stu-id="01c91-126">Choose **Associated App**.</span></span> <span data-ttu-id="01c91-127">Wählen Sie dann auf dem Blatt **Zugeordnete App** die verwaltete App aus, auf die Sie die Konfiguration anwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="01c91-127">Then, on the **Associated App** blade, choose the managed app to which you want to apply the configuration.</span></span>
8.  <span data-ttu-id="01c91-128">Wählen Sie auf dem Blatt **Konfigurationsrichtlinie hinzufügen** die Option **Konfigurationseinstellungen** aus.</span><span class="sxs-lookup"><span data-stu-id="01c91-128">On the **Add Configuration Policy** blade, choose **Configuration settings**.</span></span>
9. <span data-ttu-id="01c91-129">Wählen Sie das **Format der Konfigurationseinstellungen** aus.</span><span class="sxs-lookup"><span data-stu-id="01c91-129">Select **Configuration settings format**.</span></span> <span data-ttu-id="01c91-130">Wählen Sie eine der folgenden Einstellungen aus:</span><span class="sxs-lookup"><span data-stu-id="01c91-130">Select one of the following:</span></span>
    - <span data-ttu-id="01c91-131">**[Verwenden des Konfigurations-Designers](#Use-the-configuration-designer)**</span><span class="sxs-lookup"><span data-stu-id="01c91-131">**[Use configuration designer](#Use-the-configuration-designer)**</span></span>
    - <span data-ttu-id="01c91-132">**[Eingeben von XML-Daten](#enter-xml-data)**</span><span class="sxs-lookup"><span data-stu-id="01c91-132">**[Enter XML data](#enter-xml-data)**</span></span>
10. <span data-ttu-id="01c91-133">Wählen Sie **OK** und dann **Hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="01c91-133">Choose **OK**, and then choose **Add**.</span></span>

## <a name="use-configuration-designer"></a><span data-ttu-id="01c91-134">Verwenden des Konfigurations-Designers</span><span class="sxs-lookup"><span data-stu-id="01c91-134">Use configuration designer</span></span>

<span data-ttu-id="01c91-135">Sie können den Konfigurations-Designer für Apps auf Geräten verwenden, die in Intune registriert sind oder nicht.</span><span class="sxs-lookup"><span data-stu-id="01c91-135">You can use the configuration designer for apps on devices that are enrolled or not enrolled in Intune.</span></span> <span data-ttu-id="01c91-136">Der Designer ermöglicht Ihnen das Konfigurieren bestimmter Konfigurationsschlüssel und -werte.</span><span class="sxs-lookup"><span data-stu-id="01c91-136">The designer lets you configure specific configuration keys and values.</span></span> <span data-ttu-id="01c91-137">Sie müssen ebenfalls den Datentyp für jeden Wert angeben.</span><span class="sxs-lookup"><span data-stu-id="01c91-137">You must also specify the data type for each value.</span></span> <span data-ttu-id="01c91-138">Die Einstellungen werden für Apps automatisch bei der Installation bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="01c91-138">Settings are supplied to apps automatically when they're installed.</span></span>

### <a name="add-a-setting"></a><span data-ttu-id="01c91-139">Hinzufügen einer Einstellung</span><span class="sxs-lookup"><span data-stu-id="01c91-139">Add a setting</span></span>

1. <span data-ttu-id="01c91-140">Legen Sie für jeden Schlüssel und jeden Wert in der Konfiguration Folgendes fest:</span><span class="sxs-lookup"><span data-stu-id="01c91-140">For each key and value in the configuration, set:</span></span>
   - <span data-ttu-id="01c91-141">**Konfigurationsschlüssel**</span><span class="sxs-lookup"><span data-stu-id="01c91-141">**Configuration key**</span></span><br>
     <span data-ttu-id="01c91-142">Der Schlüssel, der die bestimmte Einstellungskonfiguration eindeutig identifiziert.</span><span class="sxs-lookup"><span data-stu-id="01c91-142">The key that uniquely identifies the specific setting configuration.</span></span>
   - <span data-ttu-id="01c91-143">**Werttyp**</span><span class="sxs-lookup"><span data-stu-id="01c91-143">**Value type**</span></span><br>
     <span data-ttu-id="01c91-144">Der Datentyp des Konfigurationswerts.</span><span class="sxs-lookup"><span data-stu-id="01c91-144">The data type of the configuration value.</span></span> <span data-ttu-id="01c91-145">Zu den Typen gehören Integer, Real, String oder Boolean.</span><span class="sxs-lookup"><span data-stu-id="01c91-145">Types include Integer, Real, String, or Boolean.</span></span>
   - <span data-ttu-id="01c91-146">**Konfigurationswert**</span><span class="sxs-lookup"><span data-stu-id="01c91-146">**Configuration value**</span></span><br>
     <span data-ttu-id="01c91-147">Der Wert für die Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="01c91-147">The value for the configuration.</span></span>
2. <span data-ttu-id="01c91-148">Wählen Sie **OK** aus, um Ihre Konfigurationseinstellungen festzulegen.</span><span class="sxs-lookup"><span data-stu-id="01c91-148">Choose **OK** to set your configuration settings.</span></span>

### <a name="delete-a-setting"></a><span data-ttu-id="01c91-149">Löschen einer Einstellung</span><span class="sxs-lookup"><span data-stu-id="01c91-149">Delete a setting</span></span>

1. <span data-ttu-id="01c91-150">Wählen Sie die Auslassungspunkte (**...** ) neben der Einstellung aus.</span><span class="sxs-lookup"><span data-stu-id="01c91-150">Choose the ellipsis (**...**) next to the setting.</span></span>
2. <span data-ttu-id="01c91-151">Klicken Sie auf **Löschen**.</span><span class="sxs-lookup"><span data-stu-id="01c91-151">Select **Delete**.</span></span>

<span data-ttu-id="01c91-152">Die Zeichen \{\{ und \}\} werden nur von Tokentypen verwendet und dürfen nicht für andere Zwecke verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="01c91-152">The \{\{ and \}\} characters are used by token types only and must not be used for other purposes.</span></span>

## <a name="enter-xml-data"></a><span data-ttu-id="01c91-153">Eingeben von XML-Daten</span><span class="sxs-lookup"><span data-stu-id="01c91-153">Enter XML data</span></span>

<span data-ttu-id="01c91-154">Sie können eine XML-Eigenschaftenliste eingeben oder einfügen, die die App-Konfigurationseinstellungen für in Intune registrierte Geräte enthält.</span><span class="sxs-lookup"><span data-stu-id="01c91-154">You can type or paste an XML property list that contains the app configuration settings for devices enrolled in Intune.</span></span> <span data-ttu-id="01c91-155">Das Format der XML-Eigenschaftenliste variiert je nach der App, die Sie konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="01c91-155">The format of the XML property list varies depending on the app that you are configuring.</span></span> <span data-ttu-id="01c91-156">Wenden Sie sich an den Hersteller der App, um ausführliche Informationen über das genau zu verwendende Format zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="01c91-156">For details about the exact format to use, contact the supplier of the app.</span></span>

<span data-ttu-id="01c91-157">Intune überprüft das XML-Format.</span><span class="sxs-lookup"><span data-stu-id="01c91-157">Intune validates the XML format.</span></span> <span data-ttu-id="01c91-158">Intune überprüft jedoch nicht, ob die XML-Eigenschaftenliste (PList) mit der Ziel-App verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="01c91-158">However, Intune does not check that the XML property list (PList) will work with the target app.</span></span>

<span data-ttu-id="01c91-159">Weitere Informationen zu XML-Eigenschaftenlisten:</span><span class="sxs-lookup"><span data-stu-id="01c91-159">To learn more about XML property lists:</span></span>

  -  <span data-ttu-id="01c91-160">Lesen Sie [Konfigurieren von iOS-Apps mit Konfigurationsrichtlinien für mobile Apps in Microsoft Intune](/intune-classic/deploy-use/configure-ios-apps-with-mobile-app-configuration-policies-in-microsoft-intune).</span><span class="sxs-lookup"><span data-stu-id="01c91-160">Read [Configure iOS apps with mobile app configuration policies in Microsoft Intune](/intune-classic/deploy-use/configure-ios-apps-with-mobile-app-configuration-policies-in-microsoft-intune).</span></span>
  -  <span data-ttu-id="01c91-161">Lesen Sie unter [Understand XML Property Lists (Grundlegendes zu XML-Eigenschaftenlisten)](https://developer.apple.com/library/ios/documentation/Cocoa/Conceptual/PropertyLists/UnderstandXMLPlist/UnderstandXMLPlist.html) in der iOS-Entwicklerbibliothek nach.</span><span class="sxs-lookup"><span data-stu-id="01c91-161">Refer to [Understand XML Property Lists](https://developer.apple.com/library/ios/documentation/Cocoa/Conceptual/PropertyLists/UnderstandXMLPlist/UnderstandXMLPlist.html) in the iOS Developer Library.</span></span>

### <a name="example-format-for-an-app-configuration-xml-file"></a><span data-ttu-id="01c91-162">Beispielformat für eine App-Konfigurations-XML-Datei</span><span class="sxs-lookup"><span data-stu-id="01c91-162">Example format for an app configuration XML file</span></span>

<span data-ttu-id="01c91-163">Wenn Sie eine App-Konfigurationsdatei erstellen, können Sie die folgenden Werte in diesem Format angeben:</span><span class="sxs-lookup"><span data-stu-id="01c91-163">When you create an app configuration file, you can specify one or more of the following values by using this format:</span></span>

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
### <a name="supported-xml-plist-data-types"></a><span data-ttu-id="01c91-164">Unterstützte XML-PList-Datentypen</span><span class="sxs-lookup"><span data-stu-id="01c91-164">Supported XML PList data types</span></span>

<span data-ttu-id="01c91-165">Intune unterstützt die folgenden Datentypen in einer Eigenschaftenliste:</span><span class="sxs-lookup"><span data-stu-id="01c91-165">Intune supports the following data types in a property list:</span></span>

- <span data-ttu-id="01c91-166">&lt;integer&gt;</span><span class="sxs-lookup"><span data-stu-id="01c91-166">&lt;integer&gt;</span></span>
- <span data-ttu-id="01c91-167">&lt;real&gt;</span><span class="sxs-lookup"><span data-stu-id="01c91-167">&lt;real&gt;</span></span>
- <span data-ttu-id="01c91-168">&lt;string&gt;</span><span class="sxs-lookup"><span data-stu-id="01c91-168">&lt;string&gt;</span></span>
- <span data-ttu-id="01c91-169">&lt;array&gt;</span><span class="sxs-lookup"><span data-stu-id="01c91-169">&lt;array&gt;</span></span>
- <span data-ttu-id="01c91-170">&lt;dict&gt;</span><span class="sxs-lookup"><span data-stu-id="01c91-170">&lt;dict&gt;</span></span>
- <span data-ttu-id="01c91-171">&lt;true /&gt; oder &lt;false /&gt;</span><span class="sxs-lookup"><span data-stu-id="01c91-171">&lt;true /&gt; or &lt;false /&gt;</span></span>

### <a name="tokens-used-in-the-property-list"></a><span data-ttu-id="01c91-172">Tokens, die in der Eigenschaftenliste verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="01c91-172">Tokens used in the property list</span></span>

<span data-ttu-id="01c91-173">Darüber hinaus unterstützt Intune die folgenden Tokentypen in der Eigenschaftenliste:</span><span class="sxs-lookup"><span data-stu-id="01c91-173">Additionally, Intune supports the following token types in the property list:</span></span>
- <span data-ttu-id="01c91-174">\{\{userPrincipalName\}\}: z.B.**John@contoso.com**</span><span class="sxs-lookup"><span data-stu-id="01c91-174">\{\{userprincipalname\}\}—for example, **John@contoso.com**</span></span>
- <span data-ttu-id="01c91-175">\{\{Mail\}\}: z.B.**John@contoso.com**</span><span class="sxs-lookup"><span data-stu-id="01c91-175">\{\{mail\}\}—for example, **John@contoso.com**</span></span>
- <span data-ttu-id="01c91-176">\{\{partialupn\}\}: z.B. **John**</span><span class="sxs-lookup"><span data-stu-id="01c91-176">\{\{partialupn\}\}—for example, **John**</span></span>
- <span data-ttu-id="01c91-177">\{\{accountid\}\}: z.B. **fc0dc142-71d8-4b12-bbea-bae2a8514c81**</span><span class="sxs-lookup"><span data-stu-id="01c91-177">\{\{accountid\}\}—for example, **fc0dc142-71d8-4b12-bbea-bae2a8514c81**</span></span>
- <span data-ttu-id="01c91-178">\{\{deviceid\}\}: z.B. **b9841cd9-9843-405f-be28-b2265c59ef97**</span><span class="sxs-lookup"><span data-stu-id="01c91-178">\{\{deviceid\}\}—for example, **b9841cd9-9843-405f-be28-b2265c59ef97**</span></span>
- <span data-ttu-id="01c91-179">\{\{userid\}\}: z.B. **3ec2c00f-b125-4519-acf0-302ac3761822**</span><span class="sxs-lookup"><span data-stu-id="01c91-179">\{\{userid\}\}—for example, **3ec2c00f-b125-4519-acf0-302ac3761822**</span></span>
- <span data-ttu-id="01c91-180">\{\{username\}\}: z.B. **John Doe**</span><span class="sxs-lookup"><span data-stu-id="01c91-180">\{\{username\}\}—for example, **John Doe**</span></span>
- <span data-ttu-id="01c91-181">\{\{serialnumber\}\}: z.B. **F4KN99ZUG5V2** (für iOS-Geräte)</span><span class="sxs-lookup"><span data-stu-id="01c91-181">\{\{serialnumber\}\}—for example, **F4KN99ZUG5V2** (for iOS devices)</span></span>
- <span data-ttu-id="01c91-182">\{\{serialnumberlast4digits\}\}: z.B. **G5V2** (für iOS-Geräte)</span><span class="sxs-lookup"><span data-stu-id="01c91-182">\{\{serialnumberlast4digits\}\}—for example, **G5V2** (for iOS devices)</span></span>

## <a name="next-steps"></a><span data-ttu-id="01c91-183">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="01c91-183">Next steps</span></span>

<span data-ttu-id="01c91-184">Fahren Sie wie gewöhnlich mit dem [Zuweisen](apps-deploy.md) und [Überwachen](apps-monitor.md) der App fort.</span><span class="sxs-lookup"><span data-stu-id="01c91-184">Continue to [assign](apps-deploy.md) and [monitor](apps-monitor.md) the app as usual.</span></span>