---
title: "Überprüfen Ihrer App-Schutzrichtlinien"
titleSuffix: Azure portal
description: "In diesen Themen wird beschrieben, wie Sie testen und überprüfen können, ob Ihre App-Schutzrichtlinie ordnungsgemäß eingerichtet wurde und wie erwartet funktioniert.\""
keywords: 
author: erikre
ms.author: erikre
manager: angerobe
ms.date: 01/23/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 15f8a838-0b69-412b-a42e-c6edb61f0cae
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: e023d06a56004d38083949819d8e843279ee1b72
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2017
---
# <a name="how-to-validate-your-app-protection-policy-setup"></a><span data-ttu-id="1ca27-103">Überprüfen der Einrichtung von App-Schutzrichtlinien</span><span class="sxs-lookup"><span data-stu-id="1ca27-103">How to validate your app protection policy setup</span></span>

[!INCLUDE[azure_portal](./includes/azure_portal.md)]


<span data-ttu-id="1ca27-104">Dieses Thema enthält Informationen zum Suchen nach Problemen nach der Einrichtung der App-Schutzrichtlinie.</span><span class="sxs-lookup"><span data-stu-id="1ca27-104">This topic provides information on checking for issues after you set up an app protection policy.</span></span> <span data-ttu-id="1ca27-105">Diese Anleitung gilt für App-Schutzrichtlinien im Azure-Portal.</span><span class="sxs-lookup"><span data-stu-id="1ca27-105">This guidance applies to app protection policies in the Azure portal.</span></span>

### <a name="checking-for-symptoms"></a><span data-ttu-id="1ca27-106">Suchen nach Symptomen</span><span class="sxs-lookup"><span data-stu-id="1ca27-106">Checking for symptoms</span></span>
<span data-ttu-id="1ca27-107">Benutzer melden so gut wie keine Probleme, da der App-Schutz ein Tool zum Schutz von Daten ist.</span><span class="sxs-lookup"><span data-stu-id="1ca27-107">Users are unlikely to report issues since app protection is a data protection tool.</span></span> <span data-ttu-id="1ca27-108">Liegt ein Problem mit der Konfiguration des App-Schutzes vor, erhält der Benutzer uneingeschränkten Zugriff, wie es auch ohne App-Schutz der Fall wäre, und er würde nicht bemerken, dass es ein Problem gibt.</span><span class="sxs-lookup"><span data-stu-id="1ca27-108">If there is a problem with the app protection configuration the user will have unrestricted access, as they would have without app protection, and would not be aware that there is an issue.</span></span> <span data-ttu-id="1ca27-109">Aus diesem Grund wird empfohlen, dass Sie Ihre App-Schutzkonfiguration überprüfen, indem Sie Ihre App-Schutzrichtlinien mit einer kleinen Gruppe von Benutzern steuern, die bewusst die Einschränkungen des App-Schutzes testen können.</span><span class="sxs-lookup"><span data-stu-id="1ca27-109">For this reason we recommend that you validate your app protection configuration by piloting your app protection policies with a small group of users who can deliberately test the app protection restrictions.</span></span>


### <a name="what-to-check"></a><span data-ttu-id="1ca27-110">Was soll überprüft werden?</span><span class="sxs-lookup"><span data-stu-id="1ca27-110">What to check</span></span>

<span data-ttu-id="1ca27-111">Wenn der Test zeigt, dass das Verhalten Ihrer App-Schutzrichtlinie nicht wie erwartet ist, empfiehlt es sich, folgende Punkte zu überprüfen:</span><span class="sxs-lookup"><span data-stu-id="1ca27-111">If testing shows that your app protection policy behavior is not as anticipated, we recommend that you check the following:</span></span>

- <span data-ttu-id="1ca27-112">Sind die Benutzer für den App-Schutz lizenziert?</span><span class="sxs-lookup"><span data-stu-id="1ca27-112">Are the users licensed for app protection?</span></span>
- <span data-ttu-id="1ca27-113">Sind die Benutzer für Office 365 lizenziert?</span><span class="sxs-lookup"><span data-stu-id="1ca27-113">Are the users licensed for O365?</span></span>
- <span data-ttu-id="1ca27-114">Welchen Status haben die App-Schutz-Apps der einzelnen Benutzers?</span><span class="sxs-lookup"><span data-stu-id="1ca27-114">The status of each of the users' app protection apps.</span></span> <span data-ttu-id="1ca27-115">Die möglichen Statuswerte für die apps sind **Eingecheckt** und **Nicht eingecheckt**.</span><span class="sxs-lookup"><span data-stu-id="1ca27-115">The possible statuses for the apps are **Checked in** and **Not checked in**.</span></span>

