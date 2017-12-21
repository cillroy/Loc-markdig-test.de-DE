---
title: "Konfigurieren der Richtlinien für die Gerätekonformität und App-Verwaltung während einer Migration von Intune"
description: "Dieser Artikel stellt die für das Konfigurieren der Richtlinien für die Gerätekompatibilität und die App-Verwaltung notwendigen Schritte während einer Migration von Intune bereit."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 07/11/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 0062d08e-e5b3-4f73-8b64-5ad95adbe945
ms.reviewer: dagerrit
ms.suite: ems
ms.openlocfilehash: b75368bb8a1172444036b5bd695a4ec36cd9727c
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2017
---
# <a name="configure-device-compliance-and-app-management-policies"></a><span data-ttu-id="ffc5c-103">Konfigurieren von Richtlinien für die Gerätekonformität und App-Verwaltung</span><span class="sxs-lookup"><span data-stu-id="ffc5c-103">Configure device compliance and app management policies</span></span>

<span data-ttu-id="ffc5c-104">Das Hauptziel der Migration zu Intune ist die Registrierung aller Geräte in Intune und die Kompatibilität aller Geräte mit ihren Richtlinien.</span><span class="sxs-lookup"><span data-stu-id="ffc5c-104">The main goal when migrating to Intune is to have all devices enrolled in Intune and compliant with its policies.</span></span> <span data-ttu-id="ffc5c-105">Geräterichtlinien helfen Ihnen nicht nur dabei, firmeneigene Geräte mit nur einem Benutzer zu verwalten, sondern auch bei der Verwaltung persönlicher (Bring-Your-Own-Device, BYOD) und freigegebener Geräte, wie z.B. Kiosks, Verkaufsortcomputer, Tablets, die von mehreren Schülern in einem Klassenzimmer verwendet werden, oder Geräte ohne Benutzer (nur iOS).</span><span class="sxs-lookup"><span data-stu-id="ffc5c-105">Device policies not only help you to manage corporate-owned single-user devices, but also personal (BYOD), and shared devices such as kiosks, point-of-sales machines, tablets shared by multiple students in a classroom, or user-less devices (iOS only).</span></span>

<span data-ttu-id="ffc5c-106">Jede Geräteplattform hat möglicherweise unterschiedliche Einstellungen, aber Geräterichtlinien von Intune funktionieren durch folgende MDM-Funktionen mit jeder Geräteplattform:</span><span class="sxs-lookup"><span data-stu-id="ffc5c-106">Each device platform may offer different settings, but Intune device policies work with each device platform by providing the following mobile device management capabilities:</span></span>

-   <span data-ttu-id="ffc5c-107">Regulierung der Zahl von Geräten, die jeder Benutzer registriert</span><span class="sxs-lookup"><span data-stu-id="ffc5c-107">Regulate numbers of devices each user enrolls.</span></span>

-   <span data-ttu-id="ffc5c-108">Verwalten der Geräteeinstellungen (z.B Verschlüsselung auf Geräteebene, Länge des Kennworts, Kameragebrauch)</span><span class="sxs-lookup"><span data-stu-id="ffc5c-108">Manage devices settings (for example, device-level encryption, password length, camera usage).</span></span>

-   <span data-ttu-id="ffc5c-109">Bereitstellen von Apps, E-Mail-Profilen, VPN-Profilen, etc.</span><span class="sxs-lookup"><span data-stu-id="ffc5c-109">Deliver apps, email profiles, VPN profiles, and so on.</span></span>

-   <span data-ttu-id="ffc5c-110">Auswerten der Kriterien für Sicherheitskompatibilitätsrichtlinien auf der Geräteebene</span><span class="sxs-lookup"><span data-stu-id="ffc5c-110">Evaluate device-level criteria for security compliance policies.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ffc5c-111">Geräteverwaltungsrichtlinien werden einzelnen Geräten oder Benutzern nicht direkt zugewiesen, sondern ganzen Benutzergruppen.</span><span class="sxs-lookup"><span data-stu-id="ffc5c-111">Device management policies are not assigned directly to individual devices or users, but instead are assigned to user groups.</span></span> <span data-ttu-id="ffc5c-112">Die Richtlinien können direkt auf Benutzergruppen und somit auch auf das Geräte des Benutzers angewendet werden; die Richtlinien können auch auf eine Gerätegruppe und somit auch auf Gruppenmitglieder angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="ffc5c-112">The policies may be directly applied to a user group, and thereby to the user's device, or the policies may be applied to a device group, and thereby to group members.</span></span>

