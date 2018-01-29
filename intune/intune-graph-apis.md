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
ms.openlocfilehash: 96b0c2f10f5fec1f8c80b7510ba5bfa231e45739
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2018
---
# <a name="how-to-use-azure-ad-to-access-the-intune-graph-api"></a><span data-ttu-id="761b6-104">Zugreifen auf die Intune Graph-API über Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="761b6-104">How to use Azure AD to access the Intune Graph API</span></span>

<span data-ttu-id="761b6-105">Die [Microsoft Graph-API](https://developer.microsoft.com/graph/) unterstützt jetzt Microsoft Intune mit bestimmten APIs und Berechtigungsrollen.</span><span class="sxs-lookup"><span data-stu-id="761b6-105">The [Microsoft Graph API](https://developer.microsoft.com/graph/) now supports Microsoft Intune with specific APIs and permission roles.</span></span>  <span data-ttu-id="761b6-106">Der Graph-API verwendet für die Authentifizierung und Zugriffsteuerung Azure Active Directory (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="761b6-106">The Graph API uses Azure Active Directory (Azure AD) for authentication and access control.</span></span>  
<span data-ttu-id="761b6-107">Für den Zugriff auf die Intune Graph-API benötigen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="761b6-107">Access to the Intune Graph API requires:</span></span>

- <span data-ttu-id="761b6-108">Eine Anwendungs-ID mit:</span><span class="sxs-lookup"><span data-stu-id="761b6-108">An application ID with:</span></span>

    - <span data-ttu-id="761b6-109">Berechtigung zum Aufrufen von Azure AD und Graph-APIs</span><span class="sxs-lookup"><span data-stu-id="761b6-109">Permission to call Azure AD and Graph APIs.</span></span>
    - <span data-ttu-id="761b6-110">Berechtigungsbereichen, die für bestimmte Anwendungsaufgaben relevant sind</span><span class="sxs-lookup"><span data-stu-id="761b6-110">Permission scopes relevant to the specific application tasks.</span></span>

- <span data-ttu-id="761b6-111">Benutzeranmeldeinformationen mit:</span><span class="sxs-lookup"><span data-stu-id="761b6-111">User credentials with:</span></span>

    - <span data-ttu-id="761b6-112">Zugriffsberechtigung für den Azure AD-Mandanten, der der Anwendung zugeordnet ist</span><span class="sxs-lookup"><span data-stu-id="761b6-112">Permission to access the Azure AD tenant associated with the application.</span></span>
    - <span data-ttu-id="761b6-113">Rollenberechtigungen zur Unterstützung der Anwendungsberechtigungsbereiche</span><span class="sxs-lookup"><span data-stu-id="761b6-113">Role permissions required to support the application permission scopes.</span></span>

- <span data-ttu-id="761b6-114">Der App durch den Endbenutzer erteilte Berechtigung zum Ausführen von Anwendungsaufgaben im Azure-Mandanten</span><span class="sxs-lookup"><span data-stu-id="761b6-114">The end user to grant permission to the app to perform applications tasks for their Azure tenant.</span></span>

<span data-ttu-id="761b6-115">Inhalt dieses Artikels</span><span class="sxs-lookup"><span data-stu-id="761b6-115">This article:</span></span>

- <span data-ttu-id="761b6-116">Erläuterung der Registrierung einer Anwendung mit Zugriff auf die Graph-API und relevante Berechtigungsrollen</span><span class="sxs-lookup"><span data-stu-id="761b6-116">Shows how to register an application with access to the Graph API and relevant permission roles.</span></span>

- <span data-ttu-id="761b6-117">Beschreiben der Intune Graph-API-Berechtigungsrollen</span><span class="sxs-lookup"><span data-stu-id="761b6-117">Describes the Intune Graph API permission roles.</span></span>

- <span data-ttu-id="761b6-118">Bereitstellen von Beispielen der Intune Graph-API-Authentifizierung für C# und PowerShell</span><span class="sxs-lookup"><span data-stu-id="761b6-118">Provides Intune Graph API authentication examples for C# and PowerShell.</span></span>

- <span data-ttu-id="761b6-119">Beschreiben der Unterstützung mehrerer Mandanten</span><span class="sxs-lookup"><span data-stu-id="761b6-119">Describes how to support multiple tenants</span></span>

<span data-ttu-id="761b6-120">Weitere Informationen finden Sie unter:</span><span class="sxs-lookup"><span data-stu-id="761b6-120">To learn more, see:</span></span>

- [<span data-ttu-id="761b6-121">Autorisieren des Zugriffs auf Webanwendungen mit OAuth 2.0 und Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="761b6-121">Authorize access to web applications using OAuth 2.0 and Azure Active Directory</span></span>](https://docs.microsoft.com/azure/active-directory/develop/active-directory-protocols-oauth-code)
- [<span data-ttu-id="761b6-122">Erste Schritte mit der Azure AD-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="761b6-122">Getting start with Azure AD authentication</span></span>](https://www.visualstudio.com/docs/integrate/get-started/auth/oauth)
- [<span data-ttu-id="761b6-123">Integrieren von Anwendungen in Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="761b6-123">Integrating applications with Azure Active Directory</span></span>](https://docs.microsoft.com/azure/active-directory/develop/active-directory-integrating-applications)
- [<span data-ttu-id="761b6-124">Grundlegendes zu OAuth 2.0</span><span class="sxs-lookup"><span data-stu-id="761b6-124">Understand OAuth 2.0</span></span>](https://oauth.net/2/)

## <a name="register-apps-to-use-graph-api"></a><span data-ttu-id="761b6-125">Registrieren von Apps für die Verwendung der Graph-API</span><span class="sxs-lookup"><span data-stu-id="761b6-125">Register apps to use Graph API</span></span>

<span data-ttu-id="761b6-126">So registrieren Sie eine App für die Verwendung der Graph-API</span><span class="sxs-lookup"><span data-stu-id="761b6-126">To register an app to use Graph API:</span></span>

1.  <span data-ttu-id="761b6-127">Melden Sie sich beim [Azure-Portal](https://portal.azure.com) mit Administratoranmeldeinformationen an.</span><span class="sxs-lookup"><span data-stu-id="761b6-127">Sign into [the Azure portal](https://portal.azure.com) using administrative credentials.</span></span>

    <span data-ttu-id="761b6-128">Dazu können Sie Folgendes verwenden:</span><span class="sxs-lookup"><span data-stu-id="761b6-128">As appropriate, you may use:</span></span>
    - <span data-ttu-id="761b6-129">Die Administratorkonto des Mandanten</span><span class="sxs-lookup"><span data-stu-id="761b6-129">The tenant admin account.</span></span>
    - <span data-ttu-id="761b6-130">Ein Mandantenbenutzerkonto mit aktivierter Einstellung **Benutzer können Anwendungen registrieren**</span><span class="sxs-lookup"><span data-stu-id="761b6-130">A tenant user account with the **Users can register applications** setting enabled.</span></span>

2.  <span data-ttu-id="761b6-131">Wählen Sie im Menü **Azure Active Directory** &gt; **App-Registrierungen** aus.</span><span class="sxs-lookup"><span data-stu-id="761b6-131">From the menu, choose **Azure Active Directory** &gt; **App Registrations**.</span></span>

    <img src="./media/azure-ad-app-reg.png" width="157" height="170" alt="The App registrations menu command" />

3.  <span data-ttu-id="761b6-132">Wählen Sie entweder **Neue Anwendungsregistrierung**, um eine neue Anwendung erstellen, oder eine vorhandene Anwendung.</span><span class="sxs-lookup"><span data-stu-id="761b6-132">Either choose **New application registration** to create a new application or choose an existing application.</span></span>  <span data-ttu-id="761b6-133">(Wenn Sie eine vorhandene Anwendung wählen, überspringen Sie den nächsten Schritt.)</span><span class="sxs-lookup"><span data-stu-id="761b6-133">(If you choose an existing application, skip the next step.)</span></span>

4.  <span data-ttu-id="761b6-134">Geben Sie auf dem Blatt **Erstellen** Folgendes an:</span><span class="sxs-lookup"><span data-stu-id="761b6-134">On the **Create** blade, specify the following:</span></span>

    1.  <span data-ttu-id="761b6-135">Einen **Namen** für die Anwendung (der angezeigt wird, wenn Benutzer sich anmelden).</span><span class="sxs-lookup"><span data-stu-id="761b6-135">A **Name** for the application (displayed when users sign in).</span></span>

    2.  <span data-ttu-id="761b6-136">Werte für **Anwendungstyp** und **Umleitungs-URI**.</span><span class="sxs-lookup"><span data-stu-id="761b6-136">The **Application type** and **Redirect URI** values.</span></span>

        <span data-ttu-id="761b6-137">Diese unterscheiden sich entsprechend Ihren Anforderungen.</span><span class="sxs-lookup"><span data-stu-id="761b6-137">These vary according to your requirements.</span></span> <span data-ttu-id="761b6-138">Wenn Sie beispielsweise eine Azure AD-[Authentifizierungsbibliothek](https://docs.microsoft.com/azure/active-directory/develop/active-directory-authentication-libraries) (ADAL) verwenden, legen Sie **Anwendungstyp** auf `Native` und **Umleitungs-URI** auf `urn:ietf:wg:oauth:2.0:oob` fest.</span><span class="sxs-lookup"><span data-stu-id="761b6-138">For example, if you're using an Azure AD [Authentication Library](https://docs.microsoft.com/azure/active-directory/develop/active-directory-authentication-libraries) (ADAL), set **Application Type** to `Native` and **Redirect URI** to `urn:ietf:wg:oauth:2.0:oob`.</span></span>

        <img src="media/azure-ad-app-new.png" width="209" height="140" alt="New app properties and values" />

        <span data-ttu-id="761b6-139">Weitere Informationen finden Sie unter [Authentifizierungsszenarien für Azure AD](https://docs.microsoft.com/azure/active-directory/develop/active-directory-authentication-scenarios).</span><span class="sxs-lookup"><span data-stu-id="761b6-139">To learn more, see [Authentication Scenarios for Azure AD](https://docs.microsoft.com/azure/active-directory/develop/active-directory-authentication-scenarios).</span></span>

5.  <span data-ttu-id="761b6-140">Auf dem Blatt „Anwendung“:</span><span class="sxs-lookup"><span data-stu-id="761b6-140">From the application blade:</span></span>

    1.  <span data-ttu-id="761b6-141">Notieren Sie sich den Wert von **Anwendungs-ID**.</span><span class="sxs-lookup"><span data-stu-id="761b6-141">Note the **Application ID** value.</span></span>

    2.  <span data-ttu-id="761b6-142">Wählen Sie **Einstellungen** &gt; **API-Zugriff** &gt; **Erforderliche Berechtigungen**.</span><span class="sxs-lookup"><span data-stu-id="761b6-142">Choose **Settings** &gt; **API access** &gt; **Required permissions**.</span></span>

    <img src="media/azure-ad-req-perm.png" width="483" height="186" alt="The Required permissions setting" />

6.  <span data-ttu-id="761b6-143">Wählen Sie auf dem Blatt **Erforderliche Berechtigungen** nacheinander **Hinzufügen** &gt; **API-Zugriff hinzufügen** &gt; **API auswählen**.</span><span class="sxs-lookup"><span data-stu-id="761b6-143">From the **Required Permissions** blade, choose **Add** &gt; **Add API access** &gt; **Select an API**.</span></span>

    <img src="media/azure-ad-add-graph.png" width="436" height="140" alt="The Microsoft Graph setting" />

7.  <span data-ttu-id="761b6-144">Wählen Sie auf dem Blatt **API auswählen** nacheinander **Microsoft Graph** &gt; **Auswählen**.</span><span class="sxs-lookup"><span data-stu-id="761b6-144">From the **Select an API** blade, choose **Microsoft Graph** &gt; **Select**.</span></span>  <span data-ttu-id="761b6-145">Das Blatt **Zugriff aktivieren** wird geöffnet, auf dem die für Ihre Anwendung verfügbaren Berechtigungsbereiche aufgeführt sind.</span><span class="sxs-lookup"><span data-stu-id="761b6-145">The **Enable access** blade opens and lists permission scopes available to your application.</span></span>

    <img src="media/azure-ad-perm-scopes.png" width="489" height="248" alt="Intune Graph API permission scopes" />

    <span data-ttu-id="761b6-146">Wählen Sie die für Ihre App erforderlichen Rollen, indem Sie ein Häkchen links neben den gewünschten Namen setzen.</span><span class="sxs-lookup"><span data-stu-id="761b6-146">Choose the roles required for your app by placing a checkmark to the left of the relevant names.</span></span>  <span data-ttu-id="761b6-147">Weitere Informationen zu bestimmten Berechtigungsbereichen in Intune finden Sie unter [Intune-Berechtigungsbereiche](#user-content-intune-permission-scopes).</span><span class="sxs-lookup"><span data-stu-id="761b6-147">To learn about specific Intune permission scopes, see [Intune permission scopes](#user-content-intune-permission-scopes).</span></span>  <span data-ttu-id="761b6-148">Weitere Informationen zu anderen Berechtigungsbereichen für die Graph-API finden Sie in der [Microsoft Graph-Berechtigungsreferenz](https://developer.microsoft.com/graph/docs/concepts/permissions_reference).</span><span class="sxs-lookup"><span data-stu-id="761b6-148">To learn about other Graph API permission scopes, see [Microsoft Graph permissions reference](https://developer.microsoft.com/graph/docs/concepts/permissions_reference).</span></span>

    <span data-ttu-id="761b6-149">Wählen Sie für optimale Ergebnisse nur so viele Rollen, wie für die Implementierung Ihrer Anwendung erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="761b6-149">For best results, choose the fewest roles needed to implement your application.</span></span>

    <span data-ttu-id="761b6-150">Klicken Sie abschließend auf **Auswählen** und **Fertig**, um Ihre Änderungen zu speichern.</span><span class="sxs-lookup"><span data-stu-id="761b6-150">When finished, choose **Select** and **Done** to save you changes.</span></span>

<span data-ttu-id="761b6-151">An diesem Punkt haben Sie auch folgende Möglichkeiten:</span><span class="sxs-lookup"><span data-stu-id="761b6-151">At this point, you may also:</span></span>

- <span data-ttu-id="761b6-152">Sie können allen Mandantenkonten die Berechtigung zum Verwenden der App ohne Angabe von Anmeldeinformationen erteilen.</span><span class="sxs-lookup"><span data-stu-id="761b6-152">Choose to grant permission for all tenant accounts to use the app without providing credentials.</span></span>  

    <span data-ttu-id="761b6-153">Zu diesem Zweck wählen Sie **Berechtigungen** und akzeptieren die Bestätigungsaufforderung.</span><span class="sxs-lookup"><span data-stu-id="761b6-153">To do so, choose **Grant permissions** and accept the confirmation prompt.</span></span>

    <span data-ttu-id="761b6-154">Wenn Sie die Anwendung zum ersten Mal ausführen, werden Sie aufgefordert, die App-Berechtigung für die ausgewählten Rollen zu erteilen.</span><span class="sxs-lookup"><span data-stu-id="761b6-154">When you run the application for the first time, you're prompted to grant the app permission to perform the selected roles.</span></span>

    <img src="media/azure-ad-grant-perm.png" width="351" height="162" alt="The Grant permissions button" />


- <span data-ttu-id="761b6-155">Sie können die App Benutzern außerhalb Ihres Mandanten zur Verfügung stellen.</span><span class="sxs-lookup"><span data-stu-id="761b6-155">Make the app available to users outside your tenant.</span></span>  <span data-ttu-id="761b6-156">(Dies ist normalerweise nur für Partner erforderlich, die mehrere Mandanten/Organisationen unterstützen.)</span><span class="sxs-lookup"><span data-stu-id="761b6-156">(This is typically only required for partners supporting multiple tenants/organizations.)</span></span>  

    <span data-ttu-id="761b6-157">Gehen Sie hierzu folgendermaßen vor:</span><span class="sxs-lookup"><span data-stu-id="761b6-157">To do so:</span></span>

  1. <span data-ttu-id="761b6-158">Wählen sie auf dem Blatt der Anwendung **Manifest**, um das Blatt **Manifest bearbeiten** zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="761b6-158">Choose **Manifest** from the application blade, which opens the **Edit Manifest** blade.</span></span>

     <img src="media/azure-ad-edit-mft.png" width="295" height="114" alt="The Edit manifest blade" />


  2. <span data-ttu-id="761b6-159">Ändern Sie den Wert der Einstellung `availableToOtherTenants` in `true`.</span><span class="sxs-lookup"><span data-stu-id="761b6-159">Change the value of the `availableToOtherTenants` setting to `true`.</span></span>

  3. <span data-ttu-id="761b6-160">Speichern Sie die Änderungen.</span><span class="sxs-lookup"><span data-stu-id="761b6-160">Save your changes.</span></span>

## <a name="intune-permission-scopes"></a><span data-ttu-id="761b6-161">Intune-Berechtigungsbereiche</span><span class="sxs-lookup"><span data-stu-id="761b6-161">Intune permission scopes</span></span>

<span data-ttu-id="761b6-162">Azure AD und die Graph-API nutzen Berechtigungsbereiche zum Steuern des Zugriffs auf Unternehmensressourcen.</span><span class="sxs-lookup"><span data-stu-id="761b6-162">Azure AD and the Graph API use permission scopes to control access to corporate resources.</span></span>  

<span data-ttu-id="761b6-163">Berechtigungsbereiche (auch _OAuth-Bereiche_ genannt) steuern den Zugriff auf bestimmte Intune-Entitäten und deren Eigenschaften.</span><span class="sxs-lookup"><span data-stu-id="761b6-163">Permission scopes (also called the _OAuth scopes_) control access to specific Intune entities and their properties.</span></span> <span data-ttu-id="761b6-164">In diesem Abschnitt werden die Berechtigungsbereiche für Intune Graph-API-Funktionen zusammengefasst.</span><span class="sxs-lookup"><span data-stu-id="761b6-164">This section summarizes the permission scopes for Intune Graph API features.</span></span>

<span data-ttu-id="761b6-165">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="761b6-165">To learn more:</span></span>
- [<span data-ttu-id="761b6-166">Azure AD-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="761b6-166">Azure AD authentication</span></span>](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-pass-through-authentication)
- [<span data-ttu-id="761b6-167">Anwendungsberechtigungsbereiche</span><span class="sxs-lookup"><span data-stu-id="761b6-167">Application permission scopes</span></span>](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-scopes)

<span data-ttu-id="761b6-168">Wenn Sie der Graph-API Berechtigung erteilen, können Sie angeben, dass die folgenden Bereiche den Zugriff auf die Intune-Funktionen steuern sollen. In der folgenden Tabelle werden die Intune Graph-API-Berechtigungsbereiche zusammengefasst.</span><span class="sxs-lookup"><span data-stu-id="761b6-168">When you grant permission to the Graph API, you can specify the following scopes to control access to Intune features: The following table summarizes the Intune Graph API permission scopes.</span></span>  <span data-ttu-id="761b6-169">Die erste Spalte enthält den Namen der Funktion entsprechend der Anzeige im Azure-Portal, die zweite den Namen des Berechtigungsbereichs.</span><span class="sxs-lookup"><span data-stu-id="761b6-169">The first column shows the name of the feature as displayed in the Azure portal and the second column provides the permission scope name.</span></span>

<span data-ttu-id="761b6-170">Einstellung _Zugriff aktivieren_</span><span class="sxs-lookup"><span data-stu-id="761b6-170">_Enable Access_ setting</span></span> | <span data-ttu-id="761b6-171">Bereichsname</span><span class="sxs-lookup"><span data-stu-id="761b6-171">Scope name</span></span>
:--|:--
<span data-ttu-id="761b6-172">__Remoteaktionen mit Auswirkungen auf Benutzer auf Microsoft Intune-Geräten ausführen__</span><span class="sxs-lookup"><span data-stu-id="761b6-172">__Perform user-impacting remote actions on Microsoft Intune devices__</span></span> | [<span data-ttu-id="761b6-173">DeviceManagementManagedDevices.PrivilegedOperations.All</span><span class="sxs-lookup"><span data-stu-id="761b6-173">DeviceManagementManagedDevices.PrivilegedOperations.All</span></span>](#user-content-mgd-po)
<span data-ttu-id="761b6-174">__Microsoft Intune-Geräte lesen und schreiben__</span><span class="sxs-lookup"><span data-stu-id="761b6-174">__Read and write Microsoft Intune devices__</span></span> | [<span data-ttu-id="761b6-175">DeviceManagementManagedDevices.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="761b6-175">DeviceManagementManagedDevices.ReadWrite.All</span></span>](#mgd-rw)
<span data-ttu-id="761b6-176">__Microsoft Intune-Geräte lesen__</span><span class="sxs-lookup"><span data-stu-id="761b6-176">__Read Microsoft Intune devices__</span></span> | [<span data-ttu-id="761b6-177">DeviceManagementManagedDevices.Read.All</span><span class="sxs-lookup"><span data-stu-id="761b6-177">DeviceManagementManagedDevices.Read.All</span></span>](#mgd-ro)
<span data-ttu-id="761b6-178">__Einstellungen für die rollenbasierte Zugriffssteuerung von Microsoft Intune-Geräten lesen und schreiben__</span><span class="sxs-lookup"><span data-stu-id="761b6-178">__Read and write Microsoft Intune RBAC settings__</span></span> | [<span data-ttu-id="761b6-179">DeviceManagementRBAC.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="761b6-179">DeviceManagementRBAC.ReadWrite.All</span></span>](#rac-rw)
<span data-ttu-id="761b6-180">__Einstellungen für die rollenbasierte Zugriffssteuerung von Microsoft Intune-Geräten lesen__</span><span class="sxs-lookup"><span data-stu-id="761b6-180">__Read Microsoft Intune RBAC settings__</span></span> | [<span data-ttu-id="761b6-181">DeviceManagementRBAC.Read.All</span><span class="sxs-lookup"><span data-stu-id="761b6-181">DeviceManagementRBAC.Read.All</span></span>](#rac=ro)
<span data-ttu-id="761b6-182">__Microsoft Intune-Apps lesen und schreiben__</span><span class="sxs-lookup"><span data-stu-id="761b6-182">__Read and write Microsoft Intune apps__</span></span> | [<span data-ttu-id="761b6-183">DeviceManagementApps.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="761b6-183">DeviceManagementApps.ReadWrite.All</span></span>](#app-rw)
<span data-ttu-id="761b6-184">__Microsoft Intune-Apps lesen__</span><span class="sxs-lookup"><span data-stu-id="761b6-184">__Read Microsoft Intune apps__</span></span> | [<span data-ttu-id="761b6-185">DeviceManagementApps.Read.All</span><span class="sxs-lookup"><span data-stu-id="761b6-185">DeviceManagementApps.Read.All</span></span>](#app-ro)
<span data-ttu-id="761b6-186">__Microsoft Intune-Gerätekonfiguration und -Richtlinien lesen und schreiben__</span><span class="sxs-lookup"><span data-stu-id="761b6-186">__Read and write Microsoft Intune Device Configuration and Policies__</span></span> | [<span data-ttu-id="761b6-187">DeviceManagementConfiguration.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="761b6-187">DeviceManagementConfiguration.ReadWrite.All</span></span>](#cfg-rw)
<span data-ttu-id="761b6-188">__Microsoft Intune-Gerätekonfiguration und -Richtlinien lesen__</span><span class="sxs-lookup"><span data-stu-id="761b6-188">__Read Microsoft Intune Device Configuration and Policies__</span></span> | [<span data-ttu-id="761b6-189">DeviceManagementConfiguration.Read.All</span><span class="sxs-lookup"><span data-stu-id="761b6-189">DeviceManagementConfiguration.Read.All</span></span>](#cfg-ro)
<span data-ttu-id="761b6-190">__Microsoft Intune-Konfiguration lesen und schreiben__</span><span class="sxs-lookup"><span data-stu-id="761b6-190">__Read and write Microsoft Intune configuration__</span></span> | [<span data-ttu-id="761b6-191">DeviceManagementServiceConfig.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="761b6-191">DeviceManagementServiceConfig.ReadWrite.All</span></span>](#svc-rw)
<span data-ttu-id="761b6-192">__Microsoft Intune-Konfiguration lesen__</span><span class="sxs-lookup"><span data-stu-id="761b6-192">__Read Microsoft Intune configuration__</span></span> | [<span data-ttu-id="761b6-193">DeviceManagementServiceConfig.Read.All</span><span class="sxs-lookup"><span data-stu-id="761b6-193">DeviceManagementServiceConfig.Read.All</span></span>](#svc-ra)

<span data-ttu-id="761b6-194">Die Tabelle enthält die Einstellungen in der Reihenfolge, in der sie im Azure-Portal angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="761b6-194">The table lists the settings as they appear in the Azure portal.</span></span> <span data-ttu-id="761b6-195">In den folgenden Abschnitten werden die Bereiche in alphabetischer Reihenfolge beschrieben.</span><span class="sxs-lookup"><span data-stu-id="761b6-195">The following sections describe the scopes in alphabetical order.</span></span>

<span data-ttu-id="761b6-196">Derzeit erfordern alle Intune-Berechtigungsbereiche Administratorzugriff.</span><span class="sxs-lookup"><span data-stu-id="761b6-196">At this time, all Intune permission scopes require administrator access.</span></span>  <span data-ttu-id="761b6-197">Dies bedeutet, dass Sie zum Ausführen von Apps oder Skripts, die auf Intune Graph-API-Ressourcen zugreifen, entsprechende Anmeldeinformationen benötigen.</span><span class="sxs-lookup"><span data-stu-id="761b6-197">This means you need corresponding credentials when running apps or scripts that access Intune Graph API resources.</span></span>

### <a name="app-ro"></a><span data-ttu-id="761b6-198">DeviceManagementApps.Read.All</span><span class="sxs-lookup"><span data-stu-id="761b6-198">DeviceManagementApps.Read.All</span></span>

- <span data-ttu-id="761b6-199">Einstellung **Zugriff aktivieren**: __Microsoft Intune-Apps lesen__</span><span class="sxs-lookup"><span data-stu-id="761b6-199">**Enable Access** setting: __Read Microsoft Intune apps__</span></span>

- <span data-ttu-id="761b6-200">Ermöglicht Lesezugriff auf die folgenden Eigenschaften und den Status der Entität:</span><span class="sxs-lookup"><span data-stu-id="761b6-200">Permits read access to the following entity properties and status:</span></span>
    - <span data-ttu-id="761b6-201">Mobile Apps</span><span class="sxs-lookup"><span data-stu-id="761b6-201">Mobile Apps</span></span>
    - <span data-ttu-id="761b6-202">Kategorien mobiler Apps</span><span class="sxs-lookup"><span data-stu-id="761b6-202">Mobile App Categories</span></span>
    - <span data-ttu-id="761b6-203">App-Schutzrichtlinien</span><span class="sxs-lookup"><span data-stu-id="761b6-203">App Protection Policies</span></span>
    - <span data-ttu-id="761b6-204">App-Konfigurationen</span><span class="sxs-lookup"><span data-stu-id="761b6-204">App Configurations</span></span>

### <a name="app-rw"></a><span data-ttu-id="761b6-205">DeviceManagementApps.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="761b6-205">DeviceManagementApps.ReadWrite.All</span></span>

- <span data-ttu-id="761b6-206">Einstellung **Zugriff aktivieren**: __Microsoft Intune-Apps lesen und schreiben__</span><span class="sxs-lookup"><span data-stu-id="761b6-206">**Enable Access** setting: __Read and write Microsoft Intune apps__</span></span>

- <span data-ttu-id="761b6-207">Ermöglicht die gleichen Vorgänge wie __DeviceManagementApps.Read.All__</span><span class="sxs-lookup"><span data-stu-id="761b6-207">Allows the same operations as __DeviceManagementApps.Read.All__</span></span>

- <span data-ttu-id="761b6-208">Ermöglicht zudem Änderungen an den folgenden Entitäten:</span><span class="sxs-lookup"><span data-stu-id="761b6-208">Also permits changes to the following entities:</span></span>

    - <span data-ttu-id="761b6-209">Mobile Apps</span><span class="sxs-lookup"><span data-stu-id="761b6-209">Mobile Apps</span></span>
    - <span data-ttu-id="761b6-210">Kategorien mobiler Apps</span><span class="sxs-lookup"><span data-stu-id="761b6-210">Mobile App Categories</span></span>
    - <span data-ttu-id="761b6-211">App-Schutzrichtlinien</span><span class="sxs-lookup"><span data-stu-id="761b6-211">App Protection Policies</span></span>
    - <span data-ttu-id="761b6-212">App-Konfigurationen</span><span class="sxs-lookup"><span data-stu-id="761b6-212">App Configurations</span></span>

### <a name="cfg-ro"></a><span data-ttu-id="761b6-213">DeviceManagementConfiguration.Read.All</span><span class="sxs-lookup"><span data-stu-id="761b6-213">DeviceManagementConfiguration.Read.All</span></span>

- <span data-ttu-id="761b6-214">Einstellung **Zugriff aktivieren**: __Microsoft Intune-Gerätekonfiguration und -Richtlinien lesen__</span><span class="sxs-lookup"><span data-stu-id="761b6-214">**Enable Access** setting: __Read Microsoft Intune device configuration and policies__</span></span>

- <span data-ttu-id="761b6-215">Ermöglicht Lesezugriff auf die folgenden Eigenschaften und den Status der Entität:</span><span class="sxs-lookup"><span data-stu-id="761b6-215">Permits read access to the following entity properties and status:</span></span>
    - <span data-ttu-id="761b6-216">Gerätekonfiguration</span><span class="sxs-lookup"><span data-stu-id="761b6-216">Device Configuration</span></span>
    - <span data-ttu-id="761b6-217">Gerätekonformitätsrichtlinie</span><span class="sxs-lookup"><span data-stu-id="761b6-217">Device Compliance Policy</span></span>
    - <span data-ttu-id="761b6-218">Benachrichtigungen</span><span class="sxs-lookup"><span data-stu-id="761b6-218">Notification Messages</span></span>

### <a name="cfg-ra"></a><span data-ttu-id="761b6-219">DeviceManagementConfiguration.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="761b6-219">DeviceManagementConfiguration.ReadWrite.All</span></span>

- <span data-ttu-id="761b6-220">Einstellung **Zugriff aktivieren**: __Microsoft Intune-Gerätekonfiguration und -Richtlinien lesen und schreiben__</span><span class="sxs-lookup"><span data-stu-id="761b6-220">**Enable Access** setting: __Read and write Microsoft Intune device configuration and policies__</span></span>

- <span data-ttu-id="761b6-221">Ermöglicht die gleichen Vorgänge wie __DeviceManagementConfiguration.Read.All__</span><span class="sxs-lookup"><span data-stu-id="761b6-221">Allows the same operations as __DeviceManagementConfiguration.Read.All__</span></span>

- <span data-ttu-id="761b6-222">Apps können auch die folgenden Entitäten erstellen, zuweisen, löschen und ändern:</span><span class="sxs-lookup"><span data-stu-id="761b6-222">Apps can also create, assign, delete, and change the following entities:</span></span>
    - <span data-ttu-id="761b6-223">Gerätekonfiguration</span><span class="sxs-lookup"><span data-stu-id="761b6-223">Device Configuration</span></span>
    - <span data-ttu-id="761b6-224">Gerätekonformitätsrichtlinie</span><span class="sxs-lookup"><span data-stu-id="761b6-224">Device Compliance Policy</span></span>
    - <span data-ttu-id="761b6-225">Benachrichtigungen</span><span class="sxs-lookup"><span data-stu-id="761b6-225">Notification Messages</span></span>

### <a name="mgd-po"></a><span data-ttu-id="761b6-226">DeviceManagementManagedDevices.PrivilegedOperations.All</span><span class="sxs-lookup"><span data-stu-id="761b6-226">DeviceManagementManagedDevices.PrivilegedOperations.All</span></span>

- <span data-ttu-id="761b6-227">Einstellung **Zugriff aktivieren**: __Remoteaktionen mit Auswirkungen auf Benutzer auf Microsoft Intune-Geräten ausführen__</span><span class="sxs-lookup"><span data-stu-id="761b6-227">**Enable Access** setting: __Perform user-impacting remote actions on Microsoft Intune devices__</span></span>

- <span data-ttu-id="761b6-228">Erlaubt die folgenden Remoteaktionen auf einem verwalteten Gerät:</span><span class="sxs-lookup"><span data-stu-id="761b6-228">Permits the following remote actions on a managed device:</span></span>
    - <span data-ttu-id="761b6-229">Außerkraftsetzen</span><span class="sxs-lookup"><span data-stu-id="761b6-229">Retire</span></span>
    - <span data-ttu-id="761b6-230">Zurücksetzen</span><span class="sxs-lookup"><span data-stu-id="761b6-230">Wipe</span></span>
    - <span data-ttu-id="761b6-231">Kennung zurücksetzen/wiederherstellen</span><span class="sxs-lookup"><span data-stu-id="761b6-231">Reset/Recover Passcode</span></span>
    - <span data-ttu-id="761b6-232">Remotesperre</span><span class="sxs-lookup"><span data-stu-id="761b6-232">Remote Lock</span></span>
    - <span data-ttu-id="761b6-233">Modus für verlorene Geräte aktivieren/deaktivieren</span><span class="sxs-lookup"><span data-stu-id="761b6-233">Enable/Disable Lost Mode</span></span>
    - <span data-ttu-id="761b6-234">PC bereinigen</span><span class="sxs-lookup"><span data-stu-id="761b6-234">Clean PC</span></span>
    - <span data-ttu-id="761b6-235">Neustart</span><span class="sxs-lookup"><span data-stu-id="761b6-235">Reboot</span></span>
    - <span data-ttu-id="761b6-236">Benutzer von gemeinsam genutzten Gerät löschen</span><span class="sxs-lookup"><span data-stu-id="761b6-236">Delete User from Shared Device</span></span>

### <a name="mgd-ro"></a><span data-ttu-id="761b6-237">DeviceManagementManagedDevices.Read.All</span><span class="sxs-lookup"><span data-stu-id="761b6-237">DeviceManagementManagedDevices.Read.All</span></span>

- <span data-ttu-id="761b6-238">Einstellung **Zugriff aktivieren**: __Microsoft Intune-Geräte lesen__</span><span class="sxs-lookup"><span data-stu-id="761b6-238">**Enable Access** setting: __Read Microsoft Intune devices__</span></span>

- <span data-ttu-id="761b6-239">Ermöglicht Lesezugriff auf die folgenden Eigenschaften und den Status der Entität:</span><span class="sxs-lookup"><span data-stu-id="761b6-239">Permits read access to the following entity properties and status:</span></span>
    - <span data-ttu-id="761b6-240">Verwaltetes Gerät</span><span class="sxs-lookup"><span data-stu-id="761b6-240">Managed Device</span></span>
    - <span data-ttu-id="761b6-241">Gerätekategorie</span><span class="sxs-lookup"><span data-stu-id="761b6-241">Device Category</span></span>
    - <span data-ttu-id="761b6-242">Erkannte App</span><span class="sxs-lookup"><span data-stu-id="761b6-242">Detected App</span></span>
    - <span data-ttu-id="761b6-243">Remoteaktionen</span><span class="sxs-lookup"><span data-stu-id="761b6-243">Remote actions</span></span>
    - <span data-ttu-id="761b6-244">Informationen zu Schadsoftware</span><span class="sxs-lookup"><span data-stu-id="761b6-244">Malware information</span></span>

### <a name="mgd-rw"></a><span data-ttu-id="761b6-245">DeviceManagementManagedDevices.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="761b6-245">DeviceManagementManagedDevices.ReadWrite.All</span></span>

- <span data-ttu-id="761b6-246">Einstellung **Zugriff aktivieren**: __Microsoft Intune-Geräte lesen und schreiben__</span><span class="sxs-lookup"><span data-stu-id="761b6-246">**Enable Access** setting: __Read and write Microsoft Intune devices__</span></span>

- <span data-ttu-id="761b6-247">Ermöglicht die gleichen Vorgänge wie __DeviceManagementManagedDevices.Read.All__</span><span class="sxs-lookup"><span data-stu-id="761b6-247">Allows the same operations as __DeviceManagementManagedDevices.Read.All__</span></span>

- <span data-ttu-id="761b6-248">Apps können auch die folgenden Entitäten erstellen, löschen und ändern:</span><span class="sxs-lookup"><span data-stu-id="761b6-248">Apps can also create, delete, and change the following entities:</span></span>
    - <span data-ttu-id="761b6-249">Verwaltetes Gerät</span><span class="sxs-lookup"><span data-stu-id="761b6-249">Managed Device</span></span>
    - <span data-ttu-id="761b6-250">Gerätekategorie</span><span class="sxs-lookup"><span data-stu-id="761b6-250">Device Category</span></span>

- <span data-ttu-id="761b6-251">Die folgenden Remoteaktionen sind ebenfalls zulässig:</span><span class="sxs-lookup"><span data-stu-id="761b6-251">The following remote actions are also allowed:</span></span>
    - <span data-ttu-id="761b6-252">Geräte suchen</span><span class="sxs-lookup"><span data-stu-id="761b6-252">Locate devices</span></span>
    - <span data-ttu-id="761b6-253">Aktivierungssperre umgehen</span><span class="sxs-lookup"><span data-stu-id="761b6-253">Bypass activation lock</span></span>
    - <span data-ttu-id="761b6-254">Remoteunterstützung anfordern</span><span class="sxs-lookup"><span data-stu-id="761b6-254">Request remote assistance</span></span>

### <a name="rac-ro"></a><span data-ttu-id="761b6-255">DeviceManagementRBAC.Read.All</span><span class="sxs-lookup"><span data-stu-id="761b6-255">DeviceManagementRBAC.Read.All</span></span>

- <span data-ttu-id="761b6-256">Einstellung **Zugriff aktivieren**: __Einstellungen für die rollenbasierte Zugriffssteuerung von Microsoft Intune-Geräten lesen__</span><span class="sxs-lookup"><span data-stu-id="761b6-256">**Enable Access** setting: __Read Microsoft Intune RBAC settings__</span></span>

- <span data-ttu-id="761b6-257">Ermöglicht Lesezugriff auf die folgenden Eigenschaften und den Status der Entität:</span><span class="sxs-lookup"><span data-stu-id="761b6-257">Permits read access to the following entity properties and status:</span></span>
    - <span data-ttu-id="761b6-258">Rollenzuweisungen</span><span class="sxs-lookup"><span data-stu-id="761b6-258">Role Assignments</span></span>
    - <span data-ttu-id="761b6-259">Rollendefinitionen</span><span class="sxs-lookup"><span data-stu-id="761b6-259">Role Definitions</span></span>
    - <span data-ttu-id="761b6-260">Ressourcenvorgänge</span><span class="sxs-lookup"><span data-stu-id="761b6-260">Resource Operations</span></span>

### <a name="rac-rw"></a><span data-ttu-id="761b6-261">DeviceManagementRBAC.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="761b6-261">DeviceManagementRBAC.ReadWrite.All</span></span>

- <span data-ttu-id="761b6-262">Einstellung **Zugriff aktivieren**: __Einstellungen für die rollenbasierte Zugriffssteuerung von Microsoft Intune-Geräten lesen und schreiben__</span><span class="sxs-lookup"><span data-stu-id="761b6-262">**Enable Access** setting: __Read and write Microsoft Intune RBAC settings__</span></span>

- <span data-ttu-id="761b6-263">Ermöglicht die gleichen Vorgänge wie __DeviceManagementRBAC.Read.All__</span><span class="sxs-lookup"><span data-stu-id="761b6-263">Allows the same operations as __DeviceManagementRBAC.Read.All__</span></span>

- <span data-ttu-id="761b6-264">Apps können auch die folgenden Entitäten erstellen, zuweisen, löschen und ändern:</span><span class="sxs-lookup"><span data-stu-id="761b6-264">Apps can also create, assign, delete, and change the following entities:</span></span>
    - <span data-ttu-id="761b6-265">Rollenzuweisungen</span><span class="sxs-lookup"><span data-stu-id="761b6-265">Role Assignments</span></span>
    - <span data-ttu-id="761b6-266">Rollendefinitionen</span><span class="sxs-lookup"><span data-stu-id="761b6-266">Role Definitions</span></span>

### <a name="svc-ro"></a><span data-ttu-id="761b6-267">DeviceManagementServiceConfig.Read.All</span><span class="sxs-lookup"><span data-stu-id="761b6-267">DeviceManagementServiceConfig.Read.All</span></span>

- <span data-ttu-id="761b6-268">Einstellung **Zugriff aktivieren**: __Microsoft Intune-Konfiguration lesen__</span><span class="sxs-lookup"><span data-stu-id="761b6-268">**Enable Access** setting: __Read Microsoft Intune configuration__</span></span>

- <span data-ttu-id="761b6-269">Ermöglicht Lesezugriff auf die folgenden Eigenschaften und den Status der Entität:</span><span class="sxs-lookup"><span data-stu-id="761b6-269">Permits read access to the following entity properties and status:</span></span>
    - <span data-ttu-id="761b6-270">Geräteregistrierung</span><span class="sxs-lookup"><span data-stu-id="761b6-270">Device Enrollment</span></span>
    - <span data-ttu-id="761b6-271">Apple Push Notification-Zertifikat</span><span class="sxs-lookup"><span data-stu-id="761b6-271">Apple Push Notification Certificate</span></span>
    - <span data-ttu-id="761b6-272">Apple-Programm zur Geräteregistrierung</span><span class="sxs-lookup"><span data-stu-id="761b6-272">Apple Device Enrollment Program</span></span>
    - <span data-ttu-id="761b6-273">Apple Volume Purchase Program</span><span class="sxs-lookup"><span data-stu-id="761b6-273">Apple Volume Purchase Program</span></span>
    - <span data-ttu-id="761b6-274">Exchange-Connector</span><span class="sxs-lookup"><span data-stu-id="761b6-274">Exchange Connector</span></span>
    - <span data-ttu-id="761b6-275">Geschäftsbedingungen</span><span class="sxs-lookup"><span data-stu-id="761b6-275">Terms and Conditions</span></span>
    - <span data-ttu-id="761b6-276">Verwaltung von Ausgaben für Telekommunikation</span><span class="sxs-lookup"><span data-stu-id="761b6-276">Telecoms Expense Management</span></span>
    - <span data-ttu-id="761b6-277">PKI in der Cloud</span><span class="sxs-lookup"><span data-stu-id="761b6-277">Cloud PKI</span></span>
    - <span data-ttu-id="761b6-278">Branding</span><span class="sxs-lookup"><span data-stu-id="761b6-278">Branding</span></span>
    - <span data-ttu-id="761b6-279">Mobile Threat Defense</span><span class="sxs-lookup"><span data-stu-id="761b6-279">Mobile Threat Defense</span></span>

### <a name="svc-rw"></a><span data-ttu-id="761b6-280">DeviceManagementServiceConfig.ReadWrite.All</span><span class="sxs-lookup"><span data-stu-id="761b6-280">DeviceManagementServiceConfig.ReadWrite.All</span></span>

- <span data-ttu-id="761b6-281">Einstellung **Zugriff aktivieren**: __Microsoft Intune-Konfiguration lesen und schreiben__</span><span class="sxs-lookup"><span data-stu-id="761b6-281">**Enable Access** setting: __Read and write Microsoft Intune configuration__</span></span>

- <span data-ttu-id="761b6-282">Ermöglicht die gleichen Vorgänge wie „DeviceManagementServiceConfig.Read.All_“</span><span class="sxs-lookup"><span data-stu-id="761b6-282">Allows the same operations as DeviceManagementServiceConfig.Read.All_</span></span>

- <span data-ttu-id="761b6-283">Apps können auch die folgenden Intune-Features konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="761b6-283">Apps can also configure the following Intune features:</span></span>
    - <span data-ttu-id="761b6-284">Geräteregistrierung</span><span class="sxs-lookup"><span data-stu-id="761b6-284">Device Enrollment</span></span>
    - <span data-ttu-id="761b6-285">Apple Push Notification-Zertifikat</span><span class="sxs-lookup"><span data-stu-id="761b6-285">Apple Push Notification Certificate</span></span>
    - <span data-ttu-id="761b6-286">Apple-Programm zur Geräteregistrierung</span><span class="sxs-lookup"><span data-stu-id="761b6-286">Apple Device Enrollment Program</span></span>
    - <span data-ttu-id="761b6-287">Apple Volume Purchase Program</span><span class="sxs-lookup"><span data-stu-id="761b6-287">Apple Volume Purchase Program</span></span>
    - <span data-ttu-id="761b6-288">Exchange-Connector</span><span class="sxs-lookup"><span data-stu-id="761b6-288">Exchange Connector</span></span>
    - <span data-ttu-id="761b6-289">Geschäftsbedingungen</span><span class="sxs-lookup"><span data-stu-id="761b6-289">Terms and Conditions</span></span>
    - <span data-ttu-id="761b6-290">Verwaltung von Ausgaben für Telekommunikation</span><span class="sxs-lookup"><span data-stu-id="761b6-290">Telecoms Expense Management</span></span>
    - <span data-ttu-id="761b6-291">PKI in der Cloud</span><span class="sxs-lookup"><span data-stu-id="761b6-291">Cloud PKI</span></span>
    - <span data-ttu-id="761b6-292">Branding</span><span class="sxs-lookup"><span data-stu-id="761b6-292">Branding</span></span>
    - <span data-ttu-id="761b6-293">Mobile Threat Defense</span><span class="sxs-lookup"><span data-stu-id="761b6-293">Mobile Threat Defense</span></span>

## <a name="azure-ad-authentication-examples"></a><span data-ttu-id="761b6-294">Beispiele für die Azure AD-Authentifizierung</span><span class="sxs-lookup"><span data-stu-id="761b6-294">Azure AD authentication examples</span></span>

<span data-ttu-id="761b6-295">In diesem Abschnitt wird gezeigt, wie Azure AD in Ihre C#- und PowerShell-Projekte integriert wird.</span><span class="sxs-lookup"><span data-stu-id="761b6-295">This section shows how to incorporate Azure AD into your C# and PowerShell projects.</span></span>

<span data-ttu-id="761b6-296">Bei jedem Beispiel müssen Sie eine Anwendungs-ID angeben, die mindestens den Berechtigungsbereich `DeviceManagementManagedDevices.Read.All` hat (siehe oben).</span><span class="sxs-lookup"><span data-stu-id="761b6-296">In each example, you'll need to specify an application ID that has at least the `DeviceManagementManagedDevices.Read.All` permission scope (discussed earlier).</span></span>

<span data-ttu-id="761b6-297">Wenn Sie eines der Beispiel testen, erhalten Sie ggf. die HTTP-Statusfehlermeldung 403 (Unzulässig):</span><span class="sxs-lookup"><span data-stu-id="761b6-297">When testing either example, you may receive HTTP status 403 (Forbidden) errors similar to the following:</span></span>

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

<span data-ttu-id="761b6-298">Wenn dies erfolgt, überprüfen Sie Folgendes:</span><span class="sxs-lookup"><span data-stu-id="761b6-298">If this happens, verify that:</span></span>

- <span data-ttu-id="761b6-299">Ob Sie die Anwendungs-ID in eine ID geändert haben, die für das Verwenden der Graph-API und des Berechtigungsbereichs `DeviceManagementManagedDevices.Read.All` autorisiert ist.</span><span class="sxs-lookup"><span data-stu-id="761b6-299">You've updated the application ID to one authorized to use the Graph API and the `DeviceManagementManagedDevices.Read.All` permission scope.</span></span>

- <span data-ttu-id="761b6-300">Ob die Anmeldeinformationen Ihres Mandanten administrative Funktionen unterstützen.</span><span class="sxs-lookup"><span data-stu-id="761b6-300">Your tenant credentials support administrative functions.</span></span>

- <span data-ttu-id="761b6-301">Ob Ihr Code den gezeigten Beispielen ähnlich ist.</span><span class="sxs-lookup"><span data-stu-id="761b6-301">Your code is similar to the displayed samples.</span></span>


### <a name="authenticate-azure-ad-in-c"></a><span data-ttu-id="761b6-302">Authentifizieren von Azure AD in C\#</span><span class="sxs-lookup"><span data-stu-id="761b6-302">Authenticate Azure AD in C\#</span></span>

<span data-ttu-id="761b6-303">Dieses Beispiel zeigt, wie Sie C# zum Abrufen einer Liste von Geräten verwenden, die Ihrem Intune-Konto zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="761b6-303">This example shows how to use C# to retrieve a list of devices associated with your Intune account.</span></span>

1.  <span data-ttu-id="761b6-304">Starten Sie Visual Studio, und erstellen Sie dann ein neues Visual C#-App-Konsolenprojekt (.NET Framework).</span><span class="sxs-lookup"><span data-stu-id="761b6-304">Start Visual Studio and then create a new Visual C# Console app (.NET Framework) project.</span></span>

2.  <span data-ttu-id="761b6-305">Geben Sie einen Namen für das Projekt und nach Wunsch weitere Details ein.</span><span class="sxs-lookup"><span data-stu-id="761b6-305">Enter a name for your project and provide other details as desired.</span></span>

    <img src="media/aad-auth-cpp-new-console.png" width="624" height="433" alt="Creating a C# console app project in Visual Studio"  />

3.  <span data-ttu-id="761b6-306">Fügen Sie im Projektmappen-Explorer das NuGet-Paket mit der Microsoft ADAL dem Projekt hinzu.</span><span class="sxs-lookup"><span data-stu-id="761b6-306">Use the Solution Explorer to add the Microsoft ADAL NuGet package to the project.</span></span>

    1.  <span data-ttu-id="761b6-307">Klicken Sie mit der rechten Maustaste auf den Projektmappen-Explorer.</span><span class="sxs-lookup"><span data-stu-id="761b6-307">Right-click the Solution Explorer.</span></span>
    2.  <span data-ttu-id="761b6-308">Wählen Sie **NuGet-Pakete verwalten**</span><span class="sxs-lookup"><span data-stu-id="761b6-308">Choose **Manage NuGet Packages…**</span></span> <span data-ttu-id="761b6-309">&gt; **Durchsuchen** aus.</span><span class="sxs-lookup"><span data-stu-id="761b6-309">&gt; **Browse**.</span></span>
    3.  <span data-ttu-id="761b6-310">Wählen Sie `Microsoft.IdentityModel.Clients.ActiveDirectory` aus, und klicken Sie anschließend auf **Installieren**.</span><span class="sxs-lookup"><span data-stu-id="761b6-310">Select `Microsoft.IdentityModel.Clients.ActiveDirectory` and then choose **Install**.</span></span>

    <img src="media/aad-auth-cpp-install-package.png" width="624" height="458" alt="Selecting the Azure AD identity model module" />

4.  <span data-ttu-id="761b6-311">Fügen Sie am Anfang der Datei **Program.cs** die folgenden Anweisungen ein:</span><span class="sxs-lookup"><span data-stu-id="761b6-311">Add the following statements to the top of **Program.cs**:</span></span>

    ``` csharp
    using Microsoft.IdentityModel.Clients.ActiveDirectory;</p>
    using System.Net.Http;
    ```

5.  <span data-ttu-id="761b6-312">Fügen Sie eine Methode zum Erstellen des Autorisierungsheaders hinzu:</span><span class="sxs-lookup"><span data-stu-id="761b6-312">Add a method to create the authorization header:</span></span>

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

    <span data-ttu-id="761b6-313">Ändern Sie den Wert von `application_ID` entsprechend in einen Wert, der dem Berechtigungsbereich `DeviceManagementManagedDevices.Read.All` mindestens erteilt wurde (siehe oben).</span><span class="sxs-lookup"><span data-stu-id="761b6-313">Remember to change the value of `application_ID` to match one granted at least the `DeviceManagementManagedDevices.Read.All` permission scope, as described earlier.</span></span>

6. <span data-ttu-id="761b6-314">Fügen Sie eine Methode zum Abrufen der Geräteliste hinzu:</span><span class="sxs-lookup"><span data-stu-id="761b6-314">Add a method to retrieve the list of devices:</span></span>

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

7.  <span data-ttu-id="761b6-315">Ändern Sie **Main** so, dass **GetMyManagedDevices** aufgerufen wird:</span><span class="sxs-lookup"><span data-stu-id="761b6-315">Update **Main** to call **GetMyManagedDevices**:</span></span>

    ``` csharp
    string devices = GetMyManagedDevices().GetAwaiter().GetResult();
    Console.WriteLine(devices);
    ```

8.  <span data-ttu-id="761b6-316">Kompilieren Sie Ihr Programm, und führen Sie es aus.</span><span class="sxs-lookup"><span data-stu-id="761b6-316">Compile and run your program.</span></span>  

<span data-ttu-id="761b6-317">Wenn Sie das Programm erstmals ausführen, sollten Sie zwei Eingabeaufforderungen erhalten.</span><span class="sxs-lookup"><span data-stu-id="761b6-317">When you first run your program, you should receive two prompts.</span></span>  <span data-ttu-id="761b6-318">Die erste fordert Ihre Anmeldeinformationen an, die zweite erteilt Berechtigungen für die Anforderung `managedDevices`.</span><span class="sxs-lookup"><span data-stu-id="761b6-318">The first requests your credentials and the second grants permissions for the `managedDevices` request.</span></span>  

<span data-ttu-id="761b6-319">Zur Bezugnahme sehen Sie hier das vollständige Programm:</span><span class="sxs-lookup"><span data-stu-id="761b6-319">For reference, here's the completed program:</span></span>

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

### <a name="authenticate-azure-ad-powershell"></a><span data-ttu-id="761b6-320">Authentifizieren von Azure AD (PowerShell)</span><span class="sxs-lookup"><span data-stu-id="761b6-320">Authenticate Azure AD (PowerShell)</span></span>

<span data-ttu-id="761b6-321">Das folgende PowerShell-Skript verwendet das AzureAD-PowerShell-Modul zur Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="761b6-321">The following PowerShell script uses the AzureAD PowerShell module for authentication.</span></span>  <span data-ttu-id="761b6-322">Weitere Informationen finden Sie unter [Azure Active Directory PowerShell, Version 2](https://docs.microsoft.co/powershell/azure/install-adv2?view=azureadps-2.0) und [Intune PowerShell-Beispiele](https://github.com/microsoftgraph/powershell-intune-samples).</span><span class="sxs-lookup"><span data-stu-id="761b6-322">To learn more, see [Azure Active Directory PowerShell Version 2](https://docs.microsoft.co/powershell/azure/install-adv2?view=azureadps-2.0) and the [Intune PowerShell examples](https://github.com/microsoftgraph/powershell-intune-samples).</span></span>

<span data-ttu-id="761b6-323">In diesem Beispiel aktualisieren Sie den Wert von `$clientID` so, dass er einer gültigen Anwendungs-ID entspricht.</span><span class="sxs-lookup"><span data-stu-id="761b6-323">In this example, update the value of `$clientID` to match a valid application ID.</span></span>

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

## <a name="support-multiple-tenants-and-partners"></a><span data-ttu-id="761b6-324">Unterstützen mehrerer Mandanten und Partner</span><span class="sxs-lookup"><span data-stu-id="761b6-324">Support multiple tenants and partners</span></span>

<span data-ttu-id="761b6-325">Wenn Organisationen mit eigenen Azure AD-Mandanten von Ihrer Organisation unterstützt werden, möchten Sie ggf. Ihren Clients erlauben, Ihre Anwendung in ihren entsprechenden Mandanten zu nutzen.</span><span class="sxs-lookup"><span data-stu-id="761b6-325">If your organization supports organizations with their own Azure AD tenants, you may want to permit your clients to use your application with their respective tenants.</span></span>

<span data-ttu-id="761b6-326">Gehen Sie hierzu folgendermaßen vor:</span><span class="sxs-lookup"><span data-stu-id="761b6-326">To do so:</span></span>

1.  <span data-ttu-id="761b6-327">Stellen Sie sicher, dass das Konto im Azure AD-Zielmandanten vorhanden ist.</span><span class="sxs-lookup"><span data-stu-id="761b6-327">Verify that the client account exists in the target Azure AD tenant.</span></span>

2.  <span data-ttu-id="761b6-328">Stellen Sie sicher, dass Ihr Mandantenkonto die Registrierung von Anwendungen durch Benutzer zulässt (siehe **Benutzereinstellungen**).</span><span class="sxs-lookup"><span data-stu-id="761b6-328">Verify that your tenant account allows users to register applications (see **User settings**).</span></span>

3.  <span data-ttu-id="761b6-329">Richten Sie eine Beziehung zwischen jedem Mandanten ein.</span><span class="sxs-lookup"><span data-stu-id="761b6-329">Establish a relationship between each tenant.</span></span>  

    <span data-ttu-id="761b6-330">Gehen Sie hierfür so vor:</span><span class="sxs-lookup"><span data-stu-id="761b6-330">To do so, either:</span></span>

    <span data-ttu-id="761b6-331">ein.</span><span class="sxs-lookup"><span data-stu-id="761b6-331">a.</span></span> <span data-ttu-id="761b6-332">Definieren Sie im [Microsoft Partner Center](https://partnercenter.microsoft.com/) eine Beziehung mit Ihrem Client und seiner E-Mail-Adresse.</span><span class="sxs-lookup"><span data-stu-id="761b6-332">Use the [Microsoft Partner Center](https://partnercenter.microsoft.com/) to define a relationship with your client and their email address.</span></span>

    <span data-ttu-id="761b6-333">b.</span><span class="sxs-lookup"><span data-stu-id="761b6-333">b.</span></span> <span data-ttu-id="761b6-334">Laden Sie den Benutzer ein, Gast Ihres Mandanten zu werden.</span><span class="sxs-lookup"><span data-stu-id="761b6-334">Invite the user to become a guest of your tenant.</span></span>

<span data-ttu-id="761b6-335">So laden Sie den Benutzer ein, Gast Ihres Mandanten zu werden</span><span class="sxs-lookup"><span data-stu-id="761b6-335">To invite the user to be a guest of your tenant:</span></span>

1.  <span data-ttu-id="761b6-336">Wählen Sie **Gastbenutzer hinzufügen** im Bereich **Schnellaufgaben** aus.</span><span class="sxs-lookup"><span data-stu-id="761b6-336">Choose **Add a guest user** from the **Quick tasks** panel.</span></span>

    <img src="media/azure-ad-add-guest.png" width="448" height="138" alt="Use Quick Tasks to add a guest user" />

2.  <span data-ttu-id="761b6-337">Geben Sie die E-Mail-Adresse des Clients ein, und fügen Sie (optional) eine personalisierte Nachricht für die Einladung hinzu.</span><span class="sxs-lookup"><span data-stu-id="761b6-337">Enter the client's email address and (optionally) add a personalized message for the invite.</span></span>

    <img src="media/azure-ad-guest-invite.png" width="203" height="106" alt="Inviting an external user as a guest" />

3.  <span data-ttu-id="761b6-338">Klicken Sie auf **Einladen**.</span><span class="sxs-lookup"><span data-stu-id="761b6-338">Choose **Invite**.</span></span>

<span data-ttu-id="761b6-339">Dem Benutzer wird eine Einladung gesendet.</span><span class="sxs-lookup"><span data-stu-id="761b6-339">This sends an invite to the user.</span></span>

   <img src="media/aad-multiple-tenant-invitation.png" width="624" height="523" alt="A sample guest invitation" />


   <span data-ttu-id="761b6-340">Der Benutzer muss auf den Link **Erste Schritte** klicken, um Ihre Einladung anzunehmen.</span><span class="sxs-lookup"><span data-stu-id="761b6-340">The user needs to choose the **Get Started** link to accept your invitation.</span></span>

<span data-ttu-id="761b6-341">Nachdem die Beziehung eingerichtet oder Ihre Einladung akzeptiert wurde, fügen Sie das Benutzerkonto der **Verzeichnisrolle** hinzu.</span><span class="sxs-lookup"><span data-stu-id="761b6-341">When the relationship is established (or your invitation has been accepted), add the user account to the **Directory role**.</span></span>

<span data-ttu-id="761b6-342">Denken Sie daran, den Benutzer bei Bedarf anderen Rollen hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="761b6-342">Remember to add the user to other roles as needed.</span></span> <span data-ttu-id="761b6-343">Um beispielsweise dem Benutzer das Verwalten von Intune-Einstellungen zu erlauben, müssen Sie entweder ein **globaler Administrator** oder **Intune-Dienstadministrator** sein.</span><span class="sxs-lookup"><span data-stu-id="761b6-343">For example, to allow the user to manage Intune settings, they need to be either a **Global Administrator** or an **Intune Service administrator**.</span></span>

<span data-ttu-id="761b6-344">Ferner gilt Folgendes:</span><span class="sxs-lookup"><span data-stu-id="761b6-344">Also:</span></span>

- <span data-ttu-id="761b6-345">Verwenden Sie http://portal.office.com, um Ihrem Benutzerkonto eine Intune-Lizenz zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="761b6-345">Use http://portal.office.com to assign an Intune license to your user account.</span></span>

- <span data-ttu-id="761b6-346">Ändern Sie den Anwendungscode so, dass die Azure AD-Mandantendomäne des Clients und nicht Ihre eigene authentifiziert wird.</span><span class="sxs-lookup"><span data-stu-id="761b6-346">Update application code to authenticate to the client's Azure AD tenant domain, rather than your own.</span></span>

    <span data-ttu-id="761b6-347">Angenommen, die Mandantendomäne heißt `contosopartner.onmicrosoft.com` und die des Clients `northwind.onmicrosoft.com`. Sie müssen dann Ihren Code so ändern, dass Sie beim Mandanten des Clients authentifiziert werden.</span><span class="sxs-lookup"><span data-stu-id="761b6-347">For example, suppose your tenant domain is `contosopartner.onmicrosoft.com` and your client's tenant domain is `northwind.onmicrosoft.com`, you would update your code to authenticate to your client's tenant.</span></span>

    <span data-ttu-id="761b6-348">Um dies in einer C#-Anwendung basierend auf dem vorherigen Beispiel zu tun, ändern Sie den Wert der Variablen `authority`:</span><span class="sxs-lookup"><span data-stu-id="761b6-348">To do so in a C# application based on the earlier example, you'd change the value of the `authority` variable:</span></span>

    ``` csharp
    string authority = "https://login.microsoftonline.com/common/";
    ```

    <span data-ttu-id="761b6-349">in</span><span class="sxs-lookup"><span data-stu-id="761b6-349">to</span></span>

    ``` csharp
    string authority = "https://login.microsoftonline.com/northwind.onmicrosoft.com/";
    ```
