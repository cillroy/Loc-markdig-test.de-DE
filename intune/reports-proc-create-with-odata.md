---
title: Erstellen eines Berichts aus dem OData-Feed mit Power BI | Microsoft-Dokumentation
description: Erstellen Sie eine Treemap-Visualisierung mithilfe von Power BI Desktop mit einem interaktiven Filter der Intune Data Warehouse-API.
keywords: Intune Data Warehouse
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 10/18/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: A2C8A336-29D3-47DF-BB4A-62748339391D
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 1e0ffcaa2ff8bd9e622c1d27f27564bd78df0276
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2017
---
# <a name="create-a-report-from-the-odata-feed-with-power-bi"></a><span data-ttu-id="bc38a-104">Erstellen eines Berichts aus dem OData-Feed mit Power BI</span><span class="sxs-lookup"><span data-stu-id="bc38a-104">Create a report from the OData feed with Power BI</span></span>

<span data-ttu-id="bc38a-105">In diesem Tutorial wird erläutert, wie Sie eine Treemap-Visualisierung mithilfe von Power BI Desktop mit einem interaktiven Filter erstellen können.</span><span class="sxs-lookup"><span data-stu-id="bc38a-105">In this tutorial, you're going to create a treemap visualization using Power BI Desktop with an interactive filter.</span></span> <span data-ttu-id="bc38a-106">Beispielsweise möchte Ihr Finanzdirektor möglicherweise wissen, in welchem Zusammenhang die Verteilung aller Geräte mit den Geräten, die nur im Besitz von Unternehmen sind, bzw. mit persönlichen Geräten steht.</span><span class="sxs-lookup"><span data-stu-id="bc38a-106">For example, your CFO might like to how the overall distribution of devices compares to just company owned to personal devices.</span></span> <span data-ttu-id="bc38a-107">Die Treemap gibt einen Überblick über die Gesamtanzahl von Gerätetypen.</span><span class="sxs-lookup"><span data-stu-id="bc38a-107">The treemap provides insight into the total number of device types.</span></span> <span data-ttu-id="bc38a-108">Sie können die Anzahl von iOS-, Android- und Windows-Geräten prüfen, die weder einem Unternehmen noch einer Privatperson gehören.</span><span class="sxs-lookup"><span data-stu-id="bc38a-108">You can review the number of iOS, Android, and Windows devices that are either company owned or personally owned.</span></span>

### <a name="overview-of-creating-the-chart"></a><span data-ttu-id="bc38a-109">Übersicht zum Erstellen des Diagramms</span><span class="sxs-lookup"><span data-stu-id="bc38a-109">Overview of creating the chart</span></span>

<span data-ttu-id="bc38a-110">Gehen Sie wie folgt vor, um dieses Diagramm zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="bc38a-110">To create this chart, you will:</span></span>
1. <span data-ttu-id="bc38a-111">Falls noch nicht geschehen, installieren Sie Power BI Desktop.</span><span class="sxs-lookup"><span data-stu-id="bc38a-111">Install Power BI Desktop if you don't already have it.</span></span>
2. <span data-ttu-id="bc38a-112">Stellen Sie eine Verbindung mit dem Intune Data Warehouse-Datenmodell her, und rufen Sie aktuelle Daten für das Modell ab.</span><span class="sxs-lookup"><span data-stu-id="bc38a-112">Connect to the Intune Data Warehouse data model and retrieve current data for the model.</span></span>
3. <span data-ttu-id="bc38a-113">Erstellen oder verwalten Sie die Beziehungen des Datenmodells.</span><span class="sxs-lookup"><span data-stu-id="bc38a-113">Create or manage the data model relationships.</span></span>
4. <span data-ttu-id="bc38a-114">Erstellen Sie das Diagramm mit Daten aus der **Gerätetabelle**.</span><span class="sxs-lookup"><span data-stu-id="bc38a-114">Create the chart with data from the **devices** table.</span></span>
5. <span data-ttu-id="bc38a-115">Erstellen Sie einen interaktiven Filter.</span><span class="sxs-lookup"><span data-stu-id="bc38a-115">Create an interactive filter.</span></span>
6. <span data-ttu-id="bc38a-116">Lassen Sie sich das fertige Diagramm anzeigen.</span><span class="sxs-lookup"><span data-stu-id="bc38a-116">View the finished chart.</span></span>

