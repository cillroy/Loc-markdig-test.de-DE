---
title: Umgehung der iOS-Aktivierungssperre mit Intune
titlesuffix: Azure portal
description: "Erfahren Sie, wie Sie mithilfe von Intune die iOS-Aktivierungssperre umgehen, um auf gesperrte Geräte zuzugreifen.\""
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 08/22/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 9ca3b0ba-e41c-45fb-af28-119dff47c59f
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: d960486a93a5b8825e8c015553e12d9d7bc4b017
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2018
---
# <a name="bypass-activation-lock-on-supervised-ios-devices-with-intune"></a><span data-ttu-id="c9ad7-103">Umgehen der Aktivierungssperre auf überwachten iOS-Geräten mit Intune</span><span class="sxs-lookup"><span data-stu-id="c9ad7-103">Bypass Activation Lock on Supervised iOS devices with Intune</span></span>


[!INCLUDE [azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="c9ad7-104">Microsoft Intune kann Sie bei der Verwaltung der iOS-Aktivierungssperre unterstützen, einer Funktion der Mein iPhone suchen-App für Geräte mit iOS 8.0 und höher.</span><span class="sxs-lookup"><span data-stu-id="c9ad7-104">Microsoft Intune can help you manage iOS Activation Lock, a feature of the Find My iPhone app for iOS 8.0 and later devices.</span></span> <span data-ttu-id="c9ad7-105">Die Aktivierungssperre wird automatisch aktiviert, wenn ein Benutzer die App „Mein iPhone suchen“ auf einem Gerät öffnet.</span><span class="sxs-lookup"><span data-stu-id="c9ad7-105">Activation Lock is enabled automatically when a user opens the Find My iPhone app on a device.</span></span> <span data-ttu-id="c9ad7-106">Nach der Aktivierung müssen die Apple-ID und das Kennwort des Benutzers eingegeben werden, bevor folgende Vorgänge möglich sind:</span><span class="sxs-lookup"><span data-stu-id="c9ad7-106">After it is enabled, the user's Apple ID and password must be entered before anyone can:</span></span>

- <span data-ttu-id="c9ad7-107">Deaktivieren von „Mein iPhone suchen“</span><span class="sxs-lookup"><span data-stu-id="c9ad7-107">Turn off Find My iPhone</span></span>
- <span data-ttu-id="c9ad7-108">Löschen des Geräts</span><span class="sxs-lookup"><span data-stu-id="c9ad7-108">Erase the device</span></span>
- <span data-ttu-id="c9ad7-109">Reaktivieren des Geräts</span><span class="sxs-lookup"><span data-stu-id="c9ad7-109">Reactivate the device</span></span>

## <a name="how-activation-lock-affects-you"></a><span data-ttu-id="c9ad7-110">Auswirkungen der Aktivierungssperre</span><span class="sxs-lookup"><span data-stu-id="c9ad7-110">How Activation Lock affects you</span></span>

<span data-ttu-id="c9ad7-111">Obwohl die Aktivierungssperre zum Schutz von iOS-Geräten beiträgt und die Chancen einer Wiederherstellung bei Verlust oder Diebstahl des Geräts erhöht, kann diese Funktion Sie als IT-Administrator vor eine Reihe von Herausforderungen stellen.</span><span class="sxs-lookup"><span data-stu-id="c9ad7-111">While Activation Lock helps secure iOS devices and improves the chances of recovering a lost or stolen device, this capability can present you, as an IT admin, with a number of challenges.</span></span> <span data-ttu-id="c9ad7-112">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="c9ad7-112">For example:</span></span>

- <span data-ttu-id="c9ad7-113">Ein Benutzer richtet die Aktivierungssperre auf einem Gerät ein.</span><span class="sxs-lookup"><span data-stu-id="c9ad7-113">A user sets up Activation Lock on a device.</span></span> <span data-ttu-id="c9ad7-114">Anschließend verlässt der Benutzer das Unternehmen und gibt das Gerät zurück.</span><span class="sxs-lookup"><span data-stu-id="c9ad7-114">The user then leaves the company and returns the device.</span></span> <span data-ttu-id="c9ad7-115">Ohne die Apple-ID und das Kennwort des Benutzers gibt es keine Möglichkeit, das Gerät zu reaktivieren.</span><span class="sxs-lookup"><span data-stu-id="c9ad7-115">Without the user's Apple ID and password, there is no way to reactivate the device.</span></span>
- <span data-ttu-id="c9ad7-116">Sie benötigen einen Bericht über alle Geräte, bei denen die Aktivierungssperre aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="c9ad7-116">You need a report of all devices that have Activation Lock enabled.</span></span>
- <span data-ttu-id="c9ad7-117">Während einer Geräteaktualisierung in Ihrem Unternehmen möchten Sie einige Geräte einer anderen Abteilung zuweisen.</span><span class="sxs-lookup"><span data-stu-id="c9ad7-117">You want to reassign some devices to a different department during a device refresh in your organization.</span></span> <span data-ttu-id="c9ad7-118">Es können nur Geräte neu zugewiesen werden, bei denen die Aktivierungssperre nicht aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="c9ad7-118">You can only reassign devices that do not have Activation Lock enabled.</span></span>

<span data-ttu-id="c9ad7-119">Apple hat zur Behebung dieser Probleme eine Umgehung der Aktivierungssperre in iOS 7.1 eingeführt.</span><span class="sxs-lookup"><span data-stu-id="c9ad7-119">To help solve these problems, Apple introduced Activation Lock bypass in iOS 7.1.</span></span> <span data-ttu-id="c9ad7-120">Mit der Umgehung der Aktivierungssperre können Sie die Aktivierungssperre von überwachten Geräten ohne Apple-ID und Kennwort des Benutzers entfernen.</span><span class="sxs-lookup"><span data-stu-id="c9ad7-120">Activation Lock bypass lets you remove the Activation Lock from supervised devices without the user's Apple ID and password.</span></span> <span data-ttu-id="c9ad7-121">Überwachte Geräte können einen gerätespezifischen Umgehungscode für die Aktivierungssperre generieren, der auf dem Aktivierungsserver von Apple gespeichert wird.</span><span class="sxs-lookup"><span data-stu-id="c9ad7-121">Supervised devices can generate a device-specific Activation Lock bypass code, which is stored on Apple's activation server.</span></span>

>[!TIP]
><span data-ttu-id="c9ad7-122">Im überwachten Modus für iOS-Geräte können Sie mit dem Apple Configurator ein Gerät sperren, um die Funktionen auf bestimmte geschäftliche Zwecke zu beschränken.</span><span class="sxs-lookup"><span data-stu-id="c9ad7-122">Supervised mode for iOS devices lets you use Apple Configurator to lock down a device and limit functionality to specific business purposes.</span></span> <span data-ttu-id="c9ad7-123">Der überwachte Modus ist in der Regel nur für firmeneigene Geräte vorgesehen.</span><span class="sxs-lookup"><span data-stu-id="c9ad7-123">Supervised mode is used only for corporate-owned devices.</span></span>

<span data-ttu-id="c9ad7-124">Auf der [Website von Apple](https://support.apple.com/HT201365) erfahren Sie mehr über die Aktivierungssperre.</span><span class="sxs-lookup"><span data-stu-id="c9ad7-124">You can read more about Activation Lock on [Apple's web site](https://support.apple.com/HT201365).</span></span>

## <a name="how-intune-helps-you-manage-activation-lock"></a><span data-ttu-id="c9ad7-125">Unterstützung von Intune beim Verwalten der Aktivierungssperre</span><span class="sxs-lookup"><span data-stu-id="c9ad7-125">How Intune helps you manage Activation Lock</span></span>
<span data-ttu-id="c9ad7-126">Intune kann den Status der Aktivierungssperre von überwachten Geräten anfordern, die iOS 8.0 und höher ausführen.</span><span class="sxs-lookup"><span data-stu-id="c9ad7-126">Intune can request the Activation Lock status of supervised devices that run iOS 8.0 and later.</span></span> <span data-ttu-id="c9ad7-127">Ausschließlich für überwachte Geräte kann Intune den Umgehungscode der Aktivierungssperre abrufen und ihn direkt auf das Gerät anwenden.</span><span class="sxs-lookup"><span data-stu-id="c9ad7-127">For supervised devices only, Intune can retrieve the Activation Lock bypass code and directly issue it to the device.</span></span> <span data-ttu-id="c9ad7-128">Wenn das Gerät zurückgesetzt wurde, können Sie direkt auf das Gerät zugreifen, indem Sie einen leeren Benutzernamen und den Code als Kennwort verwenden.</span><span class="sxs-lookup"><span data-stu-id="c9ad7-128">If the device has been wiped, you can directly access the device by using a blank user name and the code as the password.</span></span>

<span data-ttu-id="c9ad7-129">**Die Unternehmensvorteile der Verwaltung der Aktivierungssperre mit Intune sind Folgende:**</span><span class="sxs-lookup"><span data-stu-id="c9ad7-129">**The business benefits of using Intune to manage Activation Lock are:**</span></span>

- <span data-ttu-id="c9ad7-130">Der Benutzer erhält die Sicherheitsvorteile der App „Mein iPhone suchen“.</span><span class="sxs-lookup"><span data-stu-id="c9ad7-130">The user gets the security benefits of the Find My iPhone app.</span></span>
- <span data-ttu-id="c9ad7-131">Sie können es den Benutzern ermöglichen, ihre Arbeit zu erledigen, in dem Wissen, dass Sie das Gerät außer Kraft setzen oder entsperren können, wenn es einem neuen Zweck zugewiesen werden soll.</span><span class="sxs-lookup"><span data-stu-id="c9ad7-131">You can enable users to do their work and know that when a device needs to be repurposed, you can retire or unlock it.</span></span>

## <a name="before-you-start"></a><span data-ttu-id="c9ad7-132">Vorbereitung</span><span class="sxs-lookup"><span data-stu-id="c9ad7-132">Before you start</span></span>
<span data-ttu-id="c9ad7-133">Bevor Sie die Aktivierungssperre auf Geräten umgehen können, müssen Sie sie aktivieren, indem Sie dieser Anleitung folgen:</span><span class="sxs-lookup"><span data-stu-id="c9ad7-133">Before you can bypass Activation Lock on devices, you must enable it by following these instructions:</span></span>

1. <span data-ttu-id="c9ad7-134">Konfigurieren Sie ein Intune-Profil für die Einschränkung von Geräten für iOS. Verwenden Sie dafür die Informationen unter [So konfigurieren Sie Einstellungen für Geräteeinschränkungen](/intune-azure/configure-devices/how-to-configure-device-restrictions).</span><span class="sxs-lookup"><span data-stu-id="c9ad7-134">Configure an Intune device restriction profile for iOS using the information in [How to configure device restriction settings](/intune-azure/configure-devices/how-to-configure-device-restrictions).</span></span>
2. <span data-ttu-id="c9ad7-135">Aktivieren Sie in den [Einstellungen für Geräteeinschränkungen für iOS](device-restrictions-ios.md) unter **Allgemein** die Option **Aktivierungssperre**.</span><span class="sxs-lookup"><span data-stu-id="c9ad7-135">In the [device restriction settings for iOS](device-restrictions-ios.md), under the **General** settings, enable the option **Activation Lock**.</span></span>
3. <span data-ttu-id="c9ad7-136">Speichern Sie das Profil, und [weisen Sie es den Geräten zu](device-profile-assign.md), auf denen Sie die Umgehung der Aktivierungssperre verwalten möchten.</span><span class="sxs-lookup"><span data-stu-id="c9ad7-136">Save the profile, and then [assign it](device-profile-assign.md) to the devices on which you want to manage Activation Lock bypass.</span></span>


## <a name="how-to-use-activation-lock-bypass"></a><span data-ttu-id="c9ad7-137">Verwenden der Umgehung der Aktivierungssperre</span><span class="sxs-lookup"><span data-stu-id="c9ad7-137">How to use Activation Lock bypass</span></span>

>[!IMPORTANT]
><span data-ttu-id="c9ad7-138">Nachdem die Aktivierungssperre auf einem Gerät umgangen wurde, wird automatisch eine neue Aktivierungssperre angewendet, wenn die App „Mein iPhone suchen“ geöffnet wird.</span><span class="sxs-lookup"><span data-stu-id="c9ad7-138">After you bypass the Activation Lock on a device, if the Find My iPhone app is opened, a new Activation Lock is automatically applied.</span></span> <span data-ttu-id="c9ad7-139">Aus diesem Grund **muss das Gerät physisch verfügbar sein, bevor Sie dieses Verfahren ausführen**.</span><span class="sxs-lookup"><span data-stu-id="c9ad7-139">Because of this, **you should be in physical possession of the device before you follow this procedure**.</span></span>

<span data-ttu-id="c9ad7-140">Die Intune-Remotegeräteaktion **Aktivierungssperre umgehen** entfernt die Aktivierungssperre auf einem iOS-Gerät, ohne dass die Apple-ID und das Kennwort des Benutzers angegeben werden muss.</span><span class="sxs-lookup"><span data-stu-id="c9ad7-140">The Intune **Bypass Activation Lock** remote device action removes the activation lock from an iOS device without the user’s Apple ID and password.</span></span> <span data-ttu-id="c9ad7-141">Nachdem Sie die Aktivierungssperre umgangen haben, aktiviert das Gerät die Aktivierungssperre erneut, wenn die App „Mein iPhone suchen“ gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="c9ad7-141">Once you bypass the activation lock, the device turns on activation lock again when the Find My iPhone app launches.</span></span> <span data-ttu-id="c9ad7-142">Umgehen Sie die Aktivierungssperre nur, wenn Sie physischen Zugriff auf das Gerät haben.</span><span class="sxs-lookup"><span data-stu-id="c9ad7-142">Only bypass the activation lock if you have physical access to the device.</span></span>

1. <span data-ttu-id="c9ad7-143">Melden Sie sich beim Azure-Portal an.</span><span class="sxs-lookup"><span data-stu-id="c9ad7-143">Sign into the Azure portal.</span></span>
2. <span data-ttu-id="c9ad7-144">Wählen Sie **Weitere Dienste** > **Überwachung und Verwaltung** > **Intune** aus.</span><span class="sxs-lookup"><span data-stu-id="c9ad7-144">Choose **More Services** > **Monitoring + Management** > **Intune**.</span></span>
3. <span data-ttu-id="c9ad7-145">Wählen Sie auf dem Blatt **Intune** die Option **Geräte** aus.</span><span class="sxs-lookup"><span data-stu-id="c9ad7-145">On the **Intune** blade, choose **Devices**.</span></span>
4. <span data-ttu-id="c9ad7-146">Wählen Sie auf dem Blatt **Geräte und Gruppen** die Option **Alle Geräte** aus.</span><span class="sxs-lookup"><span data-stu-id="c9ad7-146">On the **Devices and groups** blade, choose **All devices**.</span></span>
5. <span data-ttu-id="c9ad7-147">Wählen Sie aus der Liste der verwalteten Geräte ein überwachtes iOS-Gerät aus, und wählen Sie dann die Remotegeräteaktion **Aktivierungssperre umgehen**.</span><span class="sxs-lookup"><span data-stu-id="c9ad7-147">From the list of devices you manage, choose a supervised iOS device, and then choose the **Bypass Activation Lock** device remote action.</span></span>

## <a name="next-steps"></a><span data-ttu-id="c9ad7-148">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="c9ad7-148">Next steps</span></span>

<span data-ttu-id="c9ad7-149">Sie können den Status der Entsperranforderung in der Workload **Geräte verwalten** auf der Detailseite für das Gerät überprüfen.</span><span class="sxs-lookup"><span data-stu-id="c9ad7-149">You can examine the status of the unlock request on the details page for the device in the **Manage devices** workload.</span></span>
