---
title: "Planen von Benutzer- und Gerätegruppen"
description: "Planen Sie Gruppen, um Ihren organisatorischen Bedürfnissen gerecht zu werden."
keywords: 
author: sanchusa
manager: angrobe
ms.date: 10/25/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f11bb256-1094-4f7e-b826-1314c57f3356
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: lpatha
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 679399f306f3837a010cc01799c7567c1e5b5b39
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2018
---
# <a name="plan-your-user-and-device-groups"></a><span data-ttu-id="23957-103">Planen von Benutzer- und Gerätegruppen</span><span class="sxs-lookup"><span data-stu-id="23957-103">Plan your user and device groups</span></span>

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="23957-104">Mit Gruppen erhalten Sie in Intune maximale Flexibilität beim Verwalten Ihrer Geräte und Benutzer.</span><span class="sxs-lookup"><span data-stu-id="23957-104">Groups in Intune give you great flexibility when you're managing your devices and users.</span></span> <span data-ttu-id="23957-105">Sie können Gruppen anhand der folgenden Kriterien einrichten, um den Anforderungen Ihrer Organisation zu entsprechen:</span><span class="sxs-lookup"><span data-stu-id="23957-105">You can set up groups to suit your organizational needs according to:</span></span>

- <span data-ttu-id="23957-106">Geografischer Standort</span><span class="sxs-lookup"><span data-stu-id="23957-106">geographic location</span></span>
- <span data-ttu-id="23957-107">Abteilung</span><span class="sxs-lookup"><span data-stu-id="23957-107">department</span></span>
- <span data-ttu-id="23957-108">Hardwareeigenschaften</span><span class="sxs-lookup"><span data-stu-id="23957-108">hardware characteristics</span></span>
- <span data-ttu-id="23957-109">Betriebssystem</span><span class="sxs-lookup"><span data-stu-id="23957-109">operating system</span></span>
- <span data-ttu-id="23957-110">Unternehmenseigenes Gerät oder im Besitz des Benutzers</span><span class="sxs-lookup"><span data-stu-id="23957-110">whether the device is user-owned or company-owned</span></span>


## <a name="how-intune-groups-work"></a><span data-ttu-id="23957-111">Funktionsweise von Intune-Gruppen</span><span class="sxs-lookup"><span data-stu-id="23957-111">How Intune groups work</span></span>


<span data-ttu-id="23957-112">Die Standardansicht des Knotens **Gruppen** in der Intune-Verwaltungskonsole:</span><span class="sxs-lookup"><span data-stu-id="23957-112">This is the default view of the **Groups** node in the Intune admin console:</span></span>

![Screenshot der Standardansicht des Knotens „Gruppen“ in der Intune-Konsole](../media/Intune_Planning_Groups_Default_small.png)

<span data-ttu-id="23957-114">Richtlinien werden für Gruppen bereitgestellt, daher ist die Gruppenhierarchie eine der wichtigsten Überlegungen zum Entwurf.</span><span class="sxs-lookup"><span data-stu-id="23957-114">Policies are deployed to groups, so group hierarchy is one of your key design considerations.</span></span> <span data-ttu-id="23957-115">Sie sollten wissen, dass Sie die übergeordnete Gruppe einer Gruppe nicht ändern können, nachdem Sie die Gruppe erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="23957-115">It's important to know that you cannot change a group’s parent group after you've created the group.</span></span> <span data-ttu-id="23957-116">Sobald Sie beginnen, den Intune-Dienst zu verwenden, ist es äußerst wichtig, wie Sie Ihre Gruppen entwerfen.</span><span class="sxs-lookup"><span data-stu-id="23957-116">How you design your groups is critically important from the moment you start using the Intune service.</span></span> <span data-ttu-id="23957-117">Einige empfohlene Methoden für den Entwurf einer Gruppenhierarchie auf Basis der Anforderungen Ihres Unternehmens werden hier beschrieben.</span><span class="sxs-lookup"><span data-stu-id="23957-117">Some recommended practices for designing a group hierarchy based on your organizational needs are described here.</span></span>

## <a name="group-membership-rules"></a><span data-ttu-id="23957-118">Regeln für Gruppenmitgliedschaft</span><span class="sxs-lookup"><span data-stu-id="23957-118">Group membership rules</span></span>

