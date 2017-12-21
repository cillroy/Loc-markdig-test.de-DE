---
title: Installieren der PC-Clientsoftware
description: Befolgen Sie diese Anleitung zum Verwalten Ihrer Windows-PCs durch die Microsoft Intune-Clientsoftware.
keywords: 
author: nathbarn
ms.author: nathbarn
ms.date: 07/13/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 64c11e53-8d64-41b9-9550-4b4e395e8c52
ms.reviewer: owenyen
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 9316f78155b38f74765a353186a29dc90afce547
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2017
---
# <a name="install-the-intune-software-client-on-windows-pcs"></a><span data-ttu-id="fe722-103">Installieren des Intune-Softwareclients auf Windows-PCs</span><span class="sxs-lookup"><span data-stu-id="fe722-103">Install the Intune software client on Windows PCs</span></span>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="fe722-104">Windows-PCs können mithilfe der Installation der Intune-Clientsoftware registriert werden.</span><span class="sxs-lookup"><span data-stu-id="fe722-104">Windows PCs can be enrolled by installing the Intune client software.</span></span> <span data-ttu-id="fe722-105">Die Intune-Clientsoftware kann mithilfe der folgenden Methoden installiert werden:</span><span class="sxs-lookup"><span data-stu-id="fe722-105">The Intune client software can be installed by using the following methods:</span></span>

- <span data-ttu-id="fe722-106">Vom IT-Administrator, mithilfe einer der folgenden Methoden: Manuelle Installation, Gruppenrichtlinie oder in einem Datenträgerimage enthaltene Installation</span><span class="sxs-lookup"><span data-stu-id="fe722-106">By the IT admin, using one of these methods: manual installation, Group Policy, or installation included in a disk image</span></span>

- <span data-ttu-id="fe722-107">Von Endbenutzern, die die Clientsoftware manuell installieren</span><span class="sxs-lookup"><span data-stu-id="fe722-107">By end users, who manually install the client software</span></span>

<span data-ttu-id="fe722-108">Die Intune-Clientsoftware enthält die für die Registrierung des PCs in der Intune-Verwaltung mindestens erforderliche Software.</span><span class="sxs-lookup"><span data-stu-id="fe722-108">The Intune client software contains the minimum software necessary to enroll the PC in Intune management.</span></span> <span data-ttu-id="fe722-109">Nach der Registrierung eines PCs lädt die Intune-Clientsoftware dann die vollständige Clientsoftware herunter, die für die Verwaltung des PC benötigt wird.</span><span class="sxs-lookup"><span data-stu-id="fe722-109">After a PC has been enrolled, the Intune client software then downloads the full client software required for PC management.</span></span>

<span data-ttu-id="fe722-110">Diese Downloadserie verringert die Auswirkungen auf die Netzwerkbandbreite und reduziert die Zeit, die zur ersten Registrierung des PC in Intune erforderlich ist, auf ein Mindestmaß.</span><span class="sxs-lookup"><span data-stu-id="fe722-110">This series of downloads reduces the impact on the network's bandwidth and minimizes the time required to initially enroll the PC in Intune.</span></span> <span data-ttu-id="fe722-111">Außerdem wird sichergestellt, dass auf dem Client die neueste verfügbare Software läuft, nachdem der zweite Download abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="fe722-111">It also ensures that the client has the most recent software available after the second download has finished.</span></span>

<span data-ttu-id="fe722-112">Eine Lizenz für Intune ermöglicht die Installation der Intune-Clientsoftware auf bis zu fünf PCs.</span><span class="sxs-lookup"><span data-stu-id="fe722-112">One Intune license allows the installation of the Intune client software on up to five PCs.</span></span>

## <a name="download-the-intune-client-software"></a><span data-ttu-id="fe722-113">Herunterladen der Intune-Clientsoftware</span><span class="sxs-lookup"><span data-stu-id="fe722-113">Download the Intune client software</span></span>

<span data-ttu-id="fe722-114">Mit Ausnahme der Methode, bei denen Benutzer die Intune-Clientsoftware selbst installieren, erfordern alle Methoden, dass die Software zuerst von IT-Administratoren heruntergeladen wird, damit sie anschließend den Endbenutzern bereitgestellt werden kann.</span><span class="sxs-lookup"><span data-stu-id="fe722-114">All methods, except those in which users install the Intune client software themselves, require that IT admins download the software first so that it can be subsequently deployed to end users.</span></span>

