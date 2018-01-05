---
title: "Umschließen von Android-Apps mit dem Intune App Wrapping Tool"
description: "In diesem Artikel erfahren Sie, wie Sie Ihre Android-Apps umschließen, ohne den Code der App selbst zu ändern. Bereiten Sie die Apps vor, damit Sie Verwaltungsrichtlinien für mobile Apps anwenden können."
keywords: 
author: erikre
ms.author: erikre
manager: angrobe
ms.date: 07/07/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e9c349c8-51ae-4d73-b74a-6173728a520b
ms.reviewer: oldang
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 2a349595fc5711b8754d635d3cc1890e833b2701
ms.sourcegitcommit: e37e916e2bf14f092d3a767bc90d68c181d739fb
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/03/2018
---
# <a name="prepare-android-apps-for-app-protection-policies-with-the-intune-app-wrapping-tool"></a><span data-ttu-id="25814-104">Vorbereiten von Android-Apps für App-Schutzrichtlinien mit dem Intune App Wrapping Tool</span><span class="sxs-lookup"><span data-stu-id="25814-104">Prepare Android apps for app protection policies with the Intune App Wrapping Tool</span></span>

[!INCLUDE[both-portals](./includes/note-for-both-portals.md)]

<span data-ttu-id="25814-105">Verwenden Sie das Microsoft Intune App Wrapping Tool für Android zum Ändern des Verhaltens Ihrer internen Android-Apps, indem Sie die Features der App einschränken, ohne den eigentlichen Code der App zu ändern.</span><span class="sxs-lookup"><span data-stu-id="25814-105">Use the Microsoft Intune App Wrapping Tool for Android to change the behavior of your in-house Android apps by restricting features of the app without changing the code of the app itself.</span></span>

<span data-ttu-id="25814-106">Das Tool ist eine Windows-Befehlszeilenanwendung, die in PowerShell ausgeführt wird und einen Wrapper um die Android-App erstellt.</span><span class="sxs-lookup"><span data-stu-id="25814-106">The tool is a Windows command-line application that runs in PowerShell and creates a wrapper around your Android app.</span></span> <span data-ttu-id="25814-107">Nachdem der Wrapper um die App erstellt wurde, können Sie die App-Funktionalität ändern, indem Sie in Intune [Verwaltungsrichtlinien für mobile Anwendungen](/intune-classic/deploy-use/configure-and-deploy-mobile-application-management-policies-in-the-microsoft-intune-console) konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="25814-107">After the app is wrapped, you can change the app’s functionality by configuring [mobile application management policies](/intune-classic/deploy-use/configure-and-deploy-mobile-application-management-policies-in-the-microsoft-intune-console) in Intune.</span></span>


