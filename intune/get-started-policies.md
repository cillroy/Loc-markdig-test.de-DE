---
title: Erste Schritte mit Richtlinien
titlesuffix: Azure portal
description: "Erstellen Sie Richtlinien, um zu verhindern, dass Benutzer nicht autorisierte Aktionen mit ihren Geräten vornehmen."
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 10/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 1ac74ba5-7441-44ac-98b5-9d8bb8899747
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 5bef1d46bff5d519ae6153f6858c929c70fc504a
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2017
---
# <a name="get-started-with-policies"></a><span data-ttu-id="9fc8a-103">Erste Schritte mit Richtlinien</span><span class="sxs-lookup"><span data-stu-id="9fc8a-103">Get started with policies</span></span>

<span data-ttu-id="9fc8a-104">Eine der wichtigsten Zielsetzungen bei den ersten Schritten mit Intune ist das Registrieren von Geräten, um sicherzustellen, dass sie mit den Unternehmensrichtlinien kompatibel sind.</span><span class="sxs-lookup"><span data-stu-id="9fc8a-104">One of the main goals of getting started with Intune is enrolling devices to make sure that they are compliant with corporate policies.</span></span> <span data-ttu-id="9fc8a-105">Mit Kompatibilitätsrichtlinien können Sie nicht nur spezielle Gerätetypen wie z.B. firmeneigene Kioske verwalten, sondern auch persönliche Geräte und Tablets sowie benutzerlose Geräte.</span><span class="sxs-lookup"><span data-stu-id="9fc8a-105">Compliance policies not only help you to manage specialized device types, such as corporate-owned kiosks, but also personal (Bring Your Own) devices, tablets, and user-less devices.</span></span>

![Kompatibilitätsdashboard mit sehr wenigen Daten](/intune/media/generic-compliance-dashboard.png)

<span data-ttu-id="9fc8a-107">Kompatibilitätsrichtlinien bieten folgende Managementfunktionen für mobile Geräte:</span><span class="sxs-lookup"><span data-stu-id="9fc8a-107">Compliance policies provide the following management capabilities for mobile devices:</span></span>

* <span data-ttu-id="9fc8a-108">Regulierung der Anzahl von Geräten, die jeder Benutzer registriert</span><span class="sxs-lookup"><span data-stu-id="9fc8a-108">Regulate numbers of devices each user enrolls</span></span>
* <span data-ttu-id="9fc8a-109">Verwalten der Geräteeinstellungen (z.B Verschlüsselung auf Geräteebene, Länge des Kennworts, Kameragebrauch)</span><span class="sxs-lookup"><span data-stu-id="9fc8a-109">Manage devices settings (e.g. device-level encryption, password length, camera usage)</span></span>
* <span data-ttu-id="9fc8a-110">Bereitstellen von Apps, E-Mail-Profilen, VPN-Profilen, etc.</span><span class="sxs-lookup"><span data-stu-id="9fc8a-110">Deliver apps, email profiles, VPN profiles, etc.</span></span>
* <span data-ttu-id="9fc8a-111">Auswerten der Kriterien für Sicherheitskompatibilitätsrichtlinien auf Geräteebene</span><span class="sxs-lookup"><span data-stu-id="9fc8a-111">Evaluate device-level criteria for security compliance policies</span></span>

<span data-ttu-id="9fc8a-112">Sie erstellen Kompatibilitätsrichtlinien für jede Plattform einzeln.</span><span class="sxs-lookup"><span data-stu-id="9fc8a-112">You create compliance policies for each platform separately.</span></span> <span data-ttu-id="9fc8a-113">In dieser Übung verwenden wir nur iOS.</span><span class="sxs-lookup"><span data-stu-id="9fc8a-113">For this exercise, we’ll stick to iOS.</span></span> <span data-ttu-id="9fc8a-114">Die folgenden Richtlinien sind für iOS-Geräte verfügbar:</span><span class="sxs-lookup"><span data-stu-id="9fc8a-114">The following policies are available for iOS devices:</span></span>

* <span data-ttu-id="9fc8a-115">PIN- oder Kennwortkonfiguration</span><span class="sxs-lookup"><span data-stu-id="9fc8a-115">PIN or password configuration</span></span>
* <span data-ttu-id="9fc8a-116">Geräteverschlüsselung</span><span class="sxs-lookup"><span data-stu-id="9fc8a-116">Device encryption</span></span>
* <span data-ttu-id="9fc8a-117">Per Jailbreak manipuliertes Gerät</span><span class="sxs-lookup"><span data-stu-id="9fc8a-117">Jailbroken device</span></span>
* <span data-ttu-id="9fc8a-118">E-Mail-Profil</span><span class="sxs-lookup"><span data-stu-id="9fc8a-118">Email profile</span></span>
* <span data-ttu-id="9fc8a-119">Minimale Version des Betriebssystems</span><span class="sxs-lookup"><span data-stu-id="9fc8a-119">Minimum OS version</span></span>
* <span data-ttu-id="9fc8a-120">Maximale Version des Betriebssystems</span><span class="sxs-lookup"><span data-stu-id="9fc8a-120">Maximum OS version</span></span>

<span data-ttu-id="9fc8a-121">__Wie erstelle ich eine Richtlinie?__</span><span class="sxs-lookup"><span data-stu-id="9fc8a-121">__How do I create a policy?__</span></span>