## <a name="task-list-for-device-compliance-policies"></a><span data-ttu-id="ffc5c-113">Aufgabenliste für Gerätekompatibilitätsrichtlinien</span><span class="sxs-lookup"><span data-stu-id="ffc5c-113">Task list for device compliance policies</span></span>

### <a name="task-1-add-device-groups-optional"></a><span data-ttu-id="ffc5c-114">Aufgabe 1: Mobile Gerätegruppen hinzufügen (optional)</span><span class="sxs-lookup"><span data-stu-id="ffc5c-114">Task 1: Add device groups (optional)</span></span>

<span data-ttu-id="ffc5c-115">Sie können Gerätegruppen erstellen, wenn Sie Verwaltungsaufgaben basierend auf Geräteidentität statt auf Benutzeridentität durchführen müssen.</span><span class="sxs-lookup"><span data-stu-id="ffc5c-115">You can create device groups when you need to perform administrative tasks based on device identity instead of user identity.</span></span>

<span data-ttu-id="ffc5c-116">Benutzergruppen sind nützlich bei der Verwaltung von Geräten ohne dedizierte Benutzer, wie z.B Kioskgeräte, oder von Geräten, die für Schichtarbeiter freigegeben oder einem bestimmtem Standort zugewiesen wurden.</span><span class="sxs-lookup"><span data-stu-id="ffc5c-116">Device groups are useful for managing devices that do not have dedicated users, such as kiosk devices, devices shared by shift workers, or devices assigned to a specific location.</span></span>

<span data-ttu-id="ffc5c-117">Wenn Sie Gerätegruppen schon vor der Geräteregistrierung konfigurieren, können Sie Gerätekategorien nutzen, um Geräte automatisch mit Gruppen vor der Registrierung zu verknüpfen.</span><span class="sxs-lookup"><span data-stu-id="ffc5c-117">By configuring device groups ahead of device enrollment, you can use device categories to automatically join devices to groups upon enrollment.</span></span> <span data-ttu-id="ffc5c-118">Dann erhalten Sie automatisch die Geräterichtlinien ihrer Gruppe.</span><span class="sxs-lookup"><span data-stu-id="ffc5c-118">Then they will receive their group’s device policies automatically.</span></span> <span data-ttu-id="ffc5c-119">[Erste Schritte mit Gruppen](groups-get-started.md).</span><span class="sxs-lookup"><span data-stu-id="ffc5c-119">[Get started with groups](groups-get-started.md).</span></span>

### <a name="task-2-use-resource-access-profiles-wi-fi-vpn-and-email-certificates"></a><span data-ttu-id="ffc5c-120">Aufgabe 2: Verwenden von Profilen für den Ressourcenzugriff (WLAN, VPN und E-Mail-Zertifikate)</span><span class="sxs-lookup"><span data-stu-id="ffc5c-120">Task 2: Use resource access profiles (Wi-Fi, VPN, and email certificates)</span></span>

<span data-ttu-id="ffc5c-121">Profile für den Ressourcenzugriff stellen Zertifikate und Zugriffskonfigurationen für die Geräteregistrierung bereit.</span><span class="sxs-lookup"><span data-stu-id="ffc5c-121">Resource access profiles supply certificates and access configurations to enrolled devices.</span></span> <span data-ttu-id="ffc5c-122">Wenn Sie eine zertifikatbasierte Authentifizierung nutzen, [konfigurieren Sie Zertifikate](certificates-configure.md).</span><span class="sxs-lookup"><span data-stu-id="ffc5c-122">If you are using certificate-based authentication, [configure certificates](certificates-configure.md).</span></span>

