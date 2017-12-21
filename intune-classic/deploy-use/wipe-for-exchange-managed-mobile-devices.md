---
title: "Zurücksetzen mobiler Geräte, die mit Exchange verwaltet werden"
description: "Mit Microsoft Intune können Sie mobile Geräte zurücksetzen, die mithilfe von Exchange ActiveSync (EAS) mit dem Intune Exchange Connector verwaltet werden."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 11/14/2016
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: e116b620-1e12-4b5c-9905-2f7acf2ae530
ROBOTS: NOINDEX,NOFOLLOW
ms.reviewer: lancecra
ms.suite: ems
ms.custom: intune-classic
ms.openlocfilehash: 00baa49411221ec520d03bb651b1b90d539e1bdc
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2017
---
# <a name="wipe-for-exchange-managed-mobile-devices"></a><span data-ttu-id="1b233-103">Wipe for Exchange-managed mobile devices</span><span class="sxs-lookup"><span data-stu-id="1b233-103">Wipe for Exchange-managed mobile devices</span></span>

[!INCLUDE[classic-portal](../includes/classic-portal.md)]

<span data-ttu-id="1b233-104">Mit Microsoft Intune können Sie mobile Geräte zurücksetzen, die mithilfe von Exchange ActiveSync (EAS) mit dem Intune Exchange Connector verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="1b233-104">Microsoft Intune allows you to wipe or reset mobile devices that are managed using Exchange ActiveSync (EAS) with the Intune Exchange Connector.</span></span> <span data-ttu-id="1b233-105">In der folgenden Tabelle werden die verfügbaren Funktionen zum Zurücksetzen über Exchange ActiveSync beschrieben:</span><span class="sxs-lookup"><span data-stu-id="1b233-105">The following table describes the wipe capabilities available through Exchange ActiveSync:</span></span>

|<span data-ttu-id="1b233-106">Typ des Zurücksetzens</span><span class="sxs-lookup"><span data-stu-id="1b233-106">Type of wipe</span></span>|<span data-ttu-id="1b233-107">Windows 8.1 und Windows RT 8.1</span><span class="sxs-lookup"><span data-stu-id="1b233-107">Windows 8.1 and Windows RT 8.1</span></span>|<span data-ttu-id="1b233-108">iOS</span><span class="sxs-lookup"><span data-stu-id="1b233-108">iOS</span></span>|<span data-ttu-id="1b233-109">Android</span><span class="sxs-lookup"><span data-stu-id="1b233-109">Android</span></span>|
|----------------|----------------------------------|--------------|-------------------|-------|-----------|
|<span data-ttu-id="1b233-110">Vollständiges Zurücksetzen</span><span class="sxs-lookup"><span data-stu-id="1b233-110">Full wipe</span></span>|<span data-ttu-id="1b233-111">E-Mail-Konto und zwischengespeicherte E-Mails werden entfernt.</span><span class="sxs-lookup"><span data-stu-id="1b233-111">Removes mail account and cached mail.</span></span>|<span data-ttu-id="1b233-112">Zurück auf XWerkseinstellungen.</span><span class="sxs-lookup"><span data-stu-id="1b233-112">XFactory reset.</span></span>|<span data-ttu-id="1b233-113">Zurück auf Werkseinstellungen</span><span class="sxs-lookup"><span data-stu-id="1b233-113">Factory reset.</span></span>|
|<span data-ttu-id="1b233-114">Selektives Zurücksetzen/E-Mail</span><span class="sxs-lookup"><span data-stu-id="1b233-114">Selective wipe/email</span></span>|<span data-ttu-id="1b233-115">E-Mail-Konto wird entfernt</span><span class="sxs-lookup"><span data-stu-id="1b233-115">Removes email account.</span></span>|<span data-ttu-id="1b233-116">Nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="1b233-116">Not supported.</span></span>|<span data-ttu-id="1b233-117">Nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="1b233-117">Not supported.</span></span>|
|<span data-ttu-id="1b233-118">Selektives Zurücksetzen/Richtlinien</span><span class="sxs-lookup"><span data-stu-id="1b233-118">Selective wipe/policies</span></span>|<span data-ttu-id="1b233-119">Die Durchsetzung von Richtlinien wird entfernt, es werden jedoch keine Einstellungen geändert.</span><span class="sxs-lookup"><span data-stu-id="1b233-119">Policy enforcement removed, but settings are not changed</span></span>|<span data-ttu-id="1b233-120">Die Durchsetzung von XRichtlinien wird entfernt, es werden jedoch keine Einstellungen geändert.</span><span class="sxs-lookup"><span data-stu-id="1b233-120">XPolicy enforcement removed, but settings are not changed.</span></span>|<span data-ttu-id="1b233-121">Die Durchsetzung von Richtlinien wird entfernt, es werden jedoch keine Einstellungen geändert.</span><span class="sxs-lookup"><span data-stu-id="1b233-121">Policy enforcement removed, but settings are not changed.</span></span>|
