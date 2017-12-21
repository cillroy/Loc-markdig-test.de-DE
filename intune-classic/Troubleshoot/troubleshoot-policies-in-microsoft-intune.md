---
title: Behandlung von Problemen mit Richtlinien
description: Behandeln Sie Richtlinienkonfigurationsprobleme.
keywords: 
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 01/04/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 99fb6db6-21c5-46cd-980d-50f063ab8ab8
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: tscott
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: a8f042496137887be16e13dd9564ebc9ba736389
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2017
---
# <a name="troubleshoot-policies-in-microsoft-intune"></a><span data-ttu-id="c25c0-103">Behandlung von Problemen mit Richtlinien in Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="c25c0-103">Troubleshoot policies in Microsoft Intune</span></span>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="c25c0-104">Wenn beim Bereitstellen und Verwalten von Intune-Richtlinien Probleme auftreten, beginnen Sie hier.</span><span class="sxs-lookup"><span data-stu-id="c25c0-104">If you are having problems deploying and managing Intune policies, start here.</span></span> <span data-ttu-id="c25c0-105">In diesem Thema werden einige allgemeine Probleme, die auftreten können, sowie deren Lösungen behandelt.</span><span class="sxs-lookup"><span data-stu-id="c25c0-105">This topic contains some common problems you might encounter together with solutions.</span></span>

## <a name="general-issues"></a><span data-ttu-id="c25c0-106">Allgemeine Probleme</span><span class="sxs-lookup"><span data-stu-id="c25c0-106">General Issues</span></span>

### <a name="was-a-deployed-policy-applied-to-the-device"></a><span data-ttu-id="c25c0-107">Wurde eine bereitgestellte Richtlinie auf das Gerät angewendet?</span><span class="sxs-lookup"><span data-stu-id="c25c0-107">Was a deployed policy applied to the device?</span></span>
<span data-ttu-id="c25c0-108">**Problem:** Sie sind sich nicht sicher, ob eine Richtlinie ordnungsgemäß angewendet wurde.</span><span class="sxs-lookup"><span data-stu-id="c25c0-108">**Issue:** You are unsure if a policy was correctly applied.</span></span>

<span data-ttu-id="c25c0-109">In der Intune-Verwaltungskonsole verfügt jedes Gerät unter **Geräteeigenschaften**über eine Registerkarte „Richtlinie“.</span><span class="sxs-lookup"><span data-stu-id="c25c0-109">In the Intune admin console every device has a policy tab under **Device Properties**.</span></span> <span data-ttu-id="c25c0-110">Jede Richtlinie verfügt über einen **vorgesehenen Wert** und einen **Status**.</span><span class="sxs-lookup"><span data-stu-id="c25c0-110">Each policy has an **Intended Value** and a **Status**.</span></span> <span data-ttu-id="c25c0-111">Den vorgesehenen Wert möchten Sie durch Zuweisen der Richtlinie erzielen.</span><span class="sxs-lookup"><span data-stu-id="c25c0-111">The intended value is what you meant to achieve when assigning the policy.</span></span> <span data-ttu-id="c25c0-112">Der Status gibt an, was tatsächlich angewendet wurde, wenn alle für das Gerät geltenden Richtlinien sowie die Einschränkungen und Anforderungen der Hardware und des Betriebssystems zusammen betrachtet werden.</span><span class="sxs-lookup"><span data-stu-id="c25c0-112">The status is what is actually applied when all of the policies that apply to the device, as well as the restrictions and requirements of the hardware and the operating system, are considered together.</span></span> <span data-ttu-id="c25c0-113">Mögliche Status sind:</span><span class="sxs-lookup"><span data-stu-id="c25c0-113">Possible statuses are:</span></span>

-   <span data-ttu-id="c25c0-114">**Konform**: Das Gerät hat die Richtlinie empfangen und meldet dem Dienst, dass es der Einstellung entspricht.</span><span class="sxs-lookup"><span data-stu-id="c25c0-114">**Conforms**: the device has received the policy and reports to the service that it  conforms to the setting.</span></span>

-   <span data-ttu-id="c25c0-115">**Nicht zutreffend**: Die Richtlinieneinstellung ist nicht zutreffend.</span><span class="sxs-lookup"><span data-stu-id="c25c0-115">**Not applicable**: The policy setting is not applicable.</span></span> <span data-ttu-id="c25c0-116">Beispielsweise wären E-Mail-Einstellungen für iOS-Geräte nicht auf ein Android-Gerät anwendbar.</span><span class="sxs-lookup"><span data-stu-id="c25c0-116">For example,  email settings for iOS devices would not apply to an Android device.</span></span>