- <span data-ttu-id="23957-119">Eine Gruppe kann entweder Benutzer oder Geräte enthalten, aber nicht beides.</span><span class="sxs-lookup"><span data-stu-id="23957-119">A group can contain either users or devices, but not both.</span></span>

    * <span data-ttu-id="23957-120">**Gerätegruppen**.</span><span class="sxs-lookup"><span data-stu-id="23957-120">**Device groups**.</span></span> <span data-ttu-id="23957-121">Hierbei sind sowohl Computer als auch mobile Geräte enthalten.</span><span class="sxs-lookup"><span data-stu-id="23957-121">This includes computers and mobile devices.</span></span> <span data-ttu-id="23957-122">Bevor Sie einer Gruppe einen Computer hinzufügen können, muss dieser registriert werden.</span><span class="sxs-lookup"><span data-stu-id="23957-122">Before you can add a computer to a group, it must be enrolled.</span></span> <span data-ttu-id="23957-123">Bevor Sie einer Gruppe ein mobiles Gerät hinzufügen können, muss Ihre Umgebung für die Unterstützung mobiler Geräte konfiguriert werden, und die Geräte müssen entweder registriert oder über Exchange ActiveSync ermittelt werden.</span><span class="sxs-lookup"><span data-stu-id="23957-123">Before you can add a mobile device to a group, your environment must be configured to support mobile devices, and the device must be enrolled or discovered in Exchange ActiveSync.</span></span>

    * <span data-ttu-id="23957-124">**Benutzergruppen**.</span><span class="sxs-lookup"><span data-stu-id="23957-124">**User groups**.</span></span> <span data-ttu-id="23957-125">Eine Gruppe kann Benutzer aus Sicherheitsgruppen aufweisen.</span><span class="sxs-lookup"><span data-stu-id="23957-125">A group can have users from security groups.</span></span> <span data-ttu-id="23957-126">Sicherheitsgruppen sind mit Ihrer Active Directory-Instanz synchronisiert.</span><span class="sxs-lookup"><span data-stu-id="23957-126">Security groups sync with your instance of Active Directory.</span></span> <span data-ttu-id="23957-127">Wenn Sie keine Active Directory-Synchronisierung verwenden, können Sie diese Gruppen manuell erstellen.</span><span class="sxs-lookup"><span data-stu-id="23957-127">If you do not sync with Active Directory, you can manually create these groups.</span></span>

- <span data-ttu-id="23957-128">Ein Gerät oder ein Benutzer kann zu mehr als einer Gruppe gehören.</span><span class="sxs-lookup"><span data-stu-id="23957-128">A device or a user can belong to more than one group.</span></span>

- <span data-ttu-id="23957-129">Mitglieder können in einer Gruppe auf Basis folgender Mitgliedschaftsregeln ein- und ausgeschlossen werden:</span><span class="sxs-lookup"><span data-stu-id="23957-129">A group can include and exclude members based on the following membership rules:</span></span>

    * <span data-ttu-id="23957-130">**Mitgliedschaftskriterien**.</span><span class="sxs-lookup"><span data-stu-id="23957-130">**Criteria Membership**.</span></span> <span data-ttu-id="23957-131">Hierbei handelt es sich um dynamische Regeln, die von Intune zum Ein- bzw. Ausschließen von Mitgliedern ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="23957-131">These are dynamic rules that Intune runs to include or exclude members.</span></span> <span data-ttu-id="23957-132">Von diesen Kriterien werden Sicherheitsgruppen und andere Informationen verwendet, die mit Ihrer lokalen Active Directory-Instanz synchronisiert werden.</span><span class="sxs-lookup"><span data-stu-id="23957-132">These criteria use security groups and other information synced with your local instance of Active Directory.</span></span> <span data-ttu-id="23957-133">Erfolgen Änderungen an der Sicherheitsgruppe oder den Daten, ändert beim Synchronisieren mit Active Directory auch die Gruppenmitgliedschaft.</span><span class="sxs-lookup"><span data-stu-id="23957-133">When the security group or data changes, the group membership changes when you sync with Active Directory.</span></span>

    * <span data-ttu-id="23957-134">**Direkte Mitgliedschaft**.</span><span class="sxs-lookup"><span data-stu-id="23957-134">**Direct Membership**.</span></span> <span data-ttu-id="23957-135">Hierbei handelt es sich um statische Regeln, durch die Mitglieder explizit hinzugefügt oder ausgeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="23957-135">These are static rules that explicitly add or exclude members.</span></span> <span data-ttu-id="23957-136">Die Mitgliederliste ist statisch.</span><span class="sxs-lookup"><span data-stu-id="23957-136">The membership list is static.</span></span>

-   <span data-ttu-id="23957-137">Der Active Directory-Domänendienst (AD DS) ist nicht erforderlich, wenn Sie Benutzergruppen oder Gerätegruppen erstellen, die Benutzer oder Computer einschließen.</span><span class="sxs-lookup"><span data-stu-id="23957-137">Active Directory Domain Services (AD DS) is not required when you create user groups or device groups that include users or computers.</span></span> <span data-ttu-id="23957-138">Damit mobile Geräte zu Gerätegruppen gehören können, muss Ihre Umgebung jedoch so konfiguriert sein, dass mobile Geräte unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="23957-138">But, for device groups to include mobile devices, your environment must be configured to support mobile devices.</span></span>

    <span data-ttu-id="23957-139">Zusätzlich müssen die Geräte ermittelt und in Intune hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="23957-139">Additionally, the devices must be discovered and added to Intune.</span></span>

## <a name="group-relationship-rules"></a><span data-ttu-id="23957-140">Regeln für Gruppenbeziehungen</span><span class="sxs-lookup"><span data-stu-id="23957-140">Group relationship rules</span></span>

