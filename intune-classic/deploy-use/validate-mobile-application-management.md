---
title: "Überprüfen Ihres MAM-Setups"
description: "In diesem Thema wird beschrieben, wie Sie testen und überprüfen können, ob Ihre MAM-Richtlinie ordnungsgemäß eingerichtet wurde und wie erwartet funktioniert."
keywords: 
author: andredm7
ms.author: andredm
manager: angerobe
ms.date: 12/19/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 41d82597-e13e-4c3e-9151-e71392236ca0
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: joglocke
ms.custom: intune-classic
ms.openlocfilehash: fe7cea635f583e4889ebaffbde58c56b75a82c22
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2018
---
# <a name="validating-your-mobile-application-management-setup"></a><span data-ttu-id="3721f-103">Überprüfen des Setups für die Verwaltung Ihrer mobilen Anwendungen</span><span class="sxs-lookup"><span data-stu-id="3721f-103">Validating your mobile application management setup</span></span>

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="3721f-104">Dieses Thema enthält Informationen zum Suchen nach Problemen nach der Einrichtung der mobilen Anwendungsverwaltung (MAM).</span><span class="sxs-lookup"><span data-stu-id="3721f-104">This topic provides information on checking for issues after you set up mobile application management (MAM).</span></span> <span data-ttu-id="3721f-105">Diese Anleitung gilt für MAM-Richtlinien im Azure-Portal.</span><span class="sxs-lookup"><span data-stu-id="3721f-105">This guidance applies to MAM policies in the Azure portal.</span></span>

### <a name="checking-for-symptoms"></a><span data-ttu-id="3721f-106">Suchen nach Symptomen</span><span class="sxs-lookup"><span data-stu-id="3721f-106">Checking for symptoms</span></span>
<span data-ttu-id="3721f-107">Benutzer melden so gut wie keine Probleme, da MAM ein Tool zum Schutz von Daten ist.</span><span class="sxs-lookup"><span data-stu-id="3721f-107">Users are unlikely to report issues since MAM is a data protection tool.</span></span> <span data-ttu-id="3721f-108">Liegt ein Problem mit der MAM-Konfiguration vor, erhält der Benutzer uneingeschränkten Zugriff, so wie es ohne MAM der Fall wäre, und er würde nicht bemerken, dass es ein Problem gibt.</span><span class="sxs-lookup"><span data-stu-id="3721f-108">If there is a problem with the MAM configuration the user will have unrestricted access, as they would have without MAM, and would not be aware that there is an issue.</span></span> <span data-ttu-id="3721f-109">Aus diesem Grund wird empfohlen, dass Sie Ihre MAM-Konfiguration überprüfen, indem Sie Ihre MAM-Richtlinien mit einer kleinen Gruppe von Benutzern steuern, die bewusst die MAM-Einschränkungen testen können.</span><span class="sxs-lookup"><span data-stu-id="3721f-109">For this reason we recommend that you validate your MAM configuration by piloting your MAM policies with a small group of users who can deliberately test the MAM restrictions.</span></span>


### <a name="what-to-check"></a><span data-ttu-id="3721f-110">Was soll überprüft werden?</span><span class="sxs-lookup"><span data-stu-id="3721f-110">What to check</span></span>

<span data-ttu-id="3721f-111">Wenn der Test zeigt, dass das Verhalten Ihrer MAM-Richtlinie nicht wie erwartet ist, empfiehlt es sich, folgende Punkte zu überprüfen:</span><span class="sxs-lookup"><span data-stu-id="3721f-111">If testing shows that your MAM policy behavior is not as anticipated, we recommend that you check the following:</span></span>

- <span data-ttu-id="3721f-112">Sind die Benutzer für MAM lizenziert?</span><span class="sxs-lookup"><span data-stu-id="3721f-112">Are the users licensed for MAM?</span></span>
- <span data-ttu-id="3721f-113">Sind die Benutzer für Office 365 lizenziert?</span><span class="sxs-lookup"><span data-stu-id="3721f-113">Are the users licensed for O365?</span></span>
- <span data-ttu-id="3721f-114">Der Status der MAM-Apps eines jeden Benutzers.</span><span class="sxs-lookup"><span data-stu-id="3721f-114">The status of each of the users' MAM apps.</span></span> <span data-ttu-id="3721f-115">Die möglichen Statuswerte für die apps sind **Eingecheckt** und **Nicht eingecheckt**.</span><span class="sxs-lookup"><span data-stu-id="3721f-115">The possible statuses for the apps are **Checked in** and **Not checked in**.</span></span>

