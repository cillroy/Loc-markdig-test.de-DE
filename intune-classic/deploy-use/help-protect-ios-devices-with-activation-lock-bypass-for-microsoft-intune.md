---
title: "Verwalten der iOS-Aktivierungssperre auf Geräten"
description: "Microsoft Intune kann Sie beim Verwalten der iOS-Aktivierungssperre unterstützen, einem Feature der App „Mein iPhone suchen“ für iOS 7.1 und höher."
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 04/24/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: bb49e926-15c4-4f01-b6eb-cee6f7ee1984
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 0cdc029fc439707fb42f7aff66b4739bf542ca33
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2017
---
# <a name="help-protect-ios-devices-with-activation-lock-bypass-for-microsoft-intune"></a><span data-ttu-id="8ed41-103">Unterstützen des Schutz von iOS-Geräten durch Umgehung der Aktivierungssperre für Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="8ed41-103">Help protect iOS devices with Activation Lock bypass for Microsoft Intune</span></span>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="8ed41-104">Microsoft Intune kann Sie bei der Verwaltung der iOS-Aktivierungssperre unterstützen, einer Funktion der Mein iPhone suchen-App für Geräte mit iOS 8.0 und höher.</span><span class="sxs-lookup"><span data-stu-id="8ed41-104">Microsoft Intune can help you manage iOS Activation Lock, a feature of the Find My iPhone app for iOS 8.0 and later devices.</span></span> <span data-ttu-id="8ed41-105">Die Aktivierungssperre wird automatisch aktiviert, wenn ein Benutzer die App „Mein iPhone suchen“ auf einem Gerät öffnet.</span><span class="sxs-lookup"><span data-stu-id="8ed41-105">Activation Lock is enabled automatically when a user opens the Find My iPhone app on a device.</span></span> <span data-ttu-id="8ed41-106">Nach der Aktivierung müssen die Apple-ID und das Kennwort des Benutzers eingegeben werden, bevor folgende Vorgänge möglich sind:</span><span class="sxs-lookup"><span data-stu-id="8ed41-106">After it is enabled, the user's Apple ID and password must be entered before anyone can:</span></span> 

-   <span data-ttu-id="8ed41-107">Deaktivieren von „Mein iPhone suchen“</span><span class="sxs-lookup"><span data-stu-id="8ed41-107">Turn off Find My iPhone</span></span>

-   <span data-ttu-id="8ed41-108">Löschen des Geräts</span><span class="sxs-lookup"><span data-stu-id="8ed41-108">Erase the device</span></span>

-   <span data-ttu-id="8ed41-109">Reaktivieren des Geräts</span><span class="sxs-lookup"><span data-stu-id="8ed41-109">Reactivate the device</span></span>

## <a name="how-activation-lock-affects-you"></a><span data-ttu-id="8ed41-110">Auswirkungen der Aktivierungssperre</span><span class="sxs-lookup"><span data-stu-id="8ed41-110">How Activation Lock affects you</span></span>
<span data-ttu-id="8ed41-111">Obwohl die Aktivierungssperre zum Schutz von iOS-Geräten beiträgt und die Chancen einer Wiederherstellung bei Verlust oder Diebstahl des Geräts erhöht, kann diese Funktion Sie als IT-Administrator vor eine Reihe von Herausforderungen stellen.</span><span class="sxs-lookup"><span data-stu-id="8ed41-111">While Activation Lock helps secure iOS devices and improves the chances of recovering a lost or stolen device, this capability can present you, as an IT admin, with a number of challenges.</span></span> <span data-ttu-id="8ed41-112">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="8ed41-112">For example:</span></span>

