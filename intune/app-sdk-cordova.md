---
title: Microsoft Intune App SDK-Cordova-Plug-In
description: 
keywords: sdk, Cordova, intune
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 10/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: bb940cb9-d43f-45ca-b065-ac0adc61dc6f
ms.reviewer: oydang
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: fd4cedd20f427966dc3cfb7c2748f57b4d0746ab
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2017
---
# <a name="microsoft-intune-app-sdk-cordova-plugin"></a><span data-ttu-id="e2a6f-103">Microsoft Intune App SDK-Cordova-Plug-In</span><span class="sxs-lookup"><span data-stu-id="e2a6f-103">Microsoft Intune App SDK Cordova Plugin</span></span>

> [!NOTE]
> <span data-ttu-id="e2a6f-104">Lesen Sie am besten zuerst den Leitfaden [Erste Schritte mit dem Microsoft Intune App SDK](app-sdk-get-started.md). Dort finden Sie Informationen zu den Vorbereitungen, die Sie auf den verschiedenen unterstützten Plattformen für die Integration treffen müssen.</span><span class="sxs-lookup"><span data-stu-id="e2a6f-104">You may wish to first read the [Get Started with Intune App SDK](app-sdk-get-started.md) article, which explains how to prepare for integration on each supported platform.</span></span>

## <a name="overview"></a><span data-ttu-id="e2a6f-105">Übersicht</span><span class="sxs-lookup"><span data-stu-id="e2a6f-105">Overview</span></span>

<span data-ttu-id="e2a6f-106">Das [Intune App SDK-Cordova-Plug-In](/intune-classic/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune) in iOS- und Android-Apps, erstellt mit Cordova.</span><span class="sxs-lookup"><span data-stu-id="e2a6f-106">The [Intune App SDK Cordova Plugin](/intune-classic/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune) in iOS and Android apps built with Cordova.</span></span> <span data-ttu-id="e2a6f-107">Das Plug-In ermöglicht es Entwicklern, Funktionen der Intune-App und Datenschutzfunktionen in die Cordova-basierte App zu integrieren.</span><span class="sxs-lookup"><span data-stu-id="e2a6f-107">The plugin allows developers to integrate Intune app and data protection features into their Cordova-based app.</span></span>

<span data-ttu-id="e2a6f-108">Sie werden feststellen, dass Sie die meisten SDK-Funktionen aktivieren können, ohne das Verhalten Ihrer App zu ändern.</span><span class="sxs-lookup"><span data-stu-id="e2a6f-108">You will find that you can enable SDK features without changing your app's behavior.</span></span> <span data-ttu-id="e2a6f-109">Nachdem Sie das Plug-In in Ihrer iOS- oder Android-App erstellt haben, kann der Microsoft Intune-Administrator die Intune-App-Schutzrichtlinie bereitstellen, die aus einer Vielzahl von Datenschutzfeatures besteht.</span><span class="sxs-lookup"><span data-stu-id="e2a6f-109">Once you have built the plugin into your iOS or Android app, the Microsoft Intune administrator will be able to deploy Intune app protection policy, which consists of a variety of data protection features.</span></span> <span data-ttu-id="e2a6f-110">Das Plug-In ist so programmiert, dass die meisten Schritte automatisch beim Cordova-Buildprozess ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="e2a6f-110">The plugin is built so that most of the steps are automatically performed in the Cordova build process.</span></span> <span data-ttu-id="e2a6f-111">Dadurch sollten Sie Ihre App schnell für die Intune-App-Schutzrichtlinie aktivieren können.</span><span class="sxs-lookup"><span data-stu-id="e2a6f-111">As a result, you should be able to get your app enabled for Intune app protection quickly.</span></span> <span data-ttu-id="e2a6f-112">Um zu beginnen, befolgen Sie die nachstehenden Anweisungen basierend auf Ihrer Zielplattform.</span><span class="sxs-lookup"><span data-stu-id="e2a6f-112">To get started, follow the steps below based on your target platform.</span></span>

