---
title: "Überwachen der Kompatibilität mit bedingtem Zugriff bei Exchange lokal und Exchange Online"
titlesuffix: Azure portal
description: "Überwachen der Kompatibilität mit bedingtem Zugriff bei Exchange lokal und Exchange Online durch das Azure-Portal für Intune"
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 04/24/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 5712682d-285b-43fd-9978-3dcfd95ec5f9
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: be0c1cef0dd6562feb54724edbf8ae22072e3d95
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2017
---
# <a name="monitor-conditional-access-compliance-for-on-premises-exchange-and-exchange-online-in-intune"></a><span data-ttu-id="15ae9-103">Überwachen der Konformität mit bedingtem Zugriff für Exchange lokal und Exchange Online in Intune</span><span class="sxs-lookup"><span data-stu-id="15ae9-103">Monitor conditional access compliance for on-premises Exchange and Exchange Online in Intune</span></span>

<span data-ttu-id="15ae9-104">Ab Version Intune 1704 können Administratoren Berichtsinformationen in Zusammenhang mit Exchange ActiveSync-Gerät-Geräteeinträgen sehen, die entweder über den lokalen Exchange-Connector oder dem Intune Service to Service Connector (Exchange Online-Connector) mit Intune synchronisiert werden.</span><span class="sxs-lookup"><span data-stu-id="15ae9-104">Beginning with Intune 1704 release, admins can see reporting information related to Exchange ActiveSync device records that are synchronized with Intune through either the on-premises Exchange Connector or the Intune service-to-service connector (Exchange Online connector).</span></span> <span data-ttu-id="15ae9-105">Berichte zur Kompatibilität mit bedingtem Zugriff enthalten eine Zusammenfassung der Geräte mit unterschiedlichen Synchronisierungsstatus:</span><span class="sxs-lookup"><span data-stu-id="15ae9-105">The conditional access compliance reporting provides a summary of devices with different synchronization states:</span></span>

-   <span data-ttu-id="15ae9-106">**Zulassen**</span><span class="sxs-lookup"><span data-stu-id="15ae9-106">**Allow**</span></span>

-   <span data-ttu-id="15ae9-107">**Blockieren**</span><span class="sxs-lookup"><span data-stu-id="15ae9-107">**Block**</span></span>

-   <span data-ttu-id="15ae9-108">**Quarantäne**</span><span class="sxs-lookup"><span data-stu-id="15ae9-108">**Quarantine**</span></span>

## <a name="to-monitor-conditional-access-compliance"></a><span data-ttu-id="15ae9-109">Überwachen der Kompatibilität mit bedingtem Zugriff</span><span class="sxs-lookup"><span data-stu-id="15ae9-109">To monitor conditional access compliance</span></span>

