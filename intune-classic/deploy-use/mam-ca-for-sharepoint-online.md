---
title: "Erstellen einer App-basierten bedingten Zugriffsrichtlinie für SharePoint Online"
description: 
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 05/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 531b09bb-ddfd-498f-8ee3-6675d2466208
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: chrisgre
ms.suite: ems
ms.openlocfilehash: 9d16da3bbbeaaa768d5e2a01b403c227bb194354
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2017
---
# <a name="set-up-app-based-conditional-access-ca-policies-for-sharepoint-online"></a><span data-ttu-id="12597-102">Einrichten von App-basierten bedingten Zugriffsrichtlinien für SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="12597-102">Set up app-based conditional access (CA) policies for SharePoint Online</span></span>

[!INCLUDE[note for both-portals](../includes/note-for-both-portals.md)]

<span data-ttu-id="12597-103">Dieses Thema enthält Anweisungen zum Einrichten von App-basierten bedingten Zugriffsrichtlinien für SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="12597-103">This topic provides guidance on how to set up app-based conditional access policy for SharePoint Online.</span></span> <span data-ttu-id="12597-104">App-basierte bedingte Zugriffsrichtlinien unterstützen Administratoren dabei, nur mobile Apps zuzulassen, auf die App-Schutzrichtlinien von Intune angewendet wurden.</span><span class="sxs-lookup"><span data-stu-id="12597-104">App-based CA helps admins to only allow mobile apps that have Intune app protection policies applied to.</span></span>

## <a name="to-create-the-app-based-ca-policy-for-sharepoint-online"></a><span data-ttu-id="12597-105">So erstellen Sie eine App-basierte bedingte Zugriffsrichtlinie für SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="12597-105">To create the app-based CA policy for SharePoint Online</span></span>

