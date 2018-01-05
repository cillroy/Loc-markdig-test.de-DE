---
title: "Erstellen von Gruppen zum Organisieren von Benutzern und Geräten"
description: "Erstellen von Benutzern und Gruppen für Ihr Intune-Abonnement"
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 02/14/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5fdf98c8-fe67-4d7a-9837-ed1234348014
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 24ab124a7c8724fb41684b5d1ae9564c6f83dc60
ms.sourcegitcommit: e37e916e2bf14f092d3a767bc90d68c181d739fb
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/03/2018
---
# <a name="create-groups-to-organize-users-and-devices"></a><span data-ttu-id="65ecc-103">Erstellen von Gruppen zum Organisieren von Benutzern und Geräten</span><span class="sxs-lookup"><span data-stu-id="65ecc-103">Create groups to organize users and devices</span></span>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="65ecc-104">In diesem Thema erfahren Administratoren, wie sie Benutzergruppen in Intune erstellen können.</span><span class="sxs-lookup"><span data-stu-id="65ecc-104">This topic tells administrators how they can create groups of users in Intune.</span></span>

<span data-ttu-id="65ecc-105">Mit Gruppen erhalten Sie in Intune maximale Flexibilität beim Verwalten Ihrer Geräte und Benutzer.</span><span class="sxs-lookup"><span data-stu-id="65ecc-105">Groups in Intune give you great flexibility for managing your devices and users.</span></span> <span data-ttu-id="65ecc-106">Sie können Gruppen einrichten, die Ihren organisatorischen Anforderungen (z. B. nach geografischem Standort, nach Abteilung oder nach Hardwareeigenschaften) entsprechen und diese dazu verwenden, um eine Vielzahl von Verwaltungsaufgaben ausführen, die von der Bereitstellung von Richtlinien für eine Gruppe von Benutzern bis zur Bereitstellung von Anwendungen auf einer Reihe von Geräten reichen.</span><span class="sxs-lookup"><span data-stu-id="65ecc-106">You can set up groups to suit your organizational needs (for example, by geographic location, department, or hardware characteristics) and use them to perform a wide variety of administrative tasks, from deploying policies for a set of users to deploying applications to a set of devices.</span></span>

## <a name="group-management-moving-to-azure-ad"></a><span data-ttu-id="65ecc-107">Gruppenverwaltung wechselt zu Azure AD</span><span class="sxs-lookup"><span data-stu-id="65ecc-107">Group management moving to Azure AD</span></span>

<span data-ttu-id="65ecc-108">**Ab November 2016** erfolgt die Verwaltung von Benutzer- und Gerätegruppen für neue Konten im Azure Active Directory-Portal (Azure AD).</span><span class="sxs-lookup"><span data-stu-id="65ecc-108">**Starting in November 2016**, new accounts will manage user and device groups in the Azure Active Directory (AD) portal.</span></span> <span data-ttu-id="65ecc-109">Im Dezember 2016 beginnt das Intune-Produktteam mit der Migration von Bestandskunden zur neuen Azure AD-basierten Gruppenverwaltungsoberfläche.</span><span class="sxs-lookup"><span data-stu-id="65ecc-109">In December 2016, the Intune product team will begin to migrate existing customers to the new Azure AD-based group management experience.</span></span> <span data-ttu-id="65ecc-110">Alle Benutzer- und -Gerätegruppen werden zu Azure AD-Sicherheitsgruppen migriert.</span><span class="sxs-lookup"><span data-stu-id="65ecc-110">All user and device groups will be migrated to Azure AD security groups.</span></span> <span data-ttu-id="65ecc-111">Mit den Migrationen wird erst begonnen, wenn wir die Auswirkungen auf Ihre alltägliche Arbeit auf ein Minimum beschränken und erwarten können, dass Auswirkungen auf Ihre Benutzer ausbleiben.</span><span class="sxs-lookup"><span data-stu-id="65ecc-111">We won’t start migrations until we can minimize any effect on your day-to-day work, and when we expect there will be no effect on your users.</span></span> <span data-ttu-id="65ecc-112">Außerdem benachrichtigen wir Sie, bevor wir Ihr Konto migrieren.</span><span class="sxs-lookup"><span data-stu-id="65ecc-112">We also will give you notice before we migrate your account.</span></span>


