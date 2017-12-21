---
title: Festlegen von Nutzungsbedingungen in Microsoft Intune
titlesuffix: Azure portal
description: "Legen Sie Geschäftsbedingungen fest, die Benutzern im Unternehmensportal für Intune angezeigt werden. "
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 10/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 4a3a11a8-9c0c-4334-8c6b-6fea4d0a2efb
ms.reviewer: amyro
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 4842bf766659ebedd89035a8b13521ca63e2f3a4
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2017
---
# <a name="ensure-users-accept-company-terms-for-access"></a><span data-ttu-id="7be3d-103">Sicherstellen, dass Benutzer Geschäftsbedingungen für den Zugriff akzeptieren</span><span class="sxs-lookup"><span data-stu-id="7be3d-103">Ensure users accept company terms for access</span></span>

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="7be3d-104">Als Intune-Administrator können Sie festlegen, dass für Benutzer die Annahme der Geschäftsbedingungen Ihres Unternehmens erforderlich ist, bevor diese das Unternehmensportal verwenden können, um ihre Geräte zu registrieren und auf Ressourcen wie Unternehmens-Apps und -E-Mails zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="7be3d-104">As an Intune admin, you can require that users accept your company's terms and conditions before they can use the Company Portal to enroll their devices and access resources like company apps and email.</span></span> <span data-ttu-id="7be3d-105">Die Konfiguration der Geschäftsbedingungen ist optional.</span><span class="sxs-lookup"><span data-stu-id="7be3d-105">Configuration of terms and conditions is optional.</span></span>

<span data-ttu-id="7be3d-106">Sie können mehrere Sätze von Bedingungen erstellen und diese verschiedenen Gruppen zuweisen, um z. B. verschiedene Sprachen zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="7be3d-106">You can create multiple sets of terms and assign them to different groups, such as to support different languages.</span></span>

## <a name="create-terms-and-conditions"></a><span data-ttu-id="7be3d-107">Erstellen von Geschäftsbedingungen</span><span class="sxs-lookup"><span data-stu-id="7be3d-107">Create terms and conditions</span></span>
<span data-ttu-id="7be3d-108">Führen Sie die folgenden Schritte aus, um Geschäftsbedingungen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="7be3d-108">Complete these steps to create terms and conditions.</span></span> <span data-ttu-id="7be3d-109">Der Anzeigename und die Beschreibung sind für administrative Zwecke vorgesehen, während die Eigenschaften der Bedingungen den Benutzern im Unternehmensportal angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="7be3d-109">The display name and description are for administrative use while terms properties are displayed to users in the Company Portal.</span></span>

1. <span data-ttu-id="7be3d-110">Wählen Sie im Azure-Portal die Option **Geräteregistrierung** und dann **Geschäftsbedingungen** aus.</span><span class="sxs-lookup"><span data-stu-id="7be3d-110">In the Azure portal, choose **Device enrollment**, and then choose **Terms and Conditions**.</span></span>
2. <span data-ttu-id="7be3d-111">Wählen Sie **Erstellen** aus.</span><span class="sxs-lookup"><span data-stu-id="7be3d-111">Select **Create**.</span></span>
<span data-ttu-id="7be3d-112">![Screenshot: Azure-Portal mit Schaltfläche zum Erstellen von Geschäftsbedingungen](media/terms-create-terms.png)</span><span class="sxs-lookup"><span data-stu-id="7be3d-112">![Screenshot of the Azure portal showing Create button for terms and conditions](media/terms-create-terms.png)</span></span>
3. <span data-ttu-id="7be3d-113">Geben Sie auf dem erweiterten Blatt die folgenden Informationen an:</span><span class="sxs-lookup"><span data-stu-id="7be3d-113">On the expanded blade, specify the following information:</span></span>

   - <span data-ttu-id="7be3d-114">**Anzeigename**: Die Bezeichnung für die Bedingungen im Azure-Portal.</span><span class="sxs-lookup"><span data-stu-id="7be3d-114">**Display name**: The name for the terms in the Azure portal.</span></span> <span data-ttu-id="7be3d-115">Diese Bezeichnung wird den Benutzern nicht angezeigt.</span><span class="sxs-lookup"><span data-stu-id="7be3d-115">Users don't see this name.</span></span>

   - <span data-ttu-id="7be3d-116">**Beschreibung**: Optionale Details, die Ihnen dabei helfen, diese Bedingungen im Azure-Portal zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="7be3d-116">**Description**: Optional details that help you identify this set of terms in the Azure portal.</span></span>

