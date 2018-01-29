---
title: Erste Schritte mit Benutzern
titlesuffix: Azure portal
description: "Fügen Sie in Intune Benutzer hinzu, um ihnen den Zugriff auf Unternehmensressourcen auf mobilen Geräten zu ermöglichen."
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 10/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 22a232de-ab93-44ab-b0b5-d2b3ccb007fe
ms.reviewer: 
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 4d7ff6b4943d6cba05b9c7909882de6515ae7ce9
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2018
---
# <a name="get-started-with-managing-users"></a><span data-ttu-id="1aa99-103">Erste Schritte mit der Benutzerverwaltung</span><span class="sxs-lookup"><span data-stu-id="1aa99-103">Get started with managing users</span></span>

<span data-ttu-id="1aa99-104">Denken Sie an die verschiedenen Personen in Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="1aa99-104">Think about all the different people in your organization.</span></span> <span data-ttu-id="1aa99-105">Jeder von ihnen, der Unternehmensdaten verwendet, benötigt einen Benutzer, um den Zugriff auf die Daten in Intune zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="1aa99-105">Every one of them that uses company data will need a user to manage access to it in Intune.</span></span>

## <a name="how-do-i-create-a-user"></a><span data-ttu-id="1aa99-106">Wie erstelle ich einen Benutzer?</span><span class="sxs-lookup"><span data-stu-id="1aa99-106">How do I create a user?</span></span>

