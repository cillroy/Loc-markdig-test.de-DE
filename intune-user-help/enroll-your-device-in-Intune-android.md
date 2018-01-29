---
title: "Registrieren Ihres Android-Geräts bei Intune | Microsoft-Dokumentation"
description: "Beschreibt, wie Sie ein Android-Gerät bei Intune registrieren."
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 10/05/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 0ed3a002-7533-4001-ae24-e10b64b66620
searchScope:
- User help
ROBOTS: 
ms.reviewer: arnab
ms.suite: ems
ms.custom: intune-enduser
ms.openlocfilehash: 1a410b6626074b92ad81f620d332a6351a6db34b
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2018
---
# <a name="enroll-your-android-device-in-intune"></a><span data-ttu-id="6e39d-103">Registrieren Ihres Android-Geräts bei Intune</span><span class="sxs-lookup"><span data-stu-id="6e39d-103">Enroll your Android device in Intune</span></span>

<span data-ttu-id="6e39d-104">Wenn Ihr Unternehmen oder Ihre Schule Microsoft Intune verwendet, können Sie Ihr Android-Gerät registrieren, um Zugriff auf Unternehmens-E-Mails, Dateien und weitere Ressourcen zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="6e39d-104">If your company or school uses Microsoft Intune, you can enroll your Android device to get access to company email, files, and other resources.</span></span> <span data-ttu-id="6e39d-105">Wenn Sie Ihre Geräte registrieren, kann Ihre IT-Abteilung diese Geschäfts-, Schul- oder Uniressourcen verwalten, schützen und Ihnen gleichzeitig die Möglichkeit bieten, Ihr bevorzugtes Gerät zu verwenden, um Ihre Arbeit erledigen.</span><span class="sxs-lookup"><span data-stu-id="6e39d-105">When you enroll your devices, your IT department can manage those work or school resources, keep them secure, and give you the freedom to use your preferred device to get your work done.</span></span> <span data-ttu-id="6e39d-106">Weitere Informationen zur Registrierung finden Sie unter [Was geschieht, wenn ich die Unternehmensportal-App installiere und mein Gerät bei registriere?](what-happens-if-you-install-the-Company-Portal-app-and-enroll-your-device-in-intune-android.md)</span><span class="sxs-lookup"><span data-stu-id="6e39d-106">To learn more about enrollment, see [What happens when I install and Company Portal app and enroll my device?](what-happens-if-you-install-the-Company-Portal-app-and-enroll-your-device-in-intune-android.md)</span></span>

