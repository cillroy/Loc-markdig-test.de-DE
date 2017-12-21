---
title: "Hinzufügen von App-Konfigurationsrichtlinien für verwaltete Android-Geräte | Microsoft-Dokumentation"
titlesuffix: Azure portal
description: "Erfahren Sie, wie Sie App-Konfigurationsrichtlinien zum Bereitstellen von Konfigurationsdaten für eine Android for Work-App beim Ausführen verwenden."
keywords: 
author: erikre
ms.author: erikre
manager: angrobe
ms.date: 10/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: d0b6f3fe-2bd4-4518-a6fe-b9fd115ed5e0
ms.reviewer: chrisbal
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: c936c6e0c23afa374c1de73d83e69a4e014d60e5
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2017
---
# <a name="add-app-configuration-policies-for-managed-android-devices"></a><span data-ttu-id="0703e-103">Hinzufügen von App-Konfigurationsrichtlinien für verwaltete Android-Geräte</span><span class="sxs-lookup"><span data-stu-id="0703e-103">Add app configuration policies for managed Android devices</span></span>

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="0703e-104">Verwenden Sie App-Konfigurationsrichtlinien in Microsoft Intune, um Einstellungen anzugeben, wenn Benutzer eine Android for Work-App ausführen.</span><span class="sxs-lookup"><span data-stu-id="0703e-104">Use app configuration policies in Microsoft Intune to supply settings when users run an Android for Work app.</span></span> <span data-ttu-id="0703e-105">Sie weisen diese Richtlinien nicht direkt Benutzern und Geräten zu.</span><span class="sxs-lookup"><span data-stu-id="0703e-105">You do not assign these policies directly to users and devices.</span></span> <span data-ttu-id="0703e-106">Stattdessen verknüpfen Sie eine Richtlinie mit einer App und weisen dann die App zu.</span><span class="sxs-lookup"><span data-stu-id="0703e-106">Instead, you associate a policy with an app, and then assign the app.</span></span> <span data-ttu-id="0703e-107">Die Richtlinieneinstellungen werden verwendet, wenn die App danach sucht (in der Regel beim ersten Ausführen).</span><span class="sxs-lookup"><span data-stu-id="0703e-107">The policy settings are used when the app checks for them, typically the first time it is run.</span></span>

> [!Note]  
> <span data-ttu-id="0703e-108">Nicht jede App unterstützt App-Konfigurationen.</span><span class="sxs-lookup"><span data-stu-id="0703e-108">Not every app supports app configuration.</span></span> <span data-ttu-id="0703e-109">Fragen Sie den App-Entwickler, um herauszufinden, ob er die App so erstellt hat, dass App-Konfigurationsrichtlinien unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="0703e-109">Check with the app developer to see whether they have built their app to support app configuration policies.</span></span>

1. <span data-ttu-id="0703e-110">Melden Sie sich im Azure-Portal an.</span><span class="sxs-lookup"><span data-stu-id="0703e-110">Sign in to the Azure portal.</span></span>
2. <span data-ttu-id="0703e-111">Wählen Sie **Weitere Dienste** > **Überwachung und Verwaltung** + **Intune** aus.</span><span class="sxs-lookup"><span data-stu-id="0703e-111">Choose **More Services** > **Monitoring + Management** + **Intune**.</span></span>
3. <span data-ttu-id="0703e-112">Wählen Sie die Workload **Mobile Apps** aus.</span><span class="sxs-lookup"><span data-stu-id="0703e-112">Choose the **Mobile apps** workload.</span></span>
4. <span data-ttu-id="0703e-113">Wählen Sie in der Gruppe **Verwalten** **App-Konfigurationsrichtlinien** und dann **Hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="0703e-113">Choose **App configuration policies** in the **Manage** group, and then choose **Add**.</span></span>
5. <span data-ttu-id="0703e-114">Legen Sie die folgenden Details fest:</span><span class="sxs-lookup"><span data-stu-id="0703e-114">Set the following details:</span></span>
    - <span data-ttu-id="0703e-115">**Name**</span><span class="sxs-lookup"><span data-stu-id="0703e-115">**Name**</span></span>  
      <span data-ttu-id="0703e-116">Der Name des Profils, das im Azure-Portal angezeigt wird</span><span class="sxs-lookup"><span data-stu-id="0703e-116">The name of the profile that will appear in the Azure portal.</span></span>
    - <span data-ttu-id="0703e-117">**Beschreibung**</span><span class="sxs-lookup"><span data-stu-id="0703e-117">**Description**</span></span>  
      <span data-ttu-id="0703e-118">Die Beschreibung des Profils, das im Azure-Portal angezeigt wird</span><span class="sxs-lookup"><span data-stu-id="0703e-118">The  description of the profile that will appear in the Azure portal.</span></span>
    - <span data-ttu-id="0703e-119">**Geräteregistrierungstyp**</span><span class="sxs-lookup"><span data-stu-id="0703e-119">**Device enrollment type**</span></span>  
      <span data-ttu-id="0703e-120">Klicken Sie auf **Verwaltete Geräte**.</span><span class="sxs-lookup"><span data-stu-id="0703e-120">Choose **Managed devices**.</span></span>
