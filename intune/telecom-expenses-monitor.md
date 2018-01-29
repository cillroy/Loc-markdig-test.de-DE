---
title: Einrichten eines TEM-Diensts (Telecom Expense Management)
titleSuffix: Azure portal
description: "Konfigurieren Sie den Saaswedo-TEM-Dienst für die Integration in Intune.\""
keywords: Saaswedo
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 10/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: b7bf5802-4b65-4aeb-ac99-8e639dd89c2a
ms.reviewer: sumitp
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: af69568df461d992a02800a7e188bf0ca71e51d5
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2018
---
# <a name="set-up-a-telecom-expense-management-service-in-intune"></a><span data-ttu-id="e73c2-104">Einrichten eines TEM-Diensts (Telecom Expense Management) in Intune</span><span class="sxs-lookup"><span data-stu-id="e73c2-104">Set up a telecom expense management service in Intune</span></span>
[!INCLUDE [azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="e73c2-105">Intune ermöglicht es Ihnen, durch Datenverwendung auf firmeneigenen mobilen Geräten Telekommunikationsausgaben zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="e73c2-105">Intune enables you to manage telecom expenses incurred from data usage on corporate-owned mobile devices.</span></span> <span data-ttu-id="e73c2-106">Die TEM-Lösung Datalert des Drittanbieter-Softwareentwicklers Saaswedo wurde in Intune integriert, um diese Funktion zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="e73c2-106">To enable this capability, Intune has integrated with the third-party software developer Saaswedo’s Datalert telecom expense management solution.</span></span> <span data-ttu-id="e73c2-107">Datalert ist eine TEM-Software, mit der Sie Ihre Telekommunikationsdatennutzung verwalten und kostenintensive und unerwartete Daten- und Roamingzuschläge für mit Intune verwaltete Geräte vermeiden können.</span><span class="sxs-lookup"><span data-stu-id="e73c2-107">Datalert is real-time telecom expense management software that lets you manage telecom data usage and avoid costly and unexpected data and roaming overages for your Intune-managed devices.</span></span>

<span data-ttu-id="e73c2-108">Durch die Intune-Integration mit Datalert können Sie Datennutzungsgrenzwerte im In- und Ausland zentral festlegen, überwachen und erzwingen, sobald definierte Schwellenwerte überschritten werden.</span><span class="sxs-lookup"><span data-stu-id="e73c2-108">Intune's integration with Datalert enables you to centrally set, monitor and enforce roaming and domestic data usage limits by using automated alerts when the limits exceed defined thresholds.</span></span> <span data-ttu-id="e73c2-109">Sie können den Dienst so konfigurieren, dass verschiedene Aktionen für Einzelpersonen oder Gruppen von Endbenutzern ausgeführt werden, darunter das Deaktivieren von Roaming, wenn ein Benutzer den Schwellenwert überschreitet.</span><span class="sxs-lookup"><span data-stu-id="e73c2-109">You can configure the service to apply different actions to individuals or groups of end users, including disabling roaming, when users exceed the threshold.</span></span> <span data-ttu-id="e73c2-110">Berichte für Datennutzungs- und Überwachungsinformationen stehen in der Datalert-Verwaltungskonsole zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="e73c2-110">Reports that provide data usage and monitoring information are available from the Datalert management console.</span></span>

<span data-ttu-id="e73c2-111">Das folgende Diagramm zeigt, wie Intune mit Datalert integriert.</span><span class="sxs-lookup"><span data-stu-id="e73c2-111">The following diagram shows how Intune integrates with Datalert.</span></span>

  ![Diagramm der Integration von Intune und Datalert](./media/tem-datalert-intune-solution-diagram.png)

<span data-ttu-id="e73c2-113">Bevor Sie den Datalert-Dienst mit Intune verwenden können, müssen Sie in der Datalert-Konsole und in Intune Einstellungen konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="e73c2-113">Before you can use the Datalert service with Intune, you need to configure settings in the Datalert console and in Intune.</span></span> <span data-ttu-id="e73c2-114">Die Verbindung muss für den Datalert-Dienst und für Intune aktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="e73c2-114">The connection must be turned on for the Datalert service and for Intune.</span></span> <span data-ttu-id="e73c2-115">Wenn die Datalert-Seite der Verbindung aktiviert ist, aber nicht die Intune-Seite, empfängt Intune die Kommunikation, ignoriert sie jedoch.</span><span class="sxs-lookup"><span data-stu-id="e73c2-115">If the Datalert side of the connection is enabled, but not the Intune side, Intune receives the communication, but ignores it.</span></span>

## <a name="supported-platforms"></a><span data-ttu-id="e73c2-116">Unterstützte Plattformen</span><span class="sxs-lookup"><span data-stu-id="e73c2-116">Supported platforms</span></span>

- <span data-ttu-id="e73c2-117">Samsung KNOX</span><span class="sxs-lookup"><span data-stu-id="e73c2-117">Samsung Knox</span></span>
- <span data-ttu-id="e73c2-118">iOS 8.0 und höher</span><span class="sxs-lookup"><span data-stu-id="e73c2-118">iOS 8.0 and later</span></span>

## <a name="prerequisites"></a><span data-ttu-id="e73c2-119">Voraussetzungen</span><span class="sxs-lookup"><span data-stu-id="e73c2-119">Prerequisites</span></span>

- <span data-ttu-id="e73c2-120">Ein Abonnement für Microsoft Intune und Zugriff auf das Azure-Portal.</span><span class="sxs-lookup"><span data-stu-id="e73c2-120">A subscription to Microsoft Intune, and access to the Azure portal.</span></span>
- <span data-ttu-id="e73c2-121">Ein Abonnement des TEM-Diensts Datalert</span><span class="sxs-lookup"><span data-stu-id="e73c2-121">A subscription to the Datalert telecom expense management service</span></span>

## <a name="list-of-telecom-expense-management-providers"></a><span data-ttu-id="e73c2-122">Liste von TEM-Anbietern</span><span class="sxs-lookup"><span data-stu-id="e73c2-122">List of telecom expense management providers</span></span>

<span data-ttu-id="e73c2-123">In Intune sind derzeit die folgenden TEM-Anbieter integriert:</span><span class="sxs-lookup"><span data-stu-id="e73c2-123">Intune currently integrates with the following telecom expense management providers:</span></span>

[<span data-ttu-id="e73c2-124">TEM-Dienst Saaswedo Datalert</span><span class="sxs-lookup"><span data-stu-id="e73c2-124">Saaswedo Datalert telecom expense management service</span></span>](http://www.datalert.biz/)

## <a name="deploy-the-intune-and-datalert-integrated-solution"></a><span data-ttu-id="e73c2-125">Bereitstellen von integrierten Intune- und Datalertlösungen</span><span class="sxs-lookup"><span data-stu-id="e73c2-125">Deploy the Intune and Datalert integrated solution</span></span>

<span data-ttu-id="e73c2-126">Bevor Sie beginnen, stellen Sie sicher, dass Sie bereits ein TEM-Dienst-Abonnement für Intune und Datalert haben.</span><span class="sxs-lookup"><span data-stu-id="e73c2-126">Before you start, make sure that you already have an Intune and a Datalert telecom expense management service subscription.</span></span>

### <a name="step-1-connect-the-datalert-service-to-microsoft-intune"></a><span data-ttu-id="e73c2-127">Schritt 1: Verbinden des Datalert-Diensts mit Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="e73c2-127">Step 1: Connect the Datalert service to Microsoft Intune</span></span>

1. <span data-ttu-id="e73c2-128">Melden Sie sich in der Datalert-Verwaltungskonsole mit Ihren Administratoranmeldeinformationen an.</span><span class="sxs-lookup"><span data-stu-id="e73c2-128">Sign into the Datalert management console with your administrator credentials.</span></span>

2. <span data-ttu-id="e73c2-129">Gehen Sie in der Datalert-Verwaltungskonsole zur Registerkarte **Einstellungen** und anschließend zu **MDM-Konfiguration**.</span><span class="sxs-lookup"><span data-stu-id="e73c2-129">On the Datalert management console, go to the **Settings** tab, and then to **MDM configuration**.</span></span>

3. <span data-ttu-id="e73c2-130">Wählen Sie **Unblock** (Blockierung aufheben) aus, damit Sie die Einstellungen auf der Seite eingeben können.</span><span class="sxs-lookup"><span data-stu-id="e73c2-130">Select **Unblock** to enable you to enter the settings on the page.</span></span>

4. <span data-ttu-id="e73c2-131">Wählen Sie für **Server-MDM** die Option **Microsoft Intune** aus.</span><span class="sxs-lookup"><span data-stu-id="e73c2-131">For **Server MDM**, choose **Microsoft Intune**.</span></span>

5. <span data-ttu-id="e73c2-132">Geben Sie für die **Azure AD-Domäne** Ihre Azure-Mandanten-ID ein, und wählen Sie dann die Schaltfläche **Verbindung**.</span><span class="sxs-lookup"><span data-stu-id="e73c2-132">For **Azure AD domain**, enter your Azure tenant ID, and then select the **Connection** button.</span></span>

    <span data-ttu-id="e73c2-133">Durch das Auswählen von **Verbindung** überprüft Datalert Intune, um sicherzustellen, dass nicht bereits Verbindungen zwischen Datalert und Intune bestehen.</span><span class="sxs-lookup"><span data-stu-id="e73c2-133">Selecting **Connection** makes the Datalert service check in with Intune to ensure that there are no pre-existing Datalert connections with Intune.</span></span> <span data-ttu-id="e73c2-134">Nach wenigen Sekunden wird eine Microsoft-Anmeldeseite angezeigt, gefolgt von der Datalert-Azure-Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="e73c2-134">After a few seconds, a Microsoft log-in page appears, followed by the Datalert Azure authentication.</span></span>

6. <span data-ttu-id="e73c2-135">Wählen Sie auf Microsoft-Authentifizierungsseite **Annehmen** aus.</span><span class="sxs-lookup"><span data-stu-id="e73c2-135">On the Microsoft authentication page, select **Accept**.</span></span> <span data-ttu-id="e73c2-136">Sie werden zu einer Seite von Datalert mit dem Inhalt „Danke“ umgeleitet, die nach einigen Sekunden geschlossen wird.</span><span class="sxs-lookup"><span data-stu-id="e73c2-136">You are redirected to a Datalert “thank you” page, which closes after a few seconds.</span></span> <span data-ttu-id="e73c2-137">Datalert überprüft die Verbindung und zeigt grüne Häkchen neben einer Liste von bereits überprüften Elementen an.</span><span class="sxs-lookup"><span data-stu-id="e73c2-137">Datalert validates the connection, and displays green check marks beside a list of items that it validated.</span></span> <span data-ttu-id="e73c2-138">Wenn bei der Validierung ein Fehler auftritt, wird eine Meldung in Rot angezeigt.</span><span class="sxs-lookup"><span data-stu-id="e73c2-138">If the validation fails, you see a message in red.</span></span> <span data-ttu-id="e73c2-139">In diesem Fall erhalten Sie beim Datalert-Support Hilfe.</span><span class="sxs-lookup"><span data-stu-id="e73c2-139">If this happens, contact Datalert Support for help.</span></span>

    <span data-ttu-id="e73c2-140">Der folgende Screenshot zeigt die grünen Häkchen, die angezeigt werden, sobald die Verbindung erfolgreich aufgebaut wurde.</span><span class="sxs-lookup"><span data-stu-id="e73c2-140">The following screenshot shows the green check marks that you can expect to see once the connection is successful.</span></span>

   ![Die Datalert-Seite, die eine erfolgreiche Verbindung anzeigt](./media/tem-mdm-configuration-mdm-server-page.png)

### <a name="step-2-check-that-the-telecom-expense-management-feature-is-active-in-intune"></a><span data-ttu-id="e73c2-142">Schritt 2: Überprüfen, ob die TEM-Funktion in Intune aktiv ist</span><span class="sxs-lookup"><span data-stu-id="e73c2-142">Step 2: Check that the telecom expense management feature is Active in Intune</span></span>

<span data-ttu-id="e73c2-143">Nach Abschluss von Schritt 1 sollte die Verbindung automatisch aktiviert werden und der Verbindungsstatus **Aktiv** im Azure-Portal angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="e73c2-143">After you complete Step 1 above, your connection should be automatically enabled, and a connection status of **Active** should be showing in the Azure portal.</span></span> <span data-ttu-id="e73c2-144">Diese Schritte zeigen Ihnen, wie Sie auf den Status **Aktiv** prüfen.</span><span class="sxs-lookup"><span data-stu-id="e73c2-144">These steps show you how to check for the **Active** status.</span></span>

1. <span data-ttu-id="e73c2-145">Melden Sie sich im Azure-Portal an.</span><span class="sxs-lookup"><span data-stu-id="e73c2-145">Sign in to the Azure portal.</span></span>

2. <span data-ttu-id="e73c2-146">Wählen Sie **Weitere Dienste** > **Überwachung und Verwaltung** > **Intune** aus.</span><span class="sxs-lookup"><span data-stu-id="e73c2-146">Choose **More Services** > **Monitoring + Management** > **Intune**.</span></span>

3. <span data-ttu-id="e73c2-147">Wählen Sie auf dem Blatt **Intune** die Option **Gerätekonfiguration** aus.</span><span class="sxs-lookup"><span data-stu-id="e73c2-147">On the **Intune** blade, choose **Device configuration**.</span></span>

4. <span data-ttu-id="e73c2-148">Wählen Sie auf dem Blatt **Gerätekonfiguration** die Option **Setup** > **Telecom Expense Management** aus.</span><span class="sxs-lookup"><span data-stu-id="e73c2-148">On the **Device Configuration** blade, choose **Setup** > **Telecom Expense Management**.</span></span>

   <span data-ttu-id="e73c2-149">Suchen Sie nach dem **Aktiv**-Verbindungsstatus oben auf der Seite.</span><span class="sxs-lookup"><span data-stu-id="e73c2-149">Look for the **Active** connection status at the top of the page.</span></span>

   ![Azure-Portal mit aktivem Datalert-Verbindungsstatus](./media/tem-azure-portal-enable-service.png)

### <a name="step-3-deploy-the-datalert-app-to-corporate-enrolled-devices"></a><span data-ttu-id="e73c2-151">Schritt 3: Bereitstellen der Datalert-App für in Unternehmen registrierte Geräte</span><span class="sxs-lookup"><span data-stu-id="e73c2-151">Step 3: Deploy the Datalert app to corporate enrolled devices</span></span>

<span data-ttu-id="e73c2-152">Um sicherzustellen, dass die Datennutzung nur von firmeneigenen Leitungen gesammelt wurde, müssen Sie Gerätekategorien in Intune erstellen und dann die Datalert-App nur für Firmentelefone zum Ziel stellen.</span><span class="sxs-lookup"><span data-stu-id="e73c2-152">To ensure that data usage from only corporate-owned lines is collected, you need to create device categories in Intune, and then target the Datalert app to only corporate phones.</span></span> <span data-ttu-id="e73c2-153">Führen Sie die Schritte in folgenden Unterabschnitten durch.</span><span class="sxs-lookup"><span data-stu-id="e73c2-153">Complete the steps in the following subsections.</span></span>

#### <a name="define-device-categories-and-device-groups-mapped-to-the-categories"></a><span data-ttu-id="e73c2-154">Definieren Sie Gerätekategorien und Gerätegruppen, die den Kategorien zugeordnet sind</span><span class="sxs-lookup"><span data-stu-id="e73c2-154">Define device categories and device groups mapped to the categories</span></span>

<span data-ttu-id="e73c2-155">Abhängig von Ihren organisatorischen Bedürfnissen müssen Sie mindestens zwei Gerätekategorien (z.B. Unternehmen und Privat) und dynamische Gerätegruppen für jede Kategorie erstellen.</span><span class="sxs-lookup"><span data-stu-id="e73c2-155">Depending on your organizational needs, you'll need to create at least two device categories (for example, Corporate and Personal) and create dynamic device groups for each category.</span></span> <span data-ttu-id="e73c2-156">Sie können je nach Bedarf weitere Kategorien für Ihre Organisation erstellen.</span><span class="sxs-lookup"><span data-stu-id="e73c2-156">You can create more categories for your organization, as needed.</span></span>

<span data-ttu-id="e73c2-157">Diese Kategorien werden Benutzern während der Registrierung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="e73c2-157">These categories will be shown to users during enrollment.</span></span> <span data-ttu-id="e73c2-158">Je nachdem, welche Kategorie Benutzer auswählen, wird das registrierte Gerät in die entsprechende Gerätegruppe verschoben.</span><span class="sxs-lookup"><span data-stu-id="e73c2-158">Depending on which category users choose, the enrolled device will be moved to the corresponding device group.</span></span> <span data-ttu-id="e73c2-159">Schritte zum Erstellen von Gerätekategorien finden Sie unter [Zuweisen von Geräten zu Gruppen](device-group-mapping.md).</span><span class="sxs-lookup"><span data-stu-id="e73c2-159">For steps on how to create device categories, see [Map devices to groups](device-group-mapping.md).</span></span>

  ![Screenshot des Blatts „Richtlinie hinzufügen“](./media/tem-dynamic-membership-rules.png)

#### <a name="create-the-datalert-app-in-intune"></a><span data-ttu-id="e73c2-161">Erstellen einer Datalert-App in Intune</span><span class="sxs-lookup"><span data-stu-id="e73c2-161">Create the Datalert app in Intune</span></span>

<span data-ttu-id="e73c2-162">Um die Datalert-App in Intune für jede Plattform zu erstellen, gehen Sie wie folgt vor.</span><span class="sxs-lookup"><span data-stu-id="e73c2-162">Follow these steps to create the Datalert app in Intune for each platform.</span></span> <span data-ttu-id="e73c2-163">iOS wird in den folgenden Schritten als Beispiel verwendet.</span><span class="sxs-lookup"><span data-stu-id="e73c2-163">iOS is used as an example in these steps.</span></span>

1. <span data-ttu-id="e73c2-164">Wählen Sie im Azure-Portal auf dem Blatt **Intune** die Option **Mobile Apps** aus.</span><span class="sxs-lookup"><span data-stu-id="e73c2-164">On the **Intune** blade of the Azure portal, choose **Mobile apps**.</span></span>

2. <span data-ttu-id="e73c2-165">Wählen Sie auf dem Blatt **Mobile Apps** die Option **Verwalten** > **Apps** aus.</span><span class="sxs-lookup"><span data-stu-id="e73c2-165">On the **Mobile apps** blade, choose **Manage** > **Apps**.</span></span>

3. <span data-ttu-id="e73c2-166">Wählen Sie **Hinzufügen** aus, um eine App hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="e73c2-166">Select **Add** to add an app.</span></span>

4. <span data-ttu-id="e73c2-167">Wählen Sie den Anwendungstyp aus.</span><span class="sxs-lookup"><span data-stu-id="e73c2-167">Select the app type.</span></span> <span data-ttu-id="e73c2-168">Für iOS würden Sie zum Beispiel **iOS Store-App** auswählen.</span><span class="sxs-lookup"><span data-stu-id="e73c2-168">For example, for iOS, you would select **iOS Store App**.</span></span>

5. <span data-ttu-id="e73c2-169">In **App Store durchsuchen**, suchen Sie nach der Datalert-App durch Eingabe von **Datalert** im Suchfenster.</span><span class="sxs-lookup"><span data-stu-id="e73c2-169">In **Search the App Store**, look for the Datalert app by typing **Datalert** in the search window.</span></span>

6. <span data-ttu-id="e73c2-170">Wählen Sie die **Datalert**-App aus, und wählen Sie **OK**.</span><span class="sxs-lookup"><span data-stu-id="e73c2-170">Select the **Datalert** app, and select **OK**.</span></span>

   ![Screenshot des Blatts „Richtlinie hinzufügen“](./media/tem-select-app-from-apple-app-store.png)

7. <span data-ttu-id="e73c2-172">Schließen Sie die verbleibenden Schritte zum Erstellen einer App für iOS ab.</span><span class="sxs-lookup"><span data-stu-id="e73c2-172">Complete the remaining steps to create an app for iOS.</span></span>

   ![Screenshot des Blatts „Richtlinie hinzufügen“](./media/tem-steps-to-create-the-app.png)

#### <a name="assign-the-datalert-app-to-the-corporate-device-group"></a><span data-ttu-id="e73c2-174">Zuweisen der Datalert-App zur Unternehmensgerätegruppe</span><span class="sxs-lookup"><span data-stu-id="e73c2-174">Assign the Datalert app to the corporate device group</span></span>

1. <span data-ttu-id="e73c2-175">Wählen Sie die Datalert-App für iOS aus, die Sie im vorherigen Schritt erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="e73c2-175">Select the iOS Datalert app that you created in the previous step.</span></span>

2. <span data-ttu-id="e73c2-176">Navigieren Sie auf dem Blatt **Apps** zu **Verwalten** > **Zuweisungen**.</span><span class="sxs-lookup"><span data-stu-id="e73c2-176">On the **Apps** blade, go to **Manage** > **Assignments**.</span></span>

3. <span data-ttu-id="e73c2-177">Wählen Sie **Gruppen auswählen** aus, und befolgen Sie die Schritte zum Auswählen der Unternehmensgerätegruppe.</span><span class="sxs-lookup"><span data-stu-id="e73c2-177">Choose **Select groups**, and follow the steps to select the corporate device group.</span></span>

4. <span data-ttu-id="e73c2-178">Legen Sie fest, ob die Installation der App für die Gruppe erforderlich oder optional ist.</span><span class="sxs-lookup"><span data-stu-id="e73c2-178">Choose whether to make the app installation required or optional for the group.</span></span> <span data-ttu-id="e73c2-179">Auf dem folgenden Beispiel-Screenshot wird die Installation als erforderlich angezeigt, was bedeutet, dass Benutzer die Datalert-App nach der Registrierung ihres Geräts installieren müssen.</span><span class="sxs-lookup"><span data-stu-id="e73c2-179">The following example screenshot shows the installation as required, which means that users must install the Datalert app installation after enrolling their device.</span></span>

   ![Screenshot des Blatts „Richtlinie hinzufügen“](./media/tem-assign-datalert-app-to-device-group.png)

### <a name="step-4-add-corporate-paid-phone-lines-to-the-datalert-console"></a><span data-ttu-id="e73c2-181">Schritt 4: Hinzufügen von kostenpflichtigen Firmentelefonleitungen zur Datalert-Konsole</span><span class="sxs-lookup"><span data-stu-id="e73c2-181">Step 4: Add corporate paid phone lines to the Datalert console</span></span>

<span data-ttu-id="e73c2-182">Sie haben nun die Intune- und Datalert-Dienste so konfiguriert, dass sie miteinander kommunizieren können.</span><span class="sxs-lookup"><span data-stu-id="e73c2-182">You now have configured the Intune and Datalert services to communicate with each other.</span></span> <span data-ttu-id="e73c2-183">Sie müssen jetzt die kostenpflichtigen Firmentelefonleitungen zur Datalert-Konsole hinzufügen und Schwellenwerte und Aktionen für alle Funk- oder Roaming-Verwendungsverstöße definieren.</span><span class="sxs-lookup"><span data-stu-id="e73c2-183">You now need to add your corporate paid phone lines to the Datalert console and define thresholds and actions for any cellular or roaming usage violations.</span></span> <span data-ttu-id="e73c2-184">Sie können vom Unternehmen bezahlte Telefonleitungen der Datalert-Konsole entweder manuell hinzufügen oder die Zeilen nach der Registrierung des Geräts in Intune automatisch hinzufügen lassen.</span><span class="sxs-lookup"><span data-stu-id="e73c2-184">You can either add corporate paid phone lines to the Datalert console manually or have the lines added automatically after the device is enrolled into Intune.</span></span>

<span data-ttu-id="e73c2-185">Um diese Elemente festzulegen, gehen Sie zur [Seite „Datalert setup for Microsoft Intune“ (Datalertsetup für Microsoft Intune)](http://www.datalert.fr/microsoft-intune/intune-setup) (http://www.datalert.fr/microsoft-intune/intune-setup), und führen Sie die Schritte im Setup-Assistenten unter der Registerkarte **Einstellungen** aus.</span><span class="sxs-lookup"><span data-stu-id="e73c2-185">To set these items, go to the [Datalert setup for Microsoft Intune page](http://www.datalert.fr/microsoft-intune/intune-setup) (http://www.datalert.fr/microsoft-intune/intune-setup), and follow the steps in the setup wizard under the **Settings** tab.</span></span>

  ![Screenshot des Blatts „Richtlinie hinzufügen“](./media/tem-add-phone-lines-to-datalert-console.png)


<span data-ttu-id="e73c2-187">Der Datalert-Dienst ist jetzt aktiv, und es wird damit begonnen, die Datennutzung zu überwachen und auf Geräten, die die Verwendung der konfigurierten Grenzwerte überschreiten, Mobilfunk- und Roamingdaten zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="e73c2-187">The Datalert service is now active, and it starts monitoring data usage and disabling cellular and roaming data on devices that exceed the configured usage limits.</span></span>

## <a name="client-enrollment-experience"></a><span data-ttu-id="e73c2-188">Clientregistrierung</span><span class="sxs-lookup"><span data-stu-id="e73c2-188">Client enrollment experience</span></span>
<span data-ttu-id="e73c2-189">Beachten Sie bei der Clientregistrierung folgende Themen:</span><span class="sxs-lookup"><span data-stu-id="e73c2-189">For client enrollment experience see following:</span></span>
-   [<span data-ttu-id="e73c2-190">Registrieren Ihres iOS-Geräts im Telecom Expense Management</span><span class="sxs-lookup"><span data-stu-id="e73c2-190">Enroll your iOS device in telecom expense management</span></span>](https://docs.microsoft.com/intune-user-help/enroll-your-device-with-telecom-expense-management-ios)
-   [<span data-ttu-id="e73c2-191">Registrieren Ihres Android-Gerät im Telecom Expense Management</span><span class="sxs-lookup"><span data-stu-id="e73c2-191">Enroll your Android device in telecom expense management</span></span>](https://docs.microsoft.com/intune-user-help/enroll-your-device-with-telecom-expense-management-android)

## <a name="turning-off-the-datalert-service"></a><span data-ttu-id="e73c2-192">Deaktivieren des Datalert-Diensts</span><span class="sxs-lookup"><span data-stu-id="e73c2-192">Turning off the Datalert service</span></span>

<span data-ttu-id="e73c2-193">Wenn Sie den Datalert-Dienst im Azure-Portal zu deaktivieren, geschieht Folgendes:</span><span class="sxs-lookup"><span data-stu-id="e73c2-193">If you disable the Datalert service in the Azure portal:</span></span>

- <span data-ttu-id="e73c2-194">Alle Aktionen, die aufgrund vergangener Verstöße gegen die Nutzungsgrenzwerte auf Geräte angewendet wurden, werden rückgängig gemacht.</span><span class="sxs-lookup"><span data-stu-id="e73c2-194">All of the actions that have been applied to devices, due to past violations of the usage limits, are undone.</span></span>
- <span data-ttu-id="e73c2-195">Datenzugriffe und Roaming werden für Benutzer nicht mehr blockiert.</span><span class="sxs-lookup"><span data-stu-id="e73c2-195">Users are no longer blocked from data access and roaming.</span></span>
- <span data-ttu-id="e73c2-196">Intune weiterhin empfängt die Signale vom Dienst, ignoriert diese jedoch.</span><span class="sxs-lookup"><span data-stu-id="e73c2-196">Intune still receives the signals coming from the service, but ignores them.</span></span>

<span data-ttu-id="e73c2-197">**So deaktivieren Sie den Dienst**</span><span class="sxs-lookup"><span data-stu-id="e73c2-197">**To turn off the service**</span></span>

1. <span data-ttu-id="e73c2-198">Wählen Sie auf dem Blatt **Telecom Expense Management** im Azure-Portal die Option **Deaktivieren** aus.</span><span class="sxs-lookup"><span data-stu-id="e73c2-198">On the **Telecom Expense Management** blade in the Azure portal, select **Disable**.</span></span>

2. <span data-ttu-id="e73c2-199">Wählen Sie **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="e73c2-199">Select **Save**.</span></span>

## <a name="viewing-data-usage-and-roaming-reports"></a><span data-ttu-id="e73c2-200">Anzeigen der Datennutzungs- und Roamingberichte</span><span class="sxs-lookup"><span data-stu-id="e73c2-200">Viewing data usage and roaming reports</span></span>

<span data-ttu-id="e73c2-201">Zum aktuellen Zeitpunkt sind Nutzungsberichte nur in der Datalert-Verwaltungskonsole von Saaswedo verfügbar.</span><span class="sxs-lookup"><span data-stu-id="e73c2-201">At this time, data usage reporting is available only in Saaswedo’s Datalert management console.</span></span>

<span data-ttu-id="e73c2-202">Die Anweisungen, denen Ihre Endbenutzer befolgen, um die Datalert-App zu installieren, werden bald verfügbar sein.</span><span class="sxs-lookup"><span data-stu-id="e73c2-202">The instructions that your end users follow to install the Datalert app will be added soon.</span></span>
