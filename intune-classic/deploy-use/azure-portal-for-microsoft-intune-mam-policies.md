---
title: "Azure-Portal für MAM-Richtlinien"
description: "Erstellen Sie Verwaltungsrichtlinien für mobile Apps mithilfe des Azure-Portals. Die Richtlinien, die Sie hier erstellen, können auf Geräte mit oder ohne Registrierung in Intune angewendet werden."
keywords: 
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 10/22/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 7d6dae94-a833-40b7-9016-14ea234bb33c
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: joglocke
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: ccc31a4f999c0d78256fec44dd54cc4a519df9ea
ms.sourcegitcommit: e37e916e2bf14f092d3a767bc90d68c181d739fb
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/03/2018
---
# <a name="azure-portal-for-intune-app-protection-policies"></a><span data-ttu-id="ddeaf-104">Azure-Portal für App-Schutzrichtlinien für Intune</span><span class="sxs-lookup"><span data-stu-id="ddeaf-104">Azure portal for Intune app protection policies</span></span>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="ddeaf-105">Das Azure-Portal wird verwendet, um App-Schutzrichtlinien für folgende Apps zu verwalten:</span><span class="sxs-lookup"><span data-stu-id="ddeaf-105">The Azure portal is used to create and manage app protection policies for:</span></span>

- <span data-ttu-id="ddeaf-106">Apps, die auf Geräten ausgeführt werden, die **in Intune registriert und verwaltet** werden.</span><span class="sxs-lookup"><span data-stu-id="ddeaf-106">Apps running on devices that are **enrolled and managed in Intune**.</span></span>

- <span data-ttu-id="ddeaf-107">Apps, die auf Geräten ausgeführt werden, die **nicht** in einer MDM-Lösung registriert sind.</span><span class="sxs-lookup"><span data-stu-id="ddeaf-107">Apps running on devices that are **not enrolled** in any MDM solution.</span></span>
- <span data-ttu-id="ddeaf-108">Apps, die auf Geräten ausgeführt werden, die **in einer MDM-Lösung von Drittanbietern registriert sind**.</span><span class="sxs-lookup"><span data-stu-id="ddeaf-108">Apps running on devices that are **enrolled in a third-party MDM solution**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ddeaf-109">Das Azure-Portal ist die neue Administratorkonsole für die Erstellung von App-Schutzrichtlinien. Sie können jedoch auch eine App-Schutzrichtlinie erstellen, die Apps für Geräte unterstützt, die bei Intune registriert sind, indem Sie die [Intune-Verwaltungskonsole](configure-and-deploy-mobile-application-management-policies-in-the-microsoft-intune-console.md) für MDM-Szenarios verwenden.</span><span class="sxs-lookup"><span data-stu-id="ddeaf-109">The Azure portal is the new admin console for creating app protection policies, but you can also create an app protection policy that supports apps for devices enrolled into Intune by using the [Intune admin console](configure-and-deploy-mobile-application-management-policies-in-the-microsoft-intune-console.md) for MDM scenarios.</span></span>
> 
> <span data-ttu-id="ddeaf-110">Möglicherweise sind in der Intune-Verwaltungskonsole nicht alle App-Schutzrichtlinieneinstellungen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="ddeaf-110">You might not see all the app protection policy settings available on the Intune admin console.</span></span> <span data-ttu-id="ddeaf-111">Darüber hinaus werden die Richtlinien, die im Azure-Portal erstellt wurden, die in der Intune-Verwaltungskonsole überschreiben, wenn Sie App-Schutzrichtlinien sowohl in der Intune-Verwaltungskonsole als auch im Azure-Portal erstellen.</span><span class="sxs-lookup"><span data-stu-id="ddeaf-111">Additionally, if you create app protection policies both on the Intune admin console and in the Azure portal, the policies created in the Azure portal will override the ones created on the Intune admin console.</span></span> <span data-ttu-id="ddeaf-112">In diesem Szenario werden die App-Schutzrichtlinien des Azure-Portals auf die Apps angewendet und für Benutzer bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="ddeaf-112">In this scenario, the Azure portal app protection policies will be applied to the apps and deployed to users.</span></span>


