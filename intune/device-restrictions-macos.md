---
title: "Einstellungen für Geräteeinschränkungen für macOS"
titlesuffix: Azure portal
description: "In diesem Artikel lernen Sie die Intune-Einstellungen zur Steuerung von Geräteeinstellungen und -funktionen auf macOS-Geräten kennen."
keywords: 
author: vhorne
ms.author: victorh
manager: angrobe
ms.date: 08/01/2017
ms.topic: article
ms.prod: 
ms.service: microsoft-intune
ms.technology: 
ms.assetid: 3129cbaf-96c2-4837-8907-ca87a605a496
ms.reviewer: heenamac
ms.suite: ems
ms.custom: intune-azure
ms.openlocfilehash: d37b839bdd434c1a90d54e83f391e236205eb7d2
ms.sourcegitcommit: 2459bfda07a2afd2cfcd94a1972a3fb2e565ce8d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2018
---
# <a name="macos-device-restriction-settings-in-microsoft-intune"></a><span data-ttu-id="4014f-103">Einstellungen für Geräteeinschränkungen für macOS-Geräte in Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="4014f-103">macOS device restriction settings in Microsoft Intune</span></span>

[!INCLUDE [azure_portal](./includes/azure_portal.md)]

<span data-ttu-id="4014f-104">Verwenden Sie diese Einstellungen zum Verwalten von macOS-Geräten in einem Geräteeinschränkungsprofil.</span><span class="sxs-lookup"><span data-stu-id="4014f-104">Use these settings to manage macOS devices in a device restriction profile.</span></span>

## <a name="password"></a><span data-ttu-id="4014f-105">Kennwort</span><span class="sxs-lookup"><span data-stu-id="4014f-105">Password</span></span>
-   <span data-ttu-id="4014f-106">**Kennwort:** Der Endbenutzer muss ein Kennwort eingeben, um auf das Gerät zugreifen zu können.</span><span class="sxs-lookup"><span data-stu-id="4014f-106">**Password** - Require the end user to enter a password to access the device.</span></span>
    -   <span data-ttu-id="4014f-107">**Erforderlicher Kennworttyp:** Geben Sie an, ob das Kennwort rein numerisch sein darf oder ob es alphanumerisch sein muss (also Buchstaben und Zahlen enthalten muss).</span><span class="sxs-lookup"><span data-stu-id="4014f-107">**Required password type** - Specify whether the password can be Numeric only, or whether it must be Alphanumeric (contain letters and numbers).</span></span> <span data-ttu-id="4014f-108">Diese Einstellung wird lediglich unter Mac OS X 10.10.3 und höher unterstützt.</span><span class="sxs-lookup"><span data-stu-id="4014f-108">This setting is supported only on Mac OS X version 10.10.3 and later.</span></span>
    -   <span data-ttu-id="4014f-109">**Anzahl nicht alphanumerischer Zeichen im Kennwort:** Geben Sie die erforderliche Anzahl komplexer Zeichen im Kennwort an (**0** bis **4**).</span><span class="sxs-lookup"><span data-stu-id="4014f-109">**Number of non-alphanumeric characters in password** - Specify the number of complex characters required in the password (**0** to **4**).</span></span><br><span data-ttu-id="4014f-110">Bei einem komplexen Zeichen handelt es sich um ein Symbol, wie **?**</span><span class="sxs-lookup"><span data-stu-id="4014f-110">A complex character is a symbol, like **?**</span></span>
    -   <span data-ttu-id="4014f-111">**Minimale Kennwortlänge:** Geben Sie die Mindestanzahl von Zeichen an, die Benutzer für das Kennwort festlegen müssen (zwischen **4** und **16** Zeichen).</span><span class="sxs-lookup"><span data-stu-id="4014f-111">**Minimum password length** - Enter the minimum length of password a user must configure (between **4** and **16** characters).</span></span>
    -   <span data-ttu-id="4014f-112">**Einfache Kennwörter:** Erlauben Sie die Verwendung einfacher Kennwörter wie **0000** oder **1234**.</span><span class="sxs-lookup"><span data-stu-id="4014f-112">**Simple passwords** - Allow the use of simple passwords such as **0000** or **1234**.</span></span>
    -   <span data-ttu-id="4014f-113">**Maximaler Zeitraum der Bildschirmsperre (in Minuten) bis zur Anforderung eines Kennworts:** Geben Sie an, wie lange der Computer inaktiv sein muss, bevor er mithilfe eines Kennworts entsperrt werden muss.</span><span class="sxs-lookup"><span data-stu-id="4014f-113">**Maximum minutes after screen lock before password is required** - Specify how long the computer must be inactive before a password is required to unlock it.</span></span>
    -   <span data-ttu-id="4014f-114">**Maximaler Zeitraum der Inaktivität (in Minuten) bis zur Bildschirmsperrung:** Geben Sie die Zeitdauer an, die der Computer inaktiv sein muss, bevor der Bildschirms gesperrt wird.</span><span class="sxs-lookup"><span data-stu-id="4014f-114">**Maximum minutes of inactivity until screen locks** - Specify the length of time that the computer must be idle before the screen locks.</span></span>
    -   <span data-ttu-id="4014f-115">**Kennwortablauf (Tage):** Geben Sie an, nach wie vielen Tagen der Benutzer das Kennwort ändern muss (**1** bis **255** Tage).</span><span class="sxs-lookup"><span data-stu-id="4014f-115">**Password expiration (days)** - Specify how many days elapse before the user must change the password (**1** to **255** days).</span></span>
    -   <span data-ttu-id="4014f-116">**Wiederverwendung vorheriger Kennwörter verhindern:** Geben Sie die Anzahl von vorherigen Kennwörtern an, die nicht erneut verwendet werden dürfen (**1** bis **24**).</span><span class="sxs-lookup"><span data-stu-id="4014f-116">**Prevent reuse of previous passwords** - Specify the number of previously used passwords that cannot be reused (**1** to **24**).</span></span>

