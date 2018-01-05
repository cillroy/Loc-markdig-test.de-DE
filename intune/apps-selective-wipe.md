---
title: "So setzen Sie nur die Unternehmensdaten in einer App zurück"
titleSuffix: Azure portal
description: "Erfahren Sie, wie Sie Apps mit Microsoft Intune selektiv zurücksetzen.\""
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 12/05/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 42605e6e-5b84-44ff-b86e-346ea123b53e
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 67d3333a7c6c56b032a9f0e1800b453924d677eb
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2017
---
# <a name="how-to-wipe-only-corporate-data-from-intune-managed-apps"></a><span data-ttu-id="cb621-103">Zurücksetzen nur von Unternehmensdaten in einer in Intune verwalteten App</span><span class="sxs-lookup"><span data-stu-id="cb621-103">How to wipe only corporate data from Intune-managed apps</span></span>

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="cb621-104">Wenn ein Gerät verloren geht oder gestohlen wird oder wenn der Mitarbeiter das Unternehmen verlässt, müssen Sie sicherstellen, dass Unternehmensdaten in Apps vom Gerät entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="cb621-104">When a device is lost or stolen, or if the employee leaves your company, you want to make sure company app data is removed from the device.</span></span> <span data-ttu-id="cb621-105">Allerdings sollten Sie persönliche Daten nicht vom Gerät entfernen, insbesondere dann nicht, wenn das Gerät dem Mitarbeiter gehört.</span><span class="sxs-lookup"><span data-stu-id="cb621-105">But you might not want to remove personal data on the device, especially if this is an employee-owned device.</span></span>

>[!NOTE]
> <span data-ttu-id="cb621-106">Für das Zurücksetzen von Unternehmensdaten von mit Intune verwalteten Apps werden derzeit die iOS- und Android-Plattform unterstützt.</span><span class="sxs-lookup"><span data-stu-id="cb621-106">The iOS and Android platforms are the two platforms currently supported for wiping corporate data from Intune managed apps.</span></span>

<span data-ttu-id="cb621-107">Um Unternehmensdaten aus Apps selektiv zu entfernen, erstellen Sie mithilfe der Schritte in diesem Thema eine Zurücksetzungsanforderung.</span><span class="sxs-lookup"><span data-stu-id="cb621-107">To selectively remove company app data, create a wipe request by using the steps in this topic.</span></span> <span data-ttu-id="cb621-108">Nach Abschluss der Anforderung werden die Unternehmensdaten beim nächsten Ausführen der Anwendung aus der App entfernt.</span><span class="sxs-lookup"><span data-stu-id="cb621-108">After the request is finished, the next time the app runs on the device, company data is removed from the app.</span></span>

>[!IMPORTANT]
> <span data-ttu-id="cb621-109">Direkt aus der App mit dem nativen Adressbuch synchronisierte Kontakte werden entfernt.</span><span class="sxs-lookup"><span data-stu-id="cb621-109">Contacts synced directly from the app to the native address book are removed.</span></span> <span data-ttu-id="cb621-110">Kontakte, die aus dem nativen Adressbuch mit einer anderen externen Quelle synchronisiert werden, können nicht zurückgesetzt werden.</span><span class="sxs-lookup"><span data-stu-id="cb621-110">Any contacts synced from the native address book to another external source cannot be wiped.</span></span> <span data-ttu-id="cb621-111">Dies betrifft derzeit nur die Microsoft Outlook-App.</span><span class="sxs-lookup"><span data-stu-id="cb621-111">Currently, this only applies to the Microsoft Outlook app.</span></span>

## <a name="create-a-wipe-request"></a><span data-ttu-id="cb621-112">Erstellen einer Zurücksetzungsanforderung</span><span class="sxs-lookup"><span data-stu-id="cb621-112">Create a wipe request</span></span>

