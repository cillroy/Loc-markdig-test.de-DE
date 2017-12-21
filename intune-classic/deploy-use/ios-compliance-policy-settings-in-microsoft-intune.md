---
title: "Einstellungen für Konformitätsrichtlinien für iOS-Geräte"
description: "Dieses Thema beschreibt die Regeln und Einstellungen, die Sie in einer Kompatibilitätsrichtlinie für iOS-Geräte festlegen können."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 12/15/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4a59d24f-ed58-49b1-b874-b2d4aea3ec76
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: chrisgre
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 5486edbecfcd349ff03b0f72b66e32cb7fc61e2c
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2017
---
# <a name="compliance-policy-settings-for-ios-devices-in-microsoft-intune"></a><span data-ttu-id="4ba29-103">Einstellungen für Kompatibilitätsrichtlinien für iOS-Geräte in Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="4ba29-103">Compliance policy settings for iOS devices in Microsoft Intune</span></span>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="4ba29-104">Die in diesem Thema beschriebenen Richtlinieneinstellungen gelten für Geräte mit iOS 8.0 und höher.</span><span class="sxs-lookup"><span data-stu-id="4ba29-104">The policy settings described in this topic apply to devices running iOS 8.0 and later.</span></span>

<span data-ttu-id="4ba29-105">Wenn Sie Informationen zu anderen Plattformen suchen, wählen Sie eine der folgenden Optionen:</span><span class="sxs-lookup"><span data-stu-id="4ba29-105">If you are looking for information about other platforms, select one of the following:</span></span>
> [!div class="op_single_selector"]
- [<span data-ttu-id="4ba29-106">Einstellungen für Kompatibilitätsrichtlinien für Android-Geräte</span><span class="sxs-lookup"><span data-stu-id="4ba29-106">Compliance policy settings for Android devices</span></span>](android-compliance-policy-settings-in-microsoft-intune.md)
- [<span data-ttu-id="4ba29-107">Einstellungen für Kompatibilitätsrichtlinien für Android for Work</span><span class="sxs-lookup"><span data-stu-id="4ba29-107">Compliance policy settings for Android for work</span></span>](afw-compliance-policy-settings-in-microsoft-intune.md)
- [<span data-ttu-id="4ba29-108">Einstellungen für Kompatibilitätsrichtlinien für Windows-Geräte</span><span class="sxs-lookup"><span data-stu-id="4ba29-108">Compliance policy settings for Windows devices</span></span>](windows-compliance-policy-settings-in-microsoft-intune.md)

## <a name="system-security-settings"></a><span data-ttu-id="4ba29-109">Einstellungen für die Systemsicherheit</span><span class="sxs-lookup"><span data-stu-id="4ba29-109">System security settings</span></span>
### <a name="password"></a><span data-ttu-id="4ba29-110">Kennwort</span><span class="sxs-lookup"><span data-stu-id="4ba29-110">Password</span></span>
- <span data-ttu-id="4ba29-111">**Kennwort zum Entsperren mobiler Geräte erforderlich**: Legen Sie für diese Einstellung **Ja** fest, damit Benutzer ein Kennwort eingeben müssen, um auf ihre Geräte zugreifen zu können.</span><span class="sxs-lookup"><span data-stu-id="4ba29-111">**Require a password to unlock mobile devices**: Set this to **Yes** to require the user to enter a password before they can access their device.</span></span> <span data-ttu-id="4ba29-112">iOS-Geräte mit Kennwort sind verschlüsselt.</span><span class="sxs-lookup"><span data-stu-id="4ba29-112">iOS devices that use a password are encrypted.</span></span>

- <span data-ttu-id="4ba29-113">**Einfache Kennwörter zulassen**: Legen Sie für diese Einstellung **Ja** fest, damit Benutzer einfache Kennwörter wie **1234** oder **1111** erstellen können.</span><span class="sxs-lookup"><span data-stu-id="4ba29-113">**Allow simple passwords**: Set this to **Yes** to let the user create a simple password like **1234** or **1111**.</span></span>

