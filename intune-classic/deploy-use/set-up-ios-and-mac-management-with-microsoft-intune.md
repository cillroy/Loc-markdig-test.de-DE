---
title: Set up iOS and Mac management
description: "Aktivieren Sie die mobile Geräteverwaltung (Mobile Device Management, MDM) für iOS-Geräte einschließlich iPads und iPhones sowie Mac OS X-Geräte mit Microsoft Intune."
keywords: 
author: nathbarn
ms.author: nathbarn
manager: angrobe
ms.date: 03/13/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: dc451224-1372-4b84-b641-cfa67cb3849b
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: d07d9acb2956d99c0ee613d603b820d58f40f247
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2017
---
# <a name="set-up-ios-and-mac-device-management"></a><span data-ttu-id="b4977-103">Einrichten der iOS- und Mac-Geräteverwaltung</span><span class="sxs-lookup"><span data-stu-id="b4977-103">Set up iOS and Mac device management</span></span>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="b4977-104">Intune ermöglicht die Verwaltung mobiler Geräte (mobile device management, MDM) wie iPads, iPhones und Mac OS-Geräte und ermöglicht Benutzern den Zugriff auf Unternehmens-E-Mails und -Apps.</span><span class="sxs-lookup"><span data-stu-id="b4977-104">Intune enables mobile device management (MDM) of iPads, iPhones, and macOS devices and gives users access to company email and apps.</span></span> <span data-ttu-id="b4977-105">Zum Verwalten von iOS- und Mac-Geräten benötigen Sie ein APNS-Zertifikat (Apple Push Notification Service).</span><span class="sxs-lookup"><span data-stu-id="b4977-105">An Apple Push Notification service (APNs) certificate is required for Intune to manage iOS and Mac devices.</span></span> <span data-ttu-id="b4977-106">Sobald das Zertifikat in Intune hinzugefügt ist, können Benutzer die Unternehmensportal-App zur Registrierung ihrer Geräte installieren, oder der Administrator kann die [Verwaltung von firmeneigenen iOS-Geräten](enroll-corporate-owned-ios-devices-in-microsoft-intune.md) einrichten.</span><span class="sxs-lookup"><span data-stu-id="b4977-106">After the certificate is added to Intune, users can install the Company Portal app to enroll their devices, or the admin can set up [corporate-owned iOS device management](enroll-corporate-owned-ios-devices-in-microsoft-intune.md).</span></span>