### <a name="a-note-about-tables-and-entities"></a><span data-ttu-id="bc38a-117">Hinweis zu Tabellen und Entitäten</span><span class="sxs-lookup"><span data-stu-id="bc38a-117">A note about tables and entities</span></span>

<span data-ttu-id="bc38a-118">In Power BI arbeiten Sie mit Tabellen.</span><span class="sxs-lookup"><span data-stu-id="bc38a-118">You work with tables in Power BI.</span></span> <span data-ttu-id="bc38a-119">Eine Tabelle enthält Datenfelder.</span><span class="sxs-lookup"><span data-stu-id="bc38a-119">A table contains data fields.</span></span> <span data-ttu-id="bc38a-120">Jedes Datenfeld ist einem Datentypen zugeordnet.</span><span class="sxs-lookup"><span data-stu-id="bc38a-120">Each data field has a data type.</span></span> <span data-ttu-id="bc38a-121">Das Feld kann nur Daten dieses Datentyps enthalten.</span><span class="sxs-lookup"><span data-stu-id="bc38a-121">The field can only contain data of the data type.</span></span> <span data-ttu-id="bc38a-122">Datentypen sind u.a. Nummern, Text oder Datumsangaben.</span><span class="sxs-lookup"><span data-stu-id="bc38a-122">Data types are numbers, text, dates, and so on.</span></span> <span data-ttu-id="bc38a-123">Die Tabellen in Power BI füllen sich mit kürzlich erfassten Daten aus Ihrem Mandanten, wenn Sie das Modell laden.</span><span class="sxs-lookup"><span data-stu-id="bc38a-123">The tables in Power BI fill with recent historical data from your tenant when you load the model.</span></span> <span data-ttu-id="bc38a-124">Obwohl sich die spezifischen Daten mit der Zeit ändern, bleibt die Tabellenstruktur solange unverändert, bis das zugrunde liegende Datenmodell aktualisiert worden ist.</span><span class="sxs-lookup"><span data-stu-id="bc38a-124">Although the specific data changes with time, the table structure won't change unless the underlying data model is updated.</span></span>

<span data-ttu-id="bc38a-125">Die Verwendung der Begriffe _Entität_ und _Tabelle_ erscheint Ihnen möglicherweise nicht ganz eindeutig.</span><span class="sxs-lookup"><span data-stu-id="bc38a-125">You may be confused by the use of the term _entity_ and _table_.</span></span> <span data-ttu-id="bc38a-126">Sie können über einen OData-Feed auf das Datenmodell zugreifen.</span><span class="sxs-lookup"><span data-stu-id="bc38a-126">The data model is accessible through an OData feed.</span></span> <span data-ttu-id="bc38a-127">Im Zusammenhang mit OData gelten die Container, die in Power BI als Tabellen bezeichnet werden, als Entitäten.</span><span class="sxs-lookup"><span data-stu-id="bc38a-127">In the universe of the OData, the containers that are called tables in Power BI are called entities.</span></span> <span data-ttu-id="bc38a-128">Beide Begriffe beziehen sich auf dasselbe Konzept zum Speichern Ihrer Daten.</span><span class="sxs-lookup"><span data-stu-id="bc38a-128">These terms both refer to the same thing that holds your data.</span></span>

## <a name="install-power-bi-desktop"></a><span data-ttu-id="bc38a-129">Installieren von Power BI Desktop</span><span class="sxs-lookup"><span data-stu-id="bc38a-129">Install Power BI Desktop</span></span>

