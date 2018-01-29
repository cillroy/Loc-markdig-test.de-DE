---
title: Intune App SDK-Xamarin-Komponente
description: 
keywords: sdk, Xamarin, intune
author: erikre
manager: angrobe
ms.author: erikre
ms.date: 11/01/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 275d574b-3560-4992-877c-c6aa480717f4
ms.reviewer: aanavath
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 8ffb12c64a4aa54aff7028229bb40143173af6ca
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2018
---
# <a name="microsoft-intune-app-sdk-xamarin-component"></a><span data-ttu-id="83a00-103">Intune App SDK-Xamarin-Komponente</span><span class="sxs-lookup"><span data-stu-id="83a00-103">Microsoft Intune App SDK Xamarin Component</span></span>

> [!NOTE]
> <span data-ttu-id="83a00-104">Lesen Sie am besten zuerst den Leitfaden [Erste Schritte mit dem Microsoft Intune App SDK](app-sdk-get-started.md). Dort finden Sie Informationen zu den Vorbereitungen, die Sie auf den verschiedenen unterstützten Plattformen für die Integration treffen müssen.</span><span class="sxs-lookup"><span data-stu-id="83a00-104">You may wish to first read the [Get Started with Intune App SDK](app-sdk-get-started.md) article, which explains how to prepare for integration on each supported platform.</span></span>