4. <span data-ttu-id="7be3d-117">Wählen Sie den Pfeil neben „Nutzungsbedingungen definieren“ aus, um das Blatt „Nutzungsbedingungen“ zu öffnen, und geben Sie dann die folgende Informationen ein:</span><span class="sxs-lookup"><span data-stu-id="7be3d-117">Select the arrow next to Define terms of use to open the Terms and Conditions blade, and then enter the following information:</span></span>

   ![Screenshots des Bildschirms mit der Akzeptanz von Nutzungsbedingungen für Endbenutzer mit der Zusammenfassung der Nutzungsbedingungen](./media/terms-summary-create.png)

   - <span data-ttu-id="7be3d-119">**Titel**: Der Name für Ihre Bedingungen, die Benutzern im Unternehmensportal oberhalb der **Zusammenfassung** angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="7be3d-119">**Title**: The name for your terms that users see in the Company Portal above the **Summary**.</span></span>
   - <span data-ttu-id="7be3d-120">**Zusammenfassung der Nutzungsbedingungen**: Text, aus dem hervorgeht, welche Folgen die Annahme der Bedingungen für den Benutzer hat.</span><span class="sxs-lookup"><span data-stu-id="7be3d-120">**Summary of Terms**: Text that explains what it means when users accept the terms.</span></span> <span data-ttu-id="7be3d-121">Beispiel: Durch die Registrierung Ihres Geräts stimmen Sie den von Contoso dargelegten Nutzungsbedingungen zu.</span><span class="sxs-lookup"><span data-stu-id="7be3d-121">For example, "By enrolling your device, you are agreeing to the terms of use set out by Contoso.</span></span> <span data-ttu-id="7be3d-122">Lesen Sie die Bedingungen sorgfältig durch, bevor Sie fortfahren.</span><span class="sxs-lookup"><span data-stu-id="7be3d-122">Read the terms carefully before proceeding."</span></span>
   - <span data-ttu-id="7be3d-123">**Geschäftsbedingungen**: Die Geschäftsbedingungen, die den Benutzern angezeigt und von ihnen angenommen oder abgelehnt werden müssen.</span><span class="sxs-lookup"><span data-stu-id="7be3d-123">**Terms and Conditions**: The terms and conditions that users see and must either accept or reject.</span></span>

5. <span data-ttu-id="7be3d-124">Wählen Sie **OK** und dann **Erstellen** aus.</span><span class="sxs-lookup"><span data-stu-id="7be3d-124">Select **Ok** and then select **Create**.</span></span>

## <a name="see-how-terms-are-displayed-to-your-users"></a><span data-ttu-id="7be3d-125">Darstellung der Nutzungsbedingungen für die Benutzer</span><span class="sxs-lookup"><span data-stu-id="7be3d-125">See how terms are displayed to your users</span></span>
<span data-ttu-id="7be3d-126">Das folgende Beispiel zeigt **Titel** und **Zusammenfassung der Nutzungsbedingungen** in der Verwaltungskonsole und im Unternehmensportal.</span><span class="sxs-lookup"><span data-stu-id="7be3d-126">The following example shows the **Title** and **Summary of Terms** in the admin console and Company Portal.</span></span>

![Screenshot von „Titel“ und „Zusammenfassung der Nutzungsbedingungen“ in der Verwaltungskonsole und im Unternehmensportal.](./media/terms-summary-terms.png)

<span data-ttu-id="7be3d-128">Das folgende Beispiel zeigt die Geschäftsbedingungen in der Verwaltungskonsole und im Unternehmensportal.</span><span class="sxs-lookup"><span data-stu-id="7be3d-128">The following example shows the terms and conditions in the admin console and the Company Portal.</span></span>

![Screenshot der Geschäftsbedingungen in der Verwaltungskonsole und im Unternehmensportal.](./media/terms-properties-terms.png)

## <a name="assign-terms-and-conditions"></a><span data-ttu-id="7be3d-130">Zuweisen von Geschäftsbedingungen</span><span class="sxs-lookup"><span data-stu-id="7be3d-130">Assign terms and conditions</span></span>

<span data-ttu-id="7be3d-131">Sie können Geschäftsbedingungen zu Benutzergruppen zuweisen, die diese vor der Verwendung des Unternehmensportals annehmen müssen.</span><span class="sxs-lookup"><span data-stu-id="7be3d-131">You can assign terms and conditions to groups of user who must accept them before using the Company Portal.</span></span>

