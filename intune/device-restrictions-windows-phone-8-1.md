---
title: "Einstellungen für Geräteeinschränkungen für Windows Phone 8.1 in Intune"
titleSuffix: Azure portal
description: "In diesem Artikel lernen Sie die Intune-Einstellungen zur Steuerung von Geräteeinstellungen und -funktionen auf Windows Phone 8.1-Geräten kennen."
keywords: 
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 08/01/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: c2d42714-49ca-43b3-b080-2e67a4268198
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: bc0ff540bfacf16119cb5727458b42c0a7269c3a
ms.sourcegitcommit: a9d734877340894637e03f4b4ef83f7d01ddedc8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2017
---
# <a name="windows-phone-81-device-restriction-settings-in-microsoft-intune"></a><span data-ttu-id="ce385-103">Einstellungen für Geräteeinschränkungen für Windows Phone 8.1 in Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="ce385-103">Windows Phone 8.1 device restriction settings in Microsoft Intune</span></span>

[!INCLUDE[azure_portal](./includes/azure_portal.md)]

## <a name="general"></a><span data-ttu-id="ce385-104">Allgemein</span><span class="sxs-lookup"><span data-stu-id="ce385-104">General</span></span>

-   <span data-ttu-id="ce385-105">**Kamera:** Erlaubt oder sperrt die Verwendung der Kamera des Geräts.</span><span class="sxs-lookup"><span data-stu-id="ce385-105">**Camera** - Enables or blocks the device's camera.</span></span>
-   <span data-ttu-id="ce385-106">**Kopieren und einfügen:** Lässt Kopier- und Einfügefunktionen auf Geräten zu oder sperrt diese Funktionen.</span><span class="sxs-lookup"><span data-stu-id="ce385-106">**Copy and paste** - Enables or blocks copy and paste functionality on devices.</span></span>
-   <span data-ttu-id="ce385-107">**Wechselmedien:** Erlaubt dem Gerät, Wechselmedien wie SD-Karten zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="ce385-107">**Removable storage** - Lets the device use removable storage such as SD cards.</span></span>
-   <span data-ttu-id="ce385-108">**Geolocation:** Erlaubt dem Gerät die Nutzung von Standortinformationen.</span><span class="sxs-lookup"><span data-stu-id="ce385-108">**Geolocation** - Enables the device to utilize location information.</span></span>
-   <span data-ttu-id="ce385-109">**Microsoft-Konto:** Erlaubt oder sperrt das Verknüpfen des Geräts mit einem Microsoft-Konto durch den Benutzer.</span><span class="sxs-lookup"><span data-stu-id="ce385-109">**Microsoft account** - Enable or block the user from linking a Microsoft account to the device.</span></span>
-   <span data-ttu-id="ce385-110">**Bildschirmaufnahme:** Erlaubt dem Benutzer, den Bildschirminhalt als Bilddatei zu erfassen.</span><span class="sxs-lookup"><span data-stu-id="ce385-110">**Screen capture** - Lets the user capture the contents of the screen as an image file.</span></span>
-   <span data-ttu-id="ce385-111">**Übermittlung von Diagnosedaten:** Ermöglicht dem Gerät die Übermittlung von Diagnoseinformationen an Microsoft.</span><span class="sxs-lookup"><span data-stu-id="ce385-111">**Diagnostic data submission** - Enables the device to submit diagnostic information to Microsoft.</span></span>
-   <span data-ttu-id="ce385-112">**Synchronisierung benutzerdefinierter E-Mail-Konten:** Ermöglicht dem Gerät das Herstellen einer Verbindung mit nicht von Microsoft stammenden E-Mail-Konten.</span><span class="sxs-lookup"><span data-stu-id="ce385-112">**Custom email accounts sync** - Enables the device to connect to non-Microsoft email accounts.</span></span>

## <a name="password"></a><span data-ttu-id="ce385-113">Kennwort</span><span class="sxs-lookup"><span data-stu-id="ce385-113">Password</span></span>