-   <span data-ttu-id="c25c0-117">**Ausstehend**: Die Richtlinie wurde an das Gerät gesendet, hat aber noch keinen Status an den Dienst gemeldet.</span><span class="sxs-lookup"><span data-stu-id="c25c0-117">**Pending**: The policy was sent to the device, but hasn't reported status to the service.</span></span> <span data-ttu-id="c25c0-118">Beispiel: Verschlüsselung unter Android erfordert, dass der Benutzer die Verschlüsselung aktiviert, und sie könnte aus diesem Grund ausstehen.</span><span class="sxs-lookup"><span data-stu-id="c25c0-118">For example, encryption on Android requires the user to enable encryption and might therefore be pending.</span></span>

<span data-ttu-id="c25c0-119">Der folgende Screenshot zeigt zwei eindeutige Beispiele:</span><span class="sxs-lookup"><span data-stu-id="c25c0-119">In the screenshot below you can see two clear examples:</span></span>

-   <span data-ttu-id="c25c0-120">**Einfache Kennwörter zulassen** ist auf **Ja**gesetzt, wie in der Spalte **Beabsichtigter Wert** gezeigt, der **Status** ist jedoch **Nicht zutreffend**.</span><span class="sxs-lookup"><span data-stu-id="c25c0-120">**Allow simple passwords** is set to **Yes**, as shown in the **Intended Value** column, but its **Status** is **Not applicable**.</span></span> <span data-ttu-id="c25c0-121">Dies liegt daran, dass einfache Kennwörter für Android-Geräte nicht unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="c25c0-121">This is because simple passwords are not supported for Android devices.</span></span>

-   <span data-ttu-id="c25c0-122">Ebenso gilt das erweiterte Richtlinienelement **E-Mail-Einstellungen für iOS-Geräte** nicht für dieses Gerät, da es ein Android-Gerät ist.</span><span class="sxs-lookup"><span data-stu-id="c25c0-122">Similarly, the expanded policy item **Email settings for iOS devices** is not applied to this device, as it is an Android device.</span></span>

![Intune-Geräterichtlinie](../media/Intune-Device-Policy-v.2.jpg)

> [!NOTE]
> <span data-ttu-id="c25c0-124">Denken Sie daran: Wenn zwei Richtlinien mit unterschiedlichen Einschränkungsstufen für das gleiche Gerät gelten, wird in der Praxis die restriktivere Richtlinie angewendet.</span><span class="sxs-lookup"><span data-stu-id="c25c0-124">Remember that when two policies with different levels of restriction apply to the same device or user, the more restrictive policy applies in practice.</span></span>


## <a name="issues-with-enrolled-devices"></a><span data-ttu-id="c25c0-125">Probleme mit registrierten Geräten</span><span class="sxs-lookup"><span data-stu-id="c25c0-125">Issues with enrolled devices</span></span>

### <a name="alert-saving-of-access-rules-to-exchange-has-failed"></a><span data-ttu-id="c25c0-126">Warnung: Fehler beim Speichern von Zugriffsregeln in Exchange</span><span class="sxs-lookup"><span data-stu-id="c25c0-126">Alert: Saving of Access Rules to Exchange has Failed</span></span>
<span data-ttu-id="c25c0-127">**Problem**: Sie erhalten die Warnung **Fehler beim Speichern von Zugriffsregeln in Exchange**  in der Verwaltungskonsole.</span><span class="sxs-lookup"><span data-stu-id="c25c0-127">**Issue**: You receive the alert **Saving of Access Rules to Exchange has Failed**  in the admin console.</span></span>

<span data-ttu-id="c25c0-128">Wenn Sie Richtlinien im Exchange-Arbeitsbereich „Lokale Richtlinie“ in der Verwaltungskonsole erstellt haben, aber Office 365 verwenden, werden die konfigurierten Richtlinieneinstellungen von Intune nicht erzwungen.</span><span class="sxs-lookup"><span data-stu-id="c25c0-128">If you  created policies in the Exchange On-Premises Policy workspace under the Admin Console but are using O365, the configured policy settings are not enforced by Intune.</span></span> <span data-ttu-id="c25c0-129">Beachten Sie die Richtlinienquelle in der Warnung.</span><span class="sxs-lookup"><span data-stu-id="c25c0-129">Note the policy source from the alert.</span></span>  <span data-ttu-id="c25c0-130">Löschen Sie im Exchange-Arbeitsbereich „Lokale Richtlinie“ die Legacyregeln, weil diese in Intune globale Exchange-Regeln für lokales Exchange und für Office 365 nicht relevant sind.</span><span class="sxs-lookup"><span data-stu-id="c25c0-130">Under the Exchange On-premises Policy workspace delete the legacy rules, as these are Global Exchange rules within Intune for on-premises Exchange, and are not relevant to O365.</span></span> <span data-ttu-id="c25c0-131">Erstellen Sie dann eine neue Richtlinie für Office 365.</span><span class="sxs-lookup"><span data-stu-id="c25c0-131">Then, create new policy for O365.</span></span>