1.  <span data-ttu-id="fe722-115">Klicken Sie in der [Microsoft Intune-Verwaltungskonsole](https://manage.microsoft.com/) auf **Admin** &gt; **Download der Clientsoftware**.</span><span class="sxs-lookup"><span data-stu-id="fe722-115">In the [Microsoft Intune administration console](https://manage.microsoft.com/), click **Admin** &gt; **Client Software Download**.</span></span>

  ![Herunterladen des Intune-PC-Clients](../media/pc-sa-client-download.png)

2. <span data-ttu-id="fe722-117">Klicken Sie auf der Seite **Clientsoftwaredownload** auf **Clientsoftwaredownload**.</span><span class="sxs-lookup"><span data-stu-id="fe722-117">On the **Client Software Download** page, click **Download Client Software**.</span></span> <span data-ttu-id="fe722-118">Speichern Sie anschließend das Paket **Microsoft_Intune_Setup.zip**, das die Software enthält, an einem sicheren Speicherort in Ihrem Netzwerk.</span><span class="sxs-lookup"><span data-stu-id="fe722-118">Then save the **Microsoft_Intune_Setup.zip** package that contains the software to a secure location on your network.</span></span>

  <span data-ttu-id="fe722-119">Das Installationspaket der Intune-Clientsoftware enthält eindeutige und spezifische Informationen zu Ihrem Konto, die über ein eingebettetes Zertifikat verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="fe722-119">The Intune client software installation package contains unique and specific information, which is available through an embedded certificate, about your account.</span></span> <span data-ttu-id="fe722-120">Wenn nicht autorisierte Benutzer Zugriff auf das Installationspaket erhalten, können sie PCs bei dem Konto registrieren, dem das eingebettete Zertifikat entspricht, und möglicherweise Zugriff auf Unternehmensressourcen erhalten.</span><span class="sxs-lookup"><span data-stu-id="fe722-120">If unauthorized users gain access to the installation package, they can enroll PCs to the account that is represented by its embedded certificate and might gain access to company resources.</span></span>

3. <span data-ttu-id="fe722-121">Extrahieren Sie an dem sicheren Ort in Ihrem Netzwerk den Inhalt des Installationspakets.</span><span class="sxs-lookup"><span data-stu-id="fe722-121">Extract the contents of the installation package to the secure location on your network.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="fe722-122">Sie dürfen die extrahierte Datei **ACCOUNTCERT** weder umbenennen noch entfernen, da sonst die Installation der Clientsoftware misslingt.</span><span class="sxs-lookup"><span data-stu-id="fe722-122">Do not rename or remove the **ACCOUNTCERT** file that is extracted, or the client software installation will fail.</span></span>

## <a name="deploy-the-client-software-manually"></a><span data-ttu-id="fe722-123">Manuelles Bereitstellen der Clientsoftware</span><span class="sxs-lookup"><span data-stu-id="fe722-123">Deploy the client software manually</span></span>

<span data-ttu-id="fe722-124">Auf den Computern, auf denen die Clientsoftware installiert werden soll, wechseln Sie zu dem Ordner, in dem sich die Installationsdateien der Clientsoftware befinden.</span><span class="sxs-lookup"><span data-stu-id="fe722-124">On the computer(s) on which the client software is going to be installed, go to the folder where the client software installation files are located.</span></span> <span data-ttu-id="fe722-125">Führen Sie dann **Microsoft_Intune_Setup.exe** aus, um die Clientsoftware zu installieren.</span><span class="sxs-lookup"><span data-stu-id="fe722-125">Then run **Microsoft_Intune_Setup.exe** to install the client software.</span></span>

> [!NOTE]
> <span data-ttu-id="fe722-126">Der Installationsstatus wird angezeigt, wenn Sie mit dem Mauszeiger auf das Symbol in der Taskleiste des Client-PCs zeigen.</span><span class="sxs-lookup"><span data-stu-id="fe722-126">The status of the installation is displayed when you hover over the icon in the taskbar on the client PC.</span></span>

## <a name="deploy-the-client-software-by-using-group-policy"></a><span data-ttu-id="fe722-127">Bereitstellen der Clientsoftware mithilfe von Gruppenrichtlinien</span><span class="sxs-lookup"><span data-stu-id="fe722-127">Deploy the client software by using Group Policy</span></span>

1.  <span data-ttu-id="fe722-128">Führen Sie im Ordner, der die Dateien **Microsoft_Intune_Setup.exe** und **MicrosoftIntune.accountcert** enthält, den folgenden Befehl aus, um die Windows Installer-basierten Installationsprogramme für 32-Bit- und 64-Bit-Computer zu extrahieren:</span><span class="sxs-lookup"><span data-stu-id="fe722-128">In the folder that contains the files **Microsoft_Intune_Setup.exe** and **MicrosoftIntune.accountcert**, run the following command to extract the Windows Installer-based installation programs for 32-bit and 64-bit computers:</span></span>

    ```
    Microsoft_Intune_Setup.exe/Extract <destination folder>
    ```

2.  <span data-ttu-id="fe722-129">Kopieren Sie die Dateien **Microsoft_Intune_x86.msi**, **Microsoft_Intune_x64.msi** und **MicrosoftIntune.accountcert** in einen Netzwerkpfad, auf den alle Computer, auf denen die Clientsoftware installiert werden soll, zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="fe722-129">Copy the **Microsoft_Intune_x86.msi** file, the **Microsoft_Intune_x64.msi** file, and the **MicrosoftIntune.accountcert** file to a network location that can be accessed by all computers on which the client software is going to be installed.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="fe722-130">Benennen Sie die Dateien nicht um, und trennen sie sie nicht, da bei der Installation der Clientsoftware sonst ein Fehler auftritt.</span><span class="sxs-lookup"><span data-stu-id="fe722-130">Do not separate or rename the files or the client software installation will fail.</span></span>

3.  <span data-ttu-id="fe722-131">Verwenden Sie Gruppenrichtlinien, um die Software auf Computern in Ihrem Netzwerk bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="fe722-131">Use Group Policy to deploy the software to computers on your network.</span></span>

    <span data-ttu-id="fe722-132">Weitere Informationen zum automatischen Bereitstellen von Software mithilfe von Gruppenrichtlinien finden Sie unter [Gruppenrichtlinien für Anfänger](https://technet.microsoft.com/library/hh147307.aspx).</span><span class="sxs-lookup"><span data-stu-id="fe722-132">For more information about how to use Group Policy to automatically deploy software, see [Group Policy for Beginners](https://technet.microsoft.com/library/hh147307.aspx).</span></span>

## <a name="deploy-the-client-software-as-part-of-an-image"></a><span data-ttu-id="fe722-133">Bereitstellen der Clientsoftware als Teil eines Images</span><span class="sxs-lookup"><span data-stu-id="fe722-133">Deploy the client software as part of an image</span></span>
<span data-ttu-id="fe722-134">Sie können die Intune-Clientsoftware als Teil eines Betriebssystemabbilds auf Computern installieren. Verwenden Sie dazu die folgende Vorgehensweise als Leitfaden:</span><span class="sxs-lookup"><span data-stu-id="fe722-134">You can deploy the Intune client software to computers as part of an operating system image by using the following procedure as a guide:</span></span>

1.  <span data-ttu-id="fe722-135">Kopieren Sie die Clientinstallationsdateien **Microsoft_Intune_Setup.exe** und **MicrosoftIntune.accountcert** in den Ordner **%Systemdrive%\Temp\Microsoft_Intune_Setup** auf dem Referenzcomputer.</span><span class="sxs-lookup"><span data-stu-id="fe722-135">Copy the client installation files, **Microsoft_Intune_Setup.exe** and **MicrosoftIntune.accountcert**, to the **%Systemdrive%\Temp\Microsoft_Intune_Setup** folder on the reference computer.</span></span>

2.  <span data-ttu-id="fe722-136">Erstellen Sie den Registrierungseintrag **WindowsIntuneEnrollPending** , indem Sie dem Skript **SetupComplete.cmd** den folgenden Befehl hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="fe722-136">Create the **WindowsIntuneEnrollPending** registry entry by adding the following command to the **SetupComplete.cmd** script:</span></span>

    ```
    %windir%\system32\reg.exe add HKEY_LOCAL_MACHINE\Software\Microsoft\Onlinemanagement\Deployment /v
    WindowsIntuneEnrollPending /t REG_DWORD /d 1
    ```

3.  <span data-ttu-id="fe722-137">Fügen Sie **setupcomplete.cmd** den folgenden Befehl hinzu, um das Registrierungspaket mit dem Befehlszeilenargument „/PrepareEnroll“ auszuführen:</span><span class="sxs-lookup"><span data-stu-id="fe722-137">Add the following command to **setupcomplete.cmd** to run the enrollment package with the /PrepareEnroll command-line argument:</span></span>

    ```
    %systemdrive%\temp\Microsoft_Intune_Setup\Microsoft_Intune_Setup.exe /PrepareEnroll
    ```
    > [!TIP]
    > <span data-ttu-id="fe722-138">Mithilfe des Skripts **SetupComplete.cmd** können von Windows Setup Veränderungen am System vorgenommen werden, bevor sich ein Benutzer anmeldet.</span><span class="sxs-lookup"><span data-stu-id="fe722-138">The **SetupComplete.cmd** script enables Windows Setup to make modifications to the system before a user signs on.</span></span> <span data-ttu-id="fe722-139">Durch das Befehlszeilenargument **/PrepareEnroll** wird ein Zielcomputer auf die automatische Registrierung bei Intune nach Beenden von Windows Setup vorbereitet.</span><span class="sxs-lookup"><span data-stu-id="fe722-139">The **/PrepareEnroll** command-line argument prepares a targeted computer to be automatically enrolled in Intune after Windows Setup finishes.</span></span>

4.  <span data-ttu-id="fe722-140">Legen Sie die Datei **SetupComplete.cmd** auf dem Referenzcomputer im Ordner **%Windir%\Setup\Scripts** ab.</span><span class="sxs-lookup"><span data-stu-id="fe722-140">Put **SetupComplete.cmd** in the **%Windir%\Setup\Scripts** folder on the reference computer.</span></span>

5.  <span data-ttu-id="fe722-141">Erstellen Sie ein Systemabbild des Referenzcomputers, und stellen sie es auf den Zielcomputern bereit.</span><span class="sxs-lookup"><span data-stu-id="fe722-141">Capture an image of the reference computer and then deploy this to targeted computers.</span></span>

    <span data-ttu-id="fe722-142">Wenn der Zielcomputer nach Beenden von Windows Setup neu gestartet wird, wird der Registrierungsschlüssel **WindowsIntuneEnrollPending** erstellt.</span><span class="sxs-lookup"><span data-stu-id="fe722-142">When the targeted computer restarts at the completion of Windows Setup, the **WindowsIntuneEnrollPending** registry key is created.</span></span> <span data-ttu-id="fe722-143">Mit dem Registrierungspaket wird überprüft, ob der Computer registriert ist.</span><span class="sxs-lookup"><span data-stu-id="fe722-143">The enrollment package checks to see if the computer is enrolled.</span></span> <span data-ttu-id="fe722-144">Wenn der Computer registriert ist, ist keine weitere Aktion erforderlich.</span><span class="sxs-lookup"><span data-stu-id="fe722-144">If the computer is enrolled, no further action is taken.</span></span> <span data-ttu-id="fe722-145">Wenn der Computer nicht registriert ist, wird vom Registrierungspaket eine Aufgabe zur automatischen Microsoft Intune-Registrierung erstellt.</span><span class="sxs-lookup"><span data-stu-id="fe722-145">If the computer is not enrolled, the enrollment package creates a Microsoft Intune Automatic Enrollment Task.</span></span>

    <span data-ttu-id="fe722-146">Bei der Ausführung dieser Aufgabe zur automatischen Registrierung zum nächsten geplanten Zeitpunkt prüft die Aufgabe das Vorhandensein des Registrierungswerts **WindowsIntuneEnrollPending** und versucht, den Ziel-PC bei Intune zu registrieren.</span><span class="sxs-lookup"><span data-stu-id="fe722-146">When the automatic enrollment task runs at the next scheduled time, it checks the existence of the **WindowsIntuneEnrollPending** registry value, and it tries to enroll the targeted PC in Intune.</span></span> <span data-ttu-id="fe722-147">Sollte die Registrierung aus einem beliebigen Grund fehlschlagen, wird die Registrierung beim nächsten Ausführen der Aufgabe erneut versucht.</span><span class="sxs-lookup"><span data-stu-id="fe722-147">If the enrollment fails for any reason, the enrollment is retried the next time the task runs.</span></span> <span data-ttu-id="fe722-148">Die Wiederholungen werden für einen Monat ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="fe722-148">The retries continue for a month.</span></span>

    <span data-ttu-id="fe722-149">Die Aufgabe zur automatischen Intune-Registrierung, der Registrierungswert **WindowsIntuneEnrollPending** und das Kontozertifikat werden entweder vom Zielcomputer gelöscht, sobald die Registrierung erfolgreich war oder ein Monat vergangen ist (egal was zuerst kommt).</span><span class="sxs-lookup"><span data-stu-id="fe722-149">The Intune Automatic Enrollment Task, the **WindowsIntuneEnrollPending** registry value, and the account certificate are deleted from the targeted computer either when the enrollment is successful or after a month (whichever comes first).</span></span>

## <a name="instruct-users-to-self-enroll"></a><span data-ttu-id="fe722-150">Einweisen von Benutzern in die eigenständige Registrierung</span><span class="sxs-lookup"><span data-stu-id="fe722-150">Instruct users to self-enroll</span></span>

<span data-ttu-id="fe722-151">Benutzer können die Intune-Clientsoftware installieren, indem Sie auf die [Unternehmensportal-Website](https://portal.manage.microsoft.com) gehen.</span><span class="sxs-lookup"><span data-stu-id="fe722-151">Users install the Intune client software by going to the [Company Portal website](https://portal.manage.microsoft.com).</span></span> <span data-ttu-id="fe722-152">Die genauen Informationen, die den Benutzern im Webportal angezeigt werden, können je nach MDM-Autorität Ihres Kontos und je nach Betriebssystemplattform und Version des Benutzer-PCs variieren.</span><span class="sxs-lookup"><span data-stu-id="fe722-152">The exact information that users see in the web portal varies, depending on your account's MDM Authority and the OS platform/version of the user's PC.</span></span>

<span data-ttu-id="fe722-153">Wenn Benutzern keine Lizenz für Intune zugewiesen wurde oder die MDM-Autorität der Organisation nicht auf Intune festgelegt wurde, werden den Benutzern keine Optionen zum Registrieren angezeigt.</span><span class="sxs-lookup"><span data-stu-id="fe722-153">If users haven't been assigned an Intune license or if the organization's MDM Authority hasn't been set to Intune, users aren't shown any options to enroll.</span></span>

<span data-ttu-id="fe722-154">Wenn Benutzern eine Lizenz für Intune zugewiesen wurde und die MDM-Autorität der Organisation auf Intune festgelegt wurde:</span><span class="sxs-lookup"><span data-stu-id="fe722-154">If users have been assigned an Intune license, and the organization's MDM Authority has been set to Intune:</span></span>

- <span data-ttu-id="fe722-155">Windows 7- oder Windows 8-PC-Benutzern wird die Option zum Anmelden bei Intune NUR angezeigt, indem sie die PC-Clientsoftware, die in ihrer Organisation eindeutig ist, herunterladen und installieren.</span><span class="sxs-lookup"><span data-stu-id="fe722-155">Windows 7 or Windows 8 PC users are shown ONLY the option to enroll to Intune by downloading and installing the PC client software that is unique to their organization.</span></span>

- <span data-ttu-id="fe722-156">Windows 10- oder Windows 8.1-PC-Benutzern werden zwei Registrierungsoptionen angezeigt:</span><span class="sxs-lookup"><span data-stu-id="fe722-156">Windows 10 or Windows 8.1 PC users are shown two enrollment options:</span></span>

  -  <span data-ttu-id="fe722-157">**PC als mobiles Gerät registrieren**: Benutzer wählen die Schaltfläche **ANLEITUNG ZUM REGISTRIEREN** und werden zu Anweisungen weitergeleitet, wie sie ihren PC als mobiles Gerät registrieren.</span><span class="sxs-lookup"><span data-stu-id="fe722-157">**Enroll PC as a mobile device**: Users choose the **Find Out How to Enroll** button and are taken to instructions on how to enroll their PC as a mobile device.</span></span> <span data-ttu-id="fe722-158">Diese Schaltfläche wird hervorgehoben angezeigt, da die MDM-Registrierung die Standardeinstellung und die bevorzugte Registrierungsoption ist.</span><span class="sxs-lookup"><span data-stu-id="fe722-158">This button is prominently displayed, because MDM enrollment is considered to be the default and preferred enrollment option.</span></span> <span data-ttu-id="fe722-159">Die MDM-Option ist jedoch nicht auf dieses Thema anwendbar, das nur die Installation der Clientsoftware behandelt.</span><span class="sxs-lookup"><span data-stu-id="fe722-159">However, the MDM option is not applicable to this topic, which covers only the client software installation.</span></span>
  - <span data-ttu-id="fe722-160">**Registrieren des PCs mit Intune-Clientsoftware**: Ihre Benutzer müssen den Link **Zum Herunterladen hier klicken** auswählen, der sie durch die Installation der Clientsoftware führt.</span><span class="sxs-lookup"><span data-stu-id="fe722-160">**Enroll PC using the Intune client software**: You'll need to tell your users to select the **Click here to download it** link, which takes them through the client software installation.</span></span>

<span data-ttu-id="fe722-161">In der folgende Tabelle werden die Optionen zusammengefasst.</span><span class="sxs-lookup"><span data-stu-id="fe722-161">The following table summarizes the options.</span></span>

  ![Standardregistrierungsoptionen pro Plattform](../media/default-enrollment-options-table.png)

<span data-ttu-id="fe722-163">Die folgenden Screenshots zeigen, was die Benutzer sehen, wenn sie mithilfe des Softwareclients ihre Geräte registrieren.</span><span class="sxs-lookup"><span data-stu-id="fe722-163">The following screenshots show what users see as they enroll their devices using the software client.</span></span>

<span data-ttu-id="fe722-164">Benutzer werden zuerst aufgefordert, ihr Gerät zu identifizieren oder zu registrieren.</span><span class="sxs-lookup"><span data-stu-id="fe722-164">Users are first prompted to identify or to enroll their device.</span></span>

  ![Gerät identifizieren oder registrieren](../media/identify-device-or-enroll.png)

<span data-ttu-id="fe722-166">Damit Ihre Benutzer die PC-Clientsoftware installieren können, müssen Sie den Link **Zum Herunterladen hier klicken** auswählen, wodurch Benutzer die PC-Clientsoftware herunterzuladen können und sie durch den Installationsvorgang geführt werden.</span><span class="sxs-lookup"><span data-stu-id="fe722-166">To have your users install the PC client software, you'll need to tell them to select the **Click here to download it** link, which enables users to download the PC client software and takes them through the installation process.</span></span> <span data-ttu-id="fe722-167">Die **ANLEITUNG ZUM REGISTRIEREN**-Schaltfläche führt Benutzer zur Dokumentation für die Registrierung mithilfe der MDM-Registrierung, die für diese Softwareclient-Anweisungen nicht relevant ist.</span><span class="sxs-lookup"><span data-stu-id="fe722-167">The **Find out how to enroll** button takes users to documentation about how to enroll using MDM enrollment, which is not relevant to these software client instructions.</span></span>

  ![Link „Zum Herunterladen hier klicken“ auswählen](../media/enroll-your-windows-device.png)

<span data-ttu-id="fe722-169">Wenn Benutzer auf den Link klicken, sehen sie eine **Software herunterladen**-Schaltfläche, die sie auswählen, um die Installation der PC-Clientsoftware zu starten.</span><span class="sxs-lookup"><span data-stu-id="fe722-169">When users click the link, they see a **Download Software** button, which they select to start the PC client software installation.</span></span>

  ![Schaltfläche „Software herunterladen“ auswählen](../media/download-pc-client-software.png)

<span data-ttu-id="fe722-171">Benutzer werden dann aufgefordert, sich mit ihren Unternehmensanmeldeinformationen anzumelden.</span><span class="sxs-lookup"><span data-stu-id="fe722-171">Users are then asked to sign in with their corporate credentials.</span></span>

  ![Mit Ihren Anmeldeinformationen anmelden](../media/sign-in-to-intune.png)

<span data-ttu-id="fe722-173">Benutzer werden auf die Willkommensseite für die Installation geführt.</span><span class="sxs-lookup"><span data-stu-id="fe722-173">Users are taken to the Welcome page for the installation.</span></span>

  ![Willkommensseite für die PC-Clientinstallation](../media/welcome-to-pc-agent-install-wizard.png)

<span data-ttu-id="fe722-175">Die Benutzer wählen **Weiter** aus, und die Installation wird gestartet.</span><span class="sxs-lookup"><span data-stu-id="fe722-175">Users choose **Next**, and the installation starts.</span></span>

  ![Willkommensseite für die PC-Clientinstallation](../media/welcome-to-pc-agent-install-wizard.png)

<span data-ttu-id="fe722-177">Wenn die Installation abgeschlossen ist, wählen die Benutzer **Fertig stellen** aus.</span><span class="sxs-lookup"><span data-stu-id="fe722-177">When the installation completes, users choose **Finish**.</span></span>

  ![Abschließen der PC-Clientinstallation](../media/completed-the-setup-wizard.png)

<span data-ttu-id="fe722-179">Wenn Benutzer versuchen, ihren PC als mobiles Gerät zu registrieren, nachdem sie ihn bereits mithilfe der Intune-PC-Clientsoftware registriert haben, wird ihnen der folgenden Fehlerbildschirm angezeigt.</span><span class="sxs-lookup"><span data-stu-id="fe722-179">If users try to enroll their PC as a mobile device after having already enrolled using the Intune PC client software, they see the following error screen.</span></span>

  ![Bildschirm, der angezeigt wird, wenn der Computer bereits registriert ist](../media/page-shown-if-pc-already-enrolled.png)

## <a name="monitor-and-validate-successful-client-deployment"></a><span data-ttu-id="fe722-181">Überwachen und Überprüfen der erfolgreichen Clientbereitstellung</span><span class="sxs-lookup"><span data-stu-id="fe722-181">Monitor and validate successful client deployment</span></span>
<span data-ttu-id="fe722-182">Verwenden Sie eins der folgenden Verfahren, um die erfolgreiche Clientbereitstellung zu überwachen und zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="fe722-182">Use one of the following procedures to help you monitor and validate successful client deployment.</span></span>

### <a name="to-verify-the-installation-of-the-client-software-from-the-microsoft-intune-administrator-console"></a><span data-ttu-id="fe722-183">So überprüfen Sie die Installation der Clientsoftware mithilfe der Microsoft Intune-Administratorkonsole</span><span class="sxs-lookup"><span data-stu-id="fe722-183">To verify the installation of the client software from the Microsoft Intune administrator console</span></span>

1.  <span data-ttu-id="fe722-184">Klicken Sie in der [Microsoft Intune-Verwaltungskonsole](https://manage.microsoft.com/) auf **Gruppen** &gt; **Alle Geräte** &gt; **Alle Computer**.</span><span class="sxs-lookup"><span data-stu-id="fe722-184">In the [Microsoft Intune administration console](https://manage.microsoft.com/), click **Groups** &gt; **All Devices** &gt; **All Computers**.</span></span>

2.  <span data-ttu-id="fe722-185">Suchen Sie in der Liste der Computer die verwalteten Computer, von denen mit Intune kommuniziert wird. Um nach einem bestimmten verwalteten Computer zu suchen, geben Sie den Computernamen oder einen Teil des Namens in das Textfeld **Geräte suchen** ein.</span><span class="sxs-lookup"><span data-stu-id="fe722-185">In the list, find the computers that are communicating with Intune, or search for a specific managed computer by typing the computer name (or any part of the name) in the **Search devices** box.</span></span>

3.  <span data-ttu-id="fe722-186">Überprüfen Sie den Status des Computers im unteren Bereich der Konsole.</span><span class="sxs-lookup"><span data-stu-id="fe722-186">Examine the status of the computer in the bottom pane of the console.</span></span> <span data-ttu-id="fe722-187">Beheben Sie alle Fehler.</span><span class="sxs-lookup"><span data-stu-id="fe722-187">Resolve any errors.</span></span>

### <a name="to-create-a-computer-inventory-report-to-display-all-enrolled-computers"></a><span data-ttu-id="fe722-188">So erstellen Sie einen Computerinventurbericht zum Anzeigen aller registrierten Computer</span><span class="sxs-lookup"><span data-stu-id="fe722-188">To create a computer inventory report to display all enrolled computers</span></span>

1.  <span data-ttu-id="fe722-189">Klicken Sie in der [Microsoft Intune-Verwaltungskonsole](https://manage.microsoft.com/) auf **Berichte** &gt; **Computerinventurberichte**.</span><span class="sxs-lookup"><span data-stu-id="fe722-189">In the [Microsoft Intune administration console](https://manage.microsoft.com/), click **Reports** &gt; **Computer Inventory Reports**.</span></span>

2.  <span data-ttu-id="fe722-190">Belassen Sie auf der Seite **Neuen Bericht erstellen** die Standardwerte in den Feldern (sofern Sie keine Filter anwenden möchten), und klicken Sie anschließend auf **Bericht anzeigen**.</span><span class="sxs-lookup"><span data-stu-id="fe722-190">On the **Create New Report** page, leave the default values in all fields (unless you want to apply filters), and then click **View Report**.</span></span>

3.  <span data-ttu-id="fe722-191">In einem neuen Fenster wird die Seite **Computerinventurbericht** geöffnet, auf der alle erfolgreich bei Intune registrierten Computer angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="fe722-191">The **Computer Inventory Report** page opens in a new window that displays all computers that are successfully enrolled in Intune.</span></span>

    > [!TIP]
    > <span data-ttu-id="fe722-192">Klicken Sie im Bericht auf beliebige Spaltenüberschriften, um die Liste nach dem Inhalt der betreffenden Spalte zu sortieren.</span><span class="sxs-lookup"><span data-stu-id="fe722-192">Click any column heading in the report to sort the list by the contents of that column.</span></span>

## <a name="uninstall-the-windows-client-software"></a><span data-ttu-id="fe722-193">Deinstallieren der Windows-Clientsoftware</span><span class="sxs-lookup"><span data-stu-id="fe722-193">Uninstall the Windows client software</span></span>

<span data-ttu-id="fe722-194">Es gibt zwei Möglichkeiten, die Registrierung der Clientsoftware von Windows aufzugeben:</span><span class="sxs-lookup"><span data-stu-id="fe722-194">There are two ways to unenroll the Windows client software:</span></span>

- <span data-ttu-id="fe722-195">Über die Intune-Verwaltungskonsole aus (empfohlene Methode)</span><span class="sxs-lookup"><span data-stu-id="fe722-195">From the Intune admin console (recommended method)</span></span>
- <span data-ttu-id="fe722-196">Über eine Eingabeaufforderung auf dem Client</span><span class="sxs-lookup"><span data-stu-id="fe722-196">From a command prompt on the client</span></span>

### <a name="unenroll-by-using-the-intune-admin-console"></a><span data-ttu-id="fe722-197">Registrierung durch Verwendung der Intune-Verwaltungskonsole aufheben</span><span class="sxs-lookup"><span data-stu-id="fe722-197">Unenroll by using the Intune admin console</span></span>

<span data-ttu-id="fe722-198">Um die Registrierung des Softwareclients über die Intune-Verwaltungskonsole aufzuheben, navigieren sie zu **Gruppen** > **Alle Computer** > **Geräte**.</span><span class="sxs-lookup"><span data-stu-id="fe722-198">To unenroll the software client by using the Intune admin console, go to **Groups** > **All Computers** > **Devices**.</span></span> <span data-ttu-id="fe722-199">Klicken Sie mit der rechten Maustaste auf den Client, und wählen Sie **Abkoppeln/Zurücksetzen** aus.</span><span class="sxs-lookup"><span data-stu-id="fe722-199">Right-click the client, and select **Retire/Wipe**.</span></span>

### <a name="unenroll-by-using-a-command-prompt-on-the-client"></a><span data-ttu-id="fe722-200">Aufgeben der Registrierung durch Verwendung einer Eingabeaufforderung auf dem Client</span><span class="sxs-lookup"><span data-stu-id="fe722-200">Unenroll by using a command prompt on the client</span></span>

<span data-ttu-id="fe722-201">Führen Sie mithilfe einer Eingabeaufforderung mit erhöhten Rechten die folgenden Befehle aus.</span><span class="sxs-lookup"><span data-stu-id="fe722-201">Using an elevated command prompt, run one of the following commands.</span></span>

<span data-ttu-id="fe722-202">**Methode 1**</span><span class="sxs-lookup"><span data-stu-id="fe722-202">**Method 1**:</span></span>

    "C:\Program Files\Microsoft\OnlineManagement\Common\ProvisioningUtil.exe" /UninstallAgents /MicrosoftIntune

<span data-ttu-id="fe722-203">**Methode 2**</span><span class="sxs-lookup"><span data-stu-id="fe722-203">**Method 2**</span></span><br><span data-ttu-id="fe722-204">Beachten Sie, dass alle diese Agents auf jeder Windows-SKU installiert sind:</span><span class="sxs-lookup"><span data-stu-id="fe722-204">Note that all of these agents are installed on every SKU of Windows:</span></span>

    wmic product where name="Microsoft Endpoint Protection Management Components" call uninstall<br>
    wmic product where name="Microsoft Intune Notification Service" call uninstall<br>
    wmic product where name="System Center 2012 - Operations Manager Agent" call uninstall<br>
    wmic product where name="Microsoft Online Management Policy Agent" call uninstall<br>
    wmic product where name="Microsoft Policy Platform" call uninstall<br>
    wmic product where name="Microsoft Security Client" call uninstall<br>
    wmic product where name="Microsoft Online Management Client" call uninstall<br>
    wmic product where name="Microsoft Online Management Client Service" call uninstall<br>
    wmic product where name="Microsoft Easy Assist v2" call uninstall<br>
    wmic product where name="Microsoft Intune Monitoring Agent" call uninstall<br>
    wmic product where name="Windows Intune Endpoint Protection Agent" call uninstall<br>
    wmic product where name="Windows Firewall Configuration Provider" call uninstall<br>
    wmic product where name="Microsoft Intune Center" call uninstall<br>
    wmic product where name="Microsoft Online Management Update Manager" call uninstall<br>
    wmic product where name="Microsoft Online Management Agent Installer" call uninstall<br>
    wmic product where name="Microsoft Intune" call uninstall<br>
    wmic product where name="Windows Endpoint Protection Management Components" call uninstall<br>
    wmic product where name="Windows Intune Notification Service" call uninstall<br>
    wmic product where name="System Center 2012 - Operations Manager Agent" call uninstall<br>
    wmic product where name="Windows Online Management Policy Agent" call uninstall<br>
    wmic product where name="Windows Policy Platform" call uninstall<br>
    wmic product where name="Windows Security Client" call uninstall<br>
    wmic product where name="Windows Online Management Client" call uninstall<br>
    wmic product where name="Windows Online Management Client Service" call uninstall<br>
    wmic product where name="Windows Easy Assist v2" call uninstall<br>
    wmic product where name="Windows Intune Monitoring Agent" call uninstall<br>
    wmic product where name="Windows Intune Endpoint Protection Agent" call uninstall<br>
    wmic product where name="Windows Firewall Configuration Provider" call uninstall<br>
    wmic product where name="Windows Intune Center" call uninstall<br>
    wmic product where name="Windows Online Management Update Manager" call uninstall<br>
    wmic product where name="Windows Online Management Agent Installer" call uninstall<br>
    wmic product where name="Windows Intune" call uninstall

> [!TIP]
> <span data-ttu-id="fe722-205">Durch die Aufhebung der Registrierung eines Clients verbleibt ein ungesicherter Bericht auf Serverseite für den betroffenen Client.</span><span class="sxs-lookup"><span data-stu-id="fe722-205">Client unenrollment will leave a stale sever-side record for the affected client.</span></span> <span data-ttu-id="fe722-206">Der Vorgang zur Aufhebung der Registrierung ist asynchron. Es gibt neun Agents, die gelöscht werden müssen, also dauert es bis zu 30 Minuten, bis der Vorgang abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="fe722-206">The unenrollment process is asynchronous, and there are nine agents to uninstall, so it may take up to 30 mins to complete.</span></span>

### <a name="check-the-unenrollment-status"></a><span data-ttu-id="fe722-207">Überprüfen des Status der Aufhebung der Registrierung</span><span class="sxs-lookup"><span data-stu-id="fe722-207">Check the unenrollment status</span></span>

<span data-ttu-id="fe722-208">Überprüfen Sie „%ProgramFiles%\Microsoft\OnlineManagement“, und stellen Sie sicher, dass ausschließlich die folgenden Verzeichnisse auf der linken Seite angezeigt werden:</span><span class="sxs-lookup"><span data-stu-id="fe722-208">Check "%ProgramFiles%\Microsoft\OnlineManagement" and ensure that only the following directories are shown on the left:</span></span>

- <span data-ttu-id="fe722-209">AgentInstaller</span><span class="sxs-lookup"><span data-stu-id="fe722-209">AgentInstaller</span></span>
- <span data-ttu-id="fe722-210">Protokolle</span><span class="sxs-lookup"><span data-stu-id="fe722-210">Logs</span></span>
- <span data-ttu-id="fe722-211">Updates</span><span class="sxs-lookup"><span data-stu-id="fe722-211">Updates</span></span>
- <span data-ttu-id="fe722-212">Allgemein</span><span class="sxs-lookup"><span data-stu-id="fe722-212">Common</span></span>

### <a name="remove-the-onlinemanagement-folder"></a><span data-ttu-id="fe722-213">Entfernen des Ordner „OnlineManagement“</span><span class="sxs-lookup"><span data-stu-id="fe722-213">Remove the OnlineManagement folder</span></span>

<span data-ttu-id="fe722-214">Der Prozess zur Aufhebung der Registrierung entfernt nicht den OnlineManagement-Ordner.</span><span class="sxs-lookup"><span data-stu-id="fe722-214">The unenrollment process does not remove the OnlineManagement folder.</span></span> <span data-ttu-id="fe722-215">Warten Sie nach der Deinstallation 30 Minuten, und führen Sie dann diesen Befehl aus.</span><span class="sxs-lookup"><span data-stu-id="fe722-215">Wait 30 minutes after the uninstall, and then run this command.</span></span> <span data-ttu-id="fe722-216">Wenn Sie ihn zu früh ausführen, kann die Deinstallation in einem unbekannten Status verbleiben.</span><span class="sxs-lookup"><span data-stu-id="fe722-216">If you run it too soon, the uninstall could be left in an unknown state.</span></span> <span data-ttu-id="fe722-217">Um den Ordner zu entfernen, starten Sie einen Befehl mit erhöhten Rechten, und führen Sie folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="fe722-217">To remove the folder, start an elevated prompt and run:</span></span>

    "rd /s /q %ProgramFiles%\Microsoft\OnlineManagement".

### <a name="next-steps"></a><span data-ttu-id="fe722-218">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="fe722-218">Next steps</span></span>
<span data-ttu-id="fe722-219">[Verwalten von Windows-PCs mit Microsoft Intune](manage-windows-pcs-with-microsoft-intune.md)
[Problembehandlung beim Clientsetup](../troubleshoot/troubleshoot-client-setup-in-microsoft-intune.md)</span><span class="sxs-lookup"><span data-stu-id="fe722-219">[Manage Windows PCs with Microsoft Intune](manage-windows-pcs-with-microsoft-intune.md)
[Troubleshoot client setup](../troubleshoot/troubleshoot-client-setup-in-microsoft-intune.md)</span></span>
