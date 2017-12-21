---
title: "Festlegen von Registrierungseinschränkungen in Intune"
titlesuffix: Azure portal
description: "Schränken Sie die Registrierung plattformbezogen ein, und legen Sie in Intune einen Grenzwert für die Geräteregistrierung fest. \""
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 10/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f0a2b858-a824-4598-ab81-bdd8e62ac3b3
ms.reviewer: amyros
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 8ddf5cc624685e684973b0e4ee85de609845f3bd
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2017
---
# <a name="add-groups-in-intune"></a><span data-ttu-id="8859a-104">Hinzufügen von Gruppen in Intune</span><span class="sxs-lookup"><span data-stu-id="8859a-104">Add groups in Intune</span></span>
<span data-ttu-id="8859a-105">Intune verwendet Azure Active Directory-Gruppen (AD) zur Verwaltung von Geräten und Benutzern.</span><span class="sxs-lookup"><span data-stu-id="8859a-105">Intune uses Azure Active Directory (AD) groups to manage devices and users.</span></span> <span data-ttu-id="8859a-106">Als Intune-Administrator können Sie Gruppen entsprechend der Anforderungen Ihrer Organisation einrichten.</span><span class="sxs-lookup"><span data-stu-id="8859a-106">As an Intune admin, you can set up groups to suit your organizational needs.</span></span> <span data-ttu-id="8859a-107">Sie können Gruppen erstellen, um Benutzer oder Geräte nach geografischem Standort, Abteilung oder Hardwareeigenschaften zu organisieren.</span><span class="sxs-lookup"><span data-stu-id="8859a-107">Create groups to organize users or devices by geographic location, department, or hardware characteristics.</span></span> <span data-ttu-id="8859a-108">Sie können Gruppen zur bedarfsgerechten Verwaltung von Aufgaben verwenden.</span><span class="sxs-lookup"><span data-stu-id="8859a-108">Use groups to manage tasks at scale.</span></span> <span data-ttu-id="8859a-109">So können Sie beispielsweise Richtlinien für viele Benutzer festlegen oder Apps für eine Reihe von Geräten bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="8859a-109">For example, you can set policies for many users or  deploy apps to a set of devices.</span></span>

<span data-ttu-id="8859a-110">In diesem Thema wird das Hinzufügen von Gruppen für die Verwendung in Intune erläutert.</span><span class="sxs-lookup"><span data-stu-id="8859a-110">This topic explains how to add groups for use in Intune.</span></span>

<span data-ttu-id="8859a-111">Sie können die folgenden Gruppentypen hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="8859a-111">You can add the following types of groups:</span></span>
- <span data-ttu-id="8859a-112">**Zugewiesene Gruppen**: Manuelles Hinzufügen von Benutzern oder Geräten in eine statische Gruppe</span><span class="sxs-lookup"><span data-stu-id="8859a-112">**Assigned groups** - Manually add users or devices into a static group</span></span>
- <span data-ttu-id="8859a-113">**Dynamische Gruppen**: (Mit Azure Active Directory Premium) Dynamisches Erstellen von Benutzer- oder Gerätegruppen, die durch einfache oder erweiterte Regeln definiert werden</span><span class="sxs-lookup"><span data-stu-id="8859a-113">**Dynamic groups** - (Using Azure Active Directory Premium) Let you dynamically build either user or device groups defined with either simple or advanced rules</span></span>

## <a name="add-a-new-group"></a><span data-ttu-id="8859a-114">Hinzufügen einer neuen Gruppe</span><span class="sxs-lookup"><span data-stu-id="8859a-114">Add a new group</span></span>

<span data-ttu-id="8859a-115">Führen Sie die folgenden Schritte aus, um eine neue Gruppe zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="8859a-115">Use the following steps to create a new group.</span></span>
1. <span data-ttu-id="8859a-116">Wechseln Sie im Azure-Portal zu **Gruppen**, und wählen Sie dann auf dem Blatt **Alle Gruppen** die Option **Neue Gruppe** aus.</span><span class="sxs-lookup"><span data-stu-id="8859a-116">In the Azure portal, go **Groups** and then choose **New group** in the **All groups** blade.</span></span>
  <span data-ttu-id="8859a-117">![Screenshot des Azure-Portals mit ausgewählter Option „Neue Gruppe“](./media/groups-add-new.png)</span><span class="sxs-lookup"><span data-stu-id="8859a-117">![Screenshot of the Azure portal with New Group selected](./media/groups-add-new.png)</span></span>