### <a name="task-3-create-and-deploy-device-configuration-profiles"></a><span data-ttu-id="ffc5c-123">Aufgabe 3: Erstellen und Bereitstellen von Gerätekonfigurationsprofilen</span><span class="sxs-lookup"><span data-stu-id="ffc5c-123">Task 3: Create and deploy device configuration profiles</span></span>

<span data-ttu-id="ffc5c-124">Sie müssen ein Gerätekonfigurationsprofil erstellen, um Einstellungen auf der Geräteebene zu erzwingen, wie z.B. Deaktivieren der Kamera, App Store, Konfigurieren des Einzelanwendungsmodus, Startbildschirm, etc.</span><span class="sxs-lookup"><span data-stu-id="ffc5c-124">You need to create a device configuration profile to enforce device-level settings, for example: disable camera, app-store, configure single-app mode, home screen, and so on.</span></span> <span data-ttu-id="ffc5c-125">Erfahren Sie mehr über [Geräteprofile](device-profiles.md).</span><span class="sxs-lookup"><span data-stu-id="ffc5c-125">Learn about [device profiles](device-profiles.md).</span></span>

####  <a name="directly-import-ios-configuration-profiles-optional"></a><span data-ttu-id="ffc5c-126">Direkter Import von iOS-Konfigurationsprofilen (optional)</span><span class="sxs-lookup"><span data-stu-id="ffc5c-126">Directly import iOS configuration profiles (optional)</span></span>

-   <span data-ttu-id="ffc5c-127">**iOS-Profile von Apple Configurator (iOS 7.1 und höher):** Wenn Ihre vorhandene MDM-Projektmappe Apple Configurator-Profile verwendet (MOBILECONFIG-Dateien), kann Intune diese direkt als benutzerdefinierte Konfigurationsrichtlinien importieren.</span><span class="sxs-lookup"><span data-stu-id="ffc5c-127">**Apple Configurator iOS profiles (iOS 7.1 and later):** If your existing MDM solution uses Apple Configurator profiles (.mobileconfig files), Intune can directly import them as custom configuration policies.</span></span>

-   <span data-ttu-id="ffc5c-128">**Richtlinien für die Konfiguration von mobilen iOS-Anwendungen:** Wenn Ihre vorhandene MDM-Lösung Richtlinien für die Konfiguration von mobilen iOS-Anwendungen verwendet, kann Intune diese direkt importieren, sofern sie dem XML-Format entsprechen, das von Apple für Eigenschaftenlisten festgelegt wurde.</span><span class="sxs-lookup"><span data-stu-id="ffc5c-128">**iOS Mobile Application Configuration policies:** If your existing MDM solution uses iOS Mobile Application Configuration policies, Intune can directly import them as long as they meet the XML format specified by Apple for property lists.</span></span>

- <span data-ttu-id="ffc5c-129">Erfahren Sie, wie Sie eine benutzerdefinierte Richtlinie für [iOS](custom-settings-ios.md) hinzufügen können.</span><span class="sxs-lookup"><span data-stu-id="ffc5c-129">Learn how to add a custom policy for [iOS](custom-settings-ios.md).</span></span>

### <a name="task-4-create-and-deploy-device-compliance-policies-optional"></a><span data-ttu-id="ffc5c-130">Aufgabe 4: Erstellen und Bereitstellen einer Gerätekompatibilitätsrichtlinie (optional)</span><span class="sxs-lookup"><span data-stu-id="ffc5c-130">Task 4: Create and deploy device compliance policies (optional)</span></span>

<span data-ttu-id="ffc5c-131">Gerätekonformitätsrichtlinien werten sicherheitsorientierte Einstellungen aus und bieten eine Berichterstattung, die anzeigt, ob die Geräte den Unternehmensansprüchen entsprechen.</span><span class="sxs-lookup"><span data-stu-id="ffc5c-131">Device compliance policies evaluate security-oriented settings, and provide reporting that shows whether the devices are compliant with corporate standards or not.</span></span> <span data-ttu-id="ffc5c-132">Dazu zählen die folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="ffc5c-132">Such settings include:</span></span>

