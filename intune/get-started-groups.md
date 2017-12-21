---
title: Erste Schritte mit Gruppen
titleSuffix: Azure portal
description: "Organisieren Sie Benutzer in Gruppen, um die Richtlinien und Apps leichter zu verwalten, auf die sie zugreifen können."
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 10/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 39a93fb5-d318-4997-a409-b64549a00e7a
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 6d176a3331f52e6d9faadf356792503266a0b73f
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2017
---
# <a name="get-started-with-groups"></a><span data-ttu-id="d2698-103">Erste Schritte mit Gruppen</span><span class="sxs-lookup"><span data-stu-id="d2698-103">Get started with groups</span></span>

<span data-ttu-id="d2698-104">Mit Gruppen können Sie Benutzer verwalten und den Zugriff Ihrer Mitarbeiter auf Ihre Unternehmensressourcen steuern.</span><span class="sxs-lookup"><span data-stu-id="d2698-104">Groups are used to manage your users, and control your employees' access to your company resources.</span></span> <span data-ttu-id="d2698-105">Diese Ressourcen können Teil Ihres Verzeichnisses oder externe Ressourcen wie SaaS-Apps oder SharePoint-Websites sein.</span><span class="sxs-lookup"><span data-stu-id="d2698-105">These resources can be part of your directory or can be external resources, like SaaS apps or SharePoint sites.</span></span>

<span data-ttu-id="d2698-106">Microsoft Intune verwendet Azure Active Directory (Azure AD) zum Verwalten des Zugriffs auf Unternehmensressourcen.</span><span class="sxs-lookup"><span data-stu-id="d2698-106">Microsoft Intune uses Azure Active Directory (Azure AD) to manage access to company resources.</span></span> <span data-ttu-id="d2698-107">Dieser Zugriff wird mithilfe von Rollen im Verzeichnis gesteuert.</span><span class="sxs-lookup"><span data-stu-id="d2698-107">This access is controlled using roles in the directory.</span></span> <span data-ttu-id="d2698-108">Intune verwaltet dann diesen Zugriff für mobile Geräte, wodurch Mitgliedern dieser Gruppe der Zugriff auf Ressourcen gewährt wird.</span><span class="sxs-lookup"><span data-stu-id="d2698-108">Intune then manages this access for mobile devices, which allows members of that group to access resources.</span></span>

## <a name="how-do-i-create-a-group"></a><span data-ttu-id="d2698-109">Wie erstelle ich eine Gruppe?</span><span class="sxs-lookup"><span data-stu-id="d2698-109">How do I create a group?</span></span>

1. <span data-ttu-id="d2698-110">Melden Sie sich beim [Azure-Portal](https://portal.azure.com) an.</span><span class="sxs-lookup"><span data-stu-id="d2698-110">Sign in to the [Azure portal](https://portal.azure.com).</span></span>
2. <span data-ttu-id="d2698-111">Suchen Sie über **Ressourcen durchsuchen** nach **Intune**.</span><span class="sxs-lookup"><span data-stu-id="d2698-111">Using **Search resources**, search for **Intune**.</span></span>
3. <span data-ttu-id="d2698-112">Wenn Sie das Blatt **Microsoft Intune** geöffnet haben, wählen Sie **Gruppen** aus.</span><span class="sxs-lookup"><span data-stu-id="d2698-112">Once you've opened the **Microsoft Intune** blade, select **Groups**.</span></span>
4. <span data-ttu-id="d2698-113">Wählen Sie auf dem Blatt **Users and Groups – All Groups** (Benutzer und Gruppen – Alle Gruppen) die Option **Neue Gruppe** aus.</span><span class="sxs-lookup"><span data-stu-id="d2698-113">On the **Users and groups – All groups** blade, select the **New group** command.</span></span>
5. <span data-ttu-id="d2698-114">Fügen Sie auf dem Blatt **Gruppe** einen **Namen** und eine **Beschreibung** für die Gruppe hinzu.</span><span class="sxs-lookup"><span data-stu-id="d2698-114">On the **Group** blade, add a **Name** and **Description** for the group.</span></span>
6. <span data-ttu-id="d2698-115">Legen Sie den **Mitgliedschaftstyp** auf **Zugewiesen** fest.</span><span class="sxs-lookup"><span data-stu-id="d2698-115">Set the **Membership type** as **Assigned**.</span></span> <span data-ttu-id="d2698-116">Für die Testgruppe sollten Sie **Office-Features nicht aktivieren**.</span><span class="sxs-lookup"><span data-stu-id="d2698-116">Do not **Enable Office features** for the test group.</span></span>
7. <span data-ttu-id="d2698-117">Klicken Sie auf **Erstellen**.</span><span class="sxs-lookup"><span data-stu-id="d2698-117">Click **Create**.</span></span>

<span data-ttu-id="d2698-118">Wenn Sie eine Gruppe erfolgreich erstellt haben, sollte sie in der Liste **Alle Gruppen** angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="d2698-118">If you've successfully created a group, it should appear in the list of **All groups**.</span></span> <span data-ttu-id="d2698-119">Versuchen Sie andernfalls, eine andere Gruppe zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="d2698-119">If it doesn't appear there, try to create another group.</span></span>

## <a name="next-steps"></a><span data-ttu-id="d2698-120">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="d2698-120">Next steps</span></span>

<span data-ttu-id="d2698-121">[Erste Schritte mit Richtlinien:](get-started-policies.md) Erstellen Sie Richtlinien, um zu verhindern, dass Benutzer nicht autorisierte Aktionen mit ihren Geräten vornehmen.</span><span class="sxs-lookup"><span data-stu-id="d2698-121">[Get started with policies](get-started-policies.md) - Create policies to prevent users from doing unauthorized things with their devices.</span></span>

## <a name="learn-more"></a><span data-ttu-id="d2698-122">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="d2698-122">Learn more</span></span>

* [<span data-ttu-id="d2698-123">Hinzufügen von Gruppen in Intune</span><span class="sxs-lookup"><span data-stu-id="d2698-123">Set enrollment restrictions using groups in Intune</span></span>](groups-add.md)
* [<span data-ttu-id="d2698-124">Verwalten des Zugriffs auf Ressourcen mit Azure Active Directory-Gruppen</span><span class="sxs-lookup"><span data-stu-id="d2698-124">Manage access to company resources using groups in Azure Active Directory</span></span>](https://docs.microsoft.com/azure/active-directory/active-directory-manage-groups)
