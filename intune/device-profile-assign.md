---
title: "So weisen Sie Geräteprofile mit Intune zu"
titlesuffix: Azure portal
description: "Nachdem Sie ein Intune-Geräteprofil erstellt haben, lesen Sie dieses Thema, um zu erfahren, wie Sie es Geräten zuweisen."
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 07/05/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f6f5414d-0e41-42fc-b6cf-e7ad76e1e06d
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 6ab9f8709c13b5efe37b2a4787f3c4803be08b68
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2017
---
# <a name="how-to-assign-microsoft-intune-device-profiles"></a><span data-ttu-id="8b78f-103">Zuweisen von Microsoft Intune-Geräteprofilen</span><span class="sxs-lookup"><span data-stu-id="8b78f-103">How to assign Microsoft Intune device profiles</span></span>

## <a name="assign-a-device-profile"></a><span data-ttu-id="8b78f-104">Zuweisen eines Geräteprofils</span><span class="sxs-lookup"><span data-stu-id="8b78f-104">Assign a device profile</span></span>

1. <span data-ttu-id="8b78f-105">Melden Sie sich beim Azure-Portal an.</span><span class="sxs-lookup"><span data-stu-id="8b78f-105">Sign into the Azure portal.</span></span>
2. <span data-ttu-id="8b78f-106">Wählen Sie **Weitere Dienste** > **Überwachung und Verwaltung** > **Intune** aus.</span><span class="sxs-lookup"><span data-stu-id="8b78f-106">Choose **More Services** > **Monitoring + Management** > **Intune**.</span></span>
3. <span data-ttu-id="8b78f-107">Wählen Sie auf dem Blatt **Intune** die Option **Gerätekonfiguration** aus.</span><span class="sxs-lookup"><span data-stu-id="8b78f-107">On the **Intune** blade, choose **Device configuration**.</span></span>
1. <span data-ttu-id="8b78f-108">Wählen Sie auf dem Blatt **Gerätekonfiguration** die Option **Verwalten** > **Profile** aus.</span><span class="sxs-lookup"><span data-stu-id="8b78f-108">On the **Device configuration** blade, choose **Manage** > **Profiles**.</span></span>
2. <span data-ttu-id="8b78f-109">Wählen Sie auf dem Blatt mit der Profilliste das Profil, das Sie verwalten möchten, und dann auf dem Blatt <*Profilname*> **Berichte** die Option **Verwalten** > **Zuweisungen** aus.</span><span class="sxs-lookup"><span data-stu-id="8b78f-109">In the list of profiles blade, choose the profile you want to manage, and then, on the <*profile name*> **Reports** blade, choose **Manage** > **Assignments**.</span></span>
3. <span data-ttu-id="8b78f-110">Wählen Sie auf dem nächsten Blatt entweder die Option **Einschließen** (zum Einschließen von Gruppen) oder die Option **Ausschließen** (zum Ausschließen von Gruppen) aus. Wählen Sie anschließend **Gruppen auswählen** aus.</span><span class="sxs-lookup"><span data-stu-id="8b78f-110">On the next blade, choose either **Include** (to include groups) or **Exclude** (to exclude groups), then choose **Select groups**.</span></span>
<span data-ttu-id="8b78f-111">![Einschließen und Ausschließen von Gruppen aus einer Profilzuweisung.](./media/group-include-exclude.png)</span><span class="sxs-lookup"><span data-stu-id="8b78f-111">![Include and exclude groups from a profile assignment.](./media/group-include-exclude.png)</span></span>
4. <span data-ttu-id="8b78f-112">Wählen Sie auf dem Blatt **Gruppen auswählen** diejenigen Azure AD-Gruppen aus, die Sie in die Zuordnung einschließen oder aus der Zuordnung ausschließen möchten.</span><span class="sxs-lookup"><span data-stu-id="8b78f-112">On the **Select groups** blade, choose the Azure AD groups, which you want to include in, or exclude from the assignment.</span></span> <span data-ttu-id="8b78f-113">Sie können **STRG** gedrückt halten, um mehrere Gruppen auswählen.</span><span class="sxs-lookup"><span data-stu-id="8b78f-113">You can hold down the **CTRL** key to select multiple groups.</span></span>
4. <span data-ttu-id="8b78f-114">Wenn Sie fertig sind, wählen Sie auf dem Blatt **Gruppen auswählen** die Option **Auswählen** aus.</span><span class="sxs-lookup"><span data-stu-id="8b78f-114">When you are done, on the **Select groups** blade, choose **Select**.</span></span>