-   <span data-ttu-id="ffc5c-133">PIN-Länge</span><span class="sxs-lookup"><span data-stu-id="ffc5c-133">PIN length</span></span>

-   <span data-ttu-id="ffc5c-134">Status „Jail-broken“ (Nutzungsbeschränkungen entfernt)</span><span class="sxs-lookup"><span data-stu-id="ffc5c-134">Jail-broken status</span></span>

-   <span data-ttu-id="ffc5c-135">BS-Version</span><span class="sxs-lookup"><span data-stu-id="ffc5c-135">OS version</span></span>

<span data-ttu-id="ffc5c-136">Hier finden Sie weitere Ressourcen für die Einstellungen der Gerätekompatibilität:</span><span class="sxs-lookup"><span data-stu-id="ffc5c-136">See additional resources for device compliance settings:</span></span>

-   <span data-ttu-id="ffc5c-137">Erfahren Sie mehr über [Gerätekompatibilitätsrichtlinien](device-compliance.md).</span><span class="sxs-lookup"><span data-stu-id="ffc5c-137">Learn about [device compliance policies](device-compliance.md).</span></span>

-   <span data-ttu-id="ffc5c-138">Erfahren Sie, wie Sie eine [Gerätekompatibilitätsrichtlinie erstellen](device-compliance-get-started.md) können.</span><span class="sxs-lookup"><span data-stu-id="ffc5c-138">Learn [how to create a device compliance policy](device-compliance-get-started.md).</span></span>

### <a name="task-5-publish-and-deploy-apps"></a><span data-ttu-id="ffc5c-139">Aufgabe 5: Veröffentlichen und Bereitstellen von Apps</span><span class="sxs-lookup"><span data-stu-id="ffc5c-139">Task 5: Publish and deploy apps</span></span>

<span data-ttu-id="ffc5c-140">Wenn Sie MDM mit Intune verwenden, können Sie Apps bereitstellen, indem Sie entweder deren automatische Installation verlangen oder sie über das Unternehmensportal zur Verfügung stellen.</span><span class="sxs-lookup"><span data-stu-id="ffc5c-140">When using Intune MDM, you can supply apps by either requiring their automatic installation, or making them available in the Company Portal.</span></span>

-   <span data-ttu-id="ffc5c-141">[So fügen Sie Apps hinzu](apps-add.md)</span><span class="sxs-lookup"><span data-stu-id="ffc5c-141">[How to add apps](apps-add.md).</span></span>

-   <span data-ttu-id="ffc5c-142">[Bereitstellen von Apps](apps-deploy.md)</span><span class="sxs-lookup"><span data-stu-id="ffc5c-142">[How to deploy apps](apps-deploy.md).</span></span>

### <a name="task-6-enable-device-enrollment"></a><span data-ttu-id="ffc5c-143">Aufgabe 6: Aktivieren der Geräteregistrierung</span><span class="sxs-lookup"><span data-stu-id="ffc5c-143">Task 6: Enable device enrollment</span></span>

<span data-ttu-id="ffc5c-144">Die Geräteregistrierung ist nötig, um das Gerät zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="ffc5c-144">Device enrollment is necessary to manage the device.</span></span> <span data-ttu-id="ffc5c-145">Erfahren Sie, wie Sie sich [auf die Registrierung von firmeneigenen und persönlichen Geräten vorbereiten](device-enrollment.md) können.</span><span class="sxs-lookup"><span data-stu-id="ffc5c-145">Learn [how to get ready to enroll corporate-owned and user personal's devices](device-enrollment.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="ffc5c-146">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="ffc5c-146">Next steps</span></span>

<span data-ttu-id="ffc5c-147">[Konfigurieren von App-Schutzrichtlinien (optional)](migration-guide-app-protection-policies.md)</span><span class="sxs-lookup"><span data-stu-id="ffc5c-147">[Configure app protection policies (optional)](migration-guide-app-protection-policies.md).</span></span>