-  <span data-ttu-id="4ba29-114">**Minimale Kennwortlänge:** Geben Sie die Mindestanzahl an Ziffern oder Zeichen an, die das Benutzerkennwort enthalten muss.</span><span class="sxs-lookup"><span data-stu-id="4ba29-114">**Minimum password length**: Specify the minimum number of digits or characters that the user’s password must have.</span></span>

- <span data-ttu-id="4ba29-115">**Erforderlicher Kennworttyp**: Geben Sie an, ob der Benutzer ein **alphanumerisches** oder ein **numerisches** Kennwort erstellen muss.</span><span class="sxs-lookup"><span data-stu-id="4ba29-115">**Required password type**: Specify whether the user must create an **Alphanumeric** password or a **Numeric** password.</span></span>

- <span data-ttu-id="4ba29-116">**Minimale Anzahl von Zeichensätzen**: Wenn **Erforderlicher Kennworttyp** auf **Alphanumerisch** festgelegt ist, gibt diese Einstellung die Mindestanzahl von Zeichensätzen an, die das Kennwort enthalten muss.</span><span class="sxs-lookup"><span data-stu-id="4ba29-116">**Minimum number of character sets**: If you set **Required password type** to **Alphanumeric**, use this setting to specify the minimum number of character sets that the password must have.</span></span> <span data-ttu-id="4ba29-117">Es gibt vier Zeichensätze:</span><span class="sxs-lookup"><span data-stu-id="4ba29-117">The four character sets are:</span></span>
  -   <span data-ttu-id="4ba29-118">Kleinbuchstaben</span><span class="sxs-lookup"><span data-stu-id="4ba29-118">Lowercase letters</span></span>
  -   <span data-ttu-id="4ba29-119">Großbuchstaben</span><span class="sxs-lookup"><span data-stu-id="4ba29-119">Uppercase letters</span></span>
  -   <span data-ttu-id="4ba29-120">Symbole</span><span class="sxs-lookup"><span data-stu-id="4ba29-120">Symbols</span></span>
  -   <span data-ttu-id="4ba29-121">Zahlen</span><span class="sxs-lookup"><span data-stu-id="4ba29-121">Numbers</span></span>

  <span data-ttu-id="4ba29-122">Wenn Sie eine höhere Anzahl festlegen, muss der Benutzer ein komplexeres Kennwort erstellen.</span><span class="sxs-lookup"><span data-stu-id="4ba29-122">Setting a higher number will require the user to create a password that is more complex.</span></span>

  <span data-ttu-id="4ba29-123">Bei iOS-Geräten bezieht sich diese Einstellung auf die Anzahl von Sonderzeichen (z. B. **!**, **#**, **&amp;**), die im Kennwort enthalten sein müssen.</span><span class="sxs-lookup"><span data-stu-id="4ba29-123">For iOS devices, this setting refers to the number of special characters (for example, **!**, **#**, **&amp;**) that must be included in the password.</span></span>

- <span data-ttu-id="4ba29-124">**Minuten Inaktivität vor erneuter Anforderung des Kennworts**: Geben Sie die Leerlaufzeit an, nach der ein Benutzer sein Kennwort erneut eingeben muss.</span><span class="sxs-lookup"><span data-stu-id="4ba29-124">**Minutes of inactivity before password is required**:  Specify the idle time before the user must reenter their password.</span></span>

- <span data-ttu-id="4ba29-125">**Kennwortablauf (Tage):** Wählen Sie die Anzahl von Tagen aus, bevor das Kennwort des Benutzers abläuft und er ein neues erstellen muss.</span><span class="sxs-lookup"><span data-stu-id="4ba29-125">**Password expiration (days)**: Select the number of days before the user’s password expires and they must create a new one.</span></span>

- <span data-ttu-id="4ba29-126">**Kennwortverlauf speichern**: Verwenden Sie diese Einstellung in Verbindung mit **Wiederverwendung vorheriger Kennwörter verhindern**, um zu verhindern, dass der Benutzer zuvor bereits verwendete Kennwörter erstellt.</span><span class="sxs-lookup"><span data-stu-id="4ba29-126">**Remember password history**: Use this setting in conjunction with **Prevent reuse of previous passwords** to restrict the user from creating previously used passwords.</span></span>

- <span data-ttu-id="4ba29-127">**Wiederverwendung vorheriger Kennwörter verhindern:** Wenn Sie **Kennwortverlauf speichern** aktiviert haben, geben Sie die Anzahl der zuvor verwendeten Kennwörter ein, die nicht erneut verwendet werden dürfen.</span><span class="sxs-lookup"><span data-stu-id="4ba29-127">**Prevent reuse of previous passwords**: If you selected **Remember password history**, specify the number of previously used passwords that cannot be reused.</span></span>

- <span data-ttu-id="4ba29-128">**Kennworteingabe verlangen, wenn das Gerät aus dem Leerlauf zurückkehrt**: Verwenden Sie diese Einstellung zusammen mit der Einstellung **Minuten Inaktivität vor erneuter Anforderung des Kennworts**.</span><span class="sxs-lookup"><span data-stu-id="4ba29-128">**Require a password when the device returns from an idle state**: Use this setting together with the in the **Minutes of inactivity before password is required** setting.</span></span> <span data-ttu-id="4ba29-129">Der Benutzer wird zur Eingabe eines Kennworts aufgefordert, um auf ein Gerät zugreifen zu können, das für die in der Einstellung **Minuten Inaktivität vor erneuter Anforderung des Kennworts** angegebene Zeit inaktiv war.</span><span class="sxs-lookup"><span data-stu-id="4ba29-129">The user is prompted to enter a password to access a device that has been inactive for the time specified in the **Minutes of inactivity before password is required** setting.</span></span>

### <a name="email-profile"></a><span data-ttu-id="4ba29-130">E-Mail-Profil</span><span class="sxs-lookup"><span data-stu-id="4ba29-130">Email profile</span></span>
- <span data-ttu-id="4ba29-131">**E-Mail-Konto muss von Intune verwaltet werden**: Wenn diese Option auf **Ja** festgelegt ist, muss das Gerät das auf dem Gerät bereitgestellte E-Mail-Profil verwenden.</span><span class="sxs-lookup"><span data-stu-id="4ba29-131">**Email account must be managed by Intune**: When this option is set to **Yes**, the device must use the email profile deployed to the device.</span></span> <span data-ttu-id="4ba29-132">Das Gerät wird in den folgenden Situationen als nicht kompatibel betrachtet:</span><span class="sxs-lookup"><span data-stu-id="4ba29-132">The device is considered noncompliant in the following situations:</span></span>
  - <span data-ttu-id="4ba29-133">Das E-Mail-Profil wird für eine andere Benutzergruppe bereitgestellt als die Benutzergruppe, auf die die Kompatibilitätsrichtlinie ausgerichtet ist.</span><span class="sxs-lookup"><span data-stu-id="4ba29-133">The email profile is deployed to a user group other than the user group that the compliance policy targets.</span></span>
  - <span data-ttu-id="4ba29-134">Der Benutzer hat bereits ein E-Mail-Konto auf dem Gerät eingerichtet, das dem Intune-E-Mail-Profil entspricht, das auf dem Gerät bereitgestellt wurde.</span><span class="sxs-lookup"><span data-stu-id="4ba29-134">The user has already set up an email account on the device that matches the Intune email profile deployed to the device.</span></span> <span data-ttu-id="4ba29-135">Intune kann das vom Benutzer bereitgestellte Profil nicht überschreiben und daher nicht verwalten.</span><span class="sxs-lookup"><span data-stu-id="4ba29-135">Intune cannot overwrite the user-provisioned profile, and therefore cannot manage it.</span></span> <span data-ttu-id="4ba29-136">Zum Sicherstellen der Kompatibilität muss der Benutzer die vorhandenen E-Mail-Einstellungen entfernen.</span><span class="sxs-lookup"><span data-stu-id="4ba29-136">To ensure compliance, the user must remove the existing email settings.</span></span> <span data-ttu-id="4ba29-137">Anschließend kann Intune das verwaltete E-Mail-Profil installieren.</span><span class="sxs-lookup"><span data-stu-id="4ba29-137">Then, Intune can install the managed email profile.</span></span>

- <span data-ttu-id="4ba29-138">**Wählen Sie das E-Mail-Profil aus, das von Intune verwaltet werden muss**: Wenn die Einstellung **E-Mail-Konto muss von Intune verwaltet werden** aktiviert ist, wählen Sie **Auswählen** aus, um das Intune-E-Mail-Profil anzugeben.</span><span class="sxs-lookup"><span data-stu-id="4ba29-138">**Select the email profile that must be managed by Intune**: If the **Email account must be managed by Intune** setting is selected, choose **Select** to specify the Intune email profile.</span></span> <span data-ttu-id="4ba29-139">Das E-Mail-Profil muss auf dem Gerät vorhanden sein.</span><span class="sxs-lookup"><span data-stu-id="4ba29-139">The email profile must be present on the device.</span></span>

     <span data-ttu-id="4ba29-140">Weitere Informationen zu E-Mail-Profilen finden Sie unter [Konfigurieren des Zugriffs auf Unternehmens-E-Mail mithilfe von E-Mail-Profilen in Microsoft Intune](configure-access-to-corporate-email-using-email-profiles-with-microsoft-intune.md).</span><span class="sxs-lookup"><span data-stu-id="4ba29-140">For details about email profiles, see [Configure access to corporate email using email profiles with Microsoft Intune](configure-access-to-corporate-email-using-email-profiles-with-microsoft-intune.md).</span></span>

## <a name="device-health-settings"></a><span data-ttu-id="4ba29-141">Einstellungen für die Geräteintegrität</span><span class="sxs-lookup"><span data-stu-id="4ba29-141">Device health settings</span></span>

- <span data-ttu-id="4ba29-142">**Gerät darf keinen Jailbreak oder Rootzugriff verwenden**: Wenn Sie diese Einstellung aktivieren, sind Geräte mit Jailbreak nicht kompatibel.</span><span class="sxs-lookup"><span data-stu-id="4ba29-142">**Device must not be jailbroken or rooted**: If you enable this setting, jailbroken devices will not be compliant.</span></span>

##  <a name="device-properties"></a><span data-ttu-id="4ba29-143">Geräteeigenschaften</span><span class="sxs-lookup"><span data-stu-id="4ba29-143">Device properties</span></span>
- <span data-ttu-id="4ba29-144">**Minimal erforderliches Betriebssystem**: Wenn ein Gerät die Anforderungen an die erforderliche Mindestversion des Betriebssystems nicht erfüllt, wird es als nicht kompatibel gemeldet.</span><span class="sxs-lookup"><span data-stu-id="4ba29-144">**Minimum OS required**: When a device does not meet the minimum OS version requirement, it is reported as noncompliant.</span></span>
<span data-ttu-id="4ba29-145">Ein Link mit Informationen zum Upgradevorgang wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="4ba29-145">A link with information on how to upgrade appears.</span></span> <span data-ttu-id="4ba29-146">Der Benutzer kann sein Gerät aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="4ba29-146">The user can choose to upgrade their device.</span></span> <span data-ttu-id="4ba29-147">Danach kann er auf Unternehmensressourcen zugreifen.</span><span class="sxs-lookup"><span data-stu-id="4ba29-147">After that, they can access company resources.</span></span>

- <span data-ttu-id="4ba29-148">**Maximal zulässige Betriebssystemversion:** Wenn auf einem Gerät eine neuere Betriebssystemversion verwendet wird, als die Regel erlaubt, wird der Zugriff auf Unternehmensressourcen gesperrt, und der Benutzer wird gebeten, sich an den IT-Administrator zu wenden. Mit diesem Gerät kann solange nicht auf Unternehmensressourcen zugegriffen werden, bis die Regel geändert und die betreffende Betriebssystemversion zugelassen wird.</span><span class="sxs-lookup"><span data-stu-id="4ba29-148">**Maximum OS version allowed**: When a device is using an OS version later than the one specified in the rule, access to company resources is blocked and the user is asked to contact their IT admin. Until there is a change in rule to allow the OS version, this device cannot be used to access company resources.</span></span>