## <a name="how-to-exclude-groups-from-a-device-profile-assignment"></a><span data-ttu-id="8b78f-115">Ausschließen von Gruppen aus einer Geräteprofilzuweisung</span><span class="sxs-lookup"><span data-stu-id="8b78f-115">How to exclude groups from a device profile assignment</span></span>

<span data-ttu-id="8b78f-116">Mit Intune-Gerätekonfigurationsprofilen können Sie Gruppen aus der Richtlinienzuweisung ausschließen.</span><span class="sxs-lookup"><span data-stu-id="8b78f-116">Intune device configuration profiles let you exclude groups from policy assignment.</span></span> <span data-ttu-id="8b78f-117">So könnten Sie z.B. der Gruppe **Alle Unternehmensbenutzer** ein Geräteprofil zuweisen und gleichzeitig alle Mitglieder der Gruppe **Oberes Management** ausschließen.</span><span class="sxs-lookup"><span data-stu-id="8b78f-117">For example, you could assign a device profile to the **All corporate users** group, but exclude any members of the **Senior Management Staff** group.</span></span>

<span data-ttu-id="8b78f-118">Achten Sie beim Ausschließen von Gruppen aus einer Zuweisung darauf, dass Sie nur Benutzer oder nur Gerätegruppen ausschließen und keine Kombination aus verschiedenen Gruppen.</span><span class="sxs-lookup"><span data-stu-id="8b78f-118">When you exclude groups from an assignment, exclude only user, or only device groups, not a mixture of groups.</span></span> <span data-ttu-id="8b78f-119">Intune berücksichtigt beim Ausschließen von Gruppen keine Zuweisung eines Benutzers zu einem Gerät.</span><span class="sxs-lookup"><span data-stu-id="8b78f-119">Intune does not take into account any user to device association when excluding groups.</span></span> <span data-ttu-id="8b78f-120">Es ist unwahrscheinlich, dass das Einschließen von Benutzergruppen und gleichzeitige Ausschließen von Gerätegruppen die von Ihnen gewünschten Ergebnisse liefert.</span><span class="sxs-lookup"><span data-stu-id="8b78f-120">Including user groups while excluding device groups is unlikely to produce the results you need.</span></span> <span data-ttu-id="8b78f-121">Bei einer Kombination aus verschiedenen Gruppen oder bei anderen Konflikten hat die Funktion „Einschließen“ Vorrang vor der Funktion „Ausschließen“.</span><span class="sxs-lookup"><span data-stu-id="8b78f-121">In case where mixed groups are used, or there are other conflicts, inclusion takes precedence over exclusion.</span></span>

<span data-ttu-id="8b78f-122">Beispiel: Sie möchten allen Geräten in Ihrem Unternehmen, mit Ausnahme von Kioskgeräten, ein Geräteprofil zuweisen.</span><span class="sxs-lookup"><span data-stu-id="8b78f-122">For example, you want to assign a device profile to all devices in your organization, except kiosk devices.</span></span> <span data-ttu-id="8b78f-123">Nun schließen Sie die Gruppe **Alle Benutzer** ein und gleichzeitig die Gruppe **Alle Geräte** aus.</span><span class="sxs-lookup"><span data-stu-id="8b78f-123">You include the **All Users** group, but exclude the **All Devices** group.</span></span>

<span data-ttu-id="8b78f-124">In diesem Fall erhalten alle Benutzer und ihre Geräte die Richtlinie, selbst wenn das Gerät des Benutzers der Gruppe **Alle Geräte** angehört.</span><span class="sxs-lookup"><span data-stu-id="8b78f-124">In this case, all your users and their devices get the policy, even if the user’s device is part of the **All Devices** group.</span></span> 

