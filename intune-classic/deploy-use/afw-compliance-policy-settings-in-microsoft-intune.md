---
title: "Kompatibilitätseinstellungen für Android for Work"
description: "In diesem Thema werden die Gerätekompatibilitätsrichtlinien für Android-Geräte beschrieben, die mit Android for Work kompatibel sind."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 02/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e721c5c7-9678-4f3b-81d4-564da5efd337
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: chrisbal
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 7bfbb14ae632a735a51da3b079af9bbb3ec7ba89
ms.sourcegitcommit: e37e916e2bf14f092d3a767bc90d68c181d739fb
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/03/2018
---
# <a name="compliance-policy-settings-for-android-for-work-devices-in-microsoft-intune"></a><span data-ttu-id="075fe-103">Einstellungen für Kompatibilitätsrichtlinien für Android for Work-Geräte in Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="075fe-103">Compliance policy settings for Android for Work devices in Microsoft Intune</span></span>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="075fe-104">Die in diesem Thema beschriebenen Richtlinieneinstellungen gelten für Android for Work-Geräte.</span><span class="sxs-lookup"><span data-stu-id="075fe-104">The policy settings described in this topic apply to Android for Work devices.</span></span>

<span data-ttu-id="075fe-105">Wenn Sie Informationen zu anderen Plattformen suchen, wählen Sie eine der folgenden Optionen:</span><span class="sxs-lookup"><span data-stu-id="075fe-105">If you are looking for information about other platforms, select one of the following:</span></span>
> [!div class="op_single_selector"]
> - [Einstellungen für Kompatibilitätsrichtlinien für Android](android-compliance-policy-settings-in-microsoft-intune.md)
> - [Einstellungen für Kompatibilitätsrichtlinien für iOS-Geräte](ios-compliance-policy-settings-in-microsoft-intune.md)
> - [Einstellungen für Kompatibilitätsrichtlinien für Windows-Geräte](windows-compliance-policy-settings-in-microsoft-intune.md)

## <a name="system-security-settings"></a><span data-ttu-id="075fe-109">Einstellungen für die Systemsicherheit</span><span class="sxs-lookup"><span data-stu-id="075fe-109">System security settings</span></span>
### <a name="password"></a><span data-ttu-id="075fe-110">Kennwort</span><span class="sxs-lookup"><span data-stu-id="075fe-110">Password</span></span>
- <span data-ttu-id="075fe-111">**Kennwort zum Entsperren mobiler Geräte erforderlich:** Legen Sie für diese Einstellung **Ja** fest, damit Benutzer ein Kennwort eingeben müssen, um auf ihre Geräte zugreifen zu können.</span><span class="sxs-lookup"><span data-stu-id="075fe-111">**Require a password to unlock mobile devices:** Set this to **Yes** to require users to enter a password before they can access their device.</span></span>

-  <span data-ttu-id="075fe-112">**Minimale Kennwortlänge:** Geben Sie die Mindestanzahl an Ziffern oder Zeichen an, die das Benutzerkennwort enthalten muss.</span><span class="sxs-lookup"><span data-stu-id="075fe-112">**Minimum password length:** Specify the minimum number of digits or characters that the user’s password must contain.</span></span>

- <span data-ttu-id="075fe-113">**Kennwortstärke:** Mit dieser Einstellung wird erkannt, ob die angegebenen Kennwortanforderungen auf dem Gerät konfiguriert wurden.</span><span class="sxs-lookup"><span data-stu-id="075fe-113">**Password quality:** This setting detects if the password requirements you specify is configured on the device.</span></span> <span data-ttu-id="075fe-114">Aktivieren Sie diese Einstellung, um festzulegen, dass Benutzer für Android-Geräte bestimmte Kennwortanforderungen konfigurieren müssen.</span><span class="sxs-lookup"><span data-stu-id="075fe-114">Enable this setting to require that users configure certain password requirements for Android devices.</span></span> <span data-ttu-id="075fe-115">Es stehen die folgenden Optionen zur Auswahl:</span><span class="sxs-lookup"><span data-stu-id="075fe-115">Choose from:</span></span>
  -   <span data-ttu-id="075fe-116">**Biometrie auf niedriger Sicherheitsstufe**</span><span class="sxs-lookup"><span data-stu-id="075fe-116">**Low security biometric**</span></span>
  - <span data-ttu-id="075fe-117">**Erforderlich**</span><span class="sxs-lookup"><span data-stu-id="075fe-117">**Required**</span></span>
  -   <span data-ttu-id="075fe-118">**Mindestens numerisch**</span><span class="sxs-lookup"><span data-stu-id="075fe-118">**At least numeric**</span></span>
  -   <span data-ttu-id="075fe-119">**Mindestens alphabetisch**</span><span class="sxs-lookup"><span data-stu-id="075fe-119">**At least alphabetic**</span></span>
  -   <span data-ttu-id="075fe-120">**Mindestens alphanumerisch**</span><span class="sxs-lookup"><span data-stu-id="075fe-120">**At least alphanumeric**</span></span>
  -   <span data-ttu-id="075fe-121">**Alphanumerisch mit Symbolen**</span><span class="sxs-lookup"><span data-stu-id="075fe-121">**Alphanumeric with symbols**</span></span>

