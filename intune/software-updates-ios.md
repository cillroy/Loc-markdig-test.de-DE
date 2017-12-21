---
title: Konfigurieren von iOS-Updaterichtlinien
titlesuffix: Azure portal
description: "Konfigurieren Sie die Richtlinien, damit unter iOS die automatische Installation des neuesten Softwareupdates bei überwachten iOS-Geräten durchgesetzt werden kann."
keywords: 
author: dougeby
manager: dougeby
ms.date: 08/02/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e6334421-85e1-4457-9c44-e5db8d4ee00e
ms.openlocfilehash: 199760a60ee2290560ebdf933192de0eaf569e9e
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2017
---
# <a name="configure-ios-update-policies"></a><span data-ttu-id="2f557-103">Konfigurieren von iOS-Updaterichtlinien</span><span class="sxs-lookup"><span data-stu-id="2f557-103">Configure iOS update policies</span></span>
<span data-ttu-id="2f557-104">Aktualisieren Sie die Richtlinien, damit Sie unter iOS die automatische Installation des neuesten Softwareupdates bei überwachten iOS-Geräten durchsetzen können.</span><span class="sxs-lookup"><span data-stu-id="2f557-104">Update policies for iOS let you force supervised iOS devices to automatically install the latest available software update.</span></span> <span data-ttu-id="2f557-105">Sie haben die Möglichkeit, die Tage und Uhrzeiten zu konfigurieren, an denen Geräte keine Updates installieren sollen.</span><span class="sxs-lookup"><span data-stu-id="2f557-105">You have the option to configure the days and times when you do not want devices to install the update.</span></span>

## <a name="configure-the-ios-update-policy"></a><span data-ttu-id="2f557-106">Konfigurieren der iOS-Updaterichtlinie</span><span class="sxs-lookup"><span data-stu-id="2f557-106">Configure the iOS update policy</span></span>
1. <span data-ttu-id="2f557-107">Wechseln Sie zu dem Blatt „Intune“ im Azure-Portal.</span><span class="sxs-lookup"><span data-stu-id="2f557-107">Go to the Intune blade in the Azure portal.</span></span>
2. <span data-ttu-id="2f557-108">Wählen Sie auf dem Blatt **Intune** die Option **Softwareupdates** > **iOS-Updaterichtlinien** aus.</span><span class="sxs-lookup"><span data-stu-id="2f557-108">On the **Intune** blade, choose **Software updates** > **iOS Update Policies**.</span></span>
4. <span data-ttu-id="2f557-109">Klicken Sie auf dem Richtlinienblatt auf **Erstellen**, und geben Sie dann einen Namen und eine Beschreibung für die Richtlinie ein.</span><span class="sxs-lookup"><span data-stu-id="2f557-109">On the policies blade, choose **Create**, and then enter a name and description for the policy.</span></span>
5. <span data-ttu-id="2f557-110">Klicken Sie auf **Einstellungen** > **Konfigurieren**, und geben Sie dann an, wann die Installation der neuesten Updates auf iOS-Geräte nicht erzwungen werden soll.</span><span class="sxs-lookup"><span data-stu-id="2f557-110">Select **Settings** > **Configure**, and enter the details for when iOS devices are not be forced to install the latest update.</span></span>
6. <span data-ttu-id="2f557-111">Wählen Sie **OK** aus, um diese Konfiguration zu speichern.</span><span class="sxs-lookup"><span data-stu-id="2f557-111">Choose **OK** to save this configuration.</span></span> <span data-ttu-id="2f557-112">Damit befinden Sie sich wieder auf dem Blatt **Updaterichtlinie erstellen**.</span><span class="sxs-lookup"><span data-stu-id="2f557-112">You are now back in the **Create update policy** blade.</span></span> <span data-ttu-id="2f557-113">Wählen Sie **Erstellen** aus, um die Richtlinie zu erstellen und Ihre Einstellungen zu speichern.</span><span class="sxs-lookup"><span data-stu-id="2f557-113">Choose **Create** to create the policy and save your settings.</span></span>

<span data-ttu-id="2f557-114">Das Profil wird erstellt und auf dem Blatt mit der Liste der iOS-Updaterichtlinien angezeigt.</span><span class="sxs-lookup"><span data-stu-id="2f557-114">The profile is created and appears on the iOS update policies list blade.</span></span>