1.  <span data-ttu-id="cb621-113">Melden Sie sich beim [Azure-Portal](https://portal.azure.com) an.</span><span class="sxs-lookup"><span data-stu-id="cb621-113">Sign in to the [Azure portal](https://portal.azure.com).</span></span>

2.  <span data-ttu-id="cb621-114">Wählen Sie **Weitere Dienste** aus, geben Sie in das Filtertextfeld **Intune** ein, und wählen Sie **Intune** aus.</span><span class="sxs-lookup"><span data-stu-id="cb621-114">Choose **More Services**, type **Intune** in the filter textbox, and select **Intune**.</span></span> <span data-ttu-id="cb621-115">Das Intune-Blatt wird geöffnet. Wählen Sie das Blatt **Mobile Apps** aus.</span><span class="sxs-lookup"><span data-stu-id="cb621-115">The Intune blade opens, choose the **Mobile apps** blade.</span></span>

    ![Screenshot des Blatts „Microsoft Intune“](./media/apps-selective-wipe01.png)

3.  <span data-ttu-id="cb621-117">Wählen Sie auf dem Blatt **Mobile Apps** die Option **Selektive App-Zurücksetzung** aus.</span><span class="sxs-lookup"><span data-stu-id="cb621-117">On the **Mobile apps blade**, choose **App selective wipe**.</span></span>

4.  <span data-ttu-id="cb621-118">Wählen Sie **Neue Zurücksetzungsanforderung** aus.</span><span class="sxs-lookup"><span data-stu-id="cb621-118">Choose  **New wipe request**.</span></span> <span data-ttu-id="cb621-119">Dadurch wird das Blatt **Neue Zurücksetzungsanforderung** geöffnet.</span><span class="sxs-lookup"><span data-stu-id="cb621-119">The **New wipe request** blade opens.</span></span>

    ![Screenshot des Blatts „Neue Zurücksetzungsanforderung“](./media/AzurePortal_MAM_NewWipeRequest.png)

5.  <span data-ttu-id="cb621-121">Wählen Sie **Benutzer** aus, um das Blatt **Benutzer** zu öffnen, und den Benutzer auszuwählen, dessen App-Daten gelöscht werden sollen.</span><span class="sxs-lookup"><span data-stu-id="cb621-121">Choose **User** to open the **User** blade, and select the user whose app data you want to wipe.</span></span>

6.  <span data-ttu-id="cb621-122">Wählen Sie als Nächstes **Gerät** auf dem Blatt **Neue Zurücksetzungsanforderung** aus.</span><span class="sxs-lookup"><span data-stu-id="cb621-122">Next, choose **Device** from the **New wipe request** blade.</span></span> <span data-ttu-id="cb621-123">Damit öffnen Sie das Blatt **Gerät auswählen**, auf dem alle Geräte aufgeführt werden, die dem ausgewählten Benutzer zugeordnet sind. Es enthält außerdem zwei Spalten – eine mit dem Gerätenamen, einem vom Benutzer festgelegten Anzeigenamen, und eine mit dem Gerätetyp und der Geräteplattform.</span><span class="sxs-lookup"><span data-stu-id="cb621-123">This opens the **Select Device** blade that lists all the devices associated with the selected user, and also provides two columns, the device name, which is a friendly name defined by the user, and the device type, its device platform.</span></span> <span data-ttu-id="cb621-124">Wählen Sie das Gerät aus, das zurückgesetzt werden soll.</span><span class="sxs-lookup"><span data-stu-id="cb621-124">Select the device you want to wipe.</span></span>

7.  <span data-ttu-id="cb621-125">Sie befinden sich nun wieder auf dem Blatt **Neue Zurücksetzungsanforderung**.</span><span class="sxs-lookup"><span data-stu-id="cb621-125">You are now back on the **New wipe request** blade.</span></span> <span data-ttu-id="cb621-126">Wählen Sie **OK** aus, um eine Zurücksetzungsanforderung zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="cb621-126">Choose **Ok** to make a wipe request.</span></span>

<span data-ttu-id="cb621-127">Der Dienst erstellt für jede geschützte App auf dem Gerät und den zugeordneten Benutzer eine separate Zurücksetzungsanforderung und überwacht diese.</span><span class="sxs-lookup"><span data-stu-id="cb621-127">The service creates and tracks a separate wipe request for each protected app on the device, and the user associated with the wipe request.</span></span>

## <a name="monitor-your-wipe-requests"></a><span data-ttu-id="cb621-128">Überwachen der Löschanforderungen</span><span class="sxs-lookup"><span data-stu-id="cb621-128">Monitor your wipe requests</span></span>

<span data-ttu-id="cb621-129">Sie erhalten einen zusammengefassten Bericht, der den Gesamtstatus der Zurücksetzungsanforderung zeigt und die Anzahl der ausstehenden Anforderungen und Fehler enthält.</span><span class="sxs-lookup"><span data-stu-id="cb621-129">You can have a summarized report that shows the overall status of the wipe request, and includes the number of pending requests and failures.</span></span> <span data-ttu-id="cb621-130">Um weitere Informationen zu erhalten, gehen Sie folgendermaßen vor:</span><span class="sxs-lookup"><span data-stu-id="cb621-130">To get more details, follow these steps:</span></span>

1.  <span data-ttu-id="cb621-131">Auf dem Blatt **Mobile Apps – Selektive App-Zurücksetzung** wird eine Liste mit Ihren Anforderungen, gruppiert nach Benutzer, angezeigt.</span><span class="sxs-lookup"><span data-stu-id="cb621-131">On the **Mobile Apps - App selective wipe** blade, you can see the list of your requests grouped by users.</span></span> <span data-ttu-id="cb621-132">Da das System für jede geschützte App, die auf dem Gerät ausgeführt wird, eine Zurücksetzungsanforderung erstellt, werden möglicherweise für einen Benutzer mehrere Anforderungen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="cb621-132">Because the system creates a wipe request for each protected app running on the device, you might see multiple requests for a user.</span></span> <span data-ttu-id="cb621-133">Der Status gibt an, ob eine Zurücksetzungsaufforderung noch **aussteht**oder **fehlgeschlagen**ist, bzw. **erfolgreich**ausgeführt wurde.</span><span class="sxs-lookup"><span data-stu-id="cb621-133">The status indicates whether a wipe request is **pending**, **failed**, or **successful**.</span></span>

    ![Screenshot des Zurücksetzungsanforderungsstatus auf dem Blatt „Selektive App-Zurücksetzung“](./media/wipe-request-status-1.png)

<span data-ttu-id="cb621-135">Darüber hinaus können Sie den Gerätenamen und den Gerätetyp anzeigen. Diese Informationen sind beim Lesen von Berichten hilfreich.</span><span class="sxs-lookup"><span data-stu-id="cb621-135">Additionally, you'll be able to see the device name, and its device type, which can be helpful when reading the reports.</span></span>

>[!IMPORTANT]
> <span data-ttu-id="cb621-136">Der Benutzer muss die App für das Zurücksetzen öffnen, und das Zurücksetzen dauert bis zu 30 Minuten, nachdem die Anforderung gestellt wurde.</span><span class="sxs-lookup"><span data-stu-id="cb621-136">The user must open the app for the wipe to occur, and the wipe may take up to 30 minutes after the request was made.</span></span>

## <a name="delete-a-wipe-request"></a><span data-ttu-id="cb621-137">Löschen einer Zurücksetzungsanforderung</span><span class="sxs-lookup"><span data-stu-id="cb621-137">Delete a wipe request</span></span>

<span data-ttu-id="cb621-138">Zurücksetzungen mit Status „Ausstehend“ werden angezeigt, bis Sie sie manuell löschen.</span><span class="sxs-lookup"><span data-stu-id="cb621-138">Wipes with pending status are displayed until you manually delete them.</span></span>  <span data-ttu-id="cb621-139">So löschen Sie manuell eine Zurücksetzungsanforderung</span><span class="sxs-lookup"><span data-stu-id="cb621-139">To manually delete a wipe request:</span></span>

1.  <span data-ttu-id="cb621-140">Führen Sie auf dem Blatt **Mobile Apps – Selektive App-Zurücksetzung** folgende Schritte durch.</span><span class="sxs-lookup"><span data-stu-id="cb621-140">On the **Mobile Apps - App selective wipe** blade.</span></span>

2.  <span data-ttu-id="cb621-141">Klicken Sie mit der rechten Maustaste auf die Zurücksetzungsanforderung, die Sie löschen möchten, und wählen Sie dann **Zurücksetzungsanforderung löschen** aus.</span><span class="sxs-lookup"><span data-stu-id="cb621-141">From the list, right-click on the wipe request you want to delete, then choose **Delete wipe request**.</span></span>

    ![Screenshot der Zurücksetzungsanforderungsliste auf dem Blatt „Selektive App-Zurücksetzung“](./media/delete-wipe-request.png)

3.  <span data-ttu-id="cb621-143">Sie werden aufgefordert, den Löschvorgang zu bestätigen. Wählen Sie **Ja** oder **Nein** aus, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="cb621-143">You're prompted to confirm the deletion, choose **Yes** or **No**, then click **OK**.</span></span>

### <a name="see-also"></a><span data-ttu-id="cb621-144">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="cb621-144">See also</span></span>
[<span data-ttu-id="cb621-145">Was sind App-Schutzrichtlinien?</span><span class="sxs-lookup"><span data-stu-id="cb621-145">What's app protection policy</span></span>](app-protection-policy.md)

[<span data-ttu-id="cb621-146">Was ist die App-Verwaltung?</span><span class="sxs-lookup"><span data-stu-id="cb621-146">What's app management</span></span>](app-management.md)
