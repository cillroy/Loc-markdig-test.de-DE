---
title: "Konfigurieren der Intune-Einstellungen für Bildungseinrichtungen für Windows 10"
titleSuffix: Azure portal
description: "In diesem Artikel erfahren Sie, wie Sie mit Intune Einstellungen für Windows 10 Education auf Geräten konfigurieren, die Sie verwalten."
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 09/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 6f4de4bd-3dde-4a8d-8e22-46c5d06c3eea
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 12e36761320557f6af9554d3b671fc133253c13c
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2017
---
# <a name="how-to-configure-windows-10-education-settings-in-microsoft-intune"></a><span data-ttu-id="def59-103">Konfigurieren von Einstellungen für Bildungseinrichtungen für Windows 10 in Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="def59-103">How to configure Windows 10 education settings in Microsoft Intune</span></span>

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="def59-104">Mit Education-Profilen können Sie Details für die Konfiguration der Windows Take a Test-App einschließlich Kontodetails und die Test-URL angeben.</span><span class="sxs-lookup"><span data-stu-id="def59-104">Education profiles let you specify details that configure the Windows Take a Test app including account details, and the test URL.</span></span> <span data-ttu-id="def59-105">Wenn Sie diese Konfiguration vornehmen, öffnet sich die Take a Test-App mit dem angegebenen Test, und auf dem Gerät können keine anderen Apps ausgeführt werden, bevor der Test abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="def59-105">When you configure this, the Take a Test app opens with the test you specify, and no other apps can be run on the device until the test is complete.</span></span>

