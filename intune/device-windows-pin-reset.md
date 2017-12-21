---
title: "Zurücksetzen der Kennung auf Windows-Geräten mit Intune"
titlesuffix: Azure portal
description: "In diesem Artikel erfahren Sie, wie Sie mithilfe von Intune die Kennung auf Windows-Geräten mit dem integrierten PIN-Zurücksetzungsdienst von Microsoft zurücksetzen können."
keywords: 
author: arob98
ms.author: angrobe
manager: angrobe
ms.date: 08/09/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5027d012-d6c2-4971-a9ac-217f91d67d87
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: faf3e9b81f76755135f73f8753305d96d227ec14
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2017
---
# <a name="reset-the-passcode-on-windows-devices-integrated-with-the-microsoft-pin-reset-service-using-intune"></a><span data-ttu-id="08a44-103">Zurücksetzen der Kennung auf Windows-Geräten mit dem integrierten PIN-Zurücksetzungsdienst von Microsoft mithilfe von Intune</span><span class="sxs-lookup"><span data-stu-id="08a44-103">Reset the passcode on Windows devices integrated with the Microsoft PIN Reset Service using Intune</span></span>

<span data-ttu-id="08a44-104">Die Zurücksetzungsfunktion der Kennung ist bei Windows-Geräten in den PIN-Zurücksetzungsdienst von Microsoft integriert, mit dem Sie für Geräte, auf denen Windows 10 Mobile ausgeführt wird, eine neue Kennung generieren können.</span><span class="sxs-lookup"><span data-stu-id="08a44-104">The reset passcode capability for Windows devices integrates with the Microsoft Pin Reset Service to let you generate a new passcode for devices that run Windows 10 Mobile.</span></span> <span data-ttu-id="08a44-105">Auf den Geräten muss das Windows 10 Creators Update oder höher ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="08a44-105">The devices must be running the Windows 10 Creators Update, or later.</span></span>

## <a name="supported-platforms"></a><span data-ttu-id="08a44-106">Unterstützte Plattformen</span><span class="sxs-lookup"><span data-stu-id="08a44-106">Supported platforms</span></span>

- <span data-ttu-id="08a44-107">Windows – Unterstützt unter Windows 10 Creators Update und höher (mit Azure AD verknüpft)</span><span class="sxs-lookup"><span data-stu-id="08a44-107">Windows - Supported on Windows 10 Creators Update and later (Azure AD joined)</span></span>
- <span data-ttu-id="08a44-108">Windows Phone – Nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="08a44-108">Windows Phone - Not supported</span></span>
- <span data-ttu-id="08a44-109">iOS – Nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="08a44-109">iOS - Not supported</span></span>
- <span data-ttu-id="08a44-110">macOS – Nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="08a44-110">macOS - Not supported</span></span>
- <span data-ttu-id="08a44-111">Android – Nicht unterstützt</span><span class="sxs-lookup"><span data-stu-id="08a44-111">Android - Not supported</span></span>


## <a name="before-you-start"></a><span data-ttu-id="08a44-112">Vorbereitung</span><span class="sxs-lookup"><span data-stu-id="08a44-112">Before you start</span></span>

<span data-ttu-id="08a44-113">Bevor Sie die Kennung auf von Ihnen verwalteten Windows-Geräten remote zurücksetzen können, müssen Sie den PIN-Zurücksetzungsdienst in Ihren Intune-Mandanten integrieren und die Geräte, die Sie verwalten, konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="08a44-113">Before you can remotely reset the passcode on Windows devices you can manage, you must onboard the PIN reset service to your Intune tenant, and configure devices you manage.</span></span> <span data-ttu-id="08a44-114">Gehen Sie dazu folgendermaßen vor:</span><span class="sxs-lookup"><span data-stu-id="08a44-114">Follow these instructions to get that set up:</span></span>

### <a name="connect-intune-with-the-pin-reset-service"></a><span data-ttu-id="08a44-115">Verbinden von Intune mit dem PIN-Zurücksetzungsdienst</span><span class="sxs-lookup"><span data-stu-id="08a44-115">Connect Intune with the PIN reset service</span></span>

