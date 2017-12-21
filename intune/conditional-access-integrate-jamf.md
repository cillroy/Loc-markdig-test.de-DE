---
title: "Integrieren von Jamf Pro in Intune zu Konformitätszwecken"
titlesuffix: Azure portal
description: "Verwenden Sie die Konformität zum Absichern von mit Jamf verwalteten Geräten."
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 12/14/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4b6dcbcc-4661-4463-9a36-698d673502c6
ms.reviewer: elocholi
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 8160ec67c6adf25e4a2555cc4195c26821ba070b
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2017
---
# <a name="integrate-jamf-pro-with-intune-for-compliance"></a><span data-ttu-id="57bba-103">Integrieren von Jamf Pro in Intune zu Konformitätszwecken</span><span class="sxs-lookup"><span data-stu-id="57bba-103">Integrate Jamf Pro with Intune for compliance</span></span>

|<span data-ttu-id="57bba-104">Gilt für: Intune im Azure-Portal</span><span class="sxs-lookup"><span data-stu-id="57bba-104">Applies to: Intune in the Azure portal</span></span> |
|--|
|<span data-ttu-id="57bba-105">Suchen Sie nach der Dokumentation zu Intune im klassischen Portal?</span><span class="sxs-lookup"><span data-stu-id="57bba-105">Looking for documentation about Intune in the classic portal?</span></span> <span data-ttu-id="57bba-106">[Klicken Sie hier](/intune/introduction-intune?toc=/intune-classic/toc.json).</span><span class="sxs-lookup"><span data-stu-id="57bba-106">[Go here](/intune/introduction-intune?toc=/intune-classic/toc.json).</span></span>|
| |