6. <span data-ttu-id="0703e-121">Wählen Sie **Android** als **Plattform** aus.</span><span class="sxs-lookup"><span data-stu-id="0703e-121">Select **Android** for **Platform**.</span></span>
7. <span data-ttu-id="0703e-122">Wählen Sie **Zugeordnete App** aus, um die App auszuwählen, für die Sie eine App-Konfigurationsrichtlinie definieren möchten.</span><span class="sxs-lookup"><span data-stu-id="0703e-122">Select **Associated App** to choose the app for which you want to define an  app configuration policy.</span></span> <span data-ttu-id="0703e-123">Wählen Sie aus der Liste von Android for Work-Apps aus, die Sie genehmigt und mit Intune synchronisiert haben.</span><span class="sxs-lookup"><span data-stu-id="0703e-123">Select from the list of Android for Work apps that you have approved and synchronized with Intune.</span></span>
8. <span data-ttu-id="0703e-124">Wählen Sie **Konfigurationseinstellungen** aus.</span><span class="sxs-lookup"><span data-stu-id="0703e-124">Select **Configuration settings**.</span></span> <span data-ttu-id="0703e-125">Sie können Konfigurationen auf diese Weise festlegen:</span><span class="sxs-lookup"><span data-stu-id="0703e-125">You can set configurations by using:</span></span>
    - <span data-ttu-id="0703e-126">im [Konfigurations-Designer](#Use-the-configuration-designer)</span><span class="sxs-lookup"><span data-stu-id="0703e-126">[Configuration designer](#Use-the-configuration-designer)</span></span>
    - <span data-ttu-id="0703e-127">im [JSON-Editor](#Enter-the-JSON-editor)</span><span class="sxs-lookup"><span data-stu-id="0703e-127">[JSON editor](#Enter-the-JSON-editor)</span></span>
9. <span data-ttu-id="0703e-128">Wählen Sie **OK** und dann **Hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="0703e-128">Choose **OK**, and then choose **Add**.</span></span>

## <a name="use-the-configuration-designer"></a><span data-ttu-id="0703e-129">Verwenden des Konfigurations-Designers</span><span class="sxs-lookup"><span data-stu-id="0703e-129">Use the configuration designer</span></span>

<span data-ttu-id="0703e-130">Sie können den Konfigurations-Designer für Apps auf Geräten verwenden, die in Intune registriert sind oder nicht.</span><span class="sxs-lookup"><span data-stu-id="0703e-130">You can use the configuration designer for apps on devices that are enrolled or not enrolled in Intune.</span></span> <span data-ttu-id="0703e-131">Der Designer ermöglicht Ihnen das Konfigurieren bestimmter Konfigurationsschlüssel und -werte.</span><span class="sxs-lookup"><span data-stu-id="0703e-131">The designer lets you configure specific configuration keys and values.</span></span> <span data-ttu-id="0703e-132">Sie müssen ebenfalls den Datentyp für jeden Wert angeben.</span><span class="sxs-lookup"><span data-stu-id="0703e-132">You must also specify the data type for each value.</span></span>

<span data-ttu-id="0703e-133">Legen Sie für jeden Schlüssel und jeden Wert in der Konfiguration Folgendes fest:</span><span class="sxs-lookup"><span data-stu-id="0703e-133">For each key and value in the configuration, set:</span></span>

  - <span data-ttu-id="0703e-134">**Konfigurationsschlüssel**</span><span class="sxs-lookup"><span data-stu-id="0703e-134">**Configuration key**</span></span>  
     <span data-ttu-id="0703e-135">Der Schlüssel, der die bestimmte Einstellungskonfiguration eindeutig identifiziert.</span><span class="sxs-lookup"><span data-stu-id="0703e-135">The key that uniquely identifies the specific setting configuration.</span></span>
  - <span data-ttu-id="0703e-136">**Werttyp**</span><span class="sxs-lookup"><span data-stu-id="0703e-136">**Value type**</span></span>  
    <span data-ttu-id="0703e-137">Der Datentyp des Konfigurationswerts.</span><span class="sxs-lookup"><span data-stu-id="0703e-137">The data type of the configuration value.</span></span> <span data-ttu-id="0703e-138">Zu den Typen gehören Integer, Real, String oder Boolean.</span><span class="sxs-lookup"><span data-stu-id="0703e-138">Types include Integer, Real, String, or Boolean.</span></span>
  - <span data-ttu-id="0703e-139">**Konfigurationswert**</span><span class="sxs-lookup"><span data-stu-id="0703e-139">**Configuration value**</span></span>  
    <span data-ttu-id="0703e-140">Der Wert für die Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="0703e-140">The value for the configuration.</span></span> 

## <a name="enter-the-json-editor"></a><span data-ttu-id="0703e-141">Eingabe mit dem JSON-Editor</span><span class="sxs-lookup"><span data-stu-id="0703e-141">Enter the JSON editor</span></span>

<span data-ttu-id="0703e-142">Einige Konfigurationseinstellungen für Apps (z.B. die mit Bündeltypen) können nicht mit dem Konfigurations-Designer konfiguriert werden.</span><span class="sxs-lookup"><span data-stu-id="0703e-142">Some configuration settings on apps (such as those with Bundle types) cannot be configured with the configuration designer.</span></span> <span data-ttu-id="0703e-143">Sie müssen den JSON-Editor für diese Werte verwenden.</span><span class="sxs-lookup"><span data-stu-id="0703e-143">You need to use the JSON editor for those values.</span></span> <span data-ttu-id="0703e-144">Einstellungen werden Apps automatisch bereitgestellt, wenn die App installiert wird.</span><span class="sxs-lookup"><span data-stu-id="0703e-144">Settings are supplied to apps automatically when the app is installed.</span></span>

1. <span data-ttu-id="0703e-145">Wählen Sie für **Format der Konfigurationseinstellungen** die Option **JSON-Editor aufrufen** aus.</span><span class="sxs-lookup"><span data-stu-id="0703e-145">For **Configuration settings format**, select **Enter JSON editor**.</span></span>
2. <span data-ttu-id="0703e-146">Im Editor können Sie JSON-Werte für Konfigurationseinstellungen definieren.</span><span class="sxs-lookup"><span data-stu-id="0703e-146">In the editor, you can define JSON values for configuration settings.</span></span> <span data-ttu-id="0703e-147">Sie können **JSON-Vorlage herunterladen** auswählen, um eine Beispieldatei herunterzuladen, die Sie dann konfigurieren können.</span><span class="sxs-lookup"><span data-stu-id="0703e-147">You can choose **Download JSON template** to download a sample file that you can then configure.</span></span>
3. <span data-ttu-id="0703e-148">Wählen Sie **OK** und dann **Hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="0703e-148">Choose **OK**, and then choose **Add**.</span></span>

<span data-ttu-id="0703e-149">Die Richtlinie wird erstellt und auf dem Blatt mit der Richtlinienliste angezeigt.</span><span class="sxs-lookup"><span data-stu-id="0703e-149">The policy is created and appears on the policies list blade.</span></span>

<span data-ttu-id="0703e-150">Wenn die zugewiesene App auf einem Gerät gestartet wird, wird sie mit den Einstellungen ausgeführt, die Sie in der App-Konfigurationsrichtlinie konfiguriert haben.</span><span class="sxs-lookup"><span data-stu-id="0703e-150">When the assigned app is run on a device, it runs with the settings that you configured in the app configuration policy.</span></span>

## <a name="preconfigure-the-permissions-grant-state-for-apps"></a><span data-ttu-id="0703e-151">Vorkonfigurieren des Erteilungsstatus von Berechtigungen für Apps</span><span class="sxs-lookup"><span data-stu-id="0703e-151">Preconfigure the permissions grant state for apps</span></span>

<span data-ttu-id="0703e-152">Sie können auch die Berechtigung vorkonfigurieren, dass Apps auf Android-Gerätefeatures zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="0703e-152">You can also preconfigure permission for apps to access Android device features.</span></span> <span data-ttu-id="0703e-153">Standardmäßig fordern Android-Apps, die Geräteberechtigungen erfordern – z.B. Zugriff auf den Standort oder die Gerätekamera –, die Benutzer zum Annehmen oder Ablehnen der Berechtigungen auf.</span><span class="sxs-lookup"><span data-stu-id="0703e-153">By default, Android apps that require device permissions—such as access to location or the device camera—prompt users to accept or deny permissions.</span></span> <span data-ttu-id="0703e-154">Wenn eine App z.B. das Gerätemikrofon verwendet, wird der Benutzer aufgefordert, der App die Berechtigung zur Verwendung des Mikrofons zu erteilen.</span><span class="sxs-lookup"><span data-stu-id="0703e-154">For example, if an app uses the device's microphone, the user is prompted to grant the app permission to use the microphone.</span></span>

1. <span data-ttu-id="0703e-155">Melden Sie sich im Azure-Portal an.</span><span class="sxs-lookup"><span data-stu-id="0703e-155">Sign in to the Azure portal.</span></span>
2. <span data-ttu-id="0703e-156">Wählen Sie **Weitere Dienste** > **Überwachung und Verwaltung** + **Intune** aus.</span><span class="sxs-lookup"><span data-stu-id="0703e-156">Choose **More Services** > **Monitoring + Management** + **Intune**.</span></span>
3. <span data-ttu-id="0703e-157">Wählen Sie **Mobile Apps** aus.</span><span class="sxs-lookup"><span data-stu-id="0703e-157">Choose **Mobile apps**.</span></span> <span data-ttu-id="0703e-158">Wählen Sie unter **Verwalten** die Option **App-Konfigurationsrichtlinien** und dann **Hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="0703e-158">Under **Manage**, choose **App configuration policies**, and then choose **Add**.</span></span>
4. <span data-ttu-id="0703e-159">Legen Sie die folgenden Details fest:</span><span class="sxs-lookup"><span data-stu-id="0703e-159">Set the following details:</span></span>
    - <span data-ttu-id="0703e-160">**Name**.</span><span class="sxs-lookup"><span data-stu-id="0703e-160">**Name**.</span></span> <span data-ttu-id="0703e-161">Der Name des Profils, das im Azure-Portal angezeigt wird</span><span class="sxs-lookup"><span data-stu-id="0703e-161">The name of the profile that will appear in the Azure portal.</span></span>
    - <span data-ttu-id="0703e-162">**Beschreibung**.</span><span class="sxs-lookup"><span data-stu-id="0703e-162">**Description**.</span></span> <span data-ttu-id="0703e-163">Die Beschreibung des Profils, das im Azure-Portal angezeigt wird</span><span class="sxs-lookup"><span data-stu-id="0703e-163">The  description of the profile that will appear in the Azure portal.</span></span>
    - <span data-ttu-id="0703e-164">**Plattform**</span><span class="sxs-lookup"><span data-stu-id="0703e-164">**Platform**.</span></span> <span data-ttu-id="0703e-165">Wählen Sie **Android** aus.</span><span class="sxs-lookup"><span data-stu-id="0703e-165">Select **Android**.</span></span>
    - <span data-ttu-id="0703e-166">**Geräteregistrierungstyp**</span><span class="sxs-lookup"><span data-stu-id="0703e-166">**Device enrollment type**.</span></span> <span data-ttu-id="0703e-167">**Verwaltete Geräte** ist bereits für Sie ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="0703e-167">**Managed devices** is pre-selected for you.</span></span>
5. <span data-ttu-id="0703e-168">Wählen Sie **Zugeordnete App** aus, um die App auszuwählen, für die Sie eine Konfigurationsrichtlinie definieren möchten.</span><span class="sxs-lookup"><span data-stu-id="0703e-168">Select **Associated App** to choose the app for which you want to define a configuration policy.</span></span> <span data-ttu-id="0703e-169">Wählen Sie aus der Liste von Android for Work-Apps aus, die Sie genehmigt und mit Intune synchronisiert haben.</span><span class="sxs-lookup"><span data-stu-id="0703e-169">Select from the list of Android for Work apps that you have approved and synchronized with Intune.</span></span>
6. <span data-ttu-id="0703e-170">Wählen Sie **Berechtigungen** und dann **Hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="0703e-170">Select **Permissions** and then choose **Add**.</span></span>
7. <span data-ttu-id="0703e-171">Wählen Sie aus der Liste der verfügbaren App-Berechtigungen und dann **OK** aus.</span><span class="sxs-lookup"><span data-stu-id="0703e-171">Select from the list of available app permissions and then choose **OK**.</span></span>
8. <span data-ttu-id="0703e-172">Wählen Sie eine Option für jede Berechtigung aus, die mit dieser Richtlinie erteilt werden soll:</span><span class="sxs-lookup"><span data-stu-id="0703e-172">Select an option for each permission to grant with this policy:</span></span>
    - <span data-ttu-id="0703e-173">**Aufforderung**</span><span class="sxs-lookup"><span data-stu-id="0703e-173">**Prompt**.</span></span> <span data-ttu-id="0703e-174">Aufforderung des Benutzers zur Annahme oder Ablehnung</span><span class="sxs-lookup"><span data-stu-id="0703e-174">Prompt the user to accept or deny.</span></span>
    - <span data-ttu-id="0703e-175">**Automatisch gewähren**</span><span class="sxs-lookup"><span data-stu-id="0703e-175">**Auto grant**.</span></span> <span data-ttu-id="0703e-176">Automatische Genehmigung ohne Benachrichtigung des Benutzers</span><span class="sxs-lookup"><span data-stu-id="0703e-176">Automatically approve without notifying the user.</span></span>
    - <span data-ttu-id="0703e-177">**Automatisch verweigern**</span><span class="sxs-lookup"><span data-stu-id="0703e-177">**Auto deny**.</span></span> <span data-ttu-id="0703e-178">Automatische Ablehnung ohne Benachrichtigung des Benutzers</span><span class="sxs-lookup"><span data-stu-id="0703e-178">Automatically deny without notifying the user.</span></span>
9. <span data-ttu-id="0703e-179">Um die App-Konfigurationsrichtlinie zuzuweisen, wählen Sie die App-Konfigurationsrichtlinie, dann **Zuweisung** und anschließend **Gruppen auswählen** aus.</span><span class="sxs-lookup"><span data-stu-id="0703e-179">To assign the app configuration policy, select the app configuration policy, select **Assignment**, and then select **Select groups**.</span></span>
10. <span data-ttu-id="0703e-180">Wählen Sie die zuzuweisenden Benutzergruppen und dann **Auswählen** aus.</span><span class="sxs-lookup"><span data-stu-id="0703e-180">Select the user groups to assign, and then choose **Select**.</span></span>
11. <span data-ttu-id="0703e-181">Wählen Sie **Speichern** aus, um die Richtlinie zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="0703e-181">Choose **Save** to assign the policy.</span></span>

## <a name="next-steps"></a><span data-ttu-id="0703e-182">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="0703e-182">Next steps</span></span>

<span data-ttu-id="0703e-183">Fahren Sie damit fort, die App [zuzuweisen](apps-deploy.md) und zu [überwachen](apps-monitor.md).</span><span class="sxs-lookup"><span data-stu-id="0703e-183">Continue to [assign](apps-deploy.md) and [monitor](apps-monitor.md) the app.</span></span>