- <span data-ttu-id="23957-141">Jede Gruppe, die Sie erstellen, muss eine übergeordnete Gruppe haben.</span><span class="sxs-lookup"><span data-stu-id="23957-141">Each group you create must have a parent group.</span></span> <span data-ttu-id="23957-142">Sie können die übergeordnete Gruppe einer Gruppe nicht ändern, nachdem Sie die Gruppe erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="23957-142">You cannot change a group’s parent group after you've created the group.</span></span>

- <span data-ttu-id="23957-143">Beim Hinzufügen von Benutzern oder Geräten zu einer untergeordneten Gruppe gilt Folgendes:</span><span class="sxs-lookup"><span data-stu-id="23957-143">When you add users or devices to a child group:</span></span>

    * <span data-ttu-id="23957-144">Die untergeordnete Gruppe stellt immer eine Teilmenge der übergeordneten Gruppe dar.</span><span class="sxs-lookup"><span data-stu-id="23957-144">The child group is always a subset of the parent group.</span></span>

    * <span data-ttu-id="23957-145">Wenn Sie einer untergeordneten Gruppe Mitglieder hinzufügen, werden diese automatisch auch der entsprechenden übergeordneten Gruppe hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="23957-145">New members you add to a child group are automatically added to that group’s parent group.</span></span>

    * <span data-ttu-id="23957-146">Mitglieder, die von der übergeordneten Gruppe ausgeschlossen wurden, können der untergeordneten Gruppe nicht hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="23957-146">You cannot add a member to a child group when that member is excluded from the parent group.</span></span>

- <span data-ttu-id="23957-147">Die verfügbare Mitgliedschaft einer untergeordneten Gruppe wird durch die Mitgliedschaft der übergeordneten Gruppe definiert.</span><span class="sxs-lookup"><span data-stu-id="23957-147">The membership of a parent group defines the available membership for the child group.</span></span>

- <span data-ttu-id="23957-148">Beim Löschen einer übergeordneten Gruppe werden alle untergeordneten Gruppen gelöscht.</span><span class="sxs-lookup"><span data-stu-id="23957-148">When you delete a parent group, all child groups are deleted.</span></span>

- <span data-ttu-id="23957-149">Es ist möglich, Inhalt und Richtlinien für eine übergeordnete Gruppe bereitzustellen, aber die Bereitstellung für untergeordnete Gruppen auszuschließen.</span><span class="sxs-lookup"><span data-stu-id="23957-149">You can deploy content and policies to a parent group but exclude the deployment to child groups.</span></span>

- <span data-ttu-id="23957-150">Sie können bestimmte Benutzer oder Geräte einer untergeordneten Gruppe hinzufügen, wenn der Benutzer oder das Gerät noch kein Mitglied der übergeordneten Gruppe ist.</span><span class="sxs-lookup"><span data-stu-id="23957-150">You can add a specific user or device to a child group if the user or device is not already a member of the parent group.</span></span> <span data-ttu-id="23957-151">Wenn Sie dies tun, wird das neue Mitglied der untergeordneten Gruppe der übergeordneten Gruppe hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="23957-151">If you do this, the new member of the child group will be added to the parent group.</span></span>

    <span data-ttu-id="23957-152">Sie können jedoch keine Mitglieder einer untergeordneten Gruppe hinzufügen, wenn das Mitglied aus der übergeordneten Gruppe ausgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="23957-152">However, you cannot add a member to a child group if the member is excluded from the parent group.</span></span>

- <span data-ttu-id="23957-153">Gruppenmitgliedschaften sind rekursiv.</span><span class="sxs-lookup"><span data-stu-id="23957-153">Group membership is recursive.</span></span> <span data-ttu-id="23957-154">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="23957-154">For example:</span></span>

    * <span data-ttu-id="23957-155">**Pat** ist nur bei einer Gruppe Mitglied: bei der Sicherheitsgruppe **Laptopbenutzer** .</span><span class="sxs-lookup"><span data-stu-id="23957-155">**Pat** is a member of only one group, the **Laptop Users** security group.</span></span>

    * <span data-ttu-id="23957-156">Die Gruppe **Laptopbenutzer** ist Mitglied der Sicherheitsgruppe **Genehmigte Benutzer** .</span><span class="sxs-lookup"><span data-stu-id="23957-156">The **Laptop Users** group is a member of the **Approved Users** security group.</span></span>

    * <span data-ttu-id="23957-157">Sie erstellen in Intune eine Gruppe, von der eine dynamische Mitgliedschaftsabfrage ausgeführt wird, die die Mitglieder der Gruppe **Genehmigte Benutzer** einschließt.</span><span class="sxs-lookup"><span data-stu-id="23957-157">You create a group in Intune that uses a dynamic membership query that includes the members of the **Approved Users** group.</span></span> <span data-ttu-id="23957-158">Als Ergebnis enthält die Intune-Benutzergruppe **Pat**.</span><span class="sxs-lookup"><span data-stu-id="23957-158">The result is that your Intune user group includes **Pat**.</span></span>

