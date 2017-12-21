---
title: "App-Zugriff für Exchange Online"
description: "In diesem Thema wird beschrieben, wie Sie eine Richtlinie für bedingten Zugriff für MAM-Apps konfigurieren können."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 10/15/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f2cd1a1f-fd29-4081-8dfa-c40993a107d5
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: chrisgre
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 2528bee69ca93ae63219e89f2acf9582bca653c1
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2017
---
# <a name="create-an-exchange-online-conditional-access-to-only-allow-apps-supported-by-mam"></a><span data-ttu-id="52a3f-103">Erstellen eines bedingten Zugriffs für Exchange Online, um nur Apps zuzulassen, die von MAM unterstützt werden</span><span class="sxs-lookup"><span data-stu-id="52a3f-103">Create an Exchange Online conditional access to only allow apps supported by MAM</span></span>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="52a3f-104">Dieses Thema bietet Ihnen eine ausführliche Anleitung, wie Sie den bedingten Zugriff für Exchange Online einrichten, um nur mobile Apps zuzulassen, die App-Schutzrichtlinie für Intune unterstützen.</span><span class="sxs-lookup"><span data-stu-id="52a3f-104">This topic gives you step-by-step instructions on how to set up conditional access for  Exchange Online to only allow mobile apps that support Intune app protection policies.</span></span>