<span data-ttu-id="8b78f-125">Die Ausschließen-Funktion wertet nur direkte Mitglieder der Gruppen aus. Sie beinhaltet keine Geräte, die einem Benutzer zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="8b78f-125">Exclusion only evaluates the direct members of the groups, and does not include devices that are associated with a user.</span></span> <span data-ttu-id="8b78f-126">Geräte, die keinen Benutzer besitzen, erhalten die Richtlinie dagegen nicht, da sie der Gruppe **Alle Benutzer** nicht zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="8b78f-126">However, devices that don't have a user do not get the policy because they have no association to the **All Users** group.</span></span> 

<span data-ttu-id="8b78f-127">Wenn Sie **Alle Geräte** einschließen und gleichzeitig **Alle Benutzer** ausschließen, erhalten alle Geräte die Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="8b78f-127">If you include **All Devices**, but exclude **All Users**, all the devices receive the policy.</span></span> <span data-ttu-id="8b78f-128">Damit sollten eigentlich alle Geräte mit einem zugeordneten Benutzer von der Richtlinie ausgeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="8b78f-128">The intent in this case is to exclude devices that have an associated user from this policy.</span></span> <span data-ttu-id="8b78f-129">Dies gelingt jedoch nicht, da die Ausschließen-Funktion nur direkte Mitglieder von Gruppen vergleicht.</span><span class="sxs-lookup"><span data-stu-id="8b78f-129">However, it does not because the exclusion feature only compares direct group members.</span></span> 

>[!Tip]
><span data-ttu-id="8b78f-130">Die Ausschließen-Funktion ist für Konformitätsrichtlinien oder App-Zuweisungen derzeit nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="8b78f-130">Exclusions are not currently available for compliance policies or app assignment.</span></span> <span data-ttu-id="8b78f-131">Zum Ausschließen von Mitgliedern aus einer Zuordnung können Sie die Zuweisungsabsichten „Verfügbar“ und „Nicht verfügbar“ verwenden.</span><span class="sxs-lookup"><span data-stu-id="8b78f-131">To exclude members from an assignment, you can use the Available, and Not applicable assignment intents.</span></span> <span data-ttu-id="8b78f-132">Beispiel: Sie weisen der Gruppe **Alle Unternehmensbenutzer** eine App mit der Zuweisungsabsicht **Verfügbar** zu sowie der Gruppe **Oberes Management** mit der Zuweisungsabsicht **Nicht verfügbar**.</span><span class="sxs-lookup"><span data-stu-id="8b78f-132">For example, you assign an app to **All corporate users** with the **Available** intent, and to **Senior Management Staff** with the **Not applicable** intent.</span></span> <span data-ttu-id="8b78f-133">Die App ist nun allen Benutzern *außer* den Benutzern der Gruppe **Oberes Management** zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="8b78f-133">the app is assigned to all users *except* users in the **Senior Management Staff** group.</span></span> <span data-ttu-id="8b78f-134">Weisen Sie die App hingegen der Gruppe **Alle Unternehmensbenutzer** mit der Zuweisungsabsicht **Erforderlich** zu, werden die Benutzer der Gruppe **Oberes Management** nicht ausgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="8b78f-134">If you assign the app to **All corporate users** with the **Required** intent, the users in the **Senior Management Staff** group are not excluded.</span></span>
 
    
## <a name="next-steps"></a><span data-ttu-id="8b78f-135">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="8b78f-135">Next steps</span></span>
<span data-ttu-id="8b78f-136">Weitere Informationen zum Überwachen der Zuweisungen von Geräteprofilen finden Sie unter [Überwachen von Geräteprofilen](device-profile-monitor.md).</span><span class="sxs-lookup"><span data-stu-id="8b78f-136">See [How to monitor device profiles](device-profile-monitor.md) for information to help you monitor device profile assignments.</span></span>
