---
title: "So erstellen Sie eine Konformitätsrichtlinie für macOS"
titleSuffix: Azure portal
description: "Erfahren Sie, wie Sie eine Konformitätsrichtlinie für macOS-Geräte erstellen."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 11/17/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 0444183e-f924-4605-96a8-48fdfbc58fd1
ms.reviewer: muhosabe
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 3cf085ff2ee4668ea4c14718719c466bcb982b10
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2017
---
# <a name="create-a-device-compliance-policy-for-macos-devices-with-intune"></a><span data-ttu-id="8eb29-103">Erstellen einer Gerätekonformitätsrichtlinie für macOS-Geräte in Intune</span><span class="sxs-lookup"><span data-stu-id="8eb29-103">Create a device compliance policy for macOS devices with Intune</span></span>


[!INCLUDE[azure_portal](./includes/azure_portal.md)]

## <a name="before-you-begin"></a><span data-ttu-id="8eb29-104">Vorbereitung</span><span class="sxs-lookup"><span data-stu-id="8eb29-104">Before you begin</span></span>

<span data-ttu-id="8eb29-105">Bevor Sie eine Gerätekonformitätsrichtlinie erstellen und zuweisen, überprüfen Sie die Konzepte für die Intune-Gerätekonformitätsrichtlinie.</span><span class="sxs-lookup"><span data-stu-id="8eb29-105">Before creating and assigning a device compliance policy, review the Intune device compliance policy concepts.</span></span>