<span data-ttu-id="57bba-107">Wenn Ihre Organisation [Jamf Pro](https://www.jamf.com) zur Verwaltung der Macs Ihrer Endbenutzer verwendet, können Sie Microsoft Intune-Konformitätsrichtlinien zusammen mit dem bedingten Zugriff in Azure Active Directory verwenden, um die Konformität von Geräten in Ihrer Organisation zu gewährleisten.</span><span class="sxs-lookup"><span data-stu-id="57bba-107">If your organization uses [Jamf Pro](https://www.jamf.com) to manage your end users' Macs, you can use Microsoft Intune compliance policies with Azure Active Directory conditional access to ensure that devices in your organization are compliant.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="57bba-108">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="57bba-108">Prerequisites</span></span>

<span data-ttu-id="57bba-109">Zur Konfiguration des bedingten Zugriffs mit Jamf Pro benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="57bba-109">You need the following to configure conditional access with Jamf Pro:</span></span>

- <span data-ttu-id="57bba-110">Zugriff auf die private Intune-Vorschau für den bedingten Zugriff unter macOS</span><span class="sxs-lookup"><span data-stu-id="57bba-110">Access to the Intune Private Preview for macOS conditional access</span></span>
- <span data-ttu-id="57bba-111">Jamf Pro 10.1.0 oder höher</span><span class="sxs-lookup"><span data-stu-id="57bba-111">Jamf Pro 10.1.0 or later</span></span>
- [<span data-ttu-id="57bba-112">Die Unternehmensportal-App für macOS</span><span class="sxs-lookup"><span data-stu-id="57bba-112">Company Portal app for macOS</span></span>](https://aka.ms/macoscompanyportal)
- <span data-ttu-id="57bba-113">macOS-Geräte mit OS X 10.11 Yosemite oder höher</span><span class="sxs-lookup"><span data-stu-id="57bba-113">macOS devices with OS X 10.11 Yosemite or later</span></span>

## <a name="connecting-intune-to-jamf-pro"></a><span data-ttu-id="57bba-114">Herstellen einer Verbindung zwischen Intune und Jamf Pro</span><span class="sxs-lookup"><span data-stu-id="57bba-114">Connecting Intune to Jamf Pro</span></span>

<span data-ttu-id="57bba-115">Eine Verbindung zwischen Intune und Jamf Pro können Sie folgendermaßen herstellen:</span><span class="sxs-lookup"><span data-stu-id="57bba-115">You can connect Intune with Jamf Pro by:</span></span>

1. <span data-ttu-id="57bba-116">Erstellen einer neuen Anwendung in Azure</span><span class="sxs-lookup"><span data-stu-id="57bba-116">Creating a new application in Azure</span></span>
2. <span data-ttu-id="57bba-117">Ermöglichen einer Integration von Intune in Jamf Pro</span><span class="sxs-lookup"><span data-stu-id="57bba-117">Enabling Intune to integrate with Jamf Pro</span></span>
3. <span data-ttu-id="57bba-118">Konfigurieren des bedingten Zugriffs in Jamf Pro</span><span class="sxs-lookup"><span data-stu-id="57bba-118">Configure conditional access in Jamf Pro</span></span>

## <a name="create-a-new-application-in-azure-active-directory"></a><span data-ttu-id="57bba-119">Erstellen einer neuen Anwendung in Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="57bba-119">Create a new application in Azure Active Directory</span></span>

1. <span data-ttu-id="57bba-120">Öffnen Sie **Azure Active Directory** > **App-Registrierungen**.</span><span class="sxs-lookup"><span data-stu-id="57bba-120">Open **Azure Active Directory** > **App Registrations**.</span></span>
2. <span data-ttu-id="57bba-121">Klicken Sie auf **+Registrierung einer neuen Anwendung**.</span><span class="sxs-lookup"><span data-stu-id="57bba-121">Click **+New application registration**.</span></span>
3. <span data-ttu-id="57bba-122">Geben Sie einen **Anzeigenamen** ein, z.B. **Bedingter Zugriff in Jamf**.</span><span class="sxs-lookup"><span data-stu-id="57bba-122">Enter a **display name**, such as **Jamf Conditional Access**.</span></span>
4. <span data-ttu-id="57bba-123">Wählen Sie **Web-App/API**.</span><span class="sxs-lookup"><span data-stu-id="57bba-123">Select **Web app / API**.</span></span>
5. <span data-ttu-id="57bba-124">Geben Sie die **Anmelde-URL** in Form Ihrer Jamf Pro-Instanz-URL an.</span><span class="sxs-lookup"><span data-stu-id="57bba-124">Specify the **Sign-On URL** using your Jamf Pro instance URL.</span></span>
6. <span data-ttu-id="57bba-125">Klicken Sie auf **Anwendung erstellen**.</span><span class="sxs-lookup"><span data-stu-id="57bba-125">Click **Create application**.</span></span>
7. <span data-ttu-id="57bba-126">Speichern Sie die neu erstellte **Anwendungs-ID**. Öffnen Sie dann **Einstellungen**, und navigieren Sie zu **API-Zugriff** > **Schlüssel**, um einen neuen Anwendungsschlüssel zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="57bba-126">Save the newly-created **Application ID**, then open **Settings** and navigate to **API Access** > **Keys** to create a new Application Key.</span></span> <span data-ttu-id="57bba-127">Geben Sie eine **Beschreibung** und eine **Ablaufzeit** ein, und speichern Sie dann den Anwendungsschlüssel.</span><span class="sxs-lookup"><span data-stu-id="57bba-127">Enter a **Description**, how long to wait before it **Expires**, then save the Application Key.</span></span>

  > [!IMPORTANT]
  > <span data-ttu-id="57bba-128">Der Anwendungsschlüssel wird während dieses Vorgangs nur einmal angezeigt.</span><span class="sxs-lookup"><span data-stu-id="57bba-128">The Application Key is only shown once during this process.</span></span> <span data-ttu-id="57bba-129">Achten Sie darauf, dass Sie ihn an einer Stelle speichern, an der Sie ihn problemlos abrufen können.</span><span class="sxs-lookup"><span data-stu-id="57bba-129">Be sure to save it somewhere where you can easily retrieve it.</span></span>

8. <span data-ttu-id="57bba-130">Öffnen Sie **Einstellungen**, und navigieren Sie dann zu **API-Zugriff** > **Erforderliche Berechtigungen**, und löschen Sie alle Berechtigungen.</span><span class="sxs-lookup"><span data-stu-id="57bba-130">Open **Settings**, then navigate to **API Access** > **Required Permissions** and delete all permissions.</span></span>

  > [!NOTE]
  > <span data-ttu-id="57bba-131">Fügen Sie eine neue erforderliche Berechtigung hinzu.</span><span class="sxs-lookup"><span data-stu-id="57bba-131">Add a new required permission.</span></span> <span data-ttu-id="57bba-132">Die Anwendung kann nur ordnungsgemäß funktionieren, wenn sie die einzelne erforderliche Berechtigung aufweist.</span><span class="sxs-lookup"><span data-stu-id="57bba-132">The application can have only work properly if it has the single required permission.</span></span>

9.  <span data-ttu-id="57bba-133">Wählen Sie **Microsoft Intune-API**, und klicken Sie auf **Auswählen**.</span><span class="sxs-lookup"><span data-stu-id="57bba-133">Select **Microsoft Intune API** and click **Select**.</span></span>
10. <span data-ttu-id="57bba-134">Wählen Sie **Geräteattribute an Microsoft Intune senden**, und klicken Sie auf **Auswählen**.</span><span class="sxs-lookup"><span data-stu-id="57bba-134">Choose **Send device attributes to Microsoft Intune** and click **Select**.</span></span>
11. <span data-ttu-id="57bba-135">Klicken Sie auf die Schaltfläche **Berechtigungen erteilen**, nachdem Sie die erforderlichen Berechtigungen für die Anwendung gespeichert haben.</span><span class="sxs-lookup"><span data-stu-id="57bba-135">Click the **Grant Permissions** button after saving the required permissions for the application.</span></span>

  > [!NOTE]
  > <span data-ttu-id="57bba-136">Wenn der Anwendungsschlüssel abläuft, müssen Sie einen neuen Anwendungsschlüssel in Microsoft Azure erstellen und dann die Daten für den bedingten Zugriff in Jamf Pro aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="57bba-136">If the Application Key expires, you must create a new Application Key in Microsoft Azure and then update the Conditional Access data in Jamf Pro.</span></span> <span data-ttu-id="57bba-137">In Azure kann sowohl der alte als auch der neue Schlüssel aktiv sein, um Dienstunterbrechungen zu verhindern.</span><span class="sxs-lookup"><span data-stu-id="57bba-137">Azure allows you to have both the old key and new key active to prevent service disruptions.</span></span>

## <a name="enable-intune-to-integrate-with-jamf-pro"></a><span data-ttu-id="57bba-138">Ermöglichen einer Integration von Intune in Jamf Pro</span><span class="sxs-lookup"><span data-stu-id="57bba-138">Enable Intune to integrate with Jamf Pro</span></span>

1. <span data-ttu-id="57bba-139">Öffnen Sie im Microsoft Azure-Portal **Microsoft Intune** > **Gerätekonformität** > **Partner > Geräteverwaltung**.</span><span class="sxs-lookup"><span data-stu-id="57bba-139">In the Microsoft Azure portal, open **Microsoft Intune** > **Device Compliance** > **Partner device management**.</span></span>
2. <span data-ttu-id="57bba-140">Aktivieren Sie den Konformitätsconnector für Jamf durch Einfügen der Anwendungs-ID in das Feld **Azure Active Directory-App-ID für Jamf**.</span><span class="sxs-lookup"><span data-stu-id="57bba-140">Enable the Compliance Connector for Jamf by pasting the Application ID into the **Jamf Azure Active Directory App ID** field.</span></span>
3. <span data-ttu-id="57bba-141">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="57bba-141">Click **Save**.</span></span>

## <a name="configure-microsoft-intune-integration-in-jamf-pro"></a><span data-ttu-id="57bba-142">Konfigurieren der Microsoft Intune-Integration in Jamf Pro</span><span class="sxs-lookup"><span data-stu-id="57bba-142">Configure Microsoft Intune Integration in Jamf Pro</span></span>

1. <span data-ttu-id="57bba-143">Navigieren Sie in Jamf Pro zu **Global Management** > **Conditional Access** (Globale Verwaltung > Bedingter Zugriff).</span><span class="sxs-lookup"><span data-stu-id="57bba-143">In Jamf Pro, navigate to **Global Management** > **Conditional Access**.</span></span> <span data-ttu-id="57bba-144">Klicken Sie auf der Registerkarte **Integration von Intune** auf die Schaltfläche **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="57bba-144">Click the **Edit** button on the **Microsoft Intune Integration** tab.</span></span>
2. <span data-ttu-id="57bba-145">Aktivieren Sie das Kontrollkästchen **Integration von Microsoft Intune aktivieren**.</span><span class="sxs-lookup"><span data-stu-id="57bba-145">Select the checkbox for **Enable Microsoft Intune Integration**.</span></span>
3. <span data-ttu-id="57bba-146">Geben Sie die erforderlichen Informationen zu Ihrem Azure-Mandanten ein, einschließlich **Location** (Standort) und **Domain name** (Domänenname) sowie die Angaben zu **Application ID** (Anwendungs-ID) und **Application Key** (Anwendungsschlüssel), die Sie in den vorherigen Schritten gespeichert haben.</span><span class="sxs-lookup"><span data-stu-id="57bba-146">Provide the required information about your Azure tenant, including **Location**, **Domain name**, and the **Application ID** and **Application Key** you saved from the previous steps.</span></span>
4. <span data-ttu-id="57bba-147">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="57bba-147">Click **Save**.</span></span> <span data-ttu-id="57bba-148">Jamf Pro testet Ihre Einstellungen und überprüft den Erfolg des Vorgangs.</span><span class="sxs-lookup"><span data-stu-id="57bba-148">Jamf Pro will test your settings and verify your success.</span></span>

## <a name="set-up-compliance-policies-and-register-devices"></a><span data-ttu-id="57bba-149">Einrichten von Konformitätsrichtlinien und Registrieren von Geräten</span><span class="sxs-lookup"><span data-stu-id="57bba-149">Set up compliance policies and register devices</span></span>

<span data-ttu-id="57bba-150">Nachdem Sie die Konfiguration der Integration zwischen Intune und Jamf abgeschlossen haben, müssen Sie [Konformitätsrichtlinien zu von Jamf verwalteten Geräten ](conditional-access-assign-jamf.md) zuordnen.</span><span class="sxs-lookup"><span data-stu-id="57bba-150">After you finish configuring integration between Intune and Jamf, you need to [apply compliance policies to Jamf-managed devices](conditional-access-assign-jamf.md).</span></span>

## <a name="information-shared-from-jamf-pro-to-intune"></a><span data-ttu-id="57bba-151">Von Jamf Pro für Intune freigegebene Informationen</span><span class="sxs-lookup"><span data-stu-id="57bba-151">Information shared from Jamf Pro to Intune</span></span>

<span data-ttu-id="57bba-152">Jamf Pro erfasst Inventurinformationen zu verwalteten macOS-Geräten.</span><span class="sxs-lookup"><span data-stu-id="57bba-152">Jamf Pro captures inventory information about managed macOS devices.</span></span> <span data-ttu-id="57bba-153">Jamf Pro meldet die folgenden Informationen an Intune:</span><span class="sxs-lookup"><span data-stu-id="57bba-153">Jamf Pro reports the following information to Intune:</span></span>

* <span data-ttu-id="57bba-154">Azure AD-Geräte-ID</span><span class="sxs-lookup"><span data-stu-id="57bba-154">Device Azure AD ID</span></span>
* <span data-ttu-id="57bba-155">JAMF-Inventurstatus (Inventurstatus eines Computers, der sich innerhalb der letzten 24 Stunden bei Jamf Pro eingecheckt hat)</span><span class="sxs-lookup"><span data-stu-id="57bba-155">JAMF Inventory State (inventory state of a computer checked in with Jamf Pro within the last 24 hours)</span></span>
* <span data-ttu-id="57bba-156">Betriebssystemversion</span><span class="sxs-lookup"><span data-stu-id="57bba-156">OS Version</span></span>
* <span data-ttu-id="57bba-157">Azure AD-Benutzer-ID</span><span class="sxs-lookup"><span data-stu-id="57bba-157">User Azure AD ID</span></span>
* <span data-ttu-id="57bba-158">Verschlüsselt (FileVault 2)</span><span class="sxs-lookup"><span data-stu-id="57bba-158">Encrypted (FileVault 2)</span></span>
* <span data-ttu-id="57bba-159">Gatekeeperstatus</span><span class="sxs-lookup"><span data-stu-id="57bba-159">Gatekeeper Status</span></span>
* <span data-ttu-id="57bba-160">Kennwort: Mindestanzahl von Zeichensätzen</span><span class="sxs-lookup"><span data-stu-id="57bba-160">Password: minimum number of character sets</span></span>
* <span data-ttu-id="57bba-161">Kennwortablauf (Tage)</span><span class="sxs-lookup"><span data-stu-id="57bba-161">Password expiration (days)</span></span>
* <span data-ttu-id="57bba-162">Kennworttyp: einfach, alphanumerisch oder unbekannt</span><span class="sxs-lookup"><span data-stu-id="57bba-162">Password Type - simple, alphanumeric, or unknown</span></span>
* <span data-ttu-id="57bba-163">Automatische Anmeldung verhindern</span><span class="sxs-lookup"><span data-stu-id="57bba-163">Prevent Auto Login</span></span>
* <span data-ttu-id="57bba-164">Erforderliche Kennungslänge</span><span class="sxs-lookup"><span data-stu-id="57bba-164">Required Passcode Length</span></span>
* <span data-ttu-id="57bba-165">Kennwort: Anzahl vorheriger Kennwörter zum Verhindern der Wiederverwendung</span><span class="sxs-lookup"><span data-stu-id="57bba-165">Password: number of previous passwords to prevent reuse</span></span>
* <span data-ttu-id="57bba-166">Systemintegritätsschutz</span><span class="sxs-lookup"><span data-stu-id="57bba-166">System Integrity Protection</span></span>
* <span data-ttu-id="57bba-167">Zeitpunkt des letzten Check-Ins</span><span class="sxs-lookup"><span data-stu-id="57bba-167">Last Check-In Time</span></span>
* <span data-ttu-id="57bba-168">Architekturtyp</span><span class="sxs-lookup"><span data-stu-id="57bba-168">Architecture Type</span></span>
* <span data-ttu-id="57bba-169">Verfügbare Speichersteckplätze</span><span class="sxs-lookup"><span data-stu-id="57bba-169">Available RAM Slots</span></span>
* <span data-ttu-id="57bba-170">Akkukapazität</span><span class="sxs-lookup"><span data-stu-id="57bba-170">Battery Capacity</span></span>
* <span data-ttu-id="57bba-171">Start-ROM</span><span class="sxs-lookup"><span data-stu-id="57bba-171">Boot ROM</span></span>
* <span data-ttu-id="57bba-172">Busgeschwindigkeit</span><span class="sxs-lookup"><span data-stu-id="57bba-172">Bus Speed</span></span>
* <span data-ttu-id="57bba-173">Cachegröße</span><span class="sxs-lookup"><span data-stu-id="57bba-173">Cache Size</span></span>
* <span data-ttu-id="57bba-174">Gerätename</span><span class="sxs-lookup"><span data-stu-id="57bba-174">Device Name</span></span>
* <span data-ttu-id="57bba-175">Domäne beitreten</span><span class="sxs-lookup"><span data-stu-id="57bba-175">Domain Join</span></span>
* <span data-ttu-id="57bba-176">Jamf-ID</span><span class="sxs-lookup"><span data-stu-id="57bba-176">Jamf ID</span></span>
* <span data-ttu-id="57bba-177">MAC-Adresse</span><span class="sxs-lookup"><span data-stu-id="57bba-177">MAC address</span></span>
* <span data-ttu-id="57bba-178">Automarke</span><span class="sxs-lookup"><span data-stu-id="57bba-178">Make</span></span>
* <span data-ttu-id="57bba-179">Modell</span><span class="sxs-lookup"><span data-stu-id="57bba-179">Model</span></span>
* <span data-ttu-id="57bba-180">Modellbezeichnung</span><span class="sxs-lookup"><span data-stu-id="57bba-180">Model Identifier</span></span>
* <span data-ttu-id="57bba-181">NIC-Geschwindigkeit</span><span class="sxs-lookup"><span data-stu-id="57bba-181">NIC Speed</span></span>
* <span data-ttu-id="57bba-182">Anzahl der Kerne</span><span class="sxs-lookup"><span data-stu-id="57bba-182">Number of Cores</span></span>
* <span data-ttu-id="57bba-183">Prozessoranzahl</span><span class="sxs-lookup"><span data-stu-id="57bba-183">Number of Processors</span></span>
* <span data-ttu-id="57bba-184">Betriebssystem</span><span class="sxs-lookup"><span data-stu-id="57bba-184">OS</span></span>
* <span data-ttu-id="57bba-185">Plattform</span><span class="sxs-lookup"><span data-stu-id="57bba-185">Platform</span></span>
* <span data-ttu-id="57bba-186">Prozessorgeschwindigkeit</span><span class="sxs-lookup"><span data-stu-id="57bba-186">Processor Speed</span></span>
* <span data-ttu-id="57bba-187">Prozessortyp</span><span class="sxs-lookup"><span data-stu-id="57bba-187">Processor Type</span></span>
* <span data-ttu-id="57bba-188">Sekundäre MAC-Adresse</span><span class="sxs-lookup"><span data-stu-id="57bba-188">Secondary MAC Address</span></span>
* <span data-ttu-id="57bba-189">Seriennummer</span><span class="sxs-lookup"><span data-stu-id="57bba-189">Serial Number</span></span>
* <span data-ttu-id="57bba-190">SMC-Version</span><span class="sxs-lookup"><span data-stu-id="57bba-190">SMC Version</span></span>
* <span data-ttu-id="57bba-191">RAM gesamt</span><span class="sxs-lookup"><span data-stu-id="57bba-191">Total RAM</span></span>
* <span data-ttu-id="57bba-192">UDID</span><span class="sxs-lookup"><span data-stu-id="57bba-192">UDID</span></span>
* <span data-ttu-id="57bba-193">Benutzer-E-Mail-Adresse</span><span class="sxs-lookup"><span data-stu-id="57bba-193">User Email</span></span>

## <a name="next-steps"></a><span data-ttu-id="57bba-194">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="57bba-194">Next steps</span></span>

- [<span data-ttu-id="57bba-195">Anwenden von Konformitätsrichtlinien auf mit Jamf verwaltete Geräte</span><span class="sxs-lookup"><span data-stu-id="57bba-195">Apply compliance policies to Jamf-managed devices</span></span>](conditional-access-assign-jamf.md)