#### <a name="user-mam-status"></a><span data-ttu-id="3721f-116">MAM-Status des Benutzers</span><span class="sxs-lookup"><span data-stu-id="3721f-116">User MAM status</span></span>
1. <span data-ttu-id="3721f-117">Wählen Sie im Azure-Portal **Mobile Anwendungsverwaltung mit Intune** > **Einstellungen** > **App-Verwaltung** > **Alle Einstellungen** > **App-Berichterstellung nach Benutzer** > **Benutzer**.</span><span class="sxs-lookup"><span data-stu-id="3721f-117">In the Azure portal choose **Intune mobile application management** > **settings** > **app management** > **All settings** > **App reporting by user** > **users**.</span></span>

2. <span data-ttu-id="3721f-118">Wählen Sie einen Benutzer aus der Liste aus, oder suchen Sie einen Benutzer und wählen Sie Ihn aus. Wählen Sie anschließend **Benutzer auswählen** aus.</span><span class="sxs-lookup"><span data-stu-id="3721f-118">Choose a user from the list or search for and choose a user, then choose **Select user**.</span></span> <span data-ttu-id="3721f-119">Am oberen Rand der Spalte **App-Berichterstellung** sehen Sie, ob der Benutzer für die MAM lizenziert ist.</span><span class="sxs-lookup"><span data-stu-id="3721f-119">At the top of the **App reporting** column you will see whether the user is licensed for MAM.</span></span> <span data-ttu-id="3721f-120">Nachfolgend sehen Sie, ob der Benutzer für Office 365 und den App-Status aller Geräte des Benutzers lizenziert ist.</span><span class="sxs-lookup"><span data-stu-id="3721f-120">Below that you will see whether the user is licensed for O365 and the app status for all of the user's devices.</span></span>

![App-Statuts für MAM](..\media\ts-mam-user-apps.png)

### <a name="what-to-do"></a><span data-ttu-id="3721f-122">Aktion</span><span class="sxs-lookup"><span data-stu-id="3721f-122">What to do</span></span>
<span data-ttu-id="3721f-123">Hier sind die Aktionen, die basierend auf den Benutzerstatus durchgeführt werden müssen:</span><span class="sxs-lookup"><span data-stu-id="3721f-123">Here are the actions to take based on the user status:</span></span>

- <span data-ttu-id="3721f-124">Wenn der Benutzer nicht für MAM lizenziert ist, weisen Sie dem Benutzer eine Intune-Lizenz zu, wie unter [Verwalten von Intune-Lizenzen](/intune/setup-steps) beschrieben.</span><span class="sxs-lookup"><span data-stu-id="3721f-124">If the user is not licensed for MAM, assign an Intune license to the user as described in [Manage Intune licenses](/intune/setup-steps).</span></span>
- <span data-ttu-id="3721f-125">Wenn der Benutzer nicht für Office 365 lizenziert ist, rufen Sie eine Lizenz für den Benutzer ab.</span><span class="sxs-lookup"><span data-stu-id="3721f-125">If the user is not licensed for O365 obtain a license for the user.</span></span>
- <span data-ttu-id="3721f-126">Wenn die App des Benutzer als **Nicht eingecheckt** aufgelistet ist, überprüfen Sie, ob Sie die MAM-Richtlinie für diese App ordnungsgemäß konfiguriert haben.</span><span class="sxs-lookup"><span data-stu-id="3721f-126">If a user's app is listed as **Not checked in**, check if you've correctly configured a MAM policy for that app.</span></span>
- <span data-ttu-id="3721f-127">Stellen Sie sicher, dass diese Bedingungen auf alle Benutzer angewendet werden, auf die die MAM Richtlinien angewendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="3721f-127">Ensure that these conditions are applied across all users to which you want MAM policies to apply.</span></span>

### <a name="see-also"></a><span data-ttu-id="3721f-128">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3721f-128">See also</span></span>
[<span data-ttu-id="3721f-129">Vorbereiten der Konfiguration von Verwaltungsrichtlinien für mobile Apps mit Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="3721f-129">Get ready to configure mobile app management policies with Microsoft Intune</span></span>](..\deploy-use\get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune.md)

[<span data-ttu-id="3721f-130">Schützen von App-Daten mithilfe der Verwaltungsrichtlinien für mobile Apps mit Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="3721f-130">Protect app data using mobile app management policies with Microsoft Intune</span></span>](..\deploy-use\protect-app-data-using-mobile-app-management-policies-with-microsoft-intune.md)