1. <span data-ttu-id="12597-106">Navigieren Sie zum [Azure-Portal](https://portal.azure.com), und melden Sie sich mit Ihren Anmeldeinformationen an.</span><span class="sxs-lookup"><span data-stu-id="12597-106">Go the [Azure portal](https://portal.azure.com) and sign in with your credentials.</span></span>

    > [!NOTE]
    > <span data-ttu-id="12597-107">Wenn Sie noch nicht mit dem Azure-Portal vertraut sind, lesen Sie das Thema [Azure-Portal für App-Schutzrichtlinien](azure-portal-for-microsoft-intune-mam-policies.md).</span><span class="sxs-lookup"><span data-stu-id="12597-107">If you're new to the Azure portal experience read the [Azure portal for app protection policies](azure-portal-for-microsoft-intune-mam-policies.md) topic.</span></span>

2. <span data-ttu-id="12597-108">Wählen Sie im linken Menü **Weitere Dienste** aus, und geben Sie in das Filtertextfeld die Zeichenfolge **Intune** ein.</span><span class="sxs-lookup"><span data-stu-id="12597-108">Choose **More services** from the left menu, then type **Intune** in the text box filter.</span></span>

3. <span data-ttu-id="12597-109">Wählen Sie **Intune-Schutz für Apps** > **Mobile Anwendungsverwaltung mit Intune** > **Alle Einstellungen** aus.</span><span class="sxs-lookup"><span data-stu-id="12597-109">Choose **Intune App Protection** > **Intune mobile application management** > **All Settings**.</span></span>

4. <span data-ttu-id="12597-110">Wählen Sie auf dem Blatt „Mobile Anwendungsverwaltung mit Intune“ die Kachel „SharePoint Online“ aus.</span><span class="sxs-lookup"><span data-stu-id="12597-110">On the Intune mobile application management blade, choose the SharePoint Online tile.</span></span>

5. <span data-ttu-id="12597-111">Wählen Sie auf dem Blatt **Zulässige Apps** die Option **Apps zulassen, die Intune-App-Richtlinien unterstützen**, um nur Apps zuzulassen, die von Intune-App-Schutzrichtlinien unterstützt werden.</span><span class="sxs-lookup"><span data-stu-id="12597-111">On the **Allowed apps** blade, choose **Allow apps that support Intune app policies** option to allow only apps that are supported by Intune app protection policies.</span></span>

    > [!NOTE] 
    > <span data-ttu-id="12597-112">Bei Auswahl der Option, nur Apps zuzulassen, die von App-Schutzrichtlinien von Intune unterstützt werden, wird eine Liste der **unterstützten** Apps angezeigt.</span><span class="sxs-lookup"><span data-stu-id="12597-112">When you select the option to only allow apps that are supported by Intune app protection policies, a list containing **only** the supported apps is displayed.</span></span>

    ![Screenshot des Blatts der zulässigen Apps mit der Liste der Apps](../media/mam-ca-spo-allowed-apps.png)

## <a name="to-assign-app-based-ca-policies-to-your-users"></a><span data-ttu-id="12597-114">So weisen Sie App-basierte bedingte Zugriffsrichtlinien zu Benutzern zu</span><span class="sxs-lookup"><span data-stu-id="12597-114">To assign app-based CA policies to your users</span></span>

1. <span data-ttu-id="12597-115">Öffnen Sie das Blatt **Eingeschränkte Benutzergruppen**, und wählen Sie dann **Benutzergruppe hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="12597-115">Open the **Restricted user groups** blade, then choose **Add user group**.</span></span>

2. <span data-ttu-id="12597-116">Wählen Sie mindestens eine Benutzergruppe aus, auf die diese Richtlinie angewendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="12597-116">Select one or more user groups that should get this policy.</span></span>

    ![Screenshot des Blatts „Eingeschränkte Benutzergruppen“ mit hervorgehobener Option „Benutzergruppe hinzufügen“](../media/mam-ca-spo-restricted-groups.png)

    > [!IMPORTANT] 
    > <span data-ttu-id="12597-118">Möglicherweise möchten Sie, dass einige Benutzer in der Benutzergruppe, die Sie im vorherigen Schritt ausgewählt haben, nicht von dieser Richtlinie betroffen sind.</span><span class="sxs-lookup"><span data-stu-id="12597-118">You may want some users in the user group you selected in the previous step not to be affected by this policy.</span></span> <span data-ttu-id="12597-119">In solchen Fällen fügen Sie die Gruppe der Benutzer der Liste der ausgenommenen Benutzergruppen hinzu.</span><span class="sxs-lookup"><span data-stu-id="12597-119">In such cases, add the group of users to the exempted user groups list.</span></span> 

3. <span data-ttu-id="12597-120">Wählen Sie auf dem Blatt **SharePoint Online** die Option **Exempted user groups** (Ausgenommene Benutzergruppen) und dann **Benutzergruppe hinzufügen** aus, um die Liste der Benutzergruppen zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="12597-120">On the **SharePoint Online** blade, choose **Exempted user groups**, then choose **Add user group** to open the list of user groups.</span></span>

4. <span data-ttu-id="12597-121">Wählen Sie die Gruppen aus, die Sie von dieser Richtlinie ausnehmen möchten.</span><span class="sxs-lookup"><span data-stu-id="12597-121">Select the groups you want to exempt from this policy.</span></span>  

## <a name="to-modify-or-delete-user-groups-from-an-existing-app-based-ca-policy"></a><span data-ttu-id="12597-122">So ändern oder löschen Sie Benutzergruppen einer vorhandenen App-basierten bedingten Zugriffsrichtlinie</span><span class="sxs-lookup"><span data-stu-id="12597-122">To modify or delete user groups from an existing app-based CA policy</span></span>

1. <span data-ttu-id="12597-123">Öffnen Sie das Blatt **Eingeschränkte Benutzergruppen**, und markieren Sie die Benutzergruppe, die Sie löschen möchten.</span><span class="sxs-lookup"><span data-stu-id="12597-123">Open the **Restricted user groups** blade, then highlight the user group you want to delete.</span></span>
2. <span data-ttu-id="12597-124">Klicken Sie auf die Auslassungspunkte, um die Optionen für den Löschvorgang anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="12597-124">Click on the ellipse to see the delete options.</span></span>
3. <span data-ttu-id="12597-125">Wählen Sie **Löschen** aus, um die Benutzergruppe aus der Liste zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="12597-125">Choose **Delete** to remove the user group from the list.</span></span>

> [!NOTE] 
> <span data-ttu-id="12597-126">Sie können die Schritte befolgen, um eine Benutzergruppe aus der Liste **Exempted user groups** (Ausgenommene Benutzergruppen) zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="12597-126">You can follow the steps procedure to remove a user group from the **Exempted user group** list.</span></span>

## <a name="next-steps"></a><span data-ttu-id="12597-127">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="12597-127">Next steps</span></span>

[<span data-ttu-id="12597-128">Blockieren von Apps, die keine moderne Authentifizierung verwenden</span><span class="sxs-lookup"><span data-stu-id="12597-128">Block apps that do not use modern authentication</span></span>](block-apps-with-no-modern-authentication.md)

## <a name="see-also"></a><span data-ttu-id="12597-129">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="12597-129">See also</span></span>

[<span data-ttu-id="12597-130">Protect app data with app protection policies (Schützen von App-Daten mithilfe von App-Schutzrichtlinien)</span><span class="sxs-lookup"><span data-stu-id="12597-130">Protect app data with app protection policies</span></span>](protect-app-data-using-mobile-app-management-policies-with-microsoft-intune.md)

[<span data-ttu-id="12597-131">Konfigurieren des App-basierten bedingten Zugriffs für Exchange Online</span><span class="sxs-lookup"><span data-stu-id="12597-131">Configure app-based CA for Exchange Online</span></span>](mam-ca-for-exchange-online.md)