-   <span data-ttu-id="8ed41-113">Ein Benutzer richtet die Aktivierungssperre auf einem Gerät ein.</span><span class="sxs-lookup"><span data-stu-id="8ed41-113">A user sets up Activation Lock on a device.</span></span> <span data-ttu-id="8ed41-114">Anschließend verlässt der Benutzer das Unternehmen und gibt das Gerät zurück.</span><span class="sxs-lookup"><span data-stu-id="8ed41-114">The user then leaves the company and returns the device.</span></span> <span data-ttu-id="8ed41-115">Ohne die Apple-ID und das Kennwort des Benutzers gibt es keine Möglichkeit, das Gerät zu reaktivieren.</span><span class="sxs-lookup"><span data-stu-id="8ed41-115">Without the user's Apple ID and password, there is no way to reactivate the device.</span></span>

-   <span data-ttu-id="8ed41-116">Sie benötigen einen Bericht über alle Geräte, bei denen die Aktivierungssperre aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="8ed41-116">You need a report of all devices that have Activation Lock enabled.</span></span>

-   <span data-ttu-id="8ed41-117">Während einer Geräteaktualisierung in Ihrem Unternehmen möchten Sie einige Geräte einer anderen Abteilung zuweisen.</span><span class="sxs-lookup"><span data-stu-id="8ed41-117">You want to reassign some devices to a different department during a device refresh in your organization.</span></span> <span data-ttu-id="8ed41-118">Es können nur Geräte neu zugewiesen werden, bei denen die Aktivierungssperre nicht aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="8ed41-118">You can only reassign devices that do not have Activation Lock enabled.</span></span>

<span data-ttu-id="8ed41-119">Apple hat zur Behebung dieser Probleme eine Umgehung der Aktivierungssperre in iOS 7.1 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="8ed41-119">To help solve these problems, Apple introduced Activation Lock bypass in iOS 7.1.</span></span> <span data-ttu-id="8ed41-120">Auf diese Weise können Sie die Aktivierungssperre von überwachten Geräten ohne Apple-ID und Kennwort des Benutzers entfernen.</span><span class="sxs-lookup"><span data-stu-id="8ed41-120">This lets you remove the Activation Lock from supervised devices without the user's Apple ID and password.</span></span> <span data-ttu-id="8ed41-121">Überwachte Geräte können einen gerätespezifischen Umgehungscode für die Aktivierungssperre generieren, der auf dem Aktivierungsserver von Apple gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="8ed41-121">Supervised devices can generate a device-specific Activation Lock bypass code, which is stored on Apple's activation server.</span></span>

> [!TIP]
> <span data-ttu-id="8ed41-122">Im überwachten Modus für iOS-Geräte können Sie mit dem Apple Configurator ein Gerät sperren, um die Funktionen auf bestimmte geschäftliche Zwecke zu beschränken.</span><span class="sxs-lookup"><span data-stu-id="8ed41-122">Supervised mode for iOS devices lets you use Apple Configurator to lock down a device and limit functionality to specific business purposes.</span></span> <span data-ttu-id="8ed41-123">Der überwachte Modus ist in der Regel nur für firmeneigene Geräte vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="8ed41-123">Supervised mode is generally only for corporate-owned devices.</span></span>

