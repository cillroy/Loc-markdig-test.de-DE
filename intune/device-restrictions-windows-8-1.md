---
title: "Einstellungen für Geräteeinschränkungen für Windows 8.1 in Intune"
titleSuffix: Azure portal
description: "In diesem Artikel lernen Sie die Intune-Einstellungen zur Steuerung von Geräteeinstellungen und -funktionen auf Windows 8.1-Geräten kennen."
keywords: 
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 08/01/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: fe5785e9-8d35-4ad7-95e8-d50f8d87154a
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: 90bf12356ffccde5303c64a0675f046459d7dc82
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2018
---
# <a name="windows-81-and-later-device-restriction-settings-in-microsoft-intune"></a><span data-ttu-id="27a4f-103">Einstellungen für Geräteeinschränkungen für Windows 8.1 und höher in Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="27a4f-103">Windows 8.1 and later device restriction settings in Microsoft Intune</span></span>

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

## <a name="general"></a><span data-ttu-id="27a4f-104">Allgemein</span><span class="sxs-lookup"><span data-stu-id="27a4f-104">General</span></span>

-   <span data-ttu-id="27a4f-105">**Übermittlung von Diagnosedaten:** Ermöglicht dem Gerät die Übermittlung von Diagnoseinformationen an Microsoft.</span><span class="sxs-lookup"><span data-stu-id="27a4f-105">**Diagnostic data submission** - Enables the device to submit diagnostic information to Microsoft.</span></span>
-   <span data-ttu-id="27a4f-106">**Firewall:** Erfordert, dass die Windows-Firewall aktiviert sein muss.</span><span class="sxs-lookup"><span data-stu-id="27a4f-106">**Firewall** - Requires that the Windows Firewall is turned on.</span></span>
-   <span data-ttu-id="27a4f-107">**Benutzerkontensteuerung:** Erfordert, dass die Benutzerkontensteuerung (User Account Control, UAC) auf Geräten verwendet werden muss.</span><span class="sxs-lookup"><span data-stu-id="27a4f-107">**User Account Control** - Requires the use of User Account Control (UAC) on devices.</span></span>