## <a name="restricted-apps"></a><span data-ttu-id="4014f-117">Eingeschränkte Apps</span><span class="sxs-lookup"><span data-stu-id="4014f-117">Restricted apps</span></span>

<span data-ttu-id="4014f-118">In der Liste der eingeschränkten Apps können Sie eine der folgenden Listen konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="4014f-118">In the restricted apps list, you can configure one of the following lists:</span></span>

<span data-ttu-id="4014f-119">**Unzulässige Apps:** Listet die (nicht von Intune verwalteten) Apps auf, die Benutzer nicht installieren und ausführen dürfen.</span><span class="sxs-lookup"><span data-stu-id="4014f-119">A **Prohibited apps** list - List the apps (not managed by Intune) that users are not allowed to install and run.</span></span>
<span data-ttu-id="4014f-120">**Genehmigte Apps:** Listet die Apps auf, die Benutzer installieren dürfen.</span><span class="sxs-lookup"><span data-stu-id="4014f-120">An **Approved apps** list - List the apps that users are allowed to install.</span></span> <span data-ttu-id="4014f-121">Um die Kompatibilität zu gewährleisten, dürfen Benutzer keine Apps installieren, die in dieser Liste nicht aufgeführt sind.</span><span class="sxs-lookup"><span data-stu-id="4014f-121">To remain compliant, users must not install apps that are not listed.</span></span> <span data-ttu-id="4014f-122">Apps, die von Intune verwaltet werden, sind automatisch zugelassen.</span><span class="sxs-lookup"><span data-stu-id="4014f-122">Apps that are managed by Intune are automatically allowed.</span></span>

<span data-ttu-id="4014f-123">Klicken Sie zum Konfigurieren einer Liste auf **Hinzufügen**. Geben Sie dann einen Namen Ihrer Wahl sowie optional den Herausgeber der App und die Paket-ID der App an (z.B. *com.apple.calculator*).</span><span class="sxs-lookup"><span data-stu-id="4014f-123">To configure the list, click **Add**, then specify a name of your choice, optionally the app publisher, and the bundle ID of the app (for example *com.apple.calculator*).</span></span>

## <a name="domains"></a><span data-ttu-id="4014f-124">Domains</span><span class="sxs-lookup"><span data-stu-id="4014f-124">Domains</span></span>

### <a name="unmarked-email-domains"></a><span data-ttu-id="4014f-125">Nicht markierte E-Mail-Domänen</span><span class="sxs-lookup"><span data-stu-id="4014f-125">Unmarked email domains</span></span>

<span data-ttu-id="4014f-126">Fügen Sie im Feld **E-Mail-Domänen-URL** eine oder mehrere URLs der Liste hinzu.</span><span class="sxs-lookup"><span data-stu-id="4014f-126">In the **Email Domain URL** field, add one or more URLs to the list.</span></span> <span data-ttu-id="4014f-127">Wenn Endbenutzer eine E-Mail von einer anderen Domäne als einer erhalten, die Sie konfiguriert haben, wird die E-Mail in der iOS-Mail-App als nicht vertrauenswürdig gekennzeichnet.</span><span class="sxs-lookup"><span data-stu-id="4014f-127">When end users receive an email from a domain other than one you configured, the email is marked as untrusted in the iOS Mail app.</span></span>