## <a name="supported-platforms"></a><span data-ttu-id="e2a6f-113">Unterstützte Plattformen</span><span class="sxs-lookup"><span data-stu-id="e2a6f-113">Supported Platforms</span></span>

* <span data-ttu-id="e2a6f-114">Das Plug-In funktioniert unter den Betriebssystemen Windows, Mac und Linux.</span><span class="sxs-lookup"><span data-stu-id="e2a6f-114">The plugin works on Windows, Mac and Linux OS</span></span>
* <span data-ttu-id="e2a6f-115">Das Plug-In funktioniert für Android-Apps mit `minSdkVersion` >= 14 und `targetSdkVersion` <= 24.</span><span class="sxs-lookup"><span data-stu-id="e2a6f-115">The plugin works for Android apps with `minSdkVersion` >= 14 and `targetSdkVersion` <= 24</span></span>
* <span data-ttu-id="e2a6f-116">Das Plug-In funktioniert für iOS-Apps, die für iOS 9.0 und höher vorgesehen sind.</span><span class="sxs-lookup"><span data-stu-id="e2a6f-116">The plugin works for iOS apps targeted for iOS 9.0 and above.</span></span>

## <a name="intune-mobile-application-management-scenarios"></a><span data-ttu-id="e2a6f-117">Intune MAM-Szenarien</span><span class="sxs-lookup"><span data-stu-id="e2a6f-117">Intune Mobile Application Management scenarios</span></span>

* <span data-ttu-id="e2a6f-118">Mit Intune MDM registrierte Geräte</span><span class="sxs-lookup"><span data-stu-id="e2a6f-118">Intune MDM-enrolled devices</span></span>
* <span data-ttu-id="e2a6f-119">Mit EMM registrierte Geräte von Drittanbietern</span><span class="sxs-lookup"><span data-stu-id="e2a6f-119">Third-party EMM-enrolled devices</span></span>
* <span data-ttu-id="e2a6f-120">Nicht verwaltete (bei keiner MDM-Lösung registrierte) Geräte</span><span class="sxs-lookup"><span data-stu-id="e2a6f-120">Unmanaged devices (not enrolled with any MDM)</span></span>

<span data-ttu-id="e2a6f-121">Cordova-Apps, die mit dem Intune App SDK Cordova Plug-In erstellt wurden, können jetzt sowohl auf registrierten als auch auf nicht registrierten Geräten mit mobiler Intune-Geräteverwaltung (Mobile Device Management, MDM) Intune-App-Schutzrichtlinien empfangen.</span><span class="sxs-lookup"><span data-stu-id="e2a6f-121">Cordova apps built with the Intune App SDK Cordova Plugin can now receive Intune app protection policies on both Intune mobile device management (MDM) enrolled devices and unenrolled devices.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="e2a6f-122">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="e2a6f-122">Prerequisites</span></span>

### <a name="android"></a><span data-ttu-id="e2a6f-123">Android</span><span class="sxs-lookup"><span data-stu-id="e2a6f-123">Android</span></span>

* <span data-ttu-id="e2a6f-124">Es muss immer die aktuelle Microsoft Intune-Unternehmensportal-App auf dem Gerät installiert sein.</span><span class="sxs-lookup"><span data-stu-id="e2a6f-124">The latest Microsoft Intune Company Portal app must always be installed on the device.</span></span>
* <span data-ttu-id="e2a6f-125">Wenn Sie bei Verwendung des Plug-Ins den Cordova-Build ausführen, ist mindestens Java 7 erforderlich.</span><span class="sxs-lookup"><span data-stu-id="e2a6f-125">Java 7 at minimum must be on the path where you will execute Cordova build when using the plugin.</span></span>

### <a name="ios"></a><span data-ttu-id="e2a6f-126">iOS</span><span class="sxs-lookup"><span data-stu-id="e2a6f-126">iOS</span></span>