> [!TIP]
> <span data-ttu-id="23957-159">Überlegen Sie beim Erstellen von Gruppen, wie Richtlinien angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="23957-159">When you create groups, think about how you will apply policy.</span></span> <span data-ttu-id="23957-160">Sie verfügen möglicherweise z.B. über Richtlinien, die für Gerätebetriebssysteme oder für verschiedene Rollen oder Organisationseinheiten gelten, die Sie schon in Ihrem Active Directory-Dienst definiert haben.</span><span class="sxs-lookup"><span data-stu-id="23957-160">For example, you might have policies that are specific to device operating systems, or policies that are specific to different roles or organizational units you've already defined in your Active Directory service.</span></span> <span data-ttu-id="23957-161">Einige Administratoren finden es sinnvoll, Gerätegruppen zu erstellen, die für iOS, Android und Windows spezifisch sind.</span><span class="sxs-lookup"><span data-stu-id="23957-161">Some admins find it useful to create device groups that are specific to iOS, Android, and Windows.</span></span> <span data-ttu-id="23957-162">Dies erfolgt zusätzlich zum Erstellen von Benutzergruppen für jede Rolle im Unternehmen.</span><span class="sxs-lookup"><span data-stu-id="23957-162">This is in addition to creating user groups for each organizational role.</span></span>

<!--- should we just link to a policies topic at this point and remove this? Ask Rob
 You'll probably want to create a default policy that applies to all groups and devices, to establish the basic compliance requirements of your organization. Then, you create more specific policies for the broadest categories of users and devices, for example, email policies for each of the device operating systems.

 Be careful when you name your policies, so that you can easily identify them later. For example, a good, descriptive policy name is **WP Email Policy for Entire Company**.

 Each time you create a restrictive policy, you'll want to communicate it to your users. After you create the more general groups and policies, pay attention to how you create smaller groups so that you can reduce unnecessary communication.--->

## <a name="built-in-groups"></a><span data-ttu-id="23957-163">Integrierte Gruppen</span><span class="sxs-lookup"><span data-stu-id="23957-163">Built-in groups</span></span>
<span data-ttu-id="23957-164">In Intune sind neun integrierte Gruppen verfügbar, die Sie weder bearbeiten noch löschen können: <!--maybe a screen shot would be best?--></span><span class="sxs-lookup"><span data-stu-id="23957-164">Intune has nine built-in groups that you cannot edit or delete: <!--maybe a screen shot would be best?--></span></span>

-   <span data-ttu-id="23957-165">**Allen Benutzern**</span><span class="sxs-lookup"><span data-stu-id="23957-165">**All Users**</span></span>
    -   <span data-ttu-id="23957-166">Nicht gruppierte Benutzer</span><span class="sxs-lookup"><span data-stu-id="23957-166">Ungrouped Users</span></span>
-   <span data-ttu-id="23957-167">**Alle Geräte**</span><span class="sxs-lookup"><span data-stu-id="23957-167">**All Devices**</span></span>
    -   <span data-ttu-id="23957-168">Alle Computer</span><span class="sxs-lookup"><span data-stu-id="23957-168">All Computers</span></span>
    -   <span data-ttu-id="23957-169">Alle mobilen Geräte</span><span class="sxs-lookup"><span data-stu-id="23957-169">All Mobile Devices</span></span>
        -   <span data-ttu-id="23957-170">Alle direkt verwalteten Geräte</span><span class="sxs-lookup"><span data-stu-id="23957-170">All Direct Managed Devices</span></span>
        -   <span data-ttu-id="23957-171">Alle mit Exchange ActiveSync verwalteten Geräte</span><span class="sxs-lookup"><span data-stu-id="23957-171">All Exchange ActiveSync Managed Devices</span></span>
    -   <span data-ttu-id="23957-172">Alle firmeneigenen Geräte</span><span class="sxs-lookup"><span data-stu-id="23957-172">All Corporate-owned Devices</span></span>
    -   <span data-ttu-id="23957-173">Nicht gruppierte Geräte</span><span class="sxs-lookup"><span data-stu-id="23957-173">Ungrouped Devices</span></span>

> [!NOTE]
> <span data-ttu-id="23957-174">Das Motto lautet: *möglichst einfach*.</span><span class="sxs-lookup"><span data-stu-id="23957-174">Let your motto be: *keep it simple*.</span></span> <span data-ttu-id="23957-175">Wenn Ihr Unternehmen keine speziellen Anforderungen (wie z.B. die in folgenden Abschnitten beschriebenen) stellt, können Sie einen schlichten Ansatz wählen und die Standardgruppenstruktur und -richtlinien übernehmen.</span><span class="sxs-lookup"><span data-stu-id="23957-175">If your organization does not have specific needs like those described in the following sections, keep it simple and go with the default group structure and policies.</span></span> <span data-ttu-id="23957-176">Dadurch kann der Dienst auf lange Sicht besser verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="23957-176">This will make the service more manageable in the long term.</span></span> <span data-ttu-id="23957-177">Die Wartung vereinfacht sich, wenn Sie Ihre Benutzer einheitlich behandeln können.</span><span class="sxs-lookup"><span data-stu-id="23957-177">Maintenance will be easier if you can treat your users uniformly.</span></span> <span data-ttu-id="23957-178">Kleine Unterschiede in den Gruppen führen dazu, dass Sie weniger Richtlinien zu verwalten haben.</span><span class="sxs-lookup"><span data-stu-id="23957-178">With little differentiation by group, you'll have fewer policies to maintain.</span></span>