>[!IMPORTANT]
>
><span data-ttu-id="65ecc-113">Wenn Sie den Arbeitsbereich „Gruppen“ im Intune-Portal öffnen und dort den Hinweis **Intune-Benutzergruppen werden jetzt als Gruppen in Active Directory verwaltet** mit einem Link zum Azure Active Directory-Portal sehen, verwenden Sie bereits den *neuen* Ansatz für Azure AD-Sicherheitsgruppen für die Gruppenverwaltung in Intune.</span><span class="sxs-lookup"><span data-stu-id="65ecc-113">If you open the Groups workspace in the Intune portal and see **Intune user groups are now managed as groups in Azure Active Directory** with a link to the Azure Active Directory portal, then you are already using the *new* Azure AD security groups approach to group management in Intune.</span></span> <span data-ttu-id="65ecc-114">Informationen zum Erstellen von Gruppen finden Sie unter [Verwalten von Gruppen in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-groups-create-azure-portal).</span><span class="sxs-lookup"><span data-stu-id="65ecc-114">To learn how to create groups, see [Managing groups in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-groups-create-azure-portal).</span></span>
>
><span data-ttu-id="65ecc-115">Wenn kein Link zum Azure AD-Portal angezeigt wird, verwenden Sie noch das Intune-Portal für die Gruppenverwaltung.</span><span class="sxs-lookup"><span data-stu-id="65ecc-115">If you do not see the link to the Azure AD portal, you are still using the Intune portal for groups management.</span></span>

## <a name="group-management-in-the-intune-portal"></a><span data-ttu-id="65ecc-116">Gruppenverwaltung im Intune-Portal</span><span class="sxs-lookup"><span data-stu-id="65ecc-116">Group management in the Intune portal</span></span>

<span data-ttu-id="65ecc-117">Sowohl Geräte als auch Benutzergruppen werden im Arbeitsbereich „Gruppen“ der Intune-Administratorkonsole erstellt.</span><span class="sxs-lookup"><span data-stu-id="65ecc-117">Device and user groups are both created in the GROUPS workspace of the Intune administration console.</span></span>

![Arbeitsbereich „Gruppen“ der Verwaltungskonsole](./media/groups.png)


> [!TIP]
> <span data-ttu-id="65ecc-119">Weitere Informationen zum Verwenden von Gruppen finden Sie unter [Erstellen von Gruppen zum Verwalten von Benutzern und Geräten in Microsoft Intune](/intune-classic/deploy-use/use-groups-to-manage-users-and-devices-with-microsoft-intune).</span><span class="sxs-lookup"><span data-stu-id="65ecc-119">To learn more about using groups, see [Use groups to manage users and devices with Microsoft Intune](/intune-classic/deploy-use/use-groups-to-manage-users-and-devices-with-microsoft-intune).</span></span>


## <a name="create-a-device-group"></a><span data-ttu-id="65ecc-120">Erstellen einer Gerätegruppe</span><span class="sxs-lookup"><span data-stu-id="65ecc-120">Create a device group</span></span>
<span data-ttu-id="65ecc-121">Verwenden Sie Gerätegruppen zum Bereitstellen von Apps und Updates sowie zum Konfigurieren anderer Features.</span><span class="sxs-lookup"><span data-stu-id="65ecc-121">Use device groups to deploy apps and updates, and configure other features.</span></span> <span data-ttu-id="65ecc-122">Richten Sie z. B. die Gruppe „Meine Geräte“ mithilfe der folgenden Schritte ein:</span><span class="sxs-lookup"><span data-stu-id="65ecc-122">For example, set up a "My Devices" group using the following steps:</span></span>