- <span data-ttu-id="075fe-122">**Minuten der Inaktivität, bevor ein Kennwort erforderlich ist:** Gibt die Leerlaufzeit an, nach der ein Benutzer sein Kennwort erneut eingeben muss.</span><span class="sxs-lookup"><span data-stu-id="075fe-122">**Minutes of inactivity before password is required:**  Specifies the idle time before the user must re-enter their password.</span></span>

- <span data-ttu-id="075fe-123">**Kennwortablauf (Tage):** Wählen Sie die Anzahl von Tagen, bevor das Kennwort des Benutzers abläuft und er ein neues erstellen muss.</span><span class="sxs-lookup"><span data-stu-id="075fe-123">**Password expiration (days):** Select the number of days before the user’s password expires and they must create a new one.</span></span>

- <span data-ttu-id="075fe-124">**Kennwortverlauf speichern:** Verwenden Sie diese Einstellung in Verbindung mit **Wiederverwendung vorheriger Kennwörter verhindern**, um zu verhindern, dass der Benutzer zuvor bereits verwendete Kennwörter erstellt.</span><span class="sxs-lookup"><span data-stu-id="075fe-124">**Remember password history:** Use this setting in conjunction with **Prevent reuse of previous passwords** to restrict the user from creating previously used passwords.</span></span>

- <span data-ttu-id="075fe-125">**Wiederverwendung vorheriger Kennwörter verhindern:** Wenn **Kennwortverlauf speichern** aktiviert ist, geben Sie die Anzahl der zuvor verwendeten Kennwörter ein, die nicht erneut verwendet werden dürfen.</span><span class="sxs-lookup"><span data-stu-id="075fe-125">**Prevent reuse of previous passwords:** If **Remember password history** is selected, specify the number of previously used passwords that cannot be re-used.</span></span>

- <span data-ttu-id="075fe-126">**Kennworteingabe verlangen, wenn das Gerät aus dem Leerlauf zurückkehrt:** Diese Einstellung sollte zusammen mit der Einstellung **Minuten Inaktivität vor erneuter Anforderung des Kennworts** verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="075fe-126">**Require a password when the device returns from an idle state:** This setting should be used together with the in the **Minutes of inactivity before password is required** setting.</span></span> <span data-ttu-id="075fe-127">Die Endbenutzer werden zur Eingabe eines Kennworts aufgefordert, um auf ein Gerät zugreifen zu können, das für die in der Einstellung **Minuten Inaktivität vor erneuter Anforderung des Kennworts** angegebene Zeit inaktiv war.</span><span class="sxs-lookup"><span data-stu-id="075fe-127">The end-users are prompted to enter a password to access a device that has been inactive for the time specified in the **Minutes of inactivity before password is required** setting.</span></span>

### <a name="encryption"></a><span data-ttu-id="075fe-128">Verschlüsselung</span><span class="sxs-lookup"><span data-stu-id="075fe-128">Encryption</span></span>
- <span data-ttu-id="075fe-129">**Verschlüsselung auf mobilen Geräten erforderlich:** Diese Einstellung muss nicht konfiguriert werden, da Android for Work-Geräte eine Verschlüsselung erzwingen.</span><span class="sxs-lookup"><span data-stu-id="075fe-129">**Require encryption on mobile device:** You don't have to configure this setting since Android for Work devices enforce encryption.</span></span>