<span data-ttu-id="25814-108">Lesen Sie vor dem Ausführen des Tools die [Sicherheitsüberlegungen für das Ausführen des App Wrapping Tools](#security-considerations-for-running-the-app-wrapping-tool).</span><span class="sxs-lookup"><span data-stu-id="25814-108">Before running the tool, review [Security considerations for running the App Wrapping Tool](#security-considerations-for-running-the-app-wrapping-tool).</span></span> <span data-ttu-id="25814-109">Sie können das Tool von der GitHub-Seite [Microsoft Intune App Wrapping Tool for Android](https://github.com/msintuneappsdk/intune-app-wrapping-tool-android) herunterladen.</span><span class="sxs-lookup"><span data-stu-id="25814-109">To download the tool, go to the [Microsoft Intune App Wrapping Tool for Android](https://github.com/msintuneappsdk/intune-app-wrapping-tool-android) on GitHub.</span></span>



## <a name="fulfill-the-prerequisites-for-using-the-app-wrapping-tool"></a><span data-ttu-id="25814-110">Erfüllen der Voraussetzungen zur Verwendung des App Wrapping Tools</span><span class="sxs-lookup"><span data-stu-id="25814-110">Fulfill the prerequisites for using the App Wrapping Tool</span></span>

-   <span data-ttu-id="25814-111">Sie müssen das App Wrapping Tool auf einem Windows-Computer unter Windows 7 oder höher ausführen.</span><span class="sxs-lookup"><span data-stu-id="25814-111">You must run the App Wrapping Tool on a Windows computer running Windows 7 or later.</span></span>

-   <span data-ttu-id="25814-112">Die Eingabe-App muss ein gültiges Android-Anwendungspaket mit der Dateierweiterung „APK“ sein und folgende Kriterien aufweisen:</span><span class="sxs-lookup"><span data-stu-id="25814-112">Your input app must be a valid Android application package with the file extension .apk and:</span></span>

    -   <span data-ttu-id="25814-113">Darf nicht verschlüsselt sein.</span><span class="sxs-lookup"><span data-stu-id="25814-113">It cannot be encrypted.</span></span>
    -   <span data-ttu-id="25814-114">Darf nicht zuvor bereits vom Intune App Wrapping Tool umschlossen worden sein.</span><span class="sxs-lookup"><span data-stu-id="25814-114">It must not have previously been wrapped by the Intune App Wrapping Tool.</span></span>
    -   <span data-ttu-id="25814-115">Muss für Android 4.0 oder höher geschrieben sein.</span><span class="sxs-lookup"><span data-stu-id="25814-115">It must be written for Android 4.0 or later.</span></span>

-   <span data-ttu-id="25814-116">Die App muss von Ihrem oder für Ihr Unternehmen entwickelt werden.</span><span class="sxs-lookup"><span data-stu-id="25814-116">The app must be developed by or for your company.</span></span> <span data-ttu-id="25814-117">Sie können dieses Tool nicht für aus dem Google Play Store heruntergeladene Apps verwenden.</span><span class="sxs-lookup"><span data-stu-id="25814-117">You cannot use this tool on apps downloaded from the Google Play Store.</span></span>

-   <span data-ttu-id="25814-118">Um das App Wrapping Tool auszuführen, müssen Sie die neueste Version der [Java Runtime Environment](http://java.com/download/) installieren und sicherstellen, dass die Java-Pfadvariable in den Windows-Umgebungsvariablen auf C:\ProgramData\Oracle\Java\javapath festgelegt wurde.</span><span class="sxs-lookup"><span data-stu-id="25814-118">To run the App Wrapping Tool, you must install the latest version of the [Java Runtime Environment](http://java.com/download/) and then ensure that the Java path variable has been set to C:\ProgramData\Oracle\Java\javapath in your Windows environment variables.</span></span> <span data-ttu-id="25814-119">Weitere Informationen finden Sie in der [Java-Dokumentation](http://java.com/download/help/).</span><span class="sxs-lookup"><span data-stu-id="25814-119">For more help, see the [Java documentation](http://java.com/download/help/).</span></span>

    > [!NOTE]
    > <span data-ttu-id="25814-120">In einigen Fällen kann die 32-Bit-Version von Java zu Speicherproblemen führen.</span><span class="sxs-lookup"><span data-stu-id="25814-120">In some cases, the 32-bit version of Java may result in memory issues.</span></span> <span data-ttu-id="25814-121">Es ist eine gute Idee, die 64-Bit-Version zu installieren.</span><span class="sxs-lookup"><span data-stu-id="25814-121">It's a good idea to install the 64-bit version.</span></span>

- <span data-ttu-id="25814-122">Für Android müssen alle App-Pakete (APK-Dateien) signiert sein.</span><span class="sxs-lookup"><span data-stu-id="25814-122">Android requires all app packages (.apk) to be signed.</span></span> <span data-ttu-id="25814-123">Informationen zum **Wiederverwenden** vorhandener Zertifikate und für allgemeine Anleitungen für Signaturzertifikate finden Sie unter [Wiederverwendung von Signaturzertifikaten und Umschließen von Apps](https://docs.microsoft.com/en-us/intune/app-wrapper-prepare-android#reusing-signing-certificates-and-wrapping-apps).</span><span class="sxs-lookup"><span data-stu-id="25814-123">For **reusing** existing certificates and overall signing certificate guidance, see [Reusing signing certificates and wrapping apps](https://docs.microsoft.com/en-us/intune/app-wrapper-prepare-android#reusing-signing-certificates-and-wrapping-apps).</span></span> <span data-ttu-id="25814-124">Das ausführbare Java-Tool „keytool.exe“ wird zum Generieren **neuer** Anmeldeinformationen verwendet, die zum Signieren der umschlossenen Ausgabe-App erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="25814-124">The Java executable keytool.exe is used to generate **new** credentials needed to sign the wrapped output app.</span></span> <span data-ttu-id="25814-125">Kennwörter, die festgelegt werden, müssen sicher sein. Notieren Sie sich diese Kennwörter jedoch, denn sie werden benötigt, um das App Wrapping Tool auszuführen.</span><span class="sxs-lookup"><span data-stu-id="25814-125">Any passwords that are set must be secure, but make a note of them because they're needed to run the App Wrapping Tool.</span></span>

## <a name="install-the-app-wrapping-tool"></a><span data-ttu-id="25814-126">Installieren des App Wrapping Tools</span><span class="sxs-lookup"><span data-stu-id="25814-126">Install the App Wrapping Tool</span></span>

1.  <span data-ttu-id="25814-127">Laden Sie die Installationsdatei „InstallAWT.exe“ für das Intune App Wrapping Tool für Android aus dem [GitHub-Repository](https://github.com/msintuneappsdk/intune-app-wrapping-tool-android) auf einen Windows-Computer herunter.</span><span class="sxs-lookup"><span data-stu-id="25814-127">From the [GitHub repository](https://github.com/msintuneappsdk/intune-app-wrapping-tool-android), download the installation file InstallAWT.exe for the Intune App Wrapping Tool for Android to a Windows computer.</span></span> <span data-ttu-id="25814-128">Öffnen Sie die Installationsdatei.</span><span class="sxs-lookup"><span data-stu-id="25814-128">Open the installation file.</span></span>

2.  <span data-ttu-id="25814-129">Akzeptieren Sie den Lizenzvertrag, und schließen Sie die Installation ab.</span><span class="sxs-lookup"><span data-stu-id="25814-129">Accept the license agreement, then finish the installation.</span></span>

<span data-ttu-id="25814-130">Merken Sie sich den Ordner, in dem Sie das Tool installieren.</span><span class="sxs-lookup"><span data-stu-id="25814-130">Note the folder to which you installed the tool.</span></span> <span data-ttu-id="25814-131">Der Standardspeicherort lautet: C:\Programme (x86)\Microsoft Intune Mobile Application Management\Android\App Wrapping Tool.</span><span class="sxs-lookup"><span data-stu-id="25814-131">The default location is: C:\Program Files (x86)\Microsoft Intune Mobile Application Management\Android\App Wrapping Tool.</span></span>

## <a name="run-the-app-wrapping-tool"></a><span data-ttu-id="25814-132">Ausführen des App Wrapping Tools</span><span class="sxs-lookup"><span data-stu-id="25814-132">Run the App Wrapping Tool</span></span>

1. <span data-ttu-id="25814-133">Öffnen Sie auf dem Windows-Computer, auf dem Sie das App Wrapping Tool installiert haben, ein PowerShell-Fenster.</span><span class="sxs-lookup"><span data-stu-id="25814-133">On the Windows computer where you installed the App Wrapping Tool, open a PowerShell window.</span></span>

2. <span data-ttu-id="25814-134">Importieren Sie das PowerShell-Modul des App Wrapping Tools aus dem Ordner, in dem Sie das Tool installiert haben:</span><span class="sxs-lookup"><span data-stu-id="25814-134">From the folder where you installed the tool, import the App Wrapping Tool PowerShell module:</span></span>

   ```
   Import-Module .\IntuneAppWrappingTool.psm1
   ```

3. <span data-ttu-id="25814-135">Führen Sie das Tool mit dem Befehl **invoke-AppWrappingTool** aus, der die folgende Verwendungssyntax aufweist:</span><span class="sxs-lookup"><span data-stu-id="25814-135">Run the tool by using the **invoke-AppWrappingTool** command, which has the following usage syntax:</span></span>
   ```
   Invoke-AppWrappingTool [-InputPath] <String> [-OutputPath] <String> -KeyStorePath <String> -KeyStorePassword <SecureString>
   -KeyAlias <String> -KeyPassword <SecureString> [-SigAlg <String>] [<CommonParameters>]
   ```

   <span data-ttu-id="25814-136">Die folgende Tabelle führt die Eigenschaften des Befehls **invoke-AppWrappingTool** auf:</span><span class="sxs-lookup"><span data-stu-id="25814-136">The following table details the properties of the **invoke-AppWrappingTool** command:</span></span>

|<span data-ttu-id="25814-137">Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="25814-137">Property</span></span>|<span data-ttu-id="25814-138">Informationen</span><span class="sxs-lookup"><span data-stu-id="25814-138">Information</span></span>|<span data-ttu-id="25814-139">Beispiel</span><span class="sxs-lookup"><span data-stu-id="25814-139">Example</span></span>|
|-------------|--------------------|---------|
|<span data-ttu-id="25814-140">**-InputPath**&lt;String&gt;</span><span class="sxs-lookup"><span data-stu-id="25814-140">**-InputPath**&lt;String&gt;</span></span>|<span data-ttu-id="25814-141">Pfad der Android-Quelle-App (.apk).</span><span class="sxs-lookup"><span data-stu-id="25814-141">Path of the source Android app (.apk).</span></span>| |
|<span data-ttu-id="25814-142">**-OutputPath**&lt;String&gt;</span><span class="sxs-lookup"><span data-stu-id="25814-142">**-OutputPath**&lt;String&gt;</span></span>|<span data-ttu-id="25814-143">Pfad zur Android-Ausgabe-App.</span><span class="sxs-lookup"><span data-stu-id="25814-143">Path to the output Android app.</span></span> <span data-ttu-id="25814-144">Ist dies der gleiche Verzeichnispfad wie InputPath, schlägt das Verpacken fehl.</span><span class="sxs-lookup"><span data-stu-id="25814-144">If this is the same directory path as InputPath, the packaging will fail.</span></span>| |
|<span data-ttu-id="25814-145">**-KeyStorePath**&lt;String&gt;</span><span class="sxs-lookup"><span data-stu-id="25814-145">**-KeyStorePath**&lt;String&gt;</span></span>|<span data-ttu-id="25814-146">Pfad zur Keystoredatei, die das öffentliche/private Schlüsselpaar zum Signieren enthält.</span><span class="sxs-lookup"><span data-stu-id="25814-146">Path to the keystore file that has the public/private key pair for signing.</span></span>|<span data-ttu-id="25814-147">Standardmäßig werden Keystoredateien unter „C:\Programme (x86)\Java\jreX.X.X_XX\bin“ gespeichert.</span><span class="sxs-lookup"><span data-stu-id="25814-147">By default, keystore files are stored in "C:\Program Files (x86)\Java\jreX.X.X_XX\bin."</span></span> |
|<span data-ttu-id="25814-148">**-KeyStorePassword**&lt;SecureString&gt;</span><span class="sxs-lookup"><span data-stu-id="25814-148">**-KeyStorePassword**&lt;SecureString&gt;</span></span>|<span data-ttu-id="25814-149">Das Kennwort zum Entschlüsseln des KeyStore.</span><span class="sxs-lookup"><span data-stu-id="25814-149">Password used to decrypt the keystore.</span></span> <span data-ttu-id="25814-150">Für Android müssen alle Anwendungspakete (APK-Dateien) signiert sein.</span><span class="sxs-lookup"><span data-stu-id="25814-150">Android requires all application packages (.apk) to be signed.</span></span> <span data-ttu-id="25814-151">Verwenden Sie das Java-Keytool, um das KeyStorePassword zu generieren.</span><span class="sxs-lookup"><span data-stu-id="25814-151">Use Java keytool to generate the KeyStorePassword.</span></span> <span data-ttu-id="25814-152">Weitere Informationen über den Java-[Keystore](https://docs.oracle.com/javase/7/docs/api/java/security/KeyStore.html) finden Sie hier.</span><span class="sxs-lookup"><span data-stu-id="25814-152">Read more about Java [KeyStore](https://docs.oracle.com/javase/7/docs/api/java/security/KeyStore.html) here.</span></span>| |
|<span data-ttu-id="25814-153">**-KeyAlias**&lt;String&gt;</span><span class="sxs-lookup"><span data-stu-id="25814-153">**-KeyAlias**&lt;String&gt;</span></span>|<span data-ttu-id="25814-154">Der Name des Schlüssels, der zum Signieren verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="25814-154">Name of the key to be used for signing.</span></span>| |
|<span data-ttu-id="25814-155">**-KeyPassword**&lt;SecureString&gt;</span><span class="sxs-lookup"><span data-stu-id="25814-155">**-KeyPassword**&lt;SecureString&gt;</span></span>|<span data-ttu-id="25814-156">Das Kennwort zum Entschlüsseln des privaten Schlüssels, der zum Signieren verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="25814-156">Password used to decrypt the private key that will be used for signing.</span></span>| |
|<span data-ttu-id="25814-157">**-SigAlg**&lt;SecureString&gt;</span><span class="sxs-lookup"><span data-stu-id="25814-157">**-SigAlg**&lt;SecureString&gt;</span></span>| <span data-ttu-id="25814-158">(Optional) Der Name des Signaturalgorithmus, der zum Signieren verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="25814-158">(Optional) The name of the signature algorithm to be used for signing.</span></span> <span data-ttu-id="25814-159">Der Algorithmus muss mit dem privaten Schlüssel kompatibel sein.</span><span class="sxs-lookup"><span data-stu-id="25814-159">The algorithm must be compatible with the private key.</span></span>|<span data-ttu-id="25814-160">Beispiele: SHA256withRSA, SHA1withRSA</span><span class="sxs-lookup"><span data-stu-id="25814-160">Examples: SHA256withRSA, SHA1withRSA</span></span>|
| <span data-ttu-id="25814-161">**&lt;CommonParameters&gt;**</span><span class="sxs-lookup"><span data-stu-id="25814-161">**&lt;CommonParameters&gt;**</span></span> | <span data-ttu-id="25814-162">(Optional) Der Befehl unterstützt allgemeine PowerShell-Parameter, wie z.B. „verbose“ und „debug“.</span><span class="sxs-lookup"><span data-stu-id="25814-162">(Optional) The command supports common PowerShell parameters like verbose and debug.</span></span> |


- <span data-ttu-id="25814-163">Eine Liste der allgemeinen Parameter finden Sie im [Microsoft Script Center](https://technet.microsoft.com/library/hh847884.aspx).</span><span class="sxs-lookup"><span data-stu-id="25814-163">For a list of common parameters, see the [Microsoft Script Center](https://technet.microsoft.com/library/hh847884.aspx).</span></span>

- <span data-ttu-id="25814-164">Um ausführliche Informationen zu dem Tool zu erhalten, geben Sie folgenden Befehl ein:</span><span class="sxs-lookup"><span data-stu-id="25814-164">To see detailed usage information for the tool, enter the command:</span></span>

    ```
    Help Invoke-AppWrappingTool
    ```

<span data-ttu-id="25814-165">**Beispiel:**</span><span class="sxs-lookup"><span data-stu-id="25814-165">**Example:**</span></span>

<span data-ttu-id="25814-166">Importieren Sie das PowerShell-Modul.</span><span class="sxs-lookup"><span data-stu-id="25814-166">Import the PowerShell module.</span></span>
```
Import-Module "C:\Program Files (x86)\Microsoft Intune Mobile Application Management\Android\App Wrapping Tool\IntuneAppWrappingTool.psm1"
```
<span data-ttu-id="25814-167">Führen Sie das App Wrapping Tool in der nativen App „HelloWorld.apk“ aus.</span><span class="sxs-lookup"><span data-stu-id="25814-167">Run the App Wrapping Tool on the native app HelloWorld.apk.</span></span>
```
invoke-AppWrappingTool -InputPath .\app\HelloWorld.apk -OutputPath .\app_wrapped\HelloWorld_wrapped.apk -KeyStorePath "C:\Program Files (x86)\Java\jre1.8.0_91\bin\mykeystorefile" -keyAlias mykeyalias -SigAlg SHA1withRSA -Verbose
```

<span data-ttu-id="25814-168">Sie werden zur Eingabe von **KeyStorePassword** und **KeyPassword**aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="25814-168">You will then be prompted for **KeyStorePassword** and **KeyPassword**.</span></span> <span data-ttu-id="25814-169">Geben Sie die Anmeldeinformationen ein, die Sie zum Erstellen der Keystore-Datei verwendet haben.</span><span class="sxs-lookup"><span data-stu-id="25814-169">Enter the credentials you used to create the key store file.</span></span>

<span data-ttu-id="25814-170">Es wird sowohl die umschlossene App als auch eine Protokolldatei generiert und in dem von Ihnen angegebenen Ausgabepfad gespeichert.</span><span class="sxs-lookup"><span data-stu-id="25814-170">The wrapped app and a log file are generated and saved in the output path you specified.</span></span>

## <a name="reusing-signing-certificates-and-wrapping-apps"></a><span data-ttu-id="25814-171">Wiederverwendung von Signaturzertifikaten und Umschließen von Apps</span><span class="sxs-lookup"><span data-stu-id="25814-171">Reusing signing certificates and wrapping apps</span></span>
<span data-ttu-id="25814-172">Für Android müssen alle Apps durch ein gültiges Zertifikat signiert sein, um auf Android-Geräten installiert werden zu können.</span><span class="sxs-lookup"><span data-stu-id="25814-172">Android requires that all apps must be signed by a valid certificate in order to be installed on Android devices.</span></span>

<span data-ttu-id="25814-173">Umschlossene Apps können entweder als Teil des Umschließungsprozesses oder *nach* der Umschließung mithilfe Ihrer vorhandenen Tools für die Signatur signiert werden (alle Signierungsinformationen in der App, bevor die Umschließung verworfen wird).</span><span class="sxs-lookup"><span data-stu-id="25814-173">Wrapped apps can be signed either as part of the wrapping process or *after* wrapping using your existing signing tools (any signing information in the app before wrapping is discarded).</span></span>
 
<span data-ttu-id="25814-174">Wenn möglich sollten die Signierungsinformationen, die bereits während des Erstellungsprozesses verwendet wurden, während der Umschließung verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="25814-174">If possible, the signing information that was already used during the build process should be used during wrapping.</span></span> <span data-ttu-id="25814-175">In bestimmten Organisationen erfordert dies möglicherweise eine Zusammenarbeit mit der Person, die über die Keystore-Informationen verfügt (z.B. aus dem App-Entwicklungsteam).</span><span class="sxs-lookup"><span data-stu-id="25814-175">In certain organizations, this may require working with whoever owns the keystore information (ie. the app build team).</span></span> 

<span data-ttu-id="25814-176">Wenn das vorherige Signaturzertifikat nicht verwendet werden kann oder die App zuvor nicht bereitgestellt wurde, können Sie möglicherweise ein neues Signaturzertifikat erstellen, indem Sie die Anweisungen im [Android Developer-Handbuch](https://developer.android.com/studio/publish/app-signing.html#signing-manually) befolgen.</span><span class="sxs-lookup"><span data-stu-id="25814-176">If the previous signing certificate cannot be used, or the app has not been deployed before, you may create a new signing certificate by following the instructions in the [Android Developer Guide](https://developer.android.com/studio/publish/app-signing.html#signing-manually).</span></span>

<span data-ttu-id="25814-177">Wenn die App zuvor mit einem anderen Signaturzertifikat bereitgestellt wurde, kann sie nach dem Upgrade nicht zu Intune hochgeladen werden.</span><span class="sxs-lookup"><span data-stu-id="25814-177">If the app has been deployed previously with a different signing certificate, the app can't be uploaded to Intune after upgrade.</span></span> <span data-ttu-id="25814-178">App-Upgradeszenarios sind dann fehlerhaft, wenn Ihre App mit einem anderen Zertifikat signiert wird, als mit dem, mit dem die App erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="25814-178">App upgrade scenarios will be broken if your app is signed with a different certificate than the one the app is built with.</span></span> <span data-ttu-id="25814-179">Deshalb müssen alle neuen Signaturzertifikate für App-Upgrades verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="25814-179">As such, any new signing certificates should be maintained for app upgrades.</span></span> 

## <a name="security-considerations-for-running-the-app-wrapping-tool"></a><span data-ttu-id="25814-180">Sicherheitsüberlegungen zum Ausführen des App Wrapping Tools</span><span class="sxs-lookup"><span data-stu-id="25814-180">Security considerations for running the App Wrapping Tool</span></span>
<span data-ttu-id="25814-181">So verhindern Sie ein mögliches Spoofing, das Offenlegen von Informationen und Angriffe durch Rechteerweiterungen:</span><span class="sxs-lookup"><span data-stu-id="25814-181">To prevent potential spoofing, information disclosure, and elevation of privilege attacks:</span></span>

-   <span data-ttu-id="25814-182">Stellen Sie sicher, dass sich die Branchenanwendung für die Eingabe, die Ausgabeanwendung und der Java-Keystore auf demselben Windows-Computer befinden, auf dem auch das App Wrapping Tool ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="25814-182">Ensure that the input line-of-business (LOB) application, output application, and Java KeyStore are on the same Windows computer where the App Wrapping Tool is running.</span></span>

-   <span data-ttu-id="25814-183">Importieren Sie die Ausgabeanwendung auf demselben Computer, auf dem das Tool ausgeführt wird, in die Intune-Konsole.</span><span class="sxs-lookup"><span data-stu-id="25814-183">Import the output application to Intune on the same machine where the tool is running.</span></span> <span data-ttu-id="25814-184">Weitere Informationen zum Java-Keytool finden Sie unter [Keytool](https://docs.oracle.com/javase/8/docs/technotes/tools/unix/keytool.html).</span><span class="sxs-lookup"><span data-stu-id="25814-184">See [keytool](https://docs.oracle.com/javase/8/docs/technotes/tools/unix/keytool.html) for more about about Java keytool.</span></span>

-   <span data-ttu-id="25814-185">Wenn sich die Ausgabeanwendung und das Tool in einem UNC-Pfad (Universal Naming Convention) befinden und Sie das Tool und die Eingabedateien nicht auf demselben Computer ausführen, sichern Sie die Umgebung, indem Sie [Internet Protocol Security (IPsec)](http://wikipedia.org/wiki/IPsec) oder [SMB-Signaturen (Server Message Block)](https://support.microsoft.com/kb/887429) einrichten.</span><span class="sxs-lookup"><span data-stu-id="25814-185">If the output application and the tool are on a Universal Naming Convention (UNC) path and you are not running the tool and input files on the same computer, set up the environment to be secure by using [Internet Protocol Security (IPsec)](http://wikipedia.org/wiki/IPsec) or [Server Message Block (SMB) signing](https://support.microsoft.com/kb/887429).</span></span>

-   <span data-ttu-id="25814-186">Stellen Sie sicher, dass die Anwendung von einer vertrauenswürdigen Quelle stammt.</span><span class="sxs-lookup"><span data-stu-id="25814-186">Ensure that the application is coming from a trusted source.</span></span>

-   <span data-ttu-id="25814-187">Sichern Sie das Ausgabeverzeichnis, das die umschlossene Anwendung enthält.</span><span class="sxs-lookup"><span data-stu-id="25814-187">Secure the output directory that has the wrapped app.</span></span> <span data-ttu-id="25814-188">Erwägen Sie für die Ausgabe ein Verzeichnis auf Benutzerebene zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="25814-188">Consider using a user-level directory for the output.</span></span>

### <a name="see-also"></a><span data-ttu-id="25814-189">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="25814-189">See also</span></span>
- [<span data-ttu-id="25814-190">Auswählen der Vorbereitung von Apps für die mobile Anwendungsverwaltung mit Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="25814-190">Decide how to prepare apps for mobile application management with Microsoft Intune</span></span>](apps-prepare-mobile-application-management.md)

- [<span data-ttu-id="25814-191">Verwenden des SDK zum Aktivieren von Apps für die Verwaltung von mobilen Anwendungen</span><span class="sxs-lookup"><span data-stu-id="25814-191">Use the SDK to enable apps for mobile application management</span></span>](/intune/classic/deploy-use/use-the-sdk-to-enable-apps-for-mobile-application-management)
