---
title: Wo ist meine Intune-Funktion in Azure jetzt?
titlesuffix: Azure portal
description: Hilft Ihnen bei der Suche nach Intune-Funktionen im Azure-Portal.
keywords: 
author: dagerrit
ms.author: dagerrit
manager: angrobe
ms.date: 03/31/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 
ms.reviewer: dagerrit
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: d0c598cc641989c8771235c28bd82a7d692cb76c
ms.sourcegitcommit: e37e916e2bf14f092d3a767bc90d68c181d739fb
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/03/2018
---
# <a name="where-did-my-intune-feature-go-in-azure"></a><span data-ttu-id="a70b4-103">Wo ist meine Intune-Funktion in Azure jetzt?</span><span class="sxs-lookup"><span data-stu-id="a70b4-103">Where did my Intune feature go in Azure?</span></span>
<span data-ttu-id="a70b4-104">Wir hatten die Chance, einige Aufgaben logischer zu organisieren, als wir Intune in das Azure-Portal umgezogen haben.</span><span class="sxs-lookup"><span data-stu-id="a70b4-104">We took the opportunity to organize some tasks more logically as we moved Intune into the Azure portal.</span></span> <span data-ttu-id="a70b4-105">Jedoch kommt jede Verbesserung mit der neuen Aufgabe, die neue Organisation kennenzulernen.</span><span class="sxs-lookup"><span data-stu-id="a70b4-105">But every improvement comes with the cost of learning the new organization.</span></span> <span data-ttu-id="a70b4-106">Daher haben wir dieses Referenzhandbuch für diejenigen von Ihnen erstellt, die mit Intune im klassischen Portal bestens vertraut sind und sich nun fragen, wie Aufgaben in Intune im Azure-Portal erledigt werden.</span><span class="sxs-lookup"><span data-stu-id="a70b4-106">So, we created this reference guide for those of you who are thoroughly familiar with Intune in the classic portal and are wondering how to get something done in Intune in the Azure portal.</span></span> <span data-ttu-id="a70b4-107">Wenn dieser Artikel eine Funktion, die Sie suchen, nicht behandelt, hinterlassen Sie einen Kommentar am Ende des Artikels, damit wir ihn aktualisieren können.</span><span class="sxs-lookup"><span data-stu-id="a70b4-107">If this article doesn’t cover a feature you’re trying to find, please leave a comment at the end of the article so we can update it.</span></span>
## <a name="quick-reference-guide"></a><span data-ttu-id="a70b4-108">Handbuch mit Kurzübersicht</span><span class="sxs-lookup"><span data-stu-id="a70b4-108">Quick reference guide</span></span>