-   <span data-ttu-id="ce385-114">**Kennwort:** Der Endbenutzer muss ein Kennwort eingeben, um auf das Gerät zugreifen zu können.</span><span class="sxs-lookup"><span data-stu-id="ce385-114">**Password** - Require the end user to enter a password to access the device.</span></span>
    -   <span data-ttu-id="ce385-115">**Erforderlicher Kennworttyp:** Gibt den erforderlichen Typ des Kennworts an, z.B. alphanumerisch oder nur numerisch.</span><span class="sxs-lookup"><span data-stu-id="ce385-115">**Required password type** - Specifies the type of password that will be required, such as alphanumeric or numeric only.</span></span>
    -   <span data-ttu-id="ce385-116">**Minimale Kennwortlänge:** Gibt die Mindestanzahl von Zeichen an, die das Kennwort enthalten muss.</span><span class="sxs-lookup"><span data-stu-id="ce385-116">**Minimum password length** - Specifies the minimum number of characters that are required in the password.</span></span>
    -   <span data-ttu-id="ce385-117">**Einfache Kennwörter:** Gibt an, dass einfache Kennwörter, wie z.B: „0000“ und „1234“ verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="ce385-117">**Simple passwords** - Specifies that simple passwords such as ‘0000’ and ‘1234’ can be used.</span></span>
    -   <span data-ttu-id="ce385-118">**Anzahl von Anmeldefehlern, bevor das Gerät zurückgesetzt wird:** Gibt an, wie häufig ein falsches Kennwort eingegeben werden kann, bevor das Gerät zurückgesetzt wird.</span><span class="sxs-lookup"><span data-stu-id="ce385-118">**Number of sign-in failures before wiping device** - Specifies the number of times an incorrect password can be entered before the device is wiped.</span></span>
    -   <span data-ttu-id="ce385-119">**Maximaler Zeitraum der Inaktivität (in Minuten) bis zur Bildschirmsperrung:** Gibt die Zeitdauer der Inaktivität für ein Gerät an, bevor der Bildschirm automatisch gesperrt wird.</span><span class="sxs-lookup"><span data-stu-id="ce385-119">**Maximum minutes of inactivity until screen locks** - Specifies the amount of time a device must remain idle before the screen is automatically locked.</span></span>
    -   <span data-ttu-id="ce385-120">**Kennwortablauf (Tage):** Gibt die Anzahl der Tage an, bevor das Gerätekennwort geändert werden muss.</span><span class="sxs-lookup"><span data-stu-id="ce385-120">**Password expiration (days)** - Specifies the number of days before the device password must be changed.</span></span>
    -   <span data-ttu-id="ce385-121">**Wiederverwendung vorheriger Kennwörter verhindern:** Gibt an, wie viele zuvor verwendete Kennwörter gespeichert werden.</span><span class="sxs-lookup"><span data-stu-id="ce385-121">**Prevent reuse of previous passwords** - Specifies how many previously used passwords are remembered.</span></span>
-   <span data-ttu-id="ce385-122">**Verschlüsselung:** Schreibt vor, dass die Daten auf unterstützten mobilen Geräten verschlüsselt werden müssen.</span><span class="sxs-lookup"><span data-stu-id="ce385-122">**Encryption** - Requires that the data on supported mobile devices be encrypted.</span></span>

## <a name="app-store"></a><span data-ttu-id="ce385-123">App Store</span><span class="sxs-lookup"><span data-stu-id="ce385-123">App Store</span></span>

-   <span data-ttu-id="ce385-124">**App-Store:** Erlaubt Benutzern, über das Gerät eine Verbindung mit dem App Store herzustellen.</span><span class="sxs-lookup"><span data-stu-id="ce385-124">**App store** - Lets users connect to the app store from the device.</span></span>

## <a name="restricted-apps"></a><span data-ttu-id="ce385-125">Eingeschränkte Apps</span><span class="sxs-lookup"><span data-stu-id="ce385-125">Restricted apps</span></span>

<span data-ttu-id="ce385-126">In der Liste der eingeschränkten Apps können Sie eine der folgenden Listen konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="ce385-126">In the restricted apps list, you can configure one of the following lists:</span></span>

<span data-ttu-id="ce385-127">**Blockierte Apps:** Listet die (nicht von Intune verwalteten) Apps auf, die Benutzer nicht installieren und ausführen dürfen.</span><span class="sxs-lookup"><span data-stu-id="ce385-127">A **Blocked apps** list - List the apps (not managed by Intune) that users are not allowed to install and run.</span></span>
<span data-ttu-id="ce385-128">**Zulässige Apps:** Listet die Apps auf, die Benutzer installieren dürfen.</span><span class="sxs-lookup"><span data-stu-id="ce385-128">An **Allowed apps** list - List the apps that users are allowed to install.</span></span> <span data-ttu-id="ce385-129">Apps, die von Intune verwaltet werden, sind automatisch zugelassen.</span><span class="sxs-lookup"><span data-stu-id="ce385-129">Apps that are managed by Intune are automatically allowed.</span></span>

<span data-ttu-id="ce385-130">Klicken Sie zum Konfigurieren einer Liste auf **Hinzufügen**. Geben Sie einen Namen Ihrer Wahl sowie die URL zur App im App-Store und optional den Herausgeber der App an.</span><span class="sxs-lookup"><span data-stu-id="ce385-130">To configure the list, click **Add**, then specify a name of your choice, optionally the app publisher, and the URL to the app in the app store.</span></span>

### <a name="how-to-specify-the-url-to-an-app-in-the-store"></a><span data-ttu-id="ce385-131">Angeben der URL zu einer App im Store</span><span class="sxs-lookup"><span data-stu-id="ce385-131">How to specify the URL to an app in the store</span></span>

<span data-ttu-id="ce385-132">Verwenden Sie das folgende Format, um eine App-URL in der Liste zulässiger und blockierter Apps anzugeben:</span><span class="sxs-lookup"><span data-stu-id="ce385-132">To specify an app URL in the allowed and blocked apps list, use the following format:</span></span>

