---
title: Abrufen von Daten aus der Data Warehouse-API mit einem REST-Client
description: Rufen Sie Daten aus dem Intune-Data Warehouse mit einer RESTful-API ab.
keywords: 
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 07/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: D6D15039-4036-446C-A58F-A5E18175720A
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: fb75d895a2100172fab337dcd740c076ff5e85b7
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2017
---
# <a name="get-data-from-the-intune-data-warehouse-api-with-a-rest-client"></a><span data-ttu-id="cb47d-103">Abrufen von Daten aus der Intune-Data Warehouse-API mit einem REST-Client</span><span class="sxs-lookup"><span data-stu-id="cb47d-103">Get data from the Intune Data Warehouse API with a REST client</span></span>

<span data-ttu-id="cb47d-104">Sie können auf das Intune-Data Warehouse-Datenmodell über RESTful-Endpunkte zugreifen.</span><span class="sxs-lookup"><span data-stu-id="cb47d-104">You can access the Intune Data Warehouse data model through RESTful endpoints.</span></span> <span data-ttu-id="cb47d-105">Um auf Ihre Daten zuzugreifen, muss sich der Client mithilfe von OAuth 2.0 bei Microsoft Azure Active Directory (Azure AD) autorisieren.</span><span class="sxs-lookup"><span data-stu-id="cb47d-105">To gain access to your data, your client must authorize with Microsoft Azure Active Directory (Azure AD) using OAuth 2.0.</span></span> <span data-ttu-id="cb47d-106">Richten Sie zum Aktivieren des Zugriffs zuerst eine native App in Azure ein, und erteilen Sie ihr Berechtigungen für die Microsoft Intune-API.</span><span class="sxs-lookup"><span data-stu-id="cb47d-106">To enable access, first set up a native app in Azure and grant permissions to the Microsoft Intune API.</span></span> <span data-ttu-id="cb47d-107">Ihr lokaler Client ruft die Autorisierung ab, und dann kann der Client über die native App mit den Data Warehouse-Endpunkten kommunizieren.</span><span class="sxs-lookup"><span data-stu-id="cb47d-107">Your local client gets authorization, and then the client can communicate with the Data Warehouse endpoints through the native app.</span></span>

<span data-ttu-id="cb47d-108">Für die Einrichtung eines Clients zum Abrufen von Daten aus der Data Warehouse-API bestehen die folgenden Anforderungen:</span><span class="sxs-lookup"><span data-stu-id="cb47d-108">The steps to set up a client to get data from the  Data Warehouse API require you to:</span></span>

1. <span data-ttu-id="cb47d-109">Erstellen Sie eine Client-App als eine native App in Azure.</span><span class="sxs-lookup"><span data-stu-id="cb47d-109">Create a client app as a native app in Azure</span></span>
3. <span data-ttu-id="cb47d-110">Erteilen Sie der Client-App Zugriff auf die Microsoft Intune-API.</span><span class="sxs-lookup"><span data-stu-id="cb47d-110">Grant the client app access to the Microsoft Intune API</span></span>
3. <span data-ttu-id="cb47d-111">Erstellen Sie einen lokalen REST-Client zum Abrufen der Daten.</span><span class="sxs-lookup"><span data-stu-id="cb47d-111">Create a local REST client to get the data</span></span>