## <a name="device-health-and-security-settings"></a><span data-ttu-id="075fe-130">Einstellungen für Geräteintegrität und Sicherheit</span><span class="sxs-lookup"><span data-stu-id="075fe-130">Device health and security settings</span></span>

- <span data-ttu-id="075fe-131">**Gerät darf nicht gehackt und kein Quellgerät sein:** Wenn Sie diese Einstellung aktivieren, werden gehackte Geräte als nicht kompatibel eingestuft.</span><span class="sxs-lookup"><span data-stu-id="075fe-131">**Device must not be jailbroken or rooted:** If you enable this setting, jailbroken devices will be evaluated as noncompliant.</span></span>
- <span data-ttu-id="075fe-132">**Installation von Apps aus unbekannten Quellen muss auf Geräten gesperrt sein:** Diese Einstellung muss nicht konfiguriert werden, da Android for Work-Geräte die Installation von unbekannten Quellen immer einschränken.</span><span class="sxs-lookup"><span data-stu-id="075fe-132">**Require that devices prevent installation of apps from unknown sources:** You do not have to configure this setting as Android for Work devices always restrict installation from unknown sources.</span></span> <span data-ttu-id="075fe-133">.</span><span class="sxs-lookup"><span data-stu-id="075fe-133">.</span></span>  

- <span data-ttu-id="075fe-134">**USB-Debuggen muss deaktiviert sein**: Diese Einstellung muss nicht konfiguriert werden, da USB-Debuggen auf Android for Work-Geräten bereits deaktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="075fe-134">**Require that USB debugging is  disabled**: You do not have to configure this settings as USB debugging is already disabled on Android for Work devices.</span></span>

- <span data-ttu-id="075fe-135">**Niedrigste zulässige Android-Sicherheitspatchebene**: Verwenden Sie diese Einstellung, um eine niedrigste zulässige Android-Patchebene festzulegen.</span><span class="sxs-lookup"><span data-stu-id="075fe-135">**Minimum Android security patch level**: Use this setting to specify the minimum Android patch level.</span></span>  <span data-ttu-id="075fe-136">Geräte, die nicht mindestens diese Patchebene aufweisen, sind nicht kompatibel.</span><span class="sxs-lookup"><span data-stu-id="075fe-136">Devices that are not at least at this patch level will be noncompliant.</span></span> <span data-ttu-id="075fe-137">Das Datum muss im folgenden Format angegeben werden: JJJJ-MM-TT.</span><span class="sxs-lookup"><span data-stu-id="075fe-137">The date must be specified the format: YYYY-MM-DD.</span></span>
- <span data-ttu-id="075fe-138">**Schutz vor Gerätebedrohungen muss aktiviert sein**: Verwenden Sie diese Einstellung, um die Risikobewertung mit der Lösung „Schutz vor Gerätebedrohungen“ als Kompatibilitätsvoraussetzung zu fordern.</span><span class="sxs-lookup"><span data-stu-id="075fe-138">**Require device threat protection to be enabled**: Use this setting to take the risk assessment from the device threat protection solution as a condition for compliance.</span></span> <span data-ttu-id="075fe-139">Wählen Sie aus den folgenden Optionen die maximal zulässige Bedrohungsstufe aus:</span><span class="sxs-lookup"><span data-stu-id="075fe-139">Select the maximum allowed threat level, which is one of the following:</span></span>

  - <span data-ttu-id="075fe-140">**Keine (geschützt)**: Dies ist die sicherste Einstellung.</span><span class="sxs-lookup"><span data-stu-id="075fe-140">**None (secured)** This is the most secure.</span></span> <span data-ttu-id="075fe-141">Dies bedeutet, dass das Gerät keinerlei Bedrohungen unterliegen darf.</span><span class="sxs-lookup"><span data-stu-id="075fe-141">This means that the device cannot have any threats.</span></span> <span data-ttu-id="075fe-142">Wenn auf dem Gerät Bedrohungen jeglicher Stufe erkannt werden, wird es als nicht kompatibel bewertet.</span><span class="sxs-lookup"><span data-stu-id="075fe-142">If the device is detected as having any level of threats, it will be evaluated as non-compliant.</span></span>
  - <span data-ttu-id="075fe-143">**Niedrig**: Das Gerät wird als kompatibel bewertet, wenn nur Bedrohungen niedriger Stufen vorliegen.</span><span class="sxs-lookup"><span data-stu-id="075fe-143">**Low:** Device is evaluated as compliant if only low level threats are present.</span></span> <span data-ttu-id="075fe-144">Durch Bedrohungen höherer Stufen wird das Gerät in einen nicht kompatiblen Status versetzt.</span><span class="sxs-lookup"><span data-stu-id="075fe-144">Anything higher puts the device in a non-compliant status.</span></span>
  - <span data-ttu-id="075fe-145">**Mittel**: Das Gerät wird als kompatibel bewertet, wenn die auf dem Gerät gefundenen Bedrohungen niedriger oder mittlerer Stufe sind.</span><span class="sxs-lookup"><span data-stu-id="075fe-145">**Medium:** Device is evaluated as compliant if the threats that are present on the device are low or medium level.</span></span> <span data-ttu-id="075fe-146">Wenn auf dem Gerät Bedrohungen hoher Stufen erkannt werden, wird es als nicht kompatibel bewertet.</span><span class="sxs-lookup"><span data-stu-id="075fe-146">If the device is detected to have high level threats, it is determined as non-compliant.</span></span>
  - <span data-ttu-id="075fe-147">**Hoch**: Dies ist die unsicherste Einstellung.</span><span class="sxs-lookup"><span data-stu-id="075fe-147">**High:** This is the least secure.</span></span> <span data-ttu-id="075fe-148">Mit dieser Einstellung werden grundsätzlich alle Bedrohungsstufen zugelassen. Sie ist daher wahrscheinlich nur für Berichtszwecke sinnvoll.</span><span class="sxs-lookup"><span data-stu-id="075fe-148">Essentially, this allows all threat levels, and perhaps only useful if you using this solution only for reporting purposes.</span></span>

  <span data-ttu-id="075fe-149">Weitere Informationen finden Sie unter [Erstellen einer Gerätekompatibilitätsrichtlinie](create-lookout-device-compliance-policy.md).</span><span class="sxs-lookup"><span data-stu-id="075fe-149">For more details, see [Create device compliance policy](create-lookout-device-compliance-policy.md).</span></span>

