---
title: "Auf Ihrem Gerät ist ein Zertifikat nicht vorhanden | Microsoft-Dokumentation"
description: 
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 01/04/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: df973b18-9166-417d-8aa3-49edd2bda256
searchScope: User help
ROBOTS: 
ms.reviewer: arnab
ms.suite: ems
ms.custom: intune-enduser
ms.openlocfilehash: 35e360bb0432c58f4c56bf57224e718ebf7e1536
ms.sourcegitcommit: e37e916e2bf14f092d3a767bc90d68c181d739fb
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/03/2018
---
# <a name="your-android-device-is-missing-a-certificate-that-usually-comes-installed-on-your-phone"></a><span data-ttu-id="8716e-102">Auf Ihrem Android-Gerät fehlt ein Zertifikat, das in der Regel auf Ihrem Telefon installiert ist.</span><span class="sxs-lookup"><span data-stu-id="8716e-102">Your Android device is missing a certificate that usually comes installed on your phone</span></span>

<span data-ttu-id="8716e-103">Wenn Ihr Gerät nicht bei Intune registriert ist und ein Zertifikat fehlt, das normalerweise auf Ihrem Telefon installiert ist, können Sie sich nicht bei der Unternehmensportal-App anmelden.</span><span class="sxs-lookup"><span data-stu-id="8716e-103">If your device isn’t enrolled in Intune, and it’s missing a certificate that usually comes installed on your phone, you won’t be able to sign in to the Company Portal app.</span></span> <span data-ttu-id="8716e-104">Wenn Sie versuchen, sich anzumelden, sehen Sie die folgende Meldung:</span><span class="sxs-lookup"><span data-stu-id="8716e-104">When you try to sign in, you’ll see the following message:</span></span>

![screenshot-error-message-about-missing-certificate](./media/andr-cert_install-1-cert_missing.png)

<span data-ttu-id="8716e-106">Sie können dieses Problem beheben, indem Sie das erforderliche Zertifikat von der [Zertifikatseite von Digicert](https://www.digicert.com/digicert-root-certificates.htm) abrufen.</span><span class="sxs-lookup"><span data-stu-id="8716e-106">You can fix this issue by getting the required certificate from [Digicert's certificate page](https://www.digicert.com/digicert-root-certificates.htm).</span></span>

1. <span data-ttu-id="8716e-107">Suchen Sie das Zertifikat __Baltimore CyberTrust Root__, und laden Sie es herunter.</span><span class="sxs-lookup"><span data-stu-id="8716e-107">Find and download the __Baltimore CyberTrust Root__ certificate.</span></span> <span data-ttu-id="8716e-108">Sie können es auch direkt [hier](https://www.digicert.com/CACerts/BaltimoreCyberTrustRoot.crt) herunterladen.</span><span class="sxs-lookup"><span data-stu-id="8716e-108">You can also download it directly from [here](https://www.digicert.com/CACerts/BaltimoreCyberTrustRoot.crt).</span></span>

2. <span data-ttu-id="8716e-109">Ziehen Sie vom oberen Bildschirmrand nach unten, um die Liste der aktuellen Benachrichtigungen zu öffnen, und tippen Sie auf **BaltimoreCyberTrustRoot.crt**.</span><span class="sxs-lookup"><span data-stu-id="8716e-109">Drag down from the top of the screen to display the list of your recent notifications, and tap **BaltimoreCyberTrustRoot.crt**.</span></span>

3. <span data-ttu-id="8716e-110">Das Gerät fordert Sie zum **Benennen des Zertifikats** auf.</span><span class="sxs-lookup"><span data-stu-id="8716e-110">Your device will ask you to **Name the Certificate**.</span></span> <span data-ttu-id="8716e-111">Ändern Sie den angezeigten standardmäßigen Zertifikatnamen nicht.</span><span class="sxs-lookup"><span data-stu-id="8716e-111">Do not change the default certificate name that appears.</span></span>

4. <span data-ttu-id="8716e-112">Stellen Sie sicher, dass **Verwendung von Anmeldeinformationen** auf **Für VPN und Apps** festgelegt ist, und tippen Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="8716e-112">Ensure that **Credential Use** is set to **Used for VPN and apps**, and then tap **OK**.</span></span>

    ![screenshot-certificate-name-dialog-showing-baltimore-certificate-name](./media/andr-cert_install-2-add_cert_name.png)

5. <span data-ttu-id="8716e-114">Schließen Sie den Browser und die Unternehmensportal-App.</span><span class="sxs-lookup"><span data-stu-id="8716e-114">Close your browser and the Company Portal app.</span></span>

6. <span data-ttu-id="8716e-115">Öffnen Sie die Unternehmensportal-App erneut.</span><span class="sxs-lookup"><span data-stu-id="8716e-115">Reopen the Company Portal app.</span></span> <span data-ttu-id="8716e-116">Sie sollten sich jetzt bei der Unternehmensportal-App anmelden können.</span><span class="sxs-lookup"><span data-stu-id="8716e-116">You should now be able to sign in to the Company Portal app.</span></span> <span data-ttu-id="8716e-117">Wenn Sie die Unternehmensportal-App weiterhin nicht verwenden können, wenden Sie sich mithilfe der Informationen auf der [Unternehmensportal-Website](https://portal.manage.microsoft.com#HelpDeskDialog) an die Supportabteilung Ihres Unternehmens, um weitere Anweisungen zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="8716e-117">If you still cannot use the Company Portal app, contact your company support using the information provided on the [Company Portal website](https://portal.manage.microsoft.com#HelpDeskDialog) for further instructions.</span></span>

>[!NOTE]
> <span data-ttu-id="8716e-118">Wenn das Problem durch Installieren dieses Zertifikats nicht behoben werden kann und Ihnen eine Meldung zu einem anderen fehlenden Zertifikat angezeigt wird, müssen Sie weitere Schritte ausführen, um [das fehlende Zertifikat zu installieren](your-device-is-missing-an-IT-required-certificate-android.md).</span><span class="sxs-lookup"><span data-stu-id="8716e-118">If installing this certificate doesn't solve the issue, and you see a different "missing certificate" message, you will need to take additional steps to [install the missing certificate](your-device-is-missing-an-IT-required-certificate-android.md).</span></span>

<span data-ttu-id="8716e-119">Benötigen Sie weitere Unterstützung?</span><span class="sxs-lookup"><span data-stu-id="8716e-119">Still need help?</span></span> <span data-ttu-id="8716e-120">Kontaktieren Sie den Support Ihres Unternehmens.</span><span class="sxs-lookup"><span data-stu-id="8716e-120">Contact your company support.</span></span> <span data-ttu-id="8716e-121">Die entsprechenden Kontaktinformationen finden Sie auf der [Unternehmensportal-Website](https://portal.manage.microsoft.com#HelpDeskDialog).</span><span class="sxs-lookup"><span data-stu-id="8716e-121">For contact information, check the [Company Portal website](https://portal.manage.microsoft.com#HelpDeskDialog).</span></span>
