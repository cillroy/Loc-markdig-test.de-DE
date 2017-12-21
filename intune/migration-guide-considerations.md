---
title: "Besondere Überlegungen bei der Migration"
description: "Dieser Artikel bietet spezielle Überlegungen bei der Migration, bevor Sie eine Migrationskampagne starten."
keywords: 
author: andredm7
ms.author: andredm
manager: angrobe
ms.date: 07/12/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: f29d2894-e98b-4f2c-b444-a8ccc1b7efdd
ms.reviewer: dagerrit
ms.suite: ems
ms.openlocfilehash: 7ff1180275fddc7f0d6ef957c4680d7c34ad471e
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2017
---
# <a name="special-migration-considerations"></a><span data-ttu-id="47f89-103">Besondere Überlegungen bei der Migration</span><span class="sxs-lookup"><span data-stu-id="47f89-103">Special migration considerations</span></span>

<span data-ttu-id="47f89-104">Es gibt spezielle Aspekte bei der Migration, die je nach vorhandener Umgebung des MDM-Anbieters zu berücksichtigen sind.</span><span class="sxs-lookup"><span data-stu-id="47f89-104">There are special migration considerations which may apply depending on your existing MDM provider environment.</span></span>

## <a name="factory-reset-for-apples-device-enrollment-program-dep"></a><span data-ttu-id="47f89-105">Apple Device Enrollment Programm (DEP) auf Werkseinstellungen zurücksetzen</span><span class="sxs-lookup"><span data-stu-id="47f89-105">Factory reset for Apple’s Device Enrollment Program (DEP)</span></span>

<span data-ttu-id="47f89-106">Das Apple-Programm zur Geräteregistrierung (Device Enrollment Program, DEP) legt Gerätekonfigurationen fest, die vom Endbenutzer nicht entfernt werden können.</span><span class="sxs-lookup"><span data-stu-id="47f89-106">The Apple Device Enrollment Program (DEP) sets device configurations that cannot be removed by the end user.</span></span> <span data-ttu-id="47f89-107">Wenn Sie die erweiterten Verwaltungsfunktionen von DEP beibehalten möchten, muss das Gerät für die Anmeldung bei Intune auf die Werkseinstellungen zurückgesetzt werden.</span><span class="sxs-lookup"><span data-stu-id="47f89-107">To retain the advanced management features of DEP, the device must be returned to the out-of-box (new) state by a factory reset to enroll it into Intune.</span></span>

<span data-ttu-id="47f89-108">Um die Geräte in Intune weiter mit dem Programm zur Geräteregistrierung zu verwalten, [richten Sie die iOS-Geräteregistrierung mit dem Programm zur Geräteregistrierung ein](device-enrollment-program-enroll-ios.md).</span><span class="sxs-lookup"><span data-stu-id="47f89-108">To continue using DEP to manage the devices in Intune, [set up iOS device enrollment with Device Enrollment Program](device-enrollment-program-enroll-ios.md).</span></span>


## <a name="next-steps"></a><span data-ttu-id="47f89-109">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="47f89-109">Next steps</span></span>

[<span data-ttu-id="47f89-110">Phase 2: Die Migration</span><span class="sxs-lookup"><span data-stu-id="47f89-110">Phase 2: Migration campaign</span></span>](migration-guide-campaign.md)