* <span data-ttu-id="e2a6f-127">Für MDM-Features muss die aktuelle Microsoft Intune-Unternehmensportal-App auf dem Gerät installiert sein.</span><span class="sxs-lookup"><span data-stu-id="e2a6f-127">The latest Microsoft Intune Company Portal app must be installed on the device for MDM features.</span></span> <span data-ttu-id="e2a6f-128">Sie ist *nicht* für die Intune-App-Schutzrichtlinie ohne Geräteregistrierungsfeatures erforderlich.</span><span class="sxs-lookup"><span data-stu-id="e2a6f-128">It is *not* needed for Intune app protection policy without device enrollment features.</span></span>

### <a name="both-platforms"></a><span data-ttu-id="e2a6f-129">Beide Plattformen</span><span class="sxs-lookup"><span data-stu-id="e2a6f-129">Both platforms</span></span>

* <span data-ttu-id="e2a6f-130">Es wird Version 0.8.0+ des [Azure Active Directory Authentifizierungsbibliothek Plug-Ins (ADAL) für Cordova](https://github.com/AzureAD/azure-activedirectory-library-for-cordova) benötigt.</span><span class="sxs-lookup"><span data-stu-id="e2a6f-130">Version 0.8.0+ of the [Azure Active Directory Authentication Libraries (ADAL) plugin for Cordova](https://github.com/AzureAD/azure-activedirectory-library-for-cordova) is required.</span></span>

> [!NOTE]
> <span data-ttu-id="e2a6f-131">Aufgrund eines Apache Cordova-Bugs führen die [hier](https://issues.apache.org/jira/browse/CB-6227?jql=text%20~%20%22plugin%20dependency%22) aufgelisteten Apps, die schon über die Plug-In-Abhängigkeit verfügen, das Upgrade auf die benötigte Version nicht automatisch aus.</span><span class="sxs-lookup"><span data-stu-id="e2a6f-131">Due to an Apache Cordova bug the filed [here](https://issues.apache.org/jira/browse/CB-6227?jql=text%20~%20%22plugin%20dependency%22), apps that already have the plugin dependency will not automatically upgrade the plugin to the requested version.</span></span>



## <a name="quick-start"></a><span data-ttu-id="e2a6f-132">Schnellstart</span><span class="sxs-lookup"><span data-stu-id="e2a6f-132">Quick start</span></span>

1. <span data-ttu-id="e2a6f-133">Updaten Sie Ihre ADAL-Version:</span><span class="sxs-lookup"><span data-stu-id="e2a6f-133">Update your version of ADAL:</span></span>

  ```shell
  cordova plugin remove cordova-plugin-ms-adal
  cordova plugin add cordova-plugin-ms-adal@0.8.x
  ```

2. <span data-ttu-id="e2a6f-134">Fügen Sie das Intune App SDK für Cordova-Plug-In hinzu:</span><span class="sxs-lookup"><span data-stu-id="e2a6f-134">Add the Intune App SDK for Cordova plugin:</span></span>

  ```shell
  cordova plugin add cordova-plugin-ms-intune-mam
  ```

## <a name="build-the-plugin-into-your-ios-app"></a><span data-ttu-id="e2a6f-135">Erstellen des Plug-Ins in Ihrer iOS-App</span><span class="sxs-lookup"><span data-stu-id="e2a6f-135">Build the plugin into your iOS app</span></span>

<span data-ttu-id="e2a6f-136">Sie müssen einige Schritte abschließen, um Ihre App für die Intune-App-Schutzrichtlinie zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="e2a6f-136">You'll need to complete some steps for your app to be enabled for Intune app protection policy.</span></span> <span data-ttu-id="e2a6f-137">Der Einfachheit halber werden diese Schritte im Cordova-Buildprozess als Prebuild-Hook automatisch ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="e2a6f-137">For convenience, these steps are performed automatically in the Cordova build process as a pre-build hook.</span></span> <span data-ttu-id="e2a6f-138">Dadurch werden die automatisierten Schritte Ihre `*.pbxproj`- , `*-Info.plist`-, und `*.entitlements`-Dateien ändern, die einer Projektkonfiguration zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="e2a6f-138">As a result, the automated steps will modify your `*.pbxproj` , `*-Info.plist`, and `*.entitlements` files that are associated with a project configuration.</span></span> <span data-ttu-id="e2a6f-139">Wenn das Projekt keine Berechtigungsdatei enthält, wird das Plug-In automatisch eine erstellen.</span><span class="sxs-lookup"><span data-stu-id="e2a6f-139">If your project doesn't contain an entitlements file, the plugin will create one automatically.</span></span>

<span data-ttu-id="e2a6f-140">Dieses Setup unterstützt nur ein einziges Ziel. Wenn es mehrere Ziele gibt, führt es die Konfiguration auf dem Ziel aus, das als erstes gefunden wird.</span><span class="sxs-lookup"><span data-stu-id="e2a6f-140">This setup only supports a single target and will perform the configuration on the first target found if there are multiple targets.</span></span> <span data-ttu-id="e2a6f-141">Wenn der Prozess fehlschlägt, überprüfen Sie, dass:</span><span class="sxs-lookup"><span data-stu-id="e2a6f-141">If the process fails, check that:</span></span>

1. <span data-ttu-id="e2a6f-142">Das Xcode-Projekt Ihrer App `[name].xcodeproj` ist, wobei `[name]` der Wert wie definiert in `config.xml` ist.</span><span class="sxs-lookup"><span data-stu-id="e2a6f-142">Your app's Xcode project is `[name].xcodeproj` where `[name]` is the value defined in `config.xml`</span></span>
2. <span data-ttu-id="e2a6f-143">Ihr Projekt verwendet die [Standardverzeichnisstruktur der Cordova-App](https://cordova.apache.org/docs/en/latest/reference/cordova-cli/index.html#directory-structure).</span><span class="sxs-lookup"><span data-stu-id="e2a6f-143">Your project uses the [standard Cordova app directory structure](https://cordova.apache.org/docs/en/latest/reference/cordova-cli/index.html#directory-structure).</span></span>

## <a name="build-the-plugin-into-your-android-app"></a><span data-ttu-id="e2a6f-144">Erstellen des Plug-Ins in Ihrer Android-App</span><span class="sxs-lookup"><span data-stu-id="e2a6f-144">Build the plugin into your Android app</span></span>

1. <span data-ttu-id="e2a6f-145">Importieren Sie dieses Plug-In mit den aktuellsten Cordova-Tools.</span><span class="sxs-lookup"><span data-stu-id="e2a6f-145">Import this plugin with the latest Cordova tools.</span></span> <span data-ttu-id="e2a6f-146">Das Plug-In wird automatisch als ein `after_compile`-Schritt aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="e2a6f-146">The plugin will be automatically invoked as an `after_compile` step.</span></span>

2. <span data-ttu-id="e2a6f-147">Das Plug-In erstellt am Ende des Buildprozesses eine Intune-fähige Version einer erstellten APK-Datei (Android API 14+).</span><span class="sxs-lookup"><span data-stu-id="e2a6f-147">The plugin will create a Intune-enabled version of a built apk (Android API 14+) at the end of the build process.</span></span> <span data-ttu-id="e2a6f-148">Das Buildausgabe wird eine `[Project]-intunewrapped-[Build_Configuration].apk` (z.B. `helloWorld-intunewrapped-debug.apk`) enthalten.</span><span class="sxs-lookup"><span data-stu-id="e2a6f-148">The build output will contain a `[Project]-intunewrapped-[Build_Configuration].apk` (e.g. `helloWorld-intunewrapped-debug.apk`).</span></span>

> [!NOTE]
> <span data-ttu-id="e2a6f-149">Das Plug-In unterstützt nur Gradle-Builds.</span><span class="sxs-lookup"><span data-stu-id="e2a6f-149">The plugin only supports gradle builds.</span></span>

<span data-ttu-id="e2a6f-150">Aufgrund eines Cordova-Fehlers, der [hier](https://issues.apache.org/jira/browse/CB-9434) aufgeführt ist, und verursacht, dass bestimmte Cordova-Hooks in `cordova run` ignoriert werden, müssen Sie Folgendes tun, um die umschlossene App aus der Befehlszeile auszuführen:</span><span class="sxs-lookup"><span data-stu-id="e2a6f-150">Due to a Cordova bug filed [here](https://issues.apache.org/jira/browse/CB-9434) that causes certain Cordova hooks to be ignored on `cordova run`, to run the wrapped app from the command line, you must do the following:</span></span>

```shell
$ cordova build
$ cordova run --nobuild
```

## <a name="sign-your-android-app"></a><span data-ttu-id="e2a6f-151">Signieren Ihrer Android-App</span><span class="sxs-lookup"><span data-stu-id="e2a6f-151">Sign your Android app</span></span>

<span data-ttu-id="e2a6f-152">Das Plug-In erkennt automatisch Signierungsinformationen, die Sie an folgenden Speicherorten für Cordova angegeben haben:</span><span class="sxs-lookup"><span data-stu-id="e2a6f-152">The plugin automatically recognizes signing information you have provided to Cordova at the following locations:</span></span>

* <span data-ttu-id="e2a6f-153">platforms/android/debug-signing.properties</span><span class="sxs-lookup"><span data-stu-id="e2a6f-153">platforms/android/debug-signing.properties</span></span>
* <span data-ttu-id="e2a6f-154">platforms/android/release-signing.properties</span><span class="sxs-lookup"><span data-stu-id="e2a6f-154">platforms/android/release-signing.properties</span></span>
* <span data-ttu-id="e2a6f-155">res/native/android/ant.properties</span><span class="sxs-lookup"><span data-stu-id="e2a6f-155">res/native/android/ant.properties</span></span>

<span data-ttu-id="e2a6f-156">Lesen Sie die [Cordova-Gradle-Signierungsinformationen](https://cordova.apache.org/docs/en/latest/guide/platforms/android/#using-gradle), um mehr über das erwartete Format zu erfahren.</span><span class="sxs-lookup"><span data-stu-id="e2a6f-156">See [the Cordova gradle signing information](https://cordova.apache.org/docs/en/latest/guide/platforms/android/#using-gradle) for more information about the expected format.</span></span>

<span data-ttu-id="e2a6f-157">Wir unterstützen derzeit nicht die Möglichkeit, Signierungsinformationen in `build.json` oder an beliebigen Speicherorten bereitzustellen, die dem Cordova-Build über Parameter bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="e2a6f-157">We currently don't support the ability to provide signing information in `build.json` or arbitrary locations provided via parameters to Cordova build.</span></span>

## <a name="debugging-from-visual-studio"></a><span data-ttu-id="e2a6f-158">Debugging aus Visual Studio</span><span class="sxs-lookup"><span data-stu-id="e2a6f-158">Debugging from Visual Studio</span></span>

<span data-ttu-id="e2a6f-159">Nachdem die App zum ersten Mal gestartet wurde, sollten Sie ein Dialogfeld sehen, das Sie darüber informiert, dass die App von Intune verwaltet wird.</span><span class="sxs-lookup"><span data-stu-id="e2a6f-159">After launching the app for the first time you should see a dialog notifying you that the app is managed by Intune.</span></span> <span data-ttu-id="e2a6f-160">Klicken Sie auf „Nicht mehr anzeigen“. Klicken Sie dann in VS noch einmal auf die Schaltfläche Debuggen/Ausführen, damit Haltepunkte erreicht werden.</span><span class="sxs-lookup"><span data-stu-id="e2a6f-160">Hit "Don't show again" and click the debug/run button again from VS for breakpoints to be hit.</span></span>

## <a name="known-limitations"></a><span data-ttu-id="e2a6f-161">Bekannte Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="e2a6f-161">Known Limitations</span></span>

### <a name="android"></a><span data-ttu-id="e2a6f-162">Android</span><span class="sxs-lookup"><span data-stu-id="e2a6f-162">Android</span></span>

* <span data-ttu-id="e2a6f-163">Die MultiDex Unterstützung ist unvollständig.</span><span class="sxs-lookup"><span data-stu-id="e2a6f-163">MultiDex support is incomplete.</span></span>
* <span data-ttu-id="e2a6f-164">Die App muss `minSdkVersion` von 14 und `targetSdkVersion` von 24 oder niedriger haben.</span><span class="sxs-lookup"><span data-stu-id="e2a6f-164">App must have `minSdkVersion` of 14 and `targetSdkVersion` of 24 or below.</span></span> <span data-ttu-id="e2a6f-165">Wir unterstützen derzeit keine Apps für API 25.</span><span class="sxs-lookup"><span data-stu-id="e2a6f-165">We currently don't support apps targeting API 25</span></span>
* <span data-ttu-id="e2a6f-166">Wir können keine Apps erneut signieren, die mit dem V2-Signaturschema signiert wurden.</span><span class="sxs-lookup"><span data-stu-id="e2a6f-166">We cannot re-sign apps that were signed with the V2 Signature Scheme.</span></span> <span data-ttu-id="e2a6f-167">Wenn V2-signierte Apps von dem Plug-In umschlossen werden, ist die umschlossene Ausgabe-APK unsigniert.</span><span class="sxs-lookup"><span data-stu-id="e2a6f-167">When V2-signed apps are wrapped by the plugin, the wrapped output .apk will be unsigned.</span></span>
*
  * <span data-ttu-id="e2a6f-168">Sie können die Cordova-Standard-V2-Signierung deaktivieren, indem Sie Ihrer `build-extras.gradle`-Datei Folgendes hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="e2a6f-168">You can disable Cordova's default V2 Signing by adding the following to your `build-extras.gradle` file:</span></span>

  ```gradle
  android {
      signingConfigs {
          release {
              v2SigningEnabled false
          }
          debug {
              v2SigningEnabled false
          }
      }
      buildTypes {
          release {
              signingConfig signingConfigs.release
          }
          debug {
              signingConfig signingConfigs.debug
          }
      }
  }
  ```

### <a name="ios"></a><span data-ttu-id="e2a6f-169">iOS</span><span class="sxs-lookup"><span data-stu-id="e2a6f-169">iOS</span></span>

* <span data-ttu-id="e2a6f-170">Wenn Sie die Liste der UTIs unter dem Knoten **CFBundleDocumentTypes** der **Info.plist**-Datei verändern, müssen Sie die Intune-UTIs im Bereich „Importierte-UTIs“ der gleichen PLIST-Datei löschen (Knoten **UTImportedTypeDeclarations**), bevor Sie mit der erneuten Erstellung fortfahren.</span><span class="sxs-lookup"><span data-stu-id="e2a6f-170">Whenever you modify the list of UTI's under the **CFBundleDocumentTypes** node of the **Info.plist** file, you must clear the Intune UTI's in the Imported UTI's section of the same plist file (**UTImportedTypeDeclarations** node) before building again.</span></span> <span data-ttu-id="e2a6f-171">Alle Intune-UTIs beginnen mit dem Präfix `com.microsoft.intune.mam`.</span><span class="sxs-lookup"><span data-stu-id="e2a6f-171">All of the Intune UTI's will start with the prefix `com.microsoft.intune.mam`.</span></span>

* <span data-ttu-id="e2a6f-172">Wenn Sie das Intune App SDK für Cordova-Plug-In aus Ihrem Cordova-Projekt entfernen möchten, müssen Sie auch die iOS-Plattform entfernen und sie erneut hinzufügen, um einige der Intune-Konfigurationen in den XCODEPROJ- und PLIST-Dateien rückgängig zu machen.</span><span class="sxs-lookup"><span data-stu-id="e2a6f-172">If you want to remove the Intune App SDK for Cordova plugin from your Cordova project, you must also remove the iOS platform and re-add it, in order to undo some of the Intune configuration in the .xcodeproj and .plist files.</span></span>
