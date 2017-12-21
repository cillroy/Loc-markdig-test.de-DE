---
title: Bekannte Probleme in Microsoft Intune im Azure-Portal
titlesuffix: Azure portal
description: Informationen zu bekannten Problemen in Intune
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 10/31/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f33a6645-a57e-4424-a1e9-0ce932ea83c5
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 372e25968005258fd1e00cbab7db542ad0211206
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2017
---
# <a name="known-issues-in-microsoft-intune"></a><span data-ttu-id="56b51-103">Bekannte Probleme in Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="56b51-103">Known issues in Microsoft Intune</span></span>


[!INCLUDE[azure_portal](./includes/azure_portal.md)]


<span data-ttu-id="56b51-104">In diesem Thema erhalten Sie Informationen zu bekannten Problemen in Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="56b51-104">Use this topic to learn about any known issues in Microsoft Intune.</span></span>

<span data-ttu-id="56b51-105">Wenn Sie einen Fehler melden möchten, der hier nicht aufgeführt ist, [öffnen Sie eine Supportanfrage](get-support.md).</span><span class="sxs-lookup"><span data-stu-id="56b51-105">If you want to report a bug that is not listed here, [open a support request](get-support.md).</span></span>

<span data-ttu-id="56b51-106">Wenn Sie sich ein neues Feature für Intune wünschen, können Sie auf unserer [Uservoice](https://microsoftintune.uservoice.com/forums/291681-ideas/category/189016-azure-admin-console)-Website einen Bericht erstellen.</span><span class="sxs-lookup"><span data-stu-id="56b51-106">If you want to request a new feature for Intune, consider filing a report on our [Uservoice](https://microsoftintune.uservoice.com/forums/291681-ideas/category/189016-azure-admin-console) site.</span></span>

## <a name="migration"></a><span data-ttu-id="56b51-107">Migration</span><span class="sxs-lookup"><span data-stu-id="56b51-107">Migration</span></span>

### <a name="intune-legacy-pc-client-features-are-only-available-in-the-silverlight-console"></a><span data-ttu-id="56b51-108">Intune-Funktionen für Legacy-PC-Clients sind nur in der Silverlight-Konsole verfügbar</span><span class="sxs-lookup"><span data-stu-id="56b51-108">Intune legacy PC client features are only available in the Silverlight console</span></span>

<span data-ttu-id="56b51-109">Die Möglichkeit zum Verwalten von Windows 10 über die Registrierung bei Windows MDM steht in Intune über das Azure-Portal zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="56b51-109">The ability to manage Windows 10 in the Intune on Azure portal is available via Windows MDM enrollment.</span></span> <span data-ttu-id="56b51-110">Weitere Informationen finden Sie unter [Intune in der Azure-Konsole und der Legacy-Intune-PC-Client](https://docs.microsoft.com/intune-classic/deploy-use/intune-on-azure).</span><span class="sxs-lookup"><span data-stu-id="56b51-110">For more information, see [Intune on Azure console and legacy Intune PC Client](https://docs.microsoft.com/intune-classic/deploy-use/intune-on-azure).</span></span>

### <a name="groups-created-by-intune-during-migration-might-affect-functionality-of-other-microsoft-products"></a><span data-ttu-id="56b51-111">Während der Migration von Intune erstellte Gruppen könnten die Funktionalität anderer Microsoft-Produkte beeinträchtigen.</span><span class="sxs-lookup"><span data-stu-id="56b51-111">Groups created by Intune during migration might affect functionality of other Microsoft products</span></span>

<span data-ttu-id="56b51-112">Beim Migrieren von Intune zum Azure-Portal könnten Sie eine neue Gruppe mit dem Namen **All Users - b0b08746-4dbe-4a37-9adf-9e7652c0b421** sehen.</span><span class="sxs-lookup"><span data-stu-id="56b51-112">When you migrate from Intune to the Azure portal, you might see a new group named **All Users - b0b08746-4dbe-4a37-9adf-9e7652c0b421**.</span></span> <span data-ttu-id="56b51-113">Diese Gruppe enthält alle Benutzer in Ihrem Azure Active Directory, nicht nur Benutzer mit Intune-Lizenz.</span><span class="sxs-lookup"><span data-stu-id="56b51-113">This group contains all users in your Azure Active Directory, not only Intune licensed users.</span></span> <span data-ttu-id="56b51-114">Dies könnte zu Problemen mit anderen Microsoft-Produkten führen, wenn Sie erwarten, dass einige vorhandene oder neue Benutzer nicht Mitglieder von Gruppen sind.</span><span class="sxs-lookup"><span data-stu-id="56b51-114">This usage can cause issues with other Microsoft products if you expect some existing or new users to not be a member of any groups.</span></span>

### <a name="secondary-migration-required-for-select-capabilities"></a><span data-ttu-id="56b51-115">Sekundäre Migration für ausgewählte Funktionen erforderlich</span><span class="sxs-lookup"><span data-stu-id="56b51-115">Secondary migration required for select capabilities</span></span>

<span data-ttu-id="56b51-116">Vor Januar 2017 erstellte Intune-Konten müssen migriert werden, ehe die folgenden Funktionen im Azure-Portal verwendet werden können:</span><span class="sxs-lookup"><span data-stu-id="56b51-116">Intune accounts created before January 2017 must be migrated before the following capabilities can be used in the Azure portal:</span></span>

- <span data-ttu-id="56b51-117">Profile für die Unternehmensgeräteregistrierung</span><span class="sxs-lookup"><span data-stu-id="56b51-117">Corporate Device Enrollment profiles</span></span>
- <span data-ttu-id="56b51-118">Apple-Programm zur Geräteregistrierung</span><span class="sxs-lookup"><span data-stu-id="56b51-118">Apple Device Enrollment Program</span></span>
- <span data-ttu-id="56b51-119">Firmeneigene Geräten über die iOS-Seriennummer vorab deklarieren</span><span class="sxs-lookup"><span data-stu-id="56b51-119">Predeclare corporate devices by iOS serial number</span></span>
- <span data-ttu-id="56b51-120">Konten für den Geräteregistrierungs-Manager</span><span class="sxs-lookup"><span data-stu-id="56b51-120">Device Enrollment Manager accounts</span></span>
- <span data-ttu-id="56b51-121">Apple Volume Purchase Program</span><span class="sxs-lookup"><span data-stu-id="56b51-121">Apple Volume Purchase Program</span></span>

<span data-ttu-id="56b51-122">Da diese Funktionen nicht über die Intune-Konsole (Silverlight) und das Azure-Portal verwaltet werden können, erfolgt bei der Migration Folgendes:</span><span class="sxs-lookup"><span data-stu-id="56b51-122">Because these capabilities cannot be managed from both the Intune (Silverlight) console and Azure portal, the migration:</span></span>
- <span data-ttu-id="56b51-123">Werden im klassischen Portal deaktiviert</span><span class="sxs-lookup"><span data-stu-id="56b51-123">Disables them in the classic portal</span></span>
- <span data-ttu-id="56b51-124">Werden im Azure-Portal aktiviert</span><span class="sxs-lookup"><span data-stu-id="56b51-124">Enables them in the Azure portal</span></span>  

<span data-ttu-id="56b51-125">Nach dem 22. September 2017 wird die Migration dieser Funktionen in der primären Migration zu Azure zusammengeführt.</span><span class="sxs-lookup"><span data-stu-id="56b51-125">After September 22, 2017, the migration of these features will be merged into the primary migration to Azure.</span></span> <span data-ttu-id="56b51-126">Wenn Ihr Konto bereits zum Azure-Portal migriert wurde, ist es möglich, dass diese sekundäre Migration bereits abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="56b51-126">If your account was already migrated to use the Azure portal, this secondary migration may have been completed by now.</span></span> <span data-ttu-id="56b51-127">Falls dies nicht der Fall ist, werden diese Funktionen bis November 2017 zu Azure migriert.</span><span class="sxs-lookup"><span data-stu-id="56b51-127">If not, these capabilities will be migrated to Azure by November.</span></span> <span data-ttu-id="56b51-128">Sobald Ihre Kontomigration eingeleitet wurde, wird sie auch am selben Tag abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="56b51-128">Once your account’s migration begins, it will complete the same day.</span></span> <span data-ttu-id="56b51-129">Die Migration kann ab dem Zeitpunkt der Deaktivierung dieser Funktionen im klassischen Intune-Portal bis zu 6 Stunden in Anspruch nehmen.</span><span class="sxs-lookup"><span data-stu-id="56b51-129">Migration can take up to 6 hours from the time these features are disabled in the Intune classic portal.</span></span>

<span data-ttu-id="56b51-130">Wenn Sie diese Intune-Funktionen nun im Azure-Portal verwalten, achten Sie auf die folgenden Punkte:</span><span class="sxs-lookup"><span data-stu-id="56b51-130">If you now manage these Intune capabilities in the Azure portal, be aware of the following points:</span></span>

#### <a name="removes-default-corporate-device-enrollment-profiles-in-apple-dep"></a><span data-ttu-id="56b51-131">Profile für die Unternehmensgeräteregistrierung im Apple-Programm zur Geräteregistrierung (DEP) wurden entfernt.</span><span class="sxs-lookup"><span data-stu-id="56b51-131">Removes default Corporate Device Enrollment profiles in Apple DEP</span></span>
<span data-ttu-id="56b51-132">Das Azure-Portal unterstützt nicht das Standardprofil für Unternehmensgeräteregistrierungen für Geräte im Apple DEP.</span><span class="sxs-lookup"><span data-stu-id="56b51-132">The Azure portal does not support a default Corporate Device Enrollment profile for Apple Device Enrollment Program (DEP) devices.</span></span> <span data-ttu-id="56b51-133">Diese Funktionalität, die in der Intune-Konsole (Silverlight) zur Verfügung steht, wird nicht fortgeführt, um unbeabsichtigte Zuweisungen von Profilen zu verhindern.</span><span class="sxs-lookup"><span data-stu-id="56b51-133">This functionality, available in the Intune (Silverlight) console, is discontinued to prevent unintentional profile assignment.</span></span> <span data-ttu-id="56b51-134">Wenn DEP-Seriennummern im Azure-Portal synchronisiert werden, wird kein Profil zur Unternehmensgeräteregistrierung zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="56b51-134">When DEP serial numbers sync in the Azure portal, no Corporate Device Enrollment profile is assigned.</span></span> <span data-ttu-id="56b51-135">Vor der Nutzung des Geräts muss ein Registrierungsprofil zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="56b51-135">An enrollment profile must be assigned before using the device.</span></span>

#### <a name="apple-dep-token-restored-with-migration"></a><span data-ttu-id="56b51-136">Apple DEP-Token bei Migration wiederhergestellt</span><span class="sxs-lookup"><span data-stu-id="56b51-136">Apple DEP token restored with migration</span></span>

<span data-ttu-id="56b51-137">Wenn Sie ein Token für das Apple-Programm zur Geräteregistrierung im Intune-Portal (Silverlight) gelöscht haben und kein neues Token im Azure-Portal hochladen, wird das ursprüngliche Token während der Migration im Azure-Portal wiederhergestellt.</span><span class="sxs-lookup"><span data-stu-id="56b51-137">If you deleted an Apple Device Enrollment Program token in the Intune (Silverlight) portal and do not upload a new token to the Azure portal, the original token is restored in the Azure portal when you migrate.</span></span> <span data-ttu-id="56b51-138">Wenn Sie dieses Token entfernen und die DEP-Registrierung verhindern möchten, löschen Sie das Token aus dem Azure-Portal.</span><span class="sxs-lookup"><span data-stu-id="56b51-138">To remove this token and prevent DEP enrollment, delete the token from the Azure portal.</span></span>

### <a name="status-blades-for-migrated-policies-do-not-work"></a><span data-ttu-id="56b51-139">Statusblätter für migrierte Richtlinien funktionieren nicht</span><span class="sxs-lookup"><span data-stu-id="56b51-139">Status blades for migrated policies do not work</span></span>

<span data-ttu-id="56b51-140">Sie können keine Statusinformationen für Richtlinien anzeigen, die aus dem klassischen Intune-Portal in das Azure-Portal migriert wurden.</span><span class="sxs-lookup"><span data-stu-id="56b51-140">You cannot view status information for policies that were migrated from the classic portal in the Azure portal.</span></span> <span data-ttu-id="56b51-141">Im klassischen Portal können Sie jedoch weiterhin Berichte für diese Richtlinien anzeigen.</span><span class="sxs-lookup"><span data-stu-id="56b51-141">However, you can continue to view reports for these policies in the classic portal.</span></span> <span data-ttu-id="56b51-142">Zum Anzeigen von Statusinformationen für migrierte Konfigurationsrichtlinien müssen Sie diese im Azure-Portal neu erstellen.</span><span class="sxs-lookup"><span data-stu-id="56b51-142">To view status information for migrated configuration policies, recreate them in the Azure portal.</span></span>

## <a name="apps"></a><span data-ttu-id="56b51-143">Apps</span><span class="sxs-lookup"><span data-stu-id="56b51-143">Apps</span></span>

### <a name="ios-volume-purchased-apps-only-available-in-default-intune-tenant-language"></a><span data-ttu-id="56b51-144">Per Volumenlizenz erworbene Apps nur in Standardsprache des Intune-Mandanten verfügbar</span><span class="sxs-lookup"><span data-stu-id="56b51-144">iOS volume-purchased apps only available in default Intune tenant language</span></span>
<span data-ttu-id="56b51-145">Per Volumenlizenz erworbene iOS-Apps werden angezeigt und können nur für den gleichen Ländercode wie Ihr Intune-Konto zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="56b51-145">iOS volume-purchased apps are displayed, and can be assigned only for the same country code as your Intune account.</span></span> <span data-ttu-id="56b51-146">Intune synchronisiert nur Apps aus dem gleichen iTunes-Gebietsschema wie der Ländercode des Intune-Mandantenkontos.</span><span class="sxs-lookup"><span data-stu-id="56b51-146">Intune only sync apps from the same iTunes locale as the Intune tenant account country code.</span></span> <span data-ttu-id="56b51-147">Wenn Sie beispielsweise eine App kaufen, die nur im US-Store verfügbar ist, Ihr Intune-Konto jedoch auf Deutsch ist, zeigt Intune diese App nicht an.</span><span class="sxs-lookup"><span data-stu-id="56b51-147">For example, if you purchase an app which is only available in the U.S. store, but your Intune account is German, Intune will not show that app.</span></span>

### <a name="multiple-copies-of-the-same-ios-volume-purchase-program-are-uploaded"></a><span data-ttu-id="56b51-148">Es werden mehrere Kopien desselben iOS-Volumenlizenzprogramms hochgeladen.</span><span class="sxs-lookup"><span data-stu-id="56b51-148">Multiple copies of the same iOS volume-purchase program are uploaded</span></span>
<span data-ttu-id="56b51-149">Klicken Sie nicht mehrmals für das gleiche VPP-Token auf die Schaltfläche **Hochladen**.</span><span class="sxs-lookup"><span data-stu-id="56b51-149">Do not click the **Upload** button multiple times for the same VPP token.</span></span> <span data-ttu-id="56b51-150">Dies führt dazu, dass doppelte VPP-Token hochgeladen und Apps mehrmals für das gleiche VPP-Token synchronisiert werden.</span><span class="sxs-lookup"><span data-stu-id="56b51-150">This will result in duplicate VPP tokens being uploaded, and apps syncing multiple times for the same VPP token.</span></span>

<!-- ## Groups -->

## <a name="device-configuration"></a><span data-ttu-id="56b51-151">Gerätekonfiguration</span><span class="sxs-lookup"><span data-stu-id="56b51-151">Device configuration</span></span>

### <a name="you-cannot-save-a-windows-information-protection-policy-for-some-devices"></a><span data-ttu-id="56b51-152">Eine Windows Information Protection-Richtlinie kann für einige Geräte nicht gespeichert werden</span><span class="sxs-lookup"><span data-stu-id="56b51-152">You cannot save a Windows Information Protection policy for some devices</span></span>

<span data-ttu-id="56b51-153">Für Geräte, die nicht bei Intune registriert sind, können Sie in den Einstellungen für eine Windows Information Protection-Richtlinie im Feld **Unternehmensidentität** nur eine primäre Domäne angeben.</span><span class="sxs-lookup"><span data-stu-id="56b51-153">For devices not enrolled with Intune, you can only specify a primary domain in the **Corporate Identify** field in the settings for a Windows Information Protection policy.</span></span>
<span data-ttu-id="56b51-154">Wenn Sie (über **Erweiterte Einstellungen** > **Umkreisnetzwerk** > **Geschützte Domäne hinzufügen**) weitere Domänen hinzufügen, können Sie die Richtlinie nicht speichern.</span><span class="sxs-lookup"><span data-stu-id="56b51-154">If you add additional domains (using **Advanced settings** > **Network perimeter** > **Add a protected domain**), you cannot save the policy.</span></span> <span data-ttu-id="56b51-155">Die angezeigte Fehlermeldung wird in Kürze geändert, um mehr Genauigkeit zu bieten.</span><span class="sxs-lookup"><span data-stu-id="56b51-155">The error message you see will soon be changed to be more accurate.</span></span>

### <a name="cisco-anyconnect-vpn-client-support"></a><span data-ttu-id="56b51-156">Cisco AnyConnect VPN-Client-Unterstützung</span><span class="sxs-lookup"><span data-stu-id="56b51-156">Cisco AnyConnect VPN client support</span></span>

<span data-ttu-id="56b51-157">Das neueste Release des Cisco AnyConnect VPN-Clients (4.0.07072) ist derzeit nicht mit Intune kompatibel.</span><span class="sxs-lookup"><span data-stu-id="56b51-157">The latest release of the Cisco AnyConnect VPN client (4.0.07072) is not currently compatible with Intune.</span></span>
<span data-ttu-id="56b51-158">Ein zukünftiges Intune-Update wird die Kompatibilität mit dieser Version des VPN-Clients beinhalten.</span><span class="sxs-lookup"><span data-stu-id="56b51-158">A future Intune update will include compatibility with this VPN client version.</span></span> <span data-ttu-id="56b51-159">Bis dahin wird empfohlen, dass Sie Ihren Cisco AnyConnect VPN-Client nicht aktualisieren und weiterhin die vorhandene Version verwenden.</span><span class="sxs-lookup"><span data-stu-id="56b51-159">Until then, we recommend that you do not update your Cisco AnyConnect VPN client, and continue to use the existing version.</span></span>

### <a name="using-the-numeric-password-type-with-macos-sierra-devices"></a><span data-ttu-id="56b51-160">Verwenden des numerischen Kennworttyps mit macOS Sierra-Geräten</span><span class="sxs-lookup"><span data-stu-id="56b51-160">Using the numeric password type with macOS Sierra devices</span></span>

<span data-ttu-id="56b51-161">Wenn Sie derzeit in einem Geräteregistrierungsprofil für macOS Sierra-Geräte **Numerisch** **Erforderlicher Kennworttyp** auswählen, wird **Alphanumerisch** erzwungen.</span><span class="sxs-lookup"><span data-stu-id="56b51-161">Currently, if you select the **Numeric** **Required password type** in a device restriction profile for macOS Sierra devices, it is enforced as **Alphanumeric**.</span></span> <span data-ttu-id="56b51-162">Wenn Sie kein numerisches Kennwort mit diesen Geräten verwenden möchten, konfigurieren Sie diese Einstellung nicht.</span><span class="sxs-lookup"><span data-stu-id="56b51-162">If you want to use a numeric password with these devices, do not configure this setting.</span></span>
<span data-ttu-id="56b51-163">Dieses Problem wird ggf. in einer künftigen Version von MacOS korrigiert.</span><span class="sxs-lookup"><span data-stu-id="56b51-163">This issue might be corrected in a future version of macOS.</span></span>

<span data-ttu-id="56b51-164">Weitere Informationen zu diesen Einstellungen finden Sie unter [Einstellungen für Geräteeinschränkungen für macOS-Geräte in Microsoft Intune](device-restrictions-macos.md).</span><span class="sxs-lookup"><span data-stu-id="56b51-164">For more information about these settings, see [macOS device restriction settings in Microsoft Intune](device-restrictions-macos.md).</span></span>

## <a name="compliance"></a><span data-ttu-id="56b51-165">Konformität</span><span class="sxs-lookup"><span data-stu-id="56b51-165">Compliance</span></span>

### <a name="compliance-policies-from-intune-do-not-show-up-in-new-console"></a><span data-ttu-id="56b51-166">Konformitätsrichtlinien von Intune werden in der neuen Konsole nicht angezeigt</span><span class="sxs-lookup"><span data-stu-id="56b51-166">Compliance policies from Intune do not show up in new console</span></span>

<span data-ttu-id="56b51-167">Konformitätsrichtlinien, die Sie im klassischen Intune-Portal erstellt haben, werden migriert, jedoch im Azure-Portal aufgrund von Änderungen am Design nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="56b51-167">Compliance policies you created in the classic portal are migrated, but are not displayed in the Azure portal because of design changes in the Azure portal.</span></span> <span data-ttu-id="56b51-168">Konformitätsrichtlinien, die Sie im klassischen Intune-Portal erstellt haben, werden noch erzwungen, jedoch müssen Sie sie im klassischen Portal anzeigen und bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="56b51-168">Compliance policies you created in the Intune classic portal are still enforced, but you must view and edit them in the classic portal.</span></span>

<span data-ttu-id="56b51-169">Darüber hinaus werden neue Konformitätsrichtlinien, die Sie im Azure-Portal erstellen, im klassischen Portal nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="56b51-169">Additionally, new compliance policies you create in the Azure portal are not visible in the classic portal.</span></span>

<span data-ttu-id="56b51-170">Weitere Informationen finden Sie unter [Was ist die Gerätekonformität in Intune in Azure (Vorschau)?](device-compliance.md).</span><span class="sxs-lookup"><span data-stu-id="56b51-170">For more information, see [What is device compliance](device-compliance.md).</span></span>

<!-- ## Enrollment -->


## <a name="data-protection"></a><span data-ttu-id="56b51-171">Datenschutz</span><span class="sxs-lookup"><span data-stu-id="56b51-171">Data protection</span></span>

### <a name="ios-app-protection-policies"></a><span data-ttu-id="56b51-172">iOS-App-Schutzrichtlinien</span><span class="sxs-lookup"><span data-stu-id="56b51-172">iOS app protection policies</span></span>

<span data-ttu-id="56b51-173">Sie können [App-Schutzrichtlinien für iOS](app-protection-policy-settings-ios.md) definieren, die für Benutzer auf Geräten verfügbar sind, die über die Verwaltung mobiler Geräte (MAM) ohne Registrierung verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="56b51-173">You can define [app protection policies for iOS](app-protection-policy-settings-ios.md) that are available for users on devices managed through mobile app management (MAM) without enrollment.</span></span> <span data-ttu-id="56b51-174">Aufgrund eines temporären Fehlers können Sie diese Richtlinien nur für iOS-Versionen mit einer Version mit einem einzelnen Dezimaltrennzeichen anstatt mehreren Dezimaltrennzeichen definieren.</span><span class="sxs-lookup"><span data-stu-id="56b51-174">Due to a temporary error, you can only define these policies for iOS versions with a single decimal point version rather than multiple decimal points.</span></span> <span data-ttu-id="56b51-175">Anstatt also eine Mindestversion von iOS 10.3.1 festzulegen, legen Sie sie für iOS 10.3. fest.</span><span class="sxs-lookup"><span data-stu-id="56b51-175">Instead of setting a minimum version of iOS 10.3.1, you set it for iOS 10.3.</span></span> <span data-ttu-id="56b51-176">Diese Problem wird mit einem zukünftigen Update für das iOS SDK gelöst.</span><span class="sxs-lookup"><span data-stu-id="56b51-176">This will be resolved with a forthcoming update to the iOS SDK.</span></span>


## <a name="administration-and-accounts"></a><span data-ttu-id="56b51-177">Verwaltung und Konten</span><span class="sxs-lookup"><span data-stu-id="56b51-177">Administration and accounts</span></span>

<span data-ttu-id="56b51-178">Globale Administratoren (auch als Mandantenadministratoren bezeichnet) können weiterhin alltägliche Verwaltungsaufgaben ausführen, ohne über eine separate Intune- oder EMS-Lizenz (Enterprise Mobility Suite) zu verfügen.</span><span class="sxs-lookup"><span data-stu-id="56b51-178">Global Admins (also referred to as Tenant Admins) can continue day-to-day administration tasks without a separate Intune or Enterprise Mobility Suite (EMS) license.</span></span> <span data-ttu-id="56b51-179">Wenn sie den Dienst jedoch verwenden möchten, um z. B. ihr eigenes Gerät oder ein unternehmenseigenes Gerät zu registrieren bzw. das Intune-Unternehmensportal zu verwenden, benötigen sie eine Intune- oder EMS-Lizenz.</span><span class="sxs-lookup"><span data-stu-id="56b51-179">However, to use the service, such as to enroll their own device, a corporate device, or use the Intune Company Portal, they need an Intune or EMS license.</span></span>

<!-- ## Additional items -->