1. <span data-ttu-id="1aa99-107">Melden Sie sich beim [Azure-Portal](https://portal.azure.com) an.</span><span class="sxs-lookup"><span data-stu-id="1aa99-107">Sign in to the [Azure portal](https://portal.azure.com).</span></span>
2. <span data-ttu-id="1aa99-108">Suchen Sie über **Ressourcen durchsuchen** nach **Intune**.</span><span class="sxs-lookup"><span data-stu-id="1aa99-108">Using **Search resources**, search for **Intune**.</span></span>
3. <span data-ttu-id="1aa99-109">Wenn Sie das Blatt **Microsoft Intune** geöffnet haben, wählen Sie **Benutzer** aus.</span><span class="sxs-lookup"><span data-stu-id="1aa99-109">Once you've opened the **Microsoft Intune** blade, select **Users**.</span></span> <span data-ttu-id="1aa99-110">Wählen Sie auf der Seite **Alle Benutzer** die Option **+ Neuer Benutzer** aus.</span><span class="sxs-lookup"><span data-stu-id="1aa99-110">On the **All Users** page, select **+ New user**.</span></span>
4. <span data-ttu-id="1aa99-111">Machen Sie genauere Angaben zum Benutzer: geben Sie z.B. einen **Namen** und einen **Benutzernamen** ein.</span><span class="sxs-lookup"><span data-stu-id="1aa99-111">Enter details for the user, such as **Name** and **User name**.</span></span> <span data-ttu-id="1aa99-112">Der Domänennamenteil des Benutzernamens muss entweder der anfängliche Standarddomänenname „contoso.onmicrosoft.com“ oder ein verifizierter Domänenname ohne Verbund wie z.B. „contoso.com“ sein.</span><span class="sxs-lookup"><span data-stu-id="1aa99-112">The domain name portion of the user name must either be the initial default domain name “contoso.onmicrosoft.com” domain name, or a verified, non-federated domain name such as “contoso.com.”</span></span>
5. <span data-ttu-id="1aa99-113">Wählen Sie unter **Gruppen** die Testgruppe, die Sie dem Benutzer hinzufügen möchten.</span><span class="sxs-lookup"><span data-stu-id="1aa99-113">Under **Groups**, choose the test group to add the user to.</span></span>
6. <span data-ttu-id="1aa99-114">Speichern Sie das automatisch generierte Benutzerkennwort, das Sie zur Anmeldung bei einem Testgerät benötigen.</span><span class="sxs-lookup"><span data-stu-id="1aa99-114">Save the automatically generated user password so that you can use it to log in to a test device.</span></span> <span data-ttu-id="1aa99-115">Dieses Kennwort müssen Sie Benutzern geben, damit sie es in ein normales Kennwort ändern können, das sie sich leichter merken können.</span><span class="sxs-lookup"><span data-stu-id="1aa99-115">You must give this password to users so that they can change it to a normal password that they can remember.</span></span>
7. <span data-ttu-id="1aa99-116">Klicken Sie auf dem Blatt **Benutzer** auf **Erstellen**.</span><span class="sxs-lookup"><span data-stu-id="1aa99-116">On the **User** blade, select **Create**.</span></span>

## <a name="assigning-licenses-to-users"></a><span data-ttu-id="1aa99-117">Zuweisen von Lizenzen zu Benutzern</span><span class="sxs-lookup"><span data-stu-id="1aa99-117">Assigning licenses to users</span></span>

<span data-ttu-id="1aa99-118">Nachdem Sie einen Benutzer erstellt haben, können Sie über das [Office 365-Portal](http://go.microsoft.com/fwlink/p/?LinkId=698854) einem Benutzer eine Intune-Lizenz zuweisen.</span><span class="sxs-lookup"><span data-stu-id="1aa99-118">After you've created a user, you need to use the [Office 365 portal](http://go.microsoft.com/fwlink/p/?LinkId=698854) to assign an Intune license to that user.</span></span> <span data-ttu-id="1aa99-119">Wenn ein Benutzer keine Lizenz hat, kann er sein Gerät auch nicht für die Verwaltung registrieren.</span><span class="sxs-lookup"><span data-stu-id="1aa99-119">Without assigning them a license, they can't enroll their device into management.</span></span>

1. <span data-ttu-id="1aa99-120">Melden Sie sich im [Office 365-Portal](http://go.microsoft.com/fwlink/p/?LinkId=698854) mit den gleichen Anmeldeinformationen an, die Sie auch zur Anmeldung in Intune verwendet haben.</span><span class="sxs-lookup"><span data-stu-id="1aa99-120">Sign in to the [Office 365 portal](http://go.microsoft.com/fwlink/p/?LinkId=698854) with the same credentials you used to sign in to Intune.</span></span>
2. <span data-ttu-id="1aa99-121">Klicken Sie auf **Benutzer** > **Aktive Benutzer**, und klicken Sie anschließend auf den Benutzer, den Sie erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="1aa99-121">Select **Users** > **Active Users**, then select the user you previously created.</span></span>
3. <span data-ttu-id="1aa99-122">Möglicherweise nimmt das Laden aller Informationen des Benutzers einige Zeit in Anspruch.</span><span class="sxs-lookup"><span data-stu-id="1aa99-122">You may need to wait a moment for all of the user's information to load.</span></span> <span data-ttu-id="1aa99-123">Sobald Sie geladen wurden, klicken Sie für die **Produktlizenzen** des Benutzers auf **Bearbeiten**.</span><span class="sxs-lookup"><span data-stu-id="1aa99-123">Once it loads, select **Edit** for the user's **Product licenses**.</span></span>
4. <span data-ttu-id="1aa99-124">Weisen Sie dem Benutzer einen **Ort** zu und stellen Sie Intune auf **ein**.</span><span class="sxs-lookup"><span data-stu-id="1aa99-124">Assign the user a **Location**, then switch Intune to **on**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="1aa99-125">Dadurch wird eine Ihrer Lizenzen für den Benutzer verwendet.</span><span class="sxs-lookup"><span data-stu-id="1aa99-125">This uses one of your licenses for this user.</span></span> <span data-ttu-id="1aa99-126">Wenn Sie ihre dynamische Umgebung verwenden, können Sie später die Verwendung dieser Lizenz rückgängig machen, um Sie einem echten Benutzer zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="1aa99-126">If you are using your live environment, you can turn off using this license later to reassign it to a real user.</span></span>

5. <span data-ttu-id="1aa99-127">Wählen Sie **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="1aa99-127">Select **Save**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="1aa99-128">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="1aa99-128">Next steps</span></span>

<span data-ttu-id="1aa99-129">[Erste Schritte mit Gruppen:](get-started-groups.md) Organisieren Sie Benutzer in Gruppen, um die Richtlinien und Apps leichter zu verwalten, auf die sie zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="1aa99-129">[Get started with groups](get-started-groups.md) - Organize users into groups to make it easier to manage the policies and apps that they can access.</span></span>
