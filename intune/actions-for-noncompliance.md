---
title: "Aktionen bei Inkompatibilität mit Intune"
titleSuffix: Intune on Azure
description: "Erfahren Sie, wie Sie Aktionen für Inkompatibilität mit Intune erstellen."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 10/21/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6d0e0c4b-a562-44f3-82a4-80eb688d4733
ms.reviewer: muhosabe
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: a7f2fe87f2098418c9816f1e3cf0d96f62319469
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2017
---
# <a name="automate-actions-for-noncompliance"></a><span data-ttu-id="50657-103">Automatisieren von Aktionen bei Inkompatibilität</span><span class="sxs-lookup"><span data-stu-id="50657-103">Automate actions for noncompliance</span></span>

<span data-ttu-id="50657-104">Mithilfe der **Aktionen bei Inkompatibilität** können Sie eine zeitlich strukturierte Aktionsfolge für Geräte konfigurieren, die die Kriterien der Kompatibilitätsrichtlinie nicht erfüllen.</span><span class="sxs-lookup"><span data-stu-id="50657-104">The **actions for non-compliance** allow you to configure a time-ordered sequence of actions that are applied to devices that don't meet the compliance policy criteria.</span></span> <span data-ttu-id="50657-105">Intune markiert ein Gerät standardmäßig als „nicht kompatibel“, wenn erkannt wird, dass dieses die Kriterien der Kompatibilitätsrichtlinie nicht erfüllt. Das Gerät wird dann durch den bedingten Zugriff mit Azure AD blockiert.</span><span class="sxs-lookup"><span data-stu-id="50657-105">By default, when a device is detected to not meet the compliance policy criteria, Intune immediately marks it as non-compliant, then Azure AD Conditional Access blocks the device.</span></span> <span data-ttu-id="50657-106">Die **Aktionen bei Inkompatibilität** geben Ihnen mehr Entscheidungsfreiheit beim Umgang mit nicht kompatiblen Geräten.</span><span class="sxs-lookup"><span data-stu-id="50657-106">The **actions for non-compliance** give you more flexibility to decide what to do when a device is not compliant.</span></span> <span data-ttu-id="50657-107">Sie können beispielsweise festlegen, dass das Gerät nicht sofort blockiert werden soll, und dem Benutzer eine Toleranzperiode einräumen, in der er dafür sorgen kann, dass das Gerät kompatibel ist.</span><span class="sxs-lookup"><span data-stu-id="50657-107">For example, you can decide to not block the device immediately, then give the user a grace period to be compliant.</span></span>

<span data-ttu-id="50657-108">Es gibt zwei Arten von Aktionen:</span><span class="sxs-lookup"><span data-stu-id="50657-108">There are two types of actions:</span></span>

-   <span data-ttu-id="50657-109">**Benachrichtigen der Benutzer per E-Mail**: Sie können Ihre E-Mail-Benachrichtigung anpassen, bevor Sie diese an Benutzer senden.</span><span class="sxs-lookup"><span data-stu-id="50657-109">**Notify end-users via e-mail**: You can customize your email notification before sending it to the end user.</span></span> <span data-ttu-id="50657-110">Intune bietet die Anpassung der Empfänger, Betreff und Nachrichtentext, einschließlich Firmenlogo und Kontaktinformationen.</span><span class="sxs-lookup"><span data-stu-id="50657-110">Intune provides customization of the recipients, subject, and message body, including company logo, and contact information.</span></span>

-   <span data-ttu-id="50657-111">**Markieren des Geräts als nicht kompatibel**: Sie können einen Zeitplan mit der Anzahl von Tagen festlegen, nach der ein Gerät als „nicht kompatibel“ markiert werden soll.</span><span class="sxs-lookup"><span data-stu-id="50657-111">**Mark device non-compliant**: You can determine a schedule in number of days after the device should be marked not compliant.</span></span> <span data-ttu-id="50657-112">Dieser Zeitraum kann sofort beginnen oder erst nach einer gewissen Toleranzperiode, um dem Benutzer Gelegenheit zu geben, Ihre Gerätekompatibilitätsrichtlinien zu erfüllen.</span><span class="sxs-lookup"><span data-stu-id="50657-112">This can be immediately, but you can also give the user a grace period to be compliant with your device compliance policies.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="50657-113">Vorbereitung</span><span class="sxs-lookup"><span data-stu-id="50657-113">Before you begin</span></span>