<span data-ttu-id="bc38a-130">Installieren Sie die neueste Version von Power BI Desktop.</span><span class="sxs-lookup"><span data-stu-id="bc38a-130">Install the latest version of Power BI Desktop.</span></span> <span data-ttu-id="bc38a-131">Sie können Power BI Desktop aus [PowerBI.microsoft.com](https://powerbi.microsoft.com/desktop) herunterladen.</span><span class="sxs-lookup"><span data-stu-id="bc38a-131">You can download Power BI Desktop from: [PowerBI.microsoft.com](https://powerbi.microsoft.com/desktop)</span></span>

## <a name="connect-to-the-odata-feed-for-the-intune-data-warehouse-for-your-tenant"></a><span data-ttu-id="bc38a-132">Stellen Sie eine Verbindung zum OData-Feed für das Intune Data Warehouse für Ihren Mandanten her.</span><span class="sxs-lookup"><span data-stu-id="bc38a-132">Connect to the OData feed for the Intune Data Warehouse for your tenant</span></span>

> [!Note]  
> <span data-ttu-id="bc38a-133">Sie benötigen in Intune eine Berechtigung, um auf **Berichte** zugreifen zu können.</span><span class="sxs-lookup"><span data-stu-id="bc38a-133">You need permission to **Reports** in Intune.</span></span> <span data-ttu-id="bc38a-134">Weitere Informationen finden Sie unter [Autorisierung](reports-api-url.md).</span><span class="sxs-lookup"><span data-stu-id="bc38a-134">For more information, see [Authorization](reports-api-url.md).</span></span>

1. <span data-ttu-id="bc38a-135">Melden Sie sich im Azure-Portal an.</span><span class="sxs-lookup"><span data-stu-id="bc38a-135">Sign in to the Azure portal.</span></span>
2. <span data-ttu-id="bc38a-136">Wählen Sie **Weitere Dienste** > **Überwachung und Verwaltung** + **Intune** aus.</span><span class="sxs-lookup"><span data-stu-id="bc38a-136">Choose **More Services** > **Monitoring + Management** + **Intune**.</span></span>
3. <span data-ttu-id="bc38a-137">Öffnen Sie das Blatt **Intune Data Warehouse**.</span><span class="sxs-lookup"><span data-stu-id="bc38a-137">Open the **Intune Data Warehouse** blade.</span></span>
4. <span data-ttu-id="bc38a-138">Kopieren Sie die benutzerdefinierte Feed-URL.</span><span class="sxs-lookup"><span data-stu-id="bc38a-138">Copy the custom feed URL.</span></span> <span data-ttu-id="bc38a-139">Beispiel: `https://fef.tenant.manage.microsoft.com/ReportingService/DataWarehouseFEService?api-version=beta`</span><span class="sxs-lookup"><span data-stu-id="bc38a-139">For example: `https://fef.tenant.manage.microsoft.com/ReportingService/DataWarehouseFEService?api-version=beta`</span></span>
5. <span data-ttu-id="bc38a-140">Öffnen Sie Power BI Desktop.</span><span class="sxs-lookup"><span data-stu-id="bc38a-140">Open Power BI Desktop.</span></span>
6. <span data-ttu-id="bc38a-141">Klicken Sie auf **Daten abrufen** > **OData-Feed**.</span><span class="sxs-lookup"><span data-stu-id="bc38a-141">Choose **Get Data** > **Odata feed**.</span></span>
7. <span data-ttu-id="bc38a-142">Fügen Sie die benutzerdefinierte Feed-URL in das URL-Feld im Fenster **OData-Feed** ein.</span><span class="sxs-lookup"><span data-stu-id="bc38a-142">Paste the custom feed URL into the URL box in the **OData feed** window.</span></span>
8. <span data-ttu-id="bc38a-143">Wählen Sie **Basic** aus.</span><span class="sxs-lookup"><span data-stu-id="bc38a-143">Select **Basic**.</span></span>

    ![OData-Feed](media/reports-create-01-odatafeed.png)

9. <span data-ttu-id="bc38a-145">Wählen Sie **OK** aus.</span><span class="sxs-lookup"><span data-stu-id="bc38a-145">Select **OK**.</span></span>
10. <span data-ttu-id="bc38a-146">Wählen Sie **Organisationskonto** aus, und melden Sie sich anschließend mit Ihren Anmeldeinformationen für Intune an.</span><span class="sxs-lookup"><span data-stu-id="bc38a-146">Select **Organization account**, and then sign in with your Intune credentials.</span></span> 

    ![Anmeldeinformationen für das Organisationskonto](media/reports-create-02-org-account.png)

11. <span data-ttu-id="bc38a-148">Wählen Sie **Verbinden** aus.</span><span class="sxs-lookup"><span data-stu-id="bc38a-148">Select **Connect**.</span></span> <span data-ttu-id="bc38a-149">Der Navigator öffnet sich und zeigt Ihnen eine Liste mit Tabelle im Intune Data Warehouse an.</span><span class="sxs-lookup"><span data-stu-id="bc38a-149">The Navigator will open and show you the list of tables in the Intune Data Warehouse.</span></span> 

    ![Der Navigator](media/reports-create-02-loadentities.png)

12. <span data-ttu-id="bc38a-151">Wählen Sie die **Geräte** und die **OwnerTypes**-Tabellen aus.</span><span class="sxs-lookup"><span data-stu-id="bc38a-151">Select the **devices** and the **ownerTypes** tables.</span></span>  <span data-ttu-id="bc38a-152">Wählen Sie **Laden** aus.</span><span class="sxs-lookup"><span data-stu-id="bc38a-152">Select **Load**.</span></span> <span data-ttu-id="bc38a-153">Power BI lädt die Daten in das Modell.</span><span class="sxs-lookup"><span data-stu-id="bc38a-153">Power BI loads data to the model.</span></span>

## <a name="create-a-relationship"></a><span data-ttu-id="bc38a-154">Erstellen einer Beziehung</span><span class="sxs-lookup"><span data-stu-id="bc38a-154">Create a relationship</span></span> 

<span data-ttu-id="bc38a-155">Sie können mehrerer Tabellen importieren, um nicht nur die Daten in einer einzigen Tabelle zu analysieren, sondern auch tabellenübergreifende Daten.</span><span class="sxs-lookup"><span data-stu-id="bc38a-155">You can import multiple tables to analyze not just the data in a single table but related data across tables.</span></span>  <span data-ttu-id="bc38a-156">In Power BI gibt es eine Funktion, die **Autodetect** genannt wird und Beziehungen findet sowie erstellt.</span><span class="sxs-lookup"><span data-stu-id="bc38a-156">PowerBI has a feature called **autodetect** that attempts to find and create relationships for you.</span></span> <span data-ttu-id="bc38a-157">Die Tabellen im Data Warehouse wurden so konzipiert, dass sie mit der Autodetect-Funktion von Power BI kompatibel sind.</span><span class="sxs-lookup"><span data-stu-id="bc38a-157">The tables in the Data Warehouse have been built to work with PowerBI's autodetect feature.</span></span> <span data-ttu-id="bc38a-158">Auch wenn Power BI die Beziehungen nicht automatisch finden sollte, verwalten Sie sie trotzdem.</span><span class="sxs-lookup"><span data-stu-id="bc38a-158">However, even if PowerBI doesn't automatically find the relationships you still manage the relationships.</span></span>

![Verwalten von Beziehungen](media/reports-create-03-managerelationships.png)

1. <span data-ttu-id="bc38a-160">Wählen Sie **Beziehungen verwalten** aus.</span><span class="sxs-lookup"><span data-stu-id="bc38a-160">Select **Manage Relationships**.</span></span>
2. <span data-ttu-id="bc38a-161">Wählen Sie **Autodetect...** aus, wenn Power BI die Beziehungen noch nicht erkannt hat.</span><span class="sxs-lookup"><span data-stu-id="bc38a-161">Select **Autodetect...** if PowerBI has not already detected the relationships.</span></span>  
<span data-ttu-id="bc38a-162">Die Beziehung wird von einer „From“-Spalte zu einer „To“-Spalte angezeigt.</span><span class="sxs-lookup"><span data-stu-id="bc38a-162">The relationship is displayed in a From column to a To column.</span></span> <span data-ttu-id="bc38a-163">In diesem Beispiel ist das Datenfeld **ownerTypeKey** in der **Gerätetabelle** mit dem Datenfeld **ownerTypeKey** in der Tabelle **ownerTypes** verknüpft.</span><span class="sxs-lookup"><span data-stu-id="bc38a-163">In this example, the data field **ownerTypeKey** in the **devices** table links to the data field **ownerTypeKey** in the **ownerTypes** table.</span></span> <span data-ttu-id="bc38a-164">Sie können die Beziehung verwenden, um den einfachen Namen eines Gerätetypcodes in der **Gerätetabelle** nachzuschauen.</span><span class="sxs-lookup"><span data-stu-id="bc38a-164">You use the relationship to look up plain name of the device type code in the **devices** table.</span></span>

## <a name="create-a-treemap-visualization"></a><span data-ttu-id="bc38a-165">Erstellen einer Treemap-Visualisierung</span><span class="sxs-lookup"><span data-stu-id="bc38a-165">Create a treemap visualization</span></span>

<span data-ttu-id="bc38a-166">In einem Treemap-Diagramm werden hierarchische Daten als Felder in Feldern angezeigt.</span><span class="sxs-lookup"><span data-stu-id="bc38a-166">A treemap chart shows hierarchical data as boxes with in boxes.</span></span> <span data-ttu-id="bc38a-167">Jede Verzweigung der Hierarchie ist ein Feld, das kleinere Felder enthält, die untergeordnete Verzweigungen darstellen.</span><span class="sxs-lookup"><span data-stu-id="bc38a-167">Each branch of the hierarchy is a box contains smaller boxes showing subbranches.</span></span> <span data-ttu-id="bc38a-168">Sie können Power BI Desktop verwenden, um eine Treemap Ihrer Intune-Daten zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="bc38a-168">You can use Power BI desktop to create a treemap of your Intune data.</span></span>

![Visualisierungen > Treemap](media/reports-create-03-treemap.png)

1. <span data-ttu-id="bc38a-170">Wählen Sie einen Diagrammtypen</span><span class="sxs-lookup"><span data-stu-id="bc38a-170">Select a chart type.</span></span> <span data-ttu-id="bc38a-171">und **Treemap** aus.</span><span class="sxs-lookup"><span data-stu-id="bc38a-171">Select **Treemap**.</span></span>
2. <span data-ttu-id="bc38a-172">Suchen Sie im Datenmodell die **Gerätetabelle**.</span><span class="sxs-lookup"><span data-stu-id="bc38a-172">In the data model, find the **devices** table.</span></span>
3. <span data-ttu-id="bc38a-173">Erweitern Sie die **Gerätetabelle**, und wählen Sie das Datenfeld **Hersteller** im Bereich **Felder** aus.</span><span class="sxs-lookup"><span data-stu-id="bc38a-173">Expand the **devices table** and select the **manufacturer** data field in the **Fields** panel.</span></span>
4. <span data-ttu-id="bc38a-174">Ziehen Sie das Datenfeld **Hersteller** auf das Treemap-Diagramm im Berichtszeichenbereich.</span><span class="sxs-lookup"><span data-stu-id="bc38a-174">Drag the **manufacturer** data field to the Treemap chart on the report canvas.</span></span>
5. <span data-ttu-id="bc38a-175">Ziehen Sie das Datenfeld **deviceKey** aus der **Gerätetabelle** in den Abschnitt **Werte** im Bereich **Visualisierung**, und legen Sie es auf dem Feld mit der Bezeichnung **Drag data field here** (Datenfeld hierherziehen) ab.</span><span class="sxs-lookup"><span data-stu-id="bc38a-175">Drag the **deviceKey** data field from the **devices** table to the **Values** section under the **Visualizations** pane and drop on the box labeled **Drag data field here**.</span></span>  
<span data-ttu-id="bc38a-176">Jetzt verfügen Sie über eine Visualisierung der Verteilung von Herstellern und Geräten innerhalb Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="bc38a-176">You now have a visual that shows us the distribution of manufacturers of devices within your organization.</span></span>

![Treemap mit Daten](media/reports-create-06-treemapwdata.png)

## <a name="add-a-filter"></a><span data-ttu-id="bc38a-178">Hinzufügen eines Filters</span><span class="sxs-lookup"><span data-stu-id="bc38a-178">Add a filter</span></span>

<span data-ttu-id="bc38a-179">Sie können Ihrer Treemap einen Filter hinzufügen, damit Sie mithilfe Ihrer App zusätzliche Fragen beantworten können.</span><span class="sxs-lookup"><span data-stu-id="bc38a-179">You can add a filter to your treemap so that you can answer additional questions using your app.</span></span> 

1. <span data-ttu-id="bc38a-180">Wählen Sie zunächst den Berichtszeichenbereich und anschließend unter **Visualisierungen** das **Slicer-Symbol** (![Treemap with data](media/reports-create-slicer.png) (Treemap mit Daten)) aus, um einen Filter hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="bc38a-180">Select the report canvas, and then select the **Slicer icon** ( ![Treemap with data](media/reports-create-slicer.png) ) under **Visualizations** to add a filter.</span></span>
2. <span data-ttu-id="bc38a-181">Suchen Sie die Tabelle **ownerTypes** ziehen Sie das Datenfeld **ownerTypeName** im Abschnitt **Filter** auf den Bereich **Visualisierungen**.</span><span class="sxs-lookup"><span data-stu-id="bc38a-181">Find the **ownerTypes** table and drag the **ownerTypeName** data field under the **Filters** section in the **Visualizations** panel.</span></span>  
   <span data-ttu-id="bc38a-182">In der Gerätetabelle gibt es ein Datenfeld mit der Bezeichnung **OwnerTypeKey**, das einen Code enthält, der darauf hinweist, ob ein Gerät Eigentum eines Unternehmens oder einer Privatperson ist.</span><span class="sxs-lookup"><span data-stu-id="bc38a-182">Under the devices table, there's a data field called **OwnerTypeKey** that contains a code as to whether a device is company-owned or personal.</span></span> <span data-ttu-id="bc38a-183">Da Sie Anzeigenamen in diesem Filter anzeigen wollen, suchen Sie nach der Tabelle **ownerTypes**, und ziehen Sie den **ownerTypeName** dorthin.</span><span class="sxs-lookup"><span data-stu-id="bc38a-183">Since you would like to show friendly names in this filter, look for the **ownerTypes** table and drag the **ownerTypeName**.</span></span> <span data-ttu-id="bc38a-184">Das folgende Beispiel zeigt, inwiefern das Datenmodell Beziehungen zwischen den Tabellen unterstützt.</span><span class="sxs-lookup"><span data-stu-id="bc38a-184">This is an example of how the data model supports relationships between tables.</span></span>

![Treemap mit Filter](media/reports-create-08_ownertype.png)

<span data-ttu-id="bc38a-186">Nun verfügen Sie über einen interaktiven Filter, der zum Wechseln zwischen unternehmenseigenen und privaten Geräten verwendet werden kann. So können Sie Veränderungen in der Verteilung nachvollziehen.</span><span class="sxs-lookup"><span data-stu-id="bc38a-186">You now have an interactive filter that can be used to toggle between company owned and personally owned devices to see how the distribution changes.</span></span>

1. <span data-ttu-id="bc38a-187">Wählen Sie **Unternehmen** aus, damit Ihnen die Verteilung der unternehmenseigenen Geräte angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="bc38a-187">Select **Company** to see that the company owned device distribution.</span></span>
2. <span data-ttu-id="bc38a-188">Wählen Sie **Persönlich** aus, damit Ihnen die privaten Geräte angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="bc38a-188">Select **Personal** to see the personally owned devices.</span></span>

## <a name="next-steps"></a><span data-ttu-id="bc38a-189">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="bc38a-189">Next steps</span></span>

 - <span data-ttu-id="bc38a-190">Erfahren Sie mehr über das [Erstellen und Verwalten von Beziehungen](https://powerbi.microsoft.com/documentation/powerbi-desktop-create-and-manage-relationships/) in Power BI Desktop in der Power BI-Dokumentation.</span><span class="sxs-lookup"><span data-stu-id="bc38a-190">Learn more about [creating and managing relationships](https://powerbi.microsoft.com/documentation/powerbi-desktop-create-and-manage-relationships/) in the Power BI Desktop in the Power BI documentation.</span></span>
 - <span data-ttu-id="bc38a-191">Lesen Sie den Artikel [Datenmodell von Intune Data Warehouse](https://docs.microsoft.com/intune/reports-ref-data-model).</span><span class="sxs-lookup"><span data-stu-id="bc38a-191">Consult the [Intune Data Warehouse Model](https://docs.microsoft.com/intune/reports-ref-data-model).</span></span>