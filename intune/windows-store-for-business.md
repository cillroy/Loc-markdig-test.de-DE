---
title: "Verwalten von Apps aus dem Microsoft Store für Unternehmen"
titlesuffix: Azure portal
description: "Erfahren Sie, wie Sie Apps aus dem Microsoft Store für Unternehmen in Intune synchronisieren und dann zuweisen und nachverfolgen können."
keywords: 
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 11/20/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 2ed5d3f0-2749-45cd-b6bf-fd8c7c08bc1b
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: ecb5a310e8b869deb493bc5554029d641ba419c3
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2017
---
# <a name="how-to-manage-apps-you-purchased-from-the-microsoft-store-for-business-with-microsoft-intune"></a><span data-ttu-id="01793-103">Verwalten von Apps, die im Microsoft Store für Unternehmen mit Microsoft Intune erworben wurden</span><span class="sxs-lookup"><span data-stu-id="01793-103">How to manage apps you purchased from the Microsoft Store for Business with Microsoft Intune</span></span>

[!INCLUDE[azure_portal](./includes/azure_portal.md)]


<span data-ttu-id="01793-104">Im [Microsoft Store für Unternehmen](https://www.microsoft.com/business-store) können Sie Apps für Ihre Organisation suchen und einzeln oder im Rahmen eines Volumenprogramms erwerben.</span><span class="sxs-lookup"><span data-stu-id="01793-104">The [Microsoft Store for Business](https://www.microsoft.com/business-store) gives you a place to find and purchase apps for your organization, individually, or in volume.</span></span> <span data-ttu-id="01793-105">Indem Sie den Store mit Microsoft Intune verbinden, können Sie im Rahmen von per Volumenlizenz erworbenen Apps über das Azure-Portal verwalten.</span><span class="sxs-lookup"><span data-stu-id="01793-105">By connecting the store to Microsoft Intune, you can manage volume-purchased apps from the Azure portal.</span></span> <span data-ttu-id="01793-106">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="01793-106">For example:</span></span>
* <span data-ttu-id="01793-107">Sie können die Liste der Apps, die Sie im Speicher erworben haben, mit Intune synchronisieren.</span><span class="sxs-lookup"><span data-stu-id="01793-107">You can synchronize the list of apps you have purchased from the store with Intune.</span></span>
* <span data-ttu-id="01793-108">Synchronisierte Apps werden in der Intune-Verwaltungskonsole angezeigt und können wie alle anderen Apps zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="01793-108">Apps that are synchronized appear in the Intune administration console; you can assign these apps like any other apps.</span></span>
* <span data-ttu-id="01793-109">Sie können in der Intune-Verwaltungskonsole die Anzahl der verfügbaren und der verwendeten Lizenzen nachverfolgen.</span><span class="sxs-lookup"><span data-stu-id="01793-109">You can track how many licenses are available, and how many are being used in the Intune administration console.</span></span>
* <span data-ttu-id="01793-110">Intune blockiert die Zuweisung und Installation von Apps, wenn nicht genügend Lizenzen vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="01793-110">Intune blocks assignment and installation of apps if there are an insufficient number of licenses available.</span></span>
* <span data-ttu-id="01793-111">Anwendungen, die von Windows Store for Business verwaltet werden, entziehen Lizenzen automatisch, wenn ein Benutzer das Unternehmen verlässt oder der Administrator den Benutzer und dessen Geräte entfernt.</span><span class="sxs-lookup"><span data-stu-id="01793-111">Apps managed by Windows Store for Business will automatically revoke licenses when a user leaves the enterprise, or when the administrator removes the user and the user devices.</span></span>

## <a name="before-you-start"></a><span data-ttu-id="01793-112">Vorbereitung</span><span class="sxs-lookup"><span data-stu-id="01793-112">Before you start</span></span>

<span data-ttu-id="01793-113">Überprüfen Sie die folgenden Informationen, bevor Sie beginnen, Apps aus dem Microsoft Store für Unternehmen zu synchronisieren und zuzuweisen:</span><span class="sxs-lookup"><span data-stu-id="01793-113">Review the following information before you start syncing and assigning apps from the Microsoft Store for Business:</span></span>

- <span data-ttu-id="01793-114">Konfigurieren Sie Intune als Autorität zur Verwaltung mobiler Geräte für Ihre Organisation.</span><span class="sxs-lookup"><span data-stu-id="01793-114">Configure Intune as the mobile device management authority for your organization.</span></span>
- <span data-ttu-id="01793-115">Sie müssen im Microsoft Store für Unternehmen über ein registriertes Konto verfügen.</span><span class="sxs-lookup"><span data-stu-id="01793-115">You must have signed up for an account on the Microsoft Store for Business.</span></span>
- <span data-ttu-id="01793-116">Sobald ein Konto für den Windows Store für Unternehmen Intune zugeordnet wurde, können Sie dieses zugeordnete Konto nicht mehr ändern.</span><span class="sxs-lookup"><span data-stu-id="01793-116">Once you have associated a Windows Business Store account with Intune, you cannot change to a different account in the future.</span></span>
- <span data-ttu-id="01793-117">Apps, die im Store erworben wurden, können Intune nicht manuell hinzugefügt oder daraus gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="01793-117">Apps purchased from the store cannot be manually added to or deleted from Intune.</span></span> <span data-ttu-id="01793-118">Sie können nur mit dem Microsoft Store für Unternehmen synchronisiert werden.</span><span class="sxs-lookup"><span data-stu-id="01793-118">They can only be synchronized with the Microsoft Store for Business.</span></span>
- <span data-ttu-id="01793-119">Intune synchronisiert online und offline lizenzierte Apps, die Sie aus dem Microsoft Store für Unternehmen erworben haben.</span><span class="sxs-lookup"><span data-stu-id="01793-119">Intune synchronizes both online and offline licensed apps you have purchased from the Microsoft Store for Business.</span></span>
- <span data-ttu-id="01793-120">Es können nur kostenlose Offline-Apps mit Intune synchronisiert werden.</span><span class="sxs-lookup"><span data-stu-id="01793-120">Only offline apps that are free of charge can be synced to Intune.</span></span>
- <span data-ttu-id="01793-121">Geräte müssen mit Active Directory Domain Services oder einem Arbeitsbereich verknüpft sein, damit diese Funktion verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="01793-121">To use this capability, devices must be joined to Active Directory Domain Services, or workplace-joined.</span></span>
- <span data-ttu-id="01793-122">Registrierte Geräte müssen die Version 1511 oder höher von Windows 10 verwenden.</span><span class="sxs-lookup"><span data-stu-id="01793-122">Enrolled devices must be using the 1511 release of Windows 10 or later.</span></span>

## <a name="associate-your-microsoft-store-for-business-account-with-intune"></a><span data-ttu-id="01793-123">Verknüpfen Ihres Kontos für den Microsoft Store für Unternehmen mit Intune</span><span class="sxs-lookup"><span data-stu-id="01793-123">Associate your Microsoft Store for Business account with Intune</span></span>
<span data-ttu-id="01793-124">Bevor Sie die Synchronisierung in der Intune-Konsole aktivieren, müssen Sie Ihr Konto für den Windows Store für Unternehmen so konfigurieren, dass Intune als Verwaltungstool verwendet wird:</span><span class="sxs-lookup"><span data-stu-id="01793-124">Before you enable synchronization in the Intune console, you must configure your store account to use Intune as a management tool:</span></span>
1. <span data-ttu-id="01793-125">Stellen Sie sicher, dass Sie sich beim Windows Store für Unternehmen und bei Intune mit demselben Mandantenkonto anmelden.</span><span class="sxs-lookup"><span data-stu-id="01793-125">Ensure that you sign into the Business Store using the same tenant account you use to sign into Intune.</span></span>
2. <span data-ttu-id="01793-126">Wählen Sie im Windows Store für Unternehmen **Einstellungen** > **Verwaltungstools** aus.</span><span class="sxs-lookup"><span data-stu-id="01793-126">In the Business Store, choose **Settings** > **Management tools**.</span></span>
3. <span data-ttu-id="01793-127">Wählen Sie auf der Seite „Verwaltungstools“ die Option **Verwaltungstool hinzufügen** und dann **Microsoft Intune** aus.</span><span class="sxs-lookup"><span data-stu-id="01793-127">On the Management tools page, choose **Add a management tool**, and choose **Microsoft Intune**.</span></span>

> [!NOTE]
> <span data-ttu-id="01793-128">Zuvor konnten Sie nur ein Verwaltungstool zum Zuweisen von Apps mit Microsoft Store für Unternehmen zuweisen.</span><span class="sxs-lookup"><span data-stu-id="01793-128">You could previously only associate one management tool to assign apps with the Microsoft Store for Business.</span></span> <span data-ttu-id="01793-129">Nun können Sie mehrere Verwaltungstools dem Store zuordnen, z.B. Intune und Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="01793-129">You can now associate multiple management tools with the store, for example, Intune and Configuration Manager.</span></span>

<span data-ttu-id="01793-130">Sie können nun fortfahren und die Synchronisierung in der Intune-Konsole einrichten.</span><span class="sxs-lookup"><span data-stu-id="01793-130">You can now continue, and set up synchronization in the Intune console.</span></span>

## <a name="configure-synchronization"></a><span data-ttu-id="01793-131">Konfigurieren der Synchronisierung</span><span class="sxs-lookup"><span data-stu-id="01793-131">Configure synchronization</span></span>

1. <span data-ttu-id="01793-132">Melden Sie sich beim Azure-Portal an.</span><span class="sxs-lookup"><span data-stu-id="01793-132">Sign into the Azure portal.</span></span>
2. <span data-ttu-id="01793-133">Wählen Sie **Weitere Dienste** > **Überwachung und Verwaltung** > **Intune** aus.</span><span class="sxs-lookup"><span data-stu-id="01793-133">Choose **More Services** > **Monitoring + Management** > **Intune**.</span></span>
3. <span data-ttu-id="01793-134">Wählen Sie auf dem Blatt **Intune** die Option **Mobile Apps** aus.</span><span class="sxs-lookup"><span data-stu-id="01793-134">On the **Intune** blade, choose **Mobile apps**.</span></span>
1. <span data-ttu-id="01793-135">Wählen Sie auf dem Blatt **Mobile Apps** die Option **Setup** > **Microsoft Store für Unternehmen** aus.</span><span class="sxs-lookup"><span data-stu-id="01793-135">On the **Mobile Apps** blade, choose **Setup** > **Microsoft Store for Business**.</span></span>
2. <span data-ttu-id="01793-136">Klicken Sie auf **Aktivieren**.</span><span class="sxs-lookup"><span data-stu-id="01793-136">Click **Enable**.</span></span>
3. <span data-ttu-id="01793-137">Klicken Sie auf den Link zur Registrierung für den Microsoft Store für Unternehmen, falls Sie dies noch nicht getan haben, und weisen Sie Ihr Konto wie oben beschrieben zu.</span><span class="sxs-lookup"><span data-stu-id="01793-137">If you haven't already done so, click the link to sign up for the Microsoft Store for Business and associate your account as detailed previously.</span></span>
5. <span data-ttu-id="01793-138">Wählen Sie in der Dropdownliste **Sprache** die Sprache aus, in der Apps aus dem Microsoft Store für Unternehmen im Azure-Portal angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="01793-138">From the **Language** drop-down list, choose the language in which apps from the Microsoft Store for Business is displayed in the Azure portal.</span></span> <span data-ttu-id="01793-139">Die Installation der Apps erfolgt unabhängig von der Anzeigesprache in der Sprache des Endbenutzers, sofern verfügbar.</span><span class="sxs-lookup"><span data-stu-id="01793-139">Regardless of the language in which they are displayed, they are installed in the end user's language when available.</span></span>
6. <span data-ttu-id="01793-140">Klicken Sie auf **Synchronisieren**, um die im Microsoft Store erworbenen Apps in Intune abzurufen.</span><span class="sxs-lookup"><span data-stu-id="01793-140">Click **Sync** to get the apps you've purchased from the Microsoft Store into Intune.</span></span>

## <a name="synchronize-apps"></a><span data-ttu-id="01793-141">Synchronisieren von Apps</span><span class="sxs-lookup"><span data-stu-id="01793-141">Synchronize apps</span></span>

1. <span data-ttu-id="01793-142">Wählen Sie in der Workload **Mobile Apps** die Option **Setup** > **Microsoft Store für Unternehmen** aus.</span><span class="sxs-lookup"><span data-stu-id="01793-142">In the **Mobile apps** workload, choose **Setup** > **Microsoft Store for Business**.</span></span>
2. <span data-ttu-id="01793-143">Klicken Sie auf **Synchronisieren**, um die im Microsoft Store erworbenen Apps in Intune abzurufen.</span><span class="sxs-lookup"><span data-stu-id="01793-143">Click **Sync** to get the apps you've purchased from the Microsoft Store into Intune.</span></span>

## <a name="assign-apps"></a><span data-ttu-id="01793-144">Zuweisen von Apps</span><span class="sxs-lookup"><span data-stu-id="01793-144">Assign apps</span></span>

<span data-ttu-id="01793-145">Sie weisen Apps aus dem Store auf die gleiche Weise wie andere Intune-Apps zu.</span><span class="sxs-lookup"><span data-stu-id="01793-145">You assign apps from the store in the same way you assign any other Intune app.</span></span> <span data-ttu-id="01793-146">Weitere Informationen finden Sie unter [Zuweisen von Apps zu Gruppen mit Microsoft Intune](apps-deploy.md).</span><span class="sxs-lookup"><span data-stu-id="01793-146">For more information, see [How to assign apps to groups with Microsoft Intune](apps-deploy.md).</span></span> <span data-ttu-id="01793-147">Anstelle der Zuweisung von Apps auf der Seite **Alle Apps** weisen Sie diese über die Seite **Lizenzierte Apps** zu.</span><span class="sxs-lookup"><span data-stu-id="01793-147">However, instead of assigning apps from the **All Apps** page, you assign them from the **Licensed Apps** page.</span></span>

<span data-ttu-id="01793-148">Offline-Apps können Benutzergruppen, Gerätegruppen oder Gruppen mit Benutzern und Geräten als Ziel haben.</span><span class="sxs-lookup"><span data-stu-id="01793-148">Offline apps can be targeted to user groups, device groups, or groups with users and devices.</span></span>
<span data-ttu-id="01793-149">Offline-Apps können für einen bestimmten Benutzer auf einem Gerät oder für alle Benutzer auf einem Gerät installiert werden.</span><span class="sxs-lookup"><span data-stu-id="01793-149">Offline apps can be installed for a specific user on a device or for all users on a device.</span></span> 


<span data-ttu-id="01793-150">Wenn Sie eine App aus dem Microsoft Store für Unternehmen zuweisen, wird von jedem Benutzer, der die App installiert, eine Lizenz verwendet.</span><span class="sxs-lookup"><span data-stu-id="01793-150">When you assign a Microsoft Store for Business app, a license is used by each user who installs the app.</span></span> <span data-ttu-id="01793-151">Wenn alle verfügbaren Lizenzen für eine zugewiesene App verwendet werden, können Sie keine weiteren Kopien zuweisen.</span><span class="sxs-lookup"><span data-stu-id="01793-151">If you use all of the available licenses for an assigned app, you cannot assign any more copies.</span></span> <span data-ttu-id="01793-152">Unternehmen Sie eine der folgenden Aktionen aus:</span><span class="sxs-lookup"><span data-stu-id="01793-152">Take one of the following actions:</span></span>
* <span data-ttu-id="01793-153">Deinstallieren Sie die App auf einigen Geräten.</span><span class="sxs-lookup"><span data-stu-id="01793-153">Uninstall the app from some devices.</span></span>
* <span data-ttu-id="01793-154">Beschränken Sie die aktuelle Zuweisung auf die Anzahl von Benutzern, für die Sie über Lizenzen verfügen.</span><span class="sxs-lookup"><span data-stu-id="01793-154">Reduce the scope of the current assignment, targeting only the users you have sufficient licenses for.</span></span>
* <span data-ttu-id="01793-155">Erwerben Sie zusätzliche Kopien der App im Microsoft Store für Unternehmen.</span><span class="sxs-lookup"><span data-stu-id="01793-155">Buy more copies of the app from the Microsoft Store for Business.</span></span>