<span data-ttu-id="50657-114">Für die Einrichtung von Aktionen bei Inkompatibilität benötigen Sie mindestens eine Gerätekompatibilitätsrichtlinie.</span><span class="sxs-lookup"><span data-stu-id="50657-114">You need to have at least one device compliance policy created to set up actions for non-compliance.</span></span>

-   <span data-ttu-id="50657-115">Plattformspezifische Informationen zum Erstellen einer Gerätekompatibilitätsrichtlinie finden Sie hier:</span><span class="sxs-lookup"><span data-stu-id="50657-115">Learn how to create a device compliance policy for:</span></span>

    -   [<span data-ttu-id="50657-116">Android</span><span class="sxs-lookup"><span data-stu-id="50657-116">Android</span></span>](compliance-policy-create-android.md)

    -   [<span data-ttu-id="50657-117">Android for Work</span><span class="sxs-lookup"><span data-stu-id="50657-117">Android for Work</span></span>](compliance-policy-create-android-for-work.md)

    -   [<span data-ttu-id="50657-118">iOS</span><span class="sxs-lookup"><span data-stu-id="50657-118">iOS</span></span>](compliance-policy-create-ios.md)
    
    -   [<span data-ttu-id="50657-119">macOS</span><span class="sxs-lookup"><span data-stu-id="50657-119">macOS</span></span>](compliance-policy-create-mac-os.md)

    -   [<span data-ttu-id="50657-120">Windows</span><span class="sxs-lookup"><span data-stu-id="50657-120">Windows</span></span>](compliance-policy-create-windows.md)

<span data-ttu-id="50657-121">Wenn Sie den Zugriff von Geräten auf Unternehmensressourcen mithilfe von Gerätekompatibilitätsrichtlinien sperren möchten, muss der bedingte Zugriff von Azure AD fertig eingerichtet sein.</span><span class="sxs-lookup"><span data-stu-id="50657-121">You need to have Azure AD conditional access set up ready when planning to use device compliance policies to block devices from using corporate resources.</span></span>

