---
title: "Anpassen von Konsolenansichten für Administratorrollen"
description: "Filtern Sie wie in diesem Thema beschrieben die Intune-Verwaltungskonsolenansicht, damit Administratoren nur die Elemente anzeigen können, die sie für ihre Rolle benötigen."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 12/27/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e0783eaa-67dc-410e-9e80-4d3aa72f36d8
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: jeffgilb
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 3ce2401645987bd0942fa946eedd4009e952fc44
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2017
---
# <a name="customize-intune-console-views-according-to-admin-roles"></a><span data-ttu-id="1fe5a-103">Anpassen von Intune-Konsolenansichten an Administratorrollen</span><span class="sxs-lookup"><span data-stu-id="1fe5a-103">Customize Intune console views according to admin roles</span></span>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="1fe5a-104">Sie können die Microsoft Intune-Verwaltungskonsolenansicht filtern, damit Administratoren nur die Elemente anzeigen können, die sie für ihre Rolle benötigen.</span><span class="sxs-lookup"><span data-stu-id="1fe5a-104">You can filter the Microsoft Intune administration console view to allow your admins to see only the items they need to see for their role.</span></span> <span data-ttu-id="1fe5a-105">Beispielsweise empfiehlt es sich, nur den Operatoren der Verwaltungskonsole die Erlaubnis zu erteilen, Malwaredefinitionen zu aktualisieren oder die Kennung auf Geräten zurückzusetzen.</span><span class="sxs-lookup"><span data-stu-id="1fe5a-105">For example, you can allow only admin console operators to update malware definitions or reset the passcode on devices.</span></span> <span data-ttu-id="1fe5a-106">Dies erfolgt mithilfe der vorab festgelegten **Bezeichnungen**, die Sie bestimmten Benutzern zuweisen.</span><span class="sxs-lookup"><span data-stu-id="1fe5a-106">You do this by using preset **designations** that you assign to specific users.</span></span> <span data-ttu-id="1fe5a-107">Wenn diese Benutzer auf die Verwaltungskonsole zugreifen, sehen sie nur die für ihre Bezeichnung bestimmten Elemente.</span><span class="sxs-lookup"><span data-stu-id="1fe5a-107">When these users access the admin console, they can only see items that are specific to their designation.</span></span>

## <a name="to-create-a-custom-view"></a><span data-ttu-id="1fe5a-108">So erstellen Sie eine benutzerdefinierte Ansicht</span><span class="sxs-lookup"><span data-stu-id="1fe5a-108">To create a custom view</span></span>

