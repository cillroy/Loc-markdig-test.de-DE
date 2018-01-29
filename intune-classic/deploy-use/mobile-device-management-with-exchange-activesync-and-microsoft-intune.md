---
title: "Geräteverwaltung mit Exchange Active Sync"
description: "Verwalten mobiler Geräte mit der Exchange ActiveSync (EAS)-Verwaltung und dem Exchange Connector"
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 07/29/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 14f5cf53-6764-4e22-a18b-fa750b3acd41
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: chrisgre
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: f5e9bd3dd2026096c323858fc7faa915895ed55d
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2018
---
# <a name="exchange-activesync-mobile-device-management-with-microsoft-intune"></a><span data-ttu-id="ab45e-103">Verwaltung mobiler Geräte mit Exchange ActiveSync und Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="ab45e-103">Exchange ActiveSync mobile device management with Microsoft Intune</span></span>

[!INCLUDE [classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="ab45e-104">Damit mobile Geräte direkt mit Microsoft Intune verwaltet werden können, müssen sie [bei Intune registriert](prerequisites-for-enrollment.md) sein.</span><span class="sxs-lookup"><span data-stu-id="ab45e-104">For Microsoft Intune to directly manage mobile devices, devices must be [enrolled in Intune](prerequisites-for-enrollment.md).</span></span> <span data-ttu-id="ab45e-105">Alternativ können Administratoren eine eingeschränktere Verwaltungslösung ermöglichen, bei der die Exchange ActiveSync-Verwaltung (EAS) mit einem Exchange Connector verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="ab45e-105">As an alternative, admins can enable a more limited management solution that uses Exchange ActiveSync (EAS) management with an Exchange connector.</span></span> <span data-ttu-id="ab45e-106">Geräte können entweder mit lokalen Exchange-Servern oder mit Exchange Online unter Verwendung von Office 365 verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="ab45e-106">Devices can be managed with either on-premises Exchange servers or Exchange Online using Office 365.</span></span> <span data-ttu-id="ab45e-107">Intune unterstützt pro Abonnement nur eine Exchange Connector-Verbindung eines beliebigen Typs.</span><span class="sxs-lookup"><span data-stu-id="ab45e-107">Intune supports only one Exchange connector connection of any type per subscription.</span></span>

## <a name="exchange-access-rules-for-mobile-devices"></a><span data-ttu-id="ab45e-108">Exchange-Zugriffsregeln für mobile Geräte</span><span class="sxs-lookup"><span data-stu-id="ab45e-108">Exchange access rules for mobile devices</span></span> ##

<span data-ttu-id="ab45e-109">In Exchange muss über einen Satz von Regeln definiert werden, was geschieht, wenn mobile Geräte eine Verbindung mit EAS herzustellen versuchen.</span><span class="sxs-lookup"><span data-stu-id="ab45e-109">Exchange needs a set of rules that defines what happens when mobile devices attempt to connect to EAS.</span></span> <span data-ttu-id="ab45e-110">Diese Regeln werden in der Intune-Verwaltungskonsole verwaltet.</span><span class="sxs-lookup"><span data-stu-id="ab45e-110">These rules are managed in the Intune administration console.</span></span>

[<span data-ttu-id="ab45e-111">Exchange-Zugriffsregeln für mobile Geräte</span><span class="sxs-lookup"><span data-stu-id="ab45e-111">Exchange access rules for mobile devices</span></span>](exchange-access-rules-for-mobile-devices.md)

## <a name="install-the-exchange-connector"></a><span data-ttu-id="ab45e-112">Installieren des Exchange Connectors</span><span class="sxs-lookup"><span data-stu-id="ab45e-112">Install the Exchange connector</span></span>
<span data-ttu-id="ab45e-113">Mit dem Exchange Connector können Sie Ihre Exchange-Bereitstellung in der Intune-Konsole verwalten.</span><span class="sxs-lookup"><span data-stu-id="ab45e-113">The Exchange connector lets you manage your Exchange deployment in the Intune console.</span></span> <span data-ttu-id="ab45e-114">Zuerst müssen Sie den entsprechenden Intune-zu-Exchange-Connector installieren und einrichten.</span><span class="sxs-lookup"><span data-stu-id="ab45e-114">You must first install and set up the appropriate Intune-to-Exchange connector.</span></span> <span data-ttu-id="ab45e-115">Wählen Sie die entsprechende Option je nachdem aus, ob es sich um einen lokalen Exchange-Server handelt oder ob er als Dienst in der Cloud gehostet wird:</span><span class="sxs-lookup"><span data-stu-id="ab45e-115">Choose the appropriate option based on whether your Exchange server is on-premises or hosted as a service in the cloud:</span></span>

-   [<span data-ttu-id="ab45e-116">Konfigurieren von Intune für die Exchange Online-Umgebung oder für die neue Exchange Online Dedicated-Umgebung</span><span class="sxs-lookup"><span data-stu-id="ab45e-116">Configure the Intune for Exchange Online or new Exchange Online Dedicated environments</span></span>](intune-service-to-service-exchange-connector.md)
-   [<span data-ttu-id="ab45e-117">Installieren des Intune-Connectors für lokale Exchange-Server und ältere Exchange Online Dedicated-Umgebungen</span><span class="sxs-lookup"><span data-stu-id="ab45e-117">Install the Intune connector for on-premises Exchange servers and legacy Exchange Online Dedicated environments</span></span>](intune-on-premises-exchange-connector.md)


## <a name="apply-policy-for-exchange-managed-mobile-devices"></a><span data-ttu-id="ab45e-118">Anwenden der Richtlinie für mobile Geräte, die mit Exchange verwaltet werden</span><span class="sxs-lookup"><span data-stu-id="ab45e-118">Apply policy for Exchange-managed mobile devices</span></span>
<span data-ttu-id="ab45e-119">Die Intune-Konsole kann zum Verwalten von [EAS-Richtlinieneinstellungen](exchange-activesync-policy-settings-in-microsoft-intune.md) und zum [Beschränken des Zugriffs auf Unternehmensressourcen](restrict-access-to-email-and-o365-services-with-microsoft-intune.md) verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="ab45e-119">The Intune console can be used to manage [EAS policy settings](exchange-activesync-policy-settings-in-microsoft-intune.md) and to [restrict access to company resources](restrict-access-to-email-and-o365-services-with-microsoft-intune.md).</span></span> <span data-ttu-id="ab45e-120">Eine Liste der Exchange ActiveSync-Richtlinieneinstellungen und -Funktionen, die von bestimmten mobilen Geräten unterstützt werden, finden Sie unter [Exchange ActiveSync Client Comparison Table (Vergleichstabelle der Exchange ActiveSync-Clients)](http://go.microsoft.com/fwlink/?LinkId=247270).</span><span class="sxs-lookup"><span data-stu-id="ab45e-120">For a list of Exchange ActiveSync policy settings and features that specific mobile devices support, see [Exchange ActiveSync Client Comparison Table](http://go.microsoft.com/fwlink/?LinkId=247270).</span></span>

> [!NOTE]
> <span data-ttu-id="ab45e-121">Nach dem Herstellen einer Verbindung zwischen Intune und einer Microsoft Exchange-Umgebung wird bei allen Benutzern, die über Intune verwaltet werden, die EAS-Richtlinie auf die aktuelle Standardrichtlinie auf dem Microsoft Exchange-Server zurückgesetzt, wenn keine spezifische Richtlinie in Intune definiert ist.</span><span class="sxs-lookup"><span data-stu-id="ab45e-121">After connecting Intune to a Microsoft Exchange environment, the EAS policy for all users managed through Intune will be reset to the current default policy on the Microsoft Exchange server, unless a more specific policy is defined within Intune.</span></span>

## <a name="wipe-company-data-from-mobile-devices"></a><span data-ttu-id="ab45e-122">Löschen von Unternehmensdaten von mobilen Geräten</span><span class="sxs-lookup"><span data-stu-id="ab45e-122">Wipe company data from mobile devices</span></span>
<span data-ttu-id="ab45e-123">Sie können [Unternehmensdaten von mobilen Geräten, die über EAS verwaltet werden, löschen](wipe-for-exchange-managed-mobile-devices.md), wenn diese nicht mehr verwendet werden oder wenn Geräte verloren gehen oder gestohlen werden.</span><span class="sxs-lookup"><span data-stu-id="ab45e-123">Finally, you can [wipe company data from EAS-managed mobile devices](wipe-for-exchange-managed-mobile-devices.md) when they are no longer in use, or if devices are lost or stolen.</span></span>