## <a name="sign-in-to-the-azure-portal-and-customize-your-start-page"></a><span data-ttu-id="ddeaf-113">Melden Sie sich beim Azure-Portal an, und passen Sie Ihre Startseite an.</span><span class="sxs-lookup"><span data-stu-id="ddeaf-113">Sign in to the Azure portal and customize your start page</span></span>

1.  <span data-ttu-id="ddeaf-114">Navigieren Sie zum [Azure-Portal](https://portal.azure.com) und melden Sie sich mit Ihren Intune-Anmeldeinformationen an.</span><span class="sxs-lookup"><span data-stu-id="ddeaf-114">Go to the [Azure portal](https://portal.azure.com) and sign in with your Intune credentials.</span></span>

    ![Screenshot zur Anmeldeseite des Azure-Portals](../media/AppManagement/AzurePortal_MAMSigninPage.png)

2.  <span data-ttu-id="ddeaf-116">Sobald Sie erfolgreich angemeldet sind, wird das **Dashboard** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="ddeaf-116">After you've successfully signed in, you see the **Dashboard**.</span></span> <span data-ttu-id="ddeaf-117">Die Seite **Dashboard** kann angepasst werden.</span><span class="sxs-lookup"><span data-stu-id="ddeaf-117">The **Dashboard** page can be customized.</span></span>

    ![Screenshot zum Dashboard des Azure-Portals](../media/AppManagement/AzurePortal_MAMStartboard_NoMAM.png)

3.  <span data-ttu-id="ddeaf-119">Wählen Sie im linken Menü **Weitere Dienste** aus, und geben Sie in das Filtertextfeld die Zeichenfolge **Intune** ein.</span><span class="sxs-lookup"><span data-stu-id="ddeaf-119">Choose **More services** from the left menu, then type **Intune** in the text box filter.</span></span>

    ![Screenshot des Menüs „Durchsuchen“ mit hervorgehobenem Intune](../media/AppManagement/MAM-Azure-Portal-1.png)

4.  <span data-ttu-id="ddeaf-121">Wählen Sie **Intune-Schutz für Apps** > **Mobile Anwendungsverwaltung mit Intune** > **Alle Einstellungen** aus.</span><span class="sxs-lookup"><span data-stu-id="ddeaf-121">Choose **Intune App Protection** > **Intune mobile application management** > **All Settings**.</span></span>

    ![Screenshot des Blatts „Mobile Anwendungsverwaltung mit Intune“](../media/AppManagement/MAM-Azure-Portal-2.png)

5. <span data-ttu-id="ddeaf-123">(Optional:)Zum Anheften eines Blatts an die **Startseite** können Sie auf dem Blatt die Option zum **Anheften** verwenden.</span><span class="sxs-lookup"><span data-stu-id="ddeaf-123">(Optional): To pin a blade to the **Start** page, you can use the **pin** option on the blade.</span></span> <span data-ttu-id="ddeaf-124">Klicken Sie auf dem Blatt **Mobile Anwendungsverwaltung mit Intune** auf das Stecknadelsymbol, um das Blatt an die **Startseite** anzuheften.</span><span class="sxs-lookup"><span data-stu-id="ddeaf-124">Click the pin icon on the **Intune mobile application management blade** to pin that blade to the **Start** page.</span></span>

    ![Screenshot des Blatts „Mobile Anwendungsverwaltung mit Intune“ mit hervorgehobenem Pinsymbol](../media/AppManagement/AzurePortal_MAM_PinBladeAction.png)

    ![Screenshot des Dashboards mit angehefteter Intune-Kachel](../media/AppManagement/AzurePortal_MAM_Startboard_withMAM.png)

## <a name="next-steps"></a><span data-ttu-id="ddeaf-127">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="ddeaf-127">Next steps</span></span>
[<span data-ttu-id="ddeaf-128">Vorbereitungen zum Konfigurieren von App-Schutzrichtlinien</span><span class="sxs-lookup"><span data-stu-id="ddeaf-128">Get ready to configure app protection policies</span></span>](get-ready-to-configure-mobile-app-management-policies-with-microsoft-intune.md)