|<span data-ttu-id="a70b4-109">Komponente</span><span class="sxs-lookup"><span data-stu-id="a70b4-109">Feature</span></span> |<span data-ttu-id="a70b4-110">Pfad im klassischen Portal</span><span class="sxs-lookup"><span data-stu-id="a70b4-110">Path in classic portal</span></span>|<span data-ttu-id="a70b4-111">Pfad in Intune im Azure-Portal</span><span class="sxs-lookup"><span data-stu-id="a70b4-111">Path in Intune in the Azure portal</span></span>|
|------------|---------------|---------------|
|<span data-ttu-id="a70b4-112">Programm zur Geräteregistrierung (DEP) [nur iOS9]</span><span class="sxs-lookup"><span data-stu-id="a70b4-112">Device Enrollment Program (DEP) [iOS only]</span></span>|<span data-ttu-id="a70b4-113">Administrator > Verwaltung mobiler Geräte > iOS > Programm zur Geräteregistrierung</span><span class="sxs-lookup"><span data-stu-id="a70b4-113">Admin > Mobile Device Management > iOS > Device Enrollment Program</span></span>|[<span data-ttu-id="a70b4-114">Geräteregistrierung > Apple-Registrierung > Registrierungsprogrammtoken</span><span class="sxs-lookup"><span data-stu-id="a70b4-114">Device enrollment > Apple Enrollment > Enrollment Program Token</span></span>](#where-did-apple-dep-go) |
|<span data-ttu-id="a70b4-115">Programm zur Geräteregistrierung (DEP) [nur iOS9]</span><span class="sxs-lookup"><span data-stu-id="a70b4-115">Device Enrollment Program (DEP) [iOS only]</span></span>| <span data-ttu-id="a70b4-116">Administrator > Verwaltung mobiler Geräte > iOS und Mac OS X > Programm zur Geräteregistrierung</span><span class="sxs-lookup"><span data-stu-id="a70b4-116">Admin > Mobile Device Management > iOS and Mac OS X > Device Enrollment Program</span></span> |[<span data-ttu-id="a70b4-117">Geräteregistrierung > Apple-Registrierung > Seriennummern des Registrierungsprogramms</span><span class="sxs-lookup"><span data-stu-id="a70b4-117">Device enrollment > Apple Enrollment > Enrollment Program Serial Numbers</span></span>](#where-did-apple-dep-go) |
|<span data-ttu-id="a70b4-118">Registrierungsregeln</span><span class="sxs-lookup"><span data-stu-id="a70b4-118">Enrollment Rules</span></span> |<span data-ttu-id="a70b4-119">Administrator > Verwaltung mobiler Geräte > Registrierungsregeln</span><span class="sxs-lookup"><span data-stu-id="a70b4-119">Admin > Mobile Device Management > Enrollment Rules</span></span>|[<span data-ttu-id="a70b4-120">Geräteregistrierung > Registrierungseinschränkungen</span><span class="sxs-lookup"><span data-stu-id="a70b4-120">Device enrollment > Enrollment Restrictions</span></span>](#where-did-enrollment-rules-go) |
|<span data-ttu-id="a70b4-121">Gruppen nach iOS-Seriennummer</span><span class="sxs-lookup"><span data-stu-id="a70b4-121">Groups by iOS Serial Number</span></span> |<span data-ttu-id="a70b4-122">Gruppen > Alle Geräte > Vorabregistrierte Unternehmensgeräte > Nach iOS-Seriennummer</span><span class="sxs-lookup"><span data-stu-id="a70b4-122">Groups > All Devices > Corporate Pre-enrolled devices > By iOS Serial Number</span></span>|[<span data-ttu-id="a70b4-123">Geräteregistrierung > Apple-Registrierung > Seriennummern des Registrierungsprogramms</span><span class="sxs-lookup"><span data-stu-id="a70b4-123">Device enrollment > Apple Enrollment > Enrollment Program Serial Numbers</span></span>](#where-did-corporate-pre-enrolled-devices-go) |
|<span data-ttu-id="a70b4-124">Gruppen nach iOS-Seriennummer</span><span class="sxs-lookup"><span data-stu-id="a70b4-124">Groups by iOS Serial Number</span></span> |<span data-ttu-id="a70b4-125">Gruppen > Alle Geräte > Vorabregistrierte Unternehmensgeräte > Nach iOS-Seriennummer</span><span class="sxs-lookup"><span data-stu-id="a70b4-125">Groups > All Devices > Corporate Pre-enrolled devices > By iOS Serial Number</span></span>| [<span data-ttu-id="a70b4-126">Geräteregistrierung > Apple-Registrierung > AC-Seriennummern</span><span class="sxs-lookup"><span data-stu-id="a70b4-126">Device enrollment > Apple Enrollment > AC Serial numbers</span></span>](#where-did-corporate-pre-enrolled-devices-go)|
|<span data-ttu-id="a70b4-127">Gruppen nach IMEI (Alle Plattformen)</span><span class="sxs-lookup"><span data-stu-id="a70b4-127">Groups by IMEI (all platforms)</span></span>| <span data-ttu-id="a70b4-128">Gruppen > Alle Geräte > Vorabregistrierte Unternehmensgeräte > Nach IMEI (Alle Plattformen)</span><span class="sxs-lookup"><span data-stu-id="a70b4-128">Groups > All Devices > Corporate Pre-enrolled devices > By IMEI (All platforms)</span></span> | [<span data-ttu-id="a70b4-129">Geräteregistrierung > Bezeichner von Unternehmensgeräten</span><span class="sxs-lookup"><span data-stu-id="a70b4-129">Device enrollment > Corporate Device Identifiers</span></span>](#by-imei-all-platforms)|
| <span data-ttu-id="a70b4-130">Profil für die Unternehmensgeräteregistrierung</span><span class="sxs-lookup"><span data-stu-id="a70b4-130">Corporate Device Enrollment profile</span></span>| <span data-ttu-id="a70b4-131">Richtlinie > Unternehmensgeräteregistrierung</span><span class="sxs-lookup"><span data-stu-id="a70b4-131">Policy > Corporate Device Enrollment</span></span> | [<span data-ttu-id="a70b4-132">Geräteregistrierung > Apple-Registrierung > Profile des Registrierungsprogramms</span><span class="sxs-lookup"><span data-stu-id="a70b4-132">Device enrollment > Apple Enrollment > Enrollment Program Profiles</span></span>](#where-did-corporate-pre-enrolled-devices-go) |
| <span data-ttu-id="a70b4-133">Profil für die Unternehmensgeräteregistrierung</span><span class="sxs-lookup"><span data-stu-id="a70b4-133">Corporate Device Enrollment profile</span></span> | <span data-ttu-id="a70b4-134">Richtlinie > Unternehmensgeräteregistrierung</span><span class="sxs-lookup"><span data-stu-id="a70b4-134">Policy > Corporate Device Enrollment</span></span> | [<span data-ttu-id="a70b4-135">Geräteregistrierung > Apple-Registrierung > AC-Profile</span><span class="sxs-lookup"><span data-stu-id="a70b4-135">Device enrollment > Apple Enrollment > AC Profiles</span></span>](#where-did-corporate-pre-enrolled-devices-go) |
| <span data-ttu-id="a70b4-136">Android for Work</span><span class="sxs-lookup"><span data-stu-id="a70b4-136">Android for Work</span></span> | <span data-ttu-id="a70b4-137">Administrator > Verwaltung mobiler Geräte > Android for Work</span><span class="sxs-lookup"><span data-stu-id="a70b4-137">Admin > Mobile Device Management > Android for Work</span></span> | <span data-ttu-id="a70b4-138">Geräteregistrierung > Android for Work-Registrierung</span><span class="sxs-lookup"><span data-stu-id="a70b4-138">Device enrollment > Android for Work Enrollment</span></span> |
| <span data-ttu-id="a70b4-139">Geschäftsbedingungen</span><span class="sxs-lookup"><span data-stu-id="a70b4-139">Terms and Conditions</span></span> | <span data-ttu-id="a70b4-140">Richtlinien > Geschäftsbedingungen</span><span class="sxs-lookup"><span data-stu-id="a70b4-140">Policy > Terms and Conditions</span></span> | <span data-ttu-id="a70b4-141">Geräteregistrierung > Geschäftsbedingungen</span><span class="sxs-lookup"><span data-stu-id="a70b4-141">Device enrollment > Terms and Conditions</span></span> |


## <a name="where-do-i-manage-groups"></a><span data-ttu-id="a70b4-142">Wo verwalte ich Gruppen?</span><span class="sxs-lookup"><span data-stu-id="a70b4-142">Where do I manage groups?</span></span>
<span data-ttu-id="a70b4-143">Intune im Azure-Portal verwendet [Azure Active Directory (AD)](https://docs.microsoft.com/azure/active-directory/active-directory-groups-create-azure-portal) zum Verwalten von Gruppen.</span><span class="sxs-lookup"><span data-stu-id="a70b4-143">Intune in the Azure portal uses [Azure Active Directory (AD)](https://docs.microsoft.com/azure/active-directory/active-directory-groups-create-azure-portal) to manage groups.</span></span>

## <a name="where-did-enrollment-rules-go"></a><span data-ttu-id="a70b4-144">Wo sind die Registrierungsregeln hin?</span><span class="sxs-lookup"><span data-stu-id="a70b4-144">Where did enrollment rules go?</span></span>
<span data-ttu-id="a70b4-145">Im klassischen Portal konnten Sie Regeln festlegen, die die MDM-Registrierung mobiler und moderner Windows- und macOS-Geräte gesteuert haben:</span><span class="sxs-lookup"><span data-stu-id="a70b4-145">In the classic portal, you could set rules governing the MDM enrollment of mobile and modern Windows and macOS devices:</span></span>

![Abbildung der klassischen Registrierungsregeln für mobile Geräte](./media/01-classic-rules.png)

<span data-ttu-id="a70b4-147">Diese Regeln galten ausnahmslos für alle Benutzer in Ihrem Intune-Konto.</span><span class="sxs-lookup"><span data-stu-id="a70b4-147">These rules applied to all users in your Intune account without exception.</span></span> <span data-ttu-id="a70b4-148">Im Azure-Portal werden diese Regeln nun in zwei unterschiedlichen Typen von Richtlinien dargestellt: Gerätetypbeschränkungen und Einschränkungen zum Gerätelimit:</span><span class="sxs-lookup"><span data-stu-id="a70b4-148">In the Azure portal these rules now appear in two distinct polices types: Device Type Restrictions and Device Limit Restrictions:</span></span>

![Abbildung der Registrierungseinschränkungen für mobile Azure-Geräte](./media/02-azure-enroll-restrictions.png)

<span data-ttu-id="a70b4-150">Die Standardeinschränkung zum Gerätelimit entspricht dem Grenzwert für die Geräteregistrierung im klassischen Portal:</span><span class="sxs-lookup"><span data-stu-id="a70b4-150">The default Device Limit Restriction corresponds to the Device Enrollment Limit in the classic portal:</span></span>

![Abbildung der Einschränkungen zum Gerätelimit für Azure](./media/03-azure-device-limit.png)

<span data-ttu-id="a70b4-152">Die Standardeinschränkung des Gerätetyps entspricht den Plattformeinschränkungen im klassischen Portal:</span><span class="sxs-lookup"><span data-stu-id="a70b4-152">The default Device Type Restriction corresponds to the Platform Restrictions in the classic portal:</span></span>

![Abbildung von Gerätetypeinschränkungen für Azure](./media/04-azure-platform-restrictions.png)

<span data-ttu-id="a70b4-154">Die Möglichkeit, persönliche Geräte zuzulassen oder zu blockieren, wird nun unter den Plattformkonfigurationen der Gerätetypeinschränkungen verwaltet:</span><span class="sxs-lookup"><span data-stu-id="a70b4-154">The ability to allow or block personally owned devices is now managed under the Device Type Restriction’s Platform Configurations:</span></span>

![Abbildung der Blockiereinstellungen von persönlichen Azure-Geräten](./media/05-azure-personal-block.png)

<span data-ttu-id="a70b4-156">Neue Funktionen zur Einschränkung werden nur zum Azure-Portal hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="a70b4-156">New restriction capabilities will be added to the Azure Portal only.</span></span>

## <a name="where-did-apple-dep-go"></a><span data-ttu-id="a70b4-157">Wo ist Apple-DEP jetzt?</span><span class="sxs-lookup"><span data-stu-id="a70b4-157">Where did Apple DEP go?</span></span>
<span data-ttu-id="a70b4-158">Im klassischen Portal konnten Sie Intune so einrichten, dass es im Programm zur Geräteregistrierung von Apple integriert wurde, und Sie konnten die Synchronisierung mit dem Apple-Dienst manuell anfordern:</span><span class="sxs-lookup"><span data-stu-id="a70b4-158">In the classic portal, you could set up Intune to integrate with Apple’s Device Enrollment Program and manually request synchronization with Apple’s service:</span></span>

![Bild des klassischen DEP-Token](./media/06-classic-dep-token.png)

<span data-ttu-id="a70b4-160">Im Azure-Portal richten das Geräteregistrierungsprogramm von Apple mit den gleichen Schritten wie in der klassischen Intune-Konsole ein:</span><span class="sxs-lookup"><span data-stu-id="a70b4-160">In the Azure portal, you set up Apple Device Enrollment Program with the same steps as in Intune classic:</span></span>

![Abbildung des Azure-DEP-Token](./media/07-azure-dep-token.png)

<span data-ttu-id="a70b4-162">Jedoch wurde die Option **Synchronisierung** im klassischen Portal zum Workflow der Verwaltung von Seriennummern verschoben, da die Ergebnisse der manuellen Synchronisierung dort erscheinen werden:</span><span class="sxs-lookup"><span data-stu-id="a70b4-162">However the **Sync** option in the classic portal has been moved to the serial number management workflow since the results of a manual sync will appear there:</span></span>

![Abbildung der Azure-DEP-Synchronisation](./media/08-azure-dep-sync.png)

## <a name="where-did-corporate-pre-enrolled-devices-go"></a><span data-ttu-id="a70b4-164">Wo sind die vorabregistrierten Unternehmensgeräte jetzt?</span><span class="sxs-lookup"><span data-stu-id="a70b4-164">Where did corporate pre-enrolled devices go?</span></span>
### <a name="by-ios-serial-number"></a><span data-ttu-id="a70b4-165">Nach iOS-Seriennummer</span><span class="sxs-lookup"><span data-stu-id="a70b4-165">By iOS serial number</span></span>
<span data-ttu-id="a70b4-166">Im klassischen Portal können Sie iOS-Geräte über das Programm zur Geräteregistrierung von Apple (Device Enrollment Program, DEP) und das Apple Configurator-Tool registrieren.</span><span class="sxs-lookup"><span data-stu-id="a70b4-166">In the classic portal, you can enroll iOS devices through the Apple Device Enrollment Program (DEP) and the Apple Configurator tool.</span></span> <span data-ttu-id="a70b4-167">Beide Methoden bieten Gerätevorabregistrierung durch Seriennummern und umfassen die Zuweisung spezieller Geräteregistrierungsprofile.</span><span class="sxs-lookup"><span data-stu-id="a70b4-167">Both methods offer device pre-enrollment by serial number and involve the assignment of special Corporate Device Enrollment profiles.</span></span> <span data-ttu-id="a70b4-168">Vor der Registrierung kann die Registrierungsprofilzuweisung über die Gerätegruppe **Corporate Pre-enrolled Device by iOS Serial Number** (Vorabregistriertes Unternehmensgerät nach iOS-Seriennummer) verwaltet werden:</span><span class="sxs-lookup"><span data-stu-id="a70b4-168">Prior to enrollment, the enrollment profile assignment can be managed through the **Corporate Pre-enrolled Device by iOS Serial Number** device group:</span></span>

![Abbildung der klassischen Apple-Seriennummern](./media/09-classic-apple-serials.png)

<span data-ttu-id="a70b4-170">Hier werden Seriennummern für die Apple-DEP- und die Configurator-Registrierung in einer einzigen Liste aufgeführt:</span><span class="sxs-lookup"><span data-stu-id="a70b4-170">This lists serial numbers for both Apple DEP and Configurator enrollment in a single list.</span></span> <span data-ttu-id="a70b4-171">Um Profilzuweisungskonflikte zu reduzieren (DEP-Profile zu AC-Seriennummern und andersherum), haben wir die Seriennummern in zwei Listen im Azure-Portal aufgeteilt:</span><span class="sxs-lookup"><span data-stu-id="a70b4-171">To reduce profile assignment mis-match (DEP profile to AC serial number and vice-versa), we have separated the serial numbers into two lists in the Azure portal:</span></span>

<span data-ttu-id="a70b4-172">**DEP-Seriennummern**
![Abbildung von Azure DEP-Seriennummern](./media/10-azure-dep-serials.png)</span><span class="sxs-lookup"><span data-stu-id="a70b4-172">**DEP serial numbers**
![Image of Azure DEP serial numbers](./media/10-azure-dep-serials.png)</span></span>

<span data-ttu-id="a70b4-173">**Apple Configurator-Seriennummern**
![Abbildung der Azure Apple Configurator-Seriennummern](./media/11-azure-ac-serials.png)</span><span class="sxs-lookup"><span data-stu-id="a70b4-173">**Apple Configurator serial numbers**
![Image of Azure Apple Configurator serial numbers](./media/11-azure-ac-serials.png)</span></span>

### <a name="by-imei-all-platforms"></a><span data-ttu-id="a70b4-174">Durch IMEI (Alle Plattformen)</span><span class="sxs-lookup"><span data-stu-id="a70b4-174">By IMEI (all platforms)</span></span>

<span data-ttu-id="a70b4-175">Im klassischen Portal können Sie vorab IMEI-Nummern von Geräten auflisten, um sie als unternehmenseigen zu markieren, wenn sie in Intune registriert werden:</span><span class="sxs-lookup"><span data-stu-id="a70b4-175">In the classic portal, you can pre-list the IMEI numbers of devices to mark them as corporate when they enrolled to Intune:</span></span>

![Abbildung der klassischen Liste von IMEI-Nummern](./media/12-classic-corp-imei.png)

<span data-ttu-id="a70b4-177">Im Azure-Portal müssen Sie die gleichen IMEI-Nummern mit einer CSV-Datei, die durch Trennzeichen getrennte Werte enthält, in die Liste der IDs unternehmenseigener Geräte hochladen.</span><span class="sxs-lookup"><span data-stu-id="a70b4-177">In the Azure portal, you must upload the same IMEI to the Corporate Device Identifiers list with a comma-separated-values (CSV) file.</span></span> <span data-ttu-id="a70b4-178">Das neue Portal unterstützt keine manuelle Eingabe der IMEI-Nummern:</span><span class="sxs-lookup"><span data-stu-id="a70b4-178">The new portal will not support manual entry of IMEI numbers:</span></span>

![Abbildung der Azure-Liste der IMEI-Nummern](./media/13-azure-corp-imei.png)

<span data-ttu-id="a70b4-180">Intune im Azure-Portal wird zukünftig andere Typen von Bezeichnern neben IMEI unterstützen, lässt derzeit jedoch nur IMEI-Nummern für die Vorabauflistung zu.</span><span class="sxs-lookup"><span data-stu-id="a70b4-180">Intune in the Azure portal is future-proofed to support other types of identifiers beside IMEI, but currently only allows IMEI numbers for pre-listing.</span></span>

## <a name="where-did-corporate-device-enrollment-profiles-go"></a><span data-ttu-id="a70b4-181">Wo befinden sich die Profile für die Unternehmensgeräteregistrierung jetzt?</span><span class="sxs-lookup"><span data-stu-id="a70b4-181">Where did Corporate Device Enrollment profiles go?</span></span>
<span data-ttu-id="a70b4-182">Zum Registrieren von iOS-Geräten über das Apple-Geräteregistrierungsprogramm oder mit dem Apple Configurator-Tool müssen Sie ein Tool zur Unternehmensgeräteregistrierung bereitstellen, dem das Gerät zugewiesen wird.</span><span class="sxs-lookup"><span data-stu-id="a70b4-182">To enroll iOS devices through the Apple Device Enrollment Program or with the Apple Configurator tool, you must supply a Corporate Device Enrollment profile to be assigned the device.</span></span> <span data-ttu-id="a70b4-183">Im klassischen Portal fanden Erstellung und Verwaltung dieser Profile in einer einzigen Liste statt:</span><span class="sxs-lookup"><span data-stu-id="a70b4-183">In the classic portal, the creation and management of these profiles was located in a single list:</span></span>

![Abbildung der klassischen Geräteregistrierungsprofile](./media/14-classic-corp-profiles.png)

<span data-ttu-id="a70b4-185">Dieses Liste zeigt die Profile, die für den Gebrauch mit dem Apple-Geräteregistrierungsprogramm (**DEP On** (DEP aktiviert)) und Profile, die nur für den Gebrauch mit dem Apple Configurator Tool zulässig sind (**DEP Off** (DEP deaktiviert)).</span><span class="sxs-lookup"><span data-stu-id="a70b4-185">This list shows profiles enabled for use with the Apple Device Enrollment Program (**DEP On**) and profile only enabled for use with the Apple Configurator tool (**DEP Off**).</span></span>

<span data-ttu-id="a70b4-186">Um Verwechslungen zwischen den beiden Profiltypen und potenzielle nicht übereinstimmende Zuweisungen zu minimieren (DEP-Profil zu Configurator-Geräte und andersherum), haben wir die Erstellung und Verwaltung der Profile für das Registrierungsprogramm (die jeweils das Apple-Geräteregistrierungsprogramm und Apple School Manager unterstützen) sowie Apple Configurator-Profile getrennt:</span><span class="sxs-lookup"><span data-stu-id="a70b4-186">To reduce confusion between the two profile types and potential mis-matched assignments (DEP profile to Configurator devices and vice-versa), we have separated creation and management of Enrollment Program profiles (support both Apples Device Enrollment Program and Apple School Manager) and Apple Configurator profiles:</span></span>

<span data-ttu-id="a70b4-187">**DEP-Profile**
![Abbildung von Azure DEP-Profilen](./media/15-azure-dep-profiles.png)</span><span class="sxs-lookup"><span data-stu-id="a70b4-187">**DEP profiles**
![Image of Azure DEP profiles](./media/15-azure-dep-profiles.png)</span></span>

<span data-ttu-id="a70b4-188">**Apple Configurator-Profile**
![Abbildung der Azure Apple Configurator-Profile](./media/16-azure-ac-profiles.png)</span><span class="sxs-lookup"><span data-stu-id="a70b4-188">**Apple Configurator profiles**
![Image of Azure Apple Configurator profiles](./media/16-azure-ac-profiles.png)</span></span>
