---
title: Rollenbasierte Zugriffssteuerung mit Intune
titleSuffix: Azure portal
description: "Intune in Azure (Vorschau): Erfahren Sie, wie Sie mit der rollenbasierten Zugriffssteuerung steuern können, wer Aktionen ausführen und Änderungen vornehmen kann."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 06/21/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: ca3de752-3caa-46a4-b4ed-ee9012ccae8e
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 9e40e5ffc938058d2a0a32162ff39adc89485c5b
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2017
---
# <a name="role-based-administration-control-rbac-with-intune"></a><span data-ttu-id="78874-103">Rollenbasierte Zugriffssteuerung mit Intune</span><span class="sxs-lookup"><span data-stu-id="78874-103">Role-based administration control (RBAC) with Intune</span></span>

<span data-ttu-id="78874-104">Mithilfe der rollenbasierten Zugriffssteuerung können Sie bestimmen, wer verschiedene Intune-Aufgaben in Ihrer Organisation ausführen darf und für wen diese Aufgaben gelten.</span><span class="sxs-lookup"><span data-stu-id="78874-104">RBAC helps you control who can perform various Intune tasks within your organization, and who those tasks apply to.</span></span> <span data-ttu-id="78874-105">Sie können entweder die integrierten Rollen verwenden, die einige allgemeine Intune-Szenarien abdecken, oder Sie können eigene Rollen erstellen.</span><span class="sxs-lookup"><span data-stu-id="78874-105">You can either use the built-in roles that cover some common Intune scenarios, or you can create your own roles.</span></span> <span data-ttu-id="78874-106">Eine Rolle wird durch Folgendes definiert:</span><span class="sxs-lookup"><span data-stu-id="78874-106">A role is defined by:</span></span>

- <span data-ttu-id="78874-107">**Rollendefinition**: Der Name einer Rolle, die von ihr verwalteten Ressourcen und die jeder Ressource erteilten Berechtigungen.</span><span class="sxs-lookup"><span data-stu-id="78874-107">**Role definition**: The name of a role, the resources it manages, and the permissions granted for each resource.</span></span>
- <span data-ttu-id="78874-108">**Mitglieder**: Die Benutzergruppen, denen die Berechtigungen erteilt werden.</span><span class="sxs-lookup"><span data-stu-id="78874-108">**Members**: The user groups that are granted the permissions.</span></span>
- <span data-ttu-id="78874-109">**Bereich**: Die Benutzer- bzw. Gerätegruppen, die die Mitglieder verwalten können.</span><span class="sxs-lookup"><span data-stu-id="78874-109">**Scope**: The user or device groups that the members can manage.</span></span>
- <span data-ttu-id="78874-110">**Zuweisung:** Nachdem die Definition, Mitglieder und der Bereich konfiguriert wurden, wird die Rolle zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="78874-110">**Assignment**: When the definition, members, and scope have been configured, the role is assigned.</span></span>

![Beispiel für die rollenbasierte Zugriffssteuerung mit Intune](./media/intune-rbac-1.PNG)

<span data-ttu-id="78874-112">Beginnend mit dem neuen Azure-Portal bietet **Azure Active Directory (Azure AD)** zwei Verzeichnisrollen, die mit Intune verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="78874-112">Starting at the new Azure portal, **Azure Active Directory (Azure AD)** provides two Directory Roles which can be used with Intune.</span></span> <span data-ttu-id="78874-113">Diese Rollen haben die Vollzugriffsberechtigung für alle Aktivitäten in Intune:</span><span class="sxs-lookup"><span data-stu-id="78874-113">These roles are granted full permission to perform all activities in Intune:</span></span>