1. <span data-ttu-id="08a44-116">Melden Sie sich auf der [Website zur Integration des PIN-Zurücksetzungsdiensts von Microsoft](https://login.windows.net/common/oauth2/authorize?response_type=code&client_id=b8456c59-1230-44c7-a4a2-99b085333e84&resource=https%3A%2F%2Fgraph.windows.net&redirect_uri=https%3A%2F%2Fcred.microsoft.com&state=e9191523-6c2f-4f1d-a4f9-c36f26f89df0&prompt=admin_consent) an. Verwenden Sie hierzu das Mandantenadministratorkonto, mit dem Sie Ihren Intune-Mandanten verwalten.</span><span class="sxs-lookup"><span data-stu-id="08a44-116">Visit [Microsoft PIN Reset Service Integration website](https://login.windows.net/common/oauth2/authorize?response_type=code&client_id=b8456c59-1230-44c7-a4a2-99b085333e84&resource=https%3A%2F%2Fgraph.windows.net&redirect_uri=https%3A%2F%2Fcred.microsoft.com&state=e9191523-6c2f-4f1d-a4f9-c36f26f89df0&prompt=admin_consent), and sign in using the tenant administrator account you use to manage your Intune tenant.</span></span>
2. <span data-ttu-id="08a44-117">Klicken Sie nach der Anmeldung auf **Annehmen**, um dem PIN-Zurücksetzungsdienst Zugriff auf Ihr Konto zu gewähren.</span><span class="sxs-lookup"><span data-stu-id="08a44-117">After you log in, click **Accept** to give consent for the PIN reset service to access your account.</span></span><br>
<span data-ttu-id="08a44-118">![Seite "Berechtigungen" für den Dienst Zurücksetzen der PIN](./media/pin-reset-service-application.png)</span><span class="sxs-lookup"><span data-stu-id="08a44-118">![PIN reset service permissions page](./media/pin-reset-service-application.png)</span></span>
3. <span data-ttu-id="08a44-119">Im Azure-Portal wird angezeigt, dass Intune und der PIN-Zurücksetzungsdienst aus dem Blatt „Unternehmensanwendungen > Alle Anwendungen“ integriert wurden, wie der folgende Screenshot verdeutlicht:</span><span class="sxs-lookup"><span data-stu-id="08a44-119">In the Azure portal, you can verify that Intune and the PIN reset service were integrated from the Enterprise applications - All applications blade as shown in the following screenshot:</span></span><br>
<span data-ttu-id="08a44-120">![Zurücksetzen der PIN-dienstanwendung in Azure](./media/pin-reset-service-home-screen.png)</span><span class="sxs-lookup"><span data-stu-id="08a44-120">![PIN reset service application in Azure](./media/pin-reset-service-home-screen.png)</span></span>
4. <span data-ttu-id="08a44-121">Melden Sie sich auf [dieser Website](https://login.windows.net/common/oauth2/authorize?response_type=code&client_id=9115dd05-fad5-4f9c-acc7-305d08b1b04e&resource=https%3A%2F%2Fcred.microsoft.com%2F&redirect_uri=ms-appx-web%3A%2F%2FMicrosoft.AAD.BrokerPlugin%2F9115dd05-fad5-4f9c-acc7-305d08b1b04e&state=6765f8c5-f4a7-4029-b667-46a6776ad611&prompt=admin_consent) mit Ihren Anmeldeinformationen des Intune-Mandantenadministrators an. Klicken Sie erneut auf **Annehmen**, um dem Dienst Zugriff auf Ihr Konto zu gewähren.</span><span class="sxs-lookup"><span data-stu-id="08a44-121">Log in to [this website](https://login.windows.net/common/oauth2/authorize?response_type=code&client_id=9115dd05-fad5-4f9c-acc7-305d08b1b04e&resource=https%3A%2F%2Fcred.microsoft.com%2F&redirect_uri=ms-appx-web%3A%2F%2FMicrosoft.AAD.BrokerPlugin%2F9115dd05-fad5-4f9c-acc7-305d08b1b04e&state=6765f8c5-f4a7-4029-b667-46a6776ad611&prompt=admin_consent) using your Intune tenant admin credentials and, again, choose **Accept** to give consent for the service to access your account.</span></span>

### <a name="configure-windows-devices-to-use-pin-reset"></a><span data-ttu-id="08a44-122">Konfigurieren von Windows-Geräten zur Verwendung des PIN-Zurücksetzungsdiensts</span><span class="sxs-lookup"><span data-stu-id="08a44-122">Configure Windows devices to use PIN reset</span></span>

<span data-ttu-id="08a44-123">Verwenden Sie zum Konfigurieren der PIN-Zurücksetzung auf von Ihnen verwalteten Windows-Geräten eine [benutzerdefinierte Intune-Geräterichtlinie für Windows 10](custom-settings-windows-10.md), um die Funktion zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="08a44-123">To configure PIN reset on Windows devices you manage, use an [Intune Windows 10 custom device policy](custom-settings-windows-10.md) to enable the feature.</span></span> <span data-ttu-id="08a44-124">Konfigurieren Sie die Richtlinie mithilfe des folgenden Konfigurationsdienstanbieters für Windows-Richtlinien (Configuration Service Provider, CSPs):</span><span class="sxs-lookup"><span data-stu-id="08a44-124">Configure the policy using the following Windows policy configuration service provider (CSP):</span></span>


- <span data-ttu-id="08a44-125">**Für Geräte** - **./Device/Vendor/MSFT/PassportForWork/*Mandanten-ID*/Policies/EnablePinRecovery**</span><span class="sxs-lookup"><span data-stu-id="08a44-125">**For devices** - **./Device/Vendor/MSFT/PassportForWork/*tenant ID*/Policies/EnablePinRecovery**</span></span>

<span data-ttu-id="08a44-126">Die *Mandanten-ID* bezieht sich auf Ihre Azure Active Directory-ID, die Sie auf der Seite **Eigenschaften** in Azure Active Directory finden.</span><span class="sxs-lookup"><span data-stu-id="08a44-126">*tenant ID* refers to your Azure Active Directory, Directory ID which you can obtain from the **Properties** page of Azure Active Directory.</span></span>

<span data-ttu-id="08a44-127">Legen Sie den Wert diesen CSP auf **TRUE** fest.</span><span class="sxs-lookup"><span data-stu-id="08a44-127">Set the value for this CSP to **True**.</span></span>

## <a name="steps-to-reset-the-passcode"></a><span data-ttu-id="08a44-128">Vorgehensweise zur Zurücksetzung der Kennung</span><span class="sxs-lookup"><span data-stu-id="08a44-128">Steps to reset the passcode</span></span>

1. <span data-ttu-id="08a44-129">Melden Sie sich beim Azure-Portal an.</span><span class="sxs-lookup"><span data-stu-id="08a44-129">Sign into the Azure portal.</span></span>
2. <span data-ttu-id="08a44-130">Wählen Sie **Weitere Dienste** > **Überwachung und Verwaltung** > **Intune** aus.</span><span class="sxs-lookup"><span data-stu-id="08a44-130">Choose **More Services** > **Monitoring + Management** > **Intune**.</span></span>
3. <span data-ttu-id="08a44-131">Wählen Sie auf dem Blatt **Intune** die Option **Geräte** aus.</span><span class="sxs-lookup"><span data-stu-id="08a44-131">On the **Intune** blade, choose **Devices**.</span></span>
4. <span data-ttu-id="08a44-132">Wählen Sie auf dem Blatt **Geräte** die Optionen **Verwalten** > **Alle Geräte** aus.</span><span class="sxs-lookup"><span data-stu-id="08a44-132">On the **Devices** blade, choose **Manage** > **All devices**.</span></span>
5. <span data-ttu-id="08a44-133">Wählen Sie das Gerät aus, für das Sie die Kennung zurücksetzen möchten. Wählen Sie dann auf dem Blatt „Geräteeigenschaften“ die Option **Neue Kennung** aus.</span><span class="sxs-lookup"><span data-stu-id="08a44-133">Select the device for which you want to reset the passcode, and then, on the device properties blade, choose **New passcode**.</span></span>
6. <span data-ttu-id="08a44-134">Bestätigen Sie anschließend mit **Ja**.</span><span class="sxs-lookup"><span data-stu-id="08a44-134">From the confirmation that appears, choose **Yes**.</span></span> <span data-ttu-id="08a44-135">Die Kennung wird generiert und für die folgenden sieben Tage im Portal angezeigt.</span><span class="sxs-lookup"><span data-stu-id="08a44-135">The passcode is generated, and is displayed in the portal for the next seven days.</span></span>

## <a name="next-steps"></a><span data-ttu-id="08a44-136">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="08a44-136">Next steps</span></span>

<span data-ttu-id="08a44-137">Sollte bei der Zurücksetzung der Kennung ein Fehler auftreten, wird im Portal ein Link mit weiteren Informationen angezeigt.</span><span class="sxs-lookup"><span data-stu-id="08a44-137">If the passcode reset fails, a link is provided in the portal to get more information.</span></span>


