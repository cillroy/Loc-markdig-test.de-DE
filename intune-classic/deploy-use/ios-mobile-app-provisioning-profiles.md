---
title: App-Bereitstellungsprofile
description: "Intune stellt Ihnen die Tools zum proaktiven Bereitstellen einer neuen Richtlinie für Bereitstellungsprofile auf Geräten zur Verfügung, auf denen Apps installiert sind, die bald ablaufen."
keywords: 
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 12/27/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 86fbe736-7bdb-4f5e-ae21-13c91eb2462c
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 7ffd9066928e38fa09c97538859a78376ea506ae
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2018
---
# <a name="use-ios-mobile-provisioning-profile-policies-to-prevent-your-apps-from-expiring"></a><span data-ttu-id="5e7af-103">Verwenden von Richtlinien für mobile iOS-Bereitstellungsprofile, um zu verhindern, dass Apps ablaufen</span><span class="sxs-lookup"><span data-stu-id="5e7af-103">Use iOS mobile provisioning profile policies to prevent your apps from expiring</span></span>

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="5e7af-104">Die auf iPhones und iPads bereitgestellten branchenspezifischen Apple iOS-Apps wurden mit integriertem Bereitstellungsprofil und per Zertifikat signiertem Code erstellt.</span><span class="sxs-lookup"><span data-stu-id="5e7af-104">Apple iOS line of business apps that are deployed to iPhones and iPads are built with an included provisioning profile and code that is signed with a certificate.</span></span> <span data-ttu-id="5e7af-105">Beim Ausführen der App bestätigt iOS die Integrität der iOS-App und erzwingt Richtlinien, die durch das Bereitstellungsprofil definiert werden.</span><span class="sxs-lookup"><span data-stu-id="5e7af-105">When the app is run, iOS confirms the integrity of the iOS app and enforces policies that are defined by the provisioning profile.</span></span> <span data-ttu-id="5e7af-106">Folgende Überprüfungen finden statt:</span><span class="sxs-lookup"><span data-stu-id="5e7af-106">The following validations happen:</span></span>

- <span data-ttu-id="5e7af-107">**Integrität der Installationsdateien**: iOS vergleicht die Details der App mit dem öffentlichen Schlüssel des Unternehmenssignaturzertifikats.</span><span class="sxs-lookup"><span data-stu-id="5e7af-107">**Installation file integrity** - iOS compares the app's details with the enterprise signing certificate's public key.</span></span> <span data-ttu-id="5e7af-108">Wenn Unterschiede festgestellt werden, wurde der Inhalt der App möglicherweise verändert, und die Ausführung der App wird nicht zugelassen.</span><span class="sxs-lookup"><span data-stu-id="5e7af-108">If they differ, the app's content might have changed, and the app will not be allowed to run.</span></span>
- <span data-ttu-id="5e7af-109">**Erzwingen von Funktionen**: iOS versucht, die App-Funktionen aus dem Bereitstellungsprofil des Unternehmens (nicht den Bereitstellungsprofilen der einzelnen Entwickler) zu erzwingen, die in der App-Installationsdatei (IPA) enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="5e7af-109">**Capabilities enforcement** - iOS attempts to enforce the app's capabilities from the enterprise provisioning profile (not individual developer provisioning profiles) that are in the app installation (.ipa) file.</span></span>


<span data-ttu-id="5e7af-110">Das Unternehmenssignaturzertifikat, das Sie zum Signieren von Apps verwenden, ist in der Regel drei Jahre lang gültig.</span><span class="sxs-lookup"><span data-stu-id="5e7af-110">The enterprise signing certificate that you use to sign apps typically lasts for three years.</span></span> <span data-ttu-id="5e7af-111">Allerdings läuft das Bereitstellungsprofil nach einem Jahr ab.</span><span class="sxs-lookup"><span data-stu-id="5e7af-111">However, the provisioning profile expires after a year.</span></span> <span data-ttu-id="5e7af-112">Während das Zertifikat noch gültig ist, stellt Intune Ihnen die Tools zum proaktiven Bereitstellen einer neuen Richtlinie für Bereitstellungsprofile auf Geräten zur Verfügung, auf denen Apps installiert sind, die bald ablaufen.</span><span class="sxs-lookup"><span data-stu-id="5e7af-112">While the certificate is still valid, Intune gives you the tools to proactively deploy a new provisioning profile policy to devices that have apps that are nearing expiry.</span></span>
<span data-ttu-id="5e7af-113">Nach Ablauf des Zertifikats müssen Sie die App mit einem neuen Zertifikat erneut signieren und ein neues Bereitstellungsprofil mit dem Schlüssel des neuen Zertifikats einbetten.</span><span class="sxs-lookup"><span data-stu-id="5e7af-113">After the certificate expires, you must sign the app again with a new certificate and embed a new provisioning profile with the key of the new certificate.</span></span>



