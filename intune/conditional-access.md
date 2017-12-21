---
title: "Bedingter Zugriff über Intune"
titlesuffix: Azure portal
description: "Erfahren Sie, wie Sie die Bedingungen definieren, die Benutzer und Geräte erfüllen müssen, um Zugriff auf Unternehmensressourcen in Microsoft Intune zu erhalten.\""
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 05/23/2017
ms.topic: get-started-article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: a1973f38-ea55-43eb-a151-505fb34a8afb
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 6e2deb008b63fd9e9e9f37674c81745a0c8ccb04
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2017
---
# <a name="whats-conditional-access"></a><span data-ttu-id="d482f-103">Was ist bedingter Zugriff?</span><span class="sxs-lookup"><span data-stu-id="d482f-103">What's conditional access?</span></span>

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="d482f-104">Dieses Thema beschreibt den bedingten Zugriff für Enterprise Mobility + Security (EMS) und erläutert anschließend häufige Szenarien mit bedingtem Zugriff bei Verwendung von Intune.</span><span class="sxs-lookup"><span data-stu-id="d482f-104">This topic describes Conditional access as it applies to Enterprise Mobility + Security (EMS), and follows that with Conditional access common scenarios when using Intune.</span></span>

<span data-ttu-id="d482f-105">Der bedingte Zugriff von Enterprise Mobility + Security (EMS) ist kein eigenständiges Produkt, sondern eine Lösung, die für alle Dienste und Produkte im Rahmen von EMS gilt.</span><span class="sxs-lookup"><span data-stu-id="d482f-105">Enterprise Mobility + Security (EMS) Conditional Access is not a standalone product, it’s a solution that takes part on all services and products that are part of the EMS.</span></span> <span data-ttu-id="d482f-106">Die Lösung bietet eine präzise Zugriffssteuerung, sodass Sie die Sicherheit Ihrer Unternehmensdaten gewährleisten und gleichzeitig dafür sorgen können, dass die Benutzer mit jedem Gerät und an jedem Standort optimal arbeiten können.</span><span class="sxs-lookup"><span data-stu-id="d482f-106">It provides granular access control to keep your corporate data secure, while giving users an experience that allows them to do their best work from any device, and from any location.</span></span>

<span data-ttu-id="d482f-107">Sie können Bedingungen definieren, die den Zugriff auf Ihre Unternehmensdaten basierend auf dem Ort, dem Gerät, dem Benutzerstatus und der Vertraulichkeit der Anwendung einschränken.</span><span class="sxs-lookup"><span data-stu-id="d482f-107">You can define conditions that gate access to your corporate data based on location, device, user state, and application sensitivity.</span></span>

> [!NOTE] 
> <span data-ttu-id="d482f-108">Der bedingte Zugriff kann auch auf [Office 365-Dienste](https://blogs.technet.microsoft.com/wbaer/2017/02/17/conditional-access-policies-with-sharepoint-online-and-onedrive-for-business/) angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="d482f-108">Conditional Access also extends its capabilities to [Office 365 services](https://blogs.technet.microsoft.com/wbaer/2017/02/17/conditional-access-policies-with-sharepoint-online-and-onedrive-for-business/).</span></span>

![Architekturdiagramm für den bedingten Zugriff](./media/ca-diagram-1.png)

## <a name="conditional-access-with-intune"></a><span data-ttu-id="d482f-110">Bedingter Zugriff über Intune</span><span class="sxs-lookup"><span data-stu-id="d482f-110">Conditional access with Intune</span></span>

<span data-ttu-id="d482f-111">Intune fügt Richtlinien für die Konformität mobiler Geräte und für die Verwaltung mobiler Apps hinzu, um die Lösung des bedingten Zugriffs für EMS zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="d482f-111">Intune adds mobile device compliance and app management policies to support the EMS Conditional Access solution.</span></span>

![Intune und der bedingte Zugriff bei Verwendung von EMS](./media/intune-with-ca-1.png)

<span data-ttu-id="d482f-113">Möglichkeiten der Verwendung des bedingten Zugriffs in Intune:</span><span class="sxs-lookup"><span data-stu-id="d482f-113">Ways to use conditional access with Intune:</span></span>

-   <span data-ttu-id="d482f-114">**Gerätebasierter bedingter Zugriff**</span><span class="sxs-lookup"><span data-stu-id="d482f-114">**Device-based conditional access**</span></span>

    -   <span data-ttu-id="d482f-115">Bedingter Zugriff für Exchange lokal</span><span class="sxs-lookup"><span data-stu-id="d482f-115">Conditional access for Exchange on-premises</span></span>

    -   <span data-ttu-id="d482f-116">Bedingter Zugriff basierend auf der Netzwerkzugriffssteuerung</span><span class="sxs-lookup"><span data-stu-id="d482f-116">Conditional access based on network access control</span></span>

    -   <span data-ttu-id="d482f-117">Bedingter Zugriff basierend auf dem Geräterisiko</span><span class="sxs-lookup"><span data-stu-id="d482f-117">Conditional access based on device risk</span></span>

    -   <span data-ttu-id="d482f-118">Bedingter Zugriff für Windows-PCs</span><span class="sxs-lookup"><span data-stu-id="d482f-118">Conditional access for Windows PCs</span></span>

        -   <span data-ttu-id="d482f-119">Unternehmenseigene Geräte</span><span class="sxs-lookup"><span data-stu-id="d482f-119">Corporate-owned</span></span>

        -   <span data-ttu-id="d482f-120">Bring Your Own Device (BYOD)</span><span class="sxs-lookup"><span data-stu-id="d482f-120">Bring your own device (BYOD)</span></span>

-   <span data-ttu-id="d482f-121">**App-basierter bedingter Zugriff**</span><span class="sxs-lookup"><span data-stu-id="d482f-121">**App-based conditional access**</span></span>

## <a name="next-steps"></a><span data-ttu-id="d482f-122">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="d482f-122">Next steps</span></span>

[<span data-ttu-id="d482f-123">Gängige Möglichkeiten der Verwendung des bedingten Zugriffs in Intune</span><span class="sxs-lookup"><span data-stu-id="d482f-123">Common ways to use conditional access with Intune</span></span>](conditional-access-intune-common-ways-use.md)