<span data-ttu-id="cb47d-112">Aus den folgenden Schritten können Sie ersehen, wie Autorisierung und Zugriff auf eine API mit einem REST-Client erfolgen.</span><span class="sxs-lookup"><span data-stu-id="cb47d-112">Use the following steps to learn how to authorize and access the API with a REST client.</span></span> <span data-ttu-id="cb47d-113">Sehen wir uns zunächst einen generischen REST-Client am Beispiel von Postman an.</span><span class="sxs-lookup"><span data-stu-id="cb47d-113">First, you will look at using a generic REST client using Postman.</span></span> <span data-ttu-id="cb47d-114">Bei Postman handelt es sich um ein häufig verwendetes Tool zur Problembehandlung und Entwicklung von REST-Clients für APIs.</span><span class="sxs-lookup"><span data-stu-id="cb47d-114">Postman is a commonly used tool troubleshooting and developing REST clients to work with APIs.</span></span> <span data-ttu-id="cb47d-115">Weitere Informationen zu Postman finden Sie auf der [Postman](https://www.getpostman.com)-Website.</span><span class="sxs-lookup"><span data-stu-id="cb47d-115">For more information about Postman, see the [Postman](https://www.getpostman.com) site.</span></span> <span data-ttu-id="cb47d-116">Anschließend können Sie ein C#-Codebeispiel betrachten.</span><span class="sxs-lookup"><span data-stu-id="cb47d-116">Then you can look at a C# code sample.</span></span> <span data-ttu-id="cb47d-117">Darin wird gezeigt, wie ein Client autorisiert und Daten aus der API abgerufen werden.</span><span class="sxs-lookup"><span data-stu-id="cb47d-117">The sample provides an example for authorizing a client and getting data from the API.</span></span>

## <a name="create-a-client-app-as-a-native-app-in-azure"></a><span data-ttu-id="cb47d-118">Erstellen Sie eine Client-App als eine native App in Azure.</span><span class="sxs-lookup"><span data-stu-id="cb47d-118">Create a client app as a native app in Azure</span></span>

<span data-ttu-id="cb47d-119">Erstellen Sie eine native App in Azure.</span><span class="sxs-lookup"><span data-stu-id="cb47d-119">Create a native app in Azure.</span></span> <span data-ttu-id="cb47d-120">Diese native App ist die Client-App.</span><span class="sxs-lookup"><span data-stu-id="cb47d-120">This native app is the client app.</span></span> <span data-ttu-id="cb47d-121">Der Client auf dem lokalen Computer verweist auf die Intune-Data Warehouse-API, wenn der lokale Client Anmeldeinformationen anfordert.</span><span class="sxs-lookup"><span data-stu-id="cb47d-121">The client running on your local machine references the Intune Data Warehouse API when the local client requests credentials.</span></span> 

1. <span data-ttu-id="cb47d-122">Melden Sie sich für Ihren Mandanten beim Azure-Portal an.</span><span class="sxs-lookup"><span data-stu-id="cb47d-122">Sign in to the Azure portal for your tenant.</span></span> <span data-ttu-id="cb47d-123">Klicken Sie auf **Azure Active Directory** > **App-Registrierungen**, um das Blatt **App-Registrierungen** zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="cb47d-123">Choose **Azure Active Directory** > **App Registrations** to open the **App registrations** blade.</span></span>
2. <span data-ttu-id="cb47d-124">Wählen Sie **New app registration** (Neue App-Registrierung) aus.</span><span class="sxs-lookup"><span data-stu-id="cb47d-124">Select **New app registration**.</span></span>
3. <span data-ttu-id="cb47d-125">Geben Sie die App-Informationen ein.</span><span class="sxs-lookup"><span data-stu-id="cb47d-125">Type the app details.</span></span>
    1.  <span data-ttu-id="cb47d-126">Geben Sie unter **Name** einen Anzeigenamen wie „Intune-Data Warehouse-Client“ ein.</span><span class="sxs-lookup"><span data-stu-id="cb47d-126">Type a friendly name, such as Intune Data Warehouse Client, for the **Name**.</span></span>
    2.  <span data-ttu-id="cb47d-127">Wählen Sie für den **Anwendungstyp** die Option **Nativ** aus.</span><span class="sxs-lookup"><span data-stu-id="cb47d-127">Select **Native** for the **Application type**.</span></span>
    3.  <span data-ttu-id="cb47d-128">Geben Sie eine URL als **Anmelde-URL** ein.</span><span class="sxs-lookup"><span data-stu-id="cb47d-128">Type a URL for the **Sign-on URL**.</span></span> <span data-ttu-id="cb47d-129">Die Anmelde-URL richtet sich nach dem jeweiligen Szenario. Wenn Sie jedoch planen, Postman zu verwenden, geben Sie `https://www.getpostman.com/oauth2/callback` ein.</span><span class="sxs-lookup"><span data-stu-id="cb47d-129">The Sign-on URL will depend on the specific scenario, however if you plan on using Postman, type `https://www.getpostman.com/oauth2/callback`.</span></span> <span data-ttu-id="cb47d-130">Sie verwenden bei der Authentifizierung in Azure AD den Schritt zum Rückruf der Client-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="cb47d-130">You will use the callback for client authentication step when authenticating to Azure AD.</span></span>
4.  <span data-ttu-id="cb47d-131">Wählen Sie **Erstellen** aus.</span><span class="sxs-lookup"><span data-stu-id="cb47d-131">Select **Create**.</span></span>

     ![Intune Data Warehouse-API](media\reports-get_rest_data_client_overview.png)

5. <span data-ttu-id="cb47d-133">Notieren Sie sich die **Anwendungs-ID** dieser App.</span><span class="sxs-lookup"><span data-stu-id="cb47d-133">Note the **Application ID** of this app.</span></span> <span data-ttu-id="cb47d-134">Sie benötigen sie im nächsten Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="cb47d-134">You will use the ID in the next section.</span></span>

## <a name="grant-the-client-app-access-to-the-microsoft-intune-api"></a><span data-ttu-id="cb47d-135">Erteilen Sie der Client-App Zugriff auf die Microsoft Intune-API.</span><span class="sxs-lookup"><span data-stu-id="cb47d-135">Grant the client app access to the Microsoft Intune API</span></span>

<span data-ttu-id="cb47d-136">Sie haben jetzt eine in Azure definierte App.</span><span class="sxs-lookup"><span data-stu-id="cb47d-136">You now have an app defined in Azure.</span></span> <span data-ttu-id="cb47d-137">Erteilen Sie Zugriff von der nativen App auf die Microsoft Intune-API.</span><span class="sxs-lookup"><span data-stu-id="cb47d-137">Grant access from the native app to the Microsoft Intune API.</span></span>

1.  <span data-ttu-id="cb47d-138">Wählen Sie die native App aus.</span><span class="sxs-lookup"><span data-stu-id="cb47d-138">Select the native app.</span></span> <span data-ttu-id="cb47d-139">Sie haben der App einen Namen wie **Intune-Data Warehouse-Client** gegeben.</span><span class="sxs-lookup"><span data-stu-id="cb47d-139">You named the app something such as **Intune Data Warehouse Client**.</span></span>
2.  <span data-ttu-id="cb47d-140">Wählen Sie auf dem Blatt **Einstellungen** **Erforderliche Berechtigungen** aus.</span><span class="sxs-lookup"><span data-stu-id="cb47d-140">Select **Required permissions** from the **Settings** blade</span></span>
3.  <span data-ttu-id="cb47d-141">Wählen Sie auf dem Blatt **Erforderliche Berechtigungen** **Hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="cb47d-141">Select **Add** in the **Required permissions** blade.</span></span>
4.  <span data-ttu-id="cb47d-142">Wählen Sie **Hiermit wählen Sie eine API aus** aus.</span><span class="sxs-lookup"><span data-stu-id="cb47d-142">Select **Select an API**.</span></span>
5.  <span data-ttu-id="cb47d-143">Suchen Sie nach dem Namen der Web-App.</span><span class="sxs-lookup"><span data-stu-id="cb47d-143">Search for the web app name.</span></span> <span data-ttu-id="cb47d-144">Sie heißt **Microsoft Intune-API**.</span><span class="sxs-lookup"><span data-stu-id="cb47d-144">It is named **Microsoft Intune API**.</span></span>
6.  <span data-ttu-id="cb47d-145">Wählen Sie die App in der Liste aus.</span><span class="sxs-lookup"><span data-stu-id="cb47d-145">Select the app in the list.</span></span>
7.  <span data-ttu-id="cb47d-146">Wählen Sie **Auswählen** aus.</span><span class="sxs-lookup"><span data-stu-id="cb47d-146">Select **Select**.</span></span>
8.  <span data-ttu-id="cb47d-147">Aktivieren Sie das Kontrollkästchen **Delegierte Berechtigungen**, um **Get data warehouse information from Microsoft Intune** (Data Warehouse-Informationen aus Microsoft Intune abrufen) hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="cb47d-147">Check the **Delegated Permissions** box to add **Get data warehouse information from Microsoft Intune**.</span></span>

    ![Zugriff aktivieren](media\reports-get_rest_data_client_access.png)

9.  <span data-ttu-id="cb47d-149">Wählen Sie **Auswählen** aus.</span><span class="sxs-lookup"><span data-stu-id="cb47d-149">Select **Select**.</span></span>
10.  <span data-ttu-id="cb47d-150">Wählen Sie **Fertig** aus.</span><span class="sxs-lookup"><span data-stu-id="cb47d-150">Select **Done**.</span></span>
11.  <span data-ttu-id="cb47d-151">Wählen Sie optional auch auf dem Blatt „Erforderliche Berechtigungen“ **Berechtigungen erteilen** aus.</span><span class="sxs-lookup"><span data-stu-id="cb47d-151">Optionally, Select **Grant Permissions** in the Required permissions blade.</span></span> <span data-ttu-id="cb47d-152">Dadurch wird der Zugriff auf alle Konten im aktuellen Verzeichnis gewährt.</span><span class="sxs-lookup"><span data-stu-id="cb47d-152">This will grant access to all accounts in the current directory.</span></span> <span data-ttu-id="cb47d-153">Außerdem wird so verhindert, dass das Zustimmungsdialogfeld für jeden Benutzer im Mandanten angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="cb47d-153">This will prevent the consent dialog box from appearing for every user in the tenant.</span></span> <span data-ttu-id="cb47d-154">Weitere Informationen finden Sie unter [Integrieren von Anwendungen in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/develop/active-directory-integrating-applications).</span><span class="sxs-lookup"><span data-stu-id="cb47d-154">For more information, see [Integrating applications with Azure Active Directory](https://docs.microsoft.com/azure/active-directory/develop/active-directory-integrating-applications).</span></span>
12.  <span data-ttu-id="cb47d-155">Wählen Sie **Ja** aus.</span><span class="sxs-lookup"><span data-stu-id="cb47d-155">Select **Yes**.</span></span>

## <a name="get-data-from-the-microsoft-intune-api-with-postman"></a><span data-ttu-id="cb47d-156">Abrufen von Daten aus der Microsoft Intune-API mit Postman</span><span class="sxs-lookup"><span data-stu-id="cb47d-156">Get data from the Microsoft Intune API with Postman</span></span>

<span data-ttu-id="cb47d-157">Sie können mit der Intune-Data Warehouse-API und einem generischen REST-Client wie Postman arbeiten.</span><span class="sxs-lookup"><span data-stu-id="cb47d-157">You can work with the Intune Data Warehouse API with a generic REST client such as Postman.</span></span> <span data-ttu-id="cb47d-158">Postman kann einen Einblick in die Funktionen der API und das zugrunde liegende OData-Datenmodell sowie eine Problembehandlung für die Verbindung mit den API-Ressourcen durchführen.</span><span class="sxs-lookup"><span data-stu-id="cb47d-158">Postman can  provide insight into the features of the API, the underlying OData data model, and troubleshoot your  connection to the API resources.</span></span> <span data-ttu-id="cb47d-159">In diesem Abschnitt finden Sie Informationen zum Generieren eines Auth2.0-Tokens für den lokalen Client.</span><span class="sxs-lookup"><span data-stu-id="cb47d-159">In this section, you can find information about generating an Auth2.0 token for your local client.</span></span> <span data-ttu-id="cb47d-160">Der Client benötigt das Token zum Authentifizieren bei Azure AD und den Zugriff auf die API-Ressourcen.</span><span class="sxs-lookup"><span data-stu-id="cb47d-160">The client will need the token to authenticate with Azure AD and access the API resources.</span></span>

### <a name="information-you-will-need-to-make-the-call"></a><span data-ttu-id="cb47d-161">Informationen, die Sie für den Aufruf benötigen</span><span class="sxs-lookup"><span data-stu-id="cb47d-161">Information you will need to make the call</span></span>

<span data-ttu-id="cb47d-162">Sie benötigen die folgenden Informationen für einen REST-Aufruf mit Postman:</span><span class="sxs-lookup"><span data-stu-id="cb47d-162">You need the following information to make a REST call using Postman:</span></span>

| <span data-ttu-id="cb47d-163">Attribut</span><span class="sxs-lookup"><span data-stu-id="cb47d-163">Attribute</span></span>        | <span data-ttu-id="cb47d-164">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cb47d-164">Description</span></span>                                                                                                                                                                          | <span data-ttu-id="cb47d-165">Beispiel</span><span class="sxs-lookup"><span data-stu-id="cb47d-165">Example</span></span>                                                                                       |
|------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------|
| <span data-ttu-id="cb47d-166">Rückruf-URL</span><span class="sxs-lookup"><span data-stu-id="cb47d-166">Callback URL</span></span>     | <span data-ttu-id="cb47d-167">Legen Sie dies auf der Seite „Einstellungen“ Ihrer App als die Rückruf-URL fest.</span><span class="sxs-lookup"><span data-stu-id="cb47d-167">Set this as the callback URL in your app settings page.</span></span>                                                                                                                              | <span data-ttu-id="cb47d-168">https://www.getpostman.com/oauth2/callback</span><span class="sxs-lookup"><span data-stu-id="cb47d-168">https://www.getpostman.com/oauth2/callback</span></span>                                                    |
| <span data-ttu-id="cb47d-169">Tokenname</span><span class="sxs-lookup"><span data-stu-id="cb47d-169">Token Name</span></span>       | <span data-ttu-id="cb47d-170">Eine Zeichenfolge, mit der die Anmeldeinformationen der Azure-App übergeben werden.</span><span class="sxs-lookup"><span data-stu-id="cb47d-170">A string used to pass the credentials to the Azure app.</span></span> <span data-ttu-id="cb47d-171">Der Prozess generiert Ihr Token, sodass Sie die Data Warehouse-API aufrufen können.</span><span class="sxs-lookup"><span data-stu-id="cb47d-171">The process generates your token so you can make a call to the Data Warehouse API.</span></span>                          | <span data-ttu-id="cb47d-172">Bearer</span><span class="sxs-lookup"><span data-stu-id="cb47d-172">Bearer</span></span>                                                                                        |
| <span data-ttu-id="cb47d-173">Authentifizierungs-URL</span><span class="sxs-lookup"><span data-stu-id="cb47d-173">Auth URL</span></span>         | <span data-ttu-id="cb47d-174">Dies ist die URL, die zum Authentifizieren verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="cb47d-174">This is the URL used to authenticate.</span></span> | <span data-ttu-id="cb47d-175">https://login.microsoftonline.com/common/oauth2/authorize?resource=https://api.manage.microsoft.com/</span><span class="sxs-lookup"><span data-stu-id="cb47d-175">https://login.microsoftonline.com/common/oauth2/authorize?resource=https://api.manage.microsoft.com/</span></span> |
| <span data-ttu-id="cb47d-176">Zugriffstoken-URL</span><span class="sxs-lookup"><span data-stu-id="cb47d-176">Access Token URL</span></span> | <span data-ttu-id="cb47d-177">Mit dieser URL wird das Token erteilt.</span><span class="sxs-lookup"><span data-stu-id="cb47d-177">This is the URL used to grant the token.</span></span>                                                                                                                                              | <span data-ttu-id="cb47d-178">https://login.microsoftonline.com/common/oauth2/token</span><span class="sxs-lookup"><span data-stu-id="cb47d-178">https://login.microsoftonline.com/common/oauth2/token</span></span> |
| <span data-ttu-id="cb47d-179">Client-ID</span><span class="sxs-lookup"><span data-stu-id="cb47d-179">Client ID</span></span>        | <span data-ttu-id="cb47d-180">Diese haben Sie erstellt und sich bei der Erstellung der nativen App in Azure notiert.</span><span class="sxs-lookup"><span data-stu-id="cb47d-180">You created, and noted this when creating the native app in Azure.</span></span>                                                                                               | <span data-ttu-id="cb47d-181">4184c61a-e324-4f51-83d7-022b6a81b991</span><span class="sxs-lookup"><span data-stu-id="cb47d-181">4184c61a-e324-4f51-83d7-022b6a81b991</span></span>                                                          |
| <span data-ttu-id="cb47d-182">Bereich (Optional)</span><span class="sxs-lookup"><span data-stu-id="cb47d-182">Scope (Optional)</span></span> | <span data-ttu-id="cb47d-183">Leer</span><span class="sxs-lookup"><span data-stu-id="cb47d-183">Blank</span></span>                                                                                                                                                                               | <span data-ttu-id="cb47d-184">Sie können das Feld leer lassen.</span><span class="sxs-lookup"><span data-stu-id="cb47d-184">You can leave the field blank.</span></span>                                                                     |
| <span data-ttu-id="cb47d-185">Gewährungstyp</span><span class="sxs-lookup"><span data-stu-id="cb47d-185">Grant Type</span></span>       | <span data-ttu-id="cb47d-186">Das Token ist ein Autorisierungscode.</span><span class="sxs-lookup"><span data-stu-id="cb47d-186">The token is an authorization code.</span></span>                                                                                                                                                  | <span data-ttu-id="cb47d-187">Autorisierungscode</span><span class="sxs-lookup"><span data-stu-id="cb47d-187">Authorization code</span></span>                                                                            |

### <a name="odata-endpoint"></a><span data-ttu-id="cb47d-188">OData-Endpunkt</span><span class="sxs-lookup"><span data-stu-id="cb47d-188">OData endpoint</span></span>

<span data-ttu-id="cb47d-189">Sie benötigen außerdem den Endpunkt.</span><span class="sxs-lookup"><span data-stu-id="cb47d-189">You also need the endpoint.</span></span> <span data-ttu-id="cb47d-190">Um Ihren Data Warehouse-Endpunkt abzurufen, benötigen Sie die URL des benutzerdefinierten Feeds.</span><span class="sxs-lookup"><span data-stu-id="cb47d-190">To get your Data Warehouse endpoint, you will need the custom feed URL.</span></span> <span data-ttu-id="cb47d-191">Sie können den OData-Endpunkt auf dem Data Warehouse-Blatt erfahren.</span><span class="sxs-lookup"><span data-stu-id="cb47d-191">You can get the OData endpoint from the Data Warehouse blade.</span></span>

1. <span data-ttu-id="cb47d-192">Melden Sie sich im Azure-Portal an.</span><span class="sxs-lookup"><span data-stu-id="cb47d-192">Sign in to the Azure portal.</span></span>
2. <span data-ttu-id="cb47d-193">Wählen Sie **Weitere Dienste** > **Überwachung und Verwaltung** + **Intune** aus.</span><span class="sxs-lookup"><span data-stu-id="cb47d-193">Choose **More Services** > **Monitoring + Management** + **Intune**.</span></span>
3. <span data-ttu-id="cb47d-194">Wählen Sie unter **Andere Aufgaben** **Intune Data Warehouse einrichten** aus.</span><span class="sxs-lookup"><span data-stu-id="cb47d-194">Select **Set up Intune Data Warehouse** under **Other tasks**.</span></span>
4. <span data-ttu-id="cb47d-195">Kopieren Sie die URL des benutzerdefinierten Feeds unter **Berichterstellungsdienste von Drittanbietern verwenden**.</span><span class="sxs-lookup"><span data-stu-id="cb47d-195">Copy the custom feed url under **Use third-party reporting services**.</span></span> <span data-ttu-id="cb47d-196">Sie sollte etwa wie folgt aussehen: `https://fef.tenant.manage.microsoft.com/ReportingService/DataWarehouseFEService?api-version=beta`</span><span class="sxs-lookup"><span data-stu-id="cb47d-196">It should look something like: `https://fef.tenant.manage.microsoft.com/ReportingService/DataWarehouseFEService?api-version=beta`</span></span>

<span data-ttu-id="cb47d-197">Der Endpunkt weist das folgende Format auf: `https://fef.{yourtenant}.manage.microsoft.com/ReportingService/DataWarehouseFEService/{entity}?api-version={verson-number}`.</span><span class="sxs-lookup"><span data-stu-id="cb47d-197">The endpoint follows the following format: `https://fef.{yourtenant}.manage.microsoft.com/ReportingService/DataWarehouseFEService/{entity}?api-version={verson-number}`.</span></span> 

<span data-ttu-id="cb47d-198">Beispielsweise sieht die Entität **dates** wie folgt aus: `https://fef.tenant.manage.microsoft.com/ReportingService/DataWarehouseFEService/dates?api-version=beta`</span><span class="sxs-lookup"><span data-stu-id="cb47d-198">For example, the **dates** entity looks like: `https://fef.tenant.manage.microsoft.com/ReportingService/DataWarehouseFEService/dates?api-version=beta`</span></span>

<span data-ttu-id="cb47d-199">Weitere Informationen finden Sie unter [Intune Data Warehouse-API-Endpunkt](reports-api-url.md).</span><span class="sxs-lookup"><span data-stu-id="cb47d-199">For more information, see [Intune Data Warehouse API endpoint](reports-api-url.md).</span></span>

### <a name="make-the-rest-call"></a><span data-ttu-id="cb47d-200">Ausführen des REST-Aufrufs</span><span class="sxs-lookup"><span data-stu-id="cb47d-200">Make the REST call</span></span>

<span data-ttu-id="cb47d-201">Um ein neues Zugriffstoken für Postman abzurufen, müssen Sie die URL der Azure AD-Autorisierung, Ihre Client-ID und den geheimen Clientschlüssel hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="cb47d-201">To get a new access token for Postman, you must add the Azure AD authorization URL, add your Client ID, and Client Secret.</span></span> <span data-ttu-id="cb47d-202">Postman lädt die Autorisierungsseite, auf der Sie Ihre Anmeldeinformationen eingeben.</span><span class="sxs-lookup"><span data-stu-id="cb47d-202">Postman will load the authorization page where you will type your credentials.</span></span>

#### <a name="add-the-information-used-to-request-the-token"></a><span data-ttu-id="cb47d-203">Fügen Sie die Informationen zum Anfordern des Tokens hinzu.</span><span class="sxs-lookup"><span data-stu-id="cb47d-203">Add the information used to request the token</span></span>

1.  <span data-ttu-id="cb47d-204">Wenn Sie es nicht bereits installiert haben, laden Sie Postman herunter.</span><span class="sxs-lookup"><span data-stu-id="cb47d-204">Download Postman if you do not already have it installed.</span></span> <span data-ttu-id="cb47d-205">Postman können Sie unter [www.getpostman](https://www.getpostman.com) herunterladen.</span><span class="sxs-lookup"><span data-stu-id="cb47d-205">To download Postman, see [www.getpostman](https://www.getpostman.com).</span></span>
2.  <span data-ttu-id="cb47d-206">Öffnen Sie Postman.</span><span class="sxs-lookup"><span data-stu-id="cb47d-206">Open Postman.</span></span> <span data-ttu-id="cb47d-207">Wählen Sie den HTTP-Vorgang **GET** aus.</span><span class="sxs-lookup"><span data-stu-id="cb47d-207">Choose the HTTP operation **GET**.</span></span>
3.  <span data-ttu-id="cb47d-208">Fügen Sie die Endpunkt-URL in die Adresse ein.</span><span class="sxs-lookup"><span data-stu-id="cb47d-208">Paste the endpoint URL into the address.</span></span> <span data-ttu-id="cb47d-209">Sie sollte etwa wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="cb47d-209">It should look something like:</span></span>  

    `https://fef.tenant.manage.microsoft.com/ReportingService/DataWarehouseFEService/dates?api-version=beta`
4.  <span data-ttu-id="cb47d-210">Klicken Sie auf die Registerkarte **Autorisierung**, und wählen Sie aus der Liste **Typ** die Option **OAuth 2.0** aus.</span><span class="sxs-lookup"><span data-stu-id="cb47d-210">Choose the **Authorization** tab, and select **OAuth 2.0** from the **Type** list.</span></span>
5.  <span data-ttu-id="cb47d-211">Wählen Sie **Get New Access Token** (Neues Zugriffstoken abrufen) aus.</span><span class="sxs-lookup"><span data-stu-id="cb47d-211">Select **Get New Access Token**.</span></span>
6.  <span data-ttu-id="cb47d-212">Stellen Sie sicher, dass Sie die Rückruf-URL bereits zu Ihrer App in Azure hinzugefügt haben.</span><span class="sxs-lookup"><span data-stu-id="cb47d-212">Verify that you have already added the Callback URL to your app in Azure.</span></span> <span data-ttu-id="cb47d-213">Die Rückruf-URL lautet `https://www.getpostman.com/oauth2/callback`.</span><span class="sxs-lookup"><span data-stu-id="cb47d-213">The Callback URL is `https://www.getpostman.com/oauth2/callback`.</span></span>
7.  <span data-ttu-id="cb47d-214">Geben Sie „Bearer“ als **Tokenname** ein.</span><span class="sxs-lookup"><span data-stu-id="cb47d-214">Type Bearer for the **Token Name**.</span></span>
8.  <span data-ttu-id="cb47d-215">Fügen Sie die **Authentifizierungs-URL** hinzu.</span><span class="sxs-lookup"><span data-stu-id="cb47d-215">Add the **Auth URL**.</span></span> <span data-ttu-id="cb47d-216">Sie sollte etwa wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="cb47d-216">It should look something like:</span></span>  

    `https://login.microsoftonline.com/common/oauth2/authorize?resource=https://api.manage.microsoft.com/`
9.  <span data-ttu-id="cb47d-217">Fügen Sie das **Zugriffstoken** hinzu.</span><span class="sxs-lookup"><span data-stu-id="cb47d-217">Add the **Access Token URL**.</span></span> <span data-ttu-id="cb47d-218">Sie sollte etwa wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="cb47d-218">It should look something like:</span></span>  

     `https://login.microsoftonline.com/common/oauth2/token`

10. <span data-ttu-id="cb47d-219">Fügen Sie die **Client-ID** aus der nativen Anwendung hinzu, die Sie in Azure erstellt und `Intune Data Warehouse Client` genannt haben.</span><span class="sxs-lookup"><span data-stu-id="cb47d-219">Add the **Client ID** from the native app that you created in Azure and named `Intune Data Warehouse Client`.</span></span> <span data-ttu-id="cb47d-220">Sie sollte etwa wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="cb47d-220">It should look something like:</span></span>  

     `88C8527B-59CB-4679-A9C8-324941748BB4`

11. <span data-ttu-id="cb47d-221">Wählen Sie **Autorisierungscode** und „Request access token locally“ (Zugriffstoken lokal anfordern) aus.</span><span class="sxs-lookup"><span data-stu-id="cb47d-221">Select **Authorization Code**, and Request access token locally.</span></span>

12. <span data-ttu-id="cb47d-222">Wählen Sie **Request Token** (Token anfordern) aus.</span><span class="sxs-lookup"><span data-stu-id="cb47d-222">Select **Request Token**.</span></span>

    ![Informationen für das Token](media\reports-postman_getnewtoken.png)

13. <span data-ttu-id="cb47d-224">Geben Sie Ihre Anmeldeinformationen auf der Azure AD-Autorisierungsseite ein.</span><span class="sxs-lookup"><span data-stu-id="cb47d-224">Type your credentials in the Active AD authorization page.</span></span> <span data-ttu-id="cb47d-225">Die Liste der Token in Postman enthält jetzt das Token mit dem Namen `Bearer`.</span><span class="sxs-lookup"><span data-stu-id="cb47d-225">The list of tokens in Postman now contains the token named `Bearer`.</span></span>
14. <span data-ttu-id="cb47d-226">Wählen Sie **Token verwenden** aus.</span><span class="sxs-lookup"><span data-stu-id="cb47d-226">Select **Use Token**.</span></span> <span data-ttu-id="cb47d-227">Die Liste der Header enthält den neuen Schlüsselwert von „Authorization“ (Autorisierung) und den Wert `Bearer <your-authorization-token>`.</span><span class="sxs-lookup"><span data-stu-id="cb47d-227">The list of headers contains the new key value of Authorization and the value `Bearer <your-authorization-token>`.</span></span>

#### <a name="send-the-call-to-the-endpoint-using-postman"></a><span data-ttu-id="cb47d-228">Senden des Aufrufs an den Endpunkt mit Postman</span><span class="sxs-lookup"><span data-stu-id="cb47d-228">Send the call to the endpoint using Postman</span></span>

1.  <span data-ttu-id="cb47d-229">Wählen Sie **Senden** aus.</span><span class="sxs-lookup"><span data-stu-id="cb47d-229">Select **Send**.</span></span>
2.  <span data-ttu-id="cb47d-230">Die Rückgabedaten werden im Antworttextfeld von Postman angezeigt.</span><span class="sxs-lookup"><span data-stu-id="cb47d-230">The return data appears in the Postman response body.</span></span>

    ![Postman 200OK](media\reports-postman_200OK.png)

## <a name="create-a-rest-client-c-to-get-data-from-the-intune-data-warehouse"></a><span data-ttu-id="cb47d-232">Erstellen eines REST-Clients (C#), um Daten aus der Intune-Data Warehouse-API abzurufen</span><span class="sxs-lookup"><span data-stu-id="cb47d-232">Create a REST client (C#) to get data from the Intune Data Warehouse</span></span>

<span data-ttu-id="cb47d-233">Das folgende Beispiel enthält einen einfachen REST-Client.</span><span class="sxs-lookup"><span data-stu-id="cb47d-233">The following sample contains a simple REST client.</span></span> <span data-ttu-id="cb47d-234">Der Code verwendet die **httpClient**-Klasse aus der .NET-Bibliothek.</span><span class="sxs-lookup"><span data-stu-id="cb47d-234">The code uses the **httpClient** class from the .Net library.</span></span> <span data-ttu-id="cb47d-235">Sobald der Client Anmeldeinformationen für Azure AD erhält, erstellt er einen GET REST-Aufruf, um die Datumsentität aus der Data Warehouse-API abzurufen.</span><span class="sxs-lookup"><span data-stu-id="cb47d-235">Once the client gains credentials to Azure AD, the client constructs a GET REST call to retrieve the dates entity from the Data Warehouse API.</span></span>

> [!Note]  
> <span data-ttu-id="cb47d-236">Sie können [auf GitHub](https://github.com/Microsoft/Intune-Data-Warehouse/blob/master/Samples/CSharp/Program.cs) auf das folgende Codebeispiel zugreifen.</span><span class="sxs-lookup"><span data-stu-id="cb47d-236">You can access the following code [sample on GitHub](https://github.com/Microsoft/Intune-Data-Warehouse/blob/master/Samples/CSharp/Program.cs).</span></span> <span data-ttu-id="cb47d-237">Im GitHub-Repository finden Sie auch die neuesten Änderungen und Updates des Beispiels.</span><span class="sxs-lookup"><span data-stu-id="cb47d-237">Refer to the GitHub repo for the latest changes and updates to the sample.</span></span>

1.  <span data-ttu-id="cb47d-238">Öffnen Sie **Microsoft Visual Studio**.</span><span class="sxs-lookup"><span data-stu-id="cb47d-238">Open **Microsoft Visual Studio**.</span></span>
2.  <span data-ttu-id="cb47d-239">Klicken Sie auf **Datei** > **Neues Projekt**.</span><span class="sxs-lookup"><span data-stu-id="cb47d-239">Choose **File** > **New Project**.</span></span> <span data-ttu-id="cb47d-240">Erweitern Sie **Visual C#**, und wählen Sie **Konsolen-App (.NET Framework)** aus.</span><span class="sxs-lookup"><span data-stu-id="cb47d-240">Expand **Visual C#**, and choose **Console App (.Net Framework)**.</span></span> 
3.  <span data-ttu-id="cb47d-241">Nennen Sie das Projekt ` IntuneDataWarehouseSamples`, navigieren Sie dorthin, wo Sie das Projekt speichern möchten, und wählen Sie dann **OK** aus.</span><span class="sxs-lookup"><span data-stu-id="cb47d-241">Name the project ` IntuneDataWarehouseSamples`, browse to where you would like to save the project, and then select **OK**.</span></span>
4.  <span data-ttu-id="cb47d-242">Klicken Sie mit der rechten Maustaste auf den Namen der Projektmappe im Projektmappen-Explorer, und wählen Sie dann **NuGet-Pakete für Projektmappe verwalten** aus.</span><span class="sxs-lookup"><span data-stu-id="cb47d-242">Right-click the name of the solution in the Solution Explorer, and then select **Manage NuGet Packages for Solution**.</span></span> <span data-ttu-id="cb47d-243">Wählen Sie **Durchsuchen** aus, und geben Sie dann `Microsoft.IdentityModel.Clients.ActiveDirectory` in das Suchfeld ein.</span><span class="sxs-lookup"><span data-stu-id="cb47d-243">Select **Browse**, and then type `Microsoft.IdentityModel.Clients.ActiveDirectory` in the search box.</span></span>
5. <span data-ttu-id="cb47d-244">Wählen Sie das Paket aus, wählen Sie unter „Manage Packages for Your Solution“ (Pakete für Ihre Projektmappe verwalten) das Projekt **IntuneDataWarehouseSamples** aus, und wählen Sie dann **Installieren** aus.</span><span class="sxs-lookup"><span data-stu-id="cb47d-244">Choose the package, select the **IntuneDataWarehouseSamples** project under Manage Packages for Your Solution, and then select **Install**.</span></span> 
6. <span data-ttu-id="cb47d-245">Wählen Sie **I Accept** (Ich stimme zu) aus, um die NuGet-Paketlizenz zu akzeptieren.</span><span class="sxs-lookup"><span data-stu-id="cb47d-245">Select **I Accept** to accept the NuGet package license.</span></span>
7. <span data-ttu-id="cb47d-246">Öffnen Sie `Program.cs` über den Projektmappen-Explorer.</span><span class="sxs-lookup"><span data-stu-id="cb47d-246">Open `Program.cs` from the Solution Explorer.</span></span>

    ![Projekt in Visual Studio](media\reports-get_rest_data_in.png)

8.  <span data-ttu-id="cb47d-248">Ersetzen Sie den Code in „Program.cs“ durch den folgenden Code:</span><span class="sxs-lookup"><span data-stu-id="cb47d-248">Replace the code in Program.cs with the following code:</span></span>  
    ```csharp
namespace IntuneDataWarehouseSamples
{
    using System;
    using System.Net.Http;
    using System.Net.Http.Headers;
    using Microsoft.IdentityModel.Clients.ActiveDirectory;

    class Program
    {
     static void Main(string[] args)
  {
   /**
    * TODO: Replace the below values with your own.
    * emailAddress - The email address of the user that you will authenticate as.
    *
    * password  - The password for the above email address.
    *    This is inline only for simplicity in this sample. We do not 
    *    recommend storing passwords in plaintext.
    *
    * applicationId - The application ID of the native app that was created in AAD.
    *
    * warehouseUrl   - The data warehouse URL for your tenant. This can be found in 
    *      the Azure portal.
    * 
    * collectionName - The name of the warehouse entity collection you would like to 
    *      access.
    */
   var emailAddress = "intuneadmin@yourcompany.com";
   var password = "password_of(intuneadmin@yourcompany.com)";
   var applicationId = "<Application ID>";
   var warehouseUrl = "https://fef.{yourinfo}.manage.microsoft.com/ReportingService/DataWarehouseFEService?api-version=beta";
   var collectionName = "dates";

   var adalContext = new AuthenticationContext("https://login.windows.net/common/oauth2/token");
   AuthenticationResult authResult = adalContext.AcquireTokenAsync(
    resource: "https://api.manage.microsoft.com/",
    clientId: applicationId,
    userCredential: new UserPasswordCredential(emailAddress, password)).Result;

   var httpClient = new HttpClient();
   httpClient.DefaultRequestHeaders.Authorization = new AuthenticationHeaderValue("Bearer", authResult.AccessToken);

   var uriBuilder = new UriBuilder(warehouseUrl);
   uriBuilder.Path += "/" + collectionName;

   HttpResponseMessage response = httpClient.GetAsync(uriBuilder.Uri).Result;

   Console.Write(response.Content.ReadAsStringAsync().Result);
   Console.ReadKey();
  }
    }
    ```

9.  <span data-ttu-id="cb47d-249">Aktualisieren Sie die `TODO`s im Codebeispiel.</span><span class="sxs-lookup"><span data-stu-id="cb47d-249">Update the `TODO`s in the code sample.</span></span>
10.  <span data-ttu-id="cb47d-250">Drücken Sie **STRG + F5**, um den Intune.DataWarehouseAPIClient im Debugmodus zu erstellen und auszuführen.</span><span class="sxs-lookup"><span data-stu-id="cb47d-250">Press **Ctrl + F5** to build and execute the Intune.DataWarehouseAPIClient client in Debug mode.</span></span>

    ![Im JSON-Format abgerufene Datumsentität](media\reports-get_rest_data_output.png)

11.  <span data-ttu-id="cb47d-252">Überprüfen Sie die Konsolenausgabe.</span><span class="sxs-lookup"><span data-stu-id="cb47d-252">Review the console output.</span></span> <span data-ttu-id="cb47d-253">Die Ausgabe enthält die Daten im JSON-Format, die aus der **Datumsentität** in Ihrem Intune-Mandanten abgerufen wurden.</span><span class="sxs-lookup"><span data-stu-id="cb47d-253">The output contains data in a JSON format pulled from the **dates** entity in your Intune tenant.</span></span>

## <a name="next-steps"></a><span data-ttu-id="cb47d-254">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="cb47d-254">Next steps</span></span>

<span data-ttu-id="cb47d-255">Informationen zur Autorisierung, der API-URL-Struktur und den OData-Endpunkten finden Sie unter [Endpunkt der Intune Data Warehouse-API](reports-api-url.md).</span><span class="sxs-lookup"><span data-stu-id="cb47d-255">You can find details on authorization, the API URL structure, and OData endpoints in [Use the Intune Data Warehouse API](reports-api-url.md).</span></span> 

<span data-ttu-id="cb47d-256">Auch im Intune Data Warehouse-Datenmodell finden Sie die in der API enthaltenen Datenentitäten.</span><span class="sxs-lookup"><span data-stu-id="cb47d-256">You can also refer to the Intune Data Warehouse Data Model to find the data entities contained in the API.</span></span> <span data-ttu-id="cb47d-257">Weitere Informationen finden Sie unter [Datenmodell von Data Warehouse](reports-ref-data-model.md).</span><span class="sxs-lookup"><span data-stu-id="cb47d-257">For more information, see [Intune Data Warehouse API Data Model](reports-ref-data-model.md)</span></span>