1.  <span data-ttu-id="b4977-107">**Einrichten von Intune**</span><span class="sxs-lookup"><span data-stu-id="b4977-107">**Set up Intune**</span></span><br>
    <span data-ttu-id="b4977-108">Wenn nicht bereits geschehen, bereiten Sie die Verwaltung mobiler Geräte durch [Festlegen der Autorität für die Verwaltung mobiler Geräte](prerequisites-for-enrollment.md#step-2-set-mdm-authority) auf **Microsoft Intune** und Einrichten von MDM vor.</span><span class="sxs-lookup"><span data-stu-id="b4977-108">If you haven’t already, prepare for mobile device management by  [setting the mobile device management authority](prerequisites-for-enrollment.md#step-2-set-mdm-authority) as **Microsoft Intune** and setting up MDM.</span></span>

2.  <span data-ttu-id="b4977-109">**Abrufen einer Zertifikatsignierungsanforderung**</span><span class="sxs-lookup"><span data-stu-id="b4977-109">**Get a certificate signing request**</span></span><br>
    <span data-ttu-id="b4977-110">Öffnen Sie als Administrator die [Microsoft Intune-Verwaltungskonsole](https://manage.microsoft.com), navigieren Sie zu **Verwaltung** &gt;  **Verwaltung mobiler Geräte** &gt; **iOS und Mac OS X** &gt; **APNs-Zertifikat hochladen**, und wählen Sie anschließend **APNs-Zertifikatanforderung herunterladen** aus.</span><span class="sxs-lookup"><span data-stu-id="b4977-110">As an administrative user, open the [Microsoft Intune administration console](https://manage.microsoft.com), go to **Administration** &gt; **Mobile Device Management** &gt; **iOS and Mac OS X** &gt; **Upload an APNs Certificate**, and then choose **Download the APNs certificate request**.</span></span> <span data-ttu-id="b4977-111">Speichern Sie die Zertifikatsignierungsanforderung (CSR-Datei) lokal.</span><span class="sxs-lookup"><span data-stu-id="b4977-111">Save the certificate signing request (.csr) file locally.</span></span> <span data-ttu-id="b4977-112">Die CSR-Datei wird verwendet, um ein Vertrauensstellungszertifikat vom Apple Push Certificates-Portal anzufordern.</span><span class="sxs-lookup"><span data-stu-id="b4977-112">The .csr file is used to request a trust relationship certificate from the Apple Push Certificates Portal.</span></span>

    ![Dialogfeld „APNs-Zertifikat hochladen“](../media/Intune-iOS-enrollment-with-apns.png)

3.  <span data-ttu-id="b4977-114">**Abrufen eines Apple Push Notification Service-Zertifikats**</span><span class="sxs-lookup"><span data-stu-id="b4977-114">**Get an Apple Push Notification service certificate**</span></span><br>
    <span data-ttu-id="b4977-115">Wechseln Sie zum [Apple Push Certificates-Portal](http://go.microsoft.com/fwlink/?LinkId=269844), und melden Sie sich mit Ihrer Unternehmens-Apple-ID an, um das APNs-Zertifikat mithilfe der CSR-Datei zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="b4977-115">Go to the [Apple Push Certificates Portal](http://go.microsoft.com/fwlink/?LinkId=269844), and sign in with your company Apple ID to create the APNs certificate by using the .csr file.</span></span> <span data-ttu-id="b4977-116">Nachdem Sie im Apple Push Certificates-Portal **Hochladen** ausgewählt haben, erhalten Sie eine JSON-Datei, die für APNs nicht verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="b4977-116">After choosing **Upload** on Apple's Push Certificate Portal, you will receive a .json file that cannot be used for APNs.</span></span> <span data-ttu-id="b4977-117">Schließen Sie den Download ab, kehren Sie zum Apple Push Certificates-Portal für **Zertifikate für Drittanbieterserver** zurück, und wählen Sie anschließend **Herunterladen** aus.</span><span class="sxs-lookup"><span data-stu-id="b4977-117">Complete the download, return to the Apple Push Certificates Portal for **Certificates for Third-Party Servers**, and then choose **Download**.</span></span>

    <span data-ttu-id="b4977-118">Laden Sie das APNs-Zertifikat (.pem) herunter, und speichern Sie die Datei lokal.</span><span class="sxs-lookup"><span data-stu-id="b4977-118">Download the APNs (.pem) certificate, and save the file locally.</span></span>

    > [!NOTE]
    > <span data-ttu-id="b4977-119">Sie müssen dieses APNs-Zertifikat jährlich verlängern (nicht ersetzen).</span><span class="sxs-lookup"><span data-stu-id="b4977-119">Every year, you need to renew (not replace) this APNs certificate.</span></span> <span data-ttu-id="b4977-120">Verwenden Sie dieselbe Apple-ID, um sich im Apple Push Certificate-Portal anzumelden und das Zertifikat zu verlängern. Folgen Sie dann denselben Anweisungen in diesem Thema, um das Zertifikat herunterzuladen und es dann in Intune hochzuladen.</span><span class="sxs-lookup"><span data-stu-id="b4977-120">Use this same Apple ID to sign in to Apple's Push Certificate Portal to renew the certificate, and then use the same instructions in this topic to download the certificate, and then upload it to Intune.</span></span>

4.  <span data-ttu-id="b4977-121">**Hinzufügen des APNs-Zertifikats zu Intune**</span><span class="sxs-lookup"><span data-stu-id="b4977-121">**Add the APNs certificate to Intune**</span></span><br>
    <span data-ttu-id="b4977-122">Navigieren Sie in der [Microsoft Intune-Verwaltungskonsole](https://manage.microsoft.com) zu **Verwaltung** &gt; **Verwaltung mobiler Geräte** &gt; **iOS und Mac OS X** &gt; **APNs-Zertifikat hochladen**, und wählen Sie anschließend **APNs-Zertifikat hochladen** aus.</span><span class="sxs-lookup"><span data-stu-id="b4977-122">In the [Microsoft Intune administration console](https://manage.microsoft.com), go to **Administration** &gt; **Mobile Device Management** &gt; **iOS and Mac OS X** &gt; **Upload an APNs Certificate**, and then choose **Upload the APNs certificate**.</span></span> <span data-ttu-id="b4977-123">Wechseln Sie zur Zertifikatdatei (.pem), wählen Sie **Öffnen** aus, und geben Sie anschließend Ihre **Apple-ID**ein.</span><span class="sxs-lookup"><span data-stu-id="b4977-123">Go to the certificate (.pem) file, choose **Open**, and then enter your **Apple ID**.</span></span> <span data-ttu-id="b4977-124">Mit dem APNs-Zertifikat kann Intune iOS-Geräte registrieren und verwalten, indem die Richtlinie auf registrierte mobile Geräte übertragen wird.</span><span class="sxs-lookup"><span data-stu-id="b4977-124">With the APNs certificate, Intune can enroll and manage iOS devices by pushing policy to enrolled mobile devices.</span></span>

5.  <span data-ttu-id="b4977-125">**Benutzern erklären, wie sie ihre Geräte registrieren, um auf Unternehmensressourcen zugreifen zu können**</span><span class="sxs-lookup"><span data-stu-id="b4977-125">**Tell your users how to enroll their devices to get access to company resources.**</span></span>

    <span data-ttu-id="b4977-126">Registrierungsanleitungen für Endbenutzer finden Sie unter [Registrieren Ihres iOS-Geräts bei Intune](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-ios) oder unter [Registrieren Ihres Mac OS-Geräts bei Intune](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-macos).</span><span class="sxs-lookup"><span data-stu-id="b4977-126">For end-user enrollment instructions, see [Enroll your iOS device in Intune](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-ios) and [Enroll your macOS device in Intune](https://docs.microsoft.com/intune-user-help/enroll-your-device-in-intune-macos).</span></span> <span data-ttu-id="b4977-127">Im Laufe des Registrierungsprozesses werden Benutzer darüber informiert, was sie erwarten können und was IT-Administratoren auf ihren Geräten sehen können und was nicht.</span><span class="sxs-lookup"><span data-stu-id="b4977-127">The enrollment process tells users what they can expect, and what IT administrators can and can't see on their devices.</span></span>

    <span data-ttu-id="b4977-128">Informationen zu anderen Endbenutzeraufgaben finden Sie in den folgenden Artikeln:</span><span class="sxs-lookup"><span data-stu-id="b4977-128">For information about other end-user tasks, see these articles:</span></span>
    - [<span data-ttu-id="b4977-129">Ressourcen zu Endbenutzerszenarios in Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="b4977-129">Resources about the end-user experience with Microsoft Intune</span></span>](/intune/end-user-educate)
    - [<span data-ttu-id="b4977-130">Endbenutzer-Leitfaden für iOS- und Mac-Geräte</span><span class="sxs-lookup"><span data-stu-id="b4977-130">End user guidance for iOS and Mac devices</span></span>](https://docs.microsoft.com/intune-user-help/using-your-ios-or-macOS-device-with-intune)

<span data-ttu-id="b4977-131">Wenn Ihr Unternehmen oder Ihre Organisation iOS-Geräte für Benutzer erwirbt, können diese Geräte ebenfalls zur Verwaltung als [unternehmenseigene iOS-Geräte](enroll-corporate-owned-ios-devices-in-microsoft-intune.md) registriert werden.</span><span class="sxs-lookup"><span data-stu-id="b4977-131">If your company or organization buys iOS devices for users, those devices can also be enrolled for management as [company-owned iOS devices](enroll-corporate-owned-ios-devices-in-microsoft-intune.md).</span></span>

### <a name="see-also"></a><span data-ttu-id="b4977-132">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="b4977-132">See Also</span></span>
[<span data-ttu-id="b4977-133">Voraussetzungen für die Registrierung bei Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="b4977-133">Prerequisites for enrollment with Microsoft Intune</span></span>](prerequisites-for-enrollment.md)
