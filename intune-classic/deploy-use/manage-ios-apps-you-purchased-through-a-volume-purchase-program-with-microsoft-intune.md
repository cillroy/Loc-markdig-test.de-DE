---
title: Verwalten von iOS-Apps aus einem Volumenprogramm
description: "Verwenden Sie Intune, um Apps zu verwalten, die Sie über ein Volumenprogramm von Apple erworben haben. Dazu importieren Sie die Lizenzinformationen aus dem App-Store, verfolgen nach, wie viele Lizenzen verwendet wurden, und verhindern, dass mehr App-Kopien installiert werden, als Sie erworben haben."
keywords: 
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 10/11/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 1dafc28a-7f8b-4fe0-8619-f977c93d1140
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: b4a946dd16d03c41c3a07da1dd39781a8ff98f1f
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2017
---
# <a name="manage-ios-apps-you-purchased-through-a-volume-purchase-program-with-microsoft-intune"></a><span data-ttu-id="8013d-103">Verwalten von iOS-Apps, die über ein Volumenprogramm mit Microsoft Intune erworben wurden</span><span class="sxs-lookup"><span data-stu-id="8013d-103">Manage iOS apps you purchased through a volume-purchase program with Microsoft Intune</span></span>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="8013d-104">Der iOS-App-Store bietet die Möglichkeit, mehrere Lizenzen für eine App zu erwerben, die in Ihrem Unternehmen ausgeführt werden soll.</span><span class="sxs-lookup"><span data-stu-id="8013d-104">The iOS app store lets you purchase multiple licenses for an app that you want to run in your company.</span></span> <span data-ttu-id="8013d-105">Dadurch können Sie den Verwaltungsaufwand reduzieren, der durch das Nachverfolgen mehrerer erworbener App-Kopien entsteht.</span><span class="sxs-lookup"><span data-stu-id="8013d-105">This helps you reduce the administrative overhead of tracking multiple purchased copies of apps.</span></span>

<span data-ttu-id="8013d-106">Microsoft Intune unterstützt Sie bei der Verwaltung von Apps, die über ein solches Programm erworben wurden. Dazu importieren Sie die Lizenzinformationen aus dem App-Store, verfolgen nach, wie viele Lizenzen verwendet wurden, und verhindern, dass mehr App-Kopien installiert werden, als Sie erworben haben.</span><span class="sxs-lookup"><span data-stu-id="8013d-106">Microsoft Intune helps you manage apps that you purchased through this program by importing the license information from the app store, tracking how many of the licenses you have used, and preventing you from installing more copies of the app than you own.</span></span>

> [!Important]
> <span data-ttu-id="8013d-107">Derzeit weist Intune App-Lizenzen des Programms für iOS-Volumenlizenzen für Unternehmen (Volume Purchase Program for Business, VPP) Benutzern und Geräten zu.</span><span class="sxs-lookup"><span data-stu-id="8013d-107">Currently, Intune assigns iOS Volume Purchase Program for Business (VPP) app licenses to users and devices.</span></span> <span data-ttu-id="8013d-108">Aus diesem Grund müssen Benutzer möglicherweise zum Installieren der App ihr Apple-ID-Kennwort eingeben.</span><span class="sxs-lookup"><span data-stu-id="8013d-108">Because of this, users may have to enter their Apple ID password to install the app.</span></span>