### <a name="cannot-change-security-policy-for-various-enrolled-devices"></a><span data-ttu-id="c25c0-132">Sicherheitsrichtlinie für verschiedene registrierte Geräte kann nicht geändert werden</span><span class="sxs-lookup"><span data-stu-id="c25c0-132">Cannot change security policy for various enrolled devices</span></span>
<span data-ttu-id="c25c0-133">Windows Phone-Geräte gestatten keine Verringerung der Sicherheitsstufe in Sicherheitsrichtlinien, die mittels MDM oder EAS festgelegt wurden, nachdem diese festgelegt wurden.</span><span class="sxs-lookup"><span data-stu-id="c25c0-133">Windows Phone devices do not allow security policies set via MDM or EAS to be reduced in security once you've set them.</span></span> <span data-ttu-id="c25c0-134">Angenommen, Sie legen ein **Kennwort mit Mindestanzahl von Zeichen** auf 8 fest und versuchen dann, diesen Wert auf 4 zu verringern.</span><span class="sxs-lookup"><span data-stu-id="c25c0-134">For example, you set a **Minimum number of character password** to 8  then try to reduce it to 4.</span></span> <span data-ttu-id="c25c0-135">Die restriktivere Richtlinie wurde bereits auf das Gerät angewendet.</span><span class="sxs-lookup"><span data-stu-id="c25c0-135">The more restrictive policy has already been applied to the device.</span></span>

<span data-ttu-id="c25c0-136">Abhängig von der Geräteplattform müssen Sie, wenn Sie die Richtlinie auf einen niedrigeren Sicherheitswert ändern möchten, Sicherheitsrichtlinien möglicherweise zurücksetzen.</span><span class="sxs-lookup"><span data-stu-id="c25c0-136">Depending on the device platform, if you want to change the policy  to a less secure value you may need to reset security policies.</span></span>
<span data-ttu-id="c25c0-137">In Windows wischen Sie beispielsweise auf dem Desktop von rechts nach innen, um die Leiste **Charms** zu öffnen, und wählen Sie **Einstellungen** &gt; **Systemsteuerung**.</span><span class="sxs-lookup"><span data-stu-id="c25c0-137">For example, in Windows,  on the desktop swipe in from right to open the **Charms** bar and choose  **Settings** &gt; **Control Panel**.</span></span>  <span data-ttu-id="c25c0-138">Wählen Sie das Applet **Benutzerkonten** aus.</span><span class="sxs-lookup"><span data-stu-id="c25c0-138">Select the **User Accounts** applet.</span></span>
<span data-ttu-id="c25c0-139">Im linken Navigationsmenü befindet sich unten ein Link **Sicherheitsrichtlinien zurücksetzen** .</span><span class="sxs-lookup"><span data-stu-id="c25c0-139">In the left hand navigation menu, there is a **Reset Security Policies** link at the bottom.</span></span> <span data-ttu-id="c25c0-140">Klicken Sie darauf, und klicken Sie dann auf die Schaltfläche **Richtlinien zurücksetzen**.</span><span class="sxs-lookup"><span data-stu-id="c25c0-140">Choose it and then choose the **Reset Policies** button.</span></span>
<span data-ttu-id="c25c0-141">Andere MDM-Geräte, wie Android, Windows Phone 8.1 und höher sowie iOS, müssen möglicherweise außer Kraft gesetzt und bei dem Dienst neu registriert werden, damit Sie eine weniger restriktive Richtlinie anwenden können.</span><span class="sxs-lookup"><span data-stu-id="c25c0-141">Other MDM devices, such as Android, Windows Phone 8.1 and later, and iOS, may need to be retired and re-enrolled back into the service for you to be able to apply a less restrictive policy.</span></span>

## <a name="issues-with-pcs-that-run-the-intune-software-client"></a><span data-ttu-id="c25c0-142">Probleme mit PCs mit dem Intune-Softwareclient</span><span class="sxs-lookup"><span data-stu-id="c25c0-142">Issues with PCs that run the Intune software client</span></span>

