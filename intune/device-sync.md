---
title: "Synchronisieren von Geräten mit Intune"
titlesuffix: Azure portal
description: "Erfahren Sie, wie Sie Geräte mit Intune synchronisieren, um die neuesten Richtlinien und Aktionen zu erhalten."
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 08/09/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 02ad249e-f098-421f-861f-6b2ff733ac7c
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: dadcd33f39827365fc3f22c46d4332f3ea3cbf09
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2017
---
# <a name="sync-devices-with-intune-to-get-the-latest-policies-and-actions"></a><span data-ttu-id="3c8cb-103">Synchronisieren von Geräten mit Intune, um die neuesten Richtlinien und Aktionen zu erhalten</span><span class="sxs-lookup"><span data-stu-id="3c8cb-103">Sync devices with Intune to get the latest policies and actions</span></span>


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="3c8cb-104">Die Geräteaktion **Sync** (Synchronsieren) zwingt das ausgewählte Gerät dazu, sofort bei Intune einzuchecken.</span><span class="sxs-lookup"><span data-stu-id="3c8cb-104">The **Sync** device action forces the selected device to immediately check in with Intune.</span></span> <span data-ttu-id="3c8cb-105">Checkt ein Gerät ein, empfängt es sofort alle ihm zugewiesenen ausstehenden Aktionen oder Richtlinien.</span><span class="sxs-lookup"><span data-stu-id="3c8cb-105">When a device checks in, it immediately receives any pending actions or policies that have been assigned to it.</span></span>  <span data-ttu-id="3c8cb-106">Dadurch können Sie sofort zugewiesene Richtlinien überprüfen und Probleme beheben, ohne den nächsten geplanten Check-In abwarten zu müssen.</span><span class="sxs-lookup"><span data-stu-id="3c8cb-106">This action can help you to immediately validate and troubleshoot policies you’ve assigned, without waiting for the next scheduled check-in.</span></span>

## <a name="supported-platforms"></a><span data-ttu-id="3c8cb-107">Unterstützte Plattformen</span><span class="sxs-lookup"><span data-stu-id="3c8cb-107">Supported platforms</span></span>

- <span data-ttu-id="3c8cb-108">Windows</span><span class="sxs-lookup"><span data-stu-id="3c8cb-108">Windows</span></span>
- <span data-ttu-id="3c8cb-109">Windows Phone</span><span class="sxs-lookup"><span data-stu-id="3c8cb-109">Windows Phone</span></span>
- <span data-ttu-id="3c8cb-110">iOS</span><span class="sxs-lookup"><span data-stu-id="3c8cb-110">iOS</span></span>
- <span data-ttu-id="3c8cb-111">macOS</span><span class="sxs-lookup"><span data-stu-id="3c8cb-111">macOS</span></span>
- <span data-ttu-id="3c8cb-112">Android</span><span class="sxs-lookup"><span data-stu-id="3c8cb-112">Android</span></span>

## <a name="how-to-sync-a-device"></a><span data-ttu-id="3c8cb-113">So synchronisieren Sie ein Gerät</span><span class="sxs-lookup"><span data-stu-id="3c8cb-113">How to sync a device</span></span>

1. <span data-ttu-id="3c8cb-114">Melden Sie sich beim Azure-Portal an.</span><span class="sxs-lookup"><span data-stu-id="3c8cb-114">Sign into the Azure portal.</span></span>
2. <span data-ttu-id="3c8cb-115">Wählen Sie **Weitere Dienste** > **Überwachung und Verwaltung** > **Intune** aus.</span><span class="sxs-lookup"><span data-stu-id="3c8cb-115">Choose **More Services** > **Monitoring + Management** > **Intune**.</span></span>
3. <span data-ttu-id="3c8cb-116">Wählen Sie auf dem Blatt **Intune** die Option **Geräte** aus.</span><span class="sxs-lookup"><span data-stu-id="3c8cb-116">On the **Intune** blade, choose **Devices**.</span></span>
4. <span data-ttu-id="3c8cb-117">Wählen Sie auf dem Blatt **Geräte und Gruppen** die Option **Alle Geräte** aus.</span><span class="sxs-lookup"><span data-stu-id="3c8cb-117">On the **Devices and groups** blade, choose **All devices**.</span></span>
5. <span data-ttu-id="3c8cb-118">Wählen Sie aus der Liste der verwalteten Geräte ein Gerät aus, und wählen Sie dann die Remotegeräteaktion **Sync** aus.</span><span class="sxs-lookup"><span data-stu-id="3c8cb-118">From the list of devices you manage, choose a device, and then choose the **Sync** remote action.</span></span>
7. <span data-ttu-id="3c8cb-119">Wählen Sie zum Bestätigen der Aktion **Ja** aus.</span><span class="sxs-lookup"><span data-stu-id="3c8cb-119">Choose **Yes** to confirm the action.</span></span>


