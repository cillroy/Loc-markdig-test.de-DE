---
title: "Löschen verwalteter Unternehmensdaten aus Apps"
description: "Erfahren Sie, wie Sie selektiv Unternehmensdaten von Geräten entfernen können."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 01/25/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 2742e1d5-d2d5-42cd-b719-665dd6e0a0e9
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 9aeee6e35c820778b11f00d59a5afe364b9774bd
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2017
---
# <a name="wipe-company-app-data-with-intune-mam"></a><span data-ttu-id="3a61f-103">Zurücksetzen von Unternehmens-App-Daten mit Intune MAM</span><span class="sxs-lookup"><span data-stu-id="3a61f-103">Wipe company app data with Intune MAM</span></span>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="3a61f-104">Wenn ein Gerät verloren geht oder gestohlen wird oder wenn der Mitarbeiter das Unternehmen verlässt, müssen Sie sicherstellen, dass Unternehmensdaten in Apps vom Gerät entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="3a61f-104">When a device is lost or stolen, or if the employee leaves your company, you want to make sure company app data is removed from the device.</span></span> <span data-ttu-id="3a61f-105">Allerdings sollten Sie persönliche Daten nicht vom Gerät entfernen, insbesondere dann nicht, wenn das Gerät dem Mitarbeiter gehört.</span><span class="sxs-lookup"><span data-stu-id="3a61f-105">But you might not want to remove personal data on the device, especially if this is an employee-owned device.</span></span>

<span data-ttu-id="3a61f-106">Um Unternehmensdaten aus Apps selektiv zu entfernen, erstellen Sie mithilfe der Schritte in diesem Thema eine Zurücksetzungsanforderung.</span><span class="sxs-lookup"><span data-stu-id="3a61f-106">To selectively remove company app data, create a wipe request by using the steps in this topic.</span></span> <span data-ttu-id="3a61f-107">Nach Abschluss der Anforderung werden die Unternehmensdaten beim nächsten Ausführen der Anwendung aus der App entfernt.</span><span class="sxs-lookup"><span data-stu-id="3a61f-107">After the request is finished, the next time the app runs on the device, company data is removed from the app.</span></span>

>[!IMPORTANT]
> <span data-ttu-id="3a61f-108">Direkt aus der App mit dem nativen Adressbuch synchronisierte Kontakte werden entfernt.</span><span class="sxs-lookup"><span data-stu-id="3a61f-108">Contacts synced directly from the app to the native address book are removed.</span></span> <span data-ttu-id="3a61f-109">Kontakte, die aus dem nativen Adressbuch mit einer anderen externen Quelle synchronisiert werden, können nicht zurückgesetzt werden.</span><span class="sxs-lookup"><span data-stu-id="3a61f-109">Any contacts synced from the native address book to another external source cannot be wiped.</span></span> <span data-ttu-id="3a61f-110">Dies betrifft derzeit nur die Microsoft Outlook-App.</span><span class="sxs-lookup"><span data-stu-id="3a61f-110">Currently, this only applies to the Microsoft Outlook app.</span></span>

## <a name="create-a-wipe-request"></a><span data-ttu-id="3a61f-111">Erstellen einer Zurücksetzungsanforderung</span><span class="sxs-lookup"><span data-stu-id="3a61f-111">Create a wipe request</span></span>