- <span data-ttu-id="8eb29-106">Weitere Informationen über Gerätekonformitätsrichtlinien finden Sie unter [Erste Schritte bei der Gerätekonformität in Intune](device-compliance.md).</span><span class="sxs-lookup"><span data-stu-id="8eb29-106">To learn more about device compliance policies, see [get started with device compliance policies](device-compliance.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8eb29-107">Sie müssen Gerätekonformitätsrichtlinien für jede Plattform erstellen.</span><span class="sxs-lookup"><span data-stu-id="8eb29-107">You need to create device compliance policies for each platform.</span></span> <span data-ttu-id="8eb29-108">Gerätekonformitätsrichtlinien-Einstellungen für Intune hängen von den Plattformfunktionen ab, die über das MDM-Protokoll bereitgestellte Einstellungen sind.</span><span class="sxs-lookup"><span data-stu-id="8eb29-108">Intune device compliance policy settings depend on platform capabilities which are settings exposed through the MDM protocol.</span></span>

<span data-ttu-id="8eb29-109">In der Tabelle unten wird beschrieben, wie nicht konforme Einstellungen verwaltet werden, wenn eine Konformitätsrichtlinie mit einer Richtlinie für bedingten Zugriff verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="8eb29-109">The table below describes how noncompliant settings are managed when a compliance policy is used with a conditional access policy.</span></span>

-------------------------------


| <span data-ttu-id="8eb29-110">**Richtlinieneinstellung**</span><span class="sxs-lookup"><span data-stu-id="8eb29-110">**Policy setting**</span></span> | <span data-ttu-id="8eb29-111">**macOS 10.11 und höher**</span><span class="sxs-lookup"><span data-stu-id="8eb29-111">**macOS 10.11 and later**</span></span> |
| --- | --- |
| <span data-ttu-id="8eb29-112">**PIN- oder Kennwortkonfiguration**</span><span class="sxs-lookup"><span data-stu-id="8eb29-112">**PIN or password configuration**</span></span> | <span data-ttu-id="8eb29-113">Wiederhergestellt</span><span class="sxs-lookup"><span data-stu-id="8eb29-113">Remediated</span></span> |   
| <span data-ttu-id="8eb29-114">**Geräteverschlüsselung**</span><span class="sxs-lookup"><span data-stu-id="8eb29-114">**Device encryption**</span></span> | <span data-ttu-id="8eb29-115">Wiederhergestellt (durch Festlegen der PIN)</span><span class="sxs-lookup"><span data-stu-id="8eb29-115">Remediated (by setting PIN)</span></span> |
| <span data-ttu-id="8eb29-116">**E-Mail-Profil**</span><span class="sxs-lookup"><span data-stu-id="8eb29-116">**Email profile**</span></span> | <span data-ttu-id="8eb29-117">Isoliert</span><span class="sxs-lookup"><span data-stu-id="8eb29-117">Quarantined</span></span> |
|<span data-ttu-id="8eb29-118">**Minimale Version des Betriebssystems**</span><span class="sxs-lookup"><span data-stu-id="8eb29-118">**Minimum OS version**</span></span> | <span data-ttu-id="8eb29-119">Isoliert</span><span class="sxs-lookup"><span data-stu-id="8eb29-119">Quarantined</span></span> |
| <span data-ttu-id="8eb29-120">**Maximale Version des Betriebssystems**</span><span class="sxs-lookup"><span data-stu-id="8eb29-120">**Maximum OS version**</span></span> | <span data-ttu-id="8eb29-121">Isoliert</span><span class="sxs-lookup"><span data-stu-id="8eb29-121">Quarantined</span></span> |  
| <span data-ttu-id="8eb29-122">**Windows-Integritätsnachweis**</span><span class="sxs-lookup"><span data-stu-id="8eb29-122">**Windows health attestation**</span></span> | <span data-ttu-id="8eb29-123">Nicht verfügbar</span><span class="sxs-lookup"><span data-stu-id="8eb29-123">Not applicable</span></span> |  
----------------------------


<span data-ttu-id="8eb29-124">**Wiederhergestellt** = Das Betriebssystem des Geräts erzwingt die Kompatibilität.</span><span class="sxs-lookup"><span data-stu-id="8eb29-124">**Remediated** = The device operating system enforces compliance.</span></span> <span data-ttu-id="8eb29-125">(Beispiel: Der Benutzer ist gezwungen, eine PIN festzulegen.)</span><span class="sxs-lookup"><span data-stu-id="8eb29-125">(For example, the user is forced to set a PIN.)</span></span>

<span data-ttu-id="8eb29-126">**Isoliert** = Das Betriebssystem des Geräts erzwingt keine Kompatibilität.</span><span class="sxs-lookup"><span data-stu-id="8eb29-126">**Quarantined** = The device operating system does not enforce compliance.</span></span> <span data-ttu-id="8eb29-127">(Beispiel: Android-Geräte zwingen den Benutzer nicht, das Gerät zu verschlüsseln.) Wenn die Geräte nicht kompatibel sind, erfolgen die folgenden Aktionen:</span><span class="sxs-lookup"><span data-stu-id="8eb29-127">(For example, Android devices do not force the user to encrypt the device.) When the devices is not compliant, the following actions take place:</span></span>

- <span data-ttu-id="8eb29-128">Das Gerät wird blockiert, wenn eine Richtlinie für bedingten Zugriff für den Benutzer gilt.</span><span class="sxs-lookup"><span data-stu-id="8eb29-128">The device is blocked if a conditional access policy applies to the user.</span></span>
- <span data-ttu-id="8eb29-129">Das Unternehmensportal benachrichtigt den Benutzer über Kompatibilitätsprobleme.</span><span class="sxs-lookup"><span data-stu-id="8eb29-129">The company portal notifies the user about any compliance problems.</span></span>

## <a name="macos-compliance-policy-settings"></a><span data-ttu-id="8eb29-130">Einstellungen für die MacOS-Konformitätsrichtlinie</span><span class="sxs-lookup"><span data-stu-id="8eb29-130">MacOS compliance policy settings</span></span>

<span data-ttu-id="8eb29-131">Sie haben verschiedene Kategorien mit unterschiedlichen Einstellungen, aus denen Sie wählen können, wenn Sie eine neue Gerätekompatibilität mit Intune erstellen.</span><span class="sxs-lookup"><span data-stu-id="8eb29-131">You have different categories with different settings to choose from when creating a new device compliance with Intune:</span></span>

- <span data-ttu-id="8eb29-132">Geräteintegrität</span><span class="sxs-lookup"><span data-stu-id="8eb29-132">Device Health</span></span>

- <span data-ttu-id="8eb29-133">Geräteeigenschaften</span><span class="sxs-lookup"><span data-stu-id="8eb29-133">Device Properties</span></span>

- <span data-ttu-id="8eb29-134">Systemsicherheit</span><span class="sxs-lookup"><span data-stu-id="8eb29-134">System Security</span></span>

### <a name="device-health"></a><span data-ttu-id="8eb29-135">Geräteintegrität</span><span class="sxs-lookup"><span data-stu-id="8eb29-135">Device Health</span></span>

- <span data-ttu-id="8eb29-136">**Ein Systemintegritätsschutz ist vonnöten**: Legen Sie dies auf **Erforderlich** fest, um zu überprüfen, ob Ihre macOS-Geräte den Systemintegritätsschutz aktiviert haben.</span><span class="sxs-lookup"><span data-stu-id="8eb29-136">**Require a system integrity protection** : Set this to **Require** to check if your macOS devices have system integrity protection enabled.</span></span>

### <a name="device-properties"></a><span data-ttu-id="8eb29-137">Geräteeigenschaften</span><span class="sxs-lookup"><span data-stu-id="8eb29-137">Device properties</span></span>

- <span data-ttu-id="8eb29-138">**Minimale Betriebssystemversion:** Wenn ein Gerät die Anforderungen an die erforderliche Mindestversion des Betriebssystems nicht erfüllt, wird es als nicht konform gemeldet.</span><span class="sxs-lookup"><span data-stu-id="8eb29-138">**Minimum OS version** : When a device does not meet the minimum OS version requirement, it is reported as noncompliant.</span></span> <span data-ttu-id="8eb29-139">Ein Link mit Informationen zum Upgradevorgang wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="8eb29-139">A link with information on how to upgrade appears.</span></span> <span data-ttu-id="8eb29-140">Der Benutzer kann sein Gerät aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="8eb29-140">The user can choose to upgrade their device.</span></span> <span data-ttu-id="8eb29-141">Danach kann er auf Unternehmensressourcen zugreifen.</span><span class="sxs-lookup"><span data-stu-id="8eb29-141">After that, they can access company resources.</span></span>

- <span data-ttu-id="8eb29-142">**Maximale Betriebssystemversion:** Wenn auf einem Gerät eine neuere Betriebssystemversion verwendet wird, als die Regel erlaubt, wird der Zugriff auf Unternehmensressourcen gesperrt, und der Benutzer wird gebeten, sich an den IT-Administrator zu wenden. Mit diesem Gerät kann solange nicht auf Unternehmensressourcen zugegriffen werden, bis die Regel geändert und die betreffende Betriebssystemversion zugelassen wird.</span><span class="sxs-lookup"><span data-stu-id="8eb29-142">**Maximum OS version** : When a device is using an OS version later than the one specified in the rule, access to company resources is blocked and the user is asked to contact their IT admin. Until there is a change in rule to allow the OS version, this device cannot be used to access company resources.</span></span>

### <a name="system-security-settings"></a><span data-ttu-id="8eb29-143">Einstellungen für die Systemsicherheit</span><span class="sxs-lookup"><span data-stu-id="8eb29-143">System security settings</span></span>

#### <a name="password"></a><span data-ttu-id="8eb29-144">Kennwort</span><span class="sxs-lookup"><span data-stu-id="8eb29-144">Password</span></span>

- <span data-ttu-id="8eb29-145">**Kennwort zum Entsperren mobiler Geräte erforderlich:** Legen Sie für diese Einstellung auf **Erforderlich** fest, damit Benutzer ein Kennwort eingeben müssen, um auf ihre Geräte zugreifen zu können.</span><span class="sxs-lookup"><span data-stu-id="8eb29-145">**Require a password to unlock mobile devices** : Set this to **Require** so users need to enter a password before they can access their device.</span></span>

- <span data-ttu-id="8eb29-146">**Einfache Kennwörter:** Legen Sie **Blockieren** fest, damit Benutzer keine einfache Kennwörter wie **1234** oder **1111** erstellen können.</span><span class="sxs-lookup"><span data-stu-id="8eb29-146">**Simple passwords** : Set this to **Block** so user can't create a simple password like **1234** or **1111**.</span></span>

- <span data-ttu-id="8eb29-147">**Minimale Kennwortlänge:** Geben Sie die Mindestanzahl an Ziffern oder Zeichen an, die das Kennwort enthalten muss.</span><span class="sxs-lookup"><span data-stu-id="8eb29-147">**Minimum password length** : Specify the minimum number of digits or characters that the password must have.</span></span>

- <span data-ttu-id="8eb29-148">**Kennworttyp:** Geben Sie an, ob der Benutzer ein **alphanumerisches** oder ein **numerisches** Kennwort erstellen muss.</span><span class="sxs-lookup"><span data-stu-id="8eb29-148">**Password type** : Specify whether the user must create an **Alphanumeric** password or a **Numeric** password.</span></span>

- <span data-ttu-id="8eb29-149">**Anzahl von nicht-alphabetischen Zeichen im Kennwort:** Wenn Sie **Erforderlicher Kennworttyp** auf **Alphanumerisch** festlegen, gibt diese Einstellung die Mindestanzahl von Zeichensätzen an, die das Kennwort enthalten muss.</span><span class="sxs-lookup"><span data-stu-id="8eb29-149">**Number of non-alphanumeric character in password** : If you set **Required password type** to **Alphanumeric** , use this setting to specify the minimum number of character sets that the password must have.</span></span> 

    > [!NOTE]
    > <span data-ttu-id="8eb29-150">Wenn Sie eine höhere Anzahl festlegen, muss der Benutzer ein komplexeres Kennwort erstellen.</span><span class="sxs-lookup"><span data-stu-id="8eb29-150">Setting a higher number will require the user to create a password that is more complex.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="8eb29-151">Bei macOS-Geräten bezieht sich diese Einstellung auf die Anzahl von Sonderzeichen (z.B. **!**</span><span class="sxs-lookup"><span data-stu-id="8eb29-151">For macOS devices, this setting refers to the number of special characters (for example, **!**</span></span> <span data-ttu-id="8eb29-152">, **#**, **&amp;**), die im Kennwort enthalten sein müssen.</span><span class="sxs-lookup"><span data-stu-id="8eb29-152">, **#** , **&amp;** ) that must be included in the password.</span></span>

- <span data-ttu-id="8eb29-153">**Maximale Anzahl von Minuten der Inaktivität vor erneuter Anforderung des Kennworts:** Geben Sie die Leerlaufzeit an, nach der ein Benutzer sein Kennwort erneut eingeben muss.</span><span class="sxs-lookup"><span data-stu-id="8eb29-153">**Maximum minutes of inactivity before password is required** : Specify the idle time before the user must reenter their password.</span></span>

- <span data-ttu-id="8eb29-154">**Kennwortablauf (Tage):** Wählen Sie die Anzahl von Tagen aus (zwischen 1 und 250), bevor das Kennwort abläuft und ein neues erstellt werden muss.</span><span class="sxs-lookup"><span data-stu-id="8eb29-154">**Password expiration (days)**: Select the number of days (between 1 and 250) before the password expires and they must create a new one.</span></span>

- <span data-ttu-id="8eb29-155">**Anzahl der vorherigen Kennwörter zur Verhinderung von Wiederverwendung:**: Geben Sie die Anzahl von vorherigen Kennwörtern an, die nicht erneut verwendet werden dürfen.</span><span class="sxs-lookup"><span data-stu-id="8eb29-155">**Number of previous passwords to prevent reuse** : Specify the number of previously used passwords that cannot be reused.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="8eb29-156">Wenn die Kennwortanforderung auf einem macOS-Gerät geändert wird, werden die Änderungen erst wirksam, bis der Benutzer sein Kennwort ändert.</span><span class="sxs-lookup"><span data-stu-id="8eb29-156">When the password requirement is changed on a macOS device it doesn’t take effect until the next time the user changes their password.</span></span> <span data-ttu-id="8eb29-157">Wenn Sie beispielsweise die Längeneinschränkung des Kennworts auf acht Ziffern festlegen, und das macOS-Gerät derzeit ein Kennwort mit sechs Ziffern besitzt, bleibt das Gerät kompatibel, bis der Benutzer das nächste Mal das Kennwort auf dem Gerät ändert.</span><span class="sxs-lookup"><span data-stu-id="8eb29-157">For example, if you set the password length restriction to eight digits and the macOS device currently has a 6 digits password, the device remains compliant until the next time the user updates their password on the device.</span></span>

## <a name="to-create-a-device-compliance-policy"></a><span data-ttu-id="8eb29-158">So erstellen Sie eine Gerätekompatibilitätsrichtlinie</span><span class="sxs-lookup"><span data-stu-id="8eb29-158">To create a device compliance policy</span></span>

1. <span data-ttu-id="8eb29-159">Melden Sie sich im [Azure-Portal](https://portal.azure.com) mit Ihren Intune-Anmeldeinformationen an.</span><span class="sxs-lookup"><span data-stu-id="8eb29-159">Go to the [Azure portal](https://portal.azure.com), and sign in with your Intune credentials.</span></span>

2. <span data-ttu-id="8eb29-160">Sobald Sie erfolgreich angemeldet sind, wird das **Azure-Dashboard** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="8eb29-160">After you've successfully signed in, you can see the **Azure Dashboard**.</span></span>

3. <span data-ttu-id="8eb29-161">Wählen Sie im linken Menü **Weitere Dienste** aus, und geben Sie in das Filtertextfeld die Zeichenfolge **Intune** ein.</span><span class="sxs-lookup"><span data-stu-id="8eb29-161">Choose **More services** from the left menu, then type **Intune** in the text box filter.</span></span>

4. <span data-ttu-id="8eb29-162">Wählen Sie **Intune** aus. Das **Intune-Dashboard** wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="8eb29-162">Choose **Intune**, you can see the **Intune Dashboard**.</span></span>

5. <span data-ttu-id="8eb29-163">Wählen Sie **Gerätekompatibilität** aus, dann **Richtlinien** unter **Verwaltung**.</span><span class="sxs-lookup"><span data-stu-id="8eb29-163">Choose **Device compliance**, then choose **Policies** under **Manage**.</span></span>

6. <span data-ttu-id="8eb29-164">Wählen Sie **Richtlinie erstellen** aus.</span><span class="sxs-lookup"><span data-stu-id="8eb29-164">Choose **Create Policy**.</span></span>

7. <span data-ttu-id="8eb29-165">Geben Sie einen Namen und eine Beschreibung ein, und wählen Sie die Plattform aus, auf die Sie diese Richtlinie anwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="8eb29-165">Type a name, description and choose the platform that you want this policy to apply to.</span></span>

8. <span data-ttu-id="8eb29-166">Das Blatt **macOS-Konformitätsrichtlinie** wird geöffnet. Wählen Sie die Kategorien der Konformitätsrichtlinieneinstellung **Sicherheit**, **Geräteintegrität** und **Geräteeigenschaften** aus, um Ihre Einstellungen anzugeben.</span><span class="sxs-lookup"><span data-stu-id="8eb29-166">The **macOS compliance policy** blade opens, choose the device compliance setting categories **Security**, **Device health**, and **Device property** to specify your settings.</span></span>

10. <span data-ttu-id="8eb29-167">Sobald Sie mit der Auswahl Ihrer Einstellungen fertig sind, klicken Sie unter jeder Kategorie der Konformitätsrichtlinieneinstellung auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="8eb29-167">Once you are done choosing your settings, choose **OK** under each device compliance setting category.</span></span>

11. <span data-ttu-id="8eb29-168">Wählen Sie **OK** und dann **Erstellen** aus.</span><span class="sxs-lookup"><span data-stu-id="8eb29-168">Choose **OK**, then choose **Create**.</span></span>

## <a name="assign-user-groups"></a><span data-ttu-id="8eb29-169">Zuweisen von Benutzergruppen</span><span class="sxs-lookup"><span data-stu-id="8eb29-169">Assign user groups</span></span>

<span data-ttu-id="8eb29-170">Wählen Sie zum Zuweisen einer Konformitätsrichtlinie zu Benutzern eine Richtlinie aus, die Sie konfiguriert haben.</span><span class="sxs-lookup"><span data-stu-id="8eb29-170">To assign a compliance policy to users, choose a policy that you have configured.</span></span> <span data-ttu-id="8eb29-171">Vorhandene Richtlinien finden Sie auf dem Blatt **Kompatibilitätsrichtlinien**.</span><span class="sxs-lookup"><span data-stu-id="8eb29-171">Existing policies can be found in the **Compliance policies** blade.</span></span>

1. <span data-ttu-id="8eb29-172">Wählen Sie die Gerätekonformitätsrichtlinie aus, die Sie Benutzern zuweisen möchten, und abschließend **Zuweisungen** aus.</span><span class="sxs-lookup"><span data-stu-id="8eb29-172">Choose the device compliance policy you want to assign to users and choose **Assignments**.</span></span> <span data-ttu-id="8eb29-173">Damit öffnen Sie das Blatt, auf dem Sie **Azure Active Directory-Sicherheitsgruppen** auswählen und der Richtlinie zuweisen können.</span><span class="sxs-lookup"><span data-stu-id="8eb29-173">This opens the blade where you can select **Azure Active Directory security groups** and assign them to the policy.</span></span>

2. <span data-ttu-id="8eb29-174">Wählen Sie **Gruppen auswählen** aus, um das Blatt mit den Azure AD-Sicherheitsgruppen zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="8eb29-174">Choose **Select groups** to open the blade that displays the Azure AD security groups.</span></span>

3. <span data-ttu-id="8eb29-175">Wählen Sie **Auswählen** und dann **Speichern** aus, um die Gerätekonformitätsrichtlinie den Azure AD-Sicherheitsgruppen zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="8eb29-175">Choose **Select** then **Save** to assign the device compliance policy to Azure AD security groups.</span></span>

4. <span data-ttu-id="8eb29-176">Sobald Sie mit der Zuweisung der Gerätekonformitätsrichtlinie an Ihre Gruppen fertig sind, können Sie das Blatt **Zuweisungen** schließen.</span><span class="sxs-lookup"><span data-stu-id="8eb29-176">Once you're done assigning the device compliance policy to your groups, you can close the **Assignments** blade.</span></span>

    > [!TIP]
    > <span data-ttu-id="8eb29-177">Standardmäßig überprüfen Geräte alle 8 Stunden die Konformität. Benutzer können diesen Prozess jedoch nicht über die Intune-Unternehmensportal-App erzwingen.</span><span class="sxs-lookup"><span data-stu-id="8eb29-177">By default, devices check for compliance every 8 hours but users can force this process through the Intune company portal app.</span></span>

## <a name="next-steps"></a><span data-ttu-id="8eb29-178">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="8eb29-178">Next steps</span></span>

[<span data-ttu-id="8eb29-179">Überwachen von Intune-Richtlinien zur Gerätekompatibilität</span><span class="sxs-lookup"><span data-stu-id="8eb29-179">How to monitor device compliance policies</span></span>](compliance-policy-monitor.md)
