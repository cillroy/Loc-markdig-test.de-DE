---
title: Angeben von IMEI-Nummern
description: "Mithilfe von Microsoft Intune können Administratoren IMEI-Nummern für mobile Geräteplattformen zur Identifizierung von unternehmenseigenen mobilen Geräten importieren."
keywords: 
author: NathBarn
ms.author: nathbarn
manager: angrobe
ms.date: 03/22/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 1712bd39-562b-4409-9cec-155d5f4d8a39
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 0ada90ece798280db14aff6289b7e1c196bd3d83
ms.sourcegitcommit: e37e916e2bf14f092d3a767bc90d68c181d739fb
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/03/2018
---
# <a name="specify-corporate-owned-devices-with-international-mobile-equipment-identity-imei-numbers"></a><span data-ttu-id="eb868-103">Angeben unternehmenseigener Geräte über IMEI-Nummern (International Mobile Equipment Identity)</span><span class="sxs-lookup"><span data-stu-id="eb868-103">Specify corporate-owned devices with international mobile equipment identity (IMEI) numbers</span></span>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="eb868-104">Mithilfe von Microsoft Intune können Administratoren jetzt für mobile Geräteplattformen die entsprechenden IMEI-Nummern (International Mobile Equipment Identity) importieren, indem sie IMEI-Nummern für die Unterstützung der Identifizierung von unternehmenseigenen mobilen Geräten verwenden.</span><span class="sxs-lookup"><span data-stu-id="eb868-104">Microsoft Intune lets admins import international mobile equipment identity (IMEI) numbers for mobile device platforms by using IMEI numbers to help identify corporate-owned mobile devices.</span></span> <span data-ttu-id="eb868-105">Nachdem Geräte bei Intune registriert wurden, werden Geräte mit importierten IMEI-Nummern unter **Gruppen** > **Übersicht** > **Alle Geräte** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="eb868-105">After devices are enrolled in Intune, you can see devices that have imported IMEI numbers under **Groups** > **Overview** > **All Devices**.</span></span> <span data-ttu-id="eb868-106">**Gerätegruppe** listet Geräte mit importierten IMEI-Nummern in der Spalte **Besitz** als **Unternehmen** auf.</span><span class="sxs-lookup"><span data-stu-id="eb868-106">**Device group** lists devices that have imported IMEI numbers as **Corporate** in the **Ownership** column.</span></span>

