---
title: "Suchen eines Paketfamiliennamens (PFN) für Pro-App-VPN"
description: "Suchen Sie einen Paketfamiliennamen (PFN), den Sie zum Konfigurieren eines anwendungsbezogenen VPN („VPN pro App“) benötigen."
keywords: 
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 10/25/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 74643d1d-4fd9-4cff-ac79-1a42281d2f76
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: tycast
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 0e6251e67bdfd0d6bf3a0d972a02b671cf212eef
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2018
---
# <a name="find-a-package-family-name-pfn-for-per-app-vpn-configuration"></a><span data-ttu-id="bd9c4-103">Suchen eines Paketfamiliennamens (PFN) für eine Konfiguration mit VPN pro App</span><span class="sxs-lookup"><span data-stu-id="bd9c4-103">Find a package family name (PFN) for per-app VPN configuration</span></span>

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="bd9c4-104">Es gibt zwei Möglichkeiten zum Suchen eines Paketfamiliennamens (PFN), den Sie zum Einrichten eines anwendungsbezogenen VPNs benötigen.</span><span class="sxs-lookup"><span data-stu-id="bd9c4-104">There are two ways to find a PFN so that you can set up a per-app VPN.</span></span>

## <a name="find-a-pfn-for-an-app-thats-installed-on-a-windows-10-computer"></a><span data-ttu-id="bd9c4-105">Suchen eines PFN für eine App, die auf einem Windows 10-Computer installiert ist</span><span class="sxs-lookup"><span data-stu-id="bd9c4-105">Find a PFN for an app that's installed on a Windows 10 computer</span></span>