2. <span data-ttu-id="8859a-118">Geben Sie den **Namen** und die **Beschreibung** der neuen Gruppe an.</span><span class="sxs-lookup"><span data-stu-id="8859a-118">Specify the **Name** and **Description** of the new group.</span></span> <span data-ttu-id="8859a-119">Diese Eigenschaften werden nur im Verwaltungsportal und nicht den Benutzern angezeigt.</span><span class="sxs-lookup"><span data-stu-id="8859a-119">These properties only appear in the management portal and are not displayed to users.</span></span>

3. <span data-ttu-id="8859a-120">Wählen Sie den **Mitgliedschaftstyp** aus:</span><span class="sxs-lookup"><span data-stu-id="8859a-120">Choose **Membership type**:</span></span>
  - <span data-ttu-id="8859a-121">**Zugewiesen**: Zur Erstellung einer Gruppe mit manuell zugewiesenen Mitgliedern.</span><span class="sxs-lookup"><span data-stu-id="8859a-121">**Assigned** to create group with manually assigned members.</span></span> <span data-ttu-id="8859a-122">Weitere Informationen zu [zugewiesenen Azure AD-Gruppen](https://docs.microsoft.com/azure/active-directory/active-directory-groups-create-azure-portal).</span><span class="sxs-lookup"><span data-stu-id="8859a-122">Learn more about [Azure AD assigned groups](https://docs.microsoft.com/azure/active-directory/active-directory-groups-create-azure-portal).</span></span>
  - <span data-ttu-id="8859a-123">**Dynamischer Benutzer**: Zur Erstellung einer Benutzergruppe, die durch eine **Dynamische Abfrage** definiert wird.</span><span class="sxs-lookup"><span data-stu-id="8859a-123">**Dynamic User** to create a user group defined with a **Dynamic query**.</span></span>
  - <span data-ttu-id="8859a-124">**Dynamisches Gerät**: Zur Erstellung einer Gerätegruppe, die durch eine **Dynamische Abfrage** definiert wird.</span><span class="sxs-lookup"><span data-stu-id="8859a-124">**Dynamic Device** to create a device group defined with a **Dynamic query**.</span></span>

  ![Screenshot der Intune-Gruppeneigenschaften mit Name, Beschreibung, Mitgliedschaftstyp, Option „Office-Features aktivieren“ und Mitgliedern](./media/groups-add-properties.png)

  <span data-ttu-id="8859a-126">Mit Azure AD können Sie dynamische Gruppen auf der Grundlage von Regeln erstellen, die die Mitgliedschaft definieren.</span><span class="sxs-lookup"><span data-stu-id="8859a-126">Azure AD lets you create dynamic groups based on rules that define membership.</span></span> <span data-ttu-id="8859a-127">Weitere Informationen zum [Erstellen von attributbasierten dynamischen Gruppen](https://docs.microsoft.com/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal).</span><span class="sxs-lookup"><span data-stu-id="8859a-127">Learn to [create attribute-based dynamic groups](https://docs.microsoft.com/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal).</span></span>

4. <span data-ttu-id="8859a-128">Sie können die Option **Office-Features aktivieren** auswählen, um Mitgliedern von Benutzergruppen Zugriff auf freigegebene Office 365-Apps zu gewähren.</span><span class="sxs-lookup"><span data-stu-id="8859a-128">You can select **Enable Office features** to give user group members access to shared Office 365 apps.</span></span> <span data-ttu-id="8859a-129">Weitere Informationen zu [Office 365-Gruppen](https://support.office.com/article/Learn-about-Office-365-groups-b565caa1-5c40-40ef-9915-60fdb2d97fa2).</span><span class="sxs-lookup"><span data-stu-id="8859a-129">Learn more about [Office 365 Groups](https://support.office.com/article/Learn-about-Office-365-groups-b565caa1-5c40-40ef-9915-60fdb2d97fa2).</span></span>
5. <span data-ttu-id="8859a-130">Klicken Sie auf die Option **Erstellen**, um die neue Gruppe hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="8859a-130">Choose **Create** to add the new group.</span></span>

## <a name="see-also"></a><span data-ttu-id="8859a-131">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="8859a-131">See also</span></span>
- [<span data-ttu-id="8859a-132">Verwalten des Zugriffs auf Ressourcen mit Azure Active Directory-Gruppen</span><span class="sxs-lookup"><span data-stu-id="8859a-132">Manage access to resources with Azure Active Directory groups</span></span>](https://docs.microsoft.com/azure/active-directory/active-directory-manage-groups)
- [<span data-ttu-id="8859a-133">Klassische Intune-Gruppen im Azure-Portal</span><span class="sxs-lookup"><span data-stu-id="8859a-133">Intune classic groups in the Azure portal</span></span>](groups-get-started.md)