### <a name="all-users-and-devices-in-your-organization"></a><span data-ttu-id="23957-179">Alle Benutzer und Geräte in Ihrem Unternehmen</span><span class="sxs-lookup"><span data-stu-id="23957-179">All users and devices in your organization</span></span>
<span data-ttu-id="23957-180">Definieren Sie eine übergeordnete Gruppe für alle Benutzer und Geräte in Ihrem Unternehmen.</span><span class="sxs-lookup"><span data-stu-id="23957-180">Define a parent group for all users and devices in your organization.</span></span> <span data-ttu-id="23957-181">Sie verfügen wahrscheinlich über Richtlinien, die für alle gelten.</span><span class="sxs-lookup"><span data-stu-id="23957-181">You are likely to have policies that will apply to all.</span></span> <span data-ttu-id="23957-182">Zu diesem Zweck können Sie die Intune-Standardgruppen **Alle Benutzer** und **Alle Geräte** verwenden.</span><span class="sxs-lookup"><span data-stu-id="23957-182">You can use the Intune default **All Users** and **All devices** groups for this purpose.</span></span> <span data-ttu-id="23957-183">Untergruppen, die Geräte nach speziellen Eigenschaften organisieren, z.B. eine BYOD-Gruppe (Bring Your Own Device) und eine Gruppe für unternehmenseigene Geräte (Corporate-Owned, CO), können den übergeordneten Gruppen **Alle Benutzer** und **Alle Geräte** untergeordnet sein.</span><span class="sxs-lookup"><span data-stu-id="23957-183">Sub-groups that organize devices by specifics, like a group for bring your own device (BYOD) and one for corporate-owned (CO) devices, can be child groups of the **All Users** and **All devices** parent groups.</span></span>

## <a name="customize-groups-for-your-organization"></a><span data-ttu-id="23957-184">Anpassen von Gruppen für Ihre Organisation</span><span class="sxs-lookup"><span data-stu-id="23957-184">Customize groups for your organization</span></span>

### <a name="byod-and-corporate-owned-devices"></a><span data-ttu-id="23957-185">BYOD- und firmeneigene Geräte</span><span class="sxs-lookup"><span data-stu-id="23957-185">BYOD and corporate-owned devices</span></span>
<span data-ttu-id="23957-186">Wenn Ihre Organisation Mitarbeitern die Nutzung eigener Geräte gestattet, unternehmenseigene Geräte bereitstellt oder eine Kombination aus beidem zulässt, empfiehlt es sich, separate Richtlinien für diese beiden Gerätekategorien anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="23957-186">If your organization allows employees to use their own devices, provides company-owned devices, or has a combination of both, we recommend that you apply separate policies for these categories of devices.</span></span>

<span data-ttu-id="23957-187">Im Fall von BYOD oder eines kombinierten Ansatzes achten Sie darauf, dass Sie Ihre Richtlinien so planen, dass die vor Ort geltenden Datenschutzbestimmungen nicht verletzt werden.</span><span class="sxs-lookup"><span data-stu-id="23957-187">In the case of BYOD or a mix, be careful to plan policies that do not infringe on local privacy regulations.</span></span> <span data-ttu-id="23957-188">Erstellen Sie eine übergeordnete Gruppe für alle Benutzer, die ihre eigenen Geräte einsetzen.</span><span class="sxs-lookup"><span data-stu-id="23957-188">Create a parent group for all users who will be bringing their own devices.</span></span> <span data-ttu-id="23957-189">Sie können diese Gruppe dann dazu verwenden, Richtlinien anzuwenden, die für alle Benutzer in dieser Kategorie gelten.</span><span class="sxs-lookup"><span data-stu-id="23957-189">You can use this group to apply policies that are applicable to all users in this category.</span></span>

![Erstellen einer übergeordneten BYOD-Gruppe](../media/Intune_Planning_Groups_BYOD_small.png)

<span data-ttu-id="23957-191">Ebenso können Sie eine Gruppe für die Benutzer eines CO-Geräts in Ihrer Organisation erstellen:</span><span class="sxs-lookup"><span data-stu-id="23957-191">Similarly, you can create a group for the CO device users in your organization:</span></span>

![Gleichgeordnete Benutzergruppen für BYOD- und CO-Geräte](../media/Intune_Planning_Groups_BYOD_Hierachy_View_small.png)

<!---START HERE--->

### <a name="groups-for-geographic-regions"></a><span data-ttu-id="23957-193">Gruppen für geografische Regionen</span><span class="sxs-lookup"><span data-stu-id="23957-193">Groups for geographic regions</span></span>
<span data-ttu-id="23957-194">Wenn Ihre Organisation Richtlinien für bestimmte Regionen benötigt, können Sie Gruppen basierend auf der geografischen Region erstellen.</span><span class="sxs-lookup"><span data-stu-id="23957-194">If your organization needs policies for specific regions, you can create groups based on geographic region.</span></span> <span data-ttu-id="23957-195">Sie können diese auf Grundlage regionaler Gruppen anlegen, die Sie möglicherweise bereits in Ihrer Active Directory-Instanz erstellt haben, und Sie mit Azure Active Directory synchronisieren.</span><span class="sxs-lookup"><span data-stu-id="23957-195">You can base them on regional groups that you might have already created in your instance of Active Directory, and sync them with your Azure Active Directory service.</span></span> <span data-ttu-id="23957-196">Sie können regionale Gruppen auch direkt in Azure Active Directory erstellen.</span><span class="sxs-lookup"><span data-stu-id="23957-196">You also can create regional groups directly in Azure Active Directory.</span></span>