<span data-ttu-id="ce385-133">Suchen Sie im [Windows Phone Store](https://www.microsoft.com/store/apps/windows-phone) nach der App, die Sie verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="ce385-133">From the [Windows Phone Store](https://www.microsoft.com/store/apps/windows-phone) page, search for the app that you want to use.</span></span>

<span data-ttu-id="ce385-134">Öffnen Sie die Seite der App, und kopieren Sie die URL in die Zwischenablage.</span><span class="sxs-lookup"><span data-stu-id="ce385-134">Open the app’s page, and copy the URL to the clipboard.</span></span> <span data-ttu-id="ce385-135">Sie können diese URL nun in der Liste kompatibler oder nicht kompatibler Apps verwenden.</span><span class="sxs-lookup"><span data-stu-id="ce385-135">You can now use this as the URL in either the allowed or blocked apps list.</span></span>

<span data-ttu-id="ce385-136">Beispiel: Durchsuchen Sie den Store nach der Skype-App.</span><span class="sxs-lookup"><span data-stu-id="ce385-136">Example: Search the store for the Skype app.</span></span> <span data-ttu-id="ce385-137">Die URL, die Sie verwenden, ist **http://www.windowsphone.com/store/app/skype/c3f8e570-68b3-4d6a-bdbb-c0a3f4360a51**.</span><span class="sxs-lookup"><span data-stu-id="ce385-137">The URL you use will be **http://www.windowsphone.com/store/app/skype/c3f8e570-68b3-4d6a-bdbb-c0a3f4360a51**.</span></span>



### <a name="additional-options"></a><span data-ttu-id="ce385-138">Zusätzliche Optionen</span><span class="sxs-lookup"><span data-stu-id="ce385-138">Additional options</span></span>

<span data-ttu-id="ce385-139">Sie können auch auf **Importieren** klicken, um die Liste mithilfe einer CSV-Datei im Format <*App-URL*>, <*App-Name*>, <*App-Herausgeber*> aufzufüllen. Sie können auch auf **Exportieren** klicken, um eine CSV-Datei mit dem Inhalt der Liste der eingeschränkten Apps im gleichen Format zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="ce385-139">You can also click **Import** to populate the list from a csv file in the format <*app url*>, <*app name*>, <*app publisher*> or click **Export** to create a csv file containing the contents of the restricted apps list in the same format.</span></span>


## <a name="browser"></a><span data-ttu-id="ce385-140">Browser</span><span class="sxs-lookup"><span data-stu-id="ce385-140">Browser</span></span>

-   <span data-ttu-id="ce385-141">**Webbrowser:** Erlaubt oder sperrt die Verwendung des integrierten Webbrowsers auf Geräten.</span><span class="sxs-lookup"><span data-stu-id="ce385-141">**Web browser** - Enables or blocks the built-in web browser on devices.</span></span>

## <a name="cellular-and-connectivity"></a><span data-ttu-id="ce385-142">Mobilfunk und Konnektivität</span><span class="sxs-lookup"><span data-stu-id="ce385-142">Cellular and Connectivity</span></span>

-   <span data-ttu-id="ce385-143">**WLAN:** Aktiviert oder deaktiviert die WLAN-Funktionalität des Geräts.</span><span class="sxs-lookup"><span data-stu-id="ce385-143">**Wi-Fi** - Enables or disables the Wi-Fi functionality of the device.</span></span>
-   <span data-ttu-id="ce385-144">**WLAN-Tethering:** Erlaubt die Verwendung des WLAN-Tetherings auf dem Gerät.</span><span class="sxs-lookup"><span data-stu-id="ce385-144">**Wi-Fi tethering** - Enables the use of Wi-Fi tethering on the device.</span></span>
-   <span data-ttu-id="ce385-145">**Automatische Verbindung mit WLAN-Hotspots herstellen:** Erlaubt, dass das Gerät automatisch eine Verbindung mit unverschlüsselten WLAN-Hotspots herstellen und die Geschäftsbedingungen für die Verbindung automatisch akzeptieren kann.</span><span class="sxs-lookup"><span data-stu-id="ce385-145">**Automatically connect to Wi-Fi hotspots** - Enables the device to automatically connect to free Wi-Fi hotspots and automatically accept any terms of use.</span></span>
-   <span data-ttu-id="ce385-146">**WLAN-Hotspotmeldung:** Sendet Informationen über WLAN-Verbindungen, um nahegelegene Verbindungen zu ermitteln.</span><span class="sxs-lookup"><span data-stu-id="ce385-146">**Wi-Fi hotspot reporting** - Sends information about Wi-Fi connections to help the user discover nearby connections.</span></span>
-   <span data-ttu-id="ce385-147">**NFC:** Aktiviert oder deaktiviert Vorgänge, die NFC (Near Field Communication, Nahfeldkommunikation) verwenden, sofern dies vom Gerät unterstützt wird.</span><span class="sxs-lookup"><span data-stu-id="ce385-147">**NFC** - Enables or disables operations that use near field communication on devices that support it.</span></span>
-   <span data-ttu-id="ce385-148">**Bluetooth:** Aktiviert oder deaktiviert die Bluetooth-Funktionalität des Geräts.</span><span class="sxs-lookup"><span data-stu-id="ce385-148">**Bluetooth** - Enables or disables the Bluetooth functionality of the device.</span></span>
