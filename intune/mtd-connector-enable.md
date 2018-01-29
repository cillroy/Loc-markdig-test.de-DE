---
title: Aktivieren des Mobile Threat Defense-Connectors mit Intune
titlesuffix: Azure portal
description: Aktivieren Sie den Mobile Threat Defense-Connector in Intune.
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 06/21/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: dbb6a37e-ba47-4b69-922c-d25e66c279f6
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 2808eb3751ee0187f7b58091fc3c3ad3fcbb3229
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2018
---
# <a name="enable-mobile-threat-defense-in-intune"></a><span data-ttu-id="3e82b-103">Aktivieren von Mobile Threat Defense in Intune</span><span class="sxs-lookup"><span data-stu-id="3e82b-103">Enable Mobile Threat Defense in Intune</span></span>

> [!NOTE] 
> <span data-ttu-id="3e82b-104">Dieses Thema gilt für alle Mobile Threat Defense-Partner.</span><span class="sxs-lookup"><span data-stu-id="3e82b-104">This topic applies to all Mobile Threat Defense partners.</span></span>

<span data-ttu-id="3e82b-105">Um die Verbindung mit Mobile Threat Defense (MTD) in Intune zu aktivieren, muss der Intune-Connector in der MTD-Partnerkonsole bereits konfiguriert sein.</span><span class="sxs-lookup"><span data-stu-id="3e82b-105">To enable the Mobile Threat Defense (MTD) connection in Intune, you should have already configured the Intune Connector in the MTD partner console.</span></span>

## <a name="to-enable-the-mtd-connector"></a><span data-ttu-id="3e82b-106">So aktivieren Sie den MTD-Connector</span><span class="sxs-lookup"><span data-stu-id="3e82b-106">To enable the MTD connector</span></span>