- <span data-ttu-id="78874-114">**Globaler Administrator:** Benutzer mit dieser Rolle haben Zugriff auf alle administrativen Funktionen in Azure AD sowie auf Dienste, die mit Azure AD einen Verbund bilden, wie z.B. Exchange Online, SharePoint Online und Skype for Business Online.</span><span class="sxs-lookup"><span data-stu-id="78874-114">**Global Administrator:** Users with this role have access to all administrative features in Azure AD, as well as services that federate to Azure AD like Exchange Online, SharePoint Online, and Skype for Business Online.</span></span> <span data-ttu-id="78874-115">Die Person, die sich für den Azure AD-Mandanten registriert, wird ein globaler Administrator.</span><span class="sxs-lookup"><span data-stu-id="78874-115">The person who signs up for the Azure AD tenant becomes a global administrator.</span></span> <span data-ttu-id="78874-116">Nur globale Administratoren können weitere Azure AD-Administratorrollen zuweisen.</span><span class="sxs-lookup"><span data-stu-id="78874-116">Only global administrators can assign other Azure AD administrator roles.</span></span> <span data-ttu-id="78874-117">Es kann mehr als einen globalen Administrator in Ihrem Unternehmen geben.</span><span class="sxs-lookup"><span data-stu-id="78874-117">There can be more than one global administrator at your organization.</span></span> <span data-ttu-id="78874-118">Globale Administratoren können das Kennwort aller Benutzer und aller anderen Administratoren zurücksetzen.</span><span class="sxs-lookup"><span data-stu-id="78874-118">Global admins can reset the password for any user and all other administrators.</span></span>

- <span data-ttu-id="78874-119">**Intune-Dienstadministrator:** Benutzer mit dieser Rolle haben globale Berechtigungen in Intune, sobald der Dienst aktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="78874-119">**Intune Service Administrator:** Users with this role have global permissions within Intune when the service is present.</span></span> <span data-ttu-id="78874-120">Neben ersetzenden Azure-Einschränkungen bietet diese Rolle die Möglichkeit, Benutzer und Geräte zu verwalten sowie Intune-Gruppen zu erstellen und zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="78874-120">Additionally, other than any superseding Azure restrictions, this role provides the ability to manage users, devices, and create and manage Intune groups.</span></span>

