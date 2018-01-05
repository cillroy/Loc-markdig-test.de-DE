---
title: "Festlegen von Registrierungseinschränkungen in Intune"
titlesuffix: Azure portal
description: "Schränken Sie die Registrierung plattformbezogen ein, und legen Sie in Intune einen Grenzwert für die Geräteregistrierung fest. \""
keywords: 
author: ErikjeMS
ms.author: erikje
manager: angrobe
ms.date: 11/29/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 9691982c-1a03-4ac1-b7c5-73087be8c5f2
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: affd792bb8d48710e944f05fa864c7a2485e652e
ms.sourcegitcommit: e37e916e2bf14f092d3a767bc90d68c181d739fb
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/03/2018
---
# <a name="set-enrollment-restrictions"></a><span data-ttu-id="5c648-104">Festlegen von Registrierungseinschränkungen</span><span class="sxs-lookup"><span data-stu-id="5c648-104">Set enrollment restrictions</span></span>

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="5c648-105">Als Intune-Administrator können Sie Registrierungsbeschränkungen erstellen und verwalten, die die Anzahl und Typen von Geräten festlegen, die sich für die Verwaltung mit Intune registrieren können.</span><span class="sxs-lookup"><span data-stu-id="5c648-105">As an Intune administrator, you can create and manage enrollment restrictions which define the number and types of devices that can enroll into management with Intune.</span></span> <span data-ttu-id="5c648-106">Sie können mehrere Beschränkungen definieren und diese verschiedenen Benutzergruppen zuordnen.</span><span class="sxs-lookup"><span data-stu-id="5c648-106">You can create multiple restrictions and apply them to different user groups.</span></span> <span data-ttu-id="5c648-107">Für Ihre verschiedenen Beschränkungen können Sie eine [Prioritätsreihenfolge](#change-enrollment-restriction-priority) festlegen.</span><span class="sxs-lookup"><span data-stu-id="5c648-107">You can set the [priority order](#change-enrollment-restriction-priority) for your different restrictions.</span></span>

>[!NOTE]
><span data-ttu-id="5c648-108">Registrierungseinschränkungen stellen keine Sicherheitsfunktionen dar.</span><span class="sxs-lookup"><span data-stu-id="5c648-108">Enrollment restrictions are not security features.</span></span> <span data-ttu-id="5c648-109">Gefährdete Geräte können falsche Angaben zu ihren Eigenschaften enthalten.</span><span class="sxs-lookup"><span data-stu-id="5c648-109">Compromised devices can misrepresent their character.</span></span> <span data-ttu-id="5c648-110">Diese Einschränkungen sind eine bestmögliche Barriere für nicht böswillige Benutzer.</span><span class="sxs-lookup"><span data-stu-id="5c648-110">These restrictions are a best-effort barrier for non-malicious users.</span></span>

>[!NOTE]
><span data-ttu-id="5c648-111">Die unten aufgeführten Einschränkungen von Gruppen zugewiesenen Registrierungen und Prioritätsfunktionen werden derzeit für den gesamten Intune-Kundenstamm bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="5c648-111">The group-assigned enrollment restriction and priority functionality mentioned below are in the process of being rolled out across the Intune customer base.</span></span> <span data-ttu-id="5c648-112">Bis zur vollständigen Durchführung der Bereitstellung kann es sein, dass Sie noch keinen Zugriff auf Gruppen- und Prioritätsfeatures haben.</span><span class="sxs-lookup"><span data-stu-id="5c648-112">Until this roll out is complete, you might not have access to the group and priority features.</span></span> 

<span data-ttu-id="5c648-113">Sie können u.a. die folgenden spezifischen Registrierungsbeschränkungen festlegen:</span><span class="sxs-lookup"><span data-stu-id="5c648-113">The specific enrollment restrictions that you can create include:</span></span>

- <span data-ttu-id="5c648-114">Maximale Anzahl registrierter Geräte</span><span class="sxs-lookup"><span data-stu-id="5c648-114">Maximum number of enrolled devices</span></span>
- <span data-ttu-id="5c648-115">Geräteplattformen, die registriert werden können:</span><span class="sxs-lookup"><span data-stu-id="5c648-115">Device platforms that can enroll:</span></span>
  - <span data-ttu-id="5c648-116">Android</span><span class="sxs-lookup"><span data-stu-id="5c648-116">Android</span></span>
  - <span data-ttu-id="5c648-117">Android for Work</span><span class="sxs-lookup"><span data-stu-id="5c648-117">Android for Work</span></span>
  - <span data-ttu-id="5c648-118">iOS</span><span class="sxs-lookup"><span data-stu-id="5c648-118">iOS</span></span>
  - <span data-ttu-id="5c648-119">macOS</span><span class="sxs-lookup"><span data-stu-id="5c648-119">macOS</span></span>
  - <span data-ttu-id="5c648-120">Windows</span><span class="sxs-lookup"><span data-stu-id="5c648-120">Windows</span></span>
- <span data-ttu-id="5c648-121">Plattform-Betriebssystemversion für iOS, Android, Android for Work und Windows (es können nur Windows 10-Versionen verwendet werden. Lassen Sie diese Einstellung leer, wenn Windows 8.1 zulässig ist)</span><span class="sxs-lookup"><span data-stu-id="5c648-121">Platform operating system version for iOS, Android, Android for Work, and Windows (only Windows 10 versions may be used, leave this blank if Windows 8.1 is allowed)</span></span>
  - <span data-ttu-id="5c648-122">Mindestversion</span><span class="sxs-lookup"><span data-stu-id="5c648-122">Minimum version</span></span>
  - <span data-ttu-id="5c648-123">Maximalversion</span><span class="sxs-lookup"><span data-stu-id="5c648-123">Maximum version</span></span>
- <span data-ttu-id="5c648-124">Geräte in Privatbesitz einschränken (nur iOS, Android, Android for Work und macOS)</span><span class="sxs-lookup"><span data-stu-id="5c648-124">Restrict personally owned devices (iOS, Android, Android for Work, macOS only)</span></span>

## <a name="default-restrictions"></a><span data-ttu-id="5c648-125">Standardbeschränkungen</span><span class="sxs-lookup"><span data-stu-id="5c648-125">Default restrictions</span></span>

<span data-ttu-id="5c648-126">Auf den Gerätetyp und das Gerätelimit bezogene Registrierungsbeschränkungen werden standardmäßig vorgeschlagen.</span><span class="sxs-lookup"><span data-stu-id="5c648-126">Default restrictions are automatically provided for both device type and device limit enrollment restrictions.</span></span> <span data-ttu-id="5c648-127">Sie können die Optionen für die Standardeinstellungen ändern.</span><span class="sxs-lookup"><span data-stu-id="5c648-127">You can change the options for the defaults.</span></span> <span data-ttu-id="5c648-128">Standardbeschränkungen gelten für alle Benutzer- und benutzerlosen Registrierungen.</span><span class="sxs-lookup"><span data-stu-id="5c648-128">Default restrictions apply to all user and userless enrollments.</span></span> <span data-ttu-id="5c648-129">Sie können diese Standardeinstellungen überschreiben, indem Sie neue Beschränkungen mit höheren Prioritäten definieren.</span><span class="sxs-lookup"><span data-stu-id="5c648-129">You can override these defaults by creating new restrictions with higher priorities.</span></span>

## <a name="create-a-restriction"></a><span data-ttu-id="5c648-130">Definieren einer Beschränkung</span><span class="sxs-lookup"><span data-stu-id="5c648-130">Create a restriction</span></span>

1. <span data-ttu-id="5c648-131">Melden Sie sich beim Azure-Portal an.</span><span class="sxs-lookup"><span data-stu-id="5c648-131">Sign into the Azure portal.</span></span>
2. <span data-ttu-id="5c648-132">Wählen Sie **Weitere Dienste**, suchen Sie nach **Intune**, und wählen Sie dann **Intune**.</span><span class="sxs-lookup"><span data-stu-id="5c648-132">Choose **More Services**, search for **Intune**, and then choose **Intune**.</span></span>
3. <span data-ttu-id="5c648-133">Klicken Sie auf **Geräteregistrierung** > **Registrierungsbeschränkungen**.</span><span class="sxs-lookup"><span data-stu-id="5c648-133">Choose **Device enrollment** > **Enrollment restrictions**.</span></span>
4. <span data-ttu-id="5c648-134">Wählen Sie **Beschränkung erstellen**.</span><span class="sxs-lookup"><span data-stu-id="5c648-134">Choose **Create restriction**.</span></span>
5. <span data-ttu-id="5c648-135">Geben Sie für die Beschränkung einen Namen und eine Beschreibung ein.</span><span class="sxs-lookup"><span data-stu-id="5c648-135">Give the restriction a name and description.</span></span>
6. <span data-ttu-id="5c648-136">Wählen Sie einen **Beschränkungstyp**, und klicken Sie dann auf **Erstellen**.</span><span class="sxs-lookup"><span data-stu-id="5c648-136">Choose a **Restriction type** and then click **Create**.</span></span>
7. <span data-ttu-id="5c648-137">Um Beschränkungen für das Gerätelimit festzulegen, klicken Sie auf **Gerätelimit**, um die maximale Anzahl von Geräten festzulegen, die ein Benutzer registrieren kann.</span><span class="sxs-lookup"><span data-stu-id="5c648-137">For device limit restrictions, click **Device limit** to set the maximum number of devices that a user can enroll.</span></span>
8. <span data-ttu-id="5c648-138">Klicken Sie für Beschränkungen des Gerätetyps auf **Plattformen** und **Plattformkonfigurationen**, um verschiedene Plattformen und Versionen zuzulassen oder zu blockieren.</span><span class="sxs-lookup"><span data-stu-id="5c648-138">For device type restrictions, click **Platforms** and **Platform configurations** to allow or block various platforms and versions.</span></span>
9. <span data-ttu-id="5c648-139">Klicken Sie auf **Zuweisungen** > **+ Gruppen auswählen**.</span><span class="sxs-lookup"><span data-stu-id="5c648-139">Click **Assignments** > **+ Select groups**.</span></span>
10. <span data-ttu-id="5c648-140">Wählen Sie unter **Gruppen** eine oder mehrere Gruppen aus, und klicken Sie dann auf **Auswählen**.</span><span class="sxs-lookup"><span data-stu-id="5c648-140">Under **Select groups**, select one or more groups, and then click **Select**.</span></span> <span data-ttu-id="5c648-141">Die Beschränkung gilt nur für Gruppen, denen sie zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="5c648-141">The restriction only applies to groups to which it is assigned.</span></span> <span data-ttu-id="5c648-142">Wenn Sie nicht mindestens einer Gruppe eine Beschränkung zuweisen, hat sie keine Wirkung.</span><span class="sxs-lookup"><span data-stu-id="5c648-142">If you don't assign a restriction to at least one group, it won't have any effect.</span></span>
11. <span data-ttu-id="5c648-143">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="5c648-143">Click **Save**.</span></span>
12. <span data-ttu-id="5c648-144">Die neue Beschränkung wird mit einer Priorität knapp über dem Standardwert erstellt.</span><span class="sxs-lookup"><span data-stu-id="5c648-144">The new restriction is created with a priority just above the default.</span></span> <span data-ttu-id="5c648-145">Sie können [die Priorität ändern](#change-enrollment-restriction-priority).</span><span class="sxs-lookup"><span data-stu-id="5c648-145">You can [change the priority](#change-enrollment-restriction-priority).</span></span>

## <a name="set-device-type-restrictions"></a><span data-ttu-id="5c648-146">Festlegen von Gerätetypbeschränkungen</span><span class="sxs-lookup"><span data-stu-id="5c648-146">Set device type restrictions</span></span>

<span data-ttu-id="5c648-147">Sie können die Einstellungen für eine Gerätetypbeschränkung ändern, indem Sie diese Schritte ausführen:</span><span class="sxs-lookup"><span data-stu-id="5c648-147">You can change the settings for a device type restriction by following these steps:</span></span>

1. <span data-ttu-id="5c648-148">Melden Sie sich beim Azure-Portal an.</span><span class="sxs-lookup"><span data-stu-id="5c648-148">Sign into the Azure portal.</span></span>
2. <span data-ttu-id="5c648-149">Wählen Sie **Weitere Dienste**, suchen Sie nach **Intune**, und wählen Sie dann **Intune**.</span><span class="sxs-lookup"><span data-stu-id="5c648-149">Choose **More Services**, search for **Intune**, and then choose **Intune**.</span></span>
3. <span data-ttu-id="5c648-150">Klicken Sie auf **Geräteregistrierung** > **Registrierungsbeschränkungen**.</span><span class="sxs-lookup"><span data-stu-id="5c648-150">Choose **Device enrollment** > **Enrollment restrictions**.</span></span>
4. <span data-ttu-id="5c648-151">Wählen Sie unter **Gerätetypbeschränkungen** die Beschränkung, die Sie festlegen möchten.</span><span class="sxs-lookup"><span data-stu-id="5c648-151">Under **Device Type Restrictions**, choose the restriction that you want to set.</span></span>
5. <span data-ttu-id="5c648-152">Wählen Sie unter dem Namen der Beschränkung (**Alle Benutzer** für die Standardbeschränkung) die Option **Plattformen** aus.</span><span class="sxs-lookup"><span data-stu-id="5c648-152">Under the restriction name (**All Users** for the default restriction), select **Platforms**.</span></span> <span data-ttu-id="5c648-153">Wählen Sie für jede aufgeführte Plattform **Zulassen** oder **Blockieren** aus.</span><span class="sxs-lookup"><span data-stu-id="5c648-153">Choose **Allow** or **Block** for each platform listed.</span></span>
6. <span data-ttu-id="5c648-154">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="5c648-154">Click **Save**.</span></span>
7. <span data-ttu-id="5c648-155">Wählen Sie unter dem Namen der Beschränkung (**Alle Benutzer** für die Standardbeschränkung) **Plattformkonfigurationen** und dann die minimale und maximale **Version** für die aufgeführte Plattform aus.</span><span class="sxs-lookup"><span data-stu-id="5c648-155">Under the restriction name (**All Users** for the default restriction), select **Platform Configurations** and select the minimum and maximum **Versions** for the platforms listed.</span></span> <span data-ttu-id="5c648-156">Die folgenden Versionen werden unterstützt:</span><span class="sxs-lookup"><span data-stu-id="5c648-156">Supported versions include:</span></span>
   - <span data-ttu-id="5c648-157">Android und Android for Work unterstützen major.minor.rev.build.</span><span class="sxs-lookup"><span data-stu-id="5c648-157">Android and Android for Work support major.minor.rev.build.</span></span>
   - <span data-ttu-id="5c648-158">iOS unterstützt major.minor.rev.</span><span class="sxs-lookup"><span data-stu-id="5c648-158">iOS supports major.minor.rev.</span></span>
   - <span data-ttu-id="5c648-159">Windows unterstützt major.minor.rev.build nur für Windows 10.</span><span class="sxs-lookup"><span data-stu-id="5c648-159">Windows supports major.minor.rev.build for Windows 10 only.</span></span>
   <span data-ttu-id="5c648-160">Die Betriebssystemversionen gelten nicht für Apple-Geräte, die mit dem Programm zur Geräteregistrierung, dem Apple School Manager oder der App Apple Configurator registriert werden.</span><span class="sxs-lookup"><span data-stu-id="5c648-160">Operating system versions don't apply to Apple devices enrolling with Device Enrollment Program, Apple School Manager, or the Apple Configurator app.</span></span> 
8. <span data-ttu-id="5c648-161">Wählen Sie für jede aufgeführte Plattform **Zulassen** oder **Blockieren** für **Geräte in Privatbesitz** aus.</span><span class="sxs-lookup"><span data-stu-id="5c648-161">Specify whether to **Allow** or **Block** **Personally owned** devices for each platform listed.</span></span>

    ![Screenshot des Arbeitsbereichs „Gerätebeschränkungen“ mit den standardmäßigen Geräteplattformkonfigurationen für die konfigurierten Einstellungen von Geräten in Privatbesitz.](media/device-restrictions-platform-configurations.png)
9. <span data-ttu-id="5c648-163">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="5c648-163">Click **Save**.</span></span>

>[!NOTE]
>- <span data-ttu-id="5c648-164">Wenn Sie die Registrierung privater Android-Geräte blockieren, können private Android for Work-Geräte weiterhin registriert werden.</span><span class="sxs-lookup"><span data-stu-id="5c648-164">If you block personally owned Android devices from enrollment, personally owned Android for Work devices can still enroll.</span></span>
>- <span data-ttu-id="5c648-165">Standardmäßig ändern sich die Android for Work-Geräteeinstellungen gegenüber Ihren Android-Geräteeinstellungen nicht.</span><span class="sxs-lookup"><span data-stu-id="5c648-165">By default, your Android for Work devices settings will be the same as your settings for your Android devices.</span></span> <span data-ttu-id="5c648-166">Dies ändert sich allerdings, nachdem Sie ihre Android for Work-Einstellungen geändert haben.</span><span class="sxs-lookup"><span data-stu-id="5c648-166">However, after you change your Android for Work settings that will no longer be the case.</span></span>
>- <span data-ttu-id="5c648-167">Wenn Sie die private Android for Work-Registrierung blockieren, können sich nur unternehmenseigene Android-Geräte als Android for Work-Geräte registrieren.</span><span class="sxs-lookup"><span data-stu-id="5c648-167">If you block personal Android for Work enrollment, only corporate Android devices can enroll as Android for Work.</span></span>

## <a name="set-device-limit-restrictions"></a><span data-ttu-id="5c648-168">Festlegen von Einschränkungen zum Gerätelimit</span><span class="sxs-lookup"><span data-stu-id="5c648-168">Set device limit restrictions</span></span>

<span data-ttu-id="5c648-169">Sie können die Einstellungen für eine Gerätelimitbeschränkung ändern, indem Sie diese Schritte ausführen:</span><span class="sxs-lookup"><span data-stu-id="5c648-169">You can change the settings for a device limit restriction by following these steps:</span></span>

1. <span data-ttu-id="5c648-170">Melden Sie sich beim Azure-Portal an.</span><span class="sxs-lookup"><span data-stu-id="5c648-170">Sign into the Azure portal.</span></span>
2. <span data-ttu-id="5c648-171">Wählen Sie **Weitere Dienste**, suchen Sie nach **Intune**, und wählen Sie dann **Intune**.</span><span class="sxs-lookup"><span data-stu-id="5c648-171">Choose **More Services**, search for **Intune**, and then choose **Intune**.</span></span>
3. <span data-ttu-id="5c648-172">Klicken Sie auf **Geräteregistrierung** > **Registrierungsbeschränkungen**.</span><span class="sxs-lookup"><span data-stu-id="5c648-172">Choose **Device enrollment** > **Enrollment restrictions**.</span></span>
4. <span data-ttu-id="5c648-173">Wählen Sie unter **Einschränkungen zum Gerätelimit** die Beschränkung, die Sie festlegen möchten.</span><span class="sxs-lookup"><span data-stu-id="5c648-173">Under **Device Limit Restrictions**, choose the restriction that you want to set.</span></span>
5. <span data-ttu-id="5c648-174">Wählen Sie **Gerätelimit** und dann in der Dropdownliste die maximale Anzahl der Geräte aus, die ein Benutzer registrieren kann.</span><span class="sxs-lookup"><span data-stu-id="5c648-174">Choose **Device Limit** and then, in the drop-down list, select the maximum number of devices a user can enroll.</span></span>
    <span data-ttu-id="5c648-175">![Screenshot des Blatts „Einschränkungen zum Gerätelimit“ mit den Einschränkungen zur Gerätebeschränkung.](./media/device-restrictions-limit.png)</span><span class="sxs-lookup"><span data-stu-id="5c648-175">![Screenshot of the device limit restrictions blade with the device limit restrictions.](./media/device-restrictions-limit.png)</span></span>
6. <span data-ttu-id="5c648-176">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="5c648-176">Click **Save**.</span></span>

## <a name="change-enrollment-restriction-priority"></a><span data-ttu-id="5c648-177">Ändern der Priorität der Registrierungsbeschränkung</span><span class="sxs-lookup"><span data-stu-id="5c648-177">Change enrollment restriction priority</span></span>

<span data-ttu-id="5c648-178">Die Priorität wird verwendet, wenn ein Benutzer in mehreren Gruppen vorhanden ist, denen Beschränkungen zugewiesen sind.</span><span class="sxs-lookup"><span data-stu-id="5c648-178">Priority is used when a user exists in multiple groups that are assigned restrictions.</span></span> <span data-ttu-id="5c648-179">Benutzer unterliegen nur der Beschränkung mit der höchsten Priorität, die einer Gruppe zugewiesen wurde, zu der sie gehören.</span><span class="sxs-lookup"><span data-stu-id="5c648-179">Users are subject only to the highest priority restriction assigned to a group that they are in.</span></span> <span data-ttu-id="5c648-180">Beispiel: Johanna gehört zur Gruppe A, der Beschränkungen der Priorität 5 zugewiesen ist, und zur Gruppe B, der Beschränkungen der Priorität 2 zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="5c648-180">For example, Joe is in a group A assigned to priority 5 restrictions and group B assigned to priority 2 restrictions.</span></span> <span data-ttu-id="5c648-181">Johanna unterliegt also nur Einschränkungen der Priorität 2.</span><span class="sxs-lookup"><span data-stu-id="5c648-181">Joe is only subject to the priority 2 restrictions.</span></span> 

<span data-ttu-id="5c648-182">Wenn Sie eine Beschränkung definieren, wird sie der Liste direkt über dem Standardwert hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="5c648-182">When you create a restriction, it is added to the list just above the default.</span></span>

<span data-ttu-id="5c648-183">Zur Geräteregistrierung gehören Standardbeschränkungen für den Gerätetyp und das Gerätelimit.</span><span class="sxs-lookup"><span data-stu-id="5c648-183">Device enrollment includes default restrictions for both device type and device limit restrictions.</span></span> <span data-ttu-id="5c648-184">Diese beiden Beschränkungen gelten für alle Benutzer, es sei denn, sie werden durch Beschränkungen höherer Priorität außer Kraft gesetzt.</span><span class="sxs-lookup"><span data-stu-id="5c648-184">These two restrictions apply to all users unless they are overridden by higher-priority restrictions.</span></span> 

<span data-ttu-id="5c648-185">Sie können die Priorität jeder nicht standardmäßigen Beschränkung ändern.</span><span class="sxs-lookup"><span data-stu-id="5c648-185">You can change the priority of any non-default restriction.</span></span> 

<span data-ttu-id="5c648-186">**So ändern Sie Priorität einer Beschränkung**</span><span class="sxs-lookup"><span data-stu-id="5c648-186">**To change restriction priority**</span></span>

1. <span data-ttu-id="5c648-187">Melden Sie sich beim Azure-Portal an.</span><span class="sxs-lookup"><span data-stu-id="5c648-187">Sign into the Azure portal.</span></span>
2. <span data-ttu-id="5c648-188">Wählen Sie **Weitere Dienste**, suchen Sie nach **Intune**, und wählen Sie dann **Intune**.</span><span class="sxs-lookup"><span data-stu-id="5c648-188">Choose **More Services**, search for **Intune**, and then choose **Intune**.</span></span>
3. <span data-ttu-id="5c648-189">Klicken Sie auf **Geräteregistrierung** > **Registrierungsbeschränkungen**.</span><span class="sxs-lookup"><span data-stu-id="5c648-189">Choose **Device enrollment** > **Enrollment restrictions**.</span></span>
4. <span data-ttu-id="5c648-190">Zeigen Sie in der Prioritätenliste auf die Beschränkung.</span><span class="sxs-lookup"><span data-stu-id="5c648-190">Hover over the restriction in the priority list.</span></span>
5. <span data-ttu-id="5c648-191">Ziehen Sie mithilfe der drei vertikalen Punkte die Priorität an die gewünschte Position in der Liste.</span><span class="sxs-lookup"><span data-stu-id="5c648-191">Using the three vertical dots, drag the priority to the desired position in the list.</span></span>