### <a name="microsoft-intune-policy-related-errors-in-policyplatformlog"></a><span data-ttu-id="c25c0-143">Fehler in „policyplatform.log“ im Zusammenhang mit der Microsoft Intune-Richtlinie</span><span class="sxs-lookup"><span data-stu-id="c25c0-143">Microsoft Intune policy-related errors in policyplatform.log</span></span>
<span data-ttu-id="c25c0-144">Bei Windows-PCs, die mit dem Intune-Softwareclient verwaltet werden, können Richtlinienfehler in der Datei „policyplatform.log“ das Ergebnis nicht standardmäßiger Einstellungen in der Windows-Benutzerkontensteuerung (UAC) auf dem Gerät sein.</span><span class="sxs-lookup"><span data-stu-id="c25c0-144">For Windows PCs managed with the Intune software client, policy errors in the policyplatform.log file may be the result of non-default settings in the Windows User Account Control (UAC) on the device.</span></span> <span data-ttu-id="c25c0-145">Einige nicht standardmäßige UAC-Einstellungen können Microsoft Intune-Clientinstallationen und Richtlinienausführungen beeinträchtigen.</span><span class="sxs-lookup"><span data-stu-id="c25c0-145">Some non-default UAC settings can affect Microsoft Intune client installations and policy execution.</span></span>

#### <a name="to-resolve-uac-issues"></a><span data-ttu-id="c25c0-146">So beheben Sie UAC-Probleme</span><span class="sxs-lookup"><span data-stu-id="c25c0-146">To resolve UAC issues</span></span>

1.  <span data-ttu-id="c25c0-147">Koppeln Sie den Computer ab, wie unter [Retire devices from Microsoft Intune management](/intune-classic/deploy-use/retire-devices-from-microsoft-intune-management) (Abkoppeln von Geräten in der Microsoft Intune-Verwaltung) beschrieben.</span><span class="sxs-lookup"><span data-stu-id="c25c0-147">Retire the computer, as described in [Retire devices from Microsoft Intune management](/intune-classic/deploy-use/retire-devices-from-microsoft-intune-management).</span></span>

2.  <span data-ttu-id="c25c0-148">Warten Sie 20 Minuten, bis die Clientsoftware entfernt wurde.</span><span class="sxs-lookup"><span data-stu-id="c25c0-148">Wait 20 minutes for the client software to be removed.</span></span>

    > [!NOTE]
    > <span data-ttu-id="c25c0-149">Versuchen Sie nicht, den Client über „Programme und Funktionen“ zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="c25c0-149">Do not attempt to remove the client from Programs and Features.</span></span>

3.  <span data-ttu-id="c25c0-150">Geben Sie im Startmenü **UAC** ein, um die Einstellungen der Benutzerkontensteuerung zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="c25c0-150">On the start menu type **UAC** to open the User Account Control settings.</span></span>

4.  <span data-ttu-id="c25c0-151">Verschieben Sie den Schieberegler für Benachrichtigungen auf die Standardeinstellung.</span><span class="sxs-lookup"><span data-stu-id="c25c0-151">Move  the notification slider to the default setting.</span></span>

### <a name="error-cannot-obtain-the-value-from-the-computer-0x80041013"></a><span data-ttu-id="c25c0-152">FEHLER: Der Wert kann nicht vom Computer abgerufen werden, 0x80041013</span><span class="sxs-lookup"><span data-stu-id="c25c0-152">ERROR: Cannot obtain the value from the computer, 0x80041013</span></span>
<span data-ttu-id="c25c0-153">Dieser Fehler kann auftreten, wenn die Zeit auf dem lokalen System um mindestens fünf Minuten abweicht.</span><span class="sxs-lookup"><span data-stu-id="c25c0-153">This can occur if the time on the local system is out of sync by five minutes or more.</span></span> <span data-ttu-id="c25c0-154">Wenn die Zeit auf dem lokalen Computer nicht synchron ist, schlagen sichere Transaktionen fehl, da der Zeitstempel ungültig ist.</span><span class="sxs-lookup"><span data-stu-id="c25c0-154">If the time on the local computer is out of sync, secure transactions will fail because the time stamps will be invalid.</span></span>

<span data-ttu-id="c25c0-155">Um dieses Problem zu beheben, legen Sie die lokale Systemzeit so genau wie möglich auf die Internetzeit oder die auf den Domänencontrollern im Netzwerk eingestellte Zeit fest.</span><span class="sxs-lookup"><span data-stu-id="c25c0-155">To resolve this issue, set the local system time as close as possible to Internet time, or to the time set on the domain controllers on the network.</span></span>








### <a name="next-steps"></a><span data-ttu-id="c25c0-156">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="c25c0-156">Next steps</span></span>
<span data-ttu-id="c25c0-157">Wenn diese Informationen zur Problembehandlung für Sie nicht hilfreich waren, wenden Sie sich wie in [Anfordern von Support für Microsoft Intune](how-to-get-support-for-microsoft-intune.md) beschrieben an den Microsoft Support.</span><span class="sxs-lookup"><span data-stu-id="c25c0-157">If this troubleshooting information didn't help you, contact Microsoft Support as described in [How to get support for Microsoft Intune](how-to-get-support-for-microsoft-intune.md).</span></span>