## <a name="retriable-error-codes"></a><span data-ttu-id="3c8cb-120">Wiederholbare Fehlercodes</span><span class="sxs-lookup"><span data-stu-id="3c8cb-120">Retriable error codes</span></span>

<span data-ttu-id="3c8cb-121">Wenn ein Administrator die Geräteaktion **Sync** ausführt, sind iOS- und Android-Apps, die zwar fehlgeschlagen sind, aber einen wiederholbaren Fehlercode ausgelöst haben, auf dem Gerät verfügbar.</span><span class="sxs-lookup"><span data-stu-id="3c8cb-121">When an administrator runs the **Sync** device action, iOS and Androids apps that failed but  raised a retriable error code will be available to the device.</span></span> <span data-ttu-id="3c8cb-122">Allerdings dauert es sieben Tage, bis Apps, die einen nicht wiederholbaren Fehlercode ausgelöst haben, auf dem Gerät verfügbar gemacht werden können.</span><span class="sxs-lookup"><span data-stu-id="3c8cb-122">However, apps that raised a non-retriable error code must wait for seven days before they can be made available to the device.</span></span>


| <span data-ttu-id="3c8cb-123">Fehlercode</span><span class="sxs-lookup"><span data-stu-id="3c8cb-123">Error Code</span></span>  | <span data-ttu-id="3c8cb-124">Vorgeschlagene Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3c8cb-124">Suggested Description</span></span>                                                                                                                  | <span data-ttu-id="3c8cb-125">Wiederholbar</span><span class="sxs-lookup"><span data-stu-id="3c8cb-125">Retriable</span></span> |
|-------------|----------------------------------------------------------------------------------------------------------------------------------------|-----------|
| <span data-ttu-id="3c8cb-126">2016330898</span><span class="sxs-lookup"><span data-stu-id="3c8cb-126">2016330898</span></span> | <span data-ttu-id="3c8cb-127">Unbekannter Fehler aufgetreten.</span><span class="sxs-lookup"><span data-stu-id="3c8cb-127">An unknown error occurred.</span></span>                                                                                                             | <span data-ttu-id="3c8cb-128">Nein</span><span class="sxs-lookup"><span data-stu-id="3c8cb-128">No</span></span>        |
| <span data-ttu-id="3c8cb-129">2016330897</span><span class="sxs-lookup"><span data-stu-id="3c8cb-129">2016330897</span></span> | <span data-ttu-id="3c8cb-130">Ihre Verbindung zu Intune wurde aufgrund einer Zeitüberschreitung abgebrochen. Setzen Sie Ihre Verbindung zurück.</span><span class="sxs-lookup"><span data-stu-id="3c8cb-130">Your connection to Intune timed out. Reset your connection</span></span>                                                                             | <span data-ttu-id="3c8cb-131">Ja</span><span class="sxs-lookup"><span data-stu-id="3c8cb-131">Yes</span></span>       |
| <span data-ttu-id="3c8cb-132">2016330896</span><span class="sxs-lookup"><span data-stu-id="3c8cb-132">2016330896</span></span> | <span data-ttu-id="3c8cb-133">Ihre Internetverbindung wurde getrennt.</span><span class="sxs-lookup"><span data-stu-id="3c8cb-133">You lost connection to the Internet.</span></span> <span data-ttu-id="3c8cb-134">Setzen Sie Ihre Verbindung zurück.</span><span class="sxs-lookup"><span data-stu-id="3c8cb-134">Reset your connection.</span></span>                                                                            | <span data-ttu-id="3c8cb-135">Ja</span><span class="sxs-lookup"><span data-stu-id="3c8cb-135">Yes</span></span>       |
| <span data-ttu-id="3c8cb-136">2016330895</span><span class="sxs-lookup"><span data-stu-id="3c8cb-136">2016330895</span></span> | <span data-ttu-id="3c8cb-137">Ihre Internetverbindung wurde getrennt.</span><span class="sxs-lookup"><span data-stu-id="3c8cb-137">You lost connection to the Internet.</span></span> <span data-ttu-id="3c8cb-138">Setzen Sie Ihre Verbindung zurück.</span><span class="sxs-lookup"><span data-stu-id="3c8cb-138">Reset your connection.</span></span>                                                                            | <span data-ttu-id="3c8cb-139">Ja</span><span class="sxs-lookup"><span data-stu-id="3c8cb-139">Yes</span></span>       |
| <span data-ttu-id="3c8cb-140">2016330894</span><span class="sxs-lookup"><span data-stu-id="3c8cb-140">2016330894</span></span> | <span data-ttu-id="3c8cb-141">Ihre Internetverbindung wurde getrennt.</span><span class="sxs-lookup"><span data-stu-id="3c8cb-141">You lost connection to the Internet.</span></span> <span data-ttu-id="3c8cb-142">Setzen Sie Ihre Verbindung zurück.</span><span class="sxs-lookup"><span data-stu-id="3c8cb-142">Reset your connection.</span></span>                                                                            | <span data-ttu-id="3c8cb-143">Ja</span><span class="sxs-lookup"><span data-stu-id="3c8cb-143">Yes</span></span>       |
| <span data-ttu-id="3c8cb-144">2016330893</span><span class="sxs-lookup"><span data-stu-id="3c8cb-144">2016330893</span></span> | <span data-ttu-id="3c8cb-145">Ihre Internetverbindung wurde getrennt.</span><span class="sxs-lookup"><span data-stu-id="3c8cb-145">You lost connection to the Internet.</span></span> <span data-ttu-id="3c8cb-146">Setzen Sie Ihre Verbindung zurück.</span><span class="sxs-lookup"><span data-stu-id="3c8cb-146">Reset your connection.</span></span>                                                                            | <span data-ttu-id="3c8cb-147">Ja</span><span class="sxs-lookup"><span data-stu-id="3c8cb-147">Yes</span></span>       |
| <span data-ttu-id="3c8cb-148">2016330892</span><span class="sxs-lookup"><span data-stu-id="3c8cb-148">2016330892</span></span> | <span data-ttu-id="3c8cb-149">Internationales Roaming ist deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="3c8cb-149">International roaming is disabled.</span></span>                                                                                                     | <span data-ttu-id="3c8cb-150">Nein</span><span class="sxs-lookup"><span data-stu-id="3c8cb-150">No</span></span>        |
| <span data-ttu-id="3c8cb-151">2016330891</span><span class="sxs-lookup"><span data-stu-id="3c8cb-151">2016330891</span></span> | <span data-ttu-id="3c8cb-152">Während eines Anrufs kann für dieses Gerät nicht auf die Mobilfunkverbindung zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="3c8cb-152">The cellular data connection for this device cannot be accessed while a phone call is being made.</span></span> <span data-ttu-id="3c8cb-153">Warten Sie, bis der Anruf beendet wird.</span><span class="sxs-lookup"><span data-stu-id="3c8cb-153">Wait for the phone call to complete.</span></span> | <span data-ttu-id="3c8cb-154">Ja</span><span class="sxs-lookup"><span data-stu-id="3c8cb-154">Yes</span></span>       |
| <span data-ttu-id="3c8cb-155">2016330890</span><span class="sxs-lookup"><span data-stu-id="3c8cb-155">2016330890</span></span> | <span data-ttu-id="3c8cb-156">Das Mobilfunknetz für dieses Gerät:</span><span class="sxs-lookup"><span data-stu-id="3c8cb-156">The cellular network for this device.</span></span> <span data-ttu-id="3c8cb-157">Diese Geräte konnten zu diesem Zeitpunkt nicht verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="3c8cb-157">These devices could not be used at this time.</span></span>                                                   | <span data-ttu-id="3c8cb-158">Nein</span><span class="sxs-lookup"><span data-stu-id="3c8cb-158">No</span></span>        |
| <span data-ttu-id="3c8cb-159">2016330889</span><span class="sxs-lookup"><span data-stu-id="3c8cb-159">2016330889</span></span> | <span data-ttu-id="3c8cb-160">Fehler bei der sicheren Verbindung:</span><span class="sxs-lookup"><span data-stu-id="3c8cb-160">The secure connection failed.</span></span> <span data-ttu-id="3c8cb-161">Setzen Sie Ihre Verbindung zurück.</span><span class="sxs-lookup"><span data-stu-id="3c8cb-161">Reset your connection.</span></span>                                                                                   | <span data-ttu-id="3c8cb-162">Ja</span><span class="sxs-lookup"><span data-stu-id="3c8cb-162">Yes</span></span>       |
| <span data-ttu-id="3c8cb-163">2016330888</span><span class="sxs-lookup"><span data-stu-id="3c8cb-163">2016330888</span></span> | <span data-ttu-id="3c8cb-164">Fehler bei der Auswertung der Serververtrauensstellung</span><span class="sxs-lookup"><span data-stu-id="3c8cb-164">The server trust evaluation has failed.</span></span>                                                                                                | <span data-ttu-id="3c8cb-165">Nein</span><span class="sxs-lookup"><span data-stu-id="3c8cb-165">No</span></span>        |

## <a name="next-steps"></a><span data-ttu-id="3c8cb-166">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="3c8cb-166">Next steps</span></span>

<span data-ttu-id="3c8cb-167">Wählen Sie **Geräteaktionen** aus, um den Status der Synchronisierung anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="3c8cb-167">Choose **Device Actions** to see the status of the sync action.</span></span> 