1.  <span data-ttu-id="1fe5a-109">Wählen Sie in der [Microsoft Intune-Verwaltungskonsole](https://manage.microsoft.com) die Option **Admin** &gt; **Dienstadministratoren** aus.</span><span class="sxs-lookup"><span data-stu-id="1fe5a-109">In the [Microsoft Intune administration console](https://manage.microsoft.com), choose **Admin** &gt; **Service Administrators**.</span></span>

2.  <span data-ttu-id="1fe5a-110">Wählen Sie aus der Liste der Dienstadministratoren den Benutzer aus, dessen Bezeichnung Sie ändern möchten, und wählen Sie anschließend **Zugriff verwalten** aus.</span><span class="sxs-lookup"><span data-stu-id="1fe5a-110">From the list of service administrators, choose the user whose designation you want to change, and then choose **Manage Access**.</span></span>

3.  <span data-ttu-id="1fe5a-111">Wählen Sie im Dialogfeld **Zugriff verwalten** die Zugriffsebene, die dem ausgewählten Benutzer zugewiesen werden soll.</span><span class="sxs-lookup"><span data-stu-id="1fe5a-111">In the **Manage Access** dialog box, choose the level of access that you want to give the selected user.</span></span> <span data-ttu-id="1fe5a-112">Es gibt folgende Auswahlmöglichkeiten:</span><span class="sxs-lookup"><span data-stu-id="1fe5a-112">You can choose from:</span></span>

    -   <span data-ttu-id="1fe5a-113">**Vollzugriff**</span><span class="sxs-lookup"><span data-stu-id="1fe5a-113">**Full access**</span></span>
    -   <span data-ttu-id="1fe5a-114">**Schreibgeschützter Zugriff**</span><span class="sxs-lookup"><span data-stu-id="1fe5a-114">**Read-only access**</span></span>
    -   <span data-ttu-id="1fe5a-115">**Helpdesk – Gruppenknoten**</span><span class="sxs-lookup"><span data-stu-id="1fe5a-115">**Helpdesk - Groups node**</span></span>

    <span data-ttu-id="1fe5a-116">„Vollzugriff“ und „schreibgeschützter Zugriff“ sind selbsterklärend.</span><span class="sxs-lookup"><span data-stu-id="1fe5a-116">Full access and read-only access are self-explanatory.</span></span> <!--- **Helpdesk - Groups Node** allows users to choose from one of the following designations that provide custom levels of access to the Intune admin console:--->

    <span data-ttu-id="1fe5a-117">**Helpdesk – Gruppenknoten** beschränkt die Möglichkeiten, was der Administrator anzeigen und ausführen kann auf Folgendes:</span><span class="sxs-lookup"><span data-stu-id="1fe5a-117">**Helpdesk - Groups Node** restricts what the admin can see and do to the following:</span></span>

    -   <span data-ttu-id="1fe5a-118">Anzeigen der Listen von Benutzern und Geräten.</span><span class="sxs-lookup"><span data-stu-id="1fe5a-118">See lists of users and devices.</span></span> <span data-ttu-id="1fe5a-119">Der Administrator kann die Ansicht nicht mithilfe von Filtern ändern.</span><span class="sxs-lookup"><span data-stu-id="1fe5a-119">The admin cannot use filters to modify the view.</span></span> <span data-ttu-id="1fe5a-120">Sie können jedoch mithilfe der Gruppenfilterung definieren, was dem Administrator angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="1fe5a-120">However, you can use group filtering to modify what the admin can see.</span></span> <span data-ttu-id="1fe5a-121">Weitere Informationen finden Sie unter [Verwenden von Gruppen zum Verwalten von Benutzern und Geräten in Microsoft Intune](use-groups-to-manage-users-and-devices-with-microsoft-intune.md).</span><span class="sxs-lookup"><span data-stu-id="1fe5a-121">For more information, see [Use groups to manage users and devices with Microsoft Intune](use-groups-to-manage-users-and-devices-with-microsoft-intune.md).</span></span>

    -   <span data-ttu-id="1fe5a-122">Drucken der Liste der Benutzer und Geräte</span><span class="sxs-lookup"><span data-stu-id="1fe5a-122">Print the list of users and devices</span></span>

    -   <span data-ttu-id="1fe5a-123">Exportieren der Liste der Benutzer und Geräte</span><span class="sxs-lookup"><span data-stu-id="1fe5a-123">Export the list of users and devices</span></span>

    -   <span data-ttu-id="1fe5a-124">Anzeigen der Eigenschaften eines Benutzers oder Geräts</span><span class="sxs-lookup"><span data-stu-id="1fe5a-124">View the properties of a user or device</span></span>

    -   <span data-ttu-id="1fe5a-125">Führen Sie die folgenden Remoteaufgaben aus:</span><span class="sxs-lookup"><span data-stu-id="1fe5a-125">Perform the following remote tasks:</span></span>

        -   <span data-ttu-id="1fe5a-126">Vollständige Malwareüberprüfung ausführen</span><span class="sxs-lookup"><span data-stu-id="1fe5a-126">Run a full malware scan</span></span>

        -   <span data-ttu-id="1fe5a-127">Malwareschnellüberprüfung ausführen</span><span class="sxs-lookup"><span data-stu-id="1fe5a-127">Run a quick malware scan</span></span>

        -   <span data-ttu-id="1fe5a-128">Computer neu starten</span><span class="sxs-lookup"><span data-stu-id="1fe5a-128">Restart a computer</span></span>

        -   <span data-ttu-id="1fe5a-129">Update für Malwaredefinitionen ausführen</span><span class="sxs-lookup"><span data-stu-id="1fe5a-129">Update malware definitions</span></span>

        -   <span data-ttu-id="1fe5a-130">Richtlinien aktualisieren</span><span class="sxs-lookup"><span data-stu-id="1fe5a-130">Refresh policies</span></span>

        -   <span data-ttu-id="1fe5a-131">Inventur aktualisieren</span><span class="sxs-lookup"><span data-stu-id="1fe5a-131">Refresh inventory</span></span>

        -   <span data-ttu-id="1fe5a-132">Remotesperrung eines Geräts</span><span class="sxs-lookup"><span data-stu-id="1fe5a-132">Lock a device remotely</span></span>

        -   <span data-ttu-id="1fe5a-133">Zurücksetzen einer Kennung</span><span class="sxs-lookup"><span data-stu-id="1fe5a-133">Reset a passcode</span></span>

<span data-ttu-id="1fe5a-134">Wenn der von Ihnen konfigurierte Administrator das nächste Mal die Intune-Verwaltungskonsole öffnet, wird ihm die von Ihnen festgelegte Zugriffsebene zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="1fe5a-134">When the admin that you configured next opens the Intune admin console, they will be given the level of access that you designated.</span></span>
