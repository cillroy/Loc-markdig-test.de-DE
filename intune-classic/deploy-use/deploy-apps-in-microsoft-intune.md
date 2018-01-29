---
title: Bereitstellen von Apps
description: Die Informationen in diesem Thema helfen Ihnen beim Bereitstellen von Apps mit Microsoft Intune.
keywords: 
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 12/27/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3b42019e-73da-4538-a496-212f11d5bf9b
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: c33c522646acb48b02b7b8bc2d97cc0f1db18c6f
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2018
---
# <a name="deploy-apps-in-microsoft-intune"></a><span data-ttu-id="39f1a-103">Bereitstellen von Apps in Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="39f1a-103">Deploy apps in Microsoft Intune</span></span>

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="39f1a-104">Die Informationen in diesem Thema helfen Ihnen beim Bereitstellen von Apps mit Microsoft Intune.</span><span class="sxs-lookup"><span data-stu-id="39f1a-104">Use the information in this topic to help you deploy apps with Microsoft Intune.</span></span>


## <a name="deploy-an-app"></a><span data-ttu-id="39f1a-105">Bereitstellen einer App</span><span class="sxs-lookup"><span data-stu-id="39f1a-105">Deploy an app</span></span>
<span data-ttu-id="39f1a-106">Bei dieser Vorgehensweise stellen Sie die App für ausgewählte Gruppen von Geräten oder für ausgewählte Benutzer bereit.</span><span class="sxs-lookup"><span data-stu-id="39f1a-106">In this procedure, you'll deploy an app to selected groups of devices or users.</span></span>

### <a name="to-deploy-an-app"></a><span data-ttu-id="39f1a-107">So stellen Sie eine App bereit</span><span class="sxs-lookup"><span data-stu-id="39f1a-107">To deploy an app</span></span>

