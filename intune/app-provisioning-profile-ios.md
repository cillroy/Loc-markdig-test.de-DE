---
title: App-Bereitstellungsprofile
titlesuffix: Azure portal
description: "Intune stellt Ihnen die Tools zum proaktiven Zuweisen eines neuen Bereitstellungsprofils auf Geräten zur Verfügung, auf denen Apps installiert sind, die bald ablaufen.\""
keywords: 
author: erikre
ms.author: erikre
manager: angrobe
ms.date: 05/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: bbc3ba4a-df48-4aeb-988b-69a177764e3a
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: ce66677bfec48e9a5b69e23be67e2e172edc33d5
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2018
---
# <a name="use-ios-mobile-provisioning-profiles-to-prevent-your-apps-from-expiring"></a><span data-ttu-id="75867-103">Verwenden von mobilen iOS-Bereitstellungsprofilen, um zu verhindern, dass Apps ablaufen</span><span class="sxs-lookup"><span data-stu-id="75867-103">Use iOS mobile provisioning profiles to prevent your apps from expiring</span></span>

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

## <a name="introduction"></a><span data-ttu-id="75867-104">Einführung</span><span class="sxs-lookup"><span data-stu-id="75867-104">Introduction</span></span>

<span data-ttu-id="75867-105">Die iPhones und iPads zugewiesenen branchenspezifischen Apple iOS-Apps wurden mit integriertem Bereitstellungsprofil und per Zertifikat signiertem Code erstellt.</span><span class="sxs-lookup"><span data-stu-id="75867-105">Apple iOS line of business apps that are assigned to iPhones and iPads are built with an included provisioning profile and code that is signed with a certificate.</span></span> <span data-ttu-id="75867-106">Beim Ausführen der App bestätigt iOS die Integrität der iOS-App und erzwingt Richtlinien, die durch das Bereitstellungsprofil definiert werden.</span><span class="sxs-lookup"><span data-stu-id="75867-106">When the app is run, iOS confirms the integrity of the iOS app and enforces policies that are defined by the provisioning profile.</span></span> <span data-ttu-id="75867-107">Folgende Überprüfungen finden statt:</span><span class="sxs-lookup"><span data-stu-id="75867-107">The following validations happen:</span></span>

- <span data-ttu-id="75867-108">**Integrität der Installationsdateien**: iOS vergleicht die Details der App mit dem öffentlichen Schlüssel des Unternehmenssignaturzertifikats.</span><span class="sxs-lookup"><span data-stu-id="75867-108">**Installation file integrity** - iOS compares the app's details with the enterprise signing certificate's public key.</span></span> <span data-ttu-id="75867-109">Wenn Unterschiede festgestellt werden, wurde der Inhalt der App möglicherweise verändert, und die Ausführung der App wird nicht zugelassen.</span><span class="sxs-lookup"><span data-stu-id="75867-109">If they differ, the app's content might have changed, and the app will not be allowed to run.</span></span>
- <span data-ttu-id="75867-110">**Erzwingen von Funktionen**: iOS versucht, die App-Funktionen aus dem Bereitstellungsprofil des Unternehmens (nicht den Bereitstellungsprofilen der einzelnen Entwickler) zu erzwingen, die in der App-Installationsdatei (IPA) enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="75867-110">**Capabilities enforcement** - iOS attempts to enforce the app's capabilities from the enterprise provisioning profile (not individual developer provisioning profiles) that are in the app installation (.ipa) file.</span></span>


<span data-ttu-id="75867-111">Das Unternehmenssignaturzertifikat, das Sie zum Signieren von Apps verwenden, ist in der Regel drei Jahre lang gültig.</span><span class="sxs-lookup"><span data-stu-id="75867-111">The enterprise signing certificate that you use to sign apps typically lasts for three years.</span></span> <span data-ttu-id="75867-112">Allerdings läuft das Bereitstellungsprofil nach einem Jahr ab.</span><span class="sxs-lookup"><span data-stu-id="75867-112">However, the provisioning profile expires after a year.</span></span> <span data-ttu-id="75867-113">Während das Zertifikat noch gültig ist, stellt Intune Ihnen die Tools zum proaktiven Zuweisen eines neuen Bereitstellungsprofils auf Geräten zur Verfügung, auf denen Apps installiert sind, die bald ablaufen.</span><span class="sxs-lookup"><span data-stu-id="75867-113">While the certificate is still valid, Intune gives you the tools to proactively assign a new provisioning profile to devices that have apps that are nearing expiry.</span></span>
<span data-ttu-id="75867-114">Nach Ablauf des Zertifikats müssen Sie die App mit einem neuen Zertifikat erneut signieren und ein neues Bereitstellungsprofil mit dem Schlüssel des neuen Zertifikats einbetten.</span><span class="sxs-lookup"><span data-stu-id="75867-114">After the certificate expires, you must sign the app again with a new certificate and embed a new provisioning profile with the key of the new certificate.</span></span>


