---
title: "Entwicklerhandbuch zum Microsoft Intune App SDK für Android"
description: "Das Microsoft Intune App SDK für Android ermöglicht die Integration von Intune Mobile App Management (MAM) in Ihre Android-App."
keywords: SDK
author: erikre
manager: angrobe
ms.author: erikre
ms.date: 11/28/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 0100e1b5-5edd-4541-95f1-aec301fb96af
ms.reviewer: aanavath
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 7bb78d05f9225c681c5b8a3bb6f1fcee4581a0de
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2017
---
# <a name="microsoft-intune-app-sdk-for-android-developer-guide"></a><span data-ttu-id="31d69-104">Entwicklerhandbuch zum Microsoft Intune App SDK für Android</span><span class="sxs-lookup"><span data-stu-id="31d69-104">Microsoft Intune App SDK for Android developer guide</span></span>

> [!NOTE]
> <span data-ttu-id="31d69-105">Lesen Sie am besten zuerst die [Übersicht über das Intune App SDK](app-sdk.md). Dort finden Sie Informationen zu den aktuellen Features des SDK sowie zu den Vorbereitungen, die Sie auf den verschiedenen unterstützten Plattformen für die Integration treffen müssen.</span><span class="sxs-lookup"><span data-stu-id="31d69-105">You might want to first read the [Intune App SDK overview](app-sdk.md), which covers the current features of the SDK and describes how to prepare for integration on each supported platform.</span></span>

<span data-ttu-id="31d69-106">Mit dem Microsoft Intune App SDK für Android können Sie die Intune-App-Schutzrichtlinien (auch als **APP**- oder MAM-Richtlinien bezeichnet) in Ihre native Android-App integrieren.</span><span class="sxs-lookup"><span data-stu-id="31d69-106">The Microsoft Intune App SDK for Android lets you incorporate Intune app protection policies (also known as **APP** or MAM policies) into your native Android app.</span></span> <span data-ttu-id="31d69-107">Intune-fähige Anwendungen sind in das Intune App SDK integrierte Anwendungen.</span><span class="sxs-lookup"><span data-stu-id="31d69-107">An Intune-enlightened application is one that is integrated with the Intune App SDK.</span></span> <span data-ttu-id="31d69-108">Intune-Administratoren können ganz einfach App-Schutzrichtlinien für Ihre Intune-fähige App bereitstellen, wenn diese aktiv von Intune verwaltet wird.</span><span class="sxs-lookup"><span data-stu-id="31d69-108">Intune administrators can easily deploy app protection policies to your Intune-enlightened app when Intune actively manages the app.</span></span>


## <a name="whats-in-the-sdk"></a><span data-ttu-id="31d69-109">Inhalt des SDK</span><span class="sxs-lookup"><span data-stu-id="31d69-109">What's in the SDK</span></span>

<span data-ttu-id="31d69-110">Das Intune App SDK besteht aus den folgenden Dateien:</span><span class="sxs-lookup"><span data-stu-id="31d69-110">The Intune App SDK consists of the following files:</span></span>  

* <span data-ttu-id="31d69-111">**Microsoft.Intune.MAM.SDK.aar**: Die SDK-Komponenten, mit Ausnahme der Support.V4- und der Support.V7-JAR-Datei.</span><span class="sxs-lookup"><span data-stu-id="31d69-111">**Microsoft.Intune.MAM.SDK.aar**: The SDK components, with the exception of the Support.V4 and Support.V7 JAR files.</span></span> <span data-ttu-id="31d69-112">Diese Datei kann anstelle der einzelnen Komponenten verwendet werden, wenn das Buildsystem AAR-Dateien unterstützt.</span><span class="sxs-lookup"><span data-stu-id="31d69-112">This file can be used in place of the individual components if your build system supports AAR files.</span></span>
* <span data-ttu-id="31d69-113">**Microsoft.Intune.MAM.SDK.Support.v4.jar**: Die Schnittstellen, die zum Aktivieren von MAM in Apps erforderlich sind, die die Unterstützungsbibliothek von Android v4 verwenden.</span><span class="sxs-lookup"><span data-stu-id="31d69-113">**Microsoft.Intune.MAM.SDK.Support.v4.jar**: The interfaces necessary to enable MAM in apps that use the Android v4 support library.</span></span> <span data-ttu-id="31d69-114">Apps, die diese Unterstützung benötigen, müssen direkt auf die JAR-Datei verweisen.</span><span class="sxs-lookup"><span data-stu-id="31d69-114">Apps that need this support must reference the JAR file directly.</span></span>
* <span data-ttu-id="31d69-115">**Microsoft.Intune.MAM.SDK.Support.v7.jar**: Die Schnittstellen, die zum Aktivieren von MAM in Apps erforderlich sind, die die Unterstützungsbibliothek von Android v7 verwenden.</span><span class="sxs-lookup"><span data-stu-id="31d69-115">**Microsoft.Intune.MAM.SDK.Support.v7.jar**: The interfaces necessary to enable MAM in apps that use the Android v7 support library.</span></span> <span data-ttu-id="31d69-116">Apps, die diese Unterstützung benötigen, müssen direkt auf die JAR-Datei verweisen.</span><span class="sxs-lookup"><span data-stu-id="31d69-116">Apps that need this support must reference the JAR file directly.</span></span>
* <span data-ttu-id="31d69-117">**Microsoft.Intune.MDM.SDK.DownlevelStubs.jar**: Diese JAR-Datei enthält Stubs für Android-Systemklassen, die nur auf neueren Geräten vorhanden sind, auf die aber Methoden in MAMActivity verweisen.</span><span class="sxs-lookup"><span data-stu-id="31d69-117">**Microsoft.Intune.MDM.SDK.DownlevelStubs.jar**: This jar contains stubs for Android system classes which are present only on newer devices but which are referenced by methods in MAMActivity.</span></span> <span data-ttu-id="31d69-118">Neuere Geräte ignorieren diese Stubklassen.</span><span class="sxs-lookup"><span data-stu-id="31d69-118">Newer devices will ignore these stub classes.</span></span> <span data-ttu-id="31d69-119">Diese JAR-Datei ist nur dann notwendig, wenn Ihre Anwendung Reflexionen auf Klassen anwendet, die von MAMActivity abgeleitet sind. Die meisten Anwendungen müssen sie nicht einbinden.</span><span class="sxs-lookup"><span data-stu-id="31d69-119">This jar is necessary only if your app performs reflection on classes deriving from MAMActivity, and most apps do not need to include it.</span></span> <span data-ttu-id="31d69-120">Wenn Sie diese JAR-Datei verwenden, müssen Sie darauf achten, dass Sie alle Klassen aus ProGuard ausschließen.</span><span class="sxs-lookup"><span data-stu-id="31d69-120">If you use this jar, you must be careful to exclude all its classes from ProGuard.</span></span> <span data-ttu-id="31d69-121">Sie befinden sich alle unter dem Stammpaket „android“.</span><span class="sxs-lookup"><span data-stu-id="31d69-121">They will all be under the "android" root package</span></span>
* <span data-ttu-id="31d69-122">**proguard.txt**: Enthält ProGuard-Regeln, die bei der Erstellung mithilfe von ProGuard angewendet werden müssen.</span><span class="sxs-lookup"><span data-stu-id="31d69-122">**proguard.txt**: Contains ProGuard rules which must be applied if building with ProGuard.</span></span>
* <span data-ttu-id="31d69-123">**CHANGELOG.txt**: Stellt eine Aufzeichnung der Änderungen bereit, die in den einzelnen SDK-Versionen vorgenommen wurden.</span><span class="sxs-lookup"><span data-stu-id="31d69-123">**CHANGELOG.txt**: Provides a record of changes made in each SDK version.</span></span>
* <span data-ttu-id="31d69-124">**THIRDPARTYNOTICES.TXT**: Ein Urheberrechtshinweis für Drittanbieter- und/oder OSS-Code, der in Ihrer App kompiliert wird.</span><span class="sxs-lookup"><span data-stu-id="31d69-124">**THIRDPARTYNOTICES.TXT**:  An attribution notice that acknowledges third-party and/or OSS code that will be compiled into your app.</span></span>

<span data-ttu-id="31d69-125">Wenn Ihr Buildsystem keine AAR-Dateien unterstützt, können Sie die folgenden Dateien anstelle von Microsoft.Intune.MAM.SDK.aar verwenden.</span><span class="sxs-lookup"><span data-stu-id="31d69-125">If your build system does not support AAR files, you may use the following files in place of Microsoft.Intune.MAM.SDK.aar.</span></span>
* <span data-ttu-id="31d69-126">**Microsoft.Intune.MAM.SDK.jar**: Die Schnittstellen, die zum Aktivieren von MAM und Interoperabilität mit der Intune-Unternehmensportal-App erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="31d69-126">**Microsoft.Intune.MAM.SDK.jar**: The interfaces necessary to enable MAM and interoperability with the Intune Company Portal app.</span></span> <span data-ttu-id="31d69-127">In Apps muss sie als Referenz zu einer Android-Bibliothek angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="31d69-127">Apps must specify it as an Android library reference.</span></span>
* <span data-ttu-id="31d69-128">**Ressourcenverzeichnis**: Die Ressourcen (etwa Zeichenfolgen), die das SDK benötigt.</span><span class="sxs-lookup"><span data-stu-id="31d69-128">**The res directory**: The resources (like strings) on which the SDK relies.</span></span>
* <span data-ttu-id="31d69-129">**AndroidManifest.xml**: Einstiegspunkte und Bibliotheksanforderungen.</span><span class="sxs-lookup"><span data-stu-id="31d69-129">**AndroidManifest.xml**: Entry points and the library requirements.</span></span>


## <a name="requirements"></a><span data-ttu-id="31d69-130">Anforderungen</span><span class="sxs-lookup"><span data-stu-id="31d69-130">Requirements</span></span>

<span data-ttu-id="31d69-131">Das Intune App SDK ist ein kompiliertes Android-Projekt.</span><span class="sxs-lookup"><span data-stu-id="31d69-131">The Intune App SDK is a compiled Android project.</span></span> <span data-ttu-id="31d69-132">Daher ist es größtenteils unabhängig von der Version von Android, die die App für ihre API-Mindest- bzw. -Zielversion verwendet.</span><span class="sxs-lookup"><span data-stu-id="31d69-132">As a result, it is largely unaffected by the version of Android that the app uses for its minimum or target API versions.</span></span> <span data-ttu-id="31d69-133">Das SDK unterstützt Android API 19 (Android 4.4 und höher) bis Android API 26 (Android 8.0).</span><span class="sxs-lookup"><span data-stu-id="31d69-133">The SDK supports Android API 19 (Android 4.4+) through Android API 26 (Android 8.0).</span></span>


### <a name="company-portal-app"></a><span data-ttu-id="31d69-134">Unternehmensportal-App</span><span class="sxs-lookup"><span data-stu-id="31d69-134">Company Portal app</span></span>
<span data-ttu-id="31d69-135">Das Intune App SDK für Android ist darauf angewiesen, dass die [Unternehmensportal](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal)-App auf dem Gerät vorhanden ist, damit App-Schutzrichtlinien aktiviert werden können.</span><span class="sxs-lookup"><span data-stu-id="31d69-135">The Intune App SDK for Android relies on the presence of the [Company Portal](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal) app on the device to enable app protection policies.</span></span> <span data-ttu-id="31d69-136">Das Unternehmensportal ruft App-Schutzrichtlinien vom Intune-Dienst ab.</span><span class="sxs-lookup"><span data-stu-id="31d69-136">The Company Portal retrieves app protection policies from the Intune service.</span></span> <span data-ttu-id="31d69-137">Wenn die App initialisiert wird, lädt sie die entsprechende Richtlinie sowie Code, um diese Richtlinie vom Unternehmensportal zu erzwingen.</span><span class="sxs-lookup"><span data-stu-id="31d69-137">When the app initializes, it loads policy and code to enforce that policy from the Company Portal.</span></span>

> [!NOTE]
> <span data-ttu-id="31d69-138">Wenn sich die Unternehmensportal-App nicht auf dem Gerät befindet, verhält sich eine Intune-fähige App genauso wie eine normale App, die keine Intune-App-Schutzrichtlinien unterstützt.</span><span class="sxs-lookup"><span data-stu-id="31d69-138">When the Company Portal app is not on the device, an Intune-enlightened app behaves the same as a normal app that does not support Intune app protection policies.</span></span>

<span data-ttu-id="31d69-139">Für einen App-Schutz ohne Registrierung des Geräts muss der Benutzer das Gerät _**nicht**_ mithilfe der Unternehmensportal-App registrieren.</span><span class="sxs-lookup"><span data-stu-id="31d69-139">For app protection without device enrollment, the user is _**not**_ required to enroll the device by using the Company Portal app.</span></span>

## <a name="sdk-integration"></a><span data-ttu-id="31d69-140">SDK-Integration</span><span class="sxs-lookup"><span data-stu-id="31d69-140">SDK Integration</span></span>

### <a name="build-integration"></a><span data-ttu-id="31d69-141">Buildintegration</span><span class="sxs-lookup"><span data-stu-id="31d69-141">Build integration</span></span>

<span data-ttu-id="31d69-142">Das Intune App SDK ist eine Android-Standardbibliothek ohne externe Abhängigkeiten.</span><span class="sxs-lookup"><span data-stu-id="31d69-142">The Intune App SDK is a standard Android library with no external dependencies.</span></span> <span data-ttu-id="31d69-143">**Microsoft.Intune.MAM.SDK.jar** enthält sowohl die Schnittstellen, die für die Aktivierung der App-Schutzrichtlinie erforderlich sind, als auch den für die Zusammenarbeit mit der Unternehmensportal-App von Microsoft Intune erforderlichen Code.</span><span class="sxs-lookup"><span data-stu-id="31d69-143">**Microsoft.Intune.MAM.SDK.jar** contains both the interfaces necessary for an app protection policy enablement and the code necessary to interoperate with the Microsoft Intune Company Portal app.</span></span>

<span data-ttu-id="31d69-144">**Microsoft.Intune.MAM.SDK.jar** muss als Android-Bibliotheksverweis angegeben werden.</span><span class="sxs-lookup"><span data-stu-id="31d69-144">**Microsoft.Intune.MAM.SDK.jar** must be specified as an Android library reference.</span></span> <span data-ttu-id="31d69-145">Öffnen Sie dazu Ihr App-Projekt in Android Studio, und wechseln Sie zu **File > New > New module** (Datei > Neu > Neues Modul), und wählen Sie dann **Import .JAR/.AAR Package** (JAR/AAR-Paket importieren) aus.</span><span class="sxs-lookup"><span data-stu-id="31d69-145">To do this, open your app project in Android Studio and go to **File > New > New module** and select **Import .JAR/.AAR Package**.</span></span> <span data-ttu-id="31d69-146">Wählen Sie das Android-Archivpaket Microsoft.Intune.MAM.SDK.aar aus.</span><span class="sxs-lookup"><span data-stu-id="31d69-146">Select our Android archive package Microsoft.Intune.MAM.SDK.aar.</span></span>

<span data-ttu-id="31d69-147">Darüber hinaus enthalten **Microsoft.Intune.MAM.SDK.Support.v4** und **Microsoft.Intune.MAM.SDK.Support.v7** Intune-Varianten von `android.support.v4` und `android.support.v7`.</span><span class="sxs-lookup"><span data-stu-id="31d69-147">Additionally, **Microsoft.Intune.MAM.SDK.Support.v4** and **Microsoft.Intune.MAM.SDK.Support.v7** contain Intune variants of `android.support.v4` and `android.support.v7` respectively.</span></span> <span data-ttu-id="31d69-148">Sie sind für den Fall nicht in Microsoft.Intune.MAM.SDK.aar integriert, dass eine Anwendung die Unterstützungsbibliotheken nicht einbeziehen möchte.</span><span class="sxs-lookup"><span data-stu-id="31d69-148">They are not built into Microsoft.Intune.MAM.SDK.aar in case an app does not want to include the support libraries.</span></span> <span data-ttu-id="31d69-149">Dabei handelt es sich anstelle von Android-Bibliotheksprojekten um JAR-Standarddateien.</span><span class="sxs-lookup"><span data-stu-id="31d69-149">They are standard JAR files instead of Android library projects.</span></span>

#### <a name="proguard"></a><span data-ttu-id="31d69-150">ProGuard</span><span class="sxs-lookup"><span data-stu-id="31d69-150">ProGuard</span></span>