<span data-ttu-id="bd9c4-106">Wenn die App, mit der Sie arbeiten, bereits auf einem Windows 10-Computer installiert ist, können Sie den PFN mit dem PowerShell-Cmdlet [Get-AppxPackage](https://technet.microsoft.com/library/hh856044.aspx) abrufen.</span><span class="sxs-lookup"><span data-stu-id="bd9c4-106">If the app that you are working with is already installed on a Windows 10 computer, you can use the [Get-AppxPackage](https://technet.microsoft.com/library/hh856044.aspx) PowerShell cmdlet to get the PFN.</span></span>

<span data-ttu-id="bd9c4-107">Die Syntax für die „Get-AppxPackage“ lautet:</span><span class="sxs-lookup"><span data-stu-id="bd9c4-107">The syntax for Get-AppxPackage is:</span></span>

` Parameter Set: __AllParameterSets`
` Get-AppxPackage [[-Name] <String> ] [[-Publisher] <String> ] [-AllUsers] [-User <String> ] [ <CommonParameters>]`

> [!NOTE]
> <span data-ttu-id="bd9c4-108">Möglicherweise müssen Sie PowerShell als Administrator ausführen, um den PFN abzurufen.</span><span class="sxs-lookup"><span data-stu-id="bd9c4-108">You may have to run PowerShell as an admin to retrieve the PFN.</span></span>

<span data-ttu-id="bd9c4-109">Beispielsweise rufen Sie mit `Get-AppxPackage` die Informationen über alle auf dem Computer installierten universellen Apps ab.</span><span class="sxs-lookup"><span data-stu-id="bd9c4-109">For example, to get info about all the universal apps installed on the computer, use `Get-AppxPackage`.</span></span>

<span data-ttu-id="bd9c4-110">Wenn Sie Informationen über eine App abrufen möchten, von der Sie den Namen oder einen Teil des Namens kennen, verwenden Sie `Get-AppxPackage *<app_name>`.</span><span class="sxs-lookup"><span data-stu-id="bd9c4-110">To get info about an app when you know the name or part of the name, use `Get-AppxPackage *<app_name>`.</span></span> <span data-ttu-id="bd9c4-111">Das Verwenden des Platzhalterzeichens ist besonders nützlich, wenn Sie den vollständigen Namen der App nicht genau kennen.</span><span class="sxs-lookup"><span data-stu-id="bd9c4-111">Note the use of the wildcard character, which is particularly helpful if you're not sure of the full name of the app.</span></span> <span data-ttu-id="bd9c4-112">Zum Beispiel können Sie mit `Get-AppxPackage *OneNote` Informationen über OneNote abrufen.</span><span class="sxs-lookup"><span data-stu-id="bd9c4-112">For example, to get the info for OneNote, use `Get-AppxPackage *OneNote`.</span></span>


<span data-ttu-id="bd9c4-113">Für OneNote werden folgende Informationen abgerufen:</span><span class="sxs-lookup"><span data-stu-id="bd9c4-113">Here is the information retrieved for OneNote:</span></span>

`Name                   : Microsoft.Office.OneNote`

`Publisher              : CN=Microsoft Corporation, O=Microsoft Corporation, L=Redmond, S=Washington, C=US`

`Architecture           : X64`

`ResourceId             :`

`Version                : 17.6769.57631.0`

`PackageFullName        : Microsoft.Office.OneNote_17.6769.57631.0_x64__8wekyb3d8bbwe`

`InstallLocation        : C:\Program Files\WindowsApps`

`\Microsoft.Office.OneNote_17.6769.57631.0_x64__8wekyb3d8bbwe`

`IsFramework            : False`

**`PackageFamilyName      : Microsoft.Office.OneNote_8wekyb3d8bbwe`**

`PublisherId            : 8wekyb3d8bbwe`



## <a name="find-a-pfn-if-the-app-is-not-installed-on-a-computer"></a><span data-ttu-id="bd9c4-114">Suchen eines PFN, wenn die App nicht auf dem Computer installiert ist</span><span class="sxs-lookup"><span data-stu-id="bd9c4-114">Find a PFN if the app is not installed on a computer</span></span>

1.  <span data-ttu-id="bd9c4-115">Navigieren Sie zu „https://www.microsoft.com/store/apps“.</span><span class="sxs-lookup"><span data-stu-id="bd9c4-115">Go to https://www.microsoft.com/store/apps.</span></span>
2.  <span data-ttu-id="bd9c4-116">Geben Sie in der Suchleiste den Namen der App ein.</span><span class="sxs-lookup"><span data-stu-id="bd9c4-116">Enter the name of the app in the search bar.</span></span> <span data-ttu-id="bd9c4-117">Suchen Sie z.B. nach OneNote.</span><span class="sxs-lookup"><span data-stu-id="bd9c4-117">In our example, search for OneNote.</span></span>
3.  <span data-ttu-id="bd9c4-118">Wählen Sie den Link zu der App aus.</span><span class="sxs-lookup"><span data-stu-id="bd9c4-118">Choose the link to the app.</span></span> <span data-ttu-id="bd9c4-119">Am Ende der URL finden Sie eine Reihe von Buchstaben.</span><span class="sxs-lookup"><span data-stu-id="bd9c4-119">Note that the URL has a series of letters at the end.</span></span> <span data-ttu-id="bd9c4-120">In unserem Beispiel sieht die URL folgendermaßen aus: `https://www.microsoft.com/store/apps/onenote/9wzdncrfhvjl`.</span><span class="sxs-lookup"><span data-stu-id="bd9c4-120">In our example, the URL looks like this: `https://www.microsoft.com/store/apps/onenote/9wzdncrfhvjl`.</span></span>
4.  <span data-ttu-id="bd9c4-121">Fügen Sie in eine andere Registerkarte die folgende URL ein: `https://bspmts.mp.microsoft.com/v1/public/catalog/Retail/Products/<app id>/applockerdata`.</span><span class="sxs-lookup"><span data-stu-id="bd9c4-121">In a different tab, paste the following URL, `https://bspmts.mp.microsoft.com/v1/public/catalog/Retail/Products/<app id>/applockerdata`.</span></span> <span data-ttu-id="bd9c4-122">Ersetzen Sie `<app id>` durch die App-ID, die Sie unter „https://www.microsoft.com/store/apps“ gefunden haben (die Reihe von Buchstaben am Ende der URL aus Schritt 3).</span><span class="sxs-lookup"><span data-stu-id="bd9c4-122">Replace `<app id>` with the app id that you got from https://www.microsoft.com/store/apps - that series of letters at the end of the URL in step 3.</span></span> <span data-ttu-id="bd9c4-123">In unserem Beispiel für OneNote fügen Sie `https://bspmts.mp.microsoft.com/v1/public/catalog/Retail/Products/9wzdncrfhvjl/applockerdata` ein.</span><span class="sxs-lookup"><span data-stu-id="bd9c4-123">In our example of OneNote, you'd paste: `https://bspmts.mp.microsoft.com/v1/public/catalog/Retail/Products/9wzdncrfhvjl/applockerdata`.</span></span>

<span data-ttu-id="bd9c4-124">In Microsoft Edge werden die gewünschten Informationen angezeigt. In Internet Explorer müssen Sie **Öffnen** auswählen, um die Informationen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="bd9c4-124">Microsoft Edge shows the information that you want; in Internet Explorer, choose **Open** to see the information.</span></span> <span data-ttu-id="bd9c4-125">Der PFN wird in der ersten Zeile angegeben.</span><span class="sxs-lookup"><span data-stu-id="bd9c4-125">The PFN value is given on the first line.</span></span> <span data-ttu-id="bd9c4-126">Dies sind die Ergebnisse für unser Beispiel:</span><span class="sxs-lookup"><span data-stu-id="bd9c4-126">Here are the results for our example:</span></span>


`{`
`  "packageFamilyName": "Microsoft.Office.OneNote_8wekyb3d8bbwe",`
`  "packageIdentityName": "Microsoft.Office.OneNote",`
`  "windowsPhoneLegacyId": "ca05b3ab-f157-450c-8c49-a1f127f5e71d",`
`  "publisherCertificateName": "CN=Microsoft Corporation, O=Microsoft Corporation, L=Redmond, S=Washington, C=US"`
`}`