1. <span data-ttu-id="9fc8a-122">Melden Sie sich beim [Azure-Portal](https://portal.azure.com) an.</span><span class="sxs-lookup"><span data-stu-id="9fc8a-122">Sign in to the [Azure portal](https://portal.azure.com).</span></span>
2. <span data-ttu-id="9fc8a-123">Suchen Sie über **Ressourcen durchsuchen** nach **Intune**.</span><span class="sxs-lookup"><span data-stu-id="9fc8a-123">**Search resources**, search for **Intune**.</span></span>
3. <span data-ttu-id="9fc8a-124">Wählen Sie **Gerätekompatibilität** aus.</span><span class="sxs-lookup"><span data-stu-id="9fc8a-124">Select **Device compliance**.</span></span>
4. <span data-ttu-id="9fc8a-125">Wählen Sie auf dem Blatt **Gerätekompatibilität** die Option **Richtlinien** aus.</span><span class="sxs-lookup"><span data-stu-id="9fc8a-125">On the **Device compliance** blade, select **Policies**.</span></span>
5. <span data-ttu-id="9fc8a-126">Wählen Sie **Richtlinie erstellen** aus, und geben Sie dann die Details wie **Name** und **Beschreibung** ein.</span><span class="sxs-lookup"><span data-stu-id="9fc8a-126">Select **Create Policy**, then fill in the details, like **Name** and **Description**.</span></span> <span data-ttu-id="9fc8a-127">Wählen Sie **iOS** als **Plattform** aus.</span><span class="sxs-lookup"><span data-stu-id="9fc8a-127">Choose **iOS** as the **Platform**.</span></span>
6. <span data-ttu-id="9fc8a-128">Wählen Sie unter **Einstellungen** die Option **Systemsicherheit** aus, und legen Sie dann die Umschaltfläche **Anfordern eines Kennworts zum Entsperren mobiler Geräte** auf **Erforderlich** fest.</span><span class="sxs-lookup"><span data-stu-id="9fc8a-128">In **Settings**, select **System Security**, then toggle **Require a password to unlock mobile devices** to **Require**.</span></span> <span data-ttu-id="9fc8a-129">Sie können auch weitere Regeln festlegen wie z.B. **Mindestlänge von Kennwörtern**, **Erforderlicher Kennworttyp** und **Anzahl nicht alphanumerischer Zeichen im Kennwort**.</span><span class="sxs-lookup"><span data-stu-id="9fc8a-129">You can also set other rules, such as **Minimum password length**, **Required password type**, and **Number of non-alphanumeric characters in password**.</span></span> <span data-ttu-id="9fc8a-130">Wenn Sie Ihre Richtlinie eingerichtet haben, wählen Sie **OK** aus.</span><span class="sxs-lookup"><span data-stu-id="9fc8a-130">When you’ve finished setting up your policy, select **OK**.</span></span>
7. <span data-ttu-id="9fc8a-131">Kehren Sie zurück zum Blatt **Richtlinie erstellen**, und wählen Sie dann **Erstellen** aus.</span><span class="sxs-lookup"><span data-stu-id="9fc8a-131">Return to the **Create policy** blade, then select **Create**.</span></span>
8. <span data-ttu-id="9fc8a-132">Wählen Sie nach dem Erstellen der Richtlinie **Zuweisungen** aus, um sie Ihrer Testgruppe zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="9fc8a-132">Once the policy is created, select **Assignments** to assign it to your test group.</span></span> <span data-ttu-id="9fc8a-133">Wählen Sie Ihre Testgruppe mit Ihren Testbenutzern aus, und weisen Sie dieser Gruppe dann die Richtlinie zu, indem Sie auf **Speichern** klicken.</span><span class="sxs-lookup"><span data-stu-id="9fc8a-133">Select your test group – which should have your test user in it – then assign the policy to that group by clicking **Save**.</span></span>
9. <span data-ttu-id="9fc8a-134">Warten Sie einige Minuten, bis Ihr registriertes Gerät Sie zur Eingabe eines aktualisierten Kennworts auffordert, damit weiterhin Kompatibilität mit der Unternehmensrichtlinie gegeben ist.</span><span class="sxs-lookup"><span data-stu-id="9fc8a-134">Wait a few minutes, then your enrolled device should prompt you that it needs an updated password in order to remain compliant with corporate policy.</span></span> <span data-ttu-id="9fc8a-135">Sie können dies auch manuell in der **Unternehmensportal-App für iOS** überprüfen, indem Sie auf den Gerätenamen und dann auf die Schaltfläche **Synchronisieren** klicken.</span><span class="sxs-lookup"><span data-stu-id="9fc8a-135">You can also manually check for this in the **Company Portal app for iOS** by tapping on the device name, then the **Sync** button.</span></span>

## <a name="next-steps"></a><span data-ttu-id="9fc8a-136">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="9fc8a-136">Next steps</span></span>

<span data-ttu-id="9fc8a-137">[Erste Schritte beim Registrieren von Geräten:](get-started-enroll.md) Machen Sie sich mit dem Registrierungsprozess vertraut, indem Sie ein iOS-Gerät vollständig registrieren.</span><span class="sxs-lookup"><span data-stu-id="9fc8a-137">[Get started enrolling devices](get-started-enroll.md) - Learn the enrollment experience by going through a full enrollment experience of an iOS device.</span></span>

## <a name="learn-more"></a><span data-ttu-id="9fc8a-138">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="9fc8a-138">Learn more</span></span>

* [<span data-ttu-id="9fc8a-139">Überwachen von Intune-Richtlinien zur Gerätekompatibilität</span><span class="sxs-lookup"><span data-stu-id="9fc8a-139">Monitor Intune Device compliance policies</span></span>](compliance-policy-monitor.md)
* [<span data-ttu-id="9fc8a-140">Gängige Möglichkeiten der Verwendung des bedingten Zugriffs in Intune</span><span class="sxs-lookup"><span data-stu-id="9fc8a-140">Common ways to use conditional access policies with Intune</span></span>](conditional-access-intune-common-ways-use.md)