## <a name="manage-volume-purchased-apps-for-ios-devices"></a><span data-ttu-id="8013d-109">Verwalten von Apps für iOS-Geräte, die über ein Volumenprogramm erworben wurden</span><span class="sxs-lookup"><span data-stu-id="8013d-109">Manage volume-purchased apps for iOS devices</span></span>
<span data-ttu-id="8013d-110">Sie erwerben mehrere Lizenzen für iOS-Apps über das [Programm für Volumenlizenzen für Unternehmen (Volume Purchase Program, VPP) von Apple](http://www.apple.com/business/vpp/).</span><span class="sxs-lookup"><span data-stu-id="8013d-110">You purchase multiple licenses for iOS apps through the [Apple Volume Purchase Program for Business](http://www.apple.com/business/vpp/).</span></span> <span data-ttu-id="8013d-111">Dies umfasst das Einrichten eines Apple VPP-Kontos auf der Apple-Website und das Hochladen des Apple VPP-Tokens in Intune.</span><span class="sxs-lookup"><span data-stu-id="8013d-111">This involves setting up an Apple VPP account from the Apple website and uploading the Apple VPP token to Intune.</span></span>  <span data-ttu-id="8013d-112">Anschließend können Sie Ihre Informationen zum Volumenerwerb mit Intune synchronisieren und die Verwendung der im Rahmen des Volumenprogramms erworbenen App verfolgen.</span><span class="sxs-lookup"><span data-stu-id="8013d-112">You can then synchronize your volume purchase information with Intune and track your volume-purchased app use.</span></span>

## <a name="before-you-start"></a><span data-ttu-id="8013d-113">Vorbereitung</span><span class="sxs-lookup"><span data-stu-id="8013d-113">Before you start</span></span>
<span data-ttu-id="8013d-114">Bevor Sie beginnen, müssen Sie ein VPP-Token von Apple abrufen und es in Ihr Intune-Konto hochladen.</span><span class="sxs-lookup"><span data-stu-id="8013d-114">Before you start, you'll need to get a VPP token from Apple and upload this to your Intune account.</span></span> <span data-ttu-id="8013d-115">Beachten Sie darüber hinaus die folgenden Informationen:</span><span class="sxs-lookup"><span data-stu-id="8013d-115">Additionally, you should understand the following:</span></span>

* <span data-ttu-id="8013d-116">Intune unterstützt bis zu 256 VPP-Token.</span><span class="sxs-lookup"><span data-stu-id="8013d-116">Intune supports adding up to 256 VPP tokens.</span></span>
* <span data-ttu-id="8013d-117">Wenn Sie zuvor ein VPP-Token für ein anderes Produkt verwendet haben, müssen Sie für die Verwendung mit Intune ein neues erstellen.</span><span class="sxs-lookup"><span data-stu-id="8013d-117">If you previously used a VPP token with a different product, you must generate a new one to use with Intune.</span></span>
* <span data-ttu-id="8013d-118">Jedes Token ist ein Jahr lang gültig.</span><span class="sxs-lookup"><span data-stu-id="8013d-118">Each token is valid for one year.</span></span>
* <span data-ttu-id="8013d-119">Standardmäßig wird Intune zweimal täglich mit dem Apple VPP-Dienst synchronisiert.</span><span class="sxs-lookup"><span data-stu-id="8013d-119">By default, Intune syncs with the Apple VPP service twice a day.</span></span> <span data-ttu-id="8013d-120">Eine manuelle Synchronisierung können Sie jederzeit starten.</span><span class="sxs-lookup"><span data-stu-id="8013d-120">You can start a manual sync at any time.</span></span>
* <span data-ttu-id="8013d-121">Nachdem Sie den VPP-Token in Intune importiert haben, importieren Sie denselben Token in keine andere Geräteverwaltungslösung.</span><span class="sxs-lookup"><span data-stu-id="8013d-121">After you have imported the VPP token to Intune, do not import the same token to any other device management solution.</span></span> <span data-ttu-id="8013d-122">Andernfalls kann dies zu einem Verlust von Lizenzzuweisung und Benutzerdatensätzen führen.</span><span class="sxs-lookup"><span data-stu-id="8013d-122">Doing so might result in the loss of license assignment and user records.</span></span>
* <span data-ttu-id="8013d-123">Bevor Sie iOS VPP mit Intune verwenden, entfernen Sie alle vorhandenen, mit anderen Anbietern für das Mobile-Geräte-Management (MDM) erstellten VPP-Benutzerkonten.</span><span class="sxs-lookup"><span data-stu-id="8013d-123">Before you start to use iOS VPP with Intune, remove any existing VPP user accounts created with other mobile device management (MDM) vendors.</span></span> <span data-ttu-id="8013d-124">Aus Sicherheitsgründen werden diese Benutzerkonten in Intune nicht synchronisiert.</span><span class="sxs-lookup"><span data-stu-id="8013d-124">Intune will not synchronize those user accounts into Intune as a security measure.</span></span> <span data-ttu-id="8013d-125">Intune synchronisiert nur Daten aus dem Apple VPP-Dienst, der von Intune erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="8013d-125">Intune will only synchronize data from the Apple VPP service that Intune created.</span></span>
* <span data-ttu-id="8013d-126">Sie können iOS VPP-Apps nur dann auf Geräten von Benutzern bereitstellen, die mithilfe des Geräteregistrierungsprotokolls (Device Enrollment Protocol, DEP) registriert wurden, wenn Benutzeraffinität für die Geräte konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="8013d-126">You can only deploy iOS VPP apps to user's devices that were enrolled using the Device Enrollment Protocol (DEP) if user affinity for the device is configured.</span></span>

## <a name="to-get-and-upload-an-apple-vpp-token"></a><span data-ttu-id="8013d-127">So können Sie einen Apple VPP-Token abrufen und hochladen</span><span class="sxs-lookup"><span data-stu-id="8013d-127">To get and upload an Apple VPP token</span></span>

1.  <span data-ttu-id="8013d-128">Wählen Sie in der [Microsoft Intune-Verwaltungskonsole](https://manage.microsoft.com) **Verwaltung** &gt; **iOS und Mac OS X** &gt; **Volume Purchase Program**.</span><span class="sxs-lookup"><span data-stu-id="8013d-128">In the [Microsoft Intune administration console](https://manage.microsoft.com), choose **Admin** &gt; **iOS and Mac OS X** &gt;  **Volume Purchase Program**.</span></span>

2.  <span data-ttu-id="8013d-129">Klicken Sie auf den Link **Apple VPP-Konto**.</span><span class="sxs-lookup"><span data-stu-id="8013d-129">Choose the **Apple VPP Account** link.</span></span> <span data-ttu-id="8013d-130">Melden Sie sich für das Programm für Volumenlizenzen für Unternehmen (Volume Purchase Program, VPP) an, falls noch nicht erfolgt.</span><span class="sxs-lookup"><span data-stu-id="8013d-130">If you haven't already, sign up for the Volume Purchase Program for Business.</span></span> <span data-ttu-id="8013d-131">Sobald Sie registriert sind, laden Sie das Apple VPP-Token für Ihr Konto herunter.</span><span class="sxs-lookup"><span data-stu-id="8013d-131">After you sign up, download the Apple VPP token for your account.</span></span>

3.  <span data-ttu-id="8013d-132">Wählen Sie auf der Seite **Apple Volume Purchase Program (VPP) verwalten** in der Intune-Konsole die Option **VPP-Token hochladen**.</span><span class="sxs-lookup"><span data-stu-id="8013d-132">On the **Manage Apple Volume Purchase Program (VPP)** page of the Intune console, choose **Upload the VPP token**.</span></span>

4.  <span data-ttu-id="8013d-133">Geben oder fügen Sie im Dialogfeld **VPP-Token hochladen** den VPP-Token-Namen und Ihre Apple-ID ein, und wählen Sie dann **Hochladen** aus.</span><span class="sxs-lookup"><span data-stu-id="8013d-133">In the **Upload the VPP token** dialog box, enter or paste the VPP token name and your Apple ID, and then choose **Upload**.</span></span>

5.  <span data-ttu-id="8013d-134">Aktivieren Sie im Dialogfeld mit der Warnung das Kontrollkästchen, um anzugeben, dass Sie wissen, dass Sie später nicht zu einem anderen VPP-Konto wechseln können, und wählen Sie dann **Ja** aus.</span><span class="sxs-lookup"><span data-stu-id="8013d-134">In the warning dialog box, check the box to indicate that you understand that you can't change to a different VPP account later, and then choose **Yes**.</span></span>

<span data-ttu-id="8013d-135">Auf der Seite **Volume Purchase Program** werden nun Informationen zum Apple VPP-Token angezeigt, einschließlich der letzten Aktualisierung, des Ablaufdatums und der letzten Synchronisierung mit Intune.</span><span class="sxs-lookup"><span data-stu-id="8013d-135">On the **Volume Purchase Program** page, you can now view information about the Apple VPP token, including when it was last updated, when it will expire, and when it was last synchronized with Intune.</span></span>

<span data-ttu-id="8013d-136">Sie können die von Apple gespeicherten Daten jederzeit mit Intune synchronisieren, indem Sie **Jetzt synchronisieren** wählen.</span><span class="sxs-lookup"><span data-stu-id="8013d-136">You can synchronize the data held by Apple with Intune at any time by choosing **Sync now**.</span></span>

## <a name="to-deploy-a-volume-purchased-app"></a><span data-ttu-id="8013d-137">So stellen Sie per Volumenlizenz erworbene Apps bereit</span><span class="sxs-lookup"><span data-stu-id="8013d-137">To deploy a volume-purchased app</span></span>

1.  <span data-ttu-id="8013d-138">Wählen Sie in der [Microsoft Intune-Verwaltungskonsole](https://manage.microsoft.com) die Optionen **Apps** &gt; **Apps** &gt; **Per Volumenlizenz erworbene Apps**.</span><span class="sxs-lookup"><span data-stu-id="8013d-138">In the [Microsoft Intune administration console](https://manage.microsoft.com), choose **Apps** &gt; **Apps** &gt; **Volume-Purchased Apps**.</span></span> <span data-ttu-id="8013d-139">Diese Liste zeigt alle Apps, die mit dem Apple VPP-Dienst synchronisiert wurden.</span><span class="sxs-lookup"><span data-stu-id="8013d-139">This list shows all apps that were synchronized from the Apple VPP service.</span></span>

2.  <span data-ttu-id="8013d-140">Wählen Sie die bereitzustellende App und dann **Bereitstellung verwalten** aus. Befolgen Sie anschließend die Anweisungen zum Hochladen, Erstellen und Bereitstellen der App im Thema [Bereitstellen von Apps in Microsoft Intune](deploy-apps-in-microsoft-intune.md).</span><span class="sxs-lookup"><span data-stu-id="8013d-140">Choose the app that you want to deploy, choose **Manage Deployment**, and then use the instructions in the [Deploy apps in Microsoft Intune](deploy-apps-in-microsoft-intune.md) topic to finish uploading, creation, and deployment of the app.</span></span>

> [!TIP]
> <span data-ttu-id="8013d-141">Sie müssen eine Bereitstellungsaktion vom Typ **Erforderlich** auswählen.</span><span class="sxs-lookup"><span data-stu-id="8013d-141">You must choose a deployment action of **Required**.</span></span> <span data-ttu-id="8013d-142">„Verfügbare“ Installationen werden derzeit nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="8013d-142">Available installations are not currently supported.</span></span> <span data-ttu-id="8013d-143">Darüber hinaus können Sie die App nur für Benutzergruppen bereitstellen.</span><span class="sxs-lookup"><span data-stu-id="8013d-143">Additionally, you can only deploy the app to user groups.</span></span>

<span data-ttu-id="8013d-144">Wenn Sie die Anwendung als **erforderliche** Installation bereitstellen, verwendet jeder Benutzer, der die App installiert, eine Lizenz.</span><span class="sxs-lookup"><span data-stu-id="8013d-144">When you deploy the app as a **Required** installation, each user who installs the app uses a license.</span></span>

<span data-ttu-id="8013d-145">Zum Freigeben einer Lizenz müssen Sie die Bereitstellungsaktion in **Deinstallieren** ändern.</span><span class="sxs-lookup"><span data-stu-id="8013d-145">To reclaim a license, you must change the deployment action to **Uninstall**.</span></span> <span data-ttu-id="8013d-146">Die Lizenz wird freigegeben, wenn die App deinstalliert wird.</span><span class="sxs-lookup"><span data-stu-id="8013d-146">The license will be reclaimed after the app is uninstalled.</span></span>

<span data-ttu-id="8013d-147">Wenn ein Benutzer mit einem geeigneten Gerät erstmals versucht, eine VPP-App zu installieren, wird er aufgefordert, am Programm für Volumenlizenzen (Volume Purchase Program, VPP) von Apple teilzunehmen.</span><span class="sxs-lookup"><span data-stu-id="8013d-147">When a user with an eligible device first tries to install a VPP app, they will be asked to join the Apple Volume Purchase program.</span></span> <span data-ttu-id="8013d-148">Die Teilnahme muss erfolgen, bevor die App-Installation fortgesetzt wird.</span><span class="sxs-lookup"><span data-stu-id="8013d-148">They must do this before the app installation proceeds.</span></span>

<span data-ttu-id="8013d-149">Wenn keine weiteren Lizenzen verfügbar sind, schlägt die Bereitstellung fehl.</span><span class="sxs-lookup"><span data-stu-id="8013d-149">If there are no more licenses available, the deployment will fail.</span></span>

## <a name="to-monitor-apple-vpp-apps"></a><span data-ttu-id="8013d-150">So überwachen Sie Apple VPP-Apps</span><span class="sxs-lookup"><span data-stu-id="8013d-150">To monitor Apple VPP apps</span></span>
<span data-ttu-id="8013d-151">Sie können überwachen, welche VPP-Apps bereitgestellt wurden und wie viele Lizenzen vom Arbeitsbereich **Apps** im Knoten **Per Volumenlizenz erworbene Apps** verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="8013d-151">You can monitor which VPP apps have been deployed, and how many licenses are used, from the **Apps** workspace in the **Volume-Purchased Apps** node.</span></span>

> [!TIP]
> <span data-ttu-id="8013d-152">Sie können auch App-**Filter** verwenden, um den Status der einzelnen App-Installationen zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="8013d-152">You can also use app **Filters** to examine the status of each app installation.</span></span>

### <a name="see-also"></a><span data-ttu-id="8013d-153">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="8013d-153">See also</span></span>
[<span data-ttu-id="8013d-154">Bereitstellen von Apps in Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="8013d-154">Deploy apps in Microsoft Intune</span></span>](deploy-apps-in-microsoft-intune.md)