1.  <span data-ttu-id="65ecc-123">Wählen Sie in der [Intune-Administratorkonsole](https://manage.microsoft.com/) **Gruppen** > **Übersicht** > **Gruppe erstellen** aus.</span><span class="sxs-lookup"><span data-stu-id="65ecc-123">In the [Intune administration console](https://manage.microsoft.com/), choose **Groups** > **Overview** > **Create Group**.</span></span>

2.  <span data-ttu-id="65ecc-124">Geben Sie unter **Gruppenname** „Meine Geräte“ ein, und wählen Sie in der übergeordneten Gruppenliste **Alle Geräte** und anschließend **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="65ecc-124">For the **Group name**, type “My Devices” and, from the parent group list, select **All Devices**, and then choose **Next**.</span></span>

3.  <span data-ttu-id="65ecc-125">Wählen Sie **Alle Geräte** auf der Seite **Mitgliedschaftskriterien definieren** aus, um anzugeben, dass die Gruppe sowohl mobile Geräte als auch Computer enthält.</span><span class="sxs-lookup"><span data-stu-id="65ecc-125">On the **Define Membership Criteria** page, select **All devices** to indicate that the group includes both mobile devices and computers.</span></span>

4.  <span data-ttu-id="65ecc-126">Klicken Sie auf der Seite **Direkte Mitgliedschaft definieren** auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="65ecc-126">On the **Define Direct Membership** page, choose **Next**.</span></span> <span data-ttu-id="65ecc-127">Hätten Sie zuvor eine Gruppe erstellt, die nicht alle Geräte enthält, und wollten Sie dieser neuen Gruppe nun bestimmte Geräte hinzufügen, dann können Sie dies an dieser Stelle tun.</span><span class="sxs-lookup"><span data-stu-id="65ecc-127">If you previously created a group that did not include all devices, and you wanted to add specific devices to your new group, you can do that here.</span></span>

5.  <span data-ttu-id="65ecc-128">Überprüfen Sie auf der Seite **Zusammenfassung** die Aktionen, die ausgeführt werden, und wählen Sie anschließend **Fertig stellen** aus.</span><span class="sxs-lookup"><span data-stu-id="65ecc-128">On the **Summary** page, review the actions that will be taken, and then choose **Finish**.</span></span>

<span data-ttu-id="65ecc-129">Sie finden die neue Gruppe in der Liste **Gruppen** im Arbeitsbereich **Gruppen** unter **Alle Geräte**.</span><span class="sxs-lookup"><span data-stu-id="65ecc-129">You can find the newly created group in the **Groups** list, in the **Groups** workspace, under **All Devices**.</span></span> <span data-ttu-id="65ecc-130">Hier können Sie die Gruppe auch bearbeiten oder löschen.</span><span class="sxs-lookup"><span data-stu-id="65ecc-130">From here, you can also edit or delete the group.</span></span>

## <a name="create-a-user-group"></a><span data-ttu-id="65ecc-131">Erstellen einer Benutzergruppe</span><span class="sxs-lookup"><span data-stu-id="65ecc-131">Create a user group</span></span>
<span data-ttu-id="65ecc-132">Verwenden Sie Benutzergruppen, um Software- und Geräterichtlinien bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="65ecc-132">Use user groups to deploy software and device policies.</span></span> <span data-ttu-id="65ecc-133">Richten Sie z. B. die Gruppe „Intune-Benutzer“ mithilfe der folgenden Schritte ein:</span><span class="sxs-lookup"><span data-stu-id="65ecc-133">For example, set up an "Intune Users" group using the following steps:</span></span>

1.  <span data-ttu-id="65ecc-134">Wählen Sie in der [Intune-Administratorkonsole](https://manage.microsoft.com/) **Gruppen** > **Übersicht** > **Gruppe erstellen** aus.</span><span class="sxs-lookup"><span data-stu-id="65ecc-134">In the [Intune administration console](https://manage.microsoft.com/), choose **Groups** > **Overview** > **Create Group**.</span></span>

2.  <span data-ttu-id="65ecc-135">Geben Sie unter **Gruppenname** „Intune-Benutzer“ ein, und wählen Sie aus der übergeordneten Gruppenliste **Alle Benutzer** und anschließend **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="65ecc-135">For the **Group name**, type “Intune Users” and, from the parent group list, select **All Users**, and then choose **Next**.</span></span>

3.  <span data-ttu-id="65ecc-136">Setzen Sie auf der Seite **Mitgliedschaftskriterien definieren** die Option **Gruppenmitgliedschaft starten mit** auf **Alle Benutzer in der übergeordneten Gruppe**.</span><span class="sxs-lookup"><span data-stu-id="65ecc-136">On the **Define Membership Criteria** page, set **Start group membership with** to **All users in the Parent group**.</span></span>

4.  <span data-ttu-id="65ecc-137">Klicken Sie neben **Mitglieder dieser Sicherheitsgruppen ausschließen** auf **Durchsuchen** und anschließend auf **Unternehmensadministrator**.</span><span class="sxs-lookup"><span data-stu-id="65ecc-137">Beside **Exclude members from these security groups**, choose **Browse** and then select **Company Administrator**.</span></span> <span data-ttu-id="65ecc-138">Durch diesen Ausschluss können Sie die Gruppe „Intune-Benutzer“ verwalten, ohne dass das Konto „Unternehmensadministrator“ (auch als Mandantenadministrator bezeichnet) davon betroffen ist.</span><span class="sxs-lookup"><span data-stu-id="65ecc-138">This exclusion lets you manage the Intune Users group without affecting the Company Administrator account (also known as the tenant administrator).</span></span>

5.  <span data-ttu-id="65ecc-139">Klicken Sie auf der Seite **Direkte Mitgliedschaft definieren** auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="65ecc-139">On the **Define Direct Membership** page, choose **Next**.</span></span> <span data-ttu-id="65ecc-140">Hier brauchen Sie nichts zu tun, denn die Gruppe „Intune-Benutzer“ soll alle Benutzer außer dem Unternehmensadministrator einschließen.</span><span class="sxs-lookup"><span data-stu-id="65ecc-140">You don’t need to do anything here because you want the Intune Users group to include all users, except for the Company Administrator.</span></span>

6.  <span data-ttu-id="65ecc-141">Überprüfen Sie auf der Seite **Zusammenfassung** die Aktionen, die ausgeführt werden, und wählen Sie anschließend **Fertig stellen** aus.</span><span class="sxs-lookup"><span data-stu-id="65ecc-141">On the **Summary** page, review the actions that will be taken, and then choose **Finish**.</span></span>

<span data-ttu-id="65ecc-142">Sie finden die neue Gruppe in der Liste **Gruppen** im Arbeitsbereich **Gruppen** unter **Alle Benutzer**.</span><span class="sxs-lookup"><span data-stu-id="65ecc-142">You can find the newly created group in the **Groups** list, in the **Groups** workspace, under **All Users**.</span></span> <span data-ttu-id="65ecc-143">Hier können Sie die Gruppe auch bearbeiten oder löschen.</span><span class="sxs-lookup"><span data-stu-id="65ecc-143">From here, you can also edit or delete the group.</span></span>

> [!div class="step-by-step"]
> <span data-ttu-id="65ecc-144">/intune/licenses-assign [&larr; **Verwalten von Intune-Lizenzen**](/intune/licenses-assign)       [**Erstellen von Richtlinien und Apps** &rarr;](.\start-with-a-paid-subscription-to-microsoft-intune-step-6.md)</span><span class="sxs-lookup"><span data-stu-id="65ecc-144">/intune/licenses-assign [&larr; **Manage Intune licenses**](/intune/licenses-assign)       [**Create policies and apps** &rarr;](.\start-with-a-paid-subscription-to-microsoft-intune-step-6.md)</span></span>  