<span data-ttu-id="23957-197">Die nächsten Screenshots zeigen Ihnen, wie Sie Intune-Gruppen basierend auf Gruppen erstellen, die mit Ihrer lokalen Active Directory-Instanz synchronisiert sind.</span><span class="sxs-lookup"><span data-stu-id="23957-197">The next screenshots show you how to create Intune groups based on groups synced with your on-premises Active Directory instance.</span></span> <span data-ttu-id="23957-198">In diesen Beispielen wird vorausgesetzt, dass Sie über eine Active Directory-Sicherheitsgruppe namens **US Users Group** verfügen.</span><span class="sxs-lookup"><span data-stu-id="23957-198">These examples assume that you have an Active Directory security group called **US Users Group**.</span></span>

<span data-ttu-id="23957-199">Stellen Sie zunächst allgemeine Informationen bereit.</span><span class="sxs-lookup"><span data-stu-id="23957-199">First, provide general information.</span></span>

![Screenshot des Bereichs „Gruppe bearbeiten“](../media/Intune_Planning_Groups_AD_General_small.png)

<span data-ttu-id="23957-201">Wählen Sie unter den **Mitgliedschaftskriterien** die Gruppe **US Users Group**, die mit Active Directory synchronisiert wurde, als Sicherheitsgruppe aus, die unter den Mitgliedschaftsregeln verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="23957-201">Under **Membership criteria**, select **US Users Group**, synced with Active Directory, as the security group to use under membership rules.</span></span>

![Screenshot des Dialogfelds „Gruppe bearbeiten“](../media/Intune_Planning_Groups_AD_Criteria_small.png)

<span data-ttu-id="23957-203">Überprüfen Sie Ihre Eingaben, und wählen Sie anschließend **Fertig stellen** aus, um die Gruppe zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="23957-203">Review your entries, and then choose **Finish** to create the group.</span></span>

![Screenshot des Dialogfelds „Gruppe bearbeiten“](../media/Intune_Planning_Groups_AD_Summary_small.png)

<span data-ttu-id="23957-205">In unserem Beispiel haben wir auch eine Gruppe namens **MEA**, die den Nahen Osten und Asien (MEA) umfasst.</span><span class="sxs-lookup"><span data-stu-id="23957-205">In our example, we’ve also created a group called **MEA**, for the Middle East and Asia.</span></span>

> [!NOTE]
> <span data-ttu-id="23957-206">Wenn die Gruppenmitgliedschaft nicht auf Basis der Mitgliedschaft in Sicherheitsgruppen entschieden wird, stellen Sie sicher, dass Sie Gruppenmitgliedern Intune-Lizenzen zugewiesen haben.</span><span class="sxs-lookup"><span data-stu-id="23957-206">If group membership is not populated based on security group membership, make sure that you have assigned Intune licenses to group members.</span></span>

### <a name="groups-for-specific-hardware"></a><span data-ttu-id="23957-207">Gruppen für bestimmte Hardware</span><span class="sxs-lookup"><span data-stu-id="23957-207">Groups for specific hardware</span></span>
<span data-ttu-id="23957-208">Wenn Ihre Organisation Richtlinien benötigt, die auf bestimmte Hardwaretypen angewendet werden, können Sie die Gruppen auf Basis dieser Anforderung erstellen.</span><span class="sxs-lookup"><span data-stu-id="23957-208">If your organization requires policies that apply to specific hardware types, you can create groups based on this requirement.</span></span> <span data-ttu-id="23957-209">Sie können die Richtlinien basierend auf bestimmten Gruppen anlegen, die Sie bereits in Ihrer lokalen Active Directory-Instanz erstellt haben, und Sie anschließend mit Azure Active Directory synchronisieren.</span><span class="sxs-lookup"><span data-stu-id="23957-209">You can base the policies on specific groups that you have already created in your on-premises instance of Active Directory, and then sync them with Azure Active Directory.</span></span> <span data-ttu-id="23957-210">Sie können Gruppen auch direkt in Azure Active Directory erstellen.</span><span class="sxs-lookup"><span data-stu-id="23957-210">You also can create groups directly in Azure Active Directory.</span></span> <span data-ttu-id="23957-211">In diesem Beispiel verwenden wir **US Users Group** als übergeordnete Gruppe für die Gruppe der **Laptopbenutzer**.</span><span class="sxs-lookup"><span data-stu-id="23957-211">In this example, we use **US Users Group** as the parent group for the **Laptop Users** group.</span></span>

![Dialogfeld „Sicherheitsgruppe auswählen“](../media/Intune_Planning_Groups_Laptop_small.png)