## <a name="device-property-settings"></a><span data-ttu-id="075fe-150">Einstellungen für Geräteeigenschaften</span><span class="sxs-lookup"><span data-stu-id="075fe-150">Device property settings</span></span>
- <span data-ttu-id="075fe-151">**Minimal erforderliches Betriebssystem**: Wenn ein Gerät die Anforderungen an die erforderliche Mindestversion des Betriebssystems nicht erfüllt, wird es als nicht kompatibel gemeldet.</span><span class="sxs-lookup"><span data-stu-id="075fe-151">**Minimum OS required:** When a device does not meet the minimum operating system (OS) version requirement, it is reported as noncompliant.</span></span>
  <span data-ttu-id="075fe-152">Ein Link zur Vorgehensweise zum Upgrade wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="075fe-152">A link with information on how to upgrade is displayed.</span></span> <span data-ttu-id="075fe-153">Die Endbenutzer können ein Upgrade des Geräts durchführen und anschließend auf die Unternehmensressourcen zugreifen.</span><span class="sxs-lookup"><span data-stu-id="075fe-153">The end-user can choose to upgrade their device after which they can access company resources.</span></span>

- <span data-ttu-id="075fe-154">**Maximal zulässige Betriebssystemversion:** Wenn auf einem Gerät eine neuere Betriebssystemversion verwendet wird, als die Regel erlaubt, wird der Zugriff auf Unternehmensressourcen gesperrt, und der Benutzer wird gebeten, sich an den IT-Administrator zu wenden. Mit diesem Gerät kann solange nicht auf Unternehmensressourcen zugegriffen werden, bis die Regel geändert und die betreffende Betriebssystemversion zugelassen wird.</span><span class="sxs-lookup"><span data-stu-id="075fe-154">**Maximum OS version allowed:** When a device is using an operating system (OS) version later than the one specified in the rule, access to company resources is blocked and the user is asked to contact their IT admin. Until there is a change in the rule to allow the operating system version, this device cannot be used to access company resources.</span></span>
