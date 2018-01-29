---
title: "Intune AirPrint-Einstellungen für iOS- und macOS-Geräte"
titlesuffix: Azure portal
description: "Erfahren Sie, wie Sie Intune verwenden können, um iOS- und macOS-Geräte automatisch mit AirPrint-kompatiblen Druckern zu verbinden.\""
keywords: 
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 07/03/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 712a79fb-14ef-4f6b-aba5-1dfca900afd2
ms.reviewer: karanda
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: bc6dbe3c59495755aaab2a94e162833420ff658a
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2018
---
# <a name="airprint-settings-for-ios-and-macos-devices"></a><span data-ttu-id="34784-103">AirPrint-Einstellungen für iOS- und macOS-Geräte</span><span class="sxs-lookup"><span data-stu-id="34784-103">AirPrint settings for iOS and macOS devices</span></span>

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="34784-104">Verwenden Sie diese Einstellungen, um iOS- oder macOS-Geräte für die automatische Verbindung mit AirPrint-kompatiblen Druckern im Netzwerk zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="34784-104">Use these settings to configure iOS or macOS devices to automatically connect to AirPrint compatible printers on your network.</span></span> <span data-ttu-id="34784-105">Sie benötigen die IP-Adresse und den Ressourcenpfad der Drucker, um fortzufahren.</span><span class="sxs-lookup"><span data-stu-id="34784-105">You need the IP address and resource path of your printers to proceed.</span></span>

## <a name="find-airprint-printer-information"></a><span data-ttu-id="34784-106">Ermitteln von AirPrint-Druckerinformationen</span><span class="sxs-lookup"><span data-stu-id="34784-106">Find AirPrint printer information</span></span>

<span data-ttu-id="34784-107">Mit diesem Verfahren können Sie AirPrint-Informationen zur AirPrint-Nutzlast hinzufügen, sodass Benutzer von iOS-Geräten auf bekannten AirPrint-Druckern drucken können.</span><span class="sxs-lookup"><span data-stu-id="34784-107">Use this procedure to add AirPrint information to the AirPrint payload so that iOS device users can print to known AirPrint printers.</span></span>

1. <span data-ttu-id="34784-108">Öffnen Sie das Terminal auf einem Mac, der mit dem gleichen lokalen Netzwerk (Subnetz) verbunden ist wie die AirPrint-Drucker (über **/Anwendungen/Hilfsprogramme**).</span><span class="sxs-lookup"><span data-stu-id="34784-108">On a Mac that’s connected to the same local network (subnet) as the AirPrint printers, open Terminal (from **/Applications/Utilities**)</span></span>
2. <span data-ttu-id="34784-109">Geben Sie im Terminal die Zeichenfolge **ippfind** ein, und drücken Sie die EINGABETASTE.</span><span class="sxs-lookup"><span data-stu-id="34784-109">In the Terminal, type **ippfind**, then press enter.</span></span>
3. <span data-ttu-id="34784-110">Notieren Sie sich die vom Befehl zurückgegebenen Druckerinformationen, z.B.: **ipp://myprinter.local.:631/ipp/port1**.</span><span class="sxs-lookup"><span data-stu-id="34784-110">Make a note of any printer information the command returns, for example: **ipp://myprinter.local.:631/ipp/port1**.</span></span> <span data-ttu-id="34784-111">Beim ersten Teil der Informationen handelt es sich um den Namen des Druckers, beim letzten Teil um den Ressourcenpfad.</span><span class="sxs-lookup"><span data-stu-id="34784-111">The first part of the information is the name of your printer and the last part is the resource path.</span></span>
4. <span data-ttu-id="34784-112">Geben Sie im Terminal die Zeichenfolge **ping myprinter.local** ein, und drücken Sie die EINGABETASTE.</span><span class="sxs-lookup"><span data-stu-id="34784-112">In the Terminal, type **ping myprinter.local**, then press enter.</span></span>
5. <span data-ttu-id="34784-113">Notieren Sie sich die vom Befehl zurückgegebenen IP-Adressinformationen, z.B.: **PING myprinter.local (10.50.25.21)**.</span><span class="sxs-lookup"><span data-stu-id="34784-113">Make a note of the IP address information returned by the command, for example, **PING myprinter.local (10.50.25.21)**.</span></span>
6. <span data-ttu-id="34784-114">Verwenden Sie die IP-Adresse und den Ressourcenpfad in den Einstellungen der AirPrint-Nutzlast.</span><span class="sxs-lookup"><span data-stu-id="34784-114">Finally, use the IP address and resource path in the AirPrint payload settings.</span></span> <span data-ttu-id="34784-115">Eine IP-Adresse könnte beispielsweise **10.50.25.21** lauten, ein Ressourcenpfad **/ipp/port1**.</span><span class="sxs-lookup"><span data-stu-id="34784-115">An example IP address might be **10.50.25.21**, and an example resource path might be **/ipp/port1**.</span></span>

## <a name="configure-an-airprint-profile"></a><span data-ttu-id="34784-116">Konfigurieren eines AirPrint-Profils</span><span class="sxs-lookup"><span data-stu-id="34784-116">Configure an AirPrint profile</span></span>

1. <span data-ttu-id="34784-117">Wählen Sie auf dem Blatt **Gerätefunktionen** die Option **AirPrint** aus.</span><span class="sxs-lookup"><span data-stu-id="34784-117">On the **Device features** blade, choose **AirPrint**.</span></span>
2. <span data-ttu-id="34784-118">Um ein AirPrint-Ziel hinzuzufügen, geben Sie auf dem Blatt **AirPrint** die **IP-Adresse** und den **Ressourcenpfad** des Ziels ein, und klicken Sie auf **Hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="34784-118">On the **AirPrint** blade, to add an AirPrint destination, enter its **IP address** and **resource path**, and then click **Add**.</span></span>
3. <span data-ttu-id="34784-119">Fügen Sie so viele Ziele hinzu, wie Sie benötigen.</span><span class="sxs-lookup"><span data-stu-id="34784-119">Continue to add as many destinations as you need.</span></span> <span data-ttu-id="34784-120">Wenn Sie fertig sind, wählen Sie **OK** aus.</span><span class="sxs-lookup"><span data-stu-id="34784-120">When you are finished, choose **OK**.</span></span>

<span data-ttu-id="34784-121">Sie können auch eine Liste mit Druckern aus einer Datei mit durch Trennzeichen getrennten Werten (CSV-Datei) importieren oder die Liste exportieren.</span><span class="sxs-lookup"><span data-stu-id="34784-121">You can also import a list of printers from a comma-separated values (.csv) file or export the list.</span></span>


## <a name="next-steps"></a><span data-ttu-id="34784-122">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="34784-122">Next steps</span></span>

<span data-ttu-id="34784-123">Sie können nun das Geräteprofil den von Ihnen ausgewählten Gruppen zuweisen.</span><span class="sxs-lookup"><span data-stu-id="34784-123">You can now assign the device profile to the groups you choose.</span></span> <span data-ttu-id="34784-124">Weitere Informationen finden Sie unter [Zuweisen von Geräteprofilen](device-profile-assign.md).</span><span class="sxs-lookup"><span data-stu-id="34784-124">For details, see [How to assign device profiles](device-profile-assign.md).</span></span>