#### <a name="user-app-protection-status"></a><span data-ttu-id="1ca27-116">Schutzstatus der Benutzer-App</span><span class="sxs-lookup"><span data-stu-id="1ca27-116">User app protection status</span></span>
1. <span data-ttu-id="1ca27-117">Wählen Sie im Azure-Portal **Apps verwalten** > **Überwachen** >  **Benutzerstatus des App-Schutzes** > **Benutzer** aus.</span><span class="sxs-lookup"><span data-stu-id="1ca27-117">In the Azure portal choose **Manage apps** > **Monitor** >  **App protection user status** > **users**.</span></span>

2. <span data-ttu-id="1ca27-118">Wählen Sie einen Benutzer aus der Liste aus, oder suchen Sie einen Benutzer und wählen Sie Ihn aus. Wählen Sie anschließend **Benutzer auswählen** aus.</span><span class="sxs-lookup"><span data-stu-id="1ca27-118">Choose a user from the list or search for and choose a user, then choose **Select user**.</span></span> <span data-ttu-id="1ca27-119">Am oberen Rand der Spalte **App-Berichterstellung** sehen Sie, ob der Benutzer für den App-Schutz lizenziert ist.</span><span class="sxs-lookup"><span data-stu-id="1ca27-119">At the top of the **App reporting** column you will see whether the user is licensed for app protection.</span></span> <span data-ttu-id="1ca27-120">Nachfolgend sehen Sie, ob der Benutzer für Office 365 und den App-Status aller Geräte des Benutzers lizenziert ist.</span><span class="sxs-lookup"><span data-stu-id="1ca27-120">Below that you will see whether the user is licensed for O365 and the app status for all of the user's devices.</span></span>



### <a name="what-to-do"></a><span data-ttu-id="1ca27-121">Aktion</span><span class="sxs-lookup"><span data-stu-id="1ca27-121">What to do</span></span>
<span data-ttu-id="1ca27-122">Hier sind die Aktionen, die basierend auf den Benutzerstatus durchgeführt werden müssen:</span><span class="sxs-lookup"><span data-stu-id="1ca27-122">Here are the actions to take based on the user status:</span></span>

- <span data-ttu-id="1ca27-123">Wenn der Benutzer nicht für den App-Schutz lizenziert ist, weisen Sie dem Benutzer eine Intune-Lizenz zu.</span><span class="sxs-lookup"><span data-stu-id="1ca27-123">If the user is not licensed for app protection, assign an Intune license to the user.</span></span>
- <span data-ttu-id="1ca27-124">Wenn der Benutzer nicht für Office 365 lizenziert ist, rufen Sie eine Lizenz für den Benutzer ab.</span><span class="sxs-lookup"><span data-stu-id="1ca27-124">If the user is not licensed for O365 obtain a license for the user.</span></span>
- <span data-ttu-id="1ca27-125">Wenn die App des Benutzer als **Nicht eingecheckt** aufgelistet ist, überprüfen Sie, ob Sie die App-Schutzrichtlinie für diese App ordnungsgemäß konfiguriert haben.</span><span class="sxs-lookup"><span data-stu-id="1ca27-125">If a user's app is listed as **Not checked in**, check if you've correctly configured a app protection policy for that app.</span></span>
- <span data-ttu-id="1ca27-126">Stellen Sie sicher, dass diese Bedingungen auf alle Benutzer angewendet werden, für die die App-Schutzrichtlinien gelten sollen.</span><span class="sxs-lookup"><span data-stu-id="1ca27-126">Ensure that these conditions are applied across all users to which you want app protection policies to apply.</span></span>

### <a name="see-also"></a><span data-ttu-id="1ca27-127">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1ca27-127">See also</span></span>

[<span data-ttu-id="1ca27-128">Was sind Intune-App-Schutzrichtlinien?</span><span class="sxs-lookup"><span data-stu-id="1ca27-128">What is Intune app protection policy?</span></span>](app-protection-policies.md)
