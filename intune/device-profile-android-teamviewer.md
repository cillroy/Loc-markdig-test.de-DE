---
title: "Informationen zur Remoteverwaltung von Geräten mithilfe von TeamViewer"
titlesuffix: Azure portal
description: "In diesem Artikel erfahren Sie, wie Geräte mithilfe von TeamViewer remote verwaltet werden."
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 12/14/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 72cdd888-efca-46e6-b2e7-fb9696bb2fba
ms.reviewer: davidra
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 46e850cdda27444d18354b972d10b0cd02c036d9
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2017
---
# <a name="provide-remote-assistance-for-intune-managed-devices"></a><span data-ttu-id="78ec4-103">Bereitstellen von Remoteunterstützung für mit Intune verwaltete Geräte</span><span class="sxs-lookup"><span data-stu-id="78ec4-103">Provide remote assistance for Intune managed devices</span></span>

<span data-ttu-id="78ec4-104">In Intune kann die nicht im Lieferumfang inbegriffene [TeamViewer](https://www.teamviewer.com)-Software verwendet werden, um den Benutzern von Geräten, die Sie verwalten, Remoteunterstützung zu bieten.</span><span class="sxs-lookup"><span data-stu-id="78ec4-104">Intune can use the [TeamViewer](https://www.teamviewer.com) software, purchased separately, to enable you to give remote assistance to users of devices you manage.</span></span> <span data-ttu-id="78ec4-105">Führen Sie die ersten Schritte gemäß den Informationen in diesem Thema durch.</span><span class="sxs-lookup"><span data-stu-id="78ec4-105">Use the information in this topic to get started.</span></span>

## <a name="before-you-start"></a><span data-ttu-id="78ec4-106">Vorbereitung</span><span class="sxs-lookup"><span data-stu-id="78ec4-106">Before you start</span></span>

### <a name="supported-devices"></a><span data-ttu-id="78ec4-107">Unterstützte Geräte</span><span class="sxs-lookup"><span data-stu-id="78ec4-107">Supported devices</span></span>

<span data-ttu-id="78ec4-108">Mit Intune verwaltete Android- und Windows-Geräte unterstützen Remoteverwaltung.</span><span class="sxs-lookup"><span data-stu-id="78ec4-108">Intune-managed Android and Windows devices support remote administration.</span></span>

>[!NOTE]
><span data-ttu-id="78ec4-109">Windows Holographic (HoloLens), Windows Team (Surface Hub) und Windows 10S werden von der TeamViewer-Software nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="78ec4-109">Windows Holographic (HoloLens), Windows Team (Surface Hub) and Windows 10 S are not supported by the TeamViewer software.</span></span> <span data-ttu-id="78ec4-110">Sie benötigen Sie zum Verwalten von Geräten, die mit der [-PC-Clients](/intune-classic/deploy-use/pc-management-comparison?toc=/intune/toc.json) im klassischen Intune-Portal.</span><span class="sxs-lookup"><span data-stu-id="78ec4-110">You still need to manage devices using the [PC client](/intune-classic/deploy-use/pc-management-comparison?toc=/intune/toc.json) in the Intune classic portal.</span></span>



### <a name="required-permissions"></a><span data-ttu-id="78ec4-111">Erforderliche Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="78ec4-111">Required permissions</span></span>

<span data-ttu-id="78ec4-112">Stellen Sie sicher, dass dem Benutzer des Azure-Portals folgende Berechtigungen als [Intune-Rolle](https://docs.microsoft.com/intune-azure/access-control/role-based-access-control) zugewiesen sind:</span><span class="sxs-lookup"><span data-stu-id="78ec4-112">Ensure that the user of the Azure portal has the following permissions assigned to them as an [Intune role](https://docs.microsoft.com/intune-azure/access-control/role-based-access-control):</span></span>
- <span data-ttu-id="78ec4-113">Damit der Administrator die TeamViewer Connector-Einstellungen ändern kann, erteilen Sie die Berechtigung **Remoteunterstützung aktualisieren**.</span><span class="sxs-lookup"><span data-stu-id="78ec4-113">To let the admin modify the TeamViewer connector settings, grant the **Update Remote Assistance** permission.</span></span>
- <span data-ttu-id="78ec4-114">Damit der Administrator neue Remoteunterstützungsanforderungen initiieren kann, erteilen Sie die Berechtigung **Remoteunterstützung anfordern**.</span><span class="sxs-lookup"><span data-stu-id="78ec4-114">To let the admin initiate a new remote assistance request, grant the **Request Remote Assistance** permission.</span></span> <span data-ttu-id="78ec4-115">Benutzer mit der Berechtigung **Remoteunterstützung anfordern** können für jeden Benutzer die Initiierung einer Sitzung anfordern.</span><span class="sxs-lookup"><span data-stu-id="78ec4-115">Users with the **Request Remote Assistance** permission can request to initiate a session for any user.</span></span> <span data-ttu-id="78ec4-116">Sie werden durch keinen Rollenzuweisungsbereich in Intune eingeschränkt.</span><span class="sxs-lookup"><span data-stu-id="78ec4-116">They are not limited by any Intune role assignment scope.</span></span> <span data-ttu-id="78ec4-117">Intune-Rollenzuweisungsbereiche beschränken weder Geräte noch Benutzer, für die Remoteunterstützungsanforderungen initiiert werden können.</span><span class="sxs-lookup"><span data-stu-id="78ec4-117">Intune role assignment scopes do not limit the devices or users for which Remote Assistance requests can be initiated.</span></span>

>[!NOTE]
><span data-ttu-id="78ec4-118">Durch die Aktivierung von TeamViewer ermöglichen Sie es dem TeamViewer Connector für Intune TeamViewer-Sitzungen zu erstellen, Active Directory-Daten zu lesen und das Zugriffstoken des TeamViewer-Kontos zu speichern.</span><span class="sxs-lookup"><span data-stu-id="78ec4-118">By enabling TeamViewer, you are allowing the TeamViewer for Intune Connector to create TeamViewer sessions, read Active Directory data, and save the TeamViewer account access token.</span></span>

### <a name="configure-the-intune-teamviewer-connector"></a><span data-ttu-id="78ec4-119">Konfigurieren des TeamViewer Connector für Intune</span><span class="sxs-lookup"><span data-stu-id="78ec4-119">Configure the Intune TeamViewer connector</span></span>

<span data-ttu-id="78ec4-120">Bevor Sie die Remoteunterstützung für Geräte bereitstellen können, müssen Sie den TeamViewer Connector für Intune anhand der folgenden Schritte konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="78ec4-120">Before you can provide remote assistance to devices, you must configure the Intune TeamViewer connector, using the following steps:</span></span>


1. <span data-ttu-id="78ec4-121">Melden Sie sich beim Azure-Portal an.</span><span class="sxs-lookup"><span data-stu-id="78ec4-121">Sign into the Azure portal.</span></span>
2. <span data-ttu-id="78ec4-122">Wählen Sie **Weitere Dienste** > **Überwachung und Verwaltung** > **Intune** aus.</span><span class="sxs-lookup"><span data-stu-id="78ec4-122">Choose **More Services** > **Monitoring + Management** > **Intune**.</span></span>
3. <span data-ttu-id="78ec4-123">Wählen Sie auf dem Blatt **Intune** die Option **Geräte** aus.</span><span class="sxs-lookup"><span data-stu-id="78ec4-123">On the **Intune** blade, choose **Devices**.</span></span>
4. <span data-ttu-id="78ec4-124">Wählen Sie auf dem Blatt **Geräte und Gruppen** die Optionen **Setup** > **TeamViewer Connector** aus.</span><span class="sxs-lookup"><span data-stu-id="78ec4-124">On the **Devices and groups** blade, choose **Setup** > **TeamViewer Connector**.</span></span>
5. <span data-ttu-id="78ec4-125">Klicken Sie auf dem Blatt **TeamViewer Connector** auf **Aktivieren**. Zeigen Sie den Lizenzvertrag für den TeamViewer-Dienst an und akzeptieren Sie diesen.</span><span class="sxs-lookup"><span data-stu-id="78ec4-125">On the **TeamViewer Connector** blade, click **Enable**, then view and accept the TeamViewer service license agreement.</span></span>
6. <span data-ttu-id="78ec4-126">Wählen Sie **Bei TeamViewer anmelden und autorisieren**.</span><span class="sxs-lookup"><span data-stu-id="78ec4-126">Choose **Log in to TeamViewer & Authorize**.</span></span>
7. <span data-ttu-id="78ec4-127">Auf der TeamViewer-Website wird eine Webseite geöffnet.</span><span class="sxs-lookup"><span data-stu-id="78ec4-127">A web page opens to the TeamViewer site.</span></span> <span data-ttu-id="78ec4-128">Geben Sie die Anmeldeinformationen für Ihre TeamViewer-Lizenz ein, und klicken Sie dann auf **Anmelden**.</span><span class="sxs-lookup"><span data-stu-id="78ec4-128">Enter your TeamViewer license credentials, and then click **Sign In**.</span></span>


## <a name="how-to-remotely-administer-a-device"></a><span data-ttu-id="78ec4-129">Remoteverwaltung eines Geräts</span><span class="sxs-lookup"><span data-stu-id="78ec4-129">How to remotely administer a device</span></span>

1. <span data-ttu-id="78ec4-130">Melden Sie sich beim Azure-Portal an.</span><span class="sxs-lookup"><span data-stu-id="78ec4-130">Sign into the Azure portal.</span></span>
2. <span data-ttu-id="78ec4-131">Wählen Sie **Weitere Dienste** > **Überwachung und Verwaltung** > **Intune** aus.</span><span class="sxs-lookup"><span data-stu-id="78ec4-131">Choose **More Services** > **Monitoring + Management** > **Intune**.</span></span>
3. <span data-ttu-id="78ec4-132">Wählen Sie auf dem Blatt **Intune** die Option **Geräte** aus.</span><span class="sxs-lookup"><span data-stu-id="78ec4-132">On the **Intune** blade, choose **Devices**.</span></span>
4. <span data-ttu-id="78ec4-133">Wählen Sie auf dem Blatt **Geräte** die Optionen **Verwalten** > **Alle Geräte** aus.</span><span class="sxs-lookup"><span data-stu-id="78ec4-133">On the **Devices** blade, choose **Manage** > **All devices**.</span></span>
5. <span data-ttu-id="78ec4-134">Wählen Sie das Gerät aus, das Sie zur Remoteverwaltung verwenden möchten, und wählen Sie dann auf dem Blatt „Geräteeigenschaften“ **Mehr** > **Neue Remoteunterstützungssitzung**.</span><span class="sxs-lookup"><span data-stu-id="78ec4-134">Select the device that you want to remotely administer, and then, on the device properties blade, choose **More** > **New Remote Assistance Session**.</span></span>
6. <span data-ttu-id="78ec4-135">Nachdem Intune eine Verbindung mit dem TeamViewer-Dienst hergestellt hat, werden Informationen über das Gerät angezeigt.</span><span class="sxs-lookup"><span data-stu-id="78ec4-135">After Intune connects to the TeamViewer service, you'll see some information about the device.</span></span> <span data-ttu-id="78ec4-136">Wählen Sie **Verbinden**, um die Remotesitzung zu starten.</span><span class="sxs-lookup"><span data-stu-id="78ec4-136">Choose **Connect** to start the remote session.</span></span>

![Android TeamViewer-Beispiel](./media/android-teamviewer.png)

<span data-ttu-id="78ec4-138">Im TeamViewer-Fenster können Sie eine Reihe von Remoteaktionen auf dem Gerät durchführen, einschließlich der Remotesteuerung des Geräts.</span><span class="sxs-lookup"><span data-stu-id="78ec4-138">In the TeamViewer window, you can perform a range of remote actions on the device, including remote control of the device.</span></span> <span data-ttu-id="78ec4-139">Ausführliche Informationen zu den ausführbaren Aktionen finden Sie in der [TeamViewer-Dokumentation](https://www.teamviewer.com/support/documents/).</span><span class="sxs-lookup"><span data-stu-id="78ec4-139">For full details of the actions you can perform, see the [TeamViewer documentation](https://www.teamviewer.com/support/documents/).</span></span>

<span data-ttu-id="78ec4-140">Wenn Sie fertig sind, schließen Sie das TeamViewer-Fenster.</span><span class="sxs-lookup"><span data-stu-id="78ec4-140">When you are finished, close the TeamViewer window.</span></span>

## <a name="next-steps"></a><span data-ttu-id="78ec4-141">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="78ec4-141">Next steps</span></span>

<span data-ttu-id="78ec4-142">Beim Öffnen der App werden einem Benutzer auf dessen Gerät ein Benachrichtigungskennzeichen auf dem Symbol der Unternehmensportal-App sowie eine Benachrichtigung angezeigt.</span><span class="sxs-lookup"><span data-stu-id="78ec4-142">An end user sees a notification flag on the Company Portal app icon on their device, and also see a notification when they open the app.</span></span> <span data-ttu-id="78ec4-143">Anschließend kann er die Remoteunterstützungsanforderung annehmen.</span><span class="sxs-lookup"><span data-stu-id="78ec4-143">They can then accept the remote assistance request.</span></span>