<span data-ttu-id="23957-213">An diesem Punkt sollte die Hierarchie Ihrer Gruppe ähnlich wie der nächste Screenshot aussehen.</span><span class="sxs-lookup"><span data-stu-id="23957-213">At this point, your group's hierarchy should look similar to the next screenshot.</span></span> <span data-ttu-id="23957-214">Sie können sehen, dass jetzt in der Intune-Gruppe der **Laptopbenutzer** entsprechende Mitglieder enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="23957-214">You can see that there are now members in the Intune group **Laptop Users**.</span></span> <span data-ttu-id="23957-215">Alle auf diese Gruppe angewendeten Richtlinien werden auf BYOD-Laptopbenutzer aus der Region „USA“ angewendet.</span><span class="sxs-lookup"><span data-stu-id="23957-215">Any policies applied to this group will be applied to BYOD laptop users from the U.S. region.</span></span>

![Anzeigen der Gruppe „Laptopbenutzer“](../media/Intune_Planning_Groups_Laptop_Hierarchy_small.png)

### <a name="groups-for-specific-operating-systems"></a><span data-ttu-id="23957-217">Gruppen für bestimmte Betriebssysteme</span><span class="sxs-lookup"><span data-stu-id="23957-217">Groups for specific operating systems</span></span>
<span data-ttu-id="23957-218">Wenn Ihr Unternehmen Richtlinien benötigt, die auf bestimmte Betriebssysteme wie Android, iOS oder Windows angewendet werden, können Sie die Gruppen auf Basis dieser Anforderung erstellen.</span><span class="sxs-lookup"><span data-stu-id="23957-218">If your organization requires policies that apply to specific operating systems like Android, iOS, or Windows, you can create groups based on this requirement.</span></span> <span data-ttu-id="23957-219">Wie in früheren Beispielen gezeigt, können Sie diese auf Basis betriebssystemspezifischer Gruppen anlegen, die Sie bereits in Ihrer lokalen Active Directory-Instanz erstellt haben, und Sie mit Azure Active Directory synchronisieren.</span><span class="sxs-lookup"><span data-stu-id="23957-219">As in earlier examples, you can base them on OS-specific groups that you have already created in your on-premises instance of Active Directory, and sync them with Azure Active Directory.</span></span> <span data-ttu-id="23957-220">Sie können Sie auch direkt in Ihrer Azure Active Directory-Instanz erstellen.</span><span class="sxs-lookup"><span data-stu-id="23957-220">You also can create them directly in your instance of Azure Active Directory.</span></span>

<span data-ttu-id="23957-221">Mithilfe der in früheren Beispielen vorgestellten Methode können Sie Gruppen erstellen, die auf Benutzern <!--devices?--> basieren, die bestimmte Betriebssystemplattformen verwenden.</span><span class="sxs-lookup"><span data-stu-id="23957-221">By using the same method from earlier examples, you can create groups based on users <!--devices?--> who use specific operating system platforms.</span></span>

> [!NOTE]
> <span data-ttu-id="23957-222">Wenn Sie über Benutzer verfügen, die mehrere mobile Plattformen/Betriebssysteme verwenden, und Sie keine automatisierte Möglichkeit zum Kategorisieren von Benutzern als Android-, iOS- oder Windows-Benutzer haben, sollten Sie die Anwendung der Richtlinien auf Geräteebene erwägen.</span><span class="sxs-lookup"><span data-stu-id="23957-222">If you have users who use multiple mobile platforms or operating systems and you do not have an automated way to categorize users as Android users, iOS users, or Windows users, consider applying policies at the device level.</span></span> <span data-ttu-id="23957-223">Dadurch erhalten Sie mehr Flexibilität bei der Anwendung von betriebssystemspezifischen Richtlinien.</span><span class="sxs-lookup"><span data-stu-id="23957-223">This will give you more flexibility to apply policies that are specific to an operating system.</span></span>
>
> <span data-ttu-id="23957-224">Sie können keine Gruppen bereitstellen, die dynamisch auf dem Betriebssystem des Geräts basieren.</span><span class="sxs-lookup"><span data-stu-id="23957-224">You cannot provision groups dynamically based on the operating system of the device.</span></span> <span data-ttu-id="23957-225">Führen Sie stattdessen diesen Schritt aus, indem Sie Active Directory oder die Sicherheitsgruppen von Azure Active Directory verwenden.</span><span class="sxs-lookup"><span data-stu-id="23957-225">Instead, do this by using Active Directory or Azure Active Directory security groups.</span></span>

![Gruppe „Laptopbenutzer“](../media/Intune_Planning_Groups_OS_Hierachy_small.png)

<span data-ttu-id="23957-227">Nachdem alle Ihre Benutzergruppen basierend auf diesen Anforderungen Ihres Unternehmens aufgefüllt wurden, sollte die Gruppenhierarchie in etwa wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="23957-227">After all of your user groups are populated based on your organizational requirements, your group hierarchy should look something like this:</span></span>

![Ansicht der Gruppenhierarchie](../media/Intune_Planning_Groups_Midpoint_Hierachy_small.png)