## <a name="create-an-exchange-online-policy"></a><span data-ttu-id="52a3f-105">Erstellen einer Exchange Online-Richtlinie</span><span class="sxs-lookup"><span data-stu-id="52a3f-105">Create an Exchange Online policy</span></span>
1.  <span data-ttu-id="52a3f-106">Melden Sie sich beim [Azure-Portal](https://portal.azure.com) an, das das App-Zugriffsfeature enthält.</span><span class="sxs-lookup"><span data-stu-id="52a3f-106">Sign into the [Azure portal](https://portal.azure.com) that includes the app access feature.</span></span> <span data-ttu-id="52a3f-107">Wenn Sie noch nicht mit dem Azure-Portal vertraut sind, lesen Sie das Thema [Azure-Portal für App-Schutzrichtlinien](azure-portal-for-microsoft-intune-mam-policies.md).</span><span class="sxs-lookup"><span data-stu-id="52a3f-107">If you are new to the Azure portal experience read the [Azure portal for app protection policies](azure-portal-for-microsoft-intune-mam-policies.md) topic.</span></span>

2.  <span data-ttu-id="52a3f-108">Wählen Sie **Weitere Dienste** aus, und geben Sie „Intune“ ein.</span><span class="sxs-lookup"><span data-stu-id="52a3f-108">Choose **More services**, and type: "Intune".</span></span>

3.  <span data-ttu-id="52a3f-109">Wählen Sie **Intune-Schutz für Apps** aus.</span><span class="sxs-lookup"><span data-stu-id="52a3f-109">Choose **Intune App Protection**.</span></span>

4.  <span data-ttu-id="52a3f-110">Wählen Sie auf dem Blatt **Mobile Anwendungsverwaltung mit Intune** **Alle Einstellungen** aus.</span><span class="sxs-lookup"><span data-stu-id="52a3f-110">On the **Intune mobile application management** blade choose **All Settings**.</span></span>

5.  <span data-ttu-id="52a3f-111">Wählen Sie im Abschnitt **Bedingter Zugriff** **Exchange Online** aus.</span><span class="sxs-lookup"><span data-stu-id="52a3f-111">On the **Conditional access** section, choose **Exchange Online**.</span></span>

    ![Screenshot des Blatts „Einstellungen“, das den Abschnitt „Bedingter Zugriff“ anzeigt, wobei die Option „Exchange Online“ hervorgehoben ist](../media/MAM-conditional-access-1.png)

6. <span data-ttu-id="52a3f-113">Wählen Sie auf dem Blatt **Zulässige Apps** die Option **Allow apps that support Intune app policies** (Apps zulassen, die Intune-App-Richtlinien unterstützen), um nur Apps zuzulassen, die von Intune-App-Schutzrichtlinien unterstützt werden, damit sie auf Exchange Online zugreifen können.</span><span class="sxs-lookup"><span data-stu-id="52a3f-113">On the **Allowed apps** blade, choose the **Allow apps that support Intune app policies** option to allow only apps that are supported by Intune app protection policies to have the ability to access Exchange Online.</span></span> <span data-ttu-id="52a3f-114">Wenn Sie diese Option auswählen, wird die Liste der unterstützten Apps angezeigt.</span><span class="sxs-lookup"><span data-stu-id="52a3f-114">When you select this option, the list of supported apps is displayed.</span></span>

    >[!NOTE]
    ><span data-ttu-id="52a3f-115">Alle E-Mail-Clients von Exchange Active Sync, einschließlich der integrierten E-Mail-Clients unter iOS und >Android, die eine Verbindung mit Exchange Online herstellen, werden daran gehindert, >E-Mails zu senden oder zu empfangen.</span><span class="sxs-lookup"><span data-stu-id="52a3f-115">All Exchange Active Sync mail clients, including the built-in mail clients on iOS and >Android that connect to Exchange Online, will be prevented from sending or receiving >email.</span></span> <span data-ttu-id="52a3f-116">Benutzer erhalten stattdessen eine einzige E-Mail, die sie darüber informiert, dass sie die >Outlook-E-Mail-App verwenden müssen.</span><span class="sxs-lookup"><span data-stu-id="52a3f-116">Users will instead receive a single email informing them that they need to use the >Outlook mail app.</span></span>

7. <span data-ttu-id="52a3f-117">Um diese Richtlinie auf Benutzer anzuwenden, öffnen Sie das Blatt **Eingeschränkte Benutzergruppen**, und wählen Sie **Benutzergruppe hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="52a3f-117">To apply this policy to users, open the **Restricted user groups** blade, and choose **Add user group**.</span></span> <span data-ttu-id="52a3f-118">Wählen Sie mindestens eine Benutzergruppe aus, auf die diese Richtlinie angewendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="52a3f-118">Select one or more user groups that should get this policy.</span></span>

    ![Screenshot des Blatts „Eingeschränkte Benutzergruppen“ mit hervorgehobener Option „Benutzergruppe hinzufügen“](../media/mam-ca-add-user-group.png)

8. <span data-ttu-id="52a3f-120">Möglicherweise möchten Sie, dass einige Benutzer in der Benutzergruppe, die Sie im vorherigen Schritt ausgewählt haben, nicht von dieser Richtlinie betroffen sind.</span><span class="sxs-lookup"><span data-stu-id="52a3f-120">You may want some users in the user group you selected in the previous step not to be affected by this policy.</span></span> <span data-ttu-id="52a3f-121">In solchen Fällen fügen Sie die Gruppe der Benutzer der Liste der ausgenommenen Benutzergruppen hinzu.</span><span class="sxs-lookup"><span data-stu-id="52a3f-121">In such cases, add the group of users to the exempted user groups list.</span></span> <span data-ttu-id="52a3f-122">Wählen Sie auf dem Blatt **Exchange Online** **Exempted user groups** (Ausgenommene Benutzergruppen) aus.</span><span class="sxs-lookup"><span data-stu-id="52a3f-122">From the **Exchange Online** blade, choose **Exempted user groups**.</span></span> <span data-ttu-id="52a3f-123">Wählen Sie **Benutzergruppe hinzufügen** aus, um die Liste der Benutzergruppen zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="52a3f-123">Choose **Add user group** to open the list of user groups.</span></span> <span data-ttu-id="52a3f-124">Wählen Sie die Gruppen aus, die Sie von dieser Richtlinie ausnehmen möchten.</span><span class="sxs-lookup"><span data-stu-id="52a3f-124">Select the groups you want to exempt from this policy.</span></span>  

## <a name="modify-an-existing-policy"></a><span data-ttu-id="52a3f-125">Bearbeiten einer vorhandenen Richtlinie</span><span class="sxs-lookup"><span data-stu-id="52a3f-125">Modify an existing policy</span></span>
### <a name="add-or-delete-user-groups"></a><span data-ttu-id="52a3f-126">Hinzufügen oder Löschen von Benutzergruppen</span><span class="sxs-lookup"><span data-stu-id="52a3f-126">Add or delete user groups</span></span>

<span data-ttu-id="52a3f-127">Um aus der Liste der **eingeschränkten Benutzergruppen** **eine Benutzergruppe zu löschen**, öffnen Sie das Blatt **Eingeschränkte Benutzergruppen**, markieren die Benutzergruppe, die Sie löschen möchten, und klicken auf die **Schaltfläche mit den drei Punkten (...)**, um die Option **Löschen** anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="52a3f-127">To **delete a user group** from the **restricted user groups** list, open the **Restricted user groups** blade, highlight the user group you want to delete, and click on the **ellipses(...)** to see the **Delete** option.</span></span> <span data-ttu-id="52a3f-128">Wählen Sie **Löschen** aus, um die Benutzergruppe aus der Liste zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="52a3f-128">Choose **Delete** to remove the user group from the list.</span></span> <span data-ttu-id="52a3f-129">Sie können genauso vorgehen, um eine Benutzergruppe aus der Liste **exempted user group** (Ausgenommene Benutzergruppen) zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="52a3f-129">You can follow the same procedure to remove a user group from the **exempted user group** list.</span></span>


## <a name="next-steps"></a><span data-ttu-id="52a3f-130">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="52a3f-130">Next steps</span></span>
[<span data-ttu-id="52a3f-131">Blockieren von Apps, die über keine moderne Authentifizierung verfügen</span><span class="sxs-lookup"><span data-stu-id="52a3f-131">Block apps that do not have modern authentication</span></span>](block-apps-with-no-modern-authentication.md)
### <a name="see-also"></a><span data-ttu-id="52a3f-132">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="52a3f-132">See also</span></span>
[<span data-ttu-id="52a3f-133">Protect app data with app protection policies (Schützen von App-Daten mithilfe von App-Schutzrichtlinien)</span><span class="sxs-lookup"><span data-stu-id="52a3f-133">Protect app data with app protection policies</span></span>](protect-app-data-using-mobile-app-management-policies-with-microsoft-intune.md)
