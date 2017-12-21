---
title: "Überwachen von Intune-Richtlinien zur Gerätekompatibilität"
titlesuffix: Azure portal
description: "Erfahren Sie, wie Sie Richtlinien zur Gerätekonformität überwachen.\""
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 03/10/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 503d1dd2-a647-4aea-bf48-55319a3dd8a7
ms.reviewer: muhosabe
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 4b293ff41af58d4ab41a8477219939b13ffe361c
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2017
---
# <a name="monitor-intune-device-compliance-policies"></a><span data-ttu-id="1bf79-103">Überwachen von Intune-Richtlinien zur Gerätekompatibilität</span><span class="sxs-lookup"><span data-stu-id="1bf79-103">Monitor Intune Device compliance policies</span></span>

<span data-ttu-id="1bf79-104">Mithilfe von Kompatibilitätsberichten können Administratoren die Kompatibilität von Geräten in ihrer Organisation analysieren und schnell kompatibilitätsbezogene Probleme behandeln, die bei Benutzern in ihrer Organisation auftreten.</span><span class="sxs-lookup"><span data-stu-id="1bf79-104">Compliance reports help admins to analyze the compliance posture of devices in their organization, and quickly troubleshoot compliance related issues encountered by users inside their organization.</span></span> <span data-ttu-id="1bf79-105">Sie können Informationen zum allgemeinen Kompatibilitätsstatus von Geräten, zum Kompatibilitätsstatus einer einzelnen Einstellung und zum Kompatibilitätsstatus einer einzelnen Richtlinie sowie Detailinformationen zu einzelnen Geräten anzeigen, um sich über bestimmte Einstellungen und Richtlinien zu informieren, die das Gerät betreffen.</span><span class="sxs-lookup"><span data-stu-id="1bf79-105">You can view information about the overall compliance state of devices, compliance state for an individual setting, compliance state for an individual policy and drill down into individual devices to view specific settings and policies that affect the device.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="1bf79-106">Vorbereitung</span><span class="sxs-lookup"><span data-stu-id="1bf79-106">Before you begin</span></span>

<span data-ttu-id="1bf79-107">Gehen Sie wie folgt vor, um im Azure-Portal zum **Intune-Dashboard für die Gerätekompatibilität** zu gelangen:</span><span class="sxs-lookup"><span data-stu-id="1bf79-107">Follow the steps below to find the **Intune Device compliance dashboard** in the Azure portal:</span></span>