1.  <span data-ttu-id="3a61f-112">Melden Sie sich beim [Azure-Portal](https://portal.azure.com) an.</span><span class="sxs-lookup"><span data-stu-id="3a61f-112">Sign in to the [Azure portal](https://portal.azure.com).</span></span>

2.  <span data-ttu-id="3a61f-113">Wählen Sie **Weitere Dienste** aus, geben Sie in das Filtertextfeld **Intune** ein, und wählen Sie **Intune-App-Schutz** aus.</span><span class="sxs-lookup"><span data-stu-id="3a61f-113">Choose **More Services**, type **Intune** in the filter textbox, and select **Intune App Protection**.</span></span> <span data-ttu-id="3a61f-114">Das Blatt „Mobile Anwendungsverwaltung mit Intune“ wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="3a61f-114">The Intune mobile application management blade opens.</span></span>

    ![Screenshot des Blatts „Neue Zurücksetzungsanforderung“](../media/AppManagement/wipe-request-mam-main-blade.png)

2.  <span data-ttu-id="3a61f-116">Wählen Sie auf dem Blatt **Einstellungen** die Option **Zurücksetzungsanforderungen** aus.</span><span class="sxs-lookup"><span data-stu-id="3a61f-116">On the **Settings** blade, choose **Wipe requests**.</span></span>

3.  <span data-ttu-id="3a61f-117">Wählen Sie **Neue Zurücksetzungsanforderung** aus.</span><span class="sxs-lookup"><span data-stu-id="3a61f-117">Choose  **New wipe request**.</span></span> <span data-ttu-id="3a61f-118">Dadurch wird das Blatt **Neue Zurücksetzungsanforderung** geöffnet.</span><span class="sxs-lookup"><span data-stu-id="3a61f-118">The **New wipe request** blade opens.</span></span>

    ![Screenshot des Blatts „Neue Zurücksetzungsanforderung“](../media/AppManagement/AzurePortal_MAM_NewWipeRequest.png)

4.  <span data-ttu-id="3a61f-120">Wählen Sie **Benutzer** aus, um das Blatt **Benutzer** zu öffnen, und den Benutzer auszuwählen, dessen App-Daten gelöscht werden sollen.</span><span class="sxs-lookup"><span data-stu-id="3a61f-120">Choose **User** to open the **User** blade, and select the user whose app data you want to wipe.</span></span>

5.  <span data-ttu-id="3a61f-121">Wählen Sie **Gerät** aus.</span><span class="sxs-lookup"><span data-stu-id="3a61f-121">Choose **Device**.</span></span> <span data-ttu-id="3a61f-122">Damit öffnen Sie das Blatt **Gerät**, auf dem alle Geräte aufgeführt werden, die dem ausgewählten Benutzer zugeordnet sind. Es enthält außerdem zwei Spalten – eine mit dem Gerätenamen, einem vom Benutzer festgelegten Anzeigenamen, und eine mit dem Gerätetyp und der Geräteplattform.</span><span class="sxs-lookup"><span data-stu-id="3a61f-122">This opens the **Device** blade that lists all the devices associated with the selected user, and also provides two columns, the device name, which is a friendly name defined by the user, and the device type, its device platform.</span></span> <span data-ttu-id="3a61f-123">Wählen Sie das Gerät aus, das zurückgesetzt werden soll.</span><span class="sxs-lookup"><span data-stu-id="3a61f-123">Select the device you want to wipe.</span></span>

6.  <span data-ttu-id="3a61f-124">Sie befinden sich nun wieder auf dem Blatt **Neue Zurücksetzungsanforderung**.</span><span class="sxs-lookup"><span data-stu-id="3a61f-124">You are now back on the **New wipe request** blade.</span></span> <span data-ttu-id="3a61f-125">Wählen Sie **OK** aus, um eine Zurücksetzungsanforderung zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="3a61f-125">Choose **Ok** to make a wipe request.</span></span> 

<span data-ttu-id="3a61f-126">Der Dienst erstellt für jede geschützte App auf dem Gerät und den zugeordneten Benutzer eine separate Zurücksetzungsanforderung und überwacht diese.</span><span class="sxs-lookup"><span data-stu-id="3a61f-126">The service creates and tracks a separate wipe request for each protected app on the device, and the user associated with the wipe request.</span></span>

>[!NOTE]
> <span data-ttu-id="3a61f-127">Sie können auch **Zurücksetzungsanforderungen** erstellen, indem Sie auf dem Blatt „Mobile Anwendungsverwaltung mit Intune“ auf die Kachel **Zurücksetzungsanforderung** klicken.</span><span class="sxs-lookup"><span data-stu-id="3a61f-127">You can also create **Wipe requests** by clicking on the **Wipe request tile** from the Intune mobile application management blade.</span></span>

## <a name="monitor-your-wipe-requests"></a><span data-ttu-id="3a61f-128">Überwachen der Löschanforderungen</span><span class="sxs-lookup"><span data-stu-id="3a61f-128">Monitor your wipe requests</span></span>

<span data-ttu-id="3a61f-129">Sie erhalten einen zusammengefassten Bericht, der den Gesamtstatus der Zurücksetzungsanforderung zeigt und die Anzahl der ausstehenden Anforderungen und Fehler enthält.</span><span class="sxs-lookup"><span data-stu-id="3a61f-129">You can have a summarized report that shows the overall status of the wipe request, and includes the number of pending requests and failures.</span></span> <span data-ttu-id="3a61f-130">Um weitere Informationen zu erhalten, gehen Sie folgendermaßen vor:</span><span class="sxs-lookup"><span data-stu-id="3a61f-130">To get more details, follow these steps:</span></span>

1.  <span data-ttu-id="3a61f-131">Klicken Sie auf dem Blatt „Mobile Anwendungsverwaltung mit Intune“ auf die Kachel **Zurücksetzungsanforderungen**.</span><span class="sxs-lookup"><span data-stu-id="3a61f-131">On the Intune mobile application management blade, click on the **Wipe requests** tile.</span></span>

2.  <span data-ttu-id="3a61f-132">Wählen Sie auf dem Blatt **Zurücksetzungsanforderung** die Kachel **Zurücksetzungsanforderung** aus, um das Blatt **Zurücksetzungsanforderung** zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="3a61f-132">On the **Wipe request** blade, choose the **Wipe request** tile to open the **Wipe request** blade.</span></span>

3.  <span data-ttu-id="3a61f-133">Auf dem Blatt **Zurücksetzungsanforderung** wird eine Liste mit Ihren Anforderungen, gruppiert nach Benutzer, angezeigt.</span><span class="sxs-lookup"><span data-stu-id="3a61f-133">On the **Wipe request** blade, you can see the list of your requests grouped by users.</span></span> <span data-ttu-id="3a61f-134">Da das System für jede geschützte App, die auf dem Gerät ausgeführt wird, eine Zurücksetzungsanforderung erstellt, werden möglicherweise für einen Benutzer mehrere Anforderungen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="3a61f-134">Because the system creates a wipe request for each protected app running on the device, you might see multiple requests for a user.</span></span> <span data-ttu-id="3a61f-135">Der Status gibt an, ob eine Zurücksetzungsaufforderung noch **aussteht**oder **fehlgeschlagen**ist, bzw. **erfolgreich**ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="3a61f-135">The status indicates whether a wipe request is **pending**, **failed**, or **successful**.</span></span>

    ![Screenshot des Blatts „Neue Zurücksetzungsanforderung“](../media/AppManagement/wipe-request-status-1.png)

<span data-ttu-id="3a61f-137">Darüber hinaus können Sie den Gerätenamen und den Gerätetyp anzeigen. Diese Informationen sind beim Lesen von Berichten hilfreich.</span><span class="sxs-lookup"><span data-stu-id="3a61f-137">Additionally, you'll be able to see the device name, and its device type, which can be helpful when reading the reports.</span></span>

>[!IMPORTANT]
> <span data-ttu-id="3a61f-138">Der Benutzer muss die App für das Zurücksetzen öffnen, und das Zurücksetzen dauert bis zu 30 Minuten, nachdem die Anforderung gestellt wurde.</span><span class="sxs-lookup"><span data-stu-id="3a61f-138">The user must open the app for the wipe to occur, and the wipe may take up to 30 minutes after the request was made.</span></span>

## <a name="delete-a-wipe-request"></a><span data-ttu-id="3a61f-139">Löschen einer Zurücksetzungsanforderung</span><span class="sxs-lookup"><span data-stu-id="3a61f-139">Delete a wipe request</span></span>

<span data-ttu-id="3a61f-140">Zurücksetzungen mit Status „Ausstehend“ werden angezeigt, bis Sie sie manuell löschen.</span><span class="sxs-lookup"><span data-stu-id="3a61f-140">Wipes with pending status are displayed until you manually delete them.</span></span>  <span data-ttu-id="3a61f-141">So löschen Sie manuell eine Zurücksetzungsanforderung</span><span class="sxs-lookup"><span data-stu-id="3a61f-141">To manually delete a wipe request</span></span>

1.  <span data-ttu-id="3a61f-142">Klicken Sie auf dem Blatt „Mobile Anwendungsverwaltung mit Intune“ auf die Kachel **Zurücksetzungsanforderungen**.</span><span class="sxs-lookup"><span data-stu-id="3a61f-142">On the Intune mobile application management blade, click on the **Wipe requests** tile.</span></span>

2.  <span data-ttu-id="3a61f-143">Wählen Sie auf dem Blatt **Zurücksetzungsanforderung** die Kachel **Zurücksetzungsanforderung** aus, um das Blatt **Zurücksetzungsanforderung** zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="3a61f-143">On the **Wipe request** blade, choose the **Wipe request** tile to open the **Wipe request** blade.</span></span>

3.  <span data-ttu-id="3a61f-144">Klicken Sie mit der rechten Maustaste auf die Zurücksetzungsanforderung, die Sie löschen möchten, und wählen Sie dann **Zurücksetzungsanforderung abbrechen** aus.</span><span class="sxs-lookup"><span data-stu-id="3a61f-144">Right-click on the wipe request you want to delete, then choose **Delete wipe request**.</span></span>

    ![Screenshot des Blatts „Neue Zurücksetzungsanforderung“](../media/AppManagement/delete-wipe-request.png)

4.  <span data-ttu-id="3a61f-146">Sie werden aufgefordert, den Löschvorgang zu bestätigen. Wählen Sie **Ja** oder **Nein** aus, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="3a61f-146">You're prompted to confirm the deletion, choose **Yes** or **No**, then click **OK**.</span></span>


### <a name="see-also"></a><span data-ttu-id="3a61f-147">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3a61f-147">See also</span></span>
[<span data-ttu-id="3a61f-148">Schützen von App-Daten mithilfe der Verwaltungsrichtlinien für mobile Apps</span><span class="sxs-lookup"><span data-stu-id="3a61f-148">Protect app data using mobile app management policies </span></span>](protect-app-data-using-mobile-app-management-policies-with-microsoft-intune.md)

[<span data-ttu-id="3a61f-149">Verwenden des Azure-Portals</span><span class="sxs-lookup"><span data-stu-id="3a61f-149">Using the Azure portal</span></span>](azure-portal-for-microsoft-intune-mam-policies.md)