## <a name="how-to-create-an-ios-mobile-app-provisioning-profile"></a><span data-ttu-id="75867-115">Erstellen eines Bereitstellungsprofils für mobile iOS-Apps</span><span class="sxs-lookup"><span data-stu-id="75867-115">How to create an iOS mobile app provisioning profile</span></span>

1. <span data-ttu-id="75867-116">Melden Sie sich beim Azure-Portal an.</span><span class="sxs-lookup"><span data-stu-id="75867-116">Sign into the Azure portal.</span></span>
2. <span data-ttu-id="75867-117">Wählen Sie **Weitere Dienste** > **Überwachung und Verwaltung** > **Intune** aus.</span><span class="sxs-lookup"><span data-stu-id="75867-117">Choose **More Services** > **Monitoring +Management** > **Intune**.</span></span>
3. <span data-ttu-id="75867-118">Wählen Sie auf dem Blatt **Intune** die Option **Mobile Apps** aus.</span><span class="sxs-lookup"><span data-stu-id="75867-118">On the **Intune** blade, choose **Mobile apps**.</span></span>
1.  <span data-ttu-id="75867-119">Wählen Sie im Abschnitt **Mobile Apps** die Option **Verwalten** > **iOS-Bereitstellungsprofile** aus.</span><span class="sxs-lookup"><span data-stu-id="75867-119">In the **Mobile apps** workload, choose **Manage** > **iOS provisioning profiles**.</span></span>
2.  <span data-ttu-id="75867-120">Wählen Sie auf dem Blatt mit der Profilliste die Option **Profil erstellen** aus.</span><span class="sxs-lookup"><span data-stu-id="75867-120">In the list of profiles blade, choose **Create profile**.</span></span>
3. <span data-ttu-id="75867-121">Legen Sie auf dem Blatt **Profil erstellen** die folgenden Einstellungen fest:</span><span class="sxs-lookup"><span data-stu-id="75867-121">In the **Create profile** blade, configure the following values:</span></span>
    - <span data-ttu-id="75867-122">**Name**: Geben Sie einen Namen für dieses mobile Bereitstellungsprofil an.</span><span class="sxs-lookup"><span data-stu-id="75867-122">**Name** - Provide a name for this mobile provisioning profile.</span></span>
    - <span data-ttu-id="75867-123">**Beschreibung**: Geben Sie optional eine Beschreibung der Richtlinie ein.</span><span class="sxs-lookup"><span data-stu-id="75867-123">**Description** - Optionally, provide a description for the policy.</span></span>
    - <span data-ttu-id="75867-124">**Profildatei hochladen**: Klicken Sie auf **Importieren**, und wählen Sie eine Datei mit einem mobilen Apple-Konfigurationsprofil (mit der Erweiterung **.mobileprovision**) aus, die Sie von der Apple Developer-Website heruntergeladen haben.</span><span class="sxs-lookup"><span data-stu-id="75867-124">**Upload profile file** - Choose **Import**, and then choose an Apple Mobile Configuration Profile file (with the extension **.mobileprovision**) that you downloaded from the Apple Developer website.</span></span>
4. <span data-ttu-id="75867-125">Wählen Sie abschließend **Erstellen** aus.</span><span class="sxs-lookup"><span data-stu-id="75867-125">When you are done, choose **Create**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="75867-126">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="75867-126">Next steps</span></span>

<span data-ttu-id="75867-127">Weisen Sie das Profil den entsprechenden iOS-Geräten zu.</span><span class="sxs-lookup"><span data-stu-id="75867-127">Assign the profile to the required iOS devices.</span></span> <span data-ttu-id="75867-128">Weitere Informationen und Anweisungen finden Sie unter [Zuweisen von Geräteprofilen](device-profile-assign.md).</span><span class="sxs-lookup"><span data-stu-id="75867-128">For more information, use the steps in [How to assign device profiles](device-profile-assign.md).</span></span>
