---
title: "Registrieren Ihres Windows 10-Geräts bei Intune | Microsoft-Dokumentation"
description: "Registrieren Sie ein Windows 10 1607-Gerät (oder höher) bei Intune."
keywords: 
author: barlanmsft
ms.author: barlan
manager: angrobe
ms.date: 05/22/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 812e82df-76df-402b-bfe9-29302838f40e
searchScope: User help
ROBOTS: 
ms.reviewer: jieyang
ms.suite: ems
ms.custom: intune-enduser
ms.openlocfilehash: 3f575797a09fb4d74c2da2a7dc6b14a9723d3f4d
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2017
---
# <a name="enroll-your-windows-10-device-in-intune"></a><span data-ttu-id="85790-103">Registrieren eines Windows 10-Geräts bei Intune</span><span class="sxs-lookup"><span data-stu-id="85790-103">Enroll your Windows 10 device in Intune</span></span>

> [!NOTE]
> <span data-ttu-id="85790-104">Windows 10 funktioniert auf allen Geräten.</span><span class="sxs-lookup"><span data-stu-id="85790-104">Windows 10 works across all types of devices.</span></span> <span data-ttu-id="85790-105">Egal, ob Sie einen Desktop-Computer, ein Smartphone oder ein Tablet verwenden, sind die zu befolgenden Schritte dieselben, auch wenn sie sich geringfügig von den Bildern auf dieser Seite unterscheiden.</span><span class="sxs-lookup"><span data-stu-id="85790-105">Whether you're using a desktop, phone, or tablet, the steps you follow are the same - even if they look slightly different from the images on this page.</span></span>

> [!VIDEO https://channel9.msdn.com/Series/IntuneEnrollment/Windows-Enrollment/player]

1. <span data-ttu-id="85790-106">Öffnen Sie das **Startmenü**.</span><span class="sxs-lookup"><span data-stu-id="85790-106">Go to **Start**.</span></span>

  - <span data-ttu-id="85790-107">Gehen Sie auf einem **Windows 10 Desktop**-Gerät auf das **Startmenü**.</span><span class="sxs-lookup"><span data-stu-id="85790-107">If you are on a **Windows 10 desktop** device, go to the **Start menu**.</span></span>
  - <span data-ttu-id="85790-108">Wenn Sie ein **Windows 10-Mobilgerät** besitzen, gehen Sie zum **Startbildschirm**, dann wischen Sie zur Liste **Alle Apps**.</span><span class="sxs-lookup"><span data-stu-id="85790-108">If you are on a **Windows 10 Mobile** device, go to the **Start screen**, then swipe to the **All Apps** list.</span></span>

2.  <span data-ttu-id="85790-109">Öffnen Sie die Windows **Einstellungen**-App, indem Sie in der Suchleiste nach „Einstellungen“ suchen.</span><span class="sxs-lookup"><span data-stu-id="85790-109">Open the Windows **Settings** app by searching for "settings" in the search bar.</span></span>

3. <span data-ttu-id="85790-110">Wählen Sie **Konten** > **Zugriff auf Geschäfts-, Schul- oder Unikonto** > **Verbinden** aus.</span><span class="sxs-lookup"><span data-stu-id="85790-110">Select **Accounts** > **Access work or school** > **Connect**.</span></span>

    ![Wählen Sie „Auf Geschäfts-,Schul- oder Unikonto zugreifen“ aus](./media/w10-enroll-rs1-connect-to-work-or-school.png)

3.  <span data-ttu-id="85790-112">Geben Sie die E-Mail-Adresse Ihres Geschäfts-, Schul- oder Unikontos ein, und wählen Sie **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="85790-112">Enter your work or school email address, and then select **Next**.</span></span>

    ![Enter your work or school-account](./media/w10-enroll-rs1-set-up-work-or-school-account.png)

4. <span data-ttu-id="85790-114">Melden Sie sich mit Ihrem Geschäfts-, Schul- oder Unikonto bei Intune an.</span><span class="sxs-lookup"><span data-stu-id="85790-114">Sign in to Intune with your work or school account.</span></span>

    ![Geschäfts- oder Schulkonto hinzufügen](./media/w10-enroll-rs1-enter-your-credentials.png)

    <span data-ttu-id="85790-116">In einer Meldung wird angezeigt, dass Ihr Unternehmen oder Ihre Bildungseinrichtung das Gerät registriert.</span><span class="sxs-lookup"><span data-stu-id="85790-116">You’ll see a message indicating that your company or school is registering your device.</span></span>

5. <span data-ttu-id="85790-117">Wenn die Seite **Alles bereit!**</span><span class="sxs-lookup"><span data-stu-id="85790-117">When you see the **You’re all set!**</span></span> <span data-ttu-id="85790-118">sehen, wählen Sie **Schließen** aus.</span><span class="sxs-lookup"><span data-stu-id="85790-118">screen, select **Close**.</span></span> <span data-ttu-id="85790-119">Der Vorgang ist abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="85790-119">You’re done.</span></span>

  ![Klicken Sie auf dem Bildschirm „Alles erledigt!“](./media/w10-enroll-rs1-youre-all-set.png)

6. <span data-ttu-id="85790-122">Wenn Sie die Verbindung noch einmal überprüfen möchten, kehren Sie zu den **Einstellungen** zurück. Ihr Geschäfts-, Schul- oder Unikonto wird jetzt aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="85790-122">If you want to double-check that your connection looks right, go back to **Settings**, where you should now see your work or school account listed.</span></span>

    ![Validate that the connection was set up correctly](./media/w10-enroll-rs1-validate-successful-enrollment.png)

<span data-ttu-id="85790-124">Wenn Sie die obigen Schritte ausgeführt haben und trotzdem nicht auf E-Mails und Dateien Ihres Geschäfts-, Schul- oder Unikontos zugreifen können, befolgen Sie die Schritte unter [Schritte zur Problembehandlung bei Anzeige von „Zugriff auf Geschäfts-, Schul- oder Unikonto“](troubleshoot-your-windows-10-device-windows.md#troubleshooting-steps-to-follow-if-you-see-access-work-or-school).</span><span class="sxs-lookup"><span data-stu-id="85790-124">If you followed the previous steps, but still can’t access your work or school email account and files, follow the steps in [Troubleshooting steps to follow if you see Access work or school](troubleshoot-your-windows-10-device-windows.md#troubleshooting-steps-to-follow-if-you-see-access-work-or-school).</span></span>