<span data-ttu-id="def59-106">Informationen zur „Take a Test“-App finden Sie unter [Durchführen von Prüfungen in Windows 10](https://docs.microsoft.com/education/windows/take-tests-in-windows-10).</span><span class="sxs-lookup"><span data-stu-id="def59-106">For details about the Take a Test app, see [Take tests in Windows 10](https://docs.microsoft.com/education/windows/take-tests-in-windows-10).</span></span>

## <a name="create-a-device-profile-containing-education-profile-settings"></a><span data-ttu-id="def59-107">Erstellen eines Geräteprofils mit Education-Profileinstellungen</span><span class="sxs-lookup"><span data-stu-id="def59-107">Create a device profile containing education profile settings</span></span>

1. <span data-ttu-id="def59-108">Melden Sie sich beim Azure-Portal an.</span><span class="sxs-lookup"><span data-stu-id="def59-108">Sign into the Azure portal.</span></span>
2. <span data-ttu-id="def59-109">Wählen Sie **Weitere Dienste** > **Überwachung und Verwaltung** > **Intune** aus.</span><span class="sxs-lookup"><span data-stu-id="def59-109">Choose **More Services** > **Monitoring + Management** > **Intune**.</span></span>
3. <span data-ttu-id="def59-110">Wählen Sie auf dem Blatt **Intune** die Option **Gerätekonfiguration** aus.</span><span class="sxs-lookup"><span data-stu-id="def59-110">On the **Intune** blade, choose **Device configuration**.</span></span>
2. <span data-ttu-id="def59-111">Wählen Sie auf dem Blatt **Gerätekonfiguration** die Option **Verwalten** > **Profile** aus.</span><span class="sxs-lookup"><span data-stu-id="def59-111">On the **Device Configuration** blade, choose **Manage** > **Profiles**.</span></span>
3. <span data-ttu-id="def59-112">Wählen Sie auf dem Blatt „Profile“ die Option **Profil erstellen** aus.</span><span class="sxs-lookup"><span data-stu-id="def59-112">On the profiles blade, choose **Create Profile**.</span></span>
4. <span data-ttu-id="def59-113">Geben Sie auf dem Blatt **Profil erstellen** einen **Namen** und eine **Beschreibung** für das Geräteeinschränkungsprofil ein.</span><span class="sxs-lookup"><span data-stu-id="def59-113">On the **Create Profile** blade, enter a **Name** and **Description** for the device restriction profile.</span></span>
5. <span data-ttu-id="def59-114">Wählen Sie in der Dropdownliste **Plattform** die Option **Windows 10 und höher** aus.</span><span class="sxs-lookup"><span data-stu-id="def59-114">From the **Platform** drop-down list, select **Windows 10 and later**.</span></span>
6. <span data-ttu-id="def59-115">Wählen Sie in der Dropdownliste **Profiltyp** die Option **Education-Profil** aus.</span><span class="sxs-lookup"><span data-stu-id="def59-115">From the **Profile type** type drop-down list, choose **Education profile**.</span></span> 
7. <span data-ttu-id="def59-116">Wählen Sie „Einstellungen“ > „Konfigurieren“ aus, und konfigurieren Sie auf dem Blatt **Prüfung** Folgendes:</span><span class="sxs-lookup"><span data-stu-id="def59-116">Choose Settings > Configure, then, on the **Take a Test** blade, configure the following:</span></span>
    - <span data-ttu-id="def59-117">**Kontobenutzername** – Geben Sie den Benutzernamen des Kontos ein, das mit Take a Test verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="def59-117">**Account user name** - Enter the user name of the account used with Take a Test.</span></span> <span data-ttu-id="def59-118">Dies kann ein Domänenkonto, ein Azure Active Directory (AAD)-Konto oder ein lokales Computerkonto sein.</span><span class="sxs-lookup"><span data-stu-id="def59-118">This can be a domain account, an Azure Active Directory (AAD) account, or a local computer account.</span></span>
    - <span data-ttu-id="def59-119">**Bewertungs-URL** – Geben Sie die URL des Tests an, den Benutzer ausführen sollen.</span><span class="sxs-lookup"><span data-stu-id="def59-119">**Assessment URL** - Provide the URL of the test you want users to take.</span></span> <span data-ttu-id="def59-120">Weitere Informationen finden Sie in der Take a Test-Dokumentation.</span><span class="sxs-lookup"><span data-stu-id="def59-120">For more information, see the Take a Test documentation.</span></span>
    - <span data-ttu-id="def59-121">**Bildschirmaufnahme** – Geben Sie an, ob sie die Bildschirmaktivität aufnehmen möchten, während Benutzer einen Test ausführen.</span><span class="sxs-lookup"><span data-stu-id="def59-121">**Screen monitoring** - Specify whether you want to be able to monitor screen activity while users are taking a test.</span></span>
    - <span data-ttu-id="def59-122">**Textvorschlag** – Lassen Sie Textvorschläge zu oder blockieren sie diese, während Benutzer einen Test ausführen.</span><span class="sxs-lookup"><span data-stu-id="def59-122">**Text suggestion** - Allow or block text suggestions while users are taking a test.</span></span>
8. <span data-ttu-id="def59-123">Navigieren Sie anschließend zurück zum Blatt **Profil erstellen**, und klicken Sie auf **Erstellen**.</span><span class="sxs-lookup"><span data-stu-id="def59-123">When you're done, go back to the **Create Profile** blade, and hit **Create**.</span></span>

<span data-ttu-id="def59-124">Das Profil wird erstellt und auf dem Blatt mit der Profilliste angezeigt.</span><span class="sxs-lookup"><span data-stu-id="def59-124">The profile will be created and appears on the profiles list blade.</span></span>

## <a name="next-steps"></a><span data-ttu-id="def59-125">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="def59-125">Next steps</span></span>

<span data-ttu-id="def59-126">Wenn Sie fortfahren und dieses Profil Gruppen zuweisen möchten, lesen Sie unter [Zuweisen von Geräteprofilen](device-profile-assign.md) nach.</span><span class="sxs-lookup"><span data-stu-id="def59-126">If you want to go ahead and assign this profile to groups, see [How to assign device profiles](device-profile-assign.md).</span></span>



