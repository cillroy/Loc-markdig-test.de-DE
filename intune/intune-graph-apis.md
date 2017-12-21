---
title: "Zugreifen auf die Intune Graph-API über Azure Active Directory"
description: "Beschreibung der Schritte, damit Apps über Azure AD auf die Intune Graph-API zugreifen können"
keywords: Intune Graph-API C# PowerShell Berechtigungsrollen
author: vhorne
manager: angrobe
ms.author: victorh
ms.date: 06/20/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 79A67342-C06D-4D20-A447-678A6CB8D70A
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 351a066c8852125b6fbf26c039dd3718b63f8980
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2017
---
# <a name="how-to-use-azure-ad-to-access-the-intune-graph-api"></a><span data-ttu-id="8d063-104">Zugreifen auf die Intune Graph-API über Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="8d063-104">How to use Azure AD to access the Intune Graph API</span></span>

<span data-ttu-id="8d063-105">Die [Microsoft Graph-API](https://developer.microsoft.com/graph/) unterstützt jetzt Microsoft Intune mit bestimmten APIs und Berechtigungsrollen.</span><span class="sxs-lookup"><span data-stu-id="8d063-105">The [Microsoft Graph API](https://developer.microsoft.com/graph/) now supports Microsoft Intune with specific APIs and permission roles.</span></span>  <span data-ttu-id="8d063-106">Der Graph-API verwendet für die Authentifizierung und Zugriffsteuerung Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="8d063-106">The Graph API uses Azure Active Directory (Azure AD) for authentication and access control.</span></span>  
<span data-ttu-id="8d063-107">Für den Zugriff auf die Intune Graph-API benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="8d063-107">Access to the Intune Graph API requires:</span></span>

- <span data-ttu-id="8d063-108">Eine Anwendungs-ID mit:</span><span class="sxs-lookup"><span data-stu-id="8d063-108">An application ID with:</span></span>

    - <span data-ttu-id="8d063-109">Berechtigung zum Aufrufen von Azure AD und Graph-APIs</span><span class="sxs-lookup"><span data-stu-id="8d063-109">Permission to call Azure AD and Graph APIs.</span></span>
    - <span data-ttu-id="8d063-110">Berechtigungsbereichen, die für bestimmte Anwendungsaufgaben relevant sind</span><span class="sxs-lookup"><span data-stu-id="8d063-110">Permission scopes relevant to the specific application tasks.</span></span>

- <span data-ttu-id="8d063-111">Benutzeranmeldeinformationen mit:</span><span class="sxs-lookup"><span data-stu-id="8d063-111">User credentials with:</span></span>

    - <span data-ttu-id="8d063-112">Zugriffsberechtigung für den Azure AD-Mandanten, der der Anwendung zugeordnet ist</span><span class="sxs-lookup"><span data-stu-id="8d063-112">Permission to access the Azure AD tenant associated with the application.</span></span>
    - <span data-ttu-id="8d063-113">Rollenberechtigungen zur Unterstützung der Anwendungsberechtigungsbereiche</span><span class="sxs-lookup"><span data-stu-id="8d063-113">Role permissions required to support the application permission scopes.</span></span>

- <span data-ttu-id="8d063-114">Der App durch den Endbenutzer erteilte Berechtigung zum Ausführen von Anwendungsaufgaben im Azure-Mandanten</span><span class="sxs-lookup"><span data-stu-id="8d063-114">The end user to grant permission to the app to perform applications tasks for their Azure tenant.</span></span>

<span data-ttu-id="8d063-115">Inhalt dieses Artikels</span><span class="sxs-lookup"><span data-stu-id="8d063-115">This article:</span></span>

- <span data-ttu-id="8d063-116">Erläuterung der Registrierung einer Anwendung mit Zugriff auf die Graph-API und relevante Berechtigungsrollen</span><span class="sxs-lookup"><span data-stu-id="8d063-116">Shows how to register an application with access to the Graph API and relevant permission roles.</span></span>

- <span data-ttu-id="8d063-117">Beschreiben der Intune Graph-API-Berechtigungsrollen</span><span class="sxs-lookup"><span data-stu-id="8d063-117">Describes the Intune Graph API permission roles.</span></span>

- <span data-ttu-id="8d063-118">Bereitstellen von Beispielen der Intune Graph-API-Authentifizierung für C# und PowerShell</span><span class="sxs-lookup"><span data-stu-id="8d063-118">Provides Intune Graph API authentication examples for C# and PowerShell.</span></span>

- <span data-ttu-id="8d063-119">Beschreiben der Unterstützung mehrerer Mandanten</span><span class="sxs-lookup"><span data-stu-id="8d063-119">Describes how to support multiple tenants</span></span>

<span data-ttu-id="8d063-120">Weitere Informationen finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="8d063-120">To learn more, see:</span></span>

- [<span data-ttu-id="8d063-121">Autorisieren des Zugriffs auf Webanwendungen mit OAuth 2.0 und Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="8d063-121">Authorize access to web applications using OAuth 2.0 and Azure Active Directory</span></span>](https://docs.microsoft.com/azure/active-directory/develop/active-directory-protocols-oauth-code)
- [<span data-ttu-id="8d063-122">Erste Schritte mit der Azure AD-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="8d063-122">Getting start with Azure AD authentication</span></span>](https://www.visualstudio.com/docs/integrate/get-started/auth/oauth)
- [<span data-ttu-id="8d063-123">Integrieren von Anwendungen in Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="8d063-123">Integrating applications with Azure Active Directory</span></span>](https://docs.microsoft.com/azure/active-directory/develop/active-directory-integrating-applications)
- [<span data-ttu-id="8d063-124">Grundlegendes zu OAuth 2.0</span><span class="sxs-lookup"><span data-stu-id="8d063-124">Understand OAuth 2.0</span></span>](https://oauth.net/2/)

## <a name="register-apps-to-use-graph-api"></a><span data-ttu-id="8d063-125">Registrieren von Apps für die Verwendung der Graph-API</span><span class="sxs-lookup"><span data-stu-id="8d063-125">Register apps to use Graph API</span></span>

<span data-ttu-id="8d063-126">So registrieren Sie eine App für die Verwendung der Graph-API</span><span class="sxs-lookup"><span data-stu-id="8d063-126">To register an app to use Graph API:</span></span>

1.  <span data-ttu-id="8d063-127">Melden Sie sich beim [Azure-Portal](https://portal.azure.com) mit Administratoranmeldeinformationen an.</span><span class="sxs-lookup"><span data-stu-id="8d063-127">Sign into [the Azure portal](https://portal.azure.com) using administrative credentials.</span></span>

    <span data-ttu-id="8d063-128">Dazu können Sie Folgendes verwenden:</span><span class="sxs-lookup"><span data-stu-id="8d063-128">As appropriate, you may use:</span></span>
    - <span data-ttu-id="8d063-129">Die Administratorkonto des Mandanten</span><span class="sxs-lookup"><span data-stu-id="8d063-129">The tenant admin account.</span></span>
    - <span data-ttu-id="8d063-130">Ein Mandantenbenutzerkonto mit aktivierter Einstellung **Benutzer können Anwendungen registrieren**</span><span class="sxs-lookup"><span data-stu-id="8d063-130">A tenant user account with the **Users can register applications** setting enabled.</span></span>

2.  <span data-ttu-id="8d063-131">Wählen Sie im Menü **Azure Active Directory** &gt; **App-Registrierungen** aus.</span><span class="sxs-lookup"><span data-stu-id="8d063-131">From the menu, choose **Azure Active Directory** &gt; **App Registrations**.</span></span>

    <img src="./media/azure-ad-app-reg.png" width="157" height="170" alt="The App registrations menu command" />

3.  <span data-ttu-id="8d063-132">Wählen Sie entweder **Neue Anwendungsregistrierung**, um eine neue Anwendung erstellen, oder eine vorhandene Anwendung.</span><span class="sxs-lookup"><span data-stu-id="8d063-132">Either choose **New application registration** to create a new application or choose an existing application.</span></span>  <span data-ttu-id="8d063-133">(Wenn Sie eine vorhandene Anwendung wählen, überspringen Sie den nächsten Schritt.)</span><span class="sxs-lookup"><span data-stu-id="8d063-133">(If you choose an existing application, skip the next step.)</span></span>

4.  <span data-ttu-id="8d063-134">Geben Sie auf dem Blatt **Erstellen** Folgendes an:</span><span class="sxs-lookup"><span data-stu-id="8d063-134">On the **Create** blade, specify the following:</span></span>

    1.  <span data-ttu-id="8d063-135">Einen **Namen** für die Anwendung (der angezeigt wird, wenn Benutzer sich anmelden).</span><span class="sxs-lookup"><span data-stu-id="8d063-135">A **Name** for the application (displayed when users sign in).</span></span>

    2.  <span data-ttu-id="8d063-136">Werte für **Anwendungstyp** und **Umleitungs-URI**.</span><span class="sxs-lookup"><span data-stu-id="8d063-136">The **Application type** and **Redirect URI** values.</span></span>

        <span data-ttu-id="8d063-137">Diese unterscheiden sich entsprechend Ihren Anforderungen.</span><span class="sxs-lookup"><span data-stu-id="8d063-137">These vary according to your requirements.</span></span> <span data-ttu-id="8d063-138">Wenn Sie beispielsweise eine Azure AD-[Authentifizierungsbibliothek](https://docs.microsoft.com/azure/active-directory/develop/active-directory-authentication-libraries) (ADAL) verwenden, legen Sie **Anwendungstyp** auf `Native` und **Umleitungs-URI** auf `urn:ietf:wg:oauth:2.0:oob` fest.</span><span class="sxs-lookup"><span data-stu-id="8d063-138">For example, if you're using an Azure AD [Authentication Library](https://docs.microsoft.com/azure/active-directory/develop/active-directory-authentication-libraries) (ADAL), set **Application Type** to `Native` and **Redirect URI** to `urn:ietf:wg:oauth:2.0:oob`.</span></span>

        <img src="media/azure-ad-app-new.png" width="209" height="140" alt="New app properties and values" />

        <span data-ttu-id="8d063-139">Weitere Informationen finden Sie unter [Authentifizierungsszenarien für Azure AD](https://docs.microsoft.com/azure/active-directory/develop/active-directory-authentication-scenarios).</span><span class="sxs-lookup"><span data-stu-id="8d063-139">To learn more, see [Authentication Scenarios for Azure AD](https://docs.microsoft.com/azure/active-directory/develop/active-directory-authentication-scenarios).</span></span>

5.  <span data-ttu-id="8d063-140">Auf dem Blatt „Anwendung“:</span><span class="sxs-lookup"><span data-stu-id="8d063-140">From the application blade:</span></span>

    1.  <span data-ttu-id="8d063-141">Notieren Sie sich den Wert von **Anwendungs-ID**.</span><span class="sxs-lookup"><span data-stu-id="8d063-141">Note the **Application ID** value.</span></span>

    2.  <span data-ttu-id="8d063-142">Wählen Sie **Einstellungen** &gt; **API-Zugriff** &gt; **Erforderliche Berechtigungen**.</span><span class="sxs-lookup"><span data-stu-id="8d063-142">Choose **Settings** &gt; **API access** &gt; **Required permissions**.</span></span>

    <img src="media/azure-ad-req-perm.png" width="483" height="186" alt="The Required permissions setting" />

6.  <span data-ttu-id="8d063-143">Wählen Sie auf dem Blatt **Erforderliche Berechtigungen** nacheinander **Hinzufügen** &gt; **API-Zugriff hinzufügen** &gt; **API auswählen**.</span><span class="sxs-lookup"><span data-stu-id="8d063-143">From the **Required Permissions** blade, choose **Add** &gt; **Add API access** &gt; **Select an API**.</span></span>

    <img src="media/azure-ad-add-graph.png" width="436" height="140" alt="The Microsoft Graph setting" />

7.  <span data-ttu-id="8d063-144">Wählen Sie auf dem Blatt **API auswählen** nacheinander **Microsoft Graph** &gt; **Auswählen**.</span><span class="sxs-lookup"><span data-stu-id="8d063-144">From the **Select an API** blade, choose **Microsoft Graph** &gt; **Select**.</span></span>  <span data-ttu-id="8d063-145">Das Blatt **Zugriff aktivieren** wird geöffnet, auf dem die für Ihre Anwendung verfügbaren Berechtigungsbereiche aufgeführt sind.</span><span class="sxs-lookup"><span data-stu-id="8d063-145">The **Enable access** blade opens and lists permission scopes available to your application.</span></span>

    <img src="media/azure-ad-perm-scopes.png" width="489" height="248" alt="Intune Graph API permission scopes" />

    <span data-ttu-id="8d063-146">Wählen Sie die für Ihre App erforderlichen Rollen, indem Sie ein Häkchen links neben den gewünschten Namen setzen.</span><span class="sxs-lookup"><span data-stu-id="8d063-146">Choose the roles required for your app by placing a checkmark to the left of the relevant names.</span></span>  <span data-ttu-id="8d063-147">Weitere Informationen zu bestimmten Berechtigungsbereichen in Intune finden Sie unter [Intune-Berechtigungsbereiche](#user-content-intune-permission-scopes).</span><span class="sxs-lookup"><span data-stu-id="8d063-147">To learn about specific Intune permission scopes, see [Intune permission scopes](#user-content-intune-permission-scopes).</span></span>  <span data-ttu-id="8d063-148">Weitere Informationen zu anderen Berechtigungsbereichen für die Graph-API finden Sie in der [Microsoft Graph-Berechtigungsreferenz](https://developer.microsoft.com/graph/docs/concepts/permissions_reference).</span><span class="sxs-lookup"><span data-stu-id="8d063-148">To learn about other Graph API permission scopes, see [Microsoft Graph permissions reference](https://developer.microsoft.com/graph/docs/concepts/permissions_reference).</span></span>

    <span data-ttu-id="8d063-149">Wählen Sie für optimale Ergebnisse nur so viele Rollen, wie für die Implementierung Ihrer Anwendung erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="8d063-149">For best results, choose the fewest roles needed to implement your application.</span></span>

    <span data-ttu-id="8d063-150">Klicken Sie abschließend auf **Auswählen** und **Fertig**, um Ihre Änderungen zu speichern.</span><span class="sxs-lookup"><span data-stu-id="8d063-150">When finished, choose **Select** and **Done** to save you changes.</span></span>

<span data-ttu-id="8d063-151">An diesem Punkt haben Sie auch folgende Möglichkeiten:</span><span class="sxs-lookup"><span data-stu-id="8d063-151">At this point, you may also:</span></span>

- <span data-ttu-id="8d063-152">Sie können allen Mandantenkonten die Berechtigung zum Verwenden der App ohne Angabe von Anmeldeinformationen erteilen.</span><span class="sxs-lookup"><span data-stu-id="8d063-152">Choose to grant permission for all tenant accounts to use the app without providing credentials.</span></span>  

    <span data-ttu-id="8d063-153">Zu diesem Zweck wählen Sie **Berechtigungen** und akzeptieren die Bestätigungsaufforderung.</span><span class="sxs-lookup"><span data-stu-id="8d063-153">To do so, choose **Grant permissions** and accept the confirmation prompt.</span></span>

    <span data-ttu-id="8d063-154">Wenn Sie die Anwendung zum ersten Mal ausführen, werden Sie aufgefordert, die App-Berechtigung für die ausgewählten Rollen zu erteilen.</span><span class="sxs-lookup"><span data-stu-id="8d063-154">When you run the application for the first time, you're prompted to grant the app permission to perform the selected roles.</span></span>

    <img src="media/azure-ad-grant-perm.png" width="351" height="162" alt="The Grant permissions button" />

- <span data-ttu-id="8d063-155">Sie können die App Benutzern außerhalb Ihres Mandanten zur Verfügung stellen.</span><span class="sxs-lookup"><span data-stu-id="8d063-155">Make the app available to users outside your tenant.</span></span>  <span data-ttu-id="8d063-156">(Dies ist normalerweise nur für Partner erforderlich, die mehrere Mandanten/Organisationen unterstützen.)</span><span class="sxs-lookup"><span data-stu-id="8d063-156">(This is typically only required for partners supporting multiple tenants/organizations.)</span></span>  

    <span data-ttu-id="8d063-157">Gehen Sie hierzu folgendermaßen vor:</span><span class="sxs-lookup"><span data-stu-id="8d063-157">To do so:</span></span>

    1. <span data-ttu-id="8d063-158">Wählen sie auf dem Blatt der Anwendung **Manifest**, um das Blatt **Manifest bearbeiten** zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="8d063-158">Choose **Manifest** from the application blade, which opens the **Edit Manifest** blade.</span></span>

    <img src="media/azure-ad-edit-mft.png" width="295" height="114" alt="The Edit manifest blade" />

    2. <span data-ttu-id="8d063-159">Ändern Sie den Wert der Einstellung `availableToOtherTenants` in `true`.</span><span class="sxs-lookup"><span data-stu-id="8d063-159">Change the value of the `availableToOtherTenants` setting to `true`.</span></span>

    3. <span data-ttu-id="8d063-160">Speichern Sie die Änderungen.</span><span class="sxs-lookup"><span data-stu-id="8d063-160">Save your changes.</span></span>

## <a name="intune-permission-scopes"></a><span data-ttu-id="8d063-161">Intune-Berechtigungsbereiche</span><span class="sxs-lookup"><span data-stu-id="8d063-161">Intune permission scopes</span></span>

<span data-ttu-id="8d063-162">Azure AD und die Graph-API nutzen Berechtigungsbereiche zum Steuern des Zugriffs auf Unternehmensressourcen.</span><span class="sxs-lookup"><span data-stu-id="8d063-162">Azure AD and the Graph API use permission scopes to control access to corporate resources.</span></span>  

<span data-ttu-id="8d063-163">Berechtigungsbereiche (auch _OAuth-Bereiche_ genannt) steuern den Zugriff auf bestimmte Intune-Entitäten und deren Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="8d063-163">Permission scopes (also called the _OAuth scopes_) control access to specific Intune entities and their properties.</span></span> <span data-ttu-id="8d063-164">In diesem Abschnitt werden die Berechtigungsbereiche für Intune Graph-API-Funktionen zusammengefasst.</span><span class="sxs-lookup"><span data-stu-id="8d063-164">This section summarizes the permission scopes for Intune Graph API features.</span></span>

<span data-ttu-id="8d063-165">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="8d063-165">To learn more:</span></span>
- [<span data-ttu-id="8d063-166">Azure AD-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="8d063-166">Azure AD authentication</span></span>](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-pass-through-authentication)
- [<span data-ttu-id="8d063-167">Anwendungsberechtigungsbereiche</span><span class="sxs-lookup"><span data-stu-id="8d063-167">Application permission scopes</span></span>](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-scopes)

<span data-ttu-id="8d063-168">Wenn Sie der Graph-API Berechtigung erteilen, können Sie angeben, dass die folgenden Bereiche den Zugriff auf die Intune-Funktionen steuern sollen. In der folgenden Tabelle werden die Intune Graph-API-Berechtigungsbereiche zusammengefasst.</span><span class="sxs-lookup"><span data-stu-id="8d063-168">When you grant permission to the Graph API, you can specify the following scopes to control access to Intune features: The following table summarizes the Intune Graph API permission scopes.</span></span>  <span data-ttu-id="8d063-169">Die erste Spalte enthält den Namen der Funktion entsprechend der Anzeige im Azure-Portal, die zweite den Namen des Berechtigungsbereichs.</span><span class="sxs-lookup"><span data-stu-id="8d063-169">The first column shows the name of the feature as displayed in the Azure portal and the second column provides the permission scope name.</span></span>

<span data-ttu-id="8d063-170">Einstellung _Zugriff aktivieren_</span><span class="sxs-lookup"><span data-stu-id="8d063-170">_Enable Access_ setting</span></span> | <span data-ttu-id="8d063-171">Bereichsname</span><span class="sxs-lookup"><span data-stu-id="8d063-171">Scope name</span></span>
:--|:--
<span data-ttu-id="8d063-172">__Remoteaktionen mit Auswirkungen auf Benutzer auf Microsoft Intune-Geräten ausführen__</span><span class="sxs-lookup"><span data-stu-id="8d063-172">__Perform user-impacting remote actions on Microsoft Intune devices__</span></span> | [<span data-ttu-id="8d063-173">DeviceManagementManagedDevices.PrivilegedOperations.All</span><span class="sxs-lookup"><span data-stu-id="8d063-173">DeviceManagementManagedDevices.PrivilegedOperations.All</span></span>](#user-content-mgd-po)
<span data-ttu-id="8d063-174">__Microsoft Intune-Geräte lesen und schreiben__</span><span class="sxs-lookup"><span data-stu-id="8d063-174">__Read and write Microsoft Intune devices__</span></span> | [<span data-ttu-id="8d063-175">DeviceManagementManagedDevices.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="8d063-175">DeviceManagementManagedDevices.ReadWrite.All</span></span>](#mgd-rw)
<span data-ttu-id="8d063-176">__Microsoft Intune-Geräte lesen__</span><span class="sxs-lookup"><span data-stu-id="8d063-176">__Read Microsoft Intune devices__</span></span> | [<span data-ttu-id="8d063-177">DeviceManagementManagedDevices.Read.All</span><span class="sxs-lookup"><span data-stu-id="8d063-177">DeviceManagementManagedDevices.Read.All</span></span>](#mgd-ro)
<span data-ttu-id="8d063-178">__Einstellungen für die rollenbasierte Zugriffssteuerung von Microsoft Intune-Geräten lesen und schreiben__</span><span class="sxs-lookup"><span data-stu-id="8d063-178">__Read and write Microsoft Intune RBAC settings__</span></span> | [<span data-ttu-id="8d063-179">DeviceManagementRBAC.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="8d063-179">DeviceManagementRBAC.ReadWrite.All</span></span>](#rac-rw)
<span data-ttu-id="8d063-180">__Einstellungen für die rollenbasierte Zugriffssteuerung von Microsoft Intune-Geräten lesen__</span><span class="sxs-lookup"><span data-stu-id="8d063-180">__Read Microsoft Intune RBAC settings__</span></span> | [<span data-ttu-id="8d063-181">DeviceManagementRBAC.Read.All</span><span class="sxs-lookup"><span data-stu-id="8d063-181">DeviceManagementRBAC.Read.All</span></span>](#rac=ro)
<span data-ttu-id="8d063-182">__Microsoft Intune-Apps lesen und schreiben__</span><span class="sxs-lookup"><span data-stu-id="8d063-182">__Read and write Microsoft Intune apps__</span></span> | [<span data-ttu-id="8d063-183">DeviceManagementApps.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="8d063-183">DeviceManagementApps.ReadWrite.All</span></span>](#app-rw)
<span data-ttu-id="8d063-184">__Microsoft Intune-Apps lesen__</span><span class="sxs-lookup"><span data-stu-id="8d063-184">__Read Microsoft Intune apps__</span></span> | [<span data-ttu-id="8d063-185">DeviceManagementApps.Read.All</span><span class="sxs-lookup"><span data-stu-id="8d063-185">DeviceManagementApps.Read.All</span></span>](#app-ro)
<span data-ttu-id="8d063-186">__Microsoft Intune-Gerätekonfiguration und -Richtlinien lesen und schreiben__</span><span class="sxs-lookup"><span data-stu-id="8d063-186">__Read and write Microsoft Intune Device Configuration and Policies__</span></span> | [<span data-ttu-id="8d063-187">DeviceManagementConfiguration.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="8d063-187">DeviceManagementConfiguration.ReadWrite.All</span></span>](#cfg-rw)
<span data-ttu-id="8d063-188">__Microsoft Intune-Gerätekonfiguration und -Richtlinien lesen__</span><span class="sxs-lookup"><span data-stu-id="8d063-188">__Read Microsoft Intune Device Configuration and Policies__</span></span> | [<span data-ttu-id="8d063-189">DeviceManagementConfiguration.Read.All</span><span class="sxs-lookup"><span data-stu-id="8d063-189">DeviceManagementConfiguration.Read.All</span></span>](#cfg-ro)
<span data-ttu-id="8d063-190">__Microsoft Intune-Konfiguration lesen und schreiben__</span><span class="sxs-lookup"><span data-stu-id="8d063-190">__Read and write Microsoft Intune configuration__</span></span> | [<span data-ttu-id="8d063-191">DeviceManagementServiceConfig.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="8d063-191">DeviceManagementServiceConfig.ReadWrite.All</span></span>](#svc-rw)
<span data-ttu-id="8d063-192">__Microsoft Intune-Konfiguration lesen__</span><span class="sxs-lookup"><span data-stu-id="8d063-192">__Read Microsoft Intune configuration__</span></span> | [<span data-ttu-id="8d063-193">DeviceManagementServiceConfig.Read.All</span><span class="sxs-lookup"><span data-stu-id="8d063-193">DeviceManagementServiceConfig.Read.All</span></span>](#svc-ra)

<span data-ttu-id="8d063-194">Die Tabelle enthält die Einstellungen in der Reihenfolge, in der sie im Azure-Portal angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="8d063-194">The table lists the settings as they appear in the Azure portal.</span></span> <span data-ttu-id="8d063-195">In den folgenden Abschnitten werden die Bereiche in alphabetischer Reihenfolge beschrieben.</span><span class="sxs-lookup"><span data-stu-id="8d063-195">The following sections describe the scopes in alphabetical order.</span></span>

<span data-ttu-id="8d063-196">Derzeit erfordern alle Intune-Berechtigungsbereiche Administratorzugriff.</span><span class="sxs-lookup"><span data-stu-id="8d063-196">At this time, all Intune permission scopes require administrator access.</span></span>  <span data-ttu-id="8d063-197">Dies bedeutet, dass Sie zum Ausführen von Apps oder Skripts, die auf Intune Graph-API-Ressourcen zugreifen, entsprechende Anmeldeinformationen benötigen.</span><span class="sxs-lookup"><span data-stu-id="8d063-197">This means you need corresponding credentials when running apps or scripts that access Intune Graph API resources.</span></span>

### <a name="app-ro"></a><span data-ttu-id="8d063-198">DeviceManagementApps.Read.All</span><span class="sxs-lookup"><span data-stu-id="8d063-198">DeviceManagementApps.Read.All</span></span>

- <span data-ttu-id="8d063-199">Einstellung **Zugriff aktivieren**: __Microsoft Intune-Apps lesen__</span><span class="sxs-lookup"><span data-stu-id="8d063-199">**Enable Access** setting: __Read Microsoft Intune apps__</span></span>

- <span data-ttu-id="8d063-200">Ermöglicht Lesezugriff auf die folgenden Eigenschaften und den Status der Entität:</span><span class="sxs-lookup"><span data-stu-id="8d063-200">Permits read access to the following entity properties and status:</span></span>
    - <span data-ttu-id="8d063-201">Mobile Apps</span><span class="sxs-lookup"><span data-stu-id="8d063-201">Mobile Apps</span></span>
    - <span data-ttu-id="8d063-202">Kategorien mobiler Apps</span><span class="sxs-lookup"><span data-stu-id="8d063-202">Mobile App Categories</span></span>
    - <span data-ttu-id="8d063-203">App-Schutzrichtlinien</span><span class="sxs-lookup"><span data-stu-id="8d063-203">App Protection Policies</span></span>
    - <span data-ttu-id="8d063-204">App-Konfigurationen</span><span class="sxs-lookup"><span data-stu-id="8d063-204">App Configurations</span></span>

### <a name="app-rw"></a><span data-ttu-id="8d063-205">DeviceManagementApps.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="8d063-205">DeviceManagementApps.ReadWrite.All</span></span>

- <span data-ttu-id="8d063-206">Einstellung **Zugriff aktivieren**: __Microsoft Intune-Apps lesen und schreiben__</span><span class="sxs-lookup"><span data-stu-id="8d063-206">**Enable Access** setting: __Read and write Microsoft Intune apps__</span></span>

- <span data-ttu-id="8d063-207">Ermöglicht die gleichen Vorgänge wie __DeviceManagementApps.Read.All__</span><span class="sxs-lookup"><span data-stu-id="8d063-207">Allows the same operations as __DeviceManagementApps.Read.All__</span></span>

- <span data-ttu-id="8d063-208">Ermöglicht zudem Änderungen an den folgenden Entitäten:</span><span class="sxs-lookup"><span data-stu-id="8d063-208">Also permits changes to the following entities:</span></span>

    - <span data-ttu-id="8d063-209">Mobile Apps</span><span class="sxs-lookup"><span data-stu-id="8d063-209">Mobile Apps</span></span>
    - <span data-ttu-id="8d063-210">Kategorien mobiler Apps</span><span class="sxs-lookup"><span data-stu-id="8d063-210">Mobile App Categories</span></span>
    - <span data-ttu-id="8d063-211">App-Schutzrichtlinien</span><span class="sxs-lookup"><span data-stu-id="8d063-211">App Protection Policies</span></span>
    - <span data-ttu-id="8d063-212">App-Konfigurationen</span><span class="sxs-lookup"><span data-stu-id="8d063-212">App Configurations</span></span>

### <a name="cfg-ro"></a><span data-ttu-id="8d063-213">DeviceManagementConfiguration.Read.All</span><span class="sxs-lookup"><span data-stu-id="8d063-213">DeviceManagementConfiguration.Read.All</span></span>

- <span data-ttu-id="8d063-214">Einstellung **Zugriff aktivieren**: __Microsoft Intune-Gerätekonfiguration und -Richtlinien lesen__</span><span class="sxs-lookup"><span data-stu-id="8d063-214">**Enable Access** setting: __Read Microsoft Intune device configuration and policies__</span></span>

- <span data-ttu-id="8d063-215">Ermöglicht Lesezugriff auf die folgenden Eigenschaften und den Status der Entität:</span><span class="sxs-lookup"><span data-stu-id="8d063-215">Permits read access to the following entity properties and status:</span></span>
    - <span data-ttu-id="8d063-216">Gerätekonfiguration</span><span class="sxs-lookup"><span data-stu-id="8d063-216">Device Configuration</span></span>
    - <span data-ttu-id="8d063-217">Gerätekonformitätsrichtlinie</span><span class="sxs-lookup"><span data-stu-id="8d063-217">Device Compliance Policy</span></span>
    - <span data-ttu-id="8d063-218">Benachrichtigungen</span><span class="sxs-lookup"><span data-stu-id="8d063-218">Notification Messages</span></span>

### <a name="cfg-ra"></a><span data-ttu-id="8d063-219">DeviceManagementConfiguration.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="8d063-219">DeviceManagementConfiguration.ReadWrite.All</span></span>

- <span data-ttu-id="8d063-220">Einstellung **Zugriff aktivieren**: __Microsoft Intune-Gerätekonfiguration und -Richtlinien lesen und schreiben__</span><span class="sxs-lookup"><span data-stu-id="8d063-220">**Enable Access** setting: __Read and write Microsoft Intune device configuration and policies__</span></span>

- <span data-ttu-id="8d063-221">Ermöglicht die gleichen Vorgänge wie __DeviceManagementConfiguration.Read.All__</span><span class="sxs-lookup"><span data-stu-id="8d063-221">Allows the same operations as __DeviceManagementConfiguration.Read.All__</span></span>

- <span data-ttu-id="8d063-222">Apps können auch die folgenden Entitäten erstellen, zuweisen, löschen und ändern:</span><span class="sxs-lookup"><span data-stu-id="8d063-222">Apps can also create, assign, delete, and change the following entities:</span></span>
    - <span data-ttu-id="8d063-223">Gerätekonfiguration</span><span class="sxs-lookup"><span data-stu-id="8d063-223">Device Configuration</span></span>
    - <span data-ttu-id="8d063-224">Gerätekonformitätsrichtlinie</span><span class="sxs-lookup"><span data-stu-id="8d063-224">Device Compliance Policy</span></span>
    - <span data-ttu-id="8d063-225">Benachrichtigungen</span><span class="sxs-lookup"><span data-stu-id="8d063-225">Notification Messages</span></span>

### <a name="mgd-po"></a><span data-ttu-id="8d063-226">DeviceManagementManagedDevices.PrivilegedOperations.All</span><span class="sxs-lookup"><span data-stu-id="8d063-226">DeviceManagementManagedDevices.PrivilegedOperations.All</span></span>

- <span data-ttu-id="8d063-227">Einstellung **Zugriff aktivieren**: __Remoteaktionen mit Auswirkungen auf Benutzer auf Microsoft Intune-Geräten ausführen__</span><span class="sxs-lookup"><span data-stu-id="8d063-227">**Enable Access** setting: __Perform user-impacting remote actions on Microsoft Intune devices__</span></span>

- <span data-ttu-id="8d063-228">Erlaubt die folgenden Remoteaktionen auf einem verwalteten Gerät:</span><span class="sxs-lookup"><span data-stu-id="8d063-228">Permits the following remote actions on a managed device:</span></span>
    - <span data-ttu-id="8d063-229">Außerkraftsetzen</span><span class="sxs-lookup"><span data-stu-id="8d063-229">Retire</span></span>
    - <span data-ttu-id="8d063-230">Zurücksetzen</span><span class="sxs-lookup"><span data-stu-id="8d063-230">Wipe</span></span>
    - <span data-ttu-id="8d063-231">Kennung zurücksetzen/wiederherstellen</span><span class="sxs-lookup"><span data-stu-id="8d063-231">Reset/Recover Passcode</span></span>
    - <span data-ttu-id="8d063-232">Remotesperre</span><span class="sxs-lookup"><span data-stu-id="8d063-232">Remote Lock</span></span>
    - <span data-ttu-id="8d063-233">Modus für verlorene Geräte aktivieren/deaktivieren</span><span class="sxs-lookup"><span data-stu-id="8d063-233">Enable/Disable Lost Mode</span></span>
    - <span data-ttu-id="8d063-234">PC bereinigen</span><span class="sxs-lookup"><span data-stu-id="8d063-234">Clean PC</span></span>
    - <span data-ttu-id="8d063-235">Neustart</span><span class="sxs-lookup"><span data-stu-id="8d063-235">Reboot</span></span>
    - <span data-ttu-id="8d063-236">Benutzer von gemeinsam genutzten Gerät löschen</span><span class="sxs-lookup"><span data-stu-id="8d063-236">Delete User from Shared Device</span></span>

### <a name="mgd-ro"></a><span data-ttu-id="8d063-237">DeviceManagementManagedDevices.Read.All</span><span class="sxs-lookup"><span data-stu-id="8d063-237">DeviceManagementManagedDevices.Read.All</span></span>

- <span data-ttu-id="8d063-238">Einstellung **Zugriff aktivieren**: __Microsoft Intune-Geräte lesen__</span><span class="sxs-lookup"><span data-stu-id="8d063-238">**Enable Access** setting: __Read Microsoft Intune devices__</span></span>

- <span data-ttu-id="8d063-239">Ermöglicht Lesezugriff auf die folgenden Eigenschaften und den Status der Entität:</span><span class="sxs-lookup"><span data-stu-id="8d063-239">Permits read access to the following entity properties and status:</span></span>
    - <span data-ttu-id="8d063-240">Verwaltetes Gerät</span><span class="sxs-lookup"><span data-stu-id="8d063-240">Managed Device</span></span>
    - <span data-ttu-id="8d063-241">Gerätekategorie</span><span class="sxs-lookup"><span data-stu-id="8d063-241">Device Category</span></span>
    - <span data-ttu-id="8d063-242">Erkannte App</span><span class="sxs-lookup"><span data-stu-id="8d063-242">Detected App</span></span>
    - <span data-ttu-id="8d063-243">Remoteaktionen</span><span class="sxs-lookup"><span data-stu-id="8d063-243">Remote actions</span></span>
    - <span data-ttu-id="8d063-244">Informationen zu Schadsoftware</span><span class="sxs-lookup"><span data-stu-id="8d063-244">Malware information</span></span>

### <a name="mgd-rw"></a><span data-ttu-id="8d063-245">DeviceManagementManagedDevices.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="8d063-245">DeviceManagementManagedDevices.ReadWrite.All</span></span>

- <span data-ttu-id="8d063-246">Einstellung **Zugriff aktivieren**: __Microsoft Intune-Geräte lesen und schreiben__</span><span class="sxs-lookup"><span data-stu-id="8d063-246">**Enable Access** setting: __Read and write Microsoft Intune devices__</span></span>

- <span data-ttu-id="8d063-247">Ermöglicht die gleichen Vorgänge wie __DeviceManagementManagedDevices.Read.All__</span><span class="sxs-lookup"><span data-stu-id="8d063-247">Allows the same operations as __DeviceManagementManagedDevices.Read.All__</span></span>

- <span data-ttu-id="8d063-248">Apps können auch die folgenden Entitäten erstellen, löschen und ändern:</span><span class="sxs-lookup"><span data-stu-id="8d063-248">Apps can also create, delete, and change the following entities:</span></span>
    - <span data-ttu-id="8d063-249">Verwaltetes Gerät</span><span class="sxs-lookup"><span data-stu-id="8d063-249">Managed Device</span></span>
    - <span data-ttu-id="8d063-250">Gerätekategorie</span><span class="sxs-lookup"><span data-stu-id="8d063-250">Device Category</span></span>

- <span data-ttu-id="8d063-251">Die folgenden Remoteaktionen sind ebenfalls zulässig:</span><span class="sxs-lookup"><span data-stu-id="8d063-251">The following remote actions are also allowed:</span></span>
    - <span data-ttu-id="8d063-252">Geräte suchen</span><span class="sxs-lookup"><span data-stu-id="8d063-252">Locate devices</span></span>
    - <span data-ttu-id="8d063-253">Aktivierungssperre umgehen</span><span class="sxs-lookup"><span data-stu-id="8d063-253">Bypass activation lock</span></span>
    - <span data-ttu-id="8d063-254">Remoteunterstützung anfordern</span><span class="sxs-lookup"><span data-stu-id="8d063-254">Request remote assistance</span></span>

### <a name="rac-ro"></a><span data-ttu-id="8d063-255">DeviceManagementRBAC.Read.All</span><span class="sxs-lookup"><span data-stu-id="8d063-255">DeviceManagementRBAC.Read.All</span></span>

- <span data-ttu-id="8d063-256">Einstellung **Zugriff aktivieren**: __Einstellungen für die rollenbasierte Zugriffssteuerung von Microsoft Intune-Geräten lesen__</span><span class="sxs-lookup"><span data-stu-id="8d063-256">**Enable Access** setting: __Read Microsoft Intune RBAC settings__</span></span>

- <span data-ttu-id="8d063-257">Ermöglicht Lesezugriff auf die folgenden Eigenschaften und den Status der Entität:</span><span class="sxs-lookup"><span data-stu-id="8d063-257">Permits read access to the following entity properties and status:</span></span>
    - <span data-ttu-id="8d063-258">Rollenzuweisungen</span><span class="sxs-lookup"><span data-stu-id="8d063-258">Role Assignments</span></span>
    - <span data-ttu-id="8d063-259">Rollendefinitionen</span><span class="sxs-lookup"><span data-stu-id="8d063-259">Role Definitions</span></span>
    - <span data-ttu-id="8d063-260">Ressourcenvorgänge</span><span class="sxs-lookup"><span data-stu-id="8d063-260">Resource Operations</span></span>

### <a name="rac-rw"></a><span data-ttu-id="8d063-261">DeviceManagementRBAC.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="8d063-261">DeviceManagementRBAC.ReadWrite.All</span></span>

- <span data-ttu-id="8d063-262">Einstellung **Zugriff aktivieren**: __Einstellungen für die rollenbasierte Zugriffssteuerung von Microsoft Intune-Geräten lesen und schreiben__</span><span class="sxs-lookup"><span data-stu-id="8d063-262">**Enable Access** setting: __Read and write Microsoft Intune RBAC settings__</span></span>

- <span data-ttu-id="8d063-263">Ermöglicht die gleichen Vorgänge wie __DeviceManagementRBAC.Read.All__</span><span class="sxs-lookup"><span data-stu-id="8d063-263">Allows the same operations as __DeviceManagementRBAC.Read.All__</span></span>

- <span data-ttu-id="8d063-264">Apps können auch die folgenden Entitäten erstellen, zuweisen, löschen und ändern:</span><span class="sxs-lookup"><span data-stu-id="8d063-264">Apps can also create, assign, delete, and change the following entities:</span></span>
    - <span data-ttu-id="8d063-265">Rollenzuweisungen</span><span class="sxs-lookup"><span data-stu-id="8d063-265">Role Assignments</span></span>
    - <span data-ttu-id="8d063-266">Rollendefinitionen</span><span class="sxs-lookup"><span data-stu-id="8d063-266">Role Definitions</span></span>

### <a name="svc-ro"></a><span data-ttu-id="8d063-267">DeviceManagementServiceConfig.Read.All</span><span class="sxs-lookup"><span data-stu-id="8d063-267">DeviceManagementServiceConfig.Read.All</span></span>

- <span data-ttu-id="8d063-268">Einstellung **Zugriff aktivieren**: __Microsoft Intune-Konfiguration lesen__</span><span class="sxs-lookup"><span data-stu-id="8d063-268">**Enable Access** setting: __Read Microsoft Intune configuration__</span></span>

- <span data-ttu-id="8d063-269">Ermöglicht Lesezugriff auf die folgenden Eigenschaften und den Status der Entität:</span><span class="sxs-lookup"><span data-stu-id="8d063-269">Permits read access to the following entity properties and status:</span></span>
    - <span data-ttu-id="8d063-270">Geräteregistrierung</span><span class="sxs-lookup"><span data-stu-id="8d063-270">Device Enrollment</span></span>
    - <span data-ttu-id="8d063-271">Apple Push Notification-Zertifikat</span><span class="sxs-lookup"><span data-stu-id="8d063-271">Apple Push Notification Certificate</span></span>
    - <span data-ttu-id="8d063-272">Apple-Programm zur Geräteregistrierung</span><span class="sxs-lookup"><span data-stu-id="8d063-272">Apple Device Enrollment Program</span></span>
    - <span data-ttu-id="8d063-273">Apple Volume Purchase Program</span><span class="sxs-lookup"><span data-stu-id="8d063-273">Apple Volume Purchase Program</span></span>
    - <span data-ttu-id="8d063-274">Exchange-Connector</span><span class="sxs-lookup"><span data-stu-id="8d063-274">Exchange Connector</span></span>
    - <span data-ttu-id="8d063-275">Geschäftsbedingungen</span><span class="sxs-lookup"><span data-stu-id="8d063-275">Terms and Conditions</span></span>
    - <span data-ttu-id="8d063-276">Verwaltung von Ausgaben für Telekommunikation</span><span class="sxs-lookup"><span data-stu-id="8d063-276">Telecoms Expense Management</span></span>
    - <span data-ttu-id="8d063-277">PKI in der Cloud</span><span class="sxs-lookup"><span data-stu-id="8d063-277">Cloud PKI</span></span>
    - <span data-ttu-id="8d063-278">Branding</span><span class="sxs-lookup"><span data-stu-id="8d063-278">Branding</span></span>
    - <span data-ttu-id="8d063-279">Mobile Threat Defense</span><span class="sxs-lookup"><span data-stu-id="8d063-279">Mobile Threat Defense</span></span>

### <a name="svc-rw"></a><span data-ttu-id="8d063-280">DeviceManagementServiceConfig.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="8d063-280">DeviceManagementServiceConfig.ReadWrite.All</span></span>

- <span data-ttu-id="8d063-281">Einstellung **Zugriff aktivieren**: __Microsoft Intune-Konfiguration lesen und schreiben__</span><span class="sxs-lookup"><span data-stu-id="8d063-281">**Enable Access** setting: __Read and write Microsoft Intune configuration__</span></span>

- <span data-ttu-id="8d063-282">Ermöglicht die gleichen Vorgänge wie „DeviceManagementServiceConfig.Read.All_“</span><span class="sxs-lookup"><span data-stu-id="8d063-282">Allows the same operations as DeviceManagementServiceConfig.Read.All_</span></span>

- <span data-ttu-id="8d063-283">Apps können auch die folgenden Intune-Features konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="8d063-283">Apps can also configure the following Intune features:</span></span>
    - <span data-ttu-id="8d063-284">Geräteregistrierung</span><span class="sxs-lookup"><span data-stu-id="8d063-284">Device Enrollment</span></span>
    - <span data-ttu-id="8d063-285">Apple Push Notification-Zertifikat</span><span class="sxs-lookup"><span data-stu-id="8d063-285">Apple Push Notification Certificate</span></span>
    - <span data-ttu-id="8d063-286">Apple-Programm zur Geräteregistrierung</span><span class="sxs-lookup"><span data-stu-id="8d063-286">Apple Device Enrollment Program</span></span>
    - <span data-ttu-id="8d063-287">Apple Volume Purchase Program</span><span class="sxs-lookup"><span data-stu-id="8d063-287">Apple Volume Purchase Program</span></span>
    - <span data-ttu-id="8d063-288">Exchange-Connector</span><span class="sxs-lookup"><span data-stu-id="8d063-288">Exchange Connector</span></span>
    - <span data-ttu-id="8d063-289">Geschäftsbedingungen</span><span class="sxs-lookup"><span data-stu-id="8d063-289">Terms and Conditions</span></span>
    - <span data-ttu-id="8d063-290">Verwaltung von Ausgaben für Telekommunikation</span><span class="sxs-lookup"><span data-stu-id="8d063-290">Telecoms Expense Management</span></span>
    - <span data-ttu-id="8d063-291">PKI in der Cloud</span><span class="sxs-lookup"><span data-stu-id="8d063-291">Cloud PKI</span></span>
    - <span data-ttu-id="8d063-292">Branding</span><span class="sxs-lookup"><span data-stu-id="8d063-292">Branding</span></span>
    - <span data-ttu-id="8d063-293">Mobile Threat Defense</span><span class="sxs-lookup"><span data-stu-id="8d063-293">Mobile Threat Defense</span></span>

## <a name="azure-ad-authentication-examples"></a><span data-ttu-id="8d063-294">Beispiele für die Azure AD-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="8d063-294">Azure AD authentication examples</span></span>

<span data-ttu-id="8d063-295">In diesem Abschnitt wird gezeigt, wie Azure AD in Ihre C#- und PowerShell-Projekte integriert wird.</span><span class="sxs-lookup"><span data-stu-id="8d063-295">This section shows how to incorporate Azure AD into your C# and PowerShell projects.</span></span>

<span data-ttu-id="8d063-296">Bei jedem Beispiel müssen Sie eine Anwendungs-ID angeben, die mindestens den Berechtigungsbereich `DeviceManagementManagedDevices.Read.All` hat (siehe oben).</span><span class="sxs-lookup"><span data-stu-id="8d063-296">In each example, you'll need to specify an application ID that has at least the `DeviceManagementManagedDevices.Read.All` permission scope (discussed earlier).</span></span>

<span data-ttu-id="8d063-297">Wenn Sie eines der Beispiel testen, erhalten Sie ggf. die HTTP-Statusfehlermeldung 403 (Unzulässig):</span><span class="sxs-lookup"><span data-stu-id="8d063-297">When testing either example, you may receive HTTP status 403 (Forbidden) errors similar to the following:</span></span>

``` javascript
{
  "error": {
    "code": "Forbidden",
    "message": "Application is not authorized to perform this operation - Operation ID " +
       "(for customer support): 00000000-0000-0000-0000-000000000000 - " +
       "Activity ID: cc7fa3b3-bb25-420b-bfb2-1498e598ba43 - " +
       "Url: https://example.manage.microsoft.com/" +
       "Service/Resource/RESTendpoint?" +
       "api-version=2017-03-06 - CustomApiErrorPhrase: ",
    "innerError": {
      "request-id": "00000000-0000-0000-0000-000000000000",
      "date": "1980-01-0112:00:00"
    }
  }
}
```

<span data-ttu-id="8d063-298">Wenn dies erfolgt, überprüfen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="8d063-298">If this happens, verify that:</span></span>

- <span data-ttu-id="8d063-299">Ob Sie die Anwendungs-ID in eine ID geändert haben, die für das Verwenden der Graph-API und des Berechtigungsbereichs `DeviceManagementManagedDevices.Read.All` autorisiert ist.</span><span class="sxs-lookup"><span data-stu-id="8d063-299">You've updated the application ID to one authorized to use the Graph API and the `DeviceManagementManagedDevices.Read.All` permission scope.</span></span>

- <span data-ttu-id="8d063-300">Ob die Anmeldeinformationen Ihres Mandanten administrative Funktionen unterstützen.</span><span class="sxs-lookup"><span data-stu-id="8d063-300">Your tenant credentials support administrative functions.</span></span>

- <span data-ttu-id="8d063-301">Ob Ihr Code den gezeigten Beispielen ähnlich ist.</span><span class="sxs-lookup"><span data-stu-id="8d063-301">Your code is similar to the displayed samples.</span></span>


### <a name="authenticate-azure-ad-in-c"></a><span data-ttu-id="8d063-302">Authentifizieren von Azure AD in C\#</span><span class="sxs-lookup"><span data-stu-id="8d063-302">Authenticate Azure AD in C\#</span></span>

<span data-ttu-id="8d063-303">Dieses Beispiel zeigt, wie Sie C# zum Abrufen einer Liste von Geräten verwenden, die Ihrem Intune-Konto zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="8d063-303">This example shows how to use C# to retrieve a list of devices associated with your Intune account.</span></span>

1.  <span data-ttu-id="8d063-304">Starten Sie Visual Studio, und erstellen Sie dann ein neues Visual C#-App-Konsolenprojekt (.NET Framework).</span><span class="sxs-lookup"><span data-stu-id="8d063-304">Start Visual Studio and then create a new Visual C# Console app (.NET Framework) project.</span></span>

2.  <span data-ttu-id="8d063-305">Geben Sie einen Namen für das Projekt und nach Wunsch weitere Details ein.</span><span class="sxs-lookup"><span data-stu-id="8d063-305">Enter a name for your project and provide other details as desired.</span></span>

    <img src="media/aad-auth-cpp-new-console.png" width="624" height="433" alt="Creating a C# console app project in Visual Studio"  />

3.  <span data-ttu-id="8d063-306">Fügen Sie im Projektmappen-Explorer das NuGet-Paket mit der Microsoft ADAL dem Projekt hinzu.</span><span class="sxs-lookup"><span data-stu-id="8d063-306">Use the Solution Explorer to add the Microsoft ADAL NuGet package to the project.</span></span>

    1.  <span data-ttu-id="8d063-307">Klicken Sie mit der rechten Maustaste auf den Projektmappen-Explorer.</span><span class="sxs-lookup"><span data-stu-id="8d063-307">Right-click the Solution Explorer.</span></span>
    2.  <span data-ttu-id="8d063-308">Wählen Sie **NuGet-Pakete verwalten**</span><span class="sxs-lookup"><span data-stu-id="8d063-308">Choose **Manage NuGet Packages…**</span></span> <span data-ttu-id="8d063-309">&gt; **Durchsuchen** aus.</span><span class="sxs-lookup"><span data-stu-id="8d063-309">&gt; **Browse**.</span></span>
    3.  <span data-ttu-id="8d063-310">Wählen Sie `Microsoft.IdentityModel.Clients.ActiveDirectory` aus, und klicken Sie anschließend auf **Installieren**.</span><span class="sxs-lookup"><span data-stu-id="8d063-310">Select `Microsoft.IdentityModel.Clients.ActiveDirectory` and then choose **Install**.</span></span>

    <img src="media/aad-auth-cpp-install-package.png" width="624" height="458" alt="Selecting the Azure AD identity model module" />

4.  <span data-ttu-id="8d063-311">Fügen Sie am Anfang der Datei **Program.cs** die folgenden Anweisungen ein:</span><span class="sxs-lookup"><span data-stu-id="8d063-311">Add the following statements to the top of **Program.cs**:</span></span>

    ``` csharp
    using Microsoft.IdentityModel.Clients.ActiveDirectory;</p>
    using System.Net.Http;
    ```

5.  <span data-ttu-id="8d063-312">Fügen Sie eine Methode zum Erstellen des Autorisierungsheaders hinzu:</span><span class="sxs-lookup"><span data-stu-id="8d063-312">Add a method to create the authorization header:</span></span>

    ``` csharp
    private static async Task<string> GetAuthorizationHeader()
    {
        string applicationId = "<Your Application ID>";
        string authority = "https://login.microsoftonline.com/common/";
        Uri redirectUri = new Uri("urn:ietf:wg:oauth:2.0:oob");
        AuthenticationContext context = new AuthenticationContext(authority);
        AuthenticationResult result = await context.AcquireTokenAsync(
            "https://graph.microsoft.com",
            applicationId, redirectUri,
            new PlatformParameters(PromptBehavior.Auto));
        return result.CreateAuthorizationHeader();
    ```

    <span data-ttu-id="8d063-313">Ändern Sie den Wert von `application_ID` entsprechend in einen Wert, der dem Berechtigungsbereich `DeviceManagementManagedDevices.Read.All` mindestens erteilt wurde (siehe oben).</span><span class="sxs-lookup"><span data-stu-id="8d063-313">Remember to change the value of `application_ID` to match one granted at least the `DeviceManagementManagedDevices.Read.All` permission scope, as described earlier.</span></span>

6. <span data-ttu-id="8d063-314">Fügen Sie eine Methode zum Abrufen der Geräteliste hinzu:</span><span class="sxs-lookup"><span data-stu-id="8d063-314">Add a method to retrieve the list of devices:</span></span>

    ``` csharp
    private static async Task<string> GetMyManagedDevices()
    {
        string authHeader = await GetAuthorizationHeader();
        HttpClient graphClient = new HttpClient();
        graphClient.DefaultRequestHeaders.Add("Authorization", authHeader);
        return await graphClient.GetStringAsync(
            "https://graph.microsoft.com/beta/me/managedDevices");
    }
    ```

7.  <span data-ttu-id="8d063-315">Ändern Sie **Main** so, dass **GetMyManagedDevices** aufgerufen wird:</span><span class="sxs-lookup"><span data-stu-id="8d063-315">Update **Main** to call **GetMyManagedDevices**:</span></span>

    ``` csharp
    string devices = GetMyManagedDevices().GetAwaiter().GetResult();
    Console.WriteLine(devices);
    ```

8.  <span data-ttu-id="8d063-316">Kompilieren Sie Ihr Programm, und führen Sie es aus.</span><span class="sxs-lookup"><span data-stu-id="8d063-316">Compile and run your program.</span></span>  

<span data-ttu-id="8d063-317">Wenn Sie das Programm erstmals ausführen, sollten Sie zwei Eingabeaufforderungen erhalten.</span><span class="sxs-lookup"><span data-stu-id="8d063-317">When you first run your program, you should receive two prompts.</span></span>  <span data-ttu-id="8d063-318">Die erste fordert Ihre Anmeldeinformationen an, die zweite erteilt Berechtigungen für die Anforderung `managedDevices`.</span><span class="sxs-lookup"><span data-stu-id="8d063-318">The first requests your credentials and the second grants permissions for the `managedDevices` request.</span></span>  

<span data-ttu-id="8d063-319">Zur Bezugnahme sehen Sie hier das vollständige Programm:</span><span class="sxs-lookup"><span data-stu-id="8d063-319">For reference, here's the completed program:</span></span>

``` csharp
using Microsoft.IdentityModel.Clients.ActiveDirectory;
using System;
using System.Net.Http;
using System.Threading.Tasks;

namespace IntuneGraphExample
{
    class Program
    {
        static void Main(string[] args)
        {
            string devices = GetMyManagedDevices().GetAwaiter().GetResult();
            Console.WriteLine(devices);
        }

        private static async Task<string> GetAuthorizationHeader()
        {
            string applicationId = "<Your Application ID>";
            string authority = "https://login.microsoftonline.com/common/";
            Uri redirectUri = new Uri("urn:ietf:wg:oauth:2.0:oob");
            AuthenticationContext context = new AuthenticationContext(authority);
            AuthenticationResult result = await context.AcquireTokenAsync("https://graph.microsoft.com", applicationId, redirectUri, new PlatformParameters(PromptBehavior.Auto));
            return result.CreateAuthorizationHeader();
        }

        private static async Task<string> GetMyManagedDevices()
        {
            string authHeader = await GetAuthorizationHeader();
            HttpClient graphClient = new HttpClient();
            graphClient.DefaultRequestHeaders.Add("Authorization", authHeader);
            return await graphClient.GetStringAsync("https://graph.microsoft.com/beta/me/managedDevices");
        }
    }
}
```

### <a name="authenticate-azure-ad-powershell"></a><span data-ttu-id="8d063-320">Authentifizieren von Azure AD (PowerShell)</span><span class="sxs-lookup"><span data-stu-id="8d063-320">Authenticate Azure AD (PowerShell)</span></span>

<span data-ttu-id="8d063-321">Das folgende PowerShell-Skript verwendet das AzureAD-PowerShell-Modul zur Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="8d063-321">The following PowerShell script uses the AzureAD PowerShell module for authentication.</span></span>  <span data-ttu-id="8d063-322">Weitere Informationen finden Sie unter [Azure Active Directory PowerShell, Version 2](https://docs.microsoft.co/powershell/azure/install-adv2?view=azureadps-2.0) und [Intune PowerShell-Beispiele](https://github.com/microsoftgraph/powershell-intune-samples).</span><span class="sxs-lookup"><span data-stu-id="8d063-322">To learn more, see [Azure Active Directory PowerShell Version 2](https://docs.microsoft.co/powershell/azure/install-adv2?view=azureadps-2.0) and the [Intune PowerShell examples](https://github.com/microsoftgraph/powershell-intune-samples).</span></span>

<span data-ttu-id="8d063-323">In diesem Beispiel aktualisieren Sie den Wert von `$clientID` so, dass er einer gültigen Anwendungs-ID entspricht.</span><span class="sxs-lookup"><span data-stu-id="8d063-323">In this example, update the value of `$clientID` to match a valid application ID.</span></span>

``` powershell
function Get-AuthToken {
    [cmdletbinding()]
    param
    (
        [Parameter(Mandatory = $true)]
        $User
    )

    $userUpn = New-Object "System.Net.Mail.MailAddress" -ArgumentList $User
    $tenant = $userUpn.Host

    Write-Host "Checking for AzureAD module..."

    $AadModule = Get-Module -Name "AzureAD" -ListAvailable
    if ($AadModule -eq $null) {
        Write-Host "AzureAD PowerShell module not found, looking for AzureADPreview"
        $AadModule = Get-Module -Name "AzureADPreview" -ListAvailable
    }

    if ($AadModule -eq $null) {
        write-host
        write-host "AzureAD Powershell module not installed..." -f Red
        write-host "Install by running 'Install-Module AzureAD' or 'Install-Module AzureADPreview' from an elevated PowerShell prompt" -f Yellow
        write-host "Script can't continue..." -f Red
        write-host
        exit
    }

    # Getting path to ActiveDirectory Assemblies
    # If the module count is greater than 1 find the latest version

    if ($AadModule.count -gt 1) {
        $Latest_Version = ($AadModule | select version | Sort-Object)[-1]
        $aadModule = $AadModule | ? { $_.version -eq $Latest_Version.version }
        $adal = Join-Path $AadModule.ModuleBase "Microsoft.IdentityModel.Clients.ActiveDirectory.dll"
        $adalforms = Join-Path $AadModule.ModuleBase "Microsoft.IdentityModel.Clients.ActiveDirectory.Platform.dll"
    }

    else {
        $adal = Join-Path $AadModule.ModuleBase "Microsoft.IdentityModel.Clients.ActiveDirectory.dll"
        $adalforms = Join-Path $AadModule.ModuleBase "Microsoft.IdentityModel.Clients.ActiveDirectory.Platform.dll"
    }

    [System.Reflection.Assembly]::LoadFrom($adal) | Out-Null
    [System.Reflection.Assembly]::LoadFrom($adalforms) | Out-Null

    $clientId = "<Your Application ID>"
    $redirectUri = "urn:ietf:wg:oauth:2.0:oob"
    $resourceAppIdURI = "https://graph.microsoft.com"
    $authority = "https://login.microsoftonline.com/$Tenant"

    try {
        $authContext = New-Object "Microsoft.IdentityModel.Clients.ActiveDirectory.AuthenticationContext" -ArgumentList $authority
        # https://msdn.microsoft.com/library/azure/microsoft.identitymodel.clients.activedirectory.promptbehavior.aspx
        # Change the prompt behaviour to force credentials each time: Auto, Always, Never, RefreshSession
        $platformParameters = New-Object "Microsoft.IdentityModel.Clients.ActiveDirectory.PlatformParameters" -ArgumentList "Auto"
        $userId = New-Object "Microsoft.IdentityModel.Clients.ActiveDirectory.UserIdentifier" -ArgumentList ($User, "OptionalDisplayableId")
        $authResult = $authContext.AcquireTokenAsync($resourceAppIdURI, $clientId, $redirectUri, $platformParameters, $userId).Result
        # If the accesstoken is valid then create the authentication header
        if ($authResult.AccessToken) {
            # Creating header for Authorization token
            $authHeader = @{
                'Content-Type' = 'application/json'
                'Authorization' = "Bearer " + $authResult.AccessToken
                'ExpiresOn' = $authResult.ExpiresOn
            }
            return $authHeader
        }
        else {
            Write-Host
            Write-Host "Authorization Access Token is null, please re-run authentication..." -ForegroundColor Red
            Write-Host
            break
        }
    }
    catch {
        write-host $_.Exception.Message -f Red
        write-host $_.Exception.ItemName -f Red
        write-host
        break
    }   
}

$authToken = Get-AuthToken -User "<Your AAD Username>"

try {
    $uri = "https://graph.microsoft.com/beta/me/managedDevices"
    Write-Verbose $uri
    (Invoke-RestMethod -Uri $uri –Headers $authToken –Method Get).Value
}
catch {
    $ex = $_.Exception
    $errorResponse = $ex.Response.GetResponseStream()
    $reader = New-Object System.IO.StreamReader($errorResponse)
    $reader.BaseStream.Position = 0
    $reader.DiscardBufferedData()
    $responseBody = $reader.ReadToEnd();
    Write-Host "Response content:`n$responseBody" -f Red
    Write-Error "Request to $Uri failed with HTTP Status $($ex.Response.StatusCode) $($ex.Response.StatusDescription)"
    write-host
    break
}
```

## <a name="support-multiple-tenants-and-partners"></a><span data-ttu-id="8d063-324">Unterstützen mehrerer Mandanten und Partner</span><span class="sxs-lookup"><span data-stu-id="8d063-324">Support multiple tenants and partners</span></span>

<span data-ttu-id="8d063-325">Wenn Organisationen mit eigenen Azure AD-Mandanten von Ihrer Organisation unterstützt werden, möchten Sie ggf. Ihren Clients erlauben, Ihre Anwendung in ihren entsprechenden Mandanten zu nutzen.</span><span class="sxs-lookup"><span data-stu-id="8d063-325">If your organization supports organizations with their own Azure AD tenants, you may want to permit your clients to use your application with their respective tenants.</span></span>

<span data-ttu-id="8d063-326">Gehen Sie hierzu folgendermaßen vor:</span><span class="sxs-lookup"><span data-stu-id="8d063-326">To do so:</span></span>

1.  <span data-ttu-id="8d063-327">Stellen Sie sicher, dass das Konto im Azure AD-Zielmandanten vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="8d063-327">Verify that the client account exists in the target Azure AD tenant.</span></span>

2.  <span data-ttu-id="8d063-328">Stellen Sie sicher, dass Ihr Mandantenkonto die Registrierung von Anwendungen durch Benutzer zulässt (siehe **Benutzereinstellungen**).</span><span class="sxs-lookup"><span data-stu-id="8d063-328">Verify that your tenant account allows users to register applications (see **User settings**).</span></span>

3.  <span data-ttu-id="8d063-329">Richten Sie eine Beziehung zwischen jedem Mandanten ein.</span><span class="sxs-lookup"><span data-stu-id="8d063-329">Establish a relationship between each tenant.</span></span>  

    <span data-ttu-id="8d063-330">Gehen Sie hierfür so vor:</span><span class="sxs-lookup"><span data-stu-id="8d063-330">To do so, either:</span></span>

    <span data-ttu-id="8d063-331">a.</span><span class="sxs-lookup"><span data-stu-id="8d063-331">a.</span></span> <span data-ttu-id="8d063-332">Definieren Sie im [Microsoft Partner Center](https://partnercenter.microsoft.com/) eine Beziehung mit Ihrem Client und seiner E-Mail-Adresse.</span><span class="sxs-lookup"><span data-stu-id="8d063-332">Use the [Microsoft Partner Center](https://partnercenter.microsoft.com/) to define a relationship with your client and their email address.</span></span>

    <span data-ttu-id="8d063-333">b.</span><span class="sxs-lookup"><span data-stu-id="8d063-333">b.</span></span> <span data-ttu-id="8d063-334">Laden Sie den Benutzer ein, Gast Ihres Mandanten zu werden.</span><span class="sxs-lookup"><span data-stu-id="8d063-334">Invite the user to become a guest of your tenant.</span></span>

<span data-ttu-id="8d063-335">So laden Sie den Benutzer ein, Gast Ihres Mandanten zu werden</span><span class="sxs-lookup"><span data-stu-id="8d063-335">To invite the user to be a guest of your tenant:</span></span>

1.  <span data-ttu-id="8d063-336">Wählen Sie **Gastbenutzer hinzufügen** im Bereich **Schnellaufgaben** aus.</span><span class="sxs-lookup"><span data-stu-id="8d063-336">Choose **Add a guest user** from the **Quick tasks** panel.</span></span>

    <img src="media/azure-ad-add-guest.png" width="448" height="138" alt="Use Quick Tasks to add a guest user" />

2.  <span data-ttu-id="8d063-337">Geben Sie die E-Mail-Adresse des Clients ein, und fügen Sie (optional) eine personalisierte Nachricht für die Einladung hinzu.</span><span class="sxs-lookup"><span data-stu-id="8d063-337">Enter the client's email address and (optionally) add a personalized message for the invite.</span></span>

    <img src="media/azure-ad-guest-invite.png" width="203" height="106" alt="Inviting an external user as a guest" />

3.  <span data-ttu-id="8d063-338">Klicken Sie auf **Einladen**.</span><span class="sxs-lookup"><span data-stu-id="8d063-338">Choose **Invite**.</span></span>

<span data-ttu-id="8d063-339">Dem Benutzer wird eine Einladung gesendet.</span><span class="sxs-lookup"><span data-stu-id="8d063-339">This sends an invite to the user.</span></span>

   <img src="media/aad-multiple-tenant-invitation.png" width="624" height="523" alt="A sample guest invitation" />

   <span data-ttu-id="8d063-340">Der Benutzer muss auf den Link **Erste Schritte** klicken, um Ihre Einladung anzunehmen.</span><span class="sxs-lookup"><span data-stu-id="8d063-340">The user needs to choose the **Get Started** link to accept your invitation.</span></span>

<span data-ttu-id="8d063-341">Nachdem die Beziehung eingerichtet oder Ihre Einladung akzeptiert wurde, fügen Sie das Benutzerkonto der **Verzeichnisrolle** hinzu.</span><span class="sxs-lookup"><span data-stu-id="8d063-341">When the relationship is established (or your invitation has been accepted), add the user account to the **Directory role**.</span></span>

<span data-ttu-id="8d063-342">Denken Sie daran, den Benutzer bei Bedarf anderen Rollen hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="8d063-342">Remember to add the user to other roles as needed.</span></span> <span data-ttu-id="8d063-343">Um beispielsweise dem Benutzer das Verwalten von Intune-Einstellungen zu erlauben, müssen Sie entweder ein **globaler Administrator** oder **Intune-Dienstadministrator** sein.</span><span class="sxs-lookup"><span data-stu-id="8d063-343">For example, to allow the user to manage Intune settings, they need to be either a **Global Administrator** or an **Intune Service administrator**.</span></span>

<span data-ttu-id="8d063-344">Ferner gilt Folgendes:</span><span class="sxs-lookup"><span data-stu-id="8d063-344">Also:</span></span>

- <span data-ttu-id="8d063-345">Verwenden Sie http://portal.office.com, um Ihrem Benutzerkonto eine Intune-Lizenz zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="8d063-345">Use http://portal.office.com to assign an Intune license to your user account.</span></span>

- <span data-ttu-id="8d063-346">Ändern Sie den Anwendungscode so, dass die Azure AD-Mandantendomäne des Clients und nicht Ihre eigene authentifiziert wird.</span><span class="sxs-lookup"><span data-stu-id="8d063-346">Update application code to authenticate to the client's Azure AD tenant domain, rather than your own.</span></span>

    <span data-ttu-id="8d063-347">Angenommen, die Mandantendomäne heißt `contosopartner.onmicrosoft.com` und die des Clients `northwind.onmicrosoft.com`. Sie müssen dann Ihren Code so ändern, dass Sie beim Mandanten des Clients authentifiziert werden.</span><span class="sxs-lookup"><span data-stu-id="8d063-347">For example, suppose your tenant domain is `contosopartner.onmicrosoft.com` and your client's tenant domain is `northwind.onmicrosoft.com`, you would update your code to authenticate to your client's tenant.</span></span>

    <span data-ttu-id="8d063-348">Um dies in einer C#-Anwendung basierend auf dem vorherigen Beispiel zu tun, ändern Sie den Wert der Variablen `authority`:</span><span class="sxs-lookup"><span data-stu-id="8d063-348">To do so in a C# application based on the earlier example, you'd change the value of the `authority` variable:</span></span>

    ``` csharp
    string authority = "https://login.microsoftonline.com/common/";
    ```

    <span data-ttu-id="8d063-349">in</span><span class="sxs-lookup"><span data-stu-id="8d063-349">to</span></span>

    ``` csharp
    string authority = "https://login.microsoftonline.com/northwind.onmicrosoft.com/";
    ```