## <a name="password"></a><span data-ttu-id="27a4f-108">Kennwort</span><span class="sxs-lookup"><span data-stu-id="27a4f-108">Password</span></span>
-   <span data-ttu-id="27a4f-109">**Erforderlicher Kennworttyp:** Der Endbenutzer muss ein Kennwort eingeben, um auf das Gerät zugreifen zu können.</span><span class="sxs-lookup"><span data-stu-id="27a4f-109">**Required password type** - Require the end user to enter a password to access the device.</span></span>
-   <span data-ttu-id="27a4f-110">**Minimale Kennwortlänge:** Konfiguriert die erforderliche Mindestlänge (in Zeichen) für das Kennwort.</span><span class="sxs-lookup"><span data-stu-id="27a4f-110">**Minimum password length** - Configures the minimum required length (in characters) for the password.</span></span>
-   <span data-ttu-id="27a4f-111">**Anzahl von Anmeldefehlern, bevor das Gerät zurückgesetzt wird:** Setzt das Gerät zurück, wenn diese Anzahl von Anmeldefehlern erreicht ist.</span><span class="sxs-lookup"><span data-stu-id="27a4f-111">**Number of sign-in failures before wiping device** - Wipes the device if the sign-in attempts fail this number of times.</span></span>
-   <span data-ttu-id="27a4f-112">**Maximaler Zeitraum der Inaktivität (in Minuten) bis zur Bildschirmsperrung:** Gibt die Anzahl von Minuten der Inaktivität an, bevor ein Kennwort zum Entsperren des Geräts erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="27a4f-112">**Maximum minutes of inactivity until screen locks** - Specifies the number of minutes a device must be idle before a password is required to unlock it.</span></span>
-   <span data-ttu-id="27a4f-113">**Kennwortablauf (Tage):** Gibt die Anzahl der Tage an, bevor das Gerätekennwort geändert werden muss.</span><span class="sxs-lookup"><span data-stu-id="27a4f-113">**Password expiration (days)** - Specifies the number of days before the device password must be changed.</span></span>
-   <span data-ttu-id="27a4f-114">**Wiederverwendung vorheriger Kennwörter verhindern:** Gibt an, ob der Benutzer zuvor verwendete Kennwörter konfigurieren kann.</span><span class="sxs-lookup"><span data-stu-id="27a4f-114">**Prevent reuse of previous passwords** - Specifies whether the user can configure previously used passwords.</span></span>
-   <span data-ttu-id="27a4f-115">**Bildcode und PIN:** Aktiviert die Verwendung eines Bildcodes und einer PIN.</span><span class="sxs-lookup"><span data-stu-id="27a4f-115">**Picture password and PIN** - Enables the use of a picture password and PIN.</span></span> <span data-ttu-id="27a4f-116">Mit einem Bildkennwort kann sich der Benutzer mit Gesten auf einem Bild anmelden.</span><span class="sxs-lookup"><span data-stu-id="27a4f-116">A picture password lets the user sign in with gestures on a picture.</span></span> <span data-ttu-id="27a4f-117">Mit einer PIN kann sich der Benutzer mit einem vierstelligen Code schnell anmelden.</span><span class="sxs-lookup"><span data-stu-id="27a4f-117">A PIN lets users quickly sign in with a four-digit code.</span></span>
-   <span data-ttu-id="27a4f-118">**Verschlüsselung:** Schreibt vor, dass die Dateien auf den Geräten verschlüsselt werden müssen.</span><span class="sxs-lookup"><span data-stu-id="27a4f-118">**Encryption** - Requires that files on the device are encrypted.</span></span><br><span data-ttu-id="27a4f-119">Um die Verschlüsselung auf Geräten zu erzwingen, die Windows 8.1 ausführen, installieren Sie das [MDM-Clientupdate für Windows von Dezember 2014](https://support.microsoft.com/kb/3013816) auf jedem Gerät.</span><span class="sxs-lookup"><span data-stu-id="27a4f-119">To enforce encryption on devices that run Windows 8.1, you must install the [December 2014 MDM client update for Windows](https://support.microsoft.com/kb/3013816) on each device.</span></span>
<span data-ttu-id="27a4f-120">Wenn Sie diese Einstellung für Windows 8.1-Geräte aktivieren, müssen alle Benutzer des Geräts ein Microsoft-Konto haben.</span><span class="sxs-lookup"><span data-stu-id="27a4f-120">If you enable this setting for Windows 8.1 devices, all users of the device must have a Microsoft account.</span></span>
<span data-ttu-id="27a4f-121">Damit die Verschlüsselung funktioniert, muss das Gerät die Hardwarezertifizierungsanforderungen für [Microsoft InstantGo](https://blogs.windows.com/windowsexperience/2014/06/19/instantgo-a-better-way-to-sleep/#IBHULcTfI4PokO8X.97) erfüllen.</span><span class="sxs-lookup"><span data-stu-id="27a4f-121">For encryption to work, the device must meet the [Microsoft InstantGo](https://blogs.windows.com/windowsexperience/2014/06/19/instantgo-a-better-way-to-sleep/#IBHULcTfI4PokO8X.97) hardware certification requirements.</span></span>
<span data-ttu-id="27a4f-122">Wenn Sie die Verschlüsselung auf einem Gerät erzwingen, ist der Wiederherstellungsschlüssel nur über das Microsoft-Konto des Benutzers zugänglich, auf das dieser über sein eigenes OneDrive-Konto zugreift.</span><span class="sxs-lookup"><span data-stu-id="27a4f-122">When you enforce encryption on a device, the recovery key is only accessible from the user's Microsoft account, which is accessed from their OneDrive account.</span></span> <span data-ttu-id="27a4f-123">Sie können diesen Schlüssel nicht im Auftrag eines Benutzers wiederherstellen.</span><span class="sxs-lookup"><span data-stu-id="27a4f-123">You cannot recover this key on behalf of a user.</span></span>     



## <a name="browser"></a><span data-ttu-id="27a4f-124">Browser</span><span class="sxs-lookup"><span data-stu-id="27a4f-124">Browser</span></span>
-   <span data-ttu-id="27a4f-125">**AutoAusfüllen:** Erlaubt Benutzern, die Einstellungen für AutoAusfüllen im Browser zu ändern.</span><span class="sxs-lookup"><span data-stu-id="27a4f-125">**Autofill** - Enables users to change autocomplete settings in the browser.</span></span>
-   <span data-ttu-id="27a4f-126">**Betrugswarnungen:** Aktiviert oder deaktiviert Warnungen zu potenziell betrügerischen Websites.</span><span class="sxs-lookup"><span data-stu-id="27a4f-126">**Fraud warnings** - Enables or disables warnings for potential fraudulent websites.</span></span>
-   <span data-ttu-id="27a4f-127">**SmartScreen:** Aktiviert oder deaktiviert Warnungen zu potenziell betrügerischen Websites.</span><span class="sxs-lookup"><span data-stu-id="27a4f-127">**SmartScreen** - Enables or disables warnings for potential fraudulent websites.</span></span>
-   <span data-ttu-id="27a4f-128">**Javascript:** Erlaubt dem Browser, Skripts auszuführen, z.B. Java-Skripts.</span><span class="sxs-lookup"><span data-stu-id="27a4f-128">**JavaScript** - Enables the browser to run scripts, such as Java script.</span></span>
-   <span data-ttu-id="27a4f-129">**Popups:** Aktiviert oder deaktiviert den Popupblocker des Browsers.</span><span class="sxs-lookup"><span data-stu-id="27a4f-129">**Pop-ups** - Enables or disables the browser pop-up blocker.</span></span>
-   <span data-ttu-id="27a4f-130">**DNT-Kopfzeilen senden:** Sendet einen DNT-Header (Do Not Track, nicht nachverfolgen) an besuchte Websites in Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="27a4f-130">**Send do-not-track headers** - Sends a do not track header to visited sites in Internet Explorer.</span></span>
-   <span data-ttu-id="27a4f-131">**Plug-Ins** Erlaubt Benutzern, Internet Explorer Plug-Ins hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="27a4f-131">**Plugins** - Enables users to add plug-ins to Internet Explorer.</span></span>
-   <span data-ttu-id="27a4f-132">**Eingabe eines einzelnen Worts auf Intranetsite zulassen:** Erlaubt die Verwendung eines einzelnen Worts, um Internet Explorer auf eine Website wie Bing weiterzuleiten.</span><span class="sxs-lookup"><span data-stu-id="27a4f-132">**Single word entry on intranet site** - Enables use of a single word to direct Internet Explorer to a web site, such as Bing.</span></span>
-   <span data-ttu-id="27a4f-133">**Automatische Erkennung von Intranetsite:** Hilft bei der Konfiguration der Sicherheit für Intranetsites in Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="27a4f-133">**Auto detect of intranet site** - Helps configure security for intranet sites in Internet Explorer.</span></span>
-   <span data-ttu-id="27a4f-134">**Internetsicherheitsebene:** Legt die Internet Explorer-Sicherheitsstufe für Websites im Internet fest.</span><span class="sxs-lookup"><span data-stu-id="27a4f-134">**Internet security level** - Sets the Internet Explorer security level for Internet sites.</span></span>
-   <span data-ttu-id="27a4f-135">**Intranetsicherheitsebene:** Legt die Internet Explorer-Sicherheitsstufe für Websites im Intranet fest.</span><span class="sxs-lookup"><span data-stu-id="27a4f-135">**Intranet security level** - Sets the Internet Explorer security level for intranet sites.</span></span>
-   <span data-ttu-id="27a4f-136">**Sicherheitsstufe für vertrauenswürdige Sites:** Konfiguriert die Sicherheitsstufe für die Zone vertrauenswürdiger Sites.</span><span class="sxs-lookup"><span data-stu-id="27a4f-136">**Trusted sites security level** - Configures the security level for the trusted sites zone.</span></span>
-   <span data-ttu-id="27a4f-137">**Hohe Sicherheit für eingeschränkte Sites:** Konfiguriert die Sicherheitsstufe für Zone eingeschränkter Sites.</span><span class="sxs-lookup"><span data-stu-id="27a4f-137">**High security for restricted sites** - Configures the security level for the restricted sites zone.</span></span>
-   <span data-ttu-id="27a4f-138">**Menüzugriff im Unternehmensmodus:** Ermöglicht Benutzern, auf die Menüoptionen für den Unternehmensmodus von Internet Explorer zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="27a4f-138">**Enterprise mode menu access** - Lets users access the Enterprise Mode menu options from Internet Explorer.</span></span>
<span data-ttu-id="27a4f-139">Wenn Sie diese Einstellung ausgewählt haben, können Sie auch einen **Speicherort des Protokollberichts** angeben. Dieser enthält eine URL zu einem Bericht, in dem Websites angezeigt werden, für die Benutzer Zugriff im Unternehmensmodus aktiviert haben.</span><span class="sxs-lookup"><span data-stu-id="27a4f-139">If you select this setting, you can also specify a **Logging report location**, which contains a URL to a report that shows websites for which users have turned on Enterprise Mode access.</span></span>
-   <span data-ttu-id="27a4f-140">**Speicherort der Websiteliste für den Unternehmensmodus:** Gibt den Speicherort der Liste der Websites an, die den Unternehmensmodus verwenden, wenn er aktiv ist.</span><span class="sxs-lookup"><span data-stu-id="27a4f-140">**Enterprise mode site list location** - Specifies the location of the list of websites that will use Enterprise Mode when it is active.</span></span>

## <a name="cellular"></a><span data-ttu-id="27a4f-141">Mobilfunk</span><span class="sxs-lookup"><span data-stu-id="27a4f-141">Cellular</span></span>
-   <span data-ttu-id="27a4f-142">**Datenroaming:** Erlaubt das Datenroaming, wenn das Gerät in einem Mobilfunknetz verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="27a4f-142">**Data roaming** - Enables data roaming when the device is on a cellular network.</span></span>

## <a name="cloud-and-storage"></a><span data-ttu-id="27a4f-143">Cloud und Speicher</span><span class="sxs-lookup"><span data-stu-id="27a4f-143">Cloud and Storage</span></span>
-   <span data-ttu-id="27a4f-144">**Arbeitsordner-URL:** Legt die URL des Arbeitsordners so fest, damit Dokumente auf verschiedenen Geräten synchronisiert werden können.</span><span class="sxs-lookup"><span data-stu-id="27a4f-144">**Work folders URL** - Sets the URL of the work folder to allow documents to be synchronized across devices.</span></span>
-   <span data-ttu-id="27a4f-145">**Zugriff auf Windows Mail-App ohne Microsoft-Konto:** Ermöglicht den Zugriff auf die Windows Mail-Anwendung ohne Microsoft-Konto.</span><span class="sxs-lookup"><span data-stu-id="27a4f-145">**Access to Windows Mail app without a Microsoft account** - Enables access to the Windows Mail application without a Microsoft account.</span></span>    