<span data-ttu-id="8ed41-124">Sie können [hier](https://support.apple.com/en-us/HT201365)mehr zur Aktivierungssperre erfahren.</span><span class="sxs-lookup"><span data-stu-id="8ed41-124">You can read more about Activation Lock [here](https://support.apple.com/en-us/HT201365).</span></span>

## <a name="how-intune-helps-you-manage-activation-lock"></a><span data-ttu-id="8ed41-125">Unterstützung von Intune beim Verwalten der Aktivierungssperre</span><span class="sxs-lookup"><span data-stu-id="8ed41-125">How Intune helps you manage Activation Lock</span></span>
<span data-ttu-id="8ed41-126">Intune kann den Status der Aktivierungssperre von überwachten Geräten anfordern, die iOS 8.0 und höher ausführen.</span><span class="sxs-lookup"><span data-stu-id="8ed41-126">Intune can request the Activation Lock status of supervised devices that run iOS 8.0 and later.</span></span> <span data-ttu-id="8ed41-127">Ausschließlich für überwachte Geräte kann Intune den Umgehungscode der Aktivierungssperre abrufen und ihn direkt auf das Gerät anwenden.</span><span class="sxs-lookup"><span data-stu-id="8ed41-127">For supervised devices only, Intune can retrieve the Activation Lock bypass code and directly issue it to the device.</span></span> <span data-ttu-id="8ed41-128">Wenn das Gerät zurückgesetzt wurde, können Sie direkt auf das Gerät zugreifen, indem Sie einen leeren Benutzernamen und den Code als Kennwort verwenden.</span><span class="sxs-lookup"><span data-stu-id="8ed41-128">If the device has been wiped, you can directly access the device by using a blank user name and the code as the password.</span></span>

<span data-ttu-id="8ed41-129">**Folgende Geschäftsvorteile ergeben sich**:</span><span class="sxs-lookup"><span data-stu-id="8ed41-129">**The business benefits of this are**:</span></span>

-   <span data-ttu-id="8ed41-130">Der Benutzer erhält die Sicherheitsvorteile der App „Mein iPhone suchen“.</span><span class="sxs-lookup"><span data-stu-id="8ed41-130">The user gets the security benefits of the Find My iPhone app.</span></span>

-   <span data-ttu-id="8ed41-131">Sie können es den Benutzern ermöglichen, ihre Arbeit zu erledigen, in dem Wissen, dass Sie das Gerät außer Kraft setzen oder entsperren können, wenn es einem neuen Zweck zugewiesen werden soll.</span><span class="sxs-lookup"><span data-stu-id="8ed41-131">You can enable users to do their work and know that when a device needs to be re-purposed, you can retire or unlock it.</span></span>

## <a name="before-you-start"></a><span data-ttu-id="8ed41-132">Vorbereitung</span><span class="sxs-lookup"><span data-stu-id="8ed41-132">Before you start</span></span>

<span data-ttu-id="8ed41-133">Bevor Sie die Aktivierungssperre auf Geräten umgehen können, müssen Sie sie zuerst aktivieren.</span><span class="sxs-lookup"><span data-stu-id="8ed41-133">Before you can bypass Activation Lock on devices, you must enable it first.</span></span> <span data-ttu-id="8ed41-134">Dazu gehen Sie folgendermaßen vor:</span><span class="sxs-lookup"><span data-stu-id="8ed41-134">To do this:</span></span>

1. <span data-ttu-id="8ed41-135">Nutzen Sie die Informationen im Thema [Verwalten von Einstellungen und Features auf Ihren Geräten mit Microsoft Intune-Richtlinien](/intune-classic/deploy-use/ios-policy-settings-in-microsoft-intune).</span><span class="sxs-lookup"><span data-stu-id="8ed41-135">Use the information in the topic [Manage settings and features on your devices with Microsoft Intune policies](/intune-classic/deploy-use/ios-policy-settings-in-microsoft-intune).</span></span>
2. <span data-ttu-id="8ed41-136">Setzen Sie auf der Einstellungsseite im Abschnitt **Registrierung** die Einstellung **Aktivierungssperre zulassen, wenn sich das Gerät im überwachten Modus befindet** auf **Ja**.</span><span class="sxs-lookup"><span data-stu-id="8ed41-136">In the **Enrollment** section, of the settings page, configure the setting **Allow Activation Lock when the device is in supervised mode** to **Yes**.</span></span>
3. <span data-ttu-id="8ed41-137">Speichern Sie die Richtlinie und stellen Sie sie für die Geräte bereit, auf denen Sie die Umgehung der Aktivierungssperre verwalten möchten.</span><span class="sxs-lookup"><span data-stu-id="8ed41-137">Save the policy, and deploy it to the devices on which you want to manage Activation Lock bypass.</span></span>

## <a name="how-to-use-activation-lock-bypass-from-the-intune-admin-console"></a><span data-ttu-id="8ed41-138">Verwenden der Umgehung der Aktivierungssperre über die Intune-Verwaltungskonsole</span><span class="sxs-lookup"><span data-stu-id="8ed41-138">How to use Activation Lock bypass from the Intune admin console</span></span>
> [!IMPORTANT]
> <span data-ttu-id="8ed41-139">Nachdem die Aktivierungssperre auf einem Gerät umgangen wurde, wird automatisch eine neue Aktivierungssperre angewendet, wenn die App „Mein iPhone suchen“ geöffnet wird.</span><span class="sxs-lookup"><span data-stu-id="8ed41-139">After you bypass the Activation Lock on a device, a new Activation Lock is automatically applied if the Find My iPhone app is opened.</span></span> <span data-ttu-id="8ed41-140">Aus diesem Grund **muss das Gerät physisch verfügbar sein, bevor Sie dieses Verfahren ausführen**.</span><span class="sxs-lookup"><span data-stu-id="8ed41-140">Because of this, **you should be in physical possession of the device before you follow this procedure**.</span></span>

1.  <span data-ttu-id="8ed41-141">Wählen Sie in der [Microsoft Intune-Verwaltungskonsole](https://manage.microsoft.com) die Optionen **Gruppen** &gt; **Alle Geräte** &gt; **Alle unternehmenseigenen Geräte** aus.</span><span class="sxs-lookup"><span data-stu-id="8ed41-141">In the [Microsoft Intune administration console](https://manage.microsoft.com), choose **Groups** &gt; **All Devices** &gt; **All Corporate-owned Devices**.</span></span>

2.  <span data-ttu-id="8ed41-142">Wählen Sie das Gerät aus, dessen Aktivierungssperre Sie umgehen möchten.</span><span class="sxs-lookup"><span data-stu-id="8ed41-142">Select the device whose Activation Lock you want to bypass.</span></span> <span data-ttu-id="8ed41-143">Wählen Sie **Aktivierungssperre umgehen** aus.</span><span class="sxs-lookup"><span data-stu-id="8ed41-143">Choose **Activation Lock Bypass**.</span></span>

3.  <span data-ttu-id="8ed41-144">Lesen Sie die Warnmeldung.</span><span class="sxs-lookup"><span data-stu-id="8ed41-144">Read the warning message.</span></span> <span data-ttu-id="8ed41-145">Klicken Sie auf **Ja**, um den Vorgang fortzusetzen.</span><span class="sxs-lookup"><span data-stu-id="8ed41-145">Choose **Yes** to proceed.</span></span>

<span data-ttu-id="8ed41-146">Sie können den Status der Entsperranforderung auf der Detailseite für das Gerät überprüfen.</span><span class="sxs-lookup"><span data-stu-id="8ed41-146">You can examine the status of the unlock request on the details page for the device.</span></span>

## <a name="how-to-see-which-devices-are-using-activation-lock"></a><span data-ttu-id="8ed41-147">Ermitteln der Geräte mit Aktivierungssperre</span><span class="sxs-lookup"><span data-stu-id="8ed41-147">How to see which devices are using Activation Lock</span></span>
<span data-ttu-id="8ed41-148">Es gibt zwei Möglichkeiten zur Ermittlung, welche Geräte die Aktivierungssperre verwenden:</span><span class="sxs-lookup"><span data-stu-id="8ed41-148">You can see which devices are using Activation Lock in two ways:</span></span>

-   <span data-ttu-id="8ed41-149">Führen Sie die **Bestandsberichte zu mobilen Geräten**aus.</span><span class="sxs-lookup"><span data-stu-id="8ed41-149">Run the **Mobile Device Inventory Reports**.</span></span> <span data-ttu-id="8ed41-150">In diesem Bericht werden die Spalten **Status der Aktivierungssperre** und **Überwacht** angezeigt, um den Status der Geräte anzugeben.</span><span class="sxs-lookup"><span data-stu-id="8ed41-150">This report displays the **Activation Lock Status** and **Supervised** columns to indicate the state of devices.</span></span> <span data-ttu-id="8ed41-151">Die Werte für **Überwacht** sind **Ja** oder **Nein**, und die Werte für **Status der Aktivierungssperre** lauten:</span><span class="sxs-lookup"><span data-stu-id="8ed41-151">The values for **Supervised** are **Yes** or **No**, and the values for **Activation Lock Status** are:</span></span>

    -   <span data-ttu-id="8ed41-152">Aktiviert mit Umgehungscode</span><span class="sxs-lookup"><span data-stu-id="8ed41-152">Enabled with bypass code</span></span>

    -   <span data-ttu-id="8ed41-153">Aktiviert ohne Umgehungscode (Gerät wird nicht überwacht)</span><span class="sxs-lookup"><span data-stu-id="8ed41-153">Enabled without bypass code (device is not supervised)</span></span>

    -   <span data-ttu-id="8ed41-154">Aktiviert ohne Umgehungscode (Gerät ist nicht erreichbar)</span><span class="sxs-lookup"><span data-stu-id="8ed41-154">Enabled without bypass code (device cannot be reached)</span></span>

    -   <span data-ttu-id="8ed41-155">Nicht aktiviert</span><span class="sxs-lookup"><span data-stu-id="8ed41-155">Not enabled</span></span>

    <span data-ttu-id="8ed41-156">Das Feld **Status der Aktivierungssperre** ist für Geräte leer, auf denen nicht iOS 8.0 oder höher ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="8ed41-156">The **Activation Lock Status** box is blank for devices that do not run iOS 8.0 or later.</span></span>

-   <span data-ttu-id="8ed41-157">Wählen Sie ein Gerät in einer Gruppenansicht aus, um den Status der Aktivierungssperre im Gerätedetailbereich anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="8ed41-157">Select a device in a groups view to see the Activation Lock status in the device details pane.</span></span>

    <span data-ttu-id="8ed41-158">Wenn Sie ein Gerät im Knoten **Alle unternehmenseigenen Geräte** auswählen und die Aktivierungssperre für das Gerät aktiviert ist, dann wird auch der Umgehungscode angezeigt.</span><span class="sxs-lookup"><span data-stu-id="8ed41-158">If you select a device in the **All Corporate-owned Devices** node and Activation Lock is enabled for the device, you can also see the bypass code.</span></span> <span data-ttu-id="8ed41-159">Dieser Code kann dazu verwendet werden, um die Umgehung einer Aktivierungssperre manuell auszuführen.</span><span class="sxs-lookup"><span data-stu-id="8ed41-159">This code can be used to manually issue an Activation Lock bypass.</span></span>

    > [!IMPORTANT]
    ><span data-ttu-id="8ed41-160">Intune erfasst alle sieben Tage den Status der Aktivierungssperre auf Geräten.</span><span class="sxs-lookup"><span data-stu-id="8ed41-160">Intune takes inventory from devices for Activation Lock every seven days.</span></span> <span data-ttu-id="8ed41-161">Aus diesem Grund werden Geräte in der Intune-Konsole möglicherweise nicht sofort mit dem richtigen Status der Aktivierungssperre angezeigt.</span><span class="sxs-lookup"><span data-stu-id="8ed41-161">Because of this, devices might not immediately be displayed with their Activation Lock status in the Intune console.</span></span>


### <a name="see-also"></a><span data-ttu-id="8ed41-162">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="8ed41-162">See also</span></span>
<span data-ttu-id="8ed41-163">[Abkoppeln von Geräten](retire-devices-from-microsoft-intune-management.md)
[Geräteschutz durch Remotesperre und Zurücksetzen der Kennung](use-remote-lock-and-passcode-reset-in-microsoft-intune.md)</span><span class="sxs-lookup"><span data-stu-id="8ed41-163">[Retire devices](retire-devices-from-microsoft-intune-management.md)
[Help protect your devices with remote lock and passcode reset](use-remote-lock-and-passcode-reset-in-microsoft-intune.md)</span></span>
