---
title: Verwalten von per Volumenlizenz erworbenen iOS-E-Books
titlesuffix: Azure portal
description: "Erfahren Sie, wie Sie Bücher, die Sie über ein Volumenprogramm im iOS Store erworben haben, in Intune synchronisieren und dann ihre Nutzung verwalten und nachverfolgen.\""
keywords: 
author: mattbriggs
ms.author: mabrigg
manager: angrobe
ms.date: 08/17/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f5617074-2384-4812-b913-dc94f64c0818
ms.reviewer: mghadial
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 1c819364266c2bf3f0cf088508da735d0e7696ff
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2018
---
# <a name="how-to-manage-ios-ebooks-you-purchased-through-a-volume-purchase-program-with-microsoft-intune"></a><span data-ttu-id="83f5f-103">Verwalten von iOS-E-Books, die über ein Volumenprogramm erworben wurden, mit Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="83f5f-103">How to manage iOS eBooks you purchased through a volume-purchase program with Microsoft Intune</span></span>


[!INCLUDE [azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="83f5f-104">Mit dem Apple Volume Purchase Program (VPP) können Sie mehrere Lizenzen für ein Buch kaufen, das Sie an Benutzer in Ihrem Unternehmen verteilen möchten.</span><span class="sxs-lookup"><span data-stu-id="83f5f-104">The Apple Volume Purchase Program (VPP) lets you purchase multiple licenses for a book that you want to distribute to users in your company.</span></span> <span data-ttu-id="83f5f-105">Sie können Bücher aus den Stores für Unternehmen oder für Bildungseinrichtungen verteilen.</span><span class="sxs-lookup"><span data-stu-id="83f5f-105">You can distribute books from the Business, or Education stores.</span></span>

<span data-ttu-id="83f5f-106">Microsoft Intune hilft Ihnen beim Synchronisieren, Verwalten und Zuweisen der Bücher, die Sie über dieses Programm erworben haben.</span><span class="sxs-lookup"><span data-stu-id="83f5f-106">Microsoft Intune helps you synchronize, manage, and assign books that you purchased through this program.</span></span> <span data-ttu-id="83f5f-107">Sie können die Lizenzinformationen aus dem Store importieren und verfolgen, wie viele Lizenzen Sie verwendet haben.</span><span class="sxs-lookup"><span data-stu-id="83f5f-107">You can import license information from the store and track how many of the licenses you have used.</span></span>

<span data-ttu-id="83f5f-108">Die Verfahren zum Verwalten von Büchern ähneln denen zum [Verwalten von VPP-Apps](vpp-apps-ios.md).</span><span class="sxs-lookup"><span data-stu-id="83f5f-108">The procedures to manage books are similar to [managing VPP apps](vpp-apps-ios.md).</span></span>

## <a name="manage-volume-purchased-books-for-ios-devices"></a><span data-ttu-id="83f5f-109">Verwalten von per Volumenlizenz erworbenen Büchern für iOS-Geräte</span><span class="sxs-lookup"><span data-stu-id="83f5f-109">Manage volume-purchased books for iOS devices</span></span>
<span data-ttu-id="83f5f-110">Sie erwerben mehrere Lizenzen für iOS-Bücher über das [Apple Volume Purchase Program für Unternehmen](http://www.apple.com/business/vpp/) oder das [Apple Volume Purchase Program für Bildungseinrichtungen](http://volume.itunes.apple.com/us/store).</span><span class="sxs-lookup"><span data-stu-id="83f5f-110">You buy multiple licenses for iOS books through the [Apple Volume Purchase Program for Business](http://www.apple.com/business/vpp/) or the [Apple Volume Purchase Program for Education](http://volume.itunes.apple.com/us/store).</span></span> <span data-ttu-id="83f5f-111">Dieser Vorgang umfasst das Einrichten eines Apple VPP-Kontos auf der Apple-Website und das Hochladen des Apple VPP-Tokens in Intune.</span><span class="sxs-lookup"><span data-stu-id="83f5f-111">This process involves setting up an Apple VPP account from the Apple website and uploading the Apple VPP token to Intune.</span></span>  <span data-ttu-id="83f5f-112">Anschließend können Sie Ihre Informationen zum Volumenerwerb mit Intune synchronisieren und die Verwendung des per Volumenlizenz erworbenen Buchs verfolgen.</span><span class="sxs-lookup"><span data-stu-id="83f5f-112">You can then synchronize your volume purchase information with Intune and track your volume-purchased book use.</span></span>

## <a name="before-you-start"></a><span data-ttu-id="83f5f-113">Vorbereitung</span><span class="sxs-lookup"><span data-stu-id="83f5f-113">Before you start</span></span>
<span data-ttu-id="83f5f-114">Bevor Sie beginnen, rufen Sie ein VPP-Token von Apple ab und laden es in Ihr Intune-Konto hoch.</span><span class="sxs-lookup"><span data-stu-id="83f5f-114">Before you start, get a VPP token from Apple and upload it to your Intune account.</span></span> <span data-ttu-id="83f5f-115">Darüber hinaus gilt:</span><span class="sxs-lookup"><span data-stu-id="83f5f-115">Additionally:</span></span>

* <span data-ttu-id="83f5f-116">Sie können Ihrem Intune-Konto bis zu 256 VPP-Token zuordnen.</span><span class="sxs-lookup"><span data-stu-id="83f5f-116">You can associate up to 256 VPP tokens with your Intune account.</span></span>
* <span data-ttu-id="83f5f-117">Wenn Sie zuvor ein VPP-Token für ein anderes Produkt verwendet haben, müssen Sie für die Verwendung mit Intune ein neues erstellen.</span><span class="sxs-lookup"><span data-stu-id="83f5f-117">If you previously used a VPP token with a different product, you must generate a new one to use with Intune.</span></span>
* <span data-ttu-id="83f5f-118">Jedes Token ist ein Jahr lang gültig.</span><span class="sxs-lookup"><span data-stu-id="83f5f-118">Each token is valid for one year.</span></span>
* <span data-ttu-id="83f5f-119">Standardmäßig wird Intune zweimal täglich mit dem Apple VPP-Dienst synchronisiert.</span><span class="sxs-lookup"><span data-stu-id="83f5f-119">By default, Intune syncs with the Apple VPP service twice a day.</span></span> <span data-ttu-id="83f5f-120">Eine manuelle Synchronisierung können Sie jederzeit starten.</span><span class="sxs-lookup"><span data-stu-id="83f5f-120">You can start a manual sync at any time.</span></span>
* <span data-ttu-id="83f5f-121">Nachdem Sie den VPP-Token in Intune importiert haben, importieren Sie denselben Token in keine andere Geräteverwaltungslösung.</span><span class="sxs-lookup"><span data-stu-id="83f5f-121">After you have imported the VPP token to Intune, do not import the same token to any other device management solution.</span></span> <span data-ttu-id="83f5f-122">Andernfalls kann dies zu einem Verlust von Lizenzzuweisung und Benutzerdatensätzen führen.</span><span class="sxs-lookup"><span data-stu-id="83f5f-122">Doing so might result in the loss of license assignment and user records.</span></span>
* <span data-ttu-id="83f5f-123">Bevor Sie iOS-Bücher mit Intune verwenden, entfernen Sie alle vorhandenen, mit anderen Anbietern für die mobile Geräteverwaltung (MDM) erstellten VPP-Benutzerkonten.</span><span class="sxs-lookup"><span data-stu-id="83f5f-123">Before you start to use iOS books with Intune, remove any existing VPP user accounts created with other mobile device management (MDM) vendors.</span></span> <span data-ttu-id="83f5f-124">Aus Sicherheitsgründen synchronisiert Intune diese Benutzerkonten nicht.</span><span class="sxs-lookup"><span data-stu-id="83f5f-124">Intune does not synchronize those user accounts into Intune as a security measure.</span></span> <span data-ttu-id="83f5f-125">Intune synchronisiert nur Daten aus dem Apple VPP-Dienst, der von Intune erstellt wurde.</span><span class="sxs-lookup"><span data-stu-id="83f5f-125">Intune synchronizes only data from the Apple VPP service that Intune created.</span></span>
* <span data-ttu-id="83f5f-126">Wenn Sie ein Buch einem Gerät zuweisen, muss auf dem Gerät die integrierte iBooks-App installiert sein.</span><span class="sxs-lookup"><span data-stu-id="83f5f-126">When you assign a book to a device, that device must have the built-in iBooks app installed.</span></span> <span data-ttu-id="83f5f-127">Wenn dies nicht der Fall ist, muss der Endbenutzer die App erneut installieren, bevor er das Buch lesen kann.</span><span class="sxs-lookup"><span data-stu-id="83f5f-127">If it is not, the end user must reinstall the app before they can read the book.</span></span> <span data-ttu-id="83f5f-128">Sie können Intune derzeit nicht zum Wiederherstellen entfernt integrierter Apps verwenden.</span><span class="sxs-lookup"><span data-stu-id="83f5f-128">You cannot currently use Intune to restore removed built-in apps.</span></span>
* <span data-ttu-id="83f5f-129">Sie können nur Bücher von der Apple Volume Purchase Program-Website zuweisen.</span><span class="sxs-lookup"><span data-stu-id="83f5f-129">You can only assign books from the Apple Volume Purchase Program site.</span></span> <span data-ttu-id="83f5f-130">Sie können keine Bücher hochladen und dann zuweisen, die Sie intern erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="83f5f-130">You cannot upload, then assign books you created in-house.</span></span>
* <span data-ttu-id="83f5f-131">Sie können derzeit keine Bücher zu Endbenutzerkategorien zuweisen, so wie Sie Apps zuweisen können.</span><span class="sxs-lookup"><span data-stu-id="83f5f-131">You cannot currently assign books to end-user categories in the same way as you do apps.</span></span>
* <span data-ttu-id="83f5f-132">Das Freigeben einer Lizenz ist nicht möglich, nachdem das Buch zugewiesen wurde.</span><span class="sxs-lookup"><span data-stu-id="83f5f-132">You cannot reclaim a license once the book is assigned.</span></span>
* <span data-ttu-id="83f5f-133">Wenn ein Benutzer mit einem geeigneten Gerät erstmals versucht, ein VPP-Buch zu installieren, muss er dem Apple Volume Purchase Program beitreten, bevor er ein Buch installieren kann.</span><span class="sxs-lookup"><span data-stu-id="83f5f-133">When a user with an eligible device first tries to install a VPP book, they must join the Apple Volume Purchase program before they can install a book.</span></span> <span data-ttu-id="83f5f-134">Sie können auch Sicherheitsgruppen mit verwalteten Apple-IDs Lizenzen zuweisen.</span><span class="sxs-lookup"><span data-stu-id="83f5f-134">You can also assign licenses to security groups with managed Apple IDs.</span></span> <span data-ttu-id="83f5f-135">In diesem Fall müssen die Benutzer nicht ihre Apple-ID angeben, wenn ein Buch installiert wird.</span><span class="sxs-lookup"><span data-stu-id="83f5f-135">If you do this, then users are not prompted for their Apple ID when a book is installed.</span></span>

## <a name="to-get-and-upload-an-apple-vpp-token"></a><span data-ttu-id="83f5f-136">So können Sie einen Apple VPP-Token abrufen und hochladen</span><span class="sxs-lookup"><span data-stu-id="83f5f-136">To get and upload an Apple VPP token</span></span>

1. <span data-ttu-id="83f5f-137">Melden Sie sich beim Azure-Portal an.</span><span class="sxs-lookup"><span data-stu-id="83f5f-137">Sign into the Azure portal.</span></span>
2. <span data-ttu-id="83f5f-138">Wählen Sie **Weitere Dienste** > **Überwachung und Verwaltung** > **Intune** aus.</span><span class="sxs-lookup"><span data-stu-id="83f5f-138">Choose **More Services** > **Monitoring + Management** > **Intune**.</span></span>
3. <span data-ttu-id="83f5f-139">Wählen Sie auf dem Blatt **Intune** die Option **Mobile Apps** aus.</span><span class="sxs-lookup"><span data-stu-id="83f5f-139">On the **Intune** blade, choose **Mobile apps**.</span></span>
1.  <span data-ttu-id="83f5f-140">Wählen Sie in der Workload **Mobile Apps** die Option **Setup** > **iOS-VPP-Token** aus.</span><span class="sxs-lookup"><span data-stu-id="83f5f-140">In the **Mobile Apps** workload, choose **Setup** > **iOS VPP Tokens**.</span></span>
2.  <span data-ttu-id="83f5f-141">Klicken Sie auf dem Blatt mit der Liste der VPP-Token auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="83f5f-141">On the list of VPP tokens blade, click **Add**.</span></span>
3.  <span data-ttu-id="83f5f-142">Geben Sie auf dem Blatt **Neues VPP-Token** die folgenden Informationen an:</span><span class="sxs-lookup"><span data-stu-id="83f5f-142">On the **New VPP Token** blade, specify the following information:</span></span>
    - <span data-ttu-id="83f5f-143">**VPP-Tokendatei:** Stellen Sie sicher, dass Sie sich für das Volume Purchase Program für Unternehmen oder das Volume Purchase Program für Bildungseinrichtungen registriert haben.</span><span class="sxs-lookup"><span data-stu-id="83f5f-143">**VPP token file** - Ensure you have signed for the Volume Purchase Program for Business or the Volume Purchase Program for Education.</span></span> <span data-ttu-id="83f5f-144">Laden Sie dann das Apple-VPP-Token für Ihr Konto herunter und wählen es hier aus.</span><span class="sxs-lookup"><span data-stu-id="83f5f-144">Then, download the Apple VPP token for your account and select it here.</span></span>
    - <span data-ttu-id="83f5f-145">**Apple-ID:** Geben Sie die Apple-ID des Kontos ein, das dem Programm für Volumenlizenzen zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="83f5f-145">**Apple ID** - Enter the Apple ID of the account associated with the volume-purchase program.</span></span>
    - <span data-ttu-id="83f5f-146">**Typ des VPP-Kontos:** Wählen Sie **Unternehmen** oder **Bildungswesen** aus.</span><span class="sxs-lookup"><span data-stu-id="83f5f-146">**Type of VPP account** - Choose from **Business** or **Education**.</span></span>
4. <span data-ttu-id="83f5f-147">Klicken Sie abschließend auf **Hochladen**.</span><span class="sxs-lookup"><span data-stu-id="83f5f-147">When you are done, click **Upload**.</span></span>

<span data-ttu-id="83f5f-148">Das Token wird auf dem Blatt mit der Liste der Token angezeigt.</span><span class="sxs-lookup"><span data-stu-id="83f5f-148">The token is displayed in the list of tokens blade.</span></span>


<span data-ttu-id="83f5f-149">Sie können die von Apple gespeicherten Daten jederzeit mit Intune synchronisieren, indem Sie **Jetzt synchronisieren** wählen.</span><span class="sxs-lookup"><span data-stu-id="83f5f-149">You can synchronize the data held by Apple with Intune at any time by choosing **Sync now**.</span></span>

## <a name="to-assign-a-volume-purchased-app"></a><span data-ttu-id="83f5f-150">So weisen Sie per Volumenlizenz erworbene Apps zu</span><span class="sxs-lookup"><span data-stu-id="83f5f-150">To assign a volume-purchased app</span></span>

1. <span data-ttu-id="83f5f-151">Wählen Sie in der Workload **E-Books** die Option **Verwalten** > **Alle E-Books** aus.</span><span class="sxs-lookup"><span data-stu-id="83f5f-151">In the **eBooks** workload, choose **Manage** > **All eBooks**.</span></span>
2. <span data-ttu-id="83f5f-152">Wählen Sie auf dem Blatt mit der Liste der Bücher das Buch aus, das Sie zuweisen möchten, und dann **...** > **Gruppen zuweisen**.</span><span class="sxs-lookup"><span data-stu-id="83f5f-152">On the list of books blade, choose the book you want to assign, and then choose '**...**' > **Assign Groups**.</span></span>
3. <span data-ttu-id="83f5f-153">Wählen Sie auf dem Blatt <*Buchname*> - **Zugewiesene Gruppen** die Option **Verwalten** > **Zugewiesene Gruppen** aus.</span><span class="sxs-lookup"><span data-stu-id="83f5f-153">On the <*book name*> - **Groups Assigned** blade, choose **Manage** > **Groups Assigned**.</span></span>
4. <span data-ttu-id="83f5f-154">Wählen Sie **Gruppen zuweisen** und dann auf dem Blatt **Gruppen auswählen** die Azure AD-Benutzergruppen aus, denen Sie das Buch zuweisen möchten.</span><span class="sxs-lookup"><span data-stu-id="83f5f-154">Choose **Assign Groups** then, on the **Select groups** blade, choose the Azure AD user groups to which you want to assign the book.</span></span> <span data-ttu-id="83f5f-155">Gerätegruppen werden momentan nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="83f5f-155">Device groups are currently not supported.</span></span>
<span data-ttu-id="83f5f-156">Wählen Sie eine Zuweisungsaktion vom Typ **Verfügbar** oder **Erforderlich** aus.</span><span class="sxs-lookup"><span data-stu-id="83f5f-156">Choose an assignment action of **Available**, or **Required**.</span></span> 
5. <span data-ttu-id="83f5f-157">Wählen Sie abschließend **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="83f5f-157">Once you are done, choose **Save**.</span></span>

## <a name="next-steps"></a><span data-ttu-id="83f5f-158">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="83f5f-158">Next steps</span></span>

<span data-ttu-id="83f5f-159">Weitere Informationen zum Überwachen von Buchzuweisungen finden Sie unter [Überwachen von Apps](apps-monitor.md).</span><span class="sxs-lookup"><span data-stu-id="83f5f-159">See [How to monitor apps](apps-monitor.md) for information to help you monitor book assignments.</span></span>