1. <span data-ttu-id="7be3d-132">Wählen Sie im Azure-Portal die Option **Geräteregistrierung** und dann **Geschäftsbedingungen** aus.</span><span class="sxs-lookup"><span data-stu-id="7be3d-132">In the Azure portal, choose **Device enrollment**, and then choose **Terms and Conditions**.</span></span>
2. <span data-ttu-id="7be3d-133">Wählen Sie in der Liste der Geschäftsbedingungen die Bedingungen aus, die Sie zuweisen möchten, und wählen Sie dann **Zugewiesene Gruppen** aus.</span><span class="sxs-lookup"><span data-stu-id="7be3d-133">In the list of terms and conditions, select the terms you want to assign, and then select **Assigned Groups**.</span></span>
<span data-ttu-id="7be3d-134">![Screenshot des Blatts „Gruppe zuweisen“ des Azure-Portals, das die Schaltfläche „Gruppe auswählen“ und die Schaltfläche „Auswählen“ für die Zuweisung der Geschäftsbedingungen anzeigt](media/terms-assign-groups.png)</span><span class="sxs-lookup"><span data-stu-id="7be3d-134">![Screenshot of the Azure portal's Assign Group blade showing Select Group button and Select button for terms and conditions assignment](media/terms-assign-groups.png)</span></span>
3. <span data-ttu-id="7be3d-135">Klicken Sie auf die Schaltfläche **Gruppe auswählen**, und wählen Sie auf dem Blatt **Gruppen auswählen** die Gruppen aus, denen Sie die Bedingungen zuweisen möchten. Klicken Sie anschließend auf **Auswählen**.</span><span class="sxs-lookup"><span data-stu-id="7be3d-135">Click the **Select Group** button and in the **Select Groups** blade, select the groups you want to assign the terms, and then click **Select**.</span></span> <span data-ttu-id="7be3d-136">Dynamischen Gruppen können keine Geschäftsbedingungen zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="7be3d-136">Dynamic groups cannot be assigned Terms and Conditions.</span></span>
4. <span data-ttu-id="7be3d-137">Klicken Sie auf dem Blatt **Zugewiesene Gruppen** auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="7be3d-137">In the **Assigned Groups** blade, click **Save**.</span></span>  <span data-ttu-id="7be3d-138">Die Geschäftsbedingungen werden jetzt den Benutzern in den ausgewählten Gruppen zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="7be3d-138">The terms and conditions are now assigned to users in the selected groups.</span></span> <span data-ttu-id="7be3d-139">Benutzer werden beim nächsten Zugriff auf das Unternehmensportal zur Annahme der Geschäftsbedingungen aufgefordert.</span><span class="sxs-lookup"><span data-stu-id="7be3d-139">Users will be prompted to accept terms the next time they access the company portal.</span></span> <span data-ttu-id="7be3d-140">Die Geschäftsbedingungen müssen nur einmal angenommen werden.</span><span class="sxs-lookup"><span data-stu-id="7be3d-140">The terms and conditions only need to be accepted once.</span></span> <span data-ttu-id="7be3d-141">Benutzer mit mehreren Geräten müssen sie nicht auf jedem Gerät annehmen.</span><span class="sxs-lookup"><span data-stu-id="7be3d-141">Users with multiple devices don't have to accept on each device.</span></span>


## <a name="monitor-terms-and-conditions"></a><span data-ttu-id="7be3d-142">Überwachen der Geschäftsbedingungen</span><span class="sxs-lookup"><span data-stu-id="7be3d-142">Monitor terms and conditions</span></span>

1. <span data-ttu-id="7be3d-143">Wählen Sie im Azure-Portal **Weitere Dienste** > **Überwachung und Verwaltung** > **Intune** aus.</span><span class="sxs-lookup"><span data-stu-id="7be3d-143">In the Azure portal, choose **More Services** > **Monitoring + Management** > **Intune**.</span></span> <span data-ttu-id="7be3d-144">Wählen Sie auf dem Blatt „Intune“ die Option **Geräteregistrierung** und dann **Geschäftsbedingungen** aus.</span><span class="sxs-lookup"><span data-stu-id="7be3d-144">On the Intune blade, choose **Device enrollment**, and then choose **Terms and Conditions**.</span></span>
2. <span data-ttu-id="7be3d-145">Wählen Sie in der Liste der Geschäftsbedingungen die Bedingungen aus, für die Sie die Annahme anzeigen möchten, und wählen Sie dann **Annahmestatus** aus.</span><span class="sxs-lookup"><span data-stu-id="7be3d-145">In the list of terms and conditions, select the terms you want to view acceptance for, and then select **Acceptance Statuses**.</span></span>

## <a name="work-with-multiple-versions-of-terms-and-conditions"></a><span data-ttu-id="7be3d-146">Arbeiten mit mehreren Versionen der Nutzungsbedingungen</span><span class="sxs-lookup"><span data-stu-id="7be3d-146">Work with multiple versions of terms and conditions</span></span>
<span data-ttu-id="7be3d-147">Sie können Ihre Geschäftsbedingungen bearbeiten und ihre Versionen verwalten.</span><span class="sxs-lookup"><span data-stu-id="7be3d-147">You can edit your terms and conditions and manage their versions.</span></span> <span data-ttu-id="7be3d-148">Es wird empfohlen, dass Sie jedes Mal die Versionsnummer erhöhen und die Zustimmung zu den Geschäftsbedingungen anfordern, wenn Sie wichtige Änderungen an den Geschäftsbedingungen vornehmen.</span><span class="sxs-lookup"><span data-stu-id="7be3d-148">We recommend that you increase the version number and require acceptance any time you make significant changes to your terms and conditions.</span></span> <span data-ttu-id="7be3d-149">Behalten Sie die aktuelle Versionsnummer bei, wenn Sie z. B. Tippfehler korrigieren oder die Formatierung ändern.</span><span class="sxs-lookup"><span data-stu-id="7be3d-149">Keep the current version number if, for example, you are fixing typos or changing formatting.</span></span>

1. <span data-ttu-id="7be3d-150">Wählen Sie im Azure-Portal **Weitere Dienste** > **Überwachung und Verwaltung** > **Intune** aus.</span><span class="sxs-lookup"><span data-stu-id="7be3d-150">In the Azure portal, choose **More Services** > **Monitoring + Management** > **Intune**.</span></span>

2. <span data-ttu-id="7be3d-151">Wählen Sie auf dem Blatt „Intune“ die Option **Geräteregistrierung**, **Geschäftsbedingungen** und dann die Geschäftsbedingungen aus, die Sie ändern möchten. Anschließend wählen Sie die Option **Eigenschaften** aus.</span><span class="sxs-lookup"><span data-stu-id="7be3d-151">On the Intune blade, choose **Device enrollment**,  choose **Terms and Conditions**, select the terms and conditions you want to modify, and then select **Properties**.</span></span>

4. <span data-ttu-id="7be3d-152">Wählen Sie auf dem Blatt **Eigenschaften** die Option **Geschäftsbedingungen** aus, und ändern Sie bei Bedarf **Titel**, **Zusammenfassung der Nutzungsbedingungen** und **Geschäftsbedingungen**.</span><span class="sxs-lookup"><span data-stu-id="7be3d-152">On the **Properties** blade, select **Terms and Conditions** and then modify the **Title**, **Summary of Terms**, and **Terms and Conditions** as needed.</span></span> <span data-ttu-id="7be3d-153">Wenn es die von Ihnen vorgenommenen Änderungen für Benutzer erforderlich machen, die neuen Bedingungen erneut anzunehmen, klicken Sie auf **Fordert eine erneute Annahme durch die Benutzer an und erhöht die Versionsnummer auf**.</span><span class="sxs-lookup"><span data-stu-id="7be3d-153">If the changes you made make it necessary for users to reaccept the new terms, click **Require users to re-accept, and increment the version number to**</span></span>

4.  <span data-ttu-id="7be3d-154">Wählen Sie **OK** und dann **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="7be3d-154">Select **OK** and then select **Save**.</span></span>

<span data-ttu-id="7be3d-155">Benutzer müssen die aktualisierten Geschäftsbedingungen nur einmal annehmen.</span><span class="sxs-lookup"><span data-stu-id="7be3d-155">Users only have to accept updated terms and conditions once.</span></span> <span data-ttu-id="7be3d-156">Benutzer mit mehreren Geräten müssen die Geschäftsbedingungen nicht auf jedem Gerät annehmen.</span><span class="sxs-lookup"><span data-stu-id="7be3d-156">Users with multiple devices don't have to accept terms and conditions on each device.</span></span>