## <a name="overview"></a><span data-ttu-id="83a00-105">Übersicht</span><span class="sxs-lookup"><span data-stu-id="83a00-105">Overview</span></span>
<span data-ttu-id="83a00-106">Mit der [Intune App SDK-Xamarin-Komponente](https://components.xamarin.com/view/microsoft.intune.mam) können Sie die [Intune-App-Schutzrichtlinie](/intune-classic/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune) in Ihren mit Xamarin erstellten iOS- und Android-Apps aktivieren.</span><span class="sxs-lookup"><span data-stu-id="83a00-106">The [Intune App SDK Xamarin component](https://components.xamarin.com/view/microsoft.intune.mam) enables [Intune app protection policy](/intune-classic/deploy-use/protect-app-data-using-mobile-app-management-policies-with-microsoft-intune) in iOS and Android apps built with Xamarin.</span></span> <span data-ttu-id="83a00-107">Die Komponente erlaubt Entwicklern, App-Schutzfunktionen von Intune auf einfache Weise in ihre Xamarin-basierten App zu integrieren.</span><span class="sxs-lookup"><span data-stu-id="83a00-107">The component allows developers to easily build in Intune app protection features into their Xamarin-based app.</span></span>

> [!NOTE]
> <span data-ttu-id="83a00-108">Die Unterstützung für das Intune SDK für Xamarin ist derzeit in der Vorschauversion verfügbar.</span><span class="sxs-lookup"><span data-stu-id="83a00-108">Support for the Intune SDK for Xamarin is currently available in preview.</span></span> 

<span data-ttu-id="83a00-109">Mit der Microsoft Intune App SDK Xamarin-Komponente können Sie die Intune-App-Schutzrichtlinien (auch als APP- oder MAM-Richtlinien bezeichnet) in Ihre mit Xamarin entwickelten Apps integrieren.</span><span class="sxs-lookup"><span data-stu-id="83a00-109">The Microsoft Intune App SDK Xamarin Component lets you incorporate Intune app protection policies (also known as APP or MAM policies) into your apps developed with Xamarin.</span></span> <span data-ttu-id="83a00-110">MAM-fähige Anwendungen sind in das Intune App SDK integrierte Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="83a00-110">A MAM-enabled application is one that is integrated with the Intune App SDK.</span></span> <span data-ttu-id="83a00-111">Sie ermöglichen IT-Administratoren, App-Schutzrichtlinien für Ihre mobile App bereitzustellen, wenn diese aktiv von Intune verwaltet wird.</span><span class="sxs-lookup"><span data-stu-id="83a00-111">IT administrators can deploy app protection policies to your mobile app when Intune actively manages the app.</span></span>

## <a name="whats-supported"></a><span data-ttu-id="83a00-112">Was wird unterstützt?</span><span class="sxs-lookup"><span data-stu-id="83a00-112">What's supported?</span></span>

### <a name="developer-machines"></a><span data-ttu-id="83a00-113">Entwicklercomputer</span><span class="sxs-lookup"><span data-stu-id="83a00-113">Developer machines</span></span>
* <span data-ttu-id="83a00-114">macOS</span><span class="sxs-lookup"><span data-stu-id="83a00-114">macOS</span></span>


### <a name="mobile-app-platforms"></a><span data-ttu-id="83a00-115">Mobile App-Plattformen</span><span class="sxs-lookup"><span data-stu-id="83a00-115">Mobile app platforms</span></span>
* <span data-ttu-id="83a00-116">Android</span><span class="sxs-lookup"><span data-stu-id="83a00-116">Android</span></span>
* <span data-ttu-id="83a00-117">iOS</span><span class="sxs-lookup"><span data-stu-id="83a00-117">iOS</span></span>


### <a name="intune-mobile-application-management-scenarios"></a><span data-ttu-id="83a00-118">Intune MAM-Szenarien</span><span class="sxs-lookup"><span data-stu-id="83a00-118">Intune Mobile Application Management scenarios</span></span>

* <span data-ttu-id="83a00-119">Mit Intune MDM registrierte Geräte</span><span class="sxs-lookup"><span data-stu-id="83a00-119">Intune MDM-enrolled devices</span></span>
* <span data-ttu-id="83a00-120">Mit EMM registrierte Geräte von Drittanbietern</span><span class="sxs-lookup"><span data-stu-id="83a00-120">Third-party EMM-enrolled devices</span></span>
* <span data-ttu-id="83a00-121">Nicht verwaltete (bei keiner MDM-Lösung registrierte) Geräte</span><span class="sxs-lookup"><span data-stu-id="83a00-121">Unmanaged devices (not enrolled with any MDM)</span></span>

<span data-ttu-id="83a00-122">Xamarin-Apps, die mit der Intune App SDK Xamarin-Komponente erstellt wurden, können jetzt sowohl auf registrierten als auch auf nicht registrierten Geräten mit mobiler Intune-Geräteverwaltung (Mobile Device Management, MDM) Intune-App-Schutzrichtlinien empfangen.</span><span class="sxs-lookup"><span data-stu-id="83a00-122">Xamarin apps built with the Intune App SDK Xamarin Component can now receive Intune app protection policies on both Intune mobile device management (MDM) enrolled devices and unenrolled devices.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="83a00-123">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="83a00-123">Prerequisites</span></span>

* <span data-ttu-id="83a00-124">**[Nur Android]** Die aktuelle Microsoft Intune-Unternehmensportal-App muss auf dem Gerät installiert sein.</span><span class="sxs-lookup"><span data-stu-id="83a00-124">**[Android only]** The latest Microsoft Intune Company Portal app must be installed on the device.</span></span>

## <a name="get-started"></a><span data-ttu-id="83a00-125">Erste Schritte</span><span class="sxs-lookup"><span data-stu-id="83a00-125">Get started</span></span>

1.  <span data-ttu-id="83a00-126">Laden Sie [hier](https://components.xamarin.com/submit/xpkg) die **Xamarin-component.exe** herunter, und extrahieren Sie diese.</span><span class="sxs-lookup"><span data-stu-id="83a00-126">Download **Xamarin-component.exe** from [here](https://components.xamarin.com/submit/xpkg) and extract it.</span></span>

2. <span data-ttu-id="83a00-127">Lesen Sie die [Lizenzbedingungen](https://components.xamarin.com/license/microsoft.intune.mam) für die Microsoft Intune MAM-Xamarin-Komponente.</span><span class="sxs-lookup"><span data-stu-id="83a00-127">Read the [license terms](https://components.xamarin.com/license/microsoft.intune.mam) for the Microsoft Intune MAM Xamarin Component.</span></span>

3.  <span data-ttu-id="83a00-128">Laden Sie den Intune App SDK-Xamarin-Komponentenordner aus [GitHub](https://github.com/msintuneappsdk/intune-app-sdk-xamarin) oder [Xamarin](https://components.xamarin.com/license/microsoft.intune.mam) herunter, und extrahieren Sie diesen.</span><span class="sxs-lookup"><span data-stu-id="83a00-128">Download the Intune App SDK Xamarin Component folder from [GitHub](https://github.com/msintuneappsdk/intune-app-sdk-xamarin) or [Xamarin](https://components.xamarin.com/license/microsoft.intune.mam) and extract it.</span></span> <span data-ttu-id="83a00-129">Die beiden in Schritt 1 und Schritt 3 heruntergeladenen Dateien müssen sich auf derselben Verzeichnisebene befinden.</span><span class="sxs-lookup"><span data-stu-id="83a00-129">Both files downloaded from step 1 and step 3 should be in the same directory level.</span></span>

4.  <span data-ttu-id="83a00-130">Führen Sie `Xamarin.Component.exe install <.xam> file` in der Befehlszeile als Administrator aus.</span><span class="sxs-lookup"><span data-stu-id="83a00-130">In the command line as an administrator, run `Xamarin.Component.exe install <.xam> file`.</span></span>

5.  <span data-ttu-id="83a00-131">Klicken Sie in Visual Studio mit der rechten Maustaste in Ihrem zuvor erstellten Xamarin-Projekt auf **Komponenten**.</span><span class="sxs-lookup"><span data-stu-id="83a00-131">In Visual Studio, right-click **components** in your previously created Xamarin project.</span></span>

6.  <span data-ttu-id="83a00-132">Wählen Sie **Komponenten bearbeiten** aus, und fügen Sie die Intune App SDK-Komponente hinzu, die Sie lokal auf Ihren Computer heruntergeladen haben.</span><span class="sxs-lookup"><span data-stu-id="83a00-132">Select **Edit Components** and add the Intune App SDK component you’ve downloaded locally to your computer.</span></span>



## <a name="enabling-intune-app-protection-polices-in-your-ios-mobile-app"></a><span data-ttu-id="83a00-133">Aktivieren der Intune-App-Schutzrichtlinien in Ihrer mobilen iOS-App</span><span class="sxs-lookup"><span data-stu-id="83a00-133">Enabling Intune app protection polices in your iOS mobile app</span></span>
1.  <span data-ttu-id="83a00-134">Um das Intune App SDK zu starten, müssen Sie eine beliebige API der `AppDelegate.cs`-Klasse aufrufen.</span><span class="sxs-lookup"><span data-stu-id="83a00-134">In order to initialize the Intune App SDK, you need to make a call for any API in the `AppDelegate.cs` class.</span></span> <span data-ttu-id="83a00-135">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="83a00-135">For example:</span></span>

      ```csharp
      public override bool FinishedLaunching (UIApplication application, NSDictionary launchOptions)
      {
            Console.WriteLine ("Is Managed: {0}", IntuneMAMPolicyManager.Instance.PrimaryUser != null);
            return true;
      }

      ```

2.  <span data-ttu-id="83a00-136">Nachdem die Komponente hinzugefügt und gestartet wurde, können die allgemeinen Schritte ausgeführt werden, die zum Einrichten der App-SDK in der mobilen iOS-Anwendung notwendig sind.</span><span class="sxs-lookup"><span data-stu-id="83a00-136">Now that the component is added and initialized, you can follow the general steps required for building the App SDK into an iOS mobile app.</span></span> <span data-ttu-id="83a00-137">Die kompletten Unterlagen zur Aktivierung nativer iOS-Apps finden Sie unter [Microsoft Intune App SDK für iOS – Entwicklerhandbuch](app-sdk-ios.md).</span><span class="sxs-lookup"><span data-stu-id="83a00-137">You can find the full documentation for enabling native iOS apps in the [Intune App SDK for iOS Developer Guide](app-sdk-ios.md).</span></span>
3. <span data-ttu-id="83a00-138">**Wichtig**: Es gibt verschiedene Modifikationen, die spezifisch für Xamarin-basierte iOS-Apps sind.</span><span class="sxs-lookup"><span data-stu-id="83a00-138">**Important**: There are several modifications specific to Xamarin-based iOS apps.</span></span> <span data-ttu-id="83a00-139">Wenn beispielsweise Schlüsselbundgruppen aktiviert werden, muss Folgendes hinzugefügt werden, um die Xamarin-Beispiel-App zu integrieren, die von uns in die Komponente integriert wurde.</span><span class="sxs-lookup"><span data-stu-id="83a00-139">For instance, when enabling keychain groups, you need to add the following to include the Xamarin sample app we included in the component.</span></span> <span data-ttu-id="83a00-140">Nachstehend finden Sie das Beispiel einer Gruppe, die Sie in Ihren Schlüsselbund-Zugriffsgruppen benötigen:</span><span class="sxs-lookup"><span data-stu-id="83a00-140">Below is an example of the groups you would need to have in your Keychain Access groups:</span></span>

      ```xml
      <?xml version="1.0" encoding="UTF-8"?>
      <!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN" "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
      <plist version="1.0">
            <dict>
                  <key>keychain-access-groups</key>
                  <array>
                        <string>$(AppIdentifierPrefix)com.xamarin.microsoftintunesample</string>
                        <string>$(AppIdentifierPrefix)com.xamarin.microsoftintunesample.intunemam</string>
                        <string>$(AppIdentifierPrefix)com.microsoft.intune.mam</string>
                        <string>$(AppIdentifierPrefix)com.microsoft.adalcache</string>
                  </array>
            </dict>
      </plist>
      ```

<span data-ttu-id="83a00-141">Sie haben die notwendigen Schritte ausgeführt um die Komponente in Ihrer Xamarin-basierten iOS-App einzurichten.</span><span class="sxs-lookup"><span data-stu-id="83a00-141">You have completed the steps necessary to build the component into your Xamarin-based iOS app.</span></span> <span data-ttu-id="83a00-142">Wenn Sie XCode zur Projekterstellung verwenden, können Sie `Intune App SDK Settings.bundle` verwenden.</span><span class="sxs-lookup"><span data-stu-id="83a00-142">If you are utilizing Xcode for building your project, you can use the `Intune App SDK Settings.bundle`.</span></span> <span data-ttu-id="83a00-143">So können Sie die Intune-Richtlinieneinstellungen ein- und ausschalten, während Sie Ihr Projekt zum Testen und Debuggen erstellen.</span><span class="sxs-lookup"><span data-stu-id="83a00-143">This allows you to toggle Intune policy settings on and off as you build your project to test and debug.</span></span> <span data-ttu-id="83a00-144">Um das Paket bestmöglich zu nutzen, folgen Sie den Schritten im [Intune App SDK für iOS – Entwicklerhandbuch](app-sdk-ios.md) und lesen Sie den Abschnitt zu [Debuggen in Xcode](app-sdk-ios.md#status-result-and-debug-notifications).</span><span class="sxs-lookup"><span data-stu-id="83a00-144">To take advantage of this bundle, follow the steps in the [Intune App SDK for iOS Developer Guide](app-sdk-ios.md) and read the section on [debugging in Xcode](app-sdk-ios.md#status-result-and-debug-notifications).</span></span>

## <a name="enabling-app-protection-policies-in-your-android-mobile-app"></a><span data-ttu-id="83a00-145">Aktivieren der App-Schutzrichtlinien in Ihrer mobilen Android-App</span><span class="sxs-lookup"><span data-stu-id="83a00-145">Enabling app protection policies in your Android mobile app</span></span>
<span data-ttu-id="83a00-146">Für Xamarin-basierte Android-Apps, die kein Benutzeroberflächenframework verwenden, lesen und befolgen Sie das [Entwicklerhandbuch zum Microsoft Intune App SDK für Android](app-sdk-android.md).</span><span class="sxs-lookup"><span data-stu-id="83a00-146">For Xamarin-based Android apps not using a UI framework, you need to read and follow the [Intune App SDK for Android Developer Guide](app-sdk-android.md).</span></span> <span data-ttu-id="83a00-147">Für Xamarin-basierte Android-Apps müssen die Klasse, Methoden und Aktivitäten basierend auf der im Handbuch enthaltenen [Tabelle](app-sdk-android.md#replace-classes-methods-and-activities-with-their-mam-equivalent) durch das MAM-Äquivalent ersetzt werden.</span><span class="sxs-lookup"><span data-stu-id="83a00-147">For your Xamarin-based Android app, you need to replace class, methods, and activities with their MAM equivalent based on the [table](app-sdk-android.md#replace-classes-methods-and-activities-with-their-mam-equivalent) included in the guide.</span></span> <span data-ttu-id="83a00-148">Wenn Ihre App keine `android.app.Application`-Klasse definiert, müssen Sie eine erstellen. Es muss sichergestellt werden, dass Sie von `MAMApplication` erben.</span><span class="sxs-lookup"><span data-stu-id="83a00-148">If your app doesn’t define an `android.app.Application` class, you need to create one and ensure that you inherit from `MAMApplication`.</span></span>

<span data-ttu-id="83a00-149">Für Xamarin.Forms und andere UI-Frameworks haben wir ein Tool bereit gestellt. Es heißt `MAM.Remapper`.</span><span class="sxs-lookup"><span data-stu-id="83a00-149">For Xamarin Forms and other UI frameworks, we have provided a tool called `MAM.Remapper`.</span></span> <span data-ttu-id="83a00-150">Das Tool nimmt den Klassentausch für Sie vor.</span><span class="sxs-lookup"><span data-stu-id="83a00-150">The tool accomplishes the class replacement for you.</span></span> <span data-ttu-id="83a00-151">Folgende Schritte müssen Sie jedoch selbst durchführen:</span><span class="sxs-lookup"><span data-stu-id="83a00-151">However, you need to do the following steps:</span></span>

1. <span data-ttu-id="83a00-152">Fügen Sie der Version 0.1.0.0 oder höher des `Microsoft.Intune.MAM.Remapper.Tasks`-NuGet-Pakets einen Verweis hinzu.</span><span class="sxs-lookup"><span data-stu-id="83a00-152">Add a reference to the `Microsoft.Intune.MAM.Remapper.Tasks` NuGet package version 0.1.0.0 or greater.</span></span>

2. <span data-ttu-id="83a00-153">Fügen Sie Ihrer CSPROJ-Datei von Android die folgende Zeile hinzu:</span><span class="sxs-lookup"><span data-stu-id="83a00-153">Add the following line to your Android csproj:</span></span>
   ```xml
   <Import
   Project="$(NugetPack)\\Microsoft.Intune.MAM.Remapper.Tasks.0.1.X.X\\build\\MonoAndroid10\\Microsoft.Intune.MAM.Remapper.targets" />
   ```

3. <span data-ttu-id="83a00-154">Legen Sie die Buildaktion der hinzugefügten `remapping-config.json`-Datei mit **RemappingConfigFile** fest.</span><span class="sxs-lookup"><span data-stu-id="83a00-154">Set the build action of the added `remapping-config.json` file to **RemappingConfigFile**.</span></span> <span data-ttu-id="83a00-155">Die integrierte `remapping-config.json`-Datei funktioniert nur mit Xamarin.Forms.</span><span class="sxs-lookup"><span data-stu-id="83a00-155">The included `remapping-config.json` only works with Xamarin.Forms.</span></span> <span data-ttu-id="83a00-156">Greifen Sie für andere Benutzeroberflächenframeworks auf das Readme im Remapper-NuGet-Paket zurück.</span><span class="sxs-lookup"><span data-stu-id="83a00-156">For other UI frameworks, refer to the Readme included with the Remapper NuGet package.</span></span>

## <a name="next-steps"></a><span data-ttu-id="83a00-157">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="83a00-157">Next steps</span></span>

<span data-ttu-id="83a00-158">Sie haben die grundlegenden Schritte zum Erstellen der Komponente auf Ihrer App abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="83a00-158">You have completed the basic steps of building the component into your app.</span></span> <span data-ttu-id="83a00-159">Jetzt können die Schritte ausgeführt werden, die in der Xamarin Android-Beispiel-App zu finden sind.</span><span class="sxs-lookup"><span data-stu-id="83a00-159">Now you can follow the steps included in the Xamarin Android sample app.</span></span> <span data-ttu-id="83a00-160">Wir haben zwei Beispiele bereit gestellt, eine für Xamarin.Forms und eine weitere für Android.</span><span class="sxs-lookup"><span data-stu-id="83a00-160">We have provided two samples, one for Xamarin.Forms and another for Android.</span></span>