<span data-ttu-id="31d69-151">Wenn [ProGuard](http://proguard.sourceforge.net/) (oder ein beliebiger anderer Komprimierungs- oder Obfuskationsmechanismus) als Buildschritt verwendet wird, müssen Intune SDK-Klassen ausgeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="31d69-151">If [ProGuard](http://proguard.sourceforge.net/) (or any other shrinking/obfuscation mechanism) is used as a build step, Intune SDK classes must be excluded.</span></span> <span data-ttu-id="31d69-152">Für ProGuard kann dies durch Einbeziehen der Regeln aus der Datei „proguard.txt“ erreicht werden, die mit dem SDK ausgeliefert wird.</span><span class="sxs-lookup"><span data-stu-id="31d69-152">For ProGuard, this can be accomplished by including the rules from the proguard.txt file distributed with the SDK.</span></span>

<span data-ttu-id="31d69-153">Die Azure Active Directory Authentication Librarys (ADAL) weisen möglicherweise eigene ProGuard-Einschränkungen auf.</span><span class="sxs-lookup"><span data-stu-id="31d69-153">The Azure Active Directory Authentication Libraries (ADAL) may have its own ProGuard restrictions.</span></span> <span data-ttu-id="31d69-154">Wenn Ihre App ADAL integriert, müssen Sie hinsichtlich dieser Einschränkungen der ADAL-Dokumentation folgen.</span><span class="sxs-lookup"><span data-stu-id="31d69-154">If your app integrates ADAL, you must follow the ADAL documentation on these restrictions.</span></span>

### <a name="entry-points"></a><span data-ttu-id="31d69-155">Einstiegspunkte</span><span class="sxs-lookup"><span data-stu-id="31d69-155">Entry points</span></span>

<span data-ttu-id="31d69-156">Die Azure Active Directory Authentication Library ([ADAL](https://azure.microsoft.com/documentation/articles/active-directory-authentication-libraries/)) verlangt, dass diese Berechtigungen Brokerauthentifizierung ausführen.</span><span class="sxs-lookup"><span data-stu-id="31d69-156">The Azure Active Directory Authentication Library ([ADAL](https://azure.microsoft.com/documentation/articles/active-directory-authentication-libraries/)) requires these permissions to perform brokered authentication.</span></span> <span data-ttu-id="31d69-157">Wenn diese Berechtigungen der App nicht gewährt oder vom Benutzer widerrufen werden, werden Authentifizierungsflüsse deaktiviert, die den Broker (die Unternehmensportal-App) erfordern.</span><span class="sxs-lookup"><span data-stu-id="31d69-157">If these permissions are not granted to the app or are revoked by the user, authentication flows that require the broker (the Company Portal app) will be disabled.</span></span>

<span data-ttu-id="31d69-158">Das Intune App SDK erfordert Änderungen am Quellcode einer App, damit Intune-App-Schutzrichtlinien aktiviert werden können.</span><span class="sxs-lookup"><span data-stu-id="31d69-158">The Intune App SDK requires changes to an app's source code to enable Intune app protection policies.</span></span> <span data-ttu-id="31d69-159">Zu diesem Zweck werden die Android-Basisklassen durch äquivalente Intune-Basisklassen ersetzt, deren Namen das Präfix **MAM** haben.</span><span class="sxs-lookup"><span data-stu-id="31d69-159">This is done through the replacement of the Android base classes with equivalent Intune base classes, whose names have the prefix **MAM**.</span></span> <span data-ttu-id="31d69-160">Die SDK-Klassen befinden sich zwischen der Android-Basisklasse und der App-eigenen abgeleiteten Version dieser Klasse.</span><span class="sxs-lookup"><span data-stu-id="31d69-160">The SDK classes live between the Android base class and the app's own derived version of that class.</span></span> <span data-ttu-id="31d69-161">Wenn Sie beispielsweise eine Aktivität verwenden, erhalten Sie eine Vererbungshierarchie, die wie folgt aussieht: `Activity` > `MAMActivity` > `AppSpecificActivity`.</span><span class="sxs-lookup"><span data-stu-id="31d69-161">Using an activity as an example, you end up with an inheritance hierarchy that looks like: `Activity` > `MAMActivity` > `AppSpecificActivity`.</span></span>

<span data-ttu-id="31d69-162">Wenn `AppSpecificActivity` z. B. mit dem übergeordneten Element (z. B. durch Aufrufen von `super.onCreate()`) interagiert, ist `MAMActivity` die übergeordnete Klasse.</span><span class="sxs-lookup"><span data-stu-id="31d69-162">For example, when `AppSpecificActivity` interacts with its parent (for example, calling `super.onCreate()`), `MAMActivity` is the super class.</span></span>

<span data-ttu-id="31d69-163">Typische Android-Apps verfügen über einen einzelnen Modus und können über ihr [**Context**](https://developer.android.com/reference/android/content/Context.html)-Objekt auf das gesamte System zugreifen.</span><span class="sxs-lookup"><span data-stu-id="31d69-163">Typical Android apps have a single mode and can access the system through their [**Context**](https://developer.android.com/reference/android/content/Context.html) object.</span></span> <span data-ttu-id="31d69-164">Andererseits verfügen Apps, in die das Intune App SDK integriert ist, über zwei Modi.</span><span class="sxs-lookup"><span data-stu-id="31d69-164">Apps that have integrated the Intune App SDK, on the other hand, have dual modes.</span></span> <span data-ttu-id="31d69-165">Diese Apps greifen auch weiterhin über das `Context`-Objekt auf das System zu.</span><span class="sxs-lookup"><span data-stu-id="31d69-165">These apps continue to access the system through the `Context` object.</span></span> <span data-ttu-id="31d69-166">Abhängig von der verwendeten Basis-`Activity` wird das `Context`-Objekt von Android bereitgestellt oder auf intelligente Weise zwischen einer eingeschränkten Ansicht des Systems und dem von Android bereitgestellten `Context` im Multiplexmodus gesendet.</span><span class="sxs-lookup"><span data-stu-id="31d69-166">Depending on the base `Activity` used, the `Context` object will be provided by Android or will intelligently multiplex between a restricted view of the system and the Android-provided `Context`.</span></span> <span data-ttu-id="31d69-167">Nachdem Sie die Ableitung von einem der MAM-Einstiegspunkte vorgenommen haben, kann `Context` wie gewohnt gefahrlos verwendet werden, z. B. zum Starten von `Activity`-Klassen und Verwenden von `PackageManager`.</span><span class="sxs-lookup"><span data-stu-id="31d69-167">After you derive from one of the MAM entry points, it's safe to use `Context` as you would normally -- for example, starting `Activity` classes and using `PackageManager`.</span></span>


## <a name="replace-classes-methods-and-activities-with-their-mam-equivalent"></a><span data-ttu-id="31d69-168">Ersetzen von Klassen, Methoden und Aktivitäten durch das MAM-Äquivalent</span><span class="sxs-lookup"><span data-stu-id="31d69-168">Replace classes, methods, and activities with their MAM equivalent</span></span>

<span data-ttu-id="31d69-169">Android-Basisklassen müssen durch ihre jeweiligen MAM-Äquivalente ersetzt werden.</span><span class="sxs-lookup"><span data-stu-id="31d69-169">Android base classes must be replaced with their respective MAM equivalents.</span></span> <span data-ttu-id="31d69-170">Suchen Sie dazu nach allen Instanzen der in der folgenden Tabelle aufgeführten Klassen, und ersetzen Sie sie durch das Intune App SDK-Äquivalent.</span><span class="sxs-lookup"><span data-stu-id="31d69-170">To do so, find all instances of the classes listed in the following table and replace them with the Intune App SDK equivalent.</span></span> <span data-ttu-id="31d69-171">Die meisten dieser Klassen sind Klassen, von denen Ihre App-Klassen erben, aber einige (z.B. MediaPlayer) sind Klassen, die Ihre App ohne Ableitung verwendet.</span><span class="sxs-lookup"><span data-stu-id="31d69-171">Most of these are classes which your app classes will inherit from, but some (e.g. MediaPlayer) will be classes your app uses without deriving.</span></span>

| <span data-ttu-id="31d69-172">Android-Basisklasse</span><span class="sxs-lookup"><span data-stu-id="31d69-172">Android base class</span></span> | <span data-ttu-id="31d69-173">Intune App SDK-Äquivalent</span><span class="sxs-lookup"><span data-stu-id="31d69-173">Intune App SDK replacement</span></span> |
|--|--|
| <span data-ttu-id="31d69-174">android.app.Activity</span><span class="sxs-lookup"><span data-stu-id="31d69-174">android.app.Activity</span></span> | <span data-ttu-id="31d69-175">MAMActivity</span><span class="sxs-lookup"><span data-stu-id="31d69-175">MAMActivity</span></span> |
| <span data-ttu-id="31d69-176">android.app.ActivityGroup</span><span class="sxs-lookup"><span data-stu-id="31d69-176">android.app.ActivityGroup</span></span> | <span data-ttu-id="31d69-177">MAMActivityGroup</span><span class="sxs-lookup"><span data-stu-id="31d69-177">MAMActivityGroup</span></span> |
| <span data-ttu-id="31d69-178">android.app.AliasActivity</span><span class="sxs-lookup"><span data-stu-id="31d69-178">android.app.AliasActivity</span></span> | <span data-ttu-id="31d69-179">MAMAliasActivity</span><span class="sxs-lookup"><span data-stu-id="31d69-179">MAMAliasActivity</span></span> |
| <span data-ttu-id="31d69-180">android.app.Application</span><span class="sxs-lookup"><span data-stu-id="31d69-180">android.app.Application</span></span> | <span data-ttu-id="31d69-181">MAMApplication</span><span class="sxs-lookup"><span data-stu-id="31d69-181">MAMApplication</span></span> |
| <span data-ttu-id="31d69-182">android.app.DialogFragment</span><span class="sxs-lookup"><span data-stu-id="31d69-182">android.app.DialogFragment</span></span> | <span data-ttu-id="31d69-183">MAMDialogFragment</span><span class="sxs-lookup"><span data-stu-id="31d69-183">MAMDialogFragment</span></span> |
| <span data-ttu-id="31d69-184">android.app.ExpandableListActivity</span><span class="sxs-lookup"><span data-stu-id="31d69-184">android.app.ExpandableListActivity</span></span> | <span data-ttu-id="31d69-185">MAMExpandableListActivity</span><span class="sxs-lookup"><span data-stu-id="31d69-185">MAMExpandableListActivity</span></span> |
| <span data-ttu-id="31d69-186">android.app.Fragment</span><span class="sxs-lookup"><span data-stu-id="31d69-186">android.app.Fragment</span></span> | <span data-ttu-id="31d69-187">MAMFragment</span><span class="sxs-lookup"><span data-stu-id="31d69-187">MAMFragment</span></span> |
| <span data-ttu-id="31d69-188">android.app.IntentService</span><span class="sxs-lookup"><span data-stu-id="31d69-188">android.app.IntentService</span></span> | <span data-ttu-id="31d69-189">MAMIntentService</span><span class="sxs-lookup"><span data-stu-id="31d69-189">MAMIntentService</span></span> |
| <span data-ttu-id="31d69-190">android.app.LauncherActivity</span><span class="sxs-lookup"><span data-stu-id="31d69-190">android.app.LauncherActivity</span></span> | <span data-ttu-id="31d69-191">MAMLauncherActivity</span><span class="sxs-lookup"><span data-stu-id="31d69-191">MAMLauncherActivity</span></span> |
| <span data-ttu-id="31d69-192">android.app.ListActivity</span><span class="sxs-lookup"><span data-stu-id="31d69-192">android.app.ListActivity</span></span> | <span data-ttu-id="31d69-193">MAMListActivity</span><span class="sxs-lookup"><span data-stu-id="31d69-193">MAMListActivity</span></span> |
| <span data-ttu-id="31d69-194">android.app.NativeActivity</span><span class="sxs-lookup"><span data-stu-id="31d69-194">android.app.NativeActivity</span></span> | <span data-ttu-id="31d69-195">MAMNativeActivity</span><span class="sxs-lookup"><span data-stu-id="31d69-195">MAMNativeActivity</span></span> |
| <span data-ttu-id="31d69-196">android.app.PendingIntent</span><span class="sxs-lookup"><span data-stu-id="31d69-196">android.app.PendingIntent</span></span> | <span data-ttu-id="31d69-197">MAMPendingIntent (siehe [PendingIntent](#pendingintent))</span><span class="sxs-lookup"><span data-stu-id="31d69-197">MAMPendingIntent (see [Pending Intent](#pendingintent))</span></span> |
| <span data-ttu-id="31d69-198">android.app.Service</span><span class="sxs-lookup"><span data-stu-id="31d69-198">android.app.Service</span></span> | <span data-ttu-id="31d69-199">MAMService</span><span class="sxs-lookup"><span data-stu-id="31d69-199">MAMService</span></span> |
| <span data-ttu-id="31d69-200">android.app.TabActivity</span><span class="sxs-lookup"><span data-stu-id="31d69-200">android.app.TabActivity</span></span> | <span data-ttu-id="31d69-201">MAMTabActivity</span><span class="sxs-lookup"><span data-stu-id="31d69-201">MAMTabActivity</span></span> |
| <span data-ttu-id="31d69-202">android.app.TaskStackBuilder</span><span class="sxs-lookup"><span data-stu-id="31d69-202">android.app.TaskStackBuilder</span></span> | <span data-ttu-id="31d69-203">MAMTaskStackBuilder</span><span class="sxs-lookup"><span data-stu-id="31d69-203">MAMTaskStackBuilder</span></span> |
| <span data-ttu-id="31d69-204">android.app.backup.BackupAgent</span><span class="sxs-lookup"><span data-stu-id="31d69-204">android.app.backup.BackupAgent</span></span> | <span data-ttu-id="31d69-205">MAMBackupAgent</span><span class="sxs-lookup"><span data-stu-id="31d69-205">MAMBackupAgent</span></span> |
| <span data-ttu-id="31d69-206">android.app.backup.BackupAgentHelper</span><span class="sxs-lookup"><span data-stu-id="31d69-206">android.app.backup.BackupAgentHelper</span></span> | <span data-ttu-id="31d69-207">MAMBackupAgentHelper</span><span class="sxs-lookup"><span data-stu-id="31d69-207">MAMBackupAgentHelper</span></span> |
| <span data-ttu-id="31d69-208">android.app.backup.FileBackupHelper</span><span class="sxs-lookup"><span data-stu-id="31d69-208">android.app.backup.FileBackupHelper</span></span> | <span data-ttu-id="31d69-209">MAMFileBackupHelper</span><span class="sxs-lookup"><span data-stu-id="31d69-209">MAMFileBackupHelper</span></span> |
| <span data-ttu-id="31d69-210">android.app.backup.SharePreferencesBackupHelper</span><span class="sxs-lookup"><span data-stu-id="31d69-210">android.app.backup.SharePreferencesBackupHelper</span></span> | <span data-ttu-id="31d69-211">MAMSharedPreferencesBackupHelper</span><span class="sxs-lookup"><span data-stu-id="31d69-211">MAMSharedPreferencesBackupHelper</span></span> |
| <span data-ttu-id="31d69-212">android.content.BroadcastReceiver</span><span class="sxs-lookup"><span data-stu-id="31d69-212">android.content.BroadcastReceiver</span></span> | <span data-ttu-id="31d69-213">MAMBroadcastReceiver</span><span class="sxs-lookup"><span data-stu-id="31d69-213">MAMBroadcastReceiver</span></span> |
| <span data-ttu-id="31d69-214">android.content.ContentProvider</span><span class="sxs-lookup"><span data-stu-id="31d69-214">android.content.ContentProvider</span></span> | <span data-ttu-id="31d69-215">MAMContentProvider</span><span class="sxs-lookup"><span data-stu-id="31d69-215">MAMContentProvider</span></span> |
| <span data-ttu-id="31d69-216">android.os.Binder</span><span class="sxs-lookup"><span data-stu-id="31d69-216">android.os.Binder</span></span> | <span data-ttu-id="31d69-217">MAMBinder (Nur erforderlich, wenn der Binder nicht von einer Schnittstelle der Android Interface Definition Language (AIDL) generiert wird.)</span><span class="sxs-lookup"><span data-stu-id="31d69-217">MAMBinder (Only necessary if the Binder is not generated from an Android Interface Definition Language (AIDL) interface)</span></span> |
| <span data-ttu-id="31d69-218">android.media.MediaPlayer</span><span class="sxs-lookup"><span data-stu-id="31d69-218">android.media.MediaPlayer</span></span> | <span data-ttu-id="31d69-219">MAMMediaPlayer</span><span class="sxs-lookup"><span data-stu-id="31d69-219">MAMMediaPlayer</span></span> |
| <span data-ttu-id="31d69-220">android.media.MediaMetadataRetriever</span><span class="sxs-lookup"><span data-stu-id="31d69-220">android.media.MediaMetadataRetriever</span></span> | <span data-ttu-id="31d69-221">android.media.MediaMetadataRetriever</span><span class="sxs-lookup"><span data-stu-id="31d69-221">MAMMediaMetadataRetriever</span></span> |
| <span data-ttu-id="31d69-222">android.provider.DocumentsProvider</span><span class="sxs-lookup"><span data-stu-id="31d69-222">android.provider.DocumentsProvider</span></span> | <span data-ttu-id="31d69-223">MAMDocumentsProvider</span><span class="sxs-lookup"><span data-stu-id="31d69-223">MAMDocumentsProvider</span></span> |
| <span data-ttu-id="31d69-224">android.preference.PreferenceActivity</span><span class="sxs-lookup"><span data-stu-id="31d69-224">android.preference.PreferenceActivity</span></span> | <span data-ttu-id="31d69-225">MAMPreferenceActivity</span><span class="sxs-lookup"><span data-stu-id="31d69-225">MAMPreferenceActivity</span></span> |

> [!NOTE]
> <span data-ttu-id="31d69-226">Auch wenn Ihre Anwendung keinen Bedarf an einer eigenen abgeleiteten `Application`-Klasse hat, [siehe `MAMApplication` weiter unten](#mamapplication).</span><span class="sxs-lookup"><span data-stu-id="31d69-226">Even if your application does not have a need for its own derived `Application` class, [see `MAMApplication` below](#mamapplication)</span></span>

### <a name="microsoftintunemamsdksupportv4jar"></a><span data-ttu-id="31d69-227">Microsoft.Intune.MAM.SDK.Support.v4.jar:</span><span class="sxs-lookup"><span data-stu-id="31d69-227">Microsoft.Intune.MAM.SDK.Support.v4.jar:</span></span>

| <span data-ttu-id="31d69-228">Android-Klasse – Intune MAM</span><span class="sxs-lookup"><span data-stu-id="31d69-228">Android Class Intune MAM</span></span> | <span data-ttu-id="31d69-229">Intune App SDK-Äquivalent</span><span class="sxs-lookup"><span data-stu-id="31d69-229">Intune App SDK replacement</span></span> |
|--|--|
| <span data-ttu-id="31d69-230">android.support.v4.app.DialogFragment</span><span class="sxs-lookup"><span data-stu-id="31d69-230">android.support.v4.app.DialogFragment</span></span> | <span data-ttu-id="31d69-231">MAMDialogFragment</span><span class="sxs-lookup"><span data-stu-id="31d69-231">MAMDialogFragment</span></span>
| <span data-ttu-id="31d69-232">android.support.v4.app.FragmentActivity</span><span class="sxs-lookup"><span data-stu-id="31d69-232">android.support.v4.app.FragmentActivity</span></span> | <span data-ttu-id="31d69-233">MAMFragmentActivity</span><span class="sxs-lookup"><span data-stu-id="31d69-233">MAMFragmentActivity</span></span>
| <span data-ttu-id="31d69-234">android.support.v4.app.Fragment</span><span class="sxs-lookup"><span data-stu-id="31d69-234">android.support.v4.app.Fragment</span></span> | <span data-ttu-id="31d69-235">MAMFragment</span><span class="sxs-lookup"><span data-stu-id="31d69-235">MAMFragment</span></span>
| <span data-ttu-id="31d69-236">Android.Support.v4.app.JobIntentService</span><span class="sxs-lookup"><span data-stu-id="31d69-236">android.support.v4.app.JobIntentService</span></span> | <span data-ttu-id="31d69-237">MAMJobIntentService</span><span class="sxs-lookup"><span data-stu-id="31d69-237">MAMJobIntentService</span></span>
| <span data-ttu-id="31d69-238">android.support.v4.app.TaskStackBuilder</span><span class="sxs-lookup"><span data-stu-id="31d69-238">android.support.v4.app.TaskStackBuilder</span></span> | <span data-ttu-id="31d69-239">MAMTaskStackBuilder</span><span class="sxs-lookup"><span data-stu-id="31d69-239">MAMTaskStackBuilder</span></span>
| <span data-ttu-id="31d69-240">android.support.v4.content.FileProvider</span><span class="sxs-lookup"><span data-stu-id="31d69-240">android.support.v4.content.FileProvider</span></span> | <span data-ttu-id="31d69-241">MAMFileProvider</span><span class="sxs-lookup"><span data-stu-id="31d69-241">MAMFileProvider</span></span>

### <a name="microsoftintunemamsdksupportv7jar"></a><span data-ttu-id="31d69-242">Microsoft.Intune.MAM.SDK.Support.v7.jar:</span><span class="sxs-lookup"><span data-stu-id="31d69-242">Microsoft.Intune.MAM.SDK.Support.v7.jar:</span></span>

|<span data-ttu-id="31d69-243">Android-Klasse</span><span class="sxs-lookup"><span data-stu-id="31d69-243">Android Class</span></span> | <span data-ttu-id="31d69-244">Intune App SDK-Äquivalent</span><span class="sxs-lookup"><span data-stu-id="31d69-244">Intune App SDK replacement</span></span> |
|--|--|
|<span data-ttu-id="31d69-245">Android.Support.V7.app.AppCompatActivity</span><span class="sxs-lookup"><span data-stu-id="31d69-245">android.support.v7.app.AppCompatActivity</span></span> | <span data-ttu-id="31d69-246">MAMAppCompatActivity</span><span class="sxs-lookup"><span data-stu-id="31d69-246">MAMAppCompatActivity</span></span> |

### <a name="renamed-methods"></a><span data-ttu-id="31d69-247">Umbenannte Methoden</span><span class="sxs-lookup"><span data-stu-id="31d69-247">Renamed Methods</span></span>


<span data-ttu-id="31d69-248">In vielen Fällen wurde eine in der Android-Klasse verfügbare Methode in der äquivalenten MAM-Klasse als abgeschlossen gekennzeichnet.</span><span class="sxs-lookup"><span data-stu-id="31d69-248">In many cases, a method available in the Android class has been marked as final in the MAM replacement class.</span></span> <span data-ttu-id="31d69-249">In diesem Fall stellt die äquivalente MAM-Klasse eine Methode mit ähnlichem Namen (normalerweise mit dem Suffix `MAM`) bereit, die stattdessen überschrieben werden sollte.</span><span class="sxs-lookup"><span data-stu-id="31d69-249">In this case, the MAM replacement class provides a similarly named method (generally suffixed with `MAM`) that you should override instead.</span></span> <span data-ttu-id="31d69-250">Wenn z. B. von `MAMActivity` abgeleitet wird, anstatt `onCreate()` zu überschreiben und `super.onCreate()` aufzurufen, muss `Activity` `onMAMCreate()` überschreiben und `super.onMAMCreate()` aufrufen.</span><span class="sxs-lookup"><span data-stu-id="31d69-250">For example, when deriving from `MAMActivity`, instead of overriding `onCreate()` and calling `super.onCreate()`, `Activity` must override `onMAMCreate()` and call `super.onMAMCreate()`.</span></span> <span data-ttu-id="31d69-251">Der Java-Compiler sollte die abgeschlossenen Einschränkungen erzwingen, um zu verhindern, dass die ursprüngliche Methode anstelle des MAM-Äquivalents überschrieben wird.</span><span class="sxs-lookup"><span data-stu-id="31d69-251">The Java compiler should enforce the final restrictions to prevent accidental override of the original method instead of the MAM equivalent.</span></span>

### <a name="mamapplication"></a><span data-ttu-id="31d69-252">MAMApplication</span><span class="sxs-lookup"><span data-stu-id="31d69-252">MAMApplication</span></span>
<span data-ttu-id="31d69-253">Aufgrund von Einschränkungen innerhalb des MAM SDK **müssen**  Sie eine Unterklasse von `com.microsoft.intune.mam.client.app.MAMApplication` erstellen und diese als Namen der `Application`-Klasse festlegen, die in Ihrem Manifest verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="31d69-253">Due to constraints within the MAM SDK, you **must** create a subclass of `com.microsoft.intune.mam.client.app.MAMApplication` and set it as the name of the `Application` class used in your manifest.</span></span> <span data-ttu-id="31d69-254">`MAMApplication` ist abstrakt und erfordert eine Überschreibung für `byte[] getADALSecretKey`. Im Javadoc zu dieser Funktion finden Sie weitere Informationen zu ihrer Implementierung.</span><span class="sxs-lookup"><span data-stu-id="31d69-254">`MAMApplication` is abstract and requires an override for `byte[] getADALSecretKey`, please see the Javadoc on that function for more information about how to implement it.</span></span>
### <a name="pendingintent"></a><span data-ttu-id="31d69-255">PendingIntent</span><span class="sxs-lookup"><span data-stu-id="31d69-255">PendingIntent</span></span>
<span data-ttu-id="31d69-256">Anstelle von `PendingIntent.get*` müssen Sie die `MAMPendingIntent.get*`-Methode verwenden.</span><span class="sxs-lookup"><span data-stu-id="31d69-256">Instead of `PendingIntent.get*`, you must use the `MAMPendingIntent.get*` method.</span></span> <span data-ttu-id="31d69-257">Anschließend können Sie den sich ergebenden `PendingIntent` wie gewohnt verwenden.</span><span class="sxs-lookup"><span data-stu-id="31d69-257">After this, you can use the resultant `PendingIntent` as usual.</span></span>

### <a name="manifest-replacements"></a><span data-ttu-id="31d69-258">Manifestersetzungen</span><span class="sxs-lookup"><span data-stu-id="31d69-258">Manifest Replacements</span></span>
<span data-ttu-id="31d69-259">Beachten Sie, dass es möglicherweise erforderlich ist, einige der oben aufgeführten Klassenersetzungen im Manifest als auch in Java-Code vorzunehmen.</span><span class="sxs-lookup"><span data-stu-id="31d69-259">Please note that it may be necessary to perform some of the above class replacements in the manifest as well as in Java code.</span></span> <span data-ttu-id="31d69-260">Besonderer Hinweis:</span><span class="sxs-lookup"><span data-stu-id="31d69-260">Of special note:</span></span>
* <span data-ttu-id="31d69-261">Manifestverweise auf `android.support.v4.content.FileProvider` müssen durch `com.microsoft.intune.mam.client.support.v4.content.MAMFileProvider` ersetzt werden.</span><span class="sxs-lookup"><span data-stu-id="31d69-261">Manifest references to `android.support.v4.content.FileProvider` must be replaced with `com.microsoft.intune.mam.client.support.v4.content.MAMFileProvider`.</span></span>
* <span data-ttu-id="31d69-262">Wenn Ihre Anwendung keine eigene abgeleitete Anwendungklasse benötigt, muss `com.microsoft.intune.mam.client.app.MAMApplication` als Name der Anwendungsklasse festgelegt werden, die im Anwendungsmanifest verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="31d69-262">If your application does not have a need for its own derived Application class, `com.microsoft.intune.mam.client.app.MAMApplication` must be set as the name of the Application class used in the manifest.</span></span>

## <a name="sdk-permissions"></a><span data-ttu-id="31d69-263">SDK-Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="31d69-263">SDK permissions</span></span>

<span data-ttu-id="31d69-264">Das Intune App SDK erfordert drei [Android-Systemberechtigungen](https://developer.android.com/guide/topics/security/permissions.html) für Apps, die es integrieren:</span><span class="sxs-lookup"><span data-stu-id="31d69-264">The Intune App SDK requires three [Android system permissions](https://developer.android.com/guide/topics/security/permissions.html) on apps that integrate it:</span></span>

* <span data-ttu-id="31d69-265">`android.permission.GET_ACCOUNTS` (zur Laufzeit angefordert, wenn erforderlich)</span><span class="sxs-lookup"><span data-stu-id="31d69-265">`android.permission.GET_ACCOUNTS`  (requested at runtime if required)</span></span>

* `android.permission.MANAGE_ACCOUNTS`

* `android.permission.USE_CREDENTIALS`

<span data-ttu-id="31d69-266">Die Azure Active Directory Authentication Library ([ADAL](https://azure.microsoft.com/documentation/articles/active-directory-authentication-libraries/)) verlangt, dass diese Berechtigungen Brokerauthentifizierung ausführen.</span><span class="sxs-lookup"><span data-stu-id="31d69-266">The Azure Active Directory Authentication Library ([ADAL](https://azure.microsoft.com/documentation/articles/active-directory-authentication-libraries/)) requires these permissions to perform brokered authentication.</span></span> <span data-ttu-id="31d69-267">Wenn diese Berechtigungen der App nicht gewährt oder vom Benutzer widerrufen werden, werden Authentifizierungsflüsse deaktiviert, die den Broker (die Unternehmensportal-App) erfordern.</span><span class="sxs-lookup"><span data-stu-id="31d69-267">If these permissions are not granted to the app or are revoked by the user, authentication flows that require the broker (the Company Portal app) will be disabled.</span></span>

## <a name="logging"></a><span data-ttu-id="31d69-268">Logging</span><span class="sxs-lookup"><span data-stu-id="31d69-268">Logging</span></span>

<span data-ttu-id="31d69-269">Die Protokollierung sollte früh initialisiert werden, um die protokollierten Daten optimal nutzen zu können.</span><span class="sxs-lookup"><span data-stu-id="31d69-269">Logging should be initialized early to get the most value out of logged data.</span></span> <span data-ttu-id="31d69-270">`Application.onMAMCreate()` ist in der Regel der beste Ort zum Initialisieren der Protokollierung.</span><span class="sxs-lookup"><span data-stu-id="31d69-270">`Application.onMAMCreate()` is typically the best place to initialize logging.</span></span>

<span data-ttu-id="31d69-271">Erstellen Sie einen [Java-Handler](http://docs.oracle.com/javase/7/docs/api/java/util/logging/Handler.html), und fügen Sie ihn zum `MAMLogHandlerWrapper` hinzu, um MAM-Protokolle in Ihrer App zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="31d69-271">To receive MAM logs in your app, create a [Java Handler](http://docs.oracle.com/javase/7/docs/api/java/util/logging/Handler.html) and add it to the `MAMLogHandlerWrapper`.</span></span> <span data-ttu-id="31d69-272">Dadurch wird `publish()` für den Anwendungshandler für jede Protokollnachricht aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="31d69-272">This will invoke `publish()` on the application handler for every log message.</span></span>

```java
/**
 * Global log handler that enables fine grained PII filtering within MAM logs.  
 *
 * To start using this you should build your own log handler and add it via
 * MAMComponents.get(MAMLogHandlerWrapper.class).addHandler(myHandler, false);  
 *
 * You may also remove the handler entirely via
 * MAMComponents.get(MAMLogHandlerWrapper.class).removeHandler(myHandler);
 */
public interface MAMLogHandlerWrapper {
    /**
     * Add a handler, PII can be toggled.
     *
     * @param handler handler to add.
     * @param wantsPII if PII is desired in the logs.    
     */
    void addHandler(final Handler handler, final boolean wantsPII);

    /**
     * Remove a handler.
     *
     * @param handler handler to remove.
     */
    void removeHandler(final Handler handler);
}
```



## <a name="enable-features-that-require-app-participation"></a><span data-ttu-id="31d69-273">Aktivieren von Funktionen, die App-Beteiligung erfordern</span><span class="sxs-lookup"><span data-stu-id="31d69-273">Enable features that require app participation</span></span>

<span data-ttu-id="31d69-274">Es gibt verschiedene App-Schutzrichtlinien, die das SDK nicht selbst implementieren kann.</span><span class="sxs-lookup"><span data-stu-id="31d69-274">There are several app protection policies the SDK cannot implement on its own.</span></span> <span data-ttu-id="31d69-275">Die App kann ihr Verhalten zum Bereitstellen dieser Features mit mehreren APIs steuern, die Sie in der folgenden `AppPolicy`-Schnittstelle finden.</span><span class="sxs-lookup"><span data-stu-id="31d69-275">The app can control its behavior to achieve these features by using several APIs that you can find in the following `AppPolicy` interface.</span></span> <span data-ttu-id="31d69-276">Verwenden Sie `MAMPolicyManager.getPolicy`, um eine `AppPolicy`-Instanz abzurufen.</span><span class="sxs-lookup"><span data-stu-id="31d69-276">To retrieve an `AppPolicy` instance, use `MAMPolicyManager.getPolicy`.</span></span>

```java
/**
 * External facing application policies.
 */
public interface AppPolicy {

/**
 * Restrict where an app can save personal data.
 * This function is now deprecated. Please use getIsSaveToLocationAllowed(SaveLocation, String) instead
 * @return True if the app is allowed to save to personal data stores; false otherwise.
 */
@Deprecated
boolean getIsSaveToPersonalAllowed();

/**
 * Check if policy prohibits saving to a content provider location.
 *
 * @param location
 *            a content URI to check
 * @return True if location is not a content URI or if policy does not prohibit saving to the content location.
 */
boolean getIsSaveToLocationAllowed(Uri location);

/**
 * Determines if the SaveLocation passed in can be saved to by the username associated with the cloud service.
 *
 * @param service
 *           see {@link SaveLocation}.
 * @param username
 *           the username/email associated with the cloud service being saved to. Use null if a mapping between
 *           the AAD username and the cloud service username does not exist or the username is not known.
 * @return true if the location can be saved to by the identity, false if otherwise.
 */
boolean getIsSaveToLocationAllowed(SaveLocation service, String username);

/**
 * Whether the SDK PIN prompt is enabled for the app.
 *
 * @return True if the PIN is enabled. False otherwise.
 */
boolean getIsPinRequired();

/**
 * Whether the Intune Managed Browser is required to open web links.
 * @return True if the Managed Browser is required, false otherwise
 */
boolean getIsManagedBrowserRequired();

/**
 * Check if policy allows Contact sync to local contact list.
 *
 * @return True if Contact sync is allowed to save to local contact list; false otherwise.
 */
boolean getIsContactSyncAllowed();

/**
 * This method is intended for diagnostic/telemetry purposes only. It can be used to discover whether
 * file encryption is in use. File encryption is transparent to the app, and the app should not need
 * to make any business logic decisions based on this.
 * 
 * @return True if file encryption is in use.
 */
boolean diagnosticIsFileEncryptionInUse();

/**
 * Return the policy in string format to the app.
 *  
 * @return The string representing the policy.
 */
String toString();

}

```

> [!NOTE]
> <span data-ttu-id="31d69-277">`MAMPolicyManager.getPolicy` gibt stets eine App-Richtlinie ungleich NULL zurück. Dies gilt selbst dann, wenn das Gerät oder die App keiner Intune-Verwaltungsrichtlinie unterliegt.</span><span class="sxs-lookup"><span data-stu-id="31d69-277">`MAMPolicyManager.getPolicy` will always return a non-null App Policy, even if the device or app is not under an Intune management policy.</span></span>

### <a name="example-determine-if-pin-is-required-for-the-app"></a><span data-ttu-id="31d69-278">Beispiel: Ermittlung, ob eine PIN für die App erforderlich ist</span><span class="sxs-lookup"><span data-stu-id="31d69-278">Example: Determine if PIN is required for the app</span></span>

<span data-ttu-id="31d69-279">Verfügt die App über eine eigene PIN-Benutzererfahrung, können Sie diese deaktivieren, wenn der IT-Administrator das SDK so konfiguriert hat, das eine App-PIN angefordert wird.</span><span class="sxs-lookup"><span data-stu-id="31d69-279">If the app has its own PIN user experience, you might want to disable it if the IT administrator has configured the SDK to prompt for an app PIN.</span></span> <span data-ttu-id="31d69-280">Um festzustellen, ob der IT-Administrator die App-PIN-Richtlinie für diese App bereitgestellt hat, rufen Sie die folgende Methode für den aktuellen Endbenutzer auf:</span><span class="sxs-lookup"><span data-stu-id="31d69-280">To determine if the IT administrator has deployed the app PIN policy to this app, for the current end user, call the following method:</span></span>

```java

MAMPolicyManager.getPolicy(currentActivity).getIsPinRequired();
```

### <a name="example-determine-the-primary-intune-user"></a><span data-ttu-id="31d69-281">Beispiel: Ermitteln des primären Intune-Benutzers</span><span class="sxs-lookup"><span data-stu-id="31d69-281">Example: Determine the primary Intune user</span></span>

<span data-ttu-id="31d69-282">Zusätzlich zu den in AppPolicy bereitgestellten APIs wird der Benutzerprinzipalname (User Principal Name, **UPN**) auch von der `getPrimaryUser()`-API in der `MAMUserInfo`-Schnittstelle verfügbar gemacht.</span><span class="sxs-lookup"><span data-stu-id="31d69-282">In addition to the APIs exposed in AppPolicy, the user principal name (**UPN**) is also exposed by the `getPrimaryUser()` API defined inside the `MAMUserInfo` interface.</span></span> <span data-ttu-id="31d69-283">Rufen Sie Folgendes auf, um den UPN abzurufen:</span><span class="sxs-lookup"><span data-stu-id="31d69-283">To get the UPN, call the following:</span></span>

```java
MAMUserInfo info = MAMComponents.get(MAMUserInfo.class);
if (info != null) return info.getPrimaryUser();
```

<span data-ttu-id="31d69-284">Die vollständige Definition der MAMUserInfo-Schnittstelle folgt unten:</span><span class="sxs-lookup"><span data-stu-id="31d69-284">The full definition of the MAMUserInfo interface is below:</span></span>

```java
/**
 * External facing user informations.
 *
 */
public interface MAMUserInfo {
       /**
        * Get the primary user name.
        *
        * @return the primary user name or null if the device is not enrolled.
        */
       String getPrimaryUser();
}
```

### <a name="example-determine-if-saving-to-device-or-cloud-storage-is-permitted"></a><span data-ttu-id="31d69-285">Beispiel: Ermittlung, ob das Speichern auf dem Gerät oder im Cloudspeicher zulässig ist</span><span class="sxs-lookup"><span data-stu-id="31d69-285">Example: Determine if saving to device or cloud storage is permitted</span></span>

<span data-ttu-id="31d69-286">Viele Apps implementieren Funktionen, die dem Endbenutzer ermöglichen, Dateien lokal oder bei einem Cloudspeicherdienst zu speichern.</span><span class="sxs-lookup"><span data-stu-id="31d69-286">Many apps implement features that allow the end user to save files locally or to a cloud storage service.</span></span> <span data-ttu-id="31d69-287">Mit dem Intune App SDK können IT-Administratoren dafür sorgen, dass keine Datenpreisgabe erfolgt, indem sie Richtlinieneinschränkungen entsprechend den Anforderungen ihrer Organisation anwenden.</span><span class="sxs-lookup"><span data-stu-id="31d69-287">The Intune App SDK allows IT administrators to protect against data leakage by applying policy restrictions as they see fit in their organization.</span></span>  <span data-ttu-id="31d69-288">Eine der durch die IT steuerbaren Richtlinien betrifft das Speichern in einem „persönlichen“, nicht verwalteten Datenspeicher durch den Endbenutzer.</span><span class="sxs-lookup"><span data-stu-id="31d69-288">One of the policies that IT can control is whether the end user can save to a "personal," unmanaged data store.</span></span> <span data-ttu-id="31d69-289">Darunter fällt das Speichern an einem lokalen Speicherort, auf einer SD-Karte und bei Sicherungsdiensten von Drittanbietern.</span><span class="sxs-lookup"><span data-stu-id="31d69-289">This includes saving to a local location, SD card, or third-party backup services.</span></span>

<span data-ttu-id="31d69-290">**Damit die Funktion aktiviert werden kann, ist App-Beteiligung erforderlich.**</span><span class="sxs-lookup"><span data-stu-id="31d69-290">**App participation is needed to enable the feature.**</span></span> <span data-ttu-id="31d69-291">Wenn Ihre App das direkte Speichern aus der App an einem persönlichen oder Cloudspeicherort ermöglicht, müssen Sie diese Funktion implementieren, damit IT-Administratoren steuern können, ob das Speichern an einem Speicherort erlaubt ist oder nicht.</span><span class="sxs-lookup"><span data-stu-id="31d69-291">If your app allows saving to personal or cloud locations directly from the app, you must implement this feature to ensure that the IT administrator can control whether saving to a location is allowed.</span></span> <span data-ttu-id="31d69-292">Die folgende API informiert die App darüber, ob das Speichern in einem persönlichen Speicher gemäß der aktuellen Intune-Administratorrichtlinie zulässig ist.</span><span class="sxs-lookup"><span data-stu-id="31d69-292">The API below lets the app know whether saving to a personal store is allowed by the current Intune administrator's policy.</span></span> <span data-ttu-id="31d69-293">Die App kann dann die Richtlinie erzwingen, da sie über den persönlichen Datenspeicher informiert ist, der dem Endbenutzer über die App zur Verfügung steht.</span><span class="sxs-lookup"><span data-stu-id="31d69-293">The app can then enforce the policy, since it is aware of personal data store available to the end user through the app.</span></span>  

<span data-ttu-id="31d69-294">Rufen Sie Folgendes auf, um zu ermitteln, ob die Richtlinie erzwungen wird:</span><span class="sxs-lookup"><span data-stu-id="31d69-294">To determine if the policy is enforced, make the following call:</span></span>

```java
MAMPolicyManager.getPolicy(currentActivity).getIsSaveToLocationAllowed(
SaveLocation service, String username);
``````

<span data-ttu-id="31d69-295">Dabei entspricht `service` einem der folgenden Werte für SaveLocations:</span><span class="sxs-lookup"><span data-stu-id="31d69-295">... where `service` is one of the following SaveLocations:</span></span>


    * <span data-ttu-id="31d69-296">SaveLocation.ONEDRIVE_FOR_BUSINESS</span><span class="sxs-lookup"><span data-stu-id="31d69-296">SaveLocation.ONEDRIVE_FOR_BUSINESS</span></span>
    * <span data-ttu-id="31d69-297">SaveLocation.LOCAL</span><span class="sxs-lookup"><span data-stu-id="31d69-297">SaveLocation.LOCAL</span></span>
    * <span data-ttu-id="31d69-298">SaveLocation.SHAREPOINT</span><span class="sxs-lookup"><span data-stu-id="31d69-298">SaveLocation.SHAREPOINT</span></span>

<span data-ttu-id="31d69-299">Die vorherige Methode zur Ermittlung, ob die Richtlinie eines Benutzers das Speichern von Daten an verschiedenen Speicherorten gestattet, war `getIsSaveToPersonalAllowed()` innerhalb derselben **AppPolicy**-Klasse.</span><span class="sxs-lookup"><span data-stu-id="31d69-299">The previous method of determining whether a user’s policy allowed them to save data to various locations was `getIsSaveToPersonalAllowed()` within the same **AppPolicy** class.</span></span> <span data-ttu-id="31d69-300">Diese Funktion ist jetzt **veraltet** und sollte nicht verwendet werden. Der folgende Aufruf entspricht `getIsSaveToPersonalAllowed()`:</span><span class="sxs-lookup"><span data-stu-id="31d69-300">This function is now **deprecated** and should not be used, the following invocation is equivalent to `getIsSaveToPersonalAllowed()`:</span></span>

```java

MAMPolicyManager.getPolicy(currentActivity).getIsSaveToLocationAllowed(SaveLocation.LOCAL, userNameInQuestion);
```

>[!NOTE]
> <span data-ttu-id="31d69-301">Verwenden Sie `SaveLocation.OTHER`, wenn der betreffende Speicherort nicht in der **SaveLocations**-Enumeration aufgeführt ist.</span><span class="sxs-lookup"><span data-stu-id="31d69-301">Use `SaveLocation.OTHER` if the location in question is not listed in the **SaveLocations** enum.</span></span>


## <a name="register-for-notifications-from-the-sdk"></a><span data-ttu-id="31d69-302">Registrieren für Benachrichtigungen vom SDK</span><span class="sxs-lookup"><span data-stu-id="31d69-302">Register for notifications from the SDK</span></span>

### <a name="overview"></a><span data-ttu-id="31d69-303">Übersicht</span><span class="sxs-lookup"><span data-stu-id="31d69-303">Overview</span></span>
<span data-ttu-id="31d69-304">Das Intune App SDK erlaubt Ihrer App die Steuerung des Verhaltens bestimmter Richtlinien, z. B. zur selektiven Zurücksetzung, wenn sie vom IT-Administrator bereitgestellt werden.</span><span class="sxs-lookup"><span data-stu-id="31d69-304">The Intune App SDK allows your app to control the behavior of certain policies, such as selective wipe, when they are deployed by the IT administrator.</span></span> <span data-ttu-id="31d69-305">Wenn ein IT-Administrator eine solche Richtlinie bereitstellt, sendet der Intune-Dienst eine Benachrichtigung an das SDK.</span><span class="sxs-lookup"><span data-stu-id="31d69-305">When an IT administrator deploys such a policy, the Intune service sends down a notification to the SDK.</span></span>

<span data-ttu-id="31d69-306">Ihre App muss sich für Benachrichtigungen vom SDK registrieren, indem ein `MAMNotificationReceiver` erstellt und mit `MAMNotificationReceiverRegistry` registriert wird.</span><span class="sxs-lookup"><span data-stu-id="31d69-306">Your app must register for notifications from the SDK by creating a `MAMNotificationReceiver` and  registering it with `MAMNotificationReceiverRegistry`.</span></span> <span data-ttu-id="31d69-307">Zu diesem Zweck werden der Empfänger und der Typ der Benachrichtigung in `App.onCreate` angegeben, wie das folgende Beispiel veranschaulicht:</span><span class="sxs-lookup"><span data-stu-id="31d69-307">This is done by providing the receiver and the type of notification desired in  `App.onCreate`, as the example below illustrates:</span></span>

```java
@Override
public void onCreate() {
  super.onCreate();
  MAMComponents.get(MAMNotificationReceiverRegistry.class)
    .registerReceiver(
      new ToastNotificationReceiver(),
      MAMNotificationType.WIPE_USER_DATA);
  }
``````

### <a name="mamnotificationreceiver"></a><span data-ttu-id="31d69-308">MAMNotificationReceiver</span><span class="sxs-lookup"><span data-stu-id="31d69-308">MAMNotificationReceiver</span></span>

<span data-ttu-id="31d69-309">Die `MAMNotificationReceiver`-Schnittstelle empfängt lediglich Benachrichtigungen vom Intune-Dienst.</span><span class="sxs-lookup"><span data-stu-id="31d69-309">The `MAMNotificationReceiver` interface simply receives notifications from the Intune service.</span></span> <span data-ttu-id="31d69-310">Einige Benachrichtigungen werden direkt vom SDK verarbeitet, andere erfordern die Beteiligung der App.</span><span class="sxs-lookup"><span data-stu-id="31d69-310">Some notifications are handled by the SDK directly, while others require the app's participation.</span></span> <span data-ttu-id="31d69-311">Eine App **muss** „true“ oder „false“ von einer Benachrichtigung zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="31d69-311">An app **must** return either true or false from a notification.</span></span> <span data-ttu-id="31d69-312">Sie muss immer "true" zurückgeben, es sei denn, eine von ihr aufgrund der Benachrichtigung ausgeführte Aktion schlägt fehl.</span><span class="sxs-lookup"><span data-stu-id="31d69-312">It must always return true unless some action it tried to take as a result of the notification failed.</span></span>

* <span data-ttu-id="31d69-313">Dieser Fehler kann beim Intune-Dienst gemeldet werden.</span><span class="sxs-lookup"><span data-stu-id="31d69-313">This failure may be reported to the Intune service.</span></span> <span data-ttu-id="31d69-314">Ein Beispiel für ein zu berichtendes Szenario ist, wenn die Anwendung Benutzerdaten nicht zurücksetzt, nachdem der IT-Administrator eine Zurücksetzung initiiert hat.</span><span class="sxs-lookup"><span data-stu-id="31d69-314">An example of a scenario to report is if the app fails to wipe user data after the IT administrator initiates a wipe.</span></span>

>[!NOTE]
> <span data-ttu-id="31d69-315">Ein Blockieren in `MAMNotificationReceiver.onReceive` ist sicher, weil der zugehörige Rückruf nicht im Benutzeroberflächenthread ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="31d69-315">It is safe to block in `MAMNotificationReceiver.onReceive` because its callback is not running on the UI thread.</span></span>

<span data-ttu-id="31d69-316">Die `MAMNotificationReceiver`-Schnittstelle (gemäß der Definition im SDK) ist nachfolgend enthalten:</span><span class="sxs-lookup"><span data-stu-id="31d69-316">The `MAMNotificationReceiver` interface as defined in the SDK is included below :</span></span>

```java
/**
 * The SDK is signaling that a MAM event has occurred.
 *
 */
public interface MAMNotificationReceiver {

    /**
     * A notification was received.
     *
     * @param notification
     *            The notification that was received.
     * @return The receiver should return true if it handled the
     *   notification without error (or if it decided to ignore the
     *   notification). If the receiver tried to take some action in
     *   response to the notification but failed to complete that
     *   action it should return false.
     */
    boolean onReceive(MAMNotification notification);
}

```

### <a name="types-of-notifications"></a><span data-ttu-id="31d69-317">Arten von Benachrichtigungen</span><span class="sxs-lookup"><span data-stu-id="31d69-317">Types of notifications</span></span>

<span data-ttu-id="31d69-318">Folgende Benachrichtigungen werden an die App gesendet; für manche ist ggf. App-Beteiligung erforderlich:</span><span class="sxs-lookup"><span data-stu-id="31d69-318">The following notifications are sent to the app and some of them may require app participation:</span></span>

* <span data-ttu-id="31d69-319">**WIPE_USER_DATA**: Diese Benachrichtigung wird in einer `MAMUserNotification`-Klasse gesendet.</span><span class="sxs-lookup"><span data-stu-id="31d69-319">**WIPE_USER_DATA**: This notification is sent in a `MAMUserNotification` class.</span></span> <span data-ttu-id="31d69-320">Beim Empfang dieser Benachrichtigung sollte die App alle Daten im Zusammenhang mit der mit `MAMUserNotification` übergebenen „Unternehmensidentität“ löschen.</span><span class="sxs-lookup"><span data-stu-id="31d69-320">When this notification is received, the app is expected to delete all data associated with the "corporate" identity passed with the `MAMUserNotification`.</span></span> <span data-ttu-id="31d69-321">Diese Benachrichtigung wird zurzeit bei der Aufhebung der Registrierung beim APP-WE-Dienst gesendet.</span><span class="sxs-lookup"><span data-stu-id="31d69-321">This notification is currently sent during APP-WE service unenrollment.</span></span> <span data-ttu-id="31d69-322">Der primäre Name des Benutzers wird in der Regel während der Registrierung angegeben.</span><span class="sxs-lookup"><span data-stu-id="31d69-322">The user's primary name is typically specified during the enrollment process.</span></span> <span data-ttu-id="31d69-323">Wenn Sie sich für diese Benachrichtigung registrieren, muss Ihre App sicherstellen, dass alle Benutzerdaten gelöscht wurden.</span><span class="sxs-lookup"><span data-stu-id="31d69-323">If you register for this notification, your app must ensure that all the user's data has been deleted.</span></span> <span data-ttu-id="31d69-324">Wenn Sie sich nicht für sie registrieren, wird das Standardverhalten für die selektive Zurücksetzung ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="31d69-324">If you don't register for it, the default selective wipe behavior will be performed.</span></span>

* <span data-ttu-id="31d69-325">**WIPE_USER_AUXILIARY_DATA**: Apps können sich für diese Benachrichtigung registrieren, wenn das Intune App SDK die standardmäßige selektive Zurücksetzung ausführen soll, aber bei der Zurücksetzung weitere Daten entfernt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="31d69-325">**WIPE_USER_AUXILIARY_DATA**: Apps can register for this notification if they'd like the Intune App SDK to perform the default selective wipe behavior, but would still like to remove some auxiliary data when the wipe occurs.</span></span>

* <span data-ttu-id="31d69-326">**REFRESH_POLICY**: Diese Benachrichtigung wird in einer `MAMUserNotification` gesendet.</span><span class="sxs-lookup"><span data-stu-id="31d69-326">**REFRESH_POLICY**: This notification is sent in a `MAMUserNotification`.</span></span> <span data-ttu-id="31d69-327">Bei Empfang dieser Benachrichtigung muss jegliche zwischengespeicherte Intune-Richtlinie für ungültig erklärt und aktualisiert werden.</span><span class="sxs-lookup"><span data-stu-id="31d69-327">When this notification is received, any cached Intune policy must be invalidated and updated.</span></span> <span data-ttu-id="31d69-328">In der Regel wird diese Aufgabe vom SDK ausgeführt, sollte aber von der App ausgeführt werden, wenn die Richtlinie beständig verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="31d69-328">This is generally handled by the SDK; however, it should be handled by the app if the policy is used in any persistent way.</span></span>

* <span data-ttu-id="31d69-329">**MANAGEMENT_REMOVED**: Diese Benachrichtigung wird in einer `MAMUserNotification` gesendet und informiert die App darüber, dass sie bald zu einer nicht verwalteten App wird.</span><span class="sxs-lookup"><span data-stu-id="31d69-329">**MANAGEMENT_REMOVED**: This notification is sent in a `MAMUserNotification` and informs the app that it is about to become unmanaged.</span></span> <span data-ttu-id="31d69-330">Nachdem sie nicht mehr verwaltet wird, kann die App keine verschlüsselten Dateien und keine mit MAMDataProtectionManager verschlüsselten Daten mehr lesen sowie nicht mehr mit der verschlüsselten Zwischenablage interagieren bzw. anderweitig am Ökosystem der verwalteten Apps teilnehmen.</span><span class="sxs-lookup"><span data-stu-id="31d69-330">Once unmanaged, it will no longer be able to read encrypted files, read data encrypted with MAMDataProtectionManager, interact with the encrypted clipboard, or otherwise participate in the managed-app ecosystem.</span></span>


> [!NOTE]
> <span data-ttu-id="31d69-331">Eine App sollte niemals gleichzeitig für `WIPE_USER_DATA`- und für `WIPE_USER_AUXILIARY_DATA`-Benachrichtigungen registriert werden.</span><span class="sxs-lookup"><span data-stu-id="31d69-331">An app should never register for both the `WIPE_USER_DATA` and `WIPE_USER_AUXILIARY_DATA` notifications.</span></span>


## <a name="configure-azure-active-directory-authentication-library-adal"></a><span data-ttu-id="31d69-332">Konfigurieren der Authentifizierungsbibliothek von Azure Active Directory (Active Directory Authentication Library, ADAL)</span><span class="sxs-lookup"><span data-stu-id="31d69-332">Configure Azure Active Directory Authentication Library (ADAL)</span></span>

<span data-ttu-id="31d69-333">Lesen Sie zunächst die ADAL-Integrationsrichtlinien im [ADAL-Repository auf GitHub](https://github.com/AzureAD/azure-activedirectory-library-for-android).</span><span class="sxs-lookup"><span data-stu-id="31d69-333">First, please read the ADAL integration guidelines found in the [ADAL repository on GitHub](https://github.com/AzureAD/azure-activedirectory-library-for-android).</span></span>

<span data-ttu-id="31d69-334">Das SDK ist für seine Szenarien, die die [Authentifizierung](https://azure.microsoft.com/documentation/articles/active-directory-authentication-scenarios/) und den bedingten Start betreffen, auf [ADAL](https://azure.microsoft.com/documentation/articles/active-directory-authentication-libraries/) angewiesen. Dazu müssen Apps mit [Azure Active Directory](https://azure.microsoft.com/documentation/articles/active-directory-whatis/) konfiguriert sein.</span><span class="sxs-lookup"><span data-stu-id="31d69-334">The SDK relies on [ADAL](https://azure.microsoft.com/documentation/articles/active-directory-authentication-libraries/) for its [authentication](https://azure.microsoft.com/documentation/articles/active-directory-authentication-scenarios/) and conditional launch scenarios, which require apps to be configured with [Azure Active Directory](https://azure.microsoft.com/documentation/articles/active-directory-whatis/).</span></span> <span data-ttu-id="31d69-335">Die Konfigurationswerte werden dem SDK über AndroidManifest-Metadaten übermittelt.</span><span class="sxs-lookup"><span data-stu-id="31d69-335">The configuration values are communicated to the SDK via AndroidManifest metadata.</span></span>

<span data-ttu-id="31d69-336">Zum Konfigurieren der App und zum Aktivieren der geeigneten Authentifizierung fügen Sie dem App-Knoten in der Datei „AndroidManifest.xml“ Folgendes hinzu.</span><span class="sxs-lookup"><span data-stu-id="31d69-336">To configure your app and enable proper authentication, add the following to the app node in AndroidManifest.xml.</span></span> <span data-ttu-id="31d69-337">Einige dieser Konfigurationen sind nur erforderlich, wenn Ihre App für die Authentifizierung im Allgemeinen ADAL verwendet. In diesem Fall benötigen Sie die speziellen Werte, die die App verwendet, um sich selbst bei AAD zu registrieren.</span><span class="sxs-lookup"><span data-stu-id="31d69-337">Some of these configurations are only required if your app uses ADAL for authentication in general; in that case, you will need the specific values your app uses to register itself with AAD.</span></span> <span data-ttu-id="31d69-338">Damit wird sichergestellt, dass der Endbenutzer nicht zweimal zur Authentifizierung aufgefordert wird, weil AAD zwei separate Registrierungswerte erkennt: einen von der App und einen vom SDK.</span><span class="sxs-lookup"><span data-stu-id="31d69-338">This is done to ensure that the end user does not get prompted for authentication twice, due to AAD recognizing two separate registration values: one from the app and one from the SDK.</span></span>

```xml
<meta-data
    android:name="com.microsoft.intune.mam.aad.Authority"
    android:value="https://AAD authority/" />
<meta-data
    android:name="com.microsoft.intune.mam.aad.ClientID"
    android:value="your-client-ID-GUID" />
<meta-data
    android:name="com.microsoft.intune.mam.aad.NonBrokerRedirectURI"
    android:value="your-redirect-URI" />
<meta-data
    android:name="com.microsoft.intune.mam.aad.SkipBroker"
    android:value="[true | false]" />
```

### <a name="adal-metadata"></a><span data-ttu-id="31d69-339">ADAL-Metadaten</span><span class="sxs-lookup"><span data-stu-id="31d69-339">ADAL metadata</span></span>

* <span data-ttu-id="31d69-340">**Authority** ist die derzeit verwendete AAD-Autorität.</span><span class="sxs-lookup"><span data-stu-id="31d69-340">**Authority** is the current AAD authority in use.</span></span> <span data-ttu-id="31d69-341">Sofern vorhanden, sollten Sie dort Ihre eigene Umgebung verwenden, wo AAD-Konten konfiguriert wurden.</span><span class="sxs-lookup"><span data-stu-id="31d69-341">If present, you should use your own environment where AAD accounts have been configured.</span></span> <span data-ttu-id="31d69-342">Wenn dieser Wert nicht vorhanden ist, wird der Intune-Standard verwendet.</span><span class="sxs-lookup"><span data-stu-id="31d69-342">If this value is absent, an Intune default is used.</span></span>

* <span data-ttu-id="31d69-343">**ClientID** ist die zu verwendende AAD-ClientID.</span><span class="sxs-lookup"><span data-stu-id="31d69-343">**ClientID** is the AAD ClientID to be used.</span></span> <span data-ttu-id="31d69-344">Sie sollten die ClientID Ihrer eigenen App verwenden, sofern diese bei Azure AD registriert ist.</span><span class="sxs-lookup"><span data-stu-id="31d69-344">You should use your own app's ClientID if it is registered with Azure AD.</span></span> <span data-ttu-id="31d69-345">Wenn dieser Wert nicht vorhanden ist, wird der Intune-Standard verwendet.</span><span class="sxs-lookup"><span data-stu-id="31d69-345">If this value is absent, an Intune default is used.</span></span>

* <span data-ttu-id="31d69-346">**NonBrokerRedirectURI** ist der Umleitungs-URI von AAD, der in brokerfreien Fällen verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="31d69-346">**NonBrokerRedirectURI** is the AAD redirect URI to use in broker-less cases.</span></span> <span data-ttu-id="31d69-347">Erfolgt keine Angabe, wird der Standardwert `urn:ietf:wg:oauth:2.0:oob` verwendet.</span><span class="sxs-lookup"><span data-stu-id="31d69-347">If none is specified, a default value of `urn:ietf:wg:oauth:2.0:oob` is used.</span></span> <span data-ttu-id="31d69-348">Dieser Standardwert ist für die meisten Apps geeignet.</span><span class="sxs-lookup"><span data-stu-id="31d69-348">This default is suitable for most apps.</span></span>

* <span data-ttu-id="31d69-349">**SkipBroker** wird für den Fall verwendet, dass die Client-ID nicht für die Verwendung des Broker-Umleitungs-URI konfiguriert wurde.</span><span class="sxs-lookup"><span data-stu-id="31d69-349">**SkipBroker** is used in case the ClientID has not been configured to use the broker redirect URI.</span></span> <span data-ttu-id="31d69-350">Der Standardwert ist „false“.</span><span class="sxs-lookup"><span data-stu-id="31d69-350">The default value is "false."</span></span>
    * <span data-ttu-id="31d69-351">Für Apps, die **ADAL nicht integrieren** und **nicht an der geräteübergreifenden Brokerauthentifizierung/SSO teilnehmen möchten**, sollte dieser Wert auf „true“ festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="31d69-351">For apps that **do not integrate ADAL** and **do not want to participate in device-wide brokered authentication/SSO**, this should be set to "true."</span></span> <span data-ttu-id="31d69-352">Wenn dieser Wert „true“ ist, wird „NonBrokerRedirectURI“ als einziger Umleitungs-URI verwendet.</span><span class="sxs-lookup"><span data-stu-id="31d69-352">When this value is "true," the only redirect URI that will be used is NonBrokerRedirectURI.</span></span>

    * <span data-ttu-id="31d69-353">Für Apps, die das geräteübergreifende SSO-Brokering unterstützen, sollte dieser Wert „false“ sein.</span><span class="sxs-lookup"><span data-stu-id="31d69-353">For apps that do support device-wide SSO brokering, this should be "false."</span></span> <span data-ttu-id="31d69-354">Wenn der Wert „false“ ist, wählt das SDK auf Basis der Verfügbarkeit des Brokers auf dem System einen Broker aus dem Ergebnis von [`com.microsoft.aad.adal.AuthenticationContext.getRedirectUriForBroker()`](https://github.com/AzureAD/azure-activedirectory-library-for-android) und „NonBrokerRedirectURI“ aus.</span><span class="sxs-lookup"><span data-stu-id="31d69-354">When the value is "false," the SDK will select a broker between the result of [`com.microsoft.aad.adal.AuthenticationContext.getRedirectUriForBroker()`](https://github.com/AzureAD/azure-activedirectory-library-for-android) and NonBrokerRedirectURI, based on the availability of the broker on the system.</span></span> <span data-ttu-id="31d69-355">Im Allgemeinen wird der Broker über die Unternehmensportal-App oder die Azure Authenticator-App zur Verfügung gestellt.</span><span class="sxs-lookup"><span data-stu-id="31d69-355">In general, the broker will be available from the Company Portal app or Azure Authenticator app.</span></span>

### <a name="common-adal-configurations"></a><span data-ttu-id="31d69-356">Häufig verwendete ADAL-Konfigurationen</span><span class="sxs-lookup"><span data-stu-id="31d69-356">Common ADAL configurations</span></span>

<span data-ttu-id="31d69-357">Nachfolgend sind gebräuchliche Methoden zum Konfigurieren einer App mit ADAL aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="31d69-357">The following are common ways an app can be configured with ADAL.</span></span> <span data-ttu-id="31d69-358">Suchen Sie die Konfiguration Ihrer App und stellen Sie sicher, dass die ADAL-Metadatenparameter (siehe oben) auf die erforderlichen Werte festgelegt sind.</span><span class="sxs-lookup"><span data-stu-id="31d69-358">Find your app's configuration and make sure to set the ADAL metadata parameters (explained above) to the necessary values.</span></span>

1. <span data-ttu-id="31d69-359">**App kann ADAL nicht integrieren**:</span><span class="sxs-lookup"><span data-stu-id="31d69-359">**App does not integrate ADAL:**</span></span>

    | <span data-ttu-id="31d69-360">Erforderlicher ADAL-Parameter</span><span class="sxs-lookup"><span data-stu-id="31d69-360">Required ADAL parameter</span></span> | <span data-ttu-id="31d69-361">Wert</span><span class="sxs-lookup"><span data-stu-id="31d69-361">Value</span></span> |
    |--|--|
    | <span data-ttu-id="31d69-362">Authority</span><span class="sxs-lookup"><span data-stu-id="31d69-362">Authority</span></span> | <span data-ttu-id="31d69-363">Gewünschte Umgebung, in der AAD-Konten konfiguriert wurden</span><span class="sxs-lookup"><span data-stu-id="31d69-363">Desired environment where AAD accounts have been configured</span></span> |
    | <span data-ttu-id="31d69-364">SkipBroker</span><span class="sxs-lookup"><span data-stu-id="31d69-364">SkipBroker</span></span> | <span data-ttu-id="31d69-365">True</span><span class="sxs-lookup"><span data-stu-id="31d69-365">True</span></span> |

2. <span data-ttu-id="31d69-366">**App kann ADAL integrieren**:</span><span class="sxs-lookup"><span data-stu-id="31d69-366">**App integrates ADAL:**</span></span>

    |<span data-ttu-id="31d69-367">Erforderlicher ADAL-Parameter</span><span class="sxs-lookup"><span data-stu-id="31d69-367">Required ADAL parameter</span></span>| <span data-ttu-id="31d69-368">Wert</span><span class="sxs-lookup"><span data-stu-id="31d69-368">Value</span></span> |
    |--|--|
    | <span data-ttu-id="31d69-369">Authority</span><span class="sxs-lookup"><span data-stu-id="31d69-369">Authority</span></span> | <span data-ttu-id="31d69-370">Gewünschte Umgebung, in der AAD-Konten konfiguriert wurden</span><span class="sxs-lookup"><span data-stu-id="31d69-370">Desired environment where AAD accounts have been configured</span></span> |
    | <span data-ttu-id="31d69-371">ClientID</span><span class="sxs-lookup"><span data-stu-id="31d69-371">ClientID</span></span> | <span data-ttu-id="31d69-372">Client-ID der App (von Azure AD generiert, wenn die App registriert ist)</span><span class="sxs-lookup"><span data-stu-id="31d69-372">The app's ClientID (generated by Azure AD when the app is registered)</span></span> |
    | <span data-ttu-id="31d69-373">NonBrokerRedirectURI</span><span class="sxs-lookup"><span data-stu-id="31d69-373">NonBrokerRedirectURI</span></span> | <span data-ttu-id="31d69-374">Ein gültiger Umleitungs-URI für die App oder `urn:ietf:wg:oauth:2.0:oob` als Standardwert.</span><span class="sxs-lookup"><span data-stu-id="31d69-374">A valid redirect URI for the app, or `urn:ietf:wg:oauth:2.0:oob`by default.</span></span> <br><br> <span data-ttu-id="31d69-375">Stellen Sie sicher, dass Sie den Wert als zulässigen Umleitungs-URI für die Client-ID Ihrer App konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="31d69-375">Make sure to configure the value as an acceptable redirect URI for your app's ClientID.</span></span>
    | <span data-ttu-id="31d69-376">SkipBroker</span><span class="sxs-lookup"><span data-stu-id="31d69-376">SkipBroker</span></span> | <span data-ttu-id="31d69-377">False</span><span class="sxs-lookup"><span data-stu-id="31d69-377">False</span></span> |


3. <span data-ttu-id="31d69-378">**Die App kann ADAL integrieren, unterstützt aber keine Brokerauthentifizierung/geräteübergreifende einmalige Anmeldung**:</span><span class="sxs-lookup"><span data-stu-id="31d69-378">**App integrates ADAL but does not support brokered authentication/device-wide SSO:**</span></span>

    |<span data-ttu-id="31d69-379">Erforderlicher ADAL-Parameter</span><span class="sxs-lookup"><span data-stu-id="31d69-379">Required ADAL parameter</span></span>| <span data-ttu-id="31d69-380">Wert</span><span class="sxs-lookup"><span data-stu-id="31d69-380">Value</span></span> |
    |--|--|
    | <span data-ttu-id="31d69-381">Authority</span><span class="sxs-lookup"><span data-stu-id="31d69-381">Authority</span></span> | <span data-ttu-id="31d69-382">Gewünschte Umgebung, in der AAD-Konten konfiguriert wurden</span><span class="sxs-lookup"><span data-stu-id="31d69-382">Desired environment where AAD accounts have been configured</span></span> |
    | <span data-ttu-id="31d69-383">ClientID</span><span class="sxs-lookup"><span data-stu-id="31d69-383">ClientID</span></span> | <span data-ttu-id="31d69-384">Client-ID der App (von Azure AD generiert, wenn die App registriert ist)</span><span class="sxs-lookup"><span data-stu-id="31d69-384">The app's ClientID (generated by Azure AD when the app is registered)</span></span> |
    | <span data-ttu-id="31d69-385">NonBrokerRedirectURI</span><span class="sxs-lookup"><span data-stu-id="31d69-385">NonBrokerRedirectURI</span></span> | <span data-ttu-id="31d69-386">Ein gültiger Umleitungs-URI für die App oder `urn:ietf:wg:oauth:2.0:oob` als Standardwert.</span><span class="sxs-lookup"><span data-stu-id="31d69-386">A valid redirect URI for the app, or `urn:ietf:wg:oauth:2.0:oob` by default.</span></span> <br><br> <span data-ttu-id="31d69-387">Stellen Sie sicher, dass Sie den Wert als zulässigen Umleitungs-URI für die Client-ID Ihrer App konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="31d69-387">Make sure to configure the value as an acceptable redirect URI for your app's ClientID.</span></span>
    | <span data-ttu-id="31d69-388">SkipBroker</span><span class="sxs-lookup"><span data-stu-id="31d69-388">SkipBroker</span></span> | <span data-ttu-id="31d69-389">**True**</span><span class="sxs-lookup"><span data-stu-id="31d69-389">**True**</span></span> |

## <a name="app-protection-policy-without-device-enrollment"></a><span data-ttu-id="31d69-390">App-Schutzrichtlinie ohne Geräteregistrierung</span><span class="sxs-lookup"><span data-stu-id="31d69-390">App protection policy without device enrollment</span></span>

### <a name="overview"></a><span data-ttu-id="31d69-391">Übersicht</span><span class="sxs-lookup"><span data-stu-id="31d69-391">Overview</span></span>
<span data-ttu-id="31d69-392">Die Intune-App-Schutzrichtlinie ohne Geräteregistrierung (auch als APP-WE oder MAM-WE bezeichnet) ermöglicht, dass Apps von Intune verwaltet werden können, ohne dass das Gerät bei Intune MDM registriert sein muss.</span><span class="sxs-lookup"><span data-stu-id="31d69-392">Intune app protection policy without device enrollment, also known as APP-WE or MAM-WE, allows apps to be managed by Intune without the need for the device to be enrolled Intune MDM.</span></span> <span data-ttu-id="31d69-393">APP-WE funktioniert mit oder ohne Geräteregistrierung.</span><span class="sxs-lookup"><span data-stu-id="31d69-393">APP-WE works with or without device enrollment.</span></span> <span data-ttu-id="31d69-394">Es ist weiterhin erforderlich, dass das Unternehmensportal auf dem Gerät installiert ist, aber der Benutzer muss sich nicht beim Unternehmensportal anmelden und das Gerät registrieren.</span><span class="sxs-lookup"><span data-stu-id="31d69-394">The Company Portal is still required to be installed on the device, but the user does not need to sign into the Company Portal and enroll the device.</span></span>

> [!NOTE]
> <span data-ttu-id="31d69-395">Alle Apps müssen die App-Schutzrichtlinie ohne Geräteregistrierung unterstützen.</span><span class="sxs-lookup"><span data-stu-id="31d69-395">All apps are required to support app protection policy without device enrollment.</span></span>

### <a name="workflow"></a><span data-ttu-id="31d69-396">Workflow</span><span class="sxs-lookup"><span data-stu-id="31d69-396">Workflow</span></span>

<span data-ttu-id="31d69-397">Wenn eine App ein neues Benutzerkonto erstellt, sollte sie das Konto für die Verwaltung mit dem Intune App SDK registrieren.</span><span class="sxs-lookup"><span data-stu-id="31d69-397">When an app creates a new user account, it should register the account for management with the Intune App SDK.</span></span> <span data-ttu-id="31d69-398">Das SDK erledigt die Details der Registrierung der App beim APP-WE-Dienst. Bei Bedarf wiederholt es jegliche Registrierungen in entsprechenden Zeitabständen, falls Fehler auftreten.</span><span class="sxs-lookup"><span data-stu-id="31d69-398">The SDK will handle the details of enrolling the app in the APP-WE service; if necessary, it will retry any enrollments at appropriate time intervals if failures occur.</span></span>

<span data-ttu-id="31d69-399">Die App kann das Intune App-SDK auch nach dem Status eines registrierten Benutzers abfragen, um zu ermitteln, ob der Zugriff des Benutzers auf Unternehmensdaten blockiert werden sollte.</span><span class="sxs-lookup"><span data-stu-id="31d69-399">The app can also query the Intune App SDK for the status of a registered user to determine if the user should be blocked from accessing corporate content.</span></span> <span data-ttu-id="31d69-400">Es können mehrere Konten für die Verwaltung registriert werden, aber derzeit darf nur ein Konto zurzeit aktiv beim APP-WE-Dienst registriert sein.</span><span class="sxs-lookup"><span data-stu-id="31d69-400">Multiple accounts may be registered for management, but currently only one account can be actively enrolled with the APP-WE service at a time.</span></span> <span data-ttu-id="31d69-401">Dies bedeutet, dass jeweils nur ein Konto in der App die App-Schutzrichtlinie erhalten kann.</span><span class="sxs-lookup"><span data-stu-id="31d69-401">This means only one account on the app can receive app protection policy at a time.</span></span>

<span data-ttu-id="31d69-402">Die App muss einen Rückruf bereitstellen, um das geeignete Zugriffstoken aus der Azure Active Directory Authentication Library (ADAL) im Namen des SDKs zu erlangen.</span><span class="sxs-lookup"><span data-stu-id="31d69-402">The app is required to provide a callback to acquire the appropriate access token from the Azure Active Directory Authentication Library (ADAL) on behalf of the SDK.</span></span> <span data-ttu-id="31d69-403">Es wird angenommen, dass die App für die Benutzerauthentifizierung und zum Abrufen eines eigenen Zugriffstokens bereits ADAL verwendet.</span><span class="sxs-lookup"><span data-stu-id="31d69-403">It is assumed that the app already uses ADAL for user authentication and to acquire its own access tokens.</span></span>

<span data-ttu-id="31d69-404">Wenn ein Konto vollständig von der App entfernt wird, muss sie die Registrierung für das Konto aufheben, um anzuzeigen, dass die Richtlinie für diesen Benutzer nicht länger von der App angewendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="31d69-404">When the app removes an account completely, it should unregister that account to indicate that the app should no longer apply policy for that user.</span></span> <span data-ttu-id="31d69-405">Wenn der Benutzer im MAM-Dienst registriert wurde, wird die Registrierung des Benutzers aufgehoben und die App zurückgesetzt.</span><span class="sxs-lookup"><span data-stu-id="31d69-405">If the user was enrolled in the MAM service, the user will be unenrolled and the app will be wiped.</span></span>


### <a name="overview-of-app-requirements"></a><span data-ttu-id="31d69-406">Übersicht über die App-Anforderungen</span><span class="sxs-lookup"><span data-stu-id="31d69-406">Overview of app requirements</span></span>

<span data-ttu-id="31d69-407">Ihre App muss zum Implementieren der APP-WE-Integration das Benutzerkonto mit dem MAM SDK registrieren:</span><span class="sxs-lookup"><span data-stu-id="31d69-407">To implement APP-WE integration, your app must register the user account with the MAM SDK:</span></span>

1. <span data-ttu-id="31d69-408">Die App _muss_ eine Instanz der `MAMServiceAuthenticationCallback`-Schnittstelle implementieren und registrieren.</span><span class="sxs-lookup"><span data-stu-id="31d69-408">The app _must_ implement and register an instance of the `MAMServiceAuthenticationCallback` interface.</span></span> <span data-ttu-id="31d69-409">Die Rückrufinstanz sollte so früh wie möglich im Lebenszyklus der App registriert werden (in der Regel in der `onMAMCreate()`-Methode der Anwendungsklasse).</span><span class="sxs-lookup"><span data-stu-id="31d69-409">The callback instance should be registered as early as possible in the app's lifecycle (typically in the `onMAMCreate()` method of the application class).</span></span>

2. <span data-ttu-id="31d69-410">Wenn ein Benutzerkonto erstellt wurde und sich der Benutzer erfolgreich mit ADAL anmeldet, dann _muss_ die App `registerAccountForMAM()` aufrufen.</span><span class="sxs-lookup"><span data-stu-id="31d69-410">When a user account is created and the user successfully signs in with ADAL, the app _must_ call the `registerAccountForMAM()`.</span></span>

3. <span data-ttu-id="31d69-411">Wenn ein Benutzerkonto vollständig entfernt wurde, sollte die App `unregisterAccountForMAM()` aufrufen, um das Konto aus der Intune-Verwaltung zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="31d69-411">When a user account is completely removed, the app should call `unregisterAccountForMAM()` to remove the account from Intune management.</span></span>

    > [!NOTE]
    > <span data-ttu-id="31d69-412">Wenn sich ein Benutzer vorübergehend von der App abmeldet, muss die App `unregisterAccountForMAM()` nicht aufrufen.</span><span class="sxs-lookup"><span data-stu-id="31d69-412">If a user signs out of the app temporarily, the app does not need to call `unregisterAccountForMAM()`.</span></span> <span data-ttu-id="31d69-413">Der Aufruf initiiert möglicherweise eine Zurücksetzung, um Unternehmensdaten für den Benutzer vollständig zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="31d69-413">The call may initiate a wipe to completely remove corporate data for the user.</span></span>


### <a name="mamenrollmentmanager"></a><span data-ttu-id="31d69-414">MAMEnrollmentManager</span><span class="sxs-lookup"><span data-stu-id="31d69-414">MAMEnrollmentManager</span></span>

<span data-ttu-id="31d69-415">Alle erforderlichen APIs für die Authentifizierung und Registrierung befinden sich in der `MAMEnrollmentManager`-Schnittstelle.</span><span class="sxs-lookup"><span data-stu-id="31d69-415">All the necessary authentication and registration APIs can be found in the `MAMEnrollmentManager` interface.</span></span> <span data-ttu-id="31d69-416">Ein Verweis auf `MAMEnrollmentManager` kann wie folgt abgerufen werden:</span><span class="sxs-lookup"><span data-stu-id="31d69-416">A reference to the `MAMEnrollmentManager` can be obtained as follows:</span></span>

```java
MAMEnrollmentManager mgr = MAMComponents.get(MAMEnrollmentManager.class);

// make use of mgr

```

<span data-ttu-id="31d69-417">Die zurückgegebenen `MAMEnrollmentManager`-Instanz ist garantiert nicht NULL.</span><span class="sxs-lookup"><span data-stu-id="31d69-417">The `MAMEnrollmentManager` instance returned is guaranteed not to be null.</span></span> <span data-ttu-id="31d69-418">Die API-Methoden werden in zwei Kategorien unterteilt: **Authentifizierung** und **Kontoregistrierung**.</span><span class="sxs-lookup"><span data-stu-id="31d69-418">The API methods fall into two categories: **authentication** and **account registration**.</span></span>

> [!NOTE]
> <span data-ttu-id="31d69-419">`MAMEnrollmentManager` enthält einige API-Methoden, die in Kürze veraltet sein werden.</span><span class="sxs-lookup"><span data-stu-id="31d69-419">`MAMEnrollmentManager` contains some API methods that will be deprecated soon.</span></span> <span data-ttu-id="31d69-420">Aus Gründen der Übersichtlichkeit werden nur die relevanten Methoden und Ergebniscodes im folgenden Codeblock angezeigt.</span><span class="sxs-lookup"><span data-stu-id="31d69-420">For clarity, only the relevant methods and result codes are shown in the code block below.</span></span>

```java
package com.microsoft.intune.mam.policy;

public interface MAMEnrollmentManager {
    public enum Result {
        AUTHORIZATION_NEEDED,
        NOT_LICENSED,
        ENROLLMENT_SUCCEEDED,
        ENROLLMENT_FAILED,
        WRONG_USER,
        MDM_ENROLLED,
        UNENROLLMENT_SUCCEEDED,
        UNENROLLMENT_FAILED,
        PENDING,
        COMPANY_PORTAL_REQUIRED;
    }

    //Authentication methods
    interface MAMServiceAuthenticationCallback {
        String acquireToken(String upn, String aadId, String resourceId);
    }
    void registerAuthenticationCallback(MAMServiceAuthenticationCallback callback);
    void updateToken(String upn, String aadId, String resourceId, String token);

    //Registration methods
    void registerAccountForMAM(String upn, String aadId, String tenantId);
    void unregisterAccountForMAM(String upn);
    Result getRegisteredAccountStatus(String upn);
}
```

### <a name="account-authentication"></a><span data-ttu-id="31d69-421">Kontoauthentifizierung</span><span class="sxs-lookup"><span data-stu-id="31d69-421">Account authentication</span></span>

<span data-ttu-id="31d69-422">In diesem Abschnitt werden die Methoden der Authentifizierungs-API in `MAMEnrollmentManager` und deren Verwendung beschrieben.</span><span class="sxs-lookup"><span data-stu-id="31d69-422">This section describes the authentication API methods in `MAMEnrollmentManager` and how to use them.</span></span>

```java
interface MAMServiceAuthenticationCallback {
        String acquireToken(String upn, String aadId, String resourceId);
}
void registerAuthenticationCallback(MAMServiceAuthenticationCallback callback);
void updateToken(String upn, String aadId, String resourceId, String token);
```

1. <span data-ttu-id="31d69-423">Die App muss die `MAMServiceAuthenticationCallback`-Schnittstelle implementieren, damit das SDK ein ADAL-Token für den angegebenen Benutzer und die Ressourcen-ID anfordern kann.</span><span class="sxs-lookup"><span data-stu-id="31d69-423">The app must implement the `MAMServiceAuthenticationCallback` interface to allow the SDK to request an ADAL token for the given user and resource ID.</span></span> <span data-ttu-id="31d69-424">Die Rückrufinstanz muss für `MAMEnrollmentManager` bereitgestellt werden, indem die zugehörige `registerAuthenticationCallback()`-Methode aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="31d69-424">The callback instance must be provided to the `MAMEnrollmentManager` by calling its `registerAuthenticationCallback()` method.</span></span> <span data-ttu-id="31d69-425">Möglicherweise ist bereits zu einem sehr frühen Zeitpunkt im Lebenszyklus der App ein Token für Registrierungsversuche oder Eincheckvorgänge zur Aktualisierung der App-Schutzrichtlinie erforderlich, daher ist der ideale Platz zum Registrieren des Rückrufs die `onMAMCreate()`-Methode der `MAMApplication`-Unterklasse der App.</span><span class="sxs-lookup"><span data-stu-id="31d69-425">A token may be needed very early in the app lifecycle for enrollment retries or app protection policy refresh check-ins, so the ideal place to register the callback is in the `onMAMCreate()` method of the app's `MAMApplication` subclass.</span></span>

2. <span data-ttu-id="31d69-426">Die `acquireToken()`-Methode sollte das Zugriffstoken für die angeforderte Ressource-ID für den angegebenen Benutzer abrufen.</span><span class="sxs-lookup"><span data-stu-id="31d69-426">The `acquireToken()` method should acquire the access token for the requested resource ID for the given user.</span></span> <span data-ttu-id="31d69-427">Wenn sie das angeforderte Token nicht abrufen kann, muss NULL zurückgeben werden.</span><span class="sxs-lookup"><span data-stu-id="31d69-427">If it can't acquire the requested token, it should return null.</span></span>

3. <span data-ttu-id="31d69-428">Für den Fall, dass die App kein Token bereitstellen kann, wenn das SDK `acquireToken()` aufruft (wenn bei der automatischen Authentifizierung z. B. ein Fehler auftritt und der Zeitpunkt ungeeignet ist, um eine Benutzeroberfläche anzuzeigen), kann die App zu einem späteren Zeitpunkt ein Token bereitstellen, indem die `updateToken()`-Methode aufgerufen wird.</span><span class="sxs-lookup"><span data-stu-id="31d69-428">In case the app is unable to provide a token when the SDK calls `acquireToken()`  -- for example, if silent authentication fails and it is an inconvenient time to show a UI -- the app can provide a token at a later time by calling the `updateToken()` method.</span></span> <span data-ttu-id="31d69-429">Derselbe UPN sowie dieselbe AAD-ID und Ressourcen-ID, die durch den vorherigen Aufruf von `acquireToken()` angefordert wurden, müssen zusammen mit dem abschließend erhaltenen Token an `updateToken()` übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="31d69-429">The same UPN, AAD ID, and resource ID that were requested by the prior call to `acquireToken()` must be passed to `updateToken()`, along with the token that was finally acquired.</span></span> <span data-ttu-id="31d69-430">Die App sollte diese Methode so früh wie möglich aufrufen, nachdem vom bereitgestellten Rückruf NULL zurückgegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="31d69-430">The app should call this method as soon as possible after returning null from the provided callback.</span></span>

> [!NOTE]
> <span data-ttu-id="31d69-431">Das SDK ruft `acquireToken()` in regelmäßigen Abständen auf, um das Token abzurufen, daher ist das Aufrufen von `updateToken()` nicht zwingend erforderlich.</span><span class="sxs-lookup"><span data-stu-id="31d69-431">The SDK will call `acquireToken()` periodically to get the token, so calling `updateToken()` is not strictly required.</span></span> <span data-ttu-id="31d69-432">Es wird jedoch empfohlen, da es beim zeitnahen Abschließen der Registrierungen und Eincheckvorgänge für die App-Schutzrichtlinie helfen kann.</span><span class="sxs-lookup"><span data-stu-id="31d69-432">However, it is recommended as it can help enrollments and app protection policy check-ins complete in a timely manner.</span></span>


### <a name="account-registration"></a><span data-ttu-id="31d69-433">Kontoregistrierung</span><span class="sxs-lookup"><span data-stu-id="31d69-433">Account registration</span></span>

<span data-ttu-id="31d69-434">In diesem Abschnitt werden die Methoden der Kontoregistrierungs-API in `MAMEnrollmentManager` und deren Verwendung beschrieben.</span><span class="sxs-lookup"><span data-stu-id="31d69-434">This section describes the account registration API methods in `MAMEnrollmentManager` and how to use them.</span></span>

```java
void registerAccountForMAM(String upn, String aadId, String tenantId);
void unregisterAccountForMAM(String upn);
Result getRegisteredAccountStatus(String upn);
```

1. <span data-ttu-id="31d69-435">Die App sollte `registerAccountForMAM()` aufrufen, um ein Konto für die Verwaltung zu registrieren.</span><span class="sxs-lookup"><span data-stu-id="31d69-435">To register an account for management, the app should call `registerAccountForMAM()`.</span></span> <span data-ttu-id="31d69-436">Ein Benutzerkonto wird über ihren UPN und ihre AAD-Benutzer-ID identifiziert.</span><span class="sxs-lookup"><span data-stu-id="31d69-436">A user account is identified by both its UPN and its AAD user ID.</span></span> <span data-ttu-id="31d69-437">Zudem ist die Mandanten-ID erforderlich, um die Registrierungsdaten dem AAD-Mandanten des Benutzers zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="31d69-437">The tenant ID is also required to associate enrollment data with the user's AAD tenant.</span></span> <span data-ttu-id="31d69-438">Das SDK versucht möglicherweise, die App für den angegebenen Benutzer im MAM-Dienst zu registrieren. Wenn bei der Registrierung ein Fehler auftritt, wiederholt das SDK die Registrierung in regelmäßigen Abständen, bis die Registrierung des Kontos aufgehoben wurde.</span><span class="sxs-lookup"><span data-stu-id="31d69-438">The SDK may attempt to enroll the app for the given user in the MAM service; if enrollment fails, it will periodically retry enrollment until the account is unregistered.</span></span> <span data-ttu-id="31d69-439">Der Wiederholungszeitraum beträgt in der Regel 12 bis 24 Stunden.</span><span class="sxs-lookup"><span data-stu-id="31d69-439">The retry period will typically be 12-24 hours.</span></span> <span data-ttu-id="31d69-440">Das SDK stellt den Status der Registrierungsversuche asynchron über Benachrichtigungen bereit.</span><span class="sxs-lookup"><span data-stu-id="31d69-440">The SDK provides the status of enrollment attempts asynchronously via notifications.</span></span>

2. <span data-ttu-id="31d69-441">Da die AAD-Authentifizierung erforderlich ist, ist der beste Zeitpunkt zum Registrieren des Benutzerkontos im Anschluss an die Anmeldung des Benutzers in der App und der erfolgreichen Authentifizierung mithilfe der ADAL.</span><span class="sxs-lookup"><span data-stu-id="31d69-441">Because AAD authentication is required, the best time to register the user account is after the user has signed into the app and is successfully authenticated using ADAL.</span></span>
    * <span data-ttu-id="31d69-442">Die AAD-ID und die Mandanten-ID des Benutzers werden vom Aufruf der ADAL-Authentifizierung als Teil des [`AuthenticationResult`](https://github.com/AzureAD/azure-activedirectory-library-for-android)-Objekts zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="31d69-442">The user's AAD ID and tenant ID are returned from the ADAL authentication call as part of the [`AuthenticationResult`](https://github.com/AzureAD/azure-activedirectory-library-for-android) object.</span></span> <span data-ttu-id="31d69-443">Die Mandanten-ID stammt aus der `AuthenticationResult.getTenantID()`-Methode.</span><span class="sxs-lookup"><span data-stu-id="31d69-443">The tenant ID comes from the `AuthenticationResult.getTenantID()` method.</span></span>
    * <span data-ttu-id="31d69-444">Informationen zum Benutzer befinden sich in einem untergeordneten Objekt des Typs `UserInfo`, das aus `AuthenticationResult.getUserInfo()` stammt, und die AAD-Benutzer-ID wird durch den Aufruf von `UserInfo.getUserId()` aus diesem Objekt abgerufen.</span><span class="sxs-lookup"><span data-stu-id="31d69-444">Information about the user is found in a sub-object of type `UserInfo` that comes from `AuthenticationResult.getUserInfo()`, and the AAD user ID is retrieved from that object by calling `UserInfo.getUserId()`.</span></span>

3. <span data-ttu-id="31d69-445">Die App sollte `unregisterAccountForMAM()` aufrufen, um die Registrierung eines Kontos für die Intune-Verwaltung aufzuheben.</span><span class="sxs-lookup"><span data-stu-id="31d69-445">To unregister an account from Intune management, the app should call `unregisterAccountForMAM()`.</span></span> <span data-ttu-id="31d69-446">Wenn das Konto erfolgreich registriert wurde und verwaltet wird, hebt das SDK die Registrierung des Kontos auf und setzt seine Daten zurück.</span><span class="sxs-lookup"><span data-stu-id="31d69-446">If the account has been successfully enrolled and is managed, the SDK will unenroll the account and wipe its data.</span></span> <span data-ttu-id="31d69-447">Regelmäßige Registrierungsversuche für das Konto werden beendet.</span><span class="sxs-lookup"><span data-stu-id="31d69-447">Periodic enrollment retries for the account will be stopped.</span></span> <span data-ttu-id="31d69-448">Das SDK stellt den Status der Anforderung zur Aufhebung der Registrierung asynchron über Benachrichtigungen bereit.</span><span class="sxs-lookup"><span data-stu-id="31d69-448">The SDK provides the status of unenrollment request asynchronously via notifications.</span></span>

### <a name="important-implementation-notes"></a><span data-ttu-id="31d69-449">Wichtige Hinweise zur Implementierung</span><span class="sxs-lookup"><span data-stu-id="31d69-449">Important implementation notes</span></span>

#### <a name="authentication"></a><span data-ttu-id="31d69-450">Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="31d69-450">Authentication</span></span>

* <span data-ttu-id="31d69-451">Wenn die App `registerAccountForMAM()` aufruft, erhält Sie möglicherweise kurze Zeit später über ihre `MAMServiceAuthenticationCallback`-Schnittstelle einen Rückruf zu einem anderen Thread.</span><span class="sxs-lookup"><span data-stu-id="31d69-451">When the app calls `registerAccountForMAM()`, it may receive a callback on its `MAMServiceAuthenticationCallback` interface shortly thereafter, on a different thread.</span></span> <span data-ttu-id="31d69-452">Idealerweise hat die App vor der Registrierung des Kontos ihr eigenes Token von der ADAL abgerufen, um die Beschaffung des **MAMService-Tokens** zu beschleunigen.</span><span class="sxs-lookup"><span data-stu-id="31d69-452">Ideally, the app acquired its own token from ADAL prior to registering the account to expedite the acquisition of the **MAMService token**.</span></span> <span data-ttu-id="31d69-453">Wenn die App über den Rückruf ein gültiges Token zurückgibt, wird die Registrierung fortgesetzt, und die App erhält das endgültige Ergebnis über eine Benachrichtigung.</span><span class="sxs-lookup"><span data-stu-id="31d69-453">IF the app returns a valid token from the callback, enrollment will proceed and the app will get the final result via a notification.</span></span>

* <span data-ttu-id="31d69-454">Wenn die App kein gültiges AAD-Token zurückgibt, wird `AUTHENTICATION_NEEDED` als endgültiges Ergebnis des Registrierungsversuchs zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="31d69-454">If the app doesn't return a valid AAD token, the final result from the enrollment attempt will be `AUTHENTICATION_NEEDED`.</span></span> <span data-ttu-id="31d69-455">Wenn die App dieses Ergebnis über eine Benachrichtigung erhält, kann sie den Registrierungsprozess durch die Beschaffung des **MAMService-Tokens** und den Aufruf der `updateToken()`-Methode beschleunigen, um den Registrierungsprozess erneut zu initiieren.</span><span class="sxs-lookup"><span data-stu-id="31d69-455">If the app receives this Result via notification, it can expedite the enrollment process by acquiring the **MAMService token** and calling the `updateToken()` method to initiate the enrollment process again.</span></span> <span data-ttu-id="31d69-456">Dies ist jedoch _keine_ feste Anforderung, da das SDK die Registrierung in regelmäßigen Abständen erneut versucht und den Rückruf aufruft, um das Token abzurufen.</span><span class="sxs-lookup"><span data-stu-id="31d69-456">This is _not_ a firm requirement, however, since the SDK retries enrollment periodically and invokes the callback to acquire the token.</span></span>

* <span data-ttu-id="31d69-457">Die registrierte `MAMServiceAuthenticationCallback`-Schnittstelle der App wird ebenfalls aufgerufen, um ein Token für regelmäßige Eincheckvorgänge zum Aktualisieren der App-Schutzrichtlinie abzurufen. Wenn die App ein Token nicht auf Anforderung bereitstellen kann, erhält sie keine Benachrichtigung. Sie sollte jedoch zum nächsten geeigneten Zeitpunkt versuchen, ein Token abzurufen und `updateToken()` aufzurufen, um den Eincheckvorgang zu beschleunigen.</span><span class="sxs-lookup"><span data-stu-id="31d69-457">The app's registered `MAMServiceAuthenticationCallback` will also be called to acquire a token for periodic app protection policy refresh check-ins. If the app is unable to provide a token when requested, it will not get a notification, but it should attempt to acquire a token and call `updateToken()` at the next convenient time to expedite the check-in process.</span></span> <span data-ttu-id="31d69-458">Ohne Bereitstellung eines Tokens wird der Rückruf beim nächsten Eincheckversuch weiterhin aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="31d69-458">If a token is not provided, the callback will still be called at the next check-in attempt.</span></span>

#### <a name="registration"></a><span data-ttu-id="31d69-459">Registrierung</span><span class="sxs-lookup"><span data-stu-id="31d69-459">Registration</span></span>

* <span data-ttu-id="31d69-460">Der Einfachheit halber sind die Registrierungsmethoden idempotent. `registerAccountForMAM()` registriert ein Konto und die App z. B. nur, wenn das Konto noch nicht registriert ist, und `unregisterAccountForMAM()` hebt die Registrierung eines Kontos nur auf, wenn es derzeit registriert ist.</span><span class="sxs-lookup"><span data-stu-id="31d69-460">For your convenience, the registration methods are idempotent; for example, `registerAccountForMAM()`will only register an account and attempt to enroll the app if the account is not already registered, and `unregisterAccountForMAM()` will only unregister an account if it is currently registered.</span></span> <span data-ttu-id="31d69-461">Nachfolgende Aufrufe sind Leerbefehle, daher ist es nicht schädlich, diese Methoden mehrmals aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="31d69-461">Subsequent calls are no-ops, so there is no harm in calling these methods more than once.</span></span> <span data-ttu-id="31d69-462">Darüber hinaus wird die Übereinstimmung zwischen Aufrufen dieser Methoden und Benachrichtigungen über Ergebnisse nicht garantiert. Wenn z. B. `registerAccountForMAM` für eine Identität aufgerufen wird, die bereits registriert ist, wird die Benachrichtigung für diese Identität möglicherweise nicht erneut gesendet.</span><span class="sxs-lookup"><span data-stu-id="31d69-462">Additionally, correspondence between calls to these methods and notifications of results are not guaranteed: i.e. if `registerAccountForMAM` is called for an identity that is already registered, the notification may not be sent again for that identity.</span></span> <span data-ttu-id="31d69-463">Es ist möglich, dass Benachrichtigungen gesendet werden, die mit keinem Aufruf dieser Methoden übereinstimmen, da das SDK möglicherweise regelmäßig Registrierungsversuche im Hintergrund durchführt und das Aufheben der Registrierung möglicherweise durch Zurücksetzungsanforderungen ausgelöst wird, die vom Intune-Dienst empfangen wurden.</span><span class="sxs-lookup"><span data-stu-id="31d69-463">It is possible that notifications are sent that don't correspond to any calls to these methods, since the SDK may periodically try enrollments in the background, and unenrollments may be triggered by wipe requests received from the Intune service.</span></span>

* <span data-ttu-id="31d69-464">Die Registrierungsmethoden können für eine beliebige Anzahl von unterschiedlichen Identitäten aufgerufen werden, aber derzeit kann nur ein Benutzerkonto erfolgreich registriert sein.</span><span class="sxs-lookup"><span data-stu-id="31d69-464">The registration methods can be called for any number of different identities, but currently only one user account can become successfully enrolled.</span></span> <span data-ttu-id="31d69-465">Wenn mehrere Benutzerkonten, die für Intune lizenziert und Ziel der App-Schutzrichtlinie sind, zum gleichen oder nahezu dem gleichen Zeitpunkt registriert werden, gibt es keine Garantie dahingehend, welches dieser Benutzerkonten das Rennen macht.</span><span class="sxs-lookup"><span data-stu-id="31d69-465">If multiple user accounts that are licensed for Intune and targeted by app protection policy are registered at or near the same time, there is no guarantee on which one will win the race.</span></span>

* <span data-ttu-id="31d69-466">Abschließend können Sie `MAMEnrollmentManager` abfragen, um zu prüfen, ob ein bestimmtes Konto registriert ist, und um seinen aktuellen Status mithilfe der `getRegisteredAccountStatus`-Methode abzurufen.</span><span class="sxs-lookup"><span data-stu-id="31d69-466">Finally, you can query the `MAMEnrollmentManager` to see if a particular account is registered and to get its current status using the `getRegisteredAccountStatus` method.</span></span> <span data-ttu-id="31d69-467">Wenn das bereitgestellte Konto nicht registriert ist, gibt diese Methode **NULL** zurück.</span><span class="sxs-lookup"><span data-stu-id="31d69-467">If the provided account is not registered, this method will return **null**.</span></span> <span data-ttu-id="31d69-468">Wenn das Konto registriert ist, gibt diese Methode den Status des Kontos als eines der Elemente der `MAMEnrollmentManager.Result`-Enumeration zurück.</span><span class="sxs-lookup"><span data-stu-id="31d69-468">If the account is registered, this method will return the account's status as one of the members of the `MAMEnrollmentManager.Result` enumeration.</span></span>

### <a name="result-and-status-codes"></a><span data-ttu-id="31d69-469">Ergebnis und Statuscodes</span><span class="sxs-lookup"><span data-stu-id="31d69-469">Result and status codes</span></span>

<span data-ttu-id="31d69-470">Wenn ein Konto erstmalig registriert wird, verfügt es über den Status `PENDING`, wodurch angegeben wird, dass der erste Registrierungsversuch für den MAM-Dienst unvollständig ist.</span><span class="sxs-lookup"><span data-stu-id="31d69-470">When an account is first registered, it begins in the `PENDING` state, indicating that the initial MAM service enrollment attempt is incomplete.</span></span> <span data-ttu-id="31d69-471">Nachdem der Registrierungsversuch abgeschlossen ist, wird eine Benachrichtigung mit einem der Ergebniscodes aus der folgenden Tabelle gesendet.</span><span class="sxs-lookup"><span data-stu-id="31d69-471">After the enrollment attempt finishes, a notification will be sent with one of the Result codes in the table below.</span></span> <span data-ttu-id="31d69-472">Darüber hinaus gibt die `getRegisteredAccountStatus()`-Methode den Kontostatus zurück, damit die App immer bestimmen kann, ob der Zugriff für diesen Benutzer auf Unternehmensdaten blockiert ist.</span><span class="sxs-lookup"><span data-stu-id="31d69-472">In addition, the `getRegisteredAccountStatus()` method will return the account's status so the app can always determine if access to corporate content is blocked for that user.</span></span> <span data-ttu-id="31d69-473">Wenn bei der Registrierung ein Fehler auftritt, kann der Kontostatus mit der Zeit wechseln, da das SDK die Registrierung im Hintergrund erneut versucht.</span><span class="sxs-lookup"><span data-stu-id="31d69-473">If the enrollment attempt fails, the account's status may change over time as the SDK retries enrollment in the background.</span></span>

|<span data-ttu-id="31d69-474">Ergebniscode</span><span class="sxs-lookup"><span data-stu-id="31d69-474">Result code</span></span> | <span data-ttu-id="31d69-475">Erläuterung</span><span class="sxs-lookup"><span data-stu-id="31d69-475">Explanation</span></span> |
| -- | -- |
|<span data-ttu-id="31d69-476">AUTHORIZATION_NEEDED</span><span class="sxs-lookup"><span data-stu-id="31d69-476">AUTHORIZATION_NEEDED</span></span> | <span data-ttu-id="31d69-477">Dieses Ergebnis gibt an, dass von der registrierten `MAMServiceAuthenticationCallback`-Instanz der App kein Token bereitgestellt wurde oder das bereitgestellte Token war ungültig.</span><span class="sxs-lookup"><span data-stu-id="31d69-477">This result indicates that a token was not provided by the app’s registered `MAMServiceAuthenticationCallback` instance, or the provided token was invalid.</span></span>  <span data-ttu-id="31d69-478">Die App sollte ein gültiges Token abrufen und `updateToken()` aufrufen, sofern möglich.</span><span class="sxs-lookup"><span data-stu-id="31d69-478">The app should acquire a valid token and call `updateToken()` if possible.</span></span> |
| <span data-ttu-id="31d69-479">NOT_LICENSED</span><span class="sxs-lookup"><span data-stu-id="31d69-479">NOT_LICENSED</span></span> | <span data-ttu-id="31d69-480">Der Benutzer ist für Intune nicht lizenziert oder bei dem Versuch, den Kontakt zum Intune MAM-Dienst herzustellen, ist ein Fehler aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="31d69-480">The user is not licensed for Intune, or the attempt to contact the Intune MAM service failed.</span></span>  <span data-ttu-id="31d69-481">Die App sollte in einem nicht verwalteten (normalen) Zustand fortfahren, und der Benutzer sollte nicht blockiert werden.</span><span class="sxs-lookup"><span data-stu-id="31d69-481">The app should continue in an unmanaged (normal) state and the user should not be blocked.</span></span>  <span data-ttu-id="31d69-482">Registrierungen werden für den Fall in regelmäßigen Abständen wiederholt, dass der Benutzer zukünftig über eine Lizenz verfügt.</span><span class="sxs-lookup"><span data-stu-id="31d69-482">Enrollments will be retried periodically in case the user becomes licensed in the future.</span></span> |
| <span data-ttu-id="31d69-483">ENROLLMENT_SUCCEEDED</span><span class="sxs-lookup"><span data-stu-id="31d69-483">ENROLLMENT_SUCCEEDED</span></span> | <span data-ttu-id="31d69-484">Der Registrierungsversuch wurde erfolgreich durchgeführt, oder der Benutzer ist bereits registriert.</span><span class="sxs-lookup"><span data-stu-id="31d69-484">The enrollment attempt succeeded, or the user is already enrolled.</span></span>  <span data-ttu-id="31d69-485">Im Falle einer erfolgreichen Registrierung wird vor dieser Benachrichtigung eine Benachrichtigung zur Richtlinienaktualisierung gesendet.</span><span class="sxs-lookup"><span data-stu-id="31d69-485">In the case of a successful enrollment, a policy refresh notification will be sent before this notification.</span></span>  <span data-ttu-id="31d69-486">Der Zugriff auf Unternehmensdaten sollte zugelassen werden.</span><span class="sxs-lookup"><span data-stu-id="31d69-486">Access to corporate data should be allowed.</span></span> |
| <span data-ttu-id="31d69-487">ENROLLMENT_FAILED</span><span class="sxs-lookup"><span data-stu-id="31d69-487">ENROLLMENT_FAILED</span></span> | <span data-ttu-id="31d69-488">Fehler beim Registrierungsversuch.</span><span class="sxs-lookup"><span data-stu-id="31d69-488">The enrollment attempt failed.</span></span>  <span data-ttu-id="31d69-489">Weitere Details finden Sie in den Geräteprotokollen.</span><span class="sxs-lookup"><span data-stu-id="31d69-489">Further details can be found in the device logs.</span></span>  <span data-ttu-id="31d69-490">Die App sollte in diesem Zustand nicht den Zugriff auf Unternehmensdaten gestatten, da zuvor ermittelt wurde, dass der Benutzer für Intune lizenziert ist.</span><span class="sxs-lookup"><span data-stu-id="31d69-490">The app should not allow access to corporate in this state, since it was previously determined that the user is licensed for Intune.</span></span>|
| <span data-ttu-id="31d69-491">WRONG_USER</span><span class="sxs-lookup"><span data-stu-id="31d69-491">WRONG_USER</span></span> | <span data-ttu-id="31d69-492">Nur ein Benutzer pro Gerät kann eine App mit dem MAM-Dienst registrieren.</span><span class="sxs-lookup"><span data-stu-id="31d69-492">Only one user per device can enroll an app with the MAM service.</span></span>  <span data-ttu-id="31d69-493">Zunächst muss die Registrierung für alle registrierten Apps aufgehoben werden, damit die Registrierung als anderer Benutzer erfolgreich durchgeführt werden kann.</span><span class="sxs-lookup"><span data-stu-id="31d69-493">In order to enroll successfully as a different user, all enrolled apps must be unenrolled first.</span></span>  <span data-ttu-id="31d69-494">Andernfalls muss diese App als primärer Benutzer registriert werden.</span><span class="sxs-lookup"><span data-stu-id="31d69-494">Otherwise, this app must enroll as the primary user.</span></span>  <span data-ttu-id="31d69-495">Diese Überprüfung erfolgt nach der Lizenzprüfung, daher sollte der Zugriff des Benutzers auf Unternehmensdaten blockiert werden, bis die App erfolgreich registriert wurde.</span><span class="sxs-lookup"><span data-stu-id="31d69-495">This check happens after the license check, so the user should be blocked from accessing corporate data until the app is successfully enrolled.</span></span>|
| <span data-ttu-id="31d69-496">UNENROLLMENT_SUCCEEDED</span><span class="sxs-lookup"><span data-stu-id="31d69-496">UNENROLLMENT_SUCCEEDED</span></span> | <span data-ttu-id="31d69-497">Die Aufhebung der Registrierung war erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="31d69-497">Unenrollment was successful.</span></span>|
| <span data-ttu-id="31d69-498">UNENROLLMENT_FAILED</span><span class="sxs-lookup"><span data-stu-id="31d69-498">UNENROLLMENT_FAILED</span></span> | <span data-ttu-id="31d69-499">Fehler bei der Anforderung zur Aufhebung der Registrierung.</span><span class="sxs-lookup"><span data-stu-id="31d69-499">The unenrollment request failed.</span></span>  <span data-ttu-id="31d69-500">Weitere Details finden Sie in den Geräteprotokollen.</span><span class="sxs-lookup"><span data-stu-id="31d69-500">Further details can be found in the device logs.</span></span> |
| <span data-ttu-id="31d69-501">PENDING (AUSSTEHEND)</span><span class="sxs-lookup"><span data-stu-id="31d69-501">PENDING</span></span> | <span data-ttu-id="31d69-502">Der anfängliche Registrierungsversuch für den Benutzer wird ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="31d69-502">The initial enrollment attempt for the user is in progress.</span></span>  <span data-ttu-id="31d69-503">Die App kann den Zugriff auf Unternehmensdaten blockieren, bis das Registrierungsergebnis bekannt ist, aber sie ist dazu nicht verpflichtet.</span><span class="sxs-lookup"><span data-stu-id="31d69-503">The app can block access to corporate data until the enrollment result is known, but is not required to do so.</span></span> |
| <span data-ttu-id="31d69-504">COMPANY_PORTAL_REQUIRED</span><span class="sxs-lookup"><span data-stu-id="31d69-504">COMPANY_PORTAL_REQUIRED</span></span> | <span data-ttu-id="31d69-505">Der Benutzer ist für Intune lizenziert, aber die App kann nicht registriert werden, bis die Unternehmensportal-App auf dem Gerät installiert ist.</span><span class="sxs-lookup"><span data-stu-id="31d69-505">The user is licensed for Intune, but the app cannot be enrolled until the Company Portal app is installed on the device.</span></span> <span data-ttu-id="31d69-506">Das Intune App SDK versucht, den Zugriff auf die App für den angegebenen Benutzer zu blockieren und ihn zur Installation der Unternehmensportal-App zu bewegen (siehe nachfolgende Details).</span><span class="sxs-lookup"><span data-stu-id="31d69-506">The Intune App SDK will attempt to block access to the app for the given user and direct them to install the Company Portal app (see below for details).</span></span> |


### <a name="company-portal-requirement-prompt-override-optional"></a><span data-ttu-id="31d69-507">Aufforderung zur Unternehmensportalanforderung außer Kraft setzen (optional)</span><span class="sxs-lookup"><span data-stu-id="31d69-507">Company Portal requirement prompt override (optional)</span></span>

<span data-ttu-id="31d69-508">Wenn das Ergebnis `COMPANY_PORTAL_REQUIRED` zurückgegeben wird, blockiert das SDK die Verwendung von Aktivitäten, die die Identität verwenden, für die die Registrierung angefordert wurde.</span><span class="sxs-lookup"><span data-stu-id="31d69-508">If the `COMPANY_PORTAL_REQUIRED` Result is received, the SDK will block use of activities that use the identity for which enrollment was requested.</span></span> <span data-ttu-id="31d69-509">Stattdessen führt das SDK dazu, dass diese Aktivitäten eine Aufforderung zum Herunterladen des Unternehmensportals anzeigen.</span><span class="sxs-lookup"><span data-stu-id="31d69-509">Instead, the SDK will cause those activities to display a prompt to download the Company Portal.</span></span> <span data-ttu-id="31d69-510">Wenn Sie dieses Verhalten in Ihrer App verhindern möchten, können die Aktivitäten `MAMActivity.onMAMCompanyPortalRequired` implementieren.</span><span class="sxs-lookup"><span data-stu-id="31d69-510">If you want to prevent this behavior in your app, activities may implement `MAMActivity.onMAMCompanyPortalRequired`.</span></span>

<span data-ttu-id="31d69-511">Diese Methode wird aufgerufen, bevor das SDK seine standardmäßig blockierende Benutzeroberfläche anzeigt.</span><span class="sxs-lookup"><span data-stu-id="31d69-511">This method is called before the SDK displays its default blocking UI.</span></span> <span data-ttu-id="31d69-512">Wenn die App die Aktivitätsidentität ändert oder die Registrierung des Benutzers aufhebt, der die Registrierung versucht hat, wird die Aktivität nicht vom SDK blockiert.</span><span class="sxs-lookup"><span data-stu-id="31d69-512">If the app changes the activity identity or unregisters the user who attempted to enroll, the SDK will not block the activity.</span></span> <span data-ttu-id="31d69-513">In dieser Situation ist es Aufgabe der App, den Verlust von Unternehmensdaten zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="31d69-513">In this situation, it is up to the app to avoid leaking corporate data.</span></span>

### <a name="notifications"></a><span data-ttu-id="31d69-514">Benachrichtigungen</span><span class="sxs-lookup"><span data-stu-id="31d69-514">Notifications</span></span>

<span data-ttu-id="31d69-515">Es wurde eine neue Art von `MAMNotification` hinzugefügt, um die App darüber zu informieren, dass die Registrierungsanforderung abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="31d69-515">A new type of `MAMNotification` has been added in order to inform the app that the enrollment request has completed.</span></span>  <span data-ttu-id="31d69-516">`MAMEnrollmentNotification` wird über die `MAMNotificationReceiver`-Schnittstelle empfangen, wie im Abschnitt [Registrieren für Benachrichtigungen vom SDK](#register-for-notifications-from-the-sdk) beschrieben.</span><span class="sxs-lookup"><span data-stu-id="31d69-516">The `MAMEnrollmentNotification` will be received through the `MAMNotificationReceiver` interface as described in the [Register for notifications from the SDK](#register-for-notifications-from-the-sdk) section.</span></span>

```java
public interface MAMEnrollmentNotification extends MAMUserNotification {
    MAMEnrollmentManager.Result getEnrollmentResult();
}

```

<span data-ttu-id="31d69-517">Die `getEnrollmentResult()`-Methode gibt das Ergebnis der Registrierungsanforderung zurück.</span><span class="sxs-lookup"><span data-stu-id="31d69-517">The `getEnrollmentResult()` method returns the result of the enrollment request.</span></span>  <span data-ttu-id="31d69-518">Da `MAMUserNotification` von `MAMEnrollmentNotification` erweitert wird, ist die Identität des Benutzers ebenfalls verfügbar, für den die Registrierung versucht wurde.</span><span class="sxs-lookup"><span data-stu-id="31d69-518">Since `MAMEnrollmentNotification` extends `MAMUserNotification`, the identity of the user for whom the enrollment was attempted is also available.</span></span> <span data-ttu-id="31d69-519">Die App muss die `MAMNotificationReceiver`-Schnittstelle implementieren, um diese Benachrichtigungen zu erhalten. Dieser Vorgang wird ausführlich im Abschnitt [Registrieren für Benachrichtigungen vom SDK](#Register-for-notifications-from-the-SDK) beschrieben.</span><span class="sxs-lookup"><span data-stu-id="31d69-519">The app must implement the `MAMNotificationReceiver` interface to receive these notifications, detailed in the [Register for notifications from the SDK](#Register-for-notifications-from-the-SDK) section.</span></span>

<span data-ttu-id="31d69-520">Der Kontostatus für den registrierten Benutzer kann sich ändern, wenn eine Registrierungsbenachrichtigung empfangen wird, aber in einigen Fällen (wenn z. B. eine `AUTHORIZATION_NEEDED`-Benachrichtigung nach einem informativeren Ergebnis wie `WRONG_USER` empfangen wird, bleibt das informativere Ergebnis als Kontostatus erhalten) wird der Status nicht geändert.</span><span class="sxs-lookup"><span data-stu-id="31d69-520">The registered user account's status may change when an enrollment notification is received, but it will not change in some cases (e.g. if `AUTHORIZATION_NEEDED` notification is received after a more informative result such as `WRONG_USER`, the more informative result will be maintained as the account's status)</span></span>


## <a name="protecting-backup-data"></a><span data-ttu-id="31d69-521">Schutz von Sicherungsdaten</span><span class="sxs-lookup"><span data-stu-id="31d69-521">Protecting Backup data</span></span>

<span data-ttu-id="31d69-522">Seit Android Marshmallow (API 23) bietet Android einer App zwei Möglichkeiten zum Sichern ihrer Daten.</span><span class="sxs-lookup"><span data-stu-id="31d69-522">As of Android Marshmallow (API 23), Android has two ways for an app to back up its data.</span></span> <span data-ttu-id="31d69-523">Jede Option ist für Ihre App verfügbar und erfordert andere Schritte, um sicherzustellen, dass Intune-Datenschutz ordnungsgemäß implementiert wird.</span><span class="sxs-lookup"><span data-stu-id="31d69-523">Each option is available to your app and requires different steps to ensure that Intune data protection is correctly implemented.</span></span> <span data-ttu-id="31d69-524">In der folgenden Tabelle können Sie sich einen Überblick über die entsprechenden Aktionen verschaffen, die für ein korrektes Verhalten beim Datenschutz erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="31d69-524">You can review the table below on corresponding actions required for correct data protection behavior.</span></span>  <span data-ttu-id="31d69-525">Mehr über die Sicherungsmethoden erfahren Sie im [Android-API-Handbuch](http://developer.android.com/guide/topics/data/backup.html).</span><span class="sxs-lookup"><span data-stu-id="31d69-525">You can read more about the backup methods in the [Android API guide](http://developer.android.com/guide/topics/data/backup.html).</span></span>

### <a name="auto-backup-for-apps"></a><span data-ttu-id="31d69-526">Automatische Sicherung für Apps</span><span class="sxs-lookup"><span data-stu-id="31d69-526">Auto Backup for Apps</span></span>

<span data-ttu-id="31d69-527">Android hat begonnen, [automatische vollständige Sicherungen](https://developer.android.com/guide/topics/data/autobackup.html) auf Google Drive für Apps auf Android Marshmallow-Geräten unabhängig von der Ziel-API der App anzubieten.</span><span class="sxs-lookup"><span data-stu-id="31d69-527">Android began offering [automatic full backups](https://developer.android.com/guide/topics/data/autobackup.html) to Google Drive for apps on Android Marshmallow devices, regardless of the app's target API.</span></span> <span data-ttu-id="31d69-528">Wenn Sie in „AndroidManifest.xml“ explizit für `android:allowBackup` **false** festlegen, steht Ihre App niemals für Sicherungen von Android in der Warteschlange, und „Unternehmensdaten“ bleiben innerhalb der App.</span><span class="sxs-lookup"><span data-stu-id="31d69-528">In your AndroidManifest.xml, if you explicitly set `android:allowBackup` to **false**, then your app will never be queued for backups by Android and "corporate" data will stay within the app.</span></span> <span data-ttu-id="31d69-529">In diesem Fall ist keine weitere Aktion erforderlich.</span><span class="sxs-lookup"><span data-stu-id="31d69-529">In this case, no further action is necessary.</span></span>

<span data-ttu-id="31d69-530">Allerdings ist das `android:allowBackup`-Attribut standardmäßig auf „true“ festgelegt – auch wenn `android:allowBackup` nicht in der Manifestdatei angegeben ist.</span><span class="sxs-lookup"><span data-stu-id="31d69-530">However, by default the `android:allowBackup` attribute is set to true, even if `android:allowBackup` isn't specified in the manifest file.</span></span> <span data-ttu-id="31d69-531">Dies bedeutet, dass alle App-Daten automatisch im Google Drive-Konto des Benutzers gesichert werden – ein Standardverhalten, das ein **Datenverlustrisiko** darstellt.</span><span class="sxs-lookup"><span data-stu-id="31d69-531">This means all app data is automatically backed up to the user's Google Drive account, a default behavior that poses a **data leak risk**.</span></span> <span data-ttu-id="31d69-532">Daher erfordert das SDK die unten beschriebenen Änderungen, um sicherzustellen, dass Datenschutz angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="31d69-532">Therefore, the SDK requires the changes outlined below to ensure that data protection is applied.</span></span>  <span data-ttu-id="31d69-533">Es ist wichtig, die folgenden Richtlinien zu befolgen, um Kundendaten angemessen zu schützen, wenn Ihre App auf Android Marshmallow-Geräten ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="31d69-533">It is important to follow the guidelines  below to protect customer data properly if you want your app to run on Android Marshmallow devices.</span></span>  

<span data-ttu-id="31d69-534">Mit Intune können Sie alle [Funktionen für automatische Sicherung](https://developer.android.com/guide/topics/data/autobackup.html) verwenden, die bei Android verfügbar sind, einschließlich der Möglichkeit, benutzerdefinierte Regeln in XML zu definieren, jedoch müssen Sie die folgenden Schritte befolgen, um Ihre Daten zu sichern:</span><span class="sxs-lookup"><span data-stu-id="31d69-534">Intune allows you to utilize all the [Auto Backup features](https://developer.android.com/guide/topics/data/autobackup.html) available from Android, including the ability to define custom rules in XML, but you must follow the steps below to secure your data:</span></span>

1. <span data-ttu-id="31d69-535">Wenn Ihre App **keinen** benutzerdefinierten BackupAgent verwendet, verwenden Sie die Standardeinstellung MAMBackupAgent, um automatische vollständige Sicherungen zu ermöglichen, die mit Intune-Richtlinien kompatibel sind.</span><span class="sxs-lookup"><span data-stu-id="31d69-535">If your app does **not** use its own custom BackupAgent, use the default MAMBackupAgent to allow for automatic full backups that are Intune policy compliant.</span></span> <span data-ttu-id="31d69-536">In diesem Fall können Sie das Manifestattribut `android:fullBackupOnly` ignorieren, da es nicht für Ihren Sicherungs-Agent gilt.</span><span class="sxs-lookup"><span data-stu-id="31d69-536">If you do this, you can ignore the `android:fullBackupOnly` manifest attribute, as it’s not applicable for our backup agent.</span></span> <span data-ttu-id="31d69-537">Fügen Sie Folgendes in das App-Manifest ein:</span><span class="sxs-lookup"><span data-stu-id="31d69-537">Place the following in the app manifest:</span></span>

    ```xml
android:backupAgent="com.microsoft.intune.mam.client.app.backup.MAMDefaultBackupAgent"
    ```


2. <span data-ttu-id="31d69-538">**[Optional]** Wenn Sie einen optionalen benutzerdefinierten BackupAgent implementiert haben, müssen Sie sicherstellen, dass Sie MAMBackupAgent oder MAMBackupAgentHelper verwenden.</span><span class="sxs-lookup"><span data-stu-id="31d69-538">**[Optional]** If you implemented an optional custom BackupAgent, you need to make sure to use MAMBackupAgent or MAMBackupAgentHelper.</span></span> <span data-ttu-id="31d69-539">Weitere Informationen finden Sie in den folgenden Abschnitten.</span><span class="sxs-lookup"><span data-stu-id="31d69-539">See the following sections.</span></span> <span data-ttu-id="31d69-540">Wechseln Sie ggf. zu **MAMDefaultFullBackupAgent** von Intune (in Schritt 1 beschrieben), der eine einfache Sicherung für Android M und höher bietet.</span><span class="sxs-lookup"><span data-stu-id="31d69-540">Consider switching to using Intune's **MAMDefaultFullBackupAgent** (described in step 1) which provides easy back up on Android M and above.</span></span>

3. <span data-ttu-id="31d69-541">Wenn Sie festlegen, welche Art von vollständiger Sicherung Ihre App erhalten soll (ungefiltert, gefiltert oder keine), müssen Sie das Attribut `android:fullBackupContent` auf „true“, „false“ oder eine XML-Ressource in Ihrer App festlegen.</span><span class="sxs-lookup"><span data-stu-id="31d69-541">When you decide which type of full backup your app should receive (unfiltered, filtered, or none) you'll need to set the attribute `android:fullBackupContent`  to true, false, or an XML resource in your app.</span></span>

4. <span data-ttu-id="31d69-542">Dann _**müssen**_ Sie das, was Sie in `android:fullBackupContent` eingefügt haben, in ein Metadatentag namens `com.microsoft.intune.mam.FullBackupContent` in das Manifest kopieren.</span><span class="sxs-lookup"><span data-stu-id="31d69-542">Then, you _**must**_ copy whatever you put into `android:fullBackupContent` into a metadata tag named `com.microsoft.intune.mam.FullBackupContent` in the manifest.</span></span>

    <span data-ttu-id="31d69-543">**Beispiel 1**: Wenn Ihre App vollständige Sicherungen ohne Ausschlüsse erstellen soll, legen Sie sowohl das `android:fullBackupContent`-Attribut als auch das `com.microsoft.intune.mam.FullBackupContent`-Metadatentag auf **true** fest:</span><span class="sxs-lookup"><span data-stu-id="31d69-543">**Example 1**: If you want your app to have full backups without exclusions, set both the `android:fullBackupContent` attribute and `com.microsoft.intune.mam.FullBackupContent` metadata tag to **true**:</span></span>

    ```xml
    android:fullBackupContent="true"
    ...
    <meta-data android:name="com.microsoft.intune.mam.FullBackupContent" android:value="true" />  
    ```

    <span data-ttu-id="31d69-544">**Beispiel 2**: Wenn Ihre App ihren benutzerdefinierten BackupAgent verwenden und vollständige, zu Intune-Richtlinien konforme, automatische Sicherungen deaktivieren soll, müssen Sie sowohl das Attribut und das Metadatentag auf **false** festlegen:</span><span class="sxs-lookup"><span data-stu-id="31d69-544">**Example 2**: If you want your app to use its custom BackupAgent and opt out of full, Intune policy compliant, automatic backups, you must set the attribute and metadata tag to **false**:</span></span>

    ```xml
    android:fullBackupContent="false"
    ...
    <meta-data android:name="com.microsoft.intune.mam.FullBackupContent" android:value="false" />  
    ```

    <span data-ttu-id="31d69-545">**Beispiel 3**: Wenn Ihre App vollständige Sicherungen gemäß Ihrer in einer XML-Datei definierten benutzerdefinierten Regeln erhalten soll, legen Sie das Attribut und das Metadatentag auf dieselbe XML-Ressource fest:</span><span class="sxs-lookup"><span data-stu-id="31d69-545">**Example 3**: If you want your app to have full backups according to your custom rules defined in an XML file, please set the attribute and metadata tag to the same XML resource:</span></span>

    ```xml
    android:fullBackupContent="@xml/my_scheme"
    ...
    <meta-data android:name="com.microsoft.intune.mam.FullBackupContent" android:resource="@xml/my_scheme" />  
    ```


### <a name="keyvalue-backup"></a><span data-ttu-id="31d69-546">Schlüssel/Wert-Sicherung</span><span class="sxs-lookup"><span data-stu-id="31d69-546">Key/Value Backup</span></span>

<span data-ttu-id="31d69-547">Die Option [Schlüssel/Wert-Sicherung](https://developer.android.com/guide/topics/data/keyvaluebackup.html) ist für alle APIs ab Version 8 verfügbar, und sie lädt App-Daten zum [Android Backup Service](https://developer.android.com/google/backup/index.html) hoch.</span><span class="sxs-lookup"><span data-stu-id="31d69-547">The [Key/Value Backup](https://developer.android.com/guide/topics/data/keyvaluebackup.html) option is available to all APIs 8+ and uploads app data to the [Android Backup Service](https://developer.android.com/google/backup/index.html).</span></span> <span data-ttu-id="31d69-548">Die Datenmenge pro Benutzer Ihrer App ist auf 5 MB beschränkt.</span><span class="sxs-lookup"><span data-stu-id="31d69-548">The amount of data per user of your app is limited to 5MB.</span></span> <span data-ttu-id="31d69-549">Wenn Sie die Schlüssel/Wert-Sicherung verwenden, müssen Sie **BackupAgentHelper** oder **BackupAgent** verwenden.</span><span class="sxs-lookup"><span data-stu-id="31d69-549">If you use Key/Value Backup, you must use a **BackupAgentHelper** or a **BackupAgent**.</span></span>

### <a name="backupagenthelper"></a><span data-ttu-id="31d69-550">BackupAgentHelper</span><span class="sxs-lookup"><span data-stu-id="31d69-550">BackupAgentHelper</span></span>

<span data-ttu-id="31d69-551">„BackupAgentHelper“ ist einfacher zu implementieren als „BackupAgent“, was systemeigene Android-Funktionalität und Intune MAM-Integration anbelangt.</span><span class="sxs-lookup"><span data-stu-id="31d69-551">BackupAgentHelper is easier to implement than BackupAgent both in terms of native Android functionality and Intune MAM integration.</span></span> <span data-ttu-id="31d69-552">„BackupAgentHelper“ ermöglicht dem Entwickler, ganze Dateien und gemeinsam genutzte Einstellungen bei **FileBackupHelper** bzw. **SharedPreferencesBackupHelper** zu registrieren, die bei Erstellung dann „BackupAgentHelper“ hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="31d69-552">BackupAgentHelper allows the developer to register entire files and shared preferences to a **FileBackupHelper** and **SharedPreferencesBackupHelper** (respectively) which are then added to the BackupAgentHelper upon creation.</span></span> <span data-ttu-id="31d69-553">Führen Sie die nachstehenden Schritte aus, um „BackupAgentHelper“ mit Intune MAM zu verwenden:</span><span class="sxs-lookup"><span data-stu-id="31d69-553">Follow the steps below to use a BackupAgentHelper with Intune MAM:</span></span>

1. <span data-ttu-id="31d69-554">Befolgen Sie die Android-Anleitung zum [Erweitern von BackupAgentHelper](https://developer.android.com/guide/topics/data/keyvaluebackup.html#BackupAgentHelper), um die Sicherung mehrerer Identitäten mit „BackupAgentHelper“ zu nutzen.</span><span class="sxs-lookup"><span data-stu-id="31d69-554">To utilize multi-identity backup with a BackupAgentHelper, follow the Android guide to [Extending BackupAgentHelper](https://developer.android.com/guide/topics/data/keyvaluebackup.html#BackupAgentHelper).</span></span>

2. <span data-ttu-id="31d69-555">Lassen Sie die MAM-Entsprechung von „BackupAgentHelper“, „FileBackupHelper“ und „SharedPreferencesBackupHelper“ von Ihrer Klasse erweitern.</span><span class="sxs-lookup"><span data-stu-id="31d69-555">Have your class extend the MAM equivalent of BackupAgentHelper, FileBackupHelper, and SharedPreferencesBackupHelper.</span></span>

|<span data-ttu-id="31d69-556">Android-Klasse</span><span class="sxs-lookup"><span data-stu-id="31d69-556">Android class</span></span> | <span data-ttu-id="31d69-557">MAM-Entsprechung</span><span class="sxs-lookup"><span data-stu-id="31d69-557">MAM equivalent</span></span> |
|--|--|
|<span data-ttu-id="31d69-558">BackupAgentHelper</span><span class="sxs-lookup"><span data-stu-id="31d69-558">BackupAgentHelper</span></span> |<span data-ttu-id="31d69-559">MAMBackupAgentHelper</span><span class="sxs-lookup"><span data-stu-id="31d69-559">MAMBackupAgentHelper</span></span> |
|<span data-ttu-id="31d69-560">FileBackupHelper</span><span class="sxs-lookup"><span data-stu-id="31d69-560">FileBackupHelper</span></span> | <span data-ttu-id="31d69-561">MAMFileBackupHelper</span><span class="sxs-lookup"><span data-stu-id="31d69-561">MAMFileBackupHelper</span></span>
|<span data-ttu-id="31d69-562">SharedPreferencesBackupHelper</span><span class="sxs-lookup"><span data-stu-id="31d69-562">SharedPreferencesBackupHelper</span></span>| <span data-ttu-id="31d69-563">MAMSharedPreferencesBackupHelper</span><span class="sxs-lookup"><span data-stu-id="31d69-563">MAMSharedPreferencesBackupHelper</span></span>|

<span data-ttu-id="31d69-564">Das Befolgen dieser Richtlinien führt zu einer erfolgreichen Sicherung und Wiederherstellung mehrerer Identitäten.</span><span class="sxs-lookup"><span data-stu-id="31d69-564">Following these guidelines will lead to a successful multi-identity backup and restore.</span></span>

### <a name="backupagent"></a><span data-ttu-id="31d69-565">BackupAgent</span><span class="sxs-lookup"><span data-stu-id="31d69-565">BackupAgent</span></span>

<span data-ttu-id="31d69-566">„BackupAgent“ ermöglicht Ihnen die explizitere Angabe der zu sichernden Daten.</span><span class="sxs-lookup"><span data-stu-id="31d69-566">A BackupAgent allows you to be much more explicit about what data is backed up.</span></span> <span data-ttu-id="31d69-567">Da der Entwickler maßgeblich für die Implementierung verantwortlich ist, sind weitere Schritte erforderlich, um den ordnungsgemäßen Datenschutz von Intune sicherzustellen.</span><span class="sxs-lookup"><span data-stu-id="31d69-567">Because the developer is fairly responsible for the implementation, there are more steps required to ensure appropriate data protection from Intune.</span></span> <span data-ttu-id="31d69-568">Da die Arbeit größtenteils von Ihnen als Entwickler zu leisten ist, ist die Intune-Integration etwas komplizierter.</span><span class="sxs-lookup"><span data-stu-id="31d69-568">Since most of the work is pushed onto you, the developer, Intune integration is slightly more involved.</span></span>

<span data-ttu-id="31d69-569">**MAM-Integration**:</span><span class="sxs-lookup"><span data-stu-id="31d69-569">**Integrate MAM:**</span></span>

1. <span data-ttu-id="31d69-570">Lesen Sie die Android-Anleitung für die [Schlüssel/Wert-Sicherung](https://developer.android.com/guide/topics/data/keyvaluebackup.html) und insbesondere zum [Erweitern von BackupAgent](https://developer.android.com/guide/topics/data/keyvaluebackup.html#BackupAgent) sorgfältig durch, um sicherzustellen, dass Ihre BackupAgent-Implementierung den Android-Richtlinien folgt.</span><span class="sxs-lookup"><span data-stu-id="31d69-570">Please carefully read the Android guide for [Key/Value Backup](https://developer.android.com/guide/topics/data/keyvaluebackup.html) and specifically [Extending BackupAgent](https://developer.android.com/guide/topics/data/keyvaluebackup.html#BackupAgent) to ensure your BackupAgent implementation follows Android guidelines.</span></span>

2. <span data-ttu-id="31d69-571">Lassen Sie `MAMBackupAgent` von Ihrer Klasse erweitern.</span><span class="sxs-lookup"><span data-stu-id="31d69-571">Have your class extend `MAMBackupAgent`.</span></span>

<span data-ttu-id="31d69-572">**Sicherung mehrerer Identitäten**:</span><span class="sxs-lookup"><span data-stu-id="31d69-572">**Multi-identity Backup:**</span></span>

1. <span data-ttu-id="31d69-573">Bevor Sie mit der Datensicherung beginnen, prüfen Sie, ob die **Sicherung der zu sichernden Dateien oder Datenpuffer in Szenarien mit mehreren Identitäten tatsächlich vom IT-Administrator genehmigt ist**.</span><span class="sxs-lookup"><span data-stu-id="31d69-573">Before beginning your backup, check that the files or data buffers you plan to back up are indeed **permitted by the IT administrator to be backed up** in multi-identity scenarios.</span></span> <span data-ttu-id="31d69-574">Ihnen wurde die `isBackupAllowed`-Funktion in `MAMFileProtectionManager` und `MAMDataProtectionManager` bereitgestellt, um dies zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="31d69-574">We provide you with the `isBackupAllowed` function in `MAMFileProtectionManager` and `MAMDataProtectionManager` to determine this.</span></span> <span data-ttu-id="31d69-575">Wenn die Sicherung der Datei oder des Datenpuffers nicht zulässig ist, sollten Sie sie nicht in Ihre Sicherung einbeziehen.</span><span class="sxs-lookup"><span data-stu-id="31d69-575">If the file or data buffer is not allowed to be backed up, then you should not continue including it in your backup.</span></span>

2. <span data-ttu-id="31d69-576">Wenn während der Sicherung die Identitäten der in Schritt 1 überprüften Dateien gesichert werden sollen, müssen Sie `backupMAMFileIdentity(BackupDataOutput data, File … files)` mit den Dateien aufrufen, aus denen Sie Daten extrahieren möchten.</span><span class="sxs-lookup"><span data-stu-id="31d69-576">At some point during your backup, if you want to back up the identities for the files you checked in step 1, you must call `backupMAMFileIdentity(BackupDataOutput data, File … files)` with the files from which you plan to extract data.</span></span> <span data-ttu-id="31d69-577">So werden automatisch neue Sicherungsentitäten für Sie erstellt und in `BackupDataOutput` geschrieben.</span><span class="sxs-lookup"><span data-stu-id="31d69-577">This will automatically create new backup entities and write them to the `BackupDataOutput` for you.</span></span> <span data-ttu-id="31d69-578">Diese Entitäten werden bei der Wiederherstellung automatisch genutzt.</span><span class="sxs-lookup"><span data-stu-id="31d69-578">These entities will be automatically consumed upon restore.</span></span>

<span data-ttu-id="31d69-579">**Wiederherstellung mehrerer Identitäten**:</span><span class="sxs-lookup"><span data-stu-id="31d69-579">**Multi-identity Restore:**</span></span>

<span data-ttu-id="31d69-580">Die Anleitung zur Datensicherung gibt einen allgemeinen Algorithmus für die Wiederherstellung der Daten Ihrer Anwendung an und stellt im Abschnitt [Erweitern von BackupAgent](https://developer.android.com/guide/topics/data/keyvaluebackup.html#BackupAgent) ein Codebeispiel bereit.</span><span class="sxs-lookup"><span data-stu-id="31d69-580">The Data Backup guide specifies a general algorithm for restoring your application’s data and provides a code sample in the [Extending BackupAgent](https://developer.android.com/guide/topics/data/keyvaluebackup.html#BackupAgent) section.</span></span> <span data-ttu-id="31d69-581">Sie müssen der in diesem Codebeispiel bereitgestellten allgemeinen Struktur hinsichtlich der folgenden Punkte besonders aufmerksam folgen, damit die Wiederherstellung mehrerer Identitäten erfolgreich ausgeführt wird:</span><span class="sxs-lookup"><span data-stu-id="31d69-581">In order to have a successful multi-identity restore, you must follow the general structure provided in this code sample with special attention to the following:</span></span>

1.  <span data-ttu-id="31d69-582">Sie müssen eine `while(data.readNextHeader())`*-Schleife verwenden, um die Sicherungsentitäten zu durchlaufen.</span><span class="sxs-lookup"><span data-stu-id="31d69-582">You must utilize a `while(data.readNextHeader())`* loop to go through the backup entities.</span></span>

2.  <span data-ttu-id="31d69-583">Sie müssen `data.skipEntityData()`* aufrufen, wenn `data.getKey()`* nicht mit dem Schlüssel übereinstimmt, den Sie in `onBackup` erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="31d69-583">You must call `data.skipEntityData()`* if `data.getKey()`* does not match the key you wrote in `onBackup`.</span></span> <span data-ttu-id="31d69-584">Wenn Sie diesen Schritt nicht ausführen, können Ihre Wiederherstellungen möglicherweise nicht erfolgreich durchgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="31d69-584">Without performing this step, your restores may not succeed.</span></span>

3.  <span data-ttu-id="31d69-585">Vermeiden Sie eine Rückgabe während der Verarbeitung von Sicherungsentitäten im `while(data.readNextHeader())`*-Konstrukt, da die automatisch geschriebenen Entitäten sonst verloren gehen.</span><span class="sxs-lookup"><span data-stu-id="31d69-585">Avoid returning while consuming backup entities in the `while(data.readNextHeader())`* construct, as the entities we automatically write will be lost.</span></span>

* <span data-ttu-id="31d69-586">Dabei gibt `data` den Namen der lokalen Variablen für **BackupDataInput** an, die bei der Wiederherstellung an Ihre App übergeben wird.</span><span class="sxs-lookup"><span data-stu-id="31d69-586">Where `data` is the local variable name for the **BackupDataInput** that is passed to your app upon restore.</span></span>

## <a name="multi-identity-optional"></a><span data-ttu-id="31d69-587">Mehrere Identitäten (optional)</span><span class="sxs-lookup"><span data-stu-id="31d69-587">Multi-identity (optional)</span></span>

### <a name="overview"></a><span data-ttu-id="31d69-588">Übersicht</span><span class="sxs-lookup"><span data-stu-id="31d69-588">Overview</span></span>
<span data-ttu-id="31d69-589">Standardmäßig wendet das Intune App SDK Richtlinien auf die gesamte App an.</span><span class="sxs-lookup"><span data-stu-id="31d69-589">By default, the Intune App SDK will apply policy to the app as a whole.</span></span> <span data-ttu-id="31d69-590">Mehrere Identitäten sind ein optionales Feature von Intune zum Schutz von Apps, das aktiviert werden kann, um die identitätsbezogene Anwendung von Richtlinien zu ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="31d69-590">Multi-identity is an optional Intune app protection feature which can be enabled to allow policy to be applied on a per-identity level.</span></span> <span data-ttu-id="31d69-591">Dies erfordert eine deutlich stärkere Beteiligung der App als andere Features zum Schutz von Apps.</span><span class="sxs-lookup"><span data-stu-id="31d69-591">This requires significantly more app participation than other app protection features.</span></span>

<span data-ttu-id="31d69-592">Die App *muss* das SDK informieren, wenn sie die Änderung der aktiven Identität beabsichtigt.</span><span class="sxs-lookup"><span data-stu-id="31d69-592">The app *must* inform the SDK when it intends to change the active identity.</span></span> <span data-ttu-id="31d69-593">In einigen Fällen benachrichtigt das SDK seinerseits die App, wenn eine Änderung der Identität erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="31d69-593">In some cases, the SDK will also notify the app when an identity change is required.</span></span> <span data-ttu-id="31d69-594">In den meisten Fällen kann MAM jedoch nicht wissen, welche Daten auf der Benutzeroberfläche angezeigt oder in einem Thread zu einem bestimmten Zeitpunkt verwendet werden. So verwendet der Dienst die App, um die korrekte Identität festzulegen, um Datenverlust zu vermeiden.</span><span class="sxs-lookup"><span data-stu-id="31d69-594">In most cases, however, MAM cannot know what data is being displayed in the UI or used on a thread at a given time and relies on the app to set the correct identity in order to avoid data leak.</span></span> <span data-ttu-id="31d69-595">In den folgenden Abschnitten wird auf einige bestimmte Szenarios hingewiesen, die App-Aktionen erfordern.</span><span class="sxs-lookup"><span data-stu-id="31d69-595">In the sections that follow, some particular scenarios which require app action will be called out.</span></span>

> [!NOTE]
>  <span data-ttu-id="31d69-596">Fehlende korrekte App-Teilnahme kann zu Datenverlusten und anderen Sicherheitsproblemen führen.</span><span class="sxs-lookup"><span data-stu-id="31d69-596">A lack of the correct app participation can result in data leaks and other security issues.</span></span>

<span data-ttu-id="31d69-597">Sobald der Benutzer das Gerät oder die App registriert, registriert das SDK die dabei verwendete Identität und betrachtet sie als die primäre, von Intune verwaltete Identität.</span><span class="sxs-lookup"><span data-stu-id="31d69-597">Once the user enrolls the device or the app, the SDK registers this identity and considers it the primary Intune managed identity.</span></span> <span data-ttu-id="31d69-598">Andere Benutzer der App werden als nicht verwaltet mit uneingeschränkten Richtlinieneinstellungen behandelt.</span><span class="sxs-lookup"><span data-stu-id="31d69-598">Other users in the app will be treated as unmanaged, with unrestricted policy settings.</span></span>

> [!NOTE]
> <span data-ttu-id="31d69-599">Aktuell wird nur eine von Intune verwaltete Identität pro Gerät unterstützt.</span><span class="sxs-lookup"><span data-stu-id="31d69-599">Currently, only one Intune managed identity is supported per device.</span></span>

<span data-ttu-id="31d69-600">Beachten Sie, dass eine Identität einfach in Form einer Zeichenfolge definiert wird.</span><span class="sxs-lookup"><span data-stu-id="31d69-600">Note that an identity is simply defined as a string.</span></span> <span data-ttu-id="31d69-601">Bei Identitäten werden **Groß- und Kleinschreibung** nicht unterschieden, und Anforderungen einer Identität beim SDK werden möglicherweise nicht mit der gleichen Groß-/Kleinschreibung zurückgegeben, die ursprünglich beim Festlegen der Identität verwendet worden war.</span><span class="sxs-lookup"><span data-stu-id="31d69-601">Identities are **case-insensitive**, and requests to the SDK for an identity may not return the same casing that was originally used when setting the identity.</span></span>

### <a name="enabling-multi-identity"></a><span data-ttu-id="31d69-602">Aktivieren mehrerer Identitäten</span><span class="sxs-lookup"><span data-stu-id="31d69-602">Enabling Multi-identity</span></span>

<span data-ttu-id="31d69-603">Standardmäßig werden alle Apps als Einzelidentitäts-Apps betrachtet.</span><span class="sxs-lookup"><span data-stu-id="31d69-603">By default, all apps are considered to be single-identity apps.</span></span> <span data-ttu-id="31d69-604">Sie können eine App entsprechen deklarieren, dass sie mit mehreren Identitäten kompatibel ist, indem Sie die folgenden Metadaten in die Datei „AndroidManifest.xml“ einfügen.</span><span class="sxs-lookup"><span data-stu-id="31d69-604">You can declare an app to be multi-identity aware by placing the following metadata in AndroidManifest.xml.</span></span>

```xml
  <meta-data
    android:name="com.microsoft.intune.mam.MAMMultiIdentity"
    android:value="true" />
```

### <a name="setting-the-identity"></a><span data-ttu-id="31d69-605">Festlegen der Identität</span><span class="sxs-lookup"><span data-stu-id="31d69-605">Setting the Identity</span></span>

<span data-ttu-id="31d69-606">Entwickler können die Identität der App-Benutzer auf den folgenden Ebenen mit absteigender Priorität festlegen:</span><span class="sxs-lookup"><span data-stu-id="31d69-606">Developers can set the identity of the app user on the following levels in descending priority:</span></span>

  1. <span data-ttu-id="31d69-607">Threadebene</span><span class="sxs-lookup"><span data-stu-id="31d69-607">Thread level</span></span>
  2. <span data-ttu-id="31d69-608">Context (allgemein Activity)</span><span class="sxs-lookup"><span data-stu-id="31d69-608">Context  (generally Activity) level</span></span>
  3. <span data-ttu-id="31d69-609">Prozessebene</span><span class="sxs-lookup"><span data-stu-id="31d69-609">Process level</span></span>

<span data-ttu-id="31d69-610">Eine auf Threadebene festgelegte Identität hat Vorrang vor einer auf Context-Ebene festgelegten Identität, die wiederum Vorrang vor einer auf Prozessebene festgelegten Identität hat.</span><span class="sxs-lookup"><span data-stu-id="31d69-610">An identity set at the thread level supersedes an identity set at the Context level, which supersedes an identity set at the process level.</span></span> <span data-ttu-id="31d69-611">Eine in einem Context festgelegte Identität wird nur bei Bedarf in dazugehörigen Szenarios verwendet.</span><span class="sxs-lookup"><span data-stu-id="31d69-611">An identity set on a Context is only used in appropriate associated scenarios.</span></span> <span data-ttu-id="31d69-612">Datei-E/A-Vorgängen ist z.B. kein Context zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="31d69-612">File IO operations, for example, do not have an associated Context.</span></span> <span data-ttu-id="31d69-613">Apps werden in den meisten Fällen die Context-Identität für eine Activity festlegen.</span><span class="sxs-lookup"><span data-stu-id="31d69-613">Most commonly, apps will set the Context identity on an Activity.</span></span> <span data-ttu-id="31d69-614">Eine App *darf keine* Daten für eine verwaltete Identität anzeigen, es sei denn, die Identität der Activity ist auf die gleiche Identität festgelegt.</span><span class="sxs-lookup"><span data-stu-id="31d69-614">An app *must* not display data for a managed identity unless the Activity's identity is set to that same identity.</span></span> <span data-ttu-id="31d69-615">In der Regel ist die Identität auf Prozessebene nur nützlich, wenn die App nur mit einem einzelnen Benutzer auf allen Threads arbeitet.</span><span class="sxs-lookup"><span data-stu-id="31d69-615">In general, the process-level identity is only useful if the app works only with a single user at a time on all threads.</span></span> <span data-ttu-id="31d69-616">Viele Apps müssen davon nicht Gebrauch machen.</span><span class="sxs-lookup"><span data-stu-id="31d69-616">Many apps may not need to make use of it.</span></span>

<span data-ttu-id="31d69-617">Die folgenden Methoden in `MAMPolicyManager` können verwendet werden, um die Identität festzulegen und die zuvor festgelegten Identitätswerte abzurufen.</span><span class="sxs-lookup"><span data-stu-id="31d69-617">The following methods in `MAMPolicyManager` may be used to set the identity and retrieve the identity values previously set.</span></span>

```java
  public static void setUIPolicyIdentity(final Context context, final String identity, final MAMSetUIIdentityCallback mamSetUIIdentityCallback);

  public static String getUIPolicyIdentity(final Context context);

  public static MAMIdentitySwitchResult setProcessIdentity(final String identity);

  public static String getProcessIdentity();

  public static MAMIdentitySwitchResult setCurrentThreadIdentity(final String identity);

  public static String getCurrentThreadIdentity();

/**
   * Get the current app policy. This does NOT take the UI (Context) identity into account.
   * If the current operation has any context (e.g. an Activity) associated with it, use the overload below.
   */
  public static AppPolicy getPolicy();

  /**
  * Get the current app policy. This DOES take the UI (Context) identity into account.
   * If the current operation has any context (e.g. an Activity) associated with it, use this function.
   */
  public static AppPolicy getPolicy(final Context context);


  public static AppPolicy getPolicyForIdentity(final String identity);

  public static boolean getIsIdentityManaged(final String identity);

  ```

>[!NOTE]
> <span data-ttu-id="31d69-618">Sie können die Identität der App durch Festlegung auf NULL löschen.</span><span class="sxs-lookup"><span data-stu-id="31d69-618">You can clear the identity of the app by setting it to null.</span></span>
>
> <span data-ttu-id="31d69-619">Die leere Zeichenfolge kann als Identität verwendet werden, die niemals App-Schutzrichtlinien aufweist.</span><span class="sxs-lookup"><span data-stu-id="31d69-619">The empty string may be used as an identity that will never have app protection policy.</span></span>

#### <a name="results"></a><span data-ttu-id="31d69-620">Ergebnisse</span><span class="sxs-lookup"><span data-stu-id="31d69-620">Results</span></span>
<span data-ttu-id="31d69-621">Alle Methoden zum Festlegen der Identität geben über `MAMIdentitySwitchResult` Ergebniswerte zurück.</span><span class="sxs-lookup"><span data-stu-id="31d69-621">All the methods used to set the identity report back result values via `MAMIdentitySwitchResult`.</span></span> <span data-ttu-id="31d69-622">Vier Werte können zurückgegeben werden:</span><span class="sxs-lookup"><span data-stu-id="31d69-622">There are four values that can be returned:</span></span>

| <span data-ttu-id="31d69-623">Rückgabewert</span><span class="sxs-lookup"><span data-stu-id="31d69-623">Return value</span></span> | <span data-ttu-id="31d69-624">Szenario</span><span class="sxs-lookup"><span data-stu-id="31d69-624">Scenario</span></span> |
|--|--|
| <span data-ttu-id="31d69-625">SUCCEEDED</span><span class="sxs-lookup"><span data-stu-id="31d69-625">SUCCEEDED</span></span> | <span data-ttu-id="31d69-626">Die Identitätsänderung war erfolgreich.</span><span class="sxs-lookup"><span data-stu-id="31d69-626">The identity change was successful.</span></span> |
| <span data-ttu-id="31d69-627">NOT_ALLOWED</span><span class="sxs-lookup"><span data-stu-id="31d69-627">NOT_ALLOWED</span></span> | <span data-ttu-id="31d69-628">Die Änderung der Identität ist nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="31d69-628">The identity change is not allowed.</span></span> <span data-ttu-id="31d69-629">Die Änderung der Identität ist nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="31d69-629">The identity change is not allowed.</span></span> <span data-ttu-id="31d69-630">Dies tritt auch bei dem Versuch auf, die Benutzeroberflächenidentität (Context) festzulegen, wenn für den aktuellen Thread eine andere Identität festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="31d69-630">This occurs if an attempt is made to set the UI (Context) identity when a different identity is set on the current thread.</span></span> |
| <span data-ttu-id="31d69-631">CANCELLED</span><span class="sxs-lookup"><span data-stu-id="31d69-631">CANCELLED</span></span> | <span data-ttu-id="31d69-632">Der Benutzer hat die Identitätsänderung abgebrochen, in der Regel mithilfe der Schaltfläche „Zurück“ einer PIN- oder Authentifizierungseingabeaufforderung.</span><span class="sxs-lookup"><span data-stu-id="31d69-632">The user cancelled the identity change, generally by pressing the back button on a PIN or authentication prompt.</span></span> |
| <span data-ttu-id="31d69-633">FAILED</span><span class="sxs-lookup"><span data-stu-id="31d69-633">FAILED</span></span> | <span data-ttu-id="31d69-634">Bei der Identitätsänderung ist aus unbekannten Gründen ein Fehler aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="31d69-634">The identity change failed for an unspecified reason.</span></span>|

<span data-ttu-id="31d69-635">Die App *muss* sicherstellen, dass ein Identitätswechsel erfolgreich ist, bevor Unternehmensdaten angezeigt oder verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="31d69-635">The app *must* ensure that an identity switch is successful before displaying or using corporate data.</span></span> <span data-ttu-id="31d69-636">Aktuell sind Prozess- und Threadidentitätswechsel immer für eine App erfolgreich, für die mehrere Identitäten aktiviert sind. Wir behalten und jedoch vor, Fehlerbedingungen hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="31d69-636">Currently, process and thread identity switches will always succeed for a multi-identity-enabled app, however we reserve the right to add failure conditions.</span></span> <span data-ttu-id="31d69-637">Der Identitätswechsel für die Benutzeroberfläche kann möglicherweise für ungültige Argumente fehlschlagen, falls sie mit der Threadidentität in Konflikt stehen oder der Benutzer die bedingten Startanforderungen aufheben würde (z.B. indem er auf die schwarze Schaltfläche auf dem PIN-Bildschirm klicken drückt).</span><span class="sxs-lookup"><span data-stu-id="31d69-637">The UI identity switch may fail for invalid arguments, if it would conflict with the thread identity, or if the user cancels out of conditional launch requirements (e.g. presses the back button on the PIN screen).</span></span>


<span data-ttu-id="31d69-638">Bei Festlegung einer Context-Identität wird das Ergebnis asynchron gemeldet.</span><span class="sxs-lookup"><span data-stu-id="31d69-638">In the case of setting a Context identity, the result is reported asynchronously.</span></span> <span data-ttu-id="31d69-639">Wenn der Context eine Activity ist, wird dem SDK erst nach einem bedingten Start, der den Benutzer vielleicht zur Eingabe einer PIN oder seiner Unternehmensanmeldeinformationen auffordert, bekannt, ob die Änderung der Identität erfolgreich war.</span><span class="sxs-lookup"><span data-stu-id="31d69-639">If the Context is an Activity, the SDK doesn't know if the identity change succeeded until after conditional launch is performed -- which may require the user to enter a PIN or corporate credentials.</span></span> <span data-ttu-id="31d69-640">Es wird vorausgesetzt, dass die App einen `MAMSetUIIdentityCallback` für den Empfang dieses Ergebnisses implementiert. Sie können NULL für diesen Parameter übergeben.</span><span class="sxs-lookup"><span data-stu-id="31d69-640">The app is expected to implement a `MAMSetUIIdentityCallback` to receive this result, you can pass null for this parameter.</span></span>

```java
    public interface MAMSetUIIdentityCallback {
        void notifyIdentityResult(MAMIdentitySwitchResult identitySwitchResult);
  }
```

<span data-ttu-id="31d69-641">Sie können die Identität einer Activity auch direkt über eine Methode in `MAMActivity` festlegen, anstatt `MAMPolicyManager.setUIPolicyIdentity` aufzurufen.</span><span class="sxs-lookup"><span data-stu-id="31d69-641">You can also set the identity of an activity directly through a method in `MAMActivity` instead of calling `MAMPolicyManager.setUIPolicyIdentity`.</span></span> <span data-ttu-id="31d69-642">Verwenden Sie zu diesem Zweck die folgende Methode:</span><span class="sxs-lookup"><span data-stu-id="31d69-642">Use following method to do so:</span></span>

```java
     public final void switchMAMIdentity(final String newIdentity);
```

<span data-ttu-id="31d69-643">Apps können auch eine Methode in `MAMActivity` außer Kraft setzen, wenn die App über das Ergebnis von Versuchen, die Identität dieser Activity zu ändern, benachrichtigt werden soll.</span><span class="sxs-lookup"><span data-stu-id="31d69-643">You can also override a method in `MAMActivity` if you want the app to be notified of the result of attempts to change the identity of that activity.</span></span>

``` java
    public void onSwitchMAMIdentityComplete(final MAMIdentitySwitchResult result);
```

>[!NOTE]
> <span data-ttu-id="31d69-644">Wechseln der Identität kann das Neuerstellen der Activity erfordern.</span><span class="sxs-lookup"><span data-stu-id="31d69-644">Switching the identity may require recreating the activity.</span></span> <span data-ttu-id="31d69-645">In diesem Fall wird der `onSwitchMAMIdentityComplete`-Rückruf an die neue Instanz der Activity übermittelt.</span><span class="sxs-lookup"><span data-stu-id="31d69-645">In this case, the `onSwitchMAMIdentityComplete` callback will be delivered to the new instance of the activity.</span></span>


### <a name="implicit-identity-changes"></a><span data-ttu-id="31d69-646">Implizite Identitätsänderungen</span><span class="sxs-lookup"><span data-stu-id="31d69-646">Implicit Identity Changes</span></span>

<span data-ttu-id="31d69-647">Zusätzlich zu der Möglichkeit der App, die Identität festzulegen, kann die Identität eines Threads oder Kontexts sich basierend auf dem Dateneingang von einer anderen Intune-fähigen App ändern, die eine App-Schutzrichtlinie aufweist.</span><span class="sxs-lookup"><span data-stu-id="31d69-647">In addition to the app's ability to set the identity, a thread or a context's identity may change based on data ingress from another Intune-enlightened app that has app protection policy.</span></span>

#### <a name="examples"></a><span data-ttu-id="31d69-648">Beispiele</span><span class="sxs-lookup"><span data-stu-id="31d69-648">Examples</span></span>

  1. <span data-ttu-id="31d69-649">Wenn eine Activity durch einen `Intent` gestartet wird, der von einer anderen MAM-App gesendet wird, wird die Identität der Activity basierend auf der effektiven Identität in der anderen App zu dem Zeitpunkt, zu dem der `Intent` gesendet wurde, festgelegt.</span><span class="sxs-lookup"><span data-stu-id="31d69-649">If an activity is launched from an `Intent` sent by another MAM app, the activity’s identity will be set based on the effective identity in the other app at the point the `Intent` was sent.</span></span>

  2.  <span data-ttu-id="31d69-650">Für Dienste wird die Identität des Threads ähnlich für die Dauer eines `onStart`- oder `onBind`-Aufrufs festgelegt.</span><span class="sxs-lookup"><span data-stu-id="31d69-650">For services, the thread identity will be set similarly for the duration of an `onStart` or `onBind` call.</span></span> <span data-ttu-id="31d69-651">Aufrufe von `Binder`, die von `onBind` zurückgegeben werden, legen ebenfalls vorübergehend die Threadidentität fest.</span><span class="sxs-lookup"><span data-stu-id="31d69-651">Calls into the `Binder` returned from `onBind` will also temporarily set the thread identity.</span></span>

  3. <span data-ttu-id="31d69-652">An einen `ContentProvider` gerichtete Aufrufe legen auf ähnliche Weise die Threadidentität für ihre Dauer fest.</span><span class="sxs-lookup"><span data-stu-id="31d69-652">Calls into a `ContentProvider` will similarly set the thread identity for their duration.</span></span>


  <span data-ttu-id="31d69-653">Darüber hinaus könnte Benutzerinteraktion mit einer Activity eine implizite Identitätsänderung hervorrufen.</span><span class="sxs-lookup"><span data-stu-id="31d69-653">In addition, user interaction with an activity may cause an implicit identity switch.</span></span>

  <span data-ttu-id="31d69-654">**Beispiel**: Wenn ein Benutzer während `Resume` eine Autorisierungsanforderung abbricht, führt dies zu einem impliziten Wechsel zu einer leeren Identität.</span><span class="sxs-lookup"><span data-stu-id="31d69-654">**Example:** A user canceling out of an authorization prompt during `Resume` will result in an implicit switch to an empty identity.</span></span>

  <span data-ttu-id="31d69-655">Die App wird auf diese Änderungen aufmerksam gemacht und kann sie verbieten, wenn dies erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="31d69-655">The app is given an opportunity to be made aware of these changes, and, if it must, the app can forbid them.</span></span> <span data-ttu-id="31d69-656">`MAMService` und `MAMContentProvider` machen die folgende Methode verfügbar, die Unterklassen überschreiben können:</span><span class="sxs-lookup"><span data-stu-id="31d69-656">`MAMService` and `MAMContentProvider` expose the following method that subclasses may override:</span></span>

  ```java
  public void onMAMIdentitySwitchRequired(final String identity,
    final AppIdentitySwitchResultCallback callback);
  ```

  <span data-ttu-id="31d69-657">In der `MAMActivity`-Klasse ist ein zusätzlicher Parameter in der Methode vorhanden:</span><span class="sxs-lookup"><span data-stu-id="31d69-657">In the `MAMActivity` class , an additional parameter is present in the method:</span></span>

  ```java
  public void onMAMIdentitySwitchRequired(final String identity,
    final AppIdentitySwitchReason reason,
    final AppIdentitySwitchResultCallback callback);
  ```

  * <span data-ttu-id="31d69-658">`AppIdentitySwitchReason` erfasst die Quelle der impliziten Änderung und akzeptiert die Werte `CREATE`, `RESUME_CANCELLED` und `NEW_INTENT`.</span><span class="sxs-lookup"><span data-stu-id="31d69-658">The `AppIdentitySwitchReason` captures the source of the implicit switch, and can accept the values `CREATE`, `RESUME_CANCELLED`, and `NEW_INTENT`.</span></span>  <span data-ttu-id="31d69-659">Der Grund `RESUME_CANCELLED` wird verwendet, wenn das Fortsetzen der Activity bewirkt, dass PIN, Authentifizierung oder eine andere Konformitätsbenutzeroberfläche angezeigt wird, und der Benutzer versucht, die Benutzeroberfläche abzubrechen, in der Regel mithilfe der Schaltfläche „Zurück“.</span><span class="sxs-lookup"><span data-stu-id="31d69-659">The `RESUME_CANCELLED` reason is used when activity resume causes PIN, authentication, or other compliance UI to be displayed and the user attempts to cancel out of that UI, generally though use of the back button.</span></span>


  * <span data-ttu-id="31d69-660">`AppIdentitySwitchResultCallback` ist wie folgt:</span><span class="sxs-lookup"><span data-stu-id="31d69-660">The `AppIdentitySwitchResultCallback` is as follows:</span></span>

    ```java
    public interface AppIdentitySwitchResultCallback {
        /**
         * @param result
         *            whether the identity switch can proceed.
         */
        void reportIdentitySwitchResult(AppIdentitySwitchResult result);
    }
    ```

    <span data-ttu-id="31d69-661">Dabei gibt ```AppIdentitySwitchResult``` entweder SUCCESS oder FAILURE an.</span><span class="sxs-lookup"><span data-stu-id="31d69-661">Where ```AppIdentitySwitchResult``` is either SUCCESS or FAILURE.</span></span>

<span data-ttu-id="31d69-662">Die Methode `onMAMIdentitySwitchRequired` wird für alle impliziten Identitätsänderungen aufgerufen – mit Ausnahme derer, die über einen von `MAMService.onMAMBind` zurückgegebenen Binder erfolgen.</span><span class="sxs-lookup"><span data-stu-id="31d69-662">The method `onMAMIdentitySwitchRequired` is called for all implicit identity changes except for those made through a Binder returned from `MAMService.onMAMBind`.</span></span> <span data-ttu-id="31d69-663">Die Standardimplementierungen von `onMAMIdentitySwitchRequired` rufen sofort Folgendes auf:</span><span class="sxs-lookup"><span data-stu-id="31d69-663">The default implementations of `onMAMIdentitySwitchRequired` immediately call:</span></span>

*  <span data-ttu-id="31d69-664">`reportIdentitySwitchResult(FAILURE)`, wenn RESUME_CANCELLED der Grund ist.</span><span class="sxs-lookup"><span data-stu-id="31d69-664">`reportIdentitySwitchResult(FAILURE)` when the reason is RESUME_CANCELLED.</span></span>

*  <span data-ttu-id="31d69-665">`reportIdentitySwitchResult(SUCCESS)` in allen anderen Fällen.</span><span class="sxs-lookup"><span data-stu-id="31d69-665">`reportIdentitySwitchResult(SUCCESS)` in all other cases.</span></span>

  <span data-ttu-id="31d69-666">Es ist nicht anzunehmen, dass die meisten Apps einen Wechsel der Identität auf andere Weise blockieren oder verzögern müssen, aber wenn dies für eine App erforderlich ist, müssen die folgenden Punkte berücksichtigt werden:</span><span class="sxs-lookup"><span data-stu-id="31d69-666">It is not expected that most apps will need to block or delay an identity switch in a different manner, but if an app needs to do so, the following points must be considered:</span></span>

  * <span data-ttu-id="31d69-667">Wenn ein Identitätswechsel blockiert wird, ist das Ergebnis identisch mit dem Verbot des Dateneingangs durch die `Receive`-Freigabeeinstellungen.</span><span class="sxs-lookup"><span data-stu-id="31d69-667">If an identity switch is blocked, the result is the same as if `Receive` sharing settings had prohibited the data ingress.</span></span>

  * <span data-ttu-id="31d69-668">Wenn ein Dienst im Hauptthread ausgeführt wird, **muss** `reportIdentitySwitchResult` synchron aufgerufen werden. Andernfalls reagiert der UI-Thread nicht mehr.</span><span class="sxs-lookup"><span data-stu-id="31d69-668">If a Service is running on the main thread, `reportIdentitySwitchResult` **must** be called synchronously or the UI thread will hang.</span></span>

  * <span data-ttu-id="31d69-669">Für die **Activity**-Erstellung wird `onMAMIdentitySwitchRequired` vor `onMAMCreate` aufgerufen.</span><span class="sxs-lookup"><span data-stu-id="31d69-669">For **Activity** creation, `onMAMIdentitySwitchRequired` will be called before `onMAMCreate`.</span></span> <span data-ttu-id="31d69-670">Wenn die App die Benutzeroberfläche anzeigen muss, um zu bestimmen, ob das Wechseln der Identität zugelassen wird, muss die Benutzeroberfläche mit einer *anderen* Activity angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="31d69-670">If the app must show UI to determine whether to allow the identity switch, that UI must be shown using a *different* activity.</span></span>

  * <span data-ttu-id="31d69-671">Wenn in einer **Activity** ein Wechsel zu der leeren Identität mit dem Grund RESUME_CANCELLED angefordert wird, muss die App die fortgesetzte Activity ändern, um Daten mit diesem Identitätswechsel konsistent anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="31d69-671">In an **Activity**, when a switch to the empty identity is requested with the reason as RESUME_CANCELLED, the app must modify the resumed activity to display data consistent with that identity switch.</span></span>  <span data-ttu-id="31d69-672">Wenn dies nicht möglich ist, sollte die App den Wechsel verweigern, und der Benutzer wird erneut zur Einhaltung der Richtlinie für die Fortsetzung der Identität aufgefordert (z. B. durch Anzeige des PIN-Eingabe-Bildschirms der App).</span><span class="sxs-lookup"><span data-stu-id="31d69-672">If this is not possible, the app should refuse the switch, and the user will be asked again to comply with policy for the resuming identity (e.g. by being presented with the app PIN entry screen).</span></span>

    > [!NOTE]
    > <span data-ttu-id="31d69-673">Eine App mit mehreren Identitäten empfängt eingehende Daten immer von verwalteten und nicht verwalteten Apps.</span><span class="sxs-lookup"><span data-stu-id="31d69-673">A multi-identity app will always receive incoming data from both managed and unmanaged apps.</span></span> <span data-ttu-id="31d69-674">Es liegt in der Verantwortung der App, Daten von verwalteten Identitäten in einer verwalteten Weise zu behandeln.</span><span class="sxs-lookup"><span data-stu-id="31d69-674">It is the responsibility of the app to treat data from managed identities in a managed manner.</span></span>

  <span data-ttu-id="31d69-675">Wenn eine angeforderte Identität verwaltet wird (verwenden Sie `MAMPolicyManager.getIsIdentityManaged` zur Überprüfung), aber die App das Konto nicht verwenden kann (weil z. B. Konten, wie etwa E-Mail-Konten, zunächst in der App eingerichtet werden müssen), sollte das Wechseln der Identität verweigert werden.</span><span class="sxs-lookup"><span data-stu-id="31d69-675">If a requested identity is managed (use `MAMPolicyManager.getIsIdentityManaged` to check), but the app is not able to use that account (e.g. because accounts, such as email accounts, must be set up in the app first) then the identity switch should be refused.</span></span>

### <a name="preserving-identity-in-async-operations"></a><span data-ttu-id="31d69-676">Beibehalten der Identität in asynchronen Vorgängen</span><span class="sxs-lookup"><span data-stu-id="31d69-676">Preserving Identity In Async Operations</span></span>
<span data-ttu-id="31d69-677">Es ist üblich für Vorgänge im UI-Thread, dass Hintergrundaufgaben an einen anderen Thread verteilt werden.</span><span class="sxs-lookup"><span data-stu-id="31d69-677">It is common for operations on the UI thread to dispatch background tasks to another thread.</span></span> <span data-ttu-id="31d69-678">Eine App mit mehreren Identitäten muss sicherstellen, dass diese Hintergrundaufgaben mit der entsprechenden Identität arbeiten, die oft der Identität der Aktivität entspricht, die sie verteilt hat.</span><span class="sxs-lookup"><span data-stu-id="31d69-678">A multi-identity app will want to make sure that these background tasks operate with the appropriate identity, which is often the same identity used by the activity which dispatched them.</span></span> <span data-ttu-id="31d69-679">Das MAM SDK bietet `MAMAsyncTask` und `MAMIdentityExecutors` als praktische Hilfe bei der Wahrung der Identität.</span><span class="sxs-lookup"><span data-stu-id="31d69-679">The MAM SDK provides `MAMAsyncTask` and `MAMIdentityExecutors` as a convenience to aid in preserving the identity.</span></span>
#### <a name="mamasynctask"></a><span data-ttu-id="31d69-680">MAMAsyncTask</span><span class="sxs-lookup"><span data-stu-id="31d69-680">MAMAsyncTask</span></span>

<span data-ttu-id="31d69-681">Um `MAMAsyncTask` zu verwenden, arbeiten Sie einfach mit einer Vererbung davon anstatt mit AsyncTask, und ersetzen Sie die Überschreibungen von `doInBackground` und `onPreExecute` durch `doInBackgroundMAM` bzw. `onPreExecuteMAM`.</span><span class="sxs-lookup"><span data-stu-id="31d69-681">To use `MAMAsyncTask`, simply inherit from it instead of AsyncTask and replace overrides of `doInBackground` and `onPreExecute` with `doInBackgroundMAM` and `onPreExecuteMAM` respectively.</span></span> <span data-ttu-id="31d69-682">Der `MAMAsyncTask`-Konstruktor verwendet einen Aktivitätskontext.</span><span class="sxs-lookup"><span data-stu-id="31d69-682">The `MAMAsyncTask` constructor takes an activity context.</span></span> <span data-ttu-id="31d69-683">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="31d69-683">For example:</span></span>

```java
  AsyncTask<Object, Object, Object> task = new MAMAsyncTask<Object, Object, Object>(thisActivity) {

    @Override
    protected Object doInBackgroundMAM(final Object[] params) {
        // Do operations.
    }
    
    @Override
    protected void onPreExecuteMAM() {
        // Do setup.
    };
```

### <a name="mamidentityexecutors"></a><span data-ttu-id="31d69-684">MAMIdentityExecutors</span><span class="sxs-lookup"><span data-stu-id="31d69-684">MAMIdentityExecutors</span></span>
<span data-ttu-id="31d69-685">`MAMIdentityExecutors` erlaubt Ihnen das Umschließen einer vorhandenen `Executor`- oder `ExecutorService`-Instanz als identitätserhaltenden `Executor`/`ExecutorService` mit den Methoden `wrapExecutor` und `wrapExecutorService`.</span><span class="sxs-lookup"><span data-stu-id="31d69-685">`MAMIdentityExecutors` allows you to wrap an existing `Executor` or `ExecutorService` instance as an identity-preserving `Executor`/`ExecutorService` with `wrapExecutor` and `wrapExecutorService` methods.</span></span> <span data-ttu-id="31d69-686">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="31d69-686">For example</span></span>

```java
  Executor wrappedExecutor = MAMIdentityExecutors.wrapExecutor(originalExecutor, activity);
  ExecutorService wrappedService = MAMIdentityExecutors.wrapExecutorService(originalExecutorService, activity);
```

  ### <a name="file-protection"></a><span data-ttu-id="31d69-687">Dateischutz</span><span class="sxs-lookup"><span data-stu-id="31d69-687">File Protection</span></span>

  <span data-ttu-id="31d69-688">Jeder Datei wird zum Zeitpunkt der Erstellung basierend auf der Thread- und Prozessidentität eine Identität zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="31d69-688">Every file has an identity associated with it at the time of creation, based on thread and process identity.</span></span> <span data-ttu-id="31d69-689">Diese Identität wird sowohl für die Dateiverschlüsselung als auch die selektive Zurücksetzung verwendet.</span><span class="sxs-lookup"><span data-stu-id="31d69-689">This identity will be used for both file encryption and selective wipe.</span></span> <span data-ttu-id="31d69-690">Nur Dateien, deren Identität verwaltet wird und eine Richtlinie aufweist, die Verschlüsselung erfordert, werden verschlüsselt.</span><span class="sxs-lookup"><span data-stu-id="31d69-690">Only files whose identity is managed and has policy requiring encryption will be encrypted.</span></span> <span data-ttu-id="31d69-691">Die standardmäßige selektive Funktionszurücksetzung des SDK setzt nur Dateien zurück, denen die verwaltete Identität zugeordnet ist, für die eine Zurücksetzung angefordert wurde.</span><span class="sxs-lookup"><span data-stu-id="31d69-691">The SDK's default selective functionality wipe will only wipe files associated with the managed identity for which a wipe has been requested.</span></span> <span data-ttu-id="31d69-692">Die App kann die Identität einer Datei mit de `MAMFileProtectionManager`-Klasse abfragen oder ändern.</span><span class="sxs-lookup"><span data-stu-id="31d69-692">The app may query or change a file’s identity using the `MAMFileProtectionManager` class.</span></span>

  ```java
    public final class MAMFileProtectionManager {
    /**
         * Protect a file. This will synchronously trigger whatever protection is required for the 
           file, and will tag the file for future protection changes.

         *
         * @param identity
         *            Identity to set.
         * @param file
         *            File to protect.
         * @throws IOException
         *             If the file cannot be changed.
         */
        public static void protect(final File file, final String identity) throws IOException;
        
        /**
        * Protect a file obtained from a content provider. This is intended to be used for
        * sdcard (whether internal or removable) files accessed through the Storage Access Framework.
        * It may also be used with descriptors referring to private files owned by this app.
        * It is not intended to be used for files owned by other apps and such usage will fail. If
        * creating a new file via a content provider exposed by another MAM-integrated app, the new
        * file identity will automatically be set correctly if the ContentResolver in use was
        * obtained via a Context with an identity or if the thread identity is set.
        *
        * This will synchronously trigger whatever protection is required for the file, and will tag
        * the file for future protection changes. If an identity is set on a directory, it is set
        * recursively on all files and subdirectories. If MAM is operating in offline mode, this
        * method will silently do nothing.
        *
        * @param identity
        *       Identity to set.
        * @param file
        *       File to protect.
        *
        * @throws IOException
        *       If the file cannot be protected.

        */
        public static void protect(final ParcelFileDescriptor file, final String identity) throws IOException;

        /**
         * Get the protection info on a file.
         *
         * @param file
         *            File or directory to get information on.
         * @return File protection info, or null if there is no protection info.
         * @throws IOException
         *             If the file cannot be read or opened.
         */
        public static MAMFileProtectionInfo getProtectionInfo(final ParcelFileDescriptor file) throws IOException;

    }

    public interface MAMFileProtectionInfo {
        String getIdentity();
    }

  ```
#### <a name="app-responsibility"></a><span data-ttu-id="31d69-693">App-Verantwortung</span><span class="sxs-lookup"><span data-stu-id="31d69-693">App Responsibility</span></span>
<span data-ttu-id="31d69-694">MAM kann nicht automatisch eine Beziehung zwischen Dateien, die gelesen werden und Daten, die in einer `Activity` dargestellt werden, ableiten.</span><span class="sxs-lookup"><span data-stu-id="31d69-694">MAM cannot automatically infer a relationship between files being read and data being displayed in an `Activity`.</span></span> <span data-ttu-id="31d69-695">Apps *müssen* die Benutzeroberflächenidentität ordnungsgemäß festlegen, bevor Sie Unternehmensdaten anzeigen.</span><span class="sxs-lookup"><span data-stu-id="31d69-695">Apps *must* set the UI identity appropriately before displaying corporate data.</span></span> <span data-ttu-id="31d69-696">Dies beinhaltet Daten, die aus Dateien lesen.</span><span class="sxs-lookup"><span data-stu-id="31d69-696">This includes data read from files.</span></span> <span data-ttu-id="31d69-697">Wenn eine Datei von außerhalb der App stammt (entweder von einer `ContentProvider` oder aus einem öffentlich schreibbaren Speicherort), *muss* die App versuchen, die Dateiidentität (mit `MAMFileProtectionManager.getProtectionInfo`) zu bestimmen, bevor Sie Informationen anzeigen kann, die aus der Datei gelesen werden.</span><span class="sxs-lookup"><span data-stu-id="31d69-697">If a file comes from outside the app (either from a `ContentProvider` or read from a publicly writable location), the app *must* attempt to determine the file identity (using `MAMFileProtectionManager.getProtectionInfo`) before displaying information read from the file.</span></span> <span data-ttu-id="31d69-698">Wenn `getProtectionInfo` eine Identität darstellt, die nicht NULL und nicht leer ist, *muss* die Benutzeroberflächenidentität festgelegt werden, damit sie mit dieser Identität übereinstimmt (mithilfe von `MAMActivity.switchMAMIdentity` oder `MAMPolicyManager.setUIPolicyIdentity`).</span><span class="sxs-lookup"><span data-stu-id="31d69-698">If `getProtectionInfo` reports a non-null, non-empty identity, the UI identity *must* be set to match this identity (using `MAMActivity.switchMAMIdentity` or `MAMPolicyManager.setUIPolicyIdentity`).</span></span> <span data-ttu-id="31d69-699">Wenn der Identitätswechsel fehlschlägt, dürfen Daten aus der Datei *nicht angezeigt werden*.</span><span class="sxs-lookup"><span data-stu-id="31d69-699">If the identity switch fails, data from the file *must not* be displayed.</span></span>

<span data-ttu-id="31d69-700">Eine Beispielausführung sollte in etwa folgendermaßen aussehen:</span><span class="sxs-lookup"><span data-stu-id="31d69-700">An example flow might look something like the following:</span></span>
  * <span data-ttu-id="31d69-701">Der Benutzer wählt ein Dokument aus, das in der App geöffnet werden soll.</span><span class="sxs-lookup"><span data-stu-id="31d69-701">User selects a document to open in the app</span></span>
  * <span data-ttu-id="31d69-702">Während des Öffnungsvorgangs bestätigt die App die für die Darstellung des Inhalts zu verwendende Identität noch vor dem Lesen von Daten vom Datenträger.</span><span class="sxs-lookup"><span data-stu-id="31d69-702">During the open flow, prior to reading data from disk, the app confirms the identity that should be used to display the content</span></span>
    * <span data-ttu-id="31d69-703">MAMFileProtectionInfo info = MAMFileProtectionManager.getProtectionInfo(docPath)</span><span class="sxs-lookup"><span data-stu-id="31d69-703">MAMFileProtectionInfo info = MAMFileProtectionManager.getProtectionInfo(docPath)</span></span>
    * <span data-ttu-id="31d69-704">if(info)   MAMPolicyManager.setUIPolicyIdentity(activity, info.getIdentity(), callback)</span><span class="sxs-lookup"><span data-stu-id="31d69-704">if(info)   MAMPolicyManager.setUIPolicyIdentity(activity, info.getIdentity(), callback)</span></span>
    * <span data-ttu-id="31d69-705">Die App wartet, bis ein Ergebnis an den Rückruf gemeldet wird.</span><span class="sxs-lookup"><span data-stu-id="31d69-705">The app waits until a result is reported to callback</span></span>
    * <span data-ttu-id="31d69-706">Wenn das gemeldete Ergebnis einen Fehler darstellt, zeigt die App das Dokument nicht an.</span><span class="sxs-lookup"><span data-stu-id="31d69-706">If the reported result is a failure, the app does not display the document.</span></span>
  * <span data-ttu-id="31d69-707">Die App öffnet und rendert die Datei.</span><span class="sxs-lookup"><span data-stu-id="31d69-707">The app opens and renders the file</span></span>

## <a name="offline-scenarios"></a><span data-ttu-id="31d69-708">Offlineszenarios</span><span class="sxs-lookup"><span data-stu-id="31d69-708">Offline Scenarios</span></span>

<span data-ttu-id="31d69-709">Die Markierung der Dateiidentität reagiert empfindlich auf den Offlinemodus.</span><span class="sxs-lookup"><span data-stu-id="31d69-709">File identity tagging is sensitive to offline mode.</span></span> <span data-ttu-id="31d69-710">Die folgenden Punkte müssen berücksichtigt werden:</span><span class="sxs-lookup"><span data-stu-id="31d69-710">The following points should be taken into account:</span></span>

  * <span data-ttu-id="31d69-711">Wenn das Unternehmensportal nicht installiert ist, kann Dateien keine Identität zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="31d69-711">If the Company Portal is not installed, files cannot be identity-tagged.</span></span>

  * <span data-ttu-id="31d69-712">Wenn das Unternehmensportal installiert ist, aber die App nicht über die Intune MAM-Richtlinie verfügt, kann Dateien nicht zuverlässig eine Identität zugeordnet werden.</span><span class="sxs-lookup"><span data-stu-id="31d69-712">If the Company Portal is installed, but the app does not have Intune MAM policy, files cannot be reliably tagged with identity.</span></span>

  * <span data-ttu-id="31d69-713">Wenn die Zuordnung der Dateiidentität verfügbar ist, werden alle zuvor erstellte Dateien als persönlich/nicht verwaltet (zur Identität der leeren Zeichenfolge gehörend) behandelt, wenn die App nicht zuvor als verwaltete App mit einzelner Identität installiert wurde. In diesem Fall werden sie als zu dem registrierten Benutzer gehörend behandelt.</span><span class="sxs-lookup"><span data-stu-id="31d69-713">When file identity tagging becomes available, all previously created files are treated as personal/unmanaged (belonging to the empty-string identity) unless the app was previously installed as a single-identity managed app in which case they are treated as belonging to the enrolled user.</span></span>

### <a name="directory-protection"></a><span data-ttu-id="31d69-714">Verzeichnisschutz</span><span class="sxs-lookup"><span data-stu-id="31d69-714">Directory Protection</span></span>

<span data-ttu-id="31d69-715">Verzeichnisse können mithilfe derselben `protect`-Methode geschützt werden, mit der auch Dateien geschützt werden.</span><span class="sxs-lookup"><span data-stu-id="31d69-715">Directories may be protected using the same `protect` method used to protect files.</span></span> <span data-ttu-id="31d69-716">Beachten Sie, dass der Verzeichnisschutz rekursiv auf alle Dateien und Unterverzeichnisse angewendet wird, die im Verzeichnis enthalten sind, sowie auf neue Dateien, die in diesem Verzeichnis erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="31d69-716">Please note that directory protection applies recursively to all files and subdirectories contained in the directory, and to new files created within the directory.</span></span> <span data-ttu-id="31d69-717">Da der Verzeichnisschutz rekursiv angewendet wird, kann der `protect`-Aufruf bei sehr großen Verzeichnissen einige Zeit dauern.</span><span class="sxs-lookup"><span data-stu-id="31d69-717">Because directory protection is applied recursively, the `protect` call can take some time to complete for very large directories.</span></span> <span data-ttu-id="31d69-718">Aus diesem Grund möchten Apps, die Schutz auf ein Verzeichnis anwenden, das eine große Anzahl von Dateien enthält, `protect` möglicherweise asynchron in einem Hintergrundthread ausführen.</span><span class="sxs-lookup"><span data-stu-id="31d69-718">For that reason, apps applying protection to a directory that contains a large number of files might wish to run `protect` asynchronously on a background thread.</span></span>

### <a name="data-protection"></a><span data-ttu-id="31d69-719">Schutz von Daten</span><span class="sxs-lookup"><span data-stu-id="31d69-719">Data Protection</span></span>

<span data-ttu-id="31d69-720">Es ist nicht möglich, eine Datei als zu mehreren Identitäten gehörend zu kennzeichnen.</span><span class="sxs-lookup"><span data-stu-id="31d69-720">It is not possible to tag a file as belonging to multiple identities.</span></span> <span data-ttu-id="31d69-721">Apps, die zu einem anderen Benutzer gehörende Daten in der gleichen Datei speichern müssen, können dies manuell mit den Features von `MAMDataProtectionManager` durchführen.</span><span class="sxs-lookup"><span data-stu-id="31d69-721">Apps that must store data belonging to different users in the same file can do so manually, using the features provided by `MAMDataProtectionManager`.</span></span> <span data-ttu-id="31d69-722">So kann die App Daten verschlüsseln und sie an einen bestimmten Benutzer binden.</span><span class="sxs-lookup"><span data-stu-id="31d69-722">This allows the app to encrypt data and tie it to a particular user.</span></span> <span data-ttu-id="31d69-723">Die verschlüsselten Daten eignen sich für die Speicherung in einer Datei auf dem Datenträger.</span><span class="sxs-lookup"><span data-stu-id="31d69-723">The encrypted data is suitable for storing to disk in a file.</span></span> <span data-ttu-id="31d69-724">Sie können die Daten abfragen, die der Identität zugeordnet, und die Daten können später entschlüsselt werden.</span><span class="sxs-lookup"><span data-stu-id="31d69-724">You can query the data associated with the identity and the data can be unecrypted later.</span></span>

<span data-ttu-id="31d69-725">Apps, die `MAMDataProtectionManager` verwenden, sollten einen Empfänger für die `MANAGEMENT_REMOVED`-Benachrichtigung implementieren.</span><span class="sxs-lookup"><span data-stu-id="31d69-725">Apps which make use of `MAMDataProtectionManager` should implement a receiver for the `MANAGEMENT_REMOVED` notification.</span></span> <span data-ttu-id="31d69-726">Nach Abschluss dieser Benachrichtigung können Puffer, die über diese Klasse geschützt wurden, nicht mehr gelesen werden, wenn beim Schutz der Puffer die Dateiverschlüsselung aktiviert wurde.</span><span class="sxs-lookup"><span data-stu-id="31d69-726">After this notification completes, buffers which were protected via this class will no longer be readable if file encryption was enabled when the buffers were protected.</span></span> <span data-ttu-id="31d69-727">Eine App kann diese Situation durch Aufrufen von MAMDataProtectionManager.unprotect für alle Puffer während dieser Benachrichtigung beheben.</span><span class="sxs-lookup"><span data-stu-id="31d69-727">An app can remediate this situation by calling MAMDataProtectionManager.unprotect on all buffers during this notification.</span></span> <span data-ttu-id="31d69-728">Beachten Sie, dass es ebenfalls sicher ist, den Schutz während dieser Benachrichtigung aufzurufen, wenn Identitätsinformationen bewahrt werden sollen. Während der Benachrichtigung ist die Deaktivierung der Verschlüsselung gewährleistet.</span><span class="sxs-lookup"><span data-stu-id="31d69-728">Note that it is also safe to call protect during this notification if it is desired to preserve identity information -- encryption is guaranteed to be disabled during the notification.</span></span>

```java

public final class MAMDataProtectionManager {
    /**
     * Protect a stream. This will return a stream containing the protected
     * input.
     *
     * @param identity
     *            Identity to set.
     * @param input
     *            Input data to protect, read sequentially. This function
     *            will change the position of the stream but may not have
     *            read the entire stream by the time it returns. The
     *            returned stream will wrap this one. Calls to read on the
     *            returned stream may cause further reads on the original
     *            input stream. Callers should not expect to read directly
     *            from the input stream after passing it to this method.
     *            Calling close on the returned stream will close this one.
     * @return Protected input data.
     * @throws IOException
     *             If the data could not be protected
     */
    public static InputStream protect(final InputStream input, final String identity);

    /**
     * Protect a byte array. This will return protected bytes.
     *
     * @param identity
     *            Identity to set.
     * @param input
     *            Input data to protect.
     * @return Protected input data.
     * @throws IOException
     *             If the data could not be protected
     */
    public static byte[] protect(final byte[] input, final String identity) throws IOException;

    /**
     * Unprotect a stream. This will return a stream containing the
     * unprotected input.
     *
     * @param input
     *            Input data to protect, read sequentially.
     * @return Protected input data.
     * @throws IOException
     *             If the data could not be unprotected
     */
    public static InputStream unprotect(final InputStream input) throws IOException;

    /**
     * Unprotect a byte array. This will return unprotected bytes.
     *
     * @param input
     *            Input data to protect.
     * @return Protected input data.
     * @throws IOException
     *             If the data could not be unprotected
     */
    public static byte[] unprotect(final byte[] input) throws IOException;

    /**
     * Get the protection info on a stream.
     *
     * @param input
     *            Input stream to get information on. Either this input
     *            stream must have been returned by a previous call to
     *            protect OR input.markSupported() must return true.
     *            Otherwise it will be impossible to get protection info
     *            without advancing the stream position. The stream must be
     *            positioned at the beginning of the protected data.
     * @return Data protection info, or null if there is no protection
     *            info.
     * @throws IOException
     *             If the input cannot be read.
     */
    public static MAMDataProtectionInfo getProtectionInfo(final InputStream input) throws IOException;

    /**
     * Get the protection info on a stream.
     *
     * @param input
     *            Input bytes to get information on. These must be bytes
     *            returned by a previous call to protect() or a copy of
     *            such bytes.
     * @return Data protection info, or null if there is no protection
     *            info.
     * @throws IOException
     *             If the input cannot be read.
     */
    public static MAMDataProtectionInfo getProtectionInfo(final byte[] input) throws IOException;
}

```

### <a name="content-providers"></a><span data-ttu-id="31d69-729">Inhaltsanbieter</span><span class="sxs-lookup"><span data-stu-id="31d69-729">Content Providers</span></span>

<span data-ttu-id="31d69-730">Wenn die App andere Unternehmensdaten als **ParcelFileDescriptor** über **ContentProvider** bereitstellen, muss die App die Methode `isProvideContentAllowed(String)` in `MAMContentProvider` aufrufen und den Benutzerprinzipalnamen (UPN) der Besitzeridentität für den Inhalt übergeben.</span><span class="sxs-lookup"><span data-stu-id="31d69-730">If the app provides corporate data other than a **ParcelFileDescriptor** through a **ContentProvider**, the app must call the method `isProvideContentAllowed(String)` in `MAMContentProvider`, passing the owner identity's UPN (user principal name) for the content.</span></span> <span data-ttu-id="31d69-731">Wenn diese Funktion „false“ zurückgibt, darf der Inhalt *nicht* an den Aufrufer zurückgegeben werden.</span><span class="sxs-lookup"><span data-stu-id="31d69-731">If this function returns false, the content *must not* be returned to the caller.</span></span> <span data-ttu-id="31d69-732">Durch einen Inhaltsanbieter zurückgegebene Dateideskriptoren werden automatisch auf Grundlage der Dateiidentität behandelt.</span><span class="sxs-lookup"><span data-stu-id="31d69-732">File descriptors returned through a content provider are handled automatically based on the file identity.</span></span>

### <a name="selective-wipe"></a><span data-ttu-id="31d69-733">Selektives Zurücksetzen</span><span class="sxs-lookup"><span data-stu-id="31d69-733">Selective Wipe</span></span>

<span data-ttu-id="31d69-734">Wenn eine App für die `WIPE_USER_DATA`-Benachrichtigung registriert wird, genießt sie nicht den Vorteil des Standardverhaltens des SDKs bei der selektiven Zurücksetzung.</span><span class="sxs-lookup"><span data-stu-id="31d69-734">If an app registers for the `WIPE_USER_DATA` notification, it will not receive the benefit of the SDK's default selective wipe behavior.</span></span> <span data-ttu-id="31d69-735">Für Apps, die mehrere Identitäten haben können, kann dieser Verlust erheblicher sein, da die selektive Zurücksetzung nach MAM-Standard nur Dateien zurücksetzt, deren Identität das Ziel einer Zurücksetzung ist.</span><span class="sxs-lookup"><span data-stu-id="31d69-735">For multi-identity aware apps, this loss may be more significant since MAM default selective wipe will wipe only files whose identity is targeted by a wipe.</span></span>

<span data-ttu-id="31d69-736">Wenn eine App, die mehrere Identitäten haben kann, eine selektive Zurücksetzung nach MAM-Standard _**und**_ die Ausführung eigener Aktionen bei der Zurücksetzung wünscht, sollte sie für `WIPE_USER_AUXILIARY_DATA`-Benachrichtigungen registriert werden.</span><span class="sxs-lookup"><span data-stu-id="31d69-736">If a multi-identity aware application wishes MAM default selective wipe to be done _**and**_ wishes to perform its own actions on wipe, it should register for `WIPE_USER_AUXILIARY_DATA` notifications.</span></span> <span data-ttu-id="31d69-737">Diese Benachrichtigung wird sofort vom SDK gesendet, bevor es die selektive Zurücksetzung nach MAM-Standard durchführt.</span><span class="sxs-lookup"><span data-stu-id="31d69-737">This notification will be sent immediately by the SDK before it performs the MAM default selective wipe.</span></span> <span data-ttu-id="31d69-738">Eine App sollte niemals gleichzeitig für WIPE_USER_DATA und WIPE_USER_AUXILIARY_DATA registriert werden.</span><span class="sxs-lookup"><span data-stu-id="31d69-738">An app should never register for both WIPE_USER_DATA and WIPE_USER_AUXILIARY_DATA.</span></span>

## <a name="enabling-mam-targeted-configuration-for-your-android-applications-optional"></a><span data-ttu-id="31d69-739">Aktivieren der MAM-Zielkonfiguration für Ihre Android-Anwendungen (optional)</span><span class="sxs-lookup"><span data-stu-id="31d69-739">Enabling MAM targeted configuration for your Android applications (optional)</span></span>
<span data-ttu-id="31d69-740">Anwendungsspezifische Schlüssel-wert-Paare können in der Intune-Konsole konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="31d69-740">Application-specific key-value pairs may be configured in the Intune console.</span></span> <span data-ttu-id="31d69-741">Diese Schlüssel-Wert-Paare werden von Intune gar nicht übersetzt, sondern einfach an die App übergeben.</span><span class="sxs-lookup"><span data-stu-id="31d69-741">These key-value pairs are not interpreted by Intune at all, but are simply passed on to the app.</span></span> <span data-ttu-id="31d69-742">Anwendungen, die eine solche Konfiguration erhalten wollen, verwenden dazu die `MAMAppConfigManager`- und `MAMAppConfig`-Klassen.</span><span class="sxs-lookup"><span data-stu-id="31d69-742">Applications which want to receive such configuration can use the `MAMAppConfigManager` and `MAMAppConfig` classes to do so.</span></span> <span data-ttu-id="31d69-743">Wenn mehrere Richtlinie für dieselbe App vorgesehen sind, gibt es womöglich mehrere konfliktverursachende Werte für denselben Schlüssel.</span><span class="sxs-lookup"><span data-stu-id="31d69-743">If multiple policies are targeted at the same app, there may be multiple conflicting values available for the same key.</span></span>

### <a name="example"></a><span data-ttu-id="31d69-744">Beispiel</span><span class="sxs-lookup"><span data-stu-id="31d69-744">Example</span></span>
```
MAMAppConfigManager configManager = MAMComponents.get(MAMAppConfigManager.class);
String identity = "user@contoso.com"
MAMAppConfig appConfig = configManager.getAppConfig(identity);
LOGGER.info("App Config Data = " + (appConfig == null ? "null" : appConfig.getFullData()));
String valueToUse = null;
if (appConfig.hasConflict("foo")) {
    List<String> values = appConfig.getAllStringsForKey("foo");
    for (String value : values) {
        if (isCorrectValue(value)) {
            valueToUse = value;
        }
    }
} else {
    valueToUse = appConfig.getStringForKey("foo", MAMAppConfig.StringQueryType.Any);
}
LOGGER.info("Found value " + valueToUse);
```

### <a name="mamappconfig-reference"></a><span data-ttu-id="31d69-745">MAMAppConfig-Referenz</span><span class="sxs-lookup"><span data-stu-id="31d69-745">MAMAppConfig Reference</span></span>

```
public interface MAMAppConfig {
    /**
     * Conflict resolution types for Boolean values.
     */
    enum BooleanQueryType {
        /**
         * In case of conflict, arbitrarily picks one. This is not guaranteed to return the same value every time.
         */
        Any,
        /**
         * In case of conflict, returns true if any of the values are true.
         */
        Or,
        /**
         * In case of conflict, returns false if any of the values are false.
         */
        And
    }

    /**
     * Conflict resolution types for integer and double values.
     */
    enum NumberQueryType {
        /**
         * In case of conflict, arbitrarily picks one. This is not guaranteed to return the same value every time.
         */
        Any,
        /**
         * In case of conflict, returns the minimum Integer.
         */
        Min,
        /**
         * In case of conflict, returns the maximum Integer.
         */
        Max
    }

    /**
     * Conflict resolution types for Strings.
     */
    enum StringQueryType {
        /**
         * In case of conflict, arbitrarily picks one. This is not guaranteed to return the same value every time.
         */
        Any,
        /**
         * In case of conflict, returns the first result ordered alphabetically.
         */
        Min,
        /**
         * In case of conflict, returns the last result ordered alphabetically.
         */
        Max
    }

    /**
     * Retrieve the List of Dictionaries containing all the custom
     *  config data sent by the MAMService. This will return every
     * Application Configuration setting available for this user, one
     *  mapping for each policy applied to the user.
     */
    List<Map<String, String>> getFullData();

    /**
     * Returns true if there is more than one targeted custom config setting for the key provided. 
     */
    boolean hasConflict(String key);

    /**
     * @return a Boolean value for the given key if it can be coerced into a Boolean, or 
     * null if none exists or it cannot be coerced.
     */
    Boolean getBooleanForKey(String key, BooleanQueryType queryType);

    /**
     * @return a Long value for the given key if it can be coerced into a Long, or null if none exists or it cannot be coerced.
     */
    Long getIntegerForKey(String key, NumberQueryType queryType);

    /**
     * @return a Double value for the given key if it can be coerced into a Double, or null if none exists or it cannot be coerced.
     */
    Double getDoubleForKey(String key, NumberQueryType queryType);

    /**
     * @return a String value for the given key, or null if none exists.
     */
    String getStringForKey(String key, StringQueryType queryType);

    /**
     * Like getBooleanForKey except returns all values if multiple are present.
     */
    List<Boolean> getAllBooleansForKey(String key);

    /**
     * Like getIntegerForKey except returns all values if multiple are present.
     */
    List<Long> getAllIntegersForKey(String key);

    /**
     * Like getDoubleForKey except returns all values if multiple are present.
     */
    List<Double> getAllDoublesForKey(String key);

    /**
     * Like getStringForKey except returns all values if multiple are present.
     */
    List<String> getAllStringsForKey(String key);
}
```

### <a name="notification"></a><span data-ttu-id="31d69-746">Benachrichtigung</span><span class="sxs-lookup"><span data-stu-id="31d69-746">Notification</span></span>
<span data-ttu-id="31d69-747">Die App-Konfiguration fügt einen neuen Benachrichtigungstyp hinzu:</span><span class="sxs-lookup"><span data-stu-id="31d69-747">App config adds a new notification type:</span></span>
* <span data-ttu-id="31d69-748">**REFRESH_APP_CONFIG**: Diese Benachrichtigung wird in `MAMUserNotification` gesendet und informiert die App, dass neue App-Konfigurationsdaten verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="31d69-748">**REFRESH_APP_CONFIG**: This notification is sent in a `MAMUserNotification` and informs the app that new app config data is available.</span></span>

<span data-ttu-id="31d69-749">Weitere Informationen zu den Funktionen der Graph-API in Bezug auf die MAM-Zielkonfigurationswerte finden Sie unter [Graph API Reference MAM Targeted Config (Graph-API-Referenz für MAM-Zielkonfigurationen)](https://graph.microsoft.io/en-us/docs/api-reference/beta/api/intune_mam_targetedmanagedappconfiguration_create).</span><span class="sxs-lookup"><span data-stu-id="31d69-749">For more information about the capabilities of the Graph API with respect to the MAM targeted configuration values, see [Graph API Reference MAM Targeted Config](https://graph.microsoft.io/en-us/docs/api-reference/beta/api/intune_mam_targetedmanagedappconfiguration_create).</span></span> <br>

<span data-ttu-id="31d69-750">Weitere Informationen zum Erstellen einer MAM-Zielkonfigurationsrichtlinie für Apps in Android finden Sie im Abschnitt zu MAM-Zielkonfiguration für Apps unter [How to use Microsoft Intune app configuration policies for Android (Verwenden von Microsoft Intune-App-Konfigurationsrichtlinien für Android for Work)](https://docs.microsoft.com/en-us/intune/app-configuration-policies-use-android).</span><span class="sxs-lookup"><span data-stu-id="31d69-750">For more information about how to create a MAM targeted app configuration policy in Android, see the section on MAM targeted app config in [How to use Microsoft Intune app configuration policies for Android](https://docs.microsoft.com/en-us/intune/app-configuration-policies-use-android).</span></span>

## <a name="style-customization-optional"></a><span data-ttu-id="31d69-751">Anpassung von Formatvorlagen und Stil (optional)</span><span class="sxs-lookup"><span data-stu-id="31d69-751">Style Customization (optional)</span></span>

<span data-ttu-id="31d69-752">Vom MAM SDK generierte Ansichten können visuell angepasst werden, um der App noch genauer zu entsprechen.</span><span class="sxs-lookup"><span data-stu-id="31d69-752">Views generated by the MAM SDK can be visually customized to more closely match the app in which it is integrated.</span></span> <span data-ttu-id="31d69-753">Sie können primäre, sekundäre und Hintergrundfarben sowie die Größe des App-Logos anpassen.</span><span class="sxs-lookup"><span data-stu-id="31d69-753">You can customize primary, secondary, and background colors, as well as the size of the app logo.</span></span> <span data-ttu-id="31d69-754">Diese Anpassung von Formatvorlagen und Stil ist optional und es werden Standardwerte verwendet, wenn kein benutzerdefinierter Stil konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="31d69-754">This style customization is optional and defaults will be used if no custom style is configured.</span></span>


### <a name="how-to-customize"></a><span data-ttu-id="31d69-755">Vorgehensweise beim Anpassen</span><span class="sxs-lookup"><span data-stu-id="31d69-755">How to customize</span></span>
<span data-ttu-id="31d69-756">Damit Formatvorlagen- und Stiländerungen auf Intune MAM-Ansichten angewendet werden, müssen Sie zuerst eine XML-Datei für die Außerkraftsetzung von Formatvorlagen und Stil erstellen.</span><span class="sxs-lookup"><span data-stu-id="31d69-756">In order to have style changes apply to the Intune MAM views, you must first create a style override XML file.</span></span> <span data-ttu-id="31d69-757">Diese Datei sollte im Verzeichnis „/res/xml“ Ihrer App gespeichert werden, und Sie können ihr einen beliebigen Namen zuweisen.</span><span class="sxs-lookup"><span data-stu-id="31d69-757">This file should be placed in the “/res/xml” directory of your app and you may name it whatever you like.</span></span> <span data-ttu-id="31d69-758">Das folgende Beispiel veranschaulicht das Format, das diese Datei einhalten muss.</span><span class="sxs-lookup"><span data-stu-id="31d69-758">Below is an example of the format this file needs to follow.</span></span>

```xml
<?xml version="1.0" encoding="utf-8"?>
<styleOverrides>
    <item
        name="foreground_color"
        resource="@color/red"/>
    <item
        name="accent_color"
        resource="@color/blue"/>
    <item
        name="background_color"
        resource="@color/green"/>
    <item
        name="logo_image"
        resource="@drawable/app_logo"/>
</styleOverrides>

```

<span data-ttu-id="31d69-759">Sie müssen bereits in Ihrer App vorhandene Ressourcen wiederverwenden.</span><span class="sxs-lookup"><span data-stu-id="31d69-759">You must reuse resources that already exist within your app.</span></span> <span data-ttu-id="31d69-760">Sie müssen z. B. die Farbe „Grün“ in der Datei „colors.xml“ definieren und hier darauf verweisen.</span><span class="sxs-lookup"><span data-stu-id="31d69-760">For example, you must define the color green in the colors.xml file and reference it here.</span></span> <span data-ttu-id="31d69-761">Sie können nicht den hexadezimalen Farbcode „#0000ff“ verwenden.</span><span class="sxs-lookup"><span data-stu-id="31d69-761">You cannot use the Hex color code “#0000ff."</span></span> <span data-ttu-id="31d69-762">Die maximale Größe für das App-Logo beträgt 110 dip (dp).</span><span class="sxs-lookup"><span data-stu-id="31d69-762">The maximum size for the app logo is 110 dip (dp).</span></span> <span data-ttu-id="31d69-763">Sie können ein kleineres Logobild verwenden, aber die maximale Größe sorgt für optimale Ansichtsergebnisse.</span><span class="sxs-lookup"><span data-stu-id="31d69-763">You may use a smaller logo image, but adhering to the maximum size will yield the best looking results.</span></span> <span data-ttu-id="31d69-764">Wenn Sie den Grenzwert von 110 dip überschreiten, wird das Bild herunterskaliert und möglicherweise unscharf angezeigt.</span><span class="sxs-lookup"><span data-stu-id="31d69-764">If you exceed the 110 dip limit, the image will scale down and possibly cause blurring.</span></span>

<span data-ttu-id="31d69-765">Nachfolgend finden Sie die vollständige Liste der zulässigen Stilattribute, die von ihnen gesteuerten Elemente der Benutzeroberfläche, ihre XML-Elementattributnamen und den Typ der Ressource, der für die einzelnen Attribute erwartet wird.</span><span class="sxs-lookup"><span data-stu-id="31d69-765">Below is the complete list of allowed style attributes, the UI elements they control, their XML attribute item names, and the type of resource expected for each.</span></span>

|<span data-ttu-id="31d69-766">Stilattribut</span><span class="sxs-lookup"><span data-stu-id="31d69-766">Style attribute</span></span> | <span data-ttu-id="31d69-767">Betroffene Elemente der Benutzeroberfläche</span><span class="sxs-lookup"><span data-stu-id="31d69-767">UI elements affected</span></span> | <span data-ttu-id="31d69-768">Attributelementname</span><span class="sxs-lookup"><span data-stu-id="31d69-768">Attribute item name</span></span> | <span data-ttu-id="31d69-769">Erwarteter Ressourcentyp</span><span class="sxs-lookup"><span data-stu-id="31d69-769">Expected resource type</span></span> |
| -- | -- | -- | -- |
| <span data-ttu-id="31d69-770">Hintergrundfarbe</span><span class="sxs-lookup"><span data-stu-id="31d69-770">Background color</span></span> | <span data-ttu-id="31d69-771">Hintergrundfarbe für PIN-Bildschirm</span><span class="sxs-lookup"><span data-stu-id="31d69-771">PIN screen background color</span></span> <Br><span data-ttu-id="31d69-772">Füllfarbe für PIN-Feld</span><span class="sxs-lookup"><span data-stu-id="31d69-772">PIN box fill color</span></span> | <span data-ttu-id="31d69-773">background_color</span><span class="sxs-lookup"><span data-stu-id="31d69-773">background_color</span></span> | <span data-ttu-id="31d69-774">Farbe</span><span class="sxs-lookup"><span data-stu-id="31d69-774">Color</span></span> |
| <span data-ttu-id="31d69-775">Vordergrundfarbe</span><span class="sxs-lookup"><span data-stu-id="31d69-775">Foreground color</span></span> | <span data-ttu-id="31d69-776">Vordergrundtextfarbe</span><span class="sxs-lookup"><span data-stu-id="31d69-776">Foreground text color</span></span> <br> <span data-ttu-id="31d69-777">Rahmen des PIN-Felds im Standardzustand</span><span class="sxs-lookup"><span data-stu-id="31d69-777">PIN box border in default state</span></span> <br> <span data-ttu-id="31d69-778">Zeichen (einschließlich verborgener Zeichen) im PIN-Feld, wenn Benutzer eine PIN eingibt</span><span class="sxs-lookup"><span data-stu-id="31d69-778">Characters (including obfuscated characters) in PIN box when user enters a PIN</span></span>| <span data-ttu-id="31d69-779">foreground_color</span><span class="sxs-lookup"><span data-stu-id="31d69-779">foreground_color</span></span> | <span data-ttu-id="31d69-780">Farbe</span><span class="sxs-lookup"><span data-stu-id="31d69-780">Color</span></span>|
| <span data-ttu-id="31d69-781">Akzentfarbe</span><span class="sxs-lookup"><span data-stu-id="31d69-781">Accent color</span></span> | <span data-ttu-id="31d69-782">PIN-Feldrahmen (markiert)</span><span class="sxs-lookup"><span data-stu-id="31d69-782">PIN box border when highlighted</span></span> <br> <span data-ttu-id="31d69-783">Links</span><span class="sxs-lookup"><span data-stu-id="31d69-783">Hyperlinks</span></span> |<span data-ttu-id="31d69-784">accent_color</span><span class="sxs-lookup"><span data-stu-id="31d69-784">accent_color</span></span> | <span data-ttu-id="31d69-785">Farbe</span><span class="sxs-lookup"><span data-stu-id="31d69-785">Color</span></span> |
| <span data-ttu-id="31d69-786">App-Logo</span><span class="sxs-lookup"><span data-stu-id="31d69-786">App logo</span></span> | <span data-ttu-id="31d69-787">Großes Symbol, das auf dem PIN-Bildschirm der Intune-App angezeigt wird</span><span class="sxs-lookup"><span data-stu-id="31d69-787">Large icon that appears in the Intune app PIN screen</span></span> | <span data-ttu-id="31d69-788">logo_image</span><span class="sxs-lookup"><span data-stu-id="31d69-788">logo_image</span></span> | <span data-ttu-id="31d69-789">Zeichenbar</span><span class="sxs-lookup"><span data-stu-id="31d69-789">Drawable</span></span> |

## <a name="limitations"></a><span data-ttu-id="31d69-790">Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="31d69-790">Limitations</span></span>

### <a name="file-size-limitations"></a><span data-ttu-id="31d69-791">Einschränkungen der Dateigröße</span><span class="sxs-lookup"><span data-stu-id="31d69-791">File Size limitations</span></span>

<span data-ttu-id="31d69-792">Bei großen Codebasen, die ohne [ProGuard](http://proguard.sourceforge.net/) ausgeführt werden, werden die Einschränkungen des Dalvik-Formats für ausführbare Dateien zu einem Problem.</span><span class="sxs-lookup"><span data-stu-id="31d69-792">For large code bases that run without [ProGuard](http://proguard.sourceforge.net/), the limitations of the Dalvik executable file format become an issue.</span></span> <span data-ttu-id="31d69-793">Insbesondere können die folgenden Einschränkungen auftreten:</span><span class="sxs-lookup"><span data-stu-id="31d69-793">Specifically, the following limitations may occur:</span></span>

1.  <span data-ttu-id="31d69-794">Einschränkung auf 65 KB bei Feldern.</span><span class="sxs-lookup"><span data-stu-id="31d69-794">The 65K limit on fields.</span></span>
2.  <span data-ttu-id="31d69-795">Einschränkung auf 65 KB bei Methoden.</span><span class="sxs-lookup"><span data-stu-id="31d69-795">The 65K limit on methods.</span></span>

### <a name="policy-enforcement-limitations"></a><span data-ttu-id="31d69-796">Einschränkungen der Richtlinienerzwingung</span><span class="sxs-lookup"><span data-stu-id="31d69-796">Policy enforcement limitations</span></span>

* <span data-ttu-id="31d69-797">**Bildschirmaufnahme**: Das SDK kann keinen neuen Wert für die Bildschirmaufnahmeeinstellung in "Activities" erzwingen, die bereits "Activity.onCreate" durchlaufen haben.</span><span class="sxs-lookup"><span data-stu-id="31d69-797">**Screen Capture**: The SDK is unable to enforce a new screen capture setting value in Activities that have already gone through Activity.onCreate.</span></span> <span data-ttu-id="31d69-798">Dies kann dazu führen, dass für eine gewisse Zeit nach dem Konfigurieren der App zur Deaktivierung von Bildschirmaufnahmen weiterhin Bildschirmaufnahmen erstellt werden können.</span><span class="sxs-lookup"><span data-stu-id="31d69-798">This can result in a period of time where the app has been configured to disable screenshots but screenshots can still be taken.</span></span>

* <span data-ttu-id="31d69-799">**Verwenden von Inhaltsresolvers**: Durch die Intune-Richtlinie zum Übertragen oder Empfangen kann die Verwendung eines Inhaltsresolvers für den Zugriff auf den Inhaltsanbieter in einer anderen App ganz oder teilweise blockiert werden.</span><span class="sxs-lookup"><span data-stu-id="31d69-799">**Using Content Resolvers**: The "transfer or receive" Intune policy may block or partially block the use of a content resolver to access the content provider in another app.</span></span> <span data-ttu-id="31d69-800">Dadurch geben ContentResolver-Methoden NULL oder einen Fehlerwert zurück (z. B. gibt `openOutputStream` bei Blockierung `FileNotFoundException` zurück).</span><span class="sxs-lookup"><span data-stu-id="31d69-800">This will cause ContentResolver methods to return null or throw a failure value (e.g. `openOutputStream` will throw `FileNotFoundException` if blocked).</span></span> <span data-ttu-id="31d69-801">Die App kann feststellen, ob ein Fehler beim Schreiben von Daten durch einen Inhaltsresolver durch die Richtlinie verursacht wurde (oder würde), indem folgender Aufruf ausgeführt wird:</span><span class="sxs-lookup"><span data-stu-id="31d69-801">The app can determine whether a failure to write data through a content resolver was caused by policy (or would be caused by policy) by making the call:</span></span>
    ```java
    MAMPolicyManager.getPolicy(currentActivity).getIsSaveToLocationAllowed(contentURI);
    ```
    <span data-ttu-id="31d69-802">oder wenn es keine zugehörige Aktivität gibt</span><span class="sxs-lookup"><span data-stu-id="31d69-802">or if there is no associated activity</span></span>

    ```java
    MAMPolicyManager.getPolicy().getIsSaveToLocationAllowed(contentURI);
    ```

    <span data-ttu-id="31d69-803">Im zweiten Fall müssen Apps mit mehreren Identitäten unbedingt die Threadidentität ordnungsgemäß festlegen (oder eine explizite Identität an den `getPolicy`-Aufruf übergeben).</span><span class="sxs-lookup"><span data-stu-id="31d69-803">In this second case, multi-identity apps must take care to set the thread identity appropriately (or pass an explicit identity to the `getPolicy` call).</span></span>
    
### <a name="exported-services"></a><span data-ttu-id="31d69-804">Exportierte Dienste</span><span class="sxs-lookup"><span data-stu-id="31d69-804">Exported services</span></span>

 <span data-ttu-id="31d69-805">Die im Intune App SDK enthaltene Datei „AndroidManifest.xml“ enthält **MAMNotificationReceiverService**. Dies muss ein exportierter Dienst sein, damit das Unternehmensportal Benachrichtigungen an eine App mit aktiviertem Intune App SDK senden kann.</span><span class="sxs-lookup"><span data-stu-id="31d69-805">The AndroidManifest.xml file included in the Intune App SDK contains **MAMNotificationReceiverService**, which must be an exported service to allow the Company Portal to send notifications to an enlightened app.</span></span> <span data-ttu-id="31d69-806">Der Dienst prüft den Aufrufer, um sicherzustellen, dass nur das Unternehmensportal Benachrichtigungen senden kann.</span><span class="sxs-lookup"><span data-stu-id="31d69-806">The service checks the caller to ensure that only the Company Portal is allowed to send notifications.</span></span>

### <a name="reflection-limitations"></a><span data-ttu-id="31d69-807">Einschränkungen bei der Reflektion</span><span class="sxs-lookup"><span data-stu-id="31d69-807">Reflection limitations</span></span>
<span data-ttu-id="31d69-808">Einige der MAM-Basisklassen (z.B. MAMActivity und MAMDocumentsProvider) enthalten Methoden (basierend auf den ursprünglichen Android-Basisklassen), die Parameter- oder Rückgabetypen verwenden, die nur oberhalb bestimmter API-Ebenen vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="31d69-808">Some of the MAM base classes (e.g. MAMActivity, MAMDocumentsProvider) contain methods (based on the original Android base classes) which use parameter or return types only present above certain API levels.</span></span> <span data-ttu-id="31d69-809">Aus diesem Grund ist es möglicherweise nicht immer möglich, alle Methoden von App-Komponenten mit Hilfe von Reflektion aufzuzählen.</span><span class="sxs-lookup"><span data-stu-id="31d69-809">For this reason, it may not always be possible to use reflection to enumerate all methods of app components.</span></span> <span data-ttu-id="31d69-810">Diese Einschränkung ist nicht auf MAM beschränkt. Sie gilt auch, wenn die App selbst diese Methoden aus den Android-Basisklassen implementiert.</span><span class="sxs-lookup"><span data-stu-id="31d69-810">This restriction is not limited to MAM, it is the same restriction which would apply if the app itself implemented these methods from the Android base classes.</span></span>
## <a name="expectations-of-the-sdk-consumer"></a><span data-ttu-id="31d69-811">Erwartungen des SDK-Consumers</span><span class="sxs-lookup"><span data-stu-id="31d69-811">Expectations of the SDK consumer</span></span>

<span data-ttu-id="31d69-812">Das Intune SDK verwaltet des von der Android-API bereitgestellten Vertrag; jedoch ist es möglich, dass aufgrund der Richtlinienerzwingung häufiger Fehlerbedingungen ausgelöst werden.</span><span class="sxs-lookup"><span data-stu-id="31d69-812">The Intune SDK maintains the contract provided by the Android API, though failure conditions may be triggered more frequently as a result of policy enforcement.</span></span> <span data-ttu-id="31d69-813">Durch diese bewährten Methoden für Android wird die Wahrscheinlichkeit, dass Fehler auftreten, gemindert:</span><span class="sxs-lookup"><span data-stu-id="31d69-813">These Android best practices will reduce the likelihood of failure:</span></span>

* <span data-ttu-id="31d69-814">Es besteht die höhere Wahrscheinlichkeit, dass Android SDK-Funktionen, die möglicherweise NULL zurückgeben, jetzt NULL sind.</span><span class="sxs-lookup"><span data-stu-id="31d69-814">Android SDK functions that may return null have a higher likelihood of being null now.</span></span>  <span data-ttu-id="31d69-815">Um Probleme zu minimieren, stellen Sie sicher, dass NULL-Überprüfungen an den richtigen Stellen stattfinden.</span><span class="sxs-lookup"><span data-stu-id="31d69-815">To minimize issues, ensure that null checks are in the right places.</span></span>

* <span data-ttu-id="31d69-816">Funktionen, die überprüft werden können, müssen über die zugehörigen MAM-Ersatz-APIs überprüft werden.</span><span class="sxs-lookup"><span data-stu-id="31d69-816">Features that can be checked for must be checked for through their MAM replacement APIs.</span></span>

* <span data-ttu-id="31d69-817">Alle abgeleiteten Funktionen müssen an ihre übergeordneten Klassenversionen einen durchgehenden Aufruf ausführen.</span><span class="sxs-lookup"><span data-stu-id="31d69-817">Any derived functions must call through to their super class versions.</span></span>

* <span data-ttu-id="31d69-818">Vermeiden Sie eine nicht eindeutige Verwendung von APIs.</span><span class="sxs-lookup"><span data-stu-id="31d69-818">Avoid use of any API in an ambiguous way.</span></span> <span data-ttu-id="31d69-819">So führt beispielsweise die Verwendung von `Activity.startActivityForResult` ohne Überprüfung von „requestCode“ zu unerwartetem Verhalten.</span><span class="sxs-lookup"><span data-stu-id="31d69-819">For example, using `Activity.startActivityForResult` without checking the requestCode will cause strange behavior.</span></span>

## <a name="telemetry"></a><span data-ttu-id="31d69-820">Telemetrie</span><span class="sxs-lookup"><span data-stu-id="31d69-820">Telemetry</span></span>

<span data-ttu-id="31d69-821">Das Intune App SDK für Android kontrolliert nicht die Datensammlung über Ihre App.</span><span class="sxs-lookup"><span data-stu-id="31d69-821">The Intune App SDK for Android does not control data collection from your app.</span></span> <span data-ttu-id="31d69-822">Standardmäßig protokolliert die Unternehmensportal-Anwendung Telemetriedaten.</span><span class="sxs-lookup"><span data-stu-id="31d69-822">The Company Portal application logs telemetry data by default.</span></span> <span data-ttu-id="31d69-823">Diese Daten werden an Microsoft Intune gesendet.</span><span class="sxs-lookup"><span data-stu-id="31d69-823">This data is sent to Microsoft Intune.</span></span> <span data-ttu-id="31d69-824">Gemäß der Microsoft-Richtlinie sammeln wir keine personenbezogenen Informationen (PII).</span><span class="sxs-lookup"><span data-stu-id="31d69-824">As per Microsoft Policy, we do not collect any personally identifiable information (PII).</span></span>

> [!NOTE]
> <span data-ttu-id="31d69-825">Wenn Benutzer sich dazu entschließen, diese Daten nicht zu senden, müssen sie die Telemetrie unter „Einstellungen“ in der Unternehmensportal-App deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="31d69-825">If end users choose not to send this data, they must turn off telemetry under Settings on the Company Portal app.</span></span> <span data-ttu-id="31d69-826">Weitere Informationen finden Sie unter [Deaktivieren der Erfassung von Nutzungsdaten durch Microsoft](https://docs.microsoft.com/en-us/intune-user-help/turn-off-microsoft-usage-data-collection-android).</span><span class="sxs-lookup"><span data-stu-id="31d69-826">To learn more, see [Turn off Microsoft usage data collection](https://docs.microsoft.com/en-us/intune-user-help/turn-off-microsoft-usage-data-collection-android).</span></span> 

## <a name="recommended-android-best-practices"></a><span data-ttu-id="31d69-827">Empfohlene und bewährte Methoden für Android</span><span class="sxs-lookup"><span data-stu-id="31d69-827">Recommended Android best practices</span></span>

* <span data-ttu-id="31d69-828">Alle Bibliotheksprojekte sollten dasselbe "android:package" gemeinsam verwenden, wenn dies möglich ist.</span><span class="sxs-lookup"><span data-stu-id="31d69-828">All library projects should share the same android:package where possible.</span></span> <span data-ttu-id="31d69-829">Dabei kommt es während der Laufzeit nicht sporadisch zu Fehlern, da es sich um ein reines Problem zur Buildzeit handelt.</span><span class="sxs-lookup"><span data-stu-id="31d69-829">This will not sporadically fail in run-time; this is purely a build-time problem.</span></span> <span data-ttu-id="31d69-830">Neuere Versionen des Intune App SDKs werden einen Teil der Redundanz beseitigen.</span><span class="sxs-lookup"><span data-stu-id="31d69-830">Newer versions of the Intune App SDK will remove some of the redundancy.</span></span>

* <span data-ttu-id="31d69-831">Verwenden Sie die neuesten Android SDK-Buildtools.</span><span class="sxs-lookup"><span data-stu-id="31d69-831">Use the newest Android SDK build tools.</span></span>

* <span data-ttu-id="31d69-832">Entfernen Sie alle nicht benötigten und nicht verwendeten Bibliotheken (z. B. „android.support.v4“)</span><span class="sxs-lookup"><span data-stu-id="31d69-832">Remove all unnecessary and unused libraries (e.g. android.support.v4)</span></span>