> [!VIDEO https://channel9.msdn.com/Series/IntuneEnrollment/Android-Enrollment/player]

<span data-ttu-id="6e39d-107">Diese Registrierungsanweisungen gelten für native Android-Geräte und für Android-Geräte mit Samsung KNOX.</span><span class="sxs-lookup"><span data-stu-id="6e39d-107">These enrollment instructions are for native and Samsung KNOX Android devices.</span></span> <span data-ttu-id="6e39d-108">Samsung KNOX ist ein Sicherheitssystem, mit dem bestimmte Geräte von Samsung neben der nativen Android-Sicherheit zusätzlichen Schutz bieten.</span><span class="sxs-lookup"><span data-stu-id="6e39d-108">Samsung KNOX is a type of security that certain Samsung devices use to provide additional protection outside of what native Android provides.</span></span> <span data-ttu-id="6e39d-109">Wechseln Sie zu **Einstellungen** > **Geräteinformationen**, um zu überprüfen, ob es sich bei Ihrem Gerät um ein Samsung KNOX-Gerät handelt.</span><span class="sxs-lookup"><span data-stu-id="6e39d-109">To check if you have a Samsung KNOX device, go to **Settings** > **About device**.</span></span> <span data-ttu-id="6e39d-110">Wird „KNOX-Version“ nicht angezeigt, verfügen Sie über ein natives Android-Gerät.</span><span class="sxs-lookup"><span data-stu-id="6e39d-110">If you don't see "KNOX version" listed there, you have a native Android device.</span></span>

<span data-ttu-id="6e39d-111">Vor oder nach der Registrierung werden Sie möglicherweise aufgefordert, eine Kategorie auszuwählen, die am besten beschreibt, wie Sie Ihr Gerät nutzen.</span><span class="sxs-lookup"><span data-stu-id="6e39d-111">Before or after enrolling, you may be asked to choose a category that best describes how you use your device.</span></span> <span data-ttu-id="6e39d-112">Der Support Ihres Unternehmens verwendet diese Kategorie, um die Apps zu überprüfen, auf die Sie Zugriff haben.</span><span class="sxs-lookup"><span data-stu-id="6e39d-112">Your company support uses this category to help check the apps that you have access to.</span></span>

<span data-ttu-id="6e39d-113">**So registrieren Sie Ihr Android-Gerät:**</span><span class="sxs-lookup"><span data-stu-id="6e39d-113">**To enroll your Android device:**</span></span>

1. <span data-ttu-id="6e39d-114">Installieren Sie die kostenlose Intune-Unternehmensportal-App aus [Google Play](http://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal).</span><span class="sxs-lookup"><span data-stu-id="6e39d-114">Install the free Intune Company Portal app from [Google Play](http://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal).</span></span>

2. <span data-ttu-id="6e39d-115">Öffnen Sie die Unternehmensportal-App.</span><span class="sxs-lookup"><span data-stu-id="6e39d-115">Open the Company Portal app.</span></span>

3. <span data-ttu-id="6e39d-116">Tippen Sie im Unternehmensportal auf dem **Begrüßungsbildschirm** auf **Anmelden**, und melden Sie sich dann mit Ihrem Geschäfts-, Schul- oder Unikonto an.</span><span class="sxs-lookup"><span data-stu-id="6e39d-116">On the Company Portal **Welcome** screen, tap **Sign in**, and then sign in with your work or school account.</span></span>

   ![Die Willkommensseite der Unternehmensportal-App für Android mit der Aufforderung, sich mit dem erforderlichen Geschäfts-, Schul- oder Unikonto anzumelden.](./media/and-enroll-0-welcome-screen.png)   

4. <span data-ttu-id="6e39d-119">Wenn der Support Ihres Unternehmens Nutzungsbedingungen des Unternehmens eingerichtet hat, tippen Sie auf **AKZEPTIEREN**, um sie anzunehmen.</span><span class="sxs-lookup"><span data-stu-id="6e39d-119">If your company support set up company terms and conditions, tap **ACCEPT** to accept the terms.</span></span> <span data-ttu-id="6e39d-120">Dieser Bildschirm kann sich von der nachstehenden Abbildung je nach aktuell verwendeter Version von Android geringfügig unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="6e39d-120">This screen may differ slightly from the image below based on the version of Android you're currently using.</span></span>

   ![android-company-portal-sign-in](./media/and-enroll-3-accept-terms.png)

5. <span data-ttu-id="6e39d-122">Melden Sie sich bei der Unternehmensportal-App mit Ihrem Geschäfts-, Schul- oder Unikonto und dem zugehörigen Kennwort an, und tippen Sie dann auf **Anmelden**.</span><span class="sxs-lookup"><span data-stu-id="6e39d-122">Sign in to the Company Portal app using your work or school account and password, and then tap **Sign in**.</span></span>

   ![android-company-portal-sign-in](./media/and-enroll-2-cp-sign-in.png)

6. <span data-ttu-id="6e39d-124">Tippen Sie auf dem Bildschirm **Unternehmenszugriff einrichten** auf **WEITER**.</span><span class="sxs-lookup"><span data-stu-id="6e39d-124">On the **Company Access Setup** screen, tap **CONTINUE**.</span></span>

   ![Bildschirm „Unternehmenszugriff einrichten“](/intune/media/android_cp_enroll_01_1709_new.png)

   > [!NOTE]
   > <span data-ttu-id="6e39d-126">Die gelben Dreiecke bedeuten nicht, dass bereits ein Fehler vorliegt.</span><span class="sxs-lookup"><span data-stu-id="6e39d-126">The yellow triangles don't mean you've already got an error.</span></span> <span data-ttu-id="6e39d-127">Sie geben lediglich an, dass für den Registrierungsprozess noch Schritte ausgeführt werden müssen.</span><span class="sxs-lookup"><span data-stu-id="6e39d-127">Those icons indicate that there are still steps to be completed in the enrollment process.</span></span>

7. <span data-ttu-id="6e39d-128">Prüfen Sie in der angezeigten Liste, was der Support Ihres Unternehmens auf Ihrem Gerät sehen kann und was nicht, und tippen Sie auf **WEITER**.</span><span class="sxs-lookup"><span data-stu-id="6e39d-128">Review a list of what your company support can and can't see on your device, and then tap **CONTINUE**.</span></span>

   ![Datenschutzeinstellungen](/intune/media/android_cp_enroll_02_after_1710.png)

8. <span data-ttu-id="6e39d-130">Lesen Sie auf dem Bildschirm **What's next?** (Wie geht es weiter?), was während der Registrierung passiert, und tippen Sie dann auf **REGISTRIEREN**.</span><span class="sxs-lookup"><span data-stu-id="6e39d-130">On the **What's next?** screen, read about what happens during enrollment, and then tap **ENROLL**.</span></span>

   ![Was ist der nächste Schritt?](/intune/media/android_cp_enroll_03_after_1710.png)

9. <span data-ttu-id="6e39d-132">Wenn Sie Android 6.0 oder höher verwenden, führen Sie diesen Schritt aus.</span><span class="sxs-lookup"><span data-stu-id="6e39d-132">If you're using Android 6.0 or later, do this step.</span></span> <span data-ttu-id="6e39d-133">Fahren Sie andernfalls mit dem nächsten Schritt fort.</span><span class="sxs-lookup"><span data-stu-id="6e39d-133">Otherwise, go to the next step.</span></span>

   <span data-ttu-id="6e39d-134">Wenn der Support Ihres Unternehmens bestimmte Richtlinien eingerichtet hat, werden möglicherweise folgende Meldungen angezeigt:</span><span class="sxs-lookup"><span data-stu-id="6e39d-134">If your company support has set up certain policies, you may see the following messages:</span></span>
   - <span data-ttu-id="6e39d-135">**Zulassen, dass das Unternehmensportal Telefonanrufe tätigt und verwaltet?**</span><span class="sxs-lookup"><span data-stu-id="6e39d-135">**Allow Company Portal to make and manage phone calls?**</span></span>

     ![android-company-portal-sign-in](./media/and-enroll-3a-allow-phone-access.png)

   <span data-ttu-id="6e39d-137">Wenn diese Meldung angezeigt wird, tippen Sie auf **ZULASSEN**.</span><span class="sxs-lookup"><span data-stu-id="6e39d-137">If you see this message, tap **ALLOW**.</span></span> <span data-ttu-id="6e39d-138">Sie können ruhig auf „ZULASSEN“ tippen, weil **Microsoft niemals Ihre Telefonanrufe tätigt oder verwaltet**!</span><span class="sxs-lookup"><span data-stu-id="6e39d-138">It is safe to tap ALLOW because **Microsoft never makes or manages your phone calls**!</span></span> <span data-ttu-id="6e39d-139">Google steuert den Meldungstext, daher kann er von Microsoft nicht geändert werden.</span><span class="sxs-lookup"><span data-stu-id="6e39d-139">Google controls the message text, and Microsoft cannot change it.</span></span> <span data-ttu-id="6e39d-140">Wenn Sie den Zugriff gewähren, erlauben Sie Ihrem Gerät schlicht, die IMEI-Nummer (International Mobile Station Equipment Identity) Ihres Geräts an Intune zu senden.</span><span class="sxs-lookup"><span data-stu-id="6e39d-140">When you allow access, all you're doing is letting your device send your device's international mobile station equipment identity (IMEI) number to Intune.</span></span> <span data-ttu-id="6e39d-141">Die IMEI ähnelt einer Seriennummer, mit der ein mobiles Gerät eindeutig identifiziert werden kann.</span><span class="sxs-lookup"><span data-stu-id="6e39d-141">The IMEI number is like a serial number that uniquely identifies a mobile device.</span></span>

   <span data-ttu-id="6e39d-142">Wenn Sie den Zugriff verweigern, wird die Meldung bei Ihrer nächsten Anmeldung beim Unternehmensportal angezeigt. Sie können künftige Meldungen jedoch deaktivieren, indem Sie das Kontrollkästchen **Nicht mehr nachfragen** aktivieren.</span><span class="sxs-lookup"><span data-stu-id="6e39d-142">If you deny access, the message will appear again the next time you sign in to the Company Portal, but you can turn off future messages by tapping the **Never ask again** box.</span></span> <span data-ttu-id="6e39d-143">Wenn Sie den Zugriff später erlauben möchten, wechseln Sie zu **Einstellungen** &gt; **Apps** &gt; **Unternehmensportal** &gt; **Berechtigungen** &gt; **Telefon**, um die Berechtigung zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="6e39d-143">If you later decide to allow access, go to **Settings** &gt; **Apps** &gt; **Company Portal** &gt; **Permissions** &gt; **Phone**, and then turn on the permission.</span></span>

   - <span data-ttu-id="6e39d-144">**Zulassen, dass das Unternehmensportal auf Ihre Kontakte zugreift?**</span><span class="sxs-lookup"><span data-stu-id="6e39d-144">**Allow Company Portal to access your contacts?**</span></span>

     ![android-company-portal-sign-in](./media/and-enroll-3b-allow-contacts-access.png)

     <span data-ttu-id="6e39d-146">Wenn diese Meldung angezeigt wird, tippen Sie auf **ZULASSEN**.</span><span class="sxs-lookup"><span data-stu-id="6e39d-146">If you see this message, tap **ALLOW**.</span></span> <span data-ttu-id="6e39d-147">Sie können ruhig auf „ZULASSEN“ tippen, weil **Microsoft niemals auf Ihre Kontakte zugreift**!</span><span class="sxs-lookup"><span data-stu-id="6e39d-147">It is safe to tap ALLOW because **Microsoft never accesses your contacts!**</span></span> <span data-ttu-id="6e39d-148">Google steuert den Meldungstext, daher kann er von Microsoft nicht geändert werden.</span><span class="sxs-lookup"><span data-stu-id="6e39d-148">Google controls the message text, and Microsoft cannot change it.</span></span> <span data-ttu-id="6e39d-149">Wenn Sie den Zugriff gewähren, wird der Unternehmensportal-App lediglich das Erstellen, Verwenden und Verwalten Ihres Geschäftskontos erlaubt.</span><span class="sxs-lookup"><span data-stu-id="6e39d-149">When you allow access, it only lets the Company Portal app create, use, and manage your work account.</span></span>

     <span data-ttu-id="6e39d-150">Wenn Sie den Zugriff verweigern, wird die Meldung bei Ihrer nächsten Anmeldung beim Unternehmensportal angezeigt. Sie können künftige Meldungen jedoch deaktivieren, indem Sie das Kontrollkästchen **Nicht mehr nachfragen** aktivieren.</span><span class="sxs-lookup"><span data-stu-id="6e39d-150">If you deny access, the message will appear again the next time you sign in to the Company Portal, but you can turn off future messages by tapping the **Never ask again** box.</span></span> <span data-ttu-id="6e39d-151">Wenn Sie den Zugriff später erlauben möchten, wechseln Sie zu **Einstellungen** &gt; **Apps** &gt; **Unternehmensportal** &gt; **Berechtigungen** &gt; **Telefon**, um die Berechtigung zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="6e39d-151">If you later decide to allow access, go to **Settings** &gt; **Apps** &gt; **Company Portal** &gt; **Permissions** &gt; **Phone**, and then turn on the permission.</span></span>

10. <span data-ttu-id="6e39d-152">Klicken Sie auf dem Bildschirm **Geräteadministrator aktivieren** auf **Aktivieren**.</span><span class="sxs-lookup"><span data-stu-id="6e39d-152">On the **Activate device administrator** screen, tap **Activate**.</span></span>

    ![Bildschirm „Geräteadministrator aktivieren?“](./media/and-enroll-5-activate.png)

    <span data-ttu-id="6e39d-154">Die Geräteadministratorrolle wird vom Unternehmensportal benötigt, um Ihr Gerät zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="6e39d-154">The device administrator role is one that the Company Portal needs to manage your device.</span></span> <span data-ttu-id="6e39d-155">Damit kann Ihr Administrator bestimmte Dinge sehen – zum Beispiel wie oft Sie versucht haben, Ihren Bildschirm zu entsperren – und einige Aktionen vornehmen.</span><span class="sxs-lookup"><span data-stu-id="6e39d-155">It allows your admin to see certain things - like how many times you've attempted to unlock your screen - and to take some actions.</span></span>

    <span data-ttu-id="6e39d-156">Es gilt zu beachten, dass diese Aktionen im Namen der Sicherheit ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="6e39d-156">The key to remember is that these are actions that are taken in the name of security.</span></span> <span data-ttu-id="6e39d-157">Der Support Ihres Unternehmens wird nicht versuchen, Ihre Privatsphäre zu verletzen oder Ihre Daten ohne Grund zu löschen, möchte aber sicherstellen, dass Unternehmensdaten sicher aufbewahrt werden.</span><span class="sxs-lookup"><span data-stu-id="6e39d-157">Your company support isn't trying to violate your privacy or erase your information for no reason, but wants to make sure that corporate data is kept safe.</span></span>

    <span data-ttu-id="6e39d-158">Microsoft wird diese Meldung nicht kontrollieren, und wir wissen, dass die Ausdrucksweise etwas drastisch erscheinen kann.</span><span class="sxs-lookup"><span data-stu-id="6e39d-158">Microsoft does not control this message, and we understand that its phrasing can seem somewhat drastic.</span></span> <span data-ttu-id="6e39d-159">Es gibt keine Möglichkeit, dass das Unternehmensportal nur die Einschränkungen und Zugriffe anzeigt, die für Ihre Organisation relevant sind.</span><span class="sxs-lookup"><span data-stu-id="6e39d-159">There's not a way for the Company Portal to display just the restrictions and access that are relevant to your organization.</span></span> <span data-ttu-id="6e39d-160">Alle werden auf diesem Bildschirm auf einmal erteilt.</span><span class="sxs-lookup"><span data-stu-id="6e39d-160">All of them are granted at once on this screen.</span></span> <span data-ttu-id="6e39d-161">Wenden Sie sich mithilfe der Kontaktinformationen auf der [Unternehmensportalwebsite](https://portal.manage.microsoft.com#HelpDeskDialog) an den Support Ihres Unternehmens, wenn Sie spezifische Fragen zur Verwendung in Ihrer Organisation haben.</span><span class="sxs-lookup"><span data-stu-id="6e39d-161">Contact your company support for more information using the contact information in the [Company Portal website](https://portal.manage.microsoft.com#HelpDeskDialog) if you have questions specific to your individual organization's use.</span></span>

11. <span data-ttu-id="6e39d-162">Befolgen Sie die Aufforderungen zur Eingabe einer PIN oder eines Kennworts.</span><span class="sxs-lookup"><span data-stu-id="6e39d-162">Follow the prompts to enter a PIN or password.</span></span> <span data-ttu-id="6e39d-163">Wenn Sie bereits eine PIN oder ein Kennwort auf diesem Gerät eingerichtet haben, wird dieser Bildschirm nicht angezeigt, und Sie werden nicht zur Eingabe einer neuen PIN oder eines neuen Kennworts aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="6e39d-163">If you already set up a PIN or password on this device, you won't see this screen or be required to enter a new PIN or password.</span></span>

    ![Eingeben von PIN oder Kennwort](./media/and-enroll-6-PIN-native.png)

12. <span data-ttu-id="6e39d-165">Wenn Sie ein Samsung KNOX-Gerät verwenden, tippen Sie auf **Bestätigen**. Es wird eine Meldung angezeigt, die besagt, dass das Gerät registriert wird.</span><span class="sxs-lookup"><span data-stu-id="6e39d-165">If you are using a Samsung KNOX device, tap **Confirm**, and you’ll see a message that your device is being enrolled.</span></span> <span data-ttu-id="6e39d-166">Wenn Sie ein natives Android-Gerät verwenden, beachten Sie den folgenden Bildschirm, der anzeigt, dass das Gerät registriert wird.</span><span class="sxs-lookup"><span data-stu-id="6e39d-166">If you are using a native Android device, just notice the following screen that shows that your device is being enrolled.</span></span>

    ![Samsung KNOX-Datenschutzrichtlinie](./media/and-enroll-7-knox-privacy-policy.png)

    <span data-ttu-id="6e39d-168">Dieser Bildschirm zeigt an, dass das Gerät registriert wird.</span><span class="sxs-lookup"><span data-stu-id="6e39d-168">This screen shows that your device is being enrolled.</span></span>

    ![Bildschirm „Gerät wird registriert“](./media/and-enroll-8-device-enrolling.png)

13. <span data-ttu-id="6e39d-170">Wenn der Bildschirm **Einrichten des Unternehmenszugriffs** angezeigt wird, tippen Sie auf **WEITER**.</span><span class="sxs-lookup"><span data-stu-id="6e39d-170">When the **Company Access Setup** screen appears, tap **CONTINUE**.</span></span> <span data-ttu-id="6e39d-171">Wenn eine Meldung anzeigt, dass Ihr Gerät nicht kompatibel ist, befolgen Sie die Anweisungen zum Beheben des Problems, und tippen Sie dann auf **WEITER**.</span><span class="sxs-lookup"><span data-stu-id="6e39d-171">If a message indicates that your device is out of compliance, follow the instructions to fix the issue, and then tap **CONTINUE**.</span></span>

    ![Das Gerät ist nicht kompatibel, aber registriert.](/intune/media/android_cp_enroll_05_post_1709.png)

    ![Es liegen Probleme mit der Gerätekompatibilität vor, die behoben werden müssen.](/intune/media/android_cp_enroll_03_post_1709.png)

    <span data-ttu-id="6e39d-174">Tippen Sie ggf. auf die einzelnen Probleme, um weitere Informationen zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="6e39d-174">You can find out more about the issues by tapping on them.</span></span>

    ![Erweiterte Ansicht von Gerätekompatibilitätsproblemen](/intune/media/android_cp_enroll_04_post_1709.png)

    ![Bildschirm „Unternehmenszugriff einrichten“](./media/and-enroll-9d-comp-access-setup.png)  

14. <span data-ttu-id="6e39d-177">Tippen Sie auf dem Bildschirm **Einrichten des Unternehmenszugriffs abgeschlossen** auf **FERTIG**.</span><span class="sxs-lookup"><span data-stu-id="6e39d-177">On the **Company Access Setup complete** screen, tap **DONE**.</span></span> <span data-ttu-id="6e39d-178">Ihr Gerät ist jetzt bei registriert.</span><span class="sxs-lookup"><span data-stu-id="6e39d-178">Your device is now enrolled.</span></span>

    ![Bildschirm „Einrichten des Unternehmenszugriffs abgeschlossen“](./media/and-enroll-10-comp-access-setup-complete.png)

<span data-ttu-id="6e39d-180">Bevor Sie versuchen, Unternehmens-Apps zu installieren, wechseln Sie zu **Einstellungen** &gt; **Sicherheit**, und aktivieren Sie **Unknown sources** (Unbekannte Quellen).</span><span class="sxs-lookup"><span data-stu-id="6e39d-180">Before you try to install company apps, go to **Settings** &gt; **Security**, and turn on **Unknown sources**.</span></span> <span data-ttu-id="6e39d-181">Wenn Sie diese Option nicht aktivieren, bevor Sie versuchen, Apps zu installieren, wird die folgende Meldung angezeigt: „Installation blockiert.</span><span class="sxs-lookup"><span data-stu-id="6e39d-181">If you don't turn on this option before you try to install apps, you'll see the following message: "Install blocked.</span></span> <span data-ttu-id="6e39d-182">Aus Sicherheitsgründen ist Ihr Gerät so eingestellt, dass die Installation von Apps aus unbekannten Quellen blockiert wird.“</span><span class="sxs-lookup"><span data-stu-id="6e39d-182">For security reasons, your device is set to block installations of apps obtained from unknown sources."</span></span> <span data-ttu-id="6e39d-183">Sie können im Fehlerdialogfeld auf **Einstellungen** tippen, um zur Option **Unknown sources** zu wechseln.</span><span class="sxs-lookup"><span data-stu-id="6e39d-183">You can tap **Settings** on the error dialog box to go to the **Unknown sources** option.</span></span>

> [!Note]
> <span data-ttu-id="6e39d-184">Wenn Ihre Organisation Telecom Expense Management-Software verwendet, müssen Sie ein paar zusätzliche Schritte ausführen, bevor das Gerät vollständig registriert ist.</span><span class="sxs-lookup"><span data-stu-id="6e39d-184">If your organization is using telecom expense management software, you will have an additional few steps to complete before your device is fully enrolled.</span></span> <span data-ttu-id="6e39d-185">[Hier](enroll-your-device-with-telecom-expense-management-android.md) erfahren Sie mehr.</span><span class="sxs-lookup"><span data-stu-id="6e39d-185">Find out more [here](enroll-your-device-with-telecom-expense-management-android.md).</span></span>

<span data-ttu-id="6e39d-186">Sollte beim Versuch der Registrierung Ihres Geräts bei Intune ein Fehler auftreten, können Sie [Registrierungsfehler an den Support Ihres Unternehmens senden](send-enrollment-errors-to-your-it-admin-android.md).</span><span class="sxs-lookup"><span data-stu-id="6e39d-186">If you get an error while you try to enroll your device in Intune, you can [send enrollment errors to your company support](send-enrollment-errors-to-your-it-admin-android.md).</span></span>

<span data-ttu-id="6e39d-187">Benötigen Sie weitere Unterstützung?</span><span class="sxs-lookup"><span data-stu-id="6e39d-187">Still need help?</span></span> <span data-ttu-id="6e39d-188">Wenden Sie sich an den Support Ihres Unternehmens (suchen Sie auf der [Unternehmensportal-Website](https://portal.manage.microsoft.com#HelpDeskDialog) nach Kontaktinformationen) oder an das <a href="mailto:wintunedroidfbk@microsoft.com?subject=I'm having trouble with enrolling my Android device&body=Describe the issue you're experiencing here.">Microsoft Android-Team</a>.</span><span class="sxs-lookup"><span data-stu-id="6e39d-188">Contact your company support (check the [Company Portal website](https://portal.manage.microsoft.com#HelpDeskDialog) for contact information), or write the <a href="mailto:wintunedroidfbk@microsoft.com?subject=I'm having trouble with enrolling my Android device&body=Describe the issue you're experiencing here.">Microsoft Android team</a>.</span></span>