1. <span data-ttu-id="39f1a-108">Klicken Sie in der [Microsoft Intune-Administratorkonsole](https://manage.microsoft.com) auf **Apps** &gt; **Apps**, um die Liste der von Ihnen verwalteten Apps anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="39f1a-108">In the [Microsoft Intune administration console](https://manage.microsoft.com), click **Apps** &gt; **Apps** to view the list of apps that you manage.</span></span>

2.  <span data-ttu-id="39f1a-109">Wählen Sie die bereitzustellende App aus, und klicken Sie anschließend auf **Bereitstellung verwalten**.</span><span class="sxs-lookup"><span data-stu-id="39f1a-109">Select the app that you want to deploy, and then click **Manage Deployment**.</span></span>

3.  <span data-ttu-id="39f1a-110">Wählen Sie im Dialogfeld *&lt;Name der App&gt;* auf der Seite **Gruppen auswählen** die Benutzer- oder Gerätegruppen aus, für die die App bereitgestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="39f1a-110">In the *&lt;app name&gt;* dialog box, on the **Select Groups** page, choose the user or device groups to which you want to deploy the app.</span></span>

4.  <span data-ttu-id="39f1a-111">Konfigurieren Sie auf der Seite **Bereitstellungsaktion** Folgendes:</span><span class="sxs-lookup"><span data-stu-id="39f1a-111">On the **Deployment Action** page, configure the following:</span></span>

    - <span data-ttu-id="39f1a-112">**Genehmigung** – Legen Sie den Status der Bereitstellung fest:</span><span class="sxs-lookup"><span data-stu-id="39f1a-112">**Approval** - Choose whether the deployment is:</span></span>
        - <span data-ttu-id="39f1a-113">**Erforderlich** (die Installation ist obligatorisch)</span><span class="sxs-lookup"><span data-stu-id="39f1a-113">**Required** (mandatory install)</span></span>
        - <span data-ttu-id="39f1a-114">**Verfügbar** (Benutzer installieren die App über das Unternehmensportal nach Bedarf)</span><span class="sxs-lookup"><span data-stu-id="39f1a-114">**Available** (users install from the company portal on demand)</span></span>
        - <span data-ttu-id="39f1a-115">**Nicht verfügbar** (die App wird nicht installiert und nicht im Unternehmensportal angezeigt)</span><span class="sxs-lookup"><span data-stu-id="39f1a-115">**Not Applicable** (the app is not installed or shown in the company portal)</span></span>
        - <span data-ttu-id="39f1a-116">**Deinstallieren** (die App wird von den Zielgeräten deinstalliert).</span><span class="sxs-lookup"><span data-stu-id="39f1a-116">**Uninstall** (the app is uninstalled from targeted devices)</span></span>
    - <span data-ttu-id="39f1a-117">**Stichtag** – Geben Sie für erforderliche Installationen an, wann die App bereitgestellt werden soll.</span><span class="sxs-lookup"><span data-stu-id="39f1a-117">**Deadline** - For required installations, choose how soon to deploy the app.</span></span> <span data-ttu-id="39f1a-118">Sie können entweder vordefinierte Werte oder **Benutzerdefiniert** auswählen, um einen eigenen Stichtag zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="39f1a-118">You can choose from the predefined values, or you can select **Custom** to configure your own deadline.</span></span>

5. <span data-ttu-id="39f1a-119">Wenn die bereitzustellende App mithilfe einer Richtlinie für die Verwaltung mobiler Anwendungen konfiguriert werden kann, wird die Seite **Verwaltung mobiler Apps** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="39f1a-119">If the app you are deploying can be configured by a mobile application management policy, the **Mobile App Management** page is displayed.</span></span> <span data-ttu-id="39f1a-120">Wählen Sie auf dieser Seite die Richtlinie für die mobile Anwendungsverwaltung aus, die Sie dieser App zuordnen möchten.</span><span class="sxs-lookup"><span data-stu-id="39f1a-120">On this page, choose the mobile application management policy that you want to associate with this app.</span></span>

    [<span data-ttu-id="39f1a-121">Informieren Sie sich, welche Microsoft-Apps mit Richtlinien für die Verwaltung mobiler Anwendungen kompatibel sind.</span><span class="sxs-lookup"><span data-stu-id="39f1a-121">See which Microsoft apps are compatible with mobile application management policies.</span></span>](https://www.microsoft.com/server-cloud/products/microsoft-intune/partners.aspx)

6. <span data-ttu-id="39f1a-122">Wenn die bereitzustellende App mit Intune-VPN-Profilen kompatibel ist, wird die Seite **VPN-Profil** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="39f1a-122">If the app you are deploying is compatible with Intune VPN profiles, the **VPN Profile** page is displayed.</span></span> <span data-ttu-id="39f1a-123">Auf dieser Seite können Sie festlegen, dass iOS-Apps mit einem von Ihnen bereitgestellten VPN-Profil verknüpft werden sollen.</span><span class="sxs-lookup"><span data-stu-id="39f1a-123">On this page, you can choose to associate iOS apps with a VPN profile that you have deployed.</span></span> <span data-ttu-id="39f1a-124">Die VPN-Verbindung wird automatisch geöffnet, wenn die App gestartet wird.</span><span class="sxs-lookup"><span data-stu-id="39f1a-124">The VPN connection automatically opens when the app is launched.</span></span> <span data-ttu-id="39f1a-125">Um ein VPN-Profil verfügbar zu machen, müssen Sie die Profileinstellung **VPN pro App** aktivieren.</span><span class="sxs-lookup"><span data-stu-id="39f1a-125">To make a VPN profile available, it must have the **Per-app VPN** profile setting enabled.</span></span>
 <span data-ttu-id="39f1a-126">Informationen zum Konfigurieren von VPN-Profilen, einschließlich Informationen zum Verknüpfen von Profilen mit Apps, finden Sie unter [VPN-Verbindungen in Microsoft Intune](vpn-connections-in-microsoft-intune.md).</span><span class="sxs-lookup"><span data-stu-id="39f1a-126">For information about how to configure VPN profiles, including information about how to associate profiles with apps, see [VPN connections in Microsoft Intune](vpn-connections-in-microsoft-intune.md).</span></span>

<!---
>[!TIP]
>If an end user previously installed an iOS app and you now deploy it with a deployment action of **Available**, Intune will automatically begin to manage that app with no further action required by you, or the end-user.
--->

## <a name="example"></a><span data-ttu-id="39f1a-127">Beispiel</span><span class="sxs-lookup"><span data-stu-id="39f1a-127">Example</span></span>

<span data-ttu-id="39f1a-128">In diesem Beispiel haben Sie die App als **Verfügbar** für ein iOS-Gerät bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="39f1a-128">In this example, you deployed the app as **Available** to an iOS device.</span></span>
<span data-ttu-id="39f1a-129">Die App wird für Benutzergeräte im Unternehmensportal angezeigt. Die Benutzer können die App vom Portal aus installieren.</span><span class="sxs-lookup"><span data-stu-id="39f1a-129">The app displays on users' devices in the company portal, and users can install it from there.</span></span>

<span data-ttu-id="39f1a-130">In diesem Screenshot wurde z. B. die App „Bing for iOS“ mit dem Installationstyp **Externer Link** zusammen mit einem benutzerdefinierten Symbol bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="39f1a-130">For example, in this screenshot, the Bing for iOS app was deployed by using the **External Link** installation type with a custom icon.</span></span> <span data-ttu-id="39f1a-131">Die Option **Als ausgewählte App anzeigen und im Unternehmensportal hervorheben** wurde ausgewählt.</span><span class="sxs-lookup"><span data-stu-id="39f1a-131">The option **Display this as a featured app and highlight it in the company portal** was selected.</span></span>  
<span data-ttu-id="39f1a-132">![Verfügbare iOS-App](./media/available-install-on-iOS.png)</span><span class="sxs-lookup"><span data-stu-id="39f1a-132">![iOS available app](./media/available-install-on-iOS.png)</span></span>

<span data-ttu-id="39f1a-133">Wenn Sie die App als **Erforderlich** für ein iOS-Gerät bereitgestellt haben, wird der Benutzer benachrichtigt, dass diese App zur Installation bereitsteht.</span><span class="sxs-lookup"><span data-stu-id="39f1a-133">If you deployed the app as **Required** to an iOS device, the user will get a notification that an app is ready to install.</span></span> <span data-ttu-id="39f1a-134">In diesem Screenshot wurde z. B. die App „Work Folders for iOS“ mit dem Installationstyp **Verwaltete iOS-App aus dem App Store** bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="39f1a-134">For example, in this screenshot, the Work Folders for iOS app was deployed by using the **Managed iOS app from the app store** installation type.</span></span>  
<span data-ttu-id="39f1a-135">![Erforderliche iOS-App](./media/iOS-Required-install.PNG)</span><span class="sxs-lookup"><span data-stu-id="39f1a-135">![iOS required app](./media/iOS-Required-install.PNG)</span></span>

## <a name="next-steps"></a><span data-ttu-id="39f1a-136">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="39f1a-136">Next steps</span></span>

<span data-ttu-id="39f1a-137">Nachdem Sie eine Anwendung bereitgestellt haben, ist es sinnvoll, deren Status zu überwachen.</span><span class="sxs-lookup"><span data-stu-id="39f1a-137">After you deploy an app, you'll want to monitor its progress.</span></span> <span data-ttu-id="39f1a-138">Weitere Informationen finden Sie unter [Überwachen von Apps in Microsoft Intune](monitor-apps-in-microsoft-intune.md).</span><span class="sxs-lookup"><span data-stu-id="39f1a-138">For more information, see [Monitor apps in Microsoft Intune](monitor-apps-in-microsoft-intune.md).</span></span>