- <span data-ttu-id="78874-121">**Administrator für bedingten Zugriff**: Benutzer mit dieser Rolle haben nur Berechtigungen, Richtlinien für den bedingten Zugriff anzuzeigen, zu erstellen, zu bearbeiten und zu löschen.</span><span class="sxs-lookup"><span data-stu-id="78874-121">**Conditional Access Administrator:** Users with this role only have permissions to view, create, modify, and delete conditional access policies.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="78874-122">Die Rolle „Intune-Dienstadministrator“ ermöglicht nicht das Verwalten der Azure AD-Einstellungen für bedingten Zugriff.</span><span class="sxs-lookup"><span data-stu-id="78874-122">The Intune Service Administrator role does not provide the ability to manage Azure AD’s conditional access settings.</span></span>

    > [!TIP]
    > <span data-ttu-id="78874-123">Intune zeigt außerdem drei Azure AD-Erweiterungen an, **Benutzer**, **Gruppen** und **Bedingter Zugriff**, die mithilfe der rollenbasierten Zugriffssteuerung von Azure AD gesteuert werden.</span><span class="sxs-lookup"><span data-stu-id="78874-123">Intune also shows three Azure AD extensions: **Users**, **Groups**, and **Conditional access**, which are controlled using Azure AD RBAC.</span></span> <span data-ttu-id="78874-124">Darüber hinaus führt der **Benutzerkontoadministrator** lediglich auf AAD-Benutzer- und Gruppen bezogene Aktivitäten aus und verfügt nicht über Vollzugriffsberechtigungen zum Ausführen aller Aktivitäten in Intune.</span><span class="sxs-lookup"><span data-stu-id="78874-124">Additionally, the **User Account Administrator** only performs AAD user/group activities and does not have full permissions to perform all activities in Intune.</span></span> <span data-ttu-id="78874-125">Unter [Rollenbasierte Zugriffssteuerung in Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-assign-admin-roles) finden Sie weitere Details.</span><span class="sxs-lookup"><span data-stu-id="78874-125">Refer to [RBAC with Azure AD](https://docs.microsoft.com/azure/active-directory/active-directory-assign-admin-roles) for more details.</span></span>

## <a name="roles-created-in-the-intune-classic-portal"></a><span data-ttu-id="78874-126">Im klassischen Intune-Portal erstellte Rollen</span><span class="sxs-lookup"><span data-stu-id="78874-126">Roles created in the Intune classic portal</span></span>

<span data-ttu-id="78874-127">Nur Benutzer mit der Rolle **Intune-Dienstadministrator** mit Vollzugriffsberechtigung werden vom klassischen Intune-Portal zu Intune in Azure migriert.</span><span class="sxs-lookup"><span data-stu-id="78874-127">Only Intune **Service Administrators** users with "Full" permissions get migrated from the Intune classic portal to Intune in the Azure portal.</span></span> <span data-ttu-id="78874-128">Sie müssen Benutzer mit der Rolle **Intune-Dienstadministrator** mit der Zugriffsebene „Schreibgeschützt“ oder „Support“ Intune-Rollen im Azure-Portal neu zuweisen und aus dem klassischen Azure-Portal entfernen.</span><span class="sxs-lookup"><span data-stu-id="78874-128">You need to re-assign Intune **Service Administrators** users with "Read-Only" or "Helpdesk" access into the Intune roles in the Azure portal, and remove them from the classic portal.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="78874-129">Sie können den Zugriff für Intune-Dienstadministratoren im klassischen Portal ggf. beibehalten, wenn Ihre Administratoren weiterhin einen Zugriff zum Verwalten von PCs mit Intune benötigen.</span><span class="sxs-lookup"><span data-stu-id="78874-129">You might need to keep the Intune Service Administrator access in the classic portal if your admins still need access to manage PC’s using with Intune.</span></span>

## <a name="built-in-roles"></a><span data-ttu-id="78874-130">Integrierte Rollen</span><span class="sxs-lookup"><span data-stu-id="78874-130">Built-in roles</span></span>

<span data-ttu-id="78874-131">Die folgenden Rollen sind in Intune integriert. Sie können sie ohne weitere Konfiguration Gruppen zuweisen:</span><span class="sxs-lookup"><span data-stu-id="78874-131">The following roles are built into Intune and you can assign them to groups with no further configuration:</span></span>

- <span data-ttu-id="78874-132">**Support**: Führt Remoteaufgaben für Benutzer und Geräte durch und kann Anwendungen oder Richtlinien Benutzern oder Geräten zuweisen.</span><span class="sxs-lookup"><span data-stu-id="78874-132">**Help Desk Operator**: Performs remote tasks on users and devices, and can assign applications or policies to users or devices.</span></span>
- <span data-ttu-id="78874-133">**Richtlinien- und Profil-Manager**: Verwaltet Konformitätsrichtlinien, Konfigurationsprofile, die Apple-Registrierung und unternehmensbezogene Geräte-IDs.</span><span class="sxs-lookup"><span data-stu-id="78874-133">**Policy and Profile Manager**: Manages compliance policy, configuration profiles, Apple enrollment, and corporate device identifiers.</span></span>
- <span data-ttu-id="78874-134">**Operator mit beschränkter Leseberechtigung**: Kann Benutzer-, Geräte-, Registrierungs-, Konfigurations- und Anwendungsinformationen anzeigen.</span><span class="sxs-lookup"><span data-stu-id="78874-134">**Read Only Operator**: Views user, device, enrollment, configuration, and application information.</span></span> <span data-ttu-id="78874-135">Es können keine Änderungen in Intune vorgenommen werden.</span><span class="sxs-lookup"><span data-stu-id="78874-135">Cannot make changes to Intune.</span></span>
- <span data-ttu-id="78874-136">**Anwendungs-Manager**: Verwaltet mobile und verwaltete Anwendungen und kann Geräteinformationen lesen.</span><span class="sxs-lookup"><span data-stu-id="78874-136">**Application Manager**: Manages mobile and managed applications, and can read device information.</span></span>

### <a name="to-assign-a-built-in-role"></a><span data-ttu-id="78874-137">So weisen Sie eine integrierte Rolle zu</span><span class="sxs-lookup"><span data-stu-id="78874-137">To assign a built-in role</span></span>

1. <span data-ttu-id="78874-138">Wählen Sie auf der Seite **Intune-Rollen** die integrierte Rolle aus, die Sie zuweisen möchten.</span><span class="sxs-lookup"><span data-stu-id="78874-138">On the **Intune roles**, choose the built-in role you want to assign.</span></span>

2. <span data-ttu-id="78874-139">Wählen Sie auf dem Blatt <*Rollenname*> – **Eigenschaften** erst **Verwalten** und dann **Zuweisungen** aus.</span><span class="sxs-lookup"><span data-stu-id="78874-139">On the <*role name*> - **Properties** blade, choose **Manage**, then **Assignments**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="78874-140">Sie können die integrierten Rollen nicht löschen oder bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="78874-140">You cannot delete or edit the built-in roles</span></span>

3. <span data-ttu-id="78874-141">Wählen Sie auf dem Blatt „Benutzerdefinierte Rolle“ **Zuweisen** aus.</span><span class="sxs-lookup"><span data-stu-id="78874-141">On the custom role blade, choose **Assign**.</span></span>

4. <span data-ttu-id="78874-142">Geben Sie auf dem Blatt **Rollenzuweisungen** einen **Namen** und eine optionale **Beschreibung** für die Zuweisung ein, und wählen Sie dann Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="78874-142">On the **Role Assignments** blade, enter a **Name** and optional **Description** for the assignment, and then choose the following:</span></span>
    - <span data-ttu-id="78874-143">**Mitglieder:** Wählen Sie eine Gruppe aus, die den Benutzer enthält, dem Sie die Berechtigungen erteilen möchten.</span><span class="sxs-lookup"><span data-stu-id="78874-143">**Members** - Select a group that contains the user you want to give the permissions to.</span></span>
    - <span data-ttu-id="78874-144">**Bereich:** Wählen Sie eine Gruppe aus, die die Benutzer enthält, die das oben ausgewählte Mitglied verwalten soll.</span><span class="sxs-lookup"><span data-stu-id="78874-144">**Scope** - Select a group containing the users who the member above will be allowed to manage.</span></span>
<br></br>
5. <span data-ttu-id="78874-145">Klicken Sie abschließend auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="78874-145">When you are done, click **OK**.</span></span> <span data-ttu-id="78874-146">Die neue Zuweisung wird in der Liste der Zuweisungen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="78874-146">The new assignment is displayed in the list of assignments.</span></span>

### <a name="intune-rbac-table"></a><span data-ttu-id="78874-147">Intune-Tabelle zur rollenbasierten Zugriffsteuerung</span><span class="sxs-lookup"><span data-stu-id="78874-147">Intune RBAC table</span></span>

- <span data-ttu-id="78874-148">Laden Sie die [Intune-Tabelle zur rollenbasierten Zugriffsteuerung](https://gallery.technet.microsoft.com/Intune-RBAC-table-2e3c9a1a) herunter, um weitere Details zu den Möglichkeiten jeder Rolle zu erfahren.</span><span class="sxs-lookup"><span data-stu-id="78874-148">Download the [Intune RBAC table](https://gallery.technet.microsoft.com/Intune-RBAC-table-2e3c9a1a) to see more details on what each role can do.</span></span>

## <a name="custom-roles"></a><span data-ttu-id="78874-149">Benutzerdefinierte Rollen</span><span class="sxs-lookup"><span data-stu-id="78874-149">Custom roles</span></span>

<span data-ttu-id="78874-150">Sie können eine benutzerdefinierte Sicherheitsrolle erstellen, die alle für einen bestimmten Aufgabenbereich erforderlichen Berechtigungen enthält.</span><span class="sxs-lookup"><span data-stu-id="78874-150">You can create a custom role that includes any permissions required for a specific job function.</span></span> <span data-ttu-id="78874-151">Wenn beispielsweise eine IT-Abteilungsgruppe Anwendungen, Richtlinien und Konfigurationsprofile verwaltet, können Sie alle diese Berechtigungen gemeinsam einer benutzerdefinierten Rolle hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="78874-151">For example, if an IT department group manages applications, policies, and configuration profiles, you can add all those permissions together in one custom role.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="78874-152">Für das Erstellen, Bearbeiten oder Zuweisen von Rollen muss das Konto in Azure AD über eine der folgenden Berechtigungen verfügen:</span><span class="sxs-lookup"><span data-stu-id="78874-152">To create, edit, or assign roles, your account must have one of the following permissions in Azure AD:</span></span>
> - <span data-ttu-id="78874-153">**Globaler Administrator**</span><span class="sxs-lookup"><span data-stu-id="78874-153">**Global Administrator**</span></span>
> - <span data-ttu-id="78874-154">**Intune-Dienstadministrator**</span><span class="sxs-lookup"><span data-stu-id="78874-154">**Intune Service Administrator**</span></span>

### <a name="to-create-a-custom-role"></a><span data-ttu-id="78874-155">So erstellen Sie eine benutzerdefinierte Rolle</span><span class="sxs-lookup"><span data-stu-id="78874-155">To create a custom role</span></span>

1. <span data-ttu-id="78874-156">Melden Sie sich beim [Azure-Portal](https://portal.azure.com) mit Ihren Intune-Anmeldeinformationen an.</span><span class="sxs-lookup"><span data-stu-id="78874-156">Sign into the [Azure portal](https://portal.azure.com) with your Intune credentials.</span></span>

2. <span data-ttu-id="78874-157">Wählen Sie im linken Menü **Weitere Dienste** aus, und geben Sie in das Filtertextfeld die Zeichenfolge **Intune** ein.</span><span class="sxs-lookup"><span data-stu-id="78874-157">Choose **More services** from the left menu, then type **Intune** in the text box filter.</span></span>

3. <span data-ttu-id="78874-158">Wählen Sie **Intune** aus. Daraufhin wird das Intune-Dashboard geöffnet. Wählen Sie **Intune-Rollen** aus.</span><span class="sxs-lookup"><span data-stu-id="78874-158">Choose **Intune**, the Intune Dashboard opens, choose **Intune roles**.</span></span>

4. <span data-ttu-id="78874-159">Wählen Sie auf dem Blatt **Intune-Rollen** wiederum **Intune-Rollen** und dann **Benutzerdefiniert hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="78874-159">On the **Intune roles** blade, choose **Intune roles**, choose **Add custom**.</span></span>

5. <span data-ttu-id="78874-160">Geben Sie auf dem Blatt **Benutzerdefinierte Rolle hinzufügen** einen Namen und eine Beschreibung für die neue Rolle ein, und klicken Sie dann auf **Berechtigungen**.</span><span class="sxs-lookup"><span data-stu-id="78874-160">On the **Add Custom Role** blade, enter a name and description for the new role, then click **Permissions**.</span></span>

3. <span data-ttu-id="78874-161">Wählen Sie auf dem Blatt **Berechtigungen** die Berechtigungen aus, die Sie mit dieser Rolle verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="78874-161">On the **Permissions** blade, choose the permissions you want to use with this role.</span></span> <span data-ttu-id="78874-162">Entscheiden Sie mithilfe der [Tabelle zur rollenbasierten Zugriffssteuerung in Intune](https://gallery.technet.microsoft.com/Intune-RBAC-table-2e3c9a1a), welche Berechtigungen gelten sollen.</span><span class="sxs-lookup"><span data-stu-id="78874-162">Use the [Intune RBAC table](https://gallery.technet.microsoft.com/Intune-RBAC-table-2e3c9a1a) to help you decide which permissions you want to apply.</span></span>

4. <span data-ttu-id="78874-163">Wählen Sie abschließend **OK** aus.</span><span class="sxs-lookup"><span data-stu-id="78874-163">When you are done, choose **OK**.</span></span>

5. <span data-ttu-id="78874-164">Klicken Sie auf dem Blatt **Benutzerdefinierte Rolle hinzufügen** auf **Erstellen**.</span><span class="sxs-lookup"><span data-stu-id="78874-164">On the **Add Custom Role** blade, click **Create**.</span></span> <span data-ttu-id="78874-165">Die neue Rolle wird in der Liste auf dem Blatt **Intune-Rollen** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="78874-165">The new role is displayed in the list on the **Intune roles** blade.</span></span>

### <a name="to-assign-a-custom-role"></a><span data-ttu-id="78874-166">So weisen Sie eine benutzerdefinierte Rolle zu</span><span class="sxs-lookup"><span data-stu-id="78874-166">To assign a custom role</span></span>

1. <span data-ttu-id="78874-167">Wählen Sie auf der Seite **Intune-Rollen** die benutzerdefinierte Rolle aus, die Sie zuweisen möchten.</span><span class="sxs-lookup"><span data-stu-id="78874-167">On the **Intune roles**, choose the custom role you want to assign.</span></span>

2. <span data-ttu-id="78874-168">Wählen Sie auf dem Blatt <*Rollenname*> – **Eigenschaften** erst **Verwalten** und dann **Zuweisungen** aus.</span><span class="sxs-lookup"><span data-stu-id="78874-168">On the <*role name*> - **Properties** blade, choose **Manage**, then **Assignments**.</span></span> <span data-ttu-id="78874-169">Sie können auf diesem Blatt auch vorhandene Rollen bearbeiten oder löschen.</span><span class="sxs-lookup"><span data-stu-id="78874-169">On this blade, you can also edit or delete existing roles.</span></span>

3. <span data-ttu-id="78874-170">Wählen Sie auf dem Blatt „Benutzerdefinierte Rolle“ **Zuweisen** aus.</span><span class="sxs-lookup"><span data-stu-id="78874-170">On the custom role blade, choose **Assign**.</span></span>

4. <span data-ttu-id="78874-171">Geben Sie auf dem Blatt **Rollenzuweisungen** einen **Namen** und eine optionale **Beschreibung** für die Zuweisung ein, und wählen Sie dann Folgendes aus:</span><span class="sxs-lookup"><span data-stu-id="78874-171">On the **Role Assignments** blade, enter a **Name** and optional **Description** for the assignment, and then choose the following:</span></span>
    - <span data-ttu-id="78874-172">**Mitglieder:** Wählen Sie eine Gruppe aus, die den Benutzer enthält, dem Sie die Berechtigungen erteilen möchten.</span><span class="sxs-lookup"><span data-stu-id="78874-172">**Members** - Select a group that contains the user you want to give the permissions to.</span></span>
    - <span data-ttu-id="78874-173">**Bereich:** Wählen Sie eine Gruppe aus, die die Benutzer enthält, die das oben ausgewählte Mitglied verwalten soll.</span><span class="sxs-lookup"><span data-stu-id="78874-173">**Scope** - Select a group containing the users who the member above will be allowed to manage.</span></span>
<br></br>
5. <span data-ttu-id="78874-174">Klicken Sie abschließend auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="78874-174">When you are done, click **OK**.</span></span> <span data-ttu-id="78874-175">Die neue Zuweisung wird in der Liste der Zuweisungen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="78874-175">The new assignment is displayed in the list of assignments.</span></span>

## <a name="next-steps"></a><span data-ttu-id="78874-176">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="78874-176">Next steps</span></span>

[<span data-ttu-id="78874-177">Verwenden der Rolle „Intune-Support“ im Portal zur Problembehandlung</span><span class="sxs-lookup"><span data-stu-id="78874-177">Use the Intune Helpdesk operator role with the troubleshooting portal</span></span>](help-desk-operators.md)

## <a name="see-also"></a><span data-ttu-id="78874-178">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="78874-178">See also</span></span>

[<span data-ttu-id="78874-179">Zuweisen von Rollen mithilfe von Azure AD</span><span class="sxs-lookup"><span data-stu-id="78874-179">Assign roles using Azure AD</span></span>](https://docs.microsoft.com/azure/active-directory/active-directory-users-assign-role-azure-portal)