<span data-ttu-id="23957-229">Sie können diese Hierarchie dazu verwenden, die Richtlinien des Unternehmens anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="23957-229">You can use this hierarchy to apply the organization's policies.</span></span>

### <a name="device-groups"></a><span data-ttu-id="23957-230">Gerätegruppen</span><span class="sxs-lookup"><span data-stu-id="23957-230">Device groups</span></span>
<span data-ttu-id="23957-231">Sie können auch ähnliche Gruppen für Geräte erstellen, wie hier gezeigt, wobei Sie mit einer umfassenden Gruppe beginnen, die alle benutzereigenen Geräte für das BYOD-Szenario einbezieht:</span><span class="sxs-lookup"><span data-stu-id="23957-231">You also can create similar groups for devices as shown here, starting with a broad group that includes all employee-owned devices, for the BYOD scenario.</span></span>

![Dialogfeld „Gruppe erstellen“](../media/Intune_Planning_Groups_Device_General_small.png)

<span data-ttu-id="23957-233">Stellen Sie sicher, dass Sie die Option **Alle Geräte (Computer und mobile Geräte)** auswählen, damit die Gruppe alle BYOD-Geräte umfasst:</span><span class="sxs-lookup"><span data-stu-id="23957-233">Make sure that you select **All devices (computers and mobile)** so that the group will include all BYO devices:</span></span>

![Seite „Mitgliedschaftskriterien definieren“](../media/Intune_Planning_Groups_Device_Criteria_small.png)

<span data-ttu-id="23957-235">Überprüfen Sie Ihre Eingaben, und wählen Sie anschließend **Fertig stellen**aus, um die BYOD-Gruppe zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="23957-235">Review your entries, and then choose **Finish** to create the BYOD group.</span></span>

![Dialogfeld „Gruppe erstellen“](../media/Intune_Planning_Groups_Device_Summary_small.png)

<span data-ttu-id="23957-237">Setzen Sie die Erstellung der Gerätegruppen fort, bis Sie über eine Gerätegruppenhierarchie verfügen, die der Benutzergruppenhierarchie ähnelt.</span><span class="sxs-lookup"><span data-stu-id="23957-237">Continue to create device groups until you have a device group hierarchy that is similar to the user group hierarchy.</span></span> <span data-ttu-id="23957-238">Ihr Gruppenknoten wird in der Intune-Konsole etwa wie folgt aussehen:</span><span class="sxs-lookup"><span data-stu-id="23957-238">Your group node in the Intune console will look similar to this:</span></span>

![Intune-Ansicht der Gruppenhierarchie](../media/Intune_Groups_Hierarchy_Final_Small.png)

## <a name="group-hierarchies-and-naming-conventions"></a><span data-ttu-id="23957-240">Gruppenhierarchien und Benennungskonventionen</span><span class="sxs-lookup"><span data-stu-id="23957-240">Group hierarchies and naming conventions</span></span>
<span data-ttu-id="23957-241">Zur Vereinfachung der Richtlinienverwaltung wird empfohlen, jede Richtlinie gemäß dem Zweck, der Plattform und dem Bereich ihrer Anwendung zu benennen.</span><span class="sxs-lookup"><span data-stu-id="23957-241">To make policy management easier, we recommend that you name each policy according to the purpose, platform, and scope to which you apply it.</span></span> <span data-ttu-id="23957-242">Verwenden Sie einen Benennungsstandard, der die Struktur befolgt, die Sie erstellt haben, als Sie sich darauf vorbereitet haben, Ihre Richtlinien anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="23957-242">Use a naming standard that follows the group structure that you created when you prepared to apply your policies.</span></span>

<span data-ttu-id="23957-243">Eine Android-Richtlinie, die auf alle unternehmenseigenen mobilen Android-Geräte in den USA angewendet wird, kann z.B. wie folgt benannt werden: **CO_US_Mob_Android_General**</span><span class="sxs-lookup"><span data-stu-id="23957-243">For instance, for an Android policy that applies to all corporate, Android, mobile devices at the U.S. regional level, you might name the policy **CO_US_Mob_Android_General**.</span></span>

![Erstellen einer Richtlinie für Android](../media/Intune_planning_policy_android_small.png)

<span data-ttu-id="23957-245">Wenn Sie Ihre Richtlinien auf diese Art benennen, können Sie Richtlinien sowie deren vorgesehenen Zweck und Gültigkeitsbereich im **Richtlinienknoten** erkennen, wie nachfolgend dargestellt:</span><span class="sxs-lookup"><span data-stu-id="23957-245">When you name your policies this way, you can quickly identify policies and their intended use and scope in the **Policies** node, like this:</span></span>

![Liste der Intune-Richtlinien](../media/Intune_planning_policy_view_small.png)

## <a name="next-steps"></a><span data-ttu-id="23957-247">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="23957-247">Next steps</span></span>
[<span data-ttu-id="23957-248">Erstellen von Gruppen</span><span class="sxs-lookup"><span data-stu-id="23957-248">Create groups</span></span>](use-groups-to-manage-users-and-devices-with-microsoft-intune.md)