## <a name="how-to-find-out-when-a-line-of-business-app-will-expire"></a><span data-ttu-id="5e7af-114">Herausfinden, wann eine Branchen-App abläuft</span><span class="sxs-lookup"><span data-stu-id="5e7af-114">How to find out when a line of business app will expire</span></span>

1. <span data-ttu-id="5e7af-115">Wählen Sie in der [Microsoft Intune-Verwaltungskonsole](https://manage.microsoft.com) die Optionen **Apps** > **Apps** aus.</span><span class="sxs-lookup"><span data-stu-id="5e7af-115">In the [Microsoft Intune administration console](https://manage.microsoft.com), choose **Apps** > **Apps**.</span></span>
2. <span data-ttu-id="5e7af-116">Überprüfen Sie in der App-Liste die Spalte **Ablaufdatum**, um das Ablaufdatum für die App zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="5e7af-116">In the list of apps, look at the **Expiration date** column to see the expiry date for the app.</span></span> <span data-ttu-id="5e7af-117">Sie können auch die Dropdownliste **Filter** auf **Abgelaufen oder bald abgelaufen** festlegen, um nur die Apps anzuzeigen, für die Sie Maßnahmen ergreifen müssen.</span><span class="sxs-lookup"><span data-stu-id="5e7af-117">You can also set the **Filters** drop-down list to **Expired/about to expire** to see only the apps for which you must take action.</span></span>

## <a name="how-to-create-an-ios-mobile-provisioning-profile-policy"></a><span data-ttu-id="5e7af-118">Erstellen einer Richtlinie für mobile iOS-Bereitstellungsprofile</span><span class="sxs-lookup"><span data-stu-id="5e7af-118">How to create an iOS mobile provisioning profile policy</span></span>


1. <span data-ttu-id="5e7af-119">Klicken Sie in der [Microsoft Intune-Verwaltungskonsole](https://manage.microsoft.com) auf **Richtlinie** > **Übersicht** > **Richtlinie hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="5e7af-119">In the [Microsoft Intune administration console](https://manage.microsoft.com), choose **Policy** > **Overview** > **Add Policy**.</span></span>
2. <span data-ttu-id="5e7af-120">Wählen Sie im Dialogfeld **Neue Richtlinie erstellen** erst die Optionen **iOS** > **Richtlinie für mobiles Bereitstellungsprofil** und dann **Richtlinie erstellen** aus.</span><span class="sxs-lookup"><span data-stu-id="5e7af-120">In the **Create a New Policy** dialog box, choose **iOS** > **Mobile Provisioning Profile Policy**, and then choose **Create Policy**.</span></span>
3. <span data-ttu-id="5e7af-121">Konfigurieren Sie auf der Seite **Allgemein** die folgenden Werte:</span><span class="sxs-lookup"><span data-stu-id="5e7af-121">On the **General** page, configure the following values:</span></span>
    - <span data-ttu-id="5e7af-122">**Name**: Stellen Sie einen Namen für diese Richtlinie für ein mobiles Bereitstellungsprofil bereit.</span><span class="sxs-lookup"><span data-stu-id="5e7af-122">**Name** - Provide a name for this mobile provisioning profile policy.</span></span>
    - <span data-ttu-id="5e7af-123">**Beschreibung**: Geben Sie optional eine Beschreibung der Richtlinie ein.</span><span class="sxs-lookup"><span data-stu-id="5e7af-123">**Description** - Optionally, provide a description for the policy.</span></span>
    - <span data-ttu-id="5e7af-124">**Konfigurationsprofildatei**: Klicken Sie auf **Importieren**, und wählen Sie eine Datei mit einem mobilen Apple-Konfigurationsprofil (mit der Erweiterung **.mobileprovision**) aus, die Sie von der Apple Developer-Website heruntergeladen haben.</span><span class="sxs-lookup"><span data-stu-id="5e7af-124">**Configuration profile file** - Click **Import**, and then choose an Apple Mobile Configuration Profile file (with the extension **.mobileprovision**) that you downloaded from the Apple Developer website.</span></span>
4. <span data-ttu-id="5e7af-125">Wählen Sie abschließend **Richtlinie speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="5e7af-125">When you are done, choose **Save Policy**.</span></span>
5. <span data-ttu-id="5e7af-126">Stellen Sie jetzt die Richtlinie auf den erforderlichen iOS-Geräten bereit.</span><span class="sxs-lookup"><span data-stu-id="5e7af-126">Now, deploy the policy to the required iOS devices.</span></span> <span data-ttu-id="5e7af-127">Weitere Informationen finden Sie unter [Verwalten von Einstellungen und Features auf Ihren Geräten mit Microsoft Intune-Richtlinien](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md).</span><span class="sxs-lookup"><span data-stu-id="5e7af-127">For more information, see [Manage settings and features on your devices with Microsoft Intune policies](manage-settings-and-features-on-your-devices-with-microsoft-intune-policies.md).</span></span>
