---
title: "Allgemeine Tipps für die Problembehandlung"
description: "Allgemeine Ressourcen zur Lösung von Problemen mit Intune"
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 12/08/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c86a4e4a-6b9f-4835-a3d3-61a3f5f4c1ec
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: tscott
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 5ed8e03330e7d81d3bbe7d3c1810585d70791fba
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2018
---
# <a name="general-troubleshooting-tips-for-microsoft-intune"></a><span data-ttu-id="db4cf-103">Allgemeine Tipps für die Problembehandlung für Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="db4cf-103">General troubleshooting tips for Microsoft Intune</span></span>

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="db4cf-104">Nach der Bereitstellung von Microsoft Intune können möglicherweise Probleme bei der Konfiguration oder mit Clientgeräten auftreten.</span><span class="sxs-lookup"><span data-stu-id="db4cf-104">After you deploy Microsoft Intune, you might encounter problems with your configuration or with client devices.</span></span> <span data-ttu-id="db4cf-105">Die folgenden Ressourcen helfen Ihnen, die Ursache des Problems herauszufinden, sodass Sie es beheben können.</span><span class="sxs-lookup"><span data-stu-id="db4cf-105">Use the following resources to help you discover what's causing the problem so you can resolve it.</span></span>

> [!NOTE]
> <span data-ttu-id="db4cf-106">Um eine Supportanfrage zu erstellen oder eine vorhandene Anfrage anzuzeigen, [besuchen Sie das Office 365 Admin Center](https://portal.office.com/admin/default.aspx).</span><span class="sxs-lookup"><span data-stu-id="db4cf-106">To create a support request, or to view an existing request, [visit the Office 365 admin center](https://portal.office.com/admin/default.aspx).</span></span> <span data-ttu-id="db4cf-107">Weitere Informationen zu Supportoptionen finden Sie unter [Anfordern von Support für Microsoft Intune](how-to-get-support-for-microsoft-intune.md).</span><span class="sxs-lookup"><span data-stu-id="db4cf-107">For more information about support options, see [How to get support for Microsoft Intune](how-to-get-support-for-microsoft-intune.md).</span></span>

## <a name="define-the-problem"></a><span data-ttu-id="db4cf-108">Definieren des Problems</span><span class="sxs-lookup"><span data-stu-id="db4cf-108">Define the problem</span></span>

-   <span data-ttu-id="db4cf-109">Beschreiben Sie das Verhalten.</span><span class="sxs-lookup"><span data-stu-id="db4cf-109">What is the behavior?</span></span>

-   <span data-ttu-id="db4cf-110">Bei wem und auf welchen Plattformen und Geräten ist dieses Verhalten aufgetreten?</span><span class="sxs-lookup"><span data-stu-id="db4cf-110">Who experiences this behavior, and on what platforms and devices?</span></span>

-   <span data-ttu-id="db4cf-111">Funktionierte das Gerät zuvor ordnungsgemäß?</span><span class="sxs-lookup"><span data-stu-id="db4cf-111">Did the device work properly previously?</span></span>

-   <span data-ttu-id="db4cf-112">Welche Änderungen haben Sie an der Intune- oder Gerätekonfiguration vorgenommen?</span><span class="sxs-lookup"><span data-stu-id="db4cf-112">What changes did you make to the Intune or device configuration?</span></span>

-   <span data-ttu-id="db4cf-113">Wurden an der Umgebung, in der Sie arbeiten, andere Änderungen als Änderungen an der Konfiguration vorgenommen?</span><span class="sxs-lookup"><span data-stu-id="db4cf-113">Were other changes were made to the environment in which you operate, other than configuration changes?</span></span>

-   <span data-ttu-id="db4cf-114">Wie häufig tritt dieses Problem auf, und tritt es sporadisch oder dauerhaft auf?</span><span class="sxs-lookup"><span data-stu-id="db4cf-114">How frequently does this problem occur, and is it sporadic or consistent?</span></span>

-   <span data-ttu-id="db4cf-115">Könnte beim Benutzer ein Authentifizierungsproblem vorliegen?</span><span class="sxs-lookup"><span data-stu-id="db4cf-115">Could the user be experiencing an authentication issue?</span></span> <span data-ttu-id="db4cf-116">Wenn diese Möglichkeit besteht, überprüfen Sie, ob der Benutzer sich bei anderen Diensten, die Azure Active Directory verwenden, anmelden kann.</span><span class="sxs-lookup"><span data-stu-id="db4cf-116">If this is a possiblity, see if the user can sign in to other services that use Azure Active Directory.</span></span> <span data-ttu-id="db4cf-117">Prüfen Sie auch, ob der Benutzer sich von einem anderen Gerät aus anmelden kann.</span><span class="sxs-lookup"><span data-stu-id="db4cf-117">Also, see if the user can sign in from a different device.</span></span>

-   <span data-ttu-id="db4cf-118">Haben Sie den Dienststatus überprüft?</span><span class="sxs-lookup"><span data-stu-id="db4cf-118">Have you checked the service status?</span></span> <span data-ttu-id="db4cf-119">Sie können Intune-Dienststatus im [Verwaltungsportal von Office 365](https://portal.office.com/Admin/Default.aspx) überwachen.</span><span class="sxs-lookup"><span data-stu-id="db4cf-119">You can monitor Intune service health in the [Office 365 management portal](https://portal.office.com/Admin/Default.aspx).</span></span> <span data-ttu-id="db4cf-120">Wählen Sie im linken Bereich **Dienststatus** aus.</span><span class="sxs-lookup"><span data-stu-id="db4cf-120">Choose **Service Health** in the left pane.</span></span>

## <a name="collect-available-data"></a><span data-ttu-id="db4cf-121">Sammeln Sie verfügbare Daten</span><span class="sxs-lookup"><span data-stu-id="db4cf-121">Collect available data</span></span>

- <span data-ttu-id="db4cf-122">In den folgenden Ressourcen wird erläutert, wie Sie Geräteprotokolle erfassen:</span><span class="sxs-lookup"><span data-stu-id="db4cf-122">The following resources can help you learn how to collect device logs:</span></span>
  - [<span data-ttu-id="db4cf-123">Senden von Android-Diagnosedatenprotokollen an Ihren IT-Administrator über ein USB-Kabel</span><span class="sxs-lookup"><span data-stu-id="db4cf-123">Send Android diagnostic data logs to your IT administrator using a USB cable</span></span>](/intune-user-help/send-diagnostic-data-logs-to-your-it-administrator-using-a-usb-cable-android)
  - [<span data-ttu-id="db4cf-124">Senden von Android-Diagnosedatenprotokollen an Ihren IT-Administrator per E-Mail</span><span class="sxs-lookup"><span data-stu-id="db4cf-124">Send Android diagnostic data logs to your IT administrator using email</span></span>](/intune-user-help/send-diagnostic-data-logs-to-your-it-administrator-using-email-android)
  - [<span data-ttu-id="db4cf-125">Senden von Android-Registrierungsfehlern an Ihren IT-Administrator</span><span class="sxs-lookup"><span data-stu-id="db4cf-125">Send Android enrollment errors to your IT administrator</span></span>](/intune-user-help/send-enrollment-errors-to-your-it-administrator-android)
  - [<span data-ttu-id="db4cf-126">Senden von iOS-Registrierungsfehlern an Ihren IT-Administrator</span><span class="sxs-lookup"><span data-stu-id="db4cf-126">Send iOS enrollment errors to your IT administrator</span></span>](/intune-user-help/send-errors-to-your-it-admin-ios)

- <span data-ttu-id="db4cf-127">Bei Verwaltungskonsolendaten (z. B. bei Problemen mit der Richtlinienimplementierung) überprüfen Sie die gewünschte Richtlinie und den Status dieser Richtlinie, wie in [Erstellen von Gruppen zum Verwalten von Benutzern und Geräten in Microsoft Intune](/intune-classic/deploy-use/use-groups-to-manage-users-and-devices-with-microsoft-intune) beschrieben.</span><span class="sxs-lookup"><span data-stu-id="db4cf-127">With admin console data (for example, for policy implementation issues), examine the intended policy and the status of that policy, as described in [Use groups to manage users and devices with Microsoft Intune](/intune-classic/deploy-use/use-groups-to-manage-users-and-devices-with-microsoft-intune).</span></span>

## <a name="research-the-solution"></a><span data-ttu-id="db4cf-128">Recherchieren der Lösung</span><span class="sxs-lookup"><span data-stu-id="db4cf-128">Research the solution</span></span>

-   <span data-ttu-id="db4cf-129">Suchen Sie im Internet nach einer Lösung.</span><span class="sxs-lookup"><span data-stu-id="db4cf-129">Search the Web for a solution.</span></span> <span data-ttu-id="db4cf-130">Wenn Sie z. B. den Fehler 0x80073CF0 erhalten, suchen Sie im Internet nach **Technet Intune 0x80073cf0** und finden den Artikel [Behandlung von Problemen mit der App-Bereitstellung in Microsoft Intune](troubleshoot-app-deployment-problems-in-microsoft-intune.md).</span><span class="sxs-lookup"><span data-stu-id="db4cf-130">For example, if you receive the error 0x80073CF0, search for **technet intune 0x80073cf0** on the Web, and you'll find the article [Troubleshoot app deployment problems in Microsoft Intune](troubleshoot-app-deployment-problems-in-microsoft-intune.md).</span></span> <span data-ttu-id="db4cf-131">Der Artikel enthält Vorschläge zur Behebung dieses Fehlers.</span><span class="sxs-lookup"><span data-stu-id="db4cf-131">This article offers suggestions for addressing this error.</span></span>

-   <span data-ttu-id="db4cf-132">Suchen Sie im [Intune TechNet-Forum](https://social.technet.microsoft.com/Forums/en-US/home?forum=microsoftintuneprod) nach einer Antwort.</span><span class="sxs-lookup"><span data-stu-id="db4cf-132">Search for an answer in the [Intune TechNet forum](https://social.technet.microsoft.com/Forums/en-US/home?forum=microsoftintuneprod).</span></span>  <span data-ttu-id="db4cf-133">Wenn das Problem noch nicht behandelt wurde, stellen Sie Ihre Fragen im Forum, um zu schauen, welche Lösungsvorschläge von der Community kommen.</span><span class="sxs-lookup"><span data-stu-id="db4cf-133">If the issue hasn't been previously addressed, post the question to see what suggestions the community might have.</span></span>

-   <span data-ttu-id="db4cf-134">Öffnen Sie eine Supportanfrage.</span><span class="sxs-lookup"><span data-stu-id="db4cf-134">Open a support request.</span></span> <span data-ttu-id="db4cf-135">Das Intune-Supportteam kann Sie bei der Problembehandlung besser unterstützen, wenn Sie das Problem definiert und die verfügbaren Daten erfasst haben.</span><span class="sxs-lookup"><span data-stu-id="db4cf-135">Intune Support will be better able to help you resolve an issue after you've defined the problem and have collected the available data.</span></span>

    <span data-ttu-id="db4cf-136">Zum Erstellen einer Supportanfrage [besuchen Sie das Office 365 Admin Center](https://portal.office.com/admin/default.aspx).</span><span class="sxs-lookup"><span data-stu-id="db4cf-136">To create a support request, [visit the Office 365 admin center](https://portal.office.com/admin/default.aspx).</span></span> <span data-ttu-id="db4cf-137">Weitere Informationen zu Supportoptionen finden Sie unter [Anfordern von Support für Microsoft Intune](how-to-get-support-for-microsoft-intune.md).</span><span class="sxs-lookup"><span data-stu-id="db4cf-137">For more information about support options, see [How to get support for Microsoft Intune](how-to-get-support-for-microsoft-intune.md).</span></span>

## <a name="find-community-resources"></a><span data-ttu-id="db4cf-138">Suchen von Communityressourcen</span><span class="sxs-lookup"><span data-stu-id="db4cf-138">Find community resources</span></span>
<span data-ttu-id="db4cf-139">Weitere hilfreiche Informationen finden Sie in diesen Communityressourcen:</span><span class="sxs-lookup"><span data-stu-id="db4cf-139">You can find other helpful information in these community resources:</span></span>

-   <span data-ttu-id="db4cf-140">Der [Microsoft Intune Survival Guide](http://social.technet.microsoft.com/wiki/contents/articles/23431.microsoft-intune-survival-guide.aspx) enthält Links zu vielen Ressourcen, die Sie beim Konfigurieren, Verwalten und beim Beheben von Problemen mit Intune unterstützen können.</span><span class="sxs-lookup"><span data-stu-id="db4cf-140">The [Microsoft Intune Survival Guide](http://social.technet.microsoft.com/wiki/contents/articles/23431.microsoft-intune-survival-guide.aspx) contains links to many resources that can help you configure, maintain, and troubleshoot Intune.</span></span>

-   [<span data-ttu-id="db4cf-141">Intune-Blog</span><span class="sxs-lookup"><span data-stu-id="db4cf-141">The Intune blog</span></span>](http://blogs.technet.com/b/windowsintune/)

-   [<span data-ttu-id="db4cf-142">Folgen Sie Intune auf Twitter</span><span class="sxs-lookup"><span data-stu-id="db4cf-142">Follow Intune on Twitter</span></span>](https://twitter.com/MSIntune)

-   [<span data-ttu-id="db4cf-143">Intune-Foren</span><span class="sxs-lookup"><span data-stu-id="db4cf-143">The Intune forums</span></span>](https://social.technet.microsoft.com/Forums/home?category=microsoftintune&filter=alltypes&sort=lastpostdesc)

### <a name="next-steps"></a><span data-ttu-id="db4cf-144">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="db4cf-144">Next steps</span></span>
<span data-ttu-id="db4cf-145">Die folgenden Themen enthalten Hilfe zur Behandlung bestimmter Probleme.</span><span class="sxs-lookup"><span data-stu-id="db4cf-145">The following topics have troubleshooting help for specific issues.</span></span> <span data-ttu-id="db4cf-146">Wenn diese Informationen für Sie nicht hilfreich waren, wenden Sie sich wie in [Anfordern von Support für Microsoft Intune](how-to-get-support-for-microsoft-intune.md) beschrieben an den Microsoft Support.</span><span class="sxs-lookup"><span data-stu-id="db4cf-146">If that information doesn't help you, contact Microsoft Support as described in [How to get support for Microsoft Intune](how-to-get-support-for-microsoft-intune.md).</span></span>

[<span data-ttu-id="db4cf-147">Troubleshoot Endpoint Protection in Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="db4cf-147">Troubleshoot Endpoint Protection in Microsoft Intune</span></span>](troubleshoot-endpoint-protection-in-microsoft-intune.md)

[<span data-ttu-id="db4cf-148">Behandlung von Problemen mit dem Zugriff auf Unternehmensressourcen in Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="db4cf-148">Troubleshoot company resource access problems with Microsoft Intune</span></span>](troubleshoot-company-resource-access-problems-with-microsoft-intune.md)

[<span data-ttu-id="db4cf-149">Behandlung von Problemen mit der App-Bereitstellung in Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="db4cf-149">Troubleshoot app deployment problems in Microsoft Intune</span></span>](troubleshoot-app-deployment-problems-in-microsoft-intune.md)

[<span data-ttu-id="db4cf-150">Behandlung von Problemen bei der Geräteregistrierung bei Intune</span><span class="sxs-lookup"><span data-stu-id="db4cf-150">Troubleshoot device enrollment in Intune</span></span>](troubleshoot-device-enrollment-in-intune.md)

[<span data-ttu-id="db4cf-151">Behandlung von Problemen mit Richtlinien in Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="db4cf-151">Troubleshoot policies in Microsoft Intune</span></span>](troubleshoot-policies-in-microsoft-intune.md)

[<span data-ttu-id="db4cf-152">Behandlung von Problemen bei der Clienteinrichtung in Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="db4cf-152">Troubleshoot client setup in Microsoft Intune</span></span>](troubleshoot-client-setup-in-microsoft-intune.md)

[<span data-ttu-id="db4cf-153">Behandlung von Problemen bei Softwareupdates in Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="db4cf-153">Troubleshoot software updates in Microsoft Intune</span></span>](troubleshoot-software-updates-in-microsoft-intune.md)