1.  <span data-ttu-id="15ae9-110">Melden Sie sich im [Azure-Portal](https://portal.azure.com/) mit Ihren Intune-Anmeldeinformationen an.</span><span class="sxs-lookup"><span data-stu-id="15ae9-110">Go to the [Azure portal](https://portal.azure.com/), and sign in with your Intune credentials.</span></span>

2.  <span data-ttu-id="15ae9-111">Sobald Sie erfolgreich angemeldet sind, wird das **Azure-Dashboard** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="15ae9-111">After you've successfully signed in, you see the **Azure Dashboard**.</span></span>

3.  <span data-ttu-id="15ae9-112">Wählen Sie im linken Menü **Weitere Dienste** aus, und geben Sie in das Filtertextfeld die Zeichenfolge **Intune** ein.</span><span class="sxs-lookup"><span data-stu-id="15ae9-112">Choose **More services** from the left menu, then type **Intune** in the text box filter.</span></span>

4.  <span data-ttu-id="15ae9-113">Wählen Sie **Intune** aus. Das **Intune-Dashboard** wird angezeigt.</span><span class="sxs-lookup"><span data-stu-id="15ae9-113">Choose **Intune**, you see the **Intune Dashboard**.</span></span>

5.  <span data-ttu-id="15ae9-114">Wählen Sie **Bedingter Zugriff** und dann **Übersicht** aus.</span><span class="sxs-lookup"><span data-stu-id="15ae9-114">Choose **Conditional Access**, then choose **Overview**.</span></span>

6.  <span data-ttu-id="15ae9-115">Wählen Sie im Diagramm einen der drei Bereiche (**Blockiert**, **Unter Quarantäne** oder **Zugelassen**) aus, um Ihre Berichte zur Kompatibilität mit bedingtem Zugriff anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="15ae9-115">Choose one of the three areas (**Blocked**, **Quarantine** or **Allowed**) on the chart to view your conditional access compliance reporting.</span></span>

    ![Dashboard für den bedingten Zugriff](./media/CA-reporting-intune-1.png)

<span data-ttu-id="15ae9-117">Nachdem Sie einen der drei Bereiche ausgewählt haben, können Sie weitere Details über zugelassene, blockierte oder unter Quarantäne gestellte Geräte sehen.</span><span class="sxs-lookup"><span data-stu-id="15ae9-117">Once you choose one of three areas, you can see more details about devices being allowed, blocked or quarantined.</span></span>

<span data-ttu-id="15ae9-118">Sie können auch ein Drilldown auf bestimmte Geräte ausführen, um weitere Details anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="15ae9-118">You can also drill down in specific devices to see more details.</span></span> <span data-ttu-id="15ae9-119">Beispielsweise ist das in der nachfolgenden Abbildung ausgewählte Gerät blockiert.</span><span class="sxs-lookup"><span data-stu-id="15ae9-119">For example, the device chosen on the image below is blocked.</span></span> <span data-ttu-id="15ae9-120">Intune bietet Ihnen die Möglichkeit, Unternehmensdaten auf dem Blatt zum Bericht zur Kompatibilität mit bedingtem Zugriff zu entfernen.</span><span class="sxs-lookup"><span data-stu-id="15ae9-120">Intune gives you the option of removing corporate data from the conditional access compliance report blade.</span></span>

![Bericht mit Informationen zu Geräten mit bedingtem Zugriff](./media/CA-reporting-intune-3.png)

<span data-ttu-id="15ae9-122">Auf dem Blatt mit den Gerätedetails finden Sie weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="15ae9-122">At the device details blade, you can see more information:</span></span>

-   <span data-ttu-id="15ae9-123">**Übersicht:** Folgende Eigenschaften des Geräts werden angezeigt: Betriebssystemversion, Gerätemodell, Besitz, Seriennummer, Gerätehersteller, Telefonnummer und Zeitpunkt, an dem das Gerät zuletzt eingecheckt wurde.</span><span class="sxs-lookup"><span data-stu-id="15ae9-123">**Overview:** You can see device properties like: OS version, device model, ownership, serial number, device manufacturer, phone number and last time the device checked in.</span></span>

-   <span data-ttu-id="15ae9-124">**Eigenschaften:** Sie können den Gerätebesitz (privat oder Unternehmen) festlegen.</span><span class="sxs-lookup"><span data-stu-id="15ae9-124">**Properties:** You can set the device ownership (Personal or Corporate).</span></span>

-   <span data-ttu-id="15ae9-125">**Hardware:** Dieser Abschnitt enthält Informationen, die Sie in der Übersicht sehen, sowie Speicherdetails (gesamter und freier Speicherplatz), Systemgehäuse, Netzwerkdetails, Netzwerkdienst und weitere Details über Sperrungen des bedingten Zugriffs.</span><span class="sxs-lookup"><span data-stu-id="15ae9-125">**Hardware:** It provides the information you see on the Overview, and also storage details (total space and free space), system enclosure, network details, network service, and more conditional access blocking details.</span></span>

-   <span data-ttu-id="15ae9-126">**Ermittelte Apps:** In diesem Abschnitt werden alle Programme angezeigt, die auf Ihrem Gerät installiert sind.</span><span class="sxs-lookup"><span data-stu-id="15ae9-126">**Discovered Apps:** It shows all applications installed at your device.</span></span> <span data-ttu-id="15ae9-127">Sie können die Liste der installierten Apps auch im .CSV-Format exportieren.</span><span class="sxs-lookup"><span data-stu-id="15ae9-127">You can also export the list of installed apps to .CSV format.</span></span>

-   <span data-ttu-id="15ae9-128">**Kompatibilität:** In diesem Abschnitt werden alle Details zu Richtlinien für die Gerätekompatibilität angezeigt.</span><span class="sxs-lookup"><span data-stu-id="15ae9-128">**Compliance:** It shows all device compliance policy details.</span></span>

-   <span data-ttu-id="15ae9-129">**Gerätekonfiguration:** In diesem Abschnitt werden alle Details zur Gerätekonfiguration angezeigt.</span><span class="sxs-lookup"><span data-stu-id="15ae9-129">**Device Configuration:** It shows all device configuration details.</span></span>

-   <span data-ttu-id="15ae9-130">**Exchange-Zugriff:** Hier finden Sie weitere Informationen über den Gerätestatus nach der Anwendung von Richtlinien für den bedingten Zugriff.</span><span class="sxs-lookup"><span data-stu-id="15ae9-130">**Exchange Access:** Here you can learn more about the device state after applying conditional access policies.</span></span>