1. <span data-ttu-id="eb868-107">Wechseln Sie in der [Microsoft Intune-Verwaltungskonsole](https://manage.microsoft.com) zu **Gruppen** &gt; **Alle Geräte** &gt; **Vorab registrierte Unternehmensgeräte** &gt; **Nach IMEI (Alle Plattformen)**, und wählen Sie anschließend **Geräte hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="eb868-107">In the [Microsoft Intune administration console](https://manage.microsoft.com), choose **Groups** &gt; **All Devices** &gt; **All Corporate Pre-enrolled Devices** &gt; **By IMEI (All platforms)**, and then choose **Add devices…**.</span></span> <span data-ttu-id="eb868-108">Sie können Geräte auf zwei Arten hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="eb868-108">You can add devices in two ways:</span></span>

   - <span data-ttu-id="eb868-109">**Eine CSV-Datei mit Seriennummern hochladen**: Erstellen Sie eine durch Trennzeichen getrennte Liste (.csv) mit zwei Spalten ohne Header, und beschränken Sie die Liste auf 5.000 Geräte oder 5 MB pro CSV-Datei.</span><span class="sxs-lookup"><span data-stu-id="eb868-109">**Upload a .csv file that has serial numbers** – Create a two-column, comma-separated value (.csv) list without a header, and limit the list to 5,000 devices or 5 MB per .csv file.</span></span> <span data-ttu-id="eb868-110">Das Detailfeld darf maximal 128 Zeichen enthalten.</span><span class="sxs-lookup"><span data-stu-id="eb868-110">The details field is limited to 128 characters.</span></span> 


     |||
     |-|-|
     |<span data-ttu-id="eb868-111">&lt;IMEI 1&gt;</span><span class="sxs-lookup"><span data-stu-id="eb868-111">&lt;IMEI #1&gt;</span></span>|<span data-ttu-id="eb868-112">&lt;Details zu Gerät 1&gt;</span><span class="sxs-lookup"><span data-stu-id="eb868-112">&lt;Device #1 Details&gt;</span></span>|
     |<span data-ttu-id="eb868-113">&lt;IMEI 2&gt;</span><span class="sxs-lookup"><span data-stu-id="eb868-113">&lt;IMEI #2&gt;</span></span>|<span data-ttu-id="eb868-114">&lt;Details zu Gerät 2&gt;</span><span class="sxs-lookup"><span data-stu-id="eb868-114">&lt;Device #2 Details&gt;</span></span>|

     <span data-ttu-id="eb868-115">Diese CSV-Datei wird bei der Anzeige in einem Text-Editor folgendermaßen angezeigt:</span><span class="sxs-lookup"><span data-stu-id="eb868-115">This .csv file when viewed in a text editor appears as:</span></span>

     ```
     01234567890123,device details
     02234567890123,device details
     ```

   - <span data-ttu-id="eb868-116">**Gerätedetails manuell hinzufügen**: Geben Sie die IMEI-Nummer und Gerätedetails von bis zu 15 Geräten ein.</span><span class="sxs-lookup"><span data-stu-id="eb868-116">**Manually add device details** - Enter the IMEI number and device details of up to 15 devices.</span></span>

   <span data-ttu-id="eb868-117">Das Feld *Details* ist für Verwaltungszwecke bestimmt.</span><span class="sxs-lookup"><span data-stu-id="eb868-117">The *Details* field is for administrative use.</span></span> <span data-ttu-id="eb868-118">Sie können Details angeben, um das Gerät in der Liste der nach Hardware-ID aufgeführten firmeneigenen Geräte leichter zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="eb868-118">You can specify details to help identify the device in the list of Corporate-owned devices listed by hardware ID.</span></span> <span data-ttu-id="eb868-119">Diese Informationen werden nicht an das Gerät gesendet, jedoch in der Intune-Konsole angezeigt.</span><span class="sxs-lookup"><span data-stu-id="eb868-119">This information is not sent to the device, but it will appear in the Intune console.</span></span>

2. <span data-ttu-id="eb868-120">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="eb868-120">Choose **Next**.</span></span>
3. <span data-ttu-id="eb868-121">Im Bereich **Geräte überprüfen** können Sie die importierten IMEI-Nummern der Geräte bestätigen.</span><span class="sxs-lookup"><span data-stu-id="eb868-121">On the **Review Devices** pane, you can confirm the imported device IMEI numbers.</span></span> <span data-ttu-id="eb868-122">Sie können zudem entscheiden, ob die **Details** für IMEI-Nummern, die erneut importiert werden, überschrieben werden sollen.</span><span class="sxs-lookup"><span data-stu-id="eb868-122">You can also decide whether to overwrite the **Details** for IMEI numbers that are being imported again.</span></span> <span data-ttu-id="eb868-123">Sie können das Kontrollkästchen **Überschreiben** deaktivieren, um die aktuellen Informationen zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="eb868-123">You can uncheck the **Overwrite** box to preserve the Current details.</span></span> <span data-ttu-id="eb868-124">Klicken Sie auf **Fertig stellen**, um die IMEI-Nummern zu importieren.</span><span class="sxs-lookup"><span data-stu-id="eb868-124">Choose **Finish** to import the IMEI numbers.</span></span>
4. <span data-ttu-id="eb868-125">Die importierten IMEI-Nummern und Beschreibungen werden zur Liste **Nach IMEI (Alle Plattformen)** hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="eb868-125">The imported IMEI numbers and descriptions are added to the **By IMEI (All platforms)** list.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="eb868-126">Wenn Sie IMEI-Nummern für Android-Geräte importieren, achten Sie darauf, dass einige Android-Geräte über mehrere IMEI-Nummern verfügen können.</span><span class="sxs-lookup"><span data-stu-id="eb868-126">If you are importing IMEI numbers for Android devices, be aware that some Android devices can have multiple IMEI numbers.</span></span> <span data-ttu-id="eb868-127">Wenn Sie eine IMEI-Nummer importieren, es sich aber nicht um die IMEI-Nummer handelt, die vom Gerät an Intune gemeldet wird, wird das Gerät als ein persönliches Gerät und nicht als ein unternehmenseigenes Gerät eingestuft.</span><span class="sxs-lookup"><span data-stu-id="eb868-127">If you import an IMEI number but it is not the IMEI reported to Intune by the device, the device will be classifed as a personal device instead of a company-owned device.</span></span>

<span data-ttu-id="eb868-128">Wenn ein Gerät mit einer IMEI-Nummer bei Intune registriert wird (in der Regel, wenn ein Benutzer die Unternehmensportal-App installiert und den Registrierungsvorgang abschließt), wird das Gerät als „unternehmenseigen“ gekennzeichnet und in der Gruppe **IMEI-Geräte** als registriert angezeigt.</span><span class="sxs-lookup"><span data-stu-id="eb868-128">When a device that has IMEI number enrolls in Intune, usually when a user installs the Company Portal app and completes the enrollment process, the device will be tagged as corporate-owned and appear as enrolled in the **IMEI Devices** group.</span></span>

>[!NOTE]
> <span data-ttu-id="eb868-129">Wenn Ihre Organisation demnächst zum neuen Azure-Portal migriert wird, erkennen Sie eine Veränderung dieser Funktion.</span><span class="sxs-lookup"><span data-stu-id="eb868-129">When your organization is migrated to the new Azure portal in the near future, you will see a change to this feature.</span></span> <span data-ttu-id="eb868-130">In der vorhandenen Intune-Administratorkonsole können Administratoren zugehörige Details einer hochgeladenen CSV-Datei akzeptieren und die vorhandenen Details für einzelne Hardware-IDs überschreiben.</span><span class="sxs-lookup"><span data-stu-id="eb868-130">In the existing Intune administrator console, admins can accept associated details from an uploaded CSV and overwrite the existing details for individual hardware identifiers.</span></span> <span data-ttu-id="eb868-131">Sie können im neuen Azure-Portal automatisch die Details für alle Hardware-IDs überschreiben oder alle neuen Details für vorhandene IDs ignorieren.</span><span class="sxs-lookup"><span data-stu-id="eb868-131">In the new Azure portal, you’ll be able to automatically overwrite the details for all hardware identifiers or to ignore all new details for existing identifiers.</span></span>

<span data-ttu-id="eb868-132">Detaillierte Angaben über International Mobile Equipment Identifier finden Sie unter [3GGPP TS 23.003](https://portal.3gpp.org/desktopmodules/Specifications/SpecificationDetails.aspx?specificationId=729).</span><span class="sxs-lookup"><span data-stu-id="eb868-132">For detailed specifications about International Mobile Equipment Identifiers, see [3GGPP TS 23.003](https://portal.3gpp.org/desktopmodules/Specifications/SpecificationDetails.aspx?specificationId=729).</span></span>