## <a name="assign-an-ios-update-policy-to-users"></a><span data-ttu-id="2f557-115">Zuweisen einer iOS-Updaterichtlinie zu Benutzern</span><span class="sxs-lookup"><span data-stu-id="2f557-115">Assign an iOS update policy to users</span></span>
<span data-ttu-id="2f557-116">Um Benutzern eine iOS-Updaterichtlinie zuzuweisen, wählen Sie eine Richtlinie aus, die Sie konfiguriert haben.</span><span class="sxs-lookup"><span data-stu-id="2f557-116">To assign an iOS update policy to users, choose a policy that you have configured.</span></span> <span data-ttu-id="2f557-117">Vorhandene Richtlinien befinden sich auf dem Blatt **Softwareupdates** > **iOS-Updaterichtlinien**.</span><span class="sxs-lookup"><span data-stu-id="2f557-117">Existing policies are found in the **Software updates** > **iOS Update Policies** blade.</span></span>
1. <span data-ttu-id="2f557-118">Wählen Sie die Richtlinie, die Sie Benutzern zuweisen möchten, und abschließend **Zuweisungen** aus.</span><span class="sxs-lookup"><span data-stu-id="2f557-118">Choose the policy you want to assign to users and choose **Assignments**.</span></span> <span data-ttu-id="2f557-119">Das Blatt wird geöffnet, auf dem Sie Azure Active Directory-Sicherheitsgruppen auswählen und der Richtlinie zuweisen können.</span><span class="sxs-lookup"><span data-stu-id="2f557-119">The blade where you can select Azure Active Directory security groups and assign them to the policy is opened.</span></span>
2. <span data-ttu-id="2f557-120">Wählen Sie **Gruppen auswählen** aus, um das Blatt mit den Azure AD-Sicherheitsgruppen zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="2f557-120">Choose **Select groups** to open the blade that displays the Azure AD security groups.</span></span> <span data-ttu-id="2f557-121">Wählen Sie **Auswählen** aus, um die Richtlinie für Benutzer bereitzustellen.</span><span class="sxs-lookup"><span data-stu-id="2f557-121">Choose **Select** to deploy the policy to users.</span></span>

<span data-ttu-id="2f557-122">Sie haben die Richtlinie auf Benutzer angewendet.</span><span class="sxs-lookup"><span data-stu-id="2f557-122">You have applied the policy to users.</span></span> <span data-ttu-id="2f557-123">Die von den Benutzern verwendeten Geräte, denen die Richtlinie zugewiesen wurde, werden auf Updatekompatibilität überprüft.</span><span class="sxs-lookup"><span data-stu-id="2f557-123">The devices used by the users who are targeted by the policy are evaluated for update compliance.</span></span>

## <a name="change-the-restricted-days-for-the-policy"></a><span data-ttu-id="2f557-124">Ändern der eingeschränkten Tage für die Richtlinie</span><span class="sxs-lookup"><span data-stu-id="2f557-124">Change the restricted days for the policy</span></span>
1. <span data-ttu-id="2f557-125">Wählen Sie auf dem Blatt **Softwareupdates** die Option **iOS-Updaterichtlinien** aus.</span><span class="sxs-lookup"><span data-stu-id="2f557-125">On the **Software updates** blade, choose **iOS Update Policies**.</span></span>
2. <span data-ttu-id="2f557-126">Wählen Sie die iOS-Updaterichtlinie aus, die Sie aktualisieren möchten.</span><span class="sxs-lookup"><span data-stu-id="2f557-126">Select the iOS update policy that you want to update.</span></span>
3. <span data-ttu-id="2f557-127">Wählen Sie **Eigenschaften** aus, und aktualisieren Sie die Informationen zu den eingeschränkten Tagen.</span><span class="sxs-lookup"><span data-stu-id="2f557-127">Select **Properties** and update the restricted days information.</span></span>

## <a name="monitor-ios-devices-with-older-ios-versions"></a><span data-ttu-id="2f557-128">Überwachen von iOS-Geräten mit älteren iOS-Versionen</span><span class="sxs-lookup"><span data-stu-id="2f557-128">Monitor iOS devices with older iOS versions</span></span> 
<!-- 1352223 -->
<span data-ttu-id="2f557-129">Der Bericht **Out-of-date iOS Devices** (Veraltete iOS-Geräte) ist auf dem Blatt **Softwareupdates** > **iOS-Updaterichtlinien** verfügbar.</span><span class="sxs-lookup"><span data-stu-id="2f557-129">The **Out-of-date iOS Devices** report is available from the **Software updates** > **iOS Update Policies** blade.</span></span> <span data-ttu-id="2f557-130">Im Bericht wird Ihnen eine Liste der überwachten iOS-Geräte angezeigt, die unter eine iOS-Updaterichtlinie fallen und nicht aktualisiert werden konnten.</span><span class="sxs-lookup"><span data-stu-id="2f557-130">In the report, you can view a list of supervised iOS devices that were targeted by an iOS update policy and could not be updated.</span></span> <span data-ttu-id="2f557-131">Für jedes Gerät können Sie einen Status anzeigen, warum das Gerät nicht automatisch aktualisiert wurde.</span><span class="sxs-lookup"><span data-stu-id="2f557-131">For each device, you can view a status for why the device has not been automatically updated.</span></span>