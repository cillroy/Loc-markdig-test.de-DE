---
title: "Verwalten von Verknüpfungen zwischen Benutzern und Geräten für Windows-PCs"
description: "Verknüpfen eines Benutzers mit einem vom Intune verwalteten Windows-PC."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 12/15/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 53c99d63-c312-442a-8a71-de1b10fcd39b
ms.reviewer: owenyen
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 751355c34fc18cd9a1ededd498724d4652fc1368
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2018
---
# <a name="manage-user-device-linking-for-windows-pcs"></a><span data-ttu-id="8f2b8-103">Verwalten von Verknüpfungen zwischen Benutzern und Geräten für Windows-PCs</span><span class="sxs-lookup"><span data-stu-id="8f2b8-103">Manage user-device linking for Windows PCs</span></span>

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="8f2b8-104">Die Informationen in diesem Thema gelten nur für Windows-Desktops, die Sie als PCs mithilfe des Intune-Softwareclients verwalten.</span><span class="sxs-lookup"><span data-stu-id="8f2b8-104">The information in this topic applies only to Windows desktops that you are managing as PCs by using the Intune software client.</span></span> 

<span data-ttu-id="8f2b8-105">Damit Sie Software für einen Benutzer bereitstellen können, müssen Sie diesen zunächst mit einem PC verknüpfen.</span><span class="sxs-lookup"><span data-stu-id="8f2b8-105">Before you can deploy software to a user, you must link the user to a PC.</span></span> <span data-ttu-id="8f2b8-106">Sie können einen Benutzer mit mehreren PCs verknüpfen, aber einzelne PCs nur mit jeweils einem Benutzer.</span><span class="sxs-lookup"><span data-stu-id="8f2b8-106">You can link a user to multiple PCs, but each PC can be linked to only one user.</span></span> <span data-ttu-id="8f2b8-107">Benutzer werden automatisch mit den PCs verknüpft, die sie über das Unternehmensportal in Intune registrieren.</span><span class="sxs-lookup"><span data-stu-id="8f2b8-107">Users are automatically linked to any PCs that they enroll in Intune by using the company portal.</span></span>

<span data-ttu-id="8f2b8-108">So verknüpfen Sie einen Benutzer mit einem PC</span><span class="sxs-lookup"><span data-stu-id="8f2b8-108">To link a user to a PC:</span></span>

1. <span data-ttu-id="8f2b8-109">Wählen Sie in der [Microsoft Intune-Verwaltungskonsole](https://manage.microsoft.com/) die Option **Gruppen** &gt; **Alle Geräte** aus (oder eine andere Gruppe, in der der PC enthalten ist, den Sie mit einem Benutzer verknüpfen möchten).</span><span class="sxs-lookup"><span data-stu-id="8f2b8-109">In the [Microsoft Intune administration console](https://manage.microsoft.com/), choose **Groups** &gt; **All Devices** (or another group that contains the PC you want to link to a user).</span></span>

2. <span data-ttu-id="8f2b8-110">Wählen Sie den PC aus, den Sie mit einem Benutzer verknüpfen möchten, und dann **Benutzer verknüpfen** aus.</span><span class="sxs-lookup"><span data-stu-id="8f2b8-110">Select the PC that you want to link a user, and then choose **Link User**.</span></span>

   <span data-ttu-id="8f2b8-111">Im Dialogfeld **Benutzer verknüpfen** wird eine Liste verfügbarer Benutzer mit ihren Anzeigenamen, Benutzer-IDs und der Anzahl von PCs angezeigt, mit denen die Benutzer jeweils aktuell verknüpft sind.</span><span class="sxs-lookup"><span data-stu-id="8f2b8-111">The **Link User** dialog box displays a list of available users with their display name, user ID, and the number of PCs to which each user is currently linked.</span></span> <span data-ttu-id="8f2b8-112">Wenn ein Benutzer bereits mit dem ausgewählten PC verknüpft ist, werden Name und Benutzer-ID des Benutzers unter **Aktueller Benutzer**angezeigt.</span><span class="sxs-lookup"><span data-stu-id="8f2b8-112">If a user is already linked to the selected PC, that user’s name and user ID are displayed under **Current user**.</span></span> <span data-ttu-id="8f2b8-113">Wenn der PC mit keinem Benutzer verknüpft ist, wird unter **Aktueller Benutzer** der Wert **Kein Benutzer**angezeigt.</span><span class="sxs-lookup"><span data-stu-id="8f2b8-113">If the PC is not linked to any user, **No User** appears under **Current User**.</span></span>

3. <span data-ttu-id="8f2b8-114">Führen Sie eines der folgenden Verfahren aus:</span><span class="sxs-lookup"><span data-stu-id="8f2b8-114">Do one of the following:</span></span>

   - <span data-ttu-id="8f2b8-115">Wählen Sie **Abbrechen** aus, um die Verknüpfung des PC mit einem ggf. vorhandenen aktuellen Benutzer beizubehalten.</span><span class="sxs-lookup"><span data-stu-id="8f2b8-115">To leave the PC linked to its current user, if there is one, choose **Cancel**.</span></span>

   - <span data-ttu-id="8f2b8-116">Um den Link, um den aktuellen Benutzer zu entfernen, falls vorhanden, wählen Sie <strong>Verknüpfung entfernen **&gt; ** OK</strong>.</span><span class="sxs-lookup"><span data-stu-id="8f2b8-116">To remove the link to the current user, if there is one, choose <strong>Remove link **&gt; **OK</strong>.</span></span>

   - <span data-ttu-id="8f2b8-117">Zum Verknüpfen des PC mit einem neuen Benutzer wählen Sie diesen in der Liste **Alle Benutzer** aus.</span><span class="sxs-lookup"><span data-stu-id="8f2b8-117">To link the PC to a new user, in the **All users** list, select a user.</span></span> <span data-ttu-id="8f2b8-118">Überprüfen Sie, ob die Benutzerdaten korrekt sind, und wählen Sie **OK** aus.</span><span class="sxs-lookup"><span data-stu-id="8f2b8-118">Confirm that the user data is correct, and then choose **OK**.</span></span>

> [!TIP]
> <span data-ttu-id="8f2b8-119">Wenn Sie die Fähigkeit der Endbenutzer, sich mit PCs zu verknüpfen, einschränken möchten, aktivieren Sie die Option **Fähigkeit der Benutzer einschränken, sich mit PCs zu verknüpfen** in der Richtlinie **-Microsoft Intune-Agent-Einstellungen**.</span><span class="sxs-lookup"><span data-stu-id="8f2b8-119">If you want to restrict end users ability to link themselves to PCs, enable the option **Restrict users' ability to link themselves to PCs** in the **Microsoft Intune Agent Settings** policy.</span></span>

### <a name="see-also"></a><span data-ttu-id="8f2b8-120">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8f2b8-120">See also</span></span>

[<span data-ttu-id="8f2b8-121">Allgemeine Aufgaben zur Verwaltung von Windows-PCs mit dem Intune-Softwareclient</span><span class="sxs-lookup"><span data-stu-id="8f2b8-121">Common Windows PC management tasks with the Intune software client</span></span>](common-windows-pc-management-tasks-with-the-microsoft-intune-computer-client.md)