- <span data-ttu-id="50657-122">Wie das geht, erfahren Sie [hier](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access).</span><span class="sxs-lookup"><span data-stu-id="50657-122">Learn [how to setup EMS conditional access](https://docs.microsoft.com/azure/active-directory/active-directory-conditional-access).</span></span>

<span data-ttu-id="50657-123">Darüber hinaus benötigen Sie eine Benachrichtigungsvorlage.</span><span class="sxs-lookup"><span data-stu-id="50657-123">Additionally, you need to have a notification message template created.</span></span> <span data-ttu-id="50657-124">Die Benachrichtigungsvorlage wird später beim Erstellen von Aktionen bei Inkompatibilität verwendet, um eine E-Mail an Ihre Benutzer zu senden.</span><span class="sxs-lookup"><span data-stu-id="50657-124">The notification message template is used later in the process of creating actions for non-compliance to send e-mail to your users.</span></span>

### <a name="to-create-a-notification-message-template"></a><span data-ttu-id="50657-125">Erstellen einer Benachrichtigungsvorlage</span><span class="sxs-lookup"><span data-stu-id="50657-125">To create a notification message template</span></span>

1. <span data-ttu-id="50657-126">Navigieren Sie zu [Intune im Azure-Portal](https://portal.azure.com), und melden Sie sich mit Ihren Intune-Anmeldeinformationen an.</span><span class="sxs-lookup"><span data-stu-id="50657-126">Go to the [Intune on Azure portal](https://portal.azure.com), and sign in with your Intune credentials.</span></span>

2. <span data-ttu-id="50657-127">Wählen Sie im linken Menü **Weitere Dienste** aus, und geben Sie in das Filtertextfeld die Zeichenfolge **Intune** ein.</span><span class="sxs-lookup"><span data-stu-id="50657-127">Choose **More services** from the left menu, then type **Intune** in the text box filter.</span></span>

3. <span data-ttu-id="50657-128">Wählen Sie **Intune** aus.</span><span class="sxs-lookup"><span data-stu-id="50657-128">Choose **Intune**</span></span>

4. <span data-ttu-id="50657-129">Wählen Sie **Gerätekompatibilität** und dann **Benachrichtigungen** im Abschnitt **Verwalten** aus.</span><span class="sxs-lookup"><span data-stu-id="50657-129">Choose **Device compliance**, then choose **Notifications** under the **Manage** section.</span></span>

5. <span data-ttu-id="50657-130">Wählen Sie **Benachrichtigung erstellen** aus, und geben Sie Folgendes ein:</span><span class="sxs-lookup"><span data-stu-id="50657-130">Choose **Create notification**, then enter the following:</span></span>

    <span data-ttu-id="50657-131">a.</span><span class="sxs-lookup"><span data-stu-id="50657-131">a.</span></span>  <span data-ttu-id="50657-132">Name</span><span class="sxs-lookup"><span data-stu-id="50657-132">Name</span></span>

    <span data-ttu-id="50657-133">b.</span><span class="sxs-lookup"><span data-stu-id="50657-133">b.</span></span>  <span data-ttu-id="50657-134">Antragsteller</span><span class="sxs-lookup"><span data-stu-id="50657-134">Subject</span></span>

    <span data-ttu-id="50657-135">c.</span><span class="sxs-lookup"><span data-stu-id="50657-135">c.</span></span>  <span data-ttu-id="50657-136">Nachricht</span><span class="sxs-lookup"><span data-stu-id="50657-136">Message</span></span>

    <span data-ttu-id="50657-137">d.</span><span class="sxs-lookup"><span data-stu-id="50657-137">d.</span></span>  <span data-ttu-id="50657-138">E-Mail-Kopfzeile: Unternehmenslogo einschließen</span><span class="sxs-lookup"><span data-stu-id="50657-138">E-mail header – Include company logo</span></span>

    <span data-ttu-id="50657-139">e.</span><span class="sxs-lookup"><span data-stu-id="50657-139">e.</span></span>  <span data-ttu-id="50657-140">E-Mail-Fußzeile: Unternehmensnamen einschließen</span><span class="sxs-lookup"><span data-stu-id="50657-140">E-mail footer – Include company name</span></span>

    <span data-ttu-id="50657-141">f.</span><span class="sxs-lookup"><span data-stu-id="50657-141">f.</span></span>  <span data-ttu-id="50657-142">E-Mail-Fußzeile: Kontaktinformationen einschließen</span><span class="sxs-lookup"><span data-stu-id="50657-142">E-mail footer – Include contact information</span></span>

![Beispiel für die Benachrichtigungsvorlage](./media/actionsfornoncompliance-1.PNG)

<span data-ttu-id="50657-144">Klicken Sie auf **Erstellen**, sobald Sie die Informationen hinzugefügt haben.</span><span class="sxs-lookup"><span data-stu-id="50657-144">Once you're done adding the information, choose **Create**.</span></span> <span data-ttu-id="50657-145">Die Benachrichtigungsvorlage kann nun verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="50657-145">The Notification message template is available for use.</span></span>

> [!NOTE] 
> <span data-ttu-id="50657-146">Sie können auch eine zuvor erstellte Benachrichtigungsvorlage bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="50657-146">You can also edit a Notification template previously created.</span></span>

## <a name="to-create-actions-for-non-compliance"></a><span data-ttu-id="50657-147">So erstellen Sie Aktionen bei Inkompatibilität</span><span class="sxs-lookup"><span data-stu-id="50657-147">To create actions for non-compliance</span></span>

> [!TIP]
> <span data-ttu-id="50657-148">Intune stellt standardmäßig eine vordefinierte Aktion in den Aktionen für den Abschnitt „Inkompatibilität“ bereit.</span><span class="sxs-lookup"><span data-stu-id="50657-148">By default, Intune provides one action pre-defined in the actions for noncompliance section.</span></span> <span data-ttu-id="50657-149">Dabei handelt es sich um die Aktion, mit der ein Gerät als „nicht kompatibel“ markiert wird, nachdem erkannt wurde, dass dieses die Kriterien Ihrer Kompatibilitätsrichtlinie nicht erfüllt.</span><span class="sxs-lookup"><span data-stu-id="50657-149">This is the action to mark the device as not compliant after is detected to not meet your device compliance policy criteria.</span></span> <span data-ttu-id="50657-150">Sie können anpassen, wann das Gerät nach der Erkennung als „nicht kompatibel“ markiert wird.</span><span class="sxs-lookup"><span data-stu-id="50657-150">You can customize how long after the detection the device gets marked not compliant.</span></span> <span data-ttu-id="50657-151">Diese Aktion kann nicht entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="50657-151">This action cannot be removed.</span></span>

<span data-ttu-id="50657-152">Eine Aktion kann beim Erstellen einer neuen Gerätekompatibilitätsrichtlinie oder beim Bearbeiten einer bereits vorhandenen Gerätekompatibilitätsrichtlinie hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="50657-152">You can add an action by the time you’re creating a new device compliance policy or by editing an existing device compliance policy.</span></span>

1.  <span data-ttu-id="50657-153">Wählen Sie auf dem Blatt **Richtlinien zur Gerätekompatibilität** in der Intune-Workload **Richtlinien** im Abschnitt **Verwalten** aus.</span><span class="sxs-lookup"><span data-stu-id="50657-153">In the Intune workload, from the **Device compliance policies** blade, choose **Policies** under the **Manage** section.</span></span>

2.  <span data-ttu-id="50657-154">Wählen Sie eine Richtlinie zur Gerätekompatibilität aus, indem Sie auf diese klicken, und klicken Sie dann auf **Eigenschaften** im Abschnitt **Verwalten**.</span><span class="sxs-lookup"><span data-stu-id="50657-154">Choose a device compliance policy by clicking on it, then choose **Properties** under the **Manage** section.</span></span>

3.  <span data-ttu-id="50657-155">Das Blatt mit den **Eigenschaften für die Kompatibilitätsrichtlinie** wird geöffnet. Wählen Sie hier **Aktionen bei Inkompatibilität** aus.</span><span class="sxs-lookup"><span data-stu-id="50657-155">The **device compliance policy properties** blade opens, choose **Actions for noncompliance**.</span></span>

4.  <span data-ttu-id="50657-156">Wählen Sie auf dem Blatt „Aktionen bei Inkompatibilität“ die Option **Hinzufügen** aus, um Aktionsparameter anzugeben.</span><span class="sxs-lookup"><span data-stu-id="50657-156">The Actions for noncompliance blade opens, choose **Add** to specify action parameters.</span></span> <span data-ttu-id="50657-157">Sie können die zuvor erstellte Benachrichtigungsvorlage, zusätzliche Empfänger und die Toleranzperiode des Zeitplans auswählen.</span><span class="sxs-lookup"><span data-stu-id="50657-157">You can choose the message template previously created, additional recipients, and the grace period schedule.</span></span> <span data-ttu-id="50657-158">Im Zeitplan können Sie die Anzahl von Tagen (0 bis 365) angeben und dann die Richtlinien für den bedingten Zugriff erzwingen.</span><span class="sxs-lookup"><span data-stu-id="50657-158">You can specify the number of days (0 to 365) on the schedule, then you can enforce the conditional access policies.</span></span> <span data-ttu-id="50657-159">Bei Angabe von **0** Tagen wird der Zugriff auf Unternehmensressourcen mittels bedingtem Zugriff **umgehend** blockiert, wenn die Geräte die Gerätekompatibilitätsrichtlinien nicht erfüllen.</span><span class="sxs-lookup"><span data-stu-id="50657-159">If you specify **0** number of days, this means conditional access must **immediately** block access to corporate resources once the devices are non-compliant with device compliance policies.</span></span>

5.  <span data-ttu-id="50657-160">Klicken Sie auf **Hinzufügen** und dann auf **OK**, wenn Sie Ihre Informationen hinzugefügt haben.</span><span class="sxs-lookup"><span data-stu-id="50657-160">Once you're done adding your information, choose **Add**, then **OK**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="50657-161">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="50657-161">Next steps</span></span>

<span data-ttu-id="50657-162">Sie können die Aktivitäten der Gerätekompatibilität überwachen, indem Sie die auf dem Blatt „Gerätekompatibilität“ verfügbaren Berichte ausführen.</span><span class="sxs-lookup"><span data-stu-id="50657-162">You can monitor the device compliance activity by running the reports available in the device compliance blade.</span></span> <span data-ttu-id="50657-163">Erfahren Sie mehr über das [Überwachen der Gerätekompatibilität mit Intune](device-compliance-monitor.md).</span><span class="sxs-lookup"><span data-stu-id="50657-163">Learn more [how to monitor device compliance with Intune](device-compliance-monitor.md)</span></span>