1. <span data-ttu-id="3e82b-107">Melden Sie sich im [Azure-Portal](https://portal.azure.com) mit Ihren Intune-Anmeldeinformationen an.</span><span class="sxs-lookup"><span data-stu-id="3e82b-107">Go to the [Azure portal](https://portal.azure.com), and sign in with your Intune credentials.</span></span> <span data-ttu-id="3e82b-108">Sobald Sie erfolgreich angemeldet sind, wird das **Azure-Dashboard** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="3e82b-108">After you've successfully signed in, you see the **Azure Dashboard**.</span></span>

2. <span data-ttu-id="3e82b-109">Wählen Sie im **Azure-Dashboard** im linken Menü **Weitere Dienste** aus, und geben Sie in das Filtertextfeld **Intune** ein.</span><span class="sxs-lookup"><span data-stu-id="3e82b-109">On the **Azure Dashboard**, choose **More services** from the left menu, then type **Intune** in the text box filter.</span></span>

3. <span data-ttu-id="3e82b-110">Wählen Sie **Intune** aus. Das **Intune-Dashboard** wird geöffnet.</span><span class="sxs-lookup"><span data-stu-id="3e82b-110">Choose **Intune**, the **Intune Dashboard** opens.</span></span>

4. <span data-ttu-id="3e82b-111">Wählen Sie im **Intune-Dashboard** zuerst **Gerätekompatibilität** und dann im Abschnitt **Setup** die Option **Mobile Threat Defense** aus.</span><span class="sxs-lookup"><span data-stu-id="3e82b-111">On the **Intune Dashboard**, choose **Device compliance**, then choose **Mobile Threat Defense** under the **Setup** section.</span></span>

5. <span data-ttu-id="3e82b-112">Wählen Sie auf dem Blatt **Mobile Threat Defense** die Option **Hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="3e82b-112">On the **Mobile Threat Defense** blade, choose **Add**.</span></span>

6. <span data-ttu-id="3e82b-113">Wählen Sie Ihre MTD-Lösung in der Dropdownliste unter **Einzurichtenden MTD-Connector (Mobile Threat Defense) auswählen** aus.</span><span class="sxs-lookup"><span data-stu-id="3e82b-113">Choose your MTD solution as the **Mobile Threat Defense connector to setup** from the drop-down list.</span></span>

    ![MTD-Einrichtung im Intune Azure-Portal](./media/enable-mtd-connector-1.png)

7. <span data-ttu-id="3e82b-115">Aktivieren Sie die Umschaltoptionen entsprechend den Anforderungen Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="3e82b-115">Enable the toggle options according to your organization's requirements.</span></span>

## <a name="mtd-toggle-options"></a><span data-ttu-id="3e82b-116">MTD-Umschaltoptionen</span><span class="sxs-lookup"><span data-stu-id="3e82b-116">MTD toggle options</span></span>

<span data-ttu-id="3e82b-117">Sie können entscheiden, welche MTD-Umschaltoptionen Sie entsprechend den Anforderungen Ihrer Organisation aktivieren müssen.</span><span class="sxs-lookup"><span data-stu-id="3e82b-117">You can decide which MTD toggle options you need to enable according to your organization's requirements.</span></span> <span data-ttu-id="3e82b-118">Ausführlichere Informationen:</span><span class="sxs-lookup"><span data-stu-id="3e82b-118">Here's more details:</span></span>

- <span data-ttu-id="3e82b-119">**Herstellen einer Verbindung zwischen Geräten unter Android 4.1 und höher und MTD von [MTD-Partnername] for Work**: Wenn Sie diese Option aktivieren, können Geräte unter Android 4.1 und höher Sicherheitsrisiken an Intune melden.</span><span class="sxs-lookup"><span data-stu-id="3e82b-119">**Connect Android 4.1+ devices to [MTD partner name] for Work MTD**: When you enable this option, you can have Android 4.1+ devices reporting security risk back to Intune.</span></span>
    - <span data-ttu-id="3e82b-120">**Als nicht kompatibel markieren, wenn keine Daten erhalten werden**: Wenn Intune keine Daten über ein Gerät auf dieser Plattform vom MTD-Partner empfängt, betrachten Sie das Gerät als nicht kompatibel.</span><span class="sxs-lookup"><span data-stu-id="3e82b-120">**Mark as non-compliant if no data is received**: If Intune doesn't receive data about a device on this platform from the MTD partner, consider the device non-compliant.</span></span>
<br></br>
- <span data-ttu-id="3e82b-121">**Herstellen einer Verbindung zwischen Geräten unter iOS 8.0 und höher und MTD von [MTD-Partnername] for Work**: Wenn Sie diese Option aktivieren, können Geräte unter Android 4.1 und höher Sicherheitsrisiken an Intune melden.</span><span class="sxs-lookup"><span data-stu-id="3e82b-121">**Connect iOS 8.0+ devices to [MTD partner name] for Work MTD**: When you enable this option, you can have Android 4.1+ devices reporting security risk back to Intune.</span></span>
    - <span data-ttu-id="3e82b-122">**Als nicht kompatibel markieren, wenn keine Daten erhalten werden**: Wenn Intune keine Daten über ein Gerät auf dieser Plattform vom MTD-Partner empfängt, betrachten Sie das Gerät als nicht kompatibel.</span><span class="sxs-lookup"><span data-stu-id="3e82b-122">**Mark as non-compliant if no data is received**: If Intune doesn't receive data about a device on this platform from the MTD partner, consider the device non-compliant.</span></span>
<br></br>
- <span data-ttu-id="3e82b-123">**Nicht unterstützte Betriebssystemversionen blockieren**: Blockieren, wenn auf dem Gerät eine frühere Betriebssystem ausgeführt wird, als die minimal unterstützte Version.</span><span class="sxs-lookup"><span data-stu-id="3e82b-123">**Block unsupported OS versions**: Block if the device is running an operating system less than the minimum supported version.</span></span>

- <span data-ttu-id="3e82b-124">**Anzahl von Tagen, bis Partner als nicht reaktionsfähig gilt**: Anzahl von Tagen mit Inaktivität, bevor Intune den Partner als nicht reaktionsfähig betrachtet, da die Verbindung unterbrochen wurde.</span><span class="sxs-lookup"><span data-stu-id="3e82b-124">**Number of days until partner is unresponsive**: Number of days of inactivity before Intune considers teh partner to be unresponsive because the connection is lost.</span></span> <span data-ttu-id="3e82b-125">Intune ignoriert den Kompatibilitätszustand für nicht reaktionsfähige MTD-Partner.</span><span class="sxs-lookup"><span data-stu-id="3e82b-125">Intune ignores compliance state for unresponsive MTD partners.</span></span>

> [!IMPORTANT] 
> <span data-ttu-id="3e82b-126">Sie müssen die MTD-Apps hinzufügen und zuweisen, bevor Sie die Richtlinienregeln für Kompatibilität und bedingten Zugriff erstellen.</span><span class="sxs-lookup"><span data-stu-id="3e82b-126">You must add and assign the MTD apps before creating the device compliance and the conditional access policy rules.</span></span> <span data-ttu-id="3e82b-127">Dadurch wird sichergestellt, dass die MTD-App für die Installation durch Endbenutzer bereit und verfügbar ist, bevor sie Zugriff auf E-Mail oder andere Unternehmensressourcen erhalten.</span><span class="sxs-lookup"><span data-stu-id="3e82b-127">This ensures that the MTD app is ready and available for end users to install before they can get access to email or other company resources.</span></span>

> [!TIP]
> <span data-ttu-id="3e82b-128">Der **Verbindungsstatus** und der Zeitpunkt **der letzten Synchronisierung** zwischen Intune und dem MTD-Partner werden auf dem Blatt „Mobile Threat Defense“ angezeigt.</span><span class="sxs-lookup"><span data-stu-id="3e82b-128">You can see the **Connection status** and the **Last synchronized** time between Intune and the MTD partner from the Mobile Threat Defense blade.</span></span>