1.  <span data-ttu-id="1bf79-108">Melden Sie sich im [Azure-Portal](https://portal.azure.com) mit Ihren Intune-Anmeldeinformationen an.</span><span class="sxs-lookup"><span data-stu-id="1bf79-108">Go to the [Azure Portal](https://portal.azure.com), and sign in with your Intune credentials.</span></span>

2.  <span data-ttu-id="1bf79-109">Wählen Sie im linken Menü **Weitere Dienste** aus, und geben Sie in das Filtertextfeld die Zeichenfolge **Intune** ein.</span><span class="sxs-lookup"><span data-stu-id="1bf79-109">Choose **More services** from the left menu, then type **Intune** in the text box filter.</span></span>

3.  <span data-ttu-id="1bf79-110">Wählen Sie **Intune** &gt; **Gerätekompatibilität** &gt; **Übersicht** aus. Daraufhin wird das **Gerätekompatibilitätsdashboard** geöffnet.</span><span class="sxs-lookup"><span data-stu-id="1bf79-110">Choose **Intune** &gt; **Device compliance** &gt; **Overview**, then the **Device compliance dashboard** opens.</span></span>

> [!IMPORTANT] 
> <span data-ttu-id="1bf79-111">Geräte müssen in Intune registriert werden, um Gerätekompatibilitätsrichtlinien empfangen zu können.</span><span class="sxs-lookup"><span data-stu-id="1bf79-111">Devices must be enrolled into Intune to receive device compliance policies.</span></span>

## <a name="device-compliance-dashboard"></a><span data-ttu-id="1bf79-112">Gerätekompatibilitätsdashboard</span><span class="sxs-lookup"><span data-stu-id="1bf79-112">Device compliance dashboard</span></span>

<span data-ttu-id="1bf79-113">Auf dem **Gerätekompatibilitätsdashboard** können den Status der Gerätekompatibilität überwachen. Zu diesem Zweck stehen verschiedene Kacheln mit unterschiedlichen Berichten zur Verfügung, die Aufschluss über die Kompatibilität von Geräten in Ihrer Organisation geben.</span><span class="sxs-lookup"><span data-stu-id="1bf79-113">In the **Device compliance dashboard**, you can monitor the Device compliance policy states, which provides different reports within different tiles that give you the compliance posture of devices in your organization.</span></span> <span data-ttu-id="1bf79-114">Folgende Berichte sind verfügbar:</span><span class="sxs-lookup"><span data-stu-id="1bf79-114">You can view the following reports:</span></span>

-   <span data-ttu-id="1bf79-115">Allgemeine Gerätekompatibilität (aggregiert)</span><span class="sxs-lookup"><span data-stu-id="1bf79-115">Overall device compliance aggregate</span></span>

-   <span data-ttu-id="1bf79-116">Richtlinienspezifische Gerätekompatibilität</span><span class="sxs-lookup"><span data-stu-id="1bf79-116">Per-policy device compliance</span></span>

-   <span data-ttu-id="1bf79-117">Einstellungsspezifische Gerätekompatibilität</span><span class="sxs-lookup"><span data-stu-id="1bf79-117">Per-setting device compliance</span></span>

![Gerätekompatibilitätsdashboard](./media/idc-1.png)

<span data-ttu-id="1bf79-119">Darüber hinaus können Sie die spezifischen Kompatibilitätsrichtlinien und Einstellungen für ein bestimmtes Gerät sowie den endgültigen Kompatibilitätsstatus für die einzelnen Einstellungen auf dem Gerät anzeigen.</span><span class="sxs-lookup"><span data-stu-id="1bf79-119">You can also view the specific compliance policies and settings that apply to an individual device, and the final compliance state for each of those settings on the device.</span></span>

### <a name="overall-device-compliance-aggregate-report"></a><span data-ttu-id="1bf79-120">Aggregierter Bericht zur allgemeinen Gerätekompatibilität</span><span class="sxs-lookup"><span data-stu-id="1bf79-120">Overall device compliance aggregate report</span></span>

<span data-ttu-id="1bf79-121">Hierbei handelt es sich um ein Ringdiagramm mit dem aggregierten Kompatibilitätsstatus aller in Intune registrierten Geräte.</span><span class="sxs-lookup"><span data-stu-id="1bf79-121">It’s a donut chart showing the aggregate compliance state for all Intune enrolled devices.</span></span> <span data-ttu-id="1bf79-122">Die Werte für den Gerätekompatibilitätsstatus werden in zwei Datenbanken (Intune und Azure Active Directory) gespeichert.</span><span class="sxs-lookup"><span data-stu-id="1bf79-122">The device compliance states are kept in two different databases, Intune and Azure Active Directory.</span></span> <span data-ttu-id="1bf79-123">Im Anschluss werden die Statuswerte der Gerätekompatibilitätsrichtlinie ausführlicher beschrieben:</span><span class="sxs-lookup"><span data-stu-id="1bf79-123">Here’s more details about the device compliance policy states:</span></span>

-   <span data-ttu-id="1bf79-124">**Kompatibel**: Das Gerät hat erfolgreich mindestens eine vom Administrator festgelegte Einstellung der Gerätekompatibilitätsrichtlinie angewendet.</span><span class="sxs-lookup"><span data-stu-id="1bf79-124">**Compliant**: The device successfully applied one or more device compliance policy settings targeted by the admin.</span></span>

-   <span data-ttu-id="1bf79-125">**Nicht kompatibel**: Das Gerät konnte mindestens eine vom Administrator festgelegte Einstellung der Gerätekompatibilitätsrichtlinie nicht anwenden, oder der Benutzer verstößt gegen die vom Administrator festgelegten Richtlinien.</span><span class="sxs-lookup"><span data-stu-id="1bf79-125">**Not-compliant:** The device failed to apply one or more device compliance policy settings targeted by the admin or the user hasn’t complied with the policies targeted by the admin.</span></span>

-   <span data-ttu-id="1bf79-126">**In-grace period** (In Toleranzperiode): Für das Gerät wurde vom Administrator mindestens eine Einstellung für die Gerätekompatibilitätsrichtlinie festgelegt, diese wurden vom Benutzer aber noch nicht angewendet. Das Gerät ist daher zwar noch nicht kompatibel, befindet sich aber in der vom Administrator definierten Toleranzperiode.</span><span class="sxs-lookup"><span data-stu-id="1bf79-126">**In-grace period:** The device was targeted by the admin with one or more device compliance policy settings, but the user hasn’t applied the policies yet, which means the device is not-compliant, but it’s in the grace-period defined by the admin.</span></span>

    -   <span data-ttu-id="1bf79-127">Informieren Sie sich ausführlicher über Aktionen für nicht kompatible Geräte.</span><span class="sxs-lookup"><span data-stu-id="1bf79-127">Learn more about Actions for non-compliant devices.</span></span>

-   <span data-ttu-id="1bf79-128">**Device not synced** (Gerät nicht synchronisiert): Das Gerät konnte den Status der Gerätekompatibilitätsrichtlinie nicht melden. Mögliche Ursachen:</span><span class="sxs-lookup"><span data-stu-id="1bf79-128">**Device not synced:** The device failed to report its device compliance policy status because one of the following:</span></span>

    -   <span data-ttu-id="1bf79-129">**Unbekannt**: Das Gerät ist offline oder konnte aus einem anderen Grund nicht mit Intune oder Azure AD kommunizieren.</span><span class="sxs-lookup"><span data-stu-id="1bf79-129">**Unknown**: The device is offline or failed to communicate with Intune or Azure AD for other reasons.</span></span>

    -   <span data-ttu-id="1bf79-130">**Fehler**: Das Gerät konnte nicht mit Intune und Azure AD kommunizieren und hat eine Fehlermeldung mit der Ursache erhalten.</span><span class="sxs-lookup"><span data-stu-id="1bf79-130">**Error**: The device failed to communicate with Intune and Azure AD, and received an error message with the reason.</span></span>

> [!IMPORTANT] 
> <span data-ttu-id="1bf79-131">In Intune registrierte Geräte, für die keine Gerätekompatibilitätsrichtlinien festgelegt sind, werden in diesem Bericht der Kategorie **Kompatibel** zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="1bf79-131">Devices that are enrolled into Intune, but not targeted by any device compliance policies will be included in this report under the **Compliant** bucket.</span></span>

#### <a name="drill-down-option"></a><span data-ttu-id="1bf79-132">Anzeigen von Detailinformationen</span><span class="sxs-lookup"><span data-stu-id="1bf79-132">Drill-down option</span></span>

<span data-ttu-id="1bf79-133">Wenn Sie auf dem **Gerätekompatibilitätsdashboard** auf die Gerätekompatibilitätskachel klicken, können Sie für jedes Gerät, für das Gerätekompatibilitätsrichtlinien festgelegt sind, Detailinformationen zu einem bestimmten **Kompatibilitätsstatus**, **E-Mail-Alias des Benutzers**, **Gerätemodell** und **Standort** anzeigen.</span><span class="sxs-lookup"><span data-stu-id="1bf79-133">From the **Device compliance dashboard**, If you click on the Device compliance tile, you can drill-down into a specific **compliance status**, **user’s email alias**, **device model**, and **location** for each device that was targeted by the device compliance policies.</span></span>

![Gerätekompatibilitätsdashboard – Detailinformationen](./media/idc-2.png)

<span data-ttu-id="1bf79-135">Sollten Sie weitere Details zu einem bestimmten Benutzer benötigen, können Sie den Bericht mit dem Gerätekompatibilitätsdiagramm filtern, indem Sie den E-Mail-Alias des Benutzers eingeben.</span><span class="sxs-lookup"><span data-stu-id="1bf79-135">If you need more details about a specific user, you can filter the Device compliance chart report by typing the user’s e-mail alias.</span></span>

![Gerätekompatibilitätsdashboard – bestimmter Benutzer](./media/idc-3.png)

<span data-ttu-id="1bf79-137">Sie können auch auf die verschiedenen Kompatibilitätsstatuswerte des Gerätekompatibilitätsdiagramms klicken, um für den Benutzer weitere Details zu den Statuswerten der Gerätekompatibilitätsrichtlinie zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="1bf79-137">You can also click the different compliance status on the Device compliance chart to see more details about the user’s devices compliance policy statuses.</span></span>

![Gerätekompatibilitätsdashboard – verschiedene Statuswerte](./media/idc-4.png)

#### <a name="filter"></a><span data-ttu-id="1bf79-139">Filter</span><span class="sxs-lookup"><span data-stu-id="1bf79-139">Filter</span></span>

<span data-ttu-id="1bf79-140">Wenn Sie auf die Schaltfläche **Filter** klicken, wird das Filterflyout mit folgenden Optionen geöffnet:</span><span class="sxs-lookup"><span data-stu-id="1bf79-140">If you click on **Filter button**, the filter fly-out opens with the following options:</span></span>

-   <span data-ttu-id="1bf79-141">Modell</span><span class="sxs-lookup"><span data-stu-id="1bf79-141">Model</span></span>

    -   <span data-ttu-id="1bf79-142">Textfeld zur Eingabe einer beliebigen Suchzeichenfolge</span><span class="sxs-lookup"><span data-stu-id="1bf79-142">Textbox accepting free search string</span></span>
<br></br>
-   <span data-ttu-id="1bf79-143">Plattform</span><span class="sxs-lookup"><span data-stu-id="1bf79-143">Platform</span></span>

    -   <span data-ttu-id="1bf79-144">Android</span><span class="sxs-lookup"><span data-stu-id="1bf79-144">Android</span></span>

    -   <span data-ttu-id="1bf79-145">iOS</span><span class="sxs-lookup"><span data-stu-id="1bf79-145">iOS</span></span>

    -   <span data-ttu-id="1bf79-146">Mac OS</span><span class="sxs-lookup"><span data-stu-id="1bf79-146">Mac OS</span></span>

    -   <span data-ttu-id="1bf79-147">Windows</span><span class="sxs-lookup"><span data-stu-id="1bf79-147">Windows</span></span>

    -   <span data-ttu-id="1bf79-148">Windows Phone</span><span class="sxs-lookup"><span data-stu-id="1bf79-148">Windows Phone</span></span>

-   <span data-ttu-id="1bf79-149">Status</span><span class="sxs-lookup"><span data-stu-id="1bf79-149">Status</span></span>

    -   <span data-ttu-id="1bf79-150">Kompatibel</span><span class="sxs-lookup"><span data-stu-id="1bf79-150">Compliant</span></span>

    -   <span data-ttu-id="1bf79-151">Nicht kompatibel</span><span class="sxs-lookup"><span data-stu-id="1bf79-151">Not Compliant</span></span>

    -   <span data-ttu-id="1bf79-152">In Grace period (In Toleranzperiode)</span><span class="sxs-lookup"><span data-stu-id="1bf79-152">In Grace period</span></span>

    -   <span data-ttu-id="1bf79-153">Unbekannt</span><span class="sxs-lookup"><span data-stu-id="1bf79-153">Unknown</span></span>

    -   <span data-ttu-id="1bf79-154">Fehler</span><span class="sxs-lookup"><span data-stu-id="1bf79-154">Error</span></span>

<span data-ttu-id="1bf79-155">Wenn Sie auf die Schaltfläche **Aktualisieren** klicken, wird das Flyout geschlossen, und die Ergebnisse werden gemäß den ausgewählten Filterkriterien aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="1bf79-155">If clicking the **Update button**, the fly out should close and the results should update as per the selected filter criteria.</span></span>

##### <a name="device-details"></a><span data-ttu-id="1bf79-156">Gerätedetails</span><span class="sxs-lookup"><span data-stu-id="1bf79-156">Device details</span></span>

<span data-ttu-id="1bf79-157">Wenn Sie auf ein Gerät klicken, wird das Blatt **„Geräte“** geöffnet und das Gerät ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="1bf79-157">Clicking on a device, opens the **Devices Blade** with the device selected.</span></span> <span data-ttu-id="1bf79-158">Hier finden Sie weitere Details zur angewendeten Einstellung der Gerätekompatibilitätsrichtlinie für das Gerät.</span><span class="sxs-lookup"><span data-stu-id="1bf79-158">This provides more details on the device compliance policy setting applied for that device.</span></span>

![Gerätekompatibilitätsdashboard](./media/idc-6.png)

<span data-ttu-id="1bf79-160">Wenn Sie auf die eigentliche Geräterichtlinieneinstellung klicken, sehen Sie den Namen der Gerätekompatibilitätsrichtlinie, aus der die vom Administrator festgelegte Gerätekompatibilitätseinstellung stammt.</span><span class="sxs-lookup"><span data-stu-id="1bf79-160">When you click on the device policy setting itself, you can see the device compliance policy name originated that device compliance setting targeted by the admin.</span></span>

![Name der Gerätekompatibilitätseinstellung](./media/idc-7.png)

### <a name="per-policy-device-compliance-report"></a><span data-ttu-id="1bf79-162">Richtlinienspezifischer Gerätekompatibilitätsbericht</span><span class="sxs-lookup"><span data-stu-id="1bf79-162">Per-policy device compliance report</span></span>

<span data-ttu-id="1bf79-163">Dieser Bericht bietet eine richtlinienspezifische Kompatibilitätsansicht und gibt Aufschluss über die Gesamtanzahl von Geräten mit den jeweiligen Kompatibilitätsstatuswerten.</span><span class="sxs-lookup"><span data-stu-id="1bf79-163">This report provides you per compliance policy view and the total number of devices in each compliance state.</span></span> <span data-ttu-id="1bf79-164">Die Kachel für die **Richtlinienkompatibilität** steht im **Gerätekompatibilitätsdashboard** zur Verfügung und zeigt neben allen vom Administrator erstellten Richtlinien die Plattformen, für die die Richtlinie angewendet wird, sowie die Anzahl kompatibler und nicht kompatibler Geräte an.</span><span class="sxs-lookup"><span data-stu-id="1bf79-164">The **Policy compliance** title is available from the **Device compliance dashboard**, and it shows all policies previously created by the admin, the platforms the policy is applied, number of compliant devices and number of non-compliant devices.</span></span>

![Richtlinienspezifischer Gerätekompatibilitätsbericht](./media/idc-8.png)

<span data-ttu-id="1bf79-166">Wenn Sie auf die Kachel für die Richtlinienkompatibilität und anschließend auf eine der Gerätekompatibilitätsrichtlinien klicken, erhalten Sie für jedes Gerät, für das diese Gerätekompatibilitätsrichtlinie gilt, Informationen zum **Kompatibilitätsstatus**, **E-Mail-Alias des Benutzers**, **Gerätemodell** und **Standort**.</span><span class="sxs-lookup"><span data-stu-id="1bf79-166">When you click on the Policy compliance tile, then click on one of the device compliance policies, you’ll be able to see the **compliance status**, **user’s email alias**, **device model**, and **location** for each device that was targeted by that device compliance policy.</span></span>

![Kachel für die Richtlinienkompatibilität](./media/idc-9.png)

### <a name="per-setting-device-compliance-report"></a><span data-ttu-id="1bf79-168">Einstellungsspezifischer Gerätekompatibilitätsbericht</span><span class="sxs-lookup"><span data-stu-id="1bf79-168">Per-setting device compliance report</span></span>

<span data-ttu-id="1bf79-169">In diesem Bericht können Sie sich auf der Grundlage der Kompatibilitätseinstellung über die Gesamtanzahl von Geräten mit den jeweiligen Kompatibilitätsstatuswerten informieren.</span><span class="sxs-lookup"><span data-stu-id="1bf79-169">This report allows you to view, per compliance setting, the total number of devices in each compliance state.</span></span> <span data-ttu-id="1bf79-170">Die Kachel für die **Einstellungskompatibilität** steht im **Gerätekompatibilitätsdashboard** zur Verfügung und zeigt neben allen Gerätekompatibilitätsrichtlinien-Einstellungen aller vom Administrator erstellten Gerätekompatibilitätsrichtlinien die Plattformen, für die die Richtlinieneinstellungen angewendet wurden, sowie die Anzahl nicht kompatibler Geräte an.</span><span class="sxs-lookup"><span data-stu-id="1bf79-170">The **Settings compliance** title is available from the **Device compliance dashboard**, and it shows all device compliance policy settings from all device compliance policies created by the admin, the platforms which the policy settings were applied, and the number of non-compliant devices.</span></span>

![Einstellungsspezifischer Gerätekompatibilitätsbericht](./media/idc-10.png)

<span data-ttu-id="1bf79-172">Wenn Sie auf die Kachel für die Einstellungskompatibilität und anschließend auf eine der Gerätekompatibilitätsrichtlinien-Einstellungen klicken, erhalten Sie für jedes Gerät, für das diese Gerätekompatibilitätsrichtlinien-Einstellung gilt, Informationen zum **Kompatibilitätsstatus**, **E-Mail-Alias des Benutzers**, **Gerätemodell** und **Standort**.</span><span class="sxs-lookup"><span data-stu-id="1bf79-172">When you click on the Setting compliance tile, then click on one of the device compliance policy settings, you’ll be able to see the **compliance status**, **user’s email alias**, **device model**, and **location** for each device that was targeted by that device compliance policy setting.</span></span>

![Kachel für die Einstellungskompatibilität](./media/idc-11.